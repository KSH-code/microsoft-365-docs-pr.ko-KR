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
ms.openlocfilehash: b07965800c1258c03e3e7615fa88a0ed4e453c40
ms.sourcegitcommit: 260bbb93bbda62db9e88c021ccccfa75ac39a32e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/21/2020
ms.locfileid: "46845880"
---
# <a name="manage-audit-log-retention-policies"></a><span data-ttu-id="c7914-104">로그 보존 정책 감사 관리</span><span class="sxs-lookup"><span data-stu-id="c7914-104">Manage audit log retention policies</span></span>

<span data-ttu-id="c7914-105">보안 및 준수 센터에서 감사 로그 보존 정책을 작성하고 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c7914-105">You can create and manage audit log retention policies in the Security & Compliance Center.</span></span> <span data-ttu-id="c7914-106">감사 로그 보존 정책은 Microsoft 365의 새로운 고급 감사 기능의 일부입니다.</span><span class="sxs-lookup"><span data-stu-id="c7914-106">Audit log retention policies are part of the new Advanced Audit capabilities in Microsoft 365.</span></span> <span data-ttu-id="c7914-107">감사 로그 보존 정책을 사용하여 조직에서 감사 로그를 보존할 기간을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c7914-107">An audit log retention policy lets you specify how long to retain audit logs in your organization.</span></span> <span data-ttu-id="c7914-108">감사 로그를 최대 1년 동안 보유할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c7914-108">You can retain audit logs for up to one year.</span></span> <span data-ttu-id="c7914-109">다음 조건을 기준으로 정책을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c7914-109">You can create policies based on the following criteria:</span></span>

- <span data-ttu-id="c7914-110">하나 이상의 Microsoft 365 서비스에서의 모든 활동</span><span class="sxs-lookup"><span data-stu-id="c7914-110">All activities in one or more Microsoft 365 services</span></span>

- <span data-ttu-id="c7914-111">모든 사용자 또는 특정 사용자가 수행하는 (특정 서비스에서의) 특정 활동</span><span class="sxs-lookup"><span data-stu-id="c7914-111">Specific activities (in a specific service) performed by all users or by specific users</span></span>

- <span data-ttu-id="c7914-112">조직에 여러 정책이 있을 때 더 중시하는 정책을 지정하는 우선 순위</span><span class="sxs-lookup"><span data-stu-id="c7914-112">A priority level that specifies which policy takes precedence in you have multiple policies in your organization</span></span>

## <a name="default-audit-log-retention-policy"></a><span data-ttu-id="c7914-113">기본 로그 보존 정책 감사</span><span class="sxs-lookup"><span data-stu-id="c7914-113">Default audit log retention policy</span></span>

<span data-ttu-id="c7914-114">Microsoft 365의 고급 감사는 모든 조직에 기본 감사 로그 보존 정책을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="c7914-114">Advanced Audit in Microsoft 365 provides a default audit log retention policy for all organizations.</span></span> <span data-ttu-id="c7914-115">이 정책은 1년 동안 모든 Exchange, SharePoint 및 Azure Active Directory 감사 레코드를 보존합니다.</span><span class="sxs-lookup"><span data-stu-id="c7914-115">This policy retains all Exchange, SharePoint, and Azure Active Directory audit records for one year.</span></span> <span data-ttu-id="c7914-116">이 기본 정책은 **Workload** 속성(활동이 발생한 서비스)에 대한 **AzureActiveDirectory**, **Exchange** 또는 **SharePoint** 값을 포함하는 감사 레코드를 유지합니다.</span><span class="sxs-lookup"><span data-stu-id="c7914-116">This default policy retains audit records that contain the value of **AzureActiveDirectory**, **Exchange**, or **SharePoint** for the **Workload** property (which is the service in which the activity occurred).</span></span> <span data-ttu-id="c7914-117">기본 정책은 수정할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="c7914-117">The default policy can't be modified.</span></span> <span data-ttu-id="c7914-118">기본 정책에 포함된 각 워크로드의 레코드 유형 목록은 이 문서의 [추가 정보](#more-information) 섹션을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="c7914-118">See the [More information](#more-information) section in this article for a list of record types for each workload that are included in the default policy.</span></span>

> [!NOTE]
> <span data-ttu-id="c7914-119">기본 감사 로그 보존 정책은 Office 365 또는 Microsoft 365 E5 라이선스가 할당되었거나 Microsoft 365 E5 준수 애드온 라이선스가 있는 사용자가 수행한 활동에 대한 감사 레코드에만 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="c7914-119">The default audit log retention policy only applies to audit records for activity performed by users who are assigned an Office 365 or Microsoft 365 E5 license or have a Microsoft 365 E5 Compliance add-on license.</span></span> <span data-ttu-id="c7914-120">조직에 E5 이외의 사용자가 있는 경우 해당 감사 레코드는 90일 동안 유지됩니다.</span><span class="sxs-lookup"><span data-stu-id="c7914-120">If you have non-E5 users in your organization, their corresponding audit records are retained for 90 days.</span></span>

## <a name="before-you-create-an-audit-log-retention-policy"></a><span data-ttu-id="c7914-121">감사 로그 보존 정책을 생성하기 전에 다음을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="c7914-121">Before you create an audit log retention policy</span></span>

- <span data-ttu-id="c7914-122">사용자는 감사 보존 정책을 만들거나 수정하기 위해 보안 및 준수 센터에서 조직 구성 역할을 할당 받아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c7914-122">You have to be assigned the Organization Configuration role in the Security & Compliance Center to create or modify an audit retention policy.</span></span>

- <span data-ttu-id="c7914-123">조직에서 최대 50개의 감사 로그 보존 정책을 가질 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c7914-123">You can have a maximum of 50 audit log retention policies in your organization.</span></span>

- <span data-ttu-id="c7914-124">감사 로그를 90일 이상 유지하려면 감사 로그를 생성한 사용자에게 Office 365 E5 또는 Microsoft 365 E5 라이선스가 할당되거나 Microsoft 365 E5 규정 준수 또는 E5 eDiscovery 및 감사 추가 기능 라이선스가 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c7914-124">To retain an audit log for longer than 90 days, the user who generated the audit log must be assigned an Office 365 E5 or Microsoft 365 E5 license or have a Microsoft 365 E5 Compliance or E5 eDiscovery and Audit add-on license.</span></span>

- <span data-ttu-id="c7914-125">조직에서 생성한 모든 사용자 정의 감사 로그 보존 정책은 기본 보존 정책보다 우선합니다.</span><span class="sxs-lookup"><span data-stu-id="c7914-125">All custom audit log retention policies (created by your organization) take priority over the default retention policy.</span></span> <span data-ttu-id="c7914-126">예를 들어, 보존 기간이 1년보다 짧은 Exchange 사서함 활동에 대한 감사 로그 보존 정책을 만들면 Exchange 사서함 활동에 대한 감사 레코드가 사용자 지정 정책에 의해 지정된 기간 동안 유지됩니다.</span><span class="sxs-lookup"><span data-stu-id="c7914-126">For example, if you create an audit log retention policy for Exchange mailbox activity that has a retention period that's shorter than one year, audit records for Exchange mailbox activities will be retained for the shorter duration specified by the custom policy.</span></span>

## <a name="create-an-audit-log-retention-policy-in-the-compliance-center"></a><span data-ttu-id="c7914-127">규정 준수 센터에 감사 로그 보존 정책을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="c7914-127">Create an audit log retention policy in the compliance center</span></span>

1. <span data-ttu-id="c7914-128">[https://protection.office.com](https://protection.office.com)으로 이동하여 지정된 사용자 계정으로보안 및 준수 센터의 조직 구성 역할로 로그인하십시오.</span><span class="sxs-lookup"><span data-stu-id="c7914-128">Go to [https://protection.office.com](https://protection.office.com) and sign in with user account that's assigned the Organization Configuration role in the Security & Compliance Center.</span></span>

2. <span data-ttu-id="c7914-129">보안 및 규정 준수 센터의 왼쪽 창에서 **검색** > **감사 로그 검색**을 클릭하십시오.</span><span class="sxs-lookup"><span data-stu-id="c7914-129">In the left pane of the Security & Compliance Center, click **Search** > **Audit log search**.</span></span>

    <span data-ttu-id="c7914-130">**감사 로그 검색** 페이지가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="c7914-130">The **Audit log search** page is displayed.</span></span>

    ![감사 로그 검색 페이지](../media/AuditLogRetentionPolicy1.png)

3. <span data-ttu-id="c7914-132">**새 감사 보존 정책**을 클릭한 후 플라이 아웃 페이지에서 다음 필드를 완료하십시오.</span><span class="sxs-lookup"><span data-stu-id="c7914-132">Click **New audit retention policy**, and then complete the following fields on the flyout page:</span></span>

    ![감사 로그 보존 정책 플라이 아웃 페이지](../media/AuditLogRetentionPolicy2.png)

   <span data-ttu-id="c7914-134">a.</span><span class="sxs-lookup"><span data-stu-id="c7914-134">a.</span></span> <span data-ttu-id="c7914-135">**이름:** 감사 로그 보존 정책의 이름</span><span class="sxs-lookup"><span data-stu-id="c7914-135">**Name:** The name of the audit log retention policy.</span></span> <span data-ttu-id="c7914-136">이 이름은 조직에서 고유해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c7914-136">This name must be unique in your organization.</span></span>

   <span data-ttu-id="c7914-137">b.</span><span class="sxs-lookup"><span data-stu-id="c7914-137">b.</span></span> <span data-ttu-id="c7914-138">**설명:** 선택 사항이지만 레코드 유형 또는 워크로드, 정책에 지정된 사용자 및 기간과 같은 정책에 대한 정보를 제공하는 데 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c7914-138">**Description:** Optional, but helpful to provide information about the policy, such as the record type or workload, users specified in the policy, and the duration.</span></span>

   <span data-ttu-id="c7914-139">c.</span><span class="sxs-lookup"><span data-stu-id="c7914-139">c.</span></span> <span data-ttu-id="c7914-140">**레코드 유형:** 정책이 적용되는 감사 레코드 유형.</span><span class="sxs-lookup"><span data-stu-id="c7914-140">**Record types:** The audit record type the policy applies to.</span></span> <span data-ttu-id="c7914-141">하나 이상의 레코드 유형을 선택하면 정책이 선택한 레코드 유형의 모든 활동에 적용되므로 활동을 선택할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="c7914-141">If you select more than one record type, you can't select activities because the policy will apply to all activities for the selected record types.</span></span> <span data-ttu-id="c7914-142">또한 이 속성을 비워두면 **사용자** 상자에서 사용자를 선택해야합니다.</span><span class="sxs-lookup"><span data-stu-id="c7914-142">Also, if you leave this property blank, you must select a user in the **Users** box.</span></span>

   <span data-ttu-id="c7914-143">d.</span><span class="sxs-lookup"><span data-stu-id="c7914-143">d.</span></span> <span data-ttu-id="c7914-144">**활동:** 이 상자를 사용하여 선택한 레코드 유형에서 활동을 선택하십시오.</span><span class="sxs-lookup"><span data-stu-id="c7914-144">**Activities:** Use this box to choose activities from the record type that you selected.</span></span> <span data-ttu-id="c7914-145">정책을 적용할 특정 활동을 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c7914-145">You can choose specific activities to apply the policy to.</span></span> <span data-ttu-id="c7914-146">특정 활동을 선택하지 않으면 선택한 레코드 유형의 모든 활동에 정책이 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="c7914-146">If you don't choose specific activities, then the policy will apply to all activities of the selected record type.</span></span>

   <span data-ttu-id="c7914-147">e.</span><span class="sxs-lookup"><span data-stu-id="c7914-147">e.</span></span> <span data-ttu-id="c7914-148">**사용자:** 정책을 적용할 하나 이상의 사용자를 선택하십시오.</span><span class="sxs-lookup"><span data-stu-id="c7914-148">**Users:** Select one or more users to apply the policy to.</span></span> <span data-ttu-id="c7914-149">이 상자를 비워 두면 정책이 모든 사용자에 게 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="c7914-149">If you leave this box blank, then the policy will apply to all users.</span></span> <span data-ttu-id="c7914-150">**레코드 유형**을 비워둔 경우, 반드시 사용자를 선택해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c7914-150">If you leave the **Record types** blank, then you must select a user.</span></span>

   <span data-ttu-id="c7914-151">f.</span><span class="sxs-lookup"><span data-stu-id="c7914-151">f.</span></span> <span data-ttu-id="c7914-152">**기간:** 정책 기준을 충족하는 감사 로그를 보유하는 시간입니다.</span><span class="sxs-lookup"><span data-stu-id="c7914-152">**Duration:** The amount of time to retain the audit logs that meet the criteria of the policy.</span></span>

   <span data-ttu-id="c7914-153">g.</span><span class="sxs-lookup"><span data-stu-id="c7914-153">g.</span></span> <span data-ttu-id="c7914-154">**우선 순위:** 이 값은 조직의 감사 로그 보존 정책이 처리되는 순서를 결정합니다.</span><span class="sxs-lookup"><span data-stu-id="c7914-154">**Priority:** This value determines the order in which audit log retention policies in your organization are processed.</span></span> <span data-ttu-id="c7914-155">값이 높을수록 우선 순위가 높습니다.</span><span class="sxs-lookup"><span data-stu-id="c7914-155">A higher value indicates a higher priority.</span></span> <span data-ttu-id="c7914-156">예를 들어, 우선 순위 값이 **5**인 정책은 우선 순위 값이 **0**인 정책보다 우선합니다.</span><span class="sxs-lookup"><span data-stu-id="c7914-156">For example, a policy with a priority value of **5** would take priority over a policy with a priority value of **0**.</span></span> <span data-ttu-id="c7914-157">앞에서 설명한 것처럼 사용자 지정 감사 로그 보존 정책은 조직의 기본 정책보다 우선합니다.</span><span class="sxs-lookup"><span data-stu-id="c7914-157">As previously explained, any custom audit log retention policy takes priority over the default policy for your organization.</span></span>

4. <span data-ttu-id="c7914-158">**저장**을 클릭하여 새 감사 로그 보존 정책을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="c7914-158">Click **Save** to create the new audit log retention policy.</span></span>

<span data-ttu-id="c7914-159">이 시점에서는 보존 정책이 생성되었다는 표시가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="c7914-159">At this time, there's no indication that the retention policy was successfully created.</span></span> <span data-ttu-id="c7914-160">감사 로그 보존 정책의 속성 보기에 대해서는 다음 섹션을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="c7914-160">See the next section on viewing the properties of the audit log retention policies.</span></span>

## <a name="create-an-audit-log-retention-policy-in-powershell"></a><span data-ttu-id="c7914-161">PowerShell에서 감사 로그 보존 정책 생성</span><span class="sxs-lookup"><span data-stu-id="c7914-161">Create an audit log retention policy in PowerShell</span></span>

<span data-ttu-id="c7914-162">보안 및 준수 센터 PowerShell을 사용하여 감사 로그 보존 정책을 만들 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c7914-162">You can also use Security & Compliance Center PowerShell to create audit log retention policies.</span></span> 

1. <span data-ttu-id="c7914-163">[보안 및 준수 센터 PowerShell에 연결하기](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell)</span><span class="sxs-lookup"><span data-stu-id="c7914-163">[Connect to Security & Compliance Center PowerShell](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell).</span></span>

2. <span data-ttu-id="c7914-164">다음 명령을 실행하여 감사 로그 보존 정책을 생성하십시오.</span><span class="sxs-lookup"><span data-stu-id="c7914-164">Run the following command to create an audit log retention policy.</span></span> 

   ```powershell
   New-UnifiedAuditLogRetentionPolicy -Name "Microsoft Teams Audit Policy" -Description "One year retention policy for all Microsoft Teams activities" -RecordTypes MicrosoftTeams -RetentionDuration TwelveMonths -Priority 100
   ```

    <span data-ttu-id="c7914-165">이 예에서는 다음 설정으로 "Microsoft Teams Audit Policy"라는 감사 로그 보존 정책을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="c7914-165">This example creates an audit log retention policy named "Microsoft Teams Audit Policy" with these settings:</span></span>

   - <span data-ttu-id="c7914-166">정책에 대한 설명입니다.</span><span class="sxs-lookup"><span data-stu-id="c7914-166">A description of the policy.</span></span>

   - <span data-ttu-id="c7914-167">모든 Microsoft Teams 활동을 유지합니다(*RecordType* 매개 변수로 정의된 대로).</span><span class="sxs-lookup"><span data-stu-id="c7914-167">Retains all Microsoft Teams activities (as defined by the *RecordType* parameter).</span></span>

   - <span data-ttu-id="c7914-168">1년 동안 Microsoft Teams 감사 로그를 유지합니다.</span><span class="sxs-lookup"><span data-stu-id="c7914-168">Retains Microsoft Teams audit logs for one year.</span></span>

   - <span data-ttu-id="c7914-169">우선 순위 100위</span><span class="sxs-lookup"><span data-stu-id="c7914-169">A priority of 100.</span></span>

<span data-ttu-id="c7914-170">다음은 감사 로그 보존 정책을 만드는 또 다른 예시입니다.</span><span class="sxs-lookup"><span data-stu-id="c7914-170">Here's another example of creating an audit log retention policy.</span></span> <span data-ttu-id="c7914-171">이 정책은 사용자 admin@contoso.onmicrosoft.com에 대해 6 개월 동안 "사용자 로그인" 활동에 대한 감사 로그를 유지합니다.</span><span class="sxs-lookup"><span data-stu-id="c7914-171">This policy retains audit logs for the "User logged in" activity for six months for the user admin@contoso.onmicrosoft.com.</span></span>

```powershell
New-UnifiedAuditLogRetentionPolicy -Name "SixMonth retention for admin logons" -RecordTypes AzureActiveDirectoryStsLogon -Operations UserLoggedIn -UserIds admin@contoso.onmicrosoft.com -RetentionDuration SixMonths -Priority 25
```

<span data-ttu-id="c7914-172">자세한 정보는 [New-UnifiedAuditLogRetentionPolicy](https://docs.microsoft.com/powershell/module/exchange/new-unifiedauditlogretentionpolicy)를 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="c7914-172">For more information, see [New-UnifiedAuditLogRetentionPolicy](https://docs.microsoft.com/powershell/module/exchange/new-unifiedauditlogretentionpolicy).</span></span>

## <a name="view-audit-log-retention-policies"></a><span data-ttu-id="c7914-173">로그 보존 정책 감사 보기</span><span class="sxs-lookup"><span data-stu-id="c7914-173">View audit log retention policies</span></span>

<span data-ttu-id="c7914-174">현재 사용자 지정 감사 로그 보존 정책을 보는 유일한 방법은 보안 및 규정 준수 센터 PowerShell에서 **Get-UnifiedAuditRetentionPolicy** cmdlet을 사용하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="c7914-174">At this time, the only way to view custom audit log retention policies is to use the **Get-UnifiedAuditRetentionPolicy** cmdlet in Security & Compliance Center PowerShell.</span></span> <span data-ttu-id="c7914-175">다음은 조직의 감사 로그 보존 정책에 대한 설정(이전 단계에서 구성한)을 표시하는 샘플 명령입니다.</span><span class="sxs-lookup"><span data-stu-id="c7914-175">Here's a sample command to display the settings (that you configured in the previous step) for the audit log retention policies in your organization.</span></span> <span data-ttu-id="c7914-176">이 명령은 정책을 가장 높은 우선 순위에서 가장 낮은 우선 순위로 정렬합니다.</span><span class="sxs-lookup"><span data-stu-id="c7914-176">This command sorts the policies from the highest to lowest priority.</span></span>

```powershell
Get-UnifiedAuditLogRetentionPolicy | Sort-Object -Property Priority -Descending | FL Priority,Name,Description,RecordTypes,Operations,UserIds,RetentionDuration
```

> [!NOTE]
> <span data-ttu-id="c7914-177">현재 **Get-UnifiedAuditLogRetentionPolicy** cmdlet은 조직의 기본 감사 로그 정책을 반환하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c7914-177">At this time, the **Get-UnifiedAuditLogRetentionPolicy** cmdlet doesn't return the default audit log policy for your organization.</span></span>

<span data-ttu-id="c7914-178">자세한 정보는 [Get-UnifiedAuditLogRetentionPolicy](https://docs.microsoft.com/powershell/module/exchange/get-unifiedauditlogretentionpolicy)를 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="c7914-178">For more information, see [Get-UnifiedAuditLogRetentionPolicy](https://docs.microsoft.com/powershell/module/exchange/get-unifiedauditlogretentionpolicy).</span></span>

## <a name="more-information"></a><span data-ttu-id="c7914-179">추가 정보</span><span class="sxs-lookup"><span data-stu-id="c7914-179">More information</span></span>

- <span data-ttu-id="c7914-180">보안 및 규정 센터 PowerShell에서 **Set-UnifiedAuditLogRetentionPolicy** cmdlet을 사용하여 기존 감사 로그 보존 정책을 수정하십시오.</span><span class="sxs-lookup"><span data-stu-id="c7914-180">Use the **Set-UnifiedAuditLogRetentionPolicy** cmdlet in Security & Compliance Center PowerShell to modify an existing audit log retention policy.</span></span> <span data-ttu-id="c7914-181">자세한 정보는 [Set-UnifiedAuditLogRetentionPolicy](https://docs.microsoft.com/powershell/module/exchange/set-unifiedauditlogretentionpolicy)를 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="c7914-181">For more information, see [Set-UnifiedAuditLogRetentionPolicy](https://docs.microsoft.com/powershell/module/exchange/set-unifiedauditlogretentionpolicy).</span></span>

- <span data-ttu-id="c7914-182">보안 및 준수 센터 PowerShell에서 **Remove-UnifiedAuditLogRetentionPolicy** cmdlet을 사용하여 감사 로그 보존 정책을 삭제하십시오.</span><span class="sxs-lookup"><span data-stu-id="c7914-182">Use the **Remove-UnifiedAuditLogRetentionPolicy** cmdlet in Security & Compliance Center PowerShell to delete an audit log retention policy.</span></span> <span data-ttu-id="c7914-183">정책을 제거하는 데 최대 30분이 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c7914-183">It might take up to 30 minutes for the policy to be removed.</span></span> <span data-ttu-id="c7914-184">자세한 정보는 [Remove-UnifiedAuditLogRetentionPolicy](https://docs.microsoft.com/powershell/module/exchange/remove-unifiedauditlogretentionpolicy)를 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="c7914-184">For more information, see [Remove-UnifiedAuditLogRetentionPolicy](https://docs.microsoft.com/powershell/module/exchange/remove-unifiedauditlogretentionpolicy).</span></span>

- <span data-ttu-id="c7914-185">앞에서 설명한 것처럼 Azure Active Directory, Exchange 및 SharePoint의 작업에 대한 감사 레코드는 1년 동안 유지됩니다.</span><span class="sxs-lookup"><span data-stu-id="c7914-185">As previously stated, audit records for operations in Azure Active Directory, Exchange, and SharePoint are retained for one year.</span></span> <span data-ttu-id="c7914-186">다음 표에는 기본 감사 로그 보존 정책에 포함된 모든 레코드 유형(이러한 각 서비스에 대한)이 나열되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c7914-186">The following table lists all the record types (for each of these services) included in the default audit log retention policy.</span></span> <span data-ttu-id="c7914-187">이는 특정 레코드 유형, 작업 또는 사용자에 대해 사용자 지정 감사 로그 보존 정책이 우선하지 않는 한 이 레코드 유형의 작업에 대한 감사 로그가 1년 동안 보존됨을 의미합니다.</span><span class="sxs-lookup"><span data-stu-id="c7914-187">This means that audit logs for any operation with this record type are retained for one year unless a custom audit log retention policy takes precedence for a specific record type, operation, or user.</span></span> <span data-ttu-id="c7914-188">각 레코드 유형에 대한 Enum 값(감사 레코드의 RecordType 속성 값으로 표시됨)이 괄호 안에 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="c7914-188">The Enum value (which is displayed as the value for the RecordType property in an audit record) for each record type is shown in parentheses.</span></span>

   |<span data-ttu-id="c7914-189">AzureActiveDirectory</span><span class="sxs-lookup"><span data-stu-id="c7914-189">AzureActiveDirectory</span></span> |<span data-ttu-id="c7914-190">Exchange</span><span class="sxs-lookup"><span data-stu-id="c7914-190">Exchange</span></span>  |<span data-ttu-id="c7914-191">SharePoint</span><span class="sxs-lookup"><span data-stu-id="c7914-191">SharePoint</span></span>|
   |:---------|:---------|:---------|
   |<span data-ttu-id="c7914-192">AzureActiveDirectory (8)</span><span class="sxs-lookup"><span data-stu-id="c7914-192">AzureActiveDirectory (8)</span></span>|<span data-ttu-id="c7914-193">ExchangeAdmin (1)</span><span class="sxs-lookup"><span data-stu-id="c7914-193">ExchangeAdmin (1)</span></span>|<span data-ttu-id="c7914-194">ComplianceDLPSharePoint (11)</span><span class="sxs-lookup"><span data-stu-id="c7914-194">ComplianceDLPSharePoint (11)</span></span>|
   |<span data-ttu-id="c7914-195">AzureActiveDirectoryAccountLogon (9)</span><span class="sxs-lookup"><span data-stu-id="c7914-195">AzureActiveDirectoryAccountLogon (9)</span></span>|<span data-ttu-id="c7914-196">ExchangeItem (2)</span><span class="sxs-lookup"><span data-stu-id="c7914-196">ExchangeItem (2)</span></span>|<span data-ttu-id="c7914-197">ComplianceDLPSharePointClassification (33)</span><span class="sxs-lookup"><span data-stu-id="c7914-197">ComplianceDLPSharePointClassification (33)</span></span>|
   |<span data-ttu-id="c7914-198">AzureActiveDirectoryStsLogon (15)</span><span class="sxs-lookup"><span data-stu-id="c7914-198">AzureActiveDirectoryStsLogon (15)</span></span>|<span data-ttu-id="c7914-199">캠페인 (62)</span><span class="sxs-lookup"><span data-stu-id="c7914-199">Campaign (62)</span></span>|<span data-ttu-id="c7914-200">프로젝트 (35)</span><span class="sxs-lookup"><span data-stu-id="c7914-200">Project (35)</span></span>|
   ||<span data-ttu-id="c7914-201">ComplianceDLPExchange (13)</span><span class="sxs-lookup"><span data-stu-id="c7914-201">ComplianceDLPExchange (13)</span></span>|<span data-ttu-id="c7914-202">SharePoint (4)</span><span class="sxs-lookup"><span data-stu-id="c7914-202">SharePoint (4)</span></span>|
   ||<span data-ttu-id="c7914-203">ComplianceSupervisionExchange (68)</span><span class="sxs-lookup"><span data-stu-id="c7914-203">ComplianceSupervisionExchange (68)</span></span>|<span data-ttu-id="c7914-204">SharePointCommentOperation (37)</span><span class="sxs-lookup"><span data-stu-id="c7914-204">SharePointCommentOperation (37)</span></span>|
   ||<span data-ttu-id="c7914-205">CustomerKeyServiceEncryption (69)</span><span class="sxs-lookup"><span data-stu-id="c7914-205">CustomerKeyServiceEncryption (69)</span></span>|<span data-ttu-id="c7914-206">SharePointContentTypeOperation (55)</span><span class="sxs-lookup"><span data-stu-id="c7914-206">SharePointContentTypeOperation (55)</span></span>|
   ||<span data-ttu-id="c7914-207">ExchangeAggregatedOperation (19)</span><span class="sxs-lookup"><span data-stu-id="c7914-207">ExchangeAggregatedOperation (19)</span></span>|<span data-ttu-id="c7914-208">SharePointFieldOperation (56)</span><span class="sxs-lookup"><span data-stu-id="c7914-208">SharePointFieldOperation (56)</span></span>|
   ||<span data-ttu-id="c7914-209">ExchangeItemAggregated (50)</span><span class="sxs-lookup"><span data-stu-id="c7914-209">ExchangeItemAggregated (50)</span></span>|<span data-ttu-id="c7914-210">SharePointFileOperation (6)</span><span class="sxs-lookup"><span data-stu-id="c7914-210">SharePointFileOperation (6)</span></span>|
   ||<span data-ttu-id="c7914-211">ExchangeItemGroup (3)</span><span class="sxs-lookup"><span data-stu-id="c7914-211">ExchangeItemGroup (3)</span></span>|<span data-ttu-id="c7914-212">SharePointListOperation (36)</span><span class="sxs-lookup"><span data-stu-id="c7914-212">SharePointListOperation (36)</span></span>|
   ||<span data-ttu-id="c7914-213">InformationBarrierPolicyApplication (53)</span><span class="sxs-lookup"><span data-stu-id="c7914-213">InformationBarrierPolicyApplication (53)</span></span>|<span data-ttu-id="c7914-214">SharePointSharingOperation (14)</span><span class="sxs-lookup"><span data-stu-id="c7914-214">SharePointSharingOperation (14)</span></span>|
   ||||
