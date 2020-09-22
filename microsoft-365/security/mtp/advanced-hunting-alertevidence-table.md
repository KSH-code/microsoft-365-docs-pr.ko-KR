---
title: 고급 구하기 스키마의 AlertEvidence 테이블
description: 고급 구하기 스키마의 AlertEvidence 테이블에서 경고와 관련 된 정보에 대해 자세히 알아보기
keywords: 고급 구하기, 위협 검색, 사이버 위협 요소 검색, microsoft threat protection, microsoft 365, mtp, m365, search, query, 원격 분석, 스키마 참조, kusto, table, column, AlertInfo, account, address,, file, machine, user, account
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
ms.openlocfilehash: a7e2eca147bb956606380b9ac97a91b898830dd0
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/22/2020
ms.locfileid: "48197272"
---
# <a name="alertevidence"></a><span data-ttu-id="7126d-104">AlertEvidence</span><span class="sxs-lookup"><span data-stu-id="7126d-104">AlertEvidence</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="7126d-105">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="7126d-105">**Applies to:**</span></span>
- <span data-ttu-id="7126d-106">Microsoft 위협 방지</span><span class="sxs-lookup"><span data-stu-id="7126d-106">Microsoft Threat Protection</span></span>

<span data-ttu-id="7126d-107">`AlertEvidence` [고급 구하기](advanced-hunting-overview.md) 스키마의 표에는 Microsoft Defender ATP, Office 365 ATP, Microsoft Cloud App SECURITY 및 Azure ATP의 알림과 관련 된 다양 한 엔터티에 대 한 정보 (파일, IP 주소, url, 사용자 또는 장치)가 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7126d-107">The `AlertEvidence` table in the [advanced hunting](advanced-hunting-overview.md) schema contains information about various entities—files, IP addresses, URLs, users, or devices—associated with alerts from Microsoft Defender ATP, Office 365 ATP, Microsoft Cloud App Security, and Azure ATP.</span></span> <span data-ttu-id="7126d-108">이 참조를 사용하여 이 표의 정보를 반환하는 쿼리를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="7126d-108">Use this reference to construct queries that return information from this table.</span></span>

<span data-ttu-id="7126d-109">고급 헌팅 스키마의 다른 표에 대한 자세한 내용은 [고급 헌팅 참조](advanced-hunting-schema-tables.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="7126d-109">For information on other tables in the advanced hunting schema, [see the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="7126d-110">열 이름</span><span class="sxs-lookup"><span data-stu-id="7126d-110">Column name</span></span> | <span data-ttu-id="7126d-111">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="7126d-111">Data type</span></span> | <span data-ttu-id="7126d-112">설명</span><span class="sxs-lookup"><span data-stu-id="7126d-112">Description</span></span> |
|-------------|-----------|-------------|
| `Timestamp` | <span data-ttu-id="7126d-113">datetime</span><span class="sxs-lookup"><span data-stu-id="7126d-113">datetime</span></span> | <span data-ttu-id="7126d-114">이벤트가 기록된 날짜와 시간</span><span class="sxs-lookup"><span data-stu-id="7126d-114">Date and time when the event was recorded</span></span> |
| `AlertId` | <span data-ttu-id="7126d-115">문자열</span><span class="sxs-lookup"><span data-stu-id="7126d-115">string</span></span> | <span data-ttu-id="7126d-116">경고의 고유 식별자입니다.</span><span class="sxs-lookup"><span data-stu-id="7126d-116">Unique identifier for the alert</span></span> |
| `ServiceSource` | <span data-ttu-id="7126d-117">문자열</span><span class="sxs-lookup"><span data-stu-id="7126d-117">string</span></span> | <span data-ttu-id="7126d-118">경고 정보를 제공한 제품 또는 서비스</span><span class="sxs-lookup"><span data-stu-id="7126d-118">Product or service that provided the alert information</span></span> |
| `EntityType` | <span data-ttu-id="7126d-119">문자열</span><span class="sxs-lookup"><span data-stu-id="7126d-119">string</span></span> | <span data-ttu-id="7126d-120">파일, 프로세스, 장치 또는 사용자와 같은 개체의 유형입니다.</span><span class="sxs-lookup"><span data-stu-id="7126d-120">Type of object, such as a file, a process, a device, or a user</span></span> |
| `EvidenceRole` | <span data-ttu-id="7126d-121">문자열</span><span class="sxs-lookup"><span data-stu-id="7126d-121">string</span></span> | <span data-ttu-id="7126d-122">관계가 영향을 받는 지 또는 관련이 있는지를 나타내는 경고에 포함 되는 방법</span><span class="sxs-lookup"><span data-stu-id="7126d-122">How the entity is involved in an alert, indicating whether it is impacted or is merely related</span></span> |
| `EvidenceDirection` | <span data-ttu-id="7126d-123">문자열</span><span class="sxs-lookup"><span data-stu-id="7126d-123">string</span></span> | <span data-ttu-id="7126d-124">엔터티가 네트워크 연결의 원본 또는 대상 인지를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="7126d-124">Indicates whether the entity is the source or the destination of a network connection</span></span> |
| `FileName` | <span data-ttu-id="7126d-125">문자열</span><span class="sxs-lookup"><span data-stu-id="7126d-125">string</span></span> | <span data-ttu-id="7126d-126">기록된 조치가 적용된 파일의 이름</span><span class="sxs-lookup"><span data-stu-id="7126d-126">Name of the file that the recorded action was applied to</span></span> |
| `FolderPath` | <span data-ttu-id="7126d-127">문자열</span><span class="sxs-lookup"><span data-stu-id="7126d-127">string</span></span> | <span data-ttu-id="7126d-128">기록 된 작업이 적용 된 파일을 포함 하는 폴더</span><span class="sxs-lookup"><span data-stu-id="7126d-128">Folder containing the file that the recorded action was applied to</span></span> |
| `SHA1` | <span data-ttu-id="7126d-129">문자열</span><span class="sxs-lookup"><span data-stu-id="7126d-129">string</span></span> | <span data-ttu-id="7126d-130">기록된 조치가 적용된 파일의 SHA-1</span><span class="sxs-lookup"><span data-stu-id="7126d-130">SHA-1 of the file that the recorded action was applied to</span></span> |
| `SHA256` | <span data-ttu-id="7126d-131">문자열</span><span class="sxs-lookup"><span data-stu-id="7126d-131">string</span></span> | <span data-ttu-id="7126d-132">기록된 조치가 적용된 파일의 SHA-256</span><span class="sxs-lookup"><span data-stu-id="7126d-132">SHA-256 of the file that the recorded action was applied to.</span></span> <span data-ttu-id="7126d-133">이 필드는 대개 채워지지 않으며, 가능한 경우 SHA1 열을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="7126d-133">This field is usually not populated—use the SHA1 column when available.</span></span> |
| `FileSize` | <span data-ttu-id="7126d-134">int</span><span class="sxs-lookup"><span data-stu-id="7126d-134">int</span></span> | <span data-ttu-id="7126d-135">파일 크기 (바이트)입니다.</span><span class="sxs-lookup"><span data-stu-id="7126d-135">Size of the file in bytes</span></span> |
| `ThreatFamily` | <span data-ttu-id="7126d-136">문자열</span><span class="sxs-lookup"><span data-stu-id="7126d-136">string</span></span> | <span data-ttu-id="7126d-137">의심 스러운 또는 악성 파일 또는 프로세스가 분류 된 맬웨어 패밀리</span><span class="sxs-lookup"><span data-stu-id="7126d-137">Malware family that the suspicious or malicious file or process has been classified under</span></span> |
| `RemoteIP` | <span data-ttu-id="7126d-138">문자열</span><span class="sxs-lookup"><span data-stu-id="7126d-138">string</span></span> | <span data-ttu-id="7126d-139">연결된 IP 주소</span><span class="sxs-lookup"><span data-stu-id="7126d-139">IP address that was being connected to</span></span> |
| `RemoteUrl` | <span data-ttu-id="7126d-140">문자열</span><span class="sxs-lookup"><span data-stu-id="7126d-140">string</span></span> | <span data-ttu-id="7126d-141">연결된 URL 또는 FQDN(정규화된 도메인 이름)</span><span class="sxs-lookup"><span data-stu-id="7126d-141">URL or fully qualified domain name (FQDN) that was being connected to</span></span> |
| `AccountName` | <span data-ttu-id="7126d-142">문자열</span><span class="sxs-lookup"><span data-stu-id="7126d-142">string</span></span> | <span data-ttu-id="7126d-143">계정의 사용자 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="7126d-143">User name of the account</span></span> |
| `AccountDomain` | <span data-ttu-id="7126d-144">문자열</span><span class="sxs-lookup"><span data-stu-id="7126d-144">string</span></span> | <span data-ttu-id="7126d-145">계정의 도메인</span><span class="sxs-lookup"><span data-stu-id="7126d-145">Domain of the account</span></span> |
| `AccountSid` | <span data-ttu-id="7126d-146">문자열</span><span class="sxs-lookup"><span data-stu-id="7126d-146">string</span></span> | <span data-ttu-id="7126d-147">계정의 SID (보안 식별자)</span><span class="sxs-lookup"><span data-stu-id="7126d-147">Security Identifier (SID) of the account</span></span> |
| `AccountObjectId` | <span data-ttu-id="7126d-148">문자열</span><span class="sxs-lookup"><span data-stu-id="7126d-148">string</span></span> | <span data-ttu-id="7126d-149">Azure Active Directory의 계정에 대 한 고유 식별자입니다.</span><span class="sxs-lookup"><span data-stu-id="7126d-149">Unique identifier for the account in Azure Active Directory</span></span> |
| `DeviceId` | <span data-ttu-id="7126d-150">문자열</span><span class="sxs-lookup"><span data-stu-id="7126d-150">string</span></span> | <span data-ttu-id="7126d-151">서비스의 장치에 대 한 고유 식별자입니다.</span><span class="sxs-lookup"><span data-stu-id="7126d-151">Unique identifier for the device in the service</span></span> |
| `DeviceName` | <span data-ttu-id="7126d-152">문자열</span><span class="sxs-lookup"><span data-stu-id="7126d-152">string</span></span> | <span data-ttu-id="7126d-153">컴퓨터의 FQDN(정규화된 도메인 이름)</span><span class="sxs-lookup"><span data-stu-id="7126d-153">Fully qualified domain name (FQDN) of the machine</span></span> |
| `LocalIP` | <span data-ttu-id="7126d-154">문자열</span><span class="sxs-lookup"><span data-stu-id="7126d-154">string</span></span> | <span data-ttu-id="7126d-155">통신 중에 사용 되는 로컬 장치에 할당 된 IP 주소</span><span class="sxs-lookup"><span data-stu-id="7126d-155">IP address assigned to the local device used during communication</span></span> |
| `NetworkMessageId` | <span data-ttu-id="7126d-156">문자열</span><span class="sxs-lookup"><span data-stu-id="7126d-156">string</span></span> | <span data-ttu-id="7126d-157">Office 365에서 생성되는 전자 메일의 고유 식별자</span><span class="sxs-lookup"><span data-stu-id="7126d-157">Unique identifier for the email, generated by Office 365</span></span> |
| `EmailSubject` | <span data-ttu-id="7126d-158">문자열</span><span class="sxs-lookup"><span data-stu-id="7126d-158">string</span></span> | <span data-ttu-id="7126d-159">전자 메일 제목</span><span class="sxs-lookup"><span data-stu-id="7126d-159">Subject of the email</span></span> |
| `ApplicationId` | <span data-ttu-id="7126d-160">문자열</span><span class="sxs-lookup"><span data-stu-id="7126d-160">string</span></span> | <span data-ttu-id="7126d-161">응용 프로그램의 고유 식별자입니다.</span><span class="sxs-lookup"><span data-stu-id="7126d-161">Unique identifier for the application</span></span> |
| `Application` | <span data-ttu-id="7126d-162">문자열</span><span class="sxs-lookup"><span data-stu-id="7126d-162">string</span></span> | <span data-ttu-id="7126d-163">기록 된 작업을 수행한 응용 프로그램</span><span class="sxs-lookup"><span data-stu-id="7126d-163">Application that performed the recorded action</span></span> |
| `ProcessCommandLine` | <span data-ttu-id="7126d-164">문자열</span><span class="sxs-lookup"><span data-stu-id="7126d-164">string</span></span> | <span data-ttu-id="7126d-165">새 프로세스를 만드는 데 사용 되는 명령줄</span><span class="sxs-lookup"><span data-stu-id="7126d-165">Command line used to create the new process</span></span> |
| `AdditionalFields` | <span data-ttu-id="7126d-166">문자열</span><span class="sxs-lookup"><span data-stu-id="7126d-166">string</span></span> | <span data-ttu-id="7126d-167">JSON 배열 형식의 이벤트에 대 한 추가 정보</span><span class="sxs-lookup"><span data-stu-id="7126d-167">Additional information about the event in JSON array format</span></span> |

## <a name="related-topics"></a><span data-ttu-id="7126d-168">관련 항목</span><span class="sxs-lookup"><span data-stu-id="7126d-168">Related topics</span></span>
- [<span data-ttu-id="7126d-169">고급 헌팅 개요</span><span class="sxs-lookup"><span data-stu-id="7126d-169">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="7126d-170">쿼리 언어 배우기</span><span class="sxs-lookup"><span data-stu-id="7126d-170">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="7126d-171">공유 쿼리 사용</span><span class="sxs-lookup"><span data-stu-id="7126d-171">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="7126d-172">기기, 전자 메일, 앱 및 ID를 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="7126d-172">Hunt across devices, emails, apps, and identities</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="7126d-173">스키마의 이해</span><span class="sxs-lookup"><span data-stu-id="7126d-173">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="7126d-174">쿼리 모범 사례 적용</span><span class="sxs-lookup"><span data-stu-id="7126d-174">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
