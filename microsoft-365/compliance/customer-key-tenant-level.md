---
title: 테넌트 수준에서의 Microsoft 365 고객 키(공개 미리보기)
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 2/17/2021
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- M365-security-compliance
- m365solution-mip
- m365initiative-compliance
description: Microsoft 365 테넌트 내의 모든 데이터에 대해 고객 키를 설정하는 방법을 학습합니다.
ms.openlocfilehash: 7ffa9a8148a8ae699711b62da48cd2c856d48cac
ms.sourcegitcommit: 3d48e198e706f22ac903b346cadda06b2368dd1e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/11/2021
ms.locfileid: "50727481"
---
# <a name="overview-of-customer-key-for-microsoft-365-at-the-tenant-level-public-preview"></a><span data-ttu-id="76c4d-103">테넌트 수준의 Microsoft 365 고객 키 개요(공개 미리 보기)</span><span class="sxs-lookup"><span data-stu-id="76c4d-103">Overview of Customer Key for Microsoft 365 at the tenant level (public preview)</span></span>

<span data-ttu-id="76c4d-104">제공한 키를 사용하여 DEP(데이터 암호화 정책)를 만들어 테넌트에 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="76c4d-104">Using keys you provide, you can create a data encryption policy (DEP) and assign it to the tenant.</span></span> <span data-ttu-id="76c4d-105">DEP는 이러한 워크로드에 대해 테넌트 전체의 데이터를 암호화합니다.</span><span class="sxs-lookup"><span data-stu-id="76c4d-105">The DEP encrypts data across the tenant for these workloads:</span></span>

- <span data-ttu-id="76c4d-106">Teams 채팅 메시지(1:1 채팅, 그룹 채팅, 모임 채팅 및 채널 대화)</span><span class="sxs-lookup"><span data-stu-id="76c4d-106">Teams chat messages (1:1 chats, group chats, meeting chats and channel conversations)</span></span>
- <span data-ttu-id="76c4d-107">Teams 미디어 메시지(이미지, 코드, 비디오 메시지, 오디오 메시지, 위키 이미지)</span><span class="sxs-lookup"><span data-stu-id="76c4d-107">Teams media messages (images, code snippets, video messages, audio messages, wiki images)</span></span>
- <span data-ttu-id="76c4d-108">Teams 저장소에 저장된 Teams 통화 및 모임 녹음/녹화</span><span class="sxs-lookup"><span data-stu-id="76c4d-108">Teams call and meeting recordings stored in Teams storage</span></span>
- <span data-ttu-id="76c4d-109">Teams 채팅 알림</span><span class="sxs-lookup"><span data-stu-id="76c4d-109">Teams chat notifications</span></span>
- <span data-ttu-id="76c4d-110">Cortana의 Teams 채팅 제안</span><span class="sxs-lookup"><span data-stu-id="76c4d-110">Teams chat suggestions by Cortana</span></span>
- <span data-ttu-id="76c4d-111">Teams 상태 메시지</span><span class="sxs-lookup"><span data-stu-id="76c4d-111">Teams status messages</span></span>
- <span data-ttu-id="76c4d-112">Exchange Online에 대한 사용자 및 신호 정보</span><span class="sxs-lookup"><span data-stu-id="76c4d-112">User and signal information for Exchange Online</span></span>
- <span data-ttu-id="76c4d-113">응용 프로그램 수준에서 아직 암호화되지 않은 Exchange Online 사서함</span><span class="sxs-lookup"><span data-stu-id="76c4d-113">Exchange Online mailboxes that aren't already encrypted Customer Key DEPs at the application level</span></span>

<span data-ttu-id="76c4d-114">Microsoft Teams의 경우 테넌트 수준의 고객 키는 DEP가 테넌트에 할당된 시간부터 새 데이터를 암호화합니다.</span><span class="sxs-lookup"><span data-stu-id="76c4d-114">For Microsoft Teams, Customer Key at the tenant level encrypts new data from the time the DEP is assigned to the tenant.</span></span> <span data-ttu-id="76c4d-115">공개 미리 보기에서는 과거의 데이터 암호화를 지원하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="76c4d-115">Public preview does not support encrypting past data.</span></span> <span data-ttu-id="76c4d-116">Exchange Online의 경우 고객 키는 모든 기존 및 새 데이터를 암호화합니다.</span><span class="sxs-lookup"><span data-stu-id="76c4d-116">For Exchange Online, Customer Key encrypts all existing and new data.</span></span>

<span data-ttu-id="76c4d-117">테넌트당 여러 DEP를 만들 수 있지만 특정 시점에 하나의 DEP만 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="76c4d-117">You can create multiple DEPs per tenant but can only assign one DEP at any point in time.</span></span> <span data-ttu-id="76c4d-118">DEP를 할당하면 암호화가 자동으로 시작되지만 테넌트의 크기에 따라 완료하는 데 시간이 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="76c4d-118">When you assign the DEP, encryption begins automatically but can take some time to complete depending on the size of your tenant.</span></span>

## <a name="tenant-level-policies-add-broader-control-to-customer-key-for-microsoft-365"></a><span data-ttu-id="76c4d-119">테넌트 수준 정책은 Microsoft 365의 고객 키에 더 광범위한 제어를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="76c4d-119">Tenant level policies add broader control to Customer Key for Microsoft 365</span></span>

<span data-ttu-id="76c4d-120">Exchange Online 및 Sharepoint Online에 대해 이미 고객 키를 설정한 경우 새 테넌트 수준 공개 미리 보기가 어떻게 설정되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="76c4d-120">If you already have Customer Key set up for Exchange Online and Sharepoint Online, here's how the new tenant-level public preview fits in.</span></span>

<span data-ttu-id="76c4d-121">만든 테넌트 수준 암호화 정책은 Microsoft 365의 Microsoft Teams 및 Exchange Online 워크로드에 대한 모든 데이터를 암호화합니다.</span><span class="sxs-lookup"><span data-stu-id="76c4d-121">The tenant-level encryption policy you create encrypts all data for the Microsoft Teams and Exchange Online workloads in Microsoft 365.</span></span> <span data-ttu-id="76c4d-122">그러나 Exchange Online의 경우 개별 사서함에 이미 고객 키 DEP를 할당한 경우 테넌트 수준 정책은 해당 DEP를 다시 지정하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="76c4d-122">However, for Exchange Online, if you have already assigned Customer Key DEPs to individual mailboxes, the tenant-level policy won't override those DEPs.</span></span> <span data-ttu-id="76c4d-123">테넌트 수준 정책은 사서함 수준 고객 키 DEP가 아직 할당되지 않은 사서함만 암호화합니다.</span><span class="sxs-lookup"><span data-stu-id="76c4d-123">The tenant-level policy will only encrypt mailboxes that aren't assigned a mailbox level Customer Key DEP already.</span></span>

<span data-ttu-id="76c4d-124">예를 들어 비즈니스용 OneDrive 및 SharePoint에 저장된 Microsoft Teams 파일 및 일부 Teams 통화 및 모임 녹음/녹화는 SharePoint Online DEP에 의해 암호화됩니다.</span><span class="sxs-lookup"><span data-stu-id="76c4d-124">For example, Microsoft Teams files and some Teams call and meeting recordings that are saved in OneDrive for Business and SharePoint are encrypted by a SharePoint Online DEP.</span></span> <span data-ttu-id="76c4d-125">단일 SharePoint Online DEP는 단일 지리적으로 콘텐츠를 암호화합니다.</span><span class="sxs-lookup"><span data-stu-id="76c4d-125">A single SharePoint Online DEP encrypts content within a single geo.</span></span>

## <a name="set-up-customer-key-at-the-tenant-level-public-preview"></a><span data-ttu-id="76c4d-126">테넌트 수준에서 고객 키 설정(공개 미리 보기)</span><span class="sxs-lookup"><span data-stu-id="76c4d-126">Set up Customer Key at the tenant level (public preview)</span></span>

<span data-ttu-id="76c4d-127">이러한 단계는 응용 프로그램 수준에서 고객 키를 설정하는 단계와 비슷하지만 동일하지는 않습니다.</span><span class="sxs-lookup"><span data-stu-id="76c4d-127">These steps are similar but not identical to the steps for setting up Customer Key at the application level.</span></span> <span data-ttu-id="76c4d-128">이 공개 미리 보기는 테스트 테넌트의 테스트 데이터와 함께만 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="76c4d-128">You should only use this public preview with test data in test tenants.</span></span> <span data-ttu-id="76c4d-129">프로덕션 데이터나 프로덕션 환경에서는 이 릴리스를 사용하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="76c4d-129">Do not use this release with production data or in your production environment.</span></span> <span data-ttu-id="76c4d-130">고객 키의 프로덕션 배포가 이미 있는 경우 다음 단계를 사용하여 테스트 환경의 테넌트 수준에서 고객 키를 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="76c4d-130">If you already have a production deployment of Customer Key, use these steps to set up Customer Key at the tenant level in a test environment.</span></span>

<span data-ttu-id="76c4d-131">Azure PowerShell에 원격으로 연결하여 이러한 대부분의 작업을 완료합니다.</span><span class="sxs-lookup"><span data-stu-id="76c4d-131">You'll complete most of these tasks by remotely connecting to Azure PowerShell.</span></span> <span data-ttu-id="76c4d-132">최상의 결과를 얻기 위해 Azure PowerShell 버전 4.4.0 이상을 사용하세요.</span><span class="sxs-lookup"><span data-stu-id="76c4d-132">For best results, use version 4.4.0 or later of Azure PowerShell.</span></span>

<span data-ttu-id="76c4d-133">시작하기 전에 다음을 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="76c4d-133">Before you get started, make sure of the following:</span></span>

- <span data-ttu-id="76c4d-134">테넌트 수준에서 고객 키를 설정하려면 준수 관리자 역할이 있는 직장 또는 학교 계정을 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="76c4d-134">You'll need to use a work or school account that has the compliance admin role to set up Customer Key at the tenant level.</span></span>
- <span data-ttu-id="76c4d-135">조직에 적합한 라이선스가 있는지 확인</span><span class="sxs-lookup"><span data-stu-id="76c4d-135">Ensure that you have the appropriate licensing for your organization.</span></span> <span data-ttu-id="76c4d-136">구독 또는 클라우드 서비스 공급자를 사용하여 유료로 기업계약 Azure 구독을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="76c4d-136">Use a paid, invoiced Azure Subscription using either an Enterprise Agreement or a Cloud Service Provider.</span></span> <span data-ttu-id="76c4d-137">Pay As You Go 요금제 또는 신용 카드를 사용하여 구입한 Azure 구독은 고객 키에 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="76c4d-137">Azure Subscriptions purchased using Pay As You Go plans or using a credit card aren't supported for Customer Key.</span></span> <span data-ttu-id="76c4d-138">2020년 4월 1일부터 Office 365의 고객 키는 Office 365 E5, M365 E5, M365 E5 규정 준수 및 M365 E5 Information Protection & SKUS에서 제공됩니다.</span><span class="sxs-lookup"><span data-stu-id="76c4d-138">Starting April 1, 2020, Customer Key in Office 365 is offered in Office 365 E5, M365 E5, M365 E5 Compliance, and M365 E5 Information Protection & Governance SKUs.</span></span> <span data-ttu-id="76c4d-139">Office 365 Advanced Compliance SKU는 더 이상 새 라이선스를 조달할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="76c4d-139">Office 365 Advanced Compliance SKU is no longer available for procuring new licenses.</span></span> <span data-ttu-id="76c4d-140">기존 Office 365 고급 준수 라이선스는 계속 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="76c4d-140">Existing Office 365 Advanced Compliance licenses will continue to be supported.</span></span> <span data-ttu-id="76c4d-141">테넌트에 적절한 라이선스가 있는 테넌트에서 최소 하나의 라이선스로 서비스를 사용하도록 설정할 수 있는 반면, 서비스를 통해 혜택을 받은 모든 사용자에게 적절한 라이선스가 있는지 확인해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="76c4d-141">While the service can be enabled with a minimum of one license under the tenant having the appropriate license, you should still make sure all users that benefit from the service have appropriate licenses.</span></span>

### <a name="create-two-new-azure-subscriptions"></a><span data-ttu-id="76c4d-142">두 개의 새 Azure 구독 만들기</span><span class="sxs-lookup"><span data-stu-id="76c4d-142">Create two new Azure subscriptions</span></span>

<span data-ttu-id="76c4d-143">고객 키에는 각 DEP(데이터 암호화 정책)에 대해 두 개의 키가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="76c4d-143">Customer Key requires two keys for each data encryption policy (DEP).</span></span> <span data-ttu-id="76c4d-144">이를 위해서는 Azure 구독을 두 개 만들어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="76c4d-144">To achieve this, you must create two Azure subscriptions.</span></span> <span data-ttu-id="76c4d-145">조직의 개별 구성원이 각 구독에서 하나의 키를 구성하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="76c4d-145">As a best practice, Microsoft recommends that you have separate members of your organization configure one key in each subscription.</span></span> <span data-ttu-id="76c4d-146">이러한 Azure 구독만 사용하여 Microsoft 365의 암호화 키를 관리합니다.</span><span class="sxs-lookup"><span data-stu-id="76c4d-146">Only use these Azure subscriptions to administer encryption keys for Microsoft 365.</span></span> <span data-ttu-id="76c4d-147">이렇게 하여 운영자 중 한 명을 실수로, 의도적으로 또는 악의적으로 삭제하거나 책임이 있는 키를 잘못 관리한 경우 조직을 보호할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="76c4d-147">This protects your organization in case one of your operators accidentally, intentionally, or maliciously deletes or otherwise mismanages the keys for which they are responsible.</span></span>

<span data-ttu-id="76c4d-148">조직에 대해 만들 수 있는 Azure 구독 수에는 실질적인 제한이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="76c4d-148">There is no practical limit to the number of Azure subscriptions that you can create for your organization.</span></span> <span data-ttu-id="76c4d-149">이 모범 사례를 사용하면 사용자 오류의 영향을 최소화하면서 고객 키에서 사용하는 리소스를 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="76c4d-149">Following this best practice helps minimize the impact of human error while helping to manage the resources used by Customer Key.</span></span>

### <a name="register-azure-subscriptions-to-use-a-mandatory-retention-period"></a><span data-ttu-id="76c4d-150">필수 보존 기간을 사용하기 위해 Azure 구독 등록</span><span class="sxs-lookup"><span data-stu-id="76c4d-150">Register Azure subscriptions to use a mandatory retention period</span></span>

<span data-ttu-id="76c4d-151">루트 암호화 키의 일시적 또는 영구적 손실은 서비스 작업에 지장이나 심지어는 비극적일 수 있으며 데이터가 손실될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="76c4d-151">The temporary or permanent loss of root encryption keys can be disruptive or even catastrophic to service operation and can result in data loss.</span></span> <span data-ttu-id="76c4d-152">이러한 이유로 고객 키와 함께 사용되는 리소스에는 강력한 보호가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="76c4d-152">For this reason, the resources used with Customer Key require strong protection.</span></span> <span data-ttu-id="76c4d-153">고객 키와 함께 사용되는 모든 Azure 리소스는 기본 구성을 넘어 보호 메커니즘을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="76c4d-153">All the Azure resources that are used with Customer Key offer protection mechanisms beyond the default configuration.</span></span> <span data-ttu-id="76c4d-154">Azure 구독은 즉시 취소할 수 없는 취소를 방지하는 방식으로 태그를 지정하거나 등록할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="76c4d-154">Azure subscriptions can be tagged or registered in a way that will prevent immediate and irrevocable cancellation.</span></span> <span data-ttu-id="76c4d-155">이를 필수 보존 기간에 등록이라고 합니다.</span><span class="sxs-lookup"><span data-stu-id="76c4d-155">This is referred to as registering for a mandatory retention period.</span></span> <span data-ttu-id="76c4d-156">필수 보존 기간 동안 Azure 구독을 등록하는 데 필요한 단계는 Microsoft와 공동 작업해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="76c4d-156">The steps required to register Azure subscriptions for a mandatory retention period require collaboration with the Microsoft.</span></span> <span data-ttu-id="76c4d-157">이 프로세스는 영업일 5일까지 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="76c4d-157">This process can take up to five business days.</span></span> <span data-ttu-id="76c4d-158">이전에는 이 작업을 "취소 금지"라고도 합니다.</span><span class="sxs-lookup"><span data-stu-id="76c4d-158">Previously, this was sometimes referred to as "Do Not Cancel".</span></span>
  
<span data-ttu-id="76c4d-159">Microsoft 365 팀에 문의하기 전에 고객 키와 함께 사용하는 각 Azure 구독에 대해 다음 단계를 수행해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="76c4d-159">Before contacting the Microsoft 365 team, you must perform the following steps for each Azure subscription that you use with Customer Key.</span></span> <span data-ttu-id="76c4d-160">시작하기 전에 [Azure PowerShell Az](https://docs.microsoft.com/powershell/azure/new-azureps-module-az) 모듈을 설치해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="76c4d-160">Ensure that you have the [Azure PowerShell Az](https://docs.microsoft.com/powershell/azure/new-azureps-module-az) module installed before you start.</span></span>

1. <span data-ttu-id="76c4d-161">Azure PowerShell을 사용하여 로그인합니다.</span><span class="sxs-lookup"><span data-stu-id="76c4d-161">Sign in with Azure PowerShell.</span></span> <span data-ttu-id="76c4d-162">자세한 내용은 [Azure PowerShell로 로그인을 참조하세요.](https://docs.microsoft.com/powershell/azure/authenticate-azureps)</span><span class="sxs-lookup"><span data-stu-id="76c4d-162">For instructions, see [Sign in with Azure PowerShell](https://docs.microsoft.com/powershell/azure/authenticate-azureps).</span></span>

2. <span data-ttu-id="76c4d-163">Register-AzProviderFeature cmdlet을 실행하여 필수 보존 기간을 사용하기 위해 구독을 등록합니다.</span><span class="sxs-lookup"><span data-stu-id="76c4d-163">Run the Register-AzProviderFeature cmdlet to register your subscriptions to use a mandatory retention period.</span></span> <span data-ttu-id="76c4d-164">각 구독에 대해 이 작업을 수행하세요.</span><span class="sxs-lookup"><span data-stu-id="76c4d-164">Perform this action for each subscription.</span></span>

   ```powershell
   Set-AzContext -SubscriptionId <SubscriptionId>
   Register-AzProviderFeature -FeatureName mandatoryRetentionPeriodEnabled -ProviderNamespace Microsoft.Resources
   ```

3. <span data-ttu-id="76c4d-165">Microsoft에 문의하여 에서 프로세스를 [m365ck@microsoft.com.](mailto:m365ck@microsoft.com)</span><span class="sxs-lookup"><span data-stu-id="76c4d-165">Contact Microsoft to have the process finalized at [m365ck@microsoft.com](mailto:m365ck@microsoft.com).</span></span> <span data-ttu-id="76c4d-166">전자 메일에 다음을 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="76c4d-166">Include the following in your email:</span></span>

   <span data-ttu-id="76c4d-167">**제목:** 고객 키 \<*Your tenant's fully-qualified domain name*\></span><span class="sxs-lookup"><span data-stu-id="76c4d-167">**Subject**: Customer Key for \<*Your tenant's fully-qualified domain name*\></span></span>

   <span data-ttu-id="76c4d-168">**본문:** 필수 보존 기간을 마무리할 구독 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="76c4d-168">**Body**: Subscription IDs for which you want to have the mandatory retention period finalized.</span></span>
   <span data-ttu-id="76c4d-169">각 구독에 대한 Get-AzProviderFeature 출력입니다.</span><span class="sxs-lookup"><span data-stu-id="76c4d-169">The output of Get-AzProviderFeature for each subscription.</span></span>

   <span data-ttu-id="76c4d-170">이 프로세스 완료를 위한 SLA(서비스 수준 계약)는 Microsoft에 필수 보존 기간을 사용하기 위해 구독을 등록했다는 알림을(확인)한 후 영업일 5일입니다.</span><span class="sxs-lookup"><span data-stu-id="76c4d-170">The Service Level Agreement (SLA) for completion of this process is five business days once Microsoft has been notified (and verified) that you have registered your subscriptions to use a mandatory retention period.</span></span>

4. <span data-ttu-id="76c4d-171">Microsoft로부터 등록이 완료되었습니다는 알림을 받으면 다음과 같이 Get-AzProviderFeature 등록 상태를 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="76c4d-171">Once you receive notification from Microsoft that registration is complete, verify the status of your registration by running the Get-AzProviderFeature command as follows.</span></span> <span data-ttu-id="76c4d-172">확인되면 Get-AzProviderFeature 명령은 Registration State 속성에 **대해 Registered** 값을 **반환합니다.**</span><span class="sxs-lookup"><span data-stu-id="76c4d-172">If verified, the Get-AzProviderFeature command returns a value of **Registered** for the **Registration State** property.</span></span> <span data-ttu-id="76c4d-173">각 구독에 대해 이 작업을 수행하세요.</span><span class="sxs-lookup"><span data-stu-id="76c4d-173">Perform this action for each subscription.</span></span>

   ```powershell
   Set-AzContext -SubscriptionId <SubscriptionId>
   Get-AzProviderFeature -ProviderNamespace Microsoft.Resources -FeatureName mandatoryRetentionPeriodEnabled
   ```

5. <span data-ttu-id="76c4d-174">프로세스를 완료하기 위해 Register-AzResourceProvider 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="76c4d-174">To complete the process, run the Register-AzResourceProvider command.</span></span> <span data-ttu-id="76c4d-175">각 구독에 대해 이 작업을 수행하세요.</span><span class="sxs-lookup"><span data-stu-id="76c4d-175">Perform this action for each subscription.</span></span>

   ```powershell
   Set-AzContext -SubscriptionId <SubscriptionId>
   Register-AzResourceProvider -ProviderNamespace Microsoft.KeyVault
   ```

### <a name="create-a-premium-azure-key-vault-in-each-subscription"></a><span data-ttu-id="76c4d-176">각 구독에서 프리미엄 Azure Key Vault 만들기</span><span class="sxs-lookup"><span data-stu-id="76c4d-176">Create a premium Azure Key Vault in each subscription</span></span>

<span data-ttu-id="76c4d-177">키 저장소를 만드는 단계는 Azure PowerShell 설치 및 시작, Azure 구독에 연결, 리소스 그룹 만들기 및 해당 리소스 그룹에 키 자격 증명 모음 만들기를 안내하는 [Azure Key Vault](https://azure.microsoft.com/documentation/articles/key-vault-get-started/)시작에 설명되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="76c4d-177">The steps to create a key vault are documented in [Getting Started with Azure Key Vault](https://azure.microsoft.com/documentation/articles/key-vault-get-started/), which guides you through installing and launching Azure PowerShell, connecting to your Azure subscription, creating a resource group, and creating a key vault in that resource group.</span></span>
  
<span data-ttu-id="76c4d-178">키 자격 증명 모음을 만들 때 SKU(Standard 또는 Premium)를 선택해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="76c4d-178">When you create a key vault, you must choose a SKU: either Standard or Premium.</span></span> <span data-ttu-id="76c4d-179">Standard SKU를 사용하면 Azure Key Vault 키를 소프트웨어로 보호할 수 있으며, HSM(하드웨어 보안 모듈) 키 보호가 없습니다. Premium SKU는 키 자격 증명 모음 키를 보호하기 위해 HSM을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="76c4d-179">The Standard SKU allows Azure Key Vault keys to be protected with software - there is no Hardware Security Module (HSM) key protection - and the Premium SKU allows the use of HSMs for protection of Key Vault keys.</span></span> <span data-ttu-id="76c4d-180">Customer Key는 두 SKU 중 하나를 사용하는 주요 자격 증명 모음을 허용합니다. 그러나 Microsoft는 Premium SKU만 사용하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="76c4d-180">Customer Key accepts key vaults that use either SKU, though Microsoft strongly recommends that you use only the Premium SKU.</span></span> <span data-ttu-id="76c4d-181">두 형식의 키 중 하나를 사용하는 작업의 비용은 동일하기 때문에 비용의 유일한 차이점은 각 HSM으로 보호되는 키에 대한 월별 비용입니다.</span><span class="sxs-lookup"><span data-stu-id="76c4d-181">The cost of operations with keys of either type is the same, so the only difference in cost is the cost per month for each HSM-protected key.</span></span> <span data-ttu-id="76c4d-182">자세한 [내용은 Key Vault 가격을](https://azure.microsoft.com/pricing/details/key-vault/) 참조합니다.</span><span class="sxs-lookup"><span data-stu-id="76c4d-182">See [Key Vault pricing](https://azure.microsoft.com/pricing/details/key-vault/) for details.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="76c4d-183">프로덕션 데이터에는 Premium SKU 키 자격 증명 모음 및 HSM으로 보호된 키를 사용하며 테스트 및 유효성 검사를 위해 표준 SKU 키 자격 증명 모음 및 키만 사용하십시오.</span><span class="sxs-lookup"><span data-stu-id="76c4d-183">Use the Premium SKU key vaults and HSM-protected keys for production data, and only use Standard SKU key vaults and keys for testing and validation purposes.</span></span>

<span data-ttu-id="76c4d-184">키 자격 증명 모음에 공통적인 도형을 사용하며 키 자격 증명 모음 및 키의 사용 및 범위에 대한 약어를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="76c4d-184">Use a common prefix for key vaults and include an abbreviation of the use and scope of the key vault and keys.</span></span> <span data-ttu-id="76c4d-185">예를 들어 북미에 자격 증명 모음이 위치할 Contoso 서비스의 경우 가능한 이름 쌍은 Contoso-O365-NA-VaultA1 및 Contoso-O365-NA-VaultA2입니다.</span><span class="sxs-lookup"><span data-stu-id="76c4d-185">For example, for the Contoso service where the vaults will be located in North America, a possible pair of names is Contoso-O365-NA-VaultA1 and Contoso-O365-NA-VaultA2.</span></span> <span data-ttu-id="76c4d-186">자격 증명 모음 이름은 Azure 내에서 전역적으로 고유한 문자열이기 때문에 다른 Azure 고객이 원하는 이름을 이미 클레임할 경우 원하는 이름을 변형해 보아야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="76c4d-186">Vault names are globally unique strings within Azure, so you may need to try variations of your desired names in case the desired names are already claimed by other Azure customers.</span></span> <span data-ttu-id="76c4d-187">구성한 자격 증명 모음 이름은 변경할 수 없습니다. 따라서 모범 사례는 설치에 대한 서면 계획을 세우고 두 번째 사람을 사용하여 계획이 올바르게 실행되고 있는지 확인하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="76c4d-187">Once configured, vault names cannot be changed, so the best practice is to have a written plan for setup and use a second person to verify the plan is executed correctly.</span></span>

<span data-ttu-id="76c4d-188">가능한 경우 페어링되지 않은 지역에서 자격 증명 모음을 만드십시오.</span><span class="sxs-lookup"><span data-stu-id="76c4d-188">If possible, create your vaults in non-paired regions.</span></span> <span data-ttu-id="76c4d-189">페어링된 Azure 지역은 서비스 오류 도메인 전체에서 고가용성을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="76c4d-189">Paired Azure regions provide high availability across service failure domains.</span></span> <span data-ttu-id="76c4d-190">따라서 지역 쌍은 서로의 백업 지역으로 생각할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="76c4d-190">Therefore, regional pairs can be thought of as each other's backup region.</span></span> <span data-ttu-id="76c4d-191">즉, 한 지역에 배치된 Azure 리소스가 페어링된 지역을 통해 내결결성을 자동으로 얻게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="76c4d-191">This means that an Azure resource that is placed in one region is automatically gaining fault tolerance through the paired region.</span></span> <span data-ttu-id="76c4d-192">이러한 이유로 지역이 쌍을 이루는 데이터 암호화 정책에서 사용되는 두 자격 증명 모음에 대한 지역을 선택하면 총 2개의 가용성 영역만 사용 중입니다.</span><span class="sxs-lookup"><span data-stu-id="76c4d-192">For this reason, choosing regions for two vaults used in a data encryption policy where the regions are paired means that only a total of two regions of availability are in use.</span></span> <span data-ttu-id="76c4d-193">대부분의 지역에는 두 개의 지역만 있으므로 페어링되지 않은 지역을 선택할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="76c4d-193">Most geographies only have two regions, so it's not yet possible to select non-paired regions.</span></span> <span data-ttu-id="76c4d-194">가능한 경우 데이터 암호화 정책과 함께 사용되는 두 자격 증명 모음에 대해 쌍으로 설정되지 않은 두 지역을 선택하세요.</span><span class="sxs-lookup"><span data-stu-id="76c4d-194">If possible, choose two non-paired regions for the two vaults used with a data encryption policy.</span></span> <span data-ttu-id="76c4d-195">이 혜택은 총 4개의 가용성 영역의 이점입니다.</span><span class="sxs-lookup"><span data-stu-id="76c4d-195">This benefits from a total of four regions of availability.</span></span> <span data-ttu-id="76c4d-196">자세한 내용은 비즈니스 연속성 및 재해 [복구(BCDR): 현재](https://docs.microsoft.com/azure/best-practices-availability-paired-regions) 지역 쌍 목록은 Azure 페어링 지역을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="76c4d-196">For more information, see [Business continuity and disaster recovery (BCDR): Azure Paired Regions](https://docs.microsoft.com/azure/best-practices-availability-paired-regions) for a current list of regional pairs.</span></span>

### <a name="assign-permissions-to-each-key-vault"></a><span data-ttu-id="76c4d-197">각 키 자격 증명 모음에 사용 권한 할당</span><span class="sxs-lookup"><span data-stu-id="76c4d-197">Assign permissions to each key vault</span></span>

<span data-ttu-id="76c4d-198">각 키 자격 증명 모음에 대해 구현에 따라 고객 키에 대한 세 가지 사용 권한 집합을 정의해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="76c4d-198">For each key vault, you will need to define three separate sets of permissions for Customer Key, depending on your implementation.</span></span> <span data-ttu-id="76c4d-199">예를 들어 다음 각 권한 집합에 대해 하나의 사용 권한 집합을 정의해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="76c4d-199">For example, you will need to define one set of permissions for each of the following:</span></span>
  
- <span data-ttu-id="76c4d-200">**조직의 키** 자격 증명 모음에 대한 매일 관리를 수행하는 주요 자격 증명 모음 관리자</span><span class="sxs-lookup"><span data-stu-id="76c4d-200">**Key vault administrators** that will perform day-to-day management of your key vault for your organization.</span></span> <span data-ttu-id="76c4d-201">이러한 작업에는 백업, 만들기, 가져오기, 가져오기, 목록 및 복원이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="76c4d-201">These tasks include backup, create, get, import, list, and restore.</span></span>

  > [!IMPORTANT]
  > <span data-ttu-id="76c4d-202">키 자격 증명 모음 관리자에게 할당된 권한 집합에는 키를 삭제할 수 있는 권한이 포함되어 있지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="76c4d-202">The set of permissions assigned to key vault administrators does not include the permission to delete keys.</span></span> <span data-ttu-id="76c4d-203">이는 의도적인 것이고 중요한 사례입니다.</span><span class="sxs-lookup"><span data-stu-id="76c4d-203">This is intentional and an important practice.</span></span> <span data-ttu-id="76c4d-204">암호화 키를 삭제하면 데이터가 영구적으로 삭제되는 것이 일반적이지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="76c4d-204">Deleting encryption keys is not typically done, since doing so permanently destroys data.</span></span> <span data-ttu-id="76c4d-205">이 권한은 기본적으로 주요 자격 증명 모음 관리자에게 부여하지 않는 것이 가장 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="76c4d-205">As a best practice, do not grant this permission to key vault administrators by default.</span></span> <span data-ttu-id="76c4d-206">대신 주요 자격 증명 모음 참가자에 대해 이 정보를 예약하고 결과에 대한 명확한 이해가 있는 경우 단기적으로 관리자에게 할당해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="76c4d-206">Instead, reserve this for key vault contributors and only assign it to an administrator on a short term basis once a clear understanding of the consequences is understood.</span></span>
  
  <span data-ttu-id="76c4d-207">조직의 사용자에게 이러한 권한을 할당하려면 Azure PowerShell을 사용하여 Azure 구독에 로그인합니다.</span><span class="sxs-lookup"><span data-stu-id="76c4d-207">To assign these permissions to a user in your organization, log in to your Azure subscription with Azure PowerShell.</span></span> <span data-ttu-id="76c4d-208">자세한 내용은 [Azure PowerShell로 로그인을 참조하세요.](https://docs.microsoft.com/powershell/azure/authenticate-azureps)</span><span class="sxs-lookup"><span data-stu-id="76c4d-208">For instructions, see [Sign in with Azure PowerShell](https://docs.microsoft.com/powershell/azure/authenticate-azureps).</span></span>

   <span data-ttu-id="76c4d-209">Set-AzKeyVaultAccessPolicy cmdlet을 실행하여 필요한 사용 권한을 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="76c4d-209">Run the Set-AzKeyVaultAccessPolicy cmdlet to assign the necessary permissions.</span></span>

   ```powershell
   Set-AzKeyVaultAccessPolicy -VaultName <vault name> -UserPrincipalName <UPN of user> -PermissionsToKeys create,import,list,get,backup,restore
   ```

   <span data-ttu-id="76c4d-210">예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="76c4d-210">For example:</span></span>

   ```powershell
   Set-AzKeyVaultAccessPolicy -VaultName Contoso-O365EX-NA-VaultA1 -UserPrincipalName alice@contoso.com -PermissionsToKeys create,import,list,get,backup,restore
   ```

- <span data-ttu-id="76c4d-211">Azure **Key Vault** 자체에 대한 사용 권한을 변경할 수 있는 주요 자격 증명 모음 참가자입니다.</span><span class="sxs-lookup"><span data-stu-id="76c4d-211">**Key vault contributors** that can change permissions on the Azure Key Vault itself.</span></span> <span data-ttu-id="76c4d-212">직원이 팀을 떠나거나 팀에 합류할 때 또는 키 자격 증명 모음 관리자가 키를 삭제하거나 복원할 수 있는 권한이 필요한 드문 경우 이러한 권한을 변경해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="76c4d-212">You'll need to change these permissions as employees leave or join your team, or in the rare situation that the key vault administrators legitimately need permission to delete or restore a key.</span></span> <span data-ttu-id="76c4d-213">이 주요 자격 증명 모음 참가자 집합에는 키 자격 증명 모음에 대한 참가자 역할을 부여해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="76c4d-213">This set of key vault contributors needs to be granted the Contributor role on your key vault.</span></span> <span data-ttu-id="76c4d-214">Azure Resource Manager를 사용하여 이 역할을 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="76c4d-214">You can assign this role by using Azure Resource Manager.</span></span> <span data-ttu-id="76c4d-215">자세한 단계는 Role-Based [액세스](https://docs.microsoft.com/azure/active-directory/role-based-access-control-configure) 제어를 사용하여 Azure 구독 리소스에 대한 액세스를 관리하기를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="76c4d-215">For detailed steps, see [Use Role-Based Access Control](https://docs.microsoft.com/azure/active-directory/role-based-access-control-configure) to manage access to your Azure subscription resources.</span></span> <span data-ttu-id="76c4d-216">구독을 만드는 관리자는 기본적으로 이 액세스 권한과 참가자 역할에 다른 관리자를 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="76c4d-216">The administrator who creates a subscription has this access by default, and the ability to assign other administrators to the Contributor role.</span></span>

- <span data-ttu-id="76c4d-217">테넌트 수준에서 고객 키의 작업을 하는 미사용 암호화 서비스의 **Microsoft 365** 데이터입니다.</span><span class="sxs-lookup"><span data-stu-id="76c4d-217">**Microsoft 365 data at rest encryption service** that does the work of Customer Key at the tenant level.</span></span> <span data-ttu-id="76c4d-218">Microsoft 365에 대한 사용 권한을 부여하려면 다음 구문을 사용하여 **Set-AzKeyVaultAccessPolicy** cmdlet을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="76c4d-218">To give permission to Microsoft 365, run the **Set-AzKeyVaultAccessPolicy** cmdlet using the following syntax:</span></span>

   ```powershell
   Set-AzKeyVaultAccessPolicy -VaultName <vault name> -PermissionsToKeys wrapKey,unwrapKey,get -ServicePrincipalName <Microsoft 365 appID>
   ```

  <span data-ttu-id="76c4d-219">여기서,</span><span class="sxs-lookup"><span data-stu-id="76c4d-219">Where:</span></span>

  - <span data-ttu-id="76c4d-220">*자격 증명 모음* 이름은 만든 키 자격 증명 모음의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="76c4d-220">*vault name* is the name of the key vault you created.</span></span>

  <span data-ttu-id="76c4d-221">예: Rest 암호화 서비스의 Microsoft 365 데이터에서 *Microsoft 365 appID를*`c066d759-24ae-40e7-a56f-027002b5d3e4`</span><span class="sxs-lookup"><span data-stu-id="76c4d-221">Example: For the Microsoft 365 Data at Rest Encryption service, replace  *Microsoft 365 appID* with `c066d759-24ae-40e7-a56f-027002b5d3e4`</span></span>

  ```powershell
  Set-AzKeyVaultAccessPolicy -VaultName Contoso-O365EX-NA-VaultA1 -PermissionsToKeys wrapKey,unwrapKey,get -ServicePrincipalName c066d759-24ae-40e7-a56f-027002b5d3e4
  ```

### <a name="enable-and-then-confirm-soft-delete-on-your-key-vaults"></a><span data-ttu-id="76c4d-222">키 자격 증명 모음에서 소프트 삭제를 사용하도록 설정한 다음 확인</span><span class="sxs-lookup"><span data-stu-id="76c4d-222">Enable and then confirm soft delete on your key vaults</span></span>

<span data-ttu-id="76c4d-223">키를 빠르게 복구할 수 있는 경우 실수로 또는 악의적으로 삭제된 키로 인해 확장된 서비스가 사용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="76c4d-223">When you can quickly recover your keys, you are less likely to experience an extended service outage due to accidentally or maliciously deleted keys.</span></span> <span data-ttu-id="76c4d-224">고객 키와 함께 키를 사용하려면 먼저 소프트 삭제라고 하는 이 구성을 사용하도록 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="76c4d-224">Enable this configuration, referred to as Soft Delete, before you can use your keys with Customer Key.</span></span> <span data-ttu-id="76c4d-225">소프트 삭제를 사용하도록 설정하면 백업에서 복원하지 않고도 삭제 후 90일 이내에 키나 자격 증명 모음을 복구할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="76c4d-225">Enabling Soft Delete allows you to recover keys or vaults within 90 days of deletion without having to restore them from backup.</span></span>
  
<span data-ttu-id="76c4d-226">키 자격 증명 모음에서 소프트 삭제를 사용하도록 설정하려면 다음 단계를 완료합니다.</span><span class="sxs-lookup"><span data-stu-id="76c4d-226">To enable Soft Delete on your key vaults, complete these steps:</span></span>
  
1. <span data-ttu-id="76c4d-227">구독을 사용하여 Azure 구독에 Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="76c4d-227">Sign in to your Azure subscription with Windows PowerShell.</span></span> <span data-ttu-id="76c4d-228">자세한 내용은 [Azure PowerShell로 로그인을 참조하세요.](https://docs.microsoft.com/powershell/azure/authenticate-azureps)</span><span class="sxs-lookup"><span data-stu-id="76c4d-228">For instructions, see [Sign in with Azure PowerShell](https://docs.microsoft.com/powershell/azure/authenticate-azureps).</span></span>

2. <span data-ttu-id="76c4d-229">[Get-AzKeyVault](https://docs.microsoft.com/powershell/module/az.keyvault/get-azkeyvault) cmdlet을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="76c4d-229">Run the [Get-AzKeyVault](https://docs.microsoft.com/powershell/module/az.keyvault/get-azkeyvault) cmdlet.</span></span> <span data-ttu-id="76c4d-230">이 예에서 자격 증명 모음 *이름은* 소프트 삭제를 사용하도록 설정하는 키 자격 증명 모음의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="76c4d-230">In this example, *vault name* is the name of the key vault for which you are enabling soft delete:</span></span>

   ```powershell
   $v = Get-AzKeyVault -VaultName <vault name>
   $r = Get-AzResource -ResourceId $v.ResourceId
   $r.Properties | Add-Member -MemberType NoteProperty -Name enableSoftDelete -Value 'True'
   Set-AzResource -ResourceId $r.ResourceId -Properties $r.Properties
   ```

3. <span data-ttu-id="76c4d-231">**Get-AzKeyVault** cmdlet을 실행하여 키 자격 증명 모음에 대해 소프트 삭제가 구성되어 있는지 확인</span><span class="sxs-lookup"><span data-stu-id="76c4d-231">Confirm soft delete is configured for the key vault by running the **Get-AzKeyVault** cmdlet.</span></span> <span data-ttu-id="76c4d-232">키 자격 증명 모음에 대해 소프트 삭제가 제대로 구성되어 있는 경우 _Soft Delete Enabled_ 속성은 True 값을 **반환합니다.**</span><span class="sxs-lookup"><span data-stu-id="76c4d-232">If soft delete is configured properly for the key vault, then the _Soft Delete Enabled_ property returns a value of **True**:</span></span>

   ```powershell
   Get-AzKeyVault -VaultName <vault name> | fl
   ```

### <a name="add-a-key-to-each-key-vault-either-by-creating-or-importing-a-key"></a><span data-ttu-id="76c4d-233">키를 만들거나 가져와서 각 키 자격 증명 모음에 키 추가</span><span class="sxs-lookup"><span data-stu-id="76c4d-233">Add a key to each key vault either by creating or importing a key</span></span>

<span data-ttu-id="76c4d-234">Azure Key Vault에 키를 추가하는 방법에는 두 가지가 있습니다. 키 자격 증명 모음에서 직접 키를 만들거나 키를 가져올 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="76c4d-234">There are two ways to add keys to an Azure Key Vault; you can create a key directly in Key Vault, or you can import a key.</span></span> <span data-ttu-id="76c4d-235">키 자격 증명 모음에서 직접 키를 만드는 것은 덜 복잡하지만 키를 가져오면 키 생성 방법을 완전히 제어할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="76c4d-235">Creating a key directly in Key Vault is the less complicated method, while importing a key provides total control over how the key is generated.</span></span> <span data-ttu-id="76c4d-236">RSA 키를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="76c4d-236">Use the RSA keys.</span></span> <span data-ttu-id="76c4d-237">Azure Key Vault는 타원 곡선 키로 래핑 및 래핑을 지원하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="76c4d-237">Azure Key Vault doesn't support wrapping and unwrapping with elliptical curve keys.</span></span>
  
<span data-ttu-id="76c4d-238">키 자격 증명 모음에서 직접 키를 만들 수 있도록 [Add-AzKeyVaultKey](https://docs.microsoft.com/powershell/module/az.keyvault/add-azkeyvaultkey) cmdlet을 다음과 같이 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="76c4d-238">To create a key directly in your key vault, run the [Add-AzKeyVaultKey](https://docs.microsoft.com/powershell/module/az.keyvault/add-azkeyvaultkey) cmdlet as follows:</span></span>
  
```powershell
Add-AzKeyVaultKey -VaultName <vault name> -Name <key name> -Destination <HSM|Software> -KeyOps wrapKey,unwrapKey
```

<span data-ttu-id="76c4d-239">여기서,</span><span class="sxs-lookup"><span data-stu-id="76c4d-239">Where:</span></span>

- <span data-ttu-id="76c4d-240">*자격 증명* 모음 이름은 키를 만들 키 자격 증명 모음의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="76c4d-240">*vault name* is the name of the key vault in which you want to create the key.</span></span>

- <span data-ttu-id="76c4d-241">*key name은* 새 키를 제공하려는 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="76c4d-241">*key name* is the name you want to give the new key.</span></span>

  > [!TIP]
  > <span data-ttu-id="76c4d-242">키 자격 증명 모음에 대해 위에서 설명한 대로 유사한 명명 규칙을 사용하는 이름 키입니다.</span><span class="sxs-lookup"><span data-stu-id="76c4d-242">Name keys using a similar naming convention as described above for key vaults.</span></span> <span data-ttu-id="76c4d-243">이렇게 하면 키 이름만 표시하는 도구에서 문자열은 자체 설명을 합니다.</span><span class="sxs-lookup"><span data-stu-id="76c4d-243">This way, in tools that show only the key name, the string is self-describing.</span></span>
  
<span data-ttu-id="76c4d-244">HSM으로 키를 보호하려는 경우 **HSM을** _Destination_ 매개 변수 값으로 지정해야 합니다. 그렇지 않으면 Software 를 **지정합니다.**</span><span class="sxs-lookup"><span data-stu-id="76c4d-244">If you intend to protect the key with an HSM, ensure that you specify **HSM** as the value of the _Destination_ parameter, otherwise, specify **Software**.</span></span>

<span data-ttu-id="76c4d-245">예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="76c4d-245">For example,</span></span>
  
```powershell
Add-AzKeyVaultKey -VaultName Contoso-O365EX-NA-VaultA1 -Name Contoso-O365EX-NA-VaultA1-Key001 -Destination HSM -KeyOps wrapKey,unwrapKey
```

### <a name="check-the-recovery-level-of-your-keys"></a><span data-ttu-id="76c4d-246">키의 복구 수준 확인</span><span class="sxs-lookup"><span data-stu-id="76c4d-246">Check the recovery level of your keys</span></span>

<span data-ttu-id="76c4d-247">Microsoft 365를 사용하려면 Azure Key Vault 구독이 취소 금지로 설정되어 있으며 고객 키에서 사용하는 키가 소프트 삭제를 사용하도록 설정되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="76c4d-247">Microsoft 365 requires that the Azure Key Vault subscription is set to Do Not Cancel and that the keys used by Customer Key have soft delete enabled.</span></span> <span data-ttu-id="76c4d-248">키의 복구 수준을 확인하여 이를 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="76c4d-248">You can confirm this by looking at the recovery level on your keys.</span></span>
  
<span data-ttu-id="76c4d-249">키의 복구 수준을 확인하기 위해 Azure PowerShell에서 다음과 Get-AzKeyVaultKey cmdlet을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="76c4d-249">To check the recovery level of a key, in Azure PowerShell, run the Get-AzKeyVaultKey cmdlet as follows:</span></span>
  
```powershell
(Get-AzKeyVaultKey -VaultName <vault name> -Name <key name>).Attributes
```

<span data-ttu-id="76c4d-250">Recovery _Level_ 속성이 **Recoverable+ProtectedSubscription** 값 외의 값을 반환하는 경우 이 문서를 검토하고 취소 금지 목록에 구독을 추가하고 각 키 자격 증명 모음에서 "소프트 삭제"를 사용하도록 설정한 모든 단계를 따라야 합니다.</span><span class="sxs-lookup"><span data-stu-id="76c4d-250">If the _Recovery Level_ property returns anything other than a value of **Recoverable+ProtectedSubscription**, you will need to review this article and ensure that you have followed all of the steps to put the subscription on the Do Not Cancel list and that you enabled "soft delete" on each of your key vaults.</span></span> <span data-ttu-id="76c4d-251">다음으로, 전자 메일의 출력 스크린샷을 `(Get-AzKeyVaultKey -VaultName <vault name> -Name <key name>).Attributes` m365ck@microsoft.com.</span><span class="sxs-lookup"><span data-stu-id="76c4d-251">Next, send a screenshot of the output of `(Get-AzKeyVaultKey -VaultName <vault name> -Name <key name>).Attributes` in email to m365ck@microsoft.com.</span></span>

### <a name="back-up-azure-key-vault"></a><span data-ttu-id="76c4d-252">Azure Key Vault 백업</span><span class="sxs-lookup"><span data-stu-id="76c4d-252">Back up Azure Key Vault</span></span>

<span data-ttu-id="76c4d-253">키가 만들어지거나 키가 변경된 직후 백업을 수행하고 온라인 및 오프라인으로 백업 복사본을 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="76c4d-253">Immediately following creation or any change to a key, perform a backup and store copies of the backup, both online and offline.</span></span> <span data-ttu-id="76c4d-254">오프라인 복사본을 네트워크에 연결하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="76c4d-254">Don't connect offline copies to any network.</span></span> <span data-ttu-id="76c4d-255">대신 물리적 안전 또는 상업적 저장소 시설에 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="76c4d-255">Instead, store them in a physical safe or commercial storage facility.</span></span> <span data-ttu-id="76c4d-256">재해가 발생할 경우 액세스할 수 있는 위치에 백업 복사본을 하나 이상 저장해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="76c4d-256">At least one copy of the backup should be stored in a location that will be accessible if a disaster happens.</span></span> <span data-ttu-id="76c4d-257">키 자격 증명 키를 영구적으로 삭제하거나 사용할 수 없는 경우 백업 Blob은 키 자료를 복원하는 유일한 수단입니다.</span><span class="sxs-lookup"><span data-stu-id="76c4d-257">The backup blobs are the sole means of restoring key material should a Key Vault key be permanently destroyed or otherwise rendered inoperable.</span></span> <span data-ttu-id="76c4d-258">Azure Key Vault 외부에서 Azure Key Vault로 가져온 키는 고객 키가 키를 사용하는 데 필요한 메타데이터가 외부 키와 함께 존재하지 않는 때문에 백업으로 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="76c4d-258">Keys that are external to Azure Key Vault and were imported to Azure Key Vault do not qualify as a backup because the metadata necessary for Customer Key to use the key does not exist with the external key.</span></span> <span data-ttu-id="76c4d-259">Azure Key Vault에서 수행한 백업만 고객 키를 사용하여 복원 작업에 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="76c4d-259">Only a backup taken from Azure Key Vault can be used for restore operations with Customer Key.</span></span> <span data-ttu-id="76c4d-260">따라서 키를 업로드하거나 만든 후 Azure Key Vault의 백업을 만들어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="76c4d-260">Therefore, it is essential that you make a backup of Azure Key Vault once a key is uploaded or created.</span></span>
  
<span data-ttu-id="76c4d-261">Azure Key Vault 키의 백업을 만들 경우 다음과 같이 [Backup-AzKeyVaultKey](https://docs.microsoft.com/powershell/module/az.keyvault/backup-azkeyvaultkey) cmdlet을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="76c4d-261">To create a backup of an Azure Key Vault key, run the [Backup-AzKeyVaultKey](https://docs.microsoft.com/powershell/module/az.keyvault/backup-azkeyvaultkey) cmdlet as follows:</span></span>

```powershell
Backup-AzKeyVaultKey -VaultName <vault name> -Name <key name>
-OutputFile <filename.backup>
```

<span data-ttu-id="76c4d-262">출력 파일에서 접미사 를 사용하는지 `.backup` 확인</span><span class="sxs-lookup"><span data-stu-id="76c4d-262">Ensure that your output file uses the suffix `.backup`.</span></span>
  
<span data-ttu-id="76c4d-263">이 cmdlet에서 생성되는 출력 파일은 암호화되며 Azure Key Vault 외부에서 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="76c4d-263">The output file resulting from this cmdlet is encrypted and cannot be used outside of Azure Key Vault.</span></span> <span data-ttu-id="76c4d-264">백업은 백업을 수행한 Azure 구독으로만 복원할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="76c4d-264">The backup can be restored only to the Azure subscription from which the backup was taken.</span></span>
  
<span data-ttu-id="76c4d-265">예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="76c4d-265">For example:</span></span>
  
```powershell
Backup-AzKeyVaultKey -VaultName Contoso-O365EX-NA-VaultA1 -Name Contoso-O365EX-NA-VaultA1-Key001 -OutputFile Contoso-O365EX-NA-VaultA1-Key001-Backup-20170802.backup
```

### <a name="validate-azure-key-vault-configuration-settings"></a><span data-ttu-id="76c4d-266">Azure Key Vault 구성 설정 유효성 검사</span><span class="sxs-lookup"><span data-stu-id="76c4d-266">Validate Azure Key Vault configuration settings</span></span>

<span data-ttu-id="76c4d-267">DEP에서 키를 사용하기 전에 유효성 검사를 수행하는 것은 선택 사항이지만 매우 권장됩니다.</span><span class="sxs-lookup"><span data-stu-id="76c4d-267">Performing validation before using keys in a DEP is optional, but highly recommended.</span></span> <span data-ttu-id="76c4d-268">특히 이 항목에 설명된 키와 자격 증명 모음이 다른 키와 자격 증명 모음을 설정하는 단계를 사용하는 경우 고객 키를 구성하기 전에 Azure Key Vault 리소스의 상태 유효성을 검사해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="76c4d-268">In particular, if you use steps to set up your keys and vaults other than the ones described in this topic, you should validate the health of your Azure Key Vault resources before you configure Customer Key.</span></span>
  
<span data-ttu-id="76c4d-269">키가 get, wrapKey 및 unwrapKey 작업을 사용하도록 설정되어 있는지 확인:</span><span class="sxs-lookup"><span data-stu-id="76c4d-269">To verify that your keys have get, wrapKey, and unwrapKey operations enabled:</span></span>
  
<span data-ttu-id="76c4d-270">다음과 [같이 Get-AzKeyVault](https://docs.microsoft.com/powershell/module/az.keyvault/get-azkeyvault) cmdlet을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="76c4d-270">Run the [Get-AzKeyVault](https://docs.microsoft.com/powershell/module/az.keyvault/get-azkeyvault) cmdlet as follows:</span></span>
  
```powershell
Get-AzKeyVault -VaultName <vault name>
```

<span data-ttu-id="76c4d-271">출력에서 액세스 정책과 Microsoft 365 앱 ID(GUID)를 적절하게 찾아 봐야 합니다.</span><span class="sxs-lookup"><span data-stu-id="76c4d-271">In the output, look for the Access Policy and for the Microsoft 365 app ID (GUID) as appropriate.</span></span> <span data-ttu-id="76c4d-272">get, wrapKey 및 unwrapKey의 세 가지 작업은 모두 키에 대한 사용 권한 아래에 표시되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="76c4d-272">All three operations, get, wrapKey, and unwrapKey, must be shown under Permissions to Keys.</span></span>
  
<span data-ttu-id="76c4d-273">액세스 정책 구성이 올바르지 않은 경우 다음과 Set-AzKeyVaultAccessPolicy cmdlet을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="76c4d-273">If the access policy configuration is incorrect, run the Set-AzKeyVaultAccessPolicy cmdlet as follows:</span></span>
  
```powershell
Set-AzKeyVaultAccessPolicy -VaultName <vault name> -PermissionsToKeys wrapKey,unwrapKey,get -ServicePrincipalName <Microsoft 365 appID>
```

<span data-ttu-id="76c4d-274">예: Rest 암호화 서비스의 Microsoft 365 데이터에서 *Microsoft 365 appID를*`c066d759-24ae-40e7-a56f-027002b5d3e4`</span><span class="sxs-lookup"><span data-stu-id="76c4d-274">Example: For the Microsoft 365 Data at Rest Encryption service, replace  *Microsoft 365 appID* with `c066d759-24ae-40e7-a56f-027002b5d3e4`</span></span>

  ```powershell
  Set-AzKeyVaultAccessPolicy -VaultName Contoso-O365EX-NA-VaultA1 -PermissionsToKeys wrapKey,unwrapKey,get -ServicePrincipalName c066d759-24ae-40e7-a56f-027002b5d3e4
  ```

<span data-ttu-id="76c4d-275">키에 대한 만료 날짜가 설정되어 있지 않은지 확인하기 위해 다음과 같이 [Get-AzKeyVaultKey](https://docs.microsoft.com/powershell/module/az.keyvault/get-azkeyvault) cmdlet을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="76c4d-275">To verify that an expiration date is not set for your keys, run the [Get-AzKeyVaultKey](https://docs.microsoft.com/powershell/module/az.keyvault/get-azkeyvault) cmdlet as follows:</span></span>
  
```powershell
Get-AzKeyVaultKey -VaultName <vault name>
```

<span data-ttu-id="76c4d-276">만료된 키는 고객 키에서 사용할 수 없습니다. 만료된 키로 시도한 작업이 실패하여 서비스가 종료될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="76c4d-276">An expired key cannot be used by Customer Key and operations attempted with an expired key will fail and possibly result in a service outage.</span></span> <span data-ttu-id="76c4d-277">고객 키에 사용되는 키에는 만료 날짜가 없는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="76c4d-277">We strongly recommend that keys used with Customer Key do not have an expiration date.</span></span> <span data-ttu-id="76c4d-278">만료 날짜(설정된 경우)는 제거할 수 없지만 다른 날짜로 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="76c4d-278">An expiration date, once set, cannot be removed, but can be changed to a different date.</span></span> <span data-ttu-id="76c4d-279">만료 날짜가 설정된 키를 사용하려면 만료 값을 12/31/9999로 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="76c4d-279">If a key must be used that has an expiration date set, change the expiration value to 12/31/9999.</span></span> <span data-ttu-id="76c4d-280">만료 날짜가 12/31/9999가 다른 날짜로 설정된 키는 Microsoft 365 유효성 검사를 통과하지 못합니다.</span><span class="sxs-lookup"><span data-stu-id="76c4d-280">Keys with an expiration date set to a date other than 12/31/9999 won't pass Microsoft 365 validation.</span></span>
  
<span data-ttu-id="76c4d-281">12/31/9999가 아니라 다른 값으로 설정된 만료 날짜를 변경하기 위해 다음과 같이 [Update-AzKeyVaultKey](https://docs.microsoft.com/powershell/module/az.keyvault/update-azkeyvaultkey) cmdlet을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="76c4d-281">To change an expiration date that has been set to any value other than 12/31/9999, run the [Update-AzKeyVaultKey](https://docs.microsoft.com/powershell/module/az.keyvault/update-azkeyvaultkey) cmdlet as follows:</span></span>
  
```powershell
Update-AzKeyVaultKey -VaultName <vault name> -Name <key name> -Expires (Get-Date -Date "12/31/9999")
```

### <a name="obtain-the-uri-for-each-azure-key-vault-key"></a><span data-ttu-id="76c4d-282">각 Azure Key Vault 키에 대한 URI 얻기</span><span class="sxs-lookup"><span data-stu-id="76c4d-282">Obtain the URI for each Azure Key Vault key</span></span>

<span data-ttu-id="76c4d-283">Azure에서 키 자격 증명 모음을 설정하고 키를 추가하기 위한 모든 단계를 완료한 후 다음 명령을 실행하여 각 키 자격 증명 모음의 키에 대한 URI를 얻습니다.</span><span class="sxs-lookup"><span data-stu-id="76c4d-283">Once you've completed all the steps in Azure to set up your key vaults and added your keys, run the following command to get the URI for the key in each key vault.</span></span> <span data-ttu-id="76c4d-284">나중에 각 DEP를 만들고 할당할 때 이러한 URIS를 사용하여 이 정보를 안전한 장소에 저장해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="76c4d-284">You will need to use these URIs when you create and assign each DEP later, so save this information in a safe place.</span></span> <span data-ttu-id="76c4d-285">각 키 자격 증명 모음에 대해 이 명령을 한 번씩 실행해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="76c4d-285">Remember to run this command once for each key vault.</span></span>
  
<span data-ttu-id="76c4d-286">Azure PowerShell에서:</span><span class="sxs-lookup"><span data-stu-id="76c4d-286">In Azure PowerShell:</span></span>
  
```powershell
(Get-AzKeyVaultKey -VaultName <vault name>).Id
```

## <a name="set-up-the-customer-key-encryption-policy-for-your-tenant"></a><span data-ttu-id="76c4d-287">테넌트에 대한 고객 키 암호화 정책 설정</span><span class="sxs-lookup"><span data-stu-id="76c4d-287">Set up the Customer Key encryption policy for your tenant</span></span>

<span data-ttu-id="76c4d-288">이러한 cmdlet을 실행하려면 먼저 사용 권한을 할당해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="76c4d-288">You need to be assigned permissions before you can run these cmdlets.</span></span> <span data-ttu-id="76c4d-289">이 문서에서는 cmdlet의 모든 매개 변수를 나열하기는 하지만 사용자에게 할당된 사용 권한에 포함되지 않은 일부 매개 변수에는 액세스할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="76c4d-289">Although this article lists all parameters for the cmdlets, you may not have access to some parameters if they're not included in the permissions assigned to you.</span></span> <span data-ttu-id="76c4d-290">조직에서 cmdlet 또는 매개 변수를 실행하는 데 필요한 사용 권한을 확인하려면 [Find the permissions required to run any Exchange cmdlet](https://docs.microsoft.com/powershell/exchange/exchange-server/find-exchange-cmdlet-permissions)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="76c4d-290">To find the permissions required to run any cmdlet or parameter in your organization, see [Find the permissions required to run any Exchange cmdlet](https://docs.microsoft.com/powershell/exchange/exchange-server/find-exchange-cmdlet-permissions).</span></span>

### <a name="create-policy"></a><span data-ttu-id="76c4d-291">정책 만들기</span><span class="sxs-lookup"><span data-stu-id="76c4d-291">Create policy</span></span>

```powershell
   New-M365DataAtRestEncryptionPolicy [-Name] <String> -AzureKeyIDs <MultiValuedProperty> [-Description <String>]
```

<span data-ttu-id="76c4d-292">설명: 준수 관리자가 두 개의 AKV 루트 키를 사용하여 새 DEP(데이터 암호화 정책)를 만들 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="76c4d-292">Description: Enable compliance admin to create a new data encryption policy (DEP) using two AKV root keys.</span></span> <span data-ttu-id="76c4d-293">정책을 만든 후 cmdlet을 사용하여 정책을 할당할 Set-M365DataAtRestEncryptionPolicyAssignment 있습니다.</span><span class="sxs-lookup"><span data-stu-id="76c4d-293">Once created, a policy can then be assigned using Set-M365DataAtRestEncryptionPolicyAssignment cmdlet.</span></span> <span data-ttu-id="76c4d-294">키를 처음 할당하거나 키를 회전한 후 새 키가 적용될 때 최대 24시간이 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="76c4d-294">Upon first assignment of keys or after you rotate keys, it can take up to 24 hours for the new keys to take effect.</span></span> <span data-ttu-id="76c4d-295">새 DEP를 적용하는 데 24시간 이상 소요된 경우 Microsoft에 문의합니다.</span><span class="sxs-lookup"><span data-stu-id="76c4d-295">If the new DEP takes more than 24 hours to take effect, contact Microsoft.</span></span>

<span data-ttu-id="76c4d-296">예제:</span><span class="sxs-lookup"><span data-stu-id="76c4d-296">Example:</span></span>

```powershell
New-M365DataAtRestEncryptionPolicy -Name "Default_Policy" -AzureKeyIDs "https://contosoWestUSvault01.vault.azure.net/keys/Key_01","https://contosoEastUSvault01.vault.azure.net/keys/Key_02" -Description "Tenant default policy"
```

<span data-ttu-id="76c4d-297">매개 변수:</span><span class="sxs-lookup"><span data-stu-id="76c4d-297">Parameters:</span></span>

| <span data-ttu-id="76c4d-298">이름</span><span class="sxs-lookup"><span data-stu-id="76c4d-298">Name</span></span> | <span data-ttu-id="76c4d-299">설명</span><span class="sxs-lookup"><span data-stu-id="76c4d-299">Description</span></span> | <span data-ttu-id="76c4d-300">선택 사항(Y/N)</span><span class="sxs-lookup"><span data-stu-id="76c4d-300">Optional (Y/N)</span></span> |
|----------|----------|---------|
|<span data-ttu-id="76c4d-301">이름</span><span class="sxs-lookup"><span data-stu-id="76c4d-301">Name</span></span>|<span data-ttu-id="76c4d-302">데이터 암호화 정책의 이름</span><span class="sxs-lookup"><span data-stu-id="76c4d-302">Friendly name of the data encryption policy</span></span>|<span data-ttu-id="76c4d-303">N</span><span class="sxs-lookup"><span data-stu-id="76c4d-303">N</span></span>|
|<span data-ttu-id="76c4d-304">AzureKeyIDs</span><span class="sxs-lookup"><span data-stu-id="76c4d-304">AzureKeyIDs</span></span>|<span data-ttu-id="76c4d-305">데이터 암호화 정책과 연결하기 위해 Azure Key Vault 키의 URI 값 두 개를 0개로 구분하여 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="76c4d-305">Specifies two URI values of the Azure Key Vault keys, separated by a comma, to associate with the data encryption policy</span></span>|<span data-ttu-id="76c4d-306">N</span><span class="sxs-lookup"><span data-stu-id="76c4d-306">N</span></span>|
|<span data-ttu-id="76c4d-307">설명</span><span class="sxs-lookup"><span data-stu-id="76c4d-307">Description</span></span>|<span data-ttu-id="76c4d-308">데이터 암호화 정책에 대한 설명</span><span class="sxs-lookup"><span data-stu-id="76c4d-308">Description of the data encryption policy</span></span>|<span data-ttu-id="76c4d-309">N</span><span class="sxs-lookup"><span data-stu-id="76c4d-309">N</span></span>|

### <a name="assign-policy"></a><span data-ttu-id="76c4d-310">정책 할당</span><span class="sxs-lookup"><span data-stu-id="76c4d-310">Assign policy</span></span>

```powershell
Set-M365DataAtRestEncryptionPolicyAssignment -DataEncryptionPolicy “<Default_PolicyName or Default_PolicyID>”
```

<span data-ttu-id="76c4d-311">설명: 이 cmdlet은 기본 데이터 암호화 정책을 구성하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="76c4d-311">Description: This cmdlet is used for configuring default Data Encryption Policy.</span></span> <span data-ttu-id="76c4d-312">이 정책은 모든 지원 워크로드에서 데이터를 암호화하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="76c4d-312">This policy will be used to then encrypt data across all support workloads.</span></span> 

<span data-ttu-id="76c4d-313">예제:</span><span class="sxs-lookup"><span data-stu-id="76c4d-313">Example:</span></span>

```powershell
Set-M365DataAtRestEncryptionPolicyAssignment -DataEncryptionPolicy “Default_PolicyName”
```

<span data-ttu-id="76c4d-314">매개 변수:</span><span class="sxs-lookup"><span data-stu-id="76c4d-314">Parameters:</span></span>

| <span data-ttu-id="76c4d-315">이름</span><span class="sxs-lookup"><span data-stu-id="76c4d-315">Name</span></span> | <span data-ttu-id="76c4d-316">설명</span><span class="sxs-lookup"><span data-stu-id="76c4d-316">Description</span></span> | <span data-ttu-id="76c4d-317">선택 사항(Y/N)</span><span class="sxs-lookup"><span data-stu-id="76c4d-317">Optional (Y/N)</span></span> |
|----------|----------|---------|
<span data-ttu-id="76c4d-318">-DataEncryptionPolicy</span><span class="sxs-lookup"><span data-stu-id="76c4d-318">-DataEncryptionPolicy</span></span>|<span data-ttu-id="76c4d-319">할당해야 하는 데이터 암호화 정책을 지정합니다. 정책 이름 또는 정책 ID를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="76c4d-319">Specifies the data encryption policy that needs to be assigned; specify either the Policy Name or the Policy ID.</span></span>|<span data-ttu-id="76c4d-320">N</span><span class="sxs-lookup"><span data-stu-id="76c4d-320">N</span></span>|

### <a name="modify-or-refresh-policy"></a><span data-ttu-id="76c4d-321">정책 수정 또는 새로 고침</span><span class="sxs-lookup"><span data-stu-id="76c4d-321">Modify or Refresh policy</span></span>

```powershell
Set-M365DataAtRestEncryptionPolicy [-Identity] <M365DataAtRestEncryptionPolicy DataEncryptionPolicyIdParameter> -Refresh [-Enabled <Boolean>] [-Name <String>] [-Description <String>]
```

<span data-ttu-id="76c4d-322">설명: 이 cmdlet을 사용하여 기존 정책을 수정하거나 새로 고칠 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="76c4d-322">Description: The cmdlet can be used either to modify or refresh an existing policy.</span></span> <span data-ttu-id="76c4d-323">또한 정책을 활성화 또는 비활성화하는 데 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="76c4d-323">It can also be used to enable or disable a policy.</span></span> <span data-ttu-id="76c4d-324">키를 처음 할당하거나 키를 회전한 후 새 키가 적용될 때 최대 24시간이 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="76c4d-324">Upon first assignment of keys or after you rotate keys, it can take up to 24 hours for the new keys to take effect.</span></span> <span data-ttu-id="76c4d-325">새 DEP를 적용하는 데 24시간 이상 소요된 경우 Microsoft에 문의합니다.</span><span class="sxs-lookup"><span data-stu-id="76c4d-325">If the new DEP takes more than 24 hours to take effect, contact Microsoft.</span></span>

<span data-ttu-id="76c4d-326">예제:</span><span class="sxs-lookup"><span data-stu-id="76c4d-326">Examples:</span></span>

<span data-ttu-id="76c4d-327">데이터 암호화 정책을 사용하지 않도록 설정</span><span class="sxs-lookup"><span data-stu-id="76c4d-327">Disable a data encryption policy.</span></span>

```powershell
Set-M365DataAtRestEncryptionPolicy -Identity "NAM Policy" -Enabled $false
```

<span data-ttu-id="76c4d-328">데이터 암호화 정책을 새로 고침합니다.</span><span class="sxs-lookup"><span data-stu-id="76c4d-328">Refresh a data encryption policy.</span></span>

```powershell
Set-M365DataAtRestEncryptionPolicy -Identity “EUR Policy” -Refresh
```

<span data-ttu-id="76c4d-329">매개 변수:</span><span class="sxs-lookup"><span data-stu-id="76c4d-329">Parameters:</span></span>

| <span data-ttu-id="76c4d-330">이름</span><span class="sxs-lookup"><span data-stu-id="76c4d-330">Name</span></span> | <span data-ttu-id="76c4d-331">설명</span><span class="sxs-lookup"><span data-stu-id="76c4d-331">Description</span></span> | <span data-ttu-id="76c4d-332">선택 사항(Y/N)</span><span class="sxs-lookup"><span data-stu-id="76c4d-332">Optional (Y/N)</span></span> |
|----------|----------|---------|
|<span data-ttu-id="76c4d-333">-Identity</span><span class="sxs-lookup"><span data-stu-id="76c4d-333">-Identity</span></span>|<span data-ttu-id="76c4d-334">수정할 데이터 암호화 정책을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="76c4d-334">Specifies the data encryption policy that you want to modify.</span></span>|<span data-ttu-id="76c4d-335">N</span><span class="sxs-lookup"><span data-stu-id="76c4d-335">N</span></span>|
|<span data-ttu-id="76c4d-336">-Refresh</span><span class="sxs-lookup"><span data-stu-id="76c4d-336">-Refresh</span></span>|<span data-ttu-id="76c4d-337">Azure Key Vault에서 연결된 키를 회전한 후 Refresh 스위치를 사용하여 데이터 암호화 정책을 업데이트합니다.</span><span class="sxs-lookup"><span data-stu-id="76c4d-337">Use the Refresh switch to update the data encryption policy after you rotate any of the associated keys in the Azure Key Vault.</span></span> <span data-ttu-id="76c4d-338">이 스위치를 사용하면 값을 지정할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="76c4d-338">You don't need to specify a value with this switch.</span></span>|<span data-ttu-id="76c4d-339">Y</span><span class="sxs-lookup"><span data-stu-id="76c4d-339">Y</span></span>|
|<span data-ttu-id="76c4d-340">-사용 설정됨</span><span class="sxs-lookup"><span data-stu-id="76c4d-340">-Enabled</span></span>|<span data-ttu-id="76c4d-341">Enabled 매개 변수는 데이터 암호화 정책을 활성화하거나 사용하지 않도록 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="76c4d-341">The Enabled parameter enables or disable the data encryption policy.</span></span> <span data-ttu-id="76c4d-342">정책을 사용하지 않도록 설정하기 전에 테넌트에서 정책을 해제해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="76c4d-342">Before you disable a policy, you must unassign it from your tenant.</span></span> <span data-ttu-id="76c4d-343">유효한 값은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="76c4d-343">Valid values are:</span></span></br > <span data-ttu-id="76c4d-344">$true: 정책이 사용하도록 설정되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="76c4d-344">$true: The policy is enabled</span></span></br > <span data-ttu-id="76c4d-345">$true: 이 정책은 사용하도록 설정되어 있습니다. 이 값은 기본값입니다.
</span><span class="sxs-lookup"><span data-stu-id="76c4d-345">$false: The policy is disabled.</span></span>|<span data-ttu-id="76c4d-346">Y</span><span class="sxs-lookup"><span data-stu-id="76c4d-346">Y</span></span>|
|<span data-ttu-id="76c4d-347">-Name</span><span class="sxs-lookup"><span data-stu-id="76c4d-347">-Name</span></span>|<span data-ttu-id="76c4d-348">Name 매개 변수는 데이터 암호화 정책의 고유 이름을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="76c4d-348">The Name parameter specifies the unique name for the data encryption policy.</span></span>|<span data-ttu-id="76c4d-349">Y</span><span class="sxs-lookup"><span data-stu-id="76c4d-349">Y</span></span>|
|<span data-ttu-id="76c4d-350">-Description</span><span class="sxs-lookup"><span data-stu-id="76c4d-350">-Description</span></span>|<span data-ttu-id="76c4d-351">Description 매개 변수는 데이터 암호화 정책에 대한 선택적 설명을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="76c4d-351">The Description parameter specifies an optional description for the data encryption policy.</span></span>|<span data-ttu-id="76c4d-352">Y</span><span class="sxs-lookup"><span data-stu-id="76c4d-352">Y</span></span>|

### <a name="get-policy-details"></a><span data-ttu-id="76c4d-353">정책 세부 정보 확인</span><span class="sxs-lookup"><span data-stu-id="76c4d-353">Get policy details</span></span>

```powershell
Get-M365DataAtRestEncryptionPolicy [-Identity] <M365DataAtRestEncryptionPolicy DataEncryptionPolicyIdParameter>
```

<span data-ttu-id="76c4d-354">설명: 이 cmdlet은 테넌트에 대해 만들어진 모든 M365DataAtRest 암호화 정책 또는 특정 정책에 대한 세부 정보를 나열합니다.</span><span class="sxs-lookup"><span data-stu-id="76c4d-354">Description: This cmdlet lists all of M365DataAtRest encryption policies that are created for the tenant or details about a specific policy.</span></span>

<span data-ttu-id="76c4d-355">예제:</span><span class="sxs-lookup"><span data-stu-id="76c4d-355">Examples:</span></span>

<span data-ttu-id="76c4d-356">이 예에서는 조직의 M365DatAtRest 암호화 정책 요약 목록을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="76c4d-356">This example returns a summary list of M365DatAtRest Encryption policies in the organization.</span></span>

```powershell
Get-M365DataAtRestEncryptionPolicy
```

<span data-ttu-id="76c4d-357">이 예에서는 "NAM Policy"라는 데이터 암호화 정책에 대한 자세한 정보를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="76c4d-357">This example returns detailed information for the data encryption policy named "NAM Policy".</span></span>

```powershell
Get-M365DataAtRestEncryptionPolicy -Identity "NAM Policy"
```

<span data-ttu-id="76c4d-358">매개 변수:</span><span class="sxs-lookup"><span data-stu-id="76c4d-358">Parameters:</span></span>

| <span data-ttu-id="76c4d-359">이름</span><span class="sxs-lookup"><span data-stu-id="76c4d-359">Name</span></span> | <span data-ttu-id="76c4d-360">설명</span><span class="sxs-lookup"><span data-stu-id="76c4d-360">Description</span></span> | <span data-ttu-id="76c4d-361">선택 사항(Y/N)</span><span class="sxs-lookup"><span data-stu-id="76c4d-361">Optional (Y/N)</span></span> |
|----------|----------|---------|
|<span data-ttu-id="76c4d-362">-Identity</span><span class="sxs-lookup"><span data-stu-id="76c4d-362">-Identity</span></span>|<span data-ttu-id="76c4d-363">세부 정보를 나열할 데이터 암호화 정책을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="76c4d-363">Specifies the data encryption policy that you want to list the details for.</span></span>|<span data-ttu-id="76c4d-364">Y</span><span class="sxs-lookup"><span data-stu-id="76c4d-364">Y</span></span>|

### <a name="get-policy-assignment-info"></a><span data-ttu-id="76c4d-365">정책 할당 정보 보기</span><span class="sxs-lookup"><span data-stu-id="76c4d-365">Get policy assignment info</span></span>

```powershell
Get-M365DataAtRestEncryptionPolicyAssignment
```

<span data-ttu-id="76c4d-366">설명: 이 cmdlet은 현재 테넌트에 할당된 정책을 나열합니다.</span><span class="sxs-lookup"><span data-stu-id="76c4d-366">Description: This cmdlet lists the policy that’s currently assigned to the tenant.</span></span>

## <a name="offboarding-from-customer-key"></a><span data-ttu-id="76c4d-367">고객 키에서 오프보드</span><span class="sxs-lookup"><span data-stu-id="76c4d-367">Offboarding from Customer Key</span></span>

<span data-ttu-id="76c4d-368">Microsoft 관리 키로 되돌려야 하는 경우 다시 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="76c4d-368">If you need to revert back to Microsoft-managed keys, you can.</span></span> <span data-ttu-id="76c4d-369">오프보드를 해제하면 각 개별 워크로드에서 지원하는 기본 암호화를 사용하여 데이터가 다시 암호화됩니다.</span><span class="sxs-lookup"><span data-stu-id="76c4d-369">When you offboard, your data is re-encrypted using default encryption supported by each individual workload.</span></span> <span data-ttu-id="76c4d-370">예를 들어 Exchange Online에서는 Microsoft에서 관리하는 키를 사용하여 기본 암호화를 지원할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="76c4d-370">For example, Exchange Online supports default encryption using Microsoft-managed keys.</span></span>

<span data-ttu-id="76c4d-371">테넌트 수준에서 고객 키에서 테넌트의 등록을 해제하기로 결정한 경우 에서 테넌트에 대한 서비스를 "사용하지 않도록 설정"을 요청하는 전자 메일을 통해 Microsoft에 [m365ck@microsoft.com.](mailto:m365ck@microsoft.com)</span><span class="sxs-lookup"><span data-stu-id="76c4d-371">If you decided to offboard your tenant from Customer Key at the tenant level, reach out to Microsoft with a request through email to “disable” the service for the tenant at [m365ck@microsoft.com](mailto:m365ck@microsoft.com).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="76c4d-372">오프보더는 데이터 제거와는 동일하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="76c4d-372">Offboarding is not the same as a data purge.</span></span> <span data-ttu-id="76c4d-373">데이터를 삭제하면 Microsoft 365에서 조직의 데이터가 영구적으로 삭제되고, 오프보더는 삭제되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="76c4d-373">A data purge permanently crypto-deletes your organization's data from Microsoft 365, offboarding does not.</span></span> <span data-ttu-id="76c4d-374">테넌트 수준 정책에 대한 데이터 제거는 수행할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="76c4d-374">You can't perform a data purge for a tenant-level policy.</span></span> <span data-ttu-id="76c4d-375">데이터 제거 경로에 대한 자세한 내용은 키 해지 및 데이터 제거 경로 프로세스 시작을 [참조하세요.](customer-key-manage.md#revoke-your-keys-and-start-the-data-purge-path-process)</span><span class="sxs-lookup"><span data-stu-id="76c4d-375">For information about data purge path, see [Revoke your keys and start the data purge path process](customer-key-manage.md#revoke-your-keys-and-start-the-data-purge-path-process).</span></span>

## <a name="about-the-availability-key"></a><span data-ttu-id="76c4d-376">가용성 키</span><span class="sxs-lookup"><span data-stu-id="76c4d-376">About the availability key</span></span>

<span data-ttu-id="76c4d-377">가용성 키에 대한 자세한 내용은 가용성 키에 [대한 자세한 정보를 참조하세요.](customer-key-availability-key-understand.md)</span><span class="sxs-lookup"><span data-stu-id="76c4d-377">For information about the availability key, see [Learn about the availability key](customer-key-availability-key-understand.md).</span></span>

## <a name="key-rotation"></a><span data-ttu-id="76c4d-378">키 회전</span><span class="sxs-lookup"><span data-stu-id="76c4d-378">Key rotation</span></span>

<span data-ttu-id="76c4d-379">고객 키와 함께 사용되는 키 회전 또는 롤링에 대한 자세한 내용은 고객 키 또는 가용성 키 롤 또는 [회전을 참조하세요.](customer-key-availability-key-roll.md)</span><span class="sxs-lookup"><span data-stu-id="76c4d-379">For information about rotating or rolling keys used with Customer Key, see [Roll or rotate a Customer Key or an availability key](customer-key-availability-key-roll.md).</span></span> <span data-ttu-id="76c4d-380">새 버전의 키를 사용하기 위해 DEP를 업데이트하면 이 문서의 앞부분에서 설명한 대로 Set-M365DataAtRestEncryptionPolicy cmdlet을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="76c4d-380">When you update the DEP to use the new version of the keys, you'll run the Set-M365DataAtRestEncryptionPolicy cmdlet as described earlier in this article.</span></span>

## <a name="related-articles"></a><span data-ttu-id="76c4d-381">관련 문서:</span><span class="sxs-lookup"><span data-stu-id="76c4d-381">Related articles:</span></span>

- [<span data-ttu-id="76c4d-382">고객 키를 사용한 서비스 암호화</span><span class="sxs-lookup"><span data-stu-id="76c4d-382">Service encryption with Customer Key</span></span>](customer-key-overview.md)

- [<span data-ttu-id="76c4d-383">고객 키 또는 가용성 키 롤 또는 회전</span><span class="sxs-lookup"><span data-stu-id="76c4d-383">Roll or rotate a Customer Key or an availability key</span></span>](customer-key-availability-key-roll.md)

- [<span data-ttu-id="76c4d-384">가용성 키에 대해 자세히 알아보기</span><span class="sxs-lookup"><span data-stu-id="76c4d-384">Learn about the availability key</span></span>](customer-key-availability-key-understand.md)

- [<span data-ttu-id="76c4d-385">서비스 암호화</span><span class="sxs-lookup"><span data-stu-id="76c4d-385">Service Encryption</span></span>](office-365-service-encryption.md)
