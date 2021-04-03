---
title: 고급 헌팅Chema의 DeviceInfo 테이블
description: 고급 헌팅 schema의 DeviceInfo 표에서 OS, 컴퓨터 이름 및 기타 장치 정보에 대해 자세히 알아보기
keywords: 고급 헌팅, 위협 헌팅, 사이버 위협 헌팅, 검색, 쿼리, 원격 분석, schema 참조, kusto, 표, 열, 데이터 형식, 설명, deviceinfo, 장치, OS, 플랫폼, 사용자, DeviceInfo
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
ms.openlocfilehash: e6a11af94a5d2b2099d14b660cf65c846532ebd1
ms.sourcegitcommit: 582555d2b4ef5f2e2494ffdeab2c1d49e5d6b724
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/01/2021
ms.locfileid: "51500828"
---
# <a name="deviceinfo"></a><span data-ttu-id="989eb-104">DeviceInfo</span><span class="sxs-lookup"><span data-stu-id="989eb-104">DeviceInfo</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="989eb-105">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="989eb-105">**Applies to:**</span></span>
- [<span data-ttu-id="989eb-106">엔드포인트용 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="989eb-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)


><span data-ttu-id="989eb-107">Endpoint용 Defender를 경험하고 싶나요?</span><span class="sxs-lookup"><span data-stu-id="989eb-107">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="989eb-108">무료 평가판에 등록합니다.</span><span class="sxs-lookup"><span data-stu-id="989eb-108">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-advancedhuntingref-abovefoldlink)

<span data-ttu-id="989eb-109">고급 `DeviceInfo` 헌팅 [schema의](advanced-hunting-overview.md) 표에는 OS 버전, 활성 사용자 및 컴퓨터 이름을 포함하여 조직의 장치에 대한 정보가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="989eb-109">The `DeviceInfo` table in the [advanced hunting](advanced-hunting-overview.md) schema contains information about devices in the organization, including their OS version, active users, and computer name.</span></span> <span data-ttu-id="989eb-110">이 참조를 사용하여 표의 정보를 반환하는 쿼리를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="989eb-110">Use this reference to construct queries that return information from the table.</span></span>

<span data-ttu-id="989eb-111">고급 헌팅 스마의 다른 표에 대한 자세한 내용은 고급 헌팅 스마 [참조 를 참조하세요.](advanced-hunting-schema-reference.md)</span><span class="sxs-lookup"><span data-stu-id="989eb-111">For information on other tables in the advanced hunting schema, see [the advanced hunting schema reference](advanced-hunting-schema-reference.md).</span></span>

| <span data-ttu-id="989eb-112">열 이름</span><span class="sxs-lookup"><span data-stu-id="989eb-112">Column name</span></span> | <span data-ttu-id="989eb-113">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="989eb-113">Data type</span></span> | <span data-ttu-id="989eb-114">설명</span><span class="sxs-lookup"><span data-stu-id="989eb-114">Description</span></span> |
|-------------|-----------|-------------|
| `Timestamp` | <span data-ttu-id="989eb-115">datetime</span><span class="sxs-lookup"><span data-stu-id="989eb-115">datetime</span></span> | <span data-ttu-id="989eb-116">이벤트가 기록된 날짜와 시간</span><span class="sxs-lookup"><span data-stu-id="989eb-116">Date and time when the event was recorded</span></span> |
| `DeviceId` | <span data-ttu-id="989eb-117">문자열</span><span class="sxs-lookup"><span data-stu-id="989eb-117">string</span></span> | <span data-ttu-id="989eb-118">서비스에서 디바이스의 고유 식별자</span><span class="sxs-lookup"><span data-stu-id="989eb-118">Unique identifier for the device in the service</span></span> |
| `DeviceName` | <span data-ttu-id="989eb-119">문자열</span><span class="sxs-lookup"><span data-stu-id="989eb-119">string</span></span> | <span data-ttu-id="989eb-120">장치의 FQDN(FQDN)</span><span class="sxs-lookup"><span data-stu-id="989eb-120">Fully qualified domain name (FQDN) of the device</span></span> |
| `ClientVersion` | <span data-ttu-id="989eb-121">문자열</span><span class="sxs-lookup"><span data-stu-id="989eb-121">string</span></span> | <span data-ttu-id="989eb-122">디바이스에서 실행되는 끝점 에이전트 또는 센서의 버전</span><span class="sxs-lookup"><span data-stu-id="989eb-122">Version of the endpoint agent or sensor running on the device</span></span> |
| `PublicIP` | <span data-ttu-id="989eb-123">문자열</span><span class="sxs-lookup"><span data-stu-id="989eb-123">string</span></span> | <span data-ttu-id="989eb-124">등록된 장치에서 끝점용 Defender 서비스에 연결하는 데 사용하는 공용 IP 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="989eb-124">Public IP address used by the onboarded device to connect to the Defender for Endpoint service.</span></span> <span data-ttu-id="989eb-125">장치 자체의 IP 주소, NAT 장치 또는 프록시일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="989eb-125">This could be the IP address of the device itself, a NAT device, or a proxy</span></span> |
| `OSArchitecture` | <span data-ttu-id="989eb-126">문자열</span><span class="sxs-lookup"><span data-stu-id="989eb-126">string</span></span> | <span data-ttu-id="989eb-127">장치에서 실행되는 운영 체제의 아키텍처</span><span class="sxs-lookup"><span data-stu-id="989eb-127">Architecture of the operating system running on the device</span></span> |
| `OSPlatform` | <span data-ttu-id="989eb-128">문자열</span><span class="sxs-lookup"><span data-stu-id="989eb-128">string</span></span> | <span data-ttu-id="989eb-129">디바이스에서 실행되는 운영 체제의 플랫폼입니다.</span><span class="sxs-lookup"><span data-stu-id="989eb-129">Platform of the operating system running on the device.</span></span> <span data-ttu-id="989eb-130">이는 Windows 10 및 Windows 7과 같은 동일한 패밀리 내의 변형을 포함하여 특정 운영 체제를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="989eb-130">This indicates specific operating systems, including variations within the same family, such as Windows 10 and Windows 7</span></span> |
| `OSBuild` | <span data-ttu-id="989eb-131">문자열</span><span class="sxs-lookup"><span data-stu-id="989eb-131">string</span></span> | <span data-ttu-id="989eb-132">디바이스에서 실행되는 운영 체제의 빌드 버전</span><span class="sxs-lookup"><span data-stu-id="989eb-132">Build version of the operating system running on the device</span></span> |
| `IsAzureADJoined` | <span data-ttu-id="989eb-133">부울</span><span class="sxs-lookup"><span data-stu-id="989eb-133">boolean</span></span> | <span data-ttu-id="989eb-134">디바이스가 Azure Active Directory에 가입된지 여부를 나타내는 부울 표시기입니다.</span><span class="sxs-lookup"><span data-stu-id="989eb-134">Boolean indicator of whether device is joined to the Azure Active Directory</span></span> |
| `LoggedOnUsers` | <span data-ttu-id="989eb-135">문자열</span><span class="sxs-lookup"><span data-stu-id="989eb-135">string</span></span> | <span data-ttu-id="989eb-136">이벤트 당시 디바이스에 로그온된 모든 사용자 목록(JSON 배열 형식)입니다.</span><span class="sxs-lookup"><span data-stu-id="989eb-136">List of all users that are logged on the device at the time of the event in JSON array format</span></span> |
| `RegistryDeviceTag` | <span data-ttu-id="989eb-137">문자열</span><span class="sxs-lookup"><span data-stu-id="989eb-137">string</span></span> | <span data-ttu-id="989eb-138">레지스트리를 통해 추가된 장치 태그</span><span class="sxs-lookup"><span data-stu-id="989eb-138">Device tag added through the registry</span></span> |
| `ReportId` | <span data-ttu-id="989eb-139">long</span><span class="sxs-lookup"><span data-stu-id="989eb-139">long</span></span> | <span data-ttu-id="989eb-140">반복 카운터를 기반으로 하는 이벤트 식별자입니다.</span><span class="sxs-lookup"><span data-stu-id="989eb-140">Event identifier based on a repeating counter.</span></span> <span data-ttu-id="989eb-141">고유한 이벤트를 식별하려면 이 열을 DeviceName 및 Timestamp 열과 함께 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="989eb-141">To identify unique events, this column must be used in conjunction with the DeviceName and Timestamp columns</span></span> |
| `OSVersion` | <span data-ttu-id="989eb-142">문자열</span><span class="sxs-lookup"><span data-stu-id="989eb-142">string</span></span> | <span data-ttu-id="989eb-143">장치에서 실행되는 운영 체제 버전</span><span class="sxs-lookup"><span data-stu-id="989eb-143">Version of the operating system running on the device</span></span> |
| `MachineGroup` | <span data-ttu-id="989eb-144">문자열</span><span class="sxs-lookup"><span data-stu-id="989eb-144">string</span></span> | <span data-ttu-id="989eb-145">컴퓨터의 컴퓨터 그룹입니다.</span><span class="sxs-lookup"><span data-stu-id="989eb-145">Machine group of the machine.</span></span> <span data-ttu-id="989eb-146">이 그룹은 역할 기반 액세스 제어에서 컴퓨터 액세스 확인에 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="989eb-146">This group is used by role-based access control to determine access to the machine</span></span> |

## <a name="related-topics"></a><span data-ttu-id="989eb-147">관련 항목</span><span class="sxs-lookup"><span data-stu-id="989eb-147">Related topics</span></span>
- [<span data-ttu-id="989eb-148">지능형 헌팅 개요</span><span class="sxs-lookup"><span data-stu-id="989eb-148">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="989eb-149">쿼리 언어 배우기</span><span class="sxs-lookup"><span data-stu-id="989eb-149">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="989eb-150">스키마의 이해</span><span class="sxs-lookup"><span data-stu-id="989eb-150">Understand the schema</span></span>](advanced-hunting-schema-reference.md)
