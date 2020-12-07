---
title: Microsoft 365의 Exchange Online 모니터링
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 12/03/2020
audience: Admin
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Priority
search.appverid:
- MET150
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
f1.keywords:
- NOCSH
description: Microsoft 365의 메일 인시던트 또는 권고에 대한 자세한 내용은 Exchange Online 모니터링을 사용하세요.
ms.openlocfilehash: 53dc7f990f57fd8d4da68bd424947676cbf0e85d
ms.sourcegitcommit: d81c7cea85af6ad5fef81d3c930514a51464368c
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/04/2020
ms.locfileid: "49572878"
---
# <a name="exchange-online-monitoring-for-microsoft-365"></a>Microsoft 365의 Exchange Online 모니터링

Microsoft 365 관리 센터에서 Exchange Online 모니터링을 사용하여 조직의 Microsoft 365 구독에 대한 Exchange 서비스의 상태를 모니터링할 수 있습니다. Exchange Online 모니터링에서는 다음 범주에서 수집되는 인시던트와 권고에 대한 정보를 제공합니다.

- **인프라**: Microsoft에서 정기 업데이트와 문제 해결을 위해 보유하고 있는 Microsoft 365 인프라에서 문제가 발견되었습니다. 예를 들어, Exchange 또는 기타 Microsoft 365 클라우드 인프라에 발생한 문제로 인해 Exchange Online에 액세스할 수 없습니다.
- **타사 인프라**: 조직이 하위 항목을 보유하는 타사 인프라에서 문제가 발견되었고 해결하려면 조직의 조치가 필요합니다. 예를 들어, 사용자 인증 거래는 사용자가 Exchange Online에 연결하는 것을 차단하는 타사 STS(보안 토큰 서비스) 공급자에 의해 제한을 받고 있습니다.
- **고객 인프라**: 조직 인프라에서 문제가 발견되었고 해결하려면 조직의 조치가 필요합니다. 예를 들어, 만료된 인증서로 인해 사용자가 조직에서 호스트하는 STS 공급자로부터 인증 토큰을 받을 수 없으므로 Exchange Online에 액세스할 수 없습니다.

다음은 Microsoft 365 관리 센터에서 **서비스 상태** 페이지에 대한 예이며, **상태 > 서비스 상태** 에서 사용할 수 있습니다.

![Microsoft 365 관리 센터의 서비스 상태 페이지](../media/microsoft-365-exchange-monitoring/service-health-dashboard-example.png)

**상태** 열의 값은 서비스가 정상인지를 나타내고 Microsoft에서 유지 관리하는 클라우드 서비스를 기반으로 권고나 인시던트를 알려줍니다. 

**조직 및 타사 문제점** 열의 값은 조직의 인프라 또는 타사 소프트웨어에서 Exchange Online을 사용하여 사용자의 서비스 상태 환경에 영향을 줍니다. 권고나 인시던트를 해결하려면 *사용자의 조치* 가 필요합니다.

다음은 Microsoft 365 관리 센터에서 **Exchange Online** 모니터링 페이지에 대한 예이며, **상태 > 서비스 상태 > Exchange Online** 에서 사용할 수 있습니다.

![Microsoft 365 관리 센터의 Exchange Online 모니터링 페이지](../media/microsoft-365-exchange-monitoring/exhange-monitoring-example.png)

**Exchange Online** 모니터링 페이지를 사용하여 Exchange Online 서비스가 정상인지 여부를 확인하고 연결된 인시던트나 권고 사항이 있는지 확인할 수 있습니다. Exchange Online 모니터링을 사용하여 특정 메일 시나리오에 대한 서비스 상태를 확인하고 거의 실시간 신호를 보고 시나리오의 영향을 확인할 수 있습니다. 

## <a name="requirements"></a>요구 사항

다음 요구 사항을 충족하는 고객은 해당 미리 보기를 사용할 수 있습니다. 

- 조직에는 Office 365 E3, Microsoft 365 E3, Office 365 E5, Microsoft 365 E5와 같은 하나 이상의 제품에 10,000개 이상의 라이선스 수가 있어야 합니다. 

  예를 들어 조직에는 적격 제품의 총 11,500개의 라이센스에 대해 3,000개의 Office 365 E3 라이선스 및 8,500개의 Microsoft 365 E5 라이선스가 있을 수 있습니다.

- 조직에는 매월 최소 50명의 활성 Exchange Online 사용자가 있어야 합니다.

Exchange Online 모니터링을 사용하여 메일 읽기 활동을 기반으로 다음 메일 클라이언트의 상태를 볼 수 있습니다.

- Outlook 데스크톱
- 웹용 Outlook
- IOS 및 Android의 기본 메일 클라이언트 
- IOS 및 Android의 Outlook Mobile 앱 
- Outlook Mac 클라이언트

해당 클라이언트의 경우, 대시보드에서 인시던트와 권고 수와 함께, 메일을 읽는 사용자를 기반으로 지난 30분 동안의 활성 사용자 수를 볼 수 있습니다. 지난 주에 대해 동일한 간격으로 이 데이터를 비교하여 문제가 있는지 확인합니다. 

>[!Note]
> 활성 사용자 수는 단일 활동(예: 사용자가 메일을 읽는 경우)으로 측정됩니다. 지난 30분 동안의 활동만 설명합니다.
>

다음과 같은 경우에도 Exchange Online 상태를 모니터링할 수 있습니다.

- **메일 흐름**: 메시지가 Microsoft 365 네트워크에 연결된 후 지연 없이 사서함에 성공적으로 전달되는 메시지 수입니다. 
- **기본 인증 및 최신 인증**: Exchange Online 서비스에서 성공적으로 유효성 검사된 사용자 수입니다.

![메일 전달에 대한 Exchange 상태 모니터링의 예](../media/microsoft-365-exchange-monitoring/exhange-monitoring-scenario-example.png)

모든 관련 시나리오의 경우, 주요 숫자는 주 대시보드의 마지막 30분에 대한 것입니다. 각 시나리오에 대한 자세한 보기에서는 이전 주와 비교한 30분 집계를 사용하여 7일에 대한 거의 실시간 추세를 보여 줍니다. 

## <a name="send-us-feedback"></a>의견 보내기

다음과 같은 두 가지 방법으로 의견을 제공할 수 있습니다.

- Microsoft 365 관리 센터의 모든 페이지에서 **의견 보내기** 옵션을 사용할 수 있습니다.
- 특정 인시던트나 권고에 **이 게시물이 유용한가요?** 링크를 사용하여 의견 제출

![“이 게시물이 유용한가요?” 특정 인시던트나 권고에 대한 링크](../media/microsoft-365-exchange-monitoring/exhange-monitoring-example-incident-feedback.png)

## <a name="frequently-asked-questions"></a>자주 묻는 질문

#### <a name="1-why-dont-i-see-exchange-online-monitoring-under-health-in-the-microsoft-365-admin-center"></a>1. Microsoft 365 관리 센터의 상태 아래에 "Exchange Online 모니터링"이 표시되지 않는 이유는 무엇인가요? 

먼저 Microsoft 365 관리 센터의 **홈** 페이지에서 새 관리 센터를 사용하도록 설정했는지 확인합니다. 

그런 후, 다음 요구 사항을 모두 충족하는지 확인합니다. 

- 조직에는 Office 365 E3, Microsoft 365 E3, Office 365 E5, Microsoft 365 E5와 같은 하나 이상의 제품에 10,000개 이상의 라이선스 수가 있어야 합니다. 
- 조직에는 매월 최소 50명의 활성 Exchange Online 사용자가 있어야 합니다.

조직의 라이선스 수가 1만 명의 사용자 아래로 떨어지고 월간 활성 사용자가 50명 아래로 감소하는 경우, 해당 요구 사항이 충족될 때까지 Exchange Online 모니터링을 사용할 수 없습니다.

#### <a name="2-the-active-user-count-in-the-dashboard-for-each-client-appears-to-be-low-we-have-a-lot-of-active-licenses-assigned-to-users-what-does-this-mean"></a>2. 각 클라이언트에 대한 대시보드의 활성 사용자 수가 낮은 것으로 표시됩니다. 사용자에게 많은 활성 라이선스가 할당되어 있습니다. 시나리오 

모니터링에 표시되는 활성 사용자 수는 기능에서 호출한 활동을 수행한 30분 창을 기반으로 합니다. 이 수치와 사용량 수치를 혼동해서는 안 됩니다. 사용량 수치를 보려면 Microsoft 365 관리 센터에서 활동 보고서 **(보고서 > 사용**)를 사용합니다.

#### <a name="3-will-there-be-other-monitoring-scenarios-for-other-services-such-as-teams-and-sharepoint"></a>3. Teams 및 SharePoint와 같은 기타 서비스에 대한 다른 모니터링 시나리오가 있나요? 

Microsoft에서 Microsoft 365 관리 센터의 서비스 상태 대시보드 내부에서 이 환경을 바로 통합했습니다. 이를 통해 Microsoft에서 다른 서비스에 대한 모니터링 시나리오를 확장할 수 있는 기회를 갖게 됩니다. 이 기능은 공유할 뉴스가 있을 경우 발표될 예정입니다. 

#### <a name="4-what-is-the-plan-for-general-availability-of-this-experience"></a>4 .이 환경의 출시 계획은 무엇인가요? 

Microsoft에서 Microsoft 365 관리 센터의 **서비스 상태** 대시보드 내부에서 Exchange Online 모니터링을 바로 통합했습니다. 

새로운 통합 환경에서 Microsoft의 계획은 사용자 의견을 수집하고 출시 계획을 정의하는 것입니다.

#### <a name="5-is-this-a-free-included-or-paid-extra-feature"></a>5. 이 기능은 무료(포함)인가요? 무료(추가)인가요? 

이 기능은 공개 미리 보기 상태이며 질문 1에 있는 요구 사항을 충족하는 고객만 사용할 수 있습니다.

<!--
>[!Note]
>INTERNAL: That decision is pending
>
--> 

#### <a name="6-how-do-i-provide-feedback"></a>6. 사용자 의견을 제공하려면 어떻게 하나요? 

일반적인 사용자 의견을 보려면 **Exchange Online** 모니터링 페이지의 오른쪽 아래 모서리에 있는 **의견 보내기** 아이콘을 사용하세요. 

인시던트나 권고에 대한 의견을 보려면 **이 게시물이 유용한가요?** 링크를 사용하세요.

#### <a name="7-where-is-the-data-instrumented-for-the-scenarios-that-show-activity-trends"></a>7. 활동 경향을 보여주는 시나리오의 데이터는 어디에서 측정됩니까?

데이터는 Exchange Online 서비스에서 계측됩니다. 요청이 Exchange Online에 도달하기 전에 오류가 발생하거나 Exchange Online에서 오류가 발생한 경우 작업 신호가 감소합니다.

