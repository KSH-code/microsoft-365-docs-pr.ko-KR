---
title: 권한이 부여된 액세스 관리 시작
f1.keywords:
- NOCSH
ms.author: robmazz
author: robmazz
manager: laurawi
audience: ITPro
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- Strat_O365_IP
- m365-security-compliance
- m365solution-insiderrisk
- m365initiative-compliance
ms.custom:
- Ent_Solutions
- seo-marvel-apr2020
ms.assetid: ''
description: 이 문서를 사용하여 Office 365에서 권한이 부여된 액세스 관리를 사용하도록 설정하고 구성하는 방법을 자세히 알아보는 방법을 사용할 수 있습니다.
ms.openlocfilehash: 0b8d79c3012ecd321d7b00c1566aa557077d55f1
ms.sourcegitcommit: eac5d9f759f290d3c51cafaf335a1a1c43ded927
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "50126535"
---
# <a name="get-started-with-privileged-access-management"></a><span data-ttu-id="542ae-103">권한이 부여된 액세스 관리 시작</span><span class="sxs-lookup"><span data-stu-id="542ae-103">Get started with privileged access management</span></span>

<span data-ttu-id="542ae-104">이 항목에서는 조직에서 권한이 부여된 액세스 관리를 사용하도록 설정하고 구성하는 방법을 안내합니다.</span><span class="sxs-lookup"><span data-stu-id="542ae-104">This topic guides you through enabling and configuring privileged access management in your organization.</span></span> <span data-ttu-id="542ae-105">Microsoft 365 관리 센터 또는 Exchange 관리 PowerShell을 사용하여 권한 있는 액세스를 관리하고 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="542ae-105">You can use either the Microsoft 365 admin center or Exchange Management PowerShell to manage and use privileged access.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="542ae-106">시작하기 전에</span><span class="sxs-lookup"><span data-stu-id="542ae-106">Before you begin</span></span>

<span data-ttu-id="542ae-107">권한이 부여된 액세스 관리를 시작하기 전에 Microsoft [365](https://www.microsoft.com/microsoft-365/compare-all-microsoft-365-plans) 구독 및 추가 기능을 확인해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="542ae-107">Before you get started with privileged access management, you should confirm your [Microsoft 365 subscription](https://www.microsoft.com/microsoft-365/compare-all-microsoft-365-plans) and any add-ons.</span></span> <span data-ttu-id="542ae-108">권한이 부여된 액세스 관리에 액세스하고 사용하려면 조직에 다음 구독 또는 추가 기능 중 하나가 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="542ae-108">To access and use privileged access management, your organization must have one of the following subscriptions or add-ons:</span></span>

- <span data-ttu-id="542ae-109">Microsoft 365 E5 구독(유료 또는 평가판)</span><span class="sxs-lookup"><span data-stu-id="542ae-109">Microsoft 365 E5 subscription (paid or trial version)</span></span>
- <span data-ttu-id="542ae-110">Microsoft 365 E3 구독(또는 Office 365 E3 구독 + Enterprise Mobility and Security E3 구독) + Microsoft 365 E5 규정 준수 추가 기능</span><span class="sxs-lookup"><span data-stu-id="542ae-110">Microsoft 365 E3 subscription (or Office 365 E3 subscription + Enterprise Mobility and Security E3 subscription) + the Microsoft 365 E5 Compliance add-on</span></span>
- <span data-ttu-id="542ae-111">모든 Microsoft 365, Office 365, Exchange, SharePoint 또는 비즈니스용 OneDrive 구독 + Microsoft 365 E5 내부자 위험 관리 추가 기능</span><span class="sxs-lookup"><span data-stu-id="542ae-111">Any Microsoft 365, Office 365, Exchange, SharePoint, or OneDrive for Business subscription + the Microsoft 365 E5 Insider Risk Management add-on</span></span>  
- <span data-ttu-id="542ae-112">Microsoft 365 A5 구독(유료 또는 평가판)</span><span class="sxs-lookup"><span data-stu-id="542ae-112">Microsoft 365 A5 subscription (paid or trial version)</span></span>
- <span data-ttu-id="542ae-113">Microsoft 365 A3 구독(또는 Office 365 A3 구독 + Enterprise Mobility and Security A3 구독) + Microsoft A5 준수 추가 기능</span><span class="sxs-lookup"><span data-stu-id="542ae-113">Microsoft 365 A3 subscription (or Office 365 A3 subscription + Enterprise Mobility and Security A3 subscription) + the Microsoft A5 Compliance add-on</span></span>
- <span data-ttu-id="542ae-114">모든 Microsoft 365, Office 365, Exchange, SharePoint 또는 OneDrive for Education 구독 + Microsoft 365 A5 내부자 위험 관리 추가 기능</span><span class="sxs-lookup"><span data-stu-id="542ae-114">Any Microsoft 365, Office 365, Exchange, SharePoint, or OneDrive for Education subscription + the Microsoft 365 A5 Insider Risk Management add-on</span></span>
- <span data-ttu-id="542ae-115">Office 365 Enterprise E5 구독(유료 또는 평가판)</span><span class="sxs-lookup"><span data-stu-id="542ae-115">Office 365 Enterprise E5 subscription (paid or trial version)</span></span>
- <span data-ttu-id="542ae-116">Office 365 Enterprise E3 구독 + Office 365 고급 준수 추가 기능(더 이상 새 구독에 사용할 수 없음, 참고 참조)</span><span class="sxs-lookup"><span data-stu-id="542ae-116">Office 365 Enterprise E3 subscription + the Office 365 Advanced Compliance add-on (no longer available for new subscriptions, see note)</span></span>

<span data-ttu-id="542ae-117">권한이 부여된 액세스 관리 요청을 제출하고 응답하는 사용자에게 위의 라이선스 중 하나를 할당해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="542ae-117">Users submitting and responding to privileged access management requests must be assigned one of the licenses above.</span></span>

>[!IMPORTANT]
><span data-ttu-id="542ae-118">Office 365 Advanced Compliance는 더 이상 독립 실행형 구독으로 판매하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="542ae-118">Office 365 Advanced Compliance is no longer sold as a standalone subscription.</span></span> <span data-ttu-id="542ae-119">현재 구독이 만료되면 고객은 동일한 또는 추가 규정 준수 기능을 포함하는 위의 구독 중 하나로 전환해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="542ae-119">When current subscriptions expire, customers should transition to one of the subscriptions above, which contain the same or additional compliance features.</span></span>

<span data-ttu-id="542ae-120">기존 Office 365 Enterprise E5 요금제가 없는 경우 권한 있는 액세스 관리를 시도하려는 경우 기존 Office 365 [](https://www.microsoft.com/microsoft-365/enterprise) 구독에 [Microsoft 365를](/office365/admin/try-or-buy-microsoft-365) 추가하거나 Microsoft 365 Enterprise E5 평가판을 등록할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="542ae-120">If you don't have an existing Office 365 Enterprise E5 plan and want to try privileged access management, you can [add Microsoft 365](/office365/admin/try-or-buy-microsoft-365) to your existing Office 365 subscription or [sign up for a trial](https://www.microsoft.com/microsoft-365/enterprise) of Microsoft 365 Enterprise E5.</span></span>

## <a name="enable-and-configure-privileged-access-management"></a><span data-ttu-id="542ae-121">권한이 부여된 액세스 관리 사용 및 구성</span><span class="sxs-lookup"><span data-stu-id="542ae-121">Enable and configure privileged access management</span></span>

<span data-ttu-id="542ae-122">다음 단계에 따라 조직에서 권한이 부여된 액세스를 설정하고 사용하세요.</span><span class="sxs-lookup"><span data-stu-id="542ae-122">Follow these steps to set up and use privileged access in your organization:</span></span>

- [<span data-ttu-id="542ae-123">1단계: 승인자 그룹 만들기</span><span class="sxs-lookup"><span data-stu-id="542ae-123">Step 1: Create an approver's group</span></span>](privileged-access-management-configuration.md#step1)

    <span data-ttu-id="542ae-124">권한 액세스 사용을 시작하기 전에 권한 상승 및 권한 있는 작업에 대한 액세스에 대한 들어오는 요청에 대해 승인 기관이 필요한 사용자를 결정하십시오.</span><span class="sxs-lookup"><span data-stu-id="542ae-124">Before you start using privilege access, determine who needs approval authority for incoming requests for access to elevated and privileged tasks.</span></span> <span data-ttu-id="542ae-125">승인자 그룹의 일부인 사용자는 액세스 요청을 승인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="542ae-125">Any user who is part of the Approvers' group is able to approve access requests.</span></span> <span data-ttu-id="542ae-126">이 그룹은 Office 365에서 메일 사용이 가능한 보안 그룹을 만들어 사용하도록 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="542ae-126">This group is enabled by creating a mail-enabled security group in Office 365.</span></span>

- [<span data-ttu-id="542ae-127">2단계: 권한 있는 액세스 사용</span><span class="sxs-lookup"><span data-stu-id="542ae-127">Step 2: Enable privileged access</span></span>](privileged-access-management-configuration.md#step2)

    <span data-ttu-id="542ae-128">권한 있는 액세스는 권한 있는 액세스 관리 액세스 제어에서 제외하려는 시스템 계정 집합을 포함하여 기본 승인자 그룹을 사용하여 Office 365에서 명시적으로 사용하도록 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="542ae-128">Privileged access must be explicitly enabled in Office 365 with the default approver group, including a set of system accounts that you want excluded from the privileged access management access control.</span></span>

- [<span data-ttu-id="542ae-129">3단계: 액세스 정책 만들기</span><span class="sxs-lookup"><span data-stu-id="542ae-129">Step 3: Create an access policy</span></span>](privileged-access-management-configuration.md#step3)

    <span data-ttu-id="542ae-130">승인 정책을 만들면 개별 작업에서 범위가 지정되는 특정 승인 요구 사항을 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="542ae-130">Creating an approval policy allows you to define the specific approval requirements scoped at individual tasks.</span></span> <span data-ttu-id="542ae-131">승인 유형 옵션은 자동 또는 **수동입니다.** </span><span class="sxs-lookup"><span data-stu-id="542ae-131">The approval type options are **Auto** or **Manual**.</span></span>

- [<span data-ttu-id="542ae-132">4단계: 권한 있는 액세스 요청 제출/승인</span><span class="sxs-lookup"><span data-stu-id="542ae-132">Step 4: Submit/approve privileged access requests</span></span>](privileged-access-management-configuration.md#step4)

    <span data-ttu-id="542ae-133">권한이 부여된 액세스에는 연결된 승인 정책이 정의된 작업에 대한 승인이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="542ae-133">Once enabled, privileged access requires approvals for any task that has an associated approval policy defined.</span></span> <span data-ttu-id="542ae-134">승인 정책에 포함된 작업의 경우 사용자는 작업을 실행하는 데 필요한 사용 권한을 가지기 위해 액세스 승인을 요청하고 부여해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="542ae-134">For tasks included in an approval policy, users must request and be granted access approval to have permissions necessary to execute the task.</span></span>

<span data-ttu-id="542ae-135">승인이 부여된 후 요청하는 사용자는 의도한 작업을 실행할 수 있으며 권한이 부여된 액세스는 사용자를 대신하여 작업을 승인하고 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="542ae-135">After approval is granted, the requesting user can execute the intended task and privileged access will authorize and execute the task on behalf of the user.</span></span> <span data-ttu-id="542ae-136">승인은 요청한 기간(기본 기간은 4시간)에 대해 유효하게 유지되어 요청자에서 의도한 작업을 여러 번 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="542ae-136">The approval remains valid for the requested duration (default duration is 4 hours), during which the requester can execute the intended task multiple times.</span></span> <span data-ttu-id="542ae-137">이러한 모든 실행은 기록되어 보안 및 규정 준수 감사에 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="542ae-137">All such executions are logged and made available for security and compliance auditing.</span></span> 

>[!NOTE]
><span data-ttu-id="542ae-138">Exchange 관리 PowerShell을 사용하여 권한 있는 액세스를 사용하도록 설정하고 구성하려면 다단계 인증을 사용하여 [Exchange Online PowerShell에](/powershell/exchange/connect-to-exchange-online-powershell#connect-to-exchange-online-powershell-using-mfa) 연결의 단계를 수행하여 Office 365 자격 증명을 사용하여 Exchange Online PowerShell에 연결합니다.</span><span class="sxs-lookup"><span data-stu-id="542ae-138">If you want to use Exchange Management PowerShell to enable and configure privileged access, follow the steps in [Connect to Exchange Online PowerShell using Multi-Factor authentication](/powershell/exchange/connect-to-exchange-online-powershell#connect-to-exchange-online-powershell-using-mfa) to connect to Exchange Online PowerShell with your Office 365 credentials.</span></span> <span data-ttu-id="542ae-139">Exchange Online PowerShell에 연결하는 동안 권한이 부여된 액세스를 사용하도록 설정하는 단계를 조직에 대해 다단계 인증을 사용하도록 설정할 필요는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="542ae-139">You do not need to enable multi-factor authentication for your organization to use the steps to enable privileged access while connecting to Exchange Online PowerShell.</span></span> <span data-ttu-id="542ae-140">다단계 인증을 사용하여 연결하면 요청에 서명하는 데 권한이 부여된 액세스에 사용되는 OAuth 토큰이 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="542ae-140">Connecting with multi-factor authentication creates an OAuth token that is used by privileged access for signing your requests.</span></span>

<span data-ttu-id="542ae-141"><a name="step1"> </a></span><span class="sxs-lookup"><span data-stu-id="542ae-141"><a name="step1"> </a></span></span>

## <a name="step-1-create-an-approvers-group"></a><span data-ttu-id="542ae-142">1단계: 승인자 그룹 만들기</span><span class="sxs-lookup"><span data-stu-id="542ae-142">Step 1: Create an approver's group</span></span>

1. <span data-ttu-id="542ae-143">조직의 관리자 계정에 대한 자격 증명을 사용하여 [Microsoft 365](https://admin.microsoft.com) 관리 센터에 로그인합니다.</span><span class="sxs-lookup"><span data-stu-id="542ae-143">Sign into the [Microsoft 365 admin center](https://admin.microsoft.com) using credentials for an admin account in your organization.</span></span>

2. <span data-ttu-id="542ae-144">관리 센터에서 그룹 **추가**  >  **그룹으로 이동하세요.**</span><span class="sxs-lookup"><span data-stu-id="542ae-144">In the Admin Center, go to **Groups** > **Add a group**.</span></span>

3. <span data-ttu-id="542ae-145">메일 **사용이 가능한 보안** 그룹을 선택한 다음 새 그룹의 이름, 그룹 전자 메일 주소 및 **설명** 필드를 입력합니다.  </span><span class="sxs-lookup"><span data-stu-id="542ae-145">Select **mail-enabled security group** and then complete the **Name**, **Group email address**, and **Description** fields for the new group.</span></span>

4. <span data-ttu-id="542ae-146">그룹을 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="542ae-146">Save the group.</span></span> <span data-ttu-id="542ae-147">그룹을 완전히 구성하고 Microsoft 365 관리 센터에 표시하는 데 몇 분 정도 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="542ae-147">It may take a few minutes for the group to be fully configured and to appear in the Microsoft 365 admin center.</span></span>

5. <span data-ttu-id="542ae-148">새 승인자 그룹을 선택하고 편집을 **선택하여** 그룹에 사용자를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="542ae-148">Select the new approver's group and select **edit** to add users to the group.</span></span>

6. <span data-ttu-id="542ae-149">그룹을 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="542ae-149">Save the group.</span></span>

<span data-ttu-id="542ae-150"><a name="step2"> </a></span><span class="sxs-lookup"><span data-stu-id="542ae-150"><a name="step2"> </a></span></span>

## <a name="step-2-enable-privileged-access"></a><span data-ttu-id="542ae-151">2단계: 권한 있는 액세스 사용</span><span class="sxs-lookup"><span data-stu-id="542ae-151">Step 2: Enable privileged access</span></span>

### <a name="in-the-microsoft-365-admin-center"></a><span data-ttu-id="542ae-152">Microsoft 365 관리 센터에서</span><span class="sxs-lookup"><span data-stu-id="542ae-152">In the Microsoft 365 Admin Center</span></span>

1. <span data-ttu-id="542ae-153">조직의 관리자 계정에 대한 자격 증명을 사용하여 [Microsoft 365](https://admin.microsoft.com) 관리 센터에 로그인합니다.</span><span class="sxs-lookup"><span data-stu-id="542ae-153">Sign into the [Microsoft 365 Admin Center](https://admin.microsoft.com) using credentials for an admin account in your organization.</span></span>

2. <span data-ttu-id="542ae-154">관리 센터에서 개인 **정보** 보호 권한이 부여된 액세스  >    >  **& 설정**  >  **보안으로 이동합니다.**</span><span class="sxs-lookup"><span data-stu-id="542ae-154">In the Admin Center, go to **Settings** > **Org Settings** > **Security & Privacy** > **Privileged access**.</span></span>

3. <span data-ttu-id="542ae-155">권한 있는 **작업 컨트롤에 대한 승인 필요를 사용하도록** 설정</span><span class="sxs-lookup"><span data-stu-id="542ae-155">Enable the **Require approvals for privileged tasks** control.</span></span>

4. <span data-ttu-id="542ae-156">1단계에서 만든 승인자 그룹을 기본 승인자 그룹으로 **할당합니다.**</span><span class="sxs-lookup"><span data-stu-id="542ae-156">Assign the approver's group you created in Step 1 as the **Default approvers group**.</span></span>

5. <span data-ttu-id="542ae-157">**저장** 및 **닫기.**</span><span class="sxs-lookup"><span data-stu-id="542ae-157">**Save** and **Close**.</span></span>

### <a name="in-exchange-management-powershell"></a><span data-ttu-id="542ae-158">Exchange 관리 PowerShell에서</span><span class="sxs-lookup"><span data-stu-id="542ae-158">In Exchange Management PowerShell</span></span>

<span data-ttu-id="542ae-159">권한 있는 액세스를 사용하도록 설정하고 승인자 그룹을 할당하려면 Exchange Online PowerShell에서 다음 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="542ae-159">To enable privileged access and to assign the approver's group, run the following command in Exchange Online PowerShell:</span></span>

```PowerShell
Enable-ElevatedAccessControl -AdminGroup '<default approver group>' -SystemAccounts @('<systemAccountUPN1>','<systemAccountUPN2>')
```

<span data-ttu-id="542ae-160">예제:</span><span class="sxs-lookup"><span data-stu-id="542ae-160">Example:</span></span>

```PowerShell
Enable-ElevatedAccessControl -AdminGroup 'pamapprovers@fabrikam.onmicrosoft.com' -SystemAccounts @('sys1@fabrikamorg.onmicrosoft.com', 'sys2@fabrikamorg.onmicrosoft.com')
```

>[!NOTE]
><span data-ttu-id="542ae-161">조직 내의 특정 자동화가 권한 있는 액세스에 종속되지 않고도 작동할 수 있도록 시스템 계정 기능을 사용할 수 있습니다. 그러나 이러한 제외는 예외적인 것이 며 허용되는 제외는 정기적으로 승인 및 감사해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="542ae-161">System accounts feature is made available to ensure certain automations within your organizations can work without dependency on privileged access, however it is recommended that such exclusions be exceptional and those allowed should be approved and audited regularly.</span></span>

<span data-ttu-id="542ae-162"><a name="step3"> </a></span><span class="sxs-lookup"><span data-stu-id="542ae-162"><a name="step3"> </a></span></span>

## <a name="step-3-create-an-access-policy"></a><span data-ttu-id="542ae-163">3단계: 액세스 정책 만들기</span><span class="sxs-lookup"><span data-stu-id="542ae-163">Step 3: Create an access policy</span></span>

<span data-ttu-id="542ae-164">조직에 대해 최대 30개까지 권한 있는 액세스 정책을 만들고 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="542ae-164">You can create and configure up to 30 privileged access policies for your organization.</span></span>

### <a name="in-the-microsoft-365-admin-center"></a><span data-ttu-id="542ae-165">Microsoft 365 관리 센터에서</span><span class="sxs-lookup"><span data-stu-id="542ae-165">In the Microsoft 365 Admin Center</span></span>

1. <span data-ttu-id="542ae-166">조직의 관리자 계정에 대한 자격 증명을 사용하여 [Microsoft 365](https://admin.microsoft.com) 관리 센터에 로그인합니다.</span><span class="sxs-lookup"><span data-stu-id="542ae-166">Sign into the [Microsoft 365 Admin Center](https://admin.microsoft.com) using credentials for an admin account in your organization.</span></span>

2. <span data-ttu-id="542ae-167">관리 센터에서 개인 **정보** 보호 권한이 부여된 액세스  >    >  **& 설정**  >  **보안으로 이동합니다.**</span><span class="sxs-lookup"><span data-stu-id="542ae-167">In the Admin Center, go to **Settings** > **Org Settings** > **Security & Privacy** > **Privileged access**.</span></span>

3. <span data-ttu-id="542ae-168">액세스 **정책 및 요청 관리 선택.**</span><span class="sxs-lookup"><span data-stu-id="542ae-168">Select **Manage access policies and requests**.</span></span>

4. <span data-ttu-id="542ae-169">정책 **구성을** 선택하고 정책 **추가를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="542ae-169">Select **Configure policies** and select **Add a policy**.</span></span>

5. <span data-ttu-id="542ae-170">드롭다운 필드에서 조직에 적합한 값을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="542ae-170">From the drop-down fields, select the appropriate values for your organization:</span></span>
    
    <span data-ttu-id="542ae-171">**정책 유형:** 작업, 역할 또는 역할 그룹</span><span class="sxs-lookup"><span data-stu-id="542ae-171">**Policy type**: Task, Role, or Role Group</span></span>

    <span data-ttu-id="542ae-172">**정책 범위**: Exchange</span><span class="sxs-lookup"><span data-stu-id="542ae-172">**Policy scope**: Exchange</span></span>

    <span data-ttu-id="542ae-173">**정책 이름:** 사용 가능한 정책에서 선택</span><span class="sxs-lookup"><span data-stu-id="542ae-173">**Policy name**: Select from the available policies</span></span>

    <span data-ttu-id="542ae-174">**승인 유형:** 수동 또는 자동</span><span class="sxs-lookup"><span data-stu-id="542ae-174">**Approval type**: Manual or Auto</span></span>

    <span data-ttu-id="542ae-175">**승인 그룹:** 1단계에서 만든 승인자 그룹 선택</span><span class="sxs-lookup"><span data-stu-id="542ae-175">**Approval group**: Select the approvers group created in Step 1</span></span>

6. <span data-ttu-id="542ae-176">**Create(만들기)를** 선택한 다음 **닫기(닫기)를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="542ae-176">Select **Create** and then **Close**.</span></span> <span data-ttu-id="542ae-177">정책을 완전히 구성하고 사용하도록 설정하는 데 몇 분 정도 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="542ae-177">It may take a few minutes for the policy to be fully configured and enabled.</span></span>

### <a name="in-exchange-management-powershell"></a><span data-ttu-id="542ae-178">Exchange 관리 PowerShell에서</span><span class="sxs-lookup"><span data-stu-id="542ae-178">In Exchange Management PowerShell</span></span>

<span data-ttu-id="542ae-179">승인 정책을 만들고 정의하기 위해 Exchange Online PowerShell에서 다음 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="542ae-179">To create and define an approval policy, run the following command in Exchange Online PowerShell:</span></span>

```PowerShell
New-ElevatedAccessApprovalPolicy -Task 'Exchange\<exchange management cmdlet name>' -ApprovalType <Manual, Auto> -ApproverGroup '<default/custom approver group>'
```

<span data-ttu-id="542ae-180">예제:</span><span class="sxs-lookup"><span data-stu-id="542ae-180">Example:</span></span>

```PowerShell
New-ElevatedAccessApprovalPolicy -Task 'Exchange\New-MoveRequest' -ApprovalType Manual -ApproverGroup 'mbmanagers@fabrikamorg.onmicrosoft.com'
```

<span data-ttu-id="542ae-181"><a name="step4"> </a></span><span class="sxs-lookup"><span data-stu-id="542ae-181"><a name="step4"> </a></span></span>

## <a name="step-4-submitapprove-privileged-access-requests"></a><span data-ttu-id="542ae-182">4단계: 권한 있는 액세스 요청 제출/승인</span><span class="sxs-lookup"><span data-stu-id="542ae-182">Step 4: Submit/approve privileged access requests</span></span>

### <a name="requesting-elevation-authorization-to-execute-privileged-tasks"></a><span data-ttu-id="542ae-183">권한 있는 작업 실행을 위한 권한 상승 권한 부여 요청</span><span class="sxs-lookup"><span data-stu-id="542ae-183">Requesting elevation authorization to execute privileged tasks</span></span>

<span data-ttu-id="542ae-184">권한 있는 액세스 요청은 요청이 제출된 후 최대 24시간 동안 유효합니다.</span><span class="sxs-lookup"><span data-stu-id="542ae-184">Requests for privileged access are valid for up to 24 hours after the request is submitted.</span></span> <span data-ttu-id="542ae-185">승인되거나 거부되지 않은 경우 요청이 만료되고 액세스가 승인되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="542ae-185">If not approved or denied, the requests expire and access is not approved.</span></span>

#### <a name="in-the-microsoft-365-admin-center"></a><span data-ttu-id="542ae-186">Microsoft 365 관리 센터에서</span><span class="sxs-lookup"><span data-stu-id="542ae-186">In the Microsoft 365 Admin Center</span></span>

1. <span data-ttu-id="542ae-187">자격 증명을 사용하여 [Microsoft 365](https://admin.microsoft.com) 관리 센터에 로그인합니다.</span><span class="sxs-lookup"><span data-stu-id="542ae-187">Sign into the [Microsoft 365 Admin Center](https://admin.microsoft.com) using your credentials.</span></span>

2. <span data-ttu-id="542ae-188">관리 센터에서 개인 **정보** 보호 권한이 부여된 액세스  >    >  **& 설정**  >  **보안으로 이동합니다.**</span><span class="sxs-lookup"><span data-stu-id="542ae-188">In the Admin Center, go to **Settings** > **Org Settings** > **Security & Privacy** > **Privileged access**.</span></span>

3. <span data-ttu-id="542ae-189">액세스 **정책 및 요청 관리 선택.**</span><span class="sxs-lookup"><span data-stu-id="542ae-189">Select **Manage access policies and requests**.</span></span>

4. <span data-ttu-id="542ae-190">새 **요청을 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="542ae-190">Select **New request**.</span></span> <span data-ttu-id="542ae-191">드롭다운 필드에서 조직에 적합한 값을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="542ae-191">From the drop-down fields, select the appropriate values for your organization:</span></span>

    <span data-ttu-id="542ae-192">**요청 유형**: 작업, 역할 또는 역할 그룹</span><span class="sxs-lookup"><span data-stu-id="542ae-192">**Request type**: Task, Role, or Role Group</span></span>

    <span data-ttu-id="542ae-193">**요청 범위**: Exchange</span><span class="sxs-lookup"><span data-stu-id="542ae-193">**Request scope**: Exchange</span></span>

    <span data-ttu-id="542ae-194">**요청:** 사용 가능한 정책에서 선택</span><span class="sxs-lookup"><span data-stu-id="542ae-194">**Request for**: Select from the available policies</span></span>

    <span data-ttu-id="542ae-195">**기간(시간)**: 요청된 액세스의 시간입니다.</span><span class="sxs-lookup"><span data-stu-id="542ae-195">**Duration (hours)**: Number of hours of requested access.</span></span> <span data-ttu-id="542ae-196">요청할 수 있는 시간 수에는 제한이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="542ae-196">There isn't a limit on the number of hours that can be requested.</span></span>

    <span data-ttu-id="542ae-197">**설명:** 액세스 요청과 관련된 설명의 텍스트 필드</span><span class="sxs-lookup"><span data-stu-id="542ae-197">**Comments**: Text field for comments related to your access request</span></span>

5. <span data-ttu-id="542ae-198">저장을 **선택한** 다음 **닫습니다.**</span><span class="sxs-lookup"><span data-stu-id="542ae-198">Select **Save** and then **Close**.</span></span> <span data-ttu-id="542ae-199">요청은 전자 메일을 통해 승인자 그룹으로 전송됩니다.</span><span class="sxs-lookup"><span data-stu-id="542ae-199">Your request will be sent to the approver's group via email.</span></span>

#### <a name="in-exchange-management-powershell"></a><span data-ttu-id="542ae-200">Exchange 관리 PowerShell에서</span><span class="sxs-lookup"><span data-stu-id="542ae-200">In Exchange Management PowerShell</span></span>

<span data-ttu-id="542ae-201">Exchange Online PowerShell에서 다음 명령을 실행하여 승인자 그룹에 승인 요청을 만들고 제출합니다.</span><span class="sxs-lookup"><span data-stu-id="542ae-201">Run the following command in Exchange Online PowerShell to create and submit an approval request to the approver's group:</span></span>

```PowerShell
New-ElevatedAccessRequest -Task 'Exchange\<exchange management cmdlet name>' -Reason '<appropriate reason>' -DurationHours <duration in hours>
```

<span data-ttu-id="542ae-202">예제:</span><span class="sxs-lookup"><span data-stu-id="542ae-202">Example:</span></span>

```PowerShell
New-ElevatedAccessRequest -Task 'Exchange\New-MoveRequest' -Reason 'Attempting to fix the user mailbox error' -DurationHours 4
```

### <a name="view-status-of-elevation-requests"></a><span data-ttu-id="542ae-203">권한 상승 요청 상태 보기</span><span class="sxs-lookup"><span data-stu-id="542ae-203">View status of elevation requests</span></span>

<span data-ttu-id="542ae-204">승인 요청이 만들어진 후 권한 상승 요청 상태는 요청 ID와 연결된 Exchange 관리 PowerShell 또는 관리 센터에서 검토할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="542ae-204">After an approval request is created, elevation request status can be reviewed in the admin center or in Exchange Management PowerShell using the associated with request ID.</span></span>

#### <a name="in-the-microsoft-365-admin-center"></a><span data-ttu-id="542ae-205">Microsoft 365 관리 센터에서</span><span class="sxs-lookup"><span data-stu-id="542ae-205">In the Microsoft 365 admin center</span></span>

1. <span data-ttu-id="542ae-206">자격 증명으로 [Microsoft 365](https://admin.microsoft.com) 관리 센터에 로그인합니다.</span><span class="sxs-lookup"><span data-stu-id="542ae-206">Sign into the [Microsoft 365 admin center](https://admin.microsoft.com) with your credentials.</span></span>

2. <span data-ttu-id="542ae-207">관리 센터에서 개인 **정보** 보호 권한이 부여된 액세스  >    >  **권한으로 & 설정**  >  **보안으로 이동합니다.**</span><span class="sxs-lookup"><span data-stu-id="542ae-207">In the admin center, go to **Settings** > **Org Settings** > **Security & Privacy** > **Privileged access**.</span></span>

3. <span data-ttu-id="542ae-208">액세스 **정책 및 요청 관리 선택.**</span><span class="sxs-lookup"><span data-stu-id="542ae-208">Select **Manage access policies and requests**.</span></span>

4. <span data-ttu-id="542ae-209">보류 **중,** 승인됨, 거부됨 또는  **고객 Lockbox** 상태를 사용하여 제출된 요청을 필터링하려면 보기를 선택합니다.  </span><span class="sxs-lookup"><span data-stu-id="542ae-209">Select **View** to filter submitted requests by **Pending**, **Approved**, **Denied**, or **Customer Lockbox** status.</span></span>

#### <a name="in-exchange-management-powershell"></a><span data-ttu-id="542ae-210">Exchange 관리 PowerShell에서</span><span class="sxs-lookup"><span data-stu-id="542ae-210">In Exchange Management PowerShell</span></span>

<span data-ttu-id="542ae-211">Exchange Online PowerShell에서 다음 명령을 실행하여 특정 요청 ID에 대한 승인 요청 상태를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="542ae-211">Run the following command in Exchange Online PowerShell to view an approval request status for a specific request ID:</span></span>

```PowerShell
Get-ElevatedAccessRequest -Identity <request ID> | select RequestStatus
```

<span data-ttu-id="542ae-212">예제:</span><span class="sxs-lookup"><span data-stu-id="542ae-212">Example:</span></span>

```PowerShell
Get-ElevatedAccessRequest -Identity 28560ed0-419d-4cc3-8f5b-603911cbd450 | select RequestStatus
```

### <a name="approving-an-elevation-authorization-request"></a><span data-ttu-id="542ae-213">권한 상승 권한 부여 요청 승인</span><span class="sxs-lookup"><span data-stu-id="542ae-213">Approving an elevation authorization request</span></span>

<span data-ttu-id="542ae-214">승인 요청이 생성되면 관련 승인자 그룹의 구성원이 전자 메일 알림을 받고 요청 ID와 관련된 요청을 승인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="542ae-214">When an approval request is created, members of the relevant approver group receive an email notification and can approve the request associated with the request ID.</span></span> <span data-ttu-id="542ae-215">요청자에 전자 메일 메시지를 통해 요청 승인 또는 거부에 대한 알림이 제공됩니다.</span><span class="sxs-lookup"><span data-stu-id="542ae-215">The requestor is notified of the request approval or denial via email message.</span></span>

#### <a name="in-the-microsoft-365-admin-center"></a><span data-ttu-id="542ae-216">Microsoft 365 관리 센터에서</span><span class="sxs-lookup"><span data-stu-id="542ae-216">In the Microsoft 365 admin center</span></span>

1. <span data-ttu-id="542ae-217">자격 증명으로 [Microsoft 365](https://admin.microsoft.com) 관리 센터에 로그인합니다.</span><span class="sxs-lookup"><span data-stu-id="542ae-217">Sign into the [Microsoft 365 admin center](https://admin.microsoft.com) with your credentials.</span></span>

2. <span data-ttu-id="542ae-218">관리 센터에서 개인 **정보** 보호 권한 액세스  >    >  **& 설정**  >  **보안으로 이동합니다.**</span><span class="sxs-lookup"><span data-stu-id="542ae-218">In the admin center, go to **Settings** > **Org Settings** > **Security & Privacy** > **Privileged access**.</span></span>

3. <span data-ttu-id="542ae-219">액세스 **정책 및 요청 관리 선택.**</span><span class="sxs-lookup"><span data-stu-id="542ae-219">Select **Manage access policies and requests**.</span></span>

4. <span data-ttu-id="542ae-220">나열된 요청을 선택하여 세부 정보를 보고 요청에 대한 작업을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="542ae-220">Select a listed request to view the details and to take action on the request.</span></span>

5. <span data-ttu-id="542ae-221">요청을 **승인하려면** 승인을  선택하거나 거부를 선택하여 요청을 거부합니다.</span><span class="sxs-lookup"><span data-stu-id="542ae-221">Select **Approve** to approve the request or select **Deny** to deny the request.</span></span> <span data-ttu-id="542ae-222">이전에 승인된 요청은 해지를 선택하여 액세스가 해지될 **수 있습니다.**</span><span class="sxs-lookup"><span data-stu-id="542ae-222">Previously approved requests can have access revoked by selecting **Revoke**.</span></span>

#### <a name="in-exchange-management-powershell"></a><span data-ttu-id="542ae-223">Exchange 관리 PowerShell에서</span><span class="sxs-lookup"><span data-stu-id="542ae-223">In Exchange Management PowerShell</span></span>

<span data-ttu-id="542ae-224">권한 상승 권한 부여 요청을 승인하기 위해 Exchange Online PowerShell에서 다음 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="542ae-224">To approve an elevation authorization request, run the following command in Exchange Online PowerShell:</span></span>

```PowerShell
Approve-ElevatedAccessRequest -RequestId <request id> -Comment '<approval comment>'
```

<span data-ttu-id="542ae-225">예제:</span><span class="sxs-lookup"><span data-stu-id="542ae-225">Example:</span></span>

```PowerShell
Approve-ElevatedAccessRequest -RequestId a4bc1bdf-00a1-42b4-be65-b6c63d6be279 -Comment '<approval comment>'
```

<span data-ttu-id="542ae-226">권한 상승 권한 부여 요청을 거부하기 위해 Exchange Online PowerShell에서 다음 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="542ae-226">To deny an elevation authorization request, run the following command in Exchange Online PowerShell:</span></span>

```PowerShell
Deny-ElevatedAccessRequest -RequestId <request id> -Comment '<denial comment>'
```

<span data-ttu-id="542ae-227">예제:</span><span class="sxs-lookup"><span data-stu-id="542ae-227">Example:</span></span>

```PowerShell
Deny-ElevatedAccessRequest -RequestId a4bc1bdf-00a1-42b4-be65-b6c63d6be279 -Comment '<denial comment>'
```

## <a name="delete-a-privileged-access-policy-in-office-365"></a><span data-ttu-id="542ae-228">Office 365에서 권한 있는 액세스 정책 삭제</span><span class="sxs-lookup"><span data-stu-id="542ae-228">Delete a privileged access policy in Office 365</span></span>

<span data-ttu-id="542ae-229">조직에서 더 이상 필요하지 않는 경우 권한이 부여된 액세스 정책을 삭제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="542ae-229">If it is no longer needed in your organization, you can delete a privileged access policy.</span></span>

### <a name="in-the-microsoft-365-admin-center"></a><span data-ttu-id="542ae-230">Microsoft 365 관리 센터에서</span><span class="sxs-lookup"><span data-stu-id="542ae-230">In the Microsoft 365 admin center</span></span>

1. <span data-ttu-id="542ae-231">조직의 관리자 계정에 대한 자격 증명을 사용하여 [Microsoft 365](https://admin.microsoft.com) 관리 센터에 로그인합니다.</span><span class="sxs-lookup"><span data-stu-id="542ae-231">Sign into the [Microsoft 365 admin center](https://admin.microsoft.com) using credentials for an admin account in your organization.</span></span>

2. <span data-ttu-id="542ae-232">관리 센터에서 개인 **정보** 보호 권한이 부여된 액세스  >    >  **권한으로 & 설정**  >  **보안으로 이동합니다.**</span><span class="sxs-lookup"><span data-stu-id="542ae-232">In the admin center, go to **Settings** > **Org Settings** > **Security & Privacy** > **Privileged access**.</span></span>

3. <span data-ttu-id="542ae-233">액세스 **정책 및 요청 관리 선택.**</span><span class="sxs-lookup"><span data-stu-id="542ae-233">Select **Manage access policies and requests**.</span></span>

4. <span data-ttu-id="542ae-234">정책 **구성을 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="542ae-234">Select **Configure policies**.</span></span>

5. <span data-ttu-id="542ae-235">삭제할 정책을 선택한 다음 정책 **제거를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="542ae-235">Select the policy you want to delete, then select **Remove Policy**.</span></span>

6. <span data-ttu-id="542ae-236">**닫기** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="542ae-236">Select **Close**.</span></span>

### <a name="in-exchange-management-powershell"></a><span data-ttu-id="542ae-237">Exchange 관리 PowerShell에서</span><span class="sxs-lookup"><span data-stu-id="542ae-237">In Exchange Management PowerShell</span></span>

<span data-ttu-id="542ae-238">권한 있는 액세스 정책을 삭제하려면 Exchange Online Powershell에서 다음 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="542ae-238">To delete a privileged access policy, run the following command in Exchange Online Powershell:</span></span>

```PowerShell
Remove-ElevatedAccessApprovalPolicy -Identity <identity GUID of the policy you want to delete>
```

## <a name="disable-privileged-access-in-office-365"></a><span data-ttu-id="542ae-239">Office 365에서 권한 있는 액세스를 사용하지 않도록 설정</span><span class="sxs-lookup"><span data-stu-id="542ae-239">Disable privileged access in Office 365</span></span>

<span data-ttu-id="542ae-240">필요한 경우 조직에 대해 권한이 부여된 액세스 관리를 사용하지 않도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="542ae-240">If needed, you can disable privileged access management for your organization.</span></span> <span data-ttu-id="542ae-241">권한이 부여된 액세스를 사용할 수 없는 경우 연결된 승인 정책 또는 승인자 그룹은 삭제되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="542ae-241">Disabling privileged access does not delete any associated approval policies or approver groups.</span></span>

### <a name="in-the-microsoft-365-admin-center"></a><span data-ttu-id="542ae-242">Microsoft 365 관리 센터에서</span><span class="sxs-lookup"><span data-stu-id="542ae-242">In the Microsoft 365 admin center</span></span>

1. <span data-ttu-id="542ae-243">조직의 관리자 계정에 대한 자격 증명을 사용하여 [Microsoft 365](https://admin.microsoft.com) 관리 센터에 로그인합니다.</span><span class="sxs-lookup"><span data-stu-id="542ae-243">Sign into the [Microsoft 365 admin center](https://admin.microsoft.com) with credentials for an admin account in your organization.</span></span>

2. <span data-ttu-id="542ae-244">관리 센터에서 개인 **정보** 보호 권한이 부여된 액세스  >    >  **& 설정**  >  **보안으로 이동합니다.**</span><span class="sxs-lookup"><span data-stu-id="542ae-244">In the Admin Center, go to **Settings** > **Org Settings** > **Security & Privacy** > **Privileged access**.</span></span>

3. <span data-ttu-id="542ae-245">권한이 **부여된 액세스 제어에 대한 승인 필요를 사용하도록** 설정</span><span class="sxs-lookup"><span data-stu-id="542ae-245">Enable the **Require approvals for privileged access** control.</span></span>

### <a name="in-exchange-management-powershell"></a><span data-ttu-id="542ae-246">Exchange 관리 PowerShell에서</span><span class="sxs-lookup"><span data-stu-id="542ae-246">In Exchange Management PowerShell</span></span>

<span data-ttu-id="542ae-247">권한 있는 액세스를 사용하지 않도록 설정하기 위해 Exchange Online Powershell에서 다음 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="542ae-247">To disable privileged access, run the following command in Exchange Online Powershell:</span></span>

```PowerShell
Disable-ElevatedAccessControl
```
