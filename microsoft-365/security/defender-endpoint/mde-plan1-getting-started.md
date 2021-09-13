---
title: 끝점 계획 1용 Microsoft Defender 시작(미리 보기)
description: 끝점 계획 1용 Defender 사용을 시작합니다. 보안 센터를 사용하여 경고 및 장치를 관리하고 보고서를 보는 방법을 학습합니다.
search.appverid: MET150
author: denisebmsft
ms.author: deniseb
manager: dansimp
audience: ITPro
ms.topic: overview
ms.date: 08/30/2021
ms.prod: m365-security
ms.technology: mde
localization_priority: Normal
ms.reviewer: inbadian
f1.keywords: NOCSH
ms.openlocfilehash: 3af483db6b2cc9801a56d96147a0a4aed90e33ce
ms.sourcegitcommit: d08fe0282be75483608e96df4e6986d346e97180
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/12/2021
ms.locfileid: "59213665"
---
# <a name="get-started-with-microsoft-defender-for-endpoint-plan-1-preview"></a>끝점 계획 1용 Microsoft Defender 시작(미리 보기)

> [!TIP]
> 아직 Microsoft 365 E3 없는 Microsoft 365 E5 미리 보기 프로그램에 [https://aka.ms/mdep1trial](https://aka.ms/mdep1trial) 등록하세요!

Microsoft 365 Defender 포털()을 사용하면 감지된 위협에 대한 정보를 보고, 경고 및 인시던트를 관리하고, 감지된 위협에 대해 필요한 조치를 취하고, 장치를 관리할 [https://security.microsoft.com](https://security.microsoft.com) 수 있습니다. Microsoft 365 Defender 포털에서는 Endpoint Plan 1(미리 보기)에 대해 얻게 된 위협 방지 기능과 상호 작용을 시작할 수 있습니다. 다음 섹션에서는 시작하는 방법을 설명합니다.

- [Microsoft 365 Defender 포털](#the-microsoft-365-defender-portal)
- [경고에 대한 인시던트 & 관리](#view-and-manage-incidents--alerts)
- [장치 관리](#manage-devices)
- [보고서 보기](#view-reports)

## <a name="the-microsoft-365-defender-portal"></a>Microsoft 365 Defender 포털

Microsoft 365 Defender 포털()에서는 알림을 보고, 장치를 관리하고, 보고서를 [https://security.microsoft.com](https://security.microsoft.com) 볼 수 있습니다. Microsoft 365 Defender 포털에 로그인하면 다음 이미지와 같이 홈 페이지로 시작할 수 있습니다.

:::image type="content" source="../../media/mde-p1/m365-defender-portal.png" alt-text="Microsoft 365 Defender 포털":::

홈페이지는 보안 팀에 감지된 경고, 장치 상태 및 위협에 대한 스냅숏 집계 보기를 제공합니다. 보안 운영 팀이 찾고 있는 정보를 쉽고 빠르게 찾을 수 있도록 보안 센터가 설정됩니다.

> [!NOTE]
> 이 문서에 표시된 예제는 사이트 포털에 표시되는 Microsoft 365 Defender 있습니다. 포털에 표시하는 내용은 라이선스 및 사용 권한에 따라 다를 수 있습니다. 또한 보안 팀은 카드를 추가, 제거 및 다시 설정하여 조직의 포털을 사용자 지정할 수 있습니다.

### <a name="cards-highlight-key-information-and-include-recommendations"></a>카드 주요 정보 강조 표시 및 추천 포함

홈 페이지에는 다음 이미지에 표시된 활성 인시던트 카드와 같은 카드가 포함되어 있습니다.

:::image type="content" source="../../media/mde-p1/active-incidents-card.png" alt-text="활성 인시던트 카드":::

카드는 더 자세한 정보를 보기 위해 선택할 수 있는 링크 또는 단추와 함께 정보를 한눈에 제공합니다. 예제 활성 인시던트 카드를 참조하여 **모든** 인시던트 보기를 선택하여 인시던트 목록으로 이동할 수 있습니다.

:::image type="content" source="../../media/mde-p1/incidents.png" alt-text="인시던트 목록":::

### <a name="navigation-bar-makes-it-easy-to-find-alerts-the-action-center-and-more"></a>탐색 모음을 사용하면 경고, 알림 센터 등 쉽게 찾을 수 있습니다.

화면 왼쪽의 탐색 모음을 사용하면 인시던트, 경고, 알림 센터, 보고서 및 설정 간에 쉽게 이동할 수 있습니다. 다음 표에서는 탐색 모음에 대해 설명하고 있습니다.

| 탐색 모음 항목 | 설명 |
|:---|:---|
| **홈** | 웹 사이트 포털의 홈 [Microsoft 365 Defender 이동합니다.](../defender/microsoft-365-security-center-mde.md) |
| **인시던트 & 경고** | 인시던트 및 **경고를 표시하기** 위해 **확장됩니다.** |
| **인시던트 & 경고**  >  **인시던트** | 인시던트 **목록으로** 이동합니다. 경고가 트리거되고 위협이 감지되면 인시던트가 생성됩니다. 기본적으로 인시던트 목록에는 지난 30일간의 데이터가 표시되고 가장 최근 인시던트가 먼저 나열됩니다.  <br/><br/> 자세한 내용은 인시던트 [를 참조합니다.](view-incidents-queue.md) |
| **인시던트 & 경고**  >  **경고** | 경고 **목록(경고** 큐라고도 **지칭)으로 이동합니다.** 의심스러우거나 악의적인 파일, 프로세스 또는 동작이 감지되면 경고가 트리거됩니다. 기본적으로 경고 **목록에는** 지난 30일간의 데이터가 표시되고 가장 최근 경고가 먼저 나열됩니다. <br/><br/> 자세한 내용은 [경고를 참조합니다.](alerts-queue.md) |
| **알림 센터** | 재구성 및 수동 응답 작업을 추적하는 관리 센터로 이동합니다. 동작 센터는 다음 작업을 추적합니다. <br/>- Microsoft Defender 바이러스 백신 파일이 발생하는 경우 해당 파일을 차단/제거합니다. <br/>- 보안 팀이 장치를 격리합니다.<br/>- Endpoint용 Defender가 파일을 검색하고 검사합니다. <br/><br/> 자세한 내용은 Action [Center를 참조합니다.](auto-investigation-action-center.md) |
| **보안 점수** | 개선 작업 및 메트릭 목록과 함께 조직의 보안 자세에 대한 표현을 표시합니다. <br/><br/> 자세한 내용은 [Microsoft 보안 점수를 참조합니다.](../defender/microsoft-secure-score.md) |
| **Learning 허브** | 보안 기능에 대해 자세히 알아보기 위해 액세스할 수 있는 학습 경로 Microsoft 365 탐색합니다.  |
| **끝점**  >  **검색** | 장치 이름으로 특정 장치를 검색할 수 있는 페이지로 이동합니다. 결과 목록에서 위험 수준 및 상태와 같은 세부 정보를 한눈에 볼 수 있습니다. |
|  **끝점**  >  **장치 인벤토리** | 끝점용 Defender에 온보딩된 장치 목록으로 이동합니다. 노출 및 위험 수준과 같은 장치에 대한 정보를 제공합니다. <br/><br/> 자세한 내용은 장치 [인벤토리 를 참조하세요.](machines-view-overview.md) |
|  **끝점**  >  **구성 & 기준** | 보안 기준 및 구성 **관리를** 표시하기 위해 **확장됩니다.** |
|  **끝점**  >  **구성 & 기준**  >  **보안 기준** | 보안 기준은 권장 보안 설정을 효율적이고 효과적으로 적용하는 데 도움이 될 수 있는 미리 구성된 정책 및 설정 그룹입니다. 기준에는 업계 모범 사례를 기반으로 하는 설정이 포함됩니다. 기본 설정을 유지하거나 조직의 요구에 맞게 기준을 사용자 지정할 수 있습니다. <br/><br/> 자세한 내용은 [Use security baselines to configure Windows 10 devices in Intune을 참조합니다.](/mem/intune/protect/security-baselines) |
|  **끝점**  >  **구성 & 기준**  >  **구성 관리** | 장치 구성 관리 페이지로 **이동하여** 온보드 장치에 대한 정보를 보고 더 많은 장치를 온보드하는 단계를 수행합니다. |
| **보고서** | 위협 방지 보고서, 장치 [](threat-protection-reports.md)상태 및 [](machine-reports.md)준수 보고서 및 웹 보호 보고서와 같은 [보고서로 이동합니다.](web-protection-overview.md) |
| **상태** | 서비스 상태 및 메시지 **센터에** 대한 **링크를 포함합니다.**  |
| **상태**  >  **서비스 상태** | 에서 서비스 상태 페이지로 Microsoft 365 관리 센터. 이 페이지에서는 조직의 구독에서 사용할 수 있는 모든 서비스에서 상태를 볼 수 있습니다.   |
| **상태**  >  **메시지 센터** | 메시지 센터의 메시지 센터로 Microsoft 365 관리 센터. 메시지 센터에서는 계획된 변경 내용에 대한 정보를 제공합니다. 각 메시지는 출시 예정 내용, 사용자에게 미칠 수 있는 영향 및 변경 내용을 관리하는 방법에 대해 설명합니다. |  
| **역할에 & 사용 권한** | 사이트 포털 사용 권한을 부여할 Microsoft 365 Defender 있습니다. 사용 권한은 Azure AD(Azure AD)의 역할을 Azure Active Directory 부여됩니다. 역할을 선택하면 플라이아웃 창이 나타납니다. 플라이아웃에는 역할 그룹의 구성원을 추가하거나 제거할 수 있는 Azure AD에 대한 링크가 포함되어 있습니다. <br/><br/> 자세한 내용은 역할 기반 액세스 제어를 사용하여 포털 액세스 [관리를 참조합니다.](rbac.md)  |
| **설정** | 보안 센터로 나열된 Microsoft 365 Defender 포털에 대한 일반 설정 및 끝점용 Defender(끝점으로 **나열)로 이동합니다.** <br/><br/> 자세한 내용은 [를](../defender/overview-security-center.md)설정. |
| **추가 리소스** | 추가 포털 및 센터 목록(예: Azure Active Directory 및 Microsoft 365 규정 준수 센터. <br/><br/> 자세한 내용은 Microsoft 보안 포털 [및 관리 센터를 참조하세요.](../defender/portals.md) |

> [!TIP]
> 자세한 내용은 Microsoft 365 Defender [개요를 참조하세요.](../defender/microsoft-365-security-center-mde.md)

## <a name="view-and-manage-incidents--alerts"></a>경고에 대한 인시던트 & 관리

Microsoft 365 Defender 포털에 로그인할 때 인시던트 및 경고를 보고 관리해야 합니다. 인시던트 **목록으로** 시작하세요. 다음 이미지는 심각도가 높은 인시던트와 중간 심각도의 인시던트 목록을 보여줍니다. 

:::image type="content" source="../../media/mde-p1/incidents.png" alt-text="인시던트 목록":::
 
인시던트에 대한 세부 정보를 확인하려면 인시던트 선택 세부 정보에는 트리거된 경고, 영향을 받은 장치 및 사용자 수 및 기타 세부 정보가 포함됩니다. 다음 이미지는 인시던트 세부 정보의 예를 보여줍니다.

:::image type="content" source="../../media/mde-p1/single-incident.png" alt-text="사건 세부 정보":::
 
경고, 장치 및 사용자  탭을 사용하여 트리거된 경고, 영향을 받은 장치 및 영향을 받은 사용자 계정과 같은 추가 정보를 볼 수 있습니다. 그런 다음 디바이스를 고리로 설정하고 파일을 중지 및 중지하는 등의 수동 응답 작업을 수행할 수 있습니다. 

> [!TIP]
> 인시던트 보기 사용에 대한 **자세한** 내용은 인시던트 [관리를 참조합니다.](manage-incidents.md)

## <a name="manage-devices"></a>장치 관리

조직의 장치를 보고 관리하려면 탐색 모음의 **끝점에서** 장치 인벤토리 **를 선택합니다.** 다음 이미지에 표시된 장치 목록이 표시됩니다.

:::image type="content" source="../../media/mde-p1/device-inventory.png" alt-text="장치 인벤토리"::: 

이 목록에는 경고가 생성된 장치가 포함됩니다. 기본적으로 표시된 데이터는 지난 30일 동안의 데이터로, 가장 최근 항목이 먼저 나열됩니다. 장치에 대한 자세한 정보를 볼 장치를 선택합니다. 다음 이미지와 같이 플라이아웃 창이 열립니다.

:::image type="content" source="../../media/mde-p1/device-inventory-selecteddevice.png" alt-text="선택한 장치 세부 정보":::

플라이아웃 창에는 장치에 대한 활성 경고와 같은 세부 정보가 표시 며 장치 고리와 같은 작업을 수행하기 위한 링크가 포함되어 있습니다. 

장치에 활성 경고가 있는 경우 플라이아웃 창에서 볼 수 있습니다. 개별 경고를 선택하여 자세한 내용을 볼 수 있습니다. 또는 장치 격리와 같은 작업을 수행하여 다른 장치를 감염시킬 위험을 최소화하면서 장치를 더 조사할 수 있습니다. 

> [!TIP]
> 자세한 내용은 [Endpoint 장치용 Defender](investigate-machines.md)목록에서 장치 조사를 참조하세요.

## <a name="view-reports"></a>보고서 보기

Endpoint 요금제 1용 Defender에서 여러 보고서를 Microsoft 365 Defender 있습니다. 보고서에 액세스하기 위해 다음 단계를 수행합니다.

1. Microsoft 365 Defender 포털()로 [https://security.microsoft.com](https://security.microsoft.com) 이동하여 로그인합니다. 

2. 탐색 모음에서 보고서를 **선택 합니다.** 

3. 목록에서 보고서를 선택합니다. 다음과 같은 세 가지 보고서가 있습니다.

   - 위협 방지 보고서
   - 장치 상태 보고서
   - 웹 보호 보고서

> [!TIP]
> 자세한 내용은 위협 방지 [보고서를 참조하세요.](threat-protection-reports.md) 

### <a name="threat-protection-report"></a>위협 방지 보고서

위협 방지 보고서에 액세스하기 위해 Microsoft 365 Defender 포털에서 **보고서를** 선택한 다음 위협 방지 **를 선택 합니다.** 위협 방지 보고서에는 경고 추세, 상태, 범주 등이 표시됩니다. 보기는 다음 이미지와 같이  경고 추세와 경고 상태의 두 열로 정렬됩니다.
 
:::image type="content" source="../../media/mde-p1/threat-protection-report.png" alt-text="위협 방지 보고서":::

아래로 스크롤하여 각 목록의 모든 보기를 봐야 합니다. 

- 기본적으로 경고 추세 열의 보기에는 지난 30일간의 데이터가 표시되지만 보기를 설정하여 지난 3개월, 지난 6개월 또는 사용자 지정 시간 범위(최대 180일)에 대한 데이터를 표시할 수 있습니다.  
- 경고 상태 **열의** 보기는 이전 업무일의 스냅숏입니다. 

> [!TIP]
> 자세한 내용은 [Endpoint용 Defender의 위협 방지 보고서를 참조합니다.](threat-protection-reports.md)

### <a name="device-health-report"></a>장치 상태 보고서

장치 상태 보고서에 액세스하려면 Microsoft 365 Defender 포털에서 **보고서** 를 선택한 다음 장치 상태 **를 선택하세요.** 장치 상태 보고서에는 조직의 장치 전반에 걸쳐 상태 및 바이러스 백신이 표시됩니다. 위협 [방지](#threat-protection-report)보고서와 마찬가지로 보기는 다음 이미지와  같이 장치 추세와 장치 요약의 두 열로 정렬됩니다. 
 
:::image type="content" source="../../media/mde-p1/device-health-report.png" alt-text="장치 상태 보고서":::

아래로 스크롤하여 각 목록의 모든 보기를 봐야 합니다. 기본적으로 장치 추세 열의 보기에는 지난 30일 동안의 데이터가 표시되지만 보기를 변경하여 지난 3개월, 지난 6개월 또는 사용자 지정 시간 범위(최대 180일)에 대한 데이터를 표시할 수 있습니다.  장치 **요약 보기는** 이전 업무일의 스냅숏입니다.

> [!TIP]
> 자세한 내용은 장치 상태 [를 참조하세요.](machine-reports.md)

### <a name="web-protection-report"></a>웹 보호 보고서

장치 상태 보고서에 액세스하려면 Microsoft 365 Defender 포털에서 **보고서** 를 선택한 다음 웹 보호 **를 선택하세요.** 웹 보호 보고서는 다음 이미지와 같이 악의적인 URL과 같은 검색을 표시하고 차단된 URL에 액세스하려고 시도합니다. 
 
:::image type="content" source="../../media/mde-p1/web-protection-report.png" alt-text="웹 보호 보고서":::

아래로 스크롤하여 웹 보호 보고서의 모든 보기를 봐야 합니다. 일부 보기에는 더 많은 세부 정보를 보고, 위협 방지 기능을 구성하고, Endpoint용 Defender에서 예외로 사용할 지표를 관리할 수 있는 링크가 포함되어 있습니다.

> [!TIP]
> 자세한 내용은 웹 [보호를 참조합니다.](web-protection-overview.md)

## <a name="next-steps"></a>다음 단계

- [끝점 계획 1에 대한 Microsoft Defender 관리(미리 보기)](mde-p1-maintenance-operations.md)
- [엔드포인트용 Microsoft Defender](microsoft-defender-endpoint.md)