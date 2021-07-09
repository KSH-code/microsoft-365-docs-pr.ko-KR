---
title: 끝점 미리 보기 기능용 Microsoft Defender
description: 끝점용 Microsoft Defender 미리 보기 기능에 액세스하는 방법을 학습합니다.
keywords: 미리 보기, 미리 보기 환경, 끝점용 Microsoft Defender, 기능, 업데이트
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
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 0b6edbdcda61eaf402275ae0b6dc9a38c5fe19f7
ms.sourcegitcommit: 0d1b065c94125b495e9886200f7918de3bda40b3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/08/2021
ms.locfileid: "53339493"
---
# <a name="microsoft-defender-for-endpoint-preview-features"></a><span data-ttu-id="59e5a-104">끝점 미리 보기 기능용 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="59e5a-104">Microsoft Defender for Endpoint preview features</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="59e5a-105">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="59e5a-105">**Applies to:**</span></span>
- [<span data-ttu-id="59e5a-106">엔드포인트용 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="59e5a-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="59e5a-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="59e5a-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="59e5a-108">끝점용 Microsoft Defender를 경험하고 싶나요?</span><span class="sxs-lookup"><span data-stu-id="59e5a-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="59e5a-109">무료 평가판에 등록합니다.</span><span class="sxs-lookup"><span data-stu-id="59e5a-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)


<span data-ttu-id="59e5a-110">Endpoint용 Defender 서비스는 새로운 기능 향상 및 기능을 포함하기 위해 지속적으로 업데이트되고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="59e5a-110">The Defender for Endpoint service is constantly being updated to include new feature enhancements and capabilities.</span></span>

<span data-ttu-id="59e5a-111">Endpoint용 Defender 미리 보기 릴리스의 새로운 기능에 대해 알아보고 미리 보기 환경을 켜서 예정된 기능을 처음 사용해 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="59e5a-111">Learn about new features in the Defender for Endpoint preview release and be among the first to try upcoming features by turning on the preview experience.</span></span>

>[!TIP]
><span data-ttu-id="59e5a-112">다음 URL을 복사하여 피드 읽기 페이지에 붙여 넣는 방법을 통해 이 페이지가 업데이트될 때 알림을 받을 수 있습니다. `/api/search/rss?search=%22In+the+navigation+pane%2C+select+Settings+%3E+Advanced+features+%3E+Preview+features.%22&locale=en-us&facet=`</span><span class="sxs-lookup"><span data-stu-id="59e5a-112">Get notified when this page is updated by copying and pasting the following URL into your feed reader: `/api/search/rss?search=%22In+the+navigation+pane%2C+select+Settings+%3E+Advanced+features+%3E+Preview+features.%22&locale=en-us&facet=`</span></span>

<span data-ttu-id="59e5a-113">일반적으로 사용할 수 있는 새로운 기능에 대한 자세한 내용은 [Endpoint용 Defender의](whats-new-in-microsoft-defender-atp.md)새로운 기능을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="59e5a-113">For more information on new capabilities that are generally available, see [What's new in Defender for Endpoint](whats-new-in-microsoft-defender-atp.md).</span></span>

 ## <a name="what-you-need-to-know"></a><span data-ttu-id="59e5a-114">알아야 할 것</span><span class="sxs-lookup"><span data-stu-id="59e5a-114">What you need to know</span></span>

<span data-ttu-id="59e5a-115">공개 미리 보기에서 기능을 사용할 때 다음과 같은 기능을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="59e5a-115">When working with features in public preview, these features:</span></span>

- <span data-ttu-id="59e5a-116">기능이 제한되거나 제한될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="59e5a-116">May have restricted or limited functionality.</span></span> <span data-ttu-id="59e5a-117">예를 들어 이 기능은 하나의 플랫폼에만 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="59e5a-117">For example, the feature may only apply to one platform.</span></span>
- <span data-ttu-id="59e5a-118">일반적으로 GA(일반 제공)되기 전에 기능 변경 사항을 거치게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="59e5a-118">Typically go through feature changes before they're generally available (GA).</span></span>
- <span data-ttu-id="59e5a-119">Microsoft에서 완전히 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="59e5a-119">Are fully supported by Microsoft.</span></span>
- <span data-ttu-id="59e5a-120">선택한 지리적 지역 또는 클라우드 환경에서만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="59e5a-120">May only be available in selected geographic regions or cloud environments.</span></span> <span data-ttu-id="59e5a-121">예를 들어 이 기능은 정부 클라우드에 존재하지 않을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="59e5a-121">For example, the feature may not exist in the government cloud.</span></span>
- <span data-ttu-id="59e5a-122">미리 보기의 개별 기능에는 더 많은 사용 및 지원 제한이 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="59e5a-122">Individual features in preview may have more usage and support restrictions.</span></span> <span data-ttu-id="59e5a-123">이 경우 이 정보는 일반적으로 기능 설명서에 기록됩니다.</span><span class="sxs-lookup"><span data-stu-id="59e5a-123">If so, this information is typically noted in the feature documentation.</span></span>
- <span data-ttu-id="59e5a-124">미리 보기 버전은 표준 지원 수준으로 제공될 수 있으며 프로덕션 환경에 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="59e5a-124">The preview versions are provided with a standard support level, and can be used for production environments.</span></span> 



## <a name="turn-on-preview-features"></a><span data-ttu-id="59e5a-125">미리 보기 기능 설정</span><span class="sxs-lookup"><span data-stu-id="59e5a-125">Turn on preview features</span></span>

<span data-ttu-id="59e5a-126">기능을 일반적으로 사용할 수 있도록 하기 전에 전반적인 환경을 개선하는 데 도움이 되기 위해 피드백을 제공할 수 있는 예정된 기능에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="59e5a-126">You'll have access to upcoming features that you can provide feedback on to help improve the overall experience before features are generally available.</span></span>

<span data-ttu-id="59e5a-127">미리 보기 환경을 설정하여 최초로 예정된 기능을 사용해보세요.</span><span class="sxs-lookup"><span data-stu-id="59e5a-127">Turn on the preview experience setting to be among the first to try upcoming features.</span></span>

1. <span data-ttu-id="59e5a-128">탐색 창에서 고급 **기능** 설정  >  **미리 보기 기능을**  >  **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="59e5a-128">In the navigation pane, select **Settings** > **Advanced features** > **Preview features**.</span></span>

2. <span data-ttu-id="59e5a-129">설정 및 해제  간에 설정을 **전환하고** 기본 설정 **저장을 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="59e5a-129">Toggle the setting between **On** and **Off** and select **Save preferences**.</span></span>

## <a name="preview-features"></a><span data-ttu-id="59e5a-130">미리 보기 기능</span><span class="sxs-lookup"><span data-stu-id="59e5a-130">Preview features</span></span>

<span data-ttu-id="59e5a-131">미리 보기 릴리스에는 다음과 같은 기능이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="59e5a-131">The following features are included in the preview release:</span></span>

- [<span data-ttu-id="59e5a-132">웹 콘텐츠 필터링</span><span class="sxs-lookup"><span data-stu-id="59e5a-132">Web Content Filtering</span></span>](web-content-filtering.md) <br> <span data-ttu-id="59e5a-133">웹 콘텐츠 필터링은 끝점용 Microsoft Defender의 웹 보호 기능의 일부입니다.</span><span class="sxs-lookup"><span data-stu-id="59e5a-133">Web content filtering is part of web protection capabilities in Microsoft Defender for Endpoint.</span></span> <span data-ttu-id="59e5a-134">이를 통해 조직은 해당 콘텐츠 범주에 따라 웹 사이트에 대한 액세스를 추적하고 규제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="59e5a-134">It enables your organization to track and regulate access to websites based on their content categories.</span></span> <span data-ttu-id="59e5a-135">이러한 웹 사이트 중 상당수는 악의적이지 않은 경우 규정 준수 규정, 대역폭 사용량 또는 기타 문제로 문제가 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="59e5a-135">Many of these websites, while not malicious, might be problematic because of compliance regulations, bandwidth usage, or other concerns.</span></span>

- [<span data-ttu-id="59e5a-136">장치 상태 및 준수 보고서</span><span class="sxs-lookup"><span data-stu-id="59e5a-136">Device health and compliance report</span></span>](machine-reports.md) <br/> <span data-ttu-id="59e5a-137">장치 상태 및 준수 보고서는 조직의 장치에 대한 높은 수준의 정보를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="59e5a-137">The device health and compliance report provides high-level information about the devices in your organization.</span></span>

> [!TIP] 
> <span data-ttu-id="59e5a-138">끝점용 Microsoft Defender를 경험하고 싶나요?</span><span class="sxs-lookup"><span data-stu-id="59e5a-138">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="59e5a-139">무료 평가판에 등록합니다.</span><span class="sxs-lookup"><span data-stu-id="59e5a-139">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-preview-belowfoldlink)  
