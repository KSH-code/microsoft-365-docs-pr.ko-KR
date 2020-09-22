---
title: 파일럿 Microsoft Threat Protection 프로젝트 실행
description: MTP (Microsoft Threat Protection)의 이점과 채택을 효과적으로 파악 하기 위해 프로덕션 환경에서 파일럿 Microsoft 위협 보호 프로젝트를 실행 합니다.
keywords: Microsoft 위협 보호 파일럿, 파일럿 Microsoft 위협 보호 프로젝트를 실행 하 고, microsoft threat protection 파일럿 프로젝트, 사이버 보안, 고급 영구 위협, 엔터프라이즈 보안, 장치, 장치, id, 사용자, 데이터, 응용 프로그램, 인시던트, 자동화 된 조사 및 업데이트, 고급 구하기 등을 평가 합니다.
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
ms.openlocfilehash: 88d92558d86e0aa2e90ef04d88a3cd4676386f15
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/22/2020
ms.locfileid: "48195630"
---
# <a name="run-your-pilot-microsoft-threat-protection-project"></a>파일럿 Microsoft Threat Protection 프로젝트 실행 

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**적용 대상:**
- Microsoft 위협 방지

MTP (Microsoft Threat Protection)의 이점과 채택을 효과적으로 확인 하기 위해 파일럿 프로젝트를 실행할 수 있습니다. 프로덕션 환경에서 Microsoft Threat Protection을 사용 하도록 설정 하 고 정의 된 사용 사례를 시작 하기 전에이 파일럿 프로젝트에서 수행 해야 하는 작업 및 성공 기준을 결정 하는 계획 프로세스를 진행 하는 것이 가장 좋습니다. 


## <a name="how-to-use-this-pilot-playbook"></a>이 파일럿 playbook를 사용 하는 방법

이 가이드에서는 파일럿 프로젝트를 설정 하는 방법에 대 한 Microsoft 위협 보호 및 단계별 지침의 개요를 제공 합니다. 

![Microsoft Threat Protection 파일럿 실행 단계](../../media/pilotphases.png)

다음의 시간 표시 막대는 환경에 적절 한 리소스가 있는 경우에 따라 달라 집니다. 일부 검색 및 워크플로에는 다른 일부 사용자 보다 더 많은 학습 시간이 필요할 수 있습니다.

![Microsoft Threat Protection 파일럿 실행을 위한 샘플 시간 표시줄](../../media/pilotimeline.png)

>[!IMPORTANT]
>최적의 결과를 위해 파일럿 지침을 최대한 면밀 하 게 따릅니다.


### <a name="pilot-playbook-phases"></a>파일럿 playbook 단계 

Microsoft Threat Protection 파일럿을 실행 하는 데는 다음과 같은 네 가지 단계가 있습니다.

|단계 | 설명 | 
|:-------|:-----|
| ![계획](../../media/mtp/plan.png)<br>[계획](mtp-pilot-plan.md)| Microsoft Threat Protection 파일럿 프로젝트를 실행 하기 전에 고려해 야 할 사항에 대해 알아봅니다. <br><br>-범위 <br> -사용 사례 <br>- 요구 사항 <br>-테스트 계획 <br> -성공 조건 <br> -성과 기록표 
| ![미리](../../media/prepare.png) <br>[미리](mtp-evaluation.md)|  Microsoft 365 보안 센터에 액세스 하 여 마이크로소프트 Threat Protection 파일럿 환경을 설정 합니다. 다음을 안내 합니다.<br><br>-관련자 식별 및 파일럿에 대 한 승인 찾기 <br> -환경 고려 사항 <br>-액세스 <br>-Azure Active Directory 설치 <br> -구성 순서 <br> -Microsoft 365 E5 평가판 등록 <br> -도메인 구성 <br>-Microsoft 365 E5 라이선스 할당 <br> -포털에서 설치 마법사 완료|
| ![공격 시뮬레이션](../../media/mtp/run-sim.png) <br>[공격 시뮬레이션](mtp-pilot-simulate.md) | 공격을 시뮬레이트하기 위해 다음을 안내 합니다.<br><br>-테스트 환경 요구 사항 확인 <br>-시뮬레이션을 실행 합니다. <br>-문제 조사 <br>-인시던트를 해결 합니다. 
| ![맺음말 및 요약](../../media/mtp/close.png) <br>[맺음말 및 요약](mtp-pilot-close.md) | 프로세스의 끝에 도달 하면 다음을 안내 합니다.<br><br>-최종 출력으로 이동<br>-결과를 이해 관계자에 게 제공 <br>-사용자 의견 제공 <br>-다음 단계 수행 

## <a name="next-step"></a>다음 단계
|![계획 단계](../../media/mtp/plan.png) <br>[계획 단계](mtp-pilot-plan.md) | Microsoft Threat Protection 파일럿 프로젝트 계획 
|:-------|:-----|
