---
title: 관리 센터의 microsoft 365 보고서-Microsoft 365 앱 사용 현황
ms.author: sirkkuw
author: sirkkuw
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
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
description: Microsoft 365 관리 센터의 microsoft 365 보고서 대시보드를 사용 하 여 사용 현황 보고서에 대 한 Microsoft 365 앱을 가져오는 방법을 알아봅니다.
ms.openlocfilehash: 3230098336cd17236d754dbfea796c373ea98fe4
ms.sourcegitcommit: dffb9b72acd2e0bd286ff7e79c251e7ec6e8ecae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/17/2020
ms.locfileid: "47948967"
---
# <a name="microsoft-365-reports-in-the-admin-center---microsoft-365-apps-usage"></a>관리 센터의 microsoft 365 보고서-Microsoft 365 앱 사용 현황

Microsoft 365 **보고서** 대시보드에는 조직의 제품 전체에 대 한 활동 개요가 표시 됩니다. 보고서 대시보드를 통해 개별 제품 수준 보고서의 하위 수준을 표시하여 각 제품 내의 활동에 대한 더 세부화된 정보를 확인할 수 있습니다. [보고서 개요 항목](activity-reports.md)을 확인하세요.

 예를 들어 앱 전체의 활동을 확인 하 여 Microsoft 365 Apps 앱을 사용 하도록 허가 된 각 사용자의 활동을 이해 하 고이를 플랫폼 간에 활용할 수 있습니다.


 > [!NOTE]
 > 보고서를 보려면 Microsoft 365 또는 Exchange, SharePoint 또는 비즈니스용 Skype 관리자의 전역 관리자, 전역 독자 또는 보고서 독자 여야 합니다.

## <a name="how-to-get-to-the-microsoft-365-apps-usage-report"></a>Microsoft 365 Apps 사용 보고서에 액세스 하는 방법

1. 관리 센터에서 **보고서** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">사용 현황</a> 페이지를 참조하세요.

 2. **보고서 선택** 드롭다운에서 **Office 365**   \>  **Microsoft 365 앱 사용** 을 선택 합니다.

## <a name="interpret-the-microsoft-365-apps-usage-report"></a>Microsoft 365 Apps 사용 보고서 해석

**사용자 및** **플랫폼** 차트를 확인 하 여 사용자의 Microsoft 365 앱 활동을 볼 수 있습니다.

![Microsoft 365 Apps 사용 보고서](../../media/proplususagenumbers.png)

|항목|설명|
 |:-----|:-----|
 |1. <br/> |**Microsoft 365 Apps 사용 현황** 보고서는 지난 7 일, 30 일, 90 일 또는 180 일 동안의 추세를 볼 수 있습니다. 그러나 보고서에서 특정 날짜를 선택 하는 경우 테이블 (7)은 현재 날짜 로부터 최대 28 일 동안의 데이터를 표시 합니다 (보고서가 생성 된 날짜 아님). <br/> |
 |2. <br/> |각 보고서의 데이터는 대개 지난 7 일간에 포함 됩니다. <br/> |
 |3. <br/> |**사용자** 보기에는 각 앱 (Outlook, Word, Excel, PowerPoint, OneNote 및 팀)에 대 한 활성 사용자 수의 추세가 표시 됩니다. "활성 사용자"는 이러한 앱 내에서 임의의 의도적인 작업을 수행 하는 사용자입니다. <br/> |
 |4. <br/> |**플랫폼** 보기에는 각 플랫폼에 대 한 모든 앱 (Windows, Mac, 웹 및 모바일)에 대 한 활성 사용자의 추세가 표시 됩니다. <br/> |
 |5.<br/>|**사용자** 차트에서 Y 축은 각 앱에 대 한 고유한 활성 사용자 수입니다.  **플랫폼**   차트에서 Y 축은 각 플랫폼에 대 한 고유 사용자 수입니다. 두 차트의 X 축은 지정 된 플랫폼에서 앱이 사용 된 날짜입니다.<br/>|
 6.<br/>|범례에서 항목을 선택 하 여 차트에 표시 되는 계열을 필터링 할 수 있습니다. 예를 들어 **사용자** 차트에서 Outlook, Word, Excel, PowerPoint, OneDrive 또는 팀을 선택 하 여 각 항목에 관련 된 정보만 표시 합니다. 이 선택 항목을 변경 해도 아래 눈금 표에 있는 정보는 변경 되지 않습니다.|
 |7.<br/>|이 표에서는 사용자 수준별 데이터 분석 결과를 보여 줍니다. 표에서 열을 추가하거나 제거할 수 있습니다. <br/><br/>**Username** 은 Microsoft 앱에서 활동을 수행한 사용자의 전자 메일 주소입니다.<br><br/>**최종 정품 인증 날짜 (UTC)** 는 사용자가 Microsoft 365 앱 구독을 정품 인증 한 최근 날짜입니다.<br/><br/>**마지막 활동 날짜 (UTC)** 는 사용자가 의도적인 활동을 수행한 최근 날짜입니다. 특정 날짜에 발생한 활동을 보려면 차트에서 직접 날짜를 선택합니다.<br/><br/>다음 열은 선택한 기간 동안 사용자가 해당 앱에서 활성 상태 였는 지를 식별 하는 각 앱에 해당 합니다.<br> <br>**Outlook** <br>**Word** <br>**Excel**<br>**PowerPoint** <br>**OneNote**<br><br> 다음 열은 선택 된 기간 동안 사용자가 앱 (Microsoft 365 앱 내)에 대해 해당 플랫폼에서 활성 상태 인지 여부를 식별 하는 각 플랫폼에 해당 합니다.<br><br>**Outlook (Windows)**<br>**Outlook (Mac)**<br>**Outlook (웹)** <br>**Outlook (모바일)**<br> **Word (Windows)**<br> **Word (Mac)**<br> **Word (웹)**<br> **Word (모바일)**<br> **Excel (Windows)**<br> **Excel (Mac)**<br> **Excel (웹)**<br> **Excel (모바일)**<br> **PowerPoint (Windows)**<br> **PowerPoint (Mac)**<br>**PowerPoint (웹)**<br> **PowerPoint (모바일)**<br> **OneNote (Windows)**<br> **OneNote (Mac)**<br> **OneNote (웹)**<br>**OneNote (모바일)**<br> **팀 (Windows)**<br> **팀 (Mac)**<br> **팀 (웹)**<br>**팀 (모바일)** |
 |8.<br/>|**열 관리** 아이콘을 선택 하 여 보고서에서 열을 추가 하거나 제거 합니다.|
 |9.<br/>|**내보내기** 링크를 선택 하 여 보고서 데이터를 Excel .csv 파일로 내보낼 수도 있습니다. 그러면 모든 사용자의 데이터를 내보내고 추가 분석을 위해 단순 집계, 정렬 및 필터링을 수행할 수 있습니다. 사용자가 100 명 미만인 경우 보고서 자체의 테이블 내에서 정렬 및 필터링 할 수 있습니다. 사용자가 100 개를 초과 하는 경우 필터링 및 정렬 하려면 데이터를 내보내야 합니다.|
