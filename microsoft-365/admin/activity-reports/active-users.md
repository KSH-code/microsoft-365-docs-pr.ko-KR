---
title: 관리 센터의 Microsoft 365 보고서-활성 사용자
ms.author: pebaum
author: pebaum
manager: scotv
audience: Admin
ms.topic: overview
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_NonTOC
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
- GEA150
ms.assetid: fc1cf1d0-cd84-43fd-adb7-a4c4dfa8112d
description: Microsoft 365 관리 센터에서 Microsoft 365 Reports 대시보드를 사용 하 여 활성 사용자 보고서를 가져와 사용 중인 제품 라이선스의 수를 확인 하는 방법을 알아봅니다.
ms.openlocfilehash: 162e818e96f6301cf0ec31580950be1ae19a0f35
ms.sourcegitcommit: 628f195cbe3c00910f7350d8b09997a675dde989
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/21/2020
ms.locfileid: "48636998"
---
# <a name="microsoft-365-reports-in-the-admin-center---active-users"></a>관리 센터의 Microsoft 365 보고서-활성 사용자

Microsoft 365 **보고서** 대시보드에는 조직의 제품 전체에 대 한 활동 개요가 표시 됩니다. 보고서 대시보드를 통해 개별 제품 수준 보고서의 하위 수준을 표시하여 각 제품 내의 활동에 대한 더 세부화된 정보를 확인할 수 있습니다. [보고서 개요 항목](activity-reports.md)을 확인하세요.
  
예를 들어 **활성 사용자** 보고서를 사용하여 조직의 사용자가 사용 중인 제품 라이선스 수를 파악하고 어떤 사용자가 어떤 제품을 사용 중인지에 대한 정보를 드릴다운할 수 있습니다. 관리자는 이 보고서를 사용하여 충분히 이용되지 않는 제품이나 추가 교육 또는 정보가 필요한 사용자를 확인할 수 있습니다. 
  
> [!NOTE]
> 보고서를 보려면 Microsoft 365 또는 Exchange, SharePoint, 팀 서비스, 팀 통신 또는 비즈니스용 Skype 관리자의 전역 관리자, 전역 독자 또는 보고서 독자 여야 합니다.  

## <a name="how-to-get-to-the-active-users-report"></a>활성 사용자 보고서에 액세스하는 방법

1. 관리 센터에서 **보고서** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">사용 현황</a> 페이지를 참조하세요.

2. 드롭다운에서 **Office 365** \> **활성 사용자** 를 선택 합니다. 

## <a name="interpret-the-active-users-report"></a>활성 사용자 보고서 해석

  
|||
|:-----|:-----|
|1.  <br/> |**활성 사용자** 보고서에서 지난 7일, 30일, 90일 또는 180일간의 추세를 볼 수 있습니다. 그러나 보고서에서 특정 날짜를 볼 경우 테이블 (7)은 현재 날짜 로부터 최대 28 일 동안의 데이터를 표시 합니다 (보고서가 생성 된 날짜 아님).  <br/> |
|2.  <br/> |각 보고서의 데이터는 대개 최근 24 ~ 48 시간까지 포함 됩니다.  <br/> |
|3.  <br/> |**활성 사용자** 차트는 보고 기간의 일일 활성 사용자 수를 제품별로 구분해서 보여 줍니다.  <br/> **서비스** 차트는 활동 유형 및 서비스별 사용자 수를 보여 줍니다.  <br/> |
|4.  <br/> | **활성 사용자** 차트에서 X축은 선택된 보고 기간을 보여 주고 Y축은 라이선스 유형별로 구분된 일일 활성 사용자 수와 라이선스 유형별로 코딩된 색상을 표시합니다.  <br/>  **서비스** 활동 차트에서 X축은 지정된 기간에 사용자에게 허용된 개별 서비스를 표시하고 Y축은 활동 상태별 사용자 수와 활동 상태별로 코딩된 색상입니다.  <br/> |
|5.  <br/> |범례에서 항목을 선택 하 여 차트에 표시 되는 계열을 필터링 할 수 있습니다. 이 선택 항목을 변경해도 눈금 표에 있는 정보가 변경되지는 않습니다.  <br/> |
|6.  <br/> |**내보내기** ![ 데이터를 excel 파일로 내보내기 링크를 선택 하 여 excel .csv 파일에 보고서 데이터를 내보낼 수도 있습니다 ](../../media/816a224b-6ca7-4967-a135-4f6427f64dc8.JPG) . 그러면 모든 사용자의 데이터를 내보내고 향후 분석을 위해 간단하게 정렬 및 필터링을 수행할 수 있습니다. 사용자가 2,000명 미만인 경우 보고서 자체의 표에서 정렬 및 필터링할 수 있습니다. 사용자가 2,000명 이상인 경우 필터링 및 정렬하려면 데이터를 내보내야 합니다.  <br/> |
|7.  <br/> |열 컨트롤 없이 눈금 표에 표시되는 정보를 변경할 수 있습니다.  <br/> 21Vianet에서 운영 하는 구독의 경우 Yammer가 표시 되지 않습니다. <br/> <br/> |
|||

조직의 정책으로 인해 사용자 정보를 식별할 수 있는 보고서를 볼 수 없는 경우 이러한 모든 보고서의 개인 정보 설정을 변경할 수 있습니다. [Microsoft 365 관리 센터의 활동 보고서](activity-reports.md)에서 **사용자 수준의 세부 정보를 숨기는 방법** 섹션을 확인 하세요.  
