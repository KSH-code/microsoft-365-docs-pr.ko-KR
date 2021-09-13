---
title: Microsoft 365 Lighthouse 장치 준수 페이지 개요
f1.keywords: NOCSH
ms.author: sharik
author: SKjerland
manager: scotv
audience: Admin
ms.topic: article
ms.prod: microsoft-365-lighthouse
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
ms.custom:
- AdminSurgePortfolio
- M365-Lighthouse
search.appverid: MET150
description: 서비스 공급자를 사용하는 MSP(관리 Microsoft 365 Lighthouse)의 경우 장치 준수 페이지에 대해 자세히 알아보십시오.
ms.openlocfilehash: c87f808a3694c1f256a8a4787591a93444cf792f
ms.sourcegitcommit: d08fe0282be75483608e96df4e6986d346e97180
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/12/2021
ms.locfileid: "59212495"
---
# <a name="microsoft-365-lighthouse-device-compliance-page-overview"></a>Microsoft 365 Lighthouse 장치 준수 페이지 개요

> [!NOTE]
> 이 문서에 설명된 기능은 미리 보기에 있으며, 변경될 수 있으며, 요구 사항을 충족하는 파트너만 사용할 수 [있습니다.](m365-lighthouse-requirements.md) 조직에 등록이 Microsoft 365 Lighthouse 에 [등록을 Microsoft 365 Lighthouse.](m365-lighthouse-sign-up.md)

Microsoft 365 Lighthouse 창에서 디바이스를 선택하여 장치 준수 페이지를 열면 모든 고객 테넌트에  대한 Intune 장치 준수와 관련된 인사이트 및 정보를 볼 수 있습니다. 이 페이지에서는 테넌트 전체의 규정 준수 상태에 대한 개요를 보고, 각 테넌트의 장치 목록을 보고, 준수 정책 및 설정에 대한 상태 보고서를 받을 수 있습니다.

## <a name="overview-tab"></a>개요 탭  
  
개요 탭에서 테넌트 전체에서 장치 준수 상태를 보고, 월별 장치 준수 추세를 보고, 장치에 할당된 준수 정책이 있는지 추적할 수 있습니다. 조건부 액세스 정책에 따라 테넌트 장치 준수 작업 및 요구 사항에 대한 정보를 볼 수 있습니다. 

특정 고객 테넌트에 대한 자세한 장치 준수 정보를 확인하려면 해당 테넌트의 상태 열에서 값을 선택합니다. 그러면 선택한 테넌트에 대한 장치 준수 세부 정보를 볼 수 있도록 장치 탭이 열립니다.

장치 준수 데이터를 Excel(.csv) 파일로 내보내기 를 **선택합니다.**

:::image type="content" source="../media/m365-lighthouse-device-compliance-page-overview/device-overview-tab.png" alt-text="개요 탭의 스크린샷.":::

## <a name="devices-tab"></a>장치 탭

장치 탭의 색상이 지정한 개수 주석 표시줄에는 준수 상태가 규격, 미준수, 유예 기간 및 평가되지 않은 모든 고객 테넌트의 총 장치 수가 표시됩니다. 다양한 준수 상태에 대한 자세한 내용은 Intune 장치 준수 정책 [모니터링을 참조하세요.](/mem/intune/protect/compliance-policy-monitor)

특정 준수 상태의 장치가 있는 테넌트를 확인하려면 개수 주석 표시줄에서 해당 상태를 선택하여 목록을 필터링합니다. 하나 이상의 특정 고객 테넌트에 대한 장치 준수 상태를 확인하려면 **테넌트** 드롭다운 메뉴를 사용하여 목록을 필터링합니다.

목록에서 장치 이름을 선택하여 해당 장치의 현재 규정 준수 상태를 자세히 확인합니다. 디바이스를 동기화하거나 다시 시작하거나 문제 해결 또는 추가 **Microsoft Endpoint Manager** 디바이스 보기를 선택할 수 있습니다.

> [!NOTE]
> 장치를 다시 시작하면 장치 소유자에게 자동으로 통보되지 않습니다. 따라서 장치를 다시 시작하기 전에 장치 소유자에게 알릴 수 있습니다.

장치 탭에는 다음 옵션도 포함되어 있습니다.

- **내보내기:** 장치 준수 데이터를 Excel 콤보로 구분된 값(.csv) 파일로 내보낼 수 있습니다.
- **새로 고침:** 가장 최근의 장치 준수 데이터를 검색하려면 선택합니다.
- **동기화:** 호환되지 않는 상태, 유예 기간 중 또는 평가되지 않은 상태인 디바이스를 목록에서 하나 이상 선택한 다음 이 옵션을 선택하여 해당 장치가 Intune으로 체크 인되고 할당된 정책을 즉시 받게 합니다.
- **다시 시작:** 목록에서 비호준, 유예 기간 중 또는 평가되지 않은 상태인 장치를 하나 이상 선택한 다음 이 옵션을 선택하여 해당 장치를 다시 시작합니다.
- **검색:** 키워드를 입력하여 목록에서 특정 장치를 빠르게 찾습니다.
 
:::image type="content" source="../media/m365-lighthouse-device-compliance-page-overview/devices-device-tab.png" alt-text="장치 탭의 스크린샷.":::

## <a name="policies-tab"></a>정책 탭

정책 탭에서 비교 옵션을 사용하여 테넌트 전체에서 장치 준수 정책을 보고 동일한 플랫폼 유형의 두 개 또는 세 개의 정책을 비교할 **수** 있습니다.

특정 플랫폼의 장치에 대한 정책을 표시하기 위해 **OS 드롭다운** 메뉴를 사용하여 목록을 필터링합니다. 하나 이상의 특정 고객 테넌트에 대한 정책을 표시하기 위해 **테넌트** 드롭다운 메뉴를 사용하여 목록을 필터링합니다.

해당 정책에 대한 자세한 내용을 확인하려면 목록에서 정책 이름을 선택합니다. 작업을 수행하거나 추가 정보를 표시해야 하는 경우 에서 이 정책 **Microsoft Endpoint Manager.**

정책 탭에는 다음 옵션도 포함됩니다.

- **내보내기:** 장치 준수 정책 데이터를 Excel 콤보로 구분된 값(.csv) 파일로 내보낼 수 있습니다.
- **새로 고침:** 가장 최근의 장치 준수 정책 데이터를 검색하려면 선택합니다.
- **검색:** 키워드를 입력하여 목록에서 특정 장치 준수 정책을 빠르게 찾습니다.

:::image type="content" source="../media/m365-lighthouse-device-compliance-page-overview/devices-policies-tab.png" alt-text="정책 탭의 스크린샷.":::

## <a name="settings-tab"></a>설정 탭

설정 탭은 테넌트 장치 전반에 걸쳐 비호준 설정에 대한 집계 보고서를 제공합니다. 

특정 플랫폼의 장치에 대한 비호준 설정을  표시하려면 플랫폼 드롭다운 메뉴를 사용하여 목록을 필터링합니다. 하나 이상의 특정 고객 테넌트에 대한 비호준 설정을 표시하려면 **테넌트** 드롭다운 메뉴를 사용하여 목록을 필터링합니다.

목록에서 호환되지 않는 설정 이름을 선택하여 특정 비호준 설정이 있는 장치가 있는 테넌트 목록을 볼 수 있는 창을 열 수 있습니다. 여기에서 목록에서 테넌트를 선택하여 특정 비호준 설정이 있는 해당 테넌트 내의 장치에 대한 정보를 표시하여 드릴다운할 수 있습니다. 또한 디바이스를 동기화하거나 다시 시작하거나 문제 해결 또는 추가 **작업을** Microsoft Endpoint Manager 디바이스 보기를 선택할 수 있습니다.

설정 탭에는 다음 옵션도 포함됩니다.

- **내보내기:** 호환되지 않는 설정 데이터를 Excel 값(.csv) 파일로 내보낼 수 있습니다.
- **새로 고침:** 가장 최근의 비호준 설정 데이터를 검색하려면 선택합니다.
- **검색:** 키워드를 입력하여 목록에서 특정 비호준 설정을 빠르게 찾습니다.

:::image type="content" source="../media/m365-lighthouse-device-compliance-page-overview/device-settings-tab.png" alt-text="Screenshot of the 설정 tab.":::

## <a name="related-content"></a>관련 콘텐츠

[Windows 365(클라우드 PC) 페이지](m365-lighthouse-win365-page-overview.md) 개요(문서)\
[Microsoft 365 Lighthouse FAQ(문서)](m365-lighthouse-faq.yml)
