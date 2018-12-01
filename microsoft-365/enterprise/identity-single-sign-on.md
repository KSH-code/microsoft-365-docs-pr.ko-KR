---
title: '10단계: 사용자 로그인 간소화'
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 03/01/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
ms.custom: ''
description: Azure AD Seamless SSO(Seamless Single Sign-On)를 이해하고 구성합니다.
ms.openlocfilehash: 9d18cb559d3a4a9ee401e0f94fb53bc6360d88c8
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/28/2018
ms.locfileid: "26870262"
---
# <a name="step-10-simplify-user-sign-in"></a>10단계: 사용자 로그인 간소화

*이 단계는 하이브리드 환경의 선택 사항이며, Microsoft 365 Enterprise E3 및 E5 버전에 적용됩니다.*

![](./media/deploy-foundation-infrastructure/identity_icon-small.png)

이 단계에서는 사용자가 암호 및 사용자 이름(대부분의 경우)을 입력하지 않고도 Azure AD 사용자 계정을 사용하는 서비스에 로그인할 수 있도록 Azure AD Seamless SSO(Azure Active Directory Seamless Single Sign-On)를 설정합니다. 이는 사용자가 ID 페더레이션 서버와 같은 추가 온-프레미스 구성 요소 없이도 Office 365와 같은 클라우드 기반 응용 프로그램에 보다 쉽게 액세스할 수 있도록 해줍니다.

Azure AD Connect 도구를 사용하여 Azure AD Seamless SSO를 구성합니다.

[Azure AD Seamless SSO 구성 지침](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect-sso-quick-start)을 참조하세요.

|||
|:-------|:-----|
|![Microsoft 클라우드의 테스트 랩 가이드](media/m365-enterprise-test-lab-guides/cloud-tlg-icon-small.png)| [테스트 랩 가이드: Azure AD Seamless Single Sign-on](single-sign-on-m365-ent-test-environment.md) |
|||

중간 검사점으로 이 단계에 대한 [종료 조건](identity-exit-criteria.md#crit-identity-sso)을 확인할 수 있습니다.

## <a name="next-step"></a>다음 단계

|||
|:-------|:-----|
|![](./media/stepnumbers/Step11.png)| [Office 365 로그인 페이지 사용자 지정](identity-customize-office-365-sign-in.md) |

