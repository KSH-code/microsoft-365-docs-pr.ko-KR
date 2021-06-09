---
title: Microsoft Cloud App Security 통합 구성
ms.reviewer: ''
description: Microsoft Defender for Endpoint와 끝점 통합을 사용하도록 설정하는 방법을 Microsoft Cloud App Security.
keywords: 클라우드, 앱, 보안, 설정, 통합, 검색, 보고서
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 4f7aca5cb532510d55042c70d04d65f2aa08baa3
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/08/2021
ms.locfileid: "52844757"
---
# <a name="configure-microsoft-cloud-app-security-in-microsoft-defender-for-endpoint"></a><span data-ttu-id="47fc1-104">끝점 Microsoft Cloud App Security Microsoft Defender에서 업데이트 구성</span><span class="sxs-lookup"><span data-stu-id="47fc1-104">Configure Microsoft Cloud App Security in Microsoft Defender for Endpoint</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="47fc1-105">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="47fc1-105">**Applies to:**</span></span>
- [<span data-ttu-id="47fc1-106">엔드포인트용 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="47fc1-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="47fc1-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="47fc1-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="47fc1-108">끝점용 Microsoft Defender를 경험하고 싶나요?</span><span class="sxs-lookup"><span data-stu-id="47fc1-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="47fc1-109">무료 평가판에 등록합니다.</span><span class="sxs-lookup"><span data-stu-id="47fc1-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)


<span data-ttu-id="47fc1-110">Endpoint 클라우드 앱 검색 신호에 대한 Microsoft Defender의 이점을 활용하기 위해 통합을 Microsoft Cloud App Security 하세요.</span><span class="sxs-lookup"><span data-stu-id="47fc1-110">To benefit from Microsoft Defender for Endpoint cloud app discovery signals, turn on Microsoft Cloud App Security integration.</span></span>

>[!NOTE]
><span data-ttu-id="47fc1-111">이 기능은 Windows 10 버전 1709(KB4493441이 있는 OS 빌드 16299.1085)를 실행하는 장치에서 Enterprise Mobility + Security E5 라이선스와 함께 사용할 수 Windows 10. 버전 1803(OS 빌드 17134.704 [및 KB4493464](https://support.microsoft.com/help/4493464)), Windows 10, 버전 1809(OS 빌드 17763.379( [KB4489899)](https://support.microsoft.com/help/4489899)이상 버전의 Windows 10. [](https://www.microsoft.com/cloud-platform/enterprise-mobility-security) [](https://support.microsoft.com/help/4493441)</span><span class="sxs-lookup"><span data-stu-id="47fc1-111">This feature will be available with an E5 license for [Enterprise Mobility + Security](https://www.microsoft.com/cloud-platform/enterprise-mobility-security) on devices running Windows 10, version 1709 (OS Build 16299.1085 with [KB4493441](https://support.microsoft.com/help/4493441)), Windows 10, version 1803 (OS Build 17134.704 with [KB4493464](https://support.microsoft.com/help/4493464)), Windows 10, version 1809 (OS Build 17763.379 with [KB4489899](https://support.microsoft.com/help/4489899)) or later Windows 10 versions.</span></span>

> <span data-ttu-id="47fc1-112">[끝점용 Microsoft Defender와](/cloud-app-security/mde-integration) 엔드포인트의 Microsoft Cloud App Security 통합에 대한 자세한 내용은 Microsoft Defender for Endpoint Microsoft Cloud App Security.</span><span class="sxs-lookup"><span data-stu-id="47fc1-112">See [Microsoft Defender for Endpoint integration with Microsoft Cloud App Security](/cloud-app-security/mde-integration) for detailed integration of Microsoft Defender for Endpoint with Microsoft Cloud App Security.</span></span> 

## <a name="enable-microsoft-cloud-app-security-in-microsoft-defender-for-endpoint"></a><span data-ttu-id="47fc1-113">끝점용 Microsoft Defender에서 Microsoft Cloud App Security 사용</span><span class="sxs-lookup"><span data-stu-id="47fc1-113">Enable Microsoft Cloud App Security in Microsoft Defender for Endpoint</span></span>

1. <span data-ttu-id="47fc1-114">탐색 창에서 기본 **설정** 고급 기능  >  **을 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="47fc1-114">In the navigation pane, select **Preferences setup** > **Advanced features**.</span></span>
2. <span data-ttu-id="47fc1-115">를 **Microsoft Cloud App Security** 를 선택하고 토글을 켜기 로 **전환합니다.**</span><span class="sxs-lookup"><span data-stu-id="47fc1-115">Select **Microsoft Cloud App Security** and switch the toggle to **On**.</span></span>
3. <span data-ttu-id="47fc1-116">기본 **설정 저장을 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="47fc1-116">Click **Save preferences**.</span></span>

<span data-ttu-id="47fc1-117">활성화되면 끝점용 Microsoft Defender는 검색 신호를 즉시 Cloud App Security.</span><span class="sxs-lookup"><span data-stu-id="47fc1-117">Once activated, Microsoft Defender for Endpoint will immediately start forwarding discovery signals to Cloud App Security.</span></span>

## <a name="view-the-data-collected"></a><span data-ttu-id="47fc1-118">수집된 데이터 보기</span><span class="sxs-lookup"><span data-stu-id="47fc1-118">View the data collected</span></span>

<span data-ttu-id="47fc1-119">Microsoft Cloud Apps Security에서 끝점용 Microsoft Defender 데이터를 보고 액세스하는 경우 에서 장치 [조사를 Cloud App Security.](/cloud-app-security/mde-integration#investigate-devices-in-cloud-app-security)</span><span class="sxs-lookup"><span data-stu-id="47fc1-119">To view and access Microsoft Defender for Endpoint data in Microsoft Cloud Apps Security, see [Investigate devices in Cloud App Security](/cloud-app-security/mde-integration#investigate-devices-in-cloud-app-security).</span></span>


<span data-ttu-id="47fc1-120">클라우드 검색에 대한 자세한 내용은 검색된 앱 [작업을 참조하세요.](/cloud-app-security/discovered-apps)</span><span class="sxs-lookup"><span data-stu-id="47fc1-120">For more information about cloud discovery, see [Working with discovered apps](/cloud-app-security/discovered-apps).</span></span>

<span data-ttu-id="47fc1-121">평가판을 사용해 보시고 Microsoft Cloud App Security [평가판을 Microsoft Cloud App Security 참조합니다.](https://signup.microsoft.com/Signup?OfferId=757c4c34-d589-46e4-9579-120bba5c92ed&ali=1)</span><span class="sxs-lookup"><span data-stu-id="47fc1-121">If you're interested in trying Microsoft Cloud App Security, see [Microsoft Cloud App Security Trial](https://signup.microsoft.com/Signup?OfferId=757c4c34-d589-46e4-9579-120bba5c92ed&ali=1).</span></span>

## <a name="related-topic"></a><span data-ttu-id="47fc1-122">관련 항목</span><span class="sxs-lookup"><span data-stu-id="47fc1-122">Related topic</span></span>
- [<span data-ttu-id="47fc1-123">Microsoft Cloud App Security 통합</span><span class="sxs-lookup"><span data-stu-id="47fc1-123">Microsoft Cloud App Security integration</span></span>](microsoft-cloud-app-security-integration.md)
