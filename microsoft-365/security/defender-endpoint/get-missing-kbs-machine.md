---
title: 장치 ID로 누락된 KB 사용
description: 장치 ID로 누락된 보안 업데이트 검색
keywords: api, 그래프 api, 지원되는 api, get, 목록, 파일, 정보, 장치 ID, 위협 & 취약성 관리 api, 끝점 tvm api용 Microsoft Defender
search.product: eADQiWindows 10XVcnh
ms.prod: w10
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
MS.technology: mde
ms.custom: api
ms.openlocfilehash: 97cad51938c4ff3498234dbf2e9d69fd48a52367
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/04/2021
ms.locfileid: "52771876"
---
# <a name="get-missing-kbs-by-device-id"></a><span data-ttu-id="0a746-104">장치 ID로 누락된 KB 사용</span><span class="sxs-lookup"><span data-stu-id="0a746-104">Get missing KBs by device ID</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="0a746-105">**적용 사항:** [끝점용 Microsoft Defender](https://go.microsoft.com/fwlink/?linkid=2154037)</span><span class="sxs-lookup"><span data-stu-id="0a746-105">**Applies to:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span></span>

- <span data-ttu-id="0a746-106">끝점용 Microsoft Defender를 경험하고 싶나요?</span><span class="sxs-lookup"><span data-stu-id="0a746-106">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="0a746-107">무료 평가판에 등록합니다.</span><span class="sxs-lookup"><span data-stu-id="0a746-107">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

<span data-ttu-id="0a746-108">장치 ID로 누락된 KB(보안 업데이트)를 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="0a746-108">Retrieves missing KBs (security updates) by device ID</span></span>

## <a name="http-request"></a><span data-ttu-id="0a746-109">HTTP 요청</span><span class="sxs-lookup"><span data-stu-id="0a746-109">HTTP request</span></span>

```
GET /api/machines/{machineId}/getmissingkbs
```

## <a name="request-header"></a><span data-ttu-id="0a746-110">요청 헤더</span><span class="sxs-lookup"><span data-stu-id="0a746-110">Request header</span></span>

<span data-ttu-id="0a746-111">이름</span><span class="sxs-lookup"><span data-stu-id="0a746-111">Name</span></span> | <span data-ttu-id="0a746-112">유형</span><span class="sxs-lookup"><span data-stu-id="0a746-112">Type</span></span> | <span data-ttu-id="0a746-113">설명</span><span class="sxs-lookup"><span data-stu-id="0a746-113">Description</span></span>
:---|:---|:---
<span data-ttu-id="0a746-114">권한 부여</span><span class="sxs-lookup"><span data-stu-id="0a746-114">Authorization</span></span> | <span data-ttu-id="0a746-115">String</span><span class="sxs-lookup"><span data-stu-id="0a746-115">String</span></span> | <span data-ttu-id="0a746-116">Bearer {token}.</span><span class="sxs-lookup"><span data-stu-id="0a746-116">Bearer {token}.</span></span> <span data-ttu-id="0a746-117">**필수입니다**.</span><span class="sxs-lookup"><span data-stu-id="0a746-117">**Required**.</span></span>

## <a name="request-body"></a><span data-ttu-id="0a746-118">요청 본문</span><span class="sxs-lookup"><span data-stu-id="0a746-118">Request body</span></span>

<span data-ttu-id="0a746-119">비어 있음</span><span class="sxs-lookup"><span data-stu-id="0a746-119">Empty</span></span>

## <a name="response"></a><span data-ttu-id="0a746-120">응답</span><span class="sxs-lookup"><span data-stu-id="0a746-120">Response</span></span>

<span data-ttu-id="0a746-121">성공하면 이 메서드는 200 OK를 반환하고 지정된 디바이스에 본문에 kb 데이터가 누락됩니다.</span><span class="sxs-lookup"><span data-stu-id="0a746-121">If successful, this method returns 200 OK, with the specified device missing kb data in the body.</span></span>

## <a name="example"></a><span data-ttu-id="0a746-122">예시</span><span class="sxs-lookup"><span data-stu-id="0a746-122">Example</span></span>

### <a name="request"></a><span data-ttu-id="0a746-123">요청</span><span class="sxs-lookup"><span data-stu-id="0a746-123">Request</span></span>

<span data-ttu-id="0a746-124">다음은 요청의 예입니다.</span><span class="sxs-lookup"><span data-stu-id="0a746-124">Here is an example of the request.</span></span>

```
GET https://api.securitycenter.microsoft.com/api/machines/2339ad14a01bd0299afb93dfa2550136057bff96/getmissingkbs 
```

### <a name="response"></a><span data-ttu-id="0a746-125">응답</span><span class="sxs-lookup"><span data-stu-id="0a746-125">Response</span></span>

<span data-ttu-id="0a746-126">다음은 응답의 예입니다.</span><span class="sxs-lookup"><span data-stu-id="0a746-126">Here is an example of the response.</span></span>


```json
{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#Collection(microsoft.windowsDefenderATP.api.PublicProductFixDto)",
    "value": [
        {
            "id": "4540673",
            "name": "March 2020 Security Updates",
            "productsNames": [
                "windows_10",
                "edge",
                "internet_explorer"
            ],
            "url": "https://catalog.update.microsoft.com/v7/site/Search.aspx?q=KB4540673",
            "machineMissedOn": 1,
            "cveAddressed": 97
        },
         ...
        ]
}
```

## <a name="related-topics"></a><span data-ttu-id="0a746-127">관련 항목</span><span class="sxs-lookup"><span data-stu-id="0a746-127">Related topics</span></span>

- [<span data-ttu-id="0a746-128">위험 기반 위협 & 관리</span><span class="sxs-lookup"><span data-stu-id="0a746-128">Risk-based Threat & Vulnerability Management</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/next-gen-threat-and-vuln-mgt)
- [<span data-ttu-id="0a746-129">위협 & 소프트웨어 인벤토리</span><span class="sxs-lookup"><span data-stu-id="0a746-129">Threat & Vulnerability software inventory</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/tvm-software-inventory)
