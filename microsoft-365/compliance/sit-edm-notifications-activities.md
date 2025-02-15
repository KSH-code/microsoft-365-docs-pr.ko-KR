---
title: 정확한 데이터 일치 활동에 대한 알림 만들기
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.date: ''
ms.localizationpriority: high
ms.collection:
- M365-security-compliance
search.appverid:
- MOE150
- MET150
description: 정확한 데이터 일치 활동에 대한 알림을 만드는 방법을 알아보세요.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 1033b6cd84f84db65f49f95e008e20eada63ca64
ms.sourcegitcommit: 8410a49995a084e4cc9b3f7286c8d506b7a85d79
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/11/2021
ms.locfileid: "60914599"
---
# <a name="create-notifications-for-exact-data-match-activities"></a>정확한 데이터 일치 활동에 대한 알림 만들기

[EDM(정확한 데이터 일치)을 사용하여 중요한 사용자 지정 정보 유형을 만들면](sit-learn-about-exact-data-match-based-sits.md#learn-about-exact-data-match-based-sensitive-information-types) [감사 로그](search-the-audit-log-in-security-and-compliance.md#before-you-search-the-audit-log)에 여러 활동이 생성됩니다. [New-ProtectionAlert](/powershell/module/exchange/new-protectionalert) PowerShell cmdlet를 사용하여 이러한 활동이 발생할 때 알려주는 알림을 생성합니다.

- CreateSchema
- EditSchema
- RemoveSchema
- UploadDataFailed
- UploadDataCompleted

> [!NOTE]
 EDM 활동에 대한 알림을 생성하는 기능은 World Wide 및 GCC 클라우드에서만 사용할 수 있습니다.

## <a name="pre-requisites"></a>필수 구성 요소

사용하는 계정이 다음 중 하나에 해당해야 합니다.

- 전역 관리자
- 준수 관리자
- Exchange Online 관리자

DLP 권한에 관한 자세한 내용은 [권한](data-loss-prevention-policies.md#permissions)을 참조하세요.

EDM 기반 분류가 이 구독에 포함되어 있습니다.

- Office 365 E5
- Microsoft 365 E5
- Microsoft 365 E5 Compliance
- Microsoft E5/A5 Information Protection 및 거버넌스

DLP 라이선싱에 대한 자세한 내용은 [보안 & 준수에 대한 Microsoft 365 라이선스 지침](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#information-protection)을 참조하세요.

## <a name="configure-notifications-for-edm-activities"></a>EDM 활동에 대한 알림 구성

1. [보안 및 준수 센터 PowerShell](/powershell/exchange/connect-to-scc-powershell)에 연결합니다.

2. 알림을 생성하려는 작업을 사용하여 `New-ProtectionAlert`cmdlet을 실행합니다.  예를 들어 **UploadDataCompleted** 작업이 발생했을 때 알림을 받으려면 를 다음을 실행하세요.

    ```powershell
    New-ProtectionAlert -Name "EdmUploadCompleteAlertPolicy" -Category Others -NotifyUser <address to send notification to> -ThreatType Activity -Operation UploadDataCompleted -Description "Custom alert policy to track when EDM upload Completed" -AggregationType None
    ```
    
    **UploadDataFailed** 의 경우 다음을 실행할 수 있습니다.
    
    ```powershell
    New-ProtectionAlert -Name "EdmUploadFailAlertPolicy" -Category Others -NotifyUser <SMTP address to send notification to> -ThreatType Activity -Operation UploadDataFailed -Description "Custom alert policy to track when EDM upload Failed" -AggregationType None -Severity High
    ```

## <a name="related-articles"></a>관련 문서

- [정확한 데이터 일치 기반 중요한 정보 유형에 대해 자세히 알아보기](sit-learn-about-exact-data-match-based-sits.md#learn-about-exact-data-match-based-sensitive-information-types)
- [New-ProtectionAlert](/powershell/module/exchange/new-protectionalert)