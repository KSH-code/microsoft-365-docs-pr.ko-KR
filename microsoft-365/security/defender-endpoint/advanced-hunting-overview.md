---
title: 끝점용 Microsoft Defender의 고급 헌팅 개요
description: 끝점용 Microsoft Defender의 위협 헌팅 기능을 사용하여 네트워크에서 위협과 약점을 찾는 쿼리를 작성합니다.
keywords: 고급 헌팅, 위협 헌팅, 사이버 위협 헌팅, mdatp, Microsoft Defender atp, 끝점용 Microsoft Defender, wdatp, 검색, 쿼리, 원격 분석, 사용자 지정 감지, schema, kusto, 표준 시간대, UTC
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: maccruz
author: schmurky
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 6d051666e481bcf74038dc5000ebaadbd142d429
ms.sourcegitcommit: d08fe0282be75483608e96df4e6986d346e97180
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/12/2021
ms.locfileid: "59187651"
---
# <a name="proactively-hunt-for-threats-with-advanced-hunting"></a>고급 헌팅을 통해 위협을 사전 대응

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**적용 대상:**
- [엔드포인트용 Microsoft Defender](https://go.microsoft.com/fwlink/?linkid=2154037)

> Endpoint용 Defender를 경험하고 싶나요? [무료 평가판을 신청하세요.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-advancedhunting-abovefoldlink)

고급 헌팅은 최대 30일간의 원시 데이터를 탐색할 수 있는 쿼리 기반의 위협 헌팅 도구입니다. 네트워크의 이벤트를 사전에 검사하여 위협 지표와 엔터티를 찾을 수 있습니다. 데이터에 대한 유연한 액세스를 통해 알려진 위협과 잠재적 위협 모두에 대한 제약이 없는 헌팅을 할 수 있습니다.

이 비디오를 통해 고급 헌팅에 대한 간략한 개요와 빠르게 시작할 수 있는 간단한 자습서를 확인할 수 있습니다.

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4bGqo]

동일한 위협 헌팅 쿼리를 사용하여 사용자 지정 탐지 규칙을 만들 수 있습니다. 이러한 규칙은 자동으로 실행되어 의심되는 위반 활동, 잘못 구성된 컴퓨터 및 기타 결과를 확인하고 이에 대응합니다.

> [!TIP]
> 고급 [헌팅을](/microsoft-365/security/defender/advanced-hunting-overview) Microsoft 365 Defender 끝점용 Defender, microsoft Defender for Office 365, Microsoft Cloud App Security Id에 대한 Microsoft Defender의 데이터를 사용하여 위협을 헌팅합니다. [를 Microsoft 365 Defender.](/microsoft-365/security/defender/m365d-enable)

끝점용 Microsoft Defender에서 고급 헌팅 워크플로를 끝점용 Microsoft [Defender로](/microsoft-365/security/defender/advanced-hunting-migrate-from-mde)이동하는 Microsoft 365 Defender Microsoft Defender에서 고급 헌팅 쿼리 마이그레이션에서 자세히 알아보하세요.

## <a name="get-started-with-advanced-hunting"></a>고급 헌팅 시작

다음 단계에 따라 고급 헌팅 지식을 쌓아가세요.

고급 헌팅을 빠르게 시작하고 실행하려면 몇가지 단계를 수행하는 것이 좋습니다.

<br>

****

|학습 목표|설명|리소스|
|---|---|---|
|**언어 학습**|고급 헌팅은 [Kusto](/azure/kusto/query/)쿼리 언어를 기반으로 하여 동일한 구문과 연산자를 지원합니다. 첫 번째 쿼리를 실행하여 쿼리 언어 학습을 시작합니다.|[쿼리 언어 개요](advanced-hunting-query-language.md)|
|**쿼리 결과 사용 방법 학습**|결과를 보거나 내보낼 수 있는 차트 및 다양한 방법에 대해 자세히 알아보습니다. 보다 풍부한 정보를 얻을 수 있도록 쿼리를 빠르게 조정하고 드릴다운하는 방법을 살펴보아야 합니다.|[쿼리 결과로 작업](advanced-hunting-query-results.md)|
|**스키마의 이해**|스키마와 해당 열에 있는 테이블에 대한 이해를 높이세요. 쿼리를 구성할 때 데이터를 검색할 위치를 학습합니다.|[스키마 참조](advanced-hunting-schema-reference.md)|
|**미리 정의된 쿼리 사용**|다양한 위협 헌팅 시나리오를 다루는 미리 정의된 쿼리 모음을 탐색합니다.|[공유 쿼리](advanced-hunting-shared-queries.md)|
|**쿼리 최적화 및 오류 처리**|효율적이고 오류가 없는 쿼리를 만드는 방법을 이해합니다.|[쿼리 모범 사례](advanced-hunting-best-practices.md) <p> [오류 처리](advanced-hunting-errors.md)|
|**가장 완전한 적용 범위 얻기**|감사 설정을 사용하여 조직에 더 나은 데이터 범위를 제공합니다.|[고급 헌팅 범위 확장](advanced-hunting-extend-data.md)|
|**빠른 조사 실행**|고급 헌팅 쿼리를 빠르게 실행하여 의심스러운 활동을 조사합니다.|[이동 헌트로 엔터티 또는 이벤트 정보를 빠르게 *헌팅*](advanced-hunting-go-hunt.md)|
|**위협 및 해결 손상 포함**|파일을 검색하고, 앱 실행을 제한하고, 기타 작업을 수행하여 공격에 대응|[고급 헌팅 쿼리 결과에 대한 작업 수행](advanced-hunting-take-action.md)|
|**사용자 지정 탐지 규칙 만들기**|고급 헌팅 쿼리를 사용하여 경고를 트리거하고 응답 작업을 자동으로 수행할 수 있는 방법을 이해합니다.|[사용자 지정 검색 개요](overview-custom-detections.md) <p> [사용자 지정 검색 규칙](custom-detection-rules.md)|
|

## <a name="data-freshness-and-update-frequency"></a>데이터 최신성 및 업데이트 빈도

고급 헌팅 데이터는 각각 다르게 통합된 두 가지 유형으로 분류할 수 있습니다.

- **이벤트 또는 활동 데이터:** 경고, 보안 이벤트, 시스템 이벤트 및 일상적인 평가에 대한 테이블을 채우습니다. 고급 헌팅은 이를 수집하는 센서가 끝점용 Defender로 성공적으로 전송된 직후에 이 데이터를 수신합니다.
- **엔터티 데이터:** 사용자 및 장치에 대한 통합 정보로 테이블을 채우습니다. 이 데이터는 Active Directory 항목 및 이벤트 로그와 같은 비교적 정적 데이터 원본과 동적 원본에서 모두 제공됩니다. 새 데이터를 제공하기 위해 표는 15분마다 모든 새 정보로 업데이트되어 완전히 채워지지 않을 수 있는 행을 추가합니다. 24시간마다 데이터가 통합되어 각 엔터티에 대한 가장 포괄적인 최신 데이터 집합이 포함된 레코드를 삽입합니다.

## <a name="time-zone"></a>표준 시간대

고급 헌팅의 시간 정보는 현재 UTC 표준 시간대에 있습니다.

## <a name="related-topics"></a>관련 항목

- [쿼리 언어 배우기](advanced-hunting-query-language.md)
- [쿼리 결과로 작업](advanced-hunting-query-results.md)
- [공유 쿼리 사용](advanced-hunting-shared-queries.md)
- [스키마의 이해](advanced-hunting-schema-reference.md)
- [쿼리 모범 사례 적용](advanced-hunting-best-practices.md)
- [사용자 지정 검색 개요](overview-custom-detections.md)
- [Storage 계정 개요](/azure/storage/common/storage-account-overview)
- [Azure 이벤트 허브 — 빅 데이터 스트리밍 플랫폼 및 이벤트 수집 서비스](/azure/event-hubs/event-hubs-about)
