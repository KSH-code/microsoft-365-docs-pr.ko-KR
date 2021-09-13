---
title: 수신이 차단된 보낸 사람 목록에서 자신을 제거합니다.
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 04/18/2016
audience: ITPro
ms.topic: troubleshooting
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 0bcecdd4-3343-4cc0-9e58-e19d4de515e8
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
ms.custom:
- seo-marvel-apr2020
description: 이 문서에서는 목록 제거 포털을 사용하여 수신 차단된 보낸 사람 목록에서 Microsoft 365 방법을 배우게 됩니다.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 0e825c859253b759e5436dbc5419f98f0c863fa3
ms.sourcegitcommit: d08fe0282be75483608e96df4e6986d346e97180
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/12/2021
ms.locfileid: "59213215"
---
# <a name="use-the-delist-portal-to-remove-yourself-from-the-blocked-senders-list"></a>목록 해제 포털을 사용하여 수신 거부 목록에서 본인 제거

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**적용 대상**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Office 365용 Microsoft Defender 플랜 1 및 플랜 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

전자 메일 주소가 전자 메일 주소가 전자 메일 주소에 있는 받는 사람에게 전자 메일을 보내려고 할 때 Microsoft 365? 오류 메시지가 수신되지 않는 것으로 생각될 경우 목록 제거 포털을 사용하여 수신 차단된 보낸 사람 목록에서 자신을 제거할 수 있습니다.

## <a name="what-is-the-blocked-senders-list"></a>수신이 차단된 보낸 사람 목록이란?

Microsoft는 수신 거부 목록을 사용하여 스팸, 스푸핑 및 피싱 공격으로부터 고객을 보호합니다. 메일 서버의 IP 주소, 즉 메일 서버가 인터넷에서 자체를 식별하는 데 사용하는 주소는 다양한 Microsoft 365 위협으로 태그가 지정되어 있습니다. 이 Microsoft 365 IP 주소를 목록에 추가하면 데이터 센터를 통해 IP 주소와 모든 고객 간의 추가 통신이 차단됩니다.

다음과 같은 오류가 포함된 메일 메시지에 대한 응답이 수신되면 이 목록에 본인이 추가된 것입니다.

> 550 5.7.606-649 액세스 거부, 금지된 보내는 IP [_IP 주소];_ 이 목록에서 제거를 요청하기 위해 <https://sender.office.com/> 방문하여 지침을 따르하세요. 자세한 내용은 에서 [전자 메일 배달되지 않은 보고서 Exchange Online.](/Exchange/mail-flow-best-practices/non-delivery-reports-in-exchange-online/non-delivery-reports-in-exchange-online)

여기서  _IP address_ 는 메일 서버가 실행되는 컴퓨터의 IP 주소입니다.

### <a name="to-use-delist-portal-to-remove-yourself-from-the-blocked-senders-list"></a>목록 제거 포털을 사용하여 수신 차단된 보낸 사람 목록에서 자신을 제거하려면

1. 웹 브라우저에서 <https://sender.office.com>으로 이동합니다.

2. 페이지의 지시를 따릅니다. 오류 메시지가 전송된 전자 메일 주소와 오류 메시지에 지정된 IP 주소를 사용하고 있는지 확인합니다. 방문할 때마다 하나의 전자 메일 주소 및 하나의 IP 주소만 입력할 수 있습니다.

3. **전송** 을 클릭합니다.

    포털에서는 사용자가 제공한 전자 메일 주소로 전자 메일을 보냅니다. 이 전자 메일은 다음과 유사합니다.

    ![목록 목록 해지 포털을 통해 요청을 제출할 때 받은 전자 메일의 스크린샷입니다.](../../media/bf13e4f7-f68c-4e46-baa7-b6ab4cfc13f3.png)

4. 목록 해제 포털을 사용하여 사용자에게 전송된 전자 메일의 확인 링크를 클릭합니다.

    그러면 목록 해제 포털로 돌아갑니다.

5. 목록 해제 포털에서 **IP 목록 해제** 를 클릭합니다.

    IP 주소가 수신 차단된 보낸 사람 목록에서 제거되면 해당 IP 주소의 전자 메일 메시지가 해당 주소를 사용하는 받는 사람에게 Microsoft 365. 따라서 해당 IP 주소에서 보낸 전자 메일이 악의적이지 않은지 확신해야 합니다. 그렇지 않으면 IP 주소가 다시 차단될 수 있습니다.

    > [!NOTE]
    > 최대 24시간이 걸릴 수 있습니다. 제한이 제거되기 전에 결과가 크게 달라질 수 있습니다.

[IP가 차단되지](create-safe-sender-lists-in-office-365.md) 않도록 방지하는 [EOP](outbound-spam-controls.md) 및 아웃바운드 스팸 보호에서 안전한 보낸 사람 목록 만들기를 참조하세요.

## <a name="more-information"></a>추가 정보

**Outlook.com에 대한 목록이 없는 양식인 소비자 서비스는 에서** 찾을 수 [있습니다.](https://support.microsoft.com/supportrequestform/8ad563e3-288e-2a61-8122-3ba03d6b8d75) 제출 방향에 대한 [FAQ를](https://sendersupport.olc.protection.outlook.com/pm/troubleshooting.aspx) 먼저 *읽어야* 합니다.
