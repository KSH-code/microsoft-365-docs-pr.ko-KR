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
description: 이 문서에서는 Office 365 감사 로그 레코드에 대 한 결과를 내보낼 때 포함 되는 추가 속성에 대해 설명 합니다.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 250db03e7d330ed013909925b44f8d9843f1197d
ms.sourcegitcommit: 5480982967a90ca3060a59676a6b29155f2de861
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/19/2020
ms.locfileid: "49350704"
---
# <a name="detailed-properties-in-the-audit-log"></a>감사 로그의 자세한 속성

보안 & 준수 센터에서 감사 로그 검색 결과를 내보낼 때 검색 조건을 충족 하는 모든 결과를 다운로드할 수 있는 옵션이 있습니다. **Export results** \> **감사 로그 검색** 페이지에서 **모든 결과 다운로드** 를 선택 하 여이 작업을 수행 합니다. 자세한 내용은 [Search the audit log](search-the-audit-log-in-security-and-compliance.md)을 참조 하십시오.
  
 감사 로그 검색에 대 한 모든 결과를 내보낼 때 통합 된 감사 로그의 원시 데이터는 로컬 컴퓨터에 다운로드 되는 CSV (쉼표로 구분 된 값) 파일로 복사 됩니다. 이 파일에는 **Auditdata** 라는 열에 있는 각 감사 레코드의 추가 정보가 포함 됩니다. 이 열에는 감사 로그 레코드의 여러 속성에 대 한 다중 값 속성이 포함 되어 있습니다. 이 다중 값 속성의 각 **속성: 값** 쌍은 쉼표로 구분 됩니다. 
  
다음 표에서는 다중 속성 **Auditdata** 열에서 이벤트가 발생 하는 서비스에 따라 포함 되는 속성에 대해 설명 합니다. 이 속성 열이 있는 **Office 365 서비스** 는 해당 속성을 포함 하는 서비스 및 작업 유형 (사용자 또는 관리자)을 나타냅니다. 이러한 속성에 대 한 자세한 내용 또는이 항목에 나열 되지 않을 수 있는 속성에 대 한 자세한 내용은 [Management ACTIVITY API Schema](https://go.microsoft.com/fwlink/p/?LinkId=717993)를 참조 하십시오.
  
> [!TIP]
> Excel의 Power Query에서 JSON 변환 기능을 사용 하 여 각 속성에 자체 열이 포함 되도록 **Auditdata** 열을 여러 열로 분할할 수 있습니다. 이렇게 하면 하나 이상의 속성을 기준으로 정렬 및 필터링할 수 있습니다. 이 작업을 수행 하는 방법을 알아보려면 [감사 로그 기록 내보내기, 구성 및 보기](export-view-audit-log-records.md)를 참조 하세요. 
  
|**속성**|**설명**|**이 속성을 가진 Microsoft 365 서비스**|
|:-----|:-----|:-----|
|터|작업을 수행한 사용자 또는 서비스 계정입니다.|Azure Active Directory Domain Services|
|AddOnName|팀에서 추가, 제거 또는 업데이트 된 추가 기능의 이름입니다. Microsoft 팀의 추가 기능 유형은 bot, 커넥터 또는 탭입니다.|Microsoft Teams|
|AddOnType|팀에서 추가, 제거 또는 업데이트 된 추가 기능의 유형입니다. 다음 값은 추가 기능의 형식을 나타냅니다.  <br/> **1** -bot을 나타냅니다.<br/> **2** -커넥터를 나타냅니다.<br/> **3** -탭을 나타냅니다.|Microsoft Teams|
|AzureActiveDirectoryEventType|Azure Active Directory 이벤트의 유형입니다. 이벤트 유형을 나타내는 값은 다음과 같습니다.  <br/> **0** -계정 로그인 이벤트를 나타냅니다.<br/> **1** -Azure 응용 프로그램 보안 이벤트를 나타냅니다.|Azure Active Directory Domain Services|
|ChannelGuid|Microsoft 팀 채널의 ID입니다. 채널이 있는 팀이 **Teamname** 및 **teamname** 속성으로 식별 됩니다.|Microsoft Teams|
|ChannelName|Microsoft 팀 채널의 이름입니다. 채널이 있는 팀이 **Teamname** 및 **teamname** 속성으로 식별 됩니다.|Microsoft Teams|
|클라이언트|클라이언트 장치, 장치 OS 및 login 이벤트에 사용 되는 장치 브라우저 (예: Nokia Lumia 920;) Windows Phone 8; IE Mobile 11).|Azure Active Directory Domain Services|
|ClientInfoString|브라우저 버전, Outlook 버전 및 모바일 장치 정보와 같이 작업을 수행 하는 데 사용한 전자 메일 클라이언트에 대 한 정보|Exchange (사서함 활동)|
|ClientIP|활동을 로그할 때 사용 된 장치의 IP 주소입니다. IP 주소는 IPv4 또는 IPv6 주소 형식으로 표시됩니다.<br/><br/> 일부 서비스의 경우이 속성에 표시 되는 값은 사용자를 대신 하 여 서비스를 호출 하는 신뢰할 수 있는 응용 프로그램 (예: 웹 앱의 Office)의 IP 주소 이며, 활동을 수행한 사용자가 사용 하는 장치의 IP 주소가 아닙니다. <br/><br/>또한 Azure Active Directory 관련 이벤트에 대 한 관리 활동 (또는 시스템 계정에서 수행 하는 작업)에 대해 IP 주소가 기록 되지 않으며 ClientIP 속성 값은 `null` 입니다. |Azure Active Directory, Exchange, SharePoint|
|CreationTime|사용자가 활동을 수행 했을 때 UTC (협정 세계시)로 표시 되는 날짜와 시간입니다.|All|
|DestinationFileExtension|복사 하거나 이동할 파일의 파일 확장명입니다. 이 속성은 FileCopied 및 FileMoved 사용자 작업에만 표시 됩니다.|SharePoint|
|DestinationFileName|파일 이름이 복사 되거나 이동 됩니다. 이 속성은 FileCopied 및 FileMoved 작업에만 표시 됩니다.|SharePoint|
|DestinationRelativeUrl|파일을 복사 하거나 이동할 대상 폴더의 URL입니다. **SiteURL**, **DestinationRelativeURL** 및 **destinationfilename** 속성에 대 한 값의 조합이 복사 된 파일의 전체 경로 이름인 **ObjectID** 속성의 값과 같습니다. 이 속성은 FileCopied 및 FileMoved 사용자 작업에만 표시 됩니다.|SharePoint|
|EventSource|SharePoint에서 이벤트가 발생 한 것을 식별 합니다. 사용할 수 있는 값은 **SharePoint** 및 **objectmodel** 입니다.|SharePoint|
|ExternalAccess|Exchange 관리 활동의 경우, cmdlet이 조직의 사용자에 의해 실행 되었는지, Microsoft 데이터 센터 담당자나 데이터 센터 서비스 계정 또는 위임 된 관리자가 실행할지를 지정 합니다. 값이 **False** 이면 조직의 다른 사용자가 cmdlet을 실행 한 것입니다. **True** 값은 데이터 센터 직원, 데이터 센터 서비스 계정 또는 위임 된 관리자에 의해 cmdlet이 실행 되었음을 나타냅니다.  <br/> Exchange 사서함 활동의 경우 조직 외부의 사용자가 사서함에 액세스 했는지 여부를 지정 합니다.|Exchange|
|ExtendedProperties|Azure Active Directory 이벤트에 대 한 확장 된 속성입니다.|Azure Active Directory Domain Services|
|ID|보고서 항목의 ID입니다. ID는 보고서 항목을 고유 하 게 식별 합니다.|All|
|InternalLogonType|내부용으로 예약되어 있습니다.|Exchange (사서함 활동)|
|ItemType|액세스 하거나 수정한 개체의 유형입니다. 사용할 수 있는 값에는 **파일**, **폴더**, **웹**, **사이트**, **테 넌 트** 및 **documentlibrary** 가 있습니다.|SharePoint|
|LoginStatus|발생 했을 수 있는 로그인 실패를 확인 합니다.|Azure Active Directory Domain Services|
|LogonType|사서함 액세스 유형입니다. 다음 값은 사서함에 액세스 한 사용자의 유형을 나타냅니다.  <br/><br/> **0** -사서함 소유자를 나타냅니다.<br/> **1** -관리자를 나타냅니다.<br/> **2** -대리인을 나타냅니다. <br/>**3** -Microsoft 데이터 센터의 전송 서비스를 나타냅니다.<br/> **4** -Microsoft 데이터 센터의 서비스 계정을 나타냅니다. <br/>**6** -위임 된 관리자를 나타냅니다.|Exchange (사서함 활동)|
|MailboxGuid|액세스 한 사서함의 Exchange GUID입니다.|Exchange (사서함 활동)|
|MailboxOwnerUPN|액세스 한 사서함을 소유한 사용자의 전자 메일 주소입니다.|Exchange (사서함 활동)|
|구성원|팀에서 추가 되거나 제거 된 사용자를 나열 합니다. 다음 값은 사용자에게 할당된 역할 유형을 나타냅니다.  <br/><br/> **1** -소유자 역할을 나타냅니다.<br/> **2** - 구성원 역할을 나타냅니다.<br/> **3** - 게스트 역할을 나타냅니다. <br/><br/>구성원 속성에는 조직의 이름 및 구성원의 전자 메일 주소도 포함됩니다.|Microsoft Teams|
|ModifiedProperties (Name, NewValue, OldValue)|이 속성은 사이트 또는 사이트 모음 관리 그룹의 구성원으로 사용자를 추가 하는 등의 관리 이벤트에 포함 됩니다. 이 속성에는 수정 된 속성의 이름 (예: 사이트 관리자 그룹)과 수정한 속성의 새 값 (사이트 관리자로 추가한 사용자 및 수정한 개체의 이전 값)이 포함 됩니다.|모두 (관리 활동)|
|Id|Exchange 관리자 감사 로깅을 위해 cmdlet에 의해 수정 된 개체의 이름입니다.  <br/> SharePoint 작업의 경우 사용자가 액세스 하는 파일 또는 폴더의 전체 URL 경로 이름입니다.  <br/> Azure AD 활동의 경우 수정 된 사용자 계정의 이름입니다.|All|
|작업|사용자 또는 관리자 활동의 이름입니다. 이 속성의 값은 **활동** 드롭다운 목록에서 선택한 값에 해당 합니다. **모든 작업에 대해 결과 표시** 를 선택 하면 보고서에 모든 서비스에 대 한 모든 사용자 및 관리 활동에 대 한 항목이 포함 됩니다. 감사 로그에 기록 된 작업/작업에 대 한 설명은 [Office 365에서 감사 로그 검색](search-the-audit-log-in-security-and-compliance.md)의 감사 된 **작업** 탭을 참조 하십시오.  <br/> Exchange 관리 활동의 경우이 속성은 실행 된 cmdlet의 이름을 식별 합니다.|All|
|OrganizationId|조직의 GUID입니다.|All|
|경로|액세스 한 메시지가 있는 사서함 폴더의 이름입니다. 이 속성은 또한 메시지가 만들어지거나 복사/이동 되는 폴더를 식별 합니다.|Exchange (사서함 활동)|
|매개 변수|Exchange 관리 활동의 경우 Operation 속성에서 식별 된 cmdlet에 사용 된 모든 매개 변수의 이름과 값입니다.|Exchange (관리 활동)|
|RecordType|Record에서 지정한 작업의 유형입니다. 이 속성은 작업이 트리거된 서비스 또는 기능을 나타냅니다. 레코드 종류 및 해당 열거형 값의 목록 (감사 레코드에서 **RecordType** 속성에 표시 되는 값)에 대해서는 [감사 로그 레코드 종류](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-schema#auditlogrecordtype)를 참조 하십시오.| 
|ResultStatus|**작업** 속성에 지정 된 작업이 성공 했는지 여부를 나타냅니다.  <br/> Exchange 관리 활동의 경우이 값은 **True** (성공) 또는 **False** (failed) 중 하나입니다.|All  <br/>|
|SecurityComplianceCenterEventType|작업이 보안 & 준수 센터 이벤트 임을 나타냅니다. 모든 보안 & 준수 센터 작업에는이 속성에 대 한 값이 **0** 으로 포함 됩니다.|보안 및 준수 센터|
|SharingType|리소스를 공유 하는 사용자에 게 할당 된 공유 권한 유형입니다. 이 사용자는 **Usersharedwith** 속성에서 식별 됩니다.|SharePoint|
|사이트|사용자가 액세스 한 파일 또는 폴더가 있는 사이트의 GUID입니다.|SharePoint|
|SiteUrl|사용자가 액세스 한 파일 또는 폴더가 있는 사이트의 URL입니다.|SharePoint|
|SourceFileExtension|사용자가 액세스 한 파일의 파일 확장명입니다. 액세스 한 개체가 폴더인 경우이 속성은 비어 있습니다.|SharePoint|
|SourceFileName|사용자가 액세스 하는 파일 또는 폴더의 이름입니다.|SharePoint|
|SourceRelativeUrl|사용자가 액세스 한 파일이 들어 있는 폴더의 URL입니다. **SiteURL**, **SourceRelativeURL** 및 **sourcefilename** 속성의 값 조합은 사용자가 액세스 하는 파일의 전체 경로 이름인 **ObjectID** 속성의 값과 같습니다.|SharePoint|
|제목|액세스 한 메시지의 제목 줄입니다.|Exchange (사서함 활동)|
|TabType| 팀에서 추가, 제거 또는 업데이트 된 탭의 유형입니다. 이 속성에 사용할 수 있는 값은 다음과 같습니다.  <br/><br/> Excel **pin** -excel 탭입니다.  <br/> **내선** -모든 자사 및 타사 앱 예를 들면 클래스 일정, VSTS 및 양식 등이 있습니다.  <br/> **Notes** -OneNote 탭  <br/> **Pdfpin** -PDF 탭  <br/> **Powerbi** -Power BI 탭  <br/> **Powerpointpin** -PowerPoint 탭  <br/> **Sharepointfiles** -SharePoint 탭  <br/> **웹 페이지** -고정 된 웹 사이트 탭  <br/> **위 키-탭** -위 키 탭  <br/> **Wordpin** -Word 탭입니다.|Microsoft Teams|
|Target(대상)|작업 ( **Operation** ) 속성에서 식별 된 작업을 수행 하는 사용자입니다. 예를 들어 게스트 사용자가 SharePoint 또는 Microsoft 팀에 추가 된 경우에는 해당 사용자가이 속성에 나열 됩니다.|Azure Active Directory Domain Services|
|TeamGuid|Microsoft 팀의 팀 ID입니다.|Microsoft Teams|
|TeamName|Microsoft 팀의 팀 이름입니다.|Microsoft Teams|
|UserAgent|사용자 브라우저에 대 한 정보입니다. 이 정보는 브라우저에서 제공 됩니다.|SharePoint|
|UserDomain|작업을 수행한 사용자 (작업자)의 테 넌 트 조직에 대 한 id 정보입니다.|Azure Active Directory Domain Services|
|UserId|**작업** 속성에 지정 된 작업을 수행 하 여 레코드가 기록 되는 사용자입니다. 시스템 계정 (예: SHAREPOINT\system 또는 NT 권한 \ 컴퓨터)에서 수행 된 작업에 대 한 감사 레코드는 감사 로그에도 포함 됩니다. UserId 속성의 또 다른 일반적인 값은 app@sharepoint입니다. 이는 해당 활동을 수행한 "사용자"가 SharePoint에서 사용자, 관리자 또는 서비스를 대신 하 여 조직 전체 작업을 수행 하는 데 필요한 사용 권한이 있는 응용 프로그램 인지를 나타냅니다. 자세한 재용은 감사 레코드의 [앱\@sharepoint 사용자를 확인하세요](search-the-audit-log-in-security-and-compliance.md#the-appsharepoint-user-in-audit-records). |All|
|UserKey|**UserID** 속성에서 식별 된 사용자의 대체 ID입니다. 예를 들어이 속성은 SharePoint의 사용자가 수행한 이벤트에 대 한 passport 고유 ID (PUID)로 채워집니다. 또한이 속성은 다른 서비스에서 발생 하는 이벤트에 대 한 **UserID** 속성과 동일한 값과 시스템 계정에서 수행 하는 이벤트를 지정할 수 있습니다.|All|
|UserSharedWith|리소스를 공유한 사용자입니다. 이 속성은 **Operation** 속성의 값이 **SharingSet** 인 경우에 포함 됩니다. 이 사용자는 보고서의 **공유** 됨 열에도 표시 됩니다.|SharePoint|
|UserType|작업을 수행한 사용자의 유형입니다. 다음 값은 사용자 형식을 나타냅니다. <br/> <br/> **0** -일반 사용자입니다. <br/>**2** -Microsoft 365 조직의 관리자입니다. <sup>1</sup> <br/>**3** -Microsoft 데이터 센터 관리자 또는 데이터 센터 시스템 계정입니다. <br/>**4** -시스템 계정입니다. <br/>**5** -응용 프로그램 <br/>**6** -서비스 사용자입니다.<br/>**7** -사용자 지정 정책<br/>**8** -시스템 정책.|All|
|Version|기록 된 작업의 버전 번호 ( **Operation** 속성으로 식별 됨)를 나타냅니다.|All|
|워크로드|활동이 발생 한 Microsoft 365 서비스입니다.|All|
||||

> [!NOTE]
><sup>1</sup> Azure Active Directory 관련 이벤트의 경우 감사 레코드에서 관리자의 값을 사용 하지 않습니다. 관리자가 수행 하는 작업에 대 한 감사 레코드는 일반 사용자 (예 **: UserType, 0**)가 활동을 수행한 것을 나타냅니다. **UserID** 속성은 활동을 수행한 사람 (일반 사용자 또는 관리자)을 식별 합니다.<br/>

위에서 설명한 속성은 특정 이벤트의 세부 정보를 볼 때 **자세한 정보** 를 클릭 하면 표시 되기도 합니다.
  
![감사 로그 이벤트 레코드의 자세한 속성을 보려면 추가 정보를 클릭합니다.](../media/6df582ae-d339-4735-b1a6-80914fb77a08.png)
