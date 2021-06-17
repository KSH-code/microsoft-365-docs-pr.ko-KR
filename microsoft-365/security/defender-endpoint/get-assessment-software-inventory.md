---
title: 장치당 소프트웨어 인벤토리 평가 내보내기
description: DeviceId, SoftwareVendor, SoftwareName, SoftwareVersion의 모든 고유 조합에 대한 항목이 있는 테이블을 반환합니다.
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
ms.openlocfilehash: 4f2e16acf474d6da8867a6bd392f9e90e0cf166e
ms.sourcegitcommit: 34c06715e036255faa75c66ebf95c12a85f8ef42
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/17/2021
ms.locfileid: "52984847"
---
# <a name="export-software-inventory-assessment-per-device"></a><span data-ttu-id="3fbe1-104">장치당 소프트웨어 인벤토리 평가 내보내기</span><span class="sxs-lookup"><span data-stu-id="3fbe1-104">Export software inventory assessment per device</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="3fbe1-105">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="3fbe1-105">**Applies to:**</span></span>

- [<span data-ttu-id="3fbe1-106">엔드포인트용 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="3fbe1-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="3fbe1-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="3fbe1-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="3fbe1-108">끝점용 Microsoft Defender를 경험하고 싶나요?</span><span class="sxs-lookup"><span data-stu-id="3fbe1-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="3fbe1-109">무료 평가판에 등록합니다.</span><span class="sxs-lookup"><span data-stu-id="3fbe1-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

>
<span data-ttu-id="3fbe1-110">다양한 형식의 데이터를 얻기 위해 다른 API 호출이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3fbe1-110">There are different API calls to get different types of data.</span></span> <span data-ttu-id="3fbe1-111">데이터 양은 매우 크기 때문에 다음 두 가지 방법으로 데이터를 검색할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3fbe1-111">Because the amount of data can be large, there are two ways it can be retrieved:</span></span>

- <span data-ttu-id="3fbe1-112">[소프트웨어 인벤토리 평가 **OData 내보내기**](#1-export-software-inventory-assessment-odata)  API는 OData 프로토콜에 따라 조직의 모든 데이터를 Json 응답으로 끌어들입니다.</span><span class="sxs-lookup"><span data-stu-id="3fbe1-112">[Export software inventory assessment **OData**](#1-export-software-inventory-assessment-odata)  The API pulls all data in your organization as Json responses, following the OData protocol.</span></span> <span data-ttu-id="3fbe1-113">이 방법은 _100 K_ 장치 미만의 소규모 조직에 가장 적합한 방법입니다.</span><span class="sxs-lookup"><span data-stu-id="3fbe1-113">This method is best for _small organizations with less than 100-K devices_.</span></span> <span data-ttu-id="3fbe1-114">응답이 단계적이기 때문에 응답의 odata.nextLink 필드를 사용하여 다음 결과를 \@ 내보일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3fbe1-114">The response is paginated, so you can use the \@odata.nextLink field from the response to fetch the next results.</span></span>

- <span data-ttu-id="3fbe1-115">[파일을 통해 소프트웨어 인벤토리 **평가 내보내기**](#2-export-software-inventory-assessment-via-files)  이 API 솔루션을 사용하면 더 많은 양의 데이터를 더 빠르고 안정적으로 끌어 올 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3fbe1-115">[Export software inventory assessment **via files**](#2-export-software-inventory-assessment-via-files)  This API solution enables pulling larger amounts of data faster and more reliably.</span></span> <span data-ttu-id="3fbe1-116">따라서 100 K 장치가 넘는 대규모 조직에 권장됩니다.</span><span class="sxs-lookup"><span data-stu-id="3fbe1-116">Therefore, it is recommended for large organizations, with more than 100-K devices.</span></span> <span data-ttu-id="3fbe1-117">이 API는 조직의 모든 데이터를 다운로드 파일로 끌어들입니다.</span><span class="sxs-lookup"><span data-stu-id="3fbe1-117">This API pulls all data in your organization as download files.</span></span> <span data-ttu-id="3fbe1-118">응답에는 응답에서 모든 데이터를 다운로드하는 URL이 Azure 저장소.</span><span class="sxs-lookup"><span data-stu-id="3fbe1-118">The response contains URLs to download all the data from Azure Storage.</span></span> <span data-ttu-id="3fbe1-119">이 API를 사용하면 다음과 같이 모든 데이터를 Azure 저장소 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3fbe1-119">This API enables you to download all your data from Azure Storage as follows:</span></span>

  - <span data-ttu-id="3fbe1-120">API를 호출하여 모든 조직 데이터와 함께 다운로드 URL 목록을 얻습니다.</span><span class="sxs-lookup"><span data-stu-id="3fbe1-120">Call the API to get a list of download URLs with all your organization data.</span></span>

  - <span data-ttu-id="3fbe1-121">다운로드 URL을 사용하여 모든 파일을 다운로드하고 원하는 데이터를 처리합니다.</span><span class="sxs-lookup"><span data-stu-id="3fbe1-121">Download all the files using the download URLs and process the data as you like.</span></span>

<span data-ttu-id="3fbe1-122">_OData_ 또는 파일을 통해 수집되는 데이터는 현재 상태의 현재 스냅숏으로 기록 데이터를 포함하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="3fbe1-122">Data that is collected (using either _OData_ or _via files_) is the current snapshot of the current state, and does not contain historic data.</span></span> <span data-ttu-id="3fbe1-123">기록 데이터를 수집하려면 고객은 데이터를 자체 데이터 저장소에 저장해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3fbe1-123">In order to collect historic data, customers must save the data in their own data storages.</span></span>

> [!Note]
>
> <span data-ttu-id="3fbe1-124">다른 설명이 없는 한 나열된 \*\*\*\* 모든 내보내기 평가 방법은 전체 내보내기 및 장치(장치당 \*\*\*\* **_참조)입니다._**</span><span class="sxs-lookup"><span data-stu-id="3fbe1-124">Unless indicated otherwise, all export assessment methods listed are **_full export_** and **_by device_** (also referred to as **_per device_**).</span></span>

## <a name="1-export-software-inventory-assessment-odata"></a><span data-ttu-id="3fbe1-125">1. OData(소프트웨어 인벤토리 평가) 내보내기</span><span class="sxs-lookup"><span data-stu-id="3fbe1-125">1. Export software inventory assessment (OData)</span></span>

### <a name="11-api-method-description"></a><span data-ttu-id="3fbe1-126">1.1 API 메서드 설명</span><span class="sxs-lookup"><span data-stu-id="3fbe1-126">1.1 API method description</span></span>

<span data-ttu-id="3fbe1-127">이 API 응답에는 장치당 설치된 소프트웨어의 모든 데이터가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3fbe1-127">This API response contains all the data of installed software per device.</span></span> <span data-ttu-id="3fbe1-128">DeviceId, SoftwareVendor, SoftwareName, SoftwareVersion의 모든 고유 조합에 대한 항목이 있는 테이블을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="3fbe1-128">Returns a table with an entry for every unique combination of DeviceId, SoftwareVendor, SoftwareName, SoftwareVersion.</span></span>

#### <a name="limitations"></a><span data-ttu-id="3fbe1-129">제한 사항</span><span class="sxs-lookup"><span data-stu-id="3fbe1-129">Limitations</span></span>

- <span data-ttu-id="3fbe1-130">최대 페이지 크기는 200,000개입니다.</span><span class="sxs-lookup"><span data-stu-id="3fbe1-130">Maximum page size is 200,000.</span></span>

- <span data-ttu-id="3fbe1-131">이 API에 대한 속도 제한은 분당 30개 호출과 시간당 1,000개 호출입니다.</span><span class="sxs-lookup"><span data-stu-id="3fbe1-131">Rate limitations for this API are 30 calls per minute and 1000 calls per hour.</span></span>

### <a name="12-permissions"></a><span data-ttu-id="3fbe1-132">1.2 사용 권한</span><span class="sxs-lookup"><span data-stu-id="3fbe1-132">1.2 Permissions</span></span>

<span data-ttu-id="3fbe1-133">이 API를 호출하려면 다음 권한 중 하나가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="3fbe1-133">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="3fbe1-134">사용 권한을 선택하는 방법을 포함하여 자세한 내용은 [Use Microsoft Defender for Endpoint API for details을 참조합니다.](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="3fbe1-134">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs for details.](apis-intro.md)</span></span>

<span data-ttu-id="3fbe1-135">사용 권한 유형</span><span class="sxs-lookup"><span data-stu-id="3fbe1-135">Permission type</span></span> | <span data-ttu-id="3fbe1-136">사용 권한</span><span class="sxs-lookup"><span data-stu-id="3fbe1-136">Permission</span></span> | <span data-ttu-id="3fbe1-137">사용 권한 표시 이름</span><span class="sxs-lookup"><span data-stu-id="3fbe1-137">Permission display name</span></span>
---|---|---
<span data-ttu-id="3fbe1-138">응용 프로그램</span><span class="sxs-lookup"><span data-stu-id="3fbe1-138">Application</span></span> | <span data-ttu-id="3fbe1-139">Software.Read.All</span><span class="sxs-lookup"><span data-stu-id="3fbe1-139">Software.Read.All</span></span> | <span data-ttu-id="3fbe1-140">\'위협 및 취약성 관리 취약성 정보 읽기\'</span><span class="sxs-lookup"><span data-stu-id="3fbe1-140">\'Read Threat and Vulnerability Management vulnerability information\'</span></span>
<span data-ttu-id="3fbe1-141">위임(직장 또는 학교 계정)</span><span class="sxs-lookup"><span data-stu-id="3fbe1-141">Delegated (work or school account)</span></span> | <span data-ttu-id="3fbe1-142">Software.Read</span><span class="sxs-lookup"><span data-stu-id="3fbe1-142">Software.Read</span></span> | <span data-ttu-id="3fbe1-143">\'위협 및 취약성 관리 취약성 정보 읽기\'</span><span class="sxs-lookup"><span data-stu-id="3fbe1-143">\'Read Threat and Vulnerability Management vulnerability information\'</span></span>

### <a name="13-url"></a><span data-ttu-id="3fbe1-144">1.3 URL</span><span class="sxs-lookup"><span data-stu-id="3fbe1-144">1.3 URL</span></span>

```http
GET /api/machines/SoftwareInventoryByMachine
```

### <a name="14-parameters"></a><span data-ttu-id="3fbe1-145">1.4 매개 변수</span><span class="sxs-lookup"><span data-stu-id="3fbe1-145">1.4 Parameters</span></span>

- <span data-ttu-id="3fbe1-146">pageSize(기본값 = 50,000) - 응답의 결과 수입니다.</span><span class="sxs-lookup"><span data-stu-id="3fbe1-146">pageSize (default = 50,000) – number of results in response.</span></span>

- <span data-ttu-id="3fbe1-147">$top - 반환할 결과 수입니다(@odata.nextLink를 반환하지 않습니다. 따라서 모든 데이터를 끌어오지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="3fbe1-147">$top – number of results to return (doesn’t return @odata.nextLink and therefore doesn’t pull all the data)</span></span>

### <a name="15-properties"></a><span data-ttu-id="3fbe1-148">1.5 속성</span><span class="sxs-lookup"><span data-stu-id="3fbe1-148">1.5 Properties</span></span>

>[!NOTE]
>
><span data-ttu-id="3fbe1-149">-각 레코드는 약 0.5KB의 데이터입니다.</span><span class="sxs-lookup"><span data-stu-id="3fbe1-149">-Each record is approximately 0.5KB of data.</span></span> <span data-ttu-id="3fbe1-150">올바른 pageSize 매개 변수를 선택할 때 이 문제를 고려해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3fbe1-150">You should take this into account when choosing the correct pageSize parameter for you.</span></span>

><span data-ttu-id="3fbe1-151">-다음 표에 정의된 속성은 속성 ID에 따라 사전순으로 나열됩니다.</span><span class="sxs-lookup"><span data-stu-id="3fbe1-151">-The properties defined in the following table are listed alphabetically, by property ID.</span></span> <span data-ttu-id="3fbe1-152">이 API를 실행하면 결과 출력이 이 표에 나열된 순서대로 반환되지 않을 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3fbe1-152">When running this API, the resulting output will not necessarily be returned in the same order listed in this table.</span></span>
>
><span data-ttu-id="3fbe1-153">-응답에 일부 추가 열이 반환될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3fbe1-153">-Some additional columns might be returned in the response.</span></span> <span data-ttu-id="3fbe1-154">이러한 열은 임시로 제거될 수 있습니다. 문서화한 열만 사용하시기 바랍니다.</span><span class="sxs-lookup"><span data-stu-id="3fbe1-154">These columns are temporary and might be removed, please use only the documented columns.</span></span>

<span data-ttu-id="3fbe1-155">속성(ID)</span><span class="sxs-lookup"><span data-stu-id="3fbe1-155">Property (ID)</span></span> | <span data-ttu-id="3fbe1-156">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="3fbe1-156">Data type</span></span> | <span data-ttu-id="3fbe1-157">설명</span><span class="sxs-lookup"><span data-stu-id="3fbe1-157">Description</span></span> | <span data-ttu-id="3fbe1-158">반환된 값의 예</span><span class="sxs-lookup"><span data-stu-id="3fbe1-158">Example of a returned value</span></span>
:---|:---|:---|:---
<span data-ttu-id="3fbe1-159">DeviceId</span><span class="sxs-lookup"><span data-stu-id="3fbe1-159">DeviceId</span></span> | <span data-ttu-id="3fbe1-160">문자열</span><span class="sxs-lookup"><span data-stu-id="3fbe1-160">string</span></span> | <span data-ttu-id="3fbe1-161">서비스에서 장치의 고유 식별자입니다.</span><span class="sxs-lookup"><span data-stu-id="3fbe1-161">Unique identifier for the device in the service.</span></span> | <span data-ttu-id="3fbe1-162">9eaf3a8b5962e0e6b1af9ec756664a9b823df2d1</span><span class="sxs-lookup"><span data-stu-id="3fbe1-162">9eaf3a8b5962e0e6b1af9ec756664a9b823df2d1</span></span>
<span data-ttu-id="3fbe1-163">장치 이름</span><span class="sxs-lookup"><span data-stu-id="3fbe1-163">DeviceName</span></span> | <span data-ttu-id="3fbe1-164">문자열</span><span class="sxs-lookup"><span data-stu-id="3fbe1-164">string</span></span> | <span data-ttu-id="3fbe1-165">장치의 FQDN(FQDN)입니다.</span><span class="sxs-lookup"><span data-stu-id="3fbe1-165">Fully qualified domain name (FQDN) of the device.</span></span> | <span data-ttu-id="3fbe1-166">johnlaptop.europe.contoso.com</span><span class="sxs-lookup"><span data-stu-id="3fbe1-166">johnlaptop.europe.contoso.com</span></span>
<span data-ttu-id="3fbe1-167">DiskPaths</span><span class="sxs-lookup"><span data-stu-id="3fbe1-167">DiskPaths</span></span> | <span data-ttu-id="3fbe1-168">Array[string]</span><span class="sxs-lookup"><span data-stu-id="3fbe1-168">Array[string]</span></span>  | <span data-ttu-id="3fbe1-169">제품이 장치에 설치되어 있는 디스크 증거입니다.</span><span class="sxs-lookup"><span data-stu-id="3fbe1-169">Disk evidence that the product is installed on the device.</span></span> | <span data-ttu-id="3fbe1-170">[ "C: \\ Program Files (x86) \\ Microsoft \\ Silverlight \\ Application \\silverlight.exe" ]</span><span class="sxs-lookup"><span data-stu-id="3fbe1-170">[ "C:\\Program Files (x86)\\Microsoft\\Silverlight\\Application\\silverlight.exe" ]</span></span>
<span data-ttu-id="3fbe1-171">EndOfSupportDate</span><span class="sxs-lookup"><span data-stu-id="3fbe1-171">EndOfSupportDate</span></span> | <span data-ttu-id="3fbe1-172">문자열</span><span class="sxs-lookup"><span data-stu-id="3fbe1-172">string</span></span> | <span data-ttu-id="3fbe1-173">이 소프트웨어에 대한 지원이 종료되는 날짜입니다.</span><span class="sxs-lookup"><span data-stu-id="3fbe1-173">The date in which support for this software has or will end.</span></span> | <span data-ttu-id="3fbe1-174">2020-12-30</span><span class="sxs-lookup"><span data-stu-id="3fbe1-174">2020-12-30</span></span>
<span data-ttu-id="3fbe1-175">EndOfSupportStatus</span><span class="sxs-lookup"><span data-stu-id="3fbe1-175">EndOfSupportStatus</span></span> | <span data-ttu-id="3fbe1-176">문자열</span><span class="sxs-lookup"><span data-stu-id="3fbe1-176">string</span></span> | <span data-ttu-id="3fbe1-177">지원 종료 상태입니다.</span><span class="sxs-lookup"><span data-stu-id="3fbe1-177">End of support status.</span></span> <span data-ttu-id="3fbe1-178">None, EOS 버전, 예정된 EOS 버전, EOS 소프트웨어, 예정된 EOS 소프트웨어 등 가능한 값을 포함할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3fbe1-178">Can contain these possible values: None, EOS Version, Upcoming EOS Version, EOS Software, Upcoming EOS Software.</span></span> | <span data-ttu-id="3fbe1-179">예정된 EOS</span><span class="sxs-lookup"><span data-stu-id="3fbe1-179">Upcoming EOS</span></span>
<span data-ttu-id="3fbe1-180">Id</span><span class="sxs-lookup"><span data-stu-id="3fbe1-180">Id</span></span> | <span data-ttu-id="3fbe1-181">문자열</span><span class="sxs-lookup"><span data-stu-id="3fbe1-181">string</span></span> | <span data-ttu-id="3fbe1-182">레코드의 고유 식별자입니다.</span><span class="sxs-lookup"><span data-stu-id="3fbe1-182">Unique identifier for the record.</span></span> | <span data-ttu-id="3fbe1-183">123ABG55_573AG&mnp!</span><span class="sxs-lookup"><span data-stu-id="3fbe1-183">123ABG55_573AG&mnp!</span></span>
<span data-ttu-id="3fbe1-184">NumberOfWeaknesses</span><span class="sxs-lookup"><span data-stu-id="3fbe1-184">NumberOfWeaknesses</span></span> | <span data-ttu-id="3fbe1-185">int</span><span class="sxs-lookup"><span data-stu-id="3fbe1-185">int</span></span> | <span data-ttu-id="3fbe1-186">이 장치에서 이 소프트웨어의 약점 수</span><span class="sxs-lookup"><span data-stu-id="3fbe1-186">Number of weaknesses on this software on this device</span></span> | <span data-ttu-id="3fbe1-187">3</span><span class="sxs-lookup"><span data-stu-id="3fbe1-187">3</span></span>
<span data-ttu-id="3fbe1-188">OSPlatform</span><span class="sxs-lookup"><span data-stu-id="3fbe1-188">OSPlatform</span></span> | <span data-ttu-id="3fbe1-189">문자열</span><span class="sxs-lookup"><span data-stu-id="3fbe1-189">string</span></span> | <span data-ttu-id="3fbe1-190">디바이스에서 실행되는 운영 체제의 플랫폼입니다.</span><span class="sxs-lookup"><span data-stu-id="3fbe1-190">Platform of the operating system running on the device.</span></span> <span data-ttu-id="3fbe1-191">이는 Windows 10 및 Windows 7과 같이 동일한 제품군 내의 변형을 포함하여 특정 운영 체제를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="3fbe1-191">This indicates specific operating systems, including variations within the same family, such as Windows 10 and Windows 7.</span></span> <span data-ttu-id="3fbe1-192">자세한 내용은 tvm 지원 운영 체제 및 플랫폼을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="3fbe1-192">See tvm supported operating systems and platforms for details.</span></span> | <span data-ttu-id="3fbe1-193">Windows 10</span><span class="sxs-lookup"><span data-stu-id="3fbe1-193">Windows10</span></span>
<span data-ttu-id="3fbe1-194">RbacGroupName</span><span class="sxs-lookup"><span data-stu-id="3fbe1-194">RbacGroupName</span></span> | <span data-ttu-id="3fbe1-195">문자열</span><span class="sxs-lookup"><span data-stu-id="3fbe1-195">string</span></span> | <span data-ttu-id="3fbe1-196">RBAC(역할 기반 액세스 제어) 그룹입니다.</span><span class="sxs-lookup"><span data-stu-id="3fbe1-196">The role-based access control (RBAC) group.</span></span> <span data-ttu-id="3fbe1-197">이 장치가 RBAC 그룹에 할당되지 않은 경우 값은 "지정되지 않았습니다."가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3fbe1-197">If this device is not assigned to any RBAC group, the value will be “Unassigned.”</span></span> <span data-ttu-id="3fbe1-198">조직에 RBAC 그룹이 없는 경우 값은 "없음"이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3fbe1-198">If the organization doesn’t contain any RBAC groups, the value will be “None.”</span></span> | <span data-ttu-id="3fbe1-199">서버</span><span class="sxs-lookup"><span data-stu-id="3fbe1-199">Servers</span></span>
<span data-ttu-id="3fbe1-200">RegistryPaths</span><span class="sxs-lookup"><span data-stu-id="3fbe1-200">RegistryPaths</span></span> | <span data-ttu-id="3fbe1-201">Array[string]</span><span class="sxs-lookup"><span data-stu-id="3fbe1-201">Array[string]</span></span> | <span data-ttu-id="3fbe1-202">제품이 장치에 설치되어 있는 레지스트리 증거입니다.</span><span class="sxs-lookup"><span data-stu-id="3fbe1-202">Registry evidence that the product is installed in the device.</span></span> | <span data-ttu-id="3fbe1-203">[ "HKEY_LOCAL_MACHINE \\ SOFTWARE \\ WOW6432Node \\ Microsoft Windows \\ \\ CurrentVersion \\ Uninstall \\ Microsoft Silverlight" ]</span><span class="sxs-lookup"><span data-stu-id="3fbe1-203">[ "HKEY_LOCAL_MACHINE\\SOFTWARE\\WOW6432Node\\Microsoft\\Windows\\CurrentVersion\\Uninstall\\Microsoft Silverlight" ]</span></span>
<span data-ttu-id="3fbe1-204">SoftwareFirstSeenTimestamp</span><span class="sxs-lookup"><span data-stu-id="3fbe1-204">SoftwareFirstSeenTimestamp</span></span> | <span data-ttu-id="3fbe1-205">문자열</span><span class="sxs-lookup"><span data-stu-id="3fbe1-205">string</span></span> | <span data-ttu-id="3fbe1-206">디바이스에서 이 소프트웨어를 처음 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3fbe1-206">The first time this software was seen on the device.</span></span> | <span data-ttu-id="3fbe1-207">2019-04-07 02:06:47</span><span class="sxs-lookup"><span data-stu-id="3fbe1-207">2019-04-07 02:06:47</span></span>
<span data-ttu-id="3fbe1-208">SoftwareName</span><span class="sxs-lookup"><span data-stu-id="3fbe1-208">SoftwareName</span></span> | <span data-ttu-id="3fbe1-209">문자열</span><span class="sxs-lookup"><span data-stu-id="3fbe1-209">string</span></span> | <span data-ttu-id="3fbe1-210">소프트웨어 제품의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="3fbe1-210">Name of the software product.</span></span> | <span data-ttu-id="3fbe1-211">Silverlight</span><span class="sxs-lookup"><span data-stu-id="3fbe1-211">Silverlight</span></span>
<span data-ttu-id="3fbe1-212">SoftwareVendor</span><span class="sxs-lookup"><span data-stu-id="3fbe1-212">SoftwareVendor</span></span> | <span data-ttu-id="3fbe1-213">문자열</span><span class="sxs-lookup"><span data-stu-id="3fbe1-213">string</span></span> | <span data-ttu-id="3fbe1-214">소프트웨어 공급업체의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="3fbe1-214">Name of the software vendor.</span></span> | <span data-ttu-id="3fbe1-215">microsoft</span><span class="sxs-lookup"><span data-stu-id="3fbe1-215">microsoft</span></span>
<span data-ttu-id="3fbe1-216">SoftwareVersion</span><span class="sxs-lookup"><span data-stu-id="3fbe1-216">SoftwareVersion</span></span> | <span data-ttu-id="3fbe1-217">문자열</span><span class="sxs-lookup"><span data-stu-id="3fbe1-217">string</span></span> | <span data-ttu-id="3fbe1-218">소프트웨어 제품의 버전 번호입니다.</span><span class="sxs-lookup"><span data-stu-id="3fbe1-218">Version number of the software product.</span></span> | <span data-ttu-id="3fbe1-219">81.0.4044.138</span><span class="sxs-lookup"><span data-stu-id="3fbe1-219">81.0.4044.138</span></span>

### <a name="16-examples"></a><span data-ttu-id="3fbe1-220">1.6 예제</span><span class="sxs-lookup"><span data-stu-id="3fbe1-220">1.6 Examples</span></span>

#### <a name="161-request-example"></a><span data-ttu-id="3fbe1-221">1.6.1 요청 예제</span><span class="sxs-lookup"><span data-stu-id="3fbe1-221">1.6.1 Request example</span></span>

```http
GET https://api.securitycenter.microsoft.com/api/machines/SoftwareInventoryByMachine?pageSize=5  &sinceTime=2021-05-19T18%3A35%3A49.924Z 
```

#### <a name="162-response-example"></a><span data-ttu-id="3fbe1-222">1.6.2 응답 예제</span><span class="sxs-lookup"><span data-stu-id="3fbe1-222">1.6.2 Response example</span></span>

```json
{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#Collection(contoso.windowsDefenderATP.api.AssetSoftware)",
    "value": [
        {
            "deviceId": "00044f68765bbaf712342dbe6db733b6a9c59ab4",
            "rbacGroupName": "hhh",
            "deviceName": "ComputerPII_18993b45912eeb224b2be2f5ea3142726e63f16a.DomainPII_21eeb80d086e79dbfa178eadfa25e8de9acfa346.corp.contoso.com",
            "osPlatform": "Windows10",
            "softwareVendor": "microsoft",
            "softwareName": "windows_10",
            "softwareVersion": "10.0.17763.1637",
            "numberOfWeaknesses": 58,
            "diskPaths": [],
            "registryPaths": [],
            "softwareFirstSeenTimestamp": "2020-12-30 11:07:15",
            "endOfSupportStatus": "Upcoming EOS Version",
            "endOfSupportDate": "2021-05-11T00:00:00+00:00"
        },
        {
            "deviceId": "00044f68765bbaf712342dbe6db733b6a9c59ab4",
            "rbacGroupName": "hhh",
            "deviceName": "ComputerPII_18993b45912eeb224b2be2f5ea3142726e63f16a.DomainPII_21eeb80d086e79dbfa178eadfa25e8de9acfa346.corp.contoso.com",
            "osPlatform": "Windows10",
            "softwareVendor": "microsoft",
            "softwareName": ".net_framework",
            "softwareVersion": "4.0.0.0",
            "numberOfWeaknesses": 0,
            "diskPaths": [],
            "registryPaths": [
                "SOFTWARE\\Microsoft\\NET Framework Setup\\NDP\\v4.0\\Client\\Install"
            ],
            "softwareFirstSeenTimestamp": "2020-12-30 11:07:15",
            "endOfSupportStatus": "None",
            "endOfSupportDate": null
        },
        {
            "deviceId": "00044f68765bbaf712342dbe6db733b6a9c59ab4",
            "rbacGroupName": "hhh",
            "deviceName": "ComputerPII_18993b45912eeb224b2be2f5ea3142726e63f16a.DomainPII_21eed80d086e79bdfa178eadfa25e8de9acfa346.corp.contoso.com",
            "osPlatform": "Windows10",
            "softwareVendor": "microsoft",
            "softwareName": "system_center_2012_endpoint_protection",
            "softwareVersion": "4.7.214.0",
            "numberOfWeaknesses": 0,
            "diskPaths": [],
            "registryPaths": [
                "HKEY_LOCAL_MACHINE\\SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\Uninstall\\Microsoft Security Client"
            ],
            "softwareFirstSeenTimestamp": "2020-12-30 11:07:15",
            "endOfSupportStatus": "None",
            "endOfSupportDate": null
        },
        {
            "deviceId": "00044f68765ddaf71234bde6bd733d6a9c59ad4",
            "rbacGroupName": "hhh",
            "deviceName": "ComputerPII_18993b45912eeb224b2be2f5ea3142726e63f16a.DomainPII_21eeb80d086e79dbfa178aedfa25e8be9acfa346.corp.contoso.com",
            "osPlatform": "Windows10",
            "softwareVendor": "microsoft",
            "softwareName": "configuration_manager",
            "softwareVersion": "5.0.8634.1000",
            "numberOfWeaknesses": 0,
            "diskPaths": [],
            "registryPaths": [
                "HKEY_LOCAL_MACHINE\\SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\Uninstall\\{B7D3A842-E826-4542-B39B-1D883264B279}"
            ],
            "softwareFirstSeenTimestamp": "2020-12-30 11:07:15",
            "endOfSupportStatus": "None",
            "endOfSupportDate": null
        },
        {
            "deviceId": "00044f38765bbaf712342dbe6db733b6a9c59ab4",
            "rbacGroupName": "hhh",
            "deviceName": "ComputerPII_18993b45912eeb224b2de2f5ea3142726e63f16a.DomainPII_21eeb80d086e79bdfa178eadfa25e8be9acfa346.corp.contoso.com",
            "osPlatform": "Windows10",
            "softwareVendor": "microsoft",
            "softwareName": "system_center_2012_endpoint_protection",
            "softwareVersion": "4.10.209.0",
            "numberOfWeaknesses": 0,
            "diskPaths": [],
            "registryPaths": [
                "HKEY_LOCAL_MACHINE\\SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\Uninstall\\Microsoft Security Client"
            ],
            "softwareFirstSeenTimestamp": "2020-12-30 11:07:15",
            "endOfSupportStatus": "None",
            "endOfSupportDate": null
        }
    ],
    "@odata.nextLink": "https://api.securitycenter.microsoft.com/api/machines/SoftwareInventoryByMachine?pagesize=5&$skiptoken=eyJFeHBvcnREZWZpbml0aW9uIjp7IlRpbWVQYXRoIjoiMjAyMS0wMS0yNS8wMjAwLyJ9LCJFeHBvcnRGaWxlSW5kZXgiOjAsIkxpbmVTdG9wcGVkQXQiOjV9"
}
```

## <a name="2-export-software-inventory-assessment-via-files"></a><span data-ttu-id="3fbe1-223">2. 파일로 소프트웨어 인벤토리 평가 내보내기</span><span class="sxs-lookup"><span data-stu-id="3fbe1-223">2. Export software inventory assessment (via files)</span></span>

### <a name="21-api-method-description"></a><span data-ttu-id="3fbe1-224">2.1 API 메서드 설명</span><span class="sxs-lookup"><span data-stu-id="3fbe1-224">2.1 API method description</span></span>

<span data-ttu-id="3fbe1-225">이 API 응답에는 장치당 설치된 소프트웨어의 모든 데이터가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3fbe1-225">This API response contains all the data of installed software per device.</span></span> <span data-ttu-id="3fbe1-226">DeviceId, SoftwareVendor, SoftwareName, SoftwareVersion의 모든 고유 조합에 대한 항목이 있는 테이블을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="3fbe1-226">Returns a table with an entry for every unique combination of DeviceId, SoftwareVendor, SoftwareName, SoftwareVersion.</span></span>

#### <a name="211-limitations"></a><span data-ttu-id="3fbe1-227">2.1.1 제한 사항</span><span class="sxs-lookup"><span data-stu-id="3fbe1-227">2.1.1 Limitations</span></span>

<span data-ttu-id="3fbe1-228">이 API의 속도 제한은 분당 5통, 시간당 20통입니다.</span><span class="sxs-lookup"><span data-stu-id="3fbe1-228">Rate limitations for this API are 5 calls per minute and 20 calls per hour.</span></span>

### <a name="22-permissions"></a><span data-ttu-id="3fbe1-229">2.2 사용 권한</span><span class="sxs-lookup"><span data-stu-id="3fbe1-229">2.2 Permissions</span></span>

<span data-ttu-id="3fbe1-230">이 API를 호출하려면 다음 권한 중 하나가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="3fbe1-230">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="3fbe1-231">사용 권한을 선택하는 방법을 포함하여 자세한 내용은 [Use Microsoft Defender for Endpoint API for details을 참조합니다.](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="3fbe1-231">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs for details.](apis-intro.md)</span></span>

<span data-ttu-id="3fbe1-232">사용 권한 유형</span><span class="sxs-lookup"><span data-stu-id="3fbe1-232">Permission type</span></span> | <span data-ttu-id="3fbe1-233">사용 권한</span><span class="sxs-lookup"><span data-stu-id="3fbe1-233">Permission</span></span> | <span data-ttu-id="3fbe1-234">사용 권한 표시 이름</span><span class="sxs-lookup"><span data-stu-id="3fbe1-234">Permission display name</span></span>
---|---|---
<span data-ttu-id="3fbe1-235">응용 프로그램</span><span class="sxs-lookup"><span data-stu-id="3fbe1-235">Application</span></span> | <span data-ttu-id="3fbe1-236">Software.Read.All</span><span class="sxs-lookup"><span data-stu-id="3fbe1-236">Software.Read.All</span></span> | <span data-ttu-id="3fbe1-237">\'위협 및 취약성 관리 취약성 정보 읽기\'</span><span class="sxs-lookup"><span data-stu-id="3fbe1-237">\'Read Threat and Vulnerability Management vulnerability information\'</span></span>
<span data-ttu-id="3fbe1-238">위임(직장 또는 학교 계정)</span><span class="sxs-lookup"><span data-stu-id="3fbe1-238">Delegated (work or school account)</span></span> | <span data-ttu-id="3fbe1-239">Software.Read</span><span class="sxs-lookup"><span data-stu-id="3fbe1-239">Software.Read</span></span> | <span data-ttu-id="3fbe1-240">\'위협 및 취약성 관리 취약성 정보 읽기\'</span><span class="sxs-lookup"><span data-stu-id="3fbe1-240">\'Read Threat and Vulnerability Management vulnerability information\'</span></span>

### <a name="23-url"></a><span data-ttu-id="3fbe1-241">2.3 URL</span><span class="sxs-lookup"><span data-stu-id="3fbe1-241">2.3 URL</span></span>

```http
GET /api/machines/SoftwareInventoryExport
```

### <a name="parameters"></a><span data-ttu-id="3fbe1-242">매개 변수</span><span class="sxs-lookup"><span data-stu-id="3fbe1-242">Parameters</span></span>

- <span data-ttu-id="3fbe1-243">sasValidHours – 다운로드 URL이 유효한 시간(최대 24시간)</span><span class="sxs-lookup"><span data-stu-id="3fbe1-243">sasValidHours – The number of hours that the download URLs will be valid for (Maximum 24 hours)</span></span>

### <a name="25-properties"></a><span data-ttu-id="3fbe1-244">2.5 속성</span><span class="sxs-lookup"><span data-stu-id="3fbe1-244">2.5 Properties</span></span>

>[!Note]
>
>- <span data-ttu-id="3fbe1-245">파일은 여러 & Json 형식의 gzip 압축 파일 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="3fbe1-245">The files are gzip compressed & in multiline Json format.</span></span>
>
>- <span data-ttu-id="3fbe1-246">다운로드 URL은 3시간 동안만 유효합니다.</span><span class="sxs-lookup"><span data-stu-id="3fbe1-246">The download URLs are only valid for 3 hours.</span></span> <span data-ttu-id="3fbe1-247">그렇지 않으면 매개 변수를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3fbe1-247">Otherwise you can use the parameter.</span></span>
>
><span data-ttu-id="3fbe1-248">_ 데이터의 최대 다운로드 속도를 위해 데이터가 있는 동일한 Azure 지역에서 다운로드하는지 확인하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3fbe1-248">_ For maximum download speed of your data, you can make sure you are downloading from the same Azure region that your data resides.</span></span>
>
<span data-ttu-id="3fbe1-249">속성(ID)</span><span class="sxs-lookup"><span data-stu-id="3fbe1-249">Property (ID)</span></span> | <span data-ttu-id="3fbe1-250">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="3fbe1-250">Data type</span></span> | <span data-ttu-id="3fbe1-251">설명</span><span class="sxs-lookup"><span data-stu-id="3fbe1-251">Description</span></span> | <span data-ttu-id="3fbe1-252">반환된 값의 예</span><span class="sxs-lookup"><span data-stu-id="3fbe1-252">Example of a returned value</span></span>
:---|:---|:---|:---
<span data-ttu-id="3fbe1-253">파일 내보내기</span><span class="sxs-lookup"><span data-stu-id="3fbe1-253">Export files</span></span> | <span data-ttu-id="3fbe1-254">array \[ string\]</span><span class="sxs-lookup"><span data-stu-id="3fbe1-254">array\[string\]</span></span> | <span data-ttu-id="3fbe1-255">조직의 현재 스냅숏을 저장하는 파일의 다운로드 URL 목록</span><span class="sxs-lookup"><span data-stu-id="3fbe1-255">A list of download URLs for files holding the current snapshot of the organization</span></span> | <span data-ttu-id="3fbe1-256">[  Https://tvmexportstrstgeus.blob.core.windows.net/tvm-export...1”, “https://tvmexportstrstgeus.blob.core.windows.net/tvm-export...2” ]</span><span class="sxs-lookup"><span data-stu-id="3fbe1-256">[  Https://tvmexportstrstgeus.blob.core.windows.net/tvm-export...1”, “https://tvmexportstrstgeus.blob.core.windows.net/tvm-export...2” ]</span></span>
<span data-ttu-id="3fbe1-257">GeneratedTime</span><span class="sxs-lookup"><span data-stu-id="3fbe1-257">GeneratedTime</span></span> | <span data-ttu-id="3fbe1-258">문자열</span><span class="sxs-lookup"><span data-stu-id="3fbe1-258">string</span></span> | <span data-ttu-id="3fbe1-259">내보내기 생성 시간입니다.</span><span class="sxs-lookup"><span data-stu-id="3fbe1-259">The time that the export was generated.</span></span> | <span data-ttu-id="3fbe1-260">2021-05-20T08:00:00Z ]</span><span class="sxs-lookup"><span data-stu-id="3fbe1-260">2021-05-20T08:00:00Z  ]</span></span>

### <a name="26-examples"></a><span data-ttu-id="3fbe1-261">2.6 예제</span><span class="sxs-lookup"><span data-stu-id="3fbe1-261">2.6 Examples</span></span>

#### <a name="261-request-example"></a><span data-ttu-id="3fbe1-262">2.6.1 요청 예제</span><span class="sxs-lookup"><span data-stu-id="3fbe1-262">2.6.1 Request example</span></span>

```http
GET https://api.securitycenter.microsoft.com/api/machines/SoftwareInventoryExport
```

#### <a name="262-response-example"></a><span data-ttu-id="3fbe1-263">2.6.2 응답 예제</span><span class="sxs-lookup"><span data-stu-id="3fbe1-263">2.6.2 Response example</span></span>

```json
{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#microsoft.windowsDefenderATP.api.ExportFilesResponse",
    "exportFiles": [
        "https://tvmexportstrstgeus.blob.core.windows.net/tvm-export/2021-01-11/1101/SoftwareInventory/json/OrgId=12345678-195f-4223-9c7a-99fb420fd000/part-00393-e423630d-4c69-4490-8769-a4f5468c4f25.c000.json.gz?sv=2019-12-12&st=2021-01-11T11%3A55%3A51Z&se=2021-01-11T14%3A55%3A51Z&sr=b&sp=r&sig=...",
        "https://tvmexportstrstgeus.blob.core.windows.net/tvm-export/2021-01-11/1101/SoftwareInventory/json/OrgId=12345678-195f-4223-9c7a-99fb420fd000/part-00394-e423630d-4c69-4490-8769-a4f5468c4f25.c000.json.gz?sv=2019-12-12&st=2021-01-11T11%3A55%3A51Z&se=2021-01-11T14%3A55%3A51Z&sr=b&sp=r&sig=...",
        "https://tvmexportstrstgeus.blob.core.windows.net/tvm-export/2021-01-11/1101/SoftwareInventory/json/OrgId=12345678-195f-4223-9c7a-99fb420fd000/part-00394-e423630d-4c69-4490-8769-a4f5468c4f25.c001.json.gz?sv=2019-12-12&st=2021-01-11T11%3A55%3A51Z&se=2021-01-11T14%3A55%3A51Z&sr=b&sp=r&sig=..."
    ],
    "generatedTime": "2021-01-11T11:01:00Z"
}
```

## <a name="see-also"></a><span data-ttu-id="3fbe1-264">참고 항목</span><span class="sxs-lookup"><span data-stu-id="3fbe1-264">See also</span></span>

- [<span data-ttu-id="3fbe1-265">장치당 평가 방법 및 속성 내보내기</span><span class="sxs-lookup"><span data-stu-id="3fbe1-265">Export assessment methods and properties per device</span></span>](get-assessment-methods-properties.md)

- [<span data-ttu-id="3fbe1-266">장치당 보안 구성 평가 내보내기</span><span class="sxs-lookup"><span data-stu-id="3fbe1-266">Export secure configuration assessment per device</span></span>](get-assessment-secure-config.md)

- [<span data-ttu-id="3fbe1-267">장치당 소프트웨어 취약점 평가 내보내기</span><span class="sxs-lookup"><span data-stu-id="3fbe1-267">Export software vulnerabilities assessment per device</span></span>](get-assessment-software-vulnerabilities.md)

<span data-ttu-id="3fbe1-268">기타 관련</span><span class="sxs-lookup"><span data-stu-id="3fbe1-268">Other related</span></span>

- [<span data-ttu-id="3fbe1-269">위험 기반 위협 & 취약성 관리</span><span class="sxs-lookup"><span data-stu-id="3fbe1-269">Risk-based threat & vulnerability management</span></span>](next-gen-threat-and-vuln-mgt.md)

- [<span data-ttu-id="3fbe1-270">조직의 취약성</span><span class="sxs-lookup"><span data-stu-id="3fbe1-270">Vulnerabilities in your organization</span></span>](tvm-weaknesses.md)
