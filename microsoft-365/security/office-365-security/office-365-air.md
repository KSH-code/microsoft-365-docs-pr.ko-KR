---
title: Office 365 자동 조사 및 응답
keywords: AIR, autoIR, ATP, 자동화, 조사, 대응, 재구성, 위협, 고급, 위협, 보호
f1.keywords:
- NOCSH
ms.author: deniseb
author: denisebmsft
manager: dansimp
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.collection: M365-security-compliance
description: Office 365 Advanced Threat Protection 계획 2의 자동화 된 조사 및 응답 기능 사용을 시작 하세요.
ms.openlocfilehash: d777ca0a61655c8df16d62c72691195bdec330a9
ms.sourcegitcommit: 2f117a6fd27a097ca25afa933dd088b69d483974
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/20/2020
ms.locfileid: "42175782"
---
# <a name="office-365-automated-investigation-and-response"></a><span data-ttu-id="09f3d-104">Office 365 자동 조사 및 응답</span><span class="sxs-lookup"><span data-stu-id="09f3d-104">Office 365 automated investigation and response</span></span>

<span data-ttu-id="09f3d-105">[Office 365 Advanced Threat Protection](office-365-atp.md) 요금제 2에는 보안 작업 팀의 시간과 노력을 줄일 수 있는 강력한 자동 조사 및 응답 (AIR) 기능이 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="09f3d-105">[Office 365 Advanced Threat Protection](office-365-atp.md) Plan 2 includes powerful automated investigation and response (AIR) capabilities that can save your security operations team time and effort.</span></span> <span data-ttu-id="09f3d-106">특정 알림이 트리거되면 하나 이상의 보안 playbook가 시작 되 고 자동화 된 조사 프로세스가 시작 됩니다.</span><span class="sxs-lookup"><span data-stu-id="09f3d-106">When certain alerts are triggered, one or more security playbooks initiate, and the automated investigation process begins.</span></span> <span data-ttu-id="09f3d-107">이를 통해 보안 운영 팀은 트리거된 경고에 대 한 시야 없이 우선 순위가 높은 작업에 집중할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="09f3d-107">This empowers your security operations team to focus on high-priority tasks without losing sight of alerts that are triggered.</span></span> 

<span data-ttu-id="09f3d-108">높은 수준에서 AIR 흐름은 다음과 같은 방식으로 작동 합니다.</span><span class="sxs-lookup"><span data-stu-id="09f3d-108">At a high level, the AIR flow works like this:</span></span>

|<span data-ttu-id="09f3d-109">단계</span><span class="sxs-lookup"><span data-stu-id="09f3d-109">Step</span></span>  |<span data-ttu-id="09f3d-110">진행 작업</span><span class="sxs-lookup"><span data-stu-id="09f3d-110">What happens</span></span>  |
|---------|---------|
|<span data-ttu-id="09f3d-111">개</span><span class="sxs-lookup"><span data-stu-id="09f3d-111">1</span></span>     |<span data-ttu-id="09f3d-112">Office 이벤트에 의해 알림이 트리거되고 [보안 playbook](automated-investigation-response-office.md#security-playbooks) 선택한 경고에 대 한 자동 조사를 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="09f3d-112">An alert is triggered by an Office event and a [security playbook](automated-investigation-response-office.md#security-playbooks) initiates an automated investigation for selected alerts.</span></span> <br/><br/><span data-ttu-id="09f3d-113">또는 보안 분석가가 [위협 탐색기](threat-explorer.md)를 사용 하는 동안 [자동화 된 조사를 트리거할](automated-investigation-response-office.md#example-a-security-administrator-triggers-an-investigation-from-threat-explorer) 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="09f3d-113">Alternately, a security analyst can [trigger an automated investigation](automated-investigation-response-office.md#example-a-security-administrator-triggers-an-investigation-from-threat-explorer) while using [Threat Explorer](threat-explorer.md).</span></span>        |
|<span data-ttu-id="09f3d-114">2</span><span class="sxs-lookup"><span data-stu-id="09f3d-114">2</span></span>     |<span data-ttu-id="09f3d-115">자동 조사가 실행 되는 동안 전자 메일 및 해당 전자 메일에 관련 된 엔터티에 대 한 추가 데이터 (파일, Url 및 받는 사람)를 수집 합니다.</span><span class="sxs-lookup"><span data-stu-id="09f3d-115">While an automated investigation runs, it gathers additional data about the email and the entities related to that email – files, URLs, and recipients.</span></span>  <span data-ttu-id="09f3d-116">새 관련 경고가 트리거되면 조사 범위가 증가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="09f3d-116">The investigation's scope can increase, as new related alerts are triggered.</span></span>         |
|<span data-ttu-id="09f3d-117">3(sp3)</span><span class="sxs-lookup"><span data-stu-id="09f3d-117">3</span></span>     |<span data-ttu-id="09f3d-118">자동화 된 조사 도중 및 후에 [세부 정보 및 결과](air-view-investigation-results.md) 를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="09f3d-118">During and after an automated investigation, [details and results](air-view-investigation-results.md) are available to view.</span></span> <span data-ttu-id="09f3d-119">결과에는 발견 된 모든 위협을 응답 하 고 수정 하기 위해 취할 수 있는 [권장 작업이](air-remediation-actions.md) 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="09f3d-119">Results include [recommended actions](air-remediation-actions.md) that can be taken to respond and remediate any threats that were found.</span></span> <span data-ttu-id="09f3d-120">또한 모든 조사 활동을 추적 하는 [playbook 로그](air-view-investigation-results.md#playbook-log) 를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="09f3d-120">In addition, a [playbook log](air-view-investigation-results.md#playbook-log) is available that tracks all investigation activity.</span></span><br/><br/><span data-ttu-id="09f3d-121">조직에서 사용자 지정 보고 솔루션 또는 타사 솔루션을 사용 하는 경우에는 [Office 365 관리 활동 API를 사용](air-custom-reporting.md) 하 여 자동화 된 조사 및 위협에 대 한 정보를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="09f3d-121">If your organization is using a custom reporting solution or a third-party solution, you can [use the Office 365 Management Activity API](air-custom-reporting.md) to view information about automated investigations and threats.</span></span>         |
|<span data-ttu-id="09f3d-122">1-4</span><span class="sxs-lookup"><span data-stu-id="09f3d-122">4</span></span>     |<span data-ttu-id="09f3d-123">보안 운영 팀은 [조사 결과 및 권장 사항을](air-view-investigation-results.md)검토 하 고 [업데이트 관리 작업을 승인](air-remediation-actions.md#approve-or-reject-pending-actions)합니다.</span><span class="sxs-lookup"><span data-stu-id="09f3d-123">Your security operations team reviews the [investigation results and recommendations](air-view-investigation-results.md), and [approves remediation actions](air-remediation-actions.md#approve-or-reject-pending-actions).</span></span> <span data-ttu-id="09f3d-124">Office 365에서는 작업이 자동으로 수행 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="09f3d-124">In Office 365, no actions are taken automatically.</span></span> <span data-ttu-id="09f3d-125">관리 작업은 조직의 보안 팀이 승인 하는 경우에만 수행 됩니다.</span><span class="sxs-lookup"><span data-stu-id="09f3d-125">Remediation actions are taken only upon approval by your organization's security team.</span></span>         |

<span data-ttu-id="09f3d-126">자동화 된 조사 프로세스 중 및 이후에 보안 팀은 다음을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="09f3d-126">During and after an automated investigation process, your security team can do the following:</span></span>

- [<span data-ttu-id="09f3d-127">조사와 관련 된 경고에 대 한 세부 정보 보기</span><span class="sxs-lookup"><span data-stu-id="09f3d-127">View details about an alert related to an investigation</span></span>](air-view-investigation-results.md#view-details-about-an-alert-related-to-an-investigation)
- [<span data-ttu-id="09f3d-128">조사 결과 세부 정보 보기</span><span class="sxs-lookup"><span data-stu-id="09f3d-128">View the results details of an investigation</span></span>](air-view-investigation-results.md#view-details-of-an-investigation)
- [<span data-ttu-id="09f3d-129">조사 결과로 작업 검토 및 승인</span><span class="sxs-lookup"><span data-stu-id="09f3d-129">Review and approve actions as a result of an investigation</span></span>](air-remediation-actions.md#approve-or-reject-pending-actions)

<span data-ttu-id="09f3d-130">자세한 내용은 [AIR works](https://docs.microsoft.com/microsoft-365/security/office-365-security/automated-investigation-response-office)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="09f3d-130">To learn more, see [How AIR works](https://docs.microsoft.com/microsoft-365/security/office-365-security/automated-investigation-response-office).</span></span>