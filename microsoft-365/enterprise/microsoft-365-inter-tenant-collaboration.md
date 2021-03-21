---
title: Microsoft 365 테넌트 간 공동 작업
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
audience: Admin
ms.topic: overview
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-collaboration
- M365-subscription-management
- SPO_Content
search.appverid:
- MET150
- MOE150
ms.assetid: eb45fd8b-1d5d-4b0c-9c5a-479dbb176e7d
f1.keywords:
- NOCSH
description: 테넌트 및 조직 전체에서 Microsoft 365 공동 작업의 작동 방식에 대해 알아보고, 여러 조직이 안전하게 공동 작업할 수 있도록 합니다.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: b4ff55d9bc355a03e7f7336bd01d3c19a60d2d31
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/19/2021
ms.locfileid: "50923281"
---
# <a name="microsoft-365-inter-tenant-collaboration"></a>Microsoft 365 테넌트 간 공동 작업

Fabrikam과 Contoso의 두 조직이 각각 비즈니스용 Microsoft 365 테넌트가 있으며 여러 프로젝트에서 함께 작업하려는 경우를 가정해 가정해 가정합니다. 이 중 일부는 제한된 시간 동안 실행되고 일부는 진행 중입니다. Fabrikam 및 Contoso를 통해 사용자와 팀이 안전한 방식으로 다른 Microsoft 365 테넌트에서 보다 효과적으로 공동 작업을 할 수 있는 방법 Microsoft 365는 Azure AD(Azure Active Directory) B2B 공동 작업과 함께 몇 가지 옵션을 제공합니다. 이 문서에서는 Fabrikam과 Contoso가 고려할 수 있는 몇 가지 주요 시나리오에 대해 설명합니다.
  
Microsoft 365 테넌트 간 공동 작업 옵션에는 파일 및 대화를 위한 중앙 위치 사용, 일정 공유, 통신을 위한 IM 사용, 오디오/비디오 통화 사용, 리소스 및 응용 프로그램에 대한 액세스 보안이 포함됩니다. 다음 표를 사용하여 솔루션을 선택하고 자세히 알아보십시오.
  
## <a name="exchange-online-collaboration-options"></a>Exchange Online 공동 작업 옵션

| 공유 목표 | 관리 작업 | 방법 정보 |
|:-----|:-----|:-----|
|다른 Microsoft 365 조직과 일정 공유 |관리자는 Exchange Online에서 서로 다른 일정 액세스 수준을 설정하여 기업이 다른 기업과 공동 작업을 할 수 있도록 허용하고 사용자가 일정(약속이 있는/약속이 있는 정보)을 다른 사용자와 공유할 수 있도록 할 수 있습니다. | <ul><li>[공유](/exchange/sharing/sharing) </li><li> [조직 관계](/exchange/sharing/organization-relationships/organization-relationships) </li><li> [조직 관계 만들기](/exchange/sharing/organization-relationships/create-an-organization-relationship) </li><li> [조직 관계 수정 ](/exchange/sharing/organization-relationships/modify-an-organization-relationship) </li><li> [조직 관계 제거](/exchange/sharing/organization-relationships/remove-an-organization-relationship) </li><li> [외부 사용자와 사이트 공유](https://support.office.com/article/fb00dd4e-2d5f-4e8d-8ff4-94b2cf002bdd) </li></ul> |
|사용자가 조직 외부의 사용자와 일정을 공유하는 방법 제어 | 관리자는 공유 정책을 사용자 사서함에 적용하여 공유할 수 있는 사용자 및 부여된 액세스 수준을 제어합니다. |  <ul><li> [공유 정책](/exchange/sharing/sharing-policies/sharing-policies) </li><li> [공유 정책 만들기](/exchange/sharing/sharing-policies/create-a-sharing-policy) </li><li> [사서함에 공유 정책 적용](/exchange/sharing/sharing-policies/apply-a-sharing-policy) </li><li> [공유 정책 수정, 해제 또는 제거](/exchange/sharing/sharing-policies/modify-a-sharing-policy) </li></ul> |
|파트너 조직과의 보안 전자 메일 채널 구성 및 메일 흐름 제어 | 관리자는 커넥터를 만들어 파트너 조직 또는 서비스 공급자와의 메일 교환에 보안을 적용합니다. 커넥터는 TLS(전송 계층 보안)를 통해 암호화를 적용하고 파트너가 전자 메일을 보내는 도메인 이름 또는 IP 주소 범위에 대한 제한을 허용합니다. |  <ul><li> [Office 365의 전자 메일 연결 보안을 위해 Exchange Online에서 TLS를 사용하는 방법](../compliance/exchange-online-uses-tls-to-secure-email-connections.md) </li><li> [커넥터를 사용하여 메일 흐름 구성](/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow) </li><li> [원격 도메인](/exchange/mail-flow-best-practices/remote-domains/remote-domains) </li><li> [파트너 조직과의 보안 메일 흐름을 위한 커넥터 설정](/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/set-up-connectors-for-secure-mail-flow-with-a-partner) </li><li> [메일 흐름 모범 사례(개요)](/exchange/mail-flow-best-practices/mail-flow-best-practices) </li></ul> |
   
## <a name="sharepoint-online-and-onedrive-for-business-collaboration-options"></a>SharePoint Online 및 비즈니스용 OneDrive 공동 작업 옵션

| 공유 목표 | 관리 작업 | 방법 정보 |
|:-----|:-----|:-----|
|외부 사용자와 사이트 및 문서 공유 | 관리자는 테넌트에서 공유를 구성하거나 Microsoft 계정 인증, 직장 또는 학교 계정 인증 또는 게스트 계정에 대한 사이트 모음 수준을 구성합니다. |  <ul><li> [SharePoint Online 환경에 대해 외부 공유 관리](https://support.office.com/article/Manage-external-sharing-for-your-SharePoint-Online-environment-C8A462EB-0723-4B0B-8D0A-70FEAFE4BE85?ui=en-US&amp;rs=en-US&amp;ad=US) </li><li> [도메인으로 SharePoint 및 OneDrive 콘텐츠 공유 제한](/sharepoint/restricted-domains-sharing) </li><li> [SharePoint Online을 B2B(기업 대기업) 엑스트라넷 솔루션으로 사용](https://support.office.com/article/7b087413-165a-4e94-8871-4393e0b9c037) </li></ul> |
|최종 사용자의 외부 공유 추적 및 제어 | 비즈니스용 OneDrive 파일 소유자 및 SharePoint Online 최종 사용자는 사이트 및 문서 공유를 구성하고 공유를 추적하기 위한 알림을 수립합니다. |  <ul><li> [비즈니스용 OneDrive의 외부 공유에 대한 알림 구성](https://support.office.com/article/Configure-notifications-for-external-sharing-for-OneDrive-for-Business-b640c693-f170-4227-b8c1-b0a7e0fa876b) </li><li> [SharePoint 파일 또는 폴더 공유](https://support.office.com/article/1fe37332-0f9a-4719-970e-d2578da4941c) </li></ul> |
   
## <a name="skype-for-business-collaboration-options"></a>비즈니스용 Skype 공동 작업 옵션

| 공유 목표 | 관리 작업 | 방법 정보 |
|:-----|:-----|:-----|
|비즈니스용 Skype Online - 다른 비즈니스용 Skype 사용자와의 IM, 통화 및 현재 상태 | 관리자는 비즈니스용 Skype Online 사용자가 IM을 사용하도록 설정하고, 오디오/비디오 통화를 걸고, 다른 Microsoft 365 테넌트의 사용자와 현재 상태 확인을 할 수 있습니다. | [사용자가 외부 비즈니스용 Skype 사용자와 연락하도록 허용](https://support.office.com/article/b414873a-0059-4cd5-aea1-e5d0857dbc94)| 
|비즈니스용 Skype Online - Skype(소비자) 사용자의 IM, 통화 및 현재 상태 | 관리자는 비즈니스용 Skype Online 사용자가 IM을 사용하도록 설정하고, 전화를 걸고, Skype(소비자) 사용자의 현재 상태도 볼 수 있습니다. | [비즈니스용 Skype 사용자가 Skype 연락처를 추가하도록 허용](https://support.office.com/article/08666236-1894-42ae-8846-e49232bbc460)| 
   
## <a name="azure-ad-b2b-collaboration-options"></a>Azure AD B2B 공동 작업 옵션

| 공유 목표 | 관리 작업 | 방법 정보 |
|:-----|:-----|:-----|
|Azure AD B2B 공동 작업 - 조직 디렉터리의 그룹에 외부 사용자를 추가하여 콘텐츠 공유 | 한 Microsoft 365 테넌트의 전역 관리자는 다른 Microsoft 365 테넌트의 사용자를 초대하여 디렉터리에 참가하고, 해당 외부 사용자를 그룹에 추가하고, 그룹의 SharePoint 사이트 및 라이브러리와 같은 콘텐츠에 대한 액세스 권한을 부여할 수 있습니다. |  <ul><li> [Azure AD B2B 공동 작업 미리 보기란?](/azure/active-directory/active-directory-b2b-what-is-azure-ad-b2b) </li><li> [Azure AD B2B: 새로운 업데이트로 비즈니스 간 콜라브를 쉽게 만들 수 있습니다.](https://blogs.technet.microsoft.com/enterprisemobility/2017/02/01/azure-ad-b2b-new-updates-make-cross-business-collab-easy/) </li><li> [외부 공유 및 Azure Active Directory B2B 공동 작업](/azure/active-directory/active-directory-b2b-o365-external-user) </li><li> [Azure Active Directory B2B 공동 작업 API 및 사용자 지정](/azure/active-directory/active-directory-b2b-api) </li><li> [Azure AD 및 ID 쇼: Azure AD B2B 공동 작업(비즈니스-비즈니스)](https://channel9.msdn.com/Series/Azure-AD-Identity/AzureADB2B) </li></ul> |
   
## <a name="microsoft-365-collaboration-options"></a>Microsoft 365 공동 작업 옵션

| 공유 목표 | 관리 작업 | 방법 정보 |
|:-----|:-----|:-----|
|Microsoft 365 그룹 - 중앙 위치의 전자 메일, 일정, OneNote 및 공유 파일 | 그룹은 Business Essentials, Business Premium, Education 및 Enterprise E1, E3 및 E5 계획에서 지원됩니다. 한 Microsoft 365 테넌트의 사용자는 그룹을 만들고 다른 Microsoft 365 테넌트의 사용자를 게스트 사용자로 초대할 수 있습니다. Dynamics CRM에도 적용됩니다. |  <ul><li> [Microsoft 365 그룹에 대해 자세히 알아보세요.](https://support.office.com/article/b565caa1-5c40-40ef-9915-60fdb2d97fa2) </li><li> [Microsoft 365 그룹의 게스트 액세스](https://support.office.com/article/bfc7a840-868f-4fd6-a390-f347bf51aff6) </li><li> [Microsoft 365 그룹 배포](/previous-versions/dynamicscrm-2016/administering-dynamics-365/dn896591(v=crm.8)) </li></ul> |
   
## <a name="yammer-collaboration-options"></a>Yammer 옵션

| 공유 목표 | 관리 작업 | 방법 정보 |
|:-----|:-----|:-----|
|Yammer - 엔터프라이즈 소셜 미디어를 통한 공동 작업 | Yammer 관리자가 외부 그룹을 만드는 기능을 사용하지 않도록 설정하지 않는 한 사용자는 외부 그룹을 만들어 대화, 게시물을 Yammer 팔로우, 파일 공유 및 온라인 채팅을 통해 공동 작업을 할 수 있습니다. | [Yammer의 외부 그룹 만들기 및 관리](https://support.office.com/article/9ccd15ce-0efc-4dc1-81bc-4a424ab6f92a)| 
   
## <a name="teams-collaboration-options"></a>Teams 공동 작업 옵션

|공유 목표|관리 작업|방법 정보|
|:-----|:-----|:-----|
|조직 외부의 사용자와 Teams에서 공동 작업 | Microsoft 365 테넌트에 대한 전역 관리자는 Teams에서 외부 공동 작업을 활성화해야 합니다. 이제 전역 관리자와 팀 소유자가 전자 메일 주소가 있는 모든 사람을 Teams에서 공동 작업할 수 있습니다.  <br/> 관리자는 이미 테넌트에 있는 게스트를 관리하고 편집할 수도 있습니다. |  <ul><li> [게스트 액세스 권한을 부여합니다.](/microsoftteams/teams-dependencies) </li><li> [Teams에서 게스트 액세스 설정 또는 해제](/microsoftteams/set-up-guests) </li><li> [PowerShell을 사용하여 게스트 액세스 제어](/microsoftteams/guest-access-powershell) </li><li> [게스트 액세스 검사 목록](/microsoftteams/guest-access-checklist) </li><li> [게스트 사용자 보기](/microsoftteams/view-guests) </li><li> [게스트 사용자 정보 편집](/microsoftteams/edit-guests-information) </li></ul> |
|팀 소유자는 게스트가 팀 내에서 공동 작업하는 방법을 초대하고 관리할 수 있습니다.  |팀 소유자는 게스트가 팀 내에서 할 수 있는 작업을 추가로 제어할 수 있습니다. |  <ul><li> [게스트 추가](https://support.office.com/article/teams-and-channels-df38ae23-8f85-46d3-b071-cb11b9de5499?ui=en-US&amp;rs=en-US&amp;ad=US#bkmk_addingguests&amp;ID0EAABAAA=Add_guests) </li><li> [팀에 게스트 추가](/microsoftteams/add-guests) </li><li> [Teams에서 게스트 액세스 관리](/microsoftteams/manage-guests) </li><li> [팀 또는 채널에 있는 사람 보기](https://support.office.com/article/see-who-s-on-a-team-or-in-a-channel-5c6be9be-9c45-4a0f-a1a0-f332b23cb6b7?ui=en-US&amp;rs=en-US&amp;ad=US) </li></ul> |
|다른 테넌트의 게스트는 Teams의 콘텐츠를 보고 다른 구성원과 공동 작업을 할 수 있습니다. | 없음 | [게스트 액세스 환경](/microsoftteams/guest-experience)| 

## <a name="power-bi-collaboration-options"></a>Power BI 공동 작업 옵션

| 공유 목표 | 관리 작업 | 방법 정보 |
|:-----|:-----|:-----|
|Power BI를 사용하면 외부 게스트 사용자가 링크를 통해 공유되는 콘텐츠를 사용할 수 있습니다. 따라서 조직의 사용자가 조직 전체에 안전한 방식으로 콘텐츠를 배포할 수 있습니다.<br/> | Power BI 관리자는 사용자가 조직 내에서 콘텐츠를 볼 수 있도록 외부 사용자를 초대할 수 있는지 여부를 제어할 수 있습니다.| [Azure AD B2B를 사용하여 외부 게스트 사용자에게 Power BI 콘텐츠 배포](/power-bi/service-admin-azure-ad-b2b) | 
 
## <a name="points-to-be-aware-of-about-microsoft-365-inter-tenant-collaboration"></a>Microsoft 365 테넌트 간 공동 작업 관련 주의할 점

### <a name="sharing-of-user-accounts-licenses-subscriptions-and-storage"></a>사용자 계정, 라이선스, 구독 및 저장소 공유

각 조직은 자체 사용자 계정, ID, 보안 그룹, 구독, 라이선스 및 저장소를 유지 관리합니다. 사용자들은 Microsoft 365의 공동 작업 기능과 정책 및 보안 설정을 공유하여 회사 자산에 대한 제어를 유지하면서 필요한 정보에 대한 액세스 권한을 제공합니다.
  
- **사용자 계정:** 계정은 테넌트 또는 파티션 간에 공유하거나 복제할 수 없습니다. 
    
- **라이선스 &amp; 구독:** Microsoft 365에서 라이선스 계획의 라이선스(SKUS 또는 Microsoft 365 계획이라고도 합니다.)는 사용자에게 해당 계획에 대해 정의된 Microsoft 365 서비스에 대한 액세스 권한을 부여합니다. 
    
- **저장소:** Microsoft 365 라이선스 계획에서 SharePoint Online의 소프트웨어 경계 및 제한은 사서함 저장소 제한과는 별도로 관리됩니다. 사서함 저장소 제한은 Exchange Online을 사용하여 설정 및 관리됩니다. 두 시나리오에서 저장소는 테넌트에서 공유할 수 없습니다. 
    
### <a name="can-we-share-domain-namespaces-across-microsoft-365-tenants"></a>Microsoft 365 테넌트에서 도메인 네임스페이스를 공유할 수 있나요?

아니요. 조직 도메인 이름(예: fabrikam.com 또는 tailspintoys.com)은 단일 Microsoft 365 테넌트에만 연결하고 사용할 수 있습니다. 각 테넌트에는 자체 네임스페이스가 있어야 합니다. UPN, SMTP 및 SIP 네임스페이스는 테넌트에서 공유할 수 없습니다.
  
### <a name="what-about-hybrid-components-and-microsoft-365-inter-tenant-collaboration"></a>하이브리드 구성 요소 및 Microsoft 365 테넌트 간 공동 작업은 어떻게 하나요?

Exchange 조직 및 Azure AD Connect와 같은 사내 하이브리드 구성 요소는 여러 테넌트로 분할할 수 없습니다.
