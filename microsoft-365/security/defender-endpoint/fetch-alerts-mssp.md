---
title: MSSP 고객 테넌트에서 경고 페치
description: 고객 테넌트에서 경고를 페치하는 방법 학습
keywords: 관리되는 보안 서비스 공급자, mssp, 구성, 통합
search.product: eADQiWindows 10XVcnh
search.appverid: met150
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
ms.technology: mde
ms.custom: api
ms.openlocfilehash: 456507533265bc085adc1008f3264e123569a6ca
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/04/2021
ms.locfileid: "52770772"
---
# <a name="fetch-alerts-from-mssp-customer-tenant"></a><span data-ttu-id="160b3-104">MSSP 고객 테넌트에서 경고 페치</span><span class="sxs-lookup"><span data-stu-id="160b3-104">Fetch alerts from MSSP customer tenant</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="160b3-105">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="160b3-105">**Applies to:**</span></span>
- [<span data-ttu-id="160b3-106">엔드포인트용 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="160b3-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)

><span data-ttu-id="160b3-107">끝점용 Microsoft Defender를 경험하고 싶나요?</span><span class="sxs-lookup"><span data-stu-id="160b3-107">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="160b3-108">무료 평가판에 등록합니다.</span><span class="sxs-lookup"><span data-stu-id="160b3-108">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-mssp-support-abovefoldlink)

>[!NOTE]
><span data-ttu-id="160b3-109">이 작업은 MSSP에서 수행됩니다.</span><span class="sxs-lookup"><span data-stu-id="160b3-109">This action is taken by the MSSP.</span></span>


<span data-ttu-id="160b3-110">경고를 내보는 방법에는 다음 두 가지가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="160b3-110">There are two ways you can fetch alerts:</span></span>
- <span data-ttu-id="160b3-111">SIEM 메서드 사용</span><span class="sxs-lookup"><span data-stu-id="160b3-111">Using the SIEM method</span></span>
- <span data-ttu-id="160b3-112">API 사용</span><span class="sxs-lookup"><span data-stu-id="160b3-112">Using APIs</span></span>

## <a name="fetch-alerts-into-your-siem"></a><span data-ttu-id="160b3-113">SIEM으로 경고 페치</span><span class="sxs-lookup"><span data-stu-id="160b3-113">Fetch alerts into your SIEM</span></span>

<span data-ttu-id="160b3-114">SIEM 시스템으로 경고를 페치하려면 다음 단계를 수행해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="160b3-114">To fetch alerts into your SIEM system, you'll need to take the following steps:</span></span>

<span data-ttu-id="160b3-115">1단계: 타사 응용 프로그램 만들기</span><span class="sxs-lookup"><span data-stu-id="160b3-115">Step 1: Create a third-party application</span></span>

<span data-ttu-id="160b3-116">2단계: 고객의 테넌트에서 토큰 액세스 및 새로 고침</span><span class="sxs-lookup"><span data-stu-id="160b3-116">Step 2: Get access and refresh tokens from your customer's tenant</span></span>
 
<span data-ttu-id="160b3-117">3단계: 응용 프로그램에서 응용 프로그램 허용 Microsoft Defender 보안 센터</span><span class="sxs-lookup"><span data-stu-id="160b3-117">Step 3: allow your application on Microsoft Defender Security Center</span></span>
 
### <a name="step-1-create-an-application-in-azure-active-directory-azure-ad"></a><span data-ttu-id="160b3-118">1단계: Azure AD(Azure Active Directory 응용 프로그램 만들기)</span><span class="sxs-lookup"><span data-stu-id="160b3-118">Step 1: Create an application in Azure Active Directory (Azure AD)</span></span>
 
<span data-ttu-id="160b3-119">응용 프로그램을 만들고 고객의 끝점 테넌트에 대한 Microsoft Defender에서 알림을 보내기 위한 권한을 부여해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="160b3-119">You'll need to create an application and grant it permissions to fetch alerts from your customer's Microsoft Defender for Endpoint tenant.</span></span>

1. <span data-ttu-id="160b3-120">Azure AD [포털에 로그인합니다.](https://aad.portal.azure.com/)</span><span class="sxs-lookup"><span data-stu-id="160b3-120">Sign in to the [Azure AD portal](https://aad.portal.azure.com/).</span></span>

2. <span data-ttu-id="160b3-121">앱 **Azure Active Directory**  >  **등록을 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="160b3-121">Select **Azure Active Directory** > **App registrations**.</span></span>
 
3. <span data-ttu-id="160b3-122">새 **등록 을 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="160b3-122">Click **New registration**.</span></span>

4. <span data-ttu-id="160b3-123">다음 값을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="160b3-123">Specify the following values:</span></span>

    - <span data-ttu-id="160b3-124">이름: \<Tenant_name\> SIEM MSSP 커넥터(테넌트 Tenant_name 이름으로 바꾸기)</span><span class="sxs-lookup"><span data-stu-id="160b3-124">Name: \<Tenant_name\> SIEM MSSP Connector (replace Tenant_name with the tenant display name)</span></span>
 
    - <span data-ttu-id="160b3-125">지원되는 계정 유형: 이 조직 디렉터리의 계정만</span><span class="sxs-lookup"><span data-stu-id="160b3-125">Supported account types: Account in this organizational directory only</span></span> 
    - <span data-ttu-id="160b3-126">리디렉션 URI: 웹을 선택하고 입력(<domain_name> `https://<domain_name>/SiemMsspConnector` 이름으로 바꾸기)</span><span class="sxs-lookup"><span data-stu-id="160b3-126">Redirect URI: Select Web and type `https://<domain_name>/SiemMsspConnector`(replace <domain_name> with the tenant name)</span></span>

5. <span data-ttu-id="160b3-127">등록을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="160b3-127">Click **Register**.</span></span> <span data-ttu-id="160b3-128">응용 프로그램이 소유한 응용 프로그램 목록에 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="160b3-128">The application is displayed in the list of applications you own.</span></span>

6. <span data-ttu-id="160b3-129">응용 프로그램을 선택한 다음 개요 를 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="160b3-129">Select the application, then click **Overview**.</span></span>

7. <span data-ttu-id="160b3-130">응용 프로그램(클라이언트) **ID 필드의** 값을 안전한 장소로 복사하려면 다음 단계에서 이 값이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="160b3-130">Copy the value from the **Application (client) ID** field to a safe place, you will need this in the next step.</span></span>

8. <span data-ttu-id="160b3-131">새 **& 패널에서** 인증서 인증서를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="160b3-131">Select **Certificate & secrets** in the new application panel.</span></span>

9. <span data-ttu-id="160b3-132">새 **클라이언트 비밀 을 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="160b3-132">Click **New client secret**.</span></span>

    - <span data-ttu-id="160b3-133">설명: 키에 대한 설명을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="160b3-133">Description: Enter a description for the key.</span></span>
    - <span data-ttu-id="160b3-134">만료: **1년 후 선택**</span><span class="sxs-lookup"><span data-stu-id="160b3-134">Expires: Select **In 1 year**</span></span>

 
10. <span data-ttu-id="160b3-135">**추가를** 클릭하고 클라이언트 비밀 값을 안전한 장소에 복사합니다. 이 값은 다음 단계에서 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="160b3-135">Click **Add**, copy the value of the client secret to a safe place, you will need this in the next step.</span></span>
 

### <a name="step-2-get-access-and-refresh-tokens-from-your-customers-tenant"></a><span data-ttu-id="160b3-136">2단계: 고객의 테넌트에서 토큰 액세스 및 새로 고침</span><span class="sxs-lookup"><span data-stu-id="160b3-136">Step 2: Get access and refresh tokens from your customer's tenant</span></span>
<span data-ttu-id="160b3-137">이 섹션에서는 PowerShell 스크립트를 사용하여 고객의 테넌트에서 토큰을 다운로드하는 방법을 안내합니다.</span><span class="sxs-lookup"><span data-stu-id="160b3-137">This section guides you on how to use a PowerShell script to get the tokens from your customer's tenant.</span></span> <span data-ttu-id="160b3-138">이 스크립트는 이전 단계의 응용 프로그램을 사용하여 OAuth 권한 부여 코드 응용 프로그램을 사용하여 액세스 및 새로 고침 토큰을 Flow.</span><span class="sxs-lookup"><span data-stu-id="160b3-138">This script uses the application from the previous step to get the access and refresh tokens using the OAuth Authorization Code Flow.</span></span>

<span data-ttu-id="160b3-139">자격 증명을 제공한 후 응용 프로그램이 고객의 테넌트에 프로비전되는 데 필요한 동의를 응용 프로그램에 부여해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="160b3-139">After providing your credentials, you'll need to grant consent to the application so that the application is provisioned in the customer's tenant.</span></span>


1. <span data-ttu-id="160b3-140">새 폴더를 만들고 이름을 로 `MsspTokensAcquisition` 지정합니다. .</span><span class="sxs-lookup"><span data-stu-id="160b3-140">Create a new folder and name it: `MsspTokensAcquisition`.</span></span>

2. <span data-ttu-id="160b3-141">[LoginBrowser.psm1](https://github.com/shawntabrizi/Microsoft-Authentication-with-PowerShell-and-MSAL/blob/master/Authorization%20Code%20Grant%20Flow/LoginBrowser.psm1) 모듈을 다운로드하여 폴더에 `MsspTokensAcquisition` 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="160b3-141">Download the [LoginBrowser.psm1 module](https://github.com/shawntabrizi/Microsoft-Authentication-with-PowerShell-and-MSAL/blob/master/Authorization%20Code%20Grant%20Flow/LoginBrowser.psm1) and save it in the `MsspTokensAcquisition` folder.</span></span>

    >[!NOTE]
    ><span data-ttu-id="160b3-142">줄 30에서 을 로 `authorzationUrl` 바 `authorizationUrl` 대체합니다.</span><span class="sxs-lookup"><span data-stu-id="160b3-142">In line 30, replace `authorzationUrl` with `authorizationUrl`.</span></span>

3. <span data-ttu-id="160b3-143">다음 콘텐츠가 있는 파일을 만들고 폴더의 이름으로 `MsspTokensAcquisition.ps1` 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="160b3-143">Create a file with the following content and save it with the name `MsspTokensAcquisition.ps1` in the folder:</span></span>
    ```
    param (
        [Parameter(Mandatory=$true)][string]$clientId,
        [Parameter(Mandatory=$true)][string]$secret,
        [Parameter(Mandatory=$true)][string]$tenantId
    )
    [Net.ServicePointManager]::SecurityProtocol = [Net.SecurityProtocolType]::Tls12

    # Load our Login Browser Function
    Import-Module .\LoginBrowser.psm1

    # Configuration parameters
    $login = "https://login.microsoftonline.com"
    $redirectUri = "https://SiemMsspConnector"
    $resourceId = "https://graph.windows.net"

    Write-Host 'Prompt the user for his credentials, to get an authorization code'
    $authorizationUrl = ("{0}/{1}/oauth2/authorize?prompt=select_account&response_type=code&client_id={2}&redirect_uri={3}&resource={4}" -f
                        $login, $tenantId, $clientId, $redirectUri, $resourceId)
    Write-Host "authorzationUrl: $authorizationUrl"

    # Fake a proper endpoint for the Redirect URI
    $code = LoginBrowser $authorizationUrl $redirectUri

    # Acquire token using the authorization code

    $Body = @{
        grant_type = 'authorization_code'
        client_id = $clientId
        code = $code
        redirect_uri = $redirectUri
        resource = $resourceId
        client_secret = $secret
    }

    $tokenEndpoint = "$login/$tenantId/oauth2/token?"
    $Response = Invoke-RestMethod -Method Post -Uri $tokenEndpoint -Body $Body
    $token = $Response.access_token
    $refreshToken= $Response.refresh_token

    Write-Host " -----------------------------------  TOKEN ---------------------------------- "
    Write-Host $token

    Write-Host " -----------------------------------  REFRESH TOKEN ---------------------------------- "
    Write-Host $refreshToken 
    ```
4. <span data-ttu-id="160b3-144">폴더에서 상승된 PowerShell 명령 프롬프트를 열 `MsspTokensAcquisition` 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="160b3-144">Open an elevated PowerShell command prompt in the `MsspTokensAcquisition` folder.</span></span>

5. <span data-ttu-id="160b3-145">다음 명령을 실행합니다. `Set-ExecutionPolicy -ExecutionPolicy Bypass`</span><span class="sxs-lookup"><span data-stu-id="160b3-145">Run the following command: `Set-ExecutionPolicy -ExecutionPolicy Bypass`</span></span>

6. <span data-ttu-id="160b3-146">다음 명령을 입력합니다. `.\MsspTokensAcquisition.ps1 -clientId <client_id> -secret <app_key> -tenantId <customer_tenant_id>`</span><span class="sxs-lookup"><span data-stu-id="160b3-146">Enter the following commands: `.\MsspTokensAcquisition.ps1 -clientId <client_id> -secret <app_key> -tenantId <customer_tenant_id>`</span></span>
 
    - <span data-ttu-id="160b3-147">이전 단계에서 얻게 된 응용 \<client_id\> 프로그램(클라이언트) **ID로** 바)</span><span class="sxs-lookup"><span data-stu-id="160b3-147">Replace \<client_id\> with the **Application (client) ID** you got from the previous step.</span></span>
    - <span data-ttu-id="160b3-148">이전 \<app_key\> 단계에서 만든 **클라이언트** 비밀로 바 대체합니다.</span><span class="sxs-lookup"><span data-stu-id="160b3-148">Replace \<app_key\> with the **Client Secret** you created from the previous step.</span></span>
    - <span data-ttu-id="160b3-149">고객의 \<customer_tenant_id\> 테넌트 **ID로 대체합니다.**</span><span class="sxs-lookup"><span data-stu-id="160b3-149">Replace \<customer_tenant_id\> with your customer's **Tenant ID**.</span></span> 
 

7. <span data-ttu-id="160b3-150">자격 증명 및 동의를 제공해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="160b3-150">You'll be asked to provide your credentials and consent.</span></span> <span data-ttu-id="160b3-151">페이지 리디렉션을 무시합니다.</span><span class="sxs-lookup"><span data-stu-id="160b3-151">Ignore the page redirect.</span></span>

8. <span data-ttu-id="160b3-152">PowerShell 창에서 액세스 토큰과 새로 고침 토큰을 받게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="160b3-152">In the PowerShell window, you'll receive an access token and a refresh token.</span></span> <span data-ttu-id="160b3-153">새로 고침 토큰을 저장하여 SIEM 커넥터를 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="160b3-153">Save the refresh token to configure your SIEM connector.</span></span> 
 
### <a name="step-3-allow-your-application-on-microsoft-defender-security-center"></a><span data-ttu-id="160b3-154">3단계: 응용 프로그램에서 응용 프로그램 Microsoft Defender 보안 센터</span><span class="sxs-lookup"><span data-stu-id="160b3-154">Step 3: Allow your application on Microsoft Defender Security Center</span></span>
<span data-ttu-id="160b3-155">응용 프로그램에서 만든 응용 프로그램을 허용해야 Microsoft Defender 보안 센터.</span><span class="sxs-lookup"><span data-stu-id="160b3-155">You'll need to allow the application you created in Microsoft Defender Security Center.</span></span>
 
<span data-ttu-id="160b3-156">응용 프로그램을 **허용하려면** 포털 시스템 설정 관리 권한이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="160b3-156">You'll need to have **Manage portal system settings** permission to allow the application.</span></span> <span data-ttu-id="160b3-157">그렇지 않으면 고객에게 응용 프로그램을 허용하도록 요청해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="160b3-157">Otherwise, you'll need to request your customer to allow the application for you.</span></span>

1. <span data-ttu-id="160b3-158">로 `https://securitycenter.windows.com?tid=<customer_tenant_id>` 이동(고객의 테넌트 \<customer_tenant_id\> ID로 대체).</span><span class="sxs-lookup"><span data-stu-id="160b3-158">Go to `https://securitycenter.windows.com?tid=<customer_tenant_id>` (replace \<customer_tenant_id\> with the customer's tenant ID.</span></span>

2. <span data-ttu-id="160b3-159">SIEM **설정**  >  **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="160b3-159">Click **Settings** > **SIEM**.</span></span> 

3. <span data-ttu-id="160b3-160">**MSSP 탭을** 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="160b3-160">Select the **MSSP** tab.</span></span>

4. <span data-ttu-id="160b3-161">첫 번째 단계에서 응용 프로그램 **ID와** 테넌트 **ID 를 입력합니다.**</span><span class="sxs-lookup"><span data-stu-id="160b3-161">Enter the **Application ID** from the first step and your **Tenant ID**.</span></span>

5. <span data-ttu-id="160b3-162">응용 **프로그램 승인을 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="160b3-162">Click **Authorize application**.</span></span> 

 
<span data-ttu-id="160b3-163">이제 SIEM에 대한 관련 구성 파일을 다운로드하고 Endpoint API용 Defender에 연결할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="160b3-163">You can now download the relevant configuration file for your SIEM and connect to the Defender for Endpoint API.</span></span> <span data-ttu-id="160b3-164">자세한 내용은 SIEM 도구로 [경고 끌어오기를 참조하세요.](configure-siem.md)</span><span class="sxs-lookup"><span data-stu-id="160b3-164">For more information, see, [Pull alerts to your SIEM tools](configure-siem.md).</span></span>
 

- <span data-ttu-id="160b3-165">ArcSight 구성 파일/ Splunk 인증 속성 파일에서 비밀 값을 설정하여 응용 프로그램 키를 수동으로 작성합니다.</span><span class="sxs-lookup"><span data-stu-id="160b3-165">In the ArcSight configuration file / Splunk Authentication Properties file, write your application key manually by setting the secret value.</span></span>
- <span data-ttu-id="160b3-166">포털에서 새로 고침 토큰을 획득하는 대신 이전 단계의 스크립트를 사용하여 새로 고침 토큰을 획득하거나 다른 방법을 통해 새로 고침 토큰을 획득합니다.</span><span class="sxs-lookup"><span data-stu-id="160b3-166">Instead of acquiring a refresh token in the portal, use the script from the previous step to acquire a refresh token (or acquire it by other means).</span></span>

## <a name="fetch-alerts-from-mssp-customers-tenant-using-apis"></a><span data-ttu-id="160b3-167">API를 사용하여 MSSP 고객의 테넌트에서 경고 페치</span><span class="sxs-lookup"><span data-stu-id="160b3-167">Fetch alerts from MSSP customer's tenant using APIs</span></span>
 
<span data-ttu-id="160b3-168">REST API를 사용하여 경고를 끌어오는 방법에 대한 자세한 내용은 REST API를 사용하여 [경고 끌어오기 를 참조하세요.](pull-alerts-using-rest-api.md)</span><span class="sxs-lookup"><span data-stu-id="160b3-168">For information on how to fetch alerts using REST API, see [Pull alerts using REST API](pull-alerts-using-rest-api.md).</span></span>


## <a name="see-also"></a><span data-ttu-id="160b3-169">참고 항목</span><span class="sxs-lookup"><span data-stu-id="160b3-169">See also</span></span>
- [<span data-ttu-id="160b3-170">MSSP 액세스를 포털에 부여</span><span class="sxs-lookup"><span data-stu-id="160b3-170">Grant MSSP access to the portal</span></span>](grant-mssp-access.md)
- [<span data-ttu-id="160b3-171">MSSP 고객 포털에 액세스</span><span class="sxs-lookup"><span data-stu-id="160b3-171">Access the MSSP customer portal</span></span>](access-mssp-portal.md)
- [<span data-ttu-id="160b3-172">경고 알림 구성</span><span class="sxs-lookup"><span data-stu-id="160b3-172">Configure alert notifications</span></span>](configure-mssp-notifications.md)
