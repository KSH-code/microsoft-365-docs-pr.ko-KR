---
title: 손상된 전자 메일 계정에 응답
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: how-to
ms.collection:
- o365_security_incident_response
- M365-security-compliance
- m365solution-smb
ms.custom:
- TopSMBIssues
- seo-marvel-apr2020
localization_priority: Priority
search.appverid:
- MET150
description: Microsoft 365에서 제공하는 도구를 사용하여 손상된 전자 메일 계정을 인식하고 대처하는 방법에 대해 알아봅니다.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 193afd61509b7361ac18dd32d827182752fb61ed
ms.sourcegitcommit: d08fe0282be75483608e96df4e6986d346e97180
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/12/2021
ms.locfileid: "59214245"
---
# <a name="responding-to-a-compromised-email-account"></a>손상된 전자 메일 계정에 응답

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**적용 대상**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Office 365용 Microsoft Defender 플랜 1 및 플랜 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

**요약** Microsoft 365에서 손상된 전자 메일 계정을 인식하고 응답하는 방법에 대해 알아봅니다.

## <a name="what-is-a-compromised-email-account-in-microsoft-365"></a>Microsoft 365에서 손상된 전자 메일 계정이란?

Microsoft 365 사서함, 데이터 및 기타 서비스에 대한 액세스는 자격 증명(예: 사용자 이름, 암호, PIN)을 사용하여 제어됩니다. 의도된 사용자가 아닌 사용자가 해당 자격 증명을 도용하면 도난된 자격 증명이 손상된 것으로 간주됩니다. 도난된 자격 증명으로 공격자는 원래 사용자로 로그인하여 불법적인 행동을 수행할 수 있습니다.

공격자는 도난된 자격 증명을 사용하여 사용자의 Microsoft 365 사서함, SharePoint 폴더 또는 사용자의 OneDrive에 있는 파일에 액세스할 수 있습니다. 흔히 볼 수 있는 한 가지 조치는 침입자가 전자 메일을 원래 사용자로 보내 조직 내부와 외부의 받는 사람에게 보내는 것입니다. 공격자가 외부 수신자에게 데이터를 메일로 보낼 때 이것을 데이터 유출이라고 합니다.

## <a name="symptoms-of-a-compromised-microsoft-email-account"></a>손상된 Microsoft 전자 메일 계정의 증상

사용자는 Microsoft 365 사서함에서 비정상적인 활동을 알아차리고 보고할 수 있습니다. 다음은 몇 가지 일반적인 증상입니다.

- 이메일 누락 또는 삭제와 같은 의심스러운 활동
- 다른 사용자는 보낸 사람의 **보낸 편지함** 폴더에 해당 메일이 없어도 손상된 계정의 메일을 받을 수 있습니다.
- 의도된 사용자 또는 관리자가 생성하지 않은 받은 편지함 규칙이 있는지 여부 이러한 규칙은 메일을 알 수 없는 주소로 자동 전달하거나 **노트**, **정크 메일** 또는 **RSS 구독** 폴더로 이동시킬 수 있습니다.
- 전체 주소 목록에서 사용자의 표시 이름을 변경할 수 있습니다.
- 사용자의 사서함에서 메일 보내기가 차단됩니다.
- Microsoft Outlook 또는 웹용 Outlook (이전까지의 Outlook Web App)에있는 보낸 편지함 또는 지운 편지함 폴더에는 "런던에 묶여 있습니다. 돈을 보내주세요."와 같은 일반적인 해킹된 계정 메시지가 들어있습니다.
- 이름, 전화 번호 또는 우편 번호와 같은 비정상적인 프로필 변경 사항이 업데이트됩니다.
- 여러 암호 변경과 같은 비정상적인 자격 증명 변경이 요구됩니다.
- 최근에 메일 전달이 추가되었습니다.
- 가짜 은행 업무 서명이나 처방약 서명과 같은 비정상적인 서명이 최근 추가되었습니다.

사용자가 위의 증상 중 하나를 보고하면 추가 조사를 수행해야 합니다. [Microsoft 365 Defender](https://security.microsoft.com) 및 Azure 포털은 손상되었을 가능성이 있는 것으로 의심되는 사용자 계정의 활동을 조사하는 데 유용한 도구를 제공합니다.

- **Microsoft 365 Defender 포털의 통합 감사 로그**: 의심스러운 활동이 발생한 직전부터 현재 날짜까지의 기간에 대한 결과를 필터링하여 의심되는 계정에 대한 모든 활동을 검토합니다. 검색 중에 활동을 필터링하지 마세요.

- **EAC에서의 관리자 감사 로그**: Exchange Online에서 Exchange 관리 센터(EAC)를 사용하여 관리자 감사 로그 항목을 검색하고 볼 수 있습니다. 관리자 감사 로그에는 관리 권한이 할당된 관리자와 사용자가 수행하는 특정 작업이 Exchange PowerShell cmdlet을 기준으로 기록됩니다. 관리자 감사 로그의 항목은 실행된 cmdlet, 사용된 매개 변수, cmdlet을 실행한 사용자 및 영향을 받은 개체에 대한 정보를 제공합니다.

- **Azure AD 포털의 Azure AD 로그인 로그 및 기타 위험 보고서**: 다음 열의 값을 검사합니다.
  - IP 주소 검토
  - 로그인 위치
  - 로그인 시간
  - 로그인 성공 또는 실패

## <a name="how-to-secure-and-restore-email-function-to-a-suspected-compromised-microsoft-365-account-and-mailbox"></a>손상된 Microsoft 365 계정 및 사서함으로 의심되는 전자 메일 기능을 보호하고 복원하는 방법

> [!VIDEO https://videoplayercdn.osi.office.net/hub/?csid=ux-cms-en-us-msoffice&uuid=RE2jvOb&AutoPlayVideo=false]

계정에 대한 액세스 권한을 회복한 후에도 공격자는 백도어 항목을 추가하여 계정을 다시 제어하기 시작할 수 있습니다.

계정에 대한 액세스 권한을 다시 얻으려면 다음 단계를 모두 수행해야 합니다. 계정 도용자가 계정 제어를 재개하지 않는지 확인하는 것은 빠를수록 좋습니다. 이 단계는 계정 도용자가 귀하의 계정에 추가한 백도어 항목을 제거하는 데 도움이 됩니다. 이러한 단계를 수행한 후에는 컴퓨터가 손상되지 않았는지 확인하기 위해 바이러스 검사를 실행하는 것이 좋습니다.

### <a name="step-1-reset-the-users-password"></a>1단계 사용자의 암호 재설정하기

[다른 사람을 위해 비즈니스 암호 재설정하기](../../admin/add-users/reset-passwords.md#reset-my-admin-password)의 절차를 따르세요. 

> [!IMPORTANT]
>
> - 이 시점에서 공격자가 여전히 사서함에 액세스할 수 있으므로 메일을 통해 의도한 사용자에게 새 암호를 보내지 않습니다.
>
> - 암호가 강하고 대문자, 소문자, 숫자 하나 이상 및 특수 문자가 하나 이상 포함되어 있는지 확인합니다.
>
> - 최근 5개의 암호를 다시 사용하지 마세요. 암호 기록 요구 사항을 통해 최근 암호를 다시 사용할 수는 있지만 공격자가 추측할 수 없는 암호를 선택해야 합니다.
>
> - 온-프레미스 ID가 Microsoft 365와 페더레이션된 경우 온-프레미스 암호를 변경해야 하며 관리자에게 손상 사실을 알려야 합니다.
>
> - 앱 암호를 업데이트해야 합니다. 사용자 계정 암호가 재설정되어도 앱 암호가 자동으로 취소되지 않습니다. 사용자가 직접 기존 앱 암호를 삭제하고 새 암호를 만들어야 합니다. 자세한 내용은 [추가 보안 확인 페이지에서 앱 암호 만들기 및 삭제](/azure/active-directory/user-help/multi-factor-authentication-end-user-app-passwords#create-and-delete-app-passwords-from-the-additional-security-verification-page)를 참조하세요.
>
> - 특히 관리자 권한이있는 계정의 경우에는 손상 방지를 위해 MFA(다중 요소 인증)를 사용하는 것이 좋습니다. MFA에 대한 자세한 내용은 [다단계 인증 설정하기로](../../admin/security-and-compliance/set-up-multi-factor-authentication.md) 이동하세요.

### <a name="step-2-remove-suspicious-email-forwarding-addresses"></a>2단계 의심스러운 메일 전달 주소 제거하기

1. <https://admin.microsoft.com>에서 Microsoft 365 관리 센터를 엽니다.

2. **사용자** \> **활성 사용자** 로 이동합니다. 해당 사용자 계정을 찾은 다음, 확인란을 선택하지 않고 사용자(행)를 선택 합니다.

3. 세부 정보 플라이아웃이 나타나면 **메일** 탭을 선택합니다.

4. **전자 메일 전달** 구역에 있는 값이 **적용된 경우**, **전자 메일 전달 관리** 를 클릭합니다. **전자 메일 전달 관리** 에서 플라이아웃이 표시되면, **이 사서함으로 모든 메일 전송** 을 취소하고 **변경 내용 저장** 을 클릭합니다. 

### <a name="step-3-disable-any-suspicious-inbox-rules"></a>3단계는 의심스러운 받은 편지함 규칙을 사용하지 않도록 설정하기

1. 웹용 Outlook을 사용하여 사용자의 사서함에 로그인합니다..

2. 기어 아이콘을 클릭하고 **메일** 을 클릭합니다.

3. **받은 편지함 및 비우기 규칙** 을 클릭하고 규칙을 검토합니다.

4. 의심러운 규칙을 사용하지 않도록 설정하거나 삭제합니다.

### <a name="step-4-unblock-the-user-from-sending-mail"></a>4단계 사용자 메일 보내기 차단을 해제하기

손상된 것으로 의심되는 사서함이 스팸 메일을 보내기 위해 불법적으로 사용된 경우 사서함이 메일을 보내지 못하도록 차단되었을 수 있습니다.

메일 보내기에서 사서함을 차단 해제하려면 [스팸 전자 메일를 보낸 후 제한된 사용자 포털에서 사용자 제거](removing-user-from-restricted-users-portal-after-spam.md)의 절차를 따르세요.

### <a name="step-5-optional-block-the-user-account-from-signing-in"></a>5단계 선택 사항 : 사용자 계정 로그인을 차단하기

> [!IMPORTANT]
> 액세스가 다시 활성화되어도 안전하다고 판단될 때까지 손상된 것으로 의심되는 계정이 로그인하지 못하도록 차단할 수 있습니다.

1. <https://admin.microsoft.com>에서 Microsoft 365 관리 센터를 열고 **사용자** \> **활성 사용자** 로 이동합니다.

2. 사용자 계정을 찾아 선택하고 ![아이콘 더 보기](../../media/ITPro-EAC-MoreOptionsIcon.png)를 클릭한 다음 **로그인 상태 편집** 을 선택합니다.

3. 표시 되는 **로그인 차단** 창에서 **해당 사용자 로그인 차단** 을 선택한 다음 **변경 내용 저장** 을 클릭합니다.

4. <https://admin.exchange.microsoft.com>에서 EAC(Exchange 관리 센터)를 열고 **수신자** \> **사서함** 으로 이동합니다.

5. 사용자를 찾아 선택합니다. 열리는 사서함 세부 정보 플라이아웃에서 다음 단계를 따릅니다.
   - **메일 앱** 섹션에서 토글을 오른쪽의 ![사용 안 함](../../media/scc-toggle-on.png)으로 이동하여 사용 가능한 모든 설정을 차단합니다.
     - **웹용 Outlook**
     - **Outlook 데스크톱(MAPI)**
     - **Exchange 웹 서비스**
     - **모바일(Exchange ActiveSync)**
     - **IMAP**
     - **POP3**

   작업을 마쳤으면 **저장** 을 클릭한 다음, **종료** 를 클릭합니다.

### <a name="step-6-optional-remove-the-suspected-compromised-account-from-all-administrative-role-groups"></a>6단계 선택 사항: 모든 관리 역할 그룹에서 손상된 것으로 의심되는 계정 제거하기

> [!NOTE]
> 관리 역할 그룹 구성원은 계정이 보안된 후에 복원할 수 있습니다.

1. 전역 관리자 계정으로 <https://admin.microsoft.com>에서 Microsoft 365 관리 센터 열고 다음 단계를 수행합니다.
   1. **사용자** \> **활성 사용자** 로 이동합니다.
   2. 사용자 계정을 찾아 선택하고 ![아이콘 더 보기](../../media/ITPro-EAC-MoreOptionsIcon.png)를 클릭한 다음 **역할 관리** 를 선택합니다.
   3. 계정에 할당된 모든 관리 역할을 제거합니다. 작업을 마쳤으면 **변경 내용 저장** 을 클릭합니다.

2. <https://security.microsoft.com>에서 Microsoft 365 Defender 포털을 열고 다음 단계를 수행합니다.
   1. **권한 및 역할** \> **전자 메일 및 공동 작업 역할** \> **역할** 로 이동합니다.
   2. **사용 권한** 페이지에서 목록에서 각 역할 그룹을 선택한 다음 표시되는 세부 정보 플라이아웃의 **구성원** 구역에서 사용자 계정을 찾습니다. 역할 그룹에 사용자 계정이 포함되어 있는 경우 다음 단계를 수행합니다.
      1. **구성원** 섹션에서 **편집** 을 클릭합니다.
      2. 표시되는 **구성원 선택 편집** 플라이아웃에서 **편집** 을 클릭합니다.
      3. 표시되는 **구성원 선택** 플라이아웃에서 **제거** 를 클릭합니다.
      4. 표시되는 플라이아웃에서 사용자 계정을 선택하고 **제거** 를 클릭합니다.

         작업을 마쳤으면 **완료**, **저장**, 그 다음 **종료** 를 클릭합니다.

3. <https://admin.exchange.microsoft.com>에서 EAC를 열고 다음 단계를 수행합니다.
   1. **역할** \>**관리자 역할** 을 선택합니다.
   2. **관리자 역할** 페이지에서 각 역할 그룹을 수동으로 선택하고, 세부 정보 창에서 **할당된 항목** 탭을 선택하여 사용자 계정을 확인합니다. 역할 그룹에 사용자 계정이 포함되어 있는 경우 다음 단계를 수행합니다.
      1. 사용자 계정을 선택합니다.
      2. 등록하려면 이 페이지 맨 위에 있는 ![삭제 아이콘.](../../media/m365-cc-sc-delete-icon.png).

         작업을 마쳤으면 **저장** 을 클릭합니다.

### <a name="step-7-optional-additional-precautionary-steps"></a>7단계 선택 사항 : 추가 예비 단계

1. 보낸된 항목을 확인합니다. 연락처 목록에 있는 사람들에게 계정이 손상되었다는 사실을 알려야할 수도 있습니다. 공격자가 돈을 요구했을 수 있습니다. 예를 들어, 다른 국가에 묶여 돈이 필요하거나, 공격자가 컴퓨터를 도용하기 위해 바이러스를 보낼 수 있습니다.

2. 이 Exchange 계정을 대체 메일 계정으로 사용한 다른 서비스가 손상되었을 수 있습니다. 먼저 Microsoft 365 구독에 대해 이러한 단계를 수행한 다음 다른 계정에 대해 이 단계를 수행합니다.

3. 전화번호 및 주소와 같은 연락처 정보가 정확한지 확인합니다.

## <a name="secure-microsoft-365-like-a-cybersecurity-pro"></a>사이버 보안 프로그램과 같은 Microsoft 365 보안

Microsoft 365 구독에는 데이터 및 사용자를 보호하는 데 사용할 수 있는 강력한 보안 기능이 함께 제공됩니다.  [Microsoft 365 보안 로드맵 - 최초 30일, 90일 및 그 이후의 최우선 순위](security-roadmap.md)를 사용하여 Microsoft에서 권장하는 Microsoft 365 테넌트 보안을 구현합니다.

- 처음 30일 이내에 수행 할 작업 이러한 작업들은 즉각적인 영향을 미치며 사용자에게 영향을 미치지 않습니다.
- 90일 이내에 수행할 작업입니다. 이러한 작업들은 계획하고 구현하는 데 다소 시간이 걸리지만 보안 태세를 갖추는 데 큰 도움이 됩니다.
- 90일을 초과합니다. 이러한 향상된 기능은 처음 90일간의 작업에서 구축됩니다.

## <a name="see-also"></a>참고 항목

- [Microsoft 365에서 Outlook 규칙 및 사용자 지정 양식 주입 공격 감지 및 재구성](detect-and-remediate-outlook-rules-forms-attack.md)
- [인터넷 범죄 불만 센터](https://www.ic3.gov/Home/Ransomware)
- [증권 거래 위원회 - “피싱” 사기](https://www.sec.gov/investor/pubs/phishing.htm)
- Microsoft와 관리자에게 스팸 전자 메일을 직접 보고하려면 [보고서 메시지 추가 기능을 사용하세요](https://support.microsoft.com/office/b5caa9f1-cdf3-4443-af8c-ff724ea719d2).
