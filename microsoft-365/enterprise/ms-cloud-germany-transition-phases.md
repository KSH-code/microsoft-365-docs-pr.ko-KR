---
title: 마이그레이션 단계 도이클란드 Microsoft 클라우드에서 마이그레이션에 대한 작업 및 영향)
ms.author: andyber
author: andybergen
manager: laurawi
ms.date: 05/12/2021
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
ms.openlocfilehash: 73b50d52094526857e3787c29b764f55976bde12
ms.sourcegitcommit: d08fe0282be75483608e96df4e6986d346e97180
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/12/2021
ms.locfileid: "59185972"
---
# <a name="migration-phases-actions-and-impacts-for-the-migration-from-microsoft-cloud-deutschland"></a>마이그레이션 단계 도이클란드 Microsoft 클라우드에서 마이그레이션에 대한 작업 및 영향

독일 Microsoft 클라우드(MCD)에서 Microsoft Office 365 글로벌 서비스의 지역 "독일"으로 테넌트 마이그레이션은 각 워크로드에 대해 구성된 작업 및 단계 집합으로 실행됩니다. 이 그림에서는 새로운 독일 데이터 센터로의 10개 마이그레이션 단계를 보여 주었다.

[새 독일 데이터 센터로의 ![ 10단계 마이그레이션 단계 ](../media/ms-cloud-germany-migration-opt-in/migration-organization.png)](../media/ms-cloud-germany-migration-opt-in/migration-organization.png#lightbox)

조직의 전체 크기 및 복잡도에 따라 마이그레이션 프로세스가 몇 주 동안 완료됩니다. 마이그레이션이 진행 중일 때 사용자와 관리자는 이 설명서에 자세히 설명된 변경 사항과 함께 서비스를 계속 사용할 수 있습니다. 그래픽 및 테이블은 마이그레이션 중의 단계와 단계를 정의합니다.

> [!NOTE]
> Azure 서비스의 마이그레이션은 이 설명서의 일부가 아니며, 해당 정보는 Azure Germany에 대한 [마이그레이션 지침을 참조하세요.](/azure/germany/germany-migration-main)

<br>

****

|Step(s)|기간|책임자|설명|
|---|---|---|---|
|Opt-In|시간|고객|조직을 마이그레이션에 옵트인합니다.|
|사전 작업|일|고객|마이그레이션을 위해 사용자, 작업소 및 네트워크를 준비하는 데 필요한 작업을 완료합니다.|
|Azure Active Directory(Azure AD)|1~2일|Microsoft|Azure AD 조직을 전 세계로 마이그레이션합니다.|
|Azure|주|고객|새 전 세계 Azure 구독을 만들고 [Azure 서비스를 전환합니다.](/azure/azure-resource-manager/management/move-resource-group-and-subscription)|
|구독 & 라이선스 전환|1~2일|Microsoft|전 세계 구독을 구입하고, 도이치스크란드 Microsoft 클라우드 구독을 취소하고, 사용자 라이선스를 전환합니다.|
|SharePoint 및 OneDrive|15일 이상|Microsoft|URL을 SharePoint 비즈니스용 OneDrive 콘텐츠 및 sharepoint.de 마이그레이션합니다.|
|Exchange Online|15일 이상|Microsoft|콘텐츠 Exchange Online 마이그레이션하고 전 세계 URL로 전환합니다.|
|보안 및 규정 준수|1~2일|Microsoft|보안 및 & 정책 및 콘텐츠를 전환합니다.|
|비즈니스용 Skype|1~2일|Microsoft|다음 비즈니스용 Skype 전환할 Microsoft Teams.|
|Power BI & Dynamics 365|15일 이상|Microsoft|Power BI 및 Dynamics 365 콘텐츠를 마이그레이션합니다.|
|Azure AD 마무리|1~2일|Microsoft|전 세계 테넌트 컷오버를 완료합니다.|
|Clean-Up|1~2일|고객|AD FS(Active Directory Federation Services) 신뢰 파티 트러스트, Azure AD 커넥트 및 클라이언트 다시 시작과 같은 레거시 연결을 Office 정리합니다.|
|끝점 사용 안|30일|Microsoft|Azure AD가 마무리된 후 30일이 지난 후 Microsoft 클라우드 도이치랜드 Azure AD 서비스는 전환된 조직의 끝점 액세스를 중지합니다. 인증과 같은 끝점 요청은 도이치랜드 Microsoft 클라우드 서비스에 대해 이 시점부터 실패합니다. 도이치랜드 Microsoft 클라우드의 Office 365 서비스에 연결된 인스턴스에서 Azure 워크로드를 실행하는 고객은 나중에 최종 마이그레이션 단계로 이동됩니다.|
|

단계 및 해당 작업은 중요한 데이터 및 환경이 전역 서비스로 Office 365 보장합니다. 테넌트가 마이그레이션 큐에 추가되고 나면 각 작업이 백end 서비스에서 실행되는 단계 집합으로 완료됩니다. 일부 워크로드에는 관리자(또는 사용자)가 작업을 요구하거나 마이그레이션이 실행되고 마이그레이션이 구성되는 방법에서 설명하는 단계의 사용에 영향을 줄 [수 있습니다.](ms-cloud-germany-transition.md#how-is-the-migration-organized)

다음 섹션에는 마이그레이션의 다양한 단계를 진행할 때 작업에 대한 작업 및 영향이 포함되어 있습니다. 표를 검토하고 조직에 적용할 수 있는 작업이나 효과를 파악합니다. 필요한 경우 각 단계의 단계를 실행할 준비가 되도록 합니다. 필요한 단계를 완료하지 못하면 서비스가 종료될 수 있으며 서비스로의 마이그레이션이 Office 365 있습니다.

## <a name="phase-opt-in"></a>단계: Opt-In

**적용 사항:** MICROSOFT Office 365 테넌트가 있는 모든 고객은 동의 없이 MCD(Microsoft 클라우드 Office 365 테넌트)를 마이그레이션할 수 없습니다.

<br>

****

|Step(s)|설명|영향|
|---|---|---|
|**고객 작업:** 마이그레이션에 대한 동의 부여|고객은 Microsoft가 데이터 및 서비스를 전역 서비스 인스턴스로 마이그레이션하고 오케스트레이션할 수 있는 권한을 얻게 하여 마이그레이션에 Office 365 동의합니다. 두 가지 방법이 있습니다. <ol><li>테넌트 Office 365 Microsoft 주도 마이그레이션에 옵트인(opt in)합니다.</li><li>고객은 2020년 5월 1일 이후에 MCD Office 365 구독을 갱신했습니다. Microsoft는 매월 이러한 고객에게 마이그레이션을 알리고 30일 동안 기다렸다가 취소할 수 있는 기회를 제공한 다음 직접 옵트인(opt in)합니다.</li></ol>|<ul><li>테넌트가 마이그레이션에 동의한 것으로 표시되어 관리 센터에 확인이 표시됩니다.</li><li>Acknowledgment는 Office 365 메시지 센터에 게시됩니다. 서비스 구성은 도이치란드 Microsoft 클라우드 끝점에서 계속됩니다.</li></ul>
|**테넌트 관리자:** 메시지 모니터링|테넌트 관리자는 현재 Office 365 단계 상태에 대한 업데이트를 위해 메시지 센터에서 업데이트를 모니터링해야 합니다.|고객은 필요한 작업을 제시간에 실행할 수 있습니다.
|

## <a name="phase-1-before-the-migration-starts"></a>1단계: 마이그레이션 시작 전

모든 고객에게 적용되는 마이그레이션 준비 단계에 [익숙해야 합니다.](ms-cloud-germany-transition-add-pre-work.md)

소유한 하나 또는 여러 DNS 네임스페이스에서 _msoid라는_ DNS CNAME을 설정한 경우 8단계가 끝날 때까지 CNAME을 제거해야 합니다. 8단계가 끝나기 전에 CNAME _msoid를_ 제거할 수 있습니다. [DNS에 대한 사전 작업 을 참조합니다.](ms-cloud-germany-transition-add-pre-work.md#dns-entries-for-custom-domains)

Microsoft 클라우드 도이치클라드 인스턴스에서 Office 365 Azure에 대해 Single Sign-On을 사용하는 경우 그에 따라 Azure 구독 마이그레이션을 준비하고 예약해야 합니다. 에 대한 사전 작업 [Microsoft Azure.](ms-cloud-germany-transition-add-pre-work.md#microsoft-azure)

### <a name="azure-ad-connect-with-ad-fs-federation"></a>AD FS 커넥트 Azure AD 서비스

**적용 사항:** AD FS 페더러가 있는 고객

**적용된 경우:** 2단계가 시작되기 전

AD FS(Active Directory Federation Services)를 사용하는 경우 2단계가 시작되기 전에 Office 365 Global 서비스에 대한 신뢰자  트러스트 추가 전후에 [ADFS](ms-cloud-germany-transition-add-adfs.md) 구성을 백업해야 합니다.

## <a name="phase-2-azure-ad-migration"></a>2단계: Azure AD 마이그레이션

이 단계에서는 Azure Active Directory 데이터 센터 지역으로 마이그레이션되어 활성화됩니다. 이전 Azure AD 끝점은 계속 사용할 수 있습니다.

### <a name="exchange-online-hybrid---modify-authserver-on-premises"></a>Exchange Online 하이브리드 - AuthServer On-premises 수정

**다음에 적용됩니다.** 활성 하이브리드 구성을 사용하는 Exchange 서버와 Exchange 구성을 사용하는 모든 고객

**적용된 경우:** 2단계가 종료된 후

Azure AD 마이그레이션이 완료된 후 AuthServer 사내에서 인증을 위해 전역 STS(Security Token Service)를 설정해야 합니다.
이렇게 하면 하이브리드 Exchange 환경을 대상으로 하는 마이그레이션 상태의 사용자로부터의 Exchange 가용성 요청에 대한 인증 요청이 인증되어 사내 서비스에 액세스할 수 있습니다. 마찬가지로, 이렇게 하면 전역 서비스 끝점에 대한 Office 365 인증할 수 있습니다.
Azure AD 마이그레이션(2단계)이 완료된 후, Exchange(하이브리드) 토폴로지의 관리자는 Office 365 전역 서비스에 대한 새 인증 서비스 끝점을 추가해야 합니다.

PowerShell에서 Exchange 사용하여 조직의 Azure Portal에 있는 조직의 `<TenantID>` 테넌트 ID로 Azure Active Directory.

```powershell
New-AuthServer GlobalMicrosoftSts -AuthMetadataUrl https://accounts.accesscontrol.windows.net/<TenantID>/metadata/json/1
```

이 작업을 완료하지 못하면 하이브리드 사용 가능한 요청이 도이치클랜드에서 다른 서비스로 마이그레이션된 사서함 사용자에게 정보를 Office 365 있습니다.

## <a name="phase-3-subscription-transfer"></a>3단계: 구독 이전

**적용 사항:** 도이치클라일랜드(MCD)에서 Office 365 테넌트가 있는 모든 고객

<br>

****

|Step(s)|설명|영향|
|---|---|---|
|구독이 전송됩니다.|도이치클라드 Microsoft 클라우드 구독은 해당 전역 서비스 Office 365 마이그레이션됩니다. <ul><li>이 Office 365 전역 서비스 서비스는 Microsoft(제품 _매핑)에 의해 정의됩니다._</li><li> 해당 Office 365 전역 서비스 구독은 Office 365 Microsoft 클라우드 구독에 대한 전역 인스턴스에서 구매합니다.</li><li>레거시 Microsoft 클라우드 도이치클랜드 구독은 완료 시 Office 365 서비스 테넌트에서 제거됩니다.</li></ul>|<ul><li>이 단계에서는 기존 구독에 대한 변경 사항(예: 새 구독 구매 또는 시트 수 변경 없음)이 차단됩니다.</li><li>라이선스 할당 변경이 차단됩니다.</li><li>구독 마이그레이션이 완료되면 Office 365 서비스와 도이치클라드 Microsoft 클라우드 구독이 모두 Office 365 관리자 Portal에 표시될 수 있으며, 상태는 도이프란드 Microsoft 클라우드 구독의 비프로비전 으로 _표시됩니다._</li><li>도이치클라드 Microsoft 클라우드 구독 또는 SKU GUID에 종속된 모든 고객 프로세스는 손상되어 Office 365 서비스 제공을 통해 수정해야 합니다.</li><li>Office 365 서비스의 새 구독은 새 기간(월별/분기별/년)을 통해 구입하며, 고객은 도이치랜드 Microsoft 클라우드 구독의 미사용 잔액에 대한 비분산 환불을 받게 됩니다.</li></ul>|
|라이선스 재할당|할당된 Microsoft 클라우드 라이선스가 있는 사용자에게는 Office 365 라이선스가 할당됩니다.|<ul><li>사용자에게 새 Office 365 라이선스가 다시 배정됩니다. 모든 사용자의 사용자 라이선스가 새 기능에 자동으로 할당됩니다.</li><li>Office 365 서비스에서 제공하는 기능(서비스 계획)의 수는 도이치랜드의 원래 Microsoft 클라우드 제품보다 클 수 있습니다. Office 365 서비스의 사용자 라이선스는 유사한 Microsoft 클라우드 도이클란드 기능(서비스 계획)에 동일하게 할당됩니다.</li></ul>|
|**관리자 작업** 기능 사용 안|관리자는 필요한 경우 해당 기능을 사용하지 않도록 설정하기 위한 명시적 조치를 취해야 합니다.|<ul><li>사용자가 포털에서 알 수 없는 새 서비스를 볼 수 있습니다.</li><li>테넌트 관리자가 사용하지 않도록 설정하지 않은 경우 추가 기능(예: Microsoft Planner 및 Power Automate)을 사용할 수 있습니다.</li></ul> <p> 사용자의 라이선스에 할당된 서비스 계획을 사용하지 않도록 설정하는 방법에 대한 자세한 내용은 사용자 라이선스를 할당하는 동안 Microsoft 365 서비스에 대한 액세스 사용 안 하도록 [설정을 참조하세요.](disable-access-to-services-while-assigning-user-licenses.md)</li></ul>|
|**관리자 작업**|도이치스크란드 Microsoft 클라우드 구독 또는 SKU GUID에 종속된 모든 고객 프로세스를 Office 365 서비스 제공|고객 프로세스는 계속 작동됩니다.|
|

**적용된 경우:** 파트너 포털을 Office 365 Microsoft 파트너

2단계와 3단계 사이에는 파트너 포털에 액세스할 수 없습니다. 이 시간 동안 파트너는 파트너 포털에서 테넌트 정보에 액세스하지 못하게 될 수 있습니다. 마이그레이션마다 다르기 때문에 내게 필요한 경우의 기간은 시간일 수 있습니다.

클라우드 솔루션 공급자에 대한 추가 정보는 파트너 테넌트 마이그레이션 [에서 사용할 수 있습니다.](ms-cloud-germany-transition-add-csp.md#partner-tenant-migration)

## <a name="phase-4-sharepoint-online"></a>4단계: SharePoint 온라인

**적용 사항:** 온라인을 사용하는 SharePoint

여전히 SharePoint 2013 워크플로를 사용하는 경우 SharePoint Online 마이그레이션 중에 SharePoint 2013 워크플로의 SharePoint 제한합니다.

<br>

****

|Step(s)|설명|영향|
|---|---|---|
|SharePoint OneDrive 및 전환|SharePoint 온라인 및 비즈니스용 OneDrive 도이클란드 Microsoft 클라우드에서 이 Office 365 전역 서비스로 마이그레이션됩니다. <ul><li>기존 Microsoft 클라우드 네덜란드 URL(예: )이 `contoso.sharepoint.de` 보존됩니다.</li><li>기존 사이트는 보존됩니다.</li><li>도이치랜드 Microsoft 클라우드 또는 Office 365 전역 서비스 인스턴스에서 STS(Security Token Service)에서 발급한 클라이언트 쪽 인증 토큰은 전환 중에 유효합니다.</li></ul>|<ul><li>콘텐츠는 마이그레이션 중에 잠시 동안 읽기 전용으로 설정됩니다. 이 시간 동안 에 "콘텐츠를 편집할 수 없습니다." 배너가 SharePoint.</li><li>검색 인덱스는 보존되지 않습니다. 다시 생성하는 데 최대 10일이 걸릴 수 있습니다.</li><li>SharePoint 온라인 비즈니스용 OneDrive 콘텐츠는 마이그레이션 중에 두 가지 짧은 기간 동안 읽기 전용으로 설정됩니다. 이 시간 동안 사용자에게 "콘텐츠를 편집할 수 없습니다." 배너가 잠시 표시됩니다.</li><li>SharePoint Online 마이그레이션이 완료된 후 인덱스를 다시 SharePoint 온라인 및 비즈니스용 OneDrive 콘텐츠에 대한 검색 결과를 사용할 수 없습니다. 이 기간 동안 검색 쿼리는 전체 결과를 반환하지 않을 수 있습니다. 온라인 뉴스와 같은 검색 인덱스에 종속된 SharePoint 인덱싱이 완료되면 영향을 받을 수 있습니다.</li><li>SharePoint 동안 2013 워크플로가 손상되어 마이그레이션 후에 다시 게시해야 합니다.</li></ul>|
|**SPO 관리자:** 2013 SharePoint 다시 게시|SharePoint Online 관리자는 마이그레이션 후 SharePoint 2013 워크플로를 다시 게시합니다.|이 작업은 필수 작업입니다. 이렇게 하지 못하면 사용자 혼동, 지원 센터 통화 및 생산성이 저하될 수 있습니다.|
|**PowerShell 사용자:** 새 모듈로 업데이트|SharePoint Online PowerShell 모듈의 모든 사용자는 SharePoint Online 마이그레이션이 완료된 후 모듈/Microsoft.SharePointOnline.CSOM을 버전 16.0.20717.12000 이상으로 업데이트해야 합니다. 완료는 메시지 센터에서 전달됩니다.|SharePoint PowerShell을 통해 온라인으로 또는 클라이언트 쪽 개체 모델이 더 이상 실패하지 않습니다.|
|

추가 고려 사항:

- 조직에서 여전히 SharePoint 워크플로를 사용하는 경우 2021년 12월 31일 이후에는 더 이상 작동하지 않습니다. SharePoint 2013 워크플로는 2020년 11월 1일부터 시작되는 새 테넌트에 대해 기본적으로 꺼져 있습니다. SharePoint Online 서비스로의 마이그레이션이 완료되면 지원되는 Power Automate 솔루션으로 이동하는 것이 좋습니다.
- SharePoint Online 인스턴스가 아직 마이그레이션되지 않은 Microsoft 클라우드 도이클랜드 고객은 SharePoint Online PowerShell 모듈/Microsoft.SharePointOnline.CSOM 버전 16.0.20616.12000 이하를 유지해야 합니다. 그렇지 않으면 PowerShell 또는 클라이언트 쪽 SharePoint 통해 Online에 대한 연결이 실패합니다.
- 이 단계에서는 URL의 SharePoint IP 주소가 변경됩니다. Office 365 전역 서비스로 전환하고 나면 보존된 테넌트 URL(예: 및 )의 주소가 전 세계 Microsoft 365 URL 및 IP 주소 범위(SharePoint Online 및 `contoso.sharepoint.de` `contoso-my.sharepoint.de` [비즈니스용 OneDrive)로 변경됩니다.](/microsoft-365/enterprise/urls-and-ip-address-ranges#sharepoint-online-and-onedrive-for-business)
- 서비스 SharePoint OneDrive 전환하는 동안 Office Online이 예상대로 작동하지 않을 수 있습니다.
- 사용자 지정 검색 구성이 적용된 경우 전환이 완료된 후 검색 구성을 가져와야 합니다. SharePoint Online에 대한 마이그레이션 전 단계에 설명된 바와 같이 전환 전에 검색 [구성을 내보내야 합니다.](ms-cloud-germany-transition-add-pre-work.md#sharepoint-online)

> [!NOTE]
> eDiscovery를 사용하는 경우 [eDiscovery](ms-cloud-germany-transition-add-scc.md)마이그레이션 환경을 알고 있어야 합니다.

## <a name="phase-5-exchange-online"></a>5단계: Exchange Online

5단계부터 Exchange Online 사서함이 도이클란드 Microsoft 클라우드에서 전역 서비스로 Office 365 이동됩니다.

Office 365 전역 서비스 지역이 기본값으로 설정되어 내부 부하 분산 서비스가 사서함을 Office 365 해당 기본 지역으로 다시 재배포할 수 있습니다. 이 전환에서 어느 쪽에 있는 사용자(MCD 또는 전역 서비스)는 동일한 조직에 있으며 두 URL 끝점을 모두 사용할 수 있습니다.

새 지역 "독일"이 조직 설정에 추가됩니다. Exchange Online 구성은 전환 조직에 새로운 이동 독일 지역을 추가합니다.

- 사용자 및 서비스를 레거시 MCD URL( )에서 새 Office 365 서비스 `https://outlook.office.de` URL()로 `https://outlook.office365.com` 전환합니다.
- 새 독일 데이터 센터 지역에 대한 Exchange Online 서비스(Outlook Web Access 및 Exchange 관리 센터)를 이 단계에서 사용할 수 있습니다.
- 사용자는 마이그레이션 중에 레거시 MCD URL을 통해 서비스에 계속 액세스할 수 있습니다. 그러나 마이그레이션이 완료될 때 레거시 URL 사용을 중지해야 합니다.
- 사용자는 Office 온라인 기능(일정, 메일Office 사용자)에 대한 전 세계 Office 포털로 전환해야 합니다. 아직 Office 365 서비스로 마이그레이션되지 않은 서비스로의 탐색은 마이그레이션될 때까지 작동하지 않습니다.
- 이 제한 사항은 "내 계정"처럼 백그라운드 서비스에도 적용됩니다. 9단계가 완료된 후 내 계정 글로벌 서비스를 사용할 수 있습니다. 이 경우 사용자는 MCD 포털을 사용하여 계정 설정을 관리해야 합니다.
- 마이그레이션 Outlook Web App 동안 공용 폴더 환경을 제공하지 않습니다.

5단계에서 사용자 사진을 수정하려면 5단계 Exchange Online [PowerShell - Set-UserPhoto 참조합니다.](#exchange-online-powershell)

### <a name="dns-record-for-autodiscover-in-exchange-online"></a>2016년 8월의 자동 Exchange Online

**다음에 적용됩니다.** 사용자 지정 도메인에서 Exchange Online 사용하는 고객

현재 도이치클라드 Microsoft 클라우드를 지점하는 자동 검사에 대한 고객 관리 DNS 설정을 업데이트하여 Exchange Online 단계(5단계)의 완료 시 Office 365 전역 끝점을 참조해야 합니다.

CNAME이 을(를) autodiscover-outlook.office.de 있는 기존 DNS 항목은 을(를) **autodiscover.outlook.com.**

마이그레이션 단계 **9가** 완료될 때 이러한 DNS 업데이트를 수행하지 않는 고객은 마이그레이션이 완료될 때 서비스 문제가 있을 수 있습니다.

> [!NOTE]
> 자동 검색 항목에 대한 사용자 지정 도메인에 대한 관리 센터의 유효성 검사 오류는 무시할 수 있습니다. 서비스는 CNAME 레코드가 새 레코드로 변경된 autodiscover.outlook.com.

### <a name="exchange-online-powershell"></a>Exchange Online PowerShell

**적용 사항:** Exchange Online PowerShell을 Exchange Online 관리자

마이그레이션 단계에서 PowerShell cmdlet **New-MigrationEndpoint, Set-MigrationEndpoint** 및 **Test-MigrationsServerAvailability를** 사용하면 오류가 발생할 수 있습니다(프록시 오류).  이 문제는 중재 사서함이 전 세계로 마이그레이션했지만 관리자 사서함이 전 세계로 마이그레이션되지 않은 경우 또는 그 반대의 경우 발생합니다. 이 문제를 해결하기 위해 테넌트 PowerShell 세션을 만드는 동안 ConnectionUri의 라우팅 힌트로 중재 **사서함을 사용 합니다.** 예시:

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

- 다른 Outlook Web App 공유 사서함에 액세스하는 사용자(예: MCD 환경의 사용자가 전역 환경의 공유 사서함에 액세스)에는 두 번째로 인증하라는 메시지가 표시됩니다. 사용자는 먼저 에서 사서함을 인증하고 액세스한 다음 에 있는 공유 `outlook.office.de` 사서함을 열 수 있어야 `outlook.office365.com` 합니다. 다른 서비스에서 호스팅되는 공유 리소스에 액세스할 때 두 번째 인증을 해야 합니다.
- 전환하려는 기존 Microsoft 클라우드 고객 또는 전환하는 고객의 경우 파일 Outlook 정보 > **>** 계정 추가를 사용하여 공유 사서함을 > 일정 권한 보기가 실패할 수 있습니다(Outlook 클라이언트가 Rest API를 사용하려고 `https://outlook.office.de/api/v2.0/Me/Calendars` 시도). 일정 권한을 보기 위해 계정을 추가하려는 고객은 사용자 환경 변경 [](https://support.microsoft.com/office/user-experience-changes-for-sharing-a-calendar-in-outlook-5978620a-fe6c-422a-93b2-8f80e488fdec) 사항에서 설명한 레지스트리 키를 추가하여 이 작업이 Outlook 수 있습니다. 이 레지스트리 키는 그룹 정책을 사용하여 조직 전체에 배포할 수 있습니다.
- 활성 Exchange 하이브리드 구성을 사용하는 모든 고객은 독일 Microsoft 클라우드와 독일의 새 데이터 센터 지역을 Exchange Server Exchange Online 사서함을 이동하지 못합니다. 고객은 5단계 이전에 진행되는 사서함 이동이 완료되고 이 단계가 완료된 후 다시 시작되도록 해야 합니다.
- 도이클란드 Microsoft 클라우드에서 Exchange 서비스로 마이그레이션하는 동안 `Test-MigrationServerAvailabiilty` PowerShell cmdlet을 Office 365 작동하지 않을 수 있습니다. 그러나 마이그레이션이 완료된 후 제대로 작동합니다.
- 사서함이 마이그레이션된 후 클라이언트가 자격 증명 또는 권한 부여에 문제가 있는 경우 를 실행하거나 ECP(Exchange 제어판)를 사용하여 마이그레이션 끝점에서 사내 관리자 자격 증명을 `Set-MigrationEndpoint -Identity <endpointName> -Credential $(Get-Credential)` 다시 입력합니다.
- 장치용 레거시 프로토콜(POP3/IMAP4/SMTP)을 사용하는 모든 사용자가 Exchange 사서함이 새 독일 데이터 센터 지역으로 이동된 후 클라이언트의 끝점을 변경할 준비가 되도록 준비해야 [Exchange Online.](ms-cloud-germany-transition-add-pre-work.md#exchange-online)
- 사서함이 비즈니스용 Skype 후 Outlook Web App 모임을 더 이상 사용할 수 없습니다. 필요한 경우 사용자는 이 기능을 Outlook 합니다.

마이그레이션의 조직과 Exchange Online 리소스가 마이그레이션된 후 조직의 차이점에 대한 자세한 내용은 새 독일 데이터 센터 지역의 Office 365 서비스로 마이그레이션하는 동안 고객 환경의 정보를 [검토하세요.](ms-cloud-germany-transition-experience.md)

## <a name="phase-6-exchange-online-protection--security-and-compliance"></a>6단계: Exchange Online Protection/보안 및 규정 준수

**다음에 적용됩니다.** 서비스를 사용하는 Exchange Online

EOP(백 엔드 Exchange Online Protection) 기능은 새 지역 "독일"에 복사됩니다. Exchange Online 보안 및 규정 준수 기능에 대한 백 엔드 서비스도 Office 365 및 기록 테넌트 세부 정보가 마이그레이션되고 있는 경우 외부 호스트에서 테넌트로 라우팅할 수 있습니다.

하이브리드가 아닌 Exchange Online 기능만 사용하는 고객은 이 단계에서 주의를 기울일 필요가 있습니다.

### <a name="exchange-online-hybrid-deployments"></a>Exchange Online 하이브리드 배포

**다음에 적용됩니다.** 활성 하이브리드 구성을 사용하는 Exchange 서버와 Exchange 구성을 사용하는 모든 고객

마이그레이션 Exchange [](ms-cloud-germany-transition-add-pre-work.md#exchange-online-hybrid-customers) 5단계가 시작되기 전에 사전 작업 **완료가 적용되어 있는지 확인** Exchange Online 하이브리드 고객은 "Office 365 Germany" 모드에서 최신 버전의 Exchange HCW(하이브리드 구성 마법사)를 실행하여 전역 서비스로의 마이그레이션을 위한 Office 365 준비해야 합니다.

**관리자 작업:**

- 마이그레이션 단계 6이 시작되고 마이그레이션 단계 9(메시지 센터 알림이 게시될 때)가 완료될 때에는 Office 365 Worldwide 설정을 사용하여 HCW를 다시 실행하여 Office 365 전역 서비스를 설정해야 합니다. 9단계 [마이그레이션 완료] 이전의 이 작업을 완료하지 못하면 메일에 대한 NDRS가 배포와 배포에 Exchange 라우팅될 Office 365.
- 온보드 또는 오프보더 사서함 이동을 중지하거나 삭제합니다. 즉, 온-프레미스와 온-프레미스 간에 사서함을 Exchange 이동하지 Exchange Online.  이렇게 하면 사서함 이동 요청이 오류와 함께 실패하지 않습니다. 이렇게 하지 못하면 서비스 또는 클라이언트가 실패할 Office 있습니다.
- 추가 Send-Connectors HCW에서 만든 커넥터 외에 만들어지며 Exchange Online HCW 실행이 실행된 직후에 이 단계에서 업데이트해야 합니다. 그렇지 않으면 작동이 중지됩니다. 이러한 송신 커넥터에 대해 TLS 도메인을 업데이트해야 합니다. <br> TLS 도메인을 업데이트하려면 사용자 환경의 다음 PowerShell 명령을 Exchange Server 합니다.

```powershell
Set-SendConnector -Identity <SendConnectorName> -TlsDomain "mail.protection.outlook.com"
```

## <a name="phase-7-skype-for-business-online---transition-to-microsoft-teams"></a>7단계: 비즈니스용 Skype Online - Microsoft Teams

**다음에 적용됩니다.** 비즈니스용 Skype Online을 사용하는 모든 고객

비즈니스용 Skype [Online](ms-cloud-germany-transition-add-pre-work.md#skype-for-business-online) 마이그레이션에 대한 마이그레이션 전 단계를 검토하고 모든 단계를 완료해야 합니다.
이 단계에서는 비즈니스용 Skype 마이그레이션 Microsoft Teams됩니다. 기존 비즈니스용 Skype 고객은 유럽의 Office 365 전역 서비스로 마이그레이션된 다음 Microsoft Teams 서비스의 "독일" 지역에 있는 Office 365 전환됩니다.

- 사용자는 마이그레이션 날짜에 로그인할 비즈니스용 Skype 수 없습니다.
- 정책 구성이 마이그레이션됩니다.
- 사용자는 마이그레이션 후 Teams 마이그레이션되지 비즈니스용 Skype 없습니다.
- 사용자에게 데스크톱 클라이언트가 Microsoft Teams 있어야 합니다. 비즈니스용 Skype 인프라의 정책을 통해 10일 동안 설치가 진행되지만, 설치에 실패하면 사용자는 클라이언트를 다운로드하거나 지원되는 브라우저에 연결해야 합니다.
- 연락처 및 모임은 해당 연락처로 Microsoft Teams.
- 사용자는 고객 DNS 항목이 완료될 때까지 비즈니스용 Skype 서비스로 전환되는 Office 365 로그인할 수 없습니다.
- 연락처 및 기존 모임은 계속해서 모임이 비즈니스용 Skype 기능합니다.

베니티 도메인이 구성되면 비즈니스용 Skype DNS 항목을 업데이트해야 합니다. DNS [구성의](https://admin.microsoft.com/Adminportal/Home#/Domains) Microsoft 365 관리 센터 도메인을 참조하고 변경 내용을 적용합니다.

마이그레이션 9단계가 완료된 비즈니스용 Skype PowerShell을 사용하여 비즈니스용 Skype Online에 연결해야 하는 경우 다음 PowerShell 코드를 사용하여 연결합니다.

```powershell
Import-Module MicrosoftTeams
$userCredential = Get-Credential
Connect-MicrosoftTeams -Credential $userCredential
```

### <a name="known-limitations-until-finalizing-azure-ad-migration"></a>Azure AD 마이그레이션을 완료할 때까지 알려진 제한 사항
Microsoft Teams Azure AD의 기능을 활용합니다. Azure AD의 마이그레이션이 완료되지 않은 동안 일부 Microsoft Teams 사용할 수 없습니다. 9단계를 수행하고 나면 Azure AD 마이그레이션이 완료된 후 다음 기능을 완전히 사용할 수 있습니다.

- 앱 관리 센터에서 앱을 관리할 Microsoft Teams 없습니다.
- 새 팀을 Microsoft Teams 팀을 만들 수 있는 권한을 Teams 새 팀을 만들 수 있습니다. 새 팀은 관리 센터에서 만들 Microsoft Teams 없습니다.
- 웹 버전의 Microsoft Teams 사용할 수 없습니다.

## <a name="phase-8-dynamics-365"></a>8단계: Dynamics 365

**다음에 적용됩니다.** Microsoft Dynamics 365를 사용하는 모든 고객

[Microsoft Dynamics 365](ms-cloud-germany-transition-add-pre-work.md#dynamics-365) 설치 절차의 사전 작업 과정을 잘 알고 있는지 확인하십시오.

Dynamics 365를 사용 하는 고객은 조직의 Dynamics 조직을 독립적으로 마이그레이션하기 위해 추가 참여가 요구됩니다.

<br>

****

|Step(s)|설명|영향|
|---|---|---|
|Microsoft Dynamics 리소스|Microsoft Dynamics를 사용 하는 고객은 Microsoft Engineering 또는 Microsoft FastTrack Microsoft Dynamics 365를 전역 서비스 Office 365 전환합니다.\*|<ul><li>마이그레이션 후 관리자는 조직의 유효성을 검사합니다.</li><li>관리자는 필요한 경우 워크플로를 수정합니다.</li><li>관리자는 AdminOnly 모드를 적절하게 지워야 합니다.</li><li>관리자는 조직 유형을 샌드박스에서 적절하게 변경합니다. </li><li>최종 사용자에게 새 URL을 알리고 인스턴스(org)에 액세스합니다.</li><li>인바운드 연결을 새 끝점 URL로 업데이트합니다.</li><li>전환 중에 사용자가 Dynamics 서비스를 사용할 수 없습니다.</li><li>사용자는 각 Org를 마이그레이션한 후 해당 상태 및 기능의 유효성을 검사해야 합니다.</li></ul>|
|

\* (i) Microsoft Dynamics 365를 사용 하는 고객은 제공된 마이그레이션 프로세스에 정의된 이 마이그레이션 시나리오에서 조치를 취해야 합니다. (ii) 고객이 조치를 취하지 못하면 Microsoft가 마이그레이션을 완료할 수 없습니다. (iii) 고객의 비활성으로 인해 Microsoft가 마이그레이션을 완료할 수 없는 경우 고객의 구독은 2021년 10월 29일에 만료됩니다.

## <a name="phase-8-power-bi"></a>8단계: Power BI

**다음에 적용됩니다.** Microsoft PBI(Microsoft Power BI) 사용 하는 모든 고객

<br>

****

|Step(s)|설명|영향|
|---|---|---|
|리소스 Power BI 마이그레이션|Microsoft PBI(Power BI)를 사용하는 고객은 기존 PBI 마이그레이션 도구를 FastTrack Microsoft Engineering 또는 Microsoft Power BI Office 365 글로벌 서비스 인스턴스로 전환합니다.\*\*|<ul><li>다음 Power BI 항목이 전환되지 않는 경우 다시 만들어야 합니다. < </li><li>실시간 데이터 집합(예: 데이터 집합 스트리밍 또는 푸시)</li><li>Power BI 게이트웨이 구성 및 데이터 원본을 저장합니다.</li><li>실시간 데이터 집합을 토대하여 작성된 보고서는 마이그레이션 후에 사용할 수 없습니다. 다시 만들어야 합니다.</li><li>Power BI 동안 사용자가 서비스를 사용할 수 없습니다. 서비스를 사용할 수 없는 시간은 24시간을 넘지 말아야 합니다.</li><li>사용자는 마이그레이션 후 데이터 원본 및 해당 사내 데이터 게이트웨이를 Power BI 구성해야 합니다.  이렇게 할 때까지 사용자는 이러한 데이터 원본을 사용하여 이러한 데이터 원본에 대해 예약된 새로 고침 및/또는 직접 쿼리를 수행할 수 없습니다.</li><li>용량 및 고급 작업 영역은 마이그레이션할 수 없습니다. 고객은 마이그레이션 전에 모든 용량을 삭제하고 마이그레이션 후 다시 만들어야 합니다. 작업 영역이 원하는 용량으로 다시 이동됩니다.</li></ul>|
|

\*\*(i) Microsoft Power BI 고객은 제공된 마이그레이션 프로세스에 정의된 이 마이그레이션 시나리오에서 조치를 취해야 합니다. (ii) 고객이 조치를 취하지 못하면 Microsoft가 마이그레이션을 완료할 수 없습니다. (iii) 고객의 비활성으로 인해 Microsoft가 마이그레이션을 완료할 수 없는 경우 고객의 구독은 2021년 10월 29일에 만료됩니다.

## <a name="phase-9-office-apps"></a>9단계: Office 앱

**다음에 적용됩니다.** 모든 고객이 Office 데스크톱 응용 프로그램(Word, Excel, PowerPoint, Outlook, OneDrive ...)

이 단계에서는 모든 클라이언트 응용 프로그램 및 Office Online이 클라이언트 컷오버를 수행하고 있습니다. Azure AD는 서비스 및 관련 끝점을 Office 365 테넌트 범위를 마무리합니다.

Office 365 "Germany" 지역으로 전환하는 테넌트는 모든 사용자가 Office 365에서 종료하고, 로그인한 후 테넌트 마이그레이션이 9단계에 도달한 후 모든 Office 데스크톱 응용 프로그램(Word, Excel, PowerPoint, Outlook 등)과 비즈니스용 OneDrive 클라이언트에 대해 다시 로그인해야 합니다. 로그인하면 Office 서비스에서 전역 Azure AD 서비스에서 새 인증 토큰을 얻을 수 있습니다.

응용 프로그램에서 Office 로그인한 후에도 Office 데스크톱 응용 프로그램이 작동하지 않을 경우 영향을 받는 컴퓨터의 Office 클라이언트 컷오버 [도구(OCCT)를](https://github.com/microsoft/OCCT) 실행하여 문제를 해결하는 것이 좋습니다.

[OCCT(Office 클라이언트](https://github.com/microsoft/OCCT) 컷오버 도구)가 Windows 클라이언트에 미리 배포되고 예약된 경우 로그인/로그인 절차가 필요하지 않습니다.

가장 최근의 응용 프로그램을 사용하여 최상의 사용자 환경을 Office 있습니다. 기업에서는 월별 채널을 사용하는 Enterprise 합니다.

모바일 장치 사전 작업을 [완료해야](ms-cloud-germany-transition-add-pre-work.md#mobile-device-management) 합니다.

추가 고려 사항:

- 사용자에게 모든 Office 앱을 닫은 다음 다시 로그인(또는 클라이언트를 다시 시작하고 사용자가 로그인하도록 강제)하여 Office 클라이언트가 변경 내용을 선택하도록 합니다.
- 사용자 및 지원 센터 직원에게 사용자가 72시간 이내에 Office 앱을 다시 활성화하라는 Office 배너가 표시될 수 있습니다.
- 개인 Office 모든 응용 프로그램을 닫고 사용자가 로그인한 다음 다시 로그인해야 합니다. 노란색 활성화 표시줄에서 로그인하여 서비스에서 Office 365 합니다.
- 공유 컴퓨터는 개인 컴퓨터와 유사한 작업이 필요하며 특별한 절차가 필요하지 않습니다.
- 모바일 장치에서 사용자는 앱에서 로그인하고 닫은 다음 다시 로그인해야 합니다.

## <a name="phase-9-line-of-business-apps"></a>9단계: 업무 앱

**다음에 적용됩니다.** 앱에 연결된 업무용 앱을 사용하는 Office 365

업무용 앱이 있는 경우 업무용 앱에 대한 사전 작업을 [완료해야](ms-cloud-germany-transition-add-pre-work.md#line-of-business-apps) 합니다.

## <a name="phase-9--10-azure-ad-finalization"></a>9단계 &: Azure AD 마무리

**다음에 적용됩니다.** 모든 고객

테넌트가 Office 365 최종 단계(9단계: Azure AD 완료)를 완료하면 모든 서비스가 전 세계로 전환됩니다. 응용 프로그램이나 사용자는 도이치랜드 Microsoft 클라우드 끝점에 대해 테넌트의 리소스에 액세스하지 말아야 합니다. 완료가 완료되고 30일 후에 자동으로 Microsoft 클라우드 도이치랜드 Azure AD 서비스가 전환된 테넌트에 대한 끝점 액세스를 중지합니다. 인증과 같은 끝점 요청은 도이치랜드 Microsoft 클라우드 서비스에 대해 이 시점부터 실패합니다.

Microsoft Azure 테넌트가 전 세계로의 마이그레이션을 완료하는 즉시 Azure 마이그레이션 플레이북에 설명된 단계에 따라 [Azure](/azure/germany/germany-migration-main) 워크로드를 전환해야 합니다(9단계).

<br>

****

|Step(s)|설명|영향|
|---|---|---|
|사용자 끝점 업데이트|모든 사용자가 적절한 Microsoft 전 세계 끝점을 사용하여 서비스에 액세스하도록 보장|마이그레이션이 완료된 후 30일이 지난 후 Microsoft 클라우드 도이클랜드 끝점은 요청의 존중을 중지합니다. 클라이언트 또는 응용 프로그램 트래픽이 실패합니다.|
|Azure AD 응용 프로그램 끝점 업데이트|응용 프로그램의 인증, Azure Active Directory(Azure AD) Graph 및 MS Graph 끝점을 Microsoft Worldwide 서비스의 끝점으로 업데이트해야 합니다.|마이그레이션이 완료된 후 30일이 지난 후 Microsoft 클라우드 도이클랜드 끝점은 요청의 존중을 중지합니다. 클라이언트 또는 응용 프로그램 트래픽이 실패합니다.|
|Azure Workloads 마이그레이션|Azure 서비스 고객은 Azure 서비스에 대한 새 전 세계 구독을 프로비전하고 Azure 마이그레이션 플레이북당 [마이그레이션을 실행해야 합니다.](/azure/germany/germany-migration-main)|전 세계 서비스로 완전히 전환하면(10단계) 고객은 더 이상 Microsoft 클라우드 도이치랜드 Azure 포털에 있는 Azure 워크로드에 액세스할 수 없습니다.|
|

**다음에 적용됩니다.** Azure AD 등록 또는 가입 장치를 사용 하는 고객

9단계가 완료되면 Azure AD 등록 및 가입된 장치를 새 독일 데이터 센터 지역의 전환된 Azure AD 인스턴스에 연결해야 합니다.
Azure AD에 다시 가입되지 않은 장치는 10단계가 끝나면 더 이상 작동하지 않을 수 있습니다. 자세한 지침과 자세한 내용은 장치에 대한 추가 [정보를 참조하세요.](ms-cloud-germany-transition-add-devices.md)

### <a name="azure-ad-connect"></a>Azure AD Connect

**다음에 적용됩니다.** Id를 Azure AD Connect와 동기화하는 모든 고객

<br>

****

|Step(s)|설명|영향|
|---|---|---|
|Azure AD 커넥트.|Azure AD로의 컷오버가 완료되면 조직은 Office 365 서비스를 완전히 사용하고 있으며 더 이상 도이치랜드 Microsoft 클라우드에 연결되지 않습니다. 이때 고객은 델타 동기화 프로세스가 완료되어 레지스트리 경로에서 문자열 값을 `AzureInstance` 3(도이치랜드 Microsoft 클라우드)에서 0으로 변경해야 `Computer\HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Azure AD Connect` 합니다.|의 값을 `AzureInstance` 레지스트리 키로 변경합니다. 이렇게 하지 못하면 Microsoft 클라우드 도이클라드 끝점을 더 이상 사용할 수 없는 후에 개체가 동기화되지 않습니다.|
|

## <a name="post-migration"></a>마이그레이션 후

마이그레이션 후 활동 [문서를](ms-cloud-germany-transition-add-experience.md) 읽고 그에 따라 실행해야 합니다.
