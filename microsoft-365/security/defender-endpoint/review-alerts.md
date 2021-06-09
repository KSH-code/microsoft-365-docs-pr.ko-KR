---
title: 끝점용 Microsoft Defender의 경고 검토
description: 시각화된 경고 스토리 및 체인의 각 단계에 대한 세부 정보를 포함하여 경고 정보를 검토합니다.
keywords: 인시던트, 인시던트, 컴퓨터, 장치, 사용자, 경고, 경고, 조사, 그래프, 증거
ms.prod: m365-security
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: daniha
author: dansimp
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: conceptual
ms.date: 5/1/2020
ms.technology: mde
ms.openlocfilehash: b17af7931b181a5fa30271a3eee07c7abf10a010
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/08/2021
ms.locfileid: "52844025"
---
# <a name="review-alerts-in-microsoft-defender-for-endpoint"></a><span data-ttu-id="74c67-104">끝점용 Microsoft Defender의 경고 검토</span><span class="sxs-lookup"><span data-stu-id="74c67-104">Review alerts in Microsoft Defender for Endpoint</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="74c67-105">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="74c67-105">**Applies to:**</span></span>
- [<span data-ttu-id="74c67-106">엔드포인트용 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="74c67-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)

><span data-ttu-id="74c67-107">Endpoint용 Defender를 경험하고 싶나요?</span><span class="sxs-lookup"><span data-stu-id="74c67-107">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="74c67-108">무료 평가판에 등록합니다.</span><span class="sxs-lookup"><span data-stu-id="74c67-108">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-managealerts-abovefoldlink)

<span data-ttu-id="74c67-109">Microsoft Defender for Endpoint의 경고 페이지는 선택한 경고와 관련된 공격 신호 및 경고를 결합하여 자세한 경고 스토리를 생성하여 경고에 대한 전체 컨텍스트를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="74c67-109">The alert page in Microsoft Defender for Endpoint provides full context to the alert, by combining attack signals and alerts related to the selected alert, to construct a detailed alert story.</span></span>

<span data-ttu-id="74c67-110">조직에 영향을 주는 경고를 신속하게 조사하고 효과적인 조치를 취합니다.</span><span class="sxs-lookup"><span data-stu-id="74c67-110">Quickly triage, investigate, and take effective action on alerts that affect your organization.</span></span> <span data-ttu-id="74c67-111">트리거된 이유와 한 위치에서의 영향에 대해 이해합니다.</span><span class="sxs-lookup"><span data-stu-id="74c67-111">Understand why they were triggered, and their impact from one location.</span></span> <span data-ttu-id="74c67-112">자세한 내용은 이 개요를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="74c67-112">Learn more in this overview.</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4yiO5]

## <a name="getting-started-with-an-alert"></a><span data-ttu-id="74c67-113">경고 시작</span><span class="sxs-lookup"><span data-stu-id="74c67-113">Getting started with an alert</span></span>

<span data-ttu-id="74c67-114">끝점용 Defender에서 경고 이름을 선택하면 경고 페이지로 이동됩니다.</span><span class="sxs-lookup"><span data-stu-id="74c67-114">Selecting an alert's name in Defender for Endpoint will land you on its alert page.</span></span> <span data-ttu-id="74c67-115">경고 페이지에서 모든 정보가 선택한 경고의 컨텍스트로 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="74c67-115">On the alert page, all the information will be shown in context of the selected alert.</span></span> <span data-ttu-id="74c67-116">각 경고 페이지는 다음 4개 섹션으로 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="74c67-116">Each alert page consists of 4 sections:</span></span>

1. <span data-ttu-id="74c67-117">**경고 제목은** 경고의 이름을 표시하며 페이지에서 선택한 경고에 관계없이 현재 조사를 시작한 경고를 알려 주게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="74c67-117">**The alert title** shows the alert's name and is there to remind you which alert started your current investigation regardless of what you have selected on the page.</span></span>
2. <span data-ttu-id="74c67-118">[**영향을 받는 자산에는**](#review-affected-assets) 추가 정보 및 작업에 대해 클릭할 수 있는 이 경고의 영향을 받는 장치 및 사용자의 카드가 나열됩니다.</span><span class="sxs-lookup"><span data-stu-id="74c67-118">[**Affected assets**](#review-affected-assets) lists cards of devices and users affected by this alert that are clickable for further information and actions.</span></span>
3. <span data-ttu-id="74c67-119">경고 **스토리에는** 경고와 관련된 모든 엔터티가 트리 보기로 상호 연결됩니다.</span><span class="sxs-lookup"><span data-stu-id="74c67-119">The **alert story** displays all entities related to the alert, interconnected by a tree view.</span></span> <span data-ttu-id="74c67-120">제목의 경고는 선택한 경고 페이지에 처음 방문할 때 포커스가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="74c67-120">The alert in the title will be the one in focus when you first land on your selected alert's page.</span></span> <span data-ttu-id="74c67-121">경고 스토리의 엔터티는 확장 및 클릭 가능하여 경고 페이지의 컨텍스트에서 바로 작업을 수행할 수 있도록 하여 추가 정보와 응답을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="74c67-121">Entities in the alert story are expandable and clickable, to provide additional information and expedite response by allowing you to take actions right in the context of the alert page.</span></span> <span data-ttu-id="74c67-122">경고 스토리를 사용하여 조사를 시작할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="74c67-122">Use the alert story to start your investigation.</span></span> <span data-ttu-id="74c67-123">Microsoft Defender for [Endpoint에서 경고 조사에서 방법을 알아보습니다.](/microsoft-365/security/defender-endpoint/investigate-alerts)</span><span class="sxs-lookup"><span data-stu-id="74c67-123">Learn how in [Investigate alerts in Microsoft Defender for Endpoint](/microsoft-365/security/defender-endpoint/investigate-alerts).</span></span>
4. <span data-ttu-id="74c67-124">세부 **정보 창에는** 처음에 선택한 경고의 세부 정보 및 이 경고와 관련된 세부 정보 및 작업이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="74c67-124">The **details pane** will show the details of the selected alert at first, with details and actions related to this alert.</span></span> <span data-ttu-id="74c67-125">경고 스토리에서 영향을 받는 자산 또는 엔터티를 선택하면 세부 정보 창이 변경되어 선택한 개체에 대한 상황에 맞는 정보 및 작업을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="74c67-125">If you select any of the affected assets or entities in the alert story, the details pane will change to provide contextual information and actions for the selected object.</span></span>

<span data-ttu-id="74c67-126">경고의 검색 상태를 메모합니다.</span><span class="sxs-lookup"><span data-stu-id="74c67-126">Note the detection status for your alert.</span></span> 
- <span data-ttu-id="74c67-127">금지 - 의심스러운 작업을 피했습니다.</span><span class="sxs-lookup"><span data-stu-id="74c67-127">Prevented – The attempted suspicious action was avoided.</span></span> <span data-ttu-id="74c67-128">예를 들어 파일이 디스크에 기록되지 않은 경우나 실행되지 않았습니다.</span><span class="sxs-lookup"><span data-stu-id="74c67-128">For example, a file either wasn’t written to disk or executed.</span></span>
<span data-ttu-id="74c67-129">![위협을 표시하는 경고 페이지가 차단된 경우](images/detstat-prevented.png)</span><span class="sxs-lookup"><span data-stu-id="74c67-129">![An alert page showing threat was prevented](images/detstat-prevented.png)</span></span>
- <span data-ttu-id="74c67-130">차단 - 의심스러운 동작이 실행된 다음 차단됩니다.</span><span class="sxs-lookup"><span data-stu-id="74c67-130">Blocked – Suspicious behavior was executed and then blocked.</span></span> <span data-ttu-id="74c67-131">예를 들어 프로세스가 실행된 후 의심스러운 동작이 나타냈기 때문에 프로세스가 종료되었습니다.</span><span class="sxs-lookup"><span data-stu-id="74c67-131">For example, a process was executed but because it subsequently exhibited suspicious behaviors, the process was terminated.</span></span>
<span data-ttu-id="74c67-132">![위협이 차단된 경고 페이지](images/detstat-blocked.png)</span><span class="sxs-lookup"><span data-stu-id="74c67-132">![An alert page showing threat was blocked](images/detstat-blocked.png)</span></span>
- <span data-ttu-id="74c67-133">감지된 – 공격이 감지되고 활성 상태일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="74c67-133">Detected – An attack was detected and is possibly still active.</span></span>
<span data-ttu-id="74c67-134">![위협을 표시하는 경고 페이지가 검색되었습니다.](images/detstat-detected.png)</span><span class="sxs-lookup"><span data-stu-id="74c67-134">![An alert page showing threat was detected](images/detstat-detected.png)</span></span>




<span data-ttu-id="74c67-135">그런 다음 경고의  세부 정보 창에서 자동화된 조사 세부 정보를 검토하여 이미 수행된 작업을 보고 권장 작업에 대한 경고 설명을 읽을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="74c67-135">You can then also review the *automated investigation details* in your alert's details pane, to see which actions were already taken, as well as reading the alert's description for recommended actions.</span></span>

![경고 설명 및 자동 조사 섹션이 강조 표시된 세부 정보 창의 스니킷](images/alert-air-and-alert-description.png)

<span data-ttu-id="74c67-137">경고가 열리면 세부 정보 창에서 사용할 수 있는 기타 정보로는 MITRE 기술, 원본 및 추가 상황 세부 정보가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="74c67-137">Other information available in the details pane when the alert opens includes MITRE techniques, source, and additional contextual details.</span></span>




## <a name="review-affected-assets"></a><span data-ttu-id="74c67-138">영향을 받는 자산 검토</span><span class="sxs-lookup"><span data-stu-id="74c67-138">Review affected assets</span></span>

<span data-ttu-id="74c67-139">영향을 받는 자산 섹션에서 장치 또는 사용자 카드를 선택하면 세부 정보 창에서 장치 또는 사용자의 세부 정보로 전환됩니다.</span><span class="sxs-lookup"><span data-stu-id="74c67-139">Selecting a device or a user card in the affected assets sections will switch to the details of the device or user in the details pane.</span></span>

- <span data-ttu-id="74c67-140">**디바이스의** 경우 세부 정보 창에 도메인, 운영 체제 및 IP와 같은 장치 자체에 대한 정보가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="74c67-140">**For devices**, the details pane will display information about the device itself, like Domain, Operating System, and IP.</span></span> <span data-ttu-id="74c67-141">활성 경고 및 해당 장치에서 로그온한 사용자도 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="74c67-141">Active alerts and the logged on users on that device are also available.</span></span> <span data-ttu-id="74c67-142">장치를 차단하거나, 앱 실행을 제한하거나, 바이러스 백신 검색을 실행하여 즉각적인 조치를 취할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="74c67-142">You can take immediate action by isolating the device, restricting app execution, or running an antivirus scan.</span></span> <span data-ttu-id="74c67-143">또는 조사 패키지를 수집하거나 자동화된 조사를 시작하거나 장치 페이지로 이동하여 디바이스의 시점에서 조사할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="74c67-143">Alternatively, you could collect an investigation package, initiate an automated investigation, or go to the device page to investigate from the device's point of view.</span></span>

   ![디바이스를 선택할 때 세부 정보 창의 스니킷](images/device-page-details.png)

- <span data-ttu-id="74c67-145">**사용자의** 경우 세부 정보 창에는 사용자의 SAM 이름 및 SID와 같은 자세한 사용자 정보와 이 사용자가 수행한 로그온 유형 및 이와 관련된 모든 알림 및 인시던트가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="74c67-145">**For users**, the details pane will display detailed user information, such as the user's SAM name and SID, as well as logon types performed by this user and any alerts and incidents related to it.</span></span> <span data-ttu-id="74c67-146">사용자 페이지 *열기 를* 선택하여 해당 사용자의 시점에서 조사를 계속할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="74c67-146">You can select *Open user page* to continue the investigation from that user's point of view.</span></span>

   ![사용자가 선택된 경우 세부 정보 창의 스니킷](images/user-page-details.png)


## <a name="related-topics"></a><span data-ttu-id="74c67-148">관련 항목</span><span class="sxs-lookup"><span data-stu-id="74c67-148">Related topics</span></span>

- [<span data-ttu-id="74c67-149">인시던트 큐 보기 및 구성</span><span class="sxs-lookup"><span data-stu-id="74c67-149">View and organize the incidents queue</span></span>](view-incidents-queue.md)
- [<span data-ttu-id="74c67-150">인시던트 조사</span><span class="sxs-lookup"><span data-stu-id="74c67-150">Investigate incidents</span></span>](investigate-incidents.md)
- [<span data-ttu-id="74c67-151">인시던트 관리</span><span class="sxs-lookup"><span data-stu-id="74c67-151">Manage incidents</span></span>](manage-incidents.md)
