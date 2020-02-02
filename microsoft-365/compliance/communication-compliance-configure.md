---
title: 통신 준수 구성
description: 검토를 위해 직원 통신을 구성 하는 통신 준수 정책을 설정 합니다.
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
ms.openlocfilehash: 9371429caedfe2081331fab1aebbe0e1ec761e81
ms.sourcegitcommit: 2913fd74ad5086c7cac6388447285be9aa5a8e44
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/01/2020
ms.locfileid: "41661974"
---
# <a name="configure-communication-compliance-in-microsoft-365"></a><span data-ttu-id="e1b2a-103">Microsoft 365에서 통신 준수 구성</span><span class="sxs-lookup"><span data-stu-id="e1b2a-103">Configure communication compliance in Microsoft 365</span></span>

>[!IMPORTANT]
><span data-ttu-id="e1b2a-104">이 항목은 Microsoft 365 구독의 통신 준수 구성에 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e1b2a-104">This topic applies to configuring communication compliance in a Microsoft 365 subscription.</span></span> <span data-ttu-id="e1b2a-105">Office 365 구독에 대 한 감독 정책을 구성 하려면 [office 365에 대 한 감독 구성을](supervision-policies.md)참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="e1b2a-105">If you want to configure Supervision policies for an Office 365 subscription, see [Configure supervision for Office 365](supervision-policies.md).</span></span>

<span data-ttu-id="e1b2a-106">통신 준수 정책을 사용 하 여 내부 또는 외부 검토자가 검사할 직원 통신을 캡처할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e1b2a-106">Use communication compliance policies to capture employee communications for examination by internal or external reviewers.</span></span> <span data-ttu-id="e1b2a-107">통신 준수 정책을 통해 조직의 통신을 모니터링 하는 방법에 대 한 자세한 내용은 [Microsoft 365의 통신 준수 정책을](communication-compliance.md)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="e1b2a-107">For more information about how communication compliance policies can help you monitor communications in your organization, see [communication compliance policies in Microsoft 365](communication-compliance.md).</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="e1b2a-108">시작하기 전에</span><span class="sxs-lookup"><span data-stu-id="e1b2a-108">Before you begin</span></span>

<span data-ttu-id="e1b2a-109">통신 준수를 시작 하기 전에 Microsoft 365 구독을 확인 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e1b2a-109">Before you get started with communication compliance, you should confirm your Microsoft 365 subscription.</span></span> <span data-ttu-id="e1b2a-110">통신 준수 정책에 포함 된 사용자에 게는 Microsoft 365 E5 준수 라이선스, 고급 준수 추가 기능이 포함 된 Office 365 Enterprise E3 라이선스 또는 Microsoft 365 E5 구독에 포함 되어 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e1b2a-110">Users included in communication compliance policies must have a Microsoft 365 E5 Compliance license, an Office 365 Enterprise E3 license with the Advanced Compliance add-on, or be included in a Microsoft 365 E5 subscription.</span></span>

<span data-ttu-id="e1b2a-111">Microsoft 365 Enterprise E5 요금제가 아직 없는 경우 microsoft 365을 기존 Office 365 구독에 [추가](https://docs.microsoft.com/office365/admin/try-or-buy-microsoft-365) 하거나 Microsoft 365 Enterprise E5 [평가판에 등록할](https://www.microsoft.com/microsoft-365/enterprise) 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e1b2a-111">If you don't have an existing Microsoft 365 Enterprise E5 plan and want to try insider risk management, you can [add Microsoft 365](https://docs.microsoft.com/office365/admin/try-or-buy-microsoft-365) to your existing Office 365 subscription or [sign up for a trial](https://www.microsoft.com/microsoft-365/enterprise) of Microsoft 365 Enterprise E5.</span></span>
  
<span data-ttu-id="e1b2a-112">다음 단계를 완료 하 여 Microsoft 365 조직에서 통신 준수를 설정 및 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="e1b2a-112">Complete these steps to set up and use communication compliance in your Microsoft 365 organization:</span></span>

## <a name="step-1-required-enable-permissions-for-communication-compliance"></a><span data-ttu-id="e1b2a-113">1 단계 (필수 사항): 통신 준수에 대 한 사용 권한 설정</span><span class="sxs-lookup"><span data-stu-id="e1b2a-113">Step 1 (required): Enable permissions for communication compliance</span></span>

>[!Important]
><span data-ttu-id="e1b2a-114">기본적으로 전역 관리자는 통신 준수 기능에 액세스할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="e1b2a-114">By default, Global Administrators do not have access to communication compliance features.</span></span> <span data-ttu-id="e1b2a-115">이 단계에서 할당 된 역할은 통신 준수 기능에 액세스할 수 있으려면 먼저 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="e1b2a-115">The roles assigned in this step are required before any communication compliance features will be accessible.</span></span>

<span data-ttu-id="e1b2a-116">Microsoft 365 준수 센터에서 **통신 준수** 를 메뉴 옵션으로 사용할 수 있도록 하려면 **관리 검토 관리자** 역할이 할당 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e1b2a-116">To make **Communication compliance** available as a menu option in Microsoft 365 compliance center, you must be assigned the **Supervisory Review Administrator** role.</span></span> <span data-ttu-id="e1b2a-117">**관리 검토 관리자**, **사례 관리**및 **검토** 역할을 사용 하 여 검토자에 대 한 새 역할 그룹을 만들어 정책 일치 항목을 갖는 메시지를 조사 하 고 수정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e1b2a-117">You must create a new role group for reviewers with the **Supervisory Review Administrator**, **Case Management**, and **Review** roles to investigate and remediate messages with policy matches.</span></span>

### <a name="create-a-new-role-group"></a><span data-ttu-id="e1b2a-118">새 역할 그룹 만들기</span><span class="sxs-lookup"><span data-stu-id="e1b2a-118">Create a new role group</span></span>

1. <span data-ttu-id="e1b2a-119">Microsoft 365 [https://protection.office.com/permissions](https://protection.office.com/permissions) 조직의 관리자 계정에 대 한 자격 증명을 사용 하 여 로그인 합니다.</span><span class="sxs-lookup"><span data-stu-id="e1b2a-119">Sign into [https://protection.office.com/permissions](https://protection.office.com/permissions) using credentials for an admin account in your Microsoft 365 organization.</span></span>

2. <span data-ttu-id="e1b2a-120">Microsoft Office 365 보안 및 준수 센터에서 **사용 권한**으로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="e1b2a-120">In the Microsoft Office 365 security and compliance center, go to **Permissions**.</span></span> <span data-ttu-id="e1b2a-121">Office 365에서 역할을 보고 관리 하는 링크를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="e1b2a-121">Select the link to view and manage roles in Office 365.</span></span>

3. <span data-ttu-id="e1b2a-122">**만들기**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="e1b2a-122">Select **Create**.</span></span>

4. <span data-ttu-id="e1b2a-123">**이름** 필드에서 새 역할 그룹에 이름을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="e1b2a-123">In the **Name** field, give the new role group a friendly name.</span></span> <span data-ttu-id="e1b2a-124"> Select **Next**. </span><span class="sxs-lookup"><span data-stu-id="e1b2a-124">Select **Next**.</span></span>

5. <span data-ttu-id="e1b2a-125">**역할 선택을** 선택 하 고 **추가**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="e1b2a-125">Select **Choose roles** and then select **Add**.</span></span> <span data-ttu-id="e1b2a-126">**관리 검토 관리자**, **사례 관리**및 **검토**에 대 한 확인란을 선택 하 고 **추가** 및 **완료**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="e1b2a-126">Select the checkbox for **Supervisory Review Administrator**, **Case Management**, and **Review**, then select **Add** and **Done**.</span></span> <span data-ttu-id="e1b2a-127"> Select **Next**. </span><span class="sxs-lookup"><span data-stu-id="e1b2a-127">Select **Next**.</span></span>

    ![통신 준수 필수 역할 그룹](media/communication-compliance-role-groups.png)

6. <span data-ttu-id="e1b2a-129">**구성원 선택을** 선택 하 고 **추가**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="e1b2a-129">Select **Choose members** and then select **Add**.</span></span> <span data-ttu-id="e1b2a-130">정책을 만들 모든 사용자 및 그룹에 대 한 확인란을 선택 하 고 정책 일치가 포함 된 메시지를 관리 한 다음 **추가** 및 **완료**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="e1b2a-130">Select the checkbox for all the users and groups you want create policies and manage messages with policy matches, then select **Add** and **Done**.</span></span> <span data-ttu-id="e1b2a-131"> Select **Next**. </span><span class="sxs-lookup"><span data-stu-id="e1b2a-131">Select **Next**.</span></span>

7. <span data-ttu-id="e1b2a-132">마칠 **역할 그룹 만들기** 를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="e1b2a-132">Select **Create role group** to finish.</span></span>

<span data-ttu-id="e1b2a-133">역할 그룹 및 사용 권한에 대 한 자세한 내용은 [준수 센터의 사용 권한을](../security/office-365-security/protect-against-threats.md)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="e1b2a-133">For more information about role groups and permissions, see [Permissions in the Compliance Center](../security/office-365-security/protect-against-threats.md).</span></span>

## <a name="step-2-optional-set-up-groups-for-communication-compliance"></a><span data-ttu-id="e1b2a-134">2 단계 (선택 사항): 통신 준수를 위한 그룹 설정</span><span class="sxs-lookup"><span data-stu-id="e1b2a-134">Step 2 (optional): Set up groups for communication compliance</span></span>

 <span data-ttu-id="e1b2a-135">통신 준수 정책을 만들 때 통신을 검토 하 고 검토를 수행 하는 사람을 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="e1b2a-135">When you create a communication compliance policy, you define who has their communications reviewed and who performs reviews.</span></span> <span data-ttu-id="e1b2a-136">정책에서는 전자 메일 주소를 사용 하 여 개인 이나 사용자 그룹을 식별 합니다.</span><span class="sxs-lookup"><span data-stu-id="e1b2a-136">In the policy, you'll use email addresses to identify individuals or groups of people.</span></span> <span data-ttu-id="e1b2a-137">설정을 단순화 하기 위해 통신을 검토 한 사용자에 대 한 그룹을 만들고 해당 통신을 검토할 사용자에 대 한 그룹을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e1b2a-137">To simplify your setup, you can create groups for people who have their communication reviewed and groups for people who review those communications.</span></span> <span data-ttu-id="e1b2a-138">그룹을 사용 하는 경우 몇 가지 필요할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e1b2a-138">If you're using groups, you may need several.</span></span> <span data-ttu-id="e1b2a-139">예를 들어 서로 다른 두 사용자 그룹 간의 통신을 모니터링 하려는 경우 또는 감독 되지 않는 그룹을 지정 하려는 경우</span><span class="sxs-lookup"><span data-stu-id="e1b2a-139">For example, if you want to monitor communications between two distinct groups of people or if you want to specify a group that isn't going to be supervised.</span></span>

<span data-ttu-id="e1b2a-140">다음 차트를 사용 하 여 조직의 통신 준수 정책에 맞게 그룹을 구성 하는 방법을 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e1b2a-140">Use the following chart to help you configure groups in your organization for communication compliance policies:</span></span>

| <span data-ttu-id="e1b2a-141">**정책 구성원**</span><span class="sxs-lookup"><span data-stu-id="e1b2a-141">**Policy Member**</span></span> | <span data-ttu-id="e1b2a-142">**지원 되는 그룹**</span><span class="sxs-lookup"><span data-stu-id="e1b2a-142">**Supported Groups**</span></span> | <span data-ttu-id="e1b2a-143">**지원 되지 않는 그룹**</span><span class="sxs-lookup"><span data-stu-id="e1b2a-143">**Unsupported Groups**</span></span> |
|:-----|:-----|:-----|
|<span data-ttu-id="e1b2a-144">감독 사용자</span><span class="sxs-lookup"><span data-stu-id="e1b2a-144">Supervised users</span></span> <br> <span data-ttu-id="e1b2a-145">감독 되지 않은 사용자</span><span class="sxs-lookup"><span data-stu-id="e1b2a-145">Non-supervised users</span></span> | <span data-ttu-id="e1b2a-146">메일 그룹</span><span class="sxs-lookup"><span data-stu-id="e1b2a-146">Distribution groups</span></span> <br> <span data-ttu-id="e1b2a-147">Office 365 그룹</span><span class="sxs-lookup"><span data-stu-id="e1b2a-147">Office 365 groups</span></span> | <span data-ttu-id="e1b2a-148">동적 메일 그룹</span><span class="sxs-lookup"><span data-stu-id="e1b2a-148">Dynamic distribution groups</span></span> |
| <span data-ttu-id="e1b2a-149">가</span><span class="sxs-lookup"><span data-stu-id="e1b2a-149">Reviewers</span></span> | <span data-ttu-id="e1b2a-150">메일 사용 가능 보안 그룹</span><span class="sxs-lookup"><span data-stu-id="e1b2a-150">Mail-enabled security groups</span></span>  | <span data-ttu-id="e1b2a-151">메일 그룹</span><span class="sxs-lookup"><span data-stu-id="e1b2a-151">Distribution groups</span></span> <br> <span data-ttu-id="e1b2a-152">동적 메일 그룹</span><span class="sxs-lookup"><span data-stu-id="e1b2a-152">Dynamic distribution groups</span></span> |
  
<span data-ttu-id="e1b2a-153">감독 되는 사용자에 대 한 Office 365 그룹을 선택 하면 정책이 공유 Office 365 사서함의 콘텐츠 및 해당 그룹과 연결 된 Microsoft 팀 채널을 모니터링 합니다.</span><span class="sxs-lookup"><span data-stu-id="e1b2a-153">When you select an Office 365 group for supervised users, the policy monitors the content of the shared Office 365 mailbox and the Microsoft Teams channels associated with the group.</span></span> <span data-ttu-id="e1b2a-154">메일 그룹을 선택 하는 경우 정책은 개별 사용자 사서함을 모니터링 합니다.</span><span class="sxs-lookup"><span data-stu-id="e1b2a-154">When you select a distribution list, the policy monitors individual user mailboxes.</span></span>

<span data-ttu-id="e1b2a-155">그룹을 설정 하는 방법에 대 한 자세한 내용은 다음을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="e1b2a-155">For more information about setting up groups, see:</span></span>

- [<span data-ttu-id="e1b2a-156">메일 그룹 만들기 및 관리</span><span class="sxs-lookup"><span data-stu-id="e1b2a-156">Create and manage distribution groups</span></span>](https://docs.microsoft.com/Exchange/recipients-in-exchange-online/manage-distribution-groups/manage-distribution-groups)
- [<span data-ttu-id="e1b2a-157">메일 사용 가능 보안 그룹 관리</span><span class="sxs-lookup"><span data-stu-id="e1b2a-157">Manage mail-enabled security groups</span></span>](https://docs.microsoft.com/Exchange/recipients-in-exchange-online/manage-mail-enabled-security-groups)
- [<span data-ttu-id="e1b2a-158">Office 365 그룹 개요</span><span class="sxs-lookup"><span data-stu-id="e1b2a-158">Overview of Office 365 Groups</span></span>](https://docs.microsoft.com/office365/admin/create-groups/office-365-groups?view=o365-worldwide)

## <a name="step-3-required-create-a-communication-compliance-policy"></a><span data-ttu-id="e1b2a-159">3 단계 (필수 사항): 통신 준수 정책 만들기</span><span class="sxs-lookup"><span data-stu-id="e1b2a-159">Step 3 (required): Create a communication compliance policy</span></span>
  
1. <span data-ttu-id="e1b2a-160">Microsoft 365 [https://compliance.microsoft.com](https://compliance.microsoft.com) 조직의 관리자 계정에 대 한 자격 증명을 사용 하 여 로그인 합니다.</span><span class="sxs-lookup"><span data-stu-id="e1b2a-160">Sign into [https://compliance.microsoft.com](https://compliance.microsoft.com) using credentials for an admin account in your Microsoft 365 organization.</span></span>

2. <span data-ttu-id="e1b2a-161">Microsoft 365 준수 센터에서 **통신 준수**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="e1b2a-161">In the Microsoft 365 compliance center, select **Communication compliance**.</span></span>
  
3. <span data-ttu-id="e1b2a-162">**정책** 탭을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="e1b2a-162">Select the **Policies** tab.</span></span>

4. <span data-ttu-id="e1b2a-163">**정책 만들기** 를 선택 하 여 템플릿에서 새 정책을 만들고 구성 하거나 사용자 지정 정책을 만들고 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="e1b2a-163">Select **Create policy** to create and configure a new policy from a template or to create and configure a custom policy.</span></span>

    <span data-ttu-id="e1b2a-164">정책을 만들기 위해 정책 템플릿을 선택 하는 경우 다음을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="e1b2a-164">If you choose a policy template to create a policy, you will:</span></span>

    - <span data-ttu-id="e1b2a-165">정책 이름을 확인 하거나 업데이트 합니다.</span><span class="sxs-lookup"><span data-stu-id="e1b2a-165">Confirm or update the policy name.</span></span> <span data-ttu-id="e1b2a-166">정책을 만든 후에는 정책 이름을 변경할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="e1b2a-166">Policy names cannot be changed once the policy is created.</span></span>
    - <span data-ttu-id="e1b2a-167">제외할 사용자 또는 그룹 선택을 비롯 하 여 감독할 사용자 또는 그룹을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="e1b2a-167">Choose the users or groups to supervise, including choosing users or groups you'd like to exclude.</span></span>
    - <span data-ttu-id="e1b2a-168">정책에 대 한 검토자를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="e1b2a-168">Choose the reviewers for the policy.</span></span> <span data-ttu-id="e1b2a-169">검토자는 개별 사용자 또는 [메일 사용이 가능한 보안 그룹이](https://docs.microsoft.com/Exchange/recipients-in-exchange-online/manage-mail-enabled-security-groups#create-a-mail-enabled-security-group)될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e1b2a-169">Reviewers can be individual users or [mail-enabled security groups](https://docs.microsoft.com/Exchange/recipients-in-exchange-online/manage-mail-enabled-security-groups#create-a-mail-enabled-security-group).</span></span> <span data-ttu-id="e1b2a-170">모든 검토자에 게 Exchange Online에서 호스트 되는 사서함이 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e1b2a-170">All reviewers must have mailboxes hosted on Exchange Online.</span></span>
    - <span data-ttu-id="e1b2a-171">정책에 적용할 제한 된 조건 필드 (일반적으로 중요 한 정보 유형 또는 키워드 사전)를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="e1b2a-171">Choose a limited condition field, usually a sensitive info type or keyword dictionary to apply to the policy.</span></span>

    <span data-ttu-id="e1b2a-172">정책 마법사를 사용 하 여 사용자 지정 정책을 만드는 경우 다음을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="e1b2a-172">If you choose to use the policy wizard to create a custom policy, you will:</span></span>

    - <span data-ttu-id="e1b2a-173">정책에 이름과 설명을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="e1b2a-173">Give the policy a name and description.</span></span> <span data-ttu-id="e1b2a-174">정책을 만든 후에는 정책 이름을 변경할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="e1b2a-174">Policy names can't be changed once the policy is created.</span></span>
    - <span data-ttu-id="e1b2a-175">조직의 모든 사용자, 특정 사용자 및 그룹, 제외 하려는 기타 사용자 및 그룹을 비롯 하 여 감독할 사용자 또는 그룹을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="e1b2a-175">Choose the users or groups to supervise, including all users in your organization, specific users and groups, or other users and groups you'd like to exclude.</span></span> -
    - <span data-ttu-id="e1b2a-176">정책에 대 한 검토자를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="e1b2a-176">Choose the reviewers for the policy.</span></span> <span data-ttu-id="e1b2a-177">검토자는 개별 사용자 또는 [메일 사용이 가능한 보안 그룹이](https://docs.microsoft.com/Exchange/recipients-in-exchange-online/manage-mail-enabled-security-groups#create-a-mail-enabled-security-group)될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e1b2a-177">Reviewers can be individual users or [mail-enabled security groups](https://docs.microsoft.com/Exchange/recipients-in-exchange-online/manage-mail-enabled-security-groups#create-a-mail-enabled-security-group).</span></span> <span data-ttu-id="e1b2a-178">모든 검토자에 게 Exchange Online에서 호스트 되는 사서함이 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e1b2a-178">All reviewers must have mailboxes hosted on Exchange Online.</span></span>
    - <span data-ttu-id="e1b2a-179">Exchange, Microsoft 팀 또는 비즈니스용 Skype를 포함 하 여 검색할 통신 채널을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="e1b2a-179">Choose the communication channels to scan, including Exchange, Microsoft Teams, or Skype for Business.</span></span> <span data-ttu-id="e1b2a-180">또한 Microsoft 365에서 커넥터를 구성한 경우 타사 출처를 검색 하도록 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="e1b2a-180">You'll also choose to scan third-party sources if you've configured a connector in Microsoft 365.</span></span>
    - <span data-ttu-id="e1b2a-181">인바운드, 아웃 바운드 또는 내부 통신을 포함 하 여 모니터링할 통신 방향을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="e1b2a-181">Choose the communication direction to monitor, including inbound, outbound, or internal communications.</span></span>
    - <span data-ttu-id="e1b2a-182">통신 준수 정책 [조건을](communication-compliance-feature-reference.md#ConditionalSettings)정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="e1b2a-182">Define the communication compliance policy [conditions](communication-compliance-feature-reference.md#ConditionalSettings).</span></span> <span data-ttu-id="e1b2a-183">메시지 주소, 키워드, 파일 형식 및 크기 일치 조건에서 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e1b2a-183">You can choose from message address, keyword, file types, and size match conditions.</span></span>
    - <span data-ttu-id="e1b2a-184">중요 한 정보 유형을 포함 하 고 싶은 경우 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="e1b2a-184">Choose if you'd like to include sensitive information types.</span></span> <span data-ttu-id="e1b2a-185">이 단계에서는 기본 및 사용자 지정 중요 한 정보 유형을 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e1b2a-185">This step is where you can select default and custom sensitive info types.</span></span> <span data-ttu-id="e1b2a-186">통신 준수 정책 마법사의 기존 사용자 지정 중요 한 정보 유형 또는 사용자 지정 키워드 사전을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="e1b2a-186">Pick from existing custom sensitive information types or custom keyword dictionaries in the communication compliance policy wizard.</span></span> <span data-ttu-id="e1b2a-187">필요한 경우 마법사를 실행 하기 전에 이러한 항목을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e1b2a-187">You can create these items before running the wizard if needed.</span></span> <span data-ttu-id="e1b2a-188">또한 통신 준수 정책 마법사 내에서 새 중요 한 정보 유형을 만들 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e1b2a-188">You can also create new sensitive information types from within the communication compliance policy wizard.</span></span>
    - <span data-ttu-id="e1b2a-189">공격적인 언어 분류자를 사용 하도록 설정 하려면 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="e1b2a-189">Choose if you'd like to enable the offensive language classifier.</span></span> <span data-ttu-id="e1b2a-190">이 분류자는 전자 메일 메시지 본문에서 보내거나 받은 부적절 한 언어를 검색 합니다.</span><span class="sxs-lookup"><span data-stu-id="e1b2a-190">This  classifier detects inappropriate language sent or received in the body of email messages.</span></span>
    - <span data-ttu-id="e1b2a-191">검토할 통신의 비율을 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="e1b2a-191">Define the percentage of communications to review.</span></span>
    - <span data-ttu-id="e1b2a-192">정책 선택을 검토 하 고 정책을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="e1b2a-192">Review your policy selections and create the policy.</span></span>

5. <span data-ttu-id="e1b2a-193">서식 파일을 사용 하는 경우 **정책 만들기** 또는 사용자 지정 정책 마법사를 사용할 때 **제출을** 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="e1b2a-193">Select **Create policy** when using the templates or **Submit** when using the custom policy wizard.</span></span>

6. <span data-ttu-id="e1b2a-194">정책이 활성화 되는 시기와 캡처할 통신에 대 한 지침과 함께 **정책 만들기** 페이지가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e1b2a-194">The **Your policy was created** page is displayed with guidelines on when policy will be activated and which communications will be captured.</span></span>

## <a name="step-4-optional-create-employee-notice-templates"></a><span data-ttu-id="e1b2a-195">4 단계 (선택 사항): 직원 공지 서식 파일 만들기</span><span class="sxs-lookup"><span data-stu-id="e1b2a-195">Step 4 (optional): Create employee notice templates</span></span>

<span data-ttu-id="e1b2a-196">관련 직원에 게 미리 알림 메시지를 보내 정책 경고에 응답 하는 옵션을 설정 하려면 조직에 공지 서식 파일을 하나 이상 만들어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e1b2a-196">If you want to have the option of responding to a policy alert by sending a reminder notice to the associated employee, you'll need to create at least one notice template in your organization.</span></span> <span data-ttu-id="e1b2a-197">알림 서식 파일 필드는 경고 업데이트 관리 프로세스의 일부로 전송 되기 전에 편집 가능 하 게 되며 각 통신 준수 정책에 대해 사용자 지정 된 공지 서식 파일을 만드는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="e1b2a-197">The notice template fields are editable before they're sent as part of the alert remediation process, and creating a customized notice template for each communication compliance policy is recommended.</span></span>

1. <span data-ttu-id="e1b2a-198">Microsoft 365 [https://compliance.microsoft.com](https://compliance.microsoft.com) 조직의 관리자 계정에 대 한 자격 증명을 사용 하 여 로그인 합니다.</span><span class="sxs-lookup"><span data-stu-id="e1b2a-198">Sign into [https://compliance.microsoft.com](https://compliance.microsoft.com) using credentials for an admin account in your Microsoft 365 organization.</span></span>

2. <span data-ttu-id="e1b2a-199">Microsoft 365 준수 센터에서 **통신 준수**로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="e1b2a-199">In the Microsoft 365 compliance center, go to **Communication compliance**.</span></span>

3. <span data-ttu-id="e1b2a-200">**공지 템플릿** 탭을 선택한 다음 **공지 템플릿 만들기**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="e1b2a-200">Select the **Notice templates** tab and then select **Create notice template**.</span></span>

4. <span data-ttu-id="e1b2a-201">**공지 서식 파일 수정** 페이지에서 다음 필드를 작성 합니다.</span><span class="sxs-lookup"><span data-stu-id="e1b2a-201">On the **Modify a notice template** page, complete the following fields:</span></span>

    - <span data-ttu-id="e1b2a-202">주의 서식 파일 이름 (필수)</span><span class="sxs-lookup"><span data-stu-id="e1b2a-202">Notice template name (required)</span></span>
    - <span data-ttu-id="e1b2a-203">보내기 (필수)</span><span class="sxs-lookup"><span data-stu-id="e1b2a-203">Send from (required)</span></span>
    - <span data-ttu-id="e1b2a-204">참조 및 숨은 참조 (선택 사항)</span><span class="sxs-lookup"><span data-stu-id="e1b2a-204">Cc and Bcc (optional)</span></span>
    - <span data-ttu-id="e1b2a-205">제목 (필수)</span><span class="sxs-lookup"><span data-stu-id="e1b2a-205">Subject (required)</span></span>
    - <span data-ttu-id="e1b2a-206">메시지 본문 (필수)</span><span class="sxs-lookup"><span data-stu-id="e1b2a-206">Message body (required)</span></span>

5. <span data-ttu-id="e1b2a-207">**저장** 을 선택 하 여 알림 서식 파일을 만들고 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="e1b2a-207">Select **Save** to create and save the notice template.</span></span>

## <a name="step-5-optional-test-your-communication-compliance-policy"></a><span data-ttu-id="e1b2a-208">5 단계 (선택 사항): 통신 준수 정책 테스트</span><span class="sxs-lookup"><span data-stu-id="e1b2a-208">Step 5 (optional): Test your communication compliance policy</span></span>

<span data-ttu-id="e1b2a-209">통신 준수 정책을 만든 후에는 테스트를 통해 정의한 조건이 정책에 의해 적절 하 게 적용 되는지 확인 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="e1b2a-209">After you create a communication compliance policy, it's a good idea to test it to make sure that the conditions you defined are being properly enforced by the policy.</span></span> <span data-ttu-id="e1b2a-210">또한 통신 준수 정책에 중요 한 정보 유형이 포함 되어 있는 경우 [DLP (데이터 손실 방지) 정책을 테스트할](create-test-tune-dlp-policy.md) 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e1b2a-210">You may also want to [test your data loss prevention (DLP) policies](create-test-tune-dlp-policy.md) if your communication compliance policies include sensitive information types.</span></span> <span data-ttu-id="e1b2a-211">테스트할 통신을 캡처할 수 있도록 정책에 대 한 정품 인증을 제공 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e1b2a-211">Make sure you give your policies time to activate so that the communications you want to test are captured.</span></span>

<span data-ttu-id="e1b2a-212">다음 단계에 따라 통신 준수 정책을 테스트 합니다.</span><span class="sxs-lookup"><span data-stu-id="e1b2a-212">Follow these steps to test your communication compliance policy:</span></span>

1. <span data-ttu-id="e1b2a-213">테스트할 정책에 정의 된 감독 된 사용자로 로그인 한 상태에서 전자 메일 클라이언트 또는 Microsoft 팀을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="e1b2a-213">Open an email client or Microsoft Teams while signed in as a supervised user defined in the policy you want to test.</span></span>
2. <span data-ttu-id="e1b2a-214">통신 준수 정책에 정의한 기준을 충족 하는 전자 메일 또는 Microsoft 팀 채팅을 보냅니다.</span><span class="sxs-lookup"><span data-stu-id="e1b2a-214">Send an email or Microsoft Teams chat that meets the criteria you've defined in the communication compliance policy.</span></span> <span data-ttu-id="e1b2a-215">이 테스트는 키워드, 첨부 파일 크기, 도메인 등이 될 수 있습니다. 정책에서 구성 된 조건부 설정이 너무 제한적일 또는 너무 lenient 인지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="e1b2a-215">This test can be a keyword, attachment size, domain, etc. Make sure you determine if your configured conditional settings in the policy are too restrictive or too lenient.</span></span>

    > [!NOTE]
    > <span data-ttu-id="e1b2a-216">모든 원본 채널의 통신은 정책에서 완전히 처리 되는 데 최대 24 시간이 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e1b2a-216">Communications in all source channels can take up to 24 hours to fully process in a policy.</span></span>

3. <span data-ttu-id="e1b2a-217">통신 준수 정책에 지정 된 검토자로 Microsoft 365에 로그인 합니다.</span><span class="sxs-lookup"><span data-stu-id="e1b2a-217">Sign in to Microsoft 365 as a reviewer designated in the communication compliance policy.</span></span> <span data-ttu-id="e1b2a-218">정책에 대 한 경고를 보려면 **통신 준수** > **알림과** 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="e1b2a-218">Navigate to **Communication compliance** > **Alerts** to view the alerts for your policies.</span></span>

4. <span data-ttu-id="e1b2a-219">업데이트 관리 컨트롤을 사용 하 여 경고를 수정 하 고 경고가 제대로 확인 되는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="e1b2a-219">Remediate the alert using the remediation controls and verify that the alert is properly resolved.</span></span>

## <a name="step-6-optional-enable-auditing-for-your-communication-compliance-policies"></a><span data-ttu-id="e1b2a-220">6 단계 (선택 사항): 통신 준수 정책에 대 한 감사 사용</span><span class="sxs-lookup"><span data-stu-id="e1b2a-220">Step 6 (optional): Enable auditing for your communication compliance policies</span></span>

<span data-ttu-id="e1b2a-221">정책을 테스트 한 후에는 통신 준수 관리와 관련 된 활동이 기록 되도록 감사를 사용 하도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e1b2a-221">After you've tested your policies, you may want to enable auditing so that activities associated with communication compliance management are recorded.</span></span> <span data-ttu-id="e1b2a-222">이 감사는 정의 된 조직 정책과 관련 된 모든 작업 또는 통신 준수 정책이 변경 될 때마다 요약 된 것일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e1b2a-222">This audit may be a summary of all activities associated with a defined organizational policy or anytime a communication compliance policy changes.</span></span>

<span data-ttu-id="e1b2a-223">감사를 사용 하도록 설정 하면 통신 준수 정책에 내부 또는 외부 감사에 대 한 전체 준비 상태에 대 한 감사 기록이 기본적으로 제공 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e1b2a-223">When auditing is enabled, communication compliance policies have built-in audit trails for complete readiness for internal or external audits.</span></span> <span data-ttu-id="e1b2a-224">감사를 사용 하도록 설정 된 경우 정책에 대 한 기본 페이지의 **검토 작업 내보내기** 컨트롤을 사용 하 여 감사 파일을 생성 하거나 감사 작업을 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e1b2a-224">You can use the **Export review activities** control on the main page for any policy to generate an audit file or view audit activities in the unified audit log if auditing is enabled.</span></span>

<span data-ttu-id="e1b2a-225">감사를 설정 하려면 Office 365 보안 & 준수 센터의 **감사 로그 검색** 페이지에서 **사용자 및 관리자 작업 기록을 시작** 합니다 .를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="e1b2a-225">To turn on auditing, click **Start recording user and admin activity** on the **Audit log search** page in the Office 365 Security & Compliance Center.</span></span> <span data-ttu-id="e1b2a-226">이 링크가 표시되지 않으면 조직에 대해 감사가 이미 켜져 있는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="e1b2a-226">If you don't see this link, auditing has already been turned on for your organization.</span></span> <span data-ttu-id="e1b2a-227">감사를 설정한 후에는 감사 로그를 준비 중 이며 준비 완료 후 몇 시간 내에 검색을 실행할 수 있음을 알리는 메시지가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e1b2a-227">After you turn on auditing, a message is displayed that says the audit log is being prepared and that you can run a search in a couple of hours after the preparation is complete.</span></span> <span data-ttu-id="e1b2a-228">이 작업은 한 번만 수행 하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e1b2a-228">You only have to do this action once.</span></span> <span data-ttu-id="e1b2a-229">감사 로그에 대 한 자세한 내용은 Search the [audit log](search-the-audit-log-in-security-and-compliance.md)을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="e1b2a-229">For more information about the audit log, see [Search the audit log](search-the-audit-log-in-security-and-compliance.md).</span></span>
