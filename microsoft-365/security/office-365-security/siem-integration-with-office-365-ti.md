---
title: Microsoft Defender와 SIEM Office 365
f1.keywords:
- NOCSH
ms.author: deniseb
author: denisebmsft
manager: dansimp
audience: ITPro
ms.topic: article
localization_priority: None
search.appverid:
- MET150
- MOE150
ms.assetid: eb56b69b-3170-4086-82cf-ba40a530fa1b
ms.date: 08/21/2020
ms.collection:
- M365-security-compliance
description: 조직의 SIEM 서버를 Office 365 관리 API의 microsoft Defender 및 관련 위협 Office 365 통합합니다.
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: ca8f86c831df16568ae569e7b21c7e0a33475948
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/25/2021
ms.locfileid: "51205177"
---
# <a name="siem-integration-with-microsoft-defender-for-office-365"></a><span data-ttu-id="4ae2d-103">Microsoft Defender와 SIEM Office 365</span><span class="sxs-lookup"><span data-stu-id="4ae2d-103">SIEM integration with Microsoft Defender for Office 365</span></span>

<span data-ttu-id="4ae2d-104">**적용 대상**</span><span class="sxs-lookup"><span data-stu-id="4ae2d-104">**Applies to**</span></span>
- [<span data-ttu-id="4ae2d-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="4ae2d-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="4ae2d-106">Office 365용 Microsoft Defender 플랜 1 및 플랜 2</span><span class="sxs-lookup"><span data-stu-id="4ae2d-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="4ae2d-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="4ae2d-107">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="4ae2d-108">조직에서 SIEM(보안 정보 및 이벤트 관리) 서버를 사용하는 경우 SSS용 Microsoft Defender를 SIEM Office 365 통합할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4ae2d-108">If your organization is using a security information and event management (SIEM) server, you can integrate Microsoft Defender for Office 365 with your SIEM server.</span></span> <span data-ttu-id="4ae2d-109">활동 관리 API 를 사용하여 이 통합을 [설정할 Office 365 있습니다.](/office/office-365-management-api/office-365-management-activity-api-reference)</span><span class="sxs-lookup"><span data-stu-id="4ae2d-109">You can set up this integration by using the [Office 365 Activity Management API](/office/office-365-management-api/office-365-management-activity-api-reference).</span></span>

<span data-ttu-id="4ae2d-110">SIEM 통합을 사용하면 SIEM 서버 보고서에서 Microsoft Defender에서 검색한 맬웨어 또는 피싱과 Office 365 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4ae2d-110">SIEM integration enables you to view information, such as malware or phish detected by Microsoft Defender for Office 365, in your SIEM server reports.</span></span>

- <span data-ttu-id="4ae2d-111">Microsoft Defender와 Microsoft Defender의 통합 예를 Office 365 Tech Community: Office 365 및 [O365 관리 API에 대한 Defender로 SOC의](https://techcommunity.microsoft.com/t5/microsoft-security-and/improve-the-effectiveness-of-your-soc-with-office-365-atp-and/ba-p/1525185)효율성 개선을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="4ae2d-111">To see an example of SIEM integration with Microsoft Defender for Office 365, see [Tech Community blog: Improve the Effectiveness of your SOC with Defender for Office 365 and the O365 Management API](https://techcommunity.microsoft.com/t5/microsoft-security-and/improve-the-effectiveness-of-your-soc-with-office-365-atp-and/ba-p/1525185).</span></span>

- <span data-ttu-id="4ae2d-112">관리 API에 대한 Office 365 자세한 내용은 Office 365 [관리 API 개요를 참조하세요.](/office/office-365-management-api/office-365-management-apis-overview)</span><span class="sxs-lookup"><span data-stu-id="4ae2d-112">To learn more about the Office 365 Management APIs, see [Office 365 Management APIs overview](/office/office-365-management-api/office-365-management-apis-overview).</span></span>

## <a name="how-siem-integration-works"></a><span data-ttu-id="4ae2d-113">SIEM 통합의 작동 방식</span><span class="sxs-lookup"><span data-stu-id="4ae2d-113">How SIEM integration works</span></span>

<span data-ttu-id="4ae2d-114">Office 365 관리 API는 조직의 사용자, 관리자, 시스템 및 정책 작업 및 이벤트에 대한 정보를 조직 Microsoft 365 Azure Active Directory 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="4ae2d-114">The Office 365 Activity Management API retrieves information about user, admin, system, and policy actions and events from your organization's Microsoft 365 and Azure Active Directory activity logs.</span></span> <span data-ttu-id="4ae2d-115">조직에 Office 365 계획 1 또는 Office 365 또는 E5용 Microsoft Defender가 Office 365 경우 Microsoft [Defender for Office 365 있습니다.](/office/office-365-management-api/office-365-management-activity-api-schema#office-365-advanced-threat-protection-and-threat-investigation-and-response-schema)</span><span class="sxs-lookup"><span data-stu-id="4ae2d-115">If your organization has Microsoft Defender for Office 365 Plan 1 or 2, or Office 365 E5, you can use the [Microsoft Defender for Office 365 schema](/office/office-365-management-api/office-365-management-activity-api-schema#office-365-advanced-threat-protection-and-threat-investigation-and-response-schema).</span></span>

<span data-ttu-id="4ae2d-116">최근에는 Microsoft [Defender for Office 365 계획 2의](defender-for-office-365.md#microsoft-defender-for-office-365-plan-1-and-plan-2) 자동화된 조사 및 응답 기능의 이벤트가 Office 365 관리 활동 API에 추가되었습니다.</span><span class="sxs-lookup"><span data-stu-id="4ae2d-116">Recently, events from automated investigation and response capabilities in [Microsoft Defender for Office 365 Plan 2](defender-for-office-365.md#microsoft-defender-for-office-365-plan-1-and-plan-2) were added to the Office 365 Management Activity API.</span></span> <span data-ttu-id="4ae2d-117">API에는 ID, 이름 및 상태와 같은 핵심 조사 세부 정보에 대한 데이터를 포함하는 것 외에도 조사 작업 및 엔터티에 대한 높은 수준의 정보가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4ae2d-117">In addition to including data about core investigation details such as ID, name and status, the API also contains high-level information about investigation actions and entities.</span></span>

<span data-ttu-id="4ae2d-118">SIEM 서버 또는 기타 유사한 시스템은 **audit.general** 작업을 폴링하여 검색 이벤트에 액세스합니다.</span><span class="sxs-lookup"><span data-stu-id="4ae2d-118">The SIEM server or other similar system polls the **audit.general** workload to access detection events.</span></span> <span data-ttu-id="4ae2d-119">자세한 내용은 관리 API [시작을 Office 365 참조합니다.](/office/office-365-management-api/get-started-with-office-365-management-apis)</span><span class="sxs-lookup"><span data-stu-id="4ae2d-119">To learn more, see [Get started with Office 365 Management APIs](/office/office-365-management-api/get-started-with-office-365-management-apis).</span></span>

## <a name="enum-auditlogrecordtype---type-edmint32"></a><span data-ttu-id="4ae2d-120">Enum: AuditLogRecordType - 유형: Edm.Int32</span><span class="sxs-lookup"><span data-stu-id="4ae2d-120">Enum: AuditLogRecordType - Type: Edm.Int32</span></span>

### <a name="auditlogrecordtype"></a><span data-ttu-id="4ae2d-121">AuditLogRecordType</span><span class="sxs-lookup"><span data-stu-id="4ae2d-121">AuditLogRecordType</span></span>

<span data-ttu-id="4ae2d-122">다음 표에는 이벤트에 대한 Microsoft Defender와 관련된 **AuditLogRecordType의** Office 365 요약되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4ae2d-122">The following table summarizes the values of **AuditLogRecordType** that are relevant for Microsoft Defender for Office 365 events:</span></span>

|<span data-ttu-id="4ae2d-123">값</span><span class="sxs-lookup"><span data-stu-id="4ae2d-123">Value</span></span>|<span data-ttu-id="4ae2d-124">멤버 이름</span><span class="sxs-lookup"><span data-stu-id="4ae2d-124">Member name</span></span>|<span data-ttu-id="4ae2d-125">설명</span><span class="sxs-lookup"><span data-stu-id="4ae2d-125">Description</span></span>|
|---|---|---|
|<span data-ttu-id="4ae2d-126">28</span><span class="sxs-lookup"><span data-stu-id="4ae2d-126">28</span></span>|<span data-ttu-id="4ae2d-127">ThreatIntelligence</span><span class="sxs-lookup"><span data-stu-id="4ae2d-127">ThreatIntelligence</span></span>|<span data-ttu-id="4ae2d-128">Exchange Online Protection 및 Microsoft Defender for Office 365.</span><span class="sxs-lookup"><span data-stu-id="4ae2d-128">Phishing and malware events from Exchange Online Protection and Microsoft Defender for Office 365.</span></span>|
|<span data-ttu-id="4ae2d-129">41</span><span class="sxs-lookup"><span data-stu-id="4ae2d-129">41</span></span>|<span data-ttu-id="4ae2d-130">ThreatIntelligenceUrl</span><span class="sxs-lookup"><span data-stu-id="4ae2d-130">ThreatIntelligenceUrl</span></span>|<span data-ttu-id="4ae2d-131">안전한 링크 차단 및 차단은 Microsoft Defender의 이벤트 Office 365.</span><span class="sxs-lookup"><span data-stu-id="4ae2d-131">Safe Links time-of-block and block override events from Microsoft Defender for Office 365.</span></span>|
|<span data-ttu-id="4ae2d-132">47</span><span class="sxs-lookup"><span data-stu-id="4ae2d-132">47</span></span>|<span data-ttu-id="4ae2d-133">ThreatIntelligenceAtpContent</span><span class="sxs-lookup"><span data-stu-id="4ae2d-133">ThreatIntelligenceAtpContent</span></span>|<span data-ttu-id="4ae2d-134">microsoft Defender for SharePoint Online, 비즈니스용 OneDrive 및 Microsoft Teams 파일에 대한 피싱 및 맬웨어 Office 365.</span><span class="sxs-lookup"><span data-stu-id="4ae2d-134">Phishing and malware events for files in SharePoint Online, OneDrive for Business, and Microsoft Teams, from Microsoft Defender for Office 365.</span></span>|
|<span data-ttu-id="4ae2d-135">64</span><span class="sxs-lookup"><span data-stu-id="4ae2d-135">64</span></span>|<span data-ttu-id="4ae2d-136">AirInvestigation</span><span class="sxs-lookup"><span data-stu-id="4ae2d-136">AirInvestigation</span></span>|<span data-ttu-id="4ae2d-137">Microsoft Defender for Office 365 계획 2의 조사 세부 정보 및 관련 아티팩트와 같은 자동화된 조사 Office 365 이벤트입니다.</span><span class="sxs-lookup"><span data-stu-id="4ae2d-137">Automated investigation and response events, such as investigation details and relevant artifacts, from Microsoft Defender for Office 365 Plan 2.</span></span>|
|

> [!IMPORTANT]
> <span data-ttu-id="4ae2d-138">Microsoft Defender와의 SIEM 통합을 설정하려면 전역 관리자 또는 보안 및 준수 센터에 & 관리자 역할이 할당되어 있어야 Office 365.</span><span class="sxs-lookup"><span data-stu-id="4ae2d-138">You must be a global administrator or have the security administrator role assigned for the Security & Compliance Center to set up SIEM integration with Microsoft Defender for Office 365.</span></span>
>
> <span data-ttu-id="4ae2d-139">사용자 환경에 대해 감사 로깅을 설정해야 Microsoft 365 합니다.</span><span class="sxs-lookup"><span data-stu-id="4ae2d-139">Audit logging must be turned on for your Microsoft 365 environment.</span></span> <span data-ttu-id="4ae2d-140">이 문제를 확인하려면 감사 로그 검색 켜기 또는 [끄기 를 참조합니다.](../../compliance/turn-audit-log-search-on-or-off.md)</span><span class="sxs-lookup"><span data-stu-id="4ae2d-140">To get help with this, see [Turn audit log search on or off](../../compliance/turn-audit-log-search-on-or-off.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="4ae2d-141">참고 항목</span><span class="sxs-lookup"><span data-stu-id="4ae2d-141">See also</span></span>

[<span data-ttu-id="4ae2d-142">Office 365 위협 조사 및 응답</span><span class="sxs-lookup"><span data-stu-id="4ae2d-142">Office 365 threat investigation and response</span></span>](office-365-ti.md)

[<span data-ttu-id="4ae2d-143">자동화된 조사 및 대응(AIR)Office 365</span><span class="sxs-lookup"><span data-stu-id="4ae2d-143">Automated investigation and response (AIR) in Office 365</span></span>](automated-investigation-response-office.md)