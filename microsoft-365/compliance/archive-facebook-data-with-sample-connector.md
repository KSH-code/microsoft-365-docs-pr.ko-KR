---
title: Facebook 데이터를 보관할 커넥터 설정
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection: M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: 법적 보존, 콘텐츠 검색 및 보존 정책과 같은 규정 준수 기능을 사용할 수 있도록 Facebook 데이터를 Microsoft 365로 가져오는 커넥터를 설정 합니다.
ms.openlocfilehash: e35e4cb8e0f16d3cc95b3f21ce6648bbe087733d
ms.sourcegitcommit: ab0a944159d9349fbc7adc2f51c7f881254d7782
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/12/2020
ms.locfileid: "44210545"
---
# <a name="set-up-a-connector-to-archive-facebook-data-preview"></a><span data-ttu-id="c2ee5-103">Facebook 데이터를 보관할 커넥터 설정 (미리 보기)</span><span class="sxs-lookup"><span data-stu-id="c2ee5-103">Set up a connector to archive Facebook data (preview)</span></span>

<span data-ttu-id="c2ee5-104">Microsoft 365 준수 센터의 커넥터를 사용 하 여 Facebook Business 페이지의 데이터를 Microsoft 365로 가져오고 보관 합니다.</span><span class="sxs-lookup"><span data-stu-id="c2ee5-104">Use a connector in the Microsoft 365 compliance center to import and archive data from Facebook Business pages to Microsoft 365.</span></span> <span data-ttu-id="c2ee5-105">커넥터를 설정 하 고 구성한 후에는이를 Facebook Business 페이지에 연결 하 고 (예약 된 방식), Facebook 항목의 콘텐츠를 전자 메일 메시지 형식으로 변환한 다음 해당 항목을 Microsoft 365의 사서함으로 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="c2ee5-105">After you set up and configure the connector, it connects to the Facebook Business page (on a scheduled basis), converts the content of Facebook items to an email message format, and then imports those items to a mailbox in Microsoft 365.</span></span>

<span data-ttu-id="c2ee5-106">Facebook 데이터를 가져온 후 소송 보존, 콘텐츠 검색, 원본 위치 보관, 감사, 통신 준수 및 Microsoft 365 보존 정책 등의 Microsoft 365 준수 기능을 Facebook 데이터에 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c2ee5-106">After the Facebook data is imported, you can apply Microsoft 365 compliance features such as Litigation Hold, Content Search, In-Place Archiving, Auditing, Communication compliance, and Microsoft 365 retention policies to the Facebook data.</span></span> <span data-ttu-id="c2ee5-107">예를 들어 사서함이 소송 보존으로 설정 되거나 할당 되 면 Facebook 데이터가 보존 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c2ee5-107">For example, when a mailbox is placed on Litigation Hold or assigned to a retention policy, the Facebook data is preserved.</span></span> <span data-ttu-id="c2ee5-108">콘텐츠 검색을 사용 하 여 타사 데이터를 검색 하거나, 고급 eDiscovery 사례에서 Facebook 데이터가 custodian와 함께 저장 된 사서함을 연결할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c2ee5-108">You can search third-party data using Content Search or associate the mailbox where the Facebook data is stored with a custodian in an Advanced eDiscovery case.</span></span> <span data-ttu-id="c2ee5-109">커넥터를 사용 하 여 Microsoft 365에서 Facebook 데이터를 가져오고 보관 하면 조직이 정부 및 규정 정책을 준수 하는 데 도움이 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c2ee5-109">Using a connector to import and archive Facebook data in Microsoft 365 can help your organization stay compliant with government and regulatory policies.</span></span>

## <a name="prerequisites-for-setting-up-a-connector-for-facebook-business-pages"></a><span data-ttu-id="c2ee5-110">Facebook Business 페이지에 대 한 커넥터를 설정 하기 위한 필수 구성 요소</span><span class="sxs-lookup"><span data-stu-id="c2ee5-110">Prerequisites for setting up a connector for Facebook Business pages</span></span>

<span data-ttu-id="c2ee5-111">Microsoft 365 준수 센터에서 커넥터를 설정 및 구성 하 여 조직의 Facebook 비즈니스 페이지에서 데이터를 가져오고 보관 하려면 먼저 다음 필수 구성 요소를 완료 합니다.</span><span class="sxs-lookup"><span data-stu-id="c2ee5-111">Complete the following prerequisites before you can set up and configure a connector in the Microsoft 365 compliance center to import and archive data from your organization's Facebook Business pages.</span></span> 

- <span data-ttu-id="c2ee5-112">조직의 비즈니스 페이지에 대 한 Facebook 계정이 필요 합니다 (커넥터를 설정할 때이 계정에 로그인 해야 합니다.).</span><span class="sxs-lookup"><span data-stu-id="c2ee5-112">You need a Facebook account for your organization's business pages (you need to sign in to this account when setting up the connector).</span></span> <span data-ttu-id="c2ee5-113">현재는 Facebook Business 페이지의 데이터만 보관할 수 있습니다. 개별 Facebook 프로필에서 데이터를 보관할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="c2ee5-113">Currently, you can only archive data from Facebook Business pages; you can't archive data from individual Facebook profiles.</span></span>

- <span data-ttu-id="c2ee5-114">조직에 유효한 Azure 구독이 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c2ee5-114">Your organization must have a valid Azure subscription.</span></span> <span data-ttu-id="c2ee5-115">기존 Azure 구독이 없는 경우 다음 옵션 중 하나를 등록할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c2ee5-115">If you don't have an existing Azure subscription, you can sign up for one of these options:</span></span>

    - [<span data-ttu-id="c2ee5-116">무료 1 년간 Azure 구독 등록</span><span class="sxs-lookup"><span data-stu-id="c2ee5-116">Sign up for a free one year Azure subscription</span></span>](https://azure.microsoft.com/free) 

    - [<span data-ttu-id="c2ee5-117">방문 비용 청구 Azure 구독에 등록</span><span class="sxs-lookup"><span data-stu-id="c2ee5-117">Sign up for a Pay-As-You-Go Azure subscription</span></span>](https://azure.microsoft.com/pricing/purchase-options/pay-as-you-go/)

    > [!NOTE]
    > <span data-ttu-id="c2ee5-118">Microsoft 365 구독에 포함 된 [무료 Azure Active Directory 구독은](use-your-free-azure-ad-subscription-in-office-365.md) 보안 & 준수 센터의 커넥터를 지원 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c2ee5-118">The [free Azure Active Directory subscription](use-your-free-azure-ad-subscription-in-office-365.md) that's included with your Microsoft 365 subscription doesn't support the connectors in the Security & Compliance Center.</span></span>

- <span data-ttu-id="c2ee5-119">조직에서는 Office 365 가져오기 서비스가 조직의 사서함 데이터에 액세스할 수 있도록 허용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c2ee5-119">Your organization must consent to allow the Office 365 Import service to access mailbox data in your organization.</span></span> <span data-ttu-id="c2ee5-120">이 요청에 동의 하려면 [이 페이지로](https://login.microsoftonline.com/common/oauth2/authorize?client_id=570d0bec-d001-4c4e-985e-3ab17fdc3073&response_type=code&redirect_uri=https://portal.azure.com/&nonce=1234&prompt=admin_consent)이동 하 여 전역 관리자의 자격 증명으로 로그인 한 다음 요청을 수락 합니다.</span><span class="sxs-lookup"><span data-stu-id="c2ee5-120">To consent to this request, go to [this page](https://login.microsoftonline.com/common/oauth2/authorize?client_id=570d0bec-d001-4c4e-985e-3ab17fdc3073&response_type=code&redirect_uri=https://portal.azure.com/&nonce=1234&prompt=admin_consent), sign in with the credentials of a global admin, and then accept the request.</span></span>

- <span data-ttu-id="c2ee5-121">Microsoft 365 준수 센터에서 사용자 지정 커넥터를 설정 하는 사용자 (5 단계)에는 Exchange Online의 사서함 가져오기 내보내기 역할이 할당 되어 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c2ee5-121">The user who sets up the custom connector in the Microsoft 365 compliance center (in Step 5) must be assigned the Mailbox Import Export role in Exchange Online.</span></span> <span data-ttu-id="c2ee5-122">기본적으로이 역할은 Exchange Online의 어떤 역할 그룹에도 할당되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c2ee5-122">By default, this role isn't assigned to any role group in Exchange Online.</span></span> <span data-ttu-id="c2ee5-123">Exchange Online의 조직 관리 역할 그룹에 사서함 가져오기 내보내기 역할을 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c2ee5-123">You can add the Mailbox Import Export role to the Organization Management role group in Exchange Online.</span></span> <span data-ttu-id="c2ee5-124">또는 역할 그룹을 만들고 사서함 가져오기 내보내기 역할을 할당 한 다음 해당 사용자를 구성원으로 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c2ee5-124">Or you can create a role group, assign the Mailbox Import Export role, and then add the appropriate users as members.</span></span> <span data-ttu-id="c2ee5-125">자세한 내용은 "Exchange Online에서 역할 그룹 관리" 문서의 [역할 그룹 만들기](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#create-role-groups) 또는 [역할 그룹 수정](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#modify-role-groups) 섹션을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="c2ee5-125">For more information, see the  [Create role groups](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#create-role-groups) or [Modify role groups](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#modify-role-groups) sections in the article "Manage role groups in Exchange Online".</span></span>

## <a name="step-1-create-an-app-in-azure-active-directory"></a><span data-ttu-id="c2ee5-126">1 단계: Azure Active Directory에 앱 만들기</span><span class="sxs-lookup"><span data-stu-id="c2ee5-126">Step 1: Create an app in Azure Active Directory</span></span>

<span data-ttu-id="c2ee5-127">첫 번째 단계는 AAD (Azure Active Directory)에서 새 앱을 등록 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="c2ee5-127">The first step is to register a new app in Azure Active Directory (AAD).</span></span> <span data-ttu-id="c2ee5-128">이 앱은 Facebook 커넥터에 대해 4 단계와 5 단계에서 구현 하는 웹 앱 리소스에 해당 합니다.</span><span class="sxs-lookup"><span data-stu-id="c2ee5-128">This app corresponds to the web app resource that you implement in Step 4 and Step 5 for the Facebook connector.</span></span> 

<span data-ttu-id="c2ee5-129">단계별 지침은 [Azure Active Directory에서 앱 만들기](deploy-facebook-connector.md#step-1-create-an-app-in-azure-active-directory)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="c2ee5-129">For step-by-step instructions, see [Create an app in Azure Active Directory](deploy-facebook-connector.md#step-1-create-an-app-in-azure-active-directory).</span></span>

<span data-ttu-id="c2ee5-130">이 단계를 완료 하는 동안 앞의 단계별 지침을 사용 하 여 다음 정보를 텍스트 파일에 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="c2ee5-130">During the completion of this step (by using the previous step-by-step instructions), you'll save the following information to a text file.</span></span> <span data-ttu-id="c2ee5-131">이러한 값은 배포 프로세스의 이후 단계에서 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c2ee5-131">These values are used in later steps in the deployment process.</span></span>

- <span data-ttu-id="c2ee5-132">AAD 응용 프로그램 ID</span><span class="sxs-lookup"><span data-stu-id="c2ee5-132">AAD application ID</span></span>

- <span data-ttu-id="c2ee5-133">AAD 응용 프로그램 비밀</span><span class="sxs-lookup"><span data-stu-id="c2ee5-133">AAD application secret</span></span>

- <span data-ttu-id="c2ee5-134">테 넌 트 Id</span><span class="sxs-lookup"><span data-stu-id="c2ee5-134">Tenant Id</span></span>

## <a name="step-2-deploy-the-connector-web-service-from-github-to-your-azure-account"></a><span data-ttu-id="c2ee5-135">2 단계: GitHub에서 Azure 계정으로 커넥터 웹 서비스 배포</span><span class="sxs-lookup"><span data-stu-id="c2ee5-135">Step 2: Deploy the connector web service from GitHub to your Azure account</span></span>

<span data-ttu-id="c2ee5-136">다음 단계는 facebook API를 사용 하 여 facebook 계정에 연결 하 고 데이터를 추출 하 여 Microsoft 365로 가져올 수 있는 Facebook Business pages connector 앱에 대 한 소스 코드를 배포 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="c2ee5-136">The next step is to deploy the source code for the Facebook Business pages connector app that will use the Facebook API to connect to your Facebook account and extract data so you can import it to Microsoft 365.</span></span> <span data-ttu-id="c2ee5-137">조직에 대해 배포 하는 Facebook 커넥터는 Facebook Business 페이지의 항목을이 단계에서 만든 Azure 저장소 위치로 업로드 합니다.</span><span class="sxs-lookup"><span data-stu-id="c2ee5-137">The Facebook connector that you deploy for your organization will upload the items from your Facebook Business pages to the Azure Storage location that is created in this step.</span></span> <span data-ttu-id="c2ee5-138">Microsoft 365 준수 센터 (5 단계)에서 Facebook business pages connector를 만든 후에는 가져오기 서비스가 Azure Storage 위치에서 Microsoft 365 조직의 사서함으로 Facebook 비즈니스 페이지 데이터를 복사 합니다.</span><span class="sxs-lookup"><span data-stu-id="c2ee5-138">After you create a Facebook business pages connector in the Microsoft 365 compliance center (in Step 5), the Import service will copy the Facebook business pages data from the Azure Storage location to a mailbox in your Microsoft 365 organization.</span></span> <span data-ttu-id="c2ee5-139">앞에서 설명한 것 처럼 [필수 구성 요소](#prerequisites-for-setting-up-a-connector-for-facebook-business-pages) 섹션에서 azure Storage 계정을 만들려면 유효한 azure 구독이 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c2ee5-139">As previous explained in the [Prerequisites](#prerequisites-for-setting-up-a-connector-for-facebook-business-pages) section, you must have a valid Azure subscription to create an Azure Storage account.</span></span>

<span data-ttu-id="c2ee5-140">단계별 지침은 [GitHub의 커넥터 웹 서비스를 Azure 계정에 배포](deploy-facebook-connector.md#step-2-deploy-the-connector-web-service-from-github-to-your-azure-account)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="c2ee5-140">For step-by-step instructions, see [Deploy the connector web service from GitHub to your Azure account](deploy-facebook-connector.md#step-2-deploy-the-connector-web-service-from-github-to-your-azure-account).</span></span>

<span data-ttu-id="c2ee5-141">이 단계를 완료 하는 단계별 지침에서는 다음 정보를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="c2ee5-141">In the step-by-step instructions to complete this step, you'll provide the following information:</span></span>

- <span data-ttu-id="c2ee5-142">APISecretKey:이 단계를 완료 하는 동안이 비밀을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="c2ee5-142">APISecretKey: You create this secret during the completion of this step.</span></span> <span data-ttu-id="c2ee5-143">5 단계에서 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c2ee5-143">It's used in Step 5.</span></span>

- <span data-ttu-id="c2ee5-144">TenantId: 1 단계에서 Azure Active Directory에 Facebook 커넥터 앱을 만든 후 복사한 Microsoft 365 조직의 테 넌 트 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="c2ee5-144">TenantId: The tenant ID of your Microsoft 365 organization that you copied after creating the Facebook connector app in Azure Active Directory in Step 1.</span></span>

<span data-ttu-id="c2ee5-145">이 단계를 완료 한 후 Azure 앱 서비스 URL (예:을 복사 해야 https://fbconnector.azurewebsites.net) 합니다.</span><span class="sxs-lookup"><span data-stu-id="c2ee5-145">After completing this step, be sure to copy the Azure app service URL (for example, https://fbconnector.azurewebsites.net).</span></span> <span data-ttu-id="c2ee5-146">이 URL을 사용 하 여 3 단계, 4 단계, 5 단계를 완료 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c2ee5-146">You need to use this URL to complete Step 3, Step 4, and Step 5).</span></span>

## <a name="step-3-register-the-web-app-on-facebook"></a><span data-ttu-id="c2ee5-147">3 단계: Facebook에서 웹 앱 등록</span><span class="sxs-lookup"><span data-stu-id="c2ee5-147">Step 3: Register the web app on Facebook</span></span>

<span data-ttu-id="c2ee5-148">다음 단계는 Facebook에서 새 앱을 만들고 구성 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="c2ee5-148">The next step is to create and configure a new app on Facebook.</span></span> <span data-ttu-id="c2ee5-149">5 단계에서 만든 Facebook business pages connector는 facebook 웹 앱을 사용 하 여 facebook API와 상호 작용 하 여 조직의 Facebook 비즈니스 페이지에서 데이터를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="c2ee5-149">The Facebook business pages connector that you create in Step 5 uses the Facebook web app to interact with the Facebook API to obtain data from your organization's Facebook Business pages.</span></span>

<span data-ttu-id="c2ee5-150">단계별 지침은 [Facebook 앱 등록](deploy-facebook-connector.md#step-3-register-the-facebook-app)을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="c2ee5-150">For step-by-step instructions, see [Register the Facebook app](deploy-facebook-connector.md#step-3-register-the-facebook-app).</span></span>

<span data-ttu-id="c2ee5-151">단계별 지침에 따라이 단계를 완료 하는 동안 다음 정보를 텍스트 파일에 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="c2ee5-151">During the completion of this step (by following the step-by-step instructions), you save the following information to a text file.</span></span> <span data-ttu-id="c2ee5-152">이러한 값은 4 단계에서 Facebook 커넥터 응용 프로그램을 구성 하는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c2ee5-152">These values are used to configure the Facebook connector app in Step 4.</span></span>

- <span data-ttu-id="c2ee5-153">Facebook 응용 프로그램 ID</span><span class="sxs-lookup"><span data-stu-id="c2ee5-153">Facebook application ID</span></span>

- <span data-ttu-id="c2ee5-154">Facebook 응용 프로그램 비밀</span><span class="sxs-lookup"><span data-stu-id="c2ee5-154">Facebook application secret</span></span>

- <span data-ttu-id="c2ee5-155">Facebook webhook 확인 토큰</span><span class="sxs-lookup"><span data-stu-id="c2ee5-155">Facebook webhooks verify token</span></span>

## <a name="step-4-configure-the-facebook-connector-app"></a><span data-ttu-id="c2ee5-156">4 단계: Facebook 커넥터 응용 프로그램 구성</span><span class="sxs-lookup"><span data-stu-id="c2ee5-156">Step 4: Configure the Facebook connector app</span></span>

<span data-ttu-id="c2ee5-157">다음 단계에서는 1 단계에서 Azure web app 리소스를 만들 때 업로드 한 Facebook 커넥터 앱에 구성 설정을 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="c2ee5-157">The next step is to add configuration settings to the Facebook connector app that you uploaded when you created the Azure web app resource in Step 1.</span></span> <span data-ttu-id="c2ee5-158">이렇게 하려면 커넥터 응용 프로그램의 홈 페이지로 이동 하 여 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="c2ee5-158">You do this by going to the home page of your connector app and configuring it.</span></span>

<span data-ttu-id="c2ee5-159">단계별 지침은 [Facebook connector 앱 구성을](archive-facebook-data-with-sample-connector.md#step-4-configure-the-facebook-connector-app)참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="c2ee5-159">For step-by-step instructions, see [Configure the Facebook connector app](archive-facebook-data-with-sample-connector.md#step-4-configure-the-facebook-connector-app).</span></span>

<span data-ttu-id="c2ee5-160">단계별 지침에 따라이 단계를 완료 하는 동안 이전 단계를 완료 한 후 텍스트 파일에 복사한 다음 정보를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="c2ee5-160">During the completion of this step (by following the step-by-step instructions), you provide the following information (that you've copied to a text file after completing the previous steps):</span></span>

- <span data-ttu-id="c2ee5-161">Facebook 응용 프로그램 ID (3 단계에서 가져옴)</span><span class="sxs-lookup"><span data-stu-id="c2ee5-161">Facebook application ID (obtained in Step 3)</span></span>

- <span data-ttu-id="c2ee5-162">Facebook 응용 프로그램 비밀 (3 단계에서 가져옴)</span><span class="sxs-lookup"><span data-stu-id="c2ee5-162">Facebook application secret (obtained in Step 3)</span></span>

- <span data-ttu-id="c2ee5-163">Facebook webhook 확인 토큰 (3 단계에서 가져옴)</span><span class="sxs-lookup"><span data-stu-id="c2ee5-163">Facebook webhooks verify token (obtained in Step 3)</span></span>

- <span data-ttu-id="c2ee5-164">Azure Active Directory 응용 프로그램 ID (1 단계에서 가져온 AAD 응용 프로그램 ID)</span><span class="sxs-lookup"><span data-stu-id="c2ee5-164">Azure Active Directory application ID (the AAD application ID obtained in Step 1)</span></span>

- <span data-ttu-id="c2ee5-165">Azure Active Directory 응용 프로그램 비밀 (1 단계에서 얻은 AAD 응용 프로그램 암호)</span><span class="sxs-lookup"><span data-stu-id="c2ee5-165">Azure Active Directory application secret (the AAD application secret obtained in Step 1)</span></span>

## <a name="step-5-set-up-a-facebook-business-pages-connector-in-the-microsoft-365-compliance-center"></a><span data-ttu-id="c2ee5-166">5 단계: Microsoft 365 준수 센터에서 Facebook Business pages connector 설정</span><span class="sxs-lookup"><span data-stu-id="c2ee5-166">Step 5: Set up a Facebook Business pages connector in the Microsoft 365 compliance center</span></span>

<span data-ttu-id="c2ee5-167">마지막 단계에서는 microsoft 365의 Facebook Business 페이지에서 지정 된 사서함으로 데이터를 가져올 수 있는 커넥터를 마이크로소프트 365 준수 센터에 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="c2ee5-167">The final step is to set up the connector in the Microsoft 365 compliance center that will import data from your Facebook Business pages to a specified mailbox in Microsoft 365.</span></span> <span data-ttu-id="c2ee5-168">이 단계를 완료 하면 Office 365 가져오기 서비스가 Facebook 비즈니스 페이지의 데이터를 Microsoft 365로 가져오는 것을 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="c2ee5-168">After you complete this step, the Office 365 Import service will start importing data from your Facebook Business pages to Microsoft 365.</span></span>

<span data-ttu-id="c2ee5-169">단계별 지침은 [5 단계: Microsoft 365 준수 센터에서 Facebook 커넥터 설정](deploy-facebook-connector.md#step-5-set-up-a-facebook-connector-in-the-microsoft-365-compliance-center)를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="c2ee5-169">For step-by-step instructions, see [Step 5: Set up a Facebook connector in the Microsoft 365 compliance center](deploy-facebook-connector.md#step-5-set-up-a-facebook-connector-in-the-microsoft-365-compliance-center).</span></span> 

<span data-ttu-id="c2ee5-170">이 단계를 완료 하는 동안 단계별 지침에 따라 다음 정보를 입력 합니다 (단계 완료 후에 텍스트 파일로 복사한 내용).</span><span class="sxs-lookup"><span data-stu-id="c2ee5-170">During the completion of this step (by following the step-by-step instructions), you provide the following information (that you've copied to a text file after completing the steps).</span></span>

- <span data-ttu-id="c2ee5-171">AAD 응용 프로그램 ID (1 단계에서 가져옴)</span><span class="sxs-lookup"><span data-stu-id="c2ee5-171">AAD application ID (obtained in Step 1)</span></span>

- <span data-ttu-id="c2ee5-172">Azure app service URL (1 단계에서 가져옴)-예를 들면https://fbconnector.azurewebsites.net)</span><span class="sxs-lookup"><span data-stu-id="c2ee5-172">Azure app service URL (obtained in Step 1; for example, https://fbconnector.azurewebsites.net)</span></span>

- <span data-ttu-id="c2ee5-173">APISecretKey (2 단계에서 만든 것)</span><span class="sxs-lookup"><span data-stu-id="c2ee5-173">APISecretKey (that you created in Step 2)</span></span>
