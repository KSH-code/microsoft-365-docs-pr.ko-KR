---
title: 디렉터리 동기화 상태는 Microsoft 365
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Adm_O365
- seo-marvel-apr2020
ms.collection:
- Ent_O365
- M365-identity-device-management
search.appverid:
- MET150
- MOE150
- MED150
ms.assetid: 18be3b98-34ae-47be-9337-ab6c3fb372ac
description: 이 문서에서는 디렉터리 동기화의 상태를 검사하는 방법을 Office 365.
ms.openlocfilehash: 0fddffc667e4fc23b2c7663e70fb5e60c49814a2
ms.sourcegitcommit: d08fe0282be75483608e96df4e6986d346e97180
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/12/2021
ms.locfileid: "59210412"
---
# <a name="view-directory-synchronization-status-in-microsoft-365"></a>디렉터리 동기화 상태는 Microsoft 365

Azure Active Directory 환경을 Azure AD(Active Directory Domain Services)와 동기화하여 Microsoft 365 AD DS(Active Directory 도메인 서비스)를 통합한 경우 동기화 상태를 확인할 수도 있습니다.
  
## <a name="view-directory-synchronization-status"></a>디렉터리 동기화 상태 보기

- 로그인하여 Microsoft 365 관리 센터 [](https://admin.microsoft.com) **페이지에서 DirSync 상태를** 선택합니다.
- 또는 사용자 활성 **사용자로** 이동하여 활성 사용자 페이지에서 더 많은 디렉터리 동기화 \>    \> **를 선택합니다.** 디렉터리 **동기화 창에서** **DirSync 관리로 이동을 선택하십시오.**

## <a name="information-on-the-manage-directory-synchronization-page"></a>디렉터리 동기화 관리 페이지에 대한 정보

다음 표에는 페이지에서 정보를 얻을 수 있는 기능이 나열됩니다.
  
디렉터리 동기화에 문제가 있는 경우 이 페이지에도 오류가 나열됩니다. 발생할 수 있는 여러 오류에 대한 자세한 내용은 에서 디렉터리 동기화 오류 [식별을 Microsoft 365.](identify-directory-synchronization-errors.md)
  
|항목|설명|
|:-----|:-----|
|**확인된 도메인** | 소유를 확인한 Microsoft 365 테넌트의 도메인 수입니다. |
|**도메인이 확인되지 않습니다.** | 추가했지만 확인되지 않은 도메인입니다. |
|**디렉터리 동기화 사용** |True 또는 False입니다. 디렉터리 동기화를 사용하도록 설정하는지 여부를 지정합니다. |
|**최신 디렉터리 동기화** | 디렉터리 동기화를 마지막으로 시작한 시간입니다. 마지막 동기화가 3일이 지난 경우 경고와 문제 해결 도구에 대한 링크가 표시됩니다. |
|**암호 동기화 사용** | True 또는 False입니다. 당사의 사내 테넌트와 사용자 테넌트 간에 암호 해시 동기화가 Microsoft 365 지정합니다. |
|**마지막 암호 동기화** | 암호 해시 동기화가 마지막으로 시작된 시간입니다. 마지막 동기화가 3일이 지난 경우 경고와 문제 해결 도구에 대한 링크가 표시됩니다. |
|**디렉터리 동기화 클라이언트 버전** | 새 버전의 Azure AD 계정이 릴리스된 경우 커넥트 링크가 포함되어 있습니다. |
|**디렉터리 동기화 서비스 계정** | 디렉터리 동기화 서비스 Microsoft 365 이름을 나타냅니다. |
|||

## <a name="monitor-synchronization-health"></a>동기화 상태 모니터링

이 섹션에서는 각 온-프레미스 AD DS 도메인 컨트롤러에 Azure AD Connect 상태 에이전트를 설치하여 Azure AD Connect에서 제공하는 ID 인프라 및 동기화 서비스를 모니터링합니다. 모니터링 정보는 Azure AD Connect Health 포털에서 사용할 수 있습니다. 이 포털에서 경고, 성능 모니터링, 사용 현황 분석, 기타 정보를 볼 수 있습니다.

Azure AD Connect Health 사용 방법에 대한 주요 디자인 의사 결정은 Azure AD Connect 사용 방법을 기반으로 합니다.

- **관리되는 인증** 옵션을 사용하는 경우 [동기화와 함께 Azure AD Connect Health 사용](/azure/active-directory/connect-health/active-directory-aadconnect-health-sync)을 시작하여 Azure AD Connect Health를 이해하고 구성합니다.
- AD FS(Active Directory Federation Services)에서 **페더레이션 인증** 을 사용하여 계정 및 그룹의 이름만 동기화하는 경우 [AD FS와 함께 Azure AD Connect Health 사용](/azure/active-directory/connect-health/active-directory-aadconnect-health-adfs)을 시작하여 Azure AD Connect Health를 이해하고 구성합니다.

완료되면 다음을 할 수 있습니다.

- 온-프레미스 ID 서버에 Azure AD Connect Health 에이전트가 설치됩니다.
- Microsoft 365 구독에 대한 Azure AD 테넌트와 함께 온-프레미스 인프라 및 동기화 활동의 현재 상태가 Azure AD Connect Health 포털에 표시됩니다.