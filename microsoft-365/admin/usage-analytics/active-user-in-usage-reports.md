---
title: 사용 현황 Microsoft 365 활성 사용자
ms.author: efrene
author: efrene
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 093a6d0d-890b-489e-9f46-b15687d3fe4f
description: 사용 현황 분석, 활동 보고서 Microsoft 365 채택 메트릭의 활성 사용자에 대해 자세히 알아보십시오.
ms.openlocfilehash: ddbfc487089aed89c8dde8fe60b25e13dc94d4d0
ms.sourcegitcommit: aebcdbef52e42f37492a7f780b8b9b2bc0998d5c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/24/2021
ms.locfileid: "59776683"
---
# <a name="active-user-in-microsoft-365-usage-reports"></a>사용 현황 Microsoft 365 활성 사용자

## <a name="active-user-in-usage-reports"></a>사용 현황 보고서의 활성 사용자

관리 센터의 Microsoft 365 분석 [](usage-analytics.md) 및 Microsoft 365 보고서에 대한 [](../activity-reports/activity-reports.md) 활성 제품 사용자는 다음과 같이 정의됩니다. 
  
|**제품**|**활성 사용자 정의**|**노트**|
|:-----|:-----|:-----|
|Exchange Online  <br/> |다음 작업을 수행한 모든 사용자: 읽음으로 표시, 메시지 보내기, 약속 만들기, 모임 요청 보내기, 모임 요청 수락(미정) 또는 거절, 모임 취소  <br/> |표시된 일정 정보가 없습니다. 이 기능은 향후 업데이트에 추가됩니다.  <br/> |
|SharePoint Online  <br/> |내부적 또는 외부적으로 파일을 만들고, 수정하고, 보고, 삭제하고, 공유하거나 사이트에서 클라이언트와 동기화하는 작업을 수행하거나 사이트에서 페이지를 조회한 사용자입니다.  <br/> |Microsoft 365 사용 현황 분석 템플릿 앱에서 SharePoint Online에 대한 활성 사용자 메트릭은 SharePoint 팀 사이트 또는 그룹 사이트에 대해 파일 활동을 한 사용자만 반영합니다. 템플릿 앱은 관리 센터의 사용 현황 보고서에서 정의와 동일하게 동기화되도록 업데이트됩니다.  <br/> |
|비즈니스용 OneDrive  <br/> |내부적 또는 외부적으로 파일을 만들고, 수정하고, 보고, 삭제하고, 공유하거나 클라이언트와 동기화하는 작업을 수행한 사용자입니다.  <br/> ||
|Yammer  <br/> |Yammer에서 메시지를 읽거나 게시했거나 좋아하는 모든 사용자입니다.  <br/> ||
|비즈니스용 Skype  <br/> |피어 투 피어 세션(인스턴트 메시징, 음성 및 화상 통화, 응용 프로그램 공유 및 파일 전송 포함)에 참여했거나 회의를 구성했거나 회의에 참여한 모든 사용자입니다.  <br/> ||
|Office  <br/> |하나 이상의 장치에서 Microsoft 365 Pro Plus, Visio Pro Project Pro 또는 구독을 활성화한 모든 사용자입니다.  <br/> ||
|Microsoft 365 그룹  <br/> |(메시지가 그룹에 전송된 경우) 사서함 활동이 발생한 그룹 구성원  <br/> |이 정의는 그룹 사이트 파일 활동 및 Yammer 활동(그룹 사이트의 파일 활동 및 그룹과 연결된 Yammer 그룹에 게시된 메시지)을 통해 향상됩니다. 현재 사용 현황 분석 템플릿 앱에서는 이 Microsoft 365 사용할 수 없습니다.  <br/> |
|Microsoft Teams  <br/> |채팅 메시지, 비공개 채팅 메시지, 통화, 모임 또는 기타 활동에 참여한 모든 사용자입니다. 다른 활동은 사용자가 메시지, 앱에 대한 선호, 파일 작업, 검색, 팀 및 채널을 따라가고 선호하는 작업을 포함하며 이에 국한되지 않는 사용자가 다른 팀 활동의 수로 정의합니다.  <br/> ||
   
## <a name="adoption-metrics"></a>채택 메트릭

Microsoft 365 사용 [현황 분석에는](usage-analytics.md) 시간이 지날 때 제품의 채택을 보여 주기 위해 활성 사용자와 관련된 추가 채택 메트릭이 포함되어 있습니다. 이러한 메트릭은 선택한 월, 연도 및 제품에 유효하며 다음과 같이 정의됩니다. 
  
|**메트릭**|**설명**|
|:-----|:-----|
|EnabledUsers  <br/> |해당 달에 제품을 사용할 수 있는 사용자 수입니다.  <br/> |
|ActiveUsers  <br/> |해당 달에 활성 상태인 사용자 수입니다.  <br/> |
|MoMReturningUsers  <br/> |이전 달에 활성 상태인 달의 사용자 수입니다.  <br/> |
|FirstTimeUsers  <br/> |이전 서비스를 사용한 적이 없는 달의 활성 사용자 수입니다.  <br/> |
|CumulativeActiveUsers  <br/> |이전 달을 더한 달의 활성 사용자 수입니다.  <br/> |
|ActiveUsers(%)  <br/> |해당 월에 활성화된 사용자 수와 비교하여 가장 가까운 10분의 1로 반올라된 사용자 비율입니다.  <br/> |
|MoMReturningUsers(%)  <br/> |활성 사용자 수와 비교하여 이전 달에 활성 상태인 가장 가까운 10분의 1로 반올라된 사용자 비율입니다.  <br/> |
   
MoMReturningUsers, FirstTimeUsers, &amp; CumulativeActiveUsers는 2018년 1월 1일을 시작으로 Microsoft Teams.
  
