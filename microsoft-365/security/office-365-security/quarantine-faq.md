---
title: 격리된 메시지 FAQ
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: troubleshooting
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: c440b2ac-cafa-4be5-ba4c-14278a7990ae
ms.collection:
- M365-security-compliance
description: 관리자는 EOP(Exchange Online Protection)에서 격리된 메시지에 대한 질문과 대답을 볼 수 있습니다.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 896a83d4a09e8d0fcafeb6885cf2c63b6d8bb045
ms.sourcegitcommit: e12fa502bc216f6083ef5666f693a04bb727d4df
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/20/2020
ms.locfileid: "46826792"
---
# <a name="quarantined-messages-faq"></a>격리된 메시지 FAQ

이 항목에서는 Exchange Online 사서함이 있는 Microsoft 365 조직 또는 Exchange Online 사서함이 없는 독립 실행형 EOP(Exchange Online Protection) 조직에 대해 격리된 전자 메일 메시지에 대한 질문과 대답을 제공합니다.

스팸 방지 보호 기능에 대한 질문과 대답은 스팸 [방지 보호 FAQ를 참조하세요.](anti-spam-protection-faq.md)

맬웨어 방지 보호에 대한 질문과 대답은 맬웨어 [방지 보호 FAQ를 참조하세요.](anti-malware-protection-faq-eop.md)

스푸핑 방지 보호 기능에 대한 질문과 대답은 [스푸핑 방지 보호 기능 FAQ를 참조하세요.](anti-spoofing-protection-faq.md)

## <a name="how-do-i-manage-messages-that-were-quarantined-for-malware"></a>맬웨어에 대해 격리된 메시지를 관리하는 방법은 무엇인가요?

관리자만 맬웨어에 대해 격리된 메시지를 관리할 수 있습니다. 자세한 내용은 [격리된 메시지 및 파일관리를 관리자로 관리하여 참조하세요.](manage-quarantined-messages-and-files.md)

## <a name="how-do-i-quarantine-spam"></a>스팸을 격리하려면 어떻게 해야 하나요?

기본적으로 스팸 또는 스팸 필터링을 통해 스팸으로 분류된 대량 전자 메일로 분류된 메시지는 사용자의 사서함에 배달되며 정크 메일 폴더로 이동됩니다. 그러나 스팸 이나 대량 전자 메일 메시지를 격리하도록 스팸 방지 정책을 만들고 구성할 수는 있습니다. 자세한 내용은 [EOP에서 스팸 방지 정책 구성하기](configure-your-spam-filter-policies.md)를 참조하세요.

## <a name="how-do-i-give-users-access-to-the-quarantine"></a>사용자에게 격리 액세스 권한을 어떻게 부여하나요?

사용자가 격리된 메시지에 액세스하려면 유효한 계정이 필요합니다. 독립 실행형 EOP를 사용하려면 사용자가 EOP에서 메일 사용자로 표현됩니다(디렉터리 동기화를 통해 수동으로 만들거나 만듭니다). 독립 실행형 EOP 환경에서 사용자를 관리하는 방법에 대한 자세한 내용은 EOP에서 [메일 사용자 관리를 참조하세요.](manage-mail-users-in-eop.md)

## <a name="what-messages-can-end-users-access-in-quarantine"></a>최종 사용자가 격리에 액세스할 수 있는 메시지는 무엇입니까?

사용자는 스팸, 대량 전자 메일 및 (2020년 4월을 바를 대상으로) 피싱 메시지에 액세스할 수 있습니다. 최종 사용자가 메일 흐름 규칙(전송 규칙이라고도 함)에서 호스트된 격리 작업으로 인해 격리된 맬웨어, 높은 신뢰도 **Deliver the message to the hosted quarantine** 피싱 또는 격리된 메시지에 액세스할 수 없습니다. 격리된 메시지에 액세스하는 사용자에 대한 자세한 내용은 격리된 메시지 찾기 및 [해제를 사용자로 받습니다.](find-and-release-quarantined-messages-as-a-user.md)

## <a name="how-long-are-messages-kept-in-the-quarantine"></a>메시지는 어떻게 격리에 보존됩니까?

스팸 방지 정책을 사용하여 스팸, 피싱 및 대량 전자 메일 메시지가 격리에 보관되는 시간을 구성합니다. 기본값은 30일이며 최대값입니다. 자세한 내용은 [EOP에서 스팸 방지 정책 구성을 참조하세요.](configure-your-spam-filter-policies.md)

메일 흐름 규칙 동작에 의해 격리된 메시지의 경우 메시지가 호스팅된 **격리로**배달된 메시지의 경우 메시지가 30일 동안 격리에 유지됩니다. 이 기간은 구성할 수 없습니다.

해당 기간이 만료되면 메시지가 삭제되며 복구할 수 없게 됩니다.

## <a name="can-i-release-or-report-more-than-one-quarantined-message-at-a-time"></a>한 번에 2개 이상의 격리된 메시지를 해제하거나 보고할 수 있습니까?

보안 설정 & 목록에서 최대 100개 메시지를 클릭하고 릴리스할 수 있습니다.

관리자는 Exchange Online PowerShell 또는 독립 실행형 EOP PowerShell의 [Get-QuarantineMessage](https://docs.microsoft.com/powershell/module/exchange/get-quarantinemessage) 및 [Release-QuarantineMessage](https://docs.microsoft.com/powershell/module/exchange/release-quarantinemessage) cmdlet을 사용하여 격리된 메시지를 대량으로 찾아 릴리스하고 가양성을 대량으로 보고할 수 있습니다.

## <a name="are-wildcards-supported-when-searching-for-quarantined-messages-can-i-search-for-quarantined-messages-for-a-specific-domain"></a>격리된 메시지 검색 시 와일드카드가 지원됩니까? 특정 도메인에 대해 격리된 메시지를 검색할 수 있습니까?

와일드카드는 보안 및 준수 센터에서 & 지원되지 않습니다. 예를 들어 보낸 사람을 검색할 때는 전체 전자 메일 주소를 지정해야 합니다. 그렇지만 Exchange Online PowerShell 또는 독립 실행형 EOP PowerShell에서 와일드카드를 사용할 수 있습니다.

예를 들어 다음 명령을 사용하여 도메인 나의 모든 보낸 사람으로부터 스팸 격리된 메시지를 contoso.com.

```powershell
$CQ = Get-QuarantineMessage -Type Spam | where {$_.SenderAddress -like "*@contoso.com"}
```

그런 다음 아래 명령을 실행하여 해당 메시지를 원래 받는 사람 모두로 릴리스합니다.

```powershell
$CQ | foreach {Release-QuarantineMessage -Identity $_.Identity -ReleaseToAll}
```

메시지를 해제한 후에는 다시 릴리스할 수 없습니다.
