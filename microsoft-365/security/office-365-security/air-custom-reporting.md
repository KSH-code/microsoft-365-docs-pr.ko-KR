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
description: 자동화된 조사 및 대응을 사용자 지정 또는 타사 보고 솔루션과 통합하는 방법을 알아보십시오.
ms.date: 01/29/2021
ms.custom:
- air
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 3d8363ada4de60d37cb0d247d8b1af74df4226d1
ms.sourcegitcommit: d739f48b991793c08522a3d5323beba27f0111b2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/08/2021
ms.locfileid: "50142978"
---
# <a name="custom-or-third-party-reporting-solutions-for-microsoft-defender-for-office-365"></a>Office 365용 Microsoft Defender에 대한 사용자 지정 또는 타사 보고 솔루션

[Office 365용 Microsoft Defender를](office-365-atp.md)사용하면 자동화된 조사에 대한 자세한 [정보를 얻을 수 있습니다.](air-view-investigation-results.md) 그러나 일부 조직에서는 사용자 지정 또는 타사 보고 솔루션도 사용하게 됩니다. 조직에서 자동화된 조사에 [](office-365-air.md) 대한 정보를 이러한 솔루션과 통합하려는 경우 Office 365 관리 활동 API를 사용할 수 있습니다.

통합을 구성하기 위한 리소스

|리소스|설명|
|:---|:---|
|[Office 365 관리 API 개요](https://docs.microsoft.com/office/office-365-management-api/office-365-management-apis-overview)|Office 365 관리 활동 API는 Microsoft 365 및 Azure Active Directory 활동 로그의 다양한 사용자, 관리자, 시스템 및 정책 작업 및 이벤트에 대한 정보를 제공합니다.|
|[Office 365 관리 API 시작](https://docs.microsoft.com/office/office-365-management-api/get-started-with-office-365-management-apis)|Office 365 관리 API는 Azure AD를 사용하여 응용 프로그램에서 Microsoft 365 데이터에 액세스할 수 있는 인증 서비스를 제공합니다. 이 문서의 단계에 따라 이 단계를 설정하세요.|
|[Office 365 관리 작업 API 참고자료](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-reference)|Office 365 관리 활동 API를 사용하여 Microsoft 365 및 Azure AD 활동 로그에서 사용자, 관리자, 시스템 및 정책 작업 및 이벤트에 대한 정보를 검색할 수 있습니다. 이 문서의 작동 방식에 대해 자세히 알아보고자 합니다.|
|[Office 365 관리 작업 API 스키마](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-schema)|Office 365용 [Common schema](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-schema#common-schema) 및 [Defender for Office 365](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-schema#office-365-advanced-threat-protection-and-threat-investigation-and-response-schema) 및 위협 조사 및 응답 계획에 대한 개요를 확인하여 Office 365 관리 활동 API를 통해 사용할 수 있는 특정 종류의 데이터에 대해 자세히 알아보습니다.|
|

## <a name="see-also"></a>참고 항목

- [Office 365용 Microsoft Defender](office-365-atp.md)
- [Microsoft 365 Defender의 자동화된 조사 및 대응](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-autoir)
