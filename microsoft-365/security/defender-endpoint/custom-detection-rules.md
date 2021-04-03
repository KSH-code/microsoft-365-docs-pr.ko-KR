---
title: Microsoft Defender ATP에서 사용자 지정 검색 규칙 만들기
ms.reviewer: ''
description: 고급 헌팅 쿼리를 기반으로 사용자 지정 검색 규칙을 만드는 방법 학습
keywords: 사용자 지정 검색, 만들기, 관리, 경고, 편집, 요청 시 실행, 빈도, 간격, 검색 규칙, 고급 헌팅, 헌팅, 쿼리, 응답 작업, mdatp, Microsoft Defender atp
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
ms.date: 09/20/2020
ms.technology: mde
ms.openlocfilehash: 15dec5396a5ba95fe3ec7af5f9a72bbf15e07140
ms.sourcegitcommit: 582555d2b4ef5f2e2494ffdeab2c1d49e5d6b724
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/01/2021
ms.locfileid: "51500493"
---
# <a name="create-custom-detection-rules"></a>사용자 지정 검색 규칙 만들기

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**적용 대상:**
- [엔드포인트용 Microsoft Defender](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

>Endpoint용 Defender를 경험하고 싶나요? [무료 평가판에 등록합니다.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-assignaccess-abovefoldlink)

고급 헌팅 [](advanced-hunting-overview.md) 쿼리로 구축된 사용자 지정 검색 규칙을 사용하면 위반 활동 및 잘못 구성된 장치를 포함하여 다양한 이벤트 및 시스템 상태도 사전적으로 모니터링할 수 있습니다. 이러한 경고를 정기적으로 실행하여 일치하는 경우 경고를 생성하고 응답 작업을 수행할 수 있습니다.

이 문서를 읽고 새 사용자 지정 검색 규칙을 만드는 방법을 배워야 합니다. 또는 [기존 규칙 보기 및 관리를 참조합니다.](custom-detections-manage.md)

> [!NOTE]
> 사용자 지정 검색을 만들거나 관리하려면 역할에 보안 설정 관리 **권한이 필요합니다.** [](user-roles.md#create-roles-and-assign-the-role-to-an-azure-active-directory-group)

## <a name="1-prepare-the-query"></a>1. 쿼리를 준비합니다.

Microsoft Defender 보안 센터에서 고급 헌팅으로 **이동하여** 기존 쿼리를 선택하거나 새 쿼리를 생성합니다. 새 쿼리를 사용할 때 쿼리를 실행하여 오류를 식별하고 가능한 결과를 파악합니다.

>[!IMPORTANT]
>서비스가 너무 많은 경고를 반환하지 않도록 각 규칙은 실행 시 100개의 경고만 생성하는 것으로 제한됩니다. 규칙을 만들기 전에 일반적인 일과 활동에 대한 경고가 표시되지 않도록 쿼리를 조정하십시오.

### <a name="required-columns-in-the-query-results"></a>쿼리 결과의 필수 열

사용자 지정 검색 규칙에 쿼리를 사용하려면 쿼리에서 다음 열을 반환해야 합니다.

- `Timestamp`
- `DeviceId`
- `ReportId`

또는 연산자를 사용하여 결과를 사용자 지정하거나 집계하지 않는 쿼리와 같은 단순 쿼리는 일반적으로 이러한 공통 `project` `summarize` 열을 반환합니다.

보다 복잡한 쿼리에서 이러한 열을 반환하는 방법에는 여러 가지가 있습니다. 예를 들어 별로 집계 및 개수를 계산하려면 각 디바이스와 관련된 가장 최근 이벤트에서 를 반환하여 반환할 `DeviceId` `Timestamp` 수 `ReportId` 있습니다.

아래 샘플 쿼리는 바이러스 백신 검색이 있는 고유 장치( )의 수를 계산하고 이 쿼리를 사용하여 5개가 넘게 검색된 장치만 `DeviceId` 검색합니다. 최신 및 해당 `Timestamp` 을 반환하기 위해 `ReportId` 함수와 함께 `summarize` 연산자를 `arg_max` 사용 합니다.

```kusto
DeviceEvents
| where Timestamp > ago(7d)
| where ActionType == "AntivirusDetection"
| summarize (Timestamp, ReportId)=arg_max(Timestamp, ReportId), count() by DeviceId
| where count_ > 5
```

> [!TIP]
> 쿼리 성능을 향상하기 위해 규칙에 대해 의도한 실행 빈도와 일치하는 시간 필터를 설정하십시오. 최소 자주 실행은 24시간마다이기 때문에 지난 날에 대한 필터링은 모든 새 데이터를 처리합니다.

## <a name="2-create-a-new-rule-and-provide-alert-details"></a>2. 새 규칙을 만들고 경고 세부 정보를 제공합니다.

쿼리 편집기에서 쿼리를 사용하여 검색 규칙 만들기를 **선택하고** 다음 경고 세부 정보를 지정합니다.

- **검색 이름**- 검색 규칙의 이름
- **빈도**- 쿼리를 실행하고 작업을 수행하기 위한 간격입니다. [아래 추가 지침을 참조하세요.](#rule-frequency)
- **경고 제목**- 규칙에 의해 트리거된 경고와 함께 표시되는 제목
- **심각도**- 규칙으로 식별된 구성 요소 또는 활동의 잠재적 위험입니다. [경고 심각도에 대한 읽기](alerts-queue.md#severity)
- **범주**- 위협 구성 요소 또는 활동의 유형(있는 경우)입니다. [경고 범주에 대한 읽기](alerts-queue.md#understanding-alert-categories)
- **MITRE ATT&CK** 기술 - MITRE ATT&CK 프레임워크에 설명된 규칙으로 식별된 하나 이상의 공격 기술입니다. 이 섹션은 맬웨어, 랜섬웨어, 의심스러운 활동 및 원치 않는 소프트웨어와 같은 특정 경고 범주에서 사용할 수 없습니다.
- **설명**- 규칙으로 식별된 구성 요소 또는 활동에 대한 자세한 정보 
- **권장 작업**- 경고에 대한 응답으로 응답할 수 있는 추가 작업

경고 세부 정보가 표시되는 방법에 대한 자세한 내용은 경고 [큐 를 참조하세요.](alerts-queue.md)

### <a name="rule-frequency"></a>규칙 빈도

저장하면 새 사용자 지정 검색 규칙이 즉시 실행되고 지난 30일 동안의 데이터와 일치하는지 검사합니다. 그런 다음 규칙은 선택한 빈도에 따라 고정된 간격 및 콜백 기간에 따라 다시 실행됩니다.

- **24시간마다**-지난 30일간의 데이터를 확인하여 24시간마다 실행
- **12시간마다**-지난 24시간의 데이터를 확인하여 12시간마다 실행
- **3시간마다**-지난 6시간의 데이터를 확인하여 3시간마다 실행
- **매시간**-매시간 실행, 지난 2시간의 데이터 확인

규칙을 편집하면 설정한 빈도에 따라 예약된 다음 런타스에 적용된 변경 내용과 함께 규칙이 실행됩니다.


> [!TIP]
> 쿼리의 시간 필터를 조회 기간과 일치합니다. 콜백 기간 외의 결과는 무시됩니다.

검색을 모니터링할 빈도와 일치하는 빈도를 선택하고 경고에 응답할 조직의 용량을 고려합니다.

## <a name="3-choose-the-impacted-entities"></a>3. 영향을 미치는 엔터티를 선택 합니다.

영향을 받거나 영향을 받는 주 엔터티를 찾을 것으로 예상되는 쿼리 결과의 열을 식별합니다. 예를 들어 쿼리는 장치와 사용자 ID를 모두 반환할 수 있습니다. 이러한 열 중 주요 영향을 미치는 엔터티를 나타내는 열을 식별하면 서비스에서 관련 경고를 집계하고 인시던트의 상관 관계 및 대상 대응 작업을 집계하는 데 도움이 됩니다.

각 엔터티 유형에 대해 하나의 열만 선택할 수 있습니다. 쿼리에서 반환되지 않는 열은 선택할 수 없습니다.

## <a name="4-specify-actions"></a>4. 작업을 지정합니다.

사용자 지정 검색 규칙은 쿼리에서 반환되는 파일 또는 장치에 대해 자동으로 작업을 수행할 수 있습니다.

### <a name="actions-on-devices"></a>디바이스에 대한 작업

이러한 작업은 쿼리 결과의 `DeviceId` 열에 있는 장치에 적용됩니다.

- **장치 격리**- 전체 네트워크 격리가 적용될 경우 장치가 끝점용 Defender 서비스를 제외한 모든 응용 프로그램 또는 서비스에 연결할 수 없습니다. [장치 고리에 대해 자세히 알아보시고](respond-machine-alerts.md#isolate-devices-from-the-network)
- **조사 패키지 수집**- ZIP 파일에 장치 정보를 수집합니다. [조사 패키지에 대해 자세히 알아보시겠습니다.](respond-machine-alerts.md#collect-investigation-package-from-devices)
- **바이러스 백신 검사 실행**-장치에서 전체 Microsoft Defender 바이러스 백신 검사 수행
- **조사 시작**- 디바이스에서 [자동화된](automated-investigations.md) 조사 시작
- **앱 실행 제한**- Microsoft에서 발급한 인증서로 서명된 파일만 실행할 수 있도록 장치에 대한 제한을 설정합니다. [앱 실행 제한에 대한 자세한 정보](respond-machine-alerts.md#restrict-app-execution)

### <a name="actions-on-files"></a>파일에 대한 작업

이러한 작업은 쿼리 결과의 열 또는 파일에 `SHA1` `InitiatingProcessSHA1` 적용됩니다.

- **허용/차단**- 항상 실행되거나 [](manage-indicators.md) 실행이 차단될 수 있도록 파일을 사용자 지정 표시기 목록에 자동으로 추가합니다. 선택한 장치 그룹에서만 수행될 수 있도록 이 작업의 범위를 설정할 수 있습니다. 이 범위는 규칙의 범위와는 독립적입니다.
- **파일 Quarantine -deletes** the file from its current location and places a copy in quarantine

### <a name="actions-on-users"></a>사용자에 대한 작업

- **사용자를 손상된** 것으로 표시 - Azure Active Directory에서 사용자의 위험 수준을 "높음"으로 설정하여 해당 ID 보호 [정책을 트리거합니다.](https://docs.microsoft.com/azure/active-directory/identity-protection/overview-identity-protection#risk-levels)

## <a name="5-set-the-rule-scope"></a>5. 규칙 범위를 설정합니다.

규칙을 적용하는 장치를 지정하기 위해 범위를 설정합니다.

- 모든 장치
- 특정 장치 그룹

범위에 있는 장치의 데이터만 Queried로 처리됩니다. 또한 해당 디바이스에서만 작업이 수행됩니다.

## <a name="6-review-and-turn-on-the-rule"></a>6. 규칙을 검토하고 켜기.

규칙을 검토한 후 만들기를 **선택하여** 저장합니다. 사용자 지정 검색 규칙이 즉시 실행됩니다. 구성된 빈도에 따라 다시 실행하여 일치를 확인하고, 경고를 생성하고, 대응 조치를 취합니다.

사용자 지정 검색 규칙을 [보고 관리하고,](custom-detections-manage.md)이전 실행을 확인하고, 트리거된 경고를 검토할 수 있습니다. 필요한 경우 규칙을 실행하고 수정할 수도 있습니다.

## <a name="related-topics"></a>관련 항목

- [사용자 지정 검색 규칙 보기 및 관리](custom-detections-manage.md)
- [사용자 지정 검색 개요](overview-custom-detections.md)
- [지능형 헌팅 개요](advanced-hunting-overview.md)
- [고급 헌팅 쿼리 언어 알아보기](advanced-hunting-query-language.md)
- [경고 보기 및 구성](alerts-queue.md)
