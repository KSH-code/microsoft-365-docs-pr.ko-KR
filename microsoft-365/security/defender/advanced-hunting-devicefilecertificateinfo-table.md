---
title: 고급 헌팅 schema의 DeviceFileCertificateInfo 테이블
description: 고급 헌팅스키마의 DeviceFileCertificateInfo 표에 있는 파일 서명 정보에 대해 자세히 알아보시다.
keywords: 고급 헌팅, 위협 헌팅, 사이버 위협 헌팅, Microsoft 365 Defender, microsoft 365, m365, 검색, 쿼리, 원격 분석, 스마마 참조, kusto, 표, 열, 데이터 형식, 디지털 서명, 인증서, 파일 서명, DeviceFileCertificateInfo
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
ms.openlocfilehash: 1f894f3fc8cff2113004ff9c9e34ec2ca0144799
ms.sourcegitcommit: 72795ec56a7c4db863dcaaff5e9f7c41c653fda8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/26/2021
ms.locfileid: "52023216"
---
# <a name="devicefilecertificateinfo"></a><span data-ttu-id="a37ce-104">DeviceFileCertificateInfo</span><span class="sxs-lookup"><span data-stu-id="a37ce-104">DeviceFileCertificateInfo</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="a37ce-105">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="a37ce-105">**Applies to:**</span></span>
- <span data-ttu-id="a37ce-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="a37ce-106">Microsoft 365 Defender</span></span>
- <span data-ttu-id="a37ce-107">끝점용 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="a37ce-107">Microsoft Defender for Endpoint</span></span>

<span data-ttu-id="a37ce-108">고급 `DeviceFileCertificateInfo` 헌팅 [Schema의](advanced-hunting-overview.md) 표에는 파일 서명 인증서에 대한 정보가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a37ce-108">The `DeviceFileCertificateInfo` table in the [advanced hunting](advanced-hunting-overview.md) schema contains information about file signing certificates.</span></span> <span data-ttu-id="a37ce-109">이 표에서는 끝점의 파일에 대해 정기적으로 수행되는 인증서 확인 활동에서 얻은 데이터를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="a37ce-109">This table uses data obtained from certificate verification activities regularly performed on files on endpoints.</span></span>

<span data-ttu-id="a37ce-110">고급 헌팅 스키마의 다른 표에 대한 자세한 내용은 [고급 헌팅 참조](advanced-hunting-schema-tables.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="a37ce-110">For information on other tables in the advanced hunting schema, [see the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="a37ce-111">열 이름</span><span class="sxs-lookup"><span data-stu-id="a37ce-111">Column name</span></span> | <span data-ttu-id="a37ce-112">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="a37ce-112">Data type</span></span> | <span data-ttu-id="a37ce-113">설명</span><span class="sxs-lookup"><span data-stu-id="a37ce-113">Description</span></span> |
|-------------|-----------|-------------|
| `Timestamp` | <span data-ttu-id="a37ce-114">datetime</span><span class="sxs-lookup"><span data-stu-id="a37ce-114">datetime</span></span> | <span data-ttu-id="a37ce-115">이벤트가 기록된 날짜와 시간</span><span class="sxs-lookup"><span data-stu-id="a37ce-115">Date and time when the event was recorded</span></span> |
| `DeviceId` | <span data-ttu-id="a37ce-116">문자열</span><span class="sxs-lookup"><span data-stu-id="a37ce-116">string</span></span> | <span data-ttu-id="a37ce-117">서비스에서 시스템의 고유 식별자</span><span class="sxs-lookup"><span data-stu-id="a37ce-117">Unique identifier for the machine in the service</span></span> |
| `DeviceName` | <span data-ttu-id="a37ce-118">문자열</span><span class="sxs-lookup"><span data-stu-id="a37ce-118">string</span></span> | <span data-ttu-id="a37ce-119">컴퓨터의 FQDN(정규화된 도메인 이름)</span><span class="sxs-lookup"><span data-stu-id="a37ce-119">Fully qualified domain name (FQDN) of the machine</span></span> |
| `SHA1` | <span data-ttu-id="a37ce-120">문자열</span><span class="sxs-lookup"><span data-stu-id="a37ce-120">string</span></span> | <span data-ttu-id="a37ce-121">기록된 조치가 적용된 파일의 SHA-1</span><span class="sxs-lookup"><span data-stu-id="a37ce-121">SHA-1 of the file that the recorded action was applied to</span></span> |
| `IsSigned` | <span data-ttu-id="a37ce-122">부울</span><span class="sxs-lookup"><span data-stu-id="a37ce-122">boolean</span></span> | <span data-ttu-id="a37ce-123">파일에 서명이 있는지 여부를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="a37ce-123">Indicates whether the file is signed</span></span> |
| `SignatureType` | <span data-ttu-id="a37ce-124">문자열</span><span class="sxs-lookup"><span data-stu-id="a37ce-124">string</span></span> | <span data-ttu-id="a37ce-125">서명 정보가 파일 자체에 포함된 콘텐츠로 읽혀지거나 외부 카탈로그 파일에서 읽어들이는지 여부를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="a37ce-125">Indicates whether signature information was read as embedded content in the file itself or read from an external catalog file</span></span> |
| `Signer` | <span data-ttu-id="a37ce-126">문자열</span><span class="sxs-lookup"><span data-stu-id="a37ce-126">string</span></span> | <span data-ttu-id="a37ce-127">파일의 서명자에 대한 정보</span><span class="sxs-lookup"><span data-stu-id="a37ce-127">Information about the signer of the file</span></span> |
| `SignerHash` | <span data-ttu-id="a37ce-128">문자열</span><span class="sxs-lookup"><span data-stu-id="a37ce-128">string</span></span> | <span data-ttu-id="a37ce-129">서명자를 식별하는 고유 해시 값</span><span class="sxs-lookup"><span data-stu-id="a37ce-129">Unique hash value identifying the signer</span></span> |
| `Issuer` | <span data-ttu-id="a37ce-130">문자열</span><span class="sxs-lookup"><span data-stu-id="a37ce-130">string</span></span> | <span data-ttu-id="a37ce-131">발급 CA(인증 기관)에 대한 정보</span><span class="sxs-lookup"><span data-stu-id="a37ce-131">Information about the issuing certificate authority (CA)</span></span> |
| `IssuerHash` | <span data-ttu-id="a37ce-132">문자열</span><span class="sxs-lookup"><span data-stu-id="a37ce-132">string</span></span> | <span data-ttu-id="a37ce-133">발급 CA(인증 기관)를 식별하는 고유 해시 값</span><span class="sxs-lookup"><span data-stu-id="a37ce-133">Unique hash value identifying issuing certificate authority (CA)</span></span> |
| `CertificateSerialNumber` | <span data-ttu-id="a37ce-134">문자열</span><span class="sxs-lookup"><span data-stu-id="a37ce-134">string</span></span> | <span data-ttu-id="a37ce-135">발급 CA(인증 기관)에 고유한 인증서의 식별자</span><span class="sxs-lookup"><span data-stu-id="a37ce-135">Identifier for the certificate that is unique to the issuing certificate authority (CA)</span></span> |
| `CrlDistributionPointUrls` | <span data-ttu-id="a37ce-136">문자열</span><span class="sxs-lookup"><span data-stu-id="a37ce-136">string</span></span> |  <span data-ttu-id="a37ce-137">인증서 및 CRL(인증서 해지 목록)이 포함된 네트워크 공유의 URL을 나열하는 JSON 배열</span><span class="sxs-lookup"><span data-stu-id="a37ce-137">JSON array listing the URLs of network shares that contain certificates and certificate revocation lists (CRLs)</span></span> |
| `CertificateCreationTime` | <span data-ttu-id="a37ce-138">datetime</span><span class="sxs-lookup"><span data-stu-id="a37ce-138">datetime</span></span> | <span data-ttu-id="a37ce-139">인증서를 만든 날짜 및 시간</span><span class="sxs-lookup"><span data-stu-id="a37ce-139">Date and time the certificate was created</span></span> |
| `CertificateExpirationTime` | <span data-ttu-id="a37ce-140">datetime</span><span class="sxs-lookup"><span data-stu-id="a37ce-140">datetime</span></span> | <span data-ttu-id="a37ce-141">인증서가 만료되는 날짜 및 시간</span><span class="sxs-lookup"><span data-stu-id="a37ce-141">Date and time the certificate is set to expire</span></span> |
| `CertificateCountersignatureTime` | <span data-ttu-id="a37ce-142">datetime</span><span class="sxs-lookup"><span data-stu-id="a37ce-142">datetime</span></span> | <span data-ttu-id="a37ce-143">인증서가 연대 서명된 날짜 및 시간</span><span class="sxs-lookup"><span data-stu-id="a37ce-143">Date and time the certificate was countersigned</span></span> |
| `IsTrusted` | <span data-ttu-id="a37ce-144">부울</span><span class="sxs-lookup"><span data-stu-id="a37ce-144">boolean</span></span> | <span data-ttu-id="a37ce-145">알 수 없는 루트 인증서 정보, 잘못된 서명, 해지된 인증서 및 기타 의심되는 특성을 검사하는 WinVerifyTrust 함수의 결과에 따라 파일을 신뢰할 수 있는지 여부를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="a37ce-145">Indicates whether the file is trusted based on the results of the WinVerifyTrust function, which checks for unknown root certificate information, invalid signatures, revoked certificates, and other questionable attributes</span></span> |
| `IsRootSignerMicrosoft` | <span data-ttu-id="a37ce-146">부울</span><span class="sxs-lookup"><span data-stu-id="a37ce-146">boolean</span></span> | <span data-ttu-id="a37ce-147">루트 인증서의 서명자인지 여부를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="a37ce-147">Indicates whether the signer of the root certificate is Microsoft</span></span> |
| `ReportId` | <span data-ttu-id="a37ce-148">long</span><span class="sxs-lookup"><span data-stu-id="a37ce-148">long</span></span> | <span data-ttu-id="a37ce-149">반복 카운터를 기반으로 하는 이벤트 식별자입니다.</span><span class="sxs-lookup"><span data-stu-id="a37ce-149">Event identifier based on a repeating counter.</span></span> <span data-ttu-id="a37ce-150">고유한 이벤트를 식별하려면 이 열을 DeviceName 및 Timestamp 열과 함께 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a37ce-150">To identify unique events, this column must be used in conjunction with the DeviceName and Timestamp columns.</span></span> | 

## <a name="related-topics"></a><span data-ttu-id="a37ce-151">관련 항목</span><span class="sxs-lookup"><span data-stu-id="a37ce-151">Related topics</span></span>
- [<span data-ttu-id="a37ce-152">지능형 헌팅 개요</span><span class="sxs-lookup"><span data-stu-id="a37ce-152">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="a37ce-153">쿼리 언어 배우기</span><span class="sxs-lookup"><span data-stu-id="a37ce-153">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="a37ce-154">공유 쿼리 사용</span><span class="sxs-lookup"><span data-stu-id="a37ce-154">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="a37ce-155">장치, 전자 메일, 앱 및 ID를 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="a37ce-155">Hunt across devices, emails, apps, and identities</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="a37ce-156">스키마의 이해</span><span class="sxs-lookup"><span data-stu-id="a37ce-156">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="a37ce-157">쿼리 모범 사례 적용</span><span class="sxs-lookup"><span data-stu-id="a37ce-157">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
