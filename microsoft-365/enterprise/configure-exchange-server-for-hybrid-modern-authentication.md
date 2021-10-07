---
title: 하이브리드 최신 인증을 사용하도록 Exchange Server 온-프레미스를 구성하는 방법
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 06/16/2020
audience: ITPro
ms.topic: article
ms.service: o365-administration
ms.localizationpriority: medium
search.appverid:
- MET150
ms.assetid: cef3044d-d4cb-4586-8e82-ee97bd3b14ad
ms.collection:
- M365-security-compliance
f1.keywords:
- NOCSH
description: 보다 안전한 사용자 인증 및 권한 부여를 Exchange Server HMA(하이브리드 최신 인증)를 사용하도록 하이브리드 하이브리드 인증을 구성하는 방법을 학습합니다.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: ef3e584103906ec649df052897e5facdfabd8086
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/06/2021
ms.locfileid: "60190572"
---
# <a name="how-to-configure-exchange-server-on-premises-to-use-hybrid-modern-authentication"></a>하이브리드 최신 인증을 사용하도록 Exchange Server 온-프레미스를 구성하는 방법

*이 문서는 Microsoft 365 Enterprise와 Office 365 Enterprise에 모두 적용됩니다.*

HMA(하이브리드 최신 인증)는 보다 안전한 사용자 인증 및 권한 부여를 제공하는 ID 관리 방법으로, Exchange 하이브리드 배포에 사용할 수 있습니다.

## <a name="fyi"></a>FYI

시작하기 전에 다음을 호출합니다.

- 하이브리드 최신 인증 \> HMA

- Exchange \> EXCH

- \>Exchange Online EXO

또한 이 문서의 그래픽에 '회색으로 표시' 또는 '희미해진' 개체가 있는 경우 이는 회색으로 표시된 요소가 HMA 관련 구성에 포함되지 않음을 *나타냅니다.*

## <a name="enabling-hybrid-modern-authentication"></a>하이브리드 최신 인증 사용

HMA를 켜는 것은 다음을 의미합니다.

1. 시작하기 전에 사전 요구 사항을 충족하는지 확인

1. 대부분의 **선행** 요구는 비즈니스용 Skype 및 Exchange 모두 공통적이기 때문에 [하이브리드](hybrid-modern-auth-overview.md)최신 인증 개요 및 하이브리드 최신 인증 개요 및 비즈니스용 Skype 및 Exchange 서버와 함께 사용할 수 있습니다. 이 문서의 단계를 시작하기 전에 이 작업을 수행합니다.

1. Azure AD에서 **SPNS(서비스 사용자 이름)로** 사내 웹 서비스 URL 추가 EXCH가 여러 테넌트와 하이브리드에 있는 경우 이러한 사내 웹 서비스 URL을 EXCH와 하이브리드에 있는 모든 테넌트의 Azure AD에 SPNS로 추가해야 합니다. 

1. 모든 가상 Director가 HMA에 대해 사용하도록 설정되어 있는지 확인합니다.

1. EvoSTSAuth Server 개체 확인

1. EXCH에서 HMA를 사용하도록 설정

> [!NOTE]
> 사용자 버전의 Office MA를 지원하나요? [2013 및 Office 2016](modern-auth-for-office-2013-and-2016.md)클라이언트 앱에 대해 최신 Office 방법을 참조하세요.


## <a name="make-sure-you-meet-all-the-prerequisites"></a>모든 선행 요구 사항을 충족하는지 확인

많은 선행 요구 사항들이 비즈니스용 Skype 및 Exchange 모두 공통적이기 때문에 하이브리드 최신 인증 개요 및 하이브리드 최신 인증 개요 및 전제 요구 비즈니스용 Skype 및 Exchange [서버와](hybrid-modern-auth-overview.md)함께 사용하세요. 이  *문서의*  단계를 시작하기 전에 이 작업을 수행합니다.

> [!NOTE]
> Outlook Web App 및 Exchange 하이브리드 최신 인증에서는 작동하지 않습니다.

## <a name="add-on-premises-web-service-urls-as-spns-in-azure-ad"></a>Azure AD에서 SPNS로 사내 웹 서비스 URL 추가

Azure AD SPNS로 사내 웹 서비스 URL을 할당하는 명령을 실행합니다. SPNS는 인증 및 권한 부여 중에 클라이언트 컴퓨터 및 장치에서 사용됩니다. Azure Active Directory Azure AD(Azure AD)로의 연결에 사용할 수 있는 모든 URL은 Azure AD에 등록해야 합니다(내부 및 외부 네임스페이스 모두 포함).

먼저 AAD에 추가해야 하는 모든 URL을 수집합니다. 다음 명령을 사내에서 실행합니다.

```powershell
Get-MapiVirtualDirectory | FL server,*url*
Get-WebServicesVirtualDirectory | FL server,*url*
Get-ClientAccessServer | fl Name, AutodiscoverServiceInternalUri
Get-OABVirtualDirectory | FL server,*url*
Get-AutodiscoverVirtualDirectory | FL server,*url*
```

연결할 수 있는 URL 클라이언트가 AAD에 HTTPS 서비스 사용자 이름으로 나열되어 있는지 확인 EXCH가 여러 테넌트와 하이브리드에 있는 경우 이러한 HTTPS SPNS는 EXCH와 하이브리드에 있는 모든 테넌트의 AAD에 추가되어야 합니다. 

1. 먼저 다음 지침을 사용하여 [AAD에 연결합니다.](connect-to-microsoft-365-powershell.md)

    > [!NOTE]
    > 아래 명령을 사용하려면 커넥트 이 페이지의 _커넥트-MsolService_ 옵션을 사용해야 합니다.

2. 사용자 Exchange URL에 대해 다음 명령을 입력합니다.

   ```powershell
   Get-MsolServicePrincipal -AppPrincipalId 00000002-0000-0ff1-ce00-000000000000 | select -ExpandProperty ServicePrincipalNames
   ```

   https:// autodiscover.yourdomain.com 및 https:// mail.yourdomain.com *URL을* 포함해야 하지만 주로 000000002-0000-0ff1-ce00-000000000000/로 시작하는 SPNS로 구성되는 이 명령의 출력(및 나중에 비교를 위한 스크린샷)을 기록해 봐야 합니다.  누락된 https:// URL이 없는 경우 해당 특정 레코드를 이 목록에 추가해야 합니다.

3. 이 목록에 내부 및 외부 MAPI/HTTP, EWS, ActiveSync, OAB 및 Autodiscover 레코드가 없는 경우 아래 명령을 사용하여 레코드를 추가해야 합니다(예제 URL은 ' 및 '이지만 예제 `mail.corp.contoso.com` `owa.contoso.com` **URL은** 자체 URL로 대체).

   ```powershell
   $x= Get-MsolServicePrincipal -AppPrincipalId 00000002-0000-0ff1-ce00-000000000000
   $x.ServicePrincipalnames.Add("https://mail.corp.contoso.com/")
   $x.ServicePrincipalnames.Add("https://owa.contoso.com/")
   Set-MSOLServicePrincipal -AppPrincipalId 00000002-0000-0ff1-ce00-000000000000 -ServicePrincipalNames $x.ServicePrincipalNames
   ```

4. 2단계에서 Get-MsolServicePrincipal 명령을 다시 실행하고 출력을 확인하여 새 레코드가 추가된 것을 확인할 수 있습니다. 이전의 목록/스크린샷을 새 SPNS 목록과 비교합니다. 레코드에 대한 새 목록의 스크린샷을 찍을 수도 있습니다. 성공하면 목록에 두 개의 새 URL이 표시됩니다. 이 예제에서는 이제 SPNS 목록에 특정 URL 및 을  `https://mail.corp.contoso.com`  `https://owa.contoso.com` 포함합니다.

## <a name="verify-virtual-directories-are-properly-configured"></a>가상디렉터가 올바르게 구성되었는지 확인

이제 OAuth가 다음 명령을 Exchange 사용할 수 있는 모든 가상 Outlook 사용할 수 있는지 확인합니다.

```powershell
Get-MapiVirtualDirectory | FL server,*url*,*auth*
Get-WebServicesVirtualDirectory | FL server,*url*,*oauth*
Get-OABVirtualDirectory | FL server,*url*,*oauth*
Get-AutoDiscoverVirtualDirectory | FL server,*oauth*
```

출력을 확인하여 이러한 각 VDirs에서 **OAuth가** 사용하도록 설정되어 있는지 확인합니다. 이 경우 다음과 같은 모양이 됩니다( 그리고 중요한 것은 'OAuth'입니다.).

```powershell
Get-MapiVirtualDirectory | fl server,*url*,*auth*

Server                        : EX1
InternalUrl                   : https://mail.contoso.com/mapi
ExternalUrl                   : https://mail.contoso.com/mapi
IISAuthenticationMethods      : {Ntlm, OAuth, Negotiate}
InternalAuthenticationMethods : {Ntlm, OAuth, Negotiate}
ExternalAuthenticationMethods : {Ntlm, OAuth, Negotiate}
```

OAuth가 서버 및 네 개의 가상디렉터에서 누락된 경우 계속하기 전에 관련 명령을 사용하여 추가해야 합니다([Set-MapiVirtualDirectory,](/powershell/module/exchange/set-mapivirtualdirectory) [Set-WebServicesVirtualDirectory,](/powershell/module/exchange/set-webservicesvirtualdirectory) [Set-OABVirtualDirectory](/powershell/module/exchange/set-oabvirtualdirectory)및 [Set-AutodiscoverVirtualDirectory](/powershell/module/exchange/set-autodiscovervirtualdirectory)).

## <a name="confirm-the-evosts-auth-server-object-is-present"></a>EvoSTS Auth 서버 개체가 있는지 확인

이 마지막 명령에 대한 Exchange 관리 셸을 실행합니다. 이제 evoSTS 인증 공급자에 대한 항목이 On-프레미스에 유효한지 확인할 수 있습니다.

```powershell
Get-AuthServer | where {$_.Name -like "*EvoSts*"}
```

출력에 이름 EvoSts의 AuthServer가 표시되어 '사용' 상태가 True가 됩니다. 이 설정이 없는 경우 최신 버전의 하이브리드 구성 마법사를 다운로드하여 실행해야 합니다.

> [!NOTE]
> EXCH가 여러 테넌트와 함께 하이브리드에 있는 경우 출력에 EXCH와 하이브리드의 각 테넌트에 대한 Name EvoSts - {GUID}의 AuthServer가 하나 표시되어야 합니다. 이러한 모든 AuthServer 개체에 대해 'Enabled' 상태가 True가 됩니다. 

 **중요** 환경에서 Exchange 2010을 실행하는 경우 EvoSTS 인증 공급자가 만들어지지 않습니다.

## <a name="enable-hma"></a>HMA 사용

Exchange 관리 셸에서 다음 명령을 실행합니다.

```powershell
Set-AuthServer -Identity EvoSTS -IsDefaultAuthorizationEndpoint $true
Set-OrganizationConfig -OAuth2ClientProfileEnabled $true
```

EXCH 버전이 Exchange 2016(CU18 이상) 또는 Exchange 2019(CU7 이상)이고 하이브리드가 2020년 9월 이후에 다운로드된 HCW로 구성된 경우 Exchange 관리 셸, 사내에서 다음 명령을 실행합니다.

```powershell
Set-AuthServer -Identity "EvoSTS - {GUID}" -DomainName "Tenant Domain" -IsDefaultAuthorizationEndpoint $true
Set-OrganizationConfig -OAuth2ClientProfileEnabled $true
```

> [!NOTE]
> EXCH가 여러 테넌트와 하이브리드에 있는 경우 각 테넌트에 해당하는 도메인을 사용하여 EXCH에 여러 AuthServer 개체가 있습니다.   이러한 AuthServer 개체 중 하나에 대해 **IsDefaultAuthorizationEndpoint** 플래그를 **true(IsDefaultAuthorizationEndpoint** cmdlet 사용)로 설정해야 합니다. 모든 Authserver 개체에 대해 이 플래그를 true로 설정할 수 없습니다. 이러한 AuthServer 개체의 **IsDefaultAuthorizationEndpoint** 플래그 중 하나를 true로 설정한 경우에도 HMA가 사용하도록 설정됩니다.

## <a name="verify"></a>확인

HMA를 사용하도록 설정하면 클라이언트의 다음 로그인에서 새 인증 흐름을 사용하게 됩니다. HMA를 켜면 클라이언트에 대한 재인식이 트리거되지 않을 수 있으며, 새 설정을 Exchange 시간이 걸릴 수 있습니다.

또한 Outlook 클라이언트(Windows 알림 트레이에서도)의 아이콘을 마우스 오른쪽 단추로 클릭하고 '연결 상태'를 클릭하는 동시에 Ctrl 키를 눌러야 합니다. OAuth에 사용되는 bearer 토큰을 나타내는 'Bearer'의 'Authn' 유형에 대해 클라이언트의 SMTP 주소를 \* 찾아야 합니다.

> [!NOTE]
> HMA를 비즈니스용 Skype 구성해야 하나요? 지원되는 토폴로지 목록과 [](/skypeforbusiness/plan-your-deployment/modern-authentication/topologies-supported)구성 방법을 보여 주는 문서 2개가 [필요합니다.](configure-skype-for-business-for-hybrid-modern-authentication.md)


## <a name="using-hybrid-modern-authentication-with-outlook-for-ios-and-android"></a>Android 및 iOS용 Outlook에서 하이브리드 최신 인증 사용

TCP 443에서 Exchange 서버를 사용하는 사내 고객의 경우 다음 IP 주소 범위에 대한 트래픽 처리를 무시합니다.

```text
52.125.128.0/20
52.127.96.0/23
```

iOS 및 Android용 Outlook 앱은 모바일 장치에서 Microsoft 365 Office 365 앱을 사용하여 일상 생활과 작업을 찾고, 계획하고Microsoft 서비스 우선 순위를 지정하는 데 가장 적합한 방법으로 디자인됩니다. 자세한 내용은 iOS 및 Android용 하이브리드 최신 인증을 Outlook [참조하세요.](/exchange/clients/outlook-for-ios-and-android/use-hybrid-modern-auth)

## <a name="related-topics"></a>관련 항목

[전용/ITAR에서 vNext로의 Office 365 대한 최신 인증 구성 요구 사항](/exchange/troubleshoot/modern-authentication/modern-authentication-configuration)
