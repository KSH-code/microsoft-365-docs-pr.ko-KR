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
description: Microsoft 365 for Exchange Online, 비즈니스용 Skype, SharePoint Online, 비즈니스용 OneDrive 및 팀 파일에 대 한 고객 키를 설정 하는 방법을 알아봅니다.
ms.openlocfilehash: 32af637fca91c1aa3abc0853215476d55c0f18a3
ms.sourcegitcommit: dffb9b72acd2e0bd286ff7e79c251e7ec6e8ecae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/17/2020
ms.locfileid: "47949564"
---
# <a name="set-up-customer-key"></a><span data-ttu-id="d6e44-103">고객 키 설정</span><span class="sxs-lookup"><span data-stu-id="d6e44-103">Set up Customer Key</span></span>

<span data-ttu-id="d6e44-104">고객 키를 사용 하 여 조직의 암호화 키를 제어 하 고 microsoft 365을 구성 하 여 Microsoft 데이터 센터의 휴지 상태에서 데이터를 암호화 합니다.</span><span class="sxs-lookup"><span data-stu-id="d6e44-104">With Customer Key, you control your organization's encryption keys and then configure Microsoft 365 to use them to encrypt your data at rest in Microsoft's data centers.</span></span> <span data-ttu-id="d6e44-105">즉, 고객 키를 사용 하 여 고객은 해당 키를 포함 하는 암호화 계층을 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d6e44-105">In other words, Customer Key allows customers to add a layer of encryption that belongs to them, with their keys.</span></span> <span data-ttu-id="d6e44-106">미사용 데이터에는 SharePoint Online 및 비즈니스용 OneDrive에 저장되어 있는 사서함과 파일에 저장된 Exchange Online 및 비즈니스용 Skype의 데이터를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="d6e44-106">Data at rest includes data from Exchange Online and Skype for Business that is stored in mailboxes and files that are stored in SharePoint Online and OneDrive for Business.</span></span>

<span data-ttu-id="d6e44-107">Office 365에 대해 고객 키를 사용 하려면 먼저 Azure를 설정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d6e44-107">You must set up Azure before you can use Customer Key for Office 365.</span></span> <span data-ttu-id="d6e44-108">이 항목에서는 필요한 Azure 리소스를 만들고 구성 하기 위해 수행 해야 하는 단계를 설명 하 고 Office 365에서 고객 키를 설정 하는 단계를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="d6e44-108">This topic describes the steps you need to follow to create and configure the required Azure resources and then provides the steps for setting up Customer Key in Office 365.</span></span> <span data-ttu-id="d6e44-109">Azure 설치를 완료 한 후에는 조직의 사서함과 파일에 할당할 정책 및 키를 결정 합니다.</span><span class="sxs-lookup"><span data-stu-id="d6e44-109">After you have completed Azure setup, you determine which policy, and therefore, which keys, to assign to mailboxes and files in your organization.</span></span> <span data-ttu-id="d6e44-110">정책을 할당 하지 않을 사서함과 파일은 Microsoft에서 제어 및 관리 하는 암호화 정책을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="d6e44-110">Mailboxes and files for which you don't assign a policy will use encryption policies that are controlled and managed by Microsoft.</span></span> <span data-ttu-id="d6e44-111">고객 키에 대 한 자세한 내용을 보거나 일반적인 개요를 보려면 [Office 365에서 고객 키를 사용한 서비스 암호화](customer-key-overview.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="d6e44-111">For more information about Customer Key, or for a general overview, see [Service encryption with Customer Key in Office 365](customer-key-overview.md).</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="d6e44-112">이 항목의 모범 사례를 따르는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="d6e44-112">We strongly recommend that you follow the best practices in this topic.</span></span> <span data-ttu-id="d6e44-113">이를 **팁** 및 **중요**로 지칭 합니다.</span><span class="sxs-lookup"><span data-stu-id="d6e44-113">These are called out as **TIP** and **IMPORTANT**.</span></span> <span data-ttu-id="d6e44-114">고객 키를 사용 하 여 전체 조직에 해당 하는 범위를 갖는 루트 암호화 키를 제어할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d6e44-114">Customer Key gives you control over root encryption keys whose scope can be as large as your entire organization.</span></span> <span data-ttu-id="d6e44-115">즉, 이러한 키를 사용한 실수에 큰 영향을 줄 수 있으며 서비스 중단 또는 irrevocable 데이터 손실을 초래할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d6e44-115">This means that mistakes made with these keys can have a broad impact and may result in service interruptions or irrevocable loss of your data.</span></span>
  
## <a name="before-you-set-up-customer-key"></a><span data-ttu-id="d6e44-116">Customer 키를 설정 하기 전에</span><span class="sxs-lookup"><span data-stu-id="d6e44-116">Before you set up Customer Key</span></span>

<span data-ttu-id="d6e44-117">시작 하기 전에 조직에 적합 한 라이선스를 보유 하 고 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="d6e44-117">Before you get started, ensure that you have the appropriate licensing for your organization.</span></span> <span data-ttu-id="d6e44-118">Office 365에서 2020 년 4 월 1 일부 터 M365 E5, M365 E5 규격 및 M365 E5 Information Protection & 관리 Sku 365에 제공 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d6e44-118">Starting April 1, 2020, Customer Key in Office 365 is offered in Office 365 E5, M365 E5, M365 E5 Compliance, and M365 E5 Information Protection & Governance SKUs.</span></span> <span data-ttu-id="d6e44-119">Office 365 고급 규정 준수 SKU가 더 이상 조달 새 라이선스를 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="d6e44-119">Office 365 Advanced Compliance SKU is no longer available for procuring new licenses.</span></span> <span data-ttu-id="d6e44-120">기존 Office 365 고급 규정 준수 라이선스는 계속 지원 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d6e44-120">Existing Office 365 Advanced Compliance licenses will continue to be supported.</span></span>

<span data-ttu-id="d6e44-121">이 항목의 개념과 절차를 이해 하려면 [Azure 키 보관소](https://docs.microsoft.com/azure/key-vault/) 설명서를 검토 하십시오.</span><span class="sxs-lookup"><span data-stu-id="d6e44-121">To understand the concepts and procedures in this topic, review the [Azure Key Vault](https://docs.microsoft.com/azure/key-vault/) documentation.</span></span> <span data-ttu-id="d6e44-122">또한 azure에서 사용 되는 용어 (예: [AZURE AD 테 넌 트](https://docs.microsoft.com/previous-versions/azure/azure-services/jj573650(v=azure.100)#what-is-an-azure-ad-tenant))를 익힙니다.</span><span class="sxs-lookup"><span data-stu-id="d6e44-122">Also, become familiar with the terms used in Azure, for example, [Azure AD tenant](https://docs.microsoft.com/previous-versions/azure/azure-services/jj573650(v=azure.100)#what-is-an-azure-ad-tenant).</span></span>

<span data-ttu-id="d6e44-123">FastTrack은 고객 키를 등록 하는 데 사용 되는 필수 테 넌 트 및 서비스 구성 정보를 수집 하는 데만 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d6e44-123">FastTrack is only used to collect the required tenant and service configuration information used to register for Customer Key.</span></span> <span data-ttu-id="d6e44-124">고객 키 제공은 FastTrack을 통해 게시 되므로 사용자와 파트너가 모두 동일한 방법을 사용 하 여 필요한 정보를 제출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d6e44-124">The Customer Key Offers are published via FastTrack so that it is convenient for you and our partners to submit the required information using the same method.</span></span> <span data-ttu-id="d6e44-125">FastTrack을 사용 하면 제공 되는 데이터를 쉽게 보관할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d6e44-125">FastTrack also makes it easy to archive the data that you provide in the Offer.</span></span>
  
<span data-ttu-id="d6e44-126">설명서 외에 추가 지원이 필요한 경우에는 MCS (Microsoft 컨설팅 서비스), PFE (프리미어 현장 엔지니어링) 또는 Microsoft 파트너에 게 문의 하세요.</span><span class="sxs-lookup"><span data-stu-id="d6e44-126">If you need additional support beyond the documentation, contact Microsoft Consulting Services (MCS), Premier Field Engineering (PFE), or a Microsoft partner for assistance.</span></span> <span data-ttu-id="d6e44-127">설명서를 포함 하 여 고객 키에 대 한 의견을 제공 하려면 아이디어, 제안 사항 및 전망을 customerkeyfeedback@microsoft.com으로 전송 합니다.</span><span class="sxs-lookup"><span data-stu-id="d6e44-127">To provide feedback on Customer Key, including the documentation, send your ideas, suggestions, and perspectives to customerkeyfeedback@microsoft.com.</span></span>
  
## <a name="overview-of-steps-to-set-up-customer-key"></a><span data-ttu-id="d6e44-128">고객 키 설정 단계 개요</span><span class="sxs-lookup"><span data-stu-id="d6e44-128">Overview of steps to set up Customer Key</span></span>

<span data-ttu-id="d6e44-129">고객 키를 설정 하려면 나열 된 순서 대로 다음 작업을 완료 하세요.</span><span class="sxs-lookup"><span data-stu-id="d6e44-129">To set up Customer Key, complete these tasks in the listed order.</span></span> <span data-ttu-id="d6e44-130">이 문서의 나머지 부분에서는 각 작업에 대 한 자세한 지침을 제공 하거나 프로세스의 각 단계에 대 한 추가 정보로 연결 되는 내용을 소개 합니다.</span><span class="sxs-lookup"><span data-stu-id="d6e44-130">The rest of this article provides detailed instructions for each task, or links out to more information for each step in the process.</span></span>
  
<span data-ttu-id="d6e44-131">**Azure 및 Microsoft FastTrack:**</span><span class="sxs-lookup"><span data-stu-id="d6e44-131">**In Azure and Microsoft FastTrack:**</span></span>
  
<span data-ttu-id="d6e44-132">이러한 작업의 대부분은 Azure PowerShell에 원격으로 연결 하 여 완료 합니다.</span><span class="sxs-lookup"><span data-stu-id="d6e44-132">You will complete most of these tasks by remotely connecting to Azure PowerShell.</span></span> <span data-ttu-id="d6e44-133">최상의 결과를 위해 Azure PowerShell의 버전 4.4.0 이상을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="d6e44-133">For best results, use version 4.4.0 or later of Azure PowerShell.</span></span>
  
- [<span data-ttu-id="d6e44-134">두 개의 새 Azure 구독을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="d6e44-134">Create two new Azure subscriptions</span></span>](#create-two-new-azure-subscriptions)

- [<span data-ttu-id="d6e44-135">필수 보존 기간을 사용 하도록 Azure 구독 등록</span><span class="sxs-lookup"><span data-stu-id="d6e44-135">Register Azure subscriptions to use a mandatory retention period</span></span>](#register-azure-subscriptions-to-use-a-mandatory-retention-period)

  <span data-ttu-id="d6e44-136">등록에는 영업일 중 근무일까지 소요 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d6e44-136">Registration can take from one to five business days.</span></span>

- [<span data-ttu-id="d6e44-137">Office 365에 대 한 고객 키를 정품 인증 하기 위한 요청 제출</span><span class="sxs-lookup"><span data-stu-id="d6e44-137">Submit a request to activate Customer Key for Office 365</span></span>](#submit-a-request-to-activate-customer-key-for-office-365)

<span data-ttu-id="d6e44-138">새로운 두 Azure 구독을 만든 후에는 Microsoft FastTrack 포털에서 호스팅되는 웹 양식을 완료 하 여 해당 하는 고객 키 제공 요청을 제출 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d6e44-138">Once you've created the two new Azure subscriptions, you'll need to submit the appropriate Customer Key offer request by completing a web form that is hosted in the Microsoft FastTrack portal.</span></span> <span data-ttu-id="d6e44-139">**FastTrack 팀은 고객 키에 대 한 지원을 제공 하지 않습니다. Office는 FastTrack 포털을 사용 하 여 양식을 전송 하 고 고객 키에 대 한 관련 서비스를 추적 하는 데 도움이 됩니다**.</span><span class="sxs-lookup"><span data-stu-id="d6e44-139">**The FastTrack team doesn't provide assistance with Customer Key. Office simply uses the FastTrack portal to allow you to submit the form and to help us track the relevant offers for Customer Key**.</span></span>

- [<span data-ttu-id="d6e44-140">각 구독에 프리미엄 Azure 키 자격 증명 모음 만들기</span><span class="sxs-lookup"><span data-stu-id="d6e44-140">Create a premium Azure Key Vault in each subscription</span></span>](#create-a-premium-azure-key-vault-in-each-subscription)

- [<span data-ttu-id="d6e44-141">각 키 자격 증명 모음에 사용 권한 할당</span><span class="sxs-lookup"><span data-stu-id="d6e44-141">Assign permissions to each key vault</span></span>](#assign-permissions-to-each-key-vault)

- [<span data-ttu-id="d6e44-142">키 자격 증명 모음에서 일시 삭제를 사용 하도록 설정 하 고 확인</span><span class="sxs-lookup"><span data-stu-id="d6e44-142">Enable and then confirm soft delete on your key vaults</span></span>](#enable-and-then-confirm-soft-delete-on-your-key-vaults)

- [<span data-ttu-id="d6e44-143">키를 만들거나 가져오는 방법으로 각 키 보관소에 키를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="d6e44-143">Add a key to each key vault either by creating or importing a key</span></span>](#add-a-key-to-each-key-vault-either-by-creating-or-importing-a-key)

- [<span data-ttu-id="d6e44-144">키의 복구 수준 확인</span><span class="sxs-lookup"><span data-stu-id="d6e44-144">Check the recovery level of your keys</span></span>](#check-the-recovery-level-of-your-keys)

- [<span data-ttu-id="d6e44-145">Azure 키 자격 증명 모음 백업</span><span class="sxs-lookup"><span data-stu-id="d6e44-145">Back up Azure Key Vault</span></span>](#back-up-azure-key-vault)

- [<span data-ttu-id="d6e44-146">Azure 키 자격 증명 모음 구성 설정 확인</span><span class="sxs-lookup"><span data-stu-id="d6e44-146">Validate Azure Key Vault configuration settings</span></span>](#validate-azure-key-vault-configuration-settings)

- [<span data-ttu-id="d6e44-147">각 Azure Key Vault 키에 대 한 URI 가져오기</span><span class="sxs-lookup"><span data-stu-id="d6e44-147">Obtain the URI for each Azure Key Vault key</span></span>](#obtain-the-uri-for-each-azure-key-vault-key)

<span data-ttu-id="d6e44-148">**Office 365에서 다음을 수행 합니다.**</span><span class="sxs-lookup"><span data-stu-id="d6e44-148">**In Office 365:**</span></span>
  
<span data-ttu-id="d6e44-149">Exchange Online 및 비즈니스용 Skype:</span><span class="sxs-lookup"><span data-stu-id="d6e44-149">Exchange Online and Skype for Business:</span></span>
  
- [<span data-ttu-id="d6e44-150">Exchange Online 및 비즈니스용 Skype에서 사용 하기 위한 DEP (데이터 암호화 정책) 만들기</span><span class="sxs-lookup"><span data-stu-id="d6e44-150">Create a data encryption policy (DEP) for use with Exchange Online and Skype for Business</span></span>](#create-a-data-encryption-policy-dep-for-use-with-exchange-online-and-skype-for-business)

- [<span data-ttu-id="d6e44-151">사서함에 DEP 할당</span><span class="sxs-lookup"><span data-stu-id="d6e44-151">Assign a DEP to a mailbox</span></span>](#assign-a-dep-to-a-mailbox)

- [<span data-ttu-id="d6e44-152">사서함 암호화 유효성 검사</span><span class="sxs-lookup"><span data-stu-id="d6e44-152">Validate mailbox encryption</span></span>](#validate-mailbox-encryption)

<span data-ttu-id="d6e44-153">SharePoint Online 및 비즈니스용 OneDrive:</span><span class="sxs-lookup"><span data-stu-id="d6e44-153">SharePoint Online and OneDrive for Business:</span></span>
  
- [<span data-ttu-id="d6e44-154">각 SharePoint Online 및 비즈니스용 OneDrive 지역에 대 한 DEP (데이터 암호화 정책)를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="d6e44-154">Create a data encryption policy (DEP) for each SharePoint Online and OneDrive for Business geo</span></span>](#create-a-data-encryption-policy-dep-for-each-sharepoint-online-and-onedrive-for-business-geo)

- [<span data-ttu-id="d6e44-155">SharePoint Online, 비즈니스용 OneDrive 및 팀 파일에 대 한 파일 암호화 확인</span><span class="sxs-lookup"><span data-stu-id="d6e44-155">Validate file encryption for SharePoint Online, OneDrive for Business, and Teams files</span></span>](#validate-file-encryption)

## <a name="complete-tasks-in-azure-key-vault-and-microsoft-fasttrack-for-customer-key"></a><span data-ttu-id="d6e44-156">Azure Key Vault의 완료 작업 및 고객 키 용 Microsoft FastTrack</span><span class="sxs-lookup"><span data-stu-id="d6e44-156">Complete tasks in Azure Key Vault and Microsoft FastTrack for Customer Key</span></span>

<span data-ttu-id="d6e44-157">Azure Key Vault에서 이러한 작업을 완료 합니다.</span><span class="sxs-lookup"><span data-stu-id="d6e44-157">Complete these tasks in Azure Key Vault.</span></span> <span data-ttu-id="d6e44-158">Exchange Online 및 비즈니스용 Skype, SharePoint Online, 비즈니스용 OneDrive, 팀 파일 또는 Office 365에서 지원 되는 모든 서비스에 대해 고객 키를 설정할지 여부에 관계 없이 이러한 단계를 완료 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d6e44-158">You'll need to complete these steps regardless of whether you intend to set up Customer Key for Exchange Online and Skype for Business or for SharePoint Online, OneDrive for Business, and Teams files, or for all supported services in Office 365.</span></span>
  
### <a name="create-two-new-azure-subscriptions"></a><span data-ttu-id="d6e44-159">두 개의 새 Azure 구독을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="d6e44-159">Create two new Azure subscriptions</span></span>

<span data-ttu-id="d6e44-160">고객 키에는 두 개의 Azure 구독이 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="d6e44-160">Customer Key requires two Azure subscriptions.</span></span> <span data-ttu-id="d6e44-161">최상의 방법으로는 고객 키와 함께 사용할 새로운 Azure 구독을 만드는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="d6e44-161">As a best practice, Microsoft recommends that you create new Azure subscriptions for use with Customer Key.</span></span> <span data-ttu-id="d6e44-162">Azure Key Vault 키는 동일한 Azure Active Directory (Microsoft Azure Active Directory) 테 넌 트의 응용 프로그램에 대해서만 권한을 부여할 수 있으며, 조직에서 DEPs를 할당할 때 사용 하는 것과 동일한 Azure AD 테 넌 트를 사용 하 여 새 구독을 만들어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d6e44-162">Azure Key Vault keys can only be authorized for applications in the same Azure Active Directory (Microsoft Azure Active Directory) tenant, you must create the new subscriptions using the same Azure AD tenant used with your organization where the DEPs will be assigned.</span></span> <span data-ttu-id="d6e44-163">예를 들어 조직에서 전역 관리자 권한이 있는 회사 또는 학교 계정을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="d6e44-163">For example, using your work or school account that has global administrator privileges in your organization.</span></span> <span data-ttu-id="d6e44-164">자세한 단계는 [Azure for](https://azure.microsoft.com/documentation/articles/sign-up-organization/)a a a a a a a a a a a as를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="d6e44-164">For detailed steps, see [Sign up for Azure as an organization](https://azure.microsoft.com/documentation/articles/sign-up-organization/).</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="d6e44-165">고객 키에는 각 DEP (데이터 암호화 정책)에 대 한 두 개의 키가 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="d6e44-165">Customer Key requires two keys for each data encryption policy (DEP).</span></span> <span data-ttu-id="d6e44-166">이를 위해서는 두 개의 Azure 구독을 만들어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d6e44-166">In order to achieve this, you must create two Azure subscriptions.</span></span> <span data-ttu-id="d6e44-167">조직의 개별 구성원이 각 구독에서 하나의 키를 구성 하는 것이 가장 좋은 방법입니다.</span><span class="sxs-lookup"><span data-stu-id="d6e44-167">As a best practice, Microsoft recommends that you have separate members of your organization configure one key in each subscription.</span></span> <span data-ttu-id="d6e44-168">또한 이러한 Azure 구독은 Office 365의 암호화 키를 관리 하는 데에만 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d6e44-168">In addition, these Azure subscriptions should only be used to administer encryption keys for Office 365.</span></span> <span data-ttu-id="d6e44-169">이렇게 하면 운영자 중 한 명에 게 실수로 또는 악의적으로 삭제 되거나 자신이 담당 하는 키를 잘못 관리 하는 경우를 대비해 조직이 보호 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d6e44-169">This protects your organization in case one of your operators accidentally, intentionally, or maliciously deletes or otherwise mismanages the keys for which they are responsible.</span></span> <br/> <span data-ttu-id="d6e44-170">Azure Key Vault 리소스를 관리 하는 데에만 사용 되는 새 Azure 구독을 고객 키와 함께 사용 하도록 설정 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="d6e44-170">We recommend that you set up new Azure subscriptions that are solely used for managing Azure Key Vault resources for use with Customer Key.</span></span> <span data-ttu-id="d6e44-171">조직에 대해 만들 수 있는 Azure 구독 수에는 실질적인 제한이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="d6e44-171">There is no practical limit to the number of Azure subscriptions that you can create for your organization.</span></span> <span data-ttu-id="d6e44-172">이러한 모범 사례를 따르면 고객 키에서 사용 하는 리소스를 관리 하는 동안 인간 오류가 발생 하는 영향은 최소화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d6e44-172">Following these best practices will minimize the impact of human error while helping to manage the resources used by Customer Key.</span></span>
  
### <a name="submit-a-request-to-activate-customer-key-for-office-365"></a><span data-ttu-id="d6e44-173">Office 365에 대 한 고객 키를 정품 인증 하기 위한 요청 제출</span><span class="sxs-lookup"><span data-stu-id="d6e44-173">Submit a request to activate Customer Key for Office 365</span></span>

<span data-ttu-id="d6e44-174">Azure 단계를 완료 한 후에는 [Microsoft FastTrack 포털](https://fasttrack.microsoft.com/)에서 제공 요청을 제출 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d6e44-174">Once you've completed the Azure steps, you'll need to submit an offer request in the [Microsoft FastTrack portal](https://fasttrack.microsoft.com/).</span></span> <span data-ttu-id="d6e44-175">FastTrack 웹 포털을 통해 요청을 제출 하면 Microsoft는 Azure 키 자격 증명 모음 구성 데이터와 사용자가 제공한 연락처 정보를 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="d6e44-175">Once you have submitted a request through the FastTrack web portal, Microsoft verifies the Azure Key Vault configuration data and contact information you provided.</span></span> <span data-ttu-id="d6e44-176">조직의 승인 된 관리자와 관련 하 여 제안 양식에서 선택한 항목은 고객 키 등록을 완료 하는 데 필수적이 고 필수적입니다.</span><span class="sxs-lookup"><span data-stu-id="d6e44-176">The selections that you make in the offer form regarding the authorized officers of your organization is critical and necessary for completion of Customer Key registration.</span></span> <span data-ttu-id="d6e44-177">양식에서 선택한 조직의 직원은 고객 키 데이터 암호화 정책에 사용 되는 모든 키를 해지 하 고 파기 하기 위한 요청의 신뢰성을 보장 하는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d6e44-177">The officers of your organization that you select in the form will be the used to ensure the authenticity of any request to revoke and destroy all keys used with a Customer Key data encryption policy.</span></span> <span data-ttu-id="d6e44-178">이 단계를 한 번 수행 하 여 Exchange Online 및 비즈니스용 Skype를 위한 고객 키를 정품 인증 하 고 SharePoint Online 및 비즈니스용 OneDrive에 대 한 고객 키를 활성화 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d6e44-178">You'll need to do this step once to activate Customer Key for Exchange Online and Skype for Business coverage and a second time to activate Customer Key for SharePoint Online and OneDrive for Business.</span></span>
  
<span data-ttu-id="d6e44-179">고객 키를 정품 인증 하기 위한 제안을 제출 하려면 다음 단계를 완료 합니다.</span><span class="sxs-lookup"><span data-stu-id="d6e44-179">To submit an offer to activate Customer Key, complete these steps:</span></span>
  
1. <span data-ttu-id="d6e44-180">조직에서 전역 관리자 권한이 있는 회사 또는 학교 계정을 사용 하 여 [Microsoft FastTrack 포털](https://fasttrack.microsoft.com/)에 로그인 합니다.</span><span class="sxs-lookup"><span data-stu-id="d6e44-180">Using a work or school account that has global administrator permissions in your organization, log in to the [Microsoft FastTrack portal](https://fasttrack.microsoft.com/).</span></span>

2. <span data-ttu-id="d6e44-181">로그인 한 후 **대시보드로**이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="d6e44-181">Once you're logged in, browse to the **Dashboard**.</span></span>

3. <span data-ttu-id="d6e44-182">탐색 모음에서 **배포** 를 선택 **하거나** **배포 정보 카드에서** **모든 배포 리소스 보기** 를 선택 하 고 현재 서비스 목록을 검토 합니다.</span><span class="sxs-lookup"><span data-stu-id="d6e44-182">Choose **Deploy** from the navigation bar **OR** select **View all deployment resources** on the **Deploy** information card, and review the list of current offers.</span></span>

4. <span data-ttu-id="d6e44-183">고객에 게 제공 되는 혜택에 대 한 정보 카드를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="d6e44-183">Choose the information card for the offer that applies to you:</span></span>

   - <span data-ttu-id="d6e44-184">**Exchange Online 및 비즈니스용 Skype:** **Exchange online 서비스에 대 한 암호화 키 도움말 요청** 을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="d6e44-184">**Exchange Online and Skype for Business:** Choose the **Request encryption key help for Exchange online** offer.</span></span>

   - <span data-ttu-id="d6e44-185">**SharePoint Online, OneDrive 및 팀 파일:** **Sharepoint 및 OneDrive 제공에 대 한 요청 암호화 키 도움말** 을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="d6e44-185">**SharePoint Online, OneDrive, and Teams files:** Choose the **Request encryption key help for Sharepoint and OneDrive** offer.</span></span>

5. <span data-ttu-id="d6e44-186">제안 세부 정보를 검토 한 후에는 **2 단계 계속을**선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="d6e44-186">Once you've reviewed the offer details, choose **Continue to step 2**.</span></span>

6. <span data-ttu-id="d6e44-187">제공 양식에서 해당 하는 모든 정보 및 요청 된 정보를 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="d6e44-187">Fill out all applicable details and requested information on the offer form.</span></span> <span data-ttu-id="d6e44-188">인증을 승인할 조직의 관리자가 선택한 사항에 특별히 주의 하 여 암호화 키와 데이터의 영구 및 복구할 수 없는 소멸을 승인 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d6e44-188">Pay particular attention to your selections for which officers of your organization you want to authorize to approve the permanent and irreversible destruction of encryption keys and data.</span></span> <span data-ttu-id="d6e44-189">양식을 완료 했으면 **제출을**선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="d6e44-189">Once you've completed the form, choose **Submit**.</span></span>

### <a name="register-azure-subscriptions-to-use-a-mandatory-retention-period"></a><span data-ttu-id="d6e44-190">필수 보존 기간을 사용 하도록 Azure 구독 등록</span><span class="sxs-lookup"><span data-stu-id="d6e44-190">Register Azure subscriptions to use a mandatory retention period</span></span>

<span data-ttu-id="d6e44-191">루트 암호화 키의 임시 또는 영구 손실은 매우 방해가 되거나 서비스 작업에 치명적이 될 수 있으며 데이터 손실이 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d6e44-191">The temporary or permanent loss of root encryption keys can be very disruptive or even catastrophic to service operation and can result in data loss.</span></span> <span data-ttu-id="d6e44-192">이러한 이유로, 고객 키와 함께 사용 되는 리소스에는 강력한 보호가 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="d6e44-192">For this reason, the resources used with Customer Key require strong protection.</span></span> <span data-ttu-id="d6e44-193">고객 키와 함께 사용 되는 모든 Azure 리소스는 기본 구성 외에도 보호 메커니즘을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="d6e44-193">All the Azure resources that are used with Customer Key offer protection mechanisms beyond the default configuration.</span></span> <span data-ttu-id="d6e44-194">즉시 및 irrevocable 취소를 방지 하는 방식으로 Azure 구독에 태그를 지정 하거나 등록할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d6e44-194">Azure subscriptions can be tagged or registered in a way that will prevent immediate and irrevocable cancellation.</span></span> <span data-ttu-id="d6e44-195">이를 필수 보존 기간 등록 이라고 합니다.</span><span class="sxs-lookup"><span data-stu-id="d6e44-195">This is referred to as registering for a mandatory retention period.</span></span> <span data-ttu-id="d6e44-196">필수 보존 기간 동안 Azure 구독을 등록 하는 데 필요한 단계에는 Microsoft 365 팀과 공동 작업이 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="d6e44-196">The steps required to register Azure subscriptions for a mandatory retention period require collaboration with the Microsoft 365 team.</span></span> <span data-ttu-id="d6e44-197">이 프로세스는 영업일 이하의 근무일까지 소요 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d6e44-197">This process can take from one to five business days.</span></span> <span data-ttu-id="d6e44-198">이전에는이를 "취소 안 함"이 라고도 합니다.</span><span class="sxs-lookup"><span data-stu-id="d6e44-198">Previously, this was sometimes referred to as "Do Not Cancel".</span></span>
  
<span data-ttu-id="d6e44-199">Microsoft 365 팀에 연락 하기 전에 고객 키와 함께 사용 하는 각 Azure 구독에 대해 다음 단계를 수행 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d6e44-199">Before contacting the Microsoft 365 team, you must perform the following steps for each Azure subscription that you use with Customer Key.</span></span> <span data-ttu-id="d6e44-200">시작 하기 전에 [Azure PowerShell Az](https://docs.microsoft.com/powershell/azure/new-azureps-module-az) 모듈이 설치 되어 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="d6e44-200">Ensure that you have the [Azure PowerShell Az](https://docs.microsoft.com/powershell/azure/new-azureps-module-az) module installed before you start.</span></span>
  
1. <span data-ttu-id="d6e44-201">Azure PowerShell을 사용 하 여 로그인 합니다.</span><span class="sxs-lookup"><span data-stu-id="d6e44-201">Sign in with Azure PowerShell.</span></span> <span data-ttu-id="d6e44-202">자세한 내용은 [Azure PowerShell을 사용 하 여 로그인](https://docs.microsoft.com/powershell/azure/authenticate-azureps)을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="d6e44-202">For instructions, see [Sign in with Azure PowerShell](https://docs.microsoft.com/powershell/azure/authenticate-azureps).</span></span>

2. <span data-ttu-id="d6e44-203">AzProviderFeature cmdlet을 실행 하 여 구독을 등록 하 고 필수 보존 기간을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="d6e44-203">Run the Register-AzProviderFeature cmdlet to register your subscriptions to use a mandatory retention period.</span></span> <span data-ttu-id="d6e44-204">각 구독에 대해이 작업을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="d6e44-204">Perform this action for each subscription.</span></span>

   ```powershell
   Set-AzContext -SubscriptionId <SubscriptionId>
   Register-AzProviderFeature -FeatureName mandatoryRetentionPeriodEnabled -ProviderNamespace Microsoft.Resources
   ```

3. <span data-ttu-id="d6e44-205">Microsoft에 문의 하 여 해당 프로세스를 완료 합니다.</span><span class="sxs-lookup"><span data-stu-id="d6e44-205">Contact Microsoft to have the process finalized.</span></span> <span data-ttu-id="d6e44-206">SharePoint 및 비즈니스용 OneDrive 팀의 경우 [spock@microsoft.com](mailto:spock@microsoft.com)에 문의 하세요.</span><span class="sxs-lookup"><span data-stu-id="d6e44-206">For the SharePoint and OneDrive for Business team, contact [spock@microsoft.com](mailto:spock@microsoft.com).</span></span> <span data-ttu-id="d6e44-207">Exchange Online 및 비즈니스용 Skype에 대 한 자세한 내용은 [exock@microsoft.com](mailto:exock@microsoft.com)에 문의 하세요.</span><span class="sxs-lookup"><span data-stu-id="d6e44-207">For Exchange Online and Skype for Business, contact [exock@microsoft.com](mailto:exock@microsoft.com).</span></span> <span data-ttu-id="d6e44-208">전자 메일에 다음을 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="d6e44-208">Include the following in your email:</span></span>

   <span data-ttu-id="d6e44-209">**제목**: 다음에 대 한 고객 키 \<*Your tenant's fully-qualified domain name*\></span><span class="sxs-lookup"><span data-stu-id="d6e44-209">**Subject**: Customer Key for \<*Your tenant's fully-qualified domain name*\></span></span>

   <span data-ttu-id="d6e44-210">**Body**: 필수 보존 기간을 완료 하려는 구독 id입니다.</span><span class="sxs-lookup"><span data-stu-id="d6e44-210">**Body**: Subscription IDs for which you want to have the mandatory retention period finalized.</span></span>
   <span data-ttu-id="d6e44-211">각 구독에 대 한 AzProviderFeature의 출력입니다.</span><span class="sxs-lookup"><span data-stu-id="d6e44-211">The output of Get-AzProviderFeature for each subscription.</span></span>

   <span data-ttu-id="d6e44-212">이 프로세스를 완료 하는 데 필요한 SLA (서비스 수준 계약)는 Microsoft가 구독을 등록 하 여 필수 보존 기간을 사용 하도록 공지를 받은 경우 5 일 이내입니다.</span><span class="sxs-lookup"><span data-stu-id="d6e44-212">The Service Level Agreement (SLA) for completion of this process is five business days once Microsoft has been notified (and verified) that you have registered your subscriptions to use a mandatory retention period.</span></span>

4. <span data-ttu-id="d6e44-213">Microsoft에서 등록이 완료 되었음을 알리는 알림을 받으면 다음과 같이 AzProviderFeature 명령을 실행 하 여 등록 상태를 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="d6e44-213">Once you receive notification from Microsoft that registration is complete, verify the status of your registration by running the Get-AzProviderFeature command as follows.</span></span> <span data-ttu-id="d6e44-214">확인 된 경우 AzProviderFeature 명령은 **등록 상태** 속성에 대해 **등록** 된 값을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="d6e44-214">If verified, the Get-AzProviderFeature command returns a value of **Registered** for the **Registration State** property.</span></span> <span data-ttu-id="d6e44-215">각 구독에 대해이 작업을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="d6e44-215">Perform this action for each subscription.</span></span>

   ```powershell
   Set-AzContext -SubscriptionId <SubscriptionId>
   Get-AzProviderFeature -ProviderNamespace Microsoft.Resources -FeatureName mandatoryRetentionPeriodEnabled
   ```

5. <span data-ttu-id="d6e44-216">프로세스를 완료 하려면 AzResourceProvider 명령을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="d6e44-216">To complete the process, run the Register-AzResourceProvider command.</span></span> <span data-ttu-id="d6e44-217">각 구독에 대해이 작업을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="d6e44-217">Perform this action for each subscription.</span></span>

   ```powershell
   Set-AzContext -SubscriptionId <SubscriptionId>
   Register-AzResourceProvider -ProviderNamespace Microsoft.KeyVault
   ```

### <a name="create-a-premium-azure-key-vault-in-each-subscription"></a><span data-ttu-id="d6e44-218">각 구독에 프리미엄 Azure 키 자격 증명 모음 만들기</span><span class="sxs-lookup"><span data-stu-id="d6e44-218">Create a premium Azure Key Vault in each subscription</span></span>

<span data-ttu-id="d6e44-219">키 자격 증명 모음을 만드는 단계는 azure PowerShell을 설치 및 시작 하 고, Azure 구독에 연결 하 고, 리소스 그룹을 만들고, 해당 리소스 그룹에 키 자격 증명 모음을 만드는 과정을 안내 하는 [Azure Key Vault 시작](https://azure.microsoft.com/documentation/articles/key-vault-get-started/)에 설명 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d6e44-219">The steps to create a key vault are documented in [Getting Started with Azure Key Vault](https://azure.microsoft.com/documentation/articles/key-vault-get-started/), which guides you through installing and launching Azure PowerShell, connecting to your Azure subscription, creating a resource group, and creating a key vault in that resource group.</span></span>
  
<span data-ttu-id="d6e44-220">키 자격 증명 모음을 만들 때는 SKU: Standard 또는 Premium 중 하나를 선택 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d6e44-220">When you create a key vault, you must choose a SKU: either Standard or Premium.</span></span> <span data-ttu-id="d6e44-221">Standard SKU를 사용 하면 HSM (하드웨어 보안 모듈) 키 보호가 제공 되지 않으며 프리미엄 SKU는 키 자격 증명 키 보호를 위해 Hsm을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d6e44-221">The Standard SKU allows Azure Key Vault keys to be protected with software - there is no Hardware Security Module (HSM) key protection - and the Premium SKU allows the use of HSMs for protection of Key Vault keys.</span></span> <span data-ttu-id="d6e44-222">고객 키가 SKU를 사용 하는 키 보관소를 허용 하지만, Microsoft에서는 프리미엄 SKU만 사용 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="d6e44-222">Customer Key accepts key vaults that use either SKU, though Microsoft strongly recommends that you use only the Premium SKU.</span></span> <span data-ttu-id="d6e44-223">두 가지 유형의 키를 사용한 작업 비용은 같으므로, 각 HSM 보호 키에 대 한 월별 비용은 비용의 차이입니다.</span><span class="sxs-lookup"><span data-stu-id="d6e44-223">The cost of operations with keys of either type is the same, so the only difference in cost is the cost per month for each HSM-protected key.</span></span> <span data-ttu-id="d6e44-224">자세한 내용은 [키 자격 증명 모음 가격 산정](https://azure.microsoft.com/pricing/details/key-vault/) 을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="d6e44-224">See [Key Vault pricing](https://azure.microsoft.com/pricing/details/key-vault/) for details.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="d6e44-225">프로덕션 데이터에 대해 Premium SKU 키 보관소 및 HSM으로 보호 된 키를 사용 하 고 테스트 및 유효성 검사를 위해 Standard SKU 키 보관소와 키만 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="d6e44-225">Use the Premium SKU key vaults and HSM-protected keys for production data, and only use Standard SKU key vaults and keys for testing and validation purposes.</span></span>
  
<span data-ttu-id="d6e44-226">고객 키를 사용 하는 각 Microsoft 365 서비스에 대해 사용자가 만든 두 Azure 구독 각각에 키 자격 증명 모음을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="d6e44-226">For each Microsoft 365 service with which you will use Customer Key, create a key vault in each of the two Azure subscriptions that you created.</span></span> <span data-ttu-id="d6e44-227">예를 들어 Exchange Online 및 비즈니스용 Skype 전용 또는 SharePoint Online 및 비즈니스용 OneDrive 전용의 경우에는 하나의 자격 증명 모음만 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="d6e44-227">For example, for Exchange Online and Skype for Business only or SharePoint Online and OneDrive for Business only, you will create only one pair of vaults.</span></span> <span data-ttu-id="d6e44-228">Exchange Online 및 SharePoint Online 둘 다에 대해 고객 키를 사용 하도록 설정 하기 위해 두 쌍의 키 자격 증명 모음을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="d6e44-228">To enable Customer Key for both Exchange Online and SharePoint Online, you will create two pairs of key vaults.</span></span>
  
<span data-ttu-id="d6e44-229">자격 증명 모음을 연결할 데이터 암호화 정책의 용도를 반영 하는 키 보관소에 대 한 명명 규칙을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="d6e44-229">Use a naming convention for key vaults that reflects the intended use of the data encryption policy with which you will associate the vaults.</span></span> <span data-ttu-id="d6e44-230">명명 규칙 추천을 보려면 아래에서 모범 사례 섹션을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="d6e44-230">See the Best Practices section below for naming convention recommendations.</span></span>
  
<span data-ttu-id="d6e44-231">각 데이터 암호화 정책에 대해 쌍을 이룬 별도의 자격 증명 모음을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="d6e44-231">Create a separate, paired set of vaults for each data encryption policy.</span></span> <span data-ttu-id="d6e44-232">Exchange Online의 경우 사서함에 정책을 할당할 때 사용자가 데이터 암호화 정책의 범위를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="d6e44-232">For Exchange Online, the scope of a data encryption policy is chosen by you when you assign the policy to mailbox.</span></span> <span data-ttu-id="d6e44-233">사서함에는 정책이 하나만 할당 될 수 있으며 최대 50 개의 정책을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d6e44-233">A mailbox can have only one policy assigned, and you can create up to fifty policies.</span></span> <span data-ttu-id="d6e44-234">SharePoint Online의 경우 정책의 범위는 지리적 위치 또는 _지리적_으로 조직 내의 모든 데이터입니다.</span><span class="sxs-lookup"><span data-stu-id="d6e44-234">For SharePoint Online the scope of a policy is all of the data within an organization in a geographic location, or _geo_.</span></span>

<span data-ttu-id="d6e44-235">또한 키 보관소에는 저장소 용량 (매우 작음)과 키 보관소 로깅이 필요 하기 때문에 (키 보관소를 만드는 경우) 저장 된 데이터도 생성 해야 하므로 Azure 리소스 그룹을 만들어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d6e44-235">The creation of key vaults also requires the creation of Azure resource groups, since key vaults need storage capacity (though very small) and Key Vault logging, if enabled, also generates stored data.</span></span> <span data-ttu-id="d6e44-236">Microsoft는 별도의 관리자를 사용 하 여 각 리소스 그룹을 관리할 것을 권장 하 고, 관리를 모든 관련 고객 키 리소스를 관리 하는 관리자 집합과 맞추고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d6e44-236">As a best practice Microsoft recommends using separate administrators to manage each resource group, with the administration aligned with the set of administrators that will manage all related Customer Key resources.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="d6e44-237">가용성을 최대화 하기 위해 주요 자격 증명은 Microsoft 365 서비스에 가까운 지역에 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d6e44-237">To maximize availability, your key vaults should be in regions close to your Microsoft 365 service.</span></span> <span data-ttu-id="d6e44-238">예를 들어 Exchange Online 조직이 북미에 있는 경우 북미에 키 자격 증명 모음을 배치 합니다.</span><span class="sxs-lookup"><span data-stu-id="d6e44-238">For example, if your Exchange Online organization is in North America, place your key vaults in North America.</span></span> <span data-ttu-id="d6e44-239">Exchange Online 조직이 유럽에 있는 경우 키 보관소를 유럽에 배치 합니다.</span><span class="sxs-lookup"><span data-stu-id="d6e44-239">If your Exchange Online organization is in Europe, place your key vaults in Europe.</span></span><br/><span data-ttu-id="d6e44-240">키 자격 증명에 대 한 일반적인 접두사를 사용 하 고, 키 보관소와 키의 사용 및 범위 약어를 포함 하 고 (예: 보관소가 있는 Contoso SharePoint 서비스의 경우에는 해당 하는 이름 쌍이 Contoso-O365SP-VaultA1 및 Contoso-O365SP-VaultA2입니다.</span><span class="sxs-lookup"><span data-stu-id="d6e44-240">Use a common prefix for key vaults, and include an abbreviation of the use and scope of the key vault and keys (e.g., for the Contoso SharePoint service where the vaults will be located in North America, a possible pair of names is Contoso-O365SP-NA-VaultA1 and Contoso-O365SP-NA-VaultA2.</span></span> <span data-ttu-id="d6e44-241">자격 증명 이름은 Azure 내의 전역적으로 고유한 문자열이 되므로 필요한 이름이 다른 Azure 고객의 요청을 받아야 하는 경우에 대비 하 여 원하는 이름의 변형을 시도해 야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d6e44-241">Vault names are globally unique strings within Azure, so you may need to try variations of your desired names in case the desired names are already claimed by other Azure customers.</span></span> <span data-ttu-id="d6e44-242">7 월 2017 볼트 이름은 변경할 수 없으므로 설정 계획을 수립 하 고 두 번째 사용자를 사용 하 여 계획이 올바르게 실행 되는지 확인 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="d6e44-242">As of July 2017 vault names cannot be changed, so a best practice is to have a written plan for setup and use a second person to verify the plan is executed correctly.</span></span><br/><span data-ttu-id="d6e44-243">가능 하면 페어링되지 않은 지역에 자격 증명 모음을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="d6e44-243">If possible, create your vaults in non-paired regions.</span></span> <span data-ttu-id="d6e44-244">쌍을 이룬 Azure 지역에서 서비스 장애 도메인 별로 고가용성을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="d6e44-244">Paired Azure regions provide high availability across service failure domains.</span></span> <span data-ttu-id="d6e44-245">따라서 지역 쌍을 서로의 백업 지역으로 간주할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d6e44-245">Therefore, regional pairs can be thought of as each other's backup region.</span></span> <span data-ttu-id="d6e44-246">즉, 한 지역에 배치 된 Azure 리소스가 연결 된 지역을 통과 하는 내결함성을 자동으로 획득 합니다.</span><span class="sxs-lookup"><span data-stu-id="d6e44-246">This means that an Azure resource that is placed in one region is automatically gaining fault tolerance through the paired region.</span></span> <span data-ttu-id="d6e44-247">이러한 이유 때문에 지역이 연결 된 데이터 암호화 정책에서 사용 되는 두 개의 보관소에 대 한 영역을 선택 하는 것은 사용 중인 사용 가능한 영역의 총 두 영역만을 의미 합니다.</span><span class="sxs-lookup"><span data-stu-id="d6e44-247">For this reason, choosing regions for two vaults used in a data encryption policy where the regions are paired means that only a total of two regions of availability are in use.</span></span> <span data-ttu-id="d6e44-248">대부분의 지역에는 두 지역이 있으므로 아직 연결 되지 않은 영역을 선택할 수는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="d6e44-248">Most geographies only have two regions, so it's not yet possible to select non-paired regions.</span></span> <span data-ttu-id="d6e44-249">가능 하면 데이터 암호화 정책에 사용 되는 두 개의 보관소에 대해 쌍이 없는 두 개의 영역을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="d6e44-249">If possible, choose two non-paired regions for the two vaults used with a data encryption policy.</span></span> <span data-ttu-id="d6e44-250">이는 가용성의 총 4 지역에서 혜택을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="d6e44-250">This benefits from a total of four regions of availability.</span></span> <span data-ttu-id="d6e44-251">자세한 내용은 [Business 연속성 및 재해 복구 (BCDR):](https://docs.microsoft.com/azure/best-practices-availability-paired-regions) 현재 지역 쌍 목록의 Azure 연결 된 지역을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="d6e44-251">For more information, see [Business continuity and disaster recovery (BCDR): Azure Paired Regions](https://docs.microsoft.com/azure/best-practices-availability-paired-regions) for a current list of regional pairs.</span></span>
  
### <a name="assign-permissions-to-each-key-vault"></a><span data-ttu-id="d6e44-252">각 키 자격 증명 모음에 사용 권한 할당</span><span class="sxs-lookup"><span data-stu-id="d6e44-252">Assign permissions to each key vault</span></span>

<span data-ttu-id="d6e44-253">각 키 보관소에 대해 구현에 따라 고객 키에 대해 세 가지 개별 사용 권한 집합을 정의 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d6e44-253">For each key vault, you will need to define three separate sets of permissions for Customer Key, depending on your implementation.</span></span> <span data-ttu-id="d6e44-254">예를 들어 다음 각 항목에 대해 하나의 권한 집합을 정의 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d6e44-254">For example, you will need to define one set of permissions for each of the following:</span></span>
  
- <span data-ttu-id="d6e44-255">조직에 대 한 주요 자격 증명 모음을 일상적인 관리 하는 데 사용할 수 있는 **주요 자격 증명 모음 관리자**</span><span class="sxs-lookup"><span data-stu-id="d6e44-255">**Key vault administrators** that will perform day-to-day management of your key vault for your organization.</span></span> <span data-ttu-id="d6e44-256">이러한 작업에는 백업, 만들기, 가져오기, 가져오기, 목록, 복원 등이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d6e44-256">These tasks include backup, create, get, import, list, and restore.</span></span>

  > [!IMPORTANT]
  > <span data-ttu-id="d6e44-257">키 자격 증명 모음 관리자에 게 할당 된 사용 권한 집합에는 키를 삭제할 수 있는 권한이 포함 되어 있지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d6e44-257">The set of permissions assigned to key vault administrators does not include the permission to delete keys.</span></span> <span data-ttu-id="d6e44-258">이는 의도적인 것이 고 중요 한 방법입니다.</span><span class="sxs-lookup"><span data-stu-id="d6e44-258">This is intentional and an important practice.</span></span> <span data-ttu-id="d6e44-259">일반적으로 암호화 키 삭제는 데이터를 영구적으로 소멸 하기 때문에 수행 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d6e44-259">Deleting encryption keys is not typically done, since doing so permanently destroys data.</span></span> <span data-ttu-id="d6e44-260">주요 자격 증명 모음 관리자에 게 기본적으로이 사용 권한을 부여 하지 않는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="d6e44-260">As a best practice, do not grant this permission to key vault administrators by default.</span></span> <span data-ttu-id="d6e44-261">대신 주요 자격 증명 참가자에 대해이를 예약 하 고, 결과에 대 한 확실 한 이해가 이해 되 면 짧은 기간 동안 관리자 에게만 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="d6e44-261">Instead, reserve this for key vault contributors and only assign it to an administrator on a short term basis once a clear understanding of the consequences is understood.</span></span>
  
  <span data-ttu-id="d6e44-262">조직의 사용자에 게 이러한 사용 권한을 할당 하려면 Azure PowerShell을 사용 하 여 Azure 구독에 로그인 합니다.</span><span class="sxs-lookup"><span data-stu-id="d6e44-262">To assign these permissions to a user in your organization, log in to your Azure subscription with Azure PowerShell.</span></span> <span data-ttu-id="d6e44-263">자세한 내용은 [Azure PowerShell을 사용 하 여 로그인](https://docs.microsoft.com/powershell/azure/authenticate-azureps)을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="d6e44-263">For instructions, see [Sign in with Azure PowerShell](https://docs.microsoft.com/powershell/azure/authenticate-azureps).</span></span>

- <span data-ttu-id="d6e44-264">AzKeyVaultAccessPolicy cmdlet을 실행 하 여 필요한 권한을 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="d6e44-264">Run the Set-AzKeyVaultAccessPolicy cmdlet to assign the necessary permissions.</span></span>

   ```powershell
   Set-AzKeyVaultAccessPolicy -VaultName <vault name> -UserPrincipalName <UPN of user> -PermissionsToKeys create,import,list,get,backup,restore
   ```

   <span data-ttu-id="d6e44-265">예시:</span><span class="sxs-lookup"><span data-stu-id="d6e44-265">For example:</span></span>

   ```powershell
   Set-AzKeyVaultAccessPolicy -VaultName Contoso-O365EX-NA-VaultA1 -UserPrincipalName alice@contoso.com -PermissionsToKeys create,import,list,get,backup,restore
   ```

- <span data-ttu-id="d6e44-266">Azure 키 자격 증명 모음 자체에 대 한 사용 권한을 변경할 수 있는 **키 보관소 참가자**</span><span class="sxs-lookup"><span data-stu-id="d6e44-266">**Key vault contributors** that can change permissions on the Azure Key Vault itself.</span></span> <span data-ttu-id="d6e44-267">직원은 팀에 탈퇴 하거나 참가할 때 이러한 권한을 변경 해야 하며, 키 보관소 관리자가 키를 삭제 하거나 복원 하는 데 필요한 권한을 갖는 것이 아주 드문 경우입니다.</span><span class="sxs-lookup"><span data-stu-id="d6e44-267">You'll need to change these permissions as employees leave or join your team, or in the extremely rare situation that the key vault administrators legitimately need permission to delete or restore a key.</span></span> <span data-ttu-id="d6e44-268">이 키 보관소 참가자 집합에는 해당 키 자격 증명 모음에 대 한 **참가자** 역할이 부여 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d6e44-268">This set of key vault contributors needs to be granted the **Contributor** role on your key vault.</span></span> <span data-ttu-id="d6e44-269">Azure Resource Manager를 사용 하 여이 역할을 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d6e44-269">You can assign this role by using Azure Resource Manager.</span></span> <span data-ttu-id="d6e44-270">자세한 단계는 [역할 기반 액세스 제어를 사용 하 여 Azure 구독 리소스에 대 한 액세스를 관리 하](https://docs.microsoft.com/azure/active-directory/role-based-access-control-configure)는 방법을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="d6e44-270">For detailed steps, see [Use Role-Based Access Control to manage access to your Azure subscription resources](https://docs.microsoft.com/azure/active-directory/role-based-access-control-configure).</span></span> <span data-ttu-id="d6e44-271">구독을 만드는 관리자는이 액세스 권한 뿐만 아니라 다른 관리자에 게 참가자 역할을 할당할 수 있는 권한도 제공 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d6e44-271">The administrator who creates a subscription has this access implicitly, as well as the ability to assign other administrators to the Contributor role.</span></span>

- <span data-ttu-id="d6e44-272">Exchange Online 및 비즈니스용 Skype에서 고객 키를 사용 하려는 경우에는 Microsoft 365에 대 한 권한을 부여 하 여 Exchange Online 및 비즈니스용 Skype를 대신 하 여 키 자격 증명 모음을 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d6e44-272">If you intend to use Customer Key with Exchange Online and Skype for Business, you need to give permission to Microsoft 365 to use the key vault on behalf of Exchange Online and Skype for Business.</span></span> <span data-ttu-id="d6e44-273">마찬가지로, SharePoint Online 및 비즈니스용 OneDrive에서 고객 키를 사용 하려는 경우에는 Microsoft 365에 대 한 권한을 추가 하 여 SharePoint Online 및 비즈니스용 OneDrive를 대신 하 여 키 자격 증명 모음을 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d6e44-273">Likewise, if you intend to use Customer Key with SharePoint Online and OneDrive for Business, you need to add permission for the Microsoft 365 to use the key vault on behalf of SharePoint Online and OneDrive for Business.</span></span> <span data-ttu-id="d6e44-274">Microsoft 365에 대 한 사용 권한을 부여 하려면 다음 구문을 사용 하 여 **AzKeyVaultAccessPolicy** cmdlet을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="d6e44-274">To give permission to Microsoft 365, run the **Set-AzKeyVaultAccessPolicy** cmdlet using the following syntax:</span></span> 

   ```powershell
   Set-AzKeyVaultAccessPolicy -VaultName <vault name> -PermissionsToKeys wrapKey,unwrapKey,get -ServicePrincipalName <Office 365 appID>
   ```

   <span data-ttu-id="d6e44-275">여기서,</span><span class="sxs-lookup"><span data-stu-id="d6e44-275">Where:</span></span>

    - <span data-ttu-id="d6e44-276">*vault 이름은* 만든 키 보관소의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="d6e44-276">*vault name* is the name of the key vault you created.</span></span>

    - <span data-ttu-id="d6e44-277">Exchange Online 및 비즈니스용 Skype의 경우  *Office 365 appID* 를 다음으로 바꾸기 `00000002-0000-0ff1-ce00-000000000000`</span><span class="sxs-lookup"><span data-stu-id="d6e44-277">For Exchange Online and Skype for Business, replace  *Office 365 appID* with `00000002-0000-0ff1-ce00-000000000000`</span></span>

    - <span data-ttu-id="d6e44-278">SharePoint Online, 비즈니스용 OneDrive 및 팀 파일의 경우  *Office 365 appID* 를 다음으로 바꾸기 `00000003-0000-0ff1-ce00-000000000000`</span><span class="sxs-lookup"><span data-stu-id="d6e44-278">For SharePoint Online, OneDrive for Business, and Teams files, replace  *Office 365 appID* with `00000003-0000-0ff1-ce00-000000000000`</span></span>

  <span data-ttu-id="d6e44-279">예: Exchange Online 및 비즈니스용 Skype에 대 한 사용 권한 설정:</span><span class="sxs-lookup"><span data-stu-id="d6e44-279">Example: Setting permissions for Exchange Online and Skype for Business:</span></span>

   ```powershell
   Set-AzKeyVaultAccessPolicy -VaultName Contoso-O365EX-NA-VaultA1 -PermissionsToKeys wrapKey,unwrapKey,get -ServicePrincipalName 00000002-0000-0ff1-ce00-000000000000
   ```

  <span data-ttu-id="d6e44-280">예: SharePoint Online, 비즈니스용 OneDrive 및 팀 파일에 대 한 사용 권한 설정:</span><span class="sxs-lookup"><span data-stu-id="d6e44-280">Example: Setting permissions for SharePoint Online, OneDrive for Business, and Teams files:</span></span>

   ```powershell
   Set-AzKeyVaultAccessPolicy -VaultName Contoso-O365SP-NA-VaultA1 -PermissionsToKeys wrapKey,unwrapKey,get -ServicePrincipalName 00000003-0000-0ff1-ce00-000000000000
   ```

### <a name="enable-and-then-confirm-soft-delete-on-your-key-vaults"></a><span data-ttu-id="d6e44-281">키 자격 증명 모음에서 일시 삭제를 사용 하도록 설정 하 고 확인</span><span class="sxs-lookup"><span data-stu-id="d6e44-281">Enable and then confirm soft delete on your key vaults</span></span>

<span data-ttu-id="d6e44-282">키를 신속 하 게 복구할 수 있으면 실수로 또는 악의적으로 삭제 된 키로 인해 확장 서비스 중단을 경험할 가능성이 줄어듭니다.</span><span class="sxs-lookup"><span data-stu-id="d6e44-282">When you can quickly recover your keys, you are less likely to experience an extended service outage due to accidentally or maliciously deleted keys.</span></span> <span data-ttu-id="d6e44-283">사용자 키에 키를 사용할 수 있으려면 먼저 소프트 삭제 라고 하는이 구성을 사용 하도록 설정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d6e44-283">You need to enable this configuration, referred to as Soft Delete, before you can use your keys with Customer Key.</span></span> <span data-ttu-id="d6e44-284">소프트 삭제를 사용 하도록 설정 하면 백업에서 복원 하지 않고도 90 일 내에 키 또는 자격 증명 모음을 복구할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d6e44-284">Enabling Soft Delete allows you to recover keys or vaults within 90 days of deletion without having to restore them from backup.</span></span>
  
<span data-ttu-id="d6e44-285">키 자격 증명 모음에서 일시 삭제를 사용 하도록 설정 하려면 다음 단계를 완료 합니다.</span><span class="sxs-lookup"><span data-stu-id="d6e44-285">To enable Soft Delete on your key vaults, complete these steps:</span></span>
  
1. <span data-ttu-id="d6e44-286">Windows Powershell을 사용 하 여 Azure 구독에 로그인 합니다.</span><span class="sxs-lookup"><span data-stu-id="d6e44-286">Sign in to your Azure subscription with Windows Powershell.</span></span> <span data-ttu-id="d6e44-287">자세한 내용은 [Azure PowerShell을 사용 하 여 로그인](https://docs.microsoft.com/powershell/azure/authenticate-azureps)을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="d6e44-287">For instructions, see [Sign in with Azure PowerShell](https://docs.microsoft.com/powershell/azure/authenticate-azureps).</span></span>

2. <span data-ttu-id="d6e44-288">[AzKeyVault](https://docs.microsoft.com/powershell/module/az.keyvault/get-azkeyvault) cmdlet을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="d6e44-288">Run the [Get-AzKeyVault](https://docs.microsoft.com/powershell/module/az.keyvault/get-azkeyvault) cmdlet.</span></span> <span data-ttu-id="d6e44-289">이 예에서 *보관소 이름은* 소프트 삭제를 활성화할 수 있는 키 보관소의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="d6e44-289">In this example, *vault name* is the name of the key vault for which you are enabling soft delete:</span></span>

   ```powershell
   $v = Get-AzKeyVault -VaultName <vault name>
   $r = Get-AzResource -ResourceId $v.ResourceId
   $r.Properties | Add-Member -MemberType NoteProperty -Name enableSoftDelete -Value 'True'
   Set-AzResource -ResourceId $r.ResourceId -Properties $r.Properties
   ```

3. <span data-ttu-id="d6e44-290">**AzKeyVault** cmdlet을 실행 하 여 키 자격 증명 모음에 대해 소프트 삭제가 구성 되었는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="d6e44-290">Confirm soft delete is configured for the key vault by running the **Get-AzKeyVault** cmdlet.</span></span> <span data-ttu-id="d6e44-291">키 자격 증명 모음에 대해 소프트 삭제가 올바르게 구성 된 경우 _소프트 삭제 Enabled_ 속성은 **True**값을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="d6e44-291">If soft delete is configured properly for the key vault, then the _Soft Delete Enabled_ property returns a value of **True**:</span></span>

   ```powershell
   Get-AzKeyVault -VaultName <vault name> | fl
   ```

### <a name="add-a-key-to-each-key-vault-either-by-creating-or-importing-a-key"></a><span data-ttu-id="d6e44-292">키를 만들거나 가져오는 방법으로 각 키 보관소에 키를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="d6e44-292">Add a key to each key vault either by creating or importing a key</span></span>

<span data-ttu-id="d6e44-293">Azure 키 보관소에는 두 가지 방법으로 키를 추가할 수 있습니다. 키 보관소에 직접 키를 만들거나 키를 가져올 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d6e44-293">There are two ways to add keys to an Azure Key Vault; you can create a key directly in Key Vault, or you can import a key.</span></span> <span data-ttu-id="d6e44-294">키 보관소에서 직접 키를 만드는 것은 다소 복잡 한 방법 이지만 키를 가져오면 키가 생성 되는 방식을 보다 강력 하 게 제어할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d6e44-294">Creating a key directly in Key Vault is the less complicated method, while importing a key provides total control over how the key is generated.</span></span>
  
<span data-ttu-id="d6e44-295">키 보관소에 직접 키를 만들려면 다음과 같이 [AzKeyVaultKey](https://docs.microsoft.com/powershell/module/az.keyvault/add-azkeyvaultkey) cmdlet을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="d6e44-295">To create a key directly in your key vault, run the [Add-AzKeyVaultKey](https://docs.microsoft.com/powershell/module/az.keyvault/add-azkeyvaultkey) cmdlet as follows:</span></span>
  
```powershell
Add-AzKeyVaultKey -VaultName <vault name> -Name <key name> -Destination <HSM|Software> -KeyOps wrapKey,unwrapKey
```

<span data-ttu-id="d6e44-296">여기서,</span><span class="sxs-lookup"><span data-stu-id="d6e44-296">Where:</span></span>

- <span data-ttu-id="d6e44-297">*vault 이름은* 키를 만들 키 자격 증명 모음의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="d6e44-297">*vault name* is the name of the key vault in which you want to create the key.</span></span>

- <span data-ttu-id="d6e44-298">*키 이름은* 새 키에 지정할 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="d6e44-298">*key name* is the name you want to give the new key.</span></span>

  > [!TIP]
  > <span data-ttu-id="d6e44-299">키 보관소에 대해 위에서 설명한 유사 명명 규칙을 사용 하 여 이름 키</span><span class="sxs-lookup"><span data-stu-id="d6e44-299">Name keys using a similar naming convention as described above for key vaults.</span></span> <span data-ttu-id="d6e44-300">이러한 방식으로 키 이름만 표시 되는 도구에서 문자열은 자체 설명입니다.</span><span class="sxs-lookup"><span data-stu-id="d6e44-300">This way, in tools that show only the key name, the string is self-describing.</span></span>
  
- <span data-ttu-id="d6e44-301">HSM을 사용 하 여 키를 보호 하려면 _대상_ 매개 변수의 값으로 **HSM** 을 지정 하 고, 그렇지 않으면 **소프트웨어**를 지정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d6e44-301">If you intend to protect the key with an HSM, ensure that you specify **HSM** as the value of the _Destination_ parameter, otherwise, specify **Software**.</span></span>

<span data-ttu-id="d6e44-302">예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="d6e44-302">For example,</span></span>
  
```powershell
Add-AzKeyVaultKey -VaultName Contoso-O365EX-NA-VaultA1 -Name Contoso-O365EX-NA-VaultA1-Key001 -Destination Software -KeyOps wrapKey,unwrapKey
```

<span data-ttu-id="d6e44-303">키 보관소로 바로 키를 가져오려면 nCipher nShield 하드웨어 보안 모듈이 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d6e44-303">To import a key directly into your key vault, you need to have a nCipher nShield Hardware Security Module.</span></span>
  
<span data-ttu-id="d6e44-304">일부 조직에서는이 방법을 선호 하 여 키의 provenance을 설정 하 고,이 방법을 사용 하면 다음 항목도 제공 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d6e44-304">Some organizations prefer this approach to establish the provenance of their keys, and then this method also provides the following:</span></span>
  
- <span data-ttu-id="d6e44-305">가져오기에 사용 되는 도구 집합에는 nCipher에서 생성 한 키를 암호화 하는 데 사용 되는 KEK (키 교환 키)가 내보낼 수 없으며 nCipher에서 제조한 정품 HSM 내에서 생성 된다는 것이 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d6e44-305">The toolset used for import includes attestation from nCipher that the Key Exchange Key (KEK) that is used to encrypt the key you generate is not exportable and is generated inside a genuine HSM that was manufactured by nCipher.</span></span>

- <span data-ttu-id="d6e44-306">도구 집합에는 nCipher에서 제조한 정품 HSM에도 Azure 키 자격 증명 모음 보안 세계가 생성 된 nCipher의 증명이 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d6e44-306">The toolset includes attestation from nCipher that the Azure Key Vault security world was also generated on a genuine HSM manufactured by nCipher.</span></span> <span data-ttu-id="d6e44-307">이 증명은 Microsoft가 정품 nCipher 하드웨어를 사용 하 고 있음을 증명 합니다.</span><span class="sxs-lookup"><span data-stu-id="d6e44-307">This attestation proves to you that Microsoft is also using genuine nCipher hardware.</span></span>

<span data-ttu-id="d6e44-308">보안 그룹을 확인 하 여 위의 attestations 필요한 지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="d6e44-308">Check with your security group to determine if the above attestations are required.</span></span> <span data-ttu-id="d6e44-309">온-프레미스 키를 만들고 키 보관소로 가져오는 자세한 단계 [는 Azure Key vault에 대해 HSM 보호 키를 생성 하 고 전송 하는 방법을](https://azure.microsoft.com/documentation/articles/key-vault-hsm-protected-keys/)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="d6e44-309">For detailed steps to create a key on-premises and import it into your key vault, see [How to generate and transfer HSM-protected keys for Azure Key Vault](https://azure.microsoft.com/documentation/articles/key-vault-hsm-protected-keys/).</span></span> <span data-ttu-id="d6e44-310">Azure 지침을 사용 하 여 각 키 자격 증명 모음에 키를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="d6e44-310">Use the Azure instructions to create a key in each key vault.</span></span>
  
### <a name="check-the-recovery-level-of-your-keys"></a><span data-ttu-id="d6e44-311">키의 복구 수준 확인</span><span class="sxs-lookup"><span data-stu-id="d6e44-311">Check the recovery level of your keys</span></span>

<span data-ttu-id="d6e44-312">Microsoft 365에서는 Azure 키 자격 증명 모음 구독이 취소 되지 않도록 설정 되 고, 고객 키에 사용 되는 키에 소프트 삭제가 사용 되도록 되어 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d6e44-312">Microsoft 365 requires that the Azure Key Vault subscription is set to Do Not Cancel and that the keys used by Customer Key have soft delete enabled.</span></span> <span data-ttu-id="d6e44-313">키의 복구 수준을 확인 하 여이를 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d6e44-313">You can confirm this by looking at the recovery level on your keys.</span></span>
  
<span data-ttu-id="d6e44-314">키의 복구 수준을 확인 하려면 Azure PowerShell에서 다음과 같이 AzKeyVaultKey cmdlet을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="d6e44-314">To check the recovery level of a key, in Azure PowerShell, run the Get-AzKeyVaultKey cmdlet as follows:</span></span>
  
```powershell
(Get-AzKeyVaultKey -VaultName <vault name> -Name <key name>).Attributes
```

<span data-ttu-id="d6e44-315">_복구 수준_ 속성에서 복구 **가능한 + ProtectedSubscription**값이 아닌 다른 항목을 반환 하는 경우에는이 항목을 검토 하 여 구독을 취소 하지 않고 각 키 보관소에 소프트 삭제를 사용 하도록 설정 하는 모든 단계를 따랐는지 확인 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d6e44-315">If the _Recovery Level_ property returns anything other than a value of **Recoverable+ProtectedSubscription**, you will need to review this topic and ensure that you have followed all of the steps to put the subscription on the Do Not Cancel list and that you have soft delete enabled on each of your key vaults.</span></span>
  
### <a name="back-up-azure-key-vault"></a><span data-ttu-id="d6e44-316">Azure 키 자격 증명 모음 백업</span><span class="sxs-lookup"><span data-stu-id="d6e44-316">Back up Azure Key Vault</span></span>

<span data-ttu-id="d6e44-317">키를 만들거나 변경 하는 즉시 백업 및 오프 라인 복사본을 백업 및 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="d6e44-317">Immediately following creation or any change to a key, perform a backup and store copies of the backup, both online and offline.</span></span> <span data-ttu-id="d6e44-318">오프 라인 복사본은 실제 안전 또는 상업적 저장소 기능과 같은 네트워크에 연결 해서는 안 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d6e44-318">Offline copies should not be connected to any network, such as in a physical safe or commercial storage facility.</span></span> <span data-ttu-id="d6e44-319">재해 발생 시 액세스할 수 있는 위치에 백업 복사본을 하나 이상 저장 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d6e44-319">At least one copy of the backup should be stored in a location that will be accessible in the event of a disaster.</span></span> <span data-ttu-id="d6e44-320">백업 blob은 키 자료를 복원 하는 유일한 방법으로 키 자격 증명 키를 영구적으로 제거 하거나 작동 하지 않는 방식으로 렌더링 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d6e44-320">The backup blobs are the sole means of restoring key material should a Key Vault key be permanently destroyed or otherwise rendered inoperable.</span></span> <span data-ttu-id="d6e44-321">Azure 키 자격 증명 모음에 대 한 외부 키를 가져오고 Azure 키 보관소로 가져온 키는 해당 키를 사용 하는 데 필요한 메타 데이터가 외부 키가 없기 때문에 백업으로 한정 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d6e44-321">Keys that are external to Azure Key Vault and were imported to Azure Key Vault do not qualify as a backup because the metadata necessary for Customer Key to use the key does not exist with the external key.</span></span> <span data-ttu-id="d6e44-322">Azure Key Vault에서 가져온 백업만 고객 키를 사용한 복원 작업에 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d6e44-322">Only a backup taken from Azure Key Vault can be used for restore operations with Customer Key.</span></span> <span data-ttu-id="d6e44-323">따라서 키가 업로드 되거나 생성 되 면 Azure 키 자격 증명 모음을 백업 하는 것이 중요 합니다.</span><span class="sxs-lookup"><span data-stu-id="d6e44-323">Therefore, it is essential that a backup of Azure Key Vault be made once a key is uploaded or created.</span></span>
  
<span data-ttu-id="d6e44-324">Azure 키 자격 증명 키의 백업을 만들려면 다음과 같이 [AzKeyVaultKey](https://docs.microsoft.com/powershell/module/az.keyvault/backup-azkeyvaultkey) cmdlet을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="d6e44-324">To create a backup of an Azure Key Vault key, run the [Backup-AzKeyVaultKey](https://docs.microsoft.com/powershell/module/az.keyvault/backup-azkeyvaultkey) cmdlet as follows:</span></span>

```powershell
Backup-AzKeyVaultKey -VaultName <vault name> -Name <key name>
-OutputFile <filename.backup>
```

<span data-ttu-id="d6e44-325">출력 파일이 접미사를 사용 하는지 확인 `.backup` 합니다.</span><span class="sxs-lookup"><span data-stu-id="d6e44-325">Ensure that your output file uses the suffix `.backup`.</span></span>
  
<span data-ttu-id="d6e44-326">이 cmdlet에서 생성 된 출력 파일은 암호화 되며 Azure 키 자격 증명 모음 외부에서 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="d6e44-326">The output file resulting from this cmdlet is encrypted and cannot be used outside of Azure Key Vault.</span></span> <span data-ttu-id="d6e44-327">백업은 백업을 수행한 Azure 구독에만 복원할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d6e44-327">The backup can be restored only to the Azure subscription from which the backup was taken.</span></span>
  
> [!TIP]
> <span data-ttu-id="d6e44-328">출력 파일의 경우 자격 증명 모음 이름 및 키 이름을 조합 하 여 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="d6e44-328">For the output file, choose a combination of your vault name and key name.</span></span> <span data-ttu-id="d6e44-329">이렇게 하면 파일 이름이 자체 설명 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d6e44-329">This will make the file name self-describing.</span></span> <span data-ttu-id="d6e44-330">또한 백업 파일 이름이 충돌 하지 않도록 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d6e44-330">It will also ensure that backup file names do not collide.</span></span>
  
<span data-ttu-id="d6e44-331">예시:</span><span class="sxs-lookup"><span data-stu-id="d6e44-331">For example:</span></span>
  
```powershell
Backup-AzKeyVaultKey -VaultName Contoso-O365EX-NA-VaultA1 -Name Contoso-O365EX-NA-VaultA1-Key001 -OutputFile Contoso-O365EX-NA-VaultA1-Key001-Backup-20170802.backup
```

### <a name="validate-azure-key-vault-configuration-settings"></a><span data-ttu-id="d6e44-332">Azure 키 자격 증명 모음 구성 설정 확인</span><span class="sxs-lookup"><span data-stu-id="d6e44-332">Validate Azure Key Vault configuration settings</span></span>

<span data-ttu-id="d6e44-333">DEP에서 키를 사용 하기 전에 유효성 검사를 수행 하는 것은 선택 사항 이지만 가급적 권장 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d6e44-333">Performing validation before using keys in a DEP is optional, but highly recommended.</span></span> <span data-ttu-id="d6e44-334">특히이 항목에서 설명 하는 것과 다른 키 및 보관소를 설정 하는 단계를 사용 하는 경우에는 고객 키를 구성 하기 전에 Azure Key Vault 리소스의 상태를 확인 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d6e44-334">In particular, if you use steps to set up your keys and vaults other than the ones described in this topic, you should validate the health of your Azure Key Vault resources before you configure Customer Key.</span></span>
  
<span data-ttu-id="d6e44-335">키가 get, wrapKey 및 unwrapKey 작업을 사용 하도록 설정 되었는지 확인 하려면 다음을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="d6e44-335">To verify that your keys have get, wrapKey, and unwrapKey operations enabled:</span></span>
  
<span data-ttu-id="d6e44-336">다음과 같이 [AzKeyVault](https://docs.microsoft.com/powershell/module/az.keyvault/get-azkeyvault) cmdlet을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="d6e44-336">Run the [Get-AzKeyVault](https://docs.microsoft.com/powershell/module/az.keyvault/get-azkeyvault) cmdlet as follows:</span></span>
  
```powershell
Get-AzKeyVault -VaultName <vault name>
```

<span data-ttu-id="d6e44-337">출력에서 액세스 정책 및 Exchange Online id (guid) 또는 SharePoint Online id (GUID)를 적절 하 게 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="d6e44-337">In the output, look for the Access Policy and for the Exchange Online identity (GUID) or the SharePoint Online identity (GUID) as appropriate.</span></span> <span data-ttu-id="d6e44-338">위의 세 가지 사용 권한 중 일부는 키 사용 권한 아래에 표시 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d6e44-338">All three of the above permissions must be shown under Permissions to Keys.</span></span>
  
<span data-ttu-id="d6e44-339">액세스 정책 구성이 올바르지 않으면 다음과 같이 AzKeyVaultAccessPolicy cmdlet을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="d6e44-339">If the access policy configuration is incorrect, run the Set-AzKeyVaultAccessPolicy cmdlet as follows:</span></span>
  
```powershell
Set-AzKeyVaultAccessPolicy -VaultName <vault name> -PermissionsToKeys wrapKey,unwrapKey,get -ServicePrincipalName <Office 365 appID>
```

<span data-ttu-id="d6e44-340">예를 들어 Exchange Online 및 비즈니스용 Skype의 경우:</span><span class="sxs-lookup"><span data-stu-id="d6e44-340">For example, for Exchange Online and Skype for Business:</span></span>
  
```powershell
Set-AzKeyVaultAccessPolicy -VaultName Contoso-O365EX-NA-VaultA1 
-PermissionsToKeys wrapKey,unwrapKey,get -ServicePrincipalName 00000002-0000-0ff1-ce00-000000000000
```

<span data-ttu-id="d6e44-341">예를 들어 SharePoint Online 및 비즈니스용 OneDrive:</span><span class="sxs-lookup"><span data-stu-id="d6e44-341">For example, for SharePoint Online and OneDrive for Business:</span></span>
  
```powershell
Set-AzKeyVaultAccessPolicy -VaultName Contoso-O365SP-NA-VaultA1
-PermissionsToKeys wrapKey,unwrapKey,get -ServicePrincipalName 00000003-0000-0ff1-ce00-000000000000
```

<span data-ttu-id="d6e44-342">키에 대해 만료 날짜가 설정 되지 않았는지 확인 하려면 다음과 같이 [AzKeyVaultKey](https://docs.microsoft.com/powershell/module/az.keyvault/get-azkeyvault) cmdlet을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="d6e44-342">To verify that an expiration date is not set for your keys run the [Get-AzKeyVaultKey](https://docs.microsoft.com/powershell/module/az.keyvault/get-azkeyvault) cmdlet as follows:</span></span>
  
```powershell
Get-AzKeyVaultKey -VaultName <vault name>
```

<span data-ttu-id="d6e44-343">만료 된 키는 고객 키에서 사용할 수 없으며 만료 된 키로 시도한 작업은 실패 하 고 서비스 중단으로 인해 발생할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d6e44-343">An expired key cannot be used by Customer Key and operations attempted with an expired key will fail, and possibly result in a service outage.</span></span> <span data-ttu-id="d6e44-344">고객 키와 함께 사용 되는 키에는 만료 날짜가 없을 것을 적극 권장 합니다.</span><span class="sxs-lookup"><span data-stu-id="d6e44-344">We strongly recommend that keys used with Customer Key do not have an expiration date.</span></span> <span data-ttu-id="d6e44-345">만료 날짜를 설정한 후에는 제거할 수 없지만 다른 날짜로 변경할 수는 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d6e44-345">An expiration date, once set, cannot be removed, but can be changed to a different date.</span></span> <span data-ttu-id="d6e44-346">만료 날짜가 설정 된 키를 사용 해야 하는 경우 만료 값을 12/31/9999로 변경 합니다.</span><span class="sxs-lookup"><span data-stu-id="d6e44-346">If a key must be used that has an expiration date set, change the expiration value to 12/31/9999.</span></span> <span data-ttu-id="d6e44-347">만료 날짜가 12/31/9999 이외의 날짜로 설정 된 키는 Microsoft 365 유효성 검사를 통과 하지 못합니다.</span><span class="sxs-lookup"><span data-stu-id="d6e44-347">Keys with an expiration date set to a date other than 12/31/9999 will not pass Microsoft 365 validation.</span></span>
  
<span data-ttu-id="d6e44-348">12/31/9999 이외의 값으로 설정 된 만료 날짜를 변경 하려면 다음과 같이 [AzKeyVaultKey](https://docs.microsoft.com/powershell/module/az.keyvault/update-azkeyvaultkey) cmdlet을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="d6e44-348">To change an expiration date that has been set to any value other than 12/31/9999, run the [Update-AzKeyVaultKey](https://docs.microsoft.com/powershell/module/az.keyvault/update-azkeyvaultkey) cmdlet as follows:</span></span>
  
```powershell
Update-AzKeyVaultKey -VaultName <vault name> -Name <key name> -Expires (Get-Date -Date "12/31/9999")
```

> [!CAUTION]
> <span data-ttu-id="d6e44-349">고객 키와 함께 사용 하는 암호화 키에 대해 만료 날짜를 설정 하지 마십시오.</span><span class="sxs-lookup"><span data-stu-id="d6e44-349">Don't set expiration dates on encryption keys you use with Customer Key.</span></span>
  
### <a name="obtain-the-uri-for-each-azure-key-vault-key"></a><span data-ttu-id="d6e44-350">각 Azure Key Vault 키에 대 한 URI 가져오기</span><span class="sxs-lookup"><span data-stu-id="d6e44-350">Obtain the URI for each Azure Key Vault key</span></span>

<span data-ttu-id="d6e44-351">Azure의 모든 단계를 완료 하 여 키 자격 증명 모음을 설정 하 고 키를 추가한 후에는 다음 명령을 실행 하 여 각 키 자격 증명 모음에서 키에 대 한 URI를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="d6e44-351">Once you've completed all the steps in Azure to set up your key vaults and added your keys, run the following command to get the URI for the key in each key vault.</span></span> <span data-ttu-id="d6e44-352">나중에 각 DEP를 만들고 할당할 때 이러한 Uri를 사용 해야 하므로이 정보를 안전한 장소에 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="d6e44-352">You will need to use these URIs when you create and assign each DEP later, so save this information in a safe place.</span></span> <span data-ttu-id="d6e44-353">각 키 자격 증명 모음에 대해 한 번씩이 명령을 실행 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d6e44-353">Remember to run this command once for each key vault.</span></span>
  
<span data-ttu-id="d6e44-354">Azure PowerShell:</span><span class="sxs-lookup"><span data-stu-id="d6e44-354">In Azure PowerShell:</span></span>
  
```powershell
(Get-AzKeyVaultKey -VaultName <vault name>).Id
```

## <a name="office-365-setting-up-customer-key-for-exchange-online-and-skype-for-business"></a><span data-ttu-id="d6e44-355">Office 365: Exchange Online 및 비즈니스용 Skype에 대 한 고객 키 설정</span><span class="sxs-lookup"><span data-stu-id="d6e44-355">Office 365: Setting up Customer Key for Exchange Online and Skype for Business</span></span>

<span data-ttu-id="d6e44-356">시작 하기 전에 Azure 키 자격 증명 모음을 설정 하는 데 필요한 작업을 완료 했는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="d6e44-356">Before you begin, ensure that you have completed the tasks required to set up Azure Key Vault.</span></span> <span data-ttu-id="d6e44-357">자세한 내용은 [Azure Key Vault의 전체 작업 및 Microsoft FastTrack For Customer key](#complete-tasks-in-azure-key-vault-and-microsoft-fasttrack-for-customer-key) 를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="d6e44-357">See [Complete tasks in Azure Key Vault and Microsoft FastTrack for Customer Key](#complete-tasks-in-azure-key-vault-and-microsoft-fasttrack-for-customer-key) for information.</span></span>
  
<span data-ttu-id="d6e44-358">Exchange Online 및 비즈니스용 Skype에 대 한 고객 키를 설정 하려면 Windows PowerShell을 사용 하 여 Exchange Online에 원격으로 연결 하 여 다음 단계를 수행 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d6e44-358">To set up Customer Key for Exchange Online and Skype for Business, you will need to perform these steps by remotely connecting to Exchange Online with Windows PowerShell.</span></span>
  
### <a name="create-a-data-encryption-policy-dep-for-use-with-exchange-online-and-skype-for-business"></a><span data-ttu-id="d6e44-359">Exchange Online 및 비즈니스용 Skype에서 사용 하기 위한 DEP (데이터 암호화 정책) 만들기</span><span class="sxs-lookup"><span data-stu-id="d6e44-359">Create a data encryption policy (DEP) for use with Exchange Online and Skype for Business</span></span>

<span data-ttu-id="d6e44-360">DEP는 Azure Key Vault에 저장 된 키 집합과 연결 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d6e44-360">A DEP is associated with a set of keys stored in Azure Key Vault.</span></span> <span data-ttu-id="d6e44-361">Microsoft 365에서 사서함에 DEP를 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="d6e44-361">You assign a DEP to a mailbox in Microsoft 365.</span></span> <span data-ttu-id="d6e44-362">Microsoft 365에서는 정책에 식별 된 키를 사용 하 여 사서함을 암호화 합니다.</span><span class="sxs-lookup"><span data-stu-id="d6e44-362">Microsoft 365 will then use the keys identified in the policy to encrypt the mailbox.</span></span> <span data-ttu-id="d6e44-363">DEP를 만들려면 이전에 가져온 키 보관소 Uri가 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="d6e44-363">To create the DEP, you need the Key Vault URIs you obtained earlier.</span></span> <span data-ttu-id="d6e44-364">지침은 [각 Azure 키 자격 증명 모음 키의 URI 가져오기를](#obtain-the-uri-for-each-azure-key-vault-key) 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="d6e44-364">See [Obtain the URI for each Azure Key Vault key](#obtain-the-uri-for-each-azure-key-vault-key) for instructions.</span></span>
  
<span data-ttu-id="d6e44-365">항상!</span><span class="sxs-lookup"><span data-stu-id="d6e44-365">Remember!</span></span> <span data-ttu-id="d6e44-366">DEP를 만들 때 서로 다른 두 Azure 키 자격 증명 모음에 있는 두 개의 키를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="d6e44-366">When you create a DEP, you specify two keys that reside in two different Azure Key Vaults.</span></span> <span data-ttu-id="d6e44-367">이러한 키가 지리적 중복을 보장 하기 위해 별도의 두 Azure 지역에 위치 하는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="d6e44-367">Ensure that these keys are located in two separate Azure regions to ensure geo-redundancy.</span></span>
  
<span data-ttu-id="d6e44-368">DEP를 만들려면 다음 단계를 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="d6e44-368">To create the DEP, follow these steps:</span></span>
  
1. <span data-ttu-id="d6e44-369">로컬 컴퓨터에서 조직에 전역 관리자 권한이 있는 회사 또는 학교 계정을 사용 하 여 Windows PowerShell 창에서 [Exchange Online PowerShell에 연결](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell) 합니다.</span><span class="sxs-lookup"><span data-stu-id="d6e44-369">On your local computer, using a work or school account that has global administrator permissions in your organization, [connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell) in a Windows PowerShell window.</span></span>

2. <span data-ttu-id="d6e44-370">DEP를 만들려면 다음 명령을 입력 하 여 새-DataEncryptionPolicy cmdlet을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="d6e44-370">To create a DEP, use the New-DataEncryptionPolicy cmdlet by typing the following command.</span></span>

   ```powershell
   New-DataEncryptionPolicy -Name <PolicyName> -Description "Policy Description" -AzureKeyIDs <KeyVaultURI1>, <KeyVaultURI2>
   ```

   <span data-ttu-id="d6e44-371">여기서,</span><span class="sxs-lookup"><span data-stu-id="d6e44-371">Where:</span></span>

   - <span data-ttu-id="d6e44-372">*PolicyName* 는 정책에 사용 하려는 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="d6e44-372">*PolicyName* is the name you want to use for the policy.</span></span> <span data-ttu-id="d6e44-373">이름에 공백을 포함할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="d6e44-373">Names cannot contain spaces.</span></span> <span data-ttu-id="d6e44-374">예를 USA_mailboxes 합니다.</span><span class="sxs-lookup"><span data-stu-id="d6e44-374">For example, USA_mailboxes.</span></span>

   - <span data-ttu-id="d6e44-375">정책 *설명은* 정책에 대 한 정보를 파악 하는 데 도움이 되는 정책에 대 한 사용자 친숙 한 설명입니다.</span><span class="sxs-lookup"><span data-stu-id="d6e44-375">*Policy Description* is a user friendly description of the policy that will help you remember what the policy is for.</span></span> <span data-ttu-id="d6e44-376">설명에 공백을 포함할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d6e44-376">You can include spaces in the description.</span></span> <span data-ttu-id="d6e44-377">예를 들어 "미국 및 지역의 사서함에 대 한 루트 키"입니다.</span><span class="sxs-lookup"><span data-stu-id="d6e44-377">For example, "Root key for mailboxes in USA and its territories".</span></span>

   - <span data-ttu-id="d6e44-378">*KeyVaultURI1* 는 정책의 첫 번째 키에 대 한 URI입니다.</span><span class="sxs-lookup"><span data-stu-id="d6e44-378">*KeyVaultURI1* is the URI for the first key in the policy.</span></span> <span data-ttu-id="d6e44-379">예를 들면 <https://contoso_EastUSvault01.vault.azure.net/keys/USA_key_01>와 같습니다.</span><span class="sxs-lookup"><span data-stu-id="d6e44-379">For example, <https://contoso_EastUSvault01.vault.azure.net/keys/USA_key_01>.</span></span>

   - <span data-ttu-id="d6e44-380">*KeyVaultURI2* 은 정책의 두 번째 키에 대 한 URI입니다.</span><span class="sxs-lookup"><span data-stu-id="d6e44-380">*KeyVaultURI2* is the URI for the second key in the policy.</span></span> <span data-ttu-id="d6e44-381">예를 들면 <https://contoso_EastUS2vault01.vault.azure.net/keys/USA_Key_02>와 같습니다.</span><span class="sxs-lookup"><span data-stu-id="d6e44-381">For example, <https://contoso_EastUS2vault01.vault.azure.net/keys/USA_Key_02>.</span></span> <span data-ttu-id="d6e44-382">두 Uri를 쉼표와 공백으로 구분 합니다.</span><span class="sxs-lookup"><span data-stu-id="d6e44-382">Separate the two URIs by a comma and a space.</span></span>

   <span data-ttu-id="d6e44-383">예제:</span><span class="sxs-lookup"><span data-stu-id="d6e44-383">Example:</span></span>
  
   ```powershell
   New-DataEncryptionPolicy -Name USA_mailboxes -Description "Root key for mailboxes in USA and its territories" -AzureKeyIDs https://contoso_EastUSvault01.vault.azure.net/keys/USA_key_01, https://contoso_EastUS2vault01.vault.azure.net/keys/USA_Key_02
   ```

<span data-ttu-id="d6e44-384">구문 및 매개 변수에 대 한 자세한 내용은 [New-Data과 policy](https://docs.microsoft.com/powershell/module/exchange/new-data-encryptionpolicy)를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="d6e44-384">For detailed syntax and parameter information, see [New-DataEncryptionPolicy](https://docs.microsoft.com/powershell/module/exchange/new-data-encryptionpolicy).</span></span>

### <a name="assign-a-dep-to-a-mailbox"></a><span data-ttu-id="d6e44-385">사서함에 DEP 할당</span><span class="sxs-lookup"><span data-stu-id="d6e44-385">Assign a DEP to a mailbox</span></span>

<span data-ttu-id="d6e44-386">사서함 cmdlet을 사용 하 여 사서함에 DEP를 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="d6e44-386">Assign the DEP to a mailbox by using the Set-Mailbox cmdlet.</span></span> <span data-ttu-id="d6e44-387">정책을 할당 하면 Microsoft 365에서 DEP에 지정 된 키로 사서함을 암호화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d6e44-387">Once you assign the policy, Microsoft 365 can encrypt the mailbox with the key designated in the DEP.</span></span>
  
```powershell
Set-Mailbox -Identity <MailboxIdParameter> -DataEncryptionPolicy <PolicyName>
```

<span data-ttu-id="d6e44-388">여기서 *MailboxIdParameter* 는 사서함을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="d6e44-388">Where *MailboxIdParameter* specifies a mailbox.</span></span> <span data-ttu-id="d6e44-389">사서함 cmdlet에 대 한 자세한 내용은 [set-mailbox](https://docs.microsoft.com/powershell/module/exchange/set-mailbox)를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="d6e44-389">For more information about the Set-Mailbox cmdlet, see [Set-Mailbox](https://docs.microsoft.com/powershell/module/exchange/set-mailbox).</span></span>

<span data-ttu-id="d6e44-390">온 [-프레미스 사서함에 대해 Outlook을 하이브리드 최신 인증과 함께 사용 하](https://docs.microsoft.com/exchange/clients/outlook-for-ios-and-android/use-hybrid-modern-auth)는 경우 Exchange Online 테 넌 트에 동기화 되는 온-프레미스 사서함 데이터는 Set-mailuser cmdlet을 사용 하 여 DEP를 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d6e44-390">For [on-premises mailboxes using Outlook for iOS and Android with hybrid Modern Authentication](https://docs.microsoft.com/exchange/clients/outlook-for-ios-and-android/use-hybrid-modern-auth), the on-premises mailbox data that is synchronized into your Exchange Online tenant can have DEP assigned using the Set-MailUser cmdlet.</span></span>

```powershell
Set-MailUser -Identity <MailUserIdParameter> -DataEncryptionPolicy <PolicyName>
```

<span data-ttu-id="d6e44-391">여기서 *Mailuseridparameter 변수* 는 메일 사용자 (메일 사용이 가능한 사용자 라고도 함)를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="d6e44-391">Where *MailUserIdParameter* specifies a mail user (also known as a mail-enabled user).</span></span> <span data-ttu-id="d6e44-392">설정-MailUser cmdlet에 대 한 자세한 내용은 [설정-MailUser](https://docs.microsoft.com/powershell/module/exchange/set-mailuser)를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="d6e44-392">For more information about the Set-MailUser cmdlet, see [Set-MailUser](https://docs.microsoft.com/powershell/module/exchange/set-mailuser).</span></span>
  
### <a name="validate-mailbox-encryption"></a><span data-ttu-id="d6e44-393">사서함 암호화 유효성 검사</span><span class="sxs-lookup"><span data-stu-id="d6e44-393">Validate mailbox encryption</span></span>

<span data-ttu-id="d6e44-394">사서함을 암호화 하는 데 다소 시간이 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d6e44-394">Encrypting a mailbox can take some time.</span></span> <span data-ttu-id="d6e44-395">처음 정책 할당의 경우에는 서비스에서 사서함을 암호화 하기 전에 사서함이 한 데이터베이스에서 다른 데이터베이스로 완전히 이동 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d6e44-395">For first time policy assignment, the mailbox must also completely move from one database to another before the service can encrypt the mailbox.</span></span> <span data-ttu-id="d6e44-396">DEP를 변경한 후 또는 사서함에 DEP를 처음 할당할 때 암호화 유효성 검사를 시도 하기 전에 72 시간을 기다리는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="d6e44-396">We recommend that you wait 72 hours before you attempt to validate encryption after you change a DEP or the first time you assign a DEP to a mailbox.</span></span>
  
<span data-ttu-id="d6e44-397">Get-mailboxstatistics cmdlet을 사용 하 여 사서함이 암호화 되어 있는지 여부를 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d6e44-397">Use the Get-MailboxStatistics cmdlet to determine if a mailbox is encrypted.</span></span>
  
```powershell
Get-MailboxStatistics -Identity <GeneralMailboxOrMailUserIdParameter> | fl IsEncrypted
```

<span data-ttu-id="d6e44-398">사서함이 암호화 된 경우 IsEncrypted 속성은 **true** 값을 반환 하 고 사서함이 암호화 되지 않은 경우에는 **false** 로 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="d6e44-398">The IsEncrypted property returns a value of **true** if the mailbox is encrypted and a value of **false** if the mailbox is not encrypted.</span></span>

<span data-ttu-id="d6e44-399">사서함 이동을 완료 하는 데 걸리는 시간은 처음에 DEP를 할당 하는 사서함 수와 사서함 크기에 따라 달라 집니다.</span><span class="sxs-lookup"><span data-stu-id="d6e44-399">The time to complete mailbox moves depends on the number of mailboxes to which you assign a DEP for the first time, as well as the size of the mailboxes.</span></span> <span data-ttu-id="d6e44-400">사서함이 DEP를 지정한 시간 이후로 암호화 되지 않은 경우 Microsoft에 문의 하십시오.</span><span class="sxs-lookup"><span data-stu-id="d6e44-400">If the mailboxes have not been encrypted after a week from the time you assigned the DEP, contact Microsoft.</span></span>

## <a name="office-365-setting-up-customer-key-for-sharepoint-online-onedrive-for-business-and-teams-files"></a><span data-ttu-id="d6e44-401">Office 365: SharePoint Online, 비즈니스용 OneDrive 및 팀 파일에 대 한 고객 키 설정</span><span class="sxs-lookup"><span data-stu-id="d6e44-401">Office 365: Setting up Customer Key for SharePoint Online, OneDrive for Business, and Teams files</span></span>

<span data-ttu-id="d6e44-402">시작 하기 전에 Azure 키 자격 증명 모음을 설정 하는 데 필요한 작업을 완료 했는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="d6e44-402">Before you begin, ensure that you have completed the tasks required to set up Azure Key Vault.</span></span> <span data-ttu-id="d6e44-403">자세한 내용은 [Azure Key Vault의 전체 작업 및 Microsoft FastTrack For Customer key](#complete-tasks-in-azure-key-vault-and-microsoft-fasttrack-for-customer-key) 를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="d6e44-403">See [Complete tasks in Azure Key Vault and Microsoft FastTrack for Customer Key](#complete-tasks-in-azure-key-vault-and-microsoft-fasttrack-for-customer-key) for information.</span></span>
  
<span data-ttu-id="d6e44-404">SharePoint Online, 비즈니스용 OneDrive 및 팀 파일에 대 한 고객 키를 설정 하려면 Windows PowerShell을 사용 하 여 SharePoint Online에 원격으로 연결 하 여 다음 단계를 수행 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d6e44-404">To set up Customer Key for SharePoint Online, OneDrive for Business, and Teams files you will need to perform these steps by remotely connecting to SharePoint Online with Windows PowerShell.</span></span>
  
### <a name="create-a-data-encryption-policy-dep-for-each-sharepoint-online-and-onedrive-for-business-geo"></a><span data-ttu-id="d6e44-405">각 SharePoint Online 및 비즈니스용 OneDrive 지역에 대 한 DEP (데이터 암호화 정책)를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="d6e44-405">Create a data encryption policy (DEP) for each SharePoint Online and OneDrive for Business geo</span></span>

<span data-ttu-id="d6e44-406">DEP를 Azure Key Vault에 저장 된 키 집합에 연결 합니다.</span><span class="sxs-lookup"><span data-stu-id="d6e44-406">You associate a DEP with a set of keys stored in Azure Key Vault.</span></span> <span data-ttu-id="d6e44-407">한 지리적 위치에 있는 모든 데이터에 DEP를 적용 합니다 (geo 라고도 함).</span><span class="sxs-lookup"><span data-stu-id="d6e44-407">You apply a DEP to all of your data in one geographic location, also called a geo.</span></span> <span data-ttu-id="d6e44-408">Office 365의 다중 지역 기능을 사용 하는 경우, 지리적으로 서로 다른 키를 사용 하는 기능을 사용 하 여 각 지역에 하나의 DEP를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d6e44-408">If you use the multi-geo feature of Office 365, you can create one DEP per geo with the capability to use different keys per geo.</span></span> <span data-ttu-id="d6e44-409">다중 geo를 사용 하지 않는 경우에는 조직에서 SharePoint Online, 비즈니스용 OneDrive 및 팀 파일에 사용할 DEP를 하나씩 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d6e44-409">If you are not using multi-geo, you can create one DEP in your organization for use with SharePoint Online, OneDrive for Business, and Teams files.</span></span> <span data-ttu-id="d6e44-410">Microsoft 365는 DEP에서 식별 된 키를 사용 하 여 해당 지역에서 데이터를 암호화 합니다.</span><span class="sxs-lookup"><span data-stu-id="d6e44-410">Microsoft 365 uses the keys identified in the DEP to encrypt your data in that geo.</span></span> <span data-ttu-id="d6e44-411">DEP를 만들려면 이전에 가져온 키 보관소 Uri가 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="d6e44-411">To create the DEP, you need the Key Vault URIs you obtained earlier.</span></span> <span data-ttu-id="d6e44-412">지침은 [각 Azure 키 자격 증명 모음 키의 URI 가져오기를](#obtain-the-uri-for-each-azure-key-vault-key) 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="d6e44-412">See [Obtain the URI for each Azure Key Vault key](#obtain-the-uri-for-each-azure-key-vault-key) for instructions.</span></span>
  
<span data-ttu-id="d6e44-413">항상!</span><span class="sxs-lookup"><span data-stu-id="d6e44-413">Remember!</span></span> <span data-ttu-id="d6e44-414">DEP를 만들 때 서로 다른 두 Azure 키 자격 증명 모음에 있는 두 개의 키를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="d6e44-414">When you create a DEP, you specify two keys that reside in two different Azure Key Vaults.</span></span> <span data-ttu-id="d6e44-415">이러한 키가 지리적 중복을 보장 하기 위해 별도의 두 Azure 지역에 위치 하는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="d6e44-415">Ensure that these keys are located in two separate Azure regions to ensure geo-redundancy.</span></span>
  
<span data-ttu-id="d6e44-416">DEP를 만들려면 Windows PowerShell을 사용 하 여 SharePoint Online에 원격으로 연결 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d6e44-416">To create a DEP, you need to remotely connect to SharePoint Online by using Windows PowerShell.</span></span>
  
1. <span data-ttu-id="d6e44-417">로컬 컴퓨터에서 조직에 전역 관리자 권한이 있는 회사 또는 학교 계정을 사용 하 여 [SharePoint Online Powershell에 연결](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online?view=sharepoint-ps)합니다.</span><span class="sxs-lookup"><span data-stu-id="d6e44-417">On your local computer, using a work or school account that has global administrator permissions in your organization, [Connect to SharePoint Online Powershell](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online?view=sharepoint-ps).</span></span>

2. <span data-ttu-id="d6e44-418">Microsoft SharePoint Online 관리 셸에서 다음과 같이 SPODataEncryptionPolicy cmdlet을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="d6e44-418">In the Microsoft SharePoint Online Management Shell, run the Register-SPODataEncryptionPolicy cmdlet as follows:</span></span>

   ```powershell
   Register-SPODataEncryptionPolicy -PrimaryKeyVaultName <PrimaryKeyVaultName> -PrimaryKeyName <PrimaryKeyName> -PrimaryKeyVersion <PrimaryKeyVersion> -SecondaryKeyVaultName <SecondaryKeyVaultName> -SecondaryKeyName <SecondaryKeyName> -SecondaryKeyVersion <SecondaryKeyVersion>
   ```

   <span data-ttu-id="d6e44-419">DEP를 등록 하면 geo의 데이터에 대 한 암호화가 시작 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d6e44-419">When you register the DEP, encryption begins on the data in the geo.</span></span> <span data-ttu-id="d6e44-420">이 작업은 다소 시간이 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d6e44-420">This can take some time.</span></span>

### <a name="validate-file-encryption"></a><span data-ttu-id="d6e44-421">파일 암호화 확인</span><span class="sxs-lookup"><span data-stu-id="d6e44-421">Validate file encryption</span></span>

 <span data-ttu-id="d6e44-422">SharePoint Online, 비즈니스용 OneDrive 및 팀 파일의 암호화를 확인 하려면 [Sharepoint Online PowerShell에 연결한](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell)다음 SPODataEncryptionPolicy cmdlet을 사용 하 여 테 넌 트의 상태를 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="d6e44-422">To validate encryption of SharePoint Online, OneDrive for Business, and Teams files, [connect to SharePoint Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell), and then use the Get-SPODataEncryptionPolicy cmdlet to check the status of your tenant.</span></span> <span data-ttu-id="d6e44-423">고객 키 암호화가 사용 되 고 모든 사이트의 모든 파일이 암호화 된 경우 _State_ 속성은 **등록** 된 값을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="d6e44-423">The _State_ property returns a value of **registered** if Customer Key encryption is enabled and all files in all sites have been encrypted.</span></span> <span data-ttu-id="d6e44-424">암호화가 아직 진행 중인 경우이 cmdlet은 완료 된 사이트 비율에 대 한 정보를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="d6e44-424">If encryption is still in progress, this cmdlet provides information on what percentage of sites is complete.</span></span>

## <a name="related-articles"></a><span data-ttu-id="d6e44-425">관련 문서</span><span class="sxs-lookup"><span data-stu-id="d6e44-425">Related articles</span></span>

- [<span data-ttu-id="d6e44-426">고객 키를 사용한 서비스 암호화</span><span class="sxs-lookup"><span data-stu-id="d6e44-426">Service encryption with Customer Key</span></span>](customer-key-overview.md)

- [<span data-ttu-id="d6e44-427">고객 키 관리</span><span class="sxs-lookup"><span data-stu-id="d6e44-427">Manage Customer Key</span></span>](customer-key-manage.md)

- [<span data-ttu-id="d6e44-428">고객 키 또는 가용성 키 롤 또는 회전</span><span class="sxs-lookup"><span data-stu-id="d6e44-428">Roll or rotate a Customer Key or an availability key</span></span>](customer-key-availability-key-roll.md)

- [<span data-ttu-id="d6e44-429">가용성 키에 대 한 자세한 정보</span><span class="sxs-lookup"><span data-stu-id="d6e44-429">Learn about the availability key</span></span>](customer-key-availability-key-understand.md)

- [<span data-ttu-id="d6e44-430">서비스 암호화</span><span class="sxs-lookup"><span data-stu-id="d6e44-430">Service Encryption</span></span>](office-365-service-encryption.md)
