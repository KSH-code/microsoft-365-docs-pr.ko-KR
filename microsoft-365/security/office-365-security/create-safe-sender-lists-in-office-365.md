---
title: Office 365에서 수신 허용-보낸 사람 목록 만들기
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150s
ms.assetid: 9721b46d-cbea-4121-be51-542395e6fd21
description: 관리자는 인바운드 메시지가 스팸 필터링을 건너뛰도록 허용 하는 Office 365 및 EOP의 사용 가능한 옵션에 대해 알아볼 수 있습니다.
ms.openlocfilehash: 4b50a4b63377c0f3e7b12592c512449f1a3adc12
ms.sourcegitcommit: 9ed3283dd6dd959faeca5c22613f9126261b9590
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/16/2020
ms.locfileid: "43528632"
---
# <a name="create-safe-sender-lists-in-office-365"></a>Office 365에서 수신 허용-보낸 사람 목록 만들기

Exchange online 사서함이 없는 Office 365, 독립 실행형 EOP (Exchange Online Protection) 고객에 게 사서함이 있는 경우 EOP에서는 사용자가 신뢰할 수 있는 보낸 사람 으로부터 전자 메일을 수신 하도록 하는 여러 가지 방법을 제공 합니다. 이러한 옵션에는 스팸 방지 정책에서 Exchange 메일 흐름 규칙 (전송 규칙이 라고도 함), Outlook 수신 허용-IP 허용 목록 (연결 필터링), 허용 되는 보낸 사람 목록 또는 허용 도메인 목록이 포함 됩니다. 이러한 옵션은 집합적으로 _수신 허용-보낸 사람 목록_으로 간주할 수 있습니다.

사용 가능한 수신 허용-보낸 사람 목록은 다음 목록에서 권장 되는 것부터 최소 권장 사항 순으로 설명 됩니다.

1. 메일 흐름 규칙

2. Outlook 수신 허용-보낸 사람

3. IP 허용 목록 (연결 필터링)

4. 허용 된 보낸 사람 목록 또는 허용 된 도메인 목록 (스팸 방지 정책)

메일 흐름 규칙을 사용 하면 가장 유연 하 게 적절 한 메시지만 허용 됩니다. 스팸 방지 정책에서 허용 되는 보낸 사람 및 허용 도메인 목록은 보낸 사람의 전자 메일 도메인이 쉽게 위장 되므로 IP 허용 목록 처럼 안전 하지 않습니다. 그러나 ip 허용 목록에는 해당 IP 주소에서 보낸 _모든_ 도메인의 전자 메일이 스팸 필터링을 무시 하므로 위험도 표시 됩니다.

> [!IMPORTANT]
> <ul><li>수신 허용-보낸 사람 목록을 사용 하 여 스팸 필터링에 대 *한 예외를* 면밀 하 게 모니터링 해야 합니다.</li><li>수신 허용-보낸 사람 목록을 사용 하 여 가양성 (스팸으로 표시 된 전자 메일)에 대 한 도움을 받을 수 있지만 안전한 보낸 사람 목록을 가능한 경우 피해 야 하는 임시 솔루션으로 사용 하는 것이 좋습니다. 스팸 필터링에 대 한 예외로 인해 조직이 스푸핑 및 기타 공격을 막을 수 있으므로 수신 허용-보낸 사람 목록을 사용 하 여 가양성을 관리 하지 않는 것이 좋습니다. 수신 허용-보낸 사람 목록을 사용 하 여 가양성을 관리 해야 하는 경우에는 vigilant를 수행 하 고 준비 하는 동안 항목 [보고서 메시지 및 파일을 Microsoft에](report-junk-email-messages-to-microsoft.md) 보관해 두어야 합니다.</li><li>도메인이 인증 되지 않은 전자 메일을 보낼 수 있도록 허용 하려면 (스푸핑 방지 보호 무시), 스팸 방지 및 맬웨어 방지 검사를 우회 하지 않도록 하려면 [Allowedtospoof 수신 허용-보낸 사람 목록](walkthrough-spoof-intelligence-insight.md) 에 추가 하면 됩니다.</li><li>EOP 및 Outlook에서 다른 메시지 속성을 검사 하 여 메시지를 보낸 사람을 확인 합니다. 자세한 내용은이 항목의 뒷부분에 나오는 [대량 전자 메일 고려 사항](#considerations-for-bulk-email) 섹션을 참조 하십시오.</li></ul>

반면, _차단 된 보낸 사람 목록을_사용 하 여 특정 원본의 전자 메일을 차단 하는 몇 가지 옵션도 있습니다. 자세한 내용은 [Office 365에서 차단할 보낸 사람 목록 만들기](create-block-sender-lists-in-office-365.md)를 참조하세요.

## <a name="recommended-use-mail-flow-rules"></a>는 메일 흐름 규칙 사용

Exchange Online 및 독립 실행형 EOP의 메일 흐름 규칙에서는 메시지를 식별 하는 조건 및 예외를 사용 하 고 이러한 메시지에 대해 수행 해야 하는 작업을 지정 합니다. 자세한 내용은 [Exchange Online의 메일 흐름 규칙 (전송 규칙)](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/mail-flow-rules)을 참조 하세요.

다음 예에서는 스팸 필터링을 건너뛰려면 contoso.com의 전자 메일이 필요한 것으로 가정 합니다. 이렇게 하려면 다음 설정을 구성 합니다.

1. **조건**: **보낸 사람** \> **도메인** \> 은 contoso.com입니다.

2. 다음 설정 중 하나를 구성 합니다.

   - **메일 흐름 규칙 조건**: **메시지 헤더** \> 에는 다음과 같은 단어 \> **헤더 이름** `Authentication-Results` \> **(헤더 값**: `dmarc=pass` 또는 `dmarc=bestguesspass`) **이 포함 됩니다** .

     이 조건은 보내는 전자 메일 도메인의 보낸 사람 인증 상태를 확인 하 여 해당 도메인이 위장 되 고 있지 않은지 확인 합니다. 전자 메일 인증에 대 한 자세한 내용은 [SPF](set-up-spf-in-office-365-to-help-prevent-spoofing.md), [Dkim](use-dkim-to-validate-outbound-email.md)및 [DMARC](use-dmarc-to-validate-email.md)을 참조 하십시오.

   - **IP 허용 목록**: 연결 필터 정책에 원본 IP 주소 또는 주소 범위를 지정 합니다.
  
     보내는 도메인에 인증이 없는 경우이 설정을 사용 합니다. IP 허용 목록의 원본 IP 주소에 도달 하는 경우 최대한 제한적 이어야 합니다. IP 주소 범위가/24 이하인 것이 좋습니다 (더 나은 것이 좋음). 소비자 서비스 (예: outlook.com) 또는 공유 인프라에 속하는 IP 주소 범위는 사용 하지 마십시오.

   > [!IMPORTANT]
   > <ul><li>사용 안 함 메일 흐름 규칙을 보낸 사람 도메인 *만* 사용 하 여 스팸 필터링을 건너뛰도록 구성 합니다. 이렇게 하면 공격자가 보내는 도메인을 스푸핑할 때 (또는 전체 전자 메일 주소 가장), 모든 스팸 필터링을 건너뛰고, 보낸 사람 인증 검사를 건너뛸 수 있어 메시지가 받는 사람의 받은 편지함에 도착할 *가능성이 높아집니다.*</li><li>소유한 도메인 (허용 도메인이 라고도 함) 또는 인기 있는 도메인 (예: microsoft.com)을 메일 흐름 규칙의 조건으로 사용 하지 마십시오. 이렇게 하면 공격자가 다른 방식으로 필터링 할 수 있는 전자 메일을 보내는 기회가 만들어지므로 높은 위험으로 간주 됩니다.</li><li>NAT (network address translation) 게이트웨이 뒤에 있는 IP 주소를 허용 하는 경우 IP 허용 목록의 범위를 확인 하기 위해 NAT 풀에 포함 된 서버를 파악 해야 합니다. IP 주소 및 NAT 참가자가 변경 될 수 있습니다. 표준 유지 관리 절차의 일부로 IP 허용 목록 항목을 주기적으로 확인 해야 합니다.</li></ul>

3. **선택적 조건**:

   - **보낸 사람이** \> \> **조직 외부**의 **내부/외부 인** 경우:이 조건은 암시적 이지만 올바르게 구성 되지 않았을 수 있는 온-프레미스 전자 메일 서버를 고려 하는 데 사용할 수 있습니다.

   - **제목 또는 본문** \> **제목 또는 본문** \> \<에는 다음과 같은 단어 키워드가\>포함 됩니다. 제목 줄 이나 메시지 본문의 키워드나 구로 메시지를 추가로 제한할 수 있는 경우 해당 단어를 조건으로 사용할 수 있습니다.

4. **작업**: 규칙에서 이러한 작업을 모두 구성 합니다.

   a. **메시지 속성** \> 수정 **SCL (스팸** \> 지 수) 사용 **안 함 스팸 필터링**을 설정 합니다.

   b. **메시지 헤더** \> 에는 다음과 같은 단어 \> **헤더 이름**: \<customheadername\> **헤더 값**: \<customheadername\>가 **포함 됩니다** .

      예를 들면 `X-ETR: Bypass spam filtering for authenticated sender 'contoso.com'`와 같습니다. 규칙에 도메인이 둘 이상 있는 경우 머리글 텍스트를 적절 하 게 사용자 지정할 수 있습니다.

      메일 흐름 규칙으로 인해 메시지에 대 한 스팸 필터링이 생략 되 면 `SFV:SKN` 값 값은 **스팸 방지-Report** 헤더에 스탬프 처리 됩니다. 메시지가 IP 허용 목록에 있는 원본의 메시지 이면 해당 값 `IPV:CAL` 도 추가 됩니다. 이러한 값은 문제 해결에 도움이 될 수 있습니다.

![스팸 필터링을 무시 하기 위한 EAC의 메일 흐름 규칙 설정입니다.](../../media/1-AllowList-SkipFilteringFromContoso.png)

## <a name="use-outlook-safe-senders"></a>Outlook 수신 허용-보낸 사람 사용

조직 설정 대신 사용자 또는 관리자가 사서함의 수신 허용-보낸 사람 목록에 보낸 사람 전자 메일 주소를 추가할 수 있습니다. 자세한 내용은 [Office 365에서 Exchange Online 사서함의 정크 메일 설정 구성을](configure-junk-email-settings-on-exo-mailboxes.md)참조 하세요.

메시지가 사용자의 수신 허용-보낸 사람 목록으로 인해 스팸 필터링을 건너뛸 때 **스팸 방지-Report** header 필드에는 스팸, 스푸핑 및 피싱 `SFV:SFE`필터링이 무시 됨을 나타내는 값이 포함 됩니다.

## <a name="use-the-ip-allow-list"></a>IP 허용 목록 사용

앞에서 설명한 것 처럼 메일 흐름 규칙을 사용할 수 없는 경우에는 연결 필터 정책의 IP 허용 목록에 원본 전자 메일 서버를 추가 하는 것이 가장 좋습니다. 자세한 내용은 [Configure connection 필터링할지 In Office 365](configure-the-connection-filter-policy.md)을 참조 하십시오.

**참고**:

- 허용 되는 IP 주소 수를 최소로 유지 하는 것이 중요 하므로 가능 하면 전체 IP 주소 범위를 사용 하지 않는 것이 좋습니다.

- 소비자 서비스 (예: outlook.com) 또는 공유 인프라에 속하는 IP 주소 범위는 사용 하지 마십시오.

- IP 허용 목록의 항목을 정기적으로 검토 하 고 더 이상 필요 없는 항목을 제거 합니다.

> [!CAUTION]
> 메일 흐름 규칙과 같이 추가 확인이 없으면 IP 허용 목록에 있는 원본의 전자 메일이 스팸 필터링 및 보낸 사람 인증 (SPF, DKIM, DMARC) 검사를 건너뜁니다. 따라서 공격자가 받은 편지함에 전자 메일을 배달 하는 데 성공 하 게 되는 위험을 초래할 수 있습니다.

## <a name="use-allowed-sender-lists-or-allowed-domain-lists"></a>허용 되는 보낸 사람 목록 또는 허용 되는 도메인 목록 사용

스팸 방지 정책에서 허용 되는 보낸 사람 목록 또는 허용 도메인 목록을 사용 하는 것이 가장 바람직하지 않은 옵션입니다. 보낸 사람이 모든 스팸, 스푸핑, 피싱 보호 및 보낸 사람 인증 (SPF, DKIM, DMARC)을 우회 하기 때문에 *가능 하면* 이 옵션을 사용 하지 않는 것이 좋습니다. 이 메서드는 임시 테스트에만 사용 하는 것이 가장 좋습니다. 자세한 단계는 [Office 365의 스팸 방지 정책 구성](configure-your-spam-filter-policies.md) 항목에서 찾을 수 있습니다.

이러한 목록의 최대 제한은 약 1000 항목입니다. 하지만 포털에는 30 개의 항목만 입력할 수 있습니다. 30 개 보다 많은 항목을 추가 하려면 PowerShell을 사용 해야 합니다.

> [!CAUTION]
> <ul><li>이 방법을 사용할 경우 공격자가 사서함에 대 한 전자 메일을 성공적으로 필터링 할 수 있는 높은 위험을 만듭니다.</li><li>사용자가 소유한 도메인 (허용 도메인) 또는 인기 있는 도메인 (예: microsoft.com)을 허용 된 도메인 목록에 사용 하지 마십시오.</li></ul>

## <a name="considerations-for-bulk-email"></a>대량 전자 메일에 대 한 고려 사항

표준 SMTP 전자 메일 메시지는 *메시지 봉투* 와 메시지 콘텐츠로 구성 됩니다. 메시지 봉투에는 SMTP 서버 간에 메시지를 전송 및 배달 하는 데 필요한 정보가 포함 되어 있습니다. 메시지 콘텐츠에는 메시지 헤더 필드 (통칭 *메시지 헤더*) 및 메시지 본문이 포함 됩니다. 메시지 봉투는 RFC 5321에 설명 되어 있고 메시지 헤더는 RFC 5322에 설명 되어 있습니다. 실제 메시지 봉투는 메시지 전송 프로세스에 의해 생성 되며 실제로는 메시지의 일부가 아니기 때문에 받는 사람에 게는 표시 되지 않습니다.

- `5321.MailFrom` 주소 ( **메일** 보낸 사람 주소, P1 sender 또는 envelope sender)는 메시지의 SMTP 전송에 사용 되는 전자 메일 주소입니다. 이 전자 메일 주소는 일반적으로 메시지 헤더의 **반환 경로** 헤더 필드에 기록 됩니다 (보낸 사람이 다른 **반환 경로** 전자 메일 주소를 지정할 수 있지만). 메시지를 배달할 수 없는 경우 NDR 또는 바운스 메시지가 라고도 하는 배달 못 함 보고서 (예를 들어)의 받는 사람을 나타냅니다.

- `5322.From` **보낸 사람 주소 또는** P2 보낸 사람이 라고도 하는 전자 메일 주소 **는 보낸 사람의** 전자 메일 주소 이며 전자 메일 클라이언트에 표시 됩니다.

`5321.MailFrom` 및 `5322.From` 주소는 동일 합니다 (사용자 간 통신). 그러나 다른 사람을 대신 하 여 전자 메일을 보내는 경우에는 주소가 서로 다를 수 있습니다. 일반적으로 대량 전자 메일 메시지에서 가장 자주 발생 합니다.

예를 들어 파란색 Yonder Airlines가 손 정 란 여행사를 고용 하 여 전자 메일 광고를 보내도록 가정 합니다. 받은 편지함에 받은 메시지에는 다음과 같은 속성이 있습니다.

- 주소 `5321.MailFrom` 는 blueyonder.airlines@margiestravel.com입니다.

- 주소 `5322.From` 는 blueyonder@news.blueyonderairlines.com, 즉 Outlook에서 볼 수 있습니다.

EOP의 스팸 방지 정책에서 수신 허용-보낸 사람 목록 및 안전한 도메인 목록은 두 `5321.MailFrom` `5322.From` 주소를 모두 검사 합니다. Outlook 수신 허용-보낸 사람만 `5322.From` 주소를 사용 합니다.

이 메시지가 필터링 되지 않도록 하려면 다음 단계를 수행 하면 됩니다.

- Outlook 수신 허용- `5322.From` 보낸 사람으로 blueyonder@news.blueyonderairlines.com (주소)를 추가 합니다.

- [메일 흐름 규칙을 사용](#recommended-use-mail-flow-rules) 하 여 blueyonder@news.blueyonderairlines.com ( `5322.From` 주소, blueyonder.airlines@margiestravel.com ( `5321.MailFrom`) 또는 둘 다)의 메시지를 찾습니다.

자세한 내용은 [Office 365에서 수신 허용-보낸 사람 목록 만들기](create-safe-sender-lists-in-office-365.md)를 참조 하세요.
