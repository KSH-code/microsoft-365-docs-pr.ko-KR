---
title: 제로 아사이트 자동 비우기(ZAP)
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: Admin
ms.topic: conceptual
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
ms.custom:
- seo-marvel-apr2020
description: 관리자는 ZAP(제로 아우스 자동 비우기)가 Exchange Online 사서함의 배달된 메시지를 스팸 또는 피싱으로 사후 분류된 격리나 정크 메일 폴더로 리드로 이어지는 방법에 대해 알아질 수 있습니다.
ms.openlocfilehash: 9096486ed98657fede7927089592c92fffdad70e
ms.sourcegitcommit: e12fa502bc216f6083ef5666f693a04bb727d4df
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/20/2020
ms.locfileid: "46826700"
---
# <a name="zero-hour-auto-purge-zap-in-exchange-online"></a>Exchange Online의 ZAP(제로 아우스 자동 비우기)

## <a name="basic-features-of-zap"></a>ZAP의 기본 기능

Exchange Online의 사서함이 있는 Microsoft 365 조직에서 ZAP(제로 아르기 자동 비우기)는 Exchange Online 사서함으로 이미 배달된 악성, 스팸 또는 맬웨어 메시지를 사실로 감지하고 중을 보내는 전자 메일 보호 기능입니다.

ZAP는 온-프레미스 Exchange 사서함을 보호하는 독립 실행형 EOP(Exchange Online Protection) 환경에서 작동하지 않습니다.

## <a name="how-zap-works"></a>ZAP 작동 방식

스팸 및 맬웨어 서명은 매일 서비스에서 실시간으로 업데이트됩니다. 그러나 사용자는 사용자에게 콘텐츠가 전달된 후 콘텐츠가 환중화된 경우를 포함하여 다양한 이유로 악성 메시지를 계속 받을 수 있습니다. ZAP는 서비스에서 스팸 및 맬웨어 서명에 지속적으로 업데이트를 모니터링하여 이 문제를 해결합니다. ZAP는 이미 사용자 사서함에 있는 메시지를 찾아 제거할 수 있습니다.

ZAP 작업은 사용자에게 일특하지 않습니다. 또한 메시지가 탐지되어 이동될 경우 알리지 않습니다.

[수신 허용 - 보낸](create-safe-sender-lists-in-office-365.md)사람 목록, 메일 흐름 규칙(전송 규칙이라고도 함), 받은 편지함 규칙 또는 추가 필터는 ZAP보다 우선합니다. 이는 메일 흐름에서 의미와 유사하게, 서비스에 배달된 메시지에 ZAP가 필요하다고 결정해도 안전한 보낸 사람 구성으로 인해 메시지가 작동하지 않습니다. 이는 필터링을 무시하도록 메시지를 구성할 때 주의해야 할 다른 이유입니다.

### <a name="malware-zap"></a>맬웨어 ZAP

배달 **후 맬웨어가 포함된** 읽거나 읽지 않은 메시지의 경우 ZAP는 맬웨어 첨부 파일을 포함하는 메시지를 격리합니다. 관리자만 격리에서 맬웨어 메시지를 보고 관리할 수 있습니다.

맬웨어 ZAP는 맬웨어 방지 정책에서 기본적으로 사용됩니다. 자세한 내용은 [EOP에서 맬웨어 방지 정책 구성을 참조하세요.](configure-anti-malware-policies.md)

### <a name="phish-zap"></a>피싱 ZAP

배달 **후 피싱으로 식별된** 메시지를 읽거나 읽지 않은 메시지의 경우 ZAP 결과는 해당 스팸 방지 정책에서 **피싱 전자** 메일 필터링 결과에 대해 구성한 작업에 따라 달라지기도 합니다. 다음 목록에는 피싱에 대한 사용 가능한 필터링 결과 작업과 가능한 ZAP 결과가 설명되어 있습니다.

- **X-헤더 추가,** **제목 줄 끝에 텍스트를**추가: ZAP는 메시지에서 작업이 수행되지 않습니다.

- **정크 메일로 메시지**이동 : ZAP는 사서함에 정크 메일 규칙이 활성화되어 있는 한 정크 메일 폴더로 메시지를 이동합니다(기본적으로 활성화되어 있음). 자세한 내용은 [Microsoft 365에서 Exchange Online 사서함에 대한 정크 메일 설정 구성을 참조하세요.](configure-junk-email-settings-on-exo-mailboxes.md)

- **전자 메일 주소로 메시지** **리디렉션,** 메시지 **삭제, 격리**메시지: ZAP는 메시지를 격리합니다.

기본적으로 피싱 ZAP는 스팸 방지 정책에서 사용하도록 설정되어 있고 피싱 **전자** 메일 필터링 결과에 대한 기본 작업은 **격리**메시지입니다. 따라서 피싱 ZAP는 기본적으로 메시지를 격리합니다.

스팸 필터링 조건을 구성하는 방법에 대한 자세한 내용은 [Microsoft 365의 스팸 방지 정책 구성을 참조하세요.](configure-your-spam-filter-policies.md)

### <a name="spam-zap"></a>스팸 ZAP

배달 **후 스팸으로** 확인된 읽지 않은 메시지의 경우 ZAP 결과는 해당 스팸 방지 **정책에서 스팸 필터링 결과에** 대해 구성된 작업에 따라 달라지며 다음 목록에서는 스팸에 대해 사용 가능한 필터링 결과 작업 과정과 가능한 ZAP 결과에 대해 설명합니다.

- **X-헤더 추가,** **제목 줄 끝에 텍스트를**추가: ZAP는 메시지에서 작업이 수행되지 않습니다.

- **정크 메일로 메시지**이동 : ZAP는 사서함에 정크 메일 규칙이 활성화되어 있는 한 정크 메일 폴더로 메시지를 이동합니다(기본적으로 활성화되어 있음). 자세한 내용은 [Microsoft 365에서 Exchange Online 사서함에 대한 정크 메일 설정 구성을 참조하세요.](configure-junk-email-settings-on-exo-mailboxes.md)

- **전자 메일 주소로 메시지** **리디렉션,** 메시지 **삭제, 격리**메시지: ZAP는 메시지를 격리합니다. 최종 사용자는 자신의 스팸 격리 메시지를 보고 관리할 수 있습니다.

스팸 ZAP는 스팸 방지 정책에서 기본적으로 사용하도록 설정되어 **Spam** 있고 스팸 필터링 결과에 대한 기본 작업은 메시지를 정크 메일 **unread** **폴더로 이동하는**것입니다. 따라서 스팸 ZAP는 기본적으로 읽지 않은 메시지를 정크 메일 폴더로 이동합니다.

스팸 필터링 조건을 구성하는 방법에 대한 자세한 내용은 [Microsoft 365의 스팸 방지 정책 구성을 참조하세요.](configure-your-spam-filter-policies.md)

### <a name="zap-considerations-for-office-365-advanced-threat-protection-office-365-atp"></a>Office 365 ATP(Advanced Threat Protection)에 대한 ZAP 고려 사항

ZAP는 동적 배달 검사 프로세스에 있는 메시지나 맬웨어 필터링이 이미 맬웨어 경고 Text.txt파일로 첨부 파일을 대체한 위치를 **격리시키지** 않습니다. [Dynamic Delivery](dynamic-delivery-and-previewing.md) 이러한 유형의 메시지에 대한 피싱 또는 스팸 신호를 받고 메시지(정크 메일로 이동, 리디렉션, 삭제, 격리로 이동) 메시지에 대해 특정 작업을 수행하도록 설정되어 있는 경우 ZAP는 기본적으로 '정크 메일로 이동' 작업입니다.

## <a name="how-to-see-if-zap-moved-your-message"></a>ZAP가 메시지를 이동한 지 확인하는 방법

ZAP에서 메시지를 이동하라는 확인하려면 위협 방지 [상태 보고서](view-email-security-reports.md#threat-protection-status-report) 또는 [위협 탐색기(실시간 검색)를 사용하면 됩니다.](threat-explorer.md) 시스템 작업으로 ZAP는 Exchange 사서함 감사 로그에 기록되지 않습니다.

## <a name="zap-faq"></a>ZAP FAQ

### <a name="what-happens-if-a-legitimate-message-is-moved-to-the-junk-email-folder"></a>합법적 메시지가 정크 메일 폴더로 이동된 경우 어떻게 됩니까?

가양성에 대한 일반 보고 [프로세스를 따라야 합니다.](report-junk-email-messages-to-microsoft.md) 이유로 받은 편지함에서 정크 메일 폴더로 메시지가 이동되는 이유는 서비스에서 메시지가 스팸 또는 악의적으로 확인되었기 때문이기 때문입니다.

### <a name="what-if-i-use-the-quarantine-folder-instead-of-the-junk-mail-folder"></a>정크 메일 폴더 대신 격리 폴더를 사용하는 경우 어떻게 해야 하나요?

ZAP는 이 항목 앞부분에서 설명한 것과 같이 구성을 기반으로 메시지에 대해 작업을 수행합니다.

### <a name="what-if-im-using-safe-senders-mail-flow-rules-or-allowedblocked-sender-lists"></a>수신 허용 - 보낸 사람, 메일 흐름 규칙 또는 허용/수신 거부 목록을 사용하고 있는 경우 어떻게 하나요?

안전한 보낸 사람, 메일 흐름 규칙 또는 조직 설정을 우선및 허용합니다. 서비스에서 구성한 작업을 수행하므로 이러한 메시지는 ZAP에서 제외됩니다. 이는 필터링을 무시하도록 메시지를 구성할 때 주의해야 할 다른 이유입니다.

### <a name="what-if-a-message-is-moved-to-another-folder-eg-inbox-rules"></a>메시지가 다른 폴더(예: 받은 편지함 규칙)로 이동된 경우 어떻게 하나요?

ZAP는 메시지가 삭제되지 않았거나 동일한(봉계) 작업이 아직 적용되지 않은 한 계속 적용됩니다. 예를 들어 피싱 정책이 격리로 설정되어 있고 사용자 또는 관리자가 이미 이메일을 정크한 경우 격리는 파일을 격리하기 위한 조치를 취합니다.

### <a name="how-does-zap-affect-mailboxes-on-hold"></a>ZAP가 보류된 사서함에 어떤 영향을 주나요?

ZAP는 보류된 사서함에서 메시지를 격리하지 않습니다. ZAP는 스팸 방지 정책의 스팸 또는 피싱 결과에 대해 구성된 작업에 따라 정크 메일 폴더로 메시지를 이동할 수 있습니다.

Exchange Online의 보류에 대한 자세한 내용은 Exchange [Online의 원본 위치 유지 및 소송 보존을 참조하세요.](https://docs.microsoft.com/Exchange/security-and-compliance/in-place-and-litigation-holds)
