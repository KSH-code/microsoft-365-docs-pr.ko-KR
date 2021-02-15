---
title: 엔터프라이즈용 Microsoft 365 테스트 환경에 대한 권한 있는 액세스 관리
f1.keywords:
- NOCSH
ms.author: robmazz
author: robmazz
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
- M365-security-compliance
ms.custom: Ent_TLGs
description: 이 테스트 랩 가이드를 사용하여 엔터프라이즈용 Microsoft 365 테스트 환경을 권한 있는 액세스 관리를 사용하도록 설정할 수 있습니다.
ms.openlocfilehash: e9684ebd2aa147049dadfbda9408257ff801aff0
ms.sourcegitcommit: eac5d9f759f290d3c51cafaf335a1a1c43ded927
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "50126420"
---
# <a name="privileged-access-management-for-your-microsoft-365-for-enterprise-test-environment"></a><span data-ttu-id="84847-103">엔터프라이즈용 Microsoft 365 테스트 환경에 대한 권한 있는 액세스 관리</span><span class="sxs-lookup"><span data-stu-id="84847-103">Privileged access management for your Microsoft 365 for enterprise test environment</span></span>

<span data-ttu-id="84847-104">*이 테스트 랩 가이드는 엔터프라이즈용 Microsoft 365 및 Office 365 Enterprise 테스트 환경에 모두 사용할 수 있습니다.*</span><span class="sxs-lookup"><span data-stu-id="84847-104">*This Test Lab Guide can be used for both Microsoft 365 for enterprise and Office 365 Enterprise test environments.*</span></span>

<span data-ttu-id="84847-105">이 문서에서는 엔터프라이즈용 Microsoft 365 테스트 환경에서 보안을 강화하도록 권한이 부여된 액세스 관리를 구성하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="84847-105">This article describes how to configure privileged access management to increase security in your Microsoft 365 for enterprise test environment.</span></span>

<span data-ttu-id="84847-106">기본 액세스 관리 구성에는 다음 세 단계가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="84847-106">Configuring priviledged access management involves three phases:</span></span>
- [<span data-ttu-id="84847-107">1단계: 엔터프라이즈용 Microsoft 365 테스트 환경 구축</span><span class="sxs-lookup"><span data-stu-id="84847-107">Phase 1: Build out your Microsoft 365 for enterprise test environment</span></span>](#phase-1-build-out-your-microsoft-365-for-enterprise-test-environment)
- [<span data-ttu-id="84847-108">2단계: 권한 있는 액세스 관리 구성</span><span class="sxs-lookup"><span data-stu-id="84847-108">Phase 2: Configure privileged access management</span></span>](#phase-2-configure-privileged-access-management)
- [<span data-ttu-id="84847-109">3단계: 권한 상승 및 권한 있는 작업에 승인이 필요한지 확인</span><span class="sxs-lookup"><span data-stu-id="84847-109">Phase 3: Verify that approval is required for elevated and privileged tasks</span></span>](#phase-3-verify-that-approval-is-required-for-elevated-and-privileged-tasks)

![Microsoft 클라우드의 테스트 랩 가이드](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png)

> [!TIP]
> <span data-ttu-id="84847-111">엔터프라이즈용 Microsoft 365 테스트 랩 가이드 스택의 모든 문서에 대한 시각적 맵은 [엔터프라이즈용 Microsoft 365](../downloads/Microsoft365EnterpriseTLGStack.pdf)테스트 랩 가이드 스택으로 이동하세요.</span><span class="sxs-lookup"><span data-stu-id="84847-111">For a visual map to all the articles in the Microsoft 365 for enterprise Test Lab Guide stack, go to [Microsoft 365 for enterprise Test Lab Guide Stack](../downloads/Microsoft365EnterpriseTLGStack.pdf).</span></span>
  
## <a name="phase-1-build-out-your-microsoft-365-for-enterprise-test-environment"></a><span data-ttu-id="84847-112">1단계: 엔터프라이즈용 Microsoft 365 테스트 환경 구축</span><span class="sxs-lookup"><span data-stu-id="84847-112">Phase 1: Build out your Microsoft 365 for enterprise test environment</span></span>

<span data-ttu-id="84847-113">최소 요구 사항과 함께 경량 방식으로 권한 있는 액세스 관리를 구성하려면 Lightweight [base 구성의](lightweight-base-configuration-microsoft-365-enterprise.md)지침을 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="84847-113">If you want to configure privileged access management in a lightweight way with the minimum requirements, follow the instructions in [Lightweight base configuration](lightweight-base-configuration-microsoft-365-enterprise.md).</span></span>
  
<span data-ttu-id="84847-114">시뮬레이트된 엔터프라이즈에서 권한이 부여된 액세스 관리를 구성하려는 경우 통과 인증의 [지침을 따릅니다.](pass-through-auth-m365-ent-test-environment.md)</span><span class="sxs-lookup"><span data-stu-id="84847-114">If you want to configure privileged access management in a simulated enterprise, follow the instructions in [Pass-through authentication](pass-through-auth-m365-ent-test-environment.md).</span></span>
  
>[!NOTE]
><span data-ttu-id="84847-115">권한이 부여된 액세스 관리를 테스트하는 데는 시뮬레이트된 엔터프라이즈 테스트 환경이 필요하지 않습니다. 여기에는 Active Directory 도메인 서비스 포리스트에 대한 디렉터리 동기화 및 인터넷에 연결된 시뮬레이트된 인트라넷이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="84847-115">Testing privileged access management doesn't require the simulated enterprise test environment, which includes a simulated intranet connected to the internet and directory synchronization for an Active Directory Domain Services forest.</span></span> <span data-ttu-id="84847-116">권한 있는 액세스 관리를 테스트하고 일반적인 조직을 나타내는 환경에서 실험할 수 있도록 여기에 옵션으로 제공됩니다.</span><span class="sxs-lookup"><span data-stu-id="84847-116">It's provided here as an option so that you can test privileged access management and experiment with it in an environment that represents a typical organization.</span></span>

## <a name="phase-2-configure-privileged-access-management"></a><span data-ttu-id="84847-117">2단계: 권한 있는 액세스 관리 구성</span><span class="sxs-lookup"><span data-stu-id="84847-117">Phase 2: Configure privileged access management</span></span>

<span data-ttu-id="84847-118">이 단계에서는 승인자 그룹을 구성하고 엔터프라이즈용 Microsoft 365 테스트 환경에 대해 권한이 부여된 액세스 관리를 사용하도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="84847-118">In this phase, configure an approvers group and enable privileged access management for your Microsoft 365 for enterprise test environment.</span></span> <span data-ttu-id="84847-119">권한 있는 액세스 관리에 대한 추가 세부 정보 및 개요는 [Privileged 액세스 관리를 참조하십시오.](../compliance/privileged-access-management-overview.md)</span><span class="sxs-lookup"><span data-stu-id="84847-119">For additional details and an overview of privileged access management, see [Privileged access management](../compliance/privileged-access-management-overview.md).</span></span>

<span data-ttu-id="84847-120">조직에서 권한이 부여된 액세스를 설정하고 사용하기 위해 다음 단계를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="84847-120">To set up and use privileged access in your organization, perform the following steps.</span></span>

#### <a name="step-1-create-an-approvers-group"></a>[<span data-ttu-id="84847-121">1단계: 승인자 그룹 만들기</span><span class="sxs-lookup"><span data-stu-id="84847-121">Step 1: Create an approver's group</span></span>](../compliance/privileged-access-management-configuration.md#step-1-create-an-approvers-group)

<span data-ttu-id="84847-122">권한이 부여된 액세스 사용을 시작하기 전에 승격된 작업 및 권한 있는 작업에 대한 액세스에 대한 들어오는 요청에 대한 승인 권한이 있는 사용자를 결정하십시오.</span><span class="sxs-lookup"><span data-stu-id="84847-122">Before you start using privileged access, determine who will have approval authority for incoming requests for access to elevated and privileged tasks.</span></span> <span data-ttu-id="84847-123">승인자 그룹의 일부인 모든 사용자는 액세스 요청을 승인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="84847-123">All users who are part of the Approvers’ group can approve access requests.</span></span> <span data-ttu-id="84847-124">권한이 부여된 액세스를 사용하려면 Microsoft 365에서 메일 사용이 가능한 보안 그룹을 만들어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="84847-124">To use privileged access, you must create a mail-enabled security group in Microsoft 365.</span></span> <span data-ttu-id="84847-125">테스트 환경에서 새 보안 그룹 이름을 "권한 있는 액세스 승인자"로 지정하고 이전 테스트 랩 가이드 단계에서 이전에 만든 "사용자 3"을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="84847-125">In your test environment, name the new security group "Privileged Access Approvers" and add the "User 3" that was previously created in previous test lab guide steps.</span></span>

#### <a name="step-2-enable-privileged-access"></a>[<span data-ttu-id="84847-126">2단계: 권한 있는 액세스 사용</span><span class="sxs-lookup"><span data-stu-id="84847-126">Step 2: Enable privileged access</span></span>](../compliance/privileged-access-management-configuration.md#step-2-enable-privileged-access)

<span data-ttu-id="84847-127">기본 승인자 그룹을 사용하여 Microsoft 365에서 권한 있는 액세스를 명시적으로 설정해야 하고 권한 있는 액세스 관리 액세스 제어에서 제외하려는 시스템 계정 집합을 포함해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="84847-127">Privileged access needs to be explicitly turned on in Microsoft 365 with the default approver group, and it must include a set of system accounts that you want excluded from the privileged access management access control.</span></span> <span data-ttu-id="84847-128">이 가이드의 3단계를 시작하기 전에 조직에서 권한이 부여된 액세스를 사용하도록 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="84847-128">Be sure to enable privileged access in your organization before starting Phase 3 of this guide.</span></span>

## <a name="phase-3-verify-that-approval-is-required-for-elevated-and-privileged-tasks"></a><span data-ttu-id="84847-129">3단계: 권한 상승 및 권한 있는 작업에 승인이 필요한지 확인</span><span class="sxs-lookup"><span data-stu-id="84847-129">Phase 3: Verify that approval is required for elevated and privileged tasks</span></span>

<span data-ttu-id="84847-130">이 단계에서는 권한이 부여된 액세스 정책이 작동하고 있으며 사용자가 정의된 권한 상승 및 권한 있는 작업을 실행하기 위해 승인이 필요한지 확인해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="84847-130">In this phase, verify that the privileged access policy is working and that users require approval to execute defined elevated and privileged tasks.</span></span>

### <a name="test-the-ability-to-execute-a-task-not-defined-in-a-privileged-access-policy"></a><span data-ttu-id="84847-131">권한이 부여된 액세스 정책에 정의되지 않은 작업을 실행하는 기능을 테스트합니다.</span><span class="sxs-lookup"><span data-stu-id="84847-131">Test the ability to execute a task NOT defined in a privileged access policy</span></span>

<span data-ttu-id="84847-132">먼저 테스트 환경에서 전역 관리자로 구성된 사용자의 자격 증명을 사용하여 Exchange 관리 PowerShell에 연결하고 새 저널 규칙을 만들도록 시도합니다.</span><span class="sxs-lookup"><span data-stu-id="84847-132">First, connect to Exchange Management PowerShell with the credentials of a user configured as a Global Administrator in your test environment and attempt to create a new Journal rule.</span></span> <span data-ttu-id="84847-133">[New-JournalRule](/powershell/module/exchange/new-journalrule) 작업은 현재 조직에 대한 권한이 부여된 액세스 정책에 정의되어 있지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="84847-133">The [New-JournalRule](/powershell/module/exchange/new-journalrule) task is not currently defined in a privileged access policy for your organization.</span></span>

1. <span data-ttu-id="84847-134">로컬 컴퓨터에서 **Microsoft Corporation의** Exchange Online 원격 PowerShell 모듈을 열고 Microsoft Exchange Online 환경의 전역 관리자 계정을 사용하여  >  **원격 PowerShell 모듈에** 로그인합니다.</span><span class="sxs-lookup"><span data-stu-id="84847-134">On your local computer, open and sign in to the Exchange Online Remote PowerShell Module at **Microsoft Corporation** > **Microsoft Exchange Online Remote PowerShell Module** using the Global Admin account for your test environment.</span></span>

1. <span data-ttu-id="84847-135">Exchange 관리 PowerShell에서 조직에 대한 새 저널 규칙을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="84847-135">In Exchange Management PowerShell, create a new Journal rule for your organization:</span></span>

   ```ExchangeManagementPowerShell
   New-JournalRule -Name "JournalRule1" -Recipient joe@contoso.onmicrosoft.com -JournalEmailAddress barbara@adatum.com -Scope Global -Enabled $true
   ```

1. <span data-ttu-id="84847-136">Exchange 관리 PowerShell에서 새 저널 규칙이 만들어졌습니다.</span><span class="sxs-lookup"><span data-stu-id="84847-136">View that the new Journal Rule was successfully created in Exchange Management PowerShell.</span></span>

### <a name="create-a-new-privileged-access-policy-for-the-new-journalrule-task"></a><span data-ttu-id="84847-137">새 권한 있는 액세스 정책 만들기 작업에 New-JournalRule 권한 있는 액세스 정책 만들기</span><span class="sxs-lookup"><span data-stu-id="84847-137">Create a new privileged access policy for the New-JournalRule task</span></span>

>[!NOTE]
><span data-ttu-id="84847-138">이 가이드의 2단계에서 1단계와 2단계를 아직 완료하지 않은 경우 단계에 따라 "권한 액세스 승인자"라는 승인자 그룹을 만들어 테스트 환경에서 권한이 부여된 액세스를 사용하도록 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="84847-138">If you haven't already completed the Steps 1 and 2 from Phase 2 of this guide, be sure follow the steps to create an approver's group named "Privilege Access Approvers" to enable privileged access in your test environment.</span></span>

1. <span data-ttu-id="84847-139">테스트 환경의 전역 관리자 계정 자격 증명을 사용하여 [Microsoft 365](https://admin.microsoft.com) 관리 센터에 로그인합니다.</span><span class="sxs-lookup"><span data-stu-id="84847-139">Sign in to the [Microsoft 365 admin center](https://admin.microsoft.com) using credentials the Global Admin account for your test environment.</span></span>

2. <span data-ttu-id="84847-140">관리 센터에서 개인 **정보** 보호  >  **권한 & 설정**  >  **보안으로 이동합니다.**</span><span class="sxs-lookup"><span data-stu-id="84847-140">In the Admin Center, go to **Settings** > **Security & Privacy** > **Privileged access**.</span></span>

3. <span data-ttu-id="84847-141">액세스 **정책 및 요청 관리 선택.**</span><span class="sxs-lookup"><span data-stu-id="84847-141">Select **Manage access policies and requests**.</span></span>

4. <span data-ttu-id="84847-142">정책 **구성을** 선택한 다음 정책 **추가를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="84847-142">Select **Configure policies**, and then select **Add a policy**.</span></span>

5. <span data-ttu-id="84847-143">드롭다운 필드에서 다음 값을 선택하거나 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="84847-143">From the drop-down fields, select or enter the following values:</span></span>

    <span data-ttu-id="84847-144">**정책 유형**: 작업</span><span class="sxs-lookup"><span data-stu-id="84847-144">**Policy type**: Task</span></span>

    <span data-ttu-id="84847-145">**정책 범위**: Exchange</span><span class="sxs-lookup"><span data-stu-id="84847-145">**Policy scope**: Exchange</span></span>

    <span data-ttu-id="84847-146">**정책 이름:** 새 저널 규칙</span><span class="sxs-lookup"><span data-stu-id="84847-146">**Policy name**: New Journal Rule</span></span>

    <span data-ttu-id="84847-147">**승인 유형**: 수동</span><span class="sxs-lookup"><span data-stu-id="84847-147">**Approval type**: Manual</span></span>

    <span data-ttu-id="84847-148">**승인 그룹**: 권한이 부여된 액세스 승인자</span><span class="sxs-lookup"><span data-stu-id="84847-148">**Approval group**: Privileged Access Approvers</span></span>

6. <span data-ttu-id="84847-149">**Create(만들기)를** 선택한 다음 **닫기(닫기)를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="84847-149">Select **Create**, and then select **Close**.</span></span> <span data-ttu-id="84847-150">정책을 완전히 구성하고 사용하도록 설정하는 데 몇 분 정도 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="84847-150">It may take a few minutes for the policy to be fully configured and enabled.</span></span> <span data-ttu-id="84847-151">다음 단계에서 승인 요구 사항을 테스트하기 전에 정책을 완전히 사용하도록 설정하는 데 필요한 시간을 허용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="84847-151">Be sure to allow time for the policy to be fully enabled before testing the approval requirement in the next step.</span></span>

### <a name="test-approval-requirement-for-the-new-journalrule-task-defined-in-a-privileged-access-policy"></a><span data-ttu-id="84847-152">권한 있는 액세스 정책에 정의된 New-JournalRule 작업에 대한 승인 요구 사항 테스트</span><span class="sxs-lookup"><span data-stu-id="84847-152">Test approval requirement for the New-JournalRule task defined in a privileged access policy</span></span>

1. <span data-ttu-id="84847-153">로컬 컴퓨터에서 테스트 환경에 대한 전역 관리자 계정을 사용하여 **Microsoft Corporation** Microsoft Exchange Online 원격 PowerShell 모듈의 Exchange Online 원격  >  **PowerShell** 모듈을 열고 로그인합니다.</span><span class="sxs-lookup"><span data-stu-id="84847-153">On your local computer, open and sign in to the Exchange Online Remote PowerShell Module at **Microsoft Corporation** > **Microsoft Exchange Online Remote PowerShell Module** using an using the Global Admin account for your test environment.</span></span>

2. <span data-ttu-id="84847-154">Exchange 관리 PowerShell에서 조직에 대한 새 저널 규칙을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="84847-154">In Exchange Management PowerShell, create a new Journal rule for your organization:</span></span>

   ```ExchangeManagementPowerShell
   New-JournalRule -Name "JournalRule2" -Recipient user1@<your subscription domain> -JournalEmailAddress user1@<your subscription domain> -Scope Global -Enabled $true
   ```

3. <span data-ttu-id="84847-155">Exchange 관리 PowerShell에서 "사용 권한 부족" 오류를 본다.</span><span class="sxs-lookup"><span data-stu-id="84847-155">View the "Insufficient permissions" error in Exchange Management PowerShell:</span></span>

   ```ExchangeManagementPowerShell
   Insufficient permissions. Please raise an elevated access request for this task.
       + CategoryInfo          : NotSpecified: (:) [], LocalizedException
       + FullyQualifiedErrorId : [Server=CY1PR00MB0220,RequestId=7b8c7470-ddd0-4528-a01e-5e20ecc9bd54,TimeStamp=9/19/2018
       7:38:34 PM] [FailureCategory=Cmdlet-LocalizedException] 882BD051
       + PSComputerName        : outlook.office365.com
   ```

### <a name="request-access-to-create-a-new-journal-rule-using-the-new-journalrule-task"></a><span data-ttu-id="84847-156">새 저널 규칙을 만들 수 있도록 액세스 New-JournalRule 요청</span><span class="sxs-lookup"><span data-stu-id="84847-156">Request access to create a new Journal Rule using the New-JournalRule task</span></span>

1. <span data-ttu-id="84847-157">테스트 환경에 대한 전역 관리자 계정을 사용하여 [Microsoft 365](https://admin.microsoft.com) 관리 센터에 로그인합니다.</span><span class="sxs-lookup"><span data-stu-id="84847-157">Sign in to the [Microsoft 365 admin center](https://admin.microsoft.com) using the Global Admin account for your test environment.</span></span>

2. <span data-ttu-id="84847-158">관리 센터에서 개인 **정보** 보호  >  **권한 & 설정**  >  **보안으로 이동합니다.**</span><span class="sxs-lookup"><span data-stu-id="84847-158">In the Admin Center, go to **Settings** > **Security & Privacy** > **Privileged access**.</span></span>

3. <span data-ttu-id="84847-159">액세스 **정책 및 요청 관리 선택.**</span><span class="sxs-lookup"><span data-stu-id="84847-159">Select **Manage access policies and requests**.</span></span>

4. <span data-ttu-id="84847-160">새 **요청을 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="84847-160">Select **New request**.</span></span> <span data-ttu-id="84847-161">드롭다운 필드에서 조직에 적합한 값을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="84847-161">From the drop-down fields, select the appropriate values for your organization:</span></span>

    <span data-ttu-id="84847-162">**요청 유형**: 작업</span><span class="sxs-lookup"><span data-stu-id="84847-162">**Request type**: Task</span></span>

    <span data-ttu-id="84847-163">**요청 범위**: Exchange</span><span class="sxs-lookup"><span data-stu-id="84847-163">**Request scope**: Exchange</span></span>

    <span data-ttu-id="84847-164">**요청:** 새 저널 규칙</span><span class="sxs-lookup"><span data-stu-id="84847-164">**Request for**: New Journal Rule</span></span>

    <span data-ttu-id="84847-165">**기간(시간)**: 2</span><span class="sxs-lookup"><span data-stu-id="84847-165">**Duration (hours)**: 2</span></span>

    <span data-ttu-id="84847-166">**설명**: 새 저널 규칙을 만들 수 있는 권한 요청</span><span class="sxs-lookup"><span data-stu-id="84847-166">**Comments**: Request permission to create a new Journal Rule</span></span>

5. <span data-ttu-id="84847-167">**저장을** 선택한 다음 **닫기 를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="84847-167">Select **Save**, and then select **Close**.</span></span> <span data-ttu-id="84847-168">요청은 전자 메일을 통해 승인자 그룹으로 전송됩니다.</span><span class="sxs-lookup"><span data-stu-id="84847-168">Your request will be sent to the approver's group via email.</span></span>

### <a name="approve-privileged-access-request-for-the-creation-of-a-new-journal-rule"></a><span data-ttu-id="84847-169">새 저널 규칙 만들기에 대한 권한 있는 액세스 요청 승인</span><span class="sxs-lookup"><span data-stu-id="84847-169">Approve privileged access request for the creation of a new Journal Rule</span></span>

1. <span data-ttu-id="84847-170">테스트 환경의 사용자 3에 대한 자격 증명을 사용하여 [Microsoft 365](https://admin.microsoft.com) 관리 센터에 로그인합니다(테스트 환경에서 "권한이 부여된 액세스 승인자" 보안 그룹의 구성원).</span><span class="sxs-lookup"><span data-stu-id="84847-170">Sign in to the [Microsoft 365 admin center](https://admin.microsoft.com) using the credentials for User 3 in your test environment (member of the "Privileged Access Approvers" security group in your test environment).</span></span>

2. <span data-ttu-id="84847-171">관리 센터에서 개인 **정보** 보호  >  **권한 & 설정**  >  **보안으로 이동합니다.**</span><span class="sxs-lookup"><span data-stu-id="84847-171">In the Admin Center, go to **Settings** > **Security & Privacy** > **Privileged access**.</span></span>

3. <span data-ttu-id="84847-172">액세스 **정책 및 요청 관리 선택.**</span><span class="sxs-lookup"><span data-stu-id="84847-172">Select **Manage access policies and requests**.</span></span>

4. <span data-ttu-id="84847-173">보류 중인 요청을 선택한 다음 **승인을** 선택하여 전역 관리자 계정에 대한 액세스 권한을 부여하여 새 저널 규칙을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="84847-173">Select the pending request, and then select **Approve** to grant access to the Global Admin account to create a new Journal Rule.</span></span> <span data-ttu-id="84847-174">전역 관리자 계정(요청하는 사용자)은 승인이 허용된 전자 메일 확인을 받게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="84847-174">The Global Admin account (the requesting user) will receive an email confirmation that approval was granted.</span></span>

### <a name="test-creating-a-new-journal-rule-with-privileged-access-approved-for-the-new-journalrule-task"></a><span data-ttu-id="84847-175">권한 있는 액세스가 승인된 새 저널 규칙 만들기 New-JournalRule 테스트</span><span class="sxs-lookup"><span data-stu-id="84847-175">Test creating a new Journal Rule with privileged access approved for the New-JournalRule task</span></span>

1. <span data-ttu-id="84847-176">로컬 컴퓨터에서 **Microsoft Corporation의** Exchange Online 원격 PowerShell 모듈을 열고 Microsoft Exchange Online 환경의 전역 관리자 계정을 사용하여  >  **원격 PowerShell 모듈에** 로그인합니다.</span><span class="sxs-lookup"><span data-stu-id="84847-176">On your local computer, open and sign in to the Exchange Online Remote PowerShell Module at **Microsoft Corporation** > **Microsoft Exchange Online Remote PowerShell Module** using the Global Admin account for your test environment.</span></span>

1. <span data-ttu-id="84847-177">Exchange 관리 PowerShell에서 조직에 대한 새 저널 규칙을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="84847-177">In Exchange Management PowerShell, create a new Journal rule for your organization:</span></span>

   ```ExchangeManagementPowerShell
   New-JournalRule -Name "JournalRule2" -Recipient user1@<your subscription domain> -JournalEmailAddress user1@<your subscription domain> -Scope Global -Enabled $true
   ```

1. <span data-ttu-id="84847-178">Exchange 관리 PowerShell에서 새 저널 규칙이 만들어졌습니다.</span><span class="sxs-lookup"><span data-stu-id="84847-178">View that the new Journal Rule was successfully created in Exchange Management PowerShell.</span></span>

## <a name="next-step"></a><span data-ttu-id="84847-179">다음 단계</span><span class="sxs-lookup"><span data-stu-id="84847-179">Next step</span></span>

<span data-ttu-id="84847-180">테스트 환경에서 [추가 정보](m365-enterprise-test-lab-guides.md#information-protection) 보호 기능을 살펴보아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="84847-180">Explore additional [information protection](m365-enterprise-test-lab-guides.md#information-protection) features and capabilities in your test environment.</span></span>

## <a name="see-also"></a><span data-ttu-id="84847-181">참고 항목</span><span class="sxs-lookup"><span data-stu-id="84847-181">See also</span></span>

[<span data-ttu-id="84847-182">엔터프라이증용 Microsoft 365 테스트 랩 가이드</span><span class="sxs-lookup"><span data-stu-id="84847-182">Microsoft 365 for enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

[<span data-ttu-id="84847-183">엔터프라이즈용 Microsoft 365 개요</span><span class="sxs-lookup"><span data-stu-id="84847-183">Microsoft 365 for enterprise overview</span></span>](microsoft-365-overview.md)

[<span data-ttu-id="84847-184">기업용 Microsoft 365 설명서</span><span class="sxs-lookup"><span data-stu-id="84847-184">Microsoft 365 for enterprise documentation</span></span>](/microsoft-365-enterprise/)
