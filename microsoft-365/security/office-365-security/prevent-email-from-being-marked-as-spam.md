---
title: Office 365에서 가양성을 발생을 방지하는 방법
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.collection:
- M365-security-compliance
localization_priority: Priority
search.appverid:
- MOE150
- MET150
description: 'Office 365, Exchange Online 및 독립형 Exchange Online Protection(EOP)에서 가양성을 방지 하고 실제 이메일이 정크 메일로 분류되는 것을 방지하는 방법을 알아봅니다. '
ms.openlocfilehash: bf6149d21a5088e4507b65c6474918327faf3510
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/29/2020
ms.locfileid: "41598695"
---
# <a name="how-to-prevent-good-email-messages-from-being-marked-as-spam-in-office-365"></a>Office 365에서 실제 이메일이 스팸으로 표시되지 않도록 하는 방법

 **실제 전자 메일이 Office 365에서 스팸으로 표시되나요? 그렇다면 다음을 수행하세요.**

Office 365, Exchange Online 또는 독립형 Exchange Online Protection(EOP)에서 실제 메일 메시지를 스팸 (하나의 _가양성_)으로 표시 하면 [보고서 메시지 추가 기능을 사용하여](https://support.office.com/article/b5caa9f1-cdf3-4443-af8c-ff724ea719d2) Microsoft에 메시지를 보고 해야 합니다. 또한 [제출 탐색기](admin-submission.md)를 사용 하여 메시지를 제출할 수 있습니다.

## <a name="determine-why-the-message-was-marked-as-spam"></a>메시지가 스팸으로 표시되는 이유 확인

이메일 메시지 머리글을 사용 하여 메시지를 스팸으로 표시 한 이유를 확인 하면 가양성과 관련한 여러 문제를 해결할 수있습니다.  메시지 머리글을 보려면 [Outlook internet 메시지 머리글 보기](https://support.office.com/article/cd039382-dc6e-4264-ac74-c048563d212c)를 참조 하세요.

특히 **X-Forefront-Antispam-Report**라는 이름의 머리글 필드를 찾으세요.  검색할 주요 값은 다음과 같습니다.

- **SFV: SPM**: 스팸 방지 필터 (_콘텐츠 필터_)에 의해 메시지가 스팸으로 표시 되었습니다. 자세한 내용은 [Office 365 이메일 스팸 방지 보호](anti-spam-protection.md)를 참조하세요.

- **SFV:BLK**: **보낸 사람의** 이메일 주소가 받는 사람의 차단된 보낸 사람 목록에 있기 때문에 메시지가 스팸으로 표시되었음을 나타냅니다. 자세한 내용은 [정크 이메일 필터, 웹 Outlook 스팸](https://support.office.com/article/db786e79-54e2-40cc-904f-d89d57b7f41d) 및 [정크 이메일 필터 개요를 참조하세요](https://support.office.com/article/5ae3ea8e-cf41-4fa0-b02a-3b96e21de089). 

- **SFV: SKS**: 스팸방지 필더 적용 **이전에** 메시지가 스팸으로 표시되었습니다.  예를 들어 메일 흐름 규칙(전송 규칙) 스팸 신뢰 수준(SCL)에서 해당 메시지가 스팸임을 나타내는 높은 값(9)로 설정되었습니다.  서비스의 SCL 값에 대한 자세한 내용은 [스팸 신뢰 수준](spam-confidence-levels.md)을 참조하세요.

  메시지 추적을 실행 하여 메일 흐름 규칙이 높은 SCL 값을 부여했는지 확인합니다.  자세한 내용은 [보안 및 준수 센터 메시지 추적](message-trace-scc.md)을 참조하세요.

- **SFV: SKB**: 메시지는 스팸 필터 정책 (예: 차단할 보낸 사람 또는 차단할 보낸 사람 도메인)에 있는 블록 항목과 일치 하므로 스팸으로 표시 되었습니다. 자세한 내용은 [스팸 필터 정책 구성을](configure-your-spam-filter-policies.md) 참조하세요.

- **SFV: BULK**: 메시지가 스팸 방지 필터에 의해 스팸이 아닌 대량 이메일로 식별 되었습니다. 이는 메시지의 BCL(대량 불만 수준) 값이 스팸 방지 정책 설정에 정의 된 대량 임계값 **보다 클** 경우에 발생 합니다(하위 BCL 값은 메시지가 스팸일 가능성이 더 높다는 것을 의미). **X-Microsoft-스팸 방지** 머리글 필드에서 BCL 값을 볼 수 있습니다.

  대량 이메일 (_회색 메일_)은 바람직하지는 않지만 악성 마케팅이나 광고 이메일이 아니고 사용자가 의도적으로 혹은 우연히 요청한 이메일입니다.  대랑 이메일 처리 방법에 대한 기대치는 사용자마다 다르기 때문에 사용자가 직접 대랑 이메일 을 허용하거나 차단하는 정책이나 규칙을 만들 수 있습니다. 자세한 내용은 다음 항목을 참조하세요.

  - [정크 이메일과 대량 이메일의 차이점이 무엇인가요?](what-s-the-difference-between-junk-email-and-bulk-email.md)

  - [대량 불만 수준 값](bulk-complaint-level-values.md)

- **CAT:SPOOF** 또는 **CAT:PHISH**: 메시지가 스푸핑된 것 같음을 나타냅니다. 즉, 메시지 원본의 유효성을 검증할 수 없고 메시지 원본이 의심스러울 수 있습니다.

  스푸핑된 보낸 사람의 메시지를 받은 경우 해당 발신자는 자신의 이메일 도메인 SPF 및 공용 DNS의 DKIM 레코드를 확인 해야 합니다. 자세한 내용은 **인증-결과** 머리글 필드를 확인 하세요. 모든 보낸 사람이 적절한 이메일 인증 방법을 사용하도록 하기는 어려울 수 있지만, 이러한 검사를 건너뛰는 것은 매우 위험할 수 있으며 스푸핑 및 피싱 메시지의 주요 원인입니다.

> [!NOTE]
> • 다른 안티스팸 메시지 머리글과 값에 대해 알아보시려면 [스팸방지 메시지 헤더](anti-spam-message-headers.md)를 참고하세요. <br/><br/>• 특별히 설명되지 않은 다른 머리글 필드 및 값은 Microsoft 스팸방지 팀에서 진단용으로만 사용됩니다. <br/><br/>• 페시지 헤더의 **X-CustomSpam** 머리글 필드는 메시지가 Advanced Spam Filtering(ASF)에 의해 스팸으로 표시 됨을 나타냅니다.  ASF 기능을 필터링 스택의 다른 부분으로 이동 하는 중 이며, 현재 스팸 방지 정책에서 제공되는 ASF 설정을 **해제** 하는 것을 권장합니다.  자세한 내용은, [고급 스팸 필터링 옵션을](advanced-spam-filtering-asf-options.md) 참고 하세요.

## <a name="solutions-for-too-much-spam"></a>지나치게 많은 스팸 해결 방법

스팸 방지 필터링이 가장 효과적이으로 작동 되려면 관리자가 조직에서 몇 가지 설정을 구성 해야 합니다. 관리자가 아닌 경우 사용자 섹션으로 건너뛸 수 있습니다.

### <a name="for-admins"></a>관리자

- **이메일 도메인의 MX 레코드를 Office 365로 전환**: Office 365에서 보호를 제공 하려면 Office 365의 모든 이메일 도메인 MX 레코드가 office 365로 전환되어야 하고 Office 365로만 전환 (즉, 해당 도메인의 받는 사람에 대한 이메일은 항상 Office 365로 배달 됨)되어야 합니다. MX 레코드가 다른 위치(예: 서드 파티 스팸방지 솔루션이 혹은 어플라이언스)를 가리키는 경우 Office 365는 사용자에게 스팸 필터링을 제공할 수 없습니다. 이런 경우에는 모든 메시지에 대한 스팸 필터링을 무시 하는 메일 흐름 규칙을 만드는 것이 좋습니다(모든 받는 메시지의 SCL 값을-1로 설정). 나중에 MX 레코드를 먼저 Office 365로 전환한 경우에는 해당 규칙을 제거 해야 합니다.

- **사용자 보고서 메시지 추가 기능 설정**: 사용자용 보고서 메시지 추가 기능을 사용하도록 설정할 것을 강력히 권장합니다. 설정 방법은 [보고서 메시지 추가 기능 설정](enable-the-report-message-add-in.md)을 참고하세요. 

- **전송 탐색기 사용**: 관리자는 이제 Microsoft 이메일 메시지 스캐닝을 신청할 수 있습니다.  관리자는 사용자가 보낸 피드백을 볼 수 있습니다. 가양성 보고 패턴을 사용 하여 스팸 필터링 설정을 조정할 수 있습니다. 자세한 내용은, [Office 365 스캐닝을 위해 의심스러운 스팸, 피싱, Url 및 파일을 Microsoft에 제출 하는 방법을 참조 하세요](admin-submission.md).

- **사용자가 Exchange Online 서비스 설명에 **나와있는[ 허용된](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#receiving-and-sending-limits) 받기와 보내기 범위에 있는지 확인합니다. 

- **앞에서 말한 대로 스팸 방지 정책 BCL 레벨을** 확인합니다. 

### <a name="for-users"></a>사용자

- **보낸 사람을 [Outlook](https://support.office.com/article/5ae3ea8e-cf41-4fa0-b02a-3b96e21de089) 혹은 [웹 Outlook의](https://support.office.com/article/db786e79-54e2-40cc-904f-d89d57b7f41d) 수신 허용-보낸 사람 목록에** 추가합니다. 

  Office 365는 수신 허용-보낸 사람 목록 및 수신 허용-받는 사람 목록을 사용 하지만 안전한 도메인 목록은 사용 하지 않습니다. 이는 사용자가 목록에 도메인을 추가 하는 방법 (Outlook, 웹 Outlook 혹은 Outlook 추가 후 디렉토리 동기화에 의한 동기화)에 관계 없이 적용됩니다. 

- **Outlook에서 SmartScreen 필터링 해제**: 구버전의 Outlook 데스크톱 사용자는 **정크 메일 옵션에서** SmartScreen 필터링을 사용 하지 않도록 설정 합니다. SmartScreen 필터링 업데이트는 2016 년 11월에 종료 되었습니다. 만약 Outlook에서 **낮은** 혹은 **높은** 정크 이메일 보호를 설정하면 SmartScreen 필터링을 사용하게 되고 가양성이 발생할 수 있습니다.  최신 Outlook 데스크톱 사용자는 SmartScreen 필터링을 사용할 수 없습니다.  자세한 내용은 [Outlook 및 Exchange에서 SmartScreen 지원 삭제](https://techcommunity.microsoft.com/t5/Exchange-Team-Blog/Deprecating-support-for-SmartScreen-in-Outlook-and-Exchange/ba-p/605332)를 참조하세요.

## <a name="troubleshooting-a-message-is-delivered-to-the-junk-email-folder-after-passing-anti-spam-filtering"></a>문제 해결: 메시지는 스팸 방지 필터링 후 정크 메일 폴더로 배달됩니다. 

사용자 Outlook 정크 메일 옵션에서 **수신 허용 목록만** 선택 되어 있는 경우, 사용자의 수신 허용-보낸 사람 목록이나 수신 허용-받는 사람 목록에 속하지 않은 모든 메시지는 사용자 조직의 스팸 방지 필터링 통과 혹은 메일 흐름 규칙에 스팸 아닌 것으로 분류(SCL 값 -1) 되었는지 여부와 상관 없이 **정크 이메일** 폴터로 이동됩니다. 

웹 Outlook에서 메시지를 보면 보낸 사람이 수신자의 수신-허용 보낸 사람 목록에 없기 때문에 메시지가 **정크 이메일** 폴더에 있음을 나타내는 노란색 안전 팁이 표시됩니다.

메시지 머리글에는 **X-Forefront-Antispam-Report** 머리글 필드 값`SFV:SKN` (스팸 방지 필터를 사용 하여 메시지를 스팸이 아닌 것으로 표시 됨) 또는 `SFV:NSPM` (스팸 방지 필터가 스팸 아님으로 분류함)이 표시되지만, 메시지는 계속 사용자의 **정크 이메일** 폴더로 전달 됩니다.

메시지 머리글에는 사용자의 **수신 허용 목록** 설정 때문에 메시지가 정크 메일 배달 되었다는 내용은 표시 되지 않습니다. 하지만 Exchange Online PowerShell의 **Get-MailboxJunkEmailConfiguration** cmdlet을 사용하여 사용자가 신뢰할 수 있는 보낸사람만 받은 메일함에 전달 되도록 설정 했는지 확인할 수 있습니다.  

\<MailboxIdentity\>를 사서함의 이름, 별칭 또는 이메일 주소로 바꾸고 [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell)에서 다음 명령을 실행 합니다:

```PowerShell
Get-MailboxJunkEmailConfiguration -Identity "<MailboxIdentity>" | Format-List TrustedListsOnly,ContactsTrusted,TrustedSendersAndDomains
```

- *TrustedListsOnly* 속성 값`True`: 신뢰하는 보낸사람 혹은 받는 사람 (즉, 사용자의 수신 허용-보낸 사람 목록 및 수신 허용-받는 사람 목록에 속하지 않은 사용자)의 메시지가 아닌 경우 **정크 이메일** 폴더로 이동 합니다.

- *ContactsTrusted* 속성 값`True`: 사용자의 연락처도 신뢰할 수 있는 보낸 사람으로 식별 됩니다. *TrustedListsOnly* 속성 값 또한`True`, 신뢰하는 보낸사람 혹은 받는 사람 (즉, 사용자의 수신 허용-보낸 사람 목록 및 수신 허용-받는 사람 목록에 속하지 않은 사용자)의 메시지가 아닌 경우 **정크 이메일** 폴더로 이동 합니다.

- *TrustedSendersAndDomains는* 사용자의 수신 허용-보낸 사람 목록의 내용을 포함합니다.

사서함 설정 변경을 원하시면 \<MailboxIdentity\>를 사서함의 이름, 별칭 또는 사서함의 이메일 주소로 바꾸고 다음 명령을 실행 합니다:

```PowerShell
Set-MailboxJunkEmailConfiguration -Identity "<MailboxIdentity>" -TrustedListsOnly $false -ContactsTrusted $false
```

자세한 구문, 매개 변수 및 필수 권한 정보는 [Get-MailboxJunkEmailConfiguration](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/get-mailboxjunkemailconfiguration) 및 [Set-MailboxJunkEmailConfiguration](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/set-mailboxjunkemailconfiguration) 항목을 참조 하세요.

## <a name="directory-synchronization-for-standalone-eop-customers"></a>독립형 EOP 고객 디렉터리 동기화

독립형 EOP를 사용 하 여 온-프레미스 Exchange 조직을 보호 하는 경우 디렉터리 동기화를 사용하 여 사용자 설정을 서비스와 동기화 해야 합니다. 이렇게 하면 EOP에서 수신 허용-보낸 사람 목록을 유지할 수 있습니다. 자세한 내용은 [메일 사용자 관리를 위한 디렉토리 동기화 사용을](manage-mail-users-in-eop.md#use-directory-synchronization-to-manage-mail-users) 참고하세요.
