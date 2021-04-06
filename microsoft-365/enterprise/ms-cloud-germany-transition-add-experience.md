---
title: 도이클란드 Microsoft 클라우드에서 마이그레이션을 위한 마이그레이션 후 활동
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
description: '요약: 독일 Microsoft 클라우드(도이치란드 Microsoft 클라우드)에서 새 독일 데이터 센터 지역의 Office 365 서비스로 이동한 후의 마이그레이션 후 활동'
ms.openlocfilehash: 745589c1c997540094fc4a770e437de89015f88a
ms.sourcegitcommit: e0a96e08b7dc29e074065e69a2a86fc3cf0dad01
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/06/2021
ms.locfileid: "51591759"
---
# <a name="post-migration-activities-for-the-migration-from-microsoft-cloud-deutschland"></a>도이클란드 Microsoft 클라우드에서 마이그레이션을 위한 마이그레이션 후 활동

다음 섹션에서는 독일 Microsoft 클라우드(도이치란드 Microsoft 클라우드)에서 새 독일 데이터 센터 지역의 Office 365 서비스로 이동한 후 여러 서비스에 대한 마이그레이션 후 활동을 제공합니다.

## <a name="azure-ad"></a>Azure AD

### <a name="azure-ad-connect"></a>Azure AD Connect
**다음에 적용됩니다.** Id를 Azure AD Connect와 동기화하는 모든 고객

| Step(s) | 설명 | 영향 |
|:-------|:-------|:-------|
| Azure AD Connect를 업데이트합니다. | Azure AD로의 컷오버가 완료되면 조직은 Office 365 서비스를 완전히 사용하고 있으며 더 이상 도이치랜드 Microsoft 클라우드에 연결되지 않습니다. 이때 고객은 델타 동기화 프로세스가 완료되어 레지스트리 경로에서 문자열 값을 `AzureInstance` 3(도이치랜드 Microsoft 클라우드)에서 0으로 변경해야 `Computer\HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Azure AD Connect` 합니다. | 의 값을 `AzureInstance` 레지스트리 키로 변경합니다. 이렇게 하지 못하면 Microsoft 클라우드 도이클라드 끝점을 더 이상 사용할 수 없는 후에 개체가 동기화되지 않습니다. |
|||||

### <a name="azure-ad-federated-authentication-with-ad-fs"></a>AD FS를 사용하는 Azure AD 페더전 인증
**다음에 적용됩니다.** AD FS와의 페더러드 인증을 사용하는 모든 고객

| Step(s) | 설명 | 영향 |
|:-------|:-------|:-------|
| 도이치클라드 MICROSOFT 클라우드 AD FS에서 신뢰 파티 트러스트 제거 | Azure AD에 대한 컷오버가 완료되면 조직은 Office 365 서비스를 완전히 사용하고 있으며 더 이상 도이치랜드 Microsoft 클라우드에 연결되지 않습니다. 이 시점에서 고객은 도이치클라드 Microsoft 클라우드 끝점에 대한 신뢰 파티 트러스트는 제거해야 합니다. Azure AD가 IdP(ID 공급자)로 활용될 때 고객의 응용 프로그램이 도이치클라드 Microsoft 클라우드 끝점을 지점하지만 이행할 수 있습니다. | 페더리드 인증 조직 | 없음 |
||||

<!--
    Question from ckinder
    The following paragraph is not clear
-->
### <a name="group-approvals"></a>그룹 승인
**다음에 적용됩니다.** 마이그레이션 전 지난 30일 동안 Azure AD 그룹 승인 요청이 승인되지 않은 최종 사용자 

| Step(s) | 설명 | 영향 |
|:-------|:-------|:-------|
| 원래 요청이 승인되지 않은 경우 마이그레이션 전에 지난 30일 동안 Azure AD 그룹에 가입하기 위한 요청을 다시 요청해야 합니다. | 최종 사용자 고객은 마이그레이션 전 지난 30일 동안 해당 요청이 승인되지 않은 경우 액세스 패널을 사용하여 Azure AD 그룹에 가입하기 위한 요청을 다시 제출해야 합니다. |  최종 사용자: <ol><li>액세스 [패널로 이동합니다.](https://account.activedirectory.windowsazure.com/r#/joinGroups)</li><li>마이그레이션 30일 전에 구성원 승인이 보류된 Azure AD 그룹을 찾아야 합니다.</li><li>Azure AD 그룹에 다시 참가를 요청합니다.</li></ol> 마이그레이션 후 다시 요청되지 않는 한 마이그레이션을 승인할 수 없습니다. |
||||

<!--
    Question from ckinder
    The following paragraph is not clear
-->
## <a name="custom-dns-updates"></a>사용자 지정 DNS 업데이트
**다음에 적용됩니다.**  자체 DNS 영역 관리

| Step(s) | 설명 | 영향 |
|:------|:-------|:-------|
| Office 365 서비스 끝점에 대한 사내 DNS 서비스를 업데이트합니다. | 도이치클랜드 Microsoft 클라우드를 지점으로 하는 고객 관리 DNS 항목을 업데이트하여 Office 365 전역 서비스 끝점을 지점으로 해야 합니다. | 이렇게 하지 못하면 서비스 또는 소프트웨어 클라이언트가 실패할 수 있습니다. |
||||

## <a name="third-party-services"></a>타사 서비스
**다음에 적용됩니다.** Office 365 서비스 끝점에 대해 타사 서비스를 사용하는 고객

| Step(s) | 설명 | 영향 |
|:-------|:-------|:-------|
| Office 365 서비스 끝점에 대한 파트너 및 타사 서비스를 업데이트합니다. | <ul><li>Office 365 Germany를 지점하는 타사 서비스 및 파트너는 Office 365 서비스 끝점을 지점으로 하여 업데이트해야 합니다. 예: 공급업체 및 파트너에 따라 응용 프로그램의 갤러리 앱 버전(사용 가능한 경우)을 다시 등록합니다. </li><li>Graph API를 활용하는 모든 사용자 지정 응용 프로그램을 에서 로 `graph.microsoft.de` `graph.microsoft.com` 지정합니다. 변경된 끝점이 있는 다른 API도 활용하는 경우 업데이트해야 합니다. </li><li>모든 비제한 엔터프라이즈 응용 프로그램을 변경하여 전 세계 끝점으로 리디렉션합니다. </li></ul>| 필수 작업입니다. 이렇게 하지 못하면 서비스 또는 소프트웨어 클라이언트가 실패할 수 있습니다. |
||||

## <a name="sharepoint-online"></a>SharePoint Online
**적용 사항:** SharePoint 2013 워크플로를 사용하는 고객

| Step(s) | 설명 | 영향 |
|:-------|:-------|:-------|
| SharePoint 2013 워크플로를 다시 게시합니다. | 마이그레이션 전 작업에서는 SharePoint 2013 워크플로 수를 줄입니다. 이제 마이그레이션이 완료된 후 고객은 워크플로를 다시 게시할 수 있습니다. | 이 작업은 필수 작업입니다. 이렇게 하지 못하면 사용자 혼동 및 지원 센터 통화가 발생될 수 있습니다. |
| Outlook을 통해 항목 공유 | Outlook을 통해 SharePoint Online 및 비즈니스용 OneDrive의 항목 공유는 테넌트가 컷오버된 후에 더 이상 작동하지 않습니다. |<ul><li>SharePoint Online 및 비즈니스용 OneDrive에서 Outlook을 통해 항목을 공유할 수 있습니다. Outlook 단추를 누르면 공유 가능한 링크가 만들어지며 새 메시지로 Outlook Web App.</li><li>테넌트가 잘리면 이 공유 방법이 작동하지 않습니다. 이 문제는 알려진 문제로 인식하고 있습니다. 그러나 이 Outlook 기능은 사용되지 않는 경로에 있는 것이기 때문에 사용되지 않는 기능이 롤아웃될 때까지 이 문제를 해결할 계획이 없습니다. </li></ul>|
||||

## <a name="exchange-online"></a>Exchange Online
**적용 사항:** 하이브리드 Exchange 구성을 사용하는 고객

| Step(s) | 설명 | 영향 |
|:-------|:-------|:-------|
| Office 365 서비스에 대해 HCW(하이브리드 구성 마법사)를 다시 실행합니다. | 기존 HCW 구성은 도이클란드 Microsoft 클라우드를 지원하기 위한 것입니다. Exchange 서비스 마이그레이션이 완료되면 도이치란드 Microsoft 클라우드에서 사내 구성을 분리합니다. |<ul><li>필수 작업입니다. 이렇게 하지 못하면 서비스 또는 소프트웨어 클라이언트가 실패할 수 있습니다. Exchange 사서함 마이그레이션이 시작되기 전에(5일 이상의 알림이 제공된 경우) 사서함의 온보드 또는 오프보더 이동을 중지하고 삭제해야 한다고 클라이언트에 알립니다.  그렇지 않은 경우 이동 요청에 오류가 표시됩니다. </li><li>Exchange 사서함 마이그레이션이 완료되면 온보드 및 오프보더 이동을 다시 시작할 수 있도록 클라이언트에 알릴 수 있습니다. <br> Microsoft 클라우드에서 Office 365 서비스로 Exchange를 마이그레이션하는 동안 PowerShell cmdlet인 **Test-MigrationServerAvailabiilty를** 실행하면 작동하지 않을 수 있습니다. 그러나 마이그레이션이 완료된 후 제대로 작동합니다. </li><li>사서함이 마이그레이션된 후 클라이언트에서 자격 증명 또는 권한 부여에 문제가 있는 경우 사용자는 를 실행하거나 ECP(Exchange 제어판)를 사용하여 동일하게 설정하여 마이그레이션 끝점에서 자신의 사내 관리자 자격 증명을 다시 입력할 수 `Set-MigrationEndpoint endpointName -Credential $(Get-Credential)` 있습니다. </li></ul>|
