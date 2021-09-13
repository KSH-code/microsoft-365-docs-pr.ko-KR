---
title: 사용자 지정 도메인에서 Microsoft 365 파일럿
f1.keywords:
- CSH
ms.author: pebaum
author: pebaum
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Priority
ms.collection:
- Adm_O365
ms.custom:
- admindeeplinkMAC
search.appverid:
- BCS160
- MET150
- MOE150
description: 두 개의 테스트 계정만 사용하여 사용자 지정 도메인의 전자 메일 기능을 Microsoft 365 사서함으로 시험해 보는 방법에 대해 알아봅니다.
ms.openlocfilehash: 6980480893e3e544a912edbe7d7da0993e781df2
ms.sourcegitcommit: d08fe0282be75483608e96df4e6986d346e97180
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/12/2021
ms.locfileid: "59186980"
---
# <a name="pilot-microsoft-365-from-my-custom-domain"></a>사용자 지정 도메인에서 Microsoft 365 파일럿

다음 요구 사항 및 제한으로 Microsoft 365를 시험해 볼 수 있습니다.

- 현재 전자 메일 공급자가 전자 메일 전달을 제공해야 합니다.

- Microsoft 365에서 이러한 레코드를 관리하는 것이 아니라 DNS 호스팅 공급자에서 Microsoft 365 DNS 레코드를 관리해야 합니다.

    자세한 내용은 [DNS 레코드를 추가하여 도메인 연결하기](../get-help-with-domains/create-dns-records-at-any-dns-hosting-provider.md)를 참조하세요.

- 다른 전자 메일 서버의 사용자에 대한 약속 있음/없음 정보를 사용할 수 없습니다.

- 관리자는 한 위치에서 모든 사용자 계정을 관리할 수 없습니다.

- 사용자가 Microsoft 365 스팸 필터링을 사용하지 못할 수 있습니다.

- 이 기능은 매우 적은 수의 사용자에게 권장되며 파일럿용 전자 메일 사용에만 적용됩니다.

## <a name="set-up-a-microsoft-365-pilot"></a>Microsoft 365 파일럿 설정하기

Microsoft 365 파일럿을 설정하려면 다음 단계를 따르세요.

### <a name="step-1-sign-in-to-the-microsoft-365-admin-center"></a>1단계: Microsoft 365 관리 센터에 로그인하기

1. 회사 또는 학교 계정으로 [Microsoft 365 관리자 센터](https://admin.microsoft.com)에 로그인합니다.

2. 왼쪽 탐색 창에서 **설정** > **도메인** 을 선택합니다.

### <a name="step-2-verify-that-you-own-the-domain-you-want-to-use"></a>2단계: 사용하려는 도메인을 소유했는지 확인하기

1. **도메인** 페이지에서 **도메인 추가** 를 선택합니다.

2. 상자에 도메인 이름을 입력하고 **이 도메인 사용** 을 선택한 다음 **계속** 을 선택합니다.

3. 전자 메일 및 인스턴트 메시징과 같이 도메인을 사용하여 테스트하려는 서비스를 선택합니다.

4. 도메인 **확인** 페이지에서 단계별 지침을 따르고 **확인** 을 선택합니다.

    DNS 변경 내용이 적용되기까지 몇 분에서 72시간까지 걸립니다.

    확인에 성공하면 DNS 레코드를 수정하라는 메시지가 표시됩니다.

### <a name="step-3-mark-the-domain-as-shared-in-exchange-online"></a>3단계: 도메인을 Exchange Online에서 공유됨으로 표시하기

1. Exchange 관리 센터의 **메일 흐름** 섹션에서 **허용 도메인** 을 선택한 다음 수정하려는 도메인을 선택합니다.

2. 창을 두 번 클릭하여 연 다음 **내부 릴레이** 를 선택합니다.

3. **저장** 을 선택합니다.

    이 설정이 적용되는 데 몇 분 정도가 필요할 수 있습니다. 

### <a name="step-4-unblock-the-existing-email-server-optional"></a>4단계: 기존 전자 메일 서버 차단 해제하기(선택 사항)

Microsoft 365에서는 스팸 방지를 위해 EOP(Exchange Online Protection)를 사용합니다. EOP가 현재 메일 서버에서 다량의 스팸 메일이 전달되는 것을 탐지하면 기존 메일 서버를 차단할 수 있습니다. 다른 전자 메일 공급자의 스팸 방지를 신뢰하는 경우 Microsoft 365에서 서버 차단을 해제할 수 있습니다.

> [!NOTE]
> 기존 전자 메일 서버 차단을 해제하면 원래 서버를 통해 들어오는 모든 스팸이 Microsoft 365 사서함으로 전달되며, Microsoft 365에서 스팸을 얼마나 잘 방지하는지 평가할 수 없습니다.

1. Exchange 관리 센터 탐색 창에서 **보호** 를 선택한 다음 **연결 필터** 를 선택합니다.

2. **IP 허용 목록** 에서 **+** 를 선택하고 현재 전자 메일 공급자의 메일 서버 IP 주소를 추가합니다.

### <a name="step-5-create-user-accounts-and-set-the-primary-reply-to-address"></a>5단계: 사용자 계정 만들기 및 기본 회신 주소 설정하기

1. Microsoft 365 관리 센터 왼쪽 탐색에서 **사용자** > <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">**활성 사용자**</a>를 선택합니다.

2. 두 명의 기존 사용자를 추가하여 두 개의 테스트 계정을 만듭니다.

    각 계정에 대해 **+사용자 추가** 를 선택하고 테스트하려는 암호 방법을 포함하여 필요한 정보를 입력합니다.

    사용자의 전자 메일을 동일하게 유지하려면 **사용자 이름** 필드가 사용자의 현재 전자 메일 주소와 일치해야 합니다.

3. 적절한 라이선스를 선택하고 **다음** 을 클릭한 다음 **추가 완료** 를 클릭합니다.

4. **사용자 이름** 옆의 드롭다운 목록에서 사용자 지정 도메인 이름을 선택합니다.

5. **만들기** > **닫기** 를 선택합니다.

### <a name="step-6-configure-mail-to-flow-from-microsoft-365-or-office-365-to-email-server"></a>6단계: **Microsoft 365 또는 Office 365에서 전자 메일 서버로 전송되는 메일 구성하기

해당 작업에는 두 가지 단계가 있습니다.

1. Microsoft 365 또는 Office 365 환경 구성

2. Microsoft 365 또는 Office 365에서 전자 메일 서버로 커넥터 설정

### <a name="1-configure-your-microsoft-365-or-office-365-environment"></a>1. Microsoft 365 또는 Office 365 환경 구성

Microsoft 365 또는 Office 365에서 다음 사항을 완료했는지 확인합니다.

1. 커넥터를 설정하려면 시작하기 전에 할당된 사용 권한이 있어야 합니다. 필요한 사용 권한을 확인하려면 [Exchange Online의 기능 사용 권한](/exchange/permissions-exo/feature-permissions) 항목에서 Microsoft 365 및 Office 365 커넥터 항목을 참조하세요.

2. EOP 또는 Exchange Online이 전자 메일 서버에서 인터넷으로 전자 메일을 릴레이하도록 하려면 다음 작업 중 하나를 수행합니다.

   - Microsoft 365 또는 Office 365의 허용 도메인과 일치하는 주체 이름으로 구성된 인증서를 사용합니다. 인증서의 일반 이름 또는 주체 대체 이름은 조직에 대한 기본 SMTP 도메인과 일치시키는 것이 좋습니다. 자세한 내용은 [온-프레미스 전자 메일 환경의 필수 구성 요소](/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/set-up-connectors-to-route-mail#prerequisites-for-your-on-premises-email-environment)를 참조하세요.

   -또는-

   - 조직의 모든 보낸 사람 도메인과 하위 도메인이 Microsoft 365 또는 Office 365에서 허용 도메인으로 구성되어 있는지 확인합니다.

   허용 도메인 정의에 대한 자세한 내용은 [Exchange Online에서 허용 도메인 관리](/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains) 및 [Exchange Online에서 하위 도메인에 대한 메일 흐름 사용](/exchange/mail-flow-best-practices/manage-accepted-domains/enable-mail-flow-for-subdomains)을 참조하세요.

3. 메일 흐름 규칙(전송 규칙)을 사용할지 또는 도메인 이름을 사용할지 결정하여 Microsoft 365 또는 Office 365에서 전자 메일 서버로 메일을 전송합니다. 대부분의 기업은 모든 허용 도메인에 대한 메일을 전송하도록 선택합니다. 자세한 내용은 [시나리오: Exchange Online에서 조건부 메일 라우팅](/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/conditional-mail-routing)을 참조하세요.

> [!NOTE]
> [Exchange Online에서 메일 흐름 규칙 동작](/exchange/security-and-compliance/mail-flow-rules/mail-flow-rule-actions)에 설명된 대로 메일 흐름 규칙을 설정할 수 있습니다. 예를 들어 현재 메일이 메일 그룹을 통해 여러 사이트로 직접 전송되는 경우 커넥터와 함께 메일 흐름 규칙을 사용할 수 있습니다.

### <a name="2-set-up-a-connector-from-microsoft-365-or-office-365-to-your-email-server"></a>2. Microsoft 365 또는 Office 365에서 전자 메일 서버로 커넥터 설정

Microsoft 365 또는 Office 365에서 커넥터를 만들려면 **관리** 를 클릭한 다음 **Exchange** 를 클릭하여 Exchange 관리 센터로 이동합니다. 그 다음 **메일 흐름**, **커넥터** 를 차례로 클릭합니다.

마법사를 사용하여 커넥터를 설정합니다.

마법사를 시작하려면 더하기 기호 **+** 을(를) 클릭합니다. 첫 번째 화면에서 Office 365 **에서** 및 조직 메일 서버 **로** 를 선택합니다.

**다음** 을 클릭하고 마법사의 지시를 따릅니다. 추가 정보가 필요한 경우 **도움말** 또는 **추가 정보** 링크를 클릭합니다. 마법사가 설정 과정을 안내합니다. 완료되면 커넥터 유효성 검사가 실행되는지 확인합니다. 커넥터 유효성 검사가 실행되지 않는 경우 자세한 내용을 보려면 표시된 메시지를 두 번 클릭하고 문제 해결을 위해 [커넥터 유효성 검사](/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/validate-connectors)를 참조하세요.



### <a name="step-7-update-dns-records-at-your-dns-hosting-provider"></a>7단계: DNS 호스팅 공급자에서 DNS 레코드 업데이트하기

DNS 호스팅 공급자의 웹 사이트에 로그인하고 [DNS 레코드를 추가하여 도메인 연결하기](../get-help-with-domains/create-dns-records-at-any-dns-hosting-provider.md)의 지침을 따릅니다.

**다음 두 가지 예외를 수행합니다.**

- 새 MX 레코드를 만들거나 기존 MX 레코드를 변경하지 않습니다.

- 이전 전자 메일 공급자에 대해 SPF(Sender Policy Framework) 레코드가 이미 있는 경우에는 Exchange용 SPF(TXT) 레코드를 새로 만드는 대신 현재 TXT 레코드에 "include:spf.protection.outlook.com"을 추가합니다.

    예를 들어 “v=spf1 mx include:adatum.com include:spf.protection.outlook.com ~all”과 같이 추가합니다.

    아직 SPF 레코드가 없는 경우에는 Microsoft 365에서 추천하는 레코드를 수정하여 현재 전자 메일 공급자의 도메인을 포함하고 spf.protection.outlook.com을 추가합니다. 이렇게 하면 두 전자 메일 시스템에서 발송되는 메시지에 대한 권한이 승인됩니다.

### <a name="step-8-set-up-email-forwarding-at-your-current-provider"></a>8단계: 현재 공급자에서 전자 메일 전달 설정하기

현재 전자 메일 공급자에서 사용자의 전자 메일 계정이 onmicrosoft.com 도메인으로 전달되도록 설정합니다.

- 사용자 A 사서함을 usera@yourcompany.onmicrosoft.com으로 전달

- 사용자 B 사서함을 userb@yourcompany.onmicrosoft.com으로 전달

이 단계를 완료하면 usera@yourcompany.com 및 userb@yourcompany.com으로 전송된 모든 전자 메일을 Microsoft 365에서 볼 수 있습니다.

> [!NOTE]
> 전자 메일 전달을 설정하는 정확한 단계에 대해서는 현재 전자 메일 공급자에게 문의하세요.<br/>
> 현재 전자 메일 공급자에 메시지 복사본을 유지할 필요가 없습니다.<br/>
> 대부분의 공급자는 보낸 사람의 회신 주소는 그대로 유지하고 전자 메일을 전달하므로, 회신은 원래 보낸 사람에게 전송됩니다.

### <a name="step-9-test-mail-flow"></a>9단계: 메일 흐름 테스트하기

1. 사용자 A의 자격 증명을 사용하여 Outlook Web App에 로그인합니다. 

2. 다음 테스트를 수행합니다.

    - 예를 들어 사용자 B에게 전자 메일을 보내 로컬 Microsoft 전자 메일을 테스트합니다. 전자 메일은 즉시 전달됩니다. 이 시나리오에서는 Microsoft 365 사서함이 로컬이기 때문에 메시지가 원래 서버에서 사용자 B의 사서함으로 라우팅되지 않습니다.

    - 예를 들어 사용자 C에게 전자 메일을 보내 기존 전자 메일 시스템에서 전자 메일을 사용자에게 테스트합니다. 전자 메일은 원본 메일 서버에서 사용자 C의 사서함으로 배달됩니다.

    - 전달이 외부 계정에서, 기존 전자 메일 시스템의 직원 전자 메일 계정에서 제대로 설정되었는지 확인합니다. 예를 들어 사용자 C의 원래 서버 계정 또는 Hotmail 계정에서 사용자 A에게 전자 메일을 보내고 사용자 A의 Microsoft 365 사서함에 도착하는지 확인합니다.

### <a name="step-10-move-mailbox-contents"></a>10단계: 사서함 콘텐츠 이동하기

두 명의 테스트 사용자만 이동하고 사용자 A와 사용자 B가 모두 Outlook을 사용하고 있으므로, 새 Outlook 프로필에서 이전 .PST 파일을 열고 메시지, 일정 항목, 연락처 등을 복사하여 전자 메일을 이동할 수 있습니다. 자세한 내용은 [Outlook .pst 파일에서 전자 메일, 연락처 및 일정 가져오기](https://support.microsoft.com/office/import-email-contacts-and-calendar-from-an-outlook-pst-file-431a8e9a-f99f-4d5f-ae48-ded54b3440ac)를 참조하세요.

콘텐츠를 Microsoft 365 사서함의 적절한 위치로 가져온 후에는 모든 장치에서 어디서나 해당 항목에 액세스할 수 있습니다.
