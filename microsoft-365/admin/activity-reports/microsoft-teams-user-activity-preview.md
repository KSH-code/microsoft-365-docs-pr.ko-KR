---
title: 관리 센터의 microsoft 365 보고서-Microsoft 팀 사용자 활동
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ROBOTS: NOINDEX, NOFOLLOW
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
description: Microsoft 팀 사용자 활동 보고서를 가져오고 조직의 팀 활동에 대 한 정보를 파악 하는 방법을 알아봅니다.
ms.openlocfilehash: b85f073a2916b646a5a03e62913de44b410ca058
ms.sourcegitcommit: 82d8be71c5861a501ac62a774b306a3fc1d4e627
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/10/2020
ms.locfileid: "48988473"
---
# <a name="microsoft-365-reports-in-the-admin-center---microsoft-teams-user-activity"></a>관리 센터의 microsoft 365 보고서-Microsoft 팀 사용자 활동

Microsoft 365 **보고서** 대시보드에는 조직의 제품 전체에 대 한 활동 개요가 표시 됩니다. 보고서 대시보드를 통해 개별 제품 수준 보고서의 하위 수준을 표시하여 각 제품 내의 활동에 대한 더 세부화된 정보를 확인할 수 있습니다. [보고서 개요 항목](activity-reports.md)을 확인하세요. Microsoft Teams 사용자 활동 보고서에서는 조직의 Microsoft Teams 활동에 대한 정보를 확인할 수 있습니다.
  
> [!NOTE]
> 보고서를 보려면 Microsoft 365 또는 Exchange, SharePoint, 팀 서비스, 팀 통신 또는 비즈니스용 Skype 관리자의 전역 관리자, 전역 독자 또는 보고서 독자 여야 합니다.  
 
## <a name="how-to-get-to-the-microsoft-teams-user-activity-report"></a>Microsoft Teams 사용자 활동 보고서에 액세스하는 방법

1. 관리 센터에서 **보고서** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">사용 현황</a> 페이지를 참조하세요.
2. 대시보드 홈 페이지에서 Microsoft 팀 활동 카드의 **기타 보기** 단추를 클릭 합니다.

## <a name="interpret-the-microsoft-teams-user-activity-report"></a>Microsoft Teams 사용자 활동 보고서 해석

**사용자 작업** 탭을 선택 하 여 팀 보고서에서 사용자 활동을 볼 수 있습니다. <br/>![Microsoft 365 보고서-Microsoft 팀 사용자 활동](../../media/1011877f-3cf0-4417-9447-91d0b2312aab.png)

**열 선택을** 선택 하 여 보고서에서 열을 추가 하거나 제거 합니다.  <br/> ![Teams user activity report - choose columns](../../media/a1513028-cf09-4186-93a6-8a203cd22475.png)

**내보내기** 링크를 선택 하 여 보고서 데이터를 Excel .csv 파일로 내보낼 수도 있습니다. 그러면 모든 사용자의 데이터를 내보내고 향후 분석을 위해 간단하게 정렬 및 필터링을 수행할 수 있습니다. 사용자가 2,000명 미만인 경우 보고서 자체의 표에서 정렬 및 필터링할 수 있습니다. 사용자가 2,000명 이상인 경우 필터링 및 정렬하려면 데이터를 내보내야 합니다. 내보낸 형식 ( **오디오 시간** , **비디오 시간** 및 **화면 공유 시간** )은 ISO8601 duration 형식에 따릅니다.

|항목|설명|
|:-----|:-----|
|**메트릭**|**정의**|
|사용자 이름  <br/> |사용자의 전자 메일 주소입니다. 실제 전자 메일 주소를 표시하거나 이 필드를 익명으로 만들 수 있습니다.   <br/> |
|채널 메시지   <br/> |지정 된 기간에 사용자가 팀 채팅에 게시 한 고유 메시지 수입니다.  <br/> |
|채팅 메시지   <br/> |지정 된 기간에 사용자가 비공개 채팅에 게시 한 고유 메시지 수입니다.  <br/> |
|총 모임   <br/> |지정 된 기간에 사용자가 참여 한 온라인 모임 수입니다.  <br/> |
|1:1 통화   <br/> | 지정 된 기간에 사용자가 참여 한 1:1 통화 수입니다.  <br/> |
|마지막 활동 날짜 (UTC)  <br/> |사용자가 Microsoft 팀 활동에 참여 한 마지막 날짜입니다.<br/> |
|참가 한 임시 모임   <br/> | 지정 된 기간에 사용자가 참여 한 일정에 예약 되지 않은 모임 수입니다.  <br/> |
|임시로 구성 된 모임 <br/> |지정 된 기간에 사용자가 구성한 일정에 예약 되지 않은 모임 수입니다. <br/>|
|예약 된 모임  <br/> |지정 된 기간에 사용자가 구성한 예약 된 모임 수입니다.  <br/> |
|사용이 허가 됨 |사용자에 게 팀 사용이 허가 된 경우 선택 됩니다.|
|기타 활동|사용자가 활성 상태 이지만 보고서에서 제공 되는 표시 된 작업 유형 (예: 채널 메시지와 채팅 메시지 보내기 또는 회신, 1:1 통화 및 모임 참여) 보다 다른 작업을 수행 했습니다. 예를 들면, 사용자가 팀 상태나 팀 상황 메시지를 변경 하거나 채널 메시지를 게시 한 후에는 회신 하지 않는 경우를 들 수 있습니다. |
|||