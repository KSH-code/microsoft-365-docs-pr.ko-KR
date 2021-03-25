---
title: 끝점용 Microsoft Defender의 위협 인텔리전스 개념 이해
description: 조직에 대한 사용자 지정 위협 경고를 만들고 끝점용 Microsoft Defender의 위협 인텔리전스에 대한 개념 학습
keywords: 위협 인텔리전스, 경고 정의, 손상 표시기, ioc
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
ms.collection: M365-security-compliance
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: bb82634c8c2ef11131a43e8e479bf88d5626ed03
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51074119"
---
# <a name="understand-threat-intelligence-concepts"></a><span data-ttu-id="d5144-104">위협 인텔리전스 개념 이해</span><span class="sxs-lookup"><span data-stu-id="d5144-104">Understand threat intelligence concepts</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="d5144-105">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="d5144-105">**Applies to:**</span></span>
- [<span data-ttu-id="d5144-106">엔드포인트용 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="d5144-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)
- [<span data-ttu-id="d5144-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="d5144-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)



><span data-ttu-id="d5144-108">끝점용 Microsoft Defender를 경험하고 싶나요?</span><span class="sxs-lookup"><span data-stu-id="d5144-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="d5144-109">무료 평가판에 등록합니다.</span><span class="sxs-lookup"><span data-stu-id="d5144-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-threatindicator-abovefoldlink) 

<span data-ttu-id="d5144-110">고급 사이버 보안 공격은 여러 복잡한 악성 이벤트, 특성 및 상황 정보로 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="d5144-110">Advanced cybersecurity attacks comprise of multiple complex malicious events, attributes, and contextual information.</span></span> <span data-ttu-id="d5144-111">이러한 활동 중 의심스러운 활동의 식별 및 결정은 어려운 작업일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d5144-111">Identifying and deciding which of these activities qualify as suspicious can be a challenging task.</span></span> <span data-ttu-id="d5144-112">업계와 관련한 알려진 특성 및 비정상적 활동에 대한 지식은 관찰된 동작을 의심스러운 행동으로 부를 때를 아는 데 기본입니다.</span><span class="sxs-lookup"><span data-stu-id="d5144-112">Your knowledge of known attributes and abnormal activities specific to your industry is fundamental in knowing when to call an observed behavior as suspicious.</span></span>

<span data-ttu-id="d5144-113">끝점용 Microsoft Defender를 사용하면 조직에서 가능한 공격 활동을 추적하는 데 도움이 되는 사용자 지정 위협 알림을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d5144-113">With Microsoft Defender for Endpoint, you can create custom threat alerts that can help you keep track of possible attack activities in your organization.</span></span> <span data-ttu-id="d5144-114">의심스러운 이벤트에 플래그를 지정하여 단서를 모아 공격 체인을 중지할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d5144-114">You can flag suspicious events to piece together clues and possibly stop an attack chain.</span></span> <span data-ttu-id="d5144-115">이러한 사용자 지정 위협 경고는 조직에만 표시될 뿐 추적하기 위해 설정한 이벤트에 플래그를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="d5144-115">These custom threat alerts will only appear in your organization and will flag events that you set it to track.</span></span>

<span data-ttu-id="d5144-116">사용자 지정 위협 경고를 만들기 전에 경고 정의 및 IOC(손상 표시기) 뒤에 있는 개념과 이러한 경고 간의 관계를 알아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d5144-116">Before creating custom threat alerts, it's important to know the concepts behind alert definitions and indicators of compromise (IOCs) and the relationship between them.</span></span>

## <a name="alert-definitions"></a><span data-ttu-id="d5144-117">경고 정의</span><span class="sxs-lookup"><span data-stu-id="d5144-117">Alert definitions</span></span>
<span data-ttu-id="d5144-118">경고 정의는 가능한 사이버 보안 공격에 대한 조기 단서를 식별하는 데 총체적으로 사용할 수 있는 상황적 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="d5144-118">Alert definitions are contextual attributes that can be used collectively to identify early clues on a possible cybersecurity attack.</span></span> <span data-ttu-id="d5144-119">이러한 지표는 일반적으로 공격자가 공격의 목표를 달성하기 위해 수행한 활동, 특징 및 작업의 조합입니다.</span><span class="sxs-lookup"><span data-stu-id="d5144-119">These indicators are typically a combination of activities, characteristics, and actions taken by an attacker to successfully achieve the objective of an attack.</span></span> <span data-ttu-id="d5144-120">이러한 특성 조합을 모니터링하는 것은 공격에 대한 가시적 지점을 확보하고 공격자 목표에 도달하기 전에 이벤트 체인을 끊는 데 중요합니다.</span><span class="sxs-lookup"><span data-stu-id="d5144-120">Monitoring these combinations of attributes is critical in gaining a vantage point against attacks and possibly interfering with the chain of events before an attacker's objective is reached.</span></span>

## <a name="indicators-of-compromise-ioc"></a><span data-ttu-id="d5144-121">손상 표시기(IOC)</span><span class="sxs-lookup"><span data-stu-id="d5144-121">Indicators of compromise (IOC)</span></span>
<span data-ttu-id="d5144-122">IOC는 네트워크 또는 장치가 이미 위반된 것을 나타내는 개별적으로 알려진 악성 이벤트입니다.</span><span class="sxs-lookup"><span data-stu-id="d5144-122">IOCs are individually-known malicious events that indicate that a network or device has already been breached.</span></span> <span data-ttu-id="d5144-123">경고 정의와 달리 이러한 표시기는 위반의 증거로 간주됩니다.</span><span class="sxs-lookup"><span data-stu-id="d5144-123">Unlike alert definitions, these indicators are considered as evidence of a breach.</span></span> <span data-ttu-id="d5144-124">공격이 이미 수행되고 목표에 도달한(예: 유출) 후에 종종 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d5144-124">They are often seen after an attack has already been carried out and the objective has been reached, such as exfiltration.</span></span> <span data-ttu-id="d5144-125">IOC를 추적하는 것은 포렌식 조사 중에도 중요합니다.</span><span class="sxs-lookup"><span data-stu-id="d5144-125">Keeping track of IOCs is also important during forensic investigations.</span></span> <span data-ttu-id="d5144-126">공격 체인에 개입할 수 있는 기능을 제공하지는 못하기는 하지만 이러한 지표를 수집하면 향후의 공격에 대한 더 나은 방어를 만드는 데 유용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d5144-126">Although it might not provide the ability to intervene with an attack chain, gathering these indicators can be useful in creating better defenses for possible future attacks.</span></span>

## <a name="relationship-between-alert-definitions-and-iocs"></a><span data-ttu-id="d5144-127">경고 정의와 IOC 간의 관계</span><span class="sxs-lookup"><span data-stu-id="d5144-127">Relationship between alert definitions and IOCs</span></span>
<span data-ttu-id="d5144-128">Microsoft Defender for Endpoint의 컨텍스트에서 경고 정의는 IOC용 컨테이너로, 특정 IOC 일치 시에 발생된 메타데이터를 포함하여 경고를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="d5144-128">In the context of Microsoft Defender for Endpoint, alert definitions are containers for IOCs and defines the alert, including the metadata that is raised in case of a specific IOC match.</span></span> <span data-ttu-id="d5144-129">경고 정의의 일부로 다양한 메타데이터가 제공됩니다.</span><span class="sxs-lookup"><span data-stu-id="d5144-129">Various metadata is provided as part of the alert definitions.</span></span> <span data-ttu-id="d5144-130">공격의 경고 정의 이름, 심각도 및 설명과 같은 메타데이터가 다른 옵션과 함께 제공됩니다.</span><span class="sxs-lookup"><span data-stu-id="d5144-130">Metadata such as alert definition name of attack, severity, and description is provided along with other options.</span></span>

<span data-ttu-id="d5144-131">각 IOC는 해당 유형 및 값 및 해당 작업을 기반으로 구체적인 검색 논리를 정의하며, 해당 동작이 일치되는 방법을 결정합니다.</span><span class="sxs-lookup"><span data-stu-id="d5144-131">Each IOC defines the concrete detection logic based on its type and value as well as its action, which determines how it is matched.</span></span> <span data-ttu-id="d5144-132">검색이 끝점용 Microsoft Defender 콘솔에서 경고로 표시되는 방법을 정의하는 특정 경고 정의에 바인딩됩니다.</span><span class="sxs-lookup"><span data-stu-id="d5144-132">It is bound to a specific alert definition that defines how a detection is displayed as an alert on the Microsoft Defender for Endpoint console.</span></span>

<span data-ttu-id="d5144-133">다음은 IOC의 예입니다.</span><span class="sxs-lookup"><span data-stu-id="d5144-133">Here is an example of an IOC:</span></span>
- <span data-ttu-id="d5144-134">유형: Sha1</span><span class="sxs-lookup"><span data-stu-id="d5144-134">Type: Sha1</span></span>
- <span data-ttu-id="d5144-135">값: 92cfceb39d57d914ed8b14d0e37643de0797ae56</span><span class="sxs-lookup"><span data-stu-id="d5144-135">Value:  92cfceb39d57d914ed8b14d0e37643de0797ae56</span></span>
- <span data-ttu-id="d5144-136">동작: 같음</span><span class="sxs-lookup"><span data-stu-id="d5144-136">Action: Equals</span></span>

<span data-ttu-id="d5144-137">IOC는 경고 정의에 해당하는 여러 IOC가 될 수 있는 경고 정의와 다대일 관계를 맺습니다.</span><span class="sxs-lookup"><span data-stu-id="d5144-137">IOCs have a many-to-one relationship with alert definitions such that an alert definition can have many IOCs that correspond to it.</span></span>

## <a name="in-this-section"></a><span data-ttu-id="d5144-138">이 섹션의 내용</span><span class="sxs-lookup"><span data-stu-id="d5144-138">In this section</span></span>

<span data-ttu-id="d5144-139">항목</span><span class="sxs-lookup"><span data-stu-id="d5144-139">Topic</span></span> | <span data-ttu-id="d5144-140">설명</span><span class="sxs-lookup"><span data-stu-id="d5144-140">Description</span></span>
:---|:---
[<span data-ttu-id="d5144-141">SIEM 도구로 검색 끌어오기</span><span class="sxs-lookup"><span data-stu-id="d5144-141">Pull detections to your SIEM tools</span></span>](configure-siem.md)| <span data-ttu-id="d5144-142">검색을 끌어오는 다양한 방법에 대해 자세히 알아보습니다.</span><span class="sxs-lookup"><span data-stu-id="d5144-142">Learn about different ways to pull detections.</span></span>
[<span data-ttu-id="d5144-143">끝점용 Microsoft Defender에서 SIEM 통합 사용</span><span class="sxs-lookup"><span data-stu-id="d5144-143">Enable SIEM integration in Microsoft Defender for Endpoint</span></span>](enable-siem-integration.md)| <span data-ttu-id="d5144-144">지원되는 SIEM 도구를 구성하는  데 필요한 정보를 사용하고 생성할 수 있도록 포털의 설정 페이지에서 SIEM 통합 기능을 사용하도록 설정하는 방법을 알아보십시오.</span><span class="sxs-lookup"><span data-stu-id="d5144-144">Learn about enabling the SIEM integration feature in the **Settings** page in the portal so that you can use and generate the required information to configure supported SIEM tools.</span></span>
[<span data-ttu-id="d5144-145">끝점 검색을 위해 Microsoft Defender를 끌어오도록 Splunk 구성</span><span class="sxs-lookup"><span data-stu-id="d5144-145">Configure Splunk to pull Microsoft Defender for Endpoint detections</span></span>](configure-siem.md)| <span data-ttu-id="d5144-146">Splunk가 끝점 감지를 위해 Microsoft Defender를 끌어오기 위해 REST API 모듈식 입력 앱 및 기타 구성 설정을 설치하는 방법을 알아보습니다.</span><span class="sxs-lookup"><span data-stu-id="d5144-146">Learn about installing the REST API Modular Input App and other configuration settings to enable Splunk to pull Microsoft Defender for Endpoint detections.</span></span>
[<span data-ttu-id="d5144-147">끝점 감지를 위해 Microsoft Defender를 끌어오도록 HP ArcSight 구성</span><span class="sxs-lookup"><span data-stu-id="d5144-147">Configure HP ArcSight to pull Microsoft Defender for Endpoint detections</span></span>](configure-arcsight.md)| <span data-ttu-id="d5144-148">끝점 검색을 위해 Microsoft Defender를 끌어오도록 ArcSight를 구성하는 데 필요한 파일 및 HP ArcSight REST FlexConnector 패키지를 설치하는 방법을 자세히 알아보습니다.</span><span class="sxs-lookup"><span data-stu-id="d5144-148">Learn about installing the HP ArcSight REST FlexConnector package and the files you need to configure ArcSight to pull Microsoft Defender for Endpoint detections.</span></span>
[<span data-ttu-id="d5144-149">끝점 검색 필드용 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="d5144-149">Microsoft Defender for Endpoint Detection fields</span></span>](api-portal-mapping.md) | <span data-ttu-id="d5144-150">경고 API의 일부로 노출되는 데이터 필드와 이러한 필드가 Microsoft Defender 보안 센터에 매핑되는 방법을 이해합니다.</span><span class="sxs-lookup"><span data-stu-id="d5144-150">Understand what data fields are exposed as part of the alerts API and how they map to Microsoft Defender Security Center.</span></span>
[<span data-ttu-id="d5144-151">REST API를 사용하여 끝점 검색을 위한 Microsoft Defender 끌어오기</span><span class="sxs-lookup"><span data-stu-id="d5144-151">Pull Microsoft Defender for Endpoint detections using REST API</span></span>](pull-alerts-using-rest-api.md) | <span data-ttu-id="d5144-152">클라이언트 자격 증명 OAuth 2.0 흐름을 사용하여 REST API를 사용하여 끝점용 Microsoft Defender에서 검색을 끌어오는 방법을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d5144-152">Use the Client credentials OAuth 2.0 flow to pull detections from Microsoft Defender for Endpoint using REST API.</span></span>
[<span data-ttu-id="d5144-153">SIEM 도구 통합 문제 해결</span><span class="sxs-lookup"><span data-stu-id="d5144-153">Troubleshoot SIEM tool integration issues</span></span>](troubleshoot-siem.md) | <span data-ttu-id="d5144-154">SIEM 통합 기능을 사용할 때 발생할 수 있는 문제를 해결합니다.</span><span class="sxs-lookup"><span data-stu-id="d5144-154">Address issues you might encounter when using the SIEM integration feature.</span></span>



## <a name="related-topics"></a><span data-ttu-id="d5144-155">관련 항목</span><span class="sxs-lookup"><span data-stu-id="d5144-155">Related topics</span></span>
- [<span data-ttu-id="d5144-156">표시기 관리</span><span class="sxs-lookup"><span data-stu-id="d5144-156">Manage indicators</span></span>](manage-indicators.md)
