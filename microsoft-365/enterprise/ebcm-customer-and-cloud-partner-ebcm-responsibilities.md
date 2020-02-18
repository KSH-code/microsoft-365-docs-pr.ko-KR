---
title: 고객 및 클라우드 파트너 엔터프라이즈 비즈니스 연속성 책임
author: chrfox
f1.keywords:
- NOCSH
ms.author: chrfox
manager: laurawi
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
ms.custom: ''
description: 비즈니스 연속성 계획을 준비할 수 있도록 서비스 인시던트 발생 시 Microsoft가 수행하는 작업을 이해합니다.
ms.openlocfilehash: 3d4a1d6c3a69be4cb3051125d5527b1f0b25b375
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42067679"
---
# <a name="enterprise-business-continuity-management-customer-and-cloud-partner-responsibilities"></a>엔터프라이즈 비즈니스 연속성 관리 고객 및 클라우드 파트너 책임

사용자에게 Microsoft 365 클라우드 서비스를 제공하는 것은 조직과 Microsoft 사이의 파트너 관계입니다. Microsoft의 임무는 서비스를 제공하는 것이며 여러분은 클라이언트의 끝점 연결, ID 및 액세스 관리, 서비스 사용 현황 관리의 책임이 있습니다. 하지만 ID 및 디렉터리 인프라와 같은 책임을 공유하기도 합니다. 이 문서에는 서비스 인시던트 발생 시 기업의 기능을 유지하는 데 도움이 되는 몇 가지 중요한 항목에 대해 안내되어 있습니다. 또한 서비스 인시던트가 발생했을 때 Microsoft가 어떻게 도움을 드리는지도 설명되어 있습니다.

## <a name="transparency-during-service-incidents"></a>서비스 인시던트 발생 시의 투명성

Microsoft는 신뢰할 수 있는 파트너로서, 서비스 인시던트가 발생했을 때 복원력이 뛰어난 클라우드 서비스를 구축하고 구조적 절차를 따라 해결합니다. 서비스 인시던트가 발생하면 Microsoft는 고객에게 **시기 적절하고 y** **대상이 지정된** **정확한 커뮤니케이션이 **필요한 상황이라는 것을 알게 됩니다.

## <a name="timely"></a>시의적절
Microsoft는 Microsoft 365 관리 포털에서 테넌트 관련 서비스 상태 대시보드를 업데이트하여 Microsoft 365 관리자에게 알립니다. 서비스 인시던트 업데이트는 일반적으로 시간별 케이던스에서 제공됩니다. 다른 케이던스가 필요한 경우 SHD 커뮤니케이션 게시물 변경에 대해 계속 알립니다.

## <a name="targeted"></a>대상
대개 모니터링 시스템에서 문제가 감지되었을 때, 이에 영향을 받는 개인 고객부터 지역 혹은 그 이상까지 고객 기반을 식별하고 고객들에게 필요한 커뮤니케이션을 전달합니다. 이는 알아야 하는 비즈니스 관련 사항을 파악하는 데 도움이 됩니다. 또한 소음 알림은 업무에 영향을 주지 않기 때문에 기업을 방해하지 않습니다. 예를 들어 특정 사서함 데이터베이스가 영향을 받는 경우, 어떤 고객의 사용자가 인프라에 영향을 받았는지 정확히 식별하고 고객과의 커뮤니케이션을 살핍니다. 인시던트의 영향 범위가 명확하지 않은 경우에는 커뮤니케이션 영역을 영향을 받을 수 있는 고객까지 확장합니다.

## <a name="highly-available"></a>고가용성
Microsoft는 고객이 사용할 수 있는 서비스 커뮤니케이션 상태 채널을 여러 개 갖고 있습니다.

- 관리 센터에서 관리 센터 또는 서비스 상태 대시보드를 사용할 수 없는 경우에는 [백업 사이트](https://status.office365.com/)를 사용하여 서비스 상태를 모니터링할 수 있습니다.
- Twitter 계정[@MSFT365Status](https://twitter.com/msft365status?lang=en)에는 영향 보고서에 응답하고 SHD 영향 이벤트에 대한 업데이트를 게시합니다.
- Microsoft 365 테넌트 관리자용 관리 앱을 사용하면 이동 중에도 조직의 Microsoft 365 서비스 상태에 연결할 수 있습니다. 테넌트 관리자는 모바일 디바이스에서 서비스 상태 정보 및 유지 관리 상태 업데이트를 볼 수 있습니다. 자세한 내용은 [관리자 앱 FAQ](https://docs.microsoft.com/office365/admin/admin-overview/admin-mobile-app?view=o365-worldwide)를 참조하세요.
- [Microsoft 365 Service Communications API](https://docs.microsoft.com/office365/servicedescriptions/office-365-platform-service-description/service-health-and-continuity#office-365-service-communications-api)를 사용하면 서비스 커뮤니케이션에 쉽게 액세스하여 환경을 더욱 쉽게 모니터할 수 있습니다. API에 연결하고 실시간으로 서비스 상태 데이터를 수신할 수 있으며 내부 대시보드에 정보를 게시하여 엔터프라이즈 사용자에게 인시던트 내용을 알릴 수 있습니다. 내부적으로 정보를 배포하면 사고로 인한 중단 동안 고객 지원 트래픽을 줄일 수 있습니다.
- 주요 사고의 경우 Microsoft는 관리 센터 내에서 SHD에 사후 인시던트 검토(PIR)를 게시합니다. PIRs는 중단의 성격을 이해하는 데 도움이 되는 주요 인시던트 정보를 포함합니다. 일반적으로 다음의 섹션이 포함되어 있습니다.
    - 사용자 영향
    - 영향 범위
    - 인시던트 시작-종료 날짜 및 시간
    - 근본 원인
    - 수행한 작업
    - 다음 단계
- Microsoft 365 메시지 센터에서 예정된 변경 내용, 새로운 기능, 계획된 유지 관리 확인과 같은 보조 커뮤니케이션을 사용할 수 있습니다.
- 자세한 내용은 [서비스 상태 및 연속성 가이드](https://docs.microsoft.com/office365/servicedescriptions/office-365-platform-service-description/service-health-and-continuity)를 참조하여 다양한 통신 채널 및 서비스 상태를 모니터링하는 방법에 대해 자세히 알아보세요.
 
Microsoft 365 온라인 서비스에 대한 액세스를 제공하는 것이 조직과 Microsoft 사이의 파트너 관계입니다. 다음 차트는 서비스 인시던트 및 정기 운영 중 책임의 균형이 Microsoft와 고객 사이에서 어떻게 유지되는지를 요약해서 보여줍니다.

![고객 및 Microsoft 책임의 균형](../media/ebcm/responsibilities.png)

## <a name="your-environment---service-continuity"></a>사용자 환경-서비스 연속성
연속성 계획을 고려할 때, 조직에 영향을 줄 수 있는 이벤트와 그 이벤트의 전체적인 커뮤니케이션 능력에 대해 유념해야 합니다. 비즈니스에 높은 수준에서 영향을 줄 수 있는 세 가지 요소가 있습니다.

### <a name="people"></a>사람
자연재해나 유행병과 같이 직원에게 영향을 주는 상황을 고려합니다. 인력 분포가 넓을 경우 광범위하게 영향을 주지 않을 수 있기 때문에 흔히 간과하는 경우가 많습니다. 그러나 많은 직원이 오프라인 상태라면 비즈니스를 계속 운영할 수 있을까요? 어떻게 해결할 수 있을까요?

### <a name="location"></a>위치
많은 조직에서 엔터프라이즈 시스템 및 클라우드 서비스 연결을 위해 직원들에게 특정한 물리적 장소나 네트워크에 위치하도록 요구합니다.  
Microsoft는 [네트워크 연결 원칙](https://docs.microsoft.com/office365/enterprise/office-365-network-connectivity-principles)을 게시하여 기업이 클라우드 리소스에 대한 네트워크 연결 설정 모범 사례를 따르도록 합니다. 최적화 예시는 VPN 터널을 통하지 않고 사용자 네트워크에 직접적으로 연결하기 위한 분할 터널 VPN 실행을 포함합니다.  이러한 연결 원칙은 짧은 연결 시간을 유지하는 데 중요하지만, 서비스 복원에는 일반적인 공동 작업을 위해 기업 리소스에 연결하는 다른 방법이 필요합니다.

### <a name="systems"></a>시스템
많은 공동 작업 솔루션이 회사 광역 네트워크(WAN)와 같은 시스템에 의존합니다. 해당 시스템을 사용할 수 없는 경우 조직에서 어떻게 대처하나요?
이 그래픽은 둘 이상의 영역에 영향을 줄 수 있는 문제를 나타냅니다. 함께 제공되는 표에서는 고려해야 할 예를 제공합니다.

![벤 다이어그램](../media/ebcm/venn-diagram.png)

연속성 계획은 각 영역을 고려해야 합니다. 예를 들어, 사용자가 회사 네트워크에 연결해야 하는데 눈보라가 발생한 경우 어떻게 사용자가 키 리소스에 접속할 수 있나요? 눈 때문에 출근할 수 없거나 서비스 엔지니어들이 회사 네트워크에 연결해야 하는 경우, 집에서 회사 노트북을 사용할 수 있도록 권한을 주는 정책이 있나요?
