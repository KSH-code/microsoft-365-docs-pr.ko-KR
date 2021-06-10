---
title: 컴퓨터 보안 상태 수집 API를 얻습니다.
description: 끝점용 Microsoft Defender를 사용하여 장치 보안 상태 컬렉션을 검색합니다.
keywords: api, 그래프 api, 지원되는 api, get, 장치, 보안, 상태
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: w10
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: leonidzh
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.openlocfilehash: 9dab4bdccc1fead5bc2cc5b9bdff8f2a45b6c8db
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51200368"
---
# <a name="get-machines-security-states-collection-api"></a><span data-ttu-id="f3b0e-104">컴퓨터 보안 상태 수집 API를 얻습니다.</span><span class="sxs-lookup"><span data-stu-id="f3b0e-104">Get Machines security states collection API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="f3b0e-105">**적용 사항:** [끝점용 Microsoft Defender](https://go.microsoft.com/fwlink/?linkid=2154037)</span><span class="sxs-lookup"><span data-stu-id="f3b0e-105">**Applies to:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span></span>

- <span data-ttu-id="f3b0e-106">끝점용 Microsoft Defender를 경험하고 싶나요?</span><span class="sxs-lookup"><span data-stu-id="f3b0e-106">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="f3b0e-107">무료 평가판에 등록합니다.</span><span class="sxs-lookup"><span data-stu-id="f3b0e-107">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

<span data-ttu-id="f3b0e-108">장치 보안 상태 컬렉션을 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="f3b0e-108">Retrieves a collection of devices security states.</span></span>

## <a name="permissions"></a><span data-ttu-id="f3b0e-109">사용 권한</span><span class="sxs-lookup"><span data-stu-id="f3b0e-109">Permissions</span></span>
<span data-ttu-id="f3b0e-110">사용자에게 읽기 권한이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="f3b0e-110">User needs read permissions.</span></span>

## <a name="http-request"></a><span data-ttu-id="f3b0e-111">HTTP 요청</span><span class="sxs-lookup"><span data-stu-id="f3b0e-111">HTTP request</span></span>
```
GET /testwdatppreview/machinesecuritystates
```

## <a name="request-headers"></a><span data-ttu-id="f3b0e-112">요청 헤더</span><span class="sxs-lookup"><span data-stu-id="f3b0e-112">Request headers</span></span>

<span data-ttu-id="f3b0e-113">머리글</span><span class="sxs-lookup"><span data-stu-id="f3b0e-113">Header</span></span> | <span data-ttu-id="f3b0e-114">값</span><span class="sxs-lookup"><span data-stu-id="f3b0e-114">Value</span></span> 
:---|:---
<span data-ttu-id="f3b0e-115">권한 부여</span><span class="sxs-lookup"><span data-stu-id="f3b0e-115">Authorization</span></span> | <span data-ttu-id="f3b0e-116">Bearer {token}.</span><span class="sxs-lookup"><span data-stu-id="f3b0e-116">Bearer {token}.</span></span> <span data-ttu-id="f3b0e-117">**필수입니다**.</span><span class="sxs-lookup"><span data-stu-id="f3b0e-117">**Required**.</span></span>
<span data-ttu-id="f3b0e-118">콘텐츠 형식</span><span class="sxs-lookup"><span data-stu-id="f3b0e-118">Content type</span></span> | <span data-ttu-id="f3b0e-119">application/json</span><span class="sxs-lookup"><span data-stu-id="f3b0e-119">application/json</span></span>

## <a name="request-body"></a><span data-ttu-id="f3b0e-120">요청 본문</span><span class="sxs-lookup"><span data-stu-id="f3b0e-120">Request body</span></span>
<span data-ttu-id="f3b0e-121">비어 있음</span><span class="sxs-lookup"><span data-stu-id="f3b0e-121">Empty</span></span>

## <a name="response"></a><span data-ttu-id="f3b0e-122">응답</span><span class="sxs-lookup"><span data-stu-id="f3b0e-122">Response</span></span>
<span data-ttu-id="f3b0e-123">성공적이면 - 200 OK.</span><span class="sxs-lookup"><span data-stu-id="f3b0e-123">If successful - 200 OK.</span></span>

## <a name="example"></a><span data-ttu-id="f3b0e-124">예시</span><span class="sxs-lookup"><span data-stu-id="f3b0e-124">Example</span></span>

<span data-ttu-id="f3b0e-125">**요청**</span><span class="sxs-lookup"><span data-stu-id="f3b0e-125">**Request**</span></span>

<span data-ttu-id="f3b0e-126">다음은 요청의 예입니다.</span><span class="sxs-lookup"><span data-stu-id="f3b0e-126">Here is an example of the request.</span></span>

```
GET https://graph.microsoft.com/testwdatppreview/machinesecuritystates
Content-type: application/json
```

<span data-ttu-id="f3b0e-127">**응답**</span><span class="sxs-lookup"><span data-stu-id="f3b0e-127">**Response**</span></span>

<span data-ttu-id="f3b0e-128">다음은 응답의 예입니다.</span><span class="sxs-lookup"><span data-stu-id="f3b0e-128">Here is an example of the response.</span></span>
<span data-ttu-id="f3b0e-129">필드 *ID는* 디바이스 ID를 포함하며 디바이스 정보의 필드 \*ID\*\*에 해당합니다.</span><span class="sxs-lookup"><span data-stu-id="f3b0e-129">Field *id* contains device id and equal to the field *id*\* in devices info.</span></span> 

```
HTTP/1.1 200 OK
Content-type: application/json
{
    "@odata.context":"https://graph.microsoft.com/testwdatppreview/$metadata#MachineSecurityStates",
    "@odata.count":444,
    "@odata.nextLink":"https://graph.microsoft.com/testwdatppreview/machinesecuritystates?$skiptoken=[continuation token]",
    "value":[
        {
            "id":"000050e1b4afeee3742489ede9ad7a3e16bbd9c4",
            "build":14393,
            "revision":2485,
            "architecture":"Amd64",
            "osVersion":"10.0.14393.2485.amd64fre.rs1_release.180827-1809",
            "propertiesRequireAttention":[
                "AntivirusNotReporting",
                "EdrImpairedCommunications"
            ]
        },
        …
    ]
}
```
