---
title: 마이그레이션 단계, 도이치란드 Microsoft 클라우드 마이그레이션 작업 및 영향(일반)
ms.author: andyber
author: andybergen
manager: laurawi
ms.date: 12/15/2020
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
description: '요약: 독일 Microsoft 클라우드(도이치란드 Microsoft 클라우드)에서 새 독일 데이터 센터 지역의 Office 365 서비스로 이동하는 마이그레이션 단계 작업 및 영향을 이해합니다.'
ms.openlocfilehash: 940ad0799aca7ead20d226cfcf3cc4b7b21c6cdb
ms.sourcegitcommit: 222fb7fe2b26dde3d8591b61cc02113d6135012c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/06/2021
ms.locfileid: "49760201"
---
# <a name="migration-phases-actions-and-impacts-for-the-migration-from-microsoft-cloud-deutschland-general"></a>마이그레이션 단계, 도이치란드 Microsoft 클라우드 마이그레이션 작업 및 영향(일반)

독일 Microsoft 클라우드에서 Microsoft Office 365 서비스의 독일 지역으로의 테넌트 마이그레이션은 각 워크로드에 대해 구성된 작업 집합으로 실행됩니다. 이러한 작업을 수행하면 중요한 데이터 및 환경이 Office 365 서비스로 마이그레이션됩니다. 테넌트가 마이그레이션 큐에 추가된 후 각 워크로드는 백end 서비스에서 실행되는 단계 집합으로 완료됩니다. 일부 워크로드에는 관리자(또는 사용자)가 작업을 요구하거나 마이그레이션이 실행되고 마이그레이션이 구성되는 방식에 설명된 단계의 사용에 영향을 줄 [수 있습니다.](ms-cloud-germany-transition.md#how-is-the-migration-organized)

다음 섹션에는 마이그레이션의 다양한 단계를 진행할 때 작업에 대한 작업 및 영향이 포함되어 있습니다. 표를 검토하고 조직에 적용할 수 있는 작업이나 효과를 파악합니다. 필요한 경우 각 단계의 단계를 실행할 준비가 되도록 합니다. 필요한 단계를 완료하지 못하면 서비스가 종료될 수 있으며 Office 365 서비스로의 마이그레이션 완료가 지연될 수 있습니다.

## <a name="exchange-online"></a>Exchange Online

| 단계 | 설명 | 적용 대상 | 영향 |
|:-------|:-----|:-------|:-------|
| 새 독일 지역은 기존 조직 설정에 추가된 후 사서함이 Office 365 서비스로 이동됩니다. | Exchange Online 구성은 전환 조직에 새로운 이동 독일 지역을 추가합니다. 이 Office 365 서비스 지역은 기본으로 설정되어 내부 부하 분산 서비스가 Office 365 서비스의 적절한 기본 지역으로 사서함을 재배포할 수 있도록 합니다. 이 전환에서 한 쪽(독일 또는 Office 365 서비스)의 사용자는 동일한 조직에 있으며 URL 끝점을 사용할 수 있습니다. | Exchange Online | - 사용자 및 서비스를 독일 URL에서 Office 365 서비스 URL()로 `https://outlook.office365.com` 전환합니다. <br><br> - 사용자는 마이그레이션 중에 레거시 독일 URL을 통해 서비스에 계속 액세스할 수 있습니다. 즉각적인 조치가 필요하지 않습니다. <br><br> - 사용자가 Office Online 기능(일정office.com 메일, 사용자)에 대한 office.com 포털을 사용하기 시작해야 합니다. 아직 Office 365 서비스로 마이그레이션되지 않은 서비스에 대한 탐색은 마이그레이션될 때까지 작동하지 않습니다. <br><br> - Outlook Web App 동안 공용 폴더 환경을 제공하지 않습니다. |
|||||

추가 고려 사항:

- `myaccount.msft.com` 는 Office 365를 컷오버한 후에만 작동하게 합니다. 링크는 해당 시간까지 "문제가 발생했습니다." 오류 메시지가 생성됩니다.

- 다른 Outlook Web App 공유 사서함에 액세스하는 사용자(예: 독일 환경의 사용자가 전역 환경의 공유 사서함에 액세스하는 경우)는 두 번째로 인증하라는 메시지가 표시됩니다. 사용자는 먼저 사서함을 인증하고 사서함에 액세스한 다음 에 있는 공유 `outlook.office.de` 사서함을 열 수 있어야 `outlook.office365.com` 합니다. 다른 서비스에서 호스팅되는 공유 리소스에 액세스할 때 두 번째 인증을 해야 합니다.

- 전환하려는 기존 Microsoft 클라우드 고객의 경우 파일 > **Info**> 계정 추가를 사용하여 공유 사서함을 Outlook에 추가하면 일정 권한 보기가 실패할 수 있습니다(Outlook 클라이언트가 Rest API를 사용하려고 `https://outlook.office.de/api/v2.0/Me/Calendars` 시도함). 일정 권한을 보기 위해 계정을 추가하려는 고객은 [Outlook에서](https://support.microsoft.com/office/user-experience-changes-for-sharing-a-calendar-in-outlook-5978620a-fe6c-422a-93b2-8f80e488fdec) 일정 공유에 대한 사용자 환경 변경 내용에 설명된 레지스트리 키를 추가하여 이 작업이 성공할 수 있도록 할 수 있습니다. 이 레지스트리 키는 그룹 정책을 사용하여 조직 전체에 배포할 수 있습니다.

- 마이그레이션 단계에서 PowerShell cmdlet **New-migrationEndpoint, Set-MigrationEndpoint** 및 **Test-MigrationsServerAvailability를** 사용하면 오류가 발생할 수 있습니다(프록시 오류).  이 문제는 중재 사서함이 전 세계로 마이그레이션했지만 관리 사서함이 전 세계로 마이그레이션되지 않은 경우 또는 그 반대의 경우 발생합니다. 이 문제를 해결하기 위해 테넌트 PowerShell 세션을 만드는 동안 ConnectionUri의 라우팅 힌트로 중재 **사서함을 사용 합니다.** 예: `New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri "https://outlook.office365.com/powershell-liveid?email=Migration.8f3e7716-2011-43e4-96b1-aba62d229136@TENANT.onmicrosoft.de" -Credential $UserCredential -Authentication Basic -AllowRedirection`

- Exchange Online 하이브리드를 사용하는 경우:

    - 전환하기 전에 HCW(하이브리드 구성 마법사)를 다시 실행하여 도이클란드 Microsoft 클라우드에 대한 On-premises 구성을 업데이트하고 Office 365 서비스에 대해 정리 시 HCW를 다시 실행해야 합니다. 사용자 지정 도메인을 사용하는 경우 추가 DNS 업데이트가 요구될 수 있습니다.

마이그레이션과 Exchange Online 리소스가 마이그레이션된 후의 조직 차이점에 대한 자세한 내용은 새 독일 데이터 센터 지역의 [Office 365](ms-cloud-germany-transition-experience.md)서비스로 마이그레이션하는 동안 고객 환경의 정보를 검토하세요.

## <a name="exchange-online-protection"></a>Exchange Online Protection

백 엔드 EOP(Exchange Online Protection) 기능은 새로운 독일 지역으로 복사됩니다. 

| 단계 | 설명 | 적용 대상 | 영향 |
|:-------|:-----|:-------|:-------|
| Exchange Online 라우팅 및 기록 메시지 세부 정보 마이그레이션 | Exchange Online을 사용하면 외부 호스트에서 Office 365로 라우팅할 수 있습니다. 외부 MX 레코드는 EOP 서비스로 라우팅하기 위해 전환됩니다. 테넌트 구성 및 기록 세부 정보가 마이그레이션됩니다. | Exchange Online 고객 | - Microsoft에서 관리하는 DNS 항목이 Office 365 Germany EOP에서 Office 365 서비스로 업데이트됩니다. <br><br> - 고객은 EOP 마이그레이션을 위해 EOP 이중 쓰기 후 30일 동안 기다려야 합니다. 그렇지 않으면 데이터 손실이 있을 수 있습니다. |
|||||

## <a name="sharepoint-online"></a>SharePoint Online

| 단계 | 설명 | 적용 대상 | 영향 |
|:-------|:-----|:-------|:-------|
| SharePoint 및 OneDrive가 전환됩니다. | 이 단계에서 SharePoint 및 OneDrive는 도이치란드 Microsoft 클라우드에서 Office 365 서비스로 마이그레이션됩니다. 기존 Microsoft 클라우드 도이클란드 URL은 보존됩니다(예: `contoso.sharepoint.de` ). 도이클란드 Microsoft 클라우드 또는 Office 365 서비스에서 발급한 토큰은 전환 중에 유효합니다. | SharePoint 고객 | - 마이그레이션 중 두 가지 짧은 기간 동안 콘텐츠가 읽기 전용입니다. 이 시간 동안 SharePoint에서 "콘텐츠를 편집할 수 없습니다." 배너가 예상됩니다. <br><br> - 검색 인덱스는 보존되지 않습니다. 다시 생성하는 데 최대 10일이 걸릴 수 있습니다. <br><br> - SharePoint/OneDrive 콘텐츠는 마이그레이션 중 두 가지 짧은 기간 동안 읽기 전용입니다. 이 시간 동안 "콘텐츠를 편집할 수 없습니다." 배너가 잠시 표시됩니다. <br><br> - 인덱스를 다시 구성하는 동안 검색 인덱스를 사용할 수 없습니다. 이 기간 동안 검색 쿼리는 전체 결과를 반환하지 않을 수 있습니다. <br><br> - 기존 사이트가 보존됩니다. |
|||||

추가 고려 사항:

- SharePoint Online 마이그레이션이 완료 되면 데이터 인덱스가 다시 작성 됩니다. 검색 인덱스에 종속된 기능은 다시 인덱싱이 완료된 동안 영향을 받을 수 있습니다.

- 조직에서 여전히 SharePoint 2010 워크플로를 사용하는 경우 2021년 12월 31일 이후에는 더 이상 작동하지 않습니다. SharePoint 2013 워크플로는 2020년 11월 1일부터 새 테넌트에 대해 기본적으로 꺼져 있습니다. SharePoint Online 서비스로의 마이그레이션이 완료된 후 Power Automate 또는 기타 지원되는 솔루션으로 이동하는 것이 좋습니다.

- 독일 지역으로의 OneDrive 마이그레이션이 완료된 후 데이터 인덱스가 다시 생성됩니다. 다시 인덱싱이 진행되는 동안 검색 인덱스에 종속된 기능이 영향을 받을 수 있습니다.

- SharePoint Online 인스턴스가 아직 마이그레이션되지 않은 도이치랜드 Microsoft 클라우드 고객은 SharePoint Online PowerShell 모듈/Microsoft.SharePointOnline.CSOM 버전 16.0.20616.12000 이하를 유지해야 합니다. 그렇지 않으면 PowerShell 또는 클라이언트 쪽 개체 모델을 통해 SharePoint Online에 대한 연결이 실패합니다.

- SharePoint Online 인스턴스가 마이그레이션된 도이치랜드 Microsoft 클라우드 고객은 SharePoint Online PowerShell 모듈/Microsoft.SharePointOnline.CSOM을 버전 16.0.20717.12000 이상으로 업데이트해야 합니다. 그렇지 않으면 PowerShell 또는 클라이언트 쪽 개체 모델을 통해 SharePoint Online에 대한 연결이 실패합니다.


## <a name="skype-for-business-online"></a>비즈니스용 Skype Online

| 단계 | 설명 | 적용 대상 | 영향 |
|:-------|:-----|:-------|:-------|
| 비즈니스용 Skype를 Teams로 마이그레이션. | 기존 비즈니스용 Skype 고객은 유럽의 Office 365 서비스로 마이그레이션된 다음 Office 365 서비스의 독일 지역의 Microsoft Teams로 전환됩니다. | 비즈니스용 Skype 고객 | - 사용자는 마이그레이션 날짜에 비즈니스용 Skype에 로그인할 수 없습니다. 마이그레이션이 시작되기 10일 전에 관리 센터에 게시하여 마이그레이션이 언제 수행될지 알려드려야 합니다. <br><br> - 정책 구성이 마이그레이션됩니다. <br><br> - 사용자는 Teams로 마이그레이션됩니다. 마이그레이션 후 비즈니스용 Skype가 더 이상 사용되지 않습니다. <br><br> - 사용자에게 Teams 데스크톱 클라이언트가 설치되어 있어야 합니다. 설치는 비즈니스용 Skype 인프라의 정책을 통해 10일 동안 진행되지만 실패하는 경우 사용자는 클라이언트를 다운로드하거나 지원되는 브라우저에 연결해야 합니다. <br><br> - 연락처 및 모임이 Teams로 마이그레이션됩니다. <br><br> - 사용자는 고객 DNS 항목이 완료될 때까지 서비스가 Office 365 서비스로 전환되는 동안 비즈니스용 Skype에 로그인할 수 없습니다. <br><br> - 연락처 및 기존 모임은 비즈니스용 Skype 모임으로 계속 작동됩니다. |
|||||

## <a name="office-services"></a>Office Services

Office에서 가장 최근에 사용한 (MRU) 서비스는 마이그레이션이 아니라 독일 서비스에서 Office 365 서비스로의 절전입니다. Office 365 서비스 쪽의 MRU 링크만 포털에서 마이그레이션한 Office.com 표시됩니다. 독일 서비스의 MRU 링크는 Office 365 서비스의 MRU 링크로 표시되지 않습니다. Office 365에서 MRU 링크는 테넌트 마이그레이션이 완료된 후에만 액세스할 수 있습니다.

## <a name="subscription"></a>구독

| 단계 | 설명 | 적용 대상 | 영향 |
|:-------|:-----|:-------|:-------|
| 동의 없이는 고객을 마이그레이션할 수 없습니다. | Microsoft는 데이터 및 서비스의 Office 365 서비스 인스턴스 전환을 오케스트레이션할 수 있는 두 가지 방법 중 하나를 사용하여 마이그레이션할 수 있는 권리가 있습니다. <br> 관리자가 Microsoft 주도 마이그레이션에 옵트인(opt in)합니다. <br> 고객은 2020년 5월 1일 이후에 도이클란드 Microsoft 클라우드 테넌트의 모든 구독을 갱신합니다. 매월 이러한 고객에게 마이그레이션을 알리고, 30일을 기다렸다가 고객에게 취소할 수 있는 기회를 제공한 다음 ICM에서 직접 옵트인(opt in)할 수 있습니다. | 모든 Office 고객 | - 테넌트가 마이그레이션에 동의된 것으로 표시되어 관리 센터에 확인이 표시됩니다. <br><br> - 클라우드 독일 메시지 센터 테넌트에 인정이 게시됩니다. 도이치란드 Microsoft 클라우드 끝점에서 서비스 구성이 계속됩니다. <br><br> - 마이그레이션 단계 상태에 대한 업데이트를 위해 메시지 센터를 모니터링합니다. |
| 구독이 전송되는 경우 라이선스가 다시 재배치됩니다. | 테넌트가 Office 365 서비스로 전환된 후 해당 Office 365 서비스 구독은 전송된 Microsoft 클라우드 도이클랜드 구독을 구매합니다. 도이치란드에 할당된 Microsoft 클라우드 라이선스가 있는 사용자에게는 Office 365 서비스 라이선스가 할당됩니다. 레거시 Microsoft 클라우드 도이치란드 구독은 완료 시 Office 365 서비스 테넌트에서 제거됩니다. | 모든 Office 고객 | - 이 단계에서는 기존 구독에 대한 변경 내용이 차단됩니다(예: 새 구독 구매 또는 사용자 수 변경 없음). <br><br> - 라이선스 할당 변경이 차단됩니다. <br><br> - 도이치란드 Microsoft 클라우드 구독이 해당 Office 365 서비스 구독으로 마이그레이션됩니다. 이 구독의 Office 365 서비스 서비스는 Microsoft(제품 매핑라고도 합니다)에 _의해 정의됩니다._ <br><br> - Office 365 서비스에서 제공하는 기능(서비스 계획)의 수는 원래 Microsoft 클라우드 도이클란드 제품보다 클 수 있습니다. Office 365 서비스의 사용자 라이선스는 도이클랜드의 유사한 Microsoft 클라우드 기능(서비스 계획)에 동일하게 할당됩니다. 모든 사용자의 사용자 라이선스가 새 기능에 자동으로 할당됩니다. 관리자는 필요한 경우 해당 라이선스를 사용하지 않도록 설정하기 위한 명시적 조치를 취해야 합니다. <br><br> - 구독 마이그레이션이 완료되면 Office 365 서비스 및 Germany 구독이 모두 Office 365 관리 포털에 표시될 수 있으며 독일 구독 상태는 디비전되지 _않습니다._ <br><br> - 사용자는 새 Office 365 서비스 구독에 대한 라이선스를 다시 재할당합니다. 독일 구독 또는 SKU GUID에 종속된 모든 고객 프로세스는 손상될 수 있으며 Office 365 서비스 제품으로 수정해야 합니다. <br><br> - Office 365 서비스의 새 구독은 새 기간(월별/분기별/년별)을 통해 구입하며 고객은 도이클란드 Microsoft 클라우드 구독의 미사용 잔액에 대해 비분할적 환불을 받게 됩니다. <br><br> - 도이치란드 파트너 테넌트는 마이그레이션되지 않습니다. CSP 고객은 동일한 파트너의 새 Office 365 서비스 테넌트에 따라 Office 365 서비스로 마이그레이션됩니다. 고객 마이그레이션 후 파트너는 Office 365 서비스 테넌트에서만 이 고객을 관리할 수 있습니다. <br><br> - 테넌트 관리자가 사용하지 않도록 설정하지 않은 경우 추가 기능(예: Microsoft Planner 및 Microsoft Flow)을 사용할 수 있습니다. 사용자 라이선스에 할당된 서비스 계획을 사용하지 않도록 설정하는 방법에 대한 자세한 내용은 사용자 라이선스를 할당하는 동안 [Microsoft 365](disable-access-to-services-while-assigning-user-licenses.md)서비스에 대한 액세스 비활성화를 참조하세요.  |
|||||

## <a name="next-step"></a>다음 단계

[추가 사전 작업 수행](ms-cloud-germany-transition-add-pre-work.md)

## <a name="more-information"></a>추가 정보

시작:

- [독일 Microsoft 클라우드에서 새 독일 데이터 센터 지역의 Office 365 서비스로 마이그레이션](ms-cloud-germany-transition.md)
- [Microsoft Cloud Deutschland 마이그레이션 지원](https://aka.ms/germanymigrateassist)
- [마이그레이션에 대해 옵트인하는 방법](ms-cloud-germany-migration-opt-in.md)
- [마이그레이션 중의 고객 환경](ms-cloud-germany-transition-experience.md)

전환을 통해 이동:

- [추가 사전 작업](ms-cloud-germany-transition-add-pre-work.md)
- [Azure AD,](ms-cloud-germany-transition-azure-ad.md) [장치,](ms-cloud-germany-transition-add-devices.md) [환경 및](ms-cloud-germany-transition-add-experience.md) [AD FS에](ms-cloud-germany-transition-add-adfs.md)대한 추가 정보.

클라우드 앱:

- [Dynamics 365 마이그레이션 프로그램 정보](https://aka.ms/d365ceoptin)
- [Power BI 마이그레이션 프로그램 정보](https://aka.ms/pbioptin)
- [Microsoft Teams 업그레이드 시작하기](https://aka.ms/SkypeToTeams-Home)
