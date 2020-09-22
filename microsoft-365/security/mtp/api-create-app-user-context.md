---
title: 사용자 대신 사용 하 여 Microsoft Threat Protection Api에 액세스
description: 사용자 대신 사용 하 여 Microsoft Threat Protection Api에 액세스 하는 방법 알아보기
keywords: 사용자, api, 응용 프로그램, 사용자, 액세스 토큰, 토큰을 대신 하 여 액세스
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
ms.openlocfilehash: a62d90004d00e8c553f1b011e77b871df7cd94f4
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/22/2020
ms.locfileid: "48197800"
---
# <a name="access-microsoft-threat-protection-apis-on-behalf-of-user"></a>사용자 대신 Microsoft 위협 보호 Api에 액세스

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**적용 대상:**
- Microsoft 위협 방지

>[!IMPORTANT] 
>일부 정보는 상업적으로 출시 되기 전에 크게 수정 될 수 있는 prereleased 제품과 관련 되어 있습니다. Microsoft makes no warranties, express or implied, with respect to the information provided here.


이 페이지에서는 사용자를 대신 하 여 Microsoft Threat Protection에 프로그래밍 방식으로 액세스할 수 있도록 응용 프로그램을 만드는 방법에 대해 설명 합니다.

사용자 없이 프로그래밍 방식으로 Microsoft Threat Protection에 액세스 해야 하는 경우에는 [사용자 없이 Microsoft Threat protection에 액세스 하는 앱 만들기](api-create-app-web.md)를 참조 하세요.

필요한 액세스를 모르는 경우에는 [Microsoft Threat Protection Api 액세스](api-access.md)를 참조 하세요.

Microsoft Threat Protection은 대부분의 데이터와 작업을 다양 한 Api 집합을 통해 제공 합니다. 이러한 Api를 사용 하면 Microsoft 위협 방지 기능을 기반으로 하 여 작업 흐름과 로깅을 자동화할 수 있습니다. API 액세스를 사용 하려면 OAuth 2.0 인증이 필요 합니다. 자세한 내용은 [OAuth 2.0 인증 코드 흐름](https://docs.microsoft.com/azure/active-directory/develop/active-directory-v2-protocols-oauth-code)을 참조 하십시오.

일반적으로 Api를 사용 하려면 다음 단계를 수행 해야 합니다.
- AAD 응용 프로그램 만들기
- 이 응용 프로그램을 사용 하 여 액세스 토큰 가져오기
- 토큰을 사용 하 여 Microsoft Threat Protection API 액세스

이 페이지에서는 AAD 응용 프로그램을 만들고, Microsoft Threat Protection에 대 한 액세스 토큰을 가져오고, 토큰의 유효성을 검사 하는 방법에 대해 설명 합니다.

>[!NOTE]
> 사용자를 대신 하 여 Microsoft Threat Protection API에 액세스 하는 경우 올바른 응용 프로그램 권한 및 사용자 권한이 있어야 합니다.


>[!TIP]
> 포털에서 작업을 수행할 수 있는 권한이 있는 경우 API에서 해당 작업을 수행할 수 있는 권한이 있습니다.

## <a name="create-an-app"></a>앱 만들기

1. **전역 관리자** 역할이 있는 사용자를 사용 하 여 [Azure](https://portal.azure.com) 에 로그온 합니다.

2. **Azure Active Directory**  >  **앱 등록**  >  **새 등록**으로 이동 합니다. 

   ![Microsoft Azure 이미지 및 응용 프로그램 등록에 대 한 탐색](../../media/atp-azure-new-app2.png)

3. 등록에서 다음 정보를 입력 하 고 **등록**을 클릭 합니다.

   ![응용 프로그램 만들기 창의 이미지](../../media/nativeapp-create2.PNG)

   - **이름:** 응용 프로그램 이름
   - **응용 프로그램 유형:** 공용 클라이언트
   - **리디렉션 URI:**https://portal.azure.com

4. 앱이 Microsoft threat protection에 액세스 하 고 사용 권한을 할당할 수 있도록 하려면 응용 프로그램 페이지에서 **api 사용**권한 api를 선택  >  **Add permission**  >  합니다.**내 조직에서 사용 하는** >에는 **microsoft threat protection**을 입력 한 다음 **microsoft**threat protection을 선택 합니다.

    >[!NOTE]
    > Microsoft Threat Protection이 원래 목록에 표시 되지 않습니다. 텍스트 상자에 이름을 입력 하 여 표시 되는지 확인 해야 합니다.

      ![API 액세스 및 API 선택 이미지](../../media/apis-in-my-org-tab.PNG)

    - **위임 된 사용 권한을** 선택 하 > 시나리오에 대 한 관련 사용 권한 (예: **읽음**)을 선택 하 고 **사용 권한 추가**를 선택 합니다.

      ![API 액세스 및 API 선택 이미지](../../media/request-api-permissions-delegated.PNG)

     >[!IMPORTANT]
     >관련 사용 권한을 선택 해야 합니다. 

    -  필요한 사용 권한을 확인 하려면 통화할 API에서 **사용 권한** 섹션을 확인 하세요.

    - **동의 허용** 을 클릭 합니다.

      >[!NOTE]
      >사용 권한을 추가할 때마다 새 사용 권한에 대 한 **동의 부여** 를 클릭 하 여 적용 해야 합니다.

      ![권한 부여 이미지](../../media/grant-consent-delegated.PNG)

6. 응용 프로그램 ID 및 테 넌 트 ID를 적어 둡니다.

   - 응용 프로그램 페이지에서 **개요** 로 이동 하 여 다음을 복사 합니다.

   ![만든 앱 id의 이미지](../../media/app-and-tenant-ids.png)


## <a name="get-an-access-token-using-powershell"></a>PowerShell을 사용 하 여 액세스 토큰 가져오기

```
#Install the ADAL.PS package if it's not installed.
if(!(Get-Package adal.ps)) { Install-Package -Name adal.ps }

$authority = "https://login.windows.net/{tenant-id}" # replace {tenant-id} with your tenant ID.

$clientId = "{application-id}" #replace {application-id} with your application ID.

$redirectUri = "{redirect-uri}" # replace {redirect-uri} with your application redirect URI.

$resourceUrl = "https://api.security.microsoft.com"

$response = Get-ADALToken -Resource $resourceUrl -ClientId $clientId -RedirectUri $redirectUri -Authority $authority -PromptBehavior:Always
$response.AccessToken | clip
$response.AccessToken
```

## <a name="related-topics"></a>관련 항목
- [Microsoft Threat Protection Api 액세스](api-access.md)
- [응용 프로그램 컨텍스트를 사용 하 여 Microsoft 위협 방지 액세스](api-create-app-web.md)
