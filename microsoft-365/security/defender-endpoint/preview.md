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
ms.openlocfilehash: ea37ad4302eedf7d43e3ad03e94357a146c2216c
ms.sourcegitcommit: ff20f5b4e3268c7c98a84fb1cbe7db7151596b6d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/06/2021
ms.locfileid: "52245579"
---
# <a name="microsoft-defender-for-endpoint-preview-features"></a><span data-ttu-id="e76cc-104">끝점 미리 보기 기능용 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="e76cc-104">Microsoft Defender for Endpoint preview features</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

>[!IMPORTANT]
><span data-ttu-id="e76cc-105">미리 보기 버전은 서비스 수준 계약 없이 제공하며 프로덕션 워크로드에는 권장되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="e76cc-105">The preview versions are provided without a service level agreement, and it's not recommended for production workloads.</span></span> <span data-ttu-id="e76cc-106">일부 기능은 지원되지 않을 수도, 기능이 제한될 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e76cc-106">Certain features might not be supported or might have constrained capabilities.</span></span>

<span data-ttu-id="e76cc-107">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="e76cc-107">**Applies to:**</span></span>
- [<span data-ttu-id="e76cc-108">엔드포인트용 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="e76cc-108">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="e76cc-109">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="e76cc-109">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="e76cc-110">끝점용 Microsoft Defender를 경험하고 싶나요?</span><span class="sxs-lookup"><span data-stu-id="e76cc-110">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="e76cc-111">무료 평가판에 등록합니다.</span><span class="sxs-lookup"><span data-stu-id="e76cc-111">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)


<span data-ttu-id="e76cc-112">Endpoint용 Defender 서비스는 새로운 기능 향상 및 기능을 포함하기 위해 지속적으로 업데이트되고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e76cc-112">The Defender for Endpoint service is constantly being updated to include new feature enhancements and capabilities.</span></span>

<span data-ttu-id="e76cc-113">Endpoint용 Defender 미리 보기 릴리스의 새로운 기능에 대해 알아보고 미리 보기 환경을 켜서 예정된 기능을 처음 사용해 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e76cc-113">Learn about new features in the Defender for Endpoint preview release and be among the first to try upcoming features by turning on the preview experience.</span></span>

>[!TIP]
><span data-ttu-id="e76cc-114">다음 URL을 복사하여 피드 읽기 페이지에 붙여 넣는 방법을 통해 이 페이지가 업데이트될 때 알림을 받을 수 있습니다. `https://docs.microsoft.com/api/search/rss?search=%22In+the+navigation+pane%2C+select+Settings+%3E+Advanced+features+%3E+Preview+features.%22&locale=en-us&facet=`</span><span class="sxs-lookup"><span data-stu-id="e76cc-114">Get notified when this page is updated by copying and pasting the following URL into your feed reader: `https://docs.microsoft.com/api/search/rss?search=%22In+the+navigation+pane%2C+select+Settings+%3E+Advanced+features+%3E+Preview+features.%22&locale=en-us&facet=`</span></span>

<span data-ttu-id="e76cc-115">일반적으로 사용할 수 있는 새로운 기능에 대한 자세한 내용은 [Endpoint용 Defender의](whats-new-in-microsoft-defender-atp.md)새로운 기능을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="e76cc-115">For more information on new capabilities that are generally available, see [What's new in Defender for Endpoint](whats-new-in-microsoft-defender-atp.md).</span></span>

## <a name="turn-on-preview-features"></a><span data-ttu-id="e76cc-116">미리 보기 기능 설정</span><span class="sxs-lookup"><span data-stu-id="e76cc-116">Turn on preview features</span></span>

<span data-ttu-id="e76cc-117">기능을 일반적으로 사용할 수 있도록 하기 전에 전반적인 환경을 개선하는 데 도움이 되기 위해 피드백을 제공할 수 있는 예정된 기능에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e76cc-117">You'll have access to upcoming features that you can provide feedback on to help improve the overall experience before features are generally available.</span></span>

<span data-ttu-id="e76cc-118">미리 보기 환경을 설정하여 최초로 예정된 기능을 사용해보세요.</span><span class="sxs-lookup"><span data-stu-id="e76cc-118">Turn on the preview experience setting to be among the first to try upcoming features.</span></span>

1. <span data-ttu-id="e76cc-119">탐색 창에서 고급 **기능** 설정  >  **미리 보기 기능을**  >  **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="e76cc-119">In the navigation pane, select **Settings** > **Advanced features** > **Preview features**.</span></span>

2. <span data-ttu-id="e76cc-120">설정 및 해제  간에 설정을 **전환하고** 기본 설정 **저장을 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="e76cc-120">Toggle the setting between **On** and **Off** and select **Save preferences**.</span></span>

## <a name="preview-features"></a><span data-ttu-id="e76cc-121">미리 보기 기능</span><span class="sxs-lookup"><span data-stu-id="e76cc-121">Preview features</span></span>

<span data-ttu-id="e76cc-122">미리 보기 릴리스에는 다음과 같은 기능이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e76cc-122">The following features are included in the preview release:</span></span>

- [<span data-ttu-id="e76cc-123">장치 검색</span><span class="sxs-lookup"><span data-stu-id="e76cc-123">Device discovery</span></span>](device-discovery.md) <br> <span data-ttu-id="e76cc-124">추가 어플라이언스 또는 번거로운 프로세스 변경 없이도 회사 네트워크에 연결된 관리되지 않는 장치를 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e76cc-124">Helps you find unmanaged devices connected to your corporate network without the need for extra appliances or cumbersome process changes.</span></span> <span data-ttu-id="e76cc-125">온보드 장치를 사용하여 네트워크에서 관리되지 않는 장치를 찾고 취약성 및 위험을 평가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e76cc-125">Using onboarded devices, you can find unmanaged devices in your network and assess vulnerabilities and risks.</span></span> <span data-ttu-id="e76cc-126">그런 다음 검색된 장치를 온보드하여 네트워크에 관리되지 않는 끝점이 있는 경우와 관련된 위험을 줄일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e76cc-126">You can then onboard discovered devices to reduce risks associated with having unmanaged endpoints in your network.</span></span>

   > [!IMPORTANT]
   > <span data-ttu-id="e76cc-127">표준 검색은 2021년 5월 10일부터 모든 미리 보기 고객의 기본 모드가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e76cc-127">Standard discovery will be the default mode for all preview customers starting May 10, 2021.</span></span> <span data-ttu-id="e76cc-128">설정 페이지를 통해 기본 모드를 유지할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e76cc-128">You can choose to retain the basic mode through the settings page.</span></span> 


- [<span data-ttu-id="e76cc-129">웹 콘텐츠 필터링</span><span class="sxs-lookup"><span data-stu-id="e76cc-129">Web Content Filtering</span></span>](web-content-filtering.md) <br> <span data-ttu-id="e76cc-130">웹 콘텐츠 필터링은 끝점용 Microsoft Defender의 웹 보호 기능의 일부입니다.</span><span class="sxs-lookup"><span data-stu-id="e76cc-130">Web content filtering is part of web protection capabilities in Microsoft Defender for Endpoint.</span></span> <span data-ttu-id="e76cc-131">이를 통해 조직은 해당 콘텐츠 범주에 따라 웹 사이트에 대한 액세스를 추적하고 규제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e76cc-131">It enables your organization to track and regulate access to websites based on their content categories.</span></span> <span data-ttu-id="e76cc-132">이러한 웹 사이트 중 상당수는 악의적이지 않은 경우 규정 준수 규정, 대역폭 사용량 또는 기타 문제로 문제가 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e76cc-132">Many of these websites, while not malicious, might be problematic because of compliance regulations, bandwidth usage, or other concerns.</span></span>

- [<span data-ttu-id="e76cc-133">장치 상태 및 준수 보고서</span><span class="sxs-lookup"><span data-stu-id="e76cc-133">Device health and compliance report</span></span>](machine-reports.md) <br/> <span data-ttu-id="e76cc-134">장치 상태 및 준수 보고서는 조직의 장치에 대한 높은 수준의 정보를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="e76cc-134">The device health and compliance report provides high-level information about the devices in your organization.</span></span>

> [!TIP] 
> <span data-ttu-id="e76cc-135">끝점용 Microsoft Defender를 경험하고 싶나요?</span><span class="sxs-lookup"><span data-stu-id="e76cc-135">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="e76cc-136">무료 평가판에 등록합니다.</span><span class="sxs-lookup"><span data-stu-id="e76cc-136">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-preview-belowfoldlink)  
