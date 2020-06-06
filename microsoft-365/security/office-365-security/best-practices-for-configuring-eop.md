---
title: EOP 구성을 위한 모범 사례
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
ms.assetid: faf1efd1-3b0c-411a-804d-17f37292eac0
description: EOP (독립 실행형 Exchange Online Protection)에 대해 직접 설정 하 여 성공적인 작동을 방지 하 고 일반적인 구성 오류가 발생 하지 않도록 하려면 다음과 같은 모범 사례 권장 사항을 따르십시오.
ms.openlocfilehash: 69b0789612d6490305ff31d89954bc1d9258ac01
ms.sourcegitcommit: 2de6e07ec55d78a5c5cf2f45732ae68acf058bcf
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/05/2020
ms.locfileid: "44587536"
---
# <a name="best-practices-for-configuring-standalone-eop"></a>독립 실행형 EOP 구성 모범 사례

EOP (독립 실행형 Exchange Online Protection)에 대해 직접 설정 하 여 성공적인 작동을 방지 하 고 일반적인 구성 오류가 발생 하지 않도록 하려면 다음과 같은 모범 사례 권장 사항을 따르십시오. 이 항목에서는 설정 프로세스를 이미 완료했다고 가정합니다. EOP 설정을 완료하지 않은 경우 [EOP 서비스 설정](set-up-your-eop-service.md)을 참조하세요.

## <a name="use-a-test-domain"></a>테스트 도메인 사용

볼륨이 큰 프로덕션 도메인에서 구현하기 전에 테스트 도메인, 하위 도메인 또는 볼륨이 작은 도메인을 사용하여 서비스 기능을 시험적으로 사용해 보는 것이 좋습니다.

## <a name="synchronize-recipients"></a>받는 사람 동기화

조직의 온-프레미스 Active Directory 환경에 기존 사용자 계정이 있는 경우 해당 계정을 클라우드의 Azure Active Directory와 동기화 할 수 있습니다. 디렉터리 동기화를 사용하는 것이 좋습니다. 디렉터리 동기화를 사용할 경우의 이점 및 이를 설정하기 위해 수행해야 하는 단계에 대한 자세한 내용은 [EOP에서 메일 사용자 관리](manage-mail-users-in-eop.md)를 참조하세요.

## <a name="recommended-settings"></a>권장 설정

조직의 요구 사항을 충족 하기 위해 보안 설정을 사용자 지정 하는 보안 관리자를 지원 합니다. 일반적으로 EOP 및 Office 365 ATP에는 표준 및 Strict의 두 가지 보안 수준이 권장 됩니다. 이러한 설정은 [EOP 및 Office 365 ATP 보안에 대 한 권장 설정](recommended-settings-for-eop-and-office365-atp.md)에 나와 있습니다.

### <a name="miscellaneousnon-policy-settings"></a>기타/정책 외 설정

이러한 설정은 보안 정책 밖에 있는 다양 한 기능을 포함 합니다.

|||||
|---|---|---|---|
|**보안 기능 이름**|**표준을**|**항등**|**설명**|
|[스푸핑을 방지할 수 있도록 SPF 설정](set-up-spf-in-office-365-to-help-prevent-spoofing.md)|예|예||
|[DKIM을 사용하여 Office 365의 사용자 지정 도메인에서 전송한 아웃바운드 전자 메일의 유효성 검사](use-dkim-to-validate-outbound-email.md)|예|예||
|[DMARC를 사용하여 Office 365에서 전자 메일 유효성 검사](use-dmarc-to-validate-email.md)|예|예|`action=quarantine`표준 및 Strict에 사용 `action=reject` 합니다.|
|[보고서 메시지 추가 기능](enable-the-report-message-add-in.md) 을 배포 하 여 최종 사용자가 의심 스러운 전자 메일 보고 기능을 향상 시킵니다.|예|예||
|맬웨어 및 스팸 보고서 예약|예|예||
|외부 도메인에 대 한 자동 전달은 허용 하거나 모니터링 하지 않아야 합니다.|예|예||
|통합 감사를 사용 하도록 설정 해야 함|예|예||
|[사서함에 대 한 IMAP 연결](https://docs.microsoft.com/Exchange/clients-and-mobile-in-exchange-online/pop3-and-imap4/enable-or-disable-pop3-or-imap4-access)|사용 안 함|사용 안 함||
|[사서함에 대 한 POP 연결](https://docs.microsoft.com/Exchange/clients-and-mobile-in-exchange-online/pop3-and-imap4/enable-or-disable-pop3-or-imap4-access)|사용 안 함|사용 안 함||
|인증 된 SMTP 전송|사용 안 함|사용 안 함|POP3 및 IMAP4 클라이언트에서 전자 메일을 보내려면 인증 된 클라이언트 SMTP 전송 (클라이언트 SMTP 전송 또는 SMTP 인증이 라고도 함)이 필요 합니다.|
|사서함에 대 한 EWS 연결|사용 안 함|사용 안 함||
|[PowerShell 연결](https://docs.microsoft.com/powershell/exchange/exchange-online/disable-access-to-exchange-online-powershell)|사용 안 함|사용 안 함|사서함 사용자 또는 메일 사용자 ( [Get-user](https://docs.microsoft.com/powershell/module/exchange/get-user) cmdlet에서 반환 된 사용자 개체)에 사용할 수 있습니다.|
|가능한 경우 [위장 인텔리전스](learn-about-spoof-intelligence.md) 를 사용 하 여 보낸 사람에 게 허용 목록|예|예||
|[DBEB (디렉터리 기반 Edge 차단)](https://docs.microsoft.com/Exchange/mail-flow-best-practices/use-directory-based-edge-blocking)|사용|사용|도메인 유형 = 신뢰할 수 있음|
|[모든 관리자 계정에 대해 multi-factor authentication 설정](https://docs.microsoft.com/microsoft-365/admin/security-and-compliance/set-up-multi-factor-authentication)|사용|사용||
|

## <a name="troubleshooting"></a>문제 해결

관리 센터의 보고서를 사용 하 여 일반적인 문제 및 추세 문제를 해결 합니다. 메시지 추적 도구를 사용하면 메시지에 대한 단일 지점 관련 데이터를 찾을 수 있습니다. 보고에 대한 자세한 내용은 [Exchange Online Protection의 보고 및 메시지 추적](reporting-and-message-trace-in-exchange-online-protection.md)을 참조하세요. [보안 & 준수 센터의 메시지 추적](message-trace-scc.md)에서 메시지 추적 도구에 대해 자세히 알아보세요.

## <a name="report-false-positives-and-false-negatives-to-microsoft"></a>Microsoft에 가양성 및 거짓 네거티브 보고

모든 사용자에 대 한 서비스의 스팸 필터링을 향상 시키려면 가양성 (불량으로 표시 된 전자 메일)과 가양성 (잘못 된 전자 메일 허용)을 Microsoft에 분석용으로 보고 해야 합니다. 자세한 내용은 [Microsoft에 메시지와 파일 보고](report-junk-email-messages-to-microsoft.md)를 참조하세요.

## <a name="create-mail-flow-rules"></a>메일 흐름 규칙 만들기

비즈니스 요구를 충족 하기 위해 메일 흐름 규칙 (전송 규칙이 라고도 함) 또는 사용자 지정 필터를 만듭니다.

새 규칙을 프로덕션 환경으로 배포할 때는 먼저 테스트 모드 중 하나를 선택하여 규칙의 효과를 확인합니다. 규칙이 원하는 방식으로 작동하면 규칙 모드를 **적용**으로 변경합니다.

새 규칙을 배포할 때는 적용된 규칙을 모니터링하기 위해 **문제 보고서 생성** 동작을 추가할 수 있습니다.

조직에 온-프레미스 Exchange와 Exchange Online이 모두 포함 된 하이브리드 환경에서는 메일 흐름 규칙에서 사용 하는 조건을 고려해 야 합니다. 규칙을 전체 조직에 적용 하려면 온-프레미스 Exchange와 Exchange Online 모두에서 사용할 수 있는 조건을 사용 해야 합니다. 대부분의 조건은 두 환경 모두에서 사용할 수 있지만, 한 환경 에서만 사용할 수 있는 경우도 있습니다. 자세한 내용은 [메일 흐름 규칙 (전송 규칙)에서 Exchange Online을](https://docs.microsoft.com/exchange/security-and-compliance/mail-flow-rules/mail-flow-rules)확인 하세요.
