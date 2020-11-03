---
title: Microsoft 365 Defender REST API에 대 한 Hello World
description: 앱을 만들고 토큰을 사용 하 여 Microsoft 365 Defender Api에 액세스 하는 방법을 알아봅니다.
keywords: 앱, 토큰, access, aad, 앱, 응용 프로그램 등록, powershell, 스크립트, 전역 관리자, 사용 권한
search.product: eADQiWindows 10XVcnh
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.openlocfilehash: bd4f7e5485d67cf74477900ae2cc5c77f1a6ee41
ms.sourcegitcommit: 815229e39a0f905d9f06717f00dc82e2a028fa7c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/03/2020
ms.locfileid: "48844047"
---
# <a name="hello-world-for-microsoft-365-defender-rest-api"></a><span data-ttu-id="1db64-104">Microsoft 365 Defender REST API에 대 한 Hello World</span><span class="sxs-lookup"><span data-stu-id="1db64-104">Hello World for Microsoft 365 Defender REST API</span></span> 

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="1db64-105">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="1db64-105">**Applies to:**</span></span>
- <span data-ttu-id="1db64-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="1db64-106">Microsoft 365 Defender</span></span>

>[!IMPORTANT] 
><span data-ttu-id="1db64-107">일부 정보는 상업적으로 출시 되기 전에 크게 수정 될 수 있는 prereleased 제품과 관련 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1db64-107">Some information relates to prereleased product which may be substantially modified before it's commercially released.</span></span> <span data-ttu-id="1db64-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span><span class="sxs-lookup"><span data-stu-id="1db64-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span></span>


## <a name="get-incidents-using-a-simple-powershell-script"></a><span data-ttu-id="1db64-109">간단한 PowerShell 스크립트를 사용 하 여 인시던트 가져오기</span><span class="sxs-lookup"><span data-stu-id="1db64-109">Get incidents using a simple PowerShell script</span></span>

### <a name="how-long-it-takes-to-go-through-this-example"></a><span data-ttu-id="1db64-110">이 예제를 진행 하는 데 소요 되는 시간은 얼마나 됩니까?</span><span class="sxs-lookup"><span data-stu-id="1db64-110">How long it takes to go through this example?</span></span>
<span data-ttu-id="1db64-111">다음 두 단계를 수행 하는 데 5 분 정도 소요 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1db64-111">It only takes 5 minutes done in two steps:</span></span>
- <span data-ttu-id="1db64-112">응용 프로그램 등록</span><span class="sxs-lookup"><span data-stu-id="1db64-112">Application registration</span></span>
- <span data-ttu-id="1db64-113">예를 사용 합니다. 짧은 PowerShell 스크립트의 복사/붙여넣기만 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="1db64-113">Use examples: only requires copy/paste of a short PowerShell script</span></span>

### <a name="do-i-need-a-permission-to-connect"></a><span data-ttu-id="1db64-114">연결할 수 있는 권한이 필요 한가요?</span><span class="sxs-lookup"><span data-stu-id="1db64-114">Do I need a permission to connect?</span></span>
<span data-ttu-id="1db64-115">응용 프로그램 등록 단계의 azure AD (Active Directory) 테 넌 트에서 **전역 관리자** 역할이 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1db64-115">For the Application registration stage, you must have a **Global administrator** role in your Azure Active Directory (Azure AD) tenant.</span></span>

### <a name="step-1---create-an-app-in-azure-active-directory"></a><span data-ttu-id="1db64-116">1 단계-Azure Active Directory에서 앱 만들기</span><span class="sxs-lookup"><span data-stu-id="1db64-116">Step 1 - Create an App in Azure Active Directory</span></span>

1. <span data-ttu-id="1db64-117">**전역 관리자** 사용자와 함께 [Azure](https://portal.azure.com) 에 로그온 합니다.</span><span class="sxs-lookup"><span data-stu-id="1db64-117">Log on to [Azure](https://portal.azure.com) with your **Global administrator** user.</span></span>

2. <span data-ttu-id="1db64-118">**Azure Active Directory**  >  **앱 등록**  >  **새 등록** 으로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="1db64-118">Navigate to **Azure Active Directory** > **App registrations** > **New registration**.</span></span> 

   ![Microsoft Azure 이미지 및 응용 프로그램 등록에 대 한 탐색](../../media/atp-azure-new-app2.png)

3. <span data-ttu-id="1db64-120">등록 양식에서 응용 프로그램의 이름을 선택한 다음 **등록** 을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="1db64-120">In the registration form, choose a name for your application and then select **Register**.</span></span>

4. <span data-ttu-id="1db64-121">응용 프로그램에서 Microsoft Defender for Endpoint에 액세스 하 고 **모든 인시던트 읽기** 권한을 할당할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="1db64-121">Allow your Application to access Microsoft Defender for Endpoint and assign it **Read all incidents** permission:</span></span>

   - <span data-ttu-id="1db64-122">응용 프로그램 페이지에서 **api 사용 권한을** 선택 합니다.  >  **Add permission**  >  **내 조직에서 사용 하** > 사용 권한 api 추가 **microsoft 365 defender** 를 입력 하 고 **microsoft 365 defender** 를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="1db64-122">On your application page, select **API Permissions** > **Add permission** > **APIs my organization uses** > type **Microsoft 365 Defender** and select on **Microsoft 365 Defender**.</span></span>

   >[!NOTE]
   ><span data-ttu-id="1db64-123">Microsoft 365 Defender가 원래 목록에 표시 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="1db64-123">Microsoft 365 Defender does not appear in the original list.</span></span> <span data-ttu-id="1db64-124">텍스트 상자에 이름을 입력 하 여 표시 되는지 확인 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1db64-124">You need to start writing its name in the text box to see it appear.</span></span>

   ![API 액세스 및 API 선택 이미지](../../media/apis-in-my-org-tab.PNG)

   - <span data-ttu-id="1db64-126">**응용 프로그램 사용 권한** 인시던트를 선택 합니다.  >  **모든** > **사용 권한 추가** 를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="1db64-126">Choose **Application permissions** > **Incident.Read.All** > Select on **Add permissions**</span></span>

   ![API 액세스 및 API 선택 이미지](../../media/request-api-permissions.PNG)

   >[!IMPORTANT]
   ><span data-ttu-id="1db64-128">관련 사용 권한을 선택 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1db64-128">You need to select the relevant permissions.</span></span> 

     <span data-ttu-id="1db64-129">예를 들어</span><span class="sxs-lookup"><span data-stu-id="1db64-129">For instance,</span></span>

     - <span data-ttu-id="1db64-130">필요한 사용 권한을 확인 하려면 통화할 API에서 **사용 권한** 섹션을 확인 하세요.</span><span class="sxs-lookup"><span data-stu-id="1db64-130">To determine which permission you need, please look at the **Permissions** section in the API you are interested to call.</span></span>

5. <span data-ttu-id="1db64-131">**관리자 동의 부여** 선택</span><span class="sxs-lookup"><span data-stu-id="1db64-131">Select **Grant admin consent**</span></span>

    - >[!NOTE]
      > <span data-ttu-id="1db64-132">사용 권한을 추가할 때마다 새 사용 권한이 적용 되려면 **동의** 함을 선택 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1db64-132">Every time you add permission you must select on **Grant consent** for the new permission to take effect.</span></span>

    ![권한 부여 이미지](../../media/grant-consent.PNG)

6. <span data-ttu-id="1db64-134">응용 프로그램에 비밀을 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="1db64-134">Add a secret to the application.</span></span>

    - <span data-ttu-id="1db64-135">**인증서 & 비밀** 을 선택 하 고 비밀에 대 한 설명을 추가한 후 **추가** 를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="1db64-135">Select **Certificates & secrets** , add description to the secret and select **Add**.</span></span>

    >[!IMPORTANT]
    > <span data-ttu-id="1db64-136">**추가** 를 선택한 후에 **생성 된 비밀 값을 복사** 합니다.</span><span class="sxs-lookup"><span data-stu-id="1db64-136">After selecting **Add** , **copy the generated secret value**.</span></span> <span data-ttu-id="1db64-137">나간 후에는 검색할 수 없게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1db64-137">You won't be able to retrieve after you leave!</span></span>

    ![앱 만들기 키의 이미지](../../media/webapp-create-key2.png)

7. <span data-ttu-id="1db64-139">응용 프로그램 ID 및 테 넌 트 ID를 적어 둡니다.</span><span class="sxs-lookup"><span data-stu-id="1db64-139">Write down your application ID and your tenant ID:</span></span>

   - <span data-ttu-id="1db64-140">응용 프로그램 페이지에서 **개요** 로 이동 하 여 다음을 복사 합니다.</span><span class="sxs-lookup"><span data-stu-id="1db64-140">On your application page, go to **Overview** and copy the following:</span></span>

   ![만든 앱 id의 이미지](../../media/app-and-tenant-ids.png)


<span data-ttu-id="1db64-142">수행!</span><span class="sxs-lookup"><span data-stu-id="1db64-142">Done!</span></span> <span data-ttu-id="1db64-143">응용 프로그램을 성공적으로 등록 했습니다.</span><span class="sxs-lookup"><span data-stu-id="1db64-143">You have successfully registered an application.</span></span>

### <a name="step-2---get-a-token-using-the-app-and-use-this-token-to-access-the-api"></a><span data-ttu-id="1db64-144">2 단계-앱을 사용 하 여 토큰을 가져오고이 토큰을 사용 하 여 API에 액세스 합니다.</span><span class="sxs-lookup"><span data-stu-id="1db64-144">Step 2 - Get a token using the App and use this token to access the API.</span></span>

-   <span data-ttu-id="1db64-145">PowerShell ISE 또는 텍스트 편집기에 아래 스크립트를 복사 하 여 " **Get-Token.ps1** "로 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="1db64-145">Copy the script below to PowerShell ISE or to a text editor, and save it as " **Get-Token.ps1** "</span></span>
-   <span data-ttu-id="1db64-146">이 스크립트를 실행 하면 토큰이 생성 되 고 작업 폴더의 " **Latest-token.txt** " 이름 아래에 저장 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1db64-146">Running this script will generate a token and will save it in the working folder under the name " **Latest-token.txt** ".</span></span>

```
# That code gets the App Context Token and save it to a file named "Latest-token.txt" under the current directory
# Paste below your Tenant ID, App ID and App Secret (App key).

$tenantId = '' ### Paste your tenant ID here
$appId = '' ### Paste your Application ID here
$appSecret = '' ### Paste your Application secret here

$resourceAppIdUri = 'https://api.security.microsoft.com'
$oAuthUri = "https://login.windows.net/$TenantId/oauth2/token"
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

-   <span data-ttu-id="1db64-147">온전성 검사:</span><span class="sxs-lookup"><span data-stu-id="1db64-147">Sanity Check:</span></span><br>
<span data-ttu-id="1db64-148">스크립트를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="1db64-148">Run the script.</span></span><br>
<span data-ttu-id="1db64-149">브라우저에서 다음 위치로 이동 합니다. https://jwt.ms/</span><span class="sxs-lookup"><span data-stu-id="1db64-149">In your browser go to: https://jwt.ms/</span></span> <br>
<span data-ttu-id="1db64-150">토큰 (Latest-token.txt 파일의 내용)을 복사 합니다.</span><span class="sxs-lookup"><span data-stu-id="1db64-150">Copy the token (the content of the Latest-token.txt file).</span></span><br>
<span data-ttu-id="1db64-151">맨 위 상자에 붙여 넣습니다.</span><span class="sxs-lookup"><span data-stu-id="1db64-151">Paste in the top box.</span></span><br>
<span data-ttu-id="1db64-152">"역할" 섹션을 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="1db64-152">Look for the "roles" section.</span></span> <span data-ttu-id="1db64-153">역할을 찾습니다 ```Incidents.Read.All``` .</span><span class="sxs-lookup"><span data-stu-id="1db64-153">Find the ```Incidents.Read.All``` role.</span></span><br>
<span data-ttu-id="1db64-154">다음 예제는 ```Incidents.Read.All``` ```Incidents.ReadWrite.All``` 및 사용 권한을 가진 앱에서 가져온 것입니다 ```AdvancedHunting.Read.All``` .</span><span class="sxs-lookup"><span data-stu-id="1db64-154">The below example is from an app that has ```Incidents.Read.All```, ```Incidents.ReadWrite.All``` and ```AdvancedHunting.Read.All``` permissions.</span></span>

![이미지 jwt.ms](../../media/api-jwt-ms.png)

### <a name="lets-get-the-incidents"></a><span data-ttu-id="1db64-156">인시던트를 받을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1db64-156">Lets get the Incidents!</span></span>

-   <span data-ttu-id="1db64-157">아래의 스크립트는 **Get-Token.ps1** 을 사용 하 여 API에 액세스 하 고 지난 48 시간 동안 마지막으로 업데이트 된 인시던트를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="1db64-157">The script below will use **Get-Token.ps1** to access the API and will get the incidents last updated in past 48 hours.</span></span>
-   <span data-ttu-id="1db64-158">이전 스크립트 **Get-Token.ps1** 저장 한 폴더에이 스크립트를 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="1db64-158">Save this script in the same folder you saved the previous script **Get-Token.ps1**.</span></span> 
-   <span data-ttu-id="1db64-159">스크립트와 동일한 폴더에 데이터가 포함 된 json 파일을 스크립팅 합니다.</span><span class="sxs-lookup"><span data-stu-id="1db64-159">The script a json file with the data in the same folder as the scripts.</span></span>

```
# Returns Incidents last updated in the past 48 hours.

$token = ./Get-Token.ps1       #run the script Get-Token.ps1  - make sure you are running this script from the same folder of Get-Token.ps1

# Get Incidents from the last 48 hours. Make sure you have incidents in that time frame.
$dateTime = (Get-Date).ToUniversalTime().AddHours(-48).ToString("o")

# The URL contains the type of query and the time filter we created above
$url = "https://api.security.microsoft.com/api/incidents?$filter=lastUpdateTime+ge+$dateTime"

# Set the WebRequest headers
$headers = @{ 
    'Content-Type' = 'application/json'
    'Accept' = 'application/json'
    'Authorization' = "Bearer $token"
}

# Send the webrequest and get the results. 
$response = Invoke-WebRequest -Method Get -Uri $url -Headers $headers -ErrorAction Stop

# Extract the incidents from the results. 
$incidents =  ($response | ConvertFrom-Json).value | ConvertTo-Json -Depth 99

# Get string with the execution time. We concatenate that string to the output file to avoid overwrite the file
$dateTimeForFileName = Get-Date -Format o | foreach {$_ -replace ":", "."}    

# Save the result as json
$outputJsonPath = "./Latest Incidents $dateTimeForFileName.json"     

Out-File -FilePath $outputJsonPath -InputObject $incidents 
```

<span data-ttu-id="1db64-160">모두 완료 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="1db64-160">You're all done!</span></span> <span data-ttu-id="1db64-161">방금 작업을 완료 했습니다.</span><span class="sxs-lookup"><span data-stu-id="1db64-161">You have just successfully:</span></span>
-   <span data-ttu-id="1db64-162">작성 및 등록 및 응용 프로그램</span><span class="sxs-lookup"><span data-stu-id="1db64-162">Created and registered and application</span></span>
-   <span data-ttu-id="1db64-163">해당 응용 프로그램에 대 한 경고를 읽을 수 있는 권한 부여</span><span class="sxs-lookup"><span data-stu-id="1db64-163">Granted permission for that application to read alerts</span></span>
-   <span data-ttu-id="1db64-164">API 연결 됨</span><span class="sxs-lookup"><span data-stu-id="1db64-164">Connected the API</span></span>
-   <span data-ttu-id="1db64-165">PowerShell 스크립트를 사용 하 여 지난 48 시간 동안 만들어진 인시던트를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="1db64-165">Used a PowerShell script to return incidents created in the past 48 hours</span></span>



## <a name="related-topic"></a><span data-ttu-id="1db64-166">관련 항목</span><span class="sxs-lookup"><span data-stu-id="1db64-166">Related topic</span></span>
- [<span data-ttu-id="1db64-167">Microsoft 365 Defender Api 액세스</span><span class="sxs-lookup"><span data-stu-id="1db64-167">Access the Microsoft 365 Defender APIs</span></span>](api-access.md)
- [<span data-ttu-id="1db64-168">응용 프로그램 컨텍스트를 사용 하 여 Microsoft 365 Defender에 액세스</span><span class="sxs-lookup"><span data-stu-id="1db64-168">Access  Microsoft 365 Defender with application context</span></span>](api-create-app-web.md)
- [<span data-ttu-id="1db64-169">사용자 컨텍스트를 사용 하 여 Microsoft 365 Defender 액세스</span><span class="sxs-lookup"><span data-stu-id="1db64-169">Access  Microsoft 365 Defender with user context</span></span>](api-create-app-user-context.md)
