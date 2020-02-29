---
title: Office 365 사용자에 대해 다단계 인증 설정
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: sirkkuw
manager: mnirkhe
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
search.appverid:
- BCS160
- MET150
- MOE150
- BEA160
- GEA150
ms.assetid: 8f0454b2-f51a-4d9c-bcde-2c48e41621c6
description: 보안 기본값을 사용하여 Office 365 사용자의 다단계 인증을 설정하는 방법을 알아봅니다.
monikerRange: o365-worldwide
ms.openlocfilehash: cb2205e5f5b7df4f6e7d8f7263a91fb2f0f4d3e2
ms.sourcegitcommit: cf07dfccec476ac2526a6171ec6b6365686f759f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/29/2020
ms.locfileid: "42341252"
---
# <a name="set-up-multi-factor-authentication"></a>다단계 인증 설정
  
모든 새 비즈니스용 Office 365 또는 Microsoft 365 Business 구독에는 자동으로 보안 기본값이 설정됩니다. 즉, 모든 사용자는 MFA(다단계 인증)를 설정하고 모바일 장치에 인증자 앱을 설치해야 합니다. 자세한 내용은 [Office 365에 대해 2단계 인증 설정](https://support.office.com/article/ace1d096-61e5-449b-a875-58eb3d74de14)을 참조하세요.  

다음 9개의 관리자 역할은 로그인할 때마다 추가 인증을 수행해야 합니다.
- 전역 관리자
- SharePoint 관리자
- Exchange 관리자
- 조건부 액세스 관리자
- 보안 관리자
- 헬프데스크 관리자 또는 암호 관리자
- 청구 관리자
- 사용자 관리자
- 인증 관리자

필요한 경우 다른 모든 사용자들은 추가 인증을 수행하라는 요청을 받습니다. 자세한 내용은 [보안 기본값이란?](https://docs.microsoft.com/azure/active-directory/fundamentals/concept-fundamentals-security-defaults)을 참조하세요.

> [!NOTE]
> 다단계 인증을 설정하거나 수정하려면 Office 365 전역 관리자이어야 합니다. <br><br>
> 새로운 Microsoft 365 관리 센터를 사용하지 않는 경우 홈페이지 상단에 있는 **새 관리 센터 시도** 토글을 선택하여 켤 수 있습니다.

이전에 기본 정책을 사용 하여 MFA를 설정한 경우 [ 이를 해제하고 보안 기본값](#move-from-baseline-policies-to-security-defaults)을 설정해야 합니다. 그러나 Microsoft 365 Business 또는 구독에 [Azure Active Directory Premium 1 또는 Azure Active Directory Premium 2](https://azure.microsoft.com/pricing/details/active-directory/)가 포함되어 있는 경우에도 [조건부 액세스](https://docs.microsoft.com/azure/active-directory/conditional-access/overview) 정책을 설정할 수 있습니다. 조건부 액세스 정책을 사용하려면 [최신 인증이 사용 ](#enable-multi-factor-authentication-for-your-organization)되고 있는지 확인해야 합니다.

## <a name="manage-security-defaults"></a>보안 기본값 관리

1. 전역 관리자 자격 증명을 사용하여 [관리 센터](https://go.microsoft.com/fwlink/p/?linkid=834822)에 로그인합니다.
2. [Azure Active Directory 속성](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Properties)로 이동합니다.

3. 페이지 맨 아래에서 **보안 기본값 관리**를 선택합니다.
4. 보안 기본값을 사용하도록 설정하려면 **예**를 선택하고 사용하지 않도록 설정하려면 **아니요**를 선택합니다.

## <a name="move-from-baseline-policies-to-security-defaults"></a>기본 정책에서 보안 기본값으로 이동

1. [관리 센터](https://go.microsoft.com/fwlink/p/?linkid=834822)에서 **설정**을 선택합니다.

2. **로그인 및 보안**옆의 **더욱 안전하게 로그인**에서 **보기**를 선택합니다.

3. **더욱 안전하게 로그인**에서 **관리**를 선택합니다. 

4. **Azure 포털 조건부 액세스 정책** 페이지에서 **켬**으로 되어 있는 각 기본 정책을 선택하고 이 정책들을 **끔**으로 설정합니다.
5. [Azure Active Directory 속성](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Properties) 페이지로 이동합니다.
6. 페이지 맨 하단에서 **보안 기본값** 관리를 선택하고 **보안 기본값 사용** 창에서 **보안 기본값** 토글을 **예**로 전환합니다. 

## <a name="enable-modern-authentication-for-your-organization"></a>조직에 대 한 최신 인증을 사용 하도록 설정

모든 Office 2016 클라이언트 응용 프로그램은 ADAL(Active Directory Authentication Library)을 사용하여 MFA를 지원합니다. 즉, Office 2016 클라이언트에는 앱 암호가 필요하지 않습니다. 그러나 Office 365 구독이 ADAL 또는 최신 인증을 사용하도록 설정되어 있는지 확인해야 합니다.

1. 최신 인증을 사용하도록 설정하려면 [관리 센터](https://go.microsoft.com/fwlink/p/?linkid=834822)의 **설정** \> **설정**을 선택하고 **서비스**탭의 목록에서 **최신 인증**을 선택합니다.

2. **최신 인증** 패널에서 **최신 인증 사용** 확인란을 선택합니다. 

    ![사용 확인란이 선택된 최신 인증 패널](../media/enablemodernauth.png)
    
## <a name="enable-multi-factor-authentication-for-your-organization"></a>조직이 Azure 다단계 인증을 사용하도록 설정
    
1. [관리 센터](https://go.microsoft.com/fwlink/p/?linkid=834822)에서 **사용자** 및 **활성 사용자**를 선택 합니다.

2. **활성 사용자** 섹션에서 **다단계 인증**을 클릭 합니다.

3. **다단계 인증** 페이지에서 한 명의 사용자에 대해이 기능을 사용 하도록 설정 하는 경우 **사용자** 를 선택 하거나 다중 사용자를 사용 하도록 설정 하려면 **대량 업데이트** 를 선택 합니다.

4. **빠른 단계**에서 **사용** 을 클릭 합니다.

5. 팝업 창에서 **다단계 인증 사용**을 클릭 합니다.

조직에 대한 다단계 인증을 설정한 후에는 사용자가 장치에서 2단계 인증을 설정해야 합니다. 자세한 내용은 [Office 365에 대해 2단계 인증 설정](https://support.office.com/article/ace1d096-61e5-449b-a875-58eb3d74de14)을 참조하세요.
    
> [!TIP]
> 사용자에게 인증자 앱을 설정하는 방법을 설명하려면 [Office 365에서 Microsoft Authenticator 사용](https://support.office.com/article/use-microsoft-authenticator-with-office-365-1412611f-ad8d-43ab-807c-7965e5155411?ui=en-US&rs=en-US&ad=US#ID0EAADAAA=_Step_1)을 방문하세요.


> [!IMPORTANT]
> 2017년 8월을 기준으로 비즈니스용 Skype Online 및 Exchange Online을 포함하는 모든 새 Office 365 테넌트는 기본적으로 최신 인증을 사용하도록 설정되어 있습니다. 비즈니스용 Skype Online의 최신 인증 상태를 확인하려면 전역 관리자 자격 증명을 사용하여 비즈니스용 Skype Online PowerShell을 사용할 수 있습니다. Get-CsOAuthConfiguration을 실행하여ClientADALAuthOverride의 결과물을 확인합니다. ClientADALAuthOverride가 '허용'인 경우 최신 인증이 설정되어 있습니다.
Exchange Online의 MA 상태를 확인하려면 [Exchange Online에서 최신 인증을 사용하도록 설정](https://docs.microsoft.com/exchange/clients-and-mobile-in-exchange-online/enable-or-disable-modern-authentication-in-exchange-online)을 참조하세요.

## <a name="related-articles"></a>관련 문서

[Office 365 및 Microsoft 365 Business 플랜을 보호하는 10가지 주요 방법](secure-your-business-data.md)

[Windows 장치에서 Office 2013를 사용하기 위한 최신 인증의 사용](enable-modern-authentication.md)
