---
title: Microsoft Cloud 독일의 마이그레이션에 대 한 추가 환경 정보
ms.author: andyber
author: andybergen
manager: laurawi
ms.date: 12/01/2020
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
f1.keywords:
- CSH
ms.custom:
- Ent_TLGs
description: '요약: Microsoft cloud 전라남도 (Microsoft 클라우드 독일)에서 새 독일어 데이터 센터 지역의 Office 365 서비스로 이동할 때 추가 고객 환경 정보를 제공 합니다.'
ms.openlocfilehash: b282a12966e7a6dc8a1a331409834322c5087a10
ms.sourcegitcommit: 38d828ae8d4350ae774a939c8decf30cb36c3bea
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/02/2020
ms.locfileid: "49551878"
---
# <a name="additional-experience-information-for-the-migration-from-microsoft-cloud-deutschland"></a>Microsoft Cloud 독일의 마이그레이션에 대 한 추가 환경 정보 

다음 섹션에서는 고객 환경에 대 한 추가 정보를 제공 합니다.

## <a name="services"></a>서비스

### <a name="azure-ad"></a>Azure AD

| 단계 | 설명 | 적용 대상 | 영향 |
|:-------|:-----|:-------|:-------|
| Microsoft Cloud 독일의 Azure AD 테 넌 트가 Office 365 서비스에 복사 됩니다. | Azure AD가 테 넌 트를 Office 365 서비스에 복사 합니다. 테 넌 트 및 사용자 식별자는 보존 됩니다. Azure AD 서비스 호출이 Microsoft Cloud 독일에서 Office 365 서비스로 리디렉션되어 서비스에 대해 투명 하 게 처리 됩니다. | 모든 Office 고객 | -일반 데이터 보호 규정 (GDPR) 향후 요청을 위해 Azure 관리 포털에서 d m (데이터 주체 요청)이 실행 됩니다. Microsoft Cloud 독일에 상주 하는 모든 레거시 또는 고객이 진단 데이터는 30 일이 경과 하거나 그 이전에 삭제 됩니다. <br><br> -AD FS (Active Directory Federation Services)와 함께 페더레이션 인증을 사용 하는 고객은 마이그레이션 중 온-프레미스 Active Directory의 모든 인증에 사용 되는 발급자 Uri를 변경 하지 않아야 합니다. 발급자 Uri를 변경 하면 도메인의 사용자에 대 한 인증 오류가 발생 합니다. 발급자 Uri는 AD FS에서 직접 변경 하거나 도메인을 _관리_ 에서 _페더레이션_ 으로 또는 그 반대로 변환할 수 있습니다. 고객은 마이그레이션된 Azure AD 테 넌 트에서 페더레이션 도메인을 추가, 제거 또는 변환 하지 않는 것이 좋습니다. 발급자 Uri는 마이그레이션이 완전히 완료 된 후 변경 될 수 있습니다. <br><br> -Microsoft Authenticator를 사용 하는 MFA (multi-factor authentication) 요청은 테 넌 트가 Office 365 서비스에 복사 되는 동안 사용자 ObjectID (GUID)로 표시 됩니다. MFA 요청은이 표시 동작에도 불구 하 고 예상 대로 수행 됩니다.  Office 365 서비스 끝점을 사용 하 여 활성화 된 Microsoft 인증자 계정에 UPN (사용자 계정 이름)이 표시 됩니다.  Microsoft Cloud 독일 endpoints를 사용 하 여 추가 된 계정에는 사용자 ObjectID가 표시 되지만 Microsoft 클라우드 독일 및 Office 365 서비스 끝점에서 모두 작동 합니다.  |
| 글로벌 STS 서비스를 가리키도록 온-프레미스 인증을 설정 합니다. | 이렇게 하면 하이브리드 온-프레미스 환경을 대상으로 하는 Exchange 가용성 요청에 대해 Microsoft Cloud 독일로 마이그레이션하는 사용자의 요청이 온-프레미스 서비스에 액세스할 수 있도록 인증 됩니다. 마찬가지로 온-프레미스에서 Office 365 서비스 끝점으로의 요청이 인증을 보장 합니다. | 하이브리드 (온-프레미스) 배포를 사용 하는 Exchange Online 고객 | Azure AD 마이그레이션이 완료 되 면 하이브리드 (온-프레미스 Exchange) 토폴로지의 관리자는 Office 365 서비스에 대 한 새 인증 서비스 끝점을 추가 해야 합니다. Exchange PowerShell에서이 명령을 사용 하 여 `<TenantID>` 조직의 테 넌 트 ID ( **Azure Active Directory** 의 azure portal에 있음)로 대체 합니다. <br><br> - `New-AuthServer GlobalMicrosoftSts -AuthMetadataUrl https://accounts.accesscontrol.windows.net/<TenantId>/metadata/json/1` <br> <br> 이 작업을 완료 하지 못하면 하이브리드 약속 있음/없음 요청이 Microsoft Cloud 독일에서 Office 365 서비스로 마이그레이션된 사서함 사용자에 대 한 정보를 제공 하지 못할 수 있습니다.  |
| Azure 리소스 마이그레이션 | Office 365 및 Azure 리소스 (예: 네트워킹, 계산, 저장소)를 사용 하는 고객은 Office 365 서비스 인스턴스에 리소스 마이그레이션을 수행 합니다. 이 마이그레이션은 고객에 게 책임이 있습니다. 메시지 센터 게시물이 시작 신호를 받게 됩니다. Office 365 서비스 환경에서 Azure AD 조 직을 종료 하기 전에 마이그레이션을 완료 해야 합니다. | Azure 고객 | Azure 마이그레이션에 대 한 자세한 내용은 azure 마이그레이션 playbook, [Azure 전라남도 마이그레이션 지침 개요](https://docs.microsoft.com/azure/germany/germany-migration-main)를 참조 하세요. |
|||||

<!--
[Reference: Experience][Data Protection] Experience][
[Reference: Experience][Federation] 
[Reference: Experience][MFA]  


[Reference: Experience – Post Migration][Hybrid]    
        

[Reference: Experience – During Migration] [Azure] 
-->

### <a name="exchange-online"></a>Exchange Online

**UserPhoto** 를 사용 하는 경우:

| 단계 | 설명 | 적용 대상 | 영향 |
|:-------|:-----|:-------|:-------|
| 기존 조직 설정에 새 독일 지역이 추가 되 고 사서함이 Office 365 서비스로 이동 됩니다. | Exchange Online 구성은 새 로컬 이동 독일어 지역에 전환 조직에 추가 합니다. 이 Office 365 서비스 지역이 기본값으로 설정 되어 내부 부하 분산 서비스에서 Office 365 서비스의 해당 기본 지역으로 사서함을 다시 배포할 수 있도록 합니다. 이 전환에서는 두 사용자 (독일 또는 Office 365 서비스)가 동일한 조직에 있고 두 URL을 모두 사용할 수 있습니다. |  Exchange Online | 사용자 사서함이 마이그레이션 되었지만 관리자 사서함이 마이그레이션되지 않은 경우 또는 그 반대의 경우에는 관리자가 PowerShell cmdlet을 사용 하 여 **설정 된 UserPhoto** 를 실행할 수 없게 됩니다. 이 경우 관리자는 `ConnectionUri` 다음 구문을 사용 하 여 연결 설정 중에 추가 문자열을 전달 해야 합니다. <br><br> `https://outlook.office.de/PowerShell-LiveID?email=<user_email>` <br><br> 여기서 `<user_email>` 는 **userphoto** 를 사용 하 여 해당 사진을 변경 해야 하는 사용자의 전자 메일 ID에 대 한 자리 표시자입니다. |
|||||

<!--
[Reference: Experience][Exchange Online]  [if using Set-UserPhoto] 
-->  

하이브리드, 온-프레미스 배포를 사용 하는 경우:

| 단계 | 설명 | 적용 대상 | 영향 |
|:-------|:-----|:-------|:-------|
|사서함의 온 보 딩 또는 오프 보 딩 이동을 중지 하거나 삭제 합니다.  | 이렇게 하면 이동 요청이 오류와 함께 실패 하지 않습니다. | 하이브리드 (온-프레미스) 배포를 사용 하는 Exchange Online 고객 | 필수 작업입니다. 이렇게 하지 않으면 서비스 또는 소프트웨어 클라이언트에 오류가 발생할 수 있습니다. |
|||||

<!--
[Reference: Experience][Hybrid] 
--> 


### <a name="dynamics"></a>Dynamics

| 단계 | 설명 | 적용 대상 | 영향 |
|:-------|:-----|:-------|:-------|
| Microsoft Dynamics 리소스 | Microsoft Dynamics 고객은 엔지니어링 또는 FastTrack을 사용 하 여 Office 365 services 인스턴스로 Dynamics 전환 합니다. * | Microsoft Dynamics 365 고객 | -마이그레이션 후 관리자가 조직의 유효성을 검사 합니다. <br><br> -관리자가 워크플로를 필요에 따라 수정 합니다. <br><br> -관리자가 적절 하 게 AdminOnly 모드를 해제 합니다. <br><br> -관리자가 해당 조직 유형을 적절 하 게 _샌드박스_ 에서 변경 합니다. <br><br> -인스턴스 (org)에 액세스 하기 위해 새 URL의 최종 사용자에 게 알립니다. <br><br> -새 끝점 URL에 대 한 모든 인바운드 연결을 업데이트 합니다. <br><br> -전환 중에 사용자가 Dynamics 서비스를 사용할 수 없게 됩니다. <br><br> -사용자는 각 조직에서 마이그레이션한 후에 조직 상태 및 기능의 유효성을 검사 해야 합니다.  |
|||||

\* (i) Microsoft Dynamics 365를 사용 하는 고객은 마이그레이션 프로세스에서 정의 된이 마이그레이션 시나리오에서 조치를 취해야 합니다. (ii) 고객이 작업을 수행 하는 데 실패 하는 경우 Microsoft가 마이그레이션을 완료할 수 없음을 의미 합니다. (iii) Microsoft가 고객의 inaction 인해 마이그레이션을 완료할 수 없는 경우 고객의 구독은 2021 년 10 월 29 일에 만료 됩니다. 


### <a name="power-bi"></a>Power BI

| 단계 | 설명 | 적용 대상 | 영향 |
|:-------|:-----|:-------|:-------|
| Power BI 리소스 마이그레이션 | Microsoft Power BI를 사용 하는 고객은 Power BI를 Office 365 services 인스턴스로 전환 하도록 기존 PBI 마이그레이션 도구를 수동으로 트리거하는 엔지니어링 또는 FastTrack에 참여 합니다.\*\* | Microsoft Power BI 고객 | -다음 Power BI 항목은 전환 _되지_ 않으며 다시 만들어야 합니다. <br><br> -실시간 데이터 집합 (예: 스트리밍 또는 푸시 데이터 집합) <br> -Power BI 온-프레미스 데이터 게이트웨이 구성 및 데이터 원본 <br> -실시간 데이터 집합을 기반으로 작성 된 보고서는 마이그레이션 후에도 사용할 수 없으며 다시 만들어야 합니다. <br><br> -전환 중에 사용자가 Power BI 서비스를 사용할 수 없게 됩니다. 서비스를 사용할 수 없다는 것은 24 시간 이상 이어야 합니다. <br><br> -마이그레이션 후에는 사용자가 Power BI 서비스를 사용 하 여 데이터 원본 및 온-프레미스 데이터 게이트웨이를 다시 구성 해야 합니다.  이 경우에는 사용자가 이러한 데이터 원본을 사용 하 여 이러한 데이터 원본에 대해 예약 된 새로 고침 및/또는 직접 쿼리를 수행할 수 없습니다. <br><br> -용량과 프리미엄 작업 영역을 마이그레이션할 수 없습니다. 고객은 마이그레이션 전에 모든 용량을 삭제 해야 하며 마이그레이션 후에 다시 만들어야 합니다. 필요에 따라 작업 영역을 다시 용량으로 이동 합니다.  |
|||||

\*\* (i) Microsoft Power BI를 사용 하는 고객은 마이그레이션 프로세스에 정의 된이 마이그레이션 시나리오에서 조치를 취해야 합니다. (ii) 고객이 작업을 수행 하는 데 실패 하는 경우 Microsoft가 마이그레이션을 완료할 수 없음을 의미 합니다. (iii) Microsoft가 고객의 inaction 인해 마이그레이션을 완료할 수 없는 경우 고객의 구독은 2021 년 10 월 29 일에 만료 됩니다. 


### <a name="office-apps"></a>Office 앱

| 단계 | 설명 | 적용 대상 | 영향 |
|:-------|:-----|:-------|:-------|
| Office 클라이언트를 시작 하는 동안 클라이언트, Office Online에서 Azure AD는 Office 365 서비스를 가리키도록 테 넌 트 범위를 마무리 합니다.<!--v-gmoor: What?--> | 이 구성 변경은 Office 클라이언트에서 Office 365 서비스 끝점을 업데이트 하 고 가리킬 수 있도록 합니다. | 모든 Office 고객 | -고객 소유의 DNS에서 MSOID CName을 제거 합니다 (있는 경우). <br><br> -사용자에 게 _모든_ office 앱을 닫고 다시 로그인 (또는 클라이언트를 다시 시작 하 고 로그인 해야 함) 하 여 office 클라이언트에서 변경 내용을 선택할 수 있도록 합니다. <br><br> -사용자에 게 알리거나 지원 센터 직원에 게 사용자에 게 알림-72 시간 이내에 Office 앱을 다시 정품 인증 하 라는 메시지를 표시 하는 Office 배너가 표시 *될 수 있습니다* . <br><br> -개인 컴퓨터의 모든 Office 응용 프로그램을 종료 해야 하 고 사용자가 로그 아웃 한 다음 다시 로그인 해야 합니다. 노란색 정품 인증 표시줄에서 로그인 하 여 Office 365 서비스에 대해 다시 활성화 합니다. <br><br> -공유 컴퓨터에는 개인 컴퓨터와 유사한 작업이 필요 하며 특별 한 절차가 필요 하지 않습니다. <br><br> -모바일 장치에서는 사용자가 앱에서 로그 아웃 하 고 닫은 다음 다시 로그인 해야 합니다. |
|||||

<!--
[Reference: Experience][Office Apps]
--> 

## <a name="during-migration"></a>마이그레이션 진행 중


### <a name="exchange-online"></a>Exchange Online

EDiscovery:

| 단계 | 설명 | 적용 대상 | 영향 |
|:-------|:-----|:-------|:-------|
| 마이그레이션 중에 eDiscovery 검색은 SharePoint Online, 비즈니스용 OneDrive 및 마이그레이션된 Exchange Online 위치에 대해 실패 하거나 결과가 반환 됩니다. | 마이그레이션 중에 고객은 보안 & 준수 센터에서 콘텐츠 검색을 포함 하 여 사례, 보존, 검색 및 내보내기를 계속 만들 수 있습니다.  그러나 SharePoint Online, 비즈니스용 OneDrive 및 마이그레이션된 Exchange Online 위치에 대 한 검색은 0 결과를 반환 하거나 오류를 생성 합니다. 업데이트 관리에 대 한 내용은 _영향_ 열을 참조 하십시오. | EDiscovery를 사용 하는 모든 고객 |  마이그레이션 중에 검색 결과가 0 이거나 오류가 반환 되는 경우에는 SharePoint Online에 대해 다음 작업을 수행 하세요. <br><br>  [Onedrive 또는 sharepoint에서 다운로드 파일 및 폴더](https://support.office.com/article/download-files-and-folders-from-onedrive-or-sharepoint-5c7397b7-19c7-4893-84fe-d02e8fa5df05)의 지침을 수행 하 여 SharePoint Online/비즈니스용 OneDrive 사이트에서 직접 사이트를 다운로드 합니다. 이 방법을 사용 하려면 사이트에 대 한 SharePoint Online 관리자 권한 또는 읽기 전용 권한이 필요 합니다. <br><br> [Onedrive 또는 SharePoint에서 다운로드 파일 및 폴더](https://support.office.com/article/download-files-and-folders-from-onedrive-or-sharepoint-5c7397b7-19c7-4893-84fe-d02e8fa5df05)에 설명 된 대로 제한이 초과 되는 경우 고객은 [sharepoint 및 팀 파일을 컴퓨터와 동기화](https://support.office.com/article/sync-sharepoint-files-with-the-new-onedrive-sync-app-6de9ede8-5b6e-4503-80b2-6190f3354a88)하는 지침을 따라 비즈니스용 OneDrive 동기화 클라이언트를 사용할 수 있습니다. <br><br> -Exchange Online <br><br> - [Exchange Server의 원본 위치 eDiscovery](https://docs.microsoft.com/Exchange/policy-and-compliance/ediscovery/ediscovery) |
|||||

<!--
[Reference: Experience – During Migration][ [eDiscovery]
-->          


### <a name="sharepoint-online"></a>SharePoint Online

| 단계 | 설명 | 적용 대상 | 영향 |
|:-------|:-----|:-------|:-------|
| SharePoint 및 OneDrive가 전환 되었습니다. | 이 단계에서는 SharePoint 및 OneDrive가 Microsoft Cloud 독일에서 Office 365 서비스로 마이그레이션됩니다. 기존 Microsoft Cloud 독일 Url은 보존 됩니다 ( `contoso.sharepoint.de` ). Microsoft Cloud 독일 또는 Office 365 services에서 발급 한 토큰은 전환 중에 유효 합니다. | SharePoint 고객 | Inflight SharePoint 2013 마이그레이션 중에 워크플로가 중단 되며 마이그레이션 후에 다시 게시 해야 합니다. |
|||||

<!--
[Reference: Experience – During Migration][ [SPO]
-->  

### <a name="skype-for-business-online"></a>비즈니스용 Skype Online

| 단계 | 설명 | 적용 대상 | 영향 |
|:-------|:-----|:-------|:-------|
| 비즈니스용 Skype를 팀으로 마이그레이션 | 기존 비즈니스용 Skype 고객은 유럽의 Office 365 서비스로 마이그레이션하고 Office 365 서비스의 독일 지역에서 Microsoft 팀으로 전환 됩니다. | 비즈니스용 Skype 고객 |  PowerShell은 테 넌 트 및 사용자에 대 한 설정 및 정책을 관리 하는 데 사용 됩니다. PowerShell 세션에 연결 하는 경우 다음을 추가 합니다. <br><br> `-OverridePowershellUri "https://admin4E.online.lync.com/OcsPowershellOAuth"` |
|||||

<!--
[Reference: Experience – During Migration][ [SfBO]
-->  


## <a name="post-migration"></a>마이그레이션 후

### <a name="azure-ad"></a>Azure AD

하이브리드:

| 단계 | 설명 | 적용 대상 | 영향 |
|:-------|:-----|:-------|:-------|
| Azure AD Connect를 업데이트 합니다. | Azure로의 잘라내기를 완료 한 후에는 조직이 Office 365 서비스를 완전히 사용 하며 Microsoft 클라우드 독일 더 이상 연결 되지 않습니다. 이때 고객은 델타 동기화 프로세스가 완료 되었는지 확인 한 후에 해당 `AzureInstance` 레지스트리 경로에서 문자열 값 3 (Microsoft 클라우드 독일)을 0으로 변경 해야 합니다 `Computer\HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Azure AD Connect` . | 하이브리드 Azure AD-연결 된 조직 | 레지스트리 키의 값 `AzureInstance` 을 변경 합니다. 이렇게 하지 않으면 Microsoft Cloud 독일 endpoints를 더 이상 사용할 수 없게 되 면 개체가 동기화 되지 않는 것입니다. |
|||||

<!--
[Reference: Experience – Post Migration][Hybrid]
--> 

페더레이션 인증의 경우:

| 단계 | 설명 | 적용 대상 | 영향 |
|:-------|:-----|:-------|:-------|
| Microsoft Cloud 독일 AD FS에서 신뢰 당사자 트러스트를 제거 합니다. | Azure로의 잘라내기를 완료 한 후에는 조직이 Office 365 서비스를 완전히 사용 하며 Microsoft 클라우드 독일 더 이상 연결 되지 않습니다. 이 시점에서 고객은 Microsoft Cloud 독일 끝점에 대 한 신뢰 당사자 트러스트를 제거 해야 합니다. Azure AD를 Id 공급자로 사용할 때 Microsoft Cloud 독일 endpoints를 가리키는 응용 프로그램이 없는 경우에만이 작업을 수행할 수 있습니다 (IdP). | 페더레이션 인증 조직 | 없음 |
|||||

<!--
[Reference: Experience – Post Migration][Federated]
-->             

Azure AD의 경우:

| 단계 | 설명 | 적용 대상 | 영향 |
|:-------|:-----|:-------|:-------|
| 원래 요청이 승인 되지 않은 경우 마이그레이션 전에 지난 30 일 동안 Azure AD 그룹 가입 요청을 다시 요청 해야 합니다. | 마이그레이션 전에 지난 30 일 이내에 요청이 승인 되지 않은 경우 최종 사용자 고객은 액세스 패널을 사용 하 여 Azure AD 그룹에 가입 하는 요청을 제출 해야 합니다. | 마이그레이션 전 Azure AD 그룹 승인 요청이 지난 30 일 전에 승인 되지 않은 최종 사용자 |  최종 사용자의 경우: <ol><li>[Access 패널로](https://account.activedirectory.windowsazure.com/r#/joinGroups)이동 합니다.</li><li>마이그레이션 전 30 일 이내에 구성원 승인이 보류 된 Azure AD 그룹을 찾습니다.</li><li>Azure AD 그룹에 다시 참가 하도록 요청 합니다.</li></ol> 마이그레이션을 수행한 후에 다시 요청 하지 않으면 마이그레이션을 승인할 수 없도록 30 일 이내에 활성화 되는 그룹에 참가 하도록 요청 합니다. |
|||||

<!--
[Reference: Experience – Post Migration][Azure AD]
--> 

DNS:

| 단계 | 설명 | 적용 대상 | 영향 |
|:-------|:-----|:-------|:-------|
| Office 365 서비스 끝점에 대 한 온-프레미스 DNS 서비스를 업데이트 합니다. | Office 365 독일을 가리키는 고객 관리 DNS 항목은 Office 365 서비스 끝점을 가리키도록 업데이트 해야 합니다. | 모든 Office 고객 | 필수 작업입니다. 이렇게 하지 않으면 서비스 또는 소프트웨어 클라이언트에 오류가 발생할 수 있습니다. |
|||||

<!--
 [Reference: Experience – Post Migration][DNS]
-->

Office 365 서비스 끝점에 대 한 타사 서비스에 대해 다음을 수행 합니다.

| 단계 | 설명 | 적용 대상 | 영향 |
|:-------|:-----|:-------|:-------|
| Office 365 서비스 끝점에 대 한 업데이트 파트너 및 타사 서비스를 제공 합니다. | -Office 365 독일을 가리키는 타사 서비스 및 파트너는 Office 365 서비스 끝점을 가리키도록 업데이트 해야 합니다. 예: 공급 업체 및 파트너와의 맞춤 (사용 가능한 경우) 응용 프로그램의 갤러리 앱 버전에 다시 등록 합니다. <br><br> -Graph API를 활용 하는 모든 사용자 지정 응용 프로그램에서 `graph.microsoft.de` 를 가리킵니다 `graph.microsoft.com` . 또한 변경 된 끝점을 포함 하는 다른 Api를 사용 하는 경우 업데이트 해야 합니다. <br><br> -모든 타사 엔터프라이즈 응용 프로그램이 전 세계 끝점으로 리디렉션하도록 변경 합니다.  | 모든 Office 고객 | 필수 작업입니다. 이렇게 하지 않으면 서비스 또는 소프트웨어 클라이언트에 오류가 발생할 수 있습니다. |
|||||

<!--
 [Reference: Experience – Post Migration][]
--> 

### <a name="exchange-online"></a>Exchange Online

하이브리드 Exchange 구성을 사용 하는 경우:

| 단계 | 설명 | 적용 대상 | 영향 |
|:-------|:-----|:-------|:-------|
| Office 365 서비스에 대해 하이브리드 구성 마법사 (HCW)를 다시 실행 합니다. | 기존 HCW 구성은 Microsoft 클라우드 독일을 지원 하기 위한 것입니다. Exchange 서비스 마이그레이션이 완료 되 면 온-프레미스 구성을 Microsoft Cloud 독일에서 분리 합니다. | 하이브리드 배포를 실행 하는 Exchange Online 고객 | 필요한 작업입니다. 이렇게 하지 않으면 서비스 또는 소프트웨어 클라이언트에 오류가 발생할 수 있습니다. Exchange 사서함 마이그레이션을 시작 하기 전에 (5 일 이상 주의)에는 클라이언트에 게 해당 사서함의 온 보 딩 또는 오프 보 딩 이동이 중지 되 고 삭제 될 것을 알립니다.  그렇지 않으면 이동 요청에서 오류가 표시 됩니다. <br><br> -Exchange 사서함 마이그레이션이 완료 되 면 클라이언트에 게 온 보 딩 및 오프 보 딩 이동을 계속할 수 있음을 알립니다. <br> Microsoft Cloud 독일 to Office 365 services에서 Exchange를 마이그레이션하는 동안 **MigrationServerAvailabiilty** 를 실행 하면 PowerShell cmdlet이 작동 하지 않을 수 있습니다. 그러나 마이그레이션이 완료 된 후에는 제대로 작동 합니다. <br><br> 사서함이 마이그레이션된 후에 클라이언트에서 자격 증명 또는 권한 부여와 관련 된 문제가 발생 하는 경우 사용자는 `Set-MigrationEndpoint endpointName -Credential $(Get-Credential)` Exchange 제어판 (ECP)을 사용 하 여 또는 동일한 방식으로 설정 하 여 마이그레이션 끝점에 온-프레미스 관리자 자격 증명을 다시 입력할 수 있습니다.  |

<!--
[Reference: Experience – Post Migration][Hybrid]  
[Reference: Experience – Post Migration][Exchange Online]
--> 

EDiscovery:

| 단계 | 설명 | 적용 대상 | 영향 |
|:-------|:-----|:-------|:-------|
|  모든 SharePoint Online, 비즈니스용 OneDrive 및 Exchange Online 위치는 SCC (보안 및 준수 센터)와 함께 마이그레이션됩니다. | 모든 eDiscovery 활동은 전 세계의 테 넌 트에서 실행 해야 합니다. 검색은 이제 100% 완료 됩니다.  오류나 오류가 있으면 일반 지원 채널을 따라야 합니다. | EDiscovery를 사용 하는 모든 고객 | 없음 |
| 마이그레이션 전 단계 중에 만들어진 조직 차원의 보존 정책 제거 | 고객은 고객의 마이그레이션 전 작업을 수행 하는 동안 만들어진 조직 차원의 보존 정책을 제거할 수 있습니다. | 마이그레이션 전 단계의 일부로 보존 정책을 적용 한 모든 고객 | 없음 |
|||||

<!--
 [Reference: Experience – Post Migration][ [eDiscovery]             

[Reference: Experience – Post Migration][ [eDiscovery]
-->             

### <a name="sharepoint-online"></a>SharePoint Online

| 단계 | 설명 | 적용 대상 | 영향 |
|:-------|:-----|:-------|:-------|
| SharePoint 2013 워크플로를 다시 게시 합니다. | 마이그레이션 전 작업에서는 SharePoint 2013 워크플로 수를 줄였습니다. 이제 마이그레이션이 완료 되 면 고객은 워크플로를 다시 게시할 수 있습니다. | 모든 Office 고객 | 필수 작업입니다. 이 작업을 수행 하지 않으면 사용자의 혼동이 나 지원 센터 전화가 생길 수 있습니다. |
| Outlook을 통해 항목 공유 | Outlook을 통해 항목을 공유 하는 작업은 테 넌 트가 끝난 후 더 이상 작동 하지 않습니다. | SharePoint Online 및 비즈니스용 OneDrive | -SharePoint Online 및 비즈니스용 OneDrive에서는 Outlook을 통해 항목을 공유할 수 있습니다. Outlook 단추를 누르면 공유 가능한 링크가 만들어져 Outlook Web App에서 새 메시지로 푸시됩니다. <br><br> -테 넌 트를 시작한 후에는이 공유 방법이 작동 하지 않습니다. 이는 알려진 문제입니다. 그러나이 Outlook 기능은 더 이상 사용할 수 없기 때문에 문제를 해결 하는 작업은 계속 진행이 롤아웃 될 때까지 계획 되지 않습니다. |

<!--
 [Reference: Experience – Post Migration][ [SPO]
-->

## <a name="next-step"></a>다음 단계

[마이그레이션 단계 작업 및 영향 이해](ms-cloud-germany-transition-phases.md)

## <a name="more-information"></a>추가 정보

시작 하기:

- [Microsoft Cloud 독일에서 새 독일어 데이터 센터 지역의 Office 365 서비스로 마이그레이션](ms-cloud-germany-transition.md)
- [Microsoft Cloud Deutschland 마이그레이션 지원](https://aka.ms/germanymigrateassist)
- [마이그레이션에 대해 옵트인하는 방법](ms-cloud-germany-migration-opt-in.md)
- [마이그레이션 중의 고객 환경](ms-cloud-germany-transition-experience.md)

전환을 통해 이동 하는 경우:

- [마이그레이션 단계 작업 및 영향](ms-cloud-germany-transition-phases.md)
- [추가 사전 작업](ms-cloud-germany-transition-add-pre-work.md)
- [서비스](ms-cloud-germany-transition-add-general.md), [장치](ms-cloud-germany-transition-add-devices.md), [환경](ms-cloud-germany-transition-add-experience.md)및 [AD FS](ms-cloud-germany-transition-add-adfs.md)에 대 한 추가 정보

클라우드 앱:

- [Dynamics 365 마이그레이션 프로그램 정보](https://aka.ms/d365ceoptin)
- [Power BI 마이그레이션 프로그램 정보](https://aka.ms/pbioptin)
- [Microsoft Teams 업그레이드 시작하기](https://aka.ms/SkypeToTeams-Home)
