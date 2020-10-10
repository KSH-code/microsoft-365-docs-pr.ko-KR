---
title: Microsoft Threat Protection 사용 설정
description: Microsoft Threat Protection 평가판 랩 또는 파일럿 환경을 설정 하 여 장치, id, 데이터 및 응용 프로그램을 보호 하도록 설계 된 위협 방어 보호 솔루션을 통해 조직에서 도움을 얻을 수 있는 방법을 확인 하세요.
keywords: Microsoft Threat Protection 평가판, microsoft threat protection 체험, microsoft threat protection 평가 랩, microsoft 위협의 보호 파일럿, 사이버 보안, 고급 영구 위협, 엔터프라이즈 보안, 장치, 장치, id, 사용자, 데이터, 응용 프로그램, 사건, 자동화 된 조사 및 개선, 고급 구하기
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
ms.collection:
- M365-security-compliance
- m365solution-overview
- m365solution-evalutatemtp
ms.topic: conceptual
ms.openlocfilehash: 489ce48be4d995d7e91e2559311d7e619530ba4c
ms.sourcegitcommit: a83acd5b9eeefd2e20e5bac916fe29d09fb53de9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/10/2020
ms.locfileid: "48418088"
---
# <a name="create-a-microsoft-threat-protection-trial-lab-or-pilot-environment"></a>Microsoft Threat Protection 평가판 랩 또는 파일럿 환경 만들기 

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**적용 대상:**
- Microsoft 위협 방지

이 시험 운용 랩 또는 파일럿 환경을 만드는 목적은 검색, 예방, 조사 및 조직에서 사용할 수 있는 응답에 대 한 Microsoft 위협 보호의 포괄적이 고 통합 된 기능을 보여 주기 위한 것입니다. 

이 가이드에서는 권장 되는 배포 경로를 기반으로 Microsoft Threat Protection 평가를 시작 하는 단계를 안내 합니다. 목표는 평가판 계정을 사용 하는 경우 랩 환경에서 통합 Microsoft 위협 보호 서비스를 설정 하는 데 도움이 되거나 정식 라이선스를 사용 하는 경우 프로덕션 환경의 파일럿 환경에 설치 하는 것입니다. 결과는 조직의 보안 솔루션 의사 결정권자에 게 보안 작업 사용 사례를 제공 하는 데 유용 합니다. 공격 시뮬레이션을 실행 하 고 결과에 만족 하면 조직의 Microsoft 기술 영업 전문가 또는 전문가를 위한 도움을 사용 하 여 조직에서이를 완벽 하 게 배포 하 고 operationalize 수 있습니다. 

이 가이드는 다음과 같은 작업에 도움이 됩니다.
- 랩 서버 및 컴퓨터 설정
- 사용자 및 그룹을 사용 하 여 Active Directory 구성
- Azure ATP, Office ATP, Microsoft Defender ATP 및 Microsoft Cloud App Security를 설정 하 고 구성 합니다.
- 서버 및 컴퓨터에 대 한 로컬 정책 설정
- 위협 공격을 모방 하 여 Microsoft Threat Protection에서 테스트 인시던트 또는 경고 생성

>[!IMPORTANT]
>최적의 결과를 위해 랩 설치 지침을 최대한 면밀 하 게 따릅니다.


## <a name="deployment-phases"></a>배포 단계

Microsoft Threat Protection 평가판 랩 환경을 만들고 배포 하는 과정은 다음 세 단계로 진행 됩니다.

|단계 | 설명 | 
|:-------|:-----|
| ![1 단계: 준비](../../media/prepare.png)<br>[1 단계: 준비](prepare-mtpeval.md)| 평가판 랩 또는 파일럿 환경에서 Microsoft 위협 보호를 배포할 때 고려해 야 할 사항에 대해 알아봅니다. <br><br>-관련자 및 승인 <br> -환경 고려 사항 <br>-액세스 <br>-Azure Active Directory 설치 <br> -구성 순서
|  ![2 단계: 설치](../../media/setup.png) <br>[2 단계: 설치](setup-mtpeval.md)|  Microsoft 365 보안 센터에 액세스 하는 초기 단계를 수행 하 여 Microsoft Threat Protection 평가판 랩 또는 파일럿 환경을 설정 합니다. 다음을 안내 합니다.<br><br>-Microsoft 365 E5 평가판 등록 <br>  -도메인 구성<br>-Microsoft 365 E5 라이선스 할당<br>-포털에서 설치 마법사 완료|
|  ![3 단계: 온보드 & 구성](../../media/config-onboard.png) <br>[3 단계: 온보드 & 구성](config-mtpeval.md) | 각 Microsoft Threat Protection 기둥 및 온보드 끝점을 구성 합니다. 다음을 안내 합니다.<br><br>-Office 365 Advanced Threat Protection 구성<br>-Microsoft Cloud App Security 구성<br>-Azure Advanced Threat Protection 구성<br>-Microsoft Defender Advanced Threat Protection 구성 


## <a name="in-scope"></a>범위 내

이 가이드의 범위에서는 다음과 같은 작업을 수행 합니다.
-   Azure Active Directory 설정
-   Microsoft Threat Protection 설정
    -   파일럿을 실행 하는 경우 Microsoft 365 E5 평가판에 등록 하거나 정식 라이선스를 사용 합니다.
    -   도메인 구성
    -   Microsoft 365 E5 라이선스 할당
    -   포털 내에서 설정 마법사 완료
-   모범 사례에 따라 모든 Microsoft Threat Protection 핵심 요소로를 구성 합니다.
    -   Office 365 Advanced Threat Protection
    -   Azure Advanced Threat Protection
    -   Microsoft Cloud App Security
    -   Microsoft Defender Advanced Threat Protection

## <a name="out-of-scope"></a>범위를 벗어남

이 배포 가이드의 범위는 다음과 같습니다.

-   Microsoft Threat Protection과 통합할 수 있는 타사 솔루션 구성
-   프로덕션 환경의 침투 테스트

## <a name="next-step"></a>다음 단계
![1 단계: 준비](../../media/prepare.png) <br>[1 단계: 준비](prepare-mtpeval.md) 
<br> Microsoft Threat Protection 평가판 랩 또는 파일럿 환경 준비
