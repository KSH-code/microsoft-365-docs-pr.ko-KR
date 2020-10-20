---
title: Advanced Threat Protection과의 SIEM 통합
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
description: Office 365 활동 관리 API에서 조직의 SIEM server를 Office 365 Advanced Threat Protection 및 관련 위협 이벤트와 통합 합니다.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: c4c92fc45546d3d8022a3925baa9c10f9bd0090b
ms.sourcegitcommit: 153f413402f93b79be421741f3b9fed318d6d270
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/20/2020
ms.locfileid: "48600556"
---
# <a name="siem-integration-with-advanced-threat-protection"></a><span data-ttu-id="36909-103">Advanced Threat Protection과의 SIEM 통합</span><span class="sxs-lookup"><span data-stu-id="36909-103">SIEM integration with Advanced Threat Protection</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="36909-104">조직에서 SIEM (보안 정보 및 이벤트 관리) 서버를 사용 하는 경우 Office 365 Advanced Threat Protection (Office 365 ATP)을 SIEM 서버와 통합할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="36909-104">If your organization is using a security information and event management (SIEM) server, you can integrate Office 365 Advanced Threat Protection (Office 365 ATP) with your SIEM server.</span></span> <span data-ttu-id="36909-105">[Office 365 활동 관리 API](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-reference)를 사용 하 여이 통합을 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="36909-105">You can set up this integration by using the [Office 365 Activity Management API](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-reference).</span></span> 

<span data-ttu-id="36909-106">SIEM 통합을 사용 하면 SIEM server reports에서 Office 365 ATP가 검색 한 맬웨어 또는 피싱 같은 정보를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="36909-106">SIEM integration enables you to view information, such as malware or phish detected by Office 365 ATP, in your SIEM server reports.</span></span> 

- <span data-ttu-id="36909-107">Office 365 ATP와의 SIEM 통합에 대 한 예를 보려면 [기술 커뮤니티 블로그: office 365 ATP 및 O365 관리 API를 사용 하 여 SOC의 효율성 향상](https://techcommunity.microsoft.com/t5/microsoft-security-and/improve-the-effectiveness-of-your-soc-with-office-365-atp-and/ba-p/1525185)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="36909-107">To see an example of SIEM integration with Office 365 ATP, see [Tech Community blog: Improve the Effectiveness of your SOC with Office 365 ATP and the O365 Management API](https://techcommunity.microsoft.com/t5/microsoft-security-and/improve-the-effectiveness-of-your-soc-with-office-365-atp-and/ba-p/1525185).</span></span>

- <span data-ttu-id="36909-108">Office 365 관리 Api에 대 한 자세한 내용은 [office 365 관리 api 개요](https://docs.microsoft.com/office/office-365-management-api/office-365-management-apis-overview)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="36909-108">To learn more about the Office 365 Management APIs, see [Office 365 Management APIs overview](https://docs.microsoft.com/office/office-365-management-api/office-365-management-apis-overview).</span></span>

## <a name="how-siem-integration-works"></a><span data-ttu-id="36909-109">SIEM 통합 작동 방식</span><span class="sxs-lookup"><span data-stu-id="36909-109">How SIEM integration works</span></span>

<span data-ttu-id="36909-110">Office 365 활동 관리 API는 조직의 Microsoft 365 및 Azure Active Directory 활동 로그에서 사용자, 관리자, 시스템 및 정책 작업과 이벤트에 대 한 정보를 검색 합니다.</span><span class="sxs-lookup"><span data-stu-id="36909-110">The Office 365 Activity Management API retrieves information about user, admin, system, and policy actions and events from your organization's Microsoft 365 and Azure Active Directory activity logs.</span></span> <span data-ttu-id="36909-111">조직에 Office 365 ATP 계획 1 또는 2 또는 Office 365 E5가 있는 경우 [office 365 atp 스키마](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-schema#office-365-advanced-threat-protection-and-threat-investigation-and-response-schema)를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="36909-111">If your organization has Office 365 ATP Plan 1 or 2, or Office 365 E5, you can use the [Office 365 ATP schema](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-schema#office-365-advanced-threat-protection-and-threat-investigation-and-response-schema).</span></span>  

<span data-ttu-id="36909-112">최근에 [office 365 ATP 계획 2](office-365-atp.md#office-365-atp-plan-1-and-plan-2) 의 자동화 된 조사 및 응답 기능에서 발생 한 이벤트가 Office 365 관리 활동 API에 추가 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="36909-112">Recently, events from automated investigation and response capabilities in [Office 365 ATP Plan 2](office-365-atp.md#office-365-atp-plan-1-and-plan-2) were added to the Office 365 Management Activity API.</span></span> <span data-ttu-id="36909-113">API에는 ID, 이름 및 상태와 같은 핵심 조사 세부 정보에 대 한 데이터를 포함 하는 것 외에 조사 작업과 엔터티에 대 한 높은 수준의 정보도 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="36909-113">In addition to including data about core investigation details such as ID, name and status, the API also contains high-level information about investigation actions and entities.</span></span>

<span data-ttu-id="36909-114">SIEM 서버 또는 기타 유사한 시스템은 검색 이벤트에 액세스 하기 위한 **감사의 일반적인** 작업을 폴링합니다.</span><span class="sxs-lookup"><span data-stu-id="36909-114">The SIEM server or other similar system polls the **audit.general** workload to access detection events.</span></span> <span data-ttu-id="36909-115">자세한 내용은 [Office 365 관리 api 시작](https://docs.microsoft.com/office/office-365-management-api/get-started-with-office-365-management-apis)하기를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="36909-115">To learn more, see [Get started with Office 365 Management APIs](https://docs.microsoft.com/office/office-365-management-api/get-started-with-office-365-management-apis).</span></span> 

## <a name="enum-auditlogrecordtype---type-edmint32"></a><span data-ttu-id="36909-116">Enum: AuditLogRecordType: Edm. i a i. Int32</span><span class="sxs-lookup"><span data-stu-id="36909-116">Enum: AuditLogRecordType - Type: Edm.Int32</span></span>

### <a name="auditlogrecordtype"></a><span data-ttu-id="36909-117">AuditLogRecordType</span><span class="sxs-lookup"><span data-stu-id="36909-117">AuditLogRecordType</span></span>

<span data-ttu-id="36909-118">다음 표에는 Office 365 ATP 이벤트와 관련 된 **AuditLogRecordType** 의 값이 요약 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="36909-118">The following table summarizes the values of **AuditLogRecordType** that are relevant for Office 365 ATP events:</span></span>

|<span data-ttu-id="36909-119">값</span><span class="sxs-lookup"><span data-stu-id="36909-119">Value</span></span>|<span data-ttu-id="36909-120">멤버 이름</span><span class="sxs-lookup"><span data-stu-id="36909-120">Member name</span></span>|<span data-ttu-id="36909-121">설명</span><span class="sxs-lookup"><span data-stu-id="36909-121">Description</span></span>|
|---|---|---|
|<span data-ttu-id="36909-122">28@@</span><span class="sxs-lookup"><span data-stu-id="36909-122">28</span></span>|<span data-ttu-id="36909-123">ThreatIntelligence</span><span class="sxs-lookup"><span data-stu-id="36909-123">ThreatIntelligence</span></span>|<span data-ttu-id="36909-124">Exchange Online Protection 및 Office 365 ATP의 피싱 및 맬웨어 이벤트</span><span class="sxs-lookup"><span data-stu-id="36909-124">Phishing and malware events from Exchange Online Protection and Office 365 ATP.</span></span>|
|<span data-ttu-id="36909-125">41</span><span class="sxs-lookup"><span data-stu-id="36909-125">41</span></span>|<span data-ttu-id="36909-126">ThreatIntelligenceUrl</span><span class="sxs-lookup"><span data-stu-id="36909-126">ThreatIntelligenceUrl</span></span>|<span data-ttu-id="36909-127">안전한 링크 차단 시간 및 Office 365 ATP에서 무시 되는 이벤트를 차단 합니다.</span><span class="sxs-lookup"><span data-stu-id="36909-127">Safe Links time-of-block and block override events from Office 365 ATP.</span></span>|
|<span data-ttu-id="36909-128">47</span><span class="sxs-lookup"><span data-stu-id="36909-128">47</span></span>|<span data-ttu-id="36909-129">ThreatIntelligenceAtpContent</span><span class="sxs-lookup"><span data-stu-id="36909-129">ThreatIntelligenceAtpContent</span></span>|<span data-ttu-id="36909-130">Office 365 ATP에서 SharePoint Online, 비즈니스용 OneDrive 및 Microsoft 팀의 파일에 대 한 피싱 및 맬웨어 이벤트입니다.</span><span class="sxs-lookup"><span data-stu-id="36909-130">Phishing and malware events for files in SharePoint Online, OneDrive for Business, and Microsoft Teams, from Office 365 ATP.</span></span>|
|<span data-ttu-id="36909-131">64</span><span class="sxs-lookup"><span data-stu-id="36909-131">64</span></span>|<span data-ttu-id="36909-132">방송 조사</span><span class="sxs-lookup"><span data-stu-id="36909-132">AirInvestigation</span></span>|<span data-ttu-id="36909-133">Office 365 ATP 계획 2의 조사 세부 정보 및 관련 아티팩트와 같은 자동화 된 조사 및 응답 이벤트</span><span class="sxs-lookup"><span data-stu-id="36909-133">Automated investigation and response events, such as investigation details and relevant artifacts, from Office 365 ATP Plan 2.</span></span>|
|

> [!IMPORTANT]
> <span data-ttu-id="36909-134">Office 365 Advanced Threat Protection과 함께 SIEM 통합을 설정 하려면 전역 관리자 이거나 보안 & 준수 센터에 대 한 보안 관리자 역할이 할당 되어 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="36909-134">You must be a global administrator or have the security administrator role assigned for the Security & Compliance Center to set up SIEM integration with Office 365 Advanced Threat Protection.</span></span><br/><span data-ttu-id="36909-135">Microsoft 365 환경에 대해 감사 로깅을 켜야 합니다.</span><span class="sxs-lookup"><span data-stu-id="36909-135">Audit logging must be turned on for your Microsoft 365 environment.</span></span> <span data-ttu-id="36909-136">이에 대 한 도움말을 보려면 [Turn 감사 로그 검색 켜기 또는 끄기를](../../compliance/turn-audit-log-search-on-or-off.md)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="36909-136">To get help with this, see [Turn audit log search on or off](../../compliance/turn-audit-log-search-on-or-off.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="36909-137">기타 참고 항목</span><span class="sxs-lookup"><span data-stu-id="36909-137">See also</span></span>

[<span data-ttu-id="36909-138">Office 365 위협 조사 및 응답</span><span class="sxs-lookup"><span data-stu-id="36909-138">Office 365 threat investigation and response</span></span>](office-365-ti.md)

[<span data-ttu-id="36909-139">Office 365의 자동화 된 조사 및 응답 (AIR)</span><span class="sxs-lookup"><span data-stu-id="36909-139">Automated investigation and response (AIR) in Office 365</span></span>](automated-investigation-response-office.md)

