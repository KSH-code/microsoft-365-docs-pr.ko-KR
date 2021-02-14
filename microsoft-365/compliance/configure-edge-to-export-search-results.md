---
title: Microsoft Edge에서 eDiscovery 내보내기 도구 사용
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: how-to
ms.service: O365-seccomp
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
description: 보안 및 ClickOnce 센터에서 콘텐츠 검색 및 eDiscovery에서 검색 결과를 다운로드하려면 최신 버전의 Microsoft Edge를 사용하려면 지원 센터를 사용하도록 설정해야 합니다.
ms.openlocfilehash: 60f42d2884c56aaff40bc0a6a979e99698a3cd2e
ms.sourcegitcommit: 27daadad9ca0f02a833ff3cff8a574551b9581da
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/12/2020
ms.locfileid: "47546822"
---
# <a name="use-the-ediscovery-export-tool-in-microsoft-edge"></a><span data-ttu-id="75b76-103">Microsoft Edge에서 eDiscovery 내보내기 도구 사용</span><span class="sxs-lookup"><span data-stu-id="75b76-103">Use the eDiscovery Export Tool in Microsoft Edge</span></span>

<span data-ttu-id="75b76-104">최신 버전의 Microsoft Edge가 최근 변경되어 기본적으로 ClickOnce 지원이 더 이상 사용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="75b76-104">As a result of recent changes to the newest version of Microsoft Edge, ClickOnce support is no longer enabled by default.</span></span> <span data-ttu-id="75b76-105">eDiscovery 내보내기 도구를 사용하여 콘텐츠 검색 또는 eDiscovery 검색 결과를 다운로드하려면 Microsoft Internet Explorer 또는 최신 버전의 [Microsoft](https://support.microsoft.com/help/17621/internet-explorer-downloads) Edge에서 ClickOnce 지원을 사용하도록 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="75b76-105">To continue using the eDiscovery Export Tool to download Content Search or eDiscovery search results, you either need to use [Microsoft Internet Explorer](https://support.microsoft.com/help/17621/internet-explorer-downloads) or enable ClickOnce support in the newest version of Microsoft Edge.</span></span>

## <a name="enable-clickonce-support-in-microsoft-edge"></a><span data-ttu-id="75b76-106">Microsoft Edge에서 ClickOnce 지원 사용</span><span class="sxs-lookup"><span data-stu-id="75b76-106">Enable ClickOnce support in Microsoft Edge</span></span>

1. <span data-ttu-id="75b76-107">Microsoft Edge에서 다음 **edge://flags/#edge-click-once.**</span><span class="sxs-lookup"><span data-stu-id="75b76-107">In Microsoft Edge, go to **edge://flags/#edge-click-once**.</span></span>

2. <span data-ttu-id="75b76-108">기존 값이 드롭다운 목록에서 **Default** 또는 **Disabled로** 설정된 경우 해당 값을 **Enabled로 변경합니다.**</span><span class="sxs-lookup"><span data-stu-id="75b76-108">If the existing value is set to **Default** or **Disabled** in the dropdown list, change it to **Enabled**.</span></span>

   ![드롭다운 목록에서 사용 선택](../media/ClickOnceimage1.png)

3. <span data-ttu-id="75b76-110">브라우저 창 아래쪽으로 스크롤한 다음  다시 시작을 클릭하여 Edge를 다시 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="75b76-110">Scroll down to the bottom of the browser window and click **Restart** to restart Edge.</span></span>

   ![다시 시작을 클릭합니다.](../media/ClickOnceimage2.png)

<span data-ttu-id="75b76-112">**참고:** 조직에서는 그룹 정책을 사용하여 조직에서 지원을 ClickOnce 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="75b76-112">**Note:** Organizations can use Group Policy to disable ClickOnce support.</span></span> <span data-ttu-id="75b76-113">지원에 대한 조직 정책이 ClickOnce 확인을 위해 **edge://policy.**</span><span class="sxs-lookup"><span data-stu-id="75b76-113">To check if there is an organizational policy for ClickOnce support, go to **edge://policy**.</span></span> <span data-ttu-id="75b76-114">다음 스크린샷은 전체 ClickOnce 사용하도록 설정되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="75b76-114">The following screenshot shows that ClickOnce is enabled across the entire organization.</span></span> <span data-ttu-id="75b76-115">이 정책 값이 **false로** 설정된 경우 조직의 관리자에게 문의해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="75b76-115">If this policy value is set to **false**, you will need to contact an admin in your organization.</span></span>

![에지 조직 정책 목록](../media/ClickOnceimage3.png)

## <a name="install-and-run-the-ediscovery-export-tool"></a><span data-ttu-id="75b76-117">eDiscovery 내보내기 도구 설치 및 실행</span><span class="sxs-lookup"><span data-stu-id="75b76-117">Install and run the eDiscovery Export Tool</span></span>

1. <span data-ttu-id="75b76-118">콘텐츠 **검색 또는** eDiscovery 사례에서 내보내기 플라이아웃 페이지에서 결과 다운로드를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="75b76-118">Click **Download results** on the flyout page of an export in Content Search or an eDiscovery case.</span></span>

   ![플라이아웃 페이지에서 결과 다운로드를 클릭하여 검색 결과 다운로드](../media/ClickOnceExport1.png)

2. <span data-ttu-id="75b76-120">도구를 실행하라는 확인 메시지가 표시됩니다. **열기.**</span><span class="sxs-lookup"><span data-stu-id="75b76-120">You will be prompted with a confirmation to launch the tool, Click **Open**.</span></span>

   ![열기를 클릭하여 eDiscovery 내보내기 도구를 실행합니다.](../media/ClickOnceimage4.png)

   <span data-ttu-id="75b76-122">eDiscovery 내보내기 도구가 설치되어 있지 않은 경우 보안 경고가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="75b76-122">If the eDiscovery Export Tool isn't installed, you will be prompted with a Security Warning,</span></span> 

   ![설치를 클릭하여 eDiscovery 내보내기 도구 설치](../media/ClickOnceimage5.png)

3. <span data-ttu-id="75b76-124">**설치** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="75b76-124">Click **Install**.</span></span> <span data-ttu-id="75b76-125">설치한 후 내보내기 도구가 자동으로 시작됩니다.</span><span class="sxs-lookup"><span data-stu-id="75b76-125">After it's installed, the export tool will launch automatically.</span></span>

<span data-ttu-id="75b76-126">자세한 내용은 아래 항목을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="75b76-126">For more information, see the following topics:</span></span>

- [<span data-ttu-id="75b76-127">콘텐츠 검색 결과 내보내기</span><span class="sxs-lookup"><span data-stu-id="75b76-127">Export Content Search results</span></span>](export-search-results.md)

- [<span data-ttu-id="75b76-128">Microsoft Edge에서 실험 플래그를 사용하도록 설정하는 방법</span><span class="sxs-lookup"><span data-stu-id="75b76-128">How to enable experiment flags in Microsoft Edge</span></span>](https://microsoftedgesupport.microsoft.com/hc/articles/360034075294-How-to-enable-experiment-flags-in-Microsoft-Edge-Insider-channels)
