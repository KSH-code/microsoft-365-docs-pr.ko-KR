---
title: Microsoft Managed Desktop에 대 한 온-프레미스 리소스 액세스 준비
description: Azure AD가 온-프레미스 AD와 통신 하 여 인증을 제공할 수 있도록 하기 위한 중요 한 단계
keywords: microsoft Managed Desktop, microsoft 365, 서비스, 설명서
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.openlocfilehash: 0f9cbe6712b8d16f435cfdf5fd84875656fa9c2e
ms.sourcegitcommit: ef589025820ddf6edb5f454826b1c12c9bcb8e49
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/11/2019
ms.locfileid: "31824468"
---
#  <a name="prepare-on-premises-resources-access-for-microsoft-managed-desktop"></a>Microsoft Managed Desktop에 대 한 온-프레미스 리소스 액세스 준비

Microsoft Managed Desktop에서 디바이스는 Azure Active Directory에 자동으로 연결 됩니다. 즉, 온-프레미스 active directory를 사용 하는 경우 Azure AD에 연결 된 장치가 온-프레미스 active directory와 통신할 수 있는지 몇 가지 사항을 확인 해야 합니다. 

> [!NOTE]  
> *하이브리드* Azure AD 조인은 Microsoft Managed Desktop에서 지원 되지 않습니다.

사용자는 Azure Active Directory를 사용 하 여 sso (Single sign-on)를 활용할 수 있으므로 작업을 수행 하려는 때마다 자격 증명을 제공 하지 않아도 됩니다. azure active directory를 완전히 처음 사용 하는 경우에 [는 방법: azure ad join 구현 계획](https://docs.microsoft.com/azure/active-directory/devices/azureadjoin-plan)--그러나 azure Active Directory 설명서를 참조 하는 경우 Microsoft에서 *하이브리드* Azure AD 조인이 지원 되지 않는다는 점에 유의 하세요. 관리 되는 데스크톱


이 항목에서는 로컬 Active Directory 연결에 의존 하는 앱 및 기타 리소스가 Microsoft Managed Desktop에서 원활 하 게 작동 하도록 하기 위해 확인 해야 하는 사항에 대해 설명 합니다.


> [!IMPORTANT]  
> 사용자가 Azure Active Directory에서 장치를 등록 하 고 Intune에서 등록 (Microsoft Managed Desktop에 필요) 하려면이 항목의 나머지 부분을 계속 하기 전에 [장치 설정 구성](https://docs.microsoft.com/azure/active-directory/devices/azureadjoin-plan#configure-your-device-settings) 의 단계를 수행 합니다.


## <a name="single-sign-on-for-on-premises-resources"></a>온-프레미스 리소스에 대 한 Single sign-on

UPN 이나 암호를 사용 하 여 장치에 대 한 sso (Single sign-on) (기본 방법)는 기본적으로 이미 작동 중 이어야 합니다. 하지만 비즈니스용 Windows Hello를 사용할 수도 있으며,이 경우 몇 가지 추가 설정 단계가 필요 합니다. sso에 대 한 배경 정보에 대 한 자세한 내용은 [Azure AD에 가입 된 장치에서 sso에서 온-프레미스 리소스의 작동 방법을](https://docs.microsoft.com/azure/active-directory/devices/azuread-join-sso#how-it-works)참조 하세요.


### <a name="single-sign-on-by-using-upn-and-passwords"></a>UPN 및 암호를 사용 하 여 Single sign-on

사용자가 UPN 및 암호로 인증 하는 데에는 특별 한 설치가 필요 하지 않으므로 Azure에서이를 기본적으로 가져올 수 있습니다. 그러나이 작업을 제대로 수행 하려면 다음을 두 번 확인 해야 합니다.

- Windows server 2008 R2 이상 버전을 실행 하는 온-프레미스 Active directory 서버를 사용 하 여 Azure Active directory (AAD) 연결이 설정 되어 있는지 확인 합니다.
- AAD 연결이 지원 되는 버전을 실행 중 이며 Azure AD에서 이러한 세 가지 키 특성을 동기화 하도록 설정 되어 있습니다. 
    - 사용자가 온-프레미스 Active Directory에 있는 DNS 도메인 이름
    - 사용자가 온-프레미스 Active Directory에 있는 NetBIOS 도메인 이름
    - SAM 사용자의 계정 이름


### <a name="sso-by-using-windows-hello-for-business"></a>비즈니스용 Windows Hello를 사용 하 여 SSO

또는 비즈니스용 Windows Hello를 채택 하 여 빠르고, 암호를 적게 사용할 수 있습니다. 이를 설정 하려면 [비즈니스용 Windows Hello를 사용 하 여 온-프레미스 Single sign-on에 대해 Azure AD 조인 장치 구성을](https://docs.microsoft.com/windows/security/identity-protection/hello-for-business/hello-hybrid-aadj-sso-base) 방문 하 여 요구 사항을 확인 한 후에 제공 되는 단계를 따르세요.


## <a name="apps-and-resources-that-use-authentication"></a>인증을 사용 하는 앱 및 리소스

azure Active Directory에서 작동 하도록 앱을 설정 하는 방법에 대 한 전체 지침은 azure content set의 [응용 프로그램 및 리소스에 대 한 고려 사항 이해](https://docs.microsoft.com/azure/active-directory/devices/azureadjoin-plan#understand-considerations-for-applications-and-resources) 를 참조 하세요. 요약:


- Azure AD 앱 갤러리에 추가 된 것과 같은 **클라우드 기반 앱**을 사용 하는 경우에는 Microsoft Managed Desktop에서 더 이상 준비할 필요가 없습니다. 그러나 WAM (웹 계정 관리자 확인)를 사용 하지 않는 모든 Win32 앱에서 사용자에 게 인증을 요청할 수도 있습니다.

- **온-프레미스에 호스트**되는 앱의 경우 브라우저의 신뢰할 수 있는 사이트 목록에 해당 앱을 추가 해야 합니다. 이렇게 하면 사용자가 자격 증명을 입력 하 라는 메시지가 표시 되지 않고 Windows 인증이 원활 하 게 작동 합니다.

- Active Directory 페더레이션 서비스를 사용 하는 경우에는 [AD FS를 사용 하 여 single sign-on 확인 및 관리](https://docs.microsoft.com/previous-versions/azure/azure-services/jj151809(v=azure.100))의 단계를 수행 합니다. 

- 온 **-프레미스 및 이전 프로토콜을 사용**하는 앱의 경우 장치에 온-프레미스 도메인 컨트롤러에 대 한 액세스 권한이 있으면 추가 설정이 필요 하지 않습니다. 그러나 이러한 응용 프로그램에 대 한 보안 액세스를 제공 하려면 Azure AD 응용 프로그램 프록시를 배포 해야 합니다. 자세한 내용은 [Azure Active Directory의 응용 프로그램 프록시를 통해 온-프레미스 응용 프로그램에 대 한 원격 액세스](https://docs.microsoft.com/azure/active-directory/manage-apps/application-proxy)를 참조 하세요.

- 온-프레미스를 실행 하 **고 컴퓨터 인증을 사용** 하는 앱은 지원 되지 않으므로 최신 버전으로 교체 하는 것이 좋습니다.

## <a name="network-shares-that-use-authentication"></a>인증을 사용 하는 네트워크 공유

장치에서 UNC 경로를 사용 하 여 온-프레미스 도메인 컨트롤러에 액세스할 수 있는 한 사용자는 네트워크 공유에 액세스 하는 데 추가 설정이 필요 하지 않습니다.

## <a name="printers"></a>프린터

클라우드 전용 환경에서는 프린터를 자동으로 검색할 수 없지만 프린터의 UNC 경로를 사용 하 여 사용자를 직접 추가할 수도 있습니다.

<!--add fuller material on printers when available-->