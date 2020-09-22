---
title: 고급 구하기 스키마의 DeviceNetworkEvents 테이블
description: 고급 구하기 스키마의 DeviceNetworkEvents 테이블에서 쿼리할 수 있는 네트워크 연결 이벤트에 대해 자세히 알아보기
keywords: 고급 구하기, 위협 검색, 사이버 위협 검색, microsoft threat protection, microsoft 365, mtp, m365, 검색, 쿼리, 원격 분석, 스키마 참조, kusto, table, column, data type, devicenetworkevents, NetworkCommunicationEvents, network connection, 원격 ip, 로컬 ip
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
ms.openlocfilehash: be39e3f9c1216e0af44820aa9365492eefdf4c86
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/22/2020
ms.locfileid: "48197088"
---
# <a name="devicenetworkevents"></a><span data-ttu-id="39b2c-104">DeviceNetworkEvents</span><span class="sxs-lookup"><span data-stu-id="39b2c-104">DeviceNetworkEvents</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="39b2c-105">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="39b2c-105">**Applies to:**</span></span>
- <span data-ttu-id="39b2c-106">Microsoft 위협 방지</span><span class="sxs-lookup"><span data-stu-id="39b2c-106">Microsoft Threat Protection</span></span>



<span data-ttu-id="39b2c-107">`DeviceNetworkEvents` [고급 구하기](advanced-hunting-overview.md) 스키마의 표에는 네트워크 연결 및 관련 이벤트에 대 한 정보가 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="39b2c-107">The `DeviceNetworkEvents` table in the [advanced hunting](advanced-hunting-overview.md) schema contains information about network connections and related events.</span></span> <span data-ttu-id="39b2c-108">이 참조를 사용하여 이 표의 정보를 반환하는 쿼리를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="39b2c-108">Use this reference to construct queries that return information from this table.</span></span>

>[!TIP]
> <span data-ttu-id="39b2c-109">테이블에서 지 원하는 이벤트 유형 (값)에 대 한 자세한 내용은 `ActionType` 보안 센터에서 사용할 수 있는 [기본 제공 스키마 참조](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center) 를 사용 하십시오.</span><span class="sxs-lookup"><span data-stu-id="39b2c-109">For detailed information about the events types (`ActionType` values) supported by a table, use the [built-in schema reference](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center) available in the security center.</span></span>

<span data-ttu-id="39b2c-110">고급 헌팅 스키마의 다른 표에 대한 자세한 내용은 [고급 헌팅 참조](advanced-hunting-schema-tables.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="39b2c-110">For information on other tables in the advanced hunting schema, [see the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="39b2c-111">열 이름</span><span class="sxs-lookup"><span data-stu-id="39b2c-111">Column name</span></span> | <span data-ttu-id="39b2c-112">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="39b2c-112">Data type</span></span> | <span data-ttu-id="39b2c-113">설명</span><span class="sxs-lookup"><span data-stu-id="39b2c-113">Description</span></span> |
|-------------|-----------|-------------|
| `Timestamp` | <span data-ttu-id="39b2c-114">datetime</span><span class="sxs-lookup"><span data-stu-id="39b2c-114">datetime</span></span> | <span data-ttu-id="39b2c-115">이벤트가 기록된 날짜와 시간</span><span class="sxs-lookup"><span data-stu-id="39b2c-115">Date and time when the event was recorded</span></span> |
| `DeviceId` | <span data-ttu-id="39b2c-116">문자열</span><span class="sxs-lookup"><span data-stu-id="39b2c-116">string</span></span> | <span data-ttu-id="39b2c-117">서비스에서 시스템의 고유 식별자</span><span class="sxs-lookup"><span data-stu-id="39b2c-117">Unique identifier for the machine in the service</span></span> |
| `DeviceName` | <span data-ttu-id="39b2c-118">문자열</span><span class="sxs-lookup"><span data-stu-id="39b2c-118">string</span></span> | <span data-ttu-id="39b2c-119">컴퓨터의 FQDN(정규화된 도메인 이름)</span><span class="sxs-lookup"><span data-stu-id="39b2c-119">Fully qualified domain name (FQDN) of the machine</span></span> |
| `ActionType` | <span data-ttu-id="39b2c-120">문자열</span><span class="sxs-lookup"><span data-stu-id="39b2c-120">string</span></span> | <span data-ttu-id="39b2c-121">이벤트를 트리거한 작업의 유형입니다.</span><span class="sxs-lookup"><span data-stu-id="39b2c-121">Type of activity that triggered the event.</span></span> <span data-ttu-id="39b2c-122">자세한 내용은 [portal 스키마 참조](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center) 를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="39b2c-122">See the [in-portal schema reference](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center) for details</span></span> |
| `RemoteIP` | <span data-ttu-id="39b2c-123">문자열</span><span class="sxs-lookup"><span data-stu-id="39b2c-123">string</span></span> | <span data-ttu-id="39b2c-124">연결된 IP 주소</span><span class="sxs-lookup"><span data-stu-id="39b2c-124">IP address that was being connected to</span></span> |
| `RemotePort` | <span data-ttu-id="39b2c-125">int</span><span class="sxs-lookup"><span data-stu-id="39b2c-125">int</span></span> | <span data-ttu-id="39b2c-126">연결 된 원격 장치의 TCP 포트</span><span class="sxs-lookup"><span data-stu-id="39b2c-126">TCP port on the remote device that was being connected to</span></span> |
| `RemoteUrl` | <span data-ttu-id="39b2c-127">문자열</span><span class="sxs-lookup"><span data-stu-id="39b2c-127">string</span></span> | <span data-ttu-id="39b2c-128">연결된 URL 또는 FQDN(정규화된 도메인 이름)</span><span class="sxs-lookup"><span data-stu-id="39b2c-128">URL or fully qualified domain name (FQDN) that was being connected to</span></span> |
| `LocalIP` | <span data-ttu-id="39b2c-129">문자열</span><span class="sxs-lookup"><span data-stu-id="39b2c-129">string</span></span> | <span data-ttu-id="39b2c-130">통신 중에 사용 되는 로컬 컴퓨터에 할당 된 IP 주소</span><span class="sxs-lookup"><span data-stu-id="39b2c-130">IP address assigned to the local machine used during communication</span></span> |
| `LocalPort` | <span data-ttu-id="39b2c-131">int</span><span class="sxs-lookup"><span data-stu-id="39b2c-131">int</span></span> | <span data-ttu-id="39b2c-132">통신 중에 사용 되는 로컬 컴퓨터의 TCP 포트</span><span class="sxs-lookup"><span data-stu-id="39b2c-132">TCP port on the local machine used during communication</span></span> |
| `Protocol` | <span data-ttu-id="39b2c-133">문자열</span><span class="sxs-lookup"><span data-stu-id="39b2c-133">string</span></span> | <span data-ttu-id="39b2c-134">통신 중에 사용 되는 프로토콜</span><span class="sxs-lookup"><span data-stu-id="39b2c-134">Protocol used during the communication</span></span> |
| `LocalIPType` | <span data-ttu-id="39b2c-135">문자열</span><span class="sxs-lookup"><span data-stu-id="39b2c-135">string</span></span> | <span data-ttu-id="39b2c-136">IP 주소 유형 (예: Public, Private, Reserved, 루프백, Teredo, FourToSixMapping 및 브로드캐스트)</span><span class="sxs-lookup"><span data-stu-id="39b2c-136">Type of IP address, for example Public, Private, Reserved, Loopback, Teredo, FourToSixMapping, and Broadcast</span></span> |
| `RemoteIPType` | <span data-ttu-id="39b2c-137">문자열</span><span class="sxs-lookup"><span data-stu-id="39b2c-137">string</span></span> | <span data-ttu-id="39b2c-138">IP 주소 유형 (예: Public, Private, Reserved, 루프백, Teredo, FourToSixMapping 및 브로드캐스트)</span><span class="sxs-lookup"><span data-stu-id="39b2c-138">Type of IP address, for example Public, Private, Reserved, Loopback, Teredo, FourToSixMapping, and Broadcast</span></span> |
| `InitiatingProcessSHA1` | <span data-ttu-id="39b2c-139">문자열</span><span class="sxs-lookup"><span data-stu-id="39b2c-139">string</span></span> | <span data-ttu-id="39b2c-140">이벤트를 시작한 프로세스 (이미지 파일)의 SHA-1</span><span class="sxs-lookup"><span data-stu-id="39b2c-140">SHA-1 of the process (image file) that initiated the event</span></span> |
| `InitiatingProcessSHA256` | <span data-ttu-id="39b2c-141">문자열</span><span class="sxs-lookup"><span data-stu-id="39b2c-141">string</span></span> | <span data-ttu-id="39b2c-142">이벤트를 시작한 프로세스 (이미지 파일)의 SHA-256입니다.</span><span class="sxs-lookup"><span data-stu-id="39b2c-142">SHA-256 of the process (image file) that initiated the event.</span></span> <span data-ttu-id="39b2c-143">일반적으로이 필드는 채워지지 않습니다. 가능한 경우 SHA1 열을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="39b2c-143">This field is usually not populated — use the SHA1 column when available.</span></span> |
| `InitiatingProcessMD5` | <span data-ttu-id="39b2c-144">문자열</span><span class="sxs-lookup"><span data-stu-id="39b2c-144">string</span></span> | <span data-ttu-id="39b2c-145">이벤트를 시작한 프로세스 (이미지 파일)의 MD5 해시</span><span class="sxs-lookup"><span data-stu-id="39b2c-145">MD5 hash of the process (image file) that initiated the event</span></span> |
| `InitiatingProcessFileName` | <span data-ttu-id="39b2c-146">문자열</span><span class="sxs-lookup"><span data-stu-id="39b2c-146">string</span></span> | <span data-ttu-id="39b2c-147">이벤트를 시작한 프로세스의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="39b2c-147">Name of the process that initiated the event</span></span> |
| `InitiatingProcessId` | <span data-ttu-id="39b2c-148">int</span><span class="sxs-lookup"><span data-stu-id="39b2c-148">int</span></span> | <span data-ttu-id="39b2c-149">이벤트를 시작한 프로세스의 PID (프로세스 ID)</span><span class="sxs-lookup"><span data-stu-id="39b2c-149">Process ID (PID) of the process that initiated the event</span></span> |
| `InitiatingProcessCommandLine` | <span data-ttu-id="39b2c-150">문자열</span><span class="sxs-lookup"><span data-stu-id="39b2c-150">string</span></span> | <span data-ttu-id="39b2c-151">이벤트를 시작한 프로세스를 실행 하는 데 사용 되는 명령줄입니다.</span><span class="sxs-lookup"><span data-stu-id="39b2c-151">Command line used to run the process that initiated the event</span></span> |
| `InitiatingProcessCreationTime` | <span data-ttu-id="39b2c-152">datetime</span><span class="sxs-lookup"><span data-stu-id="39b2c-152">datetime</span></span> | <span data-ttu-id="39b2c-153">이벤트를 시작한 프로세스를 시작한 날짜 및 시간입니다.</span><span class="sxs-lookup"><span data-stu-id="39b2c-153">Date and time when the process that initiated the event was started</span></span> |
| `InitiatingProcessFolderPath` | <span data-ttu-id="39b2c-154">문자열</span><span class="sxs-lookup"><span data-stu-id="39b2c-154">string</span></span> | <span data-ttu-id="39b2c-155">이벤트를 시작한 프로세스 (이미지 파일)가 들어 있는 폴더</span><span class="sxs-lookup"><span data-stu-id="39b2c-155">Folder containing the process (image file) that initiated the event</span></span> |
| `InitiatingProcessParentFileName` | <span data-ttu-id="39b2c-156">문자열</span><span class="sxs-lookup"><span data-stu-id="39b2c-156">string</span></span> | <span data-ttu-id="39b2c-157">이벤트를 담당 하는 프로세스를 생성 한 상위 프로세스의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="39b2c-157">Name of the parent process that spawned the process responsible for the event</span></span> |
| `InitiatingProcessParentId` | <span data-ttu-id="39b2c-158">int</span><span class="sxs-lookup"><span data-stu-id="39b2c-158">int</span></span> | <span data-ttu-id="39b2c-159">이벤트를 담당 하는 프로세스를 생성 한 상위 프로세스의 PID (프로세스 ID)입니다.</span><span class="sxs-lookup"><span data-stu-id="39b2c-159">Process ID (PID) of the parent process that spawned the process responsible for the event</span></span> |
| `InitiatingProcessParentCreationTime` | <span data-ttu-id="39b2c-160">datetime</span><span class="sxs-lookup"><span data-stu-id="39b2c-160">datetime</span></span> | <span data-ttu-id="39b2c-161">이벤트를 담당 하는 프로세스의 부모를 시작한 날짜 및 시간입니다.</span><span class="sxs-lookup"><span data-stu-id="39b2c-161">Date and time when the parent of the process responsible for the event was started</span></span> |
| `InitiatingProcessAccountDomain` | <span data-ttu-id="39b2c-162">문자열</span><span class="sxs-lookup"><span data-stu-id="39b2c-162">string</span></span> | <span data-ttu-id="39b2c-163">이벤트를 담당 하는 프로세스를 실행 한 계정의 도메인입니다.</span><span class="sxs-lookup"><span data-stu-id="39b2c-163">Domain of the account that ran the process responsible for the event</span></span> |
| `InitiatingProcessAccountName` | <span data-ttu-id="39b2c-164">문자열</span><span class="sxs-lookup"><span data-stu-id="39b2c-164">string</span></span> | <span data-ttu-id="39b2c-165">이벤트를 담당 하는 프로세스를 실행 한 계정의 사용자 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="39b2c-165">User name of the account that ran the process responsible for the event</span></span> |
| `InitiatingProcessAccountSid` | <span data-ttu-id="39b2c-166">문자열</span><span class="sxs-lookup"><span data-stu-id="39b2c-166">string</span></span> | <span data-ttu-id="39b2c-167">이벤트를 담당 하는 프로세스를 실행 한 계정의 SID (보안 식별자)입니다.</span><span class="sxs-lookup"><span data-stu-id="39b2c-167">Security Identifier (SID) of the account that ran the process responsible for the event</span></span> |
| `InitiatingProcessIntegrityLevel` | <span data-ttu-id="39b2c-168">문자열</span><span class="sxs-lookup"><span data-stu-id="39b2c-168">string</span></span> | <span data-ttu-id="39b2c-169">이벤트를 시작한 프로세스의 무결성 수준입니다.</span><span class="sxs-lookup"><span data-stu-id="39b2c-169">Integrity level of the process that initiated the event.</span></span> <span data-ttu-id="39b2c-170">Windows에서는 인터넷 다운로드에서 시작 된 경우와 같이 특정 특성에 따라 프로세스에 무결성 수준을 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="39b2c-170">Windows assigns integrity levels to processes based on certain characteristics, such as if they were launched from an internet download.</span></span> <span data-ttu-id="39b2c-171">이러한 무결성 수준은 리소스에 대 한 사용 권한에 영향을 줍니다.</span><span class="sxs-lookup"><span data-stu-id="39b2c-171">These integrity levels influence permissions to resources</span></span> |
| `InitiatingProcessTokenElevation` | <span data-ttu-id="39b2c-172">문자열</span><span class="sxs-lookup"><span data-stu-id="39b2c-172">string</span></span> | <span data-ttu-id="39b2c-173">이벤트를 시작한 프로세스에 UAC (사용자 액세스 제어) 권한 상승이 적용 되었는지 여부를 나타내는 토큰 유형입니다.</span><span class="sxs-lookup"><span data-stu-id="39b2c-173">Token type indicating the presence or absence of User Access Control (UAC) privilege elevation applied to the process that initiated the event</span></span> |
| `ReportId` | <span data-ttu-id="39b2c-174">long</span><span class="sxs-lookup"><span data-stu-id="39b2c-174">long</span></span> | <span data-ttu-id="39b2c-175">반복 카운터를 기반으로 하는 이벤트 식별자입니다.</span><span class="sxs-lookup"><span data-stu-id="39b2c-175">Event identifier based on a repeating counter.</span></span> <span data-ttu-id="39b2c-176">고유 이벤트를 식별 하려면이 열을 장치 이름 및 타임 스탬프 열과 함께 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="39b2c-176">To identify unique events, this column must be used in conjunction with the DeviceName and Timestamp columns</span></span> |
| `AppGuardContainerId` | <span data-ttu-id="39b2c-177">문자열</span><span class="sxs-lookup"><span data-stu-id="39b2c-177">string</span></span> | <span data-ttu-id="39b2c-178">응용 프로그램 가드가 브라우저 활동을 격리 하는 데 사용 하는 가상화 된 컨테이너의 식별자입니다.</span><span class="sxs-lookup"><span data-stu-id="39b2c-178">Identifier for the virtualized container used by Application Guard to isolate browser activity</span></span> |

## <a name="related-topics"></a><span data-ttu-id="39b2c-179">관련 항목</span><span class="sxs-lookup"><span data-stu-id="39b2c-179">Related topics</span></span>
- [<span data-ttu-id="39b2c-180">고급 헌팅 개요</span><span class="sxs-lookup"><span data-stu-id="39b2c-180">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="39b2c-181">쿼리 언어 배우기</span><span class="sxs-lookup"><span data-stu-id="39b2c-181">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="39b2c-182">공유 쿼리 사용</span><span class="sxs-lookup"><span data-stu-id="39b2c-182">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="39b2c-183">기기, 전자 메일, 앱 및 ID를 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="39b2c-183">Hunt across devices, emails, apps, and identities</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="39b2c-184">스키마의 이해</span><span class="sxs-lookup"><span data-stu-id="39b2c-184">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="39b2c-185">쿼리 모범 사례 적용</span><span class="sxs-lookup"><span data-stu-id="39b2c-185">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
