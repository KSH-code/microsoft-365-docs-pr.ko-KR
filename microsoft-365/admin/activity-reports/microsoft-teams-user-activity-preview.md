---
title: 관리 센터의 Microsoft 365 보고서 - Microsoft Teams 사용자 활동
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
ms.localizationpriority: medium
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
description: 조직에서 사용자 Microsoft Teams 보고서를 얻고 조직에서 Teams 활동을 파악하는 방법을 학습합니다.
ms.openlocfilehash: 6c30575cd333ea1ad161fceefcee4e8ba3737762
ms.sourcegitcommit: 3140e2866de36d57a27d27f70d47e8167c9cc907
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/23/2021
ms.locfileid: "60553139"
---
# <a name="microsoft-365-reports-in-the-admin-center---microsoft-teams-user-activity"></a>관리 센터의 Microsoft 365 보고서 - Microsoft Teams 사용자 활동

Microsoft 365 **보고서** 대시보드에는 조직의 제품 전체에 대한 활동 개요가 표시됩니다. 보고서 대시보드를 통해 개별 제품 수준 보고서의 하위 수준을 표시하여 각 제품 내의 활동에 대한 더 세부화된 정보를 확인할 수 있습니다. [보고서 개요 항목](activity-reports.md)을 확인하세요. Microsoft Teams 사용자 활동 보고서에서는 조직의 Microsoft Teams 활동에 대한 정보를 확인할 수 있습니다.
 
## <a name="how-to-get-to-the-microsoft-teams-user-activity-report"></a>Microsoft Teams 사용자 활동 보고서에 액세스하는 방법

1. 관리 센터에서 **보고서** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">사용 현황</a> 페이지를 참조하세요.
2. 대시보드 홈페이지의 대시보드 활동 카드에서 더 보기 단추를 Microsoft Teams 클릭합니다. 

## <a name="interpret-the-microsoft-teams-user-activity-report"></a>Microsoft Teams 사용자 활동 보고서 해석

사용자 활동 탭을 선택하여 Teams **보고서에서** 사용자 활동을 볼 수 있습니다. <br/>![Microsoft 365 보고서 - Microsoft Teams 활동입니다.](../../media/1011877f-3cf0-4417-9447-91d0b2312aab.png)

열 **선택을 선택하여** 보고서에서 열을 추가하거나 제거합니다.  <br/> ![Teams 활동 보고서 - 열을 선택하십시오.](../../media/6d3c013e-2c5e-4d66-bb41-998aa4bd1c20.png)

내보내기 링크를 선택하여 보고서 데이터를 Excel .csv 내보낼 **수** 있습니다. 그러면 모든 사용자의 데이터를 내보내고 향후 분석을 위해 간단하게 정렬 및 필터링을 수행할 수 있습니다. 사용자가 2,000명 미만인 경우 보고서 자체의 표에서 정렬 및 필터링할 수 있습니다. 사용자가 2,000명 이상인 경우 필터링 및 정렬하려면 데이터를 내보내야 합니다. 오디오 **시간,** 비디오 시간 및 화면 **공유** 시간의 내보낼 형식은 ISO8601 기간 형식을 나타냅니다.

**Microsoft Teams 사용자 활동** 보고서에서 지난 7일, 30일, 90일 또는 180일간의 추세를 볼 수 있습니다. 그러나 보고서에서 특정 날짜를 선택하면 보고서가 생성된 날짜가 아니라 현재 날짜로부터 최대 28일간의 데이터가 표에 표시됩니다.

데이터 품질을 보장하기 위해 지난 3일 동안 매일 데이터 유효성 검사를 수행하고 감지된 간격을 모두 채울 것입니다. 프로세스 중에 기록 데이터에서 차이가 발견될 수 있습니다.

|항목|설명|
|:-----|:-----|
|**메트릭**|**정의**|
|사용자 이름  <br/> |사용자의 전자 메일 주소입니다. 실제 전자 메일 주소를 표시하거나 이 필드를 익명으로 만들 수 있습니다.   <br/> |
|채널 메시지   <br/> |지정된 기간 동안 사용자가 팀 채팅에 게시한 고유 메시지 수입니다.  <br/> |
|채팅 메시지   <br/> |지정된 기간 동안 사용자가 비공개 채팅에 게시한 고유 메시지 수입니다.  <br/> |
|총 모임 수   <br/> |지정된 기간 동안 사용자가 참가한 온라인 모임 수입니다.  <br/> |
|1:1 통화   <br/> | 지정된 기간 동안 사용자가 참여한 1:1 통화 수입니다.  <br/> |
|마지막 활동 날짜(UTC)  <br/> |사용자가 활동 활동에 마지막으로 참여한 Microsoft Teams 날짜입니다.<br/> |
|모임에 참여한 애드워크   <br/> | 지정된 기간 동안 사용자가 참가한 회의 수입니다.  <br/> |
|모임이 조직된 애드워크 <br/> |지정된 기간 동안 사용자가 구성한 회의의 수입니다. <br/>|
|총 모임 구성  <br/> |지정된 기간 동안 사용자가 구성한 일회성 예약 모임, 재발, 애드 호 및 미분리 모임의 합계입니다.  <br/> |
|총 참여 모임 수  <br/> |지정된 기간 동안 사용자가 참가한 일회성, 재발, 애드 호 및 미분리 모임의 합계입니다.  <br/> |
|예약된 일회성 모임 구성  <br/> |지정된 기간 동안 사용자가 구성한 일회성 예약 모임 수입니다.  <br/> |
|예약된 모임 예약된 모임  <br/> |지정된 기간 동안 사용자가 구성한 재발 모임 수입니다.  <br/> |
|모임이 예약된 일회성 모임  <br/> |지정된 기간 동안 사용자가 참가한 일회성 예약 모임 수입니다.  <br/> |
|모임이 예약된 예약된 모임에 참가  <br/> |지정된 기간 동안 사용자가 참가한 재발 모임 수입니다.  <br/> |
|사용이 허가됩니다.  <br/> |사용자에게 사용이 허가된 경우 선택된 Teams. <br/>|
|기타 활동  <br/>|사용자는 활성 상태이지만 보고서에 제공된 노출된 작업 유형(채널 메시지 및 채팅 메시지 보내기 또는 회신, 1:1 통화 및 모임에 참가 또는 참가)보다 다른 작업을 수행했습니다. 예를 들어 사용자가 메시지 상태 또는 Teams 상태 메시지를 Teams 채널 메시지 게시물을 열지만 회신하지 않는 경우를 예로 들 수 있습니다.  <br/>|
|미분위 모임 <br/>|일정 또는 재발 또는 애드 호로 분류할 수 없습니다. 이는 숫자로 짧고 대부분 변조된 원격 분석 정보로 식별할 수 없습니다. |
|||
