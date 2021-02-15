---
title: Facebook 비즈니스 페이지 데이터를 보관할 커넥터 배포
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
description: 관리자는 Facebook 비즈니스 페이지를 Microsoft 365로 가져오고 보관하는 기본 커넥터를 설정할 수 있습니다. 이 데이터를 Microsoft 365로 가져온 후 법적 보존, 콘텐츠 검색 및 보존 정책과 같은 준수 기능을 사용하여 조직의 Facebook 데이터의 거버넌스를 관리할 수 있습니다.
ms.openlocfilehash: b771c50eb5c2eb5f99269f1f399d27043ebee6bb
ms.sourcegitcommit: 6fc6aaa2b7610e148f41018abd229e3c55b2f3d0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/10/2020
ms.locfileid: "49619954"
---
# <a name="deploy-a-connector-to-archive-facebook-business-pages-data"></a><span data-ttu-id="06e86-104">Facebook 비즈니스 페이지 데이터를 보관하는 커넥터 배포</span><span class="sxs-lookup"><span data-stu-id="06e86-104">Deploy a connector to archive Facebook Business pages data</span></span>

<span data-ttu-id="06e86-105">이 문서에는 Office 365 가져오기 서비스를 사용하여 Facebook 비즈니스 페이지에서 Microsoft 365로 데이터를 가져오는 커넥터를 배포하는 단계별 프로세스가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="06e86-105">This article contains the step-by-step process to deploy a connector that uses the Office 365 Import service to import data from Facebook Business pages to Microsoft 365.</span></span> <span data-ttu-id="06e86-106">이 프로세스에 대한 개략적인 개요와 Facebook 커넥터를 배포하는 데 필요한 필수 구성 사항 목록을 확인하려면 Facebook 데이터를 보관할 커넥터 [설정을 참조하세요.](archive-facebook-data-with-sample-connector.md)</span><span class="sxs-lookup"><span data-stu-id="06e86-106">For a high-level overview of this process and a list of prerequisites required to deploy a Facebook connector, see [Set up a connector to archive Facebook data](archive-facebook-data-with-sample-connector.md).</span></span>

## <a name="step-1-create-an-app-in-azure-active-directory"></a><span data-ttu-id="06e86-107">1단계: Azure Active Directory에서 앱 만들기</span><span class="sxs-lookup"><span data-stu-id="06e86-107">Step 1: Create an app in Azure Active Directory</span></span>

1. <span data-ttu-id="06e86-108">이동하여 전역 관리자 계정의 자격 <https://portal.azure.com> 증명을 사용하여 로그인합니다.</span><span class="sxs-lookup"><span data-stu-id="06e86-108">Go to <https://portal.azure.com> and sign in using the credentials of a global admin account.</span></span>

    ![AAD에서 앱 만들기](../media/FBCimage1.png)

2. <span data-ttu-id="06e86-110">왼쪽 탐색 창에서 **Azure Active Directory를 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="06e86-110">In the left navigation pane, click **Azure Active Directory**.</span></span>

    ![Azure Active Directory 클릭](../media/FBCimage2.png)

3. <span data-ttu-id="06e86-112">왼쪽 탐색 창에서 앱 등록(미리 **보기)을** 클릭한 다음 새 **등록을 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="06e86-112">In the left navigation pane, click **App registrations (Preview)** and then click **New registration**.</span></span>

    ![Click **App registrations (Preview)** and then click **New registration**](../media/FBCimage3.png)

4. <span data-ttu-id="06e86-114">응용 프로그램을 등록합니다.</span><span class="sxs-lookup"><span data-stu-id="06e86-114">Register the application.</span></span> <span data-ttu-id="06e86-115">리디렉션 URI에서 응용 프로그램 유형 드롭다운 목록에서 웹을 선택한 다음 <https://portal.azure.com> URI의 상자에 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="06e86-115">Under Redirect URI, select Web in the application type dropdown list and then type <https://portal.azure.com> in the box for the URI.</span></span>

   ![응용 프로그램 등록](../media/FBCimage4.png)

5. <span data-ttu-id="06e86-117">응용 **프로그램(클라이언트) ID** 및 **디렉터리(테넌트) ID를** 복사하여 텍스트 파일 또는 기타 안전한 위치에 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="06e86-117">Copy the **Application (client) ID** and **Directory (tenant) ID** and save them to a text file or other safe location.</span></span> <span data-ttu-id="06e86-118">이후 단계에서 이러한 IDS를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="06e86-118">You use these IDs in later steps.</span></span>

   ![응용 프로그램 ID 및 디렉터리 ID 복사 및 저장](../media/FBCimage5.png)

6. <span data-ttu-id="06e86-120">새 **앱의 & 인증서로 이동하세요.**</span><span class="sxs-lookup"><span data-stu-id="06e86-120">Go to **Certificates & secrets for the new app.**</span></span>

   ![새 앱의 & 인증서로 이동](../media/FBCimage6.png)

7. <span data-ttu-id="06e86-122">새 **클라이언트 비밀 클릭**</span><span class="sxs-lookup"><span data-stu-id="06e86-122">Click **New client secret**</span></span>

   ![새 클라이언트 비밀 클릭](../media/FBCimage7.png)

8. <span data-ttu-id="06e86-124">새 비밀을 만드시다.</span><span class="sxs-lookup"><span data-stu-id="06e86-124">Create a new secret.</span></span> <span data-ttu-id="06e86-125">설명 상자에 비밀을 입력한 다음 만료 기간을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="06e86-125">In the description box, type the secret and then choose an expiration period.</span></span>

    ![비밀을 입력한 다음 만료 기간을 선택](../media/FBCimage8.png)

9. <span data-ttu-id="06e86-127">비밀 값을 복사하여 텍스트 파일 또는 다른 저장 위치에 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="06e86-127">Copy the value of the secret and save it to a text file or other storage location.</span></span> <span data-ttu-id="06e86-128">이후 단계에서 사용하는 AAD 응용 프로그램 비밀입니다.</span><span class="sxs-lookup"><span data-stu-id="06e86-128">This is the AAD application secret that you use in later steps.</span></span>

   ![비밀 값 복사 및 저장](../media/FBCimage9.png)

## <a name="step-2-deploy-the-connector-web-service-from-github-to-your-azure-account"></a><span data-ttu-id="06e86-130">2단계: GitHub에서 Azure 계정으로 커넥터 웹 서비스 배포</span><span class="sxs-lookup"><span data-stu-id="06e86-130">Step 2: Deploy the connector web service from GitHub to your Azure account</span></span>

1. <span data-ttu-id="06e86-131">이 [GitHub](https://github.com/microsoft/m365-sample-connector-csharp-aspnet) 사이트로 이동하여 **Azure에 배포를 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="06e86-131">Go to [this GitHub site](https://github.com/microsoft/m365-sample-connector-csharp-aspnet) and click **Deploy to Azure**.</span></span>

    ![Azure에 배포를 클릭합니다.](../media/FBCGithubApp.png)

2. <span data-ttu-id="06e86-133">**Azure에 배포를 클릭하면** 사용자 지정 템플릿 페이지를 사용하여 Azure Portal로 리디렉션됩니다.</span><span class="sxs-lookup"><span data-stu-id="06e86-133">After you click **Deploy to Azure**, you will be redirected to an Azure portal with a custom template page.</span></span> <span data-ttu-id="06e86-134">기본 사항 **및**  설정 세부 정보를 입력하고 구매를 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="06e86-134">Fill in the **Basics** and **Settings** details and then click **Purchase**.</span></span>

   - <span data-ttu-id="06e86-135">**구독:** Facebook 비즈니스 페이지 커넥터 웹 서비스를 배포할 Azure 구독을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="06e86-135">**Subscription:** Select your Azure subscription that you want to deploy the Facebook Business pages connector web service to.</span></span>

   - <span data-ttu-id="06e86-136">**리소스 그룹:** 새 리소스 그룹을 선택하거나 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="06e86-136">**Resource group:** Choose or create a new resource group.</span></span> <span data-ttu-id="06e86-137">리소스 그룹은 Azure 솔루션에 대한 관련 리소스를 보유하는 컨테이너입니다.</span><span class="sxs-lookup"><span data-stu-id="06e86-137">A resource group is a container that holds related resources for an Azure solution.</span></span>

   - <span data-ttu-id="06e86-138">**위치:** 위치를 선택하십시오.</span><span class="sxs-lookup"><span data-stu-id="06e86-138">**Location:** Choose a location.</span></span>

   - <span data-ttu-id="06e86-139">**웹앱 이름:** 커넥터 웹앱의 고유한 이름을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="06e86-139">**Web App Name:** Provide a unique name for the connector web app.</span></span> <span data-ttu-id="06e86-140">Th 이름은 3-18자 사이입니다.</span><span class="sxs-lookup"><span data-stu-id="06e86-140">Th name must be between 3 and 18 characters in length.</span></span> <span data-ttu-id="06e86-141">이 이름은 Azure 앱 서비스 URL을 만드는 데 사용됩니다. 예를 들어 **fbconnector의** 웹 앱 이름을 제공하면 Azure 앱 서비스 URL이 **fbconnector.azurewebsites.net.**</span><span class="sxs-lookup"><span data-stu-id="06e86-141">This name is used to create the Azure app service URL; for example, if you provide the Web app name of **fbconnector** then the Azure app service URL  will be **fbconnector.azurewebsites.net**.</span></span>

   - <span data-ttu-id="06e86-142">**tenantId:** 1단계에서 Azure Active Directory에서 Facebook 커넥터 앱을 만들고 복사한 Microsoft 365 조직의 테넌트 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="06e86-142">**tenantId:** The tenant ID of your Microsoft 365 organization that you copied after creating the Facebook connector app in Azure Active Directory in Step 1.</span></span>

   - <span data-ttu-id="06e86-143">**APISecretKey:** 모든 값을 비밀로 입력할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="06e86-143">**APISecretKey:** You can type any value as the secret.</span></span> <span data-ttu-id="06e86-144">5단계에서 커넥터 웹앱에 액세스하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="06e86-144">This is used to access the connector web app in Step 5.</span></span>

     ![리소스 만들기 및 저장소 계정 유형 클릭](../media/FBCimage12.png)

3. <span data-ttu-id="06e86-146">배포가 성공하면 페이지가 다음 스크린샷과 유사하게 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="06e86-146">After the deployment is successful, the page will look similar to the following screenshot:</span></span>

   ![저장소를 클릭한 다음 저장소 계정을 클릭합니다.](../media/FBCimage13.png)

## <a name="step-3-register-the-facebook-app"></a><span data-ttu-id="06e86-148">3단계: Facebook 앱 등록</span><span class="sxs-lookup"><span data-stu-id="06e86-148">Step 3: Register the Facebook app</span></span>

1. <span data-ttu-id="06e86-149">Go to <https://developers.facebook.com> , log in using the credentials for the account for your organization's Facebook Business pages, and then click Add New **App.**</span><span class="sxs-lookup"><span data-stu-id="06e86-149">Go to <https://developers.facebook.com>, log in using the credentials for the account for your organization's Facebook Business pages, and then click **Add New App**.</span></span>

   ![Facebook 비즈니스용 새 앱 추가 페이지](../media/FBCimage25.png)

2. <span data-ttu-id="06e86-151">새 앱 ID를 만드시다.</span><span class="sxs-lookup"><span data-stu-id="06e86-151">Create a new app ID.</span></span>

   ![새 앱 ID 만들기](../media/FBCimage26.png)

3. <span data-ttu-id="06e86-153">왼쪽 탐색 창에서 제품  추가를 클릭한 다음 Facebook 로그인 타일에서 **설정을** 클릭합니다. </span><span class="sxs-lookup"><span data-stu-id="06e86-153">In the left navigation pane, click **Add Products** and then click **Set Up** in the **Facebook Login** tile.</span></span>

   ![제품 추가를 클릭합니다.](../media/FBCimage27.png)

4. <span data-ttu-id="06e86-155">Facebook 로그인 통합 페이지에서 웹을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="06e86-155">On the Integrate Facebook Login page, click **Web**.</span></span>

   ![Facebook 로그인 통합 페이지에서 웹 클릭](../media/FBCimage28.png)

5. <span data-ttu-id="06e86-157">Azure 앱 서비스 URL을 추가합니다. 예를 들면 `https://fbconnector.azurewebsites.net` 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="06e86-157">Add the Azure app service URL; for example `https://fbconnector.azurewebsites.net`.</span></span>

   ![Azure 앱 서비스 URL 추가](../media/FBCimage29.png)

6. <span data-ttu-id="06e86-159">Facebook 로그인 설정의 QuickStart 섹션을 완료합니다.</span><span class="sxs-lookup"><span data-stu-id="06e86-159">Complete the QuickStart section of the Facebook Login setup.</span></span>

   ![빠른 시작 섹션 완료](../media/FBCimage30.png)

7. <span data-ttu-id="06e86-161">**Facebook** 로그인 아래의 왼쪽 탐색 창에서 설정을 클릭하고 유효한 OAuth 리디렉션 URI 상자에 **OAuth 리디렉션 URI를 추가합니다.** </span><span class="sxs-lookup"><span data-stu-id="06e86-161">In the left navigation pane under **Facebook Login**, click **Settings**, and add the OAuth redirect URI in the **Valid OAuth Redirect URIs** box.</span></span> <span data-ttu-id="06e86-162">connectorserviceuri의 값은 조직의 Azure 앱 서비스 URL인 **\<connectorserviceuri> /Views/FacebookOAuth** 형식을 `https://fbconnector.azurewebsites.net` 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="06e86-162">Use the format **\<connectorserviceuri>/Views/FacebookOAuth**, where the value for connectorserviceuri is the Azure app service URL for your organization; for example, `https://fbconnector.azurewebsites.net`.</span></span>

   ![유효한 OAuth 리디렉션 URI 상자에 OAuth 리디렉션 URI 추가](../media/FBCimage31.png)

8. <span data-ttu-id="06e86-164">왼쪽 탐색 창에서 제품  추가를 클릭한 다음 **Webhook을 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="06e86-164">In the left navigation pane, click **Add Products** and then click **Webhooks.**</span></span> <span data-ttu-id="06e86-165">페이지 **풀다운** 메뉴에서 **페이지를 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="06e86-165">In the **Page** pull-down menu, click **Page**.</span></span>

   ![제품 추가를 클릭한 다음 \*\*Webhook을 클릭합니다.](../media/FBCimage32.png)

9. <span data-ttu-id="06e86-167">Webhook 콜백 URL을 추가하고 확인 토큰을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="06e86-167">Add Webhooks Callback URL and add a verify token.</span></span> <span data-ttu-id="06e86-168">콜백 URL의 형식은 **<connectorserviceuri> /api/FbPageWebhook** 형식을 사용합니다. 여기서 connectorserviceuri의 값은 조직의 Azure 앱 서비스 URL입니다. 예를 들면 다음과 `https://fbconnector.azurewebsites.net` 같습니다.</span><span class="sxs-lookup"><span data-stu-id="06e86-168">The format of the callback URL, use the format **<connectorserviceuri>/api/FbPageWebhook**, where the value for connectorserviceuri is the Azure app service URL for your organization; for example `https://fbconnector.azurewebsites.net`.</span></span>

   <span data-ttu-id="06e86-169">확인 토큰은 강력한 암호와 유사해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="06e86-169">The verify token should similar to a strong password.</span></span> <span data-ttu-id="06e86-170">확인 토큰을 텍스트 파일 또는 다른 저장 위치에 복사합니다.</span><span class="sxs-lookup"><span data-stu-id="06e86-170">Copy the verify token to a text file or other storage location.</span></span>

   ![확인 토큰 추가](../media/FBCimage33.png)

10. <span data-ttu-id="06e86-172">피드에 대한 끝점을 테스트하고 구독합니다.</span><span class="sxs-lookup"><span data-stu-id="06e86-172">Test and subscribe to the endpoint for feed.</span></span>

    ![끝점 테스트 및 구독](../media/FBCimage34.png)

11. <span data-ttu-id="06e86-174">개인 정보 URL, 앱 아이콘 및 비즈니스 사용을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="06e86-174">Add a privacy URL, app icon, and business use.</span></span> <span data-ttu-id="06e86-175">또한 앱 ID 및 앱 비밀을 텍스트 파일 또는 다른 저장소 위치에 복사합니다.</span><span class="sxs-lookup"><span data-stu-id="06e86-175">Also, copy the app ID and app secret to a text file or other storage location.</span></span>

    ![개인 정보 URL, 앱 아이콘 및 비즈니스 사용 추가](../media/FBCimage35.png)

12. <span data-ttu-id="06e86-177">앱을 공개합니다.</span><span class="sxs-lookup"><span data-stu-id="06e86-177">Make the app public.</span></span>

    ![앱을 공개로 만들기](../media/FBCimage36.png)

13. <span data-ttu-id="06e86-179">관리자 또는 테스터 역할에 사용자를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="06e86-179">Add user to the admin or tester role.</span></span>

    ![관리자 또는 테스터 역할에 사용자 추가](../media/FBCimage37.png)

14. <span data-ttu-id="06e86-181">페이지 공용 **콘텐츠 액세스 권한을 추가합니다.**</span><span class="sxs-lookup"><span data-stu-id="06e86-181">Add the **Page Public Content Access** permission.</span></span>

    ![페이지 공용 콘텐츠 액세스 권한 dd](../media/FBCimage38.png)

15. <span data-ttu-id="06e86-183">페이지 관리 권한 추가</span><span class="sxs-lookup"><span data-stu-id="06e86-183">Add Manage Pages permission.</span></span>

    ![페이지 관리 권한 추가](../media/FBCimage39.png)

16. <span data-ttu-id="06e86-185">Facebook에서 응용 프로그램을 검토합니다.</span><span class="sxs-lookup"><span data-stu-id="06e86-185">Get the application reviewed by Facebook.</span></span>

    ![Facebook에서 응용 프로그램을 검토합니다.](../media/FBCimage40.png)

## <a name="step-4-configure-the-connector-web-app"></a><span data-ttu-id="06e86-187">4단계: 커넥터 웹앱 구성</span><span class="sxs-lookup"><span data-stu-id="06e86-187">Step 4: Configure the connector web app</span></span>

1. <span data-ttu-id="06e86-188">(여기서 `https://<AzureAppResourceName>.azurewebsites.net` AzureAppResourceName은 4단계에서 명명한 Azure 앱 리소스의 이름)로 이동하세요.</span><span class="sxs-lookup"><span data-stu-id="06e86-188">Go to `https://<AzureAppResourceName>.azurewebsites.net` (where AzureAppResourceName is the name of your Azure app resource that you named in Step 4).</span></span> <span data-ttu-id="06e86-189">예를 들어 이름이 **fbconnector이면**. `https://fbconnector.azurewebsites.net`</span><span class="sxs-lookup"><span data-stu-id="06e86-189">For example, if the name is **fbconnector**, go to `https://fbconnector.azurewebsites.net`.</span></span> <span data-ttu-id="06e86-190">앱의 홈 페이지는 다음 스크린샷과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="06e86-190">The home page of the app will look like the following screenshot:</span></span>

   ![커넥터 웹앱으로 이동](../media/FBCimage41.png)

2. <span data-ttu-id="06e86-192">로그인 **페이지를** 표시하려면 구성을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="06e86-192">Click **Configure** to display a sign in page.</span></span>

   ![로그인 페이지를 표시하려면 구성을 클릭합니다.](../media/FBCimage42.png)

3. <span data-ttu-id="06e86-194">테넌트 ID 상자에 2단계에서 획득한 테넌트 ID를 입력하거나 붙여넣습니다.</span><span class="sxs-lookup"><span data-stu-id="06e86-194">In the Tenant Id box, type or paste your tenant Id (that you obtained in Step 2).</span></span> <span data-ttu-id="06e86-195">암호 상자에 APISecretKey(2단계에서 획득한 APISecretKey)를  입력하거나 붙여넣은 다음 구성 설정 설정을 클릭하여 구성 세부 정보 페이지를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="06e86-195">In the password box, type or paste the APISecretKey (that you obtained in Step 2), and then click **Set Configuration Settings** to display the configuration details page.</span></span>

    ![테넌트 ID 및 암호를 사용하여 로그인하고 구성 세부 정보 페이지로 이동합니다.](../media/FBCimage43.png)

4. <span data-ttu-id="06e86-197">다음 구성 설정을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="06e86-197">Enter the following configuration settings</span></span>

   - <span data-ttu-id="06e86-198">**Facebook 응용 프로그램 ID:** 3단계에서 획득한 Facebook 응용 프로그램의 앱 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="06e86-198">**Facebook application ID:** The app ID for the Facebook application that you obtained in Step 3.</span></span>

   - <span data-ttu-id="06e86-199">**Facebook 응용 프로그램 비밀:** 3단계에서 획득한 Facebook 응용 프로그램의 앱 비밀입니다.</span><span class="sxs-lookup"><span data-stu-id="06e86-199">**Facebook application secret:** The app secret for the Facebook application that you obtained in Step 3.</span></span>

   - <span data-ttu-id="06e86-200">**Facebook webhook은 토큰을 검증합니다.** 3단계에서 만든 확인 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="06e86-200">**Facebook webhooks verify token:** The verify token that you created in Step 3.</span></span>

   - <span data-ttu-id="06e86-201">**AAD 응용 프로그램 ID:** 1단계에서 만든 Azure Active Directory 앱의 응용 프로그램 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="06e86-201">**AAD application ID:** The application ID for the Azure Active Directory app that you created in Step 1.</span></span>

   - <span data-ttu-id="06e86-202">**AAD 응용 프로그램 비밀:** 1단계에서 만든 APISecretKey 비밀의 값입니다.</span><span class="sxs-lookup"><span data-stu-id="06e86-202">**AAD application secret:** The value for the APISecretKey secret that you created in Step 1.</span></span>

5. <span data-ttu-id="06e86-203">연결선 **설정을** 저장하려면 저장을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="06e86-203">Click **Save** to save the connector settings.</span></span>

## <a name="step-5-set-up-a-facebook-connector-in-the-microsoft-365-compliance-center"></a><span data-ttu-id="06e86-204">5단계: Microsoft 365 규정 준수 센터에서 Facebook 커넥터 설정</span><span class="sxs-lookup"><span data-stu-id="06e86-204">Step 5: Set up a Facebook connector in the Microsoft 365 compliance center</span></span>

1. <span data-ttu-id="06e86-205">Go to [https://compliance.microsoft.com](https://compliance.microsoft.com) and then click Data **connectors** in the left nav.</span><span class="sxs-lookup"><span data-stu-id="06e86-205">Go to [https://compliance.microsoft.com](https://compliance.microsoft.com) and then click **Data connectors** in the left nav.</span></span>

2. <span data-ttu-id="06e86-206">데이터 커넥터 **페이지에서** Facebook 비즈니스 페이지 **아래에 있는 보기를** **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="06e86-206">On the **Data connectors** page under **Facebook Business pages**, click **View**.</span></span>

3. <span data-ttu-id="06e86-207">Facebook 비즈니스 **페이지 페이지에서** 커넥터 **추가를 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="06e86-207">On the **Facebook business pages** page, click **Add connector**.</span></span>

4. <span data-ttu-id="06e86-208">서비스 약관 **페이지에서** 수락을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="06e86-208">On the **Terms of service** page, click **Accept**.</span></span>

5. <span data-ttu-id="06e86-209">커넥터 **앱의** 자격 증명 추가 페이지에서 다음 정보를 입력하고 연결 유효성 검사를 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="06e86-209">On the **Add credentials for your connector app** page, enter the following information and then click **Validate connection**.</span></span>

   ![커넥터 앱 자격 증명 입력](../media/TCimage38.png)

   - <span data-ttu-id="06e86-211">이름 **상자에** 커넥터의 이름(예: Facebook 뉴스 페이지)을 **입력합니다.**</span><span class="sxs-lookup"><span data-stu-id="06e86-211">In the **Name** box, type a name for the connector, such as **Facebook news page**.</span></span>

   - <span data-ttu-id="06e86-212">연결 **URL 상자에** Azure 앱 서비스 URL을 입력하거나 붙여넣습니다. 예를 들면 `https://fbconnector.azurewebsites.net` 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="06e86-212">In the **Connection URL** box, type or paste the Azure app service URL; for example `https://fbconnector.azurewebsites.net`.</span></span>

   - <span data-ttu-id="06e86-213">암호 **상자에** 2단계에서 추가한 APISecretKey의 값을 입력하거나 붙여넣습니다.</span><span class="sxs-lookup"><span data-stu-id="06e86-213">In the **Password** box, type or paste the value of the APISecretKey that you added in Step 2.</span></span>

   - <span data-ttu-id="06e86-214">Azure **앱 ID** 상자에 1단계에서 만든 AAD 응용 프로그램 ID로도 호출되는 응용 프로그램(클라이언트) ID의 값을 입력하거나 붙여넣습니다.</span><span class="sxs-lookup"><span data-stu-id="06e86-214">In the **Azure App ID** box, type or paste the value of the Application (client) ID also called as AAD Application ID that you created in Step 1.</span></span>

6. <span data-ttu-id="06e86-215">연결의 유효성을 검사한 후 다음을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="06e86-215">After the connection is successfully validated, click **Next**.</span></span>

7. <span data-ttu-id="06e86-216">Microsoft **365** 인증 페이지에서 APISecretKey를 다시 입력하거나 붙여넣은 다음 **로그인 웹앱을 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="06e86-216">On the **Authorize Microsoft 365 to import data** page, type or paste the APISecretKey again and then click **Login web app**.</span></span>

8. <span data-ttu-id="06e86-217">Facebook 커넥터 앱 구성 페이지에서 **Facebook으로** 로그인을 클릭하고 조직의 Facebook 비즈니스 페이지에 대한 계정의 자격 증명을 사용하여 로그인합니다. </span><span class="sxs-lookup"><span data-stu-id="06e86-217">On the **Configure Facebook connector app** page, click **Login with Facebook** and log in using the credentials for the account for your organization's Facebook Business pages.</span></span> <span data-ttu-id="06e86-218">로그인한 Facebook 계정에 조직의 Facebook 비즈니스 페이지에 대한 관리자 역할이 할당되어 있는지 확인</span><span class="sxs-lookup"><span data-stu-id="06e86-218">Make sure the Facebook account that you logged in to is assigned the admin role for your organization's Facebook Business pages.</span></span>

   ![Facebook으로 로그인](../media/FBCimage50.png)

9. <span data-ttu-id="06e86-220">로그인한 Facebook 계정으로 관리되는 비즈니스 페이지 목록이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="06e86-220">A list of the business pages managed by the Facebook account that you logged in to is displayed.</span></span> <span data-ttu-id="06e86-221">보관할 페이지를 선택하고 다음을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="06e86-221">Select the page to archive and then click **Next**.</span></span>

   ![보관할 조직 비즈니스 페이지 선택](../media/FBCimage52.png)

10. <span data-ttu-id="06e86-223">**계속을** 클릭하여 커넥터 서비스 앱의 설정을 종료합니다.</span><span class="sxs-lookup"><span data-stu-id="06e86-223">Click **Continue** to exit the setup of the connector service app.</span></span>

11. <span data-ttu-id="06e86-224">필터 **설정 페이지에서** 특정 연령의 항목을 처음에 가져오는 필터를 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="06e86-224">On the **Set filters** page, you can apply a filter to initially import items that are a certain age.</span></span> <span data-ttu-id="06e86-225">연령을 선택하고 다음을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="06e86-225">Select an age, and then click **Next**.</span></span>

12. <span data-ttu-id="06e86-226">저장소 **위치** 선택 페이지에서 Facebook 항목을 가져올 Microsoft 365 사서함의 전자 메일 주소를 입력하고 다음을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="06e86-226">On the **Choose storage location** page, type the email address of Microsoft 365 mailbox that the Facebook items will be imported to, and then click **Next**.</span></span>

13. <span data-ttu-id="06e86-227">**다음을** 클릭하여 커넥터 설정을 검토한 다음 **마친을** 클릭하여 커넥터 설정을 완료합니다.</span><span class="sxs-lookup"><span data-stu-id="06e86-227">Click **Next** to review the connector settings and then click **Finish** to complete the connector setup.</span></span>

14. <span data-ttu-id="06e86-228">준수 센터에서 데이터 커넥터  페이지로 이동한 다음  커넥터 탭을 클릭하여 가져오기 프로세스의 진행률을 봐야 합니다.</span><span class="sxs-lookup"><span data-stu-id="06e86-228">In the compliance center, go to the **Data connectors** page, and click the **Connectors** tab to see the progress of the import process.</span></span>
