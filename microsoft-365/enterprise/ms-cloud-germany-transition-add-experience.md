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
ms.openlocfilehash: 8e28b9d6c8cc23e128234973039a4873b327e9fd
ms.sourcegitcommit: 7b8104015a76e02bc215e1cf08069979c70650ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/31/2021
ms.locfileid: "51476373"
---
# <a name="migration-phases-actions-and-impacts-for-the-migration-from-microsoft-cloud-deutschland-advanced"></a>마이그레이션 단계 도이클란드 Microsoft 클라우드에서 마이그레이션에 대한 작업 및 영향(고급)

독일 Microsoft 클라우드에서 Microsoft Office 365 서비스의 독일 지역으로 테넌트 마이그레이션은 단계 집합 및 각 워크로드에 대해 구성된 작업으로 실행됩니다. 이 그림에서는 새로운 독일 데이터 센터로의 10개 마이그레이션 단계를 보여 주었다.

![새 독일 데이터 센터로의 10단계 마이그레이션](../media/ms-cloud-germany-migration-opt-in/migration-organization.png)

다음 섹션에서는 독일 Microsoft 클라우드(도이치란드 Microsoft 클라우드)에서 새 독일 데이터 센터 지역의 Office 365 서비스로 전환할 때의 고객 경험에 대한 추가 정보를 제공합니다.

## <a name="office-365-portal-services-between-phase-2-and-phase-3"></a>2단계와 3단계 사이의 Office 365 포털 서비스

2단계와 3단계 사이에는 파트너 포털에 액세스할 수 없습니다. 이 시간 동안 파트너는 파트너 포털에서 테넌트 정보에 액세스하지 못하게 될 수 있습니다. 마이그레이션마다 다르기 때문에 내게 필요한 경우의 기간은 시간일 수 있습니다.

### <a name="ediscovery-phase-4-to-the-end-of-phase-9"></a>eDiscovery 4단계~9단계 종료

**다음에 적용됩니다.** eDiscovery를 사용하는 모든 고객

| Step(s) | 설명 | 영향 |
|:-------|:-------|:-------|
| 4단계의 시작부터 9단계까지 eDiscovery 검색은 실패하거나 마이그레이션된 SharePoint Online, 비즈니스용 OneDrive 및 Exchange Online 위치에 대해 0개 결과를 반환합니다. | 마이그레이션 중에 고객은 콘텐츠 검색을 포함하여 보안 및 준수 센터에서 사례, 보류& 검색 [및 내보내기 &](https://docs.microsoft.com/microsoft-365/compliance/manage-legal-investigations)수 [있습니다.](https://docs.microsoft.com/microsoft-365/compliance/search-for-content) 그러나 마이그레이션된 SharePoint Online, 비즈니스용 OneDrive 및 Exchange Online 위치를 검색하면 0개 결과가 반환되거나 오류가 발생합니다. 수정에 대한 자세한 내용은 영향 _열을 참조합니다._ | 마이그레이션 중 검색에서 결과 0개 또는 오류가 반환될 경우 SharePoint Online에 대해 다음 작업을 수행하세요. <ul><li>OneDrive 또는 SharePoint에서 파일 및 폴더 다운로드의 지침에 따라 SharePoint Online 또는 비즈니스용 [OneDrive](https://support.office.com/article/download-files-and-folders-from-onedrive-or-sharepoint-5c7397b7-19c7-4893-84fe-d02e8fa5df05)사이트에서 직접 사이트를 다운로드합니다. 이 방법을 사용하려면 사이트에 대한 SharePoint Online 관리자 권한 또는 읽기 전용 권한이 필요합니다.</li><li>[OneDrive 또는 SharePoint에서](https://support.office.com/article/download-files-and-folders-from-onedrive-or-sharepoint-5c7397b7-19c7-4893-84fe-d02e8fa5df05)파일 및 폴더 다운로드에 설명된 제한을 초과하는 경우 고객은 [컴퓨터와 SharePoint](https://support.office.com/article/sync-sharepoint-files-with-the-new-onedrive-sync-app-6de9ede8-5b6e-4503-80b2-6190f3354a88)및 Teams 파일 동기화의 지침에 따라 비즈니스용 OneDrive 동기화 클라이언트를 사용할 수 있습니다.</li><li>자세한 내용은  [In-Place eDiscovery in Exchange Server](https://docs.microsoft.com/Exchange/policy-and-compliance/ediscovery/ediscovery) |
||||

## <a name="exchange-online-set-userphoto-during-phase-5"></a>5단계 Set-UserPhoto Exchange Online 서비스

**다음에 적용됩니다.** Exchange Online에 사용자 사진을 저장하고 **Set-UserPhoto를** 사용하는 모든 고객 :

| Step(s) | 설명 | 영향 |
|:-------|:-------|:-------|
| 새 지역 "독일"이 기존 Exchange Online 조직 설정에 추가된 후 사서함이 Office 365 서비스로 이동됩니다. | Exchange Online 구성은 전환 조직에 새로운 이동 독일어 지역을 추가합니다. 이 Office 365 서비스 지역은 기본으로 설정되어 내부 부하 분산 서비스가 Office 365 서비스의 적절한 기본 지역으로 사서함을 재배포할 수 있도록 합니다. 이 전환에서 어느 쪽에 있는 사용자(독일 또는 Office 365 서비스)는 동일한 조직에 있으며 두 URL 끝점을 모두 사용할 수 있습니다. | 사용자 사서함이 마이그레이션되어도 관리자 사서함이 마이그레이션되지 않은 경우 또는 그 반대의 경우 관리자는 PowerShell cmdlet인 **Set-UserPhoto를** 실행할 수 없습니다. 이 경우 관리자는 다음 구문을 사용하여 연결 설정 중에 추가 문자열을 `ConnectionUri` 전달해야 합니다. <br> `https://outlook.office.de/PowerShell-LiveID?email=<user_email>` <br> 여기서 은 Set-UserPhoto 를 사용하여 사진을 변경해야 하는 사용자의 전자 메일 ID에 대한 자리 `<user_email>` **holder입니다.** |
||||

## <a name="post-migration"></a>마이그레이션 후

### <a name="azure-ad-phase-9"></a>Azure AD 9단계

**다음에 적용됩니다.** Id를 Azure AD Connect와 동기화하는 모든 고객

| Step(s) | 설명 | 영향 |
|:-------|:-------|:-------|
| Azure AD Connect를 업데이트합니다. | Azure AD로의 컷오버가 완료되면 조직은 Office 365 서비스를 완전히 사용하고 있으며 더 이상 도이치랜드 Microsoft 클라우드에 연결되지 않습니다. 이때 고객은 델타 동기화 프로세스가 완료되어 레지스트리 경로에서 문자열 값을 `AzureInstance` 3(도이치랜드 Microsoft 클라우드)에서 0으로 변경해야 `Computer\HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Azure AD Connect` 합니다. | 의 값을 `AzureInstance` 레지스트리 키로 변경합니다. 이렇게 하지 못하면 Microsoft 클라우드 도이클라드 끝점을 더 이상 사용할 수 없는 후에 개체가 동기화되지 않습니다. |
|||||

**다음에 적용됩니다.** ADFS와 함께 페더전된 인증을 사용하는 모든 고객

| Step(s) | 설명 | 영향 |
|:-------|:-------|:-------|
| 도이치클라드 MICROSOFT 클라우드 AD FS에서 신뢰 파티 트러스트 제거 | Azure AD에 대한 컷오버가 완료되면 조직은 Office 365 서비스를 완전히 사용하고 있으며 더 이상 도이치랜드 Microsoft 클라우드에 연결되지 않습니다. 이 시점에서 고객은 도이치클라드 Microsoft 클라우드 끝점에 대한 신뢰 파티 트러스트는 제거해야 합니다. Azure AD가 IdP(ID 공급자)로 활용될 때 고객의 응용 프로그램이 도이치클라드 Microsoft 클라우드 끝점을 지점하지만 이행할 수 있습니다. | 페더리드 인증 조직 | 없음 |
||||

<!--
    Question from ckinder
    The following paragraph is not clear
-->
**다음에 적용됩니다.** 마이그레이션 전 지난 30일 동안 Azure AD 그룹 승인 요청이 승인되지 않은 최종 사용자 

| Step(s) | 설명 | 영향 |
|:-------|:-------|:-------|
| 원래 요청이 승인되지 않은 경우 마이그레이션 전에 지난 30일 동안 Azure AD 그룹에 가입하기 위한 요청을 다시 요청해야 합니다. | 최종 사용자 고객은 마이그레이션 전 지난 30일 동안 해당 요청이 승인되지 않은 경우 액세스 패널을 사용하여 Azure AD 그룹에 가입하기 위한 요청을 다시 제출해야 합니다. |  최종 사용자: <ol><li>액세스 [패널로 이동합니다.](https://account.activedirectory.windowsazure.com/r#/joinGroups)</li><li>마이그레이션 30일 전에 구성원 승인이 보류된 Azure AD 그룹을 찾아야 합니다.</li><li>Azure AD 그룹에 다시 참가를 요청합니다.</li></ol> 마이그레이션 후 다시 요청되지 않는 한 마이그레이션을 승인할 수 없습니다. |
||||

<!--
    Question from ckinder
    The following paragraph is not clear
-->
**다음에 적용됩니다.**  자체 DNS 영역 관리

| Step(s) | 설명 | 영향 |
|:------|:-------|:-------|
| Office 365 서비스 끝점에 대한 사내 DNS 서비스를 업데이트합니다. | 도이치클랜드 Microsoft 클라우드를 지점으로 하는 고객 관리 DNS 항목을 업데이트하여 Office 365 전역 서비스 끝점을 지점으로 해야 합니다. | 이렇게 하지 못하면 서비스 또는 소프트웨어 클라이언트가 실패할 수 있습니다. |
||||

**다음에 적용됩니다.** Office 365 서비스 끝점에 대해 타사 서비스를 사용하는 고객

| Step(s) | 설명 | 영향 |
|:-------|:-------|:-------|
| Office 365 서비스 끝점에 대한 파트너 및 타사 서비스를 업데이트합니다. | <ul><li>Office 365 Germany를 지점하는 타사 서비스 및 파트너는 Office 365 서비스 끝점을 지점으로 하여 업데이트해야 합니다. 예: 공급업체 및 파트너에 따라 응용 프로그램의 갤러리 앱 버전(사용 가능한 경우)을 다시 등록합니다. </li><li>Graph API를 활용하는 모든 사용자 지정 응용 프로그램을 에서 로 `graph.microsoft.de` `graph.microsoft.com` 지정합니다. 변경된 끝점이 있는 다른 API도 활용하는 경우 업데이트해야 합니다. </li><li>모든 비제한 엔터프라이즈 응용 프로그램을 변경하여 전 세계 끝점으로 리디렉션합니다. </li></ul>| 필수 작업입니다. 이렇게 하지 못하면 서비스 또는 소프트웨어 클라이언트가 실패할 수 있습니다. |
||||

### <a name="sharepoint-online-post-migration"></a>SharePoint Online 마이그레이션 후

| Step(s) | 설명 | 영향 |
|:-------|:-------|:-------|
| SharePoint 2013 워크플로를 다시 게시합니다. | 마이그레이션 전 작업에서는 SharePoint 2013 워크플로 수를 줄입니다. 이제 마이그레이션이 완료된 후 고객은 워크플로를 다시 게시할 수 있습니다. | 이 작업은 필수 작업입니다. 이렇게 하지 못하면 사용자 혼동 및 지원 센터 통화가 발생될 수 있습니다. |
| Outlook을 통해 항목 공유 | Outlook을 통해 SharePoint Online 및 비즈니스용 OneDrive의 항목 공유는 테넌트가 컷오버된 후에 더 이상 작동하지 않습니다. |<ul><li>SharePoint Online 및 비즈니스용 OneDrive에서 Outlook을 통해 항목을 공유할 수 있습니다. Outlook 단추를 누르면 공유 가능한 링크가 만들어지며 새 메시지로 Outlook Web App.</li><li>테넌트가 잘리면 이 공유 방법이 작동하지 않습니다. 이 문제는 알려진 문제로 인식하고 있습니다. 그러나 이 Outlook 기능은 사용되지 않는 경로에 있는 것이기 때문에 사용되지 않는 기능이 롤아웃될 때까지 이 문제를 해결할 계획이 없습니다. </li></ul>|
||||

### <a name="exchange-online-post-migration"></a>Exchange Online 마이그레이션 후

하이브리드 Exchange 구성을 사용하는 경우:

| Step(s) | 설명 | 영향 |
|:-------|:-------|:-------|
| Office 365 서비스에 대해 HCW(하이브리드 구성 마법사)를 다시 실행합니다. | 기존 HCW 구성은 도이클란드 Microsoft 클라우드를 지원하기 위한 것입니다. Exchange 서비스 마이그레이션이 완료되면 도이치란드 Microsoft 클라우드에서 사내 구성을 분리합니다. |<ul><li>필수 작업입니다. 이렇게 하지 못하면 서비스 또는 소프트웨어 클라이언트가 실패할 수 있습니다. Exchange 사서함 마이그레이션이 시작되기 전에(5일 이상의 알림이 제공된 경우) 사서함의 온보드 또는 오프보더 이동을 중지하고 삭제해야 한다고 클라이언트에 알립니다.  그렇지 않은 경우 이동 요청에 오류가 표시됩니다. </li><li>Exchange 사서함 마이그레이션이 완료되면 온보드 및 오프보더 이동을 다시 시작할 수 있도록 클라이언트에 알릴 수 있습니다. <br> Microsoft 클라우드에서 Office 365 서비스로 Exchange를 마이그레이션하는 동안 PowerShell cmdlet인 **Test-MigrationServerAvailabiilty를** 실행하면 작동하지 않을 수 있습니다. 그러나 마이그레이션이 완료된 후 제대로 작동합니다. </li><li>사서함이 마이그레이션된 후 클라이언트에서 자격 증명 또는 권한 부여에 문제가 있는 경우 사용자는 를 실행하거나 ECP(Exchange 제어판)를 사용하여 동일하게 설정하여 마이그레이션 끝점에서 자신의 사내 관리자 자격 증명을 다시 입력할 수 `Set-MigrationEndpoint endpointName -Credential $(Get-Credential)` 있습니다. </li></ul>|

### <a name="ediscovery-post-migration"></a>eDiscovery 마이그레이션 후

**다음에 적용됩니다.** eDiscovery를 사용하는 모든 고객

| Step(s) | 설명 | 영향 |
|:-------|:-------|:-------|
|  모든 SharePoint Online, 비즈니스용 OneDrive 및 Exchange Online 위치가 SCC(보안 및 준수 센터)와 함께 마이그레이션됩니다. | 모든 eDiscovery 활동은 전 세계 테넌트에서 실행해야 합니다. 이제 검색이 100% 성공합니다.  오류 또는 오류는 정상적인 지원 채널을 따라야 합니다. | 없음 |
||||

**다음에 적용됩니다.**  마이그레이션 전 단계의 일부로 보존 정책을 적용한 모든 고객

| Step(s) | 설명 | 영향 |
|:-------|:-------|:-------|
| 마이그레이션 전 단계 중에 만들어진 조직 전체 보존 정책 제거 | 고객은 마이그레이션 전 작업 중에 만들어진 조직 전체 보존 정책을 제거할 수 있습니다. | 없음 |
||||

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

- [Dynamics 365 마이그레이션 프로그램 정보](/dynamics365/get-started/migrate-data-german-region)
- [Power BI 마이그레이션 프로그램 정보](/power-bi/admin/service-admin-migrate-data-germany)
- [Microsoft Teams 업그레이드 시작하기](/microsoftteams/upgrade-start-here)