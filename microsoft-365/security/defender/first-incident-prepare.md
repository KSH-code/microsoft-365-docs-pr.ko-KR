---
title: 첫 번째 인시던트에 대한 보안 준비
description: Microsoft 365 첫 번째 인시던트에 대한 테넌트의 보안 Microsoft 365 Defender.
keywords: 인시던트, 경고, 조사, 상관 관계, 공격, 컴퓨터, 장치, 사용자, IDs, ID, 사서함, 전자 메일, 365, microsoft, m365
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
ms.openlocfilehash: b73103dee0b20abbebc9c10834ba918c71f9c01b
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/06/2021
ms.locfileid: "60210654"
---
# <a name="prepare-your-security-posture-for-your-first-incident"></a>첫 번째 인시던트에 대한 보안 준비

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**적용 대상:**
- Microsoft 365 Defender

인시던트 처리를 준비하는 과정에는 다양한 종류의 보안 인시던트에서 조직의 네트워크를 충분히 보호할 수 있는 설정이 필요합니다. NIST(National Institute of Standards and Technology)는 보안 인시던트 위험을 줄이기 위해 위험 평가, 호스트 보안 강화, 네트워크를 안전하게 구성 및 맬웨어 방지를 비롯한 몇 가지 보안 관행을 권장합니다. 

Microsoft 365 Defender 인시던트 방지의 여러 측면을 해결할 수 있습니다. 

- Zero [Trust](/security/zero-trust/) 프레임워크 구현
- Microsoft 보안 점수를 통해 점수를 할당하여 보안 설정 [결정](microsoft-secure-score.md)
- 위협 및 취약성 관리의 취약점 평가를 통해 위협 [방지](../defender-endpoint/next-gen-threat-and-vuln-mgt.md)
- 준비할 수 있도록 최신 보안 위협 이해

## <a name="step-1-implement-zero-trust"></a>1단계. 제로 트러스트 구현

[Zero Trust는](/security/zero-trust/) 모바일 인력, 사용자, 장치, 응용 프로그램 및 데이터를 비롯한 모든 최신 환경의 복잡한 특성을 고려하는 통합 보안 철학 및 종단식 전략입니다. 단일 창을 제공하여 일관된 방식으로 모든 검색을 관리함으로써 Microsoft 365 Defender 팀이 Zero Trust의 기본 원칙을 [](/security/zero-trust/#guiding-principles-of-zero-trust) 보다 쉽게 구현할 수 있습니다. 

Microsoft 365 Defender 구성 요소는 끝점용 Microsoft Defender 또는 기타 모바일 보안 공급업체의 데이터를 장치 준수 정책 및 장치 기반 조건부 액세스 정책 구현에 대한 정보 원본으로 통합하여 Zero Trust에 대한 조건부 액세스 정책을 설정하기 위해 구현된 규칙 위반을 표시할 수 있습니다. 

장치 위험은 해당 장치의 사용자가 액세스할 수 있는 리소스에 직접적인 영향을 미치게 됩니다. 특정 기준에 따라 리소스에 대한 액세스 거부는 Zero Trust의 주요 테마이고 Microsoft 365 Defender 수준 조건을 결정하는 데 필요한 정보를 제공합니다. 예를 들어 Microsoft 365 Defender 및 취약성 관리 페이지를 통해 장치의 소프트웨어 버전 수준을 제공할 수 있으며 조건부 액세스 정책은 기한이 지난 또는 취약한 버전을 제한하는 장치를 제한할 수 있습니다.

자동화는 제로 트러스트 환경을 구현하고 유지 관리하는 데 중요한 부분입니다. 또한 잠재적으로 IR(인시던트 대응) 이벤트로 이어질 수 있는 경고 수를 줄입니다. Microsoft 365 Defender 구성 요소는 수정 작업(Microsoft 365 Defender [](m365d-autoir.md) 포털의 인시던트에 대한 조사), 알림 작업 및 [ServiceNow와](https://microsoft.service-now.com/sp/)같은 지원 티켓 생성과 같은 자동화할 수 있습니다.

## <a name="step-2-determine-your-organizations-security-posture"></a>2단계. 조직의 보안 설정 결정

다음으로 조직은 Microsoft [보안](microsoft-secure-score.md) 점수를 사용하여 현재 보안 Microsoft 365 Defender 결정하고 이를 개선하는 방법에 대한 권장 사항을 고려할 수 있습니다. 점수가 높을수록 조직에서 보안 권장 사항 및 개선 작업을 더 많이 수행했습니다. 보안 점수 권장 사항은 여러 제품에서 사용할 수 있으며 조직에서 점수를 더 높게 올 수 있도록 허용할 수 있습니다. 

:::image type="content" source="../../media/first-incident-prepare/first-incident-secure-score.png" alt-text="Microsoft 보안 센터의 Microsoft 보안 점수 예제":::
 
## <a name="step-3-assess-your-organizations-vulnerability-exposure"></a>3단계. 조직의 취약성 노출 평가

인시던트 방지는 중요하고 중요한 보안 인시던트에 집중하기 위한 보안 운영 노력을 간소화하는 데 도움이 될 수 있습니다. 소프트웨어 취약성은 종종 데이터 도용, 데이터 손실 또는 비즈니스 운영 중단으로 이어질 수 있는 공격에 대한 예방 가능한 진입점입니다. 계속되는 공격이 없는 경우 보안 운영은 조직에서 허용되는 수준의 [](../defender-endpoint/tvm-exposure-score.md) 취약점 노출을 달성하고 유지 관리하기 위해 노력해야 합니다.

소프트웨어 패치 진행률을 확인하기 [](../defender-endpoint/next-gen-threat-and-vuln-mgt.md) 위해 Endpoint용 Defender의 위협 및 취약성 관리 페이지를 방문하여 추가 리소스 탭을 통해 Microsoft 365 Defender 액세스할 **수** 있습니다.

:::image type="content" source="../../media/first-incident-prepare/first-incident-vulnerability.png" alt-text="Microsoft 보안 센터의 위협 및 취약성 페이지의 예"::: 
 
## <a name="4-understand-emerging-threats"></a>4. 새로운 위협 이해

보안 [포털에서](threat-analytics.md) 위협 Microsoft 365 Defender 사용하여 현재 보안 위협 환경과 함께 최신 정보를 유지할 수 있습니다. 전문가 Microsoft 보안 연구원은 최신 사이버 위협을 자세히 설명하는 보고서를 만들어 사용자의 구독, 장치 및 사용자에게 어떤 Microsoft 365 영향을 줄 수 있습니다. 이러한 보고서에는 다음이 포함됩니다.

- 활성 위협 요소 및 캠페인
- 인기 있는 새로운 공격 기술
- 중요한 취약성
- 일반적인 공격 표면
- 널리 사용되는 맬웨어

또한 위협 분석은 구성 및 경고를 확인하여 위험 상태 및 보고서에 적용할 수 있는 활성 경고가 있는지 여부를 파악합니다.

새로운 위협에 대한 권장 사항을 구현하여 보안 자세를 강화하고 공격 노출 영역을 최소화할 수 있습니다.

일정을 정해 두어 포털의 [Threat Analytics](threat-analytics.md) 섹션을 Microsoft 365 Defender 합니다.

## <a name="next-step"></a>다음 단계

[![1단계: 인시던트의 선별 및 분석 방법을 배워야 합니다.](../../media/first-incident-overview/first-incident-path-step1.png)](first-incident-analyze.md)

인시던트 [를 분석하고 을(를) 분석하는 방법을 배워야 합니다.](first-incident-analyze.md)

## <a name="see-also"></a>참고 항목

- [사고 개요](incidents-overview.md)
- [사고 조사](investigate-incidents.md)
- [인시던트 관리](manage-incidents.md)
