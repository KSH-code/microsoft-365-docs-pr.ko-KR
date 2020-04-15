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
ms.openlocfilehash: 7e48f72f2fd8cfc5042bd15f994cc98bfa5fca8c
ms.sourcegitcommit: dbbdeca5a6cd048e1bde9e820a8b8a0d6022c7a2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "43503974"
---
# <a name="set-up-multi-factor-authentication"></a>다단계 인증 설정
  
> [!IMPORTANT]
> 2019 년 10 월 21 일 이후에 구독 또는 평가판을 구매한 경우 MFA (다단계 인증)를 위해 예기치 않게 메시지가 표시 되는 경우 구독에 대해 [보안 기본값이](https://docs.microsoft.com/azure/active-directory/fundamentals/concept-fundamentals-security-defaults) 자동으로 사용 하도록 설정 됩니다.

모든 새 비즈니스용 Office 365 또는 Microsoft 365 Business 구독에는 자동으로 보안 기본값이 설정됩니다. 즉, 모든 사용자가 자신의 모바일 장치에 MFA를 설정 하 고 Microsoft Authenticator 앱을 설치 해야 합니다. 자세한 내용은 [Office 365에 대해 2단계 인증 설정](https://support.office.com/article/ace1d096-61e5-449b-a875-58eb3d74de14)을 참조하세요.  

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

필요한 경우 다른 모든 사용자들은 추가 인증을 수행하라는 요청을 받습니다. 자세한 내용은 [보안 기본값 이란?](https://docs.microsoft.com/azure/active-directory/fundamentals/concept-fundamentals-security-defaults)를 참조 하세요.

> [!NOTE]
> MFA를 설정 하거나 수정 하려면 Office 365 전역 관리자 여야 합니다. <br><br>
> 새로운 Microsoft 365 관리 센터를 사용하지 않는 경우 홈페이지 상단에 있는 **새 관리 센터 시도** 토글을 선택하여 켤 수 있습니다.

이전에 기본 정책을 사용 하여 MFA를 설정한 경우 [ 이를 해제하고 보안 기본값](#move-from-baseline-policies-to-security-defaults)을 설정해야 합니다. 그러나 Microsoft 365 Business 또는 구독에 [Azure Active Directory Premium P1 또는 Azure Active Directory Premium P2](https://azure.microsoft.com/pricing/details/active-directory/)가 포함 되어 있는 경우 [조건부 액세스](https://docs.microsoft.com/azure/active-directory/conditional-access/overview) 정책을 설정할 수도 있습니다. 조건부 액세스 정책을 사용 하려면 [최신 인증이](#enable-modern-authentication-for-your-organization) 사용 되도록 설정 되어 있는지 확인 해야 합니다.

> [!TIP]
> 사용자에게 인증자 앱을 설정하는 방법을 설명하려면 [Office 365에서 Microsoft Authenticator 사용](https://support.office.com/article/use-microsoft-authenticator-with-office-365-1412611f-ad8d-43ab-807c-7965e5155411?ui=en-US&rs=en-US&ad=US#ID0EAADAAA=_Step_1)을 방문하세요.

## <a name="manage-security-defaults"></a>보안 기본값 관리

1. 전역 관리자 자격 증명을 사용하여 [관리 센터](https://go.microsoft.com/fwlink/p/?linkid=834822)에 로그인합니다.
2. [Azure Active Directory 속성](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Properties)으로 이동합니다.
3. 페이지 맨 아래에서 **보안 기본값 관리**를 선택합니다.
4. 보안 기본값을 사용 하려면 **예** 를 선택 하 고 보안 기본값을 사용 하지 않으려면 **아니요** 를 선택한 다음 **저장**을 선택 합니다.

## <a name="move-from-baseline-policies-to-security-defaults"></a>기본 정책에서 보안 기본값으로 이동

1. [관리 센터](https://go.microsoft.com/fwlink/p/?linkid=834822)에서 **모두 표시**및 **관리 센터**아래의 **Azure Active Directory** 를 선택 합니다.

2. **Azure active directory 관리 센터** 에서 **azure active directory** > **보안**을 선택 합니다.

3. **보안 | 시작** 페이지에서 **조건부 액세스**를 선택 합니다. 

4. **조건부 액세스-정책** 페이지에서 설정 된 각 기준 정책을 선택 하 고 **이를**사용 **안 함**으로 설정할 수 있습니다.
5. [Azure Active Directory 속성](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Properties) 페이지로 이동합니다.
6. 페이지 맨 아래에서 **보안 기본값 관리**를 선택 하 **고 보안 기본값 사용 창에서** **보안 기본값 사용** 을 설정/해제를 선택한 다음 **저장** **을 선택**합니다. 

## <a name="enable-modern-authentication-for-your-organization"></a>조직에 대 한 최신 인증을 사용 하도록 설정

모든 Office 2016 클라이언트 응용 프로그램은 ADAL(Active Directory Authentication Library)을 사용하여 MFA를 지원합니다. 즉, Office 2016 클라이언트에는 앱 암호가 필요하지 않습니다. 그러나 Office 365 구독이 ADAL 또는 최신 인증을 사용하도록 설정되어 있는지 확인해야 합니다.

1. 최신 인증을 사용하도록 설정하려면 [관리 센터](https://go.microsoft.com/fwlink/p/?linkid=834822)의 **설정** \> **설정**을 선택하고 **서비스**탭의 목록에서 **최신 인증**을 선택합니다.

2. **최신** 인증 패널에서 **최신 인증 사용 (권장)** 상자를 선택 하 고 **변경 내용 저장**을 선택 합니다. 

    ![사용 확인란이 선택된 최신 인증 패널](../../media/enablemodernauth.png)
    
> [!IMPORTANT]
> 2017년 8월을 기준으로 비즈니스용 Skype Online 및 Exchange Online을 포함하는 모든 새 Office 365 테넌트는 기본적으로 최신 인증을 사용하도록 설정되어 있습니다. 비즈니스용 Skype Online의 최신 인증 상태를 확인하려면 전역 관리자 자격 증명을 사용하여 비즈니스용 Skype Online PowerShell을 사용할 수 있습니다. Get-CsOAuthConfiguration을 실행하여ClientADALAuthOverride의 결과물을 확인합니다. ClientADALAuthOverride가 '허용'인 경우 최신 인증이 설정되어 있습니다.

Exchange Online의 MA 상태를 확인하려면 [Exchange Online에서 최신 인증을 사용하도록 설정](https://docs.microsoft.com/exchange/clients-and-mobile-in-exchange-online/enable-or-disable-modern-authentication-in-exchange-online)을 참조하세요.

## <a name="related-articles"></a>관련 문서

[Office 365 및 Microsoft 365 Business 플랜을 보호하는 10가지 주요 방법](secure-your-business-data.md)

[Windows 장치에서 Office 2013를 사용하기 위한 최신 인증의 사용](enable-modern-authentication.md)
