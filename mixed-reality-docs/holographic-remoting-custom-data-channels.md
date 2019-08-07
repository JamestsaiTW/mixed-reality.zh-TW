---
title: 自訂全像攝影遠端資料通道
description: 自訂資料通道可以用來透過已建立的全像攝影遠端連線傳送使用者資料。
author: NPohl-MSFT
ms.author: nopohl
ms.date: 08/01/2019
ms.topic: article
keywords: HoloLens、遠端、全像攝影遠端
ms.openlocfilehash: 9f7f20023d496412b331606e03d0c5110bb4864f
ms.sourcegitcommit: ca949efe0279995a376750d89e23d7123eb44846
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/01/2019
ms.locfileid: "68718082"
---
# <a name="custom-holographic-remoting-data-channels"></a>自訂全像攝影遠端資料通道

>[!NOTE]
>本指導方針專屬於 HoloLens 2 上的全像攝影遠端處理。

使用自訂資料通道, 透過已建立的遠端連線傳送自訂資料。

>[!IMPORTANT]
>自訂資料通道需要自訂的主機應用程式和自訂播放機應用程式, 因為它允許兩個自訂應用程式之間的通訊。

>[!TIP]
>您可以在全像「全像」[遠端範例 github 存放庫](https://github.com/microsoft/MixedReality-HolographicRemoting-Samples)內的主機和播放機範例中找到簡單的乒乓球範例。 在```#define ENABLE_CUSTOM_DATA_CHANNEL_SAMPLE``` SampleHostMain/SamplePlayerMain 檔案內取消批註, 以啟用範例程式碼。


# <a name="create-a-custom-data-channel"></a>建立自訂資料通道


若要建立自訂資料通道, 需要下欄欄位:
```cpp
std::recursive_mutex m_customDataChannelLock;
winrt::Microsoft::Holographic::AppRemoting::IDataChannel m_customDataChannel = nullptr;
winrt::Microsoft::Holographic::AppRemoting::IDataChannel::OnDataReceived_revoker m_customChannelDataReceivedEventRevoker;
winrt::Microsoft::Holographic::AppRemoting::IDataChannel::OnClosed_revoker m_customChannelClosedEventRevoker;
```

成功建立連接之後, 就可以從主機端和 (或) 播放程式端起始新的資料通道建立。 RemoteCoNtext 和 PlayerCoNtext 都提供```CreateDataChannel()```方法來執行這項操作。 第一個參數是通道識別碼, 用來識別 susequent 作業中的資料通道。 第二個參數是優先順序, 指定此通道的資料傳輸到另一端的優先順序。 通道識別碼的有效範圍為0到 (含), 最多為主機端 63, 包括玩家端的127和64。 有效的優先順序```Low```為```Medium``` 、 ```High```或 (兩端)。

若要起始在**主機**端建立資料通道:
```cpp
// Valid channel ids for channels created on the host side are 0 up to and including 63
m_remoteContext.CreateDataChannel(0, DataChannelPriority::Low);
```

若要起始在**播放**端建立資料通道:
```cpp
// Valid channel ids for channels created on the player side are 64 up to and including 127
m_playerContext.CreateDataChannel(64, DataChannelPriority::Low);
```

>[!NOTE]
>若要建立新的自訂資料通道, 只有一個側邊 (主機或玩家) 需要呼叫```CreateDataChannel```方法。

## <a name="handling-custom-data-channel-events"></a>處理自訂資料通道事件

若要建立自訂資料通道, ```OnDataChannelCreated```必須處理事件 (在 player 和主機端上)。 它會在使用者資料通道已由任一端建立時觸發, 並提供```IDataChannel```物件, 可用來透過此通道傳送和接收資料。

若要在```OnDataChannelCreated```事件上註冊接聽程式:
```cpp
m_onDataChannelCreatedEventRevoker = m_remoteContext.OnDataChannelCreated(winrt::auto_revoke,
    [this](const IDataChannel& dataChannel, uint8_t channelId)
    {
        std::lock_guard lock(m_customDataChannelLock);
        m_customDataChannel = dataChannel;

        // Register to OnDataReceived and OnClosed event of the data channel here, see below...
    });
```

若要在收到資料時收到通知, 請在```OnDataReceived``` ```OnDataChannelCreated```處理常式所```IDataChannel```提供的物件上註冊事件。 註冊至```OnClosed```事件, 以在資料通道關閉時收到通知。

```cpp
m_customChannelDataReceivedEventRevoker = m_customDataChannel.OnDataReceived(winrt::auto_revoke, 
    [this]()
    {
        // React on data received via the custom data channel here.
    });

m_customChannelClosedEventRevoker = m_customDataChannel.OnClosed(winrt::auto_revoke,
    [this]()
    {
        // React on data channel closed here.

        std::lock_guard lock(m_customDataChannelLock);
        if (m_customDataChannel)
        {
            m_customDataChannel = nullptr;
        }
    });
```

## <a name="sending-data"></a>傳送資料

若要透過自訂資料通道傳送資料, 請```IDataChannel::SendData()```使用方法。 第一個參數是```winrt::array_view<const uint8_t>```應傳送之資料的。 第二個參數指定指出應重新傳送資料, 直到另一端認可接收為止。 

>[!IMPORTANT]
>萬一發生網路狀況不佳的情況, 相同的資料封包可能會抵達一次以上。 接收程式碼必須能夠處理這種情況。

```cpp
uint8_t data[] = {1};
m_customDataChannel.SendData(data, true);
```

## <a name="closing-a-custom-data-channel"></a>關閉自訂資料通道

若要關閉自訂資料通道, 請```IDataChannel::Close()```使用方法。 一旦自訂資料通道關閉後```OnClosed``` , 事件就會通知雙方。

```cpp
m_customDataChannel.Close();
```

## <a name="see-also"></a>另請參閱
* [撰寫全像的遠端主機應用程式](holographic-remoting-create-host.md)
* [撰寫自訂的全像遠端播放播放機應用程式](holographic-remoting-create-player.md)
* [全像攝影遠端疑難排解和限制](holographic-remoting-troubleshooting.md)
* [全像攝影遠端軟體授權條款](https://docs.microsoft.com/en-us/legal/mixed-reality/microsoft-holographic-remoting-software-license-terms)
* [Microsoft 隱私權聲明](https://go.microsoft.com/fwlink/?LinkId=521839)