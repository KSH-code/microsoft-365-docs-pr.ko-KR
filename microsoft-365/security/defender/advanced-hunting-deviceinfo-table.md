---
title: 고급 헌팅Chema의 DeviceInfo 테이블
description: 고급 헌팅 schema의 DeviceInfo 표에서 OS, 컴퓨터 이름 및 기타 컴퓨터 정보에 대해 자세히 알아보기
keywords: 고급 헌팅, 위협 헌팅, 사이버 위협 헌팅, Microsoft 위협 방지, microsoft 365, mtp, m365, 검색, 쿼리, 원격 분석, 스마마 참조, kusto, 표, 열, 데이터 형식, 설명, machineinfo, DeviceInfo, 장치, 컴퓨터, OS, 플랫폼, 사용자
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
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: 46efb531331cf76472c67c769c96804d11fb9e4b
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51071564"
---
# <a name="deviceinfo"></a><span data-ttu-id="41a64-104">DeviceInfo</span><span class="sxs-lookup"><span data-stu-id="41a64-104">DeviceInfo</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="41a64-105">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="41a64-105">**Applies to:**</span></span>
- <span data-ttu-id="41a64-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="41a64-106">Microsoft 365 Defender</span></span>



<span data-ttu-id="41a64-107">고급 `DeviceInfo` 헌팅 [schema의](advanced-hunting-overview.md) 표에는 OS 버전, 활성 사용자 및 컴퓨터 이름을 비롯한 조직의 장치에 대한 정보가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="41a64-107">The `DeviceInfo` table in the [advanced hunting](advanced-hunting-overview.md) schema contains information about devices in the organization, including OS version, active users, and computer name.</span></span> <span data-ttu-id="41a64-108">이 참조를 사용하여 이 표의 정보를 반환하는 쿼리를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="41a64-108">Use this reference to construct queries that return information from this table.</span></span>

<span data-ttu-id="41a64-109">고급 헌팅 스키마의 다른 표에 대한 자세한 내용은 [고급 헌팅 참조](advanced-hunting-schema-tables.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="41a64-109">For information on other tables in the advanced hunting schema, [see the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="41a64-110">열 이름</span><span class="sxs-lookup"><span data-stu-id="41a64-110">Column name</span></span> | <span data-ttu-id="41a64-111">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="41a64-111">Data type</span></span> | <span data-ttu-id="41a64-112">설명</span><span class="sxs-lookup"><span data-stu-id="41a64-112">Description</span></span> |
|-------------|-----------|-------------|
| `Timestamp` | <span data-ttu-id="41a64-113">datetime</span><span class="sxs-lookup"><span data-stu-id="41a64-113">datetime</span></span> | <span data-ttu-id="41a64-114">이벤트가 기록된 날짜와 시간</span><span class="sxs-lookup"><span data-stu-id="41a64-114">Date and time when the event was recorded</span></span> |
| `DeviceId` | <span data-ttu-id="41a64-115">문자열</span><span class="sxs-lookup"><span data-stu-id="41a64-115">string</span></span> | <span data-ttu-id="41a64-116">서비스에서 시스템의 고유 식별자</span><span class="sxs-lookup"><span data-stu-id="41a64-116">Unique identifier for the machine in the service</span></span> |
| `DeviceName` | <span data-ttu-id="41a64-117">문자열</span><span class="sxs-lookup"><span data-stu-id="41a64-117">string</span></span> | <span data-ttu-id="41a64-118">컴퓨터의 FQDN(정규화된 도메인 이름)</span><span class="sxs-lookup"><span data-stu-id="41a64-118">Fully qualified domain name (FQDN) of the machine</span></span> |
| `ClientVersion` | <span data-ttu-id="41a64-119">문자열</span><span class="sxs-lookup"><span data-stu-id="41a64-119">string</span></span> | <span data-ttu-id="41a64-120">기기에서 실행되는 끝점 에이전트 또는 센서의 버전</span><span class="sxs-lookup"><span data-stu-id="41a64-120">Version of the endpoint agent or sensor running on the machine</span></span> |
| `PublicIP` | <span data-ttu-id="41a64-121">문자열</span><span class="sxs-lookup"><span data-stu-id="41a64-121">string</span></span> | <span data-ttu-id="41a64-122">등록된 컴퓨터에 의해 끝점용 Microsoft Defender 서비스에 연결하는 데 사용되는 공용 IP 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="41a64-122">Public IP address used by the onboarded machine to connect to the Microsoft  Defender for Endpoint service.</span></span> <span data-ttu-id="41a64-123">컴퓨터 자체의 IP 주소, NAT 장치 또는 프록시일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="41a64-123">This could be the IP address of the machine itself, a NAT device, or a proxy</span></span> |
| `OSArchitecture` | <span data-ttu-id="41a64-124">문자열</span><span class="sxs-lookup"><span data-stu-id="41a64-124">string</span></span> | <span data-ttu-id="41a64-125">컴퓨터에서 실행 중인 운영 체제의 아키텍처</span><span class="sxs-lookup"><span data-stu-id="41a64-125">Architecture of the operating system running on the machine</span></span> |
| `OSPlatform` | <span data-ttu-id="41a64-126">문자열</span><span class="sxs-lookup"><span data-stu-id="41a64-126">string</span></span> | <span data-ttu-id="41a64-127">컴퓨터에서 실행 중인 운영 체제의 플랫폼</span><span class="sxs-lookup"><span data-stu-id="41a64-127">Platform of the operating system running on the machine.</span></span> <span data-ttu-id="41a64-128">이는 Windows 10 및 Windows 7과 같은 동일한 패밀리 내의 변형을 포함하여 특정 운영 체제를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="41a64-128">This indicates specific operating systems, including variations within the same family, such as Windows 10 and Windows 7</span></span> |
| `OSBuild` | <span data-ttu-id="41a64-129">문자열</span><span class="sxs-lookup"><span data-stu-id="41a64-129">string</span></span> | <span data-ttu-id="41a64-130">시스템에서 실행되는 운영 체제의 빌드 버전</span><span class="sxs-lookup"><span data-stu-id="41a64-130">Build version of the operating system running on the machine</span></span> |
| `IsAzureADJoined` | <span data-ttu-id="41a64-131">부울</span><span class="sxs-lookup"><span data-stu-id="41a64-131">boolean</span></span> | <span data-ttu-id="41a64-132">머신이 Azure Active Directory에 가입된지 여부를 나타내는 부울 표시기입니다.</span><span class="sxs-lookup"><span data-stu-id="41a64-132">Boolean indicator of whether machine is joined to the Azure Active Directory</span></span> |
| `AadObjectId` | <span data-ttu-id="41a64-133">문자열</span><span class="sxs-lookup"><span data-stu-id="41a64-133">string</span></span> | <span data-ttu-id="41a64-134">Azure AD에서 디바이스의 고유 식별자</span><span class="sxs-lookup"><span data-stu-id="41a64-134">Unique identifier for the device in Azure AD</span></span> |
| `LoggedOnUsers` | <span data-ttu-id="41a64-135">문자열</span><span class="sxs-lookup"><span data-stu-id="41a64-135">string</span></span> | <span data-ttu-id="41a64-136">이벤트 당시 컴퓨터에 로그온한 모든 사용자 목록(JSON 배열 형식)입니다.</span><span class="sxs-lookup"><span data-stu-id="41a64-136">List of all users that are logged on the machine at the time of the event in JSON array format</span></span> |
| `RegistryDeviceTag` | <span data-ttu-id="41a64-137">문자열</span><span class="sxs-lookup"><span data-stu-id="41a64-137">string</span></span> | <span data-ttu-id="41a64-138">레지스트리를 통해 추가된 컴퓨터 태그</span><span class="sxs-lookup"><span data-stu-id="41a64-138">Machine tag added through the registry</span></span> |
| `ReportId` | <span data-ttu-id="41a64-139">long</span><span class="sxs-lookup"><span data-stu-id="41a64-139">long</span></span> | <span data-ttu-id="41a64-140">반복 카운터를 기반으로 하는 이벤트 식별자입니다.</span><span class="sxs-lookup"><span data-stu-id="41a64-140">Event identifier based on a repeating counter.</span></span> <span data-ttu-id="41a64-141">고유한 이벤트를 식별하려면 이 열을 DeviceName 및 Timestamp 열과 함께 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="41a64-141">To identify unique events, this column must be used in conjunction with the DeviceName and Timestamp columns</span></span> |
|`AdditionalFields` | <span data-ttu-id="41a64-142">문자열</span><span class="sxs-lookup"><span data-stu-id="41a64-142">string</span></span> | <span data-ttu-id="41a64-143">JSON 배열 형식의 이벤트에 대한 추가 정보</span><span class="sxs-lookup"><span data-stu-id="41a64-143">Additional information about the event in JSON array format</span></span> |
| `OSVersion` | <span data-ttu-id="41a64-144">문자열</span><span class="sxs-lookup"><span data-stu-id="41a64-144">string</span></span> | <span data-ttu-id="41a64-145">컴퓨터에서 실행 중인 운영 체제 버전</span><span class="sxs-lookup"><span data-stu-id="41a64-145">Version of the operating system running on the machine</span></span> |
| `MachineGroup` | <span data-ttu-id="41a64-146">문자열</span><span class="sxs-lookup"><span data-stu-id="41a64-146">string</span></span> | <span data-ttu-id="41a64-147">컴퓨터의 컴퓨터 그룹입니다.</span><span class="sxs-lookup"><span data-stu-id="41a64-147">Machine group of the machine.</span></span> <span data-ttu-id="41a64-148">이 그룹은 역할 기반 액세스 제어에서 컴퓨터 액세스 확인에 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="41a64-148">This group is used by role-based access control to determine access to the machine</span></span> |

<span data-ttu-id="41a64-149">이 표에서는 장치의 주기적인 보고서 또는 신호인 하트비트 기반 장치 `DeviceInfo` 정보를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="41a64-149">The `DeviceInfo` table provides device information based on heartbeats, which are periodic reports or signals from a device.</span></span> <span data-ttu-id="41a64-150">15분마다 장치는 처럼 자주 변경되는 특성을 포함하는 부분 하트비트를 `LoggedOnUsers` 전송합니다.</span><span class="sxs-lookup"><span data-stu-id="41a64-150">Every fifteen minutes, the device sends a partial heartbeat that contains frequently changing attributes like `LoggedOnUsers`.</span></span> <span data-ttu-id="41a64-151">하루 중 한 번 장치의 특성을 포함하는 전체 하트비트가 전송됩니다.</span><span class="sxs-lookup"><span data-stu-id="41a64-151">Once a day, a full heartbeat containing the device's attributes is sent.</span></span>

<span data-ttu-id="41a64-152">다음 샘플 쿼리를 사용하여 장치의 최신 상태를 얻을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="41a64-152">You can use the following sample query to get the latest state of a device:</span></span>

```kusto
// Get latest information on user/device
DeviceInfo
| where DeviceName == "example" and isnotempty(OSPlatform)
| summarize arg_max(Timestamp, *) by DeviceId 
```

## <a name="related-topics"></a><span data-ttu-id="41a64-153">관련 항목</span><span class="sxs-lookup"><span data-stu-id="41a64-153">Related topics</span></span>
- [<span data-ttu-id="41a64-154">고급 헌팅 개요</span><span class="sxs-lookup"><span data-stu-id="41a64-154">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="41a64-155">쿼리 언어 배우기</span><span class="sxs-lookup"><span data-stu-id="41a64-155">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="41a64-156">공유 쿼리 사용</span><span class="sxs-lookup"><span data-stu-id="41a64-156">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="41a64-157">장치, 전자 메일, 앱 및 ID를 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="41a64-157">Hunt across devices, emails, apps, and identities</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="41a64-158">스키마의 이해</span><span class="sxs-lookup"><span data-stu-id="41a64-158">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="41a64-159">쿼리 모범 사례 적용</span><span class="sxs-lookup"><span data-stu-id="41a64-159">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
