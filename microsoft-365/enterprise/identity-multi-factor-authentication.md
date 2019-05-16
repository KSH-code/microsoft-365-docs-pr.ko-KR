---
title: '4단계: 안전한 사용자 인증 구성'
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 04/17/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-identity-device-management
- Strat_O365_Enterprise
ms.custom: ''
description: 사용자 계정에 대한 Multi-Factor Authentication을 이해하고 구성합니다.
ms.openlocfilehash: 73e884802329765fd6a89cfb7d0e04116c17968c
ms.sourcegitcommit: 66bb5af851947078872a4d31d3246e69f7dd42bb
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/15/2019
ms.locfileid: "34072088"
---
# <a name="step-4-configure-secure-user-authentication"></a>4단계: 안전한 사용자 인증 구성

![](./media/deploy-foundation-infrastructure/identity_icon-small.png)

<a name="identity-mfa"></a>
## <a name="set-up-multi-factor-authentication"></a>다단계 인증 설정

*이 단계는 선택 사항이며, Microsoft 365 Enterprise E3 및 E5 버전에 적용됩니다.*

이 단계에서는 MFA(다단계 인증)를 설정하여 사용자 로그인 및 트랜잭션에 두 번째 보안 계층을 추가합니다. MFA는 사용자가 암호를 올바르게 입력한 후 추가 인증 방법을 요구합니다. MFA가 없으면 암호가 유일한 인증 방법입니다. 암호의 문제는 대부분 공격자가 추측하기 쉽거나 모르는 새 신뢰할 수 없는 자와 공유된다는 점입니다.

MFA를 사용하는 경우 두 번째 보안 계층은 다음과 같습니다.

- 스마트폰과 같이 쉽게 스푸핑되거나 복제되지 않는 개인 및 신뢰할 수 있는 장치
- 지문과 같은 생체 인식 특성

MFA를 사용하도록 설정하고 사용자 계정 단위로 보조 인증 방법을 구성합니다. 사용자에게 MFA가 사용 중임을 알려, 로그인하려면 스마트폰을 필수적으로 사용해야 하는 등의 요구 사항을 이해하고 성공적으로 로그인할 수 있도록 해야 합니다.

자세한 내용은 [Multi-Factor Authentication 계획](https://docs.microsoft.com/azure/active-directory/authentication/howto-mfa-getstarted)을 참조하세요.

>[!Note]
>Microsoft Office 2010 이하 및 Apple Mail과 같은 일부 응용 프로그램에서는 MFA를 사용할 수 없습니다. 이러한 앱을 사용하려면 기존 암호 대신 "앱 암호"를 사용해야 합니다. 앱 암호를 사용하면 앱이 MFA를 무시하고 계속 작동할 수 있습니다. 앱 암호에 대한 자세한 내용은 [Office 365에 대한 앱 암호 만들기](https://support.office.com/article/Create-an-app-password-for-Office-365-3e7c860f-bda4-4441-a618-b53953ee1183)를 참조하세요.
>

|||
|:-------|:-----|
|![Microsoft 클라우드의 테스트 랩 가이드](media/m365-enterprise-test-lab-guides/cloud-tlg-icon-small.png)| [테스트 랩 가이드: 다단계 인증](multi-factor-authentication-microsoft-365-test-environment.md) |
|||

중간 검사점으로 이 단계에 대한 [종료 조건](identity-exit-criteria.md#crit-identity-mfa)을 확인할 수 있습니다.



<a name="identity-ident-prot"></a>
## <a name="protect-against-credential-compromise"></a>자격 증명 손상으로부터 보호

*이 단계는 선택 사항이며 Microsoft 365 Enterprise E5 버전에만 적용됩니다.*

이 섹션에서는 공격자가 조직의 클라우드 서비스 및 데이터에 액세스하기 위한 사용자의 계정 이름 및 암호를 파악한 경우에 발생하는 자격 증명 침해로부터 보호하는 정책 구성 방법을 알아봅니다. Azure AD ID 보호 기능에서는 공격자가 계정 및 그룹을 거쳐 가장 귀중한 데이터까지 이동하지 못하도록 하는 다양한 방법을 제공합니다.

Azure AD ID 보호를 사용하면 다음을 수행할 수 있습니다.

|||
|:---------|:---------|
|조직의 ID에서 잠재적인 취약점 확인 및 해결|Azure AD는 기계 학습을 사용하여 로그인 및 로그인 후 활동과 같은 의심스러운 활동과 비정상적인 상태를 감지합니다. ID 보호는 이 데이터를 사용하여 보고서를 생성하며 사용자가 문제를 평가하고 조치를 취할 수 있도록 경고를 생성합니다.|
|조직의 ID와 관련이 있는 의심스러운 동작을 감지하고 자동으로 대응|지정된 위험 수준에 도달했을 때 감지된 문제에 자동으로 대응하는 위험 기반 정책을 구성할 수 있습니다. 이러한 정책은 Azure Active Directory와 EMS(Enterprise Mobility + Security)에서 제공하는 다른 조건부 액세스 제어에 추가로 액세스를 자동으로 차단하거나 시정 조치(예: 암호 재설정, 후속 로그인에 다단계 인증 요구)를 취할 수 있습니다.|
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

## <a name="monitor-tenant-and-sign-in-activity"></a>테넌트 및 로그인 활동 모니터링

*이 단계는 선택 사항이며, Microsoft 365 Enterprise E3 및 E5 버전에 적용됩니다.*

이 단계에서는 Azure AD 보고를 사용하여 감사 로그 및 로그인 활동을 검토합니다. 두 가지 유형의 보고서를 사용할 수 있습니다.

**감사 로그 활동 보고서**는 Azure AD 테넌트에서 수행된 모든 작업 내역을 기록합니다. 이 보고서는 다음과 같은 질문에 대한 답을 제공합니다.

- 관리자 그룹에 다른 사용자를 추가한 사람은 누구인가요?
- 특정 앱에 로그인 중인 사용자는 누구인가요?
- 발생한 암호 재설정 횟수는 몇 회인가요?

**로그인 활동 보고서**는 감사 로그 보고서에서 보고한 작업을 수행한 사람을 기록합니다. 이 보고서는 다음과 같은 질문에 대한 답을 제공합니다.

- 조사 중인 특정 사용자의 로그인 패턴은 무엇인가요?
- 하루, 일주일 또는 한 달 동안 몇 번 로그인했나요?
- 이러한 로그인 시도에 실패한 횟수와 그 이유는 무엇인가요?

보고서 및 보고서 액세스 방법에 대한 자세한 내용은 [Azure Active Directory 보고](https://docs.microsoft.com/azure/active-directory/active-directory-reporting-azure-portal)를 참조하세요.

이 단계를 마치면 이러한 보고서에 대해 알게 되고, 계획 및 보안을 위해 보고서를 사용하여 Azure AD 이벤트 및 활동에 대한 이해를 넓힐 수 있는 방법을 파악하게 됩니다.



## <a name="next-step"></a>다음 단계

|||
|:-------|:-----|
|![](./media/stepnumbers/Step5.png)| [사용자에 대한 액세스 간소화](identity-password-reset.md) |

