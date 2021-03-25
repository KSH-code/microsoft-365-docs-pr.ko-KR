---
title: 배포 단계
description: 끝점을 준비, 설정 및 서비스로 온보딩하여 끝점용 Microsoft Defender를 배포하는 방법에 대해 자세히 알아보기
keywords: 배포, 준비, 설정, 온보드, 단계, 배포, 배포, 채택, 구성
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365solution-endpointprotect
- m365solution-overview
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 3f0527192a55d67df7e23507bed46df446f8b2b7
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/24/2021
ms.locfileid: "51165168"
---
# <a name="deployment-phases"></a>배포 단계

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**적용 대상:**
- [엔드포인트용 Microsoft Defender](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

>Endpoint용 Defender를 경험하고 싶나요? [무료 평가판에 등록합니다.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-assignaccess-abovefoldlink)

엔터프라이즈에서 예방적 보호, 사후 위반 감지, 자동화된 조사 및 대응을 활용할 수 있도록 끝점용 Microsoft Defender를 배포하는 방법을 알아보십시오. 


이 가이드는 이해 관계자 전체가 환경을 준비한 다음 평가에서 의미 있는 파일럿으로 이동하여 조직적인 방식으로 디바이스를 온보드하는 데 도움이 됩니다.

각 섹션은 이 솔루션의 별도 문서에 해당합니다.

![표의 세부 정보가 있는 배포 단계의 이미지](images/deployment-guide-phases.png)


![배포 단계 요약: 준비, 설정, 온보드](images/phase-diagrams/deployment-phases.png)

|단계 | 설명 | 
|:-------|:-----|
| [1단계: 준비](prepare-deployment.md)| 이해 관계자 승인, 환경 고려 사항, 액세스 권한 및 기능 채택 순서와 같이 끝점에 대해 Defender를 배포할 때 고려해야 하는 사항을 자세히 알아보습니다. 
| [2단계: 설치](production-deployment.md)|  라이선스 유효성 검사, 설정 마법사 완료 및 네트워크 구성과 같이 포털에 액세스할 수 있도록 해야 하는 초기 단계에 대한 지침을 얻습니다. 
| [3단계: 온보더](onboarding.md) | 배포 링을 활용하고, 끝점 유형에 따라 지원되는 온보더링 도구를 활용하고, 사용 가능한 기능을 구성하는 방법을 설명합니다. 


이 가이드를 완료하면 올바른 액세스 권한으로 설정하고, 끝점이 온보더링되어 센서 데이터를 서비스에 보고하며, 차세대 보호 및 공격 표면 감소와 같은 기능이 준비됩니다.



배포 계획 지침에 설명된 환경 아키텍처 및 [](deployment-strategy.md) 배포 방법에 관계없이 이 가이드에서는 끝점 온보드를 지원할 것입니다. 








## <a name="key-capabilities"></a>주요 기능

끝점용 Microsoft Defender는 다양한 기능을 제공 하지만 이 배포 가이드의 주요 목적은 장치를 온보딩하여 시작하는 것입니다. 이 지침은 온보드 외에도 다음 기능으로 시작할 수 있습니다.



기능 | 설명 
:---|:---
끝점 감지 및 대응 | 끝점 감지 및 대응 기능은 침입 시도 및 활성 위반을 감지, 조사 및 대응하기 위해 사용됩니다.
차세대 보호 | 네트워크의 보안 경계를 더욱 강화하기 위해 끝점용 Microsoft Defender는 모든 유형의 새로운 위협을 감지하도록 설계된 차세대 보호를 사용했습니다.
공격 표면 감소 |  스택에서 첫 번째 방어 라인을 제공합니다. 구성 설정이 올바르게 설정되고 악용 완화 기술이 적용되었는지 확인하여 이러한 기능 집합은 공격 및 악용을 저항합니다.

이러한 모든 기능은 끝점용 Microsoft Defender 라이선스 보유자가 사용할 수 있습니다. 자세한 내용은 라이선스 요구 [사항을 참조하세요.](minimum-requirements.md#licensing-requirements)

## <a name="scope"></a>Scope

### <a name="in-scope"></a>범위 내

-   Microsoft Endpoint Manager 및 Microsoft Endpoint Manager를 사용하여 끝점을 서비스에 온보드 및 기능 구성

-   끝점 끝점 감지 및 응답(EDR) 기능에 Defender 사용

-   끝점 끝점 보호 플랫폼(EPP) 기능에 Defender 사용

    -   차세대 보호

    -   공격 표면 감소


### <a name="out-of-scope"></a>범위를 벗어남

다음은 이 배포 가이드의 범위를 벗어나는 것입니다.

-   끝점용 Defender와 통합될 수 있는 타사 솔루션 구성

-   프로덕션 환경에서 침투 테스트




## <a name="see-also"></a>참고 항목
- [1단계: 준비](prepare-deployment.md)
- [2단계: 설정](production-deployment.md)
- [3단계: 온보더](onboarding.md)
- [배포 계획](deployment-strategy.md)