---
title: 개요 - 고급 헌팅
description: Microsoft 365의 고급 검색 쿼리와 이를 사용하여 네트워크의 위협과 약점을 사전에 찾는 방법에 대해 알아보세요.
keywords: 고급 헌팅, 위협 헌팅, 사이버 위협 헌팅, Microsoft 365 Defender, microsoft 365, m365, 검색, 쿼리, 원격 분석, 사용자 지정 감지, schema, kusto
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: maccruz
author: schmurky
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.custom: seo-marvel-apr2020
ms.technology: m365d
ms.openlocfilehash: b59ff2a32ef5a067576c43b9b0a394590e30b666
ms.sourcegitcommit: d08fe0282be75483608e96df4e6986d346e97180
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/12/2021
ms.locfileid: "59214695"
---
# <a name="proactively-hunt-for-threats-with-advanced-hunting-in-microsoft-365-defender"></a>고급 헌팅을 통해 위협을 사전 예방적으로 Microsoft 365 Defender

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**적용 대상:**
- Microsoft 365 Defender

> Microsoft 365 Defender를 경험해 보고 싶으신가요? [랩 환경에서 평가](m365d-evaluation.md?ocid=cx-docs-MTPtriallab)하거나 [프로덕션에서 파일럿 프로젝트를 실행](m365d-pilot.md?ocid=cx-evalpilot)할 수 있습니다.
>

고급 헌팅은 최대 30일의 원시 데이터를 탐색할 수 있는 쿼리 기반 위협 헌팅 도구입니다. 네트워크의 이벤트를 사전에 검사하여 위협 지표와 엔터티를 찾을 수 있습니다. 데이터에 대한 유연한 액세스를 통해 알려진 위협과 잠재적 위협 모두에 대한 제약이 없는 헌팅을 할 수 있습니다.
<br><br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4Bp7O]

동일한 위협 헌팅 쿼리를 사용하여 사용자 지정 검색 규칙을 만들 수 있습니다. 이러한 규칙은 자동으로 실행되어 의심되는 위반 활동, 잘못 구성된 컴퓨터 및 기타 결과를 확인하고 이에 대응합니다.

이 기능은 [끝점용 Microsoft Defender의](/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-overview) 고급 헌팅과 유사하며 다음에서 더 광범위한 데이터 집합을 검사하는 쿼리를 지원합니다.

- 엔드포인트용 Microsoft Defender
- Office 365용 Microsoft Defender
- Microsoft Cloud App Security
- Microsoft Defender for Identity

고급 헌팅을 사용 하 고 [를 켜면 Microsoft 365 Defender.](m365d-enable.md)

데이터 검색의 고급 헌팅에 Microsoft Cloud App Security 자세한 내용은 비디오를 [참조하세요.](https://www.microsoft.com/en-us/videoplayer/embed/RWFISa) 

## <a name="get-started-with-advanced-hunting"></a>고급 헌팅 시작

고급 헌팅을 빠르게 시작하기 위해 몇 가지 단계를 진행하는 것이 좋습니다.

| 학습 목표 | 설명 | 리소스 |
|--|--|--|
| **언어 학습** | 고급 헌팅은 [Kusto](/azure/kusto/query/)쿼리 언어를 기반으로 하여 동일한 구문과 연산자를 지원합니다. 첫 번째 쿼리를 실행하여 쿼리 언어 학습을 시작합니다. | [쿼리 언어 개요](advanced-hunting-query-language.md) |
| **쿼리 결과 사용 방법 학습** | 결과를 보거나 내보낼 수 있는 차트 및 다양한 방법에 대해 자세히 알아보습니다. 쿼리를 빠르게 조정하고, 드릴다운하여 더 풍부한 정보를 얻고, 응답 작업을 수행할 수 있는 방법을 살펴보고, | - [쿼리 결과 작업](advanced-hunting-query-results.md)<br /> - [쿼리 결과에 대한 작업 수행](advanced-hunting-take-action.md) |
| **스키마의 이해** | 스키마와 해당 열에 있는 테이블에 대한 이해를 높이세요. 쿼리를 구성할 때 데이터를 검색할 위치를 학습합니다. | - [Schema reference](advanced-hunting-schema-tables.md) <br />- [끝점용 Microsoft Defender에서 전환](advanced-hunting-migrate-from-mde.md) |
| **전문가 팁 및 예제 보기** | Microsoft 전문가의 가이드를 통해 무료로 교육합니다. 다양한 위협 헌팅 시나리오를 다루는 미리 정의된 쿼리 모음을 탐색합니다. | - [전문가 교육을 받을 수 있습니다.](advanced-hunting-expert-training.md) <br />- [공유 쿼리 사용](advanced-hunting-shared-queries.md) <br />- [이동 헌트](advanced-hunting-go-hunt.md) <br />- [장치, 전자 메일, 앱 및 ID에서 위협을 찾기](advanced-hunting-query-emails-devices.md) |
| **쿼리 최적화 및 오류 처리** | 효율적이고 오류가 없는 쿼리를 만드는 방법을 이해합니다. | - [쿼리 모범 사례](advanced-hunting-best-practices.md)<br />- [오류 처리](advanced-hunting-errors.md) |
| **사용자 지정 탐지 규칙 만들기** | 고급 헌팅 쿼리를 사용하여 경고를 트리거하고 응답 작업을 자동으로 수행할 수 있는 방법을 이해합니다. | - [사용자 지정 검색 개요](custom-detections-overview.md) <br />- [사용자 지정 검색 규칙](custom-detection-rules.md) |

## <a name="get-access"></a>액세스 액세스
고급 헌팅 또는 [](microsoft-365-defender.md) 기타 Microsoft 365 Defender 사용하려면 고급 헌팅에 적절한 역할이 Azure Active Directory. 고급 헌팅에 필요한 역할 및 사용 [권한에 대해 읽어 읽습니다.](custom-roles.md)

또한 끝점 데이터에 대한 액세스는 끝점용 Microsoft Defender의 RBAC(역할 기반 액세스 제어) 설정에 따라 결정됩니다. [에 대한 액세스 관리에 대해 Microsoft 365 Defender.](m365d-permissions.md)


## <a name="data-freshness-and-update-frequency"></a>데이터 최신성 및 업데이트 빈도
고급 헌팅 데이터는 각각 다르게 통합된 두 가지 유형으로 분류할 수 있습니다.

- **이벤트 또는 활동 데이터**- 경고, 보안 이벤트, 시스템 이벤트 및 일상적인 평가에 대한 테이블을 채우습니다. 고급 헌팅은 이 데이터를 수집한 센서가 해당 클라우드 서비스로 데이터를 성공적으로 전송한 직후에 이 데이터를 수신합니다. 예를 들어 끝점용 Microsoft Defender 및 ID용 Microsoft Defender에서 사용할 수 있는 직후에, 또는 도메인 컨트롤러 또는 작업장에서 정상 센서의 이벤트 데이터를 쿼리할 수 있습니다.
- **엔터티 데이터**- 사용자 및 장치에 대한 정보로 테이블을 채우는 경우 이 데이터는 Active Directory 항목 및 이벤트 로그와 같은 비교적 정적 데이터 원본과 동적 원본에서 모두 제공됩니다. 새 데이터를 제공하기 위해 표는 15분마다 모든 새 정보로 업데이트되어 완전히 채워지지 않을 수 있는 행을 추가합니다. 24시간마다 데이터가 통합되어 각 엔터티에 대한 가장 포괄적인 최신 데이터 집합이 포함된 레코드를 삽입합니다.

## <a name="time-zone"></a>표준 시간대
고급 헌팅의 시간 정보는 UTC 표준 시간대에 있습니다.

## <a name="related-topics"></a>관련 항목
- [쿼리 언어 배우기](advanced-hunting-query-language.md)
- [전문가 교육 받기](advanced-hunting-expert-training.md)
- [공유 쿼리 사용](advanced-hunting-shared-queries.md)
- [스키마의 이해](advanced-hunting-schema-tables.md)
- [쿼리 모범 사례 적용](advanced-hunting-best-practices.md)
- [사용자 지정 검색 개요](custom-detections-overview.md)
