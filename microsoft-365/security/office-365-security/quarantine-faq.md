---
title: Quarantined messages FAQ
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
- m365initiative-m365-defender
description: 관리자는 EOP(Exchange Online Protection)에서 자주 묻는 질문과 대답을 볼 수 있습니다.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 9cf1281338de66f54a6c4546b047259d647cc3ea
ms.sourcegitcommit: ee39faf3507d0edc9497117b3b2854955c959c6c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/10/2020
ms.locfileid: "49615999"
---
# <a name="quarantined-messages-faq"></a>Quarantined messages FAQ

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


이 항목에서는 Exchange Online 사서함이 있는 Microsoft 365 조직 또는 Exchange Online 사서함이 없는 독립 실행형 EOP(Exchange Online Protection) 조직에 대해 자주 묻는 질문과 대답을 제공합니다.

스팸 방지 보호에 대한 질문과 대답은 스팸 방지 보호 [FAQ를 참조하세요.](anti-spam-protection-faq.md)

맬웨어 방지 보호에 대한 질문과 대답은 맬웨어 방지 [보호 FAQ를 참조하세요.](anti-malware-protection-faq-eop.md)

스푸핑 방지 보호에 대한 질문과 대답은 스푸핑 방지 보호 [FAQ를 참조하세요.](anti-spoofing-protection-faq.md)

## <a name="how-do-i-manage-messages-that-were-quarantined-for-malware"></a>맬웨어에 대해 고지된 메시지는 어떻게 관리하나요?

관리자만 맬웨어에 대해 고지된 메시지를 관리할 수 있습니다. 자세한 내용은 관리자로 [quarantined messages and files를 참조하십시오.](manage-quarantined-messages-and-files.md)

## <a name="how-do-i-quarantine-spam"></a>스팸을 어떻게 차단하나요?

기본적으로 스팸 필터링을 통해 스팸 또는 대량 전자 메일로 분류된 메시지는 사용자의 사서함으로 배달되어 정크 메일 폴더로 이동됩니다. 그러나 스팸 또는 대량 전자 메일 메시지를 대신 차단하도록 스팸 방지 정책을 만들고 구성할 수 있습니다. 자세한 내용은 [EOP에서 스팸 방지 정책 구성하기](configure-your-spam-filter-policies.md)를 참조하세요.

## <a name="how-do-i-give-users-access-to-the-quarantine"></a>사용자에게 검지 액세스 권한을 부여하는 방법

사용자는 자신의 메시지에 액세스하려면 유효한 계정이 있어야 합니다. 독립 실행형 EOP를 사용하려면 사용자가 EOP에서 메일 사용자로 표시됩니다(디렉터리 동기화를 통해 수동으로 만들거나 생성). 독립 실행형 EOP 환경에서 사용자를 관리하는 데 대한 자세한 내용은 [EOP에서 메일 사용자 관리를 참조하십시오.](manage-mail-users-in-eop.md)

## <a name="what-messages-can-end-users-access-in-quarantine"></a>최종 사용자가 어떤 메시지에 액세스하여 액세스할 수 있나요?

사용자는 스팸, 대량 전자 메일 및 받는 사람인 피싱 메시지(2020년 4월 현재)에 액세스할 수 있습니다. 최종 사용자는 메일 흐름 규칙(전송 규칙)에서 호스트된 차단 작업으로 메시지를 배달하여 고지된 맬웨어, 높은 신뢰도 피싱 또는 메시지에 액세스할 수 없습니다.  Quarantined Messages에 액세스하는 사용자에 대한 자세한 내용은 사용자로 고지된 메시지 찾기 및 [릴리스를 참조하세요.](find-and-release-quarantined-messages-as-a-user.md)

## <a name="how-long-are-messages-kept-in-the-quarantine"></a>메시지가 얼마나 오래 보관하나요?

스팸 방지 정책을 사용하여 스팸, 피싱 및 대량 전자 메일 메시지가 보관된 기간을 구성합니다. 기본값은 최대 30일입니다. 자세한 내용은 EOP에서 스팸 방지 [정책 구성을 참조하세요.](configure-your-spam-filter-policies.md)

메일 흐름 규칙 동작에 의해 검리된 메시지의 경우 메시지를 호스팅된 검지로 배달하면 메시지는 30일 동안 보관됩니다.  이 기간은 구성할 수 없습니다.

기간이 만료되면 메시지가 삭제되고 복구할 수 없습니다.

## <a name="can-i-release-or-report-more-than-one-quarantined-message-at-a-time"></a>한 번에 2개 이상의 격리된 메시지를 해제하거나 보고할 수 있습니까?

보안 & 준수 센터에서 한에 최대 100개 메시지를 선택하고 릴리스할 수 있습니다.

관리자는 Exchange Online PowerShell 또는 독립 실행형 EOP PowerShell에서 [Get-QuarantineMessage](https://docs.microsoft.com/powershell/module/exchange/get-quarantinemessage) 및 [Release-QuarantineMessage](https://docs.microsoft.com/powershell/module/exchange/release-quarantinemessage) cmdlet을 사용하여 대량으로 독립 실행형 메시지를 찾아서 릴리스하고 가짓 긍정을 대량으로 보고할 수 있습니다.

## <a name="are-wildcards-supported-when-searching-for-quarantined-messages-can-i-search-for-quarantined-messages-for-a-specific-domain"></a>격리된 메시지 검색 시 와일드카드가 지원됩니까? 특정 도메인에 대해 격리된 메시지를 검색할 수 있습니까?

와일드카드는 보안 및 준수 센터에서 & 없습니다. 예를 들어 보낸 사람 검색 시 전체 전자 메일 주소를 지정해야 합니다. 그러나 Exchange Online PowerShell 또는 독립 실행형 EOP PowerShell에서 와일드카드를 사용할 수 있습니다.

예를 들어 다음 명령을 실행하여 도메인에 있는 모든 보낸 사람이 보낸 스팸으로 contoso.com.

```powershell
$CQ = Get-QuarantineMessage -Type Spam | where {$_.SenderAddress -like "*@contoso.com"}
```

그런 다음 다음 명령을 실행하여 모든 원래 받는 사람에게 해당 메시지를 해제합니다.

```powershell
$CQ | foreach {Release-QuarantineMessage -Identity $_.Identity -ReleaseToAll}
```

메시지를 릴리스한 후 다시 릴리스할 수 없습니다.
