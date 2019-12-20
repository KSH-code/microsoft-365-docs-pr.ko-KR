---
title: Microsoft Threat Protection 고급 헌팅 스키마의 데이터 표
description: 고급 헌팅 스키마의 표에 대해 알아보고 고급 헌팅, 위협 헌팅, 사이버 위협 헌팅, 검색, 쿼리, 원격 분석,
keywords: 스키마 참조, kusto, 표, 데이터에 대한 위협 헌팅 쿼리를 실행할 수 있는 데이터를 이해합니다.
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: lomayor
author: lomayor
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.openlocfilehash: 631b328168003668ed06e37d76177c327794ed18
ms.sourcegitcommit: 0ad0092d9c5cb2d69fc70c990a9b7cc03140611b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/19/2019
ms.locfileid: "40808663"
---
# <a name="understand-the-advanced-hunting-schema"></a><span data-ttu-id="79f4d-104">고급 헌팅 스키마 이해</span><span class="sxs-lookup"><span data-stu-id="79f4d-104">Understand the advanced hunting schema</span></span>

<span data-ttu-id="79f4d-105">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="79f4d-105">**Applies to:**</span></span>
- <span data-ttu-id="79f4d-106">Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="79f4d-106">Microsoft Threat Protection</span></span>

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

<span data-ttu-id="79f4d-107">[고급 헌팅](advanced-hunting-overview.md) 스키마는 이벤트 정보나 컴퓨터 및 엔터티에 대한 정보를 제공하는 여러 표로 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="79f4d-107">The [advanced hunting](advanced-hunting-overview.md) schema is made up of multiple tables that provide either event information or information about machines and entities.</span></span> <span data-ttu-id="79f4d-108">여러 표를 포괄하는 쿼리를 효과적으로 작성하려면 고급 헌팅 스키마에서 표 및 열을 이해해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="79f4d-108">To effectively build queries that span multiple tables, you need to understand the tables and the columns in the advanced hunting schema.</span></span>

## <a name="schema-tables"></a><span data-ttu-id="79f4d-109">스키마 표</span><span class="sxs-lookup"><span data-stu-id="79f4d-109">Schema tables</span></span>

<span data-ttu-id="79f4d-110">다음 참조는 스키마에서 모든 표를 나열합니다.</span><span class="sxs-lookup"><span data-stu-id="79f4d-110">The following reference lists all the tables in the schema.</span></span> <span data-ttu-id="79f4d-111">각 표 이름은 해당 표의 열 이름을 설명하는 페이지에 연결됩니다.</span><span class="sxs-lookup"><span data-stu-id="79f4d-111">Each table name links to a page describing the column names for that table.</span></span> <span data-ttu-id="79f4d-112">표 및 열 이름은 고급 헌팅 화면에서 스키마 표현의 일부로 보안 센터에도 나열됩니다.</span><span class="sxs-lookup"><span data-stu-id="79f4d-112">Table and column names are also listed in the security center as part of the the schema representation on the advanced hunting screen.</span></span>

| <span data-ttu-id="79f4d-113">테이블 이름</span><span class="sxs-lookup"><span data-stu-id="79f4d-113">Table name</span></span> | <span data-ttu-id="79f4d-114">설명</span><span class="sxs-lookup"><span data-stu-id="79f4d-114">Description</span></span> |
|------------|-------------|
| <span data-ttu-id="79f4d-115">**[DeviceInfo](advanced-hunting-deviceinfo-table.md)**</span><span class="sxs-lookup"><span data-stu-id="79f4d-115">**[DeviceInfo](advanced-hunting-deviceinfo-table.md)**</span></span> | <span data-ttu-id="79f4d-116">컴퓨터 정보(OS 정보 포함)</span><span class="sxs-lookup"><span data-stu-id="79f4d-116">Machine information, including OS information</span></span> |
| <span data-ttu-id="79f4d-117">**[DeviceNetworkInfo](advanced-hunting-devicenetworkinfo-table.md)**</span><span class="sxs-lookup"><span data-stu-id="79f4d-117">**[DeviceNetworkInfo](advanced-hunting-devicenetworkinfo-table.md)**</span></span> | <span data-ttu-id="79f4d-118">연결된 네트워크 및 도메인뿐만 아니라 어댑터, IP 및 MAC 주소를 비롯한 컴퓨터의 네트워크 속성</span><span class="sxs-lookup"><span data-stu-id="79f4d-118">Network properties of machines, including adapters, IP and MAC addresses, as well as connected networks and domains</span></span> |
| <span data-ttu-id="79f4d-119">**[DeviceProcessEvents](advanced-hunting-deviceprocessevents-table.md)**</span><span class="sxs-lookup"><span data-stu-id="79f4d-119">**[DeviceProcessEvents](advanced-hunting-deviceprocessevents-table.md)**</span></span> | <span data-ttu-id="79f4d-120">프로세스 생성 및 관련 이벤트</span><span class="sxs-lookup"><span data-stu-id="79f4d-120">Process creation and related events</span></span> |
| <span data-ttu-id="79f4d-121">**[DeviceNetworkEvents](advanced-hunting-devicenetworkevents-table.md)**</span><span class="sxs-lookup"><span data-stu-id="79f4d-121">**[DeviceNetworkEvents](advanced-hunting-devicenetworkevents-table.md)**</span></span> | <span data-ttu-id="79f4d-122">네트워크 연결 및 관련 이벤트</span><span class="sxs-lookup"><span data-stu-id="79f4d-122">Network connection and related events</span></span> |
| <span data-ttu-id="79f4d-123">**[DeviceFileEvents](advanced-hunting-devicefileevents-table.md)**</span><span class="sxs-lookup"><span data-stu-id="79f4d-123">**[DeviceFileEvents](advanced-hunting-devicefileevents-table.md)**</span></span> | <span data-ttu-id="79f4d-124">파일 생성, 수정 및 기타 파일 시스템 이벤트</span><span class="sxs-lookup"><span data-stu-id="79f4d-124">File creation, modification, and other file system events</span></span> |
| <span data-ttu-id="79f4d-125">**[DeviceRegistryEvents](advanced-hunting-deviceregistryevents-table.md)**</span><span class="sxs-lookup"><span data-stu-id="79f4d-125">**[DeviceRegistryEvents](advanced-hunting-deviceregistryevents-table.md)**</span></span> | <span data-ttu-id="79f4d-126">레지스트리 항목 생성 및 수정</span><span class="sxs-lookup"><span data-stu-id="79f4d-126">Creation and modification of registry entries</span></span> |
| <span data-ttu-id="79f4d-127">**[DeviceLogonEvents](advanced-hunting-devicelogonevents-table.md)**</span><span class="sxs-lookup"><span data-stu-id="79f4d-127">**[DeviceLogonEvents](advanced-hunting-devicelogonevents-table.md)**</span></span> | <span data-ttu-id="79f4d-128">로그인 및 기타 인증 이벤트</span><span class="sxs-lookup"><span data-stu-id="79f4d-128">Sign-ins and other authentication events</span></span> |
| <span data-ttu-id="79f4d-129">**[DeviceImageLoadEvents](advanced-hunting-deviceimageloadevents-table.md)**</span><span class="sxs-lookup"><span data-stu-id="79f4d-129">**[DeviceImageLoadEvents](advanced-hunting-deviceimageloadevents-table.md)**</span></span> | <span data-ttu-id="79f4d-130">DLL 로딩 이벤트</span><span class="sxs-lookup"><span data-stu-id="79f4d-130">DLL loading events</span></span> |
| <span data-ttu-id="79f4d-131">**[DeviceEvents](advanced-hunting-deviceevents-table.md)**</span><span class="sxs-lookup"><span data-stu-id="79f4d-131">**[DeviceEvents](advanced-hunting-deviceevents-table.md)**</span></span> | <span data-ttu-id="79f4d-132">Windows Defender Antivirus 및 익스플로잇 보호와 같은 보안 컨트롤에서 트리거되는 이벤트를 포함한 여러 이벤트 유형</span><span class="sxs-lookup"><span data-stu-id="79f4d-132">Multiple event types, including events triggered by security controls such as Windows Defender Antivirus and exploit protection</span></span> |
| <span data-ttu-id="79f4d-133">**[EmailEvents](advanced-hunting-emailevents-table.md)**</span><span class="sxs-lookup"><span data-stu-id="79f4d-133">**[EmailEvents](advanced-hunting-emailevents-table.md)**</span></span> | <span data-ttu-id="79f4d-134">전자 메일 배달과 차단 이벤트를 포함한 Office 365 전자 메일 이벤트</span><span class="sxs-lookup"><span data-stu-id="79f4d-134">Office 365 email events, including email delivery and blocking events</span></span> |
| <span data-ttu-id="79f4d-135">**[EmailAttachmentInfo](advanced-hunting-emailattachmentinfo-table.md)**</span><span class="sxs-lookup"><span data-stu-id="79f4d-135">**[EmailAttachmentInfo](advanced-hunting-emailattachmentinfo-table.md)**</span></span> | <span data-ttu-id="79f4d-136">Office 365 전자 메일에 첨부된 파일에 대한 정보</span><span class="sxs-lookup"><span data-stu-id="79f4d-136">Information about files attached to Office 365 emails</span></span> |
| <span data-ttu-id="79f4d-137">**[EmailUrlInfo](advanced-hunting-emailurlinfo-table.md)**</span><span class="sxs-lookup"><span data-stu-id="79f4d-137">**[EmailUrlInfo](advanced-hunting-emailurlinfo-table.md)**</span></span> | <span data-ttu-id="79f4d-138">Office 365 전자 메일의 URL에 대한 정보</span><span class="sxs-lookup"><span data-stu-id="79f4d-138">Information about URLs on Office 365 emails</span></span> |
| <span data-ttu-id="79f4d-139">**[DeviceTvmSoftwareInventoryVulnerabilities](advanced-hunting-tvm-softwareinventory-table.md)**</span><span class="sxs-lookup"><span data-stu-id="79f4d-139">**[DeviceTvmSoftwareInventoryVulnerabilities](advanced-hunting-tvm-softwareinventory-table.md)**</span></span> | <span data-ttu-id="79f4d-140">이러한 소프트웨어 제품의 알려진 모든 취약점과 함께 장치의 소프트웨어 인벤터리</span><span class="sxs-lookup"><span data-stu-id="79f4d-140">Inventory of software on devices as well as any known vulnerabilities in these software products</span></span> |
| <span data-ttu-id="79f4d-141">**[DeviceTvmSoftwareVulnerabilitiesKB](advanced-hunting-tvm-softwarevulnerability-table.md)**</span><span class="sxs-lookup"><span data-stu-id="79f4d-141">**[DeviceTvmSoftwareVulnerabilitiesKB](advanced-hunting-tvm-softwarevulnerability-table.md)**</span></span> | <span data-ttu-id="79f4d-142">익스플로잇 코드를 공개적으로 사용할 수 있는지를 포함하여 공개적으로 보고된 취약성에 대한 기술 자료</span><span class="sxs-lookup"><span data-stu-id="79f4d-142">Knowledge base of publicly disclosed vulnerabilities, including whether exploit code is publicly available</span></span> |
| <span data-ttu-id="79f4d-143">**[DeviceTvmSecureConfigurationAssessment](advanced-hunting-tvm-configassessment-table.md)**</span><span class="sxs-lookup"><span data-stu-id="79f4d-143">**[DeviceTvmSecureConfigurationAssessment](advanced-hunting-tvm-configassessment-table.md)**</span></span> | <span data-ttu-id="79f4d-144">장치에서 다양한 보안 구성의 상태를 나타내는 위협 및 취약성 관리 평가 이벤트</span><span class="sxs-lookup"><span data-stu-id="79f4d-144">Threat & Vulnerability Management assessment events, indicating the status of various security configurations on devices</span></span> |
| <span data-ttu-id="79f4d-145">**[DeviceTvmSecureConfigurationAssessmentKB](advanced-hunting-tvm-secureconfigkb-table.md)**</span><span class="sxs-lookup"><span data-stu-id="79f4d-145">**[DeviceTvmSecureConfigurationAssessmentKB](advanced-hunting-tvm-secureconfigkb-table.md)**</span></span> | <span data-ttu-id="79f4d-146">위협 및 취약성 관리에서 장치를 평가하기 위해 사용하는 다양한 보안 구성에 대한 기술 자료. 다양한 표준과 벤치 마크에 대한 매핑 포함</span><span class="sxs-lookup"><span data-stu-id="79f4d-146">Knowledge base of various security configurations used by Threat & Vulnerability Management to assess devices; includes mappings to various standards and benchmarks</span></span>  |

## <a name="related-topics"></a><span data-ttu-id="79f4d-147">관련 항목</span><span class="sxs-lookup"><span data-stu-id="79f4d-147">Related topics</span></span>
- [<span data-ttu-id="79f4d-148">사전 대응식 위협 탐지</span><span class="sxs-lookup"><span data-stu-id="79f4d-148">Proactively hunt for threats</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="79f4d-149">쿼리 언어 배우기</span><span class="sxs-lookup"><span data-stu-id="79f4d-149">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="79f4d-150">공유 쿼리 사용</span><span class="sxs-lookup"><span data-stu-id="79f4d-150">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="79f4d-151">여러 장치 및 전자 메일에서 위협을 탐지</span><span class="sxs-lookup"><span data-stu-id="79f4d-151">Hunt for threats across devices and emails</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="79f4d-152">쿼리 모범 사례 적용</span><span class="sxs-lookup"><span data-stu-id="79f4d-152">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
