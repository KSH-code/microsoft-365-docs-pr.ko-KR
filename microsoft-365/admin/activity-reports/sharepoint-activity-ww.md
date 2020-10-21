---
title: 관리 센터의 Microsoft 365 보고서-SharePoint 활동
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
description: SharePoint 작업 사용 보고서를 통해 모든 SharePoint 사용자의 활동, 공유 되는 파일 수 및 저장소 사용률에 대 한 정보를 확인할 수 있습니다.
ms.openlocfilehash: 1d4b288fed9e15139c92bc7e43795393d03ba2fb
ms.sourcegitcommit: 628f195cbe3c00910f7350d8b09997a675dde989
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/21/2020
ms.locfileid: "48649830"
---
# <a name="microsoft-365-reports-in-the-admin-center---sharepoint-activity"></a>관리 센터의 Microsoft 365 보고서-SharePoint 활동

Microsoft 365 관리자 인 **보고서** 대시보드에는 조직의 다양 한 제품에 대 한 활동 개요가 표시 됩니다. 각 제품의 고유한 활동에 대한 자세한 정보를 확인할 수 있습니다. [Microsoft 365 관리 센터에서 활동 보고서](activity-reports.md)를 확인 합니다.
  
예를 들어 파일과의 상호 작용을 확인하여 SharePoint를 사용하도록 라이선스가 부여된 모든 사용자의 활동을 파악할 수 있습니다. 또한 공유된 파일 수를 확인하여 진행 중인 공동 작업의 수준을 파악하는 데도 도움이 됩니다.
  
> [!NOTE]
> 보고서를 보려면 Microsoft 365 또는 Exchange, SharePoint, 팀 서비스, 팀 통신 또는 비즈니스용 Skype 관리자의 전역 관리자, 전역 독자 또는 보고서 독자 여야 합니다. 
 
## <a name="how-do-i-get-to-the-to-the-sharepoint-activity-report"></a>SharePoint 활동 보고서에 어떻게 액세스하나요?

1. 관리 센터에서 **보고서** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">사용 현황</a> 페이지를 참조하세요. 
2. 대시보드 홈 페이지에서 SharePoint 카드의 **자세히 보기** 단추를 클릭 합니다.
  
## <a name="interpret-the-sharepoint-activity-report"></a>SharePoint 활동 보고서 해석

**활동** 탭을 선택 하 여 SharePoint 보고서에서 활동을 볼 수 있습니다.<br/>![Microsoft 365 보고서-Microsoft SharePoint 활동 보고서](../../media/5a0a96f-0e4f-4fb9-8baa-3262275b3d1f.png)

**열 선택을** 선택 하 여 보고서에서 열을 추가 하거나 제거 합니다.  <br/> ![SharePoint 활동 보고서-열 선택](../../media/3c396cd1-9701-4712-8eaa-eb7bba702aa8.png)

**내보내기** 링크를 선택 하 여 보고서 데이터를 Excel .csv 파일로 내보낼 수도 있습니다. 그러면 모든 사용자의 데이터를 내보내고 향후 분석을 위해 간단하게 정렬 및 필터링을 수행할 수 있습니다. 사용자가 2,000명 미만인 경우 보고서 자체의 표에서 정렬 및 필터링할 수 있습니다. 사용자가 2,000명 이상인 경우 필터링 및 정렬하려면 데이터를 내보내야 합니다. 
  
|항목|설명|
|:-----|:-----|
|**메트릭**|**정의**|
|사용자 이름  <br/> |SharePoint 사이트에서 활동을 수행한 사용자의 전자 메일 주소입니다.  <br/> |
|마지막 활동 날짜 (UTC)  <br/> |파일 활동을 수행한 최근 날짜 또는 선택한 날짜 범위에 대 한 페이지가 방문 되었습니다. 특정 날짜에 발생한 활동을 보려면 차트에서 직접 날짜를 선택합니다.  <br/> |
|보거나 편집한 파일  <br/> |사용자가 업로드, 다운로드, 수정 또는 본 파일의 수입니다.   <br/> |
|동기화 된 파일  <br/> |사용자의 로컬 장치에서 SharePoint 사이트로 동기화 된 파일의 수입니다. <br/> |
|내부적으로 공유 되는 파일  <br/> | 조직 내의 사용자 또는 외부 사용자를 포함할 수 있는 그룹 내의 사용자와 공유 된 파일의 개수입니다.  <br/> |
|외부적으로 공유 되는 파일  <br/> |조직 외부의 사용자와 공유한 파일의 수입니다. <br/>|
|열어본 페이지  <br/> |사용자가 고유 페이지를 방문 합니다. <br/>|
|삭제됨  <br/> | 이는 사용자의 라이선스가 제거 되었음을 나타냅니다.  <br/>  **참고:** 삭제 된 사용자에 대 한 작업은 선택한 기간 동안 특정 시간에 라이선스가 부여 된 경우에만 보고서에 계속 표시 됩니다. 삭제된 열을 통해 사용자가 더 이상 활성이 아니지만 보고서의 데이터에 기여함을 알 수 있습니다.  <br/> |
|삭제 된 날짜  <br/> |사용자의 라이선스가 제거 된 날짜입니다. <br/>|
|할당 된 제품  <br/> |사용자에 게 라이선스가 부여 된 Microsoft 365 제품입니다.|
|||