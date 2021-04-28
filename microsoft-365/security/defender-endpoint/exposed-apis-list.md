---
title: 지원되는 엔드포인트용 Microsoft Defender API
ms.reviewer: ''
description: API 호출을 만들 수 있는 끝점 엔터티에 대해 지원되는 특정 Microsoft Defender에 대해 자세히 알아보습니다.
keywords: api, 지원되는 api, 배우, 경고, 장치, 사용자, 도메인, ip, 파일, 고급 쿼리, 고급 헌팅
search.product: eADQiWindows 10XVcnh
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
ms.openlocfilehash: 656aa26d80db73bfc52511f9dd94e58e771f3ac6
ms.sourcegitcommit: 9063c7a50a1d7dd6d2e1ca44f53d3c26f21f4ae8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/28/2021
ms.locfileid: "52073832"
---
# <a name="supported-microsoft-defender-for-endpoint-apis"></a><span data-ttu-id="09026-104">지원되는 엔드포인트용 Microsoft Defender API</span><span class="sxs-lookup"><span data-stu-id="09026-104">Supported Microsoft Defender for Endpoint APIs</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="09026-105">**적용 사항:** [끝점용 Microsoft Defender](https://go.microsoft.com/fwlink/?linkid=2154037)</span><span class="sxs-lookup"><span data-stu-id="09026-105">**Applies to:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span></span>

- <span data-ttu-id="09026-106">끝점용 Microsoft Defender를 경험하고 싶나요?</span><span class="sxs-lookup"><span data-stu-id="09026-106">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="09026-107">무료 평가판에 등록합니다.</span><span class="sxs-lookup"><span data-stu-id="09026-107">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

## <a name="endpoint-uri-and-versioning"></a><span data-ttu-id="09026-108">끝점 URI 및 버전</span><span class="sxs-lookup"><span data-stu-id="09026-108">Endpoint URI and versioning</span></span>

### <a name="endpoint-uri"></a><span data-ttu-id="09026-109">끝점 URI</span><span class="sxs-lookup"><span data-stu-id="09026-109">Endpoint URI</span></span>

> <span data-ttu-id="09026-110">서비스 기본 URI는 다음입니다. [https://api.securitycenter.microsoft.com](https://api.securitycenter.microsoft.com)</span><span class="sxs-lookup"><span data-stu-id="09026-110">The service base URI is: [https://api.securitycenter.microsoft.com](https://api.securitycenter.microsoft.com)</span></span>
>
> <span data-ttu-id="09026-111">쿼리 기반 OData에는 '/api' prefix가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="09026-111">The queries based OData have the '/api' prefix.</span></span> <span data-ttu-id="09026-112">예를 들어 알림을 얻기 위해 GET 요청을 보낼 수 있습니다. [https://api.securitycenter.microsoft.com/api/alerts](https://api.securitycenter.microsoft.com/api/alerts)</span><span class="sxs-lookup"><span data-stu-id="09026-112">For example, to get Alerts you can send GET request to [https://api.securitycenter.microsoft.com/api/alerts](https://api.securitycenter.microsoft.com/api/alerts)</span></span>

### <a name="versioning"></a><span data-ttu-id="09026-113">버전화</span><span class="sxs-lookup"><span data-stu-id="09026-113">Versioning</span></span>

> <span data-ttu-id="09026-114">API는 버전 관리가 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="09026-114">The API supports versioning.</span></span>
>
> <span data-ttu-id="09026-115">현재 버전은 **V1.0입니다.**</span><span class="sxs-lookup"><span data-stu-id="09026-115">The current version is **V1.0**.</span></span>
>
> <span data-ttu-id="09026-116">특정 버전을 사용 하도록 다음 형식을 사용 `https://api.securitycenter.microsoft.com/api/{Version}` 합니다. .</span><span class="sxs-lookup"><span data-stu-id="09026-116">To use a specific version, use this format: `https://api.securitycenter.microsoft.com/api/{Version}`.</span></span> <span data-ttu-id="09026-117">예: `https://api.securitycenter.microsoft.com/api/v1.0/alerts`</span><span class="sxs-lookup"><span data-stu-id="09026-117">For example: `https://api.securitycenter.microsoft.com/api/v1.0/alerts`</span></span>
>
> <span data-ttu-id="09026-118">버전(예: )을 지정하지 않으면 최신 `https://api.securitycenter.microsoft.com/api/alerts` 버전으로 변경됩니다.</span><span class="sxs-lookup"><span data-stu-id="09026-118">If you don't specify any version (e.g. `https://api.securitycenter.microsoft.com/api/alerts` ) you will get to the latest version.</span></span>

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

<span data-ttu-id="09026-119">API 호출을 실행할 수 있는 지원되는 개별 엔터티 및 HTTP 요청 값, 요청 헤더 및 예상 응답과 같은 세부 정보를 자세히 알아보습니다.</span><span class="sxs-lookup"><span data-stu-id="09026-119">Learn more about the individual supported entities where you can run API calls to and details such as HTTP request values, request headers and expected responses.</span></span>

## <a name="in-this-section"></a><span data-ttu-id="09026-120">이 섹션의 내용</span><span class="sxs-lookup"><span data-stu-id="09026-120">In this section</span></span>

<span data-ttu-id="09026-121">항목</span><span class="sxs-lookup"><span data-stu-id="09026-121">Topic</span></span> | <span data-ttu-id="09026-122">설명</span><span class="sxs-lookup"><span data-stu-id="09026-122">Description</span></span>
:---|:---
[<span data-ttu-id="09026-123">지능형 헌팅</span><span class="sxs-lookup"><span data-stu-id="09026-123">Advanced Hunting</span></span>](run-advanced-query-api.md) | <span data-ttu-id="09026-124">API에서 쿼리를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="09026-124">Run queries from API.</span></span>
[<span data-ttu-id="09026-125">경고 방법 및 속성</span><span class="sxs-lookup"><span data-stu-id="09026-125">Alert methods and properties</span></span>](alerts.md) | <span data-ttu-id="09026-126">경고 다운로드, 경고 만들기, 경고 업데이트 등의 API \- 호출을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="09026-126">Run API calls such as \- get alerts, create alert, update alert and more.</span></span>
[<span data-ttu-id="09026-127">자동화된 조사 방법 및 속성</span><span class="sxs-lookup"><span data-stu-id="09026-127">Automated Investigation methods and properties</span></span>](investigation.md) | <span data-ttu-id="09026-128">조사 컬렉션을 수집하는 등의 API \- 호출을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="09026-128">Run API calls such as \- get collection of Investigation.</span></span>
[<span data-ttu-id="09026-129">도메인 관련 경고 가져오기</span><span class="sxs-lookup"><span data-stu-id="09026-129">Get domain related alerts</span></span>](get-domain-related-alerts.md) | <span data-ttu-id="09026-130">도메인 관련 장치, 도메인 통계 등의 API \- 호출을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="09026-130">Run API calls such as \- get domain-related devices, domain statistics and more.</span></span>
[<span data-ttu-id="09026-131">파일 방법 및 속성</span><span class="sxs-lookup"><span data-stu-id="09026-131">File methods and properties</span></span>](files.md) | <span data-ttu-id="09026-132">파일 정보 다운로드, 파일 관련 경고, 파일 관련 장치 및 파일 통계와 같은 API \- 호출을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="09026-132">Run API calls such as \- get file information, file related alerts, file related devices, and file statistics.</span></span>
[<span data-ttu-id="09026-133">지표 방법 및 속성</span><span class="sxs-lookup"><span data-stu-id="09026-133">Indicators methods and properties</span></span>](ti-indicator.md) | <span data-ttu-id="09026-134">표시기 get, Indicator 만들기, 표시기 삭제 등의 API \- 호출을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="09026-134">Run API call such as \- get Indicators, create Indicator, and delete Indicators.</span></span>
[<span data-ttu-id="09026-135">IP 관련 경고 가져오기</span><span class="sxs-lookup"><span data-stu-id="09026-135">Get IP related alerts</span></span>](get-ip-related-alerts.md) | <span data-ttu-id="09026-136">IP 관련 경고를 수집하고 IP 통계를 수집하는 \- 등의 API 호출을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="09026-136">Run API calls such as \- get IP-related alerts and get IP statistics.</span></span>
[<span data-ttu-id="09026-137">컴퓨터 방법 및 속성</span><span class="sxs-lookup"><span data-stu-id="09026-137">Machine methods and properties</span></span>](machine.md) | <span data-ttu-id="09026-138">장치 검색, ID로 장치 검색, 로그온한 사용자에 대한 정보, 태그 편집 등의 API \- 호출을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="09026-138">Run API calls such as \- get devices, get devices by ID, information about logged on users, edit tags and more.</span></span>
[<span data-ttu-id="09026-139">컴퓨터 작업 방법 및 속성</span><span class="sxs-lookup"><span data-stu-id="09026-139">Machine Action methods and properties</span></span>](machineaction.md) | <span data-ttu-id="09026-140">ISOLATION, 바이러스 백신 검사 실행 등의 API \- 호출을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="09026-140">Run API call such as \- Isolation, Run anti-virus scan and more.</span></span>
[<span data-ttu-id="09026-141">권장 방법 및 속성</span><span class="sxs-lookup"><span data-stu-id="09026-141">Recommendation methods and properties</span></span>](recommendation.md) | <span data-ttu-id="09026-142">ID로 추천 등의 API \- 호출을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="09026-142">Run API calls such as \- get recommendation by ID.</span></span>
[<span data-ttu-id="09026-143">점수 방법 및 속성</span><span class="sxs-lookup"><span data-stu-id="09026-143">Score methods and properties</span></span>](score.md) | <span data-ttu-id="09026-144">노출 점수 얻기 또는 장치 보안 점수 얻기 등의 API \- 호출을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="09026-144">Run API calls such as \- get exposure score or get device secure score.</span></span>
[<span data-ttu-id="09026-145">소프트웨어 방법 및 속성</span><span class="sxs-lookup"><span data-stu-id="09026-145">Software methods and properties</span></span>](software.md) | <span data-ttu-id="09026-146">소프트웨어의 목록 \- 취약점과 같은 API 호출을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="09026-146">Run API calls such as \- list vulnerabilities by software.</span></span>
[<span data-ttu-id="09026-147">사용자 방법</span><span class="sxs-lookup"><span data-stu-id="09026-147">User methods</span></span>](user.md) | <span data-ttu-id="09026-148">사용자 관련 알림 및 사용자 관련 장치와 같은 API \- 호출을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="09026-148">Run API calls such as \- get user-related alerts and user-related devices.</span></span>
[<span data-ttu-id="09026-149">취약성 방법 및 속성</span><span class="sxs-lookup"><span data-stu-id="09026-149">Vulnerability methods and properties</span></span>](vulnerability.md) | <span data-ttu-id="09026-150">취약성으로 목록 장치와 같은 API \- 호출을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="09026-150">Run API calls such as \- list devices by vulnerability.</span></span>

## <a name="see-also"></a><span data-ttu-id="09026-151">참고 항목</span><span class="sxs-lookup"><span data-stu-id="09026-151">See also</span></span>

- [<span data-ttu-id="09026-152">끝점 API용 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="09026-152">Microsoft Defender for Endpoint APIs</span></span>](apis-intro.md)

- [<span data-ttu-id="09026-153">끝점용 Microsoft Defender API 릴리스 정보</span><span class="sxs-lookup"><span data-stu-id="09026-153">Microsoft Defender for Endpoint API release notes</span></span>](api-release-notes.md)
