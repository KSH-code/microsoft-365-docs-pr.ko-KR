---
title: Twitter 데이터를 보관할 커넥터 설정
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
description: 관리자가 기본 커넥터를 설정하고 사용하여 Twitter 데이터를 사이트로 가져오는 방법을 Microsoft 365.
ms.openlocfilehash: 277af8ea7367936c4c9528a8ca50ccd678745bf6
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/19/2021
ms.locfileid: "50922260"
---
# <a name="set-up-a-connector-to-archive-twitter-data-preview"></a><span data-ttu-id="86b5e-103">Twitter 데이터를 보관할 커넥터 설정(미리 보기)</span><span class="sxs-lookup"><span data-stu-id="86b5e-103">Set up a connector to archive Twitter data (preview)</span></span>

<span data-ttu-id="86b5e-104">규정 준수 센터의 커넥터를 Microsoft 365 Twitter에서 사용자로 데이터를 가져오고 Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="86b5e-104">Use a connector in the Microsoft 365 compliance center to import and archive data from Twitter to Microsoft 365.</span></span> <span data-ttu-id="86b5e-105">커넥터를 설정 및 구성한 후 일정에 따라 조직의 Twitter 계정에 연결하고 항목의 콘텐츠를 전자 메일 메시지 형식으로 변환한 다음 해당 항목을 조직의 사서함으로 Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="86b5e-105">After you set up and configure the connector, it connects to your organization's Twitter account (on a scheduled basis), converts the content of an item to an email message format, and then imports those items to a mailbox in Microsoft 365.</span></span>

<span data-ttu-id="86b5e-106">Twitter 데이터를 가져온 후 소송 보존, Microsoft 365 검색, In-Place 보관, 감사 및 보존 정책과 같은 Microsoft 365 준수 기능을 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="86b5e-106">After the Twitter data is imported, you can apply Microsoft 365 compliance features such as Litigation Hold, Content Search, In-Place Archiving, Auditing, and Microsoft 365 retention policies to the Twitter data.</span></span> <span data-ttu-id="86b5e-107">예를 들어 사서함에 소송 보존이 적용되거나 보존 정책에 할당된 경우 Twitter 데이터는 보존됩니다.</span><span class="sxs-lookup"><span data-stu-id="86b5e-107">For example, when a mailbox is placed on Litigation Hold or assigned to a retention policy, the Twitter data is preserved.</span></span> <span data-ttu-id="86b5e-108">콘텐츠 검색을 사용하여 타사 데이터를 검색하거나 Twitter 데이터가 저장된 사서함을 보관 센터 사례에 Advanced eDiscovery 있습니다.</span><span class="sxs-lookup"><span data-stu-id="86b5e-108">You can search third-party data using Content Search or associate the mailbox where the Twitter data is stored with a custodian in an Advanced eDiscovery case.</span></span> <span data-ttu-id="86b5e-109">커넥터를 사용하여 Twitter 데이터를 가져오고 보관하는 Microsoft 365 조직이 정부 및 규제 정책을 준수하는 데 도움이 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="86b5e-109">Using a connector to import and archive Twitter data in Microsoft 365 can help your organization stay compliant with government and regulatory policies.</span></span>

<span data-ttu-id="86b5e-110">Twitter 데이터를 가져온 후 소송 보존, 콘텐츠 Microsoft 365, In-Place 보관, 감사, 통신 준수 및 보존 정책과 같은 Microsoft 365 준수 기능을 사서함에 저장된 데이터에 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="86b5e-110">After Twitter data is imported, you can apply Microsoft 365 compliance features such as Litigation Hold, Content Search, In-Place Archiving, Auditing, Communication compliance, and Microsoft 365 retention policies to the data stored in the mailbox.</span></span> <span data-ttu-id="86b5e-111">예를 들어 콘텐츠 검색을 사용하여 Twitter 데이터를 검색하거나 데이터가 저장된 사서함을 보관된 사례에 Advanced eDiscovery 있습니다.</span><span class="sxs-lookup"><span data-stu-id="86b5e-111">For example, you can search Twitter data using Content Search or associate the mailbox where the data is stored with a custodian in an Advanced eDiscovery case.</span></span> <span data-ttu-id="86b5e-112">커넥터를 사용하여 Twitter 데이터를 가져오고 보관하는 Microsoft 365 조직이 정부 및 규제 정책을 준수하는 데 도움이 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="86b5e-112">Using a connector to import and archive Twitter data in Microsoft 365 can help your organization stay compliant with government and regulatory policies.</span></span>

## <a name="before-you-set-up-a-connector"></a><span data-ttu-id="86b5e-113">커넥터를 설정하기 전에</span><span class="sxs-lookup"><span data-stu-id="86b5e-113">Before you set up a connector</span></span>

<span data-ttu-id="86b5e-114">조직의 Twitter 계정에서 데이터를 가져오고 보관하기 위해 Microsoft 365 규정 준수 센터에서 커넥터를 설정하고 구성하려면 먼저 다음 선행 요구를 완료합니다.</span><span class="sxs-lookup"><span data-stu-id="86b5e-114">Complete the following prerequisites before you can set up and configure a connector in the Microsoft 365 compliance center to import and archive data from your organization's Twitter account.</span></span>

- <span data-ttu-id="86b5e-115">조직에 대한 Twitter 계정이 필요합니다. 커넥터를 설정할 때 이 계정에 로그인해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="86b5e-115">You need a Twitter account for your organization; you need to sign in to this account when setting up the connector.</span></span>

- <span data-ttu-id="86b5e-116">조직에 유효한 Azure 구독이 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="86b5e-116">Your organization must have a valid Azure subscription.</span></span> <span data-ttu-id="86b5e-117">기존 Azure 구독이 없는 경우 다음 옵션 중 하나를 등록할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="86b5e-117">If you don't have an existing Azure subscription, you can sign up for one of these options:</span></span>

    - [<span data-ttu-id="86b5e-118">1년 무료 Azure 구독에 등록</span><span class="sxs-lookup"><span data-stu-id="86b5e-118">Sign up for a free one year Azure subscription</span></span>](https://azure.microsoft.com/free) 

    - [<span data-ttu-id="86b5e-119">Pay-As-You-Go Azure 구독에 등록</span><span class="sxs-lookup"><span data-stu-id="86b5e-119">Sign up for a Pay-As-You-Go Azure subscription</span></span>](https://azure.microsoft.com/pricing/purchase-options/pay-as-you-go/)

    > [!NOTE]
    > <span data-ttu-id="86b5e-120">Azure Active Directory [](use-your-free-azure-ad-subscription-in-office-365.md) 구독에 포함된 무료 Microsoft 365 구독은 보안 및 준수 센터의 커넥터를 & 않습니다.</span><span class="sxs-lookup"><span data-stu-id="86b5e-120">The [free Azure Active Directory subscription](use-your-free-azure-ad-subscription-in-office-365.md) that's included with your Microsoft 365 subscription doesn't support the connectors in the Security & Compliance Center.</span></span>

- <span data-ttu-id="86b5e-121">Twitter 커넥터는 하루 총 200,000개 항목을 가져올 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="86b5e-121">The Twitter connector can import a total of 200,000 items in a single day.</span></span> <span data-ttu-id="86b5e-122">하루 200,000개가 넘는 Twitter 항목이 있는 경우 해당 항목을 가져오지 Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="86b5e-122">If there are more than 200,000 Twitter items in a day, none of those items will be imported to Microsoft 365.</span></span>

- <span data-ttu-id="86b5e-123">Microsoft 365 규정 준수 센터(5단계)에서 Twitter 커넥터를 설정하는 사용자에게 사서함 가져오기 내보내기 역할이 Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="86b5e-123">The user who sets up the Twitter connector in the Microsoft 365 compliance center (in Step 5) must be assigned the Mailbox Import Export role in Exchange Online.</span></span> <span data-ttu-id="86b5e-124">기본적으로이 역할은 Exchange Online의 어떤 역할 그룹에도 할당되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="86b5e-124">By default, this role isn't assigned to any role group in Exchange Online.</span></span> <span data-ttu-id="86b5e-125">사서함 가져오기 내보내기 역할을 조직의 조직 관리 역할 그룹에 추가할 수 Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="86b5e-125">You can add the Mailbox Import Export role to the Organization Management role group in Exchange Online.</span></span> <span data-ttu-id="86b5e-126">또는 역할 그룹을 만들고 사서함 가져오기 내보내기 역할을 할당한 다음 해당 사용자를 구성원으로 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="86b5e-126">Or you can create a role group, assign the Mailbox Import Export role, and then add the appropriate users as members.</span></span> <span data-ttu-id="86b5e-127">자세한 내용은 "역할 [](/Exchange/permissions-exo/role-groups#create-role-groups) 그룹에서 [](/Exchange/permissions-exo/role-groups#modify-role-groups) 역할 그룹 관리" 문서의 역할 그룹 만들기 또는 역할 그룹 수정 섹션을 Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="86b5e-127">For more information, see the  [Create role groups](/Exchange/permissions-exo/role-groups#create-role-groups) or [Modify role groups](/Exchange/permissions-exo/role-groups#modify-role-groups) sections in the article "Manage role groups in Exchange Online".</span></span>

## <a name="step-1-create-an-app-in-azure-active-directory"></a><span data-ttu-id="86b5e-128">1단계: 앱에서 앱 Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="86b5e-128">Step 1: Create an app in Azure Active Directory</span></span>

<span data-ttu-id="86b5e-129">첫 번째 단계는 AAD(Azure Active Directory 등록하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="86b5e-129">The first step is to register a new app in Azure Active Directory (AAD).</span></span> <span data-ttu-id="86b5e-130">이 앱은 Twitter 커넥터에 대해 2단계에서 구현한 웹 앱 리소스에 해당합니다.</span><span class="sxs-lookup"><span data-stu-id="86b5e-130">This app corresponds to the web app resource that you implement in Step 2 for the Twitter connector.</span></span>

<span data-ttu-id="86b5e-131">단계별 지침은 에서 [앱 만들기를 Azure Active Directory.](deploy-twitter-connector.md#step-1-create-an-app-in-azure-active-directory)</span><span class="sxs-lookup"><span data-stu-id="86b5e-131">For step-by-step instructions, see [Create an app in Azure Active Directory](deploy-twitter-connector.md#step-1-create-an-app-in-azure-active-directory).</span></span>

<span data-ttu-id="86b5e-132">이 단계를 완료하는 동안(단계별 지침에 따라) 텍스트 파일에 다음 정보를 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="86b5e-132">During the completion of this step (by following the step-by-step instructions), you'll save the following information to a text file.</span></span> <span data-ttu-id="86b5e-133">이러한 값은 배포 프로세스의 이후 단계에서 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="86b5e-133">These values will be used in later steps in the deployment process.</span></span>

- <span data-ttu-id="86b5e-134">AAD 응용 프로그램 ID</span><span class="sxs-lookup"><span data-stu-id="86b5e-134">AAD application ID</span></span>

- <span data-ttu-id="86b5e-135">AAD 응용 프로그램 비밀</span><span class="sxs-lookup"><span data-stu-id="86b5e-135">AAD application secret</span></span>

- <span data-ttu-id="86b5e-136">테넌트 ID</span><span class="sxs-lookup"><span data-stu-id="86b5e-136">Tenant Id</span></span>

## <a name="step-2-deploy-connector-web-service-from-github-repository-to-your-azure-account"></a><span data-ttu-id="86b5e-137">2단계: GitHub 리포지토리에서 Azure 계정으로 커넥터 웹 서비스 배포</span><span class="sxs-lookup"><span data-stu-id="86b5e-137">Step 2: Deploy connector web service from GitHub repository to your Azure account</span></span>

<span data-ttu-id="86b5e-138">다음 단계는 Twitter API를 사용하여 Twitter 계정에 연결하고 데이터를 추출하여 Twitter로 가져올 수 있도록 Twitter 커넥터 앱에 대한 소스 코드를 Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="86b5e-138">The next step is to deploy the source code for the Twitter connector app that will use Twitter API to connect to your Twitter account and extract data so you can import it to Microsoft 365.</span></span> <span data-ttu-id="86b5e-139">조직에 배포하는 Twitter 커넥터는 조직의 Twitter 계정의 항목을 이 단계에서 만든 Azure Storage 위치로 업로드합니다.</span><span class="sxs-lookup"><span data-stu-id="86b5e-139">The Twitter connector that you deploy for your organization will upload the items from your organization's Twitter account to the Azure Storage location that is created in this step.</span></span> <span data-ttu-id="86b5e-140">Microsoft 365 준수 센터(5단계)에서 Twitter 커넥터를 만든 후 Microsoft 365 가져오기 서비스는 Azure Storage 위치에서 사서함으로 Twitter 데이터를 Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="86b5e-140">After you create a Twitter connector in the Microsoft 365 compliance center (in Step 5), the Microsoft 365 Import service will copy the Twitter data from the Azure Storage location to a mailbox in Microsoft 365.</span></span> <span data-ttu-id="86b5e-141">커넥터를 설정하기 [](#before-you-set-up-a-connector) 전에 섹션에서 설명한 것 처럼 커넥터 계정을 만들 수 있는 유효한 Azure 구독이 Azure Storage 합니다.</span><span class="sxs-lookup"><span data-stu-id="86b5e-141">As previous explained in the [Before you set up a connector](#before-you-set-up-a-connector) section, you must have a valid Azure subscription to create an Azure Storage account.</span></span>

<span data-ttu-id="86b5e-142">Twitter 커넥터 앱의 소스 코드를 배포하는 경우:</span><span class="sxs-lookup"><span data-stu-id="86b5e-142">To deploy the source code for the Twitter connector app:</span></span>

1. <span data-ttu-id="86b5e-143">이 [사이트로 GitHub 로 이동하세요.](https://github.com/microsoft/m365-sample-twitter-connector-csharp-aspnet)</span><span class="sxs-lookup"><span data-stu-id="86b5e-143">Go to [this GitHub site](https://github.com/microsoft/m365-sample-twitter-connector-csharp-aspnet).</span></span>

2. <span data-ttu-id="86b5e-144">**Azure에 배포를 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="86b5e-144">Click **Deploy to Azure**.</span></span>

<span data-ttu-id="86b5e-145">단계별 지침은 Azure 계정으로 GitHub 커넥터 [웹 서비스 배포를 참조하세요.](deploy-twitter-connector.md#step-2-deploy-the-connector-web-service-from-github-to-your-azure-account)</span><span class="sxs-lookup"><span data-stu-id="86b5e-145">For step-by-step instructions, see [Deploy the connector web service from GitHub to your Azure account](deploy-twitter-connector.md#step-2-deploy-the-connector-web-service-from-github-to-your-azure-account).</span></span>

<span data-ttu-id="86b5e-146">이 단계를 완료하기 위해 단계별 지침을 따르는 동안 다음 정보를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="86b5e-146">While you follow the step-by-step instructions to complete this step, you provide the following information</span></span>

- <span data-ttu-id="86b5e-147">APISecretKey: 이 단계를 완료하는 동안 이 비밀을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="86b5e-147">APISecretKey: You create this secret during the completion of this step.</span></span> <span data-ttu-id="86b5e-148">5단계에서 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="86b5e-148">It's used in Step 5.</span></span>

- <span data-ttu-id="86b5e-149">tenantId: 1단계에서 twitter 앱을 Microsoft 365 후 복사한 Azure Active Directory 조직의 테넌트 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="86b5e-149">tenantId: The tenant ID of your Microsoft 365 organization that you copied after creating the Twitter app in Azure Active Directory in Step 1.</span></span>

<span data-ttu-id="86b5e-150">이 단계를 완료한 후 앱 서비스 URL(예: )을 복사해야 `https://twitterconnector.azurewebsites.net` 합니다.</span><span class="sxs-lookup"><span data-stu-id="86b5e-150">After completing this step, be sure to copy the app Service URL (for example, `https://twitterconnector.azurewebsites.net`).</span></span> <span data-ttu-id="86b5e-151">이 URL을 사용하여 3단계, 4단계 및 5단계를 완료해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="86b5e-151">You need to use this URL to complete Step 3, Step 4, and Step 5).</span></span>

## <a name="step-3-create-developer-app-on-twitter"></a><span data-ttu-id="86b5e-152">3단계: Twitter에서 개발자 앱 만들기</span><span class="sxs-lookup"><span data-stu-id="86b5e-152">Step 3: Create developer app on Twitter</span></span>

<span data-ttu-id="86b5e-153">다음 단계는 Twitter에서 개발자 앱을 만들고 구성하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="86b5e-153">The next step is to create and configure a developer app on Twitter.</span></span> <span data-ttu-id="86b5e-154">7단계에서 만든 사용자 지정 커넥터는 Twitter 앱을 사용하여 Twitter API와 상호 작용하여 조직의 Twitter 계정에서 데이터를 얻습니다.</span><span class="sxs-lookup"><span data-stu-id="86b5e-154">The custom connector that you create in Step 7 uses the Twitter app to interact with the Twitter API to obtain data from your organization's Twitter account.</span></span>

<span data-ttu-id="86b5e-155">단계별 지침은 Twitter 앱 [만들기를 참조하세요.](deploy-twitter-connector.md#step-3-create-the-twitter-app)</span><span class="sxs-lookup"><span data-stu-id="86b5e-155">For step-by-step instructions, see [Create the Twitter app](deploy-twitter-connector.md#step-3-create-the-twitter-app).</span></span>

<span data-ttu-id="86b5e-156">이 단계를 완료하는 동안(단계별 지침에 따라) 텍스트 파일에 다음 정보를 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="86b5e-156">During the completion of this step (by following the step-by-step instructions), you save the following information to a text file.</span></span> <span data-ttu-id="86b5e-157">이러한 값은 4단계에서 Twitter 커넥터 앱을 구성하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="86b5e-157">These values will be used to configure the Twitter connector app in Step 4.</span></span>

- <span data-ttu-id="86b5e-158">Twitter API 키</span><span class="sxs-lookup"><span data-stu-id="86b5e-158">Twitter API Key</span></span>

- <span data-ttu-id="86b5e-159">Twitter API 비밀 키</span><span class="sxs-lookup"><span data-stu-id="86b5e-159">Twitter API Secret Key</span></span>

- <span data-ttu-id="86b5e-160">Twitter 액세스 토큰</span><span class="sxs-lookup"><span data-stu-id="86b5e-160">Twitter Access Token</span></span>

- <span data-ttu-id="86b5e-161">Twitter 액세스 토큰 비밀</span><span class="sxs-lookup"><span data-stu-id="86b5e-161">Twitter Access Token Secret</span></span>

## <a name="step-4-configure-the-twitter-connector-app"></a><span data-ttu-id="86b5e-162">4단계: Twitter 커넥터 앱 구성</span><span class="sxs-lookup"><span data-stu-id="86b5e-162">Step 4: Configure the Twitter connector app</span></span>

<span data-ttu-id="86b5e-163">다음 단계는 2단계에서 배포한 Twitter 커넥터 앱에 구성 설정을 추가하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="86b5e-163">The next step is to add configurations settings to the Twitter connector app that you deployed in Step 2.</span></span> <span data-ttu-id="86b5e-164">이 작업을 위해 커넥터 앱의 홈 페이지로 이동하여 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="86b5e-164">You do this by going to the home page of your connector app and configuring it.</span></span>

<span data-ttu-id="86b5e-165">단계별 지침은 커넥터 웹앱 [구성을 참조하세요.](deploy-twitter-connector.md#step-4-configure-the-connector-web-app)</span><span class="sxs-lookup"><span data-stu-id="86b5e-165">For step-by-step instructions, see [Configure the connector web app](deploy-twitter-connector.md#step-4-configure-the-connector-web-app).</span></span>

<span data-ttu-id="86b5e-166">이 단계를 완료하는 동안(단계별 지침에 따라) 이전 단계를 완료한 후 텍스트 파일에 복사한 다음 정보를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="86b5e-166">During the completion of this step (by following the step-by-step instructions), you'll provide the following information (that you've copied to a text file after completing the previous steps):</span></span>

- <span data-ttu-id="86b5e-167">Twitter API 키(3단계에서 획득)</span><span class="sxs-lookup"><span data-stu-id="86b5e-167">Twitter API Key (obtained in Step 3)</span></span>

- <span data-ttu-id="86b5e-168">Twitter API 비밀 키(3단계에서 획득)</span><span class="sxs-lookup"><span data-stu-id="86b5e-168">Twitter API Secret Key (obtained in Step 3)</span></span>

- <span data-ttu-id="86b5e-169">Twitter 액세스 토큰(3단계에서 획득)</span><span class="sxs-lookup"><span data-stu-id="86b5e-169">Twitter Access Token (obtained in Step 3)</span></span>

- <span data-ttu-id="86b5e-170">Twitter 액세스 토큰 비밀(3단계에서 획득)</span><span class="sxs-lookup"><span data-stu-id="86b5e-170">Twitter Access Token Secret (obtained in Step 3)</span></span>

- <span data-ttu-id="86b5e-171">Azure Active Directory 응용 프로그램 ID(1단계에서 획득한 AAD 응용 프로그램 ID)</span><span class="sxs-lookup"><span data-stu-id="86b5e-171">Azure Active Directory application ID (the AAD application ID obtained in Step 1)</span></span>

- <span data-ttu-id="86b5e-172">Azure Active Directory 응용 프로그램 비밀(1단계에서 얻은 AAD 응용 프로그램 비밀)</span><span class="sxs-lookup"><span data-stu-id="86b5e-172">Azure Active Directory application secret (the AAD application secret obtained in Step 1)</span></span>

## <a name="step-5-set-up-a-twitter-connector-in-the-microsoft-365-compliance-center"></a><span data-ttu-id="86b5e-173">5단계: Microsoft 365 규정 준수 센터에서 Twitter 커넥터 설정</span><span class="sxs-lookup"><span data-stu-id="86b5e-173">Step 5: Set up a Twitter connector in the Microsoft 365 compliance center</span></span>

<span data-ttu-id="86b5e-174">마지막 단계는 조직의 Twitter 계정에서 지정된 사서함으로 데이터를 가져오는 Microsoft 365 준수 센터에서 Twitter 커넥터를 Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="86b5e-174">The final step is to set up the Twitter connector in the Microsoft 365 compliance center that will import data from your organization's Twitter account to a specified mailbox in Microsoft 365.</span></span> <span data-ttu-id="86b5e-175">이 단계를 완료하면 Microsoft 365 가져오기 서비스가 조직의 Twitter 계정에서 데이터 가져오기 작업을 Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="86b5e-175">After you complete this step, the Microsoft 365 Import service will start importing data from your organization's Twitter account to Microsoft 365.</span></span>

<span data-ttu-id="86b5e-176">단계별 지침은 [Set up a Twitter connector in the Microsoft 365 참조하세요.](deploy-twitter-connector.md#step-5-set-up-a-twitter-connector-in-the-microsoft-365-compliance-center)</span><span class="sxs-lookup"><span data-stu-id="86b5e-176">For step-by-step instructions, see [Set up a Twitter connector in the Microsoft 365 compliance center](deploy-twitter-connector.md#step-5-set-up-a-twitter-connector-in-the-microsoft-365-compliance-center).</span></span> 

<span data-ttu-id="86b5e-177">이 단계를 완료하는 동안(단계별 지침에 따라) 다음 정보를 제공합니다(단계를 완료한 후 텍스트 파일에 복사).</span><span class="sxs-lookup"><span data-stu-id="86b5e-177">During the completion of this step (by following the step-by-step instructions), you'll provide the following information (that you've copied to a text file after completing the steps).</span></span>

- <span data-ttu-id="86b5e-178">Azure 앱 서비스 URL(예: 2단계에서 `https://twitterconnector.azurewebsites.net` 획득)</span><span class="sxs-lookup"><span data-stu-id="86b5e-178">Azure app service URL (obtained in Step 2; for example, `https://twitterconnector.azurewebsites.net`)</span></span>

- <span data-ttu-id="86b5e-179">APISecretKey(2단계에서 만든)</span><span class="sxs-lookup"><span data-stu-id="86b5e-179">APISecretKey (that you created in Step 2)</span></span>