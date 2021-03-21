---
title: Microsoft Defender for Office 365와 SIEM 통합
f1.keywords:
- NOCSH
ms.author: deniseb
author: denisebmsft
manager: dansimp
audience: ITPro
ms.topic: overview
localization_priority: None
search.appverid:
- MET150
- MOE150
ms.assetid: eb56b69b-3170-4086-82cf-ba40a530fa1b
ms.date: 08/21/2020
ms.collection:
- M365-security-compliance
description: 조직의 SIEM 서버를 Office 365용 Microsoft Defender 및 Office 365 활동 관리 API의 관련 위협 이벤트와 통합합니다.
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 86a716499a25af2a2907d9c502d31474b27ef7bc
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/19/2021
ms.locfileid: "50916601"
---
# <a name="siem-integration-with-microsoft-defender-for-office-365"></a>Microsoft Defender for Office 365와 SIEM 통합

**적용 대상**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Office 365용 Microsoft Defender 플랜 1 및 플랜 2](office-365-atp.md)
- [Microsoft 365 Defender](../mtp/microsoft-threat-protection.md)

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


조직에서 SIEM(보안 정보 및 이벤트 관리) 서버를 사용하는 경우 Office 365용 Microsoft Defender를 SIEM 서버와 통합할 수 있습니다. [Office 365](/office/office-365-management-api/office-365-management-activity-api-reference)활동 관리 API 를 사용하여 이 통합을 설정할 수 있습니다.

SIEM 통합을 사용하면 SIEM 서버 보고서에서 Office 365용 Microsoft Defender에서 검색한 맬웨어 또는 피싱과 같은 정보를 볼 수 있습니다.

- Microsoft Defender for Office 365와 SIEM 통합의 예를 확인하면 기술 커뮤니티 [블로그: Office 365용 Defender 및 O365](https://techcommunity.microsoft.com/t5/microsoft-security-and/improve-the-effectiveness-of-your-soc-with-office-365-atp-and/ba-p/1525185)관리 API를 통해 SOC의 효율성 개선을 참조하세요.

- Office 365 관리 API에 대한 자세한 내용은 [Office 365 관리 API 개요를 참조하세요.](/office/office-365-management-api/office-365-management-apis-overview)

## <a name="how-siem-integration-works"></a>SIEM 통합의 작동 방식

Office 365 활동 관리 API는 조직의 Microsoft 365 및 Azure Active Directory 활동 로그에서 사용자, 관리자, 시스템 및 정책 작업 및 이벤트에 대한 정보를 검색합니다. 조직에 Office 365 계획 1 또는 2용 Microsoft Defender 또는 Office 365 E5가 있는 경우 [Office 365용 Microsoft Defender schema 를](/office/office-365-management-api/office-365-management-activity-api-schema#office-365-advanced-threat-protection-and-threat-investigation-and-response-schema)사용할 수 있습니다.

최근에는 [Office 365 계획 2용 Microsoft Defender의](office-365-atp.md#microsoft-defender-for-office-365-plan-1-and-plan-2) 자동화된 조사 및 응답 기능의 이벤트가 Office 365 관리 활동 API에 추가되었습니다. API에는 ID, 이름 및 상태와 같은 핵심 조사 세부 정보에 대한 데이터를 포함하는 것 외에도 조사 작업 및 엔터티에 대한 높은 수준의 정보가 포함되어 있습니다.

SIEM 서버 또는 기타 유사한 시스템은 **audit.general** 작업을 폴링하여 검색 이벤트에 액세스합니다. 자세한 내용은 Office 365 관리 API [시작을 참조합니다.](/office/office-365-management-api/get-started-with-office-365-management-apis)

## <a name="enum-auditlogrecordtype---type-edmint32"></a>Enum: AuditLogRecordType - 유형: Edm.Int32

### <a name="auditlogrecordtype"></a>AuditLogRecordType

다음 표에는 Office 365용 Microsoft Defender 이벤트와 관련된 **AuditLogRecordType** 값이 요약됩니다.

|값|멤버 이름|설명|
|---|---|---|
|28|ThreatIntelligence|Exchange Online Protection 및 Office 365용 Microsoft Defender의 피싱 및 맬웨어 이벤트|
|41|ThreatIntelligenceUrl|안전한 링크 차단 시간 및 Office 365용 Microsoft Defender의 이벤트에 대한 보호 차단|
|47|ThreatIntelligenceAtpContent|Office 365용 Microsoft Defender의 SharePoint Online, 비즈니스용 OneDrive 및 Microsoft Teams의 파일에 대한 피싱 및 맬웨어 이벤트|
|64|AirInvestigation|Office 365 계획 2용 Microsoft Defender의 조사 세부 정보 및 관련 아티팩트와 같은 자동화된 조사 및 응답 이벤트|
|

> [!IMPORTANT]
> Office 365용 Microsoft Defender와 SIEM 통합을 설정하려면 보안 및 준수 센터에 & 관리자 역할이 할당되어 있어야 합니다.
>
> Microsoft 365 환경에 대해 감사 로깅을 설정해야 합니다. 이 문제를 확인하려면 감사 로그 검색 켜기 또는 [끄기 를 참조합니다.](../../compliance/turn-audit-log-search-on-or-off.md)

## <a name="see-also"></a>참고 항목

[Office 365 위협 조사 및 응답](office-365-ti.md)

[Office 365의 자동화된 조사 및 대응(AIR)](automated-investigation-response-office.md)