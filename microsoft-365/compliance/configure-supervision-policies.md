---
title: 감독 정책 구성
description: Office 365에 대 한 통신 감독 구성
f1.keywords:
- NOCSH
ms.author: robmazz
author: robmazz
manager: laurawi
audience: Admin
ms.topic: article
f1_keywords:
- ms.o365.cc.SupervisoryReview
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- Strat_O365_IP
- M365-security-compliance
search.appverid:
- MET150
- MOE150
titleSuffix: Office 365 Compliance
ms.openlocfilehash: d0bd5411e99471ff326906f65747ec7a6f841545
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/29/2020
ms.locfileid: "41596205"
---
# <a name="configure-supervision-policies-in-office-365"></a><span data-ttu-id="fefb0-103">Office 365에서 감독 정책 구성</span><span class="sxs-lookup"><span data-stu-id="fefb0-103">Configure supervision policies in Office 365</span></span>

>[!IMPORTANT]
><span data-ttu-id="fefb0-104">이 항목은 Office 365 구독에서 감독 정책 구성에 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="fefb0-104">This topic applies to configuring supervision policies in an Office 365 subscription.</span></span> <span data-ttu-id="fefb0-105">Microsoft 365 구독에 대 한 통신 준수를 구성 하려면 [configure communications 준수 In microsoft 365 (preview)](communication-compliance-configure.md)을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="fefb0-105">If you want to configure communications compliance for a Microsoft 365 subscription, see [Configure communications compliance in Microsoft 365 (preview)](communication-compliance-configure.md).</span></span>

<span data-ttu-id="fefb0-106">감독 정책을 사용 하 여 내부 또는 외부 검토자가 검사할 직원 통신을 캡처할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fefb0-106">Use supervision policies to capture employee communications for examination by internal or external reviewers.</span></span> <span data-ttu-id="fefb0-107">감독 정책을 통해 조직의 통신을 모니터링 하는 방법에 대 한 자세한 내용은 [Office 365의 감독 정책을](supervision-policies.md)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="fefb0-107">For more information about how supervision policies can help you monitor communications in your organization, see [Supervision policies in Office 365](supervision-policies.md).</span></span>

>[!NOTE]
><span data-ttu-id="fefb0-108">감독 정책에 따라 모니터링 되는 사용자에 게는 Microsoft 365 E5 규정 준수 라이선스, 고급 준수 추가 기능이 포함 된 Office 365 Enterprise E3 라이선스 또는 Office 365 Enterprise E5 구독에 포함 되어 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="fefb0-108">Users monitored by supervision policies must have either a Microsoft 365 E5 Compliance license, an Office 365 Enterprise E3 license with the Advanced Compliance add-on, or be included in an Office 365 Enterprise E5 subscription.</span></span>
><span data-ttu-id="fefb0-109">기존 Enterprise E5 요금제가 없고, 감독을 려 고 하는 경우 [Office 365 Enterprise e 5의 평가판에 등록할](https://go.microsoft.com/fwlink/p/?LinkID=698279)수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fefb0-109">If you don't have an existing Enterprise E5 plan and want to try supervision, you can [sign up for a trial of Office 365 Enterprise E5](https://go.microsoft.com/fwlink/p/?LinkID=698279).</span></span>
  
<span data-ttu-id="fefb0-110">Office 365 조직에서 감독을 설정 및 사용 하려면 다음 단계를 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="fefb0-110">Follow these steps to set up and use supervision in your Office 365 organization:</span></span>
  
- <span data-ttu-id="fefb0-111">**1 단계 (옵션)**: [감독을 위한 그룹 설정](#step-1-set-up-groups-for-supervision-optional)</span><span class="sxs-lookup"><span data-stu-id="fefb0-111">**Step 1 (optional)**: [Set up groups for supervision](#step-1-set-up-groups-for-supervision-optional)</span></span>

    <span data-ttu-id="fefb0-112">감독 정책을 사용 하기 전에 의사 소통을 검토 하 고 검토를 수행 해야 하는 사람을 결정 합니다.</span><span class="sxs-lookup"><span data-stu-id="fefb0-112">Before you start using supervision policies, determine who needs communications reviewed and who performs reviews.</span></span> <span data-ttu-id="fefb0-113">소수의 사용자만을 시작 하 여 감독의 작동 방식을 확인 하려는 경우 지금 그룹 설정 건너뛰기를 건너뛸 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fefb0-113">If you want to get started with just a few users to see how supervision works, you can skip setting up groups for now.</span></span>

- <span data-ttu-id="fefb0-114">**2 단계 (필수 사항)**: [조직에서 감독을 사용할 수 있도록 설정](#step-2-make-supervision-available-in-your-organization-required)</span><span class="sxs-lookup"><span data-stu-id="fefb0-114">**Step 2 (required)**: [Make supervision available in your organization](#step-2-make-supervision-available-in-your-organization-required)</span></span>

    <span data-ttu-id="fefb0-115">정책을 설정할 수 있도록 자신을 관리 검토 역할 그룹에 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="fefb0-115">Add yourself to the Supervisory Review role group so you can set up policies.</span></span> <span data-ttu-id="fefb0-116">이 역할이 할당 된 사용자는 Office 365 보안 및 준수 센터의 **감독** 페이지에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fefb0-116">Anyone who has this role assigned can access the **Supervision** page in the Office 365 security and compliance center.</span></span> <span data-ttu-id="fefb0-117">다시 볼 수 있는 전자 메일이 Exchange Online에서 호스팅되는 경우 각 검토자 [에 게 Exchange online에 대 한 원격 PowerShell 액세스](https://docs.microsoft.com/powershell/exchange/exchange-online/disable-access-to-exchange-online-powershell)권한이 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="fefb0-117">If reviewable email is hosted on Exchange Online, each reviewer must have [remote PowerShell access to Exchange Online](https://docs.microsoft.com/powershell/exchange/exchange-online/disable-access-to-exchange-online-powershell).</span></span>

- <span data-ttu-id="fefb0-118">**3 단계 (선택 사항)**: [사용자 지정 중요 한 정보 유형 및 사용자 지정 키워드 사전 만들기](#step-3-create-custom-sensitive-information-types-and-custom-keyword-dictionaries-optional)</span><span class="sxs-lookup"><span data-stu-id="fefb0-118">**Step 3 (optional)**: [Create custom sensitive information types and custom keyword dictionaries](#step-3-create-custom-sensitive-information-types-and-custom-keyword-dictionaries-optional)</span></span>

    <span data-ttu-id="fefb0-119">감독 정책에 대 한 사용자 지정 중요 한 정보 유형 또는 사용자 지정 키워드 사전이 필요한 경우에는 감독 마법사를 시작 하기 전에 만들어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="fefb0-119">If you need a custom sensitive info type or a custom keyword dictionary for your supervision policy, you need to create it before starting the supervision wizard.</span></span>

- <span data-ttu-id="fefb0-120">**4 단계 (필수 사항)**: [감독 정책 설정](#step-4-set-up-a-supervision-policy-required)</span><span class="sxs-lookup"><span data-stu-id="fefb0-120">**Step 4 (required)**: [Set up a supervision policy](#step-4-set-up-a-supervision-policy-required)</span></span>

    <span data-ttu-id="fefb0-121">Office 365 보안 및 준수 센터에서 감독 정책을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="fefb0-121">You create supervision policies in the Office 365 security and compliance center.</span></span> <span data-ttu-id="fefb0-122">이러한 정책은 조직에서 검토할 대상이 되는 통신을 정의 하 고 검토를 수행 하는 사람을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="fefb0-122">These policies define which communications are subject to review in your organization and specifies who performs reviews.</span></span> <span data-ttu-id="fefb0-123">통신에는 전자 메일 및 Microsoft 팀 통신과 타사 플랫폼 통신 (예: Facebook, Twitter 등)이 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="fefb0-123">Communications include email and Microsoft Teams communications, and 3rd-party platform communications (such as Facebook, Twitter, etc.).</span></span> <span data-ttu-id="fefb0-124">Microsoft 365 구독의 통신 감독에서는 Office 365 조 직에서 만든 감독 정책이 지원 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="fefb0-124">Supervision policies created in Office 365 organizations are not supported in communication supervision in Microsoft 365 subscriptions.</span></span>

- <span data-ttu-id="fefb0-125">**5 단계 (선택 사항)**: [통신 감독 정책 테스트](#step-5-test-your-supervision-policy-optional)</span><span class="sxs-lookup"><span data-stu-id="fefb0-125">**Step 5 (optional)**: [Test your communication supervision policy](#step-5-test-your-supervision-policy-optional)</span></span>

    <span data-ttu-id="fefb0-126">감독 정책을 테스트 하 여 원하는 대로 작동 하는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="fefb0-126">Test your supervision policy to make sure it functions as desired.</span></span> <span data-ttu-id="fefb0-127">규정 준수 전략이 표준을 충족 하는지 확인 하는 것이 중요 합니다.</span><span class="sxs-lookup"><span data-stu-id="fefb0-127">It is important to ensure that your compliance strategy is meeting your standards.</span></span>

## <a name="step-1-set-up-groups-for-supervision-optional"></a><span data-ttu-id="fefb0-128">1 단계: 감독에 대 한 그룹 설정 (선택 사항)</span><span class="sxs-lookup"><span data-stu-id="fefb0-128">Step 1: Set up groups for supervision (optional)</span></span>

 <span data-ttu-id="fefb0-129">감독 정책을 만들 때는 통신을 검사 하 고 검토를 수행 하는 사람을 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="fefb0-129">When you create a supervision policy, you define who has their communications scanned and who performs reviews.</span></span> <span data-ttu-id="fefb0-130">정책에서는 전자 메일 주소를 사용 하 여 개인 이나 사용자 그룹을 식별 합니다.</span><span class="sxs-lookup"><span data-stu-id="fefb0-130">In the policy, you'll use email addresses to identify individuals or groups of people.</span></span> <span data-ttu-id="fefb0-131">설정을 간소화 하기 위해 통신을 검토 하는 사용자를 위해 통신이 검색 되 고 그룹이 있는 사용자를 위해 그룹을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fefb0-131">To simplify your setup, you can create groups for people who have their communication scanned and groups for people who review those communications.</span></span> <span data-ttu-id="fefb0-132">그룹을 사용 하는 경우 몇 가지 필요할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fefb0-132">If you're using groups, you may need several.</span></span> <span data-ttu-id="fefb0-133">예를 들어 서로 다른 두 사용자 그룹 간의 통신을 모니터링 하거나 감독 하지 않을 그룹을 지정 하려는 경우</span><span class="sxs-lookup"><span data-stu-id="fefb0-133">For example, you want to monitor communications between two distinct groups of people or if you want to specify a group that isn't going to be supervised.</span></span>

<span data-ttu-id="fefb0-134">다음 차트를 사용 하 여 통신 감독 정책에 맞게 조직의 그룹을 구성 하는 데 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="fefb0-134">Use the following chart to help you configure groups in your organization for communication supervision policies:</span></span>

| <span data-ttu-id="fefb0-135">**정책 구성원**</span><span class="sxs-lookup"><span data-stu-id="fefb0-135">**Policy Member**</span></span> | <span data-ttu-id="fefb0-136">**지원 되는 그룹**</span><span class="sxs-lookup"><span data-stu-id="fefb0-136">**Supported Groups**</span></span> | <span data-ttu-id="fefb0-137">**지원 되지 않는 그룹**</span><span class="sxs-lookup"><span data-stu-id="fefb0-137">**Unsupported Groups**</span></span> |
|:-----|:-----|:-----|
|<span data-ttu-id="fefb0-138">감독 사용자</span><span class="sxs-lookup"><span data-stu-id="fefb0-138">Supervised users</span></span> <br> <span data-ttu-id="fefb0-139">감독 되지 않은 사용자</span><span class="sxs-lookup"><span data-stu-id="fefb0-139">Non-supervised users</span></span> | <span data-ttu-id="fefb0-140">메일 그룹</span><span class="sxs-lookup"><span data-stu-id="fefb0-140">Distribution groups</span></span> <br> <span data-ttu-id="fefb0-141">Office 365 그룹</span><span class="sxs-lookup"><span data-stu-id="fefb0-141">Office 365 groups</span></span> | <span data-ttu-id="fefb0-142">동적 메일 그룹</span><span class="sxs-lookup"><span data-stu-id="fefb0-142">Dynamic distribution groups</span></span> |
| <span data-ttu-id="fefb0-143">가</span><span class="sxs-lookup"><span data-stu-id="fefb0-143">Reviewers</span></span> | <span data-ttu-id="fefb0-144">메일 사용 가능 보안 그룹</span><span class="sxs-lookup"><span data-stu-id="fefb0-144">Mail-enabled security groups</span></span>  | <span data-ttu-id="fefb0-145">메일 그룹</span><span class="sxs-lookup"><span data-stu-id="fefb0-145">Distribution groups</span></span> <br> <span data-ttu-id="fefb0-146">동적 메일 그룹</span><span class="sxs-lookup"><span data-stu-id="fefb0-146">Dynamic distribution groups</span></span> |
  
<span data-ttu-id="fefb0-147">감독 되는 사용자에 대 한 Office 365 그룹을 선택 하면 정책이 공유 Office 365 사서함의 콘텐츠 및 해당 그룹과 연결 된 Microsoft 팀 채널을 모니터링 합니다.</span><span class="sxs-lookup"><span data-stu-id="fefb0-147">When you select an Office 365 group for supervised users, the policy monitors the content of the shared Office 365 mailbox and the Microsoft Teams channels associated with the group.</span></span> <span data-ttu-id="fefb0-148">메일 그룹을 선택 하는 경우 정책은 개별 사용자 사서함을 모니터링 합니다.</span><span class="sxs-lookup"><span data-stu-id="fefb0-148">When you select a distribution list, the policy monitors individual user mailboxes.</span></span>

<span data-ttu-id="fefb0-149">대규모 엔터프라이즈 조직에서 감독 사용자를 관리 하려면 대규모 그룹의 모든 사용자를 모니터링 해야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fefb0-149">To manage supervised users in large enterprise organizations, you may need to monitor all users across large groups.</span></span> <span data-ttu-id="fefb0-150">PowerShell을 사용 하 여 할당 된 그룹에 대 한 전역 감독 정책에 대 한 메일 그룹을 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fefb0-150">You can use PowerShell to configure a distribution group for a global supervision policy for the assigned group.</span></span> <span data-ttu-id="fefb0-151">이를 통해 단일 정책을 사용 하는 수천 명의 사용자를 모니터링 하 고 조직에 새 직원이 참가할 때 감독 정책을 업데이트할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fefb0-151">This enables you to monitor thousands of users with a single policy and keep the supervision policy updated as new employees join your organization.</span></span>

1. <span data-ttu-id="fefb0-152">다음 속성을 사용 하 여 전역 감독 정책에 대 한 전용 [메일 그룹](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/new-distributiongroup?view=exchange-ps) 을 만듭니다 .이 메일 그룹이 다른 목적이 나 기타 Office 365 서비스에 사용 되지 않는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="fefb0-152">Create a dedicated [distribution group](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/new-distributiongroup?view=exchange-ps) for your global supervision policy with the following properties: Make sure that this distribution group isn't used for other purposes or other Office 365 services.</span></span>

    - <span data-ttu-id="fefb0-153">**MemberDepartRestriction = 닫힘**</span><span class="sxs-lookup"><span data-stu-id="fefb0-153">**MemberDepartRestriction = Closed**.</span></span> <span data-ttu-id="fefb0-154">사용자가 메일 그룹에서 자신을 제거할 수 없도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="fefb0-154">Ensures that users cannot remove themselves from the distribution group.</span></span>
    - <span data-ttu-id="fefb0-155">**Memberjoinrestriction = 닫힘**</span><span class="sxs-lookup"><span data-stu-id="fefb0-155">**MemberJoinRestriction = Closed**.</span></span> <span data-ttu-id="fefb0-156">사용자가 메일 그룹에 자신을 추가할 수 없도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="fefb0-156">Ensures that users cannot add themselves to the distribution group.</span></span>
    - <span data-ttu-id="fefb0-157">**ModerationEnabled = True**</span><span class="sxs-lookup"><span data-stu-id="fefb0-157">**ModerationEnabled = True**.</span></span> <span data-ttu-id="fefb0-158">이 그룹으로 전송 되는 모든 메시지에 대 한 승인이 가능 하며, 해당 그룹이 감독 정책 구성 외부에서 통신 하는 데 사용 되 고 있지는 않은지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="fefb0-158">Ensures that all messages sent to this group are subject to approval and that the group is not being used to communicate outside of the supervision policy configuration.</span></span>

    ```PowerShell
    New-DistributionGroup -Name <your group name> -Alias <your group alias> -MemberDepartRestriction 'Closed' -MemberJoinRestriction 'Closed' -ModerationEnabled $true
    ```

2. <span data-ttu-id="fefb0-159">조직의 감독 정책에 추가한 사용자를 추적 하려면 사용 되지 않는 [Exchange 사용자 지정 특성](https://docs.microsoft.com/Exchange/recipients/mailbox-custom-attributes?view=exchserver-2019&viewFallbackFrom=exchonline-ww) 을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="fefb0-159">Select an unused [Exchange custom attribute](https://docs.microsoft.com/Exchange/recipients/mailbox-custom-attributes?view=exchserver-2019&viewFallbackFrom=exchonline-ww) to track users added to the supervision policy in your organization.</span></span>

3. <span data-ttu-id="fefb0-160">다음 PowerShell 스크립트를 반복 된 일정에 따라 실행 하 여 감독 정책에 사용자를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="fefb0-160">Run the following PowerShell script on a recurring schedule to add users to the supervision policy:</span></span>

    ```PowerShell
    $Mbx = (Get-Mailbox -RecipientTypeDetails UserMailbox -ResultSize Unlimited -Filter {CustomAttribute9 -eq $Null})
    $i = 0
    ForEach ($M in $Mbx) 
    {
      Write-Host "Adding" $M.DisplayName
      Add-DistributionGroupMember -Identity <your group name> -Member $M.DistinguishedName -ErrorAction SilentlyContinue
      Set-Mailbox -Identity $M.Alias -<your custom attribute name> SRAdded 
      $i++
    }
    Write-Host $i "Mailboxes added to supervisory review distribution group."
    ```

<span data-ttu-id="fefb0-161">그룹을 설정 하는 방법에 대 한 자세한 내용은 다음을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="fefb0-161">For more information about setting up groups, see:</span></span>

- [<span data-ttu-id="fefb0-162">메일 그룹 만들기 및 관리</span><span class="sxs-lookup"><span data-stu-id="fefb0-162">Create and manage distribution groups</span></span>](https://docs.microsoft.com/Exchange/recipients-in-exchange-online/manage-distribution-groups/manage-distribution-groups)
- [<span data-ttu-id="fefb0-163">메일 사용 가능 보안 그룹 관리</span><span class="sxs-lookup"><span data-stu-id="fefb0-163">Manage mail-enabled security groups</span></span>](https://docs.microsoft.com/Exchange/recipients-in-exchange-online/manage-mail-enabled-security-groups)
- [<span data-ttu-id="fefb0-164">Office 365 그룹 개요</span><span class="sxs-lookup"><span data-stu-id="fefb0-164">Overview of Office 365 Groups</span></span>](https://docs.microsoft.com/office365/admin/create-groups/office-365-groups?view=o365-worldwide)

## <a name="step-2-make-supervision-available-in-your-organization-required"></a><span data-ttu-id="fefb0-165">2 단계: 조직에서 감독을 사용할 수 있도록 설정 (필수)</span><span class="sxs-lookup"><span data-stu-id="fefb0-165">Step 2: Make supervision available in your organization (required)</span></span>

<span data-ttu-id="fefb0-166">Office 365 보안 및 준수 센터에서 **감독** 을 메뉴 옵션으로 사용 하도록 설정 하려면 관리 검토 관리자 역할이 할당 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="fefb0-166">To make **Supervision** available as a menu option in Office 365 security and compliance center, you must be assigned the Supervisory Review Administrator role.</span></span>
  
<span data-ttu-id="fefb0-167">이렇게 하려면 자신을 관리 검토 역할 그룹의 구성원으로 추가 하거나 역할 그룹을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fefb0-167">To do this, you can either add yourself as a member of the Supervisory Review role group, or you can create a role group.</span></span>
  
### <a name="add-members-to-the-supervisory-review-role-group"></a><span data-ttu-id="fefb0-168">관리 검토 역할 그룹에 구성원 추가</span><span class="sxs-lookup"><span data-stu-id="fefb0-168">Add members to the Supervisory Review role group</span></span>

1. <span data-ttu-id="fefb0-169">Office 365 [https://protection.office.com](https://protection.office.com) 조직의 관리자 계정에 대 한 자격 증명을 사용 하 여 로그인 합니다.</span><span class="sxs-lookup"><span data-stu-id="fefb0-169">Sign into [https://protection.office.com](https://protection.office.com) using credentials for an admin account in your Office 365 organization.</span></span>

2. <span data-ttu-id="fefb0-170">Office 365 보안 및 준수 센터에서 **사용 권한**으로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="fefb0-170">In the Office 365 security and compliance center, go to **Permissions**.</span></span>

3. <span data-ttu-id="fefb0-171">**관리 검토** 역할 그룹을 선택한 다음 편집 아이콘을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="fefb0-171">Select the **Supervisory Review** role group and then click the Edit icon.</span></span>

4. <span data-ttu-id="fefb0-172">**구성원** 섹션에서 조직에 대 한 통신 감독을 관리 하려는 사용자를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="fefb0-172">In the **Members** section, add the people who you want to manage communication supervision for your organization.</span></span>

### <a name="create-a-new-role-group"></a><span data-ttu-id="fefb0-173">새 역할 그룹 만들기</span><span class="sxs-lookup"><span data-stu-id="fefb0-173">Create a new role group</span></span>

1. <span data-ttu-id="fefb0-174">Office 365 [https://protection.office.com/permissions](https://protection.office.com/permissions) 조직의 관리자 계정에 대 한 자격 증명을 사용 하 여 로그인 합니다.</span><span class="sxs-lookup"><span data-stu-id="fefb0-174">Sign into [https://protection.office.com/permissions](https://protection.office.com/permissions) using credentials for an admin account in your Office 365 organization.</span></span>

2. <span data-ttu-id="fefb0-175">Office 365 보안 및 준수 센터에서 **사용 권한** 으로 이동한 다음 추가 (**+**)를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="fefb0-175">In the Office 365 security and compliance center, go to **Permissions** and then click Add (**+**).</span></span>

3. <span data-ttu-id="fefb0-176">**역할** 섹션에서 추가 (**+**)를 클릭 하 고 아래로 스크롤하여 **관리 검토 관리자**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="fefb0-176">In the **Roles** section, click Add (**+**) and scroll down to **Supervisory Review Administrator**.</span></span> <span data-ttu-id="fefb0-177">이 역할을 역할 그룹에 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="fefb0-177">Add this role to the role group.</span></span>

4. <span data-ttu-id="fefb0-178">**구성원** 섹션에서 조직에 대 한 통신 감독을 관리 하려는 사용자를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="fefb0-178">In the **Members** section, add the people who you want to manage communication supervision for your organization.</span></span>

<span data-ttu-id="fefb0-179">역할 그룹 및 사용 권한에 대 한 자세한 내용은 [준수 센터의 사용 권한을](../security/office-365-security/permissions-in-the-security-and-compliance-center.md)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="fefb0-179">For more information about role groups and permissions, see [Permissions in the Compliance Center](../security/office-365-security/permissions-in-the-security-and-compliance-center.md).</span></span>

### <a name="enable-remote-powershell-access-for-reviewers-if-email-is-hosted-on-exchange-online"></a><span data-ttu-id="fefb0-180">검토자에 대해 원격 PowerShell 액세스 사용 (전자 메일이 Exchange Online에서 호스트 되는 경우)</span><span class="sxs-lookup"><span data-stu-id="fefb0-180">Enable remote PowerShell access for reviewers (if email is hosted on Exchange Online)</span></span>

1. <span data-ttu-id="fefb0-181">[사용 또는 사용 안 함 Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/disable-access-to-exchange-online-powershell)에 대 한 지침을 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="fefb0-181">Follow the guidance in [Enable or disable access to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/disable-access-to-exchange-online-powershell).</span></span>

## <a name="step-3-create-custom-sensitive-information-types-and-custom-keyword-dictionaries-optional"></a><span data-ttu-id="fefb0-182">3 단계: 사용자 지정 중요 한 정보 유형 및 사용자 지정 키워드 사전 만들기 (선택 사항)</span><span class="sxs-lookup"><span data-stu-id="fefb0-182">Step 3: Create custom sensitive information types and custom keyword dictionaries (optional)</span></span>

<span data-ttu-id="fefb0-183">감독 정책 마법사에서 기존 사용자 지정 중요 한 정보 유형 또는 사용자 지정 키워드 사전을 선택 하려면 먼저 필요한 경우 이러한 항목을 만들어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="fefb0-183">In order to pick from existing custom sensitive information types or custom keyword dictionaries in the supervision policy wizard, you first need to create these items if needed.</span></span>

### <a name="create-custom-keyword-dictionarylexicon-optional"></a><span data-ttu-id="fefb0-184">사용자 지정 키워드 사전/어휘 만들기 (선택 사항)</span><span class="sxs-lookup"><span data-stu-id="fefb0-184">Create custom keyword dictionary/lexicon (optional)</span></span>

<span data-ttu-id="fefb0-185">메모장과 같은 텍스트 편집기를 사용 하 여 감독 정책에서 모니터링할 키워드 용어를 포함 하는 파일을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="fefb0-185">Use a text editor (like Notepad), to create a file that includes the keyword terms you'd like to monitor in a supervision policy.</span></span> <span data-ttu-id="fefb0-186">각 용어가 별도의 줄에 있는지 확인 하 고 파일을 **유니코드/u t f-16 (꼬마)** 형식으로 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="fefb0-186">Make sure that each term is on a separate line and save the file in the **Unicode/UTF-16 (Little Endian)** format.</span></span>

### <a name="create-custom-sensitive-information-types"></a><span data-ttu-id="fefb0-187">사용자 지정 중요 한 정보 유형 만들기</span><span class="sxs-lookup"><span data-stu-id="fefb0-187">Create custom sensitive information types</span></span>

1. <span data-ttu-id="fefb0-188">새로운 중요 한 정보 유형을 만들고 Office 365 보안 & 준수 센터에 사용자 지정 사전을 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="fefb0-188">Create a new sensitive information type and add your custom dictionary in the Office 365 Security & Compliance Center.</span></span> <span data-ttu-id="fefb0-189">**중요 한 정보** 유형 **분류** \> 로 이동 하 여 **새 중요 한 정보 유형 마법사**의 단계를 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="fefb0-189">Navigate to **Classifications** \> **Sensitive info types** and follow the steps in the **New sensitive info type wizard**.</span></span> <span data-ttu-id="fefb0-190">여기에서 다음을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="fefb0-190">Here you will:</span></span>

    - <span data-ttu-id="fefb0-191">중요 한 정보 유형에 대 한 이름 및 설명 정의</span><span class="sxs-lookup"><span data-stu-id="fefb0-191">Define a name and description for the sensitive info type</span></span>
    - <span data-ttu-id="fefb0-192">근접성, 신뢰 수준 및 주 패턴 요소 정의</span><span class="sxs-lookup"><span data-stu-id="fefb0-192">Define the proximity, confidence level, and primary pattern elements</span></span>
    - <span data-ttu-id="fefb0-193">일치 요소에 대 한 요구 사항으로 사용자 지정 사전 가져오기</span><span class="sxs-lookup"><span data-stu-id="fefb0-193">Import your custom dictionary as a requirement for the matching element</span></span>
    - <span data-ttu-id="fefb0-194">선택 항목 검토 및 중요 한 정보 유형 만들기</span><span class="sxs-lookup"><span data-stu-id="fefb0-194">Review your selections and create the sensitive info type</span></span>

    <span data-ttu-id="fefb0-195">자세한 내용은 [사용자 지정 중요 한 정보 유형 만들기](create-a-custom-sensitive-information-type.md) 및 [키워드 사전 만들기](create-a-keyword-dictionary.md) 를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="fefb0-195">For more detailed information, see [Create a custom sensitive information type](create-a-custom-sensitive-information-type.md) and [Create a keyword dictionary](create-a-keyword-dictionary.md)</span></span>

    <span data-ttu-id="fefb0-196">사용자 지정 사전/어휘를 만든 후에는 [DlpKeywordDictionary](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-dlp/get-dlpkeyworddictionary) cmdlet을 사용 하 여 구성 된 키워드를 보거나 [DlpKeywordDictionary](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-dlp/set-dlpkeyworddictionary) cmdlet에서 용어를 추가 및 제거할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fefb0-196">After the custom dictionary/lexicon is created, you can view the configured keywords with the [Get-DlpKeywordDictionary](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-dlp/get-dlpkeyworddictionary) cmdlet or add and remove terms using the [Set-DlpKeywordDictionary](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-dlp/set-dlpkeyworddictionary) cmdlet.</span></span>

## <a name="step-4-set-up-a-supervision-policy-required"></a><span data-ttu-id="fefb0-197">4 단계: 감독 정책 설정 (필수)</span><span class="sxs-lookup"><span data-stu-id="fefb0-197">Step 4: Set up a supervision policy (required)</span></span>
  
1. <span data-ttu-id="fefb0-198">Office 365 [https://protection.office.com](https://protection.office.com) 조직의 관리자 계정에 대 한 자격 증명을 사용 하 여 로그인 합니다.</span><span class="sxs-lookup"><span data-stu-id="fefb0-198">Sign into [https://protection.office.com](https://protection.office.com) using credentials for an admin account in your Office 365 organization.</span></span>

2. <span data-ttu-id="fefb0-199">Office 365 보안 및 준수 센터에서 **감독**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="fefb0-199">In the Office 365 security and compliance center, select **Supervision**.</span></span>
  
3. <span data-ttu-id="fefb0-200">**만들기** 를 선택 하 고 마법사의 지시에 따라 정책 구성을 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="fefb0-200">Select **Create** and follow the wizard to set up the policy configuration.</span></span> <span data-ttu-id="fefb0-201">마법사를 사용 하 여 다음을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fefb0-201">Using the wizard, you will:</span></span>

    - <span data-ttu-id="fefb0-202">정책에 이름과 설명을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="fefb0-202">Give the policy a name and description.</span></span>
    - <span data-ttu-id="fefb0-203">제외할 사용자 또는 그룹 선택을 비롯 하 여 감독할 사용자 또는 그룹을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="fefb0-203">Choose the users or groups to supervise, including choosing users or groups you'd like to exclude.</span></span>
    - <span data-ttu-id="fefb0-204">감독 정책 [조건을](supervision-policies.md#ConditionalSettings)정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="fefb0-204">Define the supervision policy [conditions](supervision-policies.md#ConditionalSettings).</span></span> <span data-ttu-id="fefb0-205">메시지 주소, 키워드, 파일 형식 및 크기 일치 조건에서 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fefb0-205">You can choose from message address, keyword, file types, and size match conditions.</span></span>
    - <span data-ttu-id="fefb0-206">중요 한 정보 유형을 포함 하 고 싶은 경우 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="fefb0-206">Choose if you'd like to include sensitive information types.</span></span> <span data-ttu-id="fefb0-207">여기에서 기본 및 사용자 지정 중요 한 정보 유형을 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fefb0-207">This is where you can select default and custom sensitive info types.</span></span>
    - <span data-ttu-id="fefb0-208">공격적인 언어 모델을 사용 하도록 설정 하려면 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="fefb0-208">Choose if you'd like to enable the offensive language model.</span></span> <span data-ttu-id="fefb0-209">이는 전자 메일 메시지 본문에서 보내거나 받은 부적절 한 언어를 감지 합니다.</span><span class="sxs-lookup"><span data-stu-id="fefb0-209">This detects inappropriate language sent or received in the body of email messages.</span></span>
    - <span data-ttu-id="fefb0-210">검토할 통신의 비율을 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="fefb0-210">Define the percentage of communications to review.</span></span>
    - <span data-ttu-id="fefb0-211">정책에 대 한 검토자를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="fefb0-211">Choose the reviewers for the policy.</span></span> <span data-ttu-id="fefb0-212">검토자는 개별 사용자 또는 [메일 사용이 가능한 보안 그룹이](https://docs.microsoft.com/Exchange/recipients-in-exchange-online/manage-mail-enabled-security-groups#create-a-mail-enabled-security-group)될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fefb0-212">Reviewers can be individual users or [mail-enabled security groups](https://docs.microsoft.com/Exchange/recipients-in-exchange-online/manage-mail-enabled-security-groups#create-a-mail-enabled-security-group).</span></span> <span data-ttu-id="fefb0-213">모든 검토자에 게 Exchange Online에서 호스트 되는 사서함이 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="fefb0-213">All reviewers must have mailboxes hosted on Exchange Online.</span></span>
    - <span data-ttu-id="fefb0-214">정책 선택을 검토 하 고 정책을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="fefb0-214">Review your policy selections and create the policy.</span></span>

## <a name="step-5-test-your-supervision-policy-optional"></a><span data-ttu-id="fefb0-215">5 단계: 감독 정책 테스트 (선택 사항)</span><span class="sxs-lookup"><span data-stu-id="fefb0-215">Step 5: Test your supervision policy (optional)</span></span>

<span data-ttu-id="fefb0-216">통신 감독 정책을 만든 후에는 테스트를 통해 정의한 조건이 정책에 의해 적절 하 게 적용 되는지 확인 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="fefb0-216">After you create a communication supervision policy, it's a good idea to test to make sure that the conditions you defined are being properly enforced by the policy.</span></span> <span data-ttu-id="fefb0-217">또한 감독 정책에 중요 한 정보 유형이 포함 되어 있는 경우 [DLP (데이터 손실 방지) 정책을 테스트할](create-test-tune-dlp-policy.md) 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fefb0-217">You may also want to [test your data loss prevention (DLP) policies](create-test-tune-dlp-policy.md) if your supervision policies include sensitive information types.</span></span> <span data-ttu-id="fefb0-218">다음 단계에 따라 감독 정책을 테스트 합니다.</span><span class="sxs-lookup"><span data-stu-id="fefb0-218">Follow these steps to test your supervision policy:</span></span>

1. <span data-ttu-id="fefb0-219">테스트할 정책에 정의 된 감독 된 사용자로 로그인 한 전자 메일 클라이언트 또는 Microsoft 팀을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="fefb0-219">Open an email client or Microsoft Teams logged in as a supervised user defined in the policy you want to test.</span></span>
2. <span data-ttu-id="fefb0-220">감독 정책에 정의한 기준을 충족 하는 전자 메일 또는 Microsoft 팀 채팅을 보냅니다.</span><span class="sxs-lookup"><span data-stu-id="fefb0-220">Send an email or Microsoft Teams chat that meets the criteria you've defined in the supervision policy.</span></span> <span data-ttu-id="fefb0-221">키워드, 첨부 파일 크기, 도메인 등이 될 수 있습니다. 정책에서 구성 된 조건부 설정이 너무 제한적일 또는 너무 lenient 인지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="fefb0-221">This can be a keyword, attachment size, domain, etc. Make sure that you determine if your configured conditional settings in the policy are too restrictive or too lenient.</span></span>

    >[!NOTE]
    ><span data-ttu-id="fefb0-222">정의 된 정책이 적용 되는 전자 메일은 거의 실시간으로 처리 되며 정책이 구성 된 직후에 테스트할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fefb0-222">Emails subject to defined policies are processed in near real-time and can be tested immediately after the policy is configured.</span></span> <span data-ttu-id="fefb0-223">Microsoft 팀의 채팅에는 정책에서 전체 프로세스를 수행 하는 데 최대 24 시간이 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fefb0-223">Chats in Microsoft Teams can take up to 24 hours to fully process in a policy.</span></span> 

3. <span data-ttu-id="fefb0-224">통신 감독 정책에 지정 된 검토자로 Office 365 테 넌 트에 로그인 합니다.</span><span class="sxs-lookup"><span data-stu-id="fefb0-224">Log into your Office 365 tenant as a reviewer designated in the communication supervision policy.</span></span> <span data-ttu-id="fefb0-225">*사용자 지정 정책이* > **열려** 있는 **감독** > 을 탐색 하 여 정책에 대 한 보고서를 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="fefb0-225">Navigate to **Supervision** > *Your Custom Policy* > **Open** to view the report for the policy.</span></span>

