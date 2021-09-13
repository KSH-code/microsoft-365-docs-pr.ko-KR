---
title: 도이치클라드에서 마이그레이션하기 위한 추가 Azure Active Directory 정보
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
description: '요약: 독일 Microsoft Azure Active Directory(Microsoft 클라우드)에서 새 독일 데이터 센터 지역의 Office 365 서비스로 이동하는 경우의 추가 정보입니다.'
ms.openlocfilehash: 88a151b61a93b4b65e16bbd100a126d44282e513
ms.sourcegitcommit: d08fe0282be75483608e96df4e6986d346e97180
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/12/2021
ms.locfileid: "59191229"
---
# <a name="additional-azure-active-directory-information-for-the-migration-from-microsoft-cloud-deutschland"></a>도이치클라드에서 마이그레이션하기 위한 추가 Azure Active Directory 정보

Azure German 클라우드에서 Azure 공용 클라우드로의 이동을 완료하기 위해 OIDC(OpenID 커넥트) 끝점에서 상업용 클라우드 끝점 보고를 시작할 때 응용 프로그램의 인증 끝점, Azure Active Directory(Azure AD) Graph 및 MS Graph 끝점을 상업용 클라우드의 끝점으로 업데이트하는 것이 `https://login.microsoftonline.com/<TenantIdOrDomain>/.well-known/openid-configuration` 좋습니다. 
 
**언제 변경해야 하나요?**

테넌트가 독일 클라우드에서 상업용 클라우드로의 마이그레이션을 완료하면 Azure/Office 포털에서 알림을 받게 됩니다. 이 알림을 받은 후 30일이 지난 후 이러한 업데이트를 완료하면 앱이 Azure Germany 클라우드에서 Azure Public 클라우드로 마이그레이션된 테넌트에 대해 계속 작동할 수 있습니다.
 
로그인 기관을 업데이트하는 데는 세 가지 사전이 있습니다.

 - 테넌트의 OIDC 검색 `https://login.microsoftonline.com/<TenantIdOrDomain>/.well-known/openid-configuration` 끝점은 Azure AD 공용 클라우드 끝점을 반환합니다.

 - 테넌트가 페더넌트에 대해 설정된 경우 AD FS(Active Directory Federation Services)가 Azure AD Public과 동기화될 수 있도록 업데이트됩니다. 이 변경에 대한 Azure AD 커넥트 지침에 따라 업데이트할 수 있습니다.

 - 응용 프로그램에서 사용하는 리소스 응용 프로그램은 Azure AD Germany와 Azure AD Public 둘 다에서 서명된 토큰을 수락하기 위해 수정됩니다.
 
**응용 프로그램 종류**

응용 프로그램은 다음 중 한 개일 수 있습니다.

- [SPA(단일 페이지 앱)](/azure/active-directory/develop/scenario-spa-overview)
- [사용자에게 로그인하는 웹앱](/azure/active-directory/develop/scenario-web-app-sign-user-overview)
- [웹 API를 호출하는 웹 앱](/azure/active-directory/develop/scenario-web-app-call-api-overview)
- [보호된 웹 API](/azure/active-directory/develop/scenario-protected-web-api-overview)
- [웹 API를 호출하는 웹 API](/azure/active-directory/develop/scenario-web-api-call-api-overview)
- [데스크톱 앱](/azure/active-directory/develop/scenario-desktop-overview)
- [데몬 앱](/azure/active-directory/develop/scenario-daemon-overview)
- [모바일 앱](/azure/active-directory/develop/scenario-mobile-overview)
 
> [!NOTE] 
> 응용 프로그램이 권한으로 사용으로 전환하면 이 새 기관에서 토큰에 `login.microsoftonline.com` 서명합니다. 다른 앱이 호출하는 리소스 응용 프로그램을 호스팅하는 경우 래시 토큰 유효성 검사를 허용해야 합니다. 즉, 앱이 Azure AD Germany 및 Azure AD 공용 클라우드에서 서명된 토큰을 허용해야 합니다. 서비스를 호출하는 모든 클라이언트 응용 프로그램이 Azure AD 공용 클라우드로 완전히 마이그레이션될 때까지 이 lax 토큰 유효성 검사가 필요합니다. 마이그레이션 후 리소스 응용 프로그램은 Azure AD 공용 클라우드에서 서명된 토큰만 수락하면 됩니다.

**업데이트해야 하는 것**

1. Azure Germany 또는 Office 365 Germany 사용자를 인증하는 데 사용되는 응용 프로그램을 Azure Germany에서 호스팅하는 경우 인증 컨텍스트에서 기관으로 `https://login.microsoftonline.com` 사용되는지 확인

    - Azure AD 인증 컨텍스트를 참조하세요.
    - 이는 응용 프로그램에 대한 인증뿐만 아니라 응용 프로그램이 호출할 수 있는 API에 대한 인증(즉, Microsoft Graph, Azure AD Graph, Azure Resource Manager)에 적용됩니다.

2. Azure AD Graph 끝점을 로 `https://graph.windows.net` 업데이트합니다.

3. Microsoft Graph 끝점을 로 `https://graph.microsoft.com` 업데이트합니다.

4. 응용 프로그램이 공용 클라우드로 사용하는 독일 클라우드 끝점(예: Exchange Online SharePoint Online용 끝점)을 업데이트합니다.

5. 다음에 대한 관리 도구 및 스크립트에서 (대신) 환경 매개 `AzurePublic` `AzureGermany` 변수를 업데이트합니다.

    - [Azure PowerShell](/powershell/azure/install-az-ps)
    - [Azure AD PowerShell(MSOnline)](/powershell/azure/active-directory/overview)
    - [Azure AD PowerShell(AzureAD)](/powershell/azure/active-directory/install-adv2)
    - [Azure CLI](/cli/azure/install-azure-cli)
 
**게시하는 응용 프로그램은 어떻게 하나요?**

테넌트 외부에 있는 사용자가 사용할 수 있는 응용 프로그램을 게시하는 경우 연속성을 보장하기 위해 응용 프로그램 등록을 변경해야 할 수 있습니다. 응용 프로그램을 사용하는 다른 테넌트는 테넌트와 다른 시간으로 이동할 수 있습니다. 응용 프로그램에 대한 액세스 권한을 잃지 않도록 보장하려면 Azure Germany에서 Azure Public으로 동기화되는 앱에 동의해야 합니다.

**마이그레이션 중 새 다중 테넌트 응용 프로그램을 추가하는 경우**

다른 조직(다중 테넌트 응용 프로그램)에서 게시하는 새 응용 프로그램을 사용하려는 경우 마이그레이션 프로세스(2~9단계)에서 해당 응용 프로그램을 추가하지는 제한됩니다.  조직이 9단계를 완료하고 Azure 공용 인스턴스로 완전히 전환될 때 이 작업을 실행할 수 있습니다.

## <a name="additional-considerations"></a>추가 고려 사항

다음은 Azure AD에 대한 몇 가지 추가 고려 사항입니다.

- 페더타 인증의 경우:

  - 테넌트 전환이 진행되는 동안에는 페더넌트 도메인을 만들거나 승격하거나 강락하면 안 됩니다. Azure AD 서비스로의 마이그레이션이 완료된 후(테넌트가 완전히 완료된 경우) 페더링된 도메인 관리를 다시 시작할 수 있습니다.

  - AD FS(Active Directory Federation Services)에서 페더전된 인증을 사용하는 경우 마이그레이션 중에는 모든 인증에 사용되는 발급자 URIS를 변경하지 말아야 합니다. 발급자 URIS를 변경하면 도메인의 사용자에 대한 인증 오류가 발생합니다. 발급자 URIS는 AD FS에서 직접 변경할 수 있으며 도메인이 관리에서 페더러티로 변환되거나 그 반대의 경우도 마찬가지입니다. 고객이 마이그레이션되는 Azure AD 테넌트에서 페더넌트 도메인을 추가, 제거 또는 변환하지 않는 것이 좋습니다. 발급자 URIS는 마이그레이션이 완전히 완료된 후 변경할 수 있습니다.

- 네트워킹의 경우:

  - Azure Portal에서 IPv6으로 명명된 네트워크를 만들 수 `http://portal.microsoftazure.de/` 없습니다. 에서 Azure Portal을 `https://portal.azure.com` 사용하여 IPv6으로 명명된 네트워크를 만들 수 있습니다.
 
   - 도이치랜드 Microsoft 클라우드 포털에서 Azure MFA(다단계 인증) 서비스 설정에 대한 신뢰할 수 있는 IP 주소 범위를 만들 수 없습니다. 서비스용 Azure AD 포털을 Office 365 Azure MFA 신뢰할 수 있는 IP 주소 범위를 만들 수 있습니다.


- 조건부 액세스의 경우: 

  - 다음 부여 컨트롤이 있는 조건부 액세스 정책은 Office 365 서비스로의 마이그레이션이 완료될 때까지(Azure AD 마이그레이션 완료 단계 후) [지원되지](ms-cloud-germany-transition.md#how-is-the-migration-organized) 않습니다.

    - 규격 장치 필요
    - 승인된 앱 필요
    - 앱 보호 정책 필요
    
  - 조건부 액세스 정책 인터페이스는 사용하지 않도록 설정된 경우에도 테넌트에 대해 사용하도록 설정되는 보안 기본값에 대한 거짓 경고를 표시하며, 테넌트에 대해 조건부 액세스 정책이 이미 있습니다. 경고를 무시하거나 Office 365 서비스 포털을 사용하여 조건부 액세스 정책을 관리해야 합니다. 

- Intune 시나리오는 모든 Office 작업 마이그레이션을 포함하여 테넌트 마이그레이션이 완료된 후 전 세계 끝점에 대해 지원됩니다.

- MFA 요청에 모바일 앱 알림 메서드를 사용하는 Microsoft 클라우드 도이클란드 사용자는 Microsoft Authenticator 앱의 UPN(사용자 계정 이름) 대신 사용자의 ObjectId(GUID)를 볼 수 있습니다. Azure AD 테넌트의 마이그레이션이 완료되어 Office 365 서비스에서 호스팅된 후 새로운 Microsoft Authenticator 정품 인증에 사용자의 UPNS가 표시됩니다. 기존 Microsoft Authenticator 계정은 사용자 ObjectId를 계속 표시하지만 모바일 앱 알림에도 계속 사용할 수 있습니다. 

- 2019년 10월 22일 이후에 만들어진 테넌트의 경우 테넌트가 Office 365 서비스로 마이그레이션될 때 테넌트에 대해 보안 기본값이 자동으로 활성화될 수 있습니다. 테넌트 관리자는 보안 기본값을 사용하도록 설정하고 MFA에 등록할 수 있습니다. 또는 이 기능을 사용하지 않도록 설정할 수 있습니다. 자세한 내용은 [Disabling security defaults을 참조하십시오.](/azure/active-directory/fundamentals/concept-fundamentals-security-defaults#disabling-security-defaults) 

  > [!NOTE]
  > 마이그레이션 중에 자동 사용되지 않는 조직은 보안 기본값을 사용하도록 설정하는 기능이 Office 365 서비스에서 롤아웃될 수 있습니다. 보안 기본값을 명시적으로 사용하지 않도록 설정하거나 사용하도록 선택한 관리자는 속성 에서 기능을 업데이트하여 Azure Active Directory > **있습니다.** 관리자가 이 기능을 명시적으로 사용하도록 설정한 후 자동 사용이 가능하지 않습니다.

- 테넌트가 마이그레이션 중이면 Office 365 독일 포털과 Office 365 포털에서 Azure AD ad 커넥트 버전에 대한 경고가 표시됩니다. 마이그레이션이 완료된 후 버전 경고가 더 이상 경고를 표시하지 않는 경우 무시할 수 있습니다. 마이그레이션 전이나 후에 경고가 표시될 경우 두 포털에서 Azure AD 커넥트 업데이트해야 합니다. 경고 메시지는 다음을 나타냅니다. "디렉터리 동기화 도구가 사용 중입니다. Microsoft 다운로드 센터로 이동하여 최신 버전의 Azure AD 2013을 다운로드하는 커넥트."

## <a name="more-information"></a>추가 정보

시작:

- [독일 Microsoft 클라우드에서 새 독일 Office 365 서비스로 마이그레이션](ms-cloud-germany-transition.md)
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
