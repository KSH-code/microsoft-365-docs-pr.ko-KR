---
title: 개요-고급 구하기
description: Microsoft 365의 고급 검색 쿼리와 이를 사용하여 네트워크의 위협과 약점을 사전에 찾는 방법에 대해 알아보세요.
keywords: 고급 구하기, 위협 검색, 사이버 위협 요소 검색, microsoft threat protection, microsoft 365, mtp, m365, 검색, 쿼리, 원격 분석, 사용자 지정 검색, 스키마, kusto, microsoft 365 및 microsoft Threat Protection
search.product: eADQiWindows 10XVcnh
search.appverid: met150
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
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: a059c4dd1f09bc5101f5ebb027c92e6551ca8dd6
ms.sourcegitcommit: de600339b08951d6dd3933288a8da2327a4b6ef3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/13/2020
ms.locfileid: "48430424"
---
# <a name="proactively-hunt-for-threats-with-advanced-hunting-in-microsoft-threat-protection"></a>Microsoft Threat Protection의 고급 헌팅을 통한 위협에 대한 사전 대응

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**적용 대상:**
- Microsoft 위협 방지

고급 헌팅은 최대 30일간의 원시 데이터를 탐색할 수 있는 쿼리 기반의 위협 헌팅 도구입니다. 네트워크에서 이벤트를 사전에 검사 하 여 위협 지표 및 엔터티를 찾을 수 있습니다. 데이터에 대 한 유연한 액세스를 통해 알려진 위협과 잠재적인 위협 모두에 대해 제한 되지 않은 방법을 사용할 수 있습니다.
<p></p>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4Bp7O]

동일한 위협 헌팅 쿼리를 사용하여 사용자 지정 탐지 규칙을 만들 수 있습니다. 이러한 규칙은 의심 스러운 위반 활동, 잘못 구성 된 컴퓨터 및 기타 결과를 확인 한 후에 응답 하기 위해 자동으로 실행 됩니다.

이 기능은 [Microsoft DEFENDER ATP의 고급 구하기](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-overview)와 비슷합니다. Microsoft 365 보안 센터에서 제공 되는이 기능은 보다 광범위 한 데이터 집합을 확인 하는 쿼리를 지원 합니다.

- Microsoft Defender Advanced Threat Protection
- Office 365 Advanced Threat Protection
- Microsoft Cloud App Security
- Azure Advanced Threat Protection

고급 헌팅을 사용하려면 [Microsoft Threat Protection](mtp-enable.md)을 설정합니다.

## <a name="get-started-with-advanced-hunting"></a>고급 헌팅 시작

고급 구하기를 빠르게 시작 하려면 몇 가지 단계를 진행 하는 것이 좋습니다.

| 학습 목표 | 설명 | 리소스 |
|--|--|--|
| **언어 이해** | 고급 구하기는 [Kusto 쿼리 언어](https://docs.microsoft.com/azure/kusto/query/)를 기반으로 하며 같은 구문 및 연산자를 지원 합니다. 첫 번째 쿼리를 실행하여 쿼리 언어 학습을 시작합니다. | [쿼리 언어 개요](advanced-hunting-query-language.md) |
| **쿼리 결과 사용 방법 알아보기** | 결과를 보거나 내보낼 수 있는 다양 한 방법과 차트에 대해 알아봅니다. 쿼리를 빠르게 조정 하 고 드릴 다운 하 여 더 많은 정보를 얻고 응답 작업을 수행 하는 방법을 알아봅니다. | - [쿼리 결과 작업](advanced-hunting-query-results.md)<br>- [쿼리 결과에 대 한 작업 수행](advanced-hunting-take-action.md) |
| **스키마의 이해** | 스키마와 해당 열에 있는 테이블에 대한 이해를 높이세요. 쿼리를 만들 때 데이터를 찾을 위치를 알아봅니다. | - [스키마 참조](advanced-hunting-schema-tables.md)<br>- [Microsoft Defender ATP에서 전환](advanced-hunting-migrate-from-mdatp.md) |
| **전문가의 팁 및 예제 보기** | Microsoft 전문가가 제공 하는 가이드를 무료로 학습 합니다. 다양한 위협 헌팅 시나리오를 다루는 미리 정의된 쿼리 모음을 탐색합니다. | - [전문 교육 받기](advanced-hunting-expert-training.md)<br>- [공유 쿼리 사용](advanced-hunting-shared-queries.md)<br>- [헌트](advanced-hunting-go-hunt.md)<br>- [장치, 전자 메일, 앱 및 id 간의 위협 구하기](advanced-hunting-query-emails-devices.md) |
| **쿼리 최적화 및 오류 처리** | 효율적이 고 오류 없는 쿼리를 만드는 방법에 대해 알아봅니다. | - [쿼리 모범 사례](advanced-hunting-best-practices.md)<br>- [오류 처리](advanced-hunting-errors.md) |
| **사용자 지정 검색 규칙 만들기** | 고급 구하기 쿼리를 사용 하 여 알림을 트리거하고 응답 작업을 자동으로 수행 하는 방법을 이해 합니다. | - [사용자 지정 검색 개요](custom-detections-overview.md)<br>- [사용자 지정 검색 규칙](custom-detection-rules.md) |

## <a name="get-access"></a>액세스 권한
고급 구하기 또는 기타 [Microsoft 위협 방지](microsoft-threat-protection.md) 기능을 사용 하려면 Azure Active Directory에 적절 한 역할이 있어야 합니다. 또한 끝점 데이터에 대 한 액세스는 Microsoft Defender ATP의 RBAC (역할 기반 액세스 제어) 설정에 의해 결정 됩니다. [Microsoft Threat Protection 액세스 관리에 대해 자세히 알아봅니다.](mtp-permissions.md)

## <a name="data-freshness-and-update-frequency"></a>데이터 유효성 및 업데이트 빈도
고급 구하기 데이터는 서로 다르게 통합 되는 두 가지 형식으로 분류할 수 있습니다.

- **이벤트 또는 활동 데이터**-경고, 보안 이벤트, 시스템 이벤트 및 루틴 평가에 대 한 표를 채웁니다. 고급 사냥은 해당 클라우드 서비스에 성공적으로 전송 하기 위해 수집한 센서 바로 다음에이 데이터를 받습니다. 예를 들어 워크스테이션 또는 도메인 컨트롤러의 정상 센서에서 이벤트 데이터를 Microsoft Defender ATP 및 Azure ATP에서 사용 가능 하 게 되는 즉시 쿼리할 수 있습니다.
- **엔터티 데이터**-사용자 및 장치에 대 한 정보로 표를 채웁니다. 이 데이터는 상대적으로 정적인 데이터 원본과 Active Directory 항목 및 이벤트 로그 같은 동적 원본 모두에서 제공 됩니다. 새로운 데이터를 제공 하기 위해 테이블은 15 분 마다 새 정보로 업데이트 되어 완전히 채워지지 않을 수 있는 행을 추가 합니다. 24 시간 마다 데이터를 통합 하 여 각 엔터티에 대 한 가장 포괄적인 최신 데이터 집합을 포함 하는 레코드를 삽입 합니다.

## <a name="time-zone"></a>표준 시간대
고급 구하기의 시간 정보는 UTC 표준 시간대입니다.

## <a name="related-topics"></a>관련 항목
- [쿼리 언어 배우기](advanced-hunting-query-language.md)
- [전문가 교육 받기](advanced-hunting-expert-training.md)
- [공유 쿼리 사용](advanced-hunting-shared-queries.md)
- [스키마의 이해](advanced-hunting-schema-tables.md)
- [쿼리 모범 사례 적용](advanced-hunting-best-practices.md)
- [사용자 지정 검색 개요](custom-detections-overview.md)

