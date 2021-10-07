---
title: 게스트 계정에 대한 필수 구성 요소
description: 게스트 계정에 대한 구성 지침 및 조정 방법
keywords: Microsoft Managed Desktop, Microsoft 365, 서비스, 문서
ms.service: m365-md
author: jaimeo
ms.localizationpriority: medium
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
audience: Admin
ms.openlocfilehash: db07ca3bb7577aed7b334ba21893f6fe026819a0
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/06/2021
ms.locfileid: "60197140"
---
# <a name="prerequisites-for-guest-accounts"></a>게스트 계정에 대한 필수 구성 요소

## <a name="external-collaboration-settings"></a>외부 공동 작업 설정

Microsoft Managed Desktop 액세스하려면 Azure AD 조직에서 다음 구성을 권장합니다. 외부 ID/외부 공동 작업 **설정에서** Azure [Portal에서](https://portal.azure.com) 이러한 설정을 조정할 수 있습니다.

-   게스트 **사용자 액세스의 경우** 게스트 사용자로 설정하면 디렉터리 개체의 속성 및 멤버 **자격에 제한이 있습니다.**
-   게스트 **초대 설정의 경우** 구성원 사용자로 설정하고 특정 관리자 역할에 할당된 사용자는 구성원 권한이 있는 게스트를 포함하여 게스트 사용자를 **초대할 수 있습니다.**

Microsoft Managed Desktop 계정에 액세스하려면 Azure AD 조직에서 다음 구성이 필요합니다. 외부 ID/외부 공동 작업 **설정에서** Azure [Portal에서](https://portal.azure.com) 이 설정을 조정할 수 있습니다.

-   **공동 작업 제한** 에서 다음 옵션을 선택합니다.
    -   초대를 모든 도메인(가장 포함)으로 보내기 허용을 선택하면 다른 구성이 필요하지 않습니다.
    -   지정된 도메인에 대한 초대 거부를 선택하는 경우 대상 도메인에 Microsoft.com 목록에 없는지 확인 합니다. 
    -   지정된 **도메인(가장** 제한적인)에 대한 초대만 허용을 선택하는 경우  대상 도메인에 Microsoft.com 나열해야 합니다.

이러한 설정과 상호 작용하는 제한을 설정하는 경우 최신 작업 공간 서비스 Azure Active Directory **제외해야 합니다.** 예를 들어 게스트 계정이 Intune 포털에 액세스하지 못하게 하는 조건부 액세스 정책이 있는 경우 이 정책에서 최신 **작업** 공간 서비스 계정 그룹을 제외합니다.

자세한 내용은 B2B 외부 공동 작업 사용 및 게스트를 초대할 수 [있는 사용자 관리를 참조하세요.](/azure/active-directory/external-identities/delegate-invitations#to-configure-external-collaboration-settings)

## <a name="unlicensed-intune-admin"></a>라이선스가 없는 Intune 관리자

라이선스가 **없는** 관리자에 대한 액세스 허용 설정을 사용하도록 설정해야 합니다. 이 설정을 사용하도록 설정하지 않으면 서비스를 위해 Azure AD 조직에 액세스하려고 할 때 오류가 발생할 수 있습니다. 액세스 범위는 운영 직원을 포함하여 사용자에게 할당된 역할에 의해 정의되어 있는 것이기 때문에 보안에 대한 걱정 없이 이 설정을 안전하게 사용하도록 설정할 수 있습니다.

이 설정을 사용하도록 설정하려면 다음 단계를 수행합니다.

1. Microsoft Endpoint Manager [관리 센터로 이동하세요.](https://go.microsoft.com/fwlink/?linkid=2109431)
2. **테넌트 관리 역할** 관리자  >    >  **라이선스로 이동합니다.**
3. 라이선스가 없는 **관리자에** 대한 액세스 허용에서 예를 **선택합니다.**

> [!IMPORTANT]
> 예를 선택한 후 이 설정을 취소할 수 **없습니다.**

자세한 내용은 에서 라이선스가 없는 [관리자를 Microsoft Intune.](/mem/intune/fundamentals/unlicensed-admins)

## <a name="steps-to-get-ready-for-microsoft-managed-desktop"></a>준비 단계 Microsoft Managed Desktop

1. [Microsoft Managed Desktop의 필수 구성 요소](prerequisites.md)를 감토하세요.
2. [준비 상태 평가 도구](readiness-assessment-tool.md)를 실행하세요.
1. [회사 포털](../get-started/company-portal.md)을 구입하세요.
1. 게스트 계정의 선행 준비를 검토합니다(이 문서).
1. [네트워크 구성](network.md)을 확인합니다.
1. [인증서 및 네트워크 프로필을 준비](certs-wifi-lan.md)합니다.
1. [데이터에 대한 사용자 액세스를 준비](authentication.md)합니다.
1. [앱을 준비](apps.md)합니다.
1. [매핑된 드라이브를 준비](mapped-drives.md)합니다.
1. [인쇄 리소스를 준비](printing.md)합니다.
1. [장치 이름](address-device-names.md)을 기입합니다.
