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
ms.openlocfilehash: fc9e5fb29518207c5360d5fbe29b8b4848d350e2
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51075543"
---
# <a name="devicetvmsoftwareinventory"></a><span data-ttu-id="f5131-104">DeviceTvmSoftwareInventory</span><span class="sxs-lookup"><span data-stu-id="f5131-104">DeviceTvmSoftwareInventory</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="f5131-105">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="f5131-105">**Applies to:**</span></span>
- [<span data-ttu-id="f5131-106">엔드포인트용 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="f5131-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)

><span data-ttu-id="f5131-107">Endpoint용 Defender를 경험하고 싶나요?</span><span class="sxs-lookup"><span data-stu-id="f5131-107">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="f5131-108">무료 평가판에 등록합니다.</span><span class="sxs-lookup"><span data-stu-id="f5131-108">Sign up for a free trial.</span></span>](https://www.microsoft.com/WindowsForBusiness/windows-atp?ocid=docs-wdatp-advancedhuntingref-abovefoldlink)

[!include[Prerelease information](../../includes/prerelease.md)]

<span data-ttu-id="f5131-109">고급 헌팅 & 표에는 지원 종료 정보를 포함하여 현재 네트워크의 장치에 설치된 소프트웨어의 위협 & 취약성 관리 인벤토리가 `DeviceTvmSoftwareInventory` 포함되어 있습니다. [](next-gen-threat-and-vuln-mgt.md)</span><span class="sxs-lookup"><span data-stu-id="f5131-109">The `DeviceTvmSoftwareInventory` table in the advanced hunting schema contains the [Threat & Vulnerability Management](next-gen-threat-and-vuln-mgt.md) inventory of software currently installed on devices in your network, including end of support information.</span></span> <span data-ttu-id="f5131-110">예를 들어 현재 취약한 소프트웨어 버전으로 설치된 장치와 관련된 이벤트를 헌팅할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f5131-110">You can, for instance, hunt for events involving devices that are installed with a currently vulnerable software version.</span></span> <span data-ttu-id="f5131-111">이 참조를 사용하여 표의 정보를 반환하는 쿼리를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="f5131-111">Use this reference to construct queries that return information from the table.</span></span>

>[!NOTE]
><span data-ttu-id="f5131-112">및 `DeviceTvmSoftwareInventory` `DeviceTvmSoftwareVulnerabilities` 테이블이 테이블을 `DeviceTvmSoftwareInventoryVulnerabilities` 대체했습니다.</span><span class="sxs-lookup"><span data-stu-id="f5131-112">The `DeviceTvmSoftwareInventory` and `DeviceTvmSoftwareVulnerabilities` tables have replaced the `DeviceTvmSoftwareInventoryVulnerabilities` table.</span></span> <span data-ttu-id="f5131-113">처음 두 표에는 취약점 관리 활동을 알리는 데 사용할 수 있는 열이 더 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f5131-113">Together, the first two tables include more columns you can use to help inform your vulnerability management activities.</span></span>

<span data-ttu-id="f5131-114">고급 헌팅 스키마의 다른 표에 대한 자세한 내용은 [고급 헌팅 참조](/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-schema-reference)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="f5131-114">For information on other tables in the advanced hunting schema, see [the advanced hunting reference](/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-schema-reference).</span></span>

| <span data-ttu-id="f5131-115">열 이름</span><span class="sxs-lookup"><span data-stu-id="f5131-115">Column name</span></span> | <span data-ttu-id="f5131-116">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="f5131-116">Data type</span></span> | <span data-ttu-id="f5131-117">설명</span><span class="sxs-lookup"><span data-stu-id="f5131-117">Description</span></span> |
|-------------|-----------|-------------|
| `DeviceId` | <span data-ttu-id="f5131-118">문자열</span><span class="sxs-lookup"><span data-stu-id="f5131-118">string</span></span> | <span data-ttu-id="f5131-119">서비스에서 디바이스의 고유 식별자</span><span class="sxs-lookup"><span data-stu-id="f5131-119">Unique identifier for the device in the service</span></span> |
| `DeviceName` | <span data-ttu-id="f5131-120">문자열</span><span class="sxs-lookup"><span data-stu-id="f5131-120">string</span></span> | <span data-ttu-id="f5131-121">장치의 FQDN(FQDN)</span><span class="sxs-lookup"><span data-stu-id="f5131-121">Fully qualified domain name (FQDN) of the device</span></span> |
| `OSPlatform` | <span data-ttu-id="f5131-122">문자열</span><span class="sxs-lookup"><span data-stu-id="f5131-122">string</span></span> | <span data-ttu-id="f5131-123">디바이스에서 실행되는 운영 체제의 플랫폼입니다.</span><span class="sxs-lookup"><span data-stu-id="f5131-123">Platform of the operating system running on the device.</span></span> <span data-ttu-id="f5131-124">이는 Windows 10 및 Windows 7과 같이 동일한 제품군 내의 변형을 포함하여 특정 운영 체제를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="f5131-124">This indicates specific operating systems, including variations within the same family, such as Windows 10 and Windows 7.</span></span> |
| `OSVersion` | <span data-ttu-id="f5131-125">문자열</span><span class="sxs-lookup"><span data-stu-id="f5131-125">string</span></span> | <span data-ttu-id="f5131-126">장치에서 실행되는 운영 체제 버전</span><span class="sxs-lookup"><span data-stu-id="f5131-126">Version of the operating system running on the device</span></span> |
| `OSArchitecture` | <span data-ttu-id="f5131-127">문자열</span><span class="sxs-lookup"><span data-stu-id="f5131-127">string</span></span> | <span data-ttu-id="f5131-128">장치에서 실행되는 운영 체제의 아키텍처</span><span class="sxs-lookup"><span data-stu-id="f5131-128">Architecture of the operating system running on the device</span></span> |
| `SoftwareVendor` | <span data-ttu-id="f5131-129">문자열</span><span class="sxs-lookup"><span data-stu-id="f5131-129">string</span></span> | <span data-ttu-id="f5131-130">소프트웨어 공급업체의 이름</span><span class="sxs-lookup"><span data-stu-id="f5131-130">Name of the software vendor</span></span> |
| `SoftwareName` | <span data-ttu-id="f5131-131">문자열</span><span class="sxs-lookup"><span data-stu-id="f5131-131">string</span></span> | <span data-ttu-id="f5131-132">소프트웨어 제품의 이름</span><span class="sxs-lookup"><span data-stu-id="f5131-132">Name of the software product</span></span> |
| `SoftwareVersion` | <span data-ttu-id="f5131-133">문자열</span><span class="sxs-lookup"><span data-stu-id="f5131-133">string</span></span> | <span data-ttu-id="f5131-134">소프트웨어 제품의 버전 번호</span><span class="sxs-lookup"><span data-stu-id="f5131-134">Version number of the software product</span></span> |
| `EndOfSupportStatus` | <span data-ttu-id="f5131-135">문자열</span><span class="sxs-lookup"><span data-stu-id="f5131-135">string</span></span> | <span data-ttu-id="f5131-136">지정된 EOS(지원 종료) 또는 EOL(종료 날짜)을 상대로 소프트웨어 제품의 수명 주기 스테이지를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="f5131-136">Indicates the lifecycle stage of the software product relative to its specified end-of-support (EOS) or end-of-life (EOL) date</span></span> |
| `EndOfSupportDate` | <span data-ttu-id="f5131-137">문자열</span><span class="sxs-lookup"><span data-stu-id="f5131-137">string</span></span> | <span data-ttu-id="f5131-138">소프트웨어 제품의 EOS(지원 종료) 또는 EOL(종료 날짜)</span><span class="sxs-lookup"><span data-stu-id="f5131-138">End-of-support (EOS) or end-of-life (EOL) date of the software product</span></span> |



## <a name="related-topics"></a><span data-ttu-id="f5131-139">관련 항목</span><span class="sxs-lookup"><span data-stu-id="f5131-139">Related topics</span></span>

- [<span data-ttu-id="f5131-140">고급 헌팅 개요</span><span class="sxs-lookup"><span data-stu-id="f5131-140">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="f5131-141">쿼리 언어 배우기</span><span class="sxs-lookup"><span data-stu-id="f5131-141">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="f5131-142">스키마의 이해</span><span class="sxs-lookup"><span data-stu-id="f5131-142">Understand the schema</span></span>](advanced-hunting-schema-reference.md)
- [<span data-ttu-id="f5131-143">위협 및 취약성 관리 개요</span><span class="sxs-lookup"><span data-stu-id="f5131-143">Overview of Threat & Vulnerability Management</span></span>](next-gen-threat-and-vuln-mgt.md)

