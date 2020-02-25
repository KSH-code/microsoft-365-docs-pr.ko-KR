---
title: 관리 센터의 Office 365 보고서-Yammer 그룹 활동 보고서
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
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 94dd92ec-ea73-43c6-b51f-2a11fd78aa31
description: Yammer 그룹 활동 보고서를 통해 조직에서 만들고 사용 하는 Yammer 그룹의 수와 해당 활동을 파악할 수 있습니다.
ms.openlocfilehash: 436387a7476a62293107e1a22d6fc15287d4faf0
ms.sourcegitcommit: ca2b58ef8f5be24f09e73620b74a1ffcf2d4c290
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/24/2020
ms.locfileid: "42245809"
---
# <a name="office-365-reports-in-the-admin-center---yammer-groups-activity-report"></a>관리 센터의 Office 365 보고서-Yammer 그룹 활동 보고서

Office 365 **보고서** 대시보드에는 조직의 제품 전체에 대 한 활동 개요가 표시 됩니다. 보고서 대시보드를 통해 개별 제품 수준 보고서의 하위 수준을 표시하여 각 제품 내의 활동에 대한 더 세부화된 정보를 확인할 수 있습니다. [보고서 개요 항목](activity-reports.md)을 확인하세요. Yammer 그룹 활동 보고서에서는 조직의 Yammer 그룹 활동을 파악하고, 만들어지고 사용되는 Yammer 그룹의 수를 확인할 수 있습니다.
  
> [!NOTE]
> 보고서를 보려면 Microsoft 365 또는 Exchange, SharePoint 또는 비즈니스용 Skype 관리자의 전역 관리자, 전역 독자 또는 보고서 독자 여야 합니다. 

## <a name="how-to-get-to-the-yammer-groups-activity-report"></a>Yammer 그룹 활동 보고서에 액세스하는 방법

1. 관리 센터에서 **보고서** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">사용 현황</a> 페이지를 참조하세요.

    
2. **보고서 선택** 드롭다운에서 **Yammer** \> **그룹 활동**을 선택 합니다.
  
## <a name="interpret-the-yammer-groups-activity-report"></a>Yammer 그룹 활동 보고서 해석

**그룹** 및 **활동** 차트를 확인하여 Yammer 그룹 활동을 볼 수 있습니다.<br/>![Yammer groups activity chart](../media/4ba4ea03-2f74-4d86-8c63-2b18477c9769.png)
  
|||
|:-----|:-----|
|1.  <br/> |**Yammer 그룹 활동** 보고서에서 지난 7일, 30일, 90일 또는 180일간의 추세를 볼 수 있습니다. 그러나 보고서에서 특정 날짜를 선택 하는 경우 테이블 (7)은 현재 날짜 로부터 최대 28 일 동안의 데이터를 표시 합니다 (보고서가 생성 된 날짜 아님).  <br/> |
|2.  <br/> |각 보고서의 데이터는 대개 최근 24 ~ 48 시간까지 포함 됩니다. <br/> |
|3.  <br/> |**그룹** 보기에는 존재하는 총 그룹 수와 수행된 그룹 대화 활동 수가 표시됩니다.  <br/> |
|4.  <br/> |**활동** 보기에는 그룹에서 게시하고, 읽고, 좋아요를 클릭한 Yammer 메시지 수가 표시됩니다.  <br/> |
|5.  <br/> | **그룹** 차트에서 Y축은 전체 또는 활성 그룹 수입니다.  <br/>  **활동** 차트에서 Y축은 Yammer 그룹에 대해 지정된 활동 수입니다.  <br/>  세 개의 모든 차트에서 X축은 특정 보고서에 대해 선택된 날짜 범위입니다.  <br/> |
|6.  <br/> |범례에서 항목을 선택 하 여 차트에 표시 되는 계열을 필터링 할 수 있습니다. 예를 들어 **그룹** 차트에서 **요약** 또는 **활성**![합계 및 활성 아이콘](../media/8eebd496-5955-4419-8d53-5f3ba1ad1c88.png) 을 선택 하 여 각 항목에 관련 된 정보만 표시 합니다.   이 선택 항목을 변경해도 눈금 표에 있는 정보가 변경되지는 않습니다.  <br/> |
|7.  <br/> | 표시되는 그룹 목록은 가장 긴 보고 기간(180일)에 존재한(삭제되지 않은) 모든 그룹 집합으로 결정됩니다. 활동 수(받은 메시지)는 날짜 선택에 따라 달라집니다.  <br/> 참고: 열을 추가할 때까지 아래 목록의 항목 중 일부가 표시 되지 않을 수 있습니다.<br/>**그룹 이름** 은 그룹의 이름입니다.  <br/> **그룹 관리자** 는 그룹 관리자 또는 소유자의 이름입니다.  <br/> **삭제됨** 은 삭제된 Yammer 그룹 수입니다. 그룹이 삭제되었지만 보고 기간 중 활동이 있는 경우 이 플래그가 true로 설정되어 표에 표시됩니다.  <br/> **종류** 는 그룹의 종류(공개 또는 비공개)입니다.  <br/> **연결 대상 office 365** Yammer 그룹이 Office 365 그룹 이기도 한지를 나타냅니다.  <br/> **마지막 활동 날짜** 는 그룹에서 메시지를 읽거나 게시 하거나 좋아요를 수행한 최근 날짜입니다.  <br/> **구성원** 은 그룹의 구성원 수입니다.  <br/> **게시됨** 은 보고 기간에 Yammer 그룹에 게시된 메시지 수입니다.  <br/> **읽음** 은 보고 기간에 Yammer 그룹에서 읽은 메시지의 수입니다.  <br/> **좋아함** 은 보고 기간에 Yammer 그룹에서 좋아요를 클릭한 메시지 수입니다.  <br/>  조직의 정책으로 인해 사용자 정보를 식별할 수 있는 보고서를 볼 수 없는 경우 이러한 모든 보고서의 개인 정보 설정을 변경할 수 있습니다. [Microsoft 365 관리 센터의 활동 보고서](activity-reports.md)에서 **사용자 수준의 세부 정보를 숨기는 방법** 섹션을 확인 하세요.  <br/> |
|8.  <br/> |**열** 을 선택 하 여 보고서에서 열을 추가 하거나 제거 합니다.  <br/> ![Yammer groups activity - choose columns](../media/31bd549b-363d-4888-a45d-7af6fedb3588.png)|
|9.  <br/> |**내보내기** 링크를 선택 하 여 Excel .csv 파일에 보고서 데이터를 내보낼 수도 있습니다. 그러면 모든 사용자의 데이터를 내보내고 향후 분석을 위해 간단하게 정렬 및 필터링을 수행할 수 있습니다. 사용자가 2,000명 미만인 경우 보고서 자체의 표에서 정렬 및 필터링할 수 있습니다. 사용자가 2,000명 이상인 경우 필터링 및 정렬하려면 데이터를 내보내야 합니다.  <br/> |
|||
   

