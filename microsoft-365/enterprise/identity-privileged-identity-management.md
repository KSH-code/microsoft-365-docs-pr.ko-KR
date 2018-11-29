---
title: '3단계: 주문형 전역 관리자 설정'
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
description: Azure AD Privileged Identity Management를 이해하고 구성합니다.
ms.openlocfilehash: 659beff3c31d17afa03d3ecf754c581f3ca2e230
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/28/2018
ms.locfileid: "26869910"
---
# <a name="step-3-set-up-on-demand-global-administrators"></a>3단계: 주문형 전역 관리자 설정

*이 단계는 선택 사항이며 Microsoft 365 Enterprise E5 버전에만 적용됩니다.*

![](./media/deploy-foundation-infrastructure/identity_icon-small.png)

이 단계에서는 Azure AD PIM(Privileged Identity Management)을 설정하여 전역 관리자 계정이 악의적인 사용자의 공격에 노출되는 시간을 줄일 수 있습니다. PIM은 필요한 경우 전역 관리자 역할의 주문형 Just-In-Time 할당을 제공합니다.  

전역 관리자 계정은 영구 관리자가 되지 않고 적격 관리자가 됩니다. 전역 관리자 역할은 누군가가 필요로 하기 전까지는 비활성화되어 있습니다. 그러면 활성화 프로세스를 완료하여 일정 기간 전역 관리자 계정에 전역 관리자 역할을 추가합니다. 시간이 만료되면 PIM은 전역 관리자 계정에서 전역 관리자 역할을 제거합니다.

PIM은 Microsoft 365 Enterprise E5에 포함된 Azure Active Directory Premium P2에서 제공됩니다. 또는 전역 관리자 계정용 개별 Azure Active Directory Premium P2 라이선스를 구매할 수 있습니다.

Azure AD 테넌트 및 전역 관리자 계정에서 Azure PIM을 사용하도록 설정하려면 [PIM 구성 방법](https://docs.microsoft.com/azure/active-directory/active-directory-privileged-identity-management-configure)을 참조하세요.

권한 있는 액세스를 사이버 공격자로부터 보호하는 포괄적인 로드맵을 마련하려면 [Azure AD의 하이브리드 및 클라우드 배포에서 권한 있는 액세스 보호](https://docs.microsoft.com/azure/active-directory/admin-roles-best-practices)를 참조하세요.

중간 검사점으로 이 단계에 대한 [종료 조건](identity-exit-criteria.md#crit-identity-pim)을 확인할 수 있습니다.

## <a name="next-step"></a>다음 단계

|||
|:-------|:-----|
|![](./media/stepnumbers/Step4.png)| [암호 재설정 간소화](identity-password-reset.md) |

