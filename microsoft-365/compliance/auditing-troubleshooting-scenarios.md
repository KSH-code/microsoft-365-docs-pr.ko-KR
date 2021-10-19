---
title: 일반적인 시나리오 문제를 해결하려면 감사 로그를 검색합니다.
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: troubleshooting
ms.service: O365-seccomp
ms.localizationpriority: medium
ms.collection:
- Strat_O365_IP
- M365-security-compliance
search.appverid:
- MET150
- MOE150
ms.custom:
- seo-marvel-apr2020
description: 전자 메일 계정에 대한 일반적인 Microsoft 365 문제를 해결하는 데 도움이 되는 감사 로그 검색 도구를 사용하는 방법을 배워야 합니다.
ms.openlocfilehash: 0ac1bbb2ff0a9c09b661abd8f60fd960d33fd774
ms.sourcegitcommit: 43adb0d91af234c34e22d450a9c1d26aa745c2ca
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/19/2021
ms.locfileid: "60478580"
---
# <a name="search-the-audit-log-to-investigate-common-support-issues"></a>감사 로그를 검색하여 일반적인 지원 문제 조사

이 문서에서는 감사 로그 검색 도구를 사용하여 일반적인 지원 문제를 조사하는 데 도움이 되는 방법을 설명합니다. 여기에는 감사 로그를 사용하여 다음을 할 수 있습니다.

- 손상된 계정에 액세스하는 데 사용되는 컴퓨터의 IP 주소 찾기
- 사서함에 대해 전자 메일 전달을 설정하는 사용자 결정
- 사용자가 사서함에서 전자 메일 항목을 삭제한지 확인
- 사용자가 받은 편지함 규칙을 만들지 확인
- 조직 외부의 사용자가 성공적으로 로그인한 이유를 조사합니다.
- 비 E5 라이선스가 있는 사용자가 수행한 사서함 활동 검색
- 위임 사용자가 수행한 사서함 활동 검색

## <a name="using-the-audit-log-search-tool"></a>감사 로그 검색 도구 사용

이 문서에 설명된 각 문제 해결 시나리오는 이 문서의 감사 로그 검색 도구를 Microsoft 365 규정 준수 센터. 이 섹션에서는 감사 로그를 검색하는 데 필요한 사용 권한을 나열하고 감사 로그 검색에 액세스하고 실행하기 위한 단계를 설명합니다. 각 시나리오 섹션에서는 감사 로그 검색 쿼리를 구성하는 방법과 검색 조건과 일치하는 감사 레코드의 세부 정보에서 찾을 대상에 대해 설명합니다.

### <a name="permissions-required-to-use-the-audit-log-search-tool"></a>감사 로그 검색 도구를 사용하는 데 필요한 사용 권한

감사 로그를 검색하려면 View-Only 감사 로그 또는 감사 Exchange Online 역할이 할당되어야 합니다. 기본적으로 이러한 역할은 Exchange 관리 센터의 **사용 권한** 페이지에서 규정 준수 관리 및 조직 관리 역할 그룹에 할당됩니다. Office 365 및 Microsoft 365의 전역 관리자는 자동으로 Exchange Online 서비스에서 조직 관리 역할 그룹의 구성원이 됩니다. 자세한 내용은 [Exchange Online에서 역할 그룹 관리](/Exchange/permissions-exo/role-groups)를 참조하세요.

### <a name="running-audit-log-searches"></a>감사 로그 검색 실행

이 섹션에서는 감사 로그 검색을 만들고 실행하기 위한 기본에 대해 설명합니다. 이 문서의 각 문제 해결 시나리오에 대한 시작점으로 이러한 지침을 사용하세요. 자세한 단계별 지침은 감사 로그 [검색을 참조하세요.](search-the-audit-log-in-security-and-compliance.md#step-1-run-an-audit-log-search)

1. <https://compliance.microsoft.com/auditlogsearch>으로 이동하여 회사 또는 학교 계정을 사용하여 로그인합니다.
  
    **감사** 페이지가 표시됩니다.
  
    ![조건을 구성한 다음 검색을 선택하여 검색을 실행합니다.](../media/AuditLogSearchPage1.png)
  
2. 다음 검색 조건을 구성할 수 있습니다. 이 문서의 각 문제 해결 시나리오에서는 이러한 필드를 구성하기 위한 특정 지침을 권장합니다.
  
   a. **시작 날짜** 및 **종료 날짜:** 날짜 및 시간 범위를 선택하여 해당 기간 내에 발생한 이벤트를 표시합니다. 기본적으로 지난 7일이 선택됩니다. 날짜 및 시간은 UTC(협정 세계시) 형식으로 표시됩니다. 지정할 수 있는 최대 날짜 범위는 90일입니다.

   b. **활동:** 검색할 수 있는 활동을 표시하려면 드롭다운 목록을 선택합니다. 검색을 실행하면 선택한 활동에 대한 감사 기록만 표시됩니다. 모든 **활동에 대한 결과 표시를 선택하면** 다른 검색 조건을 충족하는 모든 활동에 대한 결과가 표시됩니다. 또한 일부 문제 해결 시나리오에서는 이 필드를 비워 두어야 합니다.
  
    c. **사용자:** 이 상자를 클릭한 다음 검색 결과를 표시할 사용자를 한명 이상 선택합니다. 이 상자에서 선택한 사용자가 수행한 선택한 활동에 대한 감사 레코드가 결과 목록에 표시됩니다. 조직의 모든 사용자(및 서비스 계정)에 대한 항목을 반환하려면 이 상자를 비워 둡니다.
  
    d. **파일, 폴더 또는 사이트:** 파일 또는 폴더 이름을 일부 또는 모두 입력하여 지정된 키워드가 포함된 폴더 파일과 관련된 활동을 검색합니다. 파일 또는 폴더의 URL을 지정할 수도 있습니다. URL을 사용하는 경우 전체 URL 경로를 입력해야 합니다. 또는 URL의 일부만 입력하는 경우 특수 문자나 공백을 포함하지 않습니다. 조직의 모든 파일 및 폴더에 대한 항목을 반환하려면 이 상자를 비워 둡니다. 이 필드는 이 문서의 모든 문제 해결 시나리오에서 비어 있습니다.
  
3. 검색을 **선택하여** 검색 조건을 사용하여 검색을 실행합니다.
  
    검색 결과가 로드되고 몇 분 후에 감사 로그 검색 도구의 페이지에 표시됩니다. 이 문서의 각 섹션에서는 특정 문제 해결 시나리오의 컨텍스트에서 검색할 수 있는 방법에 대한 지침을 제공합니다.

    감사 로그 검색 결과를 보고 내보내는 데 대한 자세한 내용은 다음을 참조하세요.

    - [검색 결과 보기](search-the-audit-log-in-security-and-compliance.md#step-2-view-the-search-results)
  
    - [검색 결과 내보내기](search-the-audit-log-in-security-and-compliance.md#step-3-export-the-search-results-to-a-file)

## <a name="find-the-ip-address-of-the-computer-used-to-access-a-compromised-account"></a>손상된 계정에 액세스하는 데 사용되는 컴퓨터의 IP 주소 찾기

사용자가 수행한 활동에 해당하는 IP 주소는 대부분의 감사 레코드에 포함됩니다. 사용되는 클라이언트에 대한 정보도 감사 레코드에 포함됩니다.

이 시나리오에 대한 감사 로그 검색 쿼리를 구성하는 방법에는 다음이 있습니다.

**활동:** 사례와 관련된 경우 검색할 특정 활동을 선택합니다. 손상된 계정 문제를 해결하려면 사서함  활동에서 사서함 활동에 **로그인한 Exchange 선택합니다.** 그러면 사서함에 로그인할 때 사용된 IP 주소를 보여 주는 감사 레코드가 반환됩니다. 그렇지 않은 경우 이 필드를 비워 두면 모든 활동에 대한 감사 레코드를 반환할 수 있습니다. 

> [!TIP]
> 이 필드를 비워 두면 **UserLoggedIn** 활동이 반환됩니다. 이 활동은 Azure Active Directory 사용자 계정에 로그인했다는 의미입니다. 검색 결과에서 필터링을 사용하여 **UserLoggedIn** 감사 레코드를 표시합니다.

**시작 날짜** 및 **종료 날짜:** 조사에 적용되는 날짜 범위를 선택합니다.

**사용자:** 손상된 계정을 조사하는 경우 해당 계정이 손상된 사용자를 선택합니다. 그러면 해당 사용자 계정이 수행한 활동에 대한 감사 레코드가 반환됩니다.

**파일, 폴더 또는 사이트:** 이 필드는 비워 두십시오.

검색을 실행하면 각 활동에 대한 IP 주소가 검색 결과의 **IP 주소** 열에 표시됩니다. 플라이아웃 페이지에서 자세한 정보를 확인하려면 검색 결과에서 레코드를 선택합니다.

## <a name="determine-who-set-up-email-forwarding-for-a-mailbox"></a>사서함에 대해 전자 메일 전달을 설정하는 사용자 결정

사서함에 대해 전자 메일 전달을 구성하면 사서함으로 전송된 전자 메일 메시지가 다른 사서함으로 전달됩니다. 메시지를 조직 내부 또는 외부의 사용자에게 전달할 수 있습니다. 사서함에 전자 메일 전달이 설정되어 있는 경우 사용되는 Exchange Online cmdlet은 **Set-Mailbox 입니다.**

이 시나리오에 대한 감사 로그 검색 쿼리를 구성하는 방법에는 다음이 있습니다.

**활동:** 검색에서 모든 활동에 대한 감사 레코드를 반환할 수 있도록 이 필드를 비워 두십시오. 이 설정은 **Set-Mailbox** cmdlet과 관련된 모든 감사 레코드를 반환하는 데 필요합니다.

**시작 날짜** 및 **종료 날짜:** 조사에 적용되는 날짜 범위를 선택합니다.

**사용자:** 특정 사용자에 대한 전자 메일 전달 문제를 조사하지 않는 한 이 필드를 비워 두십시오. 이렇게 하면 모든 사용자에 대해 전자 메일 전달이 설정되어 있는지 확인할 수 있습니다.

**파일, 폴더 또는 사이트:** 이 필드는 비워 두십시오.

검색을 실행한 후 검색 **결과** 페이지에서 결과 필터링을 선택합니다. 작업 열 헤더 아래에 **있는** 상자에 **Set-Mailbox** cmdlet과 관련된 감사 레코드만 표시될 수 있도록 **Set-Mailbox를** 입력합니다.

![감사 로그 검색 결과 필터링](../media/emailforwarding1.png)

이제 각 감사 레코드의 세부 정보를 확인하여 활동이 전자 메일 전달과 관련이 있는지 여부를 결정해야 합니다. 감사 레코드를 선택하여 **세부** 정보 플라이아웃 페이지를 표시한 다음 추가 정보를 **선택합니다.** 다음 스크린샷 및 설명은 사서함에 전자 메일 전달이 설정되어 있는 정보를 강조합니다.

![감사 레코드의 세부 정보입니다.](../media/emailforwarding2.png)

a. **ObjectId 필드에는** 전자 메일 전달이 설정된 사서함의 별칭이 표시됩니다. 이 사서함은 검색 결과 페이지의 **항목** 열에도 표시됩니다.

b. 매개 **변수 필드에서** *ForwardingSmtpAddress* 값은 전자 메일 전달이 사서함에 설정되어 있는 것입니다. 이 예에서는 메일이 조직 외부에 있는 mike@contoso.com 주소로 alpinehouse.onmicrosoft.com 합니다.

c. *DeliverToMailboxAndForward* 매개 변수의 *True* 값은 메시지 복사본이 sarad@alpinehouse.onmicrosoft.com 전달되어  *ForwardingSmtpAddress* 매개 변수에 지정된 전자 메일 주소로 전달됩니다. 이 예에서는 이 mike@contoso.com. *DeliverToMailboxAndForward* 매개 변수의 값이 *False로* 설정된 경우 *ForwardingSmtpAddress* 매개 변수에 지정된 주소로만 전자 메일이 전달됩니다. ObjectId 필드에 지정된 사서함으로 **배달되지** 않습니다.

d. **UserId 필드는** **ObjectId** 필드에 지정된 사서함에 대해 전자 메일 전달을 설정한 사용자를 나타냅니다. 이 사용자는 검색 결과  페이지의 사용자 열에도 표시됩니다. 이 경우 사서함 소유자가 사서함에 전자 메일 전달을 설정한 것으로 나타납니다.

사서함에서 전자 메일 전달을 설정하지 말아야 한다고 결정한 경우 PowerShell에서 다음 명령을 실행하여 전자 Exchange Online 있습니다.

```powershell
Set-Mailbox <mailbox alias> -ForwardingSmtpAddress $null 
```

전자 메일 전달과 관련된 매개 변수에 대한 자세한 내용은 [Set-Mailbox 문서를 참조하십시오.](/powershell/module/exchange/set-mailbox)

## <a name="determine-if-a-user-deleted-email-items"></a>사용자가 전자 메일 항목을 삭제한지 확인

2019년 1월부터 Microsoft는 모든 조직 및 Microsoft 조직에 대해 기본적으로 Office 365 로깅을 설정하고 있습니다. 즉, 사서함 소유자가 수행한 특정 작업이 자동으로 기록되며 사서함 감사 로그에서 해당 사서함 감사 레코드를 검색할 때 해당 사서함 감사 레코드를 사용할 수 있습니다. 사서함 감사를 기본적으로 설정하기 전에 조직의 모든 사용자 사서함에 대해 수동으로 사용하도록 설정해야 했습니다. 

기본적으로 기록되는 사서함 작업에는 사서함 소유자가 수행한 SoftDelete 및 HardDelete 사서함 작업이 포함됩니다. 즉, 다음 단계를 사용하여 감사 로그에서 삭제된 전자 메일 항목과 관련된 이벤트를 검색할 수 있습니다. 기본적으로 사서함 감사에 대한 자세한 내용은 사서함 감사 [관리를 참조하세요.](enable-mailbox-auditing.md)

이 시나리오에 대한 감사 로그 검색 쿼리를 구성하는 방법에는 다음이 있습니다.

**활동:** 사서함 **Exchange 아래에서** 다음 활동 중 하나 또는 둘 다를 선택합니다.

- **지우기 항목 폴더에서 삭제된 메시지:** 이 활동은 **SoftDelete** 사서함 감사 작업과 해당합니다. 이 활동은 사용자가 항목을 선택하고 Shift+Delete를 눌러 항목을 영구적으로 삭제할 **때도 기록됩니다.** 항목을 영구적으로 삭제한 후 사용자는 삭제된 항목 보존 기간이 만료될 때까지 복구할 수 있습니다.

- **사서함에서 메시지 제거:** 이 활동은 **HardDelete** 사서함 감사 작업에 해당합니다. 사용자가 복구 가능한 항목 폴더에서 항목을 제거하면 기록됩니다. 관리자는 보안 및 준수 센터의 콘텐츠 검색 도구를 사용하여 삭제된 항목 보존 기간이 만료되거나 사용자 사서함이 보류 중일 때까지 제거된 항목을 검색하고 복구할 수 있습니다.

**시작 날짜** 및 **종료 날짜:** 조사에 적용되는 날짜 범위를 선택합니다.

**사용자:** 이 필드에서 사용자를 선택하면 감사 로그 검색 도구는 지정한 사용자가 삭제한 전자 메일 항목(SoftDeleted 또는 HardDeleted)에 대한 감사 레코드를 반환합니다. 경우에 따라 전자 메일을 삭제하는 사용자가 사서함 소유자가 아 않을 수 있습니다.

**파일, 폴더 또는 사이트:** 이 필드는 비워 두십시오.

검색을 실행한 후 검색 결과를 필터링하여 소프트 삭제된 항목 또는 영구 삭제된 항목에 대한 감사 레코드를 표시할 수 있습니다. 감사 레코드를 선택하여 **세부** 정보 플라이아웃 페이지를 표시한 다음 추가 정보를 **선택합니다.** 제목 줄 및 삭제된 항목의 위치와 같은 삭제된 항목에 대한 추가 정보가 **AffectedItems** 필드에 표시됩니다. 다음 스크린샷은 소프트 삭제된 항목 및 영구 삭제된 항목의 **AffectedItems** 필드 예를 보여 주는 스크린샷입니다.

**소프트 삭제된 항목에 대한 AffectedItems 필드의 예**

![소프트 삭제된 항목에 대한 감사 레코드입니다.](../media/softdeleteditem.png)

**영구 삭제된 항목에 대한 AffectedItems 필드의 예**

![영구 삭제된 전자 메일 항목에 대한 감사 레코드입니다.](../media/harddeleteditem.png)

### <a name="recover-deleted-email-items"></a>삭제된 전자 메일 항목 복구

사용자는 삭제된 항목 보존 기간이 만료되지 않은 경우 소프트 삭제된 항목을 복구할 수 있습니다. Exchange Online 삭제된 항목의 기본 보존 기간은 14일이지만 관리자는 이 설정을 최대 30일로 늘일 수 있습니다. 삭제된 항목 [복구에](https://support.office.com/article/Recover-deleted-items-or-email-in-Outlook-Web-App-C3D8FC15-EEEF-4F1C-81DF-E27964B7EDD4) 대한 지침은 웹용 Outlook 항목 또는 전자 메일 복구 문서를 안내합니다.

앞서 설명한 것 처럼 관리자는 삭제된 항목 보존 기간이 만료되지 않은 경우 또는 사서함이 보류 상태인 경우 영구 삭제된 항목을 복구할 수 있습니다. 이 경우 보존 기간이 만료될 때까지 항목이 보관됩니다. 콘텐츠 검색을 실행하면 복구 가능한 항목 폴더의 영구 삭제된 항목 및 영구 삭제된 항목이 검색 쿼리와 일치하는 경우 검색 결과에 반환됩니다. 콘텐츠 검색을 실행하는 데 대한 자세한 내용은 에서 [콘텐츠 검색을 Office 365.](content-search.md)

> [!TIP]
> 삭제된 전자 메일 항목을 검색하려면 감사 레코드의 **AffectedItems** 필드에 표시되는 제목 줄 전체 또는 일부를 검색합니다.

## <a name="determine-if-a-user-created-an-inbox-rule"></a>사용자가 받은 편지함 규칙을 만들지 확인

사용자가 Exchange Online 사서함에 대한 받은 편지함 규칙을 만들면 해당 감사 레코드가 감사 로그에 저장됩니다. 받은 편지함 규칙에 대한 자세한 내용은 다음을 참조하세요.

- [받은 편지함 규칙의 웹용 Outlook](https://support.office.com/article/use-inbox-rules-in-outlook-on-the-web-8400435c-f14e-4272-9004-1548bb1848f2)
- [규칙을 사용하여 Outlook 전자 메일 메시지 관리](https://support.office.com/article/Manage-email-messages-by-using-rules-C24F5DEA-9465-4DF4-AD17-A50704D66C59)

이 시나리오에 대한 감사 로그 검색 쿼리를 구성하는 방법에는 다음이 있습니다.

**활동:** 사서함 **Exchange 아래에서** 다음 활동 중 하나 또는 둘 다를 선택합니다.

- **New-InboxRule 에서 새 받은 편지함 규칙을 Outlook Web App.** 이 활동은 웹앱 또는 PowerShell을 사용하여 받은 편지함 규칙을 만들 때 Outlook 감사 Exchange Online 반환합니다.

- **클라이언트에서 받은 편지함 Outlook 업데이트되었습니다.** 이 활동은 데스크톱 클라이언트를 사용하여 받은 편지함 규칙을 만들거나 수정하거나 제거할 때 감사 Outlook 반환합니다.

**시작 날짜** 및 **종료 날짜:** 조사에 적용되는 날짜 범위를 선택합니다.

**사용자:** 특정 사용자를 조사하지 않는 한 이 필드는 비워 두십시오. 이렇게 하면 사용자가 설정한 새 받은 편지함 규칙을 식별할 수 있습니다.

**파일, 폴더 또는 사이트:** 이 필드는 비워 두십시오.

검색을 실행하면 이 활동에 대한 모든 감사 레코드가 검색 결과에 표시됩니다. 감사 레코드를 선택하여 **세부** 정보 플라이아웃 페이지를 표시한 다음 추가 정보를 **선택합니다.** 받은 편지함 규칙 설정에 대한 정보가 매개 변수 **필드에** 표시됩니다. 다음 스크린샷 및 설명은 받은 편지함 규칙에 대한 정보를 강조합니다.

![새 받은 편지함 규칙에 대한 감사 레코드입니다.](../media/NewInboxRuleRecord.png)

a. **ObjectId 필드에** 받은 편지함 규칙의 전체 이름이 표시됩니다. 이 이름에는 사용자 사서함의 별칭(예: SaraD)과 받은 편지함 규칙의 이름(예: "관리자로부터 메시지 이동")이 포함됩니다.

b. 매개 **변수 필드에** 받은 편지함 규칙의 조건이 표시됩니다. 이 예제에서는 From 매개 변수에 의해 *조건이 지정됩니다.* From 매개 변수에 *정의된 값은* 받은 편지함 규칙이 사용자가 보낸 전자 메일에 admin@alpinehouse.onmicrosoft.com. 받은 편지함 규칙의 조건을 정의하는 데 사용할 수 있는 매개 변수의 전체 목록은 [New-InboxRule](/powershell/module/exchange/new-inboxrule) 문서를 참조하세요.

c. *MoveToFolder* 매개 변수는 받은 편지함 규칙에 대한 작업을 지정합니다. 이 예에서는 사용자로부터 받은 admin@alpinehouse.onmicrosoft.com *AdminSearch라는 폴더로 이동됩니다.* 받은 편지함 규칙의 작업을 정의하는 데 사용할 수 있는 전체 매개 변수 목록은 [New-InboxRule](/powershell/module/exchange/new-inboxrule) 문서를 참조하세요.

d. **UserId 필드는** **ObjectId** 필드에 지정된 받은 편지함 규칙을 만든 사용자를 나타냅니다. 이 사용자는 검색 결과  페이지의 사용자 열에도 표시됩니다.

## <a name="investigate-why-there-was-a-successful-login-by-a-user-outside-your-organization"></a>조직 외부의 사용자가 성공적으로 로그인한 이유를 조사합니다.

감사 로그에서 감사 레코드를 검토할 때 외부 사용자가 조직에 로그인하여 인증을 Azure Active Directory 레코드가 표시될 수 있습니다. 예를 들어 관리자의 contoso.onmicrosoft.com 다른 조직의 사용자(예: fabrikam.onmicrosoft.com)가 조직에 성공적으로 로그인했다는 감사 레코드가 contoso.onmicrosoft.com. 마찬가지로 조직에 성공적으로 로그인된 Outlook.com 또는 Live.com MSA(Microsoft 계정)가 있는 사용자를 나타내는 감사 레코드가 표시될 수 있습니다. 이러한 경우 감사된 활동은 **사용자 로그인 입니다.** 

이것은 의도적으로 설계된 동작입니다. Azure Active Directory(Azure AD)를 사용하면 외부 사용자가  조직의 SharePoint 사이트 또는 OneDrive 액세스하는 경우 통과 인증이라고 하는 것을 허용합니다. 외부 사용자가 이 작업을 하도록 할 때 자격 증명을 입력하라는 메시지가 표시 됩니다. Azure AD는 자격 증명을 사용하여 사용자를 인증합니다. 즉, Azure AD만 사용자가 신원을 확인한 것입니다. Azure AD가 사용자를 인증한 결과 감사 레코드에 로그인이 성공한 것입니다. 로그인이 성공했다고 해서 사용자가 조직에서 리소스에 액세스하거나 다른 작업을 수행할 수 있는 것은 아니며, Azure AD에서 사용자를 인증한 것만 나타냅니다. 통과 사용자가 SharePoint 또는 OneDrive 리소스에 액세스하려면 조직의 사용자가 공유 초대 메일 또는 익명 공유 링크를 보내 외부 사용자와 리소스를 명시적으로 공유해야 합니다. 

> [!NOTE]
> Azure AD는 SharePoint Online 및 비즈니스용 OneDrive 자사 응용 프로그램에만 통과 인증을 비즈니스용 OneDrive. 다른 타사 응용 프로그램에는 허용되지 않습니다.

다음은 통과 인증의 결과인 로그인한 사용자에 대한  감사 레코드의 관련 속성에 대한 예와 설명입니다. 감사 레코드를 선택하여 **세부** 정보 플라이아웃 페이지를 표시한 다음 추가 정보를 **선택합니다.**

![통과 인증 성공에 대한 감사 레코드의 예](../media/PassThroughAuth1.png)

   a. 이 필드는 조직의 리소스에 액세스하려고 시도한 사용자가 조직의 Azure AD에서 찾을 수 없는 경우를 나타냅니다.

   b. 이 필드에는 조직의 리소스에 액세스하려고 시도한 외부 사용자의 UPN이 표시됩니다. 이 사용자 ID는 감사 레코드의 **User** 및 **UserId** 속성에서도 식별됩니다.

   c. **ApplicationId** 속성은 로그온 요청을 트리거한 응용 프로그램을 식별합니다. 이 감사 레코드의 ApplicationId 속성에 표시되는 값 000000003-0000-0ff1-ce00-000000000000000은 SharePoint Online을 나타냅니다. 비즈니스용 OneDrive ApplicationId도 동일합니다.

   d. 통과 인증이 성공했다는 것입니다. 즉, 사용자가 Azure AD에서 인증된 것입니다. 

   e. **RecordType 값이** **15이면** 감사된 활동(UserLoggedIn)이 Azure AD의 STS(Secure Token Service) 로그온 이벤트입니다.

UserLoggedIn 감사 레코드에 표시되는 다른 속성에 대한 자세한 내용은 Office 365 [Management Activity API schema의](/office/office-365-management-api/office-365-management-activity-api-schema#azure-active-directory-base-schema)Azure AD 관련 Office 365 참조하세요.

통과 인증으로 인해 사용자가 감사  활동에 성공적으로 로그인하게 하는 두 가지 예제 시나리오는 다음과 같습니다. 

  - Microsoft 계정(예: SaraD@outlook.com)이 있는 사용자가 비즈니스용 OneDrive 계정의 문서에 액세스하려고 하여 fourthcoffee.onmicrosoft.com 계정의 SaraD@outlook.com 사용자 계정이 fourthcoffee.onmicrosoft.com.

  - 조직에 직장 또는 학교 계정이 있는 사용자(예: pilarp@fabrikam.onmicrosoft.com)가 SharePoint 사이트에 액세스하려고 contoso.onmicrosoft.com 해당 게스트 사용자 계정이 pilarp@fabrikam.com 없습니다 contoso.onmicrosoft.com.

### <a name="tips-for-investigating-successful-logins-resulting-from-pass-through-authentication"></a>팁 인증으로 인해 발생하는 성공적인 로그인을 조사하는 데 사용할 수 있는 정보

- 감사 로그에서 감사 레코드에 기록된 사용자에 식별된 외부 사용자가 수행한 활동을 **검색합니다.** 사용자 상자에 외부 사용자의 UPN을 **입력하고** 시나리오와 관련된 경우 날짜 범위를 사용 합니다. 예를 들어 다음 검색 조건을 사용하여 검색을 만들 수 있습니다.

   ![외부 사용자가 수행한 모든 활동을 검색합니다.](../media/PassThroughAuth2.png)

    사용자가 로그인한  활동 외에도 조직의 사용자가 외부 사용자와 리소스를 공유하고 외부 사용자가 공유한 문서를 액세스, 수정 또는 다운로드하는지 여부를 나타내는 기타 감사 레코드가 반환될 수 있습니다.

- 감사 레코드에 SharePoint 사용자가 식별한 외부 사용자와 파일을 공유했다는 것을 나타내는 공유 활동을 검색합니다.  자세한 내용은 [감사 로그에서 공유 감사 사용](use-sharing-auditing.md)을 참조하세요.

- 외부 사용자와 관련된 다른 활동을 검색하는 데 Excel 수 있도록 조사와 관련된 레코드가 포함된 감사 로그 검색 결과를 내보낼 수 있습니다. 자세한 내용은 감사 로그 레코드 [내보내기, 구성 및 보기를 참조하세요.](export-view-audit-log-records.md)

## <a name="search-for-mailbox-activities-performed-by-users-with-non-e5-licenses"></a>비 E5 라이선스가 있는 사용자가 수행한 사서함 활동 검색

조직에 [](enable-mailbox-auditing.md) 대해 기본적으로 사서함 감사가 켜져 있는 경우에도 준수 센터, **Search-UnifiedAuditLog** cmdlet 또는 Office 365 관리 활동 API를 사용하여 감사 로그 검색에서 일부 사용자에 대한 사서함 감사 이벤트를 찾을 수 없습니다. 이전 방법 중 하나에서 통합 감사 로그를 검색할 때 사서함 감사 이벤트가 E5 라이선스가 있는 사용자에 한해 반환됩니다.

E5 이 아닌 사용자에 대한 사서함 감사 로그 레코드를 검색하려면 다음 해결 작업 중 하나를 수행할 수 있습니다.

- 개별 사서함에 대해 사서함 감사를 수동으로 사용하도록 `Set-Mailbox -Identity <MailboxIdentity> -AuditEnabled $true` 설정(PowerShell에서 Exchange Online 실행). 이렇게 한 후 준수 센터, **Search-UnifiedAuditLog** cmdlet 또는 관리 활동 API를 사용하여 사서함 감사 Office 365 검색합니다.
  
  > [!NOTE]
  > 사서함 감사가 이미 사서함에서 사용하도록 설정된 것으로 보이지만 검색에서 결과가 반환되지 않았다면 _AuditEnabled_ 매개 변수의 값을 로 변경한 다음 로 `$false` 다시 `$true` 변경합니다.
  
- PowerShell에서 다음 cmdlet을 Exchange Online 있습니다.

  - [Search-MailboxAuditLog](/powershell/module/exchange/search-mailboxauditlog) - 특정 사용자에 대한 사서함 감사 로그를 검색합니다.

  - [New-MailboxAuditLogSearch](/powershell/module/exchange/new-mailboxauditlogsearch) - 특정 사용자에 대한 사서함 감사 로그를 검색하고 지정된 받는 사람에게 전자 메일을 통해 결과를 전송하도록 합니다.

## <a name="search-for-mailbox-activities-performed-in-a-specific-mailbox-including-shared-mailboxes"></a>특정 사서함에서 수행되는 사서함 활동 검색(공유 사서함 포함)

준수 센터의  감사 로그 검색 도구에 있는 사용자 드롭다운 목록 또는 Exchange Online PowerShell에서 **Search-UnifiedAuditLog -UserIds** 명령을 사용하는 경우 특정 사용자가 수행한 활동을 검색할 수 있습니다. 사서함 감사 활동의 경우 이 유형의 검색은 지정된 사용자가 수행한 활동을 검색합니다. 동일한 사서함에서 수행되는 모든 활동이 검색 결과에 반환된다고 보장하지는 않습니다. 예를 들어 특정 사용자가 수행한 사서함 활동을 검색하면 다른 사용자의 사서함에 액세스할 수 있는 권한이 할당된 대리인 사용자가 수행한 활동이 반환되지 않는 감사 로그 검색에서는 대리인 사용자가 수행한 활동에 대한 감사 레코드를 반환하지 않습니다. 대리인 사용자는 다른 사용자의 사서함에 대한 SendAs, SendOnBehalf 또는 FullAccess 사서함 권한이 할당된 사용자입니다.

또한 감사  로그 검색 도구 또는 **Search-UnifiedAuditLog -UserIds의** 사용자 드롭다운 목록을 사용하면 공유 사서함에서 수행되는 활동에 대한 결과가 반환되지 않습니다.

특정 사서함에서 수행된 활동을 검색하거나 공유 사서함에서 수행되는 활동을 검색하기 위해 **Search-UnifiedAuditLog** cmdlet을 실행하는 경우 다음 구문을 사용하십시오.

```powershell
Search-UnifiedAuditLog  -StartDate <date> -EndDate <date> -FreeText (Get-Mailbox <mailbox identity).ExchangeGuid
```

예를 들어 다음 명령은 Contoso Compliance Team 공유 사서함에서 2020년 8월과 2020년 10월 사이에 수행된 활동에 대한 감사 레코드를 반환합니다.

```powershell
Search-UnifiedAuditLog  -StartDate 08/01/2020 -EndDate 10/31/2020 -FreeText (Get-Mailbox complianceteam@contoso.onmicrosoft.com).ExchangeGuid
```

또는 **Search-MailboxAuditLog** cmdlet을 사용하여 특정 사서함에서 수행된 활동에 대한 감사 레코드를 검색할 수 있습니다. 여기에는 공유 사서함에서 수행되는 활동에 대한 검색이 포함됩니다.

다음 예에서는 Contoso Compliance Team 공유 사서함에서 수행된 활동에 대한 사서함 감사 로그 레코드를 반환합니다.

```powershell
Search-MailboxAuditLog -Identity complianceteam@contoso.onmicrosoft.com -StartDate 08/01/2020 -EndDate 10/31/2020 -ShowDetails
```

다음 예에서는 위임 사용자가 지정된 사서함에서 수행한 활동에 대한 사서함 감사 로그 레코드를 반환합니다.

```powershell
Search-MailboxAuditLog -Identity <mailbox identity> -StartDate <date> -EndDate <date> -LogonTypes Delegate -ShowDetails
```

**New-MailboxAuditLogSearch** cmdlet을 사용하여 감사 로그에서 특정 사서함을 검색하고 전자 메일을 통해 지정된 받는 사람에게 결과를 보낼 수도 있습니다.