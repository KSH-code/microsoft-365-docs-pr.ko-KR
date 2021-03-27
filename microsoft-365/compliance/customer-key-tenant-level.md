---
title: 테넌트 수준에서의 Microsoft 365 고객 키(공개 미리보기)
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 3/26/2021
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
description: 테넌트 수준에서 Microsoft 365 내에서 데이터에 대한 고객 키를 설정하는 방법을 학습합니다.
ms.openlocfilehash: 811b153d5b0a472c6e542851fec45f1f42bca59b
ms.sourcegitcommit: 94fa3e57fa6505551d84ae7b458150dceff30db7
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/26/2021
ms.locfileid: "51394706"
---
# <a name="overview-of-customer-key-for-microsoft-365-at-the-tenant-level-public-preview"></a><span data-ttu-id="e0061-103">테넌트 수준의 Microsoft 365 고객 키 개요(공개 미리 보기)</span><span class="sxs-lookup"><span data-stu-id="e0061-103">Overview of Customer Key for Microsoft 365 at the tenant level (public preview)</span></span>

<span data-ttu-id="e0061-104">제공한 키를 사용하여 DEP(데이터 암호화 정책)를 만들어 테넌트에 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e0061-104">Using keys you provide, you can create a data encryption policy (DEP) and assign it to the tenant.</span></span> <span data-ttu-id="e0061-105">만드는 테넌트 전체 DEP는 다음 데이터를 암호화합니다.</span><span class="sxs-lookup"><span data-stu-id="e0061-105">The tenant-wide DEP you create encrypts the following data:</span></span>

- <span data-ttu-id="e0061-106">Teams 채팅 메시지(1:1 채팅, 그룹 채팅, 모임 채팅 및 채널 대화)</span><span class="sxs-lookup"><span data-stu-id="e0061-106">Teams chat messages (1:1 chats, group chats, meeting chats and channel conversations)</span></span>
- <span data-ttu-id="e0061-107">Teams 미디어 메시지(이미지, 코드, 비디오 메시지, 오디오 메시지, 위키 이미지)</span><span class="sxs-lookup"><span data-stu-id="e0061-107">Teams media messages (images, code snippets, video messages, audio messages, wiki images)</span></span>
- <span data-ttu-id="e0061-108">Teams 저장소에 저장된 Teams 통화 및 모임 녹음/녹화</span><span class="sxs-lookup"><span data-stu-id="e0061-108">Teams call and meeting recordings stored in Teams storage</span></span>
- <span data-ttu-id="e0061-109">Teams 채팅 알림</span><span class="sxs-lookup"><span data-stu-id="e0061-109">Teams chat notifications</span></span>
- <span data-ttu-id="e0061-110">Cortana의 Teams 채팅 제안</span><span class="sxs-lookup"><span data-stu-id="e0061-110">Teams chat suggestions by Cortana</span></span>
- <span data-ttu-id="e0061-111">Teams 상태 메시지</span><span class="sxs-lookup"><span data-stu-id="e0061-111">Teams status messages</span></span>
- <span data-ttu-id="e0061-112">Exchange Online에 대한 사용자 및 신호 정보</span><span class="sxs-lookup"><span data-stu-id="e0061-112">User and signal information for Exchange Online</span></span>
- <span data-ttu-id="e0061-113">응용 프로그램 수준에서 아직 암호화되지 않은 Exchange Online 사서함</span><span class="sxs-lookup"><span data-stu-id="e0061-113">Exchange Online mailboxes that aren't already encrypted Customer Key DEPs at the application level</span></span>
- <span data-ttu-id="e0061-114">MIP EDM(정확한 데이터 일치) 데이터 – (데이터 파일 스케마, 규칙 패키지 및 중요한 데이터를 해시하는 데 사용되는 솔트)</span><span class="sxs-lookup"><span data-stu-id="e0061-114">MIP exact data match (EDM) data – (data file schemas, rule packages, and the salts used to hash the sensitive data)</span></span>

<span data-ttu-id="e0061-115">Microsoft Information Protection 및 Microsoft Teams의 경우 테넌트 수준의 고객 키는 DEP를 테넌트에 할당한 시간부터 새 데이터를 암호화합니다.</span><span class="sxs-lookup"><span data-stu-id="e0061-115">For Microsoft Information Protection and Microsoft Teams, Customer Key at the tenant level encrypts new data from the time you assign the DEP to the tenant.</span></span> <span data-ttu-id="e0061-116">공개 미리 보기는 과거 데이터 암호화를 지원하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="e0061-116">Public preview doesn't support encrypting past data.</span></span> <span data-ttu-id="e0061-117">Exchange Online의 경우 고객 키는 모든 기존 및 새 데이터를 암호화합니다.</span><span class="sxs-lookup"><span data-stu-id="e0061-117">For Exchange Online, Customer Key encrypts all existing and new data.</span></span>

<span data-ttu-id="e0061-118">테넌트당 여러 DEP를 만들 수 있지만 한 때 하나의 DEP만 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e0061-118">You can create multiple DEPs per tenant but can only assign one DEP at a time.</span></span> <span data-ttu-id="e0061-119">DEP를 할당하면 암호화가 자동으로 시작되지만 테넌트의 크기에 따라 완료하는 데 시간이 다소 걸립니다.</span><span class="sxs-lookup"><span data-stu-id="e0061-119">When you assign the DEP, encryption begins automatically but takes some time to complete depending on the size of your tenant.</span></span>

## <a name="tenant-level-policies-add-broader-control-to-customer-key-for-microsoft-365"></a><span data-ttu-id="e0061-120">테넌트 수준 정책은 Microsoft 365의 고객 키에 더 광범위한 제어를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="e0061-120">Tenant level policies add broader control to Customer Key for Microsoft 365</span></span>

<span data-ttu-id="e0061-121">Exchange Online 및 Sharepoint Online에 대해 이미 고객 키를 설정한 경우 새 테넌트 수준 공개 미리 보기가 어떻게 설정되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e0061-121">If you already have Customer Key set up for Exchange Online and Sharepoint Online, here's how the new tenant-level public preview fits in.</span></span>

<span data-ttu-id="e0061-122">만든 테넌트 수준 암호화 정책은 Microsoft 365의 Microsoft Teams 및 Exchange Online 워크로드에 대한 모든 데이터를 암호화합니다.</span><span class="sxs-lookup"><span data-stu-id="e0061-122">The tenant-level encryption policy you create encrypts all data for the Microsoft Teams and Exchange Online workloads in Microsoft 365.</span></span> <span data-ttu-id="e0061-123">그러나 Exchange Online의 경우 개별 사서함에 이미 고객 키 DEP를 할당한 경우 테넌트 수준 정책은 해당 DEP를 다시 지정하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="e0061-123">However, for Exchange Online, if you have already assigned Customer Key DEPs to individual mailboxes, the tenant-level policy won't override those DEPs.</span></span> <span data-ttu-id="e0061-124">테넌트 수준 정책은 사서함 수준 고객 키 DEP가 아직 할당되지 않은 사서함만 암호화합니다.</span><span class="sxs-lookup"><span data-stu-id="e0061-124">The tenant-level policy will only encrypt mailboxes that aren't assigned a mailbox level Customer Key DEP already.</span></span> <span data-ttu-id="e0061-125">테넌트 수준 DEP를 사용하여 사용자 사서함을 암호화하면 모든 콘텐츠가 암호화됩니다.</span><span class="sxs-lookup"><span data-stu-id="e0061-125">When you encrypt a user mailbox using a tenant level DEP, all its content gets encrypted.</span></span> <span data-ttu-id="e0061-126">응용 프로그램 수준에서 DEP로 암호화된 서비스에 대한 자세한 내용은 고객 키를 사용하여 서비스 [암호화를 참조하세요.](customer-key-overview.md)</span><span class="sxs-lookup"><span data-stu-id="e0061-126">For information about what gets encrypted with a DEP at the application level, see [Service encryption with Customer Key](customer-key-overview.md).</span></span>

## <a name="data-that-isnt-encrypted-with-customer-key-at-the-tenant-level"></a><span data-ttu-id="e0061-127">테넌트 수준에서 고객 키로 암호화되지 않은 데이터</span><span class="sxs-lookup"><span data-stu-id="e0061-127">Data that isn't encrypted with Customer Key at the tenant level</span></span>

<span data-ttu-id="e0061-128">고객 키는 테넌트 수준에서 다음과 같은 유형의 데이터를 암호화하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="e0061-128">Customer Key doesn't encrypt the following types of data at the tenant level.</span></span> <span data-ttu-id="e0061-129">대신 Microsoft 365는 다른 유형의 암호화를 사용하여 이 데이터를 보호합니다.</span><span class="sxs-lookup"><span data-stu-id="e0061-129">Instead, Microsoft 365 uses other types of encryption to protect this data.</span></span>

- <span data-ttu-id="e0061-130">응용 프로그램 수준에서 고객 키 DEP를 사용하여 이미 암호화한 Exchange 온라인 사서함입니다.</span><span class="sxs-lookup"><span data-stu-id="e0061-130">Exchange online mailboxes that you've already encrypted using a Customer Key DEP at the application level.</span></span> <span data-ttu-id="e0061-131">고객 키 DEP가 할당되지 않은 사서함은 테넌트 수준 DEP를 사용하여 암호화됩니다.</span><span class="sxs-lookup"><span data-stu-id="e0061-131">Mailboxes that don't have a Customer Key DEP assigned to them will be encrypted using the tenant level DEP.</span></span> <span data-ttu-id="e0061-132">이러한 정렬은 일부 사서함이 테넌트 수준 DEP로 암호화되고 일부 사서함은 응용 프로그램 수준 DEP로 암호화되어 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e0061-132">This arrangement means that you may have some mailboxes encrypted with a tenant level DEP and some mailboxes encrypted with application level DEPs.</span></span>
- <span data-ttu-id="e0061-133">SharePoint 및 비즈니스용 OneDrive는 응용 프로그램 수준에서 고객 키를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="e0061-133">SharePoint and OneDrive for Business use Customer Key at the application level.</span></span> <span data-ttu-id="e0061-134">단일 DEP는 단일 지리적으로 SharePoint의 콘텐츠를 암호화합니다.</span><span class="sxs-lookup"><span data-stu-id="e0061-134">A single DEP encrypts content in SharePoint for a single geo.</span></span>
- <span data-ttu-id="e0061-135">비즈니스용 OneDrive 및 SharePoint에 저장된 Microsoft Teams 파일 및 일부 Teams 통화 및 모임 녹음/녹화는 SharePoint Online DEP에 의해 암호화됩니다.</span><span class="sxs-lookup"><span data-stu-id="e0061-135">Microsoft Teams files and some Teams call and meeting recordings saved in OneDrive for Business and SharePoint are encrypted by a SharePoint Online DEP.</span></span>

<span data-ttu-id="e0061-136">Microsoft 365용 고객 키에서 현재 지원되지 않는 워크로드 또는 시나리오</span><span class="sxs-lookup"><span data-stu-id="e0061-136">Any workloads or scenarios that aren't currently supported by Customer Key for Microsoft 365.</span></span>

- <span data-ttu-id="e0061-137">기타 Microsoft 365 작업(예: Yammer, Planner 등)</span><span class="sxs-lookup"><span data-stu-id="e0061-137">Other Microsoft 365 workloads such as Yammer, Planner, and so on.</span></span>
- <span data-ttu-id="e0061-138">Teams 라이브 이벤트 및 Q&라이브 이벤트에서 A를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="e0061-138">Teams Live Events and Q&A in Live Events.</span></span> <span data-ttu-id="e0061-139">Teams의 경우 테넌트 수준에서 고객 키로 암호화되지 않은 시나리오는 이 시나리오뿐입니다.</span><span class="sxs-lookup"><span data-stu-id="e0061-139">For Teams, this scenario is the only one that isn't encrypted by Customer Key at the tenant level.</span></span>

## <a name="set-up-customer-key-at-the-tenant-level-public-preview"></a><span data-ttu-id="e0061-140">테넌트 수준에서 고객 키 설정(공개 미리 보기)</span><span class="sxs-lookup"><span data-stu-id="e0061-140">Set up Customer Key at the tenant level (public preview)</span></span>

<span data-ttu-id="e0061-141">이러한 단계는 응용 프로그램 수준에서 고객 키를 설정하는 단계와 비슷하지만 동일하지는 않습니다.</span><span class="sxs-lookup"><span data-stu-id="e0061-141">These steps are similar but not identical to the steps for setting up Customer Key at the application level.</span></span> <span data-ttu-id="e0061-142">테스트 테넌트의 테스트 데이터와 함께 이 공개 미리 보기만 사용</span><span class="sxs-lookup"><span data-stu-id="e0061-142">Only use this public preview with test data in test tenants.</span></span> <span data-ttu-id="e0061-143">프로덕션 데이터나 프로덕션 환경에서는 이 릴리스를 사용하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="e0061-143">Don't use this release with production data or in your production environment.</span></span> <span data-ttu-id="e0061-144">고객 키의 프로덕션 배포가 이미 있는 경우 다음 단계를 사용하여 테스트 환경의 테넌트 수준에서 고객 키를 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e0061-144">If you already have a production deployment of Customer Key, use these steps to set up Customer Key at the tenant level in a test environment.</span></span> <span data-ttu-id="e0061-145">테넌트에 테넌트 수준 DEP를 할당한 후 유효성 검사 프로세스를 시작하고 질문이나 m365ck@microsoft.com 문의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e0061-145">Once you've assigned a tenant level DEP to your tenant, you can start the validation process and contact m365ck@microsoft.com with any questions or concerns.</span></span> <span data-ttu-id="e0061-146">[Microsoft 365의](https://aka.ms/CustomerKey/PublicPreviewValidation)미사용 데이터 암호화에 대한 유효성 검사 지침의 공개 미리 보기에서 문서화된 유효성 검사 단계를 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e0061-146">You can also find documented validation steps in the public preview of [Validation Instructions for Data-at-rest Encryption for Microsoft 365](https://aka.ms/CustomerKey/PublicPreviewValidation).</span></span>

<span data-ttu-id="e0061-147">Azure PowerShell에 원격으로 연결하여 이러한 대부분의 작업을 완료합니다.</span><span class="sxs-lookup"><span data-stu-id="e0061-147">You'll complete most of these tasks by remotely connecting to Azure PowerShell.</span></span> <span data-ttu-id="e0061-148">최상의 결과를 얻기 위해 Azure PowerShell 버전 4.4.0 이상을 사용하세요.</span><span class="sxs-lookup"><span data-stu-id="e0061-148">For best results, use version 4.4.0 or later of Azure PowerShell.</span></span>

<span data-ttu-id="e0061-149">시작하기 전에 다음을 수행해야 합니다:</span><span class="sxs-lookup"><span data-stu-id="e0061-149">Before you begin:</span></span>

- <span data-ttu-id="e0061-150">테넌트 수준에서 고객 키를 설정하려면 준수 관리자 역할이 있는 직장 또는 학교 계정을 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e0061-150">You'll need to use a work or school account that has the compliance admin role to set up Customer Key at the tenant level.</span></span>
- <span data-ttu-id="e0061-151">조직에 적합한 라이선스가 있는지 확인</span><span class="sxs-lookup"><span data-stu-id="e0061-151">Ensure that you have the appropriate licensing for your organization.</span></span> <span data-ttu-id="e0061-152">구독 또는 클라우드 서비스 공급자를 사용하여 유료로 기업계약 Azure 구독을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="e0061-152">Use a paid, invoiced Azure Subscription using either an Enterprise Agreement or a Cloud Service Provider.</span></span> <span data-ttu-id="e0061-153">Pay As You Go 요금제 또는 신용 카드를 사용하여 구입한 Azure 구독은 고객 키에 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="e0061-153">Azure Subscriptions purchased using Pay As You Go plans or using a credit card aren't supported for Customer Key.</span></span> <span data-ttu-id="e0061-154">2020년 4월 1일부터 Office 365의 고객 키는 Office 365 E5, Microsoft 365 E5, Microsoft 365 E5 규정 준수 및 Microsoft 365 E5 Information Protection & SKUS에서 제공됩니다.</span><span class="sxs-lookup"><span data-stu-id="e0061-154">Starting April 1, 2020, Customer Key in Office 365 is offered in Office 365 E5, Microsoft 365 E5, Microsoft 365 E5 Compliance, and Microsoft 365 E5 Information Protection & Governance SKUs.</span></span> <span data-ttu-id="e0061-155">Office 365 Advanced Compliance SKU는 더 이상 새 라이선스에 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="e0061-155">Office 365 Advanced Compliance SKU is no longer available for new licenses.</span></span> <span data-ttu-id="e0061-156">기존 Office 365 고급 준수 라이선스는 계속 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="e0061-156">Existing Office 365 Advanced Compliance licenses will continue to be supported.</span></span> <span data-ttu-id="e0061-157">테넌트에서 적절한 라이선스가 부여된 사용자 한 명 이상으로 서비스를 사용하도록 설정하는 동시에 서비스를 통해 혜택을 받은 모든 사용자에게 적절한 라이선스가 있는지도 확인해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e0061-157">While the service can be enabled with a minimum of one appropriately licensed user under the tenant, you should still make sure all users that benefit from the service have appropriate licenses.</span></span>

### <a name="create-two-new-azure-subscriptions"></a><span data-ttu-id="e0061-158">두 개의 새 Azure 구독 만들기</span><span class="sxs-lookup"><span data-stu-id="e0061-158">Create two new Azure subscriptions</span></span>

<span data-ttu-id="e0061-159">고객 키에는 각 DEP(데이터 암호화 정책)에 대해 두 개의 키가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="e0061-159">Customer Key requires two keys for each data encryption policy (DEP).</span></span> <span data-ttu-id="e0061-160">두 개의 키를 만들하려면 Azure 구독을 두 개 만들어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e0061-160">To create two keys, you must create two Azure subscriptions.</span></span> <span data-ttu-id="e0061-161">조직의 개별 구성원이 각 구독에서 하나의 키를 구성하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="e0061-161">As a best practice, Microsoft recommends that you have separate members of your organization configure one key in each subscription.</span></span> <span data-ttu-id="e0061-162">이러한 Azure 구독만 사용하여 Microsoft 365의 암호화 키를 관리합니다.</span><span class="sxs-lookup"><span data-stu-id="e0061-162">Only use these Azure subscriptions to administer encryption keys for Microsoft 365.</span></span> <span data-ttu-id="e0061-163">다음 지침에 따라 운영자 중 한 명을 실수로, 의도적으로 또는 악의적으로 삭제하거나, 그렇지 않으면 해당 운영자가 담당하는 키를 잘못 관리하지 않는 경우 조직을 보호할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e0061-163">Following these guidelines helps protect your organization in case one of your operators accidentally, intentionally, or maliciously deletes or otherwise mismanages the keys for which they are responsible.</span></span>

<span data-ttu-id="e0061-164">조직에 대해 만들 수 있는 Azure 구독 수에는 실질적인 제한이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="e0061-164">There is no practical limit to the number of Azure subscriptions that you can create for your organization.</span></span> <span data-ttu-id="e0061-165">이 모범 사례를 사용하면 사용자 오류의 영향을 최소화하면서 고객 키에서 사용하는 리소스를 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e0061-165">Following this best practice helps minimize the impact of human error while helping to manage the resources used by Customer Key.</span></span>

### <a name="register-azure-subscriptions-to-use-a-mandatory-retention-period"></a><span data-ttu-id="e0061-166">필수 보존 기간을 사용하기 위해 Azure 구독 등록</span><span class="sxs-lookup"><span data-stu-id="e0061-166">Register Azure subscriptions to use a mandatory retention period</span></span>

<span data-ttu-id="e0061-167">루트 암호화 키의 일시적 또는 영구적 손실은 서비스 작업에 지장이나 심지어는 비극적일 수 있으며 데이터가 손실될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e0061-167">The temporary or permanent loss of root encryption keys can be disruptive or even catastrophic to service operation and can result in data loss.</span></span> <span data-ttu-id="e0061-168">이러한 이유로 고객 키와 함께 사용되는 리소스에는 강력한 보호가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="e0061-168">For this reason, the resources used with Customer Key require strong protection.</span></span> <span data-ttu-id="e0061-169">고객 키와 함께 사용되는 모든 Azure 리소스는 기본 구성을 넘어 보호 메커니즘을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="e0061-169">All the Azure resources that are used with Customer Key offer protection mechanisms beyond the default configuration.</span></span> <span data-ttu-id="e0061-170">Azure 구독은 즉시 취소할 수 없는 취소를 방지하는 방식으로 태그를 지정하거나 등록할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e0061-170">Azure subscriptions can be tagged or registered in a way that will prevent immediate and irrevocable cancellation.</span></span> <span data-ttu-id="e0061-171">이 프로세스를 필수 보존 기간에 등록이라고 합니다.</span><span class="sxs-lookup"><span data-stu-id="e0061-171">This process is referred to as registering for a mandatory retention period.</span></span> <span data-ttu-id="e0061-172">필수 보존 기간 동안 Azure 구독을 등록하는 데 필요한 단계는 Microsoft와 공동 작업해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e0061-172">The steps required to register Azure subscriptions for a mandatory retention period require collaboration with the Microsoft.</span></span> <span data-ttu-id="e0061-173">이 프로세스는 영업일 5일까지 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e0061-173">This process can take up to five business days.</span></span> <span data-ttu-id="e0061-174">이전에는 이 프로세스를 "취소 금지"라고도 합니다.</span><span class="sxs-lookup"><span data-stu-id="e0061-174">Previously, this process was sometimes referred to as "Do Not Cancel".</span></span>
  
<span data-ttu-id="e0061-175">Microsoft 365 팀에 문의하기 전에 고객 키와 함께 사용하는 각 Azure 구독에 대해 다음 단계를 수행해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e0061-175">Before contacting the Microsoft 365 team, you must perform the following steps for each Azure subscription that you use with Customer Key.</span></span> <span data-ttu-id="e0061-176">시작하기 전에 [Azure PowerShell Az](/powershell/azure/new-azureps-module-az) 모듈을 설치해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e0061-176">Ensure that you have the [Azure PowerShell Az](/powershell/azure/new-azureps-module-az) module installed before you start.</span></span>

1. <span data-ttu-id="e0061-177">Azure PowerShell을 사용하여 로그인합니다.</span><span class="sxs-lookup"><span data-stu-id="e0061-177">Sign in with Azure PowerShell.</span></span> <span data-ttu-id="e0061-178">자세한 내용은 [Azure PowerShell로 로그인을 참조하세요.](/powershell/azure/authenticate-azureps)</span><span class="sxs-lookup"><span data-stu-id="e0061-178">For instructions, see [Sign in with Azure PowerShell](/powershell/azure/authenticate-azureps).</span></span>

2. <span data-ttu-id="e0061-179">Register-AzProviderFeature cmdlet을 실행하여 필수 보존 기간을 사용하기 위해 구독을 등록합니다.</span><span class="sxs-lookup"><span data-stu-id="e0061-179">Run the Register-AzProviderFeature cmdlet to register your subscriptions to use a mandatory retention period.</span></span> <span data-ttu-id="e0061-180">각 구독에 대해 이 작업을 수행하세요.</span><span class="sxs-lookup"><span data-stu-id="e0061-180">Perform this action for each subscription.</span></span>

   ```powershell
   Set-AzContext -SubscriptionId <SubscriptionId>
   Register-AzProviderFeature -FeatureName mandatoryRetentionPeriodEnabled -ProviderNamespace Microsoft.Resources
   ```

3. <span data-ttu-id="e0061-181">Microsoft에 문의하여 에서 프로세스를 [m365ck@microsoft.com.](mailto:m365ck@microsoft.com)</span><span class="sxs-lookup"><span data-stu-id="e0061-181">Contact Microsoft to have the process finalized at [m365ck@microsoft.com](mailto:m365ck@microsoft.com).</span></span> <span data-ttu-id="e0061-182">전자 메일에 다음 콘텐츠를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="e0061-182">Include the following content in your email:</span></span>

   <span data-ttu-id="e0061-183">**제목:** 고객 키 \<*Your tenant's fully-qualified domain name*\></span><span class="sxs-lookup"><span data-stu-id="e0061-183">**Subject**: Customer Key for \<*Your tenant's fully-qualified domain name*\></span></span>

   <span data-ttu-id="e0061-184">**본문:** 필수 보존 기간을 마무리할 구독 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="e0061-184">**Body**: Subscription IDs for which you want to have the mandatory retention period finalized.</span></span>
   <span data-ttu-id="e0061-185">각 구독에 대한 Get-AzProviderFeature 출력입니다.</span><span class="sxs-lookup"><span data-stu-id="e0061-185">The output of Get-AzProviderFeature for each subscription.</span></span>

   <span data-ttu-id="e0061-186">이 프로세스 완료를 위한 SLA(서비스 수준 계약)는 Microsoft에 필수 보존 기간을 사용하기 위해 구독을 등록했다는 알림을(확인)한 후 영업일 5일입니다.</span><span class="sxs-lookup"><span data-stu-id="e0061-186">The Service Level Agreement (SLA) for completion of this process is five business days once Microsoft has been notified (and verified) that you have registered your subscriptions to use a mandatory retention period.</span></span>

4. <span data-ttu-id="e0061-187">Microsoft로부터 등록이 완료되었습니다는 알림을 받으면 다음과 같이 Get-AzProviderFeature 등록 상태를 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="e0061-187">Once you receive notification from Microsoft that registration is complete, verify the status of your registration by running the Get-AzProviderFeature command as follows.</span></span> <span data-ttu-id="e0061-188">확인되면 Get-AzProviderFeature 명령은 Registration State 속성에 **대해 Registered** 값을 **반환합니다.**</span><span class="sxs-lookup"><span data-stu-id="e0061-188">If verified, the Get-AzProviderFeature command returns a value of **Registered** for the **Registration State** property.</span></span> <span data-ttu-id="e0061-189">각 구독에 대해 이 작업을 수행하세요.</span><span class="sxs-lookup"><span data-stu-id="e0061-189">Perform this action for each subscription.</span></span>

   ```powershell
   Set-AzContext -SubscriptionId <SubscriptionId>
   Get-AzProviderFeature -ProviderNamespace Microsoft.Resources -FeatureName mandatoryRetentionPeriodEnabled
   ```

5. <span data-ttu-id="e0061-190">프로세스를 완료하기 위해 Register-AzResourceProvider 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="e0061-190">To complete the process, run the Register-AzResourceProvider command.</span></span> <span data-ttu-id="e0061-191">각 구독에 대해 이 작업을 수행하세요.</span><span class="sxs-lookup"><span data-stu-id="e0061-191">Perform this action for each subscription.</span></span>

   ```powershell
   Set-AzContext -SubscriptionId <SubscriptionId>
   Register-AzResourceProvider -ProviderNamespace Microsoft.KeyVault
   ```

### <a name="create-a-premium-azure-key-vault-in-each-subscription"></a><span data-ttu-id="e0061-192">각 구독에서 프리미엄 Azure Key Vault 만들기</span><span class="sxs-lookup"><span data-stu-id="e0061-192">Create a premium Azure Key Vault in each subscription</span></span>

<span data-ttu-id="e0061-193">키 저장소를 만드는 단계는 Azure PowerShell 설치 및 시작, Azure 구독에 연결, 리소스 그룹 만들기 및 해당 리소스 그룹에 키 자격 증명 모음 만들기를 안내하는 [Azure Key Vault](/azure/key-vault/general/overview)시작에 설명되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e0061-193">The steps to create a key vault are documented in [Getting Started with Azure Key Vault](/azure/key-vault/general/overview), which guides you through installing and launching Azure PowerShell, connecting to your Azure subscription, creating a resource group, and creating a key vault in that resource group.</span></span>
  
<span data-ttu-id="e0061-194">키 자격 증명 모음을 만들 때 SKU(Standard 또는 Premium)를 선택해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e0061-194">When you create a key vault, you must choose a SKU: either Standard or Premium.</span></span> <span data-ttu-id="e0061-195">Standard SKU를 사용하면 Azure Key Vault 키를 소프트웨어로 보호할 수 있으며, HSM(하드웨어 보안 모듈) 키 보호가 없습니다. Premium SKU는 키 자격 증명 모음 키를 보호하기 위해 HSM을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e0061-195">The Standard SKU allows Azure Key Vault keys to be protected with software - there is no Hardware Security Module (HSM) key protection - and the Premium SKU allows the use of HSMs for protection of Key Vault keys.</span></span> <span data-ttu-id="e0061-196">Customer Key는 두 SKU 중 하나를 사용하는 주요 자격 증명 모음을 허용합니다. 그러나 Microsoft는 Premium SKU만 사용하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="e0061-196">Customer Key accepts key vaults that use either SKU, though Microsoft strongly recommends that you use only the Premium SKU.</span></span> <span data-ttu-id="e0061-197">두 형식의 키 중 하나를 사용하는 작업의 비용은 동일하기 때문에 비용의 유일한 차이점은 각 HSM으로 보호되는 키에 대한 월별 비용입니다.</span><span class="sxs-lookup"><span data-stu-id="e0061-197">The cost of operations with keys of either type is the same, so the only difference in cost is the cost per month for each HSM-protected key.</span></span> <span data-ttu-id="e0061-198">자세한 [내용은 Key Vault 가격을](https://azure.microsoft.com/pricing/details/key-vault/) 참조합니다.</span><span class="sxs-lookup"><span data-stu-id="e0061-198">See [Key Vault pricing](https://azure.microsoft.com/pricing/details/key-vault/) for details.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="e0061-199">프로덕션 데이터에는 Premium SKU 키 자격 증명 모음 및 HSM으로 보호된 키를 사용하며 테스트 및 유효성 검사를 위해 표준 SKU 키 자격 증명 모음 및 키만 사용하십시오.</span><span class="sxs-lookup"><span data-stu-id="e0061-199">Use the Premium SKU key vaults and HSM-protected keys for production data, and only use Standard SKU key vaults and keys for testing and validation purposes.</span></span>

<span data-ttu-id="e0061-200">키 자격 증명 모음에 공통적인 도형을 사용하며 키 자격 증명 모음 및 키의 사용 및 범위에 대한 약어를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="e0061-200">Use a common prefix for key vaults and include an abbreviation of the use and scope of the key vault and keys.</span></span> <span data-ttu-id="e0061-201">예를 들어 북미에 자격 증명 모음이 위치할 Contoso 서비스의 경우 가능한 이름 쌍은 Contoso-O365-NA-VaultA1 및 Contoso-O365-NA-VaultA2입니다.</span><span class="sxs-lookup"><span data-stu-id="e0061-201">For example, for the Contoso service where the vaults will be located in North America, a possible pair of names is Contoso-O365-NA-VaultA1 and Contoso-O365-NA-VaultA2.</span></span> <span data-ttu-id="e0061-202">자격 증명 모음 이름은 Azure 내에서 전역적으로 고유한 문자열이기 때문에 다른 Azure 고객이 원하는 이름을 이미 클레임할 경우 원하는 이름을 변형해 보아야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e0061-202">Vault names are globally unique strings within Azure, so you may need to try variations of your desired names in case the desired names are already claimed by other Azure customers.</span></span> <span data-ttu-id="e0061-203">구성한 자격 증명 모음 이름은 변경할 수 없습니다. 따라서 모범 사례는 설치에 대한 서면 계획을 세우고 두 번째 사람을 사용하여 계획이 올바르게 실행되고 있는지 확인하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="e0061-203">Once configured, vault names cannot be changed, so the best practice is to have a written plan for setup and use a second person to verify the plan is executed correctly.</span></span>

<span data-ttu-id="e0061-204">가능한 경우 페어링되지 않은 지역에서 자격 증명 모음을 만드십시오.</span><span class="sxs-lookup"><span data-stu-id="e0061-204">If possible, create your vaults in non-paired regions.</span></span> <span data-ttu-id="e0061-205">페어링된 Azure 지역은 서비스 오류 도메인 전체에서 고가용성을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="e0061-205">Paired Azure regions provide high availability across service failure domains.</span></span> <span data-ttu-id="e0061-206">따라서 지역 쌍은 서로의 백업 지역으로 생각할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e0061-206">Therefore, regional pairs can be thought of as each other's backup region.</span></span> <span data-ttu-id="e0061-207">한 지역에 배치된 Azure 리소스는 페어링된 지역을 통해 내결결성을 자동으로 얻게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e0061-207">An Azure resource that is placed in one region is automatically gaining fault tolerance through the paired region.</span></span> <span data-ttu-id="e0061-208">데이터 암호화 정책에서 사용되는 두 개의 자격 증명 모음에 대한 지역을 선택하면 총 두 개의 가용성 영역만 사용 중입니다.</span><span class="sxs-lookup"><span data-stu-id="e0061-208">Choosing regions for two vaults used in a data encryption policy where the regions are paired means that only a total of two regions of availability are in use.</span></span> <span data-ttu-id="e0061-209">대부분의 지역에는 두 개의 지역만 있으므로 페어링되지 않은 지역을 선택할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="e0061-209">Most geographies only have two regions, so it's not yet possible to select non-paired regions.</span></span> <span data-ttu-id="e0061-210">가능한 경우 데이터 암호화 정책과 함께 사용되는 두 자격 증명 모음에 대해 쌍으로 설정되지 않은 두 지역을 선택하세요.</span><span class="sxs-lookup"><span data-stu-id="e0061-210">If possible, choose two non-paired regions for the two vaults used with a data encryption policy.</span></span> <span data-ttu-id="e0061-211">이 시나리오는 총 4개의 가용성 영역의 이점을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="e0061-211">This scenario benefits from a total of four regions of availability.</span></span> <span data-ttu-id="e0061-212">자세한 내용은 비즈니스 연속성 및 재해 [복구(BCDR): 현재](/azure/best-practices-availability-paired-regions) 지역 쌍 목록은 Azure 페어링 지역을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="e0061-212">For more information, see [Business continuity and disaster recovery (BCDR): Azure Paired Regions](/azure/best-practices-availability-paired-regions) for a current list of regional pairs.</span></span>

### <a name="assign-permissions-to-each-key-vault"></a><span data-ttu-id="e0061-213">각 키 자격 증명 모음에 사용 권한 할당</span><span class="sxs-lookup"><span data-stu-id="e0061-213">Assign permissions to each key vault</span></span>

<span data-ttu-id="e0061-214">각 키 자격 증명 모음에 대해 구현에 따라 고객 키에 대한 세 가지 개별 사용 권한 집합을 정의해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e0061-214">For each key vault, you'll need to define three separate sets of permissions for Customer Key, depending on your implementation.</span></span> <span data-ttu-id="e0061-215">예를 들어 다음과 같은 각 권한 집합에 대해 하나의 사용 권한 집합을 정의해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e0061-215">For example, you'll need to define one set of permissions for each of these:</span></span>
  
- <span data-ttu-id="e0061-216">**조직의 키** 자격 증명 모음에 대한 매일 관리를 수행하는 주요 자격 증명 모음 관리자</span><span class="sxs-lookup"><span data-stu-id="e0061-216">**Key vault administrators** that will perform day-to-day management of your key vault for your organization.</span></span> <span data-ttu-id="e0061-217">이러한 작업에는 백업, 만들기, 가져오기, 가져오기, 목록 및 복원이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="e0061-217">These tasks include backup, create, get, import, list, and restore.</span></span>

  > [!IMPORTANT]
  > <span data-ttu-id="e0061-218">키 자격 증명 모음 관리자에게 할당된 권한 집합에는 키를 삭제할 수 있는 권한이 포함되어 있지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="e0061-218">The set of permissions assigned to key vault administrators does not include the permission to delete keys.</span></span> <span data-ttu-id="e0061-219">이는 의도적인 것이고 중요한 사례입니다.</span><span class="sxs-lookup"><span data-stu-id="e0061-219">This is intentional and an important practice.</span></span> <span data-ttu-id="e0061-220">암호화 키를 삭제하면 데이터가 영구적으로 삭제되는 것이 일반적이지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="e0061-220">Deleting encryption keys is not typically done, since doing so permanently destroys data.</span></span> <span data-ttu-id="e0061-221">이 권한은 기본적으로 주요 자격 증명 모음 관리자에게 부여하지 않는 것이 가장 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="e0061-221">As a best practice, do not grant this permission to key vault administrators by default.</span></span> <span data-ttu-id="e0061-222">대신 주요 자격 증명 모음 참가자에 대해 이 정보를 예약하고 결과에 대한 명확한 이해가 있는 경우 단기적으로 관리자에게 할당해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e0061-222">Instead, reserve this for key vault contributors and only assign it to an administrator on a short term basis once a clear understanding of the consequences is understood.</span></span>
  
  <span data-ttu-id="e0061-223">조직의 사용자에게 이러한 권한을 할당하려면 Azure PowerShell을 사용하여 Azure 구독에 로그인합니다.</span><span class="sxs-lookup"><span data-stu-id="e0061-223">To assign these permissions to a user in your organization, sign in to your Azure subscription with Azure PowerShell.</span></span> <span data-ttu-id="e0061-224">자세한 내용은 [Azure PowerShell로 로그인을 참조하세요.](/powershell/azure/authenticate-azureps)</span><span class="sxs-lookup"><span data-stu-id="e0061-224">For instructions, see [Sign in with Azure PowerShell](/powershell/azure/authenticate-azureps).</span></span>

   <span data-ttu-id="e0061-225">Set-AzKeyVaultAccessPolicy cmdlet을 실행하여 필요한 사용 권한을 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="e0061-225">Run the Set-AzKeyVaultAccessPolicy cmdlet to assign the necessary permissions.</span></span>

   ```powershell
   Set-AzKeyVaultAccessPolicy -VaultName <vault name> -UserPrincipalName <UPN of user> -PermissionsToKeys create,import,list,get,backup,restore
   ```

   <span data-ttu-id="e0061-226">예를 들어 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="e0061-226">For example:</span></span>

   ```powershell
   Set-AzKeyVaultAccessPolicy -VaultName Contoso-O365EX-NA-VaultA1 -UserPrincipalName alice@contoso.com -PermissionsToKeys create,import,list,get,backup,restore
   ```

- <span data-ttu-id="e0061-227">Azure **Key Vault** 자체에 대한 사용 권한을 변경할 수 있는 주요 자격 증명 모음 참가자입니다.</span><span class="sxs-lookup"><span data-stu-id="e0061-227">**Key vault contributors** that can change permissions on the Azure Key Vault itself.</span></span> <span data-ttu-id="e0061-228">직원이 팀을 떠나거나 팀에 합류할 때 또는 키 자격 증명 모음 관리자가 키를 삭제하거나 복원할 수 있는 권한이 필요한 드문 경우 이러한 권한을 변경해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e0061-228">You'll need to change these permissions as employees leave or join your team, or in the rare situation that the key vault administrators legitimately need permission to delete or restore a key.</span></span> <span data-ttu-id="e0061-229">이 주요 자격 증명 모음 참가자 집합에는 키 자격 증명 모음에 대한 참가자 역할을 부여해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e0061-229">This set of key vault contributors needs to be granted the Contributor role on your key vault.</span></span> <span data-ttu-id="e0061-230">Azure Resource Manager를 사용하여 이 역할을 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e0061-230">You can assign this role by using Azure Resource Manager.</span></span> <span data-ttu-id="e0061-231">자세한 단계는 Role-Based [액세스](/azure/active-directory/role-based-access-control-configure) 제어를 사용하여 Azure 구독 리소스에 대한 액세스를 관리하기를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="e0061-231">For detailed steps, see [Use Role-Based Access Control](/azure/active-directory/role-based-access-control-configure) to manage access to your Azure subscription resources.</span></span> <span data-ttu-id="e0061-232">구독을 만드는 관리자는 기본적으로 이 액세스 권한과 참가자 역할에 다른 관리자를 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e0061-232">The administrator who creates a subscription has this access by default, and the ability to assign other administrators to the Contributor role.</span></span>

- <span data-ttu-id="e0061-233">테넌트 수준에서 고객 키의 작업을 하는 미사용 암호화 서비스의 **Microsoft 365** 데이터입니다.</span><span class="sxs-lookup"><span data-stu-id="e0061-233">**Microsoft 365 data at rest encryption service** that does the work of Customer Key at the tenant level.</span></span> <span data-ttu-id="e0061-234">Microsoft 365에 대한 사용 권한을 부여하려면 다음 구문을 사용하여 **Set-AzKeyVaultAccessPolicy** cmdlet을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="e0061-234">To give permission to Microsoft 365, run the **Set-AzKeyVaultAccessPolicy** cmdlet using the following syntax:</span></span>

   ```powershell
   Set-AzKeyVaultAccessPolicy -VaultName <vault name> -PermissionsToKeys wrapKey,unwrapKey,get -ServicePrincipalName <Microsoft 365 appID>
   ```

  <span data-ttu-id="e0061-235">여기서,</span><span class="sxs-lookup"><span data-stu-id="e0061-235">Where:</span></span>

  - <span data-ttu-id="e0061-236">*자격 증명 모음* 이름은 만든 키 자격 증명 모음의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="e0061-236">*vault name* is the name of the key vault you created.</span></span>

  <span data-ttu-id="e0061-237">예: Rest 암호화 서비스의 Microsoft 365 데이터에서 *Microsoft 365 appID를*`c066d759-24ae-40e7-a56f-027002b5d3e4`</span><span class="sxs-lookup"><span data-stu-id="e0061-237">Example: For the Microsoft 365 Data at Rest Encryption service, replace  *Microsoft 365 appID* with `c066d759-24ae-40e7-a56f-027002b5d3e4`</span></span>

  ```powershell
  Set-AzKeyVaultAccessPolicy -VaultName Contoso-O365EX-NA-VaultA1 -PermissionsToKeys wrapKey,unwrapKey,get -ServicePrincipalName c066d759-24ae-40e7-a56f-027002b5d3e4
  ```

### <a name="enable-and-then-confirm-soft-delete-on-your-key-vaults"></a><span data-ttu-id="e0061-238">키 자격 증명 모음에서 소프트 삭제를 사용하도록 설정한 다음 확인</span><span class="sxs-lookup"><span data-stu-id="e0061-238">Enable and then confirm soft delete on your key vaults</span></span>

<span data-ttu-id="e0061-239">키를 빠르게 복구할 수 있는 경우 실수로 또는 악의적으로 삭제된 키로 인해 확장된 서비스가 사용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="e0061-239">When you can quickly recover your keys, you are less likely to experience an extended service outage due to accidentally or maliciously deleted keys.</span></span> <span data-ttu-id="e0061-240">고객 키와 함께 키를 사용하려면 먼저 소프트 삭제라고 하는 이 구성을 사용하도록 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e0061-240">Enable this configuration, referred to as Soft Delete, before you can use your keys with Customer Key.</span></span> <span data-ttu-id="e0061-241">소프트 삭제를 사용하도록 설정하면 백업에서 복원하지 않고도 삭제 후 90일 이내에 키나 자격 증명 모음을 복구할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e0061-241">Enabling Soft Delete allows you to recover keys or vaults within 90 days of deletion without having to restore them from backup.</span></span>
  
<span data-ttu-id="e0061-242">키 자격 증명 모음에서 소프트 삭제를 사용하도록 설정하려면 다음 단계를 완료합니다.</span><span class="sxs-lookup"><span data-stu-id="e0061-242">To enable Soft Delete on your key vaults, complete these steps:</span></span>
  
1. <span data-ttu-id="e0061-243">구독을 사용하여 Azure 구독에 Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="e0061-243">Sign in to your Azure subscription with Windows PowerShell.</span></span> <span data-ttu-id="e0061-244">자세한 내용은 [Azure PowerShell로 로그인을 참조하세요.](/powershell/azure/authenticate-azureps)</span><span class="sxs-lookup"><span data-stu-id="e0061-244">For instructions, see [Sign in with Azure PowerShell](/powershell/azure/authenticate-azureps).</span></span>

2. <span data-ttu-id="e0061-245">[Get-AzKeyVault](/powershell/module/az.keyvault/get-azkeyvault) cmdlet을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="e0061-245">Run the [Get-AzKeyVault](/powershell/module/az.keyvault/get-azkeyvault) cmdlet.</span></span> <span data-ttu-id="e0061-246">이 예에서 자격 증명 모음 *이름은* 소프트 삭제를 사용하도록 설정하는 키 자격 증명 모음의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="e0061-246">In this example, *vault name* is the name of the key vault for which you are enabling soft delete:</span></span>

   ```powershell
   $v = Get-AzKeyVault -VaultName <vault name>
   $r = Get-AzResource -ResourceId $v.ResourceId
   $r.Properties | Add-Member -MemberType NoteProperty -Name enableSoftDelete -Value 'True'
   Set-AzResource -ResourceId $r.ResourceId -Properties $r.Properties
   ```

3. <span data-ttu-id="e0061-247">**Get-AzKeyVault** cmdlet을 실행하여 키 자격 증명 모음에 대해 소프트 삭제가 구성되어 있는지 확인</span><span class="sxs-lookup"><span data-stu-id="e0061-247">Confirm soft delete is configured for the key vault by running the **Get-AzKeyVault** cmdlet.</span></span> <span data-ttu-id="e0061-248">키 자격 증명 모음에 대해 소프트 삭제가 제대로 구성되어 있는 경우 _Soft Delete Enabled_ 속성은 True 값을 **반환합니다.**</span><span class="sxs-lookup"><span data-stu-id="e0061-248">If soft delete is configured properly for the key vault, then the _Soft Delete Enabled_ property returns a value of **True**:</span></span>

   ```powershell
   Get-AzKeyVault -VaultName <vault name> | fl
   ```

### <a name="add-a-key-to-each-key-vault-either-by-creating-or-importing-a-key"></a><span data-ttu-id="e0061-249">키를 만들거나 가져와서 각 키 자격 증명 모음에 키 추가</span><span class="sxs-lookup"><span data-stu-id="e0061-249">Add a key to each key vault either by creating or importing a key</span></span>

<span data-ttu-id="e0061-250">Azure Key Vault에 키를 추가하는 방법에는 두 가지가 있습니다. 키 자격 증명 모음에서 직접 키를 만들거나 키를 가져올 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e0061-250">There are two ways to add keys to an Azure Key Vault; you can create a key directly in Key Vault, or you can import a key.</span></span> <span data-ttu-id="e0061-251">키 자격 증명 모음에서 직접 키를 만드는 것은 덜 복잡하지만 키를 가져오면 키 생성 방법을 완전히 제어할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e0061-251">Creating a key directly in Key Vault is the less complicated method, while importing a key provides total control over how the key is generated.</span></span> <span data-ttu-id="e0061-252">RSA 키를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="e0061-252">Use the RSA keys.</span></span> <span data-ttu-id="e0061-253">Azure Key Vault는 타원 곡선 키로 래핑 및 래핑을 지원하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="e0061-253">Azure Key Vault doesn't support wrapping and unwrapping with elliptical curve keys.</span></span>
  
<span data-ttu-id="e0061-254">키 자격 증명 모음에서 직접 키를 만들 수 있도록 [Add-AzKeyVaultKey](/powershell/module/az.keyvault/add-azkeyvaultkey) cmdlet을 다음과 같이 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="e0061-254">To create a key directly in your key vault, run the [Add-AzKeyVaultKey](/powershell/module/az.keyvault/add-azkeyvaultkey) cmdlet as follows:</span></span>
  
```powershell
Add-AzKeyVaultKey -VaultName <vault name> -Name <key name> -Destination <HSM|Software> -KeyOps wrapKey,unwrapKey
```

<span data-ttu-id="e0061-255">여기서,</span><span class="sxs-lookup"><span data-stu-id="e0061-255">Where:</span></span>

- <span data-ttu-id="e0061-256">*자격 증명* 모음 이름은 키를 만들 키 자격 증명 모음의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="e0061-256">*vault name* is the name of the key vault in which you want to create the key.</span></span>

- <span data-ttu-id="e0061-257">*key name은* 새 키를 제공하려는 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="e0061-257">*key name* is the name you want to give the new key.</span></span>

  > [!TIP]
  > <span data-ttu-id="e0061-258">키 자격 증명 모음에 대해 위에서 설명한 대로 유사한 명명 규칙을 사용하는 이름 키입니다.</span><span class="sxs-lookup"><span data-stu-id="e0061-258">Name keys using a similar naming convention as described above for key vaults.</span></span> <span data-ttu-id="e0061-259">이렇게 하면 키 이름만 표시하는 도구에서 문자열은 자체 설명을 합니다.</span><span class="sxs-lookup"><span data-stu-id="e0061-259">This way, in tools that show only the key name, the string is self-describing.</span></span>
  
<span data-ttu-id="e0061-260">HSM으로 키를 보호하려는 경우 **HSM을** _Destination_ 매개 변수 값으로 지정해야 합니다. 그렇지 않으면 Software 를 **지정합니다.**</span><span class="sxs-lookup"><span data-stu-id="e0061-260">If you intend to protect the key with an HSM, ensure that you specify **HSM** as the value of the _Destination_ parameter, otherwise, specify **Software**.</span></span>

<span data-ttu-id="e0061-261">예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="e0061-261">For example,</span></span>
  
```powershell
Add-AzKeyVaultKey -VaultName Contoso-O365EX-NA-VaultA1 -Name Contoso-O365EX-NA-VaultA1-Key001 -Destination HSM -KeyOps wrapKey,unwrapKey
```

### <a name="check-the-recovery-level-of-your-keys"></a><span data-ttu-id="e0061-262">키의 복구 수준 확인</span><span class="sxs-lookup"><span data-stu-id="e0061-262">Check the recovery level of your keys</span></span>

<span data-ttu-id="e0061-263">Microsoft 365를 사용하려면 Azure Key Vault 구독이 취소 금지로 설정되어 있으며 고객 키에서 사용하는 키가 소프트 삭제를 사용하도록 설정되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e0061-263">Microsoft 365 requires that the Azure Key Vault subscription is set to Do Not Cancel and that the keys used by Customer Key have soft delete enabled.</span></span> <span data-ttu-id="e0061-264">키의 복구 수준을 확인하여 이러한 설정을 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e0061-264">You can confirm these settings by looking at the recovery level on your keys.</span></span>
  
<span data-ttu-id="e0061-265">키의 복구 수준을 확인하기 위해 Azure PowerShell에서 다음과 Get-AzKeyVaultKey cmdlet을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="e0061-265">To check the recovery level of a key, in Azure PowerShell, run the Get-AzKeyVaultKey cmdlet as follows:</span></span>
  
```powershell
(Get-AzKeyVaultKey -VaultName <vault name> -Name <key name>).Attributes
```

<span data-ttu-id="e0061-266">Recovery _Level_ 속성이 **Recoverable+ProtectedSubscription** 값 외의 값을 반환하는 경우 이 문서를 검토하고 취소 금지 목록에 구독을 추가하고 각 키 자격 증명 모음에서 "소프트 삭제"를 사용하도록 설정한 모든 단계를 따라야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e0061-266">If the _Recovery Level_ property returns anything other than a value of **Recoverable+ProtectedSubscription**, you will need to review this article and ensure that you have followed all of the steps to put the subscription on the Do Not Cancel list and that you enabled "soft delete" on each of your key vaults.</span></span> <span data-ttu-id="e0061-267">다음으로, 전자 메일의 출력 스크린샷을 `(Get-AzKeyVaultKey -VaultName <vault name> -Name <key name>).Attributes` m365ck@microsoft.com.</span><span class="sxs-lookup"><span data-stu-id="e0061-267">Next, send a screenshot of the output of `(Get-AzKeyVaultKey -VaultName <vault name> -Name <key name>).Attributes` in email to m365ck@microsoft.com.</span></span>

### <a name="back-up-azure-key-vault"></a><span data-ttu-id="e0061-268">Azure Key Vault 백업</span><span class="sxs-lookup"><span data-stu-id="e0061-268">Back up Azure Key Vault</span></span>

<span data-ttu-id="e0061-269">키가 만들어지거나 변경된 직후에 키를 백업하고 온라인 및 오프라인으로 백업 복사본을 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="e0061-269">Immediately following creation or any change to a key, back up the key and store copies of the backup, both online and offline.</span></span> <span data-ttu-id="e0061-270">오프라인 복사본을 네트워크에 연결하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="e0061-270">Don't connect offline copies to any network.</span></span> <span data-ttu-id="e0061-271">대신 물리적 안전 또는 상업적 저장소 시설에 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="e0061-271">Instead, store them in a physical safe or commercial storage facility.</span></span> <span data-ttu-id="e0061-272">재해가 발생할 경우 액세스할 수 있는 위치에 백업 복사본을 하나 이상 저장해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e0061-272">At least one copy of the backup should be stored in a location that will be accessible if a disaster happens.</span></span> <span data-ttu-id="e0061-273">키 자격 증명 키를 영구적으로 삭제하거나 사용할 수 없는 경우 백업 Blob은 키 자료를 복원하는 유일한 수단입니다.</span><span class="sxs-lookup"><span data-stu-id="e0061-273">The backup blobs are the sole means of restoring key material should a Key Vault key be permanently destroyed or otherwise rendered inoperable.</span></span> <span data-ttu-id="e0061-274">Azure Key Vault 외부에 있으며 Azure Key Vault로 가져온 키는 고객 키가 키를 사용하는 데 필요한 메타데이터가 외부 키와 함께 존재하지 않는 때문에 백업으로 자격이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="e0061-274">Keys that are external to Azure Key Vault and were imported to Azure Key Vault don't qualify as a backup because the metadata necessary for Customer Key to use the key doesn't exist with the external key.</span></span> <span data-ttu-id="e0061-275">Azure Key Vault에서 수행한 백업만 고객 키를 사용하여 복원 작업에 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e0061-275">Only a backup taken from Azure Key Vault can be used for restore operations with Customer Key.</span></span> <span data-ttu-id="e0061-276">따라서 키를 업로드하거나 만든 후 Azure Key Vault의 백업을 만들어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e0061-276">So, it's essential that you make a backup of Azure Key Vault once a key is uploaded or created.</span></span>
  
<span data-ttu-id="e0061-277">Azure Key Vault 키의 백업을 만들 경우 다음과 같이 [Backup-AzKeyVaultKey](/powershell/module/az.keyvault/backup-azkeyvaultkey) cmdlet을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="e0061-277">To create a backup of an Azure Key Vault key, run the [Backup-AzKeyVaultKey](/powershell/module/az.keyvault/backup-azkeyvaultkey) cmdlet as follows:</span></span>

```powershell
Backup-AzKeyVaultKey -VaultName <vault name> -Name <key name>
-OutputFile <filename.backup>
```

<span data-ttu-id="e0061-278">출력 파일에서 접미사 를 사용하는지 `.backup` 확인</span><span class="sxs-lookup"><span data-stu-id="e0061-278">Ensure that your output file uses the suffix `.backup`.</span></span>
  
<span data-ttu-id="e0061-279">이 cmdlet에서 생성되는 출력 파일은 암호화되며 Azure Key Vault 외부에서 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="e0061-279">The output file resulting from this cmdlet is encrypted and cannot be used outside of Azure Key Vault.</span></span> <span data-ttu-id="e0061-280">백업은 백업을 수행한 Azure 구독으로만 복원할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e0061-280">The backup can be restored only to the Azure subscription from which the backup was taken.</span></span>
  
<span data-ttu-id="e0061-281">예를 들어 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="e0061-281">For example:</span></span>
  
```powershell
Backup-AzKeyVaultKey -VaultName Contoso-O365EX-NA-VaultA1 -Name Contoso-O365EX-NA-VaultA1-Key001 -OutputFile Contoso-O365EX-NA-VaultA1-Key001-Backup-20170802.backup
```

### <a name="validate-azure-key-vault-configuration-settings"></a><span data-ttu-id="e0061-282">Azure Key Vault 구성 설정 유효성 검사</span><span class="sxs-lookup"><span data-stu-id="e0061-282">Validate Azure Key Vault configuration settings</span></span>

<span data-ttu-id="e0061-283">DEP에서 키를 사용하기 전에 유효성 검사를 수행하는 것은 선택 사항이지만 매우 권장됩니다.</span><span class="sxs-lookup"><span data-stu-id="e0061-283">Performing validation before using keys in a DEP is optional, but highly recommended.</span></span> <span data-ttu-id="e0061-284">특히 이 항목에 설명된 키와 자격 증명 모음이 다른 키와 자격 증명 모음을 설정하는 단계를 사용하는 경우 고객 키를 구성하기 전에 Azure Key Vault 리소스의 상태 유효성을 검사해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e0061-284">In particular, if you use steps to set up your keys and vaults other than the ones described in this topic, you should validate the health of your Azure Key Vault resources before you configure Customer Key.</span></span>
  
<span data-ttu-id="e0061-285">키가 get, wrapKey 및 unwrapKey 작업을 사용하도록 설정되어 있는지 확인:</span><span class="sxs-lookup"><span data-stu-id="e0061-285">To verify that your keys have get, wrapKey, and unwrapKey operations enabled:</span></span>
  
<span data-ttu-id="e0061-286">다음과 [같이 Get-AzKeyVault](/powershell/module/az.keyvault/get-azkeyvault) cmdlet을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="e0061-286">Run the [Get-AzKeyVault](/powershell/module/az.keyvault/get-azkeyvault) cmdlet as follows:</span></span>
  
```powershell
Get-AzKeyVault -VaultName <vault name>
```

<span data-ttu-id="e0061-287">출력에서 액세스 정책과 Microsoft 365 앱 ID(GUID)를 적절하게 찾아 봐야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e0061-287">In the output, look for the Access Policy and for the Microsoft 365 app ID (GUID) as appropriate.</span></span> <span data-ttu-id="e0061-288">get, wrapKey 및 unwrapKey의 세 가지 작업은 모두 키에 대한 사용 권한 아래에 표시되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e0061-288">All three operations, get, wrapKey, and unwrapKey, must be shown under Permissions to Keys.</span></span>
  
<span data-ttu-id="e0061-289">액세스 정책 구성이 올바르지 않은 경우 다음과 Set-AzKeyVaultAccessPolicy cmdlet을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="e0061-289">If the access policy configuration is incorrect, run the Set-AzKeyVaultAccessPolicy cmdlet as follows:</span></span>
  
```powershell
Set-AzKeyVaultAccessPolicy -VaultName <vault name> -PermissionsToKeys wrapKey,unwrapKey,get -ServicePrincipalName <Microsoft 365 appID>
```

<span data-ttu-id="e0061-290">예: Rest 암호화 서비스의 Microsoft 365 데이터에서 *Microsoft 365 appID를*`c066d759-24ae-40e7-a56f-027002b5d3e4`</span><span class="sxs-lookup"><span data-stu-id="e0061-290">Example: For the Microsoft 365 Data at Rest Encryption service, replace  *Microsoft 365 appID* with `c066d759-24ae-40e7-a56f-027002b5d3e4`</span></span>

  ```powershell
  Set-AzKeyVaultAccessPolicy -VaultName Contoso-O365EX-NA-VaultA1 -PermissionsToKeys wrapKey,unwrapKey,get -ServicePrincipalName c066d759-24ae-40e7-a56f-027002b5d3e4
  ```

<span data-ttu-id="e0061-291">키에 대한 만료 날짜가 설정되어 있지 않은지 확인하기 위해 다음과 같이 [Get-AzKeyVaultKey](/powershell/module/az.keyvault/get-azkeyvault) cmdlet을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="e0061-291">To verify that an expiration date is not set for your keys, run the [Get-AzKeyVaultKey](/powershell/module/az.keyvault/get-azkeyvault) cmdlet as follows:</span></span>
  
```powershell
Get-AzKeyVaultKey -VaultName <vault name>
```

<span data-ttu-id="e0061-292">만료된 키는 고객 키에서 사용할 수 없습니다. 만료된 키로 시도한 작업이 실패하여 서비스가 종료될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e0061-292">An expired key cannot be used by Customer Key and operations attempted with an expired key will fail and possibly result in a service outage.</span></span> <span data-ttu-id="e0061-293">고객 키에 사용되는 키에는 만료 날짜가 없는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="e0061-293">We strongly recommend that keys used with Customer Key do not have an expiration date.</span></span> <span data-ttu-id="e0061-294">만료 날짜(설정된 경우)는 제거할 수 없지만 다른 날짜로 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e0061-294">An expiration date, once set, cannot be removed, but can be changed to a different date.</span></span> <span data-ttu-id="e0061-295">만료 날짜가 설정된 키를 사용하려면 만료 값을 12/31/9999로 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="e0061-295">If a key must be used that has an expiration date set, change the expiration value to 12/31/9999.</span></span> <span data-ttu-id="e0061-296">만료 날짜가 12/31/9999가 다른 날짜로 설정된 키는 Microsoft 365 유효성 검사를 통과하지 못합니다.</span><span class="sxs-lookup"><span data-stu-id="e0061-296">Keys with an expiration date set to a date other than 12/31/9999 won't pass Microsoft 365 validation.</span></span>
  
<span data-ttu-id="e0061-297">12/31/9999가 아니라 다른 값으로 설정된 만료 날짜를 변경하기 위해 다음과 같이 [Update-AzKeyVaultKey](/powershell/module/az.keyvault/update-azkeyvaultkey) cmdlet을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="e0061-297">To change an expiration date that has been set to any value other than 12/31/9999, run the [Update-AzKeyVaultKey](/powershell/module/az.keyvault/update-azkeyvaultkey) cmdlet as follows:</span></span>
  
```powershell
Update-AzKeyVaultKey -VaultName <vault name> -Name <key name> -Expires (Get-Date -Date "12/31/9999")
```

### <a name="obtain-the-uri-for-each-azure-key-vault-key"></a><span data-ttu-id="e0061-298">각 Azure Key Vault 키에 대한 URI 얻기</span><span class="sxs-lookup"><span data-stu-id="e0061-298">Obtain the URI for each Azure Key Vault key</span></span>

<span data-ttu-id="e0061-299">Azure에서 키 자격 증명 모음을 설정하고 키를 추가하기 위한 모든 단계를 완료한 후 다음 명령을 실행하여 각 키 자격 증명 모음의 키에 대한 URI를 얻습니다.</span><span class="sxs-lookup"><span data-stu-id="e0061-299">Once you've completed all the steps in Azure to set up your key vaults and added your keys, run the following command to get the URI for the key in each key vault.</span></span> <span data-ttu-id="e0061-300">나중에 각 DEP를 만들고 할당할 때 이러한 URIS를 사용하여 이 정보를 안전한 장소에 저장해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e0061-300">You will need to use these URIs when you create and assign each DEP later, so save this information in a safe place.</span></span> <span data-ttu-id="e0061-301">각 키 자격 증명 모음에 대해 이 명령을 한 번씩 실행해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e0061-301">Remember to run this command once for each key vault.</span></span>
  
<span data-ttu-id="e0061-302">Azure PowerShell에서:</span><span class="sxs-lookup"><span data-stu-id="e0061-302">In Azure PowerShell:</span></span>
  
```powershell
(Get-AzKeyVaultKey -VaultName <vault name>).Id
```

## <a name="set-up-the-customer-key-encryption-policy-for-your-tenant"></a><span data-ttu-id="e0061-303">테넌트에 대한 고객 키 암호화 정책 설정</span><span class="sxs-lookup"><span data-stu-id="e0061-303">Set up the Customer Key encryption policy for your tenant</span></span>

<span data-ttu-id="e0061-304">이러한 cmdlet을 실행하려면 먼저 사용 권한을 할당해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e0061-304">You need to be assigned permissions before you can run these cmdlets.</span></span> <span data-ttu-id="e0061-305">이 문서에서는 cmdlet의 모든 매개 변수를 나열하기는 하지만 사용자에게 할당된 사용 권한에 포함되지 않은 일부 매개 변수에는 액세스할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="e0061-305">Although this article lists all parameters for the cmdlets, you may not have access to some parameters if they're not included in the permissions assigned to you.</span></span> <span data-ttu-id="e0061-306">조직에서 cmdlet 또는 매개 변수를 실행하는 데 필요한 사용 권한을 확인하려면 [Find the permissions required to run any Exchange cmdlet](/powershell/exchange/exchange-server/find-exchange-cmdlet-permissions)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="e0061-306">To find the permissions required to run any cmdlet or parameter in your organization, see [Find the permissions required to run any Exchange cmdlet](/powershell/exchange/exchange-server/find-exchange-cmdlet-permissions).</span></span>

### <a name="create-policy"></a><span data-ttu-id="e0061-307">정책 만들기</span><span class="sxs-lookup"><span data-stu-id="e0061-307">Create policy</span></span>

```powershell
   New-M365DataAtRestEncryptionPolicy [-Name] <String> -AzureKeyIDs <MultiValuedProperty> [-Description <String>]
```

<span data-ttu-id="e0061-308">설명: 준수 관리자가 두 개의 AKV 루트 키를 사용하여 새 DEP(데이터 암호화 정책)를 만들 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="e0061-308">Description: Enable compliance admin to create a new data encryption policy (DEP) using two AKV root keys.</span></span> <span data-ttu-id="e0061-309">정책을 만든 후 cmdlet을 사용하여 정책을 할당할 Set-M365DataAtRestEncryptionPolicyAssignment 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e0061-309">Once created, a policy can then be assigned using Set-M365DataAtRestEncryptionPolicyAssignment cmdlet.</span></span> <span data-ttu-id="e0061-310">키를 처음 할당하거나 키를 회전한 후 새 키가 적용될 때 최대 24시간이 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e0061-310">Upon first assignment of keys or after you rotate keys, it can take up to 24 hours for the new keys to take effect.</span></span> <span data-ttu-id="e0061-311">새 DEP를 적용하는 데 24시간 이상 소요된 경우 Microsoft에 문의합니다.</span><span class="sxs-lookup"><span data-stu-id="e0061-311">If the new DEP takes more than 24 hours to take effect, contact Microsoft.</span></span>

<span data-ttu-id="e0061-312">예제:</span><span class="sxs-lookup"><span data-stu-id="e0061-312">Example:</span></span>

```powershell
New-M365DataAtRestEncryptionPolicy -Name "Default_Policy" -AzureKeyIDs "https://contosoWestUSvault01.vault.azure.net/keys/Key_01","https://contosoEastUSvault01.vault.azure.net/keys/Key_02" -Description "Tenant default policy"
```

<span data-ttu-id="e0061-313">매개 변수:</span><span class="sxs-lookup"><span data-stu-id="e0061-313">Parameters:</span></span>

| <span data-ttu-id="e0061-314">이름</span><span class="sxs-lookup"><span data-stu-id="e0061-314">Name</span></span> | <span data-ttu-id="e0061-315">설명</span><span class="sxs-lookup"><span data-stu-id="e0061-315">Description</span></span> | <span data-ttu-id="e0061-316">선택 사항(Y/N)</span><span class="sxs-lookup"><span data-stu-id="e0061-316">Optional (Y/N)</span></span> |
|----------|----------|---------|
|<span data-ttu-id="e0061-317">이름</span><span class="sxs-lookup"><span data-stu-id="e0061-317">Name</span></span>|<span data-ttu-id="e0061-318">데이터 암호화 정책의 이름</span><span class="sxs-lookup"><span data-stu-id="e0061-318">Friendly name of the data encryption policy</span></span>|<span data-ttu-id="e0061-319">N</span><span class="sxs-lookup"><span data-stu-id="e0061-319">N</span></span>|
|<span data-ttu-id="e0061-320">AzureKeyIDs</span><span class="sxs-lookup"><span data-stu-id="e0061-320">AzureKeyIDs</span></span>|<span data-ttu-id="e0061-321">데이터 암호화 정책과 연결하기 위해 Azure Key Vault 키의 URI 값 두 개를 0개로 구분하여 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="e0061-321">Specifies two URI values of the Azure Key Vault keys, separated by a comma, to associate with the data encryption policy</span></span>|<span data-ttu-id="e0061-322">N</span><span class="sxs-lookup"><span data-stu-id="e0061-322">N</span></span>|
|<span data-ttu-id="e0061-323">설명</span><span class="sxs-lookup"><span data-stu-id="e0061-323">Description</span></span>|<span data-ttu-id="e0061-324">데이터 암호화 정책에 대한 설명</span><span class="sxs-lookup"><span data-stu-id="e0061-324">Description of the data encryption policy</span></span>|<span data-ttu-id="e0061-325">N</span><span class="sxs-lookup"><span data-stu-id="e0061-325">N</span></span>|

### <a name="assign-policy"></a><span data-ttu-id="e0061-326">정책 할당</span><span class="sxs-lookup"><span data-stu-id="e0061-326">Assign policy</span></span>

```powershell
Set-M365DataAtRestEncryptionPolicyAssignment -DataEncryptionPolicy "<Default_PolicyName or Default_PolicyID>"
```

<span data-ttu-id="e0061-327">설명: 이 cmdlet은 기본 데이터 암호화 정책을 구성하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="e0061-327">Description: This cmdlet is used for configuring default Data Encryption Policy.</span></span> <span data-ttu-id="e0061-328">이 정책은 모든 지원 워크로드에서 데이터를 암호화하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="e0061-328">This policy will be used to then encrypt data across all support workloads.</span></span>

<span data-ttu-id="e0061-329">예제:</span><span class="sxs-lookup"><span data-stu-id="e0061-329">Example:</span></span>

```powershell
Set-M365DataAtRestEncryptionPolicyAssignment -DataEncryptionPolicy "Default_PolicyName"
```

<span data-ttu-id="e0061-330">매개 변수:</span><span class="sxs-lookup"><span data-stu-id="e0061-330">Parameters:</span></span>

| <span data-ttu-id="e0061-331">이름</span><span class="sxs-lookup"><span data-stu-id="e0061-331">Name</span></span> | <span data-ttu-id="e0061-332">설명</span><span class="sxs-lookup"><span data-stu-id="e0061-332">Description</span></span> | <span data-ttu-id="e0061-333">선택 사항(Y/N)</span><span class="sxs-lookup"><span data-stu-id="e0061-333">Optional (Y/N)</span></span> |
|----------|----------|---------|
<span data-ttu-id="e0061-334">-DataEncryptionPolicy</span><span class="sxs-lookup"><span data-stu-id="e0061-334">-DataEncryptionPolicy</span></span>|<span data-ttu-id="e0061-335">할당해야 하는 데이터 암호화 정책을 지정합니다. 정책 이름 또는 정책 ID를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="e0061-335">Specifies the data encryption policy that needs to be assigned; specify either the Policy Name or the Policy ID.</span></span>|<span data-ttu-id="e0061-336">N</span><span class="sxs-lookup"><span data-stu-id="e0061-336">N</span></span>|

### <a name="modify-or-refresh-policy"></a><span data-ttu-id="e0061-337">정책 수정 또는 새로 고침</span><span class="sxs-lookup"><span data-stu-id="e0061-337">Modify or Refresh policy</span></span>

```powershell
Set-M365DataAtRestEncryptionPolicy [-Identity] <M365DataAtRestEncryptionPolicy DataEncryptionPolicyIdParameter> -Refresh [-Enabled <Boolean>] [-Name <String>] [-Description <String>]
```

<span data-ttu-id="e0061-338">설명: 이 cmdlet을 사용하여 기존 정책을 수정하거나 새로 고칠 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e0061-338">Description: The cmdlet can be used either to modify or refresh an existing policy.</span></span> <span data-ttu-id="e0061-339">또한 정책을 활성화 또는 비활성화하는 데 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e0061-339">It can also be used to enable or disable a policy.</span></span> <span data-ttu-id="e0061-340">키를 처음 할당하거나 키를 회전한 후 새 키가 적용될 때 최대 24시간이 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e0061-340">Upon first assignment of keys or after you rotate keys, it can take up to 24 hours for the new keys to take effect.</span></span> <span data-ttu-id="e0061-341">새 DEP를 적용하는 데 24시간 이상 소요된 경우 Microsoft에 문의합니다.</span><span class="sxs-lookup"><span data-stu-id="e0061-341">If the new DEP takes more than 24 hours to take effect, contact Microsoft.</span></span>

<span data-ttu-id="e0061-342">예제:</span><span class="sxs-lookup"><span data-stu-id="e0061-342">Examples:</span></span>

<span data-ttu-id="e0061-343">데이터 암호화 정책을 사용하지 않도록 설정</span><span class="sxs-lookup"><span data-stu-id="e0061-343">Disable a data encryption policy.</span></span>

```powershell
Set-M365DataAtRestEncryptionPolicy -Identity "NAM Policy" -Enabled $false
```

<span data-ttu-id="e0061-344">데이터 암호화 정책을 새로 고침합니다.</span><span class="sxs-lookup"><span data-stu-id="e0061-344">Refresh a data encryption policy.</span></span>

```powershell
Set-M365DataAtRestEncryptionPolicy -Identity "EUR Policy" -Refresh
```

<span data-ttu-id="e0061-345">매개 변수:</span><span class="sxs-lookup"><span data-stu-id="e0061-345">Parameters:</span></span>

| <span data-ttu-id="e0061-346">이름</span><span class="sxs-lookup"><span data-stu-id="e0061-346">Name</span></span> | <span data-ttu-id="e0061-347">설명</span><span class="sxs-lookup"><span data-stu-id="e0061-347">Description</span></span> | <span data-ttu-id="e0061-348">선택 사항(Y/N)</span><span class="sxs-lookup"><span data-stu-id="e0061-348">Optional (Y/N)</span></span> |
|----------|----------|---------|
|<span data-ttu-id="e0061-349">-Identity</span><span class="sxs-lookup"><span data-stu-id="e0061-349">-Identity</span></span>|<span data-ttu-id="e0061-350">수정할 데이터 암호화 정책을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="e0061-350">Specifies the data encryption policy that you want to modify.</span></span>|<span data-ttu-id="e0061-351">N</span><span class="sxs-lookup"><span data-stu-id="e0061-351">N</span></span>|
|<span data-ttu-id="e0061-352">-Refresh</span><span class="sxs-lookup"><span data-stu-id="e0061-352">-Refresh</span></span>|<span data-ttu-id="e0061-353">Azure Key Vault에서 연결된 키를 회전한 후 Refresh 스위치를 사용하여 데이터 암호화 정책을 업데이트합니다.</span><span class="sxs-lookup"><span data-stu-id="e0061-353">Use the Refresh switch to update the data encryption policy after you rotate any of the associated keys in the Azure Key Vault.</span></span> <span data-ttu-id="e0061-354">이 스위치를 사용하면 값을 지정할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="e0061-354">You don't need to specify a value with this switch.</span></span>|<span data-ttu-id="e0061-355">Y</span><span class="sxs-lookup"><span data-stu-id="e0061-355">Y</span></span>|
|<span data-ttu-id="e0061-356">-사용 설정됨</span><span class="sxs-lookup"><span data-stu-id="e0061-356">-Enabled</span></span>|<span data-ttu-id="e0061-357">Enabled 매개 변수는 데이터 암호화 정책을 활성화하거나 사용하지 않도록 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="e0061-357">The Enabled parameter enables or disables the data encryption policy.</span></span> <span data-ttu-id="e0061-358">정책을 사용하지 않도록 설정하기 전에 테넌트에서 정책을 해제해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e0061-358">Before you disable a policy, you must unassign it from your tenant.</span></span> <span data-ttu-id="e0061-359">유효한 값은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="e0061-359">Valid values are:</span></span></br > <span data-ttu-id="e0061-360">$true: 정책이 사용하도록 설정되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e0061-360">$true: The policy is enabled</span></span></br > <span data-ttu-id="e0061-361">$true: 이 정책은 사용하도록 설정되어 있습니다. 이 값은 기본값입니다.
</span><span class="sxs-lookup"><span data-stu-id="e0061-361">$false: The policy is disabled.</span></span>|<span data-ttu-id="e0061-362">Y</span><span class="sxs-lookup"><span data-stu-id="e0061-362">Y</span></span>|
|<span data-ttu-id="e0061-363">-Name</span><span class="sxs-lookup"><span data-stu-id="e0061-363">-Name</span></span>|<span data-ttu-id="e0061-364">Name 매개 변수는 데이터 암호화 정책의 고유 이름을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="e0061-364">The Name parameter specifies the unique name for the data encryption policy.</span></span>|<span data-ttu-id="e0061-365">Y</span><span class="sxs-lookup"><span data-stu-id="e0061-365">Y</span></span>|
|<span data-ttu-id="e0061-366">-Description</span><span class="sxs-lookup"><span data-stu-id="e0061-366">-Description</span></span>|<span data-ttu-id="e0061-367">Description 매개 변수는 데이터 암호화 정책에 대한 선택적 설명을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="e0061-367">The Description parameter specifies an optional description for the data encryption policy.</span></span>|<span data-ttu-id="e0061-368">Y</span><span class="sxs-lookup"><span data-stu-id="e0061-368">Y</span></span>|

### <a name="get-policy-details"></a><span data-ttu-id="e0061-369">정책 세부 정보 확인</span><span class="sxs-lookup"><span data-stu-id="e0061-369">Get policy details</span></span>

```powershell
Get-M365DataAtRestEncryptionPolicy [-Identity] <M365DataAtRestEncryptionPolicy DataEncryptionPolicyIdParameter>
```

<span data-ttu-id="e0061-370">설명: 이 cmdlet은 테넌트에 대해 만들어진 모든 M365DataAtRest 암호화 정책 또는 특정 정책에 대한 세부 정보를 나열합니다.</span><span class="sxs-lookup"><span data-stu-id="e0061-370">Description: This cmdlet lists all of M365DataAtRest encryption policies that are created for the tenant or details about a specific policy.</span></span>

<span data-ttu-id="e0061-371">예제:</span><span class="sxs-lookup"><span data-stu-id="e0061-371">Examples:</span></span>

<span data-ttu-id="e0061-372">이 예에서는 조직의 M365DatAtRest 암호화 정책 요약 목록을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="e0061-372">This example returns a summary list of M365DatAtRest Encryption policies in the organization.</span></span>

```powershell
Get-M365DataAtRestEncryptionPolicy
```

<span data-ttu-id="e0061-373">이 예에서는 "NAM Policy"라는 데이터 암호화 정책에 대한 자세한 정보를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="e0061-373">This example returns detailed information for the data encryption policy named "NAM Policy".</span></span>

```powershell
Get-M365DataAtRestEncryptionPolicy -Identity "NAM Policy"
```

<span data-ttu-id="e0061-374">매개 변수:</span><span class="sxs-lookup"><span data-stu-id="e0061-374">Parameters:</span></span>

| <span data-ttu-id="e0061-375">이름</span><span class="sxs-lookup"><span data-stu-id="e0061-375">Name</span></span> | <span data-ttu-id="e0061-376">설명</span><span class="sxs-lookup"><span data-stu-id="e0061-376">Description</span></span> | <span data-ttu-id="e0061-377">선택 사항(Y/N)</span><span class="sxs-lookup"><span data-stu-id="e0061-377">Optional (Y/N)</span></span> |
|----------|----------|---------|
|<span data-ttu-id="e0061-378">-Identity</span><span class="sxs-lookup"><span data-stu-id="e0061-378">-Identity</span></span>|<span data-ttu-id="e0061-379">세부 정보를 나열할 데이터 암호화 정책을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="e0061-379">Specifies the data encryption policy that you want to list the details for.</span></span>|<span data-ttu-id="e0061-380">Y</span><span class="sxs-lookup"><span data-stu-id="e0061-380">Y</span></span>|

### <a name="get-policy-assignment-info"></a><span data-ttu-id="e0061-381">정책 할당 정보 보기</span><span class="sxs-lookup"><span data-stu-id="e0061-381">Get policy assignment info</span></span>

```powershell
Get-M365DataAtRestEncryptionPolicyAssignment
```

<span data-ttu-id="e0061-382">설명: 이 cmdlet은 현재 테넌트에 할당된 정책을 나열합니다.</span><span class="sxs-lookup"><span data-stu-id="e0061-382">Description: This cmdlet lists the policy that’s currently assigned to the tenant.</span></span>

## <a name="offboarding-from-customer-key-at-the-tenant-level"></a><span data-ttu-id="e0061-383">테넌트 수준에서 고객 키에서 오프보더</span><span class="sxs-lookup"><span data-stu-id="e0061-383">Offboarding from Customer Key at the tenant level</span></span>

<span data-ttu-id="e0061-384">Microsoft 관리 키로 되전해야 하는 경우 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e0061-384">If you need to revert to Microsoft-managed keys, you can.</span></span> <span data-ttu-id="e0061-385">오프보드를 해제하면 각 개별 워크로드에서 지원하는 기본 암호화를 사용하여 데이터가 다시 암호화됩니다.</span><span class="sxs-lookup"><span data-stu-id="e0061-385">When you offboard, your data is re-encrypted using default encryption supported by each individual workload.</span></span> <span data-ttu-id="e0061-386">예를 들어 Exchange Online에서는 Microsoft에서 관리하는 키를 사용하여 기본 암호화를 지원할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e0061-386">For example, Exchange Online supports default encryption using Microsoft-managed keys.</span></span>

<span data-ttu-id="e0061-387">테넌트 수준에서 고객 키에서 테넌트의 등록을 해제하기로 결정한 경우 테넌트에 대한 서비스를 ["m365ck@microsoft.com"](mailto:m365ck@microsoft.com) 요청과 함께 전자 메일을 보내야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e0061-387">If you decide to offboard your tenant from Customer Key at the tenant level, email [m365ck@microsoft.com](mailto:m365ck@microsoft.com) with a request to "disable" the service for the tenant.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="e0061-388">오프보더는 데이터 제거와는 동일하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="e0061-388">Offboarding is not the same as a data purge.</span></span> <span data-ttu-id="e0061-389">데이터를 삭제하면 Microsoft 365에서 조직의 데이터가 영구적으로 삭제되고, 오프보더는 삭제되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="e0061-389">A data purge permanently crypto-deletes your organization's data from Microsoft 365, offboarding does not.</span></span> <span data-ttu-id="e0061-390">테넌트 수준 정책에 대한 데이터 제거는 수행할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="e0061-390">You can't perform a data purge for a tenant-level policy.</span></span> <span data-ttu-id="e0061-391">데이터 제거 경로에 대한 자세한 내용은 키 해지 및 데이터 제거 경로 프로세스 시작을 [참조하세요.](customer-key-manage.md#revoke-your-keys-and-start-the-data-purge-path-process)</span><span class="sxs-lookup"><span data-stu-id="e0061-391">For information about data purge path, see [Revoke your keys and start the data purge path process](customer-key-manage.md#revoke-your-keys-and-start-the-data-purge-path-process).</span></span>

## <a name="about-the-availability-key"></a><span data-ttu-id="e0061-392">가용성 키</span><span class="sxs-lookup"><span data-stu-id="e0061-392">About the availability key</span></span>

<span data-ttu-id="e0061-393">가용성 키에 대한 자세한 내용은 가용성 키에 [대한 자세한 정보를 참조하세요.](customer-key-availability-key-understand.md)</span><span class="sxs-lookup"><span data-stu-id="e0061-393">For information about the availability key, see [Learn about the availability key](customer-key-availability-key-understand.md).</span></span>

## <a name="key-rotation"></a><span data-ttu-id="e0061-394">키 회전</span><span class="sxs-lookup"><span data-stu-id="e0061-394">Key rotation</span></span>

<span data-ttu-id="e0061-395">고객 키와 함께 사용하는 키 회전 또는 롤링에 대한 자세한 내용은 고객 키 또는 가용성 키 롤 또는 회전을 [참조하세요.](customer-key-availability-key-roll.md)</span><span class="sxs-lookup"><span data-stu-id="e0061-395">For information about rotating or rolling keys that you use with Customer Key, see [Roll or rotate a Customer Key or an availability key](customer-key-availability-key-roll.md).</span></span> <span data-ttu-id="e0061-396">새 버전의 키를 사용하기 위해 DEP를 업데이트하면 이 문서의 앞부분에서 설명한 대로 Set-M365DataAtRestEncryptionPolicy cmdlet을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="e0061-396">When you update the DEP to use the new version of the keys, you'll run the Set-M365DataAtRestEncryptionPolicy cmdlet as described earlier in this article.</span></span>

## <a name="known-issues"></a><span data-ttu-id="e0061-397">알려진 문제</span><span class="sxs-lookup"><span data-stu-id="e0061-397">Known issues</span></span>

<span data-ttu-id="e0061-398">테넌트 수준에서 고객 키를 사용하도록 설정하면 Microsoft Teams에서 새 팀을 만들 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="e0061-398">When you enable Customer Key at the tenant level, you can't create a new team in Microsoft Teams.</span></span>

## <a name="related-articles"></a><span data-ttu-id="e0061-399">관련 문서</span><span class="sxs-lookup"><span data-stu-id="e0061-399">Related articles</span></span>

- [<span data-ttu-id="e0061-400">고객 키를 사용한 서비스 암호화</span><span class="sxs-lookup"><span data-stu-id="e0061-400">Service encryption with Customer Key</span></span>](customer-key-overview.md)

- [<span data-ttu-id="e0061-401">고객 키 또는 가용성 키 롤 또는 회전</span><span class="sxs-lookup"><span data-stu-id="e0061-401">Roll or rotate a Customer Key or an availability key</span></span>](customer-key-availability-key-roll.md)

- [<span data-ttu-id="e0061-402">가용성 키에 대해 자세히 알아보기</span><span class="sxs-lookup"><span data-stu-id="e0061-402">Learn about the availability key</span></span>](customer-key-availability-key-understand.md)

- [<span data-ttu-id="e0061-403">서비스 암호화</span><span class="sxs-lookup"><span data-stu-id="e0061-403">Service Encryption</span></span>](office-365-service-encryption.md)
