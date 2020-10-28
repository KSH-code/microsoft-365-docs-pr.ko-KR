---
title: 관리 센터의 Microsoft 365 보고서-Yammer 장치 사용 현황 보고서
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
description: Yammer 장치 사용 보고서를 다운로드 하 여 사용자가 Yammer를 사용 하는 장치에 대해 알 수 있습니다.
ms.openlocfilehash: fae76e9ef769248217140c059004efc7ad330928
ms.sourcegitcommit: c51de5e1a4cb9c4a7a9854a4226b32453d9e73e0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/28/2020
ms.locfileid: "48779388"
---
# <a name="microsoft-365-reports-in-the-admin-center---yammer-device-usage-report"></a>관리 센터의 Microsoft 365 보고서-Yammer 장치 사용 현황 보고서

Microsoft 365 **보고서** 대시보드에는 조직의 제품 전체에 대 한 활동 개요가 표시 됩니다. 보고서 대시보드를 통해 개별 제품 수준 보고서의 하위 수준을 표시하여 각 제품 내의 활동에 대한 더 세부화된 정보를 확인할 수 있습니다. [보고서 개요 항목](activity-reports.md)을 확인하세요.
  
Yammer 장치 사용 현황 보고서는 사용자가 Yammer를 사용하는 장치에 대한 정보를 제공합니다. 장치 유형별로 일일 사용자 수 및 장치 유형별로 사용자 수를 볼 수 있습니다. 선택한 기간에 대해 이 두 정보를 모두 볼 수 있습니다. 사용자당 세부 정보도 볼 수 있습니다.
  
> [!NOTE]
> 보고서를 보려면 Microsoft 365 또는 Exchange, SharePoint, 팀 서비스, 팀 통신 또는 비즈니스용 Skype 관리자의 전역 관리자, 전역 독자 또는 보고서 독자 여야 합니다.  
 
## <a name="how-do-i-get-to-the-yammer-device-usage-report"></a>Yammer 장치 사용 현황 보고서에 액세스하려면 어떻게 하나요?

1. 관리 센터에서 **보고서** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">사용 현황</a> 페이지를 참조하세요. 
2. 대시보드 홈 페이지에서 Yammer 카드의 **자세히 보기** 단추를 클릭 합니다.
  
## <a name="interpret-the-yammer-device-usage-report"></a>Yammer 장치 사용 현황 보고서 해석

**장치 사용** 탭을 선택 하 여 OneDrive 보고서에서 사용 현황을 볼 수 있습니다.<br/>![Microsoft 365 reports-Microsoft Yammer 장치 사용 현황 보고서](../../media/e21af4c0-0ad2-4485-8ab1-2f82d7dfa90e.png)

**열 선택을** 선택 하 여 보고서에서 열을 추가 하거나 제거 합니다.  <br/> ![Yammer 장치 사용 현황 보고서-열 선택](../../media/fc1fc8db-e197-4878-85c7-7ba0d67b9379.png)

**내보내기** 링크를 선택 하 여 보고서 데이터를 Excel .csv 파일로 내보낼 수도 있습니다. 그러면 모든 사용자의 데이터를 내보내고 향후 분석을 위해 간단하게 정렬 및 필터링을 수행할 수 있습니다. 사용자가 2,000명 미만인 경우 보고서 자체의 표에서 정렬 및 필터링할 수 있습니다. 사용자가 2,000명 이상인 경우 필터링 및 정렬하려면 데이터를 내보내야 합니다. 
  
|항목|설명|
|:-----|:-----|
|**메트릭**|**정의**|
|사용자 이름  <br/> |사용자의 전자 메일 주소입니다. 실제 전자 메일 주소를 표시하거나 이 필드를 익명으로 만들 수 있습니다. 이 표에는 Microsoft 365 계정을 사용 하 여 Yammer에 로그인 하거나 single sign-on을 사용 하 여 네트워크에 로그인 한 사용자가 표시 됩니다. <br/> |
|표시 이름  <br/> |사용자의 전체 이름입니다. 실제 전자 메일 주소를 표시하거나 이 필드를 익명으로 만들 수 있습니다.  <br/> |
|사용자 상태  <br/> |활성, 삭제 됨 또는 일시 중단의 세 가지 값 중 하나입니다. 이러한 보고서에서는 활성, 일시 중지 및 삭제된 사용자의 데이터를 표시합니다. 보류 중인 사용자는 메시지를 게시하거나 읽거나 좋아요를 클릭할 수 없으므로 보류 중인 사용자는 반영하지 않습니다.   <br/> |
|상태 변경 날짜 (UTC)  <br/> |Yammer에서 사용자의 상태가 변경 된 날짜입니다.  <br/> |
|마지막 활동 날짜 (UTC)  <br/> |사용자가 Yammer 활동에 참여 한 마지막 날짜 (UTC)입니다.  <br/> |
|웹  <br/> |사용자가 웹에서 Yammer를 사용 했는지 여부를 나타냅니다.  <br/> |
|Windows phone  <br/> | 사용자가 Windows phone에서 Yammer를 사용 하는지를 나타냅니다.  <br/> |
|Android 휴대폰  <br/> |사용자가 Android 휴대폰에서 Yammer를 사용 했는지 여부를 나타냅니다. <br/>|
|iphone <br/> | 사용자가 iPhone에서 Yammer를 사용 했는지 여부를 나타냅니다.  <br/> |
|용  <br/> |사용자가 iPad에서 Yammer를 사용 했는지 여부를 나타냅니다. <br/>|
|other  <br/> |사용자가 이전에 나열 되지 않은 다른 장치에서 Yammer를 사용 했는지 여부를 나타냅니다. <br/>|
|||