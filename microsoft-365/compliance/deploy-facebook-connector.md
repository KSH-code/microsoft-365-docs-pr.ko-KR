---
title: Office 365에서 Facebook 데이터를 보관 하기 위한 커넥터 배포
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
ROBOTS: NOINDEX, NOFOLLOW
description: 관리자는 Facebook Business 페이지를 가져와 Office 365에 보관 하는 기본 커넥터를 설정할 수 있습니다. 이 데이터를 Office 365로 가져온 후 법적 보존, 콘텐츠 검색 및 보존 정책과 같은 규정 준수 기능을 사용 하 여 조직의 Facebook 데이터를 관리할 수 있습니다.
ms.openlocfilehash: 786ff97c558a5618643783de803c742c50185f00
ms.sourcegitcommit: 1c962bd0d51dc12419c4e6e393bb734c972b7e38
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/12/2019
ms.locfileid: "38687140"
---
# <a name="deploy-a-connector-to-archive-facebook-data-in-office-365"></a><span data-ttu-id="45a9b-104">Office 365에서 Facebook 데이터를 보관 하기 위한 커넥터 배포</span><span class="sxs-lookup"><span data-stu-id="45a9b-104">Deploy a connector to archive Facebook data in Office 365</span></span>

<span data-ttu-id="45a9b-105">이 문서에서는 Office 365 가져오기 서비스를 사용 하 여 Facebook Business 페이지의 데이터를 Office 365로 가져오는 커넥터를 배포 하는 단계별 프로세스를 소개 합니다.</span><span class="sxs-lookup"><span data-stu-id="45a9b-105">This article contains the step-by-step process to deploy a connector that uses the Office 365 Import service to import data from Facebook Business pages to Office 365.</span></span> <span data-ttu-id="45a9b-106">이 프로세스에 대 한 간략 한 개요와 Facebook 커넥터를 배포 하는 데 필요한 필수 구성 요소 목록은 [샘플 커넥터를 사용 하 여 Office 365의 facebook 데이터 보관 (미리 보기)](archive-facebook-data-with-sample-connector.md)을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="45a9b-106">For a high-level overview of this process and a list of prerequisites required to deploy a Facebook connector, see [Use a sample connector to archive Facebook data in Office 365 (Preview)](archive-facebook-data-with-sample-connector.md).</span></span> 

## <a name="step-1-download-the-package"></a><span data-ttu-id="45a9b-107">1 단계: 패키지 다운로드</span><span class="sxs-lookup"><span data-stu-id="45a9b-107">Step 1: Download the package</span></span>

<span data-ttu-id="45a9b-108">GitHub 리포지토리의 릴리스 섹션에서 미리 작성 된 패키지를 다운로드 <https://github.com/Microsoft/m365-sample-connector-csharp-aspnet/releases>합니다.</span><span class="sxs-lookup"><span data-stu-id="45a9b-108">Download the prebuilt package from the Release section in the GitHub repository at <https://github.com/Microsoft/m365-sample-connector-csharp-aspnet/releases>.</span></span> <span data-ttu-id="45a9b-109">최신 버전의 경우 **SampleConnector**라는 zip 파일을 다운로드 합니다.</span><span class="sxs-lookup"><span data-stu-id="45a9b-109">Under the latest release, download the zip file named **SampleConnector.zip**.</span></span> <span data-ttu-id="45a9b-110">4 단계에서이 zip 파일을 Azure에 업로드 합니다.</span><span class="sxs-lookup"><span data-stu-id="45a9b-110">You upload this zip file to Azure in Step 4.</span></span>

## <a name="step-2-create-an-app-in-azure-active-directory"></a><span data-ttu-id="45a9b-111">2 단계: Azure Active Directory에 앱 만들기</span><span class="sxs-lookup"><span data-stu-id="45a9b-111">Step 2: Create an app in Azure Active Directory</span></span>

1. <span data-ttu-id="45a9b-112">으로 이동 <https://portal.azure.com> 하 고 Office 365 전역 관리자 계정의 자격 증명을 사용 하 여 로그인 합니다.</span><span class="sxs-lookup"><span data-stu-id="45a9b-112">Go to <https://portal.azure.com> and sign in using the credentials of an Office 365 global admin account.</span></span>

    ![AAD에서 앱 만들기](media/FBCimage1.png)

2. <span data-ttu-id="45a9b-114">왼쪽 탐색 창에서 **Azure Active Directory**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="45a9b-114">In the left navigation pane, click **Azure Active Directory**.</span></span>

    ![Azure Active Directory를 클릭 합니다.](media/FBCimage2.png)

3. <span data-ttu-id="45a9b-116">왼쪽 탐색 창에서 **앱 등록 (미리 보기)** 을 클릭 하 고 **새 등록**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="45a9b-116">In the left navigation pane, click **App registrations (Preview)** and then click **New registration**.</span></span>

    ![\* \* 앱 등록 (미리 보기) \* \*를 클릭 하 고 \* \* 새 등록을 클릭 합니다.](media/FBCimage3.png)

4. <span data-ttu-id="45a9b-118">응용 프로그램을 등록 합니다.</span><span class="sxs-lookup"><span data-stu-id="45a9b-118">Register the application.</span></span> <span data-ttu-id="45a9b-119">리디렉션 URI의 응용 프로그램 형식 드롭다운 목록에서 웹을 선택한 다음 URI에 <https://portal.azure.com> 대 한 상자에 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="45a9b-119">Under Redirect URI, select Web in the application type dropdown list and then type <https://portal.azure.com> in the box for the URI.</span></span>

   ![응용 프로그램 등록](media/FBCimage4.png)

5. <span data-ttu-id="45a9b-121">**응용 프로그램 (클라이언트) id** 및 **디렉터리 (테 넌 트) id** 를 복사한 다음 텍스트 파일 또는 기타 안전한 위치에 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="45a9b-121">Copy the **Application (client) ID** and **Directory (tenant) ID** and save them to a text file or other safe location.</span></span> <span data-ttu-id="45a9b-122">이후 단계에서 이러한 Id를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="45a9b-122">You use these IDs in later steps.</span></span>

   ![응용 프로그램 ID 및 디렉터리 ID를 복사 하 고 저장 합니다.](media/FBCimage5.png)

6. <span data-ttu-id="45a9b-124">**새 앱에 대 한 인증서 & 비밀으로 이동 합니다.**</span><span class="sxs-lookup"><span data-stu-id="45a9b-124">Go to **Certificates & secrets for the new app.**</span></span>

   ![새 앱에 대 한 인증서 & 비밀으로 이동 합니다.](media/FBCimage6.png)

7. <span data-ttu-id="45a9b-126">**새 클라이언트 암호** 를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="45a9b-126">Click **New client secret**</span></span>

   ![새 클라이언트 암호를 클릭 합니다.](media/FBCimage7.png)

8. <span data-ttu-id="45a9b-128">새 암호를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="45a9b-128">Create a new secret.</span></span> <span data-ttu-id="45a9b-129">설명 상자에 암호를 입력 하 고 만료 기간을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="45a9b-129">In the description box, type the secret and then choose an expiration period.</span></span> 

    ![암호를 입력 하 고 만료 기간을 선택 합니다.](media/FBCimage8.png)

9. <span data-ttu-id="45a9b-131">비밀 값을 복사 하 여 텍스트 파일 또는 기타 저장 위치에 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="45a9b-131">Copy the value of the secret and save it to a text file or other storage location.</span></span> <span data-ttu-id="45a9b-132">이는 이후 단계에서 사용 하는 AAD 응용 프로그램 비밀입니다.</span><span class="sxs-lookup"><span data-stu-id="45a9b-132">This is the AAD application secret that you use in later steps.</span></span>

   ![비밀 값을 복사 하 고 저장 합니다.](media/FBCimage9.png)

10. <span data-ttu-id="45a9b-134">다음 스크린샷에 표시 된 대로 **매니페스트로** 이동 하 여 IDENTIFIERURIS (AAD 응용 프로그램 Uri 라고도 함)를 복사 합니다.</span><span class="sxs-lookup"><span data-stu-id="45a9b-134">Go to **Manifest** and copy the identifierUris (which is also called the AAD application Uri) as highlighted in the following screenshot.</span></span> <span data-ttu-id="45a9b-135">AAD 응용 프로그램 Uri를 텍스트 파일 또는 기타 저장 위치에 복사 합니다.</span><span class="sxs-lookup"><span data-stu-id="45a9b-135">Copy the AAD application Uri to a text file or other storage location.</span></span> <span data-ttu-id="45a9b-136">6 단계에서 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="45a9b-136">You use it in Step 6.</span></span>

   ![매니페스트로 이동 하 여 AAD 응용 프로그램 Uri 복사](media/FBCimage10.png)

## <a name="step-3-create-an-azure-storage-account"></a><span data-ttu-id="45a9b-138">3 단계: Azure storage 계정 만들기</span><span class="sxs-lookup"><span data-stu-id="45a9b-138">Step 3: Create an Azure storage account</span></span>

1. <span data-ttu-id="45a9b-139">조직의 Azure 홈 페이지로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="45a9b-139">Go to the Azure home page for your organization.</span></span>

    ![Azure 홈 페이지로 이동](media/FBCimage11.png)

2. <span data-ttu-id="45a9b-141">**리소스 만들기** 를 클릭 한 다음 검색 상자에 **저장소 계정을** 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="45a9b-141">Click **Create a resource** and then type **storage account** in the search box.</span></span>

    ![리소스 만들기 및 저장소 계정 입력을 클릭 합니다.](media/FBCimage12.png)

3. <span data-ttu-id="45a9b-143">**저장소**를 클릭 한 다음 **저장소 계정을**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="45a9b-143">Click **Storage**, and then click **Storage account**.</span></span>

    ![저장소를 클릭 한 다음 저장소 계정을 클릭 합니다.](media/FBCimage13.png)

4. <span data-ttu-id="45a9b-145">**저장소 계정 만들기** 페이지의 구독 상자에서 사용 중인 Azure 구독 유형에 따라 **유료** 또는 **무료 평가판** 을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="45a9b-145">On the **Create storage account** page, in the Subscription box, select **Pay-As-You-Go** or **Free Trial** depending on which type of Azure subscription you have.</span></span> <span data-ttu-id="45a9b-146">그런 다음 리소스 그룹을 선택 하거나 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="45a9b-146">Then select or create a resource group.</span></span>

    ![진행 중 비용 청구 또는 무료 평가판을 선택 합니다.](media/FBCimage14.png)

5. <span data-ttu-id="45a9b-148">저장소 계정의 이름을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="45a9b-148">Type a name for the storage account.</span></span>

    ![저장소 계정의 이름 입력](media/FBCimage15.png)

6. <span data-ttu-id="45a9b-150">검토 한 다음 **만들기** 를 클릭 하 여 저장소 계정을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="45a9b-150">Review and then click **Create** to create the storage account.</span></span>

    ![저장소 계정 만들기](media/FBCimage16.png)

7. <span data-ttu-id="45a9b-152">잠시 후 **새로 고침** 을 클릭 하 고 **리소스로 이동을** 클릭 하 여 저장소 계정으로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="45a9b-152">After a few moments, click **Refresh** and then click **Go to resource** to navigate to the storage account.</span></span>

    ![저장소 계정으로 이동 합니다.](media/FBCimage17.png)

8. <span data-ttu-id="45a9b-154">왼쪽 탐색 창에서 **Access 키** 를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="45a9b-154">Click **Access keys** in the left navigation pane.</span></span>

    ![선택 키 클릭](media/FBCimage18.png)

9. <span data-ttu-id="45a9b-156">**연결 문자열** 을 복사 하 여 텍스트 파일 또는 기타 저장 위치에 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="45a9b-156">Copy a **Connection string** and save it to a text file or other storage location.</span></span> <span data-ttu-id="45a9b-157">이는 웹 앱 리소스를 만들 때 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="45a9b-157">You use this when creating a web app resource.</span></span>

    ![연결 문자열 복사 및 저장](media/FBCimage19.png)

## <a name="step-4-create-a-new-web-app-resource-in-azure"></a><span data-ttu-id="45a9b-159">4 단계: Azure에서 새 웹 앱 리소스 만들기</span><span class="sxs-lookup"><span data-stu-id="45a9b-159">Step 4: Create a new web app resource in Azure</span></span>

1. <span data-ttu-id="45a9b-160">Azure portal의 **홈** 페이지에서 **모든 \> \> 리소스 만들기 웹 앱**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="45a9b-160">On the **Home** page in the Azure portal, click **Create a resource \> Everything \> Web app**.</span></span> <span data-ttu-id="45a9b-161">**웹 앱** 페이지에서 **만들기**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="45a9b-161">On the **Web app** page, click **Create**.</span></span> 

   ![새 웹 앱 리소스 만들기](media/FBCimage20.png)

2. <span data-ttu-id="45a9b-163">아래와 같이 세부 정보를 입력 하 고 웹 앱을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="45a9b-163">Fill in the details (as shown below) and then create the Web app.</span></span> <span data-ttu-id="45a9b-164">**앱 이름** 상자에 입력 한 이름은 Azure 앱 서비스 URL을 만드는 데 사용 됩니다. 예: fbconnector.azurewebsites.net.</span><span class="sxs-lookup"><span data-stu-id="45a9b-164">Note that the name that you enter in the **App name** box is used to create the Azure app service URL; for example, fbconnector.azurewebsites.net.</span></span>

   ![세부 정보를 입력 한 다음 웹 앱 만들기](media/FBCimage21.png)

3. <span data-ttu-id="45a9b-166">새로 만든 웹 앱 리소스로 이동 하 여 왼쪽 탐색 창에서 **응용 프로그램 설정을** 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="45a9b-166">Go to the newly created web app resource, click **Application Settings** in the left navigation pane.</span></span> <span data-ttu-id="45a9b-167">응용 프로그램 설정에서 새 설정 추가를 클릭 하 고 다음의 세 가지 설정을 추가 합니다. (이전 단계의 텍스트 파일에 복사한 값)를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="45a9b-167">Under Application settings, click Add new setting and add the following three settings: Use the values (that you copied to the text file from the previous steps):</span></span> 

    - <span data-ttu-id="45a9b-168">**APISecretKey** – 임의의 값을 비밀로 입력할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="45a9b-168">**APISecretKey** – You can type any value as the secret.</span></span> <span data-ttu-id="45a9b-169">이는 7 단계에서 커넥터 웹 앱에 액세스 하는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="45a9b-169">This is used to access the connector web app in Step 7.</span></span>

    - <span data-ttu-id="45a9b-170">**Storageaccountconnectionstring** -3 단계에서 Azure storage 계정을 만든 후에 복사한 연결 문자열 Uri입니다.</span><span class="sxs-lookup"><span data-stu-id="45a9b-170">**StorageAccountConnectionString** — The connection string Uri that you copied after creating the Azure storage account in Step 3.</span></span>

    - <span data-ttu-id="45a9b-171">**tenantId** -2 단계에서 Azure Active Directory에 Facebook 커넥터 앱을 만든 후 복사한 Office 365 조직의 테 넌 트 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="45a9b-171">**tenantId** – The tenant ID of your Office 365 organization that you copied after creating the Facebook connector app in Azure Active Directory in Step 2.</span></span>

    ![응용 프로그램 설정 입력](media/FBCimage22.png)

4. <span data-ttu-id="45a9b-173">**일반 설정**에서 **Always (켜기**) **옆의을 클릭 합니다** .</span><span class="sxs-lookup"><span data-stu-id="45a9b-173">Under **General settings**, click **On** next to the **Always On**.</span></span> <span data-ttu-id="45a9b-174">페이지 맨 위에 있는 **저장** 을 클릭 하 여 응용 프로그램 설정을 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="45a9b-174">Click **Save** at the top of the page to save the application settings.</span></span>

   ![응용 프로그램 설정 저장](media/FBCimage23.png)

5. <span data-ttu-id="45a9b-176">마지막 단계에서는 1 단계에서 다운로드 한 Azure에 커넥터 응용 프로그램 소스 코드를 업로드 합니다.</span><span class="sxs-lookup"><span data-stu-id="45a9b-176">The final step is to upload the connector app source code to Azure that you downloaded in Step 1.</span></span> <span data-ttu-id="45a9b-177">웹 브라우저에서 scm.azurewebsites.net/ZipDeployUi로 이동 합니다.<AzureAppResourceName>https://.</span><span class="sxs-lookup"><span data-stu-id="45a9b-177">In a web browser, go to https://<AzureAppResourceName>.scm.azurewebsites.net/ZipDeployUi.</span></span> <span data-ttu-id="45a9b-178">예를 들어이 섹션의 2 단계에서 이름이 지정 된 Azure 앱 리소스의 이름이 **fbconnector**인 경우로 https://fbconnector.scm.azurewebsites.net/ZipDeployUi이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="45a9b-178">For example, if the name of your Azure app resource (which you named in step 2 in this section) is **fbconnector**, then you would go to https://fbconnector.scm.azurewebsites.net/ZipDeployUi.</span></span> 

6. <span data-ttu-id="45a9b-179">1 단계에서 다운로드 한 SampleConnector을이 페이지로 끌어서 놓습니다.</span><span class="sxs-lookup"><span data-stu-id="45a9b-179">Drag and drop the SampleConnector.zip (that you downloaded in Step 1) to this page.</span></span> <span data-ttu-id="45a9b-180">파일이 업로드 되 고 배포가 성공적으로 수행 되 면 페이지는 다음 스크린샷과 유사 하 게 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="45a9b-180">After the files are uploaded and the deployment is successful, the page will look similar to the following screenshot:</span></span>

   ![SampleConnector를 끌어서이 페이지에 저장 합니다.](media/FBCimage24.png)

## <a name="step-5-register-the-facebook-app"></a><span data-ttu-id="45a9b-182">5 단계: Facebook 앱 등록</span><span class="sxs-lookup"><span data-stu-id="45a9b-182">Step 5: Register the Facebook app</span></span>

1. <span data-ttu-id="45a9b-183"><https://developers.facebook.com>으로 이동 하 고 조직의 Facebook Business 페이지의 계정에 대 한 자격 증명을 사용 하 여 로그인 한 다음 **새 앱 추가**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="45a9b-183">Go to <https://developers.facebook.com>, log in using the credentials for the account for your organization’s Facebook Business pages, and then click **Add New App**.</span></span>

   ![Facebook business에 대 한 새 앱 추가 페이지](media/FBCimage25.png)

2. <span data-ttu-id="45a9b-185">새 앱 ID를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="45a9b-185">Create a new app ID.</span></span>

   ![새 앱 ID 만들기](media/FBCimage26.png)

3. <span data-ttu-id="45a9b-187">왼쪽 탐색 창에서 **제품 추가** 를 클릭 한 다음 **Facebook 로그인** 타일에서 **설정을** 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="45a9b-187">In the left navigation pane, click **Add Products** and then click **Set Up** in the **Facebook Login** tile.</span></span>

   ![제품 추가 클릭](media/FBCimage27.png)

4. <span data-ttu-id="45a9b-189">Facebook 로그온 페이지에서 **웹**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="45a9b-189">On the Integrate Facebook Login page, click **Web**.</span></span>

   ![Facebook 로그인 페이지에서 웹을 클릭 합니다.](media/FBCimage28.png)

5. <span data-ttu-id="45a9b-191">Azure 앱 서비스 URL을 추가 합니다. 예를 `https://fbconnector.azurewebsites.net`들어</span><span class="sxs-lookup"><span data-stu-id="45a9b-191">Add the Azure app service URL; for example `https://fbconnector.azurewebsites.net`.</span></span>

   ![Azure 앱 서비스 URL 추가](media/FBCimage29.png)

6. <span data-ttu-id="45a9b-193">Facebook 로그인 설정의 퀵 스타트 섹션을 완료 합니다.</span><span class="sxs-lookup"><span data-stu-id="45a9b-193">Complete the QuickStart section of the Facebook Login setup.</span></span>

   ![퀵 스타트 섹션 완료](media/FBCimage30.png)

7. <span data-ttu-id="45a9b-195">**Facebook 로그인**아래의 왼쪽 탐색 창에서 **설정을**클릭 하 고 **유효한 OAuth 리디렉션 URI** 상자에 OAuth 리디렉션 URI를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="45a9b-195">In the left navigation pane under **Facebook Login**, click **Settings**, and add the OAuth redirect URI in the **Valid OAuth Redirect URIs** box.</span></span> <span data-ttu-id="45a9b-196">Connectorserviceuri의 값은 조직의 Azure app 서비스 URL 인 \*\* \<connectorserviceuri>/views/facebookoauth\*\*형식을 사용 합니다. 예를 `https://fbconnector.azurewebsites.net`들면입니다.</span><span class="sxs-lookup"><span data-stu-id="45a9b-196">Use the format **\<connectorserviceuri>/Views/FacebookOAuth**, where the value for connectorserviceuri is the Azure app service URL for your organization; for example, `https://fbconnector.azurewebsites.net`.</span></span>

   ![OAuth 리디렉션 URI를 유효한 OAuth 리디렉션 Uri 상자에 추가 합니다.](media/FBCimage31.png)

8. <span data-ttu-id="45a9b-198">왼쪽 탐색 창에서 **제품 추가** 를 클릭 한 다음 **webhooks를 클릭 합니다.**</span><span class="sxs-lookup"><span data-stu-id="45a9b-198">In the left navigation pane, click **Add Products** and then click **Webhooks.**</span></span> <span data-ttu-id="45a9b-199">**페이지** 풀 다운 메뉴에서 **페이지**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="45a9b-199">In the **Page** pull-down menu, click **Page**.</span></span> 

   ![제품 추가를 클릭 한 다음 \* \* Webhooks를 클릭 합니다.](media/FBCimage32.png)

9. <span data-ttu-id="45a9b-201">Webhooks 콜백 URL을 추가 하 고 verify token을 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="45a9b-201">Add Webhooks Callback URL and add a verify token.</span></span> <span data-ttu-id="45a9b-202">콜백 URL의 형식은 \*\* <connectorserviceuri>/api/FbPageWebhook\*\*형식을 사용 하며, 여기서 connectorserviceuri의 값은 조직의 Azure 앱 서비스 URL입니다. 예를 `https://fbconnector.azurewebsites.net`들어</span><span class="sxs-lookup"><span data-stu-id="45a9b-202">The format of the callback URL, use the format **<connectorserviceuri>/api/FbPageWebhook**, where the value for connectorserviceuri is the Azure app service URL for your organization; for example `https://fbconnector.azurewebsites.net`.</span></span> 

    <span data-ttu-id="45a9b-203">Verify 토큰은 강력한 암호와 비슷해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="45a9b-203">The verify token should similar to a strong password.</span></span> <span data-ttu-id="45a9b-204">텍스트 파일 또는 기타 저장소 위치에 verify 토큰을 복사 합니다.</span><span class="sxs-lookup"><span data-stu-id="45a9b-204">Copy the verify token to a text file or other storage location.</span></span>

        ![Add the verify token](media/FBCimage33.png)

10. <span data-ttu-id="45a9b-205">테스트 하 고 피드의 끝점을 구독 합니다.</span><span class="sxs-lookup"><span data-stu-id="45a9b-205">Test and subscribe to the endpoint for feed.</span></span>

    ![테스트 및 끝점 구독](media/FBCimage34.png)

11. <span data-ttu-id="45a9b-207">개인 정보 URL, 앱 아이콘 및 비즈니스 사용을 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="45a9b-207">Add a privacy URL, app icon, and business use.</span></span> <span data-ttu-id="45a9b-208">또한 앱 ID 및 앱 암호를 텍스트 파일 또는 기타 저장 위치에 복사 합니다.</span><span class="sxs-lookup"><span data-stu-id="45a9b-208">Also, copy the app ID and app secret to a text file or other storage location.</span></span>

    ![개인 정보 URL, 앱 아이콘 및 비즈니스 용도 추가](media/FBCimage35.png)

12. <span data-ttu-id="45a9b-210">앱을 공용으로 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="45a9b-210">Make the app public.</span></span>

    ![앱을 공용으로 설정](media/FBCimage36.png)

13. <span data-ttu-id="45a9b-212">관리자 또는 테스터 역할에 사용자를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="45a9b-212">Add user to the admin or tester role.</span></span>

    ![관리자 또는 테스터 역할에 사용자 추가](media/FBCimage37.png)

14. <span data-ttu-id="45a9b-214">**페이지 공용 콘텐츠 액세스** 권한을 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="45a9b-214">Add the **Page Public Content Access** permission.</span></span>

    ![dd 페이지 공용 콘텐츠 액세스 권한](media/FBCimage38.png)

15. <span data-ttu-id="45a9b-216">페이지 관리 권한을 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="45a9b-216">Add Manage Pages permission.</span></span>

    ![페이지 관리 권한 추가](media/FBCimage39.png)

16. <span data-ttu-id="45a9b-218">Facebook에서 검토 한 응용 프로그램을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="45a9b-218">Get the application reviewed by Facebook.</span></span>

    ![Facebook에서 검토 한 응용 프로그램 가져오기](media/FBCimage40.png)

## <a name="step-6-configure-the-connector-web-app"></a><span data-ttu-id="45a9b-220">6 단계: 커넥터 웹 응용 프로그램 구성</span><span class="sxs-lookup"><span data-stu-id="45a9b-220">Step 6: Configure the connector web app</span></span>

1. <span data-ttu-id="45a9b-221">Https://\<AzureAppResourceName> (여기에서 AzureAppResourceName는 4 단계에서 명명 한 Azure 앱 리소스의 이름)으로 이동 합니다 (예: 이름이 **fbconnector**이면로 `https://fbconnector.azurewebsites.net`이동).</span><span class="sxs-lookup"><span data-stu-id="45a9b-221">Go to https://\<AzureAppResourceName>.azurewebsites.net (where AzureAppResourceName is the name of your Azure app resource that you named in Step 4) For example, if the name is **fbconnector**, go to `https://fbconnector.azurewebsites.net`.</span></span> <span data-ttu-id="45a9b-222">앱의 홈 페이지는 다음 스크린샷 처럼 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="45a9b-222">The home page of the app will look like the following screenshot:</span></span>

   ![커넥터 웹 앱으로 이동](media/FBCimage41.png)

2. <span data-ttu-id="45a9b-224">**구성을** 클릭 하 여 로그인 페이지를 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="45a9b-224">Click **Configure** to display a sign in page.</span></span>
 
   ![로그인 페이지를 표시 하려면 구성을 클릭 합니다.](media/FBCimage42.png)

3. <span data-ttu-id="45a9b-226">테 넌 트 Id 상자에 2 단계에서 받은 테 넌 트 Id를 입력 하거나 붙여 넣습니다.</span><span class="sxs-lookup"><span data-stu-id="45a9b-226">In the Tenant Id box, type or paste your tenant Id (that you obtained in Step 2).</span></span> <span data-ttu-id="45a9b-227">암호 상자에 2 단계에서 구한 APISecretKey를 입력 하거나 붙여 넣은 다음 **구성 설정 설정을** 클릭 하 여 **구성 세부 정보** 페이지를 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="45a9b-227">In the password box, type or paste the APISecretKey (that you obtained in Step 2), and then click **Set Configuration Settings** to display the **Configuration Details** page.</span></span>

    ![테 넌 트 Id 및 암호를 사용 하 여 로그인 하 고 구성 세부 정보 페이지로 이동](media/FBCimage43.png)

4. <span data-ttu-id="45a9b-229">**구성 세부 정보**에서 다음 구성 설정을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="45a9b-229">Under **Configuration Details**, enter the following configuration settings</span></span> 

   - <span data-ttu-id="45a9b-230">**Facebook 응용 프로그램 id** -5 단계에서 가져온 facebook 응용 프로그램의 앱 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="45a9b-230">**Facebook application ID** – The app ID for the Facebook application that you obtained in Step 5.</span></span>
   - <span data-ttu-id="45a9b-231">**Facebook 응용 프로그램 비밀** -5 단계에서 얻은 facebook 응용 프로그램에 대 한 앱 비밀입니다.</span><span class="sxs-lookup"><span data-stu-id="45a9b-231">**Facebook application secret** – The app secret for the Facebook application that you obtained in Step 5.</span></span>
   - <span data-ttu-id="45a9b-232">**Facebook webhook 확인 토큰** – 5 단계에서 만든 verify 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="45a9b-232">**Facebook webhooks verify token** – The verify token that you created in Step 5.</span></span>
   - <span data-ttu-id="45a9b-233">**AAD 응용 프로그램 id** -2 단계에서 만든 Azure Active Directory 앱의 응용 프로그램 id입니다.</span><span class="sxs-lookup"><span data-stu-id="45a9b-233">**AAD application ID** – The application ID for the Azure Active Directory app that you created in Step 2.</span></span>
   - <span data-ttu-id="45a9b-234">**AAD 응용 프로그램 비밀** -4 단계에서 만든 APISecretKey 암호에 대 한 값입니다.</span><span class="sxs-lookup"><span data-stu-id="45a9b-234">**AAD application secret** – The value for the APISecretKey secret that you created in Step 4.</span></span>
   - <span data-ttu-id="45a9b-235">**Aad 응용 프로그램 uri** -2 단계에서 가져온 aad 응용 프로그램 uri 예를 `https://microsoft.onmicrosoft.com/2688yu6n-12q3-23we-e3ee-121111123213`들면입니다.</span><span class="sxs-lookup"><span data-stu-id="45a9b-235">**AAD application Uri** – The AAD application Uri obtained in Step 2; for example, `https://microsoft.onmicrosoft.com/2688yu6n-12q3-23we-e3ee-121111123213`.</span></span>
   - <span data-ttu-id="45a9b-236">**App insights instrumentation 키** -이 상자를 비워 둡니다.</span><span class="sxs-lookup"><span data-stu-id="45a9b-236">**App insights instrumentation key** – Leave this box blank.</span></span>

5. <span data-ttu-id="45a9b-237">**저장** 을 클릭 하 여 커넥터 설정을 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="45a9b-237">Click **Save** to save the connector settings.</span></span>

## <a name="step-7-set-up-a-custom-connector-in-the-security--compliance-center"></a><span data-ttu-id="45a9b-238">7 단계: 보안 & 준수 센터에서 사용자 지정 커넥터 설정</span><span class="sxs-lookup"><span data-stu-id="45a9b-238">Step 7: Set up a custom connector in the Security & Compliance Center</span></span>

1. <span data-ttu-id="45a9b-239">로 이동한 <https://protection.office.com> 후 **데이터 거 버 넌 \> 스 \> 가져오기 보관 타사 데이터**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="45a9b-239">Go to <https://protection.office.com> and then click **Data governance \> Import \> Archive third-party data**.</span></span>

   ![보안 및 준수 센터로 이동한 후 데이터 관리 > 클릭 하 여 타사 데이터 가져오기 > 보관](media/FBCimage44.png)

2.  <span data-ttu-id="45a9b-241">**커넥터 추가** 를 클릭 한 다음 **Facebook 페이지**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="45a9b-241">Click **Add a connector** and then click **Facebook pages**.</span></span>

    ![Facebook 커넥터 추가 커넥터를 구성 합니다.](media/FBCimage46.png)

3.  <span data-ttu-id="45a9b-243">**커넥터 앱 추가** 페이지에서 다음 정보를 입력 하 고 **커넥터 유효성 검사**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="45a9b-243">On the **Add Connector App** page, enter the following information and then click **Validate connector**.</span></span>

    - <span data-ttu-id="45a9b-244">첫 번째 상자에 **Facebook**과 같은 커넥터의 이름을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="45a9b-244">In the first box, type a name for the connector, such as **Facebook**.</span></span>
    - <span data-ttu-id="45a9b-245">두 번째 상자에 4 단계에서 추가한 APISecretKey의 값을 입력 하거나 붙여넣습니다.</span><span class="sxs-lookup"><span data-stu-id="45a9b-245">In the second box, type or paste the value of the APISecretKey that you added in Step 4.</span></span>
    - <span data-ttu-id="45a9b-246">세 번째 상자에 Azure 앱 서비스 URL을 입력 하거나 붙여넣습니다. 예를 `https://fbconnector.azurewebsites.net`들어</span><span class="sxs-lookup"><span data-stu-id="45a9b-246">In the third box, type or paste the Azure app service URL; for example `https://fbconnector.azurewebsites.net`.</span></span>
 
    <span data-ttu-id="45a9b-247">커넥터 유효성 검사가 완료 되 면 **다음**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="45a9b-247">After the connector is successfully validated, click **Next**.</span></span>
    
    ![커넥터의 유효성이 검사 된 후 다음을 클릭 합니다.](media/FBCimage47.png)

4.  <span data-ttu-id="45a9b-249">**커넥터 앱을 사용 하 여 로그인을**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="45a9b-249">Click **Login with Connector App**.</span></span>

    ![커넥터 앱을 사용 하 여 로그인 클릭](media/FBCimage45.png)

5. <span data-ttu-id="45a9b-251">APISecretKey를 다시 입력 하거나 붙여 넣은 다음 **커넥터 서비스에 로그인을**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="45a9b-251">Type or paste the APISecretKey again and then click  **Login to Connector Service**.</span></span>

   ![APISecretKey를 입력 하거나 붙여 넣은 다음 로그인 단추를 클릭 합니다.](media/FBCimage48.png)

6. <span data-ttu-id="45a9b-253">**Facebook을 사용 하 여 로그인을**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="45a9b-253">Click **Login with Facebook**.</span></span>

   ![Facebook을 사용 하 여 \* \* 로그인을 클릭 합니다.](media/FBCimage49.png)

7. <span data-ttu-id="45a9b-255">**Facebook에 로그인** 페이지에서 조직의 Facebook Business 페이지에 대 한 계정의 자격 증명을 사용 하 여 로그인 합니다.</span><span class="sxs-lookup"><span data-stu-id="45a9b-255">On the **Log in to Facebook** page, log in using the credentials for the account for your organization’s Facebook Business pages.</span></span> <span data-ttu-id="45a9b-256">로그인 한 Facebook 계정에 조직의 Facebook Business 페이지에 대 한 관리자 역할이 할당 되었는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="45a9b-256">Make sure the Facebook account that you logged in to is assigned the admin role for your organization’s Facebook Business pages</span></span>

   ![Facebook에 로그인](media/FBCimage50.png)

8. <span data-ttu-id="45a9b-258">**페이지 선택을** 클릭 하 여 Office 365에서 보관 하려는 조직의 비즈니스 페이지를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="45a9b-258">Click **Select Pages** to choose your organization’s business pages that you want to archive in Office 365.</span></span>

   ![페이지 선택을 클릭 하 여 조직의 비즈니스 페이지를 표시 합니다.](media/FBCimage51.png)

9. <span data-ttu-id="45a9b-260">로그인 한 Facebook 계정으로 관리 되는 비즈니스 페이지 목록이 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="45a9b-260">A list of the Business pages managed by the Facebook account that you logged in to is displayed.</span></span> <span data-ttu-id="45a9b-261">보관할 페이지를 선택 하 고 **저장**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="45a9b-261">Select the page to archive and then click **Save**.</span></span>

    ![보관 하려는 조직 비즈니스 페이지를 선택 합니다.](media/FBCimage52.png)

10. <span data-ttu-id="45a9b-263">**마침** 을 클릭 하 여 커넥터 서비스 앱의 설정을 종료 합니다.</span><span class="sxs-lookup"><span data-stu-id="45a9b-263">Click **Finish** to exit the setup of the connector service app.</span></span>

    ![마침을 클릭 하 여 커넥터 서비스 앱을 종료 합니다.](media/FBCimage53.png)

11. <span data-ttu-id="45a9b-265">**필터 설정** 페이지에서 특정 연령 인 항목을 가져오고 보관 하는 필터를 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="45a9b-265">On the **Set Filters** page, you can apply a filter to import (and archive) items that are a certain age.</span></span> <span data-ttu-id="45a9b-266">**다음**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="45a9b-266">Click **Next**.</span></span>

    ![필터를 적용 하 여 특정 연령 인 항목 가져오기](media/FBCimage54.png)

12. <span data-ttu-id="45a9b-268">**저장소 계정 설정** 페이지에서 이전에 선택한 Facebook 비즈니스 페이지의 항목을 가져올 Office 365 사서함을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="45a9b-268">On the **Set Storage Account** page, select the Office 365 mailbox that the items from the Facebook Business pages that you previously selected will be imported to.</span></span>

    ![Facebook에서 가져온 Office 365 사서함 보관 항목 지정](media/FBCimage55.png)

13. <span data-ttu-id="45a9b-270">설정을 검토 하 고 **마침을** 클릭 하 여 보안 & 준수 센터에서 커넥터 설정을 완료 합니다.</span><span class="sxs-lookup"><span data-stu-id="45a9b-270">Review your settings and then click **Finish** to complete the connector setup in the Security & Compliance Center.</span></span>

    ![커넥터 설정 검토](media/FBCimage56.png)

14. <span data-ttu-id="45a9b-272">**타사 데이터 보관** 페이지로 이동 하 여 가져오기 프로세스의 진행 상황을 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="45a9b-272">Go to the **Archive third-party data** page to see the progress of the import process.</span></span>

    ![가져오기 프로세스를 추적 하기 위해 보관 된 타사 데이터 페이지로 이동 합니다.](media/FBCimage58.png)
