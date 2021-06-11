---
title: 소프트웨어 ID로 누락된 KB 다운로드
description: 소프트웨어 ID로 누락된 보안 업데이트 검색
keywords: api, 그래프 api, 지원되는 api, get, 목록, 파일, 정보, 소프트웨어 ID, 위협 & 취약성 관리 api, 끝점 tvm api용 Microsoft Defender
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
ms.openlocfilehash: bbb3e5dfe94d5efb026e21a4cbd94fac45f36594
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/08/2021
ms.locfileid: "52845225"
---
# <a name="get-missing-kbs-by-software-id"></a><span data-ttu-id="a29bf-104">소프트웨어 ID로 누락된 KB 다운로드</span><span class="sxs-lookup"><span data-stu-id="a29bf-104">Get missing KBs by software ID</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="a29bf-105">**적용 사항:** [끝점용 Microsoft Defender](https://go.microsoft.com/fwlink/?linkid=2154037)</span><span class="sxs-lookup"><span data-stu-id="a29bf-105">**Applies to:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span></span>

- <span data-ttu-id="a29bf-106">끝점용 Microsoft Defender를 경험하고 싶나요?</span><span class="sxs-lookup"><span data-stu-id="a29bf-106">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="a29bf-107">무료 평가판에 등록합니다.</span><span class="sxs-lookup"><span data-stu-id="a29bf-107">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

<span data-ttu-id="a29bf-108">소프트웨어 ID로 누락된 KB(보안 업데이트)를 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="a29bf-108">Retrieves missing KBs (security updates) by software ID</span></span>

## <a name="permissions"></a><span data-ttu-id="a29bf-109">사용 권한</span><span class="sxs-lookup"><span data-stu-id="a29bf-109">Permissions</span></span>

<span data-ttu-id="a29bf-110">이 API를 호출하려면 다음 권한 중 하나가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="a29bf-110">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="a29bf-111">사용 권한을 선택하는 방법을 포함하여 자세한 내용은 [Use Microsoft Defender for Endpoint API](apis-intro.md) for details을 참조합니다.</span><span class="sxs-lookup"><span data-stu-id="a29bf-111">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md) for details.</span></span>

<span data-ttu-id="a29bf-112">사용 권한 유형</span><span class="sxs-lookup"><span data-stu-id="a29bf-112">Permission type</span></span> |   <span data-ttu-id="a29bf-113">사용 권한</span><span class="sxs-lookup"><span data-stu-id="a29bf-113">Permission</span></span>   |   <span data-ttu-id="a29bf-114">사용 권한 표시 이름</span><span class="sxs-lookup"><span data-stu-id="a29bf-114">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="a29bf-115">응용 프로그램</span><span class="sxs-lookup"><span data-stu-id="a29bf-115">Application</span></span> |<span data-ttu-id="a29bf-116">Software.Read.All</span><span class="sxs-lookup"><span data-stu-id="a29bf-116">Software.Read.All</span></span> |   <span data-ttu-id="a29bf-117">'위협 및 취약성 관리 소프트웨어 정보 읽기'</span><span class="sxs-lookup"><span data-stu-id="a29bf-117">'Read Threat and Vulnerability Management Software information'</span></span>
<span data-ttu-id="a29bf-118">위임(직장 또는 학교 계정)</span><span class="sxs-lookup"><span data-stu-id="a29bf-118">Delegated (work or school account)</span></span> | <span data-ttu-id="a29bf-119">Software.Read</span><span class="sxs-lookup"><span data-stu-id="a29bf-119">Software.Read</span></span> |   <span data-ttu-id="a29bf-120">'위협 및 취약성 관리 소프트웨어 정보 읽기'</span><span class="sxs-lookup"><span data-stu-id="a29bf-120">'Read Threat and Vulnerability Management Software information'</span></span>

## <a name="http-request"></a><span data-ttu-id="a29bf-121">HTTP 요청</span><span class="sxs-lookup"><span data-stu-id="a29bf-121">HTTP request</span></span>

```
GET /api/Software/{Id}/getmissingkbs
```

## <a name="request-header"></a><span data-ttu-id="a29bf-122">요청 헤더</span><span class="sxs-lookup"><span data-stu-id="a29bf-122">Request header</span></span>

<span data-ttu-id="a29bf-123">이름</span><span class="sxs-lookup"><span data-stu-id="a29bf-123">Name</span></span> | <span data-ttu-id="a29bf-124">유형</span><span class="sxs-lookup"><span data-stu-id="a29bf-124">Type</span></span> | <span data-ttu-id="a29bf-125">설명</span><span class="sxs-lookup"><span data-stu-id="a29bf-125">Description</span></span>
:---|:---|:---
<span data-ttu-id="a29bf-126">권한 부여</span><span class="sxs-lookup"><span data-stu-id="a29bf-126">Authorization</span></span> | <span data-ttu-id="a29bf-127">String</span><span class="sxs-lookup"><span data-stu-id="a29bf-127">String</span></span> | <span data-ttu-id="a29bf-128">Bearer {token}.</span><span class="sxs-lookup"><span data-stu-id="a29bf-128">Bearer {token}.</span></span> <span data-ttu-id="a29bf-129">**필수입니다**.</span><span class="sxs-lookup"><span data-stu-id="a29bf-129">**Required**.</span></span>

## <a name="request-body"></a><span data-ttu-id="a29bf-130">요청 본문</span><span class="sxs-lookup"><span data-stu-id="a29bf-130">Request body</span></span>

<span data-ttu-id="a29bf-131">비어 있음</span><span class="sxs-lookup"><span data-stu-id="a29bf-131">Empty</span></span>

## <a name="response"></a><span data-ttu-id="a29bf-132">응답</span><span class="sxs-lookup"><span data-stu-id="a29bf-132">Response</span></span>

<span data-ttu-id="a29bf-133">성공하면 이 메서드는 지정된 소프트웨어에 본문에 kb 데이터가 누락된 200 OK를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="a29bf-133">If successful, this method returns 200 OK, with the specified software missing kb data in the body.</span></span>

## <a name="example"></a><span data-ttu-id="a29bf-134">예시</span><span class="sxs-lookup"><span data-stu-id="a29bf-134">Example</span></span>

### <a name="request"></a><span data-ttu-id="a29bf-135">요청</span><span class="sxs-lookup"><span data-stu-id="a29bf-135">Request</span></span>

<span data-ttu-id="a29bf-136">다음은 요청의 예입니다.</span><span class="sxs-lookup"><span data-stu-id="a29bf-136">Here is an example of the request.</span></span>

```
GET https://api.securitycenter.microsoft.com/api/Software/microsoft-_-edge/getmissingkbs
```

### <a name="response"></a><span data-ttu-id="a29bf-137">응답</span><span class="sxs-lookup"><span data-stu-id="a29bf-137">Response</span></span>

<span data-ttu-id="a29bf-138">다음은 응답의 예입니다.</span><span class="sxs-lookup"><span data-stu-id="a29bf-138">Here is an example of the response.</span></span>


```json
{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#Collection(microsoft.windowsDefenderATP.api.PublicProductFixDto)",
    "value": [
         {
            "id": "4540673",
            "name": "March 2020 Security Updates",
            "productsNames": [
                "edge"
            ],
            "url": "https://catalog.update.microsoft.com/v7/site/Search.aspx?q=KB4540673",
            "machineMissedOn": 240,
            "cveAddressed": 14
         },
         ...
        ]
}
```

## <a name="related-topics"></a><span data-ttu-id="a29bf-139">관련 항목</span><span class="sxs-lookup"><span data-stu-id="a29bf-139">Related topics</span></span>

- [<span data-ttu-id="a29bf-140">위험 기반 위협 & 관리</span><span class="sxs-lookup"><span data-stu-id="a29bf-140">Risk-based Threat & Vulnerability Management</span></span>](/microsoft-365/security/defender-endpoint/next-gen-threat-and-vuln-mgt)
- [<span data-ttu-id="a29bf-141">위협 & 소프트웨어 인벤토리</span><span class="sxs-lookup"><span data-stu-id="a29bf-141">Threat & Vulnerability software inventory</span></span>](/microsoft-365/security/defender-endpoint/tvm-software-inventory)
