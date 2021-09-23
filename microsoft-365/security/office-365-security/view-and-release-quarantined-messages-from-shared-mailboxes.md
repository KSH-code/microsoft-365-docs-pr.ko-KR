---
title: 공유 사서함에서 분리된 메시지 보기 및 릴리스
ms.author: chrisda
author: chrisda
manager: dansimp
ms.reviewer: ''
ms.date: ''
audience: ITPro
ms.topic: how-to
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: ''
ms.collection:
- M365-security-compliance
ROBOTS: NOINDEX
description: 사용자는 사용 권한이 있는 공유 사서함으로 전송된 분리된 메시지를 보고 해당 메시지를 보는 방법을 배울 수 있습니다.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: fae8ad995f5edb4735ecd62ba04a358da2769157
ms.sourcegitcommit: 0ed93816e2c1e6620e68bd1c0f00390062911606
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/23/2021
ms.locfileid: "59484086"
---
# <a name="view-and-release-quarantined-messages-from-shared-mailboxes"></a>공유 사서함에서 분리된 메시지 보기 및 릴리스

> [!NOTE]
> 이 문서에서 설명하는 기능은 현재 미리 보기로 제공되어 있으며 모든 사람이 사용할 수 있으며 변경될 수 있습니다.

사용자는 [EOP에서](find-and-release-quarantined-messages-as-a-user.md)사용자로 검색 및 릴리스에 설명된 바와 같이 받는 사람 중 한 에 있는 분리된 메시지를 관리할 수 있습니다. 그러나 사용자가 **사서함의** 공유 사서함에 설명된 모든 권한 및 다른 사람으로 보내기 또는 대신 보내기 권한이 있는 공유 사서함은 [Exchange Online.](/exchange/collaboration-exo/shared-mailboxes)

이전에는 사용자가 공유 사서함에 전송된 분리된 메시지를 관리할 수 있는 기능을 사용하려면 관리자가 공유 사서함에 대해 automapping을 사용하도록 설정(관리자가 다른 사서함에 대한 액세스 권한을 사용자에게 부여할 때 기본적으로 사용하도록 설정)을 유지해야 합니다. 그러나 사용자가 액세스할 수 있는 사서함의 크기와 수에 따라 Outlook에서 사용자가 액세스할 수  있는 모든 사서함을 열려고 할 때 성능이 아날 수 있습니다. 이러한 이유로 많은 관리자가 공유 [사서함에 대한 automapping을 제거하기로 선택했습니다.](/outlook/troubleshoot/profiles-and-accounts/remove-automapping-for-shared-mailbox)

이제 사용자가 공유 사서함으로 전송된 고지된 메시지를 관리하기 위해 더 이상 automapping이 필요하지 않습니다. 작동하기만 합니다. 공유 사서함에 전송된 서로 다른 두 가지 방법으로는 서로 다른 두 가지 방법으로 메시지에 액세스할 수 있습니다.

- 관리자가 스팸 알림(이전의 최종 사용자 스팸 알림)을 허용하도록 검사 정책을 구성한 경우 공유 사서함의 검지 알림에 액세스할 수 있는 모든  사용자는 알림의 검토 단추를 클릭하여 Microsoft 365 Defender 포털에서 검사로 이동하면 됩니다. [](quarantine-policies.md) 이 방법을 사용하면 사용자가 공유 사서함으로 전송된 분리된 메시지만 관리할 수 있습니다. 사용자는 이 컨텍스트에서 자체적으로 메시지를 관리할 수 없습니다.
- 사용자는 사이트 포털 에서 [검사로 Microsoft 365 Defender 있습니다.](find-and-release-quarantined-messages-as-a-user.md) 기본적으로 사용자에게 전송된 메시지만 표시됩니다. 그러나 정렬 결과(메시지  ID 단추 기본적으로 메시지 **ID** 단추)를 받는 사람 전자 메일 주소로 변경하고 **공유** 사서함 전자 메일 주소를 입력한 다음 새로 고침을 클릭하여 공유 사서함으로 전송된 고지된 메시지를 볼 수 있습니다. 

  ![받는 사람 전자 메일 주소로 quarantined 메시지를 정렬합니다.](../../media/quarantine-sort-results-by-recipient-email-address.png)

방법과 관계없이 사용자는 받는 사람 열을  사용하여 분리된 메시지에 대해 혼동을 피할 수 있습니다. 표시할 최대 열 수는 7개이기 때문에 사용자가 열 **수정을** 클릭하고 기존 열을 제거(예: 정책 **유형),** 받는 사람 을 선택한 다음 저장 **또는** 기본으로 저장을 **클릭해야 합니다.**

  ![정책 유형 열을 제거하고 받는 사람 열을 분리합니다.](../../media/quarantine-add-recipient-column.png)

## <a name="things-to-keep-in-mind"></a>주의 사항

- _Quarantine policies_ define what users are allowed to do or not do to quarantined messages based on why the message was quarantined why the message was quarantined (for supported features). 기본 검역 정책은 받는 사람이 메시지를 보고 이에 대해 행동할 수 있도록 기록 기능을 적용합니다. 관리자는 사용자에 대해 덜 제한적이거나 더 제한적인 기능을 정의하는 사용자 지정 검지 정책을 만들고 적용할 수 있습니다. 자세한 내용은 [Quarantine policies 을 참조하십시오.](quarantine-policies.md)

- 분리된 메시지에 대한 첫 번째 사용자가 공유 사서함을 사용하는 모든 사용자의 메시지의 결정에 따라 결정됩니다. 예를 들어 10명 사용자가 공유 사서함에 액세스하고 사용자가 메시지를 삭제하기로 결정하면 10명 모두에 대해 메시지가 삭제됩니다. 마찬가지로 사용자가 메시지를 해제하기로 결정한 경우 공유 사서함에 릴리스된 후 공유 사서함의 다른 모든 사용자가 액세스할 수 있습니다.

- 현재 공유  사서함으로 전송된 고지된  메시지에 대한 세부 정보 플라이아웃에서 보낸 사람 차단 단추를 사용할 수 없습니다.

- 공유 사서함에 대한 검지 작업과 관련하여 중첩된 보안 그룹을 사용하여 공유 사서함에 대한 액세스 권한을 부여하는 경우 중첩된 그룹의 수준은 두 개를 넘지하는 것이 좋습니다. 예를 들어 그룹 A는 그룹 C의 구성원인 그룹 B의 구성원입니다. 공유 사서함에 사용 권한을 할당하려면 그룹을 A에 추가한 다음 그룹 C를 공유 사서함에 할당하지 않습니다.  

- Exchange Online [PowerShell에서](/powershell/exchange/connect-to-exchange-online-powershell)공유 사서함에 대해 quarantined messages를 관리하려면 최종 사용자는 _RecipientAddress_ 매개 변수 값에 대해 공유 사서함 전자 메일 주소와 함께 [Get-QuarantineMessage](/powershell/module/exchange/get-quarantinemessage) cmdlet을 사용하여 메시지를 식별해야 합니다. 예제:

  ```powershell
  Get-QuarantinedMessage -RecipientAddress officeparty@contoso.com
  ```

  그런 다음 최종 사용자는 목록에서 분리된 메시지를 선택하여 보거나 조치를 취할 수 있습니다.

  이 예에서는 공유 사서함으로 전송된 모든 고지된 메시지를 보여 주며 목록의 첫 번째 메시지는 0, 두 번째 메시지는 1이 됩니다.

  ```powershell
  $SharedMessages = Get-QuarantinedMessage -RecipientAddress officeparty@contoso.com | select -ExpandProperty Identity
  $SharedMessages
  Release-QuarantinedMessage -Identity $SharedMessages[0]
  ```

  구문 및 매개 변수에 대한 자세한 내용은 다음 항목을 참조하십시오.

  - [Get-QuarantineMessage](/powershell/module/exchange/get-quarantinemessage)
  - [Get-QuarantineMessageHeader](/powershell/module/exchange/get-quarantinemessageheader)
  - [Preview-QuarantineMessage](/powershell/module/exchange/preview-quarantinemessage)
  - [Release-QuarantineMessage](/powershell/module/exchange/release-quarantinemessage)
