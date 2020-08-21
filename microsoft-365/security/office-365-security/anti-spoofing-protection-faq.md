---
title: 스푸핑 방지 보호 기능 FAQ
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
ms.assetid: ''
ms.collection:
- M365-security-compliance
description: 관리자는 EOP(Exchange Online Protection)의 스푸핑 방지 보호 기능에 대한 질문과 답변을 볼 수 있습니다.
ms.openlocfilehash: 66dbedaf638154c4a35359a4e5bc66c326c04d1e
ms.sourcegitcommit: e12fa502bc216f6083ef5666f693a04bb727d4df
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/20/2020
ms.locfileid: "46826676"
---
# <a name="anti-spoofing-protection-faq"></a>스푸핑 방지 보호 기능 FAQ

이 항목에서는 Exchange Online 사서함이 있는 Microsoft 365 조직 또는 Exchange Online 사서함이 없는 독립 실행형 EOP(Exchange Online Protection) 조직의 스푸핑 방지 보호기능에 대한 질문과 답변을 제공합니다.

스팸 방지 보호 기능에 대한 질문과 대답은 스팸 [방지 보호 FAQ를 참조하세요.](anti-spam-protection-faq.md)

맬웨어 방지 보호에 대한 질문과 대답은 맬웨어 [방지 보호 FAQ를 참조하세요.](anti-malware-protection-faq-eop.md)

## <a name="why-did-microsoft-choose-to-junk-unauthenticated-inbound-email"></a>Microsoft가 인증되지 않은 인바운드 전자 메일을 보내도록 선택하는 이유는 무엇인가요?

피싱 공격의 영향으로 인해 전자 메일 인증이 15년 이상 지속되었기 때문에 Microsoft는 합법적인 인바운드 전자 메일 손실 위험보다 인증되지 않은 인바운드 전자 메일을 지속적으로 받을 위험이 높다고 생각합니다.

## <a name="does-junking-unauthenticated-inbound-email-cause-legitimate-email-to-be-marked-as-spam"></a>인증되지 않은 인바운드 전자 메일로 인해 합법적 전자 메일이 스팸으로 표시됩니까?

Microsoft가 2018년에 이 기능을 사용하도록 설정하면 일부 가양성이 발생했습니다(좋은 메시지가 잘못된 것으로 표시됨). 하지만 시간이 지남에 따라 보낸 사람은 새로운 보낸 사람 인증 요구 사항으로 조정되며 대부분의 이메일 경로에 대해 스푸핑된(보이이이이) 메시지 수는 금지됩니다.

Microsoft 자체는 처음에 고객에게 배포하기 몇 주 전에 몇 주 전에 새로운 전자 메일 인증 요구 사항을 채택했습니다. 처음에는 혼란이 있었지만 점차적으로 감소했습니다.

## <a name="is-spoof-intelligence-available-to-microsoft-365-customers-without-atp"></a>ATP가 없는 Microsoft 365 고객은 스푸핑 인텔리전스를 사용할 수 있나요?

예. 2018년 10월을 현재, Exchange Online 사서함이 없는 모든 조직과 Exchange Online 사서함이 없는 독립 실행형 EOP 조직을 보유한 모든 조직에서 스푸핑 인텔리전스를 사용할 수 있습니다.

스푸핑 방지 기술은 초기에 Office 365 Enterprise E5 구독 또는 해당 구독에 대한 Office 365 ATP(Advanced Threat Protection) 추가 기능이 있는 조직에만 배포되었습니다.

## <a name="how-can-i-report-spam-or-non-spam-messages-back-to-microsoft"></a>스팸 또는 비스팸 메시지를 Microsoft에 다시 보고하려면 어떻게 합니까?

[Microsoft에 메시지와 파일 보고](report-junk-email-messages-to-microsoft.md)를 참조하세요.

## <a name="im-an-admin-and-i-dont-know-all-of-sources-for-messages-in-my-email-domain"></a>저는 관리자이고 내 전자 메일 도메인에서 메시지에 대한 모든 원본을 모르고 있습니다.

전자 [메일에 대해 모든 원본을 알 수 없습니다.](email-validation-and-authentication.md#you-dont-know-all-sources-for-your-email)

## <a name="what-happens-if-i-disable-anti-spoofing-protection-for-my-organization"></a>조직에서 스푸핑 방지 기능을 사용하지 않도록 설정하면 어떻게 됩니까?

피싱 및 스팸 메일을 놓치는 경우가 많아질 것이므로 이는 권장하지 않습니다. 모든 피싱이 스푸핑이 되는 것은 아니며 모든 스푸핑이 누락되지는 않습니다. 그러나 사용자의 위험은 스푸핑 방지를 사용하는 고객보다 높습니다.

이제 [커넥터에 대한 향상된 필터링을](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors) 사용할 수 있도록 전자 메일을 EOP에 배달하기 전에 MX 레코드가 다른 서버나 서비스를 가리키는 경우 스푸핑 방지 보호 기능을 더 이상 사용하지 않도록 설정하지 않습니다.

## <a name="does-anti-spoofing-protection-mean-i-will-be-protected-from-all-phishing"></a>스푸핑 방지 기능은 모든 피싱으로부터 보호받을 수 있다는 의미입니까?

Unfortunately, no. 공격자는 다른 기법(예: 무료 전자 메일 서비스의 계정 또는 계정)을 사용하도록 조정합니다. 그러나 피싱 방지 기능은 다른 유형의 피싱 방법을 탐지하는 데 그다지 유용합니다. EOP의 보호 계층은 함께 작동하고 서로 위에 구축됩니다.

## <a name="do-other-large-email-services-block-unauthenticated-inbound-email"></a>다른 대규모 전자 메일 서비스가 인증되지 않은 인바운드 전자 메일을 차단하나요?

거의 모든 대형 전자 메일 서비스는 기존의 SPF, DKIM 및 DMARC 검사를 구현합니다. 일부 서비스는 다른 일반적인 검사를 포함하고 있지만 인증되지 않은 전자 메일을 차단하고 이를 스푸핑된 메시지로 간주하는 EOP는 거의 없습니다. 그러나 업체에서는 피싱 문제 때문에 인증되지 않은 전자 메일 문제에 대해 더욱 알게 됩니다.

## <a name="do-i-still-need-to-enable-the-advanced-spam-filter-setting-spf-record-hard-fail-_markasspamspfrecordhardfail_-if-i-enable-anti-spoofing"></a>스푸핑 방지를 사용하는 경우에도 고급 스팸 필터 설정 "SPF 레코드: 하드_실패"(MarkAsSpamSpfRecordHardFail)를_사용하도록 설정해야 하나요?

아니요. 스푸핑 방지 설정은 더 이상 필요하지 않지만 SPF 하드 실패 및 더 광범위한 기준을 고려하기 때문입니다. 스푸핑 방지를 사용하고 **SPF 레코드: 하드 실패**(_MarkAsSpamSpfRecordHardFail_)를 켠 경우 더 많은 오탐지가 발생할 것입니다.

스팸이나 피싱 메시지를 검색할 경우 추가적인 이점은 제공하지 않고 대부분 오탐지가 발생하기도 하며 대부분 의미로 오탐지될 수 있으며 이 기능을 사용하지 않도록 설정하는 것이 좋습니다. 자세한 내용은 [EOP에서 ASF(고급 스팸 필터) 설정을 참조하세요.](advanced-spam-filtering-asf-options.md)

## <a name="does-sender-rewriting-scheme-help-fix-forwarded-email"></a>보낸 사람 다시 작성 체크인을 통해 전달된 전자 메일을 수정할 수 있나요?

SRS는 전달된 전자 메일 문제를 부분적으로만 수정합니다. SMTP **MAIL FROM을**다시 쓰면 SRS를 통해 전달된 메시지가 다음 대상에서 SPF를 통과하는 지 확인할 수 있습니다. 그러나 스푸핑 방지는 MAIL FROM 또는 **From** DKIM 서명 도메인(또는 다른 신호)과 **함께 From** 주소를 기반으로 하기 때문에 SRS로 전달된 전자 메일이 스푸핑으로 표시되지 않도록 할 수 없습니다.
