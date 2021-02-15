---
title: Microsoft 365에 대한 디렉터리 동기화 설정
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 09/30/2020
audience: Admin
ms.topic: get-started-article
ms.service: o365-administration
localization_priority: Normal
f1.keywords:
- CSH
ms.custom: Adm_O365
ms.collection:
- Ent_O365
- M365-identity-device-management
search.appverid:
- MET150
- MOE150
- MED15
- MBS150
- BCS160
ms.assetid: 1b3b5318-6977-42ed-b5c7-96fa74b08846
description: Microsoft 365와 프레미스 Active Directory 간에 디렉터리 동기화를 설정하는 방법을 알아보십시오.
ms.openlocfilehash: 308774dcdbaffc1096ab6ad144484e6920accdfa
ms.sourcegitcommit: 04c4252457d9b976d31f53e0ba404e8f5b80d527
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/01/2020
ms.locfileid: "48327096"
---
# <a name="set-up-directory-synchronization-for-microsoft-365"></a>Microsoft 365에 대한 디렉터리 동기화 설정

*이 문서는 Microsoft 365 Enterprise와 Office 365 Enterprise에 모두 적용됩니다.*

Microsoft 365는 Azure AD(Azure Active Directory) 테넌트를 사용하여 인증을 위한 ID와 클라우드 기반 리소스 액세스 권한을 저장하고 관리합니다. 

AD DS(Active Directory Domain Services) 도메인 또는 포리스트가 있는 경우 AD DS 사용자 계정, 그룹 및 연락처를 Microsoft 365 구독의 Azure AD 테넌트와 동기화할 수 있습니다. Microsoft 365의 하이브리드 ID입니다. 해당 구성 요소는 다음과 같습니다.

![Microsoft 365의 디렉터리 동기화 구성 요소](../media/about-microsoft-365-identity/hybrid-identity.png)

Azure AD Connect는 On-premises 서버에서 실행되어 AD DS를 Azure AD 테넌트와 동기화합니다. 디렉터리 동기화와 함께 다음 인증 옵션을 지정할 수도 있습니다.

- PHS(암호 해시 동기화)

  Azure AD는 인증 자체를 수행합니다.

- 통과 인증(PTA)

  Azure AD에는 AD DS가 인증을 수행하고 있습니다.

- 페더레이션 인증

  Azure AD는 다른 ID 공급자에게 인증을 요청하는 클라이언트 컴퓨터를 참조합니다.

자세한 [내용은 하이브리드 ID를](plan-for-directory-synchronization.md) 참조하세요.
  
## <a name="1-review-prerequisites-for-azure-ad-connect"></a>1. Azure AD Connect의 선행 준비 검토

Microsoft 365 구독으로 무료 Azure AD 구독을 받을 수 있습니다. 디렉터리 동기화를 설정하면 Azure AD Connect가 On-premises 서버 중 하나에 설치됩니다.
  
Microsoft 365의 경우 다음을 해야 합니다.
  
- On-premises 도메인을 확인 합니다. Azure AD Connect 마법사가 이 정보를 안내합니다.
- Microsoft 365 테넌트 및 AD DS의 관리자 계정의 사용자 이름과 암호를 얻습니다.

Azure AD Connect를 설치하는 On-프레미스 서버의 경우 다음이 필요합니다.
  
|**서버 OS**|**기타 소프트웨어**|
|:-----|:-----|
|Windows Server 2012 R2 이상 | - PowerShell은 기본적으로 설치되어 있습니다. 필요한 작업은 없습니다.  <br> - Net 4.5.1 이상 릴리스는 Windows 업데이트를 통해 제공됩니다. 제어판에서 Windows Server에 대한 최신 업데이트를 설치해야 합니다. |
|Windows Server 2008 R2 서비스 팩 1(SP1) 또는 Windows Server 2012 | - 최신 버전의 PowerShell은 4.0 Windows Management Framework 있습니다. Microsoft 다운로드 [센터에서 검색합니다.](https://go.microsoft.com/fwlink/p/?LinkId=717996)  <br> - .Net 4.5.1 이상 릴리스는 [Microsoft 다운로드 센터에서 사용할 수 있습니다.](https://go.microsoft.com/fwlink/p/?LinkId=717996) |
|Windows Server 2008 | - 지원되는 최신 PowerShell 버전은 Microsoft Windows Management Framework 3.0에서 [사용할 수 있습니다.](https://go.microsoft.com/fwlink/p/?LinkId=717996)  <br> - .Net 4.5.1 이상 릴리스는 [Microsoft 다운로드 센터에서 사용할 수 있습니다.](https://go.microsoft.com/fwlink/p/?LinkId=717996) |

Azure AD Connect에 대한 하드웨어, 소프트웨어, 계정 및 사용 권한 요구 사항, SSL 인증서 요구 사항 및 개체 제한에 대한 자세한 내용은 [Azure Active Directory Connect에](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-install-prerequisites) 대한 사전 요구 사항을 참조하세요.
  
Azure AD [Connect](https://docs.microsoft.com/azure/active-directory/hybrid/reference-connect-version-history) 버전 릴리스 기록을 검토하여 각 릴리스에 포함 및 수정된 버전을 볼 수 있습니다.

## <a name="2-install-azure-ad-connect-and-configure-directory-synchronization"></a>2. Azure AD Connect 설치 및 디렉터리 동기화 구성

시작하기 전에 다음이 있는지를 확인한 후 다음을 선택해야 할 수 있습니다.

- Microsoft 365 전역 관리자의 사용자 이름 및 암호
- AD DS 도메인 관리자의 사용자 이름 및 암호
- 인증 방법(PHS, PTA, 페더타)
- [Azure AD Seamless SSO(Single Sign-On)를 사용할지 여부](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-sso)

아래 단계를 수행하세요.

1. [Microsoft 365](https://admin.microsoft.com) 관리 센터에 로그인하고 왼쪽 탐색에서 https://admin.microsoft.com) **사용자** \> **활성** 사용자를 선택하세요.
2. 활성 사용자 **페이지에서** 더 많은(3개 점) 디렉터리  \> **동기화를 선택합니다.**
  
3. Azure **Active Directory 준비** 페이지에서 다운로드 센터로 이동을 선택하여 **Azure AD Connect** 도구 링크를 다운로드하여 시작할 수 있습니다. 
4. Azure AD Connect 및 Azure AD Connect Health 설치 [로드맵의](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-install-roadmap)단계를 따릅니다.

## <a name="3-finish-setting-up-domains"></a>3. 도메인 설정 완료

DNS 레코드를 관리하여 도메인 설정을 완료할 때 [Microsoft 365용 DNS](https://docs.microsoft.com/office365/admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider) 레코드 만들기의 단계를 따릅니다.

## <a name="next-step"></a>다음 단계

[사용자 계정에 라이선스 할당](assign-licenses-to-user-accounts.md)
