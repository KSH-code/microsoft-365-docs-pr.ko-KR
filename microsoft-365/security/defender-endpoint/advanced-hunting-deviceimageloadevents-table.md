---
title: 고급 헌팅chema의 DeviceImageLoadEvents 테이블
description: 고급 헌팅 스위마의 DeviceImageLoadEvents 테이블에서 DLL 로딩 이벤트에 대해 자세히 알아보시고
keywords: 고급 헌팅, 위협 헌팅, 사이버 위협 헌팅, 검색, 쿼리, 원격 분석, schema 참조, kusto, 표, 열, 데이터 형식, 설명, deviceimageloadevents, DLL 로드, 라이브러리, 파일 이미지, ImageLoadEvents
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: lomayor
author: lomayor
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: aad270a101e7052e04e4530e661e0e86c2db70d2
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51075108"
---
# <a name="deviceimageloadevents"></a><span data-ttu-id="3d247-104">DeviceImageLoadEvents</span><span class="sxs-lookup"><span data-stu-id="3d247-104">DeviceImageLoadEvents</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="3d247-105">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="3d247-105">**Applies to:**</span></span>
- [<span data-ttu-id="3d247-106">엔드포인트용 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="3d247-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)


><span data-ttu-id="3d247-107">Endpoint용 Defender를 경험하고 싶나요?</span><span class="sxs-lookup"><span data-stu-id="3d247-107">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="3d247-108">무료 평가판에 등록합니다.</span><span class="sxs-lookup"><span data-stu-id="3d247-108">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-advancedhuntingref-abovefoldlink)

<span data-ttu-id="3d247-109">고급 `DeviceImageLoadEvents` 헌팅 [일정의](advanced-hunting-overview.md) 표에는 DLL 로드 이벤트에 대한 정보가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3d247-109">The `DeviceImageLoadEvents` table in the [advanced hunting](advanced-hunting-overview.md) schema contains information about DLL loading events.</span></span> <span data-ttu-id="3d247-110">이 참조를 사용하여 표의 정보를 반환하는 쿼리를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="3d247-110">Use this reference to construct queries that return information from the table.</span></span>

<span data-ttu-id="3d247-111">고급 헌팅 스마의 다른 표에 대한 자세한 내용은 고급 헌팅 스마 [참조 를 참조하세요.](advanced-hunting-schema-reference.md)</span><span class="sxs-lookup"><span data-stu-id="3d247-111">For information on other tables in the advanced hunting schema, see [the advanced hunting schema reference](advanced-hunting-schema-reference.md).</span></span>

| <span data-ttu-id="3d247-112">열 이름</span><span class="sxs-lookup"><span data-stu-id="3d247-112">Column name</span></span> | <span data-ttu-id="3d247-113">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="3d247-113">Data type</span></span> | <span data-ttu-id="3d247-114">설명</span><span class="sxs-lookup"><span data-stu-id="3d247-114">Description</span></span> |
|-------------|-----------|-------------|
| `Timestamp` | <span data-ttu-id="3d247-115">datetime</span><span class="sxs-lookup"><span data-stu-id="3d247-115">datetime</span></span> | <span data-ttu-id="3d247-116">이벤트가 기록된 날짜와 시간</span><span class="sxs-lookup"><span data-stu-id="3d247-116">Date and time when the event was recorded</span></span> |
| `DeviceId` | <span data-ttu-id="3d247-117">문자열</span><span class="sxs-lookup"><span data-stu-id="3d247-117">string</span></span> | <span data-ttu-id="3d247-118">서비스에서 디바이스의 고유 식별자</span><span class="sxs-lookup"><span data-stu-id="3d247-118">Unique identifier for the device in the service</span></span> |
| `DeviceName` | <span data-ttu-id="3d247-119">문자열</span><span class="sxs-lookup"><span data-stu-id="3d247-119">string</span></span> | <span data-ttu-id="3d247-120">장치의 FQDN(FQDN)</span><span class="sxs-lookup"><span data-stu-id="3d247-120">Fully qualified domain name (FQDN) of the device</span></span> |
| `ActionType` | <span data-ttu-id="3d247-121">문자열</span><span class="sxs-lookup"><span data-stu-id="3d247-121">string</span></span> | <span data-ttu-id="3d247-122">이벤트를 트리거한 활동 유형</span><span class="sxs-lookup"><span data-stu-id="3d247-122">Type of activity that triggered the event</span></span> |
| `FileName` | <span data-ttu-id="3d247-123">문자열</span><span class="sxs-lookup"><span data-stu-id="3d247-123">string</span></span> | <span data-ttu-id="3d247-124">기록된 조치가 적용된 파일의 이름</span><span class="sxs-lookup"><span data-stu-id="3d247-124">Name of the file that the recorded action was applied to</span></span> |
| `FolderPath` | <span data-ttu-id="3d247-125">문자열</span><span class="sxs-lookup"><span data-stu-id="3d247-125">string</span></span> | <span data-ttu-id="3d247-126">기록된 작업이 적용된 파일이 들어 있는 폴더</span><span class="sxs-lookup"><span data-stu-id="3d247-126">Folder containing the file that the recorded action was applied to</span></span> |
| `SHA1` | <span data-ttu-id="3d247-127">문자열</span><span class="sxs-lookup"><span data-stu-id="3d247-127">string</span></span> | <span data-ttu-id="3d247-128">기록된 조치가 적용된 파일의 SHA-1</span><span class="sxs-lookup"><span data-stu-id="3d247-128">SHA-1 of the file that the recorded action was applied to</span></span> |
| `MD5` | <span data-ttu-id="3d247-129">문자열</span><span class="sxs-lookup"><span data-stu-id="3d247-129">string</span></span> | <span data-ttu-id="3d247-130">기록된 작업이 적용된 파일의 MD5 해시입니다.</span><span class="sxs-lookup"><span data-stu-id="3d247-130">MD5 hash of the file that the recorded action was applied to</span></span> |
| `InitiatingProcessAccountDomain` | <span data-ttu-id="3d247-131">문자열</span><span class="sxs-lookup"><span data-stu-id="3d247-131">string</span></span> | <span data-ttu-id="3d247-132">이벤트를 담당하는 프로세스를 시작한 계정의 도메인입니다.</span><span class="sxs-lookup"><span data-stu-id="3d247-132">Domain of the account that ran the process responsible for the event</span></span> |
| `InitiatingProcessAccountName` | <span data-ttu-id="3d247-133">문자열</span><span class="sxs-lookup"><span data-stu-id="3d247-133">string</span></span> | <span data-ttu-id="3d247-134">이벤트를 담당하는 프로세스를 시작한 계정의 사용자 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="3d247-134">User name of the account that ran the process responsible for the event</span></span> |
| `InitiatingProcessAccountSid` | <span data-ttu-id="3d247-135">문자열</span><span class="sxs-lookup"><span data-stu-id="3d247-135">string</span></span> | <span data-ttu-id="3d247-136">이벤트를 담당하는 프로세스를 시작한 계정의 SID(보안 식별자)입니다.</span><span class="sxs-lookup"><span data-stu-id="3d247-136">Security Identifier (SID) of the account that ran the process responsible for the event</span></span> |
| `InitiatingProcessIntegrityLevel` | <span data-ttu-id="3d247-137">문자열</span><span class="sxs-lookup"><span data-stu-id="3d247-137">string</span></span> | <span data-ttu-id="3d247-138">이벤트를 시작한 프로세스의 무결성 수준입니다.</span><span class="sxs-lookup"><span data-stu-id="3d247-138">Integrity level of the process that initiated the event.</span></span> <span data-ttu-id="3d247-139">Windows는 인터넷 다운로드에서 시작된 경우와 같이 특정 특성을 기반으로 프로세스에 무결성 수준을 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="3d247-139">Windows assigns integrity levels to processes based on certain characteristics, such as if they were launched from an internet download.</span></span> <span data-ttu-id="3d247-140">이러한 무결성 수준은 리소스에 대한 사용 권한에 영향을 미치기</span><span class="sxs-lookup"><span data-stu-id="3d247-140">These integrity levels influence permissions to resources</span></span> |
| `InitiatingProcessTokenElevation` | <span data-ttu-id="3d247-141">문자열</span><span class="sxs-lookup"><span data-stu-id="3d247-141">string</span></span> | <span data-ttu-id="3d247-142">이벤트를 시작한 프로세스에 적용되는 UAC(사용자 액세스 제어) 권한 상승의 유무를 나타내는 토큰 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="3d247-142">Token type indicating the presence or absence of User Access Control (UAC) privilege elevation applied to the process that initiated the event</span></span> |
| `InitiatingProcessSHA1` | <span data-ttu-id="3d247-143">문자열</span><span class="sxs-lookup"><span data-stu-id="3d247-143">string</span></span> | <span data-ttu-id="3d247-144">이벤트를 시작한 프로세스(이미지 파일)의 SHA-1</span><span class="sxs-lookup"><span data-stu-id="3d247-144">SHA-1 of the process (image file) that initiated the event</span></span> |
| `InitiatingProcessMD5` | <span data-ttu-id="3d247-145">문자열</span><span class="sxs-lookup"><span data-stu-id="3d247-145">string</span></span> | <span data-ttu-id="3d247-146">이벤트를 시작한 프로세스(이미지 파일)의 MD5 해시입니다.</span><span class="sxs-lookup"><span data-stu-id="3d247-146">MD5 hash of the process (image file) that initiated the event</span></span> |
| `InitiatingProcessFileName` | <span data-ttu-id="3d247-147">문자열</span><span class="sxs-lookup"><span data-stu-id="3d247-147">string</span></span> | <span data-ttu-id="3d247-148">이벤트를 시작한 프로세스의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="3d247-148">Name of the process that initiated the event</span></span> |
| `InitiatingProcessId` | <span data-ttu-id="3d247-149">int</span><span class="sxs-lookup"><span data-stu-id="3d247-149">int</span></span> | <span data-ttu-id="3d247-150">이벤트를 시작한 프로세스의 PID(프로세스 ID)입니다.</span><span class="sxs-lookup"><span data-stu-id="3d247-150">Process ID (PID) of the process that initiated the event</span></span> |
| `InitiatingProcessCommandLine` | <span data-ttu-id="3d247-151">문자열</span><span class="sxs-lookup"><span data-stu-id="3d247-151">string</span></span> | <span data-ttu-id="3d247-152">이벤트를 시작한 프로세스를 실행하는 데 사용되는 명령줄</span><span class="sxs-lookup"><span data-stu-id="3d247-152">Command line used to run the process that initiated the event</span></span> |
| `InitiatingProcessCreationTime` | <span data-ttu-id="3d247-153">datetime</span><span class="sxs-lookup"><span data-stu-id="3d247-153">datetime</span></span> | <span data-ttu-id="3d247-154">이벤트를 시작한 프로세스가 시작된 날짜 및 시간</span><span class="sxs-lookup"><span data-stu-id="3d247-154">Date and time when the process that initiated the event was started</span></span> |
| `InitiatingProcessFolderPath` | <span data-ttu-id="3d247-155">문자열</span><span class="sxs-lookup"><span data-stu-id="3d247-155">string</span></span> | <span data-ttu-id="3d247-156">이벤트를 시작한 프로세스(이미지 파일)가 포함된 폴더</span><span class="sxs-lookup"><span data-stu-id="3d247-156">Folder containing the process (image file) that initiated the event</span></span> |
| `InitiatingProcessParentId` | <span data-ttu-id="3d247-157">int</span><span class="sxs-lookup"><span data-stu-id="3d247-157">int</span></span> | <span data-ttu-id="3d247-158">이벤트를 담당하는 프로세스를 시작한 상위 프로세스의 PID(프로세스 ID)입니다.</span><span class="sxs-lookup"><span data-stu-id="3d247-158">Process ID (PID) of the parent process that spawned the process responsible for the event</span></span> |
| `InitiatingProcessParentFileName` | <span data-ttu-id="3d247-159">문자열</span><span class="sxs-lookup"><span data-stu-id="3d247-159">string</span></span> | <span data-ttu-id="3d247-160">이벤트를 담당하는 프로세스를 시작한 상위 프로세스의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="3d247-160">Name of the parent process that spawned the process responsible for the event</span></span> |
| `InitiatingProcessParentCreationTime` | <span data-ttu-id="3d247-161">datetime</span><span class="sxs-lookup"><span data-stu-id="3d247-161">datetime</span></span> | <span data-ttu-id="3d247-162">이벤트를 담당하는 프로세스의 부모가 시작된 날짜 및 시간입니다.</span><span class="sxs-lookup"><span data-stu-id="3d247-162">Date and time when the parent of the process responsible for the event was started</span></span> |
| `ReportId` | <span data-ttu-id="3d247-163">long</span><span class="sxs-lookup"><span data-stu-id="3d247-163">long</span></span> | <span data-ttu-id="3d247-164">반복 카운터를 기반으로 하는 이벤트 식별자입니다.</span><span class="sxs-lookup"><span data-stu-id="3d247-164">Event identifier based on a repeating counter.</span></span> <span data-ttu-id="3d247-165">고유한 이벤트를 식별하려면 이 열을 및 열과 `DeviceName` 함께 `Timestamp` 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3d247-165">To identify unique events, this column must be used in conjunction with the `DeviceName` and `Timestamp` columns</span></span> |
| `AppGuardContainerId` | <span data-ttu-id="3d247-166">문자열</span><span class="sxs-lookup"><span data-stu-id="3d247-166">string</span></span> | <span data-ttu-id="3d247-167">Application Guard에서 브라우저 활동을 격리하기 위해 사용하는 가상화된 컨테이너의 식별자</span><span class="sxs-lookup"><span data-stu-id="3d247-167">Identifier for the virtualized container used by Application Guard to isolate browser activity</span></span> |

## <a name="related-topics"></a><span data-ttu-id="3d247-168">관련 항목</span><span class="sxs-lookup"><span data-stu-id="3d247-168">Related topics</span></span>
- [<span data-ttu-id="3d247-169">고급 헌팅 개요</span><span class="sxs-lookup"><span data-stu-id="3d247-169">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="3d247-170">쿼리 언어 배우기</span><span class="sxs-lookup"><span data-stu-id="3d247-170">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="3d247-171">스키마의 이해</span><span class="sxs-lookup"><span data-stu-id="3d247-171">Understand the schema</span></span>](advanced-hunting-schema-reference.md)
