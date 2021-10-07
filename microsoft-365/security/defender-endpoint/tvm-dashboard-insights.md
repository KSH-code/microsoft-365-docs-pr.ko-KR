---
title: 대시보드 정보 - 위협 및 취약성 관리
description: 이 위협 및 취약성 관리 대시보드는 SecOps 및 보안 관리자가 사이버 보안 위협을 해결하고 조직의 보안 탄력성을 구축하는 데 도움이 될 수 있습니다.
keywords: Endpoint-tvm용 Microsoft Defender, Endpoint-tvm 대시보드용 Microsoft Defender 대시보드, 위협 & 취약성 관리, 위협 및 취약성 관리, 위험 기반 위협 & 취약성 관리, 보안 구성, 장치용 Microsoft 보안 점수, 노출 점수
search.appverid: met150
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 79bae1cdf4ce21ef00f622bfd438238e69f6ff8a
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/06/2021
ms.locfileid: "60193916"
---
# <a name="dashboard-insights---threat-and-vulnerability-management"></a>대시보드 정보 - 위협 및 취약성 관리

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**적용 대상:**

- [엔드포인트용 Microsoft Defender](https://go.microsoft.com/fwlink/?linkid=2154037)
- [위협 및 취약성 관리](next-gen-threat-and-vuln-mgt.md)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Endpoint용 Defender를 경험하고 싶나요? [무료 평가판을 신청하세요.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-portaloverview-abovefoldlink)

위협 및 취약성 관리 끝점용 Defender의 구성 요소로, 다음을 포함하여 보안 관리자와 보안 운영 팀 모두에게 고유한 가치를 제공합니다.

- 엔드포인트 취약점과 관련된 실시간 EDR(엔드포인트 탐지 및 대응) 인사이트
- 인시던트 조사 중에 평가할 수 있는 장치 취약성 컨텍스트
- 기본 제공 수정 프로세스 및 Microsoft Intune Microsoft Endpoint Configuration Manager

포털의 위협 및 취약성 관리 기능을 사용하여 [Microsoft 365 Defender 수](https://security.microsoft.com/) 있습니다.

- 주요 보안 권장 사항, 소프트웨어 취약성, 수정 활동 및 노출된 장치와 함께 노출 점수 및 장치에 대한 Microsoft 보안 점수 보기
- 엔드포인트 EDR 정보를 고려하여 처리합니다.
- 재구성 옵션을 선택하여 재구성 작업을 Triage and track the remediation tasks
- 예외 옵션 선택 및 활성 예외 추적

> [!NOTE]
> 지난 30일 동안 활성화되지 않은 장치는 조직의 노출 점수와 장치에 대한 Microsoft 보안 점수를 위협 및 취약성 관리 영향을 미치지 않습니다.

이 비디오를 시청하여 대시보드의 개요를 위협 및 취약성 관리 있습니다.

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4r1nv]

## <a name="threat-and-vulnerability-management-dashboard"></a>위협 및 취약성 관리 대시보드

:::image type="content" source="../../media/tvmdashboard.png" lightbox="../../media/tvmdashboard.png" alt-text="장치용 위협 및 취약성 관리 대시보드.":::

<br>

****

|영역|설명|
|---|---|
|**선택한 장치 그룹(#/#)**|대시보드 및 위협 및 취약성 관리 그룹으로 표시하려는 데이터 및 카드 데이터를 필터링합니다. 필터에서 선택한 사항은 필터 페이지 전체에 위협 및 취약성 관리 적용됩니다.|
|[**노출 점수**](tvm-exposure-score.md)|위협 및 취약성에 대한 조직의 현재 장치 노출 상태를 확인합니다. 조직의 노출 점수에 영향을 주는 요인으로는 디바이스에서 발견된 약점, 장치가 위반될 가능성, 조직에 대한 장치 값, 장치에서 검색된 관련 경고 등 여러 가지 요인이 있습니다. 목표는 조직의 노출 점수를 낮출 수 있도록 보다 안전하게 하는 것입니다. 점수를 줄이기 위해 보안 권장 사항에 나열된 관련 보안 구성 문제를 수정해야 합니다.|
|[**디바이스용 Microsoft Secure Score**](tvm-microsoft-secure-score-devices.md)|조직의 운영 체제, 응용 프로그램, 네트워크, 계정 및 보안 제어에 대한 보안 자세를 참조합니다. 목표는 관련 보안 구성 문제를 수정하여 디바이스에 대한 점수를 높이는 것입니다. 막대를 선택하면 보안 권장 **페이지로 이동됩니다.**|
|**디바이스 노출 분포**|노출 수준에 따라 노출되는 장치 수를 참조합니다. 도넛형 차트에서 섹션을 선택하여 장치 목록  페이지로 이동하여 영향을 받는 장치 이름, 노출 수준, 위험 수준 및 도메인, 운영 체제 플랫폼, 상태, 마지막으로 확인된 경우 및 태그와 같은 기타 세부 정보를 확인합니다.|
|**주요 보안 권장 사항**|조직의 위험 노출 및 필요한 긴급도에 따라 정렬 및 우선 순위가 지정되는 정렬된 보안 권장 사항을 참조하세요. **목록의** 나머지 보안 권장 사항을 표시하려면 자세한 정보 표시를 선택합니다. 예외가 **있는** 권장 사항 목록에 대해 예외 표시를 선택합니다.|
|**취약한 상위 소프트웨어**|네트워크 장치에 설치된 취약한 소프트웨어의 스택 순위 목록과 조직의 노출 점수에 어떤 영향을 미치는지 실시간으로 조직의 소프트웨어 인벤토리를 확인합니다. 자세한 내용은 항목을 선택하거나 **소프트웨어** 인벤토리 페이지에서 나머지 취약한 소프트웨어 목록을 확인하려면 자세히 **표시를** 선택합니다.|
|**상위 수정 활동**|보안 권장 사항에서 생성된 수정 활동을 추적합니다. 목록의 각 항목을 선택하여 재구성 페이지에서  세부 정보를 보거나  자세히 표시를 선택하여 나머지 재구성 활동 및 활성 예외를 볼 수 있습니다.|
|**노출된 상위 장치**|노출된 장치 이름 및 노출 수준을 확인합니다. 목록에서 장치 이름을 선택하여 경고, 위험, 인시던트, 보안 권장 사항, 설치된 소프트웨어 및 노출된 장치와 관련된 검색된 취약점을 볼 수 있는 장치 페이지로 이동합니다. 노출된 **장치 목록의** 나머지를 표시하려면 더 보기를 선택합니다. 장치 목록에서 태그를 관리하고, 자동화된 조사를 시작하고, 라이브 응답 세션을 시작하고, 조사 패키지를 수집하고, 바이러스 백신 검색을 실행하고, 앱 실행을 제한하고, 장치를 격리할 수 있습니다.|
|

포털 전체에서 사용되는 아이콘에 대한 자세한 내용은 [끝점 아이콘용 Microsoft Defender를 참조하세요.](portal-overview.md#microsoft-defender-for-endpoint-icons)

## <a name="related-topics"></a>관련 항목

- [위협 및 취약성 관리 개요](next-gen-threat-and-vuln-mgt.md)
- [노출 점수](tvm-exposure-score.md)
- [장치용 Microsoft Secure Score](tvm-microsoft-secure-score-devices.md)
- [보안 권장 사항](tvm-security-recommendation.md)
- [소프트웨어 인벤토리](tvm-software-inventory.md)
- [이벤트 타임라인](threat-and-vuln-mgt-event-timeline.md)
