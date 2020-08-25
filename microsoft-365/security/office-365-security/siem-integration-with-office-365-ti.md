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
# <a name="siem-integration-with-advanced-threat-protection"></a>고급 위협 방지와 SIEM 통합

조직에서 SIEM(보안 인시던트 및 이벤트 관리) 서버를 사용하는 경우 Office 365 ATP(Advanced Threat Protection)를 SIEM 서버와 통합할 수 있습니다. Office 365 활동 관리 [API를 사용하여 이 통합을 설정할 수 있습니다.](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-reference) 

SIEM 통합을 사용하면 SIEM 서버 보고서에서 Office 365 ATP에서 감지한 맬웨어 또는 피싱과 같은 정보를 볼 수 있습니다. 

- Office 365 ATP와 SIEM을 통합하는 예제를 보려면 기술 [커뮤니티 블로그를 참조하세요. Office 365 ATP 및 O365 관리 API를 사용하여 SOC의 효과를 개선하세요.](https://techcommunity.microsoft.com/t5/microsoft-security-and/improve-the-effectiveness-of-your-soc-with-office-365-atp-and/ba-p/1525185)

- Office 365 관리 API에 대한 자세한 내용은 [Office 365 관리 API 개요를 참조하세요.](https://docs.microsoft.com/office/office-365-management-api/office-365-management-apis-overview)

## <a name="how-siem-integration-works"></a>SIEM 통합 작동 방식

Office 365 활동 관리 API는 조직의 Microsoft 365 및 Azure Active Directory 활동 로그에서 사용자, 관리자, 시스템, 정책 작업 및 이벤트에 대한 정보를 검색합니다. 조직에 Office 365 ATP 플랜 1 또는 2 또는 Office 365 E5가 있는 경우 [Office 365 ATP 스키마를 사용할 수 있습니다.](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-schema#office-365-advanced-threat-protection-and-threat-investigation-and-response-schema)  

최근 Office 365 ATP 계획 2의 자동화된 조사 및 [대응 기능의 이벤트가](office-365-atp.md#office-365-atp-plan-1-and-plan-2) Office 365 관리 작업 API에 추가되었습니다. 이 API에는 ID, 이름 및 상태와 같은 핵심 조사 세부 정보가 포함된 뿐만 항목 및 기관에 대한 고급 정보도 포함됩니다.

SIEM 서버 또는 기타 유사한 시스템은 **audit.general 작업을 폴링하여** 감지 이벤트에 액세스합니다. 자세한 내용은 [Office 365 관리 API 시작을 참조하세요.](https://docs.microsoft.com/office/office-365-management-api/get-started-with-office-365-management-apis) 


## <a name="enum-auditlogrecordtype---type-edmint32"></a>Enum: AuditLogRecordType - Type: Edm.Int32

### <a name="auditlogrecordtype"></a>AuditLogRecordType

다음 표에서는 Office 365 ATP **이벤트와 관련된 AuditLogRecordType의** 값을 요약합니다.

|값|멤버 이름|설명|
|---|---|---|
|28|ThreatIntelligence|Exchange Online Protection 및 Office 365 ATP의 피싱 및 맬웨어 이벤트|
|41|ThreatIntelligenceUrl|ATP 안전한 링크 시간 차단 및 Office 365 ATP의 재정의 이벤트를 재정의하지 못하도록 차단합니다.|
|47|ThreatIntelligenceAtpContent|Office 365 ATP의 SharePoint 온라인, 비즈니스용 OneDrive 및 Microsoft Teams의 파일에 대한 피싱 및 맬웨어 이벤트입니다.|
|64|AirInvestigation|Office 365 ATP 계획 2에서 조사 세부 정보 및 관련 아티팩트와 같은 자동화된 조사 및 대응 이벤트.|
|

> [!IMPORTANT]
> Office 365 Advanced Threat Protection과 SIEM통합을 설정하려면 보안 & 준수 센터에 대해 전역 관리자 또는 보안 관리자 역할을 할당해야 합니다.<br/>감사 로깅이 Microsoft 365 환경에 대해 켜져 있는 것이 좋습니다. 이에 대한 도와지를 확인하려면 [감사 로그 검색 켜기 또는 끄기를 참조하세요.](../../compliance/turn-audit-log-search-on-or-off.md)

## <a name="see-also"></a>참고 항목

[Office 365 위협 조사 및 응답](office-365-ti.md)

[Office 365의 자동화된 조사 및 대응(AIR)](automated-investigation-response-office.md)


