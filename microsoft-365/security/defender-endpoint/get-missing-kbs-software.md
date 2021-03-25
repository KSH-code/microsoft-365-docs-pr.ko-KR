---
title: 소프트웨어 ID로 누락된 KB 다운로드
description: 소프트웨어 ID로 누락된 보안 업데이트 검색
keywords: api, 그래프 api, 지원되는 api, get, 목록, 파일, 정보, 소프트웨어 ID, 위협 & 취약성 관리 api, mdatp tvm api
search.product: eADQiWindows 10XVcnh
ms.prod: w10
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: ellevin
author: levinec
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.openlocfilehash: c90854b043674a61c4996456c9d718b3c25afd1c
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51197792"
---
# <a name="get-missing-kbs-by-software-id"></a><span data-ttu-id="31488-104">소프트웨어 ID로 누락된 KB 다운로드</span><span class="sxs-lookup"><span data-stu-id="31488-104">Get missing KBs by software ID</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="31488-105">**적용 사항:** [끝점용 Microsoft Defender](https://go.microsoft.com/fwlink/?linkid=2154037)</span><span class="sxs-lookup"><span data-stu-id="31488-105">**Applies to:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span></span>

- <span data-ttu-id="31488-106">끝점용 Microsoft Defender를 경험하고 싶나요?</span><span class="sxs-lookup"><span data-stu-id="31488-106">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="31488-107">무료 평가판에 등록합니다.</span><span class="sxs-lookup"><span data-stu-id="31488-107">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

<span data-ttu-id="31488-108">소프트웨어 ID로 누락된 KB(보안 업데이트)를 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="31488-108">Retrieves missing KBs (security updates) by software ID</span></span>

## <a name="permissions"></a><span data-ttu-id="31488-109">사용 권한</span><span class="sxs-lookup"><span data-stu-id="31488-109">Permissions</span></span>

<span data-ttu-id="31488-110">이 API를 호출하려면 다음 권한 중 하나가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="31488-110">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="31488-111">사용 권한을 선택하는 방법을 포함하여 자세한 내용은 [Use Microsoft Defender for Endpoint API](apis-intro.md) for details을 참조합니다.</span><span class="sxs-lookup"><span data-stu-id="31488-111">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md) for details.</span></span>

<span data-ttu-id="31488-112">사용 권한 유형</span><span class="sxs-lookup"><span data-stu-id="31488-112">Permission type</span></span> |   <span data-ttu-id="31488-113">사용 권한</span><span class="sxs-lookup"><span data-stu-id="31488-113">Permission</span></span>   |   <span data-ttu-id="31488-114">사용 권한 표시 이름</span><span class="sxs-lookup"><span data-stu-id="31488-114">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="31488-115">응용 프로그램</span><span class="sxs-lookup"><span data-stu-id="31488-115">Application</span></span> |<span data-ttu-id="31488-116">Software.Read.All</span><span class="sxs-lookup"><span data-stu-id="31488-116">Software.Read.All</span></span> |   <span data-ttu-id="31488-117">'위협 및 취약성 관리 소프트웨어 정보 읽기'</span><span class="sxs-lookup"><span data-stu-id="31488-117">'Read Threat and Vulnerability Management Software information'</span></span>
<span data-ttu-id="31488-118">위임(직장 또는 학교 계정)</span><span class="sxs-lookup"><span data-stu-id="31488-118">Delegated (work or school account)</span></span> | <span data-ttu-id="31488-119">Software.Read</span><span class="sxs-lookup"><span data-stu-id="31488-119">Software.Read</span></span> |   <span data-ttu-id="31488-120">'위협 및 취약성 관리 소프트웨어 정보 읽기'</span><span class="sxs-lookup"><span data-stu-id="31488-120">'Read Threat and Vulnerability Management Software information'</span></span>

## <a name="http-request"></a><span data-ttu-id="31488-121">HTTP 요청</span><span class="sxs-lookup"><span data-stu-id="31488-121">HTTP request</span></span>

```
GET /api/Software/{Id}/getmissingkbs
```

## <a name="request-header"></a><span data-ttu-id="31488-122">요청 헤더</span><span class="sxs-lookup"><span data-stu-id="31488-122">Request header</span></span>

<span data-ttu-id="31488-123">이름</span><span class="sxs-lookup"><span data-stu-id="31488-123">Name</span></span> | <span data-ttu-id="31488-124">유형</span><span class="sxs-lookup"><span data-stu-id="31488-124">Type</span></span> | <span data-ttu-id="31488-125">설명</span><span class="sxs-lookup"><span data-stu-id="31488-125">Description</span></span>
:---|:---|:---
<span data-ttu-id="31488-126">권한 부여</span><span class="sxs-lookup"><span data-stu-id="31488-126">Authorization</span></span> | <span data-ttu-id="31488-127">문자열</span><span class="sxs-lookup"><span data-stu-id="31488-127">String</span></span> | <span data-ttu-id="31488-128">Bearer {token}.</span><span class="sxs-lookup"><span data-stu-id="31488-128">Bearer {token}.</span></span> <span data-ttu-id="31488-129">**필수입니다**.</span><span class="sxs-lookup"><span data-stu-id="31488-129">**Required**.</span></span>

## <a name="request-body"></a><span data-ttu-id="31488-130">요청 본문</span><span class="sxs-lookup"><span data-stu-id="31488-130">Request body</span></span>

<span data-ttu-id="31488-131">비어 있음</span><span class="sxs-lookup"><span data-stu-id="31488-131">Empty</span></span>

## <a name="response"></a><span data-ttu-id="31488-132">응답</span><span class="sxs-lookup"><span data-stu-id="31488-132">Response</span></span>

<span data-ttu-id="31488-133">성공하면 이 메서드는 지정된 소프트웨어에 본문에 kb 데이터가 누락된 200 OK를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="31488-133">If successful, this method returns 200 OK, with the specified software missing kb data in the body.</span></span>

## <a name="example"></a><span data-ttu-id="31488-134">예제</span><span class="sxs-lookup"><span data-stu-id="31488-134">Example</span></span>

### <a name="request"></a><span data-ttu-id="31488-135">요청</span><span class="sxs-lookup"><span data-stu-id="31488-135">Request</span></span>

<span data-ttu-id="31488-136">다음은 요청의 예입니다.</span><span class="sxs-lookup"><span data-stu-id="31488-136">Here is an example of the request.</span></span>

```
GET https://api.securitycenter.microsoft.com/api/Software/microsoft-_-edge/getmissingkbs
```

### <a name="response"></a><span data-ttu-id="31488-137">응답</span><span class="sxs-lookup"><span data-stu-id="31488-137">Response</span></span>

<span data-ttu-id="31488-138">다음은 응답의 예입니다.</span><span class="sxs-lookup"><span data-stu-id="31488-138">Here is an example of the response.</span></span>


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

## <a name="related-topics"></a><span data-ttu-id="31488-139">관련 항목</span><span class="sxs-lookup"><span data-stu-id="31488-139">Related topics</span></span>

- [<span data-ttu-id="31488-140">위험 기반 위협 & 관리</span><span class="sxs-lookup"><span data-stu-id="31488-140">Risk-based Threat & Vulnerability Management</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/next-gen-threat-and-vuln-mgt)
- [<span data-ttu-id="31488-141">위협 & 소프트웨어 인벤토리</span><span class="sxs-lookup"><span data-stu-id="31488-141">Threat & Vulnerability software inventory</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/tvm-software-inventory)
