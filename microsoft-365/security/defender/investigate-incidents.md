---
title: Defender에서 인시던트 Microsoft 365 분석
description: 장치, 사용자 및 사서함과 관련된 인시던트를 분석합니다.
keywords: 인시던트, 인시던트, 분석, 응답, 컴퓨터, 장치, 사용자, ID, 메일, 전자 메일, 사서함, 조사, 그래프, 증거
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
ms.openlocfilehash: 72e1efb8a06fb7fa64b83ab6522fe4cdcfd1a73e
ms.sourcegitcommit: 5a1cb7d95070eef47d401a4693cc137a90550a5e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/06/2021
ms.locfileid: "52259639"
---
# <a name="analyze-incidents-in-microsoft-365-defender"></a><span data-ttu-id="e7689-104">Defender에서 인시던트 Microsoft 365 분석</span><span class="sxs-lookup"><span data-stu-id="e7689-104">Analyze incidents in Microsoft 365 Defender</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="e7689-105">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="e7689-105">**Applies to:**</span></span>

- <span data-ttu-id="e7689-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="e7689-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="e7689-107">Microsoft 365 Defender는 장치, 사용자 및 사서함에서 모든 관련 경고, 자산, 조사 및 증거를 인시던트에 집계하여 공격의 전체 너비를 포괄적으로 살펴 봐야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e7689-107">Microsoft 365 Defender aggregates all related alerts, assets, investigations, and evidence from across your devices, users, and mailboxes into an incident to give you a comprehensive look into the entire breadth of an attack.</span></span>

<span data-ttu-id="e7689-108">인시던트 내에서 네트워크에 영향을 주는 경고를 분석하고, 경고의 의미를 이해하고, 효과적인 수정 계획을 고안할 수 있도록 증거를 수집합니다.</span><span class="sxs-lookup"><span data-stu-id="e7689-108">Within an incident, you analyze the alerts that affect your network, understand what they mean, and collate the evidence so that you can devise an effective remediation plan.</span></span>

## <a name="initial-analysis"></a><span data-ttu-id="e7689-109">초기 분석</span><span class="sxs-lookup"><span data-stu-id="e7689-109">Initial analysis</span></span>

<span data-ttu-id="e7689-110">세부 정보를 살펴보기 전에 인시던트의 속성과 요약을 살펴보아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e7689-110">Before diving into the details, take a look at the properties and summary of the incident.</span></span>

<span data-ttu-id="e7689-111">확인 표시 열에서 인시던트부터 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e7689-111">You can start by selecting the incident from the check mark column.</span></span> <span data-ttu-id="e7689-112">다음은 예입니다.</span><span class="sxs-lookup"><span data-stu-id="e7689-112">Here's an example.</span></span>

:::image type="content" source="../../media/investigate-incidents/incidents-ss-incident-select.png" alt-text="확인 표시 열에서 인시던트 선택 예제":::

<span data-ttu-id="e7689-114">이렇게 하는 경우 인시던트에 대한 주요 정보(예: 심각도, 할당된 사용자) 및 [MITRE ATT가 &trade; ](https://attack.mitre.org/) 인시던트에 대한 CK 범주를&창이 열립니다.</span><span class="sxs-lookup"><span data-stu-id="e7689-114">When you do, a summary pane opens with key information about the incident, such as severity, to whom it is assigned, and the [MITRE ATT&CK&trade;](https://attack.mitre.org/) categories for the incident.</span></span> <span data-ttu-id="e7689-115">다음은 예입니다.</span><span class="sxs-lookup"><span data-stu-id="e7689-115">Here's an example.</span></span>

:::image type="content" source="../../media/investigate-incidents/incidents-ss-incident-side-panel.png" alt-text="인시던트에 대한 요약 창의 예":::

<span data-ttu-id="e7689-117">여기에서 문제 페이지 **열기 를 선택할 수 있습니다.**</span><span class="sxs-lookup"><span data-stu-id="e7689-117">From here, you can select **Open incident page**.</span></span> <span data-ttu-id="e7689-118">그러면 경고, 장치, 사용자, 조사 및 증거에 대한 추가 요약 정보와 탭을 찾을 수 있는 인시던트의 기본 페이지가 열립니다.</span><span class="sxs-lookup"><span data-stu-id="e7689-118">This opens the main page for the incident where you'll find more summary information and tabs for alerts, devices, users, investigations, and evidence.</span></span>

<span data-ttu-id="e7689-119">인시던트 큐에서 인시던트 이름을 선택하여 인시던트의 기본 페이지를 열 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e7689-119">You can also open the main page for an incident by selecting the incident name from the incident queue.</span></span>

## <a name="summary"></a><span data-ttu-id="e7689-120">요약</span><span class="sxs-lookup"><span data-stu-id="e7689-120">Summary</span></span>

<span data-ttu-id="e7689-121">요약 **페이지에서는** 인시던트에 대해 가장 많이 알 수 있는 스냅숏을 한눈에 알 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e7689-121">The **Summary** page gives you a snapshot glance at the top things to notice about the incident.</span></span>

:::image type="content" source="../../media/incidents-overview/incidents-ss-incident-summary.png" alt-text="보안 센터의 인시던트에 대한 요약 Microsoft 365 예":::

<span data-ttu-id="e7689-123">공격 범주는 킬체인에 대해 공격이 진행된 상황을 시각적 및 숫자로 볼 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="e7689-123">The attack categories give you a visual and numeric view of how advanced the attack has progressed against the kill chain.</span></span> <span data-ttu-id="e7689-124">다른 Microsoft 보안 제품과 Microsoft 365 Defender는 [MITRE ATT &trade; ](https://attack.mitre.org/) 및 CK&정렬됩니다.</span><span class="sxs-lookup"><span data-stu-id="e7689-124">As with other Microsoft security products, Microsoft 365 Defender is aligned to the [MITRE ATT&CK&trade;](https://attack.mitre.org/) framework.</span></span>

<span data-ttu-id="e7689-125">범위 섹션에서는 이 인시던트의 일부인 영향을 받는 상위 자산 목록을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="e7689-125">The scope section gives you a list of top impacted assets that are part of this incident.</span></span> <span data-ttu-id="e7689-126">위험 수준, 조사 우선 순위 및 자산에 대한 태그 지정과 같은 해당 자산에 관한 특정 정보가 있는 경우 이 섹션에도 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="e7689-126">If there is specific information regarding this asset, such as risk level, investigation priority as well as any tagging on the assets this will also surface in this section.</span></span>

<span data-ttu-id="e7689-127">경고 타임라인은 경고가 발생한 시간 순서와 이러한 경고가 이 인시던트와 연결되는 이유에 대해 살피는 기능을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="e7689-127">The alerts timeline provides a sneak peek into the chronological order in which the alerts occurred, as well as the reasons that these alerts are linked to this incident.</span></span>

<span data-ttu-id="e7689-128">마지막 - 증거 섹션에서는 인시던트에 포함된 다양한 아티팩트 수와 수정 상태에 대한 요약을 제공 하여 사용자가 조치가 필요한지 즉시 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e7689-128">And last - the evidence section provides a summary of how many different artifacts were included in the incident and their remediation status, so you can immediately identify if any action is needed by you.</span></span>

<span data-ttu-id="e7689-129">이 개요는 파악해야 하는 인시던트의 주요 특징에 대한 정보를 제공하여 인시던트의 초기 조사를 지원할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e7689-129">This overview can assist in the initial triage of the incident by providing insight into the top characteristics of the incident that you should be aware of.</span></span>

## <a name="alerts"></a><span data-ttu-id="e7689-130">경고</span><span class="sxs-lookup"><span data-stu-id="e7689-130">Alerts</span></span>

<span data-ttu-id="e7689-131">경고 **탭에서** 인시던트와 관련된 경고 및 경고에 대한 기타 정보(예: )에 대한 경고 큐를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e7689-131">On the **Alert** tab, you can view the alert queue for alerts related to the incident and other information about them such as:</span></span>

- <span data-ttu-id="e7689-132">심각도.</span><span class="sxs-lookup"><span data-stu-id="e7689-132">Severity.</span></span>
- <span data-ttu-id="e7689-133">경고에 관련된 엔터티입니다.</span><span class="sxs-lookup"><span data-stu-id="e7689-133">The entities that were involved in the alert.</span></span>
- <span data-ttu-id="e7689-134">경고의 원본(ID용 Microsoft Defender, 끝점용 Microsoft Defender, Microsoft Defender for Office 365).</span><span class="sxs-lookup"><span data-stu-id="e7689-134">The source of the alerts (Microsoft Defender for Identity, Microsoft Defender for Endpoint, Microsoft Defender for Office 365).</span></span>
- <span data-ttu-id="e7689-135">함께 연결된 이유입니다.</span><span class="sxs-lookup"><span data-stu-id="e7689-135">The reason they were linked together.</span></span>

<span data-ttu-id="e7689-136">다음은 예입니다.</span><span class="sxs-lookup"><span data-stu-id="e7689-136">Here's an example.</span></span>

:::image type="content" source="../../media/investigate-incidents/incident-alerts.png" alt-text="인시던트에 대한 경고 페이지 예":::

<span data-ttu-id="e7689-138">기본적으로 경고는 시간이 지날 때 인시던트가 어떻게 재생되는지 볼 수 있도록 시간 순서대로 지정됩니다.</span><span class="sxs-lookup"><span data-stu-id="e7689-138">By default, the alerts are ordered chronologically to allow you to see how the incident played out over time.</span></span> <span data-ttu-id="e7689-139">각 경고를 선택하면 경고의 기본 페이지로 이동하여 해당 경고에 대한 심층 분석을 진행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e7689-139">Selecting each alert takes you to the alert's main page where you can conduct an in-depth analysis of that alert.</span></span> 

<span data-ttu-id="e7689-140">경고 분석에서 경고 큐 및 경고 페이지를 사용하는 [방법 학습](investigate-alerts.md)</span><span class="sxs-lookup"><span data-stu-id="e7689-140">Learn how to use the alert queue and alert pages in [analyze alerts](investigate-alerts.md)</span></span>

## <a name="devices"></a><span data-ttu-id="e7689-141">디바이스</span><span class="sxs-lookup"><span data-stu-id="e7689-141">Devices</span></span>

<span data-ttu-id="e7689-142">장치 **탭에는** 인시던트와 관련된 모든 장치가 나열됩니다.</span><span class="sxs-lookup"><span data-stu-id="e7689-142">The **Devices** tab lists all the devices related to the incident.</span></span> <span data-ttu-id="e7689-143">다음은 예입니다.</span><span class="sxs-lookup"><span data-stu-id="e7689-143">Here's an example.</span></span>

:::image type="content" source="../../media/investigate-incidents/incident-devices.png" alt-text="인시던트에 대한 장치 페이지의 예":::

<span data-ttu-id="e7689-145">장치의 확인 표시를 선택하여 장치, 디렉터리 데이터, 활성 경고 및 로그온한 사용자의 세부 정보를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e7689-145">You can select the check mark for a device to see details of the device, directory data, active alerts, and logged on users.</span></span> <span data-ttu-id="e7689-146">Microsoft Defender for Endpoints 장치 인벤토리에서 장치 세부 정보를 확인하려면 장치의 이름을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="e7689-146">Select the name of the device to see device details in the Microsoft Defender for Endpoints device inventory.</span></span>

:::image type="content" source="../../media/investigate-incidents/incident-devices-details.png" alt-text="끝점용 Microsoft Defender의 장치 페이지 예":::

<span data-ttu-id="e7689-148">디바이스 페이지에서 모든 경고, 타임라인 및 보안 권장 사항과 같은 장치에 대한 추가 정보를 수집할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e7689-148">From the device page, you can gather additional information about the device, such as all of its alerts, a timeline, and security recommendations.</span></span> <span data-ttu-id="e7689-149">예를 들어 시간  표시 막대 탭에서 컴퓨터 타임라인을 스크롤하여 컴퓨터에서 관찰된 모든 이벤트와 동작을 시간 순서대로 볼 수 있으며, 경고가 발생했습니다.</span><span class="sxs-lookup"><span data-stu-id="e7689-149">For example, from the **Timeline** tab, you can scroll through the machine timeline and view all events and behaviors observed on the machine in chronological order, interspersed with the alerts raised.</span></span>

> [!TIP]
> <span data-ttu-id="e7689-150">디바이스 페이지에서는 필요한 경우 검색을 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e7689-150">You can do on-demand scans on a device page.</span></span> <span data-ttu-id="e7689-151">In the Microsoft 365 security center, choose **Endpoints > Device inventory**.</span><span class="sxs-lookup"><span data-stu-id="e7689-151">In the Microsoft 365 security center, choose **Endpoints > Device inventory**.</span></span> <span data-ttu-id="e7689-152">경고가 있는 장치를 선택한 다음 바이러스 백신 검색을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="e7689-152">Select a device that has alerts, and then run an antivirus scan.</span></span> <span data-ttu-id="e7689-153">바이러스 백신 검사와 같은 작업은 추적되어 장치 인벤토리 **페이지에** 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="e7689-153">Actions, such as antivirus scans, are tracked and are visible on the **Device inventory** page.</span></span> <span data-ttu-id="e7689-154">자세한 내용은 장치에서 Microsoft Defender 바이러스 백신 [실행을 참조합니다.](/microsoft-365/security/defender-endpoint/respond-machine-alerts#run-microsoft-defender-antivirus-scan-on-devices)</span><span class="sxs-lookup"><span data-stu-id="e7689-154">To learn more, see [Run Microsoft Defender Antivirus scan on devices](/microsoft-365/security/defender-endpoint/respond-machine-alerts#run-microsoft-defender-antivirus-scan-on-devices).</span></span>

## <a name="users"></a><span data-ttu-id="e7689-155">사용자</span><span class="sxs-lookup"><span data-stu-id="e7689-155">Users</span></span>

<span data-ttu-id="e7689-156">사용자 **탭에는** 인시던트의 일부로 식별되거나 인시던트와 관련된 것으로 식별된 모든 사용자가 나열됩니다.</span><span class="sxs-lookup"><span data-stu-id="e7689-156">The **Users** tab lists all the users that have been identified to be part of or related to the incident.</span></span> <span data-ttu-id="e7689-157">다음은 예입니다.</span><span class="sxs-lookup"><span data-stu-id="e7689-157">Here's an example.</span></span>

:::image type="content" source="../../media/investigate-incidents/incident-users.png" alt-text="인시던트에 대한 사용자 페이지의 예":::

<span data-ttu-id="e7689-159">사용자의 확인 표시를 선택하여 사용자 계정 위협, 노출 및 연락처 정보에 대한 세부 정보를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e7689-159">You can select the check mark for a user to see details of the user account threat, exposure, and contact information.</span></span> <span data-ttu-id="e7689-160">사용자 이름을 선택하여 추가 사용자 계정 세부 정보를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e7689-160">Select the user name to see additional user account details.</span></span>

## <a name="mailboxes"></a><span data-ttu-id="e7689-161">사서함</span><span class="sxs-lookup"><span data-stu-id="e7689-161">Mailboxes</span></span>

<span data-ttu-id="e7689-162">사서함 **탭에는** 인시던트의 일부로 식별되거나 인시던트와 관련이 있는 것으로 확인된 모든 사서함이 나열됩니다.</span><span class="sxs-lookup"><span data-stu-id="e7689-162">The **Mailboxes** tab lists all the mailboxes that have been identified to be part of or related to the incident.</span></span> <span data-ttu-id="e7689-163">다음은 예입니다.</span><span class="sxs-lookup"><span data-stu-id="e7689-163">Here's an example.</span></span>

:::image type="content" source="../../media/investigate-incidents/incident-mailboxes.png" alt-text="인시던트에 대한 사서함 페이지의 예":::

<span data-ttu-id="e7689-165">사서함의 확인 표시를 선택하여 활성 경고 목록을 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e7689-165">You can select the check mark for a mailbox to see a list of active alerts.</span></span> <span data-ttu-id="e7689-166">사서함 이름을 선택하여 Microsoft Defender for Office 365.</span><span class="sxs-lookup"><span data-stu-id="e7689-166">Select the mailbox name to see additional mailbox details on the Explorer page for Microsoft Defender for Office 365.</span></span>

## <a name="investigations"></a><span data-ttu-id="e7689-167">조사</span><span class="sxs-lookup"><span data-stu-id="e7689-167">Investigations</span></span>

<span data-ttu-id="e7689-168">조사 **탭에는** 이 인시던트의 경고에 의해 트리거된 모든 자동화된 조사가 나열됩니다.</span><span class="sxs-lookup"><span data-stu-id="e7689-168">The **Investigations** tab lists all the automated investigations triggered by alerts in this incident.</span></span> <span data-ttu-id="e7689-169">조사는 Microsoft Defender for Endpoint 및 Defender for Office 365에서 자동화된 조사를 실행하도록 구성한 방법에 따라 수정 작업을 수행하거나 분석가의 작업 승인을 Office 365.</span><span class="sxs-lookup"><span data-stu-id="e7689-169">The investigations will perform remediation actions or wait for analyst approval of actions, depending on how you configured your automated investigations to run in Microsoft Defender for Endpoint and Defender for Office 365.</span></span>

:::image type="content" source="../../media/investigate-incidents/incident-investigations.png" alt-text="인시던트에 대한 조사 페이지의 예":::

<span data-ttu-id="e7689-171">조사를 선택하여 조사 세부 사항 페이지로 이동하고 조사 및 수정 상태에 대한 전체 정보를 확인하세요.</span><span class="sxs-lookup"><span data-stu-id="e7689-171">Select an investigation to navigate to the Investigation details page to get full information on the investigation and remediation status.</span></span> <span data-ttu-id="e7689-172">조사의 일부로 승인 보류 중인 작업이 있는 경우 보류 중인 작업 탭에 표시됩니다. 인시던트 수정의 일부로 조치를 취합니다.</span><span class="sxs-lookup"><span data-stu-id="e7689-172">If there are any actions pending for approval as part of the investigation, they will appear in the Pending actions tab. Take action as part of incident remediation.</span></span>

## <a name="evidence-and-response"></a><span data-ttu-id="e7689-173">증거 및 응답</span><span class="sxs-lookup"><span data-stu-id="e7689-173">Evidence and Response</span></span>

<span data-ttu-id="e7689-174">증거 **및 응답 탭에는** 인시던트의 경고에서 지원되는 모든 이벤트와 의심스러운 엔터티가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="e7689-174">The **Evidence and Response** tab shows all the supported events and suspicious entities in the alerts in the incident.</span></span> <span data-ttu-id="e7689-175">다음은 예입니다.</span><span class="sxs-lookup"><span data-stu-id="e7689-175">Here's an example.</span></span>

:::image type="content" source="../../media/investigate-incidents/incident-evidence.png" alt-text="인시던트에 대한 증거 및 응답 페이지의 예":::

<span data-ttu-id="e7689-177">Microsoft 365 Defender는 경고에서 모든 인시던트 지원 이벤트 및 의심스러운 엔터티를 자동으로 조사하여 중요한 전자 메일, 파일, 프로세스, 서비스, IP 주소에 대한 정보를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="e7689-177">Microsoft 365 Defender automatically investigates all the incidents' supported events and suspicious entities in the alerts, providing you with information about the important emails, files, processes, services, IP Addresses, and more.</span></span> <span data-ttu-id="e7689-178">이렇게 하면 인시던트의 잠재적인 위협을 빠르게 감지하고 차단할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e7689-178">This helps you quickly detect and block potential threats in the incident.</span></span>

<span data-ttu-id="e7689-179">분석된 각 엔터티는 판정(악성, 의심스러운, 정리)과 수정 상태로 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="e7689-179">Each of the analyzed entities is marked with a verdict (Malicious, Suspicious, Clean) and a remediation status.</span></span> <span data-ttu-id="e7689-180">이렇게 하면 전체 인시던트의 수정 상태와 다음 단계를 이해하는 데 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e7689-180">This helps you understand the remediation status of the entire incident and what next steps can be taken.</span></span>

## <a name="graph-in-preview"></a><span data-ttu-id="e7689-181">Graph(미리 보기)</span><span class="sxs-lookup"><span data-stu-id="e7689-181">Graph (in Preview)</span></span>

<span data-ttu-id="e7689-182">새 **Graph** 탭(미리 보기)을 사용하면 다음을 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e7689-182">With the new **Graph** tab (in preview), you can see:</span></span>

- <span data-ttu-id="e7689-183">조직의 영향을 미치는 자산에 대한 경고 연결</span><span class="sxs-lookup"><span data-stu-id="e7689-183">The connection of alerts to the impacted assets in your organization.</span></span>
- <span data-ttu-id="e7689-184">경고와 관련된 엔터티 및 해당 경고가 공격에 대한 스토리의 일부인 방식</span><span class="sxs-lookup"><span data-stu-id="e7689-184">Which entities are related to which alerts and how they are part of the story of the attack.</span></span>
- <span data-ttu-id="e7689-185">인시던트에 대한 경고입니다.</span><span class="sxs-lookup"><span data-stu-id="e7689-185">The alerts for the incident.</span></span>

<span data-ttu-id="e7689-186">다음은 예입니다.</span><span class="sxs-lookup"><span data-stu-id="e7689-186">Here's an example.</span></span>

:::image type="content" source="../../media/investigate-incidents/incident-graph.png" alt-text="인시던트에 대한 Graph 페이지의 예":::

<span data-ttu-id="e7689-188">인시던트 그래프를 사용하면 공격의 일부인 여러 의심스러운 엔터티를 사용자, 장치 및 사서함과 같은 관련 자산에 연결하여 공격의 전체 범위를 빠르게 이해할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e7689-188">The incident graph helps you quickly understand the full scope of the attack by connecting the different suspicious entities that are part of the attack with their related assets such as users, devices, and mailboxes.</span></span> 

<span data-ttu-id="e7689-189">이제 시간이 지날 때 네트워크를 통해 공격이 확산되는 방식, 공격이 시작된 위치 및 공격이 얼마나 진행된지 이해할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e7689-189">Now you can understand how the attack spread through your network over time, where it started, and how far the attack went.</span></span>


## <a name="related-topics"></a><span data-ttu-id="e7689-190">관련 항목</span><span class="sxs-lookup"><span data-stu-id="e7689-190">Related topics</span></span>

- [<span data-ttu-id="e7689-191">인시던트 개요</span><span class="sxs-lookup"><span data-stu-id="e7689-191">Incidents overview</span></span>](incidents-overview.md)
- [<span data-ttu-id="e7689-192">인시던트 우선 순위 지정</span><span class="sxs-lookup"><span data-stu-id="e7689-192">Prioritize incidents</span></span>](incident-queue.md)
- [<span data-ttu-id="e7689-193">인시던트 관리</span><span class="sxs-lookup"><span data-stu-id="e7689-193">Manage incidents</span></span>](manage-incidents.md)

