---
title: 소프트웨어로 장치 나열
description: 이 소프트웨어가 설치된 장치 목록을 검색합니다.
keywords: api, 그래프 api, 지원되는 api, get, 목록 장치, 장치 목록, 소프트웨어로 장치 목록, 끝점 tvm api용 Microsoft Defender
search.product: eADQiWindows 10XVcnh
ms.prod: w10
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
MS.technology: mde
ms.custom: api
ms.openlocfilehash: 8312818fe06b5a25ae32bf1f9585a51fe8848de6
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/08/2021
ms.locfileid: "52845381"
---
# <a name="list-devices-by-software"></a><span data-ttu-id="79334-104">소프트웨어로 장치 나열</span><span class="sxs-lookup"><span data-stu-id="79334-104">List devices by software</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="79334-105">**적용 사항:** [끝점용 Microsoft Defender](https://go.microsoft.com/fwlink/?linkid=2154037)</span><span class="sxs-lookup"><span data-stu-id="79334-105">**Applies to:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span></span>

- <span data-ttu-id="79334-106">끝점용 Microsoft Defender를 경험하고 싶나요?</span><span class="sxs-lookup"><span data-stu-id="79334-106">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="79334-107">무료 평가판에 등록합니다.</span><span class="sxs-lookup"><span data-stu-id="79334-107">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

[!include[Prerelease information](../../includes/prerelease.md)]

<span data-ttu-id="79334-108">이 소프트웨어가 설치된 장치 참조 목록을 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="79334-108">Retrieve a list of device references that has this software installed.</span></span>

## <a name="permissions"></a><span data-ttu-id="79334-109">사용 권한</span><span class="sxs-lookup"><span data-stu-id="79334-109">Permissions</span></span>
<span data-ttu-id="79334-110">이 API를 호출하려면 다음 권한 중 하나가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="79334-110">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="79334-111">사용 권한을 선택하는 방법을 포함하여 자세한 내용은 [Use Microsoft Defender for Endpoint API](apis-intro.md) for details을 참조합니다.</span><span class="sxs-lookup"><span data-stu-id="79334-111">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md) for details.</span></span>

<span data-ttu-id="79334-112">사용 권한 유형</span><span class="sxs-lookup"><span data-stu-id="79334-112">Permission type</span></span> |   <span data-ttu-id="79334-113">사용 권한</span><span class="sxs-lookup"><span data-stu-id="79334-113">Permission</span></span>  |   <span data-ttu-id="79334-114">사용 권한 표시 이름</span><span class="sxs-lookup"><span data-stu-id="79334-114">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="79334-115">응용 프로그램</span><span class="sxs-lookup"><span data-stu-id="79334-115">Application</span></span> | <span data-ttu-id="79334-116">Software.Read.All</span><span class="sxs-lookup"><span data-stu-id="79334-116">Software.Read.All</span></span> | <span data-ttu-id="79334-117">'위협 및 취약성 관리 소프트웨어 정보 읽기'</span><span class="sxs-lookup"><span data-stu-id="79334-117">'Read Threat and Vulnerability Management Software information'</span></span>
<span data-ttu-id="79334-118">위임(직장 또는 학교 계정)</span><span class="sxs-lookup"><span data-stu-id="79334-118">Delegated (work or school account)</span></span> | <span data-ttu-id="79334-119">Software.Read</span><span class="sxs-lookup"><span data-stu-id="79334-119">Software.Read</span></span> | <span data-ttu-id="79334-120">'위협 및 취약성 관리 소프트웨어 정보 읽기'</span><span class="sxs-lookup"><span data-stu-id="79334-120">'Read Threat and Vulnerability Management Software information'</span></span>

## <a name="http-request"></a><span data-ttu-id="79334-121">HTTP 요청</span><span class="sxs-lookup"><span data-stu-id="79334-121">HTTP request</span></span>
```
GET /api/Software/{Id}/machineReferences 
```

## <a name="request-headers"></a><span data-ttu-id="79334-122">요청 헤더</span><span class="sxs-lookup"><span data-stu-id="79334-122">Request headers</span></span>

| <span data-ttu-id="79334-123">이름</span><span class="sxs-lookup"><span data-stu-id="79334-123">Name</span></span>        | <span data-ttu-id="79334-124">유형</span><span class="sxs-lookup"><span data-stu-id="79334-124">Type</span></span> | <span data-ttu-id="79334-125">설명</span><span class="sxs-lookup"><span data-stu-id="79334-125">Description</span></span>
|:--------------|:-------|:--------------|
| <span data-ttu-id="79334-126">권한 부여</span><span class="sxs-lookup"><span data-stu-id="79334-126">Authorization</span></span> | <span data-ttu-id="79334-127">String</span><span class="sxs-lookup"><span data-stu-id="79334-127">String</span></span> | <span data-ttu-id="79334-128">Bearer {token}. **필수 .**</span><span class="sxs-lookup"><span data-stu-id="79334-128">Bearer {token}.**Required**.</span></span>

## <a name="request-body"></a><span data-ttu-id="79334-129">요청 본문</span><span class="sxs-lookup"><span data-stu-id="79334-129">Request body</span></span>
<span data-ttu-id="79334-130">비어 있음</span><span class="sxs-lookup"><span data-stu-id="79334-130">Empty</span></span>

## <a name="response"></a><span data-ttu-id="79334-131">응답</span><span class="sxs-lookup"><span data-stu-id="79334-131">Response</span></span>
<span data-ttu-id="79334-132">성공하면 이 메서드는 200 OK와 소프트웨어가 본문에 설치된 장치 목록을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="79334-132">If successful, this method returns 200 OK and a list of devices with the software installed in the body.</span></span> 


## <a name="example"></a><span data-ttu-id="79334-133">예시</span><span class="sxs-lookup"><span data-stu-id="79334-133">Example</span></span>

<span data-ttu-id="79334-134">**요청**</span><span class="sxs-lookup"><span data-stu-id="79334-134">**Request**</span></span>

<span data-ttu-id="79334-135">다음은 요청의 예입니다.</span><span class="sxs-lookup"><span data-stu-id="79334-135">Here is an example of the request.</span></span>

```
GET https://api.securitycenter.microsoft.com/api/Software/microsoft-_-edge/machineReferences
```

<span data-ttu-id="79334-136">**응답**</span><span class="sxs-lookup"><span data-stu-id="79334-136">**Response**</span></span>

<span data-ttu-id="79334-137">다음은 응답의 예입니다.</span><span class="sxs-lookup"><span data-stu-id="79334-137">Here is an example of the response.</span></span>

```json

{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#MachineReferences",
    "value": [
        {
            "id": "7c7e1896fa39efb0a32a2cf421d837af1b9bf762",
            "computerDnsName": "dave_desktop",
            "osPlatform": "Windows10",
            "rbacGroupName": "GroupTwo"
        },
        {
            "id": "7d5cc2e7c305e4a0a290392abf6707f9888fda0d",
            "computerDnsName": "jane_PC",
            "osPlatform": "Windows10",
            "rbacGroupName": "GroupTwo"
        }
        ...
    ]
}
```

## <a name="related-topics"></a><span data-ttu-id="79334-138">관련 항목</span><span class="sxs-lookup"><span data-stu-id="79334-138">Related topics</span></span>
- [<span data-ttu-id="79334-139">위험 기반 위협 & 관리</span><span class="sxs-lookup"><span data-stu-id="79334-139">Risk-based Threat & Vulnerability Management</span></span>](/microsoft-365/security/defender-endpoint/next-gen-threat-and-vuln-mgt)
- [<span data-ttu-id="79334-140">위협 & 소프트웨어 인벤토리</span><span class="sxs-lookup"><span data-stu-id="79334-140">Threat & Vulnerability software inventory</span></span>](/microsoft-365/security/defender-endpoint/tvm-software-inventory)
