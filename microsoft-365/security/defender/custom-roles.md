---
title: 역할 기반 액세스 제어에 대한 사용자 지정 역할
description: 사이트 포털에서 사용자 지정 역할을 관리하는 Microsoft 365 Defender 방법
keywords: 액세스, 사용 권한, Microsoft 365 Defender, M365, 보안, MCAS, Cloud App Security, 끝점용 Microsoft Defender, 범위, 범위 지정, RBAC, 역할 기반 액세스, 사용자 지정 역할 기반 액세스, MDO의 역할 기반 auth, RBAC, 역할, 역할 및 역할 및 사용 권한 상속, 세분화 권한
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: dansimp
author: dansimp
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.technology: m365d
ms.openlocfilehash: 95fa7c4821f28775c78175aa18a413b8cd1928e5
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/06/2021
ms.locfileid: "60174414"
---
# <a name="custom-roles-in-role-based-access-control-for-microsoft-365-defender"></a>역할 기반 액세스 제어에서 사용자 지정 역할 Microsoft 365 Defender

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

[!INCLUDE [Prerelease](../includes/prerelease.md)]

**적용 대상:**

- Microsoft 365 Defender
 
다음 두 가지 유형의 역할에 액세스하는 데 사용할 수 Microsoft 365 Defender.
- **AD(Azure Active Directory 전역 역할) 역할**
- **사용자 지정 역할**

AAD(Microsoft 365 Defender 전역 역할을 사용하여 사용자 액세스 권한을 Azure Active Directory [수 있습니다.](m365d-permissions.md)

특정 제품 데이터에 대한 액세스에 대한 더 큰 유연성과 제어가 필요한 Microsoft 365 Defender 각 보안 포털을 통해 사용자 지정 역할을 만들어 액세스 권한을 관리할 수도 있습니다.  

예를 들어 끝점용 Microsoft Defender를 통해 만든 사용자 지정 역할은 사용자 지정 포털 내의 끝점 데이터를 포함하여 관련 제품 데이터에 Microsoft 365 Defender 허용합니다. 마찬가지로 Microsoft Defender for Office 365 사용자 지정 역할을 사용하면 전자 메일 포털 내의 전자 메일 & 공동 작업 데이터를 비롯한 관련 제품 데이터에 액세스할 Microsoft 365 Defender 있습니다.

기존 사용자 지정 역할이 있는 사용자는 추가 구성 없이 기존 작업 권한에 따라 Microsoft 365 Defender 포털의 데이터에 액세스할 수 있습니다.

## <a name="create-and-manage-custom-roles"></a>사용자 지정 역할 만들기 및 관리
다음 각 보안 포털을 통해 사용자 지정 역할 및 사용 권한을 만들어 개별적으로 관리할 수 있습니다. 

- 끝점용 Microsoft Defender – [끝점용 Microsoft Defender의 역할 편집](../defender-endpoint/user-roles.md)
- Microsoft Defender for Office 365 – 보안 및 준수 센터의 [& 권한](../office-365-security/permissions-in-the-security-and-compliance-center.md?preserve-view=true&view=o365-worldwide)
- Microsoft Cloud App Security – [관리자 액세스 관리](/cloud-app-security/manage-admins)

개별 포털을 통해 만든 각 사용자 지정 역할을 사용하면 관련 제품 포털의 데이터에 액세스할 수 있습니다. 예를 들어 끝점용 Microsoft Defender를 통해 만든 사용자 지정 역할은 끝점 데이터에 대한 Defender 액세스만 허용합니다.

> [!TIP]
> 탐색 창에서 사용 권한을 선택하여 Microsoft 365 Defender 및 역할에 액세스할 수도 & 있습니다. MCAS(Microsoft Cloud App Security)에 대한 액세스는 MCAS 포털을 통해 관리되고 ID용 Microsoft Defender에 대한 액세스를 제어합니다.  자세한 [내용은 Microsoft Cloud App Security](/cloud-app-security/manage-admins)

> [!NOTE]
> 사용자 지정 역할에서 만든 Microsoft Cloud App Security ID 데이터용 Microsoft Defender에 액세스할 수 있습니다. 사용자 그룹 관리자 또는 앱/인스턴스 관리자 Microsoft Cloud App Security 역할이 있는 사용자는 Microsoft Cloud App Security 포털을 통해 Microsoft 365 Defender 없습니다.

## <a name="manage-permissions-and-roles-in-the-microsoft-365-defender-portal"></a>사이트 포털에서 사용 권한 및 역할 Microsoft 365 Defender 관리
사이트 포털에서 사용 권한 및 역할을 관리할 Microsoft 365 Defender 있습니다.

1. Microsoft 365 Defender 포털에 로그인합니다 security.microsoft.com.
2. 탐색 창에서 **사용 권한 및 역할** 을 선택합니다.
3. 사용 **권한 헤더에서** 역할을 **선택합니다.**

> [!NOTE]
> 이는 Defender for Office 365 및 Endpoint용 Defender에만 적용됩니다. 다른 워크로드에 대한 액세스는 관련 포털에서 수행되어야 합니다.


## <a name="required-roles-and-permissions"></a>필요한 역할 및 사용 권한 할당
다음 표에서는 각 워크로드의 각 통합된 환경 액세스에 필요한 역할 및 사용 권한에 대해 간략하게 설명하고 있습니다. 아래 표에 정의된 역할은 개별 포털의 사용자 지정 역할을 참조하며 유사하게 이름이 지정되어 있는 경우에도 Azure AD의 전역 역할에 연결되지 않습니다.

> [!NOTE]
> 인시던트 관리를 위해서는 인시던트의 일부인 모든 제품에 대한 관리 권한이 필요합니다.
 
| **다음 역할 중 하나는 Microsoft 365 Defender**  | **Endpoint용 Defender에는 다음 역할 중 하나가 필요합니다.**  | **Defender에서 다음 역할 중 하나를 Office 365** | **다음 역할 중 하나는 다음 Cloud App Security** | 
|---------|---------|---------|---------|
| 조사 데이터 보기: <ul><li>경고 페이지</li> <li>경고 큐</li> <li>인시던트</li>  <li>인시던트 큐</li> <li>알림 센터 </li></ul>| 데이터 보기 - 보안 작업 | <ul><li>보기 전용 경고 관리 </li> <li>조직 구성</li><li>감사 로그</li> <li>보기 전용 감사 로그</li> <li>보안 읽기 권한자</li> <li>보안 관리자</li><li>보기 전용 받는 사람</li></ul>  | <ul><li>전역 관리자</li> <li>보안 관리자</li> <li>준수 관리자</li> <li>보안 운영자</li> <li>보안 읽기 권한자</li> <li>전역 읽기 권한자</li></ul> |
| 헌팅 데이터 보기 | 데이터 보기 - 보안 작업 | <ul><li>보안 읽기 권한자</li> <li>보안 관리자</li> <li>보기 전용 받는 사람</li> | <ul><li>전역 관리자</li> <li>보안 관리자</li> <li>준수 관리자</li> <li>보안 운영자</li> <li>보안 읽기 권한자</li> <li>전역 읽기 권한자</li></ul> |
| 경고 및 인시던트 관리 | 경고 조사 | <ul><li>경고 관리</li> <li>보안 관리자</li> | <ul><li>전역 관리자</li> <li>보안 관리자</li> <li>준수 관리자</li> <li>보안 운영자</li> <li>보안 읽기 권한자</li></ul> |
| 관리 센터 수정 | 활성 수정 작업 - 보안 작업 | 검색 및 제거 | |
| 사용자 지정 검색 설정 | 보안 설정 관리 |<ul><li>경고 관리</li> <li>보안 관리자</li></ul> | <ul><li>전역 관리자</li> <li>보안 관리자</li> <li>준수 관리자</li> <li>보안 운영자</li> <li>보안 읽기 권한자</li> <li>전역 읽기 권한자</li></ul> |
| 위협 분석 | 경고 및 인시던트 데이터: <ul><li>데이터 보기 - 보안 작업</li></ul>TVM 완화:<ul><li>데이터 보기 - 위협 및 취약성 관리</li></ul> | 경고 및 인시던트 데이터:<ul> <li>보기 전용 경고 관리</li> <li>경고 관리</li> <li>조직 구성</li><li>감사 로그</li> <li>보기 전용 감사 로그</li><li>보안 읽기 권한자</li> <li>보안 관리자</li><li>보기 전용 받는 사람</li> </ul> 전자 메일 시도 방지: <ul><li>보안 읽기 권한자</li> <li>보안 관리자</li><li>보기 전용 받는 사람</li> | MCAS 또는 MDI 사용자는 사용할 수 없습니다. |

예를 들어 끝점용 Microsoft Defender에서 헌팅 데이터를 보기 위해서는 데이터 보안 작업 보기 권한이 필요합니다.  

마찬가지로 Microsoft Defender에서 헌팅 데이터를 Office 365 사용자는 다음 역할 중 하나를 필요로 합니다.  

- 데이터 보안 작업 보기
- 보안 읽기 권한자
- 보안 관리자
- 보기 전용 받는 사람

## <a name="related-topics"></a>관련 항목
- [Microsoft 365 Defender에 대한 액세스 관리](m365d-permissions.md)
- [MCAS에 대한 관리자 액세스 관리](/cloud-app-security/manage-admins)
