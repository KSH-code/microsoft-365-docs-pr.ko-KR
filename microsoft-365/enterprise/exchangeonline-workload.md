---
title: Exchange Online Microsoft 365 Enterprise에 대 한 배포
author: JoeDavies-MSFT
manager: laurawi
ms.date: 06/28/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection: Ent_O365
ms.custom:
- Strat_O365_Enterprise
description: 단계에 대 한 계획을 제공 하 고 조직 전체에서 Microsoft 365 기업에서 Exchange Online의 값을 제어 하는 프로세스를 통해 수행 합니다.
ms.openlocfilehash: aafa1b28546eb77938bb3e4a5ebe9ccd60b9a60b
ms.sourcegitcommit: e491c4713115610cbe13d2fbd0d65e1a41c34d62
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/16/2019
ms.locfileid: "26870341"
---
# <a name="deploy-exchange-online-for-microsoft-365-enterprise"></a>Exchange Online Microsoft 365 Enterprise에 대 한 배포

Exchange Online은 전자 메일에 대 한 기본 클라우드 서비스 및이 통해 일정 실시간 채팅 필요 하지 않은 또는 문서 저장소에 집중 하는 방법으로 공동 작업 사용자에 게 합니다. Exchange Online 개별 및 작은 그룹 단기 통신 및 일정 방법 이며 Microsoft 365 Enterprise의 더욱 원활 값에 대 한 내장의 핵심 요소입니다. Exchange Online 더 수행 하 고 잘 알려진 Outlook 응용 프로그램의 없이 이동 중일 장치에 관계 없이 보다 효과적으로 작업할 수 있습니다.

Exchange Online도 고급 사서함을 보호 하기 위해 맬웨어 방지 및 스팸 방지 필터링을 비롯 하 여 보안 기능 및 사용자가 실수로 중요 한 정보를 보내는 경우 권한이 없는 사람에 게 하지 못하도록 하는 데이터 손실 방지 기능 합니다. Exchange Online 보안은 Microsoft 365 Enterprise의 지능형 보안 값의 핵심 요소입니다.

Exchange Online으로 새로운 인 경우 [Microsoft Exchange Online](https://products.office.com/exchange/exchange-online)을 참조 하십시오.

다음 단계를 안내 하 envisioning 온 보 딩 조직에서 Exchange online 역할 점진적 롤아웃 시리즈를 통해 Exchange online 조직 및 Exchange Online의 사용을 제어 하는 프로세스 및 해당 최종 사용자에 게 값입니다.

>[!Note]
>[단계 2-Identity](identity-infrastructure.md) Microsoft 365 Enterprise foundation 인프라를 완료 한 후에이 배포 지침을 따라야 합니다.
>

## <a name="phase-1-envision"></a>1단계: 구상

이 단계에서 Exchange Online 배포에 대 한 사람을 수집 및 어떻게 조직에서 사용할 Exchange Online의 비즈니스 요구를 해결 하는 결정 합니다.

### <a name="step-1-gather-your-exchange-online-deployment-members"></a>1 단계: Exchange Online 배포 구성원에 수집

Microsoft 365 Enterprise foundation 인프라의 [단계 2-Identity](identity-infrastructure.md) Exchange Online의 성공적인 배포에 대 한 입력 및 피드백에 대 한 권한 있는 사용자를 가져올 해야 합니다. 주요 작업 자가 비즈니스 의사 결정권자, IT 담당자가 설계자 및 구현, 최종 사용자에 대 한을 대표 등을 포함합니다. 

이러한 세 그룹 Exchange Online 배포 비즈니스 요구 사항, 사서함 마이그레이션 및 보안을의 기술적 측면 및 일반적인 사용자가 사용 되어 있음을 결과 수를 처리 하는 고려 사항을 포함 되어있는지 확인 합니다.

#### <a name="result"></a>결과

조직의 비즈니스, 기술 및 최종 사용자 측면을 대표하는 구성원 목록을 얻을 수 있습니다.

### <a name="step-2-determine-and-prioritize-your-exchange-online-business-scenarios"></a>2 단계: 확인 하 고 Exchange Online 비즈니스 시나리오를 우선순위

Exchange Online을 다른 용도로 사용할 수 있습니다. 어떤 목적으로 별도 수준의 조직, 비즈니스 그룹, 부서 또는 개별 작업 시간 및 프로젝트 팀에 비즈니스 요구 사항에 맞게 파악 해야 합니다. Exchange Online에 개별 및 작은 그룹 단기 통신 및 예약 요구를 해결 하는 대상 해야 합니다. 

Exchange Online의 혜택을 참조 하는 한 가지 방법은 개인, 팀 또는 v 팀 오늘날 상호작용 하 고 찾기를 통신, 모임 예약 및 공동 작업을 편리 하 게 제공 하는 적절 한 시나리오를 어떻게를 검사 하는 합니다. [Microsoft 팀의](teams-workload.md) 공동 작업 시나리오 중 일부에 대 한 보다 적합할 수 있다는 것을 염두에 두십시오.

Exchange Online은 다음과 같은 Microsoft 365 Enterprise에 대한 전략적 비즈니스 시나리오를 지원합니다.

- 실시간으로 또는 원하는 시간에 문서 공동 작업을 수행하여 공동 작성 프로세스 간소화
- 비즈니스 목표에 맞게 프로젝트, 작업 및 기한 관리
- 작업 습관을 이해하여 미치는 영향 개선
- 팀과 소통하여 정보를 제공하고, 정보 제공을 요청하고, 협력 및 의견 합의 도달
- 조직 내부 및 외부에서 파일을 저장 및 공유하여 조직 경계를 넘나들며 원활하게 작업 가능
- 유연한 작업 스타일을 유지하면서 어떤 장치를 사용하든 장소나 시간의 구애를 받지 않고 안전하게 더 많은 작업 처리
- 사용자의 정보 보호 및 데이터 손실 위험 최소화
- 검색 하 고 외부 위협 으로부터 보호 
- 모니터링, 보고 및 조직의 보안을 제공 하려면 신속 하 게 대처 하는 작업을 분석
- 개인 정보 보호 및 규정 준수로 조직이 GDPR(일반 데이터 보호 규정)을 준수하도록 지원

자세한 내용은 [Microsoft 365를 사용한 디지털 변환](http://transform.microsoft.com)을 참조하세요. 

#### <a name="result"></a>결과
통신, 일정 및 단기 공동 작업에 대 한 조직의 요구를 처리 하는 Exchange Online 시나리오 목록을 제공 합니다.

## <a name="phase-2-onboard"></a>2단계: 온보딩

이 단계는 Exchange Online 배포의 기술적 측면에 대 한 계획 하 고 사용자의 선택 된 그룹 전체에 배포를 시작 합니다.

### <a name="prerequisites-identity-and-device-access-configuration"></a>필수 구성 요소: ID 및 장치 액세스 구성

Exchange Online 사서함에 대 한 액세스를 보호 하려면 웹 [id 및 장치에 대 한 액세스 정책](identity-access-policies.md) 및 [Exchange Online 액세스 정책 권장](secure-email-recommended-policies.md)구성 했는지 확인 합니다.

### <a name="step-1-complete-your-technical-planning"></a>1단계: 기술 계획 완료

기술 계획을 시작 하기 전에 FastTrack을 사용 하 여 할지 여부를 결정 합니다. 조직 50 개 이상의 시트에 하는 [가능한 계획](https://technet.microsoft.com/library/dn783224.aspx)에 참여 하는 경우에 [Microsoft 365 FastTrack](https://fasttrack.microsoft.com/microsoft365), 계획, 배포 및 서비스 채택 안내 하는 추가 비용 없이 사용할 수 있는 사용할 수 있습니다. 또는 Office 365 계정을 사용 하 여 로그인 한 후 [FastTrack](https://fasttrack.microsoft.com/) 에서 사용할 수 있는 FastTrack 온 보 딩 마법사를 사용 하 여 직접이 작업을 완료할 수 있습니다.

FastTrack와 함께에서 또는 직접 계획을 수행 하는 경우 네트워크와 조직의 Exchange Online에 대 한 준비가 되었는지 여부를 확인할 필요가 있습니다. 것이 특히 중요 인터넷 대역폭, 처리량 및 Exchange에 대 한 추가 트래픽에 대 한 성능을 최대화 하기 위해 트래픽 지연에 특히 주의 하 여 foundation 인프라에서 네트워킹에 대 한 종료 기준 맞는지 온라인 기반 전자 메일 및 첨부 파일입니다.

이러한 리소스를 사용 하 여는 Exchange Online 배포의 기술적 측면에 대 한 준비 합니다. 

- [Office 365로 여러 전자 메일 계정을 마이그레이션하는 방법](https://docs.microsoft.com/Exchange/mailbox-migration/mailbox-migration)
- [Office 365 메일 마이그레이션 관리자](https://portal.office.com/onboarding/mailsetupadvisor#/) (로그인 해야 Office 365 구독)
- [Exchange Online의 공동 작업](https://technet.microsoft.com/library/jj983794(v=exchg.150).aspx)
- [Exchange Online의 받는 사람](https://technet.microsoft.com/library/jj200702(v=exchg.150).aspx)

제대로 이해 Exchange Online의 보안을 다음 리소스를 검토 합니다.

- [Exchange Online의 사용 권한](https://technet.microsoft.com/library/jj200692(v=exchg.150).aspx) 
- [보안 및 Exchange Online에 대 한 규정 준수](https://technet.microsoft.com/library/jj200706(v=exchg.150).aspx) 
- [스팸 방지 및 맬웨어 방지 보호](https://technet.microsoft.com/library/jj200731(v=exchg.150).aspx)

다음으로, 이러한 리소스를 사용 하 여 Exchange Online 사서함 관리를 이해 하려면:

- [Exchange Online에서 사용자 사서함 만들기](https://technet.microsoft.com/library/jj907304(v=exchg.150).aspx)
- [사용자 사서함 관리](https://technet.microsoft.com/library/bb123809(v=exchg.150).aspx) 
- [메일 그룹 만들기 및 관리](https://technet.microsoft.com/library/bb124513%28v=exchg.150%29.aspx)

#### <a name="result"></a>결과

프로젝트 관리자는 사서함 마이그레이션, 보안 및 관리를 이해 하 고이 정보를 Exchange Online 조직에서 선택한 그룹에 제공 준비가 됩니다.

### <a name="step-2-run-an-it-pilot"></a>2단계: IT 파일럿 실행

대부분의 중간 규모 및 대규모 조직에서는 1단계의 이해 관계자, 얼리 어답터 및 기술 전문가와 함께 IT 파일럿을 실행해야 합니다. IT 파일럿 중에 수행하는 작업은 다음과 같습니다.

- IT 파일럿 참가자에 게는 연습을 할 수는 Exchange Online 비즈니스 시나리오를 선택 합니다.
- 파일럿 참가자에 게 Office 365 라이선스 부여 하 고 Exchange Online으로 온-프레미스 사서함을 마이그레이션하십시오.
- Exchange Online 전자 메일, 일정 및 기타 기능을 테스트 하는 연습 집합이 파일럿 참가자에 게 제공 합니다.
- 변경 관리 전략을 결정 하 고 Exchange Online의 드라이브 조직 전체의 사용자 채택 하는 자료를 생성 합니다. 변경 관리 자료 (영문) 전자 메일 알림 텍스트, 내부 교육 계획 준비, 복도 포스터 및 프레젠테이션에 포함 될 수 있습니다. 이러한 자료는 Exchange Online 및 발생 인식과 구동 사용의 목표와 그 이점에 대 한 조직을 게 알립니다. 일부 아이디어를 그릴 수에 대 한 [Microsoft 팀에 대 한 관리 전략을 변경](https://docs.microsoft.com/MicrosoftTeams/change-management-strategy) 하는 문서를 참조 하십시오.
- 해당 환경에 따라 변경 관리 자료를 검토 하 여 IT 파일럿 참가자가입니다. 모범 사례에 대 한 팁 및 조언 가장 Exchange Online의 이점에 설명 하는 방법 및 통신 및 일정을 사용 하는 방법에 제공할 수 있습니다.

#### <a name="result"></a>결과

Exchange Online IT 시험 완료 되 고 초기 변경 관리 자료 된 개발, 검토 하 고, 있고 미세 조정 합니다.

### <a name="step-3-roll-out-to-a-business-group"></a>3단계: 비즈니스 그룹에 롤아웃

IT 시험을 완료 한 후 비즈니스 그룹 또는 조직에서 부서를 Exchange Online 아웃 롤 합니다. 예: Exchange 서버는 온-프레미스 전자 메일 서비스를 사용 하는 경우이 롤아웃 사서함 마이그레이션 구성 됩니다. 이 배포는 다음과 같습니다.

- 비즈니스 그룹 내에서 Exchange Online에 대 한 주요 비즈니스 시나리오의 식별 합니다.
- 알림 활동을 기대 및 부서 및 회사 또는 프로젝트 팀에 대 한 Exchange Online 사용 현황에 대 한 일정의 사용자에 게 알려야 합니다.
- Exchange Online으로 비즈니스 그룹 구성원의 온-프레미스 사서함의 마이그레이션 합니다.
- Exchange Online 및 사용 하는 방법을 소개 하는 리소스를 Exchange Online 또는 링크에 대 한 사용자 교육을 제공 합니다.
- 비즈니스 그룹의 사용자로부터 의견을 수집하고 문제에 대해 조치를 취하기 위한 피드백 메커니즘(예: 비즈니스 그룹의 모든 사용자를 포함하는 중앙 Microsoft Teams 팀)

롤아웃하는 동안 조직 차원의 롤아웃을 준비하려면 변경 관리 자료를 구체화할 수 있습니다.

#### <a name="result"></a>결과

비즈니스 그룹 올라갑니다 및 Exchange Online과 함께 실행 하 고 변경 관리 자료를 테스트 및 미세 조정 합니다.

## <a name="phase-3-drive-value"></a>3단계: 가치 창출

이 단계에서 Exchange Online의 배포를 완료 하 고 그 혜택을 실현 하기 위해 사용자를 지원 합니다.

### <a name="step-1-roll-out-exchange-online-to-the-rest-of-your-organization"></a>1 단계: 롤아웃을 Exchange Online 조직의 나머지 부분에

나머지 조직 구성원에게 롤아웃하는 과정에는 다음이 포함되어야 합니다.

- 별도 비즈니스 그룹 내에서 Exchange Online에 대 한 주요 비즈니스 시나리오의 식별 합니다.
- 기대의 조직을 알리기 위해 알림 활동에 대 한 구체화 된 변경 관리 재료 및 Exchange Online 사용 현황에 대 한 시간 표시 막대의 사용 합니다.
- Exchange online 조직의 나머지 부분에 대 한 사서함의 마이그레이션 합니다.
- 사용자 교육 제공 (영문) Exchange Online 또는 Exchange Online 및 사용 하는 방법을 소개 하는 리소스에 대 한 링크를 제공 합니다.
- 조직의 사용자로부터 의견 및 문제를 수집하기 위한 피드백 메커니즘(예: 모든 사용자를 포함하는 중앙 팀). 조직의 사용자가 2500명 미만인 경우 Teams의 공개 채널을 사용하고, 2500명 이상인 경우 Yammer의 공용 그룹 사용

#### <a name="result"></a>결과

조직을 이며 실행 하 고 변경 관리 전략 전체에 게 알리기, 교육, 및 Exchange Online을 사용 하 여 사용자를 사용 하도록 설정 합니다.

### <a name="step-2-measure-usage-manage-satisfaction-and-drive-adoption"></a>2단계: 사용 현황 측정, 만족도 관리 및 도입 촉진

전체 조직에 Exchange Online 아웃 롤링을 한 후에 변경 관리 전략을 활용 하는 계속 해야 합니다.

- 개별와 짧은 통신을 위한 기본 도구로 Exchange Online 승격 하 여 리더 있고 예약 합니다.
- 부서, 작업, 비즈니스 그룹에 대해 사용 하 여 개인을 촉진 하 고 프로젝트 팀 통신, 일정, 및 공동 작업 합니다.

다음은 몇 가지 추천 활동입니다.

- [Office 365 도입 지침](https://aka.ms/successfactors)을 통해 클라우드 서비스 도입에 대한 일반적인 모범 사례를 살펴봅니다. 
- [Office 365 활동 보고서](https://docs.microsoft.com/office365/admin/activity-reports/activity-reports)를 통해 조직 전체의 Office 365 서비스 사용을 이해합니다. 조직의 Office 365 전역 관리자에게 활동 보고서에 액세스할 수 있도록 사용자 계정에 보고서 읽기 권한자 권한을 부여해 달라고 요청합니다(Office 365 전역 관리자가 아닌 경우).
- 문제 및 Exchange Online과 경험 하는 방법에 대 한 개인의 피드백에 대 한 사용자 의견 위치 (팀이 팀 또는 Yammer를 중앙에서 공용 채널)를 모니터링 합니다. 당황한 개인을 방지 하 고 시연 롤아웃에 대 한 지원을를 최대한 신속 하 게 질문 및 문제를 해결 합니다.
- 식별 하 고 각 비즈니스 그룹에서 챔피언 촉진 시키는 자신의 성과 및 Exchange Online을 사용 하 여 최상의 방법을 중점적으로 설명 합니다. 프로젝트 성공 및 채택을 표시 하는 조직에 아웃 성공 사례를 반영 합니다. 비즈니스 그룹 내에서 기술 리더의 보증에는 리더 및 동료를 통해는 강력한 영향을 줄 수 있습니다.

#### <a name="result"></a>결과

조직은 해당 기본 개별 및 작은 그룹 단기 통신 및 일정 관리 도구와 Exchange Online 채택 했습니다.

## <a name="how-microsoft-does-microsoft-365-enterprise"></a>Microsoft에서 Microsoft 365 Enterprise를 수행하는 방법

Microsoft 내의 내밀기 고 회사의 Exchange Online으로 마이그레이션한 및 인터넷 공격 으로부터 보호 하기 위해 Exchange Online Protection을 사용 하는 방법에 대해 알아봅니다 참조 하십시오.

- [Microsoft에서 150,000개의 사서함을 Exchange Online으로 마이그레이션](https://www.microsoft.com/itshowcase/Article/Content/577/Microsoft-migrates-150000-mailboxes-to-Exchange-Online)
- [Microsoft는 위협 인텔리전스를 사용하여 위협 방지, 감지 및 대응](https://www.microsoft.com/itshowcase/Article/Content/934/Microsoft-uses-threat-intelligence-to-protect-detect-and-respond-to-threats)
- [Microsoft는 Office 365를 사용하여 피싱 시도 저지](https://www.microsoft.com/itshowcase/Article/Content/956/Microsoft-thwarts-phishing-attempts-with-Office-365)

## <a name="next-steps"></a>다음 단계

Exchange Online의 지속적인 유지 관리에 대 한 이러한 리소스를 참조 하십시오.

- [Exchange Online의 Exchange 관리 센터](https://technet.microsoft.com/library/jj200743(v=exchg.150).aspx) 
- [Exchange Online의 모니터링, 보고 및 메시지 추적](https://technet.microsoft.com/library/jj200725(v=exchg.150).aspx)
- [Exchange Online에서 전자 메일 백업](https://technet.microsoft.com/library/dn440734(v=exchg.150).aspx) 
