---
title: Microsoft Cloud 독일의 마이그레이션에 대 한 추가 일반 정보
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
description: '요약: Microsoft cloud 전라남도 (Microsoft 클라우드 독일)에서 새 독일어 데이터 센터 지역의 Office 365 서비스로 이동할 때의 추가 일반 정보를 서비스에 대해 설명 합니다.'
ms.openlocfilehash: 93692200f2519dbc647bb4e81b4bd8c646815858
ms.sourcegitcommit: c1dd5be42fe0c5dcc7c05817c941edd9076febf8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/02/2020
ms.locfileid: "49558433"
---
# <a name="additional-general-information-for-the-migration-from-microsoft-cloud-deutschland"></a>Microsoft Cloud 독일의 마이그레이션에 대 한 추가 일반 정보

다음 섹션에서는 서비스, 사전 작업 고려 사항 및 고객 환경에 대 한 추가 정보를 제공 합니다.

## <a name="azure-active-directory"></a>Azure Active Directory

Azure 독일어 클라우드에서 Azure 공개 클라우드로의 이동을 완료 하려면 응용 프로그램에 대 한 인증 끝점, Azure Active Directory (Azure AD) 그래프 및 MS Graph 끝점이 OpenID Connect (OIDC) 끝점을 사용할 때 상업용 클라우드의 사용자에 게 업데이트 되 고 상업용 클라우드 끝점에 대 한 보고를 시작 하는 것이 좋습니다 `https://login.microsoftonline.com/\<TenantIdOrDomain\>/.well-known/openid-configuration` . 
 
**이 변경 작업을 수행 해야 하는 경우**

테 넌 트가 독일어 클라우드에서 상업용 클라우드로의 마이그레이션을 완료 하면 Azure/Office 포털에서 알림이 수신 됩니다. 이 알림을 받은 후 30 일이 지나면 앱이 Azure 독일 클라우드에서 Azure 공용 클라우드로 마이그레이션되는 테 넌 트에 대해 계속 작동 하도록 할 수 있습니다.
 
로그인 기관을 업데이트 하는 세 가지 사전 조건은 다음과 같습니다.

 - 테 넌 트에 대 한 OIDC 검색 끝점이 `https://login.microsoftonline.com/\<TenantIdOrDomain\>/.well-known/openid-configuration` AZURE AD 공용 클라우드 끝점을 반환 합니다.

 - 테 넌 트가 페더레이션에 대해 설정 된 경우 AD FS (Active Directory Federation Services)가 Azure AD 공개와 동기화 되도록 업데이트 됩니다. 이 변경 작업을 수행 하기 위해 Azure AD Connect 설정을 업데이트 하는 지침을 따를 수 있습니다.

 - 응용 프로그램에서 사용 하는 리소스 응용 프로그램은 Azure AD 전라남도 및 Azure AD Public에서 모두 서명 된 토큰을 수락 하도록 수정 됩니다.
 
**응용 프로그램의 종류**

응용 프로그램은 다음 중 하나일 수 있습니다.

- [SPA (단일 페이지 응용 프로그램)](https://docs.microsoft.com/azure/active-directory/develop/scenario-spa-overview)
- [사용자에 게 로그인 하는 웹 앱](https://docs.microsoft.com/azure/active-directory/develop/scenario-web-app-sign-user-overview)
- [웹 Api를 호출 하는 웹 앱](https://docs.microsoft.com/azure/active-directory/develop/scenario-web-app-call-api-overview)
- [Protected web API](https://docs.microsoft.com/azure/active-directory/develop/scenario-protected-web-api-overview)
- [웹 Api를 호출 하는 웹 API](https://docs.microsoft.com/azure/active-directory/develop/scenario-web-api-call-api-overview)
- [데스크톱 앱](https://docs.microsoft.com/azure/active-directory/develop/scenario-desktop-overview)
- [데몬 앱](https://docs.microsoft.com/azure/active-directory/develop/scenario-daemon-overview)
- [모바일 앱](https://docs.microsoft.com/azure/active-directory/develop/scenario-mobile-overview)
 
> [!NOTE] 
> 응용 프로그램이 사용 권한으로 전환 되 면 `login.microsoftonline.com` 토큰이이 새로운 기관에 의해 서명 됩니다. 다른 앱에서 호출 하는 리소스 응용 프로그램을 호스트 하는 경우에는 느슨한 토큰 유효성 검사를 허용 해야 합니다. 즉, 앱이 Azure AD 전라남도 및 Azure AD 공용 클라우드에서 서명 된 토큰을 허용 해야 합니다. 이 느슨한 토큰 유효성 검사는 서비스를 호출 하는 모든 클라이언트 응용 프로그램이 Azure AD 공용 클라우드로 완전히 마이그레이션될 때까지 필요 합니다. 마이그레이션 후에는 리소스 응용 프로그램에서 Azure AD 공용 클라우드로 서명 된 토큰만 허용 하기만 하면 됩니다.

**업데이트 해야 할 사항**

1. Azure 독일 또는 Office 365 독일 사용자를 인증 하는 데 사용 되는 응용 프로그램을 Azure 전라남도에서 호스트 하는 경우 `https://login.microsoftonline.com` 인증 컨텍스트에서 기관으로 사용 되는지 확인 합니다.

    - Azure AD 인증 컨텍스트를 참조 하세요.
    - 이는 응용 프로그램에 대 한 인증과 응용 프로그램에서 호출 될 수 있는 Api에 대 한 인증 (즉, Microsoft Graph, Azure AD Graph, Azure Resource Manager)에 모두 적용 됩니다.

2. Azure AD Graph 끝점을로 업데이트 `https://graph.windows.net` 합니다.

3. MS Graph 끝점을로 업데이트 `https://graph.microsoft.com` 합니다.

4. 응용 프로그램에서 사용 하는 독일어 클라우드 끝점 (예: Exchange Online 및 SharePoint Online)을 공용 클라우드의 사용자에 게 업데이트 합니다.

5. `AzurePublic` `AzureGermany` 다음에 대 한 관리 도구 및 스크립트에서 환경 매개 변수를 다음으로 업데이트 (대신) 합니다.

    - [Azure PowerShell](https://docs.microsoft.com/powershell/azure/install-az-ps?view=azps-2.8.0&viewFallbackFrom=azurermps-5.6.0)
    - [Azure AD PowerShell (MSOnline)](https://docs.microsoft.com/powershell/azure/active-directory/overview?view=azureadps-1.0)
    - [Azure AD PowerShell (AzureAD)](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2?view=azureadps-2.0)
    - [Azure CLI](https://docs.microsoft.com/cli/azure/install-azure-cli?view=azure-cli-latest)
 
**게시 하는 응용 프로그램**

테 넌 트 외부에 있는 사용자가 사용할 수 있는 응용 프로그램을 게시 하는 경우 연속성을 보장 하기 위해 응용 프로그램 등록을 변경 해야 할 수 있습니다. 사용자의 응용 프로그램을 사용 하는 다른 테 넌 트는 다른 시간에 테 넌 트에서 이동할 수 있습니다. 응용 프로그램에 대 한 액세스 권한을 잃지 않으려면 azure 독일에서 Azure 공개로 동기화 되는 앱에 동의 해야 합니다.

### <a name="additional-considerations"></a>추가 고려 사항

Azure AD에 대 한 몇 가지 추가 고려 사항은 다음과 같습니다.

- 페더레이션 인증의 경우:

  - 테 넌 트 전환이 진행 중인 동안에는 페더레이션 도메인을 생성, 승격 또는 강등 하면 안 됩니다. Azure AD 서비스에 대 한 마이그레이션이 완료 되 면 (테 넌 트가 완전히 완료 됨) 페더레이션 도메인 관리를 다시 시작할 수 있습니다.

  - AD FS (Active Directory Federation Services)와 함께 페더레이션 인증을 사용 하는 경우 마이그레이션 중에 온-프레미스 AD DS (Active Directory 도메인 서비스)를 사용 하 여 모든 인증에 사용 되는 발급자 Uri를 변경 하지 않아야 합니다. 발급자 Uri를 변경 하면 도메인의 사용자에 대 한 인증 오류가 발생 합니다. 발급자 Uri는 AD FS에서 직접 변경 하거나 도메인을 관리에서 페더레이션으로 변환 하 고 그 반대의 경우에만 변경할 수 있습니다. 마이그레이션 중인 Azure AD 테 넌 트에서 페더레이션 도메인을 추가, 제거 또는 변환 하지 않는 고객을 위해 Microsoft에서 권장 합니다. 발급자 Uri는 마이그레이션이 완전히 완료 된 후 변경 될 수 있습니다.

- 네트워킹:

  - Azure portal에서는 IPv6 이름이 지정 된 네트워크를 만들 때 작동 하지 않습니다 `http://portal.microsoftazure.de/` . Azure portal을 사용 `https://portal.azure.com` 하 여 IPv6로 명명 된 네트워크를 만듭니다.
 
   - Microsoft Cloud 독일 portal에서 Azure MFA (Multi-factor Authentication) 서비스 설정에 대해 신뢰할 수 있는 IP 주소 범위를 만들 수 없습니다. Office 365 서비스에 대 한 Azure AD portal을 사용 하 여 Azure MFA 신뢰할 수 있는 IP 주소 범위를 만듭니다.


- 조건부 액세스의 경우: 

  - 다음 권한 부여 컨트롤이 포함 된 조건부 액세스 정책은 Office 365 서비스에 대 한 마이그레이션이 완료 된 후 ( [AZURE AD](ms-cloud-germany-transition.md#how-is-the-migration-organized) 마이그레이션 단계 완료 후) 지원 되지 않습니다.

    - 준수 장치 필요
    - 승인 된 앱 필요
    - 앱 보호 정책 필요
    
  - 조건부 액세스 정책 인터페이스는 사용 하지 않도록 설정 되어 있는 테 넌 트에 대 한 보안 기본값을 사용 하 고 테 넌 트에 조건부 액세스 정책이 이미 있는 경우이에 대 한 거짓 경고를 제공 합니다. 이 경고를 무시 하거나 Office 365 서비스 포털을 사용 하 여 조건부 액세스 정책을 관리 해야 합니다. 

- Intune 시나리오는 모든 office 작업을 마이그레이션하는 것을 포함 하 여 테 넌 트 마이그레이션이 완료 된 후 전 세계 끝점에 대해서만 지원 됩니다.

- Microsoft Cloud 독일 MFA 요청에 대해 모바일 앱 알림 방법을 사용 하는 사용자는 Microsoft Authenticator 앱에서 UPN (사용자 계정 이름) 대신 사용자의 ObjectId (GUID)를 참조 하세요. Azure AD 테 넌 트 마이그레이션이 완료 되 고 Office 365 서비스에서 호스트 되 면 새 Microsoft 인증자 정품 인증을 통해 사용자의 Upn이 표시 됩니다. 기존 Microsoft 인증자 계정에는 사용자 ObjectId가 계속 표시 되지만 모바일 앱 알림에 대해서는 계속 작동 합니다. 

- 2019 년 10 월 22 일 이후에 만든 테 넌 트의 경우 Office 365 서비스로 마이그레이션될 때 테 넌 트에서 자동으로 보안 기본값을 사용할 수 있습니다. 테 넌 트 관리자는 보안 기본값을 사용 하도록 설정 하 고 MFA에 등록 하도록 선택 하거나, 기능을 사용 하지 않도록 설정할 수 있습니다. 자세한 내용은 [보안 기본값 비활성화](https://docs.microsoft.com/azure/active-directory/fundamentals/concept-fundamentals-security-defaults#disabling-security-defaults)를 참조 하세요. 

  > [!NOTE]
  > Office 365 서비스에서 보안 기본값을 사용 하도록 설정 하는 기능이 롤아웃 되므로 마이그레이션 중에 자동으로 사용 하도록 설정 되지 않은 조직은 계속 자동으로 등록할 수 있습니다. 보안 기본값을 명시적으로 사용 하지 않도록 설정 하거나 사용 하도록 선택 하는 관리자는 **Azure Active Directory > 속성** 에서 기능을 업데이트 하 여이 작업을 수행할 수 있습니다. 관리자가 기능을 명시적으로 사용 하도록 설정한 후에는 자동으로 사용 하도록 설정 되지 않습니다.

- 테 넌 트가 마이그레이션의 경우 office 365 포털 및 office 365 독일 포털의 Azure AD Connect 버전에 대 한 경고가 표시 됩니다. 마이그레이션 완료 후 버전 경고에 경고가 표시 되지 않으면이를 무시할 수 있습니다. 마이그레이션 전후에 경고가 발생 하는 경우에는 각 포털에서 Azure AD Connect를 업데이트 해야 합니다. "이전 디렉터리 동기화 도구를 사용 하 고 있습니다." 라는 경고 메시지가 표시 되었습니다. Microsoft 다운로드 센터로 이동 하 여 최신 버전의 Azure AD Connect를 다운로드 하는 것이 좋습니다.

## <a name="exchange-online"></a>Exchange Online 

- `myaccount.msft.com` 는 Office 365에서 사용 하는 경우에만 작동 합니다. 링크를 통해 해당 시간까지 "문제가 발생 했습니다." 라는 오류 메시지가 표시 됩니다.

- 다른 환경에서 공유 사서함에 액세스 하는 Outlook Web App 사용자 (예: 전역 환경의 공유 사서함에 액세스할 수 있는 사용자)는 두 번째 시간을 인증 하 라는 메시지가 표시 됩니다. 사용자는에서 먼저 사서함을 인증 하 고 액세스 한 `outlook.office.de` 다음에 있는 공유 사서함을 열어야 합니다 `outlook.office365.com` . 다른 서비스에서 호스팅되는 공유 리소스에 액세스할 때 두 번째로 인증을 받아야 합니다.

- 기존 Microsoft Cloud 독일 고객 또는 전환 중인 경우 **파일 > 정보 > 계정 추가** 를 사용 하 여 Outlook에 공유 사서함을 추가 하는 경우 outlook 클라이언트에서 Rest API를 사용 하려고 할 수 있습니다 `https://outlook.office.de/api/v2.0/Me/Calendars` . 일정 권한을 보기 위해 계정을 추가 하려는 고객은 [Outlook에서 일정 공유에 대 한 사용자 환경 변경](https://support.microsoft.com/office/user-experience-changes-for-sharing-a-calendar-in-outlook-5978620a-fe6c-422a-93b2-8f80e488fdec) 에 설명 된 대로 레지스트리 키를 추가 하 여이 작업을 수행 해야 합니다. 이 레지스트리 키는 그룹 정책을 사용 하 여 조직 전체에 배포할 수 있습니다.

- 마이그레이션 단계에서는 PowerShell cmdlet **new-migrationendpoint**, **new-migrationendpoint** 및 **MigrationsServerAvailability** 를 사용 하 여 오류가 발생할 수 있습니다 (프록시의 오류). 중재 사서함이 전 세계적으로 마이그레이션 되었지만 관리자 사서함은 그렇지 않거나 그 반대 이기 때문에이 작업이 수행 됩니다. 이 문제를 해결 하려면 테 넌 트 PowerShell 세션을 만드는 동안 중재 사서함을 **Connectionuri** 의 라우팅 힌트로 사용 합니다. 예: `New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri "https://outlook.office365.com/powershell-liveid?email=Migration.8f3e7716-2011-43e4-96b1-aba62d229136@TENANT.onmicrosoft.de" -Credential $UserCredential -Authentication Basic -AllowRedirection`

- Exchange Online hybrid을 사용 하는 경우:

    - HCW (하이브리드 구성 마법사)를 다시 실행 하 여 전환 전에 Microsoft 클라우드 독일에 대 한 온-프레미스 구성을 업데이트 한 다음 Office 365 서비스에 대해 정리 시에 HCW를 다시 실행 해야 합니다. 사용자 지정 도메인을 사용 하는 경우 추가 DNS 업데이트가 필요할 수도 있습니다.

이 작업의 마이그레이션 단계 중에 필요한 작업 또는 관리 또는 사용에 대 한 영향에 대 한 자세한 내용은 [마이그레이션 단계의 작업 및 영향](ms-cloud-germany-transition-phases.md#exchange-online)에 대 한 Exchange Online 섹션을 참조 하십시오.

## <a name="office-services"></a>Office 서비스

Office에서 가장 최근에 사용 된 (MRU) 서비스는 마이그레이션이 아닌 독일 서비스에서 Office 365 서비스로 시작 됩니다. Office.com 포털에서 마이그레이션한 후에는 Office 365 서비스 쪽의 MRU 링크만 표시 됩니다. 독일 서비스의 MRU 링크는 Office 365 서비스에서 MRU 링크로 표시 되지 않습니다. Office 365에서는 테 넌 트 마이그레이션이 완료 된 후에만 MRU 링크에 액세스할 수 있습니다.

## <a name="sharepoint-online-and-onedrive"></a>SharePoint Online 및 OneDrive

- SharePoint Online 마이그레이션이 완료 되면 데이터 인덱스가 다시 작성 됩니다. 검색 인덱스에 종속 되는 기능은 다시 인덱스를 완료 하는 동안 영향을 받을 수 있습니다.

- 조직에서 여전히 SharePoint 2010 워크플로를 사용 하는 경우에는 2021 보다 12 월 31 일 이후에는 더 이상 작동 하지 않습니다. SharePoint 2013 워크플로는 새 테 넌 트에 대해 기본적으로 설정 되어 있지만 11 월 1 2020 일에 시작 되는 경우에도 계속 지원 됩니다. SharePoint Online 서비스에 대 한 마이그레이션이 완료 되 면 전원 자동화 또는 기타 지원 되는 솔루션으로 이동 하는 것이 좋습니다.

- OneDrive를 독일어로 마이그레이션한 후 데이터 인덱스를 다시 작성 합니다. 검색 인덱스에 종속 되는 기능은 다시 인덱스를 처리 하는 동안 영향을 받을 수 있습니다.


## <a name="more-information"></a>추가 정보

시작 하기:

- [Microsoft Cloud 독일에서 새 독일어 데이터 센터 지역의 Office 365 서비스로 마이그레이션](ms-cloud-germany-transition.md)
- [Microsoft Cloud Deutschland 마이그레이션 지원](https://aka.ms/germanymigrateassist)
- [마이그레이션에 대해 옵트인하는 방법](ms-cloud-germany-migration-opt-in.md)
- [마이그레이션 중의 고객 환경](ms-cloud-germany-transition-experience.md)

전환을 통해 이동 하는 경우:

- [문장 작업 및 영향 마이그레이션](ms-cloud-germany-transition-phases.md)
- [추가 사전 작업](ms-cloud-germany-transition-add-pre-work.md)
- [서비스](ms-cloud-germany-transition-add-general.md), [장치](ms-cloud-germany-transition-add-devices.md), [환경](ms-cloud-germany-transition-add-experience.md)및 [AD FS](ms-cloud-germany-transition-add-adfs.md)에 대 한 추가 정보

클라우드 앱:

- [Dynamics 365 마이그레이션 프로그램 정보](https://aka.ms/d365ceoptin)
- [Power BI 마이그레이션 프로그램 정보](https://aka.ms/pbioptin)
- [Microsoft Teams 업그레이드 시작하기](https://aka.ms/SkypeToTeams-Home)
