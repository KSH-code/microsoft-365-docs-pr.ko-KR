---
title: Microsoft 365 관리 센터의 보고서 - Dynamics 365 고객 음성 활동
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
description: Microsoft 365 보고서 대시보드를 사용하여 Microsoft Dynamics 365 고객 음성 활동 보고서를 Microsoft 365 관리 센터.
ms.openlocfilehash: 2eedcf65e95d2bf85dbf156b4e1ac2d540acdf46
ms.sourcegitcommit: 3140e2866de36d57a27d27f70d47e8167c9cc907
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/23/2021
ms.locfileid: "60553427"
---
# <a name="microsoft-365-reports-in-the-admin-center---dynamics-365-customer-voice-activity"></a>Microsoft 365 관리 센터의 보고서 - Dynamics 365 고객 음성 활동

Microsoft 365 **보고서** 대시보드에는 조직의 제품 전체에 대한 활동 개요가 표시됩니다. 보고서 대시보드를 통해 개별 제품 수준 보고서의 하위 수준을 표시하여 각 제품 내의 활동에 대한 더 세부화된 정보를 확인할 수 있습니다. [보고서 개요 항목](activity-reports.md)을 확인하세요.
  
예를 들어 Dynamics 365 Customer Voice와의 상호 작용을 보고 Microsoft Dynamics 365 Customer Voice를 사용하기 위해 라이선스가 부여된 모든 사용자의 활동을 이해할 수 있습니다. 또한 사용자가 응답한 설문 조사를 Pro 수를 보고 Pro 진행되는 공동 작업 수준을 파악하는 데 도움이 됩니다. 
  
## <a name="how-to-get-to-the-dynamics-365-customer-voice-activity-report"></a>Dynamics 365 고객 음성 활동 보고서에 도착하는 방법

1. 관리 센터에서 **보고서** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">사용 현황</a> 페이지를 참조하세요. 
2. 대시보드 홈페이지에서 Dynamics 365 고객 음성 카드의 더 보기 단추를 클릭합니다. 
  
## <a name="interpret-the-dynamics-365-customer-voice-activity-report"></a>Dynamics 365 고객 음성 활동 보고서 해석

활동 탭을 선택하여 Dynamics 365 고객 음성 보고서에서 활동을 볼 **수** 있습니다.<br/>![Microsoft 365 보고서 - Microsoft Dynamics 365 고객 음성 활동 보고서.](../../media/a7e57d18-1ac8-4d4b-bd70-83361505dc3e.png)

열 **선택을 선택하여** 보고서에서 열을 추가하거나 제거합니다.  <br/> ![Dynamics 365 고객 음성 활동 보고서 - 열을 선택 합니다.](../../media/5ab66f4b-32eb-4c9b-9683-1157ae9e2c0a.png)

내보내기 링크를 선택하여 보고서 데이터를 Excel .csv 내보낼 **수** 있습니다. 그러면 모든 사용자의 데이터를 내보내고 향후 분석을 위해 간단하게 정렬 및 필터링을 수행할 수 있습니다. 사용자가 2,000명 미만인 경우 보고서 자체의 표에서 정렬 및 필터링할 수 있습니다. 사용자가 2,000명 이상인 경우 필터링 및 정렬하려면 데이터를 내보내야 합니다. 

**Dynamics 365 고객** 음성 활동 보고서에서 지난 7일, 30일, 90일 또는 180일간의 추세를 볼 수 있습니다. 그러나 보고서에서 특정 날짜를 선택하면 보고서가 생성된 날짜가 아니라 현재 날짜로부터 최대 28일간의 데이터가 표에 표시됩니다.
  
|항목|설명|
|:-----|:-----|
|**메트릭**|**정의**|
|사용자 이름  <br/> |Microsoft Forms에서 활동을 수행한 사용자의 전자 메일 주소입니다.  <br/> |
|마지막 활동 날짜(UTC)  <br/> |선택한 날짜 범위에 대해 사용자가 양식 활동을 수행한 가장 최근 날짜입니다. 특정 날짜에 발생한 활동을 보려면 차트에서 직접 날짜를 선택합니다.<br/>이렇게 하면 해당 특정 일자에 활동을 수행한 사용자에 대한 파일 활동 데이터만 표시하도록 테이블이 필터링됩니다.  <br/> |
|생성된 설문 조사 수  <br/> |사용자가 만든 설문 조사 수입니다.   <br/> |
|설문 조사 응답 수  <br/> |설문 조사를 배포한 응답자로부터의 응답 수입니다.|
|||