---
title: Twitter 데이터를 보관할 커넥터 설정
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
description: 관리자는 네이티브 커넥터를 설정 하 여 Twitter 데이터를 Office 365로 가져올 수 있습니다. 이를 통해 Office 365의 타사 데이터 원본에서 데이터를 보관할 수 있으므로 법적 보존, 콘텐츠 검색 및 보존 정책과 같은 규정 준수 기능을 사용 하 여 조직의 타사 데이터를 관리 하는 것을 관리할 수도 있습니다.
ms.openlocfilehash: 083c293e869cb35b428592717b7cf3810e7fea8c
ms.sourcegitcommit: ce0651075aa7e3e1b189437f1990207dd10374b0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/21/2020
ms.locfileid: "41247561"
---
# <a name="set-up-a-connector-to-archive-twitter-data"></a><span data-ttu-id="00021-104">Twitter 데이터를 보관할 커넥터 설정</span><span class="sxs-lookup"><span data-stu-id="00021-104">Set up a connector to archive Twitter data</span></span>

<span data-ttu-id="00021-105">Office 365의 보안 & 준수 센터에서 커넥터를 사용 하 여 Twitter에서 데이터를 가져오고 보관 합니다.</span><span class="sxs-lookup"><span data-stu-id="00021-105">Use a connector in the Security & Compliance Center in Office 365 to import and archive data from Twitter.</span></span> <span data-ttu-id="00021-106">커넥터를 설정 하 고 구성한 후에는 일정에 따라 조직의 Twitter 계정에 연결 하 고, 항목의 콘텐츠를 전자 메일 메시지 형식으로 변환한 다음 해당 항목을 Office 365의 사서함으로 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="00021-106">After you set up and configure a connector, it connects to your organization's Twitter account (on a scheduled basis), converts the content of an item to an email message format, and then imports those items to a mailbox in Office 365.</span></span>

<span data-ttu-id="00021-107">Twitter 데이터를 가져온 후에는 사서함에 저장 된 데이터에 소송 보존, 콘텐츠 검색, 원본 위치 보관, 감사, 통신 준수 및 Office 365 고정 정책 등의 Office 365 준수 기능을 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="00021-107">After Twitter data is imported, you can apply Office 365 compliance features such as Litigation Hold, Content Search, In-Place Archiving, Auditing, Communication compliance, and Office 365 retention policies to the data stored in the mailbox.</span></span> <span data-ttu-id="00021-108">예를 들어 콘텐츠 검색을 사용 하 여 Twitter 데이터를 검색 하거나, 데이터가 고급 eDiscovery 사례에 custodian으로 저장 된 사서함을 연결할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="00021-108">For example, you can search Twitter data using Content Search or associate the mailbox where the data is stored with a custodian in an Advanced eDiscovery case.</span></span> <span data-ttu-id="00021-109">커넥터를 사용 하 여 Office 365에서 Twitter 데이터를 가져오고 보관 하면 조직이 정부 및 규정 정책을 준수 하는 데 도움이 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="00021-109">Using a connector to import and archive Twitter data in Office 365 can help your organization stay compliant with government and regulatory policies.</span></span>

## <a name="prerequisites-for-setting-up-a-connector-for-twitter"></a><span data-ttu-id="00021-110">Twitter에 대 한 커넥터를 설정 하기 위한 필수 구성 요소</span><span class="sxs-lookup"><span data-stu-id="00021-110">Prerequisites for setting up a connector for Twitter</span></span>

<span data-ttu-id="00021-111">조직의 Twitter 계정에서 데이터를 가져오고 보관 하기 위해 보안 & 준수 센터에서 커넥터를 설정 및 구성 하려면 먼저 다음 필수 구성 요소를 완료 합니다.</span><span class="sxs-lookup"><span data-stu-id="00021-111">Complete the following prerequisites before you can set up and configure a connector in the Security & Compliance Center to import and archive data from your organization's Twitter account.</span></span> 

- <span data-ttu-id="00021-112">조직에 대 한 Twitter 계정이 필요 합니다. 커넥터를 설정 하는 경우이 계정에 로그인 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="00021-112">You need a Twitter account for your organization; you need to sign in to this account when setting up the connector.</span></span>

- <span data-ttu-id="00021-113">조직에 유효한 Azure 구독이 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="00021-113">Your organization must have a valid Azure subscription.</span></span> <span data-ttu-id="00021-114">기존 Azure 구독이 없는 경우 다음 옵션 중 하나를 등록할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="00021-114">If you don't have an existing Azure subscription, you can sign up for one of these options:</span></span>

    - [<span data-ttu-id="00021-115">무료 1 년간 Azure 구독 등록</span><span class="sxs-lookup"><span data-stu-id="00021-115">Sign up for a free one year Azure subscription</span></span>](https://azure.microsoft.com/free) 

    - [<span data-ttu-id="00021-116">방문 비용 청구 Azure 구독에 등록</span><span class="sxs-lookup"><span data-stu-id="00021-116">Sign up for a Pay-As-You-Go Azure subscription</span></span>](https://azure.microsoft.com/pricing/purchase-options/pay-as-you-go/)

    > [!NOTE]
    > <span data-ttu-id="00021-117">Office 365 구독에 포함 된 [무료 Azure Active Directory 구독은](use-your-free-azure-ad-subscription-in-office-365.md) 보안 & 준수 센터의 커넥터를 지원 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="00021-117">The [free Azure Active Directory subscription](use-your-free-azure-ad-subscription-in-office-365.md) that's included with your Office 365 subscription doesn't support the connectors in the Security & Compliance Center.</span></span>

- <span data-ttu-id="00021-118">조직에서는 Office 365 가져오기 서비스가 조직의 사서함 데이터에 액세스할 수 있도록 허용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="00021-118">Your organization must consent to allow the Office 365 Import service to access mailbox data in your organization.</span></span> <span data-ttu-id="00021-119">이 요청에 동의 하려면 [이 페이지로](https://login.microsoftonline.com/common/oauth2/authorize?client_id=570d0bec-d001-4c4e-985e-3ab17fdc3073&response_type=code&redirect_uri=https://portal.azure.com/&nonce=1234&prompt=admin_consent)이동 하 여 Office 365 전역 관리자의 자격 증명으로 로그인 한 다음 요청을 수락 합니다.</span><span class="sxs-lookup"><span data-stu-id="00021-119">To consent to this request, go to [this page](https://login.microsoftonline.com/common/oauth2/authorize?client_id=570d0bec-d001-4c4e-985e-3ab17fdc3073&response_type=code&redirect_uri=https://portal.azure.com/&nonce=1234&prompt=admin_consent), sign in with the credentials of an Office 365 global admin, and then accept the request.</span></span>

- <span data-ttu-id="00021-120">보안 & 준수 (7 단계)에서 사용자 지정 커넥터를 설정 하는 사용자에 게 Exchange Online의 사서함 가져오기 내보내기 역할이 할당 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="00021-120">The user who sets up the custom connector in the Security & Compliance (in Step 7) must be assigned the Mailbox Import Export role in Exchange Online.</span></span> <span data-ttu-id="00021-121">기본적으로이 역할은 Exchange Online의 어떤 역할 그룹에도 할당되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="00021-121">By default, this role isn't assigned to any role group in Exchange Online.</span></span> <span data-ttu-id="00021-122">Exchange Online의 조직 관리 역할 그룹에 사서함 가져오기 내보내기 역할을 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="00021-122">You can add the Mailbox Import Export role to the Organization Management role group in Exchange Online.</span></span> <span data-ttu-id="00021-123">또는 새 역할 그룹을 만들고 사서함 가져오기 내보내기 역할을 할당 한 다음 해당 사용자를 구성원으로 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="00021-123">Or you can create a new role group, assign the Mailbox Import Export role, and then add the appropriate users as members.</span></span> <span data-ttu-id="00021-124">자세한 내용은 "Exchange Online에서 역할 그룹 관리" 문서의 [역할 그룹 만들기](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#create-role-groups) 또는 [역할 그룹 수정](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#modify-role-groups) 섹션을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="00021-124">For more information, see the [Create role groups](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#create-role-groups) or [Modify role groups](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#modify-role-groups) sections in the article "Manage role groups in Exchange Online".</span></span>

## <a name="step-1-download-the-pre-built-connector-app-package-from-github"></a><span data-ttu-id="00021-125">1 단계: GitHub에서 미리 작성 된 커넥터 앱 패키지 다운로드</span><span class="sxs-lookup"><span data-stu-id="00021-125">Step 1: Download the pre-built connector app package from GitHub</span></span>

<span data-ttu-id="00021-126">첫 번째 단계는 twitter API를 사용 하 여 twitter 계정에 연결 하 고 데이터를 추출 하 여 Office 365로 가져올 수 있는 Twitter 커넥터 앱의 소스 코드를 다운로드 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="00021-126">The first step is to download the source code for the Twitter connector app that will use a Twitter API to connect to your Twitter account and extract data so you can import it to Office 365.</span></span>

1. <span data-ttu-id="00021-127">[이 GitHub 사이트로](https://github.com/microsoft/m365-sample-twitter-connector-csharp-aspnet/releases)이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="00021-127">Go to [this GitHub site](https://github.com/microsoft/m365-sample-twitter-connector-csharp-aspnet/releases).</span></span> 
2. <span data-ttu-id="00021-128">최신 버전에서 **SampleConnector** 파일을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="00021-128">Under the latest release, select the **SampleConnector.zip** file.</span></span>
3. <span data-ttu-id="00021-129">로컬 컴퓨터의 위치에 ZIP 파일을 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="00021-129">Save the ZIP file to a location on your local computer.</span></span> <span data-ttu-id="00021-130">4 단계에서이 zip 파일을 Azure에 업로드 합니다.</span><span class="sxs-lookup"><span data-stu-id="00021-130">You upload this zip file to Azure in Step 4.</span></span>

## <a name="step-2-create-an-app-in-azure-active-directory"></a><span data-ttu-id="00021-131">2 단계: Azure Active Directory에 앱 만들기</span><span class="sxs-lookup"><span data-stu-id="00021-131">Step 2: Create an app in Azure Active Directory</span></span>

<span data-ttu-id="00021-132">다음 단계에서는 AAD (Azure Active Directory)에서 새 앱을 등록 합니다.</span><span class="sxs-lookup"><span data-stu-id="00021-132">The next step is to register a new app in Azure Active Directory (AAD).</span></span> <span data-ttu-id="00021-133">이 앱은 Twitter 커넥터에 대해 4 단계에서 구현 하는 웹 앱 리소스에 해당 합니다.</span><span class="sxs-lookup"><span data-stu-id="00021-133">This app corresponds to the web app resource that you implement in Step 4 for the Twitter connector.</span></span> 

<span data-ttu-id="00021-134">단계별 지침은 [2 단계: Azure Active Directory에서 앱 만들기](deploy-twitter-connector.md#step-2-create-an-app-in-azure-active-directory)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="00021-134">For step-by-step instructions, see [Step 2: Create an app in Azure Active Directory](deploy-twitter-connector.md#step-2-create-an-app-in-azure-active-directory).</span></span>

<span data-ttu-id="00021-135">단계별 지침에 따라이 단계를 완료 하는 동안 다음 정보를 텍스트 파일에 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="00021-135">During the completion of this step (by following the step-by-step instructions), you'll save the following information to a text file.</span></span> <span data-ttu-id="00021-136">이러한 값은 배포 프로세스의 이후 단계에서 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="00021-136">These values will be used in later steps in the deployment process.</span></span>

- <span data-ttu-id="00021-137">AAD 응용 프로그램 ID</span><span class="sxs-lookup"><span data-stu-id="00021-137">AAD application ID</span></span>
- <span data-ttu-id="00021-138">AAD 응용 프로그램 비밀</span><span class="sxs-lookup"><span data-stu-id="00021-138">AAD application secret</span></span>
- <span data-ttu-id="00021-139">AAD 응용 프로그램 Uri</span><span class="sxs-lookup"><span data-stu-id="00021-139">AAD application Uri</span></span>
- <span data-ttu-id="00021-140">테 넌 트 Id</span><span class="sxs-lookup"><span data-stu-id="00021-140">Tenant Id</span></span>

## <a name="step-3-create-an-azure-storage-account"></a><span data-ttu-id="00021-141">3 단계: Azure Storage 계정 만들기</span><span class="sxs-lookup"><span data-stu-id="00021-141">Step 3: Create an Azure Storage account</span></span>

<span data-ttu-id="00021-142">조직에 대해 배포 하는 Twitter 커넥터는 Twitter의 항목을이 단계에서 만든 Azure Storage 위치로 업로드 합니다.</span><span class="sxs-lookup"><span data-stu-id="00021-142">The Twitter connector that you deploy for your organization uploads the items from Twitter to the Azure Storage location that you create in this step.</span></span> <span data-ttu-id="00021-143">보안 & 준수 센터 (7 단계)에서 사용자 지정 커넥터를 만든 후에는 Office 365 가져오기 서비스가 Azure Storage 위치에서 Twitter 데이터를 Office 365의 사서함으로 복사 합니다.</span><span class="sxs-lookup"><span data-stu-id="00021-143">After you create a custom connector in the Security & Compliance Center (in Step 7), the Office 365 Import service will copy the Twitter data from the Azure Storage location to a mailbox in Office 365.</span></span> <span data-ttu-id="00021-144">앞에서 설명한 것 처럼 [필수 구성 요소](#prerequisites-for-setting-up-a-connector-for-twitter) 섹션에서 azure Storage 계정을 만들려면 유효한 azure 구독이 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="00021-144">As previous explained in the [Prerequisites](#prerequisites-for-setting-up-a-connector-for-twitter) section, you must have a valid Azure subscription to create an Azure Storage account.</span></span>

<span data-ttu-id="00021-145">단계별 지침은 [3 단계: Azure Storage Account 만들기](deploy-twitter-connector.md#step-3-create-an-azure-storage-account)를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="00021-145">For step-by-step instructions, see [Step 3: Create an Azure Storage account](deploy-twitter-connector.md#step-3-create-an-azure-storage-account).</span></span>

<span data-ttu-id="00021-146">단계별 지침에 따라이 단계를 완료 하는 동안 생성 되는 연결 문자열 Uri를 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="00021-146">During the completion of this step (by following the step-by-step instructions), you save the connection string Uri that is generated.</span></span> <span data-ttu-id="00021-147">4 단계에서 Azure에서 웹 앱 리소스를 만들 때이 문자열을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="00021-147">You use this string when creating a web app resource in Azure in Step 4.</span></span>

## <a name="step-4-create-a-web-app-resource-in-azure"></a><span data-ttu-id="00021-148">4 단계: Azure에서 웹 앱 리소스 만들기</span><span class="sxs-lookup"><span data-stu-id="00021-148">Step 4: Create a web app resource in Azure</span></span>

<span data-ttu-id="00021-149">다음 단계는 Twitter 커넥터용 Azure에서 웹 앱 리소스를 만드는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="00021-149">The next step is to create a web app resource in Azure for the Twitter connector.</span></span> 

<span data-ttu-id="00021-150">단계별 지침은 [4 단계: Azure에서 새 웹 앱 리소스 만들기](deploy-twitter-connector.md#step-4-create-a-new-web-app-resource-in-azure)를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="00021-150">For step-by-step instructions, see [Step 4: Create a new web app resource in Azure](deploy-twitter-connector.md#step-4-create-a-new-web-app-resource-in-azure).</span></span>

<span data-ttu-id="00021-151">이 단계를 완료 하는 동안 단계별 지침을 따라 웹 앱 리소스를 만들 때 다음 정보 (이전 단계를 완료 한 후에 텍스트 파일로 복사)를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="00021-151">During the completion of this step (by following the step-by-step instructions), you'll provide the following information (that you've copied to a text file after completing the previous steps) when creating the web app resource.</span></span>

- <span data-ttu-id="00021-152">APISecretKey –이 단계를 완료 하는 동안이 비밀을 만듭니다. 7 단계에서 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="00021-152">APISecretKey – You create this secret during the completion of this step; it's used in Step 7.</span></span>
- <span data-ttu-id="00021-153">StorageAccountConnectionString-3 단계에서 Azure Storage 계정을 만든 후 복사한 연결 문자열 Uri입니다.</span><span class="sxs-lookup"><span data-stu-id="00021-153">StorageAccountConnectionString – The connection string Uri that you copied after creating the Azure Storage account in Step 3.</span></span>
- <span data-ttu-id="00021-154">tenantId-2 단계에서 Azure Active Directory에 Twitter 커넥터 앱을 만든 후 복사한 Office 365 조직의 테 넌 트 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="00021-154">tenantId – The tenant ID of your Office 365 organization that you copied after creating the Twitter connector app in Azure Active Directory in Step 2.</span></span>

<span data-ttu-id="00021-155">또한이 단계에서 1 단계에서 다운로드 한 SampleConnector 파일을 업로드 하 여 Twitter 커넥터 응용 프로그램에 대 한 소스 코드를 배포 합니다.</span><span class="sxs-lookup"><span data-stu-id="00021-155">Also, you upload the SampleConnector.zip file (that you downloaded in Step 1) in this step to deploy the source code for the Twitter connector app.</span></span>

<span data-ttu-id="00021-156">이 단계를 완료 한 후 Azure 앱 서비스 URL (예: `https://twitterconnector.azurewebsites.net`)을 복사 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="00021-156">After completing this step, be sure to copy the Azure app service URL (for example, `https://twitterconnector.azurewebsites.net`).</span></span> <span data-ttu-id="00021-157">5 단계, 6 단계 및 7 단계를 완료 하려면이 URL을 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="00021-157">You need to use this URL to complete Step 5, Step 6, and Step 7).</span></span>

## <a name="step-5-create-developer-app-on-twitter"></a><span data-ttu-id="00021-158">5 단계: Twitter에서 개발자 앱 만들기</span><span class="sxs-lookup"><span data-stu-id="00021-158">Step 5: Create developer app on Twitter</span></span>

<span data-ttu-id="00021-159">다음 단계에서는 Twitter에서 개발자 앱을 만들고 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="00021-159">The next step is to create and configure a developer app on Twitter.</span></span> <span data-ttu-id="00021-160">7 단계에서 만든 사용자 지정 커넥터는 twitter 앱을 사용 하 여 Twitter API와 상호 작용 하 여 조직의 Twitter 계정에서 데이터를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="00021-160">The custom connector that you create in Step 7 uses the Twitter app to interact with the Twitter API to obtain data from your organization's Twitter account.</span></span>

<span data-ttu-id="00021-161">단계별 지침은 [5 단계: Twitter 앱 만들기](deploy-twitter-connector.md#step-5-create-the-twitter-app)를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="00021-161">For step-by-step instructions, see [Step 5: Create the Twitter app](deploy-twitter-connector.md#step-5-create-the-twitter-app).</span></span>

<span data-ttu-id="00021-162">단계별 지침에 따라이 단계를 완료 하는 동안 다음 정보를 텍스트 파일에 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="00021-162">During the completion of this step (by following the step-by-step instructions), you save the following information to a text file.</span></span> <span data-ttu-id="00021-163">이러한 값은 6 단계에서 Twitter 커넥터 응용 프로그램을 구성 하는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="00021-163">These values will be used to configure the Twitter connector app in Step 6.</span></span>

- <span data-ttu-id="00021-164">Twitter API 키</span><span class="sxs-lookup"><span data-stu-id="00021-164">Twitter API Key</span></span>
- <span data-ttu-id="00021-165">Twitter API 비밀 키</span><span class="sxs-lookup"><span data-stu-id="00021-165">Twitter API Secret Key</span></span>
- <span data-ttu-id="00021-166">Twitter 액세스 토큰</span><span class="sxs-lookup"><span data-stu-id="00021-166">Twitter Access Token</span></span>
- <span data-ttu-id="00021-167">Twitter 액세스 토큰 암호</span><span class="sxs-lookup"><span data-stu-id="00021-167">Twitter Access Token Secret</span></span>

## <a name="step-6-configure-the-twitter-connector-app"></a><span data-ttu-id="00021-168">6 단계: Twitter 커넥터 응용 프로그램 구성</span><span class="sxs-lookup"><span data-stu-id="00021-168">Step 6: Configure the Twitter connector app</span></span>

<span data-ttu-id="00021-169">다음 단계에서는 4 단계에서 Azure web app 리소스를 만들 때 업로드 한 Twitter 커넥터 앱에 구성 설정을 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="00021-169">The next step is to add configurations settings to the Twitter connector app that you uploaded when you created the Azure web app resource in Step 4.</span></span> <span data-ttu-id="00021-170">이렇게 하려면 커넥터 응용 프로그램의 홈 페이지로 이동 하 여 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="00021-170">You do this by going to the home page of your connector app and configuring it.</span></span>

<span data-ttu-id="00021-171">단계별 지침은 [6 단계: 커넥터 웹 앱 구성을](deploy-twitter-connector.md#step-6-configure-the-connector-web-app)참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="00021-171">For step-by-step instructions, see [Step 6: Configure the connector web app](deploy-twitter-connector.md#step-6-configure-the-connector-web-app).</span></span>

<span data-ttu-id="00021-172">단계별 지침에 따라이 단계를 완료 하는 동안 이전 단계를 완료 한 후에 텍스트 파일로 복사한 다음 정보를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="00021-172">During the completion of this step (by following the step-by-step instructions), you'll provide the following information (that you've copied to a text file after completing the previous steps):</span></span>

- <span data-ttu-id="00021-173">Twitter API 키 (5 단계에서 가져옴)</span><span class="sxs-lookup"><span data-stu-id="00021-173">Twitter API Key (obtained in Step 5)</span></span>
- <span data-ttu-id="00021-174">Twitter API 비밀 키 (5 단계에서 가져옴)</span><span class="sxs-lookup"><span data-stu-id="00021-174">Twitter API Secret Key (obtained in Step 5)</span></span>
- <span data-ttu-id="00021-175">Twitter 액세스 토큰 (5 단계에서 가져옴)</span><span class="sxs-lookup"><span data-stu-id="00021-175">Twitter Access Token (obtained in Step 5)</span></span>
- <span data-ttu-id="00021-176">Twitter 액세스 토큰 암호 (5 단계에서 가져옴)</span><span class="sxs-lookup"><span data-stu-id="00021-176">Twitter Access Token Secret (obtained in Step 5)</span></span>
- <span data-ttu-id="00021-177">Azure Active Directory 응용 프로그램 ID (2 단계에서 가져온 AAD 응용 프로그램 ID)</span><span class="sxs-lookup"><span data-stu-id="00021-177">Azure Active Directory application ID (the AAD application ID obtained in Step 2)</span></span>
- <span data-ttu-id="00021-178">Azure Active Directory 응용 프로그램 비밀 (2 단계에서 얻은 AAD 응용 프로그램 암호)</span><span class="sxs-lookup"><span data-stu-id="00021-178">Azure Active Directory application secret (the AAD application secret obtained in Step 2)</span></span>
- <span data-ttu-id="00021-179">Azure Active Directory 응용 프로그램 Uri (2 단계에서 가져온 AAD 응용 프로그램 Uri (예:`https://microsoft.onmicrosoft.com/2688yu6n-12q3-23we-e3ee-121111123213)`</span><span class="sxs-lookup"><span data-stu-id="00021-179">Azure Active Directory application Uri (the AAD application Uri obtained in Step 2; for example, `https://microsoft.onmicrosoft.com/2688yu6n-12q3-23we-e3ee-121111123213)`</span></span>

## <a name="step-7-set-up-a-custom-connector-in-the-security--compliance-center"></a><span data-ttu-id="00021-180">7 단계: 보안 & 준수 센터에서 사용자 지정 커넥터 설정</span><span class="sxs-lookup"><span data-stu-id="00021-180">Step 7: Set up a custom connector in the Security & Compliance Center</span></span>

<span data-ttu-id="00021-181">마지막 단계는 조직의 Twitter 계정에서 Office 365의 지정 된 사서함으로 데이터를 가져오는 사용자 지정 커넥터를 보안 & 준수 센터에 설정 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="00021-181">The final step is to set up the custom connector in the Security & Compliance Center that imports data from your organization's Twitter account to a specified mailbox in Office 365.</span></span> <span data-ttu-id="00021-182">이 단계를 성공적으로 완료 하면 Office 365 가져오기 서비스가 Twitter에서 Office 365로 데이터 가져오기를 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="00021-182">After you successfully complete this step, the Office 365 Import service will start importing data from Twitter to Office 365.</span></span> 

<span data-ttu-id="00021-183">단계별 지침은 [보안 및 준수 센터에서 7 단계: 사용자 지정 커넥터 설정](deploy-twitter-connector.md#step-7-set-up-a-custom-connector-in-the-security-and-compliance-center)를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="00021-183">For step-by-step instructions, see [Step 7: Set up a custom connector in the security and compliance center](deploy-twitter-connector.md#step-7-set-up-a-custom-connector-in-the-security-and-compliance-center).</span></span> 

<span data-ttu-id="00021-184">단계별 지침에 따라이 단계를 완료 하는 동안 다음 정보를 제공 합니다 (단계 완료 후 텍스트 파일로 복사).</span><span class="sxs-lookup"><span data-stu-id="00021-184">During the completion of this step (by following the step-by-step instructions), you'll provide the following information (that you've copied to a text file after completing the steps).</span></span>

- <span data-ttu-id="00021-185">Azure app service URL (예를 들어, `https://twitterconnector.azurewebsites.net`4 단계에서 가져옴)</span><span class="sxs-lookup"><span data-stu-id="00021-185">Azure app service URL (obtained in Step 4; for example, `https://twitterconnector.azurewebsites.net`)</span></span>
- <span data-ttu-id="00021-186">APISecretKey (4 단계에서 만든 것)</span><span class="sxs-lookup"><span data-stu-id="00021-186">APISecretKey (that you created in Step 4)</span></span>
