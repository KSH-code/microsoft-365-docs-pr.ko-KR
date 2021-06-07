---
title: 장치당 보안 구성 평가 내보내기
description: DeviceId, ConfigurationId의 모든 고유 조합에 대한 항목을 반환합니다.
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
ms.openlocfilehash: fe6a4604852965bdcc563ac0e410ca165bc5a088
ms.sourcegitcommit: b09aee96a1e2266b33ba81dfe497f24c5300bb56
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/06/2021
ms.locfileid: "52789408"
---
# <a name="export-secure-configuration-assessment-per-device"></a><span data-ttu-id="d3b46-104">장치당 보안 구성 평가 내보내기</span><span class="sxs-lookup"><span data-stu-id="d3b46-104">Export secure configuration assessment per device</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="d3b46-105">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="d3b46-105">**Applies to:**</span></span>

- [<span data-ttu-id="d3b46-106">엔드포인트용 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="d3b46-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="d3b46-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="d3b46-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="d3b46-108">끝점용 Microsoft Defender를 경험하고 싶나요?</span><span class="sxs-lookup"><span data-stu-id="d3b46-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="d3b46-109">무료 평가판에 등록합니다.</span><span class="sxs-lookup"><span data-stu-id="d3b46-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

[!include[Prerelease information](../../includes/prerelease.md)]
>
>
<span data-ttu-id="d3b46-110">장치 기준에 따라 모든 구성 및 구성 상태를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="d3b46-110">Returns all of the configurations and their status, on a per-device basis.</span></span>

<span data-ttu-id="d3b46-111">다양한 형식의 데이터를 얻기 위해 다른 API 호출이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d3b46-111">There are different API calls to get different types of data.</span></span> <span data-ttu-id="d3b46-112">데이터 양은 매우 크기 때문에 다음 두 가지 방법으로 데이터를 검색할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d3b46-112">Because the amount of data can be large, there are two ways it can be retrieved:</span></span>

- <span data-ttu-id="d3b46-113">[보안 구성 평가 **OData 내보내기:**](#1-export-secure-configuration-assessment-odata)API는 OData 프로토콜에 따라 조직의 모든 데이터를 Json 응답으로 끌어 들입니다.</span><span class="sxs-lookup"><span data-stu-id="d3b46-113">[Export secure configuration assessment **OData**](#1-export-secure-configuration-assessment-odata):  The API pulls all data in your organization as Json responses, following the OData protocol.</span></span> <span data-ttu-id="d3b46-114">이 방법은 _100 K_ 장치 미만의 소규모 조직에 가장 적합한 방법입니다.</span><span class="sxs-lookup"><span data-stu-id="d3b46-114">This method is best for _small organizations with less than 100-K devices_.</span></span> <span data-ttu-id="d3b46-115">응답이 단계적이기 때문에 응답의 odata.nextLink 필드를 사용하여 다음 결과를 \@ 내보일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d3b46-115">The response is paginated, so you can use the \@odata.nextLink field from the response to fetch the next results.</span></span>

- <span data-ttu-id="d3b46-116">파일을 통해 보안 [구성 평가 ](#2-export-secure-configuration-assessment-via-files)내보내기: 이 API 솔루션을 사용하면 더 많은 양의 데이터를 빠르고 안정적으로 끌어 올 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d3b46-116">[Export secure configuration assessment **via files**](#2-export-secure-configuration-assessment-via-files): This API solution enables pulling larger amounts of data faster and more reliably.</span></span> <span data-ttu-id="d3b46-117">따라서 100 K 장치가 넘는 대규모 조직에 권장됩니다.</span><span class="sxs-lookup"><span data-stu-id="d3b46-117">Therefore, it is recommended for large organizations, with more than 100-K devices.</span></span> <span data-ttu-id="d3b46-118">이 API는 조직의 모든 데이터를 다운로드 파일로 끌어들입니다.</span><span class="sxs-lookup"><span data-stu-id="d3b46-118">This API pulls all data in your organization as download files.</span></span> <span data-ttu-id="d3b46-119">응답에는 응답에서 모든 데이터를 다운로드하는 URL이 Azure Storage.</span><span class="sxs-lookup"><span data-stu-id="d3b46-119">The response contains URLs to download all the data from Azure Storage.</span></span> <span data-ttu-id="d3b46-120">이 API를 사용하면 다음과 같이 모든 데이터를 Azure Storage 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d3b46-120">This API enables you to download all your data from Azure Storage as follows:</span></span>

  - <span data-ttu-id="d3b46-121">API를 호출하여 모든 조직 데이터와 함께 다운로드 URL 목록을 얻습니다.</span><span class="sxs-lookup"><span data-stu-id="d3b46-121">Call the API to get a list of download URLs with all your organization data.</span></span>

  - <span data-ttu-id="d3b46-122">다운로드 URL을 사용하여 모든 파일을 다운로드하고 원하는 데이터를 처리합니다.</span><span class="sxs-lookup"><span data-stu-id="d3b46-122">Download all the files using the download URLs and process the data as you like.</span></span>

<span data-ttu-id="d3b46-123">_OData_ 또는 파일을 통해 수집되는 데이터는 현재 상태의 현재 스냅숏으로 기록 데이터를 포함하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d3b46-123">Data that is collected (using either _OData_ or _via files_) is the current snapshot of the current state, and does not contain historic data.</span></span> <span data-ttu-id="d3b46-124">기록 데이터를 수집하려면 고객은 데이터를 자체 데이터 저장소에 저장해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d3b46-124">In order to collect historic data, customers must save the data in their own data storages.</span></span>

> [!Note]
>
> <span data-ttu-id="d3b46-125">다른 설명이 없는 한 나열된 \*\*\*\* 모든 내보내기 평가 방법은 전체 내보내기 및 장치(장치당 \*\*\*\* **_참조)입니다._**</span><span class="sxs-lookup"><span data-stu-id="d3b46-125">Unless indicated otherwise, all export assessment methods listed are **_full export_** and **_by device_** (also referred to as **_per device_**).</span></span>

## <a name="1-export-secure-configuration-assessment-odata"></a><span data-ttu-id="d3b46-126">1. 보안 구성 평가 내보내기(OData)</span><span class="sxs-lookup"><span data-stu-id="d3b46-126">1. Export secure configuration assessment (OData)</span></span>

### <a name="11-api-method-description"></a><span data-ttu-id="d3b46-127">1.1 API 메서드 설명</span><span class="sxs-lookup"><span data-stu-id="d3b46-127">1.1 API method description</span></span>

<span data-ttu-id="d3b46-128">이 API 응답은 노출된 디바이스에 대한 보안 구성 평가를 포함하며 DeviceId, ConfigurationId의 모든 고유 조합에 대한 항목을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="d3b46-128">This API response contains the Secure Configuration Assessment on your exposed devices, and returns an entry for every unique combination of DeviceId, ConfigurationId.</span></span>

#### <a name="111-limitations"></a><span data-ttu-id="d3b46-129">1.1.1 제한 사항</span><span class="sxs-lookup"><span data-stu-id="d3b46-129">1.1.1 Limitations</span></span>

- <span data-ttu-id="d3b46-130">최대 페이지 크기는 200,000개입니다.</span><span class="sxs-lookup"><span data-stu-id="d3b46-130">Maximum page size is 200,000.</span></span>

- <span data-ttu-id="d3b46-131">이 API에 대한 속도 제한은 분당 30개 호출과 시간당 1,000개 호출입니다.</span><span class="sxs-lookup"><span data-stu-id="d3b46-131">Rate limitations for this API are 30 calls per minute and 1000 calls per hour.</span></span>

### <a name="12-permissions"></a><span data-ttu-id="d3b46-132">1.2 사용 권한</span><span class="sxs-lookup"><span data-stu-id="d3b46-132">1.2 Permissions</span></span>

<span data-ttu-id="d3b46-133">이 API를 호출하려면 다음 권한 중 하나가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="d3b46-133">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="d3b46-134">사용 권한을 선택하는 방법을 포함하여 자세한 내용은 [Use Microsoft Defender for Endpoint API](apis-intro.md) for details을 참조합니다.</span><span class="sxs-lookup"><span data-stu-id="d3b46-134">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md) for details.</span></span>

<span data-ttu-id="d3b46-135">사용 권한 유형</span><span class="sxs-lookup"><span data-stu-id="d3b46-135">Permission type</span></span> | <span data-ttu-id="d3b46-136">사용 권한</span><span class="sxs-lookup"><span data-stu-id="d3b46-136">Permission</span></span> | <span data-ttu-id="d3b46-137">사용 권한 표시 이름</span><span class="sxs-lookup"><span data-stu-id="d3b46-137">Permission display name</span></span>
---|---|---
<span data-ttu-id="d3b46-138">응용 프로그램</span><span class="sxs-lookup"><span data-stu-id="d3b46-138">Application</span></span> | <span data-ttu-id="d3b46-139">Vulnerability.Read.All</span><span class="sxs-lookup"><span data-stu-id="d3b46-139">Vulnerability.Read.All</span></span> | <span data-ttu-id="d3b46-140">\'위협 및 취약성 관리 취약성 정보 읽기\'</span><span class="sxs-lookup"><span data-stu-id="d3b46-140">\'Read Threat and Vulnerability Management vulnerability information\'</span></span>
<span data-ttu-id="d3b46-141">위임(직장 또는 학교 계정)</span><span class="sxs-lookup"><span data-stu-id="d3b46-141">Delegated (work or school account)</span></span> | <span data-ttu-id="d3b46-142">Vulnerability.Read</span><span class="sxs-lookup"><span data-stu-id="d3b46-142">Vulnerability.Read</span></span> | <span data-ttu-id="d3b46-143">\'위협 및 취약성 관리 취약성 정보 읽기\'</span><span class="sxs-lookup"><span data-stu-id="d3b46-143">\'Read Threat and Vulnerability Management vulnerability information\'</span></span>

### <a name="13-url"></a><span data-ttu-id="d3b46-144">1.3 URL</span><span class="sxs-lookup"><span data-stu-id="d3b46-144">1.3 URL</span></span>

```http
GET /api/machines/SecureConfigurationsAssessmentByMachine
```

### <a name="14-parameters"></a><span data-ttu-id="d3b46-145">1.4 매개 변수</span><span class="sxs-lookup"><span data-stu-id="d3b46-145">1.4 Parameters</span></span>

- <span data-ttu-id="d3b46-146">pageSize \( 기본값 = 50,000 – 응답 결과 \) 수</span><span class="sxs-lookup"><span data-stu-id="d3b46-146">pageSize \(default = 50,000\) – number of results in response</span></span>

- <span data-ttu-id="d3b46-147">\$top – 반환할 결과 수가 \( odata.nextLink를 반환하지 못하므로 모든 데이터를 \@ 끌어오지 않습니다.\)</span><span class="sxs-lookup"><span data-stu-id="d3b46-147">\$top – number of results to return \(doesn’t return \@odata.nextLink and therefore doesn’t pull all the data\)</span></span>

### <a name="15-properties"></a><span data-ttu-id="d3b46-148">1.5 속성</span><span class="sxs-lookup"><span data-stu-id="d3b46-148">1.5 Properties</span></span>

>[!Note]
>
>- <span data-ttu-id="d3b46-149">다음 표에 정의된 속성은 속성 ID에 따라 사전순으로 나열됩니다.</span><span class="sxs-lookup"><span data-stu-id="d3b46-149">The properties defined in the following table are listed alphabetically, by property ID.</span></span>  <span data-ttu-id="d3b46-150">이 API를 실행하면 결과 출력이 이 표에 나열된 순서대로 반환되지 않을 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d3b46-150">When running this API, the resulting output will not necessarily be returned in the same order listed in this table.</span></span>
>
>- <span data-ttu-id="d3b46-151">응답에 일부 추가 열이 반환될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d3b46-151">Some additional columns might be returned in the response.</span></span> <span data-ttu-id="d3b46-152">이러한 열은 임시로 제거될 수 있습니다. 문서화한 열만 사용하시기 바랍니다.</span><span class="sxs-lookup"><span data-stu-id="d3b46-152">These columns are temporary and might be removed, please use only the documented columns.</span></span>
>

<span data-ttu-id="d3b46-153">속성(ID)</span><span class="sxs-lookup"><span data-stu-id="d3b46-153">Property (ID)</span></span> | <span data-ttu-id="d3b46-154">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="d3b46-154">Data type</span></span> | <span data-ttu-id="d3b46-155">설명</span><span class="sxs-lookup"><span data-stu-id="d3b46-155">Description</span></span> | <span data-ttu-id="d3b46-156">반환된 값의 예</span><span class="sxs-lookup"><span data-stu-id="d3b46-156">Example of a returned value</span></span>
:---|:---|:---|:---
<span data-ttu-id="d3b46-157">ConfigurationCategory</span><span class="sxs-lookup"><span data-stu-id="d3b46-157">ConfigurationCategory</span></span> | <span data-ttu-id="d3b46-158">문자열</span><span class="sxs-lookup"><span data-stu-id="d3b46-158">string</span></span> | <span data-ttu-id="d3b46-159">구성이 속해 있는 범주 또는 그룹(응용 프로그램, OS, 네트워크, 계정, 보안 제어)</span><span class="sxs-lookup"><span data-stu-id="d3b46-159">Category or grouping to which the configuration belongs: Application, OS, Network, Accounts, Security controls</span></span> | <span data-ttu-id="d3b46-160">보안 제어</span><span class="sxs-lookup"><span data-stu-id="d3b46-160">Security controls</span></span>
<span data-ttu-id="d3b46-161">ConfigurationId</span><span class="sxs-lookup"><span data-stu-id="d3b46-161">ConfigurationId</span></span> | <span data-ttu-id="d3b46-162">문자열</span><span class="sxs-lookup"><span data-stu-id="d3b46-162">string</span></span> | <span data-ttu-id="d3b46-163">특정 구성의 고유 식별자</span><span class="sxs-lookup"><span data-stu-id="d3b46-163">Unique identifier for a specific configuration</span></span> | <span data-ttu-id="d3b46-164">scid-10000</span><span class="sxs-lookup"><span data-stu-id="d3b46-164">scid-10000</span></span>
<span data-ttu-id="d3b46-165">ConfigurationImpact</span><span class="sxs-lookup"><span data-stu-id="d3b46-165">ConfigurationImpact</span></span> | <span data-ttu-id="d3b46-166">문자열</span><span class="sxs-lookup"><span data-stu-id="d3b46-166">string</span></span> | <span data-ttu-id="d3b46-167">구성의 등급이 전반적인 구성 점수에 미치는 영향(1-10)</span><span class="sxs-lookup"><span data-stu-id="d3b46-167">Rated impact of the configuration to the overall configuration score (1-10)</span></span> | <span data-ttu-id="d3b46-168">9 </span><span class="sxs-lookup"><span data-stu-id="d3b46-168">9</span></span>
<span data-ttu-id="d3b46-169">ConfigurationName</span><span class="sxs-lookup"><span data-stu-id="d3b46-169">ConfigurationName</span></span> | <span data-ttu-id="d3b46-170">문자열</span><span class="sxs-lookup"><span data-stu-id="d3b46-170">string</span></span> | <span data-ttu-id="d3b46-171">구성 이름을 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="d3b46-171">Display name of the configuration</span></span> | <span data-ttu-id="d3b46-172">엔드포인트용 Microsoft Defender에 장치 온보딩</span><span class="sxs-lookup"><span data-stu-id="d3b46-172">Onboard devices to Microsoft Defender for Endpoint</span></span>
<span data-ttu-id="d3b46-173">ConfigurationSubcategory</span><span class="sxs-lookup"><span data-stu-id="d3b46-173">ConfigurationSubcategory</span></span> | <span data-ttu-id="d3b46-174">문자열</span><span class="sxs-lookup"><span data-stu-id="d3b46-174">string</span></span> | <span data-ttu-id="d3b46-175">구성이 속한 하위 범주나 하위 그룹</span><span class="sxs-lookup"><span data-stu-id="d3b46-175">Subcategory or subgrouping to which the configuration belongs.</span></span> <span data-ttu-id="d3b46-176">대부분의 경우 이는 특정 기능이나 특징을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="d3b46-176">In many cases, this describes specific capabilities or features.</span></span> | <span data-ttu-id="d3b46-177">장치 온보드</span><span class="sxs-lookup"><span data-stu-id="d3b46-177">Onboard Devices</span></span>
<span data-ttu-id="d3b46-178">DeviceId</span><span class="sxs-lookup"><span data-stu-id="d3b46-178">DeviceId</span></span> | <span data-ttu-id="d3b46-179">문자열</span><span class="sxs-lookup"><span data-stu-id="d3b46-179">string</span></span> | <span data-ttu-id="d3b46-180">서비스에서 장치의 고유 식별자입니다.</span><span class="sxs-lookup"><span data-stu-id="d3b46-180">Unique identifier for the device in the service.</span></span> | <span data-ttu-id="d3b46-181">9eaf3a8b5962e0e6b1af9ec756664a9b823df2d1</span><span class="sxs-lookup"><span data-stu-id="d3b46-181">9eaf3a8b5962e0e6b1af9ec756664a9b823df2d1</span></span>
<span data-ttu-id="d3b46-182">장치 이름</span><span class="sxs-lookup"><span data-stu-id="d3b46-182">DeviceName</span></span> | <span data-ttu-id="d3b46-183">문자열</span><span class="sxs-lookup"><span data-stu-id="d3b46-183">string</span></span> | <span data-ttu-id="d3b46-184">장치의 FQDN(FQDN)입니다.</span><span class="sxs-lookup"><span data-stu-id="d3b46-184">Fully qualified domain name (FQDN) of the device.</span></span> | <span data-ttu-id="d3b46-185">johnlaptop.europe.contoso.com</span><span class="sxs-lookup"><span data-stu-id="d3b46-185">johnlaptop.europe.contoso.com</span></span>
<span data-ttu-id="d3b46-186">IsApplicable</span><span class="sxs-lookup"><span data-stu-id="d3b46-186">IsApplicable</span></span> | <span data-ttu-id="d3b46-187">bool</span><span class="sxs-lookup"><span data-stu-id="d3b46-187">bool</span></span> | <span data-ttu-id="d3b46-188">구성 또는 정책을 적용할 수 있는지 여부를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="d3b46-188">Indicates whether the configuration or policy is applicable</span></span> | <span data-ttu-id="d3b46-189">true</span><span class="sxs-lookup"><span data-stu-id="d3b46-189">true</span></span>
<span data-ttu-id="d3b46-190">IsCompliant</span><span class="sxs-lookup"><span data-stu-id="d3b46-190">IsCompliant</span></span> | <span data-ttu-id="d3b46-191">bool</span><span class="sxs-lookup"><span data-stu-id="d3b46-191">bool</span></span> | <span data-ttu-id="d3b46-192">구성 또는 정책이 올바르게 구성되어 있는지 여부</span><span class="sxs-lookup"><span data-stu-id="d3b46-192">Indicates whether the configuration or policy is properly configured</span></span> | <span data-ttu-id="d3b46-193">false</span><span class="sxs-lookup"><span data-stu-id="d3b46-193">false</span></span>
<span data-ttu-id="d3b46-194">IsExpectedUserImpact</span><span class="sxs-lookup"><span data-stu-id="d3b46-194">IsExpectedUserImpact</span></span> | <span data-ttu-id="d3b46-195">bool</span><span class="sxs-lookup"><span data-stu-id="d3b46-195">bool</span></span> | <span data-ttu-id="d3b46-196">구성을 적용할 경우 사용자에게 영향을 줄지 여부를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="d3b46-196">Indicates whether there will be user impact if the configuration will be applied</span></span> | <span data-ttu-id="d3b46-197">true</span><span class="sxs-lookup"><span data-stu-id="d3b46-197">true</span></span>
<span data-ttu-id="d3b46-198">OSPlatform</span><span class="sxs-lookup"><span data-stu-id="d3b46-198">OSPlatform</span></span> | <span data-ttu-id="d3b46-199">문자열</span><span class="sxs-lookup"><span data-stu-id="d3b46-199">string</span></span> | <span data-ttu-id="d3b46-200">디바이스에서 실행되는 운영 체제의 플랫폼입니다.</span><span class="sxs-lookup"><span data-stu-id="d3b46-200">Platform of the operating system running on the device.</span></span> <span data-ttu-id="d3b46-201">이는 Windows 10 및 Windows 7과 같이 동일한 제품군 내의 변형을 포함하여 특정 운영 체제를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="d3b46-201">This indicates specific operating systems, including variations within the same family, such as Windows 10 and Windows 7.</span></span> <span data-ttu-id="d3b46-202">자세한 내용은 tvm 지원 운영 체제 및 플랫폼을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="d3b46-202">See tvm supported operating systems and platforms for details.</span></span> | <span data-ttu-id="d3b46-203">Windows 10</span><span class="sxs-lookup"><span data-stu-id="d3b46-203">Windows10</span></span>
<span data-ttu-id="d3b46-204">RbacGroupName</span><span class="sxs-lookup"><span data-stu-id="d3b46-204">RbacGroupName</span></span> | <span data-ttu-id="d3b46-205">문자열</span><span class="sxs-lookup"><span data-stu-id="d3b46-205">string</span></span> | <span data-ttu-id="d3b46-206">RBAC(역할 기반 액세스 제어) 그룹입니다.</span><span class="sxs-lookup"><span data-stu-id="d3b46-206">The role-based access control (RBAC) group.</span></span> <span data-ttu-id="d3b46-207">이 장치가 RBAC 그룹에 할당되지 않은 경우 값은 "지정되지 않았습니다."가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d3b46-207">If this device is not assigned to any RBAC group, the value will be “Unassigned.”</span></span> <span data-ttu-id="d3b46-208">조직에 RBAC 그룹이 없는 경우 값은 "없음"이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d3b46-208">If the organization doesn’t contain any RBAC groups, the value will be “None.”</span></span> | <span data-ttu-id="d3b46-209">서버</span><span class="sxs-lookup"><span data-stu-id="d3b46-209">Servers</span></span>
<span data-ttu-id="d3b46-210">RecommendationReference</span><span class="sxs-lookup"><span data-stu-id="d3b46-210">RecommendationReference</span></span> | <span data-ttu-id="d3b46-211">문자열</span><span class="sxs-lookup"><span data-stu-id="d3b46-211">string</span></span> | <span data-ttu-id="d3b46-212">이 소프트웨어와 관련된 권장 ID에 대한 참조입니다.</span><span class="sxs-lookup"><span data-stu-id="d3b46-212">A reference to the recommendation ID related to this software.</span></span> | <span data-ttu-id="d3b46-213">sca-_-scid-20000</span><span class="sxs-lookup"><span data-stu-id="d3b46-213">sca-_-scid-20000</span></span>
<span data-ttu-id="d3b46-214">타임스탬프</span><span class="sxs-lookup"><span data-stu-id="d3b46-214">Timestamp</span></span> | <span data-ttu-id="d3b46-215">문자열</span><span class="sxs-lookup"><span data-stu-id="d3b46-215">string</span></span> | <span data-ttu-id="d3b46-216">장치에서 구성을 마지막으로 본 시간</span><span class="sxs-lookup"><span data-stu-id="d3b46-216">Last time the configuration was seen on the device</span></span> | <span data-ttu-id="d3b46-217">2020-11-03 10:13:34.8476880</span><span class="sxs-lookup"><span data-stu-id="d3b46-217">2020-11-03 10:13:34.8476880</span></span>

### <a name="16-examples"></a><span data-ttu-id="d3b46-218">1.6 예제</span><span class="sxs-lookup"><span data-stu-id="d3b46-218">1.6 Examples</span></span>

#### <a name="161-request-example"></a><span data-ttu-id="d3b46-219">1.6.1 요청 예제</span><span class="sxs-lookup"><span data-stu-id="d3b46-219">1.6.1 Request example</span></span>

```http
GET https://api.securitycenter.microsoft.com/api/machines/SecureConfigurationsAssessmentByMachine?pageSize=5 
```

#### <a name="162-response-example"></a><span data-ttu-id="d3b46-220">1.6.2 응답 예제</span><span class="sxs-lookup"><span data-stu-id="d3b46-220">1.6.2 Response example</span></span>

```json
{
    "@odata.context": "api.securitycenter.microsoft.com/api/$metadata#Collection(microsoft.windowsDefenderATP.api.AssetConfiguration)",
    "value": [
        {
            "deviceId": "00013ee62c6b12345b10214e1801b217b50ab455c293d",
            "rbacGroupName": "hhh",
            "deviceName": "ComputerPII_5d96860d69c73fdd06fc8d1679e1eb73eceb8330",
            "osPlatform": "Windows10",
            "osVersion": "NT kernel 6.x",
            "timestamp": "2021-01-11 09:47:58.854",
            "configurationId": "scid-10000",
            "configurationCategory": "Network",
            "configurationSubcategory": "",
            "configurationImpact": 5,
            "isCompliant": true,
            "isApplicable": true,
            "isExpectedUserImpact": false,
            "configurationName": "Disable insecure administration protocol – Telnet",
            "recommendationReference": "sca-_-scid-10000"
        },
        {
            "deviceId": "0002a1be533813b9a8c6de739785365bce7910",
            "rbacGroupName": "hhh",
            "deviceName": null,
            "osPlatform": "Windows10",
            "osVersion": "10.0",
            "timestamp": "2021-01-11 09:47:58.854",
            "configurationId": "scid-20000",
            "configurationCategory": "Security controls",
            "configurationSubcategory": "Onboard Devices",
            "configurationImpact": 9,
            "isCompliant": false,
            "isApplicable": true,
            "isExpectedUserImpact": false,
            "configurationName": "Onboard devices to Microsoft Defender for Endpoint",
            "recommendationReference": "sca-_-scid-20000"
        },
        {
            "deviceId": "0002a1de123456a8c06de736785395d4ce7610",
            "rbacGroupName": "hhh",
            "deviceName": null,
            "osPlatform": "Windows10",
            "osVersion": "10.0",
            "timestamp": "2021-01-11 09:47:58.854",
            "configurationId": "scid-10000",
            "configurationCategory": "Network",
            "configurationSubcategory": "",
            "configurationImpact": 5,
            "isCompliant": true,
            "isApplicable": true,
            "isExpectedUserImpact": false,
            "configurationName": "Disable insecure administration protocol – Telnet",
            "recommendationReference": "sca-_-scid-10000"
        },
        {
            "deviceId": "00044f912345bdaf756492dbe6db733b6a9c59ab4",
            "rbacGroupName": "hhh",
            "deviceName": "ComputerPII_18663d45912eed224b2be2f5ea3142726e63f16a.DomainPII_21eeb80b086e76bdfa178eadfa25e8de9acfa346.corp.contoso.com",
            "osPlatform": "Windows10",
            "osVersion": "10.0.17763.1637",
            "timestamp": "2021-01-11 09:47:58.854",
            "configurationId": "scid-39",
            "configurationCategory": "OS",
            "configurationSubcategory": "",
            "configurationImpact": 5,
            "isCompliant": true,
            "isApplicable": true,
            "isExpectedUserImpact": false,
            "configurationName": "Enable 'Domain member: Digitally sign secure channel data (when possible)'",
            "recommendationReference": "sca-_-scid-39"
        },
        {
            "deviceId": "00044f912345daf759462bde6bd733d6a9c56ab4",
            "rbacGroupName": "hhh",
            "deviceName": "ComputerPII_18663b45612eeb224d2de2f5ea3142726e63f16a.DomainPII_21eed80d086e76dbfa178eadfa25e8be9acfa346.corp.contoso.com",
            "osPlatform": "Windows10",
            "osVersion": "10.0.17763.1637",
            "timestamp": "2021-01-11 09:47:58.854",
            "configurationId": "scid-6093",
            "configurationCategory": "Security controls",
            "configurationSubcategory": "Antivirus",
            "configurationImpact": 5,
            "isCompliant": false,
            "isApplicable": false,
            "isExpectedUserImpact": false,
            "configurationName": "Enable Microsoft Defender Antivirus real-time behavior monitoring for Linux",
            "recommendationReference": "sca-_-scid-6093"
        }
    ],
    "@odata.nextLink": "https://api.securitycenter.microsoft.com/api/machines/SecureConfigurationsAssessmentByMachine?pagesize=5&$skiptoken=eyJFeHBvcnREZWZpbml0aW9uIjp7IlRpbWVQYXRoIjoiMjAyMS0wMS0xMS8xMTAxLyJ9LCJFeHBvcnRGaWxlSW5kZXgiOjAsIkxpbmVTdG9wcGVkQXQiOjV9"
}
```

## <a name="2-export-secure-configuration-assessment-via-files"></a><span data-ttu-id="d3b46-221">2. 파일로 보안 구성 평가 내보내기</span><span class="sxs-lookup"><span data-stu-id="d3b46-221">2. Export secure configuration assessment (via files)</span></span>

### <a name="21-api-method-description"></a><span data-ttu-id="d3b46-222">2.1 API 메서드 설명</span><span class="sxs-lookup"><span data-stu-id="d3b46-222">2.1 API method description</span></span>

<span data-ttu-id="d3b46-223">이 API 응답은 노출된 디바이스에 대한 보안 구성 평가를 포함하며 DeviceId, ConfigurationId의 모든 고유 조합에 대한 항목을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="d3b46-223">This API response contains the Secure Configuration Assessment on your exposed devices, and returns an entry for every unique combination of DeviceId, ConfigurationId.</span></span>

#### <a name="212-limitations"></a><span data-ttu-id="d3b46-224">2.1.2 제한 사항</span><span class="sxs-lookup"><span data-stu-id="d3b46-224">2.1.2 Limitations</span></span>

<span data-ttu-id="d3b46-225">이 API의 속도 제한은 분당 5통, 시간당 20통입니다.</span><span class="sxs-lookup"><span data-stu-id="d3b46-225">Rate limitations for this API are 5 calls per minute and 20 calls per hour.</span></span>

### <a name="22-permissions"></a><span data-ttu-id="d3b46-226">2.2 사용 권한</span><span class="sxs-lookup"><span data-stu-id="d3b46-226">2.2 Permissions</span></span>

<span data-ttu-id="d3b46-227">이 API를 호출하려면 다음 권한 중 하나가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="d3b46-227">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="d3b46-228">사용 권한을 선택하는 방법을 포함하여 자세한 내용은 [Use Microsoft Defender for Endpoint API for details을 참조합니다.](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="d3b46-228">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs for details.](apis-intro.md)</span></span>

<span data-ttu-id="d3b46-229">사용 권한 유형</span><span class="sxs-lookup"><span data-stu-id="d3b46-229">Permission type</span></span> | <span data-ttu-id="d3b46-230">사용 권한</span><span class="sxs-lookup"><span data-stu-id="d3b46-230">Permission</span></span> | <span data-ttu-id="d3b46-231">사용 권한 표시 이름</span><span class="sxs-lookup"><span data-stu-id="d3b46-231">Permission display name</span></span>
---|---|---
<span data-ttu-id="d3b46-232">응용 프로그램</span><span class="sxs-lookup"><span data-stu-id="d3b46-232">Application</span></span> | <span data-ttu-id="d3b46-233">Vulnerability.Read.All</span><span class="sxs-lookup"><span data-stu-id="d3b46-233">Vulnerability.Read.All</span></span> | <span data-ttu-id="d3b46-234">\'"위협 및 취약성 관리" 취약성 정보 읽기\'</span><span class="sxs-lookup"><span data-stu-id="d3b46-234">\'Read "threat and vulnerability management" vulnerability information\'</span></span>
<span data-ttu-id="d3b46-235">위임(직장 또는 학교 계정)</span><span class="sxs-lookup"><span data-stu-id="d3b46-235">Delegated (work or school account)</span></span> | <span data-ttu-id="d3b46-236">Vulnerability.Read</span><span class="sxs-lookup"><span data-stu-id="d3b46-236">Vulnerability.Read</span></span> | <span data-ttu-id="d3b46-237">\'"위협 및 취약성 관리" 취약성 정보 읽기\'</span><span class="sxs-lookup"><span data-stu-id="d3b46-237">\'Read "threat and vulnerability management" vulnerability information\'</span></span>

### <a name="23-url"></a><span data-ttu-id="d3b46-238">2.3 URL</span><span class="sxs-lookup"><span data-stu-id="d3b46-238">2.3 URL</span></span>

```http
GET /api/machines/SecureConfigurationsAssessmentExport
```

### <a name="parameters"></a><span data-ttu-id="d3b46-239">매개 변수</span><span class="sxs-lookup"><span data-stu-id="d3b46-239">Parameters</span></span>

- <span data-ttu-id="d3b46-240">sasValidHours – 다운로드 URL이 유효한 시간(최대 24시간)입니다.</span><span class="sxs-lookup"><span data-stu-id="d3b46-240">sasValidHours – The number of hours that the download URLs will be valid for (Maximum 24 hours).</span></span>

### <a name="25-properties"></a><span data-ttu-id="d3b46-241">2.5 속성</span><span class="sxs-lookup"><span data-stu-id="d3b46-241">2.5 Properties</span></span>

>[!Note]
>
>- <span data-ttu-id="d3b46-242">파일은 여러 & Json 형식의 gzip 압축 파일 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="d3b46-242">The files are gzip compressed & in multiline Json format.</span></span>
>
>- <span data-ttu-id="d3b46-243">다운로드 URL은 3시간 동안만 유효합니다. 그렇지 않으면 매개 변수를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d3b46-243">The download URLs are only valid for 3 hours; otherwise you can use the parameter.</span></span>
>
>- <span data-ttu-id="d3b46-244">데이터의 최대 다운로드 속도를 위해 데이터가 있는 동일한 Azure 지역에서 다운로드하는지 확인하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d3b46-244">For maximum download speed of your data, you can make sure you are downloading from the same Azure region in which your data resides.</span></span>
>
<span data-ttu-id="d3b46-245">속성(ID)</span><span class="sxs-lookup"><span data-stu-id="d3b46-245">Property (ID)</span></span> | <span data-ttu-id="d3b46-246">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="d3b46-246">Data type</span></span> | <span data-ttu-id="d3b46-247">설명</span><span class="sxs-lookup"><span data-stu-id="d3b46-247">Description</span></span> | <span data-ttu-id="d3b46-248">반환된 값의 예</span><span class="sxs-lookup"><span data-stu-id="d3b46-248">Example of a returned value</span></span>
:---|:---|:---|:---
<span data-ttu-id="d3b46-249">파일 내보내기</span><span class="sxs-lookup"><span data-stu-id="d3b46-249">Export files</span></span> | <span data-ttu-id="d3b46-250">array \[ string\]</span><span class="sxs-lookup"><span data-stu-id="d3b46-250">array\[string\]</span></span> | <span data-ttu-id="d3b46-251">조직의 현재 스냅숏을 저장하는 파일의 다운로드 URL 목록</span><span class="sxs-lookup"><span data-stu-id="d3b46-251">A list of download URLs for files holding the current snapshot of the organization</span></span> | <span data-ttu-id="d3b46-252">[  Https://tvmexportstrstgeus.blob.core.windows.net/tvm-export...1”, “https://tvmexportstrstgeus.blob.core.windows.net/tvm-export...2” ]</span><span class="sxs-lookup"><span data-stu-id="d3b46-252">[  Https://tvmexportstrstgeus.blob.core.windows.net/tvm-export...1”, “https://tvmexportstrstgeus.blob.core.windows.net/tvm-export...2” ]</span></span>
<span data-ttu-id="d3b46-253">GeneratedTime</span><span class="sxs-lookup"><span data-stu-id="d3b46-253">GeneratedTime</span></span> | <span data-ttu-id="d3b46-254">문자열</span><span class="sxs-lookup"><span data-stu-id="d3b46-254">string</span></span> | <span data-ttu-id="d3b46-255">내보내기 생성 시간입니다.</span><span class="sxs-lookup"><span data-stu-id="d3b46-255">The time that the export was generated.</span></span> | <span data-ttu-id="d3b46-256">2021-05-20T08:00:00Z ]</span><span class="sxs-lookup"><span data-stu-id="d3b46-256">2021-05-20T08:00:00Z  ]</span></span>

### <a name="26-examples"></a><span data-ttu-id="d3b46-257">2.6 예제</span><span class="sxs-lookup"><span data-stu-id="d3b46-257">2.6 Examples</span></span>

#### <a name="261-request-example"></a><span data-ttu-id="d3b46-258">2.6.1 요청 예제</span><span class="sxs-lookup"><span data-stu-id="d3b46-258">2.6.1 Request example</span></span>

```http
GET https://api.securitycenter.microsoft.com/api/machines/SecureConfigurationsAssessmentExport
```

#### <a name="262-response-example"></a><span data-ttu-id="d3b46-259">2.6.2 응답 예제</span><span class="sxs-lookup"><span data-stu-id="d3b46-259">2.6.2 Response example</span></span>

```json
{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#contoso.windowsDefenderATP.api.ExportFilesResponse",
    "exportFiles": [
        "https://tvmexportstrstgeus.blob.core.windows.net/tvm-export/2021-01-11/1101/ScaExport/json/OrgId=12345678-195f-4223-9c7a-99fb420fd000/part-00393-e423630d-4c69-4490-8769-a4f5468c4f25.c000.json.gz?sv=2019-12-12&st=2021-01-11T11%3A55%3A51Z&se=2021-01-11T14%3A55%3A51Z&sr=b&sp=r&sig=...",
        "https://tvmexportstrstgeus.blob.core.windows.net/tvm-export/2021-01-11/1101/ScaExport/json/OrgId=12345678-195f-4223-9c7a-99fb420fd000/part-00394-e423630d-4c69-4490-8769-a4f5468c4f25.c000.json.gz?sv=2019-12-12&st=2021-01-11T11%3A55%3A51Z&se=2021-01-11T14%3A55%3A51Z&sr=b&sp=r&sig=...",
        "https://tvmexportstrstgeus.blob.core.windows.net/tvm-export/2021-01-11/1101/ScaExport/json/OrgId=12345678-195f-4223-9c7a-99fb420fd000/part-00394-e423630d-4c69-4490-8769-a4f5468c4f25.c001.json.gz?sv=2019-12-12&st=2021-01-11T11%3A55%3A51Z&se=2021-01-11T14%3A55%3A51Z&sr=b&sp=r&sig=..."
    ],
    "generatedTime": "2021-01-11T11:01:00Z"
}
```

## <a name="see-also"></a><span data-ttu-id="d3b46-260">참고 항목</span><span class="sxs-lookup"><span data-stu-id="d3b46-260">See also</span></span>

- [<span data-ttu-id="d3b46-261">장치당 평가 방법 및 속성 내보내기</span><span class="sxs-lookup"><span data-stu-id="d3b46-261">Export assessment methods and properties per device</span></span>](get-assessment-methods-properties.md)

- [<span data-ttu-id="d3b46-262">장치당 소프트웨어 인벤토리 평가 내보내기</span><span class="sxs-lookup"><span data-stu-id="d3b46-262">Export software inventory assessment per device</span></span>](get-assessment-software-inventory.md)

- [<span data-ttu-id="d3b46-263">장치당 소프트웨어 취약점 평가 내보내기</span><span class="sxs-lookup"><span data-stu-id="d3b46-263">Export software vulnerabilities assessment per device</span></span>](get-assessment-software-vulnerabilities.md)

<span data-ttu-id="d3b46-264">기타 관련</span><span class="sxs-lookup"><span data-stu-id="d3b46-264">Other related</span></span>

- [<span data-ttu-id="d3b46-265">위험 기반 위협 & 취약성 관리</span><span class="sxs-lookup"><span data-stu-id="d3b46-265">Risk-based threat & vulnerability management</span></span>](next-gen-threat-and-vuln-mgt.md)

- [<span data-ttu-id="d3b46-266">조직의 취약성</span><span class="sxs-lookup"><span data-stu-id="d3b46-266">Vulnerabilities in your organization</span></span>](tvm-weaknesses.md)
