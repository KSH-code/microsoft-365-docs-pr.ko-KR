---
title: 장치당 소프트웨어 취약점 평가 내보내기
description: API 응답은 장치당 있으며 노출된 장치에 설치된 취약한 소프트웨어와 이러한 소프트웨어 제품의 알려진 취약점을 포함 합니다. 이 표에는 운영 체제 정보, CVE ID 및 취약성 심각도 정보가 포함되어 있습니다.
keywords: api, api, 내보내기 평가, 장치 평가당, 취약성 평가 보고서, 장치 취약점 평가, 장치 취약성 보고서, 보안 구성 평가, 보안 구성 보고서, 소프트웨어 취약점 평가, 소프트웨어 취약성 보고서, 컴퓨터의 취약점 보고서,
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: v-jweston
author: jweston-1
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.custom: api
ms.openlocfilehash: 6243da415c5cc509be33eabffd12516367164bff
ms.sourcegitcommit: bc64d9f619259bd0a94e43a9010aae5cffb4d6c4
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/19/2021
ms.locfileid: "53022873"
---
# <a name="export-software-vulnerabilities-assessment-per-device"></a><span data-ttu-id="29082-105">장치당 소프트웨어 취약점 평가 내보내기</span><span class="sxs-lookup"><span data-stu-id="29082-105">Export software vulnerabilities assessment per device</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="29082-106">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="29082-106">**Applies to:**</span></span>

- [<span data-ttu-id="29082-107">엔드포인트용 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="29082-107">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="29082-108">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="29082-108">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="29082-109">끝점용 Microsoft Defender를 경험하고 싶나요?</span><span class="sxs-lookup"><span data-stu-id="29082-109">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="29082-110">무료 평가판에 등록합니다.</span><span class="sxs-lookup"><span data-stu-id="29082-110">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

>
<span data-ttu-id="29082-111">장치 기준에 따라 알려진 모든 소프트웨어 취약성 및 모든 장치에 대한 세부 정보를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="29082-111">Returns all known software vulnerabilities and their details for all devices, on a per-device basis.</span></span>

<span data-ttu-id="29082-112">다양한 형식의 데이터를 얻기 위해 다른 API 호출이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="29082-112">There are different API calls to get different types of data.</span></span> <span data-ttu-id="29082-113">데이터 양은 매우 크기 때문에 다음 두 가지 방법으로 데이터를 검색할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="29082-113">Because the amount of data can be very large, there are two ways it can be retrieved:</span></span>

1. <span data-ttu-id="29082-114">[소프트웨어 취약성 평가 **JSON 응답 내보내기**](#1-export-software-vulnerabilities-assessment-json-response)  API는 Json 응답으로 조직의 모든 데이터를 끌어 습니다.</span><span class="sxs-lookup"><span data-stu-id="29082-114">[Export software vulnerabilities assessment **JSON response**](#1-export-software-vulnerabilities-assessment-json-response)  The API pulls all data in your organization as Json responses.</span></span> <span data-ttu-id="29082-115">이 방법은 _100 K_ 장치 미만의 소규모 조직에 가장 적합한 방법입니다.</span><span class="sxs-lookup"><span data-stu-id="29082-115">This method is best for _small organizations with less than 100 K devices_.</span></span> <span data-ttu-id="29082-116">응답이 단계적이기 때문에 응답의 odata.nextLink 필드를 사용하여 다음 결과를 \@ 내보일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="29082-116">The response is paginated, so you can use the \@odata.nextLink field from the response to fetch the next results.</span></span>

2. <span data-ttu-id="29082-117">[파일을 통해 소프트웨어 **취약성 평가 내보내기**](#2-export-software-vulnerabilities-assessment-via-files) 이 API 솔루션을 사용하면 더 많은 양의 데이터를 더 빠르고 안정적으로 끌어 올 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="29082-117">[Export software vulnerabilities assessment **via files**](#2-export-software-vulnerabilities-assessment-via-files) This API solution enables pulling larger amounts of data faster and more reliably.</span></span> <span data-ttu-id="29082-118">100 K 장치가 넘는 대규모 조직에서는 Via-files를 권장합니다.</span><span class="sxs-lookup"><span data-stu-id="29082-118">Via-files is recommended for large organizations, with more than 100 K devices.</span></span> <span data-ttu-id="29082-119">이 API는 조직의 모든 데이터를 다운로드 파일로 끌어들입니다.</span><span class="sxs-lookup"><span data-stu-id="29082-119">This API pulls all data in your organization as download files.</span></span> <span data-ttu-id="29082-120">응답에는 응답에서 모든 데이터를 다운로드하는 URL이 Azure 저장소.</span><span class="sxs-lookup"><span data-stu-id="29082-120">The response contains URLs to download all the data from Azure Storage.</span></span> <span data-ttu-id="29082-121">이 API를 사용하면 다음과 같이 모든 데이터를 Azure 저장소 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="29082-121">This API enables you to download all your data from Azure Storage as follows:</span></span>

   - <span data-ttu-id="29082-122">API를 호출하여 모든 조직 데이터와 함께 다운로드 URL 목록을 얻습니다.</span><span class="sxs-lookup"><span data-stu-id="29082-122">Call the API to get a list of download URLs with all your organization data.</span></span>

   - <span data-ttu-id="29082-123">다운로드 URL을 사용하여 모든 파일을 다운로드하고 원하는 데이터를 처리합니다.</span><span class="sxs-lookup"><span data-stu-id="29082-123">Download all the files using the download URLs and process the data as you like.</span></span>

3. <span data-ttu-id="29082-124">[델타 내보내기 소프트웨어 취약성 평가 **JSON 응답**](#3-delta-export-software-vulnerabilities-assessment-json-response)  DeviceId, SoftwareVendor, SoftwareName, SoftwareVersion, CveId 및 EventTimestamp의 모든 고유 조합에 대한 항목이 있는 테이블을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="29082-124">[Delta export software vulnerabilities assessment **JSON response**](#3-delta-export-software-vulnerabilities-assessment-json-response)  Returns a table with an entry for every unique combination of: DeviceId, SoftwareVendor, SoftwareName, SoftwareVersion, CveId, and EventTimestamp.</span></span>
<span data-ttu-id="29082-125">API는 Json 응답으로 조직의 데이터를 끌어 습니다.</span><span class="sxs-lookup"><span data-stu-id="29082-125">The API pulls data in your organization as Json responses.</span></span> <span data-ttu-id="29082-126">응답이 단계적으로 진행되어 응답의 @odata.nextLink 필드를 사용하여 다음 결과를 내보일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="29082-126">The response is paginated, so you can use the @odata.nextLink field from the response to fetch the next results.</span></span> <br><br> <span data-ttu-id="29082-127">장치로 조직의 소프트웨어 취약점 평가에 대한 전체 스냅숏을 얻는 데 사용되는 전체 "소프트웨어 취약점 평가(JSON 응답)"와 달리 델타 내보내기 OData API 호출은 선택한 날짜와 현재 날짜("델타" API 호출) 사이에 수행된 변경 내용만 페치하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="29082-127">Unlike the full "software vulnerabilities assessment (JSON response)" - which is used to obtain an entire snapshot of the software vulnerabilities assessment of your organization by device - the delta export OData API call is used to fetch only the changes that have happened between a selected date and the current date (the “delta” API call).</span></span> <span data-ttu-id="29082-128">매월 많은 양의 데이터를 사용하여 전체 내보내기 대신 신규, 고정 및 업데이트된 취약성에 대한 특정 정보만 얻을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="29082-128">Instead of getting a full export with a large amount of data every time, you’ll only get specific information on new, fixed, and updated vulnerabilities.</span></span> <span data-ttu-id="29082-129">델타 내보내기 JSON 응답 API 호출을 사용하여 "고정된 취약성 수"과 같은 다양한 KPI를 계산할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="29082-129">Delta export JSON response API call can also be used to calculate different KPIs such as “how many vulnerabilities were fixed?”</span></span> <span data-ttu-id="29082-130">또는 "조직에 추가된 새 취약성의 수가 몇 개인가요?"</span><span class="sxs-lookup"><span data-stu-id="29082-130">or “how many new vulnerabilities were added to my organization?”</span></span> <br><br> <span data-ttu-id="29082-131">소프트웨어 취약성에 대한 델타 내보내기 JSON 응답 API 호출은 대상 날짜 범위에 대한 데이터만 반환하기 때문에 전체 _내보내기로 간주되지 않습니다._</span><span class="sxs-lookup"><span data-stu-id="29082-131">Because the Delta export JSON response API call for software vulnerabilities returns data for only a targeted date range, it is not considered a _full export_.</span></span>

<span data-ttu-id="29082-132">_OData_ 또는 파일을 통해 수집되는 데이터는 현재 상태의 현재 스냅숏으로 기록 데이터를 포함하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="29082-132">Data that is collected (using either _OData_ or _via files_) is the current snapshot of the current state, and does not contain historic data.</span></span> <span data-ttu-id="29082-133">기록 데이터를 수집하려면 고객은 데이터를 자체 데이터 저장소에 저장해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="29082-133">In order to collect historic data, customers must save the data in their own data storages.</span></span>

> [!Note]
>
> <span data-ttu-id="29082-134">다른 설명이 없는 한 나열된 \*\*\*\* 모든 내보내기 평가 방법은 전체 내보내기 및 장치(장치당 \*\*\*\* **_참조)입니다._**</span><span class="sxs-lookup"><span data-stu-id="29082-134">Unless indicated otherwise, all export assessment methods listed are **_full export_** and **_by device_** (also referred to as **_per device_**).</span></span>

## <a name="1-export-software-vulnerabilities-assessment-json-response"></a><span data-ttu-id="29082-135">1. 소프트웨어 취약점 평가 내보내기(JSON 응답)</span><span class="sxs-lookup"><span data-stu-id="29082-135">1. Export software vulnerabilities assessment (JSON response)</span></span>

### <a name="11-api-method-description"></a><span data-ttu-id="29082-136">1.1 API 메서드 설명</span><span class="sxs-lookup"><span data-stu-id="29082-136">1.1 API method description</span></span>

<span data-ttu-id="29082-137">이 API 응답에는 장치당 설치된 소프트웨어의 모든 데이터가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="29082-137">This API response contains all the data of installed software per device.</span></span> <span data-ttu-id="29082-138">DeviceId, SoftwareVendor, SoftwareName, SoftwareVersion, CVEID의 모든 고유 조합에 대한 항목이 있는 테이블을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="29082-138">Returns a table with an entry for every unique combination of DeviceId, SoftwareVendor, SoftwareName, SoftwareVersion, CVEID.</span></span>

#### <a name="111-limitations"></a><span data-ttu-id="29082-139">1.1.1 제한 사항</span><span class="sxs-lookup"><span data-stu-id="29082-139">1.1.1 Limitations</span></span>

- <span data-ttu-id="29082-140">최대 페이지 크기는 200,000개입니다.</span><span class="sxs-lookup"><span data-stu-id="29082-140">Maximum page size is 200,000.</span></span>

- <span data-ttu-id="29082-141">이 API에 대한 속도 제한은 분당 30개 호출과 시간당 1,000개 호출입니다.</span><span class="sxs-lookup"><span data-stu-id="29082-141">Rate limitations for this API are 30 calls per minute and 1000 calls per hour.</span></span>

### <a name="12-permissions"></a><span data-ttu-id="29082-142">1.2 사용 권한</span><span class="sxs-lookup"><span data-stu-id="29082-142">1.2 Permissions</span></span>

<span data-ttu-id="29082-143">이 API를 호출하려면 다음 권한 중 하나가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="29082-143">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="29082-144">사용 권한을 선택하는 방법을 포함하여 자세한 내용은 [Use Microsoft Defender for Endpoint API for details을 참조합니다.](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="29082-144">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs for details.](apis-intro.md)</span></span>

<span data-ttu-id="29082-145">사용 권한 유형</span><span class="sxs-lookup"><span data-stu-id="29082-145">Permission type</span></span> | <span data-ttu-id="29082-146">사용 권한</span><span class="sxs-lookup"><span data-stu-id="29082-146">Permission</span></span> | <span data-ttu-id="29082-147">사용 권한 표시 이름</span><span class="sxs-lookup"><span data-stu-id="29082-147">Permission display name</span></span>
---|---|---
<span data-ttu-id="29082-148">응용 프로그램</span><span class="sxs-lookup"><span data-stu-id="29082-148">Application</span></span> | <span data-ttu-id="29082-149">Vulnerability.Read.All</span><span class="sxs-lookup"><span data-stu-id="29082-149">Vulnerability.Read.All</span></span> | <span data-ttu-id="29082-150">\'위협 및 취약성 관리 취약성 정보 읽기\'</span><span class="sxs-lookup"><span data-stu-id="29082-150">\'Read Threat and Vulnerability Management vulnerability information\'</span></span>
<span data-ttu-id="29082-151">위임(직장 또는 학교 계정)</span><span class="sxs-lookup"><span data-stu-id="29082-151">Delegated (work or school account)</span></span> | <span data-ttu-id="29082-152">Vulnerability.Read</span><span class="sxs-lookup"><span data-stu-id="29082-152">Vulnerability.Read</span></span> | <span data-ttu-id="29082-153">\'위협 및 취약성 관리 취약성 정보 읽기\'</span><span class="sxs-lookup"><span data-stu-id="29082-153">\'Read Threat and Vulnerability Management vulnerability information\'</span></span>

### <a name="13-url"></a><span data-ttu-id="29082-154">1.3 URL</span><span class="sxs-lookup"><span data-stu-id="29082-154">1.3 URL</span></span>

```http
GET /api/machines/SoftwareVulnerabilitiesByMachine
```

### <a name="14-parameters"></a><span data-ttu-id="29082-155">1.4 매개 변수</span><span class="sxs-lookup"><span data-stu-id="29082-155">1.4 Parameters</span></span>

- <span data-ttu-id="29082-156">pageSize(기본값 = 50,000) - 응답 결과 수</span><span class="sxs-lookup"><span data-stu-id="29082-156">pageSize (default = 50,000) – number of results in response</span></span>
- <span data-ttu-id="29082-157">$top - 반환할 결과 수입니다(@odata.nextLink를 반환하지 않습니다. 따라서 모든 데이터를 끌어오지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="29082-157">$top – number of results to return (doesn’t return @odata.nextLink and therefore doesn’t pull all the data)</span></span>

### <a name="15-properties"></a><span data-ttu-id="29082-158">1.5 속성</span><span class="sxs-lookup"><span data-stu-id="29082-158">1.5 Properties</span></span>

>[!Note]
>
>- <span data-ttu-id="29082-159">각 레코드는 약 1 KB의 데이터입니다.</span><span class="sxs-lookup"><span data-stu-id="29082-159">Each record is approximately 1 KB of data.</span></span> <span data-ttu-id="29082-160">올바른 pageSize 매개 변수를 선택할 때 이 문제를 고려해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="29082-160">You should take this into account when choosing the correct pageSize parameter for you.</span></span>
>
>- <span data-ttu-id="29082-161">응답에 일부 추가 열이 반환될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="29082-161">Some additional columns might be returned in the response.</span></span> <span data-ttu-id="29082-162">이러한 열은 임시로 제거될 수 있습니다. 문서화한 열만 사용하시기 바랍니다.</span><span class="sxs-lookup"><span data-stu-id="29082-162">These columns are temporary and might be removed, please use only the documented columns.</span></span>
>
>- <span data-ttu-id="29082-163">다음 표에 정의된 속성은 속성 ID에 따라 사전순으로 나열됩니다.</span><span class="sxs-lookup"><span data-stu-id="29082-163">The properties defined in the following table are listed alphabetically, by property ID.</span></span>  <span data-ttu-id="29082-164">이 API를 실행하면 결과 출력이 이 표에 나열된 순서대로 반환되지 않을 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="29082-164">When running this API, the resulting output will not necessarily be returned in the same order listed in this table.</span></span>

<br/>

<span data-ttu-id="29082-165">속성(ID)</span><span class="sxs-lookup"><span data-stu-id="29082-165">Property (ID)</span></span> | <span data-ttu-id="29082-166">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="29082-166">Data type</span></span> | <span data-ttu-id="29082-167">설명</span><span class="sxs-lookup"><span data-stu-id="29082-167">Description</span></span> | <span data-ttu-id="29082-168">반환된 값의 예</span><span class="sxs-lookup"><span data-stu-id="29082-168">Example of a returned value</span></span>
:---|:---|:---|:---
<span data-ttu-id="29082-169">CveId</span><span class="sxs-lookup"><span data-stu-id="29082-169">CveId</span></span> | <span data-ttu-id="29082-170">문자열</span><span class="sxs-lookup"><span data-stu-id="29082-170">string</span></span> | <span data-ttu-id="29082-171">CVE(Common Vulnerabilities and Exposures) 시스템의 보안 취약성에 할당된 고유 식별자입니다.</span><span class="sxs-lookup"><span data-stu-id="29082-171">Unique identifier assigned to the security vulnerability under the Common Vulnerabilities and Exposures (CVE) system.</span></span> | <span data-ttu-id="29082-172">CVE-2020-15992</span><span class="sxs-lookup"><span data-stu-id="29082-172">CVE-2020-15992</span></span>
<span data-ttu-id="29082-173">CvssScore</span><span class="sxs-lookup"><span data-stu-id="29082-173">CvssScore</span></span> | <span data-ttu-id="29082-174">문자열</span><span class="sxs-lookup"><span data-stu-id="29082-174">string</span></span> | <span data-ttu-id="29082-175">CVE의 CVSS 점수입니다.</span><span class="sxs-lookup"><span data-stu-id="29082-175">The CVSS score of the CVE.</span></span> | <span data-ttu-id="29082-176">6.2</span><span class="sxs-lookup"><span data-stu-id="29082-176">6.2</span></span>
<span data-ttu-id="29082-177">DeviceId</span><span class="sxs-lookup"><span data-stu-id="29082-177">DeviceId</span></span> | <span data-ttu-id="29082-178">문자열</span><span class="sxs-lookup"><span data-stu-id="29082-178">string</span></span> | <span data-ttu-id="29082-179">서비스에서 장치의 고유 식별자입니다.</span><span class="sxs-lookup"><span data-stu-id="29082-179">Unique identifier for the device in the service.</span></span> | <span data-ttu-id="29082-180">9eaf3a8b5962e0e6b1af9ec756664a9b823df2d1</span><span class="sxs-lookup"><span data-stu-id="29082-180">9eaf3a8b5962e0e6b1af9ec756664a9b823df2d1</span></span>
<span data-ttu-id="29082-181">장치 이름</span><span class="sxs-lookup"><span data-stu-id="29082-181">DeviceName</span></span> | <span data-ttu-id="29082-182">문자열</span><span class="sxs-lookup"><span data-stu-id="29082-182">string</span></span> | <span data-ttu-id="29082-183">장치의 FQDN(FQDN)입니다.</span><span class="sxs-lookup"><span data-stu-id="29082-183">Fully qualified domain name (FQDN) of the device.</span></span> | <span data-ttu-id="29082-184">johnlaptop.europe.contoso.com</span><span class="sxs-lookup"><span data-stu-id="29082-184">johnlaptop.europe.contoso.com</span></span>
<span data-ttu-id="29082-185">DiskPaths</span><span class="sxs-lookup"><span data-stu-id="29082-185">DiskPaths</span></span>  | <span data-ttu-id="29082-186">배열 \[ 문자열\]</span><span class="sxs-lookup"><span data-stu-id="29082-186">Array\[string\]</span></span> | <span data-ttu-id="29082-187">제품이 장치에 설치되어 있는 디스크 증거입니다.</span><span class="sxs-lookup"><span data-stu-id="29082-187">Disk evidence that the product is installed on the device.</span></span> | <span data-ttu-id="29082-188">[ "C:\Program Files (x86)\Microsoft\Silverlight\Application\silverlight.exe" ]</span><span class="sxs-lookup"><span data-stu-id="29082-188">[ "C:\Program Files (x86)\Microsoft\Silverlight\Application\silverlight.exe" ]</span></span>
<span data-ttu-id="29082-189">ExploitabilityLevel</span><span class="sxs-lookup"><span data-stu-id="29082-189">ExploitabilityLevel</span></span> | <span data-ttu-id="29082-190">문자열</span><span class="sxs-lookup"><span data-stu-id="29082-190">string</span></span> | <span data-ttu-id="29082-191">이 취약성의 악용성 수준(NoExploit, ExploitIsPublic, ExploitIsVerified, ExploitIsInKit)</span><span class="sxs-lookup"><span data-stu-id="29082-191">The exploitability level of this vulnerability (NoExploit, ExploitIsPublic, ExploitIsVerified, ExploitIsInKit)</span></span> | <span data-ttu-id="29082-192">ExploitIsInKit</span><span class="sxs-lookup"><span data-stu-id="29082-192">ExploitIsInKit</span></span>
<span data-ttu-id="29082-193">FirstSeenTimestamp</span><span class="sxs-lookup"><span data-stu-id="29082-193">FirstSeenTimestamp</span></span> | <span data-ttu-id="29082-194">문자열</span><span class="sxs-lookup"><span data-stu-id="29082-194">string</span></span> | <span data-ttu-id="29082-195">이 제품의 CVE가 디바이스에 처음 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="29082-195">First time the CVE of this product was seen on the device.</span></span> | <span data-ttu-id="29082-196">2020-11-03 10:13:34.8476880</span><span class="sxs-lookup"><span data-stu-id="29082-196">2020-11-03 10:13:34.8476880</span></span>
<span data-ttu-id="29082-197">Id</span><span class="sxs-lookup"><span data-stu-id="29082-197">Id</span></span> | <span data-ttu-id="29082-198">문자열</span><span class="sxs-lookup"><span data-stu-id="29082-198">string</span></span> | <span data-ttu-id="29082-199">레코드의 고유 식별자입니다.</span><span class="sxs-lookup"><span data-stu-id="29082-199">Unique identifier for the record.</span></span> | <span data-ttu-id="29082-200">123ABG55_573AG&mnp!</span><span class="sxs-lookup"><span data-stu-id="29082-200">123ABG55_573AG&mnp!</span></span>
<span data-ttu-id="29082-201">LastSeenTimestamp</span><span class="sxs-lookup"><span data-stu-id="29082-201">LastSeenTimestamp</span></span> | <span data-ttu-id="29082-202">문자열</span><span class="sxs-lookup"><span data-stu-id="29082-202">string</span></span> | <span data-ttu-id="29082-203">디바이스에서 CVE를 마지막으로 본 시간입니다.</span><span class="sxs-lookup"><span data-stu-id="29082-203">Last time the CVE was seen on the device.</span></span> | <span data-ttu-id="29082-204">2020-11-03 10:13:34.8476880</span><span class="sxs-lookup"><span data-stu-id="29082-204">2020-11-03 10:13:34.8476880</span></span>
<span data-ttu-id="29082-205">OSPlatform</span><span class="sxs-lookup"><span data-stu-id="29082-205">OSPlatform</span></span> | <span data-ttu-id="29082-206">문자열</span><span class="sxs-lookup"><span data-stu-id="29082-206">string</span></span> | <span data-ttu-id="29082-207">디바이스에서 실행되는 운영 체제의 플랫폼입니다.</span><span class="sxs-lookup"><span data-stu-id="29082-207">Platform of the operating system running on the device.</span></span> <span data-ttu-id="29082-208">이 속성은 Windows 10 7과 같은 동일한 패밀리 내의 변형을 포함하여 특정 운영 Windows 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="29082-208">This property indicates specific operating systems, including variations within the same family, such as Windows 10 and Windows 7.</span></span> <span data-ttu-id="29082-209">자세한 내용은 tvm 지원 운영 체제 및 플랫폼을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="29082-209">See tvm supported operating systems and platforms for details.</span></span> | <span data-ttu-id="29082-210">Windows 10</span><span class="sxs-lookup"><span data-stu-id="29082-210">Windows10</span></span>
<span data-ttu-id="29082-211">RbacGroupName</span><span class="sxs-lookup"><span data-stu-id="29082-211">RbacGroupName</span></span>  | <span data-ttu-id="29082-212">문자열</span><span class="sxs-lookup"><span data-stu-id="29082-212">string</span></span> | <span data-ttu-id="29082-213">RBAC(역할 기반 액세스 제어) 그룹입니다.</span><span class="sxs-lookup"><span data-stu-id="29082-213">The role-based access control (RBAC) group.</span></span> <span data-ttu-id="29082-214">이 장치가 RBAC 그룹에 할당되지 않은 경우 값은 "지정되지 않았습니다."가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="29082-214">If this device is not assigned to any RBAC group, the value will be “Unassigned.”</span></span> <span data-ttu-id="29082-215">조직에 RBAC 그룹이 없는 경우 값은 "없음"이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="29082-215">If the organization doesn’t contain any RBAC groups, the value will be “None.”</span></span> | <span data-ttu-id="29082-216">서버</span><span class="sxs-lookup"><span data-stu-id="29082-216">Servers</span></span>
<span data-ttu-id="29082-217">RecommendationReference</span><span class="sxs-lookup"><span data-stu-id="29082-217">RecommendationReference</span></span> | <span data-ttu-id="29082-218">문자열</span><span class="sxs-lookup"><span data-stu-id="29082-218">string</span></span> | <span data-ttu-id="29082-219">이 소프트웨어와 관련된 권장 ID에 대한 참조입니다.</span><span class="sxs-lookup"><span data-stu-id="29082-219">A reference to the recommendation ID related to this software.</span></span> | <span data-ttu-id="29082-220">va-_-microsoft-_-silverlight</span><span class="sxs-lookup"><span data-stu-id="29082-220">va-_-microsoft-_-silverlight</span></span>
<span data-ttu-id="29082-221">RecommendedSecurityUpdate(선택 사항)</span><span class="sxs-lookup"><span data-stu-id="29082-221">RecommendedSecurityUpdate (optional)</span></span> | <span data-ttu-id="29082-222">문자열</span><span class="sxs-lookup"><span data-stu-id="29082-222">string</span></span> | <span data-ttu-id="29082-223">소프트웨어 공급업체가 취약점을 해결하기 위해 제공한 보안 업데이트의 이름 또는 설명입니다.</span><span class="sxs-lookup"><span data-stu-id="29082-223">Name or description of the security update provided by the software vendor to address the vulnerability.</span></span> | <span data-ttu-id="29082-224">2020년 4월 보안 업데이트</span><span class="sxs-lookup"><span data-stu-id="29082-224">April 2020 Security Updates</span></span>
<span data-ttu-id="29082-225">RecommendedSecurityUpdateId(선택 사항)</span><span class="sxs-lookup"><span data-stu-id="29082-225">RecommendedSecurityUpdateId (optional)</span></span> | <span data-ttu-id="29082-226">문자열</span><span class="sxs-lookup"><span data-stu-id="29082-226">string</span></span> | <span data-ttu-id="29082-227">해당 지침 또는 기술 자료(KB) 문서의 해당 보안 업데이트 또는 식별자 식별자</span><span class="sxs-lookup"><span data-stu-id="29082-227">Identifier of the applicable security updates or identifier for the corresponding guidance or knowledge base (KB) articles</span></span> | <span data-ttu-id="29082-228">4550961</span><span class="sxs-lookup"><span data-stu-id="29082-228">4550961</span></span>
<span data-ttu-id="29082-229">RegistryPaths</span><span class="sxs-lookup"><span data-stu-id="29082-229">RegistryPaths</span></span>  | <span data-ttu-id="29082-230">배열 \[ 문자열\]</span><span class="sxs-lookup"><span data-stu-id="29082-230">Array\[string\]</span></span> | <span data-ttu-id="29082-231">제품이 장치에 설치되어 있는 레지스트리 증거입니다.</span><span class="sxs-lookup"><span data-stu-id="29082-231">Registry evidence that the product is installed in the device.</span></span> | <span data-ttu-id="29082-232">[ "HKEY_LOCAL_MACHINE\SOFTWARE\WOW6432Node\Microsoft\Windows\CurrentVersion\Uninstall\MicrosoftSilverlight" ]</span><span class="sxs-lookup"><span data-stu-id="29082-232">[ "HKEY_LOCAL_MACHINE\SOFTWARE\WOW6432Node\Microsoft\Windows\CurrentVersion\Uninstall\MicrosoftSilverlight" ]</span></span>
<span data-ttu-id="29082-233">SoftwareName</span><span class="sxs-lookup"><span data-stu-id="29082-233">SoftwareName</span></span> | <span data-ttu-id="29082-234">문자열</span><span class="sxs-lookup"><span data-stu-id="29082-234">string</span></span> | <span data-ttu-id="29082-235">소프트웨어 제품의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="29082-235">Name of the software product.</span></span> | <span data-ttu-id="29082-236">chrome</span><span class="sxs-lookup"><span data-stu-id="29082-236">chrome</span></span>
<span data-ttu-id="29082-237">SoftwareVendor</span><span class="sxs-lookup"><span data-stu-id="29082-237">SoftwareVendor</span></span> | <span data-ttu-id="29082-238">문자열</span><span class="sxs-lookup"><span data-stu-id="29082-238">string</span></span> | <span data-ttu-id="29082-239">소프트웨어 공급업체의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="29082-239">Name of the software vendor.</span></span> | <span data-ttu-id="29082-240">google</span><span class="sxs-lookup"><span data-stu-id="29082-240">google</span></span>
<span data-ttu-id="29082-241">SoftwareVersion</span><span class="sxs-lookup"><span data-stu-id="29082-241">SoftwareVersion</span></span> | <span data-ttu-id="29082-242">문자열</span><span class="sxs-lookup"><span data-stu-id="29082-242">string</span></span> | <span data-ttu-id="29082-243">소프트웨어 제품의 버전 번호입니다.</span><span class="sxs-lookup"><span data-stu-id="29082-243">Version number of the software product.</span></span> | <span data-ttu-id="29082-244">81.0.4044.138</span><span class="sxs-lookup"><span data-stu-id="29082-244">81.0.4044.138</span></span>
<span data-ttu-id="29082-245">VulnerabilitySeverityLevel</span><span class="sxs-lookup"><span data-stu-id="29082-245">VulnerabilitySeverityLevel</span></span>  | <span data-ttu-id="29082-246">문자열</span><span class="sxs-lookup"><span data-stu-id="29082-246">string</span></span> | <span data-ttu-id="29082-247">CVSS 점수 및 위협 환경의 영향을 미치는 동적 요인에 따라 보안 취약성에 할당된 심각도 수준입니다.</span><span class="sxs-lookup"><span data-stu-id="29082-247">Severity level assigned to the security vulnerability based on the CVSS score and dynamic factors influenced by the threat landscape.</span></span> | <span data-ttu-id="29082-248">보통</span><span class="sxs-lookup"><span data-stu-id="29082-248">Medium</span></span>

### <a name="16-examples"></a><span data-ttu-id="29082-249">1.6 예제</span><span class="sxs-lookup"><span data-stu-id="29082-249">1.6 Examples</span></span>

#### <a name="161-request-example"></a><span data-ttu-id="29082-250">1.6.1 요청 예제</span><span class="sxs-lookup"><span data-stu-id="29082-250">1.6.1 Request example</span></span>

```http
GET https://api.securitycenter.microsoft.com/api/machines/SoftwareVulnerabilitiesByMachine?pageSize=5
```

#### <a name="162-response-example"></a><span data-ttu-id="29082-251">1.6.2 응답 예제</span><span class="sxs-lookup"><span data-stu-id="29082-251">1.6.2 Response example</span></span>

```json
{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#Collection(microsoft.windowsDefenderATP.api.AssetVulnerability)",
    "value": [
        {
            "id": "00044f612345baf759462dbe6db733b6a9c59ab4_edge_10.0.17763.1637__",
            "deviceId": "00044f612345daf756462bde6bd733b9a9c59ab4",
            "rbacGroupName": "hhh",
            "deviceName": "ComputerPII_18663b45912eed224b2de2f5ea3142726e63f16a.DomainPII_21eeb80d089e79bdfa178eabfa25e8de9acfa346.corp.contoso.com",
            "osPlatform": "Windows10",
            "osVersion": "10.0.17763.1637",
            "osArchitecture": "x64",
            "softwareVendor": "microsoft",
            "softwareName": "edge",
            "softwareVersion": "10.0.17763.1637",
            "cveId": null,
            "vulnerabilitySeverityLevel": null,
            "recommendedSecurityUpdate": null,
            "recommendedSecurityUpdateId": null,
            "recommendedSecurityUpdateUrl": null,
            "diskPaths": [],
            "registryPaths": [],
            "lastSeenTimestamp": "2020-12-30 14:17:26",
            "firstSeenTimestamp": "2020-12-30 11:07:15",
            "exploitabilityLevel": "NoExploit",
            "recommendationReference": "va-_-microsoft-_-edge"
        },
        {
            "id": "00044f912345baf756462bde6db733b9a9c56ad4_.net_framework_4.0.0.0__",
            "deviceId": "00044f912345daf756462bde6db733b6a9c59ad4",
            "rbacGroupName": "hhh",
            "deviceName": "ComputerPII_18663b45912eed224b2be2f5ea3142726e63f16a.DomainPII_21eeb80b086e79bdfa178eabfa25e8de6acfa346.corp.contoso.com",
            "osPlatform": "Windows10",
            "osVersion": "10.0.17763.1637",
            "osArchitecture": "x64",
            "softwareVendor": "microsoft",
            "softwareName": ".net_framework",
            "softwareVersion": "4.0.0.0",
            "cveId": null,
            "vulnerabilitySeverityLevel": null,
            "recommendedSecurityUpdate": null,
            "recommendedSecurityUpdateId": null,
            "recommendedSecurityUpdateUrl": null,
            "diskPaths": [],
            "registryPaths": [
                "SOFTWARE\\Microsoft\\NET Framework Setup\\NDP\\v4.0\\Client\\Install"
            ],
            "lastSeenTimestamp": "2020-12-30 13:18:33",
            "firstSeenTimestamp": "2020-12-30 11:07:15",
            "exploitabilityLevel": "NoExploit",
            "recommendationReference": "va-_-microsoft-_-.net_framework"
        },
        {
            "id": "00044f912345baf756462dbe6db733d6a9c59ab4_system_center_2012_endpoint_protection_4.10.209.0__",
            "deviceId": "00044f912345daf756462bde6db733b6a9c59ab4",
            "rbacGroupName": "hhh",
            "deviceName": "ComputerPII_18663b45912eed224b2be2f5ea3142726e63f16a.DomainPII_21eed80b089e79bdfa178eadfa25e8be6acfa346.corp.contoso.com",
            "osPlatform": "Windows10",
            "osVersion": "10.0.17763.1637",
            "osArchitecture": "x64",
            "softwareVendor": "microsoft",
            "softwareName": "system_center_2012_endpoint_protection",
            "softwareVersion": "4.10.209.0",
            "cveId": null,
            "vulnerabilitySeverityLevel": null,
            "recommendedSecurityUpdate": null,
            "recommendedSecurityUpdateId": null,
            "recommendedSecurityUpdateUrl": null,
            "diskPaths": [],
            "registryPaths": [
                "HKEY_LOCAL_MACHINE\\SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\Uninstall\\Microsoft Security Client"
            ],
            "lastSeenTimestamp": "2020-12-30 14:17:26",
            "firstSeenTimestamp": "2020-12-30 11:07:15",
            "exploitabilityLevel": "NoExploit",
            "recommendationReference": "va-_-microsoft-_-system_center_2012_endpoint_protection"
        },
        {
            "id": "00044f612345bdaf759462dbe6bd733b6a9c59ab4_onedrive_20.245.1206.2__",
            "deviceId": "00044f91234daf759492dbe6bd733b6a9c59ab4",
            "rbacGroupName": "hhh",
            "deviceName": "ComputerPII_189663d45612eed224b2be2f5ea3142729e63f16a.DomainPII_21eed80b086e79bdfa178eadfa25e8de6acfa346.corp.contoso.com",
            "osPlatform": "Windows10",
            "osVersion": "10.0.17763.1637",
            "osArchitecture": "x64",
            "softwareVendor": "microsoft",
            "softwareName": "onedrive",
            "softwareVersion": "20.245.1206.2",
            "cveId": null,
            "vulnerabilitySeverityLevel": null,
            "recommendedSecurityUpdate": null,
            "recommendedSecurityUpdateId": null,
            "recommendedSecurityUpdateUrl": null,
            "diskPaths": [],
            "registryPaths": [
                "HKEY_USERS\\S-1-5-21-2944539346-1310925172-2349113062-1001\\SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\Uninstall\\OneDriveSetup.exe"
            ],
            "lastSeenTimestamp": "2020-12-30 13:18:33",
            "firstSeenTimestamp": "2020-12-30 11:07:15",
            "exploitabilityLevel": "NoExploit",
            "recommendationReference": "va-_-microsoft-_-onedrive"
        },
        {
            "id": "00044f912345daf759462bde6db733b6a9c56ab4_windows_10_10.0.17763.1637__",
            "deviceId": "00044f912345daf756462dbe6db733d6a9c59ab4",
            "rbacGroupName": "hhh",
            "deviceName": "ComputerPII_18663b45912eeb224d2be2f5ea3142729e63f16a.DomainPII_21eeb80d086e79bdfa178eadfa25e8de6acfa346.corp.contoso.com",
            "osPlatform": "Windows10",
            "osVersion": "10.0.17763.1637",
            "osArchitecture": "x64",
            "softwareVendor": "microsoft",
            "softwareName": "windows_10",
            "softwareVersion": "10.0.17763.1637",
            "cveId": null,
            "vulnerabilitySeverityLevel": null,
            "recommendedSecurityUpdate": null,
            "recommendedSecurityUpdateId": null,
            "recommendedSecurityUpdateUrl": null,
            "diskPaths": [],
            "registryPaths": [],
            "lastSeenTimestamp": "2020-12-30 14:17:26",
            "firstSeenTimestamp": "2020-12-30 11:07:15",
            "exploitabilityLevel": "NoExploit",
            "recommendationReference": "va-_-microsoft-_-windows_10"
        }
    ],
    "@odata.nextLink": "https://api.securitycenter.microsoft.com/api/machines/SoftwareVulnerabilitiesByMachine?pagesize=5&$skiptoken=eyJFeHBvcnREZWZpbml0aW9uIjp7IlRpbWVQYXRoIjoiMjAyMS0wMS0xMS8xMTAxLyJ9LCJFeHBvcnRGaWxlSW5kZXgiOjAsIkxpbmVTdG9wcGVkQXQiOjV9"
}
```

## <a name="2-export-software-vulnerabilities-assessment-via-files"></a><span data-ttu-id="29082-252">2. 파일로 소프트웨어 취약점 평가 내보내기</span><span class="sxs-lookup"><span data-stu-id="29082-252">2. Export software vulnerabilities assessment (via files)</span></span>

### <a name="21-api-method-description"></a><span data-ttu-id="29082-253">2.1 API 메서드 설명</span><span class="sxs-lookup"><span data-stu-id="29082-253">2.1 API method description</span></span>

<span data-ttu-id="29082-254">이 API 응답에는 장치당 설치된 소프트웨어의 모든 데이터가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="29082-254">This API response contains all the data of installed software per device.</span></span> <span data-ttu-id="29082-255">DeviceId, SoftwareVendor, SoftwareName, SoftwareVersion, CVEID의 모든 고유 조합에 대한 항목이 있는 테이블을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="29082-255">Returns a table with an entry for every unique combination of DeviceId, SoftwareVendor, SoftwareName, SoftwareVersion, CVEID.</span></span>

#### <a name="212-limitations"></a><span data-ttu-id="29082-256">2.1.2 제한 사항</span><span class="sxs-lookup"><span data-stu-id="29082-256">2.1.2 Limitations</span></span>

<span data-ttu-id="29082-257">이 API의 속도 제한은 분당 5통, 시간당 20통입니다.</span><span class="sxs-lookup"><span data-stu-id="29082-257">Rate limitations for this API are 5 calls per minute and 20 calls per hour.</span></span>

### <a name="22-permissions"></a><span data-ttu-id="29082-258">2.2 사용 권한</span><span class="sxs-lookup"><span data-stu-id="29082-258">2.2 Permissions</span></span>

<span data-ttu-id="29082-259">이 API를 호출하려면 다음 권한 중 하나가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="29082-259">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="29082-260">사용 권한을 선택하는 방법을 포함하여 자세한 내용은 [Use Microsoft Defender for Endpoint API(끝점 API용 Microsoft Defender](apis-intro.md)사용)를 참조합니다.</span><span class="sxs-lookup"><span data-stu-id="29082-260">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs for details](apis-intro.md).</span></span>

<span data-ttu-id="29082-261">사용 권한 유형</span><span class="sxs-lookup"><span data-stu-id="29082-261">Permission type</span></span> | <span data-ttu-id="29082-262">사용 권한</span><span class="sxs-lookup"><span data-stu-id="29082-262">Permission</span></span> | <span data-ttu-id="29082-263">사용 권한 표시 이름</span><span class="sxs-lookup"><span data-stu-id="29082-263">Permission display name</span></span>
---|---|---
<span data-ttu-id="29082-264">응용 프로그램</span><span class="sxs-lookup"><span data-stu-id="29082-264">Application</span></span> | <span data-ttu-id="29082-265">Vulnerability.Read.All</span><span class="sxs-lookup"><span data-stu-id="29082-265">Vulnerability.Read.All</span></span> | <span data-ttu-id="29082-266">\'위협 및 취약성 관리 취약성 정보 읽기\'</span><span class="sxs-lookup"><span data-stu-id="29082-266">\'Read Threat and Vulnerability Management vulnerability information\'</span></span>
<span data-ttu-id="29082-267">위임(직장 또는 학교 계정)</span><span class="sxs-lookup"><span data-stu-id="29082-267">Delegated (work or school account)</span></span> | <span data-ttu-id="29082-268">Vulnerability.Read</span><span class="sxs-lookup"><span data-stu-id="29082-268">Vulnerability.Read</span></span> | <span data-ttu-id="29082-269">\'위협 및 취약성 관리 취약성 정보 읽기\'</span><span class="sxs-lookup"><span data-stu-id="29082-269">\'Read Threat and Vulnerability Management vulnerability information\'</span></span>

### <a name="23-url"></a><span data-ttu-id="29082-270">2.3 URL</span><span class="sxs-lookup"><span data-stu-id="29082-270">2.3 URL</span></span>

```http
GET /api/machines/SoftwareVulnerabilitiesExport
```

### <a name="24-parameters"></a><span data-ttu-id="29082-271">2.4 매개 변수</span><span class="sxs-lookup"><span data-stu-id="29082-271">2.4 Parameters</span></span>

- <span data-ttu-id="29082-272">sasValidHours – 다운로드 URL이 유효한 시간(최대 24시간)</span><span class="sxs-lookup"><span data-stu-id="29082-272">sasValidHours – The number of hours that the download URLs will be valid for (Maximum 24 hours)</span></span>

### <a name="25-properties"></a><span data-ttu-id="29082-273">2.5 속성</span><span class="sxs-lookup"><span data-stu-id="29082-273">2.5 Properties</span></span>

>[!Note]
>
>- <span data-ttu-id="29082-274">파일은 여러 & Json 형식의 gzip 압축 파일 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="29082-274">The files are gzip compressed & in multiline Json format.</span></span>
>
>- <span data-ttu-id="29082-275">다운로드 URL은 3시간 동안만 유효합니다. 그렇지 않으면 매개 변수를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="29082-275">The download URLs are only valid for 3 hours; otherwise you can use the parameter.</span></span>
>
>- <span data-ttu-id="29082-276">데이터의 최대 다운로드 속도를 위해 데이터가 있는 동일한 Azure 지역에서 다운로드하는지 확인하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="29082-276">For maximum download speed of your data, you can make sure you are downloading from the same Azure region that your data resides.</span></span>
>

>[!Note]
>
>- <span data-ttu-id="29082-277">각 레코드는 약 1KB의 데이터입니다.</span><span class="sxs-lookup"><span data-stu-id="29082-277">Each record is approximately 1KB of data.</span></span> <span data-ttu-id="29082-278">올바른 pageSize 매개 변수를 선택할 때 이 문제를 고려해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="29082-278">You should take this into account when choosing the correct pageSize parameter for you.</span></span>
>
>- <span data-ttu-id="29082-279">응답에 일부 추가 열이 반환될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="29082-279">Some additional columns might be returned in the response.</span></span> <span data-ttu-id="29082-280">이러한 열은 임시로 제거될 수 있습니다. 문서화한 열만 사용하시기 바랍니다.</span><span class="sxs-lookup"><span data-stu-id="29082-280">These columns are temporary and might be removed, please use only the documented columns.</span></span>
>

<span data-ttu-id="29082-281">속성(ID)</span><span class="sxs-lookup"><span data-stu-id="29082-281">Property (ID)</span></span> | <span data-ttu-id="29082-282">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="29082-282">Data type</span></span> | <span data-ttu-id="29082-283">설명</span><span class="sxs-lookup"><span data-stu-id="29082-283">Description</span></span> | <span data-ttu-id="29082-284">반환된 값의 예</span><span class="sxs-lookup"><span data-stu-id="29082-284">Example of a returned value</span></span>
:---|:---|:---|:---
<span data-ttu-id="29082-285">파일 내보내기</span><span class="sxs-lookup"><span data-stu-id="29082-285">Export files</span></span> | <span data-ttu-id="29082-286">array \[ string\]</span><span class="sxs-lookup"><span data-stu-id="29082-286">array\[string\]</span></span>  | <span data-ttu-id="29082-287">조직의 현재 스냅숏을 저장하는 파일의 다운로드 URL 목록입니다.</span><span class="sxs-lookup"><span data-stu-id="29082-287">A list of download URLs for files holding the current snapshot of the organization.</span></span> | <span data-ttu-id="29082-288">[  “https://tvmexportstrstgeus.blob.core.windows.net/tvm-export...1”, “https://tvmexportstrstgeus.blob.core.windows.net/tvm-export...2”  ]</span><span class="sxs-lookup"><span data-stu-id="29082-288">[  “https://tvmexportstrstgeus.blob.core.windows.net/tvm-export...1”, “https://tvmexportstrstgeus.blob.core.windows.net/tvm-export...2”  ]</span></span>
<span data-ttu-id="29082-289">GeneratedTime</span><span class="sxs-lookup"><span data-stu-id="29082-289">GeneratedTime</span></span> | <span data-ttu-id="29082-290">문자열</span><span class="sxs-lookup"><span data-stu-id="29082-290">string</span></span> | <span data-ttu-id="29082-291">내보내기 생성 시간입니다.</span><span class="sxs-lookup"><span data-stu-id="29082-291">The time that the export was generated.</span></span> | <span data-ttu-id="29082-292">2021-05-20T08:00:00Z</span><span class="sxs-lookup"><span data-stu-id="29082-292">2021-05-20T08:00:00Z</span></span>

### <a name="26-examples"></a><span data-ttu-id="29082-293">2.6 예제</span><span class="sxs-lookup"><span data-stu-id="29082-293">2.6 Examples</span></span>

#### <a name="261-request-example"></a><span data-ttu-id="29082-294">2.6.1 요청 예제</span><span class="sxs-lookup"><span data-stu-id="29082-294">2.6.1 Request example</span></span>

```http
GET https://api-us.securitycenter.contoso.com/api/machines/SoftwareVulnerabilitiesExport
```

#### <a name="262-response-example"></a><span data-ttu-id="29082-295">2.6.2 응답 예제</span><span class="sxs-lookup"><span data-stu-id="29082-295">2.6.2 Response example</span></span>

```json
{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#microsoft.windowsDefenderATP.api.ExportFilesResponse",
    "exportFiles": [
        "https://tvmexportstrstgeus.blob.core.windows.net/tvm-export/2021-01-11/1101/VaExport/json/OrgId=12345678-195f-4223-9c7a-99fb420fd000/part-00393-bcc26c4f-e531-48db-9892-c93ac5d72d5c.c000.json.gz?sv=2019-12-12&st=2021-01-11T11%3A35%3A13Z&se=2021-01-11T14%3A35%3A13Z&sr=b&sp=r&sig=...",
        "https://tvmexportstrstgeus.blob.core.windows.net/tvm-export/2021-01-11/1101/VaExport/json/OrgId=12345678-195f-4223-9c7a-99fb420fd000/part-00393-bcc26c4f-e531-48db-9892-c93ac5d72d5c.c001.json.gz?sv=2019-12-12&st=2021-01-11T11%3A35%3A13Z&se=2021-01-11T14%3A35%3A13Z&sr=b&sp=r&sig=...",
        "https://tvmexportstrstgeus.blob.core.windows.net/tvm-export/2021-01-11/1101/VaExport/json/OrgId=12345678-195f-4223-9c7a-99fb420fd000/part-00393-bcc26c4f-e531-48db-9892-c93ac5d72d5c.c002.json.gz?sv=2019-12-12&st=2021-01-11T11%3A35%3A13Z&se=2021-01-11T14%3A35%3A13Z&sr=b&sp=r&sig=..."
    ],
    "generatedTime": "2021-01-11T11:01:00Z"
}
```

## <a name="3-delta-export-software-vulnerabilities-assessment-json-response"></a><span data-ttu-id="29082-296">3. 델타 수출 소프트웨어 취약점 평가(JSON 응답)</span><span class="sxs-lookup"><span data-stu-id="29082-296">3. Delta export software vulnerabilities assessment (JSON response)</span></span>

### <a name="31-api-method-description"></a><span data-ttu-id="29082-297">3.1 API 메서드 설명</span><span class="sxs-lookup"><span data-stu-id="29082-297">3.1 API method description</span></span>

<span data-ttu-id="29082-298">DeviceId, SoftwareVendor, SoftwareName, SoftwareVersion, CveId의 모든 고유 조합에 대한 항목이 있는 테이블을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="29082-298">Returns a table with an entry for every unique combination of DeviceId, SoftwareVendor, SoftwareName, SoftwareVersion, CveId.</span></span> <span data-ttu-id="29082-299">API는 Json 응답으로 조직의 데이터를 끌어 습니다.</span><span class="sxs-lookup"><span data-stu-id="29082-299">The API pulls data in your organization as Json responses.</span></span> <span data-ttu-id="29082-300">응답이 단계적으로 진행되어 응답의 @odata.nextLink 필드를 사용하여 다음 결과를 내보일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="29082-300">The response is paginated, so you can use the @odata.nextLink field from the response to fetch the next results.</span></span> <span data-ttu-id="29082-301">장치로 조직의 소프트웨어 취약점 평가에 대한 전체 스냅숏을 얻는 데 사용되는 전체 소프트웨어 취약점 평가(JSON 응답)와 달리 델타 내보내기 JSON 응답 API 호출은 선택한 날짜와 현재 날짜("델타" API 호출) 사이에 수행된 변경 내용만 페치하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="29082-301">Unlike the full software vulnerabilities assessment (JSON response)—which is used to obtain an entire snapshot of the software vulnerabilities assessment of your organization by device—the delta export JSON response API call is used to fetch only the changes that have happened between a selected date and the current date (the “delta” API call).</span></span> <span data-ttu-id="29082-302">매월 많은 양의 데이터를 사용하여 전체 내보내기 대신 신규, 고정 및 업데이트된 취약성에 대한 특정 정보만 얻을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="29082-302">Instead of getting a full export with a large amount of data every time, you’ll only get specific information on new, fixed, and updated vulnerabilities.</span></span> <span data-ttu-id="29082-303">델타 내보내기 JSON 응답 API 호출을 사용하여 "고정된 취약성 수"과 같은 다양한 KPI를 계산할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="29082-303">Delta export JSON response API call can also be used to calculate different KPIs such as “how many vulnerabilities were fixed?”</span></span> <span data-ttu-id="29082-304">또는 "조직에 추가된 새 취약성의 수가 몇 개인가요?"</span><span class="sxs-lookup"><span data-stu-id="29082-304">or “how many new vulnerabilities were added to my organization?”</span></span>

>[!NOTE]
>
><span data-ttu-id="29082-305">적어도 일주일에 한 번씩 장치 API 호출에 의해 전체 내보내기 소프트웨어 취약성 평가를 사용하는 것이 좋습니다. 이러한 추가 내보내기 소프트웨어 취약성은 장치(델타) API 호출에 따라 변경됩니다.</span><span class="sxs-lookup"><span data-stu-id="29082-305">It is highly recommended you use the full export software vulnerabilities assessment by device API call at least once a week, and this additional export software vulnerabilities changes by device (delta) API call all the other days of the week.</span></span>  <span data-ttu-id="29082-306">다른 평가 JSON 응답 API와 달리 "델타 내보내기"는 전체 내보내기되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="29082-306">Unlike the other Assessments JSON response APIs, the “delta export” is not a full export.</span></span> <span data-ttu-id="29082-307">델타 내보내기에는 선택한 날짜와 현재 날짜 사이에 변경된 내용만 포함됩니다("델타" API 호출).</span><span class="sxs-lookup"><span data-stu-id="29082-307">The delta export includes only the changes that have happened between a selected date and the current date (the “delta” API call).</span></span>

#### <a name="311-limitations"></a><span data-ttu-id="29082-308">3.1.1 제한 사항</span><span class="sxs-lookup"><span data-stu-id="29082-308">3.1.1 Limitations</span></span>

- <span data-ttu-id="29082-309">최대 페이지 크기는 200,000개입니다.</span><span class="sxs-lookup"><span data-stu-id="29082-309">Maximum page size is 200,000.</span></span>

- <span data-ttu-id="29082-310">sinceTime 매개 변수의 최대 길이는 14일입니다.</span><span class="sxs-lookup"><span data-stu-id="29082-310">The sinceTime parameter has a maximum of 14 days.</span></span>

- <span data-ttu-id="29082-311">이 API에 대한 속도 제한은 분당 30개 호출과 시간당 1,000개 호출입니다.</span><span class="sxs-lookup"><span data-stu-id="29082-311">Rate limitations for this API are 30 calls per minute and 1000 calls per hour.</span></span>

### <a name="32-permissions"></a><span data-ttu-id="29082-312">3.2 사용 권한</span><span class="sxs-lookup"><span data-stu-id="29082-312">3.2 Permissions</span></span>

<span data-ttu-id="29082-313">이 API를 호출하려면 다음 권한 중 하나가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="29082-313">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="29082-314">사용 권한을 선택하는 방법을 포함하여 자세한 내용은 [Use Microsoft Defender for Endpoint API for details을 참조합니다.](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="29082-314">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs for details.](apis-intro.md)</span></span>

<span data-ttu-id="29082-315">사용 권한 유형</span><span class="sxs-lookup"><span data-stu-id="29082-315">Permission type</span></span> | <span data-ttu-id="29082-316">사용 권한</span><span class="sxs-lookup"><span data-stu-id="29082-316">Permission</span></span> | <span data-ttu-id="29082-317">사용 권한 표시 이름</span><span class="sxs-lookup"><span data-stu-id="29082-317">Permission display name</span></span>
---|---|---
<span data-ttu-id="29082-318">응용 프로그램</span><span class="sxs-lookup"><span data-stu-id="29082-318">Application</span></span> | <span data-ttu-id="29082-319">Vulnerability.Read.All</span><span class="sxs-lookup"><span data-stu-id="29082-319">Vulnerability.Read.All</span></span> | <span data-ttu-id="29082-320">'위협 및 취약성 관리 취약성 정보 읽기'</span><span class="sxs-lookup"><span data-stu-id="29082-320">'Read Threat and Vulnerability Management vulnerability information'</span></span>
<span data-ttu-id="29082-321">위임(직장 또는 학교 계정)</span><span class="sxs-lookup"><span data-stu-id="29082-321">Delegated (work or school account)</span></span> | <span data-ttu-id="29082-322">Vulnerability.Read</span><span class="sxs-lookup"><span data-stu-id="29082-322">Vulnerability.Read</span></span> | <span data-ttu-id="29082-323">'위협 및 취약성 관리 취약성 정보 읽기'</span><span class="sxs-lookup"><span data-stu-id="29082-323">'Read Threat and Vulnerability Management vulnerability information'</span></span>

### <a name="33-url"></a><span data-ttu-id="29082-324">3.3 URL</span><span class="sxs-lookup"><span data-stu-id="29082-324">3.3 URL</span></span>

```http
GET /api/machines/SoftwareVulnerabilityChangesByMachine 
```

### <a name="34-parameters"></a><span data-ttu-id="29082-325">3.4 매개 변수</span><span class="sxs-lookup"><span data-stu-id="29082-325">3.4 Parameters</span></span>

- <span data-ttu-id="29082-326">sinceTime(필수) - 선택한 시간과 현재 사이의 데이터입니다.</span><span class="sxs-lookup"><span data-stu-id="29082-326">sinceTime (required) – The data between a selected time and today.</span></span>
- <span data-ttu-id="29082-327">pageSize(기본값 = 50,000) - 응답 결과 수</span><span class="sxs-lookup"><span data-stu-id="29082-327">pageSize (default = 50,000) – number of results in response</span></span>
- <span data-ttu-id="29082-328">$top - 반환할 결과 수입니다(@odata.nextLink를 반환하지 않습니다. 따라서 모든 데이터를 끌어오지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="29082-328">$top – number of results to return (doesn’t return @odata.nextLink and therefore doesn’t pull all the data)</span></span>

### <a name="35-properties"></a><span data-ttu-id="29082-329">3.5 속성</span><span class="sxs-lookup"><span data-stu-id="29082-329">3.5 Properties</span></span>

<span data-ttu-id="29082-330">반환되는 각 레코드에는 장치 OData API에 대한 전체 내보내기 소프트웨어 취약점 평가의 모든 데이터와 _**EventTimestamp**_ 및 Status의 두 개의 추가 필드가 _**포함되어 있습니다.**_</span><span class="sxs-lookup"><span data-stu-id="29082-330">Each returned record contains all the data from the full export software vulnerabilities assessment by device OData API, plus two additional fields:  _**EventTimestamp**_ and _**Status**_.</span></span>

>[!NOTE]
>- <span data-ttu-id="29082-331">응답에 일부 추가 열이 반환될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="29082-331">Some additional columns might be returned in the response.</span></span> <span data-ttu-id="29082-332">이러한 열은 임시로 제거될 수 있으므로 문서화한 열만 사용하시기 바랍니다.</span><span class="sxs-lookup"><span data-stu-id="29082-332">These columns are temporary and might be removed, so please use only the documented columns.</span></span>
>
>- <span data-ttu-id="29082-333">다음 표에 정의된 속성은 속성 ID에 따라 사전순으로 나열됩니다.</span><span class="sxs-lookup"><span data-stu-id="29082-333">The properties defined in the following table are listed alphabetically, by property ID.</span></span>  <span data-ttu-id="29082-334">이 API를 실행하면 결과 출력이 이 표에 나열된 순서대로 반환되지 않을 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="29082-334">When running this API, the resulting output will not necessarily be returned in the same order listed in this table.</span></span>
<br><br/>

<span data-ttu-id="29082-335">속성(ID)</span><span class="sxs-lookup"><span data-stu-id="29082-335">Property (ID)</span></span> | <span data-ttu-id="29082-336">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="29082-336">Data type</span></span> | <span data-ttu-id="29082-337">설명</span><span class="sxs-lookup"><span data-stu-id="29082-337">Description</span></span> | <span data-ttu-id="29082-338">반환된 값의 예</span><span class="sxs-lookup"><span data-stu-id="29082-338">Example of returned value</span></span>
:---|:---|:---|:---
<span data-ttu-id="29082-339">CveId</span><span class="sxs-lookup"><span data-stu-id="29082-339">CveId</span></span> | <span data-ttu-id="29082-340">문자열</span><span class="sxs-lookup"><span data-stu-id="29082-340">string</span></span> | <span data-ttu-id="29082-341">CVE(Common Vulnerabilities and Exposures) 시스템의 보안 취약성에 할당된 고유 식별자입니다.</span><span class="sxs-lookup"><span data-stu-id="29082-341">Unique identifier assigned to the security vulnerability under the Common Vulnerabilities and Exposures (CVE) system.</span></span> | <span data-ttu-id="29082-342">CVE-2020-15992</span><span class="sxs-lookup"><span data-stu-id="29082-342">CVE-2020-15992</span></span>  
<span data-ttu-id="29082-343">CvssScore</span><span class="sxs-lookup"><span data-stu-id="29082-343">CvssScore</span></span> | <span data-ttu-id="29082-344">문자열</span><span class="sxs-lookup"><span data-stu-id="29082-344">string</span></span> | <span data-ttu-id="29082-345">CVE의 CVSS 점수입니다.</span><span class="sxs-lookup"><span data-stu-id="29082-345">The CVSS score of the CVE.</span></span> | <span data-ttu-id="29082-346">6.2</span><span class="sxs-lookup"><span data-stu-id="29082-346">6.2</span></span>  
<span data-ttu-id="29082-347">DeviceId</span><span class="sxs-lookup"><span data-stu-id="29082-347">DeviceId</span></span> | <span data-ttu-id="29082-348">문자열</span><span class="sxs-lookup"><span data-stu-id="29082-348">string</span></span> | <span data-ttu-id="29082-349">서비스에서 장치의 고유 식별자입니다.</span><span class="sxs-lookup"><span data-stu-id="29082-349">Unique identifier for the device in the service.</span></span> | <span data-ttu-id="29082-350">9eaf3a8b5962e0e6b1af9ec756664a9b823df2d1</span><span class="sxs-lookup"><span data-stu-id="29082-350">9eaf3a8b5962e0e6b1af9ec756664a9b823df2d1</span></span>  
<span data-ttu-id="29082-351">장치 이름</span><span class="sxs-lookup"><span data-stu-id="29082-351">DeviceName</span></span> | <span data-ttu-id="29082-352">문자열</span><span class="sxs-lookup"><span data-stu-id="29082-352">string</span></span> | <span data-ttu-id="29082-353">장치의 FQDN(FQDN)입니다.</span><span class="sxs-lookup"><span data-stu-id="29082-353">Fully qualified domain name (FQDN) of the device.</span></span> | <span data-ttu-id="29082-354">johnlaptop.europe.contoso.com</span><span class="sxs-lookup"><span data-stu-id="29082-354">johnlaptop.europe.contoso.com</span></span>  
<span data-ttu-id="29082-355">DiskPaths</span><span class="sxs-lookup"><span data-stu-id="29082-355">DiskPaths</span></span> | <span data-ttu-id="29082-356">Array[string]</span><span class="sxs-lookup"><span data-stu-id="29082-356">Array[string]</span></span> | <span data-ttu-id="29082-357">제품이 장치에 설치되어 있는 디스크 증거입니다.</span><span class="sxs-lookup"><span data-stu-id="29082-357">Disk evidence that the product is installed on the device.</span></span> | <span data-ttu-id="29082-358">[ "C:\Program Files (x86)\Microsoft\Silverlight\Application\silverlight.exe" ]</span><span class="sxs-lookup"><span data-stu-id="29082-358">[ "C:\Program Files (x86)\Microsoft\Silverlight\Application\silverlight.exe" ]</span></span>  
<span data-ttu-id="29082-359">EventTimestamp</span><span class="sxs-lookup"><span data-stu-id="29082-359">EventTimestamp</span></span> | <span data-ttu-id="29082-360">String</span><span class="sxs-lookup"><span data-stu-id="29082-360">String</span></span> | <span data-ttu-id="29082-361">이 델타 이벤트를 찾은 시간입니다.</span><span class="sxs-lookup"><span data-stu-id="29082-361">The time this delta event was found.</span></span> | <span data-ttu-id="29082-362">2021-01-11T11:06:08.291Z</span><span class="sxs-lookup"><span data-stu-id="29082-362">2021-01-11T11:06:08.291Z</span></span>
<span data-ttu-id="29082-363">ExploitabilityLevel</span><span class="sxs-lookup"><span data-stu-id="29082-363">ExploitabilityLevel</span></span> | <span data-ttu-id="29082-364">문자열</span><span class="sxs-lookup"><span data-stu-id="29082-364">string</span></span> | <span data-ttu-id="29082-365">이 취약성의 악용성 수준(NoExploit, ExploitIsPublic, ExploitIsVerified, ExploitIsInKit)</span><span class="sxs-lookup"><span data-stu-id="29082-365">The exploitability level of this vulnerability (NoExploit, ExploitIsPublic, ExploitIsVerified, ExploitIsInKit)</span></span> | <span data-ttu-id="29082-366">ExploitIsInKit</span><span class="sxs-lookup"><span data-stu-id="29082-366">ExploitIsInKit</span></span>  
<span data-ttu-id="29082-367">FirstSeenTimestamp</span><span class="sxs-lookup"><span data-stu-id="29082-367">FirstSeenTimestamp</span></span> | <span data-ttu-id="29082-368">문자열</span><span class="sxs-lookup"><span data-stu-id="29082-368">string</span></span> | <span data-ttu-id="29082-369">이 제품의 CVE가 디바이스에 처음 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="29082-369">First time the CVE of this product was seen on the device.</span></span> | <span data-ttu-id="29082-370">2020-11-03 10:13:34.8476880</span><span class="sxs-lookup"><span data-stu-id="29082-370">2020-11-03 10:13:34.8476880</span></span>  
<span data-ttu-id="29082-371">Id</span><span class="sxs-lookup"><span data-stu-id="29082-371">Id</span></span> | <span data-ttu-id="29082-372">문자열</span><span class="sxs-lookup"><span data-stu-id="29082-372">string</span></span> | <span data-ttu-id="29082-373">레코드의 고유 식별자입니다.</span><span class="sxs-lookup"><span data-stu-id="29082-373">Unique identifier for the record.</span></span> | <span data-ttu-id="29082-374">123ABG55_573AG&mnp!</span><span class="sxs-lookup"><span data-stu-id="29082-374">123ABG55_573AG&mnp!</span></span>  
<span data-ttu-id="29082-375">LastSeenTimestamp</span><span class="sxs-lookup"><span data-stu-id="29082-375">LastSeenTimestamp</span></span> | <span data-ttu-id="29082-376">문자열</span><span class="sxs-lookup"><span data-stu-id="29082-376">string</span></span> | <span data-ttu-id="29082-377">디바이스에서 CVE를 마지막으로 본 시간입니다.</span><span class="sxs-lookup"><span data-stu-id="29082-377">Last time the CVE was seen on the device.</span></span> | <span data-ttu-id="29082-378">2020-11-03 10:13:34.8476880</span><span class="sxs-lookup"><span data-stu-id="29082-378">2020-11-03 10:13:34.8476880</span></span>  
<span data-ttu-id="29082-379">OSPlatform</span><span class="sxs-lookup"><span data-stu-id="29082-379">OSPlatform</span></span> | <span data-ttu-id="29082-380">문자열</span><span class="sxs-lookup"><span data-stu-id="29082-380">string</span></span> | <span data-ttu-id="29082-381">디바이스에서 실행되는 운영 체제의 플랫폼입니다.</span><span class="sxs-lookup"><span data-stu-id="29082-381">Platform of the operating system running on the device.</span></span> <span data-ttu-id="29082-382">이는 Windows 10 및 Windows 7과 같이 동일한 제품군 내의 변형을 포함하여 특정 운영 체제를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="29082-382">This indicates specific operating systems, including variations within the same family, such as Windows 10 and Windows 7.</span></span> <span data-ttu-id="29082-383">자세한 내용은 tvm 지원 운영 체제 및 플랫폼을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="29082-383">See tvm supported operating systems and platforms for details.</span></span> | <span data-ttu-id="29082-384">Windows 10</span><span class="sxs-lookup"><span data-stu-id="29082-384">Windows10</span></span>  
<span data-ttu-id="29082-385">RbacGroupName</span><span class="sxs-lookup"><span data-stu-id="29082-385">RbacGroupName</span></span> | <span data-ttu-id="29082-386">문자열</span><span class="sxs-lookup"><span data-stu-id="29082-386">string</span></span> | <span data-ttu-id="29082-387">RBAC(역할 기반 액세스 제어) 그룹입니다.</span><span class="sxs-lookup"><span data-stu-id="29082-387">The role-based access control (RBAC) group.</span></span> <span data-ttu-id="29082-388">이 장치가 RBAC 그룹에 할당되지 않은 경우 값은 "지정되지 않았습니다."가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="29082-388">If this device is not assigned to any RBAC group, the value will be “Unassigned.”</span></span> <span data-ttu-id="29082-389">조직에 RBAC 그룹이 없는 경우 값은 "없음"이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="29082-389">If the organization doesn’t contain any RBAC groups, the value will be “None.”</span></span> | <span data-ttu-id="29082-390">서버</span><span class="sxs-lookup"><span data-stu-id="29082-390">Servers</span></span>  
<span data-ttu-id="29082-391">RecommendationReference</span><span class="sxs-lookup"><span data-stu-id="29082-391">RecommendationReference</span></span> | <span data-ttu-id="29082-392">문자열</span><span class="sxs-lookup"><span data-stu-id="29082-392">string</span></span> | <span data-ttu-id="29082-393">이 소프트웨어와 관련된 권장 ID에 대한 참조입니다.</span><span class="sxs-lookup"><span data-stu-id="29082-393">A reference to the recommendation ID related to this software.</span></span> | <span data-ttu-id="29082-394">va-microsoft--silverlight</span><span class="sxs-lookup"><span data-stu-id="29082-394">va--microsoft--silverlight</span></span>  
<span data-ttu-id="29082-395">RecommendedSecurityUpdate</span><span class="sxs-lookup"><span data-stu-id="29082-395">RecommendedSecurityUpdate</span></span>  | <span data-ttu-id="29082-396">문자열</span><span class="sxs-lookup"><span data-stu-id="29082-396">string</span></span> | <span data-ttu-id="29082-397">소프트웨어 공급업체가 취약점을 해결하기 위해 제공한 보안 업데이트의 이름 또는 설명입니다.</span><span class="sxs-lookup"><span data-stu-id="29082-397">Name or description of the security update provided by the software vendor to address the vulnerability.</span></span> | <span data-ttu-id="29082-398">2020년 4월 보안 업데이트</span><span class="sxs-lookup"><span data-stu-id="29082-398">April 2020 Security Updates</span></span>  
<span data-ttu-id="29082-399">RecommendedSecurityUpdateId</span><span class="sxs-lookup"><span data-stu-id="29082-399">RecommendedSecurityUpdateId</span></span>  | <span data-ttu-id="29082-400">문자열</span><span class="sxs-lookup"><span data-stu-id="29082-400">string</span></span> | <span data-ttu-id="29082-401">해당 지침 또는 기술 자료(KB) 문서의 해당 보안 업데이트 또는 식별자 식별자</span><span class="sxs-lookup"><span data-stu-id="29082-401">Identifier of the applicable security updates or identifier for the corresponding guidance or knowledge base (KB) articles</span></span> | <span data-ttu-id="29082-402">4550961</span><span class="sxs-lookup"><span data-stu-id="29082-402">4550961</span></span>  
<span data-ttu-id="29082-403">RegistryPaths</span><span class="sxs-lookup"><span data-stu-id="29082-403">RegistryPaths</span></span>  | <span data-ttu-id="29082-404">Array[string]</span><span class="sxs-lookup"><span data-stu-id="29082-404">Array[string]</span></span> | <span data-ttu-id="29082-405">제품이 장치에 설치되어 있는 레지스트리 증거입니다.</span><span class="sxs-lookup"><span data-stu-id="29082-405">Registry evidence that the product is installed in the device.</span></span> | <span data-ttu-id="29082-406">[ "HKEY_LOCAL_MACHINE\SOFTWARE\WOW6432Node\Microsoft\Windows\CurrentVersion\Uninstall\Google Chrome" ]</span><span class="sxs-lookup"><span data-stu-id="29082-406">[ "HKEY_LOCAL_MACHINE\SOFTWARE\WOW6432Node\Microsoft\Windows\CurrentVersion\Uninstall\Google Chrome" ]</span></span>  
<span data-ttu-id="29082-407">SoftwareName</span><span class="sxs-lookup"><span data-stu-id="29082-407">SoftwareName</span></span> | <span data-ttu-id="29082-408">문자열</span><span class="sxs-lookup"><span data-stu-id="29082-408">string</span></span> | <span data-ttu-id="29082-409">소프트웨어 제품의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="29082-409">Name of the software product.</span></span> | <span data-ttu-id="29082-410">chrome</span><span class="sxs-lookup"><span data-stu-id="29082-410">chrome</span></span>  
<span data-ttu-id="29082-411">SoftwareVendor</span><span class="sxs-lookup"><span data-stu-id="29082-411">SoftwareVendor</span></span> | <span data-ttu-id="29082-412">문자열</span><span class="sxs-lookup"><span data-stu-id="29082-412">string</span></span> | <span data-ttu-id="29082-413">소프트웨어 공급업체의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="29082-413">Name of the software vendor.</span></span> | <span data-ttu-id="29082-414">google</span><span class="sxs-lookup"><span data-stu-id="29082-414">google</span></span>  
<span data-ttu-id="29082-415">SoftwareVersion</span><span class="sxs-lookup"><span data-stu-id="29082-415">SoftwareVersion</span></span> | <span data-ttu-id="29082-416">문자열</span><span class="sxs-lookup"><span data-stu-id="29082-416">string</span></span> | <span data-ttu-id="29082-417">소프트웨어 제품의 버전 번호입니다.</span><span class="sxs-lookup"><span data-stu-id="29082-417">Version number of the software product.</span></span> | <span data-ttu-id="29082-418">81.0.4044.138</span><span class="sxs-lookup"><span data-stu-id="29082-418">81.0.4044.138</span></span>  
<span data-ttu-id="29082-419">상태</span><span class="sxs-lookup"><span data-stu-id="29082-419">Status</span></span> | <span data-ttu-id="29082-420">String</span><span class="sxs-lookup"><span data-stu-id="29082-420">String</span></span> | <span data-ttu-id="29082-421">**새로 추가**   (장치에 도입된 새로운 취약성의 경우)  (1) **수정되었습니다(이** 취약점이 장치에 더 이상 존재하지 않는 경우, 즉   수정된 것입니다).</span><span class="sxs-lookup"><span data-stu-id="29082-421">**New** (for a new vulnerability introduced on a device)  (1) **Fixed** (if this vulnerability doesn’t exist anymore on the device, which means it was remediated).</span></span> <span data-ttu-id="29082-422">(2)  **업데이트되었습니다.**   (장치의 취약점이 변경된 경우).</span><span class="sxs-lookup"><span data-stu-id="29082-422">(2) **Updated** (if a vulnerability on a device has changed.</span></span> <span data-ttu-id="29082-423">가능한 변경 내용은 CVSS 점수, 악용 가능성 수준, 심각도 수준, DiskPaths, RegistryPaths, RecommendedSecurityUpdate입니다.</span><span class="sxs-lookup"><span data-stu-id="29082-423">The possible changes are: CVSS score, exploitability level, severity level, DiskPaths, RegistryPaths, RecommendedSecurityUpdate).</span></span> | <span data-ttu-id="29082-424">고정</span><span class="sxs-lookup"><span data-stu-id="29082-424">Fixed</span></span>
<span data-ttu-id="29082-425">VulnerabilitySeverityLevel</span><span class="sxs-lookup"><span data-stu-id="29082-425">VulnerabilitySeverityLevel</span></span> | <span data-ttu-id="29082-426">문자열</span><span class="sxs-lookup"><span data-stu-id="29082-426">string</span></span> | <span data-ttu-id="29082-427">CVSS 점수 및 위협 환경의 영향을 미치는 동적 요인에 따라 보안 취약성에 할당된 심각도 수준입니다.</span><span class="sxs-lookup"><span data-stu-id="29082-427">Severity level assigned to the security vulnerability based on the CVSS score and dynamic factors influenced by the threat landscape.</span></span> | <span data-ttu-id="29082-428">보통</span><span class="sxs-lookup"><span data-stu-id="29082-428">Medium</span></span>  

#### <a name="clarifications"></a><span data-ttu-id="29082-429">설명</span><span class="sxs-lookup"><span data-stu-id="29082-429">Clarifications</span></span>

- <span data-ttu-id="29082-430">소프트웨어가 버전 1.0에서 버전 2.0으로 업데이트된 경우 두 버전이 모두 CVE-A에 노출되면 2개의 개별 이벤트를 받게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="29082-430">If the software was updated from version 1.0 to version 2.0, and both versions are exposed to CVE-A, you will receive 2 separate events:</span></span>  
   1. <span data-ttu-id="29082-431">Fixed – 버전 1.0의 CVE-A가 수정되었습니다.</span><span class="sxs-lookup"><span data-stu-id="29082-431">Fixed – CVE-A on version 1.0 was fixed</span></span>  
   1. <span data-ttu-id="29082-432">신규 – 버전 2.0의 CVE-A가 추가되었습니다.</span><span class="sxs-lookup"><span data-stu-id="29082-432">New – CVE-A on version 2.0 was added</span></span>

- <span data-ttu-id="29082-433">버전 1.0이 있는 소프트웨어에서 특정 시간(예: 1월 10일)에 특정 취약성(예: CVE-A)이 처음 발견된 경우 며칠 후에 동일한 CVE-A에 노출된 버전 2.0으로 소프트웨어가 업데이트된 경우 다음 두 개의 분리된 이벤트를 받게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="29082-433">If a specific vulnerability (for example, CVE-A) was first seen at a specific time (for example, January 10) on software with version 1.0, and a few days later that software was updated to version 2.0 which also exposed to the same CVE-A, you will receive these two separated events:</span></span>  
   1. <span data-ttu-id="29082-434">Fixed – CVE-X, FirstSeenTimestamp January 10, version 1,0.</span><span class="sxs-lookup"><span data-stu-id="29082-434">Fixed – CVE-X, FirstSeenTimestamp January 10, version 1,0.</span></span>  
   1. <span data-ttu-id="29082-435">신규 – CVE-X, FirstSeenTimestamp 1월 10일 버전 2.0.</span><span class="sxs-lookup"><span data-stu-id="29082-435">New – CVE-X, FirstSeenTimestamp January 10, version 2.0.</span></span>

### <a name="36-examples"></a><span data-ttu-id="29082-436">3.6 예제</span><span class="sxs-lookup"><span data-stu-id="29082-436">3.6 Examples</span></span>

#### <a name="361-request-example"></a><span data-ttu-id="29082-437">3.6.1 요청 예제</span><span class="sxs-lookup"><span data-stu-id="29082-437">3.6.1 Request example</span></span>

```http
GET https://api.securitycenter.microsoft.com/api/machines/SoftwareVulnerabilityChangesByMachine?pageSize=5&sinceTime=2021-05-19T18%3A35%3A49.924Z
```

#### <a name="362-response-example"></a><span data-ttu-id="29082-438">3.6.2 응답 예제</span><span class="sxs-lookup"><span data-stu-id="29082-438">3.6.2 Response example</span></span>

```json
{ 
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#Collection(microsoft.windowsDefenderATP.api.DeltaAssetVulnerability)", 
    "value": [ 
        { 
            "id": "008198251234544f7dfa715e278d4cec0c16c171_chrome_87.0.4280.88__", 
            "deviceId": "008198251234544f7dfa715e278b4cec0c19c171",  
            "rbacGroupName": "hhh", 
            "deviceName": "ComputerPII_1c8fee370690ca24b6a0d3f34d193b0424943a8b8.DomainPII_0dc1aee0fa366d175e514bd91a9e7a5b2b07ee8e.corp.contoso.com", 
            "osPlatform": "Windows10", 
            "osVersion": "10.0.19042.685", 
            "osArchitecture": "x64", 
            "softwareVendor": "google", 
            "softwareName": "chrome", 
            "softwareVersion": "87.0.4280.88", 
            "cveId": null, 
            "vulnerabilitySeverityLevel": null, 
            "recommendedSecurityUpdate": null, 
            "recommendedSecurityUpdateId": null, 
            "recommendedSecurityUpdateUrl": null, 
            "diskPaths": [ 
                "C:\\Program Files (x86)\\Google\\Chrome\\Application\\chrome.exe" 
            ], 
            "registryPaths": [ 
                "HKEY_LOCAL_MACHINE\\SOFTWARE\\WOW6432Node\\Microsoft\\Windows\\CurrentVersion\\Uninstall\\Google Chrome" 
            ], 
            "lastSeenTimestamp": "2021-01-04 00:29:42", 
            "firstSeenTimestamp": "2020-11-06 03:12:44", 
            "exploitabilityLevel": "NoExploit", 
            "recommendationReference": "va-_-google-_-chrome", 
            "status": "Fixed", 
            "eventTimestamp": "2021-01-11T11:06:08.291Z" 
        }, 
        { 
            "id": "00e59c61234533860738ecf488eec8abf296e41e_onedrive_20.64.329.3__", 
            "deviceId": "00e56c91234533860738ecf488eec8abf296e41e",  
            "rbacGroupName": "hhh", 
            "deviceName": "ComputerPII_82c13a8ad8cf3dbaf7bf34fada9fa3aebc124116.DomainPII_21eeb80d086e79dbfa178eadfa25e8de9acfa346.corp.contoso.com", 
            "osPlatform": "Windows10", 
            "osVersion": "10.0.18363.1256", 
            "osArchitecture": "x64", 
            "softwareVendor": "microsoft", 
            "softwareName": "onedrive", 
            "softwareVersion": "20.64.329.3", 
            "cveId": null, 
            "vulnerabilitySeverityLevel": null, 
            "recommendedSecurityUpdate": null, 
            "recommendedSecurityUpdateId": null, 
            "recommendedSecurityUpdateUrl": null, 
            "diskPaths": [], 
            "registryPaths": [ 
                "HKEY_USERS\\S-1-5-21-2127521184-1604012920-1887927527-24918864\\SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\Uninstall\\OneDriveSetup.exe" 
            ], 
            "lastSeenTimestamp": "2020-12-11 19:49:48", 
            "firstSeenTimestamp": "2020-12-07 18:25:47", 
            "exploitabilityLevel": "NoExploit", 
            "recommendationReference": "va-_-microsoft-_-onedrive", 
            "status": "Fixed", 
            "eventTimestamp": "2021-01-11T11:06:08.291Z" 
        }, 
        { 
            "id": "01aa8c73095bb12345918663f3f94ce322107d24_firefox_83.0.0.0_CVE-2020-26971_", 
            "deviceId": "01aa8c73065bb12345918693f3f94ce322107d24", 
            "rbacGroupName": "hhh", 
            "deviceName": "ComputerPII_42684eb981bea2d670027e7ad2caafd3f2b381a3.DomainPII_21eed80b086e76dbfa178eabfa25e8de9acfa346.corp.contoso.com", 
            "osPlatform": "Windows10", 
            "osVersion": "10.0.19042.685", 
            "osArchitecture": "x64", 
            "softwareVendor": "mozilla", 
            "softwareName": "firefox", 
            "softwareVersion": "83.0.0.0", 
            "cveId": "CVE-2020-26971", 
            "vulnerabilitySeverityLevel": "High", 
            "recommendedSecurityUpdate": "193220", 
            "recommendedSecurityUpdateId": null, 
            "recommendedSecurityUpdateUrl": null, 
            "diskPaths": [ 
                "C:\\Program Files (x86)\\Mozilla Firefox\\firefox.exe" 
            ], 
            "registryPaths": [ 
                "HKEY_LOCAL_MACHINE\\SOFTWARE\\WOW6432Node\\Microsoft\\Windows\\CurrentVersion\\Uninstall\\Mozilla Firefox 83.0 (x86 en-US)" 
            ], 
            "lastSeenTimestamp": "2021-01-05 17:04:30", 
            "firstSeenTimestamp": "2020-05-06 12:42:19", 
            "exploitabilityLevel": "NoExploit", 
            "recommendationReference": "va-_-mozilla-_-firefox", 
            "status": "Fixed", 
            "eventTimestamp": "2021-01-11T11:06:08.291Z" 
        }, 
        { 
            "id": "026f0fcb12345fbd2decd1a339702131422d362e_project_16.0.13701.20000__", 
            "deviceId": "029f0fcb13245fbd2decd1a336702131422d392e", 
            "rbacGroupName": "hhh", 
            "deviceName": "ComputerPII_a5706750acba75f15d69cd17f4a7fcd268d6422c.DomainPII_f290e982685f7e8eee168b4332e0ae5d2a069cd6.corp.contoso.com", 
            "osPlatform": "Windows10", 
            "osVersion": "10.0.19042.685", 
            "osArchitecture": "x64", 
            "softwareVendor": "microsoft", 
            "softwareName": "project", 
            "softwareVersion": "16.0.13701.20000", 
            "cveId": null, 
            "vulnerabilitySeverityLevel": null, 
            "recommendedSecurityUpdate": null, 
            "recommendedSecurityUpdateId": null, 
            "recommendedSecurityUpdateUrl": null, 
            "diskPaths": [], 
            "registryPaths": [ 
                "HKEY_LOCAL_MACHINE\\SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\Uninstall\\ProjectProRetail - en-us" 
            ], 
            "lastSeenTimestamp": "2021-01-03 23:38:03", 
            "firstSeenTimestamp": "2019-08-01 22:56:12", 
            "exploitabilityLevel": "NoExploit", 
            "recommendationReference": "va-_-microsoft-_-project", 
            "status": "Fixed", 
            "eventTimestamp": "2021-01-11T11:06:08.291Z" 
        }, 
        { 
            "id": "038df381234510b357ac19d0113ef622e4e212b3_chrome_81.0.4044.138_CVE-2020-16011_", 
            "deviceId": "038df381234510d357ac19b0113ef922e4e212b3",  
            "rbacGroupName": "hhh", 
            "deviceName": "ComputerPII_365f5c0bb7202c163937dad3d017969b2d760eb4.DomainPII_29596a43a2ef2bbfa00f6a16c0cb1d108bc63e32.DomainPII_3c5fefd2e6fda2f36257359404f6c1092aa6d4b8.net", 
            "osPlatform": "Windows10", 
            "osVersion": "10.0.18363.1256", 
            "osArchitecture": "x64", 
            "softwareVendor": "google", 
            "softwareName": "chrome", 
            "softwareVersion": "81.0.4044.138", 
            "cveId": "CVE-2020-16011", 
            "vulnerabilitySeverityLevel": "High", 
            "recommendedSecurityUpdate": "ADV 200002", 
            "recommendedSecurityUpdateId": null, 
            "recommendedSecurityUpdateUrl": null, 
            "diskPaths": [ 
                "C:\\Program Files (x86)\\Google\\Chrome\\Application\\chrome.exe" 
            ], 
            "registryPaths": [ 
                "HKEY_LOCAL_MACHINE\\SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\Uninstall\\{C4EBFDFD-0C55-3E5F-A919-E3C54949024A}" 
            ], 
            "lastSeenTimestamp": "2020-12-10 22:45:41", 
            "firstSeenTimestamp": "2020-07-26 02:13:43", 
            "exploitabilityLevel": "NoExploit", 
            "recommendationReference": "va-_-google-_-chrome", 
            "status": "Fixed", 
            "eventTimestamp": "2021-01-11T11:06:08.291Z" 
        } 
    ], 
    "@odata.nextLink": "https://wpatdadi-eus-stg.cloudapp.net/api/machines/SoftwareVulnerabilitiesTimeline?sincetime=2021-01-11&pagesize=5&$skiptoken=eyJFeHBvcnREZWZpbml0aW9uIjp7IlRpbWVQYXRoIjoiMjAyMS0wMS0xMS8xMTAxLyJ9LCJFeHBvcnRGaWxlSW5kZXgiOjAsIkxpbmVTdG9wcGVkQXQiOjV9" 
} 
```

## <a name="see-also"></a><span data-ttu-id="29082-439">참고 항목</span><span class="sxs-lookup"><span data-stu-id="29082-439">See also</span></span>

- [<span data-ttu-id="29082-440">장치당 평가 방법 및 속성 내보내기</span><span class="sxs-lookup"><span data-stu-id="29082-440">Export assessment methods and properties per device</span></span>](get-assessment-methods-properties.md)

- [<span data-ttu-id="29082-441">장치당 보안 구성 평가 내보내기</span><span class="sxs-lookup"><span data-stu-id="29082-441">Export secure configuration assessment per device</span></span>](get-assessment-secure-config.md)

- [<span data-ttu-id="29082-442">장치당 소프트웨어 인벤토리 평가 내보내기</span><span class="sxs-lookup"><span data-stu-id="29082-442">Export software inventory assessment per device</span></span>](get-assessment-software-inventory.md)

<span data-ttu-id="29082-443">기타 관련</span><span class="sxs-lookup"><span data-stu-id="29082-443">Other related</span></span>

- [<span data-ttu-id="29082-444">위험 기반 위협 & 취약성 관리</span><span class="sxs-lookup"><span data-stu-id="29082-444">Risk-based threat & vulnerability management</span></span>](next-gen-threat-and-vuln-mgt.md)

- [<span data-ttu-id="29082-445">조직의 취약성</span><span class="sxs-lookup"><span data-stu-id="29082-445">Vulnerabilities in your organization</span></span>](tvm-weaknesses.md)
