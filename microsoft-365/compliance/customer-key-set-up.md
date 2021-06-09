---
title: 고객 키 설정
ms.author: krowley
author: kccross
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- M365-security-compliance
description: 고객 키에 대한 고객 키를 설정하는 Microsoft 365.
ms.openlocfilehash: e187c01a355cc9b926e892cb3326b5a527c714a4
ms.sourcegitcommit: 94e64afaf12f3d8813099d8ffa46baba65772763
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/12/2021
ms.locfileid: "52344677"
---
# <a name="set-up-customer-key"></a><span data-ttu-id="ab5ee-103">고객 키 설정</span><span class="sxs-lookup"><span data-stu-id="ab5ee-103">Set up Customer Key</span></span>

<span data-ttu-id="ab5ee-104">고객 키를 사용하여 조직의 암호화 키를 제어한 다음 Microsoft Microsoft 365 센터에서 휴지의 데이터를 암호화하는 데 사용하도록 암호화 키를 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="ab5ee-104">With Customer Key, you control your organization's encryption keys and then configure Microsoft 365 to use them to encrypt your data at rest in Microsoft's data centers.</span></span> <span data-ttu-id="ab5ee-105">즉, 고객 키를 사용하면 고객이 키와 함께 고객에게 속한 암호화 계층을 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ab5ee-105">In other words, Customer Key allows customers to add a layer of encryption that belongs to them, with their keys.</span></span>

<span data-ttu-id="ab5ee-106">사용자에 대해 고객 키를 사용하기 전에 Azure를 Office 365.</span><span class="sxs-lookup"><span data-stu-id="ab5ee-106">Set up Azure before you can use Customer Key for Office 365.</span></span> <span data-ttu-id="ab5ee-107">이 문서에서는 필요한 Azure 리소스를 만들고 구성하기 위해 따라야 하는 단계에 대해 설명한 다음 이 문서에서 고객 키를 설정하기 위한 단계를 Office 365.</span><span class="sxs-lookup"><span data-stu-id="ab5ee-107">This article describes the steps you need to follow to create and configure the required Azure resources and then provides the steps for setting up Customer Key in Office 365.</span></span> <span data-ttu-id="ab5ee-108">Azure를 설정한 후 조직의 다양한 작업 부하에서 데이터를 암호화하기 위해 할당할 정책과 Microsoft 365 결정하게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ab5ee-108">After you set up Azure, you determine which policy, and therefore, which keys, to assign to encrypt data across various Microsoft 365 workloads in your organization.</span></span> <span data-ttu-id="ab5ee-109">고객 키에 대한 자세한 내용은 에서 고객 키를 사용하여 서비스 암호화를 [Office 365.](customer-key-overview.md)</span><span class="sxs-lookup"><span data-stu-id="ab5ee-109">For more information about Customer Key, or for a general overview, see [Service encryption with Customer Key in Office 365](customer-key-overview.md).</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="ab5ee-110">이 문서의 모범 사례를 따르는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="ab5ee-110">We strongly recommend that you follow the best practices in this article.</span></span> <span data-ttu-id="ab5ee-111">이러한 호출은 **TIP** 및 IMPORTANT 로 **호출합니다.**</span><span class="sxs-lookup"><span data-stu-id="ab5ee-111">These are called out as **TIP** and **IMPORTANT**.</span></span> <span data-ttu-id="ab5ee-112">고객 키는 전체 조직만큼 범위가 될 수 있는 루트 암호화 키를 제어할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="ab5ee-112">Customer Key gives you control over root encryption keys whose scope can be as large as your entire organization.</span></span> <span data-ttu-id="ab5ee-113">즉, 이러한 키로 실수하는 경우 광범위한 영향을 미칠 수 있으며 서비스가 중단되거나 데이터를 취소할 수 없는 손실이 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ab5ee-113">This means that mistakes made with these keys can have a broad impact and may result in service interruptions or irrevocable loss of your data.</span></span>
  
## <a name="before-you-set-up-customer-key"></a><span data-ttu-id="ab5ee-114">고객 키를 설정하기 전에</span><span class="sxs-lookup"><span data-stu-id="ab5ee-114">Before you set up Customer Key</span></span>

<span data-ttu-id="ab5ee-115">시작하기 전에 조직에 적절한 Azure 구독 및 라이선스가 있는지 확인하세요.</span><span class="sxs-lookup"><span data-stu-id="ab5ee-115">Before you get started, ensure that you have the appropriate Azure subscriptions and licensing for your organization.</span></span> <span data-ttu-id="ab5ee-116">유료 Azure 구독은 기업계약 또는 클라우드 서비스 공급자를 사용하여 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="ab5ee-116">Use paid Azure Subscriptions using either an Enterprise Agreement or a Cloud Service Provider.</span></span> <span data-ttu-id="ab5ee-117">신용 카드 기반 결제는 수락되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="ab5ee-117">Credit Card based payments are not accepted.</span></span> <span data-ttu-id="ab5ee-118">인보이스에 대한 계정 요구 사항을 승인하고 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="ab5ee-118">Approve and set up the account needs for invoicing.</span></span> <span data-ttu-id="ab5ee-119">무료, 평가판, 스폰서십, MSDN 구독을 통해 제공된 구독 및 레거시 지원에 속한 구독은 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="ab5ee-119">Subscriptions you got through Free, Trial, Sponsorships, MSDN Subscriptions, and those under Legacy Support are not eligible.</span></span>

<span data-ttu-id="ab5ee-120">Office 365 E5, Microsoft 365 E5, Microsoft 365 E5 Compliance 및 Microsoft 365 E5 정보 보호 & SKUS는 고객 키를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="ab5ee-120">Office 365 E5, Microsoft 365 E5, Microsoft 365 E5 Compliance, and Microsoft 365 E5 Information Protection & Governance SKUs offer Customer Key.</span></span> <span data-ttu-id="ab5ee-121">Office 365 Advanced Compliance 새 라이선스를 조달하는 데 SKU를 더 이상 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="ab5ee-121">Office 365 Advanced Compliance SKU is no longer available for procuring new licenses.</span></span> <span data-ttu-id="ab5ee-122">기존 Office 365 Advanced Compliance 라이선스가 계속 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="ab5ee-122">Existing Office 365 Advanced Compliance licenses will continue to be supported.</span></span>

<span data-ttu-id="ab5ee-123">이 문서의 개념과 절차를 이해하기 위해 [Azure Key Vault 설명서를 검토하세요.](/azure/key-vault/)</span><span class="sxs-lookup"><span data-stu-id="ab5ee-123">To understand the concepts and procedures in this article, review the [Azure Key Vault](/azure/key-vault/) documentation.</span></span> <span data-ttu-id="ab5ee-124">또한 Azure에서 사용되는 용어(예: Azure [AD 테넌트)에 익숙해지기 하세요.](/previous-versions/azure/azure-services/jj573650(v=azure.100)#what-is-an-azure-ad-tenant)</span><span class="sxs-lookup"><span data-stu-id="ab5ee-124">Also, become familiar with the terms used in Azure, for example, [Azure AD tenant](/previous-versions/azure/azure-services/jj573650(v=azure.100)#what-is-an-azure-ad-tenant).</span></span>
  
<span data-ttu-id="ab5ee-125">설명서 이외에 추가 지원이 필요한 경우 MCS(Microsoft Consulting Services), PFE(프리미어 필드 엔지니어링) 또는 Microsoft 파트너에게 지원을 요청하세요.</span><span class="sxs-lookup"><span data-stu-id="ab5ee-125">If you need more support beyond the documentation, contact Microsoft Consulting Services (MCS), Premier Field Engineering (PFE), or a Microsoft partner for assistance.</span></span> <span data-ttu-id="ab5ee-126">설명서를 포함하여 고객 키에 대한 의견을 제공하기 위해 사용자 의견, 제안 및 관점을 customerkeyfeedback@microsoft.com.</span><span class="sxs-lookup"><span data-stu-id="ab5ee-126">To provide feedback on Customer Key, including the documentation, send your ideas, suggestions, and perspectives to customerkeyfeedback@microsoft.com.</span></span>
  
## <a name="overview-of-steps-to-set-up-customer-key"></a><span data-ttu-id="ab5ee-127">고객 키 설정 단계 개요</span><span class="sxs-lookup"><span data-stu-id="ab5ee-127">Overview of steps to set up Customer Key</span></span>

<span data-ttu-id="ab5ee-128">고객 키를 설정하기 위해 나열된 순서대로 이러한 작업을 완료합니다.</span><span class="sxs-lookup"><span data-stu-id="ab5ee-128">To set up Customer Key, complete these tasks in the listed order.</span></span> <span data-ttu-id="ab5ee-129">이 문서의 나머지에서는 각 작업에 대한 자세한 지침을 제공하거나 프로세스의 각 단계에 대한 추가 정보로 연결됩니다.</span><span class="sxs-lookup"><span data-stu-id="ab5ee-129">The rest of this article provides detailed instructions for each task, or links out to more information for each step in the process.</span></span>
  
<span data-ttu-id="ab5ee-130">**Azure 및 Microsoft FastTrack에서:**</span><span class="sxs-lookup"><span data-stu-id="ab5ee-130">**In Azure and Microsoft FastTrack:**</span></span>
  
<span data-ttu-id="ab5ee-131">원격으로 연결하여 이러한 작업의 대부분을 완료할 Azure PowerShell.</span><span class="sxs-lookup"><span data-stu-id="ab5ee-131">You'll complete most of these tasks by remotely connecting to Azure PowerShell.</span></span> <span data-ttu-id="ab5ee-132">최상의 결과를 얻기 위해 버전 4.4.0 이상을 Azure PowerShell.</span><span class="sxs-lookup"><span data-stu-id="ab5ee-132">For best results, use version 4.4.0 or later of Azure PowerShell.</span></span>
  
- [<span data-ttu-id="ab5ee-133">두 개의 새 Azure 구독 만들기</span><span class="sxs-lookup"><span data-stu-id="ab5ee-133">Create two new Azure subscriptions</span></span>](#create-two-new-azure-subscriptions)

- [<span data-ttu-id="ab5ee-134">고객 키 정품 인증 요청을 제출하여 Office 365</span><span class="sxs-lookup"><span data-stu-id="ab5ee-134">Submit a request to activate Customer Key for Office 365</span></span>](#submit-a-request-to-activate-customer-key-for-office-365)
 
- [<span data-ttu-id="ab5ee-135">필수 보존 기간을 사용하기 위해 Azure 구독 등록</span><span class="sxs-lookup"><span data-stu-id="ab5ee-135">Register Azure subscriptions to use a mandatory retention period</span></span>](#register-azure-subscriptions-to-use-a-mandatory-retention-period)

  <span data-ttu-id="ab5ee-136">등록에는 영업일 1~5일이 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ab5ee-136">Registration can take from one to five business days.</span></span>

- [<span data-ttu-id="ab5ee-137">각 구독에서 프리미엄 Azure Key Vault 만들기</span><span class="sxs-lookup"><span data-stu-id="ab5ee-137">Create a premium Azure Key Vault in each subscription</span></span>](#create-a-premium-azure-key-vault-in-each-subscription)

- [<span data-ttu-id="ab5ee-138">각 키 자격 증명 모음에 사용 권한 할당</span><span class="sxs-lookup"><span data-stu-id="ab5ee-138">Assign permissions to each key vault</span></span>](#assign-permissions-to-each-key-vault)

- [<span data-ttu-id="ab5ee-139">키 자격 증명 모음에서 소프트 삭제가 사용하도록 설정되어 있는지 확인</span><span class="sxs-lookup"><span data-stu-id="ab5ee-139">Make sure soft delete is enabled on your key vaults</span></span>](#make-sure-soft-delete-is-enabled-on-your-key-vaults)

- [<span data-ttu-id="ab5ee-140">키를 만들거나 가져와서 각 키 자격 증명 모음에 키 추가</span><span class="sxs-lookup"><span data-stu-id="ab5ee-140">Add a key to each key vault either by creating or importing a key</span></span>](#add-a-key-to-each-key-vault-either-by-creating-or-importing-a-key)

- [<span data-ttu-id="ab5ee-141">키의 복구 수준 확인</span><span class="sxs-lookup"><span data-stu-id="ab5ee-141">Check the recovery level of your keys</span></span>](#check-the-recovery-level-of-your-keys)

- [<span data-ttu-id="ab5ee-142">Azure Key Vault 백업</span><span class="sxs-lookup"><span data-stu-id="ab5ee-142">Back up Azure Key Vault</span></span>](#back-up-azure-key-vault)

- [<span data-ttu-id="ab5ee-143">Azure Key Vault 구성 설정 유효성 검사</span><span class="sxs-lookup"><span data-stu-id="ab5ee-143">Validate Azure Key Vault configuration settings</span></span>](#validate-azure-key-vault-configuration-settings)

- [<span data-ttu-id="ab5ee-144">각 Azure Key Vault 키에 대한 URI 얻기</span><span class="sxs-lookup"><span data-stu-id="ab5ee-144">Obtain the URI for each Azure Key Vault key</span></span>](#obtain-the-uri-for-each-azure-key-vault-key)
  
## <a name="complete-tasks-in-azure-key-vault-and-microsoft-fasttrack-for-customer-key"></a><span data-ttu-id="ab5ee-145">Azure Key Vault 및 고객용 Microsoft FastTrack에서 작업 완료</span><span class="sxs-lookup"><span data-stu-id="ab5ee-145">Complete tasks in Azure Key Vault and Microsoft FastTrack for Customer Key</span></span>

<span data-ttu-id="ab5ee-146">Azure Key Vault에서 이러한 작업을 완료합니다.</span><span class="sxs-lookup"><span data-stu-id="ab5ee-146">Complete these tasks in Azure Key Vault.</span></span> <span data-ttu-id="ab5ee-147">고객 키와 함께 사용하는 모든 DEP에 대해 이러한 단계를 완료해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ab5ee-147">You'll need to complete these steps for all DEPs you use with Customer Key.</span></span>
  
### <a name="create-two-new-azure-subscriptions"></a><span data-ttu-id="ab5ee-148">두 개의 새 Azure 구독 만들기</span><span class="sxs-lookup"><span data-stu-id="ab5ee-148">Create two new Azure subscriptions</span></span>

<span data-ttu-id="ab5ee-149">고객 키에는 두 개의 Azure 구독이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="ab5ee-149">Customer Key requires two Azure subscriptions.</span></span> <span data-ttu-id="ab5ee-150">모범 사례로 고객 키와 함께 사용할 새 Azure 구독을 만드는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="ab5ee-150">As a best practice, Microsoft recommends that you create new Azure subscriptions for use with Customer Key.</span></span> <span data-ttu-id="ab5ee-151">Azure Key Vault 키는 동일한 Azure Active Directory(Microsoft Azure Active Directory) 테넌트의 응용 프로그램에만 권한을 부여할 수 있으며, DEP가 할당될 조직에서 사용되는 동일한 Azure AD 테넌트를 사용하여 새 구독을 만들어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ab5ee-151">Azure Key Vault keys can only be authorized for applications in the same Azure Active Directory (Microsoft Azure Active Directory) tenant, you must create the new subscriptions using the same Azure AD tenant used with your organization where the DEPs will be assigned.</span></span> <span data-ttu-id="ab5ee-152">예를 들어 조직에서 전역 관리자 권한이 있는 직장 또는 학교 계정을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ab5ee-152">For example, using your work or school account that has global administrator privileges in your organization.</span></span> <span data-ttu-id="ab5ee-153">자세한 단계는 [조직으로 Azure에 등록을 참조하세요.](/azure/active-directory/fundamentals/sign-up-organization)</span><span class="sxs-lookup"><span data-stu-id="ab5ee-153">For detailed steps, see [Sign up for Azure as an organization](/azure/active-directory/fundamentals/sign-up-organization).</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="ab5ee-154">고객 키에는 각 DEP(데이터 암호화 정책)에 대해 두 개의 키가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="ab5ee-154">Customer Key requires two keys for each data encryption policy (DEP).</span></span> <span data-ttu-id="ab5ee-155">이를 위해 Azure 구독을 두 개 만들어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ab5ee-155">In order to achieve this, you must create two Azure subscriptions.</span></span> <span data-ttu-id="ab5ee-156">조직의 개별 구성원이 각 구독에서 하나의 키를 구성하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="ab5ee-156">As a best practice, Microsoft recommends that you have separate members of your organization configure one key in each subscription.</span></span> <span data-ttu-id="ab5ee-157">이러한 Azure 구독을 사용하여 사용자에 대한 암호화 키를 Office 365.</span><span class="sxs-lookup"><span data-stu-id="ab5ee-157">You should only use these Azure subscriptions to administer encryption keys for Office 365.</span></span> <span data-ttu-id="ab5ee-158">이렇게 하여 운영자 중 한 명을 실수로, 의도적으로 또는 악의적으로 삭제하거나 책임이 있는 키를 잘못 관리한 경우 조직을 보호할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ab5ee-158">This protects your organization in case one of your operators accidentally, intentionally, or maliciously deletes or otherwise mismanages the keys for which they are responsible.</span></span>

<span data-ttu-id="ab5ee-159">조직에 대해 만들 수 있는 Azure 구독 수에는 실질적인 제한이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="ab5ee-159">There is no practical limit to the number of Azure subscriptions that you can create for your organization.</span></span> <span data-ttu-id="ab5ee-160">이러한 모범 사례를 따라 사용자 오류의 영향을 최소화하면서 고객 키에서 사용하는 리소스를 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ab5ee-160">Following these best practices will minimize the impact of human error while helping to manage the resources used by Customer Key.</span></span>
  
### <a name="submit-a-request-to-activate-customer-key-for-office-365"></a><span data-ttu-id="ab5ee-161">고객 키 정품 인증 요청을 제출하여 Office 365</span><span class="sxs-lookup"><span data-stu-id="ab5ee-161">Submit a request to activate Customer Key for Office 365</span></span>

<span data-ttu-id="ab5ee-162">두 개의 새 Azure 구독을 만든 후 Microsoft FastTrack 포털에서 적절한 고객 키 제품 요청을 [제출해야 합니다.](https://fasttrack.microsoft.com/)</span><span class="sxs-lookup"><span data-stu-id="ab5ee-162">Once you've created the two new Azure subscriptions, you'll need to submit the appropriate Customer Key offer request in the [Microsoft FastTrack portal](https://fasttrack.microsoft.com/).</span></span> <span data-ttu-id="ab5ee-163">조직 내에서 승인된 지정에 대한 제안 양식에서 선택한 것은 고객 키 등록을 완료하는 데 중요하고 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="ab5ee-163">The selections that you make in the offer form about the authorized designations within your organization are critical and necessary for completion of Customer Key registration.</span></span> <span data-ttu-id="ab5ee-164">조직 내에서 선택한 역할의 담당자는 고객 키 데이터 암호화 정책에 사용되는 모든 키를 해지하고 삭제하기 위한 모든 요청의 인증을 보장합니다.</span><span class="sxs-lookup"><span data-stu-id="ab5ee-164">The officers in those selected roles within your organization ensure the authenticity of any request to revoke and destroy all keys used with a Customer Key data encryption policy.</span></span> <span data-ttu-id="ab5ee-165">조직에 사용하려는 각 고객 키 DEP 유형에 대해 이 단계를 한 번씩 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ab5ee-165">You'll need to do this step once for each Customer Key DEP type that you intend to use for your organization.</span></span>

<span data-ttu-id="ab5ee-166">**FastTrack 팀은 고객 키에 대한 지원을 제공하지 않습니다. Office 365 FastTrack 포털을 사용하여 양식을 제출하고 고객 키에 대한 관련 제안을 추적하는 데 도움이 됩니다. FastTrack 요청을 제출한 후 해당 고객 키 온보드 팀에 문의하여 온보더링 프로세스를 시작하십시오.**</span><span class="sxs-lookup"><span data-stu-id="ab5ee-166">**The FastTrack team doesn't provide assistance with Customer Key. Office 365 simply uses the FastTrack portal to allow you to submit the form and to help us track the relevant offers for Customer Key. Once you've submitted the FastTrack request, reach out to the corresponding Customer Key onboarding team to start the onboarding process.**</span></span>
  
<span data-ttu-id="ab5ee-167">고객 키를 활성화하기 위한 제안을 제출하려면 다음 단계를 완료합니다.</span><span class="sxs-lookup"><span data-stu-id="ab5ee-167">To submit an offer to activate Customer Key, complete these steps:</span></span>
  
1. <span data-ttu-id="ab5ee-168">조직에서 전역 관리자 권한이 있는 직장 또는 학교 계정을 사용하여 [Microsoft FastTrack](https://fasttrack.microsoft.com/)포털에 로그인합니다.</span><span class="sxs-lookup"><span data-stu-id="ab5ee-168">Using a work or school account that has global administrator permissions in your organization, sign in to the [Microsoft FastTrack portal](https://fasttrack.microsoft.com/).</span></span>

2. <span data-ttu-id="ab5ee-169">로그인한 후 적절한 도메인을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="ab5ee-169">Once you're logged in, select the appropriate domain.</span></span>

3. <span data-ttu-id="ab5ee-170">선택한 도메인에 대해  위쪽 탐색 모음에서 서비스 요청을 선택하고 사용 가능한 제안 목록을 검토합니다.</span><span class="sxs-lookup"><span data-stu-id="ab5ee-170">For the selected domain, choose **Request services** from the top navigation bar, and review the list of available offers.</span></span>

4. <span data-ttu-id="ab5ee-171">적용되는 제품 정보 카드를 선택하세요.</span><span class="sxs-lookup"><span data-stu-id="ab5ee-171">Choose the information card for the offer that applies to you:</span></span>

   - <span data-ttu-id="ab5ee-172">**여러 Microsoft 365 작업:** 제안에 대한 암호화 키 요청 **Microsoft 365** 선택하세요.</span><span class="sxs-lookup"><span data-stu-id="ab5ee-172">**Multiple Microsoft 365 workloads:** Choose the **Request encryption key help for Microsoft 365** offer.</span></span>

   - <span data-ttu-id="ab5ee-173">**Exchange Online 및 비즈니스용 Skype:** 제품 **지원에 대한** 암호화 키 Exchange 선택하세요.</span><span class="sxs-lookup"><span data-stu-id="ab5ee-173">**Exchange Online and Skype for Business:** Choose the **Request encryption key help for Exchange** offer.</span></span>

   - <span data-ttu-id="ab5ee-174">**SharePoint 온라인, OneDrive 및 Teams 파일:** 요청 암호화 **키 도움말을** SharePoint 비즈니스용 OneDrive 선택하세요.</span><span class="sxs-lookup"><span data-stu-id="ab5ee-174">**SharePoint Online, OneDrive, and Teams files:** Choose the **Request encryption key help for SharePoint and OneDrive for Business** offer.</span></span>

5. <span data-ttu-id="ab5ee-175">제품 세부 정보를 검토한 후 **2단계로 계속을 선택 합니다.**</span><span class="sxs-lookup"><span data-stu-id="ab5ee-175">Once you've reviewed the offer details, choose **Continue to step 2**.</span></span>

6. <span data-ttu-id="ab5ee-176">제품 양식에 적용 가능한 모든 세부 정보와 요청된 정보를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="ab5ee-176">Fill out all applicable details and requested information on the offer form.</span></span> <span data-ttu-id="ab5ee-177">조직의 임원이 암호화 키와 데이터의 영구적이자 비버버스할 수 없는 폐기 권한을 승인할 선택에 특히 주의해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ab5ee-177">Pay particular attention to your selections for which officers of your organization you want to authorize to approve the permanent and irreversible destruction of encryption keys and data.</span></span> <span data-ttu-id="ab5ee-178">양식을 완료한 후 제출 을 **선택하세요.**</span><span class="sxs-lookup"><span data-stu-id="ab5ee-178">Once you've completed the form, choose **Submit**.</span></span>

### <a name="register-azure-subscriptions-to-use-a-mandatory-retention-period"></a><span data-ttu-id="ab5ee-179">필수 보존 기간을 사용하기 위해 Azure 구독 등록</span><span class="sxs-lookup"><span data-stu-id="ab5ee-179">Register Azure subscriptions to use a mandatory retention period</span></span>

<span data-ttu-id="ab5ee-180">루트 암호화 키의 일시적 또는 영구적 손실은 서비스 작업에 지장이나 심지어는 비극적일 수 있으며 데이터가 손실될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ab5ee-180">The temporary or permanent loss of root encryption keys can be disruptive or even catastrophic to service operation and can result in data loss.</span></span> <span data-ttu-id="ab5ee-181">이러한 이유로 고객 키와 함께 사용되는 리소스에는 강력한 보호가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="ab5ee-181">For this reason, the resources used with Customer Key require strong protection.</span></span> <span data-ttu-id="ab5ee-182">고객 키와 함께 사용되는 모든 Azure 리소스는 기본 구성을 넘어 보호 메커니즘을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="ab5ee-182">All the Azure resources that are used with Customer Key offer protection mechanisms beyond the default configuration.</span></span> <span data-ttu-id="ab5ee-183">필수 보존 기간 동안 Azure 구독에 태그를 지정하거나 *등록할 수 있습니다.*</span><span class="sxs-lookup"><span data-stu-id="ab5ee-183">You can tag or register Azure subscriptions for a *mandatory retention period*.</span></span> <span data-ttu-id="ab5ee-184">필수 보존 기간은 Azure 구독의 즉시 취소할 수 없는 취소를 방지합니다.</span><span class="sxs-lookup"><span data-stu-id="ab5ee-184">A mandatory retention period prevents immediate and irrevocable cancellation of your Azure subscription.</span></span> <span data-ttu-id="ab5ee-185">필수 보존 기간 동안 Azure 구독을 등록하는 데 필요한 단계를 수행하려면 팀과 공동 작업을 Microsoft 365 합니다.</span><span class="sxs-lookup"><span data-stu-id="ab5ee-185">The steps required to register Azure subscriptions for a mandatory retention period require collaboration with the Microsoft 365 team.</span></span> <span data-ttu-id="ab5ee-186">이 프로세스는 영업일로부터 5일까지 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ab5ee-186">This process can take from one to five business days.</span></span> <span data-ttu-id="ab5ee-187">이전에는 필수 보존 기간을 "취소 금지"라고도 합니다.</span><span class="sxs-lookup"><span data-stu-id="ab5ee-187">Previously, mandatory retention period was sometimes referred to as "Do Not Cancel".</span></span>
  
<span data-ttu-id="ab5ee-188">Microsoft 365 팀에 문의하기 전에 고객 키와 함께 사용하는 각 Azure 구독에 대해 다음 단계를 수행해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ab5ee-188">Before contacting the Microsoft 365 team, you must do the following steps for each Azure subscription that you use with Customer Key.</span></span> <span data-ttu-id="ab5ee-189">시작하기 전에 Azure PowerShell [Az](/powershell/azure/new-azureps-module-az) 모듈이 설치되어 있지 않은지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="ab5ee-189">Ensure that you have the [Azure PowerShell Az](/powershell/azure/new-azureps-module-az) module installed before you start.</span></span>
  
1. <span data-ttu-id="ab5ee-190">로그인한 Azure PowerShell.</span><span class="sxs-lookup"><span data-stu-id="ab5ee-190">Sign in with Azure PowerShell.</span></span> <span data-ttu-id="ab5ee-191">자세한 내용은 [으로 로그인을 Azure PowerShell.](/powershell/azure/authenticate-azureps)</span><span class="sxs-lookup"><span data-stu-id="ab5ee-191">For instructions, see [Sign in with Azure PowerShell](/powershell/azure/authenticate-azureps).</span></span>

2. <span data-ttu-id="ab5ee-192">Register-AzProviderFeature cmdlet을 실행하여 필수 보존 기간을 사용하기 위해 구독을 등록합니다.</span><span class="sxs-lookup"><span data-stu-id="ab5ee-192">Run the Register-AzProviderFeature cmdlet to register your subscriptions to use a mandatory retention period.</span></span> <span data-ttu-id="ab5ee-193">각 구독에 대해 이 작업을 완료합니다.</span><span class="sxs-lookup"><span data-stu-id="ab5ee-193">Complete this action for each subscription.</span></span>

   ```powershell
   Set-AzContext -SubscriptionId <SubscriptionId>
   Register-AzProviderFeature -FeatureName mandatoryRetentionPeriodEnabled -ProviderNamespace Microsoft.Resources
   ```

3. <span data-ttu-id="ab5ee-194">프로세스를 완료하기 위해 Microsoft에 문의합니다.</span><span class="sxs-lookup"><span data-stu-id="ab5ee-194">Contact Microsoft to complete the process.</span></span>

   - <span data-ttu-id="ab5ee-195">개별 Exchange Online 사서함에 DEP를 할당하기 위해 고객 키를 사용하도록 설정하는 [exock@microsoft.com.](mailto:exock@microsoft.com)</span><span class="sxs-lookup"><span data-stu-id="ab5ee-195">For enabling Customer Key for assigning DEP to individual Exchange Online mailboxes, contact [exock@microsoft.com](mailto:exock@microsoft.com).</span></span>

   - <span data-ttu-id="ab5ee-196">모든 테넌트 사용자에 대한 SharePoint Online 및 비즈니스용 OneDrive 콘텐츠(Teams 파일 포함)를 암호화할 수 있도록 DEP를 할당하기 위한 고객 키를 [spock@microsoft.com.](mailto:spock@microsoft.com)</span><span class="sxs-lookup"><span data-stu-id="ab5ee-196">For enabling Customer Key for assigning DEPs to encrypt SharePoint Online and OneDrive for Business content (including Teams files) for all tenant users, contact [spock@microsoft.com](mailto:spock@microsoft.com).</span></span>

   - <span data-ttu-id="ab5ee-197">모든 테넌트 사용자에 대해 여러 Microsoft 365(Exchange Online Teams, MIP, MIP EDM)에서 콘텐츠를 암호화할 수 있도록 DEP를 할당하기 위한 고객 키가 에 [m365-ck@service.microsoft.com.](mailto:m365-ck@service.microsoft.com)</span><span class="sxs-lookup"><span data-stu-id="ab5ee-197">For enabling Customer Key for assigning DEPs to encrypt content across multiple Microsoft 365 workloads (Exchange Online, Teams, MIP EDM) for all tenant users, contact [m365-ck@service.microsoft.com](mailto:m365-ck@service.microsoft.com).</span></span>

- <span data-ttu-id="ab5ee-198">전자 메일에 다음 정보를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="ab5ee-198">Include the following information in your email:</span></span>

   <span data-ttu-id="ab5ee-199">**제목:** 고객 키 \<*Your tenant's fully qualified domain name*\></span><span class="sxs-lookup"><span data-stu-id="ab5ee-199">**Subject**: Customer Key for \<*Your tenant's fully qualified domain name*\></span></span>

   <span data-ttu-id="ab5ee-200">**본문:** 필수 보존 기간을 완료할 구독 Get-AzProviderFeature 각 구독에 대한 결과값을 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="ab5ee-200">**Body**:  Include the subscription IDs for which you want to complete the mandatory retention period  and the output of Get-AzProviderFeature for each subscription.</span></span>

   <span data-ttu-id="ab5ee-201">이 프로세스 완료를 위한 SLA(서비스 수준 계약)는 Microsoft에 필수 보존 기간을 사용하기 위해 구독을 등록했다는 알림을(확인)한 후 영업일 5일입니다.</span><span class="sxs-lookup"><span data-stu-id="ab5ee-201">The Service Level Agreement (SLA) for completion of this process is five business days once Microsoft has been notified (and verified) that you have registered your subscriptions to use a mandatory retention period.</span></span>

4. <span data-ttu-id="ab5ee-202">Microsoft로부터 등록이 완료되었습니다는 알림을 받으면 다음과 같이 Get-AzProviderFeature 등록 상태를 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="ab5ee-202">Once you receive notification from Microsoft that registration is complete, verify the status of your registration by running the Get-AzProviderFeature command as follows.</span></span> <span data-ttu-id="ab5ee-203">확인되면 Get-AzProviderFeature 명령은 Registration State 속성에 **대해 Registered** 값을 **반환합니다.**</span><span class="sxs-lookup"><span data-stu-id="ab5ee-203">If verified, the Get-AzProviderFeature command returns a value of **Registered** for the **Registration State** property.</span></span> <span data-ttu-id="ab5ee-204">각 구독에 대해 이 단계를 완료합니다.</span><span class="sxs-lookup"><span data-stu-id="ab5ee-204">Complete this step for each subscription.</span></span>

   ```powershell
   Set-AzContext -SubscriptionId <SubscriptionId>
   Get-AzProviderFeature -ProviderNamespace Microsoft.Resources -FeatureName mandatoryRetentionPeriodEnabled
   ```

5. <span data-ttu-id="ab5ee-205">프로세스를 완료하기 위해 Register-AzResourceProvider 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="ab5ee-205">To complete the process, run the Register-AzResourceProvider command.</span></span> <span data-ttu-id="ab5ee-206">각 구독에 대해 이 단계를 완료합니다.</span><span class="sxs-lookup"><span data-stu-id="ab5ee-206">Complete this step for each subscription.</span></span>

   ```powershell
   Set-AzContext -SubscriptionId <SubscriptionId>
   Register-AzResourceProvider -ProviderNamespace Microsoft.KeyVault
   ```

### <a name="create-a-premium-azure-key-vault-in-each-subscription"></a><span data-ttu-id="ab5ee-207">각 구독에서 프리미엄 Azure Key Vault 만들기</span><span class="sxs-lookup"><span data-stu-id="ab5ee-207">Create a premium Azure Key Vault in each subscription</span></span>

<span data-ttu-id="ab5ee-208">키 저장소를 만드는 단계는 Azure [Key Vault](/azure/key-vault/general/overview)시작에 설명되어 있습니다. 이 문서에서는 Azure 키 자격 증명 모음 설치 및 시작, Azure PowerShell 연결, 리소스 그룹 만들기 및 해당 리소스 그룹에 키 자격 증명 모음 만들기를 안내합니다.</span><span class="sxs-lookup"><span data-stu-id="ab5ee-208">The steps to create a key vault are documented in [Getting Started with Azure Key Vault](/azure/key-vault/general/overview), which guides you through installing and launching Azure PowerShell, connecting to your Azure subscription, creating a resource group, and creating a key vault in that resource group.</span></span>
  
<span data-ttu-id="ab5ee-209">키 자격 증명 모음을 만들 때 SKU(Standard 또는 표준)를 선택해야 Premium.</span><span class="sxs-lookup"><span data-stu-id="ab5ee-209">When you create a key vault, you must choose a SKU: either Standard or Premium.</span></span> <span data-ttu-id="ab5ee-210">Standard SKU를 사용하면 Azure Key Vault 키를 소프트웨어로 보호할 수 있습니다. HSM(하드웨어 보안 모듈) 키 보호는 없습니다. Premium SKU를 사용하면 키 자격 증명 모음 키 보호를 위해 HSM을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ab5ee-210">The Standard SKU allows Azure Key Vault keys to be protected with software - there's no Hardware Security Module (HSM) key protection - and the Premium SKU allows the use of HSMs for protection of Key Vault keys.</span></span> <span data-ttu-id="ab5ee-211">Customer Key는 SKU 중 하나를 사용하는 주요 자격 증명 모음을 허용합니다. 그러나 Microsoft는 SKU를 사용하는 Premium 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="ab5ee-211">Customer Key accepts key vaults that use either SKU, though Microsoft strongly recommends that you use only the Premium SKU.</span></span> <span data-ttu-id="ab5ee-212">두 형식의 키 중 하나를 사용하는 작업의 비용은 동일하기 때문에 비용의 유일한 차이점은 각 HSM으로 보호되는 키에 대한 월별 비용입니다.</span><span class="sxs-lookup"><span data-stu-id="ab5ee-212">The cost of operations with keys of either type is the same, so the only difference in cost is the cost per month for each HSM-protected key.</span></span> <span data-ttu-id="ab5ee-213">자세한 [내용은 Key Vault 가격을](https://azure.microsoft.com/pricing/details/key-vault/) 참조합니다.</span><span class="sxs-lookup"><span data-stu-id="ab5ee-213">See [Key Vault pricing](https://azure.microsoft.com/pricing/details/key-vault/) for details.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="ab5ee-214">프로덕션 Premium SKU 키 자격 증명 모음 및 HSM으로 보호된 키를 사용하며 테스트 및 유효성 검사 목적으로 표준 SKU 키 자격 증명 모음 및 키만 사용하십시오.</span><span class="sxs-lookup"><span data-stu-id="ab5ee-214">Use the Premium SKU key vaults and HSM-protected keys for production data, and only use Standard SKU key vaults and keys for testing and validation purposes.</span></span>
  
<span data-ttu-id="ab5ee-215">고객 키를 사용할 각 Microsoft 365 서비스에 대해 만든 두 Azure 구독 각각에 키 자격 증명 모음을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="ab5ee-215">For each Microsoft 365 service with which you will use Customer Key, create a key vault in each of the two Azure subscriptions that you created.</span></span> <span data-ttu-id="ab5ee-216">예를 들어 고객 키가 Exchange Online, SharePoint Online 및 다중 작업 시나리오에 대해 DEP를 사용하도록 설정하려면 세 쌍의 키 자격 증명 모음을 만들어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ab5ee-216">For example, to enable Customer Key to use DEPs for Exchange Online, SharePoint Online, and multi-workload scenarios, you'll create three pairs of key vaults.</span></span>
  
<span data-ttu-id="ab5ee-217">자격 증명 모음을 연결하려는 DEP의 의도된 사용을 반영하는 주요 자격 증명 모음에 대한 이름 규칙 사용</span><span class="sxs-lookup"><span data-stu-id="ab5ee-217">Use a naming convention for key vaults that reflects the intended use of the DEP with which you will associate the vaults.</span></span> <span data-ttu-id="ab5ee-218">이름 규칙 권장 사항은 아래의 모범 사례 섹션을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="ab5ee-218">See the Best Practices section below for naming convention recommendations.</span></span>
  
<span data-ttu-id="ab5ee-219">각 데이터 암호화 정책에 대해 페어링된 별도의 자격 증명 모음 집합을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ab5ee-219">Create a separate, paired set of vaults for each data encryption policy.</span></span> <span data-ttu-id="ab5ee-220">이 Exchange Online 사서함에 정책을 할당할 때 데이터 암호화 정책의 범위가 선택됩니다.</span><span class="sxs-lookup"><span data-stu-id="ab5ee-220">For Exchange Online, the scope of a data encryption policy is chosen by you when you assign the policy to mailbox.</span></span> <span data-ttu-id="ab5ee-221">사서함에는 정책이 하나만 할당될 수 있으며 최대 50개 정책을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ab5ee-221">A mailbox can have only one policy assigned, and you can create up to 50 policies.</span></span> <span data-ttu-id="ab5ee-222">SharePoint Online 정책의 범위에는 지리적 위치 또는 지리적 위치에 있는 조직 내의 모든 데이터가 _포함됩니다._</span><span class="sxs-lookup"><span data-stu-id="ab5ee-222">The scope of a SharePoint Online policy includes all of the data within an organization in a geographic location, or _geo_.</span></span> <span data-ttu-id="ab5ee-223">다중 작업 정책의 범위에는 모든 사용자에 대해 지원되는 워크로드의 모든 데이터가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="ab5ee-223">The scope for a multi-workload policy includes all of the data across the supported workloads for all users.</span></span>

<span data-ttu-id="ab5ee-224">키 자격 증명 모음을 만들려면 Azure 리소스 그룹도 만들어야 합니다. 키 자격 증명 모음에는 저장 용량(작은 용량)이 필요하고 키 자격 증명 모음 로깅을 사용하도록 설정하면 저장된 데이터도 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="ab5ee-224">The creation of key vaults also requires the creation of Azure resource groups, since key vaults need storage capacity (though small) and Key Vault logging, if enabled, also generates stored data.</span></span> <span data-ttu-id="ab5ee-225">모범 사례로 Microsoft는 별도의 관리자를 사용하여 각 리소스 그룹을 관리하고 모든 관련 고객 키 리소스를 관리할 관리자 집합에 맞게 관리하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="ab5ee-225">As a best practice Microsoft recommends using separate administrators to manage each resource group, with the administration that's aligned with the set of administrators that will manage all related Customer Key resources.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="ab5ee-226">가용성을 최대화하기 위해 주요 자격 증명 모음을 Microsoft 365 서비스 가까이에 두는 경우 예를 들어 Exchange Online 조직이 북미에 있는 경우 주요 자격 증명 모음을 북미에 두는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="ab5ee-226">To maximize availability, place your key vaults in regions close to your Microsoft 365 service For example, if your Exchange Online organization is in North America, place your key vaults in North America.</span></span> <span data-ttu-id="ab5ee-227">조직이 Exchange Online 유럽에 있는 경우 주요 자격 증명 모음을 유럽에 두는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="ab5ee-227">If your Exchange Online organization is in Europe, place your key vaults in Europe.</span></span>
>
> <span data-ttu-id="ab5ee-228">키 자격 증명 모음에 대해 공통적인 prefix를 사용하며 키 자격 증명 모음 및 키의 사용 및 범위에 대한 약어를 포함합니다(예: 자격 증명 모음이 북미에 있는 Contoso SharePoint 서비스의 경우, 가능한 이름 쌍은 Contoso-CK-SP-NA-VaultA1 및 Contoso-CK-SP-NA-VaultA2)입니다.</span><span class="sxs-lookup"><span data-stu-id="ab5ee-228">Use a common prefix for key vaults, and include an abbreviation of the use and scope of the key vault and keys (e.g., for the Contoso SharePoint service where the vaults will be located in North America, a possible pair of names is Contoso-CK-SP-NA-VaultA1 and Contoso-CK-SP-NA-VaultA2.</span></span> <span data-ttu-id="ab5ee-229">자격 증명 모음 이름은 Azure 내에서 전역적으로 고유한 문자열이기 때문에 다른 Azure 고객이 원하는 이름을 이미 클레임할 경우 원하는 이름을 변형해 보아야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ab5ee-229">Vault names are globally unique strings within Azure, so you may need to try variations of your desired names in case the desired names are already claimed by other Azure customers.</span></span> <span data-ttu-id="ab5ee-230">2017년 7월 현재 자격 증명 모음 이름은 변경할 수 없습니다. 따라서 설치를 위한 서면 계획을 세우고 두 번째 사람을 사용하여 계획이 올바르게 실행되고 있는지 확인하는 것이 가장 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="ab5ee-230">As of July 2017 vault names cannot be changed, so a best practice is to have a written plan for setup and use a second person to verify the plan is executed correctly.</span></span>
>
> <span data-ttu-id="ab5ee-231">가능한 경우 페어링되지 않은 지역에서 자격 증명 모음을 만드십시오.</span><span class="sxs-lookup"><span data-stu-id="ab5ee-231">If possible, create your vaults in non-paired regions.</span></span> <span data-ttu-id="ab5ee-232">페어링된 Azure 지역은 서비스 오류 도메인 전체에서 고가용성을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="ab5ee-232">Paired Azure regions provide high availability across service failure domains.</span></span> <span data-ttu-id="ab5ee-233">따라서 지역 쌍은 서로의 백업 지역으로 생각할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ab5ee-233">Therefore, regional pairs can be thought of as each other's backup region.</span></span> <span data-ttu-id="ab5ee-234">즉, 한 지역에 배치된 Azure 리소스가 페어링된 지역을 통해 내결결성을 자동으로 얻게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ab5ee-234">This means that an Azure resource that is placed in one region is automatically gaining fault tolerance through the paired region.</span></span> <span data-ttu-id="ab5ee-235">이러한 이유로 지역이 쌍을 이루는 데이터 암호화 정책에서 사용되는 두 자격 증명 모음에 대한 지역을 선택하면 총 2개의 가용성 영역만 사용 중입니다.</span><span class="sxs-lookup"><span data-stu-id="ab5ee-235">For this reason, choosing regions for two vaults used in a data encryption policy where the regions are paired means that only a total of two regions of availability are in use.</span></span> <span data-ttu-id="ab5ee-236">대부분의 지역에는 두 개의 지역만 있으므로 페어링되지 않은 지역을 선택할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="ab5ee-236">Most geographies only have two regions, so it's not yet possible to select non-paired regions.</span></span> <span data-ttu-id="ab5ee-237">가능한 경우 데이터 암호화 정책과 함께 사용되는 두 자격 증명 모음에 대해 쌍으로 설정되지 않은 두 지역을 선택하세요.</span><span class="sxs-lookup"><span data-stu-id="ab5ee-237">If possible, choose two non-paired regions for the two vaults used with a data encryption policy.</span></span> <span data-ttu-id="ab5ee-238">이 혜택은 총 4개의 가용성 영역의 이점입니다.</span><span class="sxs-lookup"><span data-stu-id="ab5ee-238">This benefits from a total of four regions of availability.</span></span> <span data-ttu-id="ab5ee-239">자세한 내용은 비즈니스 연속성 및 재해 [복구(BCDR): 현재](/azure/best-practices-availability-paired-regions) 지역 쌍 목록은 Azure 페어링 지역을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="ab5ee-239">For more information, see [Business continuity and disaster recovery (BCDR): Azure Paired Regions](/azure/best-practices-availability-paired-regions) for a current list of regional pairs.</span></span>
  
### <a name="assign-permissions-to-each-key-vault"></a><span data-ttu-id="ab5ee-240">각 키 자격 증명 모음에 사용 권한 할당</span><span class="sxs-lookup"><span data-stu-id="ab5ee-240">Assign permissions to each key vault</span></span>

<span data-ttu-id="ab5ee-241">구현에 따라 각 키 자격 증명 모음에 대해 세 가지 개별 권한 집합을 정의해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ab5ee-241">You'll need to define three separate sets of permissions for each key vault, depending on your implementation.</span></span> <span data-ttu-id="ab5ee-242">예를 들어 다음 각 권한 집합에 대해 하나의 사용 권한 집합을 정의해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ab5ee-242">For example, you will need to define one set of permissions for each of the following:</span></span>
  
- <span data-ttu-id="ab5ee-243">**조직의 키** 자격 증명 모음을 매일 관리하기 위한 주요 자격 증명 모음 관리자</span><span class="sxs-lookup"><span data-stu-id="ab5ee-243">**Key vault administrators** that do day-to-day management of your key vault for your organization.</span></span> <span data-ttu-id="ab5ee-244">이러한 작업에는 백업, 만들기, 가져오기, 가져오기, 목록 및 복원이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="ab5ee-244">These tasks include backup, create, get, import, list, and restore.</span></span>

  > [!IMPORTANT]
  > <span data-ttu-id="ab5ee-245">키 자격 증명 모음 관리자에게 할당된 권한 집합에는 키를 삭제할 수 있는 권한이 포함되어 있지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="ab5ee-245">The set of permissions assigned to key vault administrators does not include the permission to delete keys.</span></span> <span data-ttu-id="ab5ee-246">이는 의도적인 것이고 중요한 사례입니다.</span><span class="sxs-lookup"><span data-stu-id="ab5ee-246">This is intentional and an important practice.</span></span> <span data-ttu-id="ab5ee-247">암호화 키를 삭제하면 데이터가 영구적으로 삭제되는 것이 일반적이지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="ab5ee-247">Deleting encryption keys is not typically done, since doing so permanently destroys data.</span></span> <span data-ttu-id="ab5ee-248">이 권한은 기본적으로 주요 자격 증명 모음 관리자에게 부여하지 않는 것이 가장 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="ab5ee-248">As a best practice, do not grant this permission to key vault administrators by default.</span></span> <span data-ttu-id="ab5ee-249">대신 주요 자격 증명 모음 참가자에 대해 이 정보를 예약하고 결과에 대한 명확한 이해가 있는 경우 단기적으로 관리자에게 할당해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ab5ee-249">Instead, reserve this for key vault contributors and only assign it to an administrator on a short term basis once a clear understanding of the consequences is understood.</span></span>
  
  <span data-ttu-id="ab5ee-250">조직의 사용자에게 이러한 권한을 할당하려면 조직에서 Azure 구독에 Azure PowerShell.</span><span class="sxs-lookup"><span data-stu-id="ab5ee-250">To assign these permissions to a user in your organization, sign in to your Azure subscription with Azure PowerShell.</span></span> <span data-ttu-id="ab5ee-251">자세한 내용은 [으로 로그인을 Azure PowerShell.](/powershell/azure/authenticate-azureps)</span><span class="sxs-lookup"><span data-stu-id="ab5ee-251">For instructions, see [Sign in with Azure PowerShell](/powershell/azure/authenticate-azureps).</span></span>

- <span data-ttu-id="ab5ee-252">Set-AzKeyVaultAccessPolicy cmdlet을 실행하여 필요한 사용 권한을 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="ab5ee-252">Run the Set-AzKeyVaultAccessPolicy cmdlet to assign the necessary permissions.</span></span>

   ```powershell
   Set-AzKeyVaultAccessPolicy -VaultName <vault name> -UserPrincipalName <UPN of user> -PermissionsToKeys create,import,list,get,backup,restore
   ```

   <span data-ttu-id="ab5ee-253">예:</span><span class="sxs-lookup"><span data-stu-id="ab5ee-253">For example:</span></span>

   ```powershell
   Set-AzKeyVaultAccessPolicy -VaultName Contoso-CK-EX-NA-VaultA1 -UserPrincipalName alice@contoso.com -PermissionsToKeys create,import,list,get,backup,restore
   ```

- <span data-ttu-id="ab5ee-254">Azure **Key Vault** 자체에 대한 사용 권한을 변경할 수 있는 주요 자격 증명 모음 참가자입니다.</span><span class="sxs-lookup"><span data-stu-id="ab5ee-254">**Key vault contributors** that can change permissions on the Azure Key Vault itself.</span></span> <span data-ttu-id="ab5ee-255">직원이 팀을 떠나거나 팀에 합류할 때 이러한 권한을 변경해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ab5ee-255">You'll need to change these permissions as employees leave or join your team.</span></span> <span data-ttu-id="ab5ee-256">키 자격 증명 모음 관리자가 키를 삭제하거나 복원할 수 있는 권한이 합법적으로 필요한 드물지만 사용 권한도 변경해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ab5ee-256">In the rare situation that the key vault administrators legitimately need permission to delete or restore a key you'll also need to change the permissions.</span></span> <span data-ttu-id="ab5ee-257">이 주요 자격 증명 모음 참가자 집합에는 키 자격 증명 모음에 대한 **참가자** 역할을 부여해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ab5ee-257">This set of key vault contributors needs to be granted the **Contributor** role on your key vault.</span></span> <span data-ttu-id="ab5ee-258">Azure Resource Manager를 사용하여 이 역할을 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ab5ee-258">You can assign this role by using Azure Resource Manager.</span></span> <span data-ttu-id="ab5ee-259">자세한 단계는 Role-Based 액세스 제어를 사용하여 Azure 구독 리소스에 대한 액세스 [관리를 참조하세요.](/azure/active-directory/role-based-access-control-configure)</span><span class="sxs-lookup"><span data-stu-id="ab5ee-259">For detailed steps, see [Use Role-Based Access Control to manage access to your Azure subscription resources](/azure/active-directory/role-based-access-control-configure).</span></span> <span data-ttu-id="ab5ee-260">구독을 만드는 관리자는 이 액세스 권한을 암시적으로 사용할 수 있으며 참가자 역할에 다른 관리자를 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ab5ee-260">The administrator who creates a subscription has this access implicitly, and the ability to assign other administrators to the Contributor role.</span></span>

- <span data-ttu-id="ab5ee-261">**고객 Microsoft 365** 사용하는 모든 키 자격 증명 모음에 대해 응용 프로그램에 대한 사용 권한을 부여하려면 wrapKey, unwrapKey 및 해당 Microsoft 365 서비스 사용자에 대한 사용 권한을 부여해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ab5ee-261">**Permissions to Microsoft 365 applications** for every key vault that you use for Customer Key, you need to give wrapKey, unwrapKey, and get permissions to the corresponding Microsoft 365 Service Principal.</span></span> 

<span data-ttu-id="ab5ee-262">서비스 사용자에 Microsoft 365 권한을 부여하려면 다음 구문을 사용하여 **Set-AzKeyVaultAccessPolicy** cmdlet을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="ab5ee-262">To give permission to Microsoft 365 Service Principal, run the **Set-AzKeyVaultAccessPolicy** cmdlet using the following syntax:</span></span>

   ```powershell
   Set-AzKeyVaultAccessPolicy -VaultName <vault name> -PermissionsToKeys wrapKey,unwrapKey,get -ServicePrincipalName <Office 365 appID>
   ```

   <span data-ttu-id="ab5ee-263">여기서,</span><span class="sxs-lookup"><span data-stu-id="ab5ee-263">Where:</span></span>

   - <span data-ttu-id="ab5ee-264">*자격 증명 모음* 이름은 만든 키 자격 증명 모음의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="ab5ee-264">*vault name* is the name of the key vault you created.</span></span>
   - <span data-ttu-id="ab5ee-265">앱 Exchange Online 비즈니스용 Skype *appID를 Office 365*`00000002-0000-0ff1-ce00-000000000000`</span><span class="sxs-lookup"><span data-stu-id="ab5ee-265">For Exchange Online and Skype for Business, replace  *Office 365 appID* with `00000002-0000-0ff1-ce00-000000000000`</span></span>
   - <span data-ttu-id="ab5ee-266">SharePoint Online, 비즈니스용 OneDrive 및 Teams 파일의 경우 *Office 365 appID를*`00000003-0000-0ff1-ce00-000000000000`</span><span class="sxs-lookup"><span data-stu-id="ab5ee-266">For SharePoint Online, OneDrive for Business, and Teams files, replace  *Office 365 appID* with `00000003-0000-0ff1-ce00-000000000000`</span></span>
   - <span data-ttu-id="ab5ee-267">모든 테넌트 사용자에게 적용되는 다중 작업 정책(Exchange, Teams, MIP EDM)의 경우 *appID를* Office 365`c066d759-24ae-40e7-a56f-027002b5d3e4`</span><span class="sxs-lookup"><span data-stu-id="ab5ee-267">For multi-workload policy (Exchange, Teams, MIP EDM) that applies to all tenant users, replace *Office 365 appID* with `c066d759-24ae-40e7-a56f-027002b5d3e4`</span></span>

  <span data-ttu-id="ab5ee-268">예: 사용자 및 Exchange Online 권한 비즈니스용 Skype.</span><span class="sxs-lookup"><span data-stu-id="ab5ee-268">Example: Setting permissions for Exchange Online and Skype for Business:</span></span>

   ```powershell
   Set-AzKeyVaultAccessPolicy -VaultName Contoso-CK-EX-NA-VaultA1 -PermissionsToKeys wrapKey,unwrapKey,get -ServicePrincipalName 00000002-0000-0ff1-ce00-000000000000
   ```

  <span data-ttu-id="ab5ee-269">예: SharePoint Online, 비즈니스용 OneDrive 및 Teams 권한 설정:</span><span class="sxs-lookup"><span data-stu-id="ab5ee-269">Example: Setting permissions for SharePoint Online, OneDrive for Business, and Teams files:</span></span>

   ```powershell
   Set-AzKeyVaultAccessPolicy -VaultName Contoso-CK-SP-NA-VaultA1 -PermissionsToKeys wrapKey,unwrapKey,get -ServicePrincipalName 00000003-0000-0ff1-ce00-000000000000
   ```

### <a name="make-sure-soft-delete-is-enabled-on-your-key-vaults"></a><span data-ttu-id="ab5ee-270">키 자격 증명 모음에서 소프트 삭제가 사용하도록 설정되어 있는지 확인</span><span class="sxs-lookup"><span data-stu-id="ab5ee-270">Make sure soft delete is enabled on your key vaults</span></span>

<span data-ttu-id="ab5ee-271">키를 빠르게 복구할 수 있는 경우 실수로 또는 악의적으로 삭제된 키로 인해 확장된 서비스가 사용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="ab5ee-271">When you can quickly recover your keys, you are less likely to experience an extended service outage due to accidentally or maliciously deleted keys.</span></span> <span data-ttu-id="ab5ee-272">고객 키와 함께 키를 사용하려면 먼저 소프트 삭제라고 하는 이 구성을 사용하도록 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ab5ee-272">Enable this configuration, referred to as Soft Delete, before you can use your keys with Customer Key.</span></span> <span data-ttu-id="ab5ee-273">소프트 삭제를 사용하도록 설정하면 백업에서 복원하지 않고도 삭제 후 90일 이내에 키나 자격 증명 모음을 복구할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ab5ee-273">Enabling Soft Delete allows you to recover keys or vaults within 90 days of deletion without having to restore them from backup.</span></span>
  
<span data-ttu-id="ab5ee-274">키 자격 증명 모음에서 소프트 삭제를 사용하도록 설정하려면 다음 단계를 완료합니다.</span><span class="sxs-lookup"><span data-stu-id="ab5ee-274">To enable Soft Delete on your key vaults, complete these steps:</span></span>
  
1. <span data-ttu-id="ab5ee-275">구독을 사용하여 Azure 구독에 Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="ab5ee-275">Sign in to your Azure subscription with Windows PowerShell.</span></span> <span data-ttu-id="ab5ee-276">자세한 내용은 [으로 로그인을 Azure PowerShell.](/powershell/azure/authenticate-azureps)</span><span class="sxs-lookup"><span data-stu-id="ab5ee-276">For instructions, see [Sign in with Azure PowerShell](/powershell/azure/authenticate-azureps).</span></span>

2. <span data-ttu-id="ab5ee-277">[Get-AzKeyVault](/powershell/module/az.keyvault/get-azkeyvault) cmdlet을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="ab5ee-277">Run the [Get-AzKeyVault](/powershell/module/az.keyvault/get-azkeyvault) cmdlet.</span></span> <span data-ttu-id="ab5ee-278">이 예에서 자격 증명 모음 *이름은* 소프트 삭제를 사용하도록 설정하는 키 자격 증명 모음의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="ab5ee-278">In this example, *vault name* is the name of the key vault for which you're enabling soft delete:</span></span>

   ```powershell
   $v = Get-AzKeyVault -VaultName <vault name>
   $r = Get-AzResource -ResourceId $v.ResourceId
   $r.Properties | Add-Member -MemberType NoteProperty -Name enableSoftDelete -Value 'True'
   Set-AzResource -ResourceId $r.ResourceId -Properties $r.Properties
   ```

3. <span data-ttu-id="ab5ee-279">**Get-AzKeyVault** cmdlet을 실행하여 키 자격 증명 모음에 대해 소프트 삭제가 구성되어 있는지 확인</span><span class="sxs-lookup"><span data-stu-id="ab5ee-279">Confirm soft delete is configured for the key vault by running the **Get-AzKeyVault** cmdlet.</span></span> <span data-ttu-id="ab5ee-280">키 자격 증명 모음에 대해 소프트 삭제가 제대로 구성되어 있는 경우 _Soft Delete Enabled_ 속성은 True 값을 **반환합니다.**</span><span class="sxs-lookup"><span data-stu-id="ab5ee-280">If soft delete is configured properly for the key vault, then the _Soft Delete Enabled_ property returns a value of **True**:</span></span>

   ```powershell
   Get-AzKeyVault -VaultName <vault name> | fl
   ```

### <a name="add-a-key-to-each-key-vault-either-by-creating-or-importing-a-key"></a><span data-ttu-id="ab5ee-281">키를 만들거나 가져와서 각 키 자격 증명 모음에 키 추가</span><span class="sxs-lookup"><span data-stu-id="ab5ee-281">Add a key to each key vault either by creating or importing a key</span></span>

<span data-ttu-id="ab5ee-282">Azure Key Vault에 키를 추가하는 방법에는 두 가지가 있습니다. 키 자격 증명 모음에서 직접 키를 만들거나 키를 가져올 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ab5ee-282">There are two ways to add keys to an Azure Key Vault; you can create a key directly in Key Vault, or you can import a key.</span></span> <span data-ttu-id="ab5ee-283">Key Vault에서 직접 키를 만드는 것은 덜 복잡하지만 키를 가져오면 키 생성 방법을 완전히 제어할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ab5ee-283">Creating a key directly in Key Vault is less complicated, but importing a key provides total control over how the key is generated.</span></span> <span data-ttu-id="ab5ee-284">RSA 키를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="ab5ee-284">Use the RSA keys.</span></span> <span data-ttu-id="ab5ee-285">Azure Key Vault는 타원 곡선 키로 래핑 및 래핑을 지원하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="ab5ee-285">Azure Key Vault doesn't support wrapping and unwrapping with elliptical curve keys.</span></span>
  
<span data-ttu-id="ab5ee-286">키 자격 증명 모음에서 직접 키를 만들 수 있도록 [Add-AzKeyVaultKey](/powershell/module/az.keyvault/add-azkeyvaultkey) cmdlet을 다음과 같이 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="ab5ee-286">To create a key directly in your key vault, run the [Add-AzKeyVaultKey](/powershell/module/az.keyvault/add-azkeyvaultkey) cmdlet as follows:</span></span>
  
```powershell
Add-AzKeyVaultKey -VaultName <vault name> -Name <key name> -Destination <HSM|Software> -KeyOps wrapKey,unwrapKey
```

<span data-ttu-id="ab5ee-287">여기서,</span><span class="sxs-lookup"><span data-stu-id="ab5ee-287">Where:</span></span>

- <span data-ttu-id="ab5ee-288">*자격 증명* 모음 이름은 키를 만들 키 자격 증명 모음의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="ab5ee-288">*vault name* is the name of the key vault in which you want to create the key.</span></span>

- <span data-ttu-id="ab5ee-289">*key name은* 새 키를 제공하려는 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="ab5ee-289">*key name* is the name you want to give the new key.</span></span>

  > [!TIP]
  > <span data-ttu-id="ab5ee-290">키 자격 증명 모음에 대해 위에서 설명한 대로 유사한 명명 규칙을 사용하는 이름 키입니다.</span><span class="sxs-lookup"><span data-stu-id="ab5ee-290">Name keys using a similar naming convention as described above for key vaults.</span></span> <span data-ttu-id="ab5ee-291">이렇게 하면 키 이름만 표시하는 도구에서 문자열은 자체 설명을 합니다.</span><span class="sxs-lookup"><span data-stu-id="ab5ee-291">This way, in tools that show only the key name, the string is self-describing.</span></span>
  
<span data-ttu-id="ab5ee-292">HSM으로 키를 보호하려는 경우 **HSM을** _Destination_ 매개 변수 값으로 지정해야 합니다. 그렇지 않으면 Software 를 **지정합니다.**</span><span class="sxs-lookup"><span data-stu-id="ab5ee-292">If you intend to protect the key with an HSM, ensure that you specify **HSM** as the value of the _Destination_ parameter, otherwise, specify **Software**.</span></span>

<span data-ttu-id="ab5ee-293">예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="ab5ee-293">For example,</span></span>
  
```powershell
Add-AzKeyVaultKey -VaultName Contoso-CK-EX-NA-VaultA1 -Name Contoso-CK-EX-NA-VaultA1-Key001 -Destination HSM -KeyOps wrapKey,unwrapKey
```

<span data-ttu-id="ab5ee-294">키를 키 자격 증명 모음으로 직접 가져오기 위해 nCipher nShield 하드웨어 보안 모듈이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="ab5ee-294">To import a key directly into your key vault, you need to have a nCipher nShield Hardware Security Module.</span></span>
  
<span data-ttu-id="ab5ee-295">일부 조직에서는 키의 입증을 설정하기 위해 이 접근 방식을 선호하고 이 방법을 통해 다음 증명도 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="ab5ee-295">Some organizations prefer this approach to establish the provenance of their keys, and then this method also provides the following attestations:</span></span>
  
- <span data-ttu-id="ab5ee-296">가져오기에 사용되는 도구et에는 nCipher에서 생성한 키를 암호화하는 데 사용되는 KEK(Key Exchange Key)가 내보낼 수 없는 것으로, nCipher에서 제조한 정품 HSM 내에서 생성되었다는 의증이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ab5ee-296">The toolset used for import includes attestation from nCipher that the Key Exchange Key (KEK) that is used to encrypt the key you generate is not exportable and is generated inside a genuine HSM that was manufactured by nCipher.</span></span>

- <span data-ttu-id="ab5ee-297">도구 모음에는 nCipher에서 Azure Key Vault 보안 월드가 nCipher에서 제조한 정품 HSM에서도 생성되었다는 증명이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ab5ee-297">The toolset includes attestation from nCipher that the Azure Key Vault security world was also generated on a genuine HSM manufactured by nCipher.</span></span> <span data-ttu-id="ab5ee-298">이 증명은 Microsoft가 정품 nCipher 하드웨어도 사용하고 있는 것을 증명합니다.</span><span class="sxs-lookup"><span data-stu-id="ab5ee-298">This attestation proves that Microsoft is also using genuine nCipher hardware.</span></span>

<span data-ttu-id="ab5ee-299">보안 그룹에 확인하여 위의 의거가 필요한지 여부를 파악합니다.</span><span class="sxs-lookup"><span data-stu-id="ab5ee-299">Check with your security group to determine if the above attestations are required.</span></span> <span data-ttu-id="ab5ee-300">키를 사내에 만들고 키 자격 증명 모음으로 가져오는 자세한 단계는 [Azure Key Vault에 대한 HSM](/azure/key-vault/keys/hsm-protected-keys)보호 키를 생성하고 전송하는 방법을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="ab5ee-300">For detailed steps to create a key on-premises and import it into your key vault, see [How to generate and transfer HSM-protected keys for Azure Key Vault](/azure/key-vault/keys/hsm-protected-keys).</span></span> <span data-ttu-id="ab5ee-301">Azure 지침을 사용하여 각 키 자격 증명 모음에 키를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ab5ee-301">Use the Azure instructions to create a key in each key vault.</span></span>
  
### <a name="check-the-recovery-level-of-your-keys"></a><span data-ttu-id="ab5ee-302">키의 복구 수준 확인</span><span class="sxs-lookup"><span data-stu-id="ab5ee-302">Check the recovery level of your keys</span></span>

<span data-ttu-id="ab5ee-303">Microsoft 365 Azure Key Vault 구독이 취소 금지로 설정되어 있으며 고객 키에서 사용하는 키가 소프트 삭제를 사용하도록 설정되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ab5ee-303">Microsoft 365 requires that the Azure Key Vault subscription is set to Do Not Cancel and that the keys used by Customer Key have soft delete enabled.</span></span> <span data-ttu-id="ab5ee-304">키의 복구 수준을 확인하여 구독 설정을 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ab5ee-304">You can confirm you subscriptions settings by looking at the recovery level on your keys.</span></span>
  
<span data-ttu-id="ab5ee-305">키의 복구 수준을 확인 Azure PowerShell 다음과 Get-AzKeyVaultKey cmdlet을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="ab5ee-305">To check the recovery level of a key, in Azure PowerShell, run the Get-AzKeyVaultKey cmdlet as follows:</span></span>
  
```powershell
(Get-AzKeyVaultKey -VaultName <vault name> -Name <key name>).Attributes
```

<span data-ttu-id="ab5ee-306">Recovery _Level_ 속성이 **Recoverable+ProtectedSubscription** 값 외의 값을 반환하는 경우 구독을 취소 금지 목록에 추가하고 각 키 자격 증명 모음에서 소프트 삭제를 사용하도록 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ab5ee-306">If the _Recovery Level_ property returns anything other than a value of **Recoverable+ProtectedSubscription**, ensure that you have put the subscription on the Do Not Cancel list and that you have soft delete enabled on each of your key vaults.</span></span>
  
### <a name="back-up-azure-key-vault"></a><span data-ttu-id="ab5ee-307">Azure Key Vault 백업</span><span class="sxs-lookup"><span data-stu-id="ab5ee-307">Back up Azure Key Vault</span></span>

<span data-ttu-id="ab5ee-308">키가 만들어지거나 키가 변경된 직후 백업을 수행하고 온라인 및 오프라인으로 백업 복사본을 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="ab5ee-308">Immediately following creation or any change to a key, perform a backup and store copies of the backup, both online and offline.</span></span> <span data-ttu-id="ab5ee-309">오프라인 복사본을 네트워크에 연결하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="ab5ee-309">Don't connect offline copies to any network.</span></span> <span data-ttu-id="ab5ee-310">대신 물리적 안전 또는 상업적 저장소 시설과 같은 오프라인 위치에 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="ab5ee-310">Instead store them in an offline location, such as in a physical safe or commercial storage facility.</span></span> <span data-ttu-id="ab5ee-311">재해가 발생할 경우 액세스할 수 있는 위치에 백업 복사본을 하나 이상 저장해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ab5ee-311">At least one copy of the backup should be stored in a location that will be accessible if a disaster occurs.</span></span> <span data-ttu-id="ab5ee-312">키 자격 증명 키를 영구적으로 삭제하거나 사용할 수 없는 경우 백업 Blob은 키 자료를 복원하는 유일한 수단입니다.</span><span class="sxs-lookup"><span data-stu-id="ab5ee-312">The backup blobs are the sole means of restoring key material should a Key Vault key be permanently destroyed or otherwise rendered inoperable.</span></span> <span data-ttu-id="ab5ee-313">Azure Key Vault 외부에서 Azure Key Vault로 가져온 키는 고객 키가 키를 사용하는 데 필요한 메타데이터가 외부 키와 함께 존재하지 않는 것이기 때문에 백업으로 자격이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="ab5ee-313">Keys that are external to Azure Key Vault and imported to Azure Key Vault don't qualify as a backup because the metadata necessary for Customer Key to use the key doesn't exist with the external key.</span></span> <span data-ttu-id="ab5ee-314">Azure Key Vault에서 수행한 백업만 고객 키를 사용하여 복원 작업에 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ab5ee-314">Only a backup taken from Azure Key Vault can be used for restore operations with Customer Key.</span></span> <span data-ttu-id="ab5ee-315">따라서 키를 업로드하거나 만든 후 Azure Key Vault의 백업을 만들어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ab5ee-315">Therefore, you must create a backup of Azure Key Vault after you upload or create a key.</span></span>
  
<span data-ttu-id="ab5ee-316">Azure Key Vault 키의 백업을 만들 경우 다음과 같이 [Backup-AzKeyVaultKey](/powershell/module/az.keyvault/backup-azkeyvaultkey) cmdlet을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="ab5ee-316">To create a backup of an Azure Key Vault key, run the [Backup-AzKeyVaultKey](/powershell/module/az.keyvault/backup-azkeyvaultkey) cmdlet as follows:</span></span>

```powershell
Backup-AzKeyVaultKey -VaultName <vault name> -Name <key name>
-OutputFile <filename.backup>
```

<span data-ttu-id="ab5ee-317">출력 파일에서 접미사 를 사용하는지 `.backup` 확인</span><span class="sxs-lookup"><span data-stu-id="ab5ee-317">Ensure that your output file uses the suffix `.backup`.</span></span>
  
<span data-ttu-id="ab5ee-318">이 cmdlet에서 생성되는 출력 파일은 암호화되며 Azure Key Vault 외부에서 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="ab5ee-318">The output file resulting from this cmdlet is encrypted and cannot be used outside of Azure Key Vault.</span></span> <span data-ttu-id="ab5ee-319">백업은 백업을 수행한 Azure 구독으로만 복원할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ab5ee-319">The backup can be restored only to the Azure subscription from which the backup was taken.</span></span>
  
> [!TIP]
> <span data-ttu-id="ab5ee-320">출력 파일의 경우 자격 증명 모음 이름과 키 이름을 조합하여 선택하십시오.</span><span class="sxs-lookup"><span data-stu-id="ab5ee-320">For the output file, choose a combination of your vault name and key name.</span></span> <span data-ttu-id="ab5ee-321">이렇게 하면 파일 이름이 자체 설명으로 지정됩니다.</span><span class="sxs-lookup"><span data-stu-id="ab5ee-321">This will make the file name self-describing.</span></span> <span data-ttu-id="ab5ee-322">또한 백업 파일 이름이 충돌하지 않도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="ab5ee-322">It will also ensure that backup file names do not collide.</span></span>
  
<span data-ttu-id="ab5ee-323">예:</span><span class="sxs-lookup"><span data-stu-id="ab5ee-323">For example:</span></span>
  
```powershell
Backup-AzKeyVaultKey -VaultName Contoso-CK-EX-NA-VaultA1 -Name Contoso-CK-EX-NA-VaultA1-Key001 -OutputFile Contoso-CK-EX-NA-VaultA1-Key001-Backup-20170802.backup
```

### <a name="validate-azure-key-vault-configuration-settings"></a><span data-ttu-id="ab5ee-324">Azure Key Vault 구성 설정 유효성 검사</span><span class="sxs-lookup"><span data-stu-id="ab5ee-324">Validate Azure Key Vault configuration settings</span></span>

<span data-ttu-id="ab5ee-325">DEP에서 키를 사용하기 전에 유효성을 검사하는 것은 선택 사항이지만 매우 권장됩니다.</span><span class="sxs-lookup"><span data-stu-id="ab5ee-325">Validating before using keys in a DEP is optional, but highly recommended.</span></span> <span data-ttu-id="ab5ee-326">단계에 따라 이 문서에 설명된 키와 자격 증명 모음을 설정하는 경우 고객 키를 구성하기 전에 Azure Key Vault 리소스의 상태 유효성을 검사합니다.</span><span class="sxs-lookup"><span data-stu-id="ab5ee-326">If you use steps to set up your keys and vaults other than the ones described in this article, validate the health of your Azure Key Vault resources before you configure Customer Key.</span></span>
  
<span data-ttu-id="ab5ee-327">키에 , 및 작업이 `get` `wrapKey` 사용하도록 `unwrapKey` 설정되어 있는지 확인:</span><span class="sxs-lookup"><span data-stu-id="ab5ee-327">To verify that your keys have `get`, `wrapKey`, and `unwrapKey` operations enabled:</span></span>
  
<span data-ttu-id="ab5ee-328">다음과 [같이 Get-AzKeyVault](/powershell/module/az.keyvault/get-azkeyvault) cmdlet을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="ab5ee-328">Run the [Get-AzKeyVault](/powershell/module/az.keyvault/get-azkeyvault) cmdlet as follows:</span></span>
  
```powershell
Get-AzKeyVault -VaultName <vault name>
```

<span data-ttu-id="ab5ee-329">출력에서 액세스 정책 및 Exchange Online ID(GUID) 또는 SharePoint Online ID(GUID)를 찾아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ab5ee-329">In the output, look for the Access Policy and for the Exchange Online identity (GUID) or the SharePoint Online identity (GUID) as appropriate.</span></span> <span data-ttu-id="ab5ee-330">위의 세 사용 권한은 모두 키에 대한 사용 권한 아래에 표시되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ab5ee-330">All three of the above permissions must be shown under Permissions to Keys.</span></span>
  
<span data-ttu-id="ab5ee-331">액세스 정책 구성이 올바르지 않은 경우 다음과 Set-AzKeyVaultAccessPolicy cmdlet을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="ab5ee-331">If the access policy configuration is incorrect, run the Set-AzKeyVaultAccessPolicy cmdlet as follows:</span></span>
  
```powershell
Set-AzKeyVaultAccessPolicy -VaultName <vault name> -PermissionsToKeys wrapKey,unwrapKey,get -ServicePrincipalName <Office 365 appID>
```

<span data-ttu-id="ab5ee-332">예를 들어 다음 Exchange Online 비즈니스용 Skype.</span><span class="sxs-lookup"><span data-stu-id="ab5ee-332">For example, for Exchange Online and Skype for Business:</span></span>
  
```powershell
Set-AzKeyVaultAccessPolicy -VaultName Contoso-CK-EX-NA-VaultA1 
-PermissionsToKeys wrapKey,unwrapKey,get -ServicePrincipalName 00000002-0000-0ff1-ce00-000000000000
```

<span data-ttu-id="ab5ee-333">예를 들어 SharePoint Online 및 비즈니스용 OneDrive:</span><span class="sxs-lookup"><span data-stu-id="ab5ee-333">For example, for SharePoint Online and OneDrive for Business:</span></span>
  
```powershell
Set-AzKeyVaultAccessPolicy -VaultName Contoso-CK-SP-NA-VaultA1
-PermissionsToKeys wrapKey,unwrapKey,get -ServicePrincipalName 00000003-0000-0ff1-ce00-000000000000
```

<span data-ttu-id="ab5ee-334">키에 대한 만료 날짜가 설정되어 있지 않은지 확인하기 위해 다음과 같이 [Get-AzKeyVaultKey](/powershell/module/az.keyvault/get-azkeyvault) cmdlet을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="ab5ee-334">To verify that an expiration date isn't set for your keys, run the [Get-AzKeyVaultKey](/powershell/module/az.keyvault/get-azkeyvault) cmdlet as follows:</span></span>
  
```powershell
Get-AzKeyVaultKey -VaultName <vault name>
```

<span data-ttu-id="ab5ee-335">고객 키는 만료된 키를 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="ab5ee-335">Customer Key can't use an expired key.</span></span> <span data-ttu-id="ab5ee-336">만료된 키로 작업을 시도하면 오류가 발생하여 서비스가 종료될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ab5ee-336">Operations attempted with an expired key will fail, and possibly result in a service outage.</span></span> <span data-ttu-id="ab5ee-337">고객 키와 함께 사용되는 키에는 만료 날짜가 없는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="ab5ee-337">We strongly recommend that keys used with Customer Key don't have an expiration date.</span></span> <span data-ttu-id="ab5ee-338">만료 날짜(설정된 경우)는 제거할 수 없지만 다른 날짜로 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ab5ee-338">An expiration date, once set, cannot be removed, but can be changed to a different date.</span></span> <span data-ttu-id="ab5ee-339">만료 날짜가 설정된 키를 사용하려면 만료 값을 12/31/9999로 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="ab5ee-339">If a key must be used that has an expiration date set, change the expiration value to 12/31/9999.</span></span> <span data-ttu-id="ab5ee-340">만료 날짜가 12/31/9999가 지난 날짜로 설정된 키는 유효성 검사를 Microsoft 365 않습니다.</span><span class="sxs-lookup"><span data-stu-id="ab5ee-340">Keys with an expiration date set to a date other than 12/31/9999 won't pass Microsoft 365 validation.</span></span>
  
<span data-ttu-id="ab5ee-341">12/31/9999가 아니라 다른 값으로 설정된 만료 날짜를 변경하기 위해 다음과 같이 [Update-AzKeyVaultKey](/powershell/module/az.keyvault/update-azkeyvaultkey) cmdlet을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="ab5ee-341">To change an expiration date that has been set to any value other than 12/31/9999, run the [Update-AzKeyVaultKey](/powershell/module/az.keyvault/update-azkeyvaultkey) cmdlet as follows:</span></span>
  
```powershell
Update-AzKeyVaultKey -VaultName <vault name> -Name <key name> -Expires (Get-Date -Date "12/31/9999")
```

> [!CAUTION]
> <span data-ttu-id="ab5ee-342">고객 키와 함께 사용하는 암호화 키에 만료 날짜를 설정하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="ab5ee-342">Don't set expiration dates on encryption keys you use with Customer Key.</span></span>
  
### <a name="obtain-the-uri-for-each-azure-key-vault-key"></a><span data-ttu-id="ab5ee-343">각 Azure Key Vault 키에 대한 URI 얻기</span><span class="sxs-lookup"><span data-stu-id="ab5ee-343">Obtain the URI for each Azure Key Vault key</span></span>

<span data-ttu-id="ab5ee-344">키 자격 증명 모음을 설정하고 키를 추가한 후 다음 명령을 실행하여 각 키 자격 증명 모음의 키에 대한 URI를 얻습니다.</span><span class="sxs-lookup"><span data-stu-id="ab5ee-344">Once you've set up your key vaults and added your keys, run the following command to get the URI for the key in each key vault.</span></span> <span data-ttu-id="ab5ee-345">나중에 각 DEP를 만들고 할당할 때 이러한 URIS를 사용하게 있으므로 이 정보를 안전한 장소에 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="ab5ee-345">You'll use these URIs when you create and assign each DEP later, so save this information in a safe place.</span></span> <span data-ttu-id="ab5ee-346">각 키 자격 증명 모음에 대해 이 명령을 한 번 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="ab5ee-346">Run this command once for each key vault.</span></span>
  
<span data-ttu-id="ab5ee-347">In Azure PowerShell:</span><span class="sxs-lookup"><span data-stu-id="ab5ee-347">In Azure PowerShell:</span></span>
  
```powershell
(Get-AzKeyVaultKey -VaultName <vault name>).Id
```

## <a name="next-steps"></a><span data-ttu-id="ab5ee-348">다음 단계</span><span class="sxs-lookup"><span data-stu-id="ab5ee-348">Next steps</span></span>

<span data-ttu-id="ab5ee-349">이 문서의 단계를 완료하면 DEP를 만들고 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ab5ee-349">Once you've completed the steps in this article, you're ready to create and assign DEPs.</span></span> <span data-ttu-id="ab5ee-350">자세한 내용은 고객 키 [관리를 참조하세요.](customer-key-manage.md)</span><span class="sxs-lookup"><span data-stu-id="ab5ee-350">For instructions, see [Manage Customer Key](customer-key-manage.md).</span></span>

## <a name="related-articles"></a><span data-ttu-id="ab5ee-351">관련 문서</span><span class="sxs-lookup"><span data-stu-id="ab5ee-351">Related articles</span></span>

- [<span data-ttu-id="ab5ee-352">고객 키를 사용한 서비스 암호화</span><span class="sxs-lookup"><span data-stu-id="ab5ee-352">Service encryption with Customer Key</span></span>](customer-key-overview.md)

- [<span data-ttu-id="ab5ee-353">고객 키 관리</span><span class="sxs-lookup"><span data-stu-id="ab5ee-353">Manage Customer Key</span></span>](customer-key-manage.md)

- [<span data-ttu-id="ab5ee-354">고객 키 또는 가용성 키 롤 또는 회전</span><span class="sxs-lookup"><span data-stu-id="ab5ee-354">Roll or rotate a Customer Key or an availability key</span></span>](customer-key-availability-key-roll.md)

- [<span data-ttu-id="ab5ee-355">가용성 키에 대해 자세히 알아보기</span><span class="sxs-lookup"><span data-stu-id="ab5ee-355">Learn about the availability key</span></span>](customer-key-availability-key-understand.md)

- [<span data-ttu-id="ab5ee-356">서비스 암호화</span><span class="sxs-lookup"><span data-stu-id="ab5ee-356">Service Encryption</span></span>](office-365-service-encryption.md)