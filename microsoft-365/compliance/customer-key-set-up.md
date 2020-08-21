---
title: 고객 키 설정
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
description: Exchange Online, 비즈니스용 Skype, SharePoint Online, 비즈니스용 OneDrive 및 Teams 파일에 대해 Microsoft 365 고객 키를 설정하는 방법을 알아보세요.
ms.openlocfilehash: 87c18c1695d2963fc8a0c064d34d2b6cdc14199c
ms.sourcegitcommit: 260bbb93bbda62db9e88c021ccccfa75ac39a32e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/21/2020
ms.locfileid: "46845836"
---
# <a name="set-up-customer-key"></a><span data-ttu-id="6c7a9-103">고객 키 설정</span><span class="sxs-lookup"><span data-stu-id="6c7a9-103">Set up Customer Key</span></span>

<span data-ttu-id="6c7a9-104">고객 키를 사용하여 조직의 암호화 키를 제어하고 Microsoft365를 구성 및 사용하여 Microsoft의 데이터 센터의 미사용 데이터를 암호화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6c7a9-104">With Customer Key, you control your organization's encryption keys and then configure Microsoft 365 to use them to encrypt your data at rest in Microsoft's data centers.</span></span> <span data-ttu-id="6c7a9-105">즉, 고객 키를 사용하면 고객이 키를 사용하여 속한 암호화 계층을 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6c7a9-105">In other words, Customer Key allows customers to add a layer of encryption that belongs to them, with their keys.</span></span> <span data-ttu-id="6c7a9-106">미사용 데이터에는 SharePoint Online 및 비즈니스용 OneDrive에 저장되어 있는 사서함과 파일에 저장된 Exchange Online 및 비즈니스용 Skype의 데이터를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="6c7a9-106">Data at rest includes data from Exchange Online and Skype for Business that is stored in mailboxes and files that are stored in SharePoint Online and OneDrive for Business.</span></span>

<span data-ttu-id="6c7a9-107">Office 365에 대한 고객 키를 사용하려면 먼저 Azure를 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6c7a9-107">You must set up Azure before you can use Customer Key for Office 365.</span></span> <span data-ttu-id="6c7a9-108">이 항목에서는 필수 Azure 리소스를 만들고 구성하고 Office 365에서 고객 키를 설정하는 단계를 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="6c7a9-108">This topic describes the steps you need to follow to create and configure the required Azure resources and then provides the steps for setting up Customer Key in Office 365.</span></span> <span data-ttu-id="6c7a9-109">Azure 설정을 완료한 후 조직의 사서함 및 파일에 할당할 정책과 어떤 키를 결정합니다.</span><span class="sxs-lookup"><span data-stu-id="6c7a9-109">After you have completed Azure setup, you determine which policy, and therefore, which keys, to assign to mailboxes and files in your organization.</span></span> <span data-ttu-id="6c7a9-110">정책을 할당하지 않은 사서함과 파일은 Microsoft에서 제어 및 관리하는 암호화 정책을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="6c7a9-110">Mailboxes and files for which you don't assign a policy will use encryption policies that are controlled and managed by Microsoft.</span></span> <span data-ttu-id="6c7a9-111">고객 키 또는 일반 개요에 대한 자세한 내용은 [Office 365의 고객 키를 사용한 서비스 암호화를 참조하세요.](customer-key-overview.md)</span><span class="sxs-lookup"><span data-stu-id="6c7a9-111">For more information about Customer Key, or for a general overview, see [Service encryption with Customer Key in Office 365](customer-key-overview.md).</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="6c7a9-112">이 항목의 모범 사례를 따르는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="6c7a9-112">We strongly recommend that you follow the best practices in this topic.</span></span> <span data-ttu-id="6c7a9-113">**TIP** 및 IMPORTANT라고 **합니다.**</span><span class="sxs-lookup"><span data-stu-id="6c7a9-113">These are called out as **TIP** and **IMPORTANT**.</span></span> <span data-ttu-id="6c7a9-114">고객 키를 사용하면 전체 조직만큼 범위를 가할 수 있는 루트 암호화 키를 제어할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6c7a9-114">Customer Key gives you control over root encryption keys whose scope can be as large as your entire organization.</span></span> <span data-ttu-id="6c7a9-115">다시 말해 이러한 키를 사용한 실수로 발생하는 실수로 인해 광범위한 영향을 미치고 데이터가 중단되거나 해지할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6c7a9-115">This means that mistakes made with these keys can have a broad impact and may result in service interruptions or irrevocable loss of your data.</span></span>
  
## <a name="before-you-set-up-customer-key"></a><span data-ttu-id="6c7a9-116">고객 키 설정 전</span><span class="sxs-lookup"><span data-stu-id="6c7a9-116">Before you set up Customer Key</span></span>

<span data-ttu-id="6c7a9-117">시작하기 전에 조직에 적합한 라이선스가 제공되었는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="6c7a9-117">Before you get started, ensure that you have the appropriate licensing for your organization.</span></span> <span data-ttu-id="6c7a9-118">Microsoft 365의 고객 키는 Office 365 E5 또는 고급 규정 준수 SKU에서 제공됩니다.</span><span class="sxs-lookup"><span data-stu-id="6c7a9-118">Customer Key in Microsoft 365 is offered in Office 365 E5 or the Advanced Compliance SKU.</span></span> <span data-ttu-id="6c7a9-119">이 항목의 개념과 절차를 이해하려면 Azure [Key Vault 설명서를 검토합니다.](https://docs.microsoft.com/azure/key-vault/)</span><span class="sxs-lookup"><span data-stu-id="6c7a9-119">To understand the concepts and procedures in this topic, review the [Azure Key Vault](https://docs.microsoft.com/azure/key-vault/) documentation.</span></span> <span data-ttu-id="6c7a9-120">또한 Azure에서 사용되는 용어(예: 테넌트)에 익숙해지도록 [합니다.](https://docs.microsoft.com/previous-versions/azure/azure-services/jj573650(v=azure.100))</span><span class="sxs-lookup"><span data-stu-id="6c7a9-120">Also, become familiar with the terms used in Azure, for example, [tenant](https://docs.microsoft.com/previous-versions/azure/azure-services/jj573650(v=azure.100)).</span></span>

<span data-ttu-id="6c7a9-121">FastTrack은 고객 키를 등록하는 데 사용되는 필요한 테넌트 및 서비스 구성 정보를 수집하는 데만 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="6c7a9-121">FastTrack is only used to collect the required tenant and service configuration information used to register for Customer Key.</span></span> <span data-ttu-id="6c7a9-122">고객 키 제안은 FastTrack을 통해 게시되므로 편리하면서와 파트너가 동일한 방법을 사용하여 필요한 정보를 제출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6c7a9-122">The Customer Key Offers are published via FastTrack so that it is convenient for you and our partners to submit the required information using the same method.</span></span> <span data-ttu-id="6c7a9-123">FastTrack은 판매에서 제공하는 데이터를 보관하기도 한편 편리합니다.</span><span class="sxs-lookup"><span data-stu-id="6c7a9-123">FastTrack also makes it easy to archive the data that you provide in the Offer.</span></span>
  
<span data-ttu-id="6c7a9-124">설명서 이후에 추가적인 지원이 필요한 경우에는 MCS(Microsoft Consulting Services), PFE(프리미어 필드 엔지니어링) 또는 Microsoft 파트너에게 도울수가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6c7a9-124">If you need additional support beyond the documentation, contact Microsoft Consulting Services (MCS), Premier Field Engineering (PFE), or a Microsoft partner for assistance.</span></span> <span data-ttu-id="6c7a9-125">설명서를 포함하여 고객 키에 대한 의견을 제공하려면 고객의 아이디어, 제안 사항 및 기술 정보를 customerkeyfeedback@microsoft.com.</span><span class="sxs-lookup"><span data-stu-id="6c7a9-125">To provide feedback on Customer Key, including the documentation, send your ideas, suggestions, and perspectives to customerkeyfeedback@microsoft.com.</span></span>
  
## <a name="overview-of-steps-to-set-up-customer-key"></a><span data-ttu-id="6c7a9-126">고객 키 설정 단계 개요</span><span class="sxs-lookup"><span data-stu-id="6c7a9-126">Overview of steps to set up Customer Key</span></span>

<span data-ttu-id="6c7a9-127">고객 키를 설정하려면 이러한 작업을 나열된 순서대로 완료합니다.</span><span class="sxs-lookup"><span data-stu-id="6c7a9-127">To set up Customer Key, complete these tasks in the listed order.</span></span> <span data-ttu-id="6c7a9-128">이 문서의 나머지 부분에서는 각 작업에 대한 자세한 지침을 제공하거나 프로세스의 각 단계에 대한 추가 정보를 연결합니다.</span><span class="sxs-lookup"><span data-stu-id="6c7a9-128">The rest of this article provides detailed instructions for each task, or links out to more information for each step in the process.</span></span>
  
<span data-ttu-id="6c7a9-129">**Azure 및 Microsoft FastTrack의 내용:**</span><span class="sxs-lookup"><span data-stu-id="6c7a9-129">**In Azure and Microsoft FastTrack:**</span></span>
  
<span data-ttu-id="6c7a9-130">Azure PowerShell에 원격으로 연결하여 이러한 작업 대부분을 완료합니다.</span><span class="sxs-lookup"><span data-stu-id="6c7a9-130">You will complete most of these tasks by remotely connecting to Azure PowerShell.</span></span> <span data-ttu-id="6c7a9-131">최상의 결과를 얻을 수 있도록 Azure PowerShell 버전 4.4.0 이상을 사용하세요.</span><span class="sxs-lookup"><span data-stu-id="6c7a9-131">For best results, use version 4.4.0 or later of Azure PowerShell.</span></span>
  
- [<span data-ttu-id="6c7a9-132">새 Azure 구독 2개를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="6c7a9-132">Create two new Azure subscriptions</span></span>](#create-two-new-azure-subscriptions)

- [<span data-ttu-id="6c7a9-133">필수 보존 기간을 사용하도록 Azure 구독 등록</span><span class="sxs-lookup"><span data-stu-id="6c7a9-133">Register Azure subscriptions to use a mandatory retention period</span></span>](#register-azure-subscriptions-to-use-a-mandatory-retention-period)

  <span data-ttu-id="6c7a9-134">등록은 일주일-5일(업무일)에 이를 걸 릴리게 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6c7a9-134">Registration can take from one to five business days.</span></span>

- [<span data-ttu-id="6c7a9-135">Office 365의 고객 키 인증 요청을 제출합니다.</span><span class="sxs-lookup"><span data-stu-id="6c7a9-135">Submit a request to activate Customer Key for Office 365</span></span>](#submit-a-request-to-activate-customer-key-for-office-365)

<span data-ttu-id="6c7a9-136">Azure 구독 2개를 만들었으면 Microsoft FastTrack 포털에서 호스트되는 웹 양식을 작성하여 적절한 고객 키 제공 요청을 제출해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6c7a9-136">Once you've created the two new Azure subscriptions, you'll need to submit the appropriate Customer Key offer request by completing a web form that is hosted in the Microsoft FastTrack portal.</span></span> <span data-ttu-id="6c7a9-137">**FastTrack 팀은 고객 키에 대한 지원을 제공하지 않습니다. Office에서는 단순히 FastTrack 포털을 사용하여 양식을 제출하고 고객 키에 대한 관련 제품을 추적하는 데 도움이 됩니다.**</span><span class="sxs-lookup"><span data-stu-id="6c7a9-137">**The FastTrack team doesn't provide assistance with Customer Key. Office simply uses the FastTrack portal to allow you to submit the form and to help us track the relevant offers for Customer Key**.</span></span>

- [<span data-ttu-id="6c7a9-138">구독마다 프리미어 Azure Key Vault 만들기</span><span class="sxs-lookup"><span data-stu-id="6c7a9-138">Create a premium Azure Key Vault in each subscription</span></span>](#create-a-premium-azure-key-vault-in-each-subscription)

- [<span data-ttu-id="6c7a9-139">각 키 상의에 사용 권한 할당</span><span class="sxs-lookup"><span data-stu-id="6c7a9-139">Assign permissions to each key vault</span></span>](#assign-permissions-to-each-key-vault)

- [<span data-ttu-id="6c7a9-140">키 취미있는 경우 소미삭제를 사용하도록 설정하고 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="6c7a9-140">Enable and then confirm soft delete on your key vaults</span></span>](#enable-and-then-confirm-soft-delete-on-your-key-vaults)

- [<span data-ttu-id="6c7a9-141">키를 만들거나 가져오는 방법으로 각 키 매개 키 변경 에키를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="6c7a9-141">Add a key to each key vault either by creating or importing a key</span></span>](#add-a-key-to-each-key-vault-either-by-creating-or-importing-a-key)

- [<span data-ttu-id="6c7a9-142">키의 복구 수준 확인</span><span class="sxs-lookup"><span data-stu-id="6c7a9-142">Check the recovery level of your keys</span></span>](#check-the-recovery-level-of-your-keys)

- [<span data-ttu-id="6c7a9-143">Azure Key Vault 백업</span><span class="sxs-lookup"><span data-stu-id="6c7a9-143">Back up Azure Key Vault</span></span>](#back-up-azure-key-vault)

- [<span data-ttu-id="6c7a9-144">Azure Key Vault 구성 설정 확인</span><span class="sxs-lookup"><span data-stu-id="6c7a9-144">Validate Azure Key Vault configuration settings</span></span>](#validate-azure-key-vault-configuration-settings)

- [<span data-ttu-id="6c7a9-145">각 Azure Key Vault 키의 URI 가져오기</span><span class="sxs-lookup"><span data-stu-id="6c7a9-145">Obtain the URI for each Azure Key Vault key</span></span>](#obtain-the-uri-for-each-azure-key-vault-key)

<span data-ttu-id="6c7a9-146">**Office 365의 경우**</span><span class="sxs-lookup"><span data-stu-id="6c7a9-146">**In Office 365:**</span></span>
  
<span data-ttu-id="6c7a9-147">Exchange Online 및 비즈니스용 Skype:</span><span class="sxs-lookup"><span data-stu-id="6c7a9-147">Exchange Online and Skype for Business:</span></span>
  
- [<span data-ttu-id="6c7a9-148">Exchange Online 및 비즈니스용 Skype에 사용할 DEP(데이터 암호화 정책) 만들기</span><span class="sxs-lookup"><span data-stu-id="6c7a9-148">Create a data encryption policy (DEP) for use with Exchange Online and Skype for Business</span></span>](#create-a-data-encryption-policy-dep-for-use-with-exchange-online-and-skype-for-business)

- [<span data-ttu-id="6c7a9-149">사서함에 DEP 할당</span><span class="sxs-lookup"><span data-stu-id="6c7a9-149">Assign a DEP to a mailbox</span></span>](#assign-a-dep-to-a-mailbox)

- [<span data-ttu-id="6c7a9-150">사서함 암호화 유효성 검사</span><span class="sxs-lookup"><span data-stu-id="6c7a9-150">Validate mailbox encryption</span></span>](#validate-mailbox-encryption)

<span data-ttu-id="6c7a9-151">SharePoint Online 및 비즈니스용 OneDrive:</span><span class="sxs-lookup"><span data-stu-id="6c7a9-151">SharePoint Online and OneDrive for Business:</span></span>
  
- [<span data-ttu-id="6c7a9-152">각 SharePoint Online 및 비즈니스용 OneDrive 지역에 대한 DEP(데이터 암호화 정책) 만들기</span><span class="sxs-lookup"><span data-stu-id="6c7a9-152">Create a data encryption policy (DEP) for each SharePoint Online and OneDrive for Business geo</span></span>](#create-a-data-encryption-policy-dep-for-each-sharepoint-online-and-onedrive-for-business-geo)

- [<span data-ttu-id="6c7a9-153">SharePoint Online, 비즈니스용 OneDrive 및 Teams 파일에 대한 파일 암호화 유효성 검사</span><span class="sxs-lookup"><span data-stu-id="6c7a9-153">Validate file encryption for SharePoint Online, OneDrive for Business, and Teams files</span></span>](#validate-file-encryption)

## <a name="complete-tasks-in-azure-key-vault-and-microsoft-fasttrack-for-customer-key"></a><span data-ttu-id="6c7a9-154">고객 키에 대한 Azure Key Vault 및 Microsoft FastTrack에서 작업 완료</span><span class="sxs-lookup"><span data-stu-id="6c7a9-154">Complete tasks in Azure Key Vault and Microsoft FastTrack for Customer Key</span></span>

<span data-ttu-id="6c7a9-155">Azure Key Vault에서 다음과 같은 작업을 완료합니다.</span><span class="sxs-lookup"><span data-stu-id="6c7a9-155">Complete these tasks in Azure Key Vault.</span></span> <span data-ttu-id="6c7a9-156">Exchange Online 및 비즈니스용 Skype에 대해 고객 키를 설정하거나 SharePoint Online, 비즈니스용 OneDrive 및 Teams 파일에 대해 설정하거나 Office 365에서 지원되는 모든 서비스에 대해 고객 키를 설정하고 있는지와 관계없이 이러한 단계를 완료해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6c7a9-156">You will need to complete these steps regardless of whether you intend to set up Customer Key for Exchange Online and Skype for Business or for SharePoint Online, OneDrive for Business, and Teams files, or for all supported services in Office 365.</span></span>
  
### <a name="create-two-new-azure-subscriptions"></a><span data-ttu-id="6c7a9-157">새 Azure 구독 2개를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="6c7a9-157">Create two new Azure subscriptions</span></span>

<span data-ttu-id="6c7a9-158">고객 키에는 두 개의 Azure 구독이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="6c7a9-158">Customer Key requires two Azure subscriptions.</span></span> <span data-ttu-id="6c7a9-159">고객 키에 사용할 새 Azure 구독을 만드는 것이 가장 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="6c7a9-159">As a best practice, Microsoft recommends that you create new Azure subscriptions for use with Customer Key.</span></span> <span data-ttu-id="6c7a9-160">Azure Key Vault 키는 동일한 AAD(Azure Active Directory) 테넌트의 응용 프로그램에 대해 권한만 부여될 수 있으며, DEP가 할당되는 조직에 사용된 것과 동일한 Azure AD 테넌트를 사용하여 새 구독을 생성해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6c7a9-160">Azure Key Vault keys can only be authorized for applications in the same Azure Active Directory (AAD) tenant, you must create the new subscriptions using the same Azure AD tenant used with your organization where the DEPs will be assigned.</span></span> <span data-ttu-id="6c7a9-161">예를 들어 조직에서 전역 관리자 권한이 있는 회사 또는 학교 계정을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="6c7a9-161">For example, using your work or school account that has global administrator privileges in your organization.</span></span> <span data-ttu-id="6c7a9-162">자세한 단계는 조직으로 [Azure에 등록을 참조하세요.](https://azure.microsoft.com/documentation/articles/sign-up-organization/)</span><span class="sxs-lookup"><span data-stu-id="6c7a9-162">For detailed steps, see [Sign up for Azure as an organization](https://azure.microsoft.com/documentation/articles/sign-up-organization/).</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="6c7a9-163">고객 키는 각 DEP(데이터 암호화 정책)에 대해 두 개의 키가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="6c7a9-163">Customer Key requires two keys for each data encryption policy (DEP).</span></span> <span data-ttu-id="6c7a9-164">이 작업을 수행하기 위해 두 개의 Azure 구독을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="6c7a9-164">In order to achieve this, you must create two Azure subscriptions.</span></span> <span data-ttu-id="6c7a9-165">모범 사례에 따르면 조직에 있는 별도의 구성원이 각 구독에서 하나의 키를 구성하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="6c7a9-165">As a best practice, Microsoft recommends that you have separate members of your organization configure one key in each subscription.</span></span> <span data-ttu-id="6c7a9-166">또한 이러한 Azure 구독은 Office 365의 암호화 키를 관리하는 용도로만 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6c7a9-166">In addition, these Azure subscriptions should only be used to administer encryption keys for Office 365.</span></span> <span data-ttu-id="6c7a9-167">이렇게 하면 운영자 중 한 명이 실수로 또는 의도적으로 삭제하거나 악의적으로 삭제하거나 관리하는 경우 조직을 보호할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6c7a9-167">This protects your organization in case one of your operators accidentally, intentionally, or maliciously deletes or otherwise mismanages the keys for which they are responsible.</span></span> <br/> <span data-ttu-id="6c7a9-168">고객 키와 함께 사용하기 위해 Azure Key Vault 리소스를 관리하는 데만 사용되는 새 Azure 구독을 설정하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="6c7a9-168">We recommend that you set up new Azure subscriptions that are solely used for managing Azure Key Vault resources for use with Customer Key.</span></span> <span data-ttu-id="6c7a9-169">조직을 위해 만들 수 있는 Azure 구독 수에는 실용성이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="6c7a9-169">There is no practical limit to the number of Azure subscriptions that you can create for your organization.</span></span> <span data-ttu-id="6c7a9-170">이러한 모범 사례를 따르면 고객 키에서 사용되는 리소스를 관리하는 동시에 인간 오류의 영향을 최소화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6c7a9-170">Following these best practices will minimize the impact of human error while helping to manage the resources used by Customer Key.</span></span>
  
### <a name="submit-a-request-to-activate-customer-key-for-office-365"></a><span data-ttu-id="6c7a9-171">Office 365의 고객 키 인증 요청을 제출합니다.</span><span class="sxs-lookup"><span data-stu-id="6c7a9-171">Submit a request to activate Customer Key for Office 365</span></span>

<span data-ttu-id="6c7a9-172">Azure 단계를 완료한 후 Microsoft FastTrack 포털에서 제품 요청을 [제출해야 합니다.](https://fasttrack.microsoft.com/)</span><span class="sxs-lookup"><span data-stu-id="6c7a9-172">Once you've completed the Azure steps, you'll need to submit an offer request in the [Microsoft FastTrack portal](https://fasttrack.microsoft.com/).</span></span> <span data-ttu-id="6c7a9-173">FastTrack 웹 포털을 통해 요청을 제출하면 Microsoft는 Azure Key Vault 구성 데이터와 제공한 연락처 정보를 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="6c7a9-173">Once you have submitted a request through the FastTrack web portal, Microsoft verifies the Azure Key Vault configuration data and contact information you provided.</span></span> <span data-ttu-id="6c7a9-174">조직의 권한이 있는 관리자와 관련하여 제품 양식에서 선택한 사항은 고객 키 등록을 완료하는 데 중요하며 필수 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="6c7a9-174">The selections that you make in the offer form regarding the authorized officers of your organization is critical and necessary for completion of Customer Key registration.</span></span> <span data-ttu-id="6c7a9-175">양식에서 선택한 조직의 관리자는 고객 키 데이터 암호화 정책과 함께 사용되는 모든 키를 해지 및 삭제하기 위한 요청의 신뢰성을 보보보하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="6c7a9-175">The officers of your organization that you select in the form will be the used to ensure the authenticity of any request to revoke and destroy all keys used with a Customer Key data encryption policy.</span></span> <span data-ttu-id="6c7a9-176">Exchange Online 및 비즈니스용 Skype 범위에 대한 고객 키를 활성화하려면 이 단계를 한 번 수행하고 SharePoint Online 및 비즈니스용 OneDrive에 대한 고객 키를 활성화하려면 이 단계를 한 번 수행해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6c7a9-176">You'll need to do this step once to activate Customer Key for Exchange Online and Skype for Business coverage and a second time to activate Customer Key for SharePoint Online and OneDrive for Business.</span></span>
  
<span data-ttu-id="6c7a9-177">고객 키를 활성화하기 위해 제품을 제출하려면 다음 단계를 완료하세요.</span><span class="sxs-lookup"><span data-stu-id="6c7a9-177">To submit an offer to activate Customer Key, complete these steps:</span></span>
  
1. <span data-ttu-id="6c7a9-178">조직에서 전역 관리자 권한을 가지고 있는 회사 또는 학교 계정을 사용하여 [Microsoft FastTrack 포털에 로그인합니다.](https://fasttrack.microsoft.com/)</span><span class="sxs-lookup"><span data-stu-id="6c7a9-178">Using a work or school account that has global administrator permissions in your organization, log in to the [Microsoft FastTrack portal](https://fasttrack.microsoft.com/).</span></span>

2. <span data-ttu-id="6c7a9-179">로그인한 후 대시보드를 **찾습니다.**</span><span class="sxs-lookup"><span data-stu-id="6c7a9-179">Once you're logged in, browse to the **Dashboard**.</span></span>

3. <span data-ttu-id="6c7a9-180">탐색 **모음에서** 배포를 **선택하거나** **정보 카드의 모든** 배포 **리소스보기를** 선택한 다음 현재 제품 목록을 검토합니다.</span><span class="sxs-lookup"><span data-stu-id="6c7a9-180">Choose **Deploy** from the navigation bar **OR** select **View all deployment resources** on the **Deploy** information card, and review the list of current offers.</span></span>

4. <span data-ttu-id="6c7a9-181">사용자에게 적용되는 제품의 정보 카드를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="6c7a9-181">Choose the information card for the offer that applies to you:</span></span>

   - <span data-ttu-id="6c7a9-182">**Exchange Online 및 비즈니스용 Skype:** Exchange **Online 서비스용 암호화 키 요청 도움말을** 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="6c7a9-182">**Exchange Online and Skype for Business:** Choose the **Request encryption key help for Exchange online** offer.</span></span>

   - <span data-ttu-id="6c7a9-183">**SharePoint Online, OneDrive 및 Teams 파일:** Choose the **Request encryption key help for Sharepoint and OneDrive** offer.</span><span class="sxs-lookup"><span data-stu-id="6c7a9-183">**SharePoint Online, OneDrive, and Teams files:** Choose the **Request encryption key help for Sharepoint and OneDrive** offer.</span></span>

5. <span data-ttu-id="6c7a9-184">제품 세부 정보를 검토한 후 **계속 2단계를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="6c7a9-184">Once you've reviewed the offer details, choose **Continue to step 2**.</span></span>

6. <span data-ttu-id="6c7a9-185">적용 가능한 모든 세부 정보 및 요청된 정보를 제품 양식에 작성합니다.</span><span class="sxs-lookup"><span data-stu-id="6c7a9-185">Fill out all applicable details and requested information on the offer form.</span></span> <span data-ttu-id="6c7a9-186">조직 관리자가 암호화 키와 데이터의 영구 적독 및 영구 소파 대독을 승인할 권한을 부여하려는 특정 사용자의 선택에 특히 주의해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6c7a9-186">Pay particular attention to your selections for which officers of your organization you want to authorize to approve the permanent and irreversible destruction of encryption keys and data.</span></span> <span data-ttu-id="6c7a9-187">양식을 완료한 후 전송을 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="6c7a9-187">Once you've completed the form, choose **Submit**.</span></span>

### <a name="register-azure-subscriptions-to-use-a-mandatory-retention-period"></a><span data-ttu-id="6c7a9-188">필수 보존 기간을 사용하도록 Azure 구독 등록</span><span class="sxs-lookup"><span data-stu-id="6c7a9-188">Register Azure subscriptions to use a mandatory retention period</span></span>

<span data-ttu-id="6c7a9-189">루트 암호화 키가 일시적으로 또는 영구적으로 손실되면 부상이 발생하거나 서비스 작업에 치명적이 생길 수 있기 어려우며 데이터 손실이 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6c7a9-189">The temporary or permanent loss of root encryption keys can be very disruptive or even catastrophic to service operation and can result in data loss.</span></span> <span data-ttu-id="6c7a9-190">따라서 고객 키와 함께 사용되는 리소스는 강력한 보호가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="6c7a9-190">For this reason, the resources used with Customer Key require strong protection.</span></span> <span data-ttu-id="6c7a9-191">고객 키와 함께 사용되는 모든 Azure 리소스는 기본 구성 이후 보호 메커니즘을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="6c7a9-191">All the Azure resources that are used with Customer Key offer protection mechanisms beyond the default configuration.</span></span> <span data-ttu-id="6c7a9-192">Azure 구독은 즉시 취소할 수 없는 취소를 방지하는 방식으로 태그를 지정하거나 등록할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6c7a9-192">Azure subscriptions can be tagged or registered in a way that will prevent immediate and irrevocable cancellation.</span></span> <span data-ttu-id="6c7a9-193">이것을 필수 보존 기간에 등록하는 것을 의미합니다.</span><span class="sxs-lookup"><span data-stu-id="6c7a9-193">This is referred to as registering for a mandatory retention period.</span></span> <span data-ttu-id="6c7a9-194">필수 보존 기간 동안 Azure 구독을 등록하는 데 필요한 단계는 Microsoft 365 팀과 공동의 공동 작업이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="6c7a9-194">The steps required to register Azure subscriptions for a mandatory retention period require collaboration with the Microsoft 365 team.</span></span> <span data-ttu-id="6c7a9-195">이 프로세스는 업무 일주일 1일에서 5일까지 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6c7a9-195">This process can take from one to five business days.</span></span> <span data-ttu-id="6c7a9-196">이전에는 이 작업을 "취소 안 함"이라고도 했습니다.</span><span class="sxs-lookup"><span data-stu-id="6c7a9-196">Previously, this was sometimes referred to as "Do Not Cancel".</span></span>
  
<span data-ttu-id="6c7a9-197">Microsoft 365 팀에 연락하기 전에 고객 키와 함께 사용하는 각 Azure 구독에 대해 다음 단계를 수행해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6c7a9-197">Before contacting the Microsoft 365 team, you must perform the following steps for each Azure subscription that you use with Customer Key.</span></span> <span data-ttu-id="6c7a9-198">시작하기 전에 [Azure PowerShell Az 모듈이](https://docs.microsoft.com/powershell/azure/new-azureps-module-az) 설치되어 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="6c7a9-198">Ensure that you have the [Azure PowerShell Az](https://docs.microsoft.com/powershell/azure/new-azureps-module-az) module installed before you start.</span></span>
  
1. <span data-ttu-id="6c7a9-199">Azure PowerShell을 사용하여 로그인합니다.</span><span class="sxs-lookup"><span data-stu-id="6c7a9-199">Sign in with Azure PowerShell.</span></span> <span data-ttu-id="6c7a9-200">지침은 Azure [PowerShell로 로그인을 참조하세요.](https://docs.microsoft.com/powershell/azure/authenticate-azureps)</span><span class="sxs-lookup"><span data-stu-id="6c7a9-200">For instructions, see [Sign in with Azure PowerShell](https://docs.microsoft.com/powershell/azure/authenticate-azureps).</span></span>

2. <span data-ttu-id="6c7a9-201">Register-AzProviderFeature cmdlet를 실행하여 필수 보존 기간을 사용하도록 구독을 등록합니다.</span><span class="sxs-lookup"><span data-stu-id="6c7a9-201">Run the Register-AzProviderFeature cmdlet to register your subscriptions to use a mandatory retention period.</span></span> <span data-ttu-id="6c7a9-202">각 구독에 대해 이 작업을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="6c7a9-202">Perform this action for each subscription.</span></span>

   ```powershell
   Set-AzContext -SubscriptionId <SubscriptionId>
   Register-AzProviderFeature -FeatureName mandatoryRetentionPeriodEnabled -ProviderNamespace Microsoft.Resources
   ```

3. <span data-ttu-id="6c7a9-203">프로세스를 완료하려면 Microsoft에 문의하세요.</span><span class="sxs-lookup"><span data-stu-id="6c7a9-203">Contact Microsoft to have the process finalized.</span></span> <span data-ttu-id="6c7a9-204">SharePoint 및 비즈니스용 OneDrive 팀의 경우 다음 [spock@microsoft.com.](mailto:spock@microsoft.com)</span><span class="sxs-lookup"><span data-stu-id="6c7a9-204">For the SharePoint and OneDrive for Business team, contact [spock@microsoft.com](mailto:spock@microsoft.com).</span></span> <span data-ttu-id="6c7a9-205">Exchange Online 및 비즈니스용 Skype에 대 한 [exock@microsoft.com.](mailto:exock@microsoft.com)</span><span class="sxs-lookup"><span data-stu-id="6c7a9-205">For Exchange Online and Skype for Business, contact [exock@microsoft.com](mailto:exock@microsoft.com).</span></span> <span data-ttu-id="6c7a9-206">전자 메일에 다음을 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="6c7a9-206">Include the following in your email:</span></span>

   <span data-ttu-id="6c7a9-207">**제목**: 다음에 대한 고객 키 \<*Your tenant's fully-qualified domain name*\></span><span class="sxs-lookup"><span data-stu-id="6c7a9-207">**Subject**: Customer Key for \<*Your tenant's fully-qualified domain name*\></span></span>

   <span data-ttu-id="6c7a9-208">**본문:** 필수 보존 기간을 마무리할 수 있는 구독 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="6c7a9-208">**Body**: Subscription IDs for which you want to have the mandatory retention period finalized.</span></span>
   <span data-ttu-id="6c7a9-209">각 구독에 대한 Get-AzProviderFeature의 출력.</span><span class="sxs-lookup"><span data-stu-id="6c7a9-209">The output of Get-AzProviderFeature for each subscription.</span></span>

   <span data-ttu-id="6c7a9-210">Microsoft가 필수 보존 기간을 사용하도록 구독을 등록하고(확인)되었음을 계속 통보한 후 이 프로세스 완료를 위한 SLA(서비스 수준 계약)는 영업일로 5일로 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6c7a9-210">The Service Level Agreement (SLA) for completion of this process is five business days once Microsoft has been notified (and verified) that you have registered your subscriptions to use a mandatory retention period.</span></span>

4. <span data-ttu-id="6c7a9-211">Microsoft로부터 알림을 받으면 다음과 같이 Get-AzProviderFeature 명령을 실행하여 등록 상태를 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="6c7a9-211">Once you receive notification from Microsoft that registration is complete, verify the status of your registration by running the Get-AzProviderFeature command as follows.</span></span> <span data-ttu-id="6c7a9-212">verified이면 Get-AzProviderFeature 명령이 등록 상태 **속성에 등록됨** **값을 반환합니다.**</span><span class="sxs-lookup"><span data-stu-id="6c7a9-212">If verified, the Get-AzProviderFeature command returns a value of **Registered** for the **Registration State** property.</span></span> <span data-ttu-id="6c7a9-213">각 구독에 대해 이 작업을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="6c7a9-213">Perform this action for each subscription.</span></span>

   ```powershell
   Set-AzContext -SubscriptionId <SubscriptionId>
   Get-AzProviderFeature -ProviderNamespace Microsoft.Resources -FeatureName mandatoryRetentionPeriodEnabled
   ```

5. <span data-ttu-id="6c7a9-214">프로세스를 완료하려면 Register-AzResourceProvider 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="6c7a9-214">To complete the process, run the Register-AzResourceProvider command.</span></span> <span data-ttu-id="6c7a9-215">각 구독에 대해 이 작업을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="6c7a9-215">Perform this action for each subscription.</span></span>

   ```powershell
   Set-AzContext -SubscriptionId <SubscriptionId>
   Register-AzResourceProvider -ProviderNamespace Microsoft.KeyVault
   ```

### <a name="create-a-premium-azure-key-vault-in-each-subscription"></a><span data-ttu-id="6c7a9-216">구독마다 프리미어 Azure Key Vault 만들기</span><span class="sxs-lookup"><span data-stu-id="6c7a9-216">Create a premium Azure Key Vault in each subscription</span></span>

<span data-ttu-id="6c7a9-217">핵심 소프트웨어를 만드는 단계는 Azure Key [Vault](https://azure.microsoft.com/documentation/articles/key-vault-get-started/)시작에 문서화되어 있으며 이는 Azure PowerShell 설치 및 실행, Azure 구독에 연결, 리소스 그룹 만들기 및 해당 리소스 그룹에 키 상이 판결생성을 안내합니다.</span><span class="sxs-lookup"><span data-stu-id="6c7a9-217">The steps to create a key vault are documented in [Getting Started with Azure Key Vault](https://azure.microsoft.com/documentation/articles/key-vault-get-started/), which guides you through installing and launching Azure PowerShell, connecting to your Azure subscription, creating a resource group, and creating a key vault in that resource group.</span></span>
  
<span data-ttu-id="6c7a9-218">키 상이스를 만들 때는 Standard 또는 Premium 중 SKU를 선택해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6c7a9-218">When you create a key vault, you must choose a SKU: either Standard or Premium.</span></span> <span data-ttu-id="6c7a9-219">Standard SKU를 사용하면 소프트웨어를 통해 Azure Key Vault 키를 보호할 수 있습니다. HSM(하드웨어 보안 모듈) 키 보호가 없고, Premium SKU는 키 Vault 키를 보호하는 데 HSM을 사용할 수 있도록 해줍니다.</span><span class="sxs-lookup"><span data-stu-id="6c7a9-219">The Standard SKU allows Azure Key Vault keys to be protected with software - there is no Hardware Security Module (HSM) key protection - and the Premium SKU allows the use of HSMs for protection of Key Vault keys.</span></span> <span data-ttu-id="6c7a9-220">고객 키는 SKU를 사용하는 키 상취를 수락합니다. 하지만 Microsoft는 개발자가 Premium SKU만 사용하도록 권장합니다.</span><span class="sxs-lookup"><span data-stu-id="6c7a9-220">Customer Key accepts key vaults that use either SKU, though Microsoft strongly recommends that you use only the Premium SKU.</span></span> <span data-ttu-id="6c7a9-221">키 가어있는 연산 비용은 동일합니다. 따라서 유일한 비용 차이는 각 HSM 보호 키의 월 순위와 같습니다.</span><span class="sxs-lookup"><span data-stu-id="6c7a9-221">The cost of operations with keys of either type is the same, so the only difference in cost is the cost per month for each HSM-protected key.</span></span> <span data-ttu-id="6c7a9-222">자세한 [내용은 Key Vault 가격 책정을](https://azure.microsoft.com/pricing/details/key-vault/) 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="6c7a9-222">See [Key Vault pricing](https://azure.microsoft.com/pricing/details/key-vault/) for details.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="6c7a9-223">프로덕션 데이터에 Premium SKU 키 vaults 및 HSM 보호 된 키를 사용하고 테스트 및 유효성 검사용으로는 표준 SKU 키 오류 및 키만 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="6c7a9-223">Use the Premium SKU key vaults and HSM-protected keys for production data, and only use Standard SKU key vaults and keys for testing and validation purposes.</span></span>
  
<span data-ttu-id="6c7a9-224">고객 키를 사용할 각 Microsoft 365 서비스에 대해, 만들었은 두 개의 각 Azure 구독에 키 매개 변수를 만드세요.</span><span class="sxs-lookup"><span data-stu-id="6c7a9-224">For each Microsoft 365 service with which you will use Customer Key, create a key vault in each of the two Azure subscriptions that you created.</span></span> <span data-ttu-id="6c7a9-225">예를 들어 Exchange Online과 비즈니스용 Skype 전용 또는 SharePoint Online 및 비즈니스용 OneDrive 전용에 한합니다. 하지만 한 쌍의 오류만 만들게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6c7a9-225">For example, for Exchange Online and Skype for Business only or SharePoint Online and OneDrive for Business only, you will create only one pair of vaults.</span></span> <span data-ttu-id="6c7a9-226">Exchange Online 및 SharePoint Online 모두에 대한 고객 키를 사용하려면 두 쌍의 키 오류를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="6c7a9-226">To enable Customer Key for both Exchange Online and SharePoint Online, you will create two pairs of key vaults.</span></span>
  
<span data-ttu-id="6c7a9-227">취자를 연결할 데이터 암호화 정책의 용도를 반영하는 키 저장소에 대한 명명 규칙을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="6c7a9-227">Use a naming convention for key vaults that reflects the intended use of the data encryption policy with which you will associate the vaults.</span></span> <span data-ttu-id="6c7a9-228">명명 규칙 권장 사항은 아래 모범 사례 섹션을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="6c7a9-228">See the Best Practices section below for naming convention recommendations.</span></span>
  
<span data-ttu-id="6c7a9-229">각 데이터 암호화 정책에 대해 쌍으로 연결된 설치 모음을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="6c7a9-229">Create a separate, paired set of vaults for each data encryption policy.</span></span> <span data-ttu-id="6c7a9-230">Exchange Online의 경우 정책을 사서함에 할당할 때 데이터 암호화 정책의 범위가 선택됩니다.</span><span class="sxs-lookup"><span data-stu-id="6c7a9-230">For Exchange Online, the scope of a data encryption policy is chosen by you when you assign the policy to mailbox.</span></span> <span data-ttu-id="6c7a9-231">사서함에는 정책이 하나만 할당될 수 있습니다. 하나의 정책에 여러 정책을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6c7a9-231">A mailbox can have only one policy assigned, and you can create up to fifty policies.</span></span> <span data-ttu-id="6c7a9-232">SharePoint Online의 경우 정책 범위는 지리적 위치 또는 지리적 위치에 있는 조직 내의 모든 _데이터입니다._</span><span class="sxs-lookup"><span data-stu-id="6c7a9-232">For SharePoint Online the scope of a policy is all of the data within an organization in a geographic location, or _geo_.</span></span>

<span data-ttu-id="6c7a9-233">키 자격함을 만들려면 키 자격이 없지만 저장소 용량이(매우 작은) 및 Key Vault 로깅(사용하도록 설정된 경우)이 하므로 이러한 그룹도 만들면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6c7a9-233">The creation of key vaults also requires the creation of Azure resource groups, since key vaults need storage capacity (though very small) and Key Vault logging, if enabled, also generates stored data.</span></span> <span data-ttu-id="6c7a9-234">Microsoft는 별도의 관리자를 사용하여 모든 관련된 고객 키 리소스를 관리하는 관리자 집합에 따라 각 리소스 그룹을 관리하는 것이 좋다는 권장 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="6c7a9-234">As a best practice Microsoft recommends using separate administrators to manage each resource group, with the administration aligned with the set of administrators that will manage all related Customer Key resources.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="6c7a9-235">가용성을 최대화하려면 키 저장소가 Microsoft 365 서비스와 가까이 지역에 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6c7a9-235">To maximize availability, your key vaults should be in regions close to your Microsoft 365 service.</span></span> <span data-ttu-id="6c7a9-236">예를 들어 Exchange Online 조직이 북미에 있는 경우 키 음성을 북미에 배치합니다.</span><span class="sxs-lookup"><span data-stu-id="6c7a9-236">For example, if your Exchange Online organization is in North America, place your key vaults in North America.</span></span> <span data-ttu-id="6c7a9-237">Exchange Online 조직이 유럽에 있는 경우 유럽에 주요 vault를 배치합니다.</span><span class="sxs-lookup"><span data-stu-id="6c7a9-237">If your Exchange Online organization is in Europe, place your key vaults in Europe.</span></span><br/><span data-ttu-id="6c7a9-238">키 매개 변수로 일반적인 접두사 사용: 여기에는 키 vault와 키(예: 모음이 북미에 위치할 Contoso SharePoint 서비스의 경우)의 사용 및 범위를 간략하게 포함할 수 있습니다. 이름 쌍은 Contoso-O365SP-NA-VaultA1 및 Contoso-O365SP-NA-VaultA2입니다.</span><span class="sxs-lookup"><span data-stu-id="6c7a9-238">Use a common prefix for key vaults, and include an abbreviation of the use and scope of the key vault and keys (e.g., for the Contoso SharePoint service where the vaults will be located in North America, a possible pair of names is Contoso-O365SP-NA-VaultA1 and Contoso-O365SP-NA-VaultA2.</span></span> <span data-ttu-id="6c7a9-239">Vault 이름은 Azure 내에서 전역적으로 고유문자열이므로, 원하는 이름은 다른 Azure 고객이 이미 클레임하는 경우 원하는 이름의 변형을 사용해 보아해야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6c7a9-239">Vault names are globally unique strings within Azure, so you may need to try variations of your desired names in case the desired names are already claimed by other Azure customers.</span></span> <span data-ttu-id="6c7a9-240">2017년 7월 부과 이름을 변경할 수 없습니다. 따라서 설치에 대한 서면을 작성하고 두 번째 사람을 사용하여 계획이 올바르게 실행되었는지 확인하는 것이 가장 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="6c7a9-240">As of July 2017 vault names cannot be changed, so a best practice is to have a written plan for setup and use a second person to verify the plan is executed correctly.</span></span><br/><span data-ttu-id="6c7a9-241">가능하면 페어링되지 않은 영역에서 휴가를 만드세요.</span><span class="sxs-lookup"><span data-stu-id="6c7a9-241">If possible, create your vaults in non-paired regions.</span></span> <span data-ttu-id="6c7a9-242">쌍이 있는 Azure 지역은 서비스 오류 도메인 간의 고가용성을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="6c7a9-242">Paired Azure regions provide high availability across service failure domains.</span></span> <span data-ttu-id="6c7a9-243">따라서 지역 쌍은 다른 지역의 백업 지역으로 간과같이 확인될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6c7a9-243">Therefore, regional pairs can be thought of as each other's backup region.</span></span> <span data-ttu-id="6c7a9-244">즉 한 지역에 배치되는 Azure 리소스는 페어링된 영역을 통해 내결함성을 자동으로 보증합니다.</span><span class="sxs-lookup"><span data-stu-id="6c7a9-244">This means that an Azure resource that is placed in one region is automatically gaining fault tolerance through the paired region.</span></span> <span data-ttu-id="6c7a9-245">이러한 이유로 지역이 쌍으로 지정되는 데이터 암호화 정책에서 사용되는 두 개의 손에 대한 지역을 선택하면 총 두 가용성 지역을 만가지 유도하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="6c7a9-245">For this reason, choosing regions for two vaults used in a data encryption policy where the regions are paired means that only a total of two regions of availability are in use.</span></span> <span data-ttu-id="6c7a9-246">대부분의 지역에는 두 개의 지역만 사용하므로 아직 페어링되지 않은 영역을 선택할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="6c7a9-246">Most geographies only have two regions, so it's not yet possible to select non-paired regions.</span></span> <span data-ttu-id="6c7a9-247">가능한 경우 데이터 암호화 정책과 함께 사용되는 두 벤트에 대해 페어링되지 않은 두 지역을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="6c7a9-247">If possible, choose two non-paired regions for the two vaults used with a data encryption policy.</span></span> <span data-ttu-id="6c7a9-248">이 경우 총 네 가지 지역의 가용성 지역이 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6c7a9-248">This benefits from a total of four regions of availability.</span></span> <span data-ttu-id="6c7a9-249">자세한 내용은 현재 지역 쌍 목록에 대한 Azure 페어링된 지역인 비즈니스용 연속성 및 [BCDR(재해 복구)을](https://docs.microsoft.com/azure/best-practices-availability-paired-regions) 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="6c7a9-249">For more information, see [Business continuity and disaster recovery (BCDR): Azure Paired Regions](https://docs.microsoft.com/azure/best-practices-availability-paired-regions) for a current list of regional pairs.</span></span>
  
### <a name="assign-permissions-to-each-key-vault"></a><span data-ttu-id="6c7a9-250">각 키 상의에 사용 권한 할당</span><span class="sxs-lookup"><span data-stu-id="6c7a9-250">Assign permissions to each key vault</span></span>

<span data-ttu-id="6c7a9-251">각 키 오류에 대해 구현에 따라 고객 키에 대해 별도의 세 가지 권한 집합을 정의해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6c7a9-251">For each key vault, you will need to define three separate sets of permissions for Customer Key, depending on your implementation.</span></span> <span data-ttu-id="6c7a9-252">예를 들어 다음의 각 권한에 대해 권한을 하나씩 정의해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6c7a9-252">For example, you will need to define one set of permissions for each of the following:</span></span>
  
- <span data-ttu-id="6c7a9-253">**조직에 대한 키 취결함에** 대한 일상 적별 관리를 수행하는 주요 문제가 있는 경우</span><span class="sxs-lookup"><span data-stu-id="6c7a9-253">**Key vault administrators** that will perform day-to-day management of your key vault for your organization.</span></span> <span data-ttu-id="6c7a9-254">이러한 작업에는 백업, 만들기, 가져오기, 가져오기, 목록 및 복원이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="6c7a9-254">These tasks include backup, create, get, import, list, and restore.</span></span>

  > [!IMPORTANT]
  > <span data-ttu-id="6c7a9-255">키 매개 변수 관리자에게 할당된 권한 집합에는 키를 삭제할 수 있는 권한이 포함되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="6c7a9-255">The set of permissions assigned to key vault administrators does not include the permission to delete keys.</span></span> <span data-ttu-id="6c7a9-256">이것은 의도적이며 중요한 한 가지 예입니다.</span><span class="sxs-lookup"><span data-stu-id="6c7a9-256">This is intentional and an important practice.</span></span> <span data-ttu-id="6c7a9-257">따라서 데이터를 영구적으로 삭제하는 것이므로 암호화 키를 삭제하는 작업은 일반적으로 수행되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="6c7a9-257">Deleting encryption keys is not typically done, since doing so permanently destroys data.</span></span> <span data-ttu-id="6c7a9-258">기본적으로 키 모음관리자에게 이 사용 권한을 부여하지 않도록 하는 것이 가장 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="6c7a9-258">As a best practice, do not grant this permission to key vault administrators by default.</span></span> <span data-ttu-id="6c7a9-259">대신 초보 자료는 키 자격 증명을 유지하고 나중에 결과에 대한 명확한 지식을 이해한 다음 약간의 권한을 관리자에게 할당하십시오.</span><span class="sxs-lookup"><span data-stu-id="6c7a9-259">Instead, reserve this for key vault contributors and only assign it to an administrator on a short term basis once a clear understanding of the consequences is understood.</span></span>
  
  <span data-ttu-id="6c7a9-260">조직의 사용자에게 이러한 사용 권한을 할당하려면 Azure PowerShell을 사용하여 Azure 구독에 로그인합니다.</span><span class="sxs-lookup"><span data-stu-id="6c7a9-260">To assign these permissions to a user in your organization, log in to your Azure subscription with Azure PowerShell.</span></span> <span data-ttu-id="6c7a9-261">지침은 Azure [PowerShell로 로그인을 참조하세요.](https://docs.microsoft.com/powershell/azure/authenticate-azureps)</span><span class="sxs-lookup"><span data-stu-id="6c7a9-261">For instructions, see [Sign in with Azure PowerShell](https://docs.microsoft.com/powershell/azure/authenticate-azureps).</span></span>

- <span data-ttu-id="6c7a9-262">Set-AzKeyVaultAccessPolicy cmdlet을 실행하여 필요한 권한을 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="6c7a9-262">Run the Set-AzKeyVaultAccessPolicy cmdlet to assign the necessary permissions.</span></span>

   ```powershell
   Set-AzKeyVaultAccessPolicy -VaultName <vault name> -UserPrincipalName <UPN of user> -PermissionsToKeys create,import,list,get,backup,restore
   ```

   <span data-ttu-id="6c7a9-263">예시:</span><span class="sxs-lookup"><span data-stu-id="6c7a9-263">For example:</span></span>

   ```powershell
   Set-AzKeyVaultAccessPolicy -VaultName Contoso-O365EX-NA-VaultA1 -UserPrincipalName alice@contoso.com -PermissionsToKeys create,import,list,get,backup,restore
   ```

- <span data-ttu-id="6c7a9-264">Azure Key **Vault 자체에서 권한을 변경할 수** 있는 주요 Vault 절차입니다.</span><span class="sxs-lookup"><span data-stu-id="6c7a9-264">**Key vault contributors** that can change permissions on the Azure Key Vault itself.</span></span> <span data-ttu-id="6c7a9-265">이러한 권한을 변경하려면 직원이 팀을 떠나거나 여기에 참여하거나, 핵심 문제가 될 경우 관리자가 키를 삭제 또는 복원하기 위한 권한이 제대로 필요하다는 경우를 예로 들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6c7a9-265">You'll need to change these permissions as employees leave or join your team, or in the extremely rare situation that the key vault administrators legitimately need permission to delete or restore a key.</span></span> <span data-ttu-id="6c7a9-266">이 주요 Vault 작업자가 키 나누기에 대한 **Contributor** 고객 역할을 부여해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6c7a9-266">This set of key vault contributors needs to be granted the **Contributor** role on your key vault.</span></span> <span data-ttu-id="6c7a9-267">Azure Resource Manager를 사용하여 이 역할을 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6c7a9-267">You can assign this role by using Azure Resource Manager.</span></span> <span data-ttu-id="6c7a9-268">자세한 단계는 역할 [기반 액세스 제어를 사용하여 Azure 구독 리소스에 대한 액세스 관리를 참조하세요.](https://docs.microsoft.com/azure/active-directory/role-based-access-control-configure)</span><span class="sxs-lookup"><span data-stu-id="6c7a9-268">For detailed steps, see [Use Role-Based Access Control to manage access to your Azure subscription resources](https://docs.microsoft.com/azure/active-directory/role-based-access-control-configure).</span></span> <span data-ttu-id="6c7a9-269">구독을 만드는 관리자가 이 액세스는 암시적으로 가지며 다른 관리자를 추가 자료 역할에 할당하는 기능도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6c7a9-269">The administrator who creates a subscription has this access implicitly, as well as the ability to assign other administrators to the Contributor role.</span></span>

- <span data-ttu-id="6c7a9-270">고객 키를 Exchange Online 및 비즈니스용 Skype와 함께 사용하려면 Exchange Online 및 비즈니스용 Skype를 대신하여 키 상석자를 사용할 수 있는 권한을 Microsoft 365에 부여해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6c7a9-270">If you intend to use Customer Key with Exchange Online and Skype for Business, you need to give permission to Microsoft 365 to use the key vault on behalf of Exchange Online and Skype for Business.</span></span> <span data-ttu-id="6c7a9-271">마찬가지로 SharePoint Online 및 비즈니스용 OneDrive에서 고객 키를 사용하려면 Microsoft 365에 대한 권한을 추가하여 SharePoint Online 및 비즈니스용 OneDrive를 대신하여 키 상이를 이용하라는 권한을 추가해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6c7a9-271">Likewise, if you intend to use Customer Key with SharePoint Online and OneDrive for Business, you need to add permission for the Microsoft 365 to use the key vault on behalf of SharePoint Online and OneDrive for Business.</span></span> <span data-ttu-id="6c7a9-272">Microsoft 365에 대한 권한을 제공하려면 다음 구문을 사용하여 **Set-AzKeyVaultAccessPolicy** cmdlet을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="6c7a9-272">To give permission to Microsoft 365, run the **Set-AzKeyVaultAccessPolicy** cmdlet using the following syntax:</span></span> 

   ```powershell
   Set-AzKeyVaultAccessPolicy -VaultName <vault name> -PermissionsToKeys wrapKey,unwrapKey,get -ServicePrincipalName <Office 365 appID>
   ```

   <span data-ttu-id="6c7a9-273">여기서,</span><span class="sxs-lookup"><span data-stu-id="6c7a9-273">Where:</span></span>

    - <span data-ttu-id="6c7a9-274">*vault name은* 만든 키 버트의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="6c7a9-274">*vault name* is the name of the key vault you created.</span></span>

    - <span data-ttu-id="6c7a9-275">Exchange Online 및 비즈니스용 Skype의 경우 *Office 365 appID를 다음으로 바꾸기*`00000002-0000-0ff1-ce00-000000000000`</span><span class="sxs-lookup"><span data-stu-id="6c7a9-275">For Exchange Online and Skype for Business, replace  *Office 365 appID* with `00000002-0000-0ff1-ce00-000000000000`</span></span>

    - <span data-ttu-id="6c7a9-276">SharePoint Online, 비즈니스용 OneDrive 및 Teams 파일의 경우 *Office 365 appID를 다음으로 바꿀 수 있습니다.*`00000003-0000-0ff1-ce00-000000000000`</span><span class="sxs-lookup"><span data-stu-id="6c7a9-276">For SharePoint Online, OneDrive for Business, and Teams files, replace  *Office 365 appID* with `00000003-0000-0ff1-ce00-000000000000`</span></span>

  <span data-ttu-id="6c7a9-277">예: Exchange Online 및 비즈니스용 Skype에 대한 사용 권한 설정:</span><span class="sxs-lookup"><span data-stu-id="6c7a9-277">Example: Setting permissions for Exchange Online and Skype for Business:</span></span>

   ```powershell
   Set-AzKeyVaultAccessPolicy -VaultName Contoso-O365EX-NA-VaultA1 -PermissionsToKeys wrapKey,unwrapKey,get -ServicePrincipalName 00000002-0000-0ff1-ce00-000000000000
   ```

  <span data-ttu-id="6c7a9-278">예제: SharePoint Online, 비즈니스용 OneDrive 및 Teams 파일에 대한 사용 권한 설정:</span><span class="sxs-lookup"><span data-stu-id="6c7a9-278">Example: Setting permissions for SharePoint Online, OneDrive for Business, and Teams files:</span></span>

   ```powershell
   Set-AzKeyVaultAccessPolicy -VaultName Contoso-O365SP-NA-VaultA1 -PermissionsToKeys wrapKey,unwrapKey,get -ServicePrincipalName 00000003-0000-0ff1-ce00-000000000000
   ```

### <a name="enable-and-then-confirm-soft-delete-on-your-key-vaults"></a><span data-ttu-id="6c7a9-279">키 취미있는 경우 소미삭제를 사용하도록 설정하고 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="6c7a9-279">Enable and then confirm soft delete on your key vaults</span></span>

<span data-ttu-id="6c7a9-280">키를 신속하게 복구할 수 있는 경우 특히 또는 악의적으로 삭제한 키로 인한 서비스 중단이 발생하는 경우가 줄어드는 경우가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6c7a9-280">When you can quickly recover your keys, you are less likely to experience an extended service outage due to accidentally or maliciously deleted keys.</span></span> <span data-ttu-id="6c7a9-281">고객 키로 키를 사용하려면 먼저 Soft Delete라는 이 구성을 사용하도록 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6c7a9-281">You need to enable this configuration, referred to as Soft Delete, before you can use your keys with Customer Key.</span></span> <span data-ttu-id="6c7a9-282">일시 삭제를 사용하도록 설정해두면 백업에서 복원하지 않아도 90일 이내에 키 또는 오류가 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6c7a9-282">Enabling Soft Delete allows you to recover keys or vaults within 90 days of deletion without having to restore them from backup.</span></span>
  
<span data-ttu-id="6c7a9-283">키 매개 파일에서 Soft 삭제를 사용하려면 아래 단계를 완료하세요.</span><span class="sxs-lookup"><span data-stu-id="6c7a9-283">To enable Soft Delete on your key vaults, complete these steps:</span></span>
  
1. <span data-ttu-id="6c7a9-284">Windows Powershell을 사용하여 Azure 구독에 로그인합니다.</span><span class="sxs-lookup"><span data-stu-id="6c7a9-284">Sign in to your Azure subscription with Windows Powershell.</span></span> <span data-ttu-id="6c7a9-285">지침은 Azure [PowerShell로 로그인을 참조하세요.](https://docs.microsoft.com/powershell/azure/authenticate-azureps)</span><span class="sxs-lookup"><span data-stu-id="6c7a9-285">For instructions, see [Sign in with Azure PowerShell](https://docs.microsoft.com/powershell/azure/authenticate-azureps).</span></span>

2. <span data-ttu-id="6c7a9-286">[Get-AzKeyVault cmdlet을 실행합니다.](https://docs.microsoft.com/powershell/module/az.keyvault/get-azkeyvault)</span><span class="sxs-lookup"><span data-stu-id="6c7a9-286">Run the [Get-AzKeyVault](https://docs.microsoft.com/powershell/module/az.keyvault/get-azkeyvault) cmdlet.</span></span> <span data-ttu-id="6c7a9-287">이 *예제에서는 이름은 삭제를* 사용하도록 설정하기 위한 키 모음의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="6c7a9-287">In this example, *vault name* is the name of the key vault for which you are enabling soft delete:</span></span>

   ```powershell
   $v = Get-AzKeyVault -VaultName <vault name>
   $r = Get-AzResource -ResourceId $v.ResourceId
   $r.Properties | Add-Member -MemberType NoteProperty -Name enableSoftDelete -Value 'True'
   Set-AzResource -ResourceId $r.ResourceId -Properties $r.Properties
   ```

3. <span data-ttu-id="6c7a9-288">**Get-AzKeyVault** cmdlet을 실행하여 키 변경에 대해 소프트 삭제가 구성되어 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="6c7a9-288">Confirm soft delete is configured for the key vault by running the **Get-AzKeyVault** cmdlet.</span></span> <span data-ttu-id="6c7a9-289">키 오류에 대해 소프트 삭제가 제대로 구성되어 있으면 _Soft Delete Enabled 속성이_ True 값을 **반환합니다.**</span><span class="sxs-lookup"><span data-stu-id="6c7a9-289">If soft delete is configured properly for the key vault, then the _Soft Delete Enabled_ property returns a value of **True**:</span></span>

   ```powershell
   Get-AzKeyVault -VaultName <vault name> | fl
   ```

### <a name="add-a-key-to-each-key-vault-either-by-creating-or-importing-a-key"></a><span data-ttu-id="6c7a9-290">키를 만들거나 가져오는 방법으로 각 키 매개 키 변경 에키를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="6c7a9-290">Add a key to each key vault either by creating or importing a key</span></span>

<span data-ttu-id="6c7a9-291">Azure Key Vault에 키를 추가하는 방법은 두 가지가 있습니다. Key Vault에서 직접 키를 만들거나 키를 가져올 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6c7a9-291">There are two ways to add keys to an Azure Key Vault; you can create a key directly in Key Vault, or you can import a key.</span></span> <span data-ttu-id="6c7a9-292">Key Vault에서 직접 키를 만드는 것은 복잡도가 없습니다. 키를 가져오면 전체 키 생성 방식을 제어할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6c7a9-292">Creating a key directly in Key Vault is the less complicated method, while importing a key provides total control over how the key is generated.</span></span>
  
<span data-ttu-id="6c7a9-293">키 매개 변수로 직접 키를 만들려면 다음과 [같이 Add-AzKeyVaultKey](https://docs.microsoft.com/powershell/module/az.keyvault/add-azkeyvaultkey) cmdlet을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="6c7a9-293">To create a key directly in your key vault, run the [Add-AzKeyVaultKey](https://docs.microsoft.com/powershell/module/az.keyvault/add-azkeyvaultkey) cmdlet as follows:</span></span>
  
```powershell
Add-AzKeyVaultKey -VaultName <vault name> -Name <key name> -Destination <HSM|Software> -KeyOps wrapKey,unwrapKey
```

<span data-ttu-id="6c7a9-294">여기서,</span><span class="sxs-lookup"><span data-stu-id="6c7a9-294">Where:</span></span>

- <span data-ttu-id="6c7a9-295">*vault* name은 키를 만들 키 모음의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="6c7a9-295">*vault name* is the name of the key vault in which you want to create the key.</span></span>

- <span data-ttu-id="6c7a9-296">*키 이름은* 새 키로 사용할 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="6c7a9-296">*key name* is the name you want to give the new key.</span></span>

  > [!TIP]
  > <span data-ttu-id="6c7a9-297">키 vaults에 대해 위에 설명한 대로 유사한 명명 규칙을 사용하여 키 이름 지정</span><span class="sxs-lookup"><span data-stu-id="6c7a9-297">Name keys using a similar naming convention as described above for key vaults.</span></span> <span data-ttu-id="6c7a9-298">이렇게 하면 키 이름만 표시하는 도구에서는 문자열에 대해 설명이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="6c7a9-298">This way, in tools that show only the key name, the string is self-describing.</span></span>
  
- <span data-ttu-id="6c7a9-299">HSM으로 키를 보호하려면 **HSM을** Destination 매개 변수의 값으로 지정하고, 그렇지 않으면 _Software를_ **지정합니다.**</span><span class="sxs-lookup"><span data-stu-id="6c7a9-299">If you intend to protect the key with an HSM, ensure that you specify **HSM** as the value of the _Destination_ parameter, otherwise, specify **Software**.</span></span>

<span data-ttu-id="6c7a9-300">예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="6c7a9-300">For example,</span></span>
  
```powershell
Add-AzKeyVaultKey -VaultName Contoso-O365EX-NA-VaultA1 -Name Contoso-O365EX-NA-VaultA1-Key001 -Destination Software -KeyOps wrapKey,unwrapKey
```

<span data-ttu-id="6c7a9-301">키 자격을 직접 키 자격에 가져오려면 nCipher nShield 하드웨어 보안 모듈이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="6c7a9-301">To import a key directly into your key vault, you need to have a nCipher nShield Hardware Security Module.</span></span>
  
<span data-ttu-id="6c7a9-302">일부 조직에서는 키를 입증하기 위해 이 접근 방법을 선사한 후 이 방법에서 다음을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="6c7a9-302">Some organizations prefer this approach to establish the provenance of their keys, and then this method also provides the following:</span></span>
  
- <span data-ttu-id="6c7a9-303">가져오기에 사용되는 도구 집합에는 생성하는 키를 암호화하는 데 사용되는 키 KEK(키 교환 키)를 내보낼 수 없고 nCipher에서 제조한 일반 HSM 내에서 생성되는 nCipher의 증명이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="6c7a9-303">The toolset used for import includes attestation from nCipher that the Key Exchange Key (KEK) that is used to encrypt the key you generate is not exportable and is generated inside a genuine HSM that was manufactured by nCipher.</span></span>

- <span data-ttu-id="6c7a9-304">이 도구 집합에는 nCipher에 의해 적정된 HSM 제조업체에서도 Azure Key Vault 보안 세계를 생성한다는 증명이 nCipher의 증명을 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="6c7a9-304">The toolset includes attestation from nCipher that the Azure Key Vault security world was also generated on a genuine HSM manufactured by nCipher.</span></span> <span data-ttu-id="6c7a9-305">이 증명은 Microsoft가 제네인 NCipher 하드웨어도 사용한다고 생각합니다.</span><span class="sxs-lookup"><span data-stu-id="6c7a9-305">This attestation proves to you that Microsoft is also using genuine nCipher hardware.</span></span>

<span data-ttu-id="6c7a9-306">보안 그룹을 확인하여 위의 증명이 필요한지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="6c7a9-306">Check with your security group to determine if the above attestations are required.</span></span> <span data-ttu-id="6c7a9-307">온-프레미스로 키를 만들고 키 권한 으로 가져오는 자세한 단계는 [Azure Key Vault에 대한 HSM 보호 키를 생성하고 전송하는 방법을 참조하세요.](https://azure.microsoft.com/documentation/articles/key-vault-hsm-protected-keys/)</span><span class="sxs-lookup"><span data-stu-id="6c7a9-307">For detailed steps to create a key on-premises and import it into your key vault, see [How to generate and transfer HSM-protected keys for Azure Key Vault](https://azure.microsoft.com/documentation/articles/key-vault-hsm-protected-keys/).</span></span> <span data-ttu-id="6c7a9-308">Azure 지침을 사용하여 각 키 상취에 키를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="6c7a9-308">Use the Azure instructions to create a key in each key vault.</span></span>
  
### <a name="check-the-recovery-level-of-your-keys"></a><span data-ttu-id="6c7a9-309">키의 복구 수준 확인</span><span class="sxs-lookup"><span data-stu-id="6c7a9-309">Check the recovery level of your keys</span></span>

<span data-ttu-id="6c7a9-310">Microsoft 365를 사용하려면 Azure Key Vault 구독이 취소 안 함으로 설정되고 고객 키에서 사용하는 키에 소재 삭제를 설정하도록 되어 있는지 확인해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6c7a9-310">Microsoft 365 requires that the Azure Key Vault subscription is set to Do Not Cancel and that the keys used by Customer Key have soft delete enabled.</span></span> <span data-ttu-id="6c7a9-311">키의 복구 수준을 확인하여 이를 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6c7a9-311">You can confirm this by looking at the recovery level on your keys.</span></span>
  
<span data-ttu-id="6c7a9-312">키의 복구 수준을 확인하려면 Azure PowerShell에서 다음과 같이 Get-AzKeyVaultKey cmdlet을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="6c7a9-312">To check the recovery level of a key, in Azure PowerShell, run the Get-AzKeyVaultKey cmdlet as follows:</span></span>
  
```powershell
(Get-AzKeyVaultKey -VaultName <vault name> -Name <key name>).Attributes
```

<span data-ttu-id="6c7a9-313">복구 _수준 속성이_ **Recoverable+ProtectedSubscription 값**이외의 값을 반환하는 경우 이 항목을 검토하고 구독을 취소하지 않음 목록에 추가하고 각 키 변경 시 점에 소재 삭제를 사용할 수 있도록 설정되었는지 확인해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6c7a9-313">If the _Recovery Level_ property returns anything other than a value of **Recoverable+ProtectedSubscription**, you will need to review this topic and ensure that you have followed all of the steps to put the subscription on the Do Not Cancel list and that you have soft delete enabled on each of your key vaults.</span></span>
  
### <a name="back-up-azure-key-vault"></a><span data-ttu-id="6c7a9-314">Azure Key Vault 백업</span><span class="sxs-lookup"><span data-stu-id="6c7a9-314">Back up Azure Key Vault</span></span>

<span data-ttu-id="6c7a9-315">키를 생성하거나 키를 변경한 후 바로 백업을 수행하고 온라인 및 오프라인으로 백업 복사본을 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="6c7a9-315">Immediately following creation or any change to a key, perform a backup and store copies of the backup, both online and offline.</span></span> <span data-ttu-id="6c7a9-316">오프라인 복사본은 물리적 안전한 저장소 시각이나 상용 저장소 시각 같은 네트워크에 연결되어서는 안 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6c7a9-316">Offline copies should not be connected to any network, such as in a physical safe or commercial storage facility.</span></span> <span data-ttu-id="6c7a9-317">적어도 하나 이상의 백업 복사본은 재해가 발생하는 경우 액세스할 수 있는 위치에 저장되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6c7a9-317">At least one copy of the backup should be stored in a location that will be accessible in the event of a disaster.</span></span> <span data-ttu-id="6c7a9-318">백업 Blob이 단지 복원되는 한가지 유일한 방법은 Key Vault 키를 영구적으로 삭제하거나 나서 운영할 수 없도록 렌더링한다는 점에서 유일한 방법입니다.</span><span class="sxs-lookup"><span data-stu-id="6c7a9-318">The backup blobs are the sole means of restoring key material should a Key Vault key be permanently destroyed or otherwise rendered inoperable.</span></span> <span data-ttu-id="6c7a9-319">Azure Key Vault 외부에서 Azure Key Vault로 가져온 키는 고객 키를 사용하는 데 필요한 메타데이터가 외부 키에 존재하지 않기 때문에 백업으로 제정되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="6c7a9-319">Keys that are external to Azure Key Vault and were imported to Azure Key Vault do not qualify as a backup because the metadata necessary for Customer Key to use the key does not exist with the external key.</span></span> <span data-ttu-id="6c7a9-320">고객 키가 포함된 복원 작업에는 Azure Key Vault에서 가온 백업만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6c7a9-320">Only a backup taken from Azure Key Vault can be used for restore operations with Customer Key.</span></span> <span data-ttu-id="6c7a9-321">따라서 키를 업로드하거나 만들면 Azure Key Vault의 백업이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="6c7a9-321">Therefore, it is essential that a backup of Azure Key Vault be made once a key is uploaded or created.</span></span>
  
<span data-ttu-id="6c7a9-322">Azure Key Vault 키의 백업을 만들려면 [다음과 같이 Backup-AzKeyVaultKey](https://docs.microsoft.com/powershell/module/az.keyvault/backup-azkeyvaultkey) cmdlet을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="6c7a9-322">To create a backup of an Azure Key Vault key, run the [Backup-AzKeyVaultKey](https://docs.microsoft.com/powershell/module/az.keyvault/backup-azkeyvaultkey) cmdlet as follows:</span></span>

```powershell
Backup-AzKeyVaultKey -VaultName <vault name> -Name <key name>
-OutputFile <filename.backup>
```

<span data-ttu-id="6c7a9-323">출력 파일에 접미사가 사용되는지 `.backup` 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="6c7a9-323">Ensure that your output file uses the suffix `.backup`.</span></span>
  
<span data-ttu-id="6c7a9-324">이 cmdlet의 결과 출력 파일은 암호화되며 Azure Key Vault 이외의 에서 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="6c7a9-324">The output file resulting from this cmdlet is encrypted and cannot be used outside of Azure Key Vault.</span></span> <span data-ttu-id="6c7a9-325">백업은 백업을 가도한 Azure 구독으로만 복원할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6c7a9-325">The backup can be restored only to the Azure subscription from which the backup was taken.</span></span>
  
> [!TIP]
> <span data-ttu-id="6c7a9-326">출력 파일에 대해 취미 이름과 키 이름을 조합하여 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="6c7a9-326">For the output file, choose a combination of your vault name and key name.</span></span> <span data-ttu-id="6c7a9-327">그러면 파일 이름이 자체 설명됩니다.</span><span class="sxs-lookup"><span data-stu-id="6c7a9-327">This will make the file name self-describing.</span></span> <span data-ttu-id="6c7a9-328">이 백업 파일 이름도 통합되지 않도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="6c7a9-328">It will also ensure that backup file names do not collide.</span></span>
  
<span data-ttu-id="6c7a9-329">예시:</span><span class="sxs-lookup"><span data-stu-id="6c7a9-329">For example:</span></span>
  
```powershell
Backup-AzKeyVaultKey -VaultName Contoso-O365EX-NA-VaultA1 -Name Contoso-O365EX-NA-VaultA1-Key001 -OutputFile Contoso-O365EX-NA-VaultA1-Key001-Backup-20170802.backup
```

### <a name="validate-azure-key-vault-configuration-settings"></a><span data-ttu-id="6c7a9-330">Azure Key Vault 구성 설정 확인</span><span class="sxs-lookup"><span data-stu-id="6c7a9-330">Validate Azure Key Vault configuration settings</span></span>

<span data-ttu-id="6c7a9-331">DEP에서 키를 사용하기 전에 유효성 검사를 수행하는 것은 선택 사항이지만 사용하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="6c7a9-331">Performing validation before using keys in a DEP is optional, but highly recommended.</span></span> <span data-ttu-id="6c7a9-332">특히 이 항목에 설명된 것 이외의 다른 키 및 이전 사용자 키를 설정하는 단계를 사용하는 경우에는 고객 키를 구성하기 전에 Azure Key Vault 리소스의 상태를 확인해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6c7a9-332">In particular, if you use steps to set up your keys and vaults other than the ones described in this topic, you should validate the health of your Azure Key Vault resources before you configure Customer Key.</span></span>
  
<span data-ttu-id="6c7a9-333">키가 get, wrapKey 및 unwrapKey 작업을 사용하도록 설정되어 있는지 확인하려면</span><span class="sxs-lookup"><span data-stu-id="6c7a9-333">To verify that your keys have get, wrapKey, and unwrapKey operations enabled:</span></span>
  
<span data-ttu-id="6c7a9-334">다음과 [같이 Get-AzKeyVault](https://docs.microsoft.com/powershell/module/az.keyvault/get-azkeyvault) cmdlet을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="6c7a9-334">Run the [Get-AzKeyVault](https://docs.microsoft.com/powershell/module/az.keyvault/get-azkeyvault) cmdlet as follows:</span></span>
  
```powershell
Get-AzKeyVault -VaultName <vault name>
```

<span data-ttu-id="6c7a9-335">출력에서 액세스 정책과 Exchange Online ID(GUID) 또는 SharePoint Online ID(GUID)가 적절하게 맞는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="6c7a9-335">In the output, look for the Access Policy and for the Exchange Online identity (GUID) or the SharePoint Online identity (GUID) as appropriate.</span></span> <span data-ttu-id="6c7a9-336">위의 사용 권한 모두 키에 대한 권한 아래에 표시해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6c7a9-336">All three of the above permissions must be shown under Permissions to Keys.</span></span>
  
<span data-ttu-id="6c7a9-337">액세스 정책 구성이 잘못된 경우 다음과 같이 Set-AzKeyVaultAccessPolicy cmdlet을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="6c7a9-337">If the access policy configuration is incorrect, run the Set-AzKeyVaultAccessPolicy cmdlet as follows:</span></span>
  
```powershell
Set-AzKeyVaultAccessPolicy -VaultName <vault name> -PermissionsToKeys wrapKey,unwrapKey,get -ServicePrincipalName <Office 365 appID>
```

<span data-ttu-id="6c7a9-338">예를 들어 Exchange Online 및 비즈니스용 Skype의 경우 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="6c7a9-338">For example, for Exchange Online and Skype for Business:</span></span>
  
```powershell
Set-AzKeyVaultAccessPolicy -VaultName Contoso-O365EX-NA-VaultA1 
-PermissionsToKeys wrapKey,unwrapKey,get -ServicePrincipalName 00000002-0000-0ff1-ce00-000000000000
```

<span data-ttu-id="6c7a9-339">예를 들어 SharePoint Online 및 비즈니스용 OneDrive의 경우 다음을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="6c7a9-339">For example, for SharePoint Online and OneDrive for Business:</span></span>
  
```powershell
Set-AzKeyVaultAccessPolicy -VaultName Contoso-O365SP-NA-VaultA1
-PermissionsToKeys wrapKey,unwrapKey,get -ServicePrincipalName 00000003-0000-0ff1-ce00-000000000000
```

<span data-ttu-id="6c7a9-340">키에 대해 만료 날짜가 설정되지 않도록 하려면 [다음과 같이 Get-AzKeyVaultKey](https://docs.microsoft.com/powershell/module/az.keyvault/get-azkeyvault) cmdlet을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="6c7a9-340">To verify that an expiration date is not set for your keys run the [Get-AzKeyVaultKey](https://docs.microsoft.com/powershell/module/az.keyvault/get-azkeyvault) cmdlet as follows:</span></span>
  
```powershell
Get-AzKeyVaultKey -VaultName <vault name>
```

<span data-ttu-id="6c7a9-341">만료된 키로 인해 고객 키와 작동이 시도된 키를 사용할 수 없는 경우 서비스가 중단될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6c7a9-341">An expired key cannot be used by Customer Key and operations attempted with an expired key will fail, and possibly result in a service outage.</span></span> <span data-ttu-id="6c7a9-342">고객 키와 함께 사용되는 키에 만료 날짜는 없는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="6c7a9-342">We strongly recommend that keys used with Customer Key do not have an expiration date.</span></span> <span data-ttu-id="6c7a9-343">설정되면 만료 날짜를 제거할 수 없지만 다른 날짜로 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6c7a9-343">An expiration date, once set, cannot be removed, but can be changed to a different date.</span></span> <span data-ttu-id="6c7a9-344">만료 날짜를 설정한 키를 사용하려면 만료 값을 12/31/9999로 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="6c7a9-344">If a key must be used that has an expiration date set, change the expiration value to 12/31/9999.</span></span> <span data-ttu-id="6c7a9-345">만료 날짜가 만료 날짜가 9999년 12월 31일이 아니면 Microsoft 365 유효성 검사를 통과하지 못합니다.</span><span class="sxs-lookup"><span data-stu-id="6c7a9-345">Keys with an expiration date set to a date other than 12/31/9999 will not pass Microsoft 365 validation.</span></span>
  
<span data-ttu-id="6c7a9-346">만료 날짜를 12/31/9999 이외의 값으로 변경하려면 [다음과 같이 Update-AzKeyVaultKey](https://docs.microsoft.com/powershell/module/az.keyvault/update-azkeyvaultkey) cmdlet을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="6c7a9-346">To change an expiration date that has been set to any value other than 12/31/9999, run the [Update-AzKeyVaultKey](https://docs.microsoft.com/powershell/module/az.keyvault/update-azkeyvaultkey) cmdlet as follows:</span></span>
  
```powershell
Update-AzKeyVaultKey -VaultName <vault name> -Name <key name> -Expires (Get-Date -Date "12/31/9999")
```

> [!CAUTION]
> <span data-ttu-id="6c7a9-347">고객 키와 함께 사용하는 암호화 키의 만료 날짜를 설정하지 마세요.</span><span class="sxs-lookup"><span data-stu-id="6c7a9-347">Don't set expiration dates on encryption keys you use with Customer Key.</span></span>
  
### <a name="obtain-the-uri-for-each-azure-key-vault-key"></a><span data-ttu-id="6c7a9-348">각 Azure Key Vault 키의 URI 가져오기</span><span class="sxs-lookup"><span data-stu-id="6c7a9-348">Obtain the URI for each Azure Key Vault key</span></span>

<span data-ttu-id="6c7a9-349">Azure의 모든 단계를 완료하여 키 변경과 키 추가를 마치면 다음 명령을 실행하여 각 키 모음에서 키의 URI를 가져오십시오.</span><span class="sxs-lookup"><span data-stu-id="6c7a9-349">Once you've completed all the steps in Azure to set up your key vaults and added your keys, run the following command to get the URI for the key in each key vault.</span></span> <span data-ttu-id="6c7a9-350">각 DEP를 나중에 만들고 할당할 때 이러한 URI를 사용하므로 해당 정보를 안전한 장소에 저장해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6c7a9-350">You will need to use these URIs when you create and assign each DEP later, so save this information in a safe place.</span></span> <span data-ttu-id="6c7a9-351">각 키 모음에 대해 이 명령을 한 번 실행해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6c7a9-351">Remember to run this command once for each key vault.</span></span>
  
<span data-ttu-id="6c7a9-352">Azure PowerShell에서:</span><span class="sxs-lookup"><span data-stu-id="6c7a9-352">In Azure PowerShell:</span></span>
  
```powershell
(Get-AzKeyVaultKey -VaultName <vault name>).Id
```

## <a name="office-365-setting-up-customer-key-for-exchange-online-and-skype-for-business"></a><span data-ttu-id="6c7a9-353">Office 365: Exchange Online 및 비즈니스용 Skype에 대한 고객 키 설정</span><span class="sxs-lookup"><span data-stu-id="6c7a9-353">Office 365: Setting up Customer Key for Exchange Online and Skype for Business</span></span>

<span data-ttu-id="6c7a9-354">시작하기 전에 Azure Key Vault를 설정하는 데 필요한 작업을 완료해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6c7a9-354">Before you begin, ensure that you have completed the tasks required to set up Azure Key Vault.</span></span> <span data-ttu-id="6c7a9-355">자세한 [내용은 Azure Key Vault 및 Microsoft FastTrack의 전체 작업을](#complete-tasks-in-azure-key-vault-and-microsoft-fasttrack-for-customer-key) 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="6c7a9-355">See [Complete tasks in Azure Key Vault and Microsoft FastTrack for Customer Key](#complete-tasks-in-azure-key-vault-and-microsoft-fasttrack-for-customer-key) for information.</span></span>
  
<span data-ttu-id="6c7a9-356">Exchange Online 및 비즈니스용 Skype에 사용할 고객 키를 설정하려면 Exchange Online에 원격으로 연결하여 조직을 지원하고 다음 단계를 Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="6c7a9-356">To set up Customer Key for Exchange Online and Skype for Business, you will need to perform these steps by remotely connecting to Exchange Online with Windows PowerShell.</span></span>
  
### <a name="create-a-data-encryption-policy-dep-for-use-with-exchange-online-and-skype-for-business"></a><span data-ttu-id="6c7a9-357">Exchange Online 및 비즈니스용 Skype에 사용할 DEP(데이터 암호화 정책) 만들기</span><span class="sxs-lookup"><span data-stu-id="6c7a9-357">Create a data encryption policy (DEP) for use with Exchange Online and Skype for Business</span></span>

<span data-ttu-id="6c7a9-358">DEP는 Azure Key Vault에 저장된 키 집합과 연결되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6c7a9-358">A DEP is associated with a set of keys stored in Azure Key Vault.</span></span> <span data-ttu-id="6c7a9-359">Microsoft 365의 사서함에 DEP를 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="6c7a9-359">You assign a DEP to a mailbox in Microsoft 365.</span></span> <span data-ttu-id="6c7a9-360">그러면 Microsoft 365는 정책에 식별된 키를 사용하여 사서함을 암호화합니다.</span><span class="sxs-lookup"><span data-stu-id="6c7a9-360">Microsoft 365 will then use the keys identified in the policy to encrypt the mailbox.</span></span> <span data-ttu-id="6c7a9-361">DEP를 만들려면 앞서 가온 키 Vault URI가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="6c7a9-361">To create the DEP, you need the Key Vault URIs you obtained earlier.</span></span> <span data-ttu-id="6c7a9-362">지침은 [각 Azure Key Vault 키에 대한 URI 가져오기를](#obtain-the-uri-for-each-azure-key-vault-key) 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="6c7a9-362">See [Obtain the URI for each Azure Key Vault key](#obtain-the-uri-for-each-azure-key-vault-key) for instructions.</span></span>
  
<span data-ttu-id="6c7a9-363">기한이지 기다해 주세요!</span><span class="sxs-lookup"><span data-stu-id="6c7a9-363">Remember!</span></span> <span data-ttu-id="6c7a9-364">DEP를 만들 때는 두 개의 다른 Azure Key Vaults에 있는 두 개의 키를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="6c7a9-364">When you create a DEP, you specify two keys that reside in two different Azure Key Vaults.</span></span> <span data-ttu-id="6c7a9-365">이러한 키가 두 개의 개별 Azure 지역에 있는지 확인하여 지리적 중복성을 보보입니다.</span><span class="sxs-lookup"><span data-stu-id="6c7a9-365">Ensure that these keys are located in two separate Azure regions to ensure geo-redundancy.</span></span>
  
<span data-ttu-id="6c7a9-366">DEP를 만들려면 다음 단계를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="6c7a9-366">To create the DEP, follow these steps:</span></span>
  
1. <span data-ttu-id="6c7a9-367">로컬 컴퓨터에서 조직의 전역 관리자 권한이 있는 회사 또는 학교 계정을 사용하여 다음 최소 Windows PowerShell [PowerShell에](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell) Windows PowerShell 합니다.</span><span class="sxs-lookup"><span data-stu-id="6c7a9-367">On your local computer, using a work or school account that has global administrator permissions in your organization, [connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell) in a Windows PowerShell window.</span></span>

2. <span data-ttu-id="6c7a9-368">DEP를 만들려면 다음 명령을 입력하여 New-DataEncryptionPolicy cmdlet을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="6c7a9-368">To create a DEP, use the New-DataEncryptionPolicy cmdlet by typing the following command.</span></span>

   ```powershell
   New-DataEncryptionPolicy -Name <PolicyName> -Description "Policy Description" -AzureKeyIDs <KeyVaultURI1>, <KeyVaultURI2>
   ```

   <span data-ttu-id="6c7a9-369">여기서,</span><span class="sxs-lookup"><span data-stu-id="6c7a9-369">Where:</span></span>

   - <span data-ttu-id="6c7a9-370">*PolicyName은* 정책에 사용할 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="6c7a9-370">*PolicyName* is the name you want to use for the policy.</span></span> <span data-ttu-id="6c7a9-371">이름에는 공백을 포함할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="6c7a9-371">Names cannot contain spaces.</span></span> <span data-ttu-id="6c7a9-372">예를 들면 USA_mailboxes.</span><span class="sxs-lookup"><span data-stu-id="6c7a9-372">For example, USA_mailboxes.</span></span>

   - <span data-ttu-id="6c7a9-373">*정책 설명은* 정책에 대한 설명을 기알 어떤 정책에 대한 설명입니다.</span><span class="sxs-lookup"><span data-stu-id="6c7a9-373">*Policy Description* is a user friendly description of the policy that will help you remember what the policy is for.</span></span> <span data-ttu-id="6c7a9-374">설명에 공백을 포함할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6c7a9-374">You can include spaces in the description.</span></span> <span data-ttu-id="6c7a9-375">예를 들면 "미국, 지사의 사서함에 대한 루트 키".</span><span class="sxs-lookup"><span data-stu-id="6c7a9-375">For example, "Root key for mailboxes in USA and its territories".</span></span>

   - <span data-ttu-id="6c7a9-376">*KeyVaultURI1은* 정책의 첫 번째 키에 대한 URI입니다.</span><span class="sxs-lookup"><span data-stu-id="6c7a9-376">*KeyVaultURI1* is the URI for the first key in the policy.</span></span> <span data-ttu-id="6c7a9-377">예를 들면 <https://contoso_EastUSvault01.vault.azure.net/keys/USA_key_01>와 같습니다.</span><span class="sxs-lookup"><span data-stu-id="6c7a9-377">For example, <https://contoso_EastUSvault01.vault.azure.net/keys/USA_key_01>.</span></span>

   - <span data-ttu-id="6c7a9-378">*KeyVaultURI2는* 정책의 두 번째 키에 대한 URI입니다.</span><span class="sxs-lookup"><span data-stu-id="6c7a9-378">*KeyVaultURI2* is the URI for the second key in the policy.</span></span> <span data-ttu-id="6c7a9-379">예를 들면 <https://contoso_EastUS2vault01.vault.azure.net/keys/USA_Key_02>와 같습니다.</span><span class="sxs-lookup"><span data-stu-id="6c7a9-379">For example, <https://contoso_EastUS2vault01.vault.azure.net/keys/USA_Key_02>.</span></span> <span data-ttu-id="6c7a9-380">두 URI를 쉼표와 공백으로 구분합니다.</span><span class="sxs-lookup"><span data-stu-id="6c7a9-380">Separate the two URIs by a comma and a space.</span></span>

   <span data-ttu-id="6c7a9-381">예제:</span><span class="sxs-lookup"><span data-stu-id="6c7a9-381">Example:</span></span>
  
   ```powershell
   New-DataEncryptionPolicy -Name USA_mailboxes -Description "Root key for mailboxes in USA and its territories" -AzureKeyIDs https://contoso_EastUSvault01.vault.azure.net/keys/USA_key_01, https://contoso_EastUS2vault01.vault.azure.net/keys/USA_Key_02
   ```

<span data-ttu-id="6c7a9-382">구문과 매개 변수에 대한 자세한 내용은 [New-DataEncryptionPolicy를 참조하세요.](https://docs.microsoft.com/powershell/module/exchange/new-data-encryptionpolicy)</span><span class="sxs-lookup"><span data-stu-id="6c7a9-382">For detailed syntax and parameter information, see [New-DataEncryptionPolicy](https://docs.microsoft.com/powershell/module/exchange/new-data-encryptionpolicy).</span></span>

### <a name="assign-a-dep-to-a-mailbox"></a><span data-ttu-id="6c7a9-383">사서함에 DEP 할당</span><span class="sxs-lookup"><span data-stu-id="6c7a9-383">Assign a DEP to a mailbox</span></span>

<span data-ttu-id="6c7a9-384">Set-Mailbox cmdlet을 사용하여 사서함에 DEP를 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="6c7a9-384">Assign the DEP to a mailbox by using the Set-Mailbox cmdlet.</span></span> <span data-ttu-id="6c7a9-385">정책을 할당하면 Microsoft 365에서 DEP에 지정된 키를 사용하여 사서함을 암호화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6c7a9-385">Once you assign the policy, Microsoft 365 can encrypt the mailbox with the key designated in the DEP.</span></span>
  
```powershell
Set-Mailbox -Identity <MailboxIdParameter> -DataEncryptionPolicy <PolicyName>
```

<span data-ttu-id="6c7a9-386">여기서 *MailboxIdParameter는* 사서함을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="6c7a9-386">Where *MailboxIdParameter* specifies a mailbox.</span></span> <span data-ttu-id="6c7a9-387">Set-Mailbox cmdlet에 대한 자세한 내용은 [Set-Mailbox를 참조하십시오.](https://docs.microsoft.com/powershell/module/exchange/set-mailbox)</span><span class="sxs-lookup"><span data-stu-id="6c7a9-387">For more information about the Set-Mailbox cmdlet, see [Set-Mailbox](https://docs.microsoft.com/powershell/module/exchange/set-mailbox).</span></span>

<span data-ttu-id="6c7a9-388">하이브리드 [최신 인증이 있는 iOS 및 Android용 Outlook을 사용하는](https://docs.microsoft.com/exchange/clients/outlook-for-ios-and-android/use-hybrid-modern-auth)온-프레미스 사서함의 경우 Exchange Online 테넌트와 동기화되는 온-프레미스 사서함 데이터에 Set-MailUser cmdlet을 사용하여 DEP를 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6c7a9-388">For [on-premises mailboxes using Outlook for iOS and Android with hybrid Modern Authentication](https://docs.microsoft.com/exchange/clients/outlook-for-ios-and-android/use-hybrid-modern-auth), the on-premises mailbox data that is synchronized into your Exchange Online tenant can have DEP assigned using the Set-MailUser cmdlet.</span></span>

```powershell
Set-MailUser -Identity <MailUserIdParameter> -DataEncryptionPolicy <PolicyName>
```

<span data-ttu-id="6c7a9-389">여기서 *MailUserIdParameter는* 메일 사용자(메일 사용이 가능한 사용자로도 알려진)를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="6c7a9-389">Where *MailUserIdParameter* specifies a mail user (also known as a mail-enabled user).</span></span> <span data-ttu-id="6c7a9-390">Set-MailUser cmdlet에 대한 자세한 내용은 [Set-MailUser를 참조하십시오.](https://docs.microsoft.com/powershell/module/exchange/set-mailuser)</span><span class="sxs-lookup"><span data-stu-id="6c7a9-390">For more information about the Set-MailUser cmdlet, see [Set-MailUser](https://docs.microsoft.com/powershell/module/exchange/set-mailuser).</span></span>
  
### <a name="validate-mailbox-encryption"></a><span data-ttu-id="6c7a9-391">사서함 암호화 유효성 검사</span><span class="sxs-lookup"><span data-stu-id="6c7a9-391">Validate mailbox encryption</span></span>

<span data-ttu-id="6c7a9-392">사서함을 암호화하는 데 시간이 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6c7a9-392">Encrypting a mailbox can take some time.</span></span> <span data-ttu-id="6c7a9-393">처음 할당 시 사서함을 암호화하기 전에 사서함을 한 데이터베이스에서 다른 데이터베이스로 완전히 이동해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6c7a9-393">For first time policy assignment, the mailbox must also completely move from one database to another before the service can encrypt the mailbox.</span></span> <span data-ttu-id="6c7a9-394">DEP를 변경하거나 사서함에 DEP를 처음 할당한 후에 암호화의 유효성을 검사하기 전에 72시간을 기다리는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="6c7a9-394">We recommend that you wait 72 hours before you attempt to validate encryption after you change a DEP or the first time you assign a DEP to a mailbox.</span></span>
  
<span data-ttu-id="6c7a9-395">Get-MailboxStatistics cmdlet을 사용하면 사서함암호화 여부를 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="6c7a9-395">Use the Get-MailboxStatistics cmdlet to determine if a mailbox is encrypted.</span></span>
  
```powershell
Get-MailboxStatistics -Identity <GeneralMailboxOrMailUserIdParameter> | fl IsEncrypted
```

<span data-ttu-id="6c7a9-396">IsEncrypted 속성은 사서함이 암호화되어 있으면 **값 true를** 반환하고, 사서함이 암호화되지 않은 경우 **False의** 값을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="6c7a9-396">The IsEncrypted property returns a value of **true** if the mailbox is encrypted and a value of **false** if the mailbox is not encrypted.</span></span>

<span data-ttu-id="6c7a9-397">사서함 이동을 완료하기 위한 시간은 사서함의 크기와 DEP를 처음으로 할당한 사서함 수에 따라 달라지기를 의미합니다.</span><span class="sxs-lookup"><span data-stu-id="6c7a9-397">The time to complete mailbox moves depends on the number of mailboxes to which you assign a DEP for the first time, as well as the size of the mailboxes.</span></span> <span data-ttu-id="6c7a9-398">DEP가 할당된 시간부터 일주일 후에 사서함이 암호화되지 않은 경우 Microsoft에 문의하세요.</span><span class="sxs-lookup"><span data-stu-id="6c7a9-398">If the mailboxes have not been encrypted after a week from the time you assigned the DEP, contact Microsoft.</span></span>

## <a name="office-365-setting-up-customer-key-for-sharepoint-online-onedrive-for-business-and-teams-files"></a><span data-ttu-id="6c7a9-399">Office 365: SharePoint Online, 비즈니스용 OneDrive 및 Teams 파일에 대한 고객 키 설정</span><span class="sxs-lookup"><span data-stu-id="6c7a9-399">Office 365: Setting up Customer Key for SharePoint Online, OneDrive for Business, and Teams files</span></span>

<span data-ttu-id="6c7a9-400">시작하기 전에 Azure Key Vault를 설정하는 데 필요한 작업을 완료해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6c7a9-400">Before you begin, ensure that you have completed the tasks required to set up Azure Key Vault.</span></span> <span data-ttu-id="6c7a9-401">자세한 [내용은 Azure Key Vault 및 Microsoft FastTrack의 전체 작업을](#complete-tasks-in-azure-key-vault-and-microsoft-fasttrack-for-customer-key) 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="6c7a9-401">See [Complete tasks in Azure Key Vault and Microsoft FastTrack for Customer Key](#complete-tasks-in-azure-key-vault-and-microsoft-fasttrack-for-customer-key) for information.</span></span>
  
<span data-ttu-id="6c7a9-402">SharePoint Online, 비즈니스용 OneDrive 및 Teams 파일에 대한 고객 키를 설정하려면 SharePoint Online과 원격으로 연결하여 다음 단계를 Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="6c7a9-402">To set up Customer Key for SharePoint Online, OneDrive for Business, and Teams files you will need to perform these steps by remotely connecting to SharePoint Online with Windows PowerShell.</span></span>
  
### <a name="create-a-data-encryption-policy-dep-for-each-sharepoint-online-and-onedrive-for-business-geo"></a><span data-ttu-id="6c7a9-403">각 SharePoint Online 및 비즈니스용 OneDrive 지역에 대한 DEP(데이터 암호화 정책) 만들기</span><span class="sxs-lookup"><span data-stu-id="6c7a9-403">Create a data encryption policy (DEP) for each SharePoint Online and OneDrive for Business geo</span></span>

<span data-ttu-id="6c7a9-404">Azure Key Vault에 저장된 키 집합과 DEP를 연결합니다.</span><span class="sxs-lookup"><span data-stu-id="6c7a9-404">You associate a DEP with a set of keys stored in Azure Key Vault.</span></span> <span data-ttu-id="6c7a9-405">단일 지리적 위치(지리적이라고도 하는)의 모든 데이터에 DEP를 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="6c7a9-405">You apply a DEP to all of your data in one geographic location, also called a geo.</span></span> <span data-ttu-id="6c7a9-406">Office 365의 Multi-Geo 기능을 사용하는 경우, 지역별로 다른 키를 사용할 수 있는 DEP를 하나 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="6c7a9-406">If you use the multi-geo feature of Office 365, you can create one DEP per geo with the capability to use different keys per geo.</span></span> <span data-ttu-id="6c7a9-407">다중 지역을 사용하지 않는 경우 조직에서 SharePoint Online, 비즈니스용 OneDrive 및 Teams 파일의 사용을 위해 DEP를 하나 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6c7a9-407">If you are not using multi-geo, you can create one DEP in your organization for use with SharePoint Online, OneDrive for Business, and Teams files.</span></span> <span data-ttu-id="6c7a9-408">Microsoft 365는 DEP에 식별된 키를 사용하여 해당 지역에서 데이터를 암호화합니다.</span><span class="sxs-lookup"><span data-stu-id="6c7a9-408">Microsoft 365 uses the keys identified in the DEP to encrypt your data in that geo.</span></span> <span data-ttu-id="6c7a9-409">DEP를 만들려면 앞서 가온 키 Vault URI가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="6c7a9-409">To create the DEP, you need the Key Vault URIs you obtained earlier.</span></span> <span data-ttu-id="6c7a9-410">지침은 [각 Azure Key Vault 키에 대한 URI 가져오기를](#obtain-the-uri-for-each-azure-key-vault-key) 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="6c7a9-410">See [Obtain the URI for each Azure Key Vault key](#obtain-the-uri-for-each-azure-key-vault-key) for instructions.</span></span>
  
<span data-ttu-id="6c7a9-411">기한이지 기다해 주세요!</span><span class="sxs-lookup"><span data-stu-id="6c7a9-411">Remember!</span></span> <span data-ttu-id="6c7a9-412">DEP를 만들 때는 두 개의 다른 Azure Key Vaults에 있는 두 개의 키를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="6c7a9-412">When you create a DEP, you specify two keys that reside in two different Azure Key Vaults.</span></span> <span data-ttu-id="6c7a9-413">이러한 키가 두 개의 개별 Azure 지역에 있는지 확인하여 지리적 중복성을 보보입니다.</span><span class="sxs-lookup"><span data-stu-id="6c7a9-413">Ensure that these keys are located in two separate Azure regions to ensure geo-redundancy.</span></span>
  
<span data-ttu-id="6c7a9-414">DEP를 만들려면 클라우드 관리 기능을 사용하여 SharePoint Online에 원격으로 Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="6c7a9-414">To create a DEP, you need to remotely connect to SharePoint Online by using Windows PowerShell.</span></span>
  
1. <span data-ttu-id="6c7a9-415">로컬 컴퓨터에서 조직에서 전역 관리자 권한을 가있는 회사 또는 학교 계정을 사용하여 [SharePoint Online Powershell에 연결합니다.](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online?view=sharepoint-ps)</span><span class="sxs-lookup"><span data-stu-id="6c7a9-415">On your local computer, using a work or school account that has global administrator permissions in your organization, [Connect to SharePoint Online Powershell](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online?view=sharepoint-ps).</span></span>

2. <span data-ttu-id="6c7a9-416">Microsoft SharePoint Online 관리 셸에서 다음과 같이 Register-SPODataEncryptionPolicy cmdlet을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="6c7a9-416">In the Microsoft SharePoint Online Management Shell, run the Register-SPODataEncryptionPolicy cmdlet as follows:</span></span>

   ```powershell
   Register-SPODataEncryptionPolicy -Identity <SPOAdminSiteUrl> -PrimaryKeyVaultName <PrimaryKeyVaultName> -PrimaryKeyName <PrimaryKeyName> -PrimaryKeyVersion <PrimaryKeyVersion> -SecondaryKeyVaultName <SecondaryKeyVaultName> -SecondaryKeyName <SecondaryKeyName> -SecondaryKeyVersion <SecondaryKeyVersion>
   ```

   <span data-ttu-id="6c7a9-417">DEP를 등록하면 해당 지역의 데이터에서 암호화가 시작됩니다.</span><span class="sxs-lookup"><span data-stu-id="6c7a9-417">When you register the DEP, encryption begins on the data in the geo.</span></span> <span data-ttu-id="6c7a9-418">이 프로세스를 완료하려면 다소 시간이 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6c7a9-418">This can take some time.</span></span>

### <a name="validate-file-encryption"></a><span data-ttu-id="6c7a9-419">파일 암호화 유효성 검사</span><span class="sxs-lookup"><span data-stu-id="6c7a9-419">Validate file encryption</span></span>

 <span data-ttu-id="6c7a9-420">SharePoint Online, 비즈니스용 OneDrive 및 Teams 파일의 암호화가 유효성을 검사하려면 [SharePoint Online PowerShell에](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell?view=exchange-ps)연결한 다음 Get-SPODataEncryptionPolicy cmdlet을 사용하여 테넌트의 상태를 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="6c7a9-420">To validate encryption of SharePoint Online, OneDrive for Business, and Teams files, [connect to SharePoint Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell?view=exchange-ps), and then use the Get-SPODataEncryptionPolicy cmdlet to check the status of your tenant.</span></span> <span data-ttu-id="6c7a9-421">_고객 키_ 암호화가 사용하도록 **설정되었고** 모든 사이트의 파일이 암호화된 경우 State 속성은 등록된 값을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="6c7a9-421">The _State_ property returns a value of **registered** if Customer Key encryption is enabled and all files in all sites have been encrypted.</span></span> <span data-ttu-id="6c7a9-422">암호화가 계속 진행 중인 경우 이 cmdlet은 어떤 사이트에서 완료하는지에 대한 정보를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="6c7a9-422">If encryption is still in progress, this cmdlet provides information on what percentage of sites is complete.</span></span>

## <a name="related-articles"></a><span data-ttu-id="6c7a9-423">관련 문서</span><span class="sxs-lookup"><span data-stu-id="6c7a9-423">Related articles</span></span>

- [<span data-ttu-id="6c7a9-424">고객 키를 사용한 서비스 암호화</span><span class="sxs-lookup"><span data-stu-id="6c7a9-424">Service encryption with Customer Key</span></span>](customer-key-overview.md)

- [<span data-ttu-id="6c7a9-425">고객 키 관리</span><span class="sxs-lookup"><span data-stu-id="6c7a9-425">Manage Customer Key</span></span>](customer-key-manage.md)

- [<span data-ttu-id="6c7a9-426">고객 키 또는 가용성 키 롤 또는 회전</span><span class="sxs-lookup"><span data-stu-id="6c7a9-426">Roll or rotate a Customer Key or an availability key</span></span>](customer-key-availability-key-roll.md)

- [<span data-ttu-id="6c7a9-427">Availability 키에 대해 알아보기</span><span class="sxs-lookup"><span data-stu-id="6c7a9-427">Learn about the availability key</span></span>](customer-key-availability-key-understand.md)

- [<span data-ttu-id="6c7a9-428">서비스 암호화</span><span class="sxs-lookup"><span data-stu-id="6c7a9-428">Service Encryption</span></span>](office-365-service-encryption.md)
