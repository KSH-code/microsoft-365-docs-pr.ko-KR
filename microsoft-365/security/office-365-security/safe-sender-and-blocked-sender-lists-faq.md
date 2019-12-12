---
title: Exchange Online에서의 안전한 발신자 및 차단된 발신자 목록
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
audience: ITPro
ms.topic: reference
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 111ab6b0-2dd2-4a87-a928-4931df6b3c4d
ms.collection:
- M365-security-compliance
description: Exchange Online 또는 EOP (Exchange Online Protection) 관리자는 서비스를 통과 하는 전자 메일 메시지가 스팸으로 표시 되지 않도록 할 수 있습니다. 이 작업을 수행 하는 한 가지 방법은 조직의 사용자에 대해 수신 허용-보낸 사람 및 수신 거부 목록을 만드는 것입니다.
ms.openlocfilehash: 5530fa8c8ee5a83c4e8515a8f31f91e45b2ec97b
ms.sourcegitcommit: 5710ce729c55d95b8b452d99ffb7ea92b5cb254a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/11/2019
ms.locfileid: "39971676"
---
# <a name="safe-sender-and-blocked-sender-lists-in-exchange-online"></a>Exchange Online에서의 안전한 발신자 및 차단된 발신자 목록

Exchange Online 또는 EOP (Exchange Online Protection) 관리자는 서비스를 통과 하는 전자 메일 메시지가 스팸으로 표시 되지 않도록 할 수 있습니다. 이 작업을 수행 하는 한 가지 방법은 조직의 사용자에 대해 수신 허용-보낸 사람 및 수신 거부 목록을 만드는 것입니다.

[Office 365에서 전자 메일이 스팸으로 표시 되지 않도록](https://docs.microsoft.com/microsoft-365/compliance/prevent-email-from-being-marked-as-spam)하는 방법에서 이러한 목록을 관리자로 사용 하는 *방법에 대 한 업데이트 된 버전의 팁 및 절차를 참조 하세요* .

관리자가 아닌 경우 Outlook에서 수신 허용-보낸 사람 목록을 사용 하 여 자신의 정크 메일을 관리 하려면[정크 메일 필터 개요](https://support.office.com/article/5ae3ea8e-cf41-4fa0-b02a-3b96e21de089)의 단계를 확인 합니다.

## <a name="what-is-the-safe-and-blocked-sender-limits-in-exchange-online"></a>Exchange Online에서 수신 허용 및 차단 된 보낸 사람 제한은 무엇입니까?

Exchange Online의 수신 및 차단 된 보낸 사람 제한은 Active Directory 및 Outlook 제한과 다릅니다. 해당 지식 영역은 다음과 같습니다.

- 수신 허용-보낸 사람 제한: 1024

- 차단 된 보낸 사람 제한: 500

참고:

[KB2590466](https://support.microsoft.com/help/2590466/you-receive-the-error-junk-e-mail-validation-error-in-outlook-web-app)에 설명 되어 있는 오류가 발생할 수 있습니다. 이 문제를 해결 하려면 "내 연락처에서 전자 메일 신뢰" 확인란의 선택을 취소 합니다. 또는 "MaxSafeSenders" 특성에 대해 설정 된 Exchange Online에서 허용 되는 최대 제한인 1024에 표시 되도록 기본 연락처 폴더에 있는 전자 메일 주소 크기를 줄일 수 있습니다. 이 특성 및 사서함 cmdlet에 대 한 자세한 내용은 다음 항목을 slmgr.vbs.

[Set-Mailbox](https://docs.microsoft.com/powershell/module/exchange/mailboxes/Set-Mailbox)

## <a name="see-also"></a>참고 항목

[Exchange Server의 보낸 사람 필터링](https://docs.microsoft.com/exchange/antispam-and-antimalware/antispam-protection/sender-filtering)
