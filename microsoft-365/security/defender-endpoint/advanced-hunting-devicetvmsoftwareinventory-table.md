---
title: 고급 헌팅 schema의 DeviceTvmSoftwareInventory 테이블
description: 고급 헌팅 스파이마의 DeviceTvmSoftwareInventory 표에서 장치의 소프트웨어 인벤토리에 대해 자세히 알아보습니다.
keywords: 고급 헌팅, 위협 헌팅, 사이버 위협 헌팅, mdatp, microsoft defender atp, wdatp 검색, 쿼리, 원격 분석, schema 참조, kusto, 표, 열, 데이터 형식, 설명, 위협 & 취약성 관리, TVM, 장치 관리, 소프트웨어, 인벤토리, 취약성, CVE ID, OS DeviceTvmSoftwareInventoryVulnerabilities
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
ms.openlocfilehash: 18e43d8e38c24a8aa28c6455dc1a769b8da0df2b
ms.sourcegitcommit: c75aac39ee8d93218a79585113ef6b36f47c9ddf
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/29/2021
ms.locfileid: "51408626"
---
# <a name="devicetvmsoftwareinventory"></a><span data-ttu-id="45754-104">DeviceTvmSoftwareInventory</span><span class="sxs-lookup"><span data-stu-id="45754-104">DeviceTvmSoftwareInventory</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="45754-105">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="45754-105">**Applies to:**</span></span>
- [<span data-ttu-id="45754-106">엔드포인트용 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="45754-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)

><span data-ttu-id="45754-107">Endpoint용 Defender를 경험하고 싶나요?</span><span class="sxs-lookup"><span data-stu-id="45754-107">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="45754-108">무료 평가판에 등록합니다.</span><span class="sxs-lookup"><span data-stu-id="45754-108">Sign up for a free trial.</span></span>](https://www.microsoft.com/WindowsForBusiness/windows-atp?ocid=docs-wdatp-advancedhuntingref-abovefoldlink)

[!include[Prerelease information](../../includes/prerelease.md)]

<span data-ttu-id="45754-109">고급 헌팅 계획의 표에는 지원 종료 정보를 포함하여 현재 네트워크의 장치에 설치된 소프트웨어의 위협 및 취약성 관리 인벤토리가 `DeviceTvmSoftwareInventory` 포함되어 있습니다. [](next-gen-threat-and-vuln-mgt.md)</span><span class="sxs-lookup"><span data-stu-id="45754-109">The `DeviceTvmSoftwareInventory` table in the advanced hunting schema contains the [threat and vulnerability management](next-gen-threat-and-vuln-mgt.md) inventory of software currently installed on devices in your network, including end of support information.</span></span> <span data-ttu-id="45754-110">예를 들어 현재 취약한 소프트웨어 버전으로 설치된 장치와 관련된 이벤트를 헌팅할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="45754-110">You can, for instance, hunt for events involving devices that are installed with a currently vulnerable software version.</span></span> <span data-ttu-id="45754-111">이 참조를 사용하여 표의 정보를 반환하는 쿼리를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="45754-111">Use this reference to construct queries that return information from the table.</span></span>

<span data-ttu-id="45754-112">DeviceTVMSoftwareInventory에는 위협 및 취약성 관리가 CPE(Common Platform Enumeration)와 일치할 수 있었던 모든 소프트웨어가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="45754-112">DeviceTVMSoftwareInventory contains all the software which threat and vulnerability management was able to match to a Common Platform Enumeration (CPE) – whether it is vulnerable or not.</span></span>

>[!NOTE]
><span data-ttu-id="45754-113">및 `DeviceTvmSoftwareInventory` `DeviceTvmSoftwareVulnerabilities` 테이블이 테이블을 `DeviceTvmSoftwareInventoryVulnerabilities` 대체했습니다.</span><span class="sxs-lookup"><span data-stu-id="45754-113">The `DeviceTvmSoftwareInventory` and `DeviceTvmSoftwareVulnerabilities` tables have replaced the `DeviceTvmSoftwareInventoryVulnerabilities` table.</span></span> <span data-ttu-id="45754-114">처음 두 표에는 취약점 관리 활동을 알리는 데 사용할 수 있는 열이 더 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="45754-114">Together, the first two tables include more columns you can use to help inform your vulnerability management activities.</span></span>

<span data-ttu-id="45754-115">고급 헌팅 스키마의 다른 표에 대한 자세한 내용은 [고급 헌팅 참조](/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-schema-reference)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="45754-115">For information on other tables in the advanced hunting schema, see [the advanced hunting reference](/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-schema-reference).</span></span>

| <span data-ttu-id="45754-116">열 이름</span><span class="sxs-lookup"><span data-stu-id="45754-116">Column name</span></span> | <span data-ttu-id="45754-117">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="45754-117">Data type</span></span> | <span data-ttu-id="45754-118">설명</span><span class="sxs-lookup"><span data-stu-id="45754-118">Description</span></span> |
|-------------|-----------|-------------|
| `DeviceId` | <span data-ttu-id="45754-119">문자열</span><span class="sxs-lookup"><span data-stu-id="45754-119">string</span></span> | <span data-ttu-id="45754-120">서비스에서 장치의 고유 식별자입니다.</span><span class="sxs-lookup"><span data-stu-id="45754-120">Unique identifier for the device in the service.</span></span> |
| `DeviceName` | <span data-ttu-id="45754-121">문자열</span><span class="sxs-lookup"><span data-stu-id="45754-121">string</span></span> | <span data-ttu-id="45754-122">장치의 FQDN(FQDN)입니다.</span><span class="sxs-lookup"><span data-stu-id="45754-122">Fully qualified domain name (FQDN) of the device.</span></span> |
| `OSPlatform` | <span data-ttu-id="45754-123">문자열</span><span class="sxs-lookup"><span data-stu-id="45754-123">string</span></span> | <span data-ttu-id="45754-124">디바이스에서 실행되는 운영 체제의 플랫폼입니다.</span><span class="sxs-lookup"><span data-stu-id="45754-124">Platform of the operating system running on the device.</span></span> <span data-ttu-id="45754-125">이는 Windows 10 및 Windows 7과 같이 동일한 제품군 내의 변형을 포함하여 특정 운영 체제를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="45754-125">This indicates specific operating systems, including variations within the same family, such as Windows 10 and Windows 7.</span></span> |
| `OSVersion` | <span data-ttu-id="45754-126">문자열</span><span class="sxs-lookup"><span data-stu-id="45754-126">string</span></span> | <span data-ttu-id="45754-127">장치에서 실행 중인 운영 체제의 버전입니다.</span><span class="sxs-lookup"><span data-stu-id="45754-127">Version of the operating system running on the device.</span></span> |
| `OSArchitecture` | <span data-ttu-id="45754-128">문자열</span><span class="sxs-lookup"><span data-stu-id="45754-128">string</span></span> | <span data-ttu-id="45754-129">장치에서 실행되는 운영 체제의 아키텍처입니다.</span><span class="sxs-lookup"><span data-stu-id="45754-129">Architecture of the operating system running on the device.</span></span> |
| `SoftwareVendor` | <span data-ttu-id="45754-130">문자열</span><span class="sxs-lookup"><span data-stu-id="45754-130">string</span></span> | <span data-ttu-id="45754-131">소프트웨어 공급업체의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="45754-131">Name of the software vendor.</span></span> |
| `SoftwareName` | <span data-ttu-id="45754-132">문자열</span><span class="sxs-lookup"><span data-stu-id="45754-132">string</span></span> | <span data-ttu-id="45754-133">소프트웨어 제품의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="45754-133">Name of the software product.</span></span> |
| `SoftwareVersion` | <span data-ttu-id="45754-134">문자열</span><span class="sxs-lookup"><span data-stu-id="45754-134">string</span></span> | <span data-ttu-id="45754-135">소프트웨어 제품의 버전 번호입니다.</span><span class="sxs-lookup"><span data-stu-id="45754-135">Version number of the software product.</span></span> |
| `EndOfSupportStatus` | <span data-ttu-id="45754-136">문자열</span><span class="sxs-lookup"><span data-stu-id="45754-136">string</span></span> | <span data-ttu-id="45754-137">지정된 EOS(지원 종료) 또는 EOL(수명 종료) 날짜를 상대로 소프트웨어 제품의 수명 주기 스테이지를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="45754-137">Indicates the lifecycle stage of the software product relative to its specified end-of-support (EOS) or end-of-life (EOL) date.</span></span> |
| `EndOfSupportDate` | <span data-ttu-id="45754-138">문자열</span><span class="sxs-lookup"><span data-stu-id="45754-138">string</span></span> | <span data-ttu-id="45754-139">소프트웨어 제품의 EOS(지원 종료) 또는 EOL(종료 날짜)</span><span class="sxs-lookup"><span data-stu-id="45754-139">End-of-support (EOS) or end-of-life (EOL) date of the software product.</span></span> |

## <a name="related-topics"></a><span data-ttu-id="45754-140">관련 항목</span><span class="sxs-lookup"><span data-stu-id="45754-140">Related topics</span></span>

- [<span data-ttu-id="45754-141">지능형 헌팅 개요</span><span class="sxs-lookup"><span data-stu-id="45754-141">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="45754-142">쿼리 언어 배우기</span><span class="sxs-lookup"><span data-stu-id="45754-142">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="45754-143">스키마에 대한 이해</span><span class="sxs-lookup"><span data-stu-id="45754-143">Understand the schema</span></span>](advanced-hunting-schema-reference.md)
- [<span data-ttu-id="45754-144">위협 및 취약성 관리 개요</span><span class="sxs-lookup"><span data-stu-id="45754-144">Overview of Threat & Vulnerability Management</span></span>](next-gen-threat-and-vuln-mgt.md)
