---
title: 3단계. SOC Microsoft 365 Defender 통합 계획
description: 서비스 Microsoft 365 Defender 보안 운영 카탈로그에 통합하기 위한 기본
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
ms.openlocfilehash: e9a915cfb698e80756e0810963e112889bd67a66
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/06/2021
ms.locfileid: "60157689"
---
# <a name="step-3-plan-for-microsoft-365-defender-integration-with-your-soc-catalog-of-services"></a>3단계. SOC Microsoft 365 Defender 통합 계획

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**적용 대상:**
- Microsoft 365 Defender

SOC(보안 운영 센터)에는 다음을 포함할 수 있는 서비스 카탈로그가 포함되어야 합니다.

- 침입 & 맬웨어 분석
- 역방향 & 기여
- 위협 인텔리전스
- 분석
- 헌팅 조사
- 포렌식스
- 사고 대응 
- CSIRT(컴퓨터 보안 인시던트 대응 팀)(SOC에서 나갈 수 있습니다.) 
- 준수 테스트
- 내부자 위협 & 모니터링
- 보안 인시던트 & 모니터링 
- 취약성 검색
- XDR(확장 검색 및 응답)/보안 오케스트레이션, 자동화 및 응답(SOAR)
- 피싱
- 데이터 손실 방지
- 브랜드 모니터링

여러 Microsoft 365 Defender 기술에 걸쳐 있으므로 SOC 팀은 각 Defender 구성 요소를 관리하고 서비스 기능에 맞추는 데 가장 적합한 역할과 책임을 결정해야 합니다.

이러한 구성 요소는 Microsoft 365 Defender 있습니다.

- **Id용 Microsoft Defender(이전의** Azure Advanced Threat Protection, Azure ATP라고도 합니다.)는 AD DS(Active Directory 도메인 서비스) 신호를 사용하여 조직을 위한 고급 위협, 손상된 ID 및 악의적인 내부자 작업을 식별, 감지 및 조사하는 클라우드 기반 보안 솔루션입니다.

- **끝점용 Microsoft Defender는** 위험 기반 취약성 관리 및 평가, 공격 표면 감소, 동작 기반 및 클라우드 기반 차세대 보호, 끝점 감지 및 대응(EDR), 자동 조사 및 수정, 관리되는 헌팅 서비스, 다양한 API 및 통합 보안 관리를 포함하는 장치에 대한 전체적인 클라우드 제공 끝점 보안 솔루션입니다.

 - **Microsoft Defender for Office 365** 는 강력한 제로 데이 보호 기능을 제공하여 알 수 없는 맬웨어 및 바이러스로부터 조직을 보호하는 클라우드 기반 전자 메일 필터링 서비스로, 유해한 링크로부터 실시간으로 조직을 보호하는 기능을 포함합니다. 또한 포괄적인 조사 및 헌팅, 대응 및 수정, 인식과 교육, 안전한 자세 기능을 제공합니다.

- **Microsoft Cloud App Security 컬렉션,** API 커넥터 및 역방향 프록시를 비롯한 다양한 배포 모드를 지원하는 CASB(Cloud Access Security Broker)입니다. 모든 Microsoft 및 타사 클라우드 서비스에서 사이버 위협을 식별하고 퇴치하기 위한 풍부한 가시성, 데이터 이동 제어 및 정교한 분석을 제공합니다.

여러 Microsoft 365 Defender 구성 요소와 기술이 사용 가능하기 때문에 SOC 팀은 각 구성 요소를 관리하고 서비스 기능에 맞추기 위해 가장 적합한 역할과 책임을 Microsoft 365 Defender 결정해야 합니다.

이 기능을 통합하려면 Microsoft 365 Defender SOC 서비스를 구체화해야 합니다. 이 문서의 기능에 대한 자세한 Microsoft 365 Defender 문서를 참조하세요.

- [엔드포인트용 Microsoft Defender란 무엇인가요?](/defender-endpoint/microsoft-defender-endpoint)
- [Microsoft Defender for Identity란?](/defender-for-identity/what-is)
- [Office 365용 Defender란 무엇인가요?](/office-365-security/defender-for-office-365)
- [Microsoft Cloud App Security란 무엇인가요?](/cloud-app-security/what-is-cloud-app-security)

## <a name="next-step"></a>다음 단계

[4단계. Microsoft 365 Defender 역할, 책임 및 감독 정의](integrate-microsoft-365-defender-secops-roles.md)

