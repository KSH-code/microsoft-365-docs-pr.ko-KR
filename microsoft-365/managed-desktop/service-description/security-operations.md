---
title: Microsoft Managed Desktop의 보안 작업
description: ''
keywords: Microsoft Managed Desktop, Microsoft 365, 서비스, 문서
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: 5698e2a88adf3d2bae84a82e0e001132293e36be
ms.sourcegitcommit: 815229e39a0f905d9f06717f00dc82e2a028fa7c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/03/2020
ms.locfileid: "48847719"
---
# <a name="security-operations-in-microsoft-managed-desktop"></a>Microsoft Managed Desktop의 보안 작업

데스크톱 환경의 보안을 유지 하기 위한 정보 보안 직원과 Microsoft Managed Desktop (데스크톱 보안 운영 센터) 파트너 이 팀은 전문가 분석을 통해 관리 되는 장치에서 모든 보안 경고를 수신 하 고이에 응답 하 고, 필요한 경우 보안 인시던트 대응 활동을 구동 합니다. SOC 사용에 대 한 자세한 내용은 관리자 포털에서 운영 설명서를 참조 하세요.

SOC는 소프트웨어, 네트워크 또는 인간 악의적 사용자을 통한 일반적인 공격 방법을 포함 하 여 Microsoft 정규 직원 으로부터 현재와 새로 등장 한 위협에 대 한 전문성을 24/7/365 제공 합니다.

SOC는 다음과 같은 서비스를 제공 합니다.
- 데이터를 분석 하 여 영향을 식별 하 고 장치 또는 환경의 전반적인 위험을 평가 하는 검색 된 이벤트에 대 한 빠르고 정확한 대응
- 장치 관리 및 격리 작업-알려진 손상 으로부터 환경을 보호 하 고 확산을 방지 하 여 위험 감소
- 보안 인시던트 대응 프로세스를 추진 하 여 사용자의 적시에 정확 하 고 정확한 통신 보장
- 악용 되기 전에 위험을 식별 하 고 해결 하기 위한 위협 및 취약성 데이터를 기반으로 한 분석 및 권장 사항
- 관리 되는 장치를 통한 고급 사냥은 알려진 위협과 잠재적인 위협에 대 한 지표 및 엔터티를 식별 합니다.

## <a name="processes"></a>프로세서

- Microsoft Managed Desktop Security 작업은 Microsoft의 [사이버 방어 운영 센터](https://www.microsoft.com/msrc/cdoc)와의 파트너 관계에 있는 전일 근무 직원 들의 팀입니다. 
- SOC는 Microsoft 관리 데스크톱에 아직 표시 되지 않은 것 처럼 내부 및 외부의 회사 전체에서의 집합적 신호를 사용 합니다.
- Microsoft 보안 솔루션은 많은 cybersecurity 보호 표준에 맞춥니다. SOC 작업은 국가 표준 및 기술 컴퓨터 보안 사고 대응 처리 가이드 (NIST 800-61 r2)를 기반으로 합니다.
- 이 프로세스를 통해 이러한 단계를 통해 환경을 보다 효율적으로 보호 하는 방식으로 분석과 설명서 및 사후 복구를 위한 정보 및 증거를 적절 하 게 수집할 수 있습니다.
    - 준비, 검색 및 분석
    - 관계
    - Eradication
    - 복구
    - 인시던트 사후 활동
- Microsoft Managed Desktop 고객은 Microsoft Threat services 전문가 서비스에 등록할 수 있습니다. 이 서비스를 사용 하는 SOC liaises에서는 경고 조회, 잠재적으로 손상 된 장치, 의심 스러운 네트워크 연결의 근본 원인 및 진행 중인 고급 지속적인 위협 캠페인에 대 한 추가 위협 인텔리전스를 비롯 하 여 조직에 영향을 주는 복잡 한 위협을 이해 하는 데 도움이 됩니다. 자세한 내용은 [Microsoft Threat 전문가가](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-threat-experts)를 참조 하세요.
- SOC의 위협 및 취약성 관리 프로세스는 Microsoft의 일부 서비스를 사용 하 여 조직에서 위협 으로부터 보호 하기 위한 권장 사항을 알리는 데 도움을 줍니다. SOC는 microsoft Defender for Endpoint 보안 센터 및 Microsoft 외부의 관련 취약성 데이터 원본에서 데이터를 사용 하 여 취약성 및 구성 오류를 검색 하 고 조치를 취할 수 있는 보고 기능을 제공 합니다.
