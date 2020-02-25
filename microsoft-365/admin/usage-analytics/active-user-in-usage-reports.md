---
title: Microsoft 365 사용 현황 보고서의 활성 사용자
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
ms.topic: reference
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 093a6d0d-890b-489e-9f46-b15687d3fe4f
description: Microsoft 365 사용 현황 분석, 활동 보고서 및 채택 메트릭에 대 한 활성 사용자에 대해 알아봅니다.
ms.openlocfilehash: 0e2f5f5112593c142b4a7829977221c5542adf49
ms.sourcegitcommit: ca2b58ef8f5be24f09e73620b74a1ffcf2d4c290
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/24/2020
ms.locfileid: "42247279"
---
# <a name="active-user-in-microsoft-365-usage-reports"></a>Microsoft 365 사용 현황 보고서의 활성 사용자

## <a name="active-user-in-usage-reports"></a>사용 현황 보고서 내 활성 사용자

[Microsoft 365 사용 분석과](usage-analytics.md) [관리 센터의 활동 보고서](../activity-reports/activity-reports.md) 에 대 한 microsoft 365 제품의 활성 사용자는 다음과 같이 정의 됩니다. 
  
|**제품**|**활성 사용자 정의**|**노트**|
|:-----|:-----|:-----|
|Exchange Online  <br/> |전자 메일을 읽거나 보내는 모든 사용자입니다.  <br/> |표시된 일정 정보가 없습니다. 이 기능은 향후 업데이트에 추가됩니다.  <br/> |
|SharePoint Online  <br/> |내부적 또는 외부적으로 파일을 만들고, 수정하고, 보고, 삭제하고, 공유하거나 사이트에서 클라이언트와 동기화하는 작업을 수행하거나 사이트에서 페이지를 조회한 사용자입니다.  <br/> |Microsoft 365 Usage Analytics 서식 파일에서 SharePoint Online에 대 한 활성 사용자 메트릭에는 SharePoint 팀 사이트 또는 그룹 사이트에 대해 파일 활동을 수행한 사용자만 반영 됩니다. 서식 파일 앱이 정의를 관리 센터의 사용 현황 보고서에 있는 것과 동일 하 게 동기화 하도록 업데이트 됩니다.  <br/> |
|비즈니스용 OneDrive  <br/> |내부적 또는 외부적으로 파일을 만들고, 수정하고, 보고, 삭제하고, 공유하거나 클라이언트와 동기화하는 작업을 수행한 사용자입니다.  <br/> ||
|Yammer  <br/> |Yammer에서 메시지를 읽거나 게시했거나 좋아하는 모든 사용자입니다.  <br/> ||
|비즈니스용 Skype  <br/> |피어 투 피어 세션(인스턴트 메시징, 음성 및 화상 통화, 응용 프로그램 공유 및 파일 전송 포함)에 참여했거나 회의를 구성했거나 회의에 참여한 모든 사용자입니다.  <br/> ||
|Office  <br/> |하나 이상의 장치에서 Microsoft 365 Pro Plus, Visio Pro 또는 Project Pro 구독을 정품 인증 한 모든 사용자입니다.  <br/> ||
|Microsoft 365 그룹  <br/> |(메시지가 그룹에 전송된 경우) 사서함 활동이 발생한 그룹 구성원  <br/> |그룹 사이트 파일 활동 및 Yammer 그룹 활동 (그룹 사이트의 파일 활동 및 그룹과 연결 된 Yammer 그룹에 게시 되는 메시지)을 사용 하 여이 정의를 향상 시킬 수 있습니다. 이 데이터는 현재 Microsoft 365 Usage Analytics 서식 파일 앱에서 사용할 수 없습니다.  <br/> |
|Microsoft Teams  <br/> |채팅 메시지, 비공개 채팅 메시지, 통화, 모임 또는 기타 활동에 참여 한 모든 사용자입니다. 기타 활동은 사용자가 포함 하는 기타 팀 활동의 수로 정의 되며, 이러한 작업은 원하는 메시지, 앱, 파일 작업, 검색, 팀 및 채널 팔 로우 및 favoriting에 제한 됩니다.  <br/> ||
   
## <a name="adoption-metrics"></a>채택 메트릭

[Microsoft 365 사용 현황 분석](usage-analytics.md) 에서는 활성 사용자와 관련 된 추가 도입 메트릭을 포함 하 여 시간의 경과에 따른 제품 채택을 보여 줍니다. 이러한 메트릭은 선택한 제품 및 월에 대해 유효 하며 다음과 같이 정의 됩니다. 
  
|**192.168.1.0**|**설명**|
|:-----|:-----|
|EnabledUsers  <br/> |해당 월에 제품을 사용할 수 있는 사용자 수입니다.  <br/> |
|Activeusers 작업  <br/> |해당 월의 활성 상태인 사용자 수입니다.  <br/> |
|MoMReturningUsers  <br/> |이전 달에도 활성화 되었던 달의 활성 사용자 수입니다.  <br/> |
|FirstTimeUsers  <br/> |이전에 서비스를 사용 하지 않았던 달의 활성 사용자 수입니다.  <br/> |
|CumulativeActiveUsers  <br/> |이전 달과 월 단위에서 활성화 된 사용자 수입니다.  <br/> |
|ActiveUsers (%)  <br/> |해당 월에 사용 하도록 설정 된 사용자 수에 비해 사용자의 백분율이 가장 가까운 달로 반올림 됩니다.  <br/> |
|MoMReturningUsers (%)  <br/> |이전 달에도 활성 상태인 활성 사용자 수에 비해 활성 상태의 가장 가까운 달로 반올림 된 사용자의 백분율입니다.  <br/> |
   
MoMReturningUsers, FirstTimeUsers, &amp; CumulativeActiveUsers는 Microsoft 팀을 포함 하 여 첫 번째 2018 1 월부터 다시 설정 되었습니다.
  
