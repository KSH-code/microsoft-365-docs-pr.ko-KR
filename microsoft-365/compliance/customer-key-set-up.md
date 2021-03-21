---
title: 응용 프로그램 수준에서 고객 키 설정
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 02/05/2020
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- M365-security-compliance
description: Exchange Online, 비즈니스용 Skype, SharePoint Online, 비즈니스용 OneDrive 및 Teams 파일용 Microsoft 365의 고객 키를 설정하는 방법을 학습합니다.
ms.openlocfilehash: a7a0c807b8778960d423d6b7d8afc20430ba89ad
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/19/2021
ms.locfileid: "50922722"
---
# <a name="set-up-customer-key-at-the-application-level"></a><span data-ttu-id="827eb-103">응용 프로그램 수준에서 고객 키 설정</span><span class="sxs-lookup"><span data-stu-id="827eb-103">Set up Customer Key at the application level</span></span>

<span data-ttu-id="827eb-104">고객 키를 사용하여 조직의 암호화 키를 제어한 다음 Microsoft 365를 구성하여 Microsoft 데이터 센터의 미사용 데이터를 암호화합니다.</span><span class="sxs-lookup"><span data-stu-id="827eb-104">With Customer Key, you control your organization's encryption keys and then configure Microsoft 365 to use them to encrypt your data at rest in Microsoft's data centers.</span></span> <span data-ttu-id="827eb-105">즉, 고객 키를 사용하면 고객이 키와 함께 고객에게 속한 암호화 계층을 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="827eb-105">In other words, Customer Key allows customers to add a layer of encryption that belongs to them, with their keys.</span></span> <span data-ttu-id="827eb-106">미사용 데이터에는 SharePoint Online 및 비즈니스용 OneDrive에 저장되어 있는 사서함과 파일에 저장된 Exchange Online 및 비즈니스용 Skype의 데이터를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="827eb-106">Data at rest includes data from Exchange Online and Skype for Business that is stored in mailboxes and files that are stored in SharePoint Online and OneDrive for Business.</span></span>

<span data-ttu-id="827eb-107">Office 365용 고객 키를 사용하려면 먼저 Azure를 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="827eb-107">You must set up Azure before you can use Customer Key for Office 365.</span></span> <span data-ttu-id="827eb-108">이 문서에서는 필요한 Azure 리소스를 만들고 구성하기 위해 따라야 하는 단계에 대해 설명한 다음 Office 365에서 고객 키를 설정하기 위한 단계를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="827eb-108">This article describes the steps you need to follow to create and configure the required Azure resources and then provides the steps for setting up Customer Key in Office 365.</span></span> <span data-ttu-id="827eb-109">Azure 설치를 완료한 후 조직의 사서함 및 파일에 할당할 정책 및 키를 결정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="827eb-109">After you have completed Azure setup, you determine which policy, and therefore, which keys, to assign to mailboxes and files in your organization.</span></span> <span data-ttu-id="827eb-110">정책을 할당하지 않는 사서함 및 파일은 Microsoft에서 제어 및 관리하는 암호화 정책을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="827eb-110">Mailboxes and files for which you don't assign a policy will use encryption policies that are controlled and managed by Microsoft.</span></span> <span data-ttu-id="827eb-111">고객 키에 대한 자세한 내용은 Office [365의 고객](customer-key-overview.md)키를 사용하여 서비스 암호화를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="827eb-111">For more information about Customer Key, or for a general overview, see [Service encryption with Customer Key in Office 365](customer-key-overview.md).</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="827eb-112">이 문서의 모범 사례를 따르는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="827eb-112">We strongly recommend that you follow the best practices in this article.</span></span> <span data-ttu-id="827eb-113">이러한 호출은 **TIP** 및 IMPORTANT 로 **호출합니다.**</span><span class="sxs-lookup"><span data-stu-id="827eb-113">These are called out as **TIP** and **IMPORTANT**.</span></span> <span data-ttu-id="827eb-114">고객 키는 전체 조직만큼 범위가 될 수 있는 루트 암호화 키를 제어할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="827eb-114">Customer Key gives you control over root encryption keys whose scope can be as large as your entire organization.</span></span> <span data-ttu-id="827eb-115">즉, 이러한 키로 실수하는 경우 광범위한 영향을 미칠 수 있으며 서비스가 중단되거나 데이터를 취소할 수 없는 손실이 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="827eb-115">This means that mistakes made with these keys can have a broad impact and may result in service interruptions or irrevocable loss of your data.</span></span>
  
## <a name="before-you-set-up-customer-key"></a><span data-ttu-id="827eb-116">고객 키를 설정하기 전에</span><span class="sxs-lookup"><span data-stu-id="827eb-116">Before you set up Customer Key</span></span>

<span data-ttu-id="827eb-117">시작하기 전에 조직에 적합한 라이선스가 있는지 확인해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="827eb-117">Before you get started, ensure that you have the appropriate licensing for your organization.</span></span> <span data-ttu-id="827eb-118">구독 또는 클라우드 서비스 공급자를 사용하여 유료로 기업계약 Azure 구독을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="827eb-118">Use a paid, invoiced Azure Subscription using either an Enterprise Agreement or a Cloud Service Provider.</span></span> <span data-ttu-id="827eb-119">Pay As You Go 요금제 또는 신용 카드를 사용하여 구입한 Azure 구독은 고객 키에 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="827eb-119">Azure Subscriptions purchased using Pay As You Go plans or using a credit card aren't supported for Customer Key.</span></span> <span data-ttu-id="827eb-120">2020년 4월 1일부터 Office 365의 고객 키는 Office 365 E5, M365 E5, M365 E5 규정 준수 및 M365 E5 Information Protection & SKUS에서 제공됩니다.</span><span class="sxs-lookup"><span data-stu-id="827eb-120">Starting April 1, 2020, Customer Key in Office 365 is offered in Office 365 E5, M365 E5, M365 E5 Compliance, and M365 E5 Information Protection & Governance SKUs.</span></span> <span data-ttu-id="827eb-121">Office 365 Advanced Compliance SKU는 더 이상 새 라이선스를 조달할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="827eb-121">Office 365 Advanced Compliance SKU is no longer available for procuring new licenses.</span></span> <span data-ttu-id="827eb-122">기존 Office 365 고급 준수 라이선스는 계속 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="827eb-122">Existing Office 365 Advanced Compliance licenses will continue to be supported.</span></span>

<span data-ttu-id="827eb-123">이 문서의 개념과 절차를 이해하기 위해 [Azure Key Vault 설명서를 검토하세요.](/azure/key-vault/)</span><span class="sxs-lookup"><span data-stu-id="827eb-123">To understand the concepts and procedures in this article, review the [Azure Key Vault](/azure/key-vault/) documentation.</span></span> <span data-ttu-id="827eb-124">또한 Azure에서 사용되는 용어(예: Azure [AD 테넌트)에 익숙해지기 하세요.](/previous-versions/azure/azure-services/jj573650(v=azure.100)#what-is-an-azure-ad-tenant)</span><span class="sxs-lookup"><span data-stu-id="827eb-124">Also, become familiar with the terms used in Azure, for example, [Azure AD tenant](/previous-versions/azure/azure-services/jj573650(v=azure.100)#what-is-an-azure-ad-tenant).</span></span>

<span data-ttu-id="827eb-125">FastTrack은 고객 키를 등록하는 데 사용되는 필수 테넌트 및 서비스 구성 정보를 수집하는 데만 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="827eb-125">FastTrack is only used to collect the required tenant and service configuration information used to register for Customer Key.</span></span> <span data-ttu-id="827eb-126">고객 주요 제품은 FastTrack을 통해 게시됩니다. 따라서 사용자와 파트너가 동일한 방법을 사용하여 필요한 정보를 제출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="827eb-126">The Customer Key Offers are published via FastTrack so that it is convenient for you and our partners to submit the required information using the same method.</span></span> <span data-ttu-id="827eb-127">FastTrack을 사용하면 제품에서 제공하는 데이터를 쉽게 보관할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="827eb-127">FastTrack also makes it easy to archive the data that you provide in the Offer.</span></span>
  
<span data-ttu-id="827eb-128">설명서 이외에 추가 지원이 필요한 경우 MCS(Microsoft Consulting Services), PFE(프리미어 필드 엔지니어링) 또는 Microsoft 파트너에게 지원을 요청하세요.</span><span class="sxs-lookup"><span data-stu-id="827eb-128">If you need more support beyond the documentation, contact Microsoft Consulting Services (MCS), Premier Field Engineering (PFE), or a Microsoft partner for assistance.</span></span> <span data-ttu-id="827eb-129">설명서를 포함하여 고객 키에 대한 의견을 제공하기 위해 사용자 의견, 제안 및 관점을 customerkeyfeedback@microsoft.com.</span><span class="sxs-lookup"><span data-stu-id="827eb-129">To provide feedback on Customer Key, including the documentation, send your ideas, suggestions, and perspectives to customerkeyfeedback@microsoft.com.</span></span>
  
## <a name="overview-of-steps-to-set-up-customer-key"></a><span data-ttu-id="827eb-130">고객 키 설정 단계 개요</span><span class="sxs-lookup"><span data-stu-id="827eb-130">Overview of steps to set up Customer Key</span></span>

<span data-ttu-id="827eb-131">고객 키를 설정하기 위해 나열된 순서대로 이러한 작업을 완료합니다.</span><span class="sxs-lookup"><span data-stu-id="827eb-131">To set up Customer Key, complete these tasks in the listed order.</span></span> <span data-ttu-id="827eb-132">이 문서의 나머지에서는 각 작업에 대한 자세한 지침을 제공하거나 프로세스의 각 단계에 대한 추가 정보로 연결됩니다.</span><span class="sxs-lookup"><span data-stu-id="827eb-132">The rest of this article provides detailed instructions for each task, or links out to more information for each step in the process.</span></span>
  
<span data-ttu-id="827eb-133">**Azure 및 Microsoft FastTrack에서:**</span><span class="sxs-lookup"><span data-stu-id="827eb-133">**In Azure and Microsoft FastTrack:**</span></span>
  
<span data-ttu-id="827eb-134">Azure PowerShell에 원격으로 연결하여 이러한 대부분의 작업을 완료합니다.</span><span class="sxs-lookup"><span data-stu-id="827eb-134">You will complete most of these tasks by remotely connecting to Azure PowerShell.</span></span> <span data-ttu-id="827eb-135">최상의 결과를 얻기 위해 Azure PowerShell 버전 4.4.0 이상을 사용하세요.</span><span class="sxs-lookup"><span data-stu-id="827eb-135">For best results, use version 4.4.0 or later of Azure PowerShell.</span></span>
  
- [<span data-ttu-id="827eb-136">두 개의 새 Azure 구독 만들기</span><span class="sxs-lookup"><span data-stu-id="827eb-136">Create two new Azure subscriptions</span></span>](#create-two-new-azure-subscriptions)

- [<span data-ttu-id="827eb-137">필수 보존 기간을 사용하기 위해 Azure 구독 등록</span><span class="sxs-lookup"><span data-stu-id="827eb-137">Register Azure subscriptions to use a mandatory retention period</span></span>](#register-azure-subscriptions-to-use-a-mandatory-retention-period)

  <span data-ttu-id="827eb-138">등록에는 영업일 1~5일이 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="827eb-138">Registration can take from one to five business days.</span></span>

- [<span data-ttu-id="827eb-139">Office 365에 대한 고객 키 정품 인증 요청 제출</span><span class="sxs-lookup"><span data-stu-id="827eb-139">Submit a request to activate Customer Key for Office 365</span></span>](#submit-a-request-to-activate-customer-key-for-office-365)

<span data-ttu-id="827eb-140">두 개의 새 Azure 구독을 만든 후 Microsoft FastTrack 포털에서 호스팅되는 웹 양식을 완료하여 적절한 고객 키 제품 요청을 제출해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="827eb-140">Once you've created the two new Azure subscriptions, you'll need to submit the appropriate Customer Key offer request by completing a web form that is hosted in the Microsoft FastTrack portal.</span></span> <span data-ttu-id="827eb-141">**FastTrack 팀은 고객 키에 대한 지원을 제공하지 않습니다. Office는 단순히 FastTrack** 포털을 사용하여 양식을 제출하고 고객 키에 대한 관련 제안을 추적하는 데 도움을 줄 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="827eb-141">**The FastTrack team doesn't provide assistance with Customer Key. Office simply uses the FastTrack portal to allow you to submit the form and to help us track the relevant offers for Customer Key**.</span></span>

- [<span data-ttu-id="827eb-142">각 구독에서 프리미엄 Azure Key Vault 만들기</span><span class="sxs-lookup"><span data-stu-id="827eb-142">Create a premium Azure Key Vault in each subscription</span></span>](#create-a-premium-azure-key-vault-in-each-subscription)

- [<span data-ttu-id="827eb-143">각 키 자격 증명 모음에 사용 권한 할당</span><span class="sxs-lookup"><span data-stu-id="827eb-143">Assign permissions to each key vault</span></span>](#assign-permissions-to-each-key-vault)

- [<span data-ttu-id="827eb-144">키 자격 증명 모음에서 소프트 삭제를 사용하도록 설정한 다음 확인</span><span class="sxs-lookup"><span data-stu-id="827eb-144">Enable and then confirm soft delete on your key vaults</span></span>](#enable-and-then-confirm-soft-delete-on-your-key-vaults)

- [<span data-ttu-id="827eb-145">키를 만들거나 가져와서 각 키 자격 증명 모음에 키 추가</span><span class="sxs-lookup"><span data-stu-id="827eb-145">Add a key to each key vault either by creating or importing a key</span></span>](#add-a-key-to-each-key-vault-either-by-creating-or-importing-a-key)

- [<span data-ttu-id="827eb-146">키의 복구 수준 확인</span><span class="sxs-lookup"><span data-stu-id="827eb-146">Check the recovery level of your keys</span></span>](#check-the-recovery-level-of-your-keys)

- [<span data-ttu-id="827eb-147">Azure Key Vault 백업</span><span class="sxs-lookup"><span data-stu-id="827eb-147">Back up Azure Key Vault</span></span>](#back-up-azure-key-vault)

- [<span data-ttu-id="827eb-148">Azure Key Vault 구성 설정 유효성 검사</span><span class="sxs-lookup"><span data-stu-id="827eb-148">Validate Azure Key Vault configuration settings</span></span>](#validate-azure-key-vault-configuration-settings)

- [<span data-ttu-id="827eb-149">각 Azure Key Vault 키에 대한 URI 얻기</span><span class="sxs-lookup"><span data-stu-id="827eb-149">Obtain the URI for each Azure Key Vault key</span></span>](#obtain-the-uri-for-each-azure-key-vault-key)

<span data-ttu-id="827eb-150">**Office 365에서:**</span><span class="sxs-lookup"><span data-stu-id="827eb-150">**In Office 365:**</span></span>
  
<span data-ttu-id="827eb-151">Exchange Online 및 비즈니스용 Skype:</span><span class="sxs-lookup"><span data-stu-id="827eb-151">Exchange Online and Skype for Business:</span></span>
  
- [<span data-ttu-id="827eb-152">Exchange Online 및 비즈니스용 Skype에서 사용할 DEP(데이터 암호화 정책) 만들기</span><span class="sxs-lookup"><span data-stu-id="827eb-152">Create a data encryption policy (DEP) for use with Exchange Online and Skype for Business</span></span>](#create-a-data-encryption-policy-dep-for-use-with-exchange-online-and-skype-for-business)

- [<span data-ttu-id="827eb-153">사서함에 DEP 할당</span><span class="sxs-lookup"><span data-stu-id="827eb-153">Assign a DEP to a mailbox</span></span>](#assign-a-dep-to-a-mailbox)

- [<span data-ttu-id="827eb-154">사서함 암호화 유효성 검사</span><span class="sxs-lookup"><span data-stu-id="827eb-154">Validate mailbox encryption</span></span>](#validate-mailbox-encryption)

<span data-ttu-id="827eb-155">SharePoint Online 및 비즈니스용 OneDrive:</span><span class="sxs-lookup"><span data-stu-id="827eb-155">SharePoint Online and OneDrive for Business:</span></span>
  
- [<span data-ttu-id="827eb-156">각 SharePoint Online 및 비즈니스용 OneDrive 지리적 데이터에 대한 DEP(데이터 암호화 정책) 만들기</span><span class="sxs-lookup"><span data-stu-id="827eb-156">Create a data encryption policy (DEP) for each SharePoint Online and OneDrive for Business geo</span></span>](#create-a-data-encryption-policy-dep-for-each-sharepoint-online-and-onedrive-for-business-geo)

- [<span data-ttu-id="827eb-157">SharePoint Online, 비즈니스용 OneDrive 및 Teams 파일에 대한 파일 암호화 유효성 검사</span><span class="sxs-lookup"><span data-stu-id="827eb-157">Validate file encryption for SharePoint Online, OneDrive for Business, and Teams files</span></span>](#validate-file-encryption)

## <a name="complete-tasks-in-azure-key-vault-and-microsoft-fasttrack-for-customer-key"></a><span data-ttu-id="827eb-158">Azure Key Vault 및 고객용 Microsoft FastTrack에서 작업 완료</span><span class="sxs-lookup"><span data-stu-id="827eb-158">Complete tasks in Azure Key Vault and Microsoft FastTrack for Customer Key</span></span>

<span data-ttu-id="827eb-159">Azure Key Vault에서 이러한 작업을 완료합니다.</span><span class="sxs-lookup"><span data-stu-id="827eb-159">Complete these tasks in Azure Key Vault.</span></span> <span data-ttu-id="827eb-160">Exchange Online 및 비즈니스용 Skype 또는 SharePoint Online, 비즈니스용 OneDrive 및 Teams 파일 또는 Office 365에서 지원되는 모든 서비스에 대해 고객 키를 설정하려는지 여부에 관계없이 이러한 단계를 완료해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="827eb-160">You'll need to complete these steps regardless of whether you intend to set up Customer Key for Exchange Online and Skype for Business or for SharePoint Online, OneDrive for Business, and Teams files, or for all supported services in Office 365.</span></span>
  
### <a name="create-two-new-azure-subscriptions"></a><span data-ttu-id="827eb-161">두 개의 새 Azure 구독 만들기</span><span class="sxs-lookup"><span data-stu-id="827eb-161">Create two new Azure subscriptions</span></span>

<span data-ttu-id="827eb-162">고객 키에는 두 개의 Azure 구독이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="827eb-162">Customer Key requires two Azure subscriptions.</span></span> <span data-ttu-id="827eb-163">모범 사례로 고객 키와 함께 사용할 새 Azure 구독을 만드는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="827eb-163">As a best practice, Microsoft recommends that you create new Azure subscriptions for use with Customer Key.</span></span> <span data-ttu-id="827eb-164">Azure Key Vault 키는 동일한 Azure Active Directory(Microsoft Azure Active Directory) 테넌트의 응용 프로그램에만 권한을 부여할 수 있으며, DEP가 할당될 조직에서 사용되는 동일한 Azure AD 테넌트를 사용하여 새 구독을 만들어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="827eb-164">Azure Key Vault keys can only be authorized for applications in the same Azure Active Directory (Microsoft Azure Active Directory) tenant, you must create the new subscriptions using the same Azure AD tenant used with your organization where the DEPs will be assigned.</span></span> <span data-ttu-id="827eb-165">예를 들어 조직에서 전역 관리자 권한이 있는 직장 또는 학교 계정을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="827eb-165">For example, using your work or school account that has global administrator privileges in your organization.</span></span> <span data-ttu-id="827eb-166">자세한 단계는 [조직으로 Azure에 등록을 참조하세요.](/azure/active-directory/fundamentals/sign-up-organization)</span><span class="sxs-lookup"><span data-stu-id="827eb-166">For detailed steps, see [Sign up for Azure as an organization](/azure/active-directory/fundamentals/sign-up-organization).</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="827eb-167">고객 키에는 각 DEP(데이터 암호화 정책)에 대해 두 개의 키가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="827eb-167">Customer Key requires two keys for each data encryption policy (DEP).</span></span> <span data-ttu-id="827eb-168">이를 위해 Azure 구독을 두 개 만들어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="827eb-168">In order to achieve this, you must create two Azure subscriptions.</span></span> <span data-ttu-id="827eb-169">조직의 개별 구성원이 각 구독에서 하나의 키를 구성하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="827eb-169">As a best practice, Microsoft recommends that you have separate members of your organization configure one key in each subscription.</span></span> <span data-ttu-id="827eb-170">이러한 Azure 구독을 사용하여 Office 365의 암호화 키를 관리해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="827eb-170">You should only use these Azure subscriptions to administer encryption keys for Office 365.</span></span> <span data-ttu-id="827eb-171">이렇게 하여 운영자 중 한 명을 실수로, 의도적으로 또는 악의적으로 삭제하거나 책임이 있는 키를 잘못 관리한 경우 조직을 보호할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="827eb-171">This protects your organization in case one of your operators accidentally, intentionally, or maliciously deletes or otherwise mismanages the keys for which they are responsible.</span></span>
>

<span data-ttu-id="827eb-172">조직에 대해 만들 수 있는 Azure 구독 수에는 실질적인 제한이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="827eb-172">There is no practical limit to the number of Azure subscriptions that you can create for your organization.</span></span> <span data-ttu-id="827eb-173">이러한 모범 사례를 따라 사용자 오류의 영향을 최소화하면서 고객 키에서 사용하는 리소스를 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="827eb-173">Following these best practices will minimize the impact of human error while helping to manage the resources used by Customer Key.</span></span>
  
### <a name="submit-a-request-to-activate-customer-key-for-office-365"></a><span data-ttu-id="827eb-174">Office 365에 대한 고객 키 정품 인증 요청 제출</span><span class="sxs-lookup"><span data-stu-id="827eb-174">Submit a request to activate Customer Key for Office 365</span></span>

<span data-ttu-id="827eb-175">Azure 단계를 완료한 후 Microsoft FastTrack 포털에서 제안 요청을 [제출해야 합니다.](https://fasttrack.microsoft.com/)</span><span class="sxs-lookup"><span data-stu-id="827eb-175">Once you've completed the Azure steps, you'll need to submit an offer request in the [Microsoft FastTrack portal](https://fasttrack.microsoft.com/).</span></span> <span data-ttu-id="827eb-176">FastTrack 웹 포털을 통해 요청을 제출하면 Microsoft는 Azure Key Vault 구성 데이터 및 제공한 연락처 정보를 검증합니다.</span><span class="sxs-lookup"><span data-stu-id="827eb-176">Once you've submitted a request through the FastTrack web portal, Microsoft verifies the Azure Key Vault configuration data and contact information you provided.</span></span> <span data-ttu-id="827eb-177">조직의 공인 담당자에 대한 제안 양식에서 선택한 것은 고객 키 등록을 완료하는 데 중요하고 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="827eb-177">The selections that you make in the offer form about the authorized officers of your organization is critical and necessary for completion of Customer Key registration.</span></span> <span data-ttu-id="827eb-178">조직의 담당자는 고객 키 데이터 암호화 정책에 사용되는 모든 키를 해지하고 삭제하기 위한 모든 요청의 인증을 보장합니다.</span><span class="sxs-lookup"><span data-stu-id="827eb-178">The officers of your organization ensure the authenticity of any request to revoke and destroy all keys used with a Customer Key data encryption policy.</span></span> <span data-ttu-id="827eb-179">Exchange Online 및 비즈니스용 Skype에 대한 고객 키를 활성화하려면 이 단계를 한 번, 두 번째로 SharePoint Online 및 비즈니스용 OneDrive에 대한 고객 키를 활성화해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="827eb-179">You'll need to do this step once to activate Customer Key for Exchange Online and Skype for Business coverage and a second time to activate Customer Key for SharePoint Online and OneDrive for Business.</span></span>
  
<span data-ttu-id="827eb-180">고객 키를 활성화하기 위한 제안을 제출하려면 다음 단계를 완료합니다.</span><span class="sxs-lookup"><span data-stu-id="827eb-180">To submit an offer to activate Customer Key, complete these steps:</span></span>
  
1. <span data-ttu-id="827eb-181">조직에서 전역 관리자 권한이 있는 직장 또는 학교 계정을 사용하여 [Microsoft FastTrack](https://fasttrack.microsoft.com/)포털에 로그인합니다.</span><span class="sxs-lookup"><span data-stu-id="827eb-181">Using a work or school account that has global administrator permissions in your organization, sign in to the [Microsoft FastTrack portal](https://fasttrack.microsoft.com/).</span></span>

2. <span data-ttu-id="827eb-182">로그인한 후 대시보드 를 **검색합니다.**</span><span class="sxs-lookup"><span data-stu-id="827eb-182">Once you're logged in, browse to the **Dashboard**.</span></span>

3. <span data-ttu-id="827eb-183">탐색 **모음에서** 배포를  **선택하거나** 배포 정보  카드에서 모든 배포 리소스 보기를 선택하고 현재 혜택 목록을 검토합니다.</span><span class="sxs-lookup"><span data-stu-id="827eb-183">Choose **Deploy** from the navigation bar **OR** select **View all deployment resources** on the **Deploy** information card, and review the list of current offers.</span></span>

4. <span data-ttu-id="827eb-184">적용되는 제품 정보 카드를 선택하세요.</span><span class="sxs-lookup"><span data-stu-id="827eb-184">Choose the information card for the offer that applies to you:</span></span>

   - <span data-ttu-id="827eb-185">**Exchange Online 및 비즈니스용 Skype:** Exchange **Online 제품용 암호화 키 요청 도움말을** 선택하세요.</span><span class="sxs-lookup"><span data-stu-id="827eb-185">**Exchange Online and Skype for Business:** Choose the **Request encryption key help for Exchange online** offer.</span></span>

   - <span data-ttu-id="827eb-186">**SharePoint Online, OneDrive 및 Teams 파일:** **Sharepoint 및 OneDrive 제안에** 대한 암호화 키 요청 도움말을 선택하세요.</span><span class="sxs-lookup"><span data-stu-id="827eb-186">**SharePoint Online, OneDrive, and Teams files:** Choose the **Request encryption key help for Sharepoint and OneDrive** offer.</span></span>

5. <span data-ttu-id="827eb-187">제품 세부 정보를 검토한 후 **2단계로 계속을 선택 합니다.**</span><span class="sxs-lookup"><span data-stu-id="827eb-187">Once you've reviewed the offer details, choose **Continue to step 2**.</span></span>

6. <span data-ttu-id="827eb-188">제품 양식에 적용 가능한 모든 세부 정보와 요청된 정보를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="827eb-188">Fill out all applicable details and requested information on the offer form.</span></span> <span data-ttu-id="827eb-189">조직의 임원이 암호화 키와 데이터의 영구적이자 비버버스할 수 없는 폐기 권한을 승인할 선택에 특히 주의해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="827eb-189">Pay particular attention to your selections for which officers of your organization you want to authorize to approve the permanent and irreversible destruction of encryption keys and data.</span></span> <span data-ttu-id="827eb-190">양식을 완료한 후 제출 을 **선택하세요.**</span><span class="sxs-lookup"><span data-stu-id="827eb-190">Once you've completed the form, choose **Submit**.</span></span>

### <a name="register-azure-subscriptions-to-use-a-mandatory-retention-period"></a><span data-ttu-id="827eb-191">필수 보존 기간을 사용하기 위해 Azure 구독 등록</span><span class="sxs-lookup"><span data-stu-id="827eb-191">Register Azure subscriptions to use a mandatory retention period</span></span>

<span data-ttu-id="827eb-192">루트 암호화 키의 일시적 또는 영구적 손실은 서비스 작업에 지장이나 심지어는 비극적일 수 있으며 데이터가 손실될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="827eb-192">The temporary or permanent loss of root encryption keys can be disruptive or even catastrophic to service operation and can result in data loss.</span></span> <span data-ttu-id="827eb-193">이러한 이유로 고객 키와 함께 사용되는 리소스에는 강력한 보호가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="827eb-193">For this reason, the resources used with Customer Key require strong protection.</span></span> <span data-ttu-id="827eb-194">고객 키와 함께 사용되는 모든 Azure 리소스는 기본 구성을 넘어 보호 메커니즘을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="827eb-194">All the Azure resources that are used with Customer Key offer protection mechanisms beyond the default configuration.</span></span> <span data-ttu-id="827eb-195">필수 보존 기간 동안 Azure 구독에 태그를 지정하거나 *등록할 수 있습니다.*</span><span class="sxs-lookup"><span data-stu-id="827eb-195">You can tag or register Azure subscriptions for a *mandatory retention period*.</span></span> <span data-ttu-id="827eb-196">필수 보존 기간은 Azure 구독의 즉시 취소할 수 없는 취소를 방지합니다.</span><span class="sxs-lookup"><span data-stu-id="827eb-196">A mandatory retention period prevents immediate and irrevocable cancellation of your Azure subscription.</span></span> <span data-ttu-id="827eb-197">필수 보존 기간 동안 Azure 구독을 등록하는 데 필요한 단계는 Microsoft 365 팀과 공동 작업해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="827eb-197">The steps required to register Azure subscriptions for a mandatory retention period require collaboration with the Microsoft 365 team.</span></span> <span data-ttu-id="827eb-198">이 프로세스는 영업일로부터 5일까지 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="827eb-198">This process can take from one to five business days.</span></span> <span data-ttu-id="827eb-199">이전에는 필수 보존 기간을 "취소 금지"라고도 합니다.</span><span class="sxs-lookup"><span data-stu-id="827eb-199">Previously, mandatory retention period was sometimes referred to as "Do Not Cancel".</span></span>
  
<span data-ttu-id="827eb-200">Microsoft 365 팀에 문의하기 전에 고객 키와 함께 사용하는 각 Azure 구독에 대해 다음 단계를 수행해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="827eb-200">Before contacting the Microsoft 365 team, you must do the following steps for each Azure subscription that you use with Customer Key.</span></span> <span data-ttu-id="827eb-201">시작하기 전에 [Azure PowerShell Az](/powershell/azure/new-azureps-module-az) 모듈을 설치해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="827eb-201">Ensure that you have the [Azure PowerShell Az](/powershell/azure/new-azureps-module-az) module installed before you start.</span></span>
  
1. <span data-ttu-id="827eb-202">Azure PowerShell을 사용하여 로그인합니다.</span><span class="sxs-lookup"><span data-stu-id="827eb-202">Sign in with Azure PowerShell.</span></span> <span data-ttu-id="827eb-203">자세한 내용은 [Azure PowerShell로 로그인을 참조하세요.](/powershell/azure/authenticate-azureps)</span><span class="sxs-lookup"><span data-stu-id="827eb-203">For instructions, see [Sign in with Azure PowerShell](/powershell/azure/authenticate-azureps).</span></span>

2. <span data-ttu-id="827eb-204">Register-AzProviderFeature cmdlet을 실행하여 필수 보존 기간을 사용하기 위해 구독을 등록합니다.</span><span class="sxs-lookup"><span data-stu-id="827eb-204">Run the Register-AzProviderFeature cmdlet to register your subscriptions to use a mandatory retention period.</span></span> <span data-ttu-id="827eb-205">각 구독에 대해 이 작업을 완료합니다.</span><span class="sxs-lookup"><span data-stu-id="827eb-205">Complete this action for each subscription.</span></span>

   ```powershell
   Set-AzContext -SubscriptionId <SubscriptionId>
   Register-AzProviderFeature -FeatureName mandatoryRetentionPeriodEnabled -ProviderNamespace Microsoft.Resources
   ```

3. <span data-ttu-id="827eb-206">프로세스를 완료하기 위해 Microsoft에 문의합니다.</span><span class="sxs-lookup"><span data-stu-id="827eb-206">Contact Microsoft to complete the process.</span></span> <span data-ttu-id="827eb-207">SharePoint 및 비즈니스용 OneDrive 팀의 경우 에 [spock@microsoft.com.](mailto:spock@microsoft.com)</span><span class="sxs-lookup"><span data-stu-id="827eb-207">For the SharePoint and OneDrive for Business team, contact [spock@microsoft.com](mailto:spock@microsoft.com).</span></span> <span data-ttu-id="827eb-208">Exchange Online 및 비즈니스용 Skype의 경우 [에](mailto:exock@microsoft.com)exock@microsoft.com.</span><span class="sxs-lookup"><span data-stu-id="827eb-208">For Exchange Online and Skype for Business, contact [exock@microsoft.com](mailto:exock@microsoft.com).</span></span> <span data-ttu-id="827eb-209">전자 메일에 다음 정보를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="827eb-209">Include the following information in your email:</span></span>

   <span data-ttu-id="827eb-210">**제목:** 고객 키 \<*Your tenant's fully qualified domain name*\></span><span class="sxs-lookup"><span data-stu-id="827eb-210">**Subject**: Customer Key for \<*Your tenant's fully qualified domain name*\></span></span>

   <span data-ttu-id="827eb-211">**본문:** 필수 보존 기간을 완료할 구독 Get-AzProviderFeature 각 구독에 대한 결과값을 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="827eb-211">**Body**: Include the subscription IDs for which you want to complete the mandatory retention period  and the output of Get-AzProviderFeature for each subscription.</span></span>

   <span data-ttu-id="827eb-212">이 프로세스 완료를 위한 SLA(서비스 수준 계약)는 Microsoft에 필수 보존 기간을 사용하기 위해 구독을 등록했다는 알림을(확인)한 후 영업일 5일입니다.</span><span class="sxs-lookup"><span data-stu-id="827eb-212">The Service Level Agreement (SLA) for completion of this process is five business days once Microsoft has been notified (and verified) that you have registered your subscriptions to use a mandatory retention period.</span></span>

4. <span data-ttu-id="827eb-213">Microsoft로부터 등록이 완료되었습니다는 알림을 받으면 다음과 같이 Get-AzProviderFeature 등록 상태를 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="827eb-213">Once you receive notification from Microsoft that registration is complete, verify the status of your registration by running the Get-AzProviderFeature command as follows.</span></span> <span data-ttu-id="827eb-214">확인되면 Get-AzProviderFeature 명령은 Registration State 속성에 **대해 Registered** 값을 **반환합니다.**</span><span class="sxs-lookup"><span data-stu-id="827eb-214">If verified, the Get-AzProviderFeature command returns a value of **Registered** for the **Registration State** property.</span></span> <span data-ttu-id="827eb-215">각 구독에 대해 이 단계를 완료합니다.</span><span class="sxs-lookup"><span data-stu-id="827eb-215">Complete this step for each subscription.</span></span>

   ```powershell
   Set-AzContext -SubscriptionId <SubscriptionId>
   Get-AzProviderFeature -ProviderNamespace Microsoft.Resources -FeatureName mandatoryRetentionPeriodEnabled
   ```

5. <span data-ttu-id="827eb-216">프로세스를 완료하기 위해 Register-AzResourceProvider 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="827eb-216">To complete the process, run the Register-AzResourceProvider command.</span></span> <span data-ttu-id="827eb-217">각 구독에 대해 이 단계를 완료합니다.</span><span class="sxs-lookup"><span data-stu-id="827eb-217">Complete this step for each subscription.</span></span>

   ```powershell
   Set-AzContext -SubscriptionId <SubscriptionId>
   Register-AzResourceProvider -ProviderNamespace Microsoft.KeyVault
   ```

### <a name="create-a-premium-azure-key-vault-in-each-subscription"></a><span data-ttu-id="827eb-218">각 구독에서 프리미엄 Azure Key Vault 만들기</span><span class="sxs-lookup"><span data-stu-id="827eb-218">Create a premium Azure Key Vault in each subscription</span></span>

<span data-ttu-id="827eb-219">키 저장소를 만드는 단계는 Azure PowerShell 설치 및 시작, Azure 구독에 연결, 리소스 그룹 만들기 및 해당 리소스 그룹에 키 자격 증명 모음 만들기를 안내하는 [Azure Key Vault](/azure/key-vault/general/overview)시작에 설명되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="827eb-219">The steps to create a key vault are documented in [Getting Started with Azure Key Vault](/azure/key-vault/general/overview), which guides you through installing and launching Azure PowerShell, connecting to your Azure subscription, creating a resource group, and creating a key vault in that resource group.</span></span>
  
<span data-ttu-id="827eb-220">키 자격 증명 모음을 만들 때 SKU(Standard 또는 Premium)를 선택해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="827eb-220">When you create a key vault, you must choose a SKU: either Standard or Premium.</span></span> <span data-ttu-id="827eb-221">Standard SKU를 사용하면 Azure Key Vault 키를 소프트웨어로 보호할 수 있으며, HSM(하드웨어 보안 모듈) 키 보호가 없습니다. Premium SKU는 키 자격 증명 모음 키를 보호하기 위해 HSM을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="827eb-221">The Standard SKU allows Azure Key Vault keys to be protected with software - there's no Hardware Security Module (HSM) key protection - and the Premium SKU allows the use of HSMs for protection of Key Vault keys.</span></span> <span data-ttu-id="827eb-222">Customer Key는 두 SKU 중 하나를 사용하는 주요 자격 증명 모음을 허용합니다. 그러나 Microsoft는 Premium SKU만 사용하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="827eb-222">Customer Key accepts key vaults that use either SKU, though Microsoft strongly recommends that you use only the Premium SKU.</span></span> <span data-ttu-id="827eb-223">두 형식의 키 중 하나를 사용하는 작업의 비용은 동일하기 때문에 비용의 유일한 차이점은 각 HSM으로 보호되는 키에 대한 월별 비용입니다.</span><span class="sxs-lookup"><span data-stu-id="827eb-223">The cost of operations with keys of either type is the same, so the only difference in cost is the cost per month for each HSM-protected key.</span></span> <span data-ttu-id="827eb-224">자세한 [내용은 Key Vault 가격을](https://azure.microsoft.com/pricing/details/key-vault/) 참조합니다.</span><span class="sxs-lookup"><span data-stu-id="827eb-224">See [Key Vault pricing](https://azure.microsoft.com/pricing/details/key-vault/) for details.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="827eb-225">프로덕션 데이터에는 Premium SKU 키 자격 증명 모음 및 HSM으로 보호된 키를 사용하며 테스트 및 유효성 검사를 위해 표준 SKU 키 자격 증명 모음 및 키만 사용하십시오.</span><span class="sxs-lookup"><span data-stu-id="827eb-225">Use the Premium SKU key vaults and HSM-protected keys for production data, and only use Standard SKU key vaults and keys for testing and validation purposes.</span></span>
  
<span data-ttu-id="827eb-226">고객 키를 사용할 각 Microsoft 365 서비스에 대해 만든 두 Azure 구독 각각에 키 자격 증명 모음을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="827eb-226">For each Microsoft 365 service with which you will use Customer Key, create a key vault in each of the two Azure subscriptions that you created.</span></span> <span data-ttu-id="827eb-227">예를 들어 Exchange Online 및 비즈니스용 Skype 전용 또는 SharePoint Online 및 비즈니스용 OneDrive의 경우 한 쌍의 자격 증명 모음만 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="827eb-227">For example, for Exchange Online and Skype for Business only or SharePoint Online and OneDrive for Business only, you'll create only one pair of vaults.</span></span> <span data-ttu-id="827eb-228">Exchange Online 및 SharePoint Online 둘 다에 대해 고객 키를 사용하도록 설정하려면 두 쌍의 키 자격 증명 모음을 만들어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="827eb-228">To enable Customer Key for both Exchange Online and SharePoint Online, you will create two pairs of key vaults.</span></span>
  
<span data-ttu-id="827eb-229">자격 증명 모음을 연결하려는 DEP의 의도된 사용을 반영하는 주요 자격 증명 모음에 대한 이름 규칙 사용</span><span class="sxs-lookup"><span data-stu-id="827eb-229">Use a naming convention for key vaults that reflects the intended use of the DEP with which you will associate the vaults.</span></span> <span data-ttu-id="827eb-230">이름 규칙 권장 사항은 아래의 모범 사례 섹션을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="827eb-230">See the Best Practices section below for naming convention recommendations.</span></span>
  
<span data-ttu-id="827eb-231">각 데이터 암호화 정책에 대해 페어링된 별도의 자격 증명 모음 집합을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="827eb-231">Create a separate, paired set of vaults for each data encryption policy.</span></span> <span data-ttu-id="827eb-232">Exchange Online의 경우 사서함에 정책을 할당할 때 데이터 암호화 정책의 범위가 선택됩니다.</span><span class="sxs-lookup"><span data-stu-id="827eb-232">For Exchange Online, the scope of a data encryption policy is chosen by you when you assign the policy to mailbox.</span></span> <span data-ttu-id="827eb-233">사서함에는 정책이 하나만 할당될 수 있으며 최대 50개 정책을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="827eb-233">A mailbox can have only one policy assigned, and you can create up to 50 policies.</span></span> <span data-ttu-id="827eb-234">SharePoint Online 정책의 범위에는 지리적 위치 또는 지리적 위치에 있는 조직 내의 모든 데이터가 _포함됩니다._</span><span class="sxs-lookup"><span data-stu-id="827eb-234">The scope of a SharePoint Online policy includes all of the data within an organization in a geographic location, or _geo_.</span></span>

<span data-ttu-id="827eb-235">키 자격 증명 모음을 만들려면 Azure 리소스 그룹도 만들어야 합니다. 키 자격 증명 모음에는 저장 용량(작은 용량)이 필요하고 키 자격 증명 모음 로깅을 사용하도록 설정하면 저장된 데이터도 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="827eb-235">The creation of key vaults also requires the creation of Azure resource groups, since key vaults need storage capacity (though small) and Key Vault logging, if enabled, also generates stored data.</span></span> <span data-ttu-id="827eb-236">모범 사례로 Microsoft는 별도의 관리자를 사용하여 각 리소스 그룹을 관리하고 모든 관련 고객 키 리소스를 관리할 관리자 집합에 맞게 관리하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="827eb-236">As a best practice Microsoft recommends using separate administrators to manage each resource group, with the administration that's aligned with the set of administrators that will manage all related Customer Key resources.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="827eb-237">가용성을 최대화하기 위해 주요 자격 증명 모음은 Microsoft 365 서비스와 가까운 지역에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="827eb-237">To maximize availability, your key vaults should be in regions close to your Microsoft 365 service.</span></span> <span data-ttu-id="827eb-238">예를 들어 Exchange Online 조직이 북미에 있는 경우 주요 자격 증명 모음을 북미에 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="827eb-238">For example, if your Exchange Online organization is in North America, place your key vaults in North America.</span></span> <span data-ttu-id="827eb-239">Exchange Online 조직이 유럽에 있는 경우 주요 자격 증명 모음을 유럽에 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="827eb-239">If your Exchange Online organization is in Europe, place your key vaults in Europe.</span></span>
> 
> <span data-ttu-id="827eb-240">키 자격 증명 모음에 대해 공통적인 prefix를 사용하며 키 자격 증명 모음 및 키의 사용 및 범위에 대한 약어를 포함합니다(예: 자격 증명 모음이 북미에 있는 Contoso SharePoint 서비스의 경우, 가능한 이름 쌍은 Contoso-O365SP-NA-VaultA1 및 Contoso-O365SP-NA-VaultA2)입니다.</span><span class="sxs-lookup"><span data-stu-id="827eb-240">Use a common prefix for key vaults, and include an abbreviation of the use and scope of the key vault and keys (e.g., for the Contoso SharePoint service where the vaults will be located in North America, a possible pair of names is Contoso-O365SP-NA-VaultA1 and Contoso-O365SP-NA-VaultA2.</span></span> <span data-ttu-id="827eb-241">자격 증명 모음 이름은 Azure 내에서 전역적으로 고유한 문자열이기 때문에 다른 Azure 고객이 원하는 이름을 이미 클레임할 경우 원하는 이름을 변형해 보아야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="827eb-241">Vault names are globally unique strings within Azure, so you may need to try variations of your desired names in case the desired names are already claimed by other Azure customers.</span></span> <span data-ttu-id="827eb-242">2017년 7월 현재 자격 증명 모음 이름은 변경할 수 없습니다. 따라서 설치를 위한 서면 계획을 세우고 두 번째 사람을 사용하여 계획이 올바르게 실행되고 있는지 확인하는 것이 가장 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="827eb-242">As of July 2017 vault names cannot be changed, so a best practice is to have a written plan for setup and use a second person to verify the plan is executed correctly.</span></span>
> 
> <span data-ttu-id="827eb-243">가능한 경우 페어링되지 않은 지역에서 자격 증명 모음을 만드십시오.</span><span class="sxs-lookup"><span data-stu-id="827eb-243">If possible, create your vaults in non-paired regions.</span></span> <span data-ttu-id="827eb-244">페어링된 Azure 지역은 서비스 오류 도메인 전체에서 고가용성을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="827eb-244">Paired Azure regions provide high availability across service failure domains.</span></span> <span data-ttu-id="827eb-245">따라서 지역 쌍은 서로의 백업 지역으로 생각할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="827eb-245">Therefore, regional pairs can be thought of as each other's backup region.</span></span> <span data-ttu-id="827eb-246">즉, 한 지역에 배치된 Azure 리소스가 페어링된 지역을 통해 내결결성을 자동으로 얻게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="827eb-246">This means that an Azure resource that is placed in one region is automatically gaining fault tolerance through the paired region.</span></span> <span data-ttu-id="827eb-247">이러한 이유로 지역이 쌍을 이루는 데이터 암호화 정책에서 사용되는 두 자격 증명 모음에 대한 지역을 선택하면 총 2개의 가용성 영역만 사용 중입니다.</span><span class="sxs-lookup"><span data-stu-id="827eb-247">For this reason, choosing regions for two vaults used in a data encryption policy where the regions are paired means that only a total of two regions of availability are in use.</span></span> <span data-ttu-id="827eb-248">대부분의 지역에는 두 개의 지역만 있으므로 페어링되지 않은 지역을 선택할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="827eb-248">Most geographies only have two regions, so it's not yet possible to select non-paired regions.</span></span> <span data-ttu-id="827eb-249">가능한 경우 데이터 암호화 정책과 함께 사용되는 두 자격 증명 모음에 대해 쌍으로 설정되지 않은 두 지역을 선택하세요.</span><span class="sxs-lookup"><span data-stu-id="827eb-249">If possible, choose two non-paired regions for the two vaults used with a data encryption policy.</span></span> <span data-ttu-id="827eb-250">이 혜택은 총 4개의 가용성 영역의 이점입니다.</span><span class="sxs-lookup"><span data-stu-id="827eb-250">This benefits from a total of four regions of availability.</span></span> <span data-ttu-id="827eb-251">자세한 내용은 비즈니스 연속성 및 재해 [복구(BCDR): 현재](/azure/best-practices-availability-paired-regions) 지역 쌍 목록은 Azure 페어링 지역을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="827eb-251">For more information, see [Business continuity and disaster recovery (BCDR): Azure Paired Regions](/azure/best-practices-availability-paired-regions) for a current list of regional pairs.</span></span>
  
### <a name="assign-permissions-to-each-key-vault"></a><span data-ttu-id="827eb-252">각 키 자격 증명 모음에 사용 권한 할당</span><span class="sxs-lookup"><span data-stu-id="827eb-252">Assign permissions to each key vault</span></span>

<span data-ttu-id="827eb-253">구현에 따라 각 키 자격 증명 모음에 대해 세 가지 개별 권한 집합을 정의해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="827eb-253">You'll need to define three separate sets of permissions for each key vault, depending on your implementation.</span></span> <span data-ttu-id="827eb-254">예를 들어 다음 각 권한 집합에 대해 하나의 사용 권한 집합을 정의해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="827eb-254">For example, you will need to define one set of permissions for each of the following:</span></span>
  
- <span data-ttu-id="827eb-255">**조직의 키** 자격 증명 모음을 매일 관리하기 위한 주요 자격 증명 모음 관리자</span><span class="sxs-lookup"><span data-stu-id="827eb-255">**Key vault administrators** that do day-to-day management of your key vault for your organization.</span></span> <span data-ttu-id="827eb-256">이러한 작업에는 백업, 만들기, 가져오기, 가져오기, 목록 및 복원이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="827eb-256">These tasks include backup, create, get, import, list, and restore.</span></span>

  > [!IMPORTANT]
  > <span data-ttu-id="827eb-257">키 자격 증명 모음 관리자에게 할당된 권한 집합에는 키를 삭제할 수 있는 권한이 포함되어 있지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="827eb-257">The set of permissions assigned to key vault administrators does not include the permission to delete keys.</span></span> <span data-ttu-id="827eb-258">이는 의도적인 것이고 중요한 사례입니다.</span><span class="sxs-lookup"><span data-stu-id="827eb-258">This is intentional and an important practice.</span></span> <span data-ttu-id="827eb-259">암호화 키를 삭제하면 데이터가 영구적으로 삭제되는 것이 일반적이지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="827eb-259">Deleting encryption keys is not typically done, since doing so permanently destroys data.</span></span> <span data-ttu-id="827eb-260">이 권한은 기본적으로 주요 자격 증명 모음 관리자에게 부여하지 않는 것이 가장 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="827eb-260">As a best practice, do not grant this permission to key vault administrators by default.</span></span> <span data-ttu-id="827eb-261">대신 주요 자격 증명 모음 참가자에 대해 이 정보를 예약하고 결과에 대한 명확한 이해가 있는 경우 단기적으로 관리자에게 할당해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="827eb-261">Instead, reserve this for key vault contributors and only assign it to an administrator on a short term basis once a clear understanding of the consequences is understood.</span></span>
  
  <span data-ttu-id="827eb-262">조직의 사용자에게 이러한 권한을 할당하려면 Azure PowerShell을 사용하여 Azure 구독에 로그인합니다.</span><span class="sxs-lookup"><span data-stu-id="827eb-262">To assign these permissions to a user in your organization, sign in to your Azure subscription with Azure PowerShell.</span></span> <span data-ttu-id="827eb-263">자세한 내용은 [Azure PowerShell로 로그인을 참조하세요.](/powershell/azure/authenticate-azureps)</span><span class="sxs-lookup"><span data-stu-id="827eb-263">For instructions, see [Sign in with Azure PowerShell](/powershell/azure/authenticate-azureps).</span></span>

- <span data-ttu-id="827eb-264">Set-AzKeyVaultAccessPolicy cmdlet을 실행하여 필요한 사용 권한을 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="827eb-264">Run the Set-AzKeyVaultAccessPolicy cmdlet to assign the necessary permissions.</span></span>

   ```powershell
   Set-AzKeyVaultAccessPolicy -VaultName <vault name> -UserPrincipalName <UPN of user> -PermissionsToKeys create,import,list,get,backup,restore
   ```

   <span data-ttu-id="827eb-265">예를 들어 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="827eb-265">For example:</span></span>

   ```powershell
   Set-AzKeyVaultAccessPolicy -VaultName Contoso-O365EX-NA-VaultA1 -UserPrincipalName alice@contoso.com -PermissionsToKeys create,import,list,get,backup,restore
   ```

- <span data-ttu-id="827eb-266">Azure **Key Vault** 자체에 대한 사용 권한을 변경할 수 있는 주요 자격 증명 모음 참가자입니다.</span><span class="sxs-lookup"><span data-stu-id="827eb-266">**Key vault contributors** that can change permissions on the Azure Key Vault itself.</span></span> <span data-ttu-id="827eb-267">직원이 팀을 떠나거나 팀에 합류할 때 이러한 권한을 변경해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="827eb-267">You'll need to change these permissions as employees leave or join your team.</span></span> <span data-ttu-id="827eb-268">키 자격 증명 모음 관리자가 키를 삭제하거나 복원할 수 있는 권한이 합법적으로 필요한 드물지만 사용 권한도 변경해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="827eb-268">In the rare situation that the key vault administrators legitimately need permission to delete or restore a key you'll also need to change the permissions.</span></span> <span data-ttu-id="827eb-269">이 주요 자격 증명 모음 참가자 집합에는 키 자격 증명 모음에 대한 **참가자** 역할을 부여해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="827eb-269">This set of key vault contributors needs to be granted the **Contributor** role on your key vault.</span></span> <span data-ttu-id="827eb-270">Azure Resource Manager를 사용하여 이 역할을 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="827eb-270">You can assign this role by using Azure Resource Manager.</span></span> <span data-ttu-id="827eb-271">자세한 단계는 Role-Based 액세스 제어를 사용하여 Azure 구독 리소스에 대한 액세스 [관리를 참조하세요.](/azure/active-directory/role-based-access-control-configure)</span><span class="sxs-lookup"><span data-stu-id="827eb-271">For detailed steps, see [Use Role-Based Access Control to manage access to your Azure subscription resources](/azure/active-directory/role-based-access-control-configure).</span></span> <span data-ttu-id="827eb-272">구독을 만드는 관리자는 이 액세스 권한을 암시적으로 사용할 수 있으며 참가자 역할에 다른 관리자를 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="827eb-272">The administrator who creates a subscription has this access implicitly, and the ability to assign other administrators to the Contributor role.</span></span>

- <span data-ttu-id="827eb-273">Exchange Online 및 비즈니스용 Skype와 함께 고객 키를 사용하려는 경우 Exchange Online 및 비즈니스용 Skype 대신 키 자격 증명 모음을 사용할 수 있는 권한을 Microsoft 365에 부여해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="827eb-273">If you intend to use Customer Key with Exchange Online and Skype for Business, you need to give permission to Microsoft 365 to use the key vault on behalf of Exchange Online and Skype for Business.</span></span> <span data-ttu-id="827eb-274">마찬가지로, SharePoint Online 및 비즈니스용 OneDrive에서 고객 키를 사용하려는 경우 SharePoint Online 및 비즈니스용 OneDrive 대신 키 자격 증명 모음을 사용할 수 있는 권한을 Microsoft 365에 추가해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="827eb-274">Likewise, if you intend to use Customer Key with SharePoint Online and OneDrive for Business, you need to add permission for the Microsoft 365 to use the key vault on behalf of SharePoint Online and OneDrive for Business.</span></span> <span data-ttu-id="827eb-275">Microsoft 365에 대한 사용 권한을 부여하려면 다음 구문을 사용하여 **Set-AzKeyVaultAccessPolicy** cmdlet을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="827eb-275">To give permission to Microsoft 365, run the **Set-AzKeyVaultAccessPolicy** cmdlet using the following syntax:</span></span>

   ```powershell
   Set-AzKeyVaultAccessPolicy -VaultName <vault name> -PermissionsToKeys wrapKey,unwrapKey,get -ServicePrincipalName <Office 365 appID>
   ```

   <span data-ttu-id="827eb-276">여기서,</span><span class="sxs-lookup"><span data-stu-id="827eb-276">Where:</span></span>

    - <span data-ttu-id="827eb-277">*자격 증명 모음* 이름은 만든 키 자격 증명 모음의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="827eb-277">*vault name* is the name of the key vault you created.</span></span>

    - <span data-ttu-id="827eb-278">Exchange Online 및 비즈니스용 Skype의 경우 *Office 365 appID를*`00000002-0000-0ff1-ce00-000000000000`</span><span class="sxs-lookup"><span data-stu-id="827eb-278">For Exchange Online and Skype for Business, replace  *Office 365 appID* with `00000002-0000-0ff1-ce00-000000000000`</span></span>

    - <span data-ttu-id="827eb-279">SharePoint Online, 비즈니스용 OneDrive 및 Teams 파일의 경우 *Office 365 appID를*`00000003-0000-0ff1-ce00-000000000000`</span><span class="sxs-lookup"><span data-stu-id="827eb-279">For SharePoint Online, OneDrive for Business, and Teams files, replace  *Office 365 appID* with `00000003-0000-0ff1-ce00-000000000000`</span></span>

  <span data-ttu-id="827eb-280">예: Exchange Online 및 비즈니스용 Skype에 대한 사용 권한 설정:</span><span class="sxs-lookup"><span data-stu-id="827eb-280">Example: Setting permissions for Exchange Online and Skype for Business:</span></span>

   ```powershell
   Set-AzKeyVaultAccessPolicy -VaultName Contoso-O365EX-NA-VaultA1 -PermissionsToKeys wrapKey,unwrapKey,get -ServicePrincipalName 00000002-0000-0ff1-ce00-000000000000
   ```

  <span data-ttu-id="827eb-281">예: SharePoint Online, 비즈니스용 OneDrive 및 Teams 파일에 대한 사용 권한 설정:</span><span class="sxs-lookup"><span data-stu-id="827eb-281">Example: Setting permissions for SharePoint Online, OneDrive for Business, and Teams files:</span></span>

   ```powershell
   Set-AzKeyVaultAccessPolicy -VaultName Contoso-O365SP-NA-VaultA1 -PermissionsToKeys wrapKey,unwrapKey,get -ServicePrincipalName 00000003-0000-0ff1-ce00-000000000000
   ```

### <a name="enable-and-then-confirm-soft-delete-on-your-key-vaults"></a><span data-ttu-id="827eb-282">키 자격 증명 모음에서 소프트 삭제를 사용하도록 설정한 다음 확인</span><span class="sxs-lookup"><span data-stu-id="827eb-282">Enable and then confirm soft delete on your key vaults</span></span>

<span data-ttu-id="827eb-283">키를 빠르게 복구할 수 있는 경우 실수로 또는 악의적으로 삭제된 키로 인해 확장된 서비스가 사용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="827eb-283">When you can quickly recover your keys, you are less likely to experience an extended service outage due to accidentally or maliciously deleted keys.</span></span> <span data-ttu-id="827eb-284">고객 키와 함께 키를 사용하려면 먼저 소프트 삭제라고 하는 이 구성을 사용하도록 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="827eb-284">You need to enable this configuration, referred to as Soft Delete, before you can use your keys with Customer Key.</span></span> <span data-ttu-id="827eb-285">소프트 삭제를 사용하도록 설정하면 백업에서 복원하지 않고도 삭제 후 90일 이내에 키나 자격 증명 모음을 복구할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="827eb-285">Enabling Soft Delete allows you to recover keys or vaults within 90 days of deletion without having to restore them from backup.</span></span>
  
<span data-ttu-id="827eb-286">키 자격 증명 모음에서 소프트 삭제를 사용하도록 설정하려면 다음 단계를 완료합니다.</span><span class="sxs-lookup"><span data-stu-id="827eb-286">To enable Soft Delete on your key vaults, complete these steps:</span></span>
  
1. <span data-ttu-id="827eb-287">구독을 사용하여 Azure 구독에 Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="827eb-287">Sign in to your Azure subscription with Windows PowerShell.</span></span> <span data-ttu-id="827eb-288">자세한 내용은 [Azure PowerShell로 로그인을 참조하세요.](/powershell/azure/authenticate-azureps)</span><span class="sxs-lookup"><span data-stu-id="827eb-288">For instructions, see [Sign in with Azure PowerShell](/powershell/azure/authenticate-azureps).</span></span>

2. <span data-ttu-id="827eb-289">[Get-AzKeyVault](/powershell/module/az.keyvault/get-azkeyvault) cmdlet을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="827eb-289">Run the [Get-AzKeyVault](/powershell/module/az.keyvault/get-azkeyvault) cmdlet.</span></span> <span data-ttu-id="827eb-290">이 예에서 자격 증명 모음 *이름은* 소프트 삭제를 사용하도록 설정하는 키 자격 증명 모음의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="827eb-290">In this example, *vault name* is the name of the key vault for which you are enabling soft delete:</span></span>

   ```powershell
   $v = Get-AzKeyVault -VaultName <vault name>
   $r = Get-AzResource -ResourceId $v.ResourceId
   $r.Properties | Add-Member -MemberType NoteProperty -Name enableSoftDelete -Value 'True'
   Set-AzResource -ResourceId $r.ResourceId -Properties $r.Properties
   ```

3. <span data-ttu-id="827eb-291">**Get-AzKeyVault** cmdlet을 실행하여 키 자격 증명 모음에 대해 소프트 삭제가 구성되어 있는지 확인</span><span class="sxs-lookup"><span data-stu-id="827eb-291">Confirm soft delete is configured for the key vault by running the **Get-AzKeyVault** cmdlet.</span></span> <span data-ttu-id="827eb-292">키 자격 증명 모음에 대해 소프트 삭제가 제대로 구성되어 있는 경우 _Soft Delete Enabled_ 속성은 True 값을 **반환합니다.**</span><span class="sxs-lookup"><span data-stu-id="827eb-292">If soft delete is configured properly for the key vault, then the _Soft Delete Enabled_ property returns a value of **True**:</span></span>

   ```powershell
   Get-AzKeyVault -VaultName <vault name> | fl
   ```

### <a name="add-a-key-to-each-key-vault-either-by-creating-or-importing-a-key"></a><span data-ttu-id="827eb-293">키를 만들거나 가져와서 각 키 자격 증명 모음에 키 추가</span><span class="sxs-lookup"><span data-stu-id="827eb-293">Add a key to each key vault either by creating or importing a key</span></span>

<span data-ttu-id="827eb-294">Azure Key Vault에 키를 추가하는 방법에는 두 가지가 있습니다. 키 자격 증명 모음에서 직접 키를 만들거나 키를 가져올 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="827eb-294">There are two ways to add keys to an Azure Key Vault; you can create a key directly in Key Vault, or you can import a key.</span></span> <span data-ttu-id="827eb-295">키 자격 증명 모음에서 직접 키를 만드는 것은 덜 복잡하지만 키를 가져오면 키 생성 방법을 완전히 제어할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="827eb-295">Creating a key directly in Key Vault is the less complicated method, while importing a key provides total control over how the key is generated.</span></span> <span data-ttu-id="827eb-296">RSA 키를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="827eb-296">Use the RSA keys.</span></span> <span data-ttu-id="827eb-297">Azure Key Vault는 타원 곡선 키로 래핑 및 래핑을 지원하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="827eb-297">Azure Key Vault doesn't support wrapping and unwrapping with elliptical curve keys.</span></span>
  
<span data-ttu-id="827eb-298">키 자격 증명 모음에서 직접 키를 만들 수 있도록 [Add-AzKeyVaultKey](/powershell/module/az.keyvault/add-azkeyvaultkey) cmdlet을 다음과 같이 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="827eb-298">To create a key directly in your key vault, run the [Add-AzKeyVaultKey](/powershell/module/az.keyvault/add-azkeyvaultkey) cmdlet as follows:</span></span>
  
```powershell
Add-AzKeyVaultKey -VaultName <vault name> -Name <key name> -Destination <HSM|Software> -KeyOps wrapKey,unwrapKey
```

<span data-ttu-id="827eb-299">여기서,</span><span class="sxs-lookup"><span data-stu-id="827eb-299">Where:</span></span>

- <span data-ttu-id="827eb-300">*자격 증명* 모음 이름은 키를 만들 키 자격 증명 모음의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="827eb-300">*vault name* is the name of the key vault in which you want to create the key.</span></span>

- <span data-ttu-id="827eb-301">*key name은* 새 키를 제공하려는 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="827eb-301">*key name* is the name you want to give the new key.</span></span>

  > [!TIP]
  > <span data-ttu-id="827eb-302">키 자격 증명 모음에 대해 위에서 설명한 대로 유사한 명명 규칙을 사용하는 이름 키입니다.</span><span class="sxs-lookup"><span data-stu-id="827eb-302">Name keys using a similar naming convention as described above for key vaults.</span></span> <span data-ttu-id="827eb-303">이렇게 하면 키 이름만 표시하는 도구에서 문자열은 자체 설명을 합니다.</span><span class="sxs-lookup"><span data-stu-id="827eb-303">This way, in tools that show only the key name, the string is self-describing.</span></span>
  
<span data-ttu-id="827eb-304">HSM으로 키를 보호하려는 경우 **HSM을** _Destination_ 매개 변수 값으로 지정해야 합니다. 그렇지 않으면 Software 를 **지정합니다.**</span><span class="sxs-lookup"><span data-stu-id="827eb-304">If you intend to protect the key with an HSM, ensure that you specify **HSM** as the value of the _Destination_ parameter, otherwise, specify **Software**.</span></span>

<span data-ttu-id="827eb-305">예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="827eb-305">For example,</span></span>
  
```powershell
Add-AzKeyVaultKey -VaultName Contoso-O365EX-NA-VaultA1 -Name Contoso-O365EX-NA-VaultA1-Key001 -Destination HSM -KeyOps wrapKey,unwrapKey
```

<span data-ttu-id="827eb-306">키를 키 자격 증명 모음으로 직접 가져오기 위해 nCipher nShield 하드웨어 보안 모듈이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="827eb-306">To import a key directly into your key vault, you need to have a nCipher nShield Hardware Security Module.</span></span>
  
<span data-ttu-id="827eb-307">일부 조직에서는 키의 입증을 설정하기 위해 이 접근 방식을 선호하고 이 방법을 통해 다음 증명도 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="827eb-307">Some organizations prefer this approach to establish the provenance of their keys, and then this method also provides the following attestations:</span></span>
  
- <span data-ttu-id="827eb-308">가져오기에 사용되는 도구et에는 nCipher에서 생성한 키를 암호화하는 데 사용되는 KEK(키 Exchange 키)가 내보낼 수 없는 것으로, nCipher에서 제조한 정품 HSM 내에서 생성되었다는 의증이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="827eb-308">The toolset used for import includes attestation from nCipher that the Key Exchange Key (KEK) that is used to encrypt the key you generate is not exportable and is generated inside a genuine HSM that was manufactured by nCipher.</span></span>

- <span data-ttu-id="827eb-309">도구 모음에는 nCipher에서 Azure Key Vault 보안 월드가 nCipher에서 제조한 정품 HSM에서도 생성되었다는 증명이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="827eb-309">The toolset includes attestation from nCipher that the Azure Key Vault security world was also generated on a genuine HSM manufactured by nCipher.</span></span> <span data-ttu-id="827eb-310">이 증명은 Microsoft가 정품 nCipher 하드웨어도 사용하고 있는 것을 증명합니다.</span><span class="sxs-lookup"><span data-stu-id="827eb-310">This attestation proves to you that Microsoft is also using genuine nCipher hardware.</span></span>

<span data-ttu-id="827eb-311">보안 그룹에 확인하여 위의 의거가 필요한지 여부를 파악합니다.</span><span class="sxs-lookup"><span data-stu-id="827eb-311">Check with your security group to determine if the above attestations are required.</span></span> <span data-ttu-id="827eb-312">키를 사내에 만들고 키 자격 증명 모음으로 가져오는 자세한 단계는 [Azure Key Vault에 대한 HSM](/azure/key-vault/keys/hsm-protected-keys)보호 키를 생성하고 전송하는 방법을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="827eb-312">For detailed steps to create a key on-premises and import it into your key vault, see [How to generate and transfer HSM-protected keys for Azure Key Vault](/azure/key-vault/keys/hsm-protected-keys).</span></span> <span data-ttu-id="827eb-313">Azure 지침을 사용하여 각 키 자격 증명 모음에 키를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="827eb-313">Use the Azure instructions to create a key in each key vault.</span></span>
  
### <a name="check-the-recovery-level-of-your-keys"></a><span data-ttu-id="827eb-314">키의 복구 수준 확인</span><span class="sxs-lookup"><span data-stu-id="827eb-314">Check the recovery level of your keys</span></span>

<span data-ttu-id="827eb-315">Microsoft 365를 사용하려면 Azure Key Vault 구독이 취소 금지로 설정되어 있으며 고객 키에서 사용하는 키가 소프트 삭제를 사용하도록 설정되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="827eb-315">Microsoft 365 requires that the Azure Key Vault subscription is set to Do Not Cancel and that the keys used by Customer Key have soft delete enabled.</span></span> <span data-ttu-id="827eb-316">키의 복구 수준을 확인하여 구독 설정을 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="827eb-316">You can confirm you subscriptions settings by looking at the recovery level on your keys.</span></span>
  
<span data-ttu-id="827eb-317">키의 복구 수준을 확인하기 위해 Azure PowerShell에서 다음과 Get-AzKeyVaultKey cmdlet을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="827eb-317">To check the recovery level of a key, in Azure PowerShell, run the Get-AzKeyVaultKey cmdlet as follows:</span></span>
  
```powershell
(Get-AzKeyVaultKey -VaultName <vault name> -Name <key name>).Attributes
```

<span data-ttu-id="827eb-318">Recovery _Level_ 속성이 **Recoverable+ProtectedSubscription** 값 외의 값을 반환하는 경우 구독을 취소 금지 목록에 추가하고 각 키 자격 증명 모음에서 소프트 삭제를 사용하도록 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="827eb-318">If the _Recovery Level_ property returns anything other than a value of **Recoverable+ProtectedSubscription**, ensure that you have put the subscription on the Do Not Cancel list and that you have soft delete enabled on each of your key vaults.</span></span>
  
### <a name="back-up-azure-key-vault"></a><span data-ttu-id="827eb-319">Azure Key Vault 백업</span><span class="sxs-lookup"><span data-stu-id="827eb-319">Back up Azure Key Vault</span></span>

<span data-ttu-id="827eb-320">키가 만들어지거나 키가 변경된 직후 백업을 수행하고 온라인 및 오프라인으로 백업 복사본을 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="827eb-320">Immediately following creation or any change to a key, perform a backup and store copies of the backup, both online and offline.</span></span> <span data-ttu-id="827eb-321">오프라인 복사본은 물리적 안전 또는 상업용 저장소 시설과 같은 네트워크에 연결하면 안 됩니다.</span><span class="sxs-lookup"><span data-stu-id="827eb-321">Offline copies should not be connected to any network, such as in a physical safe or commercial storage facility.</span></span> <span data-ttu-id="827eb-322">재해 발생 시 액세스할 수 있는 위치에 백업 복사본을 하나 이상 저장해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="827eb-322">At least one copy of the backup should be stored in a location that will be accessible in the event of a disaster.</span></span> <span data-ttu-id="827eb-323">키 자격 증명 키를 영구적으로 삭제하거나 사용할 수 없는 경우 백업 Blob은 키 자료를 복원하는 유일한 수단입니다.</span><span class="sxs-lookup"><span data-stu-id="827eb-323">The backup blobs are the sole means of restoring key material should a Key Vault key be permanently destroyed or otherwise rendered inoperable.</span></span> <span data-ttu-id="827eb-324">Azure Key Vault 외부에서 Azure Key Vault로 가져온 키는 고객 키가 키를 사용하는 데 필요한 메타데이터가 외부 키와 함께 존재하지 않는 때문에 백업으로 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="827eb-324">Keys that are external to Azure Key Vault and were imported to Azure Key Vault do not qualify as a backup because the metadata necessary for Customer Key to use the key does not exist with the external key.</span></span> <span data-ttu-id="827eb-325">Azure Key Vault에서 수행한 백업만 고객 키를 사용하여 복원 작업에 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="827eb-325">Only a backup taken from Azure Key Vault can be used for restore operations with Customer Key.</span></span> <span data-ttu-id="827eb-326">따라서 키를 업로드하거나 만든 후 Azure Key Vault의 백업을 만들어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="827eb-326">Therefore, you must create a backup of Azure Key Vault after you upload or create a key.</span></span>
  
<span data-ttu-id="827eb-327">Azure Key Vault 키의 백업을 만들 경우 다음과 같이 [Backup-AzKeyVaultKey](/powershell/module/az.keyvault/backup-azkeyvaultkey) cmdlet을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="827eb-327">To create a backup of an Azure Key Vault key, run the [Backup-AzKeyVaultKey](/powershell/module/az.keyvault/backup-azkeyvaultkey) cmdlet as follows:</span></span>

```powershell
Backup-AzKeyVaultKey -VaultName <vault name> -Name <key name>
-OutputFile <filename.backup>
```

<span data-ttu-id="827eb-328">출력 파일에서 접미사 를 사용하는지 `.backup` 확인</span><span class="sxs-lookup"><span data-stu-id="827eb-328">Ensure that your output file uses the suffix `.backup`.</span></span>
  
<span data-ttu-id="827eb-329">이 cmdlet에서 생성되는 출력 파일은 암호화되며 Azure Key Vault 외부에서 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="827eb-329">The output file resulting from this cmdlet is encrypted and cannot be used outside of Azure Key Vault.</span></span> <span data-ttu-id="827eb-330">백업은 백업을 수행한 Azure 구독으로만 복원할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="827eb-330">The backup can be restored only to the Azure subscription from which the backup was taken.</span></span>
  
> [!TIP]
> <span data-ttu-id="827eb-331">출력 파일의 경우 자격 증명 모음 이름과 키 이름을 조합하여 선택하십시오.</span><span class="sxs-lookup"><span data-stu-id="827eb-331">For the output file, choose a combination of your vault name and key name.</span></span> <span data-ttu-id="827eb-332">이렇게 하면 파일 이름이 자체 설명으로 지정됩니다.</span><span class="sxs-lookup"><span data-stu-id="827eb-332">This will make the file name self-describing.</span></span> <span data-ttu-id="827eb-333">또한 백업 파일 이름이 충돌하지 않도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="827eb-333">It will also ensure that backup file names do not collide.</span></span>
  
<span data-ttu-id="827eb-334">예를 들어 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="827eb-334">For example:</span></span>
  
```powershell
Backup-AzKeyVaultKey -VaultName Contoso-O365EX-NA-VaultA1 -Name Contoso-O365EX-NA-VaultA1-Key001 -OutputFile Contoso-O365EX-NA-VaultA1-Key001-Backup-20170802.backup
```

### <a name="validate-azure-key-vault-configuration-settings"></a><span data-ttu-id="827eb-335">Azure Key Vault 구성 설정 유효성 검사</span><span class="sxs-lookup"><span data-stu-id="827eb-335">Validate Azure Key Vault configuration settings</span></span>

<span data-ttu-id="827eb-336">DEP에서 키를 사용하기 전에 유효성을 검사하는 것은 선택 사항이지만 매우 권장됩니다.</span><span class="sxs-lookup"><span data-stu-id="827eb-336">Validating before using keys in a DEP is optional, but highly recommended.</span></span> <span data-ttu-id="827eb-337">단계에 따라 이 문서에 설명된 키와 자격 증명 모음을 설정하는 경우 고객 키를 구성하기 전에 Azure Key Vault 리소스의 상태 유효성을 검사합니다.</span><span class="sxs-lookup"><span data-stu-id="827eb-337">If you use steps to set up your keys and vaults other than the ones described in this article, validate the health of your Azure Key Vault resources before you configure Customer Key.</span></span>
  
<span data-ttu-id="827eb-338">키에 , 및 작업이 `get` `wrapKey` 사용하도록 `unwrapKey` 설정되어 있는지 확인:</span><span class="sxs-lookup"><span data-stu-id="827eb-338">To verify that your keys have `get`, `wrapKey`, and `unwrapKey` operations enabled:</span></span>
  
<span data-ttu-id="827eb-339">다음과 [같이 Get-AzKeyVault](/powershell/module/az.keyvault/get-azkeyvault) cmdlet을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="827eb-339">Run the [Get-AzKeyVault](/powershell/module/az.keyvault/get-azkeyvault) cmdlet as follows:</span></span>
  
```powershell
Get-AzKeyVault -VaultName <vault name>
```

<span data-ttu-id="827eb-340">출력에서 액세스 정책 및 Exchange Online ID(GUID) 또는 SharePoint Online ID(GUID)를 적절하게 찾아냅니다.</span><span class="sxs-lookup"><span data-stu-id="827eb-340">In the output, look for the Access Policy and for the Exchange Online identity (GUID) or the SharePoint Online identity (GUID) as appropriate.</span></span> <span data-ttu-id="827eb-341">위의 세 사용 권한은 모두 키에 대한 사용 권한 아래에 표시되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="827eb-341">All three of the above permissions must be shown under Permissions to Keys.</span></span>
  
<span data-ttu-id="827eb-342">액세스 정책 구성이 올바르지 않은 경우 다음과 Set-AzKeyVaultAccessPolicy cmdlet을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="827eb-342">If the access policy configuration is incorrect, run the Set-AzKeyVaultAccessPolicy cmdlet as follows:</span></span>
  
```powershell
Set-AzKeyVaultAccessPolicy -VaultName <vault name> -PermissionsToKeys wrapKey,unwrapKey,get -ServicePrincipalName <Office 365 appID>
```

<span data-ttu-id="827eb-343">예를 들어 Exchange Online 및 비즈니스용 Skype의 경우:</span><span class="sxs-lookup"><span data-stu-id="827eb-343">For example, for Exchange Online and Skype for Business:</span></span>
  
```powershell
Set-AzKeyVaultAccessPolicy -VaultName Contoso-O365EX-NA-VaultA1 
-PermissionsToKeys wrapKey,unwrapKey,get -ServicePrincipalName 00000002-0000-0ff1-ce00-000000000000
```

<span data-ttu-id="827eb-344">예를 들어 SharePoint Online 및 비즈니스용 OneDrive의 경우:</span><span class="sxs-lookup"><span data-stu-id="827eb-344">For example, for SharePoint Online and OneDrive for Business:</span></span>
  
```powershell
Set-AzKeyVaultAccessPolicy -VaultName Contoso-O365SP-NA-VaultA1
-PermissionsToKeys wrapKey,unwrapKey,get -ServicePrincipalName 00000003-0000-0ff1-ce00-000000000000
```

<span data-ttu-id="827eb-345">키에 대한 만료 날짜가 설정되어 있지 않은지 확인하기 위해 다음과 같이 [Get-AzKeyVaultKey](/powershell/module/az.keyvault/get-azkeyvault) cmdlet을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="827eb-345">To verify that an expiration date isn't set for your keys, run the [Get-AzKeyVaultKey](/powershell/module/az.keyvault/get-azkeyvault) cmdlet as follows:</span></span>
  
```powershell
Get-AzKeyVaultKey -VaultName <vault name>
```

<span data-ttu-id="827eb-346">고객 키는 만료된 키를 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="827eb-346">Customer Key can't use an expired key.</span></span> <span data-ttu-id="827eb-347">만료된 키로 작업을 시도하면 오류가 발생하여 서비스가 종료될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="827eb-347">Operations attempted with an expired key will fail, and possibly result in a service outage.</span></span> <span data-ttu-id="827eb-348">고객 키에 사용되는 키에는 만료 날짜가 없는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="827eb-348">We strongly recommend that keys used with Customer Key do not have an expiration date.</span></span> <span data-ttu-id="827eb-349">만료 날짜(설정된 경우)는 제거할 수 없지만 다른 날짜로 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="827eb-349">An expiration date, once set, cannot be removed, but can be changed to a different date.</span></span> <span data-ttu-id="827eb-350">만료 날짜가 설정된 키를 사용하려면 만료 값을 12/31/9999로 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="827eb-350">If a key must be used that has an expiration date set, change the expiration value to 12/31/9999.</span></span> <span data-ttu-id="827eb-351">만료 날짜가 12/31/9999가 아닌 날짜로 설정된 키는 Microsoft 365 유효성 검사를 통과하지 못합니다.</span><span class="sxs-lookup"><span data-stu-id="827eb-351">Keys with an expiration date set to a date other than 12/31/9999 will not pass Microsoft 365 validation.</span></span>
  
<span data-ttu-id="827eb-352">12/31/9999가 아니라 다른 값으로 설정된 만료 날짜를 변경하기 위해 다음과 같이 [Update-AzKeyVaultKey](/powershell/module/az.keyvault/update-azkeyvaultkey) cmdlet을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="827eb-352">To change an expiration date that has been set to any value other than 12/31/9999, run the [Update-AzKeyVaultKey](/powershell/module/az.keyvault/update-azkeyvaultkey) cmdlet as follows:</span></span>
  
```powershell
Update-AzKeyVaultKey -VaultName <vault name> -Name <key name> -Expires (Get-Date -Date "12/31/9999")
```

> [!CAUTION]
> <span data-ttu-id="827eb-353">고객 키와 함께 사용하는 암호화 키에 만료 날짜를 설정하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="827eb-353">Don't set expiration dates on encryption keys you use with Customer Key.</span></span>
  
### <a name="obtain-the-uri-for-each-azure-key-vault-key"></a><span data-ttu-id="827eb-354">각 Azure Key Vault 키에 대한 URI 얻기</span><span class="sxs-lookup"><span data-stu-id="827eb-354">Obtain the URI for each Azure Key Vault key</span></span>

<span data-ttu-id="827eb-355">키 자격 증명 모음을 설정하고 키를 추가한 후 다음 명령을 실행하여 각 키 자격 증명 모음의 키에 대한 URI를 얻습니다.</span><span class="sxs-lookup"><span data-stu-id="827eb-355">Once you've set up your key vaults and added your keys, run the following command to get the URI for the key in each key vault.</span></span> <span data-ttu-id="827eb-356">나중에 각 DEP를 만들고 할당할 때 이러한 URIS를 사용하여 이 정보를 안전한 장소에 저장해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="827eb-356">You'll need to use these URIs when you create and assign each DEP later, so save this information in a safe place.</span></span> <span data-ttu-id="827eb-357">각 키 자격 증명 모음에 대해 이 명령을 한 번 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="827eb-357">Run this command once for each key vault.</span></span>
  
<span data-ttu-id="827eb-358">Azure PowerShell에서:</span><span class="sxs-lookup"><span data-stu-id="827eb-358">In Azure PowerShell:</span></span>
  
```powershell
(Get-AzKeyVaultKey -VaultName <vault name>).Id
```

## <a name="office-365-setting-up-customer-key-for-exchange-online-and-skype-for-business"></a><span data-ttu-id="827eb-359">Office 365: Exchange Online 및 비즈니스용 Skype에 대한 고객 키 설정</span><span class="sxs-lookup"><span data-stu-id="827eb-359">Office 365: Setting up Customer Key for Exchange Online and Skype for Business</span></span>

<span data-ttu-id="827eb-360">시작하기 전에 Azure Key Vault를 설정하는 데 필요한 작업을 완료해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="827eb-360">Before you begin, ensure that you've completed the tasks required to set up Azure Key Vault.</span></span> <span data-ttu-id="827eb-361">자세한 내용은 Azure Key Vault 및 [Microsoft FastTrack for Customer Key의](#complete-tasks-in-azure-key-vault-and-microsoft-fasttrack-for-customer-key) 작업 완료를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="827eb-361">See [Complete tasks in Azure Key Vault and Microsoft FastTrack for Customer Key](#complete-tasks-in-azure-key-vault-and-microsoft-fasttrack-for-customer-key) for information.</span></span>
  
<span data-ttu-id="827eb-362">Exchange Online 및 비즈니스용 Skype에 대한 고객 키를 설정하기 위해 Exchange Online에 원격으로 연결하여 이러한 단계를 Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="827eb-362">To set up Customer Key for Exchange Online and Skype for Business, you'll complete these steps by remotely connecting to Exchange Online with Windows PowerShell.</span></span>
  
### <a name="create-a-data-encryption-policy-dep-for-use-with-exchange-online-and-skype-for-business"></a><span data-ttu-id="827eb-363">Exchange Online 및 비즈니스용 Skype에서 사용할 DEP(데이터 암호화 정책) 만들기</span><span class="sxs-lookup"><span data-stu-id="827eb-363">Create a data encryption policy (DEP) for use with Exchange Online and Skype for Business</span></span>

<span data-ttu-id="827eb-364">DEP는 Azure Key Vault에 저장된 키 집합과 연결됩니다.</span><span class="sxs-lookup"><span data-stu-id="827eb-364">A DEP is associated with a set of keys stored in Azure Key Vault.</span></span> <span data-ttu-id="827eb-365">Microsoft 365의 사서함에 DEP를 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="827eb-365">You assign a DEP to a mailbox in Microsoft 365.</span></span> <span data-ttu-id="827eb-366">그런 다음 Microsoft 365는 정책에 식별된 키를 사용하여 사서함을 암호화합니다.</span><span class="sxs-lookup"><span data-stu-id="827eb-366">Microsoft 365 will then use the keys identified in the policy to encrypt the mailbox.</span></span> <span data-ttu-id="827eb-367">DEP를 만들하려면 앞서 획득한 키 자격 증명 모음 UR이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="827eb-367">To create the DEP, you need the Key Vault URIs you obtained earlier.</span></span> <span data-ttu-id="827eb-368">지침은 각 Azure Key Vault 키에 대한 [URI 얻기를](#obtain-the-uri-for-each-azure-key-vault-key) 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="827eb-368">See [Obtain the URI for each Azure Key Vault key](#obtain-the-uri-for-each-azure-key-vault-key) for instructions.</span></span>
  
<span data-ttu-id="827eb-369">기억하세요!</span><span class="sxs-lookup"><span data-stu-id="827eb-369">Remember!</span></span> <span data-ttu-id="827eb-370">DEP를 만들 때 두 개의 서로 다른 Azure Key Vault에 두 개의 키를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="827eb-370">When you create a DEP, you specify two keys in two different Azure Key Vaults.</span></span> <span data-ttu-id="827eb-371">두 개의 별도 Azure 지역에서 이러한 키를 만들어 지리적 중복을 보장합니다.</span><span class="sxs-lookup"><span data-stu-id="827eb-371">Create these keys in two separate Azure regions to ensure geo-redundancy.</span></span>
  
<span data-ttu-id="827eb-372">DEP를 만들 수 있는 단계는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="827eb-372">To create the DEP, follow these steps:</span></span>
  
1. <span data-ttu-id="827eb-373">로컬 컴퓨터에서 조직의 전역 관리자 권한이 있는 직장 또는 학교 계정을 사용하여 조직 창에서 [Exchange Online PowerShell에](/powershell/exchange/connect-to-exchange-online-powershell) Windows PowerShell 합니다.</span><span class="sxs-lookup"><span data-stu-id="827eb-373">On your local computer, using a work or school account that has global administrator permissions in your organization, [connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell) in a Windows PowerShell window.</span></span>

2. <span data-ttu-id="827eb-374">DEP를 만들 New-DataEncryptionPolicy 명령을 입력하여 New-DataEncryptionPolicy cmdlet을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="827eb-374">To create a DEP, use the New-DataEncryptionPolicy cmdlet by typing the following command.</span></span>

   ```powershell
   New-DataEncryptionPolicy -Name <PolicyName> -Description "Policy Description" -AzureKeyIDs <KeyVaultURI1>, <KeyVaultURI2>
   ```

   <span data-ttu-id="827eb-375">여기서,</span><span class="sxs-lookup"><span data-stu-id="827eb-375">Where:</span></span>

   - <span data-ttu-id="827eb-376">*PolicyName은* 정책에 사용할 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="827eb-376">*PolicyName* is the name you want to use for the policy.</span></span> <span data-ttu-id="827eb-377">이름에는 공백을 포함할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="827eb-377">Names can't contain spaces.</span></span> <span data-ttu-id="827eb-378">예를 들어 USA_mailboxes.</span><span class="sxs-lookup"><span data-stu-id="827eb-378">For example, USA_mailboxes.</span></span>

   - <span data-ttu-id="827eb-379">*정책 설명은* 정책에 대한 정보를 기억하는 데 도움이 되는 정책에 대한 사용자에게 친숙한 설명입니다.</span><span class="sxs-lookup"><span data-stu-id="827eb-379">*Policy Description* is a user-friendly description of the policy that will help you remember what the policy is for.</span></span> <span data-ttu-id="827eb-380">설명에 공백을 포함할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="827eb-380">You can include spaces in the description.</span></span> <span data-ttu-id="827eb-381">예를 들어 "미국 사서함과 해당 지역의 루트 키"를 예로 들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="827eb-381">For example, "Root key for mailboxes in USA and its territories".</span></span>

   - <span data-ttu-id="827eb-382">*KeyVaultURI1은* 정책의 첫 번째 키에 대한 URI입니다.</span><span class="sxs-lookup"><span data-stu-id="827eb-382">*KeyVaultURI1* is the URI for the first key in the policy.</span></span> <span data-ttu-id="827eb-383">예를 들면 <https://contoso_EastUSvault01.vault.azure.net/keys/USA_key_01>와 같습니다.</span><span class="sxs-lookup"><span data-stu-id="827eb-383">For example, <https://contoso_EastUSvault01.vault.azure.net/keys/USA_key_01>.</span></span>

   - <span data-ttu-id="827eb-384">*KeyVaultURI2는* 정책의 두 번째 키에 대한 URI입니다.</span><span class="sxs-lookup"><span data-stu-id="827eb-384">*KeyVaultURI2* is the URI for the second key in the policy.</span></span> <span data-ttu-id="827eb-385">예를 들면 <https://contoso_EastUS2vault01.vault.azure.net/keys/USA_Key_02>와 같습니다.</span><span class="sxs-lookup"><span data-stu-id="827eb-385">For example, <https://contoso_EastUS2vault01.vault.azure.net/keys/USA_Key_02>.</span></span> <span data-ttu-id="827eb-386">두 URIS를 콤보와 공백으로 구분합니다.</span><span class="sxs-lookup"><span data-stu-id="827eb-386">Separate the two URIs by a comma and a space.</span></span>

   <span data-ttu-id="827eb-387">예제:</span><span class="sxs-lookup"><span data-stu-id="827eb-387">Example:</span></span>
  
   ```powershell
   New-DataEncryptionPolicy -Name USA_mailboxes -Description "Root key for mailboxes in USA and its territories" -AzureKeyIDs https://contoso_EastUSvault01.vault.azure.net/keys/USA_key_01, https://contoso_EastUS2vault01.vault.azure.net/keys/USA_Key_02
   ```

<span data-ttu-id="827eb-388">구문과 매개 변수에 대한 자세한 내용은 [New-DataEncryptionPolicy를 참조하십시오.](/powershell/module/exchange/new-data-encryptionpolicy)</span><span class="sxs-lookup"><span data-stu-id="827eb-388">For detailed syntax and parameter information, see [New-DataEncryptionPolicy](/powershell/module/exchange/new-data-encryptionpolicy).</span></span>

### <a name="assign-a-dep-to-a-mailbox"></a><span data-ttu-id="827eb-389">사서함에 DEP 할당</span><span class="sxs-lookup"><span data-stu-id="827eb-389">Assign a DEP to a mailbox</span></span>

<span data-ttu-id="827eb-390">사용자 지정 cmdlet을 사용하여 사서함에 DEP를 Set-Mailbox 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="827eb-390">Assign the DEP to a mailbox by using the Set-Mailbox cmdlet.</span></span> <span data-ttu-id="827eb-391">정책을 할당하면 Microsoft 365에서 DEP에 식별된 키로 사서함을 암호화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="827eb-391">Once you assign the policy, Microsoft 365 can encrypt the mailbox with the key identified in the DEP.</span></span>
  
```powershell
Set-Mailbox -Identity <MailboxIdParameter> -DataEncryptionPolicy <PolicyName>
```

<span data-ttu-id="827eb-392">여기서 *MailboxIdParameter는* 사용자 사서함을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="827eb-392">Where *MailboxIdParameter* specifies a user mailbox.</span></span> <span data-ttu-id="827eb-393">cmdlet에 대한 Set-Mailbox 자세한 내용은 [Set-Mailbox를 참조하십시오.](/powershell/module/exchange/set-mailbox)</span><span class="sxs-lookup"><span data-stu-id="827eb-393">For more information about the Set-Mailbox cmdlet, see [Set-Mailbox](/powershell/module/exchange/set-mailbox).</span></span>

<span data-ttu-id="827eb-394">하이브리드 환경에서는 Exchange Online 테넌트에 동기화된 사내 사서함 데이터에 DEP를 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="827eb-394">In hybrid environments, you can assign a DEP to the on-premises mailbox data that is synchronized into your Exchange Online tenant.</span></span> <span data-ttu-id="827eb-395">이 동기화된 사서함 데이터에 DEP를 할당하기 위해 이 cmdlet을 Set-MailUser 합니다.</span><span class="sxs-lookup"><span data-stu-id="827eb-395">To assign a DEP to this synchronized mailbox data, you'll use the Set-MailUser cmdlet.</span></span> <span data-ttu-id="827eb-396">하이브리드 환경의 사서함 데이터에 대한 자세한 내용은 하이브리드 최신 인증을 사용하는 iOS 및 Android용 Outlook을 사용하는 사내 [사서함을 참조하세요.](/exchange/clients/outlook-for-ios-and-android/use-hybrid-modern-auth)</span><span class="sxs-lookup"><span data-stu-id="827eb-396">For more information about mailbox data in the hybrid environment, see [on-premises mailboxes using Outlook for iOS and Android with hybrid Modern Authentication](/exchange/clients/outlook-for-ios-and-android/use-hybrid-modern-auth).</span></span>

```powershell
Set-MailUser -Identity <MailUserIdParameter> -DataEncryptionPolicy <PolicyName>
```

<span data-ttu-id="827eb-397">여기서 *MailUserIdParameter는* 메일 사용자(메일 사용이 가능한 사용자)를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="827eb-397">Where *MailUserIdParameter* specifies a mail user (also known as a mail-enabled user).</span></span> <span data-ttu-id="827eb-398">cmdlet에 대한 Set-MailUser 자세한 내용은 [Set-MailUser 를 참조하십시오.](/powershell/module/exchange/set-mailuser)</span><span class="sxs-lookup"><span data-stu-id="827eb-398">For more information about the Set-MailUser cmdlet, see [Set-MailUser](/powershell/module/exchange/set-mailuser).</span></span>
  
### <a name="validate-mailbox-encryption"></a><span data-ttu-id="827eb-399">사서함 암호화 유효성 검사</span><span class="sxs-lookup"><span data-stu-id="827eb-399">Validate mailbox encryption</span></span>

<span data-ttu-id="827eb-400">사서함 암호화에는 시간이 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="827eb-400">Encrypting a mailbox can take some time.</span></span> <span data-ttu-id="827eb-401">최초 정책 할당의 경우 서비스에서 사서함을 암호화하기 전에 사서함도 데이터베이스에서 다른 데이터베이스로 완전히 이동해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="827eb-401">For first-time policy assignment, the mailbox must also completely move from one database to another before the service can encrypt the mailbox.</span></span> <span data-ttu-id="827eb-402">DEP를 변경한 후 또는 사서함에 DEP를 처음 할당할 때 암호화 유효성 검사를 시도하기 전에 72시간 동안 기다리는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="827eb-402">We recommend that you wait 72 hours before you attempt to validate encryption after you change a DEP or the first time you assign a DEP to a mailbox.</span></span>
  
<span data-ttu-id="827eb-403">Get-MailboxStatistics cmdlet을 사용하여 사서함이 암호화되어 있는지 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="827eb-403">Use the Get-MailboxStatistics cmdlet to determine if a mailbox is encrypted.</span></span>
  
```powershell
Get-MailboxStatistics -Identity <GeneralMailboxOrMailUserIdParameter> | fl IsEncrypted
```

<span data-ttu-id="827eb-404">IsEncrypted 속성은 사서함이 암호화된 경우 **true** 값을 반환하고 사서함이 암호화되지 않은 경우 **false** 값을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="827eb-404">The IsEncrypted property returns a value of **true** if the mailbox is encrypted and a value of **false** if the mailbox isn't encrypted.</span></span> <span data-ttu-id="827eb-405">사서함 이동을 완료하는 시간은 처음으로 DEP를 할당하는 사서함 수와 사서함의 크기에 따라 달라 니다.</span><span class="sxs-lookup"><span data-stu-id="827eb-405">The time to complete mailbox moves depends on the number of mailboxes to which you assign a DEP for the first time, and the size of the mailboxes.</span></span> <span data-ttu-id="827eb-406">DEP를 할당한 후 1주일 후에도 사서함이 암호화되지 않은 경우 Microsoft에 문의합니다.</span><span class="sxs-lookup"><span data-stu-id="827eb-406">If the mailboxes haven't been encrypted after a week from the time you assigned the DEP, contact Microsoft.</span></span>

## <a name="office-365-setting-up-customer-key-for-sharepoint-online-onedrive-for-business-and-teams-files"></a><span data-ttu-id="827eb-407">Office 365: SharePoint Online, 비즈니스용 OneDrive 및 Teams 파일에 대한 고객 키 설정</span><span class="sxs-lookup"><span data-stu-id="827eb-407">Office 365: Setting up Customer Key for SharePoint Online, OneDrive for Business, and Teams files</span></span>

<span data-ttu-id="827eb-408">시작하기 전에 Azure Key Vault를 설정하는 데 필요한 작업을 완료해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="827eb-408">Before you begin, ensure that you've completed the tasks required to set up Azure Key Vault.</span></span> <span data-ttu-id="827eb-409">자세한 내용은 Azure Key Vault 및 [Microsoft FastTrack for Customer Key의](#complete-tasks-in-azure-key-vault-and-microsoft-fasttrack-for-customer-key) 작업 완료를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="827eb-409">See [Complete tasks in Azure Key Vault and Microsoft FastTrack for Customer Key](#complete-tasks-in-azure-key-vault-and-microsoft-fasttrack-for-customer-key) for information.</span></span>
  
<span data-ttu-id="827eb-410">SharePoint Online, 비즈니스용 OneDrive 및 Teams 파일에 대한 고객 키를 설정하려면 SharePoint Online에 원격으로 연결하여 이러한 단계를 Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="827eb-410">To set up Customer Key for SharePoint Online, OneDrive for Business, and Teams files you complete these steps by remotely connecting to SharePoint Online with Windows PowerShell.</span></span>
  
### <a name="create-a-data-encryption-policy-dep-for-each-sharepoint-online-and-onedrive-for-business-geo"></a><span data-ttu-id="827eb-411">각 SharePoint Online 및 비즈니스용 OneDrive 지리적 데이터에 대한 DEP(데이터 암호화 정책) 만들기</span><span class="sxs-lookup"><span data-stu-id="827eb-411">Create a data encryption policy (DEP) for each SharePoint Online and OneDrive for Business geo</span></span>

<span data-ttu-id="827eb-412">DEP를 Azure Key Vault에 저장된 키 집합과 연결합니다.</span><span class="sxs-lookup"><span data-stu-id="827eb-412">You associate a DEP with a set of keys stored in Azure Key Vault.</span></span> <span data-ttu-id="827eb-413">지역이라고도 하는 한 지리적 위치에 있는 모든 데이터에 DEP를 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="827eb-413">You apply a DEP to all of your data in one geographic location, also called a geo.</span></span> <span data-ttu-id="827eb-414">Office 365의 Multi-Geo 기능을 사용하는 경우 지리적당 다른 키를 사용할 수 있는 기능을 사용하여 지역당 DEP를 하나씩 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="827eb-414">If you use the multi-geo feature of Office 365, you can create one DEP per geo with the capability to use different keys per geo.</span></span> <span data-ttu-id="827eb-415">Multi-Geo를 사용하지 않는 경우 조직에서 SharePoint Online, 비즈니스용 OneDrive 및 Teams 파일에서 사용할 DEP를 하나 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="827eb-415">If you aren't using multi-geo, you can create one DEP in your organization for use with SharePoint Online, OneDrive for Business, and Teams files.</span></span> <span data-ttu-id="827eb-416">Microsoft 365는 DEP에 식별된 키를 사용하여 지리적으로 데이터를 암호화합니다.</span><span class="sxs-lookup"><span data-stu-id="827eb-416">Microsoft 365 uses the keys identified in the DEP to encrypt your data in that geo.</span></span> <span data-ttu-id="827eb-417">DEP를 만들하려면 앞서 획득한 키 자격 증명 모음 UR이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="827eb-417">To create the DEP, you need the Key Vault URIs you obtained earlier.</span></span> <span data-ttu-id="827eb-418">지침은 각 Azure Key Vault 키에 대한 [URI 얻기를](#obtain-the-uri-for-each-azure-key-vault-key) 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="827eb-418">See [Obtain the URI for each Azure Key Vault key](#obtain-the-uri-for-each-azure-key-vault-key) for instructions.</span></span>
  
<span data-ttu-id="827eb-419">기억하세요!</span><span class="sxs-lookup"><span data-stu-id="827eb-419">Remember!</span></span> <span data-ttu-id="827eb-420">DEP를 만들 때 두 개의 서로 다른 Azure Key Vault에 두 개의 키를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="827eb-420">When you create a DEP, you specify two keys in two different Azure Key Vaults.</span></span> <span data-ttu-id="827eb-421">두 개의 별도 Azure 지역에서 이러한 키를 만들어 지리적 중복을 보장합니다.</span><span class="sxs-lookup"><span data-stu-id="827eb-421">Create these keys in two separate Azure regions to ensure geo-redundancy.</span></span>
  
<span data-ttu-id="827eb-422">DEP를 만들 수 있도록 원격으로 SharePoint Online에 연결해야 Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="827eb-422">To create a DEP, you need to remotely connect to SharePoint Online by using Windows PowerShell.</span></span>
  
1. <span data-ttu-id="827eb-423">로컬 컴퓨터에서 조직에서 전역 관리자 권한이 있는 직장 또는 학교 계정을 사용하여 [SharePoint Online PowerShell에 연결합니다.](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online?preserve-view=true&view=sharepoint-ps)</span><span class="sxs-lookup"><span data-stu-id="827eb-423">On your local computer, using a work or school account that has global administrator permissions in your organization, [Connect to SharePoint Online PowerShell](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online?preserve-view=true&view=sharepoint-ps).</span></span>

2. <span data-ttu-id="827eb-424">Microsoft SharePoint Online 관리 셸에서 다음과 Register-SPODataEncryptionPolicy cmdlet을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="827eb-424">In the Microsoft SharePoint Online Management Shell, run the Register-SPODataEncryptionPolicy cmdlet as follows:</span></span>

   ```powershell
   Register-SPODataEncryptionPolicy -Identity <adminSiteCollectionURL> -PrimaryKeyVaultName <PrimaryKeyVaultName> -PrimaryKeyName <PrimaryKeyName> -PrimaryKeyVersion <PrimaryKeyVersion> -SecondaryKeyVaultName <SecondaryKeyVaultName> -SecondaryKeyName <SecondaryKeyName> -SecondaryKeyVersion <SecondaryKeyVersion>
   ```

   <span data-ttu-id="827eb-425">예제:</span><span class="sxs-lookup"><span data-stu-id="827eb-425">Example:</span></span>
  
   ```powershell
   Register-SPODataEncryptionPolicy -Identity https://contoso.sharepoint.com -PrimaryKeyVaultName 'stageRG3vault' -PrimaryKeyName 'SPKey3' -PrimaryKeyVersion 'f635a23bd4a44b9996ff6aadd88d42ba' -SecondaryKeyVaultName 'stageRG5vault' -SecondaryKeyName 'SPKey5' -SecondaryKeyVersion '2b3e8f1d754f438dacdec1f0945f251a’
   ```

   <span data-ttu-id="827eb-426">DEP를 등록하면 지리적 데이터에 대한 암호화가 시작됩니다.</span><span class="sxs-lookup"><span data-stu-id="827eb-426">When you register the DEP, encryption begins on the data in the geo.</span></span> <span data-ttu-id="827eb-427">암호화에는 시간이 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="827eb-427">Encryption can take some time.</span></span> <span data-ttu-id="827eb-428">이 매개 변수를 사용하는 데 대한 자세한 내용은 [Register-SPODataEncryptionPolicy를 참조하세요.](/powershell/module/sharepoint-online/register-spodataencryptionpolicy?preserve-view=true&view=sharepoint-ps)</span><span class="sxs-lookup"><span data-stu-id="827eb-428">For more information on using this parameter, see [Register-SPODataEncryptionPolicy](/powershell/module/sharepoint-online/register-spodataencryptionpolicy?preserve-view=true&view=sharepoint-ps).</span></span>

### <a name="validate-file-encryption"></a><span data-ttu-id="827eb-429">파일 암호화 유효성 검사</span><span class="sxs-lookup"><span data-stu-id="827eb-429">Validate file encryption</span></span>

 <span data-ttu-id="827eb-430">SharePoint Online, 비즈니스용 OneDrive 및 Teams 파일의 암호화 유효성을 검사하려면 [SharePoint Online PowerShell에](/powershell/exchange/connect-to-exchange-online-powershell)연결한 다음 Get-SPODataEncryptionPolicy cmdlet을 사용하여 테넌트의 상태를 검사합니다.</span><span class="sxs-lookup"><span data-stu-id="827eb-430">To validate encryption of SharePoint Online, OneDrive for Business, and Teams files, [connect to SharePoint Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell), and then use the Get-SPODataEncryptionPolicy cmdlet to check the status of your tenant.</span></span> <span data-ttu-id="827eb-431">_고객 키_ 암호화를 사용하도록  설정하고 모든 사이트의 모든 파일이 암호화된 경우 State 속성은 등록된 값을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="827eb-431">The _State_ property returns a value of **registered** if Customer Key encryption is enabled and all files in all sites have been encrypted.</span></span> <span data-ttu-id="827eb-432">암호화가 아직 진행 중이면 이 cmdlet은 등록 값을 **반환합니다.**</span><span class="sxs-lookup"><span data-stu-id="827eb-432">If encryption is still in progress, this cmdlet returns a value of **registering**.</span></span>

## <a name="related-articles"></a><span data-ttu-id="827eb-433">관련 문서</span><span class="sxs-lookup"><span data-stu-id="827eb-433">Related articles</span></span>

- [<span data-ttu-id="827eb-434">고객 키를 사용한 서비스 암호화</span><span class="sxs-lookup"><span data-stu-id="827eb-434">Service encryption with Customer Key</span></span>](customer-key-overview.md)

- [<span data-ttu-id="827eb-435">고객 키 관리</span><span class="sxs-lookup"><span data-stu-id="827eb-435">Manage Customer Key</span></span>](customer-key-manage.md)

- [<span data-ttu-id="827eb-436">고객 키 또는 가용성 키 롤 또는 회전</span><span class="sxs-lookup"><span data-stu-id="827eb-436">Roll or rotate a Customer Key or an availability key</span></span>](customer-key-availability-key-roll.md)

- [<span data-ttu-id="827eb-437">가용성 키에 대해 자세히 알아보기</span><span class="sxs-lookup"><span data-stu-id="827eb-437">Learn about the availability key</span></span>](customer-key-availability-key-understand.md)

- [<span data-ttu-id="827eb-438">서비스 암호화</span><span class="sxs-lookup"><span data-stu-id="827eb-438">Service Encryption</span></span>](office-365-service-encryption.md)