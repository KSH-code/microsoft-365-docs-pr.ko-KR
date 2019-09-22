---
title: '3단계: 사용자 로그인 보안 및 관리'
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
description: 사용자가 Windows 장치 및 Microsoft 365에 더욱 안전하게 로그인할 수 있습니다.
ms.openlocfilehash: edf51b344ed8f9c8e13587cc2ccf0ba1ed081da6
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/20/2019
ms.locfileid: "37088611"
---
# <a name="step-3-secure-and-manage-your-user-sign-ins"></a>3단계: 사용자 로그인 보안 및 관리

![](./media/deploy-foundation-infrastructure/identity_icon-small.png)


<a name="identity-windows-hello"></a>
## <a name="use-windows-hello-for-business"></a>비즈니스용 Windows Hello 사용

*이 단계는 선택 사항이며, Microsoft 365 Enterprise E3 및 E5 버전에 적용됩니다.*

Windows 10 Enterprise의 비즈니스용 windows Hello는 Windows 장치에 로그인할 때 암호를 강력한 2 단계 인증으로 대체합니다. 2단계 인증 요소는 장치에 연결된 새로운 유형의 사용자 자격 증명과 생체 인식 또는 PIN입니다.

자세한 내용은 [비즈니스용 Windows Hello 개요](https://docs.microsoft.com/windows/security/identity-protection/hello-for-business/hello-overview)를 참조하세요.


<a name="identity-mfa"></a>
## <a name="set-up-azure-multi-factor-authentication"></a>Azure 다단계 인증 설정

*이 단계는 선택 사항이며, Microsoft 365 Enterprise E3 및 E5 버전에 적용됩니다.*

이 단계에서는 Azure 다단계 MFA (Multi-Factor Authentication)를 설정하여 사용자 로그인 및 트랜잭션에 두 번째 보안 계층을 추가합니다.
 사용자가 암호를 올바르게 입력한 후 MFA는 추가 확인 방법을 필요로 합니다. MFA가 없으면 암호가 유일한 인증 방법입니다. 암호는 종종 공격자가 쉽게 추측하거나 신뢰할 수 없는 사용자와 본인도 모르게 공유되는 문제가 있습니다.

MFA를 사용하는 경우 두 번째 보안 계층은 다음과 같습니다.

- 스마트폰과 같이 쉽게 스푸핑되거나 복제되지 않는 개인 및 신뢰할 수 있는 장치
- 지문과 같은 생체 인식 특성

MFA를 사용하도록 설정하고 Azure AD(Azure Active Directory) 그룹을 사용하여 파일럿 사용자, 지리적 지역 또는 부서 등의 지정된 사용자 세트로 MFA를 롤아웃할 수 있는 [조건부 액세스 정책](https://docs.microsoft.com/azure/active-directory/authentication/howto-mfa-getstarted#enable-multi-factor-authentication-with-conditional-access)을 통해 보조 인증 방법을 구성합니다. 사용자에게 MFA가 사용 중임을 알려, 로그인하려면 스마트폰을 필수적으로 사용해야 하는 등의 요구 사항을 이해하고 성공적으로 로그인할 수 있도록 해야 합니다. 

자세한 내용은 [클라우드 기반 Azure 다단계 인증 배포 계획](https://docs.microsoft.com/azure/active-directory/authentication/howto-mfa-getstarted)을 참조하세요.

|||
|:-------|:-----|
|![Microsoft 클라우드의 테스트 랩 가이드](media/m365-enterprise-test-lab-guides/cloud-tlg-icon-small.png)| [테스트 랩 가이드: Azure 다단계 인증](multi-factor-authentication-microsoft-365-test-environment.md) |
|||

중간 검사점으로 이 단계에 대한 [종료 조건](identity-exit-criteria.md#crit-identity-mfa)을 확인할 수 있습니다.

<a name="identity-ident-prot"></a>
## <a name="protect-against-credential-compromise"></a>자격 증명 손상으로부터 보호

*이 단계는 선택 사항이며 Microsoft 365 Enterprise E5 버전에만 적용됩니다.*

이 섹션에서는 공격자가 조직의 클라우드 서비스 및 데이터에 액세스하기 위한 사용자의 계정 이름 및 암호를 파악한 경우에 발생하는 자격 증명 침해로부터 보호하는 정책 구성 방법을 알아봅니다. Azure AD ID Protection은 공격자가 사용자 계정의 자격 증명을 손상시키지 못하도록 하는데 도움이 되는 다양한 방법을 제공 합니다.

Azure AD ID 보호를 사용하면 다음을 수행할 수 있습니다.

|||
|:---------|:---------|
|조직의 ID에서 잠재적인 취약점 확인 및 해결|Azure AD는 기계 학습을 사용하여 로그인 및 로그인 후 활동과 같은 변칙 및 의심스러운 활동을 감지합니다. 이 데이터를 사용하여 Azure AD ID 보호는 문제를 평가하고 조치를 취하는 데 도움이 되는 보고서 및 경고를 생성합니다.|
|조직의 ID와 관련이 있는 의심스러운 동작을 감지하고 자동으로 대응|지정된 위험 수준에 도달했을 때 검색된 문제에 자동으로 대응하는 위험 기반 정책을 구성할 수 있습니다. Azure AD 및 Microsoft Intune에서 제공하는 다른 조건부 액세스 제어 외에도, 이러한 정책은 액세스를 자동으로 차단하거나 암호 재설정을 포함하는 수정 조치를 취하고, 후속 로그인에 대해 Azure 다단계 인증을 요구할 수 있습니다.|
|의심스러운 사건을 조사하여 관리 작업으로 해결|보안 사건에 대한 정보를 사용하여 위험 이벤트를 조사할 수 있습니다. 기본 워크플로를 사용하여 조사를 추적하고 암호 재설정과 같은 수정 작업을 시작할 수 있습니다.|

[Azure AD ID 보호에 대한 자세한 정보](https://docs.microsoft.com/azure/active-directory/active-directory-identityprotection)를 참조하세요.

[Azure AD ID 보호를 사용하도록 설정하는 단계](https://docs.microsoft.com/azure/active-directory/active-directory-identityprotection-enable)를 참조하세요.

이 단계를 수행하면 Azure AD ID 보호가 사용하도록 설정되며, 이를 사용하여 다음을 수행할 수 있습니다.

- 잠재적인 ID 취약점 해결
- 가능한 자격 증명 손상 시도 감지
- 지속적인 의심스러운 ID 사건 조사 및 해결

|||
|:-------|:-----|
|![Microsoft 클라우드의 테스트 랩 가이드](media/m365-enterprise-test-lab-guides/cloud-tlg-icon-small.png)| [테스트 랩 가이드: Azure AD ID 보호](azure-ad-identity-protection-microsoft-365-test-environment.md) |
|||

중간 검사점으로 이 단계에 대한 [종료 조건](identity-exit-criteria.md#crit-identity-ident-prot)을 확인할 수 있습니다.

|||
|:-------|:-----|
|![](./media/stepnumbers/Step4.png)| [사용자 계정 추가](identity-add-user-accounts.md) |
