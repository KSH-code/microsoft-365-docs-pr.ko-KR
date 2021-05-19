---
title: 독립 실행형 EOP 서비스 설정
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: how-to
ms.custom:
- seo-marvel-apr2020
localization_priority: Normal
ms.assetid: d74c6ddf-11b0-43ee-b298-8bb0340895f0
description: 관리자는 EOP(독립 실행형 EOP)를 설정하여 Exchange Online Protection 전자 메일 환경을 보호하는 방법을 배울 수 있습니다.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 63504dd2d729674fd84eff2fd5548c8d077cd1f1
ms.sourcegitcommit: f780de91bc00caeb1598781e0076106c76234bad
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/19/2021
ms.locfileid: "52538978"
---
# <a name="set-up-your-standalone-eop-service"></a>독립 실행형 EOP 서비스 설정

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**적용 대상**
-  [Exchange Online Protection 독립 실행형](exchange-online-protection-overview.md)

이 항목에서는 독립 실행형 EOP(독립 실행형 Exchange Online Protection 방법을 설명합니다. Office 365 도메인 마법사에서 여기로 이동했으며 Exchange Online Protection를 사용하지 않으려면 Office 365 도메인 마법사로 돌아갑니다. 커넥터 구성 방법에 대한 자세한 내용를 보려면 [Configure mail flow using connectors in Office 365](/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow)을 참조하세요.

> [!NOTE]
> 이 항목에서는 사용자가 독립 실행형 시나리오라고 하는 EOP를 통해 사서함을 보호하려는 경우를 가정합니다. 모든 사서함을 클라우드에서 호스트하고 Exchange Online 이 문서의 모든 단계를 완료할 수 없습니다. 클라우드 [사서함을 Exchange Online](https://products.office.com/exchange/compare-microsoft-exchange-online-plans) 계획 비교로 이동하여 클라우드 사서함을 등록하고 구매합니다.
>
> 일부 사서함을 사내에 호스팅하고 일부 사서함은 클라우드에서 호스팅하려는 경우 이를 하이브리드 시나리오라고 합니다. 고급 메일 흐름 설정이 필요합니다. [Exchange Server 하이브리드](/exchange/exchange-hybrid) 배포에서는 하이브리드 메일 흐름에 대해 설명하고 하이브리드 메일 흐름을 설정하는 방법을 보여 주는 리소스에 대한 링크가 있습니다.

## <a name="what-do-you-need-to-know-before-you-begin"></a>시작하기 전에 알아야 할 내용

- 이 작업의 예상 완료 시간: 1시간

- 이 문서의 절차를 수행하려면 Exchange Online Protection 사용 권한을 할당해야 합니다. 특히 조직 관리(전역 관리자) 및 Mail **Flow** 관리자  역할 그룹에 할당되는 원격 및 허용 **도메인** 역할이 필요합니다. 자세한 내용은 독립 실행형 [EOP의](feature-permissions-in-eop.md) 사용 권한 및 EAC를 사용하여 역할 그룹의 구성원 목록 [수정을 참조하세요.](manage-admin-role-group-permissions-in-eop.md#use-the-eac-modify-the-list-of-members-in-role-groups)

- 아직 EOP에 등록하지 않은 경우 [Exchange Online Protection](https://products.office.com/exchange/exchange-email-security-spam-protection)을 방문하여 서비스를 구입하거나 평가판을 신청합니다.

- 이 문서의 절차에 적용할 수 있는 바로 가기 키에 대한 자세한 내용은 Exchange 관리 센터의 바로 가기 키를 [Exchange Online.](/Exchange/accessibility/keyboard-shortcuts-in-admin-center)

> [!TIP]
> 문제가 있나요? [Exchange Online Protection](https://social.technet.microsoft.com/Forums/forefront/home?forum=FOPE) 포럼에서 도움을 요청하세요.

## <a name="step-1-use-the-microsoft-365-admin-center-to-add-and-verify-your-domain"></a>1단계: Microsoft 365 관리 센터를 사용하여 도메인 추가 및 확인

1. Microsoft 365 [관리 센터에서](../../admin/admin-overview/about-the-admin-center.md)설치로 이동하여 서비스에 도메인을 추가합니다. 

2. 도메인 소유권 확인을 위해 해당 DNS 레코드를 DNS 호스팅 공급자에 추가하는 단계를 수행합니다.

> [!TIP]
> [도메인을](../../admin/setup/add-domain.md) 추가하고 Office 365 DNS 호스팅 공급자에서 DNS 레코드 만들기를 Office 365 도메인을 서비스에 추가하고 [DNS를](../../admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider.md) 구성할 때 참조할 수 있는 유용한 리소스입니다.

## <a name="step-2-add-recipients-and-optionally-enable-dbeb"></a>2단계: 받는 사람을 추가하고 선택적으로 DBEB 사용

메일이 EOP 서비스를 통해 전달되도록 구성하려는 경우 먼저 받는 사람을 서비스에 추가하는 것이 좋습니다. [EOP에서 메일 사용자 관리](manage-mail-users-in-eop.md)에 설명된 것처럼 이러한 방법에는 몇 가지가 있습니다. 또한 받는 사람을 추가한 후에 서비스 내에서 받는 사람 확인을 적용하기 위해 DBEB(디렉터리 기반 Edge 차단)를 사용 가능하게 설정하려면 도메인 유형을 신뢰할 수 있음으로 설정해야 합니다. DBEB에 대한 자세한 내용은 [Use Directory Based Edge Blocking to Reject Messages Sent to Invalid Recipients](/exchange/mail-flow-best-practices/use-directory-based-edge-blocking)를 참조하세요.

## <a name="step-3-use-the-eac-to-set-up-mail-flow"></a>3단계: EAC를 사용하여 메일 흐름 설정

EOP 및 온-프레미스 메일 서버 간의 메일 흐름을 가능하게 하는 커넥터를 EAC(Exchange 관리 센터)에서 만듭니다. 자세한 내용은 Set [up connectors to route mail between Microsoft 365 your own email servers을 참조하십시오.](/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/set-up-connectors-to-route-mail)

### <a name="how-do-you-know-this-worked"></a>작동 여부는 어떻게 확인하나요?

서비스 및 환경 간의 메일 흐름을 검사합니다. 자세한 내용은 [커넥터의 유효성을 검사하여 메일 흐름 Microsoft 365 참조하세요.](/exchange/mail-flow-best-practices/test-mail-flow)

## <a name="step-4-allow-inbound-port-25-smtp-access"></a>4단계: 인바운드 포트 25 SMTP 액세스 허용

커넥터를 구성한 후 72시간 동안 기다렸다가 DNS 레코드 업데이트 전파를 허용합니다. 그런 후에 EOP 데이터 센터(구체적으로는 [Exchange Online Protection IP 주소](../../enterprise/urls-and-ip-address-ranges.md)에 나와 있는 IP 주소)에서 보내는 메일만 수락하도록 방화벽이나 메일 서버의 인바운드 포트 25 SMTP 트래픽을 제한합니다. 이렇게 하면 수신 가능한 인바운드 메시지 범위를 제한하여 온-프레미스 환경을 보호할 수 있습니다. 또한 메일 릴레이를 위한 연결이 허용된 IP 주소를 제어하는 설정이 메일 서버에 있는 경우에는 해당 설정도 업데이트합니다.

> [!TIP]
> 연결 제한 시간을 60초로 지정하여 SMTP 서버의 설정을 구성합니다. 이 설정은 대부분의 경우에 허용되므로 큰 첨부 파일로 보낸 메시지의 경우 어느 정도 지연될 수 있습니다.

## <a name="step-5-ensure-that-spam-is-routed-to-each-users-junk-email-folder"></a>5단계: 스팸이 각 사용자의 정크 메일 폴더로 라우팅되도록 합니다.

스팸(정크) 메일이 각 사용자의 정크 메일 폴더로 라우팅되도록 하려면 몇 가지 구성 단계를 수행해야 합니다. 단계는 Configure [standalone EOP to deliver spam to the Junk Email folder in hybrid environments](ensure-that-spam-is-routed-to-each-user-s-junk-email-folder.md)에 제공됩니다.

각 사용자의 정크 메일 폴더로 메시지를 이동하지 않을 경우 스팸 방지 정책을 편집하여 다른 작업을 선택할 수 있습니다. 자세한 내용은 [Office 365의 스팸 방지 정책 구성하기](configure-your-spam-filter-policies.md)를 참조하세요.

## <a name="step-6-use-the-microsoft-365-admin-center-to-point-your-mx-record-to-eop"></a>6단계: Microsoft 365 관리 센터를 사용하여 MX 레코드를 EOP로 설정

도메인 구성 단계에 따라 도메인의 MX 레코드를 업데이트하여 인바운드 전자 메일이 EOP를 통해 흐르게 합니다. 타사 필터링 서비스가 전자 메일을 EOP로 릴레이할 때와 달리 MX 레코드가 EOP를 직접 가리키도록 해야 합니다. 자세한 내용은 [Office 365용 DNS 레코드 만들기](../../admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider.md)를 참조하세요.

> [!NOTE]
> MX 레코드가 EOP 앞에 있는 다른 서버 또는 서비스를 설정해야 하는 경우 에서 커넥터에 대한 향상된 [필터링을 Exchange Online.](/Exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors)

### <a name="how-do-you-know-this-task-worked"></a>이 작업의 작동 여부는 어떻게 확인하나요?

이 시점은 제대로 구성된 아웃바운드 온-프레미스 커넥터에 대한 서비스 배달을 확인했으며 MX 레코드가 EOP를 가리키고 있는지 확인한 상태입니다. 이제 다음 추가 테스트를 실행하도록 선택하여 서비스에서 온-프레미스 환경으로 이메일이 전달되는지 확인할 수 있습니다.

- 서비스 및 환경 간의 메일 흐름을 검사합니다. 자세한 내용은 [커넥터의 유효성을 검사하여 메일 흐름 Microsoft 365 참조하세요.](/exchange/mail-flow-best-practices/test-mail-flow)

- 도메인이 서비스에 추가한 도메인과 일치하는 조직의 메일 받는 사람에게 웹 기반 전자 메일 계정에서 전자 메일 메시지를 보냅니다. Microsoft Outlook 또는 다른 전자 메일 클라이언트를 사용하여 온-프레미스 사서함으로의 메시지 배달을 확인합니다.

- 아웃바운드 전자 메일 테스트를 실행하려면 조직 사용자가 웹 기반 전자 메일 계정에 전자 메일을 보내도록 한 다음 메시지 수신을 확인하면 됩니다.

> [!TIP]
> 설정이 완료된 후 EOP에서 스팸 및 맬웨어를 제거하도록 추가 단계를 수행할 필요는 없습니다. EOP는 스팸과 맬웨어를 자동으로 제거합니다. 그러나 비즈니스 요구 사항에 따라 설정을 미세 조정할 수 있습니다. 자세한 내용은 [EOP의](anti-spam-and-anti-malware-protection.md) 스팸 방지 및 맬웨어 방지 보호 및 EOP의 피싱 방지 보호 [기능을 Microsoft 365.](anti-phishing-protection.md)
>
> 서비스가 실행되고 나면 [EOP를](best-practices-for-configuring-eop.md)설정한 후의 권장 설정 및 고려 사항을 설명하는 EOP 구성 모범 사례를 읽어보는 것이 좋습니다.