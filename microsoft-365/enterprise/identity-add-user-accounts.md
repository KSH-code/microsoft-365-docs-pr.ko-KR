---
title: '4단계: 사용자 계정 추가'
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 09/20/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-identity-device-management
- Strat_O365_Enterprise
ms.custom: ''
description: 사용자 계정 및 그룹을 클라우드에서 직접 추가하거나 온-프레미스 디렉터리와 동기화하는 방법으로 추가할 수 있습니다.
ms.openlocfilehash: 324d4662f868a4a92693b43c6bc0f75c11f20519
ms.sourcegitcommit: 93e6bf1b541e22129f8c443051375d0ef1374150
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/13/2020
ms.locfileid: "42633106"
---
# <a name="step-4-add-your-user-accounts"></a>4단계: 사용자 계정 추가

![2단계-ID](../media/deploy-foundation-infrastructure/identity_icon-small.png)

<a name="identity-cloud-only"></a>
## <a name="create-your-user-accounts-for-cloud-only-identity"></a>클라우드 전용 ID에 대한 사용자 계정 만들기

클라우드 전용 ID의 경우 Azure AD(Azure Active Directory)에서 사용자 및 그룹을 만듭니다. 다음을 사용할 수 있습니다.

- Microsoft 365 관리 센터
- Azure Portal
- Azure PowerShell

<a name="identity-sync"></a>
## <a name="synchronize-identities-for-hybrid-identity"></a>하이브리드 ID의 ID 동기화

*이는 하이브리드 환경의 필수 사항이며, Microsoft 365 Enterprise E3 및 E5 버전에 적용됩니다.*

이 섹션에서는 온-프레미스 AD DS(Active Directory Domain Services)를 Office 365, Microsoft Intune 및 Microsoft 365 Enterprise에 포함된 기타 클라우드 기반 서비스에서 사용하는 Azure AD 테넌트와 동기화합니다.

Azure AD Connect는 단일 또는 다중 포리스트 AD DS 환경에서 실제로 필요한 ID만 Azure AD 테넌트에 동기화하는 과정을 안내하는 지원되는 Microsoft 도구입니다. 다음 그림에서는 Azure AD Connect 동기화의 기본 프로세스를 보여 줍니다.

![Azure AD Connect에서 온-프레미스 디렉터리를 Azure AD와 동기화하는 방법](../media/identity-add-user-accounts/azure-ad-connect.png)

1. 서버에서 실행되는 Azure AD Connect는 계정, 그룹 및 연락처 변경 내용을 AD DS에서 폴링합니다.
2. Azure AD Connect는 이러한 변경 내용을 Microsoft 365 구독의 Azure AD 테넌트로 보냅니다.

하이브리드 ID 솔루션에서 가장 처음으로 결정할 사항은 인증 요구 사항입니다. 옵션은 다음과 같습니다.

- **관리되는 인증**을 사용하는 경우 Azure AD는 사용자 로그인에 대한 인증 프로세스를 처리합니다. 관리되는 인증에는 다음 두 가지 방법이 있습니다. 
    - **PHS(암호 해시 동기화)**[일부 프리미엄 기능에 권장되고 필요함] Azure AD에서 온-프레미스 디렉터리 개체에 대한 인증을 사용하도록 설정하는 가장 간단한 방법입니다. Azure AD Connect는 AD DS에서 해시된 암호를 추출하고 암호의 보안을 강화하고 Azure AD에 동기화합니다. 자세한 내용은 [Azure AD Connect 동기화를 사용하여 암호 해시 동기화 구현](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-password-hash-synchronization)을 참조하세요.
    - **PTA(통과 인증)** 는 Azure AD 기반 서비스에 대한 간단한 암호 유효성 검사 솔루션을 제공합니다. PTA는 하나 이상의 온-프레미스 서버에서 실행되는 에이전트를 사용하여 온-프레미스 AD DS를 통해 직접 사용자 인증이 유효한지 검사합니다. 자세한 내용은 [Azure Active Directory 통과 인증으로 사용자 로그인](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect-pass-through-authentication)을 참조하세요.
- **페더레이션 인증**을 사용하는 경우 인증 프로세스는 사용자의 로그인에 대해 AD FS(Active Directory Federation Services)와 같은 ID 페더레이션 서버를 통해 다른 ID 공급자로 리디렉션됩니다. ID 공급자는 스마트 카드 기반 인증과 같은 추가 인증 방법을 제공할 수 있습니다. 자세한 내용은 [Azure Active Directory 하이브리드 ID 솔루션에 적합한 인증 방법 선택](https://docs.microsoft.com/azure/security/azure-ad-choose-authn)를 참조하세요.

Microsoft 365 Enterprise에 대한 인증과 ID모델의 개요에 대한 비디오를 시청하세요.

<p> </p>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE2Pjwu]

하이브리드 ID 솔루션을 확인한 후에는 [IdFix 디렉터리 동기화 오류 수정 도구](https://www.microsoft.com/download/details.aspx?id=36832)를 다운로드하고 실행하여 AD DS에서 문제를 분석합니다.

IdFix 도구에서 식별된 모든 문제를 해결한 후에는 [암호 해시 동기화 구현](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnectsync-implement-password-hash-synchronization)에서 Azure AD Connect 도구를 설치하는 방법과 Microsoft 365 구독에 대해 온-프레미스 AD DS와 Azure AD 테넌트 간의 디렉터리 동기화를 구성하는 방법에 대한 지침을 참조하세요. 동기화가 시작되면 AD DS와 같은 온-프레미스 ID 공급자를 통해 사용자 계정 및 그룹을 유지 관리하게 됩니다.

Microsoft에서는 직원 안전과 생산성을 유지하기 위해 [ID 및 디바이스 액세스](microsoft-365-policies-configurations.md)에 대한 권장 사항을 제공합니다. 

- 하이브리드 환경에 대한 권장 요구 사항에 대해서는 [필수 구성 요소](identity-access-prerequisites.md#prerequisites) 열의 **암호 해시 동기화를 사용한 Active Directory**를 참조하세요. 

- 클라우드 전용 환경에 대한 권장 요구 사항에 대해서는 [필수 구성 요소](identity-access-prerequisites.md#prerequisites) 열의 **클라우드만**을 참조하세요.

Azure AD에 온-프레미스 사용자 및 그룹이 있으면 라이선스를 할당을 시작하고 비즈니스용 OneDrive 및 Exchange Online과 같은 생산성 워크로드를 사용할 수 있습니다.

|||
|:-------|:-----|
|![Microsoft 클라우드의 테스트 랩 가이드](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon-small.png)| [테스트 랩 가이드: 암호 해시 동기화](password-hash-sync-m365-ent-test-environment.md)<br> [테스트 랩 가이드: 경유 인증](pass-through-auth-m365-ent-test-environment.md) |
|||

중간 검사점으로 이 섹션에 해당하는 [종료 조건](identity-exit-criteria.md#crit-identity-sync)을 확인할 수 있습니다.

<a name="identity-sync-health"></a>
## <a name="monitor-synchronization-health"></a>동기화 상태 모니터링

*이 단계는 선택 사항이며 Microsoft 365 E3 및 E5 버전에 모두 적용됩니다*

이 섹션에서는 각 온-프레미스 AD DS 도메인 컨트롤러에 Azure AD Connect 상태 에이전트를 설치하여 Azure AD Connect에서 제공하는 ID 인프라 및 동기화 서비스를 모니터링합니다. 모니터링 정보는 Azure AD Connect Health 포털에서 사용할 수 있습니다. 이 포털에서 경고, 성능 모니터링, 사용 현황 분석, 기타 정보를 볼 수 있습니다.

![Azure AD Connect Health의 구성 요소](../media/identity-add-user-accounts/identity-azure-ad-connect-health.png)

Azure AD Connect Health 사용 방법에 대한 주요 디자인 의사 결정은 Azure AD Connect 사용 방법을 기반으로 합니다.

- **관리되는 인증** 옵션을 사용하는 경우 [동기화와 함께 Azure AD Connect Health 사용](https://docs.microsoft.com/azure/active-directory/connect-health/active-directory-aadconnect-health-sync)을 시작하여 Azure AD Connect Health를 이해하고 구성합니다.
- AD FS(Active Directory Federation Services)에서 **페더레이션 인증**을 사용하여 계정 및 그룹의 이름만 동기화하는 경우 [AD FS와 함께 Azure AD Connect Health 사용](https://docs.microsoft.com/azure/active-directory/connect-health/active-directory-aadconnect-health-adfs)을 시작하여 Azure AD Connect Health를 이해하고 구성합니다.

이 섹션을 완료하면 다음과 같은 결과를 얻을 수 있습니다.

- 온-프레미스 ID 서버에 Azure AD Connect Health 에이전트가 설치됩니다.
- Microsoft 365 구독에 대한 Azure AD 테넌트와 함께 온-프레미스 인프라 및 동기화 활동의 현재 상태가 Azure AD Connect Health 포털에 표시됩니다.

중간 검사점으로 이 섹션에 대한 [종료 조건](identity-exit-criteria.md#crit-identity-sync-health)을 확인할 수 있습니다.



<a name="identity-pw-writeback"></a>
## <a name="simplify-password-updates"></a>암호 업데이트 간소화

*이 단계는 하이브리드 환경의 선택 사항이며, Microsoft 365 Enterprise E3 및 E5 버전에 적용됩니다.*

이 부문에서 사용자는 Azure 액티브 디렉토리(Azure AD-Microsoft Azure Active Directory)를 통해 암호를 재설정할 수 있으며 로컬 액티브 디렉토리 도메인 서비스(AD DS-Active Directory Domain Services)로 복제될 수 있습니다. 이 과정을 암호 쓰기 저장이라고 합니다. 암호 쓰기 저장에서 사용자는 사용자 계정과 속성이 저장된 온 프레미스 AD DS를 통한 암호의 업데이트가 필요 없습니다. 온-프레미스 네트워크에 대한 원격 액세스 연결이 없는 로밍 또는 원격 사용자에게 유용합니다.

암호 쓰기 저장은 계정 손상의 높은 위험이 감지된 경우 사용자에게 온-프레미스 암호를 변경하도록 요구하는 등 Azure AD ID 보호 기능을 최대한 활용하기 위해 필요합니다.

추가 정보 및 구성 지침은 [암호 쓰기 저장을 지원하는 Azure AD SSPR](https://docs.microsoft.com/azure/active-directory/active-directory-passwords-writeback)을 참조하세요.

>[!Note]
>가능한 최상의 환경 및 새로운 기능(릴리스될 때)을 유지하도록 최신 버전의 Azure AD Connect로 업그레이드하세요. 자세한 내용은 [Azure AD Connect의 사용자 지정 설치](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect-get-started-custom)를 참조하세요.
>

|||
|:-------|:-----|
|![Microsoft 클라우드의 테스트 랩 가이드](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon-small.png)| [테스트 랩 가이드: 암호 쓰기 저장](password-writeback-m365-ent-test-environment.md) |
|||

중간 검사점으로 이 섹션에 대한 [종료 조건](identity-exit-criteria.md#crit-identity-pw-writeback)을 확인할 수 있습니다.

|||
|:-------|:-----|
|![5단계](../media/stepnumbers/Step5.png)| [그룹을 사용하여 관리](identity-use-group-management.md) |
