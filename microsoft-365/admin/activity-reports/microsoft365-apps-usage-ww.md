---
title: Microsoft 365 관리 센터의 보고서 - Microsoft 365 앱 사용 현황
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
ms.localizationpriority: medium
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_NonTOC
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
- GEA150
description: 보고서의 Microsoft 365 앱 보고서 대시보드를 사용하여 Microsoft 365 보고서를 Microsoft 365 관리 센터.
ms.openlocfilehash: 1f714281196ff27404d593c4c65ecec893bbc209
ms.sourcegitcommit: bf3965b46487f6f8cf900dd9a3af8b213a405989
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/02/2021
ms.locfileid: "60648889"
---
# <a name="microsoft-365-reports-in-the-admin-center---microsoft-365-apps-usage"></a>Microsoft 365 관리 센터의 보고서 - Microsoft 365 앱 사용 현황

Microsoft 365 보고서 대시보드에는 조직의 제품 전체에 대한 활동 개요가 표시됩니다. 보고서 대시보드를 통해 개별 제품 수준 보고서의 하위 수준을 표시하여 각 제품 내의 활동에 대한 더 세부화된 정보를 확인할 수 있습니다. [보고서 개요 항목](activity-reports.md)을 확인하세요.

 예를 들어 앱 전반의 활동과 플랫폼에서 앱 사용 방법을 보고 Microsoft 365 앱 앱을 사용하기 위해 라이선스가 부여된 각 사용자의 활동을 이해할 수 있습니다.

## <a name="how-to-get-to-the-microsoft-365-apps-usage-report"></a>사용 현황 보고서에 Microsoft 365 앱 방법

1. 관리 센터에서 **보고서** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">사용 현황</a> 페이지를 참조하세요. 
2. 대시보드 홈페이지에서 활성 사용자 -  카드의 더 보기 단추를 Microsoft 365 앱 클릭합니다.

## <a name="interpret-the-microsoft-365-apps-usage-report"></a>사용 Microsoft 365 앱 해석

사용자 및 플랫폼 차트를 확인하여 사용자의 Microsoft 365 앱 활동을 볼  **수** 있습니다.

> [!div class="mx-imgBorder"]
> ![Microsoft 365 앱 보고서입니다.](../../media/0bcf67e6-a6e4-4109-a215-369f9f20ad84.png)

|항목|설명|
 |:-----|:-----|
 |1. <br/> |사용 **Microsoft 365 앱** 지난 7일, 30일, 90일 또는 180일간의 추세를 볼 수 있습니다. 그러나 보고서에서 특정 날짜를 선택하면 보고서가 생성된 날짜가 아니라 현재 날짜로부터 최대 28일간의 데이터가 표에 표시됩니다. <br/> |
 |2. <br/> |일반적으로 각 보고서의 데이터는 최대 지난 2일까지 처리됩니다. 6일마다 데이터 품질을 보장하기 위해 부 업데이트로 보고서를 새로 고칠 것입니다. <br/> |
 |3. <br/> |사용자 **보기에는** 각 앱의 활성 사용자 수(Outlook, Word, Excel, PowerPoint, OneNote 및 앱의 Teams. "활성 사용자"는 이러한 앱 내에서 의도적인 작업을 수행하는 사용자입니다. <br/> |
 |4. <br/> |플랫폼 **보기는** 각 플랫폼(앱, Mac, 웹 및 모바일)에 대한 Windows 활성 사용자의 추세를 보여줍니다. <br/> |
 |5.<br/>|사용자 **차트에서** Y축은 각 앱의 고유 활성 사용자 수입니다. 플랫폼 **차트에서** Y축은 각 플랫폼의   고유 사용자 수입니다. 두 차트의 X축은 앱이 주어진 플랫폼에서 사용된 날짜입니다.<br/>|
 6.<br/>|범례에서 항목을 선택하여 차트에 있는 계열을 필터링할 수 있습니다. 예를 들어 사용자  차트에서 Outlook, Word, Excel, PowerPoint, OneDrive 또는 Teams 차트를 선택하여 각각 관련된 정보만 볼 수 있습니다. 이 선택을 변경해도 아래의 눈금 표에 있는 정보가 변경되지는 않습니다.|
 |7.<br/>|이 표에서는 사용자 수준별 데이터 분석 결과를 보여 줍니다. 표에서 열을 추가하거나 제거할 수 있습니다.  <br/><br/>**사용자** 이름은 사용자 이름에 대해 활동을 수행한 사용자의 전자 메일 Microsoft Apps.<br><br/>**마지막 정품 인증 날짜(UTC)는** 사용자가 컴퓨터에서 Microsoft 365 앱 구독을 활성화하거나 공유 컴퓨터에서 로그를 활성화하고 계정을 사용하여 앱을 시작하는 마지막 날짜입니다. <br/><br/>**마지막 활동 날짜(UTC)는** 사용자가 의도한 활동을 마지막으로 수행한 날짜입니다. 특정 날짜에 발생한 활동을 보려면 차트에서 직접 날짜를 선택합니다.<br/><br/>다른 열은 선택한 기간에 사용자가 해당 앱에 대해 해당 플랫폼에서 활성 상태(Microsoft 365 앱)를 식별합니다. |
 |8.<br/>|열 **선택 아이콘을** 선택하여 보고서에서 열을 추가하거나 제거합니다.|
 |9.<br/>|내보내기 링크를 선택하여 보고서 데이터를 Excel .csv 내보낼 **수** 있습니다. 이렇게 하면 모든 사용자에 대한 데이터를 내보내고 추가 분석을 위해 간단한 집계, 정렬 및 필터링을 할 수 있습니다. 사용자가 100명 미만인 경우 보고서 자체의 표 내에서 정렬 및 필터링할 수 있습니다. 사용자가 100명 이상인 경우 필터링 및 정렬하려면 데이터를 내보내야 합니다.|
