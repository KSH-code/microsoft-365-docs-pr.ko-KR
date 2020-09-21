---
title: 파일럿 Microsoft Threat Protection 프로젝트 계획
description: 예상 성과를 관리 하 고 성공적인 결과를 확인 하기 위해 관련자를 사용 하 여 파일럿 Microsoft Threat Protection 프로젝트를 계획 합니다.
keywords: Microsoft 위협 보호 파일럿, 파일럿 Microsoft 위협 보호 프로젝트 계획, 마이크로소프트의 microsoft threat Protection, Microsoft Threat Protection 파일럿 프로젝트, 사이버 보안, advanced persistent 위협, 엔터프라이즈 보안, 장치, 장치, id, 사용자, 데이터, 응용 프로그램, 사건, 자동화 된 조사 및 개선, 고급 구하기
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: dolmont
author: DulceMontemayor
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
ms.openlocfilehash: 601e81fc5265fe2ec5f41009b6c4fa43c0c8233d
ms.sourcegitcommit: 7c0873d2a804f17697844fb13f1a100fabce86c4
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/18/2020
ms.locfileid: "47962612"
---
# <a name="planning-your-pilot-microsoft-threat-protection-project"></a>파일럿 Microsoft Threat Protection 프로젝트 계획 

**적용 대상:**
- Microsoft 위협 방지

파일럿 프로젝트가 성공적인 지 확인 하려면 처음에 관련자 로부터 철저 하 게 계획 하 고 승인을 받아야 합니다. 계획 요소에는 식별 범위, 사용 사례, 요구 사항 및 성공 기준이 포함 됩니다. 

이 가이드에서는 파일럿 프로젝트를 계획 하는 방법을 안내 합니다. 

>[!IMPORTANT]
>최적의 결과를 위해 파일럿 지침을 최대한 면밀 하 게 따릅니다.


## <a name="scope"></a>Scope

시험 운용 범위에 따라 사용자 환경 및 적합 한 테스트 방법에 따른 테스트 범위가 결정 됩니다. 다음은 고려해 야 할 몇 가지 예입니다.
- 끝점, 서버, 도메인 컨트롤러를 포함 하는 개발 또는 테스트 환경
- Microsoft 365, Azure, Active Directory 서비스, 끝점 및 서버가 포함 된 프로덕션 환경

>[!NOTE]
>아직 전체 라이선스가 없는 경우에는 평가판 라이선스를 통해 [Microsoft 위협 보호를 평가](https://aka.ms/mtp-trial-lab) 하 고 파일럿 프로젝트를 계획, 준비, 설정 및 구성 하 고 실행할 수 있습니다. 관련자는 시작부터 끝까지 쉽게 프로세스를 진행 하는 데 큰 역할을 합니다.

평가할 운영 체제의 유형도 조직 makeup을 기반으로 정의 해야 합니다. 여기에는 [Mac 끝점](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-atp-mac#system-requirements), [Linux 서버](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-atp-linux#system-requirements), [Windows 10 끝점](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/minimum-requirements#supported-windows-versions), [windows Server 2016](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/minimum-requirements#supported-windows-versions)이 포함 될 수 있습니다.

## <a name="use-cases"></a>사용 사례

사용 사례는 테스트 중인 도구를 의도 한 사용자가 소비 하는 방식에 대 한 설명을 나타냅니다. 이러한 요소는 SOC 분석가와 같은 특정 가상 사용자의 관점에서 사용자 스토리로 사용 될 수 있습니다. 예를 들어,
- SOC 분석가는 내 네트워크의 장치, 사용자 및 사서함에서 알림 및 이벤트를 확인, 상관 관계, 평가 및 관리 해야 합니다. [인시던트 관리]
- SOC 분석가는 내 네트워크의 악의적인 이벤트를 자동으로 조사 하 고 대응 하기 위해 도구와 프로세스를 수행 해야 합니다. [자동 IR]
- SOC 분석가는 필자의 환경에서 알려진 문제 및 잠재적인 위협과 의심 스러운 활동을 찾기 위해 환경의 데이터를 검색 해야 합니다. [고급 구하기]

이러한 사용 사례는 정의 된 범위의 매개 변수 내에서 만들어져야 합니다. 예를 들어 테스트 범위에 Microsoft Cloud App Security와 같은 도구 평가가 포함 되어 있지 않은 경우에는이를 데이터 원본으로 사용 하는 경우에는 해당 사례를 만들 수 없습니다.

## <a name="requirements"></a>요구 사항

사용 사례 목록에서 요구 사항 만들기를 시작할 수 있습니다. 요구 사항에는 도구에서 사용 사례를 충족 하기 위해 수행 해야 하는 기능이 포함 되어 있습니다. 이러한 요구 사항은 구성 및 유지 관리, 통합에 대 한 지원, 그리고 찾기 기능, 사용자 지정 알림 작성 기능과 같은 기능별 요구 사항 등의 범주로 나눌 수 있습니다.

## <a name="test-plan"></a>테스트 계획

요구 사항에 따라 다양 한 테스트 방법이 적합할 수 있습니다. 예를 들어 자동화 된 수정의 efficacy를 평가 해야 하는 경우 테스트 계획에는 Microsoft Threat Protection 내에서 자동화 된 재구성 작업을 트리거하는 동작을 생성 하기 위한 단계가 포함 되어야 합니다. 요구 사항으로 인해 특정 동작이 나 공격을 검색 해야 하는 경우 테스트에 더 많은 단계가 포함 될 수 있습니다. 요구 사항을 정확히 테스트할 수 있도록 계획을 수립 하는 것입니다.

## <a name="success-criteria"></a>성공 기준

성공 기준은 궁극적으로 테스트 대상에 대 한 기준으로 설정 됩니다. Microsoft Threat Protection (또는 해당 문제에 대 한 다른 기술)을 다른 도구나 자체에 대해 테스트할 지 여부에 관계 없이 도구에서 제공 하는 값을 결정 하려면 몇 가지 수량화 된 기준이 있어야 합니다. 범위, 요구 사항 및 테스트 계획에 따라 성공 기준은 테스트 점수를 결정 하는 것입니다. 이는 합격 또는 불합격이 더 적거나 필요에 따라 가중치 점수를 많이 가져야 합니다. 예를 들어, 확인이 성공 하려면 도구는 특정 중요 한 영역에서 80% 이상 점수를 두어야 할 수도 있습니다.

## <a name="scorecard"></a>표

계획의 모든 요소를 함께 가져오는 한 가지 방법으로 성과 기록표를 만들 수 있습니다. 아래의 샘플 성과 기록표를 참조 하세요.

|**사용 사례**|**요구 사항**|**구성 요구 사항**|**테스트 계획**|**예상 결과**|**테스트 상태**|**점수**|**참고**|
|:-------|:-------|:-------|:-------|:-------|:-------|:-------|:-------|
|사건 관리|-Microsoft Threat Protection </br></br>-Azure ATP </br></br>-Microsoft Defender ATP </br></br>-Microsoft Cloud App Security (선택 사항)|자세한 내용은 준비, 설정 및 구성을 위한 [필수 구성 요소](https://aka.ms/mtp-trial-lab) 를 참조 하세요. |[공격 시뮬레이트](mtp-pilot-simulate.md) <br></br>[문제 조사](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-pilot-simulate.md#investigate-an-incident) |Investigators는 사고의 범위와 영향을 이해 하 고 인시던트를 관리할 수 있습니다.||||
|AutoIR|-Microsoft Threat Protection </br></br>-Azure ATP </br></br>-Microsoft Defender ATP |자세한 내용은 준비, 설정 및 구성을 위한 [필수 구성 요소](https://aka.ms/mtp-trial-lab) 를 참조 하세요. <br>AutoIR 사용  |[공격 시뮬레이트](mtp-pilot-simulate.md) <br></br>[자동화 된 조사](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-pilot-simulate.md#automated-investigation-and-remediation) |Microsoft Threat Protection에서 경고 및 인시던트가 자동으로 재구성 됨||||
|고급 헌팅|-Microsoft Threat Protection </br></br>-Microsoft Defender ATP </br></br>-Office 365 ATP   |자세한 내용은 준비, 설정 및 구성을 위한 [필수 구성 요소](https://aka.ms/mtp-trial-lab) 를 참조 하세요.|[고급 구하기 시나리오](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-pilot-simulate.md#advanced-hunting-scenario) |Investigators에서는 고급 검색을 통해 데이터를 찾고, 영향을 받는 엔터티에 대 한 피벗을 하며, 사용자 지정 감지를 만들면||||



## <a name="next-step"></a>다음 단계
|![준비 단계](../../media/prepare.png) <br>[준비 단계](prepare-mtpeval.md) | Microsoft Threat Protection 파일럿 환경 준비
|:-------|:-----|
