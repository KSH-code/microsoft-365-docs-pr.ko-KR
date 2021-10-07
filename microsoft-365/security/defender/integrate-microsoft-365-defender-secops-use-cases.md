---
title: 5단계. 사용 사례 개발 및 테스트
description: 보안 운영에 통합할 때 사용 사례를 개발하고 테스트하는 Microsoft 365 Defender 기본입니다.
keywords: 인시던트, 경고, 조사, 상관 관계, 공격, 장치, 사용자, ID, ID, 사서함, 전자 메일, 365, microsoft, m365, 인시던트 대응, 사이버 공격, 보안 작업, soc
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.technology: m365d
ms.openlocfilehash: 79a5b1ea36e6a18d880d7fec7681f826cacac48f
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/06/2021
ms.locfileid: "60158985"
---
# <a name="step-5-develop-and-test-use-cases"></a>5단계. 사용 사례 개발 및 테스트

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**적용 대상:**
- Microsoft 365 Defender

SOC(보안 Microsoft 365 Defender 센터)에 배포하는 권장 방법은 SOC 팀의 현재 도구, 프로세스 및 기술 집합에 따라 달라 하게 됩니다. 수백 개의 보안 원본이 아닌 경우 수십만 개의 데이터가 들어오기 때문에 플랫폼 전체에서 사이버 방조를 유지 관리하기가 어려울 수 있습니다. 

보안 도구는 상호 연결됩니다. 보안 기술에서 한 기능을 켜거나 프로세스를 변경하면 다른 기능이 중단될 수 있습니다. 이러한 이유로 SOC 팀에서 사용 사례를 정의하고 우선 순위를 지정하는 방법을 공식화하는 것이 좋습니다. 사용 사례는 다양한 팀에서 SOC 작업에 대한 요구 사항을 정의하고 프로세스를 테스트하는 데 도움이 됩니다. 또한 메트릭을 캡처하는 방법을 만들어 올바른 역할과 작업의 혼합이 올바른 기술에 맞게 올바른 팀에 정렬되어 있는지를 확인할 수 있습니다. 

## <a name="develop-and-formalize-use-case-process"></a>사용 사례 프로세스 개발 및 공식화

SOC는 SOC 감독 팀에서 규제하는 사용 사례를 개발하기 위한 높은 수준의 표준 및 프로세스를 정의해야 합니다. SOC 감독 팀은 비즈니스, IT, 법률, HR 및 기타 그룹과 함께 작업하여 결국 SOC 팀의 런북 및 플레이북으로 이어지기 위한 SOC 사용 사례의 우선 순위를 지정해야 합니다. 사용 사례의 우선 순위는 규정 준수 또는 개인 정보 보호와 같은 목표를 기반으로 합니다.

사용 사례 개발과 관련된 SOC 감독 활동은 다음과 같습니다. 

- 요구 사항
- 직원 교육 또는 교육 요구
- 소프트웨어 라이선스
- 공급업체 계약
- 계획 관리
- 사용 사례 레지스트리 유지 관리
- 템플릿 유지 관리/업데이트

런북 및 플레이북 만들기 프로세스를 용이하게 만들 수 있도록 사용 사례 결정 트리를 만드십시오. 이 그림은 예를 보여줍니다.

:::image type="content" source="../../media/integrate-microsoft-365-defender-secops/use-case-decision-process.png" alt-text="사용 사례 결정 프로세스.":::

높은 수준의 사용 사례 표준을 정의하고 승인한 후 다음 단계는 실제 사용 사례를 만들고 테스트하는 것입니다. 다음 섹션에서는 피싱 방지 및 위협 및 취약점 검사 시나리오를 예로 사용 합니다.

## <a name="use-case-example-1-new-phishing-variant"></a>사용 사례 예제 1: 새 피싱 변형

사용 사례를 만드는 첫 번째 단계는 스토리보드를 사용하여 워크플로를 개요화하는 것입니다. 다음은 위협 인텔리전스 팀에 대한 새로운 피싱 악용 알림을 위한 고급 스토리 보드의 예입니다.
 
:::image type="content" source="../../media/integrate-microsoft-365-defender-secops/example-use-case-workflow-storyboard-phishing.png" alt-text="피싱 방지 캠페인에 대한 사용 사례 워크플로의 예":::

### <a name="invoke-the-use-case-workflow-for-example-1"></a>예제 1과 같은 사용 사례 워크플로 호출

스토리보드가 승인되면 다음 단계는 사용 사례 워크플로를 호출하는 것입니다. 다음은 피싱 방지 캠페인의 예제 프로세스입니다. 
 
:::image type="content" source="../../media/integrate-microsoft-365-defender-secops/example-detailed-use-case-workflow-phishing.png" alt-text="피싱 방지 캠페인에 대한 자세한 사용 사례 워크플로의 예":::

## <a name="use-case-example-2-threat-and-vulnerability-scanning"></a>사용 사례 예제 2: 위협 및 취약성 검사

사용 사례를 사용할 수 있는 또 다른 시나리오는 위협 및 취약점 검사용입니다. 이 예에서 SOC는 자산 검사가 포함된 승인된 프로세스를 통해 자산에 대해 위협 및 취약성을 수정해야 합니다. 

다음은 자산의 모든 자산에 대한 고급 스토리보드의 위협 및 취약성 관리 예제입니다.
 
:::image type="content" source="../../media/integrate-microsoft-365-defender-secops/example-use-case-workflow-storyboard-tvm.png" alt-text="예제 사용 사례 워크플로를 위협 및 취약성 관리.":::

### <a name="invoke-the-use-case-workflow-for-example-2"></a>예제 2와 같은 사용 사례 워크플로 호출

다음은 위협 및 취약점 검사에 대한 예제 프로세스입니다.
 
:::image type="content" source="../../media/integrate-microsoft-365-defender-secops/example-detailed-use-case-workflow-tvm.png" alt-text="자세한 사용 사례 워크플로의 예는 위협 및 취약성 관리.":::
 
### <a name="analyze-the-use-case-output-and-lessons-learned"></a>사용 사례 출력 및 학습된 교훈 분석

사용 사례를 승인하고 테스트한 후 보안 팀 간의 격차를 사용자, 프로세스 및 관련 기술과 함께 Microsoft 365 Defender 식별해야 합니다. Microsoft 365 Defender 기술을 분석하여 원하는 결과를 달성할 수 있는지 여부를 결정해야 합니다. 검사 목록 또는 행렬을 통해 추적할 수 있습니다. 

예를 들어 피싱 방지 시나리오 예제에서 SOC 팀은 이 표에서 검색을 할 수 있습니다.


| SOC 팀 | 요구 사항 | 요구 사항을 충족하는 사람 | 요구 사항을 충족하는 프로세스 | 관련 기술 | 식별된 갭 | 사용 사례 변경 로그 | 제외(Y/N) |
|:-------|:-----|:-------|:-------|:-------|:-----|:-------|:-------|
| 위협 인텔리전스 및 분석 팀 | 데이터 원본이 위협 인텔리전스 엔진을 제대로 공급하고 있습니다. | 위협 인텔리전스 분석가/엔지니어 | 승인된 원본의 위협 인텔리전스 트리거가 설정된 데이터 피드 요구 사항 | Id용 Microsoft Defender, 끝점용 Microsoft Defender | 위협 인텔리전스 팀에서 자동화 스크립트를 사용하여 위협 인텔리전스 엔진과 Microsoft 365 Defender API를 연결하지 않은 경우 | 위협 Microsoft 365 Defender 데이터 원본으로 추가 <BR> <BR> 사용 사례 실행 책 업데이트 | N |
| 모니터링 팀 | 데이터 원본이 모니터링 대시보드를 제대로 공급하고 있습니다. | 계층 1,2 SOC 분석가 모니터링 & 경고 | 보안 및 준수 센터 보안 & 보고를 위한 워크플로 | [보안 및 준수 & 알림](/microsoft-365/security/office-365-security/alerts)  <br><br> 보안 점수 모니터링  | SOC 분석가가 보안 점수를 개선하기 위해 새로운 피싱 변형 검색을 성공적으로 보고하는 메커니즘이 없음 <br><br> [보안 및 준수 & 보고](/microsoft-365/security/office-365-security/reports-and-insights-in-security-and-compliance)| 보고 워크플로에 보안 점수 개선을 추적하는 프로세스 추가 | N | 
| 엔지니어링 및 SecOps 팀 | SOC 팀 런북에서 변경 제어 업데이트 | 계층 2 SOC 엔지니어 | SOC 팀 런북에 대한 제어 알림 절차 변경 | 보안 장치에 승인된 변경 내용 | SOC Microsoft 365 Defender 연결에 대한 변경 내용을 승인해야 합니다. | SOC Microsoft Cloud App Security, ID용 Defender, 끝점용 Defender, 보안 & 준수 센터 추가 | Y |
|||||||||

또한 SOC 팀은 위에 설명된 위협 및 취약성 관리 시나리오와 관련하여 아래 표에 설명된 검색을 만들 수 있습니다.

| SOC 팀 | 요구 사항 | 요구 사항을 충족하는 사람 | 요구 사항을 충족하는 프로세스 | 관련 기술 | 식별된 갭 | 사용 사례 변경 로그 | 제외(Y/N) |
|:-------|:-----|:-------|:-------|:-------|:-----|:-------|:-------|
| SOC 감독 | 승인된 네트워크에 연결된 모든 자산이 식별되고 분류됩니다. | SOC 감독, BU 소유자, 응용 프로그램 소유자, IT 자산 소유자 등 | 위험에 따라 자산 범주 및 특성을 검색하고 나열하는 중앙 집중식 자산 관리 시스템입니다. | ServiceNow 또는 기타 자산. <br><br>[Microsoft 365 장치 인벤토리](/security/defender-endpoint/device-discovery) | 자산의 70%만 검색했습니다. Microsoft 365 Defender 자산에 대한 수정 추적만 적용 | 자산 수명 주기 관리 서비스를 완성하여 100% Microsoft 365 Defender 보장 | N |
| SecOps & 엔지니어링 Teams | 자산의 높은 영향 및 중요 취약성은 정책에 따라 수정됩니다. | SecOps 엔지니어, SOC 분석가: 취약성 & 준수, 보안 엔지니어링 | 고위험 및 위험 취약성을 분류하기 위한 정의된 프로세스 | [위협 및 취약성 관리 대시보드](/microsoft-365/security/defender-endpoint/next-gen-threat-and-vuln-mgt) | Endpoint용 Defender는 수정 계획이나 Microsoft 권장 활동 구현이 없는 높은 영향력의 높은 경고 장치를 확인했습니다. | 정책당 30일 이내에 재구성 활동이 필요한 경우 자산 소유자에게 알리기 위한 워크플로를 추가합니다. 티켓 시스템을 구현하여 자산 소유자에게 수정 단계를 알릴 수 있습니다. | N |
| 모니터링 Teams | 위협 및 취약성 상태는 회사 인트라넷 포털을 통해 보고됩니다. | 계층 2 SOC 분석가 | 자산의 재구성 진행 Microsoft 365 Defender 보고서의 자동 생성 보고서 | [보안 및 준수 & 알림](/microsoft-365/security/office-365-security/alerts) <br><br> 보안 점수 모니터링 | 자산의 위협 및 취약성 상태에 대한 보기 또는 대시보드 보고서가 자산 소유자에게 전달되지 않습니다. | 자동화 스크립트를 만들어 조직에 대한 고위험 및 중요한 자산 취약성 수정 상태를 채우는 데 사용할 수 있습니다. | N |
|||||||||

이 예제 사용 사례에서 테스트는 각 팀의 책임에 대한 기준으로 설정된 SOC 팀의 요구 사항에서 몇 가지 차이를 나타났습니다. 사용 사례 검사 목록은 SOC 팀이 새로운 또는 기존 SOC 요구 사항과의 통합을 Microsoft 365 Defender 수 있도록 하는 데 필요한 한 포괄적일 수 있습니다. 이 프로세스는 다시 시작될 것이기 때문에 사용 사례 개발 프로세스 및 사용 사례 출력 콘텐츠는 자연스럽게 학습된 교훈으로 SOC의 런북을 업데이트하고 완성하는 데 활용됩니다.

## <a name="update-production-runbooks-and-playbooks"></a>프로덕션 런북 및 플레이북 업데이트

모든 공백에 대해 사용 사례 테스트를 수정한 후 학습된 교훈과 수집된 메트릭을 SOC 팀의 프로덕션 런북(운영 프로세스) 및 플레이북(인시던트 대응 및 에스컬레이터 절차)에 통합할 수 있습니다. 

SOC 팀 런북 및 플레이북의 유지 관리는 다양한 방법으로 구성할 수 있습니다. 각 SOC 팀이 자체적으로 담당하거나 모든 팀이 중앙 저장소에서 공유할 수 있는 단일 중앙 집중식 버전이 있을 수 있습니다. 개별 조직에 대한 런북 및 플레이북 관리는 크기, 기술, 역할 및 업무의 세분화에 기반합니다. 런북이 업데이트된 후 재생 문서 업데이트 프로세스가 따라야 합니다. 

## <a name="use-a-standard-framework-for-escalation"></a>에스컬레이터에 표준 프레임워크 사용

Playbook은 사용 사례의 성공적인 통합 및 테스트에 따라 실제 이벤트가 발생할 때 SOC 팀이 따라야 하는 단계입니다. 따라서 SOC는 업계 최고의 인시던트 대응 표준 중 하나인 [NIST](https://nvlpubs.nist.gov/nistpubs/SpecialPublications/NIST.SP.800-61r2.pdf) 인시던트 대응 표준과 같이 인시던트 대응에 대한 공식화된 접근 방식을 따라야 합니다.

NIST 4단계 인시던트 대응 프로세스에는 다음 네 단계가 포함됩니다.

1.  준비
2.  검색 및 분석
3.  포함, 제거 및 복구
4.  인시던트 사후 활동

### <a name="example-tracking-preparation-phase-activity"></a>예: 준비 단계 활동 추적

에스컬레이터 재생북의 핵심 토대 중 하나는 각 SOC 팀이 이벤트 또는 인시던트 이전, 중 및 이후에 어떤 작업을 해야 하는지 모호하지 않도록 하는 것입니다. 따라서 단계별 지침을 나열하는 것이 좋습니다. 

예를 들어 준비 단계에서는 작업의 if/then 또는 XoR 행렬을 포함할 수 있습니다. 새 피싱 변형 예제 사용 사례의 경우 이러한 행렬은 다음과 같이 표시될 수 있습니다.

| 에스컬ation이 Warranted인 이유는 무엇입니까? | 다음 단계 |
|:-------|:-----|
| 중요 트리거로 평가된 SOC 모니터링의 경고 > **500/시간**  | Go to Playbook A, Section 2, Activity 5 (with a link to the playbook section) |
| eCommerce에서 잠재적인 DDoS 공격을 보고했습니다. | Playbook B-Section C, Activity 19 호출(Playbook 섹션에 대한 링크 사용) |
| 임원은 의심스러운 전자 메일을 스피어 피싱 시도로 보고했습니다. | Go to Playbook 5, Section 2, Activity 5 (with a link to the playbook section) |
|||

준비 단계를 실행한 후 조직은 NIST에 설명된 나머지 단계를 호출해야 합니다.

- 검색 및 분석
- 포함, 제거 및 복구
- 인시던트 사후 활동 

## <a name="next-step"></a>다음 단계

[6단계. SOC 유지 관리 작업 확인](integrate-microsoft-365-defender-secops-tasks.md)

