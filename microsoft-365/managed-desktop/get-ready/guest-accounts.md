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
ms.openlocfilehash: 9daf0ded219165f692c3e5b1b6512ab264f25d41b2fda97d085a3443cbe506a3
ms.sourcegitcommit: a1b66e1e80c25d14d67a9b46c79ec7245d88e045
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/05/2021
ms.locfileid: "53819130"
---
# <a name="prerequisites-for-guest-accounts"></a>게스트 계정에 대한 필수 구성 요소

## <a name="external-collaboration-settings"></a>외부 공동 작업 설정

Microsoft Managed Desktop 액세스하려면 Azure AD 조직에서 다음 설정이 필요합니다. 외부 ID/외부 공동 작업 **설정에서** Azure [Portal에서](https://portal.azure.com) 이러한 설정을 조정할 수 있습니다.

-   게스트 **초대 제한이** 구성원 사용자로 설정되어 있으며 특정 관리자 역할에 할당된 사용자는 구성원 권한이 있는 게스트를 비롯한 게스트 사용자를 **초대할 수 있습니다.**
-   공동 **작업 제한의 경우** 다음 옵션을 선택합니다.
    -   초대를 모든 도메인(가장 포함)으로 보내기 허용을 선택하면 다른 구성이 필요하지 않습니다.
    -   지정된 도메인에 대한 초대 거부를 선택하는 경우 대상 도메인에 Microsoft.com 목록에 없는지 확인 합니다. 
    -   지정된 **도메인(가장** 제한적인)에 대한 초대만 허용을 선택하는 경우  대상 도메인에 Microsoft.com 나열해야 합니다.

이러한 설정과 상호 작용하는 제한을 설정하는 경우 최신 작업 공간 서비스 Azure Active Directory **제외해야 합니다.** 예를 들어 게스트 계정이 Intune 포털에 액세스하지 못하게 하는 조건부 액세스 정책이 있는 경우 이 정책에서 최신 **작업** 공간 서비스 계정 그룹을 제외합니다.

## <a name="unlicensed-intune-admin"></a>라이선스가 없는 Intune 관리자

라이선스가 **없는** 관리자에 대한 액세스 허용 설정을 사용하도록 설정해야 합니다. 이 설정을 사용하도록 설정하지 않으면 서비스를 위해 Azure AD 조직에 액세스하려고 할 때 오류가 발생할 수 있습니다. 액세스 범위는 운영 직원을 포함하여 사용자에게 할당된 역할에 의해 정의되어 있는 것이기 때문에 보안에 대한 걱정 없이 이 설정을 안전하게 사용하도록 설정할 수 있습니다.

이 설정을 사용하도록 설정하려면 다음 단계를 수행합니다.

1. Microsoft Endpoint Manager [관리 센터로 이동하세요.](https://go.microsoft.com/fwlink/?linkid=2109431)
2. **테넌트 관리 역할** 관리자  >    >  **라이선스로 이동합니다.**
3. 라이선스가 없는 **관리자에** 대한 액세스 허용에서 예를 **선택합니다.**

> [!IMPORTANT]
> 예를 선택한 후 이 설정을 취소할 수 **없습니다.**

자세한 내용은 에서 라이선스가 없는 [관리자를 Microsoft Intune.](/mem/intune/fundamentals/unlicensed-admins)

## <a name="steps-to-get-ready"></a>준비 단계

1. [Microsoft Managed Desktop의 필수 구성 요소](prerequisites.md)를 감토하세요.
2. [준비 상태 평가 도구](readiness-assessment-tool.md)를 사용하세요.
3. [게스트 계정의 선행 준비(이](guest-accounts.md) 문서)
4. [Microsoft Managed Desktop의 네트워크 구성](network.md)
5. [Microsoft Managed Desktop 인증서 및 네트워크 프로필 준비](certs-wifi-lan.md)
6. [Microsoft Managed Desktop의 온-프레미스 리소스 액세스 준비](authentication.md)
7. [Microsoft Managed Desktop의 앱](apps.md)
8. [Microsoft Managed Desktop의 매핑된 드라이브 준비](mapped-drives.md)
9. [Microsoft Managed Desktop의 인쇄 리소스 준비](printing.md)
