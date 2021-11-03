---
title: 지원되는 서비스 Microsoft 365 Defender
description: 라이선스 요구 사항 및 배포 절차에 Microsoft 365 Defender 통합할 수 있는 Microsoft 보안 서비스에 대해 설명합니다.
keywords: 배포, 라이선스, 지원되는 서비스, 프로비전, 구성 Microsoft 365 Defender, M365, 라이선스 자격, 끝점용 Microsoft Defender, Office 365용 Microsoft Defender, ID용 Microsoft Defender, Microsoft Cloud App Security, MCAS, E5, A5, EMS
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: dansimp
author: dansimp
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
ms.openlocfilehash: 816225e8054b268906c94df01d121455ecd0cdfa
ms.sourcegitcommit: bf3965b46487f6f8cf900dd9a3af8b213a405989
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/03/2021
ms.locfileid: "60705322"
---
# <a name="deploy-supported-services"></a>지원 서비스 배포

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**적용 대상:**
- Microsoft 365 Defender

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

[Microsoft 365 Defender](microsoft-365-defender.md) Microsoft 보안 서비스를 통합하여 정교한 공격에 대한 중앙 집중식 탐지, 예방 및 조사 기능을 제공합니다. 이 문서에서는 지원되는 서비스, 해당 라이선스 요구 사항, 하나 이상의 서비스 배포와 관련된 이점 및 제한 사항, 그리고 이러한 서비스를 개별적으로 완전히 배포하는 방법에 대한 링크를 제공합니다.

## <a name="supported-services"></a>지원되는 서비스
Microsoft 365 E5, E5 보안, A5 또는 A5 보안 라이선스 또는 유효한 라이선스 조합을 사용하면 지원되는 다음과 같은 서비스에 액세스할 수 있으며 사용자가 라이선스를 사용할 수 Microsoft 365 Defender. [라이선스 요구 사항 참조](prerequisites.md#licensing-requirements)

| 지원되는 서비스 | 설명 |
| ------ | ------ |
| 엔드포인트용 Microsoft Defender | 강력한 동작 센서, 클라우드 분석 및 위협 인텔리전스를 중심으로 구축된 엔드포인트 보호 제품군 |
|Office 365용 Microsoft Defender | 전자 메일 및 기타 공동 작업 도구를 포함하여 Office 365 및 데이터에 대한 고급 보호 |
| ID용 Microsoft Defender | 상관된 Active Directory 신호를 사용하여 고급 위협, ID 손상 및 악의적인 내부자 보호 |
| Microsoft 클라우드 앱 보안 | Microsoft 및 타사 클라우드 서비스 전반에서 사이버 위협 식별 및 퇴치 |

## <a name="deployed-services-and-functionality"></a>배포된 서비스 및 기능
Microsoft 365 Defender 더 많은 지원 서비스를 배포할 때 가시성, 상관 관계 및 수정을 개선할 수 있습니다.

### <a name="benefits-of-full-deployment"></a>전체 배포의 이점
모든 지원되는 서비스를 Microsoft 365 Defender 배포하는 것이 좋습니다. 다음은 전체 배포의 주요 이점입니다.
- 인시던트는 사용 가능한 모든 센서 및 서비스별 분석 기능의 경고 및 이벤트 신호를 기반으로 식별 및 상호 관련됩니다.
- AIR(자동화된 조사 및 수정) 플레이북은 장치, 사서함 및 사용자 계정을 비롯한 다양한 엔터티 유형에 적용됩니다.
- 장치, 사서함 및 기타 엔터티의 이벤트 및 엔터티 데이터에 대해 보다 포괄적인 고급 헌팅 스케마를 검색할 수 있습니다.

### <a name="limited-deployment-scenarios"></a>제한된 배포 시나리오
배포하는 지원되는 각 서비스는 상호 관련 정보뿐만 아니라 매우 풍부한 원시 신호 집합을 제공합니다. 배포가 제한되어도 Microsoft 365 Defender 기능을 해제하지는 못하지만 끝점, 앱, 데이터 및 ID에 대한 포괄적인 표시 기능을 제공하는 기능이 영향을 받지 않습니다. 동시에 모든 수정 기능은 배포한 서비스에서 관리할 수 있는 엔터티에만 적용됩니다.

아래 표에는 지원되는 각 서비스가 추가 데이터를 제공하는 방법, 데이터와 상호 연계하여 추가 정보를 얻을 수 있는 기회, 개선된 수정 및 응답 기능이 나열되어 있습니다.

| 서비스 | 데이터(상호 관련 & 신호) | 응답 & 수정 |
| ------ | ------ | ------ |
| 엔드포인트용 Microsoft Defender | - 끝점 상태 및 원시 이벤트<br />- 바이러스 백신, EDR, 공격 표면 감소를 비롯한 끝점 감지 및 경고<br />- 끝점에서 관찰된 파일 및 기타 엔터티에 대한 정보 | 끝점 |
|Office 365용 Microsoft Defender | - 메일 및 사서함 상태 및 원시 이벤트<br />- 전자 메일, 첨부 파일 및 링크 검색 | - 사서함<br />- Microsoft 365 계정 |
| ID용 Microsoft Defender | - 인증 이벤트를 포함한 Active Directory 신호<br />- ID 관련 동작 감지 | ID |
| Microsoft 클라우드 앱 보안 | - 사용되지 않는 클라우드 앱 및 서비스 검색(섀도 IT)<br />- 클라우드 앱에 데이터 노출<br />- 클라우드 앱과 관련된 위협 활동 | 클라우드 앱 |

## <a name="deploy-the-services"></a>서비스 배포
일반적으로 각 서비스를 배포하려면 테넌트와 일부 초기 구성에 프로비전해야 합니다. 이러한 각 서비스가 배포되는 방법을 이해하기 위해 다음 표를 참조합니다.

| 서비스 | 프로비전 지침 | 초기 구성 |
| ------ | ------ | ------ |
| 엔드포인트용 Microsoft Defender | [엔드포인트용 Microsoft Defender 배포 가이드](../defender-endpoint/deployment-phases.md) | *프로비전 지침 참조* |
|Office 365용 Microsoft Defender | *없음, Office 365로 프로비전됨* | [Office 365용 Microsoft Defender 정책 구성](/microsoft-365/security/office-365-security/defender-for-office-365#configure-atp-policies) |
| Microsoft Defender for Identity | [빠른 시작: Microsoft Defender for Identity 인스턴스 만들기](/azure-advanced-threat-protection/install-atp-step1) | *프로비전 지침 참조* |
| Microsoft 클라우드 앱 보안 | *없음* | [빠른 시작: Microsoft Cloud App Security 시작](/cloud-app-security/getting-started-with-cloud-app-security) |

지원되는 서비스를 배포한 후 를 [Microsoft 365 Defender.](m365d-enable.md)

## <a name="related-topics"></a>관련 항목

- [Microsoft 365 Defender 개요](microsoft-365-defender.md)
- [Microsoft 365 Defender 켜기](m365d-enable.md)
- [끝점용 Microsoft Defender 개요](../defender-endpoint/microsoft-defender-endpoint.md)
- [Microsoft Defender for Office 365 개요](../office-365-security/defender-for-office-365.md)
- [Microsoft Cloud App Security 개요](/cloud-app-security/what-is-cloud-app-security)
- [Microsoft Defender for Identity 개요](/azure-advanced-threat-protection/what-is-atp)
