---
title: 고급 구하기 스키마의 DeviceNetworkEvents 테이블
description: 고급 구하기 스키마의 DeviceNetworkEvents 테이블에서 쿼리할 수 있는 네트워크 연결 이벤트에 대해 자세히 알아보기
keywords: 고급 구하기, 위협 검색, 사이버 위협 사냥, microsoft threat protection, microsoft 365, mtp, m365, 검색, 쿼리, 원격 분석, 스키마 참조, kusto, table, column, data type, devicenetworkevents, NetworkCommunicationEvents, network 연결, 원격 ip, 로컬 ip
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
ms.openlocfilehash: 2e7999fef43adb372947d9edf92b84ac67f347fe
ms.sourcegitcommit: 74bf600424d0cb7b9d16b4f391aeda7875058be1
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/24/2020
ms.locfileid: "42235007"
---
# <a name="devicenetworkevents"></a><span data-ttu-id="ad885-104">DeviceNetworkEvents</span><span class="sxs-lookup"><span data-stu-id="ad885-104">DeviceNetworkEvents</span></span>

<span data-ttu-id="ad885-105">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="ad885-105">**Applies to:**</span></span>
- <span data-ttu-id="ad885-106">Microsoft 위협 방지</span><span class="sxs-lookup"><span data-stu-id="ad885-106">Microsoft Threat Protection</span></span>



<span data-ttu-id="ad885-107">`DeviceNetworkEvents` [고급 구하기](advanced-hunting-overview.md) 스키마의 표에는 네트워크 연결 및 관련 이벤트에 대 한 정보가 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ad885-107">The `DeviceNetworkEvents` table in the [advanced hunting](advanced-hunting-overview.md) schema contains information about network connections and related events.</span></span> <span data-ttu-id="ad885-108">이 참조를 사용하여 이 표의 정보를 반환하는 쿼리를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="ad885-108">Use this reference to construct queries that return information from this table.</span></span>

<span data-ttu-id="ad885-109">고급 헌팅 스키마의 다른 표에 대한 자세한 내용은 [고급 헌팅 참조](advanced-hunting-schema-tables.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="ad885-109">For information on other tables in the advanced hunting schema, [see the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="ad885-110">열 이름</span><span class="sxs-lookup"><span data-stu-id="ad885-110">Column name</span></span> | <span data-ttu-id="ad885-111">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="ad885-111">Data type</span></span> | <span data-ttu-id="ad885-112">설명</span><span class="sxs-lookup"><span data-stu-id="ad885-112">Description</span></span> |
|-------------|-----------|-------------|
| `Timestamp` | <span data-ttu-id="ad885-113">datetime</span><span class="sxs-lookup"><span data-stu-id="ad885-113">datetime</span></span> | <span data-ttu-id="ad885-114">이벤트가 기록된 날짜와 시간</span><span class="sxs-lookup"><span data-stu-id="ad885-114">Date and time when the event was recorded</span></span> |
| `DeviceId` | <span data-ttu-id="ad885-115">문자열</span><span class="sxs-lookup"><span data-stu-id="ad885-115">string</span></span> | <span data-ttu-id="ad885-116">서비스에서 시스템의 고유 식별자</span><span class="sxs-lookup"><span data-stu-id="ad885-116">Unique identifier for the machine in the service</span></span> |
| `DeviceName` | <span data-ttu-id="ad885-117">문자열</span><span class="sxs-lookup"><span data-stu-id="ad885-117">string</span></span> | <span data-ttu-id="ad885-118">컴퓨터의 FQDN(정규화된 도메인 이름)</span><span class="sxs-lookup"><span data-stu-id="ad885-118">Fully qualified domain name (FQDN) of the machine</span></span> |
| `ActionType` | <span data-ttu-id="ad885-119">문자열</span><span class="sxs-lookup"><span data-stu-id="ad885-119">string</span></span> | <span data-ttu-id="ad885-120">이벤트를 트리거한 작업의 유형입니다.</span><span class="sxs-lookup"><span data-stu-id="ad885-120">Type of activity that triggered the event</span></span> |
| `RemoteIP` | <span data-ttu-id="ad885-121">문자열</span><span class="sxs-lookup"><span data-stu-id="ad885-121">string</span></span> | <span data-ttu-id="ad885-122">연결된 IP 주소</span><span class="sxs-lookup"><span data-stu-id="ad885-122">IP address that was being connected to</span></span> |
| `RemotePort` | <span data-ttu-id="ad885-123">int</span><span class="sxs-lookup"><span data-stu-id="ad885-123">int</span></span> | <span data-ttu-id="ad885-124">연결 된 원격 장치의 TCP 포트</span><span class="sxs-lookup"><span data-stu-id="ad885-124">TCP port on the remote device that was being connected to</span></span> |
| `RemoteUrl` | <span data-ttu-id="ad885-125">문자열</span><span class="sxs-lookup"><span data-stu-id="ad885-125">string</span></span> | <span data-ttu-id="ad885-126">연결된 URL 또는 FQDN(정규화된 도메인 이름)</span><span class="sxs-lookup"><span data-stu-id="ad885-126">URL or fully qualified domain name (FQDN) that was being connected to</span></span> |
| `LocalIP` | <span data-ttu-id="ad885-127">문자열</span><span class="sxs-lookup"><span data-stu-id="ad885-127">string</span></span> | <span data-ttu-id="ad885-128">통신 중에 사용 되는 로컬 컴퓨터에 할당 된 IP 주소</span><span class="sxs-lookup"><span data-stu-id="ad885-128">IP address assigned to the local machine used during communication</span></span> |
| `LocalPort` | <span data-ttu-id="ad885-129">int</span><span class="sxs-lookup"><span data-stu-id="ad885-129">int</span></span> | <span data-ttu-id="ad885-130">통신 중에 사용 되는 로컬 컴퓨터의 TCP 포트</span><span class="sxs-lookup"><span data-stu-id="ad885-130">TCP port on the local machine used during communication</span></span> |
| `Protocol` | <span data-ttu-id="ad885-131">문자열</span><span class="sxs-lookup"><span data-stu-id="ad885-131">string</span></span> | <span data-ttu-id="ad885-132">사용 되는 IP 프로토콜 (TCP 또는 UDP에 관계 없음)</span><span class="sxs-lookup"><span data-stu-id="ad885-132">IP protocol used, whether TCP or UDP</span></span> |
| `LocalIPType` | <span data-ttu-id="ad885-133">문자열</span><span class="sxs-lookup"><span data-stu-id="ad885-133">string</span></span> | <span data-ttu-id="ad885-134">IP 주소 유형 (예: Public, Private, Reserved, 루프백, Teredo, FourToSixMapping 및 브로드캐스트)</span><span class="sxs-lookup"><span data-stu-id="ad885-134">Type of IP address, for example Public, Private, Reserved, Loopback, Teredo, FourToSixMapping, and Broadcast</span></span> |
| `RemoteIPType` | <span data-ttu-id="ad885-135">문자열</span><span class="sxs-lookup"><span data-stu-id="ad885-135">string</span></span> | <span data-ttu-id="ad885-136">IP 주소 유형 (예: Public, Private, Reserved, 루프백, Teredo, FourToSixMapping 및 브로드캐스트)</span><span class="sxs-lookup"><span data-stu-id="ad885-136">Type of IP address, for example Public, Private, Reserved, Loopback, Teredo, FourToSixMapping, and Broadcast</span></span> |
| `InitiatingProcessSHA1` | <span data-ttu-id="ad885-137">문자열</span><span class="sxs-lookup"><span data-stu-id="ad885-137">string</span></span> | <span data-ttu-id="ad885-138">이벤트를 시작한 프로세스 (이미지 파일)의 SHA-1</span><span class="sxs-lookup"><span data-stu-id="ad885-138">SHA-1 of the process (image file) that initiated the event</span></span> |
| `InitiatingProcessMD5` | <span data-ttu-id="ad885-139">문자열</span><span class="sxs-lookup"><span data-stu-id="ad885-139">string</span></span> | <span data-ttu-id="ad885-140">이벤트를 시작한 프로세스 (이미지 파일)의 MD5 해시</span><span class="sxs-lookup"><span data-stu-id="ad885-140">MD5 hash of the process (image file) that initiated the event</span></span> |
| `InitiatingProcessFileName` | <span data-ttu-id="ad885-141">문자열</span><span class="sxs-lookup"><span data-stu-id="ad885-141">string</span></span> | <span data-ttu-id="ad885-142">이벤트를 시작한 프로세스의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="ad885-142">Name of the process that initiated the event</span></span> |
| `InitiatingProcessId` | <span data-ttu-id="ad885-143">int</span><span class="sxs-lookup"><span data-stu-id="ad885-143">int</span></span> | <span data-ttu-id="ad885-144">이벤트를 시작한 프로세스의 PID (프로세스 ID)</span><span class="sxs-lookup"><span data-stu-id="ad885-144">Process ID (PID) of the process that initiated the event</span></span> |
| `InitiatingProcessCommandLine` | <span data-ttu-id="ad885-145">문자열</span><span class="sxs-lookup"><span data-stu-id="ad885-145">string</span></span> | <span data-ttu-id="ad885-146">이벤트를 시작한 프로세스를 실행 하는 데 사용 되는 명령줄입니다.</span><span class="sxs-lookup"><span data-stu-id="ad885-146">Command line used to run the process that initiated the event</span></span> |
| `InitiatingProcessCreationTime` | <span data-ttu-id="ad885-147">datetime</span><span class="sxs-lookup"><span data-stu-id="ad885-147">datetime</span></span> | <span data-ttu-id="ad885-148">이벤트를 시작한 프로세스를 시작한 날짜 및 시간입니다.</span><span class="sxs-lookup"><span data-stu-id="ad885-148">Date and time when the process that initiated the event was started</span></span> |
| `InitiatingProcessFolderPath` | <span data-ttu-id="ad885-149">문자열</span><span class="sxs-lookup"><span data-stu-id="ad885-149">string</span></span> | <span data-ttu-id="ad885-150">이벤트를 시작한 프로세스 (이미지 파일)가 들어 있는 폴더</span><span class="sxs-lookup"><span data-stu-id="ad885-150">Folder containing the process (image file) that initiated the event</span></span> |
| `InitiatingProcessParentFileName` | <span data-ttu-id="ad885-151">문자열</span><span class="sxs-lookup"><span data-stu-id="ad885-151">string</span></span> | <span data-ttu-id="ad885-152">이벤트를 담당 하는 프로세스를 생성 한 상위 프로세스의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="ad885-152">Name of the parent process that spawned the process responsible for the event</span></span> |
| `InitiatingProcessParentId` | <span data-ttu-id="ad885-153">int</span><span class="sxs-lookup"><span data-stu-id="ad885-153">int</span></span> | <span data-ttu-id="ad885-154">이벤트를 담당 하는 프로세스를 생성 한 상위 프로세스의 PID (프로세스 ID)입니다.</span><span class="sxs-lookup"><span data-stu-id="ad885-154">Process ID (PID) of the parent process that spawned the process responsible for the event</span></span> |
| `InitiatingProcessParentCreationTime` | <span data-ttu-id="ad885-155">datetime</span><span class="sxs-lookup"><span data-stu-id="ad885-155">datetime</span></span> | <span data-ttu-id="ad885-156">이벤트를 담당 하는 프로세스의 부모를 시작한 날짜 및 시간입니다.</span><span class="sxs-lookup"><span data-stu-id="ad885-156">Date and time when the parent of the process responsible for the event was started</span></span> |
| `InitiatingProcessAccountDomain` | <span data-ttu-id="ad885-157">문자열</span><span class="sxs-lookup"><span data-stu-id="ad885-157">string</span></span> | <span data-ttu-id="ad885-158">이벤트를 담당 하는 프로세스를 실행 한 계정의 도메인입니다.</span><span class="sxs-lookup"><span data-stu-id="ad885-158">Domain of the account that ran the process responsible for the event</span></span> |
| `InitiatingProcessAccountName` | <span data-ttu-id="ad885-159">문자열</span><span class="sxs-lookup"><span data-stu-id="ad885-159">string</span></span> | <span data-ttu-id="ad885-160">이벤트를 담당 하는 프로세스를 실행 한 계정의 사용자 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="ad885-160">User name of the account that ran the process responsible for the event</span></span> |
| `InitiatingProcessAccountSid` | <span data-ttu-id="ad885-161">문자열</span><span class="sxs-lookup"><span data-stu-id="ad885-161">string</span></span> | <span data-ttu-id="ad885-162">이벤트를 담당 하는 프로세스를 실행 한 계정의 SID (보안 식별자)입니다.</span><span class="sxs-lookup"><span data-stu-id="ad885-162">Security Identifier (SID) of the account that ran the process responsible for the event</span></span> |
| `InitiatingProcessIntegrityLevel` | <span data-ttu-id="ad885-163">문자열</span><span class="sxs-lookup"><span data-stu-id="ad885-163">string</span></span> | <span data-ttu-id="ad885-164">이벤트를 시작한 프로세스의 무결성 수준입니다.</span><span class="sxs-lookup"><span data-stu-id="ad885-164">Integrity level of the process that initiated the event.</span></span> <span data-ttu-id="ad885-165">Windows에서는 인터넷 다운로드에서 시작 된 경우와 같이 특정 특성에 따라 프로세스에 무결성 수준을 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="ad885-165">Windows assigns integrity levels to processes based on certain characteristics, such as if they were launched from an internet download.</span></span> <span data-ttu-id="ad885-166">이러한 무결성 수준은 리소스에 대 한 사용 권한에 영향을 줍니다.</span><span class="sxs-lookup"><span data-stu-id="ad885-166">These integrity levels influence permissions to resources</span></span> |
| `InitiatingProcessTokenElevation` | <span data-ttu-id="ad885-167">문자열</span><span class="sxs-lookup"><span data-stu-id="ad885-167">string</span></span> | <span data-ttu-id="ad885-168">이벤트를 시작한 프로세스에 UAC (사용자 액세스 제어) 권한 상승이 적용 되었는지 여부를 나타내는 토큰 유형입니다.</span><span class="sxs-lookup"><span data-stu-id="ad885-168">Token type indicating the presence or absence of User Access Control (UAC) privilege elevation applied to the process that initiated the event</span></span> |
| `ReportId` | <span data-ttu-id="ad885-169">long</span><span class="sxs-lookup"><span data-stu-id="ad885-169">long</span></span> | <span data-ttu-id="ad885-170">반복 카운터를 기반으로 하는 이벤트 식별자입니다.</span><span class="sxs-lookup"><span data-stu-id="ad885-170">Event identifier based on a repeating counter.</span></span> <span data-ttu-id="ad885-171">고유 이벤트를 식별 하려면이 열을 장치 이름 및 타임 스탬프 열과 함께 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ad885-171">To identify unique events, this column must be used in conjunction with the DeviceName and Timestamp columns</span></span> |
| `AppGuardContainerId` | <span data-ttu-id="ad885-172">문자열</span><span class="sxs-lookup"><span data-stu-id="ad885-172">string</span></span> | <span data-ttu-id="ad885-173">응용 프로그램 가드가 브라우저 활동을 격리 하는 데 사용 하는 가상화 된 컨테이너의 식별자입니다.</span><span class="sxs-lookup"><span data-stu-id="ad885-173">Identifier for the virtualized container used by Application Guard to isolate browser activity</span></span> |

## <a name="related-topics"></a><span data-ttu-id="ad885-174">관련 항목</span><span class="sxs-lookup"><span data-stu-id="ad885-174">Related topics</span></span>
- [<span data-ttu-id="ad885-175">사전 대응식 위협 탐지</span><span class="sxs-lookup"><span data-stu-id="ad885-175">Proactively hunt for threats</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="ad885-176">쿼리 언어 배우기</span><span class="sxs-lookup"><span data-stu-id="ad885-176">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="ad885-177">공유 쿼리 사용</span><span class="sxs-lookup"><span data-stu-id="ad885-177">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="ad885-178">여러 장치 및 전자 메일에서 위협을 탐지</span><span class="sxs-lookup"><span data-stu-id="ad885-178">Hunt for threats across devices and emails</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="ad885-179">스키마의 이해</span><span class="sxs-lookup"><span data-stu-id="ad885-179">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="ad885-180">쿼리 모범 사례 적용</span><span class="sxs-lookup"><span data-stu-id="ad885-180">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
