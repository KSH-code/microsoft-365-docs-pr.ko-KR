---
title: 데이터 손실 방지 계획
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
audience: ITPro
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
search.appverid:
- MET150
description: 데이터 손실 방지 계획 프로세스 개요
ms.openlocfilehash: 130675ad15a872ed14041289fb24aeec471014ff
ms.sourcegitcommit: d08fe0282be75483608e96df4e6986d346e97180
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/12/2021
ms.locfileid: "59192959"
---
# <a name="plan-for-data-loss-prevention-dlp"></a>DLP(데이터 손실 방지) 계획

모든 조직의 비즈니스 요구, 목표, 리소스 및 상황은 각 조직마다 고유하기 때문에 모든 조직은 DLP(데이터 손실 방지)를 다르게 계획하고 구현합니다. 그러나 성공한 모든 DLP 구현에 공통적인 요소가 있습니다. 이 문서에서는 조직에서 DLP 계획에 사용하는 모범 사례를 제공합니다.

## <a name="multiple-starting-points"></a>여러 시작 지점

많은 조직에서 다양한 정부 또는 산업 규정을 준수하기 위해 DLP를 구현하기로 선택했습니다. 예를 들어 유럽 연합의 GDPR(일반 데이터 보호 규정) 또는 HIPAA(Health Insurance Portability and Accountability Act) 또는 캘리포니아 소비자 개인 정보 보호법(CCPA)을 예로 들 수 있습니다. 또한 데이터 손실 방지를 구현하여 지적 재산을 보호합니다. 그러나 DLP 여정의 시작 장소와 최종 목적지는 다양합니다. 

조직은 DLP 여정을 시작할 수 있습니다.

- 채팅 및 채널 메시지 또는 Teams 디바이스의 정보를 보호하려는 경우와 같은 플랫폼 Windows 10 있습니다.
- 의료 기록과 같이 보호의 우선 순위를 지정하려는 중요한 정보를 알고 있으며 이를 보호하기 위한 정책 정의로 바로 가기
- 중요한 정보가 무엇인지, 정보의 위치, 누가 검색 및 분류로 시작하고 좀 더 까다로적인 접근 방식을 취하는지 알지 못합니다.
- 중요한 정보가 무엇인지, 정보의 위치를 모르거나, 정보로 무엇을 하고 있는지 알지 못하지만 정책 정의로 바로 이동하여 이러한 결과를 시작 위치로 사용하여 정책을 구체화할 것입니다.
- 정보 보호 스택의 전체 Microsoft 365 구현해야 하다는 것을 알고 있으므로 더 장기적인 방법으로 접근할 예정임

이러한 DLP는 고객이 DLP에 접근할 수 있는 방법의 몇 가지 예에 불과하며, 어디에서 시작해도 상관이 없습니다Microsoft 365 DLP는 시작부터 완전히 실현된 데이터 손실 방지 전략까지 다양한 유형의 정보 보호 여정을 수용할 수 있을 만큼 유연합니다. 

## <a name="overview-of-planning-process"></a>계획 프로세스 개요

데이터 [손실 방지에 대한 자세한](dlp-learn-about-dlp.md#learn-about-data-loss-prevention) 정보에서는 DLP 계획 프로세스의 세 가지 [측면을 소개합니다.](dlp-learn-about-dlp.md#plan-for-dlp) 여기서는 모든 DLP 계획에 공통되는 요소에 대해 자세히 설명할 것입니다.

### <a name="identify-stakeholders"></a>관련자 파악

DLP 정책을 구현하면 조직의 많은 부분에 적용할 수 있습니다. IT는 부정적인 결과 없이는 자체적으로 광범위한 계획을 개발할 수 없습니다. 다음을 할 수 있는 관련자를 식별해야 합니다.

- 조직이 적용하는 규정, 법률 및 산업 표준 설명
- 보호할 중요한 항목의 범주
- 사용되는 비즈니스 프로세스
- 제한해야 하는 위험한 동작
- 관련 항목 및 위험의 민감도에 따라 먼저 보호해야 하는 데이터의 우선 순위 지정
- DLP 정책 일치 이벤트 검토 및 수정 프로세스 개요 
 
일반적으로 이러한 요구는 85%의 규제 및 규정 준수 보호와 15%의 지적 재산 보호입니다. 다음은 계획 프로세스에 포함할 역할에 대한 몇 가지 제안 사항입니다.

- 규정 및 규정 준수 책임자
- 최고 위험 책임자
- 법률 담당자
- 보안 및 규정 준수 담당자
- 데이터 항목에 대한 비즈니스 소유자
- 비즈니스 사용자
- IT

### <a name="describe-the-categories-of-sensitive-information-to-protect"></a>보호할 중요한 정보의 범주 설명

그러면 이해 관계자는 보호할 중요한 정보의 범주와 사용되는 비즈니스 프로세스에 대해 설명합니다. 예를 들어 Microsoft 365 DLP는 다음 범주를 정의합니다.

- 금융 
- 의료 및 의료 정보
- 개인 정보
- 사용자 지정

관련자는 중요한 정보를 "데이터 프로세서이기 때문에 데이터 주체 정보 및 재무 정보에 대한 개인 정보 보호를 구현해야 합니다."로 식별할 수 있습니다.

 
  <!-- The business process is important as it informs the ‘data at rest’, ‘data in transit’, ‘data in use’ aspect of DLP planning and who should be sharing the items and who should not.-->

### <a name="set-goals-and-strategy"></a>목표 및 전략 설정

이해 관계자를 식별하고 보호가 필요한 중요한 정보 및 사용 위치를 파악한 후 이해 관계자는 보호 목표를 설정할 수 있으며 IT는 구현 계획을 개발할 수 있습니다. 


 <!--
### Discovery
 for the locations (DLP workloads) of these types of items.  (mapping DLP locations and data at rest, data in transit, data in use)

### IT can start coding test policies
start small and always in test mode. Note that DLP policies can feed into insider risk.

### Business process owners help with tuning
 false positive/false negative results and fitting DLP into their business processes.

-->

### <a name="set-implementation-plan"></a>구현 계획 설정

구현 계획에는 다음이 포함되어야 합니다.

- 시작 상태 및 원하는 종료 상태와 단계 중 하나에서 다른 상태로의 단계 매핑
- 중요한 항목 검색을 해결할 방법
- 정책 계획 및 정책 계획이 구현될 순서
- 모든 선행 요구 문제를 해결할 방법
- 적용으로 이동하기 전에 정책을 먼저 테스트하는 방법 계획
- 최종 사용자를 교육하는 방법
- 정책을 테스트하고 조정하는 방법
- 변화하는 규제, 법률, 산업 표준 또는 지적 재산 보호 및 비즈니스 요구에 따라 데이터 손실 방지 전략을 검토하고 업데이트하는 방법

#### <a name="map-out-path-from-start-to-desired-end-state"></a>시작에서 원하는 종료 상태로 경로 매핑

조직이 시작 상태부터 원하는 종료 상태로 어떻게 진행할지 문서화하는 것은 관련자와 의사소통하고 프로젝트 범위를 설정하는 데 필수적입니다. 다음은 DLP를 배포하는 데 일반적으로 사용되는 단계 집합입니다. 이보다 더 자세한 내용을 원하지만 이를 사용하여 DLP 채택 경로를 틀 수 있습니다.

![DLP 배포의 일반적인 순서를 보여 주며 그래픽](../media/dlp-deployment-planning.png)

#### <a name="sensitive-item-discovery"></a>중요한 항목 검색

여러 가지 방법으로 개별 중요한 항목의 위치와 위치를 검색할 수 있습니다. 민감도 레이블이 이미 배포되어 있을 수도 있으며, 항목을 검색하고 감사하는 모든 위치에 광범위한 DLP 정책을 배포하기로 결정한 것일 수 있습니다. 자세한 내용은 데이터 [알고 를 참조합니다.](information-protection.md#know-your-data)

#### <a name="policy-planning"></a>정책 계획

DLP 채택을 시작할 때 이러한 질문을 사용하여 정책 디자인 및 구현 노력에 집중할 수 있습니다.

##### <a name="what-laws-regulations-and-industry-standards-must-your-organization-comply-with"></a>조직에서 준수해야 하는 법률, 규정 및 산업 표준은 무엇입니까?

많은 조직이 규정 준수를 위해 DLP를 사용하게 많기 때문에 이 질문에 대한 대답은 DLP 구현을 계획하기 위한 자연스러운 시작 장소입니다. 그러나 IT 구현자 입장에서는 응답할 위치가 아 않을 수 있습니다. 법률 팀과 비즈니스 임원이 답변해야 합니다. 
 
**예제** 조직은 영국의 대상입니다. 재무 규정.


##### <a name="what-sensitive-items-does-your-organization-have-that-must-be-protected-from-leakage"></a>조직에서 누출로부터 보호해야 하는 중요한 항목은 무엇입니까?

조직에서 규정 준수 요구의 관점에서 해당 항목이 어디인지 알고 나면 누출로부터 보호해야 하는 중요한 항목과 이를 보호하기 위해 정책 구현의 우선 순위를 지정하는 방법을 알 수 있습니다. 이렇게 하면 가장 적합한 DLP 정책 템플릿을 선택하는 데 도움이 됩니다. Microsoft 365, 의료 및 건강, 개인 정보 보호를 위해 미리 구성된 DLP 템플릿과 함께 사용할 수 있으며 사용자 지정 템플릿을 사용하여 직접 빌드할 수 있습니다. 실제 DLP 정책을 디자인하고 만들 때 이 질문에 대한 답변을 알면 올바른 중요한 정보 유형을 선택하는 [데도 도움이 됩니다.](sensitive-information-type-learn-about.md#learn-about-sensitive-information-types)

**예제** 빠르게 시작하기 위해 , 및 중요한 정보 유형이 포함된 정책 `U.K. Financial Data` `Credit Card Number` `EU Debit Card Number` `SWIFT Code` 템플릿을 선택해야 합니다. 

##### <a name="where-are-the-sensitive-items-and-what-business-processes-are-they-involved-in"></a>중요한 항목은 어디에 있으며 어떤 비즈니스 프로세스가 관련이 있나요?

조직에서 중요한 정보를 포함하는 항목은 비즈니스를 하는 과정에서 매일 사용됩니다. 중요한 정보의 인스턴스가 발생할 수 있는 위치와 해당 인스턴스가 사용되는 비즈니스 프로세스를 알아야 합니다. 이렇게 하면 DLP 정책을 적용할 올바른 위치를 선택하는 데 도움이 됩니다. Microsoft 365 DLP 정책은 위치에 적용됩니다.

- Exchange 전자 메일
- SharePoint 사이트
- OneDrive 계정
- Teams 채팅 및 채널 메시지
- Windows 10 장치
- Microsoft Cloud App Security
- 사내 리포지토리

**예제** 조직의 내부 감사자는 신용 카드 번호 집합을 추적합니다. 이러한 스프레드시트는 보안 사이트로 SharePoint 보관합니다. 일부 직원은 복사본을 만들어 자신의 비즈니스용 OneDrive 저장하며, 이 사이트는 Windows 10 장치와 동기화됩니다. 이 중 한 명은 14명 목록을 전자 메일에 붙여넣고 검토를 위해 외부 감사인에게 보내보는 중입니다. 정책을 보안 SharePoint 사이트, 모든 내부 감사자 비즈니스용 OneDrive 계정, Windows 10 장치 및 전자 메일 Exchange 적용할 수 있습니다.

##### <a name="what-is-your-organizations-tolerance-for-leakage"></a>조직에서 누출을 허용할 수 있는 것은 무엇입니까?

조직의 여러 그룹은 허용되는 중요한 항목 누출 수준과 중요하지 않은 항목에 대해 서로 다른 보기를 사용할 수 있습니다. 누출을 완벽하게 이행하면 비즈니스에 너무 많은 비용이 들 수 있습니다.

**예제** 법률 팀과 함께 조직의 보안 그룹은 조직 외부의 모든 사용자와 신용 카드 번호를 공유하지 말아야 한다고 생각하며 누출을 0으로 요구합니다. 그러나 신용 카드 번호 활동에 대한 정기적인 검토의 일부로 내부 감사자는 일부 신용 카드 번호를 타사 감사인과 공유해야 합니다. DLP 정책으로는 전화기 외부의 신용 카드 번호 공유를 모두 금지하는 경우 내부 감사관이 추적을 완료하기 위해 업무 프로세스 중단과 비용을 추가하여 중단을 완화할 수 있습니다. 이 추가 비용은 임원진에게는 받아들일 수 없습니다. 이 문제를 해결하기 위해 허용되는 누출 수준을 결정하기 위한 내부 대화가 필요합니다. 정책이 결정된 후 특정 개인이 정보를 공유하기 위한 예외를 제공하거나 감사 전용 모드에서 적용할 수 있습니다.

#### <a name="planning-for-prerequisites"></a>선행 준비 계획

일부 DLP 위치를 모니터링하려면 먼저 충족해야 하는 선행 조건이 있습니다. 다음의 **시작하기 전에** 섹션을 참조하세요.

- [데이터 손실 방지 온-프레미스 스캐너로 시작하기(미리 보기)](dlp-on-premises-scanner-get-started.md#before-you-begin)
- [끝점 데이터 손실 방지 시작](endpoint-dlp-getting-started.md#before-you-begin)
- [Microsoft 규정 준수 확장 시작(미리 보기)](dlp-chrome-get-started.md#before-you-begin)
- [Microsoft가 아닌 클라우드 앱에 데이터 손실 방지 정책 사용(미리 보기)](dlp-use-policies-non-microsoft-cloud-apps.md#before-you-begin)

#### <a name="policy-deployment"></a>정책 배포

DLP 정책을 만든 후에는 완전히 적용하기 전에 서서히 롤아웃하면서 영향을 평가하고 효율성을 테스트하는 것이 좋습니다. 예를 들어 새 DLP 정책으로 수천 개의 문서에 대한 액세스를 의도하지 않은 것으로 차단하거나 기존 비즈니스 프로세스를 중단하지 않습니다.
  
영향이 클 수 있는 DLP 정책을 생성하는 경우에는 다음과 같은 순서를 따르는 것이 좋습니다:
  
1. **정책 팁이 없는 테스트 모드에서 시작** 하고 DLP 보고서 및 모든 사고 보고서를 사용하여 영향을 평가합니다. DLP 보고서를 사용하여 정책 일치의 횟수, 위치, 유형 및 심각도를 확인할 수 있습니다. 결과에 따라 필요한 경우 정책을 미세 조정할 수 있습니다. 테스트 모드에서 DLP 정책은 조직에서 작업하는 사용자의 생산성에 영향을 주지 않습니다. 또한 이 스테이지를 사용하여 DLP 이벤트 검토 및 문제 해결을 위한 워크플로를 테스트합니다.
    
2. **알림 및** 정책 정책을 팁 모드로 전환하여 사용자에게 규정 준수 정책을 교육하고 적용될 정책을 준비할 수 있습니다. 정책 팁에서 정책에 대한 자세한 정보를 제공하는 조직 정책 페이지에 대한 링크를 제공하는 것이 유용합니다. 이 단계에서 정책을 추가로 구체화할 수 있도록 사용자에게 가짓 긍정 보고를 요청할 수 있습니다. 정책 응용 프로그램의 결과가 관련자의 생각과 일치할 수 있다는 확신이 있는 경우 이 단계로 이동하세요. 
    
3. 규칙에서 작업이 적용되고 콘텐츠가 보호되도록 **정책에 대한 전체 적용을 시작합니다**. DLP 보고서 및 모든 사고 보고서나 알림을 계속 모니터링하여 결과가 의도한 대로 나타나는지 확인합니다. 

    ![테스트 모드를 사용하고 정책을 켜기 위한 옵션입니다.](../media/49fafaac-c6cb-41de-99c4-c43c3e380c3a.png)

    언제든지 DLP 정책을 종료할 수 있습니다. 이 경우 정책의 모든 규칙들이 영향을 받습니다. 하지만 규칙 편집기에서 상태를 전환하여 각 규칙을 개별적으로 종료할 수도 있습니다.

    ![정책에서 규칙을 끄기 위한 옵션입니다.](../media/f7b258ff-1b8b-4127-b580-83c6492f2bef.png)

    정책에서 여러 규칙의 우선 순위를 변경할 수도 있습니다. 이를 위해 편집할 정책을 엽니다. 규칙의 행에서 줄임표(**...**)를 선택하고 **아래로 이동** 또는 **마지막 규칙 가져오기** 와 같은 옵션을 선택하십시오.

    ![규칙 우선 순위를 설정합니다.](../media/dlp-set-rule-priority.png)

#### <a name="end-user-training"></a>최종 사용자 교육

DLP 정책이 트리거되면 전자 메일 알림을 보내도록 정책을 구성하고 관리자 및 최종 사용자에게 [DLP](use-notifications-and-policy-tips.md#send-email-notifications-and-show-policy-tips-for-dlp-policies) 정책에 대한 정책 팁을 표시하도록 구성할 수 있습니다. 정책이 여전히 테스트 모드에 있는 동안 차단 작업을 적용하기 전에 정책 팁은 중요한 항목에 대한 위험한 동작에 대한 인식을 높이고 사용자에게 향후 이러한 동작을 방지할 수 있도록 교육하는 유용한 방법입니다.  

#### <a name="review-dlp-requirements-and-update-strategy"></a>DLP 요구 사항 및 업데이트 전략 검토

조직이 적용하는 규정, 법률 및 산업 표준은 시간이 지날 때 변경될 예정이고 DLP에 대한 비즈니스 목표도 변합니다. 조직이 규정을 준수하고 DLP 구현이 비즈니스 요구를 계속 충족하도록 이러한 모든 영역에 대한 정기적인 검토를 포함해야 합니다.

## <a name="approaches-to-deployment"></a>배포 방법

|고객 비즈니스 요구 설명  | 접근 방식  |
|---------|---------|
|**Contoso Bank는** 높은 규제 대상 산업에 있으며 다양한 위치에 다양한 유형의 중요한 항목이 있습니다. </br> - 우선 순위가 가장 높은 중요한 정보 유형을 알고 있습니다. </br> - 정책을 롤아웃할 때 비즈니스 중단을 최소화해야 합니다. </br> - IT 리소스가 있으며 계획, 디자인 배포에 도움이 되는 전문가를 고용할 수 있습니다. </br> - Microsoft와 프리미어 지원 계약을 체결| - 시간을 내어 준수해야 하는 규정과 규정 준수 방법을 이해합니다. </br> -정보 보호 스택의 더 나은 함께 값을 이해하기 Microsoft 365 시간을 내어 사용하세요. </br> - 우선 순위가 높은 항목에 대한 민감도 레이블 지정 체계 개발 및 적용 </br> - 비즈니스 프로세스 소유자 참여 </br>- 디자인/코드 정책, 테스트 모드로 배포, 사용자 교육 </br>- 반복|
|**TailSpin Toys는** 현재 위치나 위치를 모르는 리소스 깊이가 거의 없습니다. 광범위한 Teams, 비즈니스용 OneDrive Exchange 사용하게 됩니다.     |- 우선 순위가 지정한 위치에 대한 간단한 정책으로 시작 </br>- 식별된 것을 모니터링합니다. </br>- 그에 따라 민감도 레이블 적용 </br>- 정책 구체화, 사용자 교육       |
|**Fabrikam은** 소규모 스타트업으로, 지적 재산을 보호하려는 경우 빠르게 이동해야 합니다. 일부 자원은 전담하지만 외부 전문가를 고용할 수 없습니다. </br>- 중요한 항목이 모두 Microsoft 365 비즈니스용 OneDrive/SharePoint </br>- 사용자 및 비즈니스용 OneDrive SharePoint, 직원/섀도 IT는 DropBox 및 Google drive를 사용하여 항목을 공유/저장합니다. </br>- 직원의 데이터 보호 분야보다 작업 속도 향상 </br>- 고객 지원 및 신규 직원 18명 모두 Windows 10 구입     |- 기본 DLP 정책을 Teams </br>- 항목의 기본 설정으로 SharePoint 사용 </br>- 외부 공유를 방지하는 정책 배포 </br>- 우선 순위가 지정한 위치에 정책 배포 </br>- 디바이스에 정책 Windows 10 배포 </br>- 비보안 클라우드 저장소로의 비즈니스용 OneDrive 차단      |

<!--

## Planning for workloads

### Exchange

### SharePoint

### OneDrive for Business

### Teams

### Windows 10 Devices

### Microsoft Cloud App Security (MCAS)

### On-premises Scanner
-->

## <a name="see-also"></a>참고 항목
- [데이터 손실 방지에 대해 알아보기](dlp-learn-about-dlp.md#learn-about-data-loss-prevention)
