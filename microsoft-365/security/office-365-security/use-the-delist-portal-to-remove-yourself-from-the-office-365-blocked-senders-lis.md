---
title: 수신 거부 목록에서 본인 제거
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 04/18/2016
audience: ITPro
ms.topic: troubleshooting
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 0bcecdd4-3343-4cc0-9e58-e19d4de515e8
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
ms.custom:
- seo-marvel-apr2020
description: 이 문서에서는 목록 해제 포털을 사용 하 여 Microsoft 365 수신 거부 목록에서 자신을 제거 하는 방법에 대해 설명 합니다.
ms.openlocfilehash: f4e7bcc13ac6c133880eb0ebe69ba3f724d0a84e
ms.sourcegitcommit: 4debeb8f0fce67f361676340fc390f1b283a3069
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/03/2020
ms.locfileid: "49561426"
---
# <a name="use-the-delist-portal-to-remove-yourself-from-the-blocked-senders-list"></a>목록 해제 포털을 사용하여 수신 거부 목록에서 본인 제거

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


전자 메일 주소가 Microsoft 365에 있는 받는 사람에 게 전자 메일을 보내려고 할 때 오류 메시지가 발생 하나요? 오류 메시지가 나타나지 않는다고 생각 되 면 목록 해제 포털을 사용 하 여 수신 거부 목록에서 본인을 제거할 수 있습니다.

## <a name="what-is-the-blocked-senders-list"></a>수신 거부 목록 이란?

Microsoft는 수신 거부 목록을 사용하여 스팸, 스푸핑 및 피싱 공격으로부터 고객을 보호합니다. 메일 서버의 IP 주소, 즉 메일 서버가 인터넷에서 자신을 식별 하는 데 사용 하는 주소에는 다양 한 이유로 Microsoft 365의 잠재적 위협에 대 한 태그가 지정 되어 있습니다. Microsoft 365이 목록에 IP 주소를 추가 하면 데이터 센터를 통해 IP 주소와 고객 간의 모든 추가 통신을 차단 합니다.

다음과 같은 오류가 포함된 메일 메시지에 대한 응답이 수신되면 이 목록에 본인이 추가된 것입니다.

> 550 5.7.606-649 액세스 거부, 금지 된 보낸 IP [_ip 주소_]; 이 목록에서 제거를 요청 하려면을 방문 <https://sender.office.com/> 하 여 지침을 따르세요. 자세한 내용은 [Exchange Online의 전자 메일 배달 못 함 보고서](https://docs.microsoft.com/Exchange/mail-flow-best-practices/non-delivery-reports-in-exchange-online/non-delivery-reports-in-exchange-online)를 참조 하세요.

여기서  _IP address_ 는 메일 서버가 실행되는 컴퓨터의 IP 주소입니다.

### <a name="to-use-delist-portal-to-remove-yourself-from-the-blocked-senders-list"></a>목록 해제 포털을 사용 하 여 수신 거부 목록에서 본인을 제거 하려면

1. 웹 브라우저에서 <https://sender.office.com>으로 이동합니다.

2. 페이지의 지시를 따릅니다. 오류 메시지가 전송된 전자 메일 주소와 오류 메시지에 지정된 IP 주소를 사용하고 있는지 확인합니다. 방문할 때마다 하나의 전자 메일 주소 및 하나의 IP 주소만 입력할 수 있습니다.

3. **전송** 을 클릭합니다.

    포털에서는 사용자가 제공한 전자 메일 주소로 전자 메일을 보냅니다. 전자 메일은 다음과 같이 표시 됩니다. ![ 목록 해제 포털을 통해 요청을 제출할 때 받는 전자 메일의 스크린샷](../../media/bf13e4f7-f68c-4e46-baa7-b6ab4cfc13f3.png)

4. 목록 해제 포털을 사용하여 사용자에게 전송된 전자 메일의 확인 링크를 클릭합니다.

    그러면 목록 해제 포털로 돌아갑니다.

5. 목록 해제 포털에서 **IP 목록 해제** 를 클릭합니다.

    차단 된 보낸 사람 목록에서 IP 주소를 제거한 후에는 해당 IP 주소에서 보낸 전자 메일 메시지가 Microsoft 365을 사용 하는 받는 사람에 게 배달 됩니다. 따라서 해당 IP 주소에서 보낸 전자 메일은 악성이 되거나 악성 메일이 아닐 수도 있습니다. 그렇지 않으면 IP 주소가 다시 차단 될 수 있습니다.

    > [!NOTE]
    > 제한이 제거 되기 전에 최대 24 시간이 걸릴 수도 있고 결과가 크게 다를 수 있습니다.

IP가 차단 되지 않도록 하려면 EOP 및 [EOP의 아웃 바운드 스팸 방지](outbound-spam-controls.md) [에서 수신 허용-보낸 사람 목록 만들기](create-safe-sender-lists-in-office-365.md) 를 참조 하세요.
