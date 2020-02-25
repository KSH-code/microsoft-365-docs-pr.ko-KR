---
title: Microsoft 365 사용 현황 분석 데이터 모델
f1.keywords:
- NOCSH
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
- SPO_Content
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 08c5307c-4a6b-4761-8410-a6c96725760f
description: '사용 현황 분석을 통해 API에 연결 하 고 다양 한 Microsoft 365 서비스의 사용에 대 한 월별 추세를 제공 하는 방법을 알아봅니다.  '
ms.openlocfilehash: d2d08a46ad6bcf3659c78a381ce20d99ea805ac7
ms.sourcegitcommit: ca2b58ef8f5be24f09e73620b74a1ffcf2d4c290
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/24/2020
ms.locfileid: "42255923"
---
# <a name="microsoft-365-usage-analytics-data-model"></a>Microsoft 365 사용 현황 분석 데이터 모델

## <a name="data-for-the-microsoft-365-usage-analytics-tables"></a>Microsoft 365 usage analytics 테이블에 대 한 데이터

Microsoft 365 사용 현황 분석은 다차원 데이터 모델을 노출 하는 API에 연결 됩니다. API는 미리 보기 상태이며 `https://reports.office.com/pbi/v1.0/\<tenantid\>`에서 액세스할 수 있습니다(\<tenant id\>을(를) 테넌트 GUID로 바꾸기). 
  
> [!NOTE]
> 자세한 내용은 [Microsoft Graph에서 microsoft 365 사용 현황 보고서](https://go.microsoft.com/fwlink/p/?linkid=864336)사용을 참조 하십시오. 
  
이 API는 다양 한 Microsoft 365 서비스 사용의 월별 추세에 대 한 정보를 제공 합니다. API에서 반환되는 정확한 데이터의 경우 다음 섹션의 표를 참조하세요.
  
## <a name="data-tables-returned-by-the-microsoft-365-reporting-api"></a>Microsoft 365 보고 API에서 반환 된 데이터 테이블

|**표 이름**|**테이블에 있는 정보**|**날짜 범위**|
|:-----|:-----|:-----|
|테넌트 제품 사용 현황  <br/> |사용 가능한 사용자, 활성 사용자 월 단위 재방문 사용자, 최초 사용자 및 누적 활성 사용자를 포함합니다.  <br/> |이번 달 부분 데이터를 포함하여 현시점에서 과거 12개월 동안 집계된 월별 데이터를 포함합니다.  <br/> |
|테넌트 제품 활동  <br/> |제품 내 다양한 활동에 대한 활동 및 활성 사용자 수의 월별 합계를 포함합니다.  <br/> 이 데이터 테이블에서 반환되는 제품 내의 활동에 대한 정보는 [활성 사용자 정의](active-user-in-usage-reports.md)를 참조하세요.  <br/> |이번 달 부분 데이터를 포함하여 현시점에서 과거 12개월 동안 집계된 월별 데이터를 포함합니다.  <br/> |
|테넌트 Office 라이선스  <br/> |사용자에게 할당된 Microsoft Office 구독 수에 대한 데이터를 포함합니다.  <br/> |이번 달 부분 데이터를 포함하여 현시점에서 과거 12개월에 대한 월말 상태 데이터를 포함합니다.  <br/> |
|테넌트 사서함 사용 현황  <br/> |총 사서함 수 및 저장소 사용 방법에 관한 사용자 사서함에 대한 데이터를 포함합니다.  <br/> |이번 달 부분 데이터를 포함하여 현시점에서 과거 12개월에 대한 월말 상태 데이터를 포함합니다.  <br/> |
|테넌트 클라이언트 사용 현황  <br/> |Exchange Online, 비즈니스용 Skype 및 Yammer에 연결하기 위해 특정 클라이언트/장치를 적극적으로 사용하는 사용자 수에 대한 데이터를 포함합니다.  <br/> |이번 달 부분 데이터를 포함하여 현시점에서 과거 12개월 동안 집계된 월별 데이터를 포함합니다.  <br/> |
|테넌트 SharePoint 온라인 사용 현황  <br/> |사이트 총 수, 사이트의 문서 수, 활동 유형별 파일 수 및 사용된 저장소와 같은 팀 또는 그룹 사이트를 다루는 SharePoint 사이트에 대한 데이터를 포함합니다.  <br/> |이번 달 부분 데이터를 포함하여 현시점에서 과거 12개월에 대한 월말 상태 데이터를 포함합니다.  <br/> |
|테넌트 비즈니스용 OneDrive 사용 현황  <br/> |계정 수, OneDrive 문서 수, 사용된 저장소, 활동 유형별 파일 수와 같은 OneDrive 계정에 대한 데이터를 포함합니다.  <br/> |이번 달 부분 데이터를 포함하여 현시점에서 과거 12개월에 대한 월말 상태 데이터를 포함합니다.  <br/> |
|테 넌 트 Microsoft 365 그룹 사용 현황  <br/> |사서함, SharePoint 및 Yammer를 비롯 한 Microsoft 365 그룹 사용에 대 한 데이터를 포함 합니다.  <br/> |이번 달 부분 데이터를 포함하여 현시점에서 과거 12개월에 대한 월말 상태 데이터를 포함합니다.  <br/> |
|테넌트 Office 정품 인증  <br/> |Office 구독 정품 인증 수, 장치당(Android/iOS/Mac/PC) 정품 인증 수, 서비스 요금제(예: Office Proplus, Visio, Project)에 따른 정품 인증 수에 대한 데이터를 포함합니다.  <br/> |이번 달 부분 데이터를 포함하여 현시점에서 과거 12개월에 대한 월말 상태 데이터를 포함합니다.  <br/> |
|사용자 상태  <br/> |사용자 표시 이름, 할당된 제품, 위치, 부서, 제목, 회사 등의 사용자에 대한 메타데이터를 포함합니다. 이 데이터는 지난달에 라이선스가 할당된 사용자에 대한 정보입니다. 모든 사용자는 사용자 ID로 고유하게 표시됩니다.  <br/> |이 데이터는 지난달에 할당된 라이선스를 보유했던 사용자에 대한 정보입니다.  <br/> |
|사용자 활동  <br/> |라이선스가 부여된 사용자가 수행한 활동에 대한 사용자별 수준 정보를 포함합니다.  <br/> 이 데이터 테이블에서 반환되는 제품 내의 활동에 대한 정보는 [활성 사용자 정의](active-user-in-usage-reports.md)를 참조하세요.  <br/> |이 데이터는 지난달에 모든 서비스에서 활동을 수행한 사용자에 대한 정보입니다.  <br/> |
   
각 데이터 테이블에 대한 자세한 정보를 보려면 다음 섹션을 펼치세요.
  
### <a name="data-table---user-state"></a>데이터 테이블 - 사용자 상태

이 테이블은 지난달에 할당된 라이선스를 보유한 모든 사용자에 대한 사용자 수준 세부 정보를 제공합니다. Azure Active Directory의 데이터를 가져옵니다.
  
|**열 이름**|**열 설명**|
|:-----|:-----|
|UserId  <br/> |데이터 세트 내의 다른 데이터 테이블과 결합할 수 있는 사용자를 나타내는 고유 사용자 ID입니다.  <br/> |
|시간 범위  <br/> |이 테이블에 데이터가 있는 월 값입니다.  <br/> |
|UPN  <br/> |사용자 계정 이름은 다른 외부 데이터 소스와 결합할 수 있는 사용자를 고유하게 식별합니다.  <br/> |
|DisplayName  <br/> |사용자의 표시 이름입니다.  <br/> |
|IDType  <br/> |사용자가 Yammer ID를 사용 하 여 연결 하는 Yammer 사용자 이면 id 유형이 1로, Microsoft 365 ID를 사용 하 여 Yammer에 연결 하는 경우에는 0으로 설정 됩니다.  <br/> 이 값은이 사용자가 Microsoft 365 id가 아닌 yammer id를 사용 하 여 Yammer에 연결 함을 나타내기 위해 1입니다.  <br/> |
|HasLicenseEXO  <br/> |사용자에게 라이선스가 할당되고 Exchange를 사용할 수 있는 경우 true로 설정됩니다.  <br/> |
|HasLicenseODB  <br/> |사용자에게 라이선스가 할당되고 비즈니스용 OneDrive를 사용할 수 있는 경우 true로 설정됩니다.  <br/> |
|HasLicenseSPO  <br/> |사용자에게 라이선스가 할당되고 SharePoint Online을 사용할 수 있는 경우 true로 설정됩니다.  <br/> |
|HasLicenseYAM  <br/> |사용자에게 라이선스가 할당되고 Yammer를 사용할 수 있는 경우 true로 설정됩니다.  <br/> |
|HasLicenseSFB  <br/> |사용자에게 라이선스가 할당되고 비즈니스용 Skype를 사용할 수 있는 경우 true로 설정됩니다.  <br/> |
|HasLicenseTeams  <br/> |사용자에 게 라이선스가 할당 되 고 Microsoft 팀을 사용할 수 있는 경우 true로 설정 됩니다.  <br/> |
|회사  <br/> |이 사용자의 Azure Active Directory에 표시되는 회사 데이터입니다.  <br/> |
|부서  <br/> |이 사용자의 Azure Active Directory에 표시되는 부서 데이터입니다.  <br/> |
|위치 구/군/시  <br/> |이 사용자의 Azure Active Directory에 표시되는 구/군/시 데이터입니다.  <br/> |
|LocationCountry  <br/> |이 사용자의 Azure Active Directory에 표시되는 국가 데이터입니다.  <br/> |
|LocationState  <br/> |이 사용자의 Azure Active Directory에 표시되는 상태 데이터입니다.  <br/> |
|LocationOffice  <br/> |사용자의 사무실입니다.  <br/> |
|제목  <br/> |이 사용자의 Azure Active Directory에 표시되는 제목 데이터입니다.  <br/> |
|삭제됨  <br/> |사용자가 마지막으로 완료 된 전체 달에 Microsoft 365에서 삭제 된 경우 True입니다.  <br/> |
|DeletedDate  <br/> |사용자가 Microsoft 365에서 삭제 된 날짜입니다.  <br/> |
|YAM_State  <br/> |Yammer 시스템에서 사용자의 상태는 활성, 삭제 또는 일시 중단될 수 있습니다.  <br/> |
|YAM_ActivationDate  <br/> |사용자가 입력한 Yammer에서 활성 상태인 날짜입니다.  <br/> |
|YAM_DeletionDate  <br/> |사용자가 입력한 Yammer에서 삭제 상태인 날짜입니다.  <br/> |
|YAM_SuspensionDate  <br/> |사용자가 입력한 Yammer에서 일시 중단된 상태인 날짜입니다.  <br/> |
   
### <a name="data-table---user-activity"></a>데이터 테이블 - 사용자 활동

이 테이블은 지난달에 모든 서비스에 활동을 수행한 각 사용자에 대한 데이터를 포함합니다.
  
|**열 이름**|**열 설명**|
|:-----|:-----|
|UserID  <br/> |데이터 세트 내의 다른 데이터 테이블과 결합할 수 있는 사용자를 나타내는 고유 사용자 ID입니다.  <br/> |
|IDType  <br/> |사용자가 Yammer ID를 사용 하 여 연결 하는 Yammer 사용자 이면 id 유형이 1로, Microsoft 365 ID를 사용 하 여 Yammer에 연결 하는 경우에는 0으로 설정 됩니다.  <br/> 이 값은이 사용자가 Microsoft 365 id가 아닌 yammer id를 사용 하 여 Yammer에 연결 함을 나타내기 위해 1입니다.  <br/> |
|시간 범위  <br/> |이 테이블이 데이터를 나타내는 월 값입니다.  <br/> |
|EXO_EmailSent  <br/> |보낸 전자 메일 수입니다.  <br/> |
|EXO_EmailReceived  <br/> |받은 전자 메일 수입니다.  <br/> |
|EXO_EmailRead  <br/> |사용자가 수행한 전자 메일 읽기 활동 횟수입니다. 이미 읽은 전자 메일 또는 이전에 수신된 전자 메일을 여러 번 읽었을 수 있습니다.  <br/> |
|EXO_AppointmentCreated  <br/> |만든 약속 수입니다.  <br/> |
|EXO_MeetingAccepted  <br/> |수락 된 모임 수입니다.  <br/> |
|EXO_MeetingCancelled  <br/> |취소 된 모임 수입니다.  <br/> |
|EXO_MeetingDeclined  <br/> |거절 된 모임 수입니다.  <br/> |
|EXO_MeetingSent  <br/> |전송 된 모임 수입니다.  <br/> |
|ODB_FileViewedModified  <br/> |이 사용자가 비즈니스용 OneDrive에서 상호 작용한(예: 만들기, 업데이트, 삭제, 조회 또는 다운로드 작업 수행) 파일 수입니다.  <br/> |
|ODB_FileSynched  <br/> |이 사용자가 비즈니스용 OneDrive에서 동기화한 파일 수입니다.  <br/> |
|ODB_FileSharedInternally  <br/> |이 사용자가 비즈니스용 OneDrive에서 내부적으로 공유한 파일 수 또는 외부 사용자를 포함할 수 있는 그룹 내의 사용자입니다.  <br/> |
|ODB_FileSharedExternally  <br/> |이 사용자가 비즈니스용 OneDrive에서 외부적으로 공유한 파일 수입니다.  <br/> |
|ODB_AccessByOwner  <br/> |이 사용자가 상호 작용한 사용자의 비즈니스용 OneDrive에 있는 파일 수입니다.  <br/> |
|ODB_AccessOthers  <br/> |이 사용자가 상호 작용한 다른 사용자의 비즈니스용 OneDrive에 있는 파일 수입니다.  <br/> |
|SPO_GroupFileViewedModified  <br/> |이 사용자가 그룹 사이트에서 상호 작용한 파일 수입니다.  <br/> |
|SPO_GroupFileSynched  <br/> |이 사용자가 그룹 사이트에서 동기화한 파일 수입니다.  <br/> |
|SPO_GroupFileSharedInternally  <br/> |조직 내의 사용자 또는 외부 사용자를 포함할 수 있는 그룹 내의 사용자와 공유 된 파일의 개수입니다.  <br/> |
|SPO_GroupFileSharedExternally  <br/> |사용자가 그룹 사이트에서 외부적으로 공유한 파일 수입니다.  <br/> |
|SPO_GroupAccessByOwner  <br/> |이 사용자가 상호 작용한 소유한 그룹 사이트에 있는 파일 수입니다.  <br/> |
|SPO_GroupAccessByOthers  <br/> |다른 사용자가 소유한 그룹 사이트에 있고 사용자가 상호 작용한 파일 수입니다.  <br/> |
|SPO_OtherFileViewedModified  <br/> |이 사용자가 다른 사이트에서 상호 작용 한 파일 수입니다.  <br/> |
|SPO_OtherFileSynched  <br/> |이 사용자가 다른 사이트에서 동기화 한 파일 수입니다.  <br/> |
|SPO_OtherFileSharedInternally  <br/> |이 사용자가 다른 사이트에서 내부적으로 공유한 파일의 수 또는 외부 사용자를 포함할 수 있는 그룹 내의 사용자를 포함 합니다. <br/> |
|SPO_OtherFileSharedExternally  <br/> |이 사용자가 다른 사이트에서 외부적으로 공유한 파일 수입니다.  <br/> |
|SPO_OtherAccessedByOwner  <br/> |사용자가 상호 작용 한 사이트 중 해당 하는 다른 사이트의 수입니다.  <br/> |
|SPO_OtherAccessedByOthers  <br/> |다른 사용자가 소유한 다른 사이트에 있는 사용자가 상호 작용 한 사이트 수입니다.  <br/> |
|SPO_TeamFileViewedModified  <br/> |이 사용자가 모든 팀 사이트에서 상호 작용한 파일 수입니다.  <br/> |
|SPO_TeamFileSynched  <br/> |이 사용자가 팀 사이트에서 동기화한 파일 수입니다.  <br/> |
|SPO_TeamFileSharedInternally  <br/> |이 사용자가 모든 팀 사이트에서 내부적으로 공유한 파일의 수 또는 외부 사용자를 포함할 수 있는 그룹 내의 사용자와의 관계입니다.  <br/> |
|SPO_TeamFileSharedExternally  <br/> |이 사용자가 팀 사이트에서 외부적으로 공유한 파일 수입니다.  <br/> |
|SPO_TeamAccessByOwner  <br/> |이 사용자가 상호 작용한 소유한 팀 사이트에 있는 파일 수입니다.  <br/> |
|SPO_TeamAccessByOthers  <br/> |다른 사용자가 소유한 팀 사이트에 있고 사용자가 상호 작용한 파일 수입니다.  <br/> |
|Teams_ChatMessages  <br/> |전송 된 채팅 메시지 수입니다.  <br/> |
|Teams_ChannelMessage  <br/> |채널에 게시 된 메시지 수입니다.  <br/> |
|Teams_CallParticipate  <br/> |사용자가 참여 한 통화 수입니다.  <br/> |
|Teams_MeetingParticipate  <br/> |사용자가 참가 한 모임 수입니다.  <br/> |
|Teams_HasOtherAction  <br/> |사용자가 Microsoft 팀에서 다른 작업을 수행한 경우에는 부울 값입니다.  <br/> |
|YAM_MessagePost  <br/> |이 사용자가 게시한 Yammer 메시지 수입니다.  <br/> |
|YAM_MessageLiked  <br/> |이 사용자가 좋아하는 Yammer 메시지 수입니다.  <br/> |
|YAM_MessageRead  <br/> |이 사용자가 읽은 Yammer 메시지 수입니다.  <br/> |
|SFB_P2PSummary  <br/> |이 사용자가 참여한 피어 투 피어 세션 수입니다.  <br/> |
|SFB_ConfOrgSummary  <br/> |이 사용자가 구성한 회의 세션 수입니다.  <br/> |
|SFB_ConfPartSummary  <br/> |이 사용자가 참여한 회의 세션 수입니다.  <br/> |
   
### <a name="data-table---tenant-product-usage"></a>데이터 테이블 - 테넌트 제품 사용 현황

이 테이블은 Microsoft 365 내의 각 제품에 대 한 사용, 활성, 반품 및 최초 사용자의 관점에서 월별 채택 데이터를 제공 합니다. Microsoft 365 값은 제품 중 하나에서의 실제 사용 현황을 나타냅니다.
  
|**열 이름**|**열 설명**|
|:-----|:-----|
|제품  <br/> |사용 현황 정보가 요약된 제품의 이름입니다. 제품 열의 Microsoft 365 값은 모든 제품에 걸친 활동을 나타냅니다.  <br/> |
|시간 범위  <br/> |월 값입니다. 이번 달 일부를 포함하여 지난 12개월 동안의 월별 제품당 하나의 행이 있습니다.  <br/> |
|EnabledUsers  <br/> |시간 범위 값에 대해 제품을 사용할 수 있는 사용자 수입니다. 사용자가 해당 달의 일부분의 기간에 대해 사용하도록 설정된 경우 계속 집계됩니다.  <br/> |
|Activeusers 작업  <br/> |시간 범위 값에 대해 제품에서 의도적인 활동을 수행한 사용자 수입니다.  <br/> 사용자가 제품의 주요 활동 중 하나를 수행한 경우 특정 달의 제품에 대해 활성으로 집계됩니다. 주요 활동은 **테넌트 제품 활동** 테이블에서 확인할 수 있습니다.  <br/> |
|CumulativeActiveUsers  <br/> |제품을 사용할 수 있고 새 사용 현황 시스템에서 데이터 수집이 시작된 이후 시간 범위(월)까지 제품을 1번 이상 사용한 사용자 수입니다.  <br/> |
|MoMReturningUsers  <br/> |시간 범위(월)에 활성 상태이고 이전 달에도 활성화된 사용자 수입니다.  <br/> |
|FirstTimeUsers  <br/> |새 사용 현황 시스템에서 데이터 수집이 시작된 이후 시간 범위 내에서 처음으로 활성 상태가 된 사용자 수입니다.  <br/> 이 새 보고 시스템에서 데이터 수집을 시작한 후 처음으로 사용자 활동을 감지하는 경우 사용자는 특정 달에 최초 사용자로 집계됩니다. 한 번 최초 사용자로 집계되면, 이후 오랫동안 활동이 지속되지 않아도 다시 최초 사용자로 집계되지 않습니다.  <br/> |
|콘텐츠 날짜  <br/> |시간 범위에 이번 달이 표시되는 경우 이 값은 데이터를 사용할 수 있는 이번 달의 마지막 날짜를 나타냅니다.  <br/> 시간 범위에 지난 달이 표시되는 경우 이 값은 시간 범위(월)의 마지막 날짜를 나타냅니다.  <br/> |
   
### <a name="data-table---tenant-product-activity"></a>데이터 테이블 - 테넌트 제품 활동

이 테이블은 제품 내 다양한 활동에 대한 활동 및 활성 사용자 수의 월별 합계를 제공합니다.
  
|**열 이름**|**열 설명**|
|:-----|:-----|
|시간 범위  <br/> |월 값입니다. 이번 달 일부를 포함하여 지난 12개월 동안의 월별 제품당 하나의 행이 있습니다.  <br/> |
|제품  <br/> |Microsoft 365 내에서 사용 현황 데이터를 사용할 수 있는 제품의 이름입니다.  <br/> |
|활동  <br/> |제품의 활성 사용을 보여주는 데 사용되는 제품의 활동 이름입니다.  <br/> |
|ActivityCount  <br/> |모든 활성 사용자가 제품 내에서 수행한 각 활동에 대해 집계된 총 작업 수입니다.  <br/> **참고:** SharePoint Online 및 비즈니스용 OneDrive의 경우 이 값은 사용자가 상호 작용하는 고유 문서 수를 나타냅니다.  <br/> |
|ActiveUserCount  <br/> |제품 내에서 활동을 수행한 사용자 수입니다.  <br/> |
|TotalDurationInMinute  <br/> |해당하는 비즈니스용 Skype 활동에서 활성 사용자가 오디오 또는 비디오 세션을 사용한 기간(분)입니다.  <br/> |
|콘텐츠 날짜  <br/> |시간 범위에 이번 달이 표시되는 경우 이 값은 데이터를 사용할 수 있는 이번 달의 마지막 날짜를 나타냅니다.  <br/> 시간 범위에 지난 달이 표시되는 경우 이 값은 시간 범위(월)의 마지막 날짜를 나타냅니다.  <br/> |
   
### <a name="data-table---tenant-mailbox-usage"></a>데이터 테이블 - 테넌트 사서함 사용 현황

이 테이블은 사용자 사서함이 있는 모든 라이선스가 부여된 Exchange Online 사용자의 요약 데이터로 구성됩니다. 모든 사용자 사서함의 월말 상태가 포함됩니다. 이 테이블의 데이터는 여러 달에 추가되지 않습니다. 이 테이블의 최신 월 데이터는 가장 최근의 상태를 나타냅니다.
  
|**열 이름**|**열 설명**|
|:-----|:-----|
|TotalMailboxes  <br/> |Microsoft 365 구독의 사용자 사서함 수입니다.  <br/> |
|IssueWarningQuota  <br/> |모든 사용자 사서함에서 경고를 보내기 위한 총 할당량입니다.  <br/> |
|ProhibitSendQuota  <br/> |모든 사용자 사서함에서 보내기를 금지하는 총 할당량입니다.  <br/> |
|ProhibitSendReceiveQuota  <br/> |모든 사용자 사서함에서 보내기/받기 할당량을 금지하는 총 할당량입니다.  <br/> |
|TotalItemBytes  <br/> |모든 사용자 사서함에서 사용되는 저장소의 크기(바이트)입니다.  <br/> |
|MailboxesNoWarning  <br/> |저장소 경고 제한 상태의 사용자 사서함 수입니다.  <br/> |
|MailboxesIssueWarning  <br/> |저장소 할당량에 대한 경고를 받은 사용자 사서함 수입니다.  <br/> |
|MailboxesExceedSendQuota  <br/> |보내기 할당량을 초과한 사용자 사서함 수입니다.  <br/> |
|MailboxesExceedSendReceiveQuota  <br/> |보내기/받기 할당량을 초과한 사용자 사서함 수입니다.  <br/> |
|DeletedMailboxes  <br/> |시간 범위에서 삭제된 사용자 사서함 수입니다.  <br/> |
|시간 범위  <br/> |월 값입니다.  <br/> |
|콘텐츠 날짜  <br/> |시간 범위에 이번 달이 표시되는 경우 이 값은 데이터를 사용할 수 있는 이번 달의 마지막 날짜를 나타냅니다.  <br/> 시간 범위에 지난 달이 표시되는 경우 이 값은 시간 범위(월)의 마지막 날짜를 나타냅니다.  <br/> |
   
### <a name="data-table---tenant-client-usage"></a>데이터 테이블 - 테넌트 클라이언트 사용 현황

이 테이블은 사용자가 Exchange Online, 비즈니스용 Skype, Yammer에 접속하는 데 사용하는 클라이언트에 대한 월 단위 요약 데이터를 제공합니다. 이 테이블에는 아직 SharePoint Online 및 비즈니스용 OneDrive용 클라이언트 사용 데이터는 없습니다.
  
|**열 이름**|**열 설명**|
|:-----|:-----|
|제품  <br/> |클라이언트 사용 현황 데이터를 사용할 수 있는 Microsoft 365 내의 제품 이름입니다.  <br/> |
|ClientId  <br/> |제품에 연결하는 데 사용되는 각 장치의 이름입니다.  <br/> |
|UserCount  <br/> |각 제품에 대한 각 클라이언트를 사용한 사용자 수입니다.  <br/> |
|시간 범위  <br/> |월 값  <br/> |
|콘텐츠 날짜  <br/> |시간 범위에 이번 달이 표시되는 경우 이 값은 데이터를 사용할 수 있는 이번 달의 마지막 날짜를 나타냅니다.  <br/> 시간 범위에 지난 달이 표시되는 경우 이 값은 시간 범위(월)의 마지막 날짜를 나타냅니다.  <br/> |
   
### <a name="data-table---tenant-sharepoint-online-usage"></a>데이터 테이블 - 테넌트 SharePoint 온라인 사용 현황

이 테이블은 SharePoint Online 사이트의 사용 현황 또는 활동에 대한 월 단위 요약 데이터로 구성됩니다. 이 데이터는 팀 사이트 및 그룹 사이트에만 해당됩니다. SharePoint Online 사이트의 월말 상태는 이 열에 표시됩니다. 예를 들어, 사용자가 10MB의 총 저장소를 사용하여 5개의 문서를 작성한 후 일부 파일을 삭제하고 다시 파일을 추가하여 파일의 월말 상태가 5MB의 저장소를 사용하는 파일 7개가 되는 경우 이 테이블에 표시된 값이 월말 상태가 됩니다. 이 테이블은 집계 수가 중복되지 않고 원본으로 사용되어 2개의 참조 테이블을 생성할 수 있도록 숨겨졌습니다.
  
|**열 이름**|**열 설명**|
|:-----|:-----|
|SiteType  <br/> |사이트 유형 값(전체/팀/그룹)(모든 값은 두 사이트 유형 중 하나를 나타냄)입니다.  <br/> |
|TotalSites  <br/> |종료 시간에 존재하는 사이트 수입니다.  <br/> |
|DocumentCount  <br/> |종료 시간에 사이트에 존재하는 총 문서 수입니다.  <br/> |
|Di계획 sed  <br/> |종료 시간에 모든 사이트에서 합계된 총 사용 저장소입니다.  <br/> |
|ActivityType  <br/> |다양한 파일 활동(전체/활성 파일/공유된 파일 EXT/INT/동기화된 파일)을 기록한 사이트 수입니다.  <br/> 모든 값은 파일 활동이 수행되었음을 나타냅니다.  <br/> |
|SitesWithOwnerActivities  <br/> |사이트 소유자가 자신의 고유 사이트에서 특정 파일 활동을 수행한 활성 사이트 수입니다.  <br/> |
|SitesWithNonOwnerActivities  <br/> |사이트 소유자가 아닌 다른 사용자가 사이트에서 특정 파일 활동을 수행한 달에 합계된 활성 사이트 수입니다.  <br/> |
|ActivityTotalSites  <br/> |시간 범위에서 활동을 기록한 사이트 수입니다. 사이트에서 시간 범위 초반에 있던 활동이 종료 시간에 삭제된 경우에도 해당 시간 범위에 대한 활성 사이트 총계에서 집계됩니다.  <br/> |
|시간 범위  <br/> |이 열에 날짜 값이 있습니다. 일정 테이블에 대해 다대일 관계로 사용됩니다.  <br/> |
|콘텐츠 날짜  <br/> |시간 범위에 이번 달이 표시되는 경우 이 값은 데이터를 사용할 수 있는 이번 달의 마지막 날짜를 나타냅니다.  <br/> 시간 범위에 지난 달이 표시되는 경우 이 값은 시간 범위(월)의 마지막 날짜를 나타냅니다.  <br/> |
   
### <a name="data-table---tenant-onedrive-usage"></a>데이터 테이블-테 넌 트 OneDrive 사용 현황

이 테이블은 계정 수, OneDrive 계정의 문서 수, 사용된 저장소, 활동 유형별 파일 수와 같은 OneDrive 계정에 대한 데이터를 제공합니다. 비즈니스용 OneDrive 계정의 월말 상태는 이 테이블에 표시됩니다. 예를 들어, 사용자가 10MB의 저장소를 사용하여 5개의 문서를 작성한 후 일부 문서를 삭제하고 다시 파일을 추가하여 월말에 5MB의 저장소를 사용하는 7개의 파일이 남아 있는 경우 월말에 이 테이블에는 월말 값이 표시됩니다.
  
|**열 이름**|**열 설명**|
|:-----|:-----|
|SiteType  <br/> |값은 "OneDrive" 입니다.  <br/> |
|TotalSites  <br/> |종료 시간에 존재한 비즈니스용 OneDrive 계정 수입니다.  <br/> |
|DocumentCount  <br/> |종료 시간에 모든 비즈니스용 OneDrive 계정에 존재한 총 문서 수입니다.  <br/> |
|Di계획 sed  <br/> |종료 시간에 모든 OneDrive 계정에서 합계된 총 사용 저장소입니다.  <br/> |
|ActivityType  <br/> |다양한 파일 활동(전체/활성 파일/공유된 파일 EXT/INT/동기화된 파일)을 기록한 계정 수입니다.  <br/> 모든 값은 파일 활동이 수행되었음을 나타냅니다.  <br/> |
|SitesWithOwnerActivities  <br/> |계정 소유자가 자신의 고유 계정에서 특정 파일 활동을 수행한 비즈니스용 OneDrive용 활성 계정 수입니다.  <br/> |
|SitesWithNonOwnerActivities  <br/> |계정 소유자 이외의 사용자가 파일 작업을 수행한 비즈니스용 OneDrive 계정의 수입니다.  <br/> |
|ActivityTotalSites  <br/> |시간 범위에서 활동을 기록한 비즈니스용 OneDrive 계정 수입니다. 비즈니스용 OneDrive 계정에서 시간 범위 초반에 있던 활동이 종료 시간에 삭제된 경우에도 해당 시간 범위에 대한 비즈니스용 OneDrive 활성 계정 총계에서 집계됩니다.  <br/> |
|시간 범위  <br/> |이 열에 날짜 값이 있습니다. 일정 테이블에 대해 다대일 관계로 사용됩니다.  <br/> |
|콘텐츠 날짜  <br/> |시간 범위에 이번 달이 표시되는 경우 이 값은 데이터를 사용할 수 있는 이번 달의 마지막 날짜를 나타냅니다.  <br/> 시간 범위에 지난 달이 표시되는 경우 이 값은 시간 범위(월)의 마지막 날짜를 나타냅니다.  <br/> |
   
### <a name="data-table---tenant-microsoft-365-groups-usage"></a>데이터 테이블-테 넌 트 Microsoft 365 Groups Usage

이 테이블은 조직 전체에서 Microsoft 365 그룹을 사용 하는 방법에 대 한 데이터를 제공 합니다.
  
****

|**열 이름**|**열 설명**|
|:-----|:-----|
|지난  <br/> |월 값입니다. 이번 달 일부를 포함하여 지난 12개월 동안의 월별 제품당 하나의 행이 있습니다.  <br/> |
|GroupType  <br/> |그룹 유형 (전용/공용/any)입니다.  <br/> |
|TotalGroups  <br/> |각 그룹 유형의 그룹 수입니다.  <br/> |
|ActiveGroups  <br/> |활성 그룹 수입니다.  <br/> |
|MBX_TotalGroups  <br/> |사서함 그룹의 수입니다.  <br/> |
|MBX_ActiveGroups  <br/> |활성 사서함 그룹의 수입니다.  <br/> |
|MBX_TotalActivities  <br/> |사서함 활동 수입니다.  <br/> |
|MBX_TotalItems  <br/> |사서함 항목 수입니다.  <br/> |
|MBX_StorageUsed  <br/> |사용 된 사서함 저장소의 양  <br/> |
|SPO_TotalGroups  <br/> |SharePoint 그룹 수입니다.  <br/> |
|SPO_ActiveGroups  <br/> |활성 SharePoint 그룹의 수입니다.  <br/> |
|SPO_FileAccessedActiveGroups  <br/> |파일에 액세스 한 작업을 포함 하는 SharePoint 그룹의 수입니다.  <br/> |
|SPO_FileSyncedActiveGroups  <br/> |파일 동기화 활동이 있는 SharePoint 그룹 수입니다.  <br/> |
|SPO_FileSharedInternallyActiveGroups  <br/> |공유 작업을 포함 하는 SharePoint 그룹의 수 또는 외부 사용자를 포함할 수 있는 그룹을 사용 하는 경우  <br/> |
|SPO_FileSharedExternallyActiveGroups  <br/> |외부 활동을 공유 하는 SharePoint 그룹 수입니다.  <br/> |
|SPO_TotalActivities  <br/> |SharePoint 작업 수입니다.  <br/> |
|SPO_FileAccessedActivities  <br/> |액세스 한 SharePoint 파일 활동 수입니다.  <br/> |
|SPO_FileSyncedActivities  <br/> |SharePoint 파일 동기화 된 활동의 수입니다.  <br/> |
|SPO_FileSharedInternallyActivities  <br/> |SharePoint 파일 공유 작업의 수 또는 외부 멤버를 포함할 수 있는 그룹을 사용 하는 것입니다.  <br/> |
|SPO_FileSharedExternallyActivities  <br/> |SharePoint 파일 공유 외부 활동 수입니다.  <br/> |
|SPO_TotalFiles  <br/> |SharePoint 파일 수입니다.  <br/> |
|SPO_ActiveFiles  <br/> |활성 SharePoint 파일 수입니다.  <br/> |
|SPO_StorageUsed  <br/> |사용 된 SharePoint 저장소의 양  <br/> |
|YAM_TotalGroups  <br/> |Yammer 그룹 수입니다.  <br/> |
|YAM_ActiveGroups  <br/> |활성 Yammer 그룹 수입니다.  <br/> |
|YAM_LikedActiveGroups  <br/> |활동과 같은 Yammer 그룹의 수입니다.  <br/> |
|YAM_PostedActiveGroups  <br/> |게시 된 활동을 포함 하는 Yammer 그룹의 수입니다.  <br/> |
|YAM_ReadActiveGroups  <br/> |읽기 활동이 있는 Yammer 그룹 수입니다.  <br/> |
|YAM_TotalActivities  <br/> |Yammer 활동 수입니다.  <br/> |
|YAM_LikedActivities  <br/> |활동 같은 Yammer 수입니다.  <br/> |
|YAM_PostedActivties  <br/> |Yammer 게시물 활동 수입니다.  <br/> |
|YAM_ReadActivites  <br/> |Yammer 읽기 작업 수입니다.  <br/> |
   
### <a name="data-table---tenant-office-activation"></a>데이터 테이블 - 테넌트 Office 정품 인증

이 테이블은 서비스 요금제(예: Office Proplus, Visio, Project)의 Office 구독 정품 인증 수에 대한 데이터를 제공합니다. 장치(Android/iOS/Mac/PC)당 정품 인증 수에 대한 데이터도 제공합니다.
  
|**열 이름**|**열 설명**|
|:-----|:-----|
|Service계획 이름  <br/> |아래 열에 표시되는 것과 같이 서비스 요금제 이름 값 목록 및 장치별 정품 인증 수입니다.  <br/> |
|TotalEnabled  <br/> |종료 시간까지 서비스 요금제 이름별로 사용할 수 있는 사용자 수입니다.  <br/> |
|TotalActivatedUsers  <br/> |종료 시간까지 각 서비스 요금제를 활성화한 사용자 수입니다.  <br/> |
|AndroidCount  <br/> |종료 시간까지의 Android 장치에 대한 서비스 요금제당 활성화 수입니다.  <br/> |
|iOSCount  <br/> |종료 시간까지의 iOS 장치에 대한 서비스 요금제당 활성화 수입니다.  <br/> |
|MacCount  <br/> |종료 시간까지의 MAC 장치에 대한 서비스 요금제당 활성화 수입니다.  <br/> |
|PcCount  <br/> |종료 시간까지의 PC 장치에 대한 서비스 요금제당 활성화 수입니다.  <br/> |
|WinRtCount  <br/> |종료 시간까지의 Windows Mobile 장치에 대한 서비스 요금제당 활성화 수입니다.  <br/> |
|시간 범위  <br/> |이 열에 날짜 값이 있습니다. 일정 테이블에 대해 다대일 관계로 사용됩니다.  <br/> |
|콘텐츠 날짜  <br/> |시간 범위에 이번 달이 표시되는 경우 이 값은 데이터를 사용할 수 있는 이번 달의 마지막 날짜를 나타냅니다.  <br/> 시간 범위에 지난 달이 표시되는 경우 이 값은 시간 범위(월)의 마지막 날짜를 나타냅니다.  <br/> |
   

