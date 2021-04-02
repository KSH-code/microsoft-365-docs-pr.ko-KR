---
title: 고급 헌팅 schema의 DeviceFileCertificateInfo 테이블
description: 고급 헌팅스키마의 DeviceFileCertificateInfo 표에 있는 파일 서명 정보에 대해 자세히 알아보시다.
keywords: 고급 헌팅, 위협 헌팅, 사이버 위협 헌팅, mdatp, microsoft defender atp, wdatp 검색, 쿼리, 원격 분석, schema 참조, kusto, 표, 열, 데이터 형식, 설명, 디지털 서명, 인증서, 파일 서명, DeviceFileCertificateInfo
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: maccruz
author: schmurky
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.date: 01/14/2020
ms.technology: mde
ms.openlocfilehash: f693c54828d8ede1d21167817f77b875ab5680ce
ms.sourcegitcommit: 582555d2b4ef5f2e2494ffdeab2c1d49e5d6b724
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/01/2021
ms.locfileid: "51499176"
---
# <a name="devicefilecertificateinfo"></a><span data-ttu-id="805a2-104">DeviceFileCertificateInfo</span><span class="sxs-lookup"><span data-stu-id="805a2-104">DeviceFileCertificateInfo</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="805a2-105">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="805a2-105">**Applies to:**</span></span>
- [<span data-ttu-id="805a2-106">엔드포인트용 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="805a2-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)


><span data-ttu-id="805a2-107">Endpoint용 Defender를 경험하고 싶나요?</span><span class="sxs-lookup"><span data-stu-id="805a2-107">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="805a2-108">무료 평가판에 등록합니다.</span><span class="sxs-lookup"><span data-stu-id="805a2-108">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-advancedhuntingref-abovefoldlink)

<span data-ttu-id="805a2-109">고급 `DeviceFileCertificateInfo` 헌팅 [Schema의](advanced-hunting-overview.md) 표에는 파일 서명 인증서에 대한 정보가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="805a2-109">The `DeviceFileCertificateInfo` table in the [advanced hunting](advanced-hunting-overview.md) schema contains information about file signing certificates.</span></span> <span data-ttu-id="805a2-110">이 표에서는 끝점의 파일에 대해 정기적으로 수행되는 인증서 확인 활동에서 얻은 데이터를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="805a2-110">This table uses data obtained from certificate verification activities regularly performed on files on endpoints.</span></span>

<span data-ttu-id="805a2-111">고급 헌팅 스마의 다른 표에 대한 자세한 내용은 고급 헌팅 스마 [참조 를 참조하세요.](advanced-hunting-schema-reference.md)</span><span class="sxs-lookup"><span data-stu-id="805a2-111">For information on other tables in the advanced hunting schema, see [the advanced hunting schema reference](advanced-hunting-schema-reference.md).</span></span>

| <span data-ttu-id="805a2-112">열 이름</span><span class="sxs-lookup"><span data-stu-id="805a2-112">Column name</span></span> | <span data-ttu-id="805a2-113">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="805a2-113">Data type</span></span> | <span data-ttu-id="805a2-114">설명</span><span class="sxs-lookup"><span data-stu-id="805a2-114">Description</span></span> |
|-------------|-----------|-------------|
| `Timestamp` | <span data-ttu-id="805a2-115">datetime</span><span class="sxs-lookup"><span data-stu-id="805a2-115">datetime</span></span> | <span data-ttu-id="805a2-116">이벤트가 기록된 날짜와 시간</span><span class="sxs-lookup"><span data-stu-id="805a2-116">Date and time when the event was recorded</span></span> |
| `DeviceId` | <span data-ttu-id="805a2-117">문자열</span><span class="sxs-lookup"><span data-stu-id="805a2-117">string</span></span> | <span data-ttu-id="805a2-118">서비스에서 디바이스의 고유 식별자</span><span class="sxs-lookup"><span data-stu-id="805a2-118">Unique identifier for the device in the service</span></span> |
| `DeviceName` | <span data-ttu-id="805a2-119">문자열</span><span class="sxs-lookup"><span data-stu-id="805a2-119">string</span></span> | <span data-ttu-id="805a2-120">장치의 FQDN(FQDN)</span><span class="sxs-lookup"><span data-stu-id="805a2-120">Fully qualified domain name (FQDN) of the device</span></span> |
| `SHA1` | <span data-ttu-id="805a2-121">문자열</span><span class="sxs-lookup"><span data-stu-id="805a2-121">string</span></span> | <span data-ttu-id="805a2-122">기록된 조치가 적용된 파일의 SHA-1</span><span class="sxs-lookup"><span data-stu-id="805a2-122">SHA-1 of the file that the recorded action was applied to</span></span> |
| `IsSigned` | <span data-ttu-id="805a2-123">부울</span><span class="sxs-lookup"><span data-stu-id="805a2-123">boolean</span></span> | <span data-ttu-id="805a2-124">파일에 서명이 있는지 여부를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="805a2-124">Indicates whether the file is signed</span></span> |
| `SignatureType` | <span data-ttu-id="805a2-125">문자열</span><span class="sxs-lookup"><span data-stu-id="805a2-125">string</span></span> | <span data-ttu-id="805a2-126">서명 정보가 파일 자체에 포함된 콘텐츠로 읽혀지거나 외부 카탈로그 파일에서 읽어들이는지 여부를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="805a2-126">Indicates whether signature information was read as embedded content in the file itself or read from an external catalog file</span></span> |
| `Signer` | <span data-ttu-id="805a2-127">문자열</span><span class="sxs-lookup"><span data-stu-id="805a2-127">string</span></span> | <span data-ttu-id="805a2-128">파일의 서명자에 대한 정보</span><span class="sxs-lookup"><span data-stu-id="805a2-128">Information about the signer of the file</span></span> |
| `SignerHash` | <span data-ttu-id="805a2-129">문자열</span><span class="sxs-lookup"><span data-stu-id="805a2-129">string</span></span> | <span data-ttu-id="805a2-130">서명자를 식별하는 고유 해시 값</span><span class="sxs-lookup"><span data-stu-id="805a2-130">Unique hash value identifying the signer</span></span> |
| `Issuer` | <span data-ttu-id="805a2-131">문자열</span><span class="sxs-lookup"><span data-stu-id="805a2-131">string</span></span> | <span data-ttu-id="805a2-132">발급 CA(인증 기관)에 대한 정보</span><span class="sxs-lookup"><span data-stu-id="805a2-132">Information about the issuing certificate authority (CA)</span></span> |
| `IssuerHash` | <span data-ttu-id="805a2-133">문자열</span><span class="sxs-lookup"><span data-stu-id="805a2-133">string</span></span> | <span data-ttu-id="805a2-134">발급 CA(인증 기관)를 식별하는 고유 해시 값</span><span class="sxs-lookup"><span data-stu-id="805a2-134">Unique hash value identifying issuing certificate authority (CA)</span></span> |
| `CertificateSerialNumber` | <span data-ttu-id="805a2-135">문자열</span><span class="sxs-lookup"><span data-stu-id="805a2-135">string</span></span> | <span data-ttu-id="805a2-136">발급 CA(인증 기관)에 고유한 인증서의 식별자</span><span class="sxs-lookup"><span data-stu-id="805a2-136">Identifier for the certificate that is unique to the issuing certificate authority (CA)</span></span> |
| `CrlDistributionPointUrls` | <span data-ttu-id="805a2-137">문자열</span><span class="sxs-lookup"><span data-stu-id="805a2-137">string</span></span> |  <span data-ttu-id="805a2-138">인증서 및 CRL(인증서 해지 목록)이 포함된 네트워크 공유의 URL을 나열하는 JSON 배열</span><span class="sxs-lookup"><span data-stu-id="805a2-138">JSON array listing the URLs of network shares that contain certificates and certificate revocation lists (CRLs)</span></span> |
| `CertificateCreationTime` | <span data-ttu-id="805a2-139">datetime</span><span class="sxs-lookup"><span data-stu-id="805a2-139">datetime</span></span> | <span data-ttu-id="805a2-140">인증서를 만든 날짜 및 시간</span><span class="sxs-lookup"><span data-stu-id="805a2-140">Date and time the certificate was created</span></span> |
| `CertificateExpirationTime` | <span data-ttu-id="805a2-141">datetime</span><span class="sxs-lookup"><span data-stu-id="805a2-141">datetime</span></span> | <span data-ttu-id="805a2-142">인증서가 만료되는 날짜 및 시간</span><span class="sxs-lookup"><span data-stu-id="805a2-142">Date and time the certificate is set to expire</span></span> |
| `CertificateCountersignatureTime` | <span data-ttu-id="805a2-143">datetime</span><span class="sxs-lookup"><span data-stu-id="805a2-143">datetime</span></span> | <span data-ttu-id="805a2-144">인증서가 연대 서명된 날짜 및 시간</span><span class="sxs-lookup"><span data-stu-id="805a2-144">Date and time the certificate was countersigned</span></span> |
| `IsTrusted` | <span data-ttu-id="805a2-145">부울</span><span class="sxs-lookup"><span data-stu-id="805a2-145">boolean</span></span> | <span data-ttu-id="805a2-146">알 수 없는 루트 인증서 정보, 잘못된 서명, 해지된 인증서 및 기타 의심되는 특성을 검사하는 WinVerifyTrust 함수의 결과에 따라 파일을 신뢰할 수 있는지 여부를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="805a2-146">Indicates whether the file is trusted based on the results of the WinVerifyTrust function, which checks for unknown root certificate information, invalid signatures, revoked certificates, and other questionable attributes</span></span> |
| `IsRootSignerMicrosoft` | <span data-ttu-id="805a2-147">부울</span><span class="sxs-lookup"><span data-stu-id="805a2-147">boolean</span></span> | <span data-ttu-id="805a2-148">루트 인증서의 서명자인지 여부를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="805a2-148">Indicates whether the signer of the root certificate is Microsoft</span></span> |
| `ReportId` | <span data-ttu-id="805a2-149">long</span><span class="sxs-lookup"><span data-stu-id="805a2-149">long</span></span> | <span data-ttu-id="805a2-150">반복 카운터를 기반으로 하는 이벤트 식별자입니다.</span><span class="sxs-lookup"><span data-stu-id="805a2-150">Event identifier based on a repeating counter.</span></span> <span data-ttu-id="805a2-151">고유한 이벤트를 식별하려면 이 열을 DeviceName 및 Timestamp 열과 함께 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="805a2-151">To identify unique events, this column must be used in conjunction with the DeviceName and Timestamp columns.</span></span> |


## <a name="related-topics"></a><span data-ttu-id="805a2-152">관련 항목</span><span class="sxs-lookup"><span data-stu-id="805a2-152">Related topics</span></span>
- [<span data-ttu-id="805a2-153">지능형 헌팅 개요</span><span class="sxs-lookup"><span data-stu-id="805a2-153">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="805a2-154">쿼리 언어 배우기</span><span class="sxs-lookup"><span data-stu-id="805a2-154">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="805a2-155">스키마의 이해</span><span class="sxs-lookup"><span data-stu-id="805a2-155">Understand the schema</span></span>](advanced-hunting-schema-reference.md)
