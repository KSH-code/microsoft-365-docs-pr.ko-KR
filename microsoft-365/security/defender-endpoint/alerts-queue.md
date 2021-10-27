---
title: 엔드포인트용 Microsoft Defender 경고 큐 보기 및 구성
description: Microsoft Defender for Endpoint 경고 큐의 작동 방식과 경고 목록을 정렬 및 필터링하는 방법에 대해 자세히 알아보습니다.
keywords: 경고, 큐, 경고 큐, 정렬, 순서, 필터링, 경고 관리, 신규, 진행 중, 해결된, 최근, 큐의 시간, 심각도, 기간, Microsoft 위협 전문가 경고
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.date: 03/27/2020
ms.technology: mde
ms.openlocfilehash: 39c456b3f7ad31181d47318570176710840ad8b2
ms.sourcegitcommit: da11ffdf7a09490313dfc603355799f80b0c60f9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/26/2021
ms.locfileid: "60587984"
---
# <a name="view-and-organize-the-microsoft-defender-for-endpoint-alerts-queue"></a>엔드포인트용 Microsoft Defender 경고 큐 보기 및 구성

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**적용 대상:**
- [엔드포인트용 Defender](https://go.microsoft.com/fwlink/?linkid=2154037)

> Endpoint용 Defender를 경험하고 싶나요? [무료 평가판을 신청하세요.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-alertsq-abovefoldlink)

경고 **큐에는** 네트워크의 장치에서 플래그가 지정된 경고 목록이 표시됩니다. 기본적으로 큐에는 그룹 보기에서 지난 30일 동안의 경고가 표시됩니다. 가장 최근 경고는 가장 최근 경고를 먼저 볼 수 있도록 목록 맨 위에 표시됩니다.

> [!NOTE]
> 자동화된 조사 및 수정을 통해 경고 큐가 크게 줄어들어 보안 운영 전문가가 보다 정교한 위협 및 기타 높은 가치의 이니셔티브에 집중할 수 있습니다. 경고에 지원되는 운영 체제가 있는 장치의 자동화된 조사에 지원되는 엔터티(예: 파일)가 포함되어 있는 경우 자동화된 조사 및 수정이 시작될 수 있습니다. 자동화된 조사에 대한 자세한 내용은 [Overview of Automated investigations를 참조하십시오.](automated-investigations.md)

경고 큐 보기를 사용자 지정하기 위해 선택할 수 있는 몇 가지 옵션이 있습니다.

위쪽 탐색에서 다음을 할 수 있습니다.

- 그룹 보기 또는 목록 보기 선택
- 열을 추가 또는 제거하기 위해 열 사용자 지정
- 페이지당 표시할 항목 선택
- 페이지 간 탐색
- 필터 적용

![경고 큐의 이미지입니다.](images/alerts-queue-list.png)

## <a name="sort-filter-and-group-the-alerts-queue"></a>경고 큐 정렬, 필터링 및 그룹화

다음 필터를 적용하여 경고 목록을 제한하고 경고를 보다 집중적으로 볼 수 있습니다.

### <a name="severity"></a>심각도

경고 심각도|설명
---|---
높음 <br> (빨강)|일반적으로 APT(고급 영구 위협)와 관련된 경고입니다. 이러한 경고는 장치에 노출될 수 있는 손상의 심각도로 인한 높은 위험을 나타냅니다. 몇 가지 예로는 자격 증명 도난 도구 활동, 그룹과 연결되지 않은 랜섬웨어 활동, 보안 센서 변조 또는 악의적인 공격을 나타내는 모든 악의적인 활동이 있습니다.
보통 <br> (주황색)|APT(Advanced Persistent Threat)의 일부일 수 있는 끝점 감지 및 위반 후 동작에 대한 대응 경고입니다. 여기에는 공격 단계의 일반적인 관찰된 동작, 변이적 레지스트리 변경, 의심스러운 파일 실행이 포함됩니다. 일부는 내부 보안 테스트의 일부일 수 있습니다. 또한 고급 공격의 일부일 수 있는 조사가 필요합니다.
낮음 <br> (노란색)|보행 맬웨어와 관련된 위협에 대한 경고입니다. 예를 들어 해킹 도구, 맬웨어가 아닌 해킹 도구(예: 탐색 명령 실행, 로그 지우기 등)는 조직을 대상으로 하는 고급 위협을 나타내지 않습니다. 조직의 사용자가 격리된 보안 도구 테스트에서 제공될 수도 있습니다.
정보 <br> (회색)|네트워크에 해로운 것으로 간주되지는 않지만 잠재적인 보안 문제에 대한 조직의 보안 인식을 강화할 수 있는 경고입니다.

#### <a name="understanding-alert-severity"></a>경고 심각도 이해

Microsoft Defender 바이러스 백신 (Microsoft Defender AV) 및 Endpoint 경고 심각도에 대한 Defender는 서로 다른 범위를 나타내기 때문에 다릅니다.

Microsoft Defender 바이러스 백신 위협 심각도는 감지된 위협(맬웨어)의 절대 심각도를 나타내며 감염된 경우 개별 장치에 대한 잠재적인 위험에 따라 할당됩니다.

끝점 경고 심각도에 대한 Defender는 감지된 동작의 심각도, 장치에 대한 실제 위험은 나타내지만 더 중요한 것은 조직에 대한 잠재적 위험을 나타내는 것입니다.

예를 들면 다음과 같습니다.

- 완전히 방지되고 장치를 감염시킬 수 없는 Microsoft Defender 바이러스 백신 감지된 위협에 대한 끝점용 Defender 경고의 심각도는 실제 손상이 아니기 때문에 "정보"로 분류됩니다.
- 실행 중 상업용 맬웨어에 대한 경고가 감지되지만 Microsoft Defender AV에서 차단 및 수정한 경고는 개별 장치에 일부 손상을 입히지만 조직에 위협을 일으킬 수 있기 때문에 "낮음"으로 분류됩니다.
- 실행 중 감지된 맬웨어에 대한 경고로, 개별 장치뿐만 아니라 조직에 위협이 될 수 있습니다. 이는 결국 차단된 경우와 관계없이 "중간" 또는 "높음"으로 순위가 올 수 있습니다.
- 차단되거나 수정되지 않은 의심스러운 동작 경고는 동일한 조직 위협 고려 사항을 따라 "낮음", "보통" 또는 "높음"으로 순위가 설정됩니다.

#### <a name="understanding-alert-categories"></a>경고 범주 이해

MITRE ATT 및 CK 매트릭스에서 [](https://attack.mitre.org/tactics/enterprise/) 엔터프라이즈 공격 전략에 맞게 경고 [범주를&있습니다.](https://attack.mitre.org/) 새 범주 이름은 모든 새 경고에 적용됩니다. 기존 경고는 이전 범주 이름을 보관합니다.

아래 표에는 현재 범주와 이러한 범주가 이전 범주에 일반적으로 매핑된 방식이 나열되어 있습니다.

|새 범주|API 범주 이름|위협 활동 또는 구성 요소 검색|
|---|---|---|
|컬렉션|컬렉션|유출을 위한 데이터 찾기 및 수집|
|명령 및 제어|CommandAndControl|데이터를 릴레이하거나 명령을 수신하기 위해 공격자가 제어하는 네트워크 인프라에 연결합니다.|
|자격 증명 액세스|CredentialAccess|유효한 자격 증명을 획득하여 네트워크의 장치 및 기타 리소스에 대한 제어를 확장합니다.|
|방어 공격|DefenseEvasion|보안 앱 끄기, 삽입 삭제, 루트릿 실행 등 보안 제어 방지|
|검색|검색|관리자 컴퓨터, 도메인 컨트롤러 및 파일 서버와 같은 중요한 장치 및 리소스에 대한 정보 수집|
|실행|실행|RATS 및 백도어를 비롯한 공격자 도구 및 악성 코드 시작|
|유출|유출|네트워크에서 공격자가 제어하는 외부 위치로 데이터 추출|
|Exploit|Exploit|악용 코드 및 가능한 악용 활동.|
|초기 액세스|InitialAccess|일반적으로 암호 추측, 악용 또는 피싱 전자 메일과 관련된 대상 네트워크에 대한 초기 항목을 얻습니다.|
|측면 이동|LateralMovement|대상 네트워크의 장치 간을 이동하여 중요한 리소스에 도달하거나 네트워크 지속성 확보|
|맬웨어|맬웨어|백도어, 트로이 및 기타 유형의 악성 코드.|
|지속성|지속성|자동 시작 ASEP(Extensibility Points)를 만들어 활성 상태로 유지하고 시스템 다시 시작을 계속할 수 있습니다.|
|권한 에스컬레이터|PrivilegeEscalation|권한이 부여된 프로세스 또는 계정의 컨텍스트에서 실행하여 코드에 대한 더 높은 권한 수준을 얻습니다.|
|랜섬웨어|랜섬웨어|파일을 암호화하고 액세스를 복원하기 위해 지급을 부수는 맬웨어입니다.|
|의심스러운 활동|SuspiciousActivity|맬웨어 활동 또는 공격의 일부일 수 있는 이상적 활동입니다.|
|사용자 동의 없이 설치된 소프트웨어|UnwantedSoftware|생산성 및 사용자 환경에 영향을 미치는 낮은 평판 앱 및 앱 잠재적으로 원치 않는 응용 프로그램(PUAS)으로 검색되었습니다.|

### <a name="status"></a>상태

상태에 따라 경고 목록을 제한할 수 있습니다.

### <a name="investigation-state"></a>조사 상태

자동화된 조사 상태와 대응합니다.

### <a name="category"></a>Category

특정 유형의 악의적인 활동을 표시하도록 큐를 필터링하도록 선택할 수 있습니다.

### <a name="assigned-to"></a>할당된 사용자

사용자에게 할당된 경고 표시 또는 자동화 중 선택할 수 있습니다.

### <a name="detection-source"></a>검색 원본

경고 검색을 트리거한 원본을 선택합니다. Microsoft 위협 전문가 미리 보기 참가자는 이제 새로운 위협 전문가 관리 헌팅 서비스의 검색을 필터링하고 볼 수 있습니다.

> [!NOTE]
> 바이러스 백신 필터는 장치가 기본 실시간 보호 Microsoft Defender 바이러스 백신 맬웨어 방지 제품으로 사용하는 경우만 표시됩니다.

|검색 원본|API 값|
|---|---|
|제3자 센서|ThirdPartySensors|
|바이러스 검사|WindowsDefenderAv|
|자동화된 조사|AutomatedInvestigation|
|사용자 지정 검색|CustomDetection|
|사용자 지정 TI|CustomerTI|
|EDR|WindowsDefenderAtp|
|Microsoft 365 Defender|MTP|
|Office 365용 Microsoft Defender|OfficeATP|
|Microsoft 위협 전문가|ThreatExperts|
|SmartScreen|WindowsDefenderSmartScreen|

### <a name="os-platform"></a>OS 플랫폼

조사할 OS 플랫폼을 선택하여 경고 큐 보기를 제한합니다.

### <a name="device-group"></a>장치 그룹

검사할 특정 장치 그룹이 있는 경우 그룹을 선택하여 경고 큐 보기를 제한할 수 있습니다.

### <a name="associated-threat"></a>관련 위협

이 필터를 사용하여 높은 프로필 위협과 관련된 경고에 집중할 수 있습니다. 위협 분석에서 프로필이 높은 위협의 전체 [목록을 볼 수 있습니다.](threat-analytics.md)

## <a name="related-topics"></a>관련 항목

- [끝점 경고에 대한 Microsoft Defender 관리](manage-alerts.md)
- [끝점 경고에 대한 Microsoft Defender 조사](investigate-alerts.md)
- [끝점 경고에 대한 Microsoft Defender와 관련된 파일 조사](investigate-files.md)
- [Microsoft Defender for Endpoint Devices 목록에서 장치 조사](investigate-machines.md)
- [끝점 경고에 대한 Microsoft Defender와 연결된 IP 주소 조사](investigate-ip.md)
- [끝점 경고에 대한 Microsoft Defender와 연결된 도메인 조사](investigate-domain.md)
- [끝점용 Microsoft Defender에서 사용자 계정 조사](investigate-user.md)
