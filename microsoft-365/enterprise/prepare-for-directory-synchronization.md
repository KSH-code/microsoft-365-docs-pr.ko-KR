---
title: " Microsoft 365로 디렉터리 동기화 준비"
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 09/30/2020
audience: Admin
ms.topic: article
ms.service: o365-administration
ms.localizationpriority: medium
f1.keywords:
- CSH
ms.custom:
- Adm_O365
- O365p_AddUsersWithDirSync
- O365M_AddUsersWithDirSync
- O365E_HRCSetupAADConnectAboutLM617031
- O365E_AddUsersWithDirSync
ms.collection:
- Ent_O365
- M365-identity-device-management
search.appverid:
- MET150
- MOP150
- MOE150
- MBS150
ms.assetid: 01920974-9e6f-4331-a370-13aea4e82b3e
description: 디렉터리 동기화를 사용하여 사용자를 프로비전할 수 있도록 준비하는 Microsoft 365 이 방법을 사용하는 경우의 장기적인 이점에 대해 설명
ms.openlocfilehash: 4bd244edfa11df315f83e78c97ec7fe63b5c2d9d
ms.sourcegitcommit: afee35210f8d68a7f20676ff2a829464b0b0adb2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/07/2021
ms.locfileid: "60216889"
---
# <a name="prepare-for-directory-synchronization-to-microsoft-365"></a> Microsoft 365로 디렉터리 동기화 준비

*이 문서는 Microsoft 365 Enterprise와 Office 365 Enterprise에 모두 적용됩니다.*

하이브리드 ID 및 디렉터리 동기화의 이점은 다음과 같습니다.

- 조직의 관리 프로그램 줄이기
- 선택적으로 Single Sign-On 시나리오 사용
- 2013에서 계정 변경 Microsoft 365

디렉터리 동기화 사용의 이점에 대한 자세한 내용은 에 대한 하이브리드 [ID(Azure AD)Azure Active Directory](/azure/active-directory/hybrid/whatis-hybrid-identity) 및 하이브리드 [ID를 Microsoft 365.](plan-for-directory-synchronization.md)

그러나 디렉터리 동기화를 수행하려면 AD DS(Active Directory 도메인 서비스)가 최소 오류와 함께 Microsoft 365 구독의 Azure AD 테넌트와 동기화되도록 계획하고 준비해야 합니다.

최상의 결과를 얻기 위해 다음 단계를 따르세요.

> [!NOTE]
> ASCII가 아닌 문자는 AD DS 사용자 계정의 특성에 대해 동기화되지 않습니다.

## <a name="1-directory-cleanup-tasks"></a>1. 디렉터리 정리 작업

AD DS를 Azure AD 테넌트와 동기화하기 전에 AD DS를 정리해야 합니다.

> [!IMPORTANT]
> 동기화하기 전에 AD DS 정리를 수행하지 않는 경우 배포 프로세스에 상당한 부정적인 영향을 줄 수 있습니다. 디렉터리 동기화 주기를 거치고 오류를 식별하고 다시 동기화하는 데 며칠 또는 몇 주가 걸릴 수 있습니다.

AD DS에서 Microsoft 365 할당할 각 사용자 계정에 대해 다음 정리 작업을 완료합니다.

1. **proxyAddresses** 특성에서 유효하고 고유한 전자 메일 주소를 확인 합니다.

2. **proxyAddresses 특성에서 중복된 값을 제거합니다.**

3. 가능한 경우 사용자 개체의 **userPrincipalName** 특성에 대한 유효하고 고유한 값을 **보장합니다.** 최상의 동기화 환경을 위해 AD DS UPN이 Azure AD UPN과 일치하는지 확인 합니다. 사용자에게 **userPrincipalName** 특성 값이 없는 경우 사용자 개체에는 **sAMAccountName** 특성에 대한 유효하고 고유한 값이 포함되어야 합니다.  **userPrincipalName** 특성에서 중복된 값을 제거합니다.

4. GAL(전체 주소 목록)을 최적으로 사용하려면 AD DS 사용자 계정의 다음 특성에 있는 정보가 올바른지 확인합니다.

   - givenName
   - surname
   - displayName
   - 직함
   - 부서
   - 사무실
   - 사무실 전화
   - 휴대폰 번호
   - 팩스 번호
   - 주소
   - 구/군/시
   - 시/도
   - 우편 번호
   - 국가

## <a name="2-directory-object-and-attribute-preparation"></a>2. 디렉터리 개체 및 특성 준비

AD DS와 MICROSOFT 365 성공적으로 디렉터리를 동기화하려면 AD DS 특성이 제대로 준비되어야 합니다. 예를 들어 특정 문자가 특정 환경과 동기화된 특정 특성에서 Microsoft 365 합니다. 예기치 않은 문자로 인해 디렉터리 동기화가 실패하지는 않지만 경고가 반환될 수 있습니다. 잘못된 문자로 인해 디렉터리 동기화가 실패합니다.

AD DS 사용자 중 일부에 중복 특성이 하나 이상 있는 경우 디렉터리 동기화가 실패합니다. 각 사용자는 고유한 특성을 가지고 있어야 합니다.

준비해야 하는 특성은 다음과 같습니다.

- **displayName**

  - 사용자 개체에 특성이 있는 경우 이 특성은 사용자 개체와 Microsoft 365.
  - 사용자 개체에 이 특성이 있는 경우 해당 특성에 대한 값이 있어야 합니다. 즉, 특성을 비워 두면 안 됩니다.
  - 최대 문자 수: 256

- **givenName**

  - 사용자 개체에 특성이 있는 경우 이 특성은 Microsoft 365 동기화되지만 Microsoft 365 필요하거나 사용하지 않습니다.
  - 최대 문자 수: 64

- **mail**

  - 특성 값은 디렉터리 내에서 고유해야 합니다.

    > [!NOTE]
    > 중복된 값이 있는 경우 값이 있는 첫 번째 사용자가 동기화됩니다. 이후 사용자는 해당 사용자에게 Microsoft 365. AD DS에서 두 사용자가 모두 표시될 수 있도록 Microsoft 365 값을 수정하거나 AD DS의 값을 모두 수정해야 Microsoft 365.

- **mailNickname(Exchange** 별칭)

  - 특성 값은 기간(.)으로 시작할 수 없습니다.
  - 특성 값은 디렉터리 내에서 고유해야 합니다.

    > [!NOTE]
    > 동기화된 이름의 밑어("_")는 이 특성의 원래 값에 잘못된 문자가 포함되어 있는 것입니다. 이 특성에 대한 자세한 내용은 별칭 [Exchange 참조하세요.](/powershell/module/exchange/set-mailbox)
    >

- **proxyAddresses**

  - 다중 값 특성
  - 값당 최대 문자 수: 256
  - 특성 값에 공백이 포함되어야 합니다.
  - 특성 값은 디렉터리 내에서 고유해야 합니다.
  - 잘못된 문자: \< \> ( ) ; , [ ] "

    유효하지 않은 문자는 형식이 ":"인 문자에 적용되어 SMTP:User@contso.com 허용되지만 SMTP:user:M@contoso.com 않습니다.

    > [!IMPORTANT]
    > 모든 SMTP(Simple Mail Transport Protocol) 주소는 전자 메일 메시징 표준을 준수해야 합니다. 중복되거나 원치 않는 주소(있는 경우)를 제거합니다.

- **sAMAccountName**

  - 최대 문자 수: 20
  - 특성 값은 디렉터리 내에서 고유해야 합니다.
  - 잘못된 문자: [ \ " | , / : \< \> + = ; ? \* ']
  - 사용자에게 잘못된 **sAMAccountName** 특성이 있지만 **userPrincipalName** 특성이 유효한 경우 사용자 계정이 Microsoft 365.
  - **sAMAccountName과** **userPrincipalName이** 모두 유효하지 않은 경우 AD DS **userPrincipalName** 특성을 업데이트해야 합니다.

- **sn(성)**

  - 사용자 개체에 특성이 있는 경우 이 특성은 Microsoft 365 동기화되지만 Microsoft 365 필요하거나 사용하지 않습니다.

- **targetAddress**

    사용자에 대해 채워진 **targetAddress** 특성(예: SMTP:tom@contoso.com)이 GAL에 Microsoft 365 필요합니다. 타사 메시징 마이그레이션 시나리오에서는 AD DS에 대한 Microsoft 365 확장이 필요합니다. 또한 Microsoft 365 확장은 AD DS의 디렉터리 동기화 도구를 사용하여 채워지는 Microsoft 365 개체를 관리하는 다른 유용한 특성을 추가합니다. 예를 들어 숨겨진 사서함 또는 메일 그룹을 관리하는 **msExchHideFromAddressLists** 특성이 추가됩니다.

  - 최대 문자 수: 256
  - 특성 값에 공백이 포함되어야 합니다.
  - 특성 값은 디렉터리 내에서 고유해야 합니다.
  - 잘못된 문자: \ \< \> ( ) ; , [ ] "
  - 모든 SMTP(Simple Mail Transport Protocol) 주소는 전자 메일 메시징 표준을 준수해야 합니다.

- **userPrincipalName**

  - **userPrincipalName** 특성은 사용자 이름이 다음에 기호(@) 및 도메인 이름과 같은 인터넷 스타일 로그인 형식(예: user@contoso.com. 모든 SMTP(Simple Mail Transport Protocol) 주소는 전자 메일 메시징 표준을 준수해야 합니다.
  - **userPrincipalName** 특성의 최대 문자 수는 113개입니다. 다음과 같이 기호(@)의 앞과 뒤에서 특정 문자 수가 허용됩니다.
  - 기호(@) 앞에 있는 사용자 이름의 최대 문자 수: 64
  - @ 기호 다음의 도메인 이름에 대한 최대 문자 수: 48
  - 잘못된 문자: \ % &amp; \* + / = ? { } | \< \> ( ) ; : , [ ] "
  - 문자 허용: A – Z, a - z, 0 - 9, ' . - _ ! # ^ ~
  - umlauts, accents, tildes와 같은 악센트 부호가 있는 문자는 유효하지 않은 문자입니다.
  - @ 문자는 각 **userPrincipalName 값에** 필요합니다.
  - @ 문자는 각 **userPrincipalName** 값의 첫 번째 문자일 수 없습니다.
  - 사용자 이름은 마침침(.), 앰퍼and( ), 공백 또는 기호(@)로 끝날 &amp; 수 없습니다.
  - 사용자 이름에는 공백을 포함할 수 없습니다.
  - 라우팅 가능한 도메인을 사용해야 합니다. 예를 들어 로컬 또는 내부 도메인은 사용할 수 없습니다.
  - 유니코드는 밑줄 문자로 변환됩니다.
  - **userPrincipalName은** 디렉터리에 중복된 값을 포함할 수 없습니다.

## <a name="3-prepare-the-userprincipalname-attribute"></a>3. userPrincipalName 특성 준비

Active Directory는 조직의 최종 사용자가 **sAMAccountName** 또는 **userPrincipalName** 을 사용하여 디렉터리에 로그인할 수 있도록 디자인되었습니다. 마찬가지로 최종 사용자는 자신의 직장 또는 학교 계정의 UPN(Microsoft 365 이름)을 사용하여 로그인할 수 있습니다. 디렉터리 동기화는 AD DS에 Azure Active Directory UPN을 사용하여 새 사용자를 만들하려고 시도합니다. UPN의 형식은 전자 메일 주소입니다.

이 Microsoft 365 UPN은 전자 메일 주소를 생성하는 데 사용되는 기본 특성입니다. ad DS 및 Azure AD에서 **userPrincipalName** 및 **proxyAddresses의** 기본 전자 메일 주소를 서로 다른 값으로 설정하기가 쉽습니다. 값을 서로 다른 값으로 설정하면 관리자와 최종 사용자에게 혼동을 주게 될 수 있습니다.

혼동을 줄이기 위해 이러한 특성을 맞추는 것이 가장 좋은 것입니다. AD FS(Active Directory Federation Services) 2.0을 사용한 Single Sign-On의 요구 사항을 충족하려면 Azure Active Directory 및 AD DS의 UPNS가 일치하는지와 유효한 도메인 네임스페이스를 사용하는지 확인해야 합니다.

## <a name="4-add-an-alternative-upn-suffix-to-ad-ds"></a>4. AD DS에 대체 UPN 접미사 추가

사용자의 회사 자격 증명을 사용자 회사 자격 증명과 연결하기 위해 대체 UPN 접미어를 Microsoft 365 있습니다. UPN 접미사는 UPN에서 @ 문자 오른쪽에 있는 부분입니다. Single Sign-On에 사용되는 UPN에는 문자, 숫자, 마침표, 대시 및 밑줄을 포함할 수 있으며 다른 유형의 문자는 포함할 수 없습니다.

Active Directory에 대체 UPN 접미사 추가 방법에 대한 자세한 내용은 디렉터리 동기화 [준비를 참조하세요.](https://go.microsoft.com/fwlink/p/?LinkId=525430)

## <a name="5-match-the-ad-ds-upn-with-the-microsoft-365-upn"></a>5. AD DS UPN과 UPN Microsoft 365 일치

디렉터리 동기화를 이미 설정한 경우 해당 디렉터리에 대한 Microsoft 365 AD DS에 정의된 사용자의 AD DS UPN과 일치하지 않을 수 있습니다. 도메인이 확인되기 전에 사용자에게 라이선스가 할당된 경우 이와 같은 문제가 발생할 수 있습니다. 이 문제를 해결하려면 [PowerShell을 사용하여 중복된 UPN을](https://go.microsoft.com/fwlink/p/?LinkId=396730) 수정하여 사용자의 UPN을 업데이트하여 Microsoft 365 UPN이 회사 사용자 이름 및 도메인과 일치하는지 확인 AD DS에서 UPN을 업데이트하고 AZURE ACTIVE DIRECTORY ID와 동기화하려면 AD DS를 변경하기 전에 Microsoft 365 라이선스를 제거해야 합니다.

디렉터리 동기화를 위해 라우팅할 수 없는 도메인(예: [.local 도메인)을 준비하는 방법도 참조합니다.](prepare-a-non-routable-domain-for-directory-synchronization.md)

## <a name="next-steps"></a>다음 단계

위의 1~5단계를 완료한 경우 디렉터리 동기화 설정 [을 참조하세요.](set-up-directory-synchronization.md)
