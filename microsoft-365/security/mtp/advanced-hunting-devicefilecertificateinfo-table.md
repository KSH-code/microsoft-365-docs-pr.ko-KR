---
title: 고급 구하기 스키마의 DeviceFileCertificateInfo 테이블
description: 고급 구하기 스키마의 DeviceFileCertificateInfo 테이블에 있는 파일 서명 정보에 대해 자세히 알아봅니다.
keywords: 고급 구하기, 위협 검색, 사이버 위협 사냥, microsoft threat protection, microsoft 365, mtp, m365, 검색, 쿼리, 원격 분석, 스키마 참조, kusto, table, column, data type, 디지털 서명, 인증서, 파일 서명, DeviceFileCertificateInfo
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
ms.openlocfilehash: 33f9c726839f17afbb935c6d028cc4eaa5b74843
ms.sourcegitcommit: 51097b18d94da20aa727ebfbeb6ec84c263b25c3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/12/2020
ms.locfileid: "46649454"
---
# <a name="devicefilecertificateinfo"></a><span data-ttu-id="dced7-104">DeviceFileCertificateInfo</span><span class="sxs-lookup"><span data-stu-id="dced7-104">DeviceFileCertificateInfo</span></span>

<span data-ttu-id="dced7-105">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="dced7-105">**Applies to:**</span></span>
- <span data-ttu-id="dced7-106">Microsoft 위협 방지</span><span class="sxs-lookup"><span data-stu-id="dced7-106">Microsoft Threat Protection</span></span>

<span data-ttu-id="dced7-107">`DeviceFileCertificateInfo` [고급 구하기](advanced-hunting-overview.md) 스키마의 표에는 파일 서명 인증서에 대 한 정보가 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dced7-107">The `DeviceFileCertificateInfo` table in the [advanced hunting](advanced-hunting-overview.md) schema contains information about file signing certificates.</span></span> <span data-ttu-id="dced7-108">이 테이블은 끝점에서 파일에 대해 정기적으로 수행 되는 인증서 확인 작업에서 얻은 데이터를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="dced7-108">This table uses data obtained from certificate verification activities regularly performed on files on endpoints.</span></span>

<span data-ttu-id="dced7-109">고급 헌팅 스키마의 다른 표에 대한 자세한 내용은 [고급 헌팅 참조](advanced-hunting-schema-tables.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="dced7-109">For information on other tables in the advanced hunting schema, [see the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="dced7-110">열 이름</span><span class="sxs-lookup"><span data-stu-id="dced7-110">Column name</span></span> | <span data-ttu-id="dced7-111">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="dced7-111">Data type</span></span> | <span data-ttu-id="dced7-112">설명</span><span class="sxs-lookup"><span data-stu-id="dced7-112">Description</span></span> |
|-------------|-----------|-------------|
| `Timestamp` | <span data-ttu-id="dced7-113">datetime</span><span class="sxs-lookup"><span data-stu-id="dced7-113">datetime</span></span> | <span data-ttu-id="dced7-114">이벤트가 기록된 날짜와 시간</span><span class="sxs-lookup"><span data-stu-id="dced7-114">Date and time when the event was recorded</span></span> |
| `DeviceId` | <span data-ttu-id="dced7-115">문자열</span><span class="sxs-lookup"><span data-stu-id="dced7-115">string</span></span> | <span data-ttu-id="dced7-116">서비스에서 시스템의 고유 식별자</span><span class="sxs-lookup"><span data-stu-id="dced7-116">Unique identifier for the machine in the service</span></span> |
| `DeviceName` | <span data-ttu-id="dced7-117">문자열</span><span class="sxs-lookup"><span data-stu-id="dced7-117">string</span></span> | <span data-ttu-id="dced7-118">컴퓨터의 FQDN(정규화된 도메인 이름)</span><span class="sxs-lookup"><span data-stu-id="dced7-118">Fully qualified domain name (FQDN) of the machine</span></span> |
| `SHA1` | <span data-ttu-id="dced7-119">문자열</span><span class="sxs-lookup"><span data-stu-id="dced7-119">string</span></span> | <span data-ttu-id="dced7-120">기록된 조치가 적용된 파일의 SHA-1</span><span class="sxs-lookup"><span data-stu-id="dced7-120">SHA-1 of the file that the recorded action was applied to</span></span> |
| `IsSigned` | <span data-ttu-id="dced7-121">부울</span><span class="sxs-lookup"><span data-stu-id="dced7-121">boolean</span></span> | <span data-ttu-id="dced7-122">파일 서명 여부를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="dced7-122">Indicates whether the file is signed</span></span> |
| `SignatureType` | <span data-ttu-id="dced7-123">문자열</span><span class="sxs-lookup"><span data-stu-id="dced7-123">string</span></span> | <span data-ttu-id="dced7-124">서명 정보가 파일 자체에 포함 된 콘텐츠 인지 아니면 외부 카탈로그 파일에서 읽 었는 지를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="dced7-124">Indicates whether signature information was read as embedded content in the file itself or read from an external catalog file</span></span> |
| `Signer` | <span data-ttu-id="dced7-125">문자열</span><span class="sxs-lookup"><span data-stu-id="dced7-125">string</span></span> | <span data-ttu-id="dced7-126">파일의 서명자에 대 한 정보</span><span class="sxs-lookup"><span data-stu-id="dced7-126">Information about the signer of the file</span></span> |
| `SignerHash` | <span data-ttu-id="dced7-127">문자열</span><span class="sxs-lookup"><span data-stu-id="dced7-127">string</span></span> | <span data-ttu-id="dced7-128">서명자를 식별 하는 고유한 해시 값</span><span class="sxs-lookup"><span data-stu-id="dced7-128">Unique hash value identifying the signer</span></span> |
| `Issuer` | <span data-ttu-id="dced7-129">문자열</span><span class="sxs-lookup"><span data-stu-id="dced7-129">string</span></span> | <span data-ttu-id="dced7-130">발급 CA (인증 기관)에 대 한 정보</span><span class="sxs-lookup"><span data-stu-id="dced7-130">Information about the issuing certificate authority (CA)</span></span> |
| `IssuerHash` | <span data-ttu-id="dced7-131">문자열</span><span class="sxs-lookup"><span data-stu-id="dced7-131">string</span></span> | <span data-ttu-id="dced7-132">발급 CA (인증 기관)를 식별 하는 고유한 해시 값</span><span class="sxs-lookup"><span data-stu-id="dced7-132">Unique hash value identifying issuing certificate authority (CA)</span></span> |
| `CertificateSerialNumber` | <span data-ttu-id="dced7-133">문자열</span><span class="sxs-lookup"><span data-stu-id="dced7-133">string</span></span> | <span data-ttu-id="dced7-134">발급 CA (인증 기관)에 고유한 인증서의 식별자입니다.</span><span class="sxs-lookup"><span data-stu-id="dced7-134">Identifier for the certificate that is unique to the issuing certificate authority (CA)</span></span> |
| `CrlDistributionPointUrls` | <span data-ttu-id="dced7-135">문자열</span><span class="sxs-lookup"><span data-stu-id="dced7-135">string</span></span> |  <span data-ttu-id="dced7-136">인증서 및 Crl (인증서 해지 목록)이 포함 된 네트워크 공유의 Url을 나열 하는 JSON 배열</span><span class="sxs-lookup"><span data-stu-id="dced7-136">JSON array listing the URLs of network shares that contain certificates and certificate revocation lists (CRLs)</span></span> |
| `CertificateCreationTime` | <span data-ttu-id="dced7-137">datetime</span><span class="sxs-lookup"><span data-stu-id="dced7-137">datetime</span></span> | <span data-ttu-id="dced7-138">인증서를 만든 날짜 및 시간입니다.</span><span class="sxs-lookup"><span data-stu-id="dced7-138">Date and time the certificate was created</span></span> |
| `CertificateExpirationTime` | <span data-ttu-id="dced7-139">datetime</span><span class="sxs-lookup"><span data-stu-id="dced7-139">datetime</span></span> | <span data-ttu-id="dced7-140">인증서가 만료 되도록 설정 된 날짜 및 시간</span><span class="sxs-lookup"><span data-stu-id="dced7-140">Date and time the certificate is set to expire</span></span> |
| `CertificateCountersignatureTime` | <span data-ttu-id="dced7-141">datetime</span><span class="sxs-lookup"><span data-stu-id="dced7-141">datetime</span></span> | <span data-ttu-id="dced7-142">인증서가 연대 된 날짜 및 시간</span><span class="sxs-lookup"><span data-stu-id="dced7-142">Date and time the certificate was countersigned</span></span> |
| `IsTrusted` | <span data-ttu-id="dced7-143">부울</span><span class="sxs-lookup"><span data-stu-id="dced7-143">boolean</span></span> | <span data-ttu-id="dced7-144">알 수 없는 루트 인증서 정보, 유효 하지 않은 서명, 해지 된 인증서 및 기타 불확실 한 특성이 있는지 확인 하는 WinVerifyTrust 함수 결과에 따라 파일을 신뢰할 수 있는지 여부를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="dced7-144">Indicates whether the file is trusted based on the results of the WinVerifyTrust function, which checks for unknown root certificate information, invalid signatures, revoked certificates, and other questionable attributes</span></span> |
| `IsRootSignerMicrosoft` | <span data-ttu-id="dced7-145">부울</span><span class="sxs-lookup"><span data-stu-id="dced7-145">boolean</span></span> | <span data-ttu-id="dced7-146">루트 인증서의 서명자가 Microsoft 인지 여부를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="dced7-146">Indicates whether the signer of the root certificate is Microsoft</span></span> |
| `ReportId` | <span data-ttu-id="dced7-147">long</span><span class="sxs-lookup"><span data-stu-id="dced7-147">long</span></span> | <span data-ttu-id="dced7-148">반복 카운터를 기반으로 하는 이벤트 식별자입니다.</span><span class="sxs-lookup"><span data-stu-id="dced7-148">Event identifier based on a repeating counter.</span></span> <span data-ttu-id="dced7-149">고유 이벤트를 식별 하려면이 열을 장치 이름 및 타임 스탬프 열과 함께 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="dced7-149">To identify unique events, this column must be used in conjunction with the DeviceName and Timestamp columns.</span></span> | 

## <a name="related-topics"></a><span data-ttu-id="dced7-150">관련 항목</span><span class="sxs-lookup"><span data-stu-id="dced7-150">Related topics</span></span>
- [<span data-ttu-id="dced7-151">고급 헌팅 개요</span><span class="sxs-lookup"><span data-stu-id="dced7-151">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="dced7-152">쿼리 언어 배우기</span><span class="sxs-lookup"><span data-stu-id="dced7-152">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="dced7-153">공유 쿼리 사용</span><span class="sxs-lookup"><span data-stu-id="dced7-153">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="dced7-154">장치, 전자 메일, 앱 및 id 간 헌트</span><span class="sxs-lookup"><span data-stu-id="dced7-154">Hunt across devices, emails, apps, and identities</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="dced7-155">스키마의 이해</span><span class="sxs-lookup"><span data-stu-id="dced7-155">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="dced7-156">쿼리 모범 사례 적용</span><span class="sxs-lookup"><span data-stu-id="dced7-156">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
