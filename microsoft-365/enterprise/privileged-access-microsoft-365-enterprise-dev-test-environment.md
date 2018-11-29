---
title: Microsoft 365 Enterprise 테스트 환경에 대한 권한이 부여된 액세스 관리
ms.author: robmazz
author: robmazz
manager: laurawi
ms.date: 09/21/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection: Ent_O365
ms.custom: Ent_TLGs
description: Microsoft 365 Enterprise 테스트 환경을 권한이 부여 된 액세스 관리를 사용 하도록 설정 하려면이 테스트 랩 가이드를 사용 합니다.
ms.openlocfilehash: 5f1a416a12171504af110ec62b9a7882143263e6
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/28/2018
ms.locfileid: "26869727"
---
# <a name="privileged-access-management-for-your-microsoft-365-enterprise-test-environment"></a><span data-ttu-id="4b22e-103">Microsoft 365 Enterprise 테스트 환경에 대한 권한이 부여된 액세스 관리</span><span class="sxs-lookup"><span data-stu-id="4b22e-103">Privileged access management for your Microsoft 365 Enterprise test environment</span></span>

<span data-ttu-id="4b22e-104">이 문서의 지침을과 함께 Microsoft 365 기업 테스트 환경에서 보안을 강화 하기 권한이 부여 된 액세스 관리를 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="4b22e-104">With the instructions in this article, you configure privileged access management to increase security in your Microsoft 365 Enterprise test environment.</span></span>

![Microsoft 클라우드의 테스트 랩 가이드](media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png)

> [!TIP]
> <span data-ttu-id="4b22e-106">[여기](https://aka.ms/m365etlgstack)를 클릭하여 Microsoft 365 Enterprise 테스트 랩 가이드 스택의 모든 문서에 대한 가상 맵을 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4b22e-106">Click [here](https://aka.ms/m365etlgstack) for a visual map to all the articles in the Microsoft 365 Enterprise Test Lab Guide stack.</span></span>
  
## <a name="phase-1-build-out-your-microsoft-365-enterprise-test-environment"></a><span data-ttu-id="4b22e-107">1 단계: Microsoft 365 Enterprise 테스트 환경을 구축합니다</span><span class="sxs-lookup"><span data-stu-id="4b22e-107">Phase 1: Build out your Microsoft 365 Enterprise test environment</span></span>

<span data-ttu-id="4b22e-108">최소 요구 사항을 경량 방식으로 액세스 권한을된 관리를 구성 하려면 [경량 기본 구성](lightweight-base-configuration-microsoft-365-enterprise.md)의 지시를 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="4b22e-108">If you just want to configure privileged access management in a lightweight way with the minimum requirements, follow the instructions in [Lightweight base configuration](lightweight-base-configuration-microsoft-365-enterprise.md).</span></span>
  
<span data-ttu-id="4b22e-109">시뮬레이션 된 엔터프라이즈에서 권한이 부여 된 액세스 관리를 구성 하려는 경우 [통과 인증](pass-through-auth-m365-ent-test-environment.md)에 대 한 지침을 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="4b22e-109">If you want to configure privileged access management in a simulated enterprise, follow the instructions in [Pass-through authentication](pass-through-auth-m365-ent-test-environment.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="4b22e-p101">권한이 부여 된 액세스 관리를 테스트 하지 않아도 인터넷에 연결 하는 시뮬레이션 된 인트라넷을 포함 하는 시뮬레이션 된 엔터프라이즈 테스트 환경 및 Windows Server AD 포리스트에 대 한 디렉터리 동기화 합니다. 여기에 제공 하는 옵션으로 테스트할 수 있도록 권한 관리에 액세스 하 고 일반적인 조직을 대표 하는 환경에서 사용해 합니다.</span><span class="sxs-lookup"><span data-stu-id="4b22e-p101">Testing privileged access management does not require the simulated enterprise test environment, which includes a simulated intranet connected to the Internet and directory synchronization for a Windows Server AD forest. It is provided here as an option so that you can test privileged access management and experiment with it in an environment that represents a typical organization.</span></span> 

## <a name="phase-2-configure-privileged-access-management"></a><span data-ttu-id="4b22e-112">2 단계: 액세스 권한을된 관리 구성</span><span class="sxs-lookup"><span data-stu-id="4b22e-112">Phase 2: Configure privileged access management</span></span>

<span data-ttu-id="4b22e-p102">이 단계에서 승인자 그룹을 구성 및 Microsoft 365 기업 테스트 환경에 대 한 액세스 권한을된 관리를 사용 하도록 설정 합니다. 추가 세부 정보 및 권한 개요에 대 한 관리 액세스 [Office 365에서 권한이 부여 된 액세스 관리](https://docs.microsoft.com/office365/securitycompliance/privileged-access-management-overview)를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="4b22e-p102">In this phase, you configure an approvers group and enable privileged access management for your Microsoft 365 Enterprise test environment. For additional details and an overview of privileged access management, see [Privileged access management in Office 365](https://docs.microsoft.com/office365/securitycompliance/privileged-access-management-overview).</span></span>

<span data-ttu-id="4b22e-115">설정 하 고 Office 365 조직에서 액세스 권한을된 사용 하려면 다음이 단계를 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="4b22e-115">Follow these steps to set up and use privileged access in your Office 365 organization:</span></span>

- [<span data-ttu-id="4b22e-116">1 단계: 승인자의 그룹 만들기</span><span class="sxs-lookup"><span data-stu-id="4b22e-116">Step 1: Create an approver's group</span></span>](https://docs.microsoft.com/office365/securitycompliance/privileged-access-management-configuration#step-1---create-an-approvers-group)

    <span data-ttu-id="4b22e-p103">권한 액세스를 사용 하 여를 시작 하기 전에 관리자 권한 및 권한 있는 작업에 대 한 액세스에 대 한 수신 요청에 대 한 승인 권한을 갖고 결정 합니다. 승인자 그룹의 구성원 인 모든 사용자 액세스 요청 승인 됩니다. Office 365의 메일 사용이 가능한 보안 그룹을 만들어 사용 하도록 설정 됩니다. 테스트 환경에서 "승인자가 액세스 권한이 부여 된" 이라는 새 보안 그룹을 만들고 추가 "3" 이전에 이전 테스트 랩 가이드 단계에서 만든 사용자입니다.</span><span class="sxs-lookup"><span data-stu-id="4b22e-p103">Before you start using privilege access, determine who will have approval authority for incoming requests for access to elevated and privileged tasks. Any user who is part of the Approvers’ group will be able to approve access requests. This is enabled by creating a mail-enabled security group in Office 365. Create a new security group named "Privileged Access Approvers" in your test environment and add the "User 3" previously created in prior test lab guide steps.</span></span>

- [<span data-ttu-id="4b22e-121">2 단계: 사용 권한이 부여 된 액세스</span><span class="sxs-lookup"><span data-stu-id="4b22e-121">Step 2: Enable privileged access</span></span>](https://docs.microsoft.com/office365/securitycompliance/privileged-access-management-configuration#step-2---enable-privileged-access)

    <span data-ttu-id="4b22e-p104">액세스 권한을된 명시적으로 켜져 있어야 Office 365의 기본 승인자 그룹 및 액세스 권한을된 관리 액세스 제어에서 제외 하려는 시스템 계정 집합을 포함 해야 합니다. 이 가이드의 3 단계를 시작 하기 전에 Office 365 조직에 대 한 액세스 권한을된 사용 하도록 설정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4b22e-p104">Privileged access needs to be explicitly turned on in Office 365 with the default approver group and including a set of system accounts that you’d want to be excluded from the privileged access management access control. Be sure to enable privileged access in your Office 365 organization before starting Phase 3 of this guide.</span></span>

## <a name="phase-3-verify-that-approval-is-required-for-elevated-and-privileged-tasks"></a><span data-ttu-id="4b22e-124">3 단계: 승인 관리자 권한 및 권한 있는 작업에 대 한 필수 인지 확인</span><span class="sxs-lookup"><span data-stu-id="4b22e-124">Phase 3: Verify that approval is required for elevated and privileged tasks</span></span>
<span data-ttu-id="4b22e-125">이 단계에서 권한이 부여 된 액세스 정책이 작동 하 고 사용자가 정의 된 관리자 권한 및 권한 있는 작업을 실행에 대 한 승인 필요를 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="4b22e-125">In this phase, you verify that the privileged access policy is working and users require approval to execute defined elevated and privileged tasks.</span></span>

### <a name="test-ability-to-execute-a-task-not-defined-in-a-privileged-access-policy"></a><span data-ttu-id="4b22e-126">권한이 부여 된 액세스 정책에 정의 되지 않은 작업을 실행할 수 있는 기능을 테스트 합니다.</span><span class="sxs-lookup"><span data-stu-id="4b22e-126">Test ability to execute a task NOT defined in a privileged access policy</span></span>

<span data-ttu-id="4b22e-p105">먼저, 테스트 환경에서 전역 관리자 권한으로 구성 된 사용자의 자격 증명을 가진 Exchange Management PowerShell에 연결 하 고 새 저널 규칙을 생성 하려고 합니다. [New-journalrule](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance/new-journalrule?view=exchange-ps) 작업 현재 조직에 대 한 액세스 권한을된 정책에 정의 되지 않았습니다.</span><span class="sxs-lookup"><span data-stu-id="4b22e-p105">First, connect to Exchange Management PowerShell with the credentials of a user configured as a Global Administrator in your test environment and attempt to create a new Journal rule. The [New-JournalRule](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance/new-journalrule?view=exchange-ps) task is not currently defined in a privileged access policy for your organization.</span></span>

1. <span data-ttu-id="4b22e-129">로컬 컴퓨터에서 열고에 로그인은 Exchange Online 원격 PowerShell 모듈 **Microsoft Corporation**에서 > 전역 관리자를 사용 하 여**Microsoft Exchange Online 원격 PowerShell 모듈** 테스트 환경에 대 한 계정입니다.</span><span class="sxs-lookup"><span data-stu-id="4b22e-129">On your local computer, open and sign into the the Exchange Online Remote PowerShell Module at **Microsoft Corporation** > **Microsoft Exchange Online Remote PowerShell Module** using the Global Admin account for your test environment.</span></span>

2. <span data-ttu-id="4b22e-130">Exchange 관리 Powershell에서 조직에 대 한 새 저널 규칙을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="4b22e-130">In Exchange Management Powershell, create a new Journal rule for your organization:</span></span>

```
New-JournalRule -Name "JournalRule1" -Recipient joe@contoso.onmicrosoft.com -JournalEmailAddress barbara@adatum.com -Scope Global -Enabled $true
```
4. <span data-ttu-id="4b22e-131">새 저널 규칙이 성공적으로 만들어졌는지 Exchange Management PowerShell 보기입니다.</span><span class="sxs-lookup"><span data-stu-id="4b22e-131">View that the new Journal Rule was successfully created in Exchange Management PowerShell.</span></span>

### <a name="create-a-new-privileged-access-policy-for-the-new-journalrule-task"></a><span data-ttu-id="4b22e-132">New-journalrule 작업에 대 한 새 권한이 부여 된 액세스 정책 만들기</span><span class="sxs-lookup"><span data-stu-id="4b22e-132">Create a new privileged access policy for the New-JournalRule task</span></span>

> [!NOTE]
> <span data-ttu-id="4b22e-133">단계 1과 2이이 가이드의 2 단계에서에서 아직 완료 되지 않은, 있는지 팔 로우 테스트 환경에 대 한 액세스 권한을된 사용 하도록 설정 하 고 "권한 액세스 승인자" 라는 승인자의 그룹을 만드는 단계를 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4b22e-133">If you haven't already completed the Steps 1 and 2 from Phase 2 of this guide, be sure follow the steps to create an approver's group named "Privilege Access Approvers" and to enable privileged access in your test environment.</span></span>

1. <span data-ttu-id="4b22e-134">테스트 환경에 대 한 전역 관리자 계정 자격 증명을 사용 하 여 [Microsoft 365 관리 센터](https://portal.office.com) 에 로그인 합니다.</span><span class="sxs-lookup"><span data-stu-id="4b22e-134">Sign into the [Microsoft 365 Admin Center](https://portal.office.com) using credentials the Global Admin account for your test environment.</span></span>

2. <span data-ttu-id="4b22e-135">관리 센터에서 **설정**으로 이동 > **보안 및 개인정보** > **권한이 부여 된 액세스**합니다.</span><span class="sxs-lookup"><span data-stu-id="4b22e-135">In the Admin Center, go to **Settings** > **Security & Privacy** > **Privileged access**.</span></span>

3. <span data-ttu-id="4b22e-136">**관리 액세스 정책 및 요청을**선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="4b22e-136">Select **Manage access policies and requests**.</span></span>

4. <span data-ttu-id="4b22e-137">**정책을 구성을** 선택 하 고 **정책 추가**선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="4b22e-137">Select **Configure policies** and select **Add a policy**.</span></span>

5. <span data-ttu-id="4b22e-138">드롭다운 필드에서 선택 하거나 다음 값을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="4b22e-138">From the drop-down fields, select or enter the following values:</span></span>
    
    <span data-ttu-id="4b22e-139">**정책 유형**: 작업</span><span class="sxs-lookup"><span data-stu-id="4b22e-139">**Policy type**: Task</span></span>

    <span data-ttu-id="4b22e-140">**정책 범위**: Exchange</span><span class="sxs-lookup"><span data-stu-id="4b22e-140">**Policy scope**: Exchange</span></span>

    <span data-ttu-id="4b22e-141">**정책 이름**: 새 저널 규칙</span><span class="sxs-lookup"><span data-stu-id="4b22e-141">**Policy name**: New Journal Rule</span></span>

    <span data-ttu-id="4b22e-142">**승인 유형**: manual (영문)</span><span class="sxs-lookup"><span data-stu-id="4b22e-142">**Approval type**: Manual</span></span>

    <span data-ttu-id="4b22e-143">**승인 그룹**: 권한이 부여 된 액세스 승인자</span><span class="sxs-lookup"><span data-stu-id="4b22e-143">**Approval group**: Privileged Access Approvers</span></span>

6. <span data-ttu-id="4b22e-p106">\*\*만들고 다음 \*\*닫기\*\*\*\* 를 선택 합니다. 완벽 하 게 구성 하 고 사용을 정책에 대 한 몇 분정도 걸릴 수 있습니다. 다음 단계에서 승인 요구 사항을 테스트 하기 전에 완벽 하 게 사용할 수 정책에 대 한 시간을 허용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4b22e-p106">Select **Create** and then **Close**. It may take a few minutes for the policy to be fully configured and enabled. Be sure to allow time for the policy to be fully enabled before testing the approval requirement in the next step.</span></span>

### <a name="test-approval-requirement-for-the-new-journalrule-task-defined-in-a-privileged-access-policy"></a><span data-ttu-id="4b22e-147">권한이 부여 된 액세스 정책에 정의 된 New-journalrule 작업에 대 한 승인 요구 사항 테스트</span><span class="sxs-lookup"><span data-stu-id="4b22e-147">Test approval requirement for the New-JournalRule task defined in a privileged access policy</span></span>

1. <span data-ttu-id="4b22e-148">로컬 컴퓨터에서 열고에 로그인은 Exchange Online 원격 PowerShell 모듈 **Microsoft Corporation**에서 > **Microsoft Exchange Online 원격 PowerShell 모듈** 을 사용 하 여 전역 관리자를 사용 하 여 테스트를 위한 계정 환경입니다.</span><span class="sxs-lookup"><span data-stu-id="4b22e-148">On your local computer, open and sign into the the Exchange Online Remote PowerShell Module at **Microsoft Corporation** > **Microsoft Exchange Online Remote PowerShell Module** using an using the Global Admin account for your test environment.</span></span>

2. <span data-ttu-id="4b22e-149">Exchange 관리 Powershell에서 조직에 대 한 새 저널 규칙을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="4b22e-149">In Exchange Management Powershell, create a new Journal rule for your organization:</span></span>

```
New-JournalRule -Name "JournalRule2" -Recipient user1@<your subscription domain> -JournalEmailAddress user1@<your subscription domain> -Scope Global -Enabled $true
```
3. <span data-ttu-id="4b22e-150">Exchange 관리 PowerShell의 "권한 부족" 오류를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="4b22e-150">View "Insuffient permissions" error in Exchange Management PowerShell:</span></span>

```
Insufficient permissions. Please raise an elevated access request for this task.
    + CategoryInfo          : NotSpecified: (:) [], LocalizedException
    + FullyQualifiedErrorId : [Server=CY1PR00MB0220,RequestId=7b8c7470-ddd0-4528-a01e-5e20ecc9bd54,TimeStamp=9/19/2018
    7:38:34 PM] [FailureCategory=Cmdlet-LocalizedException] 882BD051
    + PSComputerName        : outlook.office365.com
```

### <a name="request-access-to-create-a-new-journal-rule-using-the-new-journalrule-task"></a><span data-ttu-id="4b22e-151">New-journalrule 작업을 사용 하 여 새 저널 규칙 만들기에 대 한 액세스를 요청 합니다.</span><span class="sxs-lookup"><span data-stu-id="4b22e-151">Request access to create a new Journal Rule using the New-JournalRule task</span></span>

1. <span data-ttu-id="4b22e-152">테스트 환경에 대 한 전역 관리자 계정을 사용 하 여 [Microsoft 365 관리 센터](https://portal.office.com) 에 로그인 합니다.</span><span class="sxs-lookup"><span data-stu-id="4b22e-152">Sign into the [Microsoft 365 Admin Center](https://portal.office.com) using the Global Admin account for your test environment.</span></span>

2. <span data-ttu-id="4b22e-153">관리 센터에서 **설정**으로 이동 > **보안 및 개인정보** > **권한이 부여 된 액세스**합니다.</span><span class="sxs-lookup"><span data-stu-id="4b22e-153">In the Admin Center, go to **Settings** > **Security & Privacy** > **Privileged access**.</span></span>

3. <span data-ttu-id="4b22e-154">**관리 액세스 정책 및 요청을**선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="4b22e-154">Select **Manage access policies and requests**.</span></span>

4. <span data-ttu-id="4b22e-p107">**새 요청**을 선택 합니다. 드롭다운 필드에서 조직에 대 한 적절 한 값을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="4b22e-p107">Select **New request**. From the drop-down fields, select the appropriate values for your organization:</span></span>

    <span data-ttu-id="4b22e-157">**요청 유형**: 작업</span><span class="sxs-lookup"><span data-stu-id="4b22e-157">**Request type**: Task</span></span>

    <span data-ttu-id="4b22e-158">**범위 요청**: Exchange</span><span class="sxs-lookup"><span data-stu-id="4b22e-158">**Request scope**: Exchange</span></span>

    <span data-ttu-id="4b22e-159">**에 대 한 요청**: 새 저널 규칙</span><span class="sxs-lookup"><span data-stu-id="4b22e-159">**Request for**: New Journal Rule</span></span>

    <span data-ttu-id="4b22e-160">**기간 (시간)**: 2</span><span class="sxs-lookup"><span data-stu-id="4b22e-160">**Duration (hours)**: 2</span></span>

    <span data-ttu-id="4b22e-161">**설명**: 새 저널 규칙을 만들 수 있는 사용 권한 요청</span><span class="sxs-lookup"><span data-stu-id="4b22e-161">**Comments**: Request permission to create a new Journal Rule</span></span>

5. <span data-ttu-id="4b22e-p108">**저장** 한 다음 **닫기**를 선택 합니다. 전자 메일을 통해 승인자의 그룹에 사용자의 요청을 전송 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4b22e-p108">Select **Save** and then **Close**. Your request will be sent to the approver's group via email.</span></span>

### <a name="approve-privileged-access-request-for-the-creation-of-a-new-journal-rule"></a><span data-ttu-id="4b22e-164">새 저널 규칙을 만들기에 대 한 액세스 권한을된 요청을 승인</span><span class="sxs-lookup"><span data-stu-id="4b22e-164">Approve privileged access request for the creation of a new Journal Rule</span></span>

1. <span data-ttu-id="4b22e-165">사용자 3에 대 한 자격 증명을 사용 하 여 테스트 환경 (테스트 환경에서 "승인자가 액세스 권한이 있는" 보안 그룹의 구성원)에서 [Microsoft 365 관리 센터](https://portal.office.com) 에 로그인 합니다.</span><span class="sxs-lookup"><span data-stu-id="4b22e-165">Sign into the [Microsoft 365 Admin Center](https://portal.office.com) using the credentials for User 3 in your test environment (member of the "Privileged Access Approvers" security group in your test environment).</span></span>

2. <span data-ttu-id="4b22e-166">관리 센터에서 **설정**으로 이동 > **보안 및 개인정보** > **권한이 부여 된 액세스**합니다.</span><span class="sxs-lookup"><span data-stu-id="4b22e-166">In the Admin Center, go to **Settings** > **Security & Privacy** > **Privileged access**.</span></span>

3. <span data-ttu-id="4b22e-167">**관리 액세스 정책 및 요청을**선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="4b22e-167">Select **Manage access policies and requests**.</span></span>

4. <span data-ttu-id="4b22e-p109">대기 중인 요청을 선택 하 고 **승인** 새 저널 규칙을 만들려면 전역 관리자 계정에 대 한 액세스 권한을 부여 하려면 선택 합니다. 전역 관리자 계정 (요청 하는 사용자)에 승인 부여 했는지 확인 알림 전자 메일을 전송 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4b22e-p109">Select the pending request and select **Approve** to grant access to the Global Admin account to create a new Journal Rule. An notification email confirming that approval has been granted will be sent to the Global Admin account (the requesting user).</span></span>  

### <a name="test-creating-a-new-journal-rule-with-privileged-access-approved-for-the-new-journalrule-task"></a><span data-ttu-id="4b22e-170">테스트 New-journalrule 작업에 대 한 승인 액세스 권한이 있는 새 저널 규칙 만들기 (영문)</span><span class="sxs-lookup"><span data-stu-id="4b22e-170">Test creating a new Journal Rule with privileged access approved for the New-JournalRule task</span></span>

1. <span data-ttu-id="4b22e-171">로컬 컴퓨터에서 열고에 로그인은 Exchange Online 원격 PowerShell 모듈 **Microsoft Corporation**에서 > 전역 관리자를 사용 하 여**Microsoft Exchange Online 원격 PowerShell 모듈** 테스트 환경에 대 한 계정입니다.</span><span class="sxs-lookup"><span data-stu-id="4b22e-171">On your local computer, open and sign into the the Exchange Online Remote PowerShell Module at **Microsoft Corporation** > **Microsoft Exchange Online Remote PowerShell Module** using the Global Admin account for your test environment.</span></span>

2. <span data-ttu-id="4b22e-172">Exchange 관리 Powershell에서 조직에 대 한 새 저널 규칙을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="4b22e-172">In Exchange Management Powershell, create a new Journal rule for your organization:</span></span>

```
New-JournalRule -Name "JournalRule2" -Recipient user1@<your subscription domain> -JournalEmailAddress user1@<your subscription domain> -Scope Global -Enabled $true
```
3. <span data-ttu-id="4b22e-173">새 저널 규칙이 성공적으로 만들어졌는지 Exchange Management PowerShell 보기입니다.</span><span class="sxs-lookup"><span data-stu-id="4b22e-173">View that the new Journal Rule was successfully created in Exchange Management PowerShell.</span></span>

## <a name="next-step"></a><span data-ttu-id="4b22e-174">다음 단계</span><span class="sxs-lookup"><span data-stu-id="4b22e-174">Next step</span></span>

<span data-ttu-id="4b22e-175">추가 [정보 보호](m365-enterprise-test-lab-guides.md#information-protection) 기능 및 기능 테스트 환경에서 살펴봅니다.</span><span class="sxs-lookup"><span data-stu-id="4b22e-175">Explore additional [information protection](m365-enterprise-test-lab-guides.md#information-protection) features and capabilities in your test environment.</span></span>

## <a name="see-also"></a><span data-ttu-id="4b22e-176">참고 항목</span><span class="sxs-lookup"><span data-stu-id="4b22e-176">See also</span></span>

[<span data-ttu-id="4b22e-177">Microsoft 365 Enterprise 테스트 랩 가이드</span><span class="sxs-lookup"><span data-stu-id="4b22e-177">Microsoft 365 Enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

[<span data-ttu-id="4b22e-178">Microsoft 365 Enterprise 배포</span><span class="sxs-lookup"><span data-stu-id="4b22e-178">Deploy Microsoft 365 Enterprise</span></span>](deploy-microsoft-365-enterprise.md)

[<span data-ttu-id="4b22e-179">Microsoft 365 Enterprise 설명서</span><span class="sxs-lookup"><span data-stu-id="4b22e-179">Microsoft 365 Enterprise documentation</span></span>](https://docs.microsoft.com/microsoft-365-enterprise/)