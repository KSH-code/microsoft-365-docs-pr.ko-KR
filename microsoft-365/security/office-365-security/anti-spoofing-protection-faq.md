---
title: 스푸핑 방지 보호 기능 FAQ
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
- MET150
ms.assetid: ''
ms.collection:
- M365-security-compliance
description: 관리자는 EOP (Exchange Online Protection)에서 스푸핑 방지 보호에 대 한 질문과 대답을 볼 수 있습니다.
ms.openlocfilehash: 603293dd00100e3b93a225d94f2ed8fd9baae6a5
ms.sourcegitcommit: 93c0088d272cd45f1632a1dcaf04159f234abccd
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/12/2020
ms.locfileid: "44209098"
---
# <a name="anti-spoofing-protection-faq"></a>스푸핑 방지 보호 기능 FAQ

이 항목에서는 exchange online 사서함이 없는 Microsoft 365 조직의 사서함과 독립 실행형 EOP (Exchange Online Protection) 조직에 대 한 스푸핑 방지 보호 기능에 대 한 질문과 대답을 제공 합니다.

스팸 방지 보호 기능에 대 한 질문과 대답은 [스팸 방지 보호 FAQ](anti-spam-protection-faq.md)를 참조 하세요.

맬웨어 방지 보호 기능에 대 한 질문과 대답은 [맬웨어 방지 보호 FAQ](anti-malware-protection-faq-eop.md) 를 참조 하세요.

## <a name="why-did-microsoft-choose-to-junk-unauthenticated-inbound-email"></a>Microsoft에서 정크로 인증 되지 않은 인바운드 전자 메일을 선택한 이유는 무엇 인가요?

피싱 공격이 영향을 받으면서 전자 메일 인증이 15 년 동안 진행 되었기 때문에 Microsoft는 인증 되지 않은 인바운드 전자 메일을 계속 허용 하는 위험이 합법적인 인바운드 전자 메일이 손실 되는 위험 보다 높다는 것을 생각 합니다.

## <a name="does-junking-unauthenticated-inbound-email-cause-legitimate-email-to-be-marked-as-spam"></a>인증 되지 않은 인바운드 전자 메일로 인해 합법적인 전자 메일이 스팸으로 표시 junking?

Microsoft에서 2018의이 기능을 사용 하도록 설정 하면 가양성 메시지가 잘못 된 것으로 표시 됩니다. 그러나 시간이 지남에 따라 보낸 사람이 새로운 보낸 사람 인증 요구 사항에 맞게 조정 되었으며, 스푸핑된로 잘못 식별 되어 된 메시지의 수는 대부분의 전자 메일 경로에서 무시 됩니다.

Microsoft는 먼저 새 전자 메일 인증 요구 사항을 고객에 게 배포 하기 위해 몇 주 정도 도입 했습니다. 처음에는 혼란이 있었지만 점차적으로 감소했습니다.

## <a name="is-spoof-intelligence-available-to-microsoft-365-customers-without-atp"></a>Microsoft 365 고객이 ATP를 사용 하지 않고 스푸핑 인텔리전스를 사용할 수 있나요?

예. 10 월 2018 부터는 Exchange Online에 사서함이 있는 모든 조직에서 스푸핑 인텔리전스를 사용할 수 있으며 Exchange Online 사서함이 없는 독립 실행형 EOP 조직이 제공 됩니다.

스푸핑 방지 기술은 Office 365 Enterprise E5 구독 또는 구독에 대 한 office 365 Advanced Threat Protection (Office 365 ATP) 추가 기능을 사용 하는 조직에만 처음으로 배포 되었습니다.

## <a name="how-can-i-report-spam-or-non-spam-messages-back-to-microsoft"></a>스팸 또는 비스팸 메시지를 Microsoft에 다시 보고하려면 어떻게 합니까?

[Microsoft에 메시지와 파일 보고](report-junk-email-messages-to-microsoft.md)를 참조하세요.

## <a name="im-an-admin-and-i-dont-know-all-of-sources-for-messages-in-my-email-domain"></a>관리자이 고 전자 메일 도메인에 있는 메시지의 모든 원본을 알지 못하는 경우

[전자 메일의 모든 원본을 알지 못하는 것을 볼 수 있습니다](email-validation-and-authentication.md#you-dont-know-all-sources-for-your-email).

## <a name="what-happens-if-i-disable-anti-spoofing-protection-for-my-organization"></a>조직에서 스푸핑 방지 보호를 사용 하지 않도록 설정 하면 어떻게 되나요?

피싱 및 스팸 메일을 놓치는 경우가 많아질 것이므로 이는 권장하지 않습니다. 모든 피싱이 스푸핑이 되는 것은 아니며 모든 스푸핑이 누락되지는 않습니다. 그러나 사용자의 위험은 스푸핑 방지를 사용하는 고객보다 높습니다.

이제 [커넥터에 대 한 향상 된 필터링](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors) 을 사용할 수 있으므로 MX 레코드가 EOP에 전자 메일을 배달 하기 전에 다른 서버 또는 서비스를 가리키는 경우 스푸핑 방지 보호를 해제 하는 것이 더 이상 권장 되지 않습니다.

## <a name="does-anti-spoofing-protection-mean-i-will-be-protected-from-all-phishing"></a>스푸핑 방지 보호는 모든 피싱 으로부터 보호 될 것 이라는 의미 입니까?

안타깝게도 공격자는 다른 기술 (예: 손상 된 계정 또는 무료 전자 메일 서비스의 계정) 사용에 적응 합니다. 그러나 피싱 방지 보호 기능은 이러한 다른 유형의 피싱 방법을 보다 효율적으로 검색 하는 데 도움이 됩니다. EOP의 보호 계층은 함께 작동 하 고 서로의 위에 구축 됩니다.

## <a name="do-other-large-email-services-block-unauthenticated-inbound-email"></a>다른 대규모 전자 메일 서비스가 인증 되지 않은 인바운드 전자 메일을 차단 하나요?

거의 모든 대규모 전자 메일 서비스는 기존 SPF, DKIM 및 DMARC 검사를 구현 합니다. 일부 서비스는 좀 더 엄격한 검사를 수행 하지만 인증 되지 않은 전자 메일을 차단 하 고이를 스푸핑된 메시지로 취급 하기 위해 EOP을 수행 하는 경우는 거의 없습니다. 그러나 업계에서는 특히 피싱 문제로 인해 인증 되지 않은 전자 메일의 문제를 보다 잘 파악 하 고 있습니다.

## <a name="do-i-still-need-to-enable-the-advanced-spam-filter-setting-spf-record-hard-fail-_markasspamspfrecordhardfail_-if-i-enable-anti-spoofing"></a>스푸핑 방지를 사용 하도록 설정한 경우에도 고급 스팸 필터 설정 "SPF record: hard fail" (_MarkAsSpamSpfRecordHardFail_)을 사용 하도록 설정 해야 하나요?

아니요. SPF 하드에 오류가 발생 하는 것은 아니지만 보다 광범위 한 조건 집합으로 간주 되므로이 ASF 설정은 더 이상 필요 하지 않습니다. 스푸핑 방지를 사용하고 **SPF 레코드: 하드 실패**(_MarkAsSpamSpfRecordHardFail_)를 켠 경우 더 많은 오탐지가 발생할 것입니다.

스팸 또는 피싱 메시지를 검색 하는 경우에는이 기능을 사용 하지 않는 것이 좋지만 대부분의 경우에는 대개 가양성을 생성 하는 것이 좋습니다. 자세한 내용은 [EOP의 ASF (Advanced 스팸 필터) 설정을](advanced-spam-filtering-asf-options.md)참조 하십시오.

## <a name="does-sender-rewriting-scheme-help-fix-forwarded-email"></a>보낸 사람 다시 쓰기 체계가 전달 된 전자 메일을 수정 합니까?

SRS는 전달된 전자 메일 문제를 부분적으로만 수정합니다. SRS는에서 SMTP **메일**을 다시 작성 하 여 전달 된 메시지가 다음 목적지에서 SPF를 통과 하도록 할 수 있습니다. 그러나 위조 방지는 보낸 사람 주소 또는 DKIM 서명 도메인 (또는 기타 신호의)을 사용 하 여 **보내는** **출처** 를 기반으로 하기 때문에 SRS 전달 전자 메일이 스푸핑된로 표시 되지 않도록 하는 것은 충분 하지 않습니다.
