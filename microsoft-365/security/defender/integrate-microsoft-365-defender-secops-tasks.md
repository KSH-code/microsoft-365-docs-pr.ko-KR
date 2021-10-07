---
title: 6단계. SOC 유지 관리 작업 확인
description: 보안 작업에 SOC 유지 관리 Microsoft 365 Defender 식별합니다.
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
ms.openlocfilehash: 96f7c95f645f0544b0bcd80a0cd0e3f9b595733e
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/06/2021
ms.locfileid: "60197980"
---
# <a name="step-6-identify-soc-maintenance-tasks"></a>6단계. SOC 유지 관리 작업 확인

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**적용 대상:**
- Microsoft 365 Defender

다음은 사용자 관리에 대한 SOC를 유지 관리하기 위한 주기적 또는 필요한 Microsoft 365 Defender.

| 활동  | 설명 | 흐름 | 할당된 팀 |
|:-------|:-----|:-------|:-------|
| SOC 및 서비스 관리 공동 Teams   | CMDB(자산 추적), 응용 프로그램 라이선스(새 SaaS 라이선스), 장치 구매(장치 배포 업그레이드 또는 갱신) 및 Microsoft 365 제품 배포에 영향을 줄 수 있는 기타 테넌트 전체 변경(Intune, Microsoft 365 등)과 같은 주변 Microsoft 365 Defender 관리 | 매주 및 필요한 경우   | SecOps & 엔지니어링 | 
| 피싱 방지 및 데이터 손실 방지 캠페인 업데이트 | 확장된 조직(HR, 법률, 교육 등)에서 얻은 SOC 사용 사례 및 교훈을 통합합니다.  | 월별 및 필요한 경우 | SOC 감독 |
| 적절한 경우 자동화 스크립트 및 서비스 배포 | 승인된 Microsoft 사이트에서 자동화 스크립트 및 구성 파일을 다운로드하고 테스트하여 Microsoft 365 Defender 개선합니다. | 매주 및 필요한 경우 | Engineering and SecOps | 
| 포털 또는 라이선스 관리 | Microsoft 업데이트 및 새 기능에 Microsoft 메시지 포털 Microsoft 365 Defender 라이선스 요구에 대한 공지 사항을 확인합니다. | 매주 | SOC 감독| 
| SOC 에스컬레이터 티켓 업데이트 | 모든 SOC 팀은 할당된 에스컬레이터 티켓(예: Sentinel, ServiceNow 티켓)을 업데이트합니다. | 매일 | 모든 SOC 팀 | 
| 위협 Microsoft 365 Defender 수정 & 추적 | TvM 보안 점수 수정 활동을 생성하고 인트라넷 포털을 통해 자산 소유자에게 보고합니다. | 매일 | 모니터링 | 
| 보안 점수 보고서 생성 | 모니터링 팀은 보안 점수 개선을 추적하고 보고합니다. | 매주 SOC | 모니터링 | 
| IR 태블릿PC 연습 실행 | 태블릿OP 연습에서 SOC 팀 플레이북을 테스트합니다. | 필요에 따라 | 모든 SOC 팀 | 
|||||

이러한 작업을 현재 SOC 프로세스에 통합합니다.

## <a name="next-steps"></a>다음 단계

이 콘텐츠 및 Microsoft 365 Defender 라이브러리에서 참조되는 가이드를 검토하여 자체 콘텐츠 구현을 구성하고 통합하는 Microsoft 365 Defender 결정해야 합니다. [](/microsoft-365/security/defender)
