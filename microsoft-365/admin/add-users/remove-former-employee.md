---
title: 이전 직원 제거 - 개요
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
- SPO_Content
ms.custom:
- MSStore_Link
- TRN_M365B
- OKR_SMB_Videos
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
description: 이 솔루션의 단계에 따라 이전 직원을 제거하고 Microsoft 365 데이터를 보호합니다.
ms.openlocfilehash: 4b4cf59fdce81b3098ee333095daa8e1af1cd5c5
ms.sourcegitcommit: ff20f5b4e3268c7c98a84fb1cbe7db7151596b6d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/06/2021
ms.locfileid: "52241739"
---
# <a name="overview-remove-a-former-employee-and-secure-data"></a><span data-ttu-id="6fea6-103">개요: 이전 직원 및 보안 데이터 제거</span><span class="sxs-lookup"><span data-stu-id="6fea6-103">Overview: Remove a former employee and secure data</span></span>

<span data-ttu-id="6fea6-104">자주 묻는 질문은 "직원이 퇴사할 때 데이터를 보호하고 액세스를 보호하기 위해 어떻게 해야 나요?"입니다.</span><span class="sxs-lookup"><span data-stu-id="6fea6-104">A question we often get is, "What should I do to secure data and protect access when an employee leaves my organization?"</span></span> <span data-ttu-id="6fea6-105">이 문서 시리즈에서는 사용자 Microsoft 365 차단하는 방법, 데이터를 보호하기 위해 취해야 하는 단계 및 다른 직원이 데이터에 액세스할 수 있도록 허용하는 방법에 대해 설명했습니다.</span><span class="sxs-lookup"><span data-stu-id="6fea6-105">This article series explains how to block access to Microsoft 365, the steps you should take to secure your data, and how to allow other employees to access the data.</span></span>

<span data-ttu-id="6fea6-106">직원 제거에 대한 짧은 비디오를 시청합니다.</span><span class="sxs-lookup"><span data-stu-id="6fea6-106">Watch a short video about removing an employee.</span></span> <br><br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE1FOfR] 

<span data-ttu-id="6fea6-107">이 비디오가 도움이 된 경우에는 [소규모 비즈니스와 Microsoft 365를 처음 사용하는 사용자를 위한 전체 교육 시리즈](../../business-video/index.yml)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="6fea6-107">If you found this video helpful, check out the [complete training series for small businesses and those new to Microsoft 365](../../business-video/index.yml).</span></span>

<span data-ttu-id="6fea6-108">직원이 로그인하지 못하게 방지:</span><span class="sxs-lookup"><span data-stu-id="6fea6-108">To prevent an employee from logging in:</span></span>

1. <span data-ttu-id="6fea6-109">관리 센터에서 **사용자** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">활성 사용자</a> 페이지로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="6fea6-109">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Active users</a> page.</span></span>
2. <span data-ttu-id="6fea6-110">사용자 이름 옆의 상자를 선택한 다음 암호 다시 설정을 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="6fea6-110">Select the box next to the user's name, and then select **Reset password**.</span></span>
3. <span data-ttu-id="6fea6-111">새 암호를 입력한 다음 다시 설정을 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="6fea6-111">Enter a new password, and then select **Reset**.</span></span> <span data-ttu-id="6fea6-112">(보내지 않습니다.)</span><span class="sxs-lookup"><span data-stu-id="6fea6-112">(Don't send it to them.)</span></span>
4. <span data-ttu-id="6fea6-113">사용자의 이름을 선택하여 속성 창으로 이동하고 계정 탭에서 로그인 시작 **을 선택합니다.** </span><span class="sxs-lookup"><span data-stu-id="6fea6-113">Select the user's name to go to their properties pane, and on the **Account** tab, select **Initiate sign-out**.</span></span>

> [!NOTE]
> <span data-ttu-id="6fea6-114">전역 관리자가 로그인을 시작해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6fea6-114">You need to be a global administrator to initiate sign-out.</span></span>

<span data-ttu-id="6fea6-115">1시간 이내에 또는 현재 Microsoft 365 페이지에서 나면 다시 로그인하라는 메시지가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="6fea6-115">Within an hour - or after they leave the current Microsoft 365 page they are on - they're prompted to sign in again.</span></span> <span data-ttu-id="6fea6-116">액세스 토큰은 한 시간 동안 양호하기 때문에 시간 표시 막대는 해당 토큰에 남아 있는 시간 및 현재 웹 페이지를 탐색하는지 여부에 따라 결정됩니다.</span><span class="sxs-lookup"><span data-stu-id="6fea6-116">An access token is good for an hour, so the timeline depends on how much time is left on that token, and whether they navigate out of their current webpage.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="6fea6-117">이 솔루션의 단계에 번호를 매기며 정확한 순서를 사용하여 솔루션을 완료할 것은 아니어도 됩니다. 이러한 방식으로 단계를 수행해보는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="6fea6-117">Although we've numbered the steps in this solution and you don't have to complete the solution using the exact order, we do recommend doing the steps this way.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="6fea6-118">시작하기 전에</span><span class="sxs-lookup"><span data-stu-id="6fea6-118">Before you begin</span></span>

<span data-ttu-id="6fea6-119">이 솔루션의 단계를 완료하려면 전역 관리자로 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6fea6-119">You need to be a global administrator to complete the steps in this solution.</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="6fea6-120">**단계**</span><span class="sxs-lookup"><span data-stu-id="6fea6-120">**Step**</span></span> <br/> |<span data-ttu-id="6fea6-121">**이렇게 하는 이유**</span><span class="sxs-lookup"><span data-stu-id="6fea6-121">**Why do this**</span></span> <br/> |
|[<span data-ttu-id="6fea6-122">1단계 - 이전 직원이 로그인하지 못하게 방지하고 Microsoft 365 액세스 차단</span><span class="sxs-lookup"><span data-stu-id="6fea6-122">Step 1 - Prevent a former employee from logging in and block access to Microsoft 365 services</span></span>](remove-former-employee-step-1.md) <br/> |<span data-ttu-id="6fea6-123">이렇게 하면 이전 직원이 로그인하지 못하고 Microsoft 365 액세스하지 못하게 Microsoft 365 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6fea6-123">This blocks your former employee from logging in to Microsoft 365 and prevents the person from accessing Microsoft 365 services.</span></span> <br/> |
|[<span data-ttu-id="6fea6-124">2단계 - 이전 직원 사서함의 내용 저장</span><span class="sxs-lookup"><span data-stu-id="6fea6-124">Step 2 - Save the contents of a former employee's mailbox</span></span>](remove-former-employee-step-2.md) <br/> |<span data-ttu-id="6fea6-125">이 기능은 직원의 작업을 인계할 사람이나 소송이 있는 경우 유용합니다.</span><span class="sxs-lookup"><span data-stu-id="6fea6-125">This is useful for the person who is going to take over the employee's work, or if there is litigation.</span></span> <br/> |
|[<span data-ttu-id="6fea6-126">3단계 - 이전 직원의 전자 메일을 다른 직원에게 전달하거나 공유 사서함으로 변환</span><span class="sxs-lookup"><span data-stu-id="6fea6-126">Step 3 - Forward a former employee's email to another employee or convert to a shared mailbox</span></span>](remove-former-employee-step-3.md) <br/> |<span data-ttu-id="6fea6-p104">이렇게 하면 이전 직원의 전자 메일 주소를 활성 상태로 유지할 수 있습니다. 이전 직원의 주소로 여전히 전자 메일을 보내는 고객 또는 파트너가 있는 경우 업무를 인수하는 사람에게 전자 메일이 전달됩니다.</span><span class="sxs-lookup"><span data-stu-id="6fea6-p104">This lets you keep the former employee's email address active. If you have customers or partners still sending email to the former employee's address, this gets them to the person taking over the work.</span></span> <br/> |
|[<span data-ttu-id="6fea6-129">4단계 - 다른 직원에게 데이터 및 OneDrive 액세스 Outlook 부여</span><span class="sxs-lookup"><span data-stu-id="6fea6-129">Step 4 - Give another employee access to OneDrive and Outlook data</span></span>](remove-former-employee-step-6.md) <br/> |<span data-ttu-id="6fea6-130">사용자의 라이선스만 제거하고 계정을 삭제하지 않으면 30일이 지난 후에도 사용자의 OneDrive에 있는 콘텐츠에 계속 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6fea6-130">If you only remove a user's license but don't delete the account, the content in the user's OneDrive will remain accessible to you even after 30 days.</span></span> <br/><br/> <span data-ttu-id="6fea6-131">계정을 삭제하기 전에 해당 계정에 대한 액세스 권한을 OneDrive Outlook 합니다.</span><span class="sxs-lookup"><span data-stu-id="6fea6-131">Before you delete the account, you should give access of their OneDrive and Outlook to another user.</span></span> <span data-ttu-id="6fea6-132">직원의 계정을 삭제하면 해당 계정 및 OneDrive Outlook **30일** 동안 보존됩니다.</span><span class="sxs-lookup"><span data-stu-id="6fea6-132">After you delete an employee's account, the content in their OneDrive and Outlook is retained for **30** days.</span></span> <span data-ttu-id="6fea6-133">그러나 해당 30일 동안 사용자 계정을 복원하고 해당 콘텐츠에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6fea6-133">During that 30 days, however, you can restore the user's account, and gain access to their content.</span></span> <span data-ttu-id="6fea6-134">사용자 계정을 복원하면 30일이 OneDrive Outlook 콘텐츠에 계속 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6fea6-134">If you restore the user's account, the OneDrive and Outlook content will remain accessible to you even after 30 days.</span></span> <br/> |
|[<span data-ttu-id="6fea6-135">5단계 - 이전 직원의 모바일 장치 지우기 및 차단</span><span class="sxs-lookup"><span data-stu-id="6fea6-135">Step 5 - Wipe and block a former employee's mobile device</span></span>](remove-former-employee-step-4.md) <br/> |<span data-ttu-id="6fea6-136">휴대폰 또는 태블릿에서 비즈니스 데이터를 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="6fea6-136">Removes your business data from the phone or tablet.</span></span>  <br/> |
|[<span data-ttu-id="6fea6-137">6단계 - 이전 직원의 Microsoft 365 라이선스 제거 및 삭제</span><span class="sxs-lookup"><span data-stu-id="6fea6-137">Step 6 - Remove and delete the Microsoft 365 license from a former employee</span></span>](remove-former-employee-step-7.md) <br/> |<span data-ttu-id="6fea6-p106">라이선스를 제거하면 다른 사람에게 해당 라이선스를 할당할 수 있습니다. 또는 다른 사람을 고용할 때까지 라이선스 비용을 지불하지 않도록 라이선스를 삭제할 수 있습니다.  </span><span class="sxs-lookup"><span data-stu-id="6fea6-p106">When you remove a license, you can assign it to someone else. Or, you can delete the license so you don't pay for it until you hire another person. </span></span><br/><br/> <span data-ttu-id="6fea6-p107">라이선스를 제거하거나 삭제하면 사용자의 이전 전자 메일, 연락처 및 일정이 **30일** 간 보존된 후 영구적으로 삭제됩니다. 라이선스를 제거하거나 삭제하되 계정은 삭제하지 않으면 30일이 지난 후에도 사용자의 OneDrive에 있는 콘텐츠에 계속 액세스할 수 있습니다.  </span><span class="sxs-lookup"><span data-stu-id="6fea6-p107">When you remove or delete a license, the user's old email, contacts, and calendar are retained for **30 days**, then permanently deleted. If you remove or delete a license but don't delete the account, the content in the user's OneDrive will remain accessible to you even after 30 days.  </span></span><br/> |
|[<span data-ttu-id="6fea6-142">7단계 - 이전 직원의 사용자 계정 삭제</span><span class="sxs-lookup"><span data-stu-id="6fea6-142">Step 7 - Delete a former employee's user account</span></span>](remove-former-employee-step-7.md) <br/> |<span data-ttu-id="6fea6-143">그러면 관리 센터에서 계정이 제거됩니다.</span><span class="sxs-lookup"><span data-stu-id="6fea6-143">This removes the account from your admin center.</span></span> <span data-ttu-id="6fea6-144">깔끔하게 정리됩니다.</span><span class="sxs-lookup"><span data-stu-id="6fea6-144">Keeps things clean.</span></span> <br/> |

## <a name="related-articles"></a><span data-ttu-id="6fea6-145">관련 문서</span><span class="sxs-lookup"><span data-stu-id="6fea6-145">Related articles</span></span>

[<span data-ttu-id="6fea6-146">사용자 복원</span><span class="sxs-lookup"><span data-stu-id="6fea6-146">Restore a user</span></span>](restore-user.md)
