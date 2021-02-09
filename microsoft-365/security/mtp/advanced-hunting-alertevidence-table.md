---
title: 고급 헌팅chema의 AlertEvidence 표
description: 고급 헌팅 스파이마의 AlertEvidence 표에서 경고와 관련된 정보에 대해 자세히
keywords: 고급 헌팅, 위협 헌팅, 사이버 위협 헌팅, Microsoft 위협 방지, microsoft 365, mtp, m365, 검색, 쿼리, 원격 분석, schema reference, kusto, table, column, data type, description, AlertInfo, alert, entities, evidence, file, IP address, device, machine, user, account
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
ms.openlocfilehash: 7457084d49c5a9fef4ef79abc7702c6b473efcd2
ms.sourcegitcommit: 005028af7c5a6b2e95f17a0037958131484d9e73
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/08/2021
ms.locfileid: "50145304"
---
# <a name="alertevidence"></a><span data-ttu-id="402ba-104">AlertEvidence</span><span class="sxs-lookup"><span data-stu-id="402ba-104">AlertEvidence</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="402ba-105">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="402ba-105">**Applies to:**</span></span>
- <span data-ttu-id="402ba-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="402ba-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="402ba-107">고급 헌팅 계획의 표에는 `AlertEvidence` 끝점용 Microsoft Defender, Office 365용 Microsoft Defender, Microsoft Cloud App Security 및 Id용 Microsoft Defender의 경고와 관련된 다양한 엔터티(파일, IP 주소, URL, 사용자 또는 장치)에 대한 정보가 포함되어 있습니다. [](advanced-hunting-overview.md)</span><span class="sxs-lookup"><span data-stu-id="402ba-107">The `AlertEvidence` table in the [advanced hunting](advanced-hunting-overview.md) schema contains information about various entities—files, IP addresses, URLs, users, or devices—associated with alerts from Microsoft  Defender for Endpoint, Microsoft Defender for Office 365, Microsoft Cloud App Security, and Microsoft Defender for Identity.</span></span> <span data-ttu-id="402ba-108">이 참조를 사용하여 이 표의 정보를 반환하는 쿼리를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="402ba-108">Use this reference to construct queries that return information from this table.</span></span>

<span data-ttu-id="402ba-109">고급 헌팅 스키마의 다른 표에 대한 자세한 내용은 [고급 헌팅 참조](advanced-hunting-schema-tables.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="402ba-109">For information on other tables in the advanced hunting schema, [see the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="402ba-110">열 이름</span><span class="sxs-lookup"><span data-stu-id="402ba-110">Column name</span></span> | <span data-ttu-id="402ba-111">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="402ba-111">Data type</span></span> | <span data-ttu-id="402ba-112">설명</span><span class="sxs-lookup"><span data-stu-id="402ba-112">Description</span></span> |
|-------------|-----------|-------------|
| `Timestamp` | <span data-ttu-id="402ba-113">datetime</span><span class="sxs-lookup"><span data-stu-id="402ba-113">datetime</span></span> | <span data-ttu-id="402ba-114">이벤트가 기록된 날짜와 시간</span><span class="sxs-lookup"><span data-stu-id="402ba-114">Date and time when the event was recorded</span></span> |
| `AlertId` | <span data-ttu-id="402ba-115">문자열</span><span class="sxs-lookup"><span data-stu-id="402ba-115">string</span></span> | <span data-ttu-id="402ba-116">경고의 고유 식별자입니다.</span><span class="sxs-lookup"><span data-stu-id="402ba-116">Unique identifier for the alert</span></span> |
| `ServiceSource` | <span data-ttu-id="402ba-117">문자열</span><span class="sxs-lookup"><span data-stu-id="402ba-117">string</span></span> | <span data-ttu-id="402ba-118">경고 정보를 제공한 제품 또는 서비스</span><span class="sxs-lookup"><span data-stu-id="402ba-118">Product or service that provided the alert information</span></span> |
| `EntityType` | <span data-ttu-id="402ba-119">문자열</span><span class="sxs-lookup"><span data-stu-id="402ba-119">string</span></span> | <span data-ttu-id="402ba-120">파일, 프로세스, 장치 또는 사용자와 같은 개체 유형</span><span class="sxs-lookup"><span data-stu-id="402ba-120">Type of object, such as a file, a process, a device, or a user</span></span> |
| `EvidenceRole` | <span data-ttu-id="402ba-121">문자열</span><span class="sxs-lookup"><span data-stu-id="402ba-121">string</span></span> | <span data-ttu-id="402ba-122">엔터티가 영향이 있는지 또는 관련이 있는지를 나타내는 경고에 엔터티가 관련된 방법</span><span class="sxs-lookup"><span data-stu-id="402ba-122">How the entity is involved in an alert, indicating whether it is impacted or is merely related</span></span> |
| `EvidenceDirection` | <span data-ttu-id="402ba-123">문자열</span><span class="sxs-lookup"><span data-stu-id="402ba-123">string</span></span> | <span data-ttu-id="402ba-124">엔터티가 네트워크 연결의 원본인지 아니면 대상인지를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="402ba-124">Indicates whether the entity is the source or the destination of a network connection</span></span> |
| `FileName` | <span data-ttu-id="402ba-125">문자열</span><span class="sxs-lookup"><span data-stu-id="402ba-125">string</span></span> | <span data-ttu-id="402ba-126">기록된 조치가 적용된 파일의 이름</span><span class="sxs-lookup"><span data-stu-id="402ba-126">Name of the file that the recorded action was applied to</span></span> |
| `FolderPath` | <span data-ttu-id="402ba-127">문자열</span><span class="sxs-lookup"><span data-stu-id="402ba-127">string</span></span> | <span data-ttu-id="402ba-128">기록된 작업이 적용된 파일이 들어 있는 폴더</span><span class="sxs-lookup"><span data-stu-id="402ba-128">Folder containing the file that the recorded action was applied to</span></span> |
| `SHA1` | <span data-ttu-id="402ba-129">문자열</span><span class="sxs-lookup"><span data-stu-id="402ba-129">string</span></span> | <span data-ttu-id="402ba-130">기록된 조치가 적용된 파일의 SHA-1</span><span class="sxs-lookup"><span data-stu-id="402ba-130">SHA-1 of the file that the recorded action was applied to</span></span> |
| `SHA256` | <span data-ttu-id="402ba-131">문자열</span><span class="sxs-lookup"><span data-stu-id="402ba-131">string</span></span> | <span data-ttu-id="402ba-132">기록된 조치가 적용된 파일의 SHA-256</span><span class="sxs-lookup"><span data-stu-id="402ba-132">SHA-256 of the file that the recorded action was applied to.</span></span> <span data-ttu-id="402ba-133">일반적으로 이 필드는 채워지지 않습니다. 사용 가능한 경우 SHA1 열을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="402ba-133">This field is usually not populated—use the SHA1 column when available.</span></span> |
| `FileSize` | <span data-ttu-id="402ba-134">int</span><span class="sxs-lookup"><span data-stu-id="402ba-134">int</span></span> | <span data-ttu-id="402ba-135">파일 크기(bytes)입니다.</span><span class="sxs-lookup"><span data-stu-id="402ba-135">Size of the file in bytes</span></span> |
| `ThreatFamily` | <span data-ttu-id="402ba-136">문자열</span><span class="sxs-lookup"><span data-stu-id="402ba-136">string</span></span> | <span data-ttu-id="402ba-137">의심스러운 파일 또는 악성 파일 또는 프로세스가 분류된 맬웨어 패밀리</span><span class="sxs-lookup"><span data-stu-id="402ba-137">Malware family that the suspicious or malicious file or process has been classified under</span></span> |
| `RemoteIP` | <span data-ttu-id="402ba-138">문자열</span><span class="sxs-lookup"><span data-stu-id="402ba-138">string</span></span> | <span data-ttu-id="402ba-139">연결된 IP 주소</span><span class="sxs-lookup"><span data-stu-id="402ba-139">IP address that was being connected to</span></span> |
| `RemoteUrl` | <span data-ttu-id="402ba-140">문자열</span><span class="sxs-lookup"><span data-stu-id="402ba-140">string</span></span> | <span data-ttu-id="402ba-141">연결된 URL 또는 FQDN(정규화된 도메인 이름)</span><span class="sxs-lookup"><span data-stu-id="402ba-141">URL or fully qualified domain name (FQDN) that was being connected to</span></span> |
| `AccountName` | <span data-ttu-id="402ba-142">문자열</span><span class="sxs-lookup"><span data-stu-id="402ba-142">string</span></span> | <span data-ttu-id="402ba-143">계정의 사용자 이름</span><span class="sxs-lookup"><span data-stu-id="402ba-143">User name of the account</span></span> |
| `AccountDomain` | <span data-ttu-id="402ba-144">문자열</span><span class="sxs-lookup"><span data-stu-id="402ba-144">string</span></span> | <span data-ttu-id="402ba-145">계정의 도메인</span><span class="sxs-lookup"><span data-stu-id="402ba-145">Domain of the account</span></span> |
| `AccountSid` | <span data-ttu-id="402ba-146">문자열</span><span class="sxs-lookup"><span data-stu-id="402ba-146">string</span></span> | <span data-ttu-id="402ba-147">계정의 SID(보안 식별자)입니다.</span><span class="sxs-lookup"><span data-stu-id="402ba-147">Security Identifier (SID) of the account</span></span> |
| `AccountObjectId` | <span data-ttu-id="402ba-148">문자열</span><span class="sxs-lookup"><span data-stu-id="402ba-148">string</span></span> | <span data-ttu-id="402ba-149">Azure Active Directory에서 계정의 고유 식별자</span><span class="sxs-lookup"><span data-stu-id="402ba-149">Unique identifier for the account in Azure Active Directory</span></span> |
| `AccountUpn` | <span data-ttu-id="402ba-150">문자열</span><span class="sxs-lookup"><span data-stu-id="402ba-150">string</span></span> | <span data-ttu-id="402ba-151">계정의 UPN(사용자 계정 이름)</span><span class="sxs-lookup"><span data-stu-id="402ba-151">User principal name (UPN) of the account</span></span> |
| `DeviceId` | <span data-ttu-id="402ba-152">문자열</span><span class="sxs-lookup"><span data-stu-id="402ba-152">string</span></span> | <span data-ttu-id="402ba-153">서비스에서 디바이스의 고유 식별자</span><span class="sxs-lookup"><span data-stu-id="402ba-153">Unique identifier for the device in the service</span></span> |
| `DeviceName` | <span data-ttu-id="402ba-154">문자열</span><span class="sxs-lookup"><span data-stu-id="402ba-154">string</span></span> | <span data-ttu-id="402ba-155">컴퓨터의 FQDN(정규화된 도메인 이름)</span><span class="sxs-lookup"><span data-stu-id="402ba-155">Fully qualified domain name (FQDN) of the machine</span></span> |
| `LocalIP` | <span data-ttu-id="402ba-156">문자열</span><span class="sxs-lookup"><span data-stu-id="402ba-156">string</span></span> | <span data-ttu-id="402ba-157">통신 중에 사용되는 로컬 장치에 할당된 IP 주소</span><span class="sxs-lookup"><span data-stu-id="402ba-157">IP address assigned to the local device used during communication</span></span> |
| `NetworkMessageId` | <span data-ttu-id="402ba-158">문자열</span><span class="sxs-lookup"><span data-stu-id="402ba-158">string</span></span> | <span data-ttu-id="402ba-159">Office 365에서 생성되는 전자 메일의 고유 식별자</span><span class="sxs-lookup"><span data-stu-id="402ba-159">Unique identifier for the email, generated by Office 365</span></span> |
| `EmailSubject` | <span data-ttu-id="402ba-160">문자열</span><span class="sxs-lookup"><span data-stu-id="402ba-160">string</span></span> | <span data-ttu-id="402ba-161">전자 메일 제목</span><span class="sxs-lookup"><span data-stu-id="402ba-161">Subject of the email</span></span> |
| `ApplicationId` | <span data-ttu-id="402ba-162">문자열</span><span class="sxs-lookup"><span data-stu-id="402ba-162">string</span></span> | <span data-ttu-id="402ba-163">응용 프로그램의 고유 식별자</span><span class="sxs-lookup"><span data-stu-id="402ba-163">Unique identifier for the application</span></span> |
| `Application` | <span data-ttu-id="402ba-164">문자열</span><span class="sxs-lookup"><span data-stu-id="402ba-164">string</span></span> | <span data-ttu-id="402ba-165">기록된 작업을 수행한 응용 프로그램</span><span class="sxs-lookup"><span data-stu-id="402ba-165">Application that performed the recorded action</span></span> |
| `ProcessCommandLine` | <span data-ttu-id="402ba-166">문자열</span><span class="sxs-lookup"><span data-stu-id="402ba-166">string</span></span> | <span data-ttu-id="402ba-167">새 프로세스를 만드는 데 사용되는 명령줄</span><span class="sxs-lookup"><span data-stu-id="402ba-167">Command line used to create the new process</span></span> |
| `AdditionalFields` | <span data-ttu-id="402ba-168">문자열</span><span class="sxs-lookup"><span data-stu-id="402ba-168">string</span></span> | <span data-ttu-id="402ba-169">JSON 배열 형식의 이벤트에 대한 추가 정보</span><span class="sxs-lookup"><span data-stu-id="402ba-169">Additional information about the event in JSON array format</span></span> |
| `RegistryKey` |<span data-ttu-id="402ba-170">문자열</span><span class="sxs-lookup"><span data-stu-id="402ba-170">string</span></span> | <span data-ttu-id="402ba-171">기록된 작업이 적용된 레지스트리 키</span><span class="sxs-lookup"><span data-stu-id="402ba-171">Registry key that the recorded action was applied to</span></span> |
| `RegistryValueName` |<span data-ttu-id="402ba-172">문자열</span><span class="sxs-lookup"><span data-stu-id="402ba-172">string</span></span> | <span data-ttu-id="402ba-173">기록된 작업이 적용된 레지스트리 값의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="402ba-173">Name of the registry value that the recorded action was applied to</span></span> |
| `RegistryValueData` |<span data-ttu-id="402ba-174">문자열</span><span class="sxs-lookup"><span data-stu-id="402ba-174">string</span></span> | <span data-ttu-id="402ba-175">기록된 작업이 적용된 레지스트리 값의 데이터</span><span class="sxs-lookup"><span data-stu-id="402ba-175">Data of the registry value that the recorded action was applied to</span></span> |

## <a name="related-topics"></a><span data-ttu-id="402ba-176">관련 주제</span><span class="sxs-lookup"><span data-stu-id="402ba-176">Related topics</span></span>
- [<span data-ttu-id="402ba-177">고급 헌팅 개요</span><span class="sxs-lookup"><span data-stu-id="402ba-177">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="402ba-178">쿼리 언어 배우기</span><span class="sxs-lookup"><span data-stu-id="402ba-178">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="402ba-179">공유 쿼리 사용</span><span class="sxs-lookup"><span data-stu-id="402ba-179">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="402ba-180">장치, 전자 메일, 앱 및 ID를 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="402ba-180">Hunt across devices, emails, apps, and identities</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="402ba-181">스키마의 이해</span><span class="sxs-lookup"><span data-stu-id="402ba-181">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="402ba-182">쿼리 모범 사례 적용</span><span class="sxs-lookup"><span data-stu-id="402ba-182">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
