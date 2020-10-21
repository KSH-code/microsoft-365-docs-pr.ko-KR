---
title: 사용자에 대 한 강력한 암호 요구 사항 설정
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
ms.openlocfilehash: 1634e2f0de2cdd2cac5e1928adbef54457e50716
ms.sourcegitcommit: e17fd18b01d70e6428263c20cbce4b92e2a97765
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/20/2020
ms.locfileid: "48626146"
---
# <a name="set-strong-password-requirement-for-users"></a><span data-ttu-id="38c84-103">사용자에 대 한 강력한 암호 요구 사항 설정</span><span class="sxs-lookup"><span data-stu-id="38c84-103">Set strong password requirement for users</span></span>

<span data-ttu-id="38c84-104">이 문서에서는 사용자에 게 강력한 암호 요구 사항을 설정 하는 방법에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="38c84-104">This article explains how to set strong password requirements for your users.</span></span> <span data-ttu-id="38c84-105">PowerShell을 사용 하 여 이러한 단계를 완료 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="38c84-105">You have to complete these steps using PowerShell.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="38c84-106">시작하기 전에</span><span class="sxs-lookup"><span data-stu-id="38c84-106">Before you begin</span></span>

<span data-ttu-id="38c84-107">이 문서는 회사, 학교 또는 비영리 용 암호 정책을 관리 하는 사용자를 위한 것입니다.</span><span class="sxs-lookup"><span data-stu-id="38c84-107">This article is for people who manage password policy for a business, school, or nonprofit.</span></span> <span data-ttu-id="38c84-108">이 단계를 완료하려면 Microsoft 365 관리자 계정으로 로그인해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="38c84-108">To complete these steps, you need to sign in with your Microsoft 365 admin account.</span></span> <span data-ttu-id="38c84-109">[관리자 계정의 새로운 기능](../admin-overview/admin-overview.md)</span><span class="sxs-lookup"><span data-stu-id="38c84-109">[What's an admin account?](../admin-overview/admin-overview.md).</span></span> <span data-ttu-id="38c84-110">이 단계를 수행 하려면 [전역 관리자 또는 암호 관리자](about-admin-roles.md) 여야 합니다.</span><span class="sxs-lookup"><span data-stu-id="38c84-110">You must be an [global admin or password administrator](about-admin-roles.md) to perform these steps.</span></span>

<span data-ttu-id="38c84-111">또한 PowerShell을 사용 하 여 Microsoft 365에 연결 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="38c84-111">You must also connect to Microsoft 365 with PowerShell.</span></span>

## <a name="set-strong-passwords"></a><span data-ttu-id="38c84-112">강력한 암호 설정</span><span class="sxs-lookup"><span data-stu-id="38c84-112">Set strong passwords</span></span>

1. <span data-ttu-id="38c84-113">[PowerShell을 사용 하 여 Microsoft 365에 연결](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-office-365-powershell#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell)합니다.</span><span class="sxs-lookup"><span data-stu-id="38c84-113">[Connect to Microsoft 365 with PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-office-365-powershell#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell).</span></span>

2. <span data-ttu-id="38c84-114">PowerShell을 사용 하 여 다음 명령을 사용 하 여 모든 사용자에 대해 강력한 암호 요구 사항을 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="38c84-114">Using PowerShell, you can turn on strong password requirements for all users with the following command:</span></span>

    ```powershell
    Get-MsolUser | Set-MsolUser -StrongPasswordRequired $true

3. You can turn on strong password requirements for specific users with this command:

    ```powershell
    Set-MsolUser –UserPrincipalName –StrongPasswordRequired  $true
    ```

> [!NOTE]
> <span data-ttu-id="38c84-115">UserPrincipalName은 사용자 이름 뒤에 @ 기호와 도메인 이름을 입력 하는 인터넷 스타일 로그인 형식 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="38c84-115">The userPrincipalName must be in the Internet-style sign-in format where the user name is followed by the at sign (@) and a domain name.</span></span> <span data-ttu-id="38c84-116">예: user@contoso.com.</span><span class="sxs-lookup"><span data-stu-id="38c84-116">For example: user@contoso.com.</span></span>

## <a name="related-content"></a><span data-ttu-id="38c84-117">관련 콘텐츠</span><span class="sxs-lookup"><span data-stu-id="38c84-117">Related content</span></span>

[<span data-ttu-id="38c84-118">PowerShell을 사용 하 여 Microsoft 365에 연결 하는 방법</span><span class="sxs-lookup"><span data-stu-id="38c84-118">How to connect to Microsoft 365 with PowerShell</span></span>](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-office-365-powershell#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell)

[<span data-ttu-id="38c84-119">PowerShell Get-msoluser 명령에 대 한 추가 정보</span><span class="sxs-lookup"><span data-stu-id="38c84-119">More information on PowerShell MsolUser commands</span></span>](https://docs.microsoft.com/powershell/module/msonline/set-msoluser?view=azureadps-1.0)

[<span data-ttu-id="38c84-120">암호 정책에 대 한 추가 정보</span><span class="sxs-lookup"><span data-stu-id="38c84-120">More information on password policy</span></span>](https://docs.microsoft.com/azure/active-directory/authentication/concept-sspr-policy#password-policies-that-only-apply-to-cloud-user-accounts)