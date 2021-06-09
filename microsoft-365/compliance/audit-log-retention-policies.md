---
title: 로그 보존 정책 감사 관리
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- M365-security-compliance
- SPO_Content
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: 감사 로그 보존 정책은 Microsoft 365의 새로운 고급 감사 기능의 일부입니다. 감사 로그 보존 정책을 사용하여 조직에서 감사 로그를 보존할 기간을 지정할 수 있습니다.
ms.openlocfilehash: b3534f5d0572b2656711850b483651270b9e3315
ms.sourcegitcommit: 50908a93554290ff1157b58d0a868a33e012513c
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/08/2021
ms.locfileid: "52822144"
---
# <a name="manage-audit-log-retention-policies"></a><span data-ttu-id="568b3-104">로그 보존 정책 감사 관리</span><span class="sxs-lookup"><span data-stu-id="568b3-104">Manage audit log retention policies</span></span>

<span data-ttu-id="568b3-105">보안 및 준수 센터에서 감사 로그 보존 정책을 작성하고 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="568b3-105">You can create and manage audit log retention policies in the Security & Compliance Center.</span></span> <span data-ttu-id="568b3-106">감사 로그 보존 정책은 Microsoft 365의 새로운 고급 감사 기능의 일부입니다.</span><span class="sxs-lookup"><span data-stu-id="568b3-106">Audit log retention policies are part of the new Advanced Audit capabilities in Microsoft 365.</span></span> <span data-ttu-id="568b3-107">감사 로그 보존 정책을 사용하여 조직에서 감사 로그를 보존할 기간을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="568b3-107">An audit log retention policy lets you specify how long to retain audit logs in your organization.</span></span> <span data-ttu-id="568b3-108">감사 로그를 최대 10년 동안 보존할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="568b3-108">You can retain audit logs for up to 10 years.</span></span> <span data-ttu-id="568b3-109">다음 조건을 기준으로 정책을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="568b3-109">You can create policies based on the following criteria:</span></span>

- <span data-ttu-id="568b3-110">하나 이상의 Microsoft 365 서비스에서의 모든 활동</span><span class="sxs-lookup"><span data-stu-id="568b3-110">All activities in one or more Microsoft 365 services</span></span>

- <span data-ttu-id="568b3-111">모든 사용자 또는 특정 사용자가 수행하는 (Microsoft 365 서비스에서의) 특정 활동</span><span class="sxs-lookup"><span data-stu-id="568b3-111">Specific activities (in a Microsoft 365 service) performed by all users or by specific users</span></span>

- <span data-ttu-id="568b3-112">조직에 여러 정책이 있을 때 더 중시하는 정책을 지정하는 우선 순위</span><span class="sxs-lookup"><span data-stu-id="568b3-112">A priority level that specifies which policy takes precedence in you have multiple policies in your organization</span></span>

## <a name="default-audit-log-retention-policy"></a><span data-ttu-id="568b3-113">기본 로그 보존 정책 감사</span><span class="sxs-lookup"><span data-stu-id="568b3-113">Default audit log retention policy</span></span>

<span data-ttu-id="568b3-114">Microsoft 365의 고급 감사는 모든 조직에 기본 감사 로그 보존 정책을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="568b3-114">Advanced Audit in Microsoft 365 provides a default audit log retention policy for all organizations.</span></span> <span data-ttu-id="568b3-115">이 정책은 모든 Exchange Online, SharePoint Online, 비즈니스용 OneDrive 및 Azure Active Directory 감사 레코드를 1년 동안 보존합니다.</span><span class="sxs-lookup"><span data-stu-id="568b3-115">This policy retains all Exchange Online, SharePoint Online, OneDrive for Business, and Azure Active Directory audit records for one year.</span></span> <span data-ttu-id="568b3-116">이 기본 정책은 **Exchange**, **SharePoint**, **OneDrive**, **워크로드** 속성에 대한 **AzureActiveDirectory**(활동이 발생한 서비스)의 값을 포함하는 감사 레코드를 보존합니다.</span><span class="sxs-lookup"><span data-stu-id="568b3-116">This default policy retains audit records that contain the value of **Exchange**, **SharePoint**, **OneDrive**, **AzureActiveDirectory** for the **Workload** property (which is the service in which the activity occurred).</span></span> <span data-ttu-id="568b3-117">기본 정책은 수정할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="568b3-117">The default policy can't be modified.</span></span> <span data-ttu-id="568b3-118">기본 정책에 포함된 각 워크로드의 레코드 유형 목록은 이 문서의 [추가 정보](#more-information) 섹션을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="568b3-118">See the [More information](#more-information) section in this article for a list of record types for each workload that are included in the default policy.</span></span>

> [!NOTE]
> <span data-ttu-id="568b3-119">기본 감사 로그 보존 정책은 Office 365 또는 Microsoft 365 E5 라이선스가 할당되었거나 Microsoft 365 E5 준수 또는 E5 eDiscovery 및 감사 애드온 라이선스가 있는 사용자가 수행한 활동에 대한 감사 레코드에만 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="568b3-119">The default audit log retention policy only applies to audit records for activity performed by users who are assigned an Office 365 or Microsoft 365 E5 license or have a Microsoft 365 E5 Compliance or E5 eDiscovery and Audit add-on license.</span></span> <span data-ttu-id="568b3-120">조직에 E5 이외의 사용자 또는 게스트 사용자가 있는 경우 해당 감사 레코드는 90일 동안 유지됩니다.</span><span class="sxs-lookup"><span data-stu-id="568b3-120">If you have non-E5 users or guest users in your organization, their corresponding audit records are retained for 90 days.</span></span>

## <a name="before-you-create-an-audit-log-retention-policy"></a><span data-ttu-id="568b3-121">감사 로그 보존 정책을 생성하기 전에 다음을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="568b3-121">Before you create an audit log retention policy</span></span>

- <span data-ttu-id="568b3-122">사용자는 감사 보존 정책을 만들거나 수정하기 위해 보안 및 준수 센터에서 조직 구성 역할을 할당 받아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="568b3-122">You have to be assigned the Organization Configuration role in the Security & Compliance Center to create or modify an audit retention policy.</span></span>

- <span data-ttu-id="568b3-123">조직에서 최대 50개의 감사 로그 보존 정책을 가질 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="568b3-123">You can have a maximum of 50 audit log retention policies in your organization.</span></span>

- <span data-ttu-id="568b3-124">감사 로그를 90일(최대 1년) 이상 유지하려면 감사 로(감사된 황동을 실행하여)그를 생성한 사용자에게 Office 365 E5 또는 Microsoft 365 E5 라이선스가 할당되거나 Microsoft 365 E5 규정 준수 또는 E5 eDiscovery 및 감사 추가 기능 라이선스가 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="568b3-124">To retain an audit log for longer than 90 days (and up to 1 year), the user who generates the audit log (by performing an audited activity) must be assigned an Office 365 E5 or Microsoft 365 E5 license or have a Microsoft 365 E5 Compliance or E5 eDiscovery and Audit add-on license.</span></span> <span data-ttu-id="568b3-125">감사 로그를 10년 동안 보존하려면 감사 로그를 생성하는 사용자에게 E5 라이선스 외에 10년 감사 로그 보존 추가 기능 라이선스도 할당되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="568b3-125">To retain audit logs for 10 years, the user who generates the audit log must also be assigned a 10-year audit log retention add-on license in addition to an E5 license.</span></span>

- <span data-ttu-id="568b3-p106">모든 사용자 지정 감사 로그 보존 정책(조직에서 만든)은 기본 보존 정책보다 우선 순위가 적용됩니다. 예를 들어 1년보다 짧은 보존 기간이 있는 Exchange 사서함 활동에 대한 감사 로그 보존 정책을 만드는 경우 사용자 지정 정책에서 지정한 기간이 단축되는 동안 Exchange 사서함 활동에 대한 감사 레코드가 보존됩니다.</span><span class="sxs-lookup"><span data-stu-id="568b3-p106">All custom audit log retention policies (created by your organization) take priority over the default retention policy. For example, if you create an audit log retention policy for Exchange mailbox activity that has a retention period that's shorter than one year, audit records for Exchange mailbox activities will be retained for the shorter duration specified by the custom policy.</span></span>

## <a name="create-an-audit-log-retention-policy"></a><span data-ttu-id="568b3-128">감사 로그 보존 정책 생성</span><span class="sxs-lookup"><span data-stu-id="568b3-128">Create an audit log retention policy</span></span>

1. <span data-ttu-id="568b3-129">[https://compliance.microsoft.com](https://compliance.microsoft.com)으로 이동하여 보안 및 규정 준수 센터의 권한 페이지에서 조직 구성 역할이 할당된 사용자 계정으로 로그인합니다.</span><span class="sxs-lookup"><span data-stu-id="568b3-129">Go to [https://compliance.microsoft.com](https://compliance.microsoft.com) and sign in with a user account that's assigned the Organization Configuration role on the Permissions page in the Security & Compliance Center.</span></span>

2. <span data-ttu-id="568b3-130">Microsoft 365 준수 센터의 왼쪽 창에서 **모두 보기** 를 클릭한 다음 **감사** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="568b3-130">In the left pane of the Microsoft 365 compliance center, click **Show all**, and then click **Audit**.</span></span>

3. <span data-ttu-id="568b3-131">**감사 보존 정책** 탭을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="568b3-131">Click the **Audit retention policies** tab.</span></span>

4. <span data-ttu-id="568b3-132">**감사 보존 정책 만들기** 를 클릭한 다음 플라이아웃 페이지에서 다음 필드를 완료하십시오.</span><span class="sxs-lookup"><span data-stu-id="568b3-132">Click **Create audit retention policy**, and then complete the following fields on the flyout page:</span></span>

    ![새 감사 보존 정책 플라이아웃 페이지](../media/CreateAuditLogRetentionPolicy.png)

   1. <span data-ttu-id="568b3-134">**정책 이름:** 감사 로그 보존 정책의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="568b3-134">**Policy name:** The name of the audit log retention policy.</span></span> <span data-ttu-id="568b3-135">이 이름은 조직에서 고유해야 하며 정책을 만든 후 변경할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="568b3-135">This name must be unique in your organization, and it can't be change after the policy is created.</span></span>

   2. <span data-ttu-id="568b3-136">**설명:** 선택 사항이지만 레코드 유형 또는 워크로드, 정책에 지정된 사용자 및 기간과 같은 정책에 대한 정보를 제공하는 데 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="568b3-136">**Description:** Optional, but helpful to provide information about the policy, such as the record type or workload, users specified in the policy, and the duration.</span></span>

   3. <span data-ttu-id="568b3-137">**사용자:** 정책을 적용할 하나 이상의 사용자를 선택하십시오.</span><span class="sxs-lookup"><span data-stu-id="568b3-137">**Users:** Select one or more users to apply the policy to.</span></span> <span data-ttu-id="568b3-138">이 상자를 비워 두면 정책이 모든 사용자에 게 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="568b3-138">If you leave this box blank, then the policy will apply to all users.</span></span> <span data-ttu-id="568b3-139">**레코드 유형** 을 비워둔 경우 반드시 사용자를 선택해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="568b3-139">If you leave the **Record type** blank, then you must select a user.</span></span>

   4. <span data-ttu-id="568b3-140">**레코드 유형:** 정책이 적용되는 감사 레코드 유형입니다.</span><span class="sxs-lookup"><span data-stu-id="568b3-140">**Record type:** The audit record type the policy applies to.</span></span> <span data-ttu-id="568b3-141">또한 해당 속성을 비워둔 경우 **사용자** 상자에서 사용자를 선택해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="568b3-141">If you leave this property blank, you must select a user in the **Users** box.</span></span> <span data-ttu-id="568b3-142">단일 레코드 유형 또는 다중 레코드 유형을 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="568b3-142">You can select a single record type or multiple record types:</span></span>

   - <span data-ttu-id="568b3-143">단일 레코드 유형을 선택하면 **활동** 필드가 동적으로 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="568b3-143">If you select a single record type, the **Activities** field is dynamically displayed.</span></span> <span data-ttu-id="568b3-144">드롭다운 목록을 사용하여 선택한 레코드 유형에서 활동을 선택하고 정책을 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="568b3-144">You can use the drop-down list to select activities from the selected record type to apply the policy to.</span></span> <span data-ttu-id="568b3-145">특정 활동을 선택하지 않으면 선택한 레코드 유형의 모든 활동에 정책이 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="568b3-145">If you don't choose specific activities, the policy will apply to all activities of the selected record type.</span></span>

   - <span data-ttu-id="568b3-146">다중 레코드 유형을 선택한 경우에는 활동을 선택할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="568b3-146">If you select multiple record types, you don't have the ability to select activities.</span></span> <span data-ttu-id="568b3-147">선택한 레코드 유형의 모든 활동에 해당 정책이 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="568b3-147">The policy will apply to all activities of the selected record types.</span></span>

   5. <span data-ttu-id="568b3-148">**기간:** 정책 기준을 충족하는 감사 로그를 보유하는 기간입니다.</span><span class="sxs-lookup"><span data-stu-id="568b3-148">**Duration:** The amount of time to retain the audit logs that meet the criteria of the policy.</span></span>

   6. <span data-ttu-id="568b3-149">**우선 순위:** 이 값은 조직의 감사 로그 보존 정책이 처리되는 순서를 결정합니다.</span><span class="sxs-lookup"><span data-stu-id="568b3-149">**Priority:** This value determines the order in which audit log retention policies in your organization are processed.</span></span> <span data-ttu-id="568b3-150">값이 작을수록 우선 순위가 높습니다.</span><span class="sxs-lookup"><span data-stu-id="568b3-150">A lower value indicates a higher priority.</span></span> <span data-ttu-id="568b3-151">유효한 우선 순위의 숫자 값은 **1**~**10000** 사이입니다.</span><span class="sxs-lookup"><span data-stu-id="568b3-151">Valid priorities are numerical values between **1** and **10000**.</span></span> <span data-ttu-id="568b3-152">**1** 이 가장 높은 우선 순위 값이며, **10000** 이 가장 낮은 우선 순위 값입니다.</span><span class="sxs-lookup"><span data-stu-id="568b3-152">A value of **1** is the highest priority, and a value of **10000** is the lowest priority.</span></span> <span data-ttu-id="568b3-153">예를 들어 값이 **5** 인 정책이 값이 **10** 인 정책보다 우선합니다.</span><span class="sxs-lookup"><span data-stu-id="568b3-153">For example, a policy with a value of **5** takes priority over a policy with a value of **10**.</span></span> <span data-ttu-id="568b3-154">앞에서 설명한 것처럼 사용자 지정 감사 로그 보존 정책은 조직의 기본 정책보다 우선합니다.</span><span class="sxs-lookup"><span data-stu-id="568b3-154">As previously explained, any custom audit log retention policy takes priority over the default policy for your organization.</span></span>

5. <span data-ttu-id="568b3-155">**저장** 을 클릭하여 새 감사 로그 보존 정책을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="568b3-155">Click **Save** to create the new audit log retention policy.</span></span>

   <span data-ttu-id="568b3-156">새 정책은 **감사 보존 정책** 탭의 목록에 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="568b3-156">The new policy is displayed in the list on the **Audit retention policies** tab.</span></span>

## <a name="manage-audit-log-retention-policies"></a><span data-ttu-id="568b3-157">감사 로그 보존 정책 관리</span><span class="sxs-lookup"><span data-stu-id="568b3-157">Manage audit log retention policies</span></span>

<span data-ttu-id="568b3-158">감사 로그 보존 정책은 **감사 보존 정책** 탭(*대시보드* 라고도 함)에 나열됩니다.</span><span class="sxs-lookup"><span data-stu-id="568b3-158">Audit log retention policies are listed on the **Audit retention policies** tab (also called the *dashboard*).</span></span> <span data-ttu-id="568b3-159">대시보드를 사용하여 감사 보존 정책을 보고, 편집하고, 삭제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="568b3-159">You can use the dashboard to view, edit, and delete audit retention policies.</span></span>

### <a name="view-policies-in-the-dashboard"></a><span data-ttu-id="568b3-160">대시보드에서 정책 보기</span><span class="sxs-lookup"><span data-stu-id="568b3-160">View policies in the dashboard</span></span>

<span data-ttu-id="568b3-161">감사 로그 보존 정책은 대시보드에 나열되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="568b3-161">Audit log retention policies are listed in the dashboard.</span></span> <span data-ttu-id="568b3-162">대시보드에서 정책을 볼 때의 이점 중 하나는 **우선 순위** 열을 클릭하여 적용되는 우선 순위로 정책을 나열할 수 있다는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="568b3-162">One advantage of viewing policies in the dashboard is that you can click the **Priority** column to list the policies in the priority in which they are applied.</span></span> <span data-ttu-id="568b3-163">이전에 설명한 대로 값이 높을수록 우선 순위가 더 높음을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="568b3-163">As previously explained, a higher value indicates a higher priority.</span></span>

![감사 보존 정책 대시보드의 우선 순위 열](../media/AuditLogRetentionDashboardPriority.png)

<span data-ttu-id="568b3-165">플라이아웃 페이지에 설정을 표시하는 정책을 선택할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="568b3-165">You can also select a policy to display its settings on the flyout page.</span></span>

> [!NOTE]
> <span data-ttu-id="568b3-166">조직의 기본 감사 로그 보존 정책은 대시보드에 표시되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="568b3-166">The default audit log retention policy for your organization isn't displayed in the dashboard.</span></span>

### <a name="edit-policies-in-the-dashboard"></a><span data-ttu-id="568b3-167">대시보드에서 정책 편집</span><span class="sxs-lookup"><span data-stu-id="568b3-167">Edit policies in the dashboard</span></span>

<span data-ttu-id="568b3-168">정책을 편집하려면 정책을 선택하여 플라이아웃 페이지를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="568b3-168">To edit a policy, select it to display the flyout page.</span></span> <span data-ttu-id="568b3-169">하나 이상의 설정을 수정한 다음 변경 내용을 저장할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="568b3-169">You can modify one or more setting and then save your changes.</span></span>


> [!IMPORTANT]
> <span data-ttu-id="568b3-170">**New-UnifiedAuditLogRetentionPolicy** cmdlet을 사용하는 경우, 대시보드의 **감사 보존 정책 만들기** 도구에서 사용할 수 없는 레코드 종류나 활동에 대한 감사 로그 보존 정책을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="568b3-170">If you use the **New-UnifiedAuditLogRetentionPolicy** cmdlet, it's possible to create an audit log retention policy for record types or activities that aren't available in the **Create audit retention policy** tool in the dashboard.</span></span> <span data-ttu-id="568b3-171">이 경우, **감사 보존 정책** 대시보드에서 정책(예: 보존 기간 변경 또는 활동 추가 및 제거)을 편집할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="568b3-171">In this case, you won't be able to edit the policy (for example, change the retention duration or add and remove activities) from the **Audit retention policies** dashboard.</span></span> <span data-ttu-id="568b3-172">규정 준수 센터에서만 정책을 보고 삭제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="568b3-172">You'll only be able to view and delete the policy in the compliance center.</span></span> <span data-ttu-id="568b3-173">정책을 편집하려면 보안 및 준수 센터 PowerShell에서 [Set-UnifiedAuditLogRetentionPolicy](/powershell/module/exchange/set-unifiedauditlogretentionpolicy) cmdlet을 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="568b3-173">To edit the policy, you'll have to use the [Set-UnifiedAuditLogRetentionPolicy](/powershell/module/exchange/set-unifiedauditlogretentionpolicy) cmdlet in Security & Compliance Center PowerShell.</span></span><br/><br/><span data-ttu-id="568b3-174">**팁:** PowerShell을 사용하여 편집해야 하는 정책에 대한 메시지가 플라이아웃 페이지의 맨 위에 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="568b3-174">**Tip:** A message is displayed at the top of the flyout page for policies that have to be edited using PowerShell.</span></span>

### <a name="delete-policies-in-the-dashboard"></a><span data-ttu-id="568b3-175">대시보드에서 정책 삭제</span><span class="sxs-lookup"><span data-stu-id="568b3-175">Delete policies in the dashboard</span></span>

<span data-ttu-id="568b3-176">정책을 삭제하려면 **삭제** ![삭제 아이콘](../media/92a9f8e0-d469-48da-addb-69365e7ffb6f.jpg) 아이콘을 클릭한 후에 정책의 삭제를 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="568b3-176">To delete a policy, click the **Delete** ![Delete icon](../media/92a9f8e0-d469-48da-addb-69365e7ffb6f.jpg) icon and then confirm that you want to delete the policy.</span></span> <span data-ttu-id="568b3-177">정책이 대시보드에서 제거되지만 조직에서 정책이 제거되는 데 최대 30분이 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="568b3-177">The policy is removed from the dashboard, but it might take up to 30 minutes for the policy to be removed from your organization.</span></span>

## <a name="create-and-manage-audit-log-retention-policies-in-powershell"></a><span data-ttu-id="568b3-178">PowerShell에서 감사 로그 보존 정책 만들기 및 관리</span><span class="sxs-lookup"><span data-stu-id="568b3-178">Create and manage audit log retention policies in PowerShell</span></span>

<span data-ttu-id="568b3-179">보안 및 준수 센터 PowerShell을 사용하여 감사 로그 보존 정책을 만들고 관리할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="568b3-179">You can also use Security & Compliance Center PowerShell to create and manage audit log retention policies.</span></span> <span data-ttu-id="568b3-180">PowerShell을 사용하는 한 가지 이유는 UI에서 사용할 수 없는 레코드 형식 또는 활동에 대한 정책을 만들기 위한 것입니다.</span><span class="sxs-lookup"><span data-stu-id="568b3-180">One reason to use PowerShell is to create a policy for a record type or activity that isn't available in the UI.</span></span>

### <a name="create-an-audit-log-retention-policy-in-powershell"></a><span data-ttu-id="568b3-181">PowerShell에서 감사 로그 보존 정책 만들기</span><span class="sxs-lookup"><span data-stu-id="568b3-181">Create an audit log retention policy in PowerShell</span></span>

<span data-ttu-id="568b3-182">다음 단계에 따라 PowerShell에서 감사 로그 보존 정책을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="568b3-182">Follow these steps to create an audit log retention policy in PowerShell:</span></span>

1. <span data-ttu-id="568b3-183">[보안 및 준수 센터 PowerShell에 연결하기](/powershell/exchange/connect-to-scc-powershell)</span><span class="sxs-lookup"><span data-stu-id="568b3-183">[Connect to Security & Compliance Center PowerShell](/powershell/exchange/connect-to-scc-powershell).</span></span>

2. <span data-ttu-id="568b3-184">다음 명령을 실행하여 감사 로그 보존 정책을 생성하십시오.</span><span class="sxs-lookup"><span data-stu-id="568b3-184">Run the following command to create an audit log retention policy.</span></span>

   ```powershell
   New-UnifiedAuditLogRetentionPolicy -Name "Microsoft Teams Audit Policy" -Description "One year retention policy for all Microsoft Teams activities" -RecordTypes MicrosoftTeams -RetentionDuration TenYears -Priority 100
   ```

    <span data-ttu-id="568b3-185">이 예에서는 다음 설정으로 "Microsoft Teams Audit Policy"라는 감사 로그 보존 정책을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="568b3-185">This example creates an audit log retention policy named "Microsoft Teams Audit Policy" with these settings:</span></span>

   - <span data-ttu-id="568b3-186">정책에 대한 설명입니다.</span><span class="sxs-lookup"><span data-stu-id="568b3-186">A description of the policy.</span></span>

   - <span data-ttu-id="568b3-187">모든 Microsoft Teams 활동을 유지합니다(*RecordType* 매개 변수로 정의된 대로).</span><span class="sxs-lookup"><span data-stu-id="568b3-187">Retains all Microsoft Teams activities (as defined by the *RecordType* parameter).</span></span>

   - <span data-ttu-id="568b3-188">Microsoft Teams 감사 로그를 10년 동안 보존합니다.</span><span class="sxs-lookup"><span data-stu-id="568b3-188">Retains Microsoft Teams audit logs for 10 years.</span></span>

   - <span data-ttu-id="568b3-189">우선 순위 100위</span><span class="sxs-lookup"><span data-stu-id="568b3-189">A priority of 100.</span></span>

<span data-ttu-id="568b3-190">다음은 감사 로그 보존 정책을 만드는 또 다른 예시입니다.</span><span class="sxs-lookup"><span data-stu-id="568b3-190">Here's another example of creating an audit log retention policy.</span></span> <span data-ttu-id="568b3-191">이 정책은 사용자 admin@contoso.onmicrosoft.com에 대해 6 개월 동안 "사용자 로그인" 활동에 대한 감사 로그를 유지합니다.</span><span class="sxs-lookup"><span data-stu-id="568b3-191">This policy retains audit logs for the "User logged in" activity for six months for the user admin@contoso.onmicrosoft.com.</span></span>

```powershell
New-UnifiedAuditLogRetentionPolicy -Name "SixMonth retention for admin logons" -RecordTypes AzureActiveDirectoryStsLogon -Operations UserLoggedIn -UserIds admin@contoso.onmicrosoft.com -RetentionDuration SixMonths -Priority 25
```

<span data-ttu-id="568b3-192">자세한 정보는 [New-UnifiedAuditLogRetentionPolicy](/powershell/module/exchange/new-unifiedauditlogretentionpolicy)를 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="568b3-192">For more information, see [New-UnifiedAuditLogRetentionPolicy](/powershell/module/exchange/new-unifiedauditlogretentionpolicy).</span></span>

### <a name="view-policies-in-powershell"></a><span data-ttu-id="568b3-193">PowerShell에서 정책 보기</span><span class="sxs-lookup"><span data-stu-id="568b3-193">View policies in PowerShell</span></span>

<span data-ttu-id="568b3-194">보안 및 준수 센터 PowerShell에서 [Get-UnifiedAuditLogRetentionPolicy](/powershell/module/exchange/get-unifiedauditlogretentionpolicy) cmdlet을 사용하여 감사 로그 보존 정책을 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="568b3-194">Use the [Get-UnifiedAuditLogRetentionPolicy](/powershell/module/exchange/get-unifiedauditlogretentionpolicy) cmdlet in Security & Compliance Center PowerShell to view audit log retention policies.</span></span>

<span data-ttu-id="568b3-195">다음은 조직의 감사 로그 보존 정책에 대한 설정을 표시하는 샘플 명령입니다.</span><span class="sxs-lookup"><span data-stu-id="568b3-195">Here's a sample command to display the settings for all audit log retention policies in your organization.</span></span> <span data-ttu-id="568b3-196">이 명령은 정책을 가장 높은 우선 순위에서 가장 낮은 우선 순위로 정렬합니다.</span><span class="sxs-lookup"><span data-stu-id="568b3-196">This command sorts the policies from the highest to lowest priority.</span></span>

```powershell
Get-UnifiedAuditLogRetentionPolicy | Sort-Object -Property Priority -Descending | FL Priority,Name,Description,RecordTypes,Operations,UserIds,RetentionDuration
```

> [!NOTE]
> <span data-ttu-id="568b3-197">**Get-UnifiedAuditLogRetentionPolicy** cmdlet은 조직의 기본 감사 로그 보존 정책을 반환하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="568b3-197">The **Get-UnifiedAuditLogRetentionPolicy** cmdlet doesn't return the default audit log retention policy for your organization.</span></span>

### <a name="edit-policies-in-powershell"></a><span data-ttu-id="568b3-198">PowerShell에서 정책 편집</span><span class="sxs-lookup"><span data-stu-id="568b3-198">Edit policies in PowerShell</span></span>

<span data-ttu-id="568b3-199">보안 및 규정 센터 PowerShell에서 [Set-UnifiedAuditLogRetentionPolicy](/powershell/module/exchange/set-unifiedauditlogretentionpolicy) cmdlet을 사용하여 기존 감사 로그 보존 정책을 편집할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="568b3-199">Use the [Set-UnifiedAuditLogRetentionPolicy](/powershell/module/exchange/set-unifiedauditlogretentionpolicy) cmdlet in Security & Compliance Center PowerShell to edit an existing audit log retention policy.</span></span>

### <a name="delete-policies-in-powershell"></a><span data-ttu-id="568b3-200">PowerShell에서 정책 삭제</span><span class="sxs-lookup"><span data-stu-id="568b3-200">Delete policies in PowerShell</span></span>

<span data-ttu-id="568b3-201">보안 및 준수 센터 PowerShell에서 [Remove-UnifiedAuditLogRetentionPolicy](/powershell/module/exchange/remove-unifiedauditlogretentionpolicy) cmdlet을 사용하여 감사 로그 보존 정책을 삭제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="568b3-201">Use the [Remove-UnifiedAuditLogRetentionPolicy](/powershell/module/exchange/remove-unifiedauditlogretentionpolicy) cmdlet in Security & Compliance Center PowerShell to delete an audit log retention policy.</span></span> <span data-ttu-id="568b3-202">조직에서 정책이 제거되는 데 최대 30분이 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="568b3-202">It might take up to 30 minutes for the policy to be removed from your organization.</span></span>

## <a name="more-information"></a><span data-ttu-id="568b3-203">추가 정보</span><span class="sxs-lookup"><span data-stu-id="568b3-203">More information</span></span>

<span data-ttu-id="568b3-204">앞서 설명한 것처럼 Azure Active Directory, Exchange Online, SharePoint Online 및 비즈니스용 OneDrive의 작업에 대한 감사 레코드는 기본적으로 1년 동안 보존됩니다.</span><span class="sxs-lookup"><span data-stu-id="568b3-204">As previously stated, audit records for operations in Azure Active Directory, Exchange Online, SharePoint Online, and OneDrive for Business, are retained for one year by default.</span></span> <span data-ttu-id="568b3-205">다음 표에는 기본 감사 로그 보존 정책에 포함된 모든 레코드 유형(이러한 각 서비스에 대한)이 나열되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="568b3-205">The following table lists all the record types (for each of these services) included in the default audit log retention policy.</span></span> <span data-ttu-id="568b3-206">이는 특정 레코드 유형, 작업 또는 사용자에 대해 사용자 지정 감사 로그 보존 정책이 우선하지 않는 한 이 레코드 유형의 작업에 대한 감사 로그가 1년 동안 보존됨을 의미합니다.</span><span class="sxs-lookup"><span data-stu-id="568b3-206">This means that audit logs for any operation with this record type are retained for one year unless a custom audit log retention policy takes precedence for a specific record type, operation, or user.</span></span> <span data-ttu-id="568b3-207">각 레코드 유형에 대한 Enum 값(감사 레코드의 RecordType 속성 값으로 표시됨)이 괄호 안에 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="568b3-207">The Enum value (which is displayed as the value for the RecordType property in an audit record) for each record type is shown in parentheses.</span></span>

|<span data-ttu-id="568b3-208">AzureActiveDirectory</span><span class="sxs-lookup"><span data-stu-id="568b3-208">AzureActiveDirectory</span></span> |<span data-ttu-id="568b3-209">Exchange</span><span class="sxs-lookup"><span data-stu-id="568b3-209">Exchange</span></span>  |<span data-ttu-id="568b3-210">SharePoint 또는 OneDrive</span><span class="sxs-lookup"><span data-stu-id="568b3-210">SharePoint or OneDrive</span></span>|
|:---------|:---------|:---------|
|<span data-ttu-id="568b3-211">AzureActiveDirectory (8)</span><span class="sxs-lookup"><span data-stu-id="568b3-211">AzureActiveDirectory (8)</span></span>|<span data-ttu-id="568b3-212">ExchangeAdmin (1)</span><span class="sxs-lookup"><span data-stu-id="568b3-212">ExchangeAdmin (1)</span></span>|<span data-ttu-id="568b3-213">ComplianceDLPSharePoint (11)</span><span class="sxs-lookup"><span data-stu-id="568b3-213">ComplianceDLPSharePoint (11)</span></span>|
|<span data-ttu-id="568b3-214">AzureActiveDirectoryAccountLogon (9)</span><span class="sxs-lookup"><span data-stu-id="568b3-214">AzureActiveDirectoryAccountLogon (9)</span></span>|<span data-ttu-id="568b3-215">ExchangeItem (2)</span><span class="sxs-lookup"><span data-stu-id="568b3-215">ExchangeItem (2)</span></span>|<span data-ttu-id="568b3-216">ComplianceDLPSharePointClassification (33)</span><span class="sxs-lookup"><span data-stu-id="568b3-216">ComplianceDLPSharePointClassification (33)</span></span>|
|<span data-ttu-id="568b3-217">AzureActiveDirectoryStsLogon (15)</span><span class="sxs-lookup"><span data-stu-id="568b3-217">AzureActiveDirectoryStsLogon (15)</span></span>|<span data-ttu-id="568b3-218">캠페인 (62)</span><span class="sxs-lookup"><span data-stu-id="568b3-218">Campaign (62)</span></span>|<span data-ttu-id="568b3-219">프로젝트 (35)</span><span class="sxs-lookup"><span data-stu-id="568b3-219">Project (35)</span></span>|
||<span data-ttu-id="568b3-220">ComplianceDLPExchange (13)</span><span class="sxs-lookup"><span data-stu-id="568b3-220">ComplianceDLPExchange (13)</span></span>|<span data-ttu-id="568b3-221">SharePoint (4)</span><span class="sxs-lookup"><span data-stu-id="568b3-221">SharePoint (4)</span></span>|
||<span data-ttu-id="568b3-222">ComplianceSupervisionExchange (68)</span><span class="sxs-lookup"><span data-stu-id="568b3-222">ComplianceSupervisionExchange (68)</span></span>|<span data-ttu-id="568b3-223">SharePointCommentOperation (37)</span><span class="sxs-lookup"><span data-stu-id="568b3-223">SharePointCommentOperation (37)</span></span>|
||<span data-ttu-id="568b3-224">CustomerKeyServiceEncryption (69)</span><span class="sxs-lookup"><span data-stu-id="568b3-224">CustomerKeyServiceEncryption (69)</span></span>|<span data-ttu-id="568b3-225">SharePointContentTypeOperation (55)</span><span class="sxs-lookup"><span data-stu-id="568b3-225">SharePointContentTypeOperation (55)</span></span>|
||<span data-ttu-id="568b3-226">ExchangeAggregatedOperation (19)</span><span class="sxs-lookup"><span data-stu-id="568b3-226">ExchangeAggregatedOperation (19)</span></span>|<span data-ttu-id="568b3-227">SharePointFieldOperation (56)</span><span class="sxs-lookup"><span data-stu-id="568b3-227">SharePointFieldOperation (56)</span></span>|
||<span data-ttu-id="568b3-228">ExchangeItemAggregated (50)</span><span class="sxs-lookup"><span data-stu-id="568b3-228">ExchangeItemAggregated (50)</span></span>|<span data-ttu-id="568b3-229">SharePointFileOperation (6)</span><span class="sxs-lookup"><span data-stu-id="568b3-229">SharePointFileOperation (6)</span></span>|
||<span data-ttu-id="568b3-230">ExchangeItemGroup (3)</span><span class="sxs-lookup"><span data-stu-id="568b3-230">ExchangeItemGroup (3)</span></span>|<span data-ttu-id="568b3-231">SharePointListOperation (36)</span><span class="sxs-lookup"><span data-stu-id="568b3-231">SharePointListOperation (36)</span></span>|
||<span data-ttu-id="568b3-232">InformationBarrierPolicyApplication (53)</span><span class="sxs-lookup"><span data-stu-id="568b3-232">InformationBarrierPolicyApplication (53)</span></span>|<span data-ttu-id="568b3-233">SharePointSharingOperation (14)</span><span class="sxs-lookup"><span data-stu-id="568b3-233">SharePointSharingOperation (14)</span></span>|
||||
