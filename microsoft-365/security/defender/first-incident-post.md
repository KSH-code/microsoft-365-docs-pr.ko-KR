---
title: 3단계. 첫 번째 인시던트에 대한 인시던트 사후 검토 수행
description: Defender에서 첫 번째 인시던트에 대한 Microsoft 365 방법.
keywords: 인시던트, 경고, 조사, 상관 관계, 공격, 컴퓨터, 장치, 사용자, IDs, ID, 사서함, 전자 메일, 365, microsoft, m365
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
ms.openlocfilehash: 6b5311a2923d7b299ba4f70ef3c2e8d91809e7c8
ms.sourcegitcommit: 07e536f1a6e335f114da55048844e4a866fe731b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/25/2021
ms.locfileid: "52651371"
---
# <a name="step-3-perform-a-post-incident-review-of-your-first-incident"></a><span data-ttu-id="c118d-105">3단계.</span><span class="sxs-lookup"><span data-stu-id="c118d-105">Step 3.</span></span> <span data-ttu-id="c118d-106">첫 번째 인시던트에 대한 인시던트 사후 검토 수행</span><span class="sxs-lookup"><span data-stu-id="c118d-106">Perform a post-incident review of your first incident</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="c118d-107">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="c118d-107">**Applies to:**</span></span>
- <span data-ttu-id="c118d-108">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="c118d-108">Microsoft 365 Defender</span></span>

<span data-ttu-id="c118d-109">NIST(National Institute of Standards and Technology)에서는 공격으로부터 복구하기 위해 모든 단계를 수행한 후 조직에서 인시던트에 대해 알아보고 보안 자세 또는 프로세스를 개선해야 하게 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="c118d-109">National Institute of Standards and Technology (NIST) recommends that once all steps have been taken to recover from the attack, organizations must review the incident to learn from it and improve security posture or processes.</span></span> <span data-ttu-id="c118d-110">인시던트 처리의 다양한 측면을 평가하는 것은 다음 인시던트 준비에서 중요합니다.</span><span class="sxs-lookup"><span data-stu-id="c118d-110">Assessing the different aspects of incident-handling becomes important in preparing for the next incident.</span></span>

<span data-ttu-id="c118d-111">Microsoft 365 Defender는 [MITRE ATT 및 CK Framework에 부합하는](https://attack.mitre.org/)경고를 조직에 제공하여 인시던트&수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c118d-111">Microsoft 365 Defender can assist in performing post-incident activities by providing an organization with alerts that align with [MITRE ATT&CK Framework](https://attack.mitre.org/).</span></span> <span data-ttu-id="c118d-112">모든 Microsoft Defender 솔루션 레이블 공격은 ATT에 따라 CK&또는 기술에 따라 레이블 공격을 합니다.</span><span class="sxs-lookup"><span data-stu-id="c118d-112">All Microsoft Defender solutions label attacks in accordance with an ATT&CK tactic or technique.</span></span> 

<span data-ttu-id="c118d-113">이 산업 프레임워크에 경고를 매핑하면 다음을 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c118d-113">By mapping alerts to this industry framework, you can:</span></span>

- <span data-ttu-id="c118d-114">보안 범위의 격차를 분석합니다.</span><span class="sxs-lookup"><span data-stu-id="c118d-114">Conduct an analysis of gaps in security coverage.</span></span>
- <span data-ttu-id="c118d-115">대적 및 캠페인 기여를 파악합니다.</span><span class="sxs-lookup"><span data-stu-id="c118d-115">Determine adversary and campaign attribution.</span></span>
- <span data-ttu-id="c118d-116">추세 분석을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="c118d-116">Perform trend analysis.</span></span>
- <span data-ttu-id="c118d-117">공격 방법 인식에서 기술 격차를 식별합니다.</span><span class="sxs-lookup"><span data-stu-id="c118d-117">Identify skill gaps in attack method awareness.</span></span>
- <span data-ttu-id="c118d-118">더 Power Automate 위해 Playbook을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c118d-118">Create a Power Automate Playbook for faster remediation.</span></span> 

<span data-ttu-id="c118d-119">인시던트 사후 검토 활동도 보안 구성 및 보안 팀의 프로세스를 미세 조정하여 조직의 응답 기능을 향상할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c118d-119">Post-incident review activity can also result in fine-tuning your security configuration and security team's processes, enhancing your organization’s response capabilities.</span></span>

## <a name="next-step"></a><span data-ttu-id="c118d-120">다음 단계</span><span class="sxs-lookup"><span data-stu-id="c118d-120">Next step</span></span>

<span data-ttu-id="c118d-121">다음 추가 조사 경로를 참조합니다.</span><span class="sxs-lookup"><span data-stu-id="c118d-121">See these additional investigation paths:</span></span>

- [<span data-ttu-id="c118d-122">피싱 전자 메일</span><span class="sxs-lookup"><span data-stu-id="c118d-122">Phishing email</span></span>](first-incident-path-phishing.md)
- [<span data-ttu-id="c118d-123">ID 기반 공격</span><span class="sxs-lookup"><span data-stu-id="c118d-123">Identity-based attack</span></span>](first-incident-path-identity.md)


## <a name="see-also"></a><span data-ttu-id="c118d-124">참고 항목</span><span class="sxs-lookup"><span data-stu-id="c118d-124">See also</span></span>

- [<span data-ttu-id="c118d-125">사고 개요</span><span class="sxs-lookup"><span data-stu-id="c118d-125">Incidents overview</span></span>](incidents-overview.md)
- [<span data-ttu-id="c118d-126">사고 조사</span><span class="sxs-lookup"><span data-stu-id="c118d-126">Investigate incidents</span></span>](investigate-incidents.md)
- [<span data-ttu-id="c118d-127">인시던트 관리</span><span class="sxs-lookup"><span data-stu-id="c118d-127">Manage incidents</span></span>](manage-incidents.md)
