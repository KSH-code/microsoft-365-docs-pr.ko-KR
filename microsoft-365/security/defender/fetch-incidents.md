---
title: 인시던트 Microsoft 365 Defender 페치
description: 고객 테넌트에서 인시던트 Microsoft 365 Defender 페치하는 방법 학습
keywords: 관리되는 보안 서비스 공급자, mssp, 구성, 통합
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: m365d
ms.custom: api
ms.openlocfilehash: 1ea39bfce5303360165a56d6361908d1014d370f
ms.sourcegitcommit: e110f00dc6949a7a1345187375547beeb64225b2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/06/2021
ms.locfileid: "60805030"
---
# <a name="fetch-microsoft-365-defender-incidents"></a>인시던트 Microsoft 365 Defender 페치 

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**적용 대상:**
- [엔드포인트용 Microsoft Defender](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)


> [!NOTE]
> 이 작업은 MSSP에서 수행됩니다.

경고를 내보는 방법에는 다음 두 가지가 있습니다.

- SIEM 메서드 사용
- API 사용

## <a name="fetch-incidents-into-your-siem"></a>SIEM에 인시던트 페치

인시던트가 SIEM 시스템으로 페치하려면 다음 단계를 수행해야 합니다.

- 1단계: 타사 응용 프로그램 만들기
- 2단계: 고객의 테넌트에서 토큰 액세스 및 새로 고침
- 3단계: 응용 프로그램에서 응용 프로그램 허용 Microsoft 365 Defender

### <a name="step-1-create-an-application-in-azure-active-directory-azure-ad"></a>1단계: Azure AD(Azure Active Directory 응용 프로그램 만들기)

응용 프로그램을 만들고 고객의 다른 테넌트에서 알림을 보내기 위한 권한을 Microsoft 365 Defender 합니다.

1. Azure AD [포털에 로그인합니다.](https://aad.portal.azure.com/)

2. 앱 **Azure Active Directory** \> **등록을 선택합니다.**

3. 새 **등록 을 클릭합니다.**

4. 다음 값을 지정합니다.

    - 이름: \<Tenant_name\> SIEM MSSP 커넥터(테넌트 Tenant_name 이름으로 바꾸기)

    - 지원되는 계정 유형: 이 조직 디렉터리의 계정만
    - 리디렉션 URI: 웹을 선택하고 입력(<domain_name> `https://<domain_name>/SiemMsspConnector` 이름으로 바꾸기)

5. 등록을 **클릭합니다.** 응용 프로그램이 소유한 응용 프로그램 목록에 표시됩니다.

6. 응용 프로그램을 선택한 다음 개요 를 **클릭합니다.**

7. 응용 프로그램(클라이언트) **ID 필드의** 값을 안전한 장소로 복사하려면 다음 단계에서 이 값이 필요합니다.

8. 새 **& 패널에서** 인증서 인증서를 선택합니다.

9. 새 **클라이언트 비밀 을 클릭합니다.**

    - 설명: 키에 대한 설명을 입력합니다.
    - 만료: **1년 후 선택**

10. **추가를** 클릭하고 클라이언트 비밀 값을 안전한 장소에 복사합니다. 이 값은 다음 단계에서 필요합니다.

### <a name="step-2-get-access-and-refresh-tokens-from-your-customers-tenant"></a>2단계: 고객의 테넌트에서 토큰 액세스 및 새로 고침

이 섹션에서는 PowerShell 스크립트를 사용하여 고객의 테넌트에서 토큰을 다운로드하는 방법을 안내합니다. 이 스크립트는 이전 단계의 응용 프로그램을 사용하여 OAuth 권한 부여 코드 응용 프로그램을 사용하여 액세스 및 새로 고침 토큰을 Flow.

자격 증명을 제공한 후 응용 프로그램이 고객의 테넌트에 프로비전되는 데 필요한 동의를 응용 프로그램에 부여해야 합니다.

1. 새 폴더를 만들고 이름을 로 `MsspTokensAcquisition` 지정합니다. .

2. [LoginBrowser.psm1](https://github.com/shawntabrizi/Microsoft-Authentication-with-PowerShell-and-MSAL/blob/master/Authorization%20Code%20Grant%20Flow/LoginBrowser.psm1) 모듈을 다운로드하여 폴더에 `MsspTokensAcquisition` 저장합니다.

    > [!NOTE]
    > 줄 30에서 을 로 `authorzationUrl` 바 `authorizationUrl` 대체합니다.

3. 다음 콘텐츠가 있는 파일을 만들고 폴더의 이름으로 `MsspTokensAcquisition.ps1` 저장합니다.

    ```powershell
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

    Write-Host " ----------------------------------- TOKEN ---------------------------------- "
    Write-Host $token

    Write-Host " ----------------------------------- REFRESH TOKEN ---------------------------------- "
    Write-Host $refreshToken
    ```
4. 폴더에서 상승된 PowerShell 명령 프롬프트를 열 `MsspTokensAcquisition` 수 있습니다.

5. 다음 명령을 실행합니다. `Set-ExecutionPolicy -ExecutionPolicy Bypass`

6. 다음 명령을 입력합니다. `.\MsspTokensAcquisition.ps1 -clientId <client_id> -secret <app_key> -tenantId <customer_tenant_id>`

    - 이전 단계에서 얻게 된 응용 \<client_id\> 프로그램(클라이언트) **ID로** 바)
    - 이전 \<app_key\> 단계에서 만든 **클라이언트** 비밀로 바 대체합니다.
    - 고객의 \<customer_tenant_id\> 테넌트 **ID로 대체합니다.**

7. 자격 증명 및 동의를 제공해야 합니다. 페이지 리디렉션을 무시합니다.

8. PowerShell 창에서 액세스 토큰과 새로 고침 토큰을 받게 됩니다. 새로 고침 토큰을 저장하여 SIEM 커넥터를 구성합니다.

### <a name="step-3-allow-your-application-on-microsoft-365-defender"></a>3단계: 응용 프로그램에서 응용 프로그램 Microsoft 365 Defender

응용 프로그램에서 만든 응용 프로그램을 허용해야 Microsoft 365 Defender.

응용 프로그램을 **허용하려면** 포털 시스템 설정 관리 권한이 필요합니다. 그렇지 않으면 고객에게 응용 프로그램을 허용하도록 요청해야 합니다.

1. 로 `https://security.microsoft.com?tid=<customer_tenant_id>` 이동(고객의 테넌트 \<customer_tenant_id\> ID로 대체).

2. 끝점 **설정** \>  \>  \> **SIEM을 클릭합니다.**

3. **MSSP 탭을** 선택합니다.

4. 첫 번째 단계에서 응용 프로그램 **ID와** 테넌트 **ID 를 입력합니다.**

5. 응용 **프로그램 승인을 클릭합니다.**

이제 SIEM에 대한 관련 구성 파일을 다운로드하고 해당 API에 Microsoft 365 Defender 있습니다. 자세한 내용은 SIEM 도구로 [경고 끌어오기를 참조하세요.](../defender-endpoint/configure-siem.md)

- ArcSight 구성 파일/ Splunk 인증 속성 파일에서 비밀 값을 설정하여 응용 프로그램 키를 수동으로 작성합니다.
- 포털에서 새로 고침 토큰을 획득하는 대신 이전 단계의 스크립트를 사용하여 새로 고침 토큰을 획득하거나 다른 방법을 통해 새로 고침 토큰을 획득합니다.

## <a name="fetch-alerts-from-mssp-customers-tenant-using-apis"></a>API를 사용하여 MSSP 고객의 테넌트에서 경고 페치

REST API를 사용하여 경고를 끌어오는 방법에 대한 자세한 내용은 REST API를 사용하여 [경고 끌어오기 를 참조하세요.](../defender-endpoint/pull-alerts-using-rest-api.md)
