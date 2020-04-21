---
title: 제로 시간 자동 삭제 (ZAP)-스팸, 맬웨어 및 피싱에 대 한 retroactive 보호
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
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
description: 0 시간 자동 삭제 (ZAP)는 Exchange Online으로 이미 배달 된 스팸, 맬웨어 또는 피싱 메시지를 검색 하는 Microsoft 365의 전자 메일 보호 기능입니다. ZAP이 수행 하는 방법은 검색 된 악의적인 콘텐츠의 유형에 따라 다릅니다.
ms.openlocfilehash: a819269d8596f12e76cbd17b5d1302cd56837f14
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/21/2020
ms.locfileid: "43630812"
---
# <a name="zero-hour-auto-purge-zap---protection-against-spam-and-malware-in-microsoft-365"></a>제로 시간 자동 삭제 (ZAP)-Microsoft 365의 스팸 및 맬웨어에 대 한 보호

## <a name="overview"></a>개요

0 시간 자동 삭제 (ZAP)는 retroactively에서 Exchange Online 사서함으로 이미 배달 된 악의적인 피싱, 스팸 또는 맬웨어 메시지를 검색 하 고 neutralizes 하는 Microsoft 365의 전자 메일 보호 기능입니다.

ZAP은 Exchange Online 사서함이 포함 된 Microsoft 365 구독에 포함 된 기본 EOP (Exchange Online Protection)에서 사용할 수 있습니다. ZAP은 온-프레미스 Exchange 사서함을 보호 하는 독립 실행형 EOP 환경에서 작동 하지 않습니다.

## <a name="how-zap-works"></a>ZAP 작동 방식

Microsoft 365는 스팸 및 맬웨어 서명을 매일 실시간으로 업데이트 합니다. 그러나 사용자에 게 콘텐츠를 배달 한 후에 weaponized를 포함 하 여 여러 가지 이유로 인해 여전히 악의적인 메시지를 받을 수 있습니다. ZAP은 마이크로 Sfot 365 스팸 및 맬웨어 서명에 대 한 업데이트를 지속적으로 모니터링 하 여이 문제를 해결 합니다. ZAP은 이미 사용자의 사서함에 있는 메시지를 찾아 제거할 수 있습니다.

사용자가 ZAP 작업을 원활 하 게 수행할 수 있습니다. 메시지를 검색 하 고 이동한 경우 알림을 받지 않습니다.

[수신 허용-보낸 사람 목록](create-safe-sender-lists-in-office-365.md), 메일 흐름 규칙 (전송 규칙이 라고도 함), 받은 편지함 규칙 또는 추가 필터는 ZAP 보다 우선적으로 적용 됩니다.

### <a name="malware-zap"></a>맬웨어 ZAP

배달 후 맬웨어가 포함 되는 것으로 확인 된 **읽음 또는 읽지 않은 메시지** 에 대해 ZAP 설정별가 맬웨어 첨부 파일을 포함 하는 메시지를 표시 합니다. 관리자만 격리에서 맬웨어 메시지를 보고 관리할 수 있습니다.

맬웨어 ZAP은 맬웨어 방지 정책에서 기본적으로 사용 하도록 설정 됩니다. 자세한 내용은 [Microsoft 365에서 맬웨어 방지 정책 구성을](configure-anti-malware-policies.md)참조 하세요.

### <a name="phish-zap"></a>피싱 ZAP

배달 후에 피싱으로 식별 되는 **읽음 또는 읽지 않은 메시지** 의 경우 ZAP 결과는 해당 하는 스팸 방지 정책에서 **피싱 전자 메일** 필터링 결과에 대해 구성 된 작업에 따라 달라 집니다. 다음 목록에서는 피싱에 대 한 사용 가능한 필터링 결과 작업 및 가능한 ZAP 결과에 대해 설명 합니다.

- **X-헤더 추가**( **제목 줄 앞에 텍스트 포함**): ZAP이 메시지에 대해 작업을 수행 하지 않습니다.

- **정크 메일로 메시지 이동**: ZAP 사서함에서 정크 메일 규칙을 사용 하는 경우 (기본적으로 사용 하도록 설정 되어 있음) 메시지를 정크 메일 폴더로 이동 합니다. 자세한 내용은 [Microsoft 365에서 Exchange Online 사서함의 정크 메일 설정 구성을](configure-junk-email-settings-on-exo-mailboxes.md)참조 하세요.

- **전자 메일 주소로 메시지 리디렉션**, **메시지 삭제**, **격리 메시지**: ZAP 설정별 메시지 관리자만 격리 된 피싱 메시지를 보고 관리할 수 있습니다.

기본적으로 스팸 방지 정책에서 피싱 ZAP을 사용 하도록 설정 되어 있으며 **피싱 전자 메일** 필터링 결과의 기본 작업은 **메시지를 격리**하며,이는 메시지를 기본적으로 피싱 ZAP 설정별 한다는 것을 의미 합니다.

스팸 필터링 verdicts 구성에 대 한 자세한 내용은 [Microsoft 365에서 스팸 방지 정책 구성을](configure-your-spam-filter-policies.md)참조 하세요.

### <a name="spam-zap"></a>스팸 ZAP

배달 후 스팸으로 식별 된 **읽지 않은 메시지** 의 경우 ZAP 결과는 해당 하는 스팸 방지 정책에서 **스팸** 필터링 결과에 대해 구성 된 작업에 따라 달라 집니다. 스팸 및 가능한 ZAP 결과에 대 한 사용 가능한 필터링 결과 작업은 다음 목록에 설명 되어 있습니다.

- **X-헤더 추가**( **제목 줄 앞에 텍스트 포함**): ZAP이 메시지에 대해 작업을 수행 하지 않습니다.

- **정크 메일로 메시지 이동**: ZAP 사서함에서 정크 메일 규칙을 사용 하는 경우 (기본적으로 사용 하도록 설정 되어 있음) 메시지를 정크 메일 폴더로 이동 합니다. 자세한 내용은 [Microsoft 365에서 Exchange Online 사서함의 정크 메일 설정 구성을](configure-junk-email-settings-on-exo-mailboxes.md)참조 하세요.

- **전자 메일 주소로 메시지 리디렉션**, **메시지 삭제**, **격리 메시지**: ZAP 설정별 메시지 최종 사용자는 자신의 스팸 격리 된 메시지를 보고 관리할 수 있습니다.

기본적으로 스팸 방지 정책에서 스팸 ZAP을 사용 하도록 설정 되어 있으며 스팸 필터링 결과의 기본 작업은 **정크 메일 폴더로 메시지를 이동**하는 것으로 **, 스팸 zap** 은 **읽지 않은** 메시지를 정크 메일 폴더로 이동 합니다.

스팸 필터링 verdicts 구성에 대 한 자세한 내용은 [Microsoft 365에서 스팸 방지 정책 구성을](configure-your-spam-filter-policies.md)참조 하세요.

### <a name="zap-considerations-for-office-365-advanced-threat-protection-atp"></a>Office 365 ATP (Advanced Threat Protection)에 대 한 ZAP 고려 사항

ZAP은 [동적 배달](dynamic-delivery-and-previewing.md) 검색 프로세스에 포함 된 메시지를 격리 하지 않으며 맬웨어 필터링이 이미 **맬웨어 경고 텍스트인 .txt** 파일로 첨부 파일을 바꿨습니다. 이러한 유형의 메시지에 대 한 피싱 또는 스팸 신호를 수신 하 고 스팸 방지 정책의 필터링 결과 메시지에 대 한 특정 작업을 수행 하도록 설정 된 경우 (정크로 이동, 리디렉션, 삭제, 격리), ZAP은 ' 정크로 이동 ' 작업을 기본으로 합니다.

## <a name="how-to-see-if-zap-moved-your-message"></a>메시지가 ZAP에서 이동 된 것을 확인 하는 방법

ZAP이 메시지를 이동 했는지 확인 하려면 [위협 방지 상태 보고서](view-email-security-reports.md#threat-protection-status-report) 또는 [위협 탐색기 (및 실시간 검색)](threat-explorer.md)를 사용할 수 있습니다. 시스템 작업으로, ZAP이 Exchange 사서함 감사 로그에 기록 되지 않습니다.

## <a name="zap-faq"></a>ZAP FAQ

### <a name="q-what-happens-if-a-legitimate-message-is-moved-to-the-junk-email-folder"></a>Q: 합법적인 메시지를 정크 메일 폴더로 이동 하면 어떻게 되나요?

A: 일반적인 보고 프로세스는 [가양성](report-junk-email-messages-to-microsoft.md)에 따라 수행 해야 합니다. 메시지를 받은 편지함에서 정크 메일 폴더로 이동 하는 유일한 이유는 서비스가 스팸 또는 악성 메시지를 받는 것으로 확인 되었기 때문입니다.

### <a name="q-what-if-i-use-the-quarantine-folder-instead-of-the-junk-mail-folder"></a>Q: 정크 메일 폴더 대신 Quarantine 폴더를 사용 하는 경우에는 어떻게 하나요?

A: ZAP은이 항목의 앞부분에서 설명한 대로, 스팸 방지 정책 구성을 기반으로 메시지에 대해 작업을 수행 합니다.

### <a name="q-what-if-im-using-mail-flow-rules-or-allowedblocked-sender-lists"></a>Q: 메일 흐름 규칙 또는 허용/차단 된 보낸 사람 목록을 사용 하는 경우

A: 메일 흐름 규칙 또는 차단 및 조직 설정 허용이 우선적으로 적용 됩니다. 이러한 메시지는 ZAP에서 제외 됩니다.

### <a name="q-what-if-a-message-is-moved-to-another-folder-eg-inbox-rules"></a>Q: 메시지를 다른 폴더 (예: 받은 편지함 규칙)로 이동 하는 경우

A: 메시지가 삭제 되지 않았거나, 동일 하거나 더 강력 하지만 작업이 아직 적용 되지 않은 동안에도 ZAP이 계속 작동 합니다. 예를 들어 피싱 정책이 quarantine로 설정 되어 있고 사용자 또는 관리자가 이미 전자 메일을 junked 하는 경우 격리를 통해 파일을 격리 하는 작업이 수행 됩니다.

### <a name="q-does-zap-change-the-message-header"></a>Q: ZAP이 메시지 헤더를 변경 합니까?

A: 메시지 헤더는 ZAP 작업을 통해 변경 되지 않습니다.

### <a name="q-how-does-zap-affect-mailboxes-on-hold"></a>Q: ZAP이 보존 되는 사서함에 어떤 영향을 줍니까?

A: ZAP은 보류 중인 사서함에서 메시지를 격리 하지 않습니다. 스팸 방지 정책에서 스팸 또는 피싱 결과에 대해 구성 된 작업을 기반으로 메시지를 정크 메일 폴더로 이동할 수 있습니다.

Exchange Online의 보류에 대 한 자세한 내용은 [Exchange online의 원본 위치 유지 및 소송 보존](https://docs.microsoft.com/Exchange/security-and-compliance/in-place-and-litigation-holds)을 참조 하세요.
