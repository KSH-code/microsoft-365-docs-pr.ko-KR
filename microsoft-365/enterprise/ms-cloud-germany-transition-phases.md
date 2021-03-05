---
title: 마이그레이션 단계 도이클란드 Microsoft 클라우드에서 마이그레이션에 대한 작업 및 영향(일반)
ms.author: andyber
author: andybergen
manager: laurawi
ms.date: 01/26/2021
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
description: '요약: 독일 Microsoft 클라우드(도이치란드 Microsoft 클라우드)에서 새 독일 데이터 센터 지역의 Office 365 서비스로 전환할 때의 마이그레이션 단계 작업 및 영향을 이해합니다.'
ms.openlocfilehash: 1da3ff6b3347d0e996b017aa1f6243fd724ffccd
ms.sourcegitcommit: 375168ee66be862cf3b00f2733c7be02e63408cf
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/04/2021
ms.locfileid: "50454410"
---
# <a name="migration-phases-actions-and-impacts-for-the-migration-from-microsoft-cloud-deutschland-general"></a>마이그레이션 단계 도이클란드 Microsoft 클라우드에서 마이그레이션에 대한 작업 및 영향(일반)

독일 Microsoft 클라우드에서 Microsoft Office 365 서비스의 독일 지역으로 테넌트 마이그레이션은 단계 집합 및 각 워크로드에 대해 구성된 작업으로 실행됩니다. 이 그림에서는 새 독일 데이터 센터로의 9단계 마이그레이션 단계를 보여 주었다.

![새 독일 데이터 센터로의 9단계 마이그레이션](../media/ms-cloud-germany-migration-opt-in/migration-organization.png)

단계 및 해당 작업을 수행하면 중요한 데이터 및 환경이 Office 365 서비스로 마이그레이션됩니다. 테넌트가 마이그레이션 큐에 추가되고 나면 각 작업이 백end 서비스에서 실행되는 단계 집합으로 완료됩니다. 일부 워크로드에는 관리자(또는 사용자)가 작업을 요구하거나 마이그레이션이 실행되고 마이그레이션이 구성되는 방법에서 설명하는 단계의 사용에 영향을 줄 [수 있습니다.](ms-cloud-germany-transition.md#how-is-the-migration-organized)

다음 섹션에는 마이그레이션의 다양한 단계를 진행할 때 작업에 대한 작업 및 영향이 포함되어 있습니다. 표를 검토하고 조직에 적용할 수 있는 작업이나 효과를 파악합니다. 필요한 경우 각 단계의 단계를 실행할 준비가 되도록 합니다. 필요한 단계를 완료하지 못하면 서비스가 종료되고 Office 365 서비스로의 마이그레이션 완료가 지연될 수 있습니다.

## <a name="sharepoint-online-phase-4-of-9"></a>SharePoint Online(4단계 중 9단계)

| Step(s) | 설명 | 적용 대상 | 영향 |
|:-------|:-----|:-------|:-------|
| SharePoint 및 OneDrive가 전환됩니다. | SharePoint 및 OneDrive는 이 단계에서 도이클란드 Microsoft 클라우드에서 Office 365 서비스로 마이그레이션됩니다. 기존 Microsoft 클라우드 네덜란드 URL(예: )이 `contoso.sharepoint.de` 보존됩니다. 전환 중에 도이치클랜드 또는 Office 365 서비스에서 발급한 토큰이 유효합니다. | SharePoint 고객 | - 마이그레이션 중 두 가지 짧은 기간 동안 콘텐츠는 읽기 전용입니다. 이 시간 동안 SharePoint에서 "콘텐츠를 편집할 수 없습니다." 배너가 예상됩니다. <br><br> - 검색 인덱스는 보존되지 않습니다. 다시 생성하는 데 최대 10일이 걸릴 수 있습니다. <br><br> - SharePoint/OneDrive 콘텐츠는 마이그레이션 중에 두 가지 짧은 기간 동안 읽기 전용으로 설정됩니다. 이 시간 동안 사용자에게 "콘텐츠를 편집할 수 없습니다." 배너가 잠시 표시됩니다. <br><br> - 인덱스를 다시 구성하는 동안 검색 인덱스를 사용할 수 없습니다. 이 기간 동안 검색 쿼리는 전체 결과를 반환하지 않을 수 있습니다. <br><br> - 기존 사이트가 보존됩니다. |
|||||

추가 고려 사항:

- SharePoint Online 마이그레이션이 완료 되면 데이터 인덱스가 다시 작성 됩니다. 검색 인덱스에 종속된 기능은 다시 인덱싱하는 동안 영향을 받을 수 있습니다.

- 조직에서 SharePoint 2010 워크플로를 계속 사용하는 경우 2021년 12월 31일 이후에는 더 이상 작동하지 않습니다. SharePoint 2013 워크플로는 2020년 11월 1일부터 시작되는 새 테넌트에 대해 기본적으로 꺼져 있습니다. SharePoint Online 서비스로의 마이그레이션이 완료된 후 Power Automate 또는 기타 지원되는 솔루션으로 이동하는 것이 좋습니다.

- OneDrive를 독일 지역으로 마이그레이션하면 데이터 인덱스가 다시 생성됩니다. 다시 인덱싱이 진행되는 동안 검색 인덱스에 종속된 기능이 영향을 받을 수 있습니다.

- SharePoint Online 인스턴스가 아직 마이그레이션되지 않은 Microsoft 클라우드 도이클랜드 고객은 SharePoint Online PowerShell 모듈/Microsoft.SharePointOnline.CSOM 버전 16.0.20616.12000 이하를 유지해야 합니다. 그렇지 않으면 PowerShell 또는 클라이언트 쪽 개체 모델을 통해 SharePoint Online에 대한 연결이 실패합니다.

- SharePoint Online 인스턴스가 마이그레이션된 Microsoft 클라우드 도이클랜드 고객은 SharePoint Online PowerShell 모듈/Microsoft.SharePointOnline.CSOM을 버전 16.0.20717.12000 이상으로 업데이트해야 합니다. 그렇지 않으면 PowerShell 또는 클라이언트 쪽 개체 모델을 통해 SharePoint Online에 대한 연결이 실패합니다.


## <a name="exchange-online-phase-5-of-9"></a>Exchange Online(5단계 중 9단계)

| Step(s) | 설명 | 적용 대상 | 영향 |
|:-------|:-----|:-------|:-------|
| 새 독일 지역은 기존 조직 설정에 추가된 후 사서함은 Office 365 서비스로 이동됩니다. | Exchange Online 구성은 전환 조직에 새로운 이동 독일어 지역을 추가합니다. 이 Office 365 서비스 지역은 기본으로 설정되어 내부 부하 분산 서비스가 Office 365 서비스의 적절한 기본 지역으로 사서함을 재배포할 수 있도록 합니다. 이 전환에서 어느 쪽에 있는 사용자(독일 또는 Office 365 서비스)는 동일한 조직에 있으며 두 URL 끝점을 모두 사용할 수 있습니다. | Exchange Online | - 레거시 독일 URL(outlook.office.de)에서 새 Office 365 서비스 URL()로 사용자 및 서비스를 `https://outlook.office365.com` 전환합니다. <br><br> - 사용자는 마이그레이션 중에 레거시 독일 URL을 통해 서비스에 계속 액세스할 수 있습니다. 그러나 마이그레이션이 완료될 때 레거시 URL 사용을 중지해야 합니다. <br><br> - 사용자는 Office Online 기능(일정, 메일, 사용자)에 대한 전 세계 Office 포털을 사용하여 전환해야 합니다. Office 365 서비스로 마이그레이션되지 않은 서비스에 대한 탐색은 마이그레이션될 때까지 작동하지 않습니다. <br><br> - Outlook Web App 동안 공용 폴더 환경을 제공하지 않습니다. |
| AutoDiscover에 대한 사용자 지정 DNS 설정 업데이트| 현재 도이치클랜드 Microsoft 클라우드를 지점하는 자동검사에 대한 고객 관리 DNS 설정은 Exchange Online 단계(5단계)가 완료될 때 Office 365를 지점으로 하여 업데이트해야 합니다. <br> CNAME이 autodiscover-outlook.office.de 있는 기존 DNS 항목은 해당 항목을 autodiscover.outlook.com. | Exchange Online | 자동 검색을 통한 가용성 요청 및 서비스 검색 호출은 Office 365 서비스를 직접 연결합니다. 이러한 DNS 업데이트를 수행하지 않는 고객은 마이그레이션이 완료될 때 자동검출 서비스 문제가 있을 수 있습니다. |
|||||

추가 고려 사항:

- `myaccount.msft.com` Office 365를 컷오버한 후에만 작동하게 될 것입니다. 링크는 해당 시간까지 "문제가 발생했습니다." 오류 메시지가 표시됩니다.

- 다른 Outlook Web App 공유 사서함에 액세스하는 사용자(예: 독일 환경의 사용자가 전역 환경의 공유 사서함에 액세스)에는 두 번째로 인증하라는 메시지가 표시됩니다. 사용자는 먼저 에서 사서함을 인증하고 액세스한 다음 에 있는 공유 `outlook.office.de` 사서함을 열 수 있어야 `outlook.office365.com` 합니다. 다른 서비스에서 호스팅되는 공유 리소스에 액세스할 때 두 번째 인증을 해야 합니다.

- 전환하려는 기존 Microsoft 클라우드 고객 또는 전환하는 고객의 경우 파일 > **Info**> 계정 추가를 사용하여 Outlook에 공유 사서함을 추가하면 일정 권한 보기가 실패할 수 있습니다(Outlook 클라이언트가 Rest API를 사용하려고 `https://outlook.office.de/api/v2.0/Me/Calendars` 시도함). 일정 권한을 보기 위해 계정을 추가하려는 고객은 [Outlook에서](https://support.microsoft.com/office/user-experience-changes-for-sharing-a-calendar-in-outlook-5978620a-fe6c-422a-93b2-8f80e488fdec) 일정을 공유하기 위한 사용자 환경 변경에 설명된 레지스트리 키를 추가하여 이 작업이 성공하도록 할 수 있습니다. 이 레지스트리 키는 그룹 정책을 사용하여 조직 전체에 배포할 수 있습니다.

- 마이그레이션 단계에서 PowerShell cmdlet **New-migrationEndpoint, Set-MigrationEndpoint** 및 **Test-MigrationsServerAvailability를** 사용하면 오류가 발생할 수 있습니다(프록시 오류).  이 문제는 중재 사서함이 전 세계로 마이그레이션했지만 관리자 사서함이 전 세계로 마이그레이션되지 않은 경우 또는 그 반대의 경우 발생합니다. 이 문제를 해결하기 위해 테넌트 PowerShell 세션을 만드는 동안 ConnectionUri의 라우팅 힌트로 중재 **사서함을 사용 합니다.** 예: `New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri "https://outlook.office365.com/powershell-liveid?email=Migration.8f3e7716-2011-43e4-96b1-aba62d229136@TENANT.onmicrosoft.de" -Credential $UserCredential -Authentication Basic -AllowRedirection`

- Exchange Online 하이브리드를 사용하는 경우:

    - Exchange Online 하이브리드 고객은 이 전환의 일부로 HCW(하이브리드 구성 마법사)를 여러 번 실행해야 합니다. 마이그레이션 **5단계를** 시작하기 전에 Exchange Online 하이브리드 고객은 Office 365 Germany 모드에서 최신 버전의 HCW를 실행하여 Office 365 전역으로의 마이그레이션을 위한 사내 구성을 준비해야 합니다. 마이그레이션 **5단계(메시지** 센터 알림이 게시될 때)가 완료될 때 Office 365 Worldwide 설정을 사용하여 전역 서비스를 설정하기 위해 HCW를 실행해야 합니다. 사용자 지정 도메인을 사용하는 경우 추가 DNS 업데이트가 필요합니다.

마이그레이션의 조직과 Exchange Online 리소스가 마이그레이션된 후 조직의 차이점에 대한 자세한 내용은 새 독일 데이터 센터 지역의 [Office 365](ms-cloud-germany-transition-experience.md)서비스로 마이그레이션하는 동안 고객 환경의 정보를 검토하세요.

## <a name="exchange-online-protection-phase-6-of-9"></a>Exchange Online Protection(6단계 중 9단계)

백 엔드 EOP(Exchange Online Protection) 기능은 새 독일 지역에 복사됩니다. 

| Step(s) | 설명 | 적용 대상 | 영향 |
|:-------|:-----|:-------|:-------|
| Exchange Online 라우팅 마이그레이션 및 기록 메시지 세부 정보 | Exchange Online을 사용하면 외부 호스트에서 Office 365로 라우팅할 수 있습니다. 외부 MX 레코드는 EOP 서비스로 라우팅하기 위해 전환됩니다. 테넌트 구성 및 기록 세부 정보가 마이그레이션됩니다. | Exchange Online 고객 | - Microsoft 관리 DNS 항목이 Office 365 Germany EOP에서 Office 365 서비스로 업데이트됩니다. <br><br> - 고객은 EOP 이중 쓰기가 EOP 마이그레이션을 위해 30일 동안 대기해야 합니다. 그렇지 않으면 데이터 손실이 있을 수 있습니다. |
|||||



## <a name="skype-for-business-online-phase-7-of-9"></a>비즈니스용 Skype Online(7단계 중 9단계)

| Step(s) | 설명 | 적용 대상 | 영향 |
|:-------|:-----|:-------|:-------|
| 비즈니스용 Skype를 Teams로 마이그레이션 | 기존 비즈니스용 Skype 고객은 유럽의 Office 365 서비스로 마이그레이션된 다음 Office 365 서비스의 독일 지역의 Microsoft Teams로 전환됩니다. | 비즈니스용 Skype 고객 | - 사용자는 마이그레이션 날짜에 비즈니스용 Skype에 로그인할 수 없습니다. 마이그레이션이 시작되기 10일 전에 관리 센터에 게시하여 마이그레이션이 언제 수행될지 알려 주며 마이그레이션을 시작할 때 다시 알 수 있습니다. <br><br> - 정책 구성이 마이그레이션됩니다. <br><br> - 사용자는 Teams로 마이그레이션됩니다. 마이그레이션 후 더 이상 비즈니스용 Skype가 없습니다. <br><br> - 사용자에게 Teams 데스크톱 클라이언트가 설치되어 있어야 합니다. 설치는 비즈니스용 Skype 인프라의 정책을 통해 10일 동안 진행되지만 실패하는 경우 사용자는 클라이언트를 다운로드하거나 지원되는 브라우저에 연결해야 합니다. <br><br> - 연락처 및 모임이 Teams로 마이그레이션됩니다. <br><br> - 사용자는 고객 DNS 항목이 완료될 때까지 서비스가 Office 365 서비스로 전환되는 동안 비즈니스용 Skype에 로그인할 수 없습니다. <br><br> - 연락처 및 기존 모임은 비즈니스용 Skype 모임으로 계속 작동됩니다. |
|||||


## <a name="office-apps-phase-8-of-9"></a>Office 앱(8단계 중 9단계)

| Step(s) | 설명 | 적용 대상 | 영향 |
|:-------|:-----|:-------|:-------|
| 클라이언트, Office 클라이언트가 컷오버하는 동안 Azure AD는 Office 365 서비스를 지점으로 하는 테넌트 범위를 마무리합니다. | 이 구성 변경을 통해 Office 클라이언트는 Office 365 서비스 끝점을 업데이트하고 이를 지점으로 할 수 있습니다. | 모든 Office 고객 | - 사용자에게 모든 _Office_ 앱을 닫은 다음 다시 로그인(또는 클라이언트를 강제로 다시 시작하고 사용자가 로그인하도록 설정)하여 Office 클라이언트가 변경 내용을 선택할 수 있도록 합니다. <br><br> - 사용자 및 지원 센터  직원에게 72시간 이내에 Office 앱을 다시 활성화하라는 Office 배너가 표시될 수 있습니다. <br><br> - 개인 컴퓨터의 모든 Office 응용 프로그램을 닫아야 합니다. 사용자는 로그인한 다음 다시 로그인해야 합니다. 노란색 정품 인증 표시줄에서 로그인하여 Office 365 서비스에 대해 다시 정품 인증합니다. <br><br> - 공유 컴퓨터는 개인 컴퓨터와 유사한 작업이 필요하며 특별한 절차가 필요하지 않습니다. <br><br> - 모바일 장치에서 사용자는 앱에서 로그인하고 닫은 다음 다시 로그인해야 합니다. |
|||||


## <a name="office-services"></a>Office Services

Office에서 가장 최근에 사용한(MRU) 서비스는 마이그레이션이 아닌 독일 서비스에서 Office 365 서비스로의 조율입니다. Office 365 서비스 쪽의 MRU 링크만 Office 365 포털에서 마이그레이션한 Office.com 표시됩니다. 독일 서비스의 MRU 링크는 Office 365 서비스의 MRU 링크로 표시되지 않습니다. Office 365에서는 테넌트 마이그레이션이 완료된 후에만 MRU 링크에 액세스할 수 있습니다.

## <a name="subscription"></a>구독

| Step(s) | 설명 | 적용 대상 | 영향 |
|:-------|:-----|:-------|:-------|
| 동의 없이는 고객을 마이그레이션할 수 없습니다. | Microsoft는 두 가지 방법 중 하나를 사용하여 마이그레이션할 수 있는권을 얻게 하여 Microsoft가 데이터 및 서비스를 Office 365 서비스 인스턴스로의 전환을 오케스트레이션할 수 있습니다. <br> 관리자는 Microsoft 주도 마이그레이션에 옵트인(opt-in)합니다. <br> 고객은 2020년 5월 1일 이후에 Microsoft 클라우드 도이클란드 테넌트의 구독을 갱신합니다. 매월 이러한 고객에게 마이그레이션을 알리고, 30일 동안 기다렸다가 고객에게 취소할 수 있는 기회를 제공한 다음 ICM에서 직접 옵트인(opt in)합니다. | 모든 Office 고객 | - 테넌트가 마이그레이션에 동의된 것으로 표시되어 관리 센터에 확인이 표시됩니다. <br><br> - Acknowledgment is posted to Cloud Germany Message Center Tenant. 서비스 구성은 도이치란드 Microsoft 클라우드 끝점에서 계속됩니다. <br><br> - 마이그레이션 단계 상태에 대한 업데이트를 위해 메시지 센터를 모니터링합니다. |
| 구독이 전송된 후 라이선스가 다시 재배치됩니다. | 테넌트가 Office 365 서비스로 전환된 후 해당 Office 365 서비스 구독은 전달된 Microsoft 클라우드 도이치랜드 구독을 구매합니다. 할당된 Microsoft 클라우드 라이선스가 있는 사용자에게는 Office 365 서비스 라이선스가 할당됩니다. 레거시 Microsoft 클라우드 도이치랜드 구독은 완료 시 Office 365 서비스 테넌트에서 제거됩니다. | 모든 Office 고객 | - 이 단계에서는 기존 구독에 대한 변경 내용이 차단됩니다(예: 새 구독 구매 또는 시트 수 변경 없음). <br><br> - 라이선스 할당 변경이 차단됩니다. <br><br> - 도이치랜드 Microsoft 클라우드 구독이 해당 Office 365 서비스 구독으로 마이그레이션됩니다. 구독의 Office 365 서비스 제공은 Microsoft(제품 _매핑)에 의해 정의됩니다._ <br><br> - Office 365 서비스에서 제공하는 기능(서비스 계획)의 수는 원래 Microsoft 클라우드 도이치랜드 제품보다 클 수 있습니다. Office 365 서비스의 사용자 라이선스는 유사한 Microsoft 클라우드 도이클란드 기능(서비스 계획)에 동일하게 할당됩니다. 모든 사용자의 사용자 라이선스가 새 기능에 자동으로 할당됩니다. 관리자는 필요한 경우 해당 라이선스를 사용하지 않도록 설정하기 위한 명시적 조치를 취해야 합니다. <br><br> - 구독 마이그레이션이 완료되면 Office 365 서비스 및 독일 구독이 모두 Office 365 관리 포털에 표시될 수 있으며 독일 구독 상태는 비프로비전되지 _않습니다._ <br><br> - 사용자는 새 Office 365 서비스 구독에 대한 라이선스를 다시 재배정합니다. 독일 구독 또는 SKU GUID에 종속된 모든 고객 프로세스는 손상될 수 있으며 Office 365 서비스 제공으로 수정해야 합니다. <br><br> - Office 365 서비스의 새 구독은 새 기간(월별/분기별/년)을 통해 구입하며, 고객은 도이치클라우스 Microsoft 클라우드 구독의 미사용 잔액에 대해 비분산 환불을 받게 됩니다. <br><br> - 파트너 Microsoft 클라우드 도이치랜드 테넌트는 마이그레이션되지 않습니다. CSP 고객은 동일한 파트너의 새 Office 365 서비스 테넌트에서 Office 365 서비스로 마이그레이션됩니다. 고객 마이그레이션 후 파트너는 Office 365 서비스 테넌트에서만 이 고객을 관리할 수 있습니다. <br><br> - 테넌트 관리자가 사용하지 않도록 설정하지 않은 경우 추가 기능(예: Microsoft Planner 및 Microsoft Flow)을 사용할 수 있습니다. 사용자의 라이선스에 할당된 서비스 계획을 사용하지 않도록 설정하는 방법에 대한 자세한 내용은 사용자 라이선스를 할당하는 동안 [Microsoft 365](disable-access-to-services-while-assigning-user-licenses.md)서비스에 대한 액세스 사용 안 하도록 설정을 참조하세요.  |
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
- [Azure AD,](ms-cloud-germany-transition-azure-ad.md) [장치,](ms-cloud-germany-transition-add-devices.md) [환경](ms-cloud-germany-transition-add-experience.md)및 [AD FS에](ms-cloud-germany-transition-add-adfs.md)대한 추가 정보.

클라우드 앱:

- [Dynamics 365 마이그레이션 프로그램 정보](https://aka.ms/d365ceoptin)
- [Power BI 마이그레이션 프로그램 정보](https://aka.ms/pbioptin)
- [Microsoft Teams 업그레이드 시작하기](https://aka.ms/SkypeToTeams-Home)
