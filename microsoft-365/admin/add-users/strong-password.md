---
title: 사용자에 대한 강력한 암호 요구 사항 끄기
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
description: 사용자에 대해 강력한 암호 요구 사항을 설정하는 방법을 Windows PowerShell.
ms.openlocfilehash: 898eaf30d813e883e88c3ccc8ff500d72ae72854
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/08/2021
ms.locfileid: "52840661"
---
# <a name="turn-off-strong-password-requirements-for-users"></a><span data-ttu-id="c42dc-103">사용자에 대한 강력한 암호 요구 사항 끄기</span><span class="sxs-lookup"><span data-stu-id="c42dc-103">Turn off strong password requirements for users</span></span>

<span data-ttu-id="c42dc-104">이 문서에서는 사용자에 대한 강력한 암호 요구 사항을 해제하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="c42dc-104">This article explains how to turn off strong password requirements for your users.</span></span> <span data-ttu-id="c42dc-105">강력한 암호 요구 사항은 비즈니스 조직에 대한 Microsoft 365 설정되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c42dc-105">Strong password requirements are turned on by default in your Microsoft 365 for business organization.</span></span> <span data-ttu-id="c42dc-106">조직에서 강력한 암호를 사용하지 않도록 설정해야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c42dc-106">Your organization might have requirements to disable strong passwords.</span></span> <span data-ttu-id="c42dc-107">다음 단계에 따라 강력한 암호 요구 사항을 끄세요.</span><span class="sxs-lookup"><span data-stu-id="c42dc-107">Follow the steps below to turn off strong password requirements.</span></span> <span data-ttu-id="c42dc-108">PowerShell을 사용하여 이러한 단계를 완료해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c42dc-108">You have to complete these steps using PowerShell.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="c42dc-109">시작하기 전에</span><span class="sxs-lookup"><span data-stu-id="c42dc-109">Before you begin</span></span>

<span data-ttu-id="c42dc-110">이 문서는 비즈니스, 학교 또는 비영리용 암호 정책을 관리하는 사용자용입니다.</span><span class="sxs-lookup"><span data-stu-id="c42dc-110">This article is for people who manage password policy for a business, school, or nonprofit.</span></span> <span data-ttu-id="c42dc-111">이 단계를 완료하려면 Microsoft 365 관리자 계정으로 로그인해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c42dc-111">To complete these steps, you need to sign in with your Microsoft 365 admin account.</span></span> [<span data-ttu-id="c42dc-112">관리자 계정이란?</span><span class="sxs-lookup"><span data-stu-id="c42dc-112">What's an admin account?</span></span>](/microsoft-365/business-video/admin-center-overview) <span data-ttu-id="c42dc-113">이러한 단계를 [수행하려면](about-admin-roles.md) 전역 관리자 또는 암호 관리자 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c42dc-113">You must be an [global admin or password administrator](about-admin-roles.md) to perform these steps.</span></span>

<span data-ttu-id="c42dc-114">PowerShell을 사용하여 Microsoft 365 연결해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c42dc-114">You must also connect to Microsoft 365 with PowerShell.</span></span>

## <a name="set-strong-passwords"></a><span data-ttu-id="c42dc-115">강력한 암호 설정</span><span class="sxs-lookup"><span data-stu-id="c42dc-115">Set strong passwords</span></span>

1. <span data-ttu-id="c42dc-116">[커넥트 Microsoft 365 를 사용할 수 있습니다.](/office365/enterprise/powershell/connect-to-office-365-powershell#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell)</span><span class="sxs-lookup"><span data-stu-id="c42dc-116">[Connect to Microsoft 365 with PowerShell](/office365/enterprise/powershell/connect-to-office-365-powershell#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell).</span></span>

2. <span data-ttu-id="c42dc-117">PowerShell을 사용하여 다음 명령을 사용하여 모든 사용자에 대해 강력한 암호 요구 사항을 해제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c42dc-117">Using PowerShell, you can turn off strong password requirements for all users with the following command:</span></span>

    ```powershell
    Get-MsolUser | Set-MsolUser -StrongPasswordRequired $false

3. You can turn of strong password requirements for specific users with this command:

    ```powershell
    Set-MsolUser –UserPrincipalName –StrongPasswordRequired  $false
    ```

> [!NOTE]
> <span data-ttu-id="c42dc-118">userPrincipalName은 사용자 이름이 이어지고 기호(@) 및 도메인 이름이 이어지는 인터넷 스타일 로그인 형식이 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c42dc-118">The userPrincipalName must be in the Internet-style sign-in format where the user name is followed by the at sign (@) and a domain name.</span></span> <span data-ttu-id="c42dc-119">예: user@contoso.com.</span><span class="sxs-lookup"><span data-stu-id="c42dc-119">For example: user@contoso.com.</span></span>

## <a name="related-content"></a><span data-ttu-id="c42dc-120">관련 콘텐츠</span><span class="sxs-lookup"><span data-stu-id="c42dc-120">Related content</span></span>

[<span data-ttu-id="c42dc-121">PowerShell을 사용하여 Microsoft 365 방법</span><span class="sxs-lookup"><span data-stu-id="c42dc-121">How to connect to Microsoft 365 with PowerShell</span></span>](/office365/enterprise/powershell/connect-to-office-365-powershell#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell)

[<span data-ttu-id="c42dc-122">PowerShell MsolUser 명령에 대한 자세한 정보</span><span class="sxs-lookup"><span data-stu-id="c42dc-122">More information on PowerShell MsolUser commands</span></span>](/powershell/module/msonline/set-msoluser?view=azureadps-1.0)

[<span data-ttu-id="c42dc-123">암호 정책에 대한 자세한 정보</span><span class="sxs-lookup"><span data-stu-id="c42dc-123">More information on password policy</span></span>](/azure/active-directory/authentication/concept-sspr-policy#password-policies-that-only-apply-to-cloud-user-accounts)