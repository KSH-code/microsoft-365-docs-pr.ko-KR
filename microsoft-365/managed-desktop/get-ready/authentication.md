---
title: Microsoft Managed Desktop의 온-프레미스 리소스 액세스 준비
description: Azure AD가 인증을 제공하기 위해 사내 AD와 통신할 수 있도록 하는 중요한 단계
keywords: Microsoft Managed Desktop, Microsoft 365, 서비스, 문서
ms.service: m365-md
author: jaimeo
ms.localizationpriority: medium
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
audience: Admin
ms.openlocfilehash: ad4fcdf57d8a9469d29f026742a96baa630aefff
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/06/2021
ms.locfileid: "60166757"
---
#  <a name="prepare-on-premises-resources-access-for-microsoft-managed-desktop"></a>Microsoft Managed Desktop의 온-프레미스 리소스 액세스 준비

이 Microsoft Managed Desktop 디바이스는 Azure AD(Azure Active Directory 자동으로 가입됩니다. 이러한 이유로, On-premises Active Directory를 사용하는 경우 Azure AD에 가입된 장치가 On-premises Active Directory와 통신할 수 있도록 몇 가지를 검사해야 합니다. 

> [!NOTE]  
> *하이브리드* Azure AD 조인은 지원되지 Microsoft Managed Desktop.

Azure Active Directory 사용하면 사용자가 SSO(Single Sign-On)를 활용할 수 있습니다. 즉, 일반적으로 리소스를 사용할 때마다 자격 증명을 제공할 필요가 없습니다.

구독에 가입하는 Azure Active Directory 방법: Azure AD 조인 구현 계획을 [참조하세요.](/azure/active-directory/devices/azureadjoin-plan) Azure AD에 가입된 Sign-On SSO(Single Sign-On)에 대한 배경 정보는 Azure AD 가입 장치에서 SSO-프레미스 리소스가 작동하는 방법을 [참조하세요.](/azure/active-directory/devices/azuread-join-sso#how-it-works)


이 문서에서는 로컬 Active Directory 연결에 종속된 앱 및 기타 리소스가 로컬 Active Directory 연결에서 원활하게 작동하도록 보장하기 위해 확인해야 하는 Microsoft Managed Desktop.


## <a name="single-sign-on-for-on-premises-resources"></a>Sign-On 리소스에 대한 단일 리소스

UPN 및 Sign-On SSO(Single Sign-On)는 디바이스에서 기본적으로 Microsoft Managed Desktop 사용됩니다. 그러나 사용자는 비즈니스용 Windows Hello 수 있습니다. 이 경우 몇 가지 추가 설정 단계가 필요합니다. 

### <a name="single-sign-on-by-using-upn-and-password"></a>UPN 및 Sign-On 사용하여 단일 사용자 관리

대부분의 조직에서 사용자는 SSO를 사용하여 모든 장치에서 UPN 및 암호로 Microsoft Managed Desktop 있습니다. 그러나 이 함수가 작동할 수 있도록 다음을 다시 검사해야 합니다.

- Azure AD 커넥트 설정되어 있으며 Windows Server 2008 R2 이상을 실행하는 Windows Active Directory 서버를 사용하는지 확인합니다.
- Azure AD 커넥트 지원되는 버전을 실행하고 있으며 이러한 세 가지 특성을 Azure AD와 동기화할 수 있습니다. 
    - 사용자 위치의 DNS 도메인 이름(사용자가 있는 경우)의 DNS 도메인 이름
    - 사용자 위치의 NetBIOS(On-premises Active Directory)
    - 사용자의 SAM 계정 이름


### <a name="single-sign-on-by-using-windows-hello-for-business"></a>비즈니스용 Sign-On 사용하여 단일 Windows Hello 사용

Microsoft Managed Desktop 디바이스는 비즈니스용 디바이스를 사용하여 사용자에게 빠르고 암호 없는 환경을 Windows Hello 제공합니다. 사용자가 Windows Hello UPN 및 암호를 제공하지 않고도 비즈니스용 Windows Hello 작동하도록 보장하기 위해 Configure [Azure AD joined devices for On using Windows Hello Single-Sign for Business](/windows/security/identity-protection/hello-for-business/hello-hybrid-aadj-sso-base) to check the requirements을 확인한 다음 여기에 제공된 단계를 따르세요.


## <a name="apps-and-resources-that-use-authentication"></a>인증을 사용하는 앱 및 리소스

Azure 콘텐츠 [집합의](/azure/active-directory/devices/azureadjoin-plan#understand-considerations-for-applications-and-resources) 응용 프로그램 및 리소스에 대한 고려 사항 이해를 참조하여 Azure 콘텐츠 집합과 함께 작동할 앱을 설정하는 방법에 대한 자세한 Azure Active Directory. 요약:


- Azure AD 앱 갤러리에 추가된 앱과 같은 클라우드 기반 앱을 사용하는 경우 대부분 추가 준비를 할 필요가 Microsoft Managed Desktop. 그러나 WAM(웹 계정 관리자)을 사용하지 않는 Win32 앱은 사용자에게 인증을 요청하는 메시지가 계속 표시될 수 있습니다.

- 사내에서 호스팅하는 앱의 경우 브라우저의 신뢰할 수 있는 사이트 목록에 해당 앱을 추가해야 합니다. 이 단계를 Windows 사용자에게 자격 증명을 요청하지 않고도 인증이 원활하게 작동하도록 할 수 있습니다. 앱을 추가하려면 구성 [가능한](../working-with-managed-desktop/config-setting-ref.md#trusted-sites) 설정 참조에서 [신뢰할 수 있는 사이트를 참조하세요.](../working-with-managed-desktop/config-setting-ref.md)

- Active Directory Federated Services를 사용하는 경우 [AD FS를](/previous-versions/azure/azure-services/jj151809(v=azure.100))사용하여 Single Sign-On 확인 및 관리의 단계를 사용하여 SSO가 사용하도록 설정되어 있는지 확인합니다. 

- 장치가 인증을 위해온-프레미스 도메인 컨트롤러에 액세스할 수 있는 한, 사내에 있는 앱의 경우 이전 프로토콜을 사용하는 앱의 경우 추가 설정이 필요하지 않습니다. 그러나 이러한 응용 프로그램에 대한 보안 액세스를 제공하기 위해 Azure AD 응용 프로그램 프록시를 배포해야 합니다. 자세한 내용은 응용 프로그램 프록시를 통해 Azure Active Directory [원격 액세스를 참조하세요.](/azure/active-directory/manage-apps/application-proxy)

- **사내에서 실행되어** 컴퓨터 인증을 사용하는 앱은 지원되지 않습니다. 따라서 이를 최신 버전으로 바꾸는 것이 고려해야 합니다.

### <a name="network-shares-that-use-authentication"></a>인증을 사용하는 네트워크 공유

장치가 UNC 경로를 사용하여 사내 도메인 컨트롤러에 액세스할 수 있는 한 사용자가 네트워크 공유에 액세스하기 위해 추가 설정이 필요하지 않습니다.

### <a name="printers"></a>프린터

Microsoft Managed Desktop 클라우드 인쇄를 구성하지 않은 경우 장치에서는 사내 Active Directory에 게시된 프린터에 연결할 [수 없습니다.](/windows-server/administration/hybrid-cloud-print/hybrid-cloud-print-deploy)

클라우드 전용 환경에서는 프린터를 자동으로 검색할 수 없는 반면, 디바이스가 사내 도메인 컨트롤러에 액세스할 수 있는 한 사용자는 프린터 경로 또는 프린터 큐 경로를 사용하여 사내 프린터를 사용할 수 있습니다.

<!--add fuller material on printers when available-->
## <a name="steps-to-get-ready-for-microsoft-managed-desktop"></a>준비 단계 Microsoft Managed Desktop

1. [Microsoft Managed Desktop의 필수 구성 요소](prerequisites.md)를 감토하세요.
2. [준비 상태 평가 도구](readiness-assessment-tool.md)를 실행하세요.
1. [회사 포털](../get-started/company-portal.md)을 구입하세요.
1. [게스트 계정에 대한 필수 구성 요소](guest-accounts.md)를 검토합니다.
1. [네트워크 구성](network.md)을 확인합니다.
1. [인증서 및 네트워크 프로필을 준비](certs-wifi-lan.md)합니다.
1. 데이터에 대한 사용자 액세스를 준비합니다(이 문서).
1. [앱을 준비](apps.md)합니다.
1. [매핑된 드라이브를 준비](mapped-drives.md)합니다.
1. [인쇄 리소스를 준비](printing.md)합니다.
1. [장치 이름](address-device-names.md)을 기입합니다.