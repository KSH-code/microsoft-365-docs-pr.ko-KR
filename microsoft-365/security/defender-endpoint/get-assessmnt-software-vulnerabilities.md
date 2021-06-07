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
ms.openlocfilehash: 951f78ba361a12e404a5cce2071f931eab30c43f
ms.sourcegitcommit: 83df0be7144c9c5d606f70b4efa65369e86693d2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/05/2021
ms.locfileid: "52778357"
---
# <a name="export-software-vulnerabilities-assessment-per-device"></a><span data-ttu-id="f5910-105">장치당 소프트웨어 취약점 평가 내보내기</span><span class="sxs-lookup"><span data-stu-id="f5910-105">Export software vulnerabilities assessment per device</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="f5910-106">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="f5910-106">**Applies to:**</span></span>

- [<span data-ttu-id="f5910-107">엔드포인트용 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="f5910-107">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="f5910-108">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="f5910-108">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="f5910-109">끝점용 Microsoft Defender를 경험하고 싶나요?</span><span class="sxs-lookup"><span data-stu-id="f5910-109">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="f5910-110">무료 평가판에 등록합니다.</span><span class="sxs-lookup"><span data-stu-id="f5910-110">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

[!include[Prerelease information](../../includes/prerelease.md)]
>
>
<span data-ttu-id="f5910-111">장치 기준에 따라 알려진 모든 소프트웨어 취약성 및 모든 장치에 대한 세부 정보를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="f5910-111">Returns all known software vulnerabilities and their details for all devices, on a per-device basis.</span></span>

<span data-ttu-id="f5910-112">다양한 형식의 데이터를 얻기 위해 다른 API 호출이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f5910-112">There are different API calls to get different types of data.</span></span> <span data-ttu-id="f5910-113">데이터 양은 매우 크기 때문에 다음 두 가지 방법으로 데이터를 검색할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f5910-113">Because the amount of data can be very large, there are two ways it can be retrieved:</span></span>

- <span data-ttu-id="f5910-114">[소프트웨어 취약점 평가 OData 내보내기](#1-export-software-vulnerabilities-assessment-odata)  API는 OData 프로토콜에 따라 조직의 모든 데이터를 Json 응답으로 끌어들입니다.</span><span class="sxs-lookup"><span data-stu-id="f5910-114">[Export software vulnerabilities assessment OData](#1-export-software-vulnerabilities-assessment-odata)  The API pulls all data in your organization as Json responses, following the OData protocol.</span></span> <span data-ttu-id="f5910-115">이 방법은 _100 K_ 장치 미만의 소규모 조직에 가장 적합한 방법입니다.</span><span class="sxs-lookup"><span data-stu-id="f5910-115">This method is best for _small organizations with less than 100 K devices_.</span></span> <span data-ttu-id="f5910-116">응답이 단계적이기 때문에 응답의 odata.nextLink 필드를 사용하여 다음 결과를 \@ 내보일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f5910-116">The response is paginated, so you can use the \@odata.nextLink field from the response to fetch the next results.</span></span>

- <span data-ttu-id="f5910-117">[파일을 통해 소프트웨어 취약성 평가 내보내기](#2-export-software-vulnerabilities-assessment-via-files) 이 API 솔루션을 사용하면 더 많은 양의 데이터를 더 빠르고 안정적으로 끌어 올 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f5910-117">[Export software vulnerabilities assessment via files](#2-export-software-vulnerabilities-assessment-via-files) This API solution enables pulling larger amounts of data faster and more reliably.</span></span> <span data-ttu-id="f5910-118">따라서 100 K 장치가 넘는 대규모 조직에 권장됩니다.</span><span class="sxs-lookup"><span data-stu-id="f5910-118">Therefore, it is recommended for large organizations, with more than 100 K devices.</span></span> <span data-ttu-id="f5910-119">이 API는 조직의 모든 데이터를 다운로드 파일로 끌어들입니다.</span><span class="sxs-lookup"><span data-stu-id="f5910-119">This API pulls all data in your organization as download files.</span></span> <span data-ttu-id="f5910-120">응답에는 응답에서 모든 데이터를 다운로드하는 URL이 Azure Storage.</span><span class="sxs-lookup"><span data-stu-id="f5910-120">The response contains URLs to download all the data from Azure Storage.</span></span> <span data-ttu-id="f5910-121">이 API를 사용하면 다음과 같이 모든 데이터를 Azure Storage 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f5910-121">This API enables you to download all your data from Azure Storage as follows:</span></span>

  - <span data-ttu-id="f5910-122">API를 호출하여 모든 조직 데이터와 함께 다운로드 URL 목록을 얻습니다.</span><span class="sxs-lookup"><span data-stu-id="f5910-122">Call the API to get a list of download URLs with all your organization data.</span></span>

  - <span data-ttu-id="f5910-123">다운로드 URL을 사용하여 모든 파일을 다운로드하고 원하는 데이터를 처리합니다.</span><span class="sxs-lookup"><span data-stu-id="f5910-123">Download all the files using the download URLs and process the data as you like.</span></span>

<span data-ttu-id="f5910-124">_OData_ 또는 파일을 통해 수집되는 데이터는 현재 상태의 현재 스냅숏으로 기록 데이터를 포함하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="f5910-124">Data that is collected (using either _OData_ or _via files_) is the current snapshot of the current state, and does not contain historic data.</span></span> <span data-ttu-id="f5910-125">기록 데이터를 수집하려면 고객은 데이터를 자체 데이터 저장소에 저장해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f5910-125">In order to collect historic data, customers must save the data in their own data storages.</span></span>

> [!Note]
>
> <span data-ttu-id="f5910-126">다른 설명이 없는 한 나열된 \*\*\*\* 모든 내보내기 평가 방법은 전체 내보내기 및 장치(장치당 \*\*\*\* **_참조)입니다._**</span><span class="sxs-lookup"><span data-stu-id="f5910-126">Unless indicated otherwise, all export assessment methods listed are **_full export_** and **_by device_** (also referred to as **_per device_**).</span></span>

## <a name="1-export-software-vulnerabilities-assessment-odata"></a><span data-ttu-id="f5910-127">1. OData(소프트웨어 취약점 평가) 내보내기</span><span class="sxs-lookup"><span data-stu-id="f5910-127">1. Export software vulnerabilities assessment (OData)</span></span>

### <a name="11-api-method-description"></a><span data-ttu-id="f5910-128">1.1 API 메서드 설명</span><span class="sxs-lookup"><span data-stu-id="f5910-128">1.1 API method description</span></span>

<span data-ttu-id="f5910-129">이 API 응답에는 장치당 설치된 소프트웨어의 모든 데이터가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f5910-129">This API response contains all the data of installed software per device.</span></span> <span data-ttu-id="f5910-130">DeviceId, SoftwareVendor, SoftwareName, SoftwareVersion, CVEID의 모든 고유 조합에 대한 항목이 있는 테이블을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="f5910-130">Returns a table with an entry for every unique combination of DeviceId, SoftwareVendor, SoftwareName, SoftwareVersion, CVEID.</span></span>

#### <a name="limitations"></a><span data-ttu-id="f5910-131">제한 사항</span><span class="sxs-lookup"><span data-stu-id="f5910-131">Limitations</span></span>

>- <span data-ttu-id="f5910-132">최대 페이지 크기는 200,000개입니다.</span><span class="sxs-lookup"><span data-stu-id="f5910-132">Maximum page size is 200,000.</span></span>
>
>- <span data-ttu-id="f5910-133">이 API에 대한 속도 제한은 분당 30개 호출과 시간당 1,000개 호출입니다.</span><span class="sxs-lookup"><span data-stu-id="f5910-133">Rate limitations for this API are 30 calls per minute and 1000 calls per hour.</span></span>

### <a name="12-permissions"></a><span data-ttu-id="f5910-134">1.2 사용 권한</span><span class="sxs-lookup"><span data-stu-id="f5910-134">1.2 Permissions</span></span>

<span data-ttu-id="f5910-135">이 API를 호출하려면 다음 권한 중 하나가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="f5910-135">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="f5910-136">사용 권한을 선택하는 방법을 포함하여 자세한 내용은 [Use Microsoft Defender for Endpoint API for details을 참조합니다.](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="f5910-136">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs for details.](apis-intro.md)</span></span>

<span data-ttu-id="f5910-137">사용 권한 유형</span><span class="sxs-lookup"><span data-stu-id="f5910-137">Permission type</span></span> | <span data-ttu-id="f5910-138">사용 권한</span><span class="sxs-lookup"><span data-stu-id="f5910-138">Permission</span></span> | <span data-ttu-id="f5910-139">사용 권한 표시 이름</span><span class="sxs-lookup"><span data-stu-id="f5910-139">Permission display name</span></span>
---|---|---
<span data-ttu-id="f5910-140">응용 프로그램</span><span class="sxs-lookup"><span data-stu-id="f5910-140">Application</span></span> | <span data-ttu-id="f5910-141">Vulnerability.Read.All</span><span class="sxs-lookup"><span data-stu-id="f5910-141">Vulnerability.Read.All</span></span> | <span data-ttu-id="f5910-142">\'위협 및 취약성 관리 취약성 정보 읽기\'</span><span class="sxs-lookup"><span data-stu-id="f5910-142">\'Read Threat and Vulnerability Management vulnerability information\'</span></span>
<span data-ttu-id="f5910-143">위임(직장 또는 학교 계정)</span><span class="sxs-lookup"><span data-stu-id="f5910-143">Delegated (work or school account)</span></span> | <span data-ttu-id="f5910-144">Vulnerability.Read</span><span class="sxs-lookup"><span data-stu-id="f5910-144">Vulnerability.Read</span></span> | <span data-ttu-id="f5910-145">\'위협 및 취약성 관리 취약성 정보 읽기\'</span><span class="sxs-lookup"><span data-stu-id="f5910-145">\'Read Threat and Vulnerability Management vulnerability information\'</span></span>

### <a name="13-url"></a><span data-ttu-id="f5910-146">1.3 URL</span><span class="sxs-lookup"><span data-stu-id="f5910-146">1.3 URL</span></span>

```http
GET /api/machines/SoftwareVulnerabilitiesByMachine
```

### <a name="14-parameters"></a><span data-ttu-id="f5910-147">1.4 매개 변수</span><span class="sxs-lookup"><span data-stu-id="f5910-147">1.4 Parameters</span></span>

- <span data-ttu-id="f5910-148">pageSize(기본값 = 50,000) - 응답 결과 수</span><span class="sxs-lookup"><span data-stu-id="f5910-148">pageSize (default = 50,000) – number of results in response</span></span>
- <span data-ttu-id="f5910-149">$top - 반환할 결과 수입니다(@odata.nextLink를 반환하지 않습니다. 따라서 모든 데이터를 끌어오지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="f5910-149">$top – number of results to return (doesn’t return @odata.nextLink and therefore doesn’t pull all the data)</span></span>

### <a name="15-properties"></a><span data-ttu-id="f5910-150">1.5 속성</span><span class="sxs-lookup"><span data-stu-id="f5910-150">1.5 Properties</span></span>
>
>[!Note]
>
>- <span data-ttu-id="f5910-151">각 레코드는 약 1KB의 데이터입니다.</span><span class="sxs-lookup"><span data-stu-id="f5910-151">Each record is approximately 1KB of data.</span></span> <span data-ttu-id="f5910-152">올바른 pageSize 매개 변수를 선택할 때 이 문제를 고려해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f5910-152">You should take this into account when choosing the correct pageSize parameter for you.</span></span>
>
>- <span data-ttu-id="f5910-153">응답에 일부 추가 열이 반환될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f5910-153">Some additional columns might be returned in the response.</span></span> <span data-ttu-id="f5910-154">이러한 열은 임시로 제거될 수 있습니다. 문서화한 열만 사용하시기 바랍니다.</span><span class="sxs-lookup"><span data-stu-id="f5910-154">These columns are temporary and might be removed, please use only the documented columns.</span></span>
>
>- <span data-ttu-id="f5910-155">다음 표에 정의된 속성은 속성 ID에 따라 사전순으로 나열됩니다.</span><span class="sxs-lookup"><span data-stu-id="f5910-155">The properties defined in the following table are listed alphabetically, by property ID.</span></span>  <span data-ttu-id="f5910-156">이 API를 실행하면 결과 출력이 이 표에 나열된 순서대로 반환되지 않을 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f5910-156">When running this API, the resulting output will not necessarily be returned in the same order listed in this table.</span></span>
>

<span data-ttu-id="f5910-157">속성(ID)</span><span class="sxs-lookup"><span data-stu-id="f5910-157">Property (ID)</span></span> | <span data-ttu-id="f5910-158">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="f5910-158">Data type</span></span> | <span data-ttu-id="f5910-159">설명</span><span class="sxs-lookup"><span data-stu-id="f5910-159">Description</span></span> | <span data-ttu-id="f5910-160">반환된 값의 예</span><span class="sxs-lookup"><span data-stu-id="f5910-160">Example of a returned value</span></span>
:---|:---|:---|:---
<span data-ttu-id="f5910-161">CveId</span><span class="sxs-lookup"><span data-stu-id="f5910-161">CveId</span></span> | <span data-ttu-id="f5910-162">문자열</span><span class="sxs-lookup"><span data-stu-id="f5910-162">string</span></span> | <span data-ttu-id="f5910-163">CVE(Common Vulnerabilities and Exposures) 시스템의 보안 취약성에 할당된 고유 식별자입니다.</span><span class="sxs-lookup"><span data-stu-id="f5910-163">Unique identifier assigned to the security vulnerability under the Common Vulnerabilities and Exposures (CVE) system.</span></span> | <span data-ttu-id="f5910-164">CVE-2020-15992</span><span class="sxs-lookup"><span data-stu-id="f5910-164">CVE-2020-15992</span></span>
<span data-ttu-id="f5910-165">CvssScore</span><span class="sxs-lookup"><span data-stu-id="f5910-165">CvssScore</span></span> | <span data-ttu-id="f5910-166">문자열</span><span class="sxs-lookup"><span data-stu-id="f5910-166">string</span></span> | <span data-ttu-id="f5910-167">CVE의 CVSS 점수입니다.</span><span class="sxs-lookup"><span data-stu-id="f5910-167">The CVSS score of the CVE.</span></span> | <span data-ttu-id="f5910-168">6.2</span><span class="sxs-lookup"><span data-stu-id="f5910-168">6.2</span></span>
<span data-ttu-id="f5910-169">DeviceId</span><span class="sxs-lookup"><span data-stu-id="f5910-169">DeviceId</span></span> | <span data-ttu-id="f5910-170">문자열</span><span class="sxs-lookup"><span data-stu-id="f5910-170">string</span></span> | <span data-ttu-id="f5910-171">서비스에서 장치의 고유 식별자입니다.</span><span class="sxs-lookup"><span data-stu-id="f5910-171">Unique identifier for the device in the service.</span></span> | <span data-ttu-id="f5910-172">9eaf3a8b5962e0e6b1af9ec756664a9b823df2d1</span><span class="sxs-lookup"><span data-stu-id="f5910-172">9eaf3a8b5962e0e6b1af9ec756664a9b823df2d1</span></span>
<span data-ttu-id="f5910-173">장치 이름</span><span class="sxs-lookup"><span data-stu-id="f5910-173">DeviceName</span></span> | <span data-ttu-id="f5910-174">문자열</span><span class="sxs-lookup"><span data-stu-id="f5910-174">string</span></span> | <span data-ttu-id="f5910-175">장치의 FQDN(FQDN)입니다.</span><span class="sxs-lookup"><span data-stu-id="f5910-175">Fully qualified domain name (FQDN) of the device.</span></span> | <span data-ttu-id="f5910-176">johnlaptop.europe.contoso.com</span><span class="sxs-lookup"><span data-stu-id="f5910-176">johnlaptop.europe.contoso.com</span></span>
<span data-ttu-id="f5910-177">DiskPaths</span><span class="sxs-lookup"><span data-stu-id="f5910-177">DiskPaths</span></span>  | <span data-ttu-id="f5910-178">배열 \[ 문자열\]</span><span class="sxs-lookup"><span data-stu-id="f5910-178">Array\[string\]</span></span> | <span data-ttu-id="f5910-179">제품이 장치에 설치되어 있는 디스크 증거입니다.</span><span class="sxs-lookup"><span data-stu-id="f5910-179">Disk evidence that the product is installed on the device.</span></span> | <span data-ttu-id="f5910-180">[ "C:\Program Files (x86)\Microsoft\Silverlight\Application\silverlight.exe" ]</span><span class="sxs-lookup"><span data-stu-id="f5910-180">[ "C:\Program Files (x86)\Microsoft\Silverlight\Application\silverlight.exe" ]</span></span>
<span data-ttu-id="f5910-181">ExploitabilityLevel</span><span class="sxs-lookup"><span data-stu-id="f5910-181">ExploitabilityLevel</span></span> | <span data-ttu-id="f5910-182">문자열</span><span class="sxs-lookup"><span data-stu-id="f5910-182">string</span></span> | <span data-ttu-id="f5910-183">이 취약성의 악용성 수준(NoExploit, ExploitIsPublic, ExploitIsVerified, ExploitIsInKit)</span><span class="sxs-lookup"><span data-stu-id="f5910-183">The exploitability level of this vulnerability (NoExploit, ExploitIsPublic, ExploitIsVerified, ExploitIsInKit)</span></span> | <span data-ttu-id="f5910-184">ExploitIsInKit</span><span class="sxs-lookup"><span data-stu-id="f5910-184">ExploitIsInKit</span></span>
<span data-ttu-id="f5910-185">FirstSeenTimestamp</span><span class="sxs-lookup"><span data-stu-id="f5910-185">FirstSeenTimestamp</span></span> | <span data-ttu-id="f5910-186">문자열</span><span class="sxs-lookup"><span data-stu-id="f5910-186">string</span></span> | <span data-ttu-id="f5910-187">이 제품의 CVE가 디바이스에 처음 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="f5910-187">First time the CVE of this product was seen on the device.</span></span> | <span data-ttu-id="f5910-188">2020-11-03 10:13:34.8476880</span><span class="sxs-lookup"><span data-stu-id="f5910-188">2020-11-03 10:13:34.8476880</span></span>
<span data-ttu-id="f5910-189">Id</span><span class="sxs-lookup"><span data-stu-id="f5910-189">Id</span></span> | <span data-ttu-id="f5910-190">문자열</span><span class="sxs-lookup"><span data-stu-id="f5910-190">string</span></span> | <span data-ttu-id="f5910-191">레코드의 고유 식별자입니다.</span><span class="sxs-lookup"><span data-stu-id="f5910-191">Unique identifier for the record.</span></span> | <span data-ttu-id="f5910-192">123ABG55_573AG&mnp!</span><span class="sxs-lookup"><span data-stu-id="f5910-192">123ABG55_573AG&mnp!</span></span>
<span data-ttu-id="f5910-193">LastSeenTimestamp</span><span class="sxs-lookup"><span data-stu-id="f5910-193">LastSeenTimestamp</span></span> | <span data-ttu-id="f5910-194">문자열</span><span class="sxs-lookup"><span data-stu-id="f5910-194">string</span></span> | <span data-ttu-id="f5910-195">디바이스에서 CVE를 마지막으로 본 시간입니다.</span><span class="sxs-lookup"><span data-stu-id="f5910-195">Last time the CVE was seen on the device.</span></span> | <span data-ttu-id="f5910-196">2020-11-03 10:13:34.8476880</span><span class="sxs-lookup"><span data-stu-id="f5910-196">2020-11-03 10:13:34.8476880</span></span>
<span data-ttu-id="f5910-197">OSPlatform</span><span class="sxs-lookup"><span data-stu-id="f5910-197">OSPlatform</span></span> | <span data-ttu-id="f5910-198">문자열</span><span class="sxs-lookup"><span data-stu-id="f5910-198">string</span></span> | <span data-ttu-id="f5910-199">디바이스에서 실행되는 운영 체제의 플랫폼입니다.</span><span class="sxs-lookup"><span data-stu-id="f5910-199">Platform of the operating system running on the device.</span></span> <span data-ttu-id="f5910-200">이는 Windows 10 및 Windows 7과 같이 동일한 제품군 내의 변형을 포함하여 특정 운영 체제를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="f5910-200">This indicates specific operating systems, including variations within the same family, such as Windows 10 and Windows 7.</span></span> <span data-ttu-id="f5910-201">자세한 내용은 tvm 지원 운영 체제 및 플랫폼을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="f5910-201">See tvm supported operating systems and platforms for details.</span></span> | <span data-ttu-id="f5910-202">Windows 10</span><span class="sxs-lookup"><span data-stu-id="f5910-202">Windows10</span></span>
<span data-ttu-id="f5910-203">RbacGroupName</span><span class="sxs-lookup"><span data-stu-id="f5910-203">RbacGroupName</span></span>  | <span data-ttu-id="f5910-204">문자열</span><span class="sxs-lookup"><span data-stu-id="f5910-204">string</span></span> | <span data-ttu-id="f5910-205">RBAC(역할 기반 액세스 제어) 그룹입니다.</span><span class="sxs-lookup"><span data-stu-id="f5910-205">The role-based access control (RBAC) group.</span></span> <span data-ttu-id="f5910-206">이 장치가 RBAC 그룹에 할당되지 않은 경우 값은 "지정되지 않았습니다."가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f5910-206">If this device is not assigned to any RBAC group, the value will be “Unassigned.”</span></span> <span data-ttu-id="f5910-207">조직에 RBAC 그룹이 없는 경우 값은 "없음"이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f5910-207">If the organization doesn’t contain any RBAC groups, the value will be “None.”</span></span> | <span data-ttu-id="f5910-208">서버</span><span class="sxs-lookup"><span data-stu-id="f5910-208">Servers</span></span>
<span data-ttu-id="f5910-209">RecommendationReference</span><span class="sxs-lookup"><span data-stu-id="f5910-209">RecommendationReference</span></span> | <span data-ttu-id="f5910-210">문자열</span><span class="sxs-lookup"><span data-stu-id="f5910-210">string</span></span> | <span data-ttu-id="f5910-211">이 소프트웨어와 관련된 권장 ID에 대한 참조입니다.</span><span class="sxs-lookup"><span data-stu-id="f5910-211">A reference to the recommendation ID related to this software.</span></span> | <span data-ttu-id="f5910-212">va-_-microsoft-_-silverlight</span><span class="sxs-lookup"><span data-stu-id="f5910-212">va-_-microsoft-_-silverlight</span></span>
<span data-ttu-id="f5910-213">RecommendedSecurityUpdate(선택 사항)</span><span class="sxs-lookup"><span data-stu-id="f5910-213">RecommendedSecurityUpdate (optional)</span></span> | <span data-ttu-id="f5910-214">문자열</span><span class="sxs-lookup"><span data-stu-id="f5910-214">string</span></span> | <span data-ttu-id="f5910-215">소프트웨어 공급업체가 취약점을 해결하기 위해 제공한 보안 업데이트의 이름 또는 설명입니다.</span><span class="sxs-lookup"><span data-stu-id="f5910-215">Name or description of the security update provided by the software vendor to address the vulnerability.</span></span> | <span data-ttu-id="f5910-216">2020년 4월 보안 업데이트</span><span class="sxs-lookup"><span data-stu-id="f5910-216">April 2020 Security Updates</span></span>
<span data-ttu-id="f5910-217">RecommendedSecurityUpdateId(선택 사항)</span><span class="sxs-lookup"><span data-stu-id="f5910-217">RecommendedSecurityUpdateId (optional)</span></span> | <span data-ttu-id="f5910-218">문자열</span><span class="sxs-lookup"><span data-stu-id="f5910-218">string</span></span> | <span data-ttu-id="f5910-219">해당 지침 또는 기술 자료(KB) 문서의 해당 보안 업데이트 또는 식별자 식별자</span><span class="sxs-lookup"><span data-stu-id="f5910-219">Identifier of the applicable security updates or identifier for the corresponding guidance or knowledge base (KB) articles</span></span> | <span data-ttu-id="f5910-220">4550961</span><span class="sxs-lookup"><span data-stu-id="f5910-220">4550961</span></span>
<span data-ttu-id="f5910-221">RegistryPaths</span><span class="sxs-lookup"><span data-stu-id="f5910-221">RegistryPaths</span></span>  | <span data-ttu-id="f5910-222">배열 \[ 문자열\]</span><span class="sxs-lookup"><span data-stu-id="f5910-222">Array\[string\]</span></span> | <span data-ttu-id="f5910-223">제품이 장치에 설치되어 있는 레지스트리 증거입니다.</span><span class="sxs-lookup"><span data-stu-id="f5910-223">Registry evidence that the product is installed in the device.</span></span> | <span data-ttu-id="f5910-224">[ "HKEY_LOCAL_MACHINE\SOFTWARE\WOW6432Node\Microsoft\Windows\CurrentVersion\Uninstall\MicrosoftSilverlight" ]</span><span class="sxs-lookup"><span data-stu-id="f5910-224">[ "HKEY_LOCAL_MACHINE\SOFTWARE\WOW6432Node\Microsoft\Windows\CurrentVersion\Uninstall\MicrosoftSilverlight" ]</span></span>
<span data-ttu-id="f5910-225">SoftwareName</span><span class="sxs-lookup"><span data-stu-id="f5910-225">SoftwareName</span></span> | <span data-ttu-id="f5910-226">문자열</span><span class="sxs-lookup"><span data-stu-id="f5910-226">string</span></span> | <span data-ttu-id="f5910-227">소프트웨어 제품의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="f5910-227">Name of the software product.</span></span> | <span data-ttu-id="f5910-228">chrome</span><span class="sxs-lookup"><span data-stu-id="f5910-228">chrome</span></span>
<span data-ttu-id="f5910-229">SoftwareVendor</span><span class="sxs-lookup"><span data-stu-id="f5910-229">SoftwareVendor</span></span> | <span data-ttu-id="f5910-230">문자열</span><span class="sxs-lookup"><span data-stu-id="f5910-230">string</span></span> | <span data-ttu-id="f5910-231">소프트웨어 공급업체의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="f5910-231">Name of the software vendor.</span></span> | <span data-ttu-id="f5910-232">google</span><span class="sxs-lookup"><span data-stu-id="f5910-232">google</span></span>
<span data-ttu-id="f5910-233">SoftwareVersion</span><span class="sxs-lookup"><span data-stu-id="f5910-233">SoftwareVersion</span></span> | <span data-ttu-id="f5910-234">문자열</span><span class="sxs-lookup"><span data-stu-id="f5910-234">string</span></span> | <span data-ttu-id="f5910-235">소프트웨어 제품의 버전 번호입니다.</span><span class="sxs-lookup"><span data-stu-id="f5910-235">Version number of the software product.</span></span> | <span data-ttu-id="f5910-236">81.0.4044.138</span><span class="sxs-lookup"><span data-stu-id="f5910-236">81.0.4044.138</span></span>
<span data-ttu-id="f5910-237">VulnerabilitySeverityLevel</span><span class="sxs-lookup"><span data-stu-id="f5910-237">VulnerabilitySeverityLevel</span></span>  | <span data-ttu-id="f5910-238">문자열</span><span class="sxs-lookup"><span data-stu-id="f5910-238">string</span></span> | <span data-ttu-id="f5910-239">CVSS 점수 및 위협 환경의 영향을 미치는 동적 요인에 따라 보안 취약성에 할당된 심각도 수준입니다.</span><span class="sxs-lookup"><span data-stu-id="f5910-239">Severity level assigned to the security vulnerability based on the CVSS score and dynamic factors influenced by the threat landscape.</span></span> | <span data-ttu-id="f5910-240">보통</span><span class="sxs-lookup"><span data-stu-id="f5910-240">Medium</span></span>

### <a name="16-examples"></a><span data-ttu-id="f5910-241">1.6 예제</span><span class="sxs-lookup"><span data-stu-id="f5910-241">1.6 Examples</span></span>

#### <a name="161-request-example"></a><span data-ttu-id="f5910-242">1.6.1 요청 예제</span><span class="sxs-lookup"><span data-stu-id="f5910-242">1.6.1 Request example</span></span>

```http
GET https://api.securitycenter.microsoft.com/api/machines/SoftwareVulnerabilitiesByMachine?pageSize=5
```

#### <a name="162-response-example"></a><span data-ttu-id="f5910-243">1.6.2 응답 예제</span><span class="sxs-lookup"><span data-stu-id="f5910-243">1.6.2 Response example</span></span>

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

## <a name="2-export-software-vulnerabilities-assessment-via-files"></a><span data-ttu-id="f5910-244">2. 파일로 소프트웨어 취약점 평가 내보내기</span><span class="sxs-lookup"><span data-stu-id="f5910-244">2. Export software vulnerabilities assessment (via files)</span></span>

### <a name="21-api-method-description"></a><span data-ttu-id="f5910-245">2.1 API 메서드 설명</span><span class="sxs-lookup"><span data-stu-id="f5910-245">2.1 API method description</span></span>

<span data-ttu-id="f5910-246">이 API 응답에는 장치당 설치된 소프트웨어의 모든 데이터가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f5910-246">This API response contains all the data of installed software per device.</span></span> <span data-ttu-id="f5910-247">DeviceId, SoftwareVendor, SoftwareName, SoftwareVersion, CVEID의 모든 고유 조합에 대한 항목이 있는 테이블을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="f5910-247">Returns a table with an entry for every unique combination of DeviceId, SoftwareVendor, SoftwareName, SoftwareVersion, CVEID.</span></span>

#### <a name="212-limitations"></a><span data-ttu-id="f5910-248">2.1.2 제한 사항</span><span class="sxs-lookup"><span data-stu-id="f5910-248">2.1.2 Limitations</span></span>

<span data-ttu-id="f5910-249">이 API의 속도 제한은 분당 5통, 시간당 20통입니다.</span><span class="sxs-lookup"><span data-stu-id="f5910-249">Rate limitations for this API are 5 calls per minute and 20 calls per hour.</span></span>

### <a name="22-permissions"></a><span data-ttu-id="f5910-250">2.2 사용 권한</span><span class="sxs-lookup"><span data-stu-id="f5910-250">2.2 Permissions</span></span>

<span data-ttu-id="f5910-251">이 API를 호출하려면 다음 권한 중 하나가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="f5910-251">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="f5910-252">사용 권한을 선택하는 방법을 포함하여 자세한 내용은 [Use Microsoft Defender for Endpoint API(끝점 API용 Microsoft Defender](apis-intro.md)사용)를 참조합니다.</span><span class="sxs-lookup"><span data-stu-id="f5910-252">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs for details](apis-intro.md).</span></span>

<span data-ttu-id="f5910-253">사용 권한 유형</span><span class="sxs-lookup"><span data-stu-id="f5910-253">Permission type</span></span> | <span data-ttu-id="f5910-254">사용 권한</span><span class="sxs-lookup"><span data-stu-id="f5910-254">Permission</span></span> | <span data-ttu-id="f5910-255">사용 권한 표시 이름</span><span class="sxs-lookup"><span data-stu-id="f5910-255">Permission display name</span></span>
---|---|---
<span data-ttu-id="f5910-256">응용 프로그램</span><span class="sxs-lookup"><span data-stu-id="f5910-256">Application</span></span> | <span data-ttu-id="f5910-257">Vulnerability.Read.All</span><span class="sxs-lookup"><span data-stu-id="f5910-257">Vulnerability.Read.All</span></span> | <span data-ttu-id="f5910-258">\'위협 및 취약성 관리 취약성 정보 읽기\'</span><span class="sxs-lookup"><span data-stu-id="f5910-258">\'Read Threat and Vulnerability Management vulnerability information\'</span></span>
<span data-ttu-id="f5910-259">위임(직장 또는 학교 계정)</span><span class="sxs-lookup"><span data-stu-id="f5910-259">Delegated (work or school account)</span></span> | <span data-ttu-id="f5910-260">Vulnerability.Read</span><span class="sxs-lookup"><span data-stu-id="f5910-260">Vulnerability.Read</span></span> | <span data-ttu-id="f5910-261">\'위협 및 취약성 관리 취약성 정보 읽기\'</span><span class="sxs-lookup"><span data-stu-id="f5910-261">\'Read Threat and Vulnerability Management vulnerability information\'</span></span>

### <a name="23-url"></a><span data-ttu-id="f5910-262">2.3 URL</span><span class="sxs-lookup"><span data-stu-id="f5910-262">2.3 URL</span></span>

```http
GET /api/machines/SoftwareVulnerabilitiesExport
```

### <a name="24-parameters"></a><span data-ttu-id="f5910-263">2.4 매개 변수</span><span class="sxs-lookup"><span data-stu-id="f5910-263">2.4 Parameters</span></span>

- <span data-ttu-id="f5910-264">sasValidHours – 다운로드 URL이 유효한 시간(최대 24시간)</span><span class="sxs-lookup"><span data-stu-id="f5910-264">sasValidHours – The number of hours that the download URLs will be valid for (Maximum 24 hours)</span></span>

### <a name="25-properties"></a><span data-ttu-id="f5910-265">2.5 속성</span><span class="sxs-lookup"><span data-stu-id="f5910-265">2.5 Properties</span></span>

>[!Note]
>
>- <span data-ttu-id="f5910-266">파일은 여러 & Json 형식의 gzip 압축 파일 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="f5910-266">The files are gzip compressed & in multiline Json format.</span></span>
>
>- <span data-ttu-id="f5910-267">다운로드 URL은 3시간 동안만 유효합니다. 그렇지 않으면 매개 변수를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f5910-267">The download URLs are only valid for 3 hours; otherwise you can use the parameter.</span></span>
>
>- <span data-ttu-id="f5910-268">데이터의 최대 다운로드 속도를 위해 데이터가 있는 동일한 Azure 지역에서 다운로드하는지 확인하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f5910-268">For maximum download speed of your data, you can make sure you are downloading from the same Azure region that your data resides.</span></span>
>

>[!Note]
>
>- <span data-ttu-id="f5910-269">각 레코드는 약 1KB의 데이터입니다.</span><span class="sxs-lookup"><span data-stu-id="f5910-269">Each record is approximately 1KB of data.</span></span> <span data-ttu-id="f5910-270">올바른 pageSize 매개 변수를 선택할 때 이 문제를 고려해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f5910-270">You should take this into account when choosing the correct pageSize parameter for you.</span></span>
>
>- <span data-ttu-id="f5910-271">응답에 일부 추가 열이 반환될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f5910-271">Some additional columns might be returned in the response.</span></span> <span data-ttu-id="f5910-272">이러한 열은 임시로 제거될 수 있습니다. 문서화한 열만 사용하시기 바랍니다.</span><span class="sxs-lookup"><span data-stu-id="f5910-272">These columns are temporary and might be removed, please use only the documented columns.</span></span>
>

<span data-ttu-id="f5910-273">속성(ID)</span><span class="sxs-lookup"><span data-stu-id="f5910-273">Property (ID)</span></span> | <span data-ttu-id="f5910-274">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="f5910-274">Data type</span></span> | <span data-ttu-id="f5910-275">설명</span><span class="sxs-lookup"><span data-stu-id="f5910-275">Description</span></span> | <span data-ttu-id="f5910-276">반환된 값의 예</span><span class="sxs-lookup"><span data-stu-id="f5910-276">Example of a returned value</span></span>
:---|:---|:---|:---
<span data-ttu-id="f5910-277">파일 내보내기</span><span class="sxs-lookup"><span data-stu-id="f5910-277">Export files</span></span> | <span data-ttu-id="f5910-278">array \[ string\]</span><span class="sxs-lookup"><span data-stu-id="f5910-278">array\[string\]</span></span>  | <span data-ttu-id="f5910-279">조직의 현재 스냅숏을 저장하는 파일의 다운로드 URL 목록입니다.</span><span class="sxs-lookup"><span data-stu-id="f5910-279">A list of download URLs for files holding the current snapshot of the organization.</span></span> | <span data-ttu-id="f5910-280">[  “https://tvmexportstrstgeus.blob.core.windows.net/tvm-export...1”, “https://tvmexportstrstgeus.blob.core.windows.net/tvm-export...2”  ]</span><span class="sxs-lookup"><span data-stu-id="f5910-280">[  “https://tvmexportstrstgeus.blob.core.windows.net/tvm-export...1”, “https://tvmexportstrstgeus.blob.core.windows.net/tvm-export...2”  ]</span></span>
<span data-ttu-id="f5910-281">GeneratedTime</span><span class="sxs-lookup"><span data-stu-id="f5910-281">GeneratedTime</span></span> | <span data-ttu-id="f5910-282">문자열</span><span class="sxs-lookup"><span data-stu-id="f5910-282">string</span></span> | <span data-ttu-id="f5910-283">내보내기 생성 시간입니다.</span><span class="sxs-lookup"><span data-stu-id="f5910-283">The time that the export was generated.</span></span> | <span data-ttu-id="f5910-284">2021-05-20T08:00:00Z</span><span class="sxs-lookup"><span data-stu-id="f5910-284">2021-05-20T08:00:00Z</span></span>

### <a name="26-examples"></a><span data-ttu-id="f5910-285">2.6 예제</span><span class="sxs-lookup"><span data-stu-id="f5910-285">2.6 Examples</span></span>

#### <a name="261-request-example"></a><span data-ttu-id="f5910-286">2.6.1 요청 예제</span><span class="sxs-lookup"><span data-stu-id="f5910-286">2.6.1 Request example</span></span>

```http
GET https://api-us.securitycenter.contoso.com/api/machines/SoftwareVulnerabilitiesExport
```

#### <a name="262-response-example"></a><span data-ttu-id="f5910-287">2.6.2 응답 예제</span><span class="sxs-lookup"><span data-stu-id="f5910-287">2.6.2 Response example</span></span>

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

## <a name="see-also"></a><span data-ttu-id="f5910-288">참고 항목</span><span class="sxs-lookup"><span data-stu-id="f5910-288">See also</span></span>

- [<span data-ttu-id="f5910-289">장치당 평가 방법 및 속성 내보내기</span><span class="sxs-lookup"><span data-stu-id="f5910-289">Export assessment methods and properties per device</span></span>](get-assessmnt-1methods-properties.md)

- [<span data-ttu-id="f5910-290">장치당 보안 구성 평가 내보내기</span><span class="sxs-lookup"><span data-stu-id="f5910-290">Export secure configuration assessment per device</span></span>](get-assessmnt-secure-cfg.md)

- [<span data-ttu-id="f5910-291">장치당 소프트웨어 인벤토리 평가 내보내기</span><span class="sxs-lookup"><span data-stu-id="f5910-291">Export software inventory assessment per device</span></span>](get-assessmnt-software-inventory.md)

<span data-ttu-id="f5910-292">기타 관련</span><span class="sxs-lookup"><span data-stu-id="f5910-292">Other related</span></span>

- [<span data-ttu-id="f5910-293">위험 기반 위협 & 취약성 관리</span><span class="sxs-lookup"><span data-stu-id="f5910-293">Risk-based threat & vulnerability management</span></span>](next-gen-threat-and-vuln-mgt.md)

- [<span data-ttu-id="f5910-294">조직의 취약성</span><span class="sxs-lookup"><span data-stu-id="f5910-294">Vulnerabilities in your organization</span></span>](tvm-weaknesses.md)
