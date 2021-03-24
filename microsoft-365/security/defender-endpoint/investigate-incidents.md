---
title: Microsoft Defender ATP에서 인시던트 조사
description: 관련 경고를 보고, 인시던트 관리하고, 인시던트 조사에 도움이 되는 경고 메타데이터를 참조
keywords: 조사, 인시던트, 경고, 메타데이터, 위험, 검색 원본, 영향을 받는 장치, 패턴, 상관 관계
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 6f8986b3cb6b6fd846febefe8a64ab4099348f5b
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51072356"
---
# <a name="investigate-incidents-in-microsoft-defender-for-endpoint"></a><span data-ttu-id="72ef4-104">끝점용 Microsoft Defender에서 인시던트 조사</span><span class="sxs-lookup"><span data-stu-id="72ef4-104">Investigate incidents in Microsoft Defender for Endpoint</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="72ef4-105">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="72ef4-105">**Applies to:**</span></span>
- [<span data-ttu-id="72ef4-106">엔드포인트용 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="72ef4-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2146631)
- [<span data-ttu-id="72ef4-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="72ef4-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)


<span data-ttu-id="72ef4-108">네트워크에 영향을 주는 인시던트 조사, 그 의미를 파악하고 증거를 수집하여 해결합니다.</span><span class="sxs-lookup"><span data-stu-id="72ef4-108">Investigate incidents that affect your network, understand what they mean, and collate evidence to resolve them.</span></span> 

<span data-ttu-id="72ef4-109">인시던트는 조사할 때 다음을 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="72ef4-109">When you investigate an incident, you'll see:</span></span>
- <span data-ttu-id="72ef4-110">사건 세부 정보</span><span class="sxs-lookup"><span data-stu-id="72ef4-110">Incident details</span></span>
- <span data-ttu-id="72ef4-111">인시던트 설명 및 작업</span><span class="sxs-lookup"><span data-stu-id="72ef4-111">Incident comments and actions</span></span>
- <span data-ttu-id="72ef4-112">탭(경고, 장치, 조사, 증거, 그래프)</span><span class="sxs-lookup"><span data-stu-id="72ef4-112">Tabs (alerts, devices, investigations, evidence, graph)</span></span>

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RE4qLUV]


## <a name="analyze-incident-details"></a><span data-ttu-id="72ef4-113">인시던트 세부 정보 분석</span><span class="sxs-lookup"><span data-stu-id="72ef4-113">Analyze incident details</span></span> 
<span data-ttu-id="72ef4-114">인시던트 를 클릭하여 인시던트 **창을 봐야 합니다.**</span><span class="sxs-lookup"><span data-stu-id="72ef4-114">Click an incident to see the **Incident pane**.</span></span> <span data-ttu-id="72ef4-115">**인시던트 페이지** 열기 를 선택하여 인시던트 세부 정보 및 관련 정보(경고, 장치, 조사, 증거, 그래프)를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="72ef4-115">Select **Open incident page** to see the incident details and related information (alerts, devices, investigations, evidence, graph).</span></span> 

![인시던트 세부 정보의 이미지1](images/atp-incident-details.png)

### <a name="alerts"></a><span data-ttu-id="72ef4-117">경고</span><span class="sxs-lookup"><span data-stu-id="72ef4-117">Alerts</span></span>
<span data-ttu-id="72ef4-118">경고를 조사하고 경고가 인시던트에서 함께 연결된 방법을 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="72ef4-118">You can investigate the alerts and see how they were linked together in an incident.</span></span> <span data-ttu-id="72ef4-119">경고는 다음과 같은 이유로 인시던트로 그룹화됩니다.</span><span class="sxs-lookup"><span data-stu-id="72ef4-119">Alerts are grouped into incidents based on the following reasons:</span></span>
- <span data-ttu-id="72ef4-120">자동화된 조사 - 자동화된 조사가 원래 경고를 조사하는 동안 연결된 경고를 트리거했습니다.</span><span class="sxs-lookup"><span data-stu-id="72ef4-120">Automated investigation - The automated investigation triggered the linked alert while investigating the original alert</span></span> 
- <span data-ttu-id="72ef4-121">파일 특성 - 경고와 관련된 파일에는 유사한 특성이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="72ef4-121">File characteristics - The files associated with the alert have similar characteristics</span></span>
- <span data-ttu-id="72ef4-122">수동 연결 - 사용자가 수동으로 경고를 연결했습니다.</span><span class="sxs-lookup"><span data-stu-id="72ef4-122">Manual association - A user manually linked the alerts</span></span>
- <span data-ttu-id="72ef4-123">Proximate time - 경고가 특정 기간 내에 동일한 디바이스에서 트리거된 경우</span><span class="sxs-lookup"><span data-stu-id="72ef4-123">Proximate time - The alerts were triggered on the same device within a certain timeframe</span></span>
- <span data-ttu-id="72ef4-124">동일한 파일 - 경고와 연결된 파일이 정확히 동일합니다.</span><span class="sxs-lookup"><span data-stu-id="72ef4-124">Same file - The files associated with the alert are exactly the same</span></span>
- <span data-ttu-id="72ef4-125">동일한 URL - 경고를 트리거한 URL은 정확히 동일합니다.</span><span class="sxs-lookup"><span data-stu-id="72ef4-125">Same URL - The URL that triggered the alert is exactly the same</span></span>

![인시던트에서 경고가 함께 연결된 이유를 보여주는 인시던트 세부 정보 페이지가 있는 경고 탭의 이미지](images/atp-incidents-alerts-reason.png)

<span data-ttu-id="72ef4-127">경고를 관리하고 다른 정보와 함께 경고 메타데이터를 볼 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="72ef4-127">You can also manage an alert and see alert metadata along with other information.</span></span> <span data-ttu-id="72ef4-128">자세한 내용은 [경고 조사를 참조하세요.](investigate-alerts.md)</span><span class="sxs-lookup"><span data-stu-id="72ef4-128">For more information, see [Investigate alerts](investigate-alerts.md).</span></span> 

### <a name="devices"></a><span data-ttu-id="72ef4-129">디바이스</span><span class="sxs-lookup"><span data-stu-id="72ef4-129">Devices</span></span>
<span data-ttu-id="72ef4-130">또한 특정 인시던트의 일부 또는 관련 장치를 조사할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="72ef4-130">You can also investigate the devices that are part of, or related to, a given incident.</span></span> <span data-ttu-id="72ef4-131">자세한 내용은 [장치 조사를 참조하세요.](investigate-machines.md)</span><span class="sxs-lookup"><span data-stu-id="72ef4-131">For more information, see [Investigate devices](investigate-machines.md).</span></span>

![인시던트 세부 정보 페이지의 장치 탭 이미지](images/atp-incident-device-tab.png)

### <a name="investigations"></a><span data-ttu-id="72ef4-133">조사</span><span class="sxs-lookup"><span data-stu-id="72ef4-133">Investigations</span></span>
<span data-ttu-id="72ef4-134">조사를 **선택하여** 인시던트 경고에 대한 응답으로 시스템에서 시작된 모든 자동 조사를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="72ef4-134">Select **Investigations** to see all the automatic investigations launched by the system in response to the incident alerts.</span></span>

![인시던트 세부 정보 페이지의 조사 탭 이미지](images/atp-incident-investigations-tab.png)

## <a name="going-through-the-evidence"></a><span data-ttu-id="72ef4-136">증거 진행</span><span class="sxs-lookup"><span data-stu-id="72ef4-136">Going through the evidence</span></span>
<span data-ttu-id="72ef4-137">Microsoft Defender for Endpoint는 경고에서 지원되는 모든 인시던트의 지원 이벤트 및 의심스러운 엔터티를 자동으로 조사하여 중요한 파일, 프로세스, 서비스 등에 대한 자동 대응 및 정보를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="72ef4-137">Microsoft Defender for Endpoint automatically investigates all the incidents' supported events and suspicious entities in the alerts, providing you with autoresponse and information about the important files, processes, services, and more.</span></span> 

<span data-ttu-id="72ef4-138">분석된 각 엔터티는 감염, 수정 또는 의심스러운 것으로 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="72ef4-138">Each of the analyzed entities will be marked as infected, remediated, or suspicious.</span></span> 

![인시던트 세부 정보 페이지의 증거 탭 이미지](images/atp-incident-evidence-tab.png)

## <a name="visualizing-associated-cybersecurity-threats"></a><span data-ttu-id="72ef4-140">관련 사이버 보안 위협 시각화</span><span class="sxs-lookup"><span data-stu-id="72ef4-140">Visualizing associated cybersecurity threats</span></span> 
<span data-ttu-id="72ef4-141">끝점용 Microsoft Defender는 위협 정보를 인시던트로 집계하여 다양한 데이터 요소에서 들어오는 패턴 및 상관 관계도 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="72ef4-141">Microsoft Defender for Endpoint aggregates the threat information into an incident so you can see the patterns and correlations coming in from various data points.</span></span> <span data-ttu-id="72ef4-142">인시던트 그래프를 통해 이러한 상관 관계는 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="72ef4-142">You can view such correlation through the incident graph.</span></span>

### <a name="incident-graph"></a><span data-ttu-id="72ef4-143">인시던트 그래프</span><span class="sxs-lookup"><span data-stu-id="72ef4-143">Incident graph</span></span>
<span data-ttu-id="72ef4-144">**Graph는** 사이버 보안 공격에 대한 스토리를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="72ef4-144">The **Graph** tells the story of the cybersecurity attack.</span></span> <span data-ttu-id="72ef4-145">예를 들어 어떤 장치가 손상되거나 활동이 관찰된 진입점인 것을 보여 주었습니다.</span><span class="sxs-lookup"><span data-stu-id="72ef4-145">For example, it shows you what was the entry point, which indicator of compromise or activity was observed on which device.</span></span> <span data-ttu-id="72ef4-146">등.</span><span class="sxs-lookup"><span data-stu-id="72ef4-146">etc.</span></span>

![인시던트 그래프의 이미지](images/atp-incident-graph-tab.png)

<span data-ttu-id="72ef4-148">인시던트 그래프에서 원을 클릭하여 악성 파일, 관련 파일 검색, 전 세계 인스턴스 수, 조직에서 해당 인스턴스가 관찰된 경우 인스턴스 수를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="72ef4-148">You can click the circles on the incident graph to view the details of the malicious files, associated file detections, how many instances have there been worldwide, whether it’s been observed in your organization, if so, how many instances.</span></span>

![인시던트 세부 정보 이미지](images/atp-incident-graph-details.png)

## <a name="related-topics"></a><span data-ttu-id="72ef4-150">관련 항목</span><span class="sxs-lookup"><span data-stu-id="72ef4-150">Related topics</span></span>
- [<span data-ttu-id="72ef4-151">인시던트 큐</span><span class="sxs-lookup"><span data-stu-id="72ef4-151">Incidents queue</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/view-incidents-queue)
- [<span data-ttu-id="72ef4-152">끝점용 Microsoft Defender에서 인시던트 조사</span><span class="sxs-lookup"><span data-stu-id="72ef4-152">Investigate incidents in Microsoft Defender for Endpoint</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/investigate-incidents)
- [<span data-ttu-id="72ef4-153">끝점 인시던트에 대한 Microsoft Defender 관리</span><span class="sxs-lookup"><span data-stu-id="72ef4-153">Manage Microsoft Defender for Endpoint incidents</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/manage-incidents)
