---
title: Microsoft 365 Defender의 문제 개요
description: 여러 장치, 사용자 및 사서함에 표시되는 인시던트를 조사합니다.
keywords: 인시던트, 경고, 조사, 상관 관계, 공격, 컴퓨터, 장치, 사용자, IDs, ID, 사서함, 전자 메일, 365, microsoft, m365
search.product: eADQiWindows 10XVcnh
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.openlocfilehash: 6149b6f128b3c96d2338e325caa8df835c292b13
ms.sourcegitcommit: 474bd6a86c3692d11fb2c454591c89029ac5bbd5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/19/2020
ms.locfileid: "49357614"
---
# <a name="incidents-overview-in-microsoft-365-defender"></a><span data-ttu-id="a69d2-104">Microsoft 365 Defender의 문제 개요</span><span class="sxs-lookup"><span data-stu-id="a69d2-104">Incidents overview in Microsoft 365 Defender</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="a69d2-105">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="a69d2-105">**Applies to:**</span></span>
- <span data-ttu-id="a69d2-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="a69d2-106">Microsoft 365 Defender</span></span>

> <span data-ttu-id="a69d2-107">Microsoft 365 Defender를 경험해 원하십니까?</span><span class="sxs-lookup"><span data-stu-id="a69d2-107">Want to experience Microsoft 365 Defender?</span></span> <span data-ttu-id="a69d2-108">[랩 환경에서이를 평가](https://aka.ms/mtp-trial-lab) 하거나 [프로덕션에서 파일럿 프로젝트를 실행할](https://aka.ms/m365d-pilotplaybook)수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a69d2-108">You can [evaluate it in a lab environment](https://aka.ms/mtp-trial-lab) or [run your pilot project in production](https://aka.ms/m365d-pilotplaybook).</span></span>
>


<span data-ttu-id="a69d2-109">인시던트는 관련 경고에 따라 달라 집니다.</span><span class="sxs-lookup"><span data-stu-id="a69d2-109">Incidents are based on related alerts.</span></span> <span data-ttu-id="a69d2-110">네트워크에서 악성 이벤트 또는 활동이 발견되면 경고가 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="a69d2-110">Alerts are created when a malicious event or activity is seen on your network.</span></span> <span data-ttu-id="a69d2-111">개별 알림은 진행 중인 공격에 대 한 귀중 한 단서를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="a69d2-111">Individual alerts provide valuable clues about an on-going attack.</span></span> <span data-ttu-id="a69d2-112">그러나 일반적으로 공격에서는 다양 한 벡터와 기법을 사용 하 여 위반을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="a69d2-112">However, attacks typically employ various vectors and techniques to carry out a breach.</span></span> <span data-ttu-id="a69d2-113">개별 단서를 함께 사용 하는 것은 Piecing 시간이 많이 소요 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a69d2-113">Piecing individual clues together can be challenging and time-consuming.</span></span>

<span data-ttu-id="a69d2-114">이 짧은 비디오에서는 Microsoft 365 Defender의 문제에 대 한 개요를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="a69d2-114">This short video gives an overview of incidents in Microsoft 365 Defender.</span></span>
<br>

>[!VIDEO https://www.microsoft.com/videoplayer/embed/RE4Bzwz?]

<span data-ttu-id="a69d2-115">인시던트는 공격에 대 한 이야기를 구성 하는 상호 연관 된 경고의 모음입니다.</span><span class="sxs-lookup"><span data-stu-id="a69d2-115">An incident is a collection of correlated alerts that make up the story of an attack.</span></span> <span data-ttu-id="a69d2-116">네트워크의 서로 다른 장치, 사용자 및 사서함 엔터티에 있는 악의적이 고 의심 스러운 이벤트는 Microsoft 365 Defender에서 자동으로 집계 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a69d2-116">Malicious and suspicious events that are found in different device, user, and mailbox entities in the network are automatically aggregated by Microsoft 365 Defender.</span></span> <span data-ttu-id="a69d2-117">관련 알림을 인시던트로 그룹화 하면 보안 defenders 공격에 대 한 포괄적인 보기가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a69d2-117">Grouping related alerts into an incident gives security defenders a comprehensive view of an attack.</span></span> 

<span data-ttu-id="a69d2-118">예를 들어 보안 defenders는 공격이 시작 된 위치, 사용 된 방법 및 공격이 네트워크에 침입 한 정도를 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a69d2-118">For instance, security defenders can see where the attack started, what tactics were used, and how far the attack has gone into the network.</span></span> <span data-ttu-id="a69d2-119">영향을 받는 장치, 사용자 및 사서함의 수, 영향을 받는 정도, 영향을 받은 엔터티에 대 한 기타 세부 정보와 같은 공격 범위를 볼 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a69d2-119">They can also see the scope of the attack, like how many devices, users, and mailboxes were impacted, how severe the impact was, and other details about affected entities.</span></span>

<span data-ttu-id="a69d2-120">이 옵션을 설정 하면 Microsoft 365 Defender에서 자동화 및 인공 지능을 통해 개별 알림을 자동으로 조사 하 고 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a69d2-120">If enabled, Microsoft 365 Defender can automatically investigate and resolve the individual alerts through automation and artificial intelligence.</span></span> <span data-ttu-id="a69d2-121">보안 defenders 문제 보기에서 직접 공격을 해결 하기 위한 추가 수정 단계를 수행할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a69d2-121">Security defenders can also perform additional remediation steps to resolve the attack straight from the incidents view.</span></span> 

<span data-ttu-id="a69d2-122">지난 30 일 동안의 인시던트는 인시던트 큐에 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a69d2-122">Incidents from the last 30 days are shown in the incident queue.</span></span> <span data-ttu-id="a69d2-123">여기에서 보안 defenders는 위험 수준 및 기타 요소에 따라 우선 순위를 지정 해야 하는 인시던트를 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a69d2-123">From here, security defenders can see which incidents should be prioritized based on risk level and other factors.</span></span> 

<span data-ttu-id="a69d2-124">또한 보안 defenders 인시던트 이름을 바꾸고, 개별 분석가에 게 할당 하 고, 인시던트에 태그를 추가 하 여 보다 나은 사용자 지정 된 인시던트 관리 환경을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a69d2-124">Security defenders can also rename incidents, assign them to individual analysts, classify, and add tags to incidents for a better and more customized incident management experience.</span></span>



## <a name="see-also"></a><span data-ttu-id="a69d2-125">참고 항목</span><span class="sxs-lookup"><span data-stu-id="a69d2-125">See also</span></span>
- [<span data-ttu-id="a69d2-126">인시던트 우선 순위 지정</span><span class="sxs-lookup"><span data-stu-id="a69d2-126">Prioritize incidents</span></span>](incident-queue.md)
- [<span data-ttu-id="a69d2-127">인시던트 조사</span><span class="sxs-lookup"><span data-stu-id="a69d2-127">Investigate incidents</span></span>](investigate-incidents.md)
- [<span data-ttu-id="a69d2-128">인시던트 관리</span><span class="sxs-lookup"><span data-stu-id="a69d2-128">Manage incidents</span></span>](manage-incidents.md)
