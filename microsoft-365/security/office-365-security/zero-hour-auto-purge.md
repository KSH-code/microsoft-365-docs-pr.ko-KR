---
title: ZAP(제로 아워 자동 제거)
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: Admin
ms.topic: conceptual
localization_priority: Normal
search.appverid:
- MOE150
- MED150
- MBS150
- MET150
ms.assetid: 96deb75f-64e8-4c10-b570-84c99c674e15
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: 관리자는 ZAP(제로 아워 자동 제거)가 Exchange Online 사서함의 배달된 메시지를 스팸 또는 피싱으로 소급 처리된 정크 메일 폴더 또는 검역소로 이동하는 방법을 알 수 있습니다.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: b5744fdd4ce371f62fcb4b07a4cbcd003405c3db
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/19/2021
ms.locfileid: "50907979"
---
# <a name="zero-hour-auto-purge-zap-in-exchange-online"></a>Exchange Online의 ZAP(제로 아워 자동 제거)

**적용 대상**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Office 365용 Microsoft Defender 플랜 1 및 플랜 2](office-365-atp.md)
- [Microsoft 365 Defender](../mtp/microsoft-threat-protection.md)

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


## <a name="basic-features-of-zap"></a>ZAP의 기본 기능

Exchange Online에 사서함이 있는 Microsoft 365 조직에서 ZAP(제로 아워 자동 제거)는 이미 Exchange Online 사서함으로 배달된 악성 피싱, 스팸 또는 맬웨어 메시지를 소급하여 감지하고 중화하는 전자 메일 보호 기능입니다.

ZAP는 사내 Exchange 사서함을 보호하는 독립 실행형 EOP(Exchange Online Protection) 환경에서는 작동하지 않습니다.

## <a name="how-zap-works"></a>ZAP의 작동 방식

스팸 및 맬웨어 서명은 서비스에서 매일 실시간으로 업데이트됩니다. 그러나 사용자는 사용자에게 배달된 후 콘텐츠를 배달하는 경우를 포함하여 다양한 이유로 악의적인 메시지를 받을 수 있습니다. ZAP는 서비스의 스팸 및 맬웨어 서명에 대한 업데이트를 지속적으로 모니터링하여 이 문제를 해결합니다. ZAP는 사용자 사서함에 이미 있는 메시지를 찾아 제거할 수 있습니다.

ZAP 작업은 사용자에게 매끄럽게 수행됩니다. 메시지가 검색되고 이동된 경우 알림을 수신하지 않습니다.

[수신이 가능한 보낸](create-safe-sender-lists-in-office-365.md)사람 목록, 메일 흐름 규칙(전송 규칙), 받은 편지함 규칙 또는 추가 필터가 ZAP보다 우선합니다. 메일 흐름에서 발생하는 경우와 마찬가지로, 이는 서비스에서 배달된 메시지에 ZAP가 필요하다고 판단하는 경우에도 수신이 안전한 보낸 사람 구성으로 인하여 메시지가 처리되지 않습니다. 이는 필터링을 무시할 메시지를 구성할 때 주의해야 하는 또 다른 이유입니다.

### <a name="malware-zap"></a>맬웨어 ZAP

배달 **후** 맬웨어가 포함된 것으로 확인된 읽거나 읽지 않은 메시지의 경우 ZAP는 맬웨어 첨부 파일이 포함된 메시지를 차단합니다. 관리자만이 맬웨어 메시지를 확인 및 관리할 수 있습니다.

맬웨어 ZAP는 맬웨어 방지 정책에서 기본적으로 사용됩니다. 자세한 내용은 EOP에서 맬웨어 [방지 정책 구성을 참조하세요.](configure-anti-malware-policies.md)

### <a name="phish-zap"></a>피싱 ZAP

배달 **후** 피싱으로 식별된 읽거나 읽지 않은 메시지의 경우 ZAP 결과는 해당  스팸 방지 정책에서 피싱 전자 메일 필터링 결과에 대해 구성된 동작에 따라 결정됩니다. 피싱에 대해 사용 가능한 필터링 결과 작업 및 가능한 ZAP 결과에 대한 설명은 다음 목록에 설명되어 있습니다.

- **X-Header** **추가,** 제목 줄에 텍스트 추가, 전자 메일 주소로 메시지 **리디렉션** **,** 메시지 삭제: ZAP는 메시지에 대한 작업을 수행하지 않습니다.

- **정크 메일로** 메시지 이동 : ZAP는 사서함에서 정크 메일 규칙이 사용하도록 설정된 경우(기본적으로 사용하도록 설정되어 있는 경우) 메시지를 정크 메일 폴더로 이동합니다. 자세한 내용은 [Microsoft 365에서 Exchange Online](configure-junk-email-settings-on-exo-mailboxes.md)사서함에 대한 정크 메일 설정 구성을 참조하세요.

- **메시지 Quarantine message**: ZAP quarantines the message.

기본적으로 피싱 ZAP는 스팸 방지 정책에서 사용하도록 설정되어  있으며, 피싱 전자 메일 필터링 판정에 대한 기본 작업은 피싱 ZAP가 메시지를 기본적으로 차단하는 메시지입니다.

스팸 필터링 판정을 구성하는 데 대한 자세한 내용은 [Microsoft 365에서](configure-your-spam-filter-policies.md)스팸 방지 정책 구성을 참조하세요.

### <a name="spam-zap"></a>스팸 ZAP

배달 **후** 스팸으로 식별되는 읽을 수 없는 메시지의 경우 ZAP 결과는 해당  스팸 방지 정책에서 스팸 필터링 결과에 대해 구성된 동작에 따라 결정됩니다. 스팸에 대해 사용 가능한 필터링 결과 작업 및 가능한 ZAP 결과에 대한 설명은 다음 목록에 설명되어 있습니다.

- **X-Header** **추가,** 제목 줄에 텍스트 추가, 전자 메일 주소로 메시지 **리디렉션** **,** 메시지 삭제: ZAP는 메시지에 대한 작업을 수행하지 않습니다.

- **정크 메일로** 메시지 이동 : ZAP는 사서함에서 정크 메일 규칙이 사용하도록 설정된 경우(기본적으로 사용하도록 설정되어 있는 경우) 메시지를 정크 메일 폴더로 이동합니다. 자세한 내용은 [Microsoft 365에서 Exchange Online](configure-junk-email-settings-on-exo-mailboxes.md)사서함에 대한 정크 메일 설정 구성을 참조하세요.

- **메시지 Quarantine message**: ZAP quarantines the message. 최종 사용자는 자신의 스팸으로 분류된 메시지를 보고 관리할 수 있습니다.

기본적으로 스팸 ZAP는 스팸 방지 정책에서 사용하도록 설정되어  있으며 스팸 필터링 판정에 대한 기본 작업은 메시지를 정크  메일 폴더로 이동입니다. **즉,** 스팸 ZAP는 언데이트 메시지를 기본적으로 정크 메일 폴더로 이동합니다.

스팸 필터링 판정을 구성하는 데 대한 자세한 내용은 [Microsoft 365에서](configure-your-spam-filter-policies.md)스팸 방지 정책 구성을 참조하세요.

### <a name="zap-considerations-for-microsoft-defender-for-office-365"></a>Office 365용 Microsoft Defender에 대한 ZAP 고려 사항

ZAP는 안전 첨부 파일 검색에서 동적 배달을 [](atp-safe-attachments.md#dynamic-delivery-in-safe-attachments-policies) 진행하는 중이나 EOP 맬웨어 필터링이 첨부 파일을 이미 맬웨어 경고 파일로 대체한 메시지를 Text.txt **않습니다.** 이러한 유형의 메시지에 대해 피싱 또는 스팸 신호가 수신되고 스팸 방지 정책의 필터링 판정이 메시지에 대해 일부 작업(정크 메일, 리디렉션, 삭제 또는 Quarantine으로 이동)으로 설정되어 있는 경우 ZAP는 기본적으로 '정크로 이동' 작업으로 설정됩니다.

## <a name="how-to-see-if-zap-moved-your-message"></a>ZAP에서 메시지를 이동한 경우를 표시하는 방법

ZAP가 메시지를 이동한지 확인하려면 [위협](view-email-security-reports.md#threat-protection-status-report) 방지 상태 보고서 또는 위협 탐색기(및 실시간 검색)를 사용할 [수 있습니다.](threat-explorer.md) 시스템 작업으로 ZAP는 Exchange 사서함 감사 로그에 기록되지 않습니다.

## <a name="zap-faq"></a>ZAP FAQ

### <a name="what-happens-if-a-legitimate-message-is-moved-to-the-junk-email-folder"></a>합법적인 메시지가 정크 메일 폴더로 이동하면 어떻게 하나요?

가짓 긍정에 대한 일반적인 보고 [프로세스를 따라야 합니다.](report-junk-email-messages-to-microsoft.md) 메시지가 받은 편지함에서 정크 메일 폴더로 이동하는 유일한 이유는 서비스에서 메시지가 스팸 또는 악성으로 확인된 것이기 때문에입니다.

### <a name="what-if-i-use-the-quarantine-folder-instead-of-the-junk-mail-folder"></a>정크 메일 폴더 대신 Quarantine 폴더를 사용하는 경우 어떻게 하나요?

ZAP는 이 문서의 앞부분에서 설명한 대로 스팸 방지 정책의 구성에 따라 메시지에 대해 작업을 수행하게 됩니다.

### <a name="what-if-im-using-safe-senders-mail-flow-rules-or-allowedblocked-sender-lists"></a>수신 허용 - 보낸 사람, 메일 흐름 규칙 또는 허용/차단된 보낸 사람 목록을 사용하는 경우 어떻게 하나요?

수신 허용 - 보낸 사람, 메일 흐름 규칙 또는 차단 및 허용 조직 설정이 우선합니다. 서비스가 사용자가 구성한 작업을 수행 중이기 때문에 이러한 메시지는 ZAP에서 제외됩니다. 이는 필터링을 무시할 메시지를 구성할 때 주의해야 하는 또 다른 이유입니다.

### <a name="what-are-the-licensing-requirements-for-zap-to-work"></a>ZAP가 작동하기 위한 라이선스 요구 사항은 무엇입니까?

라이선스에는 제한이 없습니다. ZAP는 Exchange Online에 호스트된 모든 사서함에서 작동합니다. ZAP는 사내 Exchange 사서함을 보호하는 독립 실행형 EOP(Exchange Online Protection) 환경에서는 작동하지 않습니다.

### <a name="what-if-a-message-is-moved-to-another-folder-eg-inbox-rules"></a>메시지가 다른 폴더(예: 받은 편지함 규칙)로 이동하면 어떻게 하나요?

ZAP는 메시지가 삭제되지 않은 경우 또는 동일한 또는 더 강력한 작업이 아직 적용되지 않은 한 계속 작동합니다. 예를 들어 피싱 방지 정책이 quarantine으로 설정되어 있으며 메시지가 이미 정크 메일에 있는 경우 ZAP는 메시지를 검사하기 위한 조치를 취합니다.

### <a name="how-does-zap-affect-mailboxes-on-hold"></a>ZAP는 보류된 사서함에 어떤 영향을 미치나요?

ZAP는 보류된 사서함의 메시지를 검지하지 않습니다. ZAP는 스팸 방지 정책에서 스팸 또는 피싱 판정에 대해 구성된 작업을 기반으로 메시지를 정크 메일 폴더로 이동할 수 있습니다.

Exchange Online의 보류에 대한 자세한 내용은 [Exchange Online의 In-Place Hold and Litigation Hold를 참조하세요.](/Exchange/security-and-compliance/in-place-and-litigation-holds)