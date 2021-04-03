---
title: 발견된 취약성 가져오기
description: 특정 장치 ID와 관련된 검색된 취약성 컬렉션을 검색합니다.
keywords: api, 그래프 api, 지원되는 api, 다운로드, 목록, 파일, 정보, 발견된 취약성, 위협 & 취약성 관리 api, mdatp tvm api
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
ms.technology: mde
ms.openlocfilehash: 73b8fe5140ff635791e7d42358024bb7fb4ee926
ms.sourcegitcommit: 6e5c00f84b5201422aed094f2697016407df8fc2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/02/2021
ms.locfileid: "51570330"
---
# <a name="get-discovered-vulnerabilities"></a><span data-ttu-id="8789d-104">발견된 취약성 가져오기</span><span class="sxs-lookup"><span data-stu-id="8789d-104">Get discovered vulnerabilities</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="8789d-105">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="8789d-105">**Applies to:**</span></span>
- <span data-ttu-id="8789d-106">[엔드포인트용 Microsoft Defender](https://go.microsoft.com/fwlink/p/?linkid=2154037) </span><span class="sxs-lookup"><span data-stu-id="8789d-106">[Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)</span></span>
- [<span data-ttu-id="8789d-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="8789d-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="8789d-108">끝점용 Microsoft Defender를 경험하고 싶나요?</span><span class="sxs-lookup"><span data-stu-id="8789d-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="8789d-109">무료 평가판에 등록합니다.</span><span class="sxs-lookup"><span data-stu-id="8789d-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

## <a name="api-description"></a><span data-ttu-id="8789d-110">API 설명</span><span class="sxs-lookup"><span data-stu-id="8789d-110">API description</span></span>
<span data-ttu-id="8789d-111">특정 장치 ID와 관련된 검색된 취약성 컬렉션을 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="8789d-111">Retrieves a collection of discovered vulnerabilities related to a given device ID.</span></span>

## <a name="limitations"></a><span data-ttu-id="8789d-112">제한 사항</span><span class="sxs-lookup"><span data-stu-id="8789d-112">Limitations</span></span>
1. <span data-ttu-id="8789d-113">이 API의 속도 제한은 분당 50통, 시간당 1500통입니다.</span><span class="sxs-lookup"><span data-stu-id="8789d-113">Rate limitations for this API are 50 calls per minute and 1500 calls per hour.</span></span>

## <a name="permissions"></a><span data-ttu-id="8789d-114">사용 권한</span><span class="sxs-lookup"><span data-stu-id="8789d-114">Permissions</span></span>

<span data-ttu-id="8789d-115">이 API를 호출하려면 다음 권한 중 하나가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="8789d-115">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="8789d-116">사용 권한을 선택하는 방법을 포함하여 자세한 내용은 [끝점 API에 Microsoft Defender 사용을 참조합니다.](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="8789d-116">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md)</span></span>

<span data-ttu-id="8789d-117">사용 권한 유형</span><span class="sxs-lookup"><span data-stu-id="8789d-117">Permission type</span></span> | <span data-ttu-id="8789d-118">사용 권한</span><span class="sxs-lookup"><span data-stu-id="8789d-118">Permission</span></span> | <span data-ttu-id="8789d-119">사용 권한 표시 이름</span><span class="sxs-lookup"><span data-stu-id="8789d-119">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="8789d-120">응용 프로그램</span><span class="sxs-lookup"><span data-stu-id="8789d-120">Application</span></span> |<span data-ttu-id="8789d-121">Vulnerability.Read.All</span><span class="sxs-lookup"><span data-stu-id="8789d-121">Vulnerability.Read.All</span></span> | <span data-ttu-id="8789d-122">'위협 및 취약성 관리 취약성 정보 읽기'</span><span class="sxs-lookup"><span data-stu-id="8789d-122">'Read Threat and Vulnerability Management vulnerability information'</span></span>
<span data-ttu-id="8789d-123">위임(직장 또는 학교 계정)</span><span class="sxs-lookup"><span data-stu-id="8789d-123">Delegated (work or school account)</span></span> | <span data-ttu-id="8789d-124">Vulnerability.Read</span><span class="sxs-lookup"><span data-stu-id="8789d-124">Vulnerability.Read</span></span> | <span data-ttu-id="8789d-125">'위협 및 취약성 관리 취약성 정보 읽기'</span><span class="sxs-lookup"><span data-stu-id="8789d-125">'Read Threat and Vulnerability Management vulnerability information'</span></span>

## <a name="http-request"></a><span data-ttu-id="8789d-126">HTTP 요청</span><span class="sxs-lookup"><span data-stu-id="8789d-126">HTTP request</span></span>

```
GET /api/machines/{machineId}/vulnerabilities
```

## <a name="request-headers"></a><span data-ttu-id="8789d-127">요청 헤더</span><span class="sxs-lookup"><span data-stu-id="8789d-127">Request headers</span></span>

<span data-ttu-id="8789d-128">이름</span><span class="sxs-lookup"><span data-stu-id="8789d-128">Name</span></span> | <span data-ttu-id="8789d-129">유형</span><span class="sxs-lookup"><span data-stu-id="8789d-129">Type</span></span> | <span data-ttu-id="8789d-130">설명</span><span class="sxs-lookup"><span data-stu-id="8789d-130">Description</span></span>
:---|:---|:---
<span data-ttu-id="8789d-131">권한 부여</span><span class="sxs-lookup"><span data-stu-id="8789d-131">Authorization</span></span> | <span data-ttu-id="8789d-132">문자열</span><span class="sxs-lookup"><span data-stu-id="8789d-132">String</span></span> | <span data-ttu-id="8789d-133">Bearer {token}.</span><span class="sxs-lookup"><span data-stu-id="8789d-133">Bearer {token}.</span></span> <span data-ttu-id="8789d-134">**필수입니다**.</span><span class="sxs-lookup"><span data-stu-id="8789d-134">**Required**.</span></span>

## <a name="request-body"></a><span data-ttu-id="8789d-135">요청 본문</span><span class="sxs-lookup"><span data-stu-id="8789d-135">Request body</span></span>

<span data-ttu-id="8789d-136">비어 있음</span><span class="sxs-lookup"><span data-stu-id="8789d-136">Empty</span></span>

## <a name="response"></a><span data-ttu-id="8789d-137">응답</span><span class="sxs-lookup"><span data-stu-id="8789d-137">Response</span></span>

<span data-ttu-id="8789d-138">성공하면 이 메서드는 본문에서 발견된 취약성 정보를 사용하여 200 OK를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="8789d-138">If successful, this method returns 200 OK with the discovered vulnerability information in the body.</span></span>

## <a name="example"></a><span data-ttu-id="8789d-139">예제</span><span class="sxs-lookup"><span data-stu-id="8789d-139">Example</span></span>

### <a name="request"></a><span data-ttu-id="8789d-140">요청</span><span class="sxs-lookup"><span data-stu-id="8789d-140">Request</span></span>

<span data-ttu-id="8789d-141">다음은 요청의 예입니다.</span><span class="sxs-lookup"><span data-stu-id="8789d-141">Here is an example of the request.</span></span>

```http
GET https://api.securitycenter.microsoft.com/api/machines/ac233fa6208e1579620bf44207c4006ed7cc4501/vulnerabilities
```

### <a name="response"></a><span data-ttu-id="8789d-142">응답</span><span class="sxs-lookup"><span data-stu-id="8789d-142">Response</span></span>

<span data-ttu-id="8789d-143">다음은 응답의 예입니다.</span><span class="sxs-lookup"><span data-stu-id="8789d-143">Here is an example of the response.</span></span>

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

## <a name="see-also"></a><span data-ttu-id="8789d-144">참고 항목</span><span class="sxs-lookup"><span data-stu-id="8789d-144">See also</span></span>

- [<span data-ttu-id="8789d-145">위험 기반 위협 & 관리</span><span class="sxs-lookup"><span data-stu-id="8789d-145">Risk-based Threat & Vulnerability Management</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/next-gen-threat-and-vuln-mgt)
- [<span data-ttu-id="8789d-146">조직의 취약성</span><span class="sxs-lookup"><span data-stu-id="8789d-146">Vulnerabilities in your organization</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/tvm-weaknesses)
