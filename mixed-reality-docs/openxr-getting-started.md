---
title: 開始使用 OpenXR
description: 開始使用 Windows Mixed Reality 和 HoloLens 2 耳機上的可移植 OpenXR API 標準。
author: thetuvix
ms.author: alexturn
ms.date: 2/28/2020
ms.topic: article
keywords: OpenXR，Khronos，BasicXRApp，windows Mixed Reality OpenXR 開發人員入口網站，DirectX，原生，原生應用程式，自訂引擎，中介軟體，開始使用，101，預覽延伸模組
ms.openlocfilehash: 7a210ce25d1e7c22710f1029aca2ca7f55a8b71c
ms.sourcegitcommit: 9de2cb11321e6517db69e8c93459a205900a2174
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/24/2020
ms.locfileid: "80163332"
---
# <a name="getting-started-with-openxr"></a><span data-ttu-id="9c788-104">開始使用 OpenXR</span><span class="sxs-lookup"><span data-stu-id="9c788-104">Getting started with OpenXR</span></span>

<span data-ttu-id="9c788-105">您可以使用 OpenXR 在 HoloLens 2 或 Windows Mixed Reality 沉浸式耳機桌面上進行開發。</span><span class="sxs-lookup"><span data-stu-id="9c788-105">You can develop using OpenXR on a HoloLens 2 or Windows Mixed Reality immersive headset on the desktop.</span></span>  <span data-ttu-id="9c788-106">如果您沒有頭戴式裝置的存取權，您可以改用 HoloLens 2 模擬器或 Windows Mixed Reality 模擬器。</span><span class="sxs-lookup"><span data-stu-id="9c788-106">If you don't have access to a headset, you can use the HoloLens 2 Emulator or the Windows Mixed Reality Simulator instead.</span></span>

## <a name="getting-started-with-openxr-for-hololens-2"></a><span data-ttu-id="9c788-107">適用于 HoloLens 2 的 OpenXR 入門</span><span class="sxs-lookup"><span data-stu-id="9c788-107">Getting started with OpenXR for HoloLens 2</span></span>

<span data-ttu-id="9c788-108">若要開始開發 HoloLens 2 的 OpenXR 應用程式：</span><span class="sxs-lookup"><span data-stu-id="9c788-108">To start developing OpenXR applications for HoloLens 2:</span></span>

1. <span data-ttu-id="9c788-109">設定 HoloLens 2 或遵循指示來[安裝最新版本的 hololens 2 模擬器](using-the-hololens-emulator.md)。</span><span class="sxs-lookup"><span data-stu-id="9c788-109">Set up a HoloLens 2 or follow the instructions to [install a recent version of the HoloLens 2 emulator](using-the-hololens-emulator.md).</span></span>  <span data-ttu-id="9c788-110">如果您的裝置最近已更新其 OS，或者您使用的是最新的模擬器映射，您應該已準備好 OpenXR 1.0。</span><span class="sxs-lookup"><span data-stu-id="9c788-110">If your device has updated its OS recently or if you're using a recent emulator image, you should already have OpenXR 1.0 ready to go.</span></span>
1. <span data-ttu-id="9c788-111">若要確定您已具備所有[延伸](openxr.md#roadmap)模組的最新 OpenXR 執行時間，請從裝置或模擬器內啟動 Store 應用程式，開啟右上方的功能表，按一下 [**下載和更新**]，然後按一下 [**取得更新**]。</span><span class="sxs-lookup"><span data-stu-id="9c788-111">To make sure you've got the latest OpenXR runtime with all [extensions](openxr.md#roadmap) present, launch the Store app from within the device or emulator, open the menu in the upper-right, click **Downloads and updates** and click **Get updates**.</span></span>  <span data-ttu-id="9c788-112">這可確保 HoloLens 上的 OpenXR 執行時間是最新的。</span><span class="sxs-lookup"><span data-stu-id="9c788-112">This ensures that the OpenXR runtime on your HoloLens is up to date.</span></span>  <span data-ttu-id="9c788-113">請注意，如果您使用模擬器，模擬器映射會在您每次啟動時重設，因此最好的辦法就是確定您擁有[最新版的 HoloLens 2 模擬器映射](using-the-hololens-emulator.md)。</span><span class="sxs-lookup"><span data-stu-id="9c788-113">Note that if you're using the emulator, the emulator image will reset each time you start it, and so your best bet is to just make sure that you have [the latest version of the HoloLens 2 emulator image](using-the-hololens-emulator.md).</span></span>

## <a name="getting-started-with-openxr-for-windows-mixed-reality-headsets"></a><span data-ttu-id="9c788-114">開始使用 OpenXR for Windows Mixed Reality 耳機</span><span class="sxs-lookup"><span data-stu-id="9c788-114">Getting started with OpenXR for Windows Mixed Reality headsets</span></span>

<span data-ttu-id="9c788-115">若要開始開發沉浸式 Windows Mixed Reality 耳機的 OpenXR 應用程式：</span><span class="sxs-lookup"><span data-stu-id="9c788-115">To start developing OpenXR applications for immersive Windows Mixed Reality headsets:</span></span>

1. <span data-ttu-id="9c788-116">請確定您至少執行 Windows 10 5 月2019更新（1903），這是 Windows Mixed Reality 終端使用者執行 OpenXR 應用程式的最低需求。</span><span class="sxs-lookup"><span data-stu-id="9c788-116">Be sure you are running at least the Windows 10 May 2019 Update (1903), which is the minimum requirement for Windows Mixed Reality end users to run OpenXR applications.</span></span>  <span data-ttu-id="9c788-117">如果您是在舊版的 Windows 10 上，您可以使用<a href="https://www.microsoft.com/software-download/windows10" target="_blank">windows 10 更新</a>小幫手進行升級。</span><span class="sxs-lookup"><span data-stu-id="9c788-117">If you're on an earlier version of Windows 10, you can upgrade by using the <a href="https://www.microsoft.com/software-download/windows10" target="_blank">Windows 10 Update Assistant</a>.</span></span>
2. <span data-ttu-id="9c788-118">設定 Windows Mixed Reality 耳機，或遵循指示[啟用 Windows Mixed reality](using-the-windows-mixed-reality-simulator.md)模擬器。</span><span class="sxs-lookup"><span data-stu-id="9c788-118">Set up a Windows Mixed Reality headset or follow the instructions to [enable the Windows Mixed Reality simulator](using-the-windows-mixed-reality-simulator.md).</span></span>  <span data-ttu-id="9c788-119">當您設定 Windows Mixed Reality 時，混合現實入口網站會自動安裝 Windows Mixed Reality OpenXR 執行時間。</span><span class="sxs-lookup"><span data-stu-id="9c788-119">As you set up Windows Mixed Reality, Mixed Reality Portal will automatically install the Windows Mixed Reality OpenXR Runtime.</span></span>  <span data-ttu-id="9c788-120">然後，Microsoft Store 會讓執行時間保持在最新狀態。</span><span class="sxs-lookup"><span data-stu-id="9c788-120">The Microsoft Store will then keep the runtime up to date.</span></span>
3. <span data-ttu-id="9c788-121">從 [開始] 功能表啟動混合現實入口網站，然後按一下 [...]，讓 Windows Mixed Reality OpenXR 執行時間變成作用中功能表左下方選取 [設定 OpenXR]。</span><span class="sxs-lookup"><span data-stu-id="9c788-121">Make the Windows Mixed Reality OpenXR Runtime active by launching Mixed Reality Portal from the Start menu, clicking the ... menu in the lower-left and selecting "Set up OpenXR".</span></span><br>
<span data-ttu-id="9c788-122">![在混合現實入口網站中設定 OpenXR](images/mixed-reality-portal-set-up-openxr.png)</span><span class="sxs-lookup"><span data-stu-id="9c788-122">![Setting up OpenXR in the Mixed Reality Portal](images/mixed-reality-portal-set-up-openxr.png)</span></span>

<span data-ttu-id="9c788-123">如果您需要讓 Windows Mixed Reality OpenXR 執行時間再次生效，請重複步驟3。</span><span class="sxs-lookup"><span data-stu-id="9c788-123">If you ever need to make the Windows Mixed Reality OpenXR Runtime active again, repeat step 3.</span></span>

> [!NOTE]
> <span data-ttu-id="9c788-124">Windows Mixed Reality OpenXR 執行時間很快就會自動為所有 Windows Mixed Reality 使用者進行作用。</span><span class="sxs-lookup"><span data-stu-id="9c788-124">The Windows Mixed Reality OpenXR Runtime will soon be made active automatically for all Windows Mixed Reality end users.</span></span>

## <a name="getting-the-windows-mixed-reality-openxr-developer-portal"></a><span data-ttu-id="9c788-125">取得 Windows Mixed Reality OpenXR 開發人員入口網站</span><span class="sxs-lookup"><span data-stu-id="9c788-125">Getting the Windows Mixed Reality OpenXR Developer Portal</span></span>

<span data-ttu-id="9c788-126">若要試用 Windows Mixed Reality OpenXR 執行時間，您可以安裝<a href="https://www.microsoft.com/store/productId/9n5cvvl23qbt" target="_blank">Mixed Reality OpenXR 開發人員入口網站應用程式</a>。</span><span class="sxs-lookup"><span data-stu-id="9c788-126">To try out the Windows Mixed Reality OpenXR Runtime, you can install the <a href="https://www.microsoft.com/store/productId/9n5cvvl23qbt" target="_blank">Mixed Reality OpenXR Developer Portal app</a>.</span></span>  <span data-ttu-id="9c788-127">此應用程式提供的示範場景會演練 OpenXR 的各種功能，以及提供作用中執行時間和目前耳機的重要資訊的 [系統狀態] 頁面。</span><span class="sxs-lookup"><span data-stu-id="9c788-127">This app provides a demo scene that exercises various features of OpenXR, along with a System Status page that provides key information about the active runtime and the current headset.</span></span>

<span data-ttu-id="9c788-128">如果使用模擬器，安裝混合現實 OpenXR 開發人員入口網站的最簡單方式是使用[Windows 裝置入口網站](using-the-windows-device-portal.md)，方法是流覽至 [OpenXR] 頁面，然後按一下 [開發人員功能] 底下的 [安裝] 按鈕。</span><span class="sxs-lookup"><span data-stu-id="9c788-128">If using the emulator, the easiest way to install the Mixed Reality OpenXR Developer Portal is using [Windows Device Portal](using-the-windows-device-portal.md), by navigating to the "OpenXR" page and then clicking the "Install" button under "Developer Features".</span></span> <span data-ttu-id="9c788-129">（這也適用于實體 HoloLens 2 裝置）</span><span class="sxs-lookup"><span data-stu-id="9c788-129">(this works on a physical HoloLens 2 device as well)</span></span>

![Mixed Reality OpenXR 開發人員入口網站應用程式](images/mixed-reality-openxr-developer-portal.png)

## <a name="building-a-sample-openxr-app"></a><span data-ttu-id="9c788-131">建立範例 OpenXR 應用程式</span><span class="sxs-lookup"><span data-stu-id="9c788-131">Building a sample OpenXR app</span></span>

<span data-ttu-id="9c788-132">如果您還沒有 OpenXR 開發所需的工具，請務必加以[安裝](install-the-tools.md)。</span><span class="sxs-lookup"><span data-stu-id="9c788-132">Be sure to [install the tools](install-the-tools.md) you'll need for OpenXR development if you haven't already.</span></span>

<span data-ttu-id="9c788-133"><a href="https://github.com/Microsoft/OpenXR-SDK-VisualStudio/tree/master/samples/BasicXrApp" target="_blank">BasicXrApp</a>專案示範一個簡單的 OpenXR 範例，其中包含兩個 Visual Studio 專案檔，一個用於 Win32 桌面應用程式，另一個用於 UWP HoloLens 2 應用程式。</span><span class="sxs-lookup"><span data-stu-id="9c788-133">The <a href="https://github.com/Microsoft/OpenXR-SDK-VisualStudio/tree/master/samples/BasicXrApp" target="_blank">BasicXrApp</a> project demonstrates a simple OpenXR sample with two Visual Studio project files, one for both a Win32 desktop app and one for a UWP HoloLens 2 app.</span></span>  <span data-ttu-id="9c788-134">因為解決方案包含 HoloLens UWP 專案，所以您需要安裝在 Visual Studio 中的[通用 Windows 平臺開發工作負載](install-the-tools.md#installation-checklist)，才能完全開啟它。</span><span class="sxs-lookup"><span data-stu-id="9c788-134">Because the solution contains a HoloLens UWP project, you'll need the [Universal Windows Platform development workload](install-the-tools.md#installation-checklist) installed in Visual Studio to fully open it.</span></span>

<span data-ttu-id="9c788-135">請注意，雖然 Win32 和 UWP 專案檔因封裝和部署的差異而不同，但每個專案內的應用程式代碼都是100% 的相同！</span><span class="sxs-lookup"><span data-stu-id="9c788-135">Note that while the Win32 and UWP project files are separate due to differences in packaging and deployment, the app code inside each project is 100% the same!</span></span>

<span data-ttu-id="9c788-136">建立 OpenXR 的 Win32 桌面之後。EXE，不論是 Windows Mixed Reality 耳機或任何其他耳機，您都可以在任何支援 OpenXR 的 desktop VR 平臺上搭配使用 VR 頭戴式裝置。</span><span class="sxs-lookup"><span data-stu-id="9c788-136">After building an OpenXR Win32 desktop .EXE, you can use it with a VR headset on any desktop VR platform that supports OpenXR, whether it's a Windows Mixed Reality headset or any other headset.</span></span>

<span data-ttu-id="9c788-137">建立 OpenXR UWP 應用程式套件之後，您可以將[該套件部署](using-visual-studio.md)到 hololens 2 裝置或 Hololens 2 模擬器。</span><span class="sxs-lookup"><span data-stu-id="9c788-137">After building an OpenXR UWP app package, you can [deploy that package](using-visual-studio.md) to either a HoloLens 2 device or the HoloLens 2 Emulator.</span></span>

## <a name="integrate-the-openxr-loader-into-a-project"></a><span data-ttu-id="9c788-138">將 OpenXR 載入器整合到專案中</span><span class="sxs-lookup"><span data-stu-id="9c788-138">Integrate the OpenXR loader into a project</span></span>

<span data-ttu-id="9c788-139">若要開始在現有的專案中使用 OpenXR，您將包含 OpenXR 載入器。</span><span class="sxs-lookup"><span data-stu-id="9c788-139">To get started with OpenXR in an existing project, you'll include the OpenXR loader.</span></span>  <span data-ttu-id="9c788-140">載入器會在裝置上探索作用中的 OpenXR 執行時間，並提供其所執行核心函式和擴充功能的存取權。</span><span class="sxs-lookup"><span data-stu-id="9c788-140">The loader discovers the active OpenXR runtime on the device and provides access to the core functions and extension functions that it implements.</span></span>

<span data-ttu-id="9c788-141">您可以從 Visual Studio 專案[參考官方的 OpenXR NuGet 套件](#reference-official-openxr-nuget-package)，或從 Khronos GitHub 存放庫中[包含官方的 OpenXR 載入器來源](#include-official-openxr-loader-source)。</span><span class="sxs-lookup"><span data-stu-id="9c788-141">You can either [reference the official OpenXR NuGet package](#reference-official-openxr-nuget-package) from your Visual Studio project or [include the official OpenXR loader source](#include-official-openxr-loader-source)  from the Khronos GitHub repo.</span></span>  <span data-ttu-id="9c788-142">任一種方法都可讓您存取 OpenXR 1.0 核心功能，加上發佈的 `KHR`、`EXT` 和 `MSFT` 延伸模組。</span><span class="sxs-lookup"><span data-stu-id="9c788-142">Either approach will give you access to OpenXR 1.0 core features, plus published `KHR`, `EXT` and `MSFT` extensions.</span></span>

<span data-ttu-id="9c788-143">如果您有興趣試驗 `MSFT_preview` 延伸模組，您可以從混合現實 GitHub 存放庫[複製預覽版 OpenXR 標頭](#using-preview-extensions)。</span><span class="sxs-lookup"><span data-stu-id="9c788-143">If you're interested to experiment with `MSFT_preview` extensions as well, you can [copy in preview OpenXR headers](#using-preview-extensions) from the Mixed Reality GitHub repo.</span></span>

### <a name="reference-official-openxr-nuget-package"></a><span data-ttu-id="9c788-144">參考官方 OpenXR NuGet 套件</span><span class="sxs-lookup"><span data-stu-id="9c788-144">Reference official OpenXR NuGet package</span></span>

<span data-ttu-id="9c788-145"><a href="https://www.nuget.org/packages/OpenXR.Loader/" target="_blank"> **OpenXR 載入**器 NuGet 封裝</a>是參考預先建立 OpenXR 載入器的最簡單方式。Visual Studio C++解決方案中的 DLL。</span><span class="sxs-lookup"><span data-stu-id="9c788-145">The <a href="https://www.nuget.org/packages/OpenXR.Loader/" target="_blank">**OpenXR.Loader** NuGet package</a> is the easiest way to reference a prebuilt OpenXR loader .DLL in your Visual Studio C++ solution.</span></span>  <span data-ttu-id="9c788-146">這可讓您存取 OpenXR 1.0 核心功能，加上發佈的 `KHR`、`EXT` 和 `MSFT` 延伸模組。</span><span class="sxs-lookup"><span data-stu-id="9c788-146">This will give you access to OpenXR 1.0 core features, plus published `KHR`, `EXT` and `MSFT` extensions.</span></span>

<span data-ttu-id="9c788-147">若要將 OpenXR 的 NuGet 套件參考新增至您的C++ Visual Studio 解決方案：</span><span class="sxs-lookup"><span data-stu-id="9c788-147">To add an OpenXR.Loader NuGet package reference to your Visual Studio C++ solution:</span></span>
1. <span data-ttu-id="9c788-148">在**方案總管**中，以滑鼠右鍵按一下要使用 OpenXR 的專案，然後選取 [**管理 NuGet 套件 ...** ]。</span><span class="sxs-lookup"><span data-stu-id="9c788-148">In **Solution Explorer**, right-click the project that will use OpenXR and select **Manage NuGet Packages...**.</span></span>
1. <span data-ttu-id="9c788-149">切換至 [**流覽**] 索引標籤，並搜尋**OpenXR**。</span><span class="sxs-lookup"><span data-stu-id="9c788-149">Switch to the **Browse** tab and search for **OpenXR.Loader**.</span></span>
1. <span data-ttu-id="9c788-150">選取**OpenXR 載入**器套件，然後按一下右邊詳細資料窗格中的 [安裝]。</span><span class="sxs-lookup"><span data-stu-id="9c788-150">Select the **OpenXR.Loader** package and click Install in the details pane to the right.</span></span>
1. <span data-ttu-id="9c788-151">按一下 [確定] 以接受專案的變更。</span><span class="sxs-lookup"><span data-stu-id="9c788-151">Click OK to accept the changes to your project.</span></span>
1. <span data-ttu-id="9c788-152">將 `#include <openxr/openxr.h>` 新增至來源檔案，以開始使用 OpenXR API。</span><span class="sxs-lookup"><span data-stu-id="9c788-152">Add `#include <openxr/openxr.h>` to a source file to start using the OpenXR API.</span></span>

<span data-ttu-id="9c788-153">若要查看作用中的 OpenXR API 範例，請參閱<a href="https://github.com/Microsoft/OpenXR-SDK-VisualStudio/tree/master/samples/BasicXrApp" target="_blank">BasicXrApp</a>範例應用程式。</span><span class="sxs-lookup"><span data-stu-id="9c788-153">To see an example of the OpenXR API in action, check out the <a href="https://github.com/Microsoft/OpenXR-SDK-VisualStudio/tree/master/samples/BasicXrApp" target="_blank">BasicXrApp</a> sample app.</span></span>

### <a name="include-official-openxr-loader-source"></a><span data-ttu-id="9c788-154">包含官方 OpenXR 載入器來源</span><span class="sxs-lookup"><span data-stu-id="9c788-154">Include official OpenXR loader source</span></span>

<span data-ttu-id="9c788-155">如果您想要自行建立載入器，例如避免額外的載入器。DLL，您可以將官方的 Khronos OpenXR 載入器來源提取到您的專案中。</span><span class="sxs-lookup"><span data-stu-id="9c788-155">If you want to build the loader yourself, for example to avoid the extra loader .DLL, you can pull the official Khronos OpenXR loader sources into your project.</span></span>  <span data-ttu-id="9c788-156">這可讓您存取 OpenXR 1.0 核心功能，加上發佈的 `KHR`、`EXT` 和 `MSFT` 延伸模組。</span><span class="sxs-lookup"><span data-stu-id="9c788-156">This will give you access to OpenXR 1.0 core features, plus published `KHR`, `EXT` and `MSFT` extensions.</span></span>

<span data-ttu-id="9c788-157">若要從這裡開始，請遵循<a href="https://github.com/KhronosGroup/OpenXR-SDK" target="_blank">GitHub 上的 Khronos OpenXR-SDK</a>存放庫中的指示。</span><span class="sxs-lookup"><span data-stu-id="9c788-157">To get started here, follow the instructions in the <a href="https://github.com/KhronosGroup/OpenXR-SDK" target="_blank">Khronos OpenXR-SDK repo on GitHub</a>.</span></span>  <span data-ttu-id="9c788-158">專案設定為以 CMake 建立-如果您使用 MSBuild，則需要將程式碼複製到您自己的專案。</span><span class="sxs-lookup"><span data-stu-id="9c788-158">The project is set up to build with CMake - if you are using MSBuild, you will need to copy to the code into your own project.</span></span>

## <a name="using-preview-extensions"></a><span data-ttu-id="9c788-159">使用預覽擴充功能</span><span class="sxs-lookup"><span data-stu-id="9c788-159">Using preview extensions</span></span>

<span data-ttu-id="9c788-160">[延伸模組藍圖](openxr.md#roadmap)中所列的 `MSFT_preview` 延伸模組是預覽的實驗廠商延伸模組，以收集意見反應。</span><span class="sxs-lookup"><span data-stu-id="9c788-160">The `MSFT_preview` extensions listed in the [extension roadmap](openxr.md#roadmap) are experimental vendor extensions being previewed to gather feedback.</span></span>  <span data-ttu-id="9c788-161">這些擴充功能僅適用于開發人員裝置，並會在真正的延伸模組隨附時移除。</span><span class="sxs-lookup"><span data-stu-id="9c788-161">These extensions are for developer devices only and will be removed when the real extension ships.</span></span>

<span data-ttu-id="9c788-162">如果您有興趣試用可用的 `MSFT_preview` 延伸模組，請執行下列步驟來更新您的專案：</span><span class="sxs-lookup"><span data-stu-id="9c788-162">If you're interested to try out the available `MSFT_preview` extensions, go through the following steps to update your project:</span></span>
1. <span data-ttu-id="9c788-163">遵循上述其中一種方法，將 OpenXR 載入器整合到您的專案中。</span><span class="sxs-lookup"><span data-stu-id="9c788-163">Follow either of the approaches above to integrate an OpenXR loader into your project.</span></span>
1. <span data-ttu-id="9c788-164">以<a href="https://github.com/microsoft/OpenXR-MixedReality/tree/master/openxr_preview/include/openxr" target="_blank">GitHub 上的 Mixed Reality OpenXR</a>存放庫中的預覽標頭取代您專案中的標準 OpenXR 標頭。</span><span class="sxs-lookup"><span data-stu-id="9c788-164">Replace the standard OpenXR headers in your project with the <a href="https://github.com/microsoft/OpenXR-MixedReality/tree/master/openxr_preview/include/openxr" target="_blank">preview headers from the Mixed Reality OpenXR repo on GitHub</a>.</span></span>

<span data-ttu-id="9c788-165">然後在目標 HoloLens 2 或桌上型電腦上啟用預覽延伸模組：</span><span class="sxs-lookup"><span data-stu-id="9c788-165">To then activate preview extensions on your target HoloLens 2 or desktop PC:</span></span>
  1. <span data-ttu-id="9c788-166">在目標裝置上啟用 Windows 裝置入口網站：</span><span class="sxs-lookup"><span data-stu-id="9c788-166">Enable Windows Device Portal on the target device:</span></span>
     * <span data-ttu-id="9c788-167">如果您的目標裝置是 HoloLens 2 裝置，請遵循目標裝置上的[這些指示](using-the-windows-device-portal.md)。</span><span class="sxs-lookup"><span data-stu-id="9c788-167">If your target device is a HoloLens 2 device, [follow these instructions](using-the-windows-device-portal.md) on the target device.</span></span>  <span data-ttu-id="9c788-168">請注意，這需要實體頭戴式裝置，因為 HoloLens 2 模擬器中的已知問題會讓下一個步驟中的 UI 無法出現在模擬器中。</span><span class="sxs-lookup"><span data-stu-id="9c788-168">Note that this requires a physical headset, as a known issue in the HoloLens 2 emulator will prevent the UI in the next step from appearing in the emulator.</span></span>
     * <span data-ttu-id="9c788-169">如果您的目標裝置是連接沉浸式耳機外設的桌上型電腦，請在目標桌上型電腦上<a href="https://docs.microsoft.com/windows/uwp/debug-test-perf/device-portal-desktop#set-up-device-portal-on-windows-desktop" target="_blank">遵循這些指示</a>。</span><span class="sxs-lookup"><span data-stu-id="9c788-169">If your target device is a desktop PC with an immersive headset peripheral attached, <a href="https://docs.microsoft.com/windows/uwp/debug-test-perf/device-portal-desktop#set-up-device-portal-on-windows-desktop" target="_blank">follow these instructions</a> on the target desktop PC.</span></span>
  1. <span data-ttu-id="9c788-170">流覽至左窗格中的 [ **OpenXR** ] 索引標籤，並啟用 [**使用最新的預覽 OpenXR 運行**時間]。</span><span class="sxs-lookup"><span data-stu-id="9c788-170">Navigate to the **OpenXR** tab in the left pane and enable **Use latest preview OpenXR runtime**.</span></span>  <span data-ttu-id="9c788-171">這會啟用您裝置上的預覽執行時間，其已啟用預覽延伸模組。</span><span class="sxs-lookup"><span data-stu-id="9c788-171">This enables the preview runtime on your device, which has preview extensions activated.</span></span>

<span data-ttu-id="9c788-172">如需這些預覽延伸模組的檔，以及如何使用它們的範例，請參閱<a href="https://github.com/Microsoft/OpenXR-MixedReality#openxr-preview-extensions" target="_blank">Mixed Reality OpenXR</a>存放庫。</span><span class="sxs-lookup"><span data-stu-id="9c788-172">See the <a href="https://github.com/Microsoft/OpenXR-MixedReality#openxr-preview-extensions" target="_blank">Mixed Reality OpenXR repo</a> for documentation of these preview extensions and samples of how to use them.</span></span>

## <a name="troubleshooting"></a><span data-ttu-id="9c788-173">疑難排解</span><span class="sxs-lookup"><span data-stu-id="9c788-173">Troubleshooting</span></span>

<span data-ttu-id="9c788-174">如果您在使用 OpenXR 開發時遇到問題，請查看我們的[疑難排解秘訣](openxr-troubleshooting.md)。</span><span class="sxs-lookup"><span data-stu-id="9c788-174">If you have trouble getting up and running with OpenXR development, check out our [troubleshooting tips](openxr-troubleshooting.md).</span></span>