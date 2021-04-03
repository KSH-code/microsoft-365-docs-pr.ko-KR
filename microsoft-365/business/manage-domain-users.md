---
title: 도메인 사용자를 Microsoft 365와 동기화
f1.keywords:
- NOCSH
ms.author: efrene
author: efrene
manager: scotv
audience: Admin
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
ms.collection: M365-subscription-management
ms.custom:
- Adm_O365
- Core_O365Admin_Migration
- MiniMaven
- MSB365
- OKR_SMB_M365
- seo-marvel-mar
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
description: 도메인 제어 사용자를 비즈니스용 Microsoft 365와 동기화합니다.
ms.openlocfilehash: b477b8a1f35a790d6c49937c973c141ad9f90ad4
ms.sourcegitcommit: 53acc851abf68e2272e75df0856c0e16b0c7e48d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/02/2021
ms.locfileid: "51578410"
---
# <a name="synchronize-domain-users-to-microsoft-365"></a>도메인 사용자를 Microsoft 365와 동기화

## <a name="1-prepare-for-directory-synchronization"></a>1. 디렉터리 동기화 준비 

로컬 Active Directory 도메인에서 사용자 및 컴퓨터를 동기화하기 전에 [Microsoft 365로의](../enterprise/prepare-for-directory-synchronization.md)디렉터리 동기화 준비를 검토합니다. 특히:

   - 메일, **proxyAddresses** 및 **userPrincipalName** 특성에 대한 중복이 디렉터리에 없는지 확인합니다.  이러한 값은 고유해야 합니다. 중복된 값은 모두 제거해야 합니다.
   
   - 사용이 허가된 Microsoft 365 사용자에 해당하는 기본 전자 메일 주소와 일치하도록 각 로컬 사용자 계정에 대해 **USERPrincipalName(UPN)** 특성을 구성하는 것이 좋습니다. 예:  *mary.shelley@contoso.com.local이* 아닌 mary@contoso.
   
   - Active Directory 도메인이 *.com* 또는 *.org와* 같은 인터넷 라우팅 가능 접미사 대신 *.local* 또는 *.lan과* 같은 라우팅할 수 없는 접미사로 끝나면 디렉터리 동기화를 위해 라우팅할 수 없는 도메인 준비에 설명된 바와 같이 먼저 로컬 사용자 계정의 UPN 접미사를 조정합니다. [](../enterprise/prepare-a-non-routable-domain-for-directory-synchronization.md) 

아래 4단계에서 **IdFix** 실행을 통해 디렉터리 동기화를 위한 준비도 완료됩니다.

## <a name="2-install-and-configure-azure-ad-connect"></a>2. Azure AD Connect 설치 및 구성

로컬 Active Directory의 사용자, 그룹 및 연락처를 Azure Active Directory에 동기화하려면 Azure Active Directory Connect를 설치하고 디렉터리 동기화를 설정하세요. 

 1. 관리 [센터의](https://go.microsoft.com/fwlink/p/?linkid=2024339)왼쪽 **네비게이트에서** 설치를 선택합니다.

 2. 로그인 **및 보안에서,**  사용자의 디렉터리에서 사용자 동기화 아래에서 **보기를 선택하십시오.**

 3. On the **Sync users from your org's directory** page, choose Get **started**.

 4. 첫 번째 단계에서 IdFix 도구를 실행하여 디렉터리 동기화를 준비합니다.

 5. 마법사 단계에 따라 Azure AD Connect를 다운로드하고 이를 사용하여 도메인 제어 사용자를 Microsoft 365와 동기화합니다.


자세한 [내용은 Microsoft 365에](../enterprise/set-up-directory-synchronization.md) 대한 디렉터리 동기화 설정하기를 참조합니다.

Azure AD Connect에 대한 옵션을 구성할 때 비즈니스용 Microsoft 365에서도  지원되는 암호 **동기화,** 원활한 **Single Sign-On** 및 암호 쓰기 저장 기능을 사용하는 것이 좋습니다.

> [!NOTE]
> Azure AD Connect의 확인란을 넘어 암호 쓰기 저장을 위한 몇 가지 추가 단계가 있습니다. 자세한 내용은 방법: 암호 쓰기 [저장 구성을 참조하십시오.](/azure/active-directory/authentication/howto-sspr-writeback) 

도메인에 가입된 Windows 10 장치도 관리하려면 도메인에 가입된 [Windows 10 장치를 Microsoft 365 Business Premium에서](manage-windows-devices.md) 관리하도록 설정을 참조하여 하이브리드 Azure AD 가입을 설정하세요.