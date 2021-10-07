---
title: Microsoft 365 테넌트 간 공동 작업
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
audience: Admin
ms.topic: overview
ms.service: o365-administration
ms.localizationpriority: medium
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
description: 테넌트 Microsoft 365 조직 전체에서 공동 작업의 작동 방식에 대해 알아보고, 여러 조직이 안전하게 공동 작업할 수 있도록 합니다.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 9cb91b6bcaac212eeaf0ef4051f466751d8dbbd9
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/06/2021
ms.locfileid: "60163339"
---
# <a name="microsoft-365-inter-tenant-collaboration"></a>Microsoft 365 테넌트 간 공동 작업

Fabrikam과 Contoso의 두 조직이 각각 비즈니스 테넌트에 대한 Microsoft 365 조직을 가지며 여러 프로젝트에서 함께 작업하려는 경우를 가정해 가정해 가정합니다. 이 중 일부는 제한된 시간 동안 실행되고 일부는 진행 중입니다. Fabrikam과 Contoso는 어떻게 사용자와 팀이 안전한 방식으로 다른 Microsoft 365 테넌트에서 더 효과적으로 공동 작업을 할 수 있나요? Microsoft 365 Azure AD(Azure Active Directory) B2B 공동 작업과 함께 몇 가지 옵션을 제공합니다. 이 문서에서는 Fabrikam과 Contoso가 고려할 수 있는 몇 가지 주요 시나리오에 대해 설명합니다.

Microsoft 365 테넌트 간 공동 작업 옵션에는 파일 및 대화에 대한 중앙 위치 사용, 일정 공유, 통신을 위한 IM 사용, 오디오/비디오 통화 사용, 리소스 및 응용 프로그램에 대한 액세스 보안이 포함됩니다. 다음 표를 사용하여 솔루션을 선택하고 자세히 알아보십시오.

## <a name="exchange-online-collaboration-options"></a>Exchange Online 옵션

| 공유 목표 | 관리 작업 | 방법 정보 |
|:-----|:-----|:-----|
|다른 조직과 일정 Microsoft 365 공유 |관리자는 서로 다른 비즈니스와 공동 작업을 Exchange Online 일정(약속이 있는/약속이 있는 정보)을 다른 사용자와 공유할 수 있도록 여러 일정 액세스 수준을 설정할 수 있습니다. | <ul><li>[공유](/exchange/sharing/sharing) </li><li> [조직 관계](/exchange/sharing/organization-relationships/organization-relationships) </li><li> [조직 관계 만들기](/exchange/sharing/organization-relationships/create-an-organization-relationship) </li><li> [Exchange Online의 조직 관계 수정](/exchange/sharing/organization-relationships/modify-an-organization-relationship) </li><li> [조직 관계 제거](/exchange/sharing/organization-relationships/remove-an-organization-relationship) </li><li> [외부 사용자와 사이트 공유](https://support.office.com/article/fb00dd4e-2d5f-4e8d-8ff4-94b2cf002bdd) </li></ul> |
|사용자가 조직 외부의 사용자와 일정을 공유하는 방법 제어 | 관리자는 공유 정책을 사용자 사서함에 적용하여 공유할 수 있는 사용자 및 부여된 액세스 수준을 제어합니다. |  <ul><li> [공유 정책](/exchange/sharing/sharing-policies/sharing-policies) </li><li> [공유 정책 만들기](/exchange/sharing/sharing-policies/create-a-sharing-policy) </li><li> [사서함에 공유 정책 적용](/exchange/sharing/sharing-policies/apply-a-sharing-policy) </li><li> [공유 정책 수정, 해제 또는 제거](/exchange/sharing/sharing-policies/modify-a-sharing-policy) </li></ul> |
|파트너 조직과의 보안 전자 메일 채널 구성 및 메일 흐름 제어 | 관리자는 커넥터를 만들어 파트너 조직 또는 서비스 공급자와의 메일 교환에 보안을 적용합니다. 커넥터는 TLS(전송 계층 보안)를 통해 암호화를 적용하고 파트너가 전자 메일을 보내는 도메인 이름 또는 IP 주소 범위에 대한 제한을 허용합니다. |  <ul><li> [Office 365의 전자 메일 연결 보안을 위해 Exchange Online에서 TLS를 사용하는 방법](../compliance/exchange-online-uses-tls-to-secure-email-connections.md) </li><li> [커넥터를 사용하여 메일 흐름 구성](/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow) </li><li> [원격 도메인](/exchange/mail-flow-best-practices/remote-domains/remote-domains) </li><li> [파트너 조직과의 보안 메일 흐름을 위한 커넥터 설정](/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/set-up-connectors-for-secure-mail-flow-with-a-partner) </li><li> [메일 흐름 모범 사례(개요)](/exchange/mail-flow-best-practices/mail-flow-best-practices) </li></ul> |

## <a name="sharepoint-online-and-onedrive-for-business-collaboration-options"></a>SharePoint 온라인 및 비즈니스용 OneDrive 공동 작업 옵션

| 공유 목표 | 관리 작업 | 방법 정보 |
|:-----|:-----|:-----|
|외부 사용자와 사이트 및 문서 공유 | 관리자는 테넌트에서 공유를 구성하거나 Microsoft 계정 인증, 직장 또는 학교 계정 인증 또는 게스트 계정에 대한 사이트 모음 수준을 구성합니다. |  <ul><li> [SharePoint Online 환경에 대해 외부 공유 관리](https://support.office.com/article/Manage-external-sharing-for-your-SharePoint-Online-environment-C8A462EB-0723-4B0B-8D0A-70FEAFE4BE85?ui=en-US&amp;rs=en-US&amp;ad=US) </li><li> [도메인별 SharePoint 및 OneDrive 콘텐츠의 공유 제한](/sharepoint/restricted-domains-sharing) </li><li> [B2B SharePoint 엑스트라넷 솔루션으로 SharePoint Online 사용](https://support.office.com/article/7b087413-165a-4e94-8871-4393e0b9c037) </li></ul> |
|최종 사용자의 외부 공유 추적 및 제어 | 비즈니스용 OneDrive 소유자 및 SharePoint 온라인 최종 사용자가 사이트 및 문서 공유를 구성하고 공유를 추적할 알림을 수립합니다. |  <ul><li> [외부 공유에 대한 알림 비즈니스용 OneDrive](https://support.office.com/article/Configure-notifications-for-external-sharing-for-OneDrive-for-Business-b640c693-f170-4227-b8c1-b0a7e0fa876b) </li><li> [SharePoint 파일 또는 폴더 공유](https://support.office.com/article/1fe37332-0f9a-4719-970e-d2578da4941c) </li></ul> |

## <a name="skype-for-business-collaboration-options"></a>비즈니스용 Skype 옵션

| 공유 목표 | 관리 작업 | 방법 정보 |
|:-----|:-----|:-----|
|비즈니스용 Skype 온라인 - 다른 사용자와의 IM, 통화 비즈니스용 Skype 상태 | 관리자는 비즈니스용 Skype Online 사용자가 IM을 사용하도록 설정하고, 오디오/비디오 통화를 걸고, 다른 테넌트의 사용자와의 현재 Microsoft 365 있습니다. | [사용자가 외부 비즈니스용 Skype 사용자와 연락하도록 허용](https://support.office.com/article/b414873a-0059-4cd5-aea1-e5d0857dbc94)|
|비즈니스용 Skype 온라인 - SKYPE 사용자와의 IM, 통화 및 현재 상태 | 관리자는 비즈니스용 Skype Online 사용자가 IM을 사용하도록 설정하고, 전화를 걸고, 사용자(소비자) 사용자와의 현재 Skype 수 있습니다. | [비즈니스용 Skype 사용자가 Skype 연락처를 추가하도록 허용](https://support.office.com/article/08666236-1894-42ae-8846-e49232bbc460)|

## <a name="azure-ad-b2b-collaboration-options"></a>Azure AD B2B 공동 작업 옵션

| 공유 목표 | 관리 작업 | 방법 정보 |
|:-----|:-----|:-----|
|Azure AD B2B 공동 작업 - 조직 디렉터리의 그룹에 외부 사용자를 추가하여 콘텐츠 공유 | 한 Microsoft 365 테넌트의 Azure **AD DC** 관리자,  보안 관리자, 사용자 관리자, 클라우드 응용 프로그램 관리자 또는 전역 관리자는 다른 Microsoft 365 테넌트의 사용자를 초대하여 디렉터리에 참가하고, 해당 외부 사용자를 그룹에 추가하고, 그룹의 SharePoint 사이트 및 라이브러리와 같은 콘텐츠에 대한 액세스 권한을 부여할 수 있습니다.   |  <ul><li> [Azure AD B2B 공동 작업 미리 보기란?](/azure/active-directory/active-directory-b2b-what-is-azure-ad-b2b) </li><li> [Azure AD B2B: 새로운 업데이트로 비즈니스 간 콜라브를 쉽게 만들 수 있습니다.](https://blogs.technet.microsoft.com/enterprisemobility/2017/02/01/azure-ad-b2b-new-updates-make-cross-business-collab-easy/) </li><li> [외부 공유 및 Azure Active Directory B2B 공동 작업](/azure/active-directory/active-directory-b2b-o365-external-user) </li><li> [Azure Active Directory B2B 공동 작업 API 및 사용자 지정](/azure/active-directory/active-directory-b2b-api) </li><li> [Azure AD 및 ID 쇼: Azure AD B2B 공동 작업(비즈니스-비즈니스)](https://channel9.msdn.com/Series/Azure-AD-Identity/AzureADB2B) </li></ul> |

## <a name="microsoft-365-collaboration-options"></a>Microsoft 365 옵션

| 공유 목표 | 관리 작업 | 방법 정보 |
|:-----|:-----|:-----|
|Microsoft 365 그룹 - 중앙 위치의 전자 메일, OneNote, 공유 파일 | 그룹은 Business Essentials, Business Premium, Education 및 Enterprise E1, E3 및 E5 계획에서 지원됩니다. 한 Microsoft 365 테넌트의 사용자는 그룹을 만들고 다른 Microsoft 365 테넌트의 사용자를 게스트 사용자로 초대할 수 있습니다. Dynamics CRM에도 적용됩니다. |  <ul><li> [Microsoft 365 그룹에 대해 자세히 알아보세요.](https://support.office.com/article/b565caa1-5c40-40ef-9915-60fdb2d97fa2) </li><li> [Microsoft 365 그룹의 게스트 액세스](https://support.office.com/article/bfc7a840-868f-4fd6-a390-f347bf51aff6) </li><li> [그룹 Microsoft 365 배포](/previous-versions/dynamicscrm-2016/administering-dynamics-365/dn896591(v=crm.8)) </li></ul> |

## <a name="yammer-collaboration-options"></a>Yammer 공동 작업 옵션

| 공유 목표 | 관리 작업 | 방법 정보 |
|:-----|:-----|:-----|
|Yammer - 엔터프라이즈 소셜 미디어를 통한 공동 작업 | Yammer 관리자가 외부 그룹을 만드는 기능을 사용하지 않도록 설정하지 않는 한 사용자는 대화, 게시물을 Yammer 팔로우, 파일 공유 및 온라인 채팅을 통해 외부 그룹으로 공동 작업을 할 수 있습니다. | [Yammer의 외부 그룹 만들기 및 관리](https://support.office.com/article/9ccd15ce-0efc-4dc1-81bc-4a424ab6f92a)|

## <a name="teams-collaboration-options"></a>Teams 공동 작업 옵션

|공유 목표|관리 작업|방법 정보|
|:-----|:-----|:-----|
|조직 외부의 Teams 사용자와 공동 작업 | **테넌트의**  사용자 관리자 또는 테넌트 Microsoft 365 전역 관리자는 해당 사용자에서 외부 공동 작업을 사용하도록 Teams. 이제 전역 관리자와 팀 소유자가 전자 메일 주소가 있는 모든 사람을 초대하여 공동 작업을 할 수 Teams.  <br/> 관리자는 이미 테넌트에 있는 게스트를 관리하고 편집할 수도 있습니다. |  <ul><li> [게스트 액세스 권한을 부여합니다.](/microsoftteams/teams-dependencies) </li><li> [2016에서 게스트 액세스 설정 또는 Teams](/microsoftteams/set-up-guests) </li><li> [PowerShell을 사용하여 게스트 액세스 제어](/microsoftteams/guest-access-powershell) </li><li> [게스트 액세스 검사 목록](/microsoftteams/guest-access-checklist) </li><li> [게스트 사용자 보기](/microsoftteams/view-guests) </li><li> [게스트 사용자 정보 편집](/microsoftteams/edit-guests-information) </li></ul> |
|팀 소유자는 게스트가 팀 내에서 공동 작업하는 방법을 초대하고 관리할 수 있습니다.  |팀 소유자는 게스트가 팀 내에서 할 수 있는 작업을 추가로 제어할 수 있습니다. |  <ul><li> [게스트 추가](https://support.office.com/article/teams-and-channels-df38ae23-8f85-46d3-b071-cb11b9de5499?ui=en-US&amp;rs=en-US&amp;ad=US#bkmk_addingguests&amp;ID0EAABAAA=Add_guests) </li><li> [팀에 게스트 추가](/microsoftteams/add-guests) </li><li> [2016에서 게스트 액세스 Teams](/microsoftteams/manage-guests) </li><li> [팀 또는 채널에 있는 사람 보기](https://support.office.com/article/see-who-s-on-a-team-or-in-a-channel-5c6be9be-9c45-4a0f-a1a0-f332b23cb6b7?ui=en-US&amp;rs=en-US&amp;ad=US) </li></ul> |
|다른 테넌트의 게스트는 다른 테넌트의 콘텐츠를 보고 Teams 공동 작업할 수 있습니다. | 없음 | [게스트 액세스 환경](/microsoftteams/guest-experience)|

## <a name="power-bi-collaboration-options"></a>Power BI 옵션

| 공유 목표 | 관리 작업 | 방법 정보 |
|:-----|:-----|:-----|
|Power BI 게스트 사용자는 링크를 통해 공유되는 콘텐츠를 사용할 수 있습니다. 따라서 조직의 사용자가 조직 전체에 안전한 방식으로 콘텐츠를 배포할 수 있습니다.<br/> | Power BI 관리자가 사용자가 조직 내의 콘텐츠를 보게 외부 사용자를 초대할 수 있는지 여부를 제어할 수 있습니다.| [Azure AD Power BI 외부 게스트 사용자에게 콘텐츠 배포](/power-bi/service-admin-azure-ad-b2b) |

## <a name="points-to-be-aware-of-about-microsoft-365-inter-tenant-collaboration"></a>테넌트 간 공동 작업의 Microsoft 365 주의해야 하는 점

### <a name="sharing-of-user-accounts-licenses-subscriptions-and-storage"></a>사용자 계정, 라이선스, 구독 및 저장소 공유

각 조직은 자체 사용자 계정, ID, 보안 그룹, 구독, 라이선스 및 저장소를 유지 관리합니다. 사용자들은 공유 정책 및 Microsoft 365 설정과 함께 공동 작업 기능을 사용하여 회사 자산에 대한 제어를 유지하면서 필요한 정보에 대한 액세스를 제공합니다.

- **사용자 계정:** 계정은 테넌트 또는 파티션 간에 공유하거나 복제할 수 없습니다.

- **라이선스 &amp; 구독:** Microsoft 365 라이선스 계획(SKUS 또는 Microsoft 365 계획이라고도 하는 라이선스)을 통해 사용자는 해당 계획에 대해 정의된 Microsoft 365 서비스에 액세스할 수 있습니다.

- **Storage:** Microsoft 365 계획에서 SharePoint Online에 대한 소프트웨어 경계 및 제한은 사서함 저장소 제한과는 별도로 관리됩니다. 사서함 저장소 제한은 사서함 저장소 제한을 사용하여 설정 및 Exchange Online. 두 시나리오에서 저장소는 테넌트에서 공유할 수 없습니다.

### <a name="can-we-share-domain-namespaces-across-microsoft-365-tenants"></a>여러 테넌트에서 도메인 네임스페이스를 Microsoft 365 수 있나요?

아니요. 조직 도메인 이름(예: fabrikam.com 또는 tailspintoys.com)은 단일 테넌트에 연결하고 사용할 Microsoft 365 있습니다. 각 테넌트에는 자체 네임스페이스가 있어야 합니다. UPN, SMTP 및 SIP 네임스페이스는 테넌트에서 공유할 수 없습니다.

### <a name="what-about-hybrid-components-and-microsoft-365-inter-tenant-collaboration"></a>하이브리드 구성 요소 및 테넌트 Microsoft 365 어떻게 하나요?

Exchange 조직 및 Azure AD 커넥트 같은 사내 하이브리드 구성 요소는 여러 테넌트로 분할할 수 없습니다.
