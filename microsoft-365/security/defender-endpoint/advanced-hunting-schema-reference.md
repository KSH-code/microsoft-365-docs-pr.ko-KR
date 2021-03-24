---
title: 고급 헌팅 스마 참조
description: 위협 헌팅 쿼리를 실행할 수 있는 데이터를 이해하기 위해 고급 헌팅 스마의 표에 대해 자세히 알아보습니다.
keywords: 고급 헌팅, 위협 헌팅, 사이버 위협 헌팅, mdatp, microsoft defender atp, wdatp 검색, 쿼리, 원격 분석, schema 참조, kusto, 표, 데이터
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
ms.date: 01/14/2020
ms.technology: mde
ms.openlocfilehash: 7516744b72bc86bbf8f776adde690d75f057efd5
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51073151"
---
# <a name="understand-the-advanced-hunting-schema"></a><span data-ttu-id="e93c8-104">고급 헌팅 스키마 이해</span><span class="sxs-lookup"><span data-stu-id="e93c8-104">Understand the advanced hunting schema</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="e93c8-105">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="e93c8-105">**Applies to:**</span></span>
- [<span data-ttu-id="e93c8-106">엔드포인트용 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="e93c8-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)

><span data-ttu-id="e93c8-107">Endpoint용 Defender를 경험하고 싶나요?</span><span class="sxs-lookup"><span data-stu-id="e93c8-107">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="e93c8-108">무료 평가판에 등록합니다.</span><span class="sxs-lookup"><span data-stu-id="e93c8-108">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-advancedhuntingref-abovefoldlink)

[!include[Prerelease information](../../includes/prerelease.md)]

<span data-ttu-id="e93c8-109">고급 [헌팅](advanced-hunting-overview.md) 계획은 이벤트 정보나 장치 및 기타 엔터티에 대한 정보를 제공하는 여러 표로 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="e93c8-109">The [advanced hunting](advanced-hunting-overview.md) schema is made up of multiple tables that provide either event information or information about devices and other entities.</span></span> <span data-ttu-id="e93c8-110">여러 표를 포괄하는 쿼리를 효과적으로 작성하려면 고급 헌팅 스키마에서 표 및 열을 이해해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e93c8-110">To effectively build queries that span multiple tables, you need to understand the tables and the columns in the advanced hunting schema.</span></span>

## <a name="get-schema-information-in-the-security-center"></a><span data-ttu-id="e93c8-111">보안 센터에서 스마마 정보 얻기</span><span class="sxs-lookup"><span data-stu-id="e93c8-111">Get schema information in the security center</span></span>
<span data-ttu-id="e93c8-112">쿼리를 구성하는 동안 기본 제공된 Schema 참조를 사용하여 해당 schema의 각 테이블에 대한 다음 정보를 빠르게 얻을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e93c8-112">While constructing queries, use the built-in schema reference to quickly get the following information about each table in the schema:</span></span>

- <span data-ttu-id="e93c8-113">**테이블 설명**- 테이블에 포함된 데이터 형식 및 해당 데이터의 원본입니다.</span><span class="sxs-lookup"><span data-stu-id="e93c8-113">**Tables description**—type of data contained in the table and the source of that data.</span></span>
- <span data-ttu-id="e93c8-114">**열**- 표의 모든 열입니다.</span><span class="sxs-lookup"><span data-stu-id="e93c8-114">**Columns**—all the columns in the table.</span></span>
- <span data-ttu-id="e93c8-115">**동작 유형**- 테이블에서 지원하는 이벤트 유형을 나타내는 열의 `ActionType` 가능한 값입니다.</span><span class="sxs-lookup"><span data-stu-id="e93c8-115">**Action types**—possible values in the `ActionType` column representing the event types supported by the table.</span></span> <span data-ttu-id="e93c8-116">이벤트 정보가 포함된 테이블에만 제공됩니다.</span><span class="sxs-lookup"><span data-stu-id="e93c8-116">This is provided only for tables that contain event information.</span></span>
- <span data-ttu-id="e93c8-117">**예제 쿼리**- 테이블을 활용하는 방법을 특징으로 하는 쿼리 예제입니다.</span><span class="sxs-lookup"><span data-stu-id="e93c8-117">**Sample query**—example queries that feature how the table can be utilized.</span></span>

### <a name="access-the-schema-reference"></a><span data-ttu-id="e93c8-118">Schema 참조 액세스</span><span class="sxs-lookup"><span data-stu-id="e93c8-118">Access the schema reference</span></span>
<span data-ttu-id="e93c8-119">스마마 참조에 빠르게 액세스하려면  해당 Schema 표현에서 테이블 이름 옆에 있는 참조 보기 작업을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="e93c8-119">To quickly access the schema reference, select the **View reference** action next to the table name in the schema representation.</span></span> <span data-ttu-id="e93c8-120">또한 **Schema 참조를 선택하여** 테이블을 검색할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e93c8-120">You can also select **Schema reference** to search for a table.</span></span>

![포털 내 Schema 참조에 액세스하는 방법을 보여주는 이미지](images/ah-reference.png)

## <a name="learn-the-schema-tables"></a><span data-ttu-id="e93c8-122">Schema 테이블에 대해 자세히 알아보기</span><span class="sxs-lookup"><span data-stu-id="e93c8-122">Learn the schema tables</span></span>

<span data-ttu-id="e93c8-123">다음 참조에는 고급 헌팅 스마의 모든 테이블이 나열됩니다.</span><span class="sxs-lookup"><span data-stu-id="e93c8-123">The following reference lists all the tables in the advanced hunting schema.</span></span> <span data-ttu-id="e93c8-124">각 표 이름은 해당 표의 열 이름을 설명하는 페이지에 연결됩니다.</span><span class="sxs-lookup"><span data-stu-id="e93c8-124">Each table name links to a page describing the column names for that table.</span></span>

<span data-ttu-id="e93c8-125">표 및 열 이름은 Microsoft Defender 보안 센터의 고급 헌팅 화면의 Schema 표현에도 나열됩니다.</span><span class="sxs-lookup"><span data-stu-id="e93c8-125">Table and column names are also listed within the Microsoft Defender Security Center, in the schema representation on the advanced hunting screen.</span></span>

| <span data-ttu-id="e93c8-126">테이블 이름</span><span class="sxs-lookup"><span data-stu-id="e93c8-126">Table name</span></span> | <span data-ttu-id="e93c8-127">설명</span><span class="sxs-lookup"><span data-stu-id="e93c8-127">Description</span></span> |
|------------|-------------|
| <span data-ttu-id="e93c8-128">**[DeviceAlertEvents](advanced-hunting-devicealertevents-table.md)**</span><span class="sxs-lookup"><span data-stu-id="e93c8-128">**[DeviceAlertEvents](advanced-hunting-devicealertevents-table.md)**</span></span> | <span data-ttu-id="e93c8-129">Microsoft Defender 보안 센터에 대한 알림</span><span class="sxs-lookup"><span data-stu-id="e93c8-129">Alerts on Microsoft Defender Security Center</span></span> |
| <span data-ttu-id="e93c8-130">**[DeviceInfo](advanced-hunting-deviceinfo-table.md)**</span><span class="sxs-lookup"><span data-stu-id="e93c8-130">**[DeviceInfo](advanced-hunting-deviceinfo-table.md)**</span></span> | <span data-ttu-id="e93c8-131">OS 정보를 포함한 장치 정보</span><span class="sxs-lookup"><span data-stu-id="e93c8-131">Device information, including OS information</span></span> |
| <span data-ttu-id="e93c8-132">**[DeviceNetworkInfo](advanced-hunting-devicenetworkinfo-table.md)**</span><span class="sxs-lookup"><span data-stu-id="e93c8-132">**[DeviceNetworkInfo](advanced-hunting-devicenetworkinfo-table.md)**</span></span> | <span data-ttu-id="e93c8-133">어댑터, IP 및 MAC 주소, 연결된 네트워크 및 도메인을 비롯한 장치의 네트워크 속성</span><span class="sxs-lookup"><span data-stu-id="e93c8-133">Network properties of devices, including adapters, IP and MAC addresses, as well as connected networks and domains</span></span> |
| <span data-ttu-id="e93c8-134">**[DeviceProcessEvents](advanced-hunting-deviceprocessevents-table.md)**</span><span class="sxs-lookup"><span data-stu-id="e93c8-134">**[DeviceProcessEvents](advanced-hunting-deviceprocessevents-table.md)**</span></span> | <span data-ttu-id="e93c8-135">프로세스 생성 및 관련 이벤트</span><span class="sxs-lookup"><span data-stu-id="e93c8-135">Process creation and related events</span></span> |
| <span data-ttu-id="e93c8-136">**[DeviceNetworkEvents](advanced-hunting-devicenetworkevents-table.md)**</span><span class="sxs-lookup"><span data-stu-id="e93c8-136">**[DeviceNetworkEvents](advanced-hunting-devicenetworkevents-table.md)**</span></span> | <span data-ttu-id="e93c8-137">네트워크 연결 및 관련 이벤트</span><span class="sxs-lookup"><span data-stu-id="e93c8-137">Network connection and related events</span></span> |
| <span data-ttu-id="e93c8-138">**[DeviceFileEvents](advanced-hunting-devicefileevents-table.md)**</span><span class="sxs-lookup"><span data-stu-id="e93c8-138">**[DeviceFileEvents](advanced-hunting-devicefileevents-table.md)**</span></span> | <span data-ttu-id="e93c8-139">파일 생성, 수정 및 기타 파일 시스템 이벤트</span><span class="sxs-lookup"><span data-stu-id="e93c8-139">File creation, modification, and other file system events</span></span> |
| <span data-ttu-id="e93c8-140">**[DeviceRegistryEvents](advanced-hunting-deviceregistryevents-table.md)**</span><span class="sxs-lookup"><span data-stu-id="e93c8-140">**[DeviceRegistryEvents](advanced-hunting-deviceregistryevents-table.md)**</span></span> | <span data-ttu-id="e93c8-141">레지스트리 항목 생성 및 수정</span><span class="sxs-lookup"><span data-stu-id="e93c8-141">Creation and modification of registry entries</span></span> |
| <span data-ttu-id="e93c8-142">**[DeviceLogonEvents](advanced-hunting-devicelogonevents-table.md)**</span><span class="sxs-lookup"><span data-stu-id="e93c8-142">**[DeviceLogonEvents](advanced-hunting-devicelogonevents-table.md)**</span></span> | <span data-ttu-id="e93c8-143">로그인 및 기타 인증 이벤트</span><span class="sxs-lookup"><span data-stu-id="e93c8-143">Sign-ins and other authentication events</span></span> |
| <span data-ttu-id="e93c8-144">**[DeviceImageLoadEvents](advanced-hunting-deviceimageloadevents-table.md)**</span><span class="sxs-lookup"><span data-stu-id="e93c8-144">**[DeviceImageLoadEvents](advanced-hunting-deviceimageloadevents-table.md)**</span></span> | <span data-ttu-id="e93c8-145">DLL 로딩 이벤트</span><span class="sxs-lookup"><span data-stu-id="e93c8-145">DLL loading events</span></span> |
| <span data-ttu-id="e93c8-146">**[DeviceEvents](advanced-hunting-deviceevents-table.md)**</span><span class="sxs-lookup"><span data-stu-id="e93c8-146">**[DeviceEvents](advanced-hunting-deviceevents-table.md)**</span></span> | <span data-ttu-id="e93c8-147">Microsoft Defender 바이러스 백신 및 익스플로잇 보호와 같은 보안 컨트롤에 의해 트리거되는 이벤트를 포함하여 여러 이벤트 유형</span><span class="sxs-lookup"><span data-stu-id="e93c8-147">Multiple event types, including events triggered by security controls such as Microsoft Defender Antivirus and exploit protection</span></span> |
| <span data-ttu-id="e93c8-148">**[DeviceFileCertificateInfo](advanced-hunting-devicefilecertificateinfo-table.md)**</span><span class="sxs-lookup"><span data-stu-id="e93c8-148">**[DeviceFileCertificateInfo](advanced-hunting-devicefilecertificateinfo-table.md)**</span></span> | <span data-ttu-id="e93c8-149">끝점의 인증서 확인 이벤트에서 얻은 서명된 파일의 인증서 정보</span><span class="sxs-lookup"><span data-stu-id="e93c8-149">Certificate information of signed files obtained from certificate verification events on endpoints</span></span> |
| <span data-ttu-id="e93c8-150">**[DeviceTvmSoftwareInventory](advanced-hunting-devicetvmsoftwareinventory-table.md)**</span><span class="sxs-lookup"><span data-stu-id="e93c8-150">**[DeviceTvmSoftwareInventory](advanced-hunting-devicetvmsoftwareinventory-table.md)**</span></span> | <span data-ttu-id="e93c8-151">버전 정보 및 지원 종료 상태를 포함하여 장치에 설치된 소프트웨어 인벤토리</span><span class="sxs-lookup"><span data-stu-id="e93c8-151">Inventory of software installed on devices, including their version information and end-of-support status</span></span> |
| <span data-ttu-id="e93c8-152">**[DeviceTvmSoftwareVulnerabilities](advanced-hunting-devicetvmsoftwarevulnerabilities-table.md)**</span><span class="sxs-lookup"><span data-stu-id="e93c8-152">**[DeviceTvmSoftwareVulnerabilities](advanced-hunting-devicetvmsoftwarevulnerabilities-table.md)**</span></span> | <span data-ttu-id="e93c8-153">장치에서 발견되는 소프트웨어 취약성 및 각 취약점을 해결하기 위한 사용 가능한 보안 업데이트 목록</span><span class="sxs-lookup"><span data-stu-id="e93c8-153">Software vulnerabilities found on devices and the list of available security updates that address each vulnerability</span></span> |
| <span data-ttu-id="e93c8-154">**[DeviceTvmSoftwareVulnerabilitiesKB](advanced-hunting-devicetvmsoftwarevulnerabilitieskb-table.md)**</span><span class="sxs-lookup"><span data-stu-id="e93c8-154">**[DeviceTvmSoftwareVulnerabilitiesKB](advanced-hunting-devicetvmsoftwarevulnerabilitieskb-table.md)**</span></span> | <span data-ttu-id="e93c8-155">익스플로잇 코드를 공개적으로 사용할 수 있는지를 포함하여 공개적으로 보고된 취약성에 대한 기술 자료</span><span class="sxs-lookup"><span data-stu-id="e93c8-155">Knowledge base of publicly disclosed vulnerabilities, including whether exploit code is publicly available</span></span> |
| <span data-ttu-id="e93c8-156">**[DeviceTvmSecureConfigurationAssessment](advanced-hunting-devicetvmsecureconfigurationassessment-table.md)**</span><span class="sxs-lookup"><span data-stu-id="e93c8-156">**[DeviceTvmSecureConfigurationAssessment](advanced-hunting-devicetvmsecureconfigurationassessment-table.md)**</span></span> | <span data-ttu-id="e93c8-157">장치에서 다양한 보안 구성의 상태를 나타내는 위협 및 취약성 관리 평가 이벤트</span><span class="sxs-lookup"><span data-stu-id="e93c8-157">Threat & Vulnerability Management assessment events, indicating the status of various security configurations on devices</span></span> |
| <span data-ttu-id="e93c8-158">**[DeviceTvmSecureConfigurationAssessmentKB](advanced-hunting-devicetvmsecureconfigurationassessmentkb-table.md)**</span><span class="sxs-lookup"><span data-stu-id="e93c8-158">**[DeviceTvmSecureConfigurationAssessmentKB](advanced-hunting-devicetvmsecureconfigurationassessmentkb-table.md)**</span></span> | <span data-ttu-id="e93c8-159">위협 및 취약성 관리에서 장치를 평가하기 위해 사용하는 다양한 보안 구성에 대한 기술 자료. 다양한 표준과 벤치 마크에 대한 매핑 포함</span><span class="sxs-lookup"><span data-stu-id="e93c8-159">Knowledge base of various security configurations used by Threat & Vulnerability Management to assess devices; includes mappings to various standards and benchmarks</span></span> |


## <a name="related-topics"></a><span data-ttu-id="e93c8-160">관련 항목</span><span class="sxs-lookup"><span data-stu-id="e93c8-160">Related topics</span></span>
- [<span data-ttu-id="e93c8-161">고급 헌팅 개요</span><span class="sxs-lookup"><span data-stu-id="e93c8-161">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="e93c8-162">쿼리 언어 배우기</span><span class="sxs-lookup"><span data-stu-id="e93c8-162">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="e93c8-163">쿼리 결과 작업</span><span class="sxs-lookup"><span data-stu-id="e93c8-163">Work with query results</span></span>](advanced-hunting-query-results.md)
- [<span data-ttu-id="e93c8-164">쿼리 모범 사례 적용</span><span class="sxs-lookup"><span data-stu-id="e93c8-164">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
- [<span data-ttu-id="e93c8-165">사용자 지정 검색 개요</span><span class="sxs-lookup"><span data-stu-id="e93c8-165">Custom detections overview</span></span>](overview-custom-detections.md)
- [<span data-ttu-id="e93c8-166">고급 헌팅 데이터 스마마 변경 사항</span><span class="sxs-lookup"><span data-stu-id="e93c8-166">Advanced hunting data schema changes</span></span>](https://techcommunity.microsoft.com/t5/microsoft-defender-atp/advanced-hunting-data-schema-changes/ba-p/1043914)
