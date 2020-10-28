---
title: 관리 센터의 Microsoft 365 보고서-Yammer 활동 보고서
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
description: Yammer 활동 보고서를 가져오고 Yammer를 사용 하 여 메시지를 게시 하거나 읽거나 읽는 사용자 수에 대 한 자세한 정보를 확인 하세요.
ms.openlocfilehash: fc6bf252892cc9b3f30cdcf464cd44cfc83c4f75
ms.sourcegitcommit: c51de5e1a4cb9c4a7a9854a4226b32453d9e73e0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/28/2020
ms.locfileid: "48779378"
---
# <a name="microsoft-365-reports-in-the-admin-center---yammer-activity-report"></a>관리 센터의 Microsoft 365 보고서-Yammer 활동 보고서

Microsoft 365 admin의 **보고서** 대시보드에는 조직 내 제품의 사용 현황에 대 한 데이터가 표시 됩니다. [관리 센터에서 활동 보고서](activity-reports.md)를 체크 아웃 합니다. **Yammer 활동 보고서** 를 사용하면 메시지를 게시하거나 좋아요를 클릭하거나 읽는 데 Yammer를 사용하는 고유한 사용자 수와 조직 전체에서 생성된 활동의 크기를 확인하여 조직의 Yammer 사용 수준을 이해할 수 있습니다. 
  
> [!NOTE]
> 보고서를 보려면 Microsoft 365 또는 Exchange, SharePoint, 팀 서비스, 팀 통신 또는 비즈니스용 Skype 관리자의 전역 관리자, 전역 독자 또는 보고서 독자 여야 합니다.  
 
## <a name="how-do-i-get-to-the-yammer-activity-report"></a>Yammer 활동 보고서에 액세스 하려면 어떻게 해야 합니까?

1. 관리 센터에서 **보고서** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">사용 현황</a> 페이지를 참조하세요. 
2. 대시보드 홈 페이지에서 Yammer 카드의 **자세히 보기** 단추를 클릭 합니다.

  
## <a name="interpret-the-yammer-activity-report"></a>Yammer 활동 보고서 해석

**작업** 탭을 선택 하 여 Yammer 보고서에서 활동을 볼 수 있습니다.<br/>![Microsoft 365 reports-Microsoft Yammer 활동 보고서입니다.](../../media/9b251183-c2b3-430c-ab2d-58bf11e7e3ae.png)

**열 선택을** 선택 하 여 보고서에서 열을 추가 하거나 제거 합니다.  <br/> ![Yammer 활동 보고서-열 선택](../../media/7ef6351d-f7e9-4504-913d-2c2df9062bf6.png)

**내보내기** 링크를 선택 하 여 보고서 데이터를 Excel .csv 파일로 내보낼 수도 있습니다. 그러면 모든 사용자의 데이터를 내보내고 향후 분석을 위해 간단하게 정렬 및 필터링을 수행할 수 있습니다. 사용자가 2,000명 미만인 경우 보고서 자체의 표에서 정렬 및 필터링할 수 있습니다. 사용자가 2,000명 이상인 경우 필터링 및 정렬하려면 데이터를 내보내야 합니다. 
  
|항목|설명|
|:-----|:-----|
|**메트릭**|**정의**|
|사용자 이름  <br/> |사용자의 전자 메일 주소입니다. 실제 전자 메일 주소를 표시하거나 이 필드를 익명으로 만들 수 있습니다. 이 표에는 Microsoft 365 계정을 사용 하 여 Yammer에 로그인 하거나 single sign-on을 사용 하 여 네트워크에 로그인 한 사용자가 표시 됩니다. <br/> |
|표시 이름  <br/> |사용자의 전체 이름입니다. 실제 전자 메일 주소를 표시하거나 이 필드를 익명으로 만들 수 있습니다.  <br/> |
|사용자 상태  <br/> |활성화, 삭제 또는 일시 중단의 세 가지 값 중 하나입니다. 이러한 보고서에서는 활성, 일시 중지 및 삭제된 사용자의 데이터를 표시합니다. 보류 중인 사용자는 메시지를 게시하거나 읽거나 좋아요를 클릭할 수 없으므로 보류 중인 사용자는 반영하지 않습니다.  <br/> |
|상태 변경 날짜 (UTC)  <br/> |Yammer에서 사용자의 상태가 변경 된 날짜입니다.  <br/> |
|마지막 활동 날짜 (UTC)  <br/> | 사용자가 메시지를 게시 하거나 읽거나 좋아요를 지정한 마지막 날짜입니다.  <br/> |
|올린  <br/> |지정한 기간 동안 사용자가 게시 한 메시지 수입니다. <br/>|
|읽기  <br/> |지정한 기간 동안 사용자가 읽은 대화 수입니다.  <br/> |
|좋아요  <br/> |지정 된 기간 동안 사용자가 좋아요를 지정한 메시지 수입니다.  <br/>|
|할당 된 제품  <br/> |이 사용자에 게 할당 된 제품입니다.|
|||