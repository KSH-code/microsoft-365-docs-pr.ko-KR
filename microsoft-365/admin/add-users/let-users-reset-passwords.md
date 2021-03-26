---
title: 사용자가 암호를 직접 재설정할 수 있도록 허용
f1.keywords:
- NOCSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom:
- MSStore_Link
- TRN_M365B
- OKR_SMB_Videos
- AdminSurgePortfolio
- okr_smb
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 5bc3f460-13cc-48c0-abd6-b80bae72d04a
description: 셀프 서비스 암호 재설정 도구를 사용하여 암호를 다시 설정하는 방법에 대해 자세히 알아보습니다.
ms.openlocfilehash: f43c409e98aa98e942bd7c7cbb15302422df241d
ms.sourcegitcommit: 1244bbc4a3d150d37980cab153505ca462fa7ddc
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/26/2021
ms.locfileid: "51222126"
---
# <a name="let-users-reset-their-own-passwords"></a>사용자가 암호를 직접 재설정할 수 있도록 허용

Microsoft 365 관리자는 사용자가 셀프 서비스 [](https://go.microsoft.com/fwlink/p/?LinkId=522677) 암호 재설정 도구를 사용할 수 있도록 하여 암호를 다시 설정하지는 않습니다. 관리자의 업무를 덜 수 있습니다!
  
## <a name="before-you-begin"></a>시작하기 전에
  
- Microsoft 365 비즈니스,  교육 또는 비영리 유료 요금제로 클라우드 사용자에 대한 셀프 서비스 암호 재설정을 무료로 받을 수 있습니다. Microsoft 365 평가판에서는 작동하지 않습니다.

- Azure를 사용합니다. 이러한 단계를 수행할 때 자동으로 Azure의 이 기능을 **무료** 로 이용할 수 있습니다. 다른 Azure 기능을 사용하지 않으면 셀프 서비스 암호 재설정을 사용하는 비용이 부과되지 않습니다.

- **If you're using an on-premises Active Directory**, the above two points don't apply. 대신 이를 설정할 수 있지만 Azure AD Premium에 대한 유료 **구독이 필요합니다.**

회사, 학교 또는 비영리용 암호 만료 정책을 설정하는 사용자를 위한 문서입니다. 이 단계를 완료하려면 Microsoft 365 관리자 계정으로 로그인해야 합니다. [관리자 계정이란?](https://docs.microsoft.com/microsoft-365/business-video/admin-center-overview)

이러한 단계를 [수행하려면](about-admin-roles.md) 전역 관리자 또는 암호 관리자 되어야 합니다.

## <a name="watch-let-users-reset-their-own-passwords"></a>감시: 사용자가 암호를 직접 재설정할 수 있도록 합니다.

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE3AY8S]

이 비디오가 도움이 된 경우에는 [소규모 비즈니스와 Microsoft 365를 처음 사용하는 사용자를 위한 전체 교육 시리즈](https://support.microsoft.com/office/6ab4bbcd-79cf-4000-a0bd-d42ce4d12816)를 참조하세요.

## <a name="steps-let-people-reset-their-own-passwords"></a>단계: 사용자가 암호를 직접 재설정할 수 있도록 합니다.

다음 단계에서는 비즈니스의 모든 사용자에 대해 셀프 서비스 암호 재설정을 켭니다.
  
::: moniker range="o365-worldwide"

1. 관리 <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">센터에서</a>설정 구성 **설정** > **페이지로 이동합니다.**

::: moniker-end

::: moniker range="o365-germany"

1. 관리 <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">센터에서</a>설정 보안 개인 정보  \> **페이지로 &amp;** 이동합니다.

::: moniker-end

::: moniker range="o365-21vianet"

1. 관리 <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">센터에서</a>설정 설정 **보안** 개인 정보 \>  \> **페이지로 &amp;** 이동합니다.

::: moniker-end

2. At the top of the **Org settings** page, select the **Security & Privacy** tab.
  
3. 셀프 **서비스 암호 재설정 을 선택합니다.**

4. 셀프 **서비스 암호 재설정에서** Azure Portal로 이동을 선택하여 셀프 서비스 암호 **재설정을 켜기 를 선택합니다.**

5. 왼쪽 탐색 창에서 사용자 를 선택한 다음 사용자 창에서 | **모든 사용자** 페이지에서 암호 재설정 **을 선택합니다.**
  
6. 속성 **페이지에서** 모두를  선택하여 비즈니스의 모든 사용자에 대해 사용하도록 설정한 다음 저장을 **선택합니다.**
  
7. 사용자가 로그인하면 향후 암호를 다시 설정하는 데 도움이 되는 추가 연락처 정보를 입력하라는 메시지가 표시될 것입니다.

## <a name="related-content"></a>관련 콘텐츠

[조직의 암호 만료 정책 설정](../manage/set-password-expiration-policy.md)

[개별 사용자 암호가 만료되지 않도록 설정](set-password-to-never-expire.md)

[Microsoft 365 Business 교육 비디오](https://support.microsoft.com/office/6ab4bbcd-79cf-4000-a0bd-d42ce4d12816)
