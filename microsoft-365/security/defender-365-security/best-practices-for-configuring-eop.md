---
title: EOP 구성을 위한 모범 사례
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: conceptual
localization_priority: Normal
ms.assetid: faf1efd1-3b0c-411a-804d-17f37292eac0
description: 독립 실행형 EOP(Exchange Online Protection)에 대한 모범 사례 권장 사항을 따라 성공을 설정하고 일반적인 구성 오류를 방지합니다.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: dfd0b7290bdcded887ef6b81d5b0d4acbdd6cddb
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51073487"
---
# <a name="best-practices-for-configuring-standalone-eop"></a>독립 실행형 EOP 구성 모범 사례

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**적용 대상**
-  [Exchange Online Protection 독립 실행형](exchange-online-protection-overview.md)

독립 실행형 EOP(Exchange Online Protection)에 대한 모범 사례 권장 사항을 따라 성공을 설정하고 일반적인 구성 오류를 방지합니다. 이 항목에서는 설정 프로세스를 이미 완료했다고 가정합니다. EOP 설정을 완료하지 않은 경우 [EOP 서비스 설정](set-up-your-eop-service.md)을 참조하세요.

## <a name="use-a-test-domain"></a>테스트 도메인 사용

볼륨이 큰 프로덕션 도메인에서 구현하기 전에 테스트 도메인, 하위 도메인 또는 볼륨이 작은 도메인을 사용하여 서비스 기능을 시험적으로 사용해 보는 것이 좋습니다.

## <a name="synchronize-recipients"></a>받는 사람 동기화

조직에 기존 사용자 계정이 있는 경우 해당 계정을 클라우드의 Azure Active Directory와 동기화할 수 있습니다. 디렉터리 동기화를 사용하는 것이 좋습니다. 디렉터리 동기화를 사용할 경우의 이점 및 이를 설정하기 위해 수행해야 하는 단계에 대한 자세한 내용은 [EOP에서 메일 사용자 관리](manage-mail-users-in-eop.md)를 참조하세요.

## <a name="recommended-settings"></a>권장 설정

보안 관리자는 조직의 요구 사항을 충족하기 위해 보안 설정을 사용자 지정할 수 있습니다. 일반적으로 EOP와 Office 365용 Microsoft Defender에는 표준 및 엄격의 두 가지 보안 수준이 있습니다. 이러한 설정은 EOP 및 [Office 365용 Microsoft Defender](recommended-settings-for-eop-and-office365.md)보안에 대한 권장 설정에 나열되어 있습니다.

### <a name="miscellaneousnon-policy-settings"></a>기타/비 정책 설정

이러한 설정은 보안 정책 외부에 있는 다양한 기능을 제공합니다.

<br>

****

|보안 기능 이름|Standard|Strict|Comment|
|---|---|---|---|
|[스푸핑을 방지할 수 있도록 SPF 설정](set-up-spf-in-office-365-to-help-prevent-spoofing.md)|예|예||
|[DKIM을 사용하여 Office 365의 사용자 지정 도메인에서 전송한 아웃바운드 전자 메일의 유효성 검사](use-dkim-to-validate-outbound-email.md)|예|예||
|[DMARC를 사용하여 Office 365에서 전자 메일 유효성 검사](use-dmarc-to-validate-email.md)|예|예|Standard `action=quarantine` 및 `action=reject` Strict에 사용|
|보고서 [메시지](enable-the-report-message-add-in.md) 추가 기능 또는 [](enable-the-report-phish-add-in.md) 피싱 보고 추가 기능을 배포하여 의심스러운 전자 메일의 최종 사용자 보고 개선|예|예||
|맬웨어 및 스팸 보고서 예약|예|예||
|외부 도메인에 대한 자동 전달을 사용할 수 없습니다.|예|예||
|통합 감사를 사용하도록 설정해야 합니다.|예|예||
|[사서함에 대한 IMAP 연결](/Exchange/clients-and-mobile-in-exchange-online/pop3-and-imap4/enable-or-disable-pop3-or-imap4-access)|사용 안 함|사용 안 함||
|[사서함에 대한 POP 연결](/Exchange/clients-and-mobile-in-exchange-online/pop3-and-imap4/enable-or-disable-pop3-or-imap4-access)|사용 안 함|사용 안 함||
|인증된 SMTP 전송|사용 안 함|사용 안 함|전자 메일을 생성하고 보내는 POP3 및 IMAP4 클라이언트와 응용 프로그램 및 장치에는 인증된 클라이언트 SMTP 전송(클라이언트 SMTP 전송 또는 SMTP AUTH라고도 알려지기)이 필요합니다. <p> SMTP AUTH를 전역적으로 또는 선택적으로 사용 또는 사용하지 않도록 설정하는 방법에 대한 지침은 [Exchange Online에서 인증된](/exchange/clients-and-mobile-in-exchange-online/authenticated-client-smtp-submission)클라이언트 SMTP 전송 사용 또는 사용 안 하도록 설정을 참조하세요.|
|사서함에 대한 EWS 연결|사용 안 함|사용 안 함|Outlook에서는 약속이 있는/약속이 있는 경우, 부재 중 설정 및 일정 공유에 Exchange 웹 서비스를 사용합니다. 전역적으로 EWS를 사용하지 않도록 설정할 수 없는 경우 다음 옵션이 있습니다. <ul><li>클라이언트가 [최신](/exchange/clients-and-mobile-in-exchange-online/disable-basic-authentication-in-exchange-online) 인증(최신 인증)을 지원하는 경우 인증 정책을 사용하여 EWS에서 기본 인증을 사용하지 못하도록 합니다.</li><li>클라이언트 [액세스 규칙을 사용하여](https://docs.microsoft.com/exchange/clients-and-mobile-in-exchange-online/client-access-rules/client-access-rules) EWS를 특정 사용자 또는 원본 IP 주소로 제한합니다.</li><li>전역적으로 또는 사용자별 특정 응용 프로그램에 대한 EWS 액세스를 제어합니다. 자세한 내용은 [Exchange에서 EWS에 대한 액세스 제어를 참조하세요.](/exchange/client-developer/exchange-web-services/how-to-control-access-to-ews-in-exchange)</li></ul> <p> 보고서 [메시지 추가](enable-the-report-message-add-in.md) 기능 [](enable-the-report-phish-add-in.md) 및 피싱 보고 추가 기능에서는 지원되는 환경에서 기본적으로 REST를 사용하지만 REST를 사용할 수 없는 경우 EWS로 변경됩니다. REST를 사용하는 지원되는 환경은 다음입니다.<ul><li>Exchange Online</li><li>Exchange 2019 또는 Exchange 2016</li><li>Microsoft 365 구독 또는 일회성 구매 Outlook 2019의 현재 Windows용 Outlook</li><li>Microsoft 365 구독 또는 일회용 구매 Outlook for Mac 2016 이상에서 Mac용 현재 Outlook을 사용할 수 있습니다.</li><li>iOS 및 Android용 Outlook</li><li>웹용 Outlook</li></ul>|
|[PowerShell 연결](/powershell/exchange/disable-access-to-exchange-online-powershell)|사용 안 함|사용 안 함|사서함 사용자 또는 메일 [사용자(Get-User](/powershell/module/exchange/get-user) cmdlet에서 반환된 사용자 개체)에 사용할 수 있습니다.|
|[스푸핑 인텔리전스를](learn-about-spoof-intelligence.md) 사용하여 허용 목록에 보낸 사람 추가|예|예||
|[DBEB(디렉터리 기반 Edge 차단)](/Exchange/mail-flow-best-practices/use-directory-based-edge-blocking)|사용|사용|도메인 유형 = 권한 있는 도메인|
|[모든 관리자 계정에 대해 다단계 인증 설정](../../admin/security-and-compliance/set-up-multi-factor-authentication.md)|사용|사용||
|

## <a name="troubleshooting"></a>문제 해결

관리 센터의 보고서를 사용하여 일반적인 문제 및 추세를 해결합니다. 메시지 추적 도구를 사용하면 메시지에 대한 단일 지점 관련 데이터를 찾을 수 있습니다. 보고에 대한 자세한 내용은 [Exchange Online Protection의 보고 및 메시지 추적](reporting-and-message-trace-in-exchange-online-protection.md)을 참조하세요. 메시지 추적 도구에 대한 자세한 내용은 보안 및 준수 센터의 메시지 [추적을 & 합니다.](message-trace-scc.md)

## <a name="report-false-positives-and-false-negatives-to-microsoft"></a>Microsoft에 가짓 긍정 및 거짓 부정 보고

모든 사용자에 대해 서비스에서 스팸 필터링을 개선할 수 있도록 분석을 위해 Microsoft에 가음성(양호한 전자 메일이 양호한 것으로 표시) 및 거짓 부정(잘못된 전자 메일 허용)을 Microsoft에 보고해야 합니다. 자세한 내용은 [Microsoft에 메시지와 파일 보고](report-junk-email-messages-to-microsoft.md)를 참조하세요.

## <a name="create-mail-flow-rules"></a>메일 흐름 규칙 만들기

비즈니스 요구를 충족하기 위해 메일 흐름 규칙(전송 규칙) 또는 사용자 지정 필터를 만듭니다.

새 규칙을 프로덕션 환경으로 배포할 때는 먼저 테스트 모드 중 하나를 선택하여 규칙의 효과를 확인합니다. 규칙이 원하는 방식으로 작동하면 규칙 모드를 **적용** 으로 변경합니다.

새 규칙을 배포할 때는 적용된 규칙을 모니터링하기 위해 **문제 보고서 생성** 동작을 추가할 수 있습니다.

조직에 사내 Exchange와 Exchange Online이 모두 포함된 하이브리드 환경에서는 메일 흐름 규칙에 사용하는 조건을 고려합니다. 규칙을 전체 조직에 적용하려는 경우 온-프레미스 Exchange와 Exchange Online 둘 다에서 사용할 수 있는 조건을 사용하세요. 대부분의 조건은 두 환경에서 모두 사용할 수 있는 반면, 한 환경이나 다른 환경에서만 사용할 수 있는 몇 가지 조건이 있습니다. 자세한 내용은 [Exchange Online의 메일 흐름 규칙(전송 규칙)을 통해 자세히 알아보하세요.](/exchange/security-and-compliance/mail-flow-rules/mail-flow-rules)