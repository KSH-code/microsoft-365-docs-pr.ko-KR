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
description: Yammer 활동 보고서를 보고 메시지를 게시하거나 Yammer 읽은 사용자 수에 대해 자세히 알아 두세요.
ms.openlocfilehash: 42598322c58682e467eba99a7b01a7036fe05581
ms.sourcegitcommit: bf3965b46487f6f8cf900dd9a3af8b213a405989
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/02/2021
ms.locfileid: "60648758"
---
# <a name="microsoft-365-reports-in-the-admin-center---yammer-activity-report"></a>Microsoft 365 관리 센터의 보고서 - Yammer 활동 보고서

관리자 Microsoft 365 보고서 대시보드에는 조직 내의 제품 사용 현황에 대한 데이터가 표시됩니다. 관리 [센터에서 활동 보고서를 체크 아웃합니다.](activity-reports.md) **Yammer 활동 보고서** 를 사용하면 메시지를 게시하거나 좋아요를 클릭하거나 읽는 데 Yammer를 사용하는 고유한 사용자 수와 조직 전체에서 생성된 활동의 크기를 확인하여 조직의 Yammer 사용 수준을 이해할 수 있습니다. 
 
## <a name="how-do-i-get-to-the-yammer-activity-report"></a>Yammer 활동 보고서에 Yammer 방법

1. 관리 센터에서 **보고서** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">사용 현황</a> 페이지를 참조하세요. 
2. 대시보드 홈페이지의 대시보드 카드에서  더 보기 단추를 Yammer 클릭합니다.

  
## <a name="interpret-the-yammer-activity-report"></a>Yammer 활동 보고서 해석

활동 탭을 선택하여 보고서에서 Yammer **볼 수** 있습니다.<br/>![Microsoft 365 보고서 - Microsoft Yammer 활동 보고서.](../../media/9b251183-c2b3-430c-ab2d-58bf11e7e3ae.png)

열 **선택을 선택하여** 보고서에서 열을 추가하거나 제거합니다.  <br/> ![Yammer 활동 보고서 - 열을 선택하십시오.](../../media/7ef6351d-f7e9-4504-913d-2c2df9062bf6.png)

내보내기 링크를 선택하여 보고서 데이터를 Excel .csv 내보낼 **수** 있습니다. 그러면 모든 사용자의 데이터를 내보내고 향후 분석을 위해 간단하게 정렬 및 필터링을 수행할 수 있습니다. 사용자가 2,000명 미만인 경우 보고서 자체의 표에서 정렬 및 필터링할 수 있습니다. 사용자가 2,000명 이상인 경우 필터링 및 정렬하려면 데이터를 내보내야 합니다. 

Yammer **활동 보고서에서** 지난 7일, 30일, 90일 또는 180일간의 추세를 볼 수 있습니다. 그러나 보고서에서 특정 날짜를 선택하면 보고서가 생성된 날짜가 아니라 현재 날짜로부터 최대 28일간의 데이터가 표에 표시됩니다.
  
|항목|설명|
|:-----|:-----|
|**메트릭**|**정의**|
|사용자 이름  <br/> |사용자의 전자 메일 주소입니다. 실제 전자 메일 주소를 표시하거나 이 필드를 익명으로 만들 수 있습니다. 이 표에는 Yammer 계정을 사용하여 로그인한 Microsoft 365 로그인한 사용자 또는 Single Sign-On을 사용하여 네트워크에 로그인한 사용자가 표시됩니다. <br/> |
|표시 이름  <br/> |사용자의 전체 이름입니다. 실제 전자 메일 주소를 표시하거나 이 필드를 익명으로 만들 수 있습니다.  <br/> |
|사용자 상태  <br/> |세 가지 값 중 하나는 Activated, Deleted 또는 Suspended입니다. 이러한 보고서에서는 활성, 일시 중지 및 삭제된 사용자의 데이터를 표시합니다. 보류 중인 사용자는 메시지를 게시하거나 읽거나 좋아요를 클릭할 수 없으므로 보류 중인 사용자는 반영하지 않습니다.  <br/> |
|상태 변경 날짜(UTC)  <br/> |이 날짜에서 사용자의 상태가 변경된 Yammer.  <br/> |
|마지막 활동 날짜(UTC)  <br/> | 사용자가 메시지를 게시, 읽거나 좋아하는 마지막 날짜입니다.  <br/> |
|게시  <br/> |지정한 기간 동안 사용자가 게시한 메시지 수입니다. <br/>|
|읽기  <br/> |지정한 기간 동안 사용자가 읽은 대화 수입니다.  <br/> |
|Liked  <br/> |지정한 기간 동안 사용자가 좋아하는 메시지 수입니다.  <br/>|
|할당된 제품  <br/> |이 사용자에게 할당된 제품입니다.|
|||