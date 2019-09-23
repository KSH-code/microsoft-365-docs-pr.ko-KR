---
title: 정보 보호 인프라 종료 조건
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 09/19/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-security-compliance
- Strat_O365_Enterprise
ms.custom: ''
description: 정보 보호 기반 서비스 및 인프라에 대한 조건을 검사하여 구성이 Microsoft 365 Enterprise 요구 사항을 충족하는지 확인합니다.
ms.openlocfilehash: 02e972a80d4b42ae66193bbbc55d0f1e63be5ba6
ms.sourcegitcommit: 63e35b846d964dde5919a08c2fe432e749e8eff6
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/19/2019
ms.locfileid: "37047241"
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

<a name="crit-infoprotect-step3"></a>
## <a name="required-increased-security-for-microsoft-365-is-configured"></a>필수: Microsoft 365에 대한 강화된 보안이 구성됩니다.

[Office 365 보안 강화](https://docs.microsoft.com/office365/securitycompliance/tenant-wide-setup-for-increased-security)를 위해 다음과 같은 설정을 구성했습니다.

- Microsoft 365 보안 센터의 위협 관리 정책
- 추가 Exchange Online 테넌트 수준 설정
- SharePoint Online 관리 센터의 테넌트 정체 공유 정책
- Azure Active Directory(Azure AD)의 설정

또한 [SharePoint, OneDrive 및 Microsoft Teams를 위해 Office 365 ATP(Advanced Threat Protection)를 사용하도록 설정](https://docs.microsoft.com/office365/securitycompliance/turn-on-atp-for-spo-odb-and-teams)했습니다.

필요한 경우 [3단계](infoprotect-configure-increased-security-office-365.md)를 통해 이 요구 사항을 충족할 수 있습니다. 

<a name="crit-infoprotect-step2"></a>
## <a name="optional-classification-is-configured-across-your-environment"></a>선택: 전체 사용자 환경에서 분류 구성

법률 및 준수 팀과 함께 조직의 데이터 거버넌스 및 보안 정책을 위한 적합한 분류 및 레이블 지정 체계를 개발하기 위해 작업하였습니다. 

해당 정책은 다음과 같은 구성 및 배포에 해당합니다.

- 중요한 데이터 유형
- 보존 레이블
- 민감도 레이블
- Azure Information Protection 레이블

필요한 경우 [2단계](infoprotect-configure-classification.md)를 통해 이 요구 사항을 충족할 수 있습니다. 


<a name="crit-infoprotect-step4"></a>
## <a name="optional-windows-information-protection-is-deployed-across-your-environment"></a>선택 사항: Windows Information Protection이 환경 전체에 배포됩니다.

등록된 Windows 10 Enterprise 장치에 다음을 정의하는 Intune 정책이 배포되고 적용됩니다.

- 보호할 앱 유형.
- 보호 수준.
- 보호를 확장하는 위치.

필요한 경우, [4단계](infoprotect-deploy-windows-information-protection.md)를 통해 이 요구 사항을 충족할 수 있습니다. 

<a name="crit-infoprotect-step5"></a>
## <a name="optional-office-365-data-loss-prevention-dlp-is-deployed"></a>선택 사항: Office 365 DLP(Data Loss Prevention)

조직이 고객과 기타 개인 데이터 유형을 보호하고 산업 및 지역 규정과 요구 사항을 준수하는 데 필요한 DLP 정책 집합(위치 및 조건과 조치과 포함된 규칙 사용)을 분석하고 테스트하며 공개했습니다.

데이터 준수 및 보안 교직원이 Office 365 보안 및 준수 대시보드를 사용하여 DLP 인시던트를 모니터링합니다.

필요한 경우 [5단계](infoprotect-data-loss-prevention.md)를 통해 이 요구 사항을 충족할 수 있습니다. 

<a name="crit-infoprotect-step6"></a>
## <a name="optional-email-encryption-is-configured"></a>선택 사항: 전자 메일 암호화가 구성되었습니다.

조직에 필요한 대로 다음 전자 메일 암호화를 구성했습니다.

|||
|:-------|:-----|
| **암호화 방법** | **전자 메일이 전송될 경우** |
| [Office 365 메시지 암호화(OME)](https://docs.microsoft.com/Office365/SecurityCompliance/ome)  | 암호화를 사용하는 조직 외부 |
| [IRM(정보 권한 관리)](https://docs.microsoft.com/office365/SecurityCompliance/information-rights-management-in-exchange-online) | 암호화 및 권한 모두 사용 |
| [S/MIME(Secure/Multipurpose Internet Mail Extensions)](https://docs.microsoft.com/Exchange/policy-and-compliance/smime) | 공개 키 암호 표준을 사용하여 암호화와 디지털 서명 모두 사용 |
|||

필요한 경우, [6단계](infoprotect-email-encryption.md)를 통해 이 요구 사항을 충족할 수 있습니다.

<a name="crit-infoprotect-step7"></a>
## <a name="optional-configure-privileged-access-management-in-office-365"></a>선택 사항: Office 365의 권한이 부여된 액세스 관리 구성

권한이 부여된 액세스를 사용하고 조직에서 하나 이상의 권한이 부여된 액세스 정책을 만들어내기 위해 [Office 365에서 권한이 부여된 액세스 관리 구성](https://docs.microsoft.com/office365/securitycompliance/privileged-access-management-configuration)의 정보를 사용하였습니다. 이러한 정책을 구성하고 중요한 데이터에 대한 액세스 또는 중요한 구성 설정에 대한 액세스를 위해 적기에 맞는 액세스가 활성화됩니다.

필요한 경우 [7단계](infoprotect-configure-privileged-access-management.md)를 통해 이 요구 사항을 충족할 수 있습니다. 

## <a name="results-and-next-steps"></a>결과 및 다음 단계

Microsoft 365 Enterprise에 대한 정보 보호 인프라에서는 정의된 보안 수준, Office 365를 위한 강화된 보안, 중요한 데이터 형식 및 레이블을 사용하는 분류, WIP(Windows Information Protection), 데이터 손실 방지, 전자 메일 암호화 및 권한이 부여된 액세스 관리를 사용합니다.

Microsoft 365 Enterprise의 종단 간 배포를 따른다면 [워크 로드 및 시나리오](deploy-workloads.md)가 모든 기능 및 기초 인프라의 구성을 이용하도록 해줄 것입니다.
