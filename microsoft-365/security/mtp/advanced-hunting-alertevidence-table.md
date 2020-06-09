---
title: 고급 구하기 스키마의 AlertEvidence 테이블
description: 고급 구하기 스키마의 AlertEvidence 테이블에서 생성 된 경고와 관련 된 파일, 네트워크 주소, 사용자 또는 장치 정보에 대해 알아봅니다.
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
ms.openlocfilehash: da6e84725aa391e4cb6056fadd327fdba2436214
ms.sourcegitcommit: 73b2426001dc5a3f4b857366ef51e877db549098
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/09/2020
ms.locfileid: "44617089"
---
# <a name="alertevidence"></a><span data-ttu-id="18f88-104">AlertEvidence</span><span class="sxs-lookup"><span data-stu-id="18f88-104">AlertEvidence</span></span>

<span data-ttu-id="18f88-105">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="18f88-105">**Applies to:**</span></span>
- <span data-ttu-id="18f88-106">Microsoft 위협 방지</span><span class="sxs-lookup"><span data-stu-id="18f88-106">Microsoft Threat Protection</span></span>

<span data-ttu-id="18f88-107">`AlertEvidence` [고급 구하기](advanced-hunting-overview.md) 스키마의 표에는 Microsoft Defender ATP, Office 365 ATP, Microsoft Cloud App SECURITY 및 Azure ATP의 알림과 관련 된 다양 한 엔터티에 대 한 정보 (파일, IP 주소, url, 사용자 또는 장치)가 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="18f88-107">The `AlertEvidence` table in the [advanced hunting](advanced-hunting-overview.md) schema contains information about various entities — files, IP addresses, URLs, users, or devices — associated with alerts from Microsoft Defender ATP, Office 365 ATP, Microsoft Cloud App Security, and Azure ATP.</span></span> <span data-ttu-id="18f88-108">이 참조를 사용하여 이 표의 정보를 반환하는 쿼리를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="18f88-108">Use this reference to construct queries that return information from this table.</span></span>

<span data-ttu-id="18f88-109">고급 헌팅 스키마의 다른 표에 대한 자세한 내용은 [고급 헌팅 참조](advanced-hunting-schema-tables.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="18f88-109">For information on other tables in the advanced hunting schema, [see the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="18f88-110">열 이름</span><span class="sxs-lookup"><span data-stu-id="18f88-110">Column name</span></span> | <span data-ttu-id="18f88-111">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="18f88-111">Data type</span></span> | <span data-ttu-id="18f88-112">설명</span><span class="sxs-lookup"><span data-stu-id="18f88-112">Description</span></span> |
|-------------|-----------|-------------|
| `Timestamp` | <span data-ttu-id="18f88-113">datetime</span><span class="sxs-lookup"><span data-stu-id="18f88-113">datetime</span></span> | <span data-ttu-id="18f88-114">이벤트가 기록된 날짜와 시간</span><span class="sxs-lookup"><span data-stu-id="18f88-114">Date and time when the event was recorded</span></span> |
| `AlertId` | <span data-ttu-id="18f88-115">문자열</span><span class="sxs-lookup"><span data-stu-id="18f88-115">string</span></span> | <span data-ttu-id="18f88-116">경고의 고유 식별자입니다.</span><span class="sxs-lookup"><span data-stu-id="18f88-116">Unique identifier for the alert</span></span> |
| `EntityType` | <span data-ttu-id="18f88-117">문자열</span><span class="sxs-lookup"><span data-stu-id="18f88-117">string</span></span> | <span data-ttu-id="18f88-118">파일, 프로세스, 장치 또는 사용자와 같은 개체의 유형입니다.</span><span class="sxs-lookup"><span data-stu-id="18f88-118">Type of object, such as a file, a process, a device, or a user</span></span> |
| `EvidenceRole` | <span data-ttu-id="18f88-119">문자열</span><span class="sxs-lookup"><span data-stu-id="18f88-119">string</span></span> | <span data-ttu-id="18f88-120">관계가 영향을 받는 지 또는 관련이 있는지를 나타내는 경고에 포함 되는 방법</span><span class="sxs-lookup"><span data-stu-id="18f88-120">How the entity is involved in an alert, indicating whether it is impacted or is merely related</span></span> |
| `SHA1` | <span data-ttu-id="18f88-121">문자열</span><span class="sxs-lookup"><span data-stu-id="18f88-121">string</span></span> | <span data-ttu-id="18f88-122">기록된 조치가 적용된 파일의 SHA-1</span><span class="sxs-lookup"><span data-stu-id="18f88-122">SHA-1 of the file that the recorded action was applied to</span></span> |
| `SHA256` | <span data-ttu-id="18f88-123">문자열</span><span class="sxs-lookup"><span data-stu-id="18f88-123">string</span></span> | <span data-ttu-id="18f88-124">기록된 조치가 적용된 파일의 SHA-256</span><span class="sxs-lookup"><span data-stu-id="18f88-124">SHA-256 of the file that the recorded action was applied to.</span></span> <span data-ttu-id="18f88-125">일반적으로이 필드는 채워지지 않습니다. 가능한 경우 SHA1 열을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="18f88-125">This field is usually not populated — use the SHA1 column when available.</span></span> |
| `RemoteIP` | <span data-ttu-id="18f88-126">문자열</span><span class="sxs-lookup"><span data-stu-id="18f88-126">string</span></span> | <span data-ttu-id="18f88-127">연결된 IP 주소</span><span class="sxs-lookup"><span data-stu-id="18f88-127">IP address that was being connected to</span></span> |
| `RemoteUrl` | <span data-ttu-id="18f88-128">문자열</span><span class="sxs-lookup"><span data-stu-id="18f88-128">string</span></span> | <span data-ttu-id="18f88-129">연결된 URL 또는 FQDN(정규화된 도메인 이름)</span><span class="sxs-lookup"><span data-stu-id="18f88-129">URL or fully qualified domain name (FQDN) that was being connected to</span></span> |
| `AccountName` | <span data-ttu-id="18f88-130">문자열</span><span class="sxs-lookup"><span data-stu-id="18f88-130">string</span></span> | <span data-ttu-id="18f88-131">계정의 사용자 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="18f88-131">User name of the account</span></span> |
| `AccountDomain` | <span data-ttu-id="18f88-132">문자열</span><span class="sxs-lookup"><span data-stu-id="18f88-132">string</span></span> | <span data-ttu-id="18f88-133">계정의 도메인</span><span class="sxs-lookup"><span data-stu-id="18f88-133">Domain of the account</span></span> |
| `AccountSid` | <span data-ttu-id="18f88-134">문자열</span><span class="sxs-lookup"><span data-stu-id="18f88-134">string</span></span> | <span data-ttu-id="18f88-135">계정의 SID (보안 식별자)</span><span class="sxs-lookup"><span data-stu-id="18f88-135">Security Identifier (SID) of the account</span></span> |
| `AccountObjectId` | <span data-ttu-id="18f88-136">문자열</span><span class="sxs-lookup"><span data-stu-id="18f88-136">string</span></span> | <span data-ttu-id="18f88-137">Azure AD의 계정에 대 한 고유 식별자입니다.</span><span class="sxs-lookup"><span data-stu-id="18f88-137">Unique identifier for the account in Azure AD</span></span> |
| `DeviceId` | <span data-ttu-id="18f88-138">문자열</span><span class="sxs-lookup"><span data-stu-id="18f88-138">string</span></span> | <span data-ttu-id="18f88-139">서비스에서 시스템의 고유 식별자</span><span class="sxs-lookup"><span data-stu-id="18f88-139">Unique identifier for the machine in the service</span></span> |
| `ThreatFamily` | <span data-ttu-id="18f88-140">문자열</span><span class="sxs-lookup"><span data-stu-id="18f88-140">string</span></span> | <span data-ttu-id="18f88-141">의심 스러운 또는 악성 파일 또는 프로세스가 분류 된 맬웨어 패밀리</span><span class="sxs-lookup"><span data-stu-id="18f88-141">Malware family that the suspicious or malicious file or process has been classified under</span></span> |
| `EvidenceDirection` | <span data-ttu-id="18f88-142">문자열</span><span class="sxs-lookup"><span data-stu-id="18f88-142">string</span></span> | <span data-ttu-id="18f88-143">엔터티가 네트워크 연결의 원본 또는 대상 인지를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="18f88-143">Indicates whether the entity is the source or the destination of a network connection</span></span> |
| `AdditionalFields` | <span data-ttu-id="18f88-144">문자열</span><span class="sxs-lookup"><span data-stu-id="18f88-144">string</span></span> | <span data-ttu-id="18f88-145">JSON 배열 형식의 이벤트에 대 한 추가 정보</span><span class="sxs-lookup"><span data-stu-id="18f88-145">Additional information about the event in JSON array format</span></span> |

## <a name="related-topics"></a><span data-ttu-id="18f88-146">관련 항목</span><span class="sxs-lookup"><span data-stu-id="18f88-146">Related topics</span></span>
- [<span data-ttu-id="18f88-147">사전 대응식 위협 탐지</span><span class="sxs-lookup"><span data-stu-id="18f88-147">Proactively hunt for threats</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="18f88-148">쿼리 언어 배우기</span><span class="sxs-lookup"><span data-stu-id="18f88-148">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="18f88-149">공유 쿼리 사용</span><span class="sxs-lookup"><span data-stu-id="18f88-149">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="18f88-150">여러 장치 및 전자 메일에서 위협을 탐지</span><span class="sxs-lookup"><span data-stu-id="18f88-150">Hunt for threats across devices and emails</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="18f88-151">스키마의 이해</span><span class="sxs-lookup"><span data-stu-id="18f88-151">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="18f88-152">쿼리 모범 사례 적용</span><span class="sxs-lookup"><span data-stu-id="18f88-152">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
