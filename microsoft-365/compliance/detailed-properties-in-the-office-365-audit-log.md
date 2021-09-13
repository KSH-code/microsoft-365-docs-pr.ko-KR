---
title: 감사 로그의 자세한 속성
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: reference
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- Strat_O365_IP
- M365-security-compliance
search.appverid:
- MOE150
- BCS160
- MET150
ms.assetid: ce004100-9e7f-443e-942b-9b04098fcfc3
description: 이 문서에서는 감사 로그 레코드에 대한 결과를 내보낼 때 포함된 추가 Office 365 제공합니다.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 20965367cda41ad50070d42b306564f6a8d9bb8b
ms.sourcegitcommit: d08fe0282be75483608e96df4e6986d346e97180
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/12/2021
ms.locfileid: "59193172"
---
# <a name="detailed-properties-in-the-audit-log"></a>감사 로그의 자세한 속성

감사 로그 검색의 결과를 감사 로그 Microsoft 365 규정 준수 센터 검색 조건을 충족하는 모든 결과를 다운로드할 수 있습니다. 결과 내보내기 **를 선택하여** 감사 로그 검색 페이지에서 \> **모든** 결과 **다운로드를 선택하여 이 작업을 합니다.** 자세한 내용은 감사 로그 [검색을 참조하세요.](search-the-audit-log-in-security-and-compliance.md)
  
 감사 로그 검색에 대한 모든 결과를 내보내면 통합 감사 로그의 원시 데이터가 로컬 컴퓨터로 다운로드되는 CSV(콤보로 구분된 값) 파일에 복사됩니다. 이 파일에는 **AuditData** 열에 있는 각 감사 레코드의 추가 정보가 포함되어 있습니다. 이 열에는 감사 로그 레코드의 여러 속성에 대한 다중 값 속성이 포함되어 있습니다. 이 다중 값 속성의 각 **속성:** 값 쌍은 각 콤보로 구분됩니다. 
  
다음 표에서는 다중 속성 **AuditData** 열에 포함된 속성(이벤트가 발생하는 서비스에 따라 다를 수 있습니다.)에 대해 설명하고 있습니다. 이 **Office 365** 열이 있는 서비스 서비스는 해당 속성을 포함하는 활동의 서비스 및 유형(사용자 또는 관리자)을 나타냅니다. 이러한 속성 또는 이 항목에 나열되지 않을 수 있는 속성에 대한 자세한 내용은 [Management Activity API Schema 를 참조하세요.](/office/office-365-management-api/office-365-management-activity-api-schema)
  
> [!TIP]
> Power Query의 JSON 변환 기능을 사용하여 각 Excel 열이 있도록 **AuditData** 열을 여러 열로 분할할 수 있습니다. 이렇게 하면 하나 이상의 속성을 기준으로 정렬 및 필터링할 수 있습니다. 이 작업을 하는 방법에 대한 자세한 내용은 감사 로그 레코드 [내보내기, 구성 및 보기를 참조합니다.](export-view-audit-log-records.md) 
  
|**속성**|**설명**|**Microsoft 365 있는 서비스**|
|:-----|:-----|:-----|
|배우|작업을 수행한 사용자 또는 서비스 계정입니다.|Azure Active Directory|
|AddOnName|팀에서 추가, 제거 또는 업데이트된 추가 기능의 이름입니다. 추가 기능의 유형은 Microsoft Teams, 연결선 또는 탭입니다.|Microsoft Teams|
|AddOnType|팀에서 추가, 제거 또는 업데이트된 추가 기능의 유형입니다. 다음 값은 추가 기능의 유형을 나타냅니다.  <br/> **1** - 봇을 나타냅니다.<br/> **2** - 커넥터를 나타냅니다.<br/> **3** - 탭을 나타냅니다.|Microsoft Teams|
|AzureActiveDirectoryEventType|이벤트의 Azure Active Directory 형식입니다. 다음 값은 이벤트 유형을 나타냅니다.  <br/> **0** - 계정 로그인 이벤트를 나타냅니다.<br/> **1** - Azure 응용 프로그램 보안 이벤트를 나타냅니다.|Azure Active Directory|
|ChannelGuid|채널의 Microsoft Teams ID입니다. 채널이 있는 팀은 **TeamName** 및 **TeamGuid** 속성으로 식별됩니다.|Microsoft Teams|
|ChannelName|채널의 Microsoft Teams 이름입니다. 채널이 있는 팀은 **TeamName** 및 **TeamGuid** 속성으로 식별됩니다.|Microsoft Teams|
|클라이언트|로그인 이벤트에 사용되는 클라이언트 장치, 장치 OS 및 장치 브라우저(예: Nokia Lumia 920) Windows Phone 8; IE Mobile 11).|Azure Active Directory|
|ClientInfoString|브라우저 버전, Outlook 및 모바일 장치 정보와 같은 작업을 수행하는 데 사용된 전자 메일 클라이언트에 대한 정보|Exchange(사서함 활동)|
|ClientIP|활동이 기록될 때 사용된 장치의 IP 주소입니다. IP 주소는 IPv4 또는 IPv6 주소 형식으로 표시됩니다.<br/><br/> 일부 서비스의 경우 이 속성에 표시되는 값은 사용자를 대신하여 서비스에 호출하는 신뢰할 수 있는 응용 프로그램(예: 웹용 Office 앱)의 IP 주소가 될 수 있으며 활동을 수행한 사용자가 사용한 장치의 IP 주소가 아될 수 있습니다. <br/><br/>또한 Azure Active Directory 이벤트에 대한 관리자 활동(또는 시스템 계정에서 수행한 활동)의 경우 IP 주소가 기록되지 않습니다. ClientIP 속성의 값은 `null` 입니다. |Azure Active Directory, Exchange, SharePoint|
|CreationTime|사용자가 활동을 수행한 UTC(협정 세계시)의 날짜 및 시간입니다.|모두|
|DestinationFileExtension|복사되거나 이동된 파일의 파일 확장명입니다. 이 속성은 FileCopied 및 FileMoved 사용자 활동에만 표시됩니다.|SharePoint|
|DestinationFileName|파일의 이름이 복사되거나 이동됩니다. 이 속성은 FileCopied 및 FileMoved 작업에만 표시됩니다.|SharePoint|
|DestinationRelativeUrl|파일을 복사하거나 이동할 대상 폴더의 URL입니다. **SiteURL,** **DestinationRelativeURL** 및 **DestinationFileName** 속성 값의 조합은 **복사된** 파일의 전체 경로 이름인 ObjectID 속성 값과 동일합니다. 이 속성은 FileCopied 및 FileMoved 사용자 활동에만 표시됩니다.|SharePoint|
|EventSource|이벤트가 발생한 이벤트가 SharePoint. 가능한 값은 **SharePoint** **및 ObjectModel입니다.**|SharePoint|
|ExternalAccess|Exchange 활동의 경우 조직의 사용자, Microsoft 데이터 센터 직원 또는 데이터 센터 서비스 계정 또는 위임된 관리자가 cmdlet을 실행할지 여부를 지정합니다. False **값은** cmdlet이 조직의 누군가가 실행했다는 것을 나타냅니다. True **값은** 데이터 센터 직원, 데이터 센터 서비스 계정 또는 위임된 관리자가 cmdlet을 실행한 것입니다.  <br/> Exchange 활동의 경우 조직 외부의 사용자가 사서함에 액세스할지 여부를 지정합니다.|Exchange|
|ExtendedProperties|이벤트에 대한 확장 Azure Active Directory.|Azure Active Directory|
|ID|보고서 항목의 ID입니다. ID는 보고서 항목을 고유하게 식별합니다.|모두|
|InternalLogonType|내부용으로 예약되어 있습니다.|Exchange(사서함 활동)|
|ItemType|액세스하거나 수정한 개체의 형식입니다. 가능한 값은 **File,** **Folder,** **Web,** **Site,** **Tenant** 및 **DocumentLibrary입니다.**|SharePoint|
|LoginStatus|발생한 로그인 실패를 식별합니다.|Azure Active Directory|
|LogonType|사서함 액세스 유형입니다. 다음 값은 사서함에 액세스한 사용자의 유형을 나타냅니다.  <br/><br/> **0** - 사서함 소유자를 나타냅니다.<br/> **1** - 관리자를 나타냅니다.<br/> **2** - 대리인을 나타냅니다. <br/>**3** - Microsoft 데이터 센터의 전송 서비스를 나타냅니다.<br/> **4** - Microsoft 데이터 센터의 서비스 계정을 나타냅니다. <br/>**6** - 위임된 관리자를 나타냅니다.|Exchange(사서함 활동)|
|MailboxGuid|액세스 Exchange 사서함의 GUID입니다.|Exchange(사서함 활동)|
|MailboxOwnerUPN|액세스한 사서함을 소유한 사람의 전자 메일 주소입니다.|Exchange(사서함 활동)|
|구성원|팀에서 추가되거나 제거된 사용자를 나열합니다. 다음 값은 사용자에게 할당된 역할 유형을 나타냅니다.  <br/><br/> **1** - 소유자 역할을 나타냅니다.<br/> **2** - 구성원 역할을 나타냅니다.<br/> **3** - 게스트 역할을 나타냅니다. <br/><br/>구성원 속성에는 조직의 이름 및 구성원의 전자 메일 주소도 포함됩니다.|Microsoft Teams|
|ModifiedProperties(Name, NewValue, OldValue)|이 속성은 사이트 또는 사이트 모음 관리자 그룹의 구성원으로 사용자를 추가하는 등의 관리 이벤트에 포함됩니다. 속성에는 수정된 속성의 이름(예: 사이트 관리 그룹)의 새 값(예: 사이트 관리자로 추가된 사용자) 및 수정된 개체의 이전 값이 포함됩니다.|모두(관리자 활동)|
|ObjectId|관리자 Exchange 로깅의 경우 cmdlet에서 수정한 개체의 이름입니다.  <br/> SharePoint 작업의 경우 사용자가 액세스한 파일 또는 폴더의 전체 URL 경로 이름입니다.  <br/> Azure AD 활동의 경우 수정된 사용자 계정의 이름입니다.|모두|
|작업|사용자 또는 관리자 활동의 이름입니다. 이 속성의 값은 활동 드롭다운 목록에서 선택한 **값에** 해당합니다. 모든 **활동에 대한 결과** 표시를 선택한 경우 보고서에는 모든 서비스에 대한 모든 사용자 및 관리자 활동에 대한 항목이 포함됩니다. 감사 로그에 기록되는 작업/활동에 대한 설명은 감사 로그의 감사 로그 검색에서 감사된 활동 [탭을 Office 365.](search-the-audit-log-in-security-and-compliance.md)   <br/> Exchange 활동의 경우 이 속성은 실행된 cmdlet의 이름을 식별합니다.|모두|
|OrganizationId|조직의 GUID입니다.|모두|
|경로|액세스한 메시지가 있는 사서함 폴더의 이름입니다. 또한 이 속성은 메시지가 만들어지거나 복사/이동되는 폴더를 식별합니다.|Exchange(사서함 활동)|
|매개 변수|관리자 Exchange 작업의 경우 Operation 속성에서 식별된 cmdlet과 함께 사용된 모든 매개 변수의 이름과 값입니다.|Exchange(관리자 활동)|
|RecordType|레코드가 나타내는 작업의 유형입니다. 이 속성은 작업이 트리거된 서비스 또는 기능을 나타냅니다. 레코드 유형 목록 및 해당 ENUM 값(감사 레코드의 **RecordType** 속성에 표시되는 값)은 감사 로그 레코드 [형식 을 참조하세요.](/office/office-365-management-api/office-365-management-activity-api-schema#auditlogrecordtype)| 
|ResultStatus|**Operation** 속성에 지정된 작업이 성공적이지 여부를 나타냅니다.  <br/> Exchange 활동의 경우 값은 **True(성공)** 또는 False(실패)입니다. |모두  <br/>|
|SecurityComplianceCenterEventType|활동이 Microsoft 365 규정 준수 센터 나타냅니다. 모든 규정 준수 센터 활동의 값은 이 속성에 **대해 0입니다.**|보안 및 준수 센터|
|SharingType|리소스가 공유된 사용자에게 할당된 공유 권한의 유형입니다. 이 사용자는 **UserSharedWith 속성에서 식별됩니다.**|SharePoint|
|사이트|사용자가 액세스한 파일 또는 폴더가 있는 사이트의 GUID입니다.|SharePoint|
|SiteUrl|사용자가 액세스한 파일 또는 폴더가 있는 사이트의 URL입니다.|SharePoint|
|SourceFileExtension|사용자가 액세스한 파일의 파일 확장명입니다. 액세스한 개체가 폴더인 경우 이 속성은 비어 있습니다.|SharePoint|
|SourceFileName|사용자가 액세스한 파일 또는 폴더의 이름입니다.|SharePoint|
|SourceRelativeUrl|사용자가 액세스한 파일이 들어 있는 폴더의 URL입니다. **SiteURL,** **SourceRelativeURL** 및 **SourceFileName** 속성 값의 조합은 **ObjectID** 속성 값과 동일하며, 이는 사용자가 액세스하는 파일의 전체 경로 이름입니다.|SharePoint|
|제목|액세스한 메시지의 제목 줄입니다.|Exchange(사서함 활동)|
|TabType| 팀에서 추가, 제거 또는 업데이트된 탭 유형입니다. 이 속성에 사용할 수 있는 값은 다음입니다.  <br/><br/> **Excel 핀** - Excel 탭입니다.  <br/> **확장** - 모든 타사 및 타사 앱 클래스 일정, VSTS 및 양식과 같은 형식입니다.  <br/> **참고** - OneNote 탭입니다.  <br/> **Pdfpin** - PDF 탭입니다.  <br/> **Powerbi** - Power BI 탭입니다.  <br/> **Powerpointpin** - PowerPoint 탭.  <br/> **Sharepointfiles** - SharePoint 탭.  <br/> **웹 페이지** - 고정된 웹 사이트 탭.  <br/> **Wiki-tab** - Wiki 탭.  <br/> **Wordpin** - Word 탭|Microsoft Teams|
|대상|**Operation** 속성에서 식별된 작업이 수행된 사용자입니다. 예를 들어 게스트 사용자가 SharePoint 또는 Microsoft 팀에 추가된 경우 해당 사용자가 이 속성에 나열됩니다.|Azure Active Directory|
|TeamGuid|2013에 있는 팀의 Microsoft Teams.|Microsoft Teams|
|TeamName|팀의 이름입니다Microsoft Teams.|Microsoft Teams|
|UserAgent|사용자의 브라우저에 대한 정보입니다. 이 정보는 브라우저에서 제공됩니다.|SharePoint|
|UserDomain|작업을 수행한 사용자(배우)의 테넌트 조직에 대한 ID 정보입니다.|Azure Active Directory|
|UserId|Operation 속성에 지정된 작업을 수행한 사용자로 인해 레코드가 기록됩니다.  시스템 계정(예: SHAREPOINT\system 또는 NT AUTHORITY\SYSTEM)에서 수행한 활동에 대한 감사 레코드도 감사 로그에 포함됩니다. UserId 속성에 대한 또 다른 일반적인 값은 app@sharepoint. 이는 활동을 수행한 "사용자"가 사용자SharePoint 관리자 또는 서비스를 대신하여 조직 전체의 작업(예: SharePoint 사이트 또는 OneDrive 계정 검색)을 수행하는 데 필요한 권한이 있는 응용 프로그램입니다. 자세한 재용은 감사 레코드의 [앱\@sharepoint 사용자를 확인하세요](search-the-audit-log-in-security-and-compliance.md#the-appsharepoint-user-in-audit-records). |모두|
|UserKey|**UserID** 속성에 식별된 사용자의 대체 ID입니다. 예를 들어 이 속성은 사용자가 이 속성에 있는 사용자가 수행한 이벤트에 대한 PASSPORT PUID(고유 ID)로 SharePoint. 또한 이 속성은 시스템 계정이 수행한 다른 서비스 및 이벤트에서 발생하는 이벤트에 대한 **UserID** 속성과 동일한 값을 지정할 수도 있습니다.|모두|
|UserSharedWith|리소스를 공유한 사용자입니다. Operation 속성 값이 **SharingSet인** 경우 이 **속성이 포함됩니다.** 이 사용자는 보고서의 **공유한** 항목 열에도 나열됩니다.|SharePoint|
|UserType|작업을 수행한 사용자 유형입니다. 다음 값은 사용자 유형을 나타냅니다. <br/> <br/> **0** - 일반 사용자. <br/>**2** - 조직에 있는 Microsoft 365. <sup>1</sup> <br/>**3** - Microsoft 데이터 센터 관리자 또는 데이터 센터 시스템 계정. <br/>**4** - 시스템 계정. <br/>**5** - 응용 프로그램. <br/>**6** - 서비스 보안 주체.<br/>**7** - 사용자 지정 정책.<br/>**8** - 시스템 정책.|모두|
|버전|기록된 활동의 버전 **번호(Operation** 속성으로 식별)를 나타냅니다.|모두|
|워크로드|활동이 Microsoft 365 서비스입니다.|모두|
||||

> [!NOTE]
><sup>1</sup> Azure Active Directory 관련 이벤트의 경우 관리자의 값은 감사 레코드에 사용되지 않습니다. 관리자가 수행한 활동에 대한 감사 레코드는 일반 사용자(예: **UserType: 0)가** 활동을 수행한 것으로 표시됩니다. **UserID** 속성은 활동을 수행한 사용자(일반 사용자 또는 관리자)를 식별합니다.
