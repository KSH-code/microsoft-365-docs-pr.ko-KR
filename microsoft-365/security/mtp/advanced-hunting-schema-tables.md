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
ms.openlocfilehash: 1803445dfd9b46fce23b0dcc9585ea543f1b0347
ms.sourcegitcommit: 0c9c28a87201c7470716216d99175356fb3d1a47
ms.translationtype: MT + HT Review
ms.contentlocale: ko-KR
ms.lasthandoff: 12/09/2019
ms.locfileid: "39911411"
---
# <a name="understand-the-advanced-hunting-schema"></a><span data-ttu-id="c3579-104">고급 헌팅 스키마 이해</span><span class="sxs-lookup"><span data-stu-id="c3579-104">Understand the advanced hunting schema</span></span>

<span data-ttu-id="c3579-105">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="c3579-105">**Applies to:**</span></span>
- <span data-ttu-id="c3579-106">Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="c3579-106">Microsoft Threat Protection</span></span>

[!include[Prerelease information](prerelease.md)]

<span data-ttu-id="c3579-107">[고급 헌팅](advanced-hunting-overview.md) 스키마는 이벤트 정보나 컴퓨터 및 엔터티에 대한 정보를 제공하는 여러 표로 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="c3579-107">The [advanced hunting](advanced-hunting-overview.md) schema is made up of multiple tables that provide either event information or information about machines and entities.</span></span> <span data-ttu-id="c3579-108">여러 표를 포괄하는 쿼리를 효과적으로 작성하려면 고급 헌팅 스키마에서 표 및 열을 이해해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c3579-108">To effectively build queries that span multiple tables, you need to understand the tables and the columns in the advanced hunting schema.</span></span>

## <a name="schema-tables"></a><span data-ttu-id="c3579-109">스키마 표</span><span class="sxs-lookup"><span data-stu-id="c3579-109">Schema tables</span></span>

<span data-ttu-id="c3579-110">다음 참조는 스키마에서 모든 표를 나열합니다.</span><span class="sxs-lookup"><span data-stu-id="c3579-110">The following example lists all the resource tables in the active project.</span></span> <span data-ttu-id="c3579-111">각 표 이름은 해당 표의 열 이름을 설명하는 페이지에 연결됩니다.</span><span class="sxs-lookup"><span data-stu-id="c3579-111">Each table name links to a page describing the column names for that table.</span></span> <span data-ttu-id="c3579-112">표 및 열 이름은 고급 헌팅 화면에서 스키마 표현의 일부로 보안 센터에도 나열됩니다.</span><span class="sxs-lookup"><span data-stu-id="c3579-112">Table and column names are also listed in the security center as part of the the schema representation on the advanced hunting screen.</span></span>

| <span data-ttu-id="c3579-113">테이블 이름</span><span class="sxs-lookup"><span data-stu-id="c3579-113">Table name</span></span> | <span data-ttu-id="c3579-114">설명</span><span class="sxs-lookup"><span data-stu-id="c3579-114">Description</span></span> |
|------------|-------------|
| <span data-ttu-id="c3579-115">**[MachineInfo](advanced-hunting-machineinfo-table.md)**</span><span class="sxs-lookup"><span data-stu-id="c3579-115">**[MachineInfo](advanced-hunting-machineinfo-table.md)**</span></span> | <span data-ttu-id="c3579-116">컴퓨터 정보(OS 정보 포함)</span><span class="sxs-lookup"><span data-stu-id="c3579-116">Machine information, including OS information</span></span> |
| <span data-ttu-id="c3579-117">**[MachineNetworkInfo](advanced-hunting-machinenetworkinfo-table.md)**</span><span class="sxs-lookup"><span data-stu-id="c3579-117">**[MachineNetworkInfo](advanced-hunting-machinenetworkinfo-table.md)**</span></span> | <span data-ttu-id="c3579-118">연결된 네트워크 및 도메인뿐만 아니라 어댑터, IP 및 MAC 주소를 비롯한 컴퓨터의 네트워크 속성</span><span class="sxs-lookup"><span data-stu-id="c3579-118">Network properties of machines, including adapters, IP and MAC addresses, as well as connected networks and domains</span></span> |
| <span data-ttu-id="c3579-119">**[ProcessCreationEvents](advanced-hunting-processcreationevents-table.md)**</span><span class="sxs-lookup"><span data-stu-id="c3579-119">**[ProcessCreationEvents](advanced-hunting-processcreationevents-table.md)**</span></span> | <span data-ttu-id="c3579-120">프로세스 생성 및 관련 이벤트</span><span class="sxs-lookup"><span data-stu-id="c3579-120">Process creation and related events</span></span> |
| <span data-ttu-id="c3579-121">**[NetworkCommunicationEvents](advanced-hunting-networkcommunicationevents-table.md)**</span><span class="sxs-lookup"><span data-stu-id="c3579-121">**[NetworkCommunicationEvents](advanced-hunting-networkcommunicationevents-table.md)**</span></span> | <span data-ttu-id="c3579-122">네트워크 연결 및 관련 이벤트</span><span class="sxs-lookup"><span data-stu-id="c3579-122">Network connection and related events</span></span> |
| <span data-ttu-id="c3579-123">**[FileCreationEvents](advanced-hunting-filecreationevents-table.md)**</span><span class="sxs-lookup"><span data-stu-id="c3579-123">**[FileCreationEvents](advanced-hunting-filecreationevents-table.md)**</span></span> | <span data-ttu-id="c3579-124">파일 생성, 수정 및 기타 파일 시스템 이벤트</span><span class="sxs-lookup"><span data-stu-id="c3579-124">File creation, modification, and other file system events</span></span> |
| <span data-ttu-id="c3579-125">**[RegistryEvents](advanced-hunting-registryevents-table.md)**</span><span class="sxs-lookup"><span data-stu-id="c3579-125">**[RegistryEvents](advanced-hunting-registryevents-table.md)**</span></span> | <span data-ttu-id="c3579-126">레지스트리 항목 생성 및 수정</span><span class="sxs-lookup"><span data-stu-id="c3579-126">Creation and modification of registry entries</span></span> |
| <span data-ttu-id="c3579-127">**[LogonEvents](advanced-hunting-logonevents-table.md)**</span><span class="sxs-lookup"><span data-stu-id="c3579-127">**[LogonEvents](advanced-hunting-logonevents-table.md)**</span></span> | <span data-ttu-id="c3579-128">로그인 및 기타 인증 이벤트</span><span class="sxs-lookup"><span data-stu-id="c3579-128">Sign-ins and other authentication events</span></span> |
| <span data-ttu-id="c3579-129">**[ImageLoadEvents](advanced-hunting-imageloadevents-table.md)**</span><span class="sxs-lookup"><span data-stu-id="c3579-129">**[ImageLoadEvents](advanced-hunting-imageloadevents-table.md)**</span></span> | <span data-ttu-id="c3579-130">DLL 로딩 이벤트</span><span class="sxs-lookup"><span data-stu-id="c3579-130">DLL loading events</span></span> |
| <span data-ttu-id="c3579-131">**[MiscEvents](advanced-hunting-miscevents-table.md)**</span><span class="sxs-lookup"><span data-stu-id="c3579-131">**[MiscEvents](advanced-hunting-miscevents-table.md)**</span></span> | <span data-ttu-id="c3579-132">Windows Defender Antivirus 및 익스플로잇 보호와 같은 보안 컨트롤에서 트리거되는 이벤트를 포함한 여러 이벤트 유형</span><span class="sxs-lookup"><span data-stu-id="c3579-132">Multiple event types, including events triggered by security controls such as Windows Defender Antivirus and exploit protection</span></span> |
| <span data-ttu-id="c3579-133">**[EmailEvents](advanced-hunting-emailevents-table.md)**</span><span class="sxs-lookup"><span data-stu-id="c3579-133">**[EmailEvents](advanced-hunting-emailevents-table.md)**</span></span> | <span data-ttu-id="c3579-134">전자 메일 배달과 차단 이벤트를 포함한 Office 365 전자 메일 이벤트</span><span class="sxs-lookup"><span data-stu-id="c3579-134">Office 365 email events, including email delivery and blocking events</span></span> |
| <span data-ttu-id="c3579-135">**[EmailAttachmentInfo](advanced-hunting-emailattachmentinfo-table.md)**</span><span class="sxs-lookup"><span data-stu-id="c3579-135">**[EmailAttachmentInfo](advanced-hunting-emailattachmentinfo-table.md)**</span></span> | <span data-ttu-id="c3579-136">Office 365 전자 메일에 첨부된 파일에 대한 정보</span><span class="sxs-lookup"><span data-stu-id="c3579-136">Information about files attached to Office 365 emails</span></span> |
| <span data-ttu-id="c3579-137">**[EmailUrlInfo](advanced-hunting-emailurlinfo-table.md)**</span><span class="sxs-lookup"><span data-stu-id="c3579-137">**[EmailUrlInfo](advanced-hunting-emailurlinfo-table.md)**</span></span> | <span data-ttu-id="c3579-138">Office 365 전자 메일의 URL에 대한 정보</span><span class="sxs-lookup"><span data-stu-id="c3579-138">Information about URLs on Office 365 emails</span></span> |
| <span data-ttu-id="c3579-139">**[DeviceTvmSoftwareInventoryVulnerabilities](advanced-hunting-tvm-softwareinventory-table.md)**</span><span class="sxs-lookup"><span data-stu-id="c3579-139">**[DeviceTvmSoftwareInventoryVulnerabilities](advanced-hunting-tvm-softwareinventory-table.md)**</span></span> | <span data-ttu-id="c3579-140">이러한 소프트웨어 제품의 알려진 모든 취약점과 함께 장치의 소프트웨어 인벤터리</span><span class="sxs-lookup"><span data-stu-id="c3579-140">Inventory of software on devices as well as any known vulnerabilities in these software products</span></span> |
| <span data-ttu-id="c3579-141">**[DeviceTvmSoftwareVulnerabilitiesKB](advanced-hunting-tvm-softwarevulnerability-table.md)**</span><span class="sxs-lookup"><span data-stu-id="c3579-141">**[DeviceTvmSoftwareVulnerabilitiesKB](advanced-hunting-tvm-softwarevulnerability-table.md)**</span></span> | <span data-ttu-id="c3579-142">익스플로잇 코드를 공개적으로 사용할 수 있는지를 포함하여 공개적으로 보고된 취약성에 대한 기술 자료</span><span class="sxs-lookup"><span data-stu-id="c3579-142">Knowledge base of publicly disclosed vulnerabilities, including whether exploit code is publicly available</span></span> |
| <span data-ttu-id="c3579-143">**[DeviceTvmSecureConfigurationAssessment](advanced-hunting-tvm-configassessment-table.md)**</span><span class="sxs-lookup"><span data-stu-id="c3579-143">**[DeviceTvmSecureConfigurationAssessment](advanced-hunting-tvm-configassessment-table.md)**</span></span> | <span data-ttu-id="c3579-144">장치에서 다양한 보안 구성의 상태를 나타내는 위협 및 취약성 관리 평가 이벤트</span><span class="sxs-lookup"><span data-stu-id="c3579-144">Threat & Vulnerability Management assessment events, indicating the status of various security configurations on devices</span></span> |
| <span data-ttu-id="c3579-145">**[DeviceTvmSecureConfigurationAssessmentKB](advanced-hunting-tvm-secureconfigkb-table.md)**</span><span class="sxs-lookup"><span data-stu-id="c3579-145">**[DeviceTvmSecureConfigurationAssessmentKB](advanced-hunting-tvm-secureconfigkb-table.md)**</span></span> | <span data-ttu-id="c3579-146">위협 및 취약성 관리에서 장치를 평가하기 위해 사용하는 다양한 보안 구성에 대한 기술 자료. 다양한 표준과 벤치 마크에 대한 매핑 포함</span><span class="sxs-lookup"><span data-stu-id="c3579-146">Knowledge base of various security configurations used by Threat & Vulnerability Management to assess devices; includes mappings to various standards and benchmarks</span></span>  |

## <a name="related-topics"></a><span data-ttu-id="c3579-147">관련 항목</span><span class="sxs-lookup"><span data-stu-id="c3579-147">Related topics</span></span>
- [<span data-ttu-id="c3579-148">사전 대응식 위협 탐지</span><span class="sxs-lookup"><span data-stu-id="c3579-148">Proactively hunt for threats</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="c3579-149">쿼리 언어 배우기</span><span class="sxs-lookup"><span data-stu-id="c3579-149">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="c3579-150">공유 쿼리 사용</span><span class="sxs-lookup"><span data-stu-id="c3579-150">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="c3579-151">여러 장치 및 전자 메일에서 위협을 탐지</span><span class="sxs-lookup"><span data-stu-id="c3579-151">Hunt for threats across devices and emails</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="c3579-152">쿼리 모범 사례 적용</span><span class="sxs-lookup"><span data-stu-id="c3579-152">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
