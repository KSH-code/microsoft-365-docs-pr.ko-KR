---
title: Capacity planning and load testing SharePoint Online(용량 계획과 부하 테스트가 가능한 SharePoint Online)
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 04/10/2019
audience: Admin
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Ent_O365
- SPO_Content
f1.keywords:
- CSH
ms.custom: Adm_O365
search.appverid:
- SPO160
- MET150
ms.assetid: c932bd9b-fb9a-47ab-a330-6979d03688c0
description: 이 문서에서는 허용되지 않는 기존 부하 테스트를 수행하지 않고 SharePoint Online에 배포하는 방법을 설명합니다.
ms.openlocfilehash: fb54864168b35fed290ccb1139cb6c607969820d
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/19/2021
ms.locfileid: "50905227"
---
# <a name="capacity-planning-and-load-testing-sharepoint-online"></a><span data-ttu-id="d7aba-103">Capacity planning and load testing SharePoint Online(용량 계획과 부하 테스트가 가능한 SharePoint Online)</span><span class="sxs-lookup"><span data-stu-id="d7aba-103">Capacity planning and load testing SharePoint Online</span></span>
<span data-ttu-id="d7aba-104">이 문서에서는 기존 부하 테스트 없이 SharePoint Online에 배포할 수 있는 방법에 대해 설명합니다. 이는 SharePoint Online에서 부하 테스트가 허용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d7aba-104">This article describes how you can deploy to SharePoint Online without traditional load testing, since load-testing is not permitted on SharePoint Online.</span></span> <span data-ttu-id="d7aba-105">SharePoint 온라인은 클라우드 서비스로, 서비스의 부하 기능, 상태 및 전반적인 부하 잔액은 Microsoft에서 관리합니다.</span><span class="sxs-lookup"><span data-stu-id="d7aba-105">SharePoint Online is a cloud service and the load capabilities, health and overall balance of load in the service is managed by Microsoft.</span></span>
  
<span data-ttu-id="d7aba-106">사이트 시작의 성공을 보장하는 가장 좋은 방법은 포털 시작 롤아웃 계획에서 강조 표시된 기본 원칙, 사례 및 권장 사항을 [따르는 것입니다.](planportallaunchroll-out.md)</span><span class="sxs-lookup"><span data-stu-id="d7aba-106">The best approach to ensuring the success of launching your site is to follow basic principles, practices and recommendations which are highlighted in the [plan your portal launch roll-out](planportallaunchroll-out.md).</span></span>

## <a name="overview-of-how-sharepoint-online-performs-capacity-planning"></a><span data-ttu-id="d7aba-107">SharePoint Online에서 용량 계획을 수행하는 방법 개요</span><span class="sxs-lookup"><span data-stu-id="d7aba-107">Overview of how SharePoint Online performs Capacity planning</span></span> 
<span data-ttu-id="d7aba-108">SharePoint Online의 주요 이점 중 하나는 클라우드의 탄력성과 분산된 지역의 사용자를 위한 최적화입니다.</span><span class="sxs-lookup"><span data-stu-id="d7aba-108">One of the main benefits of SharePoint Online over an on-premises deployment is the elasticity of the cloud as well as optimizations for users in distributed regions.</span></span> <span data-ttu-id="d7aba-109">대규모 환경은 매일 수백만 사용자에 대한 서비스로 설정되어 있으므로 팜을 균형 조정하고 확장하여 용량을 효과적으로 처리하는 것이 중요합니다.</span><span class="sxs-lookup"><span data-stu-id="d7aba-109">Our large scale environment is set up to service millions of users on a daily basis, so it is important that we handle capacity effectively by balancing and expanding farms.</span></span>
  
<span data-ttu-id="d7aba-110">한 팜의 한 테넌트에서 증가를 예측할 수 없는 경우가 종종 있는 반면, 요청의 집계 합은 시간이 지날 때 예측할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d7aba-110">While the growth is often unpredictable for any one tenant in any one farm, the aggregated sum of requests is predictable over time.</span></span> <span data-ttu-id="d7aba-111">SharePoint Online의 증가 추세를 파악하여 향후 확장을 계획할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d7aba-111">By identifying the growth trends in SharePoint Online, we can plan for future expansion.</span></span>
  
<span data-ttu-id="d7aba-112">용량을 효율적으로 사용하며 예기치 않은 증가를 처리하기 위해 모든 팜에서 서비스의 다양한 요소를 추적하고 모니터링하는 자동화가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d7aba-112">In order to efficiently use capacity and deal with unexpected growth, in any farm, we have automation that tracks and monitors various elements of the service.</span></span> <span data-ttu-id="d7aba-113">여러 메트릭이 사용되고, 주요 메트릭 중 하나는 CPU 부하로, 프런트 엔드 서버를 확장하기 위해 신호로 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="d7aba-113">Multiple metrics are utilized, with one of the main ones being CPU load, which is used as a signal to scale-up front end servers.</span></span> <span data-ttu-id="d7aba-114">또한 [단계적/웨이브](planportallaunchroll-out.md)방식도 권장됩니다. SQL 환경은 시간의 따라 부하 및 증가에 따라 확장될 것이고, 단계 및 파도를 따라 해당 부하와 성장을 올바르게 분산할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d7aba-114">Additionally to this we recommend a [phased / wave approach](planportallaunchroll-out.md), as SQL environments will scale according to load and growth over time, and following the phases and waves allows for the correct distribution of that load and growth.</span></span> 

<span data-ttu-id="d7aba-115">용량은 지속적으로 하드웨어를 더 추가하는 것 이상으로, 유효한 부하 요청을 처리하도록 해당 용량을 관리 및 제어하는 데도 관련이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d7aba-115">Capacity is more than just about adding more hardware on a continuous basis but it also pertains to managing and controlling that capacity to ensure it is servicing valid load requests.</span></span> <span data-ttu-id="d7aba-116">고객이 최상의 환경을 경험할 수 있도록 권장 지침을 따르는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="d7aba-116">We recommend that customers follow the recommended guidance to ensure they have the best experience.</span></span> <span data-ttu-id="d7aba-117">또한 서비스에서 "부적당" 동작을 허용하지 않도록 하는 데 필요한 조절 패턴과 컨트롤이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d7aba-117">It also means that we have throttling patterns and controls in place to ensure we do not allow "abusive" behavior in the service.</span></span> <span data-ttu-id="d7aba-118">모든 "나쁜" 동작이 의도적인 것은 아니며 해당 동작의 영향을 제한해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d7aba-118">Whilst not all "bad" behavior is intentional, we do have to ensure that we limit the effect of that behavior.</span></span> <span data-ttu-id="d7aba-119">스로틀 및 이를 방지하는 방법에 대한 자세한 내용은 스로틀되지 않도록 하는 방법 문서를 [검토하세요.](/sharepoint/dev/general-development/how-to-avoid-getting-throttled-or-blocked-in-sharepoint-online)</span><span class="sxs-lookup"><span data-stu-id="d7aba-119">For further information on throttling and how to avoid it, review the [how to avoid being throttled guidance](/sharepoint/dev/general-development/how-to-avoid-getting-throttled-or-blocked-in-sharepoint-online) article.</span></span>

## <a name="why-you-cannot-load-test-sharepoint-online"></a><span data-ttu-id="d7aba-120">Online에서 테스트 테스트를 로드할 SharePoint 이유</span><span class="sxs-lookup"><span data-stu-id="d7aba-120">Why you cannot load test SharePoint Online</span></span>
<span data-ttu-id="d7aba-121">사내 환경에서는 부하 테스트가 확장 가정의 유효성을 검사하고 궁극적으로 팜의 중단점을 찾는 데 사용됩니다. 로드를 채도로 채우는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="d7aba-121">With on-premises environments, load testing is used to validate scale assumption and ultimately find the breaking point of a farm; by saturating it with load.</span></span> 

<span data-ttu-id="d7aba-122">온라인 SharePoint 배율이 비교적 유동적이기 때문에 특정추학에 따라 부하를 조정, 제한 및 제어하기 때문에 다르게 작업을 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d7aba-122">With SharePoint Online we need to do things differently because the scale is relatively fluid and adjusts, throttles and controls load, based on certain heuristics.</span></span> <span data-ttu-id="d7aba-123">이러한 대규모 다중 테넌트 환경인 경우 동일한 팜의 모든 테넌트를 보호해야 하여 부하 테스트를 자동으로 조정합니다.</span><span class="sxs-lookup"><span data-stu-id="d7aba-123">Being such a large scale multi-tenant environment, we must protect all tenants in the same farm, so we will automatically throttle any load tests.</span></span> <span data-ttu-id="d7aba-124">그러나 테스트를 로드하려고 하면 스로틀링되는 것 외에 배율 및 팜 균형 조정 작업이 계속 수행될 때 현재 테스트한 팜이 테스트 기간 동안 또는 테스트 후 시간 내에 배율이 변경될 수 있기 때문에 잘못된 결과를 얻게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d7aba-124">If you do however attempt to load test, besides being throttled, you will receive disappointing and potentially misleading results because the farm you tested today will probably have had scale changes during the testing window or within hours after testing, as scale and farm balancing actions are performed on an on-going basis.</span></span>

<span data-ttu-id="d7aba-125">테스트 SharePoint 서비스로 로드하는 대신 권장 사례를 따르고, 정상 포털 [만들기,](/sharepoint/portal-health) 시작 및 유지 관리 지침을 따르는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="d7aba-125">Instead of trying to load test SharePoint as a service, rather focus on following the recommended practices and follow the [Creating, launching and maintaining a healthy portal](/sharepoint/portal-health) guidance.</span></span>