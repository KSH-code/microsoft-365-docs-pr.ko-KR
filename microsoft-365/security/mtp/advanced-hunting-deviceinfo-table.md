---
title: 고급 헌팅chema의 DeviceInfo 표
description: 고급 헌팅 스위마의 DeviceInfo 표에서 OS, 컴퓨터 이름 및 기타 컴퓨터 정보에 대해 자세히 알아보기
keywords: 고급 헌팅, 위협 헌팅, 사이버 위협 헌팅, Microsoft 위협 방지, microsoft 365, mtp, m365, 검색, 쿼리, 원격 분석, schema reference, kusto, table, column, data type, description, machineinfo, DeviceInfo, device, machine, OS, platform, users
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
ms.openlocfilehash: e445902ee83b734f84d02607905413a14c016b8f
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/22/2021
ms.locfileid: "49931281"
---
# <a name="deviceinfo"></a><span data-ttu-id="c2a99-104">DeviceInfo</span><span class="sxs-lookup"><span data-stu-id="c2a99-104">DeviceInfo</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="c2a99-105">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="c2a99-105">**Applies to:**</span></span>
- <span data-ttu-id="c2a99-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="c2a99-106">Microsoft 365 Defender</span></span>



<span data-ttu-id="c2a99-107">고급 헌팅 시스템 표에는 OS 버전, 활성 사용자 및 컴퓨터 이름을 비롯한 조직의 컴퓨터에 대한 `DeviceInfo` 정보가 포함되어 있습니다. [](advanced-hunting-overview.md)</span><span class="sxs-lookup"><span data-stu-id="c2a99-107">The `DeviceInfo` table in the [advanced hunting](advanced-hunting-overview.md) schema contains information about machines in the organization, including OS version, active users, and computer name.</span></span> <span data-ttu-id="c2a99-108">이 참조를 사용하여 이 표의 정보를 반환하는 쿼리를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="c2a99-108">Use this reference to construct queries that return information from this table.</span></span>

<span data-ttu-id="c2a99-109">고급 헌팅 스키마의 다른 표에 대한 자세한 내용은 [고급 헌팅 참조](advanced-hunting-schema-tables.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="c2a99-109">For information on other tables in the advanced hunting schema, [see the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="c2a99-110">열 이름</span><span class="sxs-lookup"><span data-stu-id="c2a99-110">Column name</span></span> | <span data-ttu-id="c2a99-111">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="c2a99-111">Data type</span></span> | <span data-ttu-id="c2a99-112">설명</span><span class="sxs-lookup"><span data-stu-id="c2a99-112">Description</span></span> |
|-------------|-----------|-------------|
| `Timestamp` | <span data-ttu-id="c2a99-113">datetime</span><span class="sxs-lookup"><span data-stu-id="c2a99-113">datetime</span></span> | <span data-ttu-id="c2a99-114">이벤트가 기록된 날짜와 시간</span><span class="sxs-lookup"><span data-stu-id="c2a99-114">Date and time when the event was recorded</span></span> |
| `DeviceId` | <span data-ttu-id="c2a99-115">문자열</span><span class="sxs-lookup"><span data-stu-id="c2a99-115">string</span></span> | <span data-ttu-id="c2a99-116">서비스에서 시스템의 고유 식별자</span><span class="sxs-lookup"><span data-stu-id="c2a99-116">Unique identifier for the machine in the service</span></span> |
| `DeviceName` | <span data-ttu-id="c2a99-117">문자열</span><span class="sxs-lookup"><span data-stu-id="c2a99-117">string</span></span> | <span data-ttu-id="c2a99-118">컴퓨터의 FQDN(정규화된 도메인 이름)</span><span class="sxs-lookup"><span data-stu-id="c2a99-118">Fully qualified domain name (FQDN) of the machine</span></span> |
| `ClientVersion` | <span data-ttu-id="c2a99-119">문자열</span><span class="sxs-lookup"><span data-stu-id="c2a99-119">string</span></span> | <span data-ttu-id="c2a99-120">컴퓨터의 실행 끝점 에이전트 또는 센서 버전</span><span class="sxs-lookup"><span data-stu-id="c2a99-120">Version of the endpoint agent or sensor running on the machine</span></span> |
| `PublicIP` | <span data-ttu-id="c2a99-121">문자열</span><span class="sxs-lookup"><span data-stu-id="c2a99-121">string</span></span> | <span data-ttu-id="c2a99-122">등록된 컴퓨터의 끝점용 Microsoft Defender 서비스에 연결하는 데 사용하는 공용 IP 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="c2a99-122">Public IP address used by the onboarded machine to connect to the Microsoft  Defender for Endpoint service.</span></span> <span data-ttu-id="c2a99-123">컴퓨터 자체의 IP 주소, NAT 장치 또는 프록시일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c2a99-123">This could be the IP address of the machine itself, a NAT device, or a proxy</span></span> |
| `OSArchitecture` | <span data-ttu-id="c2a99-124">문자열</span><span class="sxs-lookup"><span data-stu-id="c2a99-124">string</span></span> | <span data-ttu-id="c2a99-125">컴퓨터에서 실행 중인 운영 체제의 아키텍처</span><span class="sxs-lookup"><span data-stu-id="c2a99-125">Architecture of the operating system running on the machine</span></span> |
| `OSPlatform` | <span data-ttu-id="c2a99-126">문자열</span><span class="sxs-lookup"><span data-stu-id="c2a99-126">string</span></span> | <span data-ttu-id="c2a99-127">컴퓨터에서 실행 중인 운영 체제의 플랫폼</span><span class="sxs-lookup"><span data-stu-id="c2a99-127">Platform of the operating system running on the machine.</span></span> <span data-ttu-id="c2a99-128">이는 Windows 10 및 Windows 7과 같은 동일한 패밀리 내의 변형을 포함하여 특정 운영 체제를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="c2a99-128">This indicates specific operating systems, including variations within the same family, such as Windows 10 and Windows 7</span></span> |
| `OSBuild` | <span data-ttu-id="c2a99-129">문자열</span><span class="sxs-lookup"><span data-stu-id="c2a99-129">string</span></span> | <span data-ttu-id="c2a99-130">시스템에서 실행되는 운영 체제의 빌드 버전</span><span class="sxs-lookup"><span data-stu-id="c2a99-130">Build version of the operating system running on the machine</span></span> |
| `IsAzureADJoined` | <span data-ttu-id="c2a99-131">부울</span><span class="sxs-lookup"><span data-stu-id="c2a99-131">boolean</span></span> | <span data-ttu-id="c2a99-132">컴퓨터의 Azure Active Directory 가입 여부를 나타내는 부울 표시기입니다.</span><span class="sxs-lookup"><span data-stu-id="c2a99-132">Boolean indicator of whether machine is joined to the Azure Active Directory</span></span> |
| `LoggedOnUsers` | <span data-ttu-id="c2a99-133">문자열</span><span class="sxs-lookup"><span data-stu-id="c2a99-133">string</span></span> | <span data-ttu-id="c2a99-134">이벤트 당시 컴퓨터에 기록된 모든 사용자 목록(JSON 배열 형식)</span><span class="sxs-lookup"><span data-stu-id="c2a99-134">List of all users that are logged on the machine at the time of the event in JSON array format</span></span> |
| `RegistryDeviceTag` | <span data-ttu-id="c2a99-135">문자열</span><span class="sxs-lookup"><span data-stu-id="c2a99-135">string</span></span> | <span data-ttu-id="c2a99-136">레지스트리를 통해 추가된 컴퓨터 태그</span><span class="sxs-lookup"><span data-stu-id="c2a99-136">Machine tag added through the registry</span></span> |
| `ReportId` | <span data-ttu-id="c2a99-137">long</span><span class="sxs-lookup"><span data-stu-id="c2a99-137">long</span></span> | <span data-ttu-id="c2a99-138">반복 카운터를 기반으로 하는 이벤트 식별자입니다.</span><span class="sxs-lookup"><span data-stu-id="c2a99-138">Event identifier based on a repeating counter.</span></span> <span data-ttu-id="c2a99-139">고유한 이벤트를 식별하려면 이 열을 DeviceName 및 타임스탬프 열과 함께 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c2a99-139">To identify unique events, this column must be used in conjunction with the DeviceName and Timestamp columns</span></span> |
| `OSVersion` | <span data-ttu-id="c2a99-140">문자열</span><span class="sxs-lookup"><span data-stu-id="c2a99-140">string</span></span> | <span data-ttu-id="c2a99-141">컴퓨터에서 실행 중인 운영 체제 버전</span><span class="sxs-lookup"><span data-stu-id="c2a99-141">Version of the operating system running on the machine</span></span> |
| `MachineGroup` | <span data-ttu-id="c2a99-142">문자열</span><span class="sxs-lookup"><span data-stu-id="c2a99-142">string</span></span> | <span data-ttu-id="c2a99-143">컴퓨터의 컴퓨터 그룹입니다.</span><span class="sxs-lookup"><span data-stu-id="c2a99-143">Machine group of the machine.</span></span> <span data-ttu-id="c2a99-144">이 그룹은 역할 기반 액세스 제어에서 컴퓨터 액세스 확인에 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="c2a99-144">This group is used by role-based access control to determine access to the machine</span></span> |

## <a name="related-topics"></a><span data-ttu-id="c2a99-145">관련 항목</span><span class="sxs-lookup"><span data-stu-id="c2a99-145">Related topics</span></span>
- [<span data-ttu-id="c2a99-146">고급 헌팅 개요</span><span class="sxs-lookup"><span data-stu-id="c2a99-146">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="c2a99-147">쿼리 언어 배우기</span><span class="sxs-lookup"><span data-stu-id="c2a99-147">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="c2a99-148">공유 쿼리 사용</span><span class="sxs-lookup"><span data-stu-id="c2a99-148">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="c2a99-149">장치, 전자 메일, 앱 및 ID를 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="c2a99-149">Hunt across devices, emails, apps, and identities</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="c2a99-150">스키마의 이해</span><span class="sxs-lookup"><span data-stu-id="c2a99-150">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="c2a99-151">쿼리 모범 사례 적용</span><span class="sxs-lookup"><span data-stu-id="c2a99-151">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
