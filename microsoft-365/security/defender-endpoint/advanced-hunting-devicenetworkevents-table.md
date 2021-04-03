---
title: 고급 헌팅chema의 DeviceNetworkEvents 테이블
description: 고급 헌팅 스위마의 DeviceNetworkEvents 테이블에서 쿼리할 수 있는 네트워크 연결 이벤트에 대해 자세히 알아보시다.
keywords: 고급 헌팅, 위협 헌팅, 사이버 위협 헌팅, 검색, 쿼리, 원격 분석, schema 참조, kusto, 표, 열, 데이터 형식, devicenetworkevents, 네트워크 연결, 원격 ip, 로컬 ip, NetworkCommunicationEvents
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
ms.technology: mde
ms.openlocfilehash: de31cb923a0584f45cb92340cf7e1c6b5ca5e9a0
ms.sourcegitcommit: 582555d2b4ef5f2e2494ffdeab2c1d49e5d6b724
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/01/2021
ms.locfileid: "51500769"
---
# <a name="devicenetworkevents"></a><span data-ttu-id="a641f-104">DeviceNetworkEvents</span><span class="sxs-lookup"><span data-stu-id="a641f-104">DeviceNetworkEvents</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="a641f-105">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="a641f-105">**Applies to:**</span></span>
- [<span data-ttu-id="a641f-106">엔드포인트용 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="a641f-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)


><span data-ttu-id="a641f-107">Endpoint용 Defender를 경험하고 싶나요?</span><span class="sxs-lookup"><span data-stu-id="a641f-107">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="a641f-108">무료 평가판에 등록합니다.</span><span class="sxs-lookup"><span data-stu-id="a641f-108">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-advancedhuntingref-abovefoldlink)

<span data-ttu-id="a641f-109">고급 `DeviceNetworkEvents` 헌팅 [계획의](advanced-hunting-overview.md) 표에는 네트워크 연결 및 관련 이벤트에 대한 정보가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a641f-109">The `DeviceNetworkEvents` table in the [advanced hunting](advanced-hunting-overview.md) schema contains information about network connections and related events.</span></span> <span data-ttu-id="a641f-110">이 참조를 사용하여 표의 정보를 반환하는 쿼리를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="a641f-110">Use this reference to construct queries that return information from the table.</span></span>

<span data-ttu-id="a641f-111">고급 헌팅 스마의 다른 표에 대한 자세한 내용은 고급 헌팅 스마 [참조 를 참조하세요.](advanced-hunting-schema-reference.md)</span><span class="sxs-lookup"><span data-stu-id="a641f-111">For information on other tables in the advanced hunting schema, see [the advanced hunting schema reference](advanced-hunting-schema-reference.md).</span></span>

| <span data-ttu-id="a641f-112">열 이름</span><span class="sxs-lookup"><span data-stu-id="a641f-112">Column name</span></span> | <span data-ttu-id="a641f-113">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="a641f-113">Data type</span></span> | <span data-ttu-id="a641f-114">설명</span><span class="sxs-lookup"><span data-stu-id="a641f-114">Description</span></span> |
|-------------|-----------|-------------|
| `Timestamp` | <span data-ttu-id="a641f-115">datetime</span><span class="sxs-lookup"><span data-stu-id="a641f-115">datetime</span></span> | <span data-ttu-id="a641f-116">이벤트가 기록된 날짜와 시간</span><span class="sxs-lookup"><span data-stu-id="a641f-116">Date and time when the event was recorded</span></span> |
| `DeviceId` | <span data-ttu-id="a641f-117">문자열</span><span class="sxs-lookup"><span data-stu-id="a641f-117">string</span></span> | <span data-ttu-id="a641f-118">서비스에서 디바이스의 고유 식별자</span><span class="sxs-lookup"><span data-stu-id="a641f-118">Unique identifier for the device in the service</span></span> |
| `DeviceName` | <span data-ttu-id="a641f-119">문자열</span><span class="sxs-lookup"><span data-stu-id="a641f-119">string</span></span> | <span data-ttu-id="a641f-120">장치의 FQDN(FQDN)</span><span class="sxs-lookup"><span data-stu-id="a641f-120">Fully qualified domain name (FQDN) of the device</span></span> |
| `ActionType` | <span data-ttu-id="a641f-121">문자열</span><span class="sxs-lookup"><span data-stu-id="a641f-121">string</span></span> | <span data-ttu-id="a641f-122">이벤트를 트리거한 활동 유형</span><span class="sxs-lookup"><span data-stu-id="a641f-122">Type of activity that triggered the event</span></span> |
| `RemoteIP` | <span data-ttu-id="a641f-123">문자열</span><span class="sxs-lookup"><span data-stu-id="a641f-123">string</span></span> | <span data-ttu-id="a641f-124">연결된 IP 주소</span><span class="sxs-lookup"><span data-stu-id="a641f-124">IP address that was being connected to</span></span> |
| `RemotePort` | <span data-ttu-id="a641f-125">int</span><span class="sxs-lookup"><span data-stu-id="a641f-125">int</span></span> | <span data-ttu-id="a641f-126">연결되고 있는 원격 장치의 TCP 포트</span><span class="sxs-lookup"><span data-stu-id="a641f-126">TCP port on the remote device that was being connected to</span></span> |
| `RemoteUrl` | <span data-ttu-id="a641f-127">문자열</span><span class="sxs-lookup"><span data-stu-id="a641f-127">string</span></span> | <span data-ttu-id="a641f-128">연결된 URL 또는 FQDN(정규화된 도메인 이름)</span><span class="sxs-lookup"><span data-stu-id="a641f-128">URL or fully qualified domain name (FQDN) that was being connected to</span></span> |
| `LocalIP` | <span data-ttu-id="a641f-129">문자열</span><span class="sxs-lookup"><span data-stu-id="a641f-129">string</span></span> | <span data-ttu-id="a641f-130">통신 중에 사용되는 로컬 장치에 할당된 IP 주소</span><span class="sxs-lookup"><span data-stu-id="a641f-130">IP address assigned to the local device used during communication</span></span> |
| `LocalPort` | <span data-ttu-id="a641f-131">int</span><span class="sxs-lookup"><span data-stu-id="a641f-131">int</span></span> | <span data-ttu-id="a641f-132">통신 중에 사용되는 로컬 장치의 TCP 포트</span><span class="sxs-lookup"><span data-stu-id="a641f-132">TCP port on the local device used during communication</span></span> |
| `Protocol` | <span data-ttu-id="a641f-133">문자열</span><span class="sxs-lookup"><span data-stu-id="a641f-133">string</span></span> | <span data-ttu-id="a641f-134">사용된 IP 프로토콜(TCP 또는 UDP와는 다를 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a641f-134">IP protocol used, whether TCP or UDP</span></span> |
| `LocalIPType` | <span data-ttu-id="a641f-135">문자열</span><span class="sxs-lookup"><span data-stu-id="a641f-135">string</span></span> | <span data-ttu-id="a641f-136">Ip 주소 유형(예: Public, Private, Reserved, Loopback, Teredo, FourToSixMapping 및 Broadcast)</span><span class="sxs-lookup"><span data-stu-id="a641f-136">Type of IP address, for example Public, Private, Reserved, Loopback, Teredo, FourToSixMapping, and Broadcast</span></span> |
| `RemoteIPType` | <span data-ttu-id="a641f-137">문자열</span><span class="sxs-lookup"><span data-stu-id="a641f-137">string</span></span> | <span data-ttu-id="a641f-138">Ip 주소 유형(예: Public, Private, Reserved, Loopback, Teredo, FourToSixMapping 및 Broadcast)</span><span class="sxs-lookup"><span data-stu-id="a641f-138">Type of IP address, for example Public, Private, Reserved, Loopback, Teredo, FourToSixMapping, and Broadcast</span></span> |
| `InitiatingProcessSHA1` | <span data-ttu-id="a641f-139">문자열</span><span class="sxs-lookup"><span data-stu-id="a641f-139">string</span></span> | <span data-ttu-id="a641f-140">이벤트를 시작한 프로세스(이미지 파일)의 SHA-1</span><span class="sxs-lookup"><span data-stu-id="a641f-140">SHA-1 of the process (image file) that initiated the event</span></span> |
| `InitiatingProcessMD5` | <span data-ttu-id="a641f-141">문자열</span><span class="sxs-lookup"><span data-stu-id="a641f-141">string</span></span> | <span data-ttu-id="a641f-142">이벤트를 시작한 프로세스(이미지 파일)의 MD5 해시입니다.</span><span class="sxs-lookup"><span data-stu-id="a641f-142">MD5 hash of the process (image file) that initiated the event</span></span> |
| `InitiatingProcessFileName` | <span data-ttu-id="a641f-143">문자열</span><span class="sxs-lookup"><span data-stu-id="a641f-143">string</span></span> | <span data-ttu-id="a641f-144">이벤트를 시작한 프로세스의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="a641f-144">Name of the process that initiated the event</span></span> |
| `InitiatingProcessId` | <span data-ttu-id="a641f-145">int</span><span class="sxs-lookup"><span data-stu-id="a641f-145">int</span></span> | <span data-ttu-id="a641f-146">이벤트를 시작한 프로세스의 PID(프로세스 ID)입니다.</span><span class="sxs-lookup"><span data-stu-id="a641f-146">Process ID (PID) of the process that initiated the event</span></span> |
| `InitiatingProcessCommandLine` | <span data-ttu-id="a641f-147">문자열</span><span class="sxs-lookup"><span data-stu-id="a641f-147">string</span></span> | <span data-ttu-id="a641f-148">이벤트를 시작한 프로세스를 실행하는 데 사용되는 명령줄</span><span class="sxs-lookup"><span data-stu-id="a641f-148">Command line used to run the process that initiated the event</span></span> |
| `InitiatingProcessCreationTime` | <span data-ttu-id="a641f-149">datetime</span><span class="sxs-lookup"><span data-stu-id="a641f-149">datetime</span></span> | <span data-ttu-id="a641f-150">이벤트를 시작한 프로세스가 시작된 날짜 및 시간</span><span class="sxs-lookup"><span data-stu-id="a641f-150">Date and time when the process that initiated the event was started</span></span> |
| `InitiatingProcessFolderPath` | <span data-ttu-id="a641f-151">문자열</span><span class="sxs-lookup"><span data-stu-id="a641f-151">string</span></span> | <span data-ttu-id="a641f-152">이벤트를 시작한 프로세스(이미지 파일)가 포함된 폴더</span><span class="sxs-lookup"><span data-stu-id="a641f-152">Folder containing the process (image file) that initiated the event</span></span> |
| `InitiatingProcessParentFileName` | <span data-ttu-id="a641f-153">문자열</span><span class="sxs-lookup"><span data-stu-id="a641f-153">string</span></span> | <span data-ttu-id="a641f-154">이벤트를 담당하는 프로세스를 시작한 상위 프로세스의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="a641f-154">Name of the parent process that spawned the process responsible for the event</span></span> |
| `InitiatingProcessParentId` | <span data-ttu-id="a641f-155">int</span><span class="sxs-lookup"><span data-stu-id="a641f-155">int</span></span> | <span data-ttu-id="a641f-156">이벤트를 담당하는 프로세스를 시작한 상위 프로세스의 PID(프로세스 ID)입니다.</span><span class="sxs-lookup"><span data-stu-id="a641f-156">Process ID (PID) of the parent process that spawned the process responsible for the event</span></span> |
| `InitiatingProcessParentCreationTime` | <span data-ttu-id="a641f-157">datetime</span><span class="sxs-lookup"><span data-stu-id="a641f-157">datetime</span></span> | <span data-ttu-id="a641f-158">이벤트를 담당하는 프로세스의 부모가 시작된 날짜 및 시간입니다.</span><span class="sxs-lookup"><span data-stu-id="a641f-158">Date and time when the parent of the process responsible for the event was started</span></span> |
| `InitiatingProcessAccountDomain` | <span data-ttu-id="a641f-159">문자열</span><span class="sxs-lookup"><span data-stu-id="a641f-159">string</span></span> | <span data-ttu-id="a641f-160">이벤트를 담당하는 프로세스를 시작한 계정의 도메인입니다.</span><span class="sxs-lookup"><span data-stu-id="a641f-160">Domain of the account that ran the process responsible for the event</span></span> |
| `InitiatingProcessAccountName` | <span data-ttu-id="a641f-161">문자열</span><span class="sxs-lookup"><span data-stu-id="a641f-161">string</span></span> | <span data-ttu-id="a641f-162">이벤트를 담당하는 프로세스를 시작한 계정의 사용자 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="a641f-162">User name of the account that ran the process responsible for the event</span></span> |
| `InitiatingProcessAccountSid` | <span data-ttu-id="a641f-163">문자열</span><span class="sxs-lookup"><span data-stu-id="a641f-163">string</span></span> | <span data-ttu-id="a641f-164">이벤트를 담당하는 프로세스를 시작한 계정의 SID(보안 식별자)입니다.</span><span class="sxs-lookup"><span data-stu-id="a641f-164">Security Identifier (SID) of the account that ran the process responsible for the event</span></span> |
| `InitiatingProcessIntegrityLevel` | <span data-ttu-id="a641f-165">문자열</span><span class="sxs-lookup"><span data-stu-id="a641f-165">string</span></span> | <span data-ttu-id="a641f-166">이벤트를 시작한 프로세스의 무결성 수준입니다.</span><span class="sxs-lookup"><span data-stu-id="a641f-166">Integrity level of the process that initiated the event.</span></span> <span data-ttu-id="a641f-167">Windows는 인터넷 다운로드에서 시작된 경우와 같이 특정 특성을 기반으로 프로세스에 무결성 수준을 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="a641f-167">Windows assigns integrity levels to processes based on certain characteristics, such as if they were launched from an internet download.</span></span> <span data-ttu-id="a641f-168">이러한 무결성 수준은 리소스에 대한 사용 권한에 영향을 미치기</span><span class="sxs-lookup"><span data-stu-id="a641f-168">These integrity levels influence permissions to resources</span></span> |
| `InitiatingProcessTokenElevation` | <span data-ttu-id="a641f-169">문자열</span><span class="sxs-lookup"><span data-stu-id="a641f-169">string</span></span> | <span data-ttu-id="a641f-170">이벤트를 시작한 프로세스에 적용되는 UAC(사용자 액세스 제어) 권한 상승의 유무를 나타내는 토큰 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="a641f-170">Token type indicating the presence or absence of User Access Control (UAC) privilege elevation applied to the process that initiated the event</span></span> |
| `ReportId` | <span data-ttu-id="a641f-171">long</span><span class="sxs-lookup"><span data-stu-id="a641f-171">long</span></span> | <span data-ttu-id="a641f-172">반복 카운터를 기반으로 하는 이벤트 식별자입니다.</span><span class="sxs-lookup"><span data-stu-id="a641f-172">Event identifier based on a repeating counter.</span></span> <span data-ttu-id="a641f-173">고유한 이벤트를 식별하려면 이 열을 및 열과 `DeviceName` 함께 `Timestamp` 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a641f-173">To identify unique events, this column must be used in conjunction with the `DeviceName` and `Timestamp` columns</span></span> |
| `AppGuardContainerId` | <span data-ttu-id="a641f-174">문자열</span><span class="sxs-lookup"><span data-stu-id="a641f-174">string</span></span> | <span data-ttu-id="a641f-175">Application Guard에서 브라우저 활동을 격리하기 위해 사용하는 가상화된 컨테이너의 식별자</span><span class="sxs-lookup"><span data-stu-id="a641f-175">Identifier for the virtualized container used by Application Guard to isolate browser activity</span></span> |

## <a name="related-topics"></a><span data-ttu-id="a641f-176">관련 항목</span><span class="sxs-lookup"><span data-stu-id="a641f-176">Related topics</span></span>
- [<span data-ttu-id="a641f-177">지능형 헌팅 개요</span><span class="sxs-lookup"><span data-stu-id="a641f-177">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="a641f-178">쿼리 언어 배우기</span><span class="sxs-lookup"><span data-stu-id="a641f-178">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="a641f-179">스키마의 이해</span><span class="sxs-lookup"><span data-stu-id="a641f-179">Understand the schema</span></span>](advanced-hunting-schema-reference.md)
