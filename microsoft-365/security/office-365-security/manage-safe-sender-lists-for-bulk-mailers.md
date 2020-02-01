---
title: 대량 메일에 대해 수신 허용 - 보낸 사람 목록 관리
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 11/17/2014
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: d48db4a3-9fbe-45e2-bbaa-1017ffdf96f8
ms.collection:
- M365-security-compliance
description: '안전한 보낸 사람 목록을 사용 하려는 경우에는 EOP (Exchange Online Protection) 및 Outlook 처리가 서로 다르게 처리 된다는 사실을 알아야 합니다. 이 서비스는 rfc 5321 보낸 사람 주소와 RFC 5322.from 주소의을 검사 하 여 수신 허용-보낸 사람 및 도메인을 고려 하 고, Outlook에서는 RFC 5322.from 주소의 주소를 사용자의 수신 허용-발신자 목록에 추가 합니다. (참고: 서비스는 차단 된 보낸 사람 주소 및 도메인에 대 한 5321 주소와 5322.from 주소의 from address)를 모두 검사 합니다.'
ms.openlocfilehash: aaede7cab2e640603c20804f4015e19f61b6c2f3
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/29/2020
ms.locfileid: "41598945"
---
# <a name="manage-safe-sender-lists-for-bulk-mailers"></a>대량 메일에 대해 수신 허용 - 보낸 사람 목록 관리

안전한 보낸 사람 목록을 사용 하려는 경우에는 EOP (Exchange Online Protection) 및 Outlook 처리가 서로 다르게 처리 된다는 사실을 알아야 합니다. Office 365 서비스는 주소와 `RFC 5321.MailFrom` `RFC 5322.From` 주소를 검사 하 여 수신 허용-보낸 사람 및 도메인을 사용 하므로 `RFC 5322.From` Outlook에서 사용자의 수신 허용-보낸 사람 목록에 주소를 추가 합니다. (참고: 서비스가 차단 된 보낸 사람 `5321.MailFrom` 및 도메인 `5322.From` 에 대 한 주소와 주소를 모두 검사 합니다.)

`RFC 5321.MailFrom address`이 주소는 `SMTP MAIL FROM` SPF 검사를 수행 하는 데 사용 되는 전자 메일 주소이 고, 메일을 배달할 수 없는 경우 반송 메시지가 배달 되는 경로입니다. 이 전자 메일 주소는 보낸 사람이 다른 `Return-Path` `Return-Path` 주소를 지정할 수 있지만 메시지 헤더의에 기본적으로 포함 됩니다.

주소 라는 메시지 헤더의 `From:` 주소는 Outlook과 같은 메일 클라이언트에 표시 되는 전자 메일 주소입니다. `RFC 5322.From`

많은 시간과 `5321.MailFrom` `5322.From` 주소가 동일 합니다. 이는 사용자 간 통신에 일반적으로 발생 합니다. 그러나 다른 사람을 대신 하 여 전자 메일을 보내는 경우에는 주소가 서로 다를 수 있습니다. 일반적으로 대량 전자 메일 메시지에서 가장 자주 발생 합니다.

예를 들어 파란색 Yonder Airlines가 손 정 란 여행사를 고용 하 여 전자 메일 광고를 보내도록 가정 합니다. 그런 다음 보낸 사람 blueyonder@news.blueyonderairlines.com에서 받은 편지함에 메시지를 받습니다. 이 예제의 특징은 다음과 같습니다.

- 주소 `5321.MailFrom` 는 blueyonder.airlines@margiestravel.com입니다.

- 주소 `5322.From` 는 blueyonder@news.blueyonderairlines.com, 즉 Outlook에서 볼 수 있습니다.

이 메시지가 필터링 되지 않도록 하려면 다음을 수행할 수 있습니다.

- **사용자**: Outlook에서 수신 허용 `RFC 5322.From` -보낸 사람으로 주소를 추가 합니다.

- **관리자**: [메일 흐름 규칙](anti-spam-protection.md#beyond-the-basics-more-ways-to-prevent-spam-in-office-365) (전송 규칙이 라고도 함)을 설정 합니다.
