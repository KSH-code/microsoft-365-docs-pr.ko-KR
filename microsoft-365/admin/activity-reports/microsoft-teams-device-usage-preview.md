---
title: 관리 센터의 Microsoft 365 보고서 - Microsoft Teams 장치 사용 현황
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
ROBOTS: NOINDEX, NOFOLLOW
search.appverid:
- BCS160
- MST160
- MET150
- MOE150
description: Microsoft 365 보고서에서 Microsoft Teams 앱 사용 현황 보고서를 확인하여 조직에서 사용되는 Microsoft Teams 앱에 대한 인사이트를 얻습니다.
ms.openlocfilehash: 096954ad246f3b10369dfbf683d04b6c81950b5e
ms.sourcegitcommit: 53acc851abf68e2272e75df0856c0e16b0c7e48d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/02/2021
ms.locfileid: "51579641"
---
# <a name="microsoft-365-reports-in-the-admin-center---microsoft-teams-device-usage"></a>관리 센터의 Microsoft 365 보고서 - Microsoft Teams 장치 사용 현황

Microsoft 365 **보고서** 대시보드에는 조직의 제품 전체에 대한 활동 개요가 표시됩니다. 보고서 대시보드를 통해 개별 제품 수준 보고서의 하위 수준을 표시하여 각 제품 내의 활동에 대한 더 세부화된 정보를 확인할 수 있습니다. [보고서 개요 항목](activity-reports.md)을 확인하세요. Microsoft Teams 앱 사용 보고서에서는 조직에서 사용되는 Microsoft Teams 앱에 대한 정보를 확인할 수 있습니다.
  
> [!NOTE]
> Microsoft 365의 전역 관리자, 전역 읽기 권한자 또는 보고서 읽기 권한자 또는 Exchange, SharePoint, Teams 서비스, Teams Communications 또는 비즈니스용 Skype 관리자인 경우 보고서를 볼 수 있어야 합니다.  
 
## <a name="how-to-get-to-the-microsoft-teams-app-usage-report"></a>Microsoft Teams 앱 사용 보고서에 액세스하는 방법

1. 관리 센터에서 **보고서** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">사용 현황</a> 페이지를 참조하세요. 
2. 대시보드 홈 페이지 Microsoft Teams  활동 카드에서 더 보기 단추를 클릭합니다.
  
## <a name="interpret-the-microsoft-teams-app-usage-report"></a>Microsoft Teams 앱 사용 보고서 해석

장치 사용 탭을 선택하여 Teams 보고서에서 장치 사용을 볼 **수** 있습니다.<br/>![Microsoft 365 보고서 - Microsoft Teams 장치 사용 현황.](../../media/e46c7f7c-8371-4a20-ae82-b20df64b0205.png)

열 **선택을 선택하여** 보고서에서 열을 추가하거나 제거합니다.  <br/> ![Teams 사용자 장치 보고서 - 열 선택](../../media/3358d5d9-931b-4d30-931f-450b2f5717da.png)

내보내기 링크를 선택하여 보고서 데이터를 Excel .csv 파일로 내보낼 **수** 있습니다. 그러면 모든 사용자의 데이터를 내보내고 향후 분석을 위해 간단하게 정렬 및 필터링을 수행할 수 있습니다. 사용자가 2,000명 미만인 경우 보고서 자체의 표에서 정렬 및 필터링할 수 있습니다. 사용자가 2,000명 이상인 경우 필터링 및 정렬하려면 데이터를 내보내야 합니다. 

**Microsoft Teams 장치 사용** 보고서에서 지난 7일, 30일, 90일 또는 180일간의 추세를 볼 수 있습니다. 그러나 보고서에서 특정 날짜를 선택하면 표(7)에 현재 날짜로부터 최대 28일간의 데이터가 표시됩니다(보고서가 생성된 날짜가 아 아지 않습니다).
  
|항목|설명|
|:-----|:-----|
|**메트릭**|**정의**|
|사용자 이름  <br/> |사용자의 표시 이름입니다.  <br/> |
|Windows  <br/> |사용자가 Windows 기반 컴퓨터의 Teams 데스크톱 클라이언트에서 활성 상태인 경우 선택됩니다.  <br/> |
|Mac  <br/> |사용자가 macOS 컴퓨터의 Teams 데스크톱 클라이언트에서 활성 상태인 경우 선택됩니다.  <br/> |
|iOS  <br/> |사용자가 iOS용 Teams 모바일 클라이언트에서 활성 상태인 경우 선택됩니다.  <br/> |
|Android 휴대폰  <br/> | 사용자가 Android용 Teams 모바일 클라이언트에서 활성 상태인 경우 선택됩니다.  <br/> |
|Chrome OS  <br/> |사용자가 ChromeOS 컴퓨터의 Teams 데스크톱 클라이언트에서 활성 상태인 경우 선택됩니다.|
|Linux  <br/> | 사용자가 Linux 컴퓨터의 Teams 데스크톱 클라이언트에서 활성 상태인 경우 선택됩니다.  <br/> |
|웹  <br/> |사용자가 디바이스의 Teams 웹 클라이언트에서 활성 상태인 경우 선택됩니다.|
|마지막 활동 날짜(UTC)  <br/> |사용자가 Teams 활동에 참가한 마지막 날짜(UTC)입니다.  <br/> |
|사용이 허가됩니다.|사용자에게 Teams를 사용할 수 있는 라이선스가 있는 경우 선택됩니다.|
|||