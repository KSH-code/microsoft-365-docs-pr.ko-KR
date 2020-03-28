---
title: Office 365에서 차단 된 보낸 사람 목록 만들기
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
description: 관리자는 Office 365 및 EOP에서 사용 가능한 옵션에 대해 설명 하 여 인바운드 메시지를 차단할 수 있습니다.
ms.openlocfilehash: 0bfab3024bc781e53600092ebc88fae25c5f4afc
ms.sourcegitcommit: d00efe6010185559e742304b55fa2d07127268fa
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/28/2020
ms.locfileid: "43033425"
---
# <a name="create-blocked-sender-lists-in-office-365"></a>Office 365에서 차단 된 보낸 사람 목록 만들기

Exchange online 사서함이 없는 Office 365, 독립 실행형 EOP (Exchange Online Protection) 고객에 게 사서함이 있는 경우 EOP에서는 원치 않는 보낸 사람의 전자 메일을 차단 하는 여러 가지 방법을 제공 합니다. 스팸 방지 정책, Exchange 메일 흐름 규칙 (전송 규칙이 라고도 함), IP 차단 목록 (연결 필터링)의 Outlook 수신 거부, 차단 된 보낸 사람 목록 또는 차단 된 도메인 목록 등이 여기에 포함 됩니다. 이러한 옵션은 _차단 된 보낸 사람 목록_으로 간주할 수 있습니다.

보낸 사람을 차단 하는 최상의 방법은 영향 범위에 따라 다릅니다. 단일 사용자의 경우 적절 한 솔루션은 Outlook 수신 거부 일 수 있습니다. 대부분의 사용자는 다른 옵션 중 하나를 선택 하는 것이 더 좋습니다. 다음 옵션은 영향 범위와 범위로 순위가 지정 됩니다. 이 목록은 좁은 범위에서 광범위 하 게 제공 되지만, 전체 권장 사항 *에 대 한 자세한 내용은 여기* 에서 설명 합니다.

1. Outlook 차단 된 보낸 사람 (각 사서함에 저장 되는 수신 거부 목록)

2. 차단 된 보낸 사람 목록 또는 차단 된 도메인 목록 (스팸 방지 정책)

3. 메일 흐름 규칙

4. IP 차단 목록 (연결 필터링)

> [!NOTE]
> 조직 전체 차단 설정을 사용 하 여 거짓 네거티브 (부재 중 스팸)를 처리할 수 있지만 이러한 메시지를 분석을 위해 Microsoft로 제출 해야 합니다. 차단 목록을 사용 하 여 거짓 네거티브를 관리 하면 관리 오버 헤드가 크게 증가 합니다. 차단 목록을 사용 하 여 누락 된 스팸을 돌리기에는 준비 중에 항목 [보고서 메시지 및 파일을 Microsoft에](report-junk-email-messages-to-microsoft.md) 유지 해야 합니다.

반면에, 수신 허용- _보낸 사람 목록을_사용 하 여 특정 원본에서 전자 메일을 보낼 수 있는 몇 가지 옵션도 있습니다. 자세한 내용은 [Office 365에서 수신 허용-보낸 사람 목록 만들기](create-safe-sender-lists-in-office-365.md)를 참조 하세요.

## <a name="use-outlook-blocked-senders"></a>Outlook 수신 거부 사용

소수의 사용자만 원치 않는 전자 메일을 받은 경우 사용자 또는 관리자는 사서함의 수신 거부 목록에 보낸 사람 전자 메일 주소를 추가할 수 있습니다. 자세한 내용은 [Office 365에서 Exchange Online 사서함의 정크 메일 설정 구성을](configure-junk-email-settings-on-exo-mailboxes.md)참조 하세요.

사용자의 차단 된 보낸 사람 목록으로 인해 메시지가 성공적으로 차단 되 면 **스팸 방지-Report** header 필드에 값 `SFV:BLK`이 포함 됩니다.

> [!NOTE]
> 원치 않는 메시지가 믿을 수 있는 출처의 뉴스레터가 면 전자 메일을 구독 취소 하 여 사용자가 메시지를 받지 않도록 하는 것이 좋습니다.

## <a name="use-blocked-sender-lists-or-blocked-domain-lists"></a>차단 된 보낸 사람 목록 또는 차단 된 도메인 목록 사용

여러 사용자에 게 영향을 줄 경우 범위가 더 넓기 때문에 스팸 방지 정책의 보낸 사람 목록이 나 차단 된 도메인 목록은 다음 최상의 옵션으로 차단 됩니다. 목록에 있는 보낸 사람이 보낸 메시지는 **스팸으로**표시 되며 **스팸** 필터 결과으로 구성한 작업은 메시지에 대해 수행 됩니다. 자세한 내용은 [Office 365의 스팸 방지 정책 구성하기](configure-your-spam-filter-policies.md)를 참조하세요.

이러한 목록의 최대 제한은 약 1000 항목입니다. 하지만 포털에는 30 개의 항목만 입력할 수 있습니다. 30 개 보다 많은 항목을 추가 하려면 PowerShell을 사용 해야 합니다.

## <a name="use-mail-flow-rules"></a>메일 흐름 규칙 사용

특정 사용자 또는 전체 조직에서 전송 되는 메시지를 차단 해야 하는 경우 메일 흐름 규칙을 사용할 수 있습니다. 메일 흐름 규칙은 보낸 사람 목록 또는 수신 거부 도메인 목록 보다 더 유연 하며 원치 않는 메시지에서 키워드나 기타 속성을 검색할 수도 있습니다.

메시지를 식별 하는 데 사용 하는 조건 또는 예외에 관계 없이 메시지의 SCL (스팸 지 수)을 9로 설정 하는 작업을 구성 하 여 메시지를 **높은 신뢰도의 스팸으로**표시 합니다. 자세한 내용은 [메일 흐름 규칙을 사용 하 여 메시지의 SCL 설정을](use-mail-flow-rules-to-set-the-spam-confidence-level-scl-in-messages.md)참조 하십시오.

> [!IMPORTANT]
> *지나치게* 적극적인 규칙을 쉽게 만들 수 있으므로 매우 구체적인 조건을 사용 하 여 차단 하려는 메시지만 식별 하는 것이 중요 합니다. 또한 규칙에 대 한 감사를 사용 하도록 설정 하 고 규칙의 결과를 테스트 하 여 모든 항목이 예상 대로 작동 하는지 확인 해야 합니다.

## <a name="use-the-ip-block-list"></a>IP 차단 목록 사용

다른 옵션 중 하나를 사용 하 여 보낸 사람을 차단할 수 없는 경우에 *만* 연결 필터 정책에서 IP 차단 목록을 사용 해야 합니다. 자세한 내용은 [Configure the connection filter policy](configure-the-connection-filter-policy.md)를 참조하십시오. 차단 된 Ip 수를 최소로 유지 하는 것이 중요 하므로 전체 IP 주소 범위를 차단 하는 것은 권장 *되지 않습니다* .

*특히* 소비자 서비스 (예: outlook.com) 또는 공유 인프라에 속하는 ip 주소 범위를 추가 하는 것을 피하고, 일반 유지 관리의 일부로 차단 된 ip 주소 목록을 검토 하는 것이 좋습니다.
