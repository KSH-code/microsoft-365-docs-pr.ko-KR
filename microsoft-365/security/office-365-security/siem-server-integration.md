---
title: Microsoft 365 서비스 및 응용 프로그램과의 SIEM 서버 통합
f1.keywords:
- NOCSH
ms.author: deniseb
author: denisebmsft
manager: dansimp
audience: ITPro
ms.topic: article
ms.date: 11/18/2019
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
ms.custom:
- Ent_Solutions
- SIEM
- seo-marvel-apr2020
description: Microsoft 365 클라우드 서비스 및 응용 프로그램과의 SIEM (보안 정보 및 이벤트 관리) 서버 통합에 대 한 개요를 확인 하세요.
ms.openlocfilehash: 0e582333615d11c500b114225435903cea386ade
ms.sourcegitcommit: 815229e39a0f905d9f06717f00dc82e2a028fa7c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/03/2020
ms.locfileid: "48846403"
---
# <a name="security-information-and-event-management-siem-server-integration-with-microsoft-365-services-and-applications"></a>Microsoft 365 서비스 및 응용 프로그램과의 SIEM (보안 정보 및 이벤트 관리) 서버 통합

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


## <a name="summary"></a>요약

조직에서 SIEM (보안 정보 및 이벤트 관리) 서버를 사용 하거나 사용할 계획 입니까? Microsoft 365 또는 Office 365와 통합 되는 방식을 궁금할 것입니다. 이 문서에서는 SIEM server를 Microsoft 365 서비스 및 응용 프로그램에 통합 하는 데 사용할 수 있는 리소스 목록을 제공 합니다.

> [!TIP]
> 아직 SIEM 서버가 없고 옵션을 탐색 하는 경우 **[Microsoft Azure 센티널](https://docs.microsoft.com/azure/sentinel/overview)** 을 고려 하세요.

## <a name="do-i-need-a-siem-server"></a>SIEM 서버가 필요 합니까?

SIEM 서버가 필요한 지 여부는 조직의 보안 요구 사항 및 데이터 위치와 같은 많은 요인에 따라 달라 집니다. Microsoft 365에는 SIEM 서버와 같은 추가 서버 없이 다양 한 조직의 보안 요구 사항을 충족 하는 다양 한 보안 기능이 포함 되어 있습니다. 일부 조직에는 SIEM 서버를 사용 해야 하는 특별 한 상황이 있습니다. 그 예는 다음과 같습니다.

- *Fabrikam* 에는 온-프레미스와 일부 콘텐츠 및 응용 프로그램, 클라우드 (하이브리드 클라우드 배포)가 있습니다. 모든 콘텐츠 및 응용 프로그램에서 보안 보고서를 가져오려면 Fabrikam은 SIEM 서버를 구현 했습니다.

- *Contoso* 는 보안 요구 사항이 특별히 엄격한 금융 서비스 조직입니다. 필요한 추가 보안 보호 기능을 활용 하기 위해 해당 환경에 SIEM 서버를 추가 했습니다.

## <a name="siem-server-integration-with-microsoft-365"></a>Microsoft 365과의 SIEM 서버 통합

SIEM 서버는 다양 한 Microsoft 365 서비스 및 응용 프로그램에서 데이터를 받을 수 있습니다. 다음 표에는 몇 가지 Microsoft 365 서비스와 응용 프로그램과 SIEM 서버 입력 및 리소스가 나와 있습니다.

****

|Microsoft 365 서비스 또는 응용 프로그램|SIEM server 입력/메서드|자세한 정보를 알아볼 수 있는 리소스|
|---|---|---|
|[Microsoft Defender for Office 365](office-365-atp.md)|감사 로그|[Microsoft Defender for Office 365의 SIEM 통합](siem-integration-with-office-365-ti.md)|
|[엔드포인트용 Microsoft Defender](https://docs.microsoft.com/windows/security/threat-protection/)|Azure에서 호스트 되는 HTTPS 끝점 <br/>REST API|[SIEM 도구에 대 한 알림 가져오기](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/configure-siem)|
|[Microsoft Cloud App Security](https://docs.microsoft.com/cloud-app-security/what-is-cloud-app-security)|로그 통합|[Microsoft Cloud App Security와의 SIEM 통합](https://docs.microsoft.com/cloud-app-security/siem)|
|

> [!TIP]
> [Azure 센티널](https://docs.microsoft.com/azure/sentinel/overview)을 살펴봅니다. Azure 센티널은 Microsoft 솔루션용 커넥터와 함께 제공 됩니다. 이러한 커넥터는 "외부에서" 사용 가능 하며 실시간 통합을 제공 합니다. Microsoft 365 Defender 솔루션 및 microsoft 365 서비스 (Office 365, Azure AD, Id 용 Microsoft Defender, Microsoft Cloud App Security 등)와 함께 Azure 센티널을 사용할 수 있습니다.

### <a name="audit-logging-must-be-turned-on"></a>감사 로깅을 설정 해야 합니다.

SIEM 서버 통합을 구성 하기 전에 감사 로깅이 설정 되어 있는지 확인 합니다.

- SharePoint Online, 비즈니스용 OneDrive 및 Azure Active Directory의 경우 [보안 & 준수 센터에서 감사 로깅이 설정 됩니다](../../compliance/turn-audit-log-search-on-or-off.md).

- Exchange Online의 경우 [사서함 감사 관리](../../compliance/enable-mailbox-auditing.md)를 참조 하세요.

## <a name="more-resources"></a>추가 리소스

[Azure Defender에서 보안 솔루션 통합 *](https://docs.microsoft.com/azure/security-center/security-center-partner-integration#exporting-data-to-a-siem)

[SIEM을 사용 하 여 Microsoft Graph 보안 API 알림 통합](https://docs.microsoft.com/graph/security-integration)
