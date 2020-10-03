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
description: 이 문서를 사용 하 여 Office 365에서 권한이 부여 된 액세스 관리를 사용 하도록 설정 하 고 구성 하는 방법을 자세히 알아보세요.
ms.openlocfilehash: d75a8944cdacb6df2d6ee6570c0ce327d0e7ae00
ms.sourcegitcommit: 79a21583a52aedd06317bbcabd8be40663379dec
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/02/2020
ms.locfileid: "48341206"
---
# <a name="get-started-with-privileged-access-management"></a><span data-ttu-id="b113d-103">권한이 부여된 액세스 관리 시작</span><span class="sxs-lookup"><span data-stu-id="b113d-103">Get started with privileged access management</span></span>

<span data-ttu-id="b113d-104">이 항목에서는 조직에서 권한이 부여 된 액세스 관리를 사용 하도록 설정 하 고 구성 하는 과정을 안내 합니다.</span><span class="sxs-lookup"><span data-stu-id="b113d-104">This topic guides you through enabling and configuring privileged access management in your organization.</span></span> <span data-ttu-id="b113d-105">Microsoft 365 관리 센터 또는 Exchange 관리 PowerShell을 사용 하 여 권한 있는 액세스를 관리 하 고 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b113d-105">You can use either the Microsoft 365 admin center or Exchange Management PowerShell to manage and use privileged access.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="b113d-106">시작하기 전에</span><span class="sxs-lookup"><span data-stu-id="b113d-106">Before you begin</span></span>

<span data-ttu-id="b113d-107">권한이 부여 된 액세스 관리를 시작 하기 전에 [Microsoft 365 구독](https://www.microsoft.com/microsoft-365/compare-all-microsoft-365-plans) 및 모든 추가 기능을 확인 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b113d-107">Before you get started with privileged access management, you should confirm your [Microsoft 365 subscription](https://www.microsoft.com/microsoft-365/compare-all-microsoft-365-plans) and any add-ons.</span></span> <span data-ttu-id="b113d-108">권한이 부여 된 액세스 관리를 액세스 하 고 사용 하려면 조직에 다음 구독 또는 추가 기능 중 하나가 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b113d-108">To access and use privileged access management, your organization must have one of the following subscriptions or add-ons:</span></span>

- <span data-ttu-id="b113d-109">Microsoft 365 E5 구독 (유료 또는 평가판 버전)</span><span class="sxs-lookup"><span data-stu-id="b113d-109">Microsoft 365 E5 subscription (paid or trial version)</span></span>
- <span data-ttu-id="b113d-110">Microsoft 365 E3 구독 (또는 Office 365 E3 구독 + Enterprise Mobility and Security E3 구독) + Microsoft 365 E5 준수 추가 기능</span><span class="sxs-lookup"><span data-stu-id="b113d-110">Microsoft 365 E3 subscription (or Office 365 E3 subscription + Enterprise Mobility and Security E3 subscription) + the Microsoft 365 E5 Compliance add-on</span></span>
- <span data-ttu-id="b113d-111">모든 Microsoft 365, Office 365, Exchange, SharePoint 또는 비즈니스용 OneDrive 구독 + Microsoft 365 E5 참가자 위험 관리 추가 기능</span><span class="sxs-lookup"><span data-stu-id="b113d-111">Any Microsoft 365, Office 365, Exchange, SharePoint, or OneDrive for Business subscription + the Microsoft 365 E5 Insider Risk Management add-on</span></span>  
- <span data-ttu-id="b113d-112">Microsoft 365 A5 구독 (유료 또는 평가판 버전)</span><span class="sxs-lookup"><span data-stu-id="b113d-112">Microsoft 365 A5 subscription (paid or trial version)</span></span>
- <span data-ttu-id="b113d-113">Microsoft 365 A3 구독 (또는 Office 365 A3 구독 + Enterprise Mobility and Security A3 구독) + Microsoft A5 준수 추가 기능</span><span class="sxs-lookup"><span data-stu-id="b113d-113">Microsoft 365 A3 subscription (or Office 365 A3 subscription + Enterprise Mobility and Security A3 subscription) + the Microsoft A5 Compliance add-on</span></span>
- <span data-ttu-id="b113d-114">모든 Microsoft 365, Office 365, Exchange, SharePoint 또는 비즈니스용 OneDrive 교육 구독 + Microsoft 365 A5 참가자 위험 관리 추가 기능</span><span class="sxs-lookup"><span data-stu-id="b113d-114">Any Microsoft 365, Office 365, Exchange, SharePoint, or OneDrive for Education subscription + the Microsoft 365 A5 Insider Risk Management add-on</span></span>
- <span data-ttu-id="b113d-115">Office 365 Enterprise E5 구독 (유료 또는 평가판 버전)</span><span class="sxs-lookup"><span data-stu-id="b113d-115">Office 365 Enterprise E5 subscription (paid or trial version)</span></span>
- <span data-ttu-id="b113d-116">Office 365 Enterprise E3 구독 + Office 365 고급 준수 추가 기능 (새 구독에 더 이상 사용할 수 없음)</span><span class="sxs-lookup"><span data-stu-id="b113d-116">Office 365 Enterprise E3 subscription + the Office 365 Advanced Compliance add-on (no longer available for new subscriptions, see note)</span></span>

<span data-ttu-id="b113d-117">권한 있는 액세스 관리 요청을 전송 하 고 응답 하는 사용자에 게는 위의 라이선스 중 하나를 할당 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b113d-117">Users submitting and responding to privileged access management requests must be assigned one of the licenses above.</span></span>

>[!IMPORTANT]
><span data-ttu-id="b113d-118">Office 365 고급 규정 준수는 더 이상 독립 실행형 구독으로 판매 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="b113d-118">Office 365 Advanced Compliance is no longer sold as a standalone subscription.</span></span> <span data-ttu-id="b113d-119">현재 구독이 만료 되 면 고객은 위의 구독 중 하나로 전환 해야 하며, 이러한 기능은 동일 하거나 추가 준수 기능이 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b113d-119">When current subscriptions expire, customers should transition to one of the subscriptions above, which contain the same or additional compliance features.</span></span>

<span data-ttu-id="b113d-120">기존 Office 365 Enterprise E5 요금제가 없고 권한 있는 액세스 관리를 시도 하려는 경우 기존 Office 365 구독에 [microsoft 365을 추가](https://docs.microsoft.com/office365/admin/try-or-buy-microsoft-365) 하거나 Microsoft 365 Enterprise e 5의 [평가판을 등록할](https://www.microsoft.com/microsoft-365/enterprise) 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b113d-120">If you don't have an existing Office 365 Enterprise E5 plan and want to try privileged access management, you can [add Microsoft 365](https://docs.microsoft.com/office365/admin/try-or-buy-microsoft-365) to your existing Office 365 subscription or [sign up for a trial](https://www.microsoft.com/microsoft-365/enterprise) of Microsoft 365 Enterprise E5.</span></span>

## <a name="enable-and-configure-privileged-access-management"></a><span data-ttu-id="b113d-121">권한 있는 액세스 관리 사용 및 구성</span><span class="sxs-lookup"><span data-stu-id="b113d-121">Enable and configure privileged access management</span></span>

<span data-ttu-id="b113d-122">조직에서 권한 있는 액세스를 설정 및 사용 하려면 다음 단계를 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="b113d-122">Follow these steps to set up and use privileged access in your organization:</span></span>

- [<span data-ttu-id="b113d-123">1 단계: 승인자 그룹 만들기</span><span class="sxs-lookup"><span data-stu-id="b113d-123">Step 1: Create an approver's group</span></span>](privileged-access-management-configuration.md#step1)

    <span data-ttu-id="b113d-124">권한 액세스 사용을 시작 하기 전에 관리자 권한 및 권한 있는 작업에 대 한 들어오는 요청 액세스에 대 한 승인 권한이 필요한 사람을 결정 합니다.</span><span class="sxs-lookup"><span data-stu-id="b113d-124">Before you start using privilege access, determine who needs approval authority for incoming requests for access to elevated and privileged tasks.</span></span> <span data-ttu-id="b113d-125">승인자 그룹에 속하는 모든 사용자는 액세스 요청을 승인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b113d-125">Any user who is part of the Approvers' group is able to approve access requests.</span></span> <span data-ttu-id="b113d-126">이 그룹은 Office 365에서 메일 사용이 가능한 보안 그룹을 만들어 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b113d-126">This group is enabled by creating a mail-enabled security group in Office 365.</span></span>

- [<span data-ttu-id="b113d-127">2 단계: 권한 있는 액세스 사용</span><span class="sxs-lookup"><span data-stu-id="b113d-127">Step 2: Enable privileged access</span></span>](privileged-access-management-configuration.md#step2)

    <span data-ttu-id="b113d-128">권한 있는 액세스 관리 액세스 제어에서 제외 하려는 시스템 계정 집합을 비롯 하 여 Office 365에서 기본 승인자 그룹을 사용 하 여 권한이 부여 된 access를 명시적으로 사용 하도록 설정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b113d-128">Privileged access must be explicitly enabled in Office 365 with the default approver group, including a set of system accounts that you want excluded from the privileged access management access control.</span></span>

- [<span data-ttu-id="b113d-129">3 단계: 액세스 정책 만들기</span><span class="sxs-lookup"><span data-stu-id="b113d-129">Step 3: Create an access policy</span></span>](privileged-access-management-configuration.md#step3)

    <span data-ttu-id="b113d-130">승인 정책을 만들면 개별 작업에서 범위가 지정 되는 특정 승인 요구 사항을 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b113d-130">Creating an approval policy allows you to define the specific approval requirements scoped at individual tasks.</span></span> <span data-ttu-id="b113d-131">승인 유형 옵션은 **자동** 또는 **수동**입니다.</span><span class="sxs-lookup"><span data-stu-id="b113d-131">The approval type options are **Auto** or **Manual**.</span></span>

- [<span data-ttu-id="b113d-132">4 단계: 권한 있는 액세스 요청 제출/승인</span><span class="sxs-lookup"><span data-stu-id="b113d-132">Step 4: Submit/approve privileged access requests</span></span>](privileged-access-management-configuration.md#step4)

    <span data-ttu-id="b113d-133">권한 있는 액세스를 사용 하도록 설정 하 고 나면 연결 된 승인 정책이 정의 된 모든 작업에 대 한 승인이 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="b113d-133">Once enabled, privileged access requires approvals for any task that has an associated approval policy defined.</span></span> <span data-ttu-id="b113d-134">승인 정책에 포함 된 작업의 경우 사용자는 작업을 실행 하는 데 필요한 권한을 요청 하 고 액세스 승인을 받아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b113d-134">For tasks included in an approval policy, users must request and be granted access approval to have permissions necessary to execute the task.</span></span>

<span data-ttu-id="b113d-135">승인을 받은 후에는 요청 하는 사용자가 원하는 작업을 실행할 수 있으며, 권한이 부여 된 access에서는 사용자를 대신 하 여 작업을 승인 하 고 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="b113d-135">After approval is granted, the requesting user can execute the intended task and privileged access will authorize and execute the task on behalf of the user.</span></span> <span data-ttu-id="b113d-136">요청 된 기간 (기본 기간: 4 시간)에 대 한 승인은 유효한 상태로 유지 되므로 요청 자가 원하는 작업을 여러 번 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b113d-136">The approval remains valid for the requested duration (default duration is 4 hours), during which the requester can execute the intended task multiple times.</span></span> <span data-ttu-id="b113d-137">이러한 모든 실행이 기록 되 고 보안 및 준수 감사를 위해 사용할 수 있게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b113d-137">All such executions are logged and made available for security and compliance auditing.</span></span> 

>[!NOTE]
><span data-ttu-id="b113d-138">Exchange 관리 PowerShell을 사용 하 여 권한 있는 액세스를 사용 하도록 설정 하 고 구성 하려면 [다단계 인증을 사용 하 여 Exchange Online powershell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell#connect-to-exchange-online-powershell-using-mfa) 에 연결의 단계를 수행 하 여 Office 365 자격 증명을 사용 하 여 Exchange online powershell에 연결 합니다.</span><span class="sxs-lookup"><span data-stu-id="b113d-138">If you want to use Exchange Management PowerShell to enable and configure privileged access, follow the steps in [Connect to Exchange Online PowerShell using Multi-Factor authentication](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell#connect-to-exchange-online-powershell-using-mfa) to connect to Exchange Online PowerShell with your Office 365 credentials.</span></span> <span data-ttu-id="b113d-139">조직에 대해 Exchange Online PowerShell에 연결 하는 동안 권한 있는 액세스를 사용 하도록 설정 하는 단계를 사용 하도록 하는 다단계 인증을 사용 하도록 설정할 필요는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="b113d-139">You do not need to enable multi-factor authentication for your organization to use the steps to enable privileged access while connecting to Exchange Online PowerShell.</span></span> <span data-ttu-id="b113d-140">다단계 인증을 사용 하 여 연결-요청에 서명 하기 위해 특권 수준의 액세스에서 사용 되는 OAuth 토큰을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="b113d-140">Connecting with multi-factor authentication creates an OAuth token that is used by privileged access for signing your requests.</span></span>

<span data-ttu-id="b113d-141"><a name="step1"> </a></span><span class="sxs-lookup"><span data-stu-id="b113d-141"><a name="step1"> </a></span></span>

## <a name="step-1-create-an-approvers-group"></a><span data-ttu-id="b113d-142">1 단계: 승인자 그룹 만들기</span><span class="sxs-lookup"><span data-stu-id="b113d-142">Step 1: Create an approver's group</span></span>

1. <span data-ttu-id="b113d-143">조직의 관리자 계정에 대 한 자격 증명을 사용 하 여 [Microsoft 365 관리 센터](https://admin.microsoft.com) 에 로그인 합니다.</span><span class="sxs-lookup"><span data-stu-id="b113d-143">Sign into the [Microsoft 365 admin center](https://admin.microsoft.com) using credentials for an admin account in your organization.</span></span>

2. <span data-ttu-id="b113d-144">관리 센터에서 그룹으로 **이동 하 여**  >  **그룹을 추가**합니다.</span><span class="sxs-lookup"><span data-stu-id="b113d-144">In the Admin Center, go to **Groups** > **Add a group**.</span></span>

3. <span data-ttu-id="b113d-145">**메일 사용이 가능한 보안 그룹** 을 선택 하 고 새 그룹에 대 한 **이름**, **그룹 전자 메일 주소**및 **설명** 필드를 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="b113d-145">Select **mail-enabled security group** and then complete the **Name**, **Group email address**, and **Description** fields for the new group.</span></span>

4. <span data-ttu-id="b113d-146">그룹을 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="b113d-146">Save the group.</span></span> <span data-ttu-id="b113d-147">그룹을 완전히 구성 하 고 Microsoft 365 관리 센터에 표시 하는 데 몇 분 정도 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b113d-147">It may take a few minutes for the group to be fully configured and to appear in the Microsoft 365 admin center.</span></span>

5. <span data-ttu-id="b113d-148">새 승인자의 그룹을 선택 하 고 **편집** 을 선택 하 여 그룹에 사용자를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="b113d-148">Select the new approver's group and select **edit** to add users to the group.</span></span>

6. <span data-ttu-id="b113d-149">그룹을 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="b113d-149">Save the group.</span></span>

<span data-ttu-id="b113d-150"><a name="step2"> </a></span><span class="sxs-lookup"><span data-stu-id="b113d-150"><a name="step2"> </a></span></span>

## <a name="step-2-enable-privileged-access"></a><span data-ttu-id="b113d-151">2 단계: 권한 있는 액세스 사용</span><span class="sxs-lookup"><span data-stu-id="b113d-151">Step 2: Enable privileged access</span></span>

### <a name="in-the-microsoft-365-admin-center"></a><span data-ttu-id="b113d-152">Microsoft 365 관리 센터에서</span><span class="sxs-lookup"><span data-stu-id="b113d-152">In the Microsoft 365 Admin Center</span></span>

1. <span data-ttu-id="b113d-153">조직의 관리자 계정에 대 한 자격 증명을 사용 하 여 [Microsoft 365 관리 센터](https://admin.microsoft.com) 에 로그인 합니다.</span><span class="sxs-lookup"><span data-stu-id="b113d-153">Sign into the [Microsoft 365 Admin Center](https://admin.microsoft.com) using credentials for an admin account in your organization.</span></span>

2. <span data-ttu-id="b113d-154">관리 센터에서 **설정**  >  **조직 설정**  >  **보안 & 개인 정보**  >  **권한 부여 액세스**로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="b113d-154">In the Admin Center, go to **Settings** > **Org Settings** > **Security & Privacy** > **Privileged access**.</span></span>

3. <span data-ttu-id="b113d-155">권한 있는 **작업에 대 한 승인 필요** 컨트롤을 사용 하도록 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="b113d-155">Enable the **Require approvals for privileged tasks** control.</span></span>

4. <span data-ttu-id="b113d-156">1 단계에서 만든 승인자 그룹을 **기본 승인자 그룹**으로 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="b113d-156">Assign the approver's group you created in Step 1 as the **Default approvers group**.</span></span>

5. <span data-ttu-id="b113d-157">**저장** 하 고 **닫습니다**.</span><span class="sxs-lookup"><span data-stu-id="b113d-157">**Save** and **Close**.</span></span>

### <a name="in-exchange-management-powershell"></a><span data-ttu-id="b113d-158">Exchange 관리 PowerShell에서</span><span class="sxs-lookup"><span data-stu-id="b113d-158">In Exchange Management PowerShell</span></span>

<span data-ttu-id="b113d-159">권한 있는 액세스를 사용 하도록 설정 하 고 승인자의 그룹을 할당 하려면 Exchange Online PowerShell에서 다음 명령을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="b113d-159">To enable privileged access and to assign the approver's group, run the following command in Exchange Online PowerShell:</span></span>

```PowerShell
Enable-ElevatedAccessControl -AdminGroup '<default approver group>' -SystemAccounts @('<systemAccountUPN1>','<systemAccountUPN2>')
```

<span data-ttu-id="b113d-160">예제:</span><span class="sxs-lookup"><span data-stu-id="b113d-160">Example:</span></span>

```PowerShell
Enable-ElevatedAccessControl -AdminGroup 'pamapprovers@fabrikam.onmicrosoft.com' -SystemAccounts @('sys1@fabrikamorg.onmicrosoft.com', sys2@fabrikamorg.onmicrosoft.com')
```

>[!NOTE]
><span data-ttu-id="b113d-161">시스템 계정 기능을 사용 하 여 조직 내의 특정 자동화 기능이 권한 있는 액세스에 대 한 종속성 없이 작동할 수 있으며, 이러한 제외를 허용 하 고 정기적으로 승인 하 고 감사 해야 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="b113d-161">System accounts feature is made available to ensure certain automations within your organizations can work without dependency on privileged access, however it is recommended that such exclusions be exceptional and those allowed should be approved and audited regularly.</span></span>

<span data-ttu-id="b113d-162"><a name="step3"> </a></span><span class="sxs-lookup"><span data-stu-id="b113d-162"><a name="step3"> </a></span></span>

## <a name="step-3-create-an-access-policy"></a><span data-ttu-id="b113d-163">3 단계: 액세스 정책 만들기</span><span class="sxs-lookup"><span data-stu-id="b113d-163">Step 3: Create an access policy</span></span>

<span data-ttu-id="b113d-164">조직에 대해 최대 30 개의 권한이 부여 된 액세스 정책을 만들고 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b113d-164">You can create and configure up to 30 privileged access policies for your organization.</span></span>

### <a name="in-the-microsoft-365-admin-center"></a><span data-ttu-id="b113d-165">Microsoft 365 관리 센터에서</span><span class="sxs-lookup"><span data-stu-id="b113d-165">In the Microsoft 365 Admin Center</span></span>

1. <span data-ttu-id="b113d-166">조직의 관리자 계정에 대 한 자격 증명을 사용 하 여 [Microsoft 365 관리 센터](https://admin.microsoft.com) 에 로그인 합니다.</span><span class="sxs-lookup"><span data-stu-id="b113d-166">Sign into the [Microsoft 365 Admin Center](https://admin.microsoft.com) using credentials for an admin account in your organization.</span></span>

2. <span data-ttu-id="b113d-167">관리 센터에서 **설정**  >  **조직 설정**  >  **보안 & 개인 정보**  >  **권한 부여 액세스**로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="b113d-167">In the Admin Center, go to **Settings** > **Org Settings** > **Security & Privacy** > **Privileged access**.</span></span>

3. <span data-ttu-id="b113d-168">**액세스 정책 및 요청 관리를**선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="b113d-168">Select **Manage access policies and requests**.</span></span>

4. <span data-ttu-id="b113d-169">정책 **구성을** 선택 하 고 **정책 추가**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="b113d-169">Select **Configure policies** and select **Add a policy**.</span></span>

5. <span data-ttu-id="b113d-170">드롭다운 필드에서 조직에 적합 한 값을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="b113d-170">From the drop-down fields, select the appropriate values for your organization:</span></span>
    
    <span data-ttu-id="b113d-171">**정책 유형**: 작업, 역할 또는 역할 그룹</span><span class="sxs-lookup"><span data-stu-id="b113d-171">**Policy type**: Task, Role, or Role Group</span></span>

    <span data-ttu-id="b113d-172">**정책 범위**: Exchange</span><span class="sxs-lookup"><span data-stu-id="b113d-172">**Policy scope**: Exchange</span></span>

    <span data-ttu-id="b113d-173">**정책 이름**: 사용 가능한 정책에서 선택</span><span class="sxs-lookup"><span data-stu-id="b113d-173">**Policy name**: Select from the available policies</span></span>

    <span data-ttu-id="b113d-174">**승인 유형**: 수동 또는 자동</span><span class="sxs-lookup"><span data-stu-id="b113d-174">**Approval type**: Manual or Auto</span></span>

    <span data-ttu-id="b113d-175">**승인 그룹**: 1 단계에서 만든 승인자 그룹을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="b113d-175">**Approval group**: Select the approvers group created in Step 1</span></span>

6. <span data-ttu-id="b113d-176">**만들기** 를 선택한 다음 **닫기를**선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="b113d-176">Select **Create** and then **Close**.</span></span> <span data-ttu-id="b113d-177">정책을 완전히 구성 및 사용 하도록 설정 하는 데 몇 분 정도 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b113d-177">It may take a few minutes for the policy to be fully configured and enabled.</span></span>

### <a name="in-exchange-management-powershell"></a><span data-ttu-id="b113d-178">Exchange 관리 PowerShell에서</span><span class="sxs-lookup"><span data-stu-id="b113d-178">In Exchange Management PowerShell</span></span>

<span data-ttu-id="b113d-179">승인 정책을 만들고 정의 하려면 Exchange Online PowerShell에서 다음 명령을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="b113d-179">To create and define an approval policy, run the following command in Exchange Online PowerShell:</span></span>

```PowerShell
New-ElevatedAccessApprovalPolicy -Task 'Exchange\<exchange management cmdlet name>' -ApprovalType <Manual, Auto> -ApproverGroup '<default/custom approver group>'
```

<span data-ttu-id="b113d-180">예제:</span><span class="sxs-lookup"><span data-stu-id="b113d-180">Example:</span></span>

```PowerShell
New-ElevatedAccessApprovalPolicy -Task 'Exchange\New-MoveRequest' -ApprovalType Manual -ApproverGroup 'mbmanagers@fabrikamorg.onmicrosoft.com'
```

<span data-ttu-id="b113d-181"><a name="step4"> </a></span><span class="sxs-lookup"><span data-stu-id="b113d-181"><a name="step4"> </a></span></span>

## <a name="step-4-submitapprove-privileged-access-requests"></a><span data-ttu-id="b113d-182">4 단계: 권한 있는 액세스 요청 제출/승인</span><span class="sxs-lookup"><span data-stu-id="b113d-182">Step 4: Submit/approve privileged access requests</span></span>

### <a name="requesting-elevation-authorization-to-execute-privileged-tasks"></a><span data-ttu-id="b113d-183">권한 있는 작업 실행을 위한 권한 상승 요청</span><span class="sxs-lookup"><span data-stu-id="b113d-183">Requesting elevation authorization to execute privileged tasks</span></span>

<span data-ttu-id="b113d-184">권한 있는 액세스에 대 한 요청은 요청이 제출 된 후 최대 24 시간 동안 유효 합니다.</span><span class="sxs-lookup"><span data-stu-id="b113d-184">Requests for privileged access are valid for up to 24 hours after the request is submitted.</span></span> <span data-ttu-id="b113d-185">승인 되거나 거부 되지 않으면 요청이 만료 되 고 액세스가 승인 되지 않은 것입니다.</span><span class="sxs-lookup"><span data-stu-id="b113d-185">If not approved or denied, the requests expire and access is not approved.</span></span>

#### <a name="in-the-microsoft-365-admin-center"></a><span data-ttu-id="b113d-186">Microsoft 365 관리 센터에서</span><span class="sxs-lookup"><span data-stu-id="b113d-186">In the Microsoft 365 Admin Center</span></span>

1. <span data-ttu-id="b113d-187">자격 증명을 사용 하 여 [Microsoft 365 관리 센터](https://admin.microsoft.com) 에 로그인 합니다.</span><span class="sxs-lookup"><span data-stu-id="b113d-187">Sign into the [Microsoft 365 Admin Center](https://admin.microsoft.com) using your credentials.</span></span>

2. <span data-ttu-id="b113d-188">관리 센터에서 **설정**  >  **조직 설정**  >  **보안 & 개인 정보**  >  **권한 부여 액세스**로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="b113d-188">In the Admin Center, go to **Settings** > **Org Settings** > **Security & Privacy** > **Privileged access**.</span></span>

3. <span data-ttu-id="b113d-189">**액세스 정책 및 요청 관리를**선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="b113d-189">Select **Manage access policies and requests**.</span></span>

4. <span data-ttu-id="b113d-190">**새 요청**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="b113d-190">Select **New request**.</span></span> <span data-ttu-id="b113d-191">드롭다운 필드에서 조직에 적합 한 값을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="b113d-191">From the drop-down fields, select the appropriate values for your organization:</span></span>

    <span data-ttu-id="b113d-192">**요청 유형**: 작업, 역할 또는 역할 그룹</span><span class="sxs-lookup"><span data-stu-id="b113d-192">**Request type**: Task, Role, or Role Group</span></span>

    <span data-ttu-id="b113d-193">**요청 범위**: Exchange</span><span class="sxs-lookup"><span data-stu-id="b113d-193">**Request scope**: Exchange</span></span>

    <span data-ttu-id="b113d-194">**요청**: 사용 가능한 정책에서 선택</span><span class="sxs-lookup"><span data-stu-id="b113d-194">**Request for**: Select from the available policies</span></span>

    <span data-ttu-id="b113d-195">**기간 (시간)**: 요청 된 액세스에 대 한 시간 수입니다.</span><span class="sxs-lookup"><span data-stu-id="b113d-195">**Duration (hours)**: Number of hours of requested access.</span></span> <span data-ttu-id="b113d-196">요청할 수 있는 시간에 제한이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="b113d-196">There isn't a limit on the number of hours that can be requested.</span></span>

    <span data-ttu-id="b113d-197">**설명**: 액세스 요청과 관련 된 설명에 대 한 텍스트 필드입니다.</span><span class="sxs-lookup"><span data-stu-id="b113d-197">**Comments**: Text field for comments related to your access request</span></span>

5. <span data-ttu-id="b113d-198">**저장** 을 선택한 다음 **닫기를**선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="b113d-198">Select **Save** and then **Close**.</span></span> <span data-ttu-id="b113d-199">요청은 전자 메일을 통해 승인자 그룹에 전송 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b113d-199">Your request will be sent to the approver's group via email.</span></span>

#### <a name="in-exchange-management-powershell"></a><span data-ttu-id="b113d-200">Exchange 관리 PowerShell에서</span><span class="sxs-lookup"><span data-stu-id="b113d-200">In Exchange Management PowerShell</span></span>

<span data-ttu-id="b113d-201">Exchange Online PowerShell에서 다음 명령을 실행 하 여 승인자 그룹에 대 한 승인 요청을 만들고 제출 합니다.</span><span class="sxs-lookup"><span data-stu-id="b113d-201">Run the following command in Exchange Online PowerShell to create and submit an approval request to the approver's group:</span></span>

```PowerShell
New-ElevatedAccessRequest -Task 'Exchange\<exchange management cmdlet name>' -Reason '<appropriate reason>' -DurationHours <duration in hours>
```

<span data-ttu-id="b113d-202">예제:</span><span class="sxs-lookup"><span data-stu-id="b113d-202">Example:</span></span>

```PowerShell
New-ElevatedAccessRequest -Task 'Exchange\New-MoveRequest' -Reason 'Attempting to fix the user mailbox error' -DurationHours 4
```

### <a name="view-status-of-elevation-requests"></a><span data-ttu-id="b113d-203">권한 상승 요청의 상태 보기</span><span class="sxs-lookup"><span data-stu-id="b113d-203">View status of elevation requests</span></span>

<span data-ttu-id="b113d-204">승인 요청을 만든 후에는 요청 ID와 연결 된을 사용 하 여 관리 센터 또는 Exchange 관리 PowerShell에서 권한 상승 요청 상태를 검토할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b113d-204">After an approval request is created, elevation request status can be reviewed in the admin center or in Exchange Management PowerShell using the associated with request ID.</span></span>

#### <a name="in-the-microsoft-365-admin-center"></a><span data-ttu-id="b113d-205">Microsoft 365 관리 센터에서</span><span class="sxs-lookup"><span data-stu-id="b113d-205">In the Microsoft 365 admin center</span></span>

1. <span data-ttu-id="b113d-206">자격 증명을 사용 하 여 [Microsoft 365 관리 센터](https://admin.microsoft.com) 에 로그인 합니다.</span><span class="sxs-lookup"><span data-stu-id="b113d-206">Sign into the [Microsoft 365 admin center](https://admin.microsoft.com) with your credentials.</span></span>

2. <span data-ttu-id="b113d-207">관리 센터에서 **설정**  >  **조직 설정**  >  **보안 & 개인 정보**  >  **권한 부여 액세스**로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="b113d-207">In the admin center, go to **Settings** > **Org Settings** > **Security & Privacy** > **Privileged access**.</span></span>

3. <span data-ttu-id="b113d-208">**액세스 정책 및 요청 관리를**선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="b113d-208">Select **Manage access policies and requests**.</span></span>

4. <span data-ttu-id="b113d-209">**보기** 를 선택 하 여 **대기**, **승인**, **거부**또는 **사용자 Lockbox** 상태를 기준으로 제출 된 요청을 필터링 합니다.</span><span class="sxs-lookup"><span data-stu-id="b113d-209">Select **View** to filter submitted requests by **Pending**, **Approved**, **Denied**, or **Customer Lockbox** status.</span></span>

#### <a name="in-exchange-management-powershell"></a><span data-ttu-id="b113d-210">Exchange 관리 PowerShell에서</span><span class="sxs-lookup"><span data-stu-id="b113d-210">In Exchange Management PowerShell</span></span>

<span data-ttu-id="b113d-211">Exchange Online PowerShell에서 다음 명령을 실행 하 여 특정 요청 ID에 대 한 승인 요청 상태를 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="b113d-211">Run the following command in Exchange Online PowerShell to view an approval request status for a specific request ID:</span></span>

```PowerShell
Get-ElevatedAccessRequest -Identity <request ID> | select RequestStatus
```

<span data-ttu-id="b113d-212">예제:</span><span class="sxs-lookup"><span data-stu-id="b113d-212">Example:</span></span>

```PowerShell
Get-ElevatedAccessRequest -Identity 28560ed0-419d-4cc3-8f5b-603911cbd450 | select RequestStatus
```

### <a name="approving-an-elevation-authorization-request"></a><span data-ttu-id="b113d-213">권한 상승 인증 요청 승인</span><span class="sxs-lookup"><span data-stu-id="b113d-213">Approving an elevation authorization request</span></span>

<span data-ttu-id="b113d-214">승인 요청이 작성 되 면 관련 승인자 그룹의 구성원은 전자 메일 알림을 수신 하 고 요청 ID와 연결 된 요청을 승인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b113d-214">When an approval request is created, members of the relevant approver group receive an email notification and can approve the request associated with the request ID.</span></span> <span data-ttu-id="b113d-215">요청자에 게는 전자 메일 메시지를 통한 승인 또는 거부 요청이 통지 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b113d-215">The requestor is notified of the request approval or denial via email message.</span></span>

#### <a name="in-the-microsoft-365-admin-center"></a><span data-ttu-id="b113d-216">Microsoft 365 관리 센터에서</span><span class="sxs-lookup"><span data-stu-id="b113d-216">In the Microsoft 365 admin center</span></span>

1. <span data-ttu-id="b113d-217">자격 증명을 사용 하 여 [Microsoft 365 관리 센터](https://admin.microsoft.com) 에 로그인 합니다.</span><span class="sxs-lookup"><span data-stu-id="b113d-217">Sign into the [Microsoft 365 admin center](https://admin.microsoft.com) with your credentials.</span></span>

2. <span data-ttu-id="b113d-218">관리 센터에서 **설정**  >  **조직 설정**  >  **보안 & 개인 정보**  >  **권한 부여 액세스**로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="b113d-218">In the admin center, go to **Settings** > **Org Settings** > **Security & Privacy** > **Privileged access**.</span></span>

3. <span data-ttu-id="b113d-219">**액세스 정책 및 요청 관리를**선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="b113d-219">Select **Manage access policies and requests**.</span></span>

4. <span data-ttu-id="b113d-220">나열 된 요청을 선택 하 여 세부 정보를 보고 요청에 대해 작업을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="b113d-220">Select a listed request to view the details and to take action on the request.</span></span>

5. <span data-ttu-id="b113d-221">요청을 승인 하려면 **승인을** 선택 하 고 요청을 거부 하려면 **거부** 를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="b113d-221">Select **Approve** to approve the request or select **Deny** to deny the request.</span></span> <span data-ttu-id="b113d-222">이전에 승인 된 요청은 **취소**를 선택 하 여 액세스를 취소할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b113d-222">Previously approved requests can have access revoked by selecting **Revoke**.</span></span>

#### <a name="in-exchange-management-powershell"></a><span data-ttu-id="b113d-223">Exchange 관리 PowerShell에서</span><span class="sxs-lookup"><span data-stu-id="b113d-223">In Exchange Management PowerShell</span></span>

<span data-ttu-id="b113d-224">권한 상승 요청을 승인 하려면 Exchange Online PowerShell에서 다음 명령을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="b113d-224">To approve an elevation authorization request, run the following command in Exchange Online PowerShell:</span></span>

```PowerShell
Approve-ElevatedAccessRequest -RequestId <request id> -Comment '<approval comment>'
```

<span data-ttu-id="b113d-225">예제:</span><span class="sxs-lookup"><span data-stu-id="b113d-225">Example:</span></span>

```PowerShell
Approve-ElevatedAccessRequest -RequestId a4bc1bdf-00a1-42b4-be65-b6c63d6be279 -Comment '<approval comment>'
```

<span data-ttu-id="b113d-226">권한 상승 요청을 거부 하려면 Exchange Online PowerShell에서 다음 명령을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="b113d-226">To deny an elevation authorization request, run the following command in Exchange Online PowerShell:</span></span>

```PowerShell
Deny-ElevatedAccessRequest -RequestId <request id> -Comment '<denial comment>'
```

<span data-ttu-id="b113d-227">예제:</span><span class="sxs-lookup"><span data-stu-id="b113d-227">Example:</span></span>

```PowerShell
Deny-ElevatedAccessRequest -RequestId a4bc1bdf-00a1-42b4-be65-b6c63d6be279 -Comment '<denial comment>'
```

## <a name="delete-a-privileged-access-policy-in-office-365"></a><span data-ttu-id="b113d-228">Office 365에서 권한이 부여 된 액세스 정책 삭제</span><span class="sxs-lookup"><span data-stu-id="b113d-228">Delete a privileged access policy in Office 365</span></span>

<span data-ttu-id="b113d-229">조직에서 더 이상 필요 하지 않은 액세스 정책을 삭제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b113d-229">If it is no longer needed in your organization, you can delete a privileged access policy.</span></span>

### <a name="in-the-microsoft-365-admin-center"></a><span data-ttu-id="b113d-230">Microsoft 365 관리 센터에서</span><span class="sxs-lookup"><span data-stu-id="b113d-230">In the Microsoft 365 admin center</span></span>

1. <span data-ttu-id="b113d-231">조직의 관리자 계정에 대 한 자격 증명을 사용 하 여 [Microsoft 365 관리 센터](https://admin.microsoft.com) 에 로그인 합니다.</span><span class="sxs-lookup"><span data-stu-id="b113d-231">Sign into the [Microsoft 365 admin center](https://admin.microsoft.com) using credentials for an admin account in your organization.</span></span>

2. <span data-ttu-id="b113d-232">관리 센터에서 **설정**  >  **조직 설정**  >  **보안 & 개인 정보**  >  **권한 부여 액세스**로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="b113d-232">In the admin center, go to **Settings** > **Org Settings** > **Security & Privacy** > **Privileged access**.</span></span>

3. <span data-ttu-id="b113d-233">**액세스 정책 및 요청 관리를**선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="b113d-233">Select **Manage access policies and requests**.</span></span>

4. <span data-ttu-id="b113d-234">**정책 구성을**선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="b113d-234">Select **Configure policies**.</span></span>

5. <span data-ttu-id="b113d-235">삭제할 정책을 선택 하 고 **정책 제거**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="b113d-235">Select the policy you want to delete, then select **Remove Policy**.</span></span>

6. <span data-ttu-id="b113d-236">**닫기**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="b113d-236">Select **Close**.</span></span>

### <a name="in-exchange-management-powershell"></a><span data-ttu-id="b113d-237">Exchange 관리 PowerShell에서</span><span class="sxs-lookup"><span data-stu-id="b113d-237">In Exchange Management PowerShell</span></span>

<span data-ttu-id="b113d-238">권한이 부여 된 액세스 정책을 삭제 하려면 Exchange Online Powershell에서 다음 명령을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="b113d-238">To delete a privileged access policy, run the following command in Exchange Online Powershell:</span></span>

```PowerShell
Remove-ElevatedAccessApprovalPolicy -Identity <identity GUID of the policy you want to delete>
```

## <a name="disable-privileged-access-in-office-365"></a><span data-ttu-id="b113d-239">Office 365에서 권한이 부여 된 액세스를 사용 하지 않도록 설정</span><span class="sxs-lookup"><span data-stu-id="b113d-239">Disable privileged access in Office 365</span></span>

<span data-ttu-id="b113d-240">필요한 경우 조직에 대해 권한이 부여 된 액세스 관리를 사용 하지 않도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b113d-240">If needed, you can disable privileged access management for your organization.</span></span> <span data-ttu-id="b113d-241">권한 있는 액세스를 사용 하지 않도록 설정 해도 연결 된 승인 정책이 나 승인자 그룹은 삭제 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="b113d-241">Disabling privileged access does not delete any associated approval policies or approver groups.</span></span>

### <a name="in-the-microsoft-365-admin-center"></a><span data-ttu-id="b113d-242">Microsoft 365 관리 센터에서</span><span class="sxs-lookup"><span data-stu-id="b113d-242">In the Microsoft 365 admin center</span></span>

1. <span data-ttu-id="b113d-243">조직의 관리자 계정에 대 한 자격 증명을 사용 하 여 [Microsoft 365 관리 센터](https://admin.microsoft.com) 에 로그인 합니다.</span><span class="sxs-lookup"><span data-stu-id="b113d-243">Sign into the [Microsoft 365 admin center](https://admin.microsoft.com) with credentials for an admin account in your organization.</span></span>

2. <span data-ttu-id="b113d-244">관리 센터에서 **설정**  >  **조직 설정**  >  **보안 & 개인 정보**  >  **권한 부여 액세스**로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="b113d-244">In the Admin Center, go to **Settings** > **Org Settings** > **Security & Privacy** > **Privileged access**.</span></span>

3. <span data-ttu-id="b113d-245">권한 있는 **액세스 제어에 대 한 승인 필요** 를 사용 하도록 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="b113d-245">Enable the **Require approvals for privileged access** control.</span></span>

### <a name="in-exchange-management-powershell"></a><span data-ttu-id="b113d-246">Exchange 관리 PowerShell에서</span><span class="sxs-lookup"><span data-stu-id="b113d-246">In Exchange Management PowerShell</span></span>

<span data-ttu-id="b113d-247">권한 있는 액세스를 사용 하지 않도록 설정 하려면 Exchange Online Powershell에서 다음 명령을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="b113d-247">To disable privileged access, run the following command in Exchange Online Powershell:</span></span>

```PowerShell
Disable-ElevatedAccessControl
```
