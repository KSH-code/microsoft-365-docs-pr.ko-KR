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
# <a name="turn-off-strong-password-requirements-for-users"></a><span data-ttu-id="4ee0a-103">사용자에 대 한 강력한 암호 요구 사항 해제</span><span class="sxs-lookup"><span data-stu-id="4ee0a-103">Turn off strong password requirements for users</span></span>

<span data-ttu-id="4ee0a-104">이 문서에서는 사용자에 대해 강력한 암호 요구 사항을 해제 하는 방법에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="4ee0a-104">This article explains how to turn off strong password requirements for your users.</span></span> <span data-ttu-id="4ee0a-105">강력한 암호 요구 사항은 Microsoft 365 for business 조 직에 기본적으로 설정 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4ee0a-105">Strong password requirements are turned on by default in your Microsoft 365 for business organization.</span></span> <span data-ttu-id="4ee0a-106">조직에서 강력한 암호를 사용 하지 않도록 설정 해야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4ee0a-106">Your organization might have requirements to disable strong passwords.</span></span> <span data-ttu-id="4ee0a-107">다음 단계에 따라 강력한 암호 요구 사항을 해제 합니다.</span><span class="sxs-lookup"><span data-stu-id="4ee0a-107">Follow the steps below to turn off strong password requirements.</span></span> <span data-ttu-id="4ee0a-108">PowerShell을 사용 하 여 이러한 단계를 완료 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4ee0a-108">You have to complete these steps using PowerShell.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="4ee0a-109">시작하기 전에</span><span class="sxs-lookup"><span data-stu-id="4ee0a-109">Before you begin</span></span>

<span data-ttu-id="4ee0a-110">이 문서는 회사, 학교 또는 비영리 용 암호 정책을 관리 하는 사용자를 위한 것입니다.</span><span class="sxs-lookup"><span data-stu-id="4ee0a-110">This article is for people who manage password policy for a business, school, or nonprofit.</span></span> <span data-ttu-id="4ee0a-111">이 단계를 완료하려면 Microsoft 365 관리자 계정으로 로그인해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4ee0a-111">To complete these steps, you need to sign in with your Microsoft 365 admin account.</span></span> [<span data-ttu-id="4ee0a-112">관리자 계정 이란?</span><span class="sxs-lookup"><span data-stu-id="4ee0a-112">What's an admin account?</span></span>](../admin-overview/admin-overview.md) <span data-ttu-id="4ee0a-113">이 단계를 수행 하려면 [전역 관리자 또는 암호 관리자](about-admin-roles.md) 여야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4ee0a-113">You must be an [global admin or password administrator](about-admin-roles.md) to perform these steps.</span></span>

<span data-ttu-id="4ee0a-114">또한 PowerShell을 사용 하 여 Microsoft 365에 연결 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4ee0a-114">You must also connect to Microsoft 365 with PowerShell.</span></span>

## <a name="set-strong-passwords"></a><span data-ttu-id="4ee0a-115">강력한 암호 설정</span><span class="sxs-lookup"><span data-stu-id="4ee0a-115">Set strong passwords</span></span>

1. <span data-ttu-id="4ee0a-116">[PowerShell을 사용 하 여 Microsoft 365에 연결](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-office-365-powershell#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell)합니다.</span><span class="sxs-lookup"><span data-stu-id="4ee0a-116">[Connect to Microsoft 365 with PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-office-365-powershell#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell).</span></span>

2. <span data-ttu-id="4ee0a-117">PowerShell을 사용 하 여 다음 명령을 사용 하 여 모든 사용자에 대해 강력한 암호 요구 사항을 해제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4ee0a-117">Using PowerShell, you can turn off strong password requirements for all users with the following command:</span></span>

    ```powershell
    Get-MsolUser | Set-MsolUser -StrongPasswordRequired $false

3. You can turn of strong password requirements for specific users with this command:

    ```powershell
    Set-MsolUser –UserPrincipalName –StrongPasswordRequired  $false
    ```

> [!NOTE]
> <span data-ttu-id="4ee0a-118">UserPrincipalName은 사용자 이름 뒤에 @ 기호와 도메인 이름을 입력 하는 인터넷 스타일 로그인 형식 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4ee0a-118">The userPrincipalName must be in the Internet-style sign-in format where the user name is followed by the at sign (@) and a domain name.</span></span> <span data-ttu-id="4ee0a-119">예: user@contoso.com.</span><span class="sxs-lookup"><span data-stu-id="4ee0a-119">For example: user@contoso.com.</span></span>

## <a name="related-content"></a><span data-ttu-id="4ee0a-120">관련 콘텐츠</span><span class="sxs-lookup"><span data-stu-id="4ee0a-120">Related content</span></span>

[<span data-ttu-id="4ee0a-121">PowerShell을 사용 하 여 Microsoft 365에 연결 하는 방법</span><span class="sxs-lookup"><span data-stu-id="4ee0a-121">How to connect to Microsoft 365 with PowerShell</span></span>](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-office-365-powershell#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell)

[<span data-ttu-id="4ee0a-122">PowerShell Get-msoluser 명령에 대 한 추가 정보</span><span class="sxs-lookup"><span data-stu-id="4ee0a-122">More information on PowerShell MsolUser commands</span></span>](https://docs.microsoft.com/powershell/module/msonline/set-msoluser?view=azureadps-1.0)

[<span data-ttu-id="4ee0a-123">암호 정책에 대 한 추가 정보</span><span class="sxs-lookup"><span data-stu-id="4ee0a-123">More information on password policy</span></span>](https://docs.microsoft.com/azure/active-directory/authentication/concept-sspr-policy#password-policies-that-only-apply-to-cloud-user-accounts)