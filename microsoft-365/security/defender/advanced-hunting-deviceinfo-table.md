---
title: 고급 헌팅Chema의 DeviceInfo 테이블
description: 고급 헌팅 schema의 DeviceInfo 표에서 OS, 컴퓨터 이름 및 기타 컴퓨터 정보에 대해 자세히 알아보기
keywords: 고급 헌팅, 위협 헌팅, 사이버 위협 헌팅, Microsoft 365 Defender, microsoft 365, m365, 검색, 쿼리, 원격 분석, 스마마 참조, kusto, 표, 열, 데이터 형식, 설명, machineinfo, DeviceInfo, 장치, 컴퓨터, OS, 플랫폼, 사용자
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: maccruz
author: schmurky
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: 99a07b1517058b0e5ab241aaae9c6899e2994432
ms.sourcegitcommit: 82a4d74020cd93ba444006317cfecc178c6d41dc
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/27/2021
ms.locfileid: "52689112"
---
# <a name="deviceinfo"></a><span data-ttu-id="8a667-104">DeviceInfo</span><span class="sxs-lookup"><span data-stu-id="8a667-104">DeviceInfo</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="8a667-105">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="8a667-105">**Applies to:**</span></span>
- <span data-ttu-id="8a667-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="8a667-106">Microsoft 365 Defender</span></span>
- <span data-ttu-id="8a667-107">끝점용 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="8a667-107">Microsoft Defender for Endpoint</span></span>



<span data-ttu-id="8a667-108">고급 `DeviceInfo` 헌팅 [schema의](advanced-hunting-overview.md) 표에는 OS 버전, 활성 사용자 및 컴퓨터 이름을 비롯한 조직의 장치에 대한 정보가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8a667-108">The `DeviceInfo` table in the [advanced hunting](advanced-hunting-overview.md) schema contains information about devices in the organization, including OS version, active users, and computer name.</span></span> <span data-ttu-id="8a667-109">이 참조를 사용하여 이 표의 정보를 반환하는 쿼리를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="8a667-109">Use this reference to construct queries that return information from this table.</span></span>

<span data-ttu-id="8a667-110">고급 헌팅 스키마의 다른 표에 대한 자세한 내용은 [고급 헌팅 참조](advanced-hunting-schema-tables.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="8a667-110">For information on other tables in the advanced hunting schema, [see the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="8a667-111">열 이름</span><span class="sxs-lookup"><span data-stu-id="8a667-111">Column name</span></span> | <span data-ttu-id="8a667-112">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="8a667-112">Data type</span></span> | <span data-ttu-id="8a667-113">설명</span><span class="sxs-lookup"><span data-stu-id="8a667-113">Description</span></span> |
|-------------|-----------|-------------|
| `Timestamp` | <span data-ttu-id="8a667-114">datetime</span><span class="sxs-lookup"><span data-stu-id="8a667-114">datetime</span></span> | <span data-ttu-id="8a667-115">이벤트가 기록된 날짜와 시간</span><span class="sxs-lookup"><span data-stu-id="8a667-115">Date and time when the event was recorded</span></span> |
| `DeviceId` | <span data-ttu-id="8a667-116">문자열</span><span class="sxs-lookup"><span data-stu-id="8a667-116">string</span></span> | <span data-ttu-id="8a667-117">서비스에서 시스템의 고유 식별자</span><span class="sxs-lookup"><span data-stu-id="8a667-117">Unique identifier for the machine in the service</span></span> |
| `DeviceName` | <span data-ttu-id="8a667-118">문자열</span><span class="sxs-lookup"><span data-stu-id="8a667-118">string</span></span> | <span data-ttu-id="8a667-119">컴퓨터의 FQDN(정규화된 도메인 이름)</span><span class="sxs-lookup"><span data-stu-id="8a667-119">Fully qualified domain name (FQDN) of the machine</span></span> |
| `ClientVersion` | <span data-ttu-id="8a667-120">문자열</span><span class="sxs-lookup"><span data-stu-id="8a667-120">string</span></span> | <span data-ttu-id="8a667-121">기기에서 실행되는 끝점 에이전트 또는 센서의 버전</span><span class="sxs-lookup"><span data-stu-id="8a667-121">Version of the endpoint agent or sensor running on the machine</span></span> |
| `PublicIP` | <span data-ttu-id="8a667-122">문자열</span><span class="sxs-lookup"><span data-stu-id="8a667-122">string</span></span> | <span data-ttu-id="8a667-123">등록된 컴퓨터에 의해 끝점용 Microsoft Defender 서비스에 연결하는 데 사용되는 공용 IP 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="8a667-123">Public IP address used by the onboarded machine to connect to the Microsoft  Defender for Endpoint service.</span></span> <span data-ttu-id="8a667-124">컴퓨터 자체의 IP 주소, NAT 장치 또는 프록시일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8a667-124">This could be the IP address of the machine itself, a NAT device, or a proxy</span></span> |
| `OSArchitecture` | <span data-ttu-id="8a667-125">문자열</span><span class="sxs-lookup"><span data-stu-id="8a667-125">string</span></span> | <span data-ttu-id="8a667-126">컴퓨터에서 실행 중인 운영 체제의 아키텍처</span><span class="sxs-lookup"><span data-stu-id="8a667-126">Architecture of the operating system running on the machine</span></span> |
| `OSPlatform` | <span data-ttu-id="8a667-127">문자열</span><span class="sxs-lookup"><span data-stu-id="8a667-127">string</span></span> | <span data-ttu-id="8a667-128">컴퓨터에서 실행 중인 운영 체제의 플랫폼</span><span class="sxs-lookup"><span data-stu-id="8a667-128">Platform of the operating system running on the machine.</span></span> <span data-ttu-id="8a667-129">이는 Windows 10 및 Windows 7과 같은 동일한 패밀리 내의 변형을 포함하여 특정 운영 체제를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="8a667-129">This indicates specific operating systems, including variations within the same family, such as Windows 10 and Windows 7</span></span> |
| `OSBuild` | <span data-ttu-id="8a667-130">문자열</span><span class="sxs-lookup"><span data-stu-id="8a667-130">string</span></span> | <span data-ttu-id="8a667-131">시스템에서 실행되는 운영 체제의 빌드 버전</span><span class="sxs-lookup"><span data-stu-id="8a667-131">Build version of the operating system running on the machine</span></span> |
| `IsAzureADJoined` | <span data-ttu-id="8a667-132">부울</span><span class="sxs-lookup"><span data-stu-id="8a667-132">boolean</span></span> | <span data-ttu-id="8a667-133">컴퓨터의 가입 여부를 나타내는 부울 표시기입니다Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="8a667-133">Boolean indicator of whether machine is joined to the Azure Active Directory</span></span> |
| `AadObjectId` | <span data-ttu-id="8a667-134">문자열</span><span class="sxs-lookup"><span data-stu-id="8a667-134">string</span></span> | <span data-ttu-id="8a667-135">Azure AD에서 디바이스의 고유 식별자</span><span class="sxs-lookup"><span data-stu-id="8a667-135">Unique identifier for the device in Azure AD</span></span> |
| `LoggedOnUsers` | <span data-ttu-id="8a667-136">문자열</span><span class="sxs-lookup"><span data-stu-id="8a667-136">string</span></span> | <span data-ttu-id="8a667-137">이벤트 당시 컴퓨터에 로그온한 모든 사용자 목록(JSON 배열 형식)입니다.</span><span class="sxs-lookup"><span data-stu-id="8a667-137">List of all users that are logged on the machine at the time of the event in JSON array format</span></span> |
| `RegistryDeviceTag` | <span data-ttu-id="8a667-138">문자열</span><span class="sxs-lookup"><span data-stu-id="8a667-138">string</span></span> | <span data-ttu-id="8a667-139">레지스트리를 통해 추가된 컴퓨터 태그</span><span class="sxs-lookup"><span data-stu-id="8a667-139">Machine tag added through the registry</span></span> |
| `OSVersion` | <span data-ttu-id="8a667-140">문자열</span><span class="sxs-lookup"><span data-stu-id="8a667-140">string</span></span> | <span data-ttu-id="8a667-141">컴퓨터에서 실행 중인 운영 체제 버전</span><span class="sxs-lookup"><span data-stu-id="8a667-141">Version of the operating system running on the machine</span></span> |
| `MachineGroup` | <span data-ttu-id="8a667-142">문자열</span><span class="sxs-lookup"><span data-stu-id="8a667-142">string</span></span> | <span data-ttu-id="8a667-143">컴퓨터의 컴퓨터 그룹입니다.</span><span class="sxs-lookup"><span data-stu-id="8a667-143">Machine group of the machine.</span></span> <span data-ttu-id="8a667-144">이 그룹은 역할 기반 액세스 제어에서 컴퓨터 액세스 확인에 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="8a667-144">This group is used by role-based access control to determine access to the machine</span></span> |
| `ReportId` | <span data-ttu-id="8a667-145">long</span><span class="sxs-lookup"><span data-stu-id="8a667-145">long</span></span> | <span data-ttu-id="8a667-146">반복 카운터를 기반으로 하는 이벤트 식별자입니다.</span><span class="sxs-lookup"><span data-stu-id="8a667-146">Event identifier based on a repeating counter.</span></span> <span data-ttu-id="8a667-147">고유한 이벤트를 식별하려면 이 열을 DeviceName 및 Timestamp 열과 함께 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8a667-147">To identify unique events, this column must be used in conjunction with the DeviceName and Timestamp columns</span></span> |
| `OnboardingStatus` | <span data-ttu-id="8a667-148">문자열</span><span class="sxs-lookup"><span data-stu-id="8a667-148">string</span></span> | <span data-ttu-id="8a667-149">디바이스가 현재 Microsoft Defender For Endpoint에 온보딩 상태인지 또는 디바이스가 지원되지 않는지 여부를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="8a667-149">Indicates whether the device is currently onboarded or not to Microsoft Defender For Endpoint or if the device is not supported</span></span> |
|`AdditionalFields` | <span data-ttu-id="8a667-150">문자열</span><span class="sxs-lookup"><span data-stu-id="8a667-150">string</span></span> | <span data-ttu-id="8a667-151">JSON 배열 형식의 이벤트에 대한 추가 정보</span><span class="sxs-lookup"><span data-stu-id="8a667-151">Additional information about the event in JSON array format</span></span> |
|`DeviceCategory` | <span data-ttu-id="8a667-152">문자열</span><span class="sxs-lookup"><span data-stu-id="8a667-152">string</span></span> | <span data-ttu-id="8a667-153">끝점, 네트워크 장치, IoT, 알 수 없음 범주의 특정 장치 유형을 그룹화하는 더 광범위한 분류</span><span class="sxs-lookup"><span data-stu-id="8a667-153">Broader classification that groups certain device types under the following categories: Endpoint, Network device, IoT, Unknown</span></span> |
|`DeviceType` | <span data-ttu-id="8a667-154">문자열</span><span class="sxs-lookup"><span data-stu-id="8a667-154">string</span></span> | <span data-ttu-id="8a667-155">네트워크 장치, Workstation, 서버, 모바일, 게임 콘솔 또는 프린터와 같은 용도 및 기능을 기반으로 하는 장치 유형</span><span class="sxs-lookup"><span data-stu-id="8a667-155">Type of device based on purpose and functionality, such as network device, workstation, server, mobile, gaming console, or printer</span></span> |
|`DeviceSubType` | <span data-ttu-id="8a667-156">문자열</span><span class="sxs-lookup"><span data-stu-id="8a667-156">string</span></span> | <span data-ttu-id="8a667-157">특정 유형의 장치에 대한 추가 수정자(예: 모바일 장치는 태블릿 또는 스마트폰일 수 있습니다)입니다.</span><span class="sxs-lookup"><span data-stu-id="8a667-157">Additional modifier for certain types of devices, for example, a mobile device can be a tablet or a smartphone</span></span> |
|`Model` | <span data-ttu-id="8a667-158">문자열</span><span class="sxs-lookup"><span data-stu-id="8a667-158">string</span></span> | <span data-ttu-id="8a667-159">공급업체 또는 제조업체의 모델 이름 또는 제품 번호</span><span class="sxs-lookup"><span data-stu-id="8a667-159">Model name or number of the product from the vendor or manufacturer</span></span> |
|`Vendor` | <span data-ttu-id="8a667-160">문자열</span><span class="sxs-lookup"><span data-stu-id="8a667-160">string</span></span> | <span data-ttu-id="8a667-161">제품 공급업체 또는 제조업체의 이름</span><span class="sxs-lookup"><span data-stu-id="8a667-161">Name of the product vendor or manufacturer</span></span> |
|`OSDistribution` | <span data-ttu-id="8a667-162">문자열</span><span class="sxs-lookup"><span data-stu-id="8a667-162">string</span></span> | <span data-ttu-id="8a667-163">Linux 플랫폼용 Ubuntu 또는 RedHat와 같은 OS 플랫폼 배포</span><span class="sxs-lookup"><span data-stu-id="8a667-163">Distribution of the OS platform, such as Ubuntu or RedHat for Linux platforms</span></span> |
|`OSVersionInfo` | <span data-ttu-id="8a667-164">문자열</span><span class="sxs-lookup"><span data-stu-id="8a667-164">string</span></span> | <span data-ttu-id="8a667-165">인기 있는 이름, 코드 이름 또는 버전 번호와 같은 OS 버전에 대한 추가 정보</span><span class="sxs-lookup"><span data-stu-id="8a667-165">Additional information about the OS version, such as the popular name, code name, or version number</span></span> |
|`MergedDeviceIds` | <span data-ttu-id="8a667-166">문자열</span><span class="sxs-lookup"><span data-stu-id="8a667-166">string</span></span> | <span data-ttu-id="8a667-167">동일한 장치에 할당된 이전 장치 ID</span><span class="sxs-lookup"><span data-stu-id="8a667-167">Previous device IDs that have been assigned to the same device</span></span> |
|`MergedToDeviceId` | <span data-ttu-id="8a667-168">문자열</span><span class="sxs-lookup"><span data-stu-id="8a667-168">string</span></span> | <span data-ttu-id="8a667-169">장치에 할당된 최신 장치 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="8a667-169">The most recent device ID assigned to a device</span></span> |

<span data-ttu-id="8a667-170">이 표에서는 장치의 주기적인 보고서 또는 신호인 하트비트 기반 장치 `DeviceInfo` 정보를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="8a667-170">The `DeviceInfo` table provides device information based on heartbeats, which are periodic reports or signals from a device.</span></span> <span data-ttu-id="8a667-171">15분마다 장치는 처럼 자주 변경되는 특성을 포함하는 부분 하트비트를 `LoggedOnUsers` 전송합니다.</span><span class="sxs-lookup"><span data-stu-id="8a667-171">Every fifteen minutes, the device sends a partial heartbeat that contains frequently changing attributes like `LoggedOnUsers`.</span></span> <span data-ttu-id="8a667-172">하루 중 한 번 장치의 특성을 포함하는 전체 하트비트가 전송됩니다.</span><span class="sxs-lookup"><span data-stu-id="8a667-172">Once a day, a full heartbeat containing the device's attributes is sent.</span></span>

<span data-ttu-id="8a667-173">다음 샘플 쿼리를 사용하여 장치의 최신 상태를 얻을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8a667-173">You can use the following sample query to get the latest state of a device:</span></span>

```kusto
// Get latest information on user/device
DeviceInfo
| where DeviceName == "example" and isnotempty(OSPlatform)
| summarize arg_max(Timestamp, *) by DeviceId 
```

## <a name="related-topics"></a><span data-ttu-id="8a667-174">관련 항목</span><span class="sxs-lookup"><span data-stu-id="8a667-174">Related topics</span></span>
- [<span data-ttu-id="8a667-175">지능형 헌팅 개요</span><span class="sxs-lookup"><span data-stu-id="8a667-175">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="8a667-176">쿼리 언어 배우기</span><span class="sxs-lookup"><span data-stu-id="8a667-176">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="8a667-177">공유 쿼리 사용</span><span class="sxs-lookup"><span data-stu-id="8a667-177">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="8a667-178">장치, 전자 메일, 앱 및 ID를 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="8a667-178">Hunt across devices, emails, apps, and identities</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="8a667-179">스키마의 이해</span><span class="sxs-lookup"><span data-stu-id="8a667-179">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="8a667-180">쿼리 모범 사례 적용</span><span class="sxs-lookup"><span data-stu-id="8a667-180">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
