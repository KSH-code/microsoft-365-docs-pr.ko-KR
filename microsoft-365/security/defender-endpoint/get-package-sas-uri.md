---
title: 패키지 SAS URI API를 얻습니다.
description: 이 API를 사용하여 조사 패키지 다운로드를 허용하는 URI를 얻습니다.
keywords: api, 그래프 api, 지원되는 api, 패키지, sas, uri
search.product: eADQiWindows 10XVcnh
ms.prod: w10
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
ms.openlocfilehash: 054db1766cdab3aa5b49da4940dcdddfe6086434
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/04/2021
ms.locfileid: "52770688"
---
# <a name="get-package-sas-uri-api"></a><span data-ttu-id="52bcd-104">패키지 SAS URI API를 얻습니다.</span><span class="sxs-lookup"><span data-stu-id="52bcd-104">Get package SAS URI API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="52bcd-105">**적용 사항:** [끝점용 Microsoft Defender](https://go.microsoft.com/fwlink/?linkid=2154037)</span><span class="sxs-lookup"><span data-stu-id="52bcd-105">**Applies to:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span></span>

- <span data-ttu-id="52bcd-106">끝점용 Microsoft Defender를 경험하고 싶나요?</span><span class="sxs-lookup"><span data-stu-id="52bcd-106">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="52bcd-107">무료 평가판에 등록합니다.</span><span class="sxs-lookup"><span data-stu-id="52bcd-107">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

## <a name="api-description"></a><span data-ttu-id="52bcd-108">API 설명</span><span class="sxs-lookup"><span data-stu-id="52bcd-108">API description</span></span>
<span data-ttu-id="52bcd-109">조사 패키지 다운로드를 허용하는 [URI를 다운로드합니다.](collect-investigation-package.md)</span><span class="sxs-lookup"><span data-stu-id="52bcd-109">Get a URI that allows downloading of an [Investigation package](collect-investigation-package.md).</span></span>


## <a name="permissions"></a><span data-ttu-id="52bcd-110">사용 권한</span><span class="sxs-lookup"><span data-stu-id="52bcd-110">Permissions</span></span>
<span data-ttu-id="52bcd-111">이 API를 호출하려면 다음 권한 중 하나가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="52bcd-111">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="52bcd-112">권한을 선택하는 방법을 포함하여 자세한 내용은 [끝점 API용 Microsoft Defender 액세스를 참조합니다.](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="52bcd-112">To learn more, including how to choose permissions, see [Access the Microsoft Defender for Endpoint APIs](apis-intro.md)</span></span>

<span data-ttu-id="52bcd-113">사용 권한 유형</span><span class="sxs-lookup"><span data-stu-id="52bcd-113">Permission type</span></span> |   <span data-ttu-id="52bcd-114">사용 권한</span><span class="sxs-lookup"><span data-stu-id="52bcd-114">Permission</span></span>  |   <span data-ttu-id="52bcd-115">사용 권한 표시 이름</span><span class="sxs-lookup"><span data-stu-id="52bcd-115">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="52bcd-116">응용 프로그램</span><span class="sxs-lookup"><span data-stu-id="52bcd-116">Application</span></span> |   <span data-ttu-id="52bcd-117">Machine.CollectForensics</span><span class="sxs-lookup"><span data-stu-id="52bcd-117">Machine.CollectForensics</span></span> |  <span data-ttu-id="52bcd-118">'포렌식 수집'</span><span class="sxs-lookup"><span data-stu-id="52bcd-118">'Collect forensics'</span></span>
<span data-ttu-id="52bcd-119">위임(직장 또는 학교 계정)</span><span class="sxs-lookup"><span data-stu-id="52bcd-119">Delegated (work or school account)</span></span> | <span data-ttu-id="52bcd-120">Machine.CollectForensics</span><span class="sxs-lookup"><span data-stu-id="52bcd-120">Machine.CollectForensics</span></span> | <span data-ttu-id="52bcd-121">'포렌식 수집'</span><span class="sxs-lookup"><span data-stu-id="52bcd-121">'Collect forensics'</span></span>

>[!Note]
> <span data-ttu-id="52bcd-122">사용자 자격 증명을 사용하여 토큰을 얻을 때:</span><span class="sxs-lookup"><span data-stu-id="52bcd-122">When obtaining a token using user credentials:</span></span>
>- <span data-ttu-id="52bcd-123">사용자에게 최소한 '경고 조사'와 같은 역할 권한이 필요합니다(자세한 내용은 역할 [만들기](user-roles.md) 및 관리 참조).</span><span class="sxs-lookup"><span data-stu-id="52bcd-123">The user needs to have at least the following role permission: 'Alerts Investigation' (See [Create and manage roles](user-roles.md) for more information)</span></span>
>- <span data-ttu-id="52bcd-124">사용자는 장치 그룹 설정에 따라 장치에 액세스할 수 있습니다(자세한 내용은 장치 그룹 만들기 및 [관리](machine-groups.md) 참조).</span><span class="sxs-lookup"><span data-stu-id="52bcd-124">The user needs to have access to the device, based on device group settings (See [Create and manage device groups](machine-groups.md) for more information)</span></span>

## <a name="http-request"></a><span data-ttu-id="52bcd-125">HTTP 요청</span><span class="sxs-lookup"><span data-stu-id="52bcd-125">HTTP request</span></span>

```http
GET https://api.securitycenter.microsoft.com/api/machineactions/{machine action id}/getPackageUri
```

## <a name="request-headers"></a><span data-ttu-id="52bcd-126">요청 헤더</span><span class="sxs-lookup"><span data-stu-id="52bcd-126">Request headers</span></span>

<span data-ttu-id="52bcd-127">이름</span><span class="sxs-lookup"><span data-stu-id="52bcd-127">Name</span></span> | <span data-ttu-id="52bcd-128">유형</span><span class="sxs-lookup"><span data-stu-id="52bcd-128">Type</span></span> | <span data-ttu-id="52bcd-129">설명</span><span class="sxs-lookup"><span data-stu-id="52bcd-129">Description</span></span>
:---|:---|:---
<span data-ttu-id="52bcd-130">권한 부여</span><span class="sxs-lookup"><span data-stu-id="52bcd-130">Authorization</span></span> | <span data-ttu-id="52bcd-131">String</span><span class="sxs-lookup"><span data-stu-id="52bcd-131">String</span></span> | <span data-ttu-id="52bcd-132">Bearer {token}.</span><span class="sxs-lookup"><span data-stu-id="52bcd-132">Bearer {token}.</span></span> <span data-ttu-id="52bcd-133">**필수입니다**.</span><span class="sxs-lookup"><span data-stu-id="52bcd-133">**Required**.</span></span>


## <a name="request-body"></a><span data-ttu-id="52bcd-134">요청 본문</span><span class="sxs-lookup"><span data-stu-id="52bcd-134">Request body</span></span>

<span data-ttu-id="52bcd-135">비어 있음</span><span class="sxs-lookup"><span data-stu-id="52bcd-135">Empty</span></span>

## <a name="response"></a><span data-ttu-id="52bcd-136">응답</span><span class="sxs-lookup"><span data-stu-id="52bcd-136">Response</span></span>

<span data-ttu-id="52bcd-137">성공하면 이 메서드는 "value" 매개 변수에 패키지에 대한 링크를 보유하는 개체가 있는 200, 확인 응답 코드를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="52bcd-137">If successful, this method returns 200, Ok response code with object that holds the link to the package in the “value” parameter.</span></span> <span data-ttu-id="52bcd-138">이 링크는 매우 짧은 시간 동안 유효하며 로컬 저장소에 패키지를 다운로드하는 데 즉시 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="52bcd-138">This link is valid for a very short time and should be used immediately for downloading the package to a local storage.</span></span>


## <a name="example"></a><span data-ttu-id="52bcd-139">예시</span><span class="sxs-lookup"><span data-stu-id="52bcd-139">Example</span></span>

<span data-ttu-id="52bcd-140">**요청**</span><span class="sxs-lookup"><span data-stu-id="52bcd-140">**Request**</span></span>

<span data-ttu-id="52bcd-141">다음은 요청의 예입니다.</span><span class="sxs-lookup"><span data-stu-id="52bcd-141">Here is an example of the request.</span></span>

```http
GET https://api.securitycenter.microsoft.com/api/machineactions/7327b54fd718525cbca07dacde913b5ac3c85673/GetPackageUri

```

<span data-ttu-id="52bcd-142">**응답**</span><span class="sxs-lookup"><span data-stu-id="52bcd-142">**Response**</span></span>

<span data-ttu-id="52bcd-143">다음은 응답의 예입니다.</span><span class="sxs-lookup"><span data-stu-id="52bcd-143">Here is an example of the response.</span></span>

```http
HTTP/1.1 200 Ok
Content-type: application/json

{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#Edm.String",
    "value": "\"https://userrequests-us.securitycenter.windows.com:443/safedownload/WDATP_Investigation_Package.zip?token=gbDyj7y%2fbWGAZjn2sFiZXlliBTXOCVG7yiJ6mXNaQ9pLByC2Wxeno9mENsPFP3xMk5l%2bZiJXjLvqAyNEzUNROxoM2I1er9dxzfVeBsxSmclJjPsAx%2btiNyxSz1Ax%2b5jaT5cL5bZg%2b8wgbwY9urXbTpGjAKh6FB1e%2b0ypcWkPm8UkfOwsmtC%2biZJ2%2bPqnkkeQk7SKMNoAvmh9%2fcqDIPKXGIBjMa0D9auzypOqd8bQXp7p2BnLSH136BxST8n9IHR4PILvRjAYW9kvtHkBpBitfydAsUW4g2oDZSPN3kCLBOoo1C4w4Lkc9Bc3GNU2IW6dfB7SHcp7G9p4BDkeJl3VuDs6esCaeBorpn9FKJ%2fXo7o9pdcI0hUPZ6Ds9hiPpwPUtz5J29CBE3QAopCK%2fsWlf6OW2WyXsrNRSnF1tVE5H3wXpREzuhD7S4AIA3OIEZKzC4jIPLeMu%2bazZU9xGwuc3gICOaokbwMJiZTqcUuK%2fV9YdBdjdg8wJ16NDU96Pl6%2fgew2KYuk6Wo7ZuHotgHI1abcsvdlpe4AvixDbqcRJthsg2PpLRaFLm5av44UGkeK6TJpFvxUn%2f9fg6Zk5yM1KUTHb8XGmutoCM8U9er6AzXZlY0gGc3D3bQOg41EJZkEZLyUEbk1hXJB36ku2%2bW01cG71t7MxMBYz7%2bdXobxpdo%3d%3bRWS%2bCeoDfTyDcfH5pkCg6hYDmCOPr%2fHYQuaUWUBNVnXURYkdyOzVHqp%2fe%2f1BNyPdVoVkpQHpz1pPS3b5g9h7IMmNKCk5gFq5m2nPx6kk9EYtzx8Ndoa2m9Yj%2bSaf8zIFke86YnfQL4AYewsnQNJJh4wc%2bXxGlBq7axDcoiOdX91rKzVicH3GSBkFoLFAKoegWWsF%2fEDZcVpF%2fXUA1K8HvB6dwyfy4y0sAqnNPxYTQ97mG7yHhxPt4Pe9YF2UPPAJVuEf8LNlQ%2bWHC9%2f7msF6UUI4%2fca%2ftpjFs%2fSNeRE8%2fyQj21TI8YTF1SowvaJuDc1ivEoeopNNGG%2bGI%2fX0SckaVxU9Hdkh0zbydSlT5SZwbSwescs0IpzECitBbaLUz4aT8KTs8T0lvx8D7Te3wVsKAJ1r3iFMQZrlk%2bS1WW8rvac7oHRx2HKURn1v7fDIQWgJr9aNsNlFz4fLJ50T2qSHuuepkLVbe93Va072aMGhvr09WVKoTpAf1j2bcFZZU6Za5PxI32mr0k90FgiYFJ1F%2f1vRDrGwvWVWUkR3Z33m4g0gHa52W1FMxQY0TJIwbovD6FaSNDx7xhKZSd5IJ7r6P91Gez49PaZRcAZPjd%2bfbul3JNm1VqQPTLohT7wa0ymRiXpSST74xtFzuEBzNSNATdbngj3%2fwV4JesTjZjIj5Dc%3d%3blumqauVlFuuO8MQffZgs0tLJ4Fq6fpeozPTdDf8Ll6XLegi079%2b4mSPFjTK0y6eohstxdoOdom2wAHiZwk0u4KLKmRkfYOdT1wHY79qKoBQ3ZDHFTys9V%2fcwKGl%2bl8IenWDutHygn5IcA1y7GTZj4g%3d%3d\""
}
```
