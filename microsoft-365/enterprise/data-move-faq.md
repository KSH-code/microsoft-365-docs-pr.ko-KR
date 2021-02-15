---
title: 데이터 이동 일반 FAQ
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 1f01bc6f-5d37-4d14-bdd3-9d94a1e23e14
f1.keywords:
- NOCSH
description: 핵심 데이터를 새 Office 365 데이터 센터 지역으로 이동하는 경우와 관련한 FAQ(질문과 대답)에 대한 답변을 찾아보실 수 있습니다.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: a7e59622e35604ebd9befbbe17a8a125ed15e101
ms.sourcegitcommit: c0cfb9b354db56fdd329aec2a89a9b2cf160c4b0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/03/2021
ms.locfileid: "50094658"
---
# <a name="data-move-general-faq"></a>데이터 이동 일반 FAQ

다음은 휴지의 핵심 고객 데이터를 새 데이터 센터 지역으로 이동하는 데 대한 일반적인 질문과 대답입니다.
  
## <a name="what-customers-are-eligible-to-request-a-move"></a>이동을 요청할 자격이 있는 고객은 무엇입니까?
  
새 데이터 센터 지역을 선택할 수 있는 국가를 선택한 기존 Microsoft 365 상용 고객은 이동을 요청할 수 있습니다. 이 프로그램은 Microsoft 365 테넌트에 할당된 적격 국가 코드가 있는 테넌트에 한해 해당 Microsoft 365 데이터 센터 지역으로 적합한 워크로드에 사용할 수 있는 핵심 고객 데이터를 마이그레이션할 수 있습니다. 국가 자격을 [](request-your-data-move.md) 확인하기 위해 데이터 이동 페이지를 요청하는 방법을 참조하세요.   

## <a name="how-do-we-define-core-customer-data"></a>핵심 고객 데이터를 정의하는 방법
 
핵심 고객 데이터는 다음 조건에 정의된 고객 데이터의 하위 [집합을 Microsoft Online Services 용어입니다.](https://aka.ms/ost) 
- Exchange Online 사서함 콘텐츠(전자 메일 본문, 일정 항목 및 전자 메일 첨부 파일 콘텐츠)
- SharePoint Online 사이트 콘텐츠 및 해당 사이트에 저장된 파일
- 비즈니스용 OneDrive에 업로드된 파일 

## <a name="what-is-in-scope-for-teams-migration"></a>Teams 마이그레이션의 범위는 무엇입니까?

Exchange Online, SharePoint Online 및 비즈니스용 OneDrive 외에도 Microsoft는 Teams 데이터를 로컬 데이터 센터로 마이그레이션합니다. 
- 비공개 메시지 및 채널 메시지를 포함한 Teams 채팅 메시지 
- 채팅에 사용되는 Teams 이미지입니다. 

Teams 파일은 SharePoint Online에 저장되고 Teams 채팅 파일은 비즈니스용 OneDrive에 저장됩니다. 음성 메일, 일정 및 연락처는 Exchange Online에 저장됩니다. 대부분의 경우 Exchange Online, SharePoint Online 및 비즈니스용 OneDrive는 고객이 이미 로컬 데이터 센터 지역의 고객이 사용하며 적합한 고객 국가에 대한 Microsoft 365 마이그레이션 프로그램의 일부입니다.

## <a name="at-what-point-is-my-migration-complete-so-that-my-tenants-core-customer-data-is-being-stored-at-rest-in-my-new-geo"></a>테넌트의 핵심 고객 데이터가 새 지리적 위치에 저장될 수 있도록 마이그레이션이 완료되는 시점은 무엇입니까?

Exchange Online과 SharePoint Online/비즈니스용 OneDrive 간의 공유 종속성으로 인해 두 서비스가 모두 마이그레이션될 때까지 마이그레이션이 완료된 것으로 간주할 수 없습니다. Exchange Online 및 SharePoint Online/비즈니스용 OneDrive는 종종 개별 시간 및 독립적으로 마이그레이션됩니다. 고객 테넌트 관리자는 각 서비스 마이그레이션이 완료되면 메시지 센터에서 확인을 받으며, 언제든 관리 센터에서 데이터 위치 카드를 확인하여 각 서비스의 휴지 상태의 핵심 고객 데이터를 확인할 수 있습니다.

## <a name="how-do-you-make-sure-my-customer-data-is-safe-during-the-move-and-that-i-wont-experience-downtime"></a>이동 중에 고객 데이터를 안전하게 보호하고 다운타임이 경험하지 않는지 어떻게 확인하나요?
  
데이터 이동은 최종 사용자에게 최소한의 영향을 미치는 백 엔드 서비스 작업입니다. 영향을 줄 수 있는 기능은 데이터 이동 중 및 이후에 [나열됩니다.](during-and-after-your-data-move.md) 당사는 가용성에 [Microsoft Online Services SLA(서비스](https://go.microsoft.com/fwlink/p/?LinkId=523897) 수준 계약)를 준수하기 때문에 고객이 이동 중에 준비하거나 모니터링할 필요가 없습니다. 
  
모든 Microsoft 365 서비스는 데이터 센터에서 동일한 버전을 실행하기 때문에 일관된 기능을 보장할 수 있습니다. 서비스는 프로세스 전반에 걸쳐 완벽하게 지원됩니다.
  
## <a name="what-is-the-impact-of-having-different-services-located-in-different-geos"></a>서로 다른 지역을 서로 다른 서비스에 두면 어떤 영향이 있나요?

일부 Microsoft 365 서비스는 일부 기존 고객 및 이동 프로세스의 중간에 있는 고객에 대해 서로 다른 지리적으로 위치할 수 있습니다. 서비스가 서로 독립적으로 실행됩니다. 이 경우 사용자 환경에는 아무 영향도 없습니다. 그러나 데이터 상주를 위해 Exchange Online과 SharePoint Online/비즈니스용 OneDrive를 동일한 데이터 센터 지역으로 마이그레이션해야 테넌트 마이그레이션이 완료된 것으로 간주할 수 있습니다.

 ## <a name="where-is-my-core-customer-data-located"></a>핵심 고객 데이터는 어디에 있나요?

고객 테넌트 관리자는 관리 센터에서 데이터 위치 카드를 보고, 특히 해당 테넌트에 대한 각 서비스의 휴지 위치에 있는 핵심 고객 데이터를 확인할 수 있습니다.  [또한 Microsoft 365](https://office.com/datamaps) 대화형 데이터 센터에서 데이터 센터 지역, 데이터 센터의 위치 및 Office 365 고객 데이터의 위치를 새 테넌트의 휴지 위치에 있는 현재 기본 핵심 고객 데이터에 대한 참조로 게시합니다. Microsoft 365 관리 센터의 조직 프로필 아래 데이터 위치 섹션을 통해 미사일 고객 데이터의 위치를 확인할 수 있습니다.  
 
## <a name="when-will-i-be-able-to-request-a-move"></a>언제 이동을 요청할 수 있나요?
  
데이터 센터 [지리적으로](request-your-data-move.md) 지원되는 기간에 대해 데이터 이동 페이지를 요청하는 방법을 참조하세요.
  
## <a name="how-can-i-request-to-be-moved"></a>이동을 요청하는 방법
  
적격 [고객에게는 Microsoft 365](https://admin.microsoft.com/)관리 센터에 페이지가 표시됩니다. 이동을 [요청하는](request-your-data-move.md) 방법에 대한 지침은 데이터 이동을 요청하는 방법을 참조하세요. 
  
## <a name="can-i-change-my-selection-after-requesting-a-move"></a>이동을 요청한 후 선택을 변경할 수 있나요?
  
요청을 제출한 후 프로세스에서 제거할 수 없습니다.
  
## <a name="what-happens-if-i-do-not-request-a-move-before-the-deadline"></a>마감일 전에 이동을 요청하지 않는 경우 어떻게 하나요?
  
열린 등록 기간 이후에는 마이그레이션 요청을 수락할 수 없습니다.

## <a name="what-if-i-want-to-move-my-data-in-order-to-get-better-network-performance"></a>네트워크 성능을 향상하기 위해 데이터를 이동하려는 경우 어떻게 하나요?
  
Microsoft 365 데이터 센터와 물리적으로의 근접성은 더 나은 네트워킹 성능을 보장하지는 않습니다. 최종 사용자와 Microsoft 365 서비스 간의 네트워크 성능에 영향을 주는 요인과 구성 요소는 여러 가지가 있습니다. 이 조정 및 성능 조정에 대한 자세한 내용은 [Microsoft 365의](network-planning-and-performance.md)네트워크 계획 및 성능 조정을 참조하세요.
  
 ## <a name="do-all-the-services-move-their-data-on-the-same-day"></a>모든 서비스가 같은 날에 데이터를 이동하나요?
 
각 서비스는 독립적으로 이동하며 데이터를 다른 시간으로 이동할 수 있습니다.
  
 ## <a name="can-i-choose-when-i-want-my-data-to-be-moved"></a>데이터를 이동할 때 선택할 수 있나요?
 
Microsoft는 이동의 구체적 날짜나 기간을 알려드릴 수 없습니다.
  
 ## <a name="can-you-share-when-my-data-will-be-moved"></a>데이터를 이동할 때 공유할 수 있나요?
  
데이터 이동은 최종 사용자에게 최소한의 영향을 미치는 백 엔드 작업입니다. 전체적으로 운영되고 자동화된 환경 내에서 데이터 이동을 수행하는 데 필요한 복잡성, 정밀도 및 규모로 인해 테넌트 또는 다른 단일 테넌트에 대해 데이터 이동이 완료될 것으로 예상되는 경우 공유를 금지합니다. 고객은 데이터 이동이 완료되었을 때 메시지 센터에서 관련 서비스별로 1번의 확인을 받게 됩니다. 
  
 ## <a name="what-happens-if-users-access-services-while-the-data-is-being-moved"></a>데이터가 이동되는 동안 사용자가 서비스에 액세스하면 어떻게 되나요?

각 [서비스에](during-and-after-your-data-move.md) 대한 데이터 이동의 일부 동안 제한될 수 있는 전체 기능 목록은 데이터 이동 중 및 이후를 참조하세요. 
  
 ## <a name="how-do-i-know-the-move-is-complete"></a>이동이 완료된 것을 어떻게 알 수 있나요?
  
Microsoft 365 메시지 센터에서 각 서비스의 데이터 이동이 완료된지 확인을 시청합니다. 각 서비스의 데이터가 이동하면 완료 알림이 게시됩니다. 그러면 Exchange Online, SharePoint Online 및 비즈니스용 Skype Online에 대해 각각 하나씩 세 개의 완료 알림이 전송됩니다. Microsoft 365 관리 센터의 조직 프로필 아래 데이터 위치 섹션을 통해 미사일 고객 데이터의 위치를 확인할 수도 있습니다.  
  
## <a name="i-am-a-microsoft-365-customer-in-one-of-the-new-datacenter-geos-but-when-i-signed-up-i-selected-a-different-country-how-can-i-be-moved-to-the-new-datacenter-geo"></a>새 데이터 센터 지역 중 하나에 있는 Microsoft 365 고객이지만 등록할 때 다른 국가를 선택했습니다. 새 데이터 센터 지역으로 이동하는 방법

테넌트와 연결된 등록 국가는 변경할 수 없습니다. 대신 새 구독을 사용하여 새 Microsoft 365 테넌트를 만들고 사용자와 데이터를 새 테넌트로 수동으로 이동해야 합니다.
  
## <a name="what-happens-if-we-are-in-process-of-email-data-migration-to-microsoft-365-during-the-exchange-online-move"></a>Exchange Online을 이동하는 동안 Microsoft 365로 전자 메일 데이터 마이그레이션을 진행하는 경우 어떻게 하나요?

이 시나리오는 매우 일반적인 시나리오로, 완전히 지원됩니다.  데이터 센터 지역 간의 클라우드 마이그레이션은 클라우드 사서함 마이그레이션을 방해하지 않습니다.
  
 ## <a name="can-i-pilot-some-users"></a>일부 사용자를 파일럿할 수 있나요?
  
별도의 평가판 테넌트를 만들어 연결을 테스트할 수 있지만 평가판 테넌트는 기존 테넌트와 어떤 방식으로도 결합할 수 없습니다.

## <a name="i-dont-want-to-wait-for-microsoft-to-move-my-data-can-i-just-create-a-new-tenant-and-move-myself"></a>Microsoft에서 내 데이터를 이동할 때까지 기다리지 않습니다. 새 테넌트만 만들어서 바로 이동할 수 있나요?
  
그렇지만 Microsoft가 데이터 이동을 수행하는 것처럼 프로세스가 원활하지 않을 수 있습니다.
  
새 데이터 센터 지역을 사용할 수 있는 후에 새 테넌트를 만드는 경우 새 테넌트가 새 지리적으로 호스트됩니다. 이 새 테넌트는 이전 테넌트와 완전히 별도이며, 모든 사용자 사서함, 콘텐츠 사이트, 도메인 이름 및 다른 데이터를 이동하는 일은 사용자가 처리해야 합니다. 한 테넌트에서 다른 테넌트로 테넌트 이름을 이동할 수는 없습니다. Microsoft는 사용자의 모든 설정, 데이터 및 구독의 이동을 관리하므로 Microsoft에서 제공하는 이동 프로그램을 기다리는 것이 좋습니다.
  
## <a name="my-customer-data-has-already-been-moved-to-a-new-datacenter-geo-can-i-move-back"></a>내 고객 데이터가 이미 새 데이터 센터 지역으로 이동되어 있습니다. 뒤로 이동할 수 있나요?
 
아니요. 이 경우 가능하지 않습니다. 새 지리적 데이터 센터로 이동한 고객은 다시 이동할 수 없습니다. 모든 지역 고객은 이전과 동일한 서비스 품질, 성능 및 보안 제어를 경험하게 됩니다. [Microsoft 365 Multi Geo는](https://aka.ms/multi-geo) 일부 고객이 추가 기능으로 사용할 수 있으며, 단일 테넌트가 여러 위성 지역을 만들고 데이터 레지던스 약정을 사용하여 사용자 데이터를 해당 지역으로 이동할 수 있도록 합니다.
  
## <a name="will-microsoft-365-tenants-hosted-in-the-new-datacenters-be-available-to-users-outside-of-the-country"></a>새 데이터 센터에 호스트된 Microsoft 365 테넌트가 국가 외부의 사용자가 사용할 수 있나요?
  
예. Microsoft는 2,700개가 넘는 ISP(인터넷 서비스 공급자)와 피어링 계약을 체결하여 전 세계 35개 국가에서 130개 이상의 위치에서 공용 인터넷 연결을 통해 대규모 글로벌 네트워크를 유지 관리합니다. 사용자는 인터넷에 있는 어디에서든지 데이터 센터에 액세스할 수 있습니다.

## <a name="my-tenant-has-configured-the-multi-geo-add-on-can-i-still-enroll-in-my-tenant-in-the-microsoft-365-move-program-to-change-my-default-geo-and-move-any-user-not-in-a-satellite-region-to-the-new-default-geo"></a>내 테넌트가 Multi Geo 추가 [기능을 구성한 경우](https://aka.ms/multi-geo) Microsoft 365 이동 프로그램에 테넌트에 등록하여 기본 지역을 변경하고 위성 지역에 있지 않은 사용자를 새 기본 지역으로 이동할 수 있나요?

예, 테넌트는 등록할 수 있지만 Multi-Geo를 구성한 고객에 대해 테넌트 수준 이동이 완전히 지원되지 않는 경우 중요한 고려 사항이 있습니다.

SharePoint Online 및 비즈니스용 OneDrive는 이 프로그램을 통해 테넌트 수준에서 새 데이터 센터 지역으로 마이그레이션할 수 없습니다. 고객 관리자는 Multi-Geo를 사용하여 사용 가능한 모든 지역으로 이동하도록 비즈니스용 OneDrive 공유를 구성할 수 있지만, 테넌트에 대해 Multi-Geo가 구성되면 테넌트의 기본 위치를 변경할 수 없습니다.

마이그레이션에 옵트인(opt in)하는 고객의 경우 현재 기본 지리적 위치의 모든 Exchange Online 사서함을 새 로컬 데이터 센터 지역으로 이동하고 기본 Exchange Online 지역을 업데이트합니다. Multi Geo 위성 지역에 구성된 EXO 사서함은 사용자가 의도한 바에 따라 위성 지역 데이터 유지를 계속 사용하도록 이동하지 않습니다. 

## <a name="related-topics"></a>관련 항목

[핵심 데이터를 새 Microsoft 365 데이터 센터 지역으로 이동](moving-data-to-new-datacenter-geos.md)

[데이터 이동을 요청하는 방법](request-your-data-move.md)

[Microsoft 365 Multi Geo](https://aka.ms/multi-geo)

[Microsoft 365 대화형 데이터 센터 맵](https://office.com/datamaps)

[Microsoft 365 지원](https://go.microsoft.com/fwlink/p/?LinkID=522459)

[새 데이터 센터 지역을 Microsoft Dynamics CRM Online](https://go.microsoft.com/fwlink/p/?Linkid=615924)
  
[지역별로 Azure 서비스](https://azure.microsoft.com/regions/)
