---
title: 도메인 사용자를 Microsoft 365와 동기화
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: sirkkuw
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
description: 도메인 제어 사용자를 비즈니스용 Microsoft 365와 동기화 합니다.
ms.openlocfilehash: b40a995a1723808d2fd171c534e9131a891840ba
ms.sourcegitcommit: e56894917d2aae05705c3b9447388d10e2156183
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/03/2020
ms.locfileid: "48841362"
---
# <a name="synchronize-domain-users-to-microsoft-365"></a>도메인 사용자를 Microsoft 365와 동기화

## <a name="1-prepare-for-directory-synchronization"></a>1. 디렉터리 동기화 준비 

로컬 Active Directory 도메인에서 사용자 및 컴퓨터를 동기화 하기 전에 [디렉터리 동기화를 Microsoft 365에 대해 준비](https://docs.microsoft.com/microsoft-365/enterprise/prepare-for-directory-synchronization)를 검토 합니다. 특히 다음을 수행 합니다.

   - 디렉터리에 **mail** , **proxyAddresses** 및 **userPrincipalName** 특성에 대 한 중복이 없는지 확인 합니다. 이러한 값은 고유 해야 하며 모든 중복 항목을 제거 해야 합니다.
   
   - 사용이 허가 된 Microsoft 365 사용자에 해당 하는 기본 전자 메일 주소와 일치 하도록 각 로컬 사용자 계정에 대 한 **userPrincipalName** (UPN) 특성을 구성 하는 것이 좋습니다. 예: *mary@contoso* 가 아닌 *mary.shelley@contoso.com*
   
   - Active Directory 도메인이 *.com* 또는 *org* 와 같이 라우팅할 수 없는 접미사로 끝나는 *.local* 경우 [디렉터리 동기화를 위해 라우팅할 수 없는 도메인을 준비](https://docs.microsoft.com/microsoft-365/enterprise/prepare-a-non-routable-domain-for-directory-synchronization)하는 방법에 설명 된 대로 로컬 사용자 계정의 UPN *접미사를 먼저* 조정 합니다. 

아래 4 단계의 **IdFix 실행** (4)에서는 온-프레미스 Active directory가 디렉터리 동기화를 수행할 수 있도록 준비 되어 있는지도 확인 합니다.

## <a name="2-install-and-configure-azure-ad-connect"></a>2. Azure AD Connect 설치 및 구성

로컬 Active Directory의 사용자, 그룹 및 연락처를 Azure Active Directory에 동기화 하려면 Azure Active Directory Connect를 설치 하 고 디렉터리 동기화를 설정 합니다. 

 1. [관리 센터](https://go.microsoft.com/fwlink/p/?linkid=2024339)의 왼쪽 탐색 창에서 **설치** 를 선택 합니다.

 2. **로그인 및 보안** 에서 조직의 **디렉터리에서 사용자 동기화** 아래의 **보기** 를 선택 합니다.

 3. **Org 디렉터리에서 사용자 동기화** 페이지에서 **시작** 을 선택 합니다.

 4. 첫 번째 단계에서는 IdFix 도구를 실행 하 여 디렉터리 동기화를 준비 합니다.

 5. 마법사의 단계에 따라 Azure AD Connect를 다운로드 하 고이를 사용 하 여 도메인 제어 사용자를 Microsoft 365와 동기화 합니다.


자세한 내용은 [Microsoft 365에 대 한 디렉터리 동기화 설정](https://docs.microsoft.com/microsoft-365/enterprise/set-up-directory-synchronization) 를 참조 하세요.

Azure AD Connect에 대 한 옵션을 구성 하는 경우 **암호 동기화** , **원활한 Single sign-on** 및 **암호 쓰기 저장** 기능을 사용 하도록 설정 하는 것이 좋습니다 (비즈니스용 Microsoft 365 에서도 지원 됨).

> [!NOTE]
> Azure AD Connect의 확인란 외에도 암호 쓰기 저장을 위한 몇 가지 추가 단계가 있습니다. 자세한 내용은 [방법: 암호 쓰기 저장 구성](https://docs.microsoft.com/azure/active-directory/authentication/howto-sspr-writeback)를 참조 하세요. 

도메인에 가입한 Windows 10 장치를 관리 하려는 경우 하이브리드 Azure AD 조인을 설정 하려면 [도메인에 가입 된 windows 10 장치를 Microsoft 365 Business Premium에서 관리할 수 있도록 설정](manage-windows-devices.md) 을 참조 하십시오. 