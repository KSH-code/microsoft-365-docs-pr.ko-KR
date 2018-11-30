---
title: 정보 보호 인프라 종료 조건
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 03/13/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
ms.custom: ''
description: 정보 보호 기반 서비스 및 인프라에 대한 조건을 검사하여 구성이 Microsoft 365 Enterprise 요구 사항을 충족하는지 확인합니다.
ms.openlocfilehash: 10d7b3b888999b65e5faff81e9a2d32e595294cf
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/28/2018
ms.locfileid: "26870247"
---
# <a name="information-protection-infrastructure-exit-criteria"></a>정보 보호 인프라 종료 조건

![](./media/deploy-foundation-infrastructure/infoprotection_icon-small.png)

기본 인프라를 완료하기 전에 정보 보호 인프라가 이러한 조건을 충족하는지 확인합니다. 

<a name="crit-infoprotect-step1"></a>
## <a name="required-security-and-information-protection-levels-for-your-organization-are-defined"></a>필수: 조직의 보안 및 정보 보호 수준 정의

조직에 필요한 보안 수준을 계획하고 결정해야 합니다. 이러한 수준은 최소 보안 수준과 함께 점점 중요해지는 정보 및 이에 필요한 데이터 보안에 대한 추가 수준을 정의합니다.

최소한 다음 세 가지 보안 수준을 사용합니다.

- 기준
- 중요
- 높은 규제

필요한 경우 [1단계](infoprotect-define-sec-infoprotect-levels.md)를 통해 이 요구 사항을 충족할 수 있습니다. 

<a name="crit-infoprotect-step4"></a>
## <a name="required-increased-security-for-office-365-is-configured"></a>필수: Office 365에 대한 향상된 보안 구성

[향상된 보안을 위한 Office 365 테넌트 구성](https://support.office.com/article/Configure-your-Office-365-tenant-for-increased-security-8d274fe3-db51-4107-ba64-865e7155b355)의 정보를 바탕으로 향상된 보안을 위해 다음 설정을 구성해야 합니다.

- Office 365 보안 및 준수 센터의 위협 관리 정책
- 추가 Exchange Online 테넌트 수준 설정
- SharePoint 관리 센터의 테넌트 수준 공유 정책
- Azure Active Directory의 설정

또한 [Office 365 ATP(Advanced Threat Protection)를 사용하도록 설정](https://support.office.com/article/Office-365-ATP-for-SharePoint-OneDrive-and-Microsoft-Teams-26261670-db33-4c53-b125-af0662c34607#turniton)해야 합니다.

필요한 경우 [3단계](infoprotect-configure-increased-security-office-365.md)를 통해 이 요구 사항을 충족할 수 있습니다. 

<a name="crit-infoprotect-step3"></a>
## <a name="optional-classification-is-configured-across-your-environment"></a>선택: 전체 사용자 환경에서 분류 구성

법률 및 준수 팀과 함께 조직의 데이터에 대한 적절한 분류 및 레이블 지정 체계를 개발해야 합니다.

- 중요한 데이터 유형
- Office 365 레이블
- Azure Information Protection 레이블

필요한 경우 [2단계](infoprotect-configure-classification.md)를 통해 이 요구 사항을 충족할 수 있습니다. 

<a name="crit-infoprotect-step5"></a>
## <a name="optional-configure-privileged-access-management-in-office-365"></a>선택 사항: Office 365의 권한이 부여된 액세스 관리 구성

[Office 365의 권한이 부여된 액세스 관리](https://docs.microsoft.com/office365/securitycompliance/privileged-access-management-configuration) 항목의 정보를 사용하여 권한이 부여된 액세스를 사용하도록 설정하고 Office 365 조직에서 하나 이상의 권한이 부여된 액세스 정책을 만듭니다. 이러한 정책을 구성했으며 중요한 데이터 액세스 또는 중요한 구성 설정 액세스를 위해 JIT(Just-In-Time) 액세스가 사용되도록 설정되었습니다.

필요한 경우 [4단계](infoprotect-configure-privileged-access-management.md)를 통해 이 요구 사항을 충족할 수 있습니다. 

## <a name="next-step"></a>다음 단계

이제 Microsoft 365 Enterprise 기본 인프라에서 실행되는 [워크로드 및 시나리오](deploy-workloads.md)(예: Microsoft Teams 및 Exchange Online)를 배포할 준비가 되었습니다.
