---
title: Twitter 데이터를 보관하는 커넥터 배포
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
ROBOTS: NOINDEX, NOFOLLOW
description: 관리자는 Twitter 데이터를 가져오고 Microsoft 365로 보관하는 기본 커넥터를 설정할 수 있습니다. 이 데이터를 Microsoft 365로 가져온 후 법적 보존, 콘텐츠 검색 및 보존 정책과 같은 준수 기능을 사용하여 조직의 Twitter 데이터의 거버넌스를 관리할 수 있습니다.
ms.openlocfilehash: 0dd996802964b2a2fc58d26e23af57193c89ee8c
ms.sourcegitcommit: 6fc6aaa2b7610e148f41018abd229e3c55b2f3d0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/10/2020
ms.locfileid: "49619914"
---
# <a name="deploy-a-connector-to-archive-twitter-data"></a><span data-ttu-id="dfab1-104">Twitter 데이터를 보관하는 커넥터 배포</span><span class="sxs-lookup"><span data-stu-id="dfab1-104">Deploy a connector to archive Twitter data</span></span>

<span data-ttu-id="dfab1-105">이 문서에는 Office 365 가져오기 서비스를 사용하여 조직의 Twitter 계정에서 Microsoft 365로 데이터를 가져오는 커넥터를 배포하는 단계별 프로세스가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dfab1-105">This article contains the step-by-step process to deploy a connector that uses the Office 365 Import service to import data from your organization's Twitter account to Microsoft 365.</span></span> <span data-ttu-id="dfab1-106">이 프로세스에 대한 개략적인 개요와 Twitter 커넥터를 배포하는 데 필요한 필수 구성 사항 목록을 확인하려면 Twitter 데이터를 보관할 커넥터 [설정을 참조하세요. ](archive-twitter-data-with-sample-connector.md)</span><span class="sxs-lookup"><span data-stu-id="dfab1-106">For a high-level overview of this process and a list of prerequisites required to deploy a Twitter connector, see [Set up a connector to archive Twitter data ](archive-twitter-data-with-sample-connector.md).</span></span> 

## <a name="step-1-create-an-app-in-azure-active-directory"></a><span data-ttu-id="dfab1-107">1단계: Azure Active Directory에서 앱 만들기</span><span class="sxs-lookup"><span data-stu-id="dfab1-107">Step 1: Create an app in Azure Active Directory</span></span>

1. <span data-ttu-id="dfab1-108">이동하여 전역 관리자 계정의 자격 <https://portal.azure.com> 증명을 사용하여 로그인합니다.</span><span class="sxs-lookup"><span data-stu-id="dfab1-108">Go to <https://portal.azure.com> and sign in using the credentials of a global admin account.</span></span>

   ![Azure에 로그인](../media/TCimage01.png)

2. <span data-ttu-id="dfab1-110">왼쪽 탐색 창에서 **Azure Active Directory를 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="dfab1-110">In the left navigation pane, click **Azure Active Directory**.</span></span>

   ![Azure Active Directory로 이동](../media/TCimage02.png)

3. <span data-ttu-id="dfab1-112">왼쪽 탐색 창에서 앱 등록(미리 **보기)을** 클릭한 다음 새 **등록을 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="dfab1-112">In the left navigation pane, click **App registrations (Preview)** and then click **New registration**.</span></span>

   ![새 앱 등록 만들기](../media/TCimage03.png)

4. <span data-ttu-id="dfab1-114">응용 프로그램을 등록합니다.</span><span class="sxs-lookup"><span data-stu-id="dfab1-114">Register the application.</span></span> <span data-ttu-id="dfab1-115">리디렉션 **URI(선택 사항)의** 응용 프로그램 유형 드롭다운 목록에서 웹을 선택한 다음  `https://portal.azure.com` URI의 상자에 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="dfab1-115">Under **Redirect URI (optional)**, select **Web** in the application type dropdown list and then type `https://portal.azure.com` in the box for the URI.</span></span>

   ![<span data-ttu-id="dfab1-116">리디렉션 https://portal.azure.com URI에 대한 형식</span><span class="sxs-lookup"><span data-stu-id="dfab1-116">Type https://portal.azure.com for the redirect URI</span></span> ](../media/TCimage04.png)

5. <span data-ttu-id="dfab1-117">응용 **프로그램(클라이언트) ID** 및 **디렉터리(테넌트) ID를** 복사하여 텍스트 파일 또는 기타 안전한 위치에 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="dfab1-117">Copy the **Application (client) ID** and **Directory (tenant) ID** and save them to a text file or other safe location.</span></span> <span data-ttu-id="dfab1-118">이후 단계에서 이러한 IDS를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dfab1-118">You use these IDs in later steps.</span></span>

    ![응용 프로그램 ID 및 디렉터리 ID 복사 및 저장](../media/TCimage05.png)

6. <span data-ttu-id="dfab1-120">Go to **Certificates & secrets for the new app** and under Client **secrets** click **New client secret.**</span><span class="sxs-lookup"><span data-stu-id="dfab1-120">Go to **Certificates & secrets for the new app** and under **Client secrets** click **New client secret**.</span></span>

   ![새 클라이언트 비밀 만들기](../media/TCimage06.png)

7. <span data-ttu-id="dfab1-122">새 비밀을 만드시다.</span><span class="sxs-lookup"><span data-stu-id="dfab1-122">Create a new secret.</span></span> <span data-ttu-id="dfab1-123">설명 상자에 비밀을 입력한 다음 만료 기간을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="dfab1-123">In the description box, type the secret and then choose an expiration period.</span></span> 

   ![비밀을 입력하고 만료 기간 선택](../media/TCimage08.png)

8. <span data-ttu-id="dfab1-125">비밀 값을 복사하여 텍스트 파일 또는 다른 저장 위치에 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="dfab1-125">Copy the value of the secret and save it to a text file or other storage location.</span></span> <span data-ttu-id="dfab1-126">이후 단계에서 사용하는 AAD 응용 프로그램 비밀입니다.</span><span class="sxs-lookup"><span data-stu-id="dfab1-126">This is the AAD application secret that you use in later steps.</span></span>

   ![비밀 복사 및 저장](../media/TCimage09.png)


## <a name="step-2-deploy-the-connector-web-service-from-github-to-your-azure-account"></a><span data-ttu-id="dfab1-128">2단계: GitHub에서 Azure 계정으로 커넥터 웹 서비스 배포</span><span class="sxs-lookup"><span data-stu-id="dfab1-128">Step 2: Deploy the connector web service from GitHub to your Azure account</span></span>

1. <span data-ttu-id="dfab1-129">이 [GitHub 사이트로](https://github.com/microsoft/m365-sample-twitter-connector-csharp-aspnet) 이동하여 **Azure에 배포를 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="dfab1-129">Go to [this GitHub site](https://github.com/microsoft/m365-sample-twitter-connector-csharp-aspnet) and click **Deploy to Azure**.</span></span>

    ![Azure 홈 페이지로 이동](../media/FBCimage11.png)

2. <span data-ttu-id="dfab1-131">**Azure에 배포를 클릭하면** 사용자 지정 템플릿 페이지를 사용하여 Azure Portal로 리디렉션됩니다.</span><span class="sxs-lookup"><span data-stu-id="dfab1-131">After you click **Deploy to Azure**, you will be redirected to an Azure portal with a custom template page.</span></span> <span data-ttu-id="dfab1-132">기본 사항 **및**  설정 세부 정보를 입력하고 구매를 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="dfab1-132">Fill in the **Basics** and **Settings** details and then click **Purchase**.</span></span>

   ![리소스 만들기 및 저장소 계정 유형 클릭](../media/FBCimage12.png)

    - <span data-ttu-id="dfab1-134">**구독:** Twitter 커넥터 웹 서비스를 배포할 Azure 구독을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="dfab1-134">**Subscription:** Select your Azure subscription that you want to deploy the Twitter connector web service to.</span></span>
    
    - <span data-ttu-id="dfab1-135">**리소스 그룹:** 새 리소스 그룹을 선택하거나 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dfab1-135">**Resource group:** Choose or create a new resource group.</span></span> <span data-ttu-id="dfab1-136">리소스 그룹은 Azure 솔루션에 대한 관련 리소스를 보유하는 컨테이너입니다.</span><span class="sxs-lookup"><span data-stu-id="dfab1-136">A resource group is a container that holds related resources for an Azure solution.</span></span>

    - <span data-ttu-id="dfab1-137">**위치:** 위치를 선택하십시오.</span><span class="sxs-lookup"><span data-stu-id="dfab1-137">**Location:** Choose a location.</span></span>

    - <span data-ttu-id="dfab1-138">**웹앱 이름:** 커넥터 웹앱의 고유한 이름을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="dfab1-138">**Web App Name:** Provide a unique name for the connector web app.</span></span> <span data-ttu-id="dfab1-139">Th 이름은 3-18자 사이입니다.</span><span class="sxs-lookup"><span data-stu-id="dfab1-139">Th name must be between 3 and 18 characters in length.</span></span> <span data-ttu-id="dfab1-140">이 이름은 Azure 앱 서비스 URL을 만드는 데 사용됩니다. 예를 들어 **twitterconnector의** 웹 앱 이름을 제공하는 경우 Azure 앱 서비스 URL이 **twitterconnector.azurewebsites.net.**</span><span class="sxs-lookup"><span data-stu-id="dfab1-140">This name is used to create the Azure app service URL; for example, if you provide the Web app name of **twitterconnector** then the Azure app service URL  will be **twitterconnector.azurewebsites.net**.</span></span>
    
    - <span data-ttu-id="dfab1-141">**tenantId:** 1단계에서 Azure Active Directory에서 Facebook 커넥터 앱을 만들고 복사한 Microsoft 365 조직의 테넌트 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="dfab1-141">**tenantId:** The tenant ID of your Microsoft 365 organization that you copied after creating the Facebook connector app in Azure       Active Directory in Step 1.</span></span>
    
   - <span data-ttu-id="dfab1-142">**APISecretKey:** 모든 값을 비밀로 입력할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dfab1-142">**APISecretKey:** You can type any value as the secret.</span></span> <span data-ttu-id="dfab1-143">5단계에서 커넥터 웹앱에 액세스하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="dfab1-143">This is used to access the connector web app in Step 5.</span></span>

3. <span data-ttu-id="dfab1-144">배포가 성공하면 페이지는 다음 스크린샷과 비슷합니다.</span><span class="sxs-lookup"><span data-stu-id="dfab1-144">After the deployment is successful, the page will look similar to the following screenshot:</span></span>

    ![저장소를 클릭한 다음 저장소 계정을 클릭합니다.](../media/FBCimage13.png)

## <a name="step-3-create-the-twitter-app"></a><span data-ttu-id="dfab1-146">3단계: Twitter 앱 만들기</span><span class="sxs-lookup"><span data-stu-id="dfab1-146">Step 3: Create the Twitter app</span></span>

1. <span data-ttu-id="dfab1-147">Go to https://developer.twitter.com , log in using the credentials for the developer account for your organization, and then click **Apps.**</span><span class="sxs-lookup"><span data-stu-id="dfab1-147">Go to https://developer.twitter.com, log in using the credentials for the developer account for your organization, and then click **Apps**.</span></span>

   ![이동하여 https://developer.twitter.com 로그인](../media/TCimage25-5.png)
2. <span data-ttu-id="dfab1-149">앱 **만들기를 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="dfab1-149">Click **Create an app**.</span></span>
   
   ![앱 페이지로 이동하여 앱 만들기](../media/TCimage26.png)

3. <span data-ttu-id="dfab1-151">앱 **세부 정보에서** 응용 프로그램에 대한 정보를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="dfab1-151">Under **App details**, add information about the application.</span></span>

   ![앱에 대한 정보 입력](../media/TCimage27.png)

4. <span data-ttu-id="dfab1-153">Twitter 개발자 대시보드에서 방금 만든 앱을 선택하고 세부 정보를 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="dfab1-153">On the Twitter developer dashboard, select the app that you just created and then click **Details**.</span></span>
   
   ![앱 ID 복사 및 저장](../media/TCimage28.png)

5. <span data-ttu-id="dfab1-155">키 및 **토큰** 탭의 **소비자 API** 키 아래에서 API 키와 API 비밀 키를 모두 복사하여 텍스트 파일 또는 다른 저장 위치에 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="dfab1-155">On the **Keys and tokens** tab, under **Consumer API keys** copy both the API Key and the API secret key and save them to a text file or other storage location.</span></span> <span data-ttu-id="dfab1-156">그런 다음 **만들기를** 클릭하여 액세스 토큰 및 액세스 토큰 비밀을 생성하고 이를 텍스트 파일 또는 다른 저장소 위치에 복사합니다.</span><span class="sxs-lookup"><span data-stu-id="dfab1-156">Then click **Create** to generate an access token and access token secret and copy these to a text file or other storage location.</span></span>
   
   ![API 비밀 키 복사 및 저장](../media/TCimage29.png)

   <span data-ttu-id="dfab1-158">그런 다음 **만들기를** 클릭하여 액세스 토큰 및 액세스 토큰 비밀을 생성하고 이를 텍스트 파일 또는 다른 저장소 위치에 복사합니다.</span><span class="sxs-lookup"><span data-stu-id="dfab1-158">Then click **Create** to generate an access token and an access token secret, and copy these to a text file or other storage location.</span></span>

6. <span data-ttu-id="dfab1-159">사용 권한 **탭을** 클릭하고 다음 스크린샷과 같이 사용 권한을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="dfab1-159">Click the **Permissions** tab and configure the permissions as shown in the following screenshot:</span></span>

   ![사용 권한 구성](../media/TCimage30.png)

7. <span data-ttu-id="dfab1-161">사용 권한 설정을 저장한  후 앱 세부 정보 탭을 클릭한 다음 세부 정보 편집 > **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="dfab1-161">After you save the permission settings, click the **App details** tab, and then click **Edit > Edit details**.</span></span>

   ![앱 세부 정보 편집](../media/TCimage31.png)

8. <span data-ttu-id="dfab1-163">다음 작업을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="dfab1-163">Do the following tasks:</span></span>

   - <span data-ttu-id="dfab1-164">커넥터 앱이 Twitter에 로그인할 수 있도록 허용하려면 확인란을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="dfab1-164">Select the checkbox to allow the connector app to sign in to Twitter.</span></span>
   
   - <span data-ttu-id="dfab1-165">**\<connectorserviceuri> /Views/TwitterOAuth** 형식을 사용하여 OAuth 리디렉션 URI를 추가합니다. 여기서 *connectorserviceuri* 값은 조직의 Azure 앱 서비스 https://twitterconnector.azurewebsites.net/Views/TwitterOAuth URL입니다.</span><span class="sxs-lookup"><span data-stu-id="dfab1-165">Add the OAuth redirect Uri using the following format: **\<connectorserviceuri>/Views/TwitterOAuth**, where the value of *connectorserviceuri* is the Azure app service URL for your organization; for example, https://twitterconnector.azurewebsites.net/Views/TwitterOAuth.</span></span>

    ![커넥터 앱이 Twitter에 로그인하고 OAuth 리디렉션 Uri를 추가하도록 허용](../media/TCimage32.png)

<span data-ttu-id="dfab1-167">Twitter 개발자 앱을 사용할 준비가 완료되었습니다.</span><span class="sxs-lookup"><span data-stu-id="dfab1-167">The Twitter developer app is now ready to use.</span></span>

## <a name="step-4-configure-the-connector-web-app"></a><span data-ttu-id="dfab1-168">4단계: 커넥터 웹앱 구성</span><span class="sxs-lookup"><span data-stu-id="dfab1-168">Step 4: Configure the connector web app</span></span> 

1. <span data-ttu-id="dfab1-169">\<AzureAppResourceName>https:// .azurewebsites.net **(여기서 AzureAppResourceName은** 4단계에서 명명한 Azure 앱 리소스의 이름)로 이동하십시오.</span><span class="sxs-lookup"><span data-stu-id="dfab1-169">Go to https://\<AzureAppResourceName>.azurewebsites.net (where **AzureAppResourceName** is the name of your Azure app resource that you named in Step 4).</span></span> <span data-ttu-id="dfab1-170">예를 들어 이름이 **twitterconnector이면**. https://twitterconnector.azurewebsites.net</span><span class="sxs-lookup"><span data-stu-id="dfab1-170">For example, if the name is **twitterconnector**, go to https://twitterconnector.azurewebsites.net.</span></span> <span data-ttu-id="dfab1-171">앱의 홈 페이지는 다음 스크린샷과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="dfab1-171">The home page of the app looks like the following screenshot:</span></span>

   ![Azure 앱 리소스 페이지로 이동](../media/FBCimage41.png)

2. <span data-ttu-id="dfab1-173">로그인 **페이지를** 표시하려면 구성을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="dfab1-173">Click **Configure** to display a sign in page.</span></span>

   ![로그인 페이지를 표시하도록 구성을 클릭합니다.](../media/FBCimage42.png)

3. <span data-ttu-id="dfab1-175">테넌트 ID 상자에 2단계에서 획득한 테넌트 ID를 입력하거나 붙여넣습니다.</span><span class="sxs-lookup"><span data-stu-id="dfab1-175">In the Tenant Id box, type or paste your tenant Id (that you obtained in Step 2).</span></span> <span data-ttu-id="dfab1-176">암호 상자에 APISecretKey(2단계에서 획득한 APISecretKey)를  입력하거나 붙여넣은 다음 구성 설정 설정을 클릭하여 구성 세부 정보 페이지를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="dfab1-176">In the password box, type or paste the APISecretKey (that you obtained in Step 2), and then click **Set Configuration Settings** to display the configuration details page.</span></span>

   ![테넌트 ID 및 API 비밀 키를 사용하여 로그인](../media/TCimage35.png)

4. <span data-ttu-id="dfab1-178">다음 구성 설정을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="dfab1-178">Enter the following configuration settings</span></span> 

   - <span data-ttu-id="dfab1-179">**Twitter Api 키:** 3단계에서 만든 Twitter 응용 프로그램의 API 키입니다.</span><span class="sxs-lookup"><span data-stu-id="dfab1-179">**Twitter Api Key:** The API key for the Twitter application that you created in Step 3.</span></span>
   
   - <span data-ttu-id="dfab1-180">**Twitter Api 비밀 키:** 3단계에서 만든 Twitter 응용 프로그램의 API 비밀 키입니다.</span><span class="sxs-lookup"><span data-stu-id="dfab1-180">**Twitter Api Secret Key:** The API secret key for the Twitter application that you created in Step 3.</span></span>
   
   - <span data-ttu-id="dfab1-181">**Twitter 액세스 토큰:** 3단계에서 만든 액세스 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="dfab1-181">**Twitter Access Token:** The access token that you created in Step 3.</span></span>
   
   - <span data-ttu-id="dfab1-182">**Twitter 액세스 토큰 비밀:** 3단계에서 만든 액세스 토큰 비밀입니다.</span><span class="sxs-lookup"><span data-stu-id="dfab1-182">**Twitter Access Token Secret:** The access token secret that you created in Step 3.</span></span>
   
   - <span data-ttu-id="dfab1-183">**AAD 응용 프로그램 ID:** 1단계에서 만든 Azure Active Directory 앱의 응용 프로그램 ID</span><span class="sxs-lookup"><span data-stu-id="dfab1-183">**AAD Application ID:** The application ID for the Azure Active Directory app that you created in Step 1</span></span>
   
   - <span data-ttu-id="dfab1-184">**AAD 응용 프로그램 비밀:** 1단계에서 만든 APISecretKey 비밀의 값입니다.</span><span class="sxs-lookup"><span data-stu-id="dfab1-184">**AAD Application Secret:** The value for the APISecretKey secret that you created in Step 1.</span></span>

5. <span data-ttu-id="dfab1-185">연결선 **설정을** 저장하려면 저장을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="dfab1-185">Click **Save** to save the connector settings.</span></span>

## <a name="step-5-set-up-a-twitter-connector-in-the-microsoft-365-compliance-center"></a><span data-ttu-id="dfab1-186">5단계: Microsoft 365 규정 준수 센터에서 Twitter 커넥터 설정</span><span class="sxs-lookup"><span data-stu-id="dfab1-186">Step 5: Set up a Twitter connector in the Microsoft 365 compliance center</span></span>

1. <span data-ttu-id="dfab1-187">Go to [https://compliance.microsoft.com](https://compliance.microsoft.com) and then click Data **connectors** in the left nav.</span><span class="sxs-lookup"><span data-stu-id="dfab1-187">Go to [https://compliance.microsoft.com](https://compliance.microsoft.com) and then click **Data connectors** in the left nav.</span></span>

2. <span data-ttu-id="dfab1-188">Twitter **아래의 데이터 커넥터** **페이지에서 보기를** **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="dfab1-188">On the **Data connectors** page under **Twitter**, click **View**.</span></span>

3. <span data-ttu-id="dfab1-189">Twitter **페이지에서** 커넥터 **추가를 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="dfab1-189">On the **Twitter** page, click **Add connector**.</span></span>

4. <span data-ttu-id="dfab1-190">서비스 약관 **페이지에서** 수락을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="dfab1-190">On the **Terms of service** page, click **Accept**.</span></span>

5. <span data-ttu-id="dfab1-191">커넥터 **앱의** 자격 증명 추가 페이지에서 다음 정보를 입력하고 연결 유효성 검사를 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="dfab1-191">On the **Add credentials for your connector app** page, enter the following information and then click **Validate connection**.</span></span>

   ![커넥터 앱 자격 증명 입력](../media/TCimage38.png)

    - <span data-ttu-id="dfab1-193">이름 **상자에** 연결선의 이름(예: Twitter 도움말 **핸들)을 입력합니다.**</span><span class="sxs-lookup"><span data-stu-id="dfab1-193">In the **Name** box, type a name for the connector, such as **Twitter help handle**.</span></span>
    
    - <span data-ttu-id="dfab1-194">커넥터 **URL 상자에** Azure 앱 서비스 URL을 입력하거나 붙여넣습니다. 예를 들면 `https://twitterconnector.azurewebsites.net` 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="dfab1-194">In the **Connector URL** box, type or paste the Azure app service URL; for example `https://twitterconnector.azurewebsites.net`.</span></span>
    
    - <span data-ttu-id="dfab1-195">암호 **상자에** 2단계에서 만든 APISecretKey 값을 입력하거나 붙여넣습니다.</span><span class="sxs-lookup"><span data-stu-id="dfab1-195">In the **Password** box, type or paste the value of the APISecretKey that you created in Step 2.</span></span>
    
    - <span data-ttu-id="dfab1-196">Azure **앱 ID** 상자에 1단계에서 획득한 Azure 응용 프로그램 앱 ID(클라이언트 ID라고도함)의 값을 입력하거나 붙여넣습니다. </span><span class="sxs-lookup"><span data-stu-id="dfab1-196">In the **Azure App ID** box, type or paste the value of the Azure Application App Id (also called the *client ID*) that you obtained in Step 1.</span></span>

6. <span data-ttu-id="dfab1-197">연결의 유효성을 검사한 후 다음을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="dfab1-197">After the connection is successfully validated, click **Next**.</span></span>

7. <span data-ttu-id="dfab1-198">Microsoft **365** 인증 페이지에서 APISecretKey를 다시 입력하거나 붙여넣은 다음 **로그인 웹앱을 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="dfab1-198">On the **Authorize Microsoft 365 to import data** page, type or paste the APISecretKey again and then click  **Login web app**.</span></span>

8. <span data-ttu-id="dfab1-199">Twitter로 **로그인을 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="dfab1-199">Click **Login with Twitter**.</span></span>

9. <span data-ttu-id="dfab1-200">Twitter 로그인 페이지에서 조직의 Twitter 계정에 대한 자격 증명을 사용하여 로그인합니다.</span><span class="sxs-lookup"><span data-stu-id="dfab1-200">On the Twitter sign in page, sign in using the credentials for your organization's Twitter account.</span></span>

   ![Twitter 계정에 로그인](../media/TCimage42.png)

   <span data-ttu-id="dfab1-202">로그인하면 Twitter 페이지에 "Twitter Connector Job Successfully set up"의 메시지가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="dfab1-202">After you sign in, the Twitter page will display the following message, "Twitter Connector Job Successfully set up."</span></span>

10. <span data-ttu-id="dfab1-203">**계속을** 클릭하여 Twitter 커넥터 설정을 완료합니다.</span><span class="sxs-lookup"><span data-stu-id="dfab1-203">Click **Continue** to complete setting up the Twitter connector.</span></span>

11. <span data-ttu-id="dfab1-204">필터 **설정 페이지에서** 특정 연령의 항목을 처음에 가져오는 필터를 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dfab1-204">On the **Set filters** page, you can apply a filter to initially import items that are a certain age.</span></span> <span data-ttu-id="dfab1-205">연령을 선택하고 다음을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="dfab1-205">Select an age, and then click **Next**.</span></span>

12. <span data-ttu-id="dfab1-206">저장소 **위치** 선택 페이지에서 Twitter 항목을 가져올 Microsoft 365 사서함의 전자 메일 주소를 입력하고 다음을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="dfab1-206">On the **Choose storage location** page, type the email address of Microsoft 365 mailbox that the Twitter items will be imported to, and then click **Next**.</span></span>

13. <span data-ttu-id="dfab1-207">**다음을** 클릭하여 커넥터 설정을 검토한 다음 **마친을** 클릭하여 커넥터 설정을 완료합니다.</span><span class="sxs-lookup"><span data-stu-id="dfab1-207">Click **Next** to review the connector settings and then click **Finish** to complete the connector setup.</span></span>

14. <span data-ttu-id="dfab1-208">준수 센터에서 데이터 커넥터  페이지로 이동한 다음  커넥터 탭을 클릭하여 가져오기 프로세스의 진행률을 봐야 합니다.</span><span class="sxs-lookup"><span data-stu-id="dfab1-208">In the compliance center, go to the **Data connectors** page, and click the **Connectors** tab to see the progress of the import process.</span></span>
