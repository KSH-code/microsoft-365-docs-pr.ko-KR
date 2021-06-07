---
title: 발견된 취약성 가져오기
description: 특정 장치 ID와 관련된 검색된 취약성 컬렉션을 검색합니다.
keywords: api, 그래프 api, 지원되는 api, 다운로드, 목록, 파일, 정보, 발견된 취약성, 위협 & 취약성 관리 api, 끝점 tvm api용 Microsoft Defender
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
author: dansimp
ms.author: dansimp
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
MS.technology: mde
ms.custom: api
ms.openlocfilehash: ac7a9ef932f2640bbc5325f0154c0ceb48ae3018
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/04/2021
ms.locfileid: "52772296"
---
# <a name="get-discovered-vulnerabilities"></a><span data-ttu-id="3e5c3-104">발견된 취약성 가져오기</span><span class="sxs-lookup"><span data-stu-id="3e5c3-104">Get discovered vulnerabilities</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="3e5c3-105">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="3e5c3-105">**Applies to:**</span></span>
- [<span data-ttu-id="3e5c3-106">엔드포인트용 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="3e5c3-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="3e5c3-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="3e5c3-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="3e5c3-108">끝점용 Microsoft Defender를 경험하고 싶나요?</span><span class="sxs-lookup"><span data-stu-id="3e5c3-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="3e5c3-109">무료 평가판에 등록합니다.</span><span class="sxs-lookup"><span data-stu-id="3e5c3-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

## <a name="api-description"></a><span data-ttu-id="3e5c3-110">API 설명</span><span class="sxs-lookup"><span data-stu-id="3e5c3-110">API description</span></span>
<span data-ttu-id="3e5c3-111">특정 장치 ID와 관련된 검색된 취약성 컬렉션을 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="3e5c3-111">Retrieves a collection of discovered vulnerabilities related to a given device ID.</span></span>

## <a name="limitations"></a><span data-ttu-id="3e5c3-112">제한 사항</span><span class="sxs-lookup"><span data-stu-id="3e5c3-112">Limitations</span></span>
1. <span data-ttu-id="3e5c3-113">이 API의 속도 제한은 분당 50통, 시간당 1500통입니다.</span><span class="sxs-lookup"><span data-stu-id="3e5c3-113">Rate limitations for this API are 50 calls per minute and 1500 calls per hour.</span></span>

## <a name="permissions"></a><span data-ttu-id="3e5c3-114">사용 권한</span><span class="sxs-lookup"><span data-stu-id="3e5c3-114">Permissions</span></span>

<span data-ttu-id="3e5c3-115">이 API를 호출하려면 다음 권한 중 하나가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="3e5c3-115">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="3e5c3-116">사용 권한을 선택하는 방법을 포함하여 자세한 내용은 [끝점 API에 Microsoft Defender 사용을 참조합니다.](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="3e5c3-116">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md)</span></span>

<span data-ttu-id="3e5c3-117">사용 권한 유형</span><span class="sxs-lookup"><span data-stu-id="3e5c3-117">Permission type</span></span> | <span data-ttu-id="3e5c3-118">사용 권한</span><span class="sxs-lookup"><span data-stu-id="3e5c3-118">Permission</span></span> | <span data-ttu-id="3e5c3-119">사용 권한 표시 이름</span><span class="sxs-lookup"><span data-stu-id="3e5c3-119">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="3e5c3-120">응용 프로그램</span><span class="sxs-lookup"><span data-stu-id="3e5c3-120">Application</span></span> |<span data-ttu-id="3e5c3-121">Vulnerability.Read.All</span><span class="sxs-lookup"><span data-stu-id="3e5c3-121">Vulnerability.Read.All</span></span> | <span data-ttu-id="3e5c3-122">'위협 및 취약성 관리 취약성 정보 읽기'</span><span class="sxs-lookup"><span data-stu-id="3e5c3-122">'Read Threat and Vulnerability Management vulnerability information'</span></span>
<span data-ttu-id="3e5c3-123">위임(직장 또는 학교 계정)</span><span class="sxs-lookup"><span data-stu-id="3e5c3-123">Delegated (work or school account)</span></span> | <span data-ttu-id="3e5c3-124">Vulnerability.Read</span><span class="sxs-lookup"><span data-stu-id="3e5c3-124">Vulnerability.Read</span></span> | <span data-ttu-id="3e5c3-125">'위협 및 취약성 관리 취약성 정보 읽기'</span><span class="sxs-lookup"><span data-stu-id="3e5c3-125">'Read Threat and Vulnerability Management vulnerability information'</span></span>

## <a name="http-request"></a><span data-ttu-id="3e5c3-126">HTTP 요청</span><span class="sxs-lookup"><span data-stu-id="3e5c3-126">HTTP request</span></span>

```
GET /api/machines/{machineId}/vulnerabilities
```

## <a name="request-headers"></a><span data-ttu-id="3e5c3-127">요청 헤더</span><span class="sxs-lookup"><span data-stu-id="3e5c3-127">Request headers</span></span>

<span data-ttu-id="3e5c3-128">이름</span><span class="sxs-lookup"><span data-stu-id="3e5c3-128">Name</span></span> | <span data-ttu-id="3e5c3-129">유형</span><span class="sxs-lookup"><span data-stu-id="3e5c3-129">Type</span></span> | <span data-ttu-id="3e5c3-130">설명</span><span class="sxs-lookup"><span data-stu-id="3e5c3-130">Description</span></span>
:---|:---|:---
<span data-ttu-id="3e5c3-131">권한 부여</span><span class="sxs-lookup"><span data-stu-id="3e5c3-131">Authorization</span></span> | <span data-ttu-id="3e5c3-132">String</span><span class="sxs-lookup"><span data-stu-id="3e5c3-132">String</span></span> | <span data-ttu-id="3e5c3-133">Bearer {token}.</span><span class="sxs-lookup"><span data-stu-id="3e5c3-133">Bearer {token}.</span></span> <span data-ttu-id="3e5c3-134">**필수입니다**.</span><span class="sxs-lookup"><span data-stu-id="3e5c3-134">**Required**.</span></span>

## <a name="request-body"></a><span data-ttu-id="3e5c3-135">요청 본문</span><span class="sxs-lookup"><span data-stu-id="3e5c3-135">Request body</span></span>

<span data-ttu-id="3e5c3-136">비어 있음</span><span class="sxs-lookup"><span data-stu-id="3e5c3-136">Empty</span></span>

## <a name="response"></a><span data-ttu-id="3e5c3-137">응답</span><span class="sxs-lookup"><span data-stu-id="3e5c3-137">Response</span></span>

<span data-ttu-id="3e5c3-138">성공하면 이 메서드는 본문에서 발견된 취약성 정보를 사용하여 200 OK를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="3e5c3-138">If successful, this method returns 200 OK with the discovered vulnerability information in the body.</span></span>

## <a name="example"></a><span data-ttu-id="3e5c3-139">예시</span><span class="sxs-lookup"><span data-stu-id="3e5c3-139">Example</span></span>

### <a name="request"></a><span data-ttu-id="3e5c3-140">요청</span><span class="sxs-lookup"><span data-stu-id="3e5c3-140">Request</span></span>

<span data-ttu-id="3e5c3-141">다음은 요청의 예입니다.</span><span class="sxs-lookup"><span data-stu-id="3e5c3-141">Here is an example of the request.</span></span>

```http
GET https://api.securitycenter.microsoft.com/api/machines/ac233fa6208e1579620bf44207c4006ed7cc4501/vulnerabilities
```

### <a name="response"></a><span data-ttu-id="3e5c3-142">응답</span><span class="sxs-lookup"><span data-stu-id="3e5c3-142">Response</span></span>

<span data-ttu-id="3e5c3-143">다음은 응답의 예입니다.</span><span class="sxs-lookup"><span data-stu-id="3e5c3-143">Here is an example of the response.</span></span>

```json
{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#Collection(Analytics.Contracts.PublicAPI.PublicVulnerabilityDto)",
    "value": [
        {
            "id": "CVE-2019-1348",
            "name": "CVE-2019-1348",
            "description": "Git could allow a remote attacker to bypass security restrictions, caused by a flaw in the --export-marks option of git fast-import. By persuading a victim to import specially-crafted content, an attacker could exploit this vulnerability to overwrite arbitrary paths.",
            "severity": "Medium",
            "cvssV3": 4.3,
            "exposedMachines": 1,
            "publishedOn": "2019-12-13T00:00:00Z",
            "updatedOn": "2019-12-13T00:00:00Z",
            "publicExploit": false,
            "exploitVerified": false,
            "exploitInKit": false,
            "exploitTypes": [],
            "exploitUris": []
        }
}
```

## <a name="see-also"></a><span data-ttu-id="3e5c3-144">참고 항목</span><span class="sxs-lookup"><span data-stu-id="3e5c3-144">See also</span></span>

- [<span data-ttu-id="3e5c3-145">위험 기반 위협 & 관리</span><span class="sxs-lookup"><span data-stu-id="3e5c3-145">Risk-based Threat & Vulnerability Management</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/next-gen-threat-and-vuln-mgt)
- [<span data-ttu-id="3e5c3-146">조직의 취약성</span><span class="sxs-lookup"><span data-stu-id="3e5c3-146">Vulnerabilities in your organization</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/tvm-weaknesses)
