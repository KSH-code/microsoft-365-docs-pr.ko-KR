---
title: 고급 헌팅chema의 DeviceNetworkEvents 테이블
description: 고급 헌팅 스위마의 DeviceNetworkEvents 테이블에서 쿼리할 수 있는 네트워크 연결 이벤트에 대해 자세히 알아보시다.
keywords: 고급 헌팅, 위협 헌팅, 사이버 위협 헌팅, Microsoft 위협 방지, microsoft 365, mtp, m365, 검색, 쿼리, 원격 분석, 스마마 참조, kusto, 표, 열, 데이터 형식, devicenetworkevents, NetworkCommunicationEvents, 네트워크 연결, 원격 IP, 로컬 ip
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
ms.openlocfilehash: 65b9b7608b39f802cc82c62b87d7104ee4ff4304
ms.sourcegitcommit: 88ab08c0fa1acbc9e066009e131b9f2b0d506c64
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/10/2021
ms.locfileid: "50712429"
---
# <a name="devicenetworkevents"></a><span data-ttu-id="8de56-104">DeviceNetworkEvents</span><span class="sxs-lookup"><span data-stu-id="8de56-104">DeviceNetworkEvents</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="8de56-105">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="8de56-105">**Applies to:**</span></span>
- <span data-ttu-id="8de56-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="8de56-106">Microsoft 365 Defender</span></span>



<span data-ttu-id="8de56-107">고급 `DeviceNetworkEvents` 헌팅 [계획의](advanced-hunting-overview.md) 표에는 네트워크 연결 및 관련 이벤트에 대한 정보가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8de56-107">The `DeviceNetworkEvents` table in the [advanced hunting](advanced-hunting-overview.md) schema contains information about network connections and related events.</span></span> <span data-ttu-id="8de56-108">이 참조를 사용하여 이 표의 정보를 반환하는 쿼리를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="8de56-108">Use this reference to construct queries that return information from this table.</span></span>

>[!TIP]
> <span data-ttu-id="8de56-109">테이블에서 지원하는 이벤트 유형(값)에 대한 자세한 내용은 보안 센터에서 사용할 수 있는 기본 제공 `ActionType` Schema 참조를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="8de56-109">For detailed information about the events types (`ActionType` values) supported by a table, use the built-in schema reference available in the security center.</span></span>

<span data-ttu-id="8de56-110">고급 헌팅 스키마의 다른 표에 대한 자세한 내용은 [고급 헌팅 참조](advanced-hunting-schema-tables.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="8de56-110">For information on other tables in the advanced hunting schema, [see the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="8de56-111">열 이름</span><span class="sxs-lookup"><span data-stu-id="8de56-111">Column name</span></span> | <span data-ttu-id="8de56-112">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="8de56-112">Data type</span></span> | <span data-ttu-id="8de56-113">설명</span><span class="sxs-lookup"><span data-stu-id="8de56-113">Description</span></span> |
|-------------|-----------|-------------|
| `Timestamp` | <span data-ttu-id="8de56-114">datetime</span><span class="sxs-lookup"><span data-stu-id="8de56-114">datetime</span></span> | <span data-ttu-id="8de56-115">이벤트가 기록된 날짜와 시간</span><span class="sxs-lookup"><span data-stu-id="8de56-115">Date and time when the event was recorded</span></span> |
| `DeviceId` | <span data-ttu-id="8de56-116">문자열</span><span class="sxs-lookup"><span data-stu-id="8de56-116">string</span></span> | <span data-ttu-id="8de56-117">서비스에서 시스템의 고유 식별자</span><span class="sxs-lookup"><span data-stu-id="8de56-117">Unique identifier for the machine in the service</span></span> |
| `DeviceName` | <span data-ttu-id="8de56-118">문자열</span><span class="sxs-lookup"><span data-stu-id="8de56-118">string</span></span> | <span data-ttu-id="8de56-119">컴퓨터의 FQDN(정규화된 도메인 이름)</span><span class="sxs-lookup"><span data-stu-id="8de56-119">Fully qualified domain name (FQDN) of the machine</span></span> |
| `ActionType` | <span data-ttu-id="8de56-120">문자열</span><span class="sxs-lookup"><span data-stu-id="8de56-120">string</span></span> | <span data-ttu-id="8de56-121">이벤트를 트리거한 활동의 유형입니다.</span><span class="sxs-lookup"><span data-stu-id="8de56-121">Type of activity that triggered the event.</span></span> <span data-ttu-id="8de56-122">자세한 내용은 포털 내 [Schema 참조를](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center) 참조합니다.</span><span class="sxs-lookup"><span data-stu-id="8de56-122">See the [in-portal schema reference](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center) for details</span></span> |
| `RemoteIP` | <span data-ttu-id="8de56-123">문자열</span><span class="sxs-lookup"><span data-stu-id="8de56-123">string</span></span> | <span data-ttu-id="8de56-124">연결된 IP 주소</span><span class="sxs-lookup"><span data-stu-id="8de56-124">IP address that was being connected to</span></span> |
| `RemotePort` | <span data-ttu-id="8de56-125">int</span><span class="sxs-lookup"><span data-stu-id="8de56-125">int</span></span> | <span data-ttu-id="8de56-126">연결되고 있는 원격 장치의 TCP 포트</span><span class="sxs-lookup"><span data-stu-id="8de56-126">TCP port on the remote device that was being connected to</span></span> |
| `RemoteUrl` | <span data-ttu-id="8de56-127">문자열</span><span class="sxs-lookup"><span data-stu-id="8de56-127">string</span></span> | <span data-ttu-id="8de56-128">연결된 URL 또는 FQDN(정규화된 도메인 이름)</span><span class="sxs-lookup"><span data-stu-id="8de56-128">URL or fully qualified domain name (FQDN) that was being connected to</span></span> |
| `LocalIP` | <span data-ttu-id="8de56-129">문자열</span><span class="sxs-lookup"><span data-stu-id="8de56-129">string</span></span> | <span data-ttu-id="8de56-130">통신 중에 사용되는 로컬 컴퓨터로 할당된 IP 주소</span><span class="sxs-lookup"><span data-stu-id="8de56-130">IP address assigned to the local machine used during communication</span></span> |
| `LocalPort` | <span data-ttu-id="8de56-131">int</span><span class="sxs-lookup"><span data-stu-id="8de56-131">int</span></span> | <span data-ttu-id="8de56-132">통신 중에 사용되는 로컬 컴퓨터의 TCP 포트</span><span class="sxs-lookup"><span data-stu-id="8de56-132">TCP port on the local machine used during communication</span></span> |
| `Protocol` | <span data-ttu-id="8de56-133">문자열</span><span class="sxs-lookup"><span data-stu-id="8de56-133">string</span></span> | <span data-ttu-id="8de56-134">통신 중에 사용되는 프로토콜</span><span class="sxs-lookup"><span data-stu-id="8de56-134">Protocol used during the communication</span></span> |
| `LocalIPType` | <span data-ttu-id="8de56-135">문자열</span><span class="sxs-lookup"><span data-stu-id="8de56-135">string</span></span> | <span data-ttu-id="8de56-136">Ip 주소 유형(예: Public, Private, Reserved, Loopback, Teredo, FourToSixMapping 및 Broadcast)</span><span class="sxs-lookup"><span data-stu-id="8de56-136">Type of IP address, for example Public, Private, Reserved, Loopback, Teredo, FourToSixMapping, and Broadcast</span></span> |
| `RemoteIPType` | <span data-ttu-id="8de56-137">문자열</span><span class="sxs-lookup"><span data-stu-id="8de56-137">string</span></span> | <span data-ttu-id="8de56-138">Ip 주소 유형(예: Public, Private, Reserved, Loopback, Teredo, FourToSixMapping 및 Broadcast)</span><span class="sxs-lookup"><span data-stu-id="8de56-138">Type of IP address, for example Public, Private, Reserved, Loopback, Teredo, FourToSixMapping, and Broadcast</span></span> |
| `InitiatingProcessSHA1` | <span data-ttu-id="8de56-139">문자열</span><span class="sxs-lookup"><span data-stu-id="8de56-139">string</span></span> | <span data-ttu-id="8de56-140">이벤트를 시작한 프로세스(이미지 파일)의 SHA-1</span><span class="sxs-lookup"><span data-stu-id="8de56-140">SHA-1 of the process (image file) that initiated the event</span></span> |
| `InitiatingProcessSHA256` | <span data-ttu-id="8de56-141">문자열</span><span class="sxs-lookup"><span data-stu-id="8de56-141">string</span></span> | <span data-ttu-id="8de56-142">이벤트를 시작한 프로세스(이미지 파일)의 SHA-256입니다.</span><span class="sxs-lookup"><span data-stu-id="8de56-142">SHA-256 of the process (image file) that initiated the event.</span></span> <span data-ttu-id="8de56-143">일반적으로이 필드는 채워지지 않습니다. 가능한 경우 SHA1 열을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="8de56-143">This field is usually not populated — use the SHA1 column when available.</span></span> |
| `InitiatingProcessMD5` | <span data-ttu-id="8de56-144">문자열</span><span class="sxs-lookup"><span data-stu-id="8de56-144">string</span></span> | <span data-ttu-id="8de56-145">이벤트를 시작한 프로세스(이미지 파일)의 MD5 해시입니다.</span><span class="sxs-lookup"><span data-stu-id="8de56-145">MD5 hash of the process (image file) that initiated the event</span></span> |
| `InitiatingProcessFileName` | <span data-ttu-id="8de56-146">문자열</span><span class="sxs-lookup"><span data-stu-id="8de56-146">string</span></span> | <span data-ttu-id="8de56-147">이벤트를 시작한 프로세스의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="8de56-147">Name of the process that initiated the event</span></span> |
| `InitiatingProcessFileSize` | <span data-ttu-id="8de56-148">long</span><span class="sxs-lookup"><span data-stu-id="8de56-148">long</span></span> | <span data-ttu-id="8de56-149">이벤트를 담당하는 프로세스를 시작한 파일의 크기입니다.</span><span class="sxs-lookup"><span data-stu-id="8de56-149">Size of the file that ran the process responsible for the event</span></span> |
| `InitiatingProcessId` | <span data-ttu-id="8de56-150">int</span><span class="sxs-lookup"><span data-stu-id="8de56-150">int</span></span> | <span data-ttu-id="8de56-151">이벤트를 시작한 프로세스의 PID(프로세스 ID)입니다.</span><span class="sxs-lookup"><span data-stu-id="8de56-151">Process ID (PID) of the process that initiated the event</span></span> |
| `InitiatingProcessCommandLine` | <span data-ttu-id="8de56-152">문자열</span><span class="sxs-lookup"><span data-stu-id="8de56-152">string</span></span> | <span data-ttu-id="8de56-153">이벤트를 시작한 프로세스를 실행하는 데 사용되는 명령줄</span><span class="sxs-lookup"><span data-stu-id="8de56-153">Command line used to run the process that initiated the event</span></span> |
| `InitiatingProcessCreationTime` | <span data-ttu-id="8de56-154">datetime</span><span class="sxs-lookup"><span data-stu-id="8de56-154">datetime</span></span> | <span data-ttu-id="8de56-155">이벤트를 시작한 프로세스가 시작된 날짜 및 시간</span><span class="sxs-lookup"><span data-stu-id="8de56-155">Date and time when the process that initiated the event was started</span></span> |
| `InitiatingProcessFolderPath` | <span data-ttu-id="8de56-156">문자열</span><span class="sxs-lookup"><span data-stu-id="8de56-156">string</span></span> | <span data-ttu-id="8de56-157">이벤트를 시작한 프로세스(이미지 파일)가 포함된 폴더</span><span class="sxs-lookup"><span data-stu-id="8de56-157">Folder containing the process (image file) that initiated the event</span></span> |
| `InitiatingProcessParentFileName` | <span data-ttu-id="8de56-158">문자열</span><span class="sxs-lookup"><span data-stu-id="8de56-158">string</span></span> | <span data-ttu-id="8de56-159">이벤트를 담당하는 프로세스를 시작한 상위 프로세스의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="8de56-159">Name of the parent process that spawned the process responsible for the event</span></span> |
| `InitiatingProcessParentId` | <span data-ttu-id="8de56-160">int</span><span class="sxs-lookup"><span data-stu-id="8de56-160">int</span></span> | <span data-ttu-id="8de56-161">이벤트를 담당하는 프로세스를 시작한 상위 프로세스의 PID(프로세스 ID)입니다.</span><span class="sxs-lookup"><span data-stu-id="8de56-161">Process ID (PID) of the parent process that spawned the process responsible for the event</span></span> |
| `InitiatingProcessParentCreationTime` | <span data-ttu-id="8de56-162">datetime</span><span class="sxs-lookup"><span data-stu-id="8de56-162">datetime</span></span> | <span data-ttu-id="8de56-163">이벤트를 담당하는 프로세스의 부모가 시작된 날짜 및 시간입니다.</span><span class="sxs-lookup"><span data-stu-id="8de56-163">Date and time when the parent of the process responsible for the event was started</span></span> |
| `InitiatingProcessAccountDomain` | <span data-ttu-id="8de56-164">문자열</span><span class="sxs-lookup"><span data-stu-id="8de56-164">string</span></span> | <span data-ttu-id="8de56-165">이벤트를 담당하는 프로세스를 시작한 계정의 도메인입니다.</span><span class="sxs-lookup"><span data-stu-id="8de56-165">Domain of the account that ran the process responsible for the event</span></span> |
| `InitiatingProcessAccountName` | <span data-ttu-id="8de56-166">문자열</span><span class="sxs-lookup"><span data-stu-id="8de56-166">string</span></span> | <span data-ttu-id="8de56-167">이벤트를 담당하는 프로세스를 시작한 계정의 사용자 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="8de56-167">User name of the account that ran the process responsible for the event</span></span> |
| `InitiatingProcessAccountSid` | <span data-ttu-id="8de56-168">문자열</span><span class="sxs-lookup"><span data-stu-id="8de56-168">string</span></span> | <span data-ttu-id="8de56-169">이벤트를 담당하는 프로세스를 시작한 계정의 SID(보안 식별자)입니다.</span><span class="sxs-lookup"><span data-stu-id="8de56-169">Security Identifier (SID) of the account that ran the process responsible for the event</span></span> |
| `InitiatingProcessAccountUpn` | <span data-ttu-id="8de56-170">문자열</span><span class="sxs-lookup"><span data-stu-id="8de56-170">string</span></span> | <span data-ttu-id="8de56-171">이벤트를 담당하는 프로세스를 시작한 계정의 UPN(사용자 계정 이름)입니다.</span><span class="sxs-lookup"><span data-stu-id="8de56-171">User principal name (UPN) of the account that ran the process responsible for the event</span></span> |
| `InitiatingProcessIntegrityLevel` | <span data-ttu-id="8de56-172">문자열</span><span class="sxs-lookup"><span data-stu-id="8de56-172">string</span></span> | <span data-ttu-id="8de56-173">이벤트를 시작한 프로세스의 무결성 수준입니다.</span><span class="sxs-lookup"><span data-stu-id="8de56-173">Integrity level of the process that initiated the event.</span></span> <span data-ttu-id="8de56-174">Windows는 인터넷 다운로드에서 시작된 경우와 같이 특정 특성을 기반으로 프로세스에 무결성 수준을 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="8de56-174">Windows assigns integrity levels to processes based on certain characteristics, such as if they were launched from an internet download.</span></span> <span data-ttu-id="8de56-175">이러한 무결성 수준은 리소스에 대한 사용 권한에 영향을 미치기</span><span class="sxs-lookup"><span data-stu-id="8de56-175">These integrity levels influence permissions to resources</span></span> |
| `InitiatingProcessTokenElevation` | <span data-ttu-id="8de56-176">문자열</span><span class="sxs-lookup"><span data-stu-id="8de56-176">string</span></span> | <span data-ttu-id="8de56-177">이벤트를 시작한 프로세스에 적용되는 UAC(사용자 액세스 제어) 권한 상승의 유무를 나타내는 토큰 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="8de56-177">Token type indicating the presence or absence of User Access Control (UAC) privilege elevation applied to the process that initiated the event</span></span> |
| `ReportId` | <span data-ttu-id="8de56-178">long</span><span class="sxs-lookup"><span data-stu-id="8de56-178">long</span></span> | <span data-ttu-id="8de56-179">반복 카운터를 기반으로 하는 이벤트 식별자입니다.</span><span class="sxs-lookup"><span data-stu-id="8de56-179">Event identifier based on a repeating counter.</span></span> <span data-ttu-id="8de56-180">고유한 이벤트를 식별하려면 이 열을 DeviceName 및 Timestamp 열과 함께 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8de56-180">To identify unique events, this column must be used in conjunction with the DeviceName and Timestamp columns</span></span> |
| `AppGuardContainerId` | <span data-ttu-id="8de56-181">문자열</span><span class="sxs-lookup"><span data-stu-id="8de56-181">string</span></span> | <span data-ttu-id="8de56-182">Application Guard에서 브라우저 활동을 격리하기 위해 사용하는 가상화된 컨테이너의 식별자</span><span class="sxs-lookup"><span data-stu-id="8de56-182">Identifier for the virtualized container used by Application Guard to isolate browser activity</span></span> |
| `AdditionalFields` | <span data-ttu-id="8de56-183">문자열</span><span class="sxs-lookup"><span data-stu-id="8de56-183">string</span></span> | <span data-ttu-id="8de56-184">JSON 배열 형식의 이벤트에 대한 추가 정보</span><span class="sxs-lookup"><span data-stu-id="8de56-184">Additional information about the event in JSON array format</span></span> |

## <a name="related-topics"></a><span data-ttu-id="8de56-185">관련 항목</span><span class="sxs-lookup"><span data-stu-id="8de56-185">Related topics</span></span>
- [<span data-ttu-id="8de56-186">고급 헌팅 개요</span><span class="sxs-lookup"><span data-stu-id="8de56-186">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="8de56-187">쿼리 언어 배우기</span><span class="sxs-lookup"><span data-stu-id="8de56-187">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="8de56-188">공유 쿼리 사용</span><span class="sxs-lookup"><span data-stu-id="8de56-188">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="8de56-189">장치, 전자 메일, 앱 및 ID를 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="8de56-189">Hunt across devices, emails, apps, and identities</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="8de56-190">스키마의 이해</span><span class="sxs-lookup"><span data-stu-id="8de56-190">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="8de56-191">쿼리 모범 사례 적용</span><span class="sxs-lookup"><span data-stu-id="8de56-191">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
