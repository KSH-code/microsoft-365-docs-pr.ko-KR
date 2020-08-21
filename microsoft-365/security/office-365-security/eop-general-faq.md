---
title: EOP 관련 일반 FAQ(질문과 대답)
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
ms.assetid: 9dbff00a-474e-4452-aeb5-5be9a6b8c6d5
ms.custom:
- seo-marvel-apr2020
description: EOP(Exchange Online Protection) 클라우드 호스팅 전자 메일 필터링 서비스에 대한 가장 일반적인 질문에 대한 대답을 확인합니다.
ms.openlocfilehash: 42162ea841f876fc5e958d67fab61dbe4bffe9de
ms.sourcegitcommit: e12fa502bc216f6083ef5666f693a04bb727d4df
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/20/2020
ms.locfileid: "46827764"
---
# <a name="eop-general-faq"></a>EOP 관련 일반 FAQ(질문과 대답)

다음은 EOP(Exchange Online Protection) 클라우드 호스팅 전자 메일 필터링 서비스에 대한 가장 일반적인 질문과 그에 대한 대답입니다. 그 이외의 FAQ(질문과 대답) 항목은 다음 링크를 참조하십시오.

- [EOP 대기, 지연 및 반송 메시지 FAQ](eop-queued-deferred-and-bounced-messages-faq.md)

- [위임된 관리 FAQ](delegated-administration-faq.md)

- [스팸 방지 및 보호 FAQ](anti-spam-protection-faq.md)

- [Quarantine FAQ](quarantine-faq.md)

- [맬웨어 방지 보호 FAQ](anti-malware-protection-faq-eop.md)

- [메시지 추적 FAQ](https://docs.microsoft.com/exchange/monitoring/trace-an-email-message/message-trace-faq)

## <a name="what-is-eop"></a>EOP란 무엇입니까?

EOP는 스팸 및 맬웨어로부터 고객을 보호하고 사용자 지정 정책 규칙을 구현하도록 구축된 클라우스 호스트 전자 메일 필터링 서비스입니다. EOP는 Exchange Online 사서함이 포함된 모든 Microsoft 365 구독에 포함됩니다. EOP는 온-프레미스 전자 메일 환경을 보호하기 위한 독립 실행형 서비스 제품으로도 사용할 수 있습니다.

## <a name="how-do-i-sign-up-for-an-eop-trial-or-purchase-eop"></a>EOP 평가판을 등록하거나 EOP를 구입할 수 있는 방법은 어떻게 됩니까?

[Exchange Online Protection 홈 페이지](https://products.office.com/exchange/exchange-email-security-spam-protection)에서 EOP 평가판을 등록하거나 EOP를 구입할 수 있습니다. 구입한 평가판의 기능은 유료 구독과 동일하지만, [Exchange Online Protection 서비스 설명](https://products.office.com/exchange/microsoft-exchange-server-licensing-licensing-overview)에서 설명하는 Exchange Enterprise CAL with Services 구독 계획에서 제공되는 추가 기능도 포함됩니다.

## <a name="how-is-eop-priced"></a>EOP 가격은 어떻게 책정됩니까?

EOP는 사용자별로 라이선스가 부여됩니다. 최신 가격 정보는 [Exchange Online Protection 홈 페이지](https://products.office.com/exchange/exchange-email-security-spam-protection)를 참조하십시오.

## <a name="how-long-does-it-take-to-put-eop-into-production"></a>EOP를 프로덕션에 배치하는 데 얼마나 소요됩니까?

MX 레코드를 변경할 경우 [EOP 서비스 설정](set-up-your-eop-service.md) 및 EOP를 통한 메일 흐름에 설명된 단계에 따라 필터링이 즉시 시작됩니다. MX 레코드가 DNS를 통해 전파되려면 24~48시간 정도 소요될 수 있습니다. 이 프로세스 중에 언제든지 보호 설정을 미세하게 미세 조사할 수 있습니다.

## <a name="do-i-have-to-use-all-features-of-microsoft-365-to-use-eop-what-if-i-just-want-eop-protection-and-thats-all"></a>EOP를 사용하려면 Microsoft 365의 모든 기능을 이용해야 하나요? EOP 보호만 사용하면 됩니까?

Microsoft 365의 다른 기능은 사용하지 않고 EOP를 사용하여 온-프레미스 사서함을 보호할 수 있습니다. 이를 독립 실행형 구독이라고 합니다. EOP 기능 목록은 [Exchange Online Protection 서비스 설명](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description)에서 찾을 수 있습니다.

## <a name="why-do-i-need-a-microsoft-365-tenant-when-signing-up-for-email-filtering-through-eop"></a>EOP를 통해 전자 메일 필터링에 등록할 때 Microsoft 365 테넌트가 필요한 이유는 무엇입니까?

Microsoft 365는 Microsoft 365 테넌트를 통해 액세스할 수 있는 제품과 서비스 모음에 지정된 이름입니다. Microsoft 365 테넌트는 전자 메일 필터링용 라이선스를 추가할 수 있는 시작점으로 생각하면 됩니다.

## <a name="does-eop-have-a-communication-portal-where-i-can-find-out-about-known-issues-and-expected-resolutions-what-about-new-features"></a>EOP에도 알려진 문제와 필요한 해결 방법에 대한 정보를 찾을 수 있는 통신 포털이 있습니까? 새로운 기능에 대한 정보는 어떻게 확인할 수 있습니까?

Microsoft 365 관리 센터에서 이러한 정보 중 일부가 제공됩니다. 서비스 수준 이벤트가 발생하는 경우 Microsoft 365 관리 센터에 로그인한 후 통신 경고(보통 주 아이콘이 표시됨)를 확인해야 합니다. 모든 항목을 읽고 적절한 조치를 취하는 것이 좋습니다.

새 EOP 기능과 관련하여 [비즈니스용 Microsoft 365 로드맵은](https://www.microsoft.com/microsoft-365/roadmap?filters=O365) 예정된 새로운 기능에 대한 정보를 찾는 데 적합한 리소스입니다. 또한 새로운 기능에 대한 블로그 기사를 Microsoft 365 블로그 [웹 사이트에 게시할 예정입니다.](https://www.microsoft.com/microsoft-365/blog/)

## <a name="does-the-service-work-with-legacy-exchange-versions-such-as-exchange-server-2010-and-non-exchange-environments"></a>Exchange Server 2010 등의 레거시 Exchange 버전 및 Exchange 이외의 환경에서도 서비스가 작동합니까?

예, 서비스는 서버에 상관없이 사용 가능하며 모든 SMTP 메일 전송 에이전트에서 사용할 수 있습니다.

## <a name="what-size-organization-can-use-the-service"></a>어떤 규모의 조직에서 서비스를 사용할 수 있습니까?

모든 규모의 조직에서 서비스를 사용할 수 있습니다. EOP 네트워크는 조직의 확장을 수용할 수 있는 충분한 용량을 갖추고 있으므로 조직이 급속하게 확장되더라도 전혀 문제가 되지 않습니다.

## <a name="what-permissions-do-i-need-to-set-up-eop"></a>EOP를 설정하려면 어떤 사용 권한이 필요합니까?

EOP를 구성하려면 전역 관리자 또는 Exchange 회사 관리자(조직 관리 역할 그룹)이어야 합니다.

## <a name="how-do-i-know-my-data-and-private-information-are-safe"></a>내 데이터와 개인 정보가 안전한지 어떻게 알 수 있습니까?

SLA(서비스 수준 계약)에 대한 정보를 비롯하여 데이터 및 개인 정보의 안전을 확보하기 위해 Microsoft에서 수행한 단계에 대한 자세한 내용을 보려면 [Office 365 보안 센터](https://www.microsoft.com/trust-center)를 참조하십시오.

## <a name="are-there-any-limits-i-should-be-aware-of-such-as-message-size-limitations"></a>메시지 크기 제한 등 주의해야 하는 제한 사항이 있습니까?

예. EOP의 제한에 대한 자세한 내용은 [Exchange Online Protection 제한](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-limits)을 참조하세요.

## <a name="does-eop-support-powershell"></a>EOP에서 PowerShell이 지원됩니까?

예, 전체 EOP 기능을 PowerShell을 통해 사용할 수 있습니다: Exchange Online 사서함이 있는 조직의 경우 원격 PowerShell; 독립 실행형 EOP 조직용 독립 실행형 EOP PowerShell 자세한 내용은 [Exchange Online PowerShell 및](https://docs.microsoft.com/powershell/exchange/exchange-online-powershell) [Exchange Online Protection PowerShell을 참조하세요.](https://docs.microsoft.com/powershell/exchange/exchange-online-protection-powershell)
