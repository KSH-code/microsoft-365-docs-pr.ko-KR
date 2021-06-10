---
title: 첫 번째 인시던트에 대한 응답 소개
description: Defender에서 첫 번째 인시던트에 응답하는 기본 Microsoft 365.
keywords: 인시던트, 경고, 조사, 상관 관계, 공격, 장치, 사용자, ID, ID, 사서함, 전자 메일, 365, microsoft, m365, 인시던트 대응, 사이버 공격
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.technology: m365d
ms.openlocfilehash: 6e65a12f42b9f5f75c1a19cb9c4a261c94feaf31
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/08/2021
ms.locfileid: "52841717"
---
# <a name="introduction-to-responding-to-your-first-incident"></a><span data-ttu-id="f4535-104">첫 번째 인시던트에 대한 응답 소개</span><span class="sxs-lookup"><span data-stu-id="f4535-104">Introduction to responding to your first incident</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="f4535-105">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="f4535-105">**Applies to:**</span></span>
- <span data-ttu-id="f4535-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="f4535-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="f4535-107">조직의 인시던트 대응 전략에 따라 점점 더 파괴적인 보안 인시던트 및 사이버 범죄를 다루는 능력이 결정됩니다.</span><span class="sxs-lookup"><span data-stu-id="f4535-107">An organization's incident response strategy determines its ability to deal with increasingly disruptive security incidents and cybercrime.</span></span> <span data-ttu-id="f4535-108">예방 조치를 취하는 것이 중요하지만 감지된 인시던트의 포함, 지우기 및 복구를 신속하게 할 수 있는 능력은 손상 및 비즈니스 손실을 최소화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f4535-108">While taking preventative measures is important, the ability to act quickly to contain, eradicate, and recover from detected incidents can minimize damage and business losses.</span></span>

<span data-ttu-id="f4535-109">이 인시던트 대응 walkthrough에서는 보안 운영 팀의 일부로 보안 운영 팀의 일부로 사용자들이 Defender 내에서 대부분의 주요 인시던트 대응 Microsoft 365 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="f4535-109">This incident response walkthrough shows how you, as part of a security operations team, can perform most of the key incident response steps within Microsoft 365 Defender.</span></span> <span data-ttu-id="f4535-110">그 단계는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="f4535-110">Here are the steps:</span></span>

- <span data-ttu-id="f4535-111">보안 준비</span><span class="sxs-lookup"><span data-stu-id="f4535-111">Preparation of your security posture</span></span>
- <span data-ttu-id="f4535-112">각 인시던트에 대해:</span><span class="sxs-lookup"><span data-stu-id="f4535-112">For each incident:</span></span>
  - <span data-ttu-id="f4535-113">1단계: Triage and analysis</span><span class="sxs-lookup"><span data-stu-id="f4535-113">Step 1: Triage and analysis</span></span>
  - <span data-ttu-id="f4535-114">2단계: 수정(포함, 지우기 및 복구)</span><span class="sxs-lookup"><span data-stu-id="f4535-114">Step 2: Remediation (containment, eradication, and recovery)</span></span>
  - <span data-ttu-id="f4535-115">3단계: 인시던트 사후 검토</span><span class="sxs-lookup"><span data-stu-id="f4535-115">Step 3: Post-incident review</span></span>

<span data-ttu-id="f4535-116">보안 인시던트는 NIST(National Institute of Standards and Technology)에서 "정보 시스템의 기밀성, 무결성 또는 가용성을 실제로 또는 잠재적으로 위협하는 사건"으로 정의됩니다. 또는 시스템에서 처리, 저장 또는 전송하는 정보 또는 보안 정책, 보안 절차 또는 허용되는 사용 정책을 위반하거나 임박한 위협을 구성할 수 있습니다."</span><span class="sxs-lookup"><span data-stu-id="f4535-116">A security incident is defined by National Institute of Standards and Technology (NIST) as "an occurrence that actually or potentially jeopardizes the confidentiality, integrity, or availability of an information system; or the information the system processes, stores, or transmits; or that constitutes a violation or imminent threat of violation of security policies, security procedures, or acceptable use policies."</span></span>

<span data-ttu-id="f4535-117">Microsoft 365 인시던트는 분석 및 인시던트 대응을 위한 논리적인 시작점입니다.</span><span class="sxs-lookup"><span data-stu-id="f4535-117">Incidents in Microsoft 365 Defender are the logical starting points for analysis and incident response.</span></span> <span data-ttu-id="f4535-118">인시던트 분석 및 수정은 일반적으로 보안 운영 팀의 작업을 대부분 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="f4535-118">Analyzing and remediating incidents typically makes up most of a security operations team's tasks.</span></span>

## <a name="next-step"></a><span data-ttu-id="f4535-119">다음 단계</span><span class="sxs-lookup"><span data-stu-id="f4535-119">Next step</span></span>

<span data-ttu-id="f4535-120">[![조직 및 테넌트 Microsoft 365 준비](../../media/first-incident-overview/first-incident-path.png)](first-incident-prepare.md)</span><span class="sxs-lookup"><span data-stu-id="f4535-120">[![Prepare your organization and Microsoft 365 tenant](../../media/first-incident-overview/first-incident-path.png)](first-incident-prepare.md)</span></span>

<span data-ttu-id="f4535-121">조직 및 Microsoft 365 테넌트가 인시던트 [처리를 준비해야 합니다.](first-incident-prepare.md)</span><span class="sxs-lookup"><span data-stu-id="f4535-121">Make sure your organization and Microsoft 365 tenant is [prepared for incident handling](first-incident-prepare.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="f4535-122">참고 항목</span><span class="sxs-lookup"><span data-stu-id="f4535-122">See also</span></span>

<span data-ttu-id="f4535-123">Defender에 대한 인시던트 Microsoft 365 지침:</span><span class="sxs-lookup"><span data-stu-id="f4535-123">Incident response guidance for Microsoft 365 Defender:</span></span>

- [<span data-ttu-id="f4535-124">사고 개요</span><span class="sxs-lookup"><span data-stu-id="f4535-124">Incidents overview</span></span>](incidents-overview.md)
- [<span data-ttu-id="f4535-125">사고 조사</span><span class="sxs-lookup"><span data-stu-id="f4535-125">Investigate incidents</span></span>](investigate-incidents.md)
- [<span data-ttu-id="f4535-126">인시던트 관리</span><span class="sxs-lookup"><span data-stu-id="f4535-126">Manage incidents</span></span>](manage-incidents.md)

<span data-ttu-id="f4535-127">첫 번째 인시던트 대응의 추가 예:</span><span class="sxs-lookup"><span data-stu-id="f4535-127">Additional examples of first incident responses:</span></span>

- [<span data-ttu-id="f4535-128">피싱 전자 메일</span><span class="sxs-lookup"><span data-stu-id="f4535-128">Phishing email</span></span>](first-incident-path-phishing.md)
- [<span data-ttu-id="f4535-129">ID 기반 공격</span><span class="sxs-lookup"><span data-stu-id="f4535-129">Identity-base attack</span></span>](first-incident-path-identity.md)

[<span data-ttu-id="f4535-130">자세한 인시던트 대응 플레이북</span><span class="sxs-lookup"><span data-stu-id="f4535-130">Detailed incident response playbooks</span></span>](/security/compass/incident-response-playbooks)


