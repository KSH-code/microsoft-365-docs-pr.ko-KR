---
title: Microsoft Threat Protection 평가
description: Microsoft Threat Protection 평가판 랩 환경을 설정 하 여 장치, id, 데이터 및 응용 프로그램을 보호 하도록 설계 된 위협 방지 솔루션을 통해 조직에서 도움을 제공 하는 방법을 확인할 수 있습니다.
keywords: Microsoft 위협 보호 평가판, microsoft threat protection, microsoft threat protection 평가 랩, 사이버 보안, 고급 영구 위협, 엔터프라이즈 보안, 장치, 장치, id, 사용자, 데이터, 응용 프로그램, 인시던트, 자동화 된 조사 및 개선, 고급 구하기
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
ms.openlocfilehash: f6ee8147965a29b87d84690535116f096e4c6006
ms.sourcegitcommit: 5476c2578400894640ae74bfe8e93c3319f685bd
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/06/2020
ms.locfileid: "44049642"
---
# <a name="create-a-microsoft-threat-protection-trial-lab-environment"></a>Microsoft Threat Protection 평가판 랩 환경 만들기 

**적용 대상:**
- Microsoft 위협 방지

이 평가판 랩 환경을 만드는 목적은 검색, 예방, 조사 및 조직에서 사용할 수 있는 응답에 대 한 Microsoft 위협 보호의 포괄적이 고 통합 된 기능을 보여 주기 위한 것입니다. 

이 가이드에서는 권장 되는 배포 경로를 기반으로 Microsoft Threat Protection 평가를 시작 하는 단계를 안내 합니다. 이 목표는 조직에서 보안 솔루션 의사 결정권자에 게 발표할 때 랩 환경 또는 개념 증명 (POC)으로 통합 Microsoft 위협 보호 서비스를 설정 하는 데 도움이 됩니다. 공격 시뮬레이션이 실행 되 고 자동화 된 조사 및 응답을 수행 하 고 결과에 만족 하면 조직의 Microsoft 기술 영업 전문가 또는 전문가를 지원 하 여 프로덕션 환경에 배포할 수 있습니다. 

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
| ![1 단계: 준비](../../media/prepare.png)<br>[1 단계: 준비](prepare-mtpeval.md)| 평가판 랩 환경에서 Microsoft 위협 보호를 배포할 때 고려해 야 할 사항에 대해 알아봅니다. <br><br>-관련자 및 승인 <br> -환경 고려 사항 <br>-액세스 <br>-Azure Active Directory 설치 <br> -구성 순서
|  ![2 단계: 설치](../../media/setup.png) <br>[2 단계: 설치](setup-mtpeval.md)|  Microsoft 365 보안 센터에 액세스 하 여 Microsoft Threat Protection 평가판 랩 환경을 설정 하기 위한 초기 단계를 수행 합니다. 다음을 안내 합니다.<br><br>-Microsoft 365 E5 평가판 등록 <br>  -도메인 구성<br>-Microsoft 365 E5 라이선스 할당<br>-포털에서 설치 마법사 완료|
|  ![3 단계: 온보드 & 구성](../../media/config-onboard.png) <br>[3 단계: 온보드 & 구성](config-mtpeval.md) | 각 Microsoft Threat Protection 기둥 및 온보드 끝점을 구성 합니다. 다음을 안내 합니다.<br><br>-Office 365 Advanced Threat Protection 구성<br>-Microsoft Cloud App Security 구성<br>-Azure Advanced Threat Protection 구성<br>-Microsoft Defender Advanced Threat Protection 구성 


## <a name="in-scope"></a>범위 내

이 평가판 랩 환경 가이드의 범위는 다음과 같습니다.
-   Azure Active Directory 설정
-   Microsoft Threat Protection 설정
    -   Microsoft 365 E5 평가판 등록
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

-   Microsoft Defender ATP와 통합할 수 있는 타사 솔루션 구성
-   프로덕션 환경의 침투 테스트

## <a name="next-step"></a>다음 단계
|||
|:-------|:-----|
|![1 단계: 준비](../../media/prepare.png) <br>[1 단계: 준비](prepare-mtpeval.md) | Microsoft Threat Protection 평가 랩 환경 준비
