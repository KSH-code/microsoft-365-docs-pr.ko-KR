---
title: REST API를 사용하여 끝점 검색을 위한 Microsoft Defender 끌어오기
description: SIEM REST API를 사용하여 Microsoft Defender for Endpoint API 끝점을 호출하여 JSON 형식으로 검색을 끌어오는 방법을 학습합니다.
keywords: 검색, 검색 끌어오기, rest api, 요청, 응답
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
ms.openlocfilehash: c8baf74d5f838c583b98fddd7d7d706c6e116a40
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51071911"
---
# <a name="pull-microsoft-defender-for-endpoint-detections-using-siem-rest-api"></a><span data-ttu-id="a6106-104">SIEM REST API를 사용하여 끝점 검색을 위한 Microsoft Defender 끌어오기</span><span class="sxs-lookup"><span data-stu-id="a6106-104">Pull Microsoft Defender for Endpoint detections using SIEM REST API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="a6106-105">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="a6106-105">**Applies to:**</span></span>
- [<span data-ttu-id="a6106-106">엔드포인트용 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="a6106-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2146631)
- [<span data-ttu-id="a6106-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="a6106-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="a6106-108">Endpoint용 Defender를 경험하고 싶나요?</span><span class="sxs-lookup"><span data-stu-id="a6106-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="a6106-109">무료 평가판에 등록합니다.</span><span class="sxs-lookup"><span data-stu-id="a6106-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-pullalerts-abovefoldlink) 


[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

>[!Note]
>- <span data-ttu-id="a6106-110">[끝점용 Microsoft Defender 경고는](alerts.md) 하나 이상의 검색으로 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="a6106-110">[Microsoft Defender for Endpoint Alert](alerts.md) is composed from one or more detections.</span></span>
>- <span data-ttu-id="a6106-111">[끝점 검색을 위한 Microsoft Defender는](api-portal-mapping.md) 장치 및 관련 경고 세부 정보에서 발생한 의심스러운 이벤트로 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="a6106-111">[Microsoft Defender for Endpoint Detection](api-portal-mapping.md) is composed from the suspicious event occurred on the Device and its related Alert details.</span></span>
><span data-ttu-id="a6106-112">-The Microsoft Defender for Endpoint Alert API는 경고 소비를 위한 최신 API로, 각 경고에 대한 자세한 관련 증거 목록을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="a6106-112">-The Microsoft Defender for Endpoint Alert API is the latest API for alert consumption and contain a detailed list of related evidence for each alert.</span></span> <span data-ttu-id="a6106-113">자세한 내용은 [Alert 메서드](alerts.md) 및 속성 및 목록 [경고를 참조하세요.](get-alerts.md)</span><span class="sxs-lookup"><span data-stu-id="a6106-113">For more information, see [Alert methods and properties](alerts.md) and [List alerts](get-alerts.md).</span></span>

<span data-ttu-id="a6106-114">끝점용 Microsoft Defender는 API에서 검색을 끌어오는 OAuth 2.0 프로토콜을 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="a6106-114">Microsoft Defender for Endpoint supports the OAuth 2.0 protocol to pull detections from the API.</span></span>

<span data-ttu-id="a6106-115">일반적으로 OAuth 2.0 프로토콜은 다음 네 가지 유형의 흐름을 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="a6106-115">In general, the OAuth 2.0 protocol supports four types of flows:</span></span>
- <span data-ttu-id="a6106-116">권한 부여 흐름</span><span class="sxs-lookup"><span data-stu-id="a6106-116">Authorization grant flow</span></span>
- <span data-ttu-id="a6106-117">암시적 흐름</span><span class="sxs-lookup"><span data-stu-id="a6106-117">Implicit flow</span></span>
- <span data-ttu-id="a6106-118">클라이언트 자격 증명 흐름</span><span class="sxs-lookup"><span data-stu-id="a6106-118">Client credentials flow</span></span>
- <span data-ttu-id="a6106-119">자원 소유자 흐름</span><span class="sxs-lookup"><span data-stu-id="a6106-119">Resource owner flow</span></span>

<span data-ttu-id="a6106-120">OAuth 사양에 대한 자세한 내용은 [OAuth](http://www.oauth.net)웹 사이트를 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="a6106-120">For more information about the OAuth specifications, see the [OAuth Website](http://www.oauth.net).</span></span>

<span data-ttu-id="a6106-121">끝점용 Microsoft Defender는  권한 부여  흐름 및 클라이언트 자격 증명 흐름을 지원하여 AAD(Azure Active Directory)를 권한 부여 서버로 사용하여 검색을 끌어오기 위한 액세스 권한을 얻습니다.</span><span class="sxs-lookup"><span data-stu-id="a6106-121">Microsoft Defender for Endpoint supports the _Authorization grant flow_ and _Client credential flow_ to obtain access to pull detections, with Azure Active Directory (AAD) as the authorization server.</span></span>

<span data-ttu-id="a6106-122">권한 _부여 흐름은_ 사용자 자격 증명을 사용하여 권한 부여 코드를 얻은 다음 액세스 토큰을 얻는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="a6106-122">The _Authorization grant flow_ uses user credentials to get an authorization code, which is then used to obtain an access token.</span></span>

<span data-ttu-id="a6106-123">클라이언트 _자격 증명 흐름은_ 클라이언트 자격 증명을 사용하여 끝점용 Microsoft Defender 끝점 URL에 대해 인증합니다.</span><span class="sxs-lookup"><span data-stu-id="a6106-123">The _Client credential flow_ uses client credentials to authenticate against the Microsoft Defender for Endpoint endpoint URL.</span></span> <span data-ttu-id="a6106-124">이 흐름은 OAuth 클라이언트가 사용자 자격 증명이 필요하지 않은 API에 대한 요청을 만드는 시나리오에 적합합니다.</span><span class="sxs-lookup"><span data-stu-id="a6106-124">This flow is suitable for scenarios when an OAuth client creates requests to an API that doesn't require user credentials.</span></span>

<span data-ttu-id="a6106-125">Microsoft Defender for Endpoint API에서 다음 메서드를 사용하여 JSON 형식으로 검색을 끌어오는 방법을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="a6106-125">Use the following method in the Microsoft Defender for Endpoint API to pull detections in JSON format.</span></span>

>[!NOTE]
><span data-ttu-id="a6106-126">Microsoft Defender 보안 센터는 유사한 경고 검색을 단일 경고에 병합합니다.</span><span class="sxs-lookup"><span data-stu-id="a6106-126">Microsoft Defender Security Center merges similar alert detections into a single alert.</span></span> <span data-ttu-id="a6106-127">이 API는 설정한 쿼리 매개 변수에 따라 원시 양식의 경고 검색을 끌어와서 자체 그룹화 및 필터링을 적용할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="a6106-127">This API pulls alert detections in its raw form based on the query parameters you set, enabling you to apply your own grouping and filtering.</span></span> 

## <a name="before-you-begin"></a><span data-ttu-id="a6106-128">시작하기 전에</span><span class="sxs-lookup"><span data-stu-id="a6106-128">Before you begin</span></span>
- <span data-ttu-id="a6106-129">검색을 끌어오기 위해 끝점용 Microsoft Defender 끝점을 호출하기 전에 AAD(Azure Active Directory)에서 SIEM 통합 응용 프로그램을 사용하도록 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a6106-129">Before calling the Microsoft Defender for Endpoint endpoint to pull detections, you'll need to enable the SIEM integration application in Azure Active Directory (AAD).</span></span> <span data-ttu-id="a6106-130">자세한 내용은 [Enable SIEM integration in Microsoft Defender for Endpoint을 참조하세요.](enable-siem-integration.md)</span><span class="sxs-lookup"><span data-stu-id="a6106-130">For more information, see [Enable SIEM integration in Microsoft Defender for Endpoint](enable-siem-integration.md).</span></span>

- <span data-ttu-id="a6106-131">Azure 응용 프로그램 등록에서 다음 값을 참고하십시오.</span><span class="sxs-lookup"><span data-stu-id="a6106-131">Take note of the following values in your Azure application registration.</span></span> <span data-ttu-id="a6106-132">서비스 또는 데몬 앱에서 OAuth 흐름을 구성하려면 다음 값이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="a6106-132">You need these values to configure the OAuth flow in your service or daemon app:</span></span>
  - <span data-ttu-id="a6106-133">응용 프로그램 ID(응용 프로그램에 고유)</span><span class="sxs-lookup"><span data-stu-id="a6106-133">Application ID (unique to your application)</span></span>
  - <span data-ttu-id="a6106-134">앱 키 또는 비밀(응용 프로그램에 고유한)</span><span class="sxs-lookup"><span data-stu-id="a6106-134">App key, or secret (unique to your application)</span></span>
  - <span data-ttu-id="a6106-135">앱의 OAuth 2.0 토큰 끝점</span><span class="sxs-lookup"><span data-stu-id="a6106-135">Your app's OAuth 2.0 token endpoint</span></span>
    - <span data-ttu-id="a6106-136">앱 페이지의 Azure  관리 포털 아래쪽에서 끝점 보기를 클릭하여 이 값을 찾으십시오.</span><span class="sxs-lookup"><span data-stu-id="a6106-136">Find this value by clicking **View Endpoints** at the bottom of the Azure Management Portal in your app's page.</span></span> <span data-ttu-id="a6106-137">끝점은 처럼 보이게 `https://login.microsoftonline.com/{tenantId}/oauth2/token` 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a6106-137">The endpoint will look like `https://login.microsoftonline.com/{tenantId}/oauth2/token`.</span></span>

## <a name="get-an-access-token"></a><span data-ttu-id="a6106-138">액세스 토큰을 얻게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a6106-138">Get an access token</span></span>
<span data-ttu-id="a6106-139">끝점에 대한 호출을 만들기 전에 액세스 토큰을 만들어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a6106-139">Before creating calls to the endpoint, you'll need to get an access token.</span></span>

<span data-ttu-id="a6106-140">액세스 토큰을 사용하여 보호된 리소스(끝점용 Microsoft Defender의 검색)에 액세스합니다.</span><span class="sxs-lookup"><span data-stu-id="a6106-140">You'll use the access token to access the protected resource, which is detections in Microsoft Defender for Endpoint.</span></span>

<span data-ttu-id="a6106-141">액세스 토큰을 얻기 위해 토큰을 발행하는 끝점에 대한 POST 요청을 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a6106-141">To get an access token, you'll need to do a POST request to the token issuing endpoint.</span></span> <span data-ttu-id="a6106-142">샘플 요청은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="a6106-142">Here is a sample request:</span></span>

```http

POST /72f988bf-86f1-41af-91ab-2d7cd011db47/oauth2/token HTTP/1.1
Host: login.microsoftonline.com
Content-Type: application/x-www-form-urlencoded

resource=https%3A%2F%2Fgraph.windows.net&client_id=35e0f735-5fe4-4693-9e68-3de80f1d3745&client_secret=IKXc6PxB2eoFNJ%2FIT%2Bl2JZZD9d9032VXz6Ul3D2WyUQ%3D&grant_type=client_credentials
```
<span data-ttu-id="a6106-143">응답에는 액세스 토큰 및 만료 정보가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="a6106-143">The response will include an access token and expiry information.</span></span>

```json
{
  "token_type": "Bearer",
  "expires_in": 3599,
  "ext_expires_in": 0,
  "expires_on": 1488720683,
  "not_before": 1488720683,
  "resource": "https://graph.windows.net",
  "access_token":"eyJ0eXaioJJOIneiowiouqSuzNiZ345FYOVkaJL0625TueyaJasjhIjEnbMlWqP..."
}
```
<span data-ttu-id="a6106-144">이제 끝점 API에  대한 요청에서 access_token 필드의 값을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a6106-144">You can now use the value in the *access_token* field in a request to the Defender for Endpoint API.</span></span>

## <a name="request"></a><span data-ttu-id="a6106-145">요청</span><span class="sxs-lookup"><span data-stu-id="a6106-145">Request</span></span>
<span data-ttu-id="a6106-146">액세스 토큰을 사용하여 앱은 끝점 API용 Microsoft Defender에 인증된 요청을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a6106-146">With an access token, your app can make authenticated requests to the Microsoft Defender for Endpoint API.</span></span> <span data-ttu-id="a6106-147">앱은 각 요청의 Authorization 헤더에 액세스 토큰을 추가해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a6106-147">Your app must append the access token to the Authorization header of each request.</span></span>

### <a name="request-syntax"></a><span data-ttu-id="a6106-148">요청 구문</span><span class="sxs-lookup"><span data-stu-id="a6106-148">Request syntax</span></span>
<span data-ttu-id="a6106-149">메서드</span><span class="sxs-lookup"><span data-stu-id="a6106-149">Method</span></span> | <span data-ttu-id="a6106-150">요청 URI</span><span class="sxs-lookup"><span data-stu-id="a6106-150">Request URI</span></span>
:---|:---|
<span data-ttu-id="a6106-151">GET</span><span class="sxs-lookup"><span data-stu-id="a6106-151">GET</span></span>| <span data-ttu-id="a6106-152">해당 지역에 적용할 수 있는 URI를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="a6106-152">Use the URI applicable for your region.</span></span> <br><br> <span data-ttu-id="a6106-153">**EU의 경우**: `https://wdatp-alertexporter-eu.windows.com/api/alerts`</span><span class="sxs-lookup"><span data-stu-id="a6106-153">**For EU**: `https://wdatp-alertexporter-eu.windows.com/api/alerts`</span></span> </br> <span data-ttu-id="a6106-154">**미국의 경우**: `https://wdatp-alertexporter-us.windows.com/api/alerts`</span><span class="sxs-lookup"><span data-stu-id="a6106-154">**For US**: `https://wdatp-alertexporter-us.windows.com/api/alerts`</span></span> <br> <span data-ttu-id="a6106-155">**영국의** 경우 : `https://wdatp-alertexporter-uk.windows.com/api/alerts`</span><span class="sxs-lookup"><span data-stu-id="a6106-155">**For UK**: `https://wdatp-alertexporter-uk.windows.com/api/alerts`</span></span> 

### <a name="request-header"></a><span data-ttu-id="a6106-156">요청 헤더</span><span class="sxs-lookup"><span data-stu-id="a6106-156">Request header</span></span>
<span data-ttu-id="a6106-157">머리글</span><span class="sxs-lookup"><span data-stu-id="a6106-157">Header</span></span> | <span data-ttu-id="a6106-158">유형</span><span class="sxs-lookup"><span data-stu-id="a6106-158">Type</span></span> | <span data-ttu-id="a6106-159">설명</span><span class="sxs-lookup"><span data-stu-id="a6106-159">Description</span></span>|
:--|:--|:--
<span data-ttu-id="a6106-160">권한 부여</span><span class="sxs-lookup"><span data-stu-id="a6106-160">Authorization</span></span> | <span data-ttu-id="a6106-161">문자열</span><span class="sxs-lookup"><span data-stu-id="a6106-161">string</span></span> | <span data-ttu-id="a6106-162">필수 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="a6106-162">Required.</span></span> <span data-ttu-id="a6106-163">**Bearer** 토큰 형식의 Azure AD 액세스 &lt; *토큰입니다.* &gt;</span><span class="sxs-lookup"><span data-stu-id="a6106-163">The Azure AD access token in the form **Bearer** &lt;*token*&gt;.</span></span> |

### <a name="request-parameters"></a><span data-ttu-id="a6106-164">요청 매개 변수</span><span class="sxs-lookup"><span data-stu-id="a6106-164">Request parameters</span></span>

<span data-ttu-id="a6106-165">선택적 쿼리 매개 변수를 사용하여 응답에 반환되는 데이터의 양을 지정하고 제어합니다.</span><span class="sxs-lookup"><span data-stu-id="a6106-165">Use optional query parameters to specify and control the amount of data returned in a response.</span></span> <span data-ttu-id="a6106-166">매개 변수 없이 이 메서드를 호출하면 응답에는 지난 2시간 동안 조직의 모든 경고가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="a6106-166">If you call this method without parameters, the response contains all the alerts in your organization in the last 2 hours.</span></span>

<span data-ttu-id="a6106-167">이름</span><span class="sxs-lookup"><span data-stu-id="a6106-167">Name</span></span> | <span data-ttu-id="a6106-168">값</span><span class="sxs-lookup"><span data-stu-id="a6106-168">Value</span></span>| <span data-ttu-id="a6106-169">설명</span><span class="sxs-lookup"><span data-stu-id="a6106-169">Description</span></span>
:---|:---|:---
<span data-ttu-id="a6106-170">sinceTimeUtc</span><span class="sxs-lookup"><span data-stu-id="a6106-170">sinceTimeUtc</span></span> | <span data-ttu-id="a6106-171">DateTime</span><span class="sxs-lookup"><span data-stu-id="a6106-171">DateTime</span></span> | <span data-ttu-id="a6106-172">필드에 따라 바운드 경고가 검색된 하위 시간을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="a6106-172">Defines the lower time bound alerts are retrieved from, based on field:</span></span> <br> `LastProcessedTimeUtc` <br> <span data-ttu-id="a6106-173">시간 범위는 sinceTimeUtc 시간에서 현재 시간까지입니다.</span><span class="sxs-lookup"><span data-stu-id="a6106-173">The time range will be: from sinceTimeUtc time to current time.</span></span> <br><br> <span data-ttu-id="a6106-174">**참고:** 지정하지 않으면 지난 2시간 동안 생성된 모든 경고가 검색됩니다.</span><span class="sxs-lookup"><span data-stu-id="a6106-174">**NOTE**: When not specified, all alerts generated in the last two hours are retrieved.</span></span>
<span data-ttu-id="a6106-175">untilTimeUtc</span><span class="sxs-lookup"><span data-stu-id="a6106-175">untilTimeUtc</span></span> | <span data-ttu-id="a6106-176">DateTime</span><span class="sxs-lookup"><span data-stu-id="a6106-176">DateTime</span></span> | <span data-ttu-id="a6106-177">바운드 경고가 검색된 상위 시간을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="a6106-177">Defines the upper time bound alerts are retrieved.</span></span> <br> <span data-ttu-id="a6106-178">시간 범위는 `sinceTimeUtc` 다음을 수시로 `untilTimeUtc` 합니다.</span><span class="sxs-lookup"><span data-stu-id="a6106-178">The time range will be: from `sinceTimeUtc` time to `untilTimeUtc` time.</span></span> <br><br> <span data-ttu-id="a6106-179">**참고:** 지정하지 않으면 기본값은 현재 시간입니다.</span><span class="sxs-lookup"><span data-stu-id="a6106-179">**NOTE**: When not specified, the default value will be the current time.</span></span>
<span data-ttu-id="a6106-180">ago</span><span class="sxs-lookup"><span data-stu-id="a6106-180">ago</span></span> | <span data-ttu-id="a6106-181">문자열</span><span class="sxs-lookup"><span data-stu-id="a6106-181">string</span></span> | <span data-ttu-id="a6106-182">경고를 끌어오는 시간 범위는 다음과 `(current_time - ago)` `current_time` 같습니다.</span><span class="sxs-lookup"><span data-stu-id="a6106-182">Pulls alerts in the following time range: from `(current_time - ago)` time to `current_time` time.</span></span> <br><br> <span data-ttu-id="a6106-183">값은 **ISO 8601** 기간 형식에 따라 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a6106-183">Value should be set according to **ISO 8601** duration format</span></span> <br> <span data-ttu-id="a6106-184">예: 지난 10분 동안 수신된 경고를 `ago=PT10M` 끌어오는 예제입니다.</span><span class="sxs-lookup"><span data-stu-id="a6106-184">Example: `ago=PT10M` will pull alerts received in the last 10 minutes.</span></span>
<span data-ttu-id="a6106-185">limit</span><span class="sxs-lookup"><span data-stu-id="a6106-185">limit</span></span> | <span data-ttu-id="a6106-186">int</span><span class="sxs-lookup"><span data-stu-id="a6106-186">int</span></span> | <span data-ttu-id="a6106-187">검색할 알림 수를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="a6106-187">Defines the number of alerts to be retrieved.</span></span> <span data-ttu-id="a6106-188">가장 최근 알림은 정의된 수에 따라 검색됩니다.</span><span class="sxs-lookup"><span data-stu-id="a6106-188">Most recent alerts will be retrieved based on the number defined.</span></span><br><br> <span data-ttu-id="a6106-189">**참고:** 지정하지 않으면 시간 범위에서 사용할 수 있는 모든 경고가 검색됩니다.</span><span class="sxs-lookup"><span data-stu-id="a6106-189">**NOTE**: When not specified, all alerts available in the time range will be retrieved.</span></span>
<span data-ttu-id="a6106-190">machinegroups</span><span class="sxs-lookup"><span data-stu-id="a6106-190">machinegroups</span></span> | <span data-ttu-id="a6106-191">문자열</span><span class="sxs-lookup"><span data-stu-id="a6106-191">string</span></span> | <span data-ttu-id="a6106-192">경고를 끌어오기 위해 장치 그룹을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="a6106-192">Specifies device groups to pull alerts from.</span></span> <br><br> <span data-ttu-id="a6106-193">**참고:** 지정하지 않으면 모든 장치 그룹의 경고가 검색됩니다.</span><span class="sxs-lookup"><span data-stu-id="a6106-193">**NOTE**: When not specified, alerts from all device groups will be retrieved.</span></span> <br><br> <span data-ttu-id="a6106-194">예제:</span><span class="sxs-lookup"><span data-stu-id="a6106-194">Example:</span></span> <br><br> ```https://wdatp-alertexporter-eu.securitycenter.windows.com/api/Alerts/?machinegroups=UKMachines&machinegroups=FranceMachines```
<span data-ttu-id="a6106-195">DeviceCreatedMachineTags</span><span class="sxs-lookup"><span data-stu-id="a6106-195">DeviceCreatedMachineTags</span></span> | <span data-ttu-id="a6106-196">문자열</span><span class="sxs-lookup"><span data-stu-id="a6106-196">string</span></span> | <span data-ttu-id="a6106-197">레지스트리의 단일 장치 태그입니다.</span><span class="sxs-lookup"><span data-stu-id="a6106-197">Single device tag from the registry.</span></span>
<span data-ttu-id="a6106-198">CloudCreatedMachineTags</span><span class="sxs-lookup"><span data-stu-id="a6106-198">CloudCreatedMachineTags</span></span> | <span data-ttu-id="a6106-199">문자열</span><span class="sxs-lookup"><span data-stu-id="a6106-199">string</span></span> | <span data-ttu-id="a6106-200">Microsoft Defender 보안 센터에서 만든 장치 태그입니다.</span><span class="sxs-lookup"><span data-stu-id="a6106-200">Device tags that were created in Microsoft Defender Security Center.</span></span>

### <a name="request-example"></a><span data-ttu-id="a6106-201">요청 예제</span><span class="sxs-lookup"><span data-stu-id="a6106-201">Request example</span></span>
<span data-ttu-id="a6106-202">다음 예제에서는 조직의 모든 검색을 검색하는 방법을 보여 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="a6106-202">The following example demonstrates how to retrieve all the detections in your organization.</span></span>

```http
GET  https://wdatp-alertexporter-eu.windows.com/api/alerts
Authorization: Bearer <your access token>
```

<span data-ttu-id="a6106-203">다음 예제에서는 2016-09-12 00:00:00 이후의 마지막 20개 검색을 요청하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="a6106-203">The following example demonstrates a request to get the last 20 detections since 2016-09-12 00:00:00.</span></span>

```http
GET  https://wdatp-alertexporter-eu.windows.com/api/alerts?limit=20&sinceTimeUtc=2016-09-12T00:00:00.000
Authorization: Bearer <your access token>
```

## <a name="response"></a><span data-ttu-id="a6106-204">응답</span><span class="sxs-lookup"><span data-stu-id="a6106-204">Response</span></span>
<span data-ttu-id="a6106-205">반환 값은 JSON 형식의 경고 개체 배열입니다.</span><span class="sxs-lookup"><span data-stu-id="a6106-205">The return value is an array of alert objects in JSON format.</span></span>

<span data-ttu-id="a6106-206">반환 값의 예는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="a6106-206">Here is an example return value:</span></span>

```json 
[
{        
        "AlertTime": "2020-09-30T14:09:20.35743Z",
        "ComputerDnsName": "mymachine1.domain.com",
        "AlertTitle": "Suspicious File Activity",
        "Category": "Malware",
        "Severity": "High",
        "AlertId": "da637370718981685665_16349121",
        "Actor": "",
        "LinkToWDATP": "https://securitycenter.windows.com/alert/da637370718981685665_16349121",
        "IocName": "",
        "IocValue": "",
        "CreatorIocName": "",
        "CreatorIocValue": "",
        "Sha1": "aabbccddee1122334455aabbccddee1122334455",
        "FileName": "cmdParent.exe",
        "FilePath": "C:\\WINDOWS\\SysWOW64\\boo3\\qwerty",
        "IpAddress": "",
        "Url": "",
        "IoaDefinitionId": "b20af1d2-5990-4672-87f1-acc2a8ff7725",
        "UserName": "",
        "AlertPart": 0,
        "FullId": "da637370718981685665_16349121:R4xEdgAvDb2LQl3BgHoA3NYqKmRSiIAG7dpxAJCYZhY=",
        "LastProcessedTimeUtc": "2020-09-30T14:11:44.0779765Z",
        "ThreatCategory": "",
        "ThreatFamily": "",
        "ThreatName": "",
        "RemediationAction": "",
        "RemediationIsSuccess": null,
        "Source": "EDR",
        "Md5": "854b85cbff2752fcb88606bca76f83c6",
        "Sha256": "",
        "WasExecutingWhileDetected": null,
        "UserDomain": "",
        "LogOnUsers": "",
        "MachineDomain": "domain.com",
        "MachineName": "mymachine1",
        "InternalIPv4List": "",
        "InternalIPv6List": "",
        "FileHash": "aabbccddee1122334455aabbccddee1122334455",
        "DeviceID": "deadbeef000040830ee54503926f556dcaf82bb0",
        "MachineGroup": "",
        "Description": "Test Alert",
        "DeviceCreatedMachineTags": "",
        "CloudCreatedMachineTags": "",
        "CommandLine": "",
        "IncidentLinkToWDATP": "https://securitycenter.windows.com/incidents/byalert?alertId=da637370718981685665_16349121&source=SIEM",
        "ReportID": 1053729833,
        "LinkToMTP": "https://security.microsoft.com/alert/da637370718981685665_16349121",
        "IncidentLinkToMTP": "https://security.microsoft.com/incidents/byalert?alertId=da637370718981685665_16349121&source=SIEM",
        "ExternalId": "31DD0A845DDA4059FDEDE031014645350AECABD3",
        "IocUniqueId": "R4xEdgAvDb2LQl3BgHoA3NYqKmRSiIAG7dpxAJCYZhY="
}
]
```

## <a name="code-examples"></a><span data-ttu-id="a6106-207">코드 예제</span><span class="sxs-lookup"><span data-stu-id="a6106-207">Code examples</span></span>
### <a name="get-access-token"></a><span data-ttu-id="a6106-208">액세스 토큰을 얻다</span><span class="sxs-lookup"><span data-stu-id="a6106-208">Get access token</span></span>
<span data-ttu-id="a6106-209">다음 코드 예제에서는 Endpoint SIEM API용 Microsoft Defender를 호출하기 위한 액세스 토큰을 얻는 방법을 보여 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="a6106-209">The following code examples demonstrate how to obtain an access token for calling the Microsoft Defender for Endpoint SIEM API.</span></span>

```csharp
AuthenticationContext context = new AuthenticationContext(string.Format("https://login.microsoftonline.com/{0}", tenantId));
ClientCredential clientCredentials = new ClientCredential(clientId, clientSecret);
AuthenticationResult authenticationResult = context.AcquireTokenAsync(detectionsResource, clientCredentials).GetAwaiter().GetResult();
```

```PowerShell
#Get current working directory
$scriptDir = Split-Path -Path $MyInvocation.MyCommand.Definition -Parent

#Paste below your Tenant ID, App ID and App Secret (App key).
$tenantId = '' ### Paste your tenant ID here
$appId = '' ### Paste your Application ID here
$appSecret = '' ### Paste your Application secret here

$resourceAppIdUri = 'https://graph.windows.net'
$oAuthUri = "https://login.microsoftonline.com/$tenantId/oauth2/token"
$authBody = [Ordered] @{
    resource = "$resourceAppIdUri"
    client_id = "$appId"
    client_secret = "$appSecret"
    grant_type = 'client_credentials'
}

#call API
$authResponse = Invoke-RestMethod -Method Post -Uri $oAuthUri -Body $authBody -ErrorAction Stop
$authResponse
Out-File -FilePath "$scriptDir\LatestSIEM-token.txt" -InputObject $authResponse.access_token
```

```Bash
tenantId='' ### Paste your tenant ID here
appId='' ### Paste your Application ID here
appSecret='' ### Paste your Application secret here
resourceAppIdUri='https://graph.windows.net'
oAuthUri="https://login.microsoftonline.com/$tenantId/oauth2/token"
scriptDir=$(pwd)

apiResponse=$(curl -s X POST "$oAuthUri" -d "resource=$resourceAppIdUri&client_id=$appId&client_secret=$appSecret&\
        grant_type=client_credentials" | cut -d "{" -f2 | cut -d "}" -f1)
IFS=","
apiResponseArr=($apiResponse)
IFS=":"
tokenArr=(${apiResponseArr[6]})
echo ${tokenArr[1]} | cut -d "\"" -f2 | cut -d "\"" -f1 >> $scriptDir/LatestSIEM-token.txt
```

### <a name="use-token-to-connect-to-the-detections-endpoint"></a><span data-ttu-id="a6106-210">토큰을 사용하여 검색 끝점에 연결</span><span class="sxs-lookup"><span data-stu-id="a6106-210">Use token to connect to the detections endpoint</span></span>
<span data-ttu-id="a6106-211">다음 코드 예제에서는 끝점용 Defender SIEM API를 호출하는 데 액세스 토큰을 사용하여 경고를 표시하는 방법을 보여 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="a6106-211">The following code examples demonstrate how to use an access token for calling the Defender for Endpoint SIEM API to get alerts.</span></span>

```csharp
HttpClient httpClient = new HttpClient();
httpClient.DefaultRequestHeaders.Authorization = new AuthenticationHeaderValue(authenticationResult.AccessTokenType, authenticationResult.AccessToken);
HttpResponseMessage response = httpClient.GetAsync("https://wdatp-alertexporter-eu.windows.com/api/alert").GetAwaiter().GetResult();
string detectionsJson = response.Content.ReadAsStringAsync().Result;
Console.WriteLine("Got detections list: {0}", detectionsJson);
```

```PowerShell
#Get current working directory
$scriptDir = Split-Path -Path $MyInvocation.MyCommand.Definition -Parent

#run the script Get-Token.ps1  - make sure you are running this script from the same folder of Get-SIEMToken.ps1
$token = Get-Content "$scriptDir\LatestSIEM-token.txt"

#Get Alert from the last xx hours 200 in this example. Make sure you have alerts in that time frame.
$dateTime = (Get-Date).ToUniversalTime().AddHours(-200).ToString("o")

#test SIEM API
$url = 'https://wdatp-alertexporter-us.windows.com/api/alerts?limit=20&sinceTimeUtc=2020-01-01T00:00:00.000'

#Set the WebRequest headers
$headers = @{ 
    'Content-Type' = 'application/json'
    Accept = 'application/json'
    Authorization = "Bearer $token" 
}

#Send the webrequest and get the results. 
$response = Invoke-WebRequest -Method Get -Uri $url -Headers $headers -ErrorAction Stop
$response
Write-Host

#Extract the alerts from the results.  This works for SIEM API:
$alerts =  $response.Content | ConvertFrom-Json | ConvertTo-Json

#Get string with the execution time. We concatenate that string to the output file to avoid overwrite the file
$dateTimeForFileName = Get-Date -Format o | foreach {$_ -replace ":", "."}    

#Save the result as json and as csv
$outputJsonPath = "$scriptDir\Latest Alerts $dateTimeForFileName.json"     
$outputCsvPath = "$scriptDir\Latest Alerts $dateTimeForFileName.csv"

Out-File -FilePath $outputJsonPath -InputObject $alerts
Get-Content -Path $outputJsonPath -Raw | ConvertFrom-Json | Select-Object -ExpandProperty value | Export-CSV $outputCsvPath -NoTypeInformation
```

```Bash
#Get current working directory
scriptDir=$(pwd)

#get the token
token=$(<$scriptDir/LatestSIEM-token.txt)

#test the SIEM API, get alerts since 1/1/2020
url='https://wdatp-alertexporter-us.windows.com/api/alerts?limit=20&sinceTimeUtc=2020-01-01T00:00:00.000'

#send web requst to API and echo JSON content
apiResponse=$(curl -s X GET "$url" -H "Content-Type: application/json" -H "Accept: application/json"\
         -H "Authorization: Bearer $token" | cut -d "[" -f2 | cut -d "]" -f1)
echo "If you see Alert info in JSON format, congratulations you accessed the MDATP SIEM API!"
echo
echo $apiResponse
```

## <a name="error-codes"></a><span data-ttu-id="a6106-212">오류 코드</span><span class="sxs-lookup"><span data-stu-id="a6106-212">Error codes</span></span>
<span data-ttu-id="a6106-213">끝점 REST용 Microsoft Defender API는 잘못된 요청으로 인해 발생하는 다음 오류 코드를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="a6106-213">The Microsoft Defender for Endpoint REST API returns the following error codes caused by an invalid request.</span></span>

<span data-ttu-id="a6106-214">HTTP 오류 코드</span><span class="sxs-lookup"><span data-stu-id="a6106-214">HTTP error code</span></span> | <span data-ttu-id="a6106-215">설명</span><span class="sxs-lookup"><span data-stu-id="a6106-215">Description</span></span>
:---|:---
<span data-ttu-id="a6106-216">401</span><span class="sxs-lookup"><span data-stu-id="a6106-216">401</span></span> | <span data-ttu-id="a6106-217">잘못된 요청 또는 잘못된 토큰</span><span class="sxs-lookup"><span data-stu-id="a6106-217">Malformed request or invalid token.</span></span>
<span data-ttu-id="a6106-218">403</span><span class="sxs-lookup"><span data-stu-id="a6106-218">403</span></span> | <span data-ttu-id="a6106-219">무단 예외 - 테넌트 관리자가 관리하지 않는 도메인 또는 테넌트 상태가 삭제됩니다.</span><span class="sxs-lookup"><span data-stu-id="a6106-219">Unauthorized exception - any of the domains is not managed by the tenant administrator or tenant state is deleted.</span></span>
<span data-ttu-id="a6106-220">500</span><span class="sxs-lookup"><span data-stu-id="a6106-220">500</span></span> | <span data-ttu-id="a6106-221">서비스에 오류가 발생했습니다.</span><span class="sxs-lookup"><span data-stu-id="a6106-221">Error in the service.</span></span>

## <a name="related-topics"></a><span data-ttu-id="a6106-222">관련 항목</span><span class="sxs-lookup"><span data-stu-id="a6106-222">Related topics</span></span>
- [<span data-ttu-id="a6106-223">끝점용 Microsoft Defender에서 SIEM 통합 사용</span><span class="sxs-lookup"><span data-stu-id="a6106-223">Enable SIEM integration in Microsoft Defender for Endpoint</span></span>](enable-siem-integration.md)
- [<span data-ttu-id="a6106-224">끝점 검색을 위해 Microsoft Defender를 끌어오도록 ArcSight 구성</span><span class="sxs-lookup"><span data-stu-id="a6106-224">Configure ArcSight to pull Microsoft Defender for Endpoint detections</span></span>](configure-arcsight.md)
- [<span data-ttu-id="a6106-225">SIEM 도구로 검색 끌어오기</span><span class="sxs-lookup"><span data-stu-id="a6106-225">Pull detections to your SIEM tools</span></span>](configure-siem.md)
- [<span data-ttu-id="a6106-226">끝점 검색 필드용 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="a6106-226">Microsoft Defender for Endpoint Detection fields</span></span>](api-portal-mapping.md)
- [<span data-ttu-id="a6106-227">SIEM 도구 통합 문제 해결</span><span class="sxs-lookup"><span data-stu-id="a6106-227">Troubleshoot SIEM tool integration issues</span></span>](troubleshoot-siem.md)
