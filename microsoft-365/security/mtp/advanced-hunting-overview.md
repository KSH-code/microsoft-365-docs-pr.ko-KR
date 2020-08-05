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
ms.collection: M365-security-compliance
ms.topic: article
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: c09047648f1d6bb6d68be78315a876be4998e595
ms.sourcegitcommit: 89178b8f20d59ca88cfca303a13062b91fbeae9d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/04/2020
ms.locfileid: "46552437"
---
# <a name="proactively-hunt-for-threats-with-advanced-hunting-in-microsoft-threat-protection"></a>Microsoft Threat Protection의 고급 헌팅을 통한 위협에 대한 사전 대응

**적용 대상:**
- Microsoft 위협 방지

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

고급 헌팅은 최대 30일간의 원시 데이터를 탐색할 수 있는 쿼리 기반의 위협 헌팅 도구입니다. 네트워크의 이벤트를 사전에 검사하여 흥미로운 지표와 엔티티를 찾을 수 있습니다. 데이터에 대한 유연한 액세스는 알려진 위협과 잠재적 위협 모두에 대한 제한없는 헌팅을 용이하게 합니다.
<p></p>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4Bp7O]

동일한 위협 헌팅 쿼리를 사용하여 사용자 지정 탐지 규칙을 만들 수 있습니다. 이러한 규칙은 침해 활동과 잘못 구성된 컴퓨터를 포함하여 다양한 이벤트와 시스템 상태를 확인하고 이에 응답하도록 자동으로 실행됩니다.

Microsoft 365 보안 센터에서 고급 구하기는 장치, 전자 메일, 앱 및 Microsoft Defender ATP, Office 365 ATP, Microsoft Cloud App Security 및 Azure ATP의 id에 대 한 데이터를 포함 하 여 다양 한 작업 영역의 데이터를 확인 하는 쿼리를 지원 합니다. 고급 헌팅을 사용하려면 [Microsoft Threat Protection](mtp-enable.md)을 설정합니다.

## <a name="get-started-with-advanced-hunting"></a>고급 헌팅 시작

고급 헌팅을 빠르게 시작하고 실행하려면 몇가지 단계를 수행하는 것이 좋습니다.

| 학습 목표 | 설명 | 리소스 |
|--|--|--|
| **언어에 대한 느낌을 받아보세요.** | 고급 구하기는 [Kusto 쿼리 언어](https://docs.microsoft.com/azure/kusto/query/)를 기반으로 하며 같은 구문 및 연산자를 지원 합니다. 첫 번째 쿼리를 실행하여 쿼리 언어 학습을 시작합니다. | [쿼리 언어 개요](advanced-hunting-query-language.md) |
| **쿼리 결과 사용 방법 알아보기** | 결과를 보거나 내보낼 수 있는 다양 한 방법과 차트에 대해 알아봅니다. 쿼리를 빠르게 조정 하 고 드릴 다운 하 여 더 많은 정보를 얻고 응답 작업을 수행 하는 방법을 알아봅니다. | - [쿼리 결과 작업](advanced-hunting-query-results.md)<br>- [쿼리 결과에 대 한 작업 수행](advanced-hunting-take-action.md) |
| **스키마의 이해** | 스키마와 해당 열에 있는 테이블에 대한 이해를 높이세요. 이는 데이터를 찾을 위치와 쿼리를 구성하는 방법을 결정하는 데 도움이 됩니다. | [스키마 참조](advanced-hunting-schema-tables.md) |
| **미리 정의 된 쿼리 활용** | 다양한 위협 헌팅 시나리오를 다루는 미리 정의된 쿼리 모음을 탐색합니다. | - [공유 쿼리 사용](advanced-hunting-shared-queries.md)<br>- [헌트](advanced-hunting-go-hunt.md) |
| **쿼리 최적화** | 전자 메일 및 장치에서 데이터를 결합하는 효율적인 쿼리 및 쿼리를 만드는 방법에 대해 알아봅니다. | - [쿼리 모범 사례](advanced-hunting-shared-queries.md) <br>- [장치 및 전자 메일 간 헌트](advanced-hunting-best-practices.md) |
| **사용자 지정 검색 규칙 만들기** | 고급 구하기 쿼리를 사용 하 여 알림을 트리거하고 응답 작업을 자동으로 적용 하는 방법을 이해 합니다. | - [사용자 지정 검색 개요](custom-detections-overview.md)<br>- [사용자 지정 검색 규칙](custom-detection-rules.md) |

## <a name="get-access"></a>액세스 권한
고급 구하기 또는 기타 [Microsoft 위협 방지](microsoft-threat-protection.md) 기능을 사용 하려면 Azure AD에서 적절 한 역할을 할당 받아야 합니다. 끝점 데이터에 대 한 액세스는 Microsoft Defender ATP에서 역할 기반 액세스 제어 설정의 영향을 받습니다. [Microsoft Threat Protection 액세스 관리에 대해 자세히 알아봅니다.](mtp-permissions.md)

## <a name="data-freshness-and-update-frequency"></a>데이터 유효성 및 업데이트 빈도
고급 구하기 데이터는 서로 다르게 통합 되는 두 가지 형식으로 분류할 수 있습니다.

- **이벤트 또는 활동 데이터** -경고, 보안 이벤트, 시스템 이벤트 및 루틴 평가에 대 한 표를 채웁니다. 고급 사냥은 해당 클라우드 서비스에 성공적으로 전송 하기 위해 수집한 센서 바로 다음에이 데이터를 받습니다. 예를 들어, 워크스테이션 또는 도메인 컨트롤러의 정상 센서에서 이벤트 데이터를 Microsoft Defender ATP 및 Azure ATP에서 사용할 수 있게 되는 즉시 쿼리를 시작할 수 있습니다.
- **엔터티 데이터** -사용자 및 장치에 대 한 통합 된 정보를 사용 하 여 표를 채웁니다. 이 데이터는 Active Directory 항목과 같은 비교적 정적인 데이터 원본 모두와 이벤트 로그 같은 동적 원본에서 가져옵니다. 새로운 데이터를 제공 하기 위해 테이블은 새 정보를 사용 하 여 15 분 마다 업데이트 되며 완전히 채워지지 않을 수도 있는 행을 추가 합니다. 24 시간 마다 데이터를 통합 하 여 각 엔터티에 대 한 가장 포괄적인 최신 데이터 집합을 포함 하는 레코드를 삽입 합니다.

## <a name="related-topics"></a>관련 항목
- [쿼리 언어 배우기](advanced-hunting-query-language.md)
- [쿼리 결과 작업](advanced-hunting-query-results.md)
- [쿼리 결과에 대 한 작업 수행](advanced-hunting-take-action.md)
- [공유 쿼리 사용](advanced-hunting-shared-queries.md)
- [여러 장치 및 전자 메일에서 위협을 탐지](advanced-hunting-query-emails-devices.md)
- [스키마의 이해](advanced-hunting-schema-tables.md)
- [쿼리 모범 사례 적용](advanced-hunting-best-practices.md)
- [사용자 지정 검색 개요](custom-detections-overview.md)
