---
title: 게스트 및 외부 B2B 액세스를 허용 하기 위한 id 및 장치 액세스 정책-Microsoft 365 Enterprise | Microsoft Docs
description: 게스트 및 외부 사용자의 액세스를 보호 하기 위한 권장 조건부 액세스 및 관련 정책에 대해 설명 합니다.
author: BrendaCarter
manager: johmar
ms.prod: microsoft-365-enterprise
ms.topic: article
f1.keywords:
- NOCSH
ms.author: bcarter
ms.reviewer: martincoetzer
ms.custom:
- it-pro
- goldenconfig
ms.collection:
- M365-identity-device-management
- M365-security-compliance
ms.openlocfilehash: ca9b752f55ebe3fecec4f312bc89b45d99cf0d7d
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/29/2020
ms.locfileid: "41601055"
---
# <a name="policies-for-allowing-guest-and-external-b2b-access"></a>게스트 및 외부 B2B 액세스를 허용 하기 위한 정책
이 문서에서는 B2B 계정 액세스 (게스트 및 외부 사용자)를 허용 하도록 권장 되는 일반 id 및 장치 액세스 정책을 조정 하는 방법에 대해 설명 합니다. 이 지침은 [일반 id 및 장치 액세스 정책을](identity-access-policies.md)기반으로 합니다.

이러한 권장 사항은 보호의 **기본** 계층에 적용 되도록 설계 되었습니다. 그러나 **중요** 및 **높은 규제** 된 보호에 대 한 요구 사항의 세분성을 기반으로 권장 사항을 조정할 수 있습니다. 

B2B 사용자가 Azure AD 테 넌 트를 사용 하 여 인증할 수 있도록 경로를 제공 하면 이러한 사용자에 게 전체 환경에 대 한 액세스 권한이 부여 되지 않습니다. B2B 사용자는 조건부 액세스 정책에 부여 된 서비스 내에서 파일과 같이 공유 되는 리소스에만 액세스할 수 있습니다.

## <a name="updating-the-common-policies-to-allow-and-protect-guest-and-external-access"></a>게스트 및 외부 액세스를 허용 하 고 보호 하기 위해 일반 정책 업데이트 

다음 다이어그램에서는 일반 id 및 장치 액세스 정책을 보여주고, 게스트 및 외부 액세스를 보호 하기 위해 추가 하거나 업데이트할 정책을 설명 합니다 (연필 아이콘 포함). 

![게스트 액세스 보호를 위한 정책 업데이트 요약](../images/identity-access-ruleset-guest.png)

다음 표에는 업데이트 하거나 새로 만드는 데 필요한 정책이 나와 있습니다. 공통 정책- [일반 id 및 장치 액세스 정책](identity-access-policies.md) 문서의 관련 구성 지침에 대 한 링크를 제공 합니다.

|보호 수준|정책도|추가 정보|
|:---------------|:-------|:----------------|
|**기준선**|[게스트 및 외부 사용자에 대 한 MFA 항상 필요](identity-access-policies.md#require-mfa-based-on-sign-in-risk)|이 새 규칙을 만들어 게스트 및 외부 사용자 에게만 적용 합니다. 로그인 위험에서 항상 MFA를 적용 하도록 모든 옵션을 선택 하지 않은 상태로 유지 합니다.|
|        |[로그인 위험이 *보통* 또는 *높을* 때 MFA 필요](identity-access-policies.md#require-mfa-based-on-sign-in-risk)|이 규칙을 수정 하 여 게스트 및 외부 사용자를 제외 합니다.|
|        |[호환 PC 필요](identity-access-policies.md#require-compliant-pcs-but-not-compliant-phones-and-tablets)|이 규칙을 수정 하 여 게스트 및 외부 사용자를 제외 합니다.|

조건부 액세스 규칙에 게스트 및 외부 사용자를 포함 하거나 제외 하려면 포함 또는 제외 탭을 클릭 하 고 **모든 게스트 및 외부 사용자**를 확인 합니다.

![게스트를 제외 하기 위한 컨트롤의 화면 캡처](../images/identity-access-exclude-guests-ui.png)

## <a name="more-information"></a>추가 정보

### <a name="guests-vs-external-users"></a>게스트 및 외부 사용자
Azure AD에서 게스트 및 외부 사용자는 동일 합니다. 이러한 두 가지 유형의 사용자는 모두 게스트입니다. 게스트 사용자는 B2B 사용자입니다.

Microsoft 팀은 게스트 사용자와 앱 내의 외부 사용자를 구분 하지만 인증 시 이러한 사용자는 둘 다 됩니다. 팀 게스트 및 외부 사용자에 대 한 자세한 내용은 [팀에 대 한 게스트 및 외부 액세스 활성화](teams-access-policies.md#enabling-guest-and-external-access-for-teams)를 참조 하세요.

### <a name="require-mfa-always-for-guest-and-external-users"></a>게스트 및 외부 사용자에 대 한 MFA 항상 필요
이 규칙은 홈 테 넌 트에서 MFA에 대 한 등록 여부에 관계 없이 테 넌 트에 MFA를 등록 하 라는 메시지를 표시 합니다. 테 넌 트의 리소스에 액세스할 때 게스트 및 외부 사용자는 모든 요청에 대해 MFA를 사용 해야 합니다. 

### <a name="excluding-guest-and-external-users-from-risk-based-mfa"></a>위험 기반 MFA 로부터 게스트 및 외부 사용자 제외
조직에서 Id 보호를 사용 하 여 B2B 사용자에 게 위험 기반 정책을 적용 하는 경우에는 해당 개인의 id로 인해 리소스 디렉터리의 B2B 공동 작업 사용자에 대 한 Id 보호 구현에 제한이 있습니다. 디렉토리로. 이러한 제한으로 인해 Microsoft는 위험 기반 MFA 정책에서 게스트 사용자를 제외 하 고이 사용자가 항상 MFA를 사용 하도록 요구 하는 것이 좋습니다. 

자세한 내용은 [B2B 공동 작업 사용자에 대 한 Id 보호의 제한 사항을](https://docs.microsoft.com/azure/active-directory/identity-protection/concept-identity-protection-b2b#limitations-of-identity-protection-for-b2b-collaboration-users)참조 하세요. 

### <a name="excluding-guest-and-external-users-from-device-management"></a>장치 관리에서 게스트 및 외부 사용자 제외 
한 조직 에서만 장치를 관리할 수 있습니다. 장치 준수를 요구 하는 정책에서 게스트 및 외부 사용자를 제외 하지 않으면 이러한 정책은 이러한 사용자를 차단 합니다. 

## <a name="next-steps"></a>다음 단계

[팀 조건부 액세스를 사용 하도록 설정 하는 방법 알아보기](teams-access-policies.md)

