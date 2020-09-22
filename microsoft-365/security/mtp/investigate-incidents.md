---
title: Microsoft Threat Protection의 인시던트 조사
description: 장치, 사용자 및 사서함과 관련된 인시던트를 분석합니다.
keywords: 인시던트, 컴퓨터, 장치, 사용자, ID, 메일, 전자 메일, 사서함, 조사, 그래프, 증거
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
ms.collection: M365-security-compliance
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.openlocfilehash: 46d82220851c78525bd0b1ee00c4abae69c0304f
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/22/2020
ms.locfileid: "48196314"
---
# <a name="investigate-incidents-in-microsoft-threat-protection"></a><span data-ttu-id="6993e-104">Microsoft Threat Protection의 인시던트 조사</span><span class="sxs-lookup"><span data-stu-id="6993e-104">Investigate incidents in Microsoft Threat Protection</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="6993e-105">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="6993e-105">**Applies to:**</span></span>

- <span data-ttu-id="6993e-106">Microsoft 위협 방지</span><span class="sxs-lookup"><span data-stu-id="6993e-106">Microsoft Threat Protection</span></span>

<span data-ttu-id="6993e-107">Microsoft Threat Protection은 모든 장치, 사용자 및 사서함에 대한 모든 관련 알림, 자산, 조사 및 증거를 집계하여 공격의 전체 범위를 포괄적으로 파악합니다.</span><span class="sxs-lookup"><span data-stu-id="6993e-107">Microsoft Threat Protection aggregates all related alerts, assets, investigations and evidence from across your devices, users, and mailboxes to give you a comprehensive look into the entire breadth of an attack.</span></span>

<span data-ttu-id="6993e-108">네트워크에 영향을 미치는 알림을 조사하고, 해당 내용이 무엇인지 이해하고, 인시던트와 관련된 증거를 수집하여 효과적인 수정 계획을 세울 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6993e-108">Investigate the alerts that affect your network, understand what they mean, and collate evidence associated with the incidents so that you can devise an effective remediation plan.</span></span>

## <a name="investigate-an-incident"></a><span data-ttu-id="6993e-109">인시던트 조사</span><span class="sxs-lookup"><span data-stu-id="6993e-109">Investigate an incident</span></span>

1. <span data-ttu-id="6993e-110">인시던트 대기열에서 인시던트를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="6993e-110">Select an incident from the incident queue.</span></span> <BR> <span data-ttu-id="6993e-111">그러면 사이드 패널이 열리고 상태, 심각도, 범주, 영향을 받는 엔터티 등과 같은 중요한 정보를 미리 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6993e-111">This opens a side panel and gives a preview of important information such as status, severity, categories, and the impacted entities.</span></span>

    ![인시던트 사이드 패널의 이미지](../../media/incident-side-panel.png)

2. <span data-ttu-id="6993e-113">**인시던트 페이지 열기**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="6993e-113">Select **Open incident page**.</span></span> <BR> <span data-ttu-id="6993e-114">그러면 인시던트 세부 정보, 메모 및 작업, 탭 (개요, 알림, 장치, 사용자, 조사, 증거)을 찾을 수있는 인시던트 페이지가 열립니다.</span><span class="sxs-lookup"><span data-stu-id="6993e-114">This opens the incident page where you'll find more information incident details, comments and actions, tabs (overview, alerts, devices, users, investigations, evidence).</span></span>

3. <span data-ttu-id="6993e-115">인시던트에 관련된 알림, 장치, 사용자, 기타 엔터티를 검토합니다.</span><span class="sxs-lookup"><span data-stu-id="6993e-115">Review the alerts, devices, users, other entities involved in the incident.</span></span>

## <a name="incident-overview"></a><span data-ttu-id="6993e-116">인시던트 개요</span><span class="sxs-lookup"><span data-stu-id="6993e-116">Incident overview</span></span>

<span data-ttu-id="6993e-117">개요 페이지에서는 인시던트에 대한 주요 정보를 볼 수 있는 스냅숏을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="6993e-117">The overview page gives you a snapshot glance into the top things to notice about the incident.</span></span>

![인시던트 개요 페이지의 이미지](../../media/incidents-overview.png)

<span data-ttu-id="6993e-119">공격 범주는 kill chain에 대한 공격 진행 정도를 시각적으로 그리고 수치적으로 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="6993e-119">The attack categories give you visual and numeric view of how advanced the attack has progressed against the kill chain.</span></span> <span data-ttu-id="6993e-120">다른 Microsoft 보안 제품과 마찬가지로 Microsoft Threat Protection은 [MITER ATT&CK&trade;](https://attack.mitre.org/) 프레임워크에 맞춰져 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6993e-120">As with other Microsoft security products, Microsoft Threat Protection is aligned to the [MITRE ATT&CK&trade;](https://attack.mitre.org/) framework.</span></span>

<span data-ttu-id="6993e-121">범위 섹션에서는 이 인시던트의 일부인 영향을 받는 상위 자산 목록을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="6993e-121">The scope section gives you a list of top impacted assets that are part of this incident.</span></span> <span data-ttu-id="6993e-122">위험 수준, 조사 우선 순위 및 자산에 대한 태그 지정과 같은 해당 자산에 관한 특정 정보가 있는 경우 이 섹션에도 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="6993e-122">If there is specific information regarding this asset, such as risk level, investigation priority as well as any tagging on the assets this will also surface in this section.</span></span>

<span data-ttu-id="6993e-123">알림 시간 표시 막대는 알림이 발생한 시간 순서와 해당 인시던트에 대해 이러한 알림이 발생한 이유에 대한 미리 보기를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="6993e-123">The alerts timeline provides a sneak peek into the chronological order in which the alerts occurred, as well as the reasons that these alerts linked to this incident.</span></span>

<span data-ttu-id="6993e-124">그리고 마지막인 증거 섹션에는 인시던트에 얼마나 많은 아티팩트가 포함되었는지와 치료 상태에 대한 요약 정보가 제공되므로 사용자 측에서 어떤 조치가 필요한지 즉시 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6993e-124">And last - the evidence section provides a summary of how many different artifacts were included in the incident and their remediation status, so you can immediately identify if any action is needed on your end.</span></span>

<span data-ttu-id="6993e-125">이 개요는 사용자가 알아야 할 인시던트의 주요 특징에 대한 통찰력을 제공함으로써 인시던트의 초기 분류를 도울 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6993e-125">This overview can assist in the initial triage of the incident by providing insight to the top characteristics of the incident that you should be aware of.</span></span>

## <a name="alerts"></a><span data-ttu-id="6993e-126">알림</span><span class="sxs-lookup"><span data-stu-id="6993e-126">Alerts</span></span>

<span data-ttu-id="6993e-127">인시던트와 관련된 모든 알림과 해당 인시던트에 대한 기타 정보를 볼 수 있습니다. 예를 들어 심각도, 알림과 관련된 엔터티, 알림 출처 (Azure ATP, Microsoft Defender ATP, Office 365 ATP), 그리고 이들이 연관된 이유들이 해당됩니다.</span><span class="sxs-lookup"><span data-stu-id="6993e-127">You can view all the alerts related to the incident and other information about them such as severity, entities that were involved in the alert, the source of the alerts (Azure ATP, Microsoft Defender ATP , Office  365 ATP) and the reason they were linked together.</span></span>

![인시던트 알림 페이지 이미지](../../media/incident-alerts.png)

<span data-ttu-id="6993e-129">기본적으로 알림은 시간을 기준으로 순서대로 정렬되며, 이를 통해 시간에 따라 처음부터 공격이 진행된 방식을 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6993e-129">By default, the alerts are ordered chronologically, to allow you to first view how the attack played out over time.</span></span> <span data-ttu-id="6993e-130">각 알림을 클릭하면 해당 경고에 대한 심도 있는 조사를 수행할 수 있는 관련 경고 페이지를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6993e-130">Clicking on each alert will lead you to the relevant alert page where you can conduct an in depth investigation of that alert.</span></span>

## <a name="devices"></a><span data-ttu-id="6993e-131">장치</span><span class="sxs-lookup"><span data-stu-id="6993e-131">Devices</span></span>

<span data-ttu-id="6993e-132">장치 탭에는 인시던트와 관련된 알림이 표시되는 모든 장치가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="6993e-132">The devices tab lists all the devices where alerts related to the incident are seen.</span></span>

<span data-ttu-id="6993e-133">공격이 수행된 컴퓨터의 이름을 클릭하면 컴퓨터 페이지로 이동하여 해당 컴퓨터에서 트리거된 알림 및 관련 이벤트를 쉽게 조사할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6993e-133">Clicking the name of the machine where the attack was conducted navigates you to its Machine page where you can see alerts that were triggered on it and related events provided to ease investigation.</span></span>

![인시던트의 컴퓨터 탭 이미지](../../media/incident-machines.png)

<span data-ttu-id="6993e-135">시간 표시 막대 탭을 선택하면 컴퓨터 시간 표시 막대를 스크롤하여 컴퓨터에서 관찰된 경고와 함께 시간 순서 대로 관찰된 모든 이벤트와 동작을 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6993e-135">Selecting the Timeline tab enables you to scroll through the machine timeline and view all events and behaviors observed on the machine in chronological order, interspersed with the alerts raised.</span></span>

## <a name="users"></a><span data-ttu-id="6993e-136">사용자</span><span class="sxs-lookup"><span data-stu-id="6993e-136">Users</span></span>

<span data-ttu-id="6993e-137">주어진 인시던트의 일부로 식별되거나 이와 관련된 사용자를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="6993e-137">See users that have been identified to be part of, or related to a given incident.</span></span>

<span data-ttu-id="6993e-138">사용자 이름을 클릭하면 추가 조사를 수행할 수 있는 사용자의 클라우드 앱 보안 페이지로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="6993e-138">Clicking the username navigates you to the user's Cloud App Security page where further investigation can be conducted.</span></span>

![인시던트의 사용자 탭 이미지](../../media/incident-users.png)

## <a name="mailboxes"></a><span data-ttu-id="6993e-140">사서함</span><span class="sxs-lookup"><span data-stu-id="6993e-140">Mailboxes</span></span>

<span data-ttu-id="6993e-141">인시던트의 일부로 식별되거나 이와 관련된 사서함을 조사하세요.</span><span class="sxs-lookup"><span data-stu-id="6993e-141">Investigate mailboxes that's been identified to be part of, or related to an incident.</span></span> <span data-ttu-id="6993e-142">추가 조사 작업을 수행하기 위해 메일 관련 알림을 선택하면 수정 작업을 취할 수 있는 Office 365 Advanced Threat Protection이 열립니다.</span><span class="sxs-lookup"><span data-stu-id="6993e-142">To do further investigative work, selecting the mail related alert will open Office 365 Advanced Threat Protection where you can take remediation actions.</span></span>

![인시던트의 사서함 탭 이미지](../../media/incident-mailboxes.png)

## <a name="investigations"></a><span data-ttu-id="6993e-144">조사</span><span class="sxs-lookup"><span data-stu-id="6993e-144">Investigations</span></span>

<span data-ttu-id="6993e-145">이 인시던트의 경고에 의해 트리거된 모든 자동화 된 조사를 확인 하려면 **조사** 를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="6993e-145">Select **Investigations** to see all the automated investigations triggered by alerts in this incident.</span></span> <span data-ttu-id="6993e-146">사용자가 Microsoft Defender ATP 및 Office 365 Advanced Threat Protection에서 자동화된 조사를 실행하도록 구성한 방법에 따라, 조사는 수정 작업을 수행하거나 분석가의 작업 승인을 기다립니다.</span><span class="sxs-lookup"><span data-stu-id="6993e-146">The investigations will perform remediation actions or wait for analyst approval of actions, depending on how you configured your automated investigations to run in Microsoft Defender ATP and Office 365 Advanced Threat Protection.</span></span>

![인시던트의 조사 탭 이미지](../../media/incident-investigations.png)

<span data-ttu-id="6993e-148">조사를 선택하여 조사 세부 사항 페이지로 이동하고 조사 및 수정 상태에 대한 전체 정보를 확인하세요.</span><span class="sxs-lookup"><span data-stu-id="6993e-148">Select an investigation to navigate to the Investigation details page to get full information on the investigation and remediation status.</span></span> <span data-ttu-id="6993e-149">조사의 일부로 승인 대기중인 작업이 있으면 보류중인 작업 탭에 나타납니다. 인시던트 수정의 일부로 조치를 취합니다.</span><span class="sxs-lookup"><span data-stu-id="6993e-149">If there are any actions pending for approval as part of the investigation they will appear in the Pending actions tab. Take action as part of incident remediation.</span></span>

## <a name="evidence"></a><span data-ttu-id="6993e-150">증거</span><span class="sxs-lookup"><span data-stu-id="6993e-150">Evidence</span></span>

<span data-ttu-id="6993e-151">Microsoft Threat Protection은 알림에서 모든 인시던트 지원 이벤트 및 의심스러운 엔터티를 자동으로 조사하여 중요한 파일, 프로세스, 서비스, 전자 메일 등에 대한 자동 응답 및 정보를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="6993e-151">Microsoft Threat Protection automatically investigates all the incidents' supported events and suspicious entities in the alerts, providing you with auto-response and information about the important files, processes, services, emails, and more.</span></span> <span data-ttu-id="6993e-152">이를 통해 인시던트의 잠재적 위협을 신속하게 탐지하고 차단할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6993e-152">This helps quickly detect and block potential threats in the incident.</span></span>

![인시던트의 증거 탭 이미지](../../media/incident-evidence.png)

<span data-ttu-id="6993e-154">분석된 각 엔터티에는 수정 상태뿐만 아니라 결과 (악성적임, 의심스러움, 깨끗함)가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="6993e-154">Each of the analyzed entities will be marked with a verdict (Malicious, Suspicious, Clean) as well as a remediation status.</span></span> <span data-ttu-id="6993e-155">이를 통해 전체 인시던트의 수정 상태를 파악하고 추가적인 치료를 위한 다음 단계를 확인하는 데 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6993e-155">This assists you in understanding the remediation status of the entire incident and what are the next steps that can be taken to further remediate.</span></span>

## <a name="related-topics"></a><span data-ttu-id="6993e-156">관련 항목</span><span class="sxs-lookup"><span data-stu-id="6993e-156">Related topics</span></span>

- [<span data-ttu-id="6993e-157">인시던트 개요</span><span class="sxs-lookup"><span data-stu-id="6993e-157">Incidents overview</span></span>](incidents-overview.md)
- [<span data-ttu-id="6993e-158">인시던트 우선 순위 지정</span><span class="sxs-lookup"><span data-stu-id="6993e-158">Prioritize incidents</span></span>](incident-queue.md)
- [<span data-ttu-id="6993e-159">인시던트 관리</span><span class="sxs-lookup"><span data-stu-id="6993e-159">Manage incidents</span></span>](manage-incidents.md)

