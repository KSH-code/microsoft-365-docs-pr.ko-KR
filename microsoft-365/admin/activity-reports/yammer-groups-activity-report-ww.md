---
title: Microsoft 365 관리 센터의 보고서 - Yammer 활동 보고서
f1.keywords:
- NOCSH
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
- MST160
- MET150
- MOE150
description: 조직에서 Yammer 그룹 활동 보고서를 통해 조직에서 만들어 Yammer 그룹 수와 해당 활동을 알 수 있습니다.
ms.openlocfilehash: dcf1851d2ce7d5e21daaaa8fffeff11b8e9c6213
ms.sourcegitcommit: 3140e2866de36d57a27d27f70d47e8167c9cc907
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/23/2021
ms.locfileid: "60552899"
---
# <a name="microsoft-365-reports-in-the-admin-center---yammer-groups-activity-report"></a>Microsoft 365 관리 센터의 보고서 - Yammer 활동 보고서

Microsoft 365 **보고서** 대시보드에는 조직의 제품 전체에 대한 활동 개요가 표시됩니다. 보고서 대시보드를 통해 개별 제품 수준 보고서의 하위 수준을 표시하여 각 제품 내의 활동에 대한 더 세부화된 정보를 확인할 수 있습니다. [보고서 개요 항목](activity-reports.md)을 확인하세요. Yammer 그룹 활동 보고서에서는 조직의 Yammer 그룹 활동을 파악하고, 만들어지고 사용되는 Yammer 그룹의 수를 확인할 수 있습니다.
 
## <a name="how-do-i-get-to-the-yammer-groups-activity-report"></a>그룹 활동 보고서에 Yammer 어떻게 하나요?

1. 관리 센터에서 **보고서** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">사용 현황</a> 페이지를 참조하세요. 
2. 대시보드 홈페이지의 대시보드 카드에서  더 보기 단추를 Yammer 클릭합니다.

  
## <a name="interpret-the-yammer-groups-activity-report"></a>Yammer 그룹 활동 보고서 해석

그룹 활동 탭을 선택하여 그룹 Yammer 볼 **수** 있습니다.<br/>![Microsoft 365 보고서 - Microsoft Yammer 그룹 활동 보고서.](../../media/3afdafe5-9269-402e-8264-c7695ceb227d.png)

열 **선택을 선택하여** 보고서에서 열을 추가하거나 제거합니다.  <br/> ![Yammer 그룹 활동 보고서 - 열을 선택하십시오.](../../media/54744932-34fe-48c3-9779-1d10c3f05be1.png)

내보내기 링크를 선택하여 보고서 데이터를 Excel .csv 내보낼 **수** 있습니다. 그러면 모든 사용자의 데이터를 내보내고 향후 분석을 위해 간단하게 정렬 및 필터링을 수행할 수 있습니다. 사용자가 2,000명 미만인 경우 보고서 자체의 표에서 정렬 및 필터링할 수 있습니다. 사용자가 2,000명 이상인 경우 필터링 및 정렬하려면 데이터를 내보내야 합니다. 

**Yammer 그룹 활동** 보고서에서 지난 7일, 30일, 90일 또는 180일간의 추세를 볼 수 있습니다. 그러나 보고서에서 특정 날짜를 선택하면 보고서가 생성된 날짜가 아니라 현재 날짜로부터 최대 28일간의 데이터가 표에 표시됩니다.
  
|항목|설명|
|:-----|:-----|
|**메트릭**|**정의**|
|그룹 이름  <br/> |그룹의 이름입니다. <br/> |
|그룹 관리자  <br/> |그룹 관리자 또는 소유자의 이름입니다.  <br/> |
|삭제됨  <br/> |삭제된 그룹 Yammer 수입니다. 그룹이 삭제되었지만 보고 기간 중 활동이 있는 경우 이 플래그가 true로 설정되어 표에 표시됩니다.  <br/> |
|유형  <br/> |그룹 유형(공개 또는 비공개)입니다. <br/> |
|연결 Office 365  <br/> |그룹이 Yammer 그룹인지 여부를 Microsoft 365 나타냅니다. <br/> |
|마지막 활동 날짜(UTC)  <br/> | 그룹에서 메시지를 읽거나 게시하거나 좋아하는 최근 날짜입니다.  <br/> |
|구성원  <br/> | 그룹의 구성원 수입니다.  <br/> |
|게시  <br/> |보고 기간 동안 Yammer 그룹에 게시된 메시지 수입니다. <br/>|
|읽기  <br/> |보고 기간 동안 Yammer 그룹에서 읽은 대화 수입니다.  <br/> |
|Liked  <br/> |보고 기간 동안 Yammer 그룹에서 좋아하는 메시지 수입니다. <br/>|
|네트워크 이름  <br/> |그룹이 속한 네트워크의 전체 이름입니다. |
|||