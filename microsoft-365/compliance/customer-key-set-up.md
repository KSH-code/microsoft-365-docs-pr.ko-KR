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
ms.openlocfilehash: c9c02f697e04a5cd01ddce1546b6712091712025
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/21/2020
ms.locfileid: "43634200"
---
# <a name="set-up-customer-key"></a><span data-ttu-id="e3519-103">고객 키 설정</span><span class="sxs-lookup"><span data-stu-id="e3519-103">Set up Customer Key</span></span>

<span data-ttu-id="e3519-104">고객 키를 사용 하 여 조직의 암호화 키를 제어 하 고 microsoft 365을 구성 하 여 Microsoft 데이터 센터의 휴지 상태에서 데이터를 암호화 합니다.</span><span class="sxs-lookup"><span data-stu-id="e3519-104">With Customer Key, you control your organization's encryption keys and then configure Microsoft 365 to use them to encrypt your data at rest in Microsoft's data centers.</span></span> <span data-ttu-id="e3519-105">즉, 고객 키를 사용 하 여 고객은 해당 키를 포함 하는 암호화 계층을 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e3519-105">In other words, Customer Key allows customers to add a layer of encryption that belongs to them, with their keys.</span></span> <span data-ttu-id="e3519-106">미사용 데이터에는 SharePoint Online 및 비즈니스용 OneDrive에 저장되어 있는 사서함과 파일에 저장된 Exchange Online 및 비즈니스용 Skype의 데이터를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="e3519-106">Data at rest includes data from Exchange Online and Skype for Business that is stored in mailboxes and files that are stored in SharePoint Online and OneDrive for Business.</span></span>

<span data-ttu-id="e3519-107">Office 365에 대해 고객 키를 사용 하려면 먼저 Azure를 설정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e3519-107">You must set up Azure before you can use Customer Key for Office 365.</span></span> <span data-ttu-id="e3519-108">이 항목에서는 필요한 Azure 리소스를 만들고 구성 하기 위해 수행 해야 하는 단계를 설명 하 고 Office 365에서 고객 키를 설정 하는 단계를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="e3519-108">This topic describes the steps you need to follow to create and configure the required Azure resources and then provides the steps for setting up Customer Key in Office 365.</span></span> <span data-ttu-id="e3519-109">Azure 설치를 완료 한 후에는 조직의 사서함과 파일에 할당할 정책 및 키를 결정 합니다.</span><span class="sxs-lookup"><span data-stu-id="e3519-109">After you have completed Azure setup, you determine which policy, and therefore, which keys, to assign to mailboxes and files in your organization.</span></span> <span data-ttu-id="e3519-110">정책을 할당 하지 않을 사서함과 파일은 Microsoft에서 제어 및 관리 하는 암호화 정책을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="e3519-110">Mailboxes and files for which you don't assign a policy will use encryption policies that are controlled and managed by Microsoft.</span></span> <span data-ttu-id="e3519-111">고객 키에 대 한 자세한 내용을 보거나 일반적인 개요를 보려면 [Office 365에서 고객 키를 사용한 서비스 암호화](customer-key-overview.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="e3519-111">For more information about Customer Key, or for a general overview, see [Service encryption with Customer Key in Office 365](customer-key-overview.md).</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="e3519-112">이 항목의 모범 사례를 따르는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="e3519-112">We strongly recommend that you follow the best practices in this topic.</span></span> <span data-ttu-id="e3519-113">이를 **팁** 및 **중요**로 지칭 합니다.</span><span class="sxs-lookup"><span data-stu-id="e3519-113">These are called out as **TIP** and **IMPORTANT**.</span></span> <span data-ttu-id="e3519-114">고객 키를 사용 하 여 전체 조직에 해당 하는 범위를 갖는 루트 암호화 키를 제어할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e3519-114">Customer Key gives you control over root encryption keys whose scope can be as large as your entire organization.</span></span> <span data-ttu-id="e3519-115">즉, 이러한 키를 사용한 실수에 큰 영향을 줄 수 있으며 서비스 중단 또는 irrevocable 데이터 손실을 초래할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e3519-115">This means that mistakes made with these keys can have a broad impact and may result in service interruptions or irrevocable loss of your data.</span></span>
  
## <a name="before-you-set-up-customer-key"></a><span data-ttu-id="e3519-116">Customer 키를 설정 하기 전에</span><span class="sxs-lookup"><span data-stu-id="e3519-116">Before you set up Customer Key</span></span>

<span data-ttu-id="e3519-117">시작 하기 전에 조직에 적합 한 라이선스를 보유 하 고 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="e3519-117">Before you get started, ensure that you have the appropriate licensing for your organization.</span></span> <span data-ttu-id="e3519-118">Microsoft 365의 고객 키는 Office 365 E5 또는 Advanced 준수 SKU에 제공 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e3519-118">Customer Key in Microsoft 365 is offered in Office 365 E5 or the Advanced Compliance SKU.</span></span> <span data-ttu-id="e3519-119">이 항목의 개념과 절차를 이해 하려면 [Azure 키 보관소](https://docs.microsoft.com/azure/key-vault/) 설명서를 검토 하십시오.</span><span class="sxs-lookup"><span data-stu-id="e3519-119">To understand the concepts and procedures in this topic, review the [Azure Key Vault](https://docs.microsoft.com/azure/key-vault/) documentation.</span></span> <span data-ttu-id="e3519-120">또한 Azure에서 사용 되는 용어 (예: [테 넌 트](https://docs.microsoft.com/previous-versions/azure/azure-services/jj573650(v=azure.100)))에 익숙해지는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="e3519-120">Also, become familiar with the terms used in Azure, for example, [tenant](https://docs.microsoft.com/previous-versions/azure/azure-services/jj573650(v=azure.100)).</span></span>

<span data-ttu-id="e3519-121">FastTrack은 고객 키를 등록 하는 데 사용 되는 필수 테 넌 트 및 서비스 구성 정보를 수집 하는 데만 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e3519-121">FastTrack is only used to collect the required tenant and service configuration information used to register for Customer Key.</span></span> <span data-ttu-id="e3519-122">고객 키 제공은 FastTrack을 통해 게시 되므로 사용자와 파트너가 모두 동일한 방법을 사용 하 여 필요한 정보를 제출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e3519-122">The Customer Key Offers are published via FastTrack so that it is convenient for you and our partners to submit the required information using the same method.</span></span> <span data-ttu-id="e3519-123">FastTrack을 사용 하면 제공 되는 데이터를 쉽게 보관할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e3519-123">FastTrack also makes it easy to archive the data that you provide in the Offer.</span></span>
  
<span data-ttu-id="e3519-124">설명서 외에 추가 지원이 필요한 경우에는 MCS (Microsoft 컨설팅 서비스), PFE (프리미어 현장 엔지니어링) 또는 Microsoft 파트너에 게 문의 하세요.</span><span class="sxs-lookup"><span data-stu-id="e3519-124">If you need additional support beyond the documentation, contact Microsoft Consulting Services (MCS), Premier Field Engineering (PFE), or a Microsoft partner for assistance.</span></span> <span data-ttu-id="e3519-125">설명서를 포함 하 여 고객 키에 대 한 의견을 제공 하려면 아이디어, 제안 사항 및 전망을 customerkeyfeedback@microsoft.com으로 전송 합니다.</span><span class="sxs-lookup"><span data-stu-id="e3519-125">To provide feedback on Customer Key, including the documentation, send your ideas, suggestions, and perspectives to customerkeyfeedback@microsoft.com.</span></span>
  
## <a name="overview-of-steps-to-set-up-customer-key"></a><span data-ttu-id="e3519-126">고객 키 설정 단계 개요</span><span class="sxs-lookup"><span data-stu-id="e3519-126">Overview of steps to set up Customer Key</span></span>

<span data-ttu-id="e3519-127">고객 키를 설정 하려면 나열 된 순서 대로 다음 작업을 완료 하세요.</span><span class="sxs-lookup"><span data-stu-id="e3519-127">To set up Customer Key, complete these tasks in the listed order.</span></span> <span data-ttu-id="e3519-128">이 문서의 나머지 부분에서는 각 작업에 대 한 자세한 지침을 제공 하거나 프로세스의 각 단계에 대 한 추가 정보로 연결 되는 내용을 소개 합니다.</span><span class="sxs-lookup"><span data-stu-id="e3519-128">The rest of this article provides detailed instructions for each task, or links out to more information for each step in the process.</span></span>
  
<span data-ttu-id="e3519-129">**Azure 및 Microsoft FastTrack:**</span><span class="sxs-lookup"><span data-stu-id="e3519-129">**In Azure and Microsoft FastTrack:**</span></span>
  
<span data-ttu-id="e3519-130">이러한 작업의 대부분은 Azure PowerShell에 원격으로 연결 하 여 완료 합니다.</span><span class="sxs-lookup"><span data-stu-id="e3519-130">You will complete most of these tasks by remotely connecting to Azure PowerShell.</span></span> <span data-ttu-id="e3519-131">최상의 결과를 위해 Azure PowerShell의 버전 4.4.0 이상을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="e3519-131">For best results, use version 4.4.0 or later of Azure PowerShell.</span></span>
  
- [<span data-ttu-id="e3519-132">두 개의 새 Azure 구독을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="e3519-132">Create two new Azure subscriptions</span></span>](#create-two-new-azure-subscriptions)

- [<span data-ttu-id="e3519-133">필수 보존 기간을 사용 하도록 Azure 구독 등록</span><span class="sxs-lookup"><span data-stu-id="e3519-133">Register Azure subscriptions to use a mandatory retention period</span></span>](#register-azure-subscriptions-to-use-a-mandatory-retention-period)

  <span data-ttu-id="e3519-134">등록에는 영업일 중 근무일까지 소요 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e3519-134">Registration can take from one to five business days.</span></span>

- [<span data-ttu-id="e3519-135">Office 365에 대 한 고객 키를 정품 인증 하기 위한 요청 제출</span><span class="sxs-lookup"><span data-stu-id="e3519-135">Submit a request to activate Customer Key for Office 365</span></span>](#submit-a-request-to-activate-customer-key-for-office-365)

<span data-ttu-id="e3519-136">새로운 두 Azure 구독을 만든 후에는 Microsoft FastTrack 포털에서 호스팅되는 웹 양식을 완료 하 여 해당 하는 고객 키 제공 요청을 제출 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e3519-136">Once you've created the two new Azure subscriptions, you'll need to submit the appropriate Customer Key offer request by completing a web form that is hosted in the Microsoft FastTrack portal.</span></span> <span data-ttu-id="e3519-137">**FastTrack 팀은 고객 키에 대 한 지원을 제공 하지 않습니다. Office는 FastTrack 포털을 사용 하 여 양식을 전송 하 고 고객 키에 대 한 관련 서비스를 추적 하는 데 도움이 됩니다**.</span><span class="sxs-lookup"><span data-stu-id="e3519-137">**The FastTrack team doesn't provide assistance with Customer Key. Office simply uses the FastTrack portal to allow you to submit the form and to help us track the relevant offers for Customer Key**.</span></span>

- [<span data-ttu-id="e3519-138">각 구독에 프리미엄 Azure 키 자격 증명 모음 만들기</span><span class="sxs-lookup"><span data-stu-id="e3519-138">Create a premium Azure Key Vault in each subscription</span></span>](#create-a-premium-azure-key-vault-in-each-subscription)

- [<span data-ttu-id="e3519-139">각 키 자격 증명 모음에 사용 권한 할당</span><span class="sxs-lookup"><span data-stu-id="e3519-139">Assign permissions to each key vault</span></span>](#assign-permissions-to-each-key-vault)

- [<span data-ttu-id="e3519-140">키 자격 증명 모음에서 일시 삭제를 사용 하도록 설정 하 고 확인</span><span class="sxs-lookup"><span data-stu-id="e3519-140">Enable and then confirm soft delete on your key vaults</span></span>](#enable-and-then-confirm-soft-delete-on-your-key-vaults)

- [<span data-ttu-id="e3519-141">키를 만들거나 가져오는 방법으로 각 키 보관소에 키를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="e3519-141">Add a key to each key vault either by creating or importing a key</span></span>](#add-a-key-to-each-key-vault-either-by-creating-or-importing-a-key)

- [<span data-ttu-id="e3519-142">키의 복구 수준 확인</span><span class="sxs-lookup"><span data-stu-id="e3519-142">Check the recovery level of your keys</span></span>](#check-the-recovery-level-of-your-keys)

- [<span data-ttu-id="e3519-143">Azure 키 자격 증명 모음 백업</span><span class="sxs-lookup"><span data-stu-id="e3519-143">Back up Azure Key Vault</span></span>](#back-up-azure-key-vault)

- [<span data-ttu-id="e3519-144">Azure 키 자격 증명 모음 구성 설정 확인</span><span class="sxs-lookup"><span data-stu-id="e3519-144">Validate Azure Key Vault configuration settings</span></span>](#validate-azure-key-vault-configuration-settings)

- [<span data-ttu-id="e3519-145">각 Azure Key Vault 키에 대 한 URI 가져오기</span><span class="sxs-lookup"><span data-stu-id="e3519-145">Obtain the URI for each Azure Key Vault key</span></span>](#obtain-the-uri-for-each-azure-key-vault-key)

<span data-ttu-id="e3519-146">**Office 365에서 다음을 수행 합니다.**</span><span class="sxs-lookup"><span data-stu-id="e3519-146">**In Office 365:**</span></span>
  
<span data-ttu-id="e3519-147">Exchange Online 및 비즈니스용 Skype:</span><span class="sxs-lookup"><span data-stu-id="e3519-147">Exchange Online and Skype for Business:</span></span>
  
- [<span data-ttu-id="e3519-148">Exchange Online 및 비즈니스용 Skype에서 사용 하기 위한 DEP (데이터 암호화 정책) 만들기</span><span class="sxs-lookup"><span data-stu-id="e3519-148">Create a data encryption policy (DEP) for use with Exchange Online and Skype for Business</span></span>](#create-a-data-encryption-policy-dep-for-use-with-exchange-online-and-skype-for-business)

- [<span data-ttu-id="e3519-149">사서함에 DEP 할당</span><span class="sxs-lookup"><span data-stu-id="e3519-149">Assign a DEP to a mailbox</span></span>](#assign-a-dep-to-a-mailbox)

- [<span data-ttu-id="e3519-150">사서함 암호화 유효성 검사</span><span class="sxs-lookup"><span data-stu-id="e3519-150">Validate mailbox encryption</span></span>](#validate-mailbox-encryption)

<span data-ttu-id="e3519-151">SharePoint Online 및 비즈니스용 OneDrive:</span><span class="sxs-lookup"><span data-stu-id="e3519-151">SharePoint Online and OneDrive for Business:</span></span>
  
- [<span data-ttu-id="e3519-152">각 SharePoint Online 및 비즈니스용 OneDrive 지역에 대 한 DEP (데이터 암호화 정책)를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="e3519-152">Create a data encryption policy (DEP) for each SharePoint Online and OneDrive for Business geo</span></span>](#create-a-data-encryption-policy-dep-for-each-sharepoint-online-and-onedrive-for-business-geo)

- [<span data-ttu-id="e3519-153">SharePoint Online, 비즈니스용 OneDrive 및 팀 파일에 대 한 파일 암호화 확인</span><span class="sxs-lookup"><span data-stu-id="e3519-153">Validate file encryption for SharePoint Online, OneDrive for Business, and Teams files</span></span>](#validate-file-encryption)

## <a name="complete-tasks-in-azure-key-vault-and-microsoft-fasttrack-for-customer-key"></a><span data-ttu-id="e3519-154">Azure Key Vault의 완료 작업 및 고객 키 용 Microsoft FastTrack</span><span class="sxs-lookup"><span data-stu-id="e3519-154">Complete tasks in Azure Key Vault and Microsoft FastTrack for Customer Key</span></span>

<span data-ttu-id="e3519-155">Azure Key Vault에서 이러한 작업을 완료 합니다.</span><span class="sxs-lookup"><span data-stu-id="e3519-155">Complete these tasks in Azure Key Vault.</span></span> <span data-ttu-id="e3519-156">Exchange Online 및 비즈니스용 Skype, SharePoint Online, 비즈니스용 OneDrive, 팀 파일 또는 Office 365에서 지원 되는 모든 서비스에 대해 고객 키를 설정할지 여부에 관계 없이 이러한 단계를 완료 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e3519-156">You will need to complete these steps regardless of whether you intend to set up Customer Key for Exchange Online and Skype for Business or for SharePoint Online, OneDrive for Business, and Teams files, or for all supported services in Office 365.</span></span>
  
### <a name="create-two-new-azure-subscriptions"></a><span data-ttu-id="e3519-157">두 개의 새 Azure 구독을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="e3519-157">Create two new Azure subscriptions</span></span>

<span data-ttu-id="e3519-158">고객 키에는 두 개의 Azure 구독이 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="e3519-158">Customer Key requires two Azure subscriptions.</span></span> <span data-ttu-id="e3519-159">최상의 방법으로는 고객 키와 함께 사용할 새로운 Azure 구독을 만드는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="e3519-159">As a best practice, Microsoft recommends that you create new Azure subscriptions for use with Customer Key.</span></span> <span data-ttu-id="e3519-160">Azure Key Vault 키에는 동일한 AAD (Azure Active Directory) 테 넌 트의 응용 프로그램에 대해서만 권한을 부여할 수 있으며, 조직에서 DEPs를 할당할 때 사용 하는 것과 동일한 Azure AD 테 넌 트를 사용 하 여 새 구독을 만들어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e3519-160">Azure Key Vault keys can only be authorized for applications in the same Azure Active Directory (AAD) tenant, you must create the new subscriptions using the same Azure AD tenant used with your organization where the DEPs will be assigned.</span></span> <span data-ttu-id="e3519-161">예를 들어 조직에서 전역 관리자 권한이 있는 회사 또는 학교 계정을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="e3519-161">For example, using your work or school account that has global administrator privileges in your organization.</span></span> <span data-ttu-id="e3519-162">자세한 단계는 [Azure for](https://azure.microsoft.com/documentation/articles/sign-up-organization/)a a a a a a a a a a a as를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="e3519-162">For detailed steps, see [Sign up for Azure as an organization](https://azure.microsoft.com/documentation/articles/sign-up-organization/).</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="e3519-163">고객 키에는 각 DEP (데이터 암호화 정책)에 대 한 두 개의 키가 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="e3519-163">Customer Key requires two keys for each data encryption policy (DEP).</span></span> <span data-ttu-id="e3519-164">이를 위해서는 두 개의 Azure 구독을 만들어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e3519-164">In order to achieve this, you must create two Azure subscriptions.</span></span> <span data-ttu-id="e3519-165">조직의 개별 구성원이 각 구독에서 하나의 키를 구성 하는 것이 가장 좋은 방법입니다.</span><span class="sxs-lookup"><span data-stu-id="e3519-165">As a best practice, Microsoft recommends that you have separate members of your organization configure one key in each subscription.</span></span> <span data-ttu-id="e3519-166">또한 이러한 Azure 구독은 Office 365의 암호화 키를 관리 하는 데에만 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e3519-166">In addition, these Azure subscriptions should only be used to administer encryption keys for Office 365.</span></span> <span data-ttu-id="e3519-167">이렇게 하면 운영자 중 한 명에 게 실수로 또는 악의적으로 삭제 되거나 자신이 담당 하는 키를 잘못 관리 하는 경우를 대비해 조직이 보호 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e3519-167">This protects your organization in case one of your operators accidentally, intentionally, or maliciously deletes or otherwise mismanages the keys for which they are responsible.</span></span> <br/> <span data-ttu-id="e3519-168">Azure Key Vault 리소스를 관리 하는 데에만 사용 되는 새 Azure 구독을 고객 키와 함께 사용 하도록 설정 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="e3519-168">We recommend that you set up new Azure subscriptions that are solely used for managing Azure Key Vault resources for use with Customer Key.</span></span> <span data-ttu-id="e3519-169">조직에 대해 만들 수 있는 Azure 구독 수에는 실질적인 제한이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="e3519-169">There is no practical limit to the number of Azure subscriptions that you can create for your organization.</span></span> <span data-ttu-id="e3519-170">이러한 모범 사례를 따르면 고객 키에서 사용 하는 리소스를 관리 하는 동안 인간 오류가 발생 하는 영향은 최소화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e3519-170">Following these best practices will minimize the impact of human error while helping to manage the resources used by Customer Key.</span></span>
  
### <a name="submit-a-request-to-activate-customer-key-for-office-365"></a><span data-ttu-id="e3519-171">Office 365에 대 한 고객 키를 정품 인증 하기 위한 요청 제출</span><span class="sxs-lookup"><span data-stu-id="e3519-171">Submit a request to activate Customer Key for Office 365</span></span>

<span data-ttu-id="e3519-172">Azure 단계를 완료 한 후에는 [Microsoft FastTrack 포털](https://fasttrack.microsoft.com/)에서 제공 요청을 제출 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e3519-172">Once you've completed the Azure steps, you'll need to submit an offer request in the [Microsoft FastTrack portal](https://fasttrack.microsoft.com/).</span></span> <span data-ttu-id="e3519-173">FastTrack 웹 포털을 통해 요청을 제출 하면 Microsoft는 Azure 키 자격 증명 모음 구성 데이터와 사용자가 제공한 연락처 정보를 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="e3519-173">Once you have submitted a request through the FastTrack web portal, Microsoft verifies the Azure Key Vault configuration data and contact information you provided.</span></span> <span data-ttu-id="e3519-174">조직의 승인 된 관리자와 관련 하 여 제안 양식에서 선택한 항목은 고객 키 등록을 완료 하는 데 필수적이 고 필수적입니다.</span><span class="sxs-lookup"><span data-stu-id="e3519-174">The selections that you make in the offer form regarding the authorized officers of your organization is critical and necessary for completion of Customer Key registration.</span></span> <span data-ttu-id="e3519-175">양식에서 선택한 조직의 직원은 고객 키 데이터 암호화 정책에 사용 되는 모든 키를 해지 하 고 파기 하기 위한 요청의 신뢰성을 보장 하는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e3519-175">The officers of your organization that you select in the form will be the used to ensure the authenticity of any request to revoke and destroy all keys used with a Customer Key data encryption policy.</span></span> <span data-ttu-id="e3519-176">이 단계를 한 번 수행 하 여 Exchange Online 및 비즈니스용 Skype를 위한 고객 키를 정품 인증 하 고 SharePoint Online 및 비즈니스용 OneDrive에 대 한 고객 키를 활성화 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e3519-176">You'll need to do this step once to activate Customer Key for Exchange Online and Skype for Business coverage and a second time to activate Customer Key for SharePoint Online and OneDrive for Business.</span></span>
  
<span data-ttu-id="e3519-177">고객 키를 정품 인증 하기 위한 제안을 제출 하려면 다음 단계를 완료 합니다.</span><span class="sxs-lookup"><span data-stu-id="e3519-177">To submit an offer to activate Customer Key, complete these steps:</span></span>
  
1. <span data-ttu-id="e3519-178">조직에서 전역 관리자 권한이 있는 회사 또는 학교 계정을 사용 하 여 [Microsoft FastTrack 포털](https://fasttrack.microsoft.com/)에 로그인 합니다.</span><span class="sxs-lookup"><span data-stu-id="e3519-178">Using a work or school account that has global administrator permissions in your organization, log in to the [Microsoft FastTrack portal](https://fasttrack.microsoft.com/).</span></span>

2. <span data-ttu-id="e3519-179">로그인 한 후 **대시보드로**이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="e3519-179">Once you're logged in, browse to the **Dashboard**.</span></span>

3. <span data-ttu-id="e3519-180">**서비스**를 선택 하 고 현재 서비스 목록을 검토 합니다.</span><span class="sxs-lookup"><span data-stu-id="e3519-180">Choose **Offers**, and review the list of current offers.</span></span>

4. <span data-ttu-id="e3519-181">사용자에 게 제공 되는 혜택에 대 한 **자세한 정보** 를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="e3519-181">Choose **Learn More** for the offer that applies to you:</span></span>

   - <span data-ttu-id="e3519-182">**Exchange Online 및 비즈니스용 Skype:** **고객 키에서 Exchange 제공에 대 한** **자세한 정보** 를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="e3519-182">**Exchange Online and Skype for Business:** Choose **Learn More** on the **Customer Key for Exchange** offer.</span></span>

   - <span data-ttu-id="e3519-183">**SharePoint Online, 비즈니스용 OneDrive 및 팀 파일:** **SharePoint 용 고객 키 및 비즈니스용 OneDrive** 제공에서 **자세한 정보** 를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="e3519-183">**SharePoint Online, OneDrive for Business, and Teams files:** Choose **Learn More** on the **Customer Key for SharePoint and OneDrive for Business** offer.</span></span>

5. <span data-ttu-id="e3519-184">**제공 세부 정보** 페이지에서 **요청 만들기**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="e3519-184">On the **Offer details** page, choose **Create Request**.</span></span>

6. <span data-ttu-id="e3519-185">제공 양식에서 해당 하는 모든 정보 및 요청 된 정보를 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="e3519-185">Fill out all applicable details and requested information on the offer form.</span></span> <span data-ttu-id="e3519-186">인증을 승인할 조직의 관리자가 선택한 사항에 특별히 주의 하 여 암호화 키와 데이터의 영구 및 복구할 수 없는 소멸을 승인 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e3519-186">Pay particular attention to your selections for which officers of your organization you want to authorize to approve the permanent and irreversible destruction of encryption keys and data.</span></span> <span data-ttu-id="e3519-187">양식을 완료 했으면 **제출을**선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="e3519-187">Once you've completed the form, choose **Submit**.</span></span>

### <a name="register-azure-subscriptions-to-use-a-mandatory-retention-period"></a><span data-ttu-id="e3519-188">필수 보존 기간을 사용 하도록 Azure 구독 등록</span><span class="sxs-lookup"><span data-stu-id="e3519-188">Register Azure subscriptions to use a mandatory retention period</span></span>

<span data-ttu-id="e3519-189">루트 암호화 키의 임시 또는 영구 손실은 매우 방해가 되거나 서비스 작업에 치명적이 될 수 있으며 데이터 손실이 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e3519-189">The temporary or permanent loss of root encryption keys can be very disruptive or even catastrophic to service operation and can result in data loss.</span></span> <span data-ttu-id="e3519-190">이러한 이유로, 고객 키와 함께 사용 되는 리소스에는 강력한 보호가 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="e3519-190">For this reason, the resources used with Customer Key require strong protection.</span></span> <span data-ttu-id="e3519-191">고객 키와 함께 사용 되는 모든 Azure 리소스는 기본 구성 외에도 보호 메커니즘을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="e3519-191">All the Azure resources that are used with Customer Key offer protection mechanisms beyond the default configuration.</span></span> <span data-ttu-id="e3519-192">즉시 및 irrevocable 취소를 방지 하는 방식으로 Azure 구독에 태그를 지정 하거나 등록할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e3519-192">Azure subscriptions can be tagged or registered in a way that will prevent immediate and irrevocable cancellation.</span></span> <span data-ttu-id="e3519-193">이를 필수 보존 기간 등록 이라고 합니다.</span><span class="sxs-lookup"><span data-stu-id="e3519-193">This is referred to as registering for a mandatory retention period.</span></span> <span data-ttu-id="e3519-194">필수 보존 기간 동안 Azure 구독을 등록 하는 데 필요한 단계에는 Microsoft 365 팀과 공동 작업이 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="e3519-194">The steps required to register Azure subscriptions for a mandatory retention period require collaboration with the Microsoft 365 team.</span></span> <span data-ttu-id="e3519-195">이 프로세스는 영업일 이하의 근무일까지 소요 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e3519-195">This process can take from one to five business days.</span></span> <span data-ttu-id="e3519-196">이전에는이를 "취소 안 함"이 라고도 합니다.</span><span class="sxs-lookup"><span data-stu-id="e3519-196">Previously, this was sometimes referred to as "Do Not Cancel".</span></span>
  
<span data-ttu-id="e3519-197">Microsoft 365 팀에 연락 하기 전에 고객 키와 함께 사용 하는 각 Azure 구독에 대해 다음 단계를 수행 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e3519-197">Before contacting the Microsoft 365 team, you must perform the following steps for each Azure subscription that you use with Customer Key.</span></span> <span data-ttu-id="e3519-198">시작 하기 전에 [Azure PowerShell Az](https://docs.microsoft.com/powershell/azure/new-azureps-module-az) 모듈이 설치 되어 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="e3519-198">Ensure that you have the [Azure PowerShell Az](https://docs.microsoft.com/powershell/azure/new-azureps-module-az) module installed before you start.</span></span>
  
1. <span data-ttu-id="e3519-199">Azure PowerShell을 사용 하 여 로그인 합니다.</span><span class="sxs-lookup"><span data-stu-id="e3519-199">Sign in with Azure PowerShell.</span></span> <span data-ttu-id="e3519-200">자세한 내용은 [Azure PowerShell을 사용 하 여 로그인](https://docs.microsoft.com/powershell/azure/authenticate-azureps)을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="e3519-200">For instructions, see [Sign in with Azure PowerShell](https://docs.microsoft.com/powershell/azure/authenticate-azureps).</span></span>

2. <span data-ttu-id="e3519-201">AzProviderFeature cmdlet을 실행 하 여 구독을 등록 하 고 필수 보존 기간을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="e3519-201">Run the Register-AzProviderFeature cmdlet to register your subscriptions to use a mandatory retention period.</span></span> <span data-ttu-id="e3519-202">각 구독에 대해이 작업을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="e3519-202">Perform this action for each subscription.</span></span>

   ```powershell
   Set-AzContext -SubscriptionId <SubscriptionId>
   Register-AzProviderFeature -FeatureName mandatoryRetentionPeriodEnabled -ProviderNamespace Microsoft.KeyVault
   ```

3. <span data-ttu-id="e3519-203">Microsoft에 문의 하 여 해당 프로세스를 완료 합니다.</span><span class="sxs-lookup"><span data-stu-id="e3519-203">Contact Microsoft to have the process finalized.</span></span> <span data-ttu-id="e3519-204">SharePoint 및 비즈니스용 OneDrive 팀의 경우 [spock@microsoft.com](mailto:spock@microsoft.com)에 문의 하세요.</span><span class="sxs-lookup"><span data-stu-id="e3519-204">For the SharePoint and OneDrive for Business team, contact [spock@microsoft.com](mailto:spock@microsoft.com).</span></span> <span data-ttu-id="e3519-205">Exchange Online 및 비즈니스용 Skype에 대 한 자세한 내용은 [exock@microsoft.com](mailto:exock@microsoft.com)에 문의 하세요.</span><span class="sxs-lookup"><span data-stu-id="e3519-205">For Exchange Online and Skype for Business, contact [exock@microsoft.com](mailto:exock@microsoft.com).</span></span> <span data-ttu-id="e3519-206">전자 메일에 다음을 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="e3519-206">Include the following in your email:</span></span>

   <span data-ttu-id="e3519-207">**제목**: \< *테 넌 트의 정규화 된 도메인 이름* 에 대 한 고객 키\></span><span class="sxs-lookup"><span data-stu-id="e3519-207">**Subject**: Customer Key for \<*Your tenant's fully-qualified domain name*\></span></span>

   <span data-ttu-id="e3519-208">**Body**: 필수 보존 기간을 완료 하려는 구독 id입니다.</span><span class="sxs-lookup"><span data-stu-id="e3519-208">**Body**: Subscription IDs for which you want to have the mandatory retention period finalized.</span></span>
   <span data-ttu-id="e3519-209">각 구독에 대 한 AzProviderFeature의 출력입니다.</span><span class="sxs-lookup"><span data-stu-id="e3519-209">The output of Get-AzProviderFeature for each subscription.</span></span>

   <span data-ttu-id="e3519-210">이 프로세스를 완료 하는 데 필요한 SLA (서비스 수준 계약)는 Microsoft가 구독을 등록 하 여 필수 보존 기간을 사용 하도록 공지를 받은 경우 5 일 이내입니다.</span><span class="sxs-lookup"><span data-stu-id="e3519-210">The Service Level Agreement (SLA) for completion of this process is five business days once Microsoft has been notified (and verified) that you have registered your subscriptions to use a mandatory retention period.</span></span>

4. <span data-ttu-id="e3519-211">Microsoft에서 등록이 완료 되었음을 알리는 알림을 받으면 다음과 같이 AzProviderFeature 명령을 실행 하 여 등록 상태를 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="e3519-211">Once you receive notification from Microsoft that registration is complete, verify the status of your registration by running the Get-AzProviderFeature command as follows.</span></span> <span data-ttu-id="e3519-212">확인 된 경우 AzProviderFeature 명령은 **등록 상태** 속성에 대해 **등록** 된 값을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="e3519-212">If verified, the Get-AzProviderFeature command returns a value of **Registered** for the **Registration State** property.</span></span> <span data-ttu-id="e3519-213">각 구독에 대해이 작업을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="e3519-213">Perform this action for each subscription.</span></span>

   ```powershell
   Set-AzContext -SubscriptionId <SubscriptionId>
   Get-AzProviderFeature -ProviderNamespace Microsoft.Resources -FeatureName mandatoryRetentionPeriodEnabled
   ```

5. <span data-ttu-id="e3519-214">프로세스를 완료 하려면 AzResourceProvider 명령을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="e3519-214">To complete the process, run the Register-AzResourceProvider command.</span></span> <span data-ttu-id="e3519-215">각 구독에 대해이 작업을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="e3519-215">Perform this action for each subscription.</span></span>

   ```powershell
   Set-AzContext -SubscriptionId <SubscriptionId>
   Register-AzResourceProvider -ProviderNamespace Microsoft.KeyVault
   ```

### <a name="create-a-premium-azure-key-vault-in-each-subscription"></a><span data-ttu-id="e3519-216">각 구독에 프리미엄 Azure 키 자격 증명 모음 만들기</span><span class="sxs-lookup"><span data-stu-id="e3519-216">Create a premium Azure Key Vault in each subscription</span></span>

<span data-ttu-id="e3519-217">키 자격 증명 모음을 만드는 단계는 azure PowerShell을 설치 및 시작 하 고, Azure 구독에 연결 하 고, 리소스 그룹을 만들고, 해당 리소스 그룹에 키 자격 증명 모음을 만드는 과정을 안내 하는 [Azure Key Vault 시작](https://azure.microsoft.com/documentation/articles/key-vault-get-started/)에 설명 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e3519-217">The steps to create a key vault are documented in [Getting Started with Azure Key Vault](https://azure.microsoft.com/documentation/articles/key-vault-get-started/), which guides you through installing and launching Azure PowerShell, connecting to your Azure subscription, creating a resource group, and creating a key vault in that resource group.</span></span>
  
<span data-ttu-id="e3519-218">키 자격 증명 모음을 만들 때는 SKU: Standard 또는 Premium 중 하나를 선택 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e3519-218">When you create a key vault, you must choose a SKU: either Standard or Premium.</span></span> <span data-ttu-id="e3519-219">Standard SKU를 사용 하면 HSM (하드웨어 보안 모듈) 키 보호가 제공 되지 않으며 프리미엄 SKU는 키 자격 증명 키 보호를 위해 Hsm을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e3519-219">The Standard SKU allows Azure Key Vault keys to be protected with software - there is no Hardware Security Module (HSM) key protection - and the Premium SKU allows the use of HSMs for protection of Key Vault keys.</span></span> <span data-ttu-id="e3519-220">고객 키가 SKU를 사용 하는 키 보관소를 허용 하지만, Microsoft에서는 프리미엄 SKU만 사용 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="e3519-220">Customer Key accepts key vaults that use either SKU, though Microsoft strongly recommends that you use only the Premium SKU.</span></span> <span data-ttu-id="e3519-221">두 가지 유형의 키를 사용한 작업 비용은 같으므로, 각 HSM 보호 키에 대 한 월별 비용은 비용의 차이입니다.</span><span class="sxs-lookup"><span data-stu-id="e3519-221">The cost of operations with keys of either type is the same, so the only difference in cost is the cost per month for each HSM-protected key.</span></span> <span data-ttu-id="e3519-222">자세한 내용은 [키 자격 증명 모음 가격 산정](https://azure.microsoft.com/pricing/details/key-vault/) 을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="e3519-222">See [Key Vault pricing](https://azure.microsoft.com/pricing/details/key-vault/) for details.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="e3519-223">프로덕션 데이터에 대해 Premium SKU 키 보관소 및 HSM으로 보호 된 키를 사용 하 고 테스트 및 유효성 검사를 위해 Standard SKU 키 보관소와 키만 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="e3519-223">Use the Premium SKU key vaults and HSM-protected keys for production data, and only use Standard SKU key vaults and keys for testing and validation purposes.</span></span>
  
<span data-ttu-id="e3519-224">고객 키를 사용 하는 각 Microsoft 365 서비스에 대해 사용자가 만든 두 Azure 구독 각각에 키 자격 증명 모음을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="e3519-224">For each Microsoft 365 service with which you will use Customer Key, create a key vault in each of the two Azure subscriptions that you created.</span></span> <span data-ttu-id="e3519-225">예를 들어 Exchange Online 및 비즈니스용 Skype 전용 또는 SharePoint Online 및 비즈니스용 OneDrive 전용의 경우에는 하나의 자격 증명 모음만 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="e3519-225">For example, for Exchange Online and Skype for Business only or SharePoint Online and OneDrive for Business only, you will create only one pair of vaults.</span></span> <span data-ttu-id="e3519-226">Exchange Online 및 SharePoint Online 둘 다에 대해 고객 키를 사용 하도록 설정 하기 위해 두 쌍의 키 자격 증명 모음을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="e3519-226">To enable Customer Key for both Exchange Online and SharePoint Online, you will create two pairs of key vaults.</span></span>
  
<span data-ttu-id="e3519-227">자격 증명 모음을 연결할 데이터 암호화 정책의 용도를 반영 하는 키 보관소에 대 한 명명 규칙을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="e3519-227">Use a naming convention for key vaults that reflects the intended use of the data encryption policy with which you will associate the vaults.</span></span> <span data-ttu-id="e3519-228">명명 규칙 추천을 보려면 아래에서 모범 사례 섹션을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="e3519-228">See the Best Practices section below for naming convention recommendations.</span></span>
  
<span data-ttu-id="e3519-229">각 데이터 암호화 정책에 대해 쌍을 이룬 별도의 자격 증명 모음을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="e3519-229">Create a separate, paired set of vaults for each data encryption policy.</span></span> <span data-ttu-id="e3519-230">Exchange Online의 경우 사서함에 정책을 할당할 때 사용자가 데이터 암호화 정책의 범위를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="e3519-230">For Exchange Online, the scope of a data encryption policy is chosen by you when you assign the policy to mailbox.</span></span> <span data-ttu-id="e3519-231">사서함에는 정책이 하나만 할당 될 수 있으며 최대 50 개의 정책을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e3519-231">A mailbox can have only one policy assigned, and you can create up to fifty policies.</span></span> <span data-ttu-id="e3519-232">SharePoint Online의 경우 정책의 범위는 지리적 위치 또는 _지리적_으로 조직 내의 모든 데이터입니다.</span><span class="sxs-lookup"><span data-stu-id="e3519-232">For SharePoint Online the scope of a policy is all of the data within an organization in a geographic location, or _geo_.</span></span>

<span data-ttu-id="e3519-233">또한 키 보관소에는 저장소 용량 (매우 작음)과 키 보관소 로깅이 필요 하기 때문에 (키 보관소를 만드는 경우) 저장 된 데이터도 생성 해야 하므로 Azure 리소스 그룹을 만들어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e3519-233">The creation of key vaults also requires the creation of Azure resource groups, since key vaults need storage capacity (though very small) and Key Vault logging, if enabled, also generates stored data.</span></span> <span data-ttu-id="e3519-234">Microsoft는 별도의 관리자를 사용 하 여 각 리소스 그룹을 관리할 것을 권장 하 고, 관리를 모든 관련 고객 키 리소스를 관리 하는 관리자 집합과 맞추고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e3519-234">As a best practice Microsoft recommends using separate administrators to manage each resource group, with the administration aligned with the set of administrators that will manage all related Customer Key resources.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="e3519-235">가용성을 최대화 하기 위해 주요 자격 증명은 Microsoft 365 서비스에 가까운 지역에 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e3519-235">To maximize availability, your key vaults should be in regions close to your Microsoft 365 service.</span></span> <span data-ttu-id="e3519-236">예를 들어 Exchange Online 조직이 북미에 있는 경우 북미에 키 자격 증명 모음을 배치 합니다.</span><span class="sxs-lookup"><span data-stu-id="e3519-236">For example, if your Exchange Online organization is in North America, place your key vaults in North America.</span></span> <span data-ttu-id="e3519-237">Exchange Online 조직이 유럽에 있는 경우 키 보관소를 유럽에 배치 합니다.</span><span class="sxs-lookup"><span data-stu-id="e3519-237">If your Exchange Online organization is in Europe, place your key vaults in Europe.</span></span><br/><span data-ttu-id="e3519-238">키 자격 증명에 대 한 일반적인 접두사를 사용 하 고, 키 보관소와 키의 사용 및 범위 약어를 포함 하 고 (예: 보관소가 있는 Contoso SharePoint 서비스의 경우에는 해당 하는 이름 쌍이 Contoso-O365SP-VaultA1 및 Contoso-O365SP-VaultA2입니다.</span><span class="sxs-lookup"><span data-stu-id="e3519-238">Use a common prefix for key vaults, and include an abbreviation of the use and scope of the key vault and keys (e.g., for the Contoso SharePoint service where the vaults will be located in North America, a possible pair of names is Contoso-O365SP-NA-VaultA1 and Contoso-O365SP-NA-VaultA2.</span></span> <span data-ttu-id="e3519-239">자격 증명 이름은 Azure 내의 전역적으로 고유한 문자열이 되므로 필요한 이름이 다른 Azure 고객의 요청을 받아야 하는 경우에 대비 하 여 원하는 이름의 변형을 시도해 야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e3519-239">Vault names are globally unique strings within Azure, so you may need to try variations of your desired names in case the desired names are already claimed by other Azure customers.</span></span> <span data-ttu-id="e3519-240">7 월 2017 볼트 이름은 변경할 수 없으므로 설정 계획을 수립 하 고 두 번째 사용자를 사용 하 여 계획이 올바르게 실행 되는지 확인 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="e3519-240">As of July 2017 vault names cannot be changed, so a best practice is to have a written plan for setup and use a second person to verify the plan is executed correctly.</span></span><br/><span data-ttu-id="e3519-241">가능 하면 페어링되지 않은 지역에 자격 증명 모음을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="e3519-241">If possible, create your vaults in non-paired regions.</span></span> <span data-ttu-id="e3519-242">쌍을 이룬 Azure 지역에서 서비스 장애 도메인 별로 고가용성을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="e3519-242">Paired Azure regions provide high availability across service failure domains.</span></span> <span data-ttu-id="e3519-243">따라서 지역 쌍을 서로의 백업 지역으로 간주할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e3519-243">Therefore, regional pairs can be thought of as each other's backup region.</span></span> <span data-ttu-id="e3519-244">즉, 한 지역에 배치 된 Azure 리소스가 연결 된 지역을 통과 하는 내결함성을 자동으로 획득 합니다.</span><span class="sxs-lookup"><span data-stu-id="e3519-244">This means that an Azure resource that is placed in one region is automatically gaining fault tolerance through the paired region.</span></span> <span data-ttu-id="e3519-245">이러한 이유 때문에 지역이 연결 된 데이터 암호화 정책에서 사용 되는 두 개의 보관소에 대 한 영역을 선택 하는 것은 사용 중인 사용 가능한 영역의 총 두 영역만을 의미 합니다.</span><span class="sxs-lookup"><span data-stu-id="e3519-245">For this reason, choosing regions for two vaults used in a data encryption policy where the regions are paired means that only a total of two regions of availability are in use.</span></span> <span data-ttu-id="e3519-246">대부분의 지역에는 두 지역이 있으므로 아직 연결 되지 않은 영역을 선택할 수는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="e3519-246">Most geographies only have two regions, so it's not yet possible to select non-paired regions.</span></span> <span data-ttu-id="e3519-247">가능 하면 데이터 암호화 정책에 사용 되는 두 개의 보관소에 대해 쌍이 없는 두 개의 영역을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="e3519-247">If possible, choose two non-paired regions for the two vaults used with a data encryption policy.</span></span> <span data-ttu-id="e3519-248">이는 가용성의 총 4 지역에서 혜택을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="e3519-248">This benefits from a total of four regions of availability.</span></span> <span data-ttu-id="e3519-249">자세한 내용은 [Business 연속성 및 재해 복구 (BCDR):](https://docs.microsoft.com/azure/best-practices-availability-paired-regions) 현재 지역 쌍 목록의 Azure 연결 된 지역을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="e3519-249">For more information, see [Business continuity and disaster recovery (BCDR): Azure Paired Regions](https://docs.microsoft.com/azure/best-practices-availability-paired-regions) for a current list of regional pairs.</span></span>
  
### <a name="assign-permissions-to-each-key-vault"></a><span data-ttu-id="e3519-250">각 키 자격 증명 모음에 사용 권한 할당</span><span class="sxs-lookup"><span data-stu-id="e3519-250">Assign permissions to each key vault</span></span>

<span data-ttu-id="e3519-251">각 키 보관소에 대해 구현에 따라 고객 키에 대해 세 가지 개별 사용 권한 집합을 정의 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e3519-251">For each key vault, you will need to define three separate sets of permissions for Customer Key, depending on your implementation.</span></span> <span data-ttu-id="e3519-252">예를 들어 다음 각 항목에 대해 하나의 권한 집합을 정의 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e3519-252">For example, you will need to define one set of permissions for each of the following:</span></span>
  
- <span data-ttu-id="e3519-253">조직에 대 한 주요 자격 증명 모음을 일상적인 관리 하는 데 사용할 수 있는 **주요 자격 증명 모음 관리자**</span><span class="sxs-lookup"><span data-stu-id="e3519-253">**Key vault administrators** that will perform day-to-day management of your key vault for your organization.</span></span> <span data-ttu-id="e3519-254">이러한 작업에는 백업, 만들기, 가져오기, 가져오기, 목록, 복원 등이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e3519-254">These tasks include backup, create, get, import, list, and restore.</span></span>

  > [!IMPORTANT]
  > <span data-ttu-id="e3519-255">키 자격 증명 모음 관리자에 게 할당 된 사용 권한 집합에는 키를 삭제할 수 있는 권한이 포함 되어 있지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="e3519-255">The set of permissions assigned to key vault administrators does not include the permission to delete keys.</span></span> <span data-ttu-id="e3519-256">이는 의도적인 것이 고 중요 한 방법입니다.</span><span class="sxs-lookup"><span data-stu-id="e3519-256">This is intentional and an important practice.</span></span> <span data-ttu-id="e3519-257">일반적으로 암호화 키 삭제는 데이터를 영구적으로 소멸 하기 때문에 수행 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="e3519-257">Deleting encryption keys is not typically done, since doing so permanently destroys data.</span></span> <span data-ttu-id="e3519-258">주요 자격 증명 모음 관리자에 게 기본적으로이 사용 권한을 부여 하지 않는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="e3519-258">As a best practice, do not grant this permission to key vault administrators by default.</span></span> <span data-ttu-id="e3519-259">대신 주요 자격 증명 참가자에 대해이를 예약 하 고, 결과에 대 한 확실 한 이해가 이해 되 면 짧은 기간 동안 관리자 에게만 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="e3519-259">Instead, reserve this for key vault contributors and only assign it to an administrator on a short term basis once a clear understanding of the consequences is understood.</span></span>
  
  <span data-ttu-id="e3519-260">조직의 사용자에 게 이러한 사용 권한을 할당 하려면 Azure PowerShell을 사용 하 여 Azure 구독에 로그인 합니다.</span><span class="sxs-lookup"><span data-stu-id="e3519-260">To assign these permissions to a user in your organization, log in to your Azure subscription with Azure PowerShell.</span></span> <span data-ttu-id="e3519-261">자세한 내용은 [Azure PowerShell을 사용 하 여 로그인](https://docs.microsoft.com/powershell/azure/authenticate-azureps)을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="e3519-261">For instructions, see [Sign in with Azure PowerShell](https://docs.microsoft.com/powershell/azure/authenticate-azureps).</span></span>

- <span data-ttu-id="e3519-262">AzKeyVaultAccessPolicy cmdlet을 실행 하 여 필요한 권한을 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="e3519-262">Run the Set-AzKeyVaultAccessPolicy cmdlet to assign the necessary permissions.</span></span>

   ```powershell
   Set-AzKeyVaultAccessPolicy -VaultName <vault name> -UserPrincipalName <UPN of user> -PermissionsToKeys create,import,list,get,backup,restore
   ```

   <span data-ttu-id="e3519-263">예시:</span><span class="sxs-lookup"><span data-stu-id="e3519-263">For example:</span></span>

   ```powershell
   Set-AzKeyVaultAccessPolicy -VaultName Contoso-O365EX-NA-VaultA1 -UserPrincipalName alice@contoso.com -PermissionsToKeys create,import,list,get,backup,restore
   ```

- <span data-ttu-id="e3519-264">Azure 키 자격 증명 모음 자체에 대 한 사용 권한을 변경할 수 있는 **키 보관소 참가자**</span><span class="sxs-lookup"><span data-stu-id="e3519-264">**Key vault contributors** that can change permissions on the Azure Key Vault itself.</span></span> <span data-ttu-id="e3519-265">직원은 팀에 탈퇴 하거나 참가할 때 이러한 권한을 변경 해야 하며, 키 보관소 관리자가 키를 삭제 하거나 복원 하는 데 필요한 권한을 갖는 것이 아주 드문 경우입니다.</span><span class="sxs-lookup"><span data-stu-id="e3519-265">You'll need to change these permissions as employees leave or join your team, or in the extremely rare situation that the key vault administrators legitimately need permission to delete or restore a key.</span></span> <span data-ttu-id="e3519-266">이 키 보관소 참가자 집합에는 해당 키 자격 증명 모음에 대 한 **참가자** 역할이 부여 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e3519-266">This set of key vault contributors needs to be granted the **Contributor** role on your key vault.</span></span> <span data-ttu-id="e3519-267">Azure Resource Manager를 사용 하 여이 역할을 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e3519-267">You can assign this role by using Azure Resource Manager.</span></span> <span data-ttu-id="e3519-268">자세한 단계는 [역할 기반 액세스 제어를 사용 하 여 Azure 구독 리소스에 대 한 액세스를 관리 하](https://docs.microsoft.com/azure/active-directory/role-based-access-control-configure)는 방법을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="e3519-268">For detailed steps, see [Use Role-Based Access Control to manage access to your Azure subscription resources](https://docs.microsoft.com/azure/active-directory/role-based-access-control-configure).</span></span> <span data-ttu-id="e3519-269">구독을 만드는 관리자는이 액세스 권한 뿐만 아니라 다른 관리자에 게 참가자 역할을 할당할 수 있는 권한도 제공 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e3519-269">The administrator who creates a subscription has this access implicitly, as well as the ability to assign other administrators to the Contributor role.</span></span>

- <span data-ttu-id="e3519-270">Exchange Online 및 비즈니스용 Skype에서 고객 키를 사용 하려는 경우에는 Microsoft 365에 대 한 권한을 부여 하 여 Exchange Online 및 비즈니스용 Skype를 대신 하 여 키 자격 증명 모음을 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e3519-270">If you intend to use Customer Key with Exchange Online and Skype for Business, you need to give permission to Microsoft 365 to use the key vault on behalf of Exchange Online and Skype for Business.</span></span> <span data-ttu-id="e3519-271">마찬가지로, SharePoint Online 및 비즈니스용 OneDrive에서 고객 키를 사용 하려는 경우에는 Microsoft 365에 대 한 권한을 추가 하 여 SharePoint Online 및 비즈니스용 OneDrive를 대신 하 여 키 자격 증명 모음을 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e3519-271">Likewise, if you intend to use Customer Key with SharePoint Online and OneDrive for Business, you need to add permission for the Microsoft 365 to use the key vault on behalf of SharePoint Online and OneDrive for Business.</span></span> <span data-ttu-id="e3519-272">Microsoft 365에 대 한 사용 권한을 부여 하려면 다음 구문을 사용 하 여 **AzKeyVaultAccessPolicy** cmdlet을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="e3519-272">To give permission to Microsoft 365, run the **Set-AzKeyVaultAccessPolicy** cmdlet using the following syntax:</span></span> 

   ```powershell
   Set-AzKeyVaultAccessPolicy -VaultName <vault name> -PermissionsToKeys wrapKey,unwrapKey,get -ServicePrincipalName <Office 365 appID>
   ```

   <span data-ttu-id="e3519-273">여기서,</span><span class="sxs-lookup"><span data-stu-id="e3519-273">Where:</span></span>

    - <span data-ttu-id="e3519-274">*vault 이름은* 만든 키 보관소의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="e3519-274">*vault name* is the name of the key vault you created.</span></span>

    - <span data-ttu-id="e3519-275">Exchange Online 및 비즈니스용 Skype의 경우 *Office 365 appID* 를 다음으로 바꾸기`00000002-0000-0ff1-ce00-000000000000`</span><span class="sxs-lookup"><span data-stu-id="e3519-275">For Exchange Online and Skype for Business, replace  *Office 365 appID* with `00000002-0000-0ff1-ce00-000000000000`</span></span>

    - <span data-ttu-id="e3519-276">SharePoint Online, 비즈니스용 OneDrive 및 팀 파일의 경우 *Office 365 appID* 를 다음으로 바꾸기`00000003-0000-0ff1-ce00-000000000000`</span><span class="sxs-lookup"><span data-stu-id="e3519-276">For SharePoint Online, OneDrive for Business, and Teams files, replace  *Office 365 appID* with `00000003-0000-0ff1-ce00-000000000000`</span></span>

  <span data-ttu-id="e3519-277">예: Exchange Online 및 비즈니스용 Skype에 대 한 사용 권한 설정:</span><span class="sxs-lookup"><span data-stu-id="e3519-277">Example: Setting permissions for Exchange Online and Skype for Business:</span></span>

   ```powershell
   Set-AzKeyVaultAccessPolicy -VaultName Contoso-O365EX-NA-VaultA1 -PermissionsToKeys wrapKey,unwrapKey,get -ServicePrincipalName 00000002-0000-0ff1-ce00-000000000000
   ```

  <span data-ttu-id="e3519-278">예: SharePoint Online, 비즈니스용 OneDrive 및 팀 파일에 대 한 사용 권한 설정:</span><span class="sxs-lookup"><span data-stu-id="e3519-278">Example: Setting permissions for SharePoint Online, OneDrive for Business, and Teams files:</span></span>

   ```powershell
   Set-AzKeyVaultAccessPolicy -VaultName Contoso-O365SP-NA-VaultA1 -PermissionsToKeys wrapKey,unwrapKey,get -ServicePrincipalName 00000003-0000-0ff1-ce00-000000000000
   ```

### <a name="enable-and-then-confirm-soft-delete-on-your-key-vaults"></a><span data-ttu-id="e3519-279">키 자격 증명 모음에서 일시 삭제를 사용 하도록 설정 하 고 확인</span><span class="sxs-lookup"><span data-stu-id="e3519-279">Enable and then confirm soft delete on your key vaults</span></span>

<span data-ttu-id="e3519-280">키를 신속 하 게 복구할 수 있으면 실수로 또는 악의적으로 삭제 된 키로 인해 확장 서비스 중단을 경험할 가능성이 줄어듭니다.</span><span class="sxs-lookup"><span data-stu-id="e3519-280">When you can quickly recover your keys, you are less likely to experience an extended service outage due to accidentally or maliciously deleted keys.</span></span> <span data-ttu-id="e3519-281">사용자 키에 키를 사용할 수 있으려면 먼저 소프트 삭제 라고 하는이 구성을 사용 하도록 설정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e3519-281">You need to enable this configuration, referred to as Soft Delete, before you can use your keys with Customer Key.</span></span> <span data-ttu-id="e3519-282">소프트 삭제를 사용 하도록 설정 하면 백업에서 복원 하지 않고도 90 일 내에 키 또는 자격 증명 모음을 복구할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e3519-282">Enabling Soft Delete allows you to recover keys or vaults within 90 days of deletion without having to restore them from backup.</span></span>
  
<span data-ttu-id="e3519-283">키 자격 증명 모음에서 일시 삭제를 사용 하도록 설정 하려면 다음 단계를 완료 합니다.</span><span class="sxs-lookup"><span data-stu-id="e3519-283">To enable Soft Delete on your key vaults, complete these steps:</span></span>
  
1. <span data-ttu-id="e3519-284">Windows Powershell을 사용 하 여 Azure 구독에 로그인 합니다.</span><span class="sxs-lookup"><span data-stu-id="e3519-284">Sign in to your Azure subscription with Windows Powershell.</span></span> <span data-ttu-id="e3519-285">자세한 내용은 [Azure PowerShell을 사용 하 여 로그인](https://docs.microsoft.com/powershell/azure/authenticate-azureps)을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="e3519-285">For instructions, see [Sign in with Azure PowerShell](https://docs.microsoft.com/powershell/azure/authenticate-azureps).</span></span>

2. <span data-ttu-id="e3519-286">[AzKeyVault](https://docs.microsoft.com/powershell/module/az.keyvault/get-azkeyvault) cmdlet을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="e3519-286">Run the [Get-AzKeyVault](https://docs.microsoft.com/powershell/module/az.keyvault/get-azkeyvault) cmdlet.</span></span> <span data-ttu-id="e3519-287">이 예에서 *보관소 이름은* 소프트 삭제를 활성화할 수 있는 키 보관소의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="e3519-287">In this example, *vault name* is the name of the key vault for which you are enabling soft delete:</span></span>

   ```powershell
   $v = Get-AzKeyVault -VaultName <vault name>
   $r = Get-AzResource -ResourceId $v.ResourceId
   $r.Properties | Add-Member -MemberType NoteProperty -Name enableSoftDelete -Value 'True'
   Set-AzResource -ResourceId $r.ResourceId -Properties $r.Properties
   ```

3. <span data-ttu-id="e3519-288">**AzKeyVault** cmdlet을 실행 하 여 키 자격 증명 모음에 대해 소프트 삭제가 구성 되었는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="e3519-288">Confirm soft delete is configured for the key vault by running the **Get-AzKeyVault** cmdlet.</span></span> <span data-ttu-id="e3519-289">키 자격 증명 모음에 대해 소프트 삭제가 올바르게 구성 된 경우 _소프트 삭제 Enabled_ 속성은 **True**값을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="e3519-289">If soft delete is configured properly for the key vault, then the _Soft Delete Enabled_ property returns a value of **True**:</span></span>

   ```powershell
   Get-AzKeyVault -VaultName <vault name> | fl
   ```

### <a name="add-a-key-to-each-key-vault-either-by-creating-or-importing-a-key"></a><span data-ttu-id="e3519-290">키를 만들거나 가져오는 방법으로 각 키 보관소에 키를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="e3519-290">Add a key to each key vault either by creating or importing a key</span></span>

<span data-ttu-id="e3519-291">Azure 키 보관소에는 두 가지 방법으로 키를 추가할 수 있습니다. 키 보관소에 직접 키를 만들거나 키를 가져올 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e3519-291">There are two ways to add keys to an Azure Key Vault; you can create a key directly in Key Vault, or you can import a key.</span></span> <span data-ttu-id="e3519-292">키 보관소에서 직접 키를 만드는 것은 다소 복잡 한 방법 이지만 키를 가져오면 키가 생성 되는 방식을 보다 강력 하 게 제어할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e3519-292">Creating a key directly in Key Vault is the less complicated method, while importing a key provides total control over how the key is generated.</span></span>
  
<span data-ttu-id="e3519-293">키 보관소에 직접 키를 만들려면 다음과 같이 [AzKeyVaultKey](https://docs.microsoft.com/powershell/module/az.keyvault/add-azkeyvaultkey) cmdlet을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="e3519-293">To create a key directly in your key vault, run the [Add-AzKeyVaultKey](https://docs.microsoft.com/powershell/module/az.keyvault/add-azkeyvaultkey) cmdlet as follows:</span></span>
  
```powershell
Add-AzKeyVaultKey -VaultName <vault name> -Name <key name> -Destination <HSM|Software> -KeyOps wrapKey,unwrapKey
```

<span data-ttu-id="e3519-294">여기서,</span><span class="sxs-lookup"><span data-stu-id="e3519-294">Where:</span></span>

- <span data-ttu-id="e3519-295">*vault 이름은* 키를 만들 키 자격 증명 모음의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="e3519-295">*vault name* is the name of the key vault in which you want to create the key.</span></span>

- <span data-ttu-id="e3519-296">*키 이름은* 새 키에 지정할 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="e3519-296">*key name* is the name you want to give the new key.</span></span>

  > [!TIP]
  > <span data-ttu-id="e3519-297">키 보관소에 대해 위에서 설명한 유사 명명 규칙을 사용 하 여 이름 키</span><span class="sxs-lookup"><span data-stu-id="e3519-297">Name keys using a similar naming convention as described above for key vaults.</span></span> <span data-ttu-id="e3519-298">이러한 방식으로 키 이름만 표시 되는 도구에서 문자열은 자체 설명입니다.</span><span class="sxs-lookup"><span data-stu-id="e3519-298">This way, in tools that show only the key name, the string is self-describing.</span></span>
  
- <span data-ttu-id="e3519-299">HSM을 사용 하 여 키를 보호 하려면 _대상_ 매개 변수의 값으로 **HSM** 을 지정 하 고, 그렇지 않으면 **소프트웨어**를 지정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e3519-299">If you intend to protect the key with an HSM, ensure that you specify **HSM** as the value of the _Destination_ parameter, otherwise, specify **Software**.</span></span>

<span data-ttu-id="e3519-300">For example,</span><span class="sxs-lookup"><span data-stu-id="e3519-300">For example,</span></span>
  
```powershell
Add-AzKeyVaultKey -VaultName Contoso-O365EX-NA-VaultA1 -Name Contoso-O365EX-NA-VaultA1-Key001 -Destination Software -KeyOps wrapKey,unwrapKey
```

<span data-ttu-id="e3519-301">키 보관소로 바로 키를 가져오려면 Thales nShield 하드웨어 보안 모듈이 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e3519-301">To import a key directly into your key vault, you need to have a Thales nShield Hardware Security Module.</span></span>
  
<span data-ttu-id="e3519-302">일부 조직에서는이 방법을 선호 하 여 키의 provenance을 설정 하 고,이 방법 역시 다음을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="e3519-302">Some organizations prefer this approach to establish the provenance of their keys, and the this method also provides the following:</span></span>
  
- <span data-ttu-id="e3519-303">가져오기에 사용 되는 도구 집합에는 Thales에서 생성 하는 키를 암호화 하는 데 사용 되는 KEK (키 교환 키)가 내보낼 수 없으며 Thales에서 제조한 정품 HSM 내에서 생성 된다는 것이 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e3519-303">The tool set used for import includes attestation from Thales that the Key Exchange Key (KEK) that is used to encrypt the key you generate is not exportable and is generated inside a genuine HSM that was manufactured by Thales.</span></span>

- <span data-ttu-id="e3519-304">이 도구 집합에는 Thales에서 제조한 정품 HSM 에서도 Azure 키 자격 증명 모음 보안 세계가 생성 된 Thales의 증명이 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e3519-304">The tool set includes attestation from Thales that the Azure Key Vault security world was also generated on a genuine HSM manufactured by Thales.</span></span> <span data-ttu-id="e3519-305">이 증명은 Microsoft가 정품 Thales 하드웨어를 사용 하 고 있음을 증명 합니다.</span><span class="sxs-lookup"><span data-stu-id="e3519-305">This attestation proves to you that Microsoft is also using genuine Thales hardware.</span></span>

<span data-ttu-id="e3519-306">보안 그룹을 확인 하 여 위의 attestations 필요한 지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="e3519-306">Check with your security group to determine if the above attestations are required.</span></span> <span data-ttu-id="e3519-307">온-프레미스 키를 만들고 키 보관소로 가져오는 자세한 단계 [는 Azure Key vault에 대해 HSM 보호 키를 생성 하 고 전송 하는 방법을](https://azure.microsoft.com/documentation/articles/key-vault-hsm-protected-keys/)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="e3519-307">For detailed steps to create a key on-premises and import it into your key vault, see [How to generate and transfer HSM-protected keys for Azure Key Vault](https://azure.microsoft.com/documentation/articles/key-vault-hsm-protected-keys/).</span></span> <span data-ttu-id="e3519-308">Azure 지침을 사용 하 여 각 키 자격 증명 모음에 키를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="e3519-308">Use the Azure instructions to create a key in each key vault.</span></span>
  
### <a name="check-the-recovery-level-of-your-keys"></a><span data-ttu-id="e3519-309">키의 복구 수준 확인</span><span class="sxs-lookup"><span data-stu-id="e3519-309">Check the recovery level of your keys</span></span>

<span data-ttu-id="e3519-310">Microsoft 365에서는 Azure 키 자격 증명 모음 구독이 취소 되지 않도록 설정 되 고, 고객 키에 사용 되는 키에 소프트 삭제가 사용 되도록 되어 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e3519-310">Microsoft 365 requires that the Azure Key Vault subscription is set to Do Not Cancel and that the keys used by Customer Key have soft delete enabled.</span></span> <span data-ttu-id="e3519-311">키의 복구 수준을 확인 하 여이를 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e3519-311">You can confirm this by looking at the recovery level on your keys.</span></span>
  
<span data-ttu-id="e3519-312">키의 복구 수준을 확인 하려면 Azure PowerShell에서 다음과 같이 AzKeyVaultKey cmdlet을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="e3519-312">To check the recovery level of a key, in Azure PowerShell, run the Get-AzKeyVaultKey cmdlet as follows:</span></span>
  
```powershell
(Get-AzKeyVaultKey -VaultName <vault name> -Name <key name>).Attributes
```

<span data-ttu-id="e3519-313">_복구 수준_ 속성에서 복구 **가능한 + ProtectedSubscription**값이 아닌 다른 항목을 반환 하는 경우에는이 항목을 검토 하 여 구독을 취소 하지 않고 각 키 보관소에 소프트 삭제를 사용 하도록 설정 하는 모든 단계를 따랐는지 확인 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e3519-313">If the _Recovery Level_ property returns anything other than a value of **Recoverable+ProtectedSubscription**, you will need to review this topic and ensure that you have followed all of the steps to put the subscription on the Do Not Cancel list and that you have soft delete enabled on each of your key vaults.</span></span>
  
### <a name="back-up-azure-key-vault"></a><span data-ttu-id="e3519-314">Azure 키 자격 증명 모음 백업</span><span class="sxs-lookup"><span data-stu-id="e3519-314">Back up Azure Key Vault</span></span>

<span data-ttu-id="e3519-315">키를 만들거나 변경 하는 즉시 백업 및 오프 라인 복사본을 백업 및 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="e3519-315">Immediately following creation or any change to a key, perform a backup and store copies of the backup, both online and offline.</span></span> <span data-ttu-id="e3519-316">오프 라인 복사본은 실제 안전 또는 상업적 저장소 기능과 같은 네트워크에 연결 해서는 안 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e3519-316">Offline copies should not be connected to any network, such as in a physical safe or commercial storage facility.</span></span> <span data-ttu-id="e3519-317">재해 발생 시 액세스할 수 있는 위치에 백업 복사본을 하나 이상 저장 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e3519-317">At least one copy of the backup should be stored in a location that will be accessible in the event of a disaster.</span></span> <span data-ttu-id="e3519-318">백업 blob은 키 자료를 복원 하는 유일한 방법으로 키 자격 증명 키를 영구적으로 제거 하거나 작동 하지 않는 방식으로 렌더링 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e3519-318">The backup blobs are the sole means of restoring key material should a Key Vault key be permanently destroyed or otherwise rendered inoperable.</span></span> <span data-ttu-id="e3519-319">Azure 키 자격 증명 모음에 대 한 외부 키를 가져오고 Azure 키 보관소로 가져온 키는 해당 키를 사용 하는 데 필요한 메타 데이터가 외부 키가 없기 때문에 백업으로 한정 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="e3519-319">Keys that are external to Azure Key Vault and were imported to Azure Key Vault do not qualify as a backup because the metadata necessary for Customer Key to use the key does not exist with the external key.</span></span> <span data-ttu-id="e3519-320">Azure Key Vault에서 가져온 백업만 고객 키를 사용한 복원 작업에 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e3519-320">Only a backup taken from Azure Key Vault can be used for restore operations with Customer Key.</span></span> <span data-ttu-id="e3519-321">따라서 키가 업로드 되거나 생성 되 면 Azure 키 자격 증명 모음을 백업 하는 것이 중요 합니다.</span><span class="sxs-lookup"><span data-stu-id="e3519-321">Therefore, it is essential that a backup of Azure Key Vault be made once a key is uploaded or created.</span></span>
  
<span data-ttu-id="e3519-322">Azure 키 자격 증명 키의 백업을 만들려면 다음과 같이 [AzKeyVaultKey](https://docs.microsoft.com/powershell/module/az.keyvault/backup-azkeyvaultkey) cmdlet을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="e3519-322">To create a backup of an Azure Key Vault key, run the [Backup-AzKeyVaultKey](https://docs.microsoft.com/powershell/module/az.keyvault/backup-azkeyvaultkey) cmdlet as follows:</span></span>

```powershell
Backup-AzKeyVaultKey -VaultName <vault name> -Name <key name>
-OutputFile <filename.backup>
```

<span data-ttu-id="e3519-323">출력 파일이 접미사 `.backup`를 사용 하는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="e3519-323">Ensure that your output file uses the suffix `.backup`.</span></span>
  
<span data-ttu-id="e3519-324">이 cmdlet에서 생성 된 출력 파일은 암호화 되며 Azure 키 자격 증명 모음 외부에서 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="e3519-324">The output file resulting from this cmdlet is encrypted and cannot be used outside of Azure Key Vault.</span></span> <span data-ttu-id="e3519-325">백업은 백업을 수행한 Azure 구독에만 복원할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e3519-325">The backup can be restored only to the Azure subscription from which the backup was taken.</span></span>
  
> [!TIP]
> <span data-ttu-id="e3519-326">출력 파일의 경우 자격 증명 모음 이름 및 키 이름을 조합 하 여 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="e3519-326">For the output file, choose a combination of your vault name and key name.</span></span> <span data-ttu-id="e3519-327">이렇게 하면 파일 이름이 자체 설명 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e3519-327">This will make the file name self-describing.</span></span> <span data-ttu-id="e3519-328">또한 백업 파일 이름이 충돌 하지 않도록 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e3519-328">It will also ensure that backup file names do not collide.</span></span>
  
<span data-ttu-id="e3519-329">예시:</span><span class="sxs-lookup"><span data-stu-id="e3519-329">For example:</span></span>
  
```powershell
Backup-AzKeyVaultKey -VaultName Contoso-O365EX-NA-VaultA1 -Name Contoso-O365EX-NA-VaultA1-Key001 -OutputFile Contoso-O365EX-NA-VaultA1-Key001-Backup-20170802.backup
```

### <a name="validate-azure-key-vault-configuration-settings"></a><span data-ttu-id="e3519-330">Azure 키 자격 증명 모음 구성 설정 확인</span><span class="sxs-lookup"><span data-stu-id="e3519-330">Validate Azure Key Vault configuration settings</span></span>

<span data-ttu-id="e3519-331">DEP에서 키를 사용 하기 전에 유효성 검사를 수행 하는 것은 선택 사항 이지만 가급적 권장 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e3519-331">Performing validation before using keys in a DEP is optional, but highly recommended.</span></span> <span data-ttu-id="e3519-332">특히이 항목에서 설명 하는 것과 다른 키 및 보관소를 설정 하는 단계를 사용 하는 경우에는 고객 키를 구성 하기 전에 Azure Key Vault 리소스의 상태를 확인 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e3519-332">In particular, if you use steps to set up your keys and vaults other than the ones described in this topic, you should validate the health of your Azure Key Vault resources before you configure Customer Key.</span></span>
  
<span data-ttu-id="e3519-333">키가 get, wrapKey 및 unwrapKey 작업을 사용 하도록 설정 되었는지 확인 하려면 다음을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="e3519-333">To verify that your keys have get, wrapKey, and unwrapKey operations enabled:</span></span>
  
<span data-ttu-id="e3519-334">다음과 같이 [AzKeyVault](https://docs.microsoft.com/powershell/module/az.keyvault/get-azkeyvault) cmdlet을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="e3519-334">Run the [Get-AzKeyVault](https://docs.microsoft.com/powershell/module/az.keyvault/get-azkeyvault) cmdlet as follows:</span></span>
  
```powershell
Get-AzKeyVault -VaultName <vault name>
```

<span data-ttu-id="e3519-335">출력에서 액세스 정책 및 Exchange Online id (guid) 또는 SharePoint Online id (GUID)를 적절 하 게 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="e3519-335">In the output, look for the Access Policy and for the Exchange Online identity (GUID) or the SharePoint Online identity (GUID) as appropriate.</span></span> <span data-ttu-id="e3519-336">위의 세 가지 사용 권한 중 일부는 키 사용 권한 아래에 표시 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e3519-336">All three of the above permissions must be shown under Permissions to Keys.</span></span>
  
<span data-ttu-id="e3519-337">액세스 정책 구성이 올바르지 않으면 다음과 같이 AzKeyVaultAccessPolicy cmdlet을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="e3519-337">If the access policy configuration is incorrect, run the Set-AzKeyVaultAccessPolicy cmdlet as follows:</span></span>
  
```powershell
Set-AzKeyVaultAccessPolicy -VaultName <vault name> -PermissionsToKeys wrapKey,unwrapKey,get -ServicePrincipalName <Office 365 appID>
```

<span data-ttu-id="e3519-338">예를 들어 Exchange Online 및 비즈니스용 Skype의 경우:</span><span class="sxs-lookup"><span data-stu-id="e3519-338">For example, for Exchange Online and Skype for Business:</span></span>
  
```powershell
Set-AzKeyVaultAccessPolicy -VaultName Contoso-O365EX-NA-VaultA1 
-PermissionsToKeys wrapKey,unwrapKey,get -ServicePrincipalName 00000002-0000-0ff1-ce00-000000000000
```

<span data-ttu-id="e3519-339">예를 들어 SharePoint Online 및 비즈니스용 OneDrive:</span><span class="sxs-lookup"><span data-stu-id="e3519-339">For example, for SharePoint Online and OneDrive for Business:</span></span>
  
```powershell
Set-AzKeyVaultAccessPolicy -VaultName Contoso-O365SP-NA-VaultA1
-PermissionsToKeys wrapKey,unwrapKey,get -ServicePrincipalName TBD
```

<span data-ttu-id="e3519-340">키에 대해 만료 날짜가 설정 되지 않았는지 확인 하려면 다음과 같이 [AzKeyVaultKey](https://docs.microsoft.com/powershell/module/az.keyvault/get-azkeyvault) cmdlet을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="e3519-340">To verify that an expiration date is not set for your keys run the [Get-AzKeyVaultKey](https://docs.microsoft.com/powershell/module/az.keyvault/get-azkeyvault) cmdlet as follows:</span></span>
  
```powershell
Get-AzKeyVaultKey -VaultName <vault name>
```

<span data-ttu-id="e3519-341">만료 된 키는 고객 키에서 사용할 수 없으며 만료 된 키로 시도한 작업은 실패 하 고 서비스 중단으로 인해 발생할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e3519-341">An expired key cannot be used by Customer Key and operations attempted with an expired key will fail, and possibly result in a service outage.</span></span> <span data-ttu-id="e3519-342">고객 키와 함께 사용 되는 키에는 만료 날짜가 없을 것을 적극 권장 합니다.</span><span class="sxs-lookup"><span data-stu-id="e3519-342">We strongly recommend that keys used with Customer Key do not have an expiration date.</span></span> <span data-ttu-id="e3519-343">만료 날짜를 설정한 후에는 제거할 수 없지만 다른 날짜로 변경할 수는 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e3519-343">An expiration date, once set, cannot be removed, but can be changed to a different date.</span></span> <span data-ttu-id="e3519-344">만료 날짜가 설정 된 키를 사용 해야 하는 경우 만료 값을 12/31/9999로 변경 합니다.</span><span class="sxs-lookup"><span data-stu-id="e3519-344">If a key must be used that has an expiration date set, change the expiration value to 12/31/9999.</span></span> <span data-ttu-id="e3519-345">만료 날짜가 12/31/9999 이외의 날짜로 설정 된 키는 Microsoft 365 유효성 검사를 통과 하지 못합니다.</span><span class="sxs-lookup"><span data-stu-id="e3519-345">Keys with an expiration date set to a date other than 12/31/9999 will not pass Microsoft 365 validation.</span></span>
  
<span data-ttu-id="e3519-346">12/31/9999 이외의 값으로 설정 된 만료 날짜를 변경 하려면 다음과 같이 [AzKeyVaultKey](https://docs.microsoft.com/powershell/module/az.keyvault/update-azkeyvaultkey) cmdlet을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="e3519-346">To change an expiration date that has been set to any value other than 12/31/9999, run the [Update-AzKeyVaultKey](https://docs.microsoft.com/powershell/module/az.keyvault/update-azkeyvaultkey) cmdlet as follows:</span></span>
  
```powershell
Update-AzKeyVaultKey -VaultName <vault name> -Name <key name> -Expires (Get-Date -Date "12/31/9999")
```

> [!CAUTION]
> <span data-ttu-id="e3519-347">고객 키와 함께 사용 하는 암호화 키에 대해 만료 날짜를 설정 하지 마십시오.</span><span class="sxs-lookup"><span data-stu-id="e3519-347">Don't set expiration dates on encryption keys you use with Customer Key.</span></span>
  
### <a name="obtain-the-uri-for-each-azure-key-vault-key"></a><span data-ttu-id="e3519-348">각 Azure Key Vault 키에 대 한 URI 가져오기</span><span class="sxs-lookup"><span data-stu-id="e3519-348">Obtain the URI for each Azure Key Vault key</span></span>

<span data-ttu-id="e3519-349">Azure의 모든 단계를 완료 하 여 키 자격 증명 모음을 설정 하 고 키를 추가한 후에는 다음 명령을 실행 하 여 각 키 자격 증명 모음에서 키에 대 한 URI를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="e3519-349">Once you've completed all the steps in Azure to set up your key vaults and added your keys, run the following command to get the URI for the key in each key vault.</span></span> <span data-ttu-id="e3519-350">나중에 각 DEP를 만들고 할당할 때 이러한 Uri를 사용 해야 하므로이 정보를 안전한 장소에 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="e3519-350">You will need to use these URIs when you create and assign each DEP later, so save this information in a safe place.</span></span> <span data-ttu-id="e3519-351">각 키 자격 증명 모음에 대해 한 번씩이 명령을 실행 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e3519-351">Remember to run this command once for each key vault.</span></span>
  
<span data-ttu-id="e3519-352">Azure PowerShell:</span><span class="sxs-lookup"><span data-stu-id="e3519-352">In Azure PowerShell:</span></span>
  
```powershell
(Get-AzKeyVaultKey -VaultName <vault name>).Id
```

## <a name="office-365-setting-up-customer-key-for-exchange-online-and-skype-for-business"></a><span data-ttu-id="e3519-353">Office 365: Exchange Online 및 비즈니스용 Skype에 대 한 고객 키 설정</span><span class="sxs-lookup"><span data-stu-id="e3519-353">Office 365: Setting up Customer Key for Exchange Online and Skype for Business</span></span>

<span data-ttu-id="e3519-354">시작 하기 전에 Azure 키 자격 증명 모음을 설정 하는 데 필요한 작업을 완료 했는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="e3519-354">Before you begin, ensure that you have completed the tasks required to set up Azure Key Vault.</span></span> <span data-ttu-id="e3519-355">자세한 내용은 [Azure Key Vault의 전체 작업 및 Microsoft FastTrack For Customer key](#complete-tasks-in-azure-key-vault-and-microsoft-fasttrack-for-customer-key) 를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="e3519-355">See [Complete tasks in Azure Key Vault and Microsoft FastTrack for Customer Key](#complete-tasks-in-azure-key-vault-and-microsoft-fasttrack-for-customer-key) for information.</span></span>
  
<span data-ttu-id="e3519-356">Exchange Online 및 비즈니스용 Skype에 대 한 고객 키를 설정 하려면 Windows PowerShell을 사용 하 여 Exchange Online에 원격으로 연결 하 여 다음 단계를 수행 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e3519-356">To set up Customer Key for Exchange Online and Skype for Business, you will need to perform these steps by remotely connecting to Exchange Online with Windows PowerShell.</span></span>
  
### <a name="create-a-data-encryption-policy-dep-for-use-with-exchange-online-and-skype-for-business"></a><span data-ttu-id="e3519-357">Exchange Online 및 비즈니스용 Skype에서 사용 하기 위한 DEP (데이터 암호화 정책) 만들기</span><span class="sxs-lookup"><span data-stu-id="e3519-357">Create a data encryption policy (DEP) for use with Exchange Online and Skype for Business</span></span>

<span data-ttu-id="e3519-358">DEP는 Azure Key Vault에 저장 된 키 집합과 연결 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e3519-358">A DEP is associated with a set of keys stored in Azure Key Vault.</span></span> <span data-ttu-id="e3519-359">Microsoft 365에서 사서함에 DEP를 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="e3519-359">You assign a DEP to a mailbox in Microsoft 365.</span></span> <span data-ttu-id="e3519-360">Microsoft 365에서는 정책에 식별 된 키를 사용 하 여 사서함을 암호화 합니다.</span><span class="sxs-lookup"><span data-stu-id="e3519-360">Microsoft 365 will then use the keys identified in the policy to encrypt the mailbox.</span></span> <span data-ttu-id="e3519-361">DEP를 만들려면 이전에 가져온 키 보관소 Uri가 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="e3519-361">To create the DEP, you need the Key Vault URIs you obtained earlier.</span></span> <span data-ttu-id="e3519-362">지침은 [각 Azure 키 자격 증명 모음 키의 URI 가져오기를](#obtain-the-uri-for-each-azure-key-vault-key) 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="e3519-362">See [Obtain the URI for each Azure Key Vault key](#obtain-the-uri-for-each-azure-key-vault-key) for instructions.</span></span>
  
<span data-ttu-id="e3519-363">항상!</span><span class="sxs-lookup"><span data-stu-id="e3519-363">Remember!</span></span> <span data-ttu-id="e3519-364">DEP를 만들 때 서로 다른 두 Azure 키 자격 증명 모음에 있는 두 개의 키를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="e3519-364">When you create a DEP, you specify two keys that reside in two different Azure Key Vaults.</span></span> <span data-ttu-id="e3519-365">이러한 키가 지리적 중복을 보장 하기 위해 별도의 두 Azure 지역에 위치 하는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="e3519-365">Ensure that these keys are located in two separate Azure regions to ensure geo-redundancy.</span></span>
  
<span data-ttu-id="e3519-366">DEP를 만들려면 다음 단계를 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="e3519-366">To create the DEP, follow these steps:</span></span>
  
1. <span data-ttu-id="e3519-367">로컬 컴퓨터에서 조직에 전역 관리자 권한이 있는 회사 또는 학교 계정을 사용 하 여 Windows PowerShell을 열고 다음 명령을 실행 하 여 [Exchange Online PowerShell에 연결](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell?view=exchange-ps) 합니다.</span><span class="sxs-lookup"><span data-stu-id="e3519-367">On your local computer, using a work or school account that has global administrator permissions in your organization, [connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell?view=exchange-ps) by opening Windows PowerShell and running the following command.</span></span>

   ```powershell
   $UserCredential = Get-Credential
   ```

2. <span data-ttu-id="e3519-368">Windows PowerShell 자격 증명 요청 대화 상자에서 회사 또는 학교 계정 정보를 입력 하 고 **확인**을 클릭 한 후에 다음 명령을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="e3519-368">In the Windows PowerShell Credential Request dialog box, enter your work or school account information, click **OK**, and then enter the following command.</span></span>

   ```powershell
   $Session = New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://outlook.office365.com/powershell-liveid/ -Credential $UserCredential -Authentication Basic -AllowRedirection
   ```

3. <span data-ttu-id="e3519-369">다음 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="e3519-369">Run the following command.</span></span>

   ```powershell
   Import-PSSession $Session
   ```

4. <span data-ttu-id="e3519-370">DEP를 만들려면 다음 명령을 입력 하 여 새-DataEncryptionPolicy cmdlet을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="e3519-370">To create a DEP, use the New-DataEncryptionPolicy cmdlet by typing the following command.</span></span>

   ```powershell
   New-DataEncryptionPolicy -Name <PolicyName> -Description "Policy Description" -AzureKeyIDs <KeyVaultURI1>, <KeyVaultURI2>
   ```

   <span data-ttu-id="e3519-371">여기서,</span><span class="sxs-lookup"><span data-stu-id="e3519-371">Where:</span></span>

   - <span data-ttu-id="e3519-372">*PolicyName* 는 정책에 사용 하려는 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="e3519-372">*PolicyName* is the name you want to use for the policy.</span></span> <span data-ttu-id="e3519-373">이름에 공백을 포함할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="e3519-373">Names cannot contain spaces.</span></span> <span data-ttu-id="e3519-374">예를 USA_mailboxes 합니다.</span><span class="sxs-lookup"><span data-stu-id="e3519-374">For example, USA_mailboxes.</span></span>

   - <span data-ttu-id="e3519-375">정책 *설명은* 정책에 대 한 정보를 파악 하는 데 도움이 되는 정책에 대 한 사용자 친숙 한 설명입니다.</span><span class="sxs-lookup"><span data-stu-id="e3519-375">*Policy Description* is a user friendly description of the policy that will help you remember what the policy is for.</span></span> <span data-ttu-id="e3519-376">설명에 공백을 포함할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e3519-376">You can include spaces in the description.</span></span> <span data-ttu-id="e3519-377">예를 들어 "미국 및 지역의 사서함에 대 한 루트 키"입니다.</span><span class="sxs-lookup"><span data-stu-id="e3519-377">For example, "Root key for mailboxes in USA and its territories".</span></span>

   - <span data-ttu-id="e3519-378">*KeyVaultURI1* 는 정책의 첫 번째 키에 대 한 URI입니다.</span><span class="sxs-lookup"><span data-stu-id="e3519-378">*KeyVaultURI1* is the URI for the first key in the policy.</span></span> <span data-ttu-id="e3519-379">예를 들면 https://contoso_EastUSvault01.vault.azure.net/keys/USA_key_01와 같습니다.</span><span class="sxs-lookup"><span data-stu-id="e3519-379">For example, https://contoso_EastUSvault01.vault.azure.net/keys/USA_key_01.</span></span>

   - <span data-ttu-id="e3519-380">*KeyVaultURI2* 은 정책의 두 번째 키에 대 한 URI입니다.</span><span class="sxs-lookup"><span data-stu-id="e3519-380">*KeyVaultURI2* is the URI for the second key in the policy.</span></span> <span data-ttu-id="e3519-381">예를 들면 https://contoso_EastUS2vault01.vault.azure.net/keys/USA_Key_02와 같습니다.</span><span class="sxs-lookup"><span data-stu-id="e3519-381">For example, https://contoso_EastUS2vault01.vault.azure.net/keys/USA_Key_02.</span></span> <span data-ttu-id="e3519-382">두 Uri를 쉼표와 공백으로 구분 합니다.</span><span class="sxs-lookup"><span data-stu-id="e3519-382">Separate the two URIs by a comma and a space.</span></span>

   <span data-ttu-id="e3519-383">예제:</span><span class="sxs-lookup"><span data-stu-id="e3519-383">Example:</span></span>
  
   ```powershell
   New-DataEncryptionPolicy -Name USA_mailboxes -Description "Root key for mailboxes in USA and its territories" -AzureKeyIDs https://contoso_EastUSvault01.vault.azure.net/keys/USA_key_01, https://contoso_EastUS2vault01.vault.azure.net/keys/USA_Key_02
   ```

### <a name="assign-a-dep-to-a-mailbox"></a><span data-ttu-id="e3519-384">사서함에 DEP 할당</span><span class="sxs-lookup"><span data-stu-id="e3519-384">Assign a DEP to a mailbox</span></span>

<span data-ttu-id="e3519-385">사서함 cmdlet을 사용 하 여 사서함에 DEP를 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="e3519-385">Assign the DEP to a mailbox by using the Set-Mailbox cmdlet.</span></span> <span data-ttu-id="e3519-386">정책을 할당 하면 Microsoft 365에서 DEP에 지정 된 키로 사서함을 암호화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e3519-386">Once you assign the policy, Microsoft 365 can encrypt the mailbox with the key designated in the DEP.</span></span>
  
```powershell
Set-Mailbox -Identity <MailboxIdParameter> -DataEncryptionPolicy <PolicyName>
```

<span data-ttu-id="e3519-387">여기서 *MailboxIdParameter* 는 사서함을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="e3519-387">Where *MailboxIdParameter* specifies a mailbox.</span></span> <span data-ttu-id="e3519-388">사서함 cmdlet에 대 한 자세한 내용은 [set-mailbox](https://docs.microsoft.com/powershell/module/exchange/mailboxes/set-mailbox?view=exchange-ps)를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="e3519-388">For more information about the Set-Mailbox cmdlet, see [Set-Mailbox](https://docs.microsoft.com/powershell/module/exchange/mailboxes/set-mailbox?view=exchange-ps).</span></span>
  
### <a name="validate-mailbox-encryption"></a><span data-ttu-id="e3519-389">사서함 암호화 유효성 검사</span><span class="sxs-lookup"><span data-stu-id="e3519-389">Validate mailbox encryption</span></span>

<span data-ttu-id="e3519-390">사서함을 암호화 하는 데 다소 시간이 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e3519-390">Encrypting a mailbox can take some time.</span></span> <span data-ttu-id="e3519-391">처음 정책 할당의 경우에는 서비스에서 사서함을 암호화 하기 전에 사서함이 한 데이터베이스에서 다른 데이터베이스로 완전히 이동 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e3519-391">For first time policy assignment, the mailbox must also completely move from one database to another before the service can encrypt the mailbox.</span></span> <span data-ttu-id="e3519-392">DEP를 변경한 후 또는 사서함에 DEP를 처음 할당할 때 암호화 유효성 검사를 시도 하기 전에 72 시간을 기다리는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="e3519-392">We recommend that you wait 72 hours before you attempt to validate encryption after you change a DEP or the first time you assign a DEP to a mailbox.</span></span>
  
<span data-ttu-id="e3519-393">Get-mailboxstatistics cmdlet을 사용 하 여 사서함이 암호화 되어 있는지 여부를 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e3519-393">Use the Get-MailboxStatistics cmdlet to determine if a mailbox is encrypted.</span></span>
  
```powershell
Get-MailboxStatistics -Identity <GeneralMailboxOrMailUserIdParameter> | fl IsEncrypted
```

<span data-ttu-id="e3519-394">사서함이 암호화 된 경우 IsEncrypted 속성은 **true** 값을 반환 하 고 사서함이 암호화 되지 않은 경우에는 **false** 로 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="e3519-394">The IsEncrypted property returns a value of **true** if the mailbox is encrypted and a value of **false** if the mailbox is not encrypted.</span></span>

<span data-ttu-id="e3519-395">사서함 이동을 완료 하는 데 걸리는 시간은 처음에 DEP를 할당 하는 사서함 수와 사서함 크기에 따라 달라 집니다.</span><span class="sxs-lookup"><span data-stu-id="e3519-395">The time to complete mailbox moves depends on the number of mailboxes to which you assign a DEP for the first time, as well as the size of the mailboxes.</span></span> <span data-ttu-id="e3519-396">사서함이 DEP를 지정한 시간 이후로 암호화 되지 않은 경우 Microsoft에 문의 하십시오.</span><span class="sxs-lookup"><span data-stu-id="e3519-396">If the mailboxes have not been encrypted after a week from the time you assigned the DEP, contact Microsoft.</span></span>

## <a name="office-365-setting-up-customer-key-for-sharepoint-online-onedrive-for-business-and-teams-files"></a><span data-ttu-id="e3519-397">Office 365: SharePoint Online, 비즈니스용 OneDrive 및 팀 파일에 대 한 고객 키 설정</span><span class="sxs-lookup"><span data-stu-id="e3519-397">Office 365: Setting up Customer Key for SharePoint Online, OneDrive for Business, and Teams files</span></span>

<span data-ttu-id="e3519-398">시작 하기 전에 Azure 키 자격 증명 모음을 설정 하는 데 필요한 작업을 완료 했는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="e3519-398">Before you begin, ensure that you have completed the tasks required to set up Azure Key Vault.</span></span> <span data-ttu-id="e3519-399">자세한 내용은 [Azure Key Vault의 전체 작업 및 Microsoft FastTrack For Customer key](#complete-tasks-in-azure-key-vault-and-microsoft-fasttrack-for-customer-key) 를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="e3519-399">See [Complete tasks in Azure Key Vault and Microsoft FastTrack for Customer Key](#complete-tasks-in-azure-key-vault-and-microsoft-fasttrack-for-customer-key) for information.</span></span>
  
<span data-ttu-id="e3519-400">SharePoint Online, 비즈니스용 OneDrive 및 팀 파일에 대 한 고객 키를 설정 하려면 Windows PowerShell을 사용 하 여 SharePoint Online에 원격으로 연결 하 여 다음 단계를 수행 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e3519-400">To set up Customer Key for SharePoint Online, OneDrive for Business, and Teams files you will need to perform these steps by remotely connecting to SharePoint Online with Windows PowerShell.</span></span>
  
### <a name="create-a-data-encryption-policy-dep-for-each-sharepoint-online-and-onedrive-for-business-geo"></a><span data-ttu-id="e3519-401">각 SharePoint Online 및 비즈니스용 OneDrive 지역에 대 한 DEP (데이터 암호화 정책)를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="e3519-401">Create a data encryption policy (DEP) for each SharePoint Online and OneDrive for Business geo</span></span>

<span data-ttu-id="e3519-402">DEP를 Azure Key Vault에 저장 된 키 집합에 연결 합니다.</span><span class="sxs-lookup"><span data-stu-id="e3519-402">You associate a DEP with a set of keys stored in Azure Key Vault.</span></span> <span data-ttu-id="e3519-403">한 지리적 위치에 있는 모든 데이터에 DEP를 적용 합니다 (geo 라고도 함).</span><span class="sxs-lookup"><span data-stu-id="e3519-403">You apply a DEP to all of your data in one geographic location, also called a geo.</span></span> <span data-ttu-id="e3519-404">Office 365의 다중 지역 기능을 사용 하는 경우, 지리적으로 서로 다른 키를 사용 하는 기능을 사용 하 여 각 지역에 하나의 DEP를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e3519-404">If you use the multi-geo feature of Office 365, you can create one DEP per geo with the capability to use different keys per geo.</span></span> <span data-ttu-id="e3519-405">다중 geo를 사용 하지 않는 경우에는 조직에서 SharePoint Online, 비즈니스용 OneDrive 및 팀 파일에 사용할 DEP를 하나씩 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e3519-405">If you are not using multi-geo, you can create one DEP in your organization for use with SharePoint Online, OneDrive for Business, and Teams files.</span></span> <span data-ttu-id="e3519-406">Microsoft 365는 DEP에서 식별 된 키를 사용 하 여 해당 지역에서 데이터를 암호화 합니다.</span><span class="sxs-lookup"><span data-stu-id="e3519-406">Microsoft 365 uses the keys identified in the DEP to encrypt your data in that geo.</span></span> <span data-ttu-id="e3519-407">DEP를 만들려면 이전에 가져온 키 보관소 Uri가 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="e3519-407">To create the DEP, you need the Key Vault URIs you obtained earlier.</span></span> <span data-ttu-id="e3519-408">지침은 [각 Azure 키 자격 증명 모음 키의 URI 가져오기를](#obtain-the-uri-for-each-azure-key-vault-key) 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="e3519-408">See [Obtain the URI for each Azure Key Vault key](#obtain-the-uri-for-each-azure-key-vault-key) for instructions.</span></span>
  
<span data-ttu-id="e3519-409">항상!</span><span class="sxs-lookup"><span data-stu-id="e3519-409">Remember!</span></span> <span data-ttu-id="e3519-410">DEP를 만들 때 서로 다른 두 Azure 키 자격 증명 모음에 있는 두 개의 키를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="e3519-410">When you create a DEP, you specify two keys that reside in two different Azure Key Vaults.</span></span> <span data-ttu-id="e3519-411">이러한 키가 지리적 중복을 보장 하기 위해 별도의 두 Azure 지역에 위치 하는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="e3519-411">Ensure that these keys are located in two separate Azure regions to ensure geo-redundancy.</span></span>
  
<span data-ttu-id="e3519-412">DEP를 만들려면 Windows PowerShell을 사용 하 여 SharePoint Online에 원격으로 연결 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e3519-412">To create a DEP, you need to remotely connect to SharePoint Online by using Windows PowerShell.</span></span>
  
1. <span data-ttu-id="e3519-413">로컬 컴퓨터에서 조직에 전역 관리자 권한이 있는 회사 또는 학교 계정을 사용 하 여 [SharePoint Online Powershell에 연결](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online?view=sharepoint-ps)합니다.</span><span class="sxs-lookup"><span data-stu-id="e3519-413">On your local computer, using a work or school account that has global administrator permissions in your organization, [Connect to SharePoint Online Powershell](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online?view=sharepoint-ps).</span></span>

2. <span data-ttu-id="e3519-414">Microsoft SharePoint Online 관리 셸에서 다음과 같이 SPODataEncryptionPolicy cmdlet을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="e3519-414">In the Microsoft SharePoint Online Management Shell, run the Register-SPODataEncryptionPolicy cmdlet as follows:</span></span>

   ```powershell
   Register-SPODataEncryptionPolicy -Identity <SPOAdminSiteUrl> -PrimaryKeyVaultName <PrimaryKeyVaultName> -PrimaryKeyName <PrimaryKeyName> -PrimaryKeyVersion <PrimaryKeyVersion> -SecondaryKeyVaultName <SecondaryKeyVaultName> -SecondaryKeyName <SecondaryKeyName> -SecondaryKeyVersion <SecondaryKeyVersion>
   ```

   <span data-ttu-id="e3519-415">DEP를 등록 하면 geo의 데이터에 대 한 암호화가 시작 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e3519-415">When you register the DEP, encryption begins on the data in the geo.</span></span> <span data-ttu-id="e3519-416">이 작업은 다소 시간이 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e3519-416">This can take some time.</span></span>

### <a name="validate-file-encryption"></a><span data-ttu-id="e3519-417">파일 암호화 확인</span><span class="sxs-lookup"><span data-stu-id="e3519-417">Validate file encryption</span></span>

 <span data-ttu-id="e3519-418">SharePoint Online, 비즈니스용 OneDrive 및 팀 파일의 암호화를 확인 하려면 [Sharepoint Online PowerShell에 연결한](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell?view=exchange-ps)다음 SPODataEncryptionPolicy cmdlet을 사용 하 여 테 넌 트의 상태를 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="e3519-418">To validate encryption of SharePoint Online, OneDrive for Business, and Teams files, [connect to SharePoint Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell?view=exchange-ps), and then use the Get-SPODataEncryptionPolicy cmdlet to check the status of your tenant.</span></span> <span data-ttu-id="e3519-419">고객 키 암호화가 사용 되 고 모든 사이트의 모든 파일이 암호화 된 경우 _State_ 속성은 **등록** 된 값을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="e3519-419">The _State_ property returns a value of **registered** if Customer Key encryption is enabled and all files in all sites have been encrypted.</span></span> <span data-ttu-id="e3519-420">암호화가 아직 진행 중인 경우이 cmdlet은 완료 된 사이트 비율에 대 한 정보를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="e3519-420">If encryption is still in progress, this cmdlet provides information on what percentage of sites is complete.</span></span>

## <a name="related-articles"></a><span data-ttu-id="e3519-421">관련 문서</span><span class="sxs-lookup"><span data-stu-id="e3519-421">Related articles</span></span>

- [<span data-ttu-id="e3519-422">고객 키를 사용한 서비스 암호화</span><span class="sxs-lookup"><span data-stu-id="e3519-422">Service encryption with Customer Key</span></span>](customer-key-overview.md)

- [<span data-ttu-id="e3519-423">고객 키 관리</span><span class="sxs-lookup"><span data-stu-id="e3519-423">Manage Customer Key</span></span>](customer-key-manage.md)

- [<span data-ttu-id="e3519-424">고객 키 또는 가용성 키 롤 또는 회전</span><span class="sxs-lookup"><span data-stu-id="e3519-424">Roll or rotate a Customer Key or an availability key</span></span>](customer-key-availability-key-roll.md)

- [<span data-ttu-id="e3519-425">가용성 키에 대 한 자세한 정보</span><span class="sxs-lookup"><span data-stu-id="e3519-425">Learn about the availability key</span></span>](customer-key-availability-key-understand.md)

- [<span data-ttu-id="e3519-426">서비스 암호화</span><span class="sxs-lookup"><span data-stu-id="e3519-426">Service Encryption</span></span>](office-365-service-encryption.md)
