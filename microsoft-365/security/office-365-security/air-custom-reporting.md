---
title: 자동화된 조사 및 응답이 있는 사용자 지정 보고 솔루션
keywords: SIEM, API, AIR, autoIR, Endpoint용 Microsoft Defender, 자동화된 조사, 통합, 사용자 지정 보고서
f1.keywords:
- NOCSH
author: JoeDavies-MSFT
ms.author: josephd
manager: dansimp
audience: ITPro
ms.topic: article
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
description: 자동화된 조사 및 응답을 사용자 지정 또는 타사 보고 솔루션과 통합하는 방법을 알아보십시오.
ms.date: 01/29/2021
ms.custom:
- air
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 6ed752f9514f1d2c8cadeb7cbbd1d7b9311b1b5f
ms.sourcegitcommit: d08fe0282be75483608e96df4e6986d346e97180
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/12/2021
ms.locfileid: "59219902"
---
# <a name="custom-or-third-party-reporting-solutions-for-microsoft-defender-for-office-365"></a>Microsoft Defender for Office 365

Microsoft [Defender for Office 365](defender-for-office-365.md)자동화된 조사에 대한 자세한 정보를 얻을 수 [있습니다.](air-view-investigation-results.md) 그러나 일부 조직에서는 사용자 지정 또는 타사 보고 솔루션도 사용하게 됩니다. 조직에서 자동화된 조사에 [](office-365-air.md) 대한 정보를 이러한 솔루션과 통합하려는 경우 관리 활동 API를 Office 365 있습니다.

**적용 대상**
- [Office 365용 Microsoft Defender 플랜 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

Microsoft [Defender for Office 365](defender-for-office-365.md)자동화된 조사에 대한 자세한 정보를 얻을 수 [있습니다.](air-view-investigation-results.md) 그러나 일부 조직에서는 사용자 지정 또는 타사 보고 솔루션도 사용하게 됩니다. 조직에서 자동화된 조사에 대한 정보를 이러한 솔루션과 통합하려는 경우 관리 활동 API를 Office 365 있습니다.

|리소스|설명|
|:---|:---|
|[Office 365 관리 API 개요](/office/office-365-management-api/office-365-management-apis-overview)|Office 365 관리 활동 API는 여러 사용자, 관리자, 시스템 및 정책 작업 및 이벤트에 대한 정보를 Microsoft 365 Azure Active Directory 로그에 제공합니다.|
|[Office 365 API 시작](/office/office-365-management-api/get-started-with-office-365-management-apis)|Office 365 관리 API는 Azure AD를 사용하여 응용 프로그램에 대한 인증 서비스를 제공하여 Microsoft 365 합니다. 이 문서의 단계에 따라 이 단계를 설정하세요.|
|[Office 365 관리 작업 API 참고자료](/office/office-365-management-api/office-365-management-activity-api-reference)|Office 365 관리 활동 API를 사용하여 사용자, 관리자, 시스템 및 정책 작업 및 이벤트에 대한 정보를 Microsoft 365 Azure AD 활동 로그에서 검색할 수 있습니다. 이 문서의 작동 방식에 대해 자세히 알아보면 이 문서를 읽어 보아야 합니다.|
|[Office 365 관리 작업 API 스키마](/office/office-365-management-api/office-365-management-activity-api-schema)|Office 365 관리 활동 [](/office/office-365-management-api/office-365-management-activity-api-schema#common-schema) API를 통해 [](/office/office-365-management-api/office-365-management-activity-api-schema#office-365-advanced-threat-protection-and-threat-investigation-and-response-schema) 사용할 수 있는 특정 종류의 데이터에 대해 알아보는 일반적인 Office 365 및 위협 조사 및 응답 Office 365 개요를 참조하세요.|
|

## <a name="see-also"></a>참고 항목

- [Office 365용 Microsoft Defender](defender-for-office-365.md)
- [Microsoft 365 Defender의 자동 조사 및 응답](/microsoft-365/security/defender/m365d-autoir)
