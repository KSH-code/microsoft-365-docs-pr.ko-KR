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
ms.openlocfilehash: 65edf54ea0bf5cb0a0210dd306db07c756149f65
ms.sourcegitcommit: d34cac68537d6e1c65be757956646e73dea6e1ab
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/22/2021
ms.locfileid: "53062130"
---
# <a name="microsoft-defender-for-endpoint-preview-features"></a><span data-ttu-id="43276-104">끝점 미리 보기 기능용 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="43276-104">Microsoft Defender for Endpoint preview features</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

>[!IMPORTANT]
><span data-ttu-id="43276-105">미리 보기 버전은 서비스 수준 계약 없이 제공하며 프로덕션 워크로드에는 권장되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="43276-105">The preview versions are provided without a service level agreement, and it's not recommended for production workloads.</span></span> <span data-ttu-id="43276-106">일부 기능은 지원되지 않을 수도, 기능이 제한될 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="43276-106">Certain features might not be supported or might have constrained capabilities.</span></span>

<span data-ttu-id="43276-107">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="43276-107">**Applies to:**</span></span>
- [<span data-ttu-id="43276-108">엔드포인트용 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="43276-108">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="43276-109">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="43276-109">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="43276-110">끝점용 Microsoft Defender를 경험하고 싶나요?</span><span class="sxs-lookup"><span data-stu-id="43276-110">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="43276-111">무료 평가판에 등록합니다.</span><span class="sxs-lookup"><span data-stu-id="43276-111">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)


<span data-ttu-id="43276-112">Endpoint용 Defender 서비스는 새로운 기능 향상 및 기능을 포함하기 위해 지속적으로 업데이트되고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="43276-112">The Defender for Endpoint service is constantly being updated to include new feature enhancements and capabilities.</span></span>

<span data-ttu-id="43276-113">Endpoint용 Defender 미리 보기 릴리스의 새로운 기능에 대해 알아보고 미리 보기 환경을 켜서 예정된 기능을 처음 사용해 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="43276-113">Learn about new features in the Defender for Endpoint preview release and be among the first to try upcoming features by turning on the preview experience.</span></span>

>[!TIP]
><span data-ttu-id="43276-114">다음 URL을 복사하여 피드 읽기 페이지에 붙여 넣는 방법을 통해 이 페이지가 업데이트될 때 알림을 받을 수 있습니다. `/api/search/rss?search=%22In+the+navigation+pane%2C+select+Settings+%3E+Advanced+features+%3E+Preview+features.%22&locale=en-us&facet=`</span><span class="sxs-lookup"><span data-stu-id="43276-114">Get notified when this page is updated by copying and pasting the following URL into your feed reader: `/api/search/rss?search=%22In+the+navigation+pane%2C+select+Settings+%3E+Advanced+features+%3E+Preview+features.%22&locale=en-us&facet=`</span></span>

<span data-ttu-id="43276-115">일반적으로 사용할 수 있는 새로운 기능에 대한 자세한 내용은 [Endpoint용 Defender의](whats-new-in-microsoft-defender-atp.md)새로운 기능을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="43276-115">For more information on new capabilities that are generally available, see [What's new in Defender for Endpoint](whats-new-in-microsoft-defender-atp.md).</span></span>

## <a name="turn-on-preview-features"></a><span data-ttu-id="43276-116">미리 보기 기능 설정</span><span class="sxs-lookup"><span data-stu-id="43276-116">Turn on preview features</span></span>

<span data-ttu-id="43276-117">기능을 일반적으로 사용할 수 있도록 하기 전에 전반적인 환경을 개선하는 데 도움이 되기 위해 피드백을 제공할 수 있는 예정된 기능에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="43276-117">You'll have access to upcoming features that you can provide feedback on to help improve the overall experience before features are generally available.</span></span>

<span data-ttu-id="43276-118">미리 보기 환경을 설정하여 최초로 예정된 기능을 사용해보세요.</span><span class="sxs-lookup"><span data-stu-id="43276-118">Turn on the preview experience setting to be among the first to try upcoming features.</span></span>

1. <span data-ttu-id="43276-119">탐색 창에서 고급 **기능** 설정  >  **미리 보기 기능을**  >  **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="43276-119">In the navigation pane, select **Settings** > **Advanced features** > **Preview features**.</span></span>

2. <span data-ttu-id="43276-120">설정 및 해제  간에 설정을 **전환하고** 기본 설정 **저장을 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="43276-120">Toggle the setting between **On** and **Off** and select **Save preferences**.</span></span>

## <a name="preview-features"></a><span data-ttu-id="43276-121">미리 보기 기능</span><span class="sxs-lookup"><span data-stu-id="43276-121">Preview features</span></span>

<span data-ttu-id="43276-122">미리 보기 릴리스에는 다음과 같은 기능이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="43276-122">The following features are included in the preview release:</span></span>

- [<span data-ttu-id="43276-123">웹 콘텐츠 필터링</span><span class="sxs-lookup"><span data-stu-id="43276-123">Web Content Filtering</span></span>](web-content-filtering.md) <br> <span data-ttu-id="43276-124">웹 콘텐츠 필터링은 끝점용 Microsoft Defender의 웹 보호 기능의 일부입니다.</span><span class="sxs-lookup"><span data-stu-id="43276-124">Web content filtering is part of web protection capabilities in Microsoft Defender for Endpoint.</span></span> <span data-ttu-id="43276-125">이를 통해 조직은 해당 콘텐츠 범주에 따라 웹 사이트에 대한 액세스를 추적하고 규제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="43276-125">It enables your organization to track and regulate access to websites based on their content categories.</span></span> <span data-ttu-id="43276-126">이러한 웹 사이트 중 상당수는 악의적이지 않은 경우 규정 준수 규정, 대역폭 사용량 또는 기타 문제로 문제가 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="43276-126">Many of these websites, while not malicious, might be problematic because of compliance regulations, bandwidth usage, or other concerns.</span></span>

- [<span data-ttu-id="43276-127">장치 상태 및 준수 보고서</span><span class="sxs-lookup"><span data-stu-id="43276-127">Device health and compliance report</span></span>](machine-reports.md) <br/> <span data-ttu-id="43276-128">장치 상태 및 준수 보고서는 조직의 장치에 대한 높은 수준의 정보를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="43276-128">The device health and compliance report provides high-level information about the devices in your organization.</span></span>

> [!TIP] 
> <span data-ttu-id="43276-129">끝점용 Microsoft Defender를 경험하고 싶나요?</span><span class="sxs-lookup"><span data-stu-id="43276-129">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="43276-130">무료 평가판에 등록합니다.</span><span class="sxs-lookup"><span data-stu-id="43276-130">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-preview-belowfoldlink)  
