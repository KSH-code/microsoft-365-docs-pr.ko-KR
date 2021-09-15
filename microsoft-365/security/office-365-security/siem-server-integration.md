---
title: SIEM 서버와 Microsoft 365 통합
f1.keywords:
- NOCSH
ms.author: deniseb
author: denisebmsft
manager: dansimp
audience: ITPro
ms.topic: article
ms.date: 11/18/2019
localization_priority: Normal
ms.collection:
- M365-security-compliance
ms.custom:
- Ent_Solutions
- SIEM
- seo-marvel-apr2020
description: 보안 클라우드 서비스 및 응용 프로그램과 SIEM(보안 정보 및 이벤트 관리) 서버 Microsoft 365 개요를 참조하세요.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 542c6a75282d32aa3b67d61f7236e82210174531
ms.sourcegitcommit: f88a0ec621e7d9bc5f376eeaf70c8a9800711f88
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/15/2021
ms.locfileid: "59353613"
---
# <a name="security-information-and-event-management-siem-server-integration-with-microsoft-365-services-and-applications"></a>보안 정보 및 이벤트 관리(SIEM) 서버와 Microsoft 365 통합

**적용 대상**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Office 365용 Microsoft Defender 플랜 1 및 플랜 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

## <a name="summary"></a>요약

조직에서 SIEM(보안 정보 및 이벤트 관리) 서버를 사용할지 또는 받을 계획입니까? 이러한 통합 방식이 Microsoft 365 Office 365. 이 문서에서는 SIEM 서버를 서비스 및 응용 프로그램과 통합하는 데 사용할 수 있는 리소스 Microsoft 365 제공합니다.

> [!TIP]
> 아직 SIEM 서버가 없는 경우 **[Sentinel을](/azure/sentinel/overview)** 사용하여 Microsoft Azure 있습니다.

## <a name="do-i-need-a-siem-server"></a>SIEM 서버가 필요한가요?

SIEM 서버가 필요한지 여부는 조직의 보안 요구 사항 및 데이터가 있는 위치 등 다양한 요인에 따라 다릅니다. Microsoft 365 SIEM 서버와 같은 추가 서버 없이도 많은 조직의 보안 요구 사항을 충족하는 다양한 보안 기능이 포함되어 있습니다. 일부 조직에는 SIEM 서버를 사용해야 하는 특별한 상황이 있습니다. 다음은 몇 가지 예입니다.

- *Fabrikam에는* 일부 콘텐츠 및 응용 프로그램이 있으며, 일부 콘텐츠와 응용 프로그램은 클라우드에 있습니다(하이브리드 클라우드 배포). 모든 콘텐츠 및 응용 프로그램에서 보안 보고서를 얻기 위해 Fabrikam은 SIEM 서버를 구현했습니다.
- *Contoso는* 특히 엄격한 보안 요구 사항이 있는 금융 서비스 조직입니다. 필요한 추가 보안 보호를 활용하기 위해 환경에 SIEM 서버를 추가했습니다.

## <a name="siem-server-integration-with-microsoft-365"></a>SIEM 서버와 Microsoft 365

SIEM 서버는 다양한 서비스 및 응용 프로그램에서 데이터를 Microsoft 365 수 있습니다. 다음 표에는 자세한 내용을 Microsoft 365 SIEM 서버 입력 및 리소스와 함께 여러 서비스 및 응용 프로그램이 나열되어 있습니다.

<br/><br/>

|Microsoft 365 서비스 또는 응용 프로그램|SIEM 서버 입력/메서드|자세한 정보를 알아볼 수 있는 리소스|
|---|---|---|
|[Office 365용 Microsoft Defender](defender-for-office-365.md)|감사 로그|[Microsoft Defender와 SIEM Office 365](siem-integration-with-office-365-ti.md)|
|[엔드포인트용 Microsoft Defender](/windows/security/threat-protection/)|Azure에서 호스트된 HTTPS 끝점 <p> REST API|[SIEM 도구로 경고 끌어오기](../defender-endpoint/configure-siem.md)|
|[Microsoft Cloud App Security](/cloud-app-security/what-is-cloud-app-security)|로그 통합|[SIEM과 Microsoft Cloud App Security](/cloud-app-security/siem)|

> [!TIP]
> [Azure Sentinel을 살펴보아야 합니다.](/azure/sentinel/overview) Azure Sentinel은 Microsoft 솔루션용 커넥터와 함께 제공합니다. 이러한 커넥터는 "첫 실행 중"으로 사용할 수 있으며 실시간 통합을 위해 제공됩니다. Azure Sentinel을 Microsoft 365 Defender 솔루션 및 Microsoft 365 서비스(Office 365 Azure AD, ID용 Microsoft Defender, Microsoft Cloud App Security 등)를 사용할 수 있습니다.

### <a name="audit-logging-must-be-turned-on"></a>감사 로깅을 설정해야 합니다.

SIEM 서버 통합을 구성하기 전에 감사 로깅이 설정되어 있는지 확인

- SharePoint, 비즈니스용 OneDrive 및 Azure Active Directory 켜기 또는 끄기 [를 참조하세요.](../../compliance/turn-audit-log-search-on-or-off.md)
- 자세한 Exchange Online 사서함 감사 [관리를 참조합니다.](../../compliance/enable-mailbox-auditing.md)

## <a name="more-resources"></a>추가 리소스

[Azure Defender에서 보안 솔루션 통합](/azure/security-center/security-center-partner-integration#exporting-data-to-a-siem)

[Microsoft Graph 보안 API 경고를 SIEM과 통합](/graph/security-integration)
