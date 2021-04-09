---
title: 마이그레이션 단계 도이클란드 Microsoft 클라우드에서 마이그레이션에 대한 작업 및 영향)
ms.author: andyber
author: andybergen
manager: laurawi
ms.date: 03/05/2021
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
ms.openlocfilehash: e3ed1d76a755ce6326ac6ae53b990136a10b564a
ms.sourcegitcommit: 437bdbf3f99610869811e80432a59b5f244f7a87
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2021
ms.locfileid: "51644719"
---
# <a name="migration-phases-actions-and-impacts-for-the-migration-from-microsoft-cloud-deutschland"></a>마이그레이션 단계 도이클란드 Microsoft 클라우드에서 마이그레이션에 대한 작업 및 영향

독일 Microsoft 클라우드(MCD)에서 Microsoft Office 365 전역 서비스의 "독일" 지역으로의 테넌트 마이그레이션은 단계 집합 및 각 워크로드에 대해 구성된 작업으로 실행됩니다. 이 그림에서는 새로운 독일 데이터 센터로의 10개 마이그레이션 단계를 보여 주었다.

![새 독일 데이터 센터로의 10단계 마이그레이션](../media/ms-cloud-germany-migration-opt-in/migration-organization.png)

조직의 전체 크기 및 복잡도에 따라 마이그레이션 프로세스가 몇 주 동안 완료됩니다. 마이그레이션이 진행 중일 때 사용자와 관리자는 이 설명서에 자세히 설명된 변경 사항과 함께 서비스를 계속 사용할 수 있습니다. 그래픽 및 테이블은 마이그레이션 중의 단계와 단계를 정의합니다.

|단계|Duration|책임자|설명|
|:--------|:--------|:--------|:--------|
|Opt-In|시간|고객|조직을 마이그레이션에 옵트인합니다.|
|사전 작업|일|고객|마이그레이션을 위해 사용자, 작업소 및 네트워크를 준비하는 데 필요한 작업을 완료합니다.|
|Azure AD(Azure Active Directory)|1~2일|Microsoft|Azure AD 조직을 전 세계로 마이그레이션합니다.|
|Azure|주|고객|새 전 세계 Azure 구독을 만들고 Azure 서비스를 전환합니다.|
|구독 & 라이선스 전환|1~2일|Microsoft|전 세계 구독을 구입하고, 도이치스크란드 Microsoft 클라우드 구독을 취소하고, 사용자 라이선스를 전환합니다.|
|SharePoint 및 OneDrive|15일 이상|Microsoft|SharePoint 및 비즈니스용 OneDrive 콘텐츠를 마이그레이션하고 URL을 sharepoint.de 합니다.|
|Exchange Online|15일 이상|Microsoft|Exchange Online 콘텐츠를 마이그레이션하고 전 세계 URL로 전환합니다.|
|보안 및 규정 준수|1~2일|Microsoft|보안 및 & 정책 및 콘텐츠를 전환합니다.|
|비즈니스용 Skype|1~2일|Microsoft|비즈니스용 Skype에서 Microsoft Teams로 전환|
|Power BI & Dynamics 365|15일 이상|Microsoft|Power BI 및 Dynamics 365 콘텐츠를 마이그레이션합니다.|
|Azure AD 마무리|1~2일|Microsoft|전 세계 테넌트 컷오버를 완료합니다.|
|Clean-Up|1~2일|고객|AD FS(Active Directory Federation Services) 신뢰 파티 트러스트, Azure AD Connect 및 Office 클라이언트 다시 시작과 같은 Microsoft 클라우드에 대한 레거시 연결을 정리합니다.|
|끝점 사용 안|30일|Microsoft|Azure AD가 마무리된 후 30일이 지난 후 Microsoft 클라우드 도이치랜드 Azure AD 서비스는 전환된 조직의 끝점 액세스를 중지합니다. 인증과 같은 끝점 요청은 도이치랜드 Microsoft 클라우드 서비스에 대해 이 시점부터 실패합니다. |


단계 및 해당 작업을 수행하면 중요한 데이터 및 환경이 Office 365 전역 서비스로 마이그레이션됩니다. 테넌트가 마이그레이션 큐에 추가되고 나면 각 작업이 백end 서비스에서 실행되는 단계 집합으로 완료됩니다. 일부 워크로드에는 관리자(또는 사용자)가 작업을 요구하거나 마이그레이션이 실행되고 마이그레이션이 구성되는 방법에서 설명하는 단계의 사용에 영향을 줄 [수 있습니다.](ms-cloud-germany-transition.md#how-is-the-migration-organized)

다음 섹션에는 마이그레이션의 다양한 단계를 진행할 때 작업에 대한 작업 및 영향이 포함되어 있습니다. 표를 검토하고 조직에 적용할 수 있는 작업이나 효과를 파악합니다. 필요한 경우 각 단계의 단계를 실행할 준비가 되도록 합니다. 필요한 단계를 완료하지 못하면 서비스가 종료되고 Office 365 서비스로의 마이그레이션 완료가 지연될 수 있습니다.

## <a name="phase-opt-in"></a>단계: Opt-In

**적용 사항:** 도이치클랜드(MCD) Microsoft에서 호스팅되는 Office 365 테넌트가 있는 모든 고객은 동의 없이 MCD에 호스트된 Office 365 테넌트를 마이그레이션할 수 없습니다.

| Step(s) | 설명 | 영향 |
|:-------|:-----|:-------|
|**고객 작업:** 마이그레이션에 대한 동의 부여| 고객은 Microsoft가 Office 365 전역 서비스 인스턴스로의 데이터 및 서비스 전환을 조율하고 마이그레이션할 수 있는 권한을 얻을 수 있도록 마이그레이션에 대한 동의를 부여합니다. 두 가지 방법이 있습니다. <ol><li>Office 365 테넌트 관리자는 Microsoft 주도 마이그레이션에 옵트인합니다. </li><li> 고객은 2020년 5월 1일 이후에 MCD Office 365 테넌트의 구독을 갱신했습니다. Microsoft는 매월 이러한 고객에게 마이그레이션을 알리고 30일 동안 기다렸다가 취소할 수 있는 기회를 제공한 다음 직접 옵트인(opt in)합니다.</li></ol> | <ul><li>테넌트가 마이그레이션에 동의한 것으로 표시되어 관리 센터에 확인이 표시됩니다. </li><li>Acknowledgment is posted to the Office 365 tenant Message Center. 서비스 구성은 도이치란드 Microsoft 클라우드 끝점에서 계속됩니다. </li><li> </li></ul>
|**테넌트 관리자:** 메시지 모니터링|테넌트 관리자는 이 시간부터 마이그레이션 단계 상태에 대한 업데이트를 Office 365 메시지 센터에서 모니터링해야 합니다.|고객은 필요한 작업을 제시간에 실행할 수 있습니다.
||||

## <a name="phase-1-before-the-migration-starts"></a>1단계: 마이그레이션 시작 전

모든 고객에게 적용되는 마이그레이션 준비 단계에 [익숙해야 합니다.](ms-cloud-germany-transition-add-pre-work.md)

소유한 하나 또는 여러 DNS 네임스페이스에서 _msoid라는_ DNS CNAME을 설정한 경우 8단계가 끝날 때까지 CNAME을 제거해야 합니다. 8단계가 끝나기 전에 CNAME _msoid를_ 제거할 수 있습니다. [DNS에 대한 사전 작업 을 참조합니다.](ms-cloud-germany-transition-add-pre-work.md#dns-entries-for-custom-domains)

도이치랜드 Microsoft 클라우드 인스턴스에서 Office 365 및 Azure에 대해 Single Sign-On을 사용하는 경우 그에 따라 Azure 구독 마이그레이션을 준비하고 예약해야 합니다. Microsoft Azure의 사전 [작업도 이해해야 합니다.](ms-cloud-germany-transition-add-pre-work.md#microsoft-azure)

### <a name="azure-ad-connect-with-ad-fs-federation"></a>AD FS 페더ation을 사용하여 Azure AD Connect
**적용 사항:** AD FS 페더러가 있는 고객

**적용된 경우:** 2단계가 시작되기 전

AD FS(Active Directory Federation Services)를 사용하는 경우 2단계가 시작되기 전에 Office 365 Global 서비스에 대한  신뢰자 트러스트 추가 전후에 [ADFS](ms-cloud-germany-transition-azure-ad.md) 구성을 백업해야 합니다.

## <a name="phase-2-azure-ad-migration"></a>2단계: Azure AD 마이그레이션
이 단계에서는 Azure Active Directory가 새 데이터 센터 지역으로 마이그레이션된 후 활성화됩니다. 이전 Azure AD 끝점은 계속 사용할 수 있습니다.

## <a name="phase-3-subscription-transfer"></a>3단계: 구독 이전

**적용 사항:** 도이치클라일랜드(MCD)에서 호스트된 Office 365 테넌트가 있는 모든 고객

파트너 Microsoft 클라우드 도이치랜드 테넌트는 마이그레이션되지 않습니다. CSP 고객은 동일한 파트너의 새 Office 365 서비스 테넌트에서 Office 365 서비스로 마이그레이션됩니다. 고객 마이그레이션 후 파트너는 Office 365 서비스 테넌트에서만 이 고객을 관리할 수 있습니다.

| Step(s) | 설명 | 영향 |
|:-------|:-------|:-------|
| 구독이 전송됩니다.| Microsoft 클라우드 도이치랜드 구독은 해당 Office 365 전역 서비스 구독으로 마이그레이션됩니다. <ul><li>이 구독의 Office 365 전역 서비스 서비스는 Microsoft(제품 _매핑)로 정의됩니다._</li><li> 해당 Office 365 전역 서비스 구독은 전달된 Microsoft 클라우드 도이치랜드 구독에 대한 Office 365 Global 인스턴스에서 구매합니다.</li><li>레거시 Microsoft 클라우드 도이치랜드 구독은 완료 시 Office 365 서비스 테넌트에서 제거됩니다.</li></ul>| <ul><li>이 단계에서는 기존 구독에 대한 변경 사항(예: 새 구독 구매 또는 시트 수 변경 없음)이 차단됩니다.</li><li>라이선스 할당 변경이 차단됩니다.</li><li>구독 마이그레이션이 완료되면 Office 365 서비스 및 Microsoft 클라우드 도이치랜드 구독이 모두 Office 365 관리 포털에 표시될 수 있으며, 상태는 도이프란드 Microsoft 클라우드 구독의 상태(디비전되지 않습니다.)입니다. </li><li>도이치클라드 Microsoft 클라우드 구독 또는 SKU GUID에 종속된 모든 고객 프로세스는 손상될 수 있으며 Office 365 서비스 제공으로 수정해야 합니다. </li><li>Office 365 서비스의 새 구독은 새 기간(월별/분기별/년)을 통해 구입하며 고객은 도이치랜드 Microsoft 클라우드 구독의 미사용 잔액에 대해 비분산 환불을 받게 됩니다. </li></ul> |
|라이선스 재할당|할당된 Microsoft 클라우드 라이선스가 있는 사용자에게는 Office 365 Global 인스턴스에 라이선스가 할당됩니다.|<ul><li>사용자는 새 Office 365 서비스 구독에 대한 라이선스를 다시 재배정합니다. 모든 사용자의 사용자 라이선스가 새 기능에 자동으로 할당됩니다.</li><li>Office 365 서비스에서 제공하는 기능(서비스 계획)의 수는 도이치랜드의 원래 Microsoft 클라우드 제품보다 클 수 있습니다. Office 365 서비스의 사용자 라이선스는 유사한 Microsoft 클라우드 도이클란드 기능(서비스 계획)에 동일하게 할당됩니다. </li></ul> 
|**관리자 작업** 기능 사용 안|관리자는 필요한 경우 해당 기능을 사용하지 않도록 설정하기 위한 명시적 조치를 취해야 합니다. |<ul><li>사용자가 포털에서 알 수 없는 새 서비스를 볼 수 있습니다.</li><li>테넌트 관리자가 사용하지 않도록 설정하지 않은 경우 추가 기능(예: Microsoft Planner 및 Microsoft Flow)을 사용할 수 있습니다. 사용자의 라이선스에 할당된 서비스 계획을 사용하지 않도록 설정하는 방법에 대한 자세한 내용은 사용자 라이선스를 할당하는 동안 [Microsoft 365](disable-access-to-services-while-assigning-user-licenses.md)서비스에 대한 액세스 사용 안 하도록 설정을 참조하세요.</li></ul>
|**관리자 작업**|Office 365 서비스 제공으로 도이치랜드 Microsoft 클라우드 구독 또는 SKU GUID에 종속된 고객 프로세스 변경|고객 프로세스는 계속 작동됩니다.
||||

**적용대:** Office 365 파트너 포털을 사용하는 Microsoft 파트너

2단계와 3단계 사이에는 파트너 포털에 액세스할 수 없습니다. 이 시간 동안 파트너는 파트너 포털에서 테넌트 정보에 액세스하지 못하게 될 수 있습니다. 마이그레이션마다 다르기 때문에 내게 필요한 경우의 기간은 시간일 수 있습니다.


## <a name="phase-4-sharepoint-online"></a>4단계: SharePoint Online

**적용 사항:** SharePoint Online을 사용하는 모든 고객

SharePoint 2013 워크플로를 계속 사용하는 경우 SharePoint Online 마이그레이션 중에 SharePoint 2013 워크플로 사용을 제한합니다.

| Step(s) | 설명 | 영향 |
|:-------|:-----|:-------|
| SharePoint 및 OneDrive가 전환됩니다. | 이 단계에서 SharePoint Online 및 비즈니스용 OneDrive는 도이치란드 Microsoft 클라우드에서 Office 365 전역 서비스로 마이그레이션됩니다.<br><ul><li>기존 Microsoft 클라우드 네덜란드 URL(예: )이 `contoso.sharepoint.de` 보존됩니다.</li><li>기존 사이트는 보존됩니다.</li><li>도이치랜드 Microsoft 클라우드 또는 Office 365 전역 서비스 인스턴스에서 STS(Security Token Service)에서 발급한 클라이언트 쪽 인증 토큰은 전환 중에 유효합니다.</li></ul>|<ul><li>콘텐츠는 마이그레이션 중에 잠시 동안 읽기 전용으로 설정됩니다. 이 시간 동안 SharePoint에서 "콘텐츠를 편집할 수 없습니다." 배너가 예상됩니다.</li><li>검색 인덱스는 보존되지 않습니다. 다시 생성하는 데 최대 10일이 걸릴 수 있습니다.</li><li>SharePoint Online 및 비즈니스용 OneDrive 콘텐츠는 마이그레이션 중에 두 가지 짧은 기간 동안 읽기 전용으로 설정됩니다. 이 시간 동안 사용자에게 "콘텐츠를 편집할 수 없습니다." 배너가 잠시 표시됩니다.</li><li>SharePoint Online 마이그레이션이 완료된 후 인덱스를 다시 생성하는 동안 SharePoint Online 및 비즈니스용 OneDrive 콘텐츠에 대한 검색 결과를 사용할 수 없게 될 수 있습니다. 이 기간 동안 검색 쿼리는 전체 결과를 반환하지 않을 수 있습니다. SharePoint Online 뉴스와 같은 검색 인덱스에 종속된 기능은 다시 인덱싱하는 동안 영향을 받을 수 있습니다.</li><li>마이그레이션 중에 SharePoint 2013 워크플로가 중단되어 마이그레이션 후에 다시 게시해야 합니다.</li></ul>
|**SPO 관리자:** SharePoint 2013 워크플로 다시 게시| SharePoint Online 관리자는 마이그레이션 후 SharePoint 2013 워크플로를 다시 게시합니다.|SharePoint 2013 워크플로를 사용할 수 있습니다.
|**PowerShell 사용자:** 새 모듈로 업데이트| SharePoint Online Powershell 모듈의 모든 사용자는 SharePoint Online 마이그레이션이 완료된 후 모듈/Microsoft.SharePointOnline.CSOM을 버전 16.0.20717.12000 이상으로 업데이트해야 합니다. 완료는 메시지 센터에서 전달됩니다.| PowerShell 또는 클라이언트 쪽 개체 모델을 통한 SharePoint Online은 더 이상 실패하지 않습니다.
||||

추가 고려 사항:

- 조직에서 SharePoint 2010 워크플로를 계속 사용하는 경우 2021년 12월 31일 이후에는 더 이상 작동하지 않습니다. SharePoint 2013 워크플로는 2020년 11월 1일부터 시작되는 새 테넌트에 대해 기본적으로 꺼져 있습니다. SharePoint Online 서비스로의 마이그레이션이 완료된 후 Power Automate 또는 기타 지원되는 솔루션으로 이동하는 것이 좋습니다.

- SharePoint Online 인스턴스가 아직 마이그레이션되지 않은 Microsoft 클라우드 도이클랜드 고객은 SharePoint Online PowerShell 모듈/Microsoft.SharePointOnline.CSOM 버전 16.0.20616.12000 이하를 유지해야 합니다. 그렇지 않으면 PowerShell 또는 클라이언트 쪽 개체 모델을 통해 SharePoint Online에 대한 연결이 실패합니다.


> [!NOTE]
> eDiscovery를 사용하는 경우 [eDiscovery](ms-cloud-germany-transition-add-experience.md)마이그레이션 환경을 알고 있어야 합니다.

## <a name="phase-5-exchange-online"></a>5단계: Exchange Online 

**다음에 적용됩니다.** Exchange Online을 사용하는 모든 고객

Exchange Online 하이브리드를 사용하는 경우: Exchange Online 하이브리드 관리자는 이 전환의 일부로  **HCW(하이브리드** 구성 마법사)를 여러 번 실행해야 합니다. 마이그레이션 [5단계가](ms-cloud-germany-transition-add-pre-work.md#exchange-online-hybrid-customers) 시작되기 전에 Exchange 사전 작업 **적용** Exchange Online 하이브리드 고객은 Office 365 전역 서비스로의 마이그레이션을 위해 "Office 365 Germany" 모드에서 최신 버전의 Exchange HCW(하이브리드 구성 마법사)를 실행해야 합니다.

마이그레이션 **단계 9(메시지** 센터 알림이 게시될 때)가 끝나면 Office 365 Worldwide 설정을 사용하여 HCW를 다시 실행하여 Office 365 전역 서비스를 설정해야 합니다.

5단계에서 사용자 사진을 수정하려면 5단계에서 Exchange Online Set-UserPhoto [참조하세요.](#exchange-online-powershell)

| Step(s) | 설명 | 영향 |
|:-------|:-------|:-------|
|**관리자:** 사서함 이동 중지|온보드 또는 오프보더 사서함 이동을 중지하거나 삭제합니다. 즉, Exchange 온-프레미스와 Exchange Online 간에 사서함을 이동하지 않습니다.  | 이렇게 하면 사서함 이동 요청이 오류와 함께 실패하지 않습니다. 이렇게 하지 못하면 서비스 또는 Office 클라이언트가 실패할 수 있습니다. |
| 새 지역 "독일"이 조직 설정에 추가됩니다. | Exchange Online 구성은 전환 조직에 새로운 이동 독일어 지역을 추가합니다. | |
| Exchange Online 사서함은 도이치클란드 Microsoft 클라우드에서 Office 365 전역 서비스로 이동됩니다.| Office 365 전역 서비스 지역이 기본값으로 설정되어 내부 부하 분산 서비스가 Office 365 서비스의 적절한 기본 지역으로 사서함을 재배포할 수 있습니다. 이 전환에서 어느 쪽에 있는 사용자(MCD 또는 전역 서비스)는 동일한 조직에 있으며 두 URL 끝점을 모두 사용할 수 있습니다. |<ul><li>레거시 MCD URL(outlook.office.de)에서 새 Office 365 서비스 URL()로 사용자 및 서비스를 `https://outlook.office365.com` 전환합니다.</li><li>사용자는 마이그레이션 중에 레거시 MCD URL을 통해 서비스에 계속 액세스할 수 있습니다. 그러나 마이그레이션이 완료될 때 레거시 URL 사용을 중지해야 합니다.</li><li>사용자는 Office Online 기능(일정, 메일, 사용자)에 대한 전 세계 Office 포털 사용으로 전환해야 합니다. Office 365 서비스로 마이그레이션되지 않은 서비스에 대한 탐색은 마이그레이션될 때까지 작동하지 않습니다. </li><li>마이그레이션 Outlook Web App 동안 공용 폴더 환경을 제공하지 않습니다. </li></ul>|
| **관리자:** 자동검사에 대한 사용자 지정 DNS 설정 업데이트| 현재 도이치클란드 Microsoft 클라우드를 지점하는 자동 검사에 대한 고객 관리 DNS 설정을 업데이트하여 Exchange Online 단계(5단계)의 완료 시 Office 365 Global 끝점을 참조해야 합니다. <br> CNAME이 autodiscover-outlook.office.de 기존 DNS 항목을 업데이트하여 해당 항목을 autodiscover.outlook.com. |  자동 검색을 통한 가용성 요청 및 서비스 검색 호출은 Office 365 서비스를 직접 연결합니다. 이러한 DNS 업데이트를 수행하지 않는 고객은 마이그레이션이 완료될 때 자동검출 서비스 문제가 있을 수 있습니다. |
||||

### <a name="exchange-online-powershell"></a>Exchange Online PowerShell
**다음에 적용됩니다.** Exchange Online PowerShell을 사용하는 Exchange Online 관리자

마이그레이션 단계에서 PowerShell cmdlet **New-MigrationEndpoint, Set-MigrationEndpoint** 및 **Test-MigrationsServerAvailability를** 사용하면 오류가 발생할 수 있습니다(프록시 오류).  이 문제는 중재 사서함이 전 세계로 마이그레이션했지만 관리자 사서함이 전 세계로 마이그레이션되지 않은 경우 또는 그 반대의 경우 발생합니다. 이 문제를 해결하기 위해 테넌트 PowerShell 세션을 만드는 동안 ConnectionUri의 라우팅 힌트로 중재 **사서함을 사용 합니다.** 예를 들어 다음과 같습니다.

```powershell
New-PSSession 
    -ConfigurationName Microsoft.Exchange 
    -ConnectionUri "https://outlook.office365.com/powershell-liveid?email=Migration.8f3e7716-2011-43e4-96b1-aba62d229136@<tenant>.onmicrosoft.de"
    -Credential $UserCredential
    -Authentication Basic
    -AllowRedirection
```
PowerShell cmdlet **Set-UserPhoto를** 사용하여 사용자 사서함이 마이그레이션되어 있지만 관리자 사서함이 마이그레이션되지 않은 경우 또는 그 반대로 마이그레이션하면 오류가 발생합니다. 이 경우 관리자는 테넌트 PowerShell 세션을 만드는 동안 사진을 변경해야 하는 사용자의 전자 메일 ID를 `ConnectionUri` 전달해야 합니다. 
```powershell
-ConnectionUri "https://outlook.office.de/powershell-liveid?email=<user_email>" 
```
 여기서 은 사용자 사서함의 전자 메일 `<user_email>` ID에 대한 자리 표시됩니다. 

추가 고려 사항:
<!--
    The statement below is not clear. What does myaccount.microsoft.com mean?


- `myaccount.microsoft.com` will only work after the tenant cutover in phase 9. Links will produce "something went wrong" error messages until that time.
-->
- 다른 Outlook Web App 공유 사서함에 액세스하는 사용자(예: MCD 환경의 사용자가 전역 환경의 공유 사서함에 액세스)에는 두 번째 인증 메시지가 표시됩니다. 사용자는 먼저 에서 사서함을 인증하고 액세스한 다음 에 있는 공유 `outlook.office.de` 사서함을 열 수 있어야 `outlook.office365.com` 합니다. 다른 서비스에서 호스팅되는 공유 리소스에 액세스할 때 두 번째 인증을 해야 합니다.

- 전환하려는 기존 Microsoft 클라우드 고객 또는 전환하는 고객의 경우 파일 > **Info**> 계정 추가를 사용하여 Outlook에 공유 사서함을 추가하면 일정 권한 보기가 실패할 수 있습니다(Outlook 클라이언트가 Rest API를 사용하려고 `https://outlook.office.de/api/v2.0/Me/Calendars` 시도). 일정 권한을 보기 위해 계정을 추가하려는 고객은 [Outlook에서](https://support.microsoft.com/office/user-experience-changes-for-sharing-a-calendar-in-outlook-5978620a-fe6c-422a-93b2-8f80e488fdec) 일정을 공유하기 위한 사용자 환경 변경에 설명된 레지스트리 키를 추가하여 이 작업이 성공하도록 할 수 있습니다. 이 레지스트리 키는 그룹 정책을 사용하여 조직 전체에 배포할 수 있습니다.

마이그레이션의 조직과 Exchange Online 리소스가 마이그레이션된 후 조직의 차이점에 대한 자세한 내용은 새 독일 데이터 센터 지역의 [Office 365](ms-cloud-germany-transition-experience.md)서비스로 마이그레이션하는 동안 고객 환경의 정보를 검토하세요.


## <a name="phase-6-exchange-online-protection--security-and-compliance"></a>6단계: Exchange Online Protection/보안 및 규정 준수

**다음에 적용됩니다.** Exchange Online을 사용하는 모든 고객<br>

백 엔드 EOP(Exchange Online Protection) 기능은 새 지역 "독일"에 복사됩니다.

| Step(s) | 설명 | 영향 |
|:-------|:-------|:-------|
| Exchange Online 라우팅 마이그레이션 및 기록 메시지 세부 정보 | Exchange Online을 사용하면 외부 호스트에서 Office 365로 라우팅할 수 있습니다. 외부 MX 레코드는 EOP 서비스로 라우팅하기 위해 전환됩니다. 테넌트 구성 및 기록 세부 정보가 마이그레이션됩니다. |<ul><li>Microsoft에서 관리하는 DNS 항목은 Office 365 Germany EOP에서 Office 365 서비스로 업데이트됩니다.</li><li>고객은 EOP 이중 쓰기가 EOP 마이그레이션을 위해 30일 동안 기다려야 합니다. 그렇지 않으면 데이터 손실이 있을 수 있습니다.</li></ul>|
||||

## <a name="phase-7-skype-for-business-online"></a>7단계: 비즈니스용 Skype Online

**다음에 적용됩니다.** 비즈니스용 Skype Online을 사용하는 모든 고객

비즈니스용 [Skype Online](ms-cloud-germany-transition-add-pre-work.md#skype-for-business-online) 마이그레이션 절차에 익숙해야 합니다.

<!--
    Question from ckinder
    the PowerShell command seems to be incomplete
-->

| Step(s) | 설명 | 영향 |
|:-------|:-------|:-------|
| 비즈니스용 Skype를 Teams로 마이그레이션 | 기존 비즈니스용 Skype 고객은 유럽의 Office 365 전역 서비스로 마이그레이션된 다음 Office 365 서비스의 "독일" 지역의 Microsoft Teams로 전환됩니다. |<ul><li>사용자는 마이그레이션 날짜에 비즈니스용 Skype에 로그인할 수 없습니다. 마이그레이션이 시작되기 10일 전에 관리 센터에 게시하여 마이그레이션이 언제 수행될지 알려 주며 마이그레이션을 시작할 때 다시 알 수 있습니다.</li><li> 정책 구성이 마이그레이션됩니다. </li><li>사용자는 Teams로 마이그레이션됩니다. 마이그레이션 후 더 이상 비즈니스용 Skype를 사용할 수 없습니다. </li><li>사용자에게 Teams 데스크톱 클라이언트가 설치되어 있어야 합니다. 설치는 비즈니스용 Skype 인프라의 정책을 통해 10일 동안 진행되지만 실패하는 경우 사용자는 클라이언트를 다운로드하거나 지원되는 브라우저에 연결해야 합니다. </li><li>연락처 및 모임이 Teams로 마이그레이션됩니다.</li><li>사용자는 고객 DNS 항목이 완료될 때까지 서비스가 Office 365 서비스로 전환되는 동안 비즈니스용 Skype에 로그인할 수 없습니다. </li><li>연락처 및 기존 모임은 계속해서 비즈니스용 Skype 모임으로 기능합니다. </li></ul>|
||||

마이그레이션 9단계가 완료된 후 PowerShell을 사용하여 비즈니스용 Skype Online에 연결해야 하는 경우 다음 코드를 사용하여 연결합니다.

```powershell
Import-Module MicrosoftTeams
$userCredential = Get-Credential
Connect-MicrosoftTeams -Credential $userCredential -OverridePowershellUri "https://admin4E.online.lync.com/OcsPowershellOAuth"
```

## <a name="phase-8-dynamics-365"></a>8단계: Dynamics 365

**다음에 적용됩니다.** Microsoft Dynamics 365를 사용하는 모든 고객

[Microsoft Dynamics 365](ms-cloud-germany-transition-add-pre-work.md#dynamics365) 설치 절차의 사전 작업 과정을 잘 알고 있는지 확인하십시오.

Dynamics 365를 사용 하는 고객은 조직의 Dynamics 조직을 독립적으로 마이그레이션하기 위해 추가 참여가 요구됩니다.

| Step(s) | 설명 | 영향 |
|:-------|:-------|:-------|
| Microsoft Dynamics 리소스 | Microsoft Dynamics를 사용할 고객은 Microsoft Engineering 또는 Microsoft FastTrack을 통해 Microsoft Dynamics 365를 Office 365 전역 서비스 인스턴스로 전환합니다.* |<ul><li>마이그레이션 후 관리자는 조직의 유효성을 검사합니다. <</li><li>관리자는 필요한 경우 워크플로를 수정합니다. </li><li>관리자는 AdminOnly 모드를 적절하게 지워야 합니다.</li><li>관리자는 조직 유형을 샌드박스에서 적절하게 변경합니다. </li><li>최종 사용자에게 새 URL을 알리고 인스턴스(org)에 액세스합니다.</li><li>인바운드 연결을 새 끝점 URL로 업데이트합니다. </li><li>전환 중에 사용자가 Dynamics 서비스를 사용할 수 없습니다. </li><li>사용자는 각 Org를 마이그레이션한 후 해당 상태 및 기능의 유효성을 검사해야 합니다.</li></ul>|
||||

\* (i) Microsoft Dynamics 365를 사용 하는 고객은 제공된 마이그레이션 프로세스에 정의된 이 마이그레이션 시나리오에서 조치를 취해야 합니다. (ii) 고객이 조치를 취하지 못하면 Microsoft가 마이그레이션을 완료할 수 없습니다. (iii) 고객의 비활성으로 인해 Microsoft가 마이그레이션을 완료할 수 없는 경우 고객의 구독은 2021년 10월 29일에 만료됩니다.

## <a name="phase-8-power-bi"></a>8단계: Power BI

**다음에 적용됩니다.** Microsoft Power BI(PBI)를 사용하는 모든 고객

| Step(s) | 설명 | 영향 |
|:-------|:-------|:-------|
| Power BI 리소스 마이그레이션 | Microsoft PBI(Power BI)를 사용하는 고객은 Power BI를 Office 365 전역 서비스 인스턴스로 전환하기 위해 기존 PBI 마이그레이션 도구를 수동으로 트리거한 후 Microsoft Engineering 또는 Microsoft FastTrack에 참여하게 됩니다.\*\* |<ul><li>다음 Power BI _항목은_ 전환되지 않습니다. 다시 만들어야 합니다. <</li><li>실시간 데이터 집합(예: 데이터 집합 스트리밍 또는 푸시) </li><li>Power BI 사내 데이터 게이트웨이 구성 및 데이터 원본 </li><li>실시간 데이터 집합을 토대하여 작성된 보고서는 마이그레이션 후에 사용할 수 없습니다. 다시 만들어야 합니다. </li><li>전환 중에 사용자가 Power BI 서비스를 사용할 수 없습니다. 서비스를 사용할 수 없는 시간은 24시간을 넘지 말아야 합니다.</li><li>사용자는 마이그레이션 후 Power BI 서비스를 사용하여 데이터 원본 및 해당 사내 데이터 게이트웨이를 다시 구성해야 합니다.  이렇게 할 때까지 사용자는 이러한 데이터 원본을 사용하여 이러한 데이터 원본에 대해 예약된 새로 고침 및/또는 직접 쿼리를 수행할 수 없습니다. </li><li>용량 및 고급 작업 영역은 마이그레이션할 수 없습니다. 고객은 마이그레이션 전에 모든 용량을 삭제하고 마이그레이션 후 다시 만들어야 합니다. 작업 영역이 원하는 용량으로 다시 이동됩니다.</li></ul>  |
||||

\*\* (i) Microsoft Power BI를 사용 하는 고객은 제공된 마이그레이션 프로세스에 정의된 이 마이그레이션 시나리오에서 조치를 취해야 합니다. (ii) 고객이 조치를 취하지 못하면 Microsoft가 마이그레이션을 완료할 수 없습니다. (iii) 고객의 비활성으로 인해 Microsoft가 마이그레이션을 완료할 수 없는 경우 고객의 구독은 2021년 10월 29일에 만료됩니다.

## <a name="phase-9--10-azure-ad-finalization"></a>9단계 &: Azure AD 마무리

**다음에 적용됩니다.** 모든 고객

Office 365 테넌트가 마이그레이션의 최종 단계를 완료하면 [Azure AD 완료(9단계)] 모든 서비스가 전 세계로 전환됩니다. 응용 프로그램이나 사용자는 도이치랜드 Microsoft 클라우드 끝점에 대해 테넌트의 리소스에 액세스하지 말아야 합니다. 완료가 완료되고 30일 후에 자동으로 Microsoft 클라우드 도이치랜드 Azure AD 서비스가 전환된 테넌트에 대한 끝점 액세스를 중지합니다. 인증과 같은 끝점 요청은 도이치랜드 Microsoft 클라우드 서비스에 대해 이 시점부터 실패합니다. 

| Step(s) | 설명 | 영향 |
|:-------|:-------|:-------|
| 사용자 끝점 업데이트 | 모든 사용자가 적절한 Microsoft 전 세계 끝점을 사용하여 서비스에 액세스하도록 보장 |마이그레이션이 완료된 후 30일이 지난 후 Microsoft 클라우드 도이클랜드 끝점은 요청의 존중을 중지합니다. 클라이언트 또는 응용 프로그램 트래픽이 실패합니다.  |
| Azure AD 응용 프로그램 끝점 업데이트 | 응용 프로그램의 인증, Azure AD(Azure Active Directory) 그래프 및 MS Graph 끝점을 Microsoft Worldwide 서비스의 끝점으로 업데이트해야 합니다. | 마이그레이션이 완료된 후 30일이 지난 후 Microsoft 클라우드 도이클랜드 끝점은 요청의 존중을 중지합니다. 클라이언트 또는 응용 프로그램 트래픽이 실패합니다. |
||||

## <a name="office-apps"></a>Office 앱

**다음에 적용됩니다.** Office 데스크톱 응용 프로그램을 사용하는 모든 고객(Word, Excel, PowerPoint, Outlook, ...)

"독일" 지역으로 전환하는 Office 365 테넌트는 테넌트 마이그레이션이 9단계에 도달한 후 모든 사용자가 Office 365에서 종료하고, 로그인한 후 모든 Office 데스크톱 응용 프로그램(Word, Excel, PowerPoint, Outlook 등)과 비즈니스용 OneDrive 클라이언트에 대해 다시 로그인해야 합니다. 로그인하면 Office 서비스가 전역 Azure AD 서비스에서 새 인증 토큰을 얻을 수 있습니다.

모바일 장치 사전 작업을 [완료해야](ms-cloud-germany-transition-add-pre-work.md#mobile-device-management) 합니다.

| Step(s) | 설명 | 영향 |
|:-------|:-------|:-------|
| 클라이언트, Office 클라이언트가 컷오버하는 동안 Azure AD는 Office 365 서비스를 지점으로 하는 테넌트 범위를 마무리합니다. | 이 구성 변경을 통해 Office 클라이언트는 Office 365 서비스 끝점을 업데이트하고 이를 지점으로 할 수 있습니다. | <ul><li>사용자에게 모든 _Office_ 앱을 닫은 다음 다시 로그인(또는 클라이언트를 강제로 다시 시작하고 사용자가 로그인하도록 설정)하여 Office 클라이언트가 변경 내용을 선택할 수 있도록 합니다. </li><li>사용자가 컷오버 후  72시간 이내에 Office 앱을 다시 활성화하라는 Office 배너가 표시될 수 있습니다. </li><li>개인 컴퓨터의 모든 Office 응용 프로그램을 닫아야 합니다. 사용자는 로그인한 다음 다시 로그인해야 합니다. 노란색 정품 인증 표시줄에서 로그인하여 Office 365 서비스에 대해 다시 정품 인증합니다.</li><li>공유 컴퓨터는 개인 컴퓨터와 유사한 작업이 필요하며 특별한 절차가 필요하지 않습니다. </li><li>모바일 장치에서 사용자는 앱에서 로그인하고 닫은 다음 다시 로그인해야 합니다.</li></ul>|
||||

## <a name="phase-9-line-of-business-apps"></a>9단계: 업무 앱

업무용 앱이 있는 경우 업무용 앱에 대한 사전 작업을 [완료해야](ms-cloud-germany-transition-add-pre-work.md#line-of-business-apps) 합니다.

## <a name="post-migration"></a>마이그레이션 후

마이그레이션 후 활동 [문서를](ms-cloud-germany-transition-add-experience.md) 읽고 그에 따라 실행해야 합니다.
