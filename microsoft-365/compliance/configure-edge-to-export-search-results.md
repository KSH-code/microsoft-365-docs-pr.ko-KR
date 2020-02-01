---
title: Microsoft Edge에서 Office 365 eDiscovery 내보내기 도구 사용
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: article
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ROBOTS: NOINDEX, NOFOLLOW
description: 보안 및 준수 센터에서 콘텐츠 검색 및 eDiscovery의 검색 결과를 내보내려면 Microsoft Edge를 사용 하 여 ClickOnce 지원을 사용 하도록 설정 해야 합니다.
ms.openlocfilehash: 896d39d81fa56b3a118b2bee450476e422ac3921
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/29/2020
ms.locfileid: "41595735"
---
# <a name="use-the-office-365-ediscovery-export-tool-in-microsoft-edge"></a><span data-ttu-id="7c575-103">Microsoft Edge에서 Office 365 eDiscovery 내보내기 도구 사용</span><span class="sxs-lookup"><span data-stu-id="7c575-103">Use the Office 365 eDiscovery Export Tool in Microsoft Edge</span></span>

<span data-ttu-id="7c575-104">Microsoft Edge의 최근 변경 사항으로 인해 ClickOnce 지원은 더 이상 기본적으로 사용 되지 않도록 설정 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7c575-104">As a result of recent changes to Microsoft Edge, ClickOnce support is no longer enabled by default.</span></span> <span data-ttu-id="7c575-105">Microsoft Office 365 eDiscovery 내보내기 도구를 계속 사용 하 여 콘텐츠 검색 또는 eDiscovery 검색 결과를 다운로드 하려면 [Microsoft Internet Explorer](https://support.microsoft.com/help/17621/internet-explorer-downloads) 를 사용 하거나 microsoft Edge에서 ClickOnce 지원을 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7c575-105">To continue using the Microsoft Office 365 eDiscovery Export Tool to download Content Search or eDiscovery search results, you either need to use [Microsoft Internet Explorer](https://support.microsoft.com/help/17621/internet-explorer-downloads) or enable ClickOnce support in Microsoft Edge.</span></span>

## <a name="how-to-enable-clickonce-support-in-microsoft-edge"></a><span data-ttu-id="7c575-106">Microsoft Edge에서 ClickOnce 지원을 사용 하도록 설정 하는 방법</span><span class="sxs-lookup"><span data-stu-id="7c575-106">How to enable ClickOnce support in Microsoft Edge</span></span>

1. <span data-ttu-id="7c575-107">Microsoft Edge에서 **edge://flags/#edge-클릭 한 번**으로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="7c575-107">In Microsoft Edge, navigate to **edge://flags/#edge-click-once**.</span></span>

2. <span data-ttu-id="7c575-108">기존 값이 드롭다운 목록에서 **기본값** 또는 **사용 안** 함으로 설정 되어 있으면 **사용**으로 변경 합니다.</span><span class="sxs-lookup"><span data-stu-id="7c575-108">If the existing value is set to **Default** or **Disabled** in the dropdown list, change it to **Enabled**.</span></span>
    
   ![](media/ClickOnceimage1.png)

3. <span data-ttu-id="7c575-109">브라우저 창의 아래쪽으로 스크롤한 다음 **다시 시작** 을 클릭 하 여 Edge를 다시 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="7c575-109">Scroll down to the bottom of the browser window and click **Restart** to restart Edge.</span></span>

   ![](media/ClickOnceimage2.png)

<span data-ttu-id="7c575-110">**참고:** 조직에서는 그룹 정책을 사용 하 여 ClickOnce 지원을 사용 하지 않도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7c575-110">**Note:** Organizations can use Group Policy to disable ClickOnce support.</span></span> <span data-ttu-id="7c575-111">ClickOnce 지원에 대 한 조직 정책이 있는지 확인 하려면 **edge://policy**로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="7c575-111">To check if there is an organizational policy for ClickOnce support, navigate to **edge://policy**.</span></span> <span data-ttu-id="7c575-112">다음 스크린샷에서는 전체 조직에서 ClickOnce가 사용 되도록 설정 되어 있음을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="7c575-112">The following screenshot shows that ClickOnce is enabled across the entire organization.</span></span> <span data-ttu-id="7c575-113">이 정책 값이 **false**로 설정 된 경우 조직의 관리자에 게 문의 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7c575-113">If this policy value is set to **false**, you will need to contact an admin in your organization.</span></span>

![](media/ClickOnceimage3.png)

## <a name="install-and-run-the-office-365-ediscovery-export-tool"></a><span data-ttu-id="7c575-114">Office 365 eDiscovery 내보내기 도구 설치 및 실행</span><span class="sxs-lookup"><span data-stu-id="7c575-114">Install and run the Office 365 eDiscovery Export Tool</span></span>

1. <span data-ttu-id="7c575-115">콘텐츠 검색 또는 eDiscovery 사례에서 내보내기의 플라이 아웃 페이지에서 **결과 다운로드** 를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="7c575-115">Click **Download results** on the flyout page of an export in Content Search or an eDiscovery case.</span></span>

   ![검색 결과를 다운로드 하려면 플라이 아웃 페이지에서 결과 다운로드를 클릭 합니다.](media/ClickOnceExport1.png)

2. <span data-ttu-id="7c575-117">도구를 시작할 것인지 묻는 메시지가 표시 되 면 **열기**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="7c575-117">You will be prompted with a confirmation to launch the tool, Click **Open**.</span></span>

   ![열기를 클릭 하 여 eDiscovery 내보내기 도구를 시작 합니다.](media/ClickOnceimage4.png)

   <span data-ttu-id="7c575-119">Microsoft Office 365 eDiscovery 내보내기 도구가 설치 되어 있지 않으면 보안 경고를 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="7c575-119">If the Microsoft Office 365 eDiscovery Export Tool isn't installed, you will be prompted with a Security Warning,</span></span> 

   ![EDiscovery 내보내기 도구를 설치 하려면 설치를 클릭 합니다.](media/ClickOnceimage5.png)

3. <span data-ttu-id="7c575-121">**설치**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="7c575-121">Click **Install**.</span></span> <span data-ttu-id="7c575-122">설치가 완료 되 면 내보내기 도구가 자동으로 실행 됩니다.</span><span class="sxs-lookup"><span data-stu-id="7c575-122">After it's installed, the export tool will launch automatically.</span></span>

<span data-ttu-id="7c575-123">자세한 내용은 다음 항목을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="7c575-123">For more information, see the following topics:</span></span>

- [<span data-ttu-id="7c575-124">콘텐츠 검색 결과 내보내기</span><span class="sxs-lookup"><span data-stu-id="7c575-124">Export Content Search results</span></span>](export-search-results.md)

- [<span data-ttu-id="7c575-125">Microsoft Edge에서 실험 플래그를 사용 하도록 설정 하는 방법</span><span class="sxs-lookup"><span data-stu-id="7c575-125">How to enable experiment flags in Microsoft Edge</span></span>](https://microsoftedgesupport.microsoft.com/hc/articles/360034075294-How-to-enable-experiment-flags-in-Microsoft-Edge-Insider-channels)
