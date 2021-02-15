---
title: 3단계. 엔터프라이즈용 Microsoft 365 테넌트의 ID
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.audience: ITPro
ms.topic: article
ms.prod: microsoft-365-enterprise
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
- m365solution-tenantmanagement
ms.custom:
- Ent_Solutions
description: Microsoft 365 테넌트에 대한 올바른 ID 모델을 배포하고 강력한 사용자 로그인을 적용합니다.
ms.openlocfilehash: 40ea67d9b30a385e36af45f57bd33906c10e495d
ms.sourcegitcommit: 99a7354e6a6b4d9d5202674ef57852d52a43fef6
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/20/2021
ms.locfileid: "49908686"
---
# <a name="step-3-identity-for-your-microsoft-365-for-enterprise-tenants"></a>3단계. 엔터프라이즈용 Microsoft 365 테넌트의 ID

Microsoft 365 테넌트에는 로그인에 대한 ID 및 인증을 관리하는 Azure AD(Azure Active Directory) 테넌트가 포함되어 있습니다. 조직에 대한 Microsoft 365 사용자 액세스 및 사용 권한을 관리하려면 ID 인프라를 올바르게 구성하는 것이 중요합니다.

## <a name="cloud-only-vs-hybrid"></a>클라우드 전용 및 하이브리드

다음은 두 가지 유형의 ID 모델과 가장 적합한 이점입니다.


| 모델 | 설명 | Microsoft 365에서 사용자 자격 증명을 인증하는 방법 | 최적 시나리오 | 가장 큰 혜택 |
|:-------|:-----|:-----|:-----|:-----|
| 클라우드 전용 | 사용자 계정은 Microsoft 365 테넌트의 Azure AD 테넌트에만 존재합니다. | Microsoft 365 테넌트의 Azure AD 테넌트는 클라우드 ID 계정으로 인증을 수행합니다. | 조직에 대한 AD DS가 필요하지 않은 조직입니다. | 간단하게 사용할 수 있습니다. 추가 디렉터리 도구 또는 서버는 필요하지 않습니다. |
| 하이브리드 |  사용자 계정은 AD DS(Active Directory 도메인 서비스)에 있으며 복사본은 Microsoft 365 테넌트의 Azure AD 테넌트에도 있습니다. Azure AD Connect는 AD DS 변경 내용을 Azure AD 테넌트와 동기화하기 위해,프레미스 서버에서 실행됩니다. Azure AD의 사용자 계정에 해시된 해시된 AD DS 사용자 계정 암호도 포함되어 있을 수 있습니다. | Microsoft 365 테넌트의 Azure AD 테넌트는 인증 프로세스를 처리하거나 사용자를 다른 ID 공급자로 리디렉션합니다. | AD DS 또는 다른 ID 공급자를 사용하는 조직 | 사용자는 On-premises 또는 클라우드 기반 리소스에 액세스할 때 동일한 자격 증명을 사용할 수 있습니다. |
||||||

다음은 클라우드 전용 ID의 기본 구성 요소입니다.
 
![클라우드 전용 ID의 기본 구성 요소](../media/about-microsoft-365-identity/cloud-only-identity.png)

이 그림에서, 프레미스 및 원격 사용자는 Microsoft 365 테넌트의 Azure AD 테넌트에 계정으로 로그인합니다.

다음은 하이브리드 ID의 기본 구성 요소입니다.

![하이브리드 ID의 기본 구성 요소](../media/about-microsoft-365-identity/hybrid-identity.png)

이 그림에서, On-premises 및 remote users sign in to their Microsoft 365 tenant with accounts in the Azure AD tenant that have been copied from their on-premises AD DS.

## <a name="synchronizing-your-on-premises-ad-ds"></a>On-premises AD DS 동기화

비즈니스 요구 사항 및 기술 요구 사항에 따라 Microsoft 365를 채택하는 엔터프라이즈 고객에게는 하이브리드 ID 모델 및 디렉터리 동기화가 가장 일반적인 선택입니다. 디렉터리 동기화를 사용하면 AD DS에서 ID를 관리할 수 있으며 사용자 계정, 그룹 및 연락처에 대한 모든 업데이트가 Microsoft 365 테넌트의 Azure AD 테넌트와 동기화됩니다.

>[!Note]
>AD DS 사용자 계정이 처음으로 동기화되는 경우 Microsoft 365 라이선스가 자동으로 할당되지는 않습니다. 전자 메일과 같은 Microsoft 365 서비스에 액세스할 수 없습니다. 먼저 사용 위치를 할당해야 합니다. 그런 다음 그룹 구성원 자격을 통해 개별적으로 또는 동적으로 이러한 사용자 계정에 라이선스를 할당합니다.
>

다음은 하이브리드 ID 모델을 사용할 때의 두 가지 인증 유형입니다.

| 인증 유형 | 설명 |
|:-------|:-----|
| 관리되는 인증 | Azure AD는 로컬에 저장된 해시된 암호 버전을 사용하여 인증 프로세스를 처리하거나, 자격 증명을 프레미스 소프트웨어 에이전트에 전송하여 해당 자격 증명을 전송하여 해당 인증서를 인증할 수 있습니다. <br> <br>  관리되는 인증에는 PHS(암호 해시 동기화) 및 PTA(통과 인증)의 두 가지 유형이 있습니다. PHS를 사용하여 Azure AD는 인증 자체를 수행합니다. PTA를 사용하여 Azure AD에는 AD DS가 인증을 수행하고 있습니다. |
| 페더레이션 인증 | Azure AD는 인증을 요청하는 클라이언트 컴퓨터를 다른 ID 공급자로 리디렉션합니다. |
|  |  |

자세한 [내용은 올바른](https://docs.microsoft.com/azure/active-directory/hybrid/choose-ad-authn) 인증 방법 선택을 참조합니다.

## <a name="enforcing-strong-sign-ins"></a>강력한 로그인 강요

사용자 로그인 보안을 강화하기 위해 다음 표의 기능을 사용 합니다.

| 기능 | 설명 | 추가 정보 | 라이선스 요구 사항 |
|:-------|:-----|:-----|:-----|:-----|
| 비즈니스용 Windows Hello | Windows 장치에서 로그인할 때 암호를 강력한 2단계 인증으로 바니다. 2단계 인증 요소는 장치에 연결된 새로운 유형의 사용자 자격 증명과 생체 인식 또는 PIN입니다. | [비즈니스용 Windows Hello 개요](https://docs.microsoft.com/windows/security/identity-protection/hello-for-business/hello-overview) | Microsoft 365 E3 혹은 E5 |
| Azure AD 암호 보호 | 알려진 약한 암호 및 해당 변형을 검색하고 차단하며 조직과 관련이 있는 약한 용어를 추가로 차단할 수도 있습니다. | [Azure AD 암호 보호 구성](https://docs.microsoft.com/azure/active-directory/authentication/concept-password-ban-bad) | Microsoft 365 E3 혹은 E5 |
| MFA(다단계 인증) 사용 | MFA를 사용하려면 사용자 로그인 시 사용자 계정 암호 이상의 추가 확인(예: 스마트폰 앱 확인 또는 스마트폰으로 전송된 문자 메시지)이 필요합니다. 사용자가 [MFA를](https://support.microsoft.com/office/set-up-multi-factor-authentication-in-microsoft-365-business-a32541df-079c-420d-9395-9d59354f7225) 설정하는 방법에 대한 지침은 이 비디오를 참조하세요. | [엔터프라이즈용 Microsoft 365 MFA](../enterprise/microsoft-365-secure-sign-in.md#mfa) | Microsoft 365 E3 혹은 E5 |
| ID 및 장치 액세스 구성 | 권장되는 선행 조건 기능 및 해당 설정과 조건부 액세스, Intune 및 Azure AD ID 보호 정책으로 구성된 설정 및 정책은 특정 액세스 요청을 허용할지 여부와 조건에 따라 결정됩니다.  | [ID 및 장치 액세스 구성](../security/office-365-security/microsoft-365-policies-configurations.md) | Microsoft 365 E3 혹은 E5 |
| Azure AD ID 보호 | 공격자가 조직의 클라우드 서비스 및 데이터에 액세스하기 위해 사용자의 계정 이름과 암호를 결정하는 자격 증명 손상으로부터 보호합니다. | [Azure AD ID 보호](https://docs.microsoft.com/azure/active-directory/active-directory-identityprotection) | Id가 & Microsoft 365 E5 또는 Microsoft 365 E3 |
|  |  |  |



## <a name="results-of-step-3"></a>3단계의 결과

Microsoft 365 테넌트의 ID에 대해 다음을 결정했습니다.

- 사용할 ID 모델입니다.
- 강력한 사용자 및 장치 액세스를 적용하는 방법

다음은 새 하이브리드 ID 요소가 강조 표시된 테넌트의 예입니다.

![테넌트에 대한 하이브리드 ID의 예](../media/tenant-management-overview/tenant-management-tenant-build-step3.png)

이 그림에서 테넌트에는 다음이 있습니다.

- DirSync 서버 및 Azure AD Connect를 사용하여 Azure AD 테넌트와 동기화되는 AD DS 포리스트입니다.
- AD DS 포리스트의 AD DS 사용자 계정 및 기타 개체의 복사본입니다.
- 사용자 계정을 기반으로 보안 사용자 로그인 및 액세스를 적용하기 위한 조건부 액세스 정책 집합입니다. 

## <a name="ongoing-maintenance-for-identity"></a>ID에 대한 지속적인 유지 관리

지속적인 기준에 따라 다음을 해야 할 수 있습니다.

- 사용자 계정 및 그룹을 추가하거나 수정합니다. 클라우드 전용 ID의 경우 Microsoft 365 관리 센터 또는 PowerShell과 같은 Azure AD 도구를 사용하여 클라우드 기반 사용자 및 그룹을 유지 관리합니다. 하이브리드 ID의 경우 AD DS 도구를 사용하여 프레미스 사용자 및 그룹을 유지 관리합니다.
- 로그인 보안 요구 사항을 적용하기 위해 ID 및 장치 액세스 구성을 추가하거나 수정합니다.

## <a name="next-step"></a>다음 단계

[![4단계. 온-프레미스 Office 서버 및 데이터 마이그레이션](../media/tenant-management-overview/tenant-management-step-grid-migration.png)](tenant-management-migration.md)

마이그레이션을 [계속하여](tenant-management-migration.md) Microsoft 365로의 마이그레이션을 계속합니다.
