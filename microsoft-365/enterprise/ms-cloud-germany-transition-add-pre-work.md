---
title: Microsoft 클라우드 독일의 마이그레이션에 대 한 추가 사전 작업 정보
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
description: '요약: Microsoft cloud 독일에서 새 독일어 데이터 센터 지역의 Office 365 서비스로 이동할 때의 추가 사전 작업 정보입니다.'
ms.openlocfilehash: 41953aa9d91faa91bd983fbbc8d93baf08c172ed
ms.sourcegitcommit: 38d828ae8d4350ae774a939c8decf30cb36c3bea
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/02/2020
ms.locfileid: "49551712"
---
# <a name="additional-pre-work-information-for-the-migration-from-microsoft-cloud-deutschland"></a>Microsoft 클라우드 독일의 마이그레이션에 대 한 추가 사전 작업 정보

| 단계 | 설명 | 적용 대상 | 영향 |
|:-------|:-----|:-------|:-------|
| [Office 365 서비스 url 및 IP 주소](https://aka.ms/o365urls)에 대 한 네트워크 연결을 확인 합니다. | Office 365 서비스에 액세스 하는 데 사용 되는 고객이 호스트 하는 모든 클라이언트와 서비스는 Office 365 서비스 끝점에 액세스할 수 있어야 합니다. | 모든 전환 고객, 그리고 네트워크 액세스 권한이 있는 고객을 Microsoft 클라우드 독일으로 제한 합니다. | 필수 작업입니다. Inaction이 서비스 또는 클라이언트 소프트웨어에 오류가 발생할 수 있습니다. |
| 마이그레이션 관련 DNS 변경 사항을 검토 하 고 준비 합니다. | 고객은 Exchange Online 및 Exchange Online Protection (MX 레코드 등)에 대 한 DNS 항목을 준비 합니다. | Exchange Online 고객 | 이는 권장 되는 작업입니다. 어떤 동작이 든, Microsoft 클라우드 독일 서비스가 사용 하지 않도록 설정 될 때까지 마이그레이션된 고객의 전자 메일이 Microsoft 클라우드 독일를 통해 라우팅됩니다. |
| 마이그레이션 관련 DNS 변경 사항을 검토 하 고 준비 합니다. | 비즈니스용 Skype Online에 대 한 고객 소유 DNS 영역 변경 | 비즈니스용 Skype Online 고객 | -DNS 레코드를 새로 고칠 수 있도록 고객 소유 도메인 DNS 레코드의 TTL (Time-to-live)을 5 분으로 업데이트 하는 것이 좋습니다. 그러나 제공 된 24 시간 변경 창 내에서 언제 든 지이 DNS 변경 사항에 대 한 Microsoft의 관리 단위를 확인할 수 있습니다. <br><br> -나중에 서비스 중단이 발생할 수 있습니다. 사용자는 비즈니스용 Skype에 로그인 할 수 없으며 Office 365 서비스에서 마이그레이션된 팀 환경으로 리디렉션됩니다. |
| 최종 사용자 및 관리 교육을 준비 하 고 Microsoft 팀으로 전환 하기 위한 준비를 합니다. | 사용자 통신 및 준비 상태를 계획 하 여 Skype에서 팀으로의 전환에 성공 합니다. | 비즈니스용 Skype Online 고객 | -클라이언트는 새 서비스에 대해 알고 있어야 하며, 서비스가 Office 365 서비스로 전환 되 면 사용 하는 방법을 확인 해야 합니다. <br><br> -고객 베 니 티 도메인 및 초기 도메인에 대 한 DNS 변경이 수행 된 후 사용자가 비즈니스용 Skype에 로그인 하 여 이제 팀으로 마이그레이션될 것을 확인할 수 있습니다. 이를 통해 팀의 데스크톱 클라이언트도 백그라운드에서 다운로드 됩니다. |
| 사용자에 대 한 최종 사용자 및 관리 교육을 준비 하 고 iOS 및 Android 용 Microsoft Outlook에 계정을 제거 하 고 다시 추가 합니다. | Microsoft Cloud 독일의 사서함을 사용 하 여 구성 된 iOS 및 Android 용 microsoft Outlook 계정을 제거 하 고 Outlook에 다시 추가 해야 새 Office 365 서비스 구성을 제대로 동기화 할 수 있습니다. | IOS 및 Android 용 Microsoft Outlook 고객 | 이전에 Microsoft Cloud 독일 용으로 구성 된 Outlook 사서함은 새 Office 365 서비스 구성을 선택 하지 않고 오류가 발생 하 고 다른 사용자 환경의 성능이 저하 될 수 있습니다. IT 관리자는 마이그레이션 후에 메일에 로그인 하거나 동기화 하는 데 문제가 있는 경우 사용자가 iOS 및 Android 용 Microsoft Outlook에 계정을 제거 하 고 다시 추가 하도록 지시 하는 문서를 제공 하는 것이 좋습니다. |
| 마이그레이션 후 사용자에 게 다시 시작 하 고 클라이언트에 로그인 하는 것을 알릴 준비를 합니다. | Office 클라이언트 라이선스는 마이그레이션에서 Microsoft 클라우드 독일 Office 365 서비스로 전환 됩니다. 클라이언트는 Office 클라이언트에 로그인 한 후 유효한 새 라이선스를 선택 합니다. | Microsoft 365 Apps 고객 |  사용자의 Office 제품은 Office 365 서비스에서 라이선스를 새로 고쳐야 합니다. 라이선스를 새로 고치지 않으면 Office 제품에서 라이선스 유효성 검사 오류가 발생할 수 있습니다. |
| 평가판 구독을 취소 합니다. | 평가판 구독은 마이그레이션되지 않으며 유료 구독 전송도 차단 됩니다. | 모든 고객 | 평가판 서비스는 만료 되었으며, 취소 후 사용자가 액세스 하는 경우 작동 하지 않습니다. |
| 독일에서 비즈니스용 Skype에 액세스 하는 사용자에 게 팀 데스크톱 클라이언트를 배포 합니다. | 마이그레이션이 공동 작업, 통화 및 채팅을 위해 사용자를 팀으로 이동 합니다. 팀 데스크톱 클라이언트를 배포 하거나 지원 되는 브라우저를 사용할 수 있는지 확인 합니다. | 비즈니스용 Skype 고객 | Inaction에서는 팀 공동 작업 서비스를 사용할 수 없게 됩니다. |
| Microsoft Cloud 독일 및 Office 365 서비스 간의 라이선스 기능 차이를 분석 합니다. | Office 365 서비스에는 현재 Microsoft 클라우드 독일에서 사용할 수 없는 추가 기능과 서비스가 포함 되어 있습니다. 구독을 전송 하는 동안에는 사용자가 새 기능을 사용할 수 있습니다. | 모든 고객 | -Microsoft Cloud 독일 및 Office 365 서비스에 대 한 라이선스에서 제공 하는 다양 한 기능을 분석 합니다. [Office 365 플랫폼 서비스 설명을](https://docs.microsoft.com/office365/servicedescriptions/office-365-platform-service-description/office-365-platform-service-description)사용 하 여 시작 합니다. <br><br> -사용자 또는 사용자 변경 관리에 대 한 영향을 제한 하기 위해 초기에 Office 365 서비스의 새로운 기능을 사용 하지 않도록 설정 하 고 필요에 따라 사용자 라이선스 할당을 변경 하는 방법을 결정 합니다. <br><br> -Office 365 서비스에서 제공 하는 새 서비스 및 기능에 대 한 사용자 및 지원 센터 직원을 준비 합니다. |
| 마이그레이션 중 실수로 콘텐츠가 삭제 되지 않도록 보호 하는 조직 차원의 [보존 정책을](https://docs.microsoft.com/microsoft-365/compliance/retention) 만듭니다.  | -마이그레이션 중 최종 사용자가 콘텐츠를 실수로 삭제 하지 않도록 하기 위해 고객은 조직 전체의 보존 정책을 사용 하도록 선택할 수 있습니다. <br><br> -마이그레이션을 수행 하는 동안 언제 든 지 저장 된 보류가 예상 대로 작동 하기는 하지만 보존 정책이 백업 안전 메커니즘인 경우에는 보존이 필요 하지 않습니다. 동시에 모든 고객, 특히 보존 정책이 사용 되지 않을 수 있습니다 (예를 들어, 유지 관리에 대 한 자세한 내용은 사용자에 게 적합 합니다. | Office 고객 | 보존 정책 [및 보존 레이블에 대해 설명 하](https://docs.microsoft.com/microsoft-365/compliance/retention-policies)는 대로 보존 정책을 적용 합니다. |
| 재해 복구 시나리오를 위한 [AD FS (Active Directory Federation Services) 팜 백업](ms-cloud-germany-transition-add-adfs.md#backup) | 고객은 도메인의 발급자 URI에 접촉 하지 않고 글로벌 & 독일 끝점에 대 한 신뢰 당사자 트러스트를 복원할 수 있도록 AD FS 팜을 적절 하 게 백업 해야 합니다. 필요한 경우 팜 백업 및 해당 복원에 대해 AD FS 빠른 복원을 사용 하는 것이 좋습니다. | 페더레이션 인증 조직 | 필수 작업입니다. Inaction는 고객의 AD FS 팜이 실패 하면 마이그레이션 중에 서비스가 영향을 받습니다. |


## <a name="exchange-online"></a>Exchange Online

| 단계 | 설명 | 적용 대상 | 영향 |
|:-------|:-----|:-------|:-------|
| 향후에 Office 365 서비스에 대 한 전환에 대해 외부 파트너에 게 알립니다. | 가용성 주소 공간 구성은 Office 365에서 약속 있음/없음 정보를 공유할 수 있도록 합니다. | 일정 및 가용성 주소 공간 공유를 사용 하도록 설정한 Exchange Online 고객 | 필수 작업입니다.  이렇게 하지 않으면 나중에 고객 마이그레이션 단계에서 서비스 또는 클라이언트 오류가 발생할 수 있습니다. |
|||||

하이브리드 Exchange가 있는 경우:

| 단계 | 설명 | 적용 대상 | 영향 |
|:-------|:-----|:-------|:-------|
| 이전 버전의 하이브리드 구성 마법사 (HCW)를 제거한 다음 최신 버전인 17.0.5378.0을 설치 하 고 실행 [https://aka.ms/hybridwizard](https://aka.ms/hybridwizard) 합니다. | 최신 버전의 HCW에는 Microsoft Cloud 독일 from Office 365 Services로 전환 하는 고객을 지원 하기 위한 필수 업데이트가 포함 되어 있습니다. <br><br> 업데이트에는 송신 커넥터 및 수신 커넥터에 대 한 온-프레미스 인증서 설정의 변경 내용이 포함 됩니다. | 하이브리드 배포를 실행 하는 Exchange Online 고객 | 필수 작업입니다. 이렇게 하지 않으면 서비스 또는 클라이언트 오류가 발생할 수 있습니다. |
|||||

## <a name="sharepoint-online"></a>SharePoint Online

SharePoint 2013이 있는 경우:

| 단계 | 설명 | 적용 대상 | 영향 |
|:-------|:-----|:-------|:-------|
| Sharepoint 2013 워크플로 제한, SharePoint Online 마이그레이션 중에 사용 | 전환 전에 SharePoint 2013 워크플로를 줄이고 진행 중인 워크플로를 완성 합니다. | SharePoint Online 고객 | Inaction을 사용 하면 사용자의 혼란을 초래 하 고 지원 센터 통화를 받을 수 있습니다. |
|||||

<!--
[Reference:  If Pre-Work][ SharePoint 2013 ]
--> 

## <a name="mobile"></a>Mobile

타사 MDM (모바일 장치 관리) 솔루션을 사용 하는 경우:

| 단계 | 설명 | 적용 대상 | 영향 |
|:-------|:-----|:-------|:-------|
| 마이그레이션 후 재구성이 필요한 지 확인 합니다. | MDM 솔루션은 끝점을 대상으로 할 수 있습니다 `outlook.de` . 이 Office 365 Services로 전환 되 면 클라이언트 프로필이 Office 365 서비스 URL로 업데이트 됩니다 `outlook.office365.com` . | Exchange Online 및 MDM 고객 | 끝점에 액세스할 수 있는 동안에도 클라이언트는 계속 작동할 수 `outlook.de` 있지만 Microsoft Cloud 독일 endpoints를 더 이상 사용 하지 못할 경우에는 실패 합니다. |
|||||

<!--
[Reference:  If Pre-Work][ Mobile]
-->             

## <a name="line-of-business-apps"></a>기간 업무 (lob) 앱

Office 365와 통합 된 타사 서비스 또는 LOB (기간 업무) 앱을 사용 하는 경우: 

| 단계 | 설명 | 적용 대상 | 영향 |
|:-------|:-----|:-------|:-------|
| 마이그레이션 후 재구성이 필요한 지 확인 합니다. | Office 365와 통합 되는 타사 서비스 및 응용 프로그램은 Microsoft 클라우드 독일 IP 주소 및 Url을 예상 하도록 코딩할 수 있습니다. | 모든 고객 | 필수 작업입니다. Inaction이 서비스 또는 클라이언트 소프트웨어에 오류가 발생할 수 있습니다. |
|||||

<!--
[Reference:  If Pre-Work][ LOB]
--> 

## <a name="azure"></a>Azure 

| 단계 | 설명 | 적용 대상 | 영향 |
|:-------|:-----|:-------|:-------|
| 사용 중인 Azure services를 확인 하 고, 파트너와 함께 작업 하 여 독일에서 Office 365 서비스 테 넌 트로 마이그레이션할 때까지 준비 합니다. [Azure 마이그레이션 playbook](https://docs.microsoft.com/azure/germany/germany-migration-main)에 설명 된 단계를 수행 합니다. | Azure 리소스 마이그레이션은 고객의 책임 이며 규정 된 단계에 따라 수동 노력이 필요 합니다. Azure 서비스를 성공적으로 마이그레이션하기 위해서는 조직에서 사용 중인 서비스를 이해 하는 것이 중요 합니다. <br><br> Office 365 독일 구독 및 서비스 마이그레이션을 시작할 수 있는 경우 동일한 id 파티션 (조직)에 Azure 구독이 있는 고객은 Microsoft에서 지정한 순서를 따라야 합니다. | Azure 고객 | -고객은 여러 Azure 구독, 즉 인프라, 서비스 및 플랫폼 구성 요소를 포함 하는 각 구독을 포함할 수 있습니다. <br><br> -관리자는이 마이그레이션 이벤트의 일환으로 마이그레이션 및 유효성 검사를 수행할 수 있도록 구독 및 관련자를 식별 해야 합니다. <br><br> 지정 된 시간 표시 막대 내에서 이러한 구독 및 Azure 구성 요소의 마이그레이션을 성공적으로 완료 하지 못하면 office 및 Azure AD 전환에 Office 365 services로의 완료가 적용 되며 데이터 손실이 발생할 수 있습니다.  <br><br> -메시지 센터 알림은 고객-led 마이그레이션을 시작할 수 있는 지점에 신호를 알립니다. |
|||||

<!--
[Reference:  If Azure Pre-Work][ Azure]
-->  

## <a name="dynamics-365"></a>Dynamics 365

| 단계 | 설명 | 적용 대상 | 영향 |
|:-------|:-----|:-------|:-------|
| Dynamics 365 샌드박스 구독의 경우 Microsoft 클라우드 독일의 Dynamics 365 구독에서 Dynamics SQL 인스턴스의 프로덕션 환경을 다운로드 해야 합니다. 최신 프로덕션 백업은 샌드박스 마이그레이션 전에 샌드박스로 복원 해야 합니다. | Dynamics 365 마이그레이션에는 고객 들이 최신 프로덕션 데이터베이스를 사용 하 여 샌드박스 환경을 새로 고칠 수 있도록 요구 합니다. | Microsoft Dynamics 고객 | FastTrack 팀은 고객이 건조 한 실행을 수행 하는 데 도움을 줍니다. x에서 w.x.y.z로의 버전 업그레이드 유효성을 검사 합니다. |
|||||

<!--
[Reference: Prework][Dynamics]
-->             

## <a name="power-bi"></a>Power BI

| 단계 | 설명 | 적용 대상 | 영향 |
|:-------|:-----|:-------|:-------|
| Power BI Microsoft Cloud 독일에서 Office 365 서비스로 마이그레이션되지 않는 Power BI 구독에서 개체를 제거 합니다. | Power BI 서비스를 마이그레이션하려면 사용자 작업을 통해 데이터 집합 및 대시보드와 같은 특정 아티팩트를 삭제 해야 합니다. | Power BI 고객 | 관리자는 구독에서 다음 항목을 제거 해야 할 수 있습니다. <br> -Real-Time 데이터 집합 (예: 스트리밍 또는 푸시 데이터 집합) <br> -Power BI 온-프레미스 데이터 게이트웨이 구성 및 데이터 원본 |
|||||

<!--
[Reference: Prework][Power BI]
--> 

## <a name="dns"></a>DNS

| 단계 | 설명 | 적용 대상 | 영향 |
|:-------|:-----|:-------|:-------|
| 현재 DNS에 MSOID CName 항목이 있으면 DNS 변경 내용을 검토 하 고 준비 합니다. | 고객 소유 DNS 영역 변경 | Office 클라이언트 서비스 고객 | MSOID CName이 있는 경우 고객 소유 DNS 레코드에 대 한 TTL (Time to Live)을 5 분으로 업데이트 합니다. |
|||||

<!--
[Reference: Prework][DNS]
-->             

## <a name="federated-identity"></a>페더레이션 ID

| 단계 | 설명 | 적용 대상 | 영향 |
|:-------|:-----|:-------|:-------|
| 글로벌 Azure AD 끝점에 대 한 신뢰 당사자 트러스트를 생성 합니다. | 고객은 [전역](https://nexus.microsoftonline-p.com/federationmetadata/2007-06/federationmetadata.xml) 끝점에 대 한 RPT (신뢰 당사자 트러스트)를 수동으로 만들어야 합니다. 이 작업은 GUI를 통해 새 RPT를 추가한 다음 (AD FS 도움말) [AZURE AD RPT 클레임 규칙](https://adfshelp.microsoft.com/AadTrustClaims/ClaimsGenerator#:~:text=%20Azure%20AD%20RPT%20Claim%20Rules%20%201,Azure%20AD.%20This%20will%20be%20what...%20More%20) 을 사용 하 여 클레임 규칙을 생성 하 고이를 RPT로 가져오는 방식으로 수행 됩니다. | 페더레이션 인증 조직 | 필수 작업입니다. Inaction에서는 마이그레이션 중에 서비스가 영향을 받습니다. |
|||||

<!--
[Reference: Prework][Federation]
-->  

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
