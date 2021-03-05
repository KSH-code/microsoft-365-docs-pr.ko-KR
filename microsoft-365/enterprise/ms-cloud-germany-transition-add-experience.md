---
title: 마이그레이션 단계 도이클란드 Microsoft 클라우드에서 마이그레이션에 대한 작업 및 영향(고급)
ms.author: andyber
author: andybergen
manager: laurawi
ms.date: 12/11/2020
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
description: '요약: 독일 Microsoft 클라우드(도이치란드 Microsoft 클라우드)에서 새 독일 데이터 센터 지역의 Office 365 서비스로 이동하는 경우의 추가 고객 환경 정보입니다.'
ms.openlocfilehash: 26db69583bac68723d5d57b07abb856c8190d9b1
ms.sourcegitcommit: 375168ee66be862cf3b00f2733c7be02e63408cf
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/04/2021
ms.locfileid: "50454470"
---
# <a name="migration-phases-actions-and-impacts-for-the-migration-from-microsoft-cloud-deutschland-advanced"></a>마이그레이션 단계 도이클란드 Microsoft 클라우드에서 마이그레이션에 대한 작업 및 영향(고급) 

독일 Microsoft 클라우드에서 Microsoft Office 365 서비스의 독일 지역으로 테넌트 마이그레이션은 단계 집합 및 각 워크로드에 대해 구성된 작업으로 실행됩니다. 이 그림에서는 새 독일 데이터 센터로의 9단계 마이그레이션 단계를 보여 주었다.

![새 독일 데이터 센터로의 9단계 마이그레이션](../media/ms-cloud-germany-migration-opt-in/migration-organization.png)

다음 섹션에서는 독일 Microsoft 클라우드(도이치란드 Microsoft 클라우드)에서 새 독일 데이터 센터 지역의 Office 365 서비스로 전환할 때의 고객 경험에 대한 추가 정보를 제공합니다.

## <a name="services"></a>서비스

9단계 중 2단계와 9단계 중 3단계 사이에는 파트너 포털에 액세스할 수 없습니다. 이 시간 동안 파트너는 파트너 포털의 테넌트 정보에 액세스하지 못하게 될 수 있습니다. 마이그레이션마다 다르기 때문에 내게 필요한 경우의 기간은 시간일 수 있습니다. 

### <a name="azure-ad-phase-2-of-9"></a>Azure AD(2단계 중 9단계)

| Step(s) | 설명 | 적용 대상 | 영향 |
|:-------|:-----|:-------|:-------|
| 도이클란드 Microsoft 클라우드의 Azure AD 테넌트가 Office 365 서비스에 복사됩니다. | Azure AD는 테넌트를 Office 365 서비스에 복사합니다. 테넌트 및 사용자 식별자는 보존됩니다. Azure AD 서비스 통화는 도이치클란드 Microsoft 클라우드에서 Office 365 서비스로 리디렉션되고 서비스에 투명합니다. | 모든 Office 고객 | - GDPR(일반 데이터 보호 규정) DSR(데이터 주체 요청)은 향후 요청을 위해 Azure 관리 포털에서 실행됩니다. 도이클란드 Microsoft 클라우드에 있는 레거시 또는 비 고객 진단 데이터는 30일 전 또는 30일 전에 삭제됩니다. <br><br> - AD FS(Active Directory Federation Services)에서 페더전된 인증을 사용하는 고객은 마이그레이션 중의 모든 인증에 사용되는 발급자 URIS를 변경하지 말아야 합니다. 발급자 URIS를 변경하면 도메인의 사용자에 대한 인증 오류가 발생합니다. 발급자 URIS는 AD FS에서 직접 변경하거나 도메인이  관리에서  페더러티로 변환되고 그 반대의 경우도 마찬가지입니다. 고객은 마이그레이션된 Azure AD 테넌트에서 페더넌트 도메인을 추가, 제거 또는 변환하지 않는 것이 좋습니다. 발급자 URIS는 마이그레이션이 완전히 완료된 후 변경할 수 있습니다. <br><br> - 테넌트가 Office 365 서비스에 복사되는 동안 Microsoft Authenticator를 사용하는 MFA(다단계 인증) 요청은 사용자 ObjectID(GUID)로 표시됩니다. 이러한 표시 동작에도 불구하고 MFA 요청은 예상대로 수행됩니다.  Office 365 서비스 끝점을 사용하여 활성화된 Microsoft Authenticator 계정에 UPN(사용자 계정 이름)이 표시됩니다.  도이치클라드 Microsoft 클라우드 끝점을 사용하여 추가된 계정은 사용자 ObjectID를 표시하지만 도이클란드 Microsoft 클라우드 및 Office 365 서비스 끝점에서 모두 사용할 수 있습니다.  |
| 전역 STS 서비스를 지점으로 하는 AuthServer 사내를 수립합니다. | 이렇게 하면 하이브리드온-프레미스 환경을 대상으로 하는 Exchange 가용성 요청을 위해 도이치클란드 Microsoft 클라우드로 마이그레이션하는 사용자의 요청이 인증되어 사내 서비스에 액세스할 수 있습니다. 마찬가지로, 이렇게 하면 사내에서 Office 365 서비스 끝점으로의 요청 인증이 보장됩니다. | 하이브리드(-프레미스) 배포가 있는 Exchange Online 고객 | Azure AD 마이그레이션이 완료된 후, 하이브리드 토폴로지의 관리자는 Office 365 서비스에 대한 새 인증 서비스 끝점을 추가해야 합니다. Exchange PowerShell에서 이 명령을 사용하여 조직의 테넌트 `<TenantID>` ID로 대체합니다(Azure **Active Directory의 Azure** Portal에 있습니다). <br><br> - `New-AuthServer GlobalMicrosoftSts -AuthMetadataUrl https://accounts.accesscontrol.windows.net/<TenantId>/metadata/json/1` <br> <br> 이 작업을 완료하지 못하면 도이치클라드 Microsoft 클라우드에서 Office 365 서비스로 마이그레이션된 사서함 사용자에게 하이브리드 사용 가능한 요청이 정보를 제공하지 못할 수 있습니다.  |
| Azure 리소스 마이그레이션. | Office 365 및 Azure 리소스(예: 네트워킹, 계산 및 저장소)를 사용하는 고객은 Office 365 서비스 인스턴스로 리소스 마이그레이션을 수행하게 됩니다. 이 마이그레이션은 고객의 책임입니다. 메시지 센터 게시물에 시작 신호가 표시됩니다. Office 365 서비스 환경에서 Azure AD 조직을 완료하기 전에 마이그레이션을 완료해야 합니다. | Azure 고객 | Azure 마이그레이션의 경우 Azure 마이그레이션 플레이북, Azure Germany에 대한 마이그레이션 [지침 개요를 참조하세요.](https://docs.microsoft.com/azure/germany/germany-migration-main) |
|||||

### <a name="exchange-online-phase-5-of-9"></a>Exchange Online(5단계 중 9단계)

**Set-UserPhoto를 사용하는 경우**:

| Step(s) | 설명 | 적용 대상 | 영향 |
|:-------|:-----|:-------|:-------|
| 새 독일 지역은 기존 조직 설정에 추가된 후 사서함이 Office 365 서비스로 이동됩니다. | Exchange Online 구성은 전환 조직에 새로운 이동 독일어 지역을 추가합니다. 이 Office 365 서비스 지역은 기본으로 설정되어 내부 부하 분산 서비스가 Office 365 서비스의 적절한 기본 지역으로 사서함을 재배포할 수 있도록 합니다. 이 전환에서 어느 쪽에 있는 사용자(독일 또는 Office 365 서비스)는 동일한 조직에 있으며 두 URL 끝점을 모두 사용할 수 있습니다. |  Exchange Online | 사용자 사서함이 마이그레이션되어도 관리자 사서함이 마이그레이션되지 않은 경우 또는 그 반대의 경우 관리자는 PowerShell cmdlet인 **Set-UserPhoto를** 실행할 수 없습니다. 이 경우 관리자는 다음 구문을 사용하여 연결 설정 중에 추가 문자열을 `ConnectionUri` 전달해야 합니다. <br><br> `https://outlook.office.de/PowerShell-LiveID?email=<user_email>` <br><br> 여기서 은 Set-UserPhoto 를 사용하여 사진을 변경해야 하는 사용자의 전자 메일 ID에 대한 자리 `<user_email>` **holder입니다.** |
|||||

하이브리드, 사내 배포를 사용하는 경우:

| Step(s) | 설명 | 적용 대상 | 영향 |
|:-------|:-----|:-------|:-------|
|사서함의 온보드 또는 오프보더 이동을 중지하거나 삭제합니다.  | 이렇게 하면 이동 요청이 오류와 함께 실패하지 않습니다. | 하이브리드(-프레미스) 배포가 있는 Exchange Online 고객 | 필수 작업입니다. 이렇게 하지 못하면 서비스 또는 소프트웨어 클라이언트가 실패할 수 있습니다. |
|||||

### <a name="dynamics-phase-8-of-9"></a>Dynamics(8~9단계)

| Step(s) | 설명 | 적용 대상 | 영향 |
|:-------|:-----|:-------|:-------|
| Microsoft Dynamics 리소스 | Microsoft Dynamics를 사용 하는 고객은 Dynamics를 Office 365 서비스 인스턴스로 전환하기 위해 엔지니어링 또는 FastTrack의 참여를 하게 됩니다.* | Microsoft Dynamics 365 고객 | - 마이그레이션 후 관리자는 조직의 유효성을 검사합니다. <br><br> - 관리자는 필요한 경우 워크플로를 수정합니다. <br><br> - 관리자는 AdminOnly 모드를 적절하게 지워야 합니다. <br><br> - 관리자는 조직 유형을 샌드박스에서 적절하게 변경합니다. <br><br> - 최종 사용자에게 새 URL을 알리고 인스턴스(org)에 액세스합니다. <br><br> - 인바운드 연결을 새 끝점 URL로 업데이트합니다. <br><br> - 전환 중에 사용자가 Dynamics 서비스를 사용할 수 없습니다. <br><br> - 사용자는 각 Org를 마이그레이션한 후 해당 상태 및 기능의 유효성을 검사해야 합니다.  |
|||||

\* (i) Microsoft Dynamics 365를 사용 하는 고객은 제공된 마이그레이션 프로세스에 정의된 이 마이그레이션 시나리오에서 조치를 취해야 합니다. (ii) 고객이 조치를 취하지 못하면 Microsoft가 마이그레이션을 완료할 수 없습니다. (iii) 고객의 비활성으로 인해 Microsoft가 마이그레이션을 완료할 수 없는 경우 고객의 구독은 2021년 10월 29일에 만료됩니다. 


### <a name="power-bi-phase-8-of-9"></a>Power BI(8단계 중 9단계)

| Step(s) | 설명 | 적용 대상 | 영향 |
|:-------|:-----|:-------|:-------|
| Power BI 리소스 마이그레이션 | Microsoft Power BI를 사용하는 고객은 Power BI를 Office 365 서비스 인스턴스로 전환하기 위해 기존 PBI 마이그레이션 도구를 수동으로 트리거한 후 엔지니어링 또는 FastTrack에 참여하게 됩니다.\*\* | Microsoft Power BI 고객 | - 다음 Power BI _항목은_ 전환되지 않습니다. 다시 만들어야 합니다. <br><br> - 실시간 데이터 집합(예: 스트리밍 또는 푸시 데이터 집합) <br> - Power BI 사내 데이터 게이트웨이 구성 및 데이터 원본 <br> - 실시간 데이터 집합을 토대하여 작성된 보고서는 마이그레이션 후에 사용할 수 없습니다. 다시 만들어야 합니다. <br><br> - 전환 중에 사용자가 Power BI 서비스를 사용할 수 없습니다. 서비스를 사용할 수 없는 시간은 24시간을 넘지 말아야 합니다. <br><br> - 사용자는 마이그레이션 후 Power BI 서비스를 사용하여 데이터 원본 및 해당 사내 데이터 게이트웨이를 다시 구성해야 합니다.  이렇게 할 때까지 사용자는 이러한 데이터 원본을 사용하여 이러한 데이터 원본에 대해 예약된 새로 고침 및/또는 직접 쿼리를 수행할 수 없습니다. <br><br> - 용량 및 고급 작업 영역은 마이그레이션할 수 없습니다. 고객은 마이그레이션 전에 모든 용량을 삭제하고 마이그레이션 후 다시 만들어야 합니다. 작업 영역이 원하는 용량으로 다시 이동됩니다.  |
|||||

\*\* (i) Microsoft Power BI를 사용 하는 고객은 제공된 마이그레이션 프로세스에 정의된 이 마이그레이션 시나리오에서 조치를 취해야 합니다. (ii) 고객이 조치를 취하지 못하면 Microsoft가 마이그레이션을 완료할 수 없습니다. (iii) 고객의 비활성으로 인해 Microsoft가 마이그레이션을 완료할 수 없는 경우 고객의 구독은 2021년 10월 29일에 만료됩니다. 



## <a name="during-migration"></a>마이그레이션 진행 중

### <a name="sharepoint-online-phase-4-of-9"></a>SharePoint Online(4단계 중 9단계)

| Step(s) | 설명 | 적용 대상 | 영향 |
|:-------|:-----|:-------|:-------|
| SharePoint 및 OneDrive가 전환됩니다. | SharePoint 및 OneDrive는 이 단계에서 도이클란드 Microsoft 클라우드에서 Office 365 서비스로 마이그레이션됩니다. 기존 Microsoft 클라우드 도이클란드 URL은 보존됩니다( `contoso.sharepoint.de` ). 전환 중에 도이치클랜드 또는 Office 365 서비스에서 발급한 토큰이 유효합니다. | SharePoint 고객 | 마이그레이션 중에 SharePoint 2013 워크플로가 중단되어 마이그레이션 후에 다시 게시해야 합니다. |
|||||


### <a name="exchange-online-phase-5-of-9"></a>Exchange Online(5단계 중 9단계)

eDiscovery의 경우:

| Step(s) | 설명 | 적용 대상 | 영향 |
|:-------|:-----|:-------|:-------|
| 마이그레이션 중에 eDiscovery 검색이 실패하거나 마이그레이션된 SharePoint Online, 비즈니스용 OneDrive 및 Exchange Online 위치에 대한 결과가 0개 반환됩니다. | 마이그레이션 중에 고객은 콘텐츠 검색을 포함하여 보안 및 준수 센터에서 사례, 보류& 검색 [및 내보내기 &](https://docs.microsoft.com/microsoft-365/compliance/manage-legal-investigations)수 [있습니다.](https://docs.microsoft.com/microsoft-365/compliance/search-for-content)  그러나 마이그레이션된 SharePoint Online, 비즈니스용 OneDrive 및 Exchange Online 위치를 검색하면 0개 결과가 반환되거나 오류가 발생합니다. 수정에 대한 자세한 내용은 영향 _열을 참조합니다._ | eDiscovery를 사용하는 모든 고객 |  검색에서 마이그레이션 중 0개 결과 또는 오류를 반환하는 경우 SharePoint Online에 대해 다음 작업을 수행하세요. <br><br>  OneDrive 또는 SharePoint에서 파일 및 폴더 다운로드의 지침에 따라 SharePoint Online/ 비즈니스용 [OneDrive](https://support.office.com/article/download-files-and-folders-from-onedrive-or-sharepoint-5c7397b7-19c7-4893-84fe-d02e8fa5df05)사이트에서 직접 사이트를 다운로드합니다. 이 방법을 사용하려면 사이트에 대한 SharePoint Online 관리자 권한 또는 읽기 전용 권한이 필요합니다. <br><br> [OneDrive 또는 SharePoint에서](https://support.office.com/article/download-files-and-folders-from-onedrive-or-sharepoint-5c7397b7-19c7-4893-84fe-d02e8fa5df05)파일 및 폴더 다운로드에 설명된 제한을 초과하는 경우 고객은 [컴퓨터와 SharePoint](https://support.office.com/article/sync-sharepoint-files-with-the-new-onedrive-sync-app-6de9ede8-5b6e-4503-80b2-6190f3354a88)및 Teams 파일 동기화의 지침에 따라 비즈니스용 OneDrive 동기화 클라이언트를 사용할 수 있습니다. <br><br> - Exchange Online <br><br> - [eDiscovery의 Exchange Server](https://docs.microsoft.com/Exchange/policy-and-compliance/ediscovery/ediscovery) |
|||||


### <a name="skype-for-business-online-phase-7-of-9"></a>비즈니스용 Skype Online(7단계 중 9단계)

| Step(s) | 설명 | 적용 대상 | 영향 |
|:-------|:-----|:-------|:-------|
| 비즈니스용 Skype를 Teams로 마이그레이션 | 기존 비즈니스용 Skype 고객은 유럽의 Office 365 서비스로 마이그레이션된 다음 Office 365 서비스의 독일 지역의 Microsoft Teams로 전환됩니다. | 비즈니스용 Skype 고객 |  PowerShell은 테넌트 및 사용자에 대한 설정 및 정책을 관리하는 데 사용합니다. PowerShell 세션에 연결할 때 다음을 추가합니다. <br><br> `-OverridePowershellUri "https://admin4E.online.lync.com/OcsPowershellOAuth"` |
|||||


## <a name="post-migration"></a>마이그레이션 후

### <a name="azure-ad-phase-9-of-9"></a>Azure AD(9단계 중 9단계)

하이브리드의 경우:

| Step(s) | 설명 | 적용 대상 | 영향 |
|:-------|:-----|:-------|:-------|
| Azure AD Connect를 업데이트합니다. | Azure AD로의 컷오버가 완료되면 조직은 Office 365 서비스를 완전히 사용하고 있으며 더 이상 도이치랜드 Microsoft 클라우드에 연결되지 않습니다. 이때 고객은 델타 동기화 프로세스가 완료되어 레지스트리 경로에서 문자열 값을 `AzureInstance` 3(도이치랜드 Microsoft 클라우드)에서 0으로 변경해야 `Computer\HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Azure AD Connect` 합니다. | 하이브리드 Azure AD 연결 조직 | 의 값을 `AzureInstance` 레지스트리 키로 변경합니다. 이렇게 하지 못하면 Microsoft 클라우드 도이클라드 끝점을 더 이상 사용할 수 없는 후에 개체가 동기화되지 않습니다. |
|||||

페더타 인증의 경우:

| Step(s) | 설명 | 적용 대상 | 영향 |
|:-------|:-----|:-------|:-------|
| 도이치클라드 MICROSOFT 클라우드 AD FS에서 신뢰 파티 트러스트 제거 | Azure AD로의 컷오버가 완료되면 조직은 Office 365 서비스를 완전히 사용하고 있으며 더 이상 도이치랜드 Microsoft 클라우드에 연결되지 않습니다. 이 시점에서 고객은 도이치클라드 Microsoft 클라우드 끝점에 대한 신뢰 파티 트러스트는 제거해야 합니다. 이는 Azure AD가 IdP(ID 공급자)로 활용될 때 고객의 응용 프로그램이 도이클란드 Microsoft 클라우드 끝점을 지점하지하는 경우만 가능합니다. | 페더리드 인증 조직 | 없음 |
|||||

Azure AD의 경우:

| Step(s) | 설명 | 적용 대상 | 영향 |
|:-------|:-----|:-------|:-------|
| 원래 요청이 승인되지 않은 경우 마이그레이션 전에 지난 30일 동안 Azure AD 그룹에 가입하기 위한 요청을 다시 요청해야 합니다. | 최종 사용자 고객은 마이그레이션 전 지난 30일 동안 해당 요청이 승인되지 않은 경우 액세스 패널을 사용하여 Azure AD 그룹에 가입하기 위한 요청을 다시 제출해야 합니다. | 마이그레이션 전 지난 30일 동안 Azure AD 그룹 승인 요청이 승인되지 않은 최종 사용자 |  최종 사용자: <ol><li>액세스 [패널로 이동합니다.](https://account.activedirectory.windowsazure.com/r#/joinGroups)</li><li>마이그레이션 30일 전에 구성원 승인이 보류된 Azure AD 그룹을 찾아야 합니다.</li><li>Azure AD 그룹에 다시 참가를 요청합니다.</li></ol> 마이그레이션 후 다시 요청되지 않는 한 마이그레이션을 승인할 수 없습니다. |
|||||

DNS의 경우:

| Step(s) | 설명 | 적용 대상 | 영향 |
|:-------|:-----|:-------|:-------|
| Office 365 서비스 끝점에 대한 사내 DNS 서비스를 업데이트합니다. | Office 365 Germany를 지점하는 고객 관리 DNS 항목을 업데이트하여 Office 365 서비스 끝점을 설정해야 합니다. | 모든 Office 고객 | 필수 작업입니다. 이렇게 하지 못하면 서비스 또는 소프트웨어 클라이언트가 실패할 수 있습니다. |
|||||

Office 365 서비스 끝점에 대한 타사 서비스:

| Step(s) | 설명 | 적용 대상 | 영향 |
|:-------|:-----|:-------|:-------|
| Office 365 서비스 끝점에 대한 파트너 및 타사 서비스를 업데이트합니다. | - Office 365 Germany를 지점하는 타사 서비스 및 파트너가 Office 365 서비스 끝점을 지점으로 하여 업데이트해야 합니다. 예: 공급업체 및 파트너에 따라 응용 프로그램의 갤러리 앱 버전(사용 가능한 경우)을 다시 등록합니다. <br><br> - Graph API를 활용하는 모든 사용자 지정 응용 프로그램을 에서 로 `graph.microsoft.de` `graph.microsoft.com` 지정합니다. 변경된 끝점이 있는 다른 API도 활용하는 경우 업데이트해야 합니다. <br><br> - 모든 비제한 엔터프라이즈 응용 프로그램을 변경하여 전 세계 끝점으로 리디렉션합니다.  | 모든 Office 고객 | 필수 작업입니다. 이렇게 하지 못하면 서비스 또는 소프트웨어 클라이언트가 실패할 수 있습니다. |
|||||

### <a name="sharepoint-online-phase-4-of-9"></a>SharePoint Online(4단계 중 9단계)

| Step(s) | 설명 | 적용 대상 | 영향 |
|:-------|:-----|:-------|:-------|
| SharePoint 2013 워크플로를 다시 게시합니다. | 마이그레이션 전 작업에서는 SharePoint 2013 워크플로 수를 줄입니다. 이제 마이그레이션이 완료된 후 고객은 워크플로를 다시 게시할 수 있습니다. | 모든 Office 고객 | 이 작업은 필수 작업입니다. 이렇게 하지 못하면 사용자 혼동 및 지원 센터 통화가 발생될 수 있습니다. |
| Outlook을 통해 항목 공유 | 테넌트가 잘리면 Outlook을 통해 항목 공유가 더 이상 작동하지 않습니다. | SharePoint Online 및 비즈니스용 OneDrive | - SharePoint Online 및 비즈니스용 OneDrive에서 Outlook을 통해 항목을 공유할 수 있습니다. Outlook 단추를 누르면 공유 가능한 링크가 만들어지며 새 메시지로 Outlook Web App. <br><br> - 테넌트가 잘리면 이 공유 방법이 작동하지 않습니다. 이 문제는 알려진 문제로 인식하고 있습니다. 그러나 이 Outlook 기능은 사용되지 않는 경로에 있는 것이기 때문에 사용되지 않는 기능이 롤아웃될 때까지 이 문제를 해결할 계획이 없습니다. |


### <a name="exchange-online-phase-5-of-9"></a>Exchange Online(5단계 중 9단계)

하이브리드 Exchange 구성을 사용하는 경우:

| Step(s) | 설명 | 적용 대상 | 영향 |
|:-------|:-----|:-------|:-------|
| Office 365 서비스에 대해 HCW(하이브리드 구성 마법사)를 다시 실행합니다. | 기존 HCW 구성은 도이클란드 Microsoft 클라우드를 지원하기 위한 것입니다. Exchange 서비스 마이그레이션이 완료되면 도이치란드 Microsoft 클라우드에서 사내 구성을 분리합니다. | 하이브리드 배포를 실행하는 Exchange Online 고객 | - 필수 작업. 이렇게 하지 못하면 서비스 또는 소프트웨어 클라이언트가 실패할 수 있습니다. Exchange 사서함 마이그레이션이 시작되기 전에(5일 이상의 알림이 제공된 경우) 사서함의 온보드 또는 오프보더 이동을 중지하고 삭제해야 한다고 클라이언트에 알립니다.  그렇지 않은 경우 이동 요청에 오류가 표시됩니다. <br><br> - Exchange 사서함 마이그레이션이 완료되면 클라이언트가 온보드 및 오프보더 이동을 다시 시작할 수 있도록 알릴 수 있습니다. <br> Microsoft 클라우드에서 Office 365 서비스로 Exchange를 마이그레이션하는 동안 PowerShell cmdlet인 **Test-MigrationServerAvailabiilty를** 실행하면 작동하지 않을 수 있습니다. 그러나 마이그레이션이 완료된 후 제대로 작동합니다. <br><br> 사서함이 마이그레이션된 후 클라이언트에서 자격 증명 또는 권한 부여에 문제가 있는 경우 사용자는 를 실행하거나 ECP(Exchange 제어판)를 사용하여 동일하게 설정하여 마이그레이션 끝점에서 자신의 사내 관리자 자격 증명을 다시 입력할 수 `Set-MigrationEndpoint endpointName -Credential $(Get-Credential)` 있습니다.  |

eDiscovery의 경우:

| Step(s) | 설명 | 적용 대상 | 영향 |
|:-------|:-----|:-------|:-------|
|  모든 SharePoint Online, 비즈니스용 OneDrive 및 Exchange Online 위치가 SCC(보안 및 준수 센터)와 함께 마이그레이션됩니다. | 모든 eDiscovery 활동은 전 세계 테넌트에서 실행해야 합니다. 이제 검색이 100% 성공합니다.  오류 또는 오류는 정상적인 지원 채널을 따라야 합니다. | eDiscovery를 사용하는 모든 고객 | 없음 |
| 마이그레이션 전 단계 중에 만들어진 조직 전체 보존 정책 제거 | 고객은 마이그레이션 전 작업 중에 만들어진 조직 전체 보존 정책을 제거할 수 있습니다. | 마이그레이션 전 단계의 일부로 보존 정책을 적용한 모든 고객입니다. | 없음 |
|||||



## <a name="next-step"></a>다음 단계

[마이그레이션 단계 작업 및 영향 이해](ms-cloud-germany-transition-phases.md)

## <a name="more-information"></a>추가 정보

시작:

- [독일 Microsoft 클라우드에서 새 독일 데이터 센터 지역의 Office 365 서비스로 마이그레이션](ms-cloud-germany-transition.md)
- [Microsoft Cloud Deutschland 마이그레이션 지원](https://aka.ms/germanymigrateassist)
- [마이그레이션에 대해 옵트인하는 방법](ms-cloud-germany-migration-opt-in.md)
- [마이그레이션 중의 고객 환경](ms-cloud-germany-transition-experience.md)

전환을 통해 이동:

- [문장 작업 및 영향 마이그레이션](ms-cloud-germany-transition-phases.md)
- [추가 사전 작업](ms-cloud-germany-transition-add-pre-work.md)
- [Azure AD,](ms-cloud-germany-transition-azure-ad.md) [장치,](ms-cloud-germany-transition-add-devices.md) [환경](ms-cloud-germany-transition-add-experience.md)및 [AD FS에](ms-cloud-germany-transition-add-adfs.md)대한 추가 정보.

클라우드 앱:

- [Dynamics 365 마이그레이션 프로그램 정보](https://aka.ms/d365ceoptin)
- [Power BI 마이그레이션 프로그램 정보](https://aka.ms/pbioptin)
- [Microsoft Teams 업그레이드 시작하기](https://aka.ms/SkypeToTeams-Home)
