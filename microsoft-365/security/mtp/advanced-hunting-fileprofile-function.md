---
title: Microsoft 365 Defender에 대한 고급 헌팅의 FileProfile() 기능
description: FileProfile()을 사용하여 고급 헌팅 쿼리 결과의 파일에 대한 정보를 보강하는 방법을 학습
keywords: 고급 헌팅, 위협 헌팅, 사이버 위협 헌팅, Microsoft 위협 방지, microsoft 365, mtp, m365, 검색, 쿼리, 원격 분석, schema reference, kusto, FileProfile, file profile, function, enrichment
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
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: 68196f126ac470088d7ba5e2923accc492d8764c
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/22/2021
ms.locfileid: "49929553"
---
# <a name="fileprofile"></a><span data-ttu-id="95e22-104">FileProfile()</span><span class="sxs-lookup"><span data-stu-id="95e22-104">FileProfile()</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="95e22-105">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="95e22-105">**Applies to:**</span></span>
- <span data-ttu-id="95e22-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="95e22-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="95e22-107">이 함수는 쿼리에서 찾은 파일에 다음 데이터를 추가하는 고급 헌팅의 `FileProfile()` 향상 함수입니다. [](advanced-hunting-overview.md)</span><span class="sxs-lookup"><span data-stu-id="95e22-107">The `FileProfile()` function is an enrichment function in [advanced hunting](advanced-hunting-overview.md) that adds the following data to files found by the query.</span></span>

| <span data-ttu-id="95e22-108">열</span><span class="sxs-lookup"><span data-stu-id="95e22-108">Column</span></span> | <span data-ttu-id="95e22-109">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="95e22-109">Data type</span></span> | <span data-ttu-id="95e22-110">설명</span><span class="sxs-lookup"><span data-stu-id="95e22-110">Description</span></span> |
|------------|-------------|-------------|
| <span data-ttu-id="95e22-111">SHA1</span><span class="sxs-lookup"><span data-stu-id="95e22-111">SHA1</span></span> | <span data-ttu-id="95e22-112">문자열</span><span class="sxs-lookup"><span data-stu-id="95e22-112">string</span></span> | <span data-ttu-id="95e22-113">기록된 조치가 적용된 파일의 SHA-1</span><span class="sxs-lookup"><span data-stu-id="95e22-113">SHA-1 of the file that the recorded action was applied to</span></span> |
| <span data-ttu-id="95e22-114">SHA256</span><span class="sxs-lookup"><span data-stu-id="95e22-114">SHA256</span></span> | <span data-ttu-id="95e22-115">문자열</span><span class="sxs-lookup"><span data-stu-id="95e22-115">string</span></span> | <span data-ttu-id="95e22-116">기록된 작업이 적용된 파일의 SHA-256</span><span class="sxs-lookup"><span data-stu-id="95e22-116">SHA-256 of the file that the recorded action was applied to</span></span> |
| <span data-ttu-id="95e22-117">MD5</span><span class="sxs-lookup"><span data-stu-id="95e22-117">MD5</span></span> | <span data-ttu-id="95e22-118">문자열</span><span class="sxs-lookup"><span data-stu-id="95e22-118">string</span></span> | <span data-ttu-id="95e22-119">기록된 작업이 적용된 파일의 MD5 해시입니다.</span><span class="sxs-lookup"><span data-stu-id="95e22-119">MD5 hash of the file that the recorded action was applied to</span></span> |
| <span data-ttu-id="95e22-120">FileSize</span><span class="sxs-lookup"><span data-stu-id="95e22-120">FileSize</span></span> | <span data-ttu-id="95e22-121">int</span><span class="sxs-lookup"><span data-stu-id="95e22-121">int</span></span> | <span data-ttu-id="95e22-122">파일 크기(bytes)입니다.</span><span class="sxs-lookup"><span data-stu-id="95e22-122">Size of the file in bytes</span></span> |
| <span data-ttu-id="95e22-123">GlobalPrevalence</span><span class="sxs-lookup"><span data-stu-id="95e22-123">GlobalPrevalence</span></span> | <span data-ttu-id="95e22-124">int</span><span class="sxs-lookup"><span data-stu-id="95e22-124">int</span></span> | <span data-ttu-id="95e22-125">Microsoft에서 전역적으로 관찰한 엔터티의 인스턴스 수</span><span class="sxs-lookup"><span data-stu-id="95e22-125">Number of instances of the entity observed by Microsoft globally</span></span> |
| <span data-ttu-id="95e22-126">GlobalFirstSeen</span><span class="sxs-lookup"><span data-stu-id="95e22-126">GlobalFirstSeen</span></span> | <span data-ttu-id="95e22-127">datetime</span><span class="sxs-lookup"><span data-stu-id="95e22-127">datetime</span></span> | <span data-ttu-id="95e22-128">Microsoft에서 엔터티를 전역적으로 처음 관찰한 날짜 및 시간</span><span class="sxs-lookup"><span data-stu-id="95e22-128">Date and time when the entity was first observed by Microsoft globally</span></span> |
| <span data-ttu-id="95e22-129">GlobalLastSeen</span><span class="sxs-lookup"><span data-stu-id="95e22-129">GlobalLastSeen</span></span> | <span data-ttu-id="95e22-130">datetime</span><span class="sxs-lookup"><span data-stu-id="95e22-130">datetime</span></span> | <span data-ttu-id="95e22-131">Microsoft에서 엔터티가 마지막으로 관찰된 날짜 및 시간</span><span class="sxs-lookup"><span data-stu-id="95e22-131">Date and time when the entity was last observed by Microsoft globally</span></span> |
| <span data-ttu-id="95e22-132">서명자</span><span class="sxs-lookup"><span data-stu-id="95e22-132">Signer</span></span> | <span data-ttu-id="95e22-133">문자열</span><span class="sxs-lookup"><span data-stu-id="95e22-133">string</span></span> | <span data-ttu-id="95e22-134">파일의 서명자에 대한 정보</span><span class="sxs-lookup"><span data-stu-id="95e22-134">Information about the signer of the file</span></span> |
| <span data-ttu-id="95e22-135">발급자</span><span class="sxs-lookup"><span data-stu-id="95e22-135">Issuer</span></span> | <span data-ttu-id="95e22-136">문자열</span><span class="sxs-lookup"><span data-stu-id="95e22-136">string</span></span> | <span data-ttu-id="95e22-137">CA(인증 기관) 발급에 대한 정보</span><span class="sxs-lookup"><span data-stu-id="95e22-137">Information about the issuing certificate authority (CA)</span></span> |
| <span data-ttu-id="95e22-138">SignerHash</span><span class="sxs-lookup"><span data-stu-id="95e22-138">SignerHash</span></span> | <span data-ttu-id="95e22-139">문자열</span><span class="sxs-lookup"><span data-stu-id="95e22-139">string</span></span> | <span data-ttu-id="95e22-140">서명자를 식별하는 고유 해시 값</span><span class="sxs-lookup"><span data-stu-id="95e22-140">Unique hash value identifying the signer</span></span> |
| <span data-ttu-id="95e22-141">IsCertificateValid</span><span class="sxs-lookup"><span data-stu-id="95e22-141">IsCertificateValid</span></span> | <span data-ttu-id="95e22-142">부울</span><span class="sxs-lookup"><span data-stu-id="95e22-142">boolean</span></span> | <span data-ttu-id="95e22-143">파일에 서명하는 데 사용된 인증서가 유효한지 여부</span><span class="sxs-lookup"><span data-stu-id="95e22-143">Whether the certificate used to sign the file is valid</span></span> |
| <span data-ttu-id="95e22-144">IsRootSignerMicrosoft</span><span class="sxs-lookup"><span data-stu-id="95e22-144">IsRootSignerMicrosoft</span></span> | <span data-ttu-id="95e22-145">부울</span><span class="sxs-lookup"><span data-stu-id="95e22-145">boolean</span></span> | <span data-ttu-id="95e22-146">루트 인증서의 서명자인지 여부를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="95e22-146">Indicates whether the signer of the root certificate is Microsoft</span></span> |
| <span data-ttu-id="95e22-147">IsExecutable</span><span class="sxs-lookup"><span data-stu-id="95e22-147">IsExecutable</span></span> | <span data-ttu-id="95e22-148">부울</span><span class="sxs-lookup"><span data-stu-id="95e22-148">boolean</span></span> | <span data-ttu-id="95e22-149">파일이 PE(Portable Executable) 파일인지 여부</span><span class="sxs-lookup"><span data-stu-id="95e22-149">Whether the file is a Portable Executable (PE) file</span></span> |
| <span data-ttu-id="95e22-150">ThreatName</span><span class="sxs-lookup"><span data-stu-id="95e22-150">ThreatName</span></span> | <span data-ttu-id="95e22-151">문자열</span><span class="sxs-lookup"><span data-stu-id="95e22-151">string</span></span> | <span data-ttu-id="95e22-152">맬웨어 또는 기타 위협이 발견된 검색 이름</span><span class="sxs-lookup"><span data-stu-id="95e22-152">Detection name for any malware or other threats found</span></span> |
| <span data-ttu-id="95e22-153">게시자</span><span class="sxs-lookup"><span data-stu-id="95e22-153">Publisher</span></span> | <span data-ttu-id="95e22-154">문자열</span><span class="sxs-lookup"><span data-stu-id="95e22-154">string</span></span> | <span data-ttu-id="95e22-155">파일을 게시한 조직의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="95e22-155">Name of the organization that published the file</span></span> |
| <span data-ttu-id="95e22-156">SoftwareName</span><span class="sxs-lookup"><span data-stu-id="95e22-156">SoftwareName</span></span> | <span data-ttu-id="95e22-157">문자열</span><span class="sxs-lookup"><span data-stu-id="95e22-157">string</span></span> | <span data-ttu-id="95e22-158">소프트웨어 제품의 이름</span><span class="sxs-lookup"><span data-stu-id="95e22-158">Name of the software product</span></span> |

## <a name="syntax"></a><span data-ttu-id="95e22-159">구문</span><span class="sxs-lookup"><span data-stu-id="95e22-159">Syntax</span></span>

```kusto
invoke FileProfile(x,y)
```

## <a name="arguments"></a><span data-ttu-id="95e22-160">인수</span><span class="sxs-lookup"><span data-stu-id="95e22-160">Arguments</span></span>

- <span data-ttu-id="95e22-161">**x**-사용할 파일 ID 열: `SHA1` , , 또는 ; `SHA256` `InitiatingProcessSHA1` `InitiatingProcessSHA256` 함수가 `SHA1` 선택하지 않은 경우 사용</span><span class="sxs-lookup"><span data-stu-id="95e22-161">**x**—file ID column to use: `SHA1`, `SHA256`, `InitiatingProcessSHA1`, or `InitiatingProcessSHA256`; function uses `SHA1` if unspecified</span></span>
- <span data-ttu-id="95e22-162">**y**-보강할 레코드 수로 제한, 1-1000; 함수에서 100을 사용하는 경우</span><span class="sxs-lookup"><span data-stu-id="95e22-162">**y**—limit to the number of records to enrich, 1-1000; function uses 100 if unspecified</span></span>

## <a name="examples"></a><span data-ttu-id="95e22-163">예</span><span class="sxs-lookup"><span data-stu-id="95e22-163">Examples</span></span>

### <a name="project-only-the-sha1-column-and-enrich-it"></a><span data-ttu-id="95e22-164">SHA1 열만 프로젝트하고 보강</span><span class="sxs-lookup"><span data-stu-id="95e22-164">Project only the SHA1 column and enrich it</span></span>

```kusto
DeviceFileEvents
| where isnotempty(SHA1) and Timestamp > ago(1d)
| take 10
| project SHA1
| invoke FileProfile()
```

### <a name="enrich-the-first-500-records-and-list-low-prevalence-files"></a><span data-ttu-id="95e22-165">처음 500개 레코드 보강 및 낮은 보전 파일 목록</span><span class="sxs-lookup"><span data-stu-id="95e22-165">Enrich the first 500 records and list low-prevalence files</span></span>

```kusto
DeviceFileEvents
| where ActionType == "FileCreated" and Timestamp > ago(1d)
| project CreatedOn = Timestamp, FileName, FolderPath, SHA1
| invoke FileProfile("SHA1", 500) 
| where GlobalPrevalence < 15
```

## <a name="related-topics"></a><span data-ttu-id="95e22-166">관련 항목</span><span class="sxs-lookup"><span data-stu-id="95e22-166">Related topics</span></span>
- [<span data-ttu-id="95e22-167">고급 헌팅 개요</span><span class="sxs-lookup"><span data-stu-id="95e22-167">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="95e22-168">쿼리 언어 배우기</span><span class="sxs-lookup"><span data-stu-id="95e22-168">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="95e22-169">스키마의 이해</span><span class="sxs-lookup"><span data-stu-id="95e22-169">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="95e22-170">더 많은 쿼리 예제 보기</span><span class="sxs-lookup"><span data-stu-id="95e22-170">Get more query examples</span></span>](advanced-hunting-shared-queries.md)
