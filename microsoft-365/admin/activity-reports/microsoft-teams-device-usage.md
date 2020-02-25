---
title: 관리 센터의 Office 365 보고서-Microsoft 팀 장치 사용 현황
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_NonTOC
search.appverid:
- BCS160
- MST160
- MET150
- MOE150
ms.assetid: 917b3e1d-203e-4439-8539-634e80196687
description: Office 365 보고서에서 Microsoft 팀 앱 사용 보고서를 가져와 조직에서 사용 되는 Microsoft 팀 앱에 대 한 정보를 습득 합니다.
ms.openlocfilehash: 1b337c7e6d7668c708bdd93185e8d0b034a29981
ms.sourcegitcommit: ca2b58ef8f5be24f09e73620b74a1ffcf2d4c290
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/24/2020
ms.locfileid: "42245940"
---
# <a name="office-365-reports-in-the-admin-center---microsoft-teams-device-usage"></a>관리 센터의 Office 365 보고서-Microsoft 팀 장치 사용 현황

Office 365 **보고서** 대시보드에는 조직의 제품 전체에 대 한 활동 개요가 표시 됩니다. 보고서 대시보드를 통해 개별 제품 수준 보고서의 하위 수준을 표시하여 각 제품 내의 활동에 대한 더 세부화된 정보를 확인할 수 있습니다. [보고서 개요 항목](activity-reports.md)을 확인하세요. Microsoft Teams 앱 사용 보고서에서는 조직에서 사용되는 Microsoft Teams 앱에 대한 정보를 확인할 수 있습니다.
  
> [!NOTE]
> 보고서를 보려면 Microsoft 365 또는 Exchange, SharePoint 또는 비즈니스용 Skype 관리자의 전역 관리자, 전역 독자 또는 보고서 독자 여야 합니다. 
 
## <a name="how-to-get-to-the-microsoft-teams-app-usage-report"></a>Microsoft Teams 앱 사용 보고서에 액세스하는 방법

1. 관리 센터에서 **보고서** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">사용 현황</a> 페이지를 참조하세요.

    
2. **보고서 선택** 드롭다운에서 **Microsoft 팀** \> **장치 사용**을 선택 합니다.
  
## <a name="interpret-the-microsoft-teams-app-usage-report"></a>Microsoft Teams 앱 사용 보고서 해석

**사용자** 및 **배포** 차트를 보고 Microsoft Teams 앱 사용에 대해 파악할 수 있습니다. 
  
![Office 365 reports - Microsoft Teams app usage](../media/de35c4de-76b4-4109-a806-66774665499b.png)
  
|||
|:-----|:-----|
|1.  <br/> |**Microsoft Teams 장치 사용** 보고서에서 지난 7일, 30일, 90일 또는 180일간의 추세를 볼 수 있습니다. 그러나 보고서에서 특정 날짜를 선택 하는 경우 테이블 (7)은 현재 날짜 로부터 최대 28 일 동안의 데이터를 표시 합니다 (보고서가 생성 된 날짜 아님).  <br/> |
|2.  <br/> |각 보고서의 데이터는 대개 최근 24 ~ 48 시간까지 포함 됩니다.  <br/> |
|3.  <br/> |**사용자** 보기에는 앱을 통한 일별 고유 사용자 수가 표시됩니다.  <br/> |
|4.  <br/> |**배포** 보기에는 선택한 기간 동안 앱별 고유 사용자 수가 표시됩니다.  <br/> |
|5.  <br/> | **사용자** 차트에서 Y축은 앱별 사용자 수입니다.  <br/>  **배포** 차트에서 Y축은 지정된 앱을 사용하는 사용자 수입니다.  <br/>  차트에서 X축은 특정 보고서에 대해 선택한 날짜 범위입니다.  <br/> |
|6.  <br/> |범례에서 항목을 선택 하 여 차트에 표시 되는 계열을 필터링 할 수 있습니다. 예를 들어 **사용자** 차트에서 **windows**, **Mac**, **통화**, **웹**, **Android 휴대폰**또는 **windows phone** 을 선택 하 여 각 항목에 관련 된 정보만 표시 합니다. 이 선택 항목을 변경해도 눈금 표에 있는 정보가 변경되지는 않습니다.  <br/> ![앱 유형을 선택 하 여 Microsoft 팀 앱 사용 현황 차트를 필터링 할 수 있습니다.](../media/64ee1cb1-ca80-4964-8234-7fc671135c3d.png)|
|7.  <br/> | 표시되는 그룹 목록은 가장 긴 보고 기간(180일)에 존재한(삭제되지 않은) 모든 그룹 집합으로 결정됩니다. 활동 수는 날짜 선택에 따라 달라집니다.  <br/> 참고: 열을 추가할 때까지 아래 목록의 항목 중 일부가 표시 되지 않을 수 있습니다.<br/> **사용자 이름**은 사용자의 전자 메일 주소입니다. 실제 전자 메일 주소를 표시하거나 이 필드를 익명으로 만들 수 있습니다.  <br/> **마지막 활동 날짜(UTC)** 는 사용자가 앱에서 Microsoft Teams 활동에 마지막으로 참여한 날짜를 나타냅니다.  <br/> **삭제됨** 은 팀이 삭제되었는지를 나타냅니다. 팀이 삭제되었지만, 보고 기간에 활동이 있는 경우 팀은 표에 삭제됨이 true로 설정된 상태로 표시됩니다.  <br/> **삭제된 날짜**는 팀이 삭제된 날짜입니다.  <br/> **Windows**는 사용자가 지정된 기간에 Windows 앱에서 활성 상태였던 경우 선택됩니다.  <br/> **Mac**은 사용자가 지정된 기간에 Mac 앱에서 활성 상태였던 경우 선택됩니다.  <br/> **웹**은 사용자가 지정된 기간에 웹앱에서 활성 상태였던 경우 선택됩니다.  <br/> **iOS**는 사용자가 지정된 기간에 iOS 앱에서 활성 상태였던 경우 선택됩니다.  <br/> **Android 휴대폰**은 사용자가 지정된 기간에 Android 휴대폰 앱에서 활성 상태였던 경우 선택됩니다.  <br/> **Windows Phone**은 사용자가 지정된 기간에 Windows Phone 앱에서 활성 상태였던 경우 선택됩니다.  <br/>  조직의 정책으로 인해 사용자 정보를 식별할 수 있는 보고서를 볼 수 없는 경우 이러한 모든 보고서의 개인 정보 설정을 변경할 수 있습니다. [Microsoft 365 관리 센터의 활동 보고서](activity-reports.md)에서 **사용자 수준의 세부 정보를 숨기는 방법** 섹션을 확인 하세요.  <br/> |
|8.  <br/> |**열** 을 선택 하 여 보고서에서 열을 추가 하거나 제거 합니다.  <br/> ![Teams uapp usage report - choose columns](../media/333f3077-696d-4829-b0a7-1046b3822222.png)|
|9.  <br/> |**내보내기** 링크를 선택 하 여 Excel .csv 파일에 보고서 데이터를 내보낼 수도 있습니다. 그러면 모든 사용자의 데이터를 내보내고 향후 분석을 위해 간단하게 정렬 및 필터링을 수행할 수 있습니다. 사용자가 2,000명 미만인 경우 보고서 자체의 표에서 정렬 및 필터링할 수 있습니다. 사용자가 2,000명 이상인 경우 필터링 및 정렬하려면 데이터를 내보내야 합니다.  <br/> |
|||
   
  

