---
title: Microsoft Threat Protection의 인시던트 조사
description: 여러 장치, 사용자 및 사서함에 표시되는 인시던트를 조사합니다.
keywords: 인시던트, 경고, 조사, 상관 관계, 공격, 컴퓨터, 장치, 사용자, IDs, ID, 사서함, 전자 메일, 365, microsoft, m365
search.product: eADQiWindows 10XVcnh
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.openlocfilehash: 989184c5dd8af6aafc525100e34e0172d96adcfe
ms.sourcegitcommit: 0c9c28a87201c7470716216d99175356fb3d1a47
ms.translationtype: MT + HT Review
ms.contentlocale: ko-KR
ms.lasthandoff: 12/09/2019
ms.locfileid: "39911429"
---
# <a name="incidents-overview-in-microsoft-threat-protection"></a><span data-ttu-id="992a6-104">Microsoft Threat Protection의 인시던트 개요</span><span class="sxs-lookup"><span data-stu-id="992a6-104">Incidents overview in Microsoft Threat Protection</span></span>

<span data-ttu-id="992a6-105">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="992a6-105">**Applies to:**</span></span>
- <span data-ttu-id="992a6-106">Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="992a6-106">Microsoft Threat Protection</span></span>

[!include[Prerelease information](prerelease.md)]

<span data-ttu-id="992a6-107">모든 인시던트의 기반은 경고입니다.</span><span class="sxs-lookup"><span data-stu-id="992a6-107">The basis of all incidents are alerts.</span></span> <span data-ttu-id="992a6-108">네트워크에서 악성 이벤트 또는 활동이 발견되면 경고가 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="992a6-108">Alerts are created when a malicious event or activity is seen on your network.</span></span> <span data-ttu-id="992a6-109">개별 경고는 개별 이벤트나 엔터티에서 발생하는 상황에 대한 유용한 단서를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="992a6-109">Individual alerts provide valuable clues in what's happening on individual events or entities.</span></span> <span data-ttu-id="992a6-110">그러나 일반적으로 공격은 다양한 공격 벡터를 사용하여 위반을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="992a6-110">However, attacks typically employ various attack vectors to carry out a breach.</span></span> <span data-ttu-id="992a6-111">개별 단서를 하나로 묶는 것은 어렵고 시간이 많이 걸리는 작업이 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="992a6-111">Piecing individual clues together can be a challenging and time-consuming task.</span></span> 

<span data-ttu-id="992a6-112">Microsoft Threat Protection는 개별 경고의 점들을 연결합니다.</span><span class="sxs-lookup"><span data-stu-id="992a6-112">Microsoft Threat Protection connects the dots on individual alerts.</span></span> <span data-ttu-id="992a6-113">다음 엔터티에 대한 악성 이벤트는 Microsoft 365 보안 센터에 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="992a6-113">Malicious events on the following entities are surfaced in the Microsoft 365 security center:</span></span>
- <span data-ttu-id="992a6-114">장치</span><span class="sxs-lookup"><span data-stu-id="992a6-114">Devices</span></span>
- <span data-ttu-id="992a6-115">사용자</span><span class="sxs-lookup"><span data-stu-id="992a6-115">Users</span></span>
- <span data-ttu-id="992a6-116">사서함</span><span class="sxs-lookup"><span data-stu-id="992a6-116">Mailboxes</span></span>

<span data-ttu-id="992a6-117">더 큰 공격의 일부가 될 특성을 보여주는 의심스러운 이벤트는 인시던트로 집계됩니다.</span><span class="sxs-lookup"><span data-stu-id="992a6-117">Suspicious events that show characteristics of being part of a larger attack are aggregated into an incident.</span></span> 

<span data-ttu-id="992a6-118">공격 범위를 확인하는 데 도움이 되는 공격이 시작된 위치와 기타 세부 정보를 정확하게 알 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="992a6-118">You'll know exactly where an attack started and other details to help you see the extent of the attack.</span></span>

<span data-ttu-id="992a6-119">플랫폼은 보안 방어자가 복잡한 크로스 엔터티 위협을 이해하고 처리하도록 올바른 시각 자료 및 데이터 표현을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="992a6-119">The platform provides security defenders with the right visuals and data representations to understand and address complex cross-entity threats.</span></span> 

<span data-ttu-id="992a6-120">공격 범위에 대한 가시성을 확보할 뿐만 아니라 인시던트를 방지하기 위한 전략적 단계를 수행하는 서비스에도 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="992a6-120">Not only will you have visibility on the scope of an attack, but you'll also have access to services that will allow you to take tactical steps to contain an incident.</span></span>


## <a name="related-topics"></a><span data-ttu-id="992a6-121">관련 항목</span><span class="sxs-lookup"><span data-stu-id="992a6-121">Related topics</span></span>
- [<span data-ttu-id="992a6-122">인시던트 우선 순위 지정</span><span class="sxs-lookup"><span data-stu-id="992a6-122">Prioritize incidents</span></span>](incident-queue.md)
- [<span data-ttu-id="992a6-123">인시던트 조사</span><span class="sxs-lookup"><span data-stu-id="992a6-123">Investigate incidents</span></span>](investigate-incidents.md)
- [<span data-ttu-id="992a6-124">인시던트 관리</span><span class="sxs-lookup"><span data-stu-id="992a6-124">Manage incidents</span></span>](manage-incidents.md)