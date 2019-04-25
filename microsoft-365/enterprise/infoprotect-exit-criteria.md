---
title: 정보 보호 인프라 종료 조건
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 04/10/2019
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-security-compliance
- Strat_O365_Enterprise
ms.custom: ''
description: 정보 보호 기반 서비스 및 인프라에 대한 조건을 검사하여 구성이 Microsoft 365 Enterprise 요구 사항을 충족하는지 확인합니다.
ms.openlocfilehash: 681b3bb2500680b4f5d5801486347aec1b801714
ms.sourcegitcommit: 81273a9df49647286235b187fa2213c5ec7e8b62
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "32283702"
---
# <a name="information-protection-infrastructure-exit-criteria"></a>정보 보호 인프라 종료 조건

![](./media/deploy-foundation-infrastructure/infoprotection_icon-small.png)

정보 보호 인프라를 다음과 같은 필수 조건 및 선택 요소에 확실히 충족하도록 하십시오.

<a name="crit-infoprotect-step1"></a>
## <a name="required-security-and-information-protection-levels-for-your-organization-are-defined"></a>필수: 조직의 보안 및 정보 보호 수준 정의

조직에 필요한 보안 수준을 계획하고 결정해야 합니다. 이러한 수준은 최소 보안 수준과 함께 점점 중요해지는 정보 및 이에 필요한 데이터 보안에 대한 추가 수준을 정의합니다.

최소한 다음 세 가지 보안 수준을 사용합니다.

- 기준
- 중요
- 높은 규제

필요한 경우 [1단계](infoprotect-define-sec-infoprotect-levels.md)를 통해 이 요구 사항을 충족할 수 있습니다. 

<a name="crit-infoprotect-step4"></a>
## <a name="required-increased-security-for-microsoft-365-is-configured"></a>필수: Microsoft 365에 대한 강화된 보안이 구성됩니다.

[Office 365 보안 강화](https://docs.microsoft.com/office365/securitycompliance/tenant-wide-setup-for-increased-security)를 위해 다음과 같은 설정을 구성했습니다.

- Microsoft 365 보안 센터의 위협 관리 정책
- 추가 Exchange Online 테넌트 수준 설정
- SharePoint 관리 센터의 테넌트 수준 공유 정책
- Azure Active Directory(Azure AD)의 설정

또한 [SharePoint, OneDrive 및 Microsoft Teams를 위해 Office 365 ATP(Advanced Threat Protection)를 사용하도록 설정](https://docs.microsoft.com/ko-KR/office365/securitycompliance/turn-on-atp-for-spo-odb-and-teams)했습니다.

필요한 경우 [3단계](infoprotect-configure-increased-security-office-365.md)를 통해 이 요구 사항을 충족할 수 있습니다. 

<a name="crit-infoprotect-step3"></a>
## <a name="optional-classification-is-configured-across-your-environment"></a>선택: 전체 사용자 환경에서 분류 구성

법률 및 준수 팀과 함께 조직의 데이터 거버넌스 및 보안 정책을 위한 적합한 분류 및 레이블 지정 체계를 개발하기 위해 작업하였습니다. 

해당 정책은 다음과 같은 구성 및 배포에 해당합니다.

- 중요한 데이터 유형
- 보존 레이블
- 민감도 레이블
- Azure Information Protection 레이블

필요한 경우 [2단계](infoprotect-configure-classification.md)를 통해 이 요구 사항을 충족할 수 있습니다. 

<a name="crit-infoprotect-step5"></a>
## <a name="optional-configure-privileged-access-management-in-office-365"></a>선택 사항: Office 365의 권한이 부여된 액세스 관리 구성

권한이 부여된 액세스를 사용하고 조직에서 하나 이상의 권한이 부여된 액세스 정책을 만들어내기 위해 [Office 365에서 권한이 부여된 액세스 관리 구성](https://docs.microsoft.com/office365/securitycompliance/privileged-access-management-configuration)의 정보를 사용하였습니다. 이러한 정책을 구성하고 중요한 데이터에 대한 액세스 또는 중요한 구성 설정에 대한 액세스를 위해 적기에 맞는 액세스가 활성화됩니다.

필요한 경우 [4단계](infoprotect-configure-privileged-access-management.md)를 통해 이 요구 사항을 충족할 수 있습니다. 

## <a name="results-and-next-steps"></a>결과 및 다음 단계

Microsoft 365 Enterprise에 대한 정보 보호 인프라에서는 정의된 보안 수준, Office 365를 위한 강화된 보안, 중요한 데이터 형식 및 레이블을 사용하는 분류 및 권한이 부여된 액세스 관리를 사용합니다.

Microsoft 365 Enterprise의 종단 간 배포를 따른다면 [워크 로드 및 시나리오](deploy-workloads.md)가 모든 기능 및 기초 인프라의 구성을 이용하도록 해줄 것입니다.
