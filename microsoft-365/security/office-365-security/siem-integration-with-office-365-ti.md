---
title: 고급 위협 방지와 SIEM 통합
f1.keywords:
- NOCSH
ms.author: deniseb
author: denisebmsft
manager: dansimp
audience: ITPro
ms.topic: overview
ms.service: O365-seccomp
localization_priority: None
search.appverid:
- MET150
- MOE150
ms.assetid: eb56b69b-3170-4086-82cf-ba40a530fa1b
ms.date: 08/21/2020
ms.collection:
- M365-security-compliance
description: 조직의 SIEM 서버를 Office 365 Advanced Threat Protection 및 Office 365 작업 관리 API의 관련 위협 이벤트와 통합합니다.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 8e9dcf24adfb227d0c454b4f5952c879cea511f7
ms.sourcegitcommit: 37da941919036a714da42eaa039682ccbe0da670
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/23/2020
ms.locfileid: "46860692"
---
# <a name="siem-integration-with-advanced-threat-protection"></a><span data-ttu-id="cbd9c-103">고급 위협 방지와 SIEM 통합</span><span class="sxs-lookup"><span data-stu-id="cbd9c-103">SIEM integration with Advanced Threat Protection</span></span>

<span data-ttu-id="cbd9c-104">조직에서 SIEM(보안 인시던트 및 이벤트 관리) 서버를 사용하는 경우 Office 365 ATP(Advanced Threat Protection)를 SIEM 서버와 통합할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cbd9c-104">If your organization is using a security incident and event management (SIEM) server, you can integrate Office 365 Advanced Threat Protection (Office 365 ATP) with your SIEM server.</span></span> <span data-ttu-id="cbd9c-105">Office 365 활동 관리 [API를 사용하여 이 통합을 설정할 수 있습니다.](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-reference)</span><span class="sxs-lookup"><span data-stu-id="cbd9c-105">You can set up this integration by using the [Office 365 Activity Management API](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-reference).</span></span> 

<span data-ttu-id="cbd9c-106">SIEM 통합을 사용하면 SIEM 서버 보고서에서 Office 365 ATP에서 감지한 맬웨어 또는 피싱과 같은 정보를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cbd9c-106">SIEM integration enables you to view information, such as malware or phish detected by Office 365 ATP, in your SIEM server reports.</span></span> 

- <span data-ttu-id="cbd9c-107">Office 365 ATP와 SIEM을 통합하는 예제를 보려면 기술 [커뮤니티 블로그를 참조하세요. Office 365 ATP 및 O365 관리 API를 사용하여 SOC의 효과를 개선하세요.](https://techcommunity.microsoft.com/t5/microsoft-security-and/improve-the-effectiveness-of-your-soc-with-office-365-atp-and/ba-p/1525185)</span><span class="sxs-lookup"><span data-stu-id="cbd9c-107">To see an example of SIEM integration with Office 365 ATP, see [Tech Community blog: Improve the Effectiveness of your SOC with Office 365 ATP and the O365 Management API](https://techcommunity.microsoft.com/t5/microsoft-security-and/improve-the-effectiveness-of-your-soc-with-office-365-atp-and/ba-p/1525185).</span></span>

- <span data-ttu-id="cbd9c-108">Office 365 관리 API에 대한 자세한 내용은 [Office 365 관리 API 개요를 참조하세요.](https://docs.microsoft.com/office/office-365-management-api/office-365-management-apis-overview)</span><span class="sxs-lookup"><span data-stu-id="cbd9c-108">To learn more about the Office 365 Management APIs, see [Office 365 Management APIs overview](https://docs.microsoft.com/office/office-365-management-api/office-365-management-apis-overview).</span></span>

## <a name="how-siem-integration-works"></a><span data-ttu-id="cbd9c-109">SIEM 통합 작동 방식</span><span class="sxs-lookup"><span data-stu-id="cbd9c-109">How SIEM integration works</span></span>

<span data-ttu-id="cbd9c-110">Office 365 활동 관리 API는 조직의 Microsoft 365 및 Azure Active Directory 활동 로그에서 사용자, 관리자, 시스템, 정책 작업 및 이벤트에 대한 정보를 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="cbd9c-110">The Office 365 Activity Management API retrieves information about user, admin, system, and policy actions and events from your organization's Microsoft 365 and Azure Active Directory activity logs.</span></span> <span data-ttu-id="cbd9c-111">조직에 Office 365 ATP 플랜 1 또는 2 또는 Office 365 E5가 있는 경우 [Office 365 ATP 스키마를 사용할 수 있습니다.](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-schema#office-365-advanced-threat-protection-and-threat-investigation-and-response-schema)</span><span class="sxs-lookup"><span data-stu-id="cbd9c-111">If your organization has Office 365 ATP Plan 1 or 2, or Office 365 E5, you can use the [Office 365 ATP schema](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-schema#office-365-advanced-threat-protection-and-threat-investigation-and-response-schema).</span></span>  

<span data-ttu-id="cbd9c-112">최근 Office 365 ATP 계획 2의 자동화된 조사 및 [대응 기능의 이벤트가](office-365-atp.md#office-365-atp-plan-1-and-plan-2) Office 365 관리 작업 API에 추가되었습니다.</span><span class="sxs-lookup"><span data-stu-id="cbd9c-112">Recently, events from automated investigation and response capabilities in [Office 365 ATP Plan 2](office-365-atp.md#office-365-atp-plan-1-and-plan-2) were added to the Office 365 Management Activity API.</span></span> <span data-ttu-id="cbd9c-113">이 API에는 ID, 이름 및 상태와 같은 핵심 조사 세부 정보가 포함된 뿐만 항목 및 기관에 대한 고급 정보도 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="cbd9c-113">In addition to including data about core investigation details such as ID, name and status, the API also contains high-level information about investigation actions and entities.</span></span>

<span data-ttu-id="cbd9c-114">SIEM 서버 또는 기타 유사한 시스템은 **audit.general 작업을 폴링하여** 감지 이벤트에 액세스합니다.</span><span class="sxs-lookup"><span data-stu-id="cbd9c-114">The SIEM server or other similar system polls the **audit.general** workload to access detection events.</span></span> <span data-ttu-id="cbd9c-115">자세한 내용은 [Office 365 관리 API 시작을 참조하세요.](https://docs.microsoft.com/office/office-365-management-api/get-started-with-office-365-management-apis)</span><span class="sxs-lookup"><span data-stu-id="cbd9c-115">To learn more, see [Get started with Office 365 Management APIs](https://docs.microsoft.com/office/office-365-management-api/get-started-with-office-365-management-apis).</span></span> 


## <a name="enum-auditlogrecordtype---type-edmint32"></a><span data-ttu-id="cbd9c-116">Enum: AuditLogRecordType - Type: Edm.Int32</span><span class="sxs-lookup"><span data-stu-id="cbd9c-116">Enum: AuditLogRecordType - Type: Edm.Int32</span></span>

### <a name="auditlogrecordtype"></a><span data-ttu-id="cbd9c-117">AuditLogRecordType</span><span class="sxs-lookup"><span data-stu-id="cbd9c-117">AuditLogRecordType</span></span>

<span data-ttu-id="cbd9c-118">다음 표에서는 Office 365 ATP **이벤트와 관련된 AuditLogRecordType의** 값을 요약합니다.</span><span class="sxs-lookup"><span data-stu-id="cbd9c-118">The following table summarizes the values of **AuditLogRecordType** that are relevant for Office 365 ATP events:</span></span>

|<span data-ttu-id="cbd9c-119">값</span><span class="sxs-lookup"><span data-stu-id="cbd9c-119">Value</span></span>|<span data-ttu-id="cbd9c-120">멤버 이름</span><span class="sxs-lookup"><span data-stu-id="cbd9c-120">Member name</span></span>|<span data-ttu-id="cbd9c-121">설명</span><span class="sxs-lookup"><span data-stu-id="cbd9c-121">Description</span></span>|
|---|---|---|
|<span data-ttu-id="cbd9c-122">28</span><span class="sxs-lookup"><span data-stu-id="cbd9c-122">28</span></span>|<span data-ttu-id="cbd9c-123">ThreatIntelligence</span><span class="sxs-lookup"><span data-stu-id="cbd9c-123">ThreatIntelligence</span></span>|<span data-ttu-id="cbd9c-124">Exchange Online Protection 및 Office 365 ATP의 피싱 및 맬웨어 이벤트</span><span class="sxs-lookup"><span data-stu-id="cbd9c-124">Phishing and malware events from Exchange Online Protection and Office 365 ATP.</span></span>|
|<span data-ttu-id="cbd9c-125">41</span><span class="sxs-lookup"><span data-stu-id="cbd9c-125">41</span></span>|<span data-ttu-id="cbd9c-126">ThreatIntelligenceUrl</span><span class="sxs-lookup"><span data-stu-id="cbd9c-126">ThreatIntelligenceUrl</span></span>|<span data-ttu-id="cbd9c-127">ATP 안전한 링크 시간 차단 및 Office 365 ATP의 재정의 이벤트를 재정의하지 못하도록 차단합니다.</span><span class="sxs-lookup"><span data-stu-id="cbd9c-127">ATP Safe Links time-of-block and block override events from Office 365 ATP.</span></span>|
|<span data-ttu-id="cbd9c-128">47</span><span class="sxs-lookup"><span data-stu-id="cbd9c-128">47</span></span>|<span data-ttu-id="cbd9c-129">ThreatIntelligenceAtpContent</span><span class="sxs-lookup"><span data-stu-id="cbd9c-129">ThreatIntelligenceAtpContent</span></span>|<span data-ttu-id="cbd9c-130">Office 365 ATP의 SharePoint 온라인, 비즈니스용 OneDrive 및 Microsoft Teams의 파일에 대한 피싱 및 맬웨어 이벤트입니다.</span><span class="sxs-lookup"><span data-stu-id="cbd9c-130">Phishing and malware events for files in SharePoint Online, OneDrive for Business, and Microsoft Teams, from Office 365 ATP.</span></span>|
|<span data-ttu-id="cbd9c-131">64</span><span class="sxs-lookup"><span data-stu-id="cbd9c-131">64</span></span>|<span data-ttu-id="cbd9c-132">AirInvestigation</span><span class="sxs-lookup"><span data-stu-id="cbd9c-132">AirInvestigation</span></span>|<span data-ttu-id="cbd9c-133">Office 365 ATP 계획 2에서 조사 세부 정보 및 관련 아티팩트와 같은 자동화된 조사 및 대응 이벤트.</span><span class="sxs-lookup"><span data-stu-id="cbd9c-133">Automated investigation and response events, such as investigation details and relevant artifacts, from Office 365 ATP Plan 2.</span></span>|
|

> [!IMPORTANT]
> <span data-ttu-id="cbd9c-134">Office 365 Advanced Threat Protection과 SIEM통합을 설정하려면 보안 & 준수 센터에 대해 전역 관리자 또는 보안 관리자 역할을 할당해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="cbd9c-134">You must be a global administrator or have the security administrator role assigned for the Security & Compliance Center to set up SIEM integration with Office 365 Advanced Threat Protection.</span></span><br/><span data-ttu-id="cbd9c-135">감사 로깅이 Microsoft 365 환경에 대해 켜져 있는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="cbd9c-135">Audit logging must be turned on for your Microsoft 365 environment.</span></span> <span data-ttu-id="cbd9c-136">이에 대한 도와지를 확인하려면 [감사 로그 검색 켜기 또는 끄기를 참조하세요.](../../compliance/turn-audit-log-search-on-or-off.md)</span><span class="sxs-lookup"><span data-stu-id="cbd9c-136">To get help with this, see [Turn audit log search on or off](../../compliance/turn-audit-log-search-on-or-off.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="cbd9c-137">참고 항목</span><span class="sxs-lookup"><span data-stu-id="cbd9c-137">See also</span></span>

[<span data-ttu-id="cbd9c-138">Office 365 위협 조사 및 응답</span><span class="sxs-lookup"><span data-stu-id="cbd9c-138">Office 365 threat investigation and response</span></span>](office-365-ti.md)

[<span data-ttu-id="cbd9c-139">Office 365의 자동화된 조사 및 대응(AIR)</span><span class="sxs-lookup"><span data-stu-id="cbd9c-139">Automated investigation and response (AIR) in Office 365</span></span>](automated-investigation-response-office.md)


