---
title: 위협 분석의 분석 보고서 섹션을 이해합니다.
ms.reviewer: ''
description: 위협 분석 보고서의 보고서 섹션에서 위협, 완화, 검색, 고급 헌팅 쿼리에 대한 정보를 제공하는 방법
keywords: 분석 보고서, 위협 분석, 검색, 고급 헌팅 쿼리, 완화,
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: maccruz
author: schmurky
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 49a0b34fb278fbb517bcfecc9d9e524d669029e3
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/06/2021
ms.locfileid: "60195188"
---
# <a name="the-analyst-report-in-threat-analytics"></a>위협 분석의 분석가 보고서

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**적용 대상:**
- [엔드포인트용 Microsoft Defender](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> 엔드포인트용 Microsoft Defender를 경험하고 싶으신가요? [무료 평가판을 신청하세요.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)

각 [위협 분석 보고서에는](threat-analytics.md) 동적 섹션과 분석 보고서라는 포괄적인 서면 _섹션이 포함되어 있습니다._ 이 섹션에 액세스하려면 추적된 위협에 대한 보고서를 열고 분석가 보고서 **탭을** 선택합니다.

![위협 분석 보고서의 분석 보고서 섹션 이미지입니다.](images/ta-analyst-report-small.png)

_위협 분석 보고서의 분석가 보고서 섹션_

## <a name="scan-the-analyst-report"></a>분석가 보고서 검사

분석 보고서의 각 섹션은 실행 가능한 정보를 제공하도록 디자인됩니다. 보고서는 다르지만 대부분의 보고서에는 다음 표에 설명된 섹션이 포함됩니다.

<br>

****

|보고서 섹션|설명|
|---|---|
|요약|위협이 처음 확인된 경우, 그 동기, 중요한 이벤트, 주요 대상 및 고유한 도구와 기술을 포함하여 위협에 대한 개요 이 정보를 사용하여 산업, 지리적 위치 및 네트워크 컨텍스트에서 위협의 우선 순위를 지정하는 방법을 추가로 평가할 수 있습니다.|
|분석|공격의 세부 정보와 공격자가 새로운 기술 또는 공격 표면을 활용하는 방법을 포함하여 위협에 대한 기술 정보|
|MITRE ATT&CK 기술 관찰|관찰된 기술이 [MITRE ATT](https://attack.mitre.org/) 및 CK 공격&매핑되는 방법|
|[완화](#apply-additional-mitigations)|권장 사항 영향을 중지하거나 줄이는 데 도움이 될 수 있는 요소입니다. 이 섹션에는 위협 분석 보고서의 일부로 동적으로 추적되지 않는 완화 기능도 포함되어 있습니다.|
|[검색 세부 정보](#understand-how-each-threat-can-be-detected)|위협과 관련된 활동 또는 구성 요소를 표면화할 수 있는 Microsoft 보안 솔루션에서 제공하는 특정 및 일반 감지.|
|[지능형 헌팅](#find-subtle-threat-artifacts-using-advanced-hunting)|[고급 헌팅은 가능한](advanced-hunting-overview.md) 위협 활동을 사전 식별하기 위한 쿼리입니다. 대부분의 쿼리는 검색을 보완하기 위해 제공됩니다. 특히 악의적인 것으로 동적으로 평가할 수 없는 잠재적으로 악의적인 구성 요소 또는 동작을 찾기 위한 쿼리가 제공됩니다.|
|참조|보고서를 작성하는 동안 분석가가 참조하는 Microsoft 및 타사 발행물 위협 분석 콘텐츠는 Microsoft 연구원이 유효성을 검사한 데이터를 기반으로 합니다. 공개적으로 사용 가능한 타사 원본의 정보는 명확하게 식별됩니다.|
|로그 변경|보고서가 게시된 시간 및 보고서가 크게 변경된 시간입니다.|
|

## <a name="apply-additional-mitigations"></a>추가 완화 적용

위협 분석은 보안 업데이트 및 보안 구성의 상태를 [동적으로 추적합니다.](threat-analytics.md#mitigations-review-list-of-mitigations-and-the-status-of-your-devices) 이 정보는 완화 탭의 차트 및 **표로 사용할 수** 있습니다.

이러한 추적된 완화 외에도 분석가 보고서에서는 동적으로 모니터링되지 않는 완화에 _대해_ 논의합니다. 다음은 동적으로 추적되지 않는 중요한 완화의 몇 가지 예입니다.

- _.lnk_ 첨부 파일 또는 기타 의심스러운 파일 형식이 있는 전자 메일 차단
- 로컬 관리자 암호 임의로 설정
- 최종 사용자에게 피싱 전자 메일 및 기타 위협 벡터 교육
- 특정 공격 [표면 감소 규칙 켜기](attack-surface-reduction.md)

완화 탭을  사용하여 위협에 대한 보안 상태를 평가할 수 있는 반면, 이러한 권장 사항을 통해 보안 상태를 개선하기 위한 추가 단계를 취할 수 있습니다. 분석가 보고서의 모든 완화 지침을 신중하게 읽고 가능한 경우 적용합니다.

## <a name="understand-how-each-threat-can-be-detected"></a>각 위협을 검색할 수 있는 방법 이해

또한 분석 보고서는 Microsoft Defender 바이러스 백신 및 끝점  감지 및 응답(EDR) 기능의 검색을 제공합니다.

### <a name="antivirus-detections"></a>바이러스 백신 검색

이러한 검색은 장치가 켜져 있는 [장치에서 Microsoft Defender 바이러스 백신](/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-antivirus-in-windows-10) 있습니다. 끝점용 Microsoft Defender에 온보딩된 장치에서 이러한 검색이 발생하면 보고서의 차트를 밝게 하는 경고도 트리거합니다.

> [!NOTE]
> 또한 분석가 보고서에는 추적된 위협과 관련한 구성 요소 또는 동작 외에도 광범위한 위협을 식별할 수 있는 일반 탐지가 나열됩니다.  이러한 일반 검색은 차트에 반영되지 않습니다.

### <a name="endpoint-detection-and-response-edr-alerts"></a>끝점 감지 및 응답(EDR) 경고

EDR [Microsoft Defender for Endpoint에](onboard-configure.md)온보딩된 장치에 대해 경고가 표시됩니다. 이러한 경고는 일반적으로 Microsoft Defender for Endpoint 센서 및 강력한 신호 원본 역할을 하는 기타 끝점 기능(예: 바이러스 백신, 네트워크 보호, 변조 보호)에 의해 수집된 보안 신호에 따라 표시됩니다.

바이러스 백신 검색 목록과 마찬가지로 일부 EDR 경고는 추적된 위협과 연결되지 않을 수 있는 의심스러운 동작에 일반적으로 플래그를 지정하도록 디자인되어 있습니다. 이러한 경우 보고서는 경고를 "일반"으로 명확하게 식별하고 보고서의 차트에 영향을주지 않습니다.

## <a name="find-subtle-threat-artifacts-using-advanced-hunting"></a>고급 헌팅을 사용하여 미묘한 위협 요소 찾기

검색을 통해 추적된 위협을 자동으로 식별하고 중지할 수 있는 반면, 많은 공격 활동은 추가 검사가 필요한 미묘한 추적을 남길 수 있습니다. 일부 공격 활동은 정상일 수도 있는 동작을 나타내기 때문에 동적으로 감지하면 작동 노이즈가 발생하거나 오탐지가 발생할 수 있습니다.

[고급 헌팅은](advanced-hunting-overview.md) 위협 활동의 미묘한 표시기를 쉽게 찾은 Kusto 쿼리 언어를 기반으로 하는 쿼리 인터페이스를 제공합니다. 또한 상황 정보를 표시하고 지표가 위협에 연결되어 있는지 여부를 확인할 수 있습니다.

분석가 보고서의 고급 헌팅 쿼리는 Microsoft 분석가에 의해 검색되어 고급 헌팅 쿼리 편집기에서 실행할 [준비가 완료되었습니다.](https://securitycenter.windows.com/advanced-hunting) 또한 쿼리를 사용하여 향후 [](custom-detection-rules.md) 일치 시 경고를 트리거하는 사용자 지정 검색 규칙을 만들 수도 있습니다.

## <a name="related-topics"></a>관련 항목

- [위협 분석 개요](threat-analytics.md)
- [고급 헌팅을 통해 위협을 사전 대응적으로 찾기](advanced-hunting-overview.md)
- [사용자 지정 검색 규칙](custom-detection-rules.md)
- 