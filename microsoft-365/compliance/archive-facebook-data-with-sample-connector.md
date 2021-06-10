---
title: Facebook 데이터를 보관할 커넥터 설정
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: how-to
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection: M365-security-compliance
ms.custom: seo-marvel-apr2020
description: '& 규정 준수 센터에서 Microsoft 365 사용하여 Facebook 비즈니스 페이지에서 & 보관 데이터를 가져오는 방법을 Microsoft 365.'
ms.openlocfilehash: 616466a3af83c1558184526aa463f68c10ef9e70
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/19/2021
ms.locfileid: "50921738"
---
# <a name="set-up-a-connector-to-archive-facebook-data-preview"></a><span data-ttu-id="6bcdc-103">Facebook 데이터를 보관할 커넥터 설정(미리 보기)</span><span class="sxs-lookup"><span data-stu-id="6bcdc-103">Set up a connector to archive Facebook data (preview)</span></span>

<span data-ttu-id="6bcdc-104">Microsoft 365 규정 준수 센터의 커넥터를 사용하여 Facebook 비즈니스 페이지에서 데이터 가져오기 및 보관을 Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="6bcdc-104">Use a connector in the Microsoft 365 compliance center to import and archive data from Facebook Business pages to Microsoft 365.</span></span> <span data-ttu-id="6bcdc-105">커넥터를 설정 및 구성하고 나면 일정에 따라 Facebook 비즈니스 페이지에 연결하고 Facebook 항목의 콘텐츠를 전자 메일 메시지 형식으로 변환한 다음 해당 항목을 페이지의 사서함으로 Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="6bcdc-105">After you set up and configure the connector, it connects to the Facebook Business page (on a scheduled basis), converts the content of Facebook items to an email message format, and then imports those items to a mailbox in Microsoft 365.</span></span>

<span data-ttu-id="6bcdc-106">Facebook 데이터를 가져온 후 소송 보존, Microsoft 365 검색, In-Place 보관, 감사, 커뮤니케이션 규정 준수 및 보존 정책과 같은 Microsoft 365 준수 기능을 Facebook 데이터에 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6bcdc-106">After the Facebook data is imported, you can apply Microsoft 365 compliance features such as Litigation Hold, Content Search, In-Place Archiving, Auditing, Communication compliance, and Microsoft 365 retention policies to the Facebook data.</span></span> <span data-ttu-id="6bcdc-107">예를 들어 사서함에 소송 보존이 적용되거나 보존 정책에 할당된 경우 Facebook 데이터는 보존됩니다.</span><span class="sxs-lookup"><span data-stu-id="6bcdc-107">For example, when a mailbox is placed on Litigation Hold or assigned to a retention policy, the Facebook data is preserved.</span></span> <span data-ttu-id="6bcdc-108">콘텐츠 검색을 사용하여 타사 데이터를 검색하거나 Facebook 데이터가 저장된 사서함을 보관 센터 사례에 Advanced eDiscovery 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6bcdc-108">You can search third-party data using Content Search or associate the mailbox where the Facebook data is stored with a custodian in an Advanced eDiscovery case.</span></span> <span data-ttu-id="6bcdc-109">커넥터를 사용하여 Facebook 데이터를 가져오고 Microsoft 365 조직이 정부 및 규제 정책을 준수하는 데 도움이 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6bcdc-109">Using a connector to import and archive Facebook data in Microsoft 365 can help your organization stay compliant with government and regulatory policies.</span></span>

## <a name="prerequisites-for-setting-up-a-connector-for-facebook-business-pages"></a><span data-ttu-id="6bcdc-110">Facebook 비즈니스 페이지에 대한 커넥터를 설정하기 위한 선행 준비</span><span class="sxs-lookup"><span data-stu-id="6bcdc-110">Prerequisites for setting up a connector for Facebook Business pages</span></span>

<span data-ttu-id="6bcdc-111">조직의 Facebook 비즈니스 페이지에서 데이터를 가져오고 보관하도록 Microsoft 365 규정 준수 센터에서 커넥터를 설정하고 구성하기 전에 다음 선행 요구를 완료합니다.</span><span class="sxs-lookup"><span data-stu-id="6bcdc-111">Complete the following prerequisites before you can set up and configure a connector in the Microsoft 365 compliance center to import and archive data from your organization's Facebook Business pages.</span></span> 

- <span data-ttu-id="6bcdc-112">조직의 비즈니스 페이지에 대한 Facebook 계정이 필요합니다(커넥터를 설정할 때 이 계정에 로그인해야 합니다).</span><span class="sxs-lookup"><span data-stu-id="6bcdc-112">You need a Facebook account for your organization's business pages (you need to sign in to this account when setting up the connector).</span></span> <span data-ttu-id="6bcdc-113">현재 Facebook 비즈니스 페이지에서만 데이터를 보관할 수 있습니다. 개별 Facebook 프로필에서 데이터를 보관할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="6bcdc-113">Currently, you can only archive data from Facebook Business pages; you can't archive data from individual Facebook profiles.</span></span>

- <span data-ttu-id="6bcdc-114">조직에 유효한 Azure 구독이 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6bcdc-114">Your organization must have a valid Azure subscription.</span></span> <span data-ttu-id="6bcdc-115">기존 Azure 구독이 없는 경우 다음 옵션 중 하나를 등록할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6bcdc-115">If you don't have an existing Azure subscription, you can sign up for one of these options:</span></span>

    - [<span data-ttu-id="6bcdc-116">1년 무료 Azure 구독에 등록</span><span class="sxs-lookup"><span data-stu-id="6bcdc-116">Sign up for a free one year Azure subscription</span></span>](https://azure.microsoft.com/free)

    - [<span data-ttu-id="6bcdc-117">Pay-As-You-Go Azure 구독에 등록</span><span class="sxs-lookup"><span data-stu-id="6bcdc-117">Sign up for a Pay-As-You-Go Azure subscription</span></span>](https://azure.microsoft.com/pricing/purchase-options/pay-as-you-go/)

    > [!NOTE]
    > <span data-ttu-id="6bcdc-118">Azure Active Directory [](use-your-free-azure-ad-subscription-in-office-365.md) 구독에 포함된 무료 Microsoft 365 구독은 보안 및 준수 센터의 커넥터를 & 않습니다.</span><span class="sxs-lookup"><span data-stu-id="6bcdc-118">The [free Azure Active Directory subscription](use-your-free-azure-ad-subscription-in-office-365.md) that's included with your Microsoft 365 subscription doesn't support the connectors in the Security & Compliance Center.</span></span>

- <span data-ttu-id="6bcdc-119">Facebook 비즈니스 페이지의 커넥터는 하루 동안 총 200,000개 항목을 가져올 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6bcdc-119">The connector for Facebook Business pages can import a total of 200,000 items in a single day.</span></span> <span data-ttu-id="6bcdc-120">하루 200,000개가 넘는 Facebook 비즈니스 항목이 있는 경우 해당 항목 중 어떤 항목도 가져오지 Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="6bcdc-120">If there are more than 200,000 Facebook Business items in a day, none of those items will be imported to Microsoft 365.</span></span>

- <span data-ttu-id="6bcdc-121">Microsoft 365 준수 센터(5단계)에서 사용자 지정 커넥터를 설정하는 사용자에게 사서함 가져오기 내보내기 역할이 Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="6bcdc-121">The user who sets up the custom connector in the Microsoft 365 compliance center (in Step 5) must be assigned the Mailbox Import Export role in Exchange Online.</span></span> <span data-ttu-id="6bcdc-122">기본적으로이 역할은 Exchange Online의 어떤 역할 그룹에도 할당되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="6bcdc-122">By default, this role isn't assigned to any role group in Exchange Online.</span></span> <span data-ttu-id="6bcdc-123">사서함 가져오기 내보내기 역할을 조직의 조직 관리 역할 그룹에 추가할 수 Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="6bcdc-123">You can add the Mailbox Import Export role to the Organization Management role group in Exchange Online.</span></span> <span data-ttu-id="6bcdc-124">또는 역할 그룹을 만들고 사서함 가져오기 내보내기 역할을 할당한 다음 해당 사용자를 구성원으로 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6bcdc-124">Or you can create a role group, assign the Mailbox Import Export role, and then add the appropriate users as members.</span></span> <span data-ttu-id="6bcdc-125">자세한 내용은 "역할 [](/Exchange/permissions-exo/role-groups#create-role-groups) 그룹에서 [](/Exchange/permissions-exo/role-groups#modify-role-groups) 역할 그룹 관리" 문서의 역할 그룹 만들기 또는 역할 그룹 수정 섹션을 Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="6bcdc-125">For more information, see the  [Create role groups](/Exchange/permissions-exo/role-groups#create-role-groups) or [Modify role groups](/Exchange/permissions-exo/role-groups#modify-role-groups) sections in the article "Manage role groups in Exchange Online".</span></span>

## <a name="step-1-create-an-app-in-azure-active-directory"></a><span data-ttu-id="6bcdc-126">1단계: 앱에서 앱 Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="6bcdc-126">Step 1: Create an app in Azure Active Directory</span></span>

<span data-ttu-id="6bcdc-127">첫 번째 단계는 AAD(Azure Active Directory 등록하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="6bcdc-127">The first step is to register a new app in Azure Active Directory (AAD).</span></span> <span data-ttu-id="6bcdc-128">이 앱은 Facebook 커넥터의 4단계 및 5단계에서 구현하는 웹 앱 리소스에 해당합니다.</span><span class="sxs-lookup"><span data-stu-id="6bcdc-128">This app corresponds to the web app resource that you implement in Step 4 and Step 5 for the Facebook connector.</span></span> 

<span data-ttu-id="6bcdc-129">단계별 지침은 에서 [앱 만들기를 Azure Active Directory.](deploy-facebook-connector.md#step-1-create-an-app-in-azure-active-directory)</span><span class="sxs-lookup"><span data-stu-id="6bcdc-129">For step-by-step instructions, see [Create an app in Azure Active Directory](deploy-facebook-connector.md#step-1-create-an-app-in-azure-active-directory).</span></span>

<span data-ttu-id="6bcdc-130">이 단계를 완료하는 동안(이전 단계별 지침을 사용하여) 텍스트 파일에 다음 정보를 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="6bcdc-130">During the completion of this step (by using the previous step-by-step instructions), you'll save the following information to a text file.</span></span> <span data-ttu-id="6bcdc-131">이러한 값은 배포 프로세스의 이후 단계에서 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="6bcdc-131">These values are used in later steps in the deployment process.</span></span>

- <span data-ttu-id="6bcdc-132">AAD 응용 프로그램 ID</span><span class="sxs-lookup"><span data-stu-id="6bcdc-132">AAD application ID</span></span>

- <span data-ttu-id="6bcdc-133">AAD 응용 프로그램 비밀</span><span class="sxs-lookup"><span data-stu-id="6bcdc-133">AAD application secret</span></span>

- <span data-ttu-id="6bcdc-134">테넌트 ID</span><span class="sxs-lookup"><span data-stu-id="6bcdc-134">Tenant Id</span></span>

## <a name="step-2-deploy-the-connector-web-service-from-github-to-your-azure-account"></a><span data-ttu-id="6bcdc-135">2단계: Azure 계정으로 GitHub 커넥터 웹 서비스 배포</span><span class="sxs-lookup"><span data-stu-id="6bcdc-135">Step 2: Deploy the connector web service from GitHub to your Azure account</span></span>

<span data-ttu-id="6bcdc-136">다음 단계는 Facebook API를 사용하여 Facebook 계정에 연결하고 데이터를 추출하여 Facebook 비즈니스 페이지 커넥터 앱에 대한 소스 코드를 배포하는 Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="6bcdc-136">The next step is to deploy the source code for the Facebook Business pages connector app that will use the Facebook API to connect to your Facebook account and extract data so you can import it to Microsoft 365.</span></span> <span data-ttu-id="6bcdc-137">조직에 배포하는 Facebook 커넥터는 Facebook 비즈니스 페이지의 항목을 이 단계에서 만든 Azure Storage 위치로 업로드합니다.</span><span class="sxs-lookup"><span data-stu-id="6bcdc-137">The Facebook connector that you deploy for your organization will upload the items from your Facebook Business pages to the Azure Storage location that is created in this step.</span></span> <span data-ttu-id="6bcdc-138">Microsoft 365 규정 준수 센터(5단계)에서 Facebook 비즈니스 페이지 커넥터를 만든 후 가져오기 서비스는 Facebook 비즈니스 페이지 데이터를 Azure Storage 위치에서 Microsoft 365 조직의 사서함으로 복사합니다.</span><span class="sxs-lookup"><span data-stu-id="6bcdc-138">After you create a Facebook business pages connector in the Microsoft 365 compliance center (in Step 5), the Import service will copy the Facebook business pages data from the Azure Storage location to a mailbox in your Microsoft 365 organization.</span></span> <span data-ttu-id="6bcdc-139">[Prerequisites](#prerequisites-for-setting-up-a-connector-for-facebook-business-pages) 섹션에서 설명한 것 처럼 계정 계정을 만들 수 있는 유효한 Azure 구독이 Azure Storage 합니다.</span><span class="sxs-lookup"><span data-stu-id="6bcdc-139">As previous explained in the [Prerequisites](#prerequisites-for-setting-up-a-connector-for-facebook-business-pages) section, you must have a valid Azure subscription to create an Azure Storage account.</span></span>

<span data-ttu-id="6bcdc-140">단계별 지침은 Azure 계정으로 GitHub 커넥터 [웹 서비스 배포를 참조하세요.](deploy-facebook-connector.md#step-2-deploy-the-connector-web-service-from-github-to-your-azure-account)</span><span class="sxs-lookup"><span data-stu-id="6bcdc-140">For step-by-step instructions, see [Deploy the connector web service from GitHub to your Azure account](deploy-facebook-connector.md#step-2-deploy-the-connector-web-service-from-github-to-your-azure-account).</span></span>

<span data-ttu-id="6bcdc-141">이 단계를 완료하는 단계별 지침에서는 다음 정보를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="6bcdc-141">In the step-by-step instructions to complete this step, you'll provide the following information:</span></span>

- <span data-ttu-id="6bcdc-142">APISecretKey: 이 단계를 완료하는 동안 이 비밀을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="6bcdc-142">APISecretKey: You create this secret during the completion of this step.</span></span> <span data-ttu-id="6bcdc-143">5단계에서 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="6bcdc-143">It's used in Step 5.</span></span>

- <span data-ttu-id="6bcdc-144">TenantId: 1단계에서 Facebook 커넥터 앱을 Microsoft 365 후 복사한 Azure Active Directory 조직의 테넌트 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="6bcdc-144">TenantId: The tenant ID of your Microsoft 365 organization that you copied after creating the Facebook connector app in Azure Active Directory in Step 1.</span></span>

<span data-ttu-id="6bcdc-145">이 단계를 완료한 후 Azure 앱 서비스 URL(예: 을 복사해야 https://fbconnector.azurewebsites.net) 합니다.</span><span class="sxs-lookup"><span data-stu-id="6bcdc-145">After completing this step, be sure to copy the Azure app service URL (for example, https://fbconnector.azurewebsites.net).</span></span> <span data-ttu-id="6bcdc-146">이 URL을 사용하여 3단계, 4단계 및 5단계를 완료해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6bcdc-146">You need to use this URL to complete Step 3, Step 4, and Step 5).</span></span>

## <a name="step-3-register-the-web-app-on-facebook"></a><span data-ttu-id="6bcdc-147">3단계: Facebook에서 웹앱 등록</span><span class="sxs-lookup"><span data-stu-id="6bcdc-147">Step 3: Register the web app on Facebook</span></span>

<span data-ttu-id="6bcdc-148">다음 단계는 Facebook에서 새 앱을 만들고 구성하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="6bcdc-148">The next step is to create and configure a new app on Facebook.</span></span> <span data-ttu-id="6bcdc-149">5단계에서 만든 Facebook 비즈니스 페이지 커넥터는 Facebook 웹앱을 사용하여 Facebook API와 상호 작용하여 조직의 Facebook 비즈니스 페이지에서 데이터를 얻습니다.</span><span class="sxs-lookup"><span data-stu-id="6bcdc-149">The Facebook business pages connector that you create in Step 5 uses the Facebook web app to interact with the Facebook API to obtain data from your organization's Facebook Business pages.</span></span>

<span data-ttu-id="6bcdc-150">단계별 지침은 Facebook 앱 [등록을 참조하세요.](deploy-facebook-connector.md#step-3-register-the-facebook-app)</span><span class="sxs-lookup"><span data-stu-id="6bcdc-150">For step-by-step instructions, see [Register the Facebook app](deploy-facebook-connector.md#step-3-register-the-facebook-app).</span></span>

<span data-ttu-id="6bcdc-151">이 단계를 완료하는 동안(단계별 지침에 따라) 텍스트 파일에 다음 정보를 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="6bcdc-151">During the completion of this step (by following the step-by-step instructions), you save the following information to a text file.</span></span> <span data-ttu-id="6bcdc-152">이러한 값은 4단계에서 Facebook 커넥터 앱을 구성하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="6bcdc-152">These values are used to configure the Facebook connector app in Step 4.</span></span>

- <span data-ttu-id="6bcdc-153">Facebook 응용 프로그램 ID</span><span class="sxs-lookup"><span data-stu-id="6bcdc-153">Facebook application ID</span></span>

- <span data-ttu-id="6bcdc-154">Facebook 응용 프로그램 비밀</span><span class="sxs-lookup"><span data-stu-id="6bcdc-154">Facebook application secret</span></span>

- <span data-ttu-id="6bcdc-155">Facebook webhook에서 토큰 확인</span><span class="sxs-lookup"><span data-stu-id="6bcdc-155">Facebook webhooks verify token</span></span>

## <a name="step-4-configure-the-facebook-connector-app"></a><span data-ttu-id="6bcdc-156">4단계: Facebook 커넥터 앱 구성</span><span class="sxs-lookup"><span data-stu-id="6bcdc-156">Step 4: Configure the Facebook connector app</span></span>

<span data-ttu-id="6bcdc-157">다음 단계는 1단계에서 Azure Web App 리소스를 만들 때 업로드한 Facebook 커넥터 앱에 구성 설정을 추가하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="6bcdc-157">The next step is to add configuration settings to the Facebook connector app that you uploaded when you created the Azure web app resource in Step 1.</span></span> <span data-ttu-id="6bcdc-158">이 작업을 위해 커넥터 앱의 홈 페이지로 이동하여 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="6bcdc-158">You do this by going to the home page of your connector app and configuring it.</span></span>

<span data-ttu-id="6bcdc-159">단계별 지침은 Facebook 커넥터 앱 [구성을 참조하세요.](archive-facebook-data-with-sample-connector.md#step-4-configure-the-facebook-connector-app)</span><span class="sxs-lookup"><span data-stu-id="6bcdc-159">For step-by-step instructions, see [Configure the Facebook connector app](archive-facebook-data-with-sample-connector.md#step-4-configure-the-facebook-connector-app).</span></span>

<span data-ttu-id="6bcdc-160">이 단계를 완료하는 동안(단계별 지침에 따라) 이전 단계를 완료한 후 텍스트 파일에 복사한 다음 정보를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="6bcdc-160">During the completion of this step (by following the step-by-step instructions), you provide the following information (that you've copied to a text file after completing the previous steps):</span></span>

- <span data-ttu-id="6bcdc-161">Facebook 응용 프로그램 ID(3단계에서 획득)</span><span class="sxs-lookup"><span data-stu-id="6bcdc-161">Facebook application ID (obtained in Step 3)</span></span>

- <span data-ttu-id="6bcdc-162">Facebook 응용 프로그램 비밀(3단계에서 획득)</span><span class="sxs-lookup"><span data-stu-id="6bcdc-162">Facebook application secret (obtained in Step 3)</span></span>

- <span data-ttu-id="6bcdc-163">Facebook webhook은 토큰 확인(3단계에서 획득)</span><span class="sxs-lookup"><span data-stu-id="6bcdc-163">Facebook webhooks verify token (obtained in Step 3)</span></span>

- <span data-ttu-id="6bcdc-164">Azure Active Directory 응용 프로그램 ID(1단계에서 획득한 AAD 응용 프로그램 ID)</span><span class="sxs-lookup"><span data-stu-id="6bcdc-164">Azure Active Directory application ID (the AAD application ID obtained in Step 1)</span></span>

- <span data-ttu-id="6bcdc-165">Azure Active Directory 응용 프로그램 비밀(1단계에서 얻은 AAD 응용 프로그램 비밀)</span><span class="sxs-lookup"><span data-stu-id="6bcdc-165">Azure Active Directory application secret (the AAD application secret obtained in Step 1)</span></span>

## <a name="step-5-set-up-a-facebook-business-pages-connector-in-the-microsoft-365-compliance-center"></a><span data-ttu-id="6bcdc-166">5단계: Microsoft 365 규정 준수 센터에서 Facebook 비즈니스 페이지 커넥터 설정</span><span class="sxs-lookup"><span data-stu-id="6bcdc-166">Step 5: Set up a Facebook Business pages connector in the Microsoft 365 compliance center</span></span>

<span data-ttu-id="6bcdc-167">마지막 단계는 Facebook 비즈니스 페이지에서 지정된 사서함으로 데이터를 가져오는 Microsoft 365 준수 센터에서 커넥터를 설정하는 Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="6bcdc-167">The final step is to set up the connector in the Microsoft 365 compliance center that will import data from your Facebook Business pages to a specified mailbox in Microsoft 365.</span></span> <span data-ttu-id="6bcdc-168">이 단계를 완료하고 나면 Microsoft 365 가져오기 서비스가 Facebook 비즈니스 페이지에서 페이지로 데이터를 가져오기 Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="6bcdc-168">After you complete this step, the Microsoft 365 Import service will start importing data from your Facebook Business pages to Microsoft 365.</span></span>

<span data-ttu-id="6bcdc-169">단계별 지침은 [5단계:](deploy-facebook-connector.md#step-5-set-up-a-facebook-connector-in-the-microsoft-365-compliance-center)규정 준수 센터에서 Facebook 커넥터 Microsoft 365 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="6bcdc-169">For step-by-step instructions, see [Step 5: Set up a Facebook connector in the Microsoft 365 compliance center](deploy-facebook-connector.md#step-5-set-up-a-facebook-connector-in-the-microsoft-365-compliance-center).</span></span> 

<span data-ttu-id="6bcdc-170">이 단계를 완료하는 동안(단계별 지침에 따라) 다음 정보를 제공합니다(단계를 완료한 후 텍스트 파일에 복사한 경우).</span><span class="sxs-lookup"><span data-stu-id="6bcdc-170">During the completion of this step (by following the step-by-step instructions), you provide the following information (that you've copied to a text file after completing the steps).</span></span>

- <span data-ttu-id="6bcdc-171">AAD 응용 프로그램 ID(1단계에서 획득)</span><span class="sxs-lookup"><span data-stu-id="6bcdc-171">AAD application ID (obtained in Step 1)</span></span>

- <span data-ttu-id="6bcdc-172">Azure 앱 서비스 URL(예: 1단계에서 획득) https://fbconnector.azurewebsites.net)</span><span class="sxs-lookup"><span data-stu-id="6bcdc-172">Azure app service URL (obtained in Step 1; for example, https://fbconnector.azurewebsites.net)</span></span>

- <span data-ttu-id="6bcdc-173">APISecretKey(2단계에서 만든)</span><span class="sxs-lookup"><span data-stu-id="6bcdc-173">APISecretKey (that you created in Step 2)</span></span>