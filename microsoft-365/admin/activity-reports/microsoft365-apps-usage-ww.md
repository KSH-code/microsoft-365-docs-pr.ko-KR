---
title: 관리 센터의 Microsoft 365 보고서 - Microsoft 365 앱 사용 현황
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
description: Microsoft 365 관리 센터의 Microsoft 365 보고서 대시보드를 사용하여 사용 현황 보고서를 다운로드하는 방법을 학습합니다.
ms.openlocfilehash: 0c30cee0c1abd76553d3adfebebb8fe38e92c56a
ms.sourcegitcommit: 039205fdaaa2a233ff7e95cd91bace474b84b68c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/09/2020
ms.locfileid: "49611920"
---
# <a name="microsoft-365-reports-in-the-admin-center---microsoft-365-apps-usage"></a>관리 센터의 Microsoft 365 보고서 - Microsoft 365 앱 사용 현황

Microsoft 365 **보고서** 대시보드에는 조직의 제품 전체에 대한 활동 개요가 표시됩니다. 보고서 대시보드를 통해 개별 제품 수준 보고서의 하위 수준을 표시하여 각 제품 내의 활동에 대한 더 세부화된 정보를 확인할 수 있습니다. [보고서 개요 항목](activity-reports.md)을 확인하세요.

 예를 들어 앱 전체의 활동과 플랫폼에서 앱 사용 방법을 보고 Microsoft 365 앱 앱을 사용하기 위해 라이선스가 부여된 각 사용자의 활동을 이해할 수 있습니다.


 > [!NOTE]
 > 보고서를 표시하려면 Microsoft 365의 전역 관리자, 전역 읽기 권한자 또는 보고서 읽기 권한자 또는 Exchange, SharePoint 또는 비즈니스용 Skype 관리자 되어야 합니다.

## <a name="how-to-get-to-the-microsoft-365-apps-usage-report"></a>Microsoft 365 앱 사용 현황 보고서에 액세스하는 방법

1. 관리 센터에서 **보고서** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">사용 현황</a> 페이지를 참조하세요. 
2. 대시보드 홈페이지에서 활성 사용자 -  Microsoft 365 앱 카드의 더 보기 단추를 클릭합니다.

## <a name="interpret-the-microsoft-365-apps-usage-report"></a>Microsoft 365 앱 사용 현황 보고서 해석

사용자 및 플랫폼 차트를 확인하여 사용자의 Microsoft 365  앱 활동을 볼 **수** 있습니다.

![Microsoft 365 앱 사용 현황 보고서](../../media/0bcf67e6-a6e4-4109-a215-369f9f20ad84.png)

|항목|설명|
 |:-----|:-----|
 |1. <br/> |**Microsoft 365** 앱 사용 현황 보고서에서 지난 7일, 30일, 90일 또는 180일간의 추세를 볼 수 있습니다. 그러나 보고서에서 특정 날짜를 선택하면 표(7)에 현재 날짜로부터 최대 28일간의 데이터가 표시됩니다(보고서가 생성된 날짜가 아미지 않습니다). <br/> |
 |2. <br/> |각 보고서의 데이터는 일반적으로 최근 7일까지 처리됩니다. <br/> |
 |3. <br/> |사용자 **보기에는** 각 앱의 활성 사용자 수(Outlook, Word, Excel, PowerPoint, OneNote 및 Teams)의 추세가 표시됩니다. "활성 사용자"는 이러한 앱 내에서 의도적인 작업을 수행하는 사용자입니다. <br/> |
 |4. <br/> |플랫폼 **보기는** 각 플랫폼(Windows, Mac, 웹 및 모바일)의 모든 앱에 대한 활성 사용자의 추세를 보여 주며, <br/> |
 |5.<br/>|사용자 **차트에서** Y축은 각 앱의 고유 활성 사용자 수입니다. 플랫폼 **차트에서** Y축은 각 플랫폼의 고유 사용자   수입니다. 두 차트의 X축은 앱이 주어진 플랫폼에서 사용된 날짜입니다.<br/>|
 6.<br/>|범례에서 항목을 선택하여 차트에 표시하는 계열을 필터링할 수 있습니다. 예를 들어 사용자  차트에서 Outlook, Word, Excel, PowerPoint, OneDrive 또는 Teams를 선택하여 각각에 관련된 정보만 볼 수 있습니다. 이 선택을 변경해도 아래 표의 정보는 변경되지 않습니다.|
 |7.<br/>|이 표에서는 사용자 수준별 데이터 분석 결과를 보여 줍니다. 표에서 열을 추가하거나 제거할 수 있습니다. <br/><br/>**사용자** 이름은 Microsoft Apps에서 활동을 수행한 사용자의 전자 메일 주소입니다.<br><br/>**마지막 활성화 날짜(UTC)는** 사용자가 Microsoft 365 앱 구독을 정품 인증한 마지막 날짜입니다.<br/><br/>**마지막 활동 날짜(UTC)는** 사용자가 의도한 활동을 마지막으로 수행한 날짜입니다. 특정 날짜에 발생한 활동을 보려면 차트에서 직접 날짜를 선택합니다.<br/><br/>다른 열은 선택한 기간에 사용자가 해당 앱(Microsoft 365 앱 내에서)에 대해 해당 플랫폼에서 활성 상태인지 식별합니다. |
 |8.<br/>|열 선택 **아이콘을** 선택하여 보고서에서 열을 추가하거나 제거합니다.|
 |9.<br/>|내보내기 링크를 선택하여 보고서 데이터를 Excel .csv 파일로 내보낼 **수** 있습니다. 이렇게 하면 모든 사용자에 대한 데이터를 내보내고 추가 분석을 위해 간단한 집계, 정렬 및 필터링을 할 수 있습니다. 사용자가 100명 미만인 경우 보고서 자체의 테이블 내에서 정렬 및 필터링할 수 있습니다. 사용자가 100명 이상인 경우 필터링 및 정렬하려면 데이터를 내보내야 합니다.|
