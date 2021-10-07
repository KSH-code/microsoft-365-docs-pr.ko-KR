---
title: Microsoft Defender와 SIEM Office 365
f1.keywords:
- NOCSH
ms.author: deniseb
author: denisebmsft
manager: dansimp
audience: ITPro
ms.topic: article
ms.localizationpriority: ''
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
ms.openlocfilehash: 3dbb175ba169c9bb8f4d7240d59d9886391167c3
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/06/2021
ms.locfileid: "60176358"
---
# <a name="siem-integration-with-microsoft-defender-for-office-365"></a>Microsoft Defender와 SIEM Office 365

**적용 대상**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Office 365용 Microsoft Defender 플랜 1 및 플랜 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


조직에서 SIEM(보안 정보 및 이벤트 관리) 서버를 사용하는 경우 SSS용 Microsoft Defender를 SIEM Office 365 통합할 수 있습니다. 활동 관리 API 를 사용하여 이 통합을 [설정할 Office 365 있습니다.](/office/office-365-management-api/office-365-management-activity-api-reference)

SIEM 통합을 사용하면 SIEM 서버 보고서에서 Microsoft Defender에서 검색한 맬웨어 또는 피싱과 Office 365 볼 수 있습니다.

- Microsoft Defender와 Microsoft Defender의 통합 예를 Office 365 Tech Community: Office 365 및 [O365 관리 API에 대한 Defender로 SOC의](https://techcommunity.microsoft.com/t5/microsoft-security-and/improve-the-effectiveness-of-your-soc-with-office-365-atp-and/ba-p/1525185)효율성 개선을 참조하세요.
- 관리 API에 대한 Office 365 자세한 내용은 Office 365 [관리 API 개요를 참조하세요.](/office/office-365-management-api/office-365-management-apis-overview)

## <a name="how-siem-integration-works"></a>SIEM 통합의 작동 방식

Office 365 관리 API는 조직의 사용자, 관리자, 시스템 및 정책 작업 및 이벤트에 대한 정보를 조직 Microsoft 365 Azure Active Directory 검색합니다. 조직에 Office 365 계획 1 또는 2에 대한 Microsoft Defender가 Office 365 E5 경우 Microsoft [Defender for Office 365 있습니다.](/office/office-365-management-api/office-365-management-activity-api-schema#office-365-advanced-threat-protection-and-threat-investigation-and-response-schema)

최근에는 Microsoft [Defender for Office 365 계획 2의](defender-for-office-365.md#microsoft-defender-for-office-365-plan-1-and-plan-2) 자동화된 조사 및 응답 기능의 이벤트가 Office 365 관리 활동 API에 추가되었습니다. API에는 ID, 이름 및 상태와 같은 핵심 조사 세부 정보에 대한 데이터를 포함하는 것 외에도 조사 작업 및 엔터티에 대한 높은 수준의 정보가 포함되어 있습니다.

SIEM 서버 또는 기타 유사한 시스템은 **audit.general** 작업을 폴링하여 검색 이벤트에 액세스합니다. 자세한 내용은 관리 API [시작을 Office 365 참조합니다.](/office/office-365-management-api/get-started-with-office-365-management-apis)

## <a name="enum-auditlogrecordtype---type-edmint32"></a>Enum: AuditLogRecordType - 유형: Edm.Int32

### <a name="auditlogrecordtype"></a>AuditLogRecordType

다음 표에는 이벤트에 대한 Microsoft Defender와 관련된 **AuditLogRecordType의** Office 365 요약되어 있습니다.<br/><br/>

| 값 | 멤버 이름 | 설명 |
|---|---|---|
| 28| ThreatIntelligence | Exchange Online Protection 및 Microsoft Defender for Office 365. |
| 41| ThreatIntelligenceUrl | 금고 Microsoft Defender에서 차단 시간 및 차단 이벤트를 Office 365. |
| 47| ThreatIntelligenceAtpContent | microsoft Defender for SharePoint Online, 비즈니스용 OneDrive 및 Microsoft Teams 파일에 대한 피싱 및 맬웨어 Office 365. |
| 64| AirInvestigation | Microsoft Defender for Office 365 계획 2의 조사 세부 정보 및 관련 아티팩트와 같은 자동화된 조사 Office 365 이벤트입니다. |

> [!IMPORTANT]
> microsoft Defender와 MICROSOFT Defender의 SIEM 통합을 설정하려면 Microsoft 365 Defender 포털에 전역 관리자 또는 보안 관리자 역할이 할당되어 있어야 Office 365. 자세한 내용은 [Microsoft 365 Defender 포털 권한](permissions-microsoft-365-security-center.md)을 참조하세요.
>
> 사용자 환경에 대해 감사 로깅을 설정해야 Microsoft 365 합니다. 이 문제를 확인하려면 감사 로그 검색 켜기 또는 [끄기 를 참조합니다.](../../compliance/turn-audit-log-search-on-or-off.md)

## <a name="see-also"></a>참고 항목

[Office 365 위협 조사 및 응답](office-365-ti.md)

[자동화된 조사 및 대응(AIR)Office 365](automated-investigation-response-office.md)