---
title: 관리 센터의 Microsoft 365 보고서 - Microsoft 365 그룹
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
search.appverid:
- BCS160
- MET150
- MOE150
- GEA150
ms.assetid: a27f1a99-3557-4f85-9560-a28e3d822a40
description: Microsoft 365 그룹 보고서를 다운로드하여 그룹 및 그룹 활동에 대해 알 수 있습니다.
ms.openlocfilehash: 4a89f09f89e399905d0cb6927eca76c1242dfc62
ms.sourcegitcommit: 039205fdaaa2a233ff7e95cd91bace474b84b68c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/09/2020
ms.locfileid: "49611946"
---
# <a name="microsoft-365-reports-in-the-admin-center---microsoft-365-groups"></a>관리 센터의 Microsoft 365 보고서 - Microsoft 365 그룹

Microsoft 365 **보고서** 대시보드에는 조직의 제품 전체에 대한 활동 개요가 표시됩니다. 보고서 대시보드를 통해 개별 제품 수준 보고서의 하위 수준을 표시하여 각 제품 내의 활동에 대한 더 세부화된 정보를 확인할 수 있습니다. [보고서 개요 항목](activity-reports.md)을 확인하세요. Microsoft 365 그룹 보고서에서 조직의 그룹 활동에 대한 정보를 얻고 만들어지고 사용되는 그룹 수를 볼 수 있습니다.
  
> [!NOTE]
> Microsoft 365의 전역 관리자, 전역 읽기 권한자 또는 보고서 읽기 권한자 또는 Exchange, SharePoint, Teams 서비스, Teams 커뮤니케이션 또는 비즈니스용 Skype 관리자인 경우 보고서를 볼 수 있어야 합니다.  
  
## <a name="how-to-get-to-the-groups-report"></a>그룹 보고서에 도착하는 방법

1. 관리 센터에서 **보고서** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">사용 현황</a> 페이지를 참조하세요. 
2. 대시보드 홈 페이지에서 활성 사용자  - Microsoft 365 앱 또는 활성 사용자 - Microsoft 365 서비스 카드의 추가 보기 단추를 클릭하여 Office 365 보고서 페이지로 이동합니다.
  
## <a name="interpret-the-groups-report"></a>그룹 보고서 해석

그룹 활동 탭을 선택하여 Office 365 보고서에서 정품 인증을 **볼 수** 있습니다.<br/>![Microsoft 365 보고서 - Microsoft Office 365 그룹 활동.](../../media/ab90e30b-8938-4110-ab3d-ee472a4cfe21.png)

열 **선택을 선택하여** 보고서에서 열을 추가하거나 제거합니다.  <br/> ![Office 365 그룹 활동 보고서 - 열 선택](../../media/1600556a-f5f1-47d9-b325-cd77c78f4004.png)

내보내기 링크를 선택하여 보고서 데이터를 Excel .csv 파일로 내보낼 **수** 있습니다. 그러면 모든 사용자의 데이터를 내보내고 향후 분석을 위해 간단하게 정렬 및 필터링을 수행할 수 있습니다. 사용자가 2,000명 미만인 경우 보고서 자체의 표에서 정렬 및 필터링할 수 있습니다. 사용자가 2,000명 이상인 경우 필터링 및 정렬하려면 데이터를 내보내야 합니다. 

|항목|설명|
|:-----|:-----|
|**메트릭**|**정의**|
|그룹 이름  <br/> |그룹의 이름입니다.  <br/> |
|삭제됨  <br/> |삭제된 그룹 수입니다. 그룹이 삭제되었지만 보고 기간 중 활동이 있는 경우 이 플래그가 true로 설정되어 표에 표시됩니다.  <br/> |
|그룹 소유자  <br/> |그룹 소유자의 이름입니다.  <br/> |
|마지막 활동 날짜(UTC)  <br/> |그룹에서 메시지를 받은 가장 최신 날짜입니다. 전자 메일 대화, Yammer 또는 사이트에서 활동이 발생한 최근 날짜입니다.  <br/> |
|유형  <br/> |그룹 유형입니다. 비공개 또는 공개 그룹일 수 있습니다.  <br/> |
|Exchange에서 받은 전자 메일  <br/> |그룹에서 받은 메시지 수입니다.|
|Exchange의 전자 메일(합계)  <br/> |그룹 사서함의 총 항목 수입니다.  <br/> |
|Exchange에 사용되는 사서함 저장소(MB)  <br/> |그룹의 사서함에서 사용하는 저장소입니다. <br/>|
|SharePoint 파일(합계)  <br/> |SharePoint 그룹 사이트에 저장된 파일 수입니다.  <br/> |
|SharePoint 파일(활성)  <br/> |보고 기간 동안 SharePoint 그룹 사이트의 파일 수(보거나 수정, 동기화, 내부 또는 외부적으로 공유)한 파일 수입니다.  <br/> |
|SharePoint에 사용되는 총 사이트 저장소(MB)  <br/> |보고 기간 동안 사용된 저장소의 양(MB)입니다.  <br/> |
|메시지의 Yammer(게시)  <br/> |보고 기간 동안 Yammer 그룹에 게시된 메시지 수입니다.  <br/> |
|메시지의 Yammer(읽기)  <br/> |보고 기간 동안 Yammer 그룹에서 읽은 대화 수입니다.  <br/> |
|메시지의 Yammer(liked)  <br/> |보고 기간 동안 Yammer 그룹에서 좋아하는 메시지 수입니다.  <br/> |
|구성원  <br/> |그룹의 구성원 수입니다.  <br/> |
|외부 구성원 |그룹의 외부 사용자 수입니다.|
|||