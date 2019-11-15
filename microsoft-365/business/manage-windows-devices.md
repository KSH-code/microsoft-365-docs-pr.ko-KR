---
title: 도메인에 가입 된 Windows 10 장치를 Microsoft 365 Business에서 관리할 수 있도록 설정
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- M365-identity-device-management
ms.custom:
- Adm_O365
- Core_O365Admin_Migration
- MiniMaven
- MSB365
- OKR_SMB_M365
search.appverid:
- BCS160
- MET150
ms.assetid: 9b4de218-f1ad-41fa-a61b-e9e8ac0cf993
description: Microsoft 365에서 로컬 Active Directory에 가입 된 Windows 10 장치를 보호 하도록 설정 하는 방법을 알아봅니다.
ms.openlocfilehash: 93e3364fc94f3878bec13d0a87b17a7d3678a4cc
ms.sourcegitcommit: 9a057e70637dcfe06d4f729a96c02be989cf9e25
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/14/2019
ms.locfileid: "38633272"
---
# <a name="enable-domain-joined-windows-10-devices-to-be-managed-by-microsoft-365-business"></a>도메인에 가입 된 Windows 10 장치를 Microsoft 365 Business에서 관리할 수 있도록 설정

조직에서 Windows Server Active Directory 온-프레미스를 사용 하는 경우에는 Microsoft 365 Business를 설정 하 여 Windows 10 장치를 보호 하 되, 로컬 인증을 필요로 하는 온-프레미스 리소스에 대 한 액세스를 계속 유지할 수 있습니다.
이 보호를 설정 하기 위해 **하이브리드 AZURE AD에 가입 된 장치**를 구현할 수 있습니다. 이러한 장치는 온-프레미스 Active Directory 및 Azure Active Directory에 모두 가입 되어 있습니다.

이 비디오에서는 다음 단계에서 자세히 설명 되는 가장 일반적인 시나리오에 대해이 설정을 구성 하는 단계를 보여 줍니다.

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE3C9hO]
  

## <a name="1-prepare-for-directory-synchronization"></a>1. 디렉터리 동기화 준비 

로컬 Active Directory 도메인에서 사용자 및 컴퓨터를 동기화 하기 전에 [Office 365에 대 한 디렉터리 동기화 준비](https://docs.microsoft.com/office365/enterprise/prepare-for-directory-synchronization)를 검토 합니다. 특히 다음을 수행 합니다.

   - 디렉터리에 **mail**, **proxyAddresses**및 **userPrincipalName**특성에 대 한 중복이 없는지 확인 합니다. 이러한 값은 고유 해야 하며 모든 중복 항목을 제거 해야 합니다.
   
   - 사용이 허가 된 Microsoft 365 사용자에 해당 하는 기본 전자 메일 주소와 일치 하도록 각 로컬 사용자 계정에 대 한 **userPrincipalName** (UPN) 특성을 구성 하는 것이 좋습니다. 예: *mary@contoso* 가 아닌 *mary.shelley@contoso.com*
   
   - Active Directory 도메인이 *.com* 또는 *org*와 같이 라우팅할 수 없는 접미사로 끝나는 ** 경우 [디렉터리 동기화를 위해 라우팅할 수 없는 도메인을 준비](https://docs.microsoft.com/office365/enterprise/prepare-a-non-routable-domain-for-directory-synchronization)하는 방법에 설명 된 대로 로컬 사용자 계정의 UPN *접미사를 먼저*조정 합니다. 

## <a name="2-install-and-configure-azure-ad-connect"></a>2. Azure AD Connect 설치 및 구성

로컬 Active Directory의 사용자, 그룹 및 연락처를 Azure Active Directory에 동기화 하려면 Azure Active Directory Connect를 설치 하 고 디렉터리 동기화를 설정 합니다. 자세한 내용은 [Office 365에 대 한 디렉터리 동기화 설정](https://support.office.com/article/1b3b5318-6977-42ed-b5c7-96fa74b08846) 를 참조 하세요.

> [!NOTE]
> 이 단계는 Microsoft 365 비즈니스에서 동일 합니다. 

Azure AD Connect에 대 한 옵션을 구성 하는 경우 **암호 동기화**, **원활한 Single sign-on**및 **암호 쓰기 저장** 기능을 사용 하도록 설정 하는 것이 좋습니다 (Microsoft 365 Business 에서도 지원 됨).

> [!NOTE]
> Azure AD Connect의 확인란 외에도 암호 쓰기 저장을 위한 몇 가지 추가 단계가 있습니다. 자세한 내용은 [방법: 암호 쓰기 저장 구성](https://docs.microsoft.com/azure/active-directory/authentication/howto-sspr-writeback)를 참조 하세요. 

## <a name="3-configure-hybrid-azure-ad-join"></a>3. 하이브리드 Azure AD 조인 구성

Windows 10 장치에서 하이브리드 Azure AD에 가입 되도록 설정 하기 전에 다음 필수 구성 요소를 충족 하는지 확인 합니다.

   - 최신 버전의 Azure AD Connect를 실행 하 고 있습니다.

   - Azure AD connect에서 하이브리드 Azure AD에 가입 하려는 장치의 모든 컴퓨터 개체를 동기화 했습니다. 컴퓨터 개체가 특정 OU (조직 구성 단위)에 속하는 경우 이러한 Ou가 Azure AD connect 에서도 동기화 되도록 설정 되어 있는지 확인 합니다.

기존 도메인에 가입한 Windows 10 장치를 하이브리드 Azure AD에 연결 된 상태로 등록 하려면 [자습서: managed domains에 대 한 하이브리드 Azure Active Directory Join 구성](https://docs.microsoft.com/azure/active-directory/devices/hybrid-azuread-join-managed-domains#configure-hybrid-azure-ad-join)의 단계를 수행 합니다. 이 하이브리드는 기존 온-프레미스 Active Directory에서 가입한 Windows 10 컴퓨터를 사용할 수 있도록 설정 하 고 클라우드를 준비 합니다.
    
## <a name="4-enable-automatic-enrollment-for-windows-10"></a>4. Windows 10에 대해 자동 등록을 사용 하도록 설정

 Intune에서 모바일 장치 관리용 Windows 10 장치를 자동으로 등록 하려면 [그룹 정책을 사용 하 여 자동으로 windows 10 장치 등록](https://docs.microsoft.com/windows/client-management/mdm/enroll-a-windows-10-device-automatically-using-group-policy)을 참조 하세요. 로컬 컴퓨터 수준에서 그룹 정책을 설정 하거나, 대량 작업의 경우 그룹 정책 관리 콘솔과 ADMX 템플릿을 사용 하 여 도메인 컨트롤러에서이 그룹 정책 설정을 만들 수 있습니다.

## <a name="5-configure-seamless-single-sign-on"></a>5. 원활한 Single Sign-on 구성

  원활한 SSO는 회사 컴퓨터를 사용할 때 사용자에 게 Microsoft 365 클라우드 리소스를 자동으로 로그인 합니다. [Azure Active Directory 원활한 Single sign-on: 빠른 시작](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-sso-quick-start#step-2-enable-the-feature)에 설명 된 두 가지 그룹 정책 옵션 중 하나를 배포 하기만 하면 됩니다. **그룹 정책** 옵션을 사용 하 여 사용자의 설정을 변경할 수는 없지만 **그룹 정책 기본 설정** 옵션은 값을 설정 하지만 사용자 구성 가능도 그대로 둡니다.

## <a name="6-set-up-windows-hello-for-business"></a>6. 비즈니스용 Windows Hello 설정

 비즈니스용 Windows Hello는 암호를 강력한 2 단계 인증 (2FA)으로 대체 하 여 로컬 컴퓨터에 로그인 합니다. 한 가지 요인은 비대칭 키 쌍이 고 다른 하나는 장치에서 지 원하는 경우 지문 또는 얼굴 인식과 같은 다른 로컬 제스처 또는 PIN입니다. 가능한 경우 암호를 2 FA 및 Windows Hello for Business로 바꾸는 것이 좋습니다.

비즈니스용 하이브리드 Windows Hello를 구성 하려면 [하이브리드 키 트러스트 Windows hello For Business 필수 구성 요소](https://docs.microsoft.com/windows/security/identity-protection/hello-for-business/hello-hybrid-key-trust-prereqs)를 참조 하세요. 그런 다음 [비즈니스용 하이브리드 Windows Hello 키 트러스트 설정](https://docs.microsoft.com/windows/security/identity-protection/hello-for-business/hello-hybrid-key-whfb-settings)의 지침을 따릅니다. 
