---
title: 사용자에 대한 디렉터리 동기화 Microsoft 365
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 09/30/2020
audience: Admin
ms.topic: article
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
description: Microsoft 365 Active Directory 간에 디렉터리 동기화를 설정하는 방법을 알아보십시오.
ms.openlocfilehash: f6537e1c813e564b728891ffb13f644c3850a07e
ms.sourcegitcommit: d08fe0282be75483608e96df4e6986d346e97180
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/12/2021
ms.locfileid: "59215682"
---
# <a name="set-up-directory-synchronization-for-microsoft-365"></a>사용자에 대한 디렉터리 동기화 Microsoft 365

*이 문서는 Microsoft 365 Enterprise와 Office 365 Enterprise에 모두 적용됩니다.*

Microsoft 365 Azure AD(Azure Active Directory) 테넌트에서 클라우드 기반 리소스에 액세스하기 위한 인증 및 사용 권한에 대한 ID를 저장하고 관리합니다. 

AD DS(Active Directory 도메인 서비스) 도메인 또는 포리스트가 있는 경우 AD DS 사용자 계정, 그룹 및 연락처를 Microsoft 365 Azure AD 테넌트와 동기화할 수 있습니다. 이 ID는 하이브리드 Microsoft 365. 구성 요소는 다음과 같습니다.

![사용자에 대한 디렉터리 동기화 구성 Microsoft 365.](../media/about-microsoft-365-identity/hybrid-identity.png)

Azure AD 커넥트 실행되어 AD DS를 Azure AD 테넌트와 동기화합니다. 디렉터리 동기화와 함께 다음 인증 옵션을 지정할 수도 있습니다.

- PHS(암호 해시 동기화)

  Azure AD는 인증 자체를 수행합니다.

- 통과 인증(PTA)

  Azure AD에는 AD DS가 인증을 수행하고 있습니다.

- 페더레이션 인증

  Azure AD는 인증을 요청하는 클라이언트 컴퓨터를 다른 ID 공급자에게 참조합니다.

자세한 [내용은 하이브리드 ID를](plan-for-directory-synchronization.md) 참조하세요.
  
## <a name="1-review-prerequisites-for-azure-ad-connect"></a>1. Azure AD 2013의 선행 커넥트

Azure AD 구독을 무료로 받을 수 Microsoft 365. 디렉터리 동기화를 설정하면 Azure AD 커넥트 서버 중 하나에 설치됩니다.
  
이 Microsoft 365 다음을 해야 합니다.
  
- 사내 도메인을 검증합니다. Azure AD 커넥트 안내합니다.
- 테넌트 및 AD DS의 관리자 계정의 Microsoft 365 이름과 암호를 얻습니다.

Azure AD 2016을 설치하는 커넥트 서버의 경우 다음이 필요합니다.
  
|**서버 OS**|**기타 소프트웨어**|
|:-----|:-----|
|Windows Server 2012 R2 이상 | - PowerShell은 기본적으로 설치되어 있습니다. 필요한 작업은 없습니다.  <br> - Net 4.5.1 이상 릴리스는 업데이트 업데이트를 통해 Windows 있습니다. 제어판에서 Windows 최신 업데이트를 설치해야 합니다. |
|Windows Server 2008 R2 서비스 팩 1(SP1) 또는 Windows Server 2012 | - 최신 버전의 PowerShell은 4.0 Windows Management Framework 있습니다. Microsoft 다운로드 [센터에서 검색합니다.](https://go.microsoft.com/fwlink/p/?LinkId=717996)  <br> - .Net 4.5.1 이상 릴리스는 [Microsoft 다운로드 센터에서 사용할 수 있습니다.](https://go.microsoft.com/fwlink/p/?LinkId=717996) |
|Windows Server 2008 | - 지원되는 최신 버전의 PowerShell은 Microsoft Windows Management Framework 3.0에서 사용할 [수 있습니다.](https://go.microsoft.com/fwlink/p/?LinkId=717996)  <br> - .Net 4.5.1 이상 릴리스는 [Microsoft 다운로드 센터에서 사용할 수 있습니다.](https://go.microsoft.com/fwlink/p/?LinkId=717996) |

Azure AD Azure Active Directory 커넥트 하드웨어, [소프트웨어,](/azure/active-directory/hybrid/how-to-connect-install-prerequisites) 계정 및 사용 권한 요구 사항, SSL 인증서 요구 사항 및 개체 제한에 대한 자세한 내용은 커넥트.
  
또한 Azure AD 커넥트 릴리스 기록을 검토하여 각 [릴리스에](/azure/active-directory/hybrid/reference-connect-version-history) 포함 및 고정된 버전을 볼 수 있습니다.

## <a name="2-install-azure-ad-connect-and-configure-directory-synchronization"></a>2. Azure AD 커넥트 설치 및 디렉터리 동기화 구성

시작하기 전에 다음이 있는지 확인한 후 다음을 선택해야 할 수 있습니다.

- 전역 관리자의 사용자 Microsoft 365 암호
- AD DS 도메인 관리자의 사용자 이름 및 암호
- 어떤 인증 방법(PHS, PTA, 페더래드)
- [Azure AD Seamless SSO(Single Sign-On)를](/azure/active-directory/hybrid/how-to-connect-sso) 사용할지 여부

다음 단계를 따릅니다:

1. Microsoft 365 관리 센터 [로그인하고](https://admin.microsoft.com) 왼쪽 탐색 창에서 https://admin.microsoft.com) **사용자** \> **활성** 사용자를 선택 합니다.
2. 활성 **사용자 페이지에서** 더 **(세** 점) 디렉터리 동기화 \> **를 선택합니다.**
  
3. Azure Active Directory **준비** 페이지에서 다운로드 센터로 이동을 선택하여 **Azure AD** 커넥트 도구 링크를 시작하세요. 
4. Azure AD 커넥트 Azure AD 커넥트 [설치 로드맵의 단계를 따릅니다.](/azure/active-directory/hybrid/how-to-connect-install-roadmap)

## <a name="3-finish-setting-up-domains"></a>3. 도메인 설정 완료

DNS 레코드를 관리할 때 도메인에 Microsoft 365 [DNS](/office365/admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider) 레코드 만들기의 단계에 따라 도메인 설정을 완료합니다.

## <a name="next-step"></a>다음 단계

[사용자 계정에 라이선스 할당](assign-licenses-to-user-accounts.md)