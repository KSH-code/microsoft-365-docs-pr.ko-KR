---
title: '9단계: 암호 업데이트 간소화'
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
description: 하이브리드 환경에 대한 암호 쓰기 저장을 이해하고 구성합니다.
ms.openlocfilehash: 55da101ca729de804ae76dafbe35a46969af9d8d
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/28/2018
ms.locfileid: "26869901"
---
# <a name="step-9-simplify-password-updates"></a>9단계: 암호 업데이트 간소화

*이 단계는 하이브리드 환경의 선택 사항이며, Microsoft 365 Enterprise E3 및 E5 버전에 적용됩니다.*

![](./media/deploy-foundation-infrastructure/identity_icon-small.png)

이 단계에서는 사용자가 Azure AD(Active Directory)를 통해 자신의 암호를 재설정하도록 허용합니다. 이는 로컬 Windows Server AD(Active Directory)에 복제됩니다. 이 프로세스를 암호 쓰기 저장이라고 합니다. 암호 쓰기 저장을 사용하면 사용자가 사용자 계정 및 해당 특성이 저장된 온-프레미스 Windows Server AD를 통해 암호를 업데이트할 필요가 없습니다. 이는 온-프레미스 네트워크에 대한 원격 액세스 연결이 없는 로밍 또는 원격 사용자에게 유용합니다.

암호 쓰기 저장은 계정 손상의 높은 위험이 감지된 경우 사용자에게 온-프레미스 암호를 변경하도록 요구하는 등 ID 보호 기능을 최대한 활용하기 위해 필요합니다.

추가 정보 및 구성 지침은 [암호 쓰기 저장을 지원하는 Azure AD SSPR](https://docs.microsoft.com/azure/active-directory/active-directory-passwords-writeback)을 참조하세요.

>[!Note]
>가능한 최상의 환경 및 새로운 기능(릴리스될 때)을 유지하도록 최신 버전의 Azure AD Connect로 업그레이드하세요. 자세한 내용은 [Azure AD Connect의 사용자 지정 설치](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect-get-started-custom)를 참조하세요.
>

중간 검사점으로 이 단계에 대한 [종료 조건](identity-exit-criteria.md#crit-identity-pw-writeback)을 확인할 수 있습니다.

## <a name="next-step"></a>다음 단계

|||
|:-------|:-----|
|![](./media/stepnumbers/Step10.png)| [사용자 로그인 간소화](identity-single-sign-on.md) |

