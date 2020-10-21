---
title: 관리 센터의 Microsoft 365 보고서-SharePoint 사이트 사용 현황
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
ms.custom: AdminSurgePortfolio
ROBOTS: NOINDEX, NOFOLLOW
search.appverid:
- BCS160
- MST160
- MET150
- MOE150
description: Sharepoint 사이트 사용 보고서를 다운로드 하 여 사용자가 SharePoint 사이트에 저장 하는 파일의 수, 현재 사용 되 고 있는 총 저장소 및 사용 된 전체 저장 용량을 확인 합니다.
ms.openlocfilehash: bc9345a5e281f1e7343bf62a2dc6832587d0786e
ms.sourcegitcommit: 628f195cbe3c00910f7350d8b09997a675dde989
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/21/2020
ms.locfileid: "48649829"
---
# <a name="microsoft-365-reports-in-the-admin-center---sharepoint-site-usage"></a>관리 센터의 Microsoft 365 보고서-SharePoint 사이트 사용 현황

Microsoft 365 관리자 인 **보고서** 대시보드에는 조직의 다양 한 제품에 대 한 활동 개요가 표시 됩니다. 각 제품의 고유한 활동에 대한 자세한 정보를 확인할 수 있습니다. 예를 들어 사용자가 SharePoint 사이트에 저장한 총 파일 수, 현재 적극적으로 사용 중인 파일 수 및 모든 SharePoint 사이트에서 사용된 저장소와 관련하여 SharePoint에서 얻는 값을 대략적으로 볼 수 있습니다. 그런 다음 SharePoint 사이트 사용 보고서를 확인하여 추세와 모든 사이트에 대한 수준별 세부 정보를 파악할 수 있습니다. 
  
> [!NOTE]
> 보고서를 보려면 Microsoft 365 또는 Exchange, SharePoint, 팀 서비스, 팀 통신 또는 비즈니스용 Skype 관리자의 전역 관리자, 전역 독자 또는 보고서 독자 여야 합니다.
관리 센터의 Microsoft 365 보고서는 GCC High 및 DoD 테 넌 트에 대해서는 지원 되지 않습니다.
 
## <a name="how-to-get-to-the-sharepoint-site-usage-report"></a>SharePoint 사이트 사용 보고서에 액세스하는 방법

1. 관리 센터에서 **보고서** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">사용 현황</a> 페이지를 참조하세요. 
2. 대시보드 홈 페이지에서 SharePoint 카드의 **자세히 보기** 단추를 클릭 합니다.
  
## <a name="interpret-the-sharepoint-site-usage-report"></a>SharePoint 사이트 사용 현황 보고서 해석

**사이트 사용** 탭을 선택 하 여 SharePoint 보고서에서 사이트 사용량을 볼 수 있습니다.<br/>![Microsoft 365 보고서-Microsoft SharePoint 사이트 사용 현황 보고서](../../media/d1cb6200-e81c-460b-9d05-53f4bd7cf5ee.png)

**열 선택을** 선택 하 여 보고서에서 열을 추가 하거나 제거 합니다.  <br/> ![SharePoint 사이트 사용 현황 보고서-열 선택](../../media/639f3cfd-6725-4318-a225-6d5c2f01770c.png)

**내보내기** 링크를 선택 하 여 보고서 데이터를 Excel .csv 파일로 내보낼 수도 있습니다. 그러면 모든 사용자의 데이터를 내보내고 향후 분석을 위해 간단하게 정렬 및 필터링을 수행할 수 있습니다. 사용자가 2,000명 미만인 경우 보고서 자체의 표에서 정렬 및 필터링할 수 있습니다. 사용자가 2,000명 이상인 경우 필터링 및 정렬하려면 데이터를 내보내야 합니다. 
  
|항목|설명|
|:-----|:-----|
|**메트릭**|**정의**|
|사이트 URL  <br/> |사이트의 전체 URL입니다. <br/> |
|삭제됨  <br/> |사이트의 삭제 상태입니다. 사이트가 삭제됨으로 표시되려면 7일 이상이 소요됩니다.  <br/> |
|사이트 소유자  <br/> |사이트의 주 소유자의 사용자 이름입니다.   <br/> |
|사이트 소유자의 사용자 이름  <br/> |사이트 소유자의 전자 메일 주소입니다. <br/> |
|마지막 활동 날짜 (UTC)  <br/> | 마지막으로 파일 활동이 검색 되었거나 사이트에서 페이지를 본 날짜입니다.  <br/> |
|파일  <br/> |사이트에 있는 파일의 수입니다. <br/>|
|활성 파일  <br/> | 사이트에 있는 활성 파일의 수입니다.<br/> 참고: 보고서에 대해 지정 된 기간 동안 파일이 제거 된 경우 보고서에 표시 되는 활성 파일의 수는 사이트의 현재 파일 수 보다 클 수 있습니다.  <br/> |
|사용 되는 저장소 (MB)  <br/> |현재 사이트에서 사용 되 고 있는 저장소 크기입니다.  <br/>|
|할당 된 저장소 (MB)  <br/> |사이트에 할당 된 저장소의 최대 크기입니다.  <br/>|
|페이지 보기  <br/> |사이트에서 페이지를 본 횟수입니다.  <br/>|
|열어본 페이지  <br/> |사이트에서 열어본 고유 페이지 수입니다.  <br/>|
|루트 웹 서식 파일  <br/> |사이트를 만드는 데 사용 되는 서식 파일입니다.  <br/> 참고: 다른 사이트 유형별로 데이터를 필터링 하려면 데이터를 내보내고 루트 웹 서식 파일 열을 사용 합니다. |
|||