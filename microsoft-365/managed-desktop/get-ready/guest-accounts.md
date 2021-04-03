---
title: 게스트 계정에 대한 필수 구성 요소
description: 게스트 계정에 대한 구성 지침 및 조정 방법
keywords: Microsoft Managed Desktop, Microsoft 365, 서비스, 문서
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
audience: Admin
ms.openlocfilehash: bbf679a01716fc48d37b241d69740f50a985f048
ms.sourcegitcommit: 53acc851abf68e2272e75df0856c0e16b0c7e48d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/02/2021
ms.locfileid: "51574610"
---
# <a name="prerequisites-for-guest-accounts"></a>게스트 계정에 대한 필수 구성 요소

Microsoft Managed Desktop을 사용하려면 Azure AD 조직에서 게스트 계정 액세스를 위해 다음 설정이 필요합니다. 외부 ID/외부 공동 작업에서 [Azure Portal에서](https://portal.azure.com) **이러한 설정을 조정할 수 있습니다.**

-   **게스트 초대자** 역할의 관리자 및 사용자는 예로 설정하여 초대할 수 **있습니다.**
-   공동 **작업 제한의 경우** 다음 옵션을 선택합니다.
    -   초대를 모든 도메인(가장 포함)으로 보내기 허용을 선택하면 다른 구성이 필요하지 않습니다.
    -   지정된 도메인에 대한 초대 거부를 선택하는 경우 대상 도메인에 Microsoft.com 목록에 없는지 확인 합니다. 
    -   지정된 **도메인(가장** 제한적인)에 대한 초대만 허용을 선택하는 경우  대상 도메인에 Microsoft.com 나열해야 합니다.

이러한 설정과 상호 작용하는 제한을 설정하는 경우 Azure Active Directory 최신 작업 공간 서비스 계정 을 **제외해야 합니다.** 예를 들어 게스트 계정이 Intune 포털에 액세스하지 못하게 하는 조건부 액세스 정책이 있는 경우 이 정책에서 최신 **작업** 공간 서비스 계정 그룹을 제외합니다.

## <a name="steps-to-get-ready"></a>준비 단계

1. [Microsoft Managed Desktop의 선행 준비를 검토합니다.](prerequisites.md)
2. 준비 [평가 도구 사용.](readiness-assessment-tool.md)
3. [게스트 계정의 선행 준비(이](guest-accounts.md) 문서)
4. [Microsoft Managed Desktop의 네트워크 구성](network.md)
5. [Microsoft Managed Desktop 인증서 및 네트워크 프로필 준비](certs-wifi-lan.md)
6. [Microsoft Managed Desktop의 온-프레미스 리소스 액세스 준비](authentication.md)
7. [Microsoft Managed Desktop의 앱](apps.md)
8. [Microsoft Managed Desktop의 매핑된 드라이브 준비](mapped-drives.md)
9. [Microsoft Managed Desktop의 인쇄 리소스 준비](printing.md)