---
title: Microsoft 365 Defender 평가
description: Microsoft 365 Defender 평가판 랩 또는 파일럿 환경을 설정하여 조직의 장치, ID, 데이터 및 응용 프로그램을 보호하도록 설계된 보안 솔루션을 체험해 보아야 합니다.
keywords: Microsoft 위협 방지 평가판, Microsoft Threat Protection 평가, Microsoft Threat Protection 평가, Microsoft Threat Protection 평가 랩, Microsoft Threat Protection 파일럿, 사이버 보안, 고급 영구 위협, 엔터프라이즈 보안, 장치, 장치, ID, 사용자, 데이터, 응용 프로그램, 인시던트, 자동화된 조사 및 수정, 고급 헌팅
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
ms.openlocfilehash: 8504b036203e1f73dc9e0a0d79a228425fb88bfa
ms.sourcegitcommit: 0a8b0186cc041db7341e57f375d0d010b7682b7d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/11/2020
ms.locfileid: "49659636"
---
# <a name="create-a-microsoft-365-defender-trial-lab-or-pilot-environment"></a>Microsoft 365 Defender 평가판 랩 또는 파일럿 환경 만들기 

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**적용 대상:**
- Microsoft 365 Defender


이 가이드는 사용자 및 그룹과 함께 랩 환경을 설정하는 데 도움을 주며 위협 공격을 모방하고 의미 있는 평가판 결과를 얻을 수 있도록 Microsoft 365 Defender의 기능 구성을 안내합니다. 

이 평가판 랩 또는 파일럿 환경을 만드는 목적은 포괄적이고 통합된 Microsoft 365 Defender 기능을 보여 주는 것입니다. 이 지능형 보안 솔루션이 조직에서 고급 위협을 감지, 방지, 자동으로 조사 및 대응하는 방법을 경험해 보십시오. 


권장 배포 경로를 기반으로 Microsoft 365 Defender 평가를 시작하는 단계를 안내합니다. 목표는 시험 계정을 사용 하 고 테스트 환경에서 또는 전체 라이선스를 사용 하 고 프로덕션에서 파일럿 환경에서 보안 솔루션을 설정 하는 데 도움이 됩니다. 시험 랩 또는 파일럿 환경을 준비하면 조직의 의사 결정권자에 보안 작업 사용 사례를 제시하는 데 도움이 될 수 있습니다. 공격 시뮬레이션 실행을 완료하고 그 결과에 만족하면 조직의 Microsoft 기술 영업 전문가 또는 전문가의 도움을 통해 조직에 완전히 배포하고 운영할 수 있습니다. 

이 가이드는 다음을 도와 줄 것입니다.
- 랩 서버 및 컴퓨터 설정
- 사용자 및 그룹을 통해 Active Directory 구성
- Id용 Microsoft Defender, Office 365용 Microsoft Defender, 끝점용 Microsoft Defender 및 Microsoft Cloud App Security 설정 및 구성
- 서버 및 컴퓨터에 대한 로컬 정책 설정
- 위협 공격을 모방하여 Microsoft 365 Defender에서 테스트 인시던트 또는 경고 생성

>[!IMPORTANT]
>최적의 결과를 얻기 위해 랩 설정 지침을 최대한 따르세요.


## <a name="deployment-phases"></a>배포 단계

Microsoft 365 Defender 평가판 랩 환경을 만드는 세 가지 단계가 있습니다.

![배포 단계: 준비, 설정, 온보드](../../media/evaluation-guide-phases.png)

|단계 | 설명 | 
|:-------|:-----|
|[1단계: 준비](prepare-mtpeval.md)| 평가판 랩 또는 파일럿 환경에서 Microsoft 365 Defender를 배포할 때 고려해야 할 사항에 대해 자세히 알아보습니다. <br><br>- 이해 관계자 및 사인오프 <br> - 환경 고려 사항 <br>- Access <br>- Azure Active Directory 설정 <br> - 구성 순서
|[2단계: 설정](setup-mtpeval.md)|  Microsoft 365 보안 센터에 액세스하여 Microsoft 365 Defender 평가판 랩 또는 파일럿 환경을 설정하는 초기 단계를 수행합니다. 다음을 안내합니다.<br><br>- Microsoft 365 E5 평가판 등록 <br>  - 도메인 구성<br>- Microsoft 365 E5 라이선스 할당<br>- 포털에서 설정 마법사 완료|
|[3단계: 온보드 & 구성](config-mtpeval.md) | 각 Microsoft 365 Defender 기조 및 끝점을 구성합니다. 다음을 안내합니다.<br><br>- Office 365용 Microsoft Defender 구성<br>- Microsoft Cloud App Security 구성<br>- Id에 대한 Microsoft Defender 구성<br>- 끝점용 Microsoft Defender 구성


이 가이드를 완료한 후 관련 이해 관계자와 필요한 승인을 식별하고, 올바른 액세스 권한을 가지며, 평가판에 등록하고, 도메인을 구성하고, 각 Microsoft 365 Defender 기조를 구성하고, 끝점이 서비스에 등록됩니다.

## <a name="key-capabilities"></a>주요 기능

Microsoft 365 Defender는 많은 기능을 제공 하지만 이 배포 가이드의 주요 목적은 장치를 온보딩하여 시작하는 것입니다. 이 지침은 온보드 외에도 다음과 같은 기능으로 시작할 수 있습니다.


기능 | 설명 
:---|:---
Office 365용 Microsoft Defender | 오늘날의 위협으로부터 전체 Office 365에 대한 열의를 보호합니다.
ID용 Microsoft Defender | 손상된 ID 및 악의적인 내부자 작업에 대한 위협을 식별하고 감지합니다.
Microsoft Cloud App Security | 풍부한 가시성을 제공하고, 데이터 이동을 제어하고, 클라우드 서비스 전반에 걸쳐 사이버 위협을 감지합니다.
엔드포인트용 Microsoft Defender | 포괄적인 끝점 보안을 통해 고급 위협을 방지, 감지 및 대응합니다.


## <a name="in-scope"></a>범위 내

이 가이드의 범위에는 다음과 같은 작업이 있습니다.
-   Azure Active Directory 설정
-   Microsoft 365 Defender 설정
    -   파일럿을 실행하는 경우 Microsoft 365 E5 평가판에 등록하거나 정식 라이선스 사용
    -   도메인 구성
    -   Microsoft 365 E5 라이선스 할당
    -   포털 내에서 설정 마법사 완료
-   모범 사례에 따라 모든 Microsoft 365 Defender 기조 구성
    -   Office 365용 Microsoft Defender
    -   ID용 Microsoft Defender
    -   Microsoft Cloud App Security
    -   엔드포인트용 Microsoft Defender

## <a name="out-of-scope"></a>범위를 벗어남

다음은 이 배포 가이드의 범위를 벗어날 수 있습니다.

-   Microsoft 365 Defender와 통합될 수 있는 타사 솔루션 구성
-   프로덕션 환경의 침투 테스트

## <a name="next-step"></a>다음 단계
[1단계: 준비](prepare-mtpeval.md) 
<br> Microsoft 365 Defender 평가판 랩 또는 파일럿 환경 준비
