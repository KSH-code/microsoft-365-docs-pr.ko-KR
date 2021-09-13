---
title: 권장 방법 및 속성
description: 최근 경고 중 가장 최근 알림을 검색합니다.
keywords: api, 그래프 api, 지원되는 api, get, alerts, recent
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dolmont
author: DulceMontemayor
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
MS.technology: mde
ms.custom: api
ms.openlocfilehash: d3c29e5112a2cf68452bcb830681dac853eb8e1b
ms.sourcegitcommit: d08fe0282be75483608e96df4e6986d346e97180
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/12/2021
ms.locfileid: "59220327"
---
# <a name="recommendation-resource-type"></a>권장 리소스 유형

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**적용 사항:** [끝점용 Microsoft Defender](https://go.microsoft.com/fwlink/?linkid=2154037)

> Endpoint용 Defender를 경험하고 싶나요? [무료 평가판을 신청하세요.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

[!include[Prerelease information](../../includes/prerelease.md)]

## <a name="methods"></a>메서드

<br>

****

|방법|반환 형식|설명|
|---|---|---|
|[모든 권장 사항 목록](get-all-recommendations.md)|추천 컬렉션|조직에 영향을 주는 모든 보안 권장 사항 목록을 검색합니다.|
|[ID별 권장 사항 가져오기](get-recommendation-by-id.md)|권장 사항|ID로 보안 권장을 검색합니다.|
|[권장 소프트웨어 다운로드](list-recommendation-software.md)|[소프트웨어](software.md)|특정 소프트웨어와 관련된 보안 권장 검색|
|[추천 장치 사용](get-recommendation-machines.md)|MachineRef 컬렉션|보안 권장과 연결된 장치 목록을 검색합니다.|
|[권장 취약성 확인](get-recommendation-vulnerabilities.md)|[취약성](vulnerability.md) 컬렉션|보안 권장과 관련된 취약점 목록을 검색합니다.|
|

## <a name="properties"></a>속성

<br>

****

|속성|유형|설명|
|---|---|---|
|id|문자열|권장 ID|
|productName|문자열|관련 소프트웨어 이름|
|recommendationName|문자열|권장 이름|
|약점|Long|검색된 취약성 수|
|공급업체|String|관련 공급업체 이름|
|recommendedVersion|String|권장 버전|
|recommendedProgram|문자열|권장 프로그램|
|recommendedVendor|String|권장 공급업체|
|recommendationCategory|문자열|권장 범주. 가능한 값은 "계정", "응용 프로그램", "네트워크", "OS", "SecurityControls"입니다.|
|subCategory|문자열|권장 하위 범주|
|severityScore|실수|구성이 조직의 장치에 대한 Microsoft 보안 점수에 미치는 잠재적인 영향(1-10)|
|publicExploit|부울|공용 악용 사용 가능|
|activeAlert|부울|활성 경고가 이 권장과 연결됩니다.|
|associatedThreats|문자열 컬렉션|위협 분석 보고서가 이 권장과 연결됩니다.|
|remediationType|String|수정 유형입니다. 가능한 값은 "ConfigurationChange","Update","Upgrade","Uninstall"입니다.|
|상태|Enum|권장 예외 상태입니다. 가능한 값은 "Active" 및 "Exception"입니다.|
|configScoreImpact|실수|장치에 대한 Microsoft 보안 점수 영향|
|exposureImpact|실수|노출 점수 영향|
|totalMachineCount|Long|설치된 장치 수|
|exposedMachinesCount|Long|취약성에 노출되는 설치된 장치 수|
|nonProductivityImpactedAssets|Long|영향을 받지 않는 장치 수|
|relatedComponent|String|관련 소프트웨어 구성 요소|
|
