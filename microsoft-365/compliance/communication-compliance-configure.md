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
ms.openlocfilehash: 82ee16e84bc20b88e577cfd3e8b8187059536469
ms.sourcegitcommit: 0f09f54f43924d1fcd2fdcfcbf04c53519b92a7b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/05/2020
ms.locfileid: "41784695"
---
# <a name="configure-communication-compliance-in-microsoft-365"></a><span data-ttu-id="81c12-103">Microsoft 365에서 통신 준수 구성</span><span class="sxs-lookup"><span data-stu-id="81c12-103">Configure communication compliance in Microsoft 365</span></span>

>[!IMPORTANT]
><span data-ttu-id="81c12-104">이 항목은 Microsoft 365 구독의 통신 준수 구성에 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="81c12-104">This topic applies to configuring communication compliance in a Microsoft 365 subscription.</span></span> <span data-ttu-id="81c12-105">Office 365 구독에 대 한 감독 정책을 구성 하려면 [office 365에 대 한 감독 구성을](supervision-policies.md)참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="81c12-105">If you want to configure Supervision policies for an Office 365 subscription, see [Configure supervision for Office 365](supervision-policies.md).</span></span>

<span data-ttu-id="81c12-106">통신 준수 정책을 사용 하 여 내부 또는 외부 검토자가 검사할 직원 통신을 캡처할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="81c12-106">Use communication compliance policies to capture employee communications for examination by internal or external reviewers.</span></span> <span data-ttu-id="81c12-107">통신 준수 정책을 통해 조직의 통신을 모니터링 하는 방법에 대 한 자세한 내용은 [Microsoft 365의 통신 준수 정책을](communication-compliance.md)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="81c12-107">For more information about how communication compliance policies can help you monitor communications in your organization, see [communication compliance policies in Microsoft 365](communication-compliance.md).</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="81c12-108">시작하기 전에</span><span class="sxs-lookup"><span data-stu-id="81c12-108">Before you begin</span></span>

<span data-ttu-id="81c12-109">통신 준수를 시작 하기 전에 Microsoft 365 구독을 확인 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="81c12-109">Before you get started with communication compliance, you should confirm your Microsoft 365 subscription.</span></span> <span data-ttu-id="81c12-110">통신 준수 정책에 포함 된 사용자에 게는 Microsoft 365 E5 준수 라이선스, 고급 준수 추가 기능이 포함 된 Office 365 Enterprise E3 라이선스 또는 Microsoft 365 E5 구독에 포함 되어 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="81c12-110">Users included in communication compliance policies must have a Microsoft 365 E5 Compliance license, an Office 365 Enterprise E3 license with the Advanced Compliance add-on, or be included in a Microsoft 365 E5 subscription.</span></span>

<span data-ttu-id="81c12-111">Microsoft 365 Enterprise E5 요금제가 아직 없는 경우 microsoft 365을 기존 Office 365 구독에 [추가](https://docs.microsoft.com/office365/admin/try-or-buy-microsoft-365) 하거나 Microsoft 365 Enterprise E5 [평가판에 등록할](https://www.microsoft.com/microsoft-365/enterprise) 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="81c12-111">If you don't have an existing Microsoft 365 Enterprise E5 plan and want to try insider risk management, you can [add Microsoft 365](https://docs.microsoft.com/office365/admin/try-or-buy-microsoft-365) to your existing Office 365 subscription or [sign up for a trial](https://www.microsoft.com/microsoft-365/enterprise) of Microsoft 365 Enterprise E5.</span></span>
  
<span data-ttu-id="81c12-112">다음 단계를 완료 하 여 Microsoft 365 조직에서 통신 준수를 설정 및 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="81c12-112">Complete these steps to set up and use communication compliance in your Microsoft 365 organization:</span></span>

## <a name="step-1-required-enable-permissions-for-communication-compliance"></a><span data-ttu-id="81c12-113">1 단계 (필수 사항): 통신 준수에 대 한 사용 권한 설정</span><span class="sxs-lookup"><span data-stu-id="81c12-113">Step 1 (required): Enable permissions for communication compliance</span></span>

>[!Important]
><span data-ttu-id="81c12-114">기본적으로 전역 관리자는 통신 준수 기능에 액세스할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="81c12-114">By default, Global Administrators do not have access to communication compliance features.</span></span> <span data-ttu-id="81c12-115">이 단계에서 할당 된 역할은 통신 준수 기능에 액세스할 수 있으려면 먼저 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="81c12-115">The roles assigned in this step are required before any communication compliance features will be accessible.</span></span>

<span data-ttu-id="81c12-116">Microsoft 365 준수 센터에서 **통신 준수** 를 메뉴 옵션으로 사용할 수 있도록 하려면 **관리 검토 관리자** 역할이 할당 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="81c12-116">To make **Communication compliance** available as a menu option in Microsoft 365 compliance center, you must be assigned the **Supervisory Review Administrator** role.</span></span> <span data-ttu-id="81c12-117">**관리 검토 관리자**, **사례 관리**및 **검토** 역할을 사용 하 여 검토자에 대 한 새 역할 그룹을 만들어 정책 일치 항목을 갖는 메시지를 조사 하 고 수정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="81c12-117">You must create a new role group for reviewers with the **Supervisory Review Administrator**, **Case Management**, and **Review** roles to investigate and remediate messages with policy matches.</span></span>

### <a name="create-a-new-role-group"></a><span data-ttu-id="81c12-118">새 역할 그룹 만들기</span><span class="sxs-lookup"><span data-stu-id="81c12-118">Create a new role group</span></span>

1. <span data-ttu-id="81c12-119">Microsoft 365 [https://protection.office.com/permissions](https://protection.office.com/permissions) 조직의 관리자 계정에 대 한 자격 증명을 사용 하 여 로그인 합니다.</span><span class="sxs-lookup"><span data-stu-id="81c12-119">Sign into [https://protection.office.com/permissions](https://protection.office.com/permissions) using credentials for an admin account in your Microsoft 365 organization.</span></span>

2. <span data-ttu-id="81c12-120">Microsoft Office 365 보안 및 준수 센터에서 **사용 권한**으로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="81c12-120">In the Microsoft Office 365 security and compliance center, go to **Permissions**.</span></span> <span data-ttu-id="81c12-121">Office 365에서 역할을 보고 관리 하는 링크를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="81c12-121">Select the link to view and manage roles in Office 365.</span></span>

3. <span data-ttu-id="81c12-122">**만들기**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="81c12-122">Select **Create**.</span></span>

4. <span data-ttu-id="81c12-123">**이름** 필드에서 새 역할 그룹에 이름을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="81c12-123">In the **Name** field, give the new role group a friendly name.</span></span> <span data-ttu-id="81c12-124"> Select **Next**. </span><span class="sxs-lookup"><span data-stu-id="81c12-124">Select **Next**.</span></span>

5. <span data-ttu-id="81c12-125">**역할 선택을** 선택 하 고 **추가**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="81c12-125">Select **Choose roles** and then select **Add**.</span></span> <span data-ttu-id="81c12-126">**관리 검토 관리자**, **사례 관리**및 **검토**에 대 한 확인란을 선택 하 고 **추가** 및 **완료**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="81c12-126">Select the checkbox for **Supervisory Review Administrator**, **Case Management**, and **Review**, then select **Add** and **Done**.</span></span> <span data-ttu-id="81c12-127"> Select **Next**. </span><span class="sxs-lookup"><span data-stu-id="81c12-127">Select **Next**.</span></span>

    ![통신 준수 필수 역할 그룹](media/communication-compliance-role-groups.png)

6. <span data-ttu-id="81c12-129">**구성원 선택을** 선택 하 고 **추가**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="81c12-129">Select **Choose members** and then select **Add**.</span></span> <span data-ttu-id="81c12-130">정책을 만들 모든 사용자 및 그룹에 대 한 확인란을 선택 하 고 정책 일치가 포함 된 메시지를 관리 한 다음 **추가** 및 **완료**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="81c12-130">Select the checkbox for all the users and groups you want create policies and manage messages with policy matches, then select **Add** and **Done**.</span></span> <span data-ttu-id="81c12-131"> Select **Next**. </span><span class="sxs-lookup"><span data-stu-id="81c12-131">Select **Next**.</span></span>

7. <span data-ttu-id="81c12-132">마칠 **역할 그룹 만들기** 를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="81c12-132">Select **Create role group** to finish.</span></span>

<span data-ttu-id="81c12-133">역할 그룹 및 사용 권한에 대 한 자세한 내용은 [준수 센터의 사용 권한을](../security/office-365-security/protect-against-threats.md)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="81c12-133">For more information about role groups and permissions, see [Permissions in the Compliance Center](../security/office-365-security/protect-against-threats.md).</span></span>

## <a name="step-2-required-enable-the-office-365-audit-log"></a><span data-ttu-id="81c12-134">2 단계 (필수 사항): Office 365 감사 로그 사용</span><span class="sxs-lookup"><span data-stu-id="81c12-134">Step 2 (required): Enable the Office 365 audit log</span></span>

<span data-ttu-id="81c12-135">통신 준수를 위해서는 감사 로그가 알림을 표시 하 고 검토자가 수행한 업데이트 관리 작업을 추적 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="81c12-135">Communication compliance requires audit logs to show alerts and track remediation actions taken by reviewers.</span></span> <span data-ttu-id="81c12-136">감사 로그는 정의 된 조직 정책과 관련 된 모든 작업을 요약 한 것 이거나, 통신 준수 정책이 변경 되는 경우에도 해당 됩니다.</span><span class="sxs-lookup"><span data-stu-id="81c12-136">The audit logs are a summary of all activities associated with a defined organizational policy or anytime a communication compliance policy changes.</span></span>

<span data-ttu-id="81c12-137">감사를 설정 하는 단계별 지침은 [Turn Office 365 감사 로그 검색 설정 또는 해제](turn-audit-log-search-on-or-off.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="81c12-137">For step-by-step instructions to turn on auditing, see [Turn Office 365 audit log search on or off](turn-audit-log-search-on-or-off.md).</span></span> <span data-ttu-id="81c12-138">감사를 설정한 후에는 감사 로그를 준비 중 이며 준비 완료 후 몇 시간 내에 검색을 실행할 수 있음을 알리는 메시지가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="81c12-138">After you turn on auditing, a message is displayed that says the audit log is being prepared and that you can run a search in a couple of hours after the preparation is complete.</span></span> <span data-ttu-id="81c12-139">이 작업은 한 번만 수행 하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="81c12-139">You only have to do this action once.</span></span> <span data-ttu-id="81c12-140">감사 로그를 사용 하는 방법에 대 한 자세한 내용은 [Search the audit log](search-the-audit-log-in-security-and-compliance.md)을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="81c12-140">For more information about the using the audit log, see [Search the audit log](search-the-audit-log-in-security-and-compliance.md).</span></span>


## <a name="step-3-optional-set-up-groups-for-communication-compliance"></a><span data-ttu-id="81c12-141">3 단계 (선택 사항): 통신 준수를 위한 그룹 설정</span><span class="sxs-lookup"><span data-stu-id="81c12-141">Step 3 (optional): Set up groups for communication compliance</span></span>

 <span data-ttu-id="81c12-142">통신 준수 정책을 만들 때 통신을 검토 하 고 검토를 수행 하는 사람을 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="81c12-142">When you create a communication compliance policy, you define who has their communications reviewed and who performs reviews.</span></span> <span data-ttu-id="81c12-143">정책에서는 전자 메일 주소를 사용 하 여 개인 이나 사용자 그룹을 식별 합니다.</span><span class="sxs-lookup"><span data-stu-id="81c12-143">In the policy, you'll use email addresses to identify individuals or groups of people.</span></span> <span data-ttu-id="81c12-144">설정을 단순화 하기 위해 통신을 검토 한 사용자에 대 한 그룹을 만들고 해당 통신을 검토할 사용자에 대 한 그룹을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="81c12-144">To simplify your setup, you can create groups for people who have their communication reviewed and groups for people who review those communications.</span></span> <span data-ttu-id="81c12-145">그룹을 사용 하는 경우 몇 가지 필요할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="81c12-145">If you're using groups, you may need several.</span></span> <span data-ttu-id="81c12-146">예를 들어 서로 다른 두 사용자 그룹 간의 통신을 모니터링 하려는 경우 또는 감독 되지 않는 그룹을 지정 하려는 경우</span><span class="sxs-lookup"><span data-stu-id="81c12-146">For example, if you want to monitor communications between two distinct groups of people or if you want to specify a group that isn't going to be supervised.</span></span>

<span data-ttu-id="81c12-147">다음 차트를 사용 하 여 조직의 통신 준수 정책에 맞게 그룹을 구성 하는 방법을 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="81c12-147">Use the following chart to help you configure groups in your organization for communication compliance policies:</span></span>

| <span data-ttu-id="81c12-148">**정책 구성원**</span><span class="sxs-lookup"><span data-stu-id="81c12-148">**Policy Member**</span></span> | <span data-ttu-id="81c12-149">**지원 되는 그룹**</span><span class="sxs-lookup"><span data-stu-id="81c12-149">**Supported Groups**</span></span> | <span data-ttu-id="81c12-150">**지원 되지 않는 그룹**</span><span class="sxs-lookup"><span data-stu-id="81c12-150">**Unsupported Groups**</span></span> |
|:-----|:-----|:-----|
|<span data-ttu-id="81c12-151">감독 사용자</span><span class="sxs-lookup"><span data-stu-id="81c12-151">Supervised users</span></span> <br> <span data-ttu-id="81c12-152">감독 되지 않은 사용자</span><span class="sxs-lookup"><span data-stu-id="81c12-152">Non-supervised users</span></span> | <span data-ttu-id="81c12-153">메일 그룹</span><span class="sxs-lookup"><span data-stu-id="81c12-153">Distribution groups</span></span> <br> <span data-ttu-id="81c12-154">Office 365 그룹</span><span class="sxs-lookup"><span data-stu-id="81c12-154">Office 365 groups</span></span> | <span data-ttu-id="81c12-155">동적 메일 그룹</span><span class="sxs-lookup"><span data-stu-id="81c12-155">Dynamic distribution groups</span></span> |
| <span data-ttu-id="81c12-156">가</span><span class="sxs-lookup"><span data-stu-id="81c12-156">Reviewers</span></span> | <span data-ttu-id="81c12-157">메일 사용 가능 보안 그룹</span><span class="sxs-lookup"><span data-stu-id="81c12-157">Mail-enabled security groups</span></span>  | <span data-ttu-id="81c12-158">메일 그룹</span><span class="sxs-lookup"><span data-stu-id="81c12-158">Distribution groups</span></span> <br> <span data-ttu-id="81c12-159">동적 메일 그룹</span><span class="sxs-lookup"><span data-stu-id="81c12-159">Dynamic distribution groups</span></span> |
  
<span data-ttu-id="81c12-160">감독 되는 사용자에 대 한 Office 365 그룹을 선택 하면 정책이 공유 Office 365 사서함의 콘텐츠 및 해당 그룹과 연결 된 Microsoft 팀 채널을 모니터링 합니다.</span><span class="sxs-lookup"><span data-stu-id="81c12-160">When you select an Office 365 group for supervised users, the policy monitors the content of the shared Office 365 mailbox and the Microsoft Teams channels associated with the group.</span></span> <span data-ttu-id="81c12-161">메일 그룹을 선택 하는 경우 정책은 개별 사용자 사서함을 모니터링 합니다.</span><span class="sxs-lookup"><span data-stu-id="81c12-161">When you select a distribution list, the policy monitors individual user mailboxes.</span></span>

<span data-ttu-id="81c12-162">그룹을 설정 하는 방법에 대 한 자세한 내용은 다음을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="81c12-162">For more information about setting up groups, see:</span></span>

- [<span data-ttu-id="81c12-163">메일 그룹 만들기 및 관리</span><span class="sxs-lookup"><span data-stu-id="81c12-163">Create and manage distribution groups</span></span>](https://docs.microsoft.com/Exchange/recipients-in-exchange-online/manage-distribution-groups/manage-distribution-groups)
- [<span data-ttu-id="81c12-164">메일 사용 가능 보안 그룹 관리</span><span class="sxs-lookup"><span data-stu-id="81c12-164">Manage mail-enabled security groups</span></span>](https://docs.microsoft.com/Exchange/recipients-in-exchange-online/manage-mail-enabled-security-groups)
- [<span data-ttu-id="81c12-165">Office 365 그룹 개요</span><span class="sxs-lookup"><span data-stu-id="81c12-165">Overview of Office 365 Groups</span></span>](https://docs.microsoft.com/office365/admin/create-groups/office-365-groups?view=o365-worldwide)

## <a name="step-4-required-create-a-communication-compliance-policy"></a><span data-ttu-id="81c12-166">4 단계 (필수 사항): 통신 준수 정책 만들기</span><span class="sxs-lookup"><span data-stu-id="81c12-166">Step 4 (required): Create a communication compliance policy</span></span>
  
1. <span data-ttu-id="81c12-167">Microsoft 365 [https://compliance.microsoft.com](https://compliance.microsoft.com) 조직의 관리자 계정에 대 한 자격 증명을 사용 하 여 로그인 합니다.</span><span class="sxs-lookup"><span data-stu-id="81c12-167">Sign into [https://compliance.microsoft.com](https://compliance.microsoft.com) using credentials for an admin account in your Microsoft 365 organization.</span></span>

2. <span data-ttu-id="81c12-168">Microsoft 365 준수 센터에서 **통신 준수**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="81c12-168">In the Microsoft 365 compliance center, select **Communication compliance**.</span></span>
  
3. <span data-ttu-id="81c12-169">**정책** 탭을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="81c12-169">Select the **Policies** tab.</span></span>

4. <span data-ttu-id="81c12-170">**정책 만들기** 를 선택 하 여 템플릿에서 새 정책을 만들고 구성 하거나 사용자 지정 정책을 만들고 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="81c12-170">Select **Create policy** to create and configure a new policy from a template or to create and configure a custom policy.</span></span>

    <span data-ttu-id="81c12-171">정책을 만들기 위해 정책 템플릿을 선택 하는 경우 다음을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="81c12-171">If you choose a policy template to create a policy, you will:</span></span>

    - <span data-ttu-id="81c12-172">정책 이름을 확인 하거나 업데이트 합니다.</span><span class="sxs-lookup"><span data-stu-id="81c12-172">Confirm or update the policy name.</span></span> <span data-ttu-id="81c12-173">정책을 만든 후에는 정책 이름을 변경할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="81c12-173">Policy names cannot be changed once the policy is created.</span></span>
    - <span data-ttu-id="81c12-174">제외할 사용자 또는 그룹 선택을 비롯 하 여 감독할 사용자 또는 그룹을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="81c12-174">Choose the users or groups to supervise, including choosing users or groups you'd like to exclude.</span></span>
    - <span data-ttu-id="81c12-175">정책에 대 한 검토자를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="81c12-175">Choose the reviewers for the policy.</span></span> <span data-ttu-id="81c12-176">검토자는 개별 사용자 또는 [메일 사용이 가능한 보안 그룹이](https://docs.microsoft.com/Exchange/recipients-in-exchange-online/manage-mail-enabled-security-groups#create-a-mail-enabled-security-group)될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="81c12-176">Reviewers can be individual users or [mail-enabled security groups](https://docs.microsoft.com/Exchange/recipients-in-exchange-online/manage-mail-enabled-security-groups#create-a-mail-enabled-security-group).</span></span> <span data-ttu-id="81c12-177">모든 검토자에 게 Exchange Online에서 호스트 되는 사서함이 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="81c12-177">All reviewers must have mailboxes hosted on Exchange Online.</span></span>
    - <span data-ttu-id="81c12-178">정책에 적용할 제한 된 조건 필드 (일반적으로 중요 한 정보 유형 또는 키워드 사전)를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="81c12-178">Choose a limited condition field, usually a sensitive info type or keyword dictionary to apply to the policy.</span></span>

    <span data-ttu-id="81c12-179">정책 마법사를 사용 하 여 사용자 지정 정책을 만드는 경우 다음을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="81c12-179">If you choose to use the policy wizard to create a custom policy, you will:</span></span>

    - <span data-ttu-id="81c12-180">정책에 이름과 설명을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="81c12-180">Give the policy a name and description.</span></span> <span data-ttu-id="81c12-181">정책을 만든 후에는 정책 이름을 변경할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="81c12-181">Policy names can't be changed once the policy is created.</span></span>
    - <span data-ttu-id="81c12-182">조직의 모든 사용자, 특정 사용자 및 그룹, 제외 하려는 기타 사용자 및 그룹을 비롯 하 여 감독할 사용자 또는 그룹을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="81c12-182">Choose the users or groups to supervise, including all users in your organization, specific users and groups, or other users and groups you'd like to exclude.</span></span> -
    - <span data-ttu-id="81c12-183">정책에 대 한 검토자를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="81c12-183">Choose the reviewers for the policy.</span></span> <span data-ttu-id="81c12-184">검토자는 개별 사용자 또는 [메일 사용이 가능한 보안 그룹이](https://docs.microsoft.com/Exchange/recipients-in-exchange-online/manage-mail-enabled-security-groups#create-a-mail-enabled-security-group)될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="81c12-184">Reviewers can be individual users or [mail-enabled security groups](https://docs.microsoft.com/Exchange/recipients-in-exchange-online/manage-mail-enabled-security-groups#create-a-mail-enabled-security-group).</span></span> <span data-ttu-id="81c12-185">모든 검토자에 게 Exchange Online에서 호스트 되는 사서함이 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="81c12-185">All reviewers must have mailboxes hosted on Exchange Online.</span></span>
    - <span data-ttu-id="81c12-186">Exchange, Microsoft 팀 또는 비즈니스용 Skype를 포함 하 여 검색할 통신 채널을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="81c12-186">Choose the communication channels to scan, including Exchange, Microsoft Teams, or Skype for Business.</span></span> <span data-ttu-id="81c12-187">또한 Microsoft 365에서 커넥터를 구성한 경우 타사 출처를 검색 하도록 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="81c12-187">You'll also choose to scan third-party sources if you've configured a connector in Microsoft 365.</span></span>
    - <span data-ttu-id="81c12-188">인바운드, 아웃 바운드 또는 내부 통신을 포함 하 여 모니터링할 통신 방향을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="81c12-188">Choose the communication direction to monitor, including inbound, outbound, or internal communications.</span></span>
    - <span data-ttu-id="81c12-189">통신 준수 정책 [조건을](communication-compliance-feature-reference.md#ConditionalSettings)정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="81c12-189">Define the communication compliance policy [conditions](communication-compliance-feature-reference.md#ConditionalSettings).</span></span> <span data-ttu-id="81c12-190">메시지 주소, 키워드, 파일 형식 및 크기 일치 조건에서 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="81c12-190">You can choose from message address, keyword, file types, and size match conditions.</span></span>
    - <span data-ttu-id="81c12-191">중요 한 정보 유형을 포함 하 고 싶은 경우 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="81c12-191">Choose if you'd like to include sensitive information types.</span></span> <span data-ttu-id="81c12-192">이 단계에서는 기본 및 사용자 지정 중요 한 정보 유형을 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="81c12-192">This step is where you can select default and custom sensitive info types.</span></span> <span data-ttu-id="81c12-193">통신 준수 정책 마법사의 기존 사용자 지정 중요 한 정보 유형 또는 사용자 지정 키워드 사전을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="81c12-193">Pick from existing custom sensitive information types or custom keyword dictionaries in the communication compliance policy wizard.</span></span> <span data-ttu-id="81c12-194">필요한 경우 마법사를 실행 하기 전에 이러한 항목을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="81c12-194">You can create these items before running the wizard if needed.</span></span> <span data-ttu-id="81c12-195">또한 통신 준수 정책 마법사 내에서 새 중요 한 정보 유형을 만들 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="81c12-195">You can also create new sensitive information types from within the communication compliance policy wizard.</span></span>
    - <span data-ttu-id="81c12-196">공격적인 언어 분류자를 사용 하도록 설정 하려면 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="81c12-196">Choose if you'd like to enable the offensive language classifier.</span></span> <span data-ttu-id="81c12-197">이 분류자는 전자 메일 메시지 본문에서 보내거나 받은 부적절 한 언어를 검색 합니다.</span><span class="sxs-lookup"><span data-stu-id="81c12-197">This  classifier detects inappropriate language sent or received in the body of email messages.</span></span>
    - <span data-ttu-id="81c12-198">검토할 통신의 비율을 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="81c12-198">Define the percentage of communications to review.</span></span>
    - <span data-ttu-id="81c12-199">정책 선택을 검토 하 고 정책을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="81c12-199">Review your policy selections and create the policy.</span></span>

5. <span data-ttu-id="81c12-200">서식 파일을 사용 하는 경우 **정책 만들기** 또는 사용자 지정 정책 마법사를 사용할 때 **제출을** 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="81c12-200">Select **Create policy** when using the templates or **Submit** when using the custom policy wizard.</span></span>

6. <span data-ttu-id="81c12-201">정책이 활성화 되는 시기와 캡처할 통신에 대 한 지침과 함께 **정책 만들기** 페이지가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="81c12-201">The **Your policy was created** page is displayed with guidelines on when policy will be activated and which communications will be captured.</span></span>

## <a name="step-5-optional-create-employee-notice-templates"></a><span data-ttu-id="81c12-202">5 단계 (선택 사항): 직원 공지 서식 파일 만들기</span><span class="sxs-lookup"><span data-stu-id="81c12-202">Step 5 (optional): Create employee notice templates</span></span>

<span data-ttu-id="81c12-203">관련 직원에 게 미리 알림 메시지를 보내 정책 경고에 응답 하는 옵션을 설정 하려면 조직에 공지 서식 파일을 하나 이상 만들어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="81c12-203">If you want to have the option of responding to a policy alert by sending a reminder notice to the associated employee, you'll need to create at least one notice template in your organization.</span></span> <span data-ttu-id="81c12-204">알림 서식 파일 필드는 경고 업데이트 관리 프로세스의 일부로 전송 되기 전에 편집 가능 하 게 되며 각 통신 준수 정책에 대해 사용자 지정 된 공지 서식 파일을 만드는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="81c12-204">The notice template fields are editable before they're sent as part of the alert remediation process, and creating a customized notice template for each communication compliance policy is recommended.</span></span>

1. <span data-ttu-id="81c12-205">Microsoft 365 [https://compliance.microsoft.com](https://compliance.microsoft.com) 조직의 관리자 계정에 대 한 자격 증명을 사용 하 여 로그인 합니다.</span><span class="sxs-lookup"><span data-stu-id="81c12-205">Sign into [https://compliance.microsoft.com](https://compliance.microsoft.com) using credentials for an admin account in your Microsoft 365 organization.</span></span>

2. <span data-ttu-id="81c12-206">Microsoft 365 준수 센터에서 **통신 준수**로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="81c12-206">In the Microsoft 365 compliance center, go to **Communication compliance**.</span></span>

3. <span data-ttu-id="81c12-207">**공지 템플릿** 탭을 선택한 다음 **공지 템플릿 만들기**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="81c12-207">Select the **Notice templates** tab and then select **Create notice template**.</span></span>

4. <span data-ttu-id="81c12-208">**공지 서식 파일 수정** 페이지에서 다음 필드를 작성 합니다.</span><span class="sxs-lookup"><span data-stu-id="81c12-208">On the **Modify a notice template** page, complete the following fields:</span></span>

    - <span data-ttu-id="81c12-209">주의 서식 파일 이름 (필수)</span><span class="sxs-lookup"><span data-stu-id="81c12-209">Notice template name (required)</span></span>
    - <span data-ttu-id="81c12-210">보내기 (필수)</span><span class="sxs-lookup"><span data-stu-id="81c12-210">Send from (required)</span></span>
    - <span data-ttu-id="81c12-211">참조 및 숨은 참조 (선택 사항)</span><span class="sxs-lookup"><span data-stu-id="81c12-211">Cc and Bcc (optional)</span></span>
    - <span data-ttu-id="81c12-212">제목 (필수)</span><span class="sxs-lookup"><span data-stu-id="81c12-212">Subject (required)</span></span>
    - <span data-ttu-id="81c12-213">메시지 본문 (필수)</span><span class="sxs-lookup"><span data-stu-id="81c12-213">Message body (required)</span></span>

5. <span data-ttu-id="81c12-214">**저장** 을 선택 하 여 알림 서식 파일을 만들고 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="81c12-214">Select **Save** to create and save the notice template.</span></span>

## <a name="step-6-optional-test-your-communication-compliance-policy"></a><span data-ttu-id="81c12-215">6 단계 (선택 사항): 통신 준수 정책 테스트</span><span class="sxs-lookup"><span data-stu-id="81c12-215">Step 6 (optional): Test your communication compliance policy</span></span>

<span data-ttu-id="81c12-216">통신 준수 정책을 만든 후에는 테스트를 통해 정의한 조건이 정책에 의해 적절 하 게 적용 되는지 확인 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="81c12-216">After you create a communication compliance policy, it's a good idea to test it to make sure that the conditions you defined are being properly enforced by the policy.</span></span> <span data-ttu-id="81c12-217">또한 통신 준수 정책에 중요 한 정보 유형이 포함 되어 있는 경우 [DLP (데이터 손실 방지) 정책을 테스트할](create-test-tune-dlp-policy.md) 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="81c12-217">You may also want to [test your data loss prevention (DLP) policies](create-test-tune-dlp-policy.md) if your communication compliance policies include sensitive information types.</span></span> <span data-ttu-id="81c12-218">테스트할 통신을 캡처할 수 있도록 정책에 대 한 정품 인증을 제공 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="81c12-218">Make sure you give your policies time to activate so that the communications you want to test are captured.</span></span>

<span data-ttu-id="81c12-219">다음 단계에 따라 통신 준수 정책을 테스트 합니다.</span><span class="sxs-lookup"><span data-stu-id="81c12-219">Follow these steps to test your communication compliance policy:</span></span>

1. <span data-ttu-id="81c12-220">테스트할 정책에 정의 된 감독 된 사용자로 로그인 한 상태에서 전자 메일 클라이언트 또는 Microsoft 팀을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="81c12-220">Open an email client or Microsoft Teams while signed in as a supervised user defined in the policy you want to test.</span></span>
2. <span data-ttu-id="81c12-221">통신 준수 정책에 정의한 기준을 충족 하는 전자 메일 또는 Microsoft 팀 채팅을 보냅니다.</span><span class="sxs-lookup"><span data-stu-id="81c12-221">Send an email or Microsoft Teams chat that meets the criteria you've defined in the communication compliance policy.</span></span> <span data-ttu-id="81c12-222">이 테스트는 키워드, 첨부 파일 크기, 도메인 등이 될 수 있습니다. 정책에서 구성 된 조건부 설정이 너무 제한적일 또는 너무 lenient 인지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="81c12-222">This test can be a keyword, attachment size, domain, etc. Make sure you determine if your configured conditional settings in the policy are too restrictive or too lenient.</span></span>

    > [!NOTE]
    > <span data-ttu-id="81c12-223">모든 원본 채널의 통신은 정책에서 완전히 처리 되는 데 최대 24 시간이 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="81c12-223">Communications in all source channels can take up to 24 hours to fully process in a policy.</span></span>

3. <span data-ttu-id="81c12-224">통신 준수 정책에 지정 된 검토자로 Microsoft 365에 로그인 합니다.</span><span class="sxs-lookup"><span data-stu-id="81c12-224">Sign in to Microsoft 365 as a reviewer designated in the communication compliance policy.</span></span> <span data-ttu-id="81c12-225">정책에 대 한 경고를 보려면 **통신 준수** > **알림과** 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="81c12-225">Navigate to **Communication compliance** > **Alerts** to view the alerts for your policies.</span></span>

4. <span data-ttu-id="81c12-226">업데이트 관리 컨트롤을 사용 하 여 경고를 수정 하 고 경고가 제대로 확인 되는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="81c12-226">Remediate the alert using the remediation controls and verify that the alert is properly resolved.</span></span>
