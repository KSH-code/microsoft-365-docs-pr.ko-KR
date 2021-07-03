---
title: 파일럿 Microsoft 365 Defender 계획
description: 이해 관계자와 함께 Microsoft 365 Defender 계획을 세우고 기대치를 관리하고 성공적인 결과를 보장합니다.
keywords: Microsoft 365 Defender 파일럿, 파일럿 Microsoft 365 Defender 프로젝트 계획, 프로덕션 Microsoft 365 Defender 평가, Microsoft 365 Defender 파일럿 프로젝트, 사이버 보안, 고급 영구 위협, 엔터프라이즈 보안, 장치, 장치, ID, 사용자, 데이터, 응용 프로그램, 인시던트, 자동화된 조사 및 수정, 고급 헌팅
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: dolmont
author: DulceMontemayor
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365solution-scenario
- m365solution-pilotmtpproject
ms.topic: conceptual
ms.technology: m365d
ms.openlocfilehash: 6a52df8035ce6f84770a2d06c3b8c127e426622e
ms.sourcegitcommit: 4886457c0d4248407bddec56425dba50bb60d9c4
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/03/2021
ms.locfileid: "53286000"
---
# <a name="planning-your-pilot-microsoft-365-defender-project"></a>파일럿 Microsoft 365 Defender 계획 

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**적용 대상:**
- Microsoft 365 Defender

|![계획](../../media/phase-diagrams/1-planning.png)<br/>계획|[![준비](../../media/phase-diagrams/2-prepare.png)](prepare-m365d-eval.md)<br/>[준비](prepare-m365d-eval.md) | [![공격 시뮬레이션](../../media/phase-diagrams/3-simluate.png)](m365d-pilot-simulate.md)<br/>[공격 시뮬레이션](m365d-pilot-simulate.md) | [![닫기 및 요약](../../media/phase-diagrams/4-summary.png)](m365d-pilot-close.md)<br/>[닫기 및 요약](m365d-pilot-close.md)|
|--|--|--|--|
|*여기 있습니다!*| | | |

현재 계획 단계에 있습니다.

파일럿 프로젝트가 성공적이 되도록 철저하게 계획하고 이해 관계자로부터 승인을 받을 수 있도록 하는 것이 중요합니다. 계획 요소에는 범위 식별, 사용 사례, 요구 사항 및 성공 기준이 포함됩니다.

이 가이드에서는 파일럿 프로젝트를 계획하는 방법을 안내합니다. 

>[!IMPORTANT]
>최적의 결과를 얻기 위해 가능한 한 파일럿 지침을 따르세요.


## <a name="scope"></a>범위

파일럿 범위는 환경 및 허용되는 테스트 방법에 따라 테스트의 범위가 결정됩니다. 다음은 고려해야 할 몇 가지 범위 예제입니다.

- 끝점, 서버, 도메인 컨트롤러를 포함하는 개발 또는 테스트 환경
- Microsoft 365, Azure, Active Directory 서비스, 끝점 및 서버를 사용하여 프로덕션 환경

>[!NOTE]
>아직 정식 라이선스가 없는 경우 평가판 라이선스를 통해 파일럿 프로젝트를 [계획, 준비Microsoft 365 Defender](m365d-evaluation.md?ocid=cx-docs-MTPtriallab) 구성 및 실행하기 위한 평가판을 얻을 수 있습니다. 이해 관계자는 프로세스를 시작부터 완료까지 용이하게 하는 데 큰 역할을 합니다.

평가할 운영 체제 유형도 조직 구성에 따라 정의해야 합니다. Mac 끝점, [](/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-atp-mac#system-requirements) [Linux 서버,](/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-atp-linux#system-requirements)Windows 10 [끝점,](/windows/security/threat-protection/microsoft-defender-atp/minimum-requirements#supported-windows-versions) [Windows Server 2016.](/windows/security/threat-protection/microsoft-defender-atp/minimum-requirements#supported-windows-versions)

## <a name="use-cases"></a>사용 사례

사용 사례는 테스트할 도구가 의도한 사용자가 사용하는 방법에 대한 설명을 표현합니다. 이러한 스토리는 SOC 분석가와 같은 특정 개인의 시점에서 사용자 스토리로 공식화될 수 있습니다. 예를 들어 다음과 같습니다.

- SOC 분석가인 경우 네트워크의 장치, 사용자 및 사서함에서 경고 및 이벤트를 보고, 상관 관계하고, 평가하고 관리해야 합니다. [인시던트 관리]
- SOC 분석가인 경우 네트워크에서 악의적인 이벤트를 자동으로 조사하고 대응하는 도구와 프로세스가 있어야 합니다. [Auto IR]
- SOC 분석가인 I must search data from my environment to find known and potential threats, and suspicious activities. [고급 헌팅]

이러한 사용 사례는 정의된 범위의 매개 변수 내에 만들어야 합니다. 예를 들어 테스트 범위에 Microsoft Cloud App Security 도구에 대한 평가가 포함되어 있지 않은 경우 데이터 원본으로 이 기능을 사용하는 사례를 만들지 말아야 합니다.

## <a name="requirements"></a>요구 사항

사용 사례 목록에서 요구 사항을 만들 수 있습니다. 요구 사항에는 도구가 사용 사례를 충족하는 데 필요한 기능이 포함됩니다. 이러한 요구 사항은 구성 및 유지 관리, 통합 지원, 헌팅 기능 및 사용자 지정 경고 작성 능력과 같은 기능별 요구 사항과 같은 범주로 분류될 수 있습니다.

## <a name="test-plan"></a>테스트 계획

요구 사항에 따라 다양한 테스트 방법이 적절할 수 있습니다. 예를 들어 자동화된 재구성의 요구 사항을 평가해야 하는 경우 테스트 계획에는 자동 수정 작업 내에서 자동화된 수정 작업을 트리거하는 동작을 생성하는 단계를 포함해야 Microsoft 365 Defender. 특정 동작이나 공격을 감지해야 하는 경우 테스트에 더 많은 단계가 수반될 수 있습니다. 요구 사항을 정확하게 테스트하기 위한 계획을 세우는 것이 중요합니다.

## <a name="success-criteria"></a>성공 기준

성공 조건은 궁극적으로 테스트할 대상을 측정하기 위한 막대 집합입니다. 다른 도구에 Microsoft 365 Defender(또는 해당 기술에 대한 다른 기술)를 테스트하는 경우 도구에서 제공하는 값을 결정하기 위해 몇 가지 수량화 기준이 있어야 합니다. 범위, 요구 사항 및 테스트 계획에 따라 성공 기준에 따라 테스트 점수가 결정됩니다. 이 점수는 통과 또는 실패보다 작고 요구에 따라 가중 점수가 더 많이 주어야 합니다. 예를 들어 성공하려면 도구가 식별하는 특정 중요 영역에서 80% 이상의 점수를 득점해야 할 수 있습니다.

## <a name="scorecard"></a>Scorecard

계획의 모든 요소를 함께 가져오는 한 가지 방법은 점수 기록표를 만드는 것입니다. 아래 샘플 점수 기록표를 참조하세요.

| 사용 사례 | 요구 사항 | 구성 요구 사항 | 테스트 계획 | 예상 결과 | 테스트 상태 | 점수 | 참고 |
|:-------|:-------|:-------|:-------|:-------|:-------|:-------|:-------|
|인시던트 관리|- Microsoft 365 Defender </br></br>- Id에 대한 Microsoft Defender </br></br>- 끝점용 Microsoft Defender </br></br>- Microsoft Cloud App Security(선택 사항)|자세한 [내용은](m365d-evaluation.md?ocid=cx-docs-MTPtriallab) 준비, 설정 및 구성에 대한 선행 구성을 참조합니다. |[공격 시뮬레이션](m365d-pilot-simulate.md) <br></br>[인시던트 조사](./m365d-pilot-simulate.md#investigate-an-incident) |조사자는 인시던트의 범위와 영향을 이해하고 인시던트 관리||||
|AutoIR|- Microsoft 365 Defender </br></br>- Id에 대한 Microsoft Defender </br></br>- 끝점용 Microsoft Defender |자세한 [내용은](m365d-evaluation.md?ocid=cx-docs-MTPtriallab) 준비, 설정 및 구성에 대한 선행 구성을 참조합니다. <br>AutoIR 사용  |[공격 시뮬레이션](m365d-pilot-simulate.md) <br></br>[자동화된 조사](m365d-pilot-simulate.md#automated-investigation-and-remediation) |알림 및 인시던트는 알림 및 인시던트가 자동으로 Microsoft 365 Defender||||
|고급 헌팅|- Microsoft 365 Defender </br></br>- 끝점용 Microsoft Defender </br></br>-Microsoft Defender for Office 365 |자세한 [내용은](m365d-evaluation.md?ocid=cx-docs-MTPtriallab) 준비, 설정 및 구성에 대한 선행 구성을 참조합니다.|[고급 헌팅 시나리오](./m365d-pilot-simulate.md#advanced-hunting-scenario) |조사자는 고급 헌팅을 통해 데이터를 찾고 영향을 미치는 엔터티에 피벗하고 사용자 지정 검색을 만들어 데이터를 찾을 수 있습니다.||||

## <a name="next-step"></a>다음 단계

|![준비 단계](../../media/mtp/prep.png) <br>[준비 단계](prepare-m365d-eval.md) | 파일럿 Microsoft 365 Defender 준비
|:-------|:-----|
