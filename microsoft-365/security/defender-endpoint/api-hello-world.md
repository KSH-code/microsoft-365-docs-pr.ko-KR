---
title: Endpoint API용 Microsoft Defender용 Hello World
ms.reviewer: ''
description: 끝점 API용 Microsoft Defender에 대한 'Hello world' 스타일 API 호출을 생성합니다.
keywords: api, 지원되는 api, 고급 헌팅, 쿼리, Microsoft Defender atp, 끝점용 Microsoft Defender
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
MS.technology: mde
ms.custom: api
ms.openlocfilehash: 843fe093a2cfb8c328c51676e55f15ae732f7869
ms.sourcegitcommit: 4886457c0d4248407bddec56425dba50bb60d9c4
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/03/2021
ms.locfileid: "53286024"
---
# <a name="microsoft-defender-for-endpoint-api---hello-world"></a><span data-ttu-id="62173-104">Endpoint API용 Microsoft Defender API - Hello World</span><span class="sxs-lookup"><span data-stu-id="62173-104">Microsoft Defender for Endpoint API - Hello World</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="62173-105">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="62173-105">**Applies to:**</span></span>
- [<span data-ttu-id="62173-106">엔드포인트용 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="62173-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)


- <span data-ttu-id="62173-107">끝점용 Microsoft Defender를 경험하고 싶나요?</span><span class="sxs-lookup"><span data-stu-id="62173-107">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="62173-108">무료 평가판에 등록합니다.</span><span class="sxs-lookup"><span data-stu-id="62173-108">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


## <a name="get-alerts-using-a-simple-powershell-script"></a><span data-ttu-id="62173-109">간단한 PowerShell 스크립트를 사용하여 알림 표시</span><span class="sxs-lookup"><span data-stu-id="62173-109">Get Alerts using a simple PowerShell script</span></span>

### <a name="how-long-it-takes-to-go-through-this-example"></a><span data-ttu-id="62173-110">이 예제를 진행하는 데 얼마나 걸리나요?</span><span class="sxs-lookup"><span data-stu-id="62173-110">How long it takes to go through this example?</span></span>
<span data-ttu-id="62173-111">다음 두 단계에서만 5분 정도 걸립니다.</span><span class="sxs-lookup"><span data-stu-id="62173-111">It only takes 5 minutes done in two steps:</span></span>
- <span data-ttu-id="62173-112">응용 프로그램 등록</span><span class="sxs-lookup"><span data-stu-id="62173-112">Application registration</span></span>
- <span data-ttu-id="62173-113">예제 사용: 짧은 PowerShell 스크립트의 복사/붙여넣기만 필요</span><span class="sxs-lookup"><span data-stu-id="62173-113">Use examples: only requires copy/paste of a short PowerShell script</span></span>

### <a name="do-i-need-a-permission-to-connect"></a><span data-ttu-id="62173-114">연결할 수 있는 권한이 필요한가요?</span><span class="sxs-lookup"><span data-stu-id="62173-114">Do I need a permission to connect?</span></span>
<span data-ttu-id="62173-115">응용 프로그램 등록 단계의 경우  Azure AD(Azure AD) 테넌트에 Azure Active Directory 전역 관리자 역할이 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="62173-115">For the Application registration stage, you must have a **Global administrator** role in your Azure Active Directory (Azure AD) tenant.</span></span>

### <a name="step-1---create-an-app-in-azure-active-directory"></a><span data-ttu-id="62173-116">1단계 - 앱에서 앱 Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="62173-116">Step 1 - Create an App in Azure Active Directory</span></span>

1. <span data-ttu-id="62173-117">전역 관리자 [사용자로 Azure에](https://portal.azure.com) **로그온합니다.**</span><span class="sxs-lookup"><span data-stu-id="62173-117">Log on to [Azure](https://portal.azure.com) with your **Global administrator** user.</span></span>

2. <span data-ttu-id="62173-118">앱 등록 **Azure Active Directory**  >  **새**  >  **등록으로 이동합니다.**</span><span class="sxs-lookup"><span data-stu-id="62173-118">Navigate to **Azure Active Directory** > **App registrations** > **New registration**.</span></span>

   ![응용 Microsoft Azure 탐색 및 이미지](images/atp-azure-new-app2.png)

3. <span data-ttu-id="62173-120">등록 양식에서 응용 프로그램의 이름을 선택하고 등록을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="62173-120">In the registration form, choose a name for your application and then click **Register**.</span></span>

4. <span data-ttu-id="62173-121">응용 프로그램이 끝점용 Defender에 액세스하여 '모든 경고 읽기' 권한을 **할당하도록 허용합니다.**</span><span class="sxs-lookup"><span data-stu-id="62173-121">Allow your Application to access Defender for Endpoint and assign it **'Read all alerts'** permission:</span></span>

   - <span data-ttu-id="62173-122">응용 프로그램 페이지에서 **조직에서** 사용하는 API 권한 추가 API를 클릭하고  >    >   **windowsDefenderATP를 > WindowsDefenderATP를** **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="62173-122">On your application page, click **API Permissions** > **Add permission** > **APIs my organization uses** > type **WindowsDefenderATP** and click on **WindowsDefenderATP**.</span></span>

   - <span data-ttu-id="62173-123">**참고:** WindowsDefenderATP가 원래 목록에 나타나지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="62173-123">**Note**: WindowsDefenderATP does not appear in the original list.</span></span> <span data-ttu-id="62173-124">표시하려면 텍스트 상자에 이름을 쓰기 시작해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="62173-124">You need to start writing its name in the text box to see it appear.</span></span>

   ![API 액세스 및 API 선택의 이미지1](images/add-permission.png)

   - <span data-ttu-id="62173-126">응용 **프로그램 권한**  >  **경고.읽기.>** 권한 추가 클릭 **선택**</span><span class="sxs-lookup"><span data-stu-id="62173-126">Choose **Application permissions** > **Alert.Read.All** > Click on **Add permissions**</span></span>

   ![API 액세스 및 API 선택의 이미지2](images/application-permissions.png)

   <span data-ttu-id="62173-128">**중요 참고** 사항: 관련 권한을 선택해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="62173-128">**Important note**: You need to select the relevant permissions.</span></span> <span data-ttu-id="62173-129">'모든 경고 읽기'는 예시일 뿐입니다.</span><span class="sxs-lookup"><span data-stu-id="62173-129">'Read All Alerts' is only an example!</span></span>

     <span data-ttu-id="62173-130">예를 들어</span><span class="sxs-lookup"><span data-stu-id="62173-130">For instance,</span></span>

     - <span data-ttu-id="62173-131">고급 [쿼리를 실행하려면](run-advanced-query-api.md)'고급 쿼리 실행' 사용 권한을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="62173-131">To [run advanced queries](run-advanced-query-api.md), select 'Run advanced queries' permission</span></span>
     - <span data-ttu-id="62173-132">컴퓨터 [격리하려면](isolate-machine.md)'컴퓨터 격리' 사용 권한을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="62173-132">To [isolate a machine](isolate-machine.md), select 'Isolate machine' permission</span></span>
     - <span data-ttu-id="62173-133">필요한 사용 권한을 확인하려면 호출할  API의 사용 권한 섹션을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="62173-133">To determine which permission you need, please look at the **Permissions** section in the API you are interested to call.</span></span>

5. <span data-ttu-id="62173-134">동의 **부여를 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="62173-134">Click **Grant consent**</span></span>

   - <span data-ttu-id="62173-135">**참고:** 권한을 추가할 때마다 새  사용 권한을 적용하기 위해 동의 부여를 클릭해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="62173-135">**Note**: Every time you add permission you must click on **Grant consent** for the new permission to take effect.</span></span>

   ![권한 부여 이미지](images/grant-consent.png)

6. <span data-ttu-id="62173-137">응용 프로그램에 비밀을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="62173-137">Add a secret to the application.</span></span>

   - <span data-ttu-id="62173-138">인증서를 **&,** 비밀에 설명을 추가하고 추가를 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="62173-138">Click **Certificates & secrets**, add description to the secret and click **Add**.</span></span>

    <span data-ttu-id="62173-139">**중요:** 추가를 클릭한 후 생성된 **비밀 값을 복사합니다.**</span><span class="sxs-lookup"><span data-stu-id="62173-139">**Important**: After click Add, **copy the generated secret value**.</span></span> <span data-ttu-id="62173-140">나가면 검색할 수 없습니다!</span><span class="sxs-lookup"><span data-stu-id="62173-140">You won't be able to retrieve after you leave!</span></span>

    ![앱 키 만들기 이미지](images/webapp-create-key2.png)

7. <span data-ttu-id="62173-142">응용 프로그램 ID 및 테넌트 ID를 기록해 써야 합니다.</span><span class="sxs-lookup"><span data-stu-id="62173-142">Write down your application ID and your tenant ID:</span></span>

   - <span data-ttu-id="62173-143">응용 프로그램 페이지에서 개요로 **이동하여** 다음을 복사합니다.</span><span class="sxs-lookup"><span data-stu-id="62173-143">On your application page, go to **Overview** and copy the following:</span></span>

   ![생성된 앱 ID의 이미지](images/app-and-tenant-ids.png)

<span data-ttu-id="62173-145">완료!</span><span class="sxs-lookup"><span data-stu-id="62173-145">Done!</span></span> <span data-ttu-id="62173-146">응용 프로그램을 성공적으로 등록했습니다.</span><span class="sxs-lookup"><span data-stu-id="62173-146">You have successfully registered an application!</span></span>

### <a name="step-2---get-a-token-using-the-app-and-use-this-token-to-access-the-api"></a><span data-ttu-id="62173-147">2단계 - 앱을 사용하여 토큰을 다운로드하고 이 토큰을 사용하여 API에 액세스합니다.</span><span class="sxs-lookup"><span data-stu-id="62173-147">Step 2 - Get a token using the App and use this token to access the API.</span></span>

- <span data-ttu-id="62173-148">아래 스크립트를 PowerShell ISE 또는 텍스트 편집기로 복사하고 **"** Get-Token.ps1"</span><span class="sxs-lookup"><span data-stu-id="62173-148">Copy the script below to PowerShell ISE or to a text editor, and save it as "**Get-Token.ps1**"</span></span>
- <span data-ttu-id="62173-149">이 스크립트를 실행하면 토큰이 생성되고 ""라는 이름의 작업 **폴더에Latest-token.txt.**</span><span class="sxs-lookup"><span data-stu-id="62173-149">Running this script will generate a token and will save it in the working folder under the name "**Latest-token.txt**".</span></span>

   ```powershell
   # That code gets the App Context Token and save it to a file named "Latest-token.txt" under the current directory
   # Paste below your Tenant ID, App ID and App Secret (App key).

   $tenantId = '' ### Paste your tenant ID here
   $appId = '' ### Paste your Application ID here
   $appSecret = '' ### Paste your Application secret here

   $resourceAppIdUri = 'https://api.securitycenter.microsoft.com'
   $oAuthUri = "https://login.microsoftonline.com/$TenantId/oauth2/token"
   $authBody = [Ordered] @{
       resource = "$resourceAppIdUri"
       client_id = "$appId"
       client_secret = "$appSecret"
       grant_type = 'client_credentials'
   }
   $authResponse = Invoke-RestMethod -Method Post -Uri $oAuthUri -Body $authBody -ErrorAction Stop
   $token = $authResponse.access_token
   Out-File -FilePath "./Latest-token.txt" -InputObject $token
   return $token
   ```

- <span data-ttu-id="62173-150">다음을 검사합니다.</span><span class="sxs-lookup"><span data-stu-id="62173-150">Sanity Check:</span></span>
  - <span data-ttu-id="62173-151">스크립트를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="62173-151">Run the script.</span></span>
  - <span data-ttu-id="62173-152">브라우저에서 다음으로 이동하세요. <https://jwt.ms/></span><span class="sxs-lookup"><span data-stu-id="62173-152">In your browser go to: <https://jwt.ms/></span></span>
  - <span data-ttu-id="62173-153">토큰(Latest-token.txt 복사합니다.</span><span class="sxs-lookup"><span data-stu-id="62173-153">Copy the token (the content of the Latest-token.txt file).</span></span>
  - <span data-ttu-id="62173-154">위쪽 상자에 붙여 넣습니다.</span><span class="sxs-lookup"><span data-stu-id="62173-154">Paste in the top box.</span></span>
  - <span data-ttu-id="62173-155">"역할" 섹션을 찾아 봐야 합니다.</span><span class="sxs-lookup"><span data-stu-id="62173-155">Look for the "roles" section.</span></span> <span data-ttu-id="62173-156">Alert.Read.All 역할을 찾아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="62173-156">Find the Alert.Read.All role.</span></span>

  ![이미지 jwt.ms](images/api-jwt-ms.png)

### <a name="lets-get-the-alerts"></a><span data-ttu-id="62173-158">경고를 받을 수 있습니다!</span><span class="sxs-lookup"><span data-stu-id="62173-158">Lets get the Alerts!</span></span>

- <span data-ttu-id="62173-159">아래 스크립트는 **Get-Token.ps1** API에 액세스하고 지난 48시간 동안의 알림을 받을 것입니다.</span><span class="sxs-lookup"><span data-stu-id="62173-159">The script below will use **Get-Token.ps1** to access the API and will get the past 48 hours Alerts.</span></span>
- <span data-ttu-id="62173-160">이전 스크립트 파일을 저장한 폴더에 이 스크립트를 **Get-Token.ps1.**</span><span class="sxs-lookup"><span data-stu-id="62173-160">Save this script in the same folder you saved the previous script **Get-Token.ps1**.</span></span>
- <span data-ttu-id="62173-161">스크립트는 스크립트와 동일한 폴더에 데이터를 사용하여 두 개의 파일(json 및 csv)을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="62173-161">The script creates two files (json and csv) with the data in the same folder as the scripts.</span></span>

  ```powershell
  # Returns Alerts created in the past 48 hours.

  $token = ./Get-Token.ps1       #run the script Get-Token.ps1  - make sure you are running this script from the same folder of Get-Token.ps1

  # Get Alert from the last 48 hours. Make sure you have alerts in that time frame.
  $dateTime = (Get-Date).ToUniversalTime().AddHours(-48).ToString("o")

  # The URL contains the type of query and the time filter we create above
  # Read more about other query options and filters at   Https://TBD- add the documentation link
  $url = "https://api.securitycenter.microsoft.com/api/alerts?`$filter=alertCreationTime ge $dateTime"

  # Set the WebRequest headers
  $headers = @{
      'Content-Type' = 'application/json'
      Accept = 'application/json'
      Authorization = "Bearer $token"
  }

  # Send the webrequest and get the results.
  $response = Invoke-WebRequest -Method Get -Uri $url -Headers $headers -ErrorAction Stop

  # Extract the alerts from the results.
  $alerts =  ($response | ConvertFrom-Json).value | ConvertTo-Json

  # Get string with the execution time. We concatenate that string to the output file to avoid overwrite the file
  $dateTimeForFileName = Get-Date -Format o | foreach {$_ -replace ":", "."}

  # Save the result as json and as csv
  $outputJsonPath = "./Latest Alerts $dateTimeForFileName.json"
  $outputCsvPath = "./Latest Alerts $dateTimeForFileName.csv"

  Out-File -FilePath $outputJsonPath -InputObject $alerts
  ($alerts | ConvertFrom-Json) | Export-CSV $outputCsvPath -NoTypeInformation
  ```

<span data-ttu-id="62173-162">모두 완료했습니다!</span><span class="sxs-lookup"><span data-stu-id="62173-162">You're all done!</span></span> <span data-ttu-id="62173-163">다음을 성공적으로 완료했습니다.</span><span class="sxs-lookup"><span data-stu-id="62173-163">You have just successfully:</span></span>

- <span data-ttu-id="62173-164">생성 및 등록 및 응용 프로그램</span><span class="sxs-lookup"><span data-stu-id="62173-164">Created and registered and application</span></span>
- <span data-ttu-id="62173-165">경고를 읽을 수 있는 해당 응용 프로그램에 대한 사용 권한 부여</span><span class="sxs-lookup"><span data-stu-id="62173-165">Granted permission for that application to read alerts</span></span>
- <span data-ttu-id="62173-166">API 연결</span><span class="sxs-lookup"><span data-stu-id="62173-166">Connected the API</span></span>
- <span data-ttu-id="62173-167">PowerShell 스크립트를 사용하여 지난 48시간 동안 생성된 경고 반환</span><span class="sxs-lookup"><span data-stu-id="62173-167">Used a PowerShell script to return alerts created in the past 48 hours</span></span>

## <a name="related-topic"></a><span data-ttu-id="62173-168">관련 항목</span><span class="sxs-lookup"><span data-stu-id="62173-168">Related topic</span></span>

- [<span data-ttu-id="62173-169">끝점 API용 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="62173-169">Microsoft Defender for Endpoint APIs</span></span>](exposed-apis-list.md)
- [<span data-ttu-id="62173-170">응용 프로그램 컨텍스트를 통해 끝점용 Microsoft Defender 액세스</span><span class="sxs-lookup"><span data-stu-id="62173-170">Access Microsoft Defender for Endpoint with application context</span></span>](exposed-apis-create-app-webapp.md)
- [<span data-ttu-id="62173-171">사용자 컨텍스트를 통해 끝점용 Microsoft Defender 액세스</span><span class="sxs-lookup"><span data-stu-id="62173-171">Access Microsoft Defender for Endpoint with user context</span></span>](exposed-apis-create-app-nativeapp.md)
