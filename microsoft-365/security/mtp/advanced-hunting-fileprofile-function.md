---
title: Microsoft Threat Protection의 FileProfile () 함수 고급 구하기
description: FileProfile ()을 사용 하 여 고급 구하기 쿼리 결과의 파일에 대 한 정보를 보강 하는 방법을 알아봅니다.
keywords: 고급 구하기, 위협 검색, 사이버 위협 사냥, microsoft threat protection, microsoft 365, mtp, m365, 검색, 쿼리, 원격 분석, 스키마 참조, kusto, FileProfile, file profile, function, 향상
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: microsoft-365-enterprise
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
ms.collection: M365-security-compliance
ms.topic: article
ms.openlocfilehash: 039b9dc038cd1a1645aee2289f3bdb389eb3f426
ms.sourcegitcommit: eee4f651bd51d5aedd64e42d02bfed8ccb9be4cd
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/02/2020
ms.locfileid: "44515943"
---
# <a name="fileprofile"></a><span data-ttu-id="99214-104">FileProfile ()</span><span class="sxs-lookup"><span data-stu-id="99214-104">FileProfile()</span></span>

<span data-ttu-id="99214-105">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="99214-105">**Applies to:**</span></span>
- <span data-ttu-id="99214-106">Microsoft 위협 방지</span><span class="sxs-lookup"><span data-stu-id="99214-106">Microsoft Threat Protection</span></span>

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

<span data-ttu-id="99214-107">`FileProfile()`이 함수는 [고급](advanced-hunting-overview.md) 검색에서 쿼리에 의해 찾은 파일에 다음 데이터를 추가 하는 향상 함수입니다.</span><span class="sxs-lookup"><span data-stu-id="99214-107">The `FileProfile()` function is an enrichment function in [advanced hunting](advanced-hunting-overview.md) that adds the following data to files found by the query.</span></span>

| <span data-ttu-id="99214-108">열</span><span class="sxs-lookup"><span data-stu-id="99214-108">Column</span></span> | <span data-ttu-id="99214-109">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="99214-109">Data type</span></span> | <span data-ttu-id="99214-110">설명</span><span class="sxs-lookup"><span data-stu-id="99214-110">Description</span></span> |
|------------|-------------|-------------|
| <span data-ttu-id="99214-111">SHA1</span><span class="sxs-lookup"><span data-stu-id="99214-111">SHA1</span></span> | <span data-ttu-id="99214-112">문자열</span><span class="sxs-lookup"><span data-stu-id="99214-112">string</span></span> | <span data-ttu-id="99214-113">기록된 조치가 적용된 파일의 SHA-1</span><span class="sxs-lookup"><span data-stu-id="99214-113">SHA-1 of the file that the recorded action was applied to</span></span> |
| <span data-ttu-id="99214-114">SHA256</span><span class="sxs-lookup"><span data-stu-id="99214-114">SHA256</span></span> | <span data-ttu-id="99214-115">문자열</span><span class="sxs-lookup"><span data-stu-id="99214-115">string</span></span> | <span data-ttu-id="99214-116">기록 된 작업이 적용 된 파일의 SHA-256</span><span class="sxs-lookup"><span data-stu-id="99214-116">SHA-256 of the file that the recorded action was applied to</span></span> |
| <span data-ttu-id="99214-117">MD5</span><span class="sxs-lookup"><span data-stu-id="99214-117">MD5</span></span> | <span data-ttu-id="99214-118">문자열</span><span class="sxs-lookup"><span data-stu-id="99214-118">string</span></span> | <span data-ttu-id="99214-119">기록 된 작업이 적용 된 파일의 MD5 해시</span><span class="sxs-lookup"><span data-stu-id="99214-119">MD5 hash of the file that the recorded action was applied to</span></span> |
| <span data-ttu-id="99214-120">FileSize</span><span class="sxs-lookup"><span data-stu-id="99214-120">FileSize</span></span> | <span data-ttu-id="99214-121">int</span><span class="sxs-lookup"><span data-stu-id="99214-121">int</span></span> | <span data-ttu-id="99214-122">파일 크기 (바이트)입니다.</span><span class="sxs-lookup"><span data-stu-id="99214-122">Size of the file in bytes</span></span> |
| <span data-ttu-id="99214-123">GlobalPrevalence</span><span class="sxs-lookup"><span data-stu-id="99214-123">GlobalPrevalence</span></span> | <span data-ttu-id="99214-124">int</span><span class="sxs-lookup"><span data-stu-id="99214-124">int</span></span> | <span data-ttu-id="99214-125">Microsoft에서 전역적으로 관찰 한 엔터티 인스턴스 수</span><span class="sxs-lookup"><span data-stu-id="99214-125">Number of instances of the entity observed by Microsoft globally</span></span> |
| <span data-ttu-id="99214-126">GlobalFirstSeen 경우</span><span class="sxs-lookup"><span data-stu-id="99214-126">GlobalFirstSeen</span></span> | <span data-ttu-id="99214-127">datetime</span><span class="sxs-lookup"><span data-stu-id="99214-127">datetime</span></span> | <span data-ttu-id="99214-128">Microsoft에서 처음으로 엔터티를 관측 한 날짜 및 시간입니다.</span><span class="sxs-lookup"><span data-stu-id="99214-128">Date and time when the entity was first observed by Microsoft globally</span></span> |
| <span data-ttu-id="99214-129">GlobalLastSeen</span><span class="sxs-lookup"><span data-stu-id="99214-129">GlobalLastSeen</span></span> | <span data-ttu-id="99214-130">datetime</span><span class="sxs-lookup"><span data-stu-id="99214-130">datetime</span></span> | <span data-ttu-id="99214-131">Microsoft에서 전역적으로 엔터티를 마지막으로 관찰 한 날짜 및 시간입니다.</span><span class="sxs-lookup"><span data-stu-id="99214-131">Date and time when the entity was last observed by Microsoft globally</span></span> |
| <span data-ttu-id="99214-132">받은</span><span class="sxs-lookup"><span data-stu-id="99214-132">Signer</span></span> | <span data-ttu-id="99214-133">문자열</span><span class="sxs-lookup"><span data-stu-id="99214-133">string</span></span> | <span data-ttu-id="99214-134">파일의 서명자에 대 한 정보</span><span class="sxs-lookup"><span data-stu-id="99214-134">Information about the signer of the file</span></span> |
| <span data-ttu-id="99214-135">발급</span><span class="sxs-lookup"><span data-stu-id="99214-135">Issuer</span></span> | <span data-ttu-id="99214-136">문자열</span><span class="sxs-lookup"><span data-stu-id="99214-136">string</span></span> | <span data-ttu-id="99214-137">발급 CA (인증 기관)에 대 한 정보</span><span class="sxs-lookup"><span data-stu-id="99214-137">Information about the issuing certificate authority (CA)</span></span> |
| <span data-ttu-id="99214-138">SignerHash</span><span class="sxs-lookup"><span data-stu-id="99214-138">SignerHash</span></span> | <span data-ttu-id="99214-139">문자열</span><span class="sxs-lookup"><span data-stu-id="99214-139">string</span></span> | <span data-ttu-id="99214-140">서명자를 식별 하는 고유한 해시 값</span><span class="sxs-lookup"><span data-stu-id="99214-140">Unique hash value identifying the signer</span></span> |
| <span data-ttu-id="99214-141">IsCertificateValid</span><span class="sxs-lookup"><span data-stu-id="99214-141">IsCertificateValid</span></span> | <span data-ttu-id="99214-142">부울</span><span class="sxs-lookup"><span data-stu-id="99214-142">boolean</span></span> | <span data-ttu-id="99214-143">파일 서명에 사용 된 인증서가 유효한 지 여부</span><span class="sxs-lookup"><span data-stu-id="99214-143">Whether the certificate used to sign the file is valid</span></span> |
| <span data-ttu-id="99214-144">IsRootSignerMicrosoft</span><span class="sxs-lookup"><span data-stu-id="99214-144">IsRootSignerMicrosoft</span></span> | <span data-ttu-id="99214-145">부울</span><span class="sxs-lookup"><span data-stu-id="99214-145">boolean</span></span> | <span data-ttu-id="99214-146">루트 인증서의 서명자가 Microsoft 인지 여부를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="99214-146">Indicates whether the signer of the root certificate is Microsoft</span></span> |
| <span data-ttu-id="99214-147">IsExecutable</span><span class="sxs-lookup"><span data-stu-id="99214-147">IsExecutable</span></span> | <span data-ttu-id="99214-148">부울</span><span class="sxs-lookup"><span data-stu-id="99214-148">boolean</span></span> | <span data-ttu-id="99214-149">PE (이식 가능한 실행) 파일 인지 여부</span><span class="sxs-lookup"><span data-stu-id="99214-149">Whether the file is a Portable Executable (PE) file</span></span> |
| <span data-ttu-id="99214-150">Mail.threatname</span><span class="sxs-lookup"><span data-stu-id="99214-150">ThreatName</span></span> | <span data-ttu-id="99214-151">문자열</span><span class="sxs-lookup"><span data-stu-id="99214-151">string</span></span> | <span data-ttu-id="99214-152">발견 된 맬웨어 또는 기타 위협에 대 한 검색 이름</span><span class="sxs-lookup"><span data-stu-id="99214-152">Detection name for any malware or other threats found</span></span> |
| <span data-ttu-id="99214-153">Publisher</span><span class="sxs-lookup"><span data-stu-id="99214-153">Publisher</span></span> | <span data-ttu-id="99214-154">문자열</span><span class="sxs-lookup"><span data-stu-id="99214-154">string</span></span> | <span data-ttu-id="99214-155">파일을 게시 한 조직의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="99214-155">Name of the organization that published the file</span></span> |
| <span data-ttu-id="99214-156">SoftwareName</span><span class="sxs-lookup"><span data-stu-id="99214-156">SoftwareName</span></span> | <span data-ttu-id="99214-157">문자열</span><span class="sxs-lookup"><span data-stu-id="99214-157">string</span></span> | <span data-ttu-id="99214-158">소프트웨어 제품의 이름</span><span class="sxs-lookup"><span data-stu-id="99214-158">Name of the software product</span></span> |

## <a name="syntax"></a><span data-ttu-id="99214-159">구문과</span><span class="sxs-lookup"><span data-stu-id="99214-159">Syntax</span></span>

```kusto
invoke FileProfile(x,y)
```

## <a name="arguments"></a><span data-ttu-id="99214-160">인수나</span><span class="sxs-lookup"><span data-stu-id="99214-160">Arguments</span></span>

- <span data-ttu-id="99214-161">**x** -다음을 사용할 파일 ID 열: `SHA1` , `SHA256` , `InitiatingProcessSHA1` 또는 `InitiatingProcessSHA256` ; function이 `SHA1` 지정 되지 않은 경우 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="99214-161">**x** — file ID column to use: `SHA1`, `SHA256`, `InitiatingProcessSHA1` or `InitiatingProcessSHA256`; function uses `SHA1` if unspecified</span></span>
- <span data-ttu-id="99214-162">**y** -보강할 레코드 수에 대 한 제한 1-1000; 함수가 지정 되지 않은 경우 100을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="99214-162">**y** — limit to the number of records to enrich, 1-1000; function uses 100 if unspecified</span></span>

## <a name="examples"></a><span data-ttu-id="99214-163">예</span><span class="sxs-lookup"><span data-stu-id="99214-163">Examples</span></span>

### <a name="project-only-the-sha1-column-and-enrich-it"></a><span data-ttu-id="99214-164">SHA1 열만 프로젝트 및 보강</span><span class="sxs-lookup"><span data-stu-id="99214-164">Project only the SHA1 column and enrich it</span></span>

```kusto
DeviceFileEvents
| where isnotempty(SHA1) and Timestamp > ago(1d)
| take 10
| project SHA1
| invoke FileProfile()
```

### <a name="enrich-the-first-500-records-and-list-low-prevalence-files"></a><span data-ttu-id="99214-165">처음 500 레코드를 보강 하 고 낮은 전파 파일 목록 표시</span><span class="sxs-lookup"><span data-stu-id="99214-165">Enrich the first 500 records and list low-prevalence files</span></span>

```kusto
DeviceFileEvents
| where ActionType == "FileCreated" and Timestamp > ago(1d)
| project CreatedOn = Timestamp, FileName, FolderPath, SHA1
| invoke FileProfile("SHA1", 500) 
| where GlobalPrevalence < 15
```

## <a name="related-topics"></a><span data-ttu-id="99214-166">관련 항목</span><span class="sxs-lookup"><span data-stu-id="99214-166">Related topics</span></span>
- [<span data-ttu-id="99214-167">고급 헌팅 개요</span><span class="sxs-lookup"><span data-stu-id="99214-167">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="99214-168">쿼리 언어 배우기</span><span class="sxs-lookup"><span data-stu-id="99214-168">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="99214-169">스키마의 이해</span><span class="sxs-lookup"><span data-stu-id="99214-169">Understand the schema</span></span>](advanced-hunting-schema-tables.md)