---
title: 관리 센터의 Microsoft 365 보고서 - SharePoint 사이트 사용 현황
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
description: SharePoint 사이트 사용 현황 보고서를 통해 사용자가 SharePoint 사이트에 저장하는 파일 수, 적극적으로 사용되는 파일 수 및 사용된 총 저장소 수를 알 수 있습니다.
ms.openlocfilehash: bc9345a5e281f1e7343bf62a2dc6832587d0786e
ms.sourcegitcommit: 628f195cbe3c00910f7350d8b09997a675dde989
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/21/2020
ms.locfileid: "48649829"
---
# <a name="microsoft-365-reports-in-the-admin-center---sharepoint-site-usage"></a>관리 센터의 Microsoft 365 보고서 - SharePoint 사이트 사용 현황

Microsoft 365 관리자는 **보고서** 대시보드에 조직의 다양한 제품에 대한 활동 개요가 표시됩니다. 각 제품의 고유한 활동에 대한 자세한 정보를 확인할 수 있습니다. 예를 들어 사용자가 SharePoint 사이트에 저장한 총 파일 수, 현재 적극적으로 사용 중인 파일 수 및 모든 SharePoint 사이트에서 사용된 저장소와 관련하여 SharePoint에서 얻는 값을 대략적으로 볼 수 있습니다. 그런 다음 SharePoint 사이트 사용 보고서를 확인하여 추세와 모든 사이트에 대한 수준별 세부 정보를 파악할 수 있습니다. 
  
> [!NOTE]
> Microsoft 365의 전역 관리자, 전역 읽기 권한자 또는 보고서 읽기 권한자 또는 Exchange, SharePoint, Teams 서비스, Teams 커뮤니케이션 또는 비즈니스용 Skype 관리자인 경우 보고서를 볼 수 있어야 합니다.
관리 센터의 Microsoft 365 보고서는 GCC High 및 DoD 테넌트에 지원되지 않습니다.
 
## <a name="how-to-get-to-the-sharepoint-site-usage-report"></a>SharePoint 사이트 사용 보고서에 액세스하는 방법

1. 관리 센터에서 **보고서** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">사용 현황</a> 페이지를 참조하세요. 
2. 대시보드 홈페이지에서 SharePoint 카드의  더 보기 단추를 클릭합니다.
  
## <a name="interpret-the-sharepoint-site-usage-report"></a>SharePoint 사이트 사용 현황 보고서 해석

사이트 사용 탭을 선택하여 SharePoint 보고서에서 사이트 사용 **현황을 볼 수** 있습니다.<br/>![Microsoft 365 보고서 - Microsoft SharePoint 사이트 사용 현황 보고서](../../media/d1cb6200-e81c-460b-9d05-53f4bd7cf5ee.png)

열 **선택을 선택하여** 보고서에서 열을 추가하거나 제거합니다.  <br/> ![SharePoint 사이트 사용 현황 보고서 - 열 선택](../../media/639f3cfd-6725-4318-a225-6d5c2f01770c.png)

내보내기 링크를 선택하여 보고서 데이터를 Excel .csv 파일로 내보낼 **수** 있습니다. 그러면 모든 사용자의 데이터를 내보내고 향후 분석을 위해 간단하게 정렬 및 필터링을 수행할 수 있습니다. 사용자가 2,000명 미만인 경우 보고서 자체의 표에서 정렬 및 필터링할 수 있습니다. 사용자가 2,000명 이상인 경우 필터링 및 정렬하려면 데이터를 내보내야 합니다. 
  
|항목|설명|
|:-----|:-----|
|**메트릭**|**정의**|
|사이트 URL  <br/> |사이트의 전체 URL입니다. <br/> |
|삭제됨  <br/> |사이트의 지우기 상태입니다. 사이트가 삭제됨으로 표시되려면 7일 이상이 소요됩니다.  <br/> |
|사이트 소유자  <br/> |사이트의 기본 소유자의 사용자 이름입니다.   <br/> |
|사이트 소유자 사용자 이름  <br/> |사이트 소유자의 전자 메일 주소입니다. <br/> |
|마지막 활동 날짜(UTC)  <br/> | 파일 활동이 마지막으로 검색되거나 사이트에서 페이지를 본 날짜입니다.  <br/> |
|파일  <br/> |사이트의 파일 수입니다. <br/>|
|활성 파일  <br/> | 사이트의 활성 파일 수입니다.<br/> 참고: 보고서에 대해 지정된 기간 동안 파일이 제거된 경우 보고서에 표시된 활성 파일 수가 사이트의 현재 파일 수보다 클 수 있습니다.  <br/> |
|사용된 저장소(MB)  <br/> |현재 사이트에서 사용 중인 저장소의 양입니다.  <br/>|
|할당된 저장소(MB)  <br/> |사이트에 할당된 최대 저장소 양입니다.  <br/>|
|페이지 보기  <br/> |사이트에서 페이지를 본 횟수입니다.  <br/>|
|방문한 페이지  <br/> |사이트에서 방문한 고유 페이지 수입니다.  <br/>|
|루트 웹 서식 파일  <br/> |사이트를 만드는 데 사용되는 서식 파일입니다.  <br/> 참고: 여러 사이트 유형으로 데이터를 필터링하려는 경우 데이터를 내보내고 루트 웹 서식 파일 열을 사용하세요. |
|||