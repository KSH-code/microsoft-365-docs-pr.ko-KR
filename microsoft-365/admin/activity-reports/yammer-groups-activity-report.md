---
title: 관리 센터의 Microsoft 365 보고서 - Yammer 활동 보고서
f1.keywords:
- NOCSH
ms.author: kwekua
author: kwekua
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
ms.assetid: 94dd92ec-ea73-43c6-b51f-2a11fd78aa31
description: 조직에서 Yammer 그룹 활동 보고서를 통해 조직에서 만들어 Yammer 그룹 수와 해당 활동을 알 수 있습니다.
ms.openlocfilehash: 7cd06c76b8a1a38eb7ebe1c45d099f7f554acdb3
ms.sourcegitcommit: 53acc851abf68e2272e75df0856c0e16b0c7e48d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/02/2021
ms.locfileid: "51579437"
---
# <a name="microsoft-365-reports-in-the-admin-center---yammer-groups-activity-report"></a>관리 센터의 Microsoft 365 보고서 - Yammer 활동 보고서

Microsoft 365 **보고서** 대시보드에는 조직의 제품 전체에 대한 활동 개요가 표시됩니다. 보고서 대시보드를 통해 개별 제품 수준 보고서의 하위 수준을 표시하여 각 제품 내의 활동에 대한 더 세부화된 정보를 확인할 수 있습니다. [보고서 개요 항목](activity-reports.md)을 확인하세요. Yammer 그룹 활동 보고서에서는 조직의 Yammer 그룹 활동을 파악하고, 만들어지고 사용되는 Yammer 그룹의 수를 확인할 수 있습니다.
  
> [!NOTE]
> Microsoft 365의 전역 관리자, 전역 읽기 권한자 또는 보고서 읽기 권한자 또는 Exchange, SharePoint, Teams 서비스, Teams Communications 또는 비즈니스용 Skype 관리자인 경우 보고서를 볼 수 있어야 합니다.  

## <a name="how-to-get-to-the-yammer-groups-activity-report"></a>Yammer 그룹 활동 보고서에 액세스하는 방법

1. 관리 센터에서 **보고서** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">사용 현황</a> 페이지를 참조하세요.

    
2. 보고서 **선택 드롭다운** 목록에서  그룹 Yammer \> **선택합니다.**
  
## <a name="interpret-the-yammer-groups-activity-report"></a>Yammer 그룹 활동 보고서 해석

**그룹** 및 **활동** 차트를 확인하여 Yammer 그룹 활동을 볼 수 있습니다.<br/>![Yammer groups activity chart](../../media/4ba4ea03-2f74-4d86-8c63-2b18477c9769.png)
  
|항목|설명|
|:-----|:-----|
|1.  <br/> |**Yammer 그룹 활동** 보고서에서 지난 7일, 30일, 90일 또는 180일간의 추세를 볼 수 있습니다. 그러나 보고서에서 특정 날짜를 선택하면 표(7)에 현재 날짜로부터 최대 28일간의 데이터가 표시됩니다(보고서가 생성된 날짜가 아 아지 않습니다).  <br/> |
|2.  <br/> |각 보고서의 데이터는 일반적으로 최근 24시간에서 48시간까지 처리됩니다. <br/> |
|3.  <br/> |**그룹** 보기에는 존재하는 총 그룹 수와 수행된 그룹 대화 활동 수가 표시됩니다.  <br/> |
|4.  <br/> |**활동** 보기에는 그룹에서 게시하고, 읽고, 좋아요를 클릭한 Yammer 메시지 수가 표시됩니다.  <br/> |
|5.  <br/> | **그룹** 차트에서 Y축은 전체 또는 활성 그룹 수입니다.  <br/>  **활동** 차트에서 Y축은 Yammer 그룹에 대해 지정된 활동 수입니다.  <br/>  세 개의 모든 차트에서 X축은 특정 보고서에 대해 선택된 날짜 범위입니다.  <br/> |
|6.  <br/> |범례에서 항목을 선택하여 차트에 있는 계열을 필터링할 수 있습니다. 예를 들어 그룹  차트에서  총계 또는 **활성** 합계 및 활성 아이콘을 선택하여 각각에 관련된 정보만 ![ 볼 수 ](../../media/8eebd496-5955-4419-8d53-5f3ba1ad1c88.png) 있습니다.   이 선택 항목을 변경해도 눈금 표에 있는 정보가 변경되지는 않습니다.  <br/> |
|7.  <br/> | 표시되는 그룹 목록은 가장 긴 보고 기간(180일)에 존재한(삭제되지 않은) 모든 그룹 집합으로 결정됩니다. 활동 수(받은 메시지)는 날짜 선택에 따라 달라집니다.  <br/> 참고: 아래 목록에서 항목을 추가할 때까지 열에 일부 항목이 표시될 수 있습니다.<br/>**그룹 이름** 은 그룹의 이름입니다.  <br/> **그룹 관리자** 는 그룹 관리자 또는 소유자의 이름입니다.  <br/> **삭제됨** 은 삭제된 Yammer 그룹 수입니다. 그룹이 삭제되었지만 보고 기간 중 활동이 있는 경우 이 플래그가 true로 설정되어 표에 표시됩니다.  <br/> **종류** 는 그룹의 종류(공개 또는 비공개)입니다.  <br/> **Office 365에** 연결되면 Yammer 그룹이 Microsoft 365 그룹인지 여부를 나타냅니다.  <br/> **마지막 활동 날짜는** 그룹에서 메시지를 읽거나 게시하거나 좋아하는 최근 날짜입니다.  <br/> **구성원** 은 그룹의 구성원 수입니다.  <br/> **게시됨** 은 보고 기간에 Yammer 그룹에 게시된 메시지 수입니다.  <br/> **읽음** 은 보고 기간에 Yammer 그룹에서 읽은 메시지의 수입니다.  <br/> **좋아함** 은 보고 기간에 Yammer 그룹에서 좋아요를 클릭한 메시지 수입니다. <br/> **네트워크 이름은** 그룹이 속한 네트워크의 전체 이름입니다. <br/>  조직의 정책으로 인해 사용자 정보를 식별할 수 있는 보고서를 볼 수 없는 경우 이러한 모든 보고서의 개인 정보 설정을 변경할 수 있습니다. Microsoft 365 관리 센터의 활동 보고서에서 사용자 수준 세부 정보를 숨기는 방법 [섹션을 참조하세요.](activity-reports.md)   <br/> |
|8.  <br/> |열을 **선택하여** 보고서에서 열을 추가하거나 제거합니다.  <br/> ![Yammer groups activity - choose columns](../../media/c56c807f-fbc0-4d37-8bd3-e779bd0606a7.png)|
|9.  <br/> |내보내기 링크를 선택하여 보고서 데이터를 Excel .csv 파일로 내보낼 **수** 있습니다. 그러면 모든 사용자의 데이터를 내보내고 향후 분석을 위해 간단하게 정렬 및 필터링을 수행할 수 있습니다. 사용자가 2,000명 미만인 경우 보고서 자체의 표에서 정렬 및 필터링할 수 있습니다. 사용자가 2,000명 이상인 경우 필터링 및 정렬하려면 데이터를 내보내야 합니다.  <br/> |
|||
   

