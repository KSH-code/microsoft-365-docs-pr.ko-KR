---
title: Microsoft 365 Defender에 대한 고급 헌팅의 FileProfile() 기능
description: FileProfile()을 사용하여 고급 헌팅 쿼리 결과의 파일에 대한 정보를 강화하는 방법에 대해 자세히 알아보기
keywords: 고급 헌팅, 위협 헌팅, 사이버 위협 헌팅, Microsoft 위협 방지, microsoft 365, mtp, m365, 검색, 쿼리, 원격 분석, schema 참조, kusto, FileProfile, 파일 프로필, 기능, 향상
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: lomayor
author: lomayor
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: a9ca0af0c522205309ffdcbfd1ac28638bd197c7
ms.sourcegitcommit: ef98b8a18d275e5b5961e63d2b0743d046321737
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/26/2021
ms.locfileid: "51382796"
---
# <a name="fileprofile"></a><span data-ttu-id="8d23b-104">FileProfile()</span><span class="sxs-lookup"><span data-stu-id="8d23b-104">FileProfile()</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="8d23b-105">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="8d23b-105">**Applies to:**</span></span>
- <span data-ttu-id="8d23b-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="8d23b-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="8d23b-107">이 함수는 쿼리에서 찾은 파일에 다음 데이터를 추가하는 고급 헌팅의 `FileProfile()` 향상 함수입니다. [](advanced-hunting-overview.md)</span><span class="sxs-lookup"><span data-stu-id="8d23b-107">The `FileProfile()` function is an enrichment function in [advanced hunting](advanced-hunting-overview.md) that adds the following data to files found by the query.</span></span>

| <span data-ttu-id="8d23b-108">열</span><span class="sxs-lookup"><span data-stu-id="8d23b-108">Column</span></span> | <span data-ttu-id="8d23b-109">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="8d23b-109">Data type</span></span> | <span data-ttu-id="8d23b-110">설명</span><span class="sxs-lookup"><span data-stu-id="8d23b-110">Description</span></span> |
|------------|---------------|-------------|
| `SHA1` | <span data-ttu-id="8d23b-111">문자열</span><span class="sxs-lookup"><span data-stu-id="8d23b-111">string</span></span> | <span data-ttu-id="8d23b-112">기록된 조치가 적용된 파일의 SHA-1</span><span class="sxs-lookup"><span data-stu-id="8d23b-112">SHA-1 of the file that the recorded action was applied to</span></span> |
| `SHA256` | <span data-ttu-id="8d23b-113">문자열</span><span class="sxs-lookup"><span data-stu-id="8d23b-113">string</span></span> | <span data-ttu-id="8d23b-114">기록된 작업이 적용된 파일의 SHA-256</span><span class="sxs-lookup"><span data-stu-id="8d23b-114">SHA-256 of the file that the recorded action was applied to</span></span> |
| `MD5` | <span data-ttu-id="8d23b-115">문자열</span><span class="sxs-lookup"><span data-stu-id="8d23b-115">string</span></span> | <span data-ttu-id="8d23b-116">기록된 작업이 적용된 파일의 MD5 해시입니다.</span><span class="sxs-lookup"><span data-stu-id="8d23b-116">MD5 hash of the file that the recorded action was applied to</span></span> |
| `FileSize` | <span data-ttu-id="8d23b-117">int</span><span class="sxs-lookup"><span data-stu-id="8d23b-117">int</span></span> | <span data-ttu-id="8d23b-118">파일 크기(bytes)입니다.</span><span class="sxs-lookup"><span data-stu-id="8d23b-118">Size of the file in bytes</span></span> |
| `GlobalPrevalence` | <span data-ttu-id="8d23b-119">int</span><span class="sxs-lookup"><span data-stu-id="8d23b-119">int</span></span> | <span data-ttu-id="8d23b-120">Microsoft에서 전역적으로 관찰하는 엔터티의 인스턴스 수</span><span class="sxs-lookup"><span data-stu-id="8d23b-120">Number of instances of the entity observed by Microsoft globally</span></span> |
| `GlobalFirstSeen` | <span data-ttu-id="8d23b-121">datetime</span><span class="sxs-lookup"><span data-stu-id="8d23b-121">datetime</span></span> | <span data-ttu-id="8d23b-122">Microsoft에서 엔터티를 전역적으로 처음 관찰한 날짜 및 시간</span><span class="sxs-lookup"><span data-stu-id="8d23b-122">Date and time when the entity was first observed by Microsoft globally</span></span> |
| `GlobalLastSeen` | <span data-ttu-id="8d23b-123">datetime</span><span class="sxs-lookup"><span data-stu-id="8d23b-123">datetime</span></span> | <span data-ttu-id="8d23b-124">Microsoft에서 엔터티를 마지막으로 관찰한 날짜 및 시간</span><span class="sxs-lookup"><span data-stu-id="8d23b-124">Date and time when the entity was last observed by Microsoft globally</span></span> |
| `Signer` | <span data-ttu-id="8d23b-125">문자열</span><span class="sxs-lookup"><span data-stu-id="8d23b-125">string</span></span> | <span data-ttu-id="8d23b-126">파일의 서명자에 대한 정보</span><span class="sxs-lookup"><span data-stu-id="8d23b-126">Information about the signer of the file</span></span> |
| `Issuer` | <span data-ttu-id="8d23b-127">문자열</span><span class="sxs-lookup"><span data-stu-id="8d23b-127">string</span></span> | <span data-ttu-id="8d23b-128">발급 CA(인증 기관)에 대한 정보</span><span class="sxs-lookup"><span data-stu-id="8d23b-128">Information about the issuing certificate authority (CA)</span></span> |
| `SignerHash` | <span data-ttu-id="8d23b-129">문자열</span><span class="sxs-lookup"><span data-stu-id="8d23b-129">string</span></span> | <span data-ttu-id="8d23b-130">서명자를 식별하는 고유 해시 값</span><span class="sxs-lookup"><span data-stu-id="8d23b-130">Unique hash value identifying the signer</span></span> |
| `IsCertificateValid` | <span data-ttu-id="8d23b-131">부울</span><span class="sxs-lookup"><span data-stu-id="8d23b-131">boolean</span></span> | <span data-ttu-id="8d23b-132">파일에 서명하는 데 사용된 인증서가 유효한지 여부</span><span class="sxs-lookup"><span data-stu-id="8d23b-132">Whether the certificate used to sign the file is valid</span></span> |
| `IsRootSignerMicrosoft` | <span data-ttu-id="8d23b-133">부울</span><span class="sxs-lookup"><span data-stu-id="8d23b-133">boolean</span></span> | <span data-ttu-id="8d23b-134">루트 인증서의 서명자인지 여부를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="8d23b-134">Indicates whether the signer of the root certificate is Microsoft</span></span> |
| `SignatureState` | <span data-ttu-id="8d23b-135">문자열</span><span class="sxs-lookup"><span data-stu-id="8d23b-135">string</span></span> | <span data-ttu-id="8d23b-136">파일 서명 상태: SignedValid - 파일이 유효한 서명으로 서명되었습니다. SignedInvalid - 파일이 서명되지만 인증서가 잘못되었거나 서명되지 않았습니다. 파일이 서명되지 않았고 알 수 없음 - 파일에 대한 정보를 검색할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="8d23b-136">State of the file signature: SignedValid - the file is signed with a valid signature, SignedInvalid - the file is signed but the certificate is invalid, Unsigned - the file is not signed, Unknown - information about the file cannot be retrieved</span></span>
| `IsExecutable` | <span data-ttu-id="8d23b-137">부울</span><span class="sxs-lookup"><span data-stu-id="8d23b-137">boolean</span></span> | <span data-ttu-id="8d23b-138">파일이 PE(Portable Executable) 파일인지 여부</span><span class="sxs-lookup"><span data-stu-id="8d23b-138">Whether the file is a Portable Executable (PE) file</span></span> |
| `ThreatName` | <span data-ttu-id="8d23b-139">문자열</span><span class="sxs-lookup"><span data-stu-id="8d23b-139">string</span></span> | <span data-ttu-id="8d23b-140">발견된 맬웨어 또는 기타 위협에 대한 검색 이름</span><span class="sxs-lookup"><span data-stu-id="8d23b-140">Detection name for any malware or other threats found</span></span> |
| `Publisher` | <span data-ttu-id="8d23b-141">문자열</span><span class="sxs-lookup"><span data-stu-id="8d23b-141">string</span></span> | <span data-ttu-id="8d23b-142">파일을 게시한 조직의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="8d23b-142">Name of the organization that published the file</span></span> |
| `SoftwareName` | <span data-ttu-id="8d23b-143">문자열</span><span class="sxs-lookup"><span data-stu-id="8d23b-143">string</span></span> | <span data-ttu-id="8d23b-144">소프트웨어 제품의 이름</span><span class="sxs-lookup"><span data-stu-id="8d23b-144">Name of the software product</span></span> |

## <a name="syntax"></a><span data-ttu-id="8d23b-145">구문</span><span class="sxs-lookup"><span data-stu-id="8d23b-145">Syntax</span></span>

```kusto
invoke FileProfile(x,y)
```

## <a name="arguments"></a><span data-ttu-id="8d23b-146">인수</span><span class="sxs-lookup"><span data-stu-id="8d23b-146">Arguments</span></span>

- <span data-ttu-id="8d23b-147">**x**-사용할 파일 ID 열: `SHA1` , , 또는 ; `SHA256` `InitiatingProcessSHA1` `InitiatingProcessSHA256` 함수가 `SHA1` 선택하지 않은 경우 사용</span><span class="sxs-lookup"><span data-stu-id="8d23b-147">**x**—file ID column to use: `SHA1`, `SHA256`, `InitiatingProcessSHA1`, or `InitiatingProcessSHA256`; function uses `SHA1` if unspecified</span></span>
- <span data-ttu-id="8d23b-148">**y**- 보강할 레코드 수로 제한, 1-1000; 함수가 100을 사용하는 경우</span><span class="sxs-lookup"><span data-stu-id="8d23b-148">**y**—limit to the number of records to enrich, 1-1000; function uses 100 if unspecified</span></span>


>[!TIP]
> <span data-ttu-id="8d23b-149">향상 함수는 사용할 수 있는 경우만 추가 정보를 보여 주게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8d23b-149">Enrichment functions will show supplemental information only when they are available.</span></span> <span data-ttu-id="8d23b-150">정보의 가용성은 다양한 요소에 따라 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="8d23b-150">Availability of information is varied and depends on a lot of factors.</span></span> <span data-ttu-id="8d23b-151">쿼리에서 FileProfile()을 사용하거나 사용자 지정 검색을 만들 때 이를 고려해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8d23b-151">Make sure to consider this when using FileProfile() in your queries or in creating custom detections.</span></span> <span data-ttu-id="8d23b-152">최상의 결과를 얻기 위해 FileProfile() 함수를 SHA1과 함께 사용하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="8d23b-152">For best results, we recommend using the FileProfile() function with SHA1.</span></span>

## <a name="examples"></a><span data-ttu-id="8d23b-153">예</span><span class="sxs-lookup"><span data-stu-id="8d23b-153">Examples</span></span>

### <a name="project-only-the-sha1-column-and-enrich-it"></a><span data-ttu-id="8d23b-154">SHA1 열만 프로젝트하고 강화</span><span class="sxs-lookup"><span data-stu-id="8d23b-154">Project only the SHA1 column and enrich it</span></span>

```kusto
DeviceFileEvents
| where isnotempty(SHA1) and Timestamp > ago(1d)
| take 10
| project SHA1
| invoke FileProfile()
```

### <a name="enrich-the-first-500-records-and-list-low-prevalence-files"></a><span data-ttu-id="8d23b-155">처음 500개 레코드 보강 및 낮은 보전 파일 목록</span><span class="sxs-lookup"><span data-stu-id="8d23b-155">Enrich the first 500 records and list low-prevalence files</span></span>

```kusto
DeviceFileEvents
| where ActionType == "FileCreated" and Timestamp > ago(1d)
| project CreatedOn = Timestamp, FileName, FolderPath, SHA1
| invoke FileProfile("SHA1", 500) 
| where GlobalPrevalence < 15
```

## <a name="related-topics"></a><span data-ttu-id="8d23b-156">관련 항목</span><span class="sxs-lookup"><span data-stu-id="8d23b-156">Related topics</span></span>
- [<span data-ttu-id="8d23b-157">고급 헌팅 개요</span><span class="sxs-lookup"><span data-stu-id="8d23b-157">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="8d23b-158">쿼리 언어 배우기</span><span class="sxs-lookup"><span data-stu-id="8d23b-158">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="8d23b-159">스키마의 이해</span><span class="sxs-lookup"><span data-stu-id="8d23b-159">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="8d23b-160">더 많은 쿼리 예제 보기</span><span class="sxs-lookup"><span data-stu-id="8d23b-160">Get more query examples</span></span>](advanced-hunting-shared-queries.md)
