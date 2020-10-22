---
title: 사용자에 대 한 강력한 암호 요구 사항 해제
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
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
description: Windows PowerShell을 사용 하 여 사용자에 대 한 강력한 암호 요구 사항을 설정 하는 방법을 알아봅니다.
ms.openlocfilehash: f9a0b76d024cc18552657144e4ccf8de8a72f0d9
ms.sourcegitcommit: 3b1bd8aa1430bc9565743a446bbc27b199f30f73
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/22/2020
ms.locfileid: "48655738"
---
# <a name="turn-off-strong-password-requirements-for-users"></a>사용자에 대 한 강력한 암호 요구 사항 해제

이 문서에서는 사용자에 대해 강력한 암호 요구 사항을 해제 하는 방법에 대해 설명 합니다. 강력한 암호 요구 사항은 Microsoft 365 for business 조 직에 기본적으로 설정 되어 있습니다. 조직에서 강력한 암호를 사용 하지 않도록 설정 해야 할 수 있습니다. 다음 단계에 따라 강력한 암호 요구 사항을 해제 합니다. PowerShell을 사용 하 여 이러한 단계를 완료 해야 합니다.

## <a name="before-you-begin"></a>시작하기 전에

이 문서는 회사, 학교 또는 비영리 용 암호 정책을 관리 하는 사용자를 위한 것입니다. 이 단계를 완료하려면 Microsoft 365 관리자 계정으로 로그인해야 합니다. [관리자 계정 이란?](../admin-overview/admin-overview.md) 이 단계를 수행 하려면 [전역 관리자 또는 암호 관리자](about-admin-roles.md) 여야 합니다.

또한 PowerShell을 사용 하 여 Microsoft 365에 연결 해야 합니다.

## <a name="set-strong-passwords"></a>강력한 암호 설정

1. [PowerShell을 사용 하 여 Microsoft 365에 연결](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-office-365-powershell#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell)합니다.

2. PowerShell을 사용 하 여 다음 명령을 사용 하 여 모든 사용자에 대해 강력한 암호 요구 사항을 해제할 수 있습니다.

    ```powershell
    Get-MsolUser | Set-MsolUser -StrongPasswordRequired $false

3. You can turn of strong password requirements for specific users with this command:

    ```powershell
    Set-MsolUser –UserPrincipalName –StrongPasswordRequired  $false
    ```

> [!NOTE]
> UserPrincipalName은 사용자 이름 뒤에 @ 기호와 도메인 이름을 입력 하는 인터넷 스타일 로그인 형식 이어야 합니다. 예: user@contoso.com.

## <a name="related-content"></a>관련 콘텐츠

[PowerShell을 사용 하 여 Microsoft 365에 연결 하는 방법](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-office-365-powershell#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell)

[PowerShell Get-msoluser 명령에 대 한 추가 정보](https://docs.microsoft.com/powershell/module/msonline/set-msoluser?view=azureadps-1.0)

[암호 정책에 대 한 추가 정보](https://docs.microsoft.com/azure/active-directory/authentication/concept-sspr-policy#password-policies-that-only-apply-to-cloud-user-accounts)