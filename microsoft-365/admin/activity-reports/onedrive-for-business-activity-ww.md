---
title: Microsoft 365 관리 센터의 보고서 - 비즈니스용 OneDrive 활동
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
- MST160
- MET150
- MOE150
description: 조직의 OneDrive 사용 현황 보고서를 보고 모든 OneDrive 사용자, 공유되는 파일 수 및 저장소 사용률을 알 수 있습니다.
ms.openlocfilehash: 145bf6cc4f079e4916730b949ed0c4a798242860
ms.sourcegitcommit: d08fe0282be75483608e96df4e6986d346e97180
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/12/2021
ms.locfileid: "59185420"
---
# <a name="microsoft-365-reports-in-the-admin-center---onedrive-for-business-activity"></a>Microsoft 365 관리 센터의 보고서 - 비즈니스용 OneDrive 활동

Microsoft 365 **보고서** 대시보드에는 조직의 제품 전체에 대한 활동 개요가 표시됩니다. 보고서 대시보드를 통해 개별 제품 수준 보고서의 하위 수준을 표시하여 각 제품 내의 활동에 대한 더 세부화된 정보를 확인할 수 있습니다. [보고서 개요 항목](activity-reports.md)을 확인하세요.
  
예를 들어 OneDrive에 있는 파일과의 상호 작용을 확인하여 OneDrive를 사용하도록 라이선스가 부여된 모든 사용자의 활동을 파악할 수 있습니다. 또한 공유된 파일 수를 확인하여 진행 중인 공동 작업의 수준을 파악하는 데도 도움이 됩니다.
  
> [!NOTE]
> 보고서를 표시하려면 Microsoft 365, Exchange, SharePoint, Teams 서비스, Teams Communications 또는 비즈니스용 Skype 관리자의 전역 관리자, 전역 읽기 권한자 또는 보고서 읽기 권한자 비즈니스용 Skype 있어야 합니다.  
 
## <a name="how-do-i-get-to-the-onedrive-activity-report"></a>OneDrive 활동 보고서에 액세스하려면 어떻게 하나요?

1. 관리 센터에서 **보고서** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">사용 현황</a> 페이지를 참조하세요. 
2. 대시보드 홈페이지의 대시보드 카드에서  더 보기 단추를 OneDrive 클릭합니다.
  
## <a name="interpret-the-onedrive-for-business-activity-report"></a>비즈니스용 OneDrive 활동 보고서 해석

활동 탭을 선택하여 보고서에서 OneDrive 볼 **수** 있습니다.<br/>![Microsoft 365 - Microsoft OneDrive 보고서입니다.](../../media/c89df0b0-2611-4acf-9ef7-17cedf7977be.png)

열 **선택을 선택하여** 보고서에서 열을 추가하거나 제거합니다.  <br/> ![OneDrive 보고서 - 열을 선택하십시오.](../../media/252f311f-ffde-4e5a-9158-2b822bf86964.png)

내보내기 링크를 선택하여 보고서 데이터를 Excel .csv 내보낼 **수** 있습니다. 그러면 모든 사용자의 데이터를 내보내고 향후 분석을 위해 간단하게 정렬 및 필터링을 수행할 수 있습니다. 사용자가 2,000명 미만인 경우 보고서 자체의 표에서 정렬 및 필터링할 수 있습니다. 사용자가 2,000명 이상인 경우 필터링 및 정렬하려면 데이터를 내보내야 합니다. 
  
|항목|설명|
|:-----|:-----|
|**메트릭**|**정의**|
|사용자 이름  <br/> |계정 소유자의 사용자 OneDrive.  <br/> |
|마지막 활동 날짜(UTC)  <br/> |선택한 날짜 범위에 대한 OneDrive 활동이 수행된 최근 날짜입니다. . 특정 날짜에 발생한 활동을 보려면 차트에서 직접 날짜를 선택합니다.  <br/> |
|보거나 편집한 파일  <br/> |사용자가 업로드, 다운로드, 수정 또는 본 파일 수입니다.   <br/> |
|동기화된 파일  <br/> |사용자의 로컬 장치에서 로컬 계정으로 동기화된 파일 OneDrive 수입니다. <br/> |
|내부적으로 공유되는 파일  <br/> | 조직 내의 사용자 또는 그룹 내의 사용자(외부 사용자를 포함할 수 있는 사용자)와 공유된 파일 수입니다.  <br/> |
|외부에서 공유되는 파일  <br/> |조직 외부의 사용자와 공유된 파일 수입니다. <br/>|
|삭제됨  <br/> | 이는 사용자의 라이선스가 제거되었다는 것입니다.  <br/> 참고: 삭제된 사용자의 활동은 선택한 기간 동안 사용이 허가된 경우 보고서에 계속 표시됩니다. **삭제된** 열을 통해 사용자가 더 이상 활성이 아니지만 보고서의 데이터에 기여함을 알 수 있습니다.  <br/> |
|삭제된 날짜  <br/> |사용자의 라이선스가 제거된 날짜입니다. <br/>|
|할당된 제품  <br/> |사용자에게 Microsoft 365 라이선스가 있는 제품입니다.|
|||