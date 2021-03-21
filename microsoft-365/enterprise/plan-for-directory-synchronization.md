---
title: Microsoft 365에 대한 하이브리드 ID 및 디렉터리 동기화
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
audience: Admin
ms.topic: conceptual
ms.date: 09/30/2020
ms.service: o365-administration
localization_priority: Normal
f1.keywords:
- CSH
ms.custom: Adm_O365
ms.collection:
- Ent_O365
- M365-identity-device-management
search.appverid:
- MOE150
- MET150
ms.assetid: d3577c90-dda5-45ca-afb0-370d2889b10f
description: Microsoft 365, Active Directory 도메인 서비스 정리 및 Azure Active Directory Connect 도구와의 디렉터리 동기화에 대해 설명합니다.
ms.openlocfilehash: 7b717f65bb434918a5eb0ab2bf4a5acab2d08eea
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/19/2021
ms.locfileid: "50927547"
---
# <a name="hybrid-identity-and-directory-synchronization-for-microsoft-365"></a>Microsoft 365에 대한 하이브리드 ID 및 디렉터리 동기화

*이 문서는 Microsoft 365 Enterprise와 Office 365 Enterprise에 모두 적용됩니다.*

비즈니스 요구 사항 및 기술 요구 사항에 따라 Microsoft 365를 채택하는 엔터프라이즈 고객에게는 하이브리드 ID 모델 및 디렉터리 동기화가 가장 일반적으로 선택됩니다. 디렉터리 동기화를 통해 AD DS(Active Directory 도메인 서비스)의 ID를 관리할 수 있으며 사용자 계정, 그룹 및 연락처에 대한 모든 업데이트가 Microsoft 365 구독의 Azure AD(Azure Active Directory) 테넌트와 동기화됩니다.

>[!Note]
>AD DS 사용자 계정이 처음으로 동기화되는 경우 Microsoft 365 라이선스가 자동으로 할당되지는 않습니다. 전자 메일과 같은 Microsoft 365 서비스에 액세스할 수 없습니다. 먼저 사용 위치를 할당해야 합니다. 그런 다음 그룹 구성원 자격을 통해 개별적으로 또는 동적으로 이러한 사용자 계정에 라이선스를 할당합니다.
>

## <a name="authentication-for-hybrid-identity"></a>하이브리드 ID에 대한 인증

하이브리드 ID 모델을 사용하는 경우 두 가지 인증 유형이 있습니다.

- 관리되는 인증

  Azure AD는 로컬에 저장된 해시된 버전의 암호를 사용하여 인증 프로세스를 처리하거나, 자격 증명을 사내 소프트웨어 에이전트로 전송하여 인증 프로세스를 처리합니다.

- 페더레이션 인증

  Azure AD는 인증을 요청하는 클라이언트 컴퓨터를 다른 ID 공급자로 리디렉션합니다.

### <a name="managed-authentication"></a>관리되는 인증

관리되는 인증에는 두 가지 유형이 있습니다.

- PHS(암호 해시 동기화)

  Azure AD는 인증 자체를 수행합니다.

- 통과 인증(PTA)

  Azure AD에는 AD DS가 인증을 수행하고 있습니다.


#### <a name="password-hash-synchronization-phs"></a>PHS(암호 해시 동기화)

PHS를 사용하여 AD DS 사용자 계정을 Microsoft 365와 동기화하고 사용자를 사내에서 관리합니다. 사용자 암호 해시가 AD DS에서 Azure AD로 동기화되어 사용자가 동일한 암호를 사내 및 클라우드에서 사용할 수 있도록 합니다. Azure AD에서 AD DS ID에 대한 인증을 사용하도록 설정하는 가장 간단한 방법입니다. 

![PHS(암호 해시 동기화)](../media/plan-for-directory-synchronization/phs-authentication.png)

암호가 변경되거나 다시 설정되면 새 암호 해시가 Azure AD와 동기화되어 사용자가 클라우드 리소스 및 사내 리소스에 대해 항상 동일한 암호를 사용할 수 있습니다. 사용자 암호는 Azure AD로 전송되거나 Azure AD에 명확한 텍스트로 저장되지 않습니다. ID 보호와 같은 Azure AD의 일부 프리미엄 기능에는 선택한 인증 방법에 관계없이 PHS가 요구됩니다.
  
자세한 [내용은 올바른](/azure/active-directory/hybrid/choose-ad-authn) 인증 방법 선택을 참조합니다.
  
#### <a name="pass-through-authentication-pta"></a>통과 인증(PTA)

PTA는 하나 이상의 사내 서버에서 실행되는 소프트웨어 에이전트를 사용하여 AD DS를 통해 직접 사용자의 유효성을 검사하는 Azure AD 인증 서비스에 대한 간단한 암호 유효성 검사를 제공합니다. PTA를 사용하여 AD DS 사용자 계정을 Microsoft 365와 동기화하고 사용자를 사내에서 관리합니다. 

![통과 인증(PTA)](../media/plan-for-directory-synchronization/pta-authentication.png)

PTA를 사용하면 사용자가 자신의 사내 계정과 암호를 사용하여 사내 및 Microsoft 365 리소스와 응용 프로그램에 모두 로그인할 수 있습니다. 이 구성은 Azure AD에 암호 해시를 저장하지 않고 사용자 암호의 유효성을 검사합니다. 

PTA는 또한 보안 요구 사항이 있는 조직을 위해 바로 사내 사용자 계정 상태, 암호 정책 및 로그온 시간을 적용하기 위한 것입니다. 
  
자세한 [내용은 올바른](/azure/active-directory/hybrid/choose-ad-authn) 인증 방법 선택을 참조합니다.
  
### <a name="federated-authentication"></a>페더레이션 인증

페더러드 인증은 주로 보다 복잡한 인증 요구 사항이 있는 대기업 조직을 위한 것입니다. AD DS ID는 Microsoft 365와 동기화되고 사용자 계정은 사내에서 관리됩니다. 페더임 인증을 사용하는 경우 사용자는 동일한 암호를 사내 및 클라우드에서 사용할 수 있으며 Microsoft 365를 사용하기 위해 다시 로그인할 수도 없습니다. 

페더타 인증은 스마트 카드 기반 인증 또는 타사 다단계 인증과 같은 추가 인증 요구 사항을 지원할 수 있으며 일반적으로 조직에서 Azure AD에서 기본적으로 지원하지 않는 인증 요구 사항이 있는 경우 필요합니다.
 
자세한 [내용은 올바른](/azure/active-directory/hybrid/choose-ad-authn) 인증 방법 선택을 참조합니다.
  
#### <a name="third-party-authentication-and-identity-providers"></a>타사 인증 및 ID 공급자

사내 디렉터리 개체는 Microsoft 365와 동기화될 수 있으며 클라우드 리소스 액세스는 주로 타사 IdP(ID 공급자)에서 관리합니다. 조직에서 타사 페더러ation 솔루션을 사용하는 경우 타사 페더러ation 솔루션이 Azure AD와 호환되는 경우 Microsoft 365용 해당 솔루션으로 로그인을 구성할 수 있습니다.
  
자세한 내용은 [Azure AD 페더ation 호환성](/azure/active-directory/connect/active-directory-aadconnect-federation-compatibility) 목록을 참조하세요.
  
## <a name="ad-ds-preparation"></a>AD DS 준비

동기화를 사용하여 Microsoft 365로 원활하게 전환하려면 Microsoft 365 디렉터리 동기화 배포를 시작하기 전에 AD DS 포리스트를 준비해야 합니다.
  
디렉터리 준비는 다음 작업에 중점을 두야 합니다.

- 중복 **proxyAddress** 및 **userPrincipalName 특성을** 제거합니다.
- 유효한 **userPrincipalName** 특성으로 비어 있으며 잘못된 **userPrincipalName** 특성을 업데이트합니다.
- **givenName**, surname ( **sn** ), **sAMAccountName**, **displayName**, **mail**, **proxyAddresses**, **mailNickname** 및 **userPrincipalName** 특성에서 유효하지 않은 문자와 의심할 수 있는 문자를 제거합니다. 특성을 준비하는 데 대한 자세한 내용은 Azure Active Directory 동기화 도구로 동기화된 특성 [목록을 참조하세요.](https://go.microsoft.com/fwlink/p/?LinkId=396719)

    > [!NOTE]
    > 이러한 특성은 Azure AD Connect가 동기화하는 특성과 같습니다. 
  
## <a name="multi-forest-deployment-considerations"></a>다중 포리스트 배포 고려 사항

여러 포리스트 및 SSO 옵션의 경우 Azure AD Connect의 사용자 지정 [설치를 사용하세요.](/azure/active-directory/hybrid/how-to-connect-install-custom)
  
조직에 인증을 위한 포리스트가 여러 개 있는 경우(로그온 포리스트) 다음을 사용하는 것이 좋습니다.
  
- **포리스트 통합을 고려합니다.** 일반적으로 여러 포리스트를 유지 관리하는 데 더 많은 오버헤드가 필요합니다. 조직에 별도의 포리스트의 필요성을 요구하는 보안 제약 조건이 없는 경우, 사내 환경을 단순화하는 것이 좋습니다.
- **기본 로그온 포리스트에서만 사용** Microsoft 365의 초기 롤아웃을 위해 기본 로그온 포리스트에만 Microsoft 365를 배포하는 것을 고려합니다. 

다중 포리스트 AD DS 배포를 통합할 수 없는 경우 또는 다른 디렉터리 서비스를 사용하여 ID를 관리하는 경우 Microsoft 또는 파트너의 도움을 통해 이러한 디렉터리를 동기화할 수 있습니다.
  
자세한 [내용은 Azure AD Connect에 대한 토폴로지](/azure/active-directory/hybrid/plan-connect-topologies) 를 참조하세요.
  
## <a name="features-that-are-dependent-on-directory-synchronization"></a>디렉터리 동기화에 종속된 기능
  
디렉터리 동기화는 다음과 같은 기능을 위해 필요합니다.
  
- Azure AD Seamless SSO(Single Sign-On)
- Skype 동시 사용
- 다음을 비롯한 Exchange 하이브리드 배포
  - 온-프레미스 Exchange 환경과 Microsoft 365 간에 완전히 공유된 GAL(전체 주소 목록)입니다.
  - 여러 메일 시스템에서 GAL 정보를 동기화합니다.
  - Microsoft 365 서비스 제품에서 사용자를 추가하고 제거할 수 있는 기능입니다. 이렇게 하려면 다음이 필요합니다.
  - 디렉터리 동기화 설정 중에 양측 동기화를 구성해야 합니다. 기본적으로 디렉터리 동기화 도구는 디렉터리 정보를 클라우드에만 기록합니다. 양자 동기화를 구성할 때 제한된 수의 개체 특성이 클라우드에서 복사되도록 쓰기 저장 기능을 사용하도록 설정한 다음 로컬 AD DS에 다시 기록할 수 있습니다. 쓰기 쓰기 기능을 Exchange 하이브리드 모드라고도 합니다. 
  - On-premises Exchange hybrid deployment
  - 일부 사용자 사서함을 Microsoft 365로 이동하는 동시에 다른 사용자 사서함을 사내에 유지하는 능력
  - 수신이 안전한 보낸 사람 및 수신이 차단된 보낸 사람은 Microsoft 365로 복제됩니다.
  - 기본 위임 및 전자 메일 대신 보내기 기능
  - 통합된 사내 스마트 카드 또는 다단계 인증 솔루션이 있습니다.
- 사진, 미리 보기, 회의실 및 보안 그룹 동기화

## <a name="next-step"></a>다음 단계

하이브리드 ID를 배포할 준비가 되면 디렉터리 동기화 [준비를 참조합니다.](prepare-for-directory-synchronization.md)
