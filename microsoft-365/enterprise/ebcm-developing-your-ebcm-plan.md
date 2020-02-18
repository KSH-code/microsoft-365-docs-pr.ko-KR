---
title: 엔터프라이즈 비즈니스 연속성 관리 계획에 대한 고려 사항
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
description: 클라우드 인식 비즈니스 연속성 계획을 개발할 때 고려해야 할 사항.
ms.openlocfilehash: f8518a96461d33093b9d736f890f6166dc6b3c97
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/29/2020
ms.locfileid: "41601095"
---
# <a name="developing-your-continuity-plan"></a>연속성 계획 개발

이 항목에서는 Microsoft 365 종속성을 고려한 비즈니스 연속성 계획 개발에 대한 지침을 제공합니다. 여기에서 비즈니스 기능을 분석하고 Microsoft 365 서비스에 종속되는 기능을 식별하는 방법을 권장합니다. 서비스 장애가 발생할 수 있고 이러한 가능성에 대비하면서 이 분석을 수행합니다.

광범위하게 비즈니스 연속성 계획에는 4가지 측면인 평가, 계획, 기능 유효성 검사, 통신 및 조정이 포함됩니다.

## <a name="assessment"></a>평가
먼저 조직의 비즈니스 기능과 해당 기능을 지원하는 서비스 및 프로세스를 확인해야 합니다. 여기에는 각 비즈니스 기능의 중요도에 따라 순위를 지정하고 각 비즈니스 기능에 종속된 프로세스와 서비스를 식별하는 비즈니스 영향 분석 완료가 포함됩니다. 다음은 자체 평가를 시작하는 데 도움이 되는 샘플 표입니다.

**샘플 비즈니스 영향 평가 (BIA)**

다음은 `name of the service, system, process, or function`에 대한 BIA 문서입니다.

|BIA 필드|설명|
|---------|---------|
|BIA 형식|`is it a business process or technology, service or system?`|
|BIA 이름|`name of the service/system/function/process`|
|서비스 설명|`give a full description of the service, process, or function`|
|엔터프라이즈 기능|`some examples: customer services; legal; marketing; risk management, security, sales, information technology, production, manufacturing`|
|회계 연도|`the current fiscal year, re-evaluate these on a regular basis`|
|중요도|`develop your own classifications, but here are some examples: mission critical, important, deferrable`|
|사업부|`name of the business unit that owns this business function`|
|프로세스 (서비스, 특징)|`the name of the process, service, or feature`|
|비즈니스 그룹 선임 리더|`the name and contact information of the senior leader of the business group that owns this business process`|
|기술에 설정된 **내부** SLA 또는 OLA가 있나요?|`please explain in as much detail as possible`|
|기술에 설정된 **외부** SLA 또는 OLA가 있나요?|`please explain in as much detail as possible`|
|이 기술에는 특정 프로세스 SLA를 추진하는 알려진 경영진 요구사항이 있나요? 그렇다면 자세히 설명해주세요.|`details here`|
|이 서비스와 연결된 데이터가 손실되거나 손상되면 주요 이벤트가 발생하나요? 그렇다면 자세히 설명해주세요.|`details here`|
|서비스의 주요 기능 중 일부 또는 전부에 대한 해결 방법이나 대안이 있습니까? 그렇다면 자세히 설명해주세요.|`details here`|
|서비스에서 PII (개인 식별 정보)와 같은 고객 데이터를 처리, 저장하거나 전송하나요? 그렇다면 자세히 설명해주세요.|`details here`|
|BIA 상태|`develop your own status classification, here are some examples: planned, started, in-progress, complete, on-hold, expired`|
|완료 날짜|`the date this BIA was completed`|
|BIA 촉진자|`name of the person or group who is responsible for developing and maintaining this BIA`|
|BIA 승인|`name of the person or group who is the executive sponsor of this BIA and who has responsibility for approving it.`|
|참가자|`optional list of the people who helped develop this BIA and their contact information`|
|BIA 승인 위치|`indicate where the executive approval is located, or attach proof to this document`|

## <a name="planning"></a>계획

그런 다음 비즈니스 프로세스를 확인하여 연속되는 종속성 관계가 존재하는 위치를 확인합니다. 결과를 바탕으로 복원 전략 및 전략을 지원하는 표준 운영 절차의 우선 순위를 정하고 구성합니다.

[Microsoft 서비스 맵](https://docs.microsoft.com/azure/azure-monitor/insights/service-map)을 사용하여 이 매핑에 대해 도움을 받을 수 있습니다. Microsoft 서비스 맵은 Windows 및 Linux 시스템에서 응용 프로그램 구성 요소를 자동으로 검색하고, 모든 TCP 종속성을 매핑하여 연결을 식별하고, 앱이 종속된 원격 타사 시스템을 확인합니다. Active Directory와 같이 일반적으로 어두운 네트워크 영역에도 종속성을 매핑합니다.

다음 샘플 종속성 분석 (DA)에서 시작하세요. 종속성 분석 (DA)에서 프로세스 종속성을 식별하고 검사합니다. 사용자, 공급자, 고객, 파트너십 및 시설을 포함하고 있는지 확인합니다. 이 분석의 데이터는 프로세스의 복구 요구 사항과 종속성을 지원하는 복구 기능 간의 차이를 식별하는 데 사용됩니다.


|필드|설명|
|---------|---------|
|프로세스 유형|         |
|촉진자|         |
|완료한 사람|         |
|완료 날짜|         |
|참가자|         |
  
## <a name="capability-validation"></a>기능 유효성 검사

비즈니스 프로세스를 인벤토리에 포함하고 다른 프로세스 및 기술에 대한 관계를 매핑한 후 모든 프로세스에 대한 유효성 검사 시나리오를 작성해야 합니다. 기본적으로 비즈니스 프로세스 연속성 계획의 유효성을 검사하는 방법에 대해 알아보세요. 일부는 다른 것보다 더 중요하므로, 그에 대해 우선 순위를 지정하는 것이 좋습니다.
계획이 수립되면 사고 대응 및 연속성 조치에 대한 직원 교육을 정기적으로 실시하는 것이 중요합니다. 사후 검토를 사용하여 각 유효성 검사 또는 테스트의 학습을 통합하여 복원력 전략을 강화해야 합니다.

## <a name="incident-coordination-and-communication"></a>사고 조정 및 통신

서비스 문제가 발생하면 정상적인 통신 채널이 영향을 받거나 성능이 저하될 수 있으므로 사고 중에 조직이 연결 상태를 유지할 수 있도록 대안을 미리 준비해야 합니다. 보안 및 규정 준수를 위해 통신 채널을 설정하고, 사용자는 중단 전에 사용에 대한 교육을 받는 것이 중요합니다. 문제가 발생한 상태에서 사용자에게 임시적이고 잘 알지 못하는 솔루션을 찾기보다는 알려진 상태에서 다른 알려진 상태로 장애 조치를 하는 것이 훨씬 더 좋습니다.

Microsoft의 각 서비스 팀은 일반적인 통신 채널을 사용할 수 없을 때 이를 조정하는 데 도움이 되는 내부 대체 통신 채널을 마련했습니다. 여기에는 백업 전화 통신 및 오디오 회의 솔루션, Yammer 그룹, Teams 그룹, 내부 서비스 상태 대시보드 및 내부 인시던트 관리 소프트웨어가 포함 됩니다.

비즈니스 영향 분석 및 종속성 분석을 수행하는 동안 주요 프로세스와 해당 프로세스에 종속 되는 기술 또는 서비스를 매핑하게 됩니다. 이 계획 단계에서 의사 소통에 특별한 주의를 기울이고 대안을 생각해야 합니다. 다음은 몇 가지 예입니다.

- 전자메일이 사용자와 이해 관계자에게 정보를 제공하는 기본 방법이고 전자메일 서비스가 저하되거나 사용 불가능한 경우 Microsoft Teams, Yammer 또는 타사 서비스와 같은 다른 서비스를 백업으로 사용할 수 있습니다. 핵심은 이를 사전에 설정하고 사용자가 어디로 가야하는지 교육하는 것입니다. Yammer 스레드는 아무도 해당 스레드가 존재하는지 모르거나, 어느 누구도 북마크하지 않은 경우 유용하지 않습니다.  
- 내부 인시던트 관리 프로세스가 음성 통신을 사용하여 응답을 조정하는 경우 위기 중에 사용할 대체 전화 솔루션을 설정합니다. 이 솔루션은 기본 서비스와 완전히 동등할 필요는 없지만 비즈니스 연속성 및 인시던트 관리 팀을 조율하는 데 필요한 최소 수준의 공동 작업을 제공해야 합니다. 또한 사용자에게 전체 주소 목록에 휴대폰 번호를 게시하도록 요청하면 극단적인 경우 추가적인 백업 통신 계층을 제공할 수 있습니다.
- 사고가 진행되는 동안 상태 업데이트를 제공할 수 있는 사용자 지정 서비스 상태 대시보드 또는 기타 사이트를 만들 수 있습니다. 사전에 정보를 구할 수 있도록 사용자를 교육하면 불필요한 헬프 데스크 요청을 줄이고 상황이 신속하고 효율적으로 처리되고 있다는 사용자 기반에 대한 자신감을 심어줄 수 있습니다. 가시성을 높이려면 O365 Service Communications API를 사용하여 이를 M365에 연결하세요.  
- 비즈니스 연속성 계획 및 표준 운영 절차의 위치를 잘 알고 있는 것이 중요 합니다. 로컬 장치와 자동 동기화하도록 구성된 SharePoint Online 또는 비즈니스용 OneDrive와 함께 중요한 문서의 온라인 및 오프라인 복사본을 유지하는 것이 좋습니다. 복구에 절대적으로 중요한 서비스/네트워크 운영 센터 및 기타 유사한 팀의 경우 응급 상황에서 사용할 수 있도록 하드 카피를 보관할 수도 있습니다.

## <a name="know-your-external-points-of-integration"></a>외부 통합 지점을 파악하세요.

비즈니스 모델에 관계없이 모든 회사에는 고객, 파트너 및 공급 업체와의 통합 지점이 있습니다. 비즈니스 가치 공급망은 외부 엔터티와의 통합을 기반으로 합니다. 서비스 중단에 대한 비즈니스 연속성 개선을 위해서는 각 통합 지점에 대한 고려와 보호가 필요합니다.  
공급망을 분석할 때 내부 통신을 분석하는 것과 동일한 방식으로 외부 통신을 고려해야 합니다. 고객이 연락하는 방법으로 유일하게 Exchange Online 서버에만 의존하고 있나요? 가동 시간이 영향을 받는 경우에 사용할 수 있는 대체 통신 방법을 공급 업체에 알리셨나요? 다음은 생각을 정리하는 방법을 제안하는 샘플 표입니다.

|외부 엔터티 이름|영향을 주는 인시던트 시나리오|Microsoft 365 서비스 통합|대안|
|---------|---------|---------|---------|
|`vendor name`|메일 흐름|Exchange Online은 Contoso와의 유일한 통신 수단입니다.|외부 Microsoft Teams 채널 또는 타사 공동 작업 소프트웨어 설정          |
|`service supplier name`|채팅|Microsoft Teams|타사 인스턴트 메시징|
|`partner name`|음성|Microsoft Teams|휴대폰 또는 공공 pstn      |
|`supplier name`|파일 공유|외부 공유 SharePoint 사이트 및 OneDrive|타사 파일 공유         |
