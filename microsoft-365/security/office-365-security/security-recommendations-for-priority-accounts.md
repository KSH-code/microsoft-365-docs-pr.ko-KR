---
title: Microsoft 365의 우선 순위 계정에 대한 보안 권장 사항
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: Admin
ms.topic: conceptual
ms.date: ''
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: ''
ms.collection:
- M365-security-compliance
description: 관리자는 Microsoft 365 조직의 우선 순위 계정에 대한 보안 설정을 높이고 보고서, 경고 및 조사를 사용하는 방법을 배울 수 있습니다.
ms.openlocfilehash: 9788131ea881a1cb3c36a60dfaac01ed5daf0901
ms.sourcegitcommit: 5ba0015c1554048f817fdfdc85359eee1368da64
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/06/2021
ms.locfileid: "49769253"
---
# <a name="security-recommendations-for-priority-accounts-in-microsoft-365"></a>Microsoft 365의 우선 순위 계정에 대한 보안 권장 사항

조직의 임원에게 작업을 요청하는 긴급 메시지를 받은 경우 어떻게 하나요? 이 작업을 하나요? 대부분의 사람들은 요청을 준수합니다.

공격자에 대해 무작위 또는 알 수 없는 사용자의 자격 증명을 얻기 위해 임의 Net을 캐스팅하는 일반 피싱 공격은 비효율적입니다. 반면, 강력  또는 권한 위치에  있는 사용자를 대상으로 하는 스피어 피싱 또는 고래 공격은 공격자에 대한 보상이 훨씬 더 많이 있습니다. 이러한 우선 순위 계정이 손상된 경우 공격자는 조직 내의 관리자, 재무, 제품 또는 물리적 액세스 기능이 있는 계정에 액세스할 수 있습니다.

Microsoft 365 및 Office 365용 Microsoft Defender에는 우선 순위 계정에 대한 추가 보안 계층을 제공하는 데 도움이 되는 다양한 기능이 포함되어 있습니다. 사용 가능한 기능 및 사용 방법에 대한 설명은 이 문서에 설명됩니다.

![아이콘 양식의 보안 권장 사항 요약](../../media/security-recommendations-for-priority-users.png)

## <a name="increase-sign-in-security-for-priority-accounts"></a>우선 순위 계정에 대한 로그인 보안 강화

우선 순위 계정을 사용하려면 로그인 보안을 강화해야 합니다. MFA(다단계 인증)를 요구하고 레거시 인증 프로토콜을 사용할 수 있도록 설정하여 로그인 보안을 강화할 수 있습니다.

자세한 내용은 [1단계를 참조하세요. MFA를 사용하여](https://docs.microsoft.com/microsoft-365/solutions/empower-people-to-work-remotely-secure-sign-in)원격 작업자에 대한 로그인 보안을 강화합니다. 이 문서는 원격 작업자에 대한 것이지만 우선 순위 사용자에게는 동일한 개념이 적용됩니다.

**참고**:

- 기본 인증은 EWS(Exchange Web Services), EWS(Exchange Online), Exchange ActiveSync, POP3, IMAP4 및 원격 PowerShell에서 사용되지 않습니다. 자세한 내용은 이 블로그 [게시물을 참조하세요.](https://developer.microsoft.com/office/blogs/deferred-end-of-support-date-for-basic-authentication-in-exchange-online/)

- Exchange [Online의](https://docs.microsoft.com/exchange/clients-and-mobile-in-exchange-online/disable-basic-authentication-in-exchange-online) 인증 정책 및 [클라이언트 액세스](https://docs.microsoft.com/exchange/clients-and-mobile-in-exchange-online/client-access-rules/client-access-rules) 규칙을 사용하여 POP3, IMAP4 및 인증된 SMTP와 같은 기본 인증 및 레거시 인증 프로토콜을 차단할 수 있습니다.

- 개별 사서함에서 POP3 및 IMAP4 액세스를 사용하지 않도록 설정할 수 있습니다. 조직 수준에서 인증된 SMTP를 사용하지 않도록 설정하고 인증된 SMTP를 계속 필요로 하는 특정 사서함에서 사용하도록 설정할 수 있습니다. 자세한 내용은 다음 항목을 참조하세요.
  - [사용자에 대해 POP3 또는 IMAP4 액세스 사용 또는 사용 안 하도록 설정](https://docs.microsoft.com/exchange/clients-and-mobile-in-exchange-online/pop3-and-imap4/enable-or-disable-pop3-or-imap4-access)
  - [인증된 클라이언트 SMTP 전송(SMTP AUTH) 사용 또는 사용 안 하도록 설정](https://docs.microsoft.com/exchange/clients-and-mobile-in-exchange-online/authenticated-client-smtp-submission)

## <a name="use-strict-preset-security-policies-for-priority-accounts"></a>우선 순위 계정에 대해 엄격한 미리 설정 보안 정책 사용

우선 순위 사용자는 EOP(Exchange Online Protection) 및 Office 365용 Defender에서 사용할 수 있는 다양한 보호에 대해 더 엄격한 작업이 필요합니다.

예를 들어 스팸으로 분류된 메시지를 정크 메일 폴더로 배달하는 대신 우선 순위 계정에 사용할 경우 동일한 메시지를 차단해야 합니다.

미리 설정한 보안 정책에서 Strict 프로필을 사용하여 우선 순위 계정에 대해 이 엄격한 접근 방식을 구현할 수 있습니다.

미리 설정한 보안 정책은 EOP 및 Office 365용 Defender의 모든 보호에 대해 권장되는 Strict 정책 설정을 적용할 수 있는 편리하고 중앙 위치입니다. 자세한 내용은 EOP 및 [Office 365용 Microsoft Defender의](preset-security-policies.md)미리 설정 보안 정책을 참조하세요.

Strict 정책 설정이 기본 및 표준 정책 설정과 어떻게 다른지 자세한 내용은 EOP 및 [Office 365용 Microsoft Defender](recommended-settings-for-eop-and-office365-atp.md)보안에 대한 권장 설정을 참조하세요.

## <a name="apply-user-tags-to-priority-accounts"></a>우선 순위 계정에 사용자 태그 적용

Microsoft Defender for Office 365 계획 2(Microsoft 365 E5 또는 추가 기능 구독의 일부)의 사용자 태그는 보고서 및 인시던트 조사에서 특정 사용자 또는 사용자 그룹을 신속하게 식별하고 분류하는 방법입니다.

**우선 순위 계정은** 우선 순위 계정과 관련된 인시던트 및 경고를 식별하는 데 사용할 수 있는 기본 제공 사용자 태그(시스템 태그라고도 하는) 유형입니다. 우선 순위 계정에 대한 **자세한 내용은** 우선 순위 계정 관리 [및 모니터링을 참조하세요.](https://docs.microsoft.com/microsoft-365/admin/setup/priority-accounts)

사용자 지정 태그를 만들어 우선 순위 계정을 추가로 식별하고 분류할 수도 있습니다. 자세한 내용은 [사용자 태그를 참조하세요.](user-tags.md) 사용자 지정 사용자 **태그와** 동일한 인터페이스에서 우선 순위 계정(시스템 태그)을 관리할 수 있습니다.

## <a name="monitor-priority-accounts-in-alerts-reports-and-detections"></a>경고, 보고서 및 검색에서 우선 순위 계정 모니터링

우선 순위 사용자를 보호하고 태그를 지정한 후 EOP 및 Office 365용 Defender에서 사용 가능한 보고서, 경고 및 조사를 사용하여 우선 순위 계정과 관련된 인시던트 또는 검색을 빠르게 식별할 수 있습니다. 다음 표에서는 사용자 태그를 지원하는 기능에 대한 설명을 제공합니다.

<br>

****

|기능|설명|
|---|---|
|경고|영향을 받는 사용자의 사용자 태그는 보안 및 준수  센터의 경고 보기 페이지에서 & 있습니다. 자세한 내용은 경고 [보기를 참조하세요.](https://docs.microsoft.com/microsoft-365/compliance/alert-policies#viewing-alerts)|
|위협 탐색기 <p> 실시간 탐지|**위협 탐색기(Office** 365 계획 2용  Microsoft Defender) 또는 실시간 검색(Office 365 계획 1용 Microsoft Defender)에서 사용자 태그가 전자 메일 그리드 보기 및 전자 메일 세부 정보 플라이아웃에 표시됩니다. 사용자 태그는 필터링 가능한 속성으로도 사용할 수 있습니다. 자세한 내용은 [위협 탐색기에서 태그를 참조하세요.](threat-explorer.md#tags-in-threat-explorer)|
|캠페인 보기|사용자 태그는 Microsoft Defender for Office 365 계획 2의 캠페인 보기에서 필터링할 수 있는 여러 속성 중 하나입니다. 자세한 내용은 캠페인 [보기를 참조하세요.](campaigns.md)|
|위협 방지 상태 보고서|위협 방지 상태 보고서의 거의 모든 보기 및 세부 정보 테이블에서 우선 순위 계정으로 결과를 **필터링할 수 있습니다.** 자세한 내용은 위협 방지 상태 [보고서를 참조하세요.](view-email-security-reports.md#threat-protection-status-report)|
|우선 순위 계정 보고서에 대한 전자 메일 문제|**EAC(Exchange** 관리 센터)의 우선 순위 계정 보고서에 대한 전자 메일 문제에는 우선 순위 계정에 대한 미확인 및 지연된 메시지에 대한 **정보가 포함되어 있습니다.** 자세한 내용은 우선 순위 계정 [보고서에 대한 전자 메일 문제를 참조하세요.](https://docs.microsoft.com/exchange/monitoring/mail-flow-reports/mfr-email-issues-for-priority-accounts-report)|
|

## <a name="see-also"></a>참고 항목

[Office 365용 Microsoft Defender의 우선 순위 계정 보호 발표](https://techcommunity.microsoft.com/t5/microsoft-defender-for-office/announcing-priority-account-protection-in-microsoft-defender-for/ba-p/1696385)
