---
title: Microsoft 365 Defender에서 인시던트 조사
description: 장치, 사용자 및 사서함과 관련된 인시던트를 분석합니다.
keywords: 인시던트, 컴퓨터, 장치, 사용자, ID, 메일, 전자 메일, 사서함, 조사, 그래프, 증거
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: macapara
author: mjcaparas
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
ms.openlocfilehash: 10fa2765a4fe5bd256e0588af0db51f5a22339a2
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51070052"
---
# <a name="investigate-incidents-in-microsoft-365-defender"></a><span data-ttu-id="20823-104">Microsoft 365 Defender에서 인시던트 조사</span><span class="sxs-lookup"><span data-stu-id="20823-104">Investigate incidents in Microsoft 365 Defender</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="20823-105">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="20823-105">**Applies to:**</span></span>

- <span data-ttu-id="20823-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="20823-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="20823-107">Microsoft 365 Defender는 장치, 사용자 및 사서함 전체의 모든 관련 경고, 자산, 조사 및 증거를 집계하여 공격의 전체 너비를 포괄적으로 살펴 봐야 합니다.</span><span class="sxs-lookup"><span data-stu-id="20823-107">Microsoft 365 Defender aggregates all related alerts, assets, investigations and evidence from across your devices, users, and mailboxes to give you a comprehensive look into the entire breadth of an attack.</span></span>

<span data-ttu-id="20823-108">네트워크에 영향을 미치는 알림을 조사하고, 해당 내용이 무엇인지 이해하고, 인시던트와 관련된 증거를 수집하여 효과적인 수정 계획을 세울 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="20823-108">Investigate the alerts that affect your network, understand what they mean, and collate evidence associated with the incidents so that you can devise an effective remediation plan.</span></span>

## <a name="investigate-an-incident"></a><span data-ttu-id="20823-109">인시던트 조사</span><span class="sxs-lookup"><span data-stu-id="20823-109">Investigate an incident</span></span>

1. <span data-ttu-id="20823-110">인시던트 대기열에서 인시던트를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="20823-110">Select an incident from the incident queue.</span></span> <BR> <span data-ttu-id="20823-111">사이드 패널이 열리며 상태, 심각도, 범주 및 영향을 주는 엔터티와 같은 중요한 정보를 미리 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="20823-111">A side panel opens and gives a preview of important information such as status, severity, categories, and the impacted entities.</span></span>

    ![인시던트 사이드 패널의 이미지](../../media/incident-side-panel.png)

2. <span data-ttu-id="20823-113">**인시던트 페이지 열기** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="20823-113">Select **Open incident page**.</span></span> <BR> <span data-ttu-id="20823-114">그러면 인시던트 세부 정보, 설명 및 작업, 탭(개요, 경고, 장치, 사용자, 조사, 증거)을 찾을 수 있는 인시던트 페이지가 열립니다.</span><span class="sxs-lookup"><span data-stu-id="20823-114">This opens the incident page where you'll find more information incident details, comments, and actions, tabs (overview, alerts, devices, users, investigations, evidence).</span></span>

3. <span data-ttu-id="20823-115">인시던트에 관련된 알림, 장치, 사용자, 기타 엔터티를 검토합니다.</span><span class="sxs-lookup"><span data-stu-id="20823-115">Review the alerts, devices, users, other entities involved in the incident.</span></span>

## <a name="incident-overview"></a><span data-ttu-id="20823-116">인시던트 개요</span><span class="sxs-lookup"><span data-stu-id="20823-116">Incident overview</span></span>

<span data-ttu-id="20823-117">개요 페이지에서는 인시던트에 대한 주요 정보를 볼 수 있는 스냅숏을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="20823-117">The overview page gives you a snapshot glance into the top things to notice about the incident.</span></span>

![인시던트 개요 페이지의 이미지](../../media/incidents-overview.png)

<span data-ttu-id="20823-119">공격 범주는 킬체인에 대해 공격이 진행된 상황을 시각적 및 숫자로 볼 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="20823-119">The attack categories give you a visual and numeric view of how advanced the attack has progressed against the kill chain.</span></span> <span data-ttu-id="20823-120">다른 Microsoft 보안 제품과 함께 Microsoft 365 Defender는 [MITRE ATT 및 &trade; CK](https://attack.mitre.org/)&정렬됩니다.</span><span class="sxs-lookup"><span data-stu-id="20823-120">As with other Microsoft security products, Microsoft 365 Defender is aligned to the [MITRE ATT&CK&trade;](https://attack.mitre.org/) framework.</span></span>

<span data-ttu-id="20823-121">범위 섹션에서는 이 인시던트의 일부인 영향을 받는 상위 자산 목록을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="20823-121">The scope section gives you a list of top impacted assets that are part of this incident.</span></span> <span data-ttu-id="20823-122">위험 수준, 조사 우선 순위 및 자산에 대한 태그 지정과 같은 해당 자산에 관한 특정 정보가 있는 경우 이 섹션에도 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="20823-122">If there is specific information regarding this asset, such as risk level, investigation priority as well as any tagging on the assets this will also surface in this section.</span></span>

<span data-ttu-id="20823-123">알림 시간 표시 막대는 알림이 발생한 시간 순서와 해당 인시던트에 대해 이러한 알림이 발생한 이유에 대한 미리 보기를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="20823-123">The alerts timeline provides a sneak peek into the chronological order in which the alerts occurred, as well as the reasons that these alerts linked to this incident.</span></span>

<span data-ttu-id="20823-124">그리고 마지막인 증거 섹션에는 인시던트에 얼마나 많은 아티팩트가 포함되었는지와 치료 상태에 대한 요약 정보가 제공되므로 사용자 측에서 어떤 조치가 필요한지 즉시 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="20823-124">And last - the evidence section provides a summary of how many different artifacts were included in the incident and their remediation status, so you can immediately identify if any action is needed on your end.</span></span>

<span data-ttu-id="20823-125">이 개요는 사용자가 알아야 할 인시던트의 주요 특징에 대한 통찰력을 제공함으로써 인시던트의 초기 분류를 도울 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="20823-125">This overview can assist in the initial triage of the incident by providing insight to the top characteristics of the incident that you should be aware of.</span></span>

## <a name="alerts"></a><span data-ttu-id="20823-126">알림</span><span class="sxs-lookup"><span data-stu-id="20823-126">Alerts</span></span>

<span data-ttu-id="20823-127">인시던트와 관련된 모든 경고 및 심각도, 경고에 관련된 엔터티, 경고의 원본(ID에 대한 Microsoft Defender, 끝점용 Microsoft Defender, Office 365용 Microsoft Defender) 및 이러한 경고가 함께 연결된 이유와 같은 기타 정보를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="20823-127">You can view all the alerts related to the incident and other information about them such as severity, entities that were involved in the alert, the source of the alerts (Microsoft Defender for Identity, Microsoft Defender for Endpoint, Microsoft Defender for Office 365) and the reason they were linked together.</span></span>

![인시던트 알림 페이지 이미지](../../media/incident-alerts.png)

<span data-ttu-id="20823-129">기본적으로 알림은 시간을 기준으로 순서대로 정렬되며, 이를 통해 시간에 따라 처음부터 공격이 진행된 방식을 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="20823-129">By default, the alerts are ordered chronologically, to allow you to first view how the attack played out over time.</span></span> <span data-ttu-id="20823-130">각 경고를 클릭하면 해당 경고에 대한 심층 조사를 실시할 수 있는 관련 경고 페이지로 이동됩니다.</span><span class="sxs-lookup"><span data-stu-id="20823-130">Clicking on each alert will lead you to the relevant alert page where you can conduct an in-depth investigation of that alert.</span></span> <span data-ttu-id="20823-131">경고 조사에서 경고 페이지 및 통합 경고 큐를 사용하는 [방법에 대해 자세히 알아보기](investigate-alerts.md)</span><span class="sxs-lookup"><span data-stu-id="20823-131">Learn how to use alert pages and the unified alert queue in [Investigate alerts](investigate-alerts.md)</span></span>

## <a name="devices"></a><span data-ttu-id="20823-132">장치</span><span class="sxs-lookup"><span data-stu-id="20823-132">Devices</span></span>

<span data-ttu-id="20823-133">장치 탭에는 인시던트와 관련된 알림이 표시되는 모든 장치가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="20823-133">The devices tab lists all the devices where alerts related to the incident are seen.</span></span>

<span data-ttu-id="20823-134">공격이 수행된 컴퓨터의 이름을 클릭하면 컴퓨터 페이지로 이동하여 해당 컴퓨터에서 트리거된 알림 및 관련 이벤트를 쉽게 조사할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="20823-134">Clicking the name of the machine where the attack was conducted navigates you to its Machine page where you can see alerts that were triggered on it and related events provided to ease investigation.</span></span>

![인시던트의 컴퓨터 탭 이미지](../../media/incident-machines.png)

<span data-ttu-id="20823-136">시간 표시 막대 탭을 선택하면 컴퓨터 시간 표시 막대를 스크롤하여 컴퓨터에서 관찰된 경고와 함께 시간 순서 대로 관찰된 모든 이벤트와 동작을 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="20823-136">Selecting the Timeline tab enables you to scroll through the machine timeline and view all events and behaviors observed on the machine in chronological order, interspersed with the alerts raised.</span></span>

## <a name="users"></a><span data-ttu-id="20823-137">사용자</span><span class="sxs-lookup"><span data-stu-id="20823-137">Users</span></span>

<span data-ttu-id="20823-138">주어진 인시던트의 일부로 식별되거나 이와 관련된 사용자를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="20823-138">See users that have been identified to be part of, or related to a given incident.</span></span>

<span data-ttu-id="20823-139">사용자 이름을 클릭하면 추가 조사를 수행할 수 있는 사용자의 클라우드 앱 보안 페이지로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="20823-139">Clicking the username navigates you to the user's Cloud App Security page where further investigation can be conducted.</span></span>

![인시던트의 사용자 탭 이미지](../../media/incident-users.png)

## <a name="mailboxes"></a><span data-ttu-id="20823-141">사서함</span><span class="sxs-lookup"><span data-stu-id="20823-141">Mailboxes</span></span>

<span data-ttu-id="20823-142">인시던트의 일부로 식별되거나 이와 관련된 사서함을 조사하세요.</span><span class="sxs-lookup"><span data-stu-id="20823-142">Investigate mailboxes that's been identified to be part of, or related to an incident.</span></span> <span data-ttu-id="20823-143">추가 조사 작업을 수행하려면 메일 관련 알림을 선택하면 수정 작업을 수행할 수 있는 Office 365용 Microsoft Defender가 열립니다.</span><span class="sxs-lookup"><span data-stu-id="20823-143">To do further investigative work, selecting the mail-related alert will open Microsoft Defender for Office 365 where you can take remediation actions.</span></span>

![인시던트의 사서함 탭 이미지](../../media/incident-mailboxes.png)

## <a name="investigations"></a><span data-ttu-id="20823-145">조사</span><span class="sxs-lookup"><span data-stu-id="20823-145">Investigations</span></span>

<span data-ttu-id="20823-146">조사를 **선택하여** 이 인시던트의 경고에 의해 트리거된 모든 자동화된 조사를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="20823-146">Select **Investigations** to see all the automated investigations triggered by alerts in this incident.</span></span> <span data-ttu-id="20823-147">조사는 끝점용 Microsoft Defender 및 Office 365용 Defender에서 자동화된 조사를 실행하도록 구성한 방법에 따라 수정 작업을 수행하거나 분석가의 작업 승인을 기다릴 것입니다.</span><span class="sxs-lookup"><span data-stu-id="20823-147">The investigations will perform remediation actions or wait for analyst approval of actions, depending on how you configured your automated investigations to run in Microsoft Defender for Endpoint and Defender for Office 365.</span></span>

![인시던트의 조사 탭 이미지](../../media/incident-investigations.png)

<span data-ttu-id="20823-149">조사를 선택하여 조사 세부 사항 페이지로 이동하고 조사 및 수정 상태에 대한 전체 정보를 확인하세요.</span><span class="sxs-lookup"><span data-stu-id="20823-149">Select an investigation to navigate to the Investigation details page to get full information on the investigation and remediation status.</span></span> <span data-ttu-id="20823-150">조사의 일부로 승인 보류 중인 작업이 있는 경우 보류 중인 작업 탭에 표시됩니다. 인시던트 수정의 일부로 조치를 취합니다.</span><span class="sxs-lookup"><span data-stu-id="20823-150">If there are any actions pending for approval as part of the investigation, they will appear in the Pending actions tab. Take action as part of incident remediation.</span></span>

## <a name="evidence"></a><span data-ttu-id="20823-151">증거</span><span class="sxs-lookup"><span data-stu-id="20823-151">Evidence</span></span>

<span data-ttu-id="20823-152">Microsoft 365 Defender는 경고에서 모든 인시던트 지원 이벤트 및 의심스러운 엔터티를 자동으로 조사하여 중요한 파일, 프로세스, 서비스, 전자 메일 등에 대한 자동 대응 및 정보를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="20823-152">Microsoft 365 Defender automatically investigates all the incidents' supported events and suspicious entities in the alerts, providing you with autoresponse and information about the important files, processes, services, emails, and more.</span></span> <span data-ttu-id="20823-153">이를 통해 인시던트의 잠재적 위협을 신속하게 탐지하고 차단할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="20823-153">This helps quickly detect and block potential threats in the incident.</span></span>

![인시던트의 증거 탭 이미지](../../media/incident-evidence.png)

<span data-ttu-id="20823-155">분석된 각 엔터티에는 수정 상태뿐만 아니라 결과 (악성적임, 의심스러움, 깨끗함)가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="20823-155">Each of the analyzed entities will be marked with a verdict (Malicious, Suspicious, Clean) as well as a remediation status.</span></span> <span data-ttu-id="20823-156">이를 통해 전체 인시던트의 수정 상태를 파악하고 추가적인 치료를 위한 다음 단계를 확인하는 데 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="20823-156">This assists you in understanding the remediation status of the entire incident and what are the next steps that can be taken to further remediate.</span></span>

## <a name="related-topics"></a><span data-ttu-id="20823-157">관련 항목</span><span class="sxs-lookup"><span data-stu-id="20823-157">Related topics</span></span>

- [<span data-ttu-id="20823-158">인시던트 개요</span><span class="sxs-lookup"><span data-stu-id="20823-158">Incidents overview</span></span>](incidents-overview.md)
- [<span data-ttu-id="20823-159">인시던트 우선 순위 지정</span><span class="sxs-lookup"><span data-stu-id="20823-159">Prioritize incidents</span></span>](incident-queue.md)
- [<span data-ttu-id="20823-160">인시던트 관리</span><span class="sxs-lookup"><span data-stu-id="20823-160">Manage incidents</span></span>](manage-incidents.md)

