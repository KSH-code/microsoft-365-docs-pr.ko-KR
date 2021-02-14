---
title: 감독 정책 구성
description: 내부 또는 외부 검토자에 의해 검사할 직원 커뮤니케이션을 캡처하도록 Office 365에서 통신 감독 정책을 구성합니다.
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
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 74244b5288043a1d1bc62e0ae09ee8c25ff7d4e1
ms.sourcegitcommit: 27daadad9ca0f02a833ff3cff8a574551b9581da
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/12/2020
ms.locfileid: "47546780"
---
# <a name="configure-supervision-policies-in-office-365"></a><span data-ttu-id="ebb2d-103">Office 365에서 감독 정책 구성</span><span class="sxs-lookup"><span data-stu-id="ebb2d-103">Configure supervision policies in Office 365</span></span>

>[!IMPORTANT]
><span data-ttu-id="ebb2d-104">2020년 2월 Microsoft 365 규정 준수의 커뮤니케이션 규정 준수가 릴리스된 후 Office 365의 감독은 사용 중지됩니다.</span><span class="sxs-lookup"><span data-stu-id="ebb2d-104">Following the release of communication compliance in Microsoft 365 Compliance in February 2020, Supervision in Office 365 is being retired.</span></span> <span data-ttu-id="ebb2d-105">감독 정책은 더 이상 만들 수 없습니다. 정책은 결국 읽기 전용 액세스의 연장된 후에 제거됩니다.</span><span class="sxs-lookup"><span data-stu-id="ebb2d-105">Supervision policies will no longer be available for creation, and policies will eventually be removed, after an extended period of read only access.</span></span>
>
><span data-ttu-id="ebb2d-106">감독을 사용하는 경우 다음에 유의해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ebb2d-106">If you use Supervision, be aware that:</span></span>
>
>- <span data-ttu-id="ebb2d-107">2020년 6월 15일부터 테넌트는 새 감독 정책을 만들 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="ebb2d-107">Beginning June 15th, 2020, tenants will not have the ability to create new Supervision policies.</span></span>
>- <span data-ttu-id="ebb2d-108">2020년 8월 31일부터 기존 정책은 새 메시지 캡처를 중지합니다.</span><span class="sxs-lookup"><span data-stu-id="ebb2d-108">Beginning August 31st, 2020, existing policies will stop capturing new messages.</span></span>
>- <span data-ttu-id="ebb2d-109">2020년 10월 26일부터 기존 정책이 삭제됩니다.</span><span class="sxs-lookup"><span data-stu-id="ebb2d-109">Beginning October 26th, 2020, existing policies will be deleted.</span></span>
>
><span data-ttu-id="ebb2d-110">현재 Office 365에서 감독을 탐색하거나 사용하고 있는 고객이 훨씬 [](communication-compliance.md) 풍부한 지능형 기능 집합으로 커뮤니케이션 모니터링 또는 규정 요구 사항을 해결하기 위해 새로운 통신 준수 솔루션을 사용하는 것이 능동적으로 권장됩니다.</span><span class="sxs-lookup"><span data-stu-id="ebb2d-110">We actively encourage customers who are currently exploring or using Supervision in Office 365 to use the new [communication compliance](communication-compliance.md) solution to address your communications monitoring or regulatory requirements with a much richer set of intelligent capabilities.</span></span>

<span data-ttu-id="ebb2d-111">감독 정책을 사용하여 내부 또는 외부 검토자에 의해 검사할 직원 커뮤니케이션을 캡처합니다.</span><span class="sxs-lookup"><span data-stu-id="ebb2d-111">Use supervision policies to capture employee communications for examination by internal or external reviewers.</span></span> <span data-ttu-id="ebb2d-112">감독 정책이 조직의 통신을 모니터링하는 데 도움이 되는 방법에 대한 자세한 내용은 [Office 365의](supervision-policies.md)감독 정책을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="ebb2d-112">For more information about how supervision policies can help you monitor communications in your organization, see [Supervision policies in Office 365](supervision-policies.md).</span></span>

>[!NOTE]
><span data-ttu-id="ebb2d-113">감독 정책에 따라 모니터링되는 사용자는 Microsoft 365 E5 준수 라이선스, 고급 준수 추가 기능의 Office 365 Enterprise E3 라이선스가 있어야 합니다. 또는 Office 365 Enterprise E5 구독에 포함되거나 Microsoft 365 E5 구독에 포함되어 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ebb2d-113">Users monitored by supervision policies must have a Microsoft 365 E5 Compliance license, an Office 365 Enterprise E3 license with the Advanced Compliance add-on, or be included in an Office 365 Enterprise E5 subscription, or be included in a Microsoft 365 E5 subscription.</span></span>
><span data-ttu-id="ebb2d-114">기존 Enterprise E5 요금제가 없는 경우 감독을 시도하려는 경우 [Office 365 Enterprise E5](https://go.microsoft.com/fwlink/p/?LinkID=698279)평가판을 등록할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ebb2d-114">If you don't have an existing Enterprise E5 plan and want to try supervision, you can [sign up for a trial of Office 365 Enterprise E5](https://go.microsoft.com/fwlink/p/?LinkID=698279).</span></span>
  
<span data-ttu-id="ebb2d-115">다음 단계에 따라 조직에서 감독을 설정하고 사용하세요.</span><span class="sxs-lookup"><span data-stu-id="ebb2d-115">Follow these steps to set up and use supervision in your organization:</span></span>
  
- <span data-ttu-id="ebb2d-116">**1단계(선택 사항)**: [감독을 위한 그룹 설정](#step-1-set-up-groups-for-supervision-optional)</span><span class="sxs-lookup"><span data-stu-id="ebb2d-116">**Step 1 (optional)**: [Set up groups for supervision](#step-1-set-up-groups-for-supervision-optional)</span></span>

    <span data-ttu-id="ebb2d-117">감독 정책 사용을 시작하기 전에 검토된 커뮤니케이션이 필요한 사용자와 검토를 수행할 인원을 결정하십시오.</span><span class="sxs-lookup"><span data-stu-id="ebb2d-117">Before you start using supervision policies, determine who needs communications reviewed and who performs reviews.</span></span> <span data-ttu-id="ebb2d-118">소수의 사용자만 시작하여 감독의 작동 방식에 대해 보고 싶은 경우 지금 그룹 설정을 건너뛸 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ebb2d-118">If you want to get started with just a few users to see how supervision works, you can skip setting up groups for now.</span></span>

- <span data-ttu-id="ebb2d-119">**2단계(필수)**: [조직에서](#step-2-make-supervision-available-in-your-organization-required) 감독을 사용할 수 있도록 설정</span><span class="sxs-lookup"><span data-stu-id="ebb2d-119">**Step 2 (required)**: [Make supervision available in your organization](#step-2-make-supervision-available-in-your-organization-required)</span></span>

    <span data-ttu-id="ebb2d-120">정책을 설정할 수 있도록 감독 검토 역할 그룹에 자신을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="ebb2d-120">Add yourself to the Supervisory Review role group so you can set up policies.</span></span> <span data-ttu-id="ebb2d-121">이 역할이 할당된 모든  사람은 보안 및 준수 센터의 감독 & 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ebb2d-121">Anyone who has this role assigned can access the **Supervision** page in the Security & Compliance Center.</span></span> <span data-ttu-id="ebb2d-122">검토 가능한 전자 메일이 Exchange Online에서 호스팅된 경우 각 검토자는 Exchange Online에 대한 원격 [PowerShell](https://docs.microsoft.com/powershell/exchange/disable-access-to-exchange-online-powershell)액세스 권한이 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ebb2d-122">If reviewable email is hosted on Exchange Online, each reviewer must have [remote PowerShell access to Exchange Online](https://docs.microsoft.com/powershell/exchange/disable-access-to-exchange-online-powershell).</span></span>

- <span data-ttu-id="ebb2d-123">**3단계(선택 사항)**: 사용자 지정 중요한 정보 유형 및 [사용자 지정 키워드 사전 만들기](#step-3-create-custom-sensitive-information-types-and-custom-keyword-dictionaries-optional)</span><span class="sxs-lookup"><span data-stu-id="ebb2d-123">**Step 3 (optional)**: [Create custom sensitive information types and custom keyword dictionaries](#step-3-create-custom-sensitive-information-types-and-custom-keyword-dictionaries-optional)</span></span>

    <span data-ttu-id="ebb2d-124">감독 정책에 대한 사용자 지정 중요한 정보 유형 또는 사용자 지정 키워드 사전이 필요한 경우 감독 마법사를 시작하기 전에 만들어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ebb2d-124">If you need a custom sensitive info type or a custom keyword dictionary for your supervision policy, you need to create it before starting the supervision wizard.</span></span>

- <span data-ttu-id="ebb2d-125">**4단계(필수)**: 감독 [정책 설정](#step-4-set-up-a-supervision-policy-required)</span><span class="sxs-lookup"><span data-stu-id="ebb2d-125">**Step 4 (required)**: [Set up a supervision policy](#step-4-set-up-a-supervision-policy-required)</span></span>

    <span data-ttu-id="ebb2d-126">보안 및 준수 센터에서 & 정책을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ebb2d-126">You create supervision policies in the Security & Compliance Center.</span></span> <span data-ttu-id="ebb2d-127">이러한 정책은 조직에서 검토할 커뮤니케이션을 정의하고 검토를 수행하는 대상을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="ebb2d-127">These policies define which communications are subject to review in your organization and specifies who performs reviews.</span></span> <span data-ttu-id="ebb2d-128">커뮤니케이션에는 전자 메일 및 Microsoft Teams 통신, 제3자 플랫폼 통신(예: Facebook, Twitter 등)이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="ebb2d-128">Communications include email and Microsoft Teams communications, and 3rd-party platform communications (such as Facebook, Twitter, etc.).</span></span> <span data-ttu-id="ebb2d-129">조직에서 만든 감독 정책은 Microsoft 365 구독의 통신 감독에서 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="ebb2d-129">Supervision policies created in organizations are not supported in communication supervision in Microsoft 365 subscriptions.</span></span>

- <span data-ttu-id="ebb2d-130">**5단계(선택 사항)**: [통신 감독 정책 테스트](#step-5-test-your-supervision-policy-optional)</span><span class="sxs-lookup"><span data-stu-id="ebb2d-130">**Step 5 (optional)**: [Test your communication supervision policy](#step-5-test-your-supervision-policy-optional)</span></span>

    <span data-ttu-id="ebb2d-131">감독 정책을 테스트하여 감독 정책이 원하는 경우와 같은 기능을 하는지 검사합니다.</span><span class="sxs-lookup"><span data-stu-id="ebb2d-131">Test your supervision policy to make sure it functions as desired.</span></span> <span data-ttu-id="ebb2d-132">규정 준수 전략이 표준을 충족하는지 보장하는 것이 중요합니다.</span><span class="sxs-lookup"><span data-stu-id="ebb2d-132">It is important to ensure that your compliance strategy is meeting your standards.</span></span>

## <a name="step-1-set-up-groups-for-supervision-optional"></a><span data-ttu-id="ebb2d-133">1단계: 감독을 위한 그룹 설정(선택 사항)</span><span class="sxs-lookup"><span data-stu-id="ebb2d-133">Step 1: Set up groups for supervision (optional)</span></span>

 <span data-ttu-id="ebb2d-134">감독 정책을 만들 때 통신을 검사한 사용자와 검토를 수행하는 사용자 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="ebb2d-134">When you create a supervision policy, you define who has their communications scanned and who performs reviews.</span></span> <span data-ttu-id="ebb2d-135">정책에서 전자 메일 주소를 사용하여 개인 또는 사용자 그룹을 식별합니다.</span><span class="sxs-lookup"><span data-stu-id="ebb2d-135">In the policy, you'll use email addresses to identify individuals or groups of people.</span></span> <span data-ttu-id="ebb2d-136">설정을 간소화하기 위해 통신을 검사한 사용자에 대한 그룹과 해당 통신을 검토하는 사용자에 대한 그룹을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ebb2d-136">To simplify your setup, you can create groups for people who have their communication scanned and groups for people who review those communications.</span></span> <span data-ttu-id="ebb2d-137">그룹을 사용하는 경우 여러 가지가 필요할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ebb2d-137">If you're using groups, you may need several.</span></span> <span data-ttu-id="ebb2d-138">예를 들어 서로 다른 두 사용자 그룹 간의 통신을 모니터링하거나 감독되지 않을 그룹을 지정하려는 경우를 예로 들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ebb2d-138">For example, you want to monitor communications between two distinct groups of people or if you want to specify a group that isn't going to be supervised.</span></span>

<span data-ttu-id="ebb2d-139">다음 차트를 사용하여 조직의 통신 감독 정책에 대한 그룹을 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ebb2d-139">Use the following chart to help you configure groups in your organization for communication supervision policies:</span></span>

| <span data-ttu-id="ebb2d-140">**정책 구성원**</span><span class="sxs-lookup"><span data-stu-id="ebb2d-140">**Policy Member**</span></span> | <span data-ttu-id="ebb2d-141">**지원되는 그룹**</span><span class="sxs-lookup"><span data-stu-id="ebb2d-141">**Supported Groups**</span></span> | <span data-ttu-id="ebb2d-142">**미지원 그룹**</span><span class="sxs-lookup"><span data-stu-id="ebb2d-142">**Unsupported Groups**</span></span> |
|:-----|:-----|:-----|
|<span data-ttu-id="ebb2d-143">감독된 사용자</span><span class="sxs-lookup"><span data-stu-id="ebb2d-143">Supervised users</span></span> <br> <span data-ttu-id="ebb2d-144">감독되지 않는 사용자</span><span class="sxs-lookup"><span data-stu-id="ebb2d-144">Non-supervised users</span></span> | <span data-ttu-id="ebb2d-145">메일 그룹</span><span class="sxs-lookup"><span data-stu-id="ebb2d-145">Distribution groups</span></span> <br> <span data-ttu-id="ebb2d-146">Microsoft 365 그룹</span><span class="sxs-lookup"><span data-stu-id="ebb2d-146">Microsoft 365 groups</span></span> | <span data-ttu-id="ebb2d-147">동적 메일 그룹</span><span class="sxs-lookup"><span data-stu-id="ebb2d-147">Dynamic distribution groups</span></span> |
| <span data-ttu-id="ebb2d-148">검토자</span><span class="sxs-lookup"><span data-stu-id="ebb2d-148">Reviewers</span></span> | <span data-ttu-id="ebb2d-149">메일 사용 가능 보안 그룹</span><span class="sxs-lookup"><span data-stu-id="ebb2d-149">Mail-enabled security groups</span></span>  | <span data-ttu-id="ebb2d-150">메일 그룹</span><span class="sxs-lookup"><span data-stu-id="ebb2d-150">Distribution groups</span></span> <br> <span data-ttu-id="ebb2d-151">동적 메일 그룹</span><span class="sxs-lookup"><span data-stu-id="ebb2d-151">Dynamic distribution groups</span></span> |
  
<span data-ttu-id="ebb2d-152">관리되는 사용자에 대해 Microsoft 365 그룹을 선택하면 정책은 공유 사서함 및 그룹과 연결된 Microsoft Teams 채널의 콘텐츠를 모니터링합니다.</span><span class="sxs-lookup"><span data-stu-id="ebb2d-152">When you select a Microsoft 365 group for supervised users, the policy monitors the content of the shared mailbox and the Microsoft Teams channels associated with the group.</span></span> <span data-ttu-id="ebb2d-153">메일 목록을 선택하면 정책이 개별 사용자 사서함을 모니터링합니다.</span><span class="sxs-lookup"><span data-stu-id="ebb2d-153">When you select a distribution list, the policy monitors individual user mailboxes.</span></span>

<span data-ttu-id="ebb2d-154">대규모 엔터프라이즈 조직에서 감독되는 사용자를 관리하려면 대규모 그룹에서 모든 사용자를 모니터링해야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ebb2d-154">To manage supervised users in large enterprise organizations, you may need to monitor all users across large groups.</span></span> <span data-ttu-id="ebb2d-155">PowerShell을 사용하여 할당된 그룹에 대한 전역 감독 정책에 대한 메일 그룹을 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ebb2d-155">You can use PowerShell to configure a distribution group for a global supervision policy for the assigned group.</span></span> <span data-ttu-id="ebb2d-156">이렇게 하면 단일 정책을 사용하여 수천 명의 사용자를 모니터링하고 새 직원이 조직에 가입할 때 감독 정책을 업데이트할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ebb2d-156">This enables you to monitor thousands of users with a single policy and keep the supervision policy updated as new employees join your organization.</span></span>

1. <span data-ttu-id="ebb2d-157">다음 속성을 [](https://docs.microsoft.com/powershell/module/exchange/new-distributiongroup) 사용하여 전역 감독 정책에 대한 전용 메일 그룹을 만드시다. 이 메일 그룹이 다른 목적이나 다른 Office 365 서비스에 사용되지 않는지 확인</span><span class="sxs-lookup"><span data-stu-id="ebb2d-157">Create a dedicated [distribution group](https://docs.microsoft.com/powershell/module/exchange/new-distributiongroup) for your global supervision policy with the following properties: Make sure that this distribution group isn't used for other purposes or other Office 365 services.</span></span>

    - <span data-ttu-id="ebb2d-158">**MemberDepartRestriction = Closed**.</span><span class="sxs-lookup"><span data-stu-id="ebb2d-158">**MemberDepartRestriction = Closed**.</span></span> <span data-ttu-id="ebb2d-159">사용자가 메일 그룹에서 자신을 제거할 수 없는지 확인</span><span class="sxs-lookup"><span data-stu-id="ebb2d-159">Ensures that users cannot remove themselves from the distribution group.</span></span>
    - <span data-ttu-id="ebb2d-160">**MemberJoinRestriction = Closed**.</span><span class="sxs-lookup"><span data-stu-id="ebb2d-160">**MemberJoinRestriction = Closed**.</span></span> <span data-ttu-id="ebb2d-161">사용자가 메일 그룹에 자신을 추가할 수 없는지 확인</span><span class="sxs-lookup"><span data-stu-id="ebb2d-161">Ensures that users cannot add themselves to the distribution group.</span></span>
    - <span data-ttu-id="ebb2d-162">**ModerationEnabled = True**.</span><span class="sxs-lookup"><span data-stu-id="ebb2d-162">**ModerationEnabled = True**.</span></span> <span data-ttu-id="ebb2d-163">이 그룹에 전송된 모든 메시지에 승인이 적용되고 그룹이 감독 정책 구성 외부에서 통신하는 데 사용되지 않는지 확인</span><span class="sxs-lookup"><span data-stu-id="ebb2d-163">Ensures that all messages sent to this group are subject to approval and that the group is not being used to communicate outside of the supervision policy configuration.</span></span>

    ```PowerShell
    New-DistributionGroup -Name <your group name> -Alias <your group alias> -MemberDepartRestriction 'Closed' -MemberJoinRestriction 'Closed' -ModerationEnabled $true
    ```

2. <span data-ttu-id="ebb2d-164">사용되지 않는 [Exchange](https://docs.microsoft.com/Exchange/recipients/mailbox-custom-attributes?view=exchserver-2019&viewFallbackFrom=exchonline-ww) 사용자 지정 특성을 선택하여 조직의 감독 정책에 추가된 사용자를 추적합니다.</span><span class="sxs-lookup"><span data-stu-id="ebb2d-164">Select an unused [Exchange custom attribute](https://docs.microsoft.com/Exchange/recipients/mailbox-custom-attributes?view=exchserver-2019&viewFallbackFrom=exchonline-ww) to track users added to the supervision policy in your organization.</span></span>

3. <span data-ttu-id="ebb2d-165">다음과 같은 PowerShell 스크립트를 일정에 따라 실행하여 감독 정책에 사용자를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="ebb2d-165">Run the following PowerShell script on a recurring schedule to add users to the supervision policy:</span></span>

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

<span data-ttu-id="ebb2d-166">그룹 설정에 대한 자세한 내용은 다음을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="ebb2d-166">For more information about setting up groups, see:</span></span>

- [<span data-ttu-id="ebb2d-167">메일 그룹 만들기 및 관리</span><span class="sxs-lookup"><span data-stu-id="ebb2d-167">Create and manage distribution groups</span></span>](https://docs.microsoft.com/Exchange/recipients-in-exchange-online/manage-distribution-groups/manage-distribution-groups)
- [<span data-ttu-id="ebb2d-168">메일 사용 가능 보안 그룹 관리</span><span class="sxs-lookup"><span data-stu-id="ebb2d-168">Manage mail-enabled security groups</span></span>](https://docs.microsoft.com/Exchange/recipients-in-exchange-online/manage-mail-enabled-security-groups)
- [<span data-ttu-id="ebb2d-169">Microsoft 365 그룹 개요</span><span class="sxs-lookup"><span data-stu-id="ebb2d-169">Overview of Microsoft 365 Groups</span></span>](https://docs.microsoft.com/office365/admin/create-groups/office-365-groups?view=o365-worldwide)

## <a name="step-2-make-supervision-available-in-your-organization-required"></a><span data-ttu-id="ebb2d-170">2단계: 조직에서 감독을 사용할 수 있도록 설정(필수)</span><span class="sxs-lookup"><span data-stu-id="ebb2d-170">Step 2: Make supervision available in your organization (required)</span></span>

<span data-ttu-id="ebb2d-171">보안 **및** 준수 센터에서 감독을 메뉴 옵션으로 사용할 & 관리 검토 관리자 역할이 할당되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ebb2d-171">To make **Supervision** available as a menu option in Security & Compliance Center, you must be assigned the Supervisory Review Administrator role.</span></span>
  
<span data-ttu-id="ebb2d-172">이렇게 하여 자신을 관리 검토 역할 그룹의 구성원으로 추가하거나 역할 그룹을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ebb2d-172">To do this, you can either add yourself as a member of the Supervisory Review role group, or you can create a role group.</span></span>
  
### <a name="add-members-to-the-supervisory-review-role-group"></a><span data-ttu-id="ebb2d-173">관리 검토 역할 그룹에 구성원 추가</span><span class="sxs-lookup"><span data-stu-id="ebb2d-173">Add members to the Supervisory Review role group</span></span>

1. <span data-ttu-id="ebb2d-174">조직의 [https://protection.office.com](https://protection.office.com) 관리자 계정에 대한 자격 증명을 사용하여 로그인합니다.</span><span class="sxs-lookup"><span data-stu-id="ebb2d-174">Sign into [https://protection.office.com](https://protection.office.com) using credentials for an admin account in your organization.</span></span>

2. <span data-ttu-id="ebb2d-175">보안 및 & 센터에서 사용 **권한으로 이동 합니다.**</span><span class="sxs-lookup"><span data-stu-id="ebb2d-175">In the Security & Compliance Center, go to **Permissions**.</span></span>

3. <span data-ttu-id="ebb2d-176">관리 **검토 역할** 그룹을 선택하고 편집 아이콘을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="ebb2d-176">Select the **Supervisory Review** role group and then click the Edit icon.</span></span>

4. <span data-ttu-id="ebb2d-177">구성원 **섹션에서** 조직에 대한 통신 감독을 관리하려는 인원을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="ebb2d-177">In the **Members** section, add the people who you want to manage communication supervision for your organization.</span></span>

### <a name="create-a-new-role-group"></a><span data-ttu-id="ebb2d-178">새 역할 그룹 만들기</span><span class="sxs-lookup"><span data-stu-id="ebb2d-178">Create a new role group</span></span>

1. <span data-ttu-id="ebb2d-179">조직의 [https://protection.office.com/permissions](https://protection.office.com/permissions) 관리자 계정에 대한 자격 증명을 사용하여 로그인합니다.</span><span class="sxs-lookup"><span data-stu-id="ebb2d-179">Sign into [https://protection.office.com/permissions](https://protection.office.com/permissions) using credentials for an admin account in your organization.</span></span>

2. <span data-ttu-id="ebb2d-180">보안 및 & 센터에서 사용 권한으로 이동한 다음 추가()를  **+** 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="ebb2d-180">In the Security & Compliance Center, go to **Permissions** and then click Add (**+**).</span></span>

3. <span data-ttu-id="ebb2d-181">역할 **섹션에서** 추가()를 클릭하고 아래로 스크롤하여 관리 검토 **+** **관리자로 스크롤합니다.**</span><span class="sxs-lookup"><span data-stu-id="ebb2d-181">In the **Roles** section, click Add (**+**) and scroll down to **Supervisory Review Administrator**.</span></span> <span data-ttu-id="ebb2d-182">역할 그룹에 이 역할을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="ebb2d-182">Add this role to the role group.</span></span>

4. <span data-ttu-id="ebb2d-183">구성원 **섹션에서** 조직에 대한 통신 감독을 관리하려는 인원을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="ebb2d-183">In the **Members** section, add the people who you want to manage communication supervision for your organization.</span></span>

<span data-ttu-id="ebb2d-184">역할 그룹 및 사용 권한에 대한 자세한 내용은 준수 센터의 사용 [권한을 참조하세요.](../security/office-365-security/permissions-in-the-security-and-compliance-center.md)</span><span class="sxs-lookup"><span data-stu-id="ebb2d-184">For more information about role groups and permissions, see [Permissions in the Compliance Center](../security/office-365-security/permissions-in-the-security-and-compliance-center.md).</span></span>

### <a name="enable-remote-powershell-access-for-reviewers-if-email-is-hosted-on-exchange-online"></a><span data-ttu-id="ebb2d-185">검토자에 대해 원격 PowerShell 액세스 사용(전자 메일이 Exchange Online에 호스트된 경우)</span><span class="sxs-lookup"><span data-stu-id="ebb2d-185">Enable remote PowerShell access for reviewers (if email is hosted on Exchange Online)</span></span>

1. <span data-ttu-id="ebb2d-186">Exchange Online [PowerShell 액세스 사용](https://docs.microsoft.com/powershell/exchange/disable-access-to-exchange-online-powershell)또는 사용 안 하도록 설정의 지침을 따르는 합니다.</span><span class="sxs-lookup"><span data-stu-id="ebb2d-186">Follow the guidance in [Enable or disable access to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/disable-access-to-exchange-online-powershell).</span></span>

## <a name="step-3-create-custom-sensitive-information-types-and-custom-keyword-dictionaries-optional"></a><span data-ttu-id="ebb2d-187">3단계: 사용자 지정 중요한 정보 유형 및 사용자 지정 키워드 사전 만들기(선택 사항)</span><span class="sxs-lookup"><span data-stu-id="ebb2d-187">Step 3: Create custom sensitive information types and custom keyword dictionaries (optional)</span></span>

<span data-ttu-id="ebb2d-188">감독 정책 마법사에서 기존 사용자 지정 중요한 정보 유형 또는 사용자 지정 키워드 사전을 선택하려면 먼저 필요한 경우 이러한 항목을 만들어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ebb2d-188">In order to pick from existing custom sensitive information types or custom keyword dictionaries in the supervision policy wizard, you first need to create these items if needed.</span></span>

### <a name="create-custom-keyword-dictionarylexicon-optional"></a><span data-ttu-id="ebb2d-189">사용자 지정 키워드 사전/사전 만들기(선택 사항)</span><span class="sxs-lookup"><span data-stu-id="ebb2d-189">Create custom keyword dictionary/lexicon (optional)</span></span>

<span data-ttu-id="ebb2d-190">메모장과 같은 텍스트 편집기를 사용하여 감독 정책에서 모니터링할 키워드 용어가 포함된 파일을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ebb2d-190">Use a text editor (like Notepad), to create a file that includes the keyword terms you'd like to monitor in a supervision policy.</span></span> <span data-ttu-id="ebb2d-191">각 용어가 별도의 줄에 있는지 확인하여 **유니코드/UTF-16(Little Endian)** 형식으로 파일을 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="ebb2d-191">Make sure that each term is on a separate line and save the file in the **Unicode/UTF-16 (Little Endian)** format.</span></span>

### <a name="create-custom-sensitive-information-types"></a><span data-ttu-id="ebb2d-192">사용자 지정 중요한 정보 유형 만들기</span><span class="sxs-lookup"><span data-stu-id="ebb2d-192">Create custom sensitive information types</span></span>

1. <span data-ttu-id="ebb2d-193">새 중요한 정보 유형을 만들고 보안 및 준수 센터에서 사용자 지정 & 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="ebb2d-193">Create a new sensitive information type and add your custom dictionary in the Security & Compliance Center.</span></span> <span data-ttu-id="ebb2d-194">분류 **중요한** \> **정보 유형으로 이동하고** 새 중요한 정보 유형 마법사의 **단계를 따릅니다.**</span><span class="sxs-lookup"><span data-stu-id="ebb2d-194">Navigate to **Classifications** \> **Sensitive info types** and follow the steps in the **New sensitive info type wizard**.</span></span> <span data-ttu-id="ebb2d-195">여기서 다음을 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ebb2d-195">Here you will:</span></span>

    - <span data-ttu-id="ebb2d-196">중요한 정보 유형에 대한 이름 및 설명 정의</span><span class="sxs-lookup"><span data-stu-id="ebb2d-196">Define a name and description for the sensitive info type</span></span>
    - <span data-ttu-id="ebb2d-197">근접성, 신뢰 수준 및 기본 패턴 요소 정의</span><span class="sxs-lookup"><span data-stu-id="ebb2d-197">Define the proximity, confidence level, and primary pattern elements</span></span>
    - <span data-ttu-id="ebb2d-198">일치하는 요소에 대한 요구 사항으로 사용자 지정 사전 가져오기</span><span class="sxs-lookup"><span data-stu-id="ebb2d-198">Import your custom dictionary as a requirement for the matching element</span></span>
    - <span data-ttu-id="ebb2d-199">선택을 검토하고 중요한 정보 유형 만들기</span><span class="sxs-lookup"><span data-stu-id="ebb2d-199">Review your selections and create the sensitive info type</span></span>

    <span data-ttu-id="ebb2d-200">자세한 내용은 사용자 지정 중요한 정보 유형 [만들기](create-a-custom-sensitive-information-type.md) 및 키워드 [사전 만들기를 참조하세요.](create-a-keyword-dictionary.md)</span><span class="sxs-lookup"><span data-stu-id="ebb2d-200">For more detailed information, see [Create a custom sensitive information type](create-a-custom-sensitive-information-type.md) and [Create a keyword dictionary](create-a-keyword-dictionary.md)</span></span>

    <span data-ttu-id="ebb2d-201">사용자 지정 사전/사전을 만든 후 [Get-DlpKeywordDictionary](https://docs.microsoft.com/powershell/module/exchange/get-dlpkeyworddictionary) cmdlet을 사용하여 구성된 키워드를 보거나 [Set-DlpKeywordDictionary](https://docs.microsoft.com/powershell/module/exchange/set-dlpkeyworddictionary) cmdlet을 사용하여 용어를 추가 및 제거할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ebb2d-201">After the custom dictionary/lexicon is created, you can view the configured keywords with the [Get-DlpKeywordDictionary](https://docs.microsoft.com/powershell/module/exchange/get-dlpkeyworddictionary) cmdlet or add and remove terms using the [Set-DlpKeywordDictionary](https://docs.microsoft.com/powershell/module/exchange/set-dlpkeyworddictionary) cmdlet.</span></span>

## <a name="step-4-set-up-a-supervision-policy-required"></a><span data-ttu-id="ebb2d-202">4단계: 감독 정책 설정(필수)</span><span class="sxs-lookup"><span data-stu-id="ebb2d-202">Step 4: Set up a supervision policy (required)</span></span>
  
1. <span data-ttu-id="ebb2d-203">조직의 [https://protection.office.com](https://protection.office.com) 관리자 계정에 대한 자격 증명을 사용하여 로그인합니다.</span><span class="sxs-lookup"><span data-stu-id="ebb2d-203">Sign into [https://protection.office.com](https://protection.office.com) using credentials for an admin account in your organization.</span></span>

2. <span data-ttu-id="ebb2d-204">보안 및 & 센터에서 **감독을 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="ebb2d-204">In the Security & Compliance Center, select **Supervision**.</span></span>
  
3. <span data-ttu-id="ebb2d-205">**만들기를** 선택하고 마법사에 따라 정책 구성을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="ebb2d-205">Select **Create** and follow the wizard to set up the policy configuration.</span></span> <span data-ttu-id="ebb2d-206">마법사를 사용하여 다음을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="ebb2d-206">Using the wizard, you will:</span></span>

    - <span data-ttu-id="ebb2d-207">정책에 이름과 설명을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="ebb2d-207">Give the policy a name and description.</span></span>
    - <span data-ttu-id="ebb2d-208">제외할 사용자 또는 그룹 선택을 포함하여 감독할 사용자 또는 그룹을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="ebb2d-208">Choose the users or groups to supervise, including choosing users or groups you'd like to exclude.</span></span>
    - <span data-ttu-id="ebb2d-209">감독 정책 조건을 [정의합니다.](supervision-policies.md#ConditionalSettings)</span><span class="sxs-lookup"><span data-stu-id="ebb2d-209">Define the supervision policy [conditions](supervision-policies.md#ConditionalSettings).</span></span> <span data-ttu-id="ebb2d-210">메시지 주소, 키워드, 파일 형식 및 크기 일치 조건에서 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ebb2d-210">You can choose from message address, keyword, file types, and size match conditions.</span></span>
    - <span data-ttu-id="ebb2d-211">중요한 정보 유형을 포함할지 선택하십시오.</span><span class="sxs-lookup"><span data-stu-id="ebb2d-211">Choose if you'd like to include sensitive information types.</span></span> <span data-ttu-id="ebb2d-212">여기서 기본 및 사용자 지정 중요한 정보 유형을 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ebb2d-212">This is where you can select default and custom sensitive info types.</span></span>
    - <span data-ttu-id="ebb2d-213">비방성 언어 모델을 사용하도록 설정하려면 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="ebb2d-213">Choose if you'd like to enable the offensive language model.</span></span> <span data-ttu-id="ebb2d-214">전자 메일 메시지 본문에 보내거나 받은 부적절한 언어를 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="ebb2d-214">This detects inappropriate language sent or received in the body of email messages.</span></span>
    - <span data-ttu-id="ebb2d-215">검토할 통신 비율을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="ebb2d-215">Define the percentage of communications to review.</span></span>
    - <span data-ttu-id="ebb2d-216">정책에 대한 검토자 선택</span><span class="sxs-lookup"><span data-stu-id="ebb2d-216">Choose the reviewers for the policy.</span></span> <span data-ttu-id="ebb2d-217">검토자는 개별 사용자 또는 메일 사용이 가능한 [보안 그룹일 수 있습니다.](https://docs.microsoft.com/Exchange/recipients-in-exchange-online/manage-mail-enabled-security-groups#create-a-mail-enabled-security-group)</span><span class="sxs-lookup"><span data-stu-id="ebb2d-217">Reviewers can be individual users or [mail-enabled security groups](https://docs.microsoft.com/Exchange/recipients-in-exchange-online/manage-mail-enabled-security-groups#create-a-mail-enabled-security-group).</span></span> <span data-ttu-id="ebb2d-218">모든 검토자는 Exchange Online에 호스트된 사서함이 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ebb2d-218">All reviewers must have mailboxes hosted on Exchange Online.</span></span>
    - <span data-ttu-id="ebb2d-219">정책 선택을 검토하고 정책을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="ebb2d-219">Review your policy selections and create the policy.</span></span>

## <a name="step-5-test-your-supervision-policy-optional"></a><span data-ttu-id="ebb2d-220">5단계: 감독 정책 테스트(선택 사항)</span><span class="sxs-lookup"><span data-stu-id="ebb2d-220">Step 5: Test your supervision policy (optional)</span></span>

<span data-ttu-id="ebb2d-221">통신 감독 정책을 만든 후 정의한 조건이 정책에 의해 제대로 적용되고 있는지 테스트하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="ebb2d-221">After you create a communication supervision policy, it's a good idea to test to make sure that the conditions you defined are being properly enforced by the policy.</span></span> <span data-ttu-id="ebb2d-222">감독 정책에 중요한 정보 유형이 포함된 경우 [DLP(데이터](create-test-tune-dlp-policy.md) 손실 방지) 정책을 테스트할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ebb2d-222">You may also want to [test your data loss prevention (DLP) policies](create-test-tune-dlp-policy.md) if your supervision policies include sensitive information types.</span></span> <span data-ttu-id="ebb2d-223">다음 단계에 따라 감독 정책을 테스트합니다.</span><span class="sxs-lookup"><span data-stu-id="ebb2d-223">Follow these steps to test your supervision policy:</span></span>

1. <span data-ttu-id="ebb2d-224">테스트할 정책에 정의된 감독된 사용자로 로그인한 전자 메일 클라이언트 또는 Microsoft Teams를 여는 경우</span><span class="sxs-lookup"><span data-stu-id="ebb2d-224">Open an email client or Microsoft Teams logged in as a supervised user defined in the policy you want to test.</span></span>
2. <span data-ttu-id="ebb2d-225">감독 정책에서 정의한 기준을 충족하는 전자 메일 또는 Microsoft Teams 채팅을 전송합니다.</span><span class="sxs-lookup"><span data-stu-id="ebb2d-225">Send an email or Microsoft Teams chat that meets the criteria you've defined in the supervision policy.</span></span> <span data-ttu-id="ebb2d-226">키워드, 첨부 파일 크기, 도메인 등이 될 수 있습니다. 정책에서 구성된 조건부 설정이 너무 제한적이거나 너무 무의미한지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="ebb2d-226">This can be a keyword, attachment size, domain, etc. Make sure that you determine if your configured conditional settings in the policy are too restrictive or too lenient.</span></span>

    >[!NOTE]
    ><span data-ttu-id="ebb2d-227">정의된 정책이 적용된 전자 메일은 거의 실시간으로 처리되고 정책이 구성된 직후 테스트할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ebb2d-227">Emails subject to defined policies are processed in near real-time and can be tested immediately after the policy is configured.</span></span> <span data-ttu-id="ebb2d-228">Microsoft Teams의 채팅은 정책에서 완전히 처리되는 데 최대 24시간이 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ebb2d-228">Chats in Microsoft Teams can take up to 24 hours to fully process in a policy.</span></span> 

3. <span data-ttu-id="ebb2d-229">통신 감독 정책에 지정된 검토자로 Microsoft 365에 로그인합니다.</span><span class="sxs-lookup"><span data-stu-id="ebb2d-229">Log into Microsoft 365 as a reviewer designated in the communication supervision policy.</span></span> <span data-ttu-id="ebb2d-230">사용자 **지정** 정책 열기 감독으로 이동하여  >    >   정책에 대한 보고서를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ebb2d-230">Navigate to **Supervision** > *Your Custom Policy* > **Open** to view the report for the policy.</span></span>

