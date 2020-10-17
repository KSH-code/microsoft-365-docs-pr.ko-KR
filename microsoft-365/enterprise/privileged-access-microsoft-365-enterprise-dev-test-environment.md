---
title: 엔터프라이즈 테스트 환경용 Microsoft 365에 대 한 권한이 부여 된 액세스 관리
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
description: 이 테스트 랩 가이드를 사용 하 여 권한 있는 액세스 관리 엔터프라이즈 테스트 환경용 Microsoft 365을 사용 하도록 설정 합니다.
ms.openlocfilehash: 24ca7a6408a4290c54dd2bcd7c3f6061eb8f6c05
ms.sourcegitcommit: 53ff1fe6d6143b0bf011031eea9b85dc01ae4f74
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48487591"
---
# <a name="privileged-access-management-for-your-microsoft-365-for-enterprise-test-environment"></a><span data-ttu-id="38c01-103">엔터프라이즈 테스트 환경용 Microsoft 365에 대 한 권한이 부여 된 액세스 관리</span><span class="sxs-lookup"><span data-stu-id="38c01-103">Privileged access management for your Microsoft 365 for enterprise test environment</span></span>

<span data-ttu-id="38c01-104">*이 테스트 랩 가이드는 enterprise 및 Office 365 Enterprise 테스트 환경용 Microsoft 365에 모두 사용할 수 있습니다.*</span><span class="sxs-lookup"><span data-stu-id="38c01-104">*This Test Lab Guide can be used for both Microsoft 365 for enterprise and Office 365 Enterprise test environments.*</span></span>

<span data-ttu-id="38c01-105">이 문서에서는 엔터프라이즈 테스트 환경용 Microsoft 365의 보안을 강화 하도록 권한이 부여 된 액세스 관리를 구성 하는 방법을 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="38c01-105">This article describes how to configure privileged access management to increase security in your Microsoft 365 for enterprise test environment.</span></span>

<span data-ttu-id="38c01-106">Priviledged 액세스 관리 구성에는 다음 세 단계가 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="38c01-106">Configuring priviledged access management involves three phases:</span></span>
- [<span data-ttu-id="38c01-107">1 단계: 엔터프라이즈 테스트 환경용 Microsoft 365 구축</span><span class="sxs-lookup"><span data-stu-id="38c01-107">Phase 1: Build out your Microsoft 365 for enterprise test environment</span></span>](#phase-1-build-out-your-microsoft-365-for-enterprise-test-environment)
- [<span data-ttu-id="38c01-108">2 단계: 권한 있는 액세스 관리 구성</span><span class="sxs-lookup"><span data-stu-id="38c01-108">Phase 2: Configure privileged access management</span></span>](#phase-2-configure-privileged-access-management)
- [<span data-ttu-id="38c01-109">3 단계: 관리자 권한 및 권한 있는 작업에 대 한 승인이 필요한 지 확인</span><span class="sxs-lookup"><span data-stu-id="38c01-109">Phase 3: Verify that approval is required for elevated and privileged tasks</span></span>](#phase-3-verify-that-approval-is-required-for-elevated-and-privileged-tasks)

![Microsoft 클라우드의 테스트 랩 가이드](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png)

> [!TIP]
> <span data-ttu-id="38c01-111">엔터프라이즈 테스트 랩 가이드 스택의 Microsoft 365에 있는 모든 문서에 대 한 시각적 지도를 보려면 [microsoft 365 for 엔터프라이즈 테스트 랩 가이드 스택을](../downloads/Microsoft365EnterpriseTLGStack.pdf)방문 하세요.</span><span class="sxs-lookup"><span data-stu-id="38c01-111">For a visual map to all the articles in the Microsoft 365 for enterprise Test Lab Guide stack, go to [Microsoft 365 for enterprise Test Lab Guide Stack](../downloads/Microsoft365EnterpriseTLGStack.pdf).</span></span>
  
## <a name="phase-1-build-out-your-microsoft-365-for-enterprise-test-environment"></a><span data-ttu-id="38c01-112">1 단계: 엔터프라이즈 테스트 환경용 Microsoft 365 구축</span><span class="sxs-lookup"><span data-stu-id="38c01-112">Phase 1: Build out your Microsoft 365 for enterprise test environment</span></span>

<span data-ttu-id="38c01-113">최소 요구 사항에 따라 간단한 방식으로 권한이 부여 된 액세스 관리를 구성 하려면 [경량 기본 구성](lightweight-base-configuration-microsoft-365-enterprise.md)의 지침을 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="38c01-113">If you want to configure privileged access management in a lightweight way with the minimum requirements, follow the instructions in [Lightweight base configuration](lightweight-base-configuration-microsoft-365-enterprise.md).</span></span>
  
<span data-ttu-id="38c01-114">시뮬레이트된 엔터프라이즈에서 권한이 부여 된 액세스 관리를 구성 하려면 [통과 인증](pass-through-auth-m365-ent-test-environment.md)의 지침을 따르세요.</span><span class="sxs-lookup"><span data-stu-id="38c01-114">If you want to configure privileged access management in a simulated enterprise, follow the instructions in [Pass-through authentication](pass-through-auth-m365-ent-test-environment.md).</span></span>
  
>[!NOTE]
><span data-ttu-id="38c01-115">권한이 부여 된 액세스 관리를 테스트 하려면 Active Directory 도메인 서비스 포리스트의 인터넷 및 디렉터리 동기화에 연결 된 시뮬레이트된 인트라넷을 포함 하는 시뮬레이트된 엔터프라이즈 테스트 환경이 필요 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="38c01-115">Testing privileged access management doesn't require the simulated enterprise test environment, which includes a simulated intranet connected to the internet and directory synchronization for an Active Directory Domain Services forest.</span></span> <span data-ttu-id="38c01-116">이 섹션은 권한 있는 액세스 관리를 테스트 하 고 일반적인 조직을 나타내는 환경에서 테스트할 수 있도록 옵션으로 제공 됩니다.</span><span class="sxs-lookup"><span data-stu-id="38c01-116">It's provided here as an option so that you can test privileged access management and experiment with it in an environment that represents a typical organization.</span></span>

## <a name="phase-2-configure-privileged-access-management"></a><span data-ttu-id="38c01-117">2 단계: 권한 있는 액세스 관리 구성</span><span class="sxs-lookup"><span data-stu-id="38c01-117">Phase 2: Configure privileged access management</span></span>

<span data-ttu-id="38c01-118">이 단계에서는 승인자 그룹을 구성 하 고 Microsoft 365에 대 한 권한이 부여 된 액세스 관리를 엔터프라이즈 테스트 환경에 사용 하도록 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="38c01-118">In this phase, configure an approvers group and enable privileged access management for your Microsoft 365 for enterprise test environment.</span></span> <span data-ttu-id="38c01-119">권한 있는 액세스 관리에 대 한 자세한 내용 및 개요는 [권한이 부여 된 액세스 관리](../compliance/privileged-access-management-overview.md)를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="38c01-119">For additional details and an overview of privileged access management, see [Privileged access management](../compliance/privileged-access-management-overview.md).</span></span>

<span data-ttu-id="38c01-120">조직에서 권한이 부여 된 액세스를 설정 및 사용 하려면 다음 단계를 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="38c01-120">To set up and use privileged access in your organization, perform the following steps.</span></span>

#### <a name="step-1-create-an-approvers-group"></a>[<span data-ttu-id="38c01-121">1 단계: 승인자 그룹 만들기</span><span class="sxs-lookup"><span data-stu-id="38c01-121">Step 1: Create an approver's group</span></span>](../compliance/privileged-access-management-configuration.md#step-1-create-an-approvers-group)

<span data-ttu-id="38c01-122">권한 있는 액세스 사용을 시작 하기 전에 관리자 권한 및 권한 있는 작업에 대 한 수신 요청 액세스에 대 한 승인 기관을 사용자에 게 결정 합니다.</span><span class="sxs-lookup"><span data-stu-id="38c01-122">Before you start using privileged access, determine who will have approval authority for incoming requests for access to elevated and privileged tasks.</span></span> <span data-ttu-id="38c01-123">승인자 그룹에 속하는 모든 사용자는 액세스 요청을 승인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="38c01-123">All users who are part of the Approvers’ group can approve access requests.</span></span> <span data-ttu-id="38c01-124">권한 있는 액세스를 사용 하려면 Microsoft 365에서 메일 사용이 가능한 보안 그룹을 만들어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="38c01-124">To use privileged access, you must create a mail-enabled security group in Microsoft 365.</span></span> <span data-ttu-id="38c01-125">테스트 환경에서 새 보안 그룹 "권한이 부여 된 액세스 승인자"의 이름을 선택 하 고 이전 테스트 랩 가이드 단계에서 이전에 만든 "사용자 3"을 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="38c01-125">In your test environment, name the new security group "Privileged Access Approvers" and add the "User 3" that was previously created in previous test lab guide steps.</span></span>

#### <a name="step-2-enable-privileged-access"></a>[<span data-ttu-id="38c01-126">2 단계: 권한 있는 액세스 사용</span><span class="sxs-lookup"><span data-stu-id="38c01-126">Step 2: Enable privileged access</span></span>](../compliance/privileged-access-management-configuration.md#step-2-enable-privileged-access)

<span data-ttu-id="38c01-127">권한 있는 액세스는 Microsoft 365에서 기본 승인자 그룹을 사용 하 여 명시적으로 설정 해야 하며, 권한이 부여 된 액세스 관리 액세스 제어에서 제외 하려는 시스템 계정 집합을 포함 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="38c01-127">Privileged access needs to be explicitly turned on in Microsoft 365 with the default approver group, and it must include a set of system accounts that you want excluded from the privileged access management access control.</span></span> <span data-ttu-id="38c01-128">이 가이드의 3 단계를 시작 하기 전에 조직에서 권한이 부여 된 액세스를 사용 하도록 설정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="38c01-128">Be sure to enable privileged access in your organization before starting Phase 3 of this guide.</span></span>

## <a name="phase-3-verify-that-approval-is-required-for-elevated-and-privileged-tasks"></a><span data-ttu-id="38c01-129">3 단계: 관리자 권한 및 권한 있는 작업에 대 한 승인이 필요한 지 확인</span><span class="sxs-lookup"><span data-stu-id="38c01-129">Phase 3: Verify that approval is required for elevated and privileged tasks</span></span>

<span data-ttu-id="38c01-130">이 단계에서는 권한이 부여 된 액세스 정책이 작동 하 고 사용자에 게 권한 상승 및 권한 있는 작업을 실행 하기 위한 승인이 필요한 지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="38c01-130">In this phase, verify that the privileged access policy is working and that users require approval to execute defined elevated and privileged tasks.</span></span>

### <a name="test-the-ability-to-execute-a-task-not-defined-in-a-privileged-access-policy"></a><span data-ttu-id="38c01-131">권한이 부여 된 액세스 정책에 정의 되지 않은 작업 실행 기능 테스트</span><span class="sxs-lookup"><span data-stu-id="38c01-131">Test the ability to execute a task NOT defined in a privileged access policy</span></span>

<span data-ttu-id="38c01-132">먼저 테스트 환경에서 전역 관리자로 구성 된 사용자의 자격 증명을 사용 하 여 Exchange 관리 PowerShell에 연결한 다음 새 저널 규칙을 만들려고 합니다.</span><span class="sxs-lookup"><span data-stu-id="38c01-132">First, connect to Exchange Management PowerShell with the credentials of a user configured as a Global Administrator in your test environment and attempt to create a new Journal rule.</span></span> <span data-ttu-id="38c01-133">[Set-journalrule](https://docs.microsoft.com/powershell/module/exchange/new-journalrule) 작업은 현재 조직에 대해 권한이 부여 된 액세스 정책에 정의 되어 있지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="38c01-133">The [New-JournalRule](https://docs.microsoft.com/powershell/module/exchange/new-journalrule) task is not currently defined in a privileged access policy for your organization.</span></span>

1. <span data-ttu-id="38c01-134">로컬 컴퓨터에서 **Microsoft Corporation**  >  테스트 환경의 전역 관리자 계정을 사용 하 여 microsoft Corporation**microsoft exchange online 원격 powershell** 모듈에서 Exchange online 원격 powershell 모듈을 열고 로그인 합니다.</span><span class="sxs-lookup"><span data-stu-id="38c01-134">On your local computer, open and sign in to the Exchange Online Remote PowerShell Module at **Microsoft Corporation** > **Microsoft Exchange Online Remote PowerShell Module** using the Global Admin account for your test environment.</span></span>

1. <span data-ttu-id="38c01-135">Exchange 관리 PowerShell에서 조직에 대 한 새 저널 규칙을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="38c01-135">In Exchange Management PowerShell, create a new Journal rule for your organization:</span></span>

   ```ExchangeManagementPowerShell
   New-JournalRule -Name "JournalRule1" -Recipient joe@contoso.onmicrosoft.com -JournalEmailAddress barbara@adatum.com -Scope Global -Enabled $true
   ```

1. <span data-ttu-id="38c01-136">Exchange 관리 PowerShell에서 새 저널 규칙을 성공적으로 만들었는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="38c01-136">View that the new Journal Rule was successfully created in Exchange Management PowerShell.</span></span>

### <a name="create-a-new-privileged-access-policy-for-the-new-journalrule-task"></a><span data-ttu-id="38c01-137">New-JournalRule 작업에 대 한 새 권한 있는 액세스 정책 만들기</span><span class="sxs-lookup"><span data-stu-id="38c01-137">Create a new privileged access policy for the New-JournalRule task</span></span>

>[!NOTE]
><span data-ttu-id="38c01-138">이 가이드의 2 단계에 나와 있는 1 ~ 2 단계를 아직 완료 하지 않은 경우에는 단계에 따라 "권한 액세스 승인자" 라는 승인자 그룹을 만들어 테스트 환경에서 권한이 부여 된 액세스를 사용 하도록 설정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="38c01-138">If you haven't already completed the Steps 1 and 2 from Phase 2 of this guide, be sure follow the steps to create an approver's group named "Privilege Access Approvers" to enable privileged access in your test environment.</span></span>

1. <span data-ttu-id="38c01-139">자격 증명을 사용 하 여 [Microsoft 365 관리 센터](https://admin.microsoft.com) 에 로그인 테스트 환경에 대 한 전역 관리자 계정입니다.</span><span class="sxs-lookup"><span data-stu-id="38c01-139">Sign in to the [Microsoft 365 admin center](https://admin.microsoft.com) using credentials the Global Admin account for your test environment.</span></span>

2. <span data-ttu-id="38c01-140">관리 센터에서 **설정**  >  **보안 & 개인 정보**  >  **권한이 부여 된 액세스**로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="38c01-140">In the Admin Center, go to **Settings** > **Security & Privacy** > **Privileged access**.</span></span>

3. <span data-ttu-id="38c01-141">**액세스 정책 및 요청 관리를**선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="38c01-141">Select **Manage access policies and requests**.</span></span>

4. <span data-ttu-id="38c01-142">**정책 구성을**선택 하 고 **정책 추가**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="38c01-142">Select **Configure policies**, and then select **Add a policy**.</span></span>

5. <span data-ttu-id="38c01-143">드롭다운 필드에서 다음 값을 선택 하거나 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="38c01-143">From the drop-down fields, select or enter the following values:</span></span>

    <span data-ttu-id="38c01-144">**정책 유형**: 작업</span><span class="sxs-lookup"><span data-stu-id="38c01-144">**Policy type**: Task</span></span>

    <span data-ttu-id="38c01-145">**정책 범위**: Exchange</span><span class="sxs-lookup"><span data-stu-id="38c01-145">**Policy scope**: Exchange</span></span>

    <span data-ttu-id="38c01-146">**정책 이름**: 새 저널 규칙</span><span class="sxs-lookup"><span data-stu-id="38c01-146">**Policy name**: New Journal Rule</span></span>

    <span data-ttu-id="38c01-147">**승인 유형**: 수동</span><span class="sxs-lookup"><span data-stu-id="38c01-147">**Approval type**: Manual</span></span>

    <span data-ttu-id="38c01-148">**승인 그룹**: 권한 있는 액세스 승인자</span><span class="sxs-lookup"><span data-stu-id="38c01-148">**Approval group**: Privileged Access Approvers</span></span>

6. <span data-ttu-id="38c01-149">**만들기**를 선택한 다음 **닫기를**선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="38c01-149">Select **Create**, and then select **Close**.</span></span> <span data-ttu-id="38c01-150">정책을 완전히 구성 및 사용 하도록 설정 하는 데 몇 분 정도 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="38c01-150">It may take a few minutes for the policy to be fully configured and enabled.</span></span> <span data-ttu-id="38c01-151">다음 단계에서 승인 요구 사항을 테스트 하기 전에 정책을 완전히 사용 하도록 설정할 시간을 허용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="38c01-151">Be sure to allow time for the policy to be fully enabled before testing the approval requirement in the next step.</span></span>

### <a name="test-approval-requirement-for-the-new-journalrule-task-defined-in-a-privileged-access-policy"></a><span data-ttu-id="38c01-152">권한 있는 액세스 정책에 정의 된 New-JournalRule 작업에 대 한 승인 요구 사항 테스트</span><span class="sxs-lookup"><span data-stu-id="38c01-152">Test approval requirement for the New-JournalRule task defined in a privileged access policy</span></span>

1. <span data-ttu-id="38c01-153">로컬 컴퓨터에서 **Microsoft Corporation**  >  테스트 환경에 대 한 전역 관리자 계정을 사용 하 여 microsoft Corporation**microsoft exchange online 원격 powershell** 모듈에서 Exchange online 원격 powershell 모듈을 열고 로그인 합니다.</span><span class="sxs-lookup"><span data-stu-id="38c01-153">On your local computer, open and sign in to the Exchange Online Remote PowerShell Module at **Microsoft Corporation** > **Microsoft Exchange Online Remote PowerShell Module** using an using the Global Admin account for your test environment.</span></span>

2. <span data-ttu-id="38c01-154">Exchange 관리 PowerShell에서 조직에 대 한 새 저널 규칙을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="38c01-154">In Exchange Management PowerShell, create a new Journal rule for your organization:</span></span>

   ```ExchangeManagementPowerShell
   New-JournalRule -Name "JournalRule2" -Recipient user1@<your subscription domain> -JournalEmailAddress user1@<your subscription domain> -Scope Global -Enabled $true
   ```

3. <span data-ttu-id="38c01-155">Exchange 관리 PowerShell에서 "사용 권한 부족" 오류를 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="38c01-155">View the "Insufficient permissions" error in Exchange Management PowerShell:</span></span>

   ```ExchangeManagementPowerShell
   Insufficient permissions. Please raise an elevated access request for this task.
       + CategoryInfo          : NotSpecified: (:) [], LocalizedException
       + FullyQualifiedErrorId : [Server=CY1PR00MB0220,RequestId=7b8c7470-ddd0-4528-a01e-5e20ecc9bd54,TimeStamp=9/19/2018
       7:38:34 PM] [FailureCategory=Cmdlet-LocalizedException] 882BD051
       + PSComputerName        : outlook.office365.com
   ```

### <a name="request-access-to-create-a-new-journal-rule-using-the-new-journalrule-task"></a><span data-ttu-id="38c01-156">New-JournalRule 작업을 사용 하 여 새 저널 규칙을 만들도록 액세스 요청</span><span class="sxs-lookup"><span data-stu-id="38c01-156">Request access to create a new Journal Rule using the New-JournalRule task</span></span>

1. <span data-ttu-id="38c01-157">테스트 환경에 대 한 전역 관리자 계정을 사용 하 여 [Microsoft 365 관리 센터](https://admin.microsoft.com) 에 로그인 합니다.</span><span class="sxs-lookup"><span data-stu-id="38c01-157">Sign in to the [Microsoft 365 admin center](https://admin.microsoft.com) using the Global Admin account for your test environment.</span></span>

2. <span data-ttu-id="38c01-158">관리 센터에서 **설정**  >  **보안 & 개인 정보**  >  **권한이 부여 된 액세스**로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="38c01-158">In the Admin Center, go to **Settings** > **Security & Privacy** > **Privileged access**.</span></span>

3. <span data-ttu-id="38c01-159">**액세스 정책 및 요청 관리를**선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="38c01-159">Select **Manage access policies and requests**.</span></span>

4. <span data-ttu-id="38c01-160">**새 요청**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="38c01-160">Select **New request**.</span></span> <span data-ttu-id="38c01-161">드롭다운 필드에서 조직에 적합 한 값을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="38c01-161">From the drop-down fields, select the appropriate values for your organization:</span></span>

    <span data-ttu-id="38c01-162">**요청 유형**: 작업</span><span class="sxs-lookup"><span data-stu-id="38c01-162">**Request type**: Task</span></span>

    <span data-ttu-id="38c01-163">**요청 범위**: Exchange</span><span class="sxs-lookup"><span data-stu-id="38c01-163">**Request scope**: Exchange</span></span>

    <span data-ttu-id="38c01-164">**요청**: 새 저널 규칙</span><span class="sxs-lookup"><span data-stu-id="38c01-164">**Request for**: New Journal Rule</span></span>

    <span data-ttu-id="38c01-165">**기간 (시간)**: 2</span><span class="sxs-lookup"><span data-stu-id="38c01-165">**Duration (hours)**: 2</span></span>

    <span data-ttu-id="38c01-166">**설명**: 새 저널 규칙을 만드는 권한을 요청 합니다.</span><span class="sxs-lookup"><span data-stu-id="38c01-166">**Comments**: Request permission to create a new Journal Rule</span></span>

5. <span data-ttu-id="38c01-167">**저장**을 선택한 다음 **닫기를**선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="38c01-167">Select **Save**, and then select **Close**.</span></span> <span data-ttu-id="38c01-168">요청은 전자 메일을 통해 승인자 그룹에 전송 됩니다.</span><span class="sxs-lookup"><span data-stu-id="38c01-168">Your request will be sent to the approver's group via email.</span></span>

### <a name="approve-privileged-access-request-for-the-creation-of-a-new-journal-rule"></a><span data-ttu-id="38c01-169">새 저널 규칙 만들기에 대 한 권한 있는 액세스 요청 승인</span><span class="sxs-lookup"><span data-stu-id="38c01-169">Approve privileged access request for the creation of a new Journal Rule</span></span>

1. <span data-ttu-id="38c01-170">테스트 환경의 사용자 3에 대 한 자격 증명 (테스트 환경에서 "권한이 부여 된 액세스 승인자" 보안 그룹의 구성원)을 사용 하 여 [Microsoft 365 관리 센터](https://admin.microsoft.com) 에 로그인 합니다.</span><span class="sxs-lookup"><span data-stu-id="38c01-170">Sign in to the [Microsoft 365 admin center](https://admin.microsoft.com) using the credentials for User 3 in your test environment (member of the "Privileged Access Approvers" security group in your test environment).</span></span>

2. <span data-ttu-id="38c01-171">관리 센터에서 **설정**  >  **보안 & 개인 정보**  >  **권한이 부여 된 액세스**로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="38c01-171">In the Admin Center, go to **Settings** > **Security & Privacy** > **Privileged access**.</span></span>

3. <span data-ttu-id="38c01-172">**액세스 정책 및 요청 관리를**선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="38c01-172">Select **Manage access policies and requests**.</span></span>

4. <span data-ttu-id="38c01-173">대기 중인 요청을 선택한 다음 **승인** 을 선택 하 여 전역 관리자 계정에 대 한 액세스 권한을 부여 하 고 새 저널 규칙을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="38c01-173">Select the pending request, and then select **Approve** to grant access to the Global Admin account to create a new Journal Rule.</span></span> <span data-ttu-id="38c01-174">전역 관리자 계정 (요청 하는 사용자)에 게 승인이 부여 되었음을 알리는 전자 메일 확인 메시지가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="38c01-174">The Global Admin account (the requesting user) will receive an email confirmation that approval was granted.</span></span>

### <a name="test-creating-a-new-journal-rule-with-privileged-access-approved-for-the-new-journalrule-task"></a><span data-ttu-id="38c01-175">New-JournalRule 작업에 대해 승인 된 액세스 권한으로 새 저널 규칙 만들기 테스트</span><span class="sxs-lookup"><span data-stu-id="38c01-175">Test creating a new Journal Rule with privileged access approved for the New-JournalRule task</span></span>

1. <span data-ttu-id="38c01-176">로컬 컴퓨터에서 **Microsoft Corporation**  >  테스트 환경의 전역 관리자 계정을 사용 하 여 microsoft Corporation**microsoft exchange online 원격 powershell** 모듈에서 Exchange online 원격 powershell 모듈을 열고 로그인 합니다.</span><span class="sxs-lookup"><span data-stu-id="38c01-176">On your local computer, open and sign in to the Exchange Online Remote PowerShell Module at **Microsoft Corporation** > **Microsoft Exchange Online Remote PowerShell Module** using the Global Admin account for your test environment.</span></span>

1. <span data-ttu-id="38c01-177">Exchange 관리 PowerShell에서 조직에 대 한 새 저널 규칙을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="38c01-177">In Exchange Management PowerShell, create a new Journal rule for your organization:</span></span>

   ```ExchangeManagementPowerShell
   New-JournalRule -Name "JournalRule2" -Recipient user1@<your subscription domain> -JournalEmailAddress user1@<your subscription domain> -Scope Global -Enabled $true
   ```

1. <span data-ttu-id="38c01-178">Exchange 관리 PowerShell에서 새 저널 규칙을 성공적으로 만들었는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="38c01-178">View that the new Journal Rule was successfully created in Exchange Management PowerShell.</span></span>

## <a name="next-step"></a><span data-ttu-id="38c01-179">다음 단계</span><span class="sxs-lookup"><span data-stu-id="38c01-179">Next step</span></span>

<span data-ttu-id="38c01-180">테스트 환경에서 추가 [정보 보호](m365-enterprise-test-lab-guides.md#information-protection) 기능에 대해 알아봅니다.</span><span class="sxs-lookup"><span data-stu-id="38c01-180">Explore additional [information protection](m365-enterprise-test-lab-guides.md#information-protection) features and capabilities in your test environment.</span></span>

## <a name="see-also"></a><span data-ttu-id="38c01-181">참고 항목</span><span class="sxs-lookup"><span data-stu-id="38c01-181">See also</span></span>

[<span data-ttu-id="38c01-182">엔터프라이증용 Microsoft 365 테스트 랩 가이드</span><span class="sxs-lookup"><span data-stu-id="38c01-182">Microsoft 365 for enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

[<span data-ttu-id="38c01-183">엔터프라이즈용 Microsoft 365 개요</span><span class="sxs-lookup"><span data-stu-id="38c01-183">Microsoft 365 for enterprise overview</span></span>](microsoft-365-overview.md)

[<span data-ttu-id="38c01-184">엔터프라이즈 설명서에 대 한 Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="38c01-184">Microsoft 365 for enterprise documentation</span></span>](https://docs.microsoft.com/microsoft-365-enterprise/)
