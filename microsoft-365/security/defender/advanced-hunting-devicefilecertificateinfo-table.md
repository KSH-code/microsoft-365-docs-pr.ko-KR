---
title: 고급 헌팅 schema의 DeviceFileCertificateInfo 테이블
description: 고급 헌팅스키마의 DeviceFileCertificateInfo 표에 있는 파일 서명 정보에 대해 자세히 알아보시다.
keywords: 고급 헌팅, 위협 헌팅, 사이버 위협 헌팅, Microsoft 위협 방지, microsoft 365, mtp, m365, 검색, 쿼리, 원격 분석, 스마 참조, kusto, 표, 열, 데이터 형식, 디지털 서명, 인증서, 파일 서명, DeviceFileCertificateInfo
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: maccruz
author: schmurky
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: eafe84e2d08ce15fe2c3a7cbfafb0822a2f38666
ms.sourcegitcommit: 582555d2b4ef5f2e2494ffdeab2c1d49e5d6b724
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/01/2021
ms.locfileid: "51498639"
---
# <a name="devicefilecertificateinfo"></a><span data-ttu-id="d280a-104">DeviceFileCertificateInfo</span><span class="sxs-lookup"><span data-stu-id="d280a-104">DeviceFileCertificateInfo</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="d280a-105">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="d280a-105">**Applies to:**</span></span>
- <span data-ttu-id="d280a-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="d280a-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="d280a-107">고급 `DeviceFileCertificateInfo` 헌팅 [Schema의](advanced-hunting-overview.md) 표에는 파일 서명 인증서에 대한 정보가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d280a-107">The `DeviceFileCertificateInfo` table in the [advanced hunting](advanced-hunting-overview.md) schema contains information about file signing certificates.</span></span> <span data-ttu-id="d280a-108">이 표에서는 끝점의 파일에 대해 정기적으로 수행되는 인증서 확인 활동에서 얻은 데이터를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="d280a-108">This table uses data obtained from certificate verification activities regularly performed on files on endpoints.</span></span>

<span data-ttu-id="d280a-109">고급 헌팅 스키마의 다른 표에 대한 자세한 내용은 [고급 헌팅 참조](advanced-hunting-schema-tables.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="d280a-109">For information on other tables in the advanced hunting schema, [see the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="d280a-110">열 이름</span><span class="sxs-lookup"><span data-stu-id="d280a-110">Column name</span></span> | <span data-ttu-id="d280a-111">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="d280a-111">Data type</span></span> | <span data-ttu-id="d280a-112">설명</span><span class="sxs-lookup"><span data-stu-id="d280a-112">Description</span></span> |
|-------------|-----------|-------------|
| `Timestamp` | <span data-ttu-id="d280a-113">datetime</span><span class="sxs-lookup"><span data-stu-id="d280a-113">datetime</span></span> | <span data-ttu-id="d280a-114">이벤트가 기록된 날짜와 시간</span><span class="sxs-lookup"><span data-stu-id="d280a-114">Date and time when the event was recorded</span></span> |
| `DeviceId` | <span data-ttu-id="d280a-115">문자열</span><span class="sxs-lookup"><span data-stu-id="d280a-115">string</span></span> | <span data-ttu-id="d280a-116">서비스에서 시스템의 고유 식별자</span><span class="sxs-lookup"><span data-stu-id="d280a-116">Unique identifier for the machine in the service</span></span> |
| `DeviceName` | <span data-ttu-id="d280a-117">문자열</span><span class="sxs-lookup"><span data-stu-id="d280a-117">string</span></span> | <span data-ttu-id="d280a-118">컴퓨터의 FQDN(정규화된 도메인 이름)</span><span class="sxs-lookup"><span data-stu-id="d280a-118">Fully qualified domain name (FQDN) of the machine</span></span> |
| `SHA1` | <span data-ttu-id="d280a-119">문자열</span><span class="sxs-lookup"><span data-stu-id="d280a-119">string</span></span> | <span data-ttu-id="d280a-120">기록된 조치가 적용된 파일의 SHA-1</span><span class="sxs-lookup"><span data-stu-id="d280a-120">SHA-1 of the file that the recorded action was applied to</span></span> |
| `IsSigned` | <span data-ttu-id="d280a-121">부울</span><span class="sxs-lookup"><span data-stu-id="d280a-121">boolean</span></span> | <span data-ttu-id="d280a-122">파일에 서명이 있는지 여부를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="d280a-122">Indicates whether the file is signed</span></span> |
| `SignatureType` | <span data-ttu-id="d280a-123">문자열</span><span class="sxs-lookup"><span data-stu-id="d280a-123">string</span></span> | <span data-ttu-id="d280a-124">서명 정보가 파일 자체에 포함된 콘텐츠로 읽혀지거나 외부 카탈로그 파일에서 읽어들이는지 여부를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="d280a-124">Indicates whether signature information was read as embedded content in the file itself or read from an external catalog file</span></span> |
| `Signer` | <span data-ttu-id="d280a-125">문자열</span><span class="sxs-lookup"><span data-stu-id="d280a-125">string</span></span> | <span data-ttu-id="d280a-126">파일의 서명자에 대한 정보</span><span class="sxs-lookup"><span data-stu-id="d280a-126">Information about the signer of the file</span></span> |
| `SignerHash` | <span data-ttu-id="d280a-127">문자열</span><span class="sxs-lookup"><span data-stu-id="d280a-127">string</span></span> | <span data-ttu-id="d280a-128">서명자를 식별하는 고유 해시 값</span><span class="sxs-lookup"><span data-stu-id="d280a-128">Unique hash value identifying the signer</span></span> |
| `Issuer` | <span data-ttu-id="d280a-129">문자열</span><span class="sxs-lookup"><span data-stu-id="d280a-129">string</span></span> | <span data-ttu-id="d280a-130">발급 CA(인증 기관)에 대한 정보</span><span class="sxs-lookup"><span data-stu-id="d280a-130">Information about the issuing certificate authority (CA)</span></span> |
| `IssuerHash` | <span data-ttu-id="d280a-131">문자열</span><span class="sxs-lookup"><span data-stu-id="d280a-131">string</span></span> | <span data-ttu-id="d280a-132">발급 CA(인증 기관)를 식별하는 고유 해시 값</span><span class="sxs-lookup"><span data-stu-id="d280a-132">Unique hash value identifying issuing certificate authority (CA)</span></span> |
| `CertificateSerialNumber` | <span data-ttu-id="d280a-133">문자열</span><span class="sxs-lookup"><span data-stu-id="d280a-133">string</span></span> | <span data-ttu-id="d280a-134">발급 CA(인증 기관)에 고유한 인증서의 식별자</span><span class="sxs-lookup"><span data-stu-id="d280a-134">Identifier for the certificate that is unique to the issuing certificate authority (CA)</span></span> |
| `CrlDistributionPointUrls` | <span data-ttu-id="d280a-135">문자열</span><span class="sxs-lookup"><span data-stu-id="d280a-135">string</span></span> |  <span data-ttu-id="d280a-136">인증서 및 CRL(인증서 해지 목록)이 포함된 네트워크 공유의 URL을 나열하는 JSON 배열</span><span class="sxs-lookup"><span data-stu-id="d280a-136">JSON array listing the URLs of network shares that contain certificates and certificate revocation lists (CRLs)</span></span> |
| `CertificateCreationTime` | <span data-ttu-id="d280a-137">datetime</span><span class="sxs-lookup"><span data-stu-id="d280a-137">datetime</span></span> | <span data-ttu-id="d280a-138">인증서를 만든 날짜 및 시간</span><span class="sxs-lookup"><span data-stu-id="d280a-138">Date and time the certificate was created</span></span> |
| `CertificateExpirationTime` | <span data-ttu-id="d280a-139">datetime</span><span class="sxs-lookup"><span data-stu-id="d280a-139">datetime</span></span> | <span data-ttu-id="d280a-140">인증서가 만료되는 날짜 및 시간</span><span class="sxs-lookup"><span data-stu-id="d280a-140">Date and time the certificate is set to expire</span></span> |
| `CertificateCountersignatureTime` | <span data-ttu-id="d280a-141">datetime</span><span class="sxs-lookup"><span data-stu-id="d280a-141">datetime</span></span> | <span data-ttu-id="d280a-142">인증서가 연대 서명된 날짜 및 시간</span><span class="sxs-lookup"><span data-stu-id="d280a-142">Date and time the certificate was countersigned</span></span> |
| `IsTrusted` | <span data-ttu-id="d280a-143">부울</span><span class="sxs-lookup"><span data-stu-id="d280a-143">boolean</span></span> | <span data-ttu-id="d280a-144">알 수 없는 루트 인증서 정보, 잘못된 서명, 해지된 인증서 및 기타 의심되는 특성을 검사하는 WinVerifyTrust 함수의 결과에 따라 파일을 신뢰할 수 있는지 여부를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="d280a-144">Indicates whether the file is trusted based on the results of the WinVerifyTrust function, which checks for unknown root certificate information, invalid signatures, revoked certificates, and other questionable attributes</span></span> |
| `IsRootSignerMicrosoft` | <span data-ttu-id="d280a-145">부울</span><span class="sxs-lookup"><span data-stu-id="d280a-145">boolean</span></span> | <span data-ttu-id="d280a-146">루트 인증서의 서명자인지 여부를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="d280a-146">Indicates whether the signer of the root certificate is Microsoft</span></span> |
| `ReportId` | <span data-ttu-id="d280a-147">long</span><span class="sxs-lookup"><span data-stu-id="d280a-147">long</span></span> | <span data-ttu-id="d280a-148">반복 카운터를 기반으로 하는 이벤트 식별자입니다.</span><span class="sxs-lookup"><span data-stu-id="d280a-148">Event identifier based on a repeating counter.</span></span> <span data-ttu-id="d280a-149">고유한 이벤트를 식별하려면 이 열을 DeviceName 및 Timestamp 열과 함께 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d280a-149">To identify unique events, this column must be used in conjunction with the DeviceName and Timestamp columns.</span></span> | 

## <a name="related-topics"></a><span data-ttu-id="d280a-150">관련 항목</span><span class="sxs-lookup"><span data-stu-id="d280a-150">Related topics</span></span>
- [<span data-ttu-id="d280a-151">지능형 헌팅 개요</span><span class="sxs-lookup"><span data-stu-id="d280a-151">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="d280a-152">쿼리 언어 배우기</span><span class="sxs-lookup"><span data-stu-id="d280a-152">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="d280a-153">공유 쿼리 사용</span><span class="sxs-lookup"><span data-stu-id="d280a-153">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="d280a-154">장치, 전자 메일, 앱 및 ID를 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="d280a-154">Hunt across devices, emails, apps, and identities</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="d280a-155">스키마의 이해</span><span class="sxs-lookup"><span data-stu-id="d280a-155">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="d280a-156">쿼리 모범 사례 적용</span><span class="sxs-lookup"><span data-stu-id="d280a-156">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
