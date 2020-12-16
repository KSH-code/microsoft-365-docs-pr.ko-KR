---
title: 관리 센터의 Microsoft 365 보고서 - SharePoint 사이트 사용 현황
ms.author: pebaum
author: pebaum
manager: pamgreen
audience: Admin
ms.topic: overview
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
- SPO160
- BSA160
ms.assetid: 4ecfb843-e5d5-464d-8bf6-7ed512a9b213
description: 'SharePoint 사이트 사용 현황 보고서를 통해 사용자가 SharePoint 사이트에 저장하는 파일 수, 적극적으로 사용되는 파일 수 및 사용된 총 저장소 수를 알 수 있습니다. '
ms.openlocfilehash: 7da72dccb4a90ed204ffa785040b1968ac70feb3
ms.sourcegitcommit: 849b365bd3eaa9f3c3a9ef9f5973ef81af9156fa
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/16/2020
ms.locfileid: "49688208"
---
# <a name="microsoft-365-reports-in-the-admin-center---sharepoint-site-usage"></a>관리 센터의 Microsoft 365 보고서 - SharePoint 사이트 사용 현황

Microsoft 365 관리자는 **보고서** 대시보드에 조직의 다양한 제품에 대한 활동 개요가 표시됩니다. 각 제품의 고유한 활동에 대한 자세한 정보를 확인할 수 있습니다. 예를 들어 사용자가 SharePoint 사이트에 저장한 총 파일 수, 현재 적극적으로 사용 중인 파일 수 및 모든 SharePoint 사이트에서 사용된 저장소와 관련하여 SharePoint에서 얻는 값을 대략적으로 볼 수 있습니다. 그런 다음 SharePoint 사이트 사용 보고서를 확인하여 추세와 모든 사이트에 대한 수준별 세부 정보를 파악할 수 있습니다. 
  
> [!NOTE]
> Microsoft 365의 전역 관리자, 전역 읽기 권한자 또는 보고서 읽기 권한자 또는 Exchange, SharePoint, Teams 서비스, Teams 커뮤니케이션 또는 비즈니스용 Skype 관리자인 경우 보고서를 볼 수 있어야 합니다.
관리 센터의 Microsoft 365 보고서는 GCC High 및 DoD 테넌트에 지원되지 않습니다.
 
## <a name="how-to-get-to-the-sharepoint-site-usage-report"></a>SharePoint 사이트 사용 보고서에 액세스하는 방법

1. 관리 센터에서 보고서 사용 **현황으로** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">이동하세요.</a>
    
2. SharePoint **파일에서 더 보기를** **클릭합니다.** 

3. **SharePoint 활동 옆의** 아래쪽 화살표를 클릭하여 메뉴를 니다.

4. **SharePoint** \> **사이트 사용 현황을 선택합니다.**
  
## <a name="interpreting-the-sharepoint-site-usage-report"></a>SharePoint 사이트 사용 보고서 해석

![SharePoint Site Usage Report](../../media/4f88fb7d-9aa8-470e-9e23-e31caaf77d78.png)
  
|항목|설명|
|:-----|:-----|
|1.  <br/> |**SharePoint 사이트 사용** 보고서에서 지난 7일, 30일, 90일 또는 180일간의 추세를 볼 수 있습니다. 그러나 보고서에서 특정 날짜를 선택하면 표(7)에 현재 날짜로부터 최대 28일간의 데이터가 표시됩니다(보고서가 생성된 날짜가 아미지 않습니다).  <br/> |
|2.  <br/> |각 보고서의 데이터는 일반적으로 최근 24시간에서 48시간까지 처리됩니다. <br/> |
|3.  <br/> |사이트  차트는 사용자가 보고 기간 내에 파일을 보거나 수정, 업로드, 다운로드, 공유 또는 동기화하거나 페이지를 본 사이트를 포함하여 전체 및 활성 사이트 수를 보여줍니다.  <br/> |
|4.  <br/> |**파일** 차트에는 모든 사이트의 파일 총 개수와 활성 파일 개수가 표시됩니다. 총 파일 개수에는 사용자 파일과 시스템 파일이 모두 해당합니다. 파일은 지정된 기간에 저장, 동기화, 수정 또는 공유된 경우에만 활성 상태로 간주됩니다.  |
|5.  <br/> |**저장소** 차트에는 보고 기간 동안 할당되어 사용된 저장소의 추세가 표시됩니다.  <br/> |
|6.  <br/> |**페이지** 차트에는 모든 사이트에서 본 페이지 수가 표시됩니다.  <br/> |
|7.  <br/> |범례에서 항목을 선택하여 차트를 필터링할 수 있습니다. 예를 들어 파일 **차트에서** 파일 또는 활성 **파일을** **선택합니다.** 사이트 **차트에서** 총 사이트 또는 활성 사이트를 **선택할** **수 있습니다.** 저장소 **차트에서** 할당된  저장소 또는 사용된 **저장소를 선택할 수 있습니다.** 이 선택 항목을 변경해도 눈금 표에 있는 정보가 변경되지는 않습니다.  <br/> |
|8.  <br/> | 이 표에서는 사이트 수준별 활동 분석 결과를 보여줍니다.  <br/> ![사용 현황 보고서의 열 옵션](../../media/sharepointsite-usage.png)           <br/> **사이트 URL** 은 사이트의 전체 URL입니다.  <br/> **삭제됨** 은 사이트의 삭제 상태입니다. 사이트가 삭제됨으로 표시되려면 7일 이상이 소요됩니다.  <br/> **사이트 소유자** 는 사이트 기본 소유자의 사용자 이름입니다.  <br/>**사이트 소유자 계정 이름은** 사이트 소유자의 전자 메일 주소입니다.  <br/> **마지막 활동 날짜(UTC)** 는 사이트에서 마지막으로 파일 활동을 검색하거나 페이지를 본 날짜를 나타냅니다.  <br/> **파일 수** 는 사이트의 파일 수입니다.  <br/> **활성 파일은** 사이트의 활성 파일 수입니다.<br/> 참고: 보고서에 대해 지정된 기간 동안 파일이 제거된 경우 보고서에 표시된 활성 파일 수가 사이트의 현재 파일 수보다 클 수 있습니다.<br/>**사용된 저장소(MB)** 는 사이트에서 현재 사용 중인 저장소의 크기입니다.  <br/> **할당된 저장소(MB)** 는 사이트에 할당된 저장소의 최대 크기입니다.  <br/> **페이지 보기** 는 사이트에서 페이지가 조회된 횟수입니다.  <br/> **열어본 페이지** 는 사이트에서 열어본 고유 페이지 수입니다.  <br/> **루트 웹 서식 파일** 은 사이트를 만드는 데 사용된 서식 파일입니다.  <br/> 참고: 여러 사이트 유형으로 데이터를 필터링하려는 경우 데이터를 내보내고 루트 웹 서식 파일 열을 사용하세요. <br/>조직의 정책으로 인해 사용자 정보를 식별할 수 있는 보고서를 볼 수 없는 경우 이러한 모든 보고서의 개인 정보 설정을 변경할 수 있습니다. Microsoft 365 관리 센터의 활동 보고서에서 사용자 수준 세부 정보를 숨기는 방법 [섹션을 참조하세요.](activity-reports.md)   <br/> |
|9.  <br/> |열 **관리 열을** 선택하여 보고서에서 열을 추가하거나 ![ ](../../media/13d2e536-de88-4db3-80c7-7a3a57298eb4.png) 제거합니다.    <br/> |
|10.  <br/> |내보내기 링크를 선택하여 보고서 데이터를 Excel .csv 파일로 내보낼 **수** ![ ](../../media/4dc548cc-8061-48d5-9240-6793affca43a.png) 있습니다. 그러면 모든 사이트의 데이터를 내보내고 향후 분석을 위해 간단하게 정렬 및 필터링을 수행할 수 있습니다. 사이트가 2,000개 미만인 경우 보고서 자체의 표에서 정렬 및 필터링할 수 있습니다. 사이트가 2,000개 이상인 경우 필터링 및 정렬하려면 데이터를 내보내야 합니다.  <br/> 참고: 데이터를 Excel 파일로 내보내면 콘텐츠 보고서가 생성된 날짜가 열의 **데이터** 파일에 반영됩니다.      <br/>   |
|||
