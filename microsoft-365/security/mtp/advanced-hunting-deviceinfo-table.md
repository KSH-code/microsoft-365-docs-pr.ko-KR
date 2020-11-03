---
title: 고급 구하기 스키마의 DeviceInfo 테이블
description: 고급 구하기 스키마의 DeviceInfo 테이블에 있는 OS, 컴퓨터 이름 및 기타 컴퓨터 정보에 대해 자세히 알아봅니다.
keywords: 고급 구하기, 위협 검색, 사이버 위협 사냥, microsoft threat protection, microsoft 365, mtp, m365, 검색, 쿼리, 원격 분석, 스키마 참조, kusto, table, description, DeviceInfo, device, machine, OS, 플랫폼, 사용자
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
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.openlocfilehash: 1bb48b4332bc9d60de15bb513f04a503d6a6913b
ms.sourcegitcommit: 815229e39a0f905d9f06717f00dc82e2a028fa7c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/03/2020
ms.locfileid: "48842717"
---
# <a name="deviceinfo"></a><span data-ttu-id="8bd45-104">DeviceInfo</span><span class="sxs-lookup"><span data-stu-id="8bd45-104">DeviceInfo</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="8bd45-105">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="8bd45-105">**Applies to:**</span></span>
- <span data-ttu-id="8bd45-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="8bd45-106">Microsoft 365 Defender</span></span>



<span data-ttu-id="8bd45-107">`DeviceInfo` [고급 구하기](advanced-hunting-overview.md) 스키마의 표에는 OS 버전, 활성 사용자 및 컴퓨터 이름을 비롯 하 여 조직의 컴퓨터에 대 한 정보가 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8bd45-107">The `DeviceInfo` table in the [advanced hunting](advanced-hunting-overview.md) schema contains information about machines in the organization, including OS version, active users, and computer name.</span></span> <span data-ttu-id="8bd45-108">이 참조를 사용하여 이 표의 정보를 반환하는 쿼리를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="8bd45-108">Use this reference to construct queries that return information from this table.</span></span>

<span data-ttu-id="8bd45-109">고급 헌팅 스키마의 다른 표에 대한 자세한 내용은 [고급 헌팅 참조](advanced-hunting-schema-tables.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="8bd45-109">For information on other tables in the advanced hunting schema, [see the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="8bd45-110">열 이름</span><span class="sxs-lookup"><span data-stu-id="8bd45-110">Column name</span></span> | <span data-ttu-id="8bd45-111">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="8bd45-111">Data type</span></span> | <span data-ttu-id="8bd45-112">설명</span><span class="sxs-lookup"><span data-stu-id="8bd45-112">Description</span></span> |
|-------------|-----------|-------------|
| `Timestamp` | <span data-ttu-id="8bd45-113">datetime</span><span class="sxs-lookup"><span data-stu-id="8bd45-113">datetime</span></span> | <span data-ttu-id="8bd45-114">이벤트가 기록된 날짜와 시간</span><span class="sxs-lookup"><span data-stu-id="8bd45-114">Date and time when the event was recorded</span></span> |
| `DeviceId` | <span data-ttu-id="8bd45-115">문자열</span><span class="sxs-lookup"><span data-stu-id="8bd45-115">string</span></span> | <span data-ttu-id="8bd45-116">서비스에서 시스템의 고유 식별자</span><span class="sxs-lookup"><span data-stu-id="8bd45-116">Unique identifier for the machine in the service</span></span> |
| `DeviceName` | <span data-ttu-id="8bd45-117">문자열</span><span class="sxs-lookup"><span data-stu-id="8bd45-117">string</span></span> | <span data-ttu-id="8bd45-118">컴퓨터의 FQDN(정규화된 도메인 이름)</span><span class="sxs-lookup"><span data-stu-id="8bd45-118">Fully qualified domain name (FQDN) of the machine</span></span> |
| `ClientVersion` | <span data-ttu-id="8bd45-119">문자열</span><span class="sxs-lookup"><span data-stu-id="8bd45-119">string</span></span> | <span data-ttu-id="8bd45-120">컴퓨터에서 실행 되는 끝점 에이전트 또는 센서의 버전</span><span class="sxs-lookup"><span data-stu-id="8bd45-120">Version of the endpoint agent or sensor running on the machine</span></span> |
| `PublicIP` | <span data-ttu-id="8bd45-121">문자열</span><span class="sxs-lookup"><span data-stu-id="8bd45-121">string</span></span> | <span data-ttu-id="8bd45-122">등록 컴퓨터에서 Microsoft Defender for Endpoint 서비스에 연결 하는 데 사용 하는 공용 IP 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="8bd45-122">Public IP address used by the onboarded machine to connect to the Microsoft  Defender for Endpoint service.</span></span> <span data-ttu-id="8bd45-123">컴퓨터 자체의 IP 주소, NAT 장치 또는 프록시 일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8bd45-123">This could be the IP address of the machine itself, a NAT device, or a proxy</span></span> |
| `OSArchitecture` | <span data-ttu-id="8bd45-124">문자열</span><span class="sxs-lookup"><span data-stu-id="8bd45-124">string</span></span> | <span data-ttu-id="8bd45-125">컴퓨터에서 실행 중인 운영 체제의 아키텍처</span><span class="sxs-lookup"><span data-stu-id="8bd45-125">Architecture of the operating system running on the machine</span></span> |
| `OSPlatform` | <span data-ttu-id="8bd45-126">문자열</span><span class="sxs-lookup"><span data-stu-id="8bd45-126">string</span></span> | <span data-ttu-id="8bd45-127">컴퓨터에서 실행 중인 운영 체제의 플랫폼</span><span class="sxs-lookup"><span data-stu-id="8bd45-127">Platform of the operating system running on the machine.</span></span> <span data-ttu-id="8bd45-128">이는 Windows 10 및 Windows 7과 같은 제품군 내의 변형을 비롯 하 여 특정 운영 체제를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="8bd45-128">This indicates specific operating systems, including variations within the same family, such as Windows 10 and Windows 7</span></span> |
| `OSBuild` | <span data-ttu-id="8bd45-129">문자열</span><span class="sxs-lookup"><span data-stu-id="8bd45-129">string</span></span> | <span data-ttu-id="8bd45-130">컴퓨터에서 실행 되는 운영 체제의 빌드 버전</span><span class="sxs-lookup"><span data-stu-id="8bd45-130">Build version of the operating system running on the machine</span></span> |
| `IsAzureADJoined` | <span data-ttu-id="8bd45-131">부울</span><span class="sxs-lookup"><span data-stu-id="8bd45-131">boolean</span></span> | <span data-ttu-id="8bd45-132">컴퓨터가 Azure Active Directory에 가입 되어 있는지 여부를 나타내는 부울 표시기입니다.</span><span class="sxs-lookup"><span data-stu-id="8bd45-132">Boolean indicator of whether machine is joined to the Azure Active Directory</span></span> |
| `LoggedOnUsers` | <span data-ttu-id="8bd45-133">문자열</span><span class="sxs-lookup"><span data-stu-id="8bd45-133">string</span></span> | <span data-ttu-id="8bd45-134">JSON 배열 형식의 이벤트가 발생 했을 때 컴퓨터에 로그온 한 모든 사용자의 목록</span><span class="sxs-lookup"><span data-stu-id="8bd45-134">List of all users that are logged on the machine at the time of the event in JSON array format</span></span> |
| `RegistryDeviceTag` | <span data-ttu-id="8bd45-135">문자열</span><span class="sxs-lookup"><span data-stu-id="8bd45-135">string</span></span> | <span data-ttu-id="8bd45-136">레지스트리를 통해 추가 된 기계 태그</span><span class="sxs-lookup"><span data-stu-id="8bd45-136">Machine tag added through the registry</span></span> |
| `ReportId` | <span data-ttu-id="8bd45-137">long</span><span class="sxs-lookup"><span data-stu-id="8bd45-137">long</span></span> | <span data-ttu-id="8bd45-138">반복 카운터를 기반으로 하는 이벤트 식별자입니다.</span><span class="sxs-lookup"><span data-stu-id="8bd45-138">Event identifier based on a repeating counter.</span></span> <span data-ttu-id="8bd45-139">고유 이벤트를 식별 하려면이 열을 장치 이름 및 타임 스탬프 열과 함께 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8bd45-139">To identify unique events, this column must be used in conjunction with the DeviceName and Timestamp columns</span></span> |
| `OSVersion` | <span data-ttu-id="8bd45-140">문자열</span><span class="sxs-lookup"><span data-stu-id="8bd45-140">string</span></span> | <span data-ttu-id="8bd45-141">컴퓨터에서 실행 중인 운영 체제 버전</span><span class="sxs-lookup"><span data-stu-id="8bd45-141">Version of the operating system running on the machine</span></span> |
| `MachineGroup` | <span data-ttu-id="8bd45-142">문자열</span><span class="sxs-lookup"><span data-stu-id="8bd45-142">string</span></span> | <span data-ttu-id="8bd45-143">컴퓨터의 컴퓨터 그룹입니다.</span><span class="sxs-lookup"><span data-stu-id="8bd45-143">Machine group of the machine.</span></span> <span data-ttu-id="8bd45-144">역할 기반 액세스 제어에서이 그룹을 사용 하 여 컴퓨터에 대 한 액세스를 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="8bd45-144">This group is used by role-based access control to determine access to the machine</span></span> |

## <a name="related-topics"></a><span data-ttu-id="8bd45-145">관련 항목</span><span class="sxs-lookup"><span data-stu-id="8bd45-145">Related topics</span></span>
- [<span data-ttu-id="8bd45-146">고급 헌팅 개요</span><span class="sxs-lookup"><span data-stu-id="8bd45-146">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="8bd45-147">쿼리 언어 배우기</span><span class="sxs-lookup"><span data-stu-id="8bd45-147">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="8bd45-148">공유 쿼리 사용</span><span class="sxs-lookup"><span data-stu-id="8bd45-148">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="8bd45-149">기기, 전자 메일, 앱 및 ID를 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="8bd45-149">Hunt across devices, emails, apps, and identities</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="8bd45-150">스키마의 이해</span><span class="sxs-lookup"><span data-stu-id="8bd45-150">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="8bd45-151">쿼리 모범 사례 적용</span><span class="sxs-lookup"><span data-stu-id="8bd45-151">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
