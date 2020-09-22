---
title: 자동화 된 조사 및 응답과 함께 사용자 지정 보고 솔루션 사용
keywords: AIR, autoIR, ATP, 자동화, 조사, 대응, 재구성, 위협, 고급, 위협, 보호
f1.keywords:
- NOCSH
ms.author: deniseb
author: denisebmsft
manager: dansimp
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.collection: M365-security-compliance
description: 사용자 지정 또는 타사 보고 솔루션을 사용 하 여 자동화 된 조사 및 응답을 통합 하는 방법을 알아봅니다.
ms.openlocfilehash: 2ff0ef995fc8418c3d57895f00ea96f05b0aaa97
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/22/2020
ms.locfileid: "48195608"
---
# <a name="use-the-management-activity-api-for-custom-or-third-party-reporting-solutions"></a>사용자 지정 또는 타사 보고 솔루션에 대해 관리 활동 API 사용

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


[Office 365 Advanced Threat Protection](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp)을 사용 하 여 [자동화 된 조사에 대 한 자세한 정보](air-view-investigation-results.md)를 확인할 수 있습니다. 그러나 일부 조직에서는 사용자 지정 또는 타사 보고 솔루션을 사용 하기도 합니다. 조직에서 이러한 솔루션을 통해 자동화 된 조사에 대 한 정보를 통합 하려는 경우에는 Office 365 관리 활동 API를 사용할 수 있습니다.

다음 리소스를 사용 하 여이를 설정할 수 있습니다.

****

|리소스|설명|
|---|---|
|[Office 365 관리 Api 개요](https://docs.microsoft.com/office/office-365-management-api/office-365-management-apis-overview)|Office 365 관리 활동 API는 Microsoft 365 및 Azure Active Directory 활동 로그에서 다양 한 사용자, 관리자, 시스템 및 정책 작업과 이벤트에 대 한 정보를 제공 합니다.|
|[Office 365 관리 Api 시작 하기](https://docs.microsoft.com/office/office-365-management-api/get-started-with-office-365-management-apis)|Office 365 관리 API는 Azure AD를 사용 하 여 응용 프로그램에서 Microsoft 365 데이터에 액세스 하는 데 필요한 인증 서비스를 제공 합니다. 이 문서에서 설명 하는 단계에 따라 설정 합니다.|
|[Office 365 관리 활동 API 참조](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-reference)|Office 365 관리 활동 API를 사용 하 여 Microsoft 365 및 Azure AD 활동 로그에서 사용자, 관리자, 시스템 및 정책 작업과 이벤트에 대 한 정보를 검색할 수 있습니다. 이 문서를 읽으면 작동 방식에 대해 자세히 알아볼 수 있습니다.|
|[Office 365 관리 활동 API 스키마](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-schema)|Office 365 관리 활동 API를 통해 사용할 수 있는 특정 종류의 데이터에 대 한 자세한 내용은 [일반 스키마](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-schema#common-schema) 및 [Office 365 ATP 및 위협 조사 및 응답 스키마](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-schema#office-365-advanced-threat-protection-and-threat-investigation-and-response-schema) 개요를 확인 하세요.|
|

## <a name="related-articles"></a>관련 문서

- [Office 365 Advanced Threat Protection](office-365-atp.md)

- [Microsoft Threat Protection의 자동화 된 조사 및 응답에 대해 자세히 알아보기](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-autoir)
