---
title: 2단계. Zero Trust Framework를 사용하여 SOC 통합 준비 평가 수행
description: 보안 작업에 통합할 때 Zero Trust Framework를 사용하여 SOC Microsoft 365 Defender 준비 평가를 수행하는 기본 설정입니다.
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
localization_priority: Normal
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
ms.openlocfilehash: 27cbc0ec7286812cebc500952bc68adad3586eb8
ms.sourcegitcommit: d08fe0282be75483608e96df4e6986d346e97180
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/12/2021
ms.locfileid: "59192452"
---
# <a name="step-2-perform-a-soc-integration-readiness-assessment-using-the-zero-trust-framework"></a>2단계. Zero Trust Framework를 사용하여 SOC 통합 준비 평가 수행

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**적용 대상:**
- Microsoft 365 Defender

SOC(보안 운영 센터) 팀의 핵심 기능이 정의되고 나면 조직의 다음 단계는 Zero Trust 접근 방식을 통해 Microsoft Defender의 채택을 [준비하는 것입니다.](/security/zero-trust/) 채택은 환경에 대해 Defender의 기능을 평가하면서 업계를 Microsoft 365 Defender 모범 사례를 사용하여 배포하는 데 필요한 요구 사항을 결정하는 데 도움이 될 수 있습니다. 

이 접근 방식은 강력한 보호 기반을 기반으로 하며 ID, 끝점(장치), 데이터, 앱, 인프라 및 네트워킹과 같은 주요 영역을 포함합니다. 준비 평가 팀은 사용자 설정에 대한 기본 요구 사항이 Microsoft 365 Defender 충족되지 않았기 때문에 수정이 필요한 영역을 결정합니다. 

다음은 SOC가 SOC의 프로세스를 완전히 최적화하기 위해 수정해야 하는 몇 가지 항목입니다.

- **ID:**     레거시 AD DS(Active Directory 도메인 서비스) 도메인, MFA 계획 없음, 권한 있는 계정 인벤토리 없음 등
- **끝점(장치):**  많은 레거시 운영 체제, 제한된 장치 인벤토리 등
- **데이터 및 앱:**    데이터 거버넌스 표준이 부족하고 통합되지 않는 사용자 지정 앱의 인벤토리가 없습니다.
- **인프라:**   많은 수의 허가되지 않은 SaaS 라이선스, 컨테이너 보안 없음 등
- **네트워킹:**   낮은 대역폭, 플랫 네트워크, 무선 보안 문제 등으로 인한 성능 문제

조직은 또한 [](m365d-enable.md) 구성 요구 사항의 Microsoft 365 Defender 설정 문서를 따라야 합니다. 이러한 단계에서는 SOC 팀이 사용 사례를 효과적으로 개발하기 위해 수행해야 하는 재구성 활동을 결정하게 됩니다. 

채택 절차 및 사용 사례 만들기는 3단계와 4단계에 설명되어 있습니다.

## <a name="next-step"></a>다음 단계

[3단계. SOC Microsoft 365 Defender 통합 계획](integrate-microsoft-365-defender-secops-services.md)
