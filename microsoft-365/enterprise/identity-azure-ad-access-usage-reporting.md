---
title: '13단계: 테넌트 및 로그인 활동 모니터링'
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
description: Azure AD 액세스 및 사용 현황 보고를 이해하고 구성합니다.
ms.openlocfilehash: 997d52bc11036e1dbb7dcc6e1f9f48a59b2ddbf5
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/28/2018
ms.locfileid: "26869705"
---
# <a name="step-13-monitor-tenant-and-sign-in-activity"></a>13단계: 테넌트 및 로그인 활동 모니터링

*이 단계는 선택 사항이며, Microsoft 365 Enterprise E3 및 E5 버전에 적용됩니다.*

![](./media/deploy-foundation-infrastructure/identity_icon-small.png)

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
|![](./media/stepnumbers/Step14.png)| [사용자가 자신의 그룹을 만들고 관리하도록 허용](identity-self-service-group-management.md) |
