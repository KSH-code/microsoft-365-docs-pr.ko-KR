---
title: 권장 암호 정책
f1.keywords:
- CSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
ms.localizationpriority: high
ms.collection:
- Adm_O365
- Adm_NonTOC
ms.custom:
- AdminSurgePortfolio
- okr_smb
- AdminTemplateSet
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 9fa2539a-2211-41fd-85a0-bc37b9619ca4
description: 암호 공격에 대한 조직의 보안을 강화하고 공통 암호를 금지하고 위험 기반 다단계 인증을 사용하세요.
ms.openlocfilehash: d05b642455369cda3897733044727719e671a619
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/06/2021
ms.locfileid: "60171762"
---
# <a name="password-policy-recommendations"></a>권장 암호 정책

조직의 관리자는 조직의 사용자에 대한 암호 정책을 설정할 책임이 있습니다. 암호 정책의 설정은 복잡하고 혼동될 수 있습니다. 이 문서에서는 조직을 암호 공격으로부터 더 안전하게 보호하기 위한 권장 사항을 제공합니다.
  
조직의 Microsoft 365 암호 만료 주기를 확인하려면 [Microsoft 365 암호 만료 정책 설정](../manage/set-password-expiration-policy.md)을 참조하세요.

Microsoft 365 암호에 대한 자세한 내용은 다음을 참조 하세요.

[암호 다시 설정](../add-users/reset-passwords.md) (문서)

[개별 사용자의 암호를 만료 기한 없음으로 설정](../add-users/set-password-to-never-expire.md) (문서)

[사용자가 암호를 직접 재설정할 수 있도록 허용](../add-users/let-users-reset-passwords.md) (문서)

[사용자 암호 다시 전송 - 관리자 도움말](../add-users/resend-user-password.md) (문서)
  
## <a name="understanding-password-recommendations"></a>암호 권장 사항 이해

좋은 암호의 예는 몇 가지 광범위한 범주로 분류됩니다.
  
- **일반적인 공격에 대한 저항** 사용자가 암호를 입력하는 위치(좋은 맬웨어 검색을 사용하는 알려지고 신뢰하는 장치, 유효성이 검사된 사이트) 및 선택할 암호(길이와 고유성)를 선택하는 것과 관련이 있습니다.

- **성공한 해커 공격 포함** 성공적인 해커 공격 포함은 특정 서비스에 대한 노출을 제한하거나, 사용자의 암호가 도난 당한 경우 그 피해를 완전히 방지하는 것입니다. 예를 들어, 소셜 네트워킹 자격 증명이 침해되어도 은행 계좌를 취약하게 만들지 않도록 하거나 보안이 취약한 계정에서 중요한 계정에 대한 재설정 링크를 수락하지 않도록 합니다.

- **인간 본성 이해** 많은 유효한 암호의 예가 자연스러운 인간 행동으로 실패합니다. 연구에 따르면 사용자에게 부과되는 거의 모든 규칙이 암호 품질을 약화시킬 수 있음을 보여주기 때문에 인간의 본성을 이해하는 것이 중요합니다. 길이 요구 사항, 특수 문자 요구 사항, 암호 변경 요구 사항 모두 암호의 정규화하므로 공격자가 암호를 추측하거나 해독하기 쉽게 만듭니다.

## <a name="password-guidelines-for-administrators"></a>관리자를 위한 암호 관련 지침

더욱 안전한 암호 시스템의 기본 목적은 암호 다양성입니다. 암호 정책에 다양하고 추측하기 어려운 비밀번호를 포함하고 싶을 것입니다. 다음은 조직을 최대한 안전한 상태로 유지하기 위한 몇 가지 권장 사항입니다.
  
- 8자 이상 길이 요구 사항 유지

- 문자 구성 요구 사항은 필요하지 않습니다. 예: \*&amp;(^%$

- 사용자 계정의 주기적인 암호 재설정 필요 없음

- 가장 취약한 암호를 사용하지 않도록 일반적인 암호 금지

- 사용자에게 조직 암호를 회사 관련이 아닌 목적으로 재사용하지 않도록 교육합니다.

- [다단계 인증](../security-and-compliance/set-up-multi-factor-authentication.md) 등록 시행

- 위험 기반 다단계 인증 챌린지 사용

### <a name="password-guidance-for-your-users"></a>사용자를 위한 암호 지침

다음은 조직의 사용자를 위한 몇 가지 암호 지침입니다. 사용자가 이러한 권장 사항을 알고 있어야 하며 조직 수준에서 권장 암호 정책을 시행해야 합니다.
  
- 다른 웹 사이트에서 사용하는 것과 같거나 비슷한 암호를 사용하지 마세요.

- 예를 들어 **password** 같은 한 단어나 **Iloveyou** 와 같은 일반적으로 사용되는 문구를 사용하지 마세요.

- 친구나 가족의 이름과 생일, 좋아하는 밴드, 사용하기 좋아하는 문구와 같이 자신에 대해 많이 아는 사람들도 암호를 추측하기 어렵게 만듭니다.

## <a name="some-common-approaches-and-their-negative-impacts"></a>몇 가지 일반적인 접근 방법과 부정적인 영향

다음은 가장 자주 사용하는 암호 관리 사례이지만 연구는 이 예의 부정적인 영향에 대해 경고합니다.
  
### <a name="password-expiration-requirements-for-users"></a>사용자의 암호 만료 요구 사항

암호 만료 요구 사항은 사용자가 서로 밀접하게 관련이 있는 순차적인 단어 및 숫자로 구성된 예측 가능한 암호를 선택하도록 하기 때문에 득보다 해를 줄 수 있습니다. 이 경우 이전 암호를 기준으로 다음 암호를 예측할 수 있습니다. 사이버 범죄자는 자격 증명이 손상되는 즉시 거의 항상 자격 증명을 사용하므로 암호 만료 요구 사항에는 방지 이점이 없습니다. 자세한 내용은 [강제 비밀번호 변경을 다시 생각할 시간](https://go.microsoft.com/fwlink/p/?linkid=861018)을 확인하세요.
  
### <a name="requiring-long-passwords"></a>긴 암호 요구

암호 길이 요구 사항(10자 이상)에는 예측 가능하고 바람직하지 않은 사용자 동작이 발생할 수 있습니다. 예를 들어, 16자 암호를 입력해야 하는 사용자가 문자 길이 요구 사항을 충족하지만 추측하기 어렵지 않은 **fourfourfourfour** 또는 **passwordpassword** 와 같은 반복되는 패턴을 선택할 수 있습니다. 또한 길이 요구 사항으로 사용자는 암호를 적어 두거나 재사용하거나 문서에 암호화되지 않은 상태로 저장하는 등의 안전하지 않은 방법을 채택할 확률이 높아집니다. 사용자가 고유한 암호를 생각하도록 유도하려면 최소 8자 길이의 적정 요구 사항을 유지하는 것이 좋습니다.
  
### <a name="requiring-the-use-of-multiple-character-sets"></a>여러 문자 집합을 사용해야 하는 경우

암호 복잡성 요구 사항은 주요 공간을 줄이고 사용자가 득보다 해가 될 수 있는 예측 가능한 방식으로 행동하도록 합니다. 대부분의 시스템에서는 암호 복잡성 요구 사항을 어느 정도 적용합니다. 예를 들어, 암호에 다음 세 가지 범주의 문자가 모두 있어야 합니다.
  
- 대문자

- 소문자

- 영숫자가 아닌 문자

대부분의 사용자는 첫 번째 위치에는 대문자, 마지막에는 기호, 마지막에서 두 번째 위치에는 숫자를 사용하는 등의 유사한 패턴을 사용합니다. 사이버 범죄자는 이 사실을 알고 있으므로 "s"에 대한 "$", "a"에 대한 "@", "l"에 대한 "1"과 같은 가장 일반적인 대체를 사용하여 사전 공격을 실행합니다. 사용자가 대/소문자, 숫자, 특수 문자를 원하는 대로 조합하여 선택하도록 하면 부정적인 영항을 끼칩니다. 일부 복잡한 요구 사항은 사용자가 안전하고 기억하기 쉬운 암호를 사용하지 못하게 하고 덜 안전하고 덜 기억하기 쉬운 암호를 제공하도록 합니다.
  
## <a name="successful-patterns"></a>성공한 패턴

이와 대조적으로, 다음은 암호 다양성을 위해 권장되는 몇 가지 권장 사항입니다.
  
### <a name="ban-common-passwords"></a>일반적인 암호 금지

암호를 만들 때 사용자에게 제공해야 하는 가장 중요한 암호 요구 사항은 조직의 무작위 암호 공격에 대한 취약성을 줄이기 위해 일반적인 암호 사용을 금지하는 것입니다. 일반적인 사용자 암호에는 **abcdefg**, **password**, **monkey** 가 있습니다.
  
### <a name="educate-users-to-not-re-use-organization-passwords-anywhere-else"></a>다른 곳에서 조직 암호를 다시 사용하지 않도록 사용자를 교육합니다.

조직의 사용자에게 전달한 가장 중요한 메시지 중 하나는 조직 암호를 다른 위치에서 다시 사용하지 않는 것입니다. 외부 웹 사이트에서 조직 암호를 사용하면 사이버 범죄자가 암호를 해킹할 가능성이 크게 높아집니다.
  
### <a name="enforce-multi-factor-authentication-registration"></a>다단계 인증 등록 시행

사용자가 대체 전자 메일 주소, 전화 번호 또는 푸시 알림에 등록된 장치 등의 연락처 및 보안 정보를 업데이트하여 보안 문제에 대응하고 보안 이벤트 알림을 받을 수 있도록 합니다. 업데이트된 연락처 및 보안 정보는 사용자가 암호를 잊어버린 경우 또는 다른 사용자가 자신의 계정을 사용하려고 시도하는 경우 신원을 확인하는 데 도움이 됩니다. 로그인 시도나 암호 변경 같은 보안 이벤트의 경우에도 대역 외 알림 채널을 제공합니다. 
  
자세한 내용은 [다단계 인증을 설정](../security-and-compliance/set-up-multi-factor-authentication.md)을 참조하세요.
  
### <a name="enable-risk-based-multi-factor-authentication"></a>위험 기반 다단계 인증 사용

위험 기반 다단계 인증을 사용하면 시스템에서 의심스러운 작업이 감지되면 사용자가 합법적 계정 소유자인지 확인하도록 요구할 수 있습니다. 
  
## <a name="next-steps"></a>다음 단계

암호 관리에 대해 더 알고 싶으세요? 다음 문서를 읽어보세요.

- [암호는 이제 그만, 암호 없이 사용하기](https://www.microsoft.com/security/business/identity-access-management/passwordless-authentication)

- [Microsoft 암호 지침](https://www.microsoft.com/research/wp-content/uploads/2016/06/Microsoft_Password_Guidance-1.pdf)

- [강력한 웹 암호는 어떤 작업을 수행하나요?](https://go.microsoft.com/fwlink/p/?linkid=861008)

- [암호 포트폴리오 및 Finite-Effort 사용자](https://go.microsoft.com/fwlink/p/?linkid=861014)

- [사용자의 마음을 읽어 취약한 암호 방지](https://go.microsoft.com/fwlink/p/?linkid=861015)

- [보안 암호 선택](https://go.microsoft.com/fwlink/p/?linkid=861016)

- [필수 암호 변경 내용을 다시 생각하는 시간](https://go.microsoft.com/fwlink/p/?linkid=861018)

- [2015년 최악의 비밀번호](https://go.microsoft.com/fwlink/p/?linkid=861020)

## <a name="related-content"></a>관련 콘텐츠

[암호 다시 설정](../add-users/reset-passwords.md)(문서)\
[개별 사용자의 암호를 만료 기한 없음으로 설정](../add-users/set-password-to-never-expire.md)(문서)\
[사용자가 암호를 직접 재설정할 수 있도록 허용](../add-users/let-users-reset-passwords.md)(문서)\
[사용자 암호 다시 전송 - 관리자 도움말](../add-users/resend-user-password.md) (문서)
