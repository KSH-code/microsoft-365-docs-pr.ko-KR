---
title: Microsoft Threat Protection에서 지원 되는 서비스 배포
description: Microsoft Threat Protection, 라이선스 요구 사항 및 배포 절차에 따라 통합 될 수 있는 Microsoft 보안 서비스에 대해 알아봅니다.
keywords: 배포, 라이선스, 지원 서비스, 프로 비전, 구성 Microsoft Threat Protection, M365, 라이선스 자격, Microsoft Defender ATP, MDATP, Office 365 ATP, Azure ATP, Microsoft Cloud App Security, MCAS, advanced Threat Protection, E5, A5, EMS
search.product: eADQiWindows 10XVcnh
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: lomayor
author: lomayor
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.openlocfilehash: 2b0e033bb80fd73d5b5194bd59ab9c9f14a644b3
ms.sourcegitcommit: cc3b64a91e16ccdaa9c338b9a9056dbe3963ba9e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/10/2020
ms.locfileid: "42569053"
---
# <a name="deploy-supported-services"></a>지원 서비스 사용

**적용 대상:**
- Microsoft 위협 방지

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

[Microsoft Threat Protection](microsoft-threat-protection.md) 은 다양 한 Microsoft 보안 서비스를 통합 하 여 정교한 공격에 대 한 중앙 집중식 검색, 예방 및 조사 기능을 제공 합니다. 이 문서에서는 지원 되는 서비스, 라이선스 요구 사항, 하나 이상의 서비스 배포와 관련 된 장점과 제한 사항에 대해 설명 하 고 개별적으로 배포 하는 방법에 대 한 링크를 제공 합니다.

## <a name="supported-services"></a>지원 되는 서비스
[Microsoft 365 E5, E5 Security 또는 A5 라이선스 또는 유효한 라이선스 조합을](prerequisites.md#licensing-requirements) 사용 하면 지원 되는 다음 서비스에 대 한 액세스를 제공 하 고 통해 microsoft 365 보안 센터에서 Microsoft Threat Protection을 사용할 수 있습니다.

| 지원 되는 서비스 | 설명 |
| ------ | ------ |
| Microsoft Defender ATP | 강력한 행태 센서, 클라우드 분석 및 위협 인텔리전스를 기반으로 구축 된 Endpoint protection 제품군 |
| Office 365 ATP | 전자 메일 및 기타 공동 작업 도구를 비롯 하 여 Office 365의 앱 및 데이터에 대 한 고급 보호 기능 |
| Azure ATP | 상호 연관 된 Active Directory 신호를 사용 하 여 advanced threat, 손상 된 id 및 악의적인 참가자에 대 한 보호 |
| Microsoft Cloud App Security | Microsoft 및 타사 클라우드 서비스에서 cyberthreats을 식별 하 고 combats를 사용 합니다. |

## <a name="deployed-services-and-functionality"></a>배포 된 서비스 및 기능
Microsoft 위협 보호를 통해 지원 되는 서비스를 배포 하는 것과 같은 향상 된 가시성, 상관 관계 및 수정이 제공 됩니다.

### <a name="benefits-of-full-deployment"></a>전체 배포의 장점
Microsoft Threat Protection의 전체 이점을 얻으려면 지원 되는 모든 서비스를 배포 하는 것이 좋습니다. 전체 배포의 주요 이점은 다음과 같습니다.
- 사용 가능한 모든 센서 및 서비스 관련 분석 기능에서 발생 하는 경고 및 이벤트 신호의 기반 인시던트 식별 및 상관 관계
- 장치, 사서함 및 사용자 계정을 비롯 한 다양 한 엔터티 유형에 서 자동 조사 및 재구성 (AIR) playbook가 적용 됩니다.
- 장치, 사서함 및 기타 엔터티에서 이벤트 및 엔터티 데이터에 대 한 보다 포괄적인 고급 구하기 스키마를 쿼리할 수 있습니다.

### <a name="limited-deployment-scenarios"></a>제한 된 배포 시나리오
배포 하는 지원 되는 각 서비스는 매우 다양 한 원시 신호의 집합 뿐 아니라 상호 연관 된 정보를 제공 합니다. 제한 된 배포로 인해 Microsoft Threat Protection 기능을 사용 하지 않도록 설정 해도 끝점, 앱, 데이터 및 id에 대 한 포괄적인 가시성을 제공 하는 기능을 사용할 수 없습니다. 동시에 관리 기능은 배포한 서비스에서 관리할 수 있는 엔터티에만 적용 됩니다.

아래 표에는 지원 되는 각 서비스가 추가 데이터를 제공 하는 방법, 데이터를 연관 시켜 추가 정보를 얻을 수 있는 기회, 개선 및 대응 기능에 대 한 자세한 내용이 나와 있습니다.

| 서비스 | 데이터 (상호 연관 & 정보) | 업데이트 관리 & 응답 범위 |
| ------ | ------ | ------ |
| Microsoft Defender ATP | -끝점 상태 및 원시 이벤트<br />-바이러스 백신, EDR, attack surface reduction를 포함 한 끝점 감지 및 경고<br />-끝점에서 관찰 된 파일 및 기타 엔터티에 대 한 정보 | 엔드포인트 |
| Office 365 ATP | -메일 및 사서함 상태 및 원시 이벤트<br />-전자 메일, 첨부 파일 및 링크 감지 | -사서함<br />-Office 365 계정 |
| Azure ATP | -Active Directory 신호 (인증 이벤트 포함)<br />-Id 관련 동작 감지 | ID |
| Microsoft Cloud App Security | -Unsanctioned 클라우드 앱 & 서비스 검색 (섀도 IT)<br />-클라우드 앱에 대 한 데이터 노출<br />-위협 활동 연결 된 클라우드 앱 | 클라우드 앱 |

## <a name="deploy-the-services"></a>서비스 배포
각 서비스를 배포 하려면 일반적으로 테 넌 트 및 몇 가지 초기 구성에 프로 비전을 수행 해야 합니다. 이러한 각 서비스가 배포 되는 방식을 이해 하려면 다음 표를 참조 하십시오.

| 서비스 | 프로 비전 지침 | 초기 구성 |
| ------ | ------ | ------ |
| Microsoft Defender ATP | [Microsoft Defender ATP에 대 한 라이선스 프로비저닝 및 전체 설정 확인](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/licensing) | *프로비저닝 지침 참조* |
| Office 365 ATP | *없음, Office 365와 함께 구축 됨* | [ATP 정책 구성](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp#configure-atp-policies) |
| Azure ATP | [빠른 시작: Azure ATP 인스턴스 만들기](https://docs.microsoft.com/azure-advanced-threat-protection/install-atp-step1) | *프로비저닝 지침 참조* |
| Microsoft Cloud App Security | *없음* | [퀵 스타트: Microsoft Cloud App Security 시작](https://docs.microsoft.com/cloud-app-security/getting-started-with-cloud-app-security) |

지원 되는 서비스를 배포한 후에는 [Microsoft Threat Protection을 켜십시오](mtp-enable.md).

## <a name="related-topics"></a>관련 항목

- [Microsoft 위협 방지 개요](microsoft-threat-protection.md)
- [Microsoft 위협 방지 설정](mtp-enable.md)
- [Microsoft Defender ATP 개요](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection)
- [Office 365 ATP 개요](../office-365-security/office-365-atp.md)
- [Microsoft Cloud App Security 개요](https://docs.microsoft.com/cloud-app-security/what-is-cloud-app-security)
- [Azure ATP 개요](https://docs.microsoft.com/azure-advanced-threat-protection/what-is-atp)
