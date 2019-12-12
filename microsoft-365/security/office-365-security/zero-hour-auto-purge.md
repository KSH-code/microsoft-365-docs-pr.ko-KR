---
title: 제로 아워 자동 비우기 - 스팸 및 맬웨어로부터 보호
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 11/21/2019
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MOE150
- MED150
- MBS150
- MET150
ms.assetid: 96deb75f-64e8-4c10-b570-84c99c674e15
ms.collection:
- M365-security-compliance
description: ZAP (자동 삭제)은 사용자의 받은 편지 함으로 이미 배달 된 스팸 또는 맬웨어가 있는 메시지를 검색 한 다음 악의적인 콘텐츠를 렌더링 하는 전자 메일 보호 기능입니다. ZAP이 수행 하는 방법은 검색 된 악의적인 콘텐츠의 유형에 따라 다릅니다.
ms.openlocfilehash: 3a888e6a6b4de57efcb0a8b8284432a2b9f1095a
ms.sourcegitcommit: 5710ce729c55d95b8b452d99ffb7ea92b5cb254a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/11/2019
ms.locfileid: "39971386"
---
# <a name="zero-hour-auto-purge---protection-against-spam-and-malware"></a>제로 아워 자동 비우기 - 스팸 및 맬웨어로부터 보호

## <a name="overview"></a>개요

ZAP (자동 삭제)은 사용자의 받은 편지 함으로 이미 배달 된 피싱, 스팸 또는 맬웨어가 있는 메시지를 검색 한 다음 악성 콘텐츠 무해 함을 렌더링 하는 전자 메일 보호 기능입니다. ZAP이 수행 하는 방법은 검색 된 악의적인 콘텐츠의 유형에 따라 다릅니다. 메일은 mail content, Url 또는 attachments로 인해 zapped 될 수 있습니다.

ZAP은 Exchange Online 사서함이 포함 된 모든 Office 365 구독에 포함 된 기본 Exchange Online Protection에서 사용할 수 있습니다.

## <a name="how-zap-works"></a>ZAP 작동 방식

Office 365에서는 매일 실시간으로 스팸 방지 엔진 및 맬웨어 서명을 업데이트 합니다. 그러나 사용자에 게 콘텐츠를 배달 한 후에 weaponized를 포함 하 여 여러 가지 이유로 인해 사용자가 여전히 해당 받은 편지함에 악성 메시지를 배달 하도록 할 수 있습니다. ZAP은 Office 365 스팸 및 맬웨어 서명에 대 한 업데이트를 지속적으로 모니터링 하 여이를 해결 합니다. ZAP은 이전에 전달한 메시지 중 사용자의 받은 편지함에 이미 배달 된 메시지가 있는지 찾아 제거할 수 있습니다.

사서함 사용자에 게는 ZAP 동작이 원활 하 게 수행 됩니다. 전자 메일 메시지를 이동 하는 경우이 사용자에 게 알림이 제공 되지 않습니다. 메시지가 2 일 보다 오래 된 것은 아니어야 합니다.

허용 목록, [메일 흐름 규칙](use-transport-rules-to-configure-bulk-email-filtering.md) (전송 규칙이 라고도 함) 및 최종 사용자 규칙 또는 추가 필터가 ZAP 보다 우선적으로 적용 됩니다.

### <a name="malware-zap"></a>맬웨어 ZAP

새로 검색 된 맬웨어의 경우 ZAP은 첨부 파일을 포함 하 여 전체 메시지를 맬웨어 격리로 이동 합니다. 메시지는 메일의 읽기 상태와 관계 없이 이동 됩니다. 동적 배달 검색 프로세스에서 메시지에 대 한 맬웨어 신호가 수신 되 면 메시지에 대해 스팸 메일로 이동 작업이 수행 됩니다. 그런 다음 동적 배달이 배달 검사 시간을 완료 하 고 적절 한 조치를 취할 수 있도록 합니다.

맬웨어 ZAP은 맬웨어 정책에서 기본적으로 사용 하도록 설정 됩니다. Exchange Online PowerShell 또는 Exchange Online Protection PowerShell의 [get-malwarefilterpolicy](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/set-malwarefilterpolicy) Cmdlet에서 *ZapEnabled* 매개 변수를 사용 하 여 맬웨어 ZAP을 사용 하지 않도록 설정할 수 있습니다. 보안 및 준수 센터에서 맬웨어 정책을 편집 하 여 맬웨어 ZAP을 사용 하거나 사용 하지 않도록 설정할 수도 있습니다.

### <a name="phish-zap"></a>피싱 ZAP

배달 후에 피싱으로 식별 되는 메일의 경우에는 메일의 읽기 상태에 관계 없이 특정 사용자를 포함 하는 스팸 정책에 따라 ZAP이 작업을 수행 합니다. 정책 피싱 동작이 작업을 수행 *하지 않도록* 설정 (X-헤더 추가, 주체 수정, 작업 없음) 되 면 ZAP은 메일에 대해 아무 작업도 수행 하지 않습니다. 피싱 동작이 정크로 이동 하도록 설정 된 경우 ZAP은 메시지를 사용자의 받은 편지함에 있는 정크 메일 폴더로 이동 합니다. **다른 피싱 작업 (리디렉션, 삭제, 격리)을 사용할 경우에는 메시지가 피싱 격리로 이동 됩니다**. 구성 요구 사항 및 제외 항목은 아래에서 읽으십시오. [스팸 필터 정책을 구성](https://docs.microsoft.com//office365/securitycompliance/configure-your-spam-filter-policies) 하는 방법에 대 한 자세한 내용은 여기에서 확인할 수 있습니다.

피싱 ZAP은 스팸 정책에서 기본적으로 사용 하도록 설정 되어 있습니다. EOP cmdlet의 *PhishZapEnabled* 매개 변수를 사용 하 여 피싱 ZAP을 사용 하지 [않도록 설정할 수](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/Set-HostedContentFilterPolicy)있습니다.

### <a name="spam-zap"></a>스팸 ZAP

배달 후 스팸으로 확인 된 메일의 경우, 메시지를 읽지 않은 경우에만 ZAP이 특정 사용자를 포함 하는 스팸 정책에 따라 동작을 수행 합니다.  정책 스팸 작업이 작업을 수행 하지 않도록 설정 된 경우 (X-헤더 추가, 주체 수정, 작업 없음), ZAP은 메일에 대해 아무 작업도 수행 하지 않습니다. 스팸 동작이 정크로 이동 하도록 설정 된 경우 ZAP은 메시지를 사용자의 받은 편지함에 있는 정크 메일 폴더로 이동 합니다. **다른 스팸 작업 (리디렉션, 삭제, 격리) ZAP은 메시지를 스팸 격리로 이동**합니다. 구성 요구 사항 및 제외 항목은 아래에서 읽으십시오. [스팸 필터 정책을 구성](https://docs.microsoft.com//office365/securitycompliance/configure-your-spam-filter-policies) 하는 방법에 대 한 자세한 내용은 여기에서 확인할 수 있습니다.

스팸 ZAP은 스팸 정책에서 기본적으로 사용 하도록 설정 되어 있습니다. Exchange Online PowerShell 또는 Exchange Online Protection PowerShell에서 [get-hostedcontentfilterpolicy](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/Set-HostedContentFilterPolicy) Cmdlet의 *SpamZapEnabled* 매개 변수를 사용 하 여 스팸 ZAP을 사용 하지 않도록 설정할 수 있습니다.

### <a name="phish-and-spam-zap-requirements-exclusions-and-notices"></a>피싱 및 스팸 ZAP 요구 사항, 제외 및 알림

> [!IMPORTANT]
> 피싱 및 스팸 ZAP을 모두 제어 하는 이전 *ZapEnabled* cmdlet 매개 변수는 **사용 되지 않으며, 2020 년 2 월 1**일입니다. ZapEnabled 매개 변수를 사용 하는 스크립트를 작성 한 경우이를 SpamZapEnabled 및 PhishZapEnabled를 사용 하도록 업데이트 하는 것이 좋습니다. 전환 기간에는 cmdlet을 통해 모든 3 개의 매개 변수 (ZapEnabled, PhishZapEnabled 및 SpamZapEnabled)를 사용할 수 있습니다. UI 또는 PowerShell을 통해 명시적으로 설정 하기 전에는 PhishZapEnabled 및 SpamZapEnabled에 ZapEnabled 매개 변수의 상속 된 값이 표시 됩니다. 새 매개 변수를 설정한 후에는 ZapEnabled 매개 변수에서 더 이상 상속 되지 않습니다. 더 이상 사용 되지 않도록 설정 된 후에 ZapEnabled는 PhishZapEnabled 또는 SpamZapEnabled 속성에 영향을 주지 않으며 ZapEnabled가 cmdlet의 매개 변수 목록에서 제거 됩니다.

ZAP은 동적 배달 검색 프로세스에 있거나 대체 된 첨부 파일이 있는 맬웨어 결과 이미 있는 격리로 메시지를 이동 하지 않습니다. 이러한 유형의 메시지에 대 한 피싱 또는 스팸 신호를 수신 하 고 스팸 정책/피싱 작업이 몇 가지 작업을 수행 하도록 설정 된 경우 (정크로 이동, 리디렉션, 삭제, 격리), ZAP은 ' 정크로 이동 ' 작업을 기본으로 합니다. ZAP이 메시지에 대해 ' 정크로 이동 ' 작업을 수행 하려면 사용자에 게 정크 메일 보호를 사용 하도록 설정 하 고 기본 정크 메일 설정을 사용 해야 합니다. (Outlook의 사용자 옵션에 대 한 자세한 내용은 [정크 메일 필터의 보호 수준 변경을](https://support.office.com/article/e89c12d8-9d61-4320-8c57-d982c8d52f6b) 참조 하세요.)

## <a name="how-to-see-if-zap-moved-your-message"></a>메시지가 ZAP에서 이동 된 것을 확인 하는 방법

ZAP이 메시지를 이동 했는지 확인 하려면 [위협 방지 상태 보고서](../../compliance/view-email-security-reports.md#threat-protection-status-report) 또는 [위협 탐색기 (및 실시간 검색)](threat-explorer.md)를 사용할 수 있습니다.

## <a name="disable-zap"></a>ZAP 사용 안 함

Exchange Online PowerShell에 연결하려면 [Exchange Online PowerShell에 연결](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell)을 참조하세요. Exchange Online Protection PowerShell에 연결 하려면 [Exchange Online Protection powershell에 연결](https://docs.microsoft.com/powershell/exchange/exchange-eop/connect-to-exchange-online-protection-powershell)을 참조 하세요.

### <a name="disable-malware-zap"></a>맬웨어 ZAP 사용 안 함 * *

Exchange Online PowerShell 또는 Exchange Online Protection PowerShell에서 [get-malwarefilterpolicy](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/set-malwarefilterpolicy) Cmdlet의 *ZapEnabled* 매개 변수를 통해 맬웨어 ZAP을 사용 하지 않도록 설정할 수 있습니다. 보안 및 준수 센터에서 맬웨어 정책을 편집 하 여 맬웨어 ZAP을 사용 하거나 사용 하지 않도록 설정할 수도 있습니다.

이 예에서는 "Test" 라는 맬웨어 필터 정책에서 ZAP을 사용 하지 않도록 설정 합니다.

```Powershell
Set-MalwareFilterPolicy -Identity Test -ZapEnabled $false
```

구문 및 매개 변수에 대 한 자세한 내용은 [get-malwarefilterpolicy](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/set-malwarefilterpolicy)를 참조 하십시오.

### <a name="disable-phish-zap-and-spam-zap"></a>피싱 ZAP 및 스팸 ZAP 사용 안 함

O365 테 넌 트에 대 한 피싱 및 스팸 ZAP을 사용 하지 않도록 설정 하거나, 사용자 집합 [을 설정 하려면](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/Set-HostedContentFilterPolicy)EOP cmdlet *PhishZapEnabled* 및 *SpamZapEnabled* 매개 변수를 사용 합니다.

다음 예제에서는 "Test" 라는 콘텐츠 필터 정책에 대해 피싱 및 스팸 ZAP을 사용 하지 않도록 설정 합니다.

```Powershell
Set-HostedContentFilterPolicy -Identity Test -PhishZapEnabled $false -SpamZapEnabled $false
```

구문 및 매개 변수에 대 한 자세한 내용은 [get-hostedcontentfilterpolicy](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/Set-HostedContentFilterPolicy)를 참조 하십시오.

## <a name="faq"></a>FAQ

### <a name="what-happens-if-a-legitimate-message-is-moved-to-the-junk-mail-folder"></a>합법적인 메시지를 정크 메일 폴더로 이동 하면 어떻게 되나요?

[가양성](../../compliance/prevent-email-from-being-marked-as-spam.md)에 대 한 일반 보고 프로세스를 따라야 합니다. 메시지를 받은 편지함에서 정크 메일 폴더로 이동 하는 유일한 이유는 서비스가 스팸 또는 악성 메시지를 받는 것으로 확인 되었기 때문입니다.

### <a name="what-if-i-use-the-office-365-quarantine-instead-of-the-junk-mail-folder"></a>정크 메일 폴더 대신 Office 365 검역을 사용 하는 경우에는 어떻게 하나요?

스팸 방지 정책에서 피싱 및 스팸 작업 설정 구성에 따라 작업을 수행 합니다. 맬웨어, 피싱 및 스팸 ZAP에 대 한 자세한 내용은 위를 참조 하세요.

### <a name="what-if-i-have-a-custom-mail-flow-rule-block-allow-rule"></a>사용자 지정 메일 흐름 규칙 (차단/허용 규칙)이 있는 경우 어떻게 하나요?

관리자가 만든 규칙 (메일 흐름 규칙) 또는 차단 및 허용 규칙을 우선적으로 사용 합니다. 이러한 메시지는 기능 조건에서 제외 되므로 메일 흐름은 규칙 동작 (차단/허용 규칙)을 따릅니다.

### <a name="what-if-a-message-is-moved-to-another-folder-eg-inbox-rule"></a>다른 폴더 (예: 받은 편지함 규칙)로 메시지를 이동 하는 경우

메시지가 삭제 되었거나 정크 상태인 경우가 아니면이 경우에도 ZAP이 작동 합니다.

## <a name="related-topics"></a>관련 주제

[Office 365 이메일 스팸 방지 보호](anti-spam-protection.md)

[Office 365 스팸 필터로 전자 메일 스팸을 차단하여 거짓 부정 문제 방지](reduce-spam-email.md)
