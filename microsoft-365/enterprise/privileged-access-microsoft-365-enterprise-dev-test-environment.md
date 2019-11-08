---
title: Microsoft 365 Enterprise 테스트 환경에 대한 권한이 부여된 액세스 관리
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
description: 이 테스트 랩 가이드를 사용 하 여 Microsoft 365 Enterprise Test environment 권한 있는 액세스 관리를 사용 하도록 설정 합니다.
ms.openlocfilehash: f701f3f8f74036966de2c516d662ef77341f4842
ms.sourcegitcommit: b424ea039c5915975f3efce8793bfc8dd2fdf906
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/07/2019
ms.locfileid: "38033613"
---
# <a name="privileged-access-management-for-your-microsoft-365-enterprise-test-environment"></a><span data-ttu-id="ab6e2-103">Microsoft 365 Enterprise 테스트 환경에 대한 권한이 부여된 액세스 관리</span><span class="sxs-lookup"><span data-stu-id="ab6e2-103">Privileged access management for your Microsoft 365 Enterprise test environment</span></span>

<span data-ttu-id="ab6e2-104">이 문서의 지침을 사용 하 여 Microsoft 365 Enterprise 테스트 환경에서 보안을 강화 하도록 권한이 부여 된 액세스 관리를 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="ab6e2-104">With the instructions in this article, you configure privileged access management to increase security in your Microsoft 365 Enterprise test environment.</span></span>

![Microsoft 클라우드의 테스트 랩 가이드](media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png)

> [!TIP]
> <span data-ttu-id="ab6e2-106">[여기](https://aka.ms/m365etlgstack)를 클릭하여 Microsoft 365 Enterprise 테스트 랩 가이드 스택의 모든 문서에 대한 가상 맵을 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ab6e2-106">Click [here](https://aka.ms/m365etlgstack) for a visual map to all the articles in the Microsoft 365 Enterprise Test Lab Guide stack.</span></span>
  
## <a name="phase-1-build-out-your-microsoft-365-enterprise-test-environment"></a><span data-ttu-id="ab6e2-107">1 단계: Microsoft 365 Enterprise 테스트 환경 구축</span><span class="sxs-lookup"><span data-stu-id="ab6e2-107">Phase 1: Build out your Microsoft 365 Enterprise test environment</span></span>

<span data-ttu-id="ab6e2-108">최소 요구 사항에 따라 간단한 방식으로 권한 있는 액세스 관리를 구성 하려는 경우에는 [간단한 기본 구성](lightweight-base-configuration-microsoft-365-enterprise.md)의 지침을 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="ab6e2-108">If you just want to configure privileged access management in a lightweight way with the minimum requirements, follow the instructions in [Lightweight base configuration](lightweight-base-configuration-microsoft-365-enterprise.md).</span></span>
  
<span data-ttu-id="ab6e2-109">시뮬레이트된 엔터프라이즈에서 권한이 부여 된 액세스 관리를 구성 하려면 [통과 인증](pass-through-auth-m365-ent-test-environment.md)의 지침을 따르세요.</span><span class="sxs-lookup"><span data-stu-id="ab6e2-109">If you want to configure privileged access management in a simulated enterprise, follow the instructions in [Pass-through authentication](pass-through-auth-m365-ent-test-environment.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="ab6e2-110">권한 있는 액세스 관리를 테스트 하는 경우에는 AD DS 포리스트에 대 한 인터넷 및 디렉터리 동기화에 연결 된 시뮬레이트된 인트라넷을 포함 하는 시뮬레이트된 엔터프라이즈 테스트 환경이 필요 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="ab6e2-110">Testing privileged access management does not require the simulated enterprise test environment, which includes a simulated intranet connected to the Internet and directory synchronization for an AD DS forest.</span></span> <span data-ttu-id="ab6e2-111">이 옵션은 권한 있는 액세스 관리를 테스트 하 고 일반적인 조직을 나타내는 환경에서 테스트해 볼 수 있도록 여기에서 제공 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ab6e2-111">It is provided here as an option so that you can test privileged access management and experiment with it in an environment that represents a typical organization.</span></span> 

## <a name="phase-2-configure-privileged-access-management"></a><span data-ttu-id="ab6e2-112">2 단계: 권한 있는 액세스 관리 구성</span><span class="sxs-lookup"><span data-stu-id="ab6e2-112">Phase 2: Configure privileged access management</span></span>

<span data-ttu-id="ab6e2-113">이 단계에서는 승인자 그룹을 구성 하 고 Microsoft 365 Enterprise 테스트 환경에 대해 권한이 부여 된 액세스 관리를 사용 하도록 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="ab6e2-113">In this phase, you configure an approvers group and enable privileged access management for your Microsoft 365 Enterprise test environment.</span></span> <span data-ttu-id="ab6e2-114">권한 있는 액세스 관리에 대 한 자세한 내용 및 개요는 [Office 365의 권한이 부여 된 액세스 관리](https://docs.microsoft.com/office365/securitycompliance/privileged-access-management-overview)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="ab6e2-114">For additional details and an overview of privileged access management, see [Privileged access management in Office 365](https://docs.microsoft.com/office365/securitycompliance/privileged-access-management-overview).</span></span>

<span data-ttu-id="ab6e2-115">Office 365 조직에서 권한 있는 액세스를 설정 및 사용 하려면 다음 단계를 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="ab6e2-115">Follow these steps to set up and use privileged access in your Office 365 organization:</span></span>

- [<span data-ttu-id="ab6e2-116">1 단계: 승인자 그룹 만들기</span><span class="sxs-lookup"><span data-stu-id="ab6e2-116">Step 1: Create an approver's group</span></span>](https://docs.microsoft.com/microsoft-365/compliance/privileged-access-management-configuration#step-1-create-an-approvers-group)

    <span data-ttu-id="ab6e2-117">권한 액세스 사용을 시작 하기 전에 권한 상승 및 권한 있는 작업에 대 한 수신 요청 액세스에 대 한 승인 기관을 사용자에 게 결정 합니다.</span><span class="sxs-lookup"><span data-stu-id="ab6e2-117">Before you start using privilege access, determine who will have approval authority for incoming requests for access to elevated and privileged tasks.</span></span> <span data-ttu-id="ab6e2-118">승인자 그룹에 속하는 모든 사용자는 액세스 요청을 승인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ab6e2-118">Any user who is part of the Approvers’ group will be able to approve access requests.</span></span> <span data-ttu-id="ab6e2-119">이 기능은 Office 365에서 메일 사용이 가능한 보안 그룹을 만들어 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ab6e2-119">This is enabled by creating a mail-enabled security group in Office 365.</span></span> <span data-ttu-id="ab6e2-120">테스트 환경에 "권한이 부여 된 액세스 승인자" 라는 새 보안 그룹을 만들고 이전 테스트 랩 가이드 단계에서 만든 "사용자 3"을 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="ab6e2-120">Create a new security group named "Privileged Access Approvers" in your test environment and add the "User 3" previously created in prior test lab guide steps.</span></span>

- [<span data-ttu-id="ab6e2-121">2 단계: 권한 있는 액세스 사용</span><span class="sxs-lookup"><span data-stu-id="ab6e2-121">Step 2: Enable privileged access</span></span>](https://docs.microsoft.com/microsoft-365/compliance/privileged-access-management-configuration#step-2-enable-privileged-access)

    <span data-ttu-id="ab6e2-122">권한 있는 액세스는 Office 365에서 기본 승인자 그룹을 사용 하 고 권한 있는 액세스 관리 액세스 제어에서 제외할 시스템 계정 집합을 포함 하 여 명시적으로 설정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ab6e2-122">Privileged access needs to be explicitly turned on in Office 365 with the default approver group and including a set of system accounts that you’d want to be excluded from the privileged access management access control.</span></span> <span data-ttu-id="ab6e2-123">이 가이드의 3 단계를 시작 하기 전에 Office 365 조직에서 권한이 부여 된 액세스를 사용 하도록 설정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ab6e2-123">Be sure to enable privileged access in your Office 365 organization before starting Phase 3 of this guide.</span></span>

## <a name="phase-3-verify-that-approval-is-required-for-elevated-and-privileged-tasks"></a><span data-ttu-id="ab6e2-124">3 단계: 관리자 권한 및 권한 있는 작업에 대 한 승인이 필요한 지 확인</span><span class="sxs-lookup"><span data-stu-id="ab6e2-124">Phase 3: Verify that approval is required for elevated and privileged tasks</span></span>

<span data-ttu-id="ab6e2-125">이 단계에서는 권한이 부여 된 액세스 정책이 작동 하 고 있는지 확인 하 고 사용자에 게 권한 상승 및 권한이 부여 된 작업을 실행 하기 위한 승인을 받아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ab6e2-125">In this phase, you verify that the privileged access policy is working and users require approval to execute defined elevated and privileged tasks.</span></span>

### <a name="test-ability-to-execute-a-task-not-defined-in-a-privileged-access-policy"></a><span data-ttu-id="ab6e2-126">권한 있는 액세스 정책에 정의 되지 않은 작업을 실행 하는 테스트 기능</span><span class="sxs-lookup"><span data-stu-id="ab6e2-126">Test ability to execute a task NOT defined in a privileged access policy</span></span>

<span data-ttu-id="ab6e2-127">먼저 테스트 환경에서 전역 관리자로 구성 된 사용자의 자격 증명을 사용 하 여 Exchange 관리 PowerShell에 연결한 다음 새 저널 규칙을 만들려고 합니다.</span><span class="sxs-lookup"><span data-stu-id="ab6e2-127">First, connect to Exchange Management PowerShell with the credentials of a user configured as a Global Administrator in your test environment and attempt to create a new Journal rule.</span></span> <span data-ttu-id="ab6e2-128">[Set-journalrule](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance/new-journalrule?view=exchange-ps) 작업은 현재 조직에 대해 권한이 부여 된 액세스 정책에 정의 되어 있지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="ab6e2-128">The [New-JournalRule](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance/new-journalrule?view=exchange-ps) task is not currently defined in a privileged access policy for your organization.</span></span>

1. <span data-ttu-id="ab6e2-129">로컬 컴퓨터에서 테스트 환경의 전역 관리자 계정을 사용 하 여 **microsoft Corporation** > **microsoft exchange online 원격 powershell** 모듈의 Exchange online 원격 powershell 모듈을 열고 로그인 합니다.</span><span class="sxs-lookup"><span data-stu-id="ab6e2-129">On your local computer, open and sign into the the Exchange Online Remote PowerShell Module at **Microsoft Corporation** > **Microsoft Exchange Online Remote PowerShell Module** using the Global Admin account for your test environment.</span></span>

2. <span data-ttu-id="ab6e2-130">Exchange 관리 Powershell에서 조직에 대 한 새 저널 규칙을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="ab6e2-130">In Exchange Management Powershell, create a new Journal rule for your organization:</span></span>

```ExchangeManagementPowerShell
New-JournalRule -Name "JournalRule1" -Recipient joe@contoso.onmicrosoft.com -JournalEmailAddress barbara@adatum.com -Scope Global -Enabled $true
```

4. <span data-ttu-id="ab6e2-131">Exchange 관리 PowerShell에서 새 저널 규칙을 성공적으로 만들었는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="ab6e2-131">View that the new Journal Rule was successfully created in Exchange Management PowerShell.</span></span>

### <a name="create-a-new-privileged-access-policy-for-the-new-journalrule-task"></a><span data-ttu-id="ab6e2-132">새 Set-journalrule 작업에 대 한 새 권한 있는 액세스 정책 만들기</span><span class="sxs-lookup"><span data-stu-id="ab6e2-132">Create a new privileged access policy for the New-JournalRule task</span></span>

> [!NOTE]
> <span data-ttu-id="ab6e2-133">이 가이드의 2 단계에 나와 있는 1 ~ 2 단계를 아직 완료 하지 않은 경우 다음 단계에 따라 승인자 그룹 "권한 액세스 승인자"를 만들고 테스트 환경에서 권한이 부여 된 액세스를 사용 하도록 설정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ab6e2-133">If you haven't already completed the Steps 1 and 2 from Phase 2 of this guide, be sure follow the steps to create an approver's group named "Privilege Access Approvers" and to enable privileged access in your test environment.</span></span>

1. <span data-ttu-id="ab6e2-134">자격 증명을 사용 하 여 [Microsoft 365 관리 센터](https://admin.microsoft.com) 에 로그인 테스트 환경에 대 한 전역 관리자 계정입니다.</span><span class="sxs-lookup"><span data-stu-id="ab6e2-134">Sign into the [Microsoft 365 admin center](https://admin.microsoft.com) using credentials the Global Admin account for your test environment.</span></span>

2. <span data-ttu-id="ab6e2-135">관리 센터에서 **설정** > **보안 & 개인 정보** > **권한이 부여 된 액세스**로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="ab6e2-135">In the Admin Center, go to **Settings** > **Security & Privacy** > **Privileged access**.</span></span>

3. <span data-ttu-id="ab6e2-136">**액세스 정책 및 요청 관리를**선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="ab6e2-136">Select **Manage access policies and requests**.</span></span>

4. <span data-ttu-id="ab6e2-137">정책 **구성을** 선택 하 고 **정책 추가**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="ab6e2-137">Select **Configure policies** and select **Add a policy**.</span></span>

5. <span data-ttu-id="ab6e2-138">드롭다운 필드에서 다음 값을 선택 하거나 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="ab6e2-138">From the drop-down fields, select or enter the following values:</span></span>

    <span data-ttu-id="ab6e2-139">**정책 유형**: 작업</span><span class="sxs-lookup"><span data-stu-id="ab6e2-139">**Policy type**: Task</span></span>

    <span data-ttu-id="ab6e2-140">**정책 범위**: Exchange</span><span class="sxs-lookup"><span data-stu-id="ab6e2-140">**Policy scope**: Exchange</span></span>

    <span data-ttu-id="ab6e2-141">**정책 이름**: 새 저널 규칙</span><span class="sxs-lookup"><span data-stu-id="ab6e2-141">**Policy name**: New Journal Rule</span></span>

    <span data-ttu-id="ab6e2-142">**승인 유형**: 수동</span><span class="sxs-lookup"><span data-stu-id="ab6e2-142">**Approval type**: Manual</span></span>

    <span data-ttu-id="ab6e2-143">**승인 그룹**: 권한 있는 액세스 승인자</span><span class="sxs-lookup"><span data-stu-id="ab6e2-143">**Approval group**: Privileged Access Approvers</span></span>

6. <span data-ttu-id="ab6e2-144">**만들기** 를 선택한 다음 **닫기를**선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="ab6e2-144">Select **Create** and then **Close**.</span></span> <span data-ttu-id="ab6e2-145">정책을 완전히 구성 및 사용 하도록 설정 하는 데 몇 분 정도 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ab6e2-145">It may take a few minutes for the policy to be fully configured and enabled.</span></span> <span data-ttu-id="ab6e2-146">다음 단계에서 승인 요구 사항을 테스트 하기 전에 정책을 완전히 사용 하도록 설정할 시간을 허용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ab6e2-146">Be sure to allow time for the policy to be fully enabled before testing the approval requirement in the next step.</span></span>

### <a name="test-approval-requirement-for-the-new-journalrule-task-defined-in-a-privileged-access-policy"></a><span data-ttu-id="ab6e2-147">권한 있는 액세스 정책에 정의 된 Set-journalrule 작업에 대 한 승인 요구 사항 테스트</span><span class="sxs-lookup"><span data-stu-id="ab6e2-147">Test approval requirement for the New-JournalRule task defined in a privileged access policy</span></span>

1. <span data-ttu-id="ab6e2-148">로컬 컴퓨터에서 테스트 환경에 대 한 전역 관리자 계정을 사용 하 여 **microsoft Corporation** > **microsoft exchange online 원격 powershell 모듈** 의 Exchange online 원격 powershell 모듈을 열고 로그인 합니다.</span><span class="sxs-lookup"><span data-stu-id="ab6e2-148">On your local computer, open and sign into the the Exchange Online Remote PowerShell Module at **Microsoft Corporation** > **Microsoft Exchange Online Remote PowerShell Module** using an using the Global Admin account for your test environment.</span></span>

2. <span data-ttu-id="ab6e2-149">Exchange 관리 Powershell에서 조직에 대 한 새 저널 규칙을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="ab6e2-149">In Exchange Management Powershell, create a new Journal rule for your organization:</span></span>

```ExchangeManagementPowerShell
New-JournalRule -Name "JournalRule2" -Recipient user1@<your subscription domain> -JournalEmailAddress user1@<your subscription domain> -Scope Global -Enabled $true
```

3. <span data-ttu-id="ab6e2-150">Exchange 관리 PowerShell에서 "Insuffient 사용 권한" 오류 보기:</span><span class="sxs-lookup"><span data-stu-id="ab6e2-150">View "Insuffient permissions" error in Exchange Management PowerShell:</span></span>

```ExchangeManagementPowerShell
Insufficient permissions. Please raise an elevated access request for this task.
    + CategoryInfo          : NotSpecified: (:) [], LocalizedException
    + FullyQualifiedErrorId : [Server=CY1PR00MB0220,RequestId=7b8c7470-ddd0-4528-a01e-5e20ecc9bd54,TimeStamp=9/19/2018
    7:38:34 PM] [FailureCategory=Cmdlet-LocalizedException] 882BD051
    + PSComputerName        : outlook.office365.com
```

### <a name="request-access-to-create-a-new-journal-rule-using-the-new-journalrule-task"></a><span data-ttu-id="ab6e2-151">Set-journalrule 작업을 사용 하 여 새 저널 규칙을 만들도록 액세스 요청</span><span class="sxs-lookup"><span data-stu-id="ab6e2-151">Request access to create a new Journal Rule using the New-JournalRule task</span></span>

1. <span data-ttu-id="ab6e2-152">테스트 환경에 대 한 전역 관리자 계정을 사용 하 여 [Microsoft 365 관리 센터](https://admin.microsoft.com) 에 로그인 합니다.</span><span class="sxs-lookup"><span data-stu-id="ab6e2-152">Sign into the [Microsoft 365 admin center](https://admin.microsoft.com) using the Global Admin account for your test environment.</span></span>

2. <span data-ttu-id="ab6e2-153">관리 센터에서 **설정** > **보안 & 개인 정보** > **권한이 부여 된 액세스**로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="ab6e2-153">In the Admin Center, go to **Settings** > **Security & Privacy** > **Privileged access**.</span></span>

3. <span data-ttu-id="ab6e2-154">**액세스 정책 및 요청 관리를**선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="ab6e2-154">Select **Manage access policies and requests**.</span></span>

4. <span data-ttu-id="ab6e2-155">**새 요청**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="ab6e2-155">Select **New request**.</span></span> <span data-ttu-id="ab6e2-156">드롭다운 필드에서 조직에 적합 한 값을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="ab6e2-156">From the drop-down fields, select the appropriate values for your organization:</span></span>

    <span data-ttu-id="ab6e2-157">**요청 유형**: 작업</span><span class="sxs-lookup"><span data-stu-id="ab6e2-157">**Request type**: Task</span></span>

    <span data-ttu-id="ab6e2-158">**요청 범위**: Exchange</span><span class="sxs-lookup"><span data-stu-id="ab6e2-158">**Request scope**: Exchange</span></span>

    <span data-ttu-id="ab6e2-159">**요청**: 새 저널 규칙</span><span class="sxs-lookup"><span data-stu-id="ab6e2-159">**Request for**: New Journal Rule</span></span>

    <span data-ttu-id="ab6e2-160">**기간 (시간)**: 2</span><span class="sxs-lookup"><span data-stu-id="ab6e2-160">**Duration (hours)**: 2</span></span>

    <span data-ttu-id="ab6e2-161">**설명**: 새 저널 규칙을 만드는 권한을 요청 합니다.</span><span class="sxs-lookup"><span data-stu-id="ab6e2-161">**Comments**: Request permission to create a new Journal Rule</span></span>

5. <span data-ttu-id="ab6e2-162">**저장** 을 선택한 다음 **닫기를**선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="ab6e2-162">Select **Save** and then **Close**.</span></span> <span data-ttu-id="ab6e2-163">요청은 전자 메일을 통해 승인자 그룹에 전송 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ab6e2-163">Your request will be sent to the approver's group via email.</span></span>

### <a name="approve-privileged-access-request-for-the-creation-of-a-new-journal-rule"></a><span data-ttu-id="ab6e2-164">새 저널 규칙 만들기에 대 한 권한 있는 액세스 요청 승인</span><span class="sxs-lookup"><span data-stu-id="ab6e2-164">Approve privileged access request for the creation of a new Journal Rule</span></span>

1. <span data-ttu-id="ab6e2-165">테스트 환경의 사용자 3에 대 한 자격 증명 (테스트 환경에서 "권한이 부여 된 액세스 승인자" 보안 그룹의 구성원)을 사용 하 여 [Microsoft 365 관리 센터](https://admin.microsoft.com) 에 로그인 합니다.</span><span class="sxs-lookup"><span data-stu-id="ab6e2-165">Sign into the [Microsoft 365 admin center](https://admin.microsoft.com) using the credentials for User 3 in your test environment (member of the "Privileged Access Approvers" security group in your test environment).</span></span>

2. <span data-ttu-id="ab6e2-166">관리 센터에서 **설정** > **보안 & 개인 정보** > **권한이 부여 된 액세스**로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="ab6e2-166">In the Admin Center, go to **Settings** > **Security & Privacy** > **Privileged access**.</span></span>

3. <span data-ttu-id="ab6e2-167">**액세스 정책 및 요청 관리를**선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="ab6e2-167">Select **Manage access policies and requests**.</span></span>

4. <span data-ttu-id="ab6e2-168">대기 중인 요청을 선택 하 고 **승인을** 선택 하 여 새 저널 규칙을 만들 전역 관리자 계정에 대 한 액세스 권한을 부여 합니다.</span><span class="sxs-lookup"><span data-stu-id="ab6e2-168">Select the pending request and select **Approve** to grant access to the Global Admin account to create a new Journal Rule.</span></span> <span data-ttu-id="ab6e2-169">승인이 부여 되었음을 확인 하는 알림 전자 메일은 전역 관리자 계정 (요청 사용자)으로 전송 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ab6e2-169">An notification email confirming that approval has been granted will be sent to the Global Admin account (the requesting user).</span></span>  

### <a name="test-creating-a-new-journal-rule-with-privileged-access-approved-for-the-new-journalrule-task"></a><span data-ttu-id="ab6e2-170">Set-journalrule 작업에 대해 승인 된 액세스 권한을 사용 하 여 새 저널 규칙 만들기 테스트</span><span class="sxs-lookup"><span data-stu-id="ab6e2-170">Test creating a new Journal Rule with privileged access approved for the New-JournalRule task</span></span>

1. <span data-ttu-id="ab6e2-171">로컬 컴퓨터에서 테스트 환경의 전역 관리자 계정을 사용 하 여 **microsoft Corporation** > **microsoft exchange online 원격 powershell** 모듈의 Exchange online 원격 powershell 모듈을 열고 로그인 합니다.</span><span class="sxs-lookup"><span data-stu-id="ab6e2-171">On your local computer, open and sign into the the Exchange Online Remote PowerShell Module at **Microsoft Corporation** > **Microsoft Exchange Online Remote PowerShell Module** using the Global Admin account for your test environment.</span></span>

2. <span data-ttu-id="ab6e2-172">Exchange 관리 Powershell에서 조직에 대 한 새 저널 규칙을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="ab6e2-172">In Exchange Management Powershell, create a new Journal rule for your organization:</span></span>

```ExchangeManagementPowerShell
New-JournalRule -Name "JournalRule2" -Recipient user1@<your subscription domain> -JournalEmailAddress user1@<your subscription domain> -Scope Global -Enabled $true
```

3. <span data-ttu-id="ab6e2-173">Exchange 관리 PowerShell에서 새 저널 규칙을 성공적으로 만들었는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="ab6e2-173">View that the new Journal Rule was successfully created in Exchange Management PowerShell.</span></span>

## <a name="next-step"></a><span data-ttu-id="ab6e2-174">다음 단계</span><span class="sxs-lookup"><span data-stu-id="ab6e2-174">Next step</span></span>

<span data-ttu-id="ab6e2-175">테스트 환경에서 추가 [정보 보호](m365-enterprise-test-lab-guides.md#information-protection) 기능에 대해 알아봅니다.</span><span class="sxs-lookup"><span data-stu-id="ab6e2-175">Explore additional [information protection](m365-enterprise-test-lab-guides.md#information-protection) features and capabilities in your test environment.</span></span>

## <a name="see-also"></a><span data-ttu-id="ab6e2-176">참고 항목</span><span class="sxs-lookup"><span data-stu-id="ab6e2-176">See also</span></span>

[<span data-ttu-id="ab6e2-177">Microsoft 365 Enterprise 테스트 랩 가이드</span><span class="sxs-lookup"><span data-stu-id="ab6e2-177">Microsoft 365 Enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

[<span data-ttu-id="ab6e2-178">Microsoft 365 Enterprise 배포</span><span class="sxs-lookup"><span data-stu-id="ab6e2-178">Deploy Microsoft 365 Enterprise</span></span>](deploy-microsoft-365-enterprise.md)

[<span data-ttu-id="ab6e2-179">Microsoft 365 Enterprise 설명서</span><span class="sxs-lookup"><span data-stu-id="ab6e2-179">Microsoft 365 Enterprise documentation</span></span>](https://docs.microsoft.com/microsoft-365-enterprise/)