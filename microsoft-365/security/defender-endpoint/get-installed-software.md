---
title: 설치된 소프트웨어 가져오기
description: 특정 장치 ID와 관련된 설치된 소프트웨어 컬렉션을 검색합니다.
keywords: api, 그래프 api, 지원되는 api, 다운로드, 목록, 파일, 정보, 소프트웨어 인벤토리, 장치당 설치된 소프트웨어, 위협 & 취약성 관리 api, 끝점 tvm api용 Microsoft Defender
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dolmont
author: DulceMontemayor
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: ebd689fd53dd804f857c6bec7a412c27988835d0
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/21/2021
ms.locfileid: "51935116"
---
# <a name="get-installed-software"></a><span data-ttu-id="7aa57-104">설치된 소프트웨어 가져오기</span><span class="sxs-lookup"><span data-stu-id="7aa57-104">Get installed software</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="7aa57-105">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="7aa57-105">**Applies to:**</span></span>
- [<span data-ttu-id="7aa57-106">엔드포인트용 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="7aa57-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="7aa57-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="7aa57-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="7aa57-108">끝점용 Microsoft Defender를 경험하고 싶나요?</span><span class="sxs-lookup"><span data-stu-id="7aa57-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="7aa57-109">무료 평가판에 등록합니다.</span><span class="sxs-lookup"><span data-stu-id="7aa57-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

[!include[Prerelease information](../../includes/prerelease.md)]

<span data-ttu-id="7aa57-110">특정 장치 ID와 관련된 설치된 소프트웨어 컬렉션을 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="7aa57-110">Retrieves a collection of installed software related to a given device ID.</span></span>

## <a name="permissions"></a><span data-ttu-id="7aa57-111">사용 권한</span><span class="sxs-lookup"><span data-stu-id="7aa57-111">Permissions</span></span>
<span data-ttu-id="7aa57-112">이 API를 호출하려면 다음 권한 중 하나가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="7aa57-112">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="7aa57-113">사용 권한을 선택하는 방법을 포함하여 자세한 내용은 [끝점 API에 Microsoft Defender 사용을 참조합니다.](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="7aa57-113">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md)</span></span>

<span data-ttu-id="7aa57-114">사용 권한 유형</span><span class="sxs-lookup"><span data-stu-id="7aa57-114">Permission type</span></span> |   <span data-ttu-id="7aa57-115">사용 권한</span><span class="sxs-lookup"><span data-stu-id="7aa57-115">Permission</span></span>  |   <span data-ttu-id="7aa57-116">사용 권한 표시 이름</span><span class="sxs-lookup"><span data-stu-id="7aa57-116">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="7aa57-117">응용 프로그램</span><span class="sxs-lookup"><span data-stu-id="7aa57-117">Application</span></span> |<span data-ttu-id="7aa57-118">Software.Read.All</span><span class="sxs-lookup"><span data-stu-id="7aa57-118">Software.Read.All</span></span> |    <span data-ttu-id="7aa57-119">'위협 및 취약성 관리 소프트웨어 정보 읽기'</span><span class="sxs-lookup"><span data-stu-id="7aa57-119">'Read Threat and Vulnerability Management Software information'</span></span>
<span data-ttu-id="7aa57-120">위임(직장 또는 학교 계정)</span><span class="sxs-lookup"><span data-stu-id="7aa57-120">Delegated (work or school account)</span></span> | <span data-ttu-id="7aa57-121">Software.Read</span><span class="sxs-lookup"><span data-stu-id="7aa57-121">Software.Read</span></span> |    <span data-ttu-id="7aa57-122">'위협 및 취약성 관리 소프트웨어 정보 읽기'</span><span class="sxs-lookup"><span data-stu-id="7aa57-122">'Read Threat and Vulnerability Management Software information'</span></span>

## <a name="http-request"></a><span data-ttu-id="7aa57-123">HTTP 요청</span><span class="sxs-lookup"><span data-stu-id="7aa57-123">HTTP request</span></span>
```
GET /api/machines/{machineId}/software
```

## <a name="request-headers"></a><span data-ttu-id="7aa57-124">요청 헤더</span><span class="sxs-lookup"><span data-stu-id="7aa57-124">Request headers</span></span>

<span data-ttu-id="7aa57-125">이름</span><span class="sxs-lookup"><span data-stu-id="7aa57-125">Name</span></span> | <span data-ttu-id="7aa57-126">유형</span><span class="sxs-lookup"><span data-stu-id="7aa57-126">Type</span></span> | <span data-ttu-id="7aa57-127">설명</span><span class="sxs-lookup"><span data-stu-id="7aa57-127">Description</span></span>
:---|:---|:---
<span data-ttu-id="7aa57-128">권한 부여</span><span class="sxs-lookup"><span data-stu-id="7aa57-128">Authorization</span></span> | <span data-ttu-id="7aa57-129">문자열</span><span class="sxs-lookup"><span data-stu-id="7aa57-129">String</span></span> | <span data-ttu-id="7aa57-130">Bearer {token}.</span><span class="sxs-lookup"><span data-stu-id="7aa57-130">Bearer {token}.</span></span> <span data-ttu-id="7aa57-131">**필수입니다**.</span><span class="sxs-lookup"><span data-stu-id="7aa57-131">**Required**.</span></span>


## <a name="request-body"></a><span data-ttu-id="7aa57-132">요청 본문</span><span class="sxs-lookup"><span data-stu-id="7aa57-132">Request body</span></span>
<span data-ttu-id="7aa57-133">비어 있음</span><span class="sxs-lookup"><span data-stu-id="7aa57-133">Empty</span></span>

## <a name="response"></a><span data-ttu-id="7aa57-134">응답</span><span class="sxs-lookup"><span data-stu-id="7aa57-134">Response</span></span>
<span data-ttu-id="7aa57-135">성공하면 이 메서드는 본문에 설치된 소프트웨어 정보를 사용하여 200 OK를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="7aa57-135">If successful, this method returns 200 OK with the installed software information in the body.</span></span>


## <a name="example"></a><span data-ttu-id="7aa57-136">예시</span><span class="sxs-lookup"><span data-stu-id="7aa57-136">Example</span></span>

<span data-ttu-id="7aa57-137">**요청**</span><span class="sxs-lookup"><span data-stu-id="7aa57-137">**Request**</span></span>

<span data-ttu-id="7aa57-138">다음은 요청의 예입니다.</span><span class="sxs-lookup"><span data-stu-id="7aa57-138">Here is an example of the request.</span></span>

```http
GET https://api.securitycenter.microsoft.com/api/machines/ac233fa6208e1579620bf44207c4006ed7cc4501/software
```

<span data-ttu-id="7aa57-139">**응답**</span><span class="sxs-lookup"><span data-stu-id="7aa57-139">**Response**</span></span>

<span data-ttu-id="7aa57-140">다음은 응답의 예입니다.</span><span class="sxs-lookup"><span data-stu-id="7aa57-140">Here is an example of the response.</span></span>


```
{
"@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#Software",
"value": [
        {
"id": "microsoft-_-internet_explorer",
"name": "internet_explorer",
"vendor": "microsoft",
"weaknesses": 67,
"publicExploit": true,
"activeAlert": false,
"exposedMachines": 42115,
"impactScore": 46.2037163
        }
    ]
}
```

## <a name="see-also"></a><span data-ttu-id="7aa57-141">참고 항목</span><span class="sxs-lookup"><span data-stu-id="7aa57-141">See also</span></span>

- [<span data-ttu-id="7aa57-142">위험 기반 위협 & 관리</span><span class="sxs-lookup"><span data-stu-id="7aa57-142">Risk-based Threat & Vulnerability Management</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/next-gen-threat-and-vuln-mgt)
- [<span data-ttu-id="7aa57-143">위협 & 소프트웨어 인벤토리</span><span class="sxs-lookup"><span data-stu-id="7aa57-143">Threat & Vulnerability software inventory</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/tvm-software-inventory)
