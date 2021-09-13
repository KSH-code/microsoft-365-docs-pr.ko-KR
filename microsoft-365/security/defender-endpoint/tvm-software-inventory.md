---
title: 소프트웨어 인벤토리의 위협 및 취약성 관리
description: Endpoint용 Microsoft Defender for Endpoint 위협 및 취약성 관리 소프트웨어 인벤토리 페이지에는 소프트웨어에서 감지된 약점 및 취약성의 수가 표시됩니다.
keywords: 위협 및 취약성 관리, Endpoint용 Microsoft Defender, Endpoint용 Microsoft Defender 소프트웨어 인벤토리, Endpoint 위협 & 취약성 관리용 Microsoft Defender, Endpoint 위협 & 취약성 관리 소프트웨어 인벤토리, Endpoint tvm용 Microsoft Defender 소프트웨어 인벤토리, tvm 소프트웨어 인벤토리
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 333cacf1bce50463fdfbac4023ae724a7564809c
ms.sourcegitcommit: d08fe0282be75483608e96df4e6986d346e97180
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/12/2021
ms.locfileid: "59220205"
---
# <a name="software-inventory---threat-and-vulnerability-management"></a>소프트웨어 인벤토리 - 위협 및 취약성 관리

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**적용 대상:**
- [엔드포인트용 Microsoft Defender](https://go.microsoft.com/fwlink/?linkid=2154037)
- [위협 및 취약성 관리](next-gen-threat-and-vuln-mgt.md)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Endpoint용 Defender를 경험하고 싶나요? [무료 평가판을 신청하세요.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-portaloverview-abovefoldlink)

위협 및 취약성 관리 소프트웨어 인벤토리는 공식 [CPE(Common Platform Enumerations)가](https://nvd.nist.gov/products/cpe)있는 조직의 알려진 소프트웨어 목록입니다. 공식 CPE가 없는 소프트웨어 제품에는 취약점이 게시되지 않습니다. 또한 공급업체 이름, 약점 수, 위협, 노출된 장치 수 등의 세부 정보도 포함됩니다.

## <a name="how-it-works"></a>작업 방법

검색 필드에서는 끝점 감지 및 응답 기능에 대한 Microsoft Defender의 감지 및 취약점 평가를 담당하는 동일한 신호 집합을 [활용하고 있습니다.](overview-endpoint-detection-response.md)

실시간이기 때문에 발견된 취약성 정보를 몇 분 만에 볼 수 있습니다. 엔진이 여러 보안 피드에서 정보를 자동으로 잡습니다. 실제로 특정 소프트웨어가 라이브 위협 캠페인에 연결되어 있는지를 볼 수 있습니다. 또한 위협 분석 보고서가 사용 가능해지자마자 링크를 제공합니다.

## <a name="navigate-to-the-software-inventory-page"></a>소프트웨어 인벤토리 페이지로 이동합니다.

웹 사이트 포털의 위협 및 취약성 관리  메뉴에서 소프트웨어 인벤토리를 선택하여 소프트웨어 [인벤토리 페이지에 Microsoft 365 Defender 액세스합니다.](portal-overview.md)

장치 목록에서 개별 디바이스 페이지의 특정 디바이스에서 소프트웨어를 [볼 수 있습니다.](machines-view-overview.md)

>[!NOTE]
>Microsoft Defender for Endpoint 전역 검색을 사용하여 소프트웨어를 검색하는 경우 공백 대신 밑면을 넣어야 합니다. 예를 들어 최상의 검색 결과를 위해 "windows_10" 대신 "Windows 10"를 작성합니다.

## <a name="software-inventory-overview"></a>소프트웨어 인벤토리 개요

소프트웨어 **인벤토리** 페이지는 공급업체 이름, 발견된 약점, 관련된 위협, 노출 장치, 노출 점수에 미치는 영향, 태그를 포함하여 네트워크에 설치된 소프트웨어 목록으로 열립니다.

소프트웨어에서 발견된 약점, 관련된 위협 및 소프트웨어가 지원 종료에 도달한지 여부와 같은 태그를 기준으로 목록 보기를 필터링할 수 있습니다.

:::image type="content" alt-text="소프트웨어 인벤토리 방문 페이지의 예입니다." source="images/tvm-software-inventory.png" lightbox="images/tvm-software-inventory.png":::

조사할 소프트웨어를 선택합니다. 플라이아웃 패널은 페이지에 있는 정보를 보다 컴팩트하게 볼 수 있는 보기로 열립니다. 조사를 더 깊이 진행하고 소프트웨어 페이지 열기를 선택하거나 부정확성 보고를 선택하여 기술 불일치에 플래그를 지정합니다. 

### <a name="software-that-isnt-supported"></a>지원되지 않는 소프트웨어

위협 요소에 의해 현재 지원되지 & 취약성 관리 소프트웨어 인벤토리 페이지에 있을 수 있습니다. 지원되지 않는 경우 제한된 데이터만 사용할 수 있습니다. "약점" 섹션의 "사용할 수 없는" 옵션을 사용하여 지원되지 않는 소프트웨어로 필터링합니다.

:::image type="content" alt-text="지원되지 않는 소프트웨어 필터입니다." source="images/tvm-unsupported-software-filter.png" lightbox="images/tvm-unsupported-software-filter.png":::

다음은 소프트웨어가 지원되지 않는다는 것입니다.

- 약점 필드에 "사용할 수 없습니다."가 표시
- 노출된 장치 필드에 대시가 표시
- 사이드 패널 및 소프트웨어 페이지에 추가된 정보 텍스트
- 소프트웨어 페이지에 보안 권장 사항, 발견된 취약성 또는 이벤트 타임라인 섹션이 없습니다.

현재 CPE가 없는 제품은 소프트웨어 인벤토리 페이지에는 표시되지 않고 장치 수준 소프트웨어 인벤토리에만 표시됩니다.

## <a name="software-inventory-on-devices"></a>장치의 소프트웨어 인벤토리

포털 Microsoft 365 Defender 패널에서 장치 인벤토리 **[로 이동하세요.](machines-view-overview.md)** 장치 페이지를 열 장치의 이름(예: Computer1)을  선택한 다음 소프트웨어 인벤토리 탭을 선택하여 장치에 있는 알려진 모든 소프트웨어 목록을 확인합니다. 자세한 정보를 사용하여 플라이아웃을 열기 위해 특정 소프트웨어 항목을 선택합니다.

현재 소프트웨어가 디바이스 수준에서 지원되지 않는 경우에도 소프트웨어가 장치 수준에서 표시될 위협 및 취약성 관리. 그러나 제한된 데이터만 사용할 수 있습니다. 소프트웨어가 "취약성" 열에 "사용할 수 없습니다."라고 표시될 것이기 때문에 지원되지 않는지 알 수 있습니다.

CPE가 없는 소프트웨어는 이 장치별 소프트웨어 인벤토리 아래에도 표시될 수 있습니다.

### <a name="software-evidence"></a>소프트웨어 증거

레지스트리, 디스크 또는 둘 다에서 디바이스에서 특정 소프트웨어를 검색한 위치의 증거를 참조하세요. 디바이스 소프트웨어 인벤토리의 모든 장치에서 찾을 수 있습니다.

플라이아웃을 열고 "소프트웨어 증거" 섹션을 찾아보는 소프트웨어 이름을 선택합니다.

:::image type="content" alt-text="소프트웨어 증거 레지스트리 경로를 Windows 10 장치 목록의 소프트웨어 증거 예제입니다." source="images/tvm-software-evidence.png" lightbox="images/tvm-software-evidence.png":::

## <a name="software-pages"></a>소프트웨어 페이지

몇 가지 다른 방법으로 소프트웨어 페이지를 볼 수 있습니다.

- 소프트웨어 인벤토리 > 소프트웨어 이름 선택> 플라이아웃에서 소프트웨어 열기 페이지 선택 
- [보안 권장 >](tvm-security-recommendation.md) 플라이아웃에서 소프트웨어 열기 > **권장** 사항 선택
- [이벤트 타임라인](threat-and-vuln-mgt-event-timeline.md) > 플라이아웃의 "관련 구성 > 요소" 섹션에서 하이퍼링크된 소프트웨어 이름(예: Visual Studio 2017)을 선택합니다.

 전체 페이지는 특정 소프트웨어의 모든 세부 정보와 다음 정보가 함께 표시됩니다.

- 공급업체 정보가 있는 사이드 패널, 조직의 소프트웨어 보전(설치된 장치 수, 패치되지 않은 노출된 장치 포함), 사용 가능 여부 및 악용 여부, 노출 점수에 미치는 영향
- 취약성 및 잘못 구성의 수 및 심각도에 대한 데이터 시각화 또한 노출된 장치 수가 있는 그래프입니다.
- 정보를 표시하는 탭:
  - 식별된 취약점에 대한 해당 보안 권장 사항
  - 검색된 취약성의 명명된 CV
  - 소프트웨어가 설치된 장치(장치 이름, 도메인, OS 등)입니다.
  - 소프트웨어 버전 목록(버전이 설치된 장치 수, 검색된 취약성 수 및 설치된 장치의 이름 포함)

    :::image type="content" alt-text="소프트웨어 세부 Visual Studio, 약점, 노출된 장치 등 2017용 소프트웨어 예제 페이지" source="images/tvm-software-page-example.png" lightbox="images/tvm-software-page-example.png":::

## <a name="report-inaccuracy"></a>부정확성 보고

모호하거나 부정확하거나 불완전한 정보가 표시될 경우 가짓 긍정을 보고합니다. 또한 이미 수정된 보안 권장 사항에 대한 보고를 할 수 있습니다.

1. 소프트웨어 인벤토리 페이지에서 소프트웨어 플라이아웃을 니다.
2. 부정확 **보고를 선택합니다.**
3. 플라이아웃 창의 드롭다운 메뉴에서 부정확성 범주를 선택하고 전자 메일 주소를 입력하고 부정확성에 대한 세부 정보를 입력합니다.
4. **전송** 을 선택합니다. 피드백은 즉시 전문가에게 위협 및 취약성 관리 전송됩니다.

## <a name="related-articles"></a>관련 문서

- [위협 및 취약성 관리 개요](next-gen-threat-and-vuln-mgt.md)
- [보안 권장 사항](tvm-security-recommendation.md)
- [이벤트 타임라인](threat-and-vuln-mgt-event-timeline.md)
- [끝점 장치용 Microsoft Defender 목록 보기 및 구성](machines-view-overview.md)
