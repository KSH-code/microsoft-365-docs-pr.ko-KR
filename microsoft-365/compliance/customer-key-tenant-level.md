---
title: 테넌트 수준에서의 Microsoft 365 고객 키(공개 미리보기)
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 12/17/2020
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
description: Microsoft 365 테넌트 내의 모든 데이터에 대해 고객 키를 설정하는 방법을 알아보습니다.
ms.openlocfilehash: f14bbc0cb6dd29883efa4c8d294d8d65cae98641
ms.sourcegitcommit: 98b889e674ad1d5fa37d4b6c5fc3eda60a1d67f3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/05/2021
ms.locfileid: "49751272"
---
# <a name="overview-of-customer-key-for-microsoft-365-at-the-tenant-level-public-preview"></a><span data-ttu-id="4fffb-103">테넌트 수준의 Microsoft 365 고객 키 개요(공개 미리 보기)</span><span class="sxs-lookup"><span data-stu-id="4fffb-103">Overview of Customer Key for Microsoft 365 at the tenant level (public preview)</span></span>

<span data-ttu-id="4fffb-104">제공한 키를 사용하여 DEP(데이터 암호화 정책)를 만들고 테넌트에 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4fffb-104">Using keys you provide, you can create a data encryption policy (DEP) and assign it to the tenant.</span></span> <span data-ttu-id="4fffb-105">DEP는 이러한 워크로드에 대한 테넌트에서 데이터를 암호화합니다.</span><span class="sxs-lookup"><span data-stu-id="4fffb-105">The DEP encrypts data across the tenant for these workloads:</span></span>

- <span data-ttu-id="4fffb-106">Teams 채팅 메시지(1:1 채팅, 그룹 채팅, 모임 채팅 및 채널 대화)</span><span class="sxs-lookup"><span data-stu-id="4fffb-106">Teams chat messages (1:1 chats, group chats, meeting chats and channel conversations)</span></span>
- <span data-ttu-id="4fffb-107">Teams 미디어 메시지(이미지, 코드, 비디오, 위키 이미지)</span><span class="sxs-lookup"><span data-stu-id="4fffb-107">Teams media messages (images, code snippets, videos, wiki images)</span></span>
- <span data-ttu-id="4fffb-108">Teams 저장소에 저장된 Teams 통화 및 모임 녹음/녹화</span><span class="sxs-lookup"><span data-stu-id="4fffb-108">Teams call and meeting recordings stored in Teams storage</span></span>
- <span data-ttu-id="4fffb-109">Teams 채팅 알림</span><span class="sxs-lookup"><span data-stu-id="4fffb-109">Teams chat notifications</span></span>
- <span data-ttu-id="4fffb-110">Cortana의 Teams 채팅 제안</span><span class="sxs-lookup"><span data-stu-id="4fffb-110">Teams chat suggestions by Cortana</span></span>
- <span data-ttu-id="4fffb-111">Teams 상태 메시지</span><span class="sxs-lookup"><span data-stu-id="4fffb-111">Teams status messages</span></span>
- <span data-ttu-id="4fffb-112">Exchange Online에 대한 사용자 및 신호 정보</span><span class="sxs-lookup"><span data-stu-id="4fffb-112">User and signal information for Exchange Online</span></span>

<span data-ttu-id="4fffb-113">Microsoft Teams의 경우 테넌트 수준의 고객 키는 DEP가 테넌트에 할당된 시간부터 새 데이터를 암호화합니다.</span><span class="sxs-lookup"><span data-stu-id="4fffb-113">For Microsoft Teams, Customer Key at the tenant level encrypts new data from the time the DEP is assigned to the tenant.</span></span> <span data-ttu-id="4fffb-114">공개 미리 보기에서는 과거의 데이터 암호화를 지원하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="4fffb-114">Public preview does not support encrypting past data.</span></span> <span data-ttu-id="4fffb-115">Exchange Online의 경우 고객 키는 기존 데이터와 새 데이터를 모두 암호화합니다.</span><span class="sxs-lookup"><span data-stu-id="4fffb-115">For Exchange Online, Customer Key encrypts all existing and new data.</span></span>

<span data-ttu-id="4fffb-116">테넌트당 여러 DEP를 만들 수 있지만 특정 시점에 하나의 DEP만 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4fffb-116">You can create multiple DEPs per tenant but can only assign one DEP at any point in time.</span></span> <span data-ttu-id="4fffb-117">DEP를 할당하면 암호화가 자동으로 시작되지만 테넌트의 크기에 따라 완료하는 데 시간이 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4fffb-117">When you assign the DEP, encryption begins automatically but can take some time to complete depending on the size of your tenant.</span></span>

## <a name="tenant-level-policies-add-broader-control-to-customer-key-for-microsoft-365"></a><span data-ttu-id="4fffb-118">테넌트 수준 정책은 Microsoft 365의 고객 키에 더 광범위한 제어를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="4fffb-118">Tenant level policies add broader control to Customer Key for Microsoft 365</span></span>

<span data-ttu-id="4fffb-119">Exchange Online 및 Sharepoint Online에 대해 이미 고객 키를 설정한 경우 새 테넌트 수준 공개 미리 보기가 어떻게 설정되어 있는가?</span><span class="sxs-lookup"><span data-stu-id="4fffb-119">If you already have Customer Key set up for Exchange Online and Sharepoint Online, here's how the new tenant-level public preview fits in.</span></span>

<span data-ttu-id="4fffb-120">만든 테넌트 수준 암호화 정책은 Microsoft 365의 Microsoft Teams 및 Exchange Online 워크로드에 대한 모든 데이터를 암호화합니다.</span><span class="sxs-lookup"><span data-stu-id="4fffb-120">The tenant-level encryption policy you create encrypts all data for the Microsoft Teams and Exchange Online workloads in Microsoft 365.</span></span> <span data-ttu-id="4fffb-121">이 정책은 고객 키에서 이미 만든 세부적으로 조정된 DEP를 방해하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="4fffb-121">This policy doesn't interfere with finely tuned DEPs you've already created in Customer Key.</span></span>

<span data-ttu-id="4fffb-122">예제:</span><span class="sxs-lookup"><span data-stu-id="4fffb-122">Examples:</span></span>

<span data-ttu-id="4fffb-123">비즈니스용 OneDrive 및 SharePoint에 저장된 Microsoft Teams 파일 및 일부 Teams 통화 및 모임 녹음/녹화는 SharePoint Online DEP에 의해 암호화됩니다.</span><span class="sxs-lookup"><span data-stu-id="4fffb-123">Microsoft Teams files and some Teams call and meeting recordings that are saved in OneDrive for Business and SharePoint are encrypted by a SharePoint Online DEP.</span></span> <span data-ttu-id="4fffb-124">단일 SharePoint Online DEP는 단일 지리적으로 콘텐츠를 암호화합니다.</span><span class="sxs-lookup"><span data-stu-id="4fffb-124">A single SharePoint Online DEP encrypts content within a single geo.</span></span> <span data-ttu-id="4fffb-125">테넌트 수준 DEP는 새 정책을 사용하여 암호화된 데이터를 다시 암호화합니다.</span><span class="sxs-lookup"><span data-stu-id="4fffb-125">The tenant-level DEP will encrypt the encrypted data again with the new policy.</span></span>

<span data-ttu-id="4fffb-126">Exchange Online의 경우 고객 키를 사용하여 하나 이상의 사용자 사서함을 암호화하는 DEP를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4fffb-126">For Exchange Online, you can create a DEP that encrypts one or more user mailboxes with Customer Key.</span></span> <span data-ttu-id="4fffb-127">테넌트 수준 정책을 만들 때 해당 정책은 암호화된 사서함을 암호화하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="4fffb-127">When you create a tenant-level policy, that policy will not encrypt the encrypted mailboxes.</span></span> <span data-ttu-id="4fffb-128">그러나 테넌트 수준 키는 이미 DEP의 영향을 받지 않는 사서함을 암호화합니다.</span><span class="sxs-lookup"><span data-stu-id="4fffb-128">However,  the tenant-level key will encrypt the mailboxes that are not affected by a DEP already.</span></span>

## <a name="set-up-customer-key-at-the-tenant-level-public-preview"></a><span data-ttu-id="4fffb-129">테넌트 수준에서 고객 키 설정(공개 미리 보기)</span><span class="sxs-lookup"><span data-stu-id="4fffb-129">Set up Customer Key at the tenant level (public preview)</span></span>

<span data-ttu-id="4fffb-130">이러한 단계는 응용 프로그램 수준에서 고객 키를 설정하는 단계와 비슷하지만 동일하지는 않습니다.</span><span class="sxs-lookup"><span data-stu-id="4fffb-130">These steps are similar but not identical to the steps for setting up Customer Key at the application level.</span></span> <span data-ttu-id="4fffb-131">테스트 테넌트의 테스트 데이터와 함께 이 공개 미리 보기만 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4fffb-131">You should only use this public preview with test data in test tenants.</span></span> <span data-ttu-id="4fffb-132">프로덕션 데이터나 프로덕션 환경에서는 이 릴리스를 사용하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="4fffb-132">Do not use this release with production data or in your production environment.</span></span> <span data-ttu-id="4fffb-133">고객 키의 프로덕션 배포가 이미 있는 경우 다음 단계를 사용하여 테스트 환경의 테넌트 수준에서 고객 키를 설정하십시오.</span><span class="sxs-lookup"><span data-stu-id="4fffb-133">If you already have a production deployment of Customer Key, use these steps to set up Customer Key at the tenant level in a test environment.</span></span>

<span data-ttu-id="4fffb-134">Azure PowerShell에 원격으로 연결하여 이러한 대부분의 작업을 완료합니다.</span><span class="sxs-lookup"><span data-stu-id="4fffb-134">You'll complete most of these tasks by remotely connecting to Azure PowerShell.</span></span> <span data-ttu-id="4fffb-135">최상의 결과를 얻기 위해 Azure PowerShell 버전 4.4.0 이상을 사용하세요.</span><span class="sxs-lookup"><span data-stu-id="4fffb-135">For best results, use version 4.4.0 or later of Azure PowerShell.</span></span>

<span data-ttu-id="4fffb-136">시작하기 전에 다음을 반드시 확인하십시오.</span><span class="sxs-lookup"><span data-stu-id="4fffb-136">Before you get started, make sure of the following:</span></span>

- <span data-ttu-id="4fffb-137">테넌트 수준에서 고객 키를 설정하려면 준수 관리자 역할이 있는 직장 또는 학교 계정을 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4fffb-137">You'll need to use a work or school account that has the compliance admin role to set up Customer Key at the tenant level.</span></span>
- <span data-ttu-id="4fffb-138">조직에 적절한 라이선스가 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="4fffb-138">Ensure that you have the appropriate licensing for your organization.</span></span> <span data-ttu-id="4fffb-139">클라우드 서비스 공급자 또는 클라우드 서비스 공급자를 사용하여 기업계약 송장된 Azure 구독을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="4fffb-139">Use a paid, invoiced Azure Subscription using either an Enterprise Agreement or a Cloud Service Provider.</span></span> <span data-ttu-id="4fffb-140">결제 플랜 또는 신용 카드를 사용하여 구입한 Azure 구독은 고객 키에 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="4fffb-140">Azure Subscriptions purchased using Pay As You Go plans or using a credit card aren't supported for Customer Key.</span></span> <span data-ttu-id="4fffb-141">2020년 4월 1일부터 Office 365의 고객 키는 Office 365 E5, M365 E5, M365 E5 규정 준수 및 M365 E5 정보 보호 & 관리 SKUS에서 제공됩니다.</span><span class="sxs-lookup"><span data-stu-id="4fffb-141">Starting April 1, 2020, Customer Key in Office 365 is offered in Office 365 E5, M365 E5, M365 E5 Compliance, and M365 E5 Information Protection & Governance SKUs.</span></span> <span data-ttu-id="4fffb-142">Office 365 Advanced Compliance SKU는 더 이상 새 라이선스를 조달할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="4fffb-142">Office 365 Advanced Compliance SKU is no longer available for procuring new licenses.</span></span> <span data-ttu-id="4fffb-143">기존 Office 365 고급 준수 라이선스는 계속 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="4fffb-143">Existing Office 365 Advanced Compliance licenses will continue to be supported.</span></span> <span data-ttu-id="4fffb-144">적절한 라이선스가 있는 테넌트에서 최소 하나의 라이선스로 서비스를 사용하도록 설정하는 것이 가능하기는 하지만, 서비스를 통해 혜택을 받은 모든 사용자에게 적절한 라이선스가 있는지도 여전히 확인해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4fffb-144">While the service can be enabled with a minimum of one license under the tenant having the appropriate license, you should still make sure all users that benefit from the service have appropriate licenses.</span></span>

### <a name="create-two-new-azure-subscriptions"></a><span data-ttu-id="4fffb-145">새 Azure 구독 2개 만들기</span><span class="sxs-lookup"><span data-stu-id="4fffb-145">Create two new Azure subscriptions</span></span>

<span data-ttu-id="4fffb-146">고객 키에는 각 DEP(데이터 암호화 정책)에 대해 두 개의 키가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="4fffb-146">Customer Key requires two keys for each data encryption policy (DEP).</span></span> <span data-ttu-id="4fffb-147">이를 위해서는 Azure 구독을 두 개 만들어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4fffb-147">To achieve this, you must create two Azure subscriptions.</span></span> <span data-ttu-id="4fffb-148">조직의 개별 구성원이 각 구독에서 하나의 키를 구성하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="4fffb-148">As a best practice, Microsoft recommends that you have separate members of your organization configure one key in each subscription.</span></span> <span data-ttu-id="4fffb-149">이러한 Azure 구독만 사용하여 Microsoft 365의 암호화 키를 관리합니다.</span><span class="sxs-lookup"><span data-stu-id="4fffb-149">Only use these Azure subscriptions to administer encryption keys for Microsoft 365.</span></span> <span data-ttu-id="4fffb-150">이렇게 하여 운영자 중 한 명이 실수로 의도적으로 또는 악의적으로 삭제하거나 책임이 있는 키를 잘못 관리한 경우 조직을 보호합니다.</span><span class="sxs-lookup"><span data-stu-id="4fffb-150">This protects your organization in case one of your operators accidentally, intentionally, or maliciously deletes or otherwise mismanages the keys for which they are responsible.</span></span>

<span data-ttu-id="4fffb-151">조직에 대해 만들 수 있는 Azure 구독 수에는 실질적으로 제한이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="4fffb-151">There is no practical limit to the number of Azure subscriptions that you can create for your organization.</span></span> <span data-ttu-id="4fffb-152">이 모범 사례를 사용하면 사용자 오류의 영향을 최소화하면서 고객 키에서 사용하는 리소스를 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4fffb-152">Following this best practice helps minimize the impact of human error while helping to manage the resources used by Customer Key.</span></span>

### <a name="register-azure-subscriptions-to-use-a-mandatory-retention-period"></a><span data-ttu-id="4fffb-153">필수 보존 기간을 사용하기 위해 Azure 구독 등록</span><span class="sxs-lookup"><span data-stu-id="4fffb-153">Register Azure subscriptions to use a mandatory retention period</span></span>

<span data-ttu-id="4fffb-154">루트 암호화 키의 일시적 또는 영구적 손실은 서비스 작업에 지장이나 심지어는 비극적일 수 있으며 데이터가 손실될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4fffb-154">The temporary or permanent loss of root encryption keys can be disruptive or even catastrophic to service operation and can result in data loss.</span></span> <span data-ttu-id="4fffb-155">이러한 이유로 고객 키와 함께 사용되는 리소스에는 강력한 보호가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="4fffb-155">For this reason, the resources used with Customer Key require strong protection.</span></span> <span data-ttu-id="4fffb-156">고객 키와 함께 사용되는 모든 Azure 리소스는 기본 구성을 넘어 보호 메커니즘을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="4fffb-156">All the Azure resources that are used with Customer Key offer protection mechanisms beyond the default configuration.</span></span> <span data-ttu-id="4fffb-157">Azure 구독은 즉시 취소할 수 없는 취소를 방지하는 방식으로 태그를 지정하거나 등록할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4fffb-157">Azure subscriptions can be tagged or registered in a way that will prevent immediate and irrevocable cancellation.</span></span> <span data-ttu-id="4fffb-158">이를 필수 보존 기간에 등록이라고 합니다.</span><span class="sxs-lookup"><span data-stu-id="4fffb-158">This is referred to as registering for a mandatory retention period.</span></span> <span data-ttu-id="4fffb-159">필수 보존 기간 동안 Azure 구독을 등록하는 데 필요한 단계는 Microsoft와 공동 작업해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4fffb-159">The steps required to register Azure subscriptions for a mandatory retention period require collaboration with the Microsoft.</span></span> <span data-ttu-id="4fffb-160">이 프로세스는 영업일 최대 5일이 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4fffb-160">This process can take up to five business days.</span></span> <span data-ttu-id="4fffb-161">이전에는 이 작업을 "Do Not Cancel"이라고도 합니다.</span><span class="sxs-lookup"><span data-stu-id="4fffb-161">Previously, this was sometimes referred to as "Do Not Cancel".</span></span>
  
<span data-ttu-id="4fffb-162">Microsoft 365 팀에 문의하기 전에 고객 키와 함께 사용하는 각 Azure 구독에 대해 다음 단계를 수행해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4fffb-162">Before contacting the Microsoft 365 team, you must perform the following steps for each Azure subscription that you use with Customer Key.</span></span> <span data-ttu-id="4fffb-163">시작하기 전에 [Azure PowerShell Az](https://docs.microsoft.com/powershell/azure/new-azureps-module-az) 모듈을 설치해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4fffb-163">Ensure that you have the [Azure PowerShell Az](https://docs.microsoft.com/powershell/azure/new-azureps-module-az) module installed before you start.</span></span>

1. <span data-ttu-id="4fffb-164">Azure PowerShell로 로그인합니다.</span><span class="sxs-lookup"><span data-stu-id="4fffb-164">Sign in with Azure PowerShell.</span></span> <span data-ttu-id="4fffb-165">자세한 내용은 [Azure PowerShell로 로그인을 참조하세요.](https://docs.microsoft.com/powershell/azure/authenticate-azureps)</span><span class="sxs-lookup"><span data-stu-id="4fffb-165">For instructions, see [Sign in with Azure PowerShell](https://docs.microsoft.com/powershell/azure/authenticate-azureps).</span></span>

2. <span data-ttu-id="4fffb-166">Register-AzProviderFeature cmdlet을 실행하여 필수 보존 기간을 사용하기 위해 구독을 등록합니다.</span><span class="sxs-lookup"><span data-stu-id="4fffb-166">Run the Register-AzProviderFeature cmdlet to register your subscriptions to use a mandatory retention period.</span></span> <span data-ttu-id="4fffb-167">각 구독에 대해 이 작업을 수행하십시오.</span><span class="sxs-lookup"><span data-stu-id="4fffb-167">Perform this action for each subscription.</span></span>

   ```powershell
   Set-AzContext -SubscriptionId <SubscriptionId>
   Register-AzProviderFeature -FeatureName mandatoryRetentionPeriodEnabled -ProviderNamespace Microsoft.Resources
   ```

3. <span data-ttu-id="4fffb-168">Microsoft에 문의하여 프로세스가 [m365ck@microsoft.com.](mailto:m365ck@microsoft.com)</span><span class="sxs-lookup"><span data-stu-id="4fffb-168">Contact Microsoft to have the process finalized at [m365ck@microsoft.com](mailto:m365ck@microsoft.com).</span></span> <span data-ttu-id="4fffb-169">전자 메일에 다음을 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="4fffb-169">Include the following in your email:</span></span>

   <span data-ttu-id="4fffb-170">**제목:** 고객 키 \<*Your tenant's fully-qualified domain name*\></span><span class="sxs-lookup"><span data-stu-id="4fffb-170">**Subject**: Customer Key for \<*Your tenant's fully-qualified domain name*\></span></span>

   <span data-ttu-id="4fffb-171">**본문:** 필수 보존 기간을 마무리할 구독 신분</span><span class="sxs-lookup"><span data-stu-id="4fffb-171">**Body**: Subscription IDs for which you want to have the mandatory retention period finalized.</span></span>
   <span data-ttu-id="4fffb-172">각 구독에 대한 Get-AzProviderFeature 출력입니다.</span><span class="sxs-lookup"><span data-stu-id="4fffb-172">The output of Get-AzProviderFeature for each subscription.</span></span>

   <span data-ttu-id="4fffb-173">이 프로세스 완료를 위한 SLA(서비스 수준 계약)는 Microsoft가 필수 보존 기간을 사용하기 위해 구독을 등록했다는 알림을(확인)한 후 영업일 5일입니다.</span><span class="sxs-lookup"><span data-stu-id="4fffb-173">The Service Level Agreement (SLA) for completion of this process is five business days once Microsoft has been notified (and verified) that you have registered your subscriptions to use a mandatory retention period.</span></span>

4. <span data-ttu-id="4fffb-174">Microsoft로부터 등록이 완료된다는 알림을 받으면 다음과 같이 Get-AzProviderFeature 등록 상태를 확인하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4fffb-174">Once you receive notification from Microsoft that registration is complete, verify the status of your registration by running the Get-AzProviderFeature command as follows.</span></span> <span data-ttu-id="4fffb-175">확인된 Get-AzProviderFeature 명령은 등록 상태 속성에 **대해 Registered** 값을 **반환합니다.**</span><span class="sxs-lookup"><span data-stu-id="4fffb-175">If verified, the Get-AzProviderFeature command returns a value of **Registered** for the **Registration State** property.</span></span> <span data-ttu-id="4fffb-176">각 구독에 대해 이 작업을 수행하십시오.</span><span class="sxs-lookup"><span data-stu-id="4fffb-176">Perform this action for each subscription.</span></span>

   ```powershell
   Set-AzContext -SubscriptionId <SubscriptionId>
   Get-AzProviderFeature -ProviderNamespace Microsoft.Resources -FeatureName mandatoryRetentionPeriodEnabled
   ```

5. <span data-ttu-id="4fffb-177">프로세스를 완료하기 위해 Register-AzResourceProvider 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="4fffb-177">To complete the process, run the Register-AzResourceProvider command.</span></span> <span data-ttu-id="4fffb-178">각 구독에 대해 이 작업을 수행하십시오.</span><span class="sxs-lookup"><span data-stu-id="4fffb-178">Perform this action for each subscription.</span></span>

   ```powershell
   Set-AzContext -SubscriptionId <SubscriptionId>
   Register-AzResourceProvider -ProviderNamespace Microsoft.KeyVault
   ```

### <a name="create-a-premium-azure-key-vault-in-each-subscription"></a><span data-ttu-id="4fffb-179">각 구독에서 프리미엄 Azure Key Vault 만들기</span><span class="sxs-lookup"><span data-stu-id="4fffb-179">Create a premium Azure Key Vault in each subscription</span></span>

<span data-ttu-id="4fffb-180">키 자격 증명 모음을 만드는 단계는 Azure PowerShell 설치 및 시작, Azure 구독 연결, 리소스 그룹 만들기 및 해당 리소스 그룹에서 키 자격 증명 모음 만들기를 안내하는 [Azure Key Vault](https://azure.microsoft.com/documentation/articles/key-vault-get-started/)시작에 설명되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4fffb-180">The steps to create a key vault are documented in [Getting Started with Azure Key Vault](https://azure.microsoft.com/documentation/articles/key-vault-get-started/), which guides you through installing and launching Azure PowerShell, connecting to your Azure subscription, creating a resource group, and creating a key vault in that resource group.</span></span>
  
<span data-ttu-id="4fffb-181">키 자격 증명 모음을 만들 때 SKU(Standard 또는 Premium)를 선택해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4fffb-181">When you create a key vault, you must choose a SKU: either Standard or Premium.</span></span> <span data-ttu-id="4fffb-182">Standard SKU를 사용하면 Azure Key Vault 키를 소프트웨어로 보호할 수 있습니다. HSM(하드웨어 보안 모듈) 키 보호가 없습니다. Premium SKU는 키 자격 증명 모음 키 보호를 위해 HSM을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4fffb-182">The Standard SKU allows Azure Key Vault keys to be protected with software - there is no Hardware Security Module (HSM) key protection - and the Premium SKU allows the use of HSMs for protection of Key Vault keys.</span></span> <span data-ttu-id="4fffb-183">Customer Key는 SKU 중 하나를 사용하는 주요 자격 증명 모음을 수락합니다. 그러나 Microsoft는 Premium SKU만 사용하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="4fffb-183">Customer Key accepts key vaults that use either SKU, though Microsoft strongly recommends that you use only the Premium SKU.</span></span> <span data-ttu-id="4fffb-184">두 유형의 키 중 하나를 사용하는 작업의 비용은 동일하기 때문에 비용의 유일한 차이는 각 HSM으로 보호되는 키에 대한 월별 비용입니다.</span><span class="sxs-lookup"><span data-stu-id="4fffb-184">The cost of operations with keys of either type is the same, so the only difference in cost is the cost per month for each HSM-protected key.</span></span> <span data-ttu-id="4fffb-185">자세한 [내용은 Key Vault 가격을](https://azure.microsoft.com/pricing/details/key-vault/) 참조합니다.</span><span class="sxs-lookup"><span data-stu-id="4fffb-185">See [Key Vault pricing](https://azure.microsoft.com/pricing/details/key-vault/) for details.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="4fffb-186">프로덕션 데이터에는 Premium SKU 키 자격 증명 모음 및 HSM으로 보호된 키를 사용하며 테스트 및 유효성 검사를 위해 표준 SKU 키 자격 증명 모음 및 키만 사용하십시오.</span><span class="sxs-lookup"><span data-stu-id="4fffb-186">Use the Premium SKU key vaults and HSM-protected keys for production data, and only use Standard SKU key vaults and keys for testing and validation purposes.</span></span>

<span data-ttu-id="4fffb-187">키 자격 증명 모음에 공통된 도우미를 사용하며 키 자격 증명 모음 및 키의 사용 및 범위에 대한 약어를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="4fffb-187">Use a common prefix for key vaults and include an abbreviation of the use and scope of the key vault and keys.</span></span> <span data-ttu-id="4fffb-188">예를 들어 북미에 자격 증명 모음이 위치할 Contoso 서비스의 경우 가능한 이름 쌍은 Contoso-O365-NA-VaultA1 및 Contoso-O365-NA-VaultA2입니다.</span><span class="sxs-lookup"><span data-stu-id="4fffb-188">For example, for the Contoso service where the vaults will be located in North America, a possible pair of names is Contoso-O365-NA-VaultA1 and Contoso-O365-NA-VaultA2.</span></span> <span data-ttu-id="4fffb-189">자격 증명 모음 이름은 Azure 내에서 전역적으로 고유한 문자열이기 때문에 다른 Azure 고객이 원하는 이름을 이미 요구하는 경우 원하는 이름의 변형을 시도해야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4fffb-189">Vault names are globally unique strings within Azure, so you may need to try variations of your desired names in case the desired names are already claimed by other Azure customers.</span></span> <span data-ttu-id="4fffb-190">구성한 자격 증명 모음 이름은 변경할 수 없습니다. 따라서 설치 계획을 서면으로 작성하고 두 번째 사람을 사용하여 계획이 올바르게 실행되고 있는지 확인하는 것이 가장 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="4fffb-190">Once configured, vault names cannot be changed, so the best practice is to have a written plan for setup and use a second person to verify the plan is executed correctly.</span></span>

<span data-ttu-id="4fffb-191">가능한 경우 페어링되지 않은 지역에서 자격 증명 모음을 만드십시오.</span><span class="sxs-lookup"><span data-stu-id="4fffb-191">If possible, create your vaults in non-paired regions.</span></span> <span data-ttu-id="4fffb-192">페어링된 Azure 지역은 서비스 오류 도메인 전체에서 고가용성을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="4fffb-192">Paired Azure regions provide high availability across service failure domains.</span></span> <span data-ttu-id="4fffb-193">따라서 지역 쌍은 서로의 백업 지역으로 생각할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4fffb-193">Therefore, regional pairs can be thought of as each other's backup region.</span></span> <span data-ttu-id="4fffb-194">즉, 한 지역에 배치된 Azure 리소스가 페어링된 지역을 통해 내결점성을 자동으로 얻게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4fffb-194">This means that an Azure resource that is placed in one region is automatically gaining fault tolerance through the paired region.</span></span> <span data-ttu-id="4fffb-195">이러한 이유로 지역이 페어링된 데이터 암호화 정책에서 사용되는 두 자격 증명 모음에 대한 지역을 선택하면 총 두 개의 가용성 영역만 사용 중입니다.</span><span class="sxs-lookup"><span data-stu-id="4fffb-195">For this reason, choosing regions for two vaults used in a data encryption policy where the regions are paired means that only a total of two regions of availability are in use.</span></span> <span data-ttu-id="4fffb-196">대부분의 지역에는 두 개의 지역만 있으므로 페어링되지 않은 지역을 선택할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="4fffb-196">Most geographies only have two regions, so it's not yet possible to select non-paired regions.</span></span> <span data-ttu-id="4fffb-197">가능한 경우 데이터 암호화 정책과 함께 사용되는 두 자격 증명 모음에 대해 쌍으로 설정되지 않은 두 지역을 선택하십시오.</span><span class="sxs-lookup"><span data-stu-id="4fffb-197">If possible, choose two non-paired regions for the two vaults used with a data encryption policy.</span></span> <span data-ttu-id="4fffb-198">이 혜택은 총 네 가지 가용성 영역의 이점입니다.</span><span class="sxs-lookup"><span data-stu-id="4fffb-198">This benefits from a total of four regions of availability.</span></span> <span data-ttu-id="4fffb-199">자세한 내용은 [BCDR(비즈니스](https://docs.microsoft.com/azure/best-practices-availability-paired-regions) 연속성 및 재해 복구): 현재 지역 쌍 목록은 Azure 페어링된 지역을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="4fffb-199">For more information, see [Business continuity and disaster recovery (BCDR): Azure Paired Regions](https://docs.microsoft.com/azure/best-practices-availability-paired-regions) for a current list of regional pairs.</span></span>

### <a name="assign-permissions-to-each-key-vault"></a><span data-ttu-id="4fffb-200">각 키 자격 증명 모음에 사용 권한 할당</span><span class="sxs-lookup"><span data-stu-id="4fffb-200">Assign permissions to each key vault</span></span>

<span data-ttu-id="4fffb-201">각 키 자격 증명 모음에 대해 구현에 따라 고객 키에 대한 세 가지 사용 권한 집합을 정의해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4fffb-201">For each key vault, you will need to define three separate sets of permissions for Customer Key, depending on your implementation.</span></span> <span data-ttu-id="4fffb-202">예를 들어 다음 각 권한 집합에 대해 하나의 사용 권한 집합을 정의해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4fffb-202">For example, you will need to define one set of permissions for each of the following:</span></span>
  
- <span data-ttu-id="4fffb-203">**조직의 주요** 자격 증명 모음을 매일 관리하기 위한 주요 자격 증명 모음 관리자</span><span class="sxs-lookup"><span data-stu-id="4fffb-203">**Key vault administrators** that will perform day-to-day management of your key vault for your organization.</span></span> <span data-ttu-id="4fffb-204">이러한 작업에는 백업, 만들기, 가져오기, 가져오기, 목록 및 복원이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="4fffb-204">These tasks include backup, create, get, import, list, and restore.</span></span>

  > [!IMPORTANT]
  > <span data-ttu-id="4fffb-205">키 자격 증명 모음 관리자에게 할당된 권한 집합에는 키 삭제 권한이 포함되어 있지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="4fffb-205">The set of permissions assigned to key vault administrators does not include the permission to delete keys.</span></span> <span data-ttu-id="4fffb-206">이는 의도적인 것이고 중요한 사례입니다.</span><span class="sxs-lookup"><span data-stu-id="4fffb-206">This is intentional and an important practice.</span></span> <span data-ttu-id="4fffb-207">암호화 키를 삭제하는 작업은 일반적으로 수행되지 않습니다. 이렇게 하면 데이터가 영구적으로 삭제됩니다.</span><span class="sxs-lookup"><span data-stu-id="4fffb-207">Deleting encryption keys is not typically done, since doing so permanently destroys data.</span></span> <span data-ttu-id="4fffb-208">이 권한은 기본적으로 주요 자격 증명 모음 관리자에게 부여하지 않는 것이 가장 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="4fffb-208">As a best practice, do not grant this permission to key vault administrators by default.</span></span> <span data-ttu-id="4fffb-209">대신 주요 자격 증명 모음 참가자에 대해 이 정보를 예약하고 결과에 대한 명확한 이해가 있는 경우 단기적으로 관리자에게만 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="4fffb-209">Instead, reserve this for key vault contributors and only assign it to an administrator on a short term basis once a clear understanding of the consequences is understood.</span></span>
  
  <span data-ttu-id="4fffb-210">조직의 사용자에게 이러한 권한을 할당하려면 Azure PowerShell을 사용하여 Azure 구독에 로그인합니다.</span><span class="sxs-lookup"><span data-stu-id="4fffb-210">To assign these permissions to a user in your organization, log in to your Azure subscription with Azure PowerShell.</span></span> <span data-ttu-id="4fffb-211">자세한 내용은 [Azure PowerShell로 로그인을 참조하세요.](https://docs.microsoft.com/powershell/azure/authenticate-azureps)</span><span class="sxs-lookup"><span data-stu-id="4fffb-211">For instructions, see [Sign in with Azure PowerShell](https://docs.microsoft.com/powershell/azure/authenticate-azureps).</span></span>

   <span data-ttu-id="4fffb-212">Set-AzKeyVaultAccessPolicy cmdlet을 실행하여 필요한 사용 권한을 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="4fffb-212">Run the Set-AzKeyVaultAccessPolicy cmdlet to assign the necessary permissions.</span></span>

   ```powershell
   Set-AzKeyVaultAccessPolicy -VaultName <vault name> -UserPrincipalName <UPN of user> -PermissionsToKeys create,import,list,get,backup,restore
   ```

   <span data-ttu-id="4fffb-213">예시:</span><span class="sxs-lookup"><span data-stu-id="4fffb-213">For example:</span></span>

   ```powershell
   Set-AzKeyVaultAccessPolicy -VaultName Contoso-O365EX-NA-VaultA1 -UserPrincipalName alice@contoso.com -PermissionsToKeys create,import,list,get,backup,restore
   ```

- <span data-ttu-id="4fffb-214">Azure **Key Vault** 자체에 대한 사용 권한을 변경할 수 있는 주요 자격 증명 모음 참가자입니다.</span><span class="sxs-lookup"><span data-stu-id="4fffb-214">**Key vault contributors** that can change permissions on the Azure Key Vault itself.</span></span> <span data-ttu-id="4fffb-215">직원이 팀을 떠나거나 팀에 합류할 때 또는 키 자격 증명 모음 관리자가 키를 삭제하거나 복원할 수 있는 권한이 합법적으로 필요한 드문 상황에서 이러한 권한을 변경해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4fffb-215">You'll need to change these permissions as employees leave or join your team, or in the rare situation that the key vault administrators legitimately need permission to delete or restore a key.</span></span> <span data-ttu-id="4fffb-216">주요 자격 증명 모음 참가자 집합은 키 자격 증명 모음에 대한 참가자 역할을 부여해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4fffb-216">This set of key vault contributors needs to be granted the Contributor role on your key vault.</span></span> <span data-ttu-id="4fffb-217">Azure Resource Manager를 사용하여 이 역할을 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4fffb-217">You can assign this role by using Azure Resource Manager.</span></span> <span data-ttu-id="4fffb-218">자세한 단계는 [Role-Based](https://docs.microsoft.com/azure/active-directory/role-based-access-control-configure) 액세스 제어를 사용하여 Azure 구독 리소스에 대한 액세스를 관리하세요.</span><span class="sxs-lookup"><span data-stu-id="4fffb-218">For detailed steps, see [Use Role-Based Access Control](https://docs.microsoft.com/azure/active-directory/role-based-access-control-configure) to manage access to your Azure subscription resources.</span></span> <span data-ttu-id="4fffb-219">구독을 만드는 관리자는 기본적으로 이 액세스 권한과 참가자 역할에 다른 관리자를 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4fffb-219">The administrator who creates a subscription has this access by default, and the ability to assign other administrators to the Contributor role.</span></span>

- <span data-ttu-id="4fffb-220">테넌트 수준에서 고객 키의 작업을 하는 미사용 암호화 서비스의 **Microsoft 365** 데이터입니다.</span><span class="sxs-lookup"><span data-stu-id="4fffb-220">**Microsoft 365 data at rest encryption service** that does the work of Customer Key at the tenant level.</span></span> <span data-ttu-id="4fffb-221">Microsoft 365에 대한 사용 권한을 부여하려면 다음 구문을 사용하여 **Set-AzKeyVaultAccessPolicy** cmdlet을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="4fffb-221">To give permission to Microsoft 365, run the **Set-AzKeyVaultAccessPolicy** cmdlet using the following syntax:</span></span>

   ```powershell
   Set-AzKeyVaultAccessPolicy -VaultName <vault name> -PermissionsToKeys wrapKey,unwrapKey,get -ServicePrincipalName <Microsoft 365 appID>
   ```

  <span data-ttu-id="4fffb-222">여기서,</span><span class="sxs-lookup"><span data-stu-id="4fffb-222">Where:</span></span>

  - <span data-ttu-id="4fffb-223">*자격 증명* 모음 이름은 만든 키 자격 증명 모음의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="4fffb-223">*vault name* is the name of the key vault you created.</span></span>

  <span data-ttu-id="4fffb-224">예: Rest 암호화 서비스의 Microsoft 365 데이터에서 *Microsoft 365 appID를*`c066d759-24ae-40e7-a56f-027002b5d3e4`</span><span class="sxs-lookup"><span data-stu-id="4fffb-224">Example: For the Microsoft 365 Data at Rest Encryption service, replace  *Microsoft 365 appID* with `c066d759-24ae-40e7-a56f-027002b5d3e4`</span></span>

  ```powershell
  Set-AzKeyVaultAccessPolicy -VaultName Contoso-O365EX-NA-VaultA1 -PermissionsToKeys wrapKey,unwrapKey,get -ServicePrincipalName c066d759-24ae-40e7-a56f-027002b5d3e4
  ```

### <a name="enable-and-then-confirm-soft-delete-on-your-key-vaults"></a><span data-ttu-id="4fffb-225">키 자격 증명 모음에서 소프트 삭제를 사용하도록 설정한 다음 확인</span><span class="sxs-lookup"><span data-stu-id="4fffb-225">Enable and then confirm soft delete on your key vaults</span></span>

<span data-ttu-id="4fffb-226">키를 빠르게 복구할 수 있는 경우 실수로 또는 악의적으로 삭제된 키로 인해 확장된 서비스가 사용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="4fffb-226">When you can quickly recover your keys, you are less likely to experience an extended service outage due to accidentally or maliciously deleted keys.</span></span> <span data-ttu-id="4fffb-227">고객 키와 함께 키를 사용하려면 먼저 소프트 삭제라고 하는 이 구성을 사용하도록 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4fffb-227">Enable this configuration, referred to as Soft Delete, before you can use your keys with Customer Key.</span></span> <span data-ttu-id="4fffb-228">소프트 삭제를 사용하도록 설정하면 삭제 후 90일 이내에 키나 자격 증명 모음을 백업에서 복원하지 않고도 복구할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4fffb-228">Enabling Soft Delete allows you to recover keys or vaults within 90 days of deletion without having to restore them from backup.</span></span>
  
<span data-ttu-id="4fffb-229">키 자격 증명 모음에서 소프트 삭제를 사용하도록 설정하려면 다음 단계를 완료합니다.</span><span class="sxs-lookup"><span data-stu-id="4fffb-229">To enable Soft Delete on your key vaults, complete these steps:</span></span>
  
1. <span data-ttu-id="4fffb-230">사용자 계정을 사용하여 Azure 구독에 Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="4fffb-230">Sign in to your Azure subscription with Windows PowerShell.</span></span> <span data-ttu-id="4fffb-231">자세한 내용은 [Azure PowerShell로 로그인을 참조하세요.](https://docs.microsoft.com/powershell/azure/authenticate-azureps)</span><span class="sxs-lookup"><span data-stu-id="4fffb-231">For instructions, see [Sign in with Azure PowerShell](https://docs.microsoft.com/powershell/azure/authenticate-azureps).</span></span>

2. <span data-ttu-id="4fffb-232">[Get-AzKeyVault](https://docs.microsoft.com/powershell/module/az.keyvault/get-azkeyvault) cmdlet을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="4fffb-232">Run the [Get-AzKeyVault](https://docs.microsoft.com/powershell/module/az.keyvault/get-azkeyvault) cmdlet.</span></span> <span data-ttu-id="4fffb-233">이 예에서 *자격* 증명 모음 이름은 소프트 삭제를 사용하도록 설정하는 키 자격 증명 모음의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="4fffb-233">In this example, *vault name* is the name of the key vault for which you are enabling soft delete:</span></span>

   ```powershell
   $v = Get-AzKeyVault -VaultName <vault name>
   $r = Get-AzResource -ResourceId $v.ResourceId
   $r.Properties | Add-Member -MemberType NoteProperty -Name enableSoftDelete -Value 'True'
   Set-AzResource -ResourceId $r.ResourceId -Properties $r.Properties
   ```

3. <span data-ttu-id="4fffb-234">**Get-AzKeyVault** cmdlet을 실행하여 키 자격 증명 모음에 대해 소프트 삭제가 구성되어 있는지를 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4fffb-234">Confirm soft delete is configured for the key vault by running the **Get-AzKeyVault** cmdlet.</span></span> <span data-ttu-id="4fffb-235">키 자격 증명 모음에 대해 소프트 삭제가 제대로 구성되어 있는 경우 _Soft Delete Enabled_ 속성은 True 값을 **반환합니다.**</span><span class="sxs-lookup"><span data-stu-id="4fffb-235">If soft delete is configured properly for the key vault, then the _Soft Delete Enabled_ property returns a value of **True**:</span></span>

   ```powershell
   Get-AzKeyVault -VaultName <vault name> | fl
   ```

### <a name="add-a-key-to-each-key-vault-either-by-creating-or-importing-a-key"></a><span data-ttu-id="4fffb-236">키를 만들거나 가져와서 각 키 자격 증명 모음에 키 추가</span><span class="sxs-lookup"><span data-stu-id="4fffb-236">Add a key to each key vault either by creating or importing a key</span></span>

<span data-ttu-id="4fffb-237">Azure Key Vault에 키를 추가하는 방법에는 두 가지가 있습니다. 키 자격 증명 모음에서 직접 키를 만들거나 키를 가져올 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4fffb-237">There are two ways to add keys to an Azure Key Vault; you can create a key directly in Key Vault, or you can import a key.</span></span> <span data-ttu-id="4fffb-238">키 자격 증명 모음에서 직접 키를 만드는 것은 덜 복잡하지만 키를 가져오면 키 생성 방법을 완전히 제어할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4fffb-238">Creating a key directly in Key Vault is the less complicated method, while importing a key provides total control over how the key is generated.</span></span> <span data-ttu-id="4fffb-239">RSA 키를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="4fffb-239">Use the RSA keys.</span></span> <span data-ttu-id="4fffb-240">Azure Key Vault는 타원형 곡선 키로 래핑 및 래핑을 지원하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="4fffb-240">Azure Key Vault doesn't support wrapping and unwrapping with elliptical curve keys.</span></span>
  
<span data-ttu-id="4fffb-241">키 자격 증명 모음에서 직접 키를 만들 수 있도록 [Add-AzKeyVaultKey](https://docs.microsoft.com/powershell/module/az.keyvault/add-azkeyvaultkey) cmdlet을 다음과 같이 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="4fffb-241">To create a key directly in your key vault, run the [Add-AzKeyVaultKey](https://docs.microsoft.com/powershell/module/az.keyvault/add-azkeyvaultkey) cmdlet as follows:</span></span>
  
```powershell
Add-AzKeyVaultKey -VaultName <vault name> -Name <key name> -Destination <HSM|Software> -KeyOps wrapKey,unwrapKey
```

<span data-ttu-id="4fffb-242">여기서,</span><span class="sxs-lookup"><span data-stu-id="4fffb-242">Where:</span></span>

- <span data-ttu-id="4fffb-243">*자격 증명* 모음 이름은 키를 만들 키 자격 증명 모음의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="4fffb-243">*vault name* is the name of the key vault in which you want to create the key.</span></span>

- <span data-ttu-id="4fffb-244">*키 이름은* 새 키를 지정하려는 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="4fffb-244">*key name* is the name you want to give the new key.</span></span>

  > [!TIP]
  > <span data-ttu-id="4fffb-245">키 자격 증명에 대해 위에서 설명한 대로 유사한 명명 규칙을 사용하여 키의 이름을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="4fffb-245">Name keys using a similar naming convention as described above for key vaults.</span></span> <span data-ttu-id="4fffb-246">이렇게 하면 키 이름만 표시하는 도구에서 문자열이 자체 설명을 합니다.</span><span class="sxs-lookup"><span data-stu-id="4fffb-246">This way, in tools that show only the key name, the string is self-describing.</span></span>
  
<span data-ttu-id="4fffb-247">HSM을 사용하여 키를 보호하려는 경우 **HSM을** _Destination_ 매개 변수 값으로 지정해야 합니다. 그렇지 않으면 **Software를 지정합니다.**</span><span class="sxs-lookup"><span data-stu-id="4fffb-247">If you intend to protect the key with an HSM, ensure that you specify **HSM** as the value of the _Destination_ parameter, otherwise, specify **Software**.</span></span>

<span data-ttu-id="4fffb-248">예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="4fffb-248">For example,</span></span>
  
```powershell
Add-AzKeyVaultKey -VaultName Contoso-O365EX-NA-VaultA1 -Name Contoso-O365EX-NA-VaultA1-Key001 -Destination HSM -KeyOps wrapKey,unwrapKey
```

### <a name="check-the-recovery-level-of-your-keys"></a><span data-ttu-id="4fffb-249">키의 복구 수준 확인</span><span class="sxs-lookup"><span data-stu-id="4fffb-249">Check the recovery level of your keys</span></span>

<span data-ttu-id="4fffb-250">Microsoft 365를 사용하려면 Azure Key Vault 구독이 Do Not Cancel으로 설정되고 고객 키에서 사용하는 키가 소프트 삭제를 사용하도록 설정되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4fffb-250">Microsoft 365 requires that the Azure Key Vault subscription is set to Do Not Cancel and that the keys used by Customer Key have soft delete enabled.</span></span> <span data-ttu-id="4fffb-251">키의 복구 수준을 확인하여 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4fffb-251">You can confirm this by looking at the recovery level on your keys.</span></span>
  
<span data-ttu-id="4fffb-252">키의 복구 수준을 확인하기 위해 Azure PowerShell에서 다음과 Get-AzKeyVaultKey cmdlet을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="4fffb-252">To check the recovery level of a key, in Azure PowerShell, run the Get-AzKeyVaultKey cmdlet as follows:</span></span>
  
```powershell
(Get-AzKeyVaultKey -VaultName <vault name> -Name <key name>).Attributes
```

<span data-ttu-id="4fffb-253">Recovery _Level_ 속성이 **Recoverable+ProtectedSubscription** 값 외의 값을 반환하는 경우 이 문서를 검토하고 취소 금지 목록에 구독을 추가하고 각 키 자격 증명 모음에서 "소프트 삭제"를 사용하도록 설정한 모든 단계를 따라야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4fffb-253">If the _Recovery Level_ property returns anything other than a value of **Recoverable+ProtectedSubscription**, you will need to review this article and ensure that you have followed all of the steps to put the subscription on the Do Not Cancel list and that you enabled "soft delete" on each of your key vaults.</span></span> <span data-ttu-id="4fffb-254">다음으로, 전자 메일로 출력된 스크린샷을 `(Get-AzKeyVaultKey -VaultName <vault name> -Name <key name>).Attributes` m365ck@microsoft.com.</span><span class="sxs-lookup"><span data-stu-id="4fffb-254">Next, send a screenshot of the output of `(Get-AzKeyVaultKey -VaultName <vault name> -Name <key name>).Attributes` in email to m365ck@microsoft.com.</span></span>

### <a name="back-up-azure-key-vault"></a><span data-ttu-id="4fffb-255">Azure Key Vault 백업</span><span class="sxs-lookup"><span data-stu-id="4fffb-255">Back up Azure Key Vault</span></span>

<span data-ttu-id="4fffb-256">키를 만들거나 변경한 직후 온라인과 오프라인에서 백업을 수행하고 백업 복사본을 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="4fffb-256">Immediately following creation or any change to a key, perform a backup and store copies of the backup, both online and offline.</span></span> <span data-ttu-id="4fffb-257">오프라인 복사본을 네트워크에 연결하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="4fffb-257">Don't connect offline copies to any network.</span></span> <span data-ttu-id="4fffb-258">대신 물리적 안전 또는 상업용 저장소 시설에 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="4fffb-258">Instead, store them in a physical safe or commercial storage facility.</span></span> <span data-ttu-id="4fffb-259">재해가 발생할 경우 액세스할 수 있는 위치에 백업 복사본을 하나 이상 저장해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4fffb-259">At least one copy of the backup should be stored in a location that will be accessible if a disaster happens.</span></span> <span data-ttu-id="4fffb-260">키 자격 증명 모음 키를 영구적으로 삭제하거나 그렇지 않으면 사용할 수 없는 경우 백업 Blob은 키 자료를 복원하는 유일한 수단입니다.</span><span class="sxs-lookup"><span data-stu-id="4fffb-260">The backup blobs are the sole means of restoring key material should a Key Vault key be permanently destroyed or otherwise rendered inoperable.</span></span> <span data-ttu-id="4fffb-261">Azure Key Vault 외부에서 Azure Key Vault로 가져온 키는 고객 키에 필요한 메타데이터가 외부 키와 함께 존재하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="4fffb-261">Keys that are external to Azure Key Vault and were imported to Azure Key Vault do not qualify as a backup because the metadata necessary for Customer Key to use the key does not exist with the external key.</span></span> <span data-ttu-id="4fffb-262">Azure Key Vault에서 사용한 백업만 고객 키를 사용하여 복원 작업에 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4fffb-262">Only a backup taken from Azure Key Vault can be used for restore operations with Customer Key.</span></span> <span data-ttu-id="4fffb-263">따라서 키를 업로드하거나 만든 후 Azure Key Vault의 백업을 만들어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4fffb-263">Therefore, it is essential that you make a backup of Azure Key Vault once a key is uploaded or created.</span></span>
  
<span data-ttu-id="4fffb-264">Azure Key Vault 키의 백업을 만들 경우 다음과 같이 [Backup-AzKeyVaultKey](https://docs.microsoft.com/powershell/module/az.keyvault/backup-azkeyvaultkey) cmdlet을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="4fffb-264">To create a backup of an Azure Key Vault key, run the [Backup-AzKeyVaultKey](https://docs.microsoft.com/powershell/module/az.keyvault/backup-azkeyvaultkey) cmdlet as follows:</span></span>

```powershell
Backup-AzKeyVaultKey -VaultName <vault name> -Name <key name>
-OutputFile <filename.backup>
```

<span data-ttu-id="4fffb-265">출력 파일에 접미사가 사용되도록 `.backup` 합니다.</span><span class="sxs-lookup"><span data-stu-id="4fffb-265">Ensure that your output file uses the suffix `.backup`.</span></span>
  
<span data-ttu-id="4fffb-266">이 cmdlet에서 생성되는 출력 파일은 암호화되며 Azure Key Vault 외부에서는 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="4fffb-266">The output file resulting from this cmdlet is encrypted and cannot be used outside of Azure Key Vault.</span></span> <span data-ttu-id="4fffb-267">백업은 백업을 수행한 Azure 구독으로만 복원할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4fffb-267">The backup can be restored only to the Azure subscription from which the backup was taken.</span></span>
  
<span data-ttu-id="4fffb-268">예시:</span><span class="sxs-lookup"><span data-stu-id="4fffb-268">For example:</span></span>
  
```powershell
Backup-AzKeyVaultKey -VaultName Contoso-O365EX-NA-VaultA1 -Name Contoso-O365EX-NA-VaultA1-Key001 -OutputFile Contoso-O365EX-NA-VaultA1-Key001-Backup-20170802.backup
```

### <a name="validate-azure-key-vault-configuration-settings"></a><span data-ttu-id="4fffb-269">Azure Key Vault 구성 설정 유효성 검사</span><span class="sxs-lookup"><span data-stu-id="4fffb-269">Validate Azure Key Vault configuration settings</span></span>

<span data-ttu-id="4fffb-270">DEP에서 키를 사용하기 전에 유효성 검사를 수행하는 것은 선택 사항이지만 매우 권장됩니다.</span><span class="sxs-lookup"><span data-stu-id="4fffb-270">Performing validation before using keys in a DEP is optional, but highly recommended.</span></span> <span data-ttu-id="4fffb-271">특히 단계에 따라 이 항목에 설명된 키와 자격 증명 모음을 설정하는 경우 고객 키를 구성하기 전에 Azure Key Vault 리소스의 상태 유효성을 검사해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4fffb-271">In particular, if you use steps to set up your keys and vaults other than the ones described in this topic, you should validate the health of your Azure Key Vault resources before you configure Customer Key.</span></span>
  
<span data-ttu-id="4fffb-272">키가 Get, wrapKey 및 unwrapKey 작업을 사용하도록 설정되어 있는지 확인:</span><span class="sxs-lookup"><span data-stu-id="4fffb-272">To verify that your keys have get, wrapKey, and unwrapKey operations enabled:</span></span>
  
<span data-ttu-id="4fffb-273">[Get-AzKeyVault](https://docs.microsoft.com/powershell/module/az.keyvault/get-azkeyvault) cmdlet을 다음과 같이 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="4fffb-273">Run the [Get-AzKeyVault](https://docs.microsoft.com/powershell/module/az.keyvault/get-azkeyvault) cmdlet as follows:</span></span>
  
```powershell
Get-AzKeyVault -VaultName <vault name>
```

<span data-ttu-id="4fffb-274">출력에서 액세스 정책과 Microsoft 365 GUID(앱 ID)를 적절하게 찾아 봐야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4fffb-274">In the output, look for the Access Policy and for the Microsoft 365 app ID (GUID) as appropriate.</span></span> <span data-ttu-id="4fffb-275">Get, wrapKey 및 unwrapKey의 세 가지 작업은 모두 키에 대한 사용 권한 아래에 표시되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4fffb-275">All three operations, get, wrapKey, and unwrapKey, must be shown under Permissions to Keys.</span></span>
  
<span data-ttu-id="4fffb-276">액세스 정책 구성이 올바르지 않은 경우 다음과 Set-AzKeyVaultAccessPolicy cmdlet을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="4fffb-276">If the access policy configuration is incorrect, run the Set-AzKeyVaultAccessPolicy cmdlet as follows:</span></span>
  
```powershell
Set-AzKeyVaultAccessPolicy -VaultName <vault name> -PermissionsToKeys wrapKey,unwrapKey,get -ServicePrincipalName <Microsoft 365 appID>
```

<span data-ttu-id="4fffb-277">예: Rest 암호화 서비스의 Microsoft 365 데이터에서 *Microsoft 365 appID를*`c066d759-24ae-40e7-a56f-027002b5d3e4`</span><span class="sxs-lookup"><span data-stu-id="4fffb-277">Example: For the Microsoft 365 Data at Rest Encryption service, replace  *Microsoft 365 appID* with `c066d759-24ae-40e7-a56f-027002b5d3e4`</span></span>

  ```powershell
  Set-AzKeyVaultAccessPolicy -VaultName Contoso-O365EX-NA-VaultA1 -PermissionsToKeys wrapKey,unwrapKey,get -ServicePrincipalName c066d759-24ae-40e7-a56f-027002b5d3e4
  ```

<span data-ttu-id="4fffb-278">키에 대한 만료 날짜가 설정되어 있지 않은지 확인하기 위해 다음과 같이 [Get-AzKeyVaultKey](https://docs.microsoft.com/powershell/module/az.keyvault/get-azkeyvault) cmdlet을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="4fffb-278">To verify that an expiration date is not set for your keys, run the [Get-AzKeyVaultKey](https://docs.microsoft.com/powershell/module/az.keyvault/get-azkeyvault) cmdlet as follows:</span></span>
  
```powershell
Get-AzKeyVaultKey -VaultName <vault name>
```

<span data-ttu-id="4fffb-279">만료된 키는 고객 키에서 사용할 수 없습니다. 만료된 키로 시도한 작업이 실패하여 서비스 작동이 종료될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4fffb-279">An expired key cannot be used by Customer Key and operations attempted with an expired key will fail and possibly result in a service outage.</span></span> <span data-ttu-id="4fffb-280">고객 키와 함께 사용되는 키에는 만료 날짜가 없는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="4fffb-280">We strongly recommend that keys used with Customer Key do not have an expiration date.</span></span> <span data-ttu-id="4fffb-281">일단 설정된 만료 날짜는 제거할 수 없지만 다른 날짜로 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4fffb-281">An expiration date, once set, cannot be removed, but can be changed to a different date.</span></span> <span data-ttu-id="4fffb-282">만료 날짜가 설정된 키를 사용하려면 만료 값을 9999년 12월 31일로 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="4fffb-282">If a key must be used that has an expiration date set, change the expiration value to 12/31/9999.</span></span> <span data-ttu-id="4fffb-283">만료 날짜가 12/31/9999가 아닌 날짜로 설정된 키는 Microsoft 365 유효성 검사를 통과하지 못합니다.</span><span class="sxs-lookup"><span data-stu-id="4fffb-283">Keys with an expiration date set to a date other than 12/31/9999 will not pass Microsoft 365 validation.</span></span>
  
<span data-ttu-id="4fffb-284">9999년 12월 31일이 아니라 다른 값으로 설정된 만료 날짜를 변경하기 위해 다음과 같이 [Update-AzKeyVaultKey](https://docs.microsoft.com/powershell/module/az.keyvault/update-azkeyvaultkey) cmdlet을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="4fffb-284">To change an expiration date that has been set to any value other than 12/31/9999, run the [Update-AzKeyVaultKey](https://docs.microsoft.com/powershell/module/az.keyvault/update-azkeyvaultkey) cmdlet as follows:</span></span>
  
```powershell
Update-AzKeyVaultKey -VaultName <vault name> -Name <key name> -Expires (Get-Date -Date "12/31/9999")
```

### <a name="obtain-the-uri-for-each-azure-key-vault-key"></a><span data-ttu-id="4fffb-285">각 Azure Key Vault 키에 대한 URI 획득</span><span class="sxs-lookup"><span data-stu-id="4fffb-285">Obtain the URI for each Azure Key Vault key</span></span>

<span data-ttu-id="4fffb-286">Azure의 모든 단계를 완료하여 키 자격 증명 모음을 설정하고 키를 추가한 후 다음 명령을 실행하여 각 키 자격 증명 모음의 키에 대한 URI를 얻습니다.</span><span class="sxs-lookup"><span data-stu-id="4fffb-286">Once you've completed all the steps in Azure to set up your key vaults and added your keys, run the following command to get the URI for the key in each key vault.</span></span> <span data-ttu-id="4fffb-287">나중에 각 DEP를 만들고 할당할 때 이러한 URIS를 사용하여 이 정보를 안전한 장소에 저장해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4fffb-287">You will need to use these URIs when you create and assign each DEP later, so save this information in a safe place.</span></span> <span data-ttu-id="4fffb-288">각 키 자격 증명 모음에 대해 이 명령을 한 번 실행해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4fffb-288">Remember to run this command once for each key vault.</span></span>
  
<span data-ttu-id="4fffb-289">Azure PowerShell에서:</span><span class="sxs-lookup"><span data-stu-id="4fffb-289">In Azure PowerShell:</span></span>
  
```powershell
(Get-AzKeyVaultKey -VaultName <vault name>).Id
```

## <a name="set-up-the-customer-key-encryption-policy-for-your-tenant"></a><span data-ttu-id="4fffb-290">테넌트에 대한 고객 키 암호화 정책 설정</span><span class="sxs-lookup"><span data-stu-id="4fffb-290">Set up the Customer Key encryption policy for your tenant</span></span>

<span data-ttu-id="4fffb-291">이러한 cmdlet을 실행하려면 먼저 사용 권한을 할당해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4fffb-291">You need to be assigned permissions before you can run these cmdlets.</span></span> <span data-ttu-id="4fffb-292">이 문서에서는 cmdlet의 모든 매개 변수를 나열하기는 하지만 사용자에게 할당된 사용 권한에 포함되지 않은 일부 매개 변수에는 액세스할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="4fffb-292">Although this article lists all parameters for the cmdlets, you may not have access to some parameters if they're not included in the permissions assigned to you.</span></span> <span data-ttu-id="4fffb-293">조직에서 cmdlet 또는 매개 변수를 실행하는 데 필요한 사용 권한을 확인하려면 [Find the permissions required to run any Exchange cmdlet](https://docs.microsoft.com/powershell/exchange/exchange-server/find-exchange-cmdlet-permissions)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="4fffb-293">To find the permissions required to run any cmdlet or parameter in your organization, see [Find the permissions required to run any Exchange cmdlet](https://docs.microsoft.com/powershell/exchange/exchange-server/find-exchange-cmdlet-permissions).</span></span>

### <a name="create-policy"></a><span data-ttu-id="4fffb-294">정책 만들기</span><span class="sxs-lookup"><span data-stu-id="4fffb-294">Create policy</span></span>

```powershell
   New-M365DataAtRestEncryptionPolicy [-Name] <String> -AzureKeyIDs <MultiValuedProperty> [-Description <String>] [-Enabled <Boolean>]
```

<span data-ttu-id="4fffb-295">설명: 준수 관리자가 두 개의 AKV 루트 키를 사용하여 DEP(새 데이터 암호화 정책)를 만들 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="4fffb-295">Description: Enable compliance admin to create a new data encryption policy (DEP) using two AKV root keys.</span></span> <span data-ttu-id="4fffb-296">만든 정책은 cmdlet을 사용하여 할당할 Set-M365DataAtRestEncryptionPolicy 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4fffb-296">Once created, a policy can then be assigned using Set-M365DataAtRestEncryptionPolicy cmdlet.</span></span> <span data-ttu-id="4fffb-297">키를 처음 할당하거나 키를 회전한 후 새 키를 적용하는 데 최대 24시간이 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4fffb-297">Upon first assignment of keys or after you rotate keys, it can take up to 24 hours for the new keys to take effect.</span></span> <span data-ttu-id="4fffb-298">새 DEP를 적용하는 데 24시간 이상 소요된 경우 Microsoft에 문의합니다.</span><span class="sxs-lookup"><span data-stu-id="4fffb-298">If the new DEP takes more than 24 hours to take effect, contact Microsoft.</span></span>

<span data-ttu-id="4fffb-299">예제:</span><span class="sxs-lookup"><span data-stu-id="4fffb-299">Example:</span></span>

```powershell
New-M365DataAtRestEncryptionPolicy -Name "Default_Policy" -AzureKeyIDs "https://contosoWestUSvault01.vault.azure.net/keys/Key_01","https://contosoEastUSvault01.vault.azure.net/keys/Key_02" -Description "Tenant default policy"
```

<span data-ttu-id="4fffb-300">매개 변수:</span><span class="sxs-lookup"><span data-stu-id="4fffb-300">Parameters:</span></span>

| <span data-ttu-id="4fffb-301">이름</span><span class="sxs-lookup"><span data-stu-id="4fffb-301">Name</span></span> | <span data-ttu-id="4fffb-302">설명</span><span class="sxs-lookup"><span data-stu-id="4fffb-302">Description</span></span> | <span data-ttu-id="4fffb-303">선택 사항(Y/N)</span><span class="sxs-lookup"><span data-stu-id="4fffb-303">Optional (Y/N)</span></span> |
|--|--|--|
|<span data-ttu-id="4fffb-304">이름</span><span class="sxs-lookup"><span data-stu-id="4fffb-304">Name</span></span>|<span data-ttu-id="4fffb-305">데이터 암호화 정책의 이름</span><span class="sxs-lookup"><span data-stu-id="4fffb-305">Friendly name of the data encryption policy</span></span>|<span data-ttu-id="4fffb-306">N</span><span class="sxs-lookup"><span data-stu-id="4fffb-306">N</span></span>|
|<span data-ttu-id="4fffb-307">AzureKeyIDs</span><span class="sxs-lookup"><span data-stu-id="4fffb-307">AzureKeyIDs</span></span>|<span data-ttu-id="4fffb-308">데이터 암호화 정책과 연결하기 위해 Azure Key Vault 키의 URI 값 두 개를 콤보로 구분하여 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="4fffb-308">Specifies two URI values of the Azure Key Vault keys, separated by a comma, to associate with the data encryption policy</span></span>|<span data-ttu-id="4fffb-309">N</span><span class="sxs-lookup"><span data-stu-id="4fffb-309">N</span></span>|
|<span data-ttu-id="4fffb-310">설명</span><span class="sxs-lookup"><span data-stu-id="4fffb-310">Description</span></span>|<span data-ttu-id="4fffb-311">데이터 암호화 정책에 대한 설명</span><span class="sxs-lookup"><span data-stu-id="4fffb-311">Description of the data encryption policy</span></span>|<span data-ttu-id="4fffb-312">N</span><span class="sxs-lookup"><span data-stu-id="4fffb-312">N</span></span>|

### <a name="assign-policy"></a><span data-ttu-id="4fffb-313">정책 할당</span><span class="sxs-lookup"><span data-stu-id="4fffb-313">Assign policy</span></span>

```powershell
Set-M365DataAtRestEncryptionPolicyAssignment -Policy “<Default_PolicyName or Default_PolicyID>”
```

<span data-ttu-id="4fffb-314">설명: 이 cmdlet은 기본 데이터 암호화 정책을 구성하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="4fffb-314">Description: This cmdlet is used for configuring default Data Encryption Policy.</span></span> <span data-ttu-id="4fffb-315">이 정책은 모든 지원 워크로드에서 데이터를 암호화하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="4fffb-315">This policy will be used to then encrypt data across all support workloads.</span></span> 

<span data-ttu-id="4fffb-316">예제:</span><span class="sxs-lookup"><span data-stu-id="4fffb-316">Example:</span></span>

```powershell
Set-M365DataAtRestEncryptionPolicyAssignment -Policy “Tenant default policy”
```

<span data-ttu-id="4fffb-317">매개 변수:</span><span class="sxs-lookup"><span data-stu-id="4fffb-317">Parameters:</span></span>
| <span data-ttu-id="4fffb-318">이름</span><span class="sxs-lookup"><span data-stu-id="4fffb-318">Name</span></span> | <span data-ttu-id="4fffb-319">설명</span><span class="sxs-lookup"><span data-stu-id="4fffb-319">Description</span></span> | <span data-ttu-id="4fffb-320">선택 사항(Y/N)</span><span class="sxs-lookup"><span data-stu-id="4fffb-320">Optional (Y/N)</span></span> |
|--|--|--|
<span data-ttu-id="4fffb-321">-Policy</span><span class="sxs-lookup"><span data-stu-id="4fffb-321">-Policy</span></span>|<span data-ttu-id="4fffb-322">할당해야 하는 데이터 암호화 정책을 지정합니다. 정책 이름 또는 정책 ID를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="4fffb-322">Specifies the data encryption policy that needs to be assigned; specify either the Policy Name or the Policy ID.</span></span>|<span data-ttu-id="4fffb-323">N</span><span class="sxs-lookup"><span data-stu-id="4fffb-323">N</span></span>|

### <a name="modify-or-refresh-policy"></a><span data-ttu-id="4fffb-324">정책 수정 또는 새로 고침</span><span class="sxs-lookup"><span data-stu-id="4fffb-324">Modify or Refresh policy</span></span>

```powershell
Set-M365DataAtRestEncryptionPolicy [-Identity] < M365DataAtRestEncryptionPolicy DataEncryptionPolicyIdParameter> -Refresh [-Enabled <Boolean>] [-Name <String>] [-Description <String>]
```

<span data-ttu-id="4fffb-325">설명: 이 cmdlet을 사용하여 기존 정책을 수정하거나 새로 고칠 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4fffb-325">Description: The cmdlet can be used either to modify or refresh an existing policy.</span></span> <span data-ttu-id="4fffb-326">또한 정책을 활성화 또는 비활성화하는 데 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4fffb-326">It can also be used to enable or disable a policy.</span></span> <span data-ttu-id="4fffb-327">키를 처음 할당하거나 키를 회전한 후 새 키를 적용하는 데 최대 24시간이 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4fffb-327">Upon first assignment of keys or after you rotate keys, it can take up to 24 hours for the new keys to take effect.</span></span> <span data-ttu-id="4fffb-328">새 DEP를 적용하는 데 24시간 이상 소요된 경우 Microsoft에 문의합니다.</span><span class="sxs-lookup"><span data-stu-id="4fffb-328">If the new DEP takes more than 24 hours to take effect, contact Microsoft.</span></span>

<span data-ttu-id="4fffb-329">예제:</span><span class="sxs-lookup"><span data-stu-id="4fffb-329">Examples:</span></span>

<span data-ttu-id="4fffb-330">데이터 암호화 정책을 사용하지 않도록 설정</span><span class="sxs-lookup"><span data-stu-id="4fffb-330">Disable a data encryption policy.</span></span>

```powershell
Set-M365DataAtRestEncryptionPolicy -Identity "NAM Policy" -Enabled $false
```

<span data-ttu-id="4fffb-331">데이터 암호화 정책을 새로 고침합니다.</span><span class="sxs-lookup"><span data-stu-id="4fffb-331">Refresh a data encryption policy.</span></span>

```powershell
Set-M365DataAtRestEncryptionPolicy -Identity “EUR Policy” -Refresh
```

<span data-ttu-id="4fffb-332">매개 변수:</span><span class="sxs-lookup"><span data-stu-id="4fffb-332">Parameters:</span></span>
| <span data-ttu-id="4fffb-333">이름</span><span class="sxs-lookup"><span data-stu-id="4fffb-333">Name</span></span> | <span data-ttu-id="4fffb-334">설명</span><span class="sxs-lookup"><span data-stu-id="4fffb-334">Description</span></span> | <span data-ttu-id="4fffb-335">선택 사항(Y/N)</span><span class="sxs-lookup"><span data-stu-id="4fffb-335">Optional (Y/N)</span></span> |
|--|--|--|
|<span data-ttu-id="4fffb-336">-Identity</span><span class="sxs-lookup"><span data-stu-id="4fffb-336">-Identity</span></span>|<span data-ttu-id="4fffb-337">수정할 데이터 암호화 정책을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="4fffb-337">Specifies the data encryption policy that you want to modify.</span></span>|<span data-ttu-id="4fffb-338">N</span><span class="sxs-lookup"><span data-stu-id="4fffb-338">N</span></span>|
|<span data-ttu-id="4fffb-339">-Refresh</span><span class="sxs-lookup"><span data-stu-id="4fffb-339">-Refresh</span></span>|<span data-ttu-id="4fffb-340">Azure Key Vault에서 연결된 키를 회전한 후 새로 고침 스위치를 사용하여 데이터 암호화 정책을 업데이트합니다.</span><span class="sxs-lookup"><span data-stu-id="4fffb-340">Use the Refresh switch to update the data encryption policy after you rotate any of the associated keys in the Azure Key Vault.</span></span> <span data-ttu-id="4fffb-341">이 스위치를 사용하면 값을 지정할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="4fffb-341">You don't need to specify a value with this switch.</span></span>|<span data-ttu-id="4fffb-342">Y</span><span class="sxs-lookup"><span data-stu-id="4fffb-342">Y</span></span>|
|<span data-ttu-id="4fffb-343">-Enabled</span><span class="sxs-lookup"><span data-stu-id="4fffb-343">-Enabled</span></span>|<span data-ttu-id="4fffb-344">Enabled 매개 변수는 데이터 암호화 정책을 사용하도록 설정하거나 사용하지 않도록 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="4fffb-344">The Enabled parameter enables or disable the data encryption policy.</span></span> <span data-ttu-id="4fffb-345">정책을 사용하지 않도록 설정하기 전에 테넌트에서 정책을 해제해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4fffb-345">Before you disable a policy, you must unassign it from your tenant.</span></span> <span data-ttu-id="4fffb-346">유효한 값은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="4fffb-346">Valid values are:</span></span></br > <span data-ttu-id="4fffb-347">$true: 정책 사용</span><span class="sxs-lookup"><span data-stu-id="4fffb-347">$true: The policy is enabled</span></span></br > <span data-ttu-id="4fffb-348">$true: 이 정책은 사용하도록 설정되어 있습니다. 이 값은 기본값입니다.
</span><span class="sxs-lookup"><span data-stu-id="4fffb-348">$false: The policy is disabled.</span></span>|<span data-ttu-id="4fffb-349">Y</span><span class="sxs-lookup"><span data-stu-id="4fffb-349">Y</span></span>|
|<span data-ttu-id="4fffb-350">-Name</span><span class="sxs-lookup"><span data-stu-id="4fffb-350">-Name</span></span>|<span data-ttu-id="4fffb-351">Name 매개 변수는 데이터 암호화 정책의 고유 이름을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="4fffb-351">The Name parameter specifies the unique name for the data encryption policy.</span></span>|<span data-ttu-id="4fffb-352">Y</span><span class="sxs-lookup"><span data-stu-id="4fffb-352">Y</span></span>
|<span data-ttu-id="4fffb-353">-Description</span><span class="sxs-lookup"><span data-stu-id="4fffb-353">-Description</span></span>|<span data-ttu-id="4fffb-354">Description 매개 변수는 데이터 암호화 정책에 대한 선택적 설명을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="4fffb-354">The Description parameter specifies an optional description for the data encryption policy.</span></span>|<span data-ttu-id="4fffb-355">Y</span><span class="sxs-lookup"><span data-stu-id="4fffb-355">Y</span></span>|

### <a name="get-policy-details"></a><span data-ttu-id="4fffb-356">정책 세부 정보 확인</span><span class="sxs-lookup"><span data-stu-id="4fffb-356">Get policy details</span></span>

```powershell
Get-M365DataAtRestEncryptionPolicy [-Identity] < M365DataAtRestEncryptionPolicy DataEncryptionPolicyIdParameter>
```

<span data-ttu-id="4fffb-357">설명: 이 cmdlet은 테넌트에 대해 만들어진 모든 M365DataAtRest 암호화 정책 또는 특정 정책에 대한 세부 정보를 나열합니다.</span><span class="sxs-lookup"><span data-stu-id="4fffb-357">Description: This cmdlet lists all of M365DataAtRest encryption policies that are created for the tenant or details about a specific policy.</span></span>

<span data-ttu-id="4fffb-358">예제:</span><span class="sxs-lookup"><span data-stu-id="4fffb-358">Examples:</span></span>

<span data-ttu-id="4fffb-359">이 예에서는 조직의 M365DatAtRest 암호화 정책 요약 목록을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="4fffb-359">This example returns a summary list of M365DatAtRest Encryption policies in the organization.</span></span>

```powershell
Get-M365DataAtRestEncryptionPolicy
```

<span data-ttu-id="4fffb-360">이 예에서는 "NAM Policy"라는 데이터 암호화 정책에 대한 자세한 정보를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="4fffb-360">This example returns detailed information for the data encryption policy named "NAM Policy".</span></span>

```powershell
Get-M365DataAtRestEncryptionPolicy -Identity "NAM Policy"
```

<span data-ttu-id="4fffb-361">매개 변수:</span><span class="sxs-lookup"><span data-stu-id="4fffb-361">Parameters:</span></span>

| <span data-ttu-id="4fffb-362">이름</span><span class="sxs-lookup"><span data-stu-id="4fffb-362">Name</span></span> | <span data-ttu-id="4fffb-363">설명</span><span class="sxs-lookup"><span data-stu-id="4fffb-363">Description</span></span> | <span data-ttu-id="4fffb-364">선택 사항(Y/N)</span><span class="sxs-lookup"><span data-stu-id="4fffb-364">Optional (Y/N)</span></span> |
|--|--|--|
|<span data-ttu-id="4fffb-365">-Identity</span><span class="sxs-lookup"><span data-stu-id="4fffb-365">-Identity</span></span>|<span data-ttu-id="4fffb-366">세부 정보를 나열할 데이터 암호화 정책을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="4fffb-366">Specifies the data encryption policy that you want to list the details for.</span></span>|<span data-ttu-id="4fffb-367">Y</span><span class="sxs-lookup"><span data-stu-id="4fffb-367">Y</span></span>|

### <a name="get-policy-assignment-info"></a><span data-ttu-id="4fffb-368">정책 할당 정보 보기</span><span class="sxs-lookup"><span data-stu-id="4fffb-368">Get policy assignment info</span></span>

```powershell
Get-M365DataAtRestEncryptionPolicyAssignment
```

<span data-ttu-id="4fffb-369">설명: 이 cmdlet은 현재 테넌트에 할당된 정책을 나열합니다.</span><span class="sxs-lookup"><span data-stu-id="4fffb-369">Description: This cmdlet lists the policy that’s currently assigned to the tenant.</span></span>

## <a name="offboarding-from-customer-key"></a><span data-ttu-id="4fffb-370">고객 키에서 오프보더</span><span class="sxs-lookup"><span data-stu-id="4fffb-370">Offboarding from Customer Key</span></span>

<span data-ttu-id="4fffb-371">Microsoft 관리 키로 되돌려야 하는 경우 다시 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4fffb-371">If you need to revert back to Microsoft-managed keys, you can.</span></span> <span data-ttu-id="4fffb-372">오프보드를 해제하면 각 개별 워크로드에서 지원하는 기본 암호화를 사용하여 데이터가 다시 암호화됩니다.</span><span class="sxs-lookup"><span data-stu-id="4fffb-372">When you offboard, your data is re-encrypted using default encryption supported by each individual workload.</span></span> <span data-ttu-id="4fffb-373">예를 들어 Exchange Online에서는 Microsoft에서 관리하는 키를 사용하여 기본 암호화를 지원할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4fffb-373">For example, Exchange Online supports default encryption using Microsoft-managed keys.</span></span>

<span data-ttu-id="4fffb-374">테넌트 수준에서 고객 키에서 테넌트의 등록을 해제하기로 결정한 경우 전자 메일을 통해 Microsoft에 연락하여 테넌트에 대한 서비스를 "사용하지 않도록 설정"하여 [m365ck@microsoft.com.](mailto:m365ck@microsoft.com)</span><span class="sxs-lookup"><span data-stu-id="4fffb-374">If you decided to offboard your tenant from Customer Key at the tenant level, reach out to Microsoft with a request through email to “disable” the service for the tenant at [m365ck@microsoft.com](mailto:m365ck@microsoft.com).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="4fffb-375">오프보더는 데이터 제거와는 동일하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="4fffb-375">Offboarding is not the same as a data purge.</span></span> <span data-ttu-id="4fffb-376">데이터를 삭제하면 조직 데이터가 Microsoft 365에서 영구적으로 삭제되고, 오프보더는 삭제되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="4fffb-376">A data purge permanently crypto-deletes your organization's data from Microsoft 365, offboarding does not.</span></span> <span data-ttu-id="4fffb-377">테넌트 수준 정책에 대한 데이터 제거는 수행할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="4fffb-377">You can't perform a data purge for a tenant-level policy.</span></span> <span data-ttu-id="4fffb-378">데이터 제거 경로에 대한 자세한 내용은 키 해지 및 데이터 제거 경로 프로세스 [시작을 참조하세요.](customer-key-manage.md#revoke-your-keys-and-start-the-data-purge-path-process)</span><span class="sxs-lookup"><span data-stu-id="4fffb-378">For information about data purge path, see [Revoke your keys and start the data purge path process](customer-key-manage.md#revoke-your-keys-and-start-the-data-purge-path-process).</span></span>

## <a name="about-the-availability-key"></a><span data-ttu-id="4fffb-379">가용성 키</span><span class="sxs-lookup"><span data-stu-id="4fffb-379">About the availability key</span></span>

<span data-ttu-id="4fffb-380">가용성 키에 대한 자세한 내용은 [가용성 키에 대한 자세한 내용을 참조하십시오.](customer-key-availability-key-understand.md)</span><span class="sxs-lookup"><span data-stu-id="4fffb-380">For information about the availability key, see [Learn about the availability key](customer-key-availability-key-understand.md).</span></span>

## <a name="key-rotation"></a><span data-ttu-id="4fffb-381">키 회전</span><span class="sxs-lookup"><span data-stu-id="4fffb-381">Key rotation</span></span>

<span data-ttu-id="4fffb-382">고객 키와 함께 사용되는 키 회전 또는 롤링에 대한 자세한 내용은 고객 키 또는 가용성 키 롤 또는 회전을 [참조하세요.](customer-key-availability-key-roll.md)</span><span class="sxs-lookup"><span data-stu-id="4fffb-382">For information about rotating or rolling keys used with Customer Key, see [Roll or rotate a Customer Key or an availability key](customer-key-availability-key-roll.md).</span></span> <span data-ttu-id="4fffb-383">새 버전의 키를 사용하기 위해 DEP를 업데이트하면 이 문서의 앞부분에서 설명한 대로 Set-M365DataAtRestEncryptionPolicy cmdlet을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="4fffb-383">When you update the DEP to use the new version of the keys, you'll run the Set-M365DataAtRestEncryptionPolicy cmdlet as described earlier in this article.</span></span>

## <a name="related-articles"></a><span data-ttu-id="4fffb-384">관련 문서:</span><span class="sxs-lookup"><span data-stu-id="4fffb-384">Related articles:</span></span>

- [<span data-ttu-id="4fffb-385">고객 키를 사용한 서비스 암호화</span><span class="sxs-lookup"><span data-stu-id="4fffb-385">Service encryption with Customer Key</span></span>](customer-key-overview.md)

- [<span data-ttu-id="4fffb-386">고객 키 또는 가용성 키 롤 또는 회전</span><span class="sxs-lookup"><span data-stu-id="4fffb-386">Roll or rotate a Customer Key or an availability key</span></span>](customer-key-availability-key-roll.md)

- [<span data-ttu-id="4fffb-387">가용성 키에 대해 자세히</span><span class="sxs-lookup"><span data-stu-id="4fffb-387">Learn about the availability key</span></span>](customer-key-availability-key-understand.md)

- [<span data-ttu-id="4fffb-388">서비스 암호화</span><span class="sxs-lookup"><span data-stu-id="4fffb-388">Service Encryption</span></span>](office-365-service-encryption.md)
