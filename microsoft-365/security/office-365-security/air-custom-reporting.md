---
title: 자동화된 조사 및 응답이 있는 사용자 지정 보고 솔루션
keywords: SIEM, API, AIR, autoIR, ATP, 자동화된 조사, 통합, 사용자 지정 보고서
f1.keywords:
- NOCSH
ms.author: deniseb
author: denisebmsft
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
ms.openlocfilehash: 82f3b38e5b6e31313c94f5ac389e883f6b076540
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/25/2021
ms.locfileid: "51206719"
---
# <a name="custom-or-third-party-reporting-solutions-for-microsoft-defender-for-office-365"></a>Office 365용 Microsoft Defender에 대한 사용자 지정 또는 타사 보고 솔루션

[Microsoft Defender for Office 365를](defender-for-office-365.md)사용하면 자동화된 조사에 대한 자세한 [정보를 얻을 수 있습니다.](air-view-investigation-results.md) 그러나 일부 조직에서는 사용자 지정 또는 타사 보고 솔루션도 사용하게 됩니다. 조직에서 자동화된 조사에 [](office-365-air.md) 대한 정보를 이러한 솔루션과 통합하려는 경우 Office 365 관리 활동 API를 사용할 수 있습니다.

**적용 대상**
- [Office 365용 Microsoft Defender 플랜 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

[Microsoft Defender for Office 365를](defender-for-office-365.md)사용하면 자동화된 조사에 대한 자세한 [정보를 얻을 수 있습니다.](air-view-investigation-results.md) 그러나 일부 조직에서는 사용자 지정 또는 타사 보고 솔루션도 사용하게 됩니다. 조직에서 자동화된 조사에 대한 정보를 이러한 솔루션과 통합하려는 경우 Office 365 관리 활동 API를 사용할 수 있습니다.

|리소스|설명|
|:---|:---|
|[Office 365 관리 API 개요](/office/office-365-management-api/office-365-management-apis-overview)|Office 365 관리 활동 API는 Microsoft 365 및 Azure Active Directory 활동 로그의 다양한 사용자, 관리자, 시스템 및 정책 작업 및 이벤트에 대한 정보를 제공합니다.|
|[Office 365 관리 API 시작](/office/office-365-management-api/get-started-with-office-365-management-apis)|Office 365 관리 API는 Azure AD를 사용하여 응용 프로그램이 Microsoft 365 데이터에 액세스하는 데 사용할 인증 서비스를 제공합니다. 이 문서의 단계에 따라 이 단계를 설정하세요.|
|[Office 365 관리 작업 API 참고자료](/office/office-365-management-api/office-365-management-activity-api-reference)|Office 365 관리 활동 API를 사용하여 Microsoft 365 및 Azure AD 활동 로그에서 사용자, 관리자, 시스템 및 정책 작업 및 이벤트에 대한 정보를 검색할 수 있습니다. 이 문서의 작동 방식에 대해 자세히 알아보면 이 문서를 읽어 보아야 합니다.|
|[Office 365 관리 작업 API 스키마](/office/office-365-management-api/office-365-management-activity-api-schema)|Common [schema](/office/office-365-management-api/office-365-management-activity-api-schema#common-schema) and the [Defender for Office 365 및 Threat investigation and response schema의](/office/office-365-management-api/office-365-management-activity-api-schema#office-365-advanced-threat-protection-and-threat-investigation-and-response-schema) 개요를 확인하여 Office 365 관리 활동 API를 통해 사용할 수 있는 특정 종류의 데이터에 대해 자세히 알아보습니다.|
|

## <a name="see-also"></a>참고 항목

- [Office 365용 Microsoft Defender](defender-for-office-365.md)
- [Microsoft 365 Defender의 자동화된 조사 및 대응](/microsoft-365/security/defender/m365d-autoir)
