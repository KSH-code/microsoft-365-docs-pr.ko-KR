---
title: '5단계: 다단계 인증 설정'
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 03/05/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
ms.custom: ''
description: 사용자 계정에 대한 Multi-Factor Authentication을 이해하고 구성합니다.
ms.openlocfilehash: a54eb047c94430a2b3f61d06500c929e400e3d82
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/28/2018
ms.locfileid: "26870203"
---
# <a name="step-5-set-up-multi-factor-authentication"></a>5단계: 다단계 인증 설정

*이 단계는 선택 사항이며, Microsoft 365 Enterprise E3 및 E5 버전에 적용됩니다.*

![](./media/deploy-foundation-infrastructure/identity_icon-small.png)

이 단계에서는 MFA(다단계 인증)를 설정하여 사용자 로그인 및 트랜잭션에 두 번째 보안 계층을 추가합니다. MFA는 사용자가 암호를 올바르게 입력한 후 추가 인증 방법을 요구합니다. MFA가 없으면 암호가 유일한 인증 방법입니다. 암호의 문제는 대부분 공격자가 추측하기 쉽거나 모르는 새 신뢰할 수 없는 자와 공유된다는 점입니다.

MFA를 사용하는 경우 두 번째 보안 계층은 다음과 같습니다.

- 스마트폰과 같이 쉽게 스푸핑되거나 복제되지 않는 개인 및 신뢰할 수 있는 장치
- 지문과 같은 생체 인식 특성

MFA를 사용하도록 설정하고 사용자 계정 단위로 보조 인증 방법을 구성합니다. 사용자에게 MFA가 사용 중임을 알려, 로그인하려면 스마트폰을 필수적으로 사용해야 하는 등의 요구 사항을 이해하고 성공적으로 로그인할 수 있도록 해야 합니다.

자세한 내용은 [Office 365 배포에 대한 다단계 인증 계획](https://support.office.com/article/Plan-for-multifactor-authentication-for-Office-365-Deployments-043807b2-21db-4d5c-b430-c8a6dee0e6ba)을 참조하세요.

다단계 인증을 구성하려면 [Office 365 사용자에 대해 다단계 인증을 설정](https://support.office.com/article/Set-up-multi-factor-authentication-for-Office-365-users-8f0454b2-f51a-4d9c-bcde-2c48e41621c6)합니다.

조건부 액세스 정책을 사용하는 MFA가 필요할 수 있습니다. 예를 들어 인증 위험이 중간 또는 높은 것으로 판단되는 경우 MFA를 요구하는 정책을 구성할 수 있습니다. 자세한 내용은 정보 보호 단계에서 [일반 ID 및 장치 액세스 정책](identity-access-policies.md#require-mfa-based-on-sign-in-risk)을 참조하세요.

>[!Note]
>Microsoft Office 2010 이하 및 Apple Mail과 같은 일부 응용 프로그램에서는 MFA를 사용할 수 없습니다. 이러한 앱을 사용하려면 기존 암호 대신 "앱 암호"를 사용해야 합니다. 앱 암호를 사용하면 앱이 MFA를 무시하고 계속 작동할 수 있습니다. 앱 암호에 대한 자세한 내용은 [Office 365에 대한 앱 암호 만들기](https://support.office.com/article/Create-an-app-password-for-Office-365-3e7c860f-bda4-4441-a618-b53953ee1183)를 참조하세요.
>

|||
|:-------|:-----|
|![Microsoft 클라우드의 테스트 랩 가이드](media/m365-enterprise-test-lab-guides/cloud-tlg-icon-small.png)| [테스트 랩 가이드: 다단계 인증](multi-factor-authentication-microsoft-365-test-environment.md) |
|||

중간 검사점으로 이 단계에 대한 [종료 조건](identity-exit-criteria.md#crit-identity-mfa)을 확인할 수 있습니다.

## <a name="next-step"></a>다음 단계

|||
|:-------|:-----|
|![](./media/stepnumbers/Step6.png)| [자격 증명 손상으로부터 보호](identity-azure-ad-identity-protection.md) |

