---
title: Twitter 데이터를 보관 하기 위한 커넥터 배포
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
description: 관리자는 네이티브 커넥터를 설정 하 여 Twitter 데이터를 가져오고 Microsoft 365로 보관할 수 있습니다. 이 데이터를 Microsoft 365로 가져온 후 법적 보존, 콘텐츠 검색 및 보존 정책과 같은 규정 준수 기능을 사용 하 여 조직의 Twitter 데이터에 대 한 관리를 관리할 수 있습니다.
ms.openlocfilehash: 01c4901544e47cd1c361a132e144440f00bd8504
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/22/2020
ms.locfileid: "48200831"
---
# <a name="deploy-a-connector-to-archive-twitter-data"></a><span data-ttu-id="02f09-104">Twitter 데이터를 보관 하기 위한 커넥터 배포</span><span class="sxs-lookup"><span data-stu-id="02f09-104">Deploy a connector to archive Twitter data</span></span>

<span data-ttu-id="02f09-105">이 문서에는 Office 365 가져오기 서비스를 사용 하 여 조직의 Twitter 계정에서 Microsoft 365로 데이터를 가져오는 커넥터를 배포 하는 단계별 프로세스가 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="02f09-105">This article contains the step-by-step process to deploy a connector that uses the Office 365 Import service to import data from your organization's Twitter account to Microsoft 365.</span></span> <span data-ttu-id="02f09-106">이 프로세스에 대 한 간략 한 개요와 Twitter 커넥터를 배포 하는 데 필요한 필수 구성 요소 목록은 [twitter 데이터를 보관할 커넥터 설정을 ](archive-twitter-data-with-sample-connector.md)참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="02f09-106">For a high-level overview of this process and a list of prerequisites required to deploy a Twitter connector, see [Set up a connector to archive Twitter data ](archive-twitter-data-with-sample-connector.md).</span></span> 

## <a name="step-1-create-an-app-in-azure-active-directory"></a><span data-ttu-id="02f09-107">1 단계: Azure Active Directory에 앱 만들기</span><span class="sxs-lookup"><span data-stu-id="02f09-107">Step 1: Create an app in Azure Active Directory</span></span>

1. <span data-ttu-id="02f09-108">로 이동 하 <https://portal.azure.com> 고 전역 관리자 계정의 자격 증명을 사용 하 여 로그인 합니다.</span><span class="sxs-lookup"><span data-stu-id="02f09-108">Go to <https://portal.azure.com> and sign in using the credentials of a global admin account.</span></span>

   ![Azure에 로그인 합니다.](../media/TCimage01.png)

2. <span data-ttu-id="02f09-110">왼쪽 탐색 창에서 **Azure Active Directory**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="02f09-110">In the left navigation pane, click **Azure Active Directory**.</span></span>

   ![Azure Active Directory로 이동](../media/TCimage02.png)

3. <span data-ttu-id="02f09-112">왼쪽 탐색 창에서 **앱 등록 (미리 보기)** 을 클릭 하 고 **새 등록**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="02f09-112">In the left navigation pane, click **App registrations (Preview)** and then click **New registration**.</span></span>

   ![새 앱 등록 만들기](../media/TCimage03.png)

4. <span data-ttu-id="02f09-114">응용 프로그램을 등록 합니다.</span><span class="sxs-lookup"><span data-stu-id="02f09-114">Register the application.</span></span> <span data-ttu-id="02f09-115">**Uri 리디렉션 (선택 사항)** 아래의 응용 프로그램 형식 드롭다운 목록에서 **웹** 을 선택한 다음 `https://portal.azure.com` URI에 대 한 상자에 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="02f09-115">Under **Redirect URI (optional)**, select **Web** in the application type dropdown list and then type `https://portal.azure.com` in the box for the URI.</span></span>

   ![<span data-ttu-id="02f09-116">https://portal.azure.com리디렉션 URI의 유형입니다.</span><span class="sxs-lookup"><span data-stu-id="02f09-116">Type https://portal.azure.com for the redirect URI</span></span> ](../media/TCimage04.png)

5. <span data-ttu-id="02f09-117">**응용 프로그램 (클라이언트) id** 및 **디렉터리 (테 넌 트) id** 를 복사한 다음 텍스트 파일 또는 기타 안전한 위치에 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="02f09-117">Copy the **Application (client) ID** and **Directory (tenant) ID** and save them to a text file or other safe location.</span></span> <span data-ttu-id="02f09-118">이후 단계에서 이러한 Id를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="02f09-118">You use these IDs in later steps.</span></span>

    ![응용 프로그램 Id 및 디렉터리 Id 복사 및 저장](../media/TCimage05.png)

6. <span data-ttu-id="02f09-120">**새 앱에 대 한 인증서 & 비밀** 으로 이동 하 고 **클라이언트 암호** 에서 **새 클라이언트 암호**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="02f09-120">Go to **Certificates & secrets for the new app** and under **Client secrets** click **New client secret**.</span></span>

   ![새 클라이언트 암호 만들기](../media/TCimage06.png)

7. <span data-ttu-id="02f09-122">새 암호를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="02f09-122">Create a new secret.</span></span> <span data-ttu-id="02f09-123">설명 상자에 암호를 입력 하 고 만료 기간을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="02f09-123">In the description box, type the secret and then choose an expiration period.</span></span> 

   ![암호 입력 및 만료 기간 선택](../media/TCimage08.png)

8. <span data-ttu-id="02f09-125">비밀 값을 복사 하 여 텍스트 파일 또는 기타 저장 위치에 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="02f09-125">Copy the value of the secret and save it to a text file or other storage location.</span></span> <span data-ttu-id="02f09-126">이는 이후 단계에서 사용 하는 AAD 응용 프로그램 비밀입니다.</span><span class="sxs-lookup"><span data-stu-id="02f09-126">This is the AAD application secret that you use in later steps.</span></span>

   ![암호 복사 및 저장](../media/TCimage09.png)


## <a name="step-2-deploy-the-connector-web-service-from-github-to-your-azure-account"></a><span data-ttu-id="02f09-128">2 단계: GitHub에서 Azure 계정으로 커넥터 웹 서비스 배포</span><span class="sxs-lookup"><span data-stu-id="02f09-128">Step 2: Deploy the connector web service from GitHub to your Azure account</span></span>

1. <span data-ttu-id="02f09-129">[이 GitHub 사이트로](https://github.com/microsoft/m365-sample-twitter-connector-csharp-aspnet) 이동한 후 **Azure에 배포를**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="02f09-129">Go to [this GitHub site](https://github.com/microsoft/m365-sample-twitter-connector-csharp-aspnet) and click **Deploy to Azure**.</span></span>

    ![Azure 홈 페이지로 이동](../media/FBCimage11.png)

2. <span data-ttu-id="02f09-131">**Azure에 배포**를 클릭 하면 사용자 지정 서식 파일 페이지를 사용 하 여 azure 포털로 리디렉션됩니다.</span><span class="sxs-lookup"><span data-stu-id="02f09-131">After you click **Deploy to Azure**, you will be redirected to an Azure portal with a custom template page.</span></span> <span data-ttu-id="02f09-132">**기본 사항** 및 **설정** 세부 정보를 입력 하 고 **구매**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="02f09-132">Fill in the **Basics** and **Settings** details and then click **Purchase**.</span></span>

   ![리소스 만들기 및 저장소 계정 입력을 클릭 합니다.](../media/FBCimage12.png)

    - <span data-ttu-id="02f09-134">**구독:** Twitter 커넥터 웹 서비스를 배포 하려는 Azure 구독을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="02f09-134">**Subscription:** Select your Azure subscription that you want to deploy the Twitter connector web service to.</span></span>
    
    - <span data-ttu-id="02f09-135">**리소스 그룹:** 새 리소스 그룹을 선택 하거나 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="02f09-135">**Resource group:** Choose or create a new resource group.</span></span> <span data-ttu-id="02f09-136">리소스 그룹은 Azure 솔루션에 대 한 관련 리소스를 포함 하는 컨테이너입니다.</span><span class="sxs-lookup"><span data-stu-id="02f09-136">A resource group is a container that holds related resources for an Azure solution.</span></span>

    - <span data-ttu-id="02f09-137">**위치:** 위치를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="02f09-137">**Location:** Choose a location.</span></span>

    - <span data-ttu-id="02f09-138">**웹 응용 프로그램 이름:** 커넥터 웹 응용 프로그램의 고유한 이름을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="02f09-138">**Web App Name:** Provide a unique name for the connector web app.</span></span> <span data-ttu-id="02f09-139">Th 이름의 길이는 3에서 18 자 사이 여야 합니다.</span><span class="sxs-lookup"><span data-stu-id="02f09-139">Th name must be between 3 and 18 characters in length.</span></span> <span data-ttu-id="02f09-140">이 이름은 Azure app service URL을 만드는 데 사용 됩니다. 예를 들어, 웹 앱 이름을 **twitterconnector** 로 제공 하는 경우 Azure APP service URL이 **twitterconnector.azurewebsites.net**됩니다.</span><span class="sxs-lookup"><span data-stu-id="02f09-140">This name is used to create the Azure app service URL; for example, if you provide the Web app name of **twitterconnector** then the Azure app service URL  will be **twitterconnector.azurewebsites.net**.</span></span>
    
    - <span data-ttu-id="02f09-141">**tenantId:** 1 단계에서 Azure Active Directory에 Facebook connector 앱을 만든 후 복사한 Microsoft 365 조직의 테 넌 트 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="02f09-141">**tenantId:** The tenant ID of your Microsoft 365 organization that you copied after creating the Facebook connector app in Azure       Active Directory in Step 1.</span></span>
    
   - <span data-ttu-id="02f09-142">**APISecretKey:** 임의의 값을 비밀로 입력할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="02f09-142">**APISecretKey:** You can type any value as the secret.</span></span> <span data-ttu-id="02f09-143">이는 5 단계에서 커넥터 웹 앱에 액세스 하는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="02f09-143">This is used to access the connector web app in Step 5.</span></span>

3. <span data-ttu-id="02f09-144">배포가 성공적으로 완료 되 면 페이지는 다음 스크린샷과 유사 하 게 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="02f09-144">After the deployment is successful, the page will look similar to the following screenshot:</span></span>

    ![저장소를 클릭 한 다음 저장소 계정을 클릭 합니다.](../media/FBCimage13.png)

## <a name="step-3-create-the-twitter-app"></a><span data-ttu-id="02f09-146">3 단계: Twitter 응용 프로그램 만들기</span><span class="sxs-lookup"><span data-stu-id="02f09-146">Step 3: Create the Twitter app</span></span>

1. <span data-ttu-id="02f09-147">으로 이동 하 고 https://developer.twitter.com 조직의 개발자 계정에 대 한 자격 증명을 사용 하 여 로그인 한 다음 **앱**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="02f09-147">Go to https://developer.twitter.com, log in using the credentials for the developer account for your organization, and then click **Apps**.</span></span>

   ![으로 이동 https://developer.twitter.com 하 여 로그인 합니다.](../media/TCimage25-5.png)
2. <span data-ttu-id="02f09-149">**앱 만들기**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="02f09-149">Click **Create an app**.</span></span>
   
   ![앱을 만들려면 앱 페이지로 이동](../media/TCimage26.png)

3. <span data-ttu-id="02f09-151">**앱 세부 정보**에서 응용 프로그램에 대 한 정보를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="02f09-151">Under **App details**, add information about the application.</span></span>

   ![앱에 대 한 정보 입력](../media/TCimage27.png)

4. <span data-ttu-id="02f09-153">Twitter 개발자 대시보드에서 방금 만든 앱을 선택 하 고 **세부 정보**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="02f09-153">On the Twitter developer dashboard, select the app that you just created and then click **Details**.</span></span>
   
   ![앱 Id 복사 및 저장](../media/TCimage28.png)

5. <span data-ttu-id="02f09-155">**키 및 토큰** 탭의 **Consumer api** 키 아래에서 api 키와 api 비밀 키를 모두 복사 하 여 텍스트 파일 또는 기타 저장 위치에 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="02f09-155">On the **Keys and tokens** tab, under **Consumer API keys** copy both the API Key and the API secret key and save them to a text file or other storage location.</span></span> <span data-ttu-id="02f09-156">그런 다음 **만들기** 를 클릭 하 여 액세스 토큰 및 액세스 토큰 암호를 생성 하 고이를 텍스트 파일 또는 기타 저장소 위치로 복사 합니다.</span><span class="sxs-lookup"><span data-stu-id="02f09-156">Then click **Create** to generate an access token and access token secret and copy these to a text file or other storage location.</span></span>
   
   ![API 비밀 키에 복사 및 저장](../media/TCimage29.png)

   <span data-ttu-id="02f09-158">그런 다음 **만들기** 를 클릭 하 여 액세스 토큰과 액세스 토큰 비밀을 생성 한 다음 텍스트 파일 또는 기타 저장소 위치로 복사 합니다.</span><span class="sxs-lookup"><span data-stu-id="02f09-158">Then click **Create** to generate an access token and an access token secret, and copy these to a text file or other storage location.</span></span>

6. <span data-ttu-id="02f09-159">**사용 권한** 탭을 클릭 하 고 다음 스크린샷에 표시 된 대로 사용 권한을 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="02f09-159">Click the **Permissions** tab and configure the permissions as shown in the following screenshot:</span></span>

   ![사용 권한 구성](../media/TCimage30.png)

7. <span data-ttu-id="02f09-161">권한 설정을 저장 한 후에는 **앱 세부 정보** 탭을 클릭 한 다음 **세부 정보 편집 >** 편집을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="02f09-161">After you save the permission settings, click the **App details** tab, and then click **Edit > Edit details**.</span></span>

   ![앱 세부 정보 편집](../media/TCimage31.png)

8. <span data-ttu-id="02f09-163">다음 작업을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="02f09-163">Do the following tasks:</span></span>

   - <span data-ttu-id="02f09-164">커넥터 앱이 Twitter에 로그인 하도록 허용 하는 확인란을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="02f09-164">Select the checkbox to allow the connector app to sign in to Twitter.</span></span>
   
   - <span data-ttu-id="02f09-165">다음 형식을 사용 하 여 OAuth 리디렉션 Uri를 추가 합니다 (예: \*\* \<connectorserviceuri> /Views/TwitterOAuth\*\*). *connectorserviceuri* 의 값은 조직의 Azure app 서비스 URL입니다. https://twitterconnector.azurewebsites.net/Views/TwitterOAuth</span><span class="sxs-lookup"><span data-stu-id="02f09-165">Add the OAuth redirect Uri using the following format: **\<connectorserviceuri>/Views/TwitterOAuth**, where the value of *connectorserviceuri* is the Azure app service URL for your organization; for example, https://twitterconnector.azurewebsites.net/Views/TwitterOAuth.</span></span>

    ![커넥터 앱이 Twitter에 로그인 하 고 OAuth 리디렉션 Uri를 추가할 수 있도록 허용](../media/TCimage32.png)

<span data-ttu-id="02f09-167">이제 Twitter 개발자 앱을 사용할 준비가 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="02f09-167">The Twitter developer app is now ready to use.</span></span>

## <a name="step-4-configure-the-connector-web-app"></a><span data-ttu-id="02f09-168">4 단계: 커넥터 웹 응용 프로그램 구성</span><span class="sxs-lookup"><span data-stu-id="02f09-168">Step 4: Configure the connector web app</span></span> 

1. <span data-ttu-id="02f09-169">Https:// \<AzureAppResourceName> (여기서 **AzureAppResourceName** 은 4 단계에서 명명 한 Azure 앱 리소스의 이름)으로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="02f09-169">Go to https://\<AzureAppResourceName>.azurewebsites.net (where **AzureAppResourceName** is the name of your Azure app resource that you named in Step 4).</span></span> <span data-ttu-id="02f09-170">예를 들어 이름이 **twitterconnector**인 경우로 이동 https://twitterconnector.azurewebsites.net 합니다.</span><span class="sxs-lookup"><span data-stu-id="02f09-170">For example, if the name is **twitterconnector**, go to https://twitterconnector.azurewebsites.net.</span></span> <span data-ttu-id="02f09-171">이 앱의 홈 페이지는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="02f09-171">The home page of the app looks like the following screenshot:</span></span>

   ![Azure 앱 리소스 페이지로 이동](../media/FBCimage41.png)

2. <span data-ttu-id="02f09-173">**구성을** 클릭 하 여 로그인 페이지를 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="02f09-173">Click **Configure** to display a sign in page.</span></span>

   ![로그인 페이지를 표시 하려면 구성을 클릭 합니다.](../media/FBCimage42.png)

3. <span data-ttu-id="02f09-175">테 넌 트 Id 상자에 2 단계에서 받은 테 넌 트 Id를 입력 하거나 붙여 넣습니다.</span><span class="sxs-lookup"><span data-stu-id="02f09-175">In the Tenant Id box, type or paste your tenant Id (that you obtained in Step 2).</span></span> <span data-ttu-id="02f09-176">암호 상자에 2 단계에서 구한 APISecretKey를 입력 하거나 붙여 넣은 다음 **구성 설정 설정을** 클릭 하 여 구성 세부 정보 페이지를 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="02f09-176">In the password box, type or paste the APISecretKey (that you obtained in Step 2), and then click **Set Configuration Settings** to display the configuration details page.</span></span>

   ![테 넌 트 Id 및 API 비밀 키를 사용 하 여 로그인](../media/TCimage35.png)

4. <span data-ttu-id="02f09-178">다음 구성 설정을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="02f09-178">Enter the following configuration settings</span></span> 

   - <span data-ttu-id="02f09-179">**Twitter Api 키:** 3 단계에서 만든 Twitter 응용 프로그램에 대 한 API 키입니다.</span><span class="sxs-lookup"><span data-stu-id="02f09-179">**Twitter Api Key:** The API key for the Twitter application that you created in Step 3.</span></span>
   
   - <span data-ttu-id="02f09-180">**Twitter Api 비밀 키:** 3 단계에서 만든 Twitter 응용 프로그램에 대 한 API 비밀 키입니다.</span><span class="sxs-lookup"><span data-stu-id="02f09-180">**Twitter Api Secret Key:** The API secret key for the Twitter application that you created in Step 3.</span></span>
   
   - <span data-ttu-id="02f09-181">**Twitter 액세스 토큰:** 3 단계에서 만든 액세스 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="02f09-181">**Twitter Access Token:** The access token that you created in Step 3.</span></span>
   
   - <span data-ttu-id="02f09-182">**Twitter 액세스 토큰 암호:** 3 단계에서 만든 액세스 토큰 비밀입니다.</span><span class="sxs-lookup"><span data-stu-id="02f09-182">**Twitter Access Token Secret:** The access token secret that you created in Step 3.</span></span>
   
   - <span data-ttu-id="02f09-183">**AAD 응용 프로그램 ID:** 1 단계에서 만든 Azure Active Directory 앱의 응용 프로그램 ID</span><span class="sxs-lookup"><span data-stu-id="02f09-183">**AAD Application ID:** The application ID for the Azure Active Directory app that you created in Step 1</span></span>
   
   - <span data-ttu-id="02f09-184">**AAD 응용 프로그램 암호:** 1 단계에서 만든 APISecretKey 암호에 대 한 값입니다.</span><span class="sxs-lookup"><span data-stu-id="02f09-184">**AAD Application Secret:** The value for the APISecretKey secret that you created in Step 1.</span></span>

5. <span data-ttu-id="02f09-185">**저장** 을 클릭 하 여 커넥터 설정을 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="02f09-185">Click **Save** to save the connector settings.</span></span>

## <a name="step-5-set-up-a-twitter-connector-in-the-microsoft-365-compliance-center"></a><span data-ttu-id="02f09-186">5 단계: Microsoft 365 준수 센터에서 Twitter 커넥터 설정</span><span class="sxs-lookup"><span data-stu-id="02f09-186">Step 5: Set up a Twitter connector in the Microsoft 365 compliance center</span></span>

1. <span data-ttu-id="02f09-187">로 이동한 [https://compliance.microsoft.com](https://compliance.microsoft.com) 후 왼쪽 탐색 창에서 **데이터 커넥터** 를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="02f09-187">Go to [https://compliance.microsoft.com](https://compliance.microsoft.com) and then click **Data connectors** in the left nav.</span></span>

2. <span data-ttu-id="02f09-188">**데이터 커넥터** 페이지의 **Twitter**에서 **보기**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="02f09-188">On the **Data connectors** page under **Twitter**, click **View**.</span></span>

3. <span data-ttu-id="02f09-189">**Twitter** 페이지에서 **커넥터 추가**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="02f09-189">On the **Twitter** page, click **Add connector**.</span></span>

4. <span data-ttu-id="02f09-190">**서비스 약관** 페이지에서 **수락**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="02f09-190">On the **Terms of service** page, click **Accept**.</span></span>

5. <span data-ttu-id="02f09-191">**커넥터 응용 프로그램에 대 한 자격 증명 추가** 페이지에서 다음 정보를 입력 한 다음 **연결 유효성 검사**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="02f09-191">On the **Add credentials for your connector app** page, enter the following information and then click **Validate connection**.</span></span>

   ![커넥터 앱 자격 증명 입력](../media/TCimage38.png)

    - <span data-ttu-id="02f09-193">**이름** 상자에 **Twitter 도움말 핸들과**같은 커넥터의 이름을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="02f09-193">In the **Name** box, type a name for the connector, such as **Twitter help handle**.</span></span>
    
    - <span data-ttu-id="02f09-194">**커넥터 URL** 상자에 Azure 앱 서비스 URL을 입력 하거나 붙여넣습니다. 예를 `https://twitterconnector.azurewebsites.net` 들어</span><span class="sxs-lookup"><span data-stu-id="02f09-194">In the **Connector URL** box, type or paste the Azure app service URL; for example `https://twitterconnector.azurewebsites.net`.</span></span>
    
    - <span data-ttu-id="02f09-195">**암호** 상자에 2 단계에서 만든 APISecretKey의 값을 입력 하거나 붙여넣습니다.</span><span class="sxs-lookup"><span data-stu-id="02f09-195">In the **Password** box, type or paste the value of the APISecretKey that you created in Step 2.</span></span>
    
    - <span data-ttu-id="02f09-196">**Azure 앱 id** 상자에 1 단계에서 구한 Azure 응용 프로그램 id ( *클라이언트 ID*라고도 함)의 값을 입력 하거나 붙여넣습니다.</span><span class="sxs-lookup"><span data-stu-id="02f09-196">In the **Azure App ID** box, type or paste the value of the Azure Application App Id (also called the *client ID*) that you obtained in Step 1.</span></span>

6. <span data-ttu-id="02f09-197">연결이 성공적으로 확인 되 면 **다음**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="02f09-197">After the connection is successfully validated, click **Next**.</span></span>

7. <span data-ttu-id="02f09-198">**Microsoft 365에서 데이터를 가져올 수 있는 권한을 부여** 합니다 페이지에서 APISecretKey를 다시 입력 하거나 붙여 넣은 다음 **로그인 웹 앱**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="02f09-198">On the **Authorize Microsoft 365 to import data** page, type or paste the APISecretKey again and then click  **Login web app**.</span></span>

8. <span data-ttu-id="02f09-199">**Twitter를 사용 하 여 로그인을**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="02f09-199">Click **Login with Twitter**.</span></span>

9. <span data-ttu-id="02f09-200">Twitter 로그인 페이지에서 조직의 Twitter 계정에 대 한 자격 증명을 사용 하 여 로그인 합니다.</span><span class="sxs-lookup"><span data-stu-id="02f09-200">On the Twitter sign in page, sign in using the credentials for your organization's Twitter account.</span></span>

   ![Twitter 계정에 로그인 합니다.](../media/TCimage42.png)

   <span data-ttu-id="02f09-202">로그인 하면 Twitter 페이지에 "Twitter 커넥터 작업을 설정 했습니다." 라는 메시지가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="02f09-202">After you sign in, the Twitter page will display the following message, "Twitter Connector Job Successfully set up."</span></span>

10. <span data-ttu-id="02f09-203">**계속** 을 클릭 하 여 Twitter 커넥터 설정을 완료 합니다.</span><span class="sxs-lookup"><span data-stu-id="02f09-203">Click **Continue** to complete setting up the Twitter connector.</span></span>

11. <span data-ttu-id="02f09-204">**필터 설정** 페이지에서 특정 기간에 해당 하는 항목을 처음 가져올 때 필터를 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="02f09-204">On the **Set filters** page, you can apply a filter to initially import items that are a certain age.</span></span> <span data-ttu-id="02f09-205">보존 기간을 선택 하 고 **다음**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="02f09-205">Select an age, and then click **Next**.</span></span>

12. <span data-ttu-id="02f09-206">**저장 위치 선택** 페이지에서 Twitter 항목을 가져올 Microsoft 365 사서함의 전자 메일 주소를 입력 하 고 **다음**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="02f09-206">On the **Choose storage location** page, type the email address of Microsoft 365 mailbox that the Twitter items will be imported to, and then click **Next**.</span></span>

13. <span data-ttu-id="02f09-207">**관리자 동의 제공**에서 **동의 제공** 을 클릭 한 다음 단계를 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="02f09-207">On the **Provide admin consent**, click **Provide consent** and then follow the steps.</span></span> <span data-ttu-id="02f09-208">조직의 데이터에 액세스 하려면 Office 365 가져오기 서비스에 대 한 동의를 제공 하는 전역 관리자 여야 합니다.</span><span class="sxs-lookup"><span data-stu-id="02f09-208">You must be a global admin to provide consent for the Office 365 Import service to access data in your organization.</span></span>

14. <span data-ttu-id="02f09-209">**다음** 을 클릭 하 여 커넥터 설정을 검토 한 다음 **마침을** 클릭 하 여 커넥터 설치를 완료 합니다.</span><span class="sxs-lookup"><span data-stu-id="02f09-209">Click **Next** to review the connector settings and then click **Finish** to complete the connector setup.</span></span>

15. <span data-ttu-id="02f09-210">준수 센터에서 **데이터 커넥터** 페이지로 이동한 다음 **커넥터** 탭을 클릭 하 여 가져오기 프로세스의 진행 상태를 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="02f09-210">In the compliance center, go to the **Data connectors** page, and click the **Connectors** tab to see the progress of the import process.</span></span>
