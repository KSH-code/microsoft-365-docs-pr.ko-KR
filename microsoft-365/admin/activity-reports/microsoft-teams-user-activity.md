---
title: Microsoft 365 관리 센터 보고서 - Microsoft Teams 활동
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
ms.assetid: 07f67fc4-c0a4-4d3f-ad20-f40c7f6db524
description: 조직에서 사용자 Microsoft Teams 보고서를 얻고 조직에서 Teams 활동을 파악하는 방법을 학습합니다.
ms.openlocfilehash: ec5e6d2aa17fb3e58136a61336f06f6d41f3162f
ms.sourcegitcommit: bf3965b46487f6f8cf900dd9a3af8b213a405989
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/02/2021
ms.locfileid: "60648964"
---
# <a name="microsoft-365-admin-center-reports---microsoft-teams-user-activity"></a>Microsoft 365 관리 센터 보고서 - Microsoft Teams 활동

Microsoft 365 보고서 대시보드에는 조직의 제품 전체에 대한 활동 개요가 표시됩니다. 보고서 대시보드를 통해 개별 제품 수준 보고서의 하위 수준을 표시하여 각 제품 내의 활동에 대한 더 세부화된 정보를 확인할 수 있습니다. [보고서 개요 항목](activity-reports.md)을 확인하세요. Microsoft Teams 사용자 활동 보고서에서는 조직의 Microsoft Teams 활동에 대한 정보를 확인할 수 있습니다.
 
## <a name="how-to-get-to-the-microsoft-teams-user-activity-report"></a>Microsoft Teams 사용자 활동 보고서에 액세스하는 방법

1. 관리 센터에서 **보고서** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">사용 현황</a> 페이지를 참조하세요.

    
2. 보고서 **선택 드롭다운** 목록에서  사용자 Microsoft Teams \> **선택합니다.**
  
## <a name="interpret-the-microsoft-teams-user-activity-report"></a>Microsoft Teams 사용자 활동 보고서 해석

**활동** 및 **사용자** 차트를 보고 Microsoft Teams 사용자 활동에 대해 파악할 수 있습니다.<br/>![Microsoft 365 보고서 - Microsoft Teams 활동입니다.](../../media/40359f81-25f7-416d-bb1e-37289133ef6b.png)
  
|항목|설명|
|:-----|:-----|
|1.  <br/> |**Microsoft Teams 사용자 활동** 보고서에서 지난 7일, 30일, 90일 또는 180일간의 추세를 볼 수 있습니다. 그러나 보고서에서 특정 날짜를 선택하면 보고서가 생성된 날짜가 아니라 현재 날짜로부터 최대 28일간의 데이터가 표에 표시됩니다.  <br/> |
|2.  <br/> |각 보고서의 데이터는 일반적으로 최근 24시간에서 48시간까지 처리됩니다.  <br/> |
|3.  <br/> |데이터 품질을 보장하기 위해 지난 5일 동안 매일 데이터 유효성 검사를 수행하고 감지된 간격을 채울 것입니다. 프로세스 중에 기록 데이터에서 차이가 발견될 수 있습니다.  <br/> |
|4.  <br/> |**활동** 보기에는 활동 유형별 Microsoft Teams 활동 수가 표시됩니다. 활동 유형은 팀 채팅 메시지 수, 비공개 채팅 메시지 수, 통화 수 또는 모임 수입니다.  <br/> |
|5.  <br/> |**사용자** 보기에는 활동 유형별 사용자 수가 표시됩니다. 활동 유형은 팀 채팅 메시지 수, 비공개 채팅 메시지 수, 통화 수 또는 모임 수입니다.  <br/> |
|6.  <br/> | 활동 **차트에서** Y축은 지정된 활동의 수입니다.  <br/>  파일 **차트에서** Y축은 팀 채팅, 비공개 채팅, 통화 또는 모임에 참가하는 사용자 수입니다.  <br/>  차트의 X축은 특정 보고서에 대해 선택한 날짜 범위입니다.  <br/> |
|7.  <br/> |범례에서 항목을 선택하여 차트에 있는 계열을 필터링할 수 있습니다. 예를 들어 활동  차트에서 채널 메시지, 채팅 **메시지,** 통화  또는 모임을 선택하여 각각에 관련된 정보만 볼 수 있습니다.   이 선택 항목을 변경해도 눈금 표에 있는 정보가 변경되지는 않습니다.  <br/> ![활동 Microsoft Teams 필터링합니다.](../../media/c819c4ea-6e9a-4411-a0dd-9f800d64ce38.png)|
|8.  <br/> | 표시되는 그룹 목록은 가장 긴 보고 기간(180일)에 존재한(삭제되지 않은) 모든 그룹 집합으로 결정됩니다. 활동 수는 날짜 선택에 따라 달라집니다.  <br/> 참고: 아래 목록에서 항목을 추가할 때까지 열에 일부 항목이 표시될 수 있습니다.<br/>**사용자 이름** 은 사용자의 전자 메일 주소입니다. 실제 전자 메일 주소를 표시하거나 이 필드를 익명으로 만들 수 있습니다.  <br/> **마지막 활동 날짜(UTC)** 는 사용자가 Microsoft Teams 활동에 마지막으로 참여한 날짜를 나타냅니다.  <br/> **채널 메시지** 는 지정된 기간에 사용자가 팀 채팅에 게시한 고유 메시지 수입니다.  <br/> **채팅 메시지** 는 지정된 기간에 사용자가 비공개 채팅에 게시한 고유 메시지 수입니다.  <br/> **통화** 는 지정된 기간에 사용자가 참여한 통화 수입니다.  <br/> **모임** 은 지정된 기간에 사용자가 참여한 온라인 모임 수입니다.  <br/> **기타 활동** 은 사용자별 기타 팀 활동 수입니다.  <br/> **삭제됨** 은 팀이 삭제되었는지를 나타냅니다. 팀이 삭제되었지만, 보고 기간에 활동이 있는 경우 팀은 표에 삭제됨이 true로 설정된 상태로 표시됩니다.  <br/> **삭제된 날짜** 는 팀이 삭제된 날짜입니다.  <br/> **지정된 제품** 은 사용자에게 지정된 제품의 목록입니다.  <br/>  조직의 정책으로 인해 사용자 정보를 식별할 수 있는 보고서를 볼 수 없는 경우 이러한 모든 보고서의 개인 정보 설정을 변경할 수 있습니다. 작업 **보고서의** 사용자 수준 세부 정보를 숨기는 방법 섹션을 [Microsoft 365 관리 센터.](activity-reports.md)  <br/> |
|9.  <br/> |열을 **선택하여** 보고서에서 열을 추가하거나 제거합니다.  <br/> ![Teams 활동 보고서 - 열을 선택하십시오.](../../media/eb5fbcee-e371-4d36-a0c6-fa54732311ec.png)|
|10.  <br/> |내보내기 링크를 선택하여 보고서 데이터를 Excel .csv 내보낼 **수** 있습니다. 그러면 모든 사용자의 데이터를 내보내고 향후 분석을 위해 간단하게 정렬 및 필터링을 수행할 수 있습니다. 사용자가 2,000명 미만인 경우 보고서 자체의 표에서 정렬 및 필터링할 수 있습니다. 사용자가 2,000명 이상인 경우 필터링 및 정렬하려면 데이터를 내보내야 합니다.  <br/> |
|||
   

