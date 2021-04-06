---
title: 도이클란드 Microsoft 클라우드에서 마이그레이션하는 동안의 eDiscovery 경험에 대한 정보
ms.author: andyber
author: andybergen
manager: laurawi
ms.date: 12/01/2020
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
f1.keywords:
- CSH
ms.custom:
- Ent_TLGs
description: '요약: 도이치란드 Microsoft 클라우드에서 마이그레이션하기 위한 eDiscovery 마이그레이션 단계입니다.'
ms.openlocfilehash: 16da6e6d1994ae107b62ff1f915454568a35344d
ms.sourcegitcommit: e0a96e08b7dc29e074065e69a2a86fc3cf0dad01
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/06/2021
ms.locfileid: "51592142"
---
# <a name="information-about-the-ediscovery-experience-during-the-migration-from-microsoft-cloud-deutschland"></a><span data-ttu-id="71094-103">도이클란드 Microsoft 클라우드에서 마이그레이션하는 동안의 eDiscovery 경험에 대한 정보</span><span class="sxs-lookup"><span data-stu-id="71094-103">Information about the eDiscovery experience during the migration from Microsoft Cloud Deutschland</span></span>
<span data-ttu-id="71094-104">다음 섹션에서는 독일 Microsoft 클라우드(도이치란드 Microsoft 클라우드)에서 새 독일 데이터 센터 지역의 Office 365 서비스로 전환할 때의 eDiscovery 경험에 대한 추가 정보를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="71094-104">The following sections provide additional information about the eDiscovery experience when moving from Microsoft Cloud Germany (Microsoft Cloud Deutschland) to Office 365 services in the new German datacenter region.</span></span>

## <a name="ediscovery-administration-until-phase-4"></a><span data-ttu-id="71094-105">4단계까지의 eDiscovery 관리</span><span class="sxs-lookup"><span data-stu-id="71094-105">eDiscovery administration until phase 4</span></span>
<span data-ttu-id="71094-106">4단계까지는 보안 및 준수 센터를 완전히 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="71094-106">Until phase 4, the Security and Compliance Center will be fully available.</span></span> <span data-ttu-id="71094-107">모든 콘텐츠는 여전히 Microsoft 클라우드 독일에 남아 있으며 Microsoft 클라우드 독일 보안 및 규정 준수 센터( 에서 관리할 수 https://protection.office.de/) 있습니다.</span><span class="sxs-lookup"><span data-stu-id="71094-107">All content still remains in the Microsoft Cloud Germany and is manageable by the Microsoft Cloud Germany Security and Compliance Center (https://protection.office.de/).</span></span>

## <a name="ediscovery-experience-between-phase-4-until-the-the-end-of-phase-9"></a><span data-ttu-id="71094-108">4단계에서 9단계가 끝날 때까지의 eDiscovery 환경</span><span class="sxs-lookup"><span data-stu-id="71094-108">eDiscovery experience between phase 4 until the the end of phase 9</span></span>
<span data-ttu-id="71094-109">4단계의 시작부터 9단계까지 eDiscovery 검색은 실패하거나 마이그레이션된 SharePoint Online, 비즈니스용 OneDrive 및 Exchange Online 위치에 대해 0개 결과를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="71094-109">From the beginning of phase 4 until phase 9 is completed, eDiscovery searches will fail or return 0 results for SharePoint Online, OneDrive for Business, and Exchange Online locations that have been migrated.</span></span>

> [!NOTE]
> <span data-ttu-id="71094-110">마이그레이션 중에 고객은 콘텐츠 검색을 포함하여 보안 및 준수 센터에서 사례, 보류& 검색 [및 내보내기 &](https://docs.microsoft.com/microsoft-365/compliance/manage-legal-investigations)수 [있습니다.](https://docs.microsoft.com/microsoft-365/compliance/search-for-content)</span><span class="sxs-lookup"><span data-stu-id="71094-110">During migration, customers can continue to create cases, holds, searches, and exports in the [Security & Compliance Center](https://docs.microsoft.com/microsoft-365/compliance/manage-legal-investigations), including [Content Search](https://docs.microsoft.com/microsoft-365/compliance/search-for-content).</span></span> <span data-ttu-id="71094-111">그러나 마이그레이션된 SharePoint Online, 비즈니스용 OneDrive 및 Exchange Online 위치를 검색하면 0개 결과가 반환되거나 오류가 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="71094-111">However, searches against SharePoint Online, OneDrive for Business, and Exchange Online locations that have been migrated will either return 0 results or produce an error.</span></span>

<span data-ttu-id="71094-112">마이그레이션 중 검색에서 결과 0개 또는 오류가 반환될 경우 SharePoint Online에 대해 다음 작업을 수행하세요.</span><span class="sxs-lookup"><span data-stu-id="71094-112">In the event that a search returns zero results or an error during migration, please take the following action for SharePoint Online:</span></span> 
- <span data-ttu-id="71094-113">OneDrive 또는 SharePoint에서 파일 및 폴더 다운로드의 지침에 따라 SharePoint Online 또는 비즈니스용 [OneDrive](https://support.office.com/article/download-files-and-folders-from-onedrive-or-sharepoint-5c7397b7-19c7-4893-84fe-d02e8fa5df05)사이트에서 직접 사이트를 다운로드합니다.</span><span class="sxs-lookup"><span data-stu-id="71094-113">Download sites directly from the SharePoint Online or OneDrive for Business site by following the instructions in [Download files and folders from OneDrive or SharePoint](https://support.office.com/article/download-files-and-folders-from-onedrive-or-sharepoint-5c7397b7-19c7-4893-84fe-d02e8fa5df05).</span></span> <span data-ttu-id="71094-114">이 방법을 사용하려면 사이트에 대한 SharePoint Online 관리자 권한 또는 읽기 전용 권한이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="71094-114">This method will require SharePoint Online administrator permissions or read-only permissions on the site.</span></span>
- <span data-ttu-id="71094-115">[OneDrive 또는 SharePoint에서](https://support.office.com/article/download-files-and-folders-from-onedrive-or-sharepoint-5c7397b7-19c7-4893-84fe-d02e8fa5df05)파일 및 폴더 다운로드에 설명된 제한을 초과하는 경우 고객은 [컴퓨터와 SharePoint](https://support.office.com/article/sync-sharepoint-files-with-the-new-onedrive-sync-app-6de9ede8-5b6e-4503-80b2-6190f3354a88)및 Teams 파일 동기화의 지침에 따라 비즈니스용 OneDrive 동기화 클라이언트를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="71094-115">If limits are exceeded, as explained in [Download files and folders from OneDrive or SharePoint](https://support.office.com/article/download-files-and-folders-from-onedrive-or-sharepoint-5c7397b7-19c7-4893-84fe-d02e8fa5df05), customers can use the OneDrive for Business sync client by following the guidance in [Sync SharePoint and Teams files with your computer](https://support.office.com/article/sync-sharepoint-files-with-the-new-onedrive-sync-app-6de9ede8-5b6e-4503-80b2-6190f3354a88).</span></span>

- <span data-ttu-id="71094-116">자세한 내용은 에서 [In-Place eDiscovery in Exchange Server.](https://docs.microsoft.com/Exchange/policy-and-compliance/ediscovery/ediscovery)</span><span class="sxs-lookup"><span data-stu-id="71094-116">For more information, see  [In-Place eDiscovery in Exchange Server](https://docs.microsoft.com/Exchange/policy-and-compliance/ediscovery/ediscovery).</span></span>


## <a name="ediscovery-administration-after-phase-9"></a><span data-ttu-id="71094-117">9단계 이후의 eDiscovery 관리</span><span class="sxs-lookup"><span data-stu-id="71094-117">eDiscovery administration after phase 9</span></span>

<span data-ttu-id="71094-118">**다음에 적용됩니다.** eDiscovery를 사용하는 모든 고객</span><span class="sxs-lookup"><span data-stu-id="71094-118">**Applies to:** All customers using eDiscovery</span></span>

<span data-ttu-id="71094-119">9단계에서 새 독일 데이터 센터 지역으로 이동하는 최종 단계가 완료됩니다.</span><span class="sxs-lookup"><span data-stu-id="71094-119">In phase 9, the final steps for moving to the new German datacenter region will be completed.</span></span> <span data-ttu-id="71094-120">이 단계에서는 나머지 모든 서비스 구성 요소가 마이그레이션됩니다.</span><span class="sxs-lookup"><span data-stu-id="71094-120">In this phase, all remaining service components will be migrated.</span></span> <span data-ttu-id="71094-121">9단계 이후에는 Microsoft 클라우드 독일(protection.office.de)의 보안 및 준수 센터 사용이 더 이상 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="71094-121">After phase 9, using the Security and Compliance Center in Microsoft Cloud Germany (protection.office.de) is no longer supported.</span></span> <span data-ttu-id="71094-122">대신 새 [보안](https://security.microsoft.com/) 센터 또는 [규정 준수 센터를 사용하세요.](https://compliance.microsoft.com/)</span><span class="sxs-lookup"><span data-stu-id="71094-122">Please use the new [Security Center](https://security.microsoft.com/) or [Compliance Center](https://compliance.microsoft.com/) instead.</span></span> <span data-ttu-id="71094-123">모든 데이터가 새 관리 포털로 마이그레이션됩니다.</span><span class="sxs-lookup"><span data-stu-id="71094-123">All data have been migrated to the new admin portals.</span></span> 

| <span data-ttu-id="71094-124">Step(s)</span><span class="sxs-lookup"><span data-stu-id="71094-124">Step(s)</span></span> | <span data-ttu-id="71094-125">설명</span><span class="sxs-lookup"><span data-stu-id="71094-125">Description</span></span> | <span data-ttu-id="71094-126">영향</span><span class="sxs-lookup"><span data-stu-id="71094-126">Impact</span></span> |
|:-------|:-------|:-------|
|  <span data-ttu-id="71094-127">모든 SharePoint Online, 비즈니스용 OneDrive 및 Exchange Online 위치가 SCC(보안 및 준수 센터)와 함께 마이그레이션됩니다.</span><span class="sxs-lookup"><span data-stu-id="71094-127">All SharePoint Online, OneDrive for Business, and Exchange Online locations have been migrated along with the Security and Compliance Center (SCC).</span></span> | <span data-ttu-id="71094-128">모든 eDiscovery 활동은 전 세계 테넌트에서 실행해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="71094-128">All eDiscovery activity should be run from the worldwide tenant.</span></span> <span data-ttu-id="71094-129">이제 검색이 100% 성공합니다.</span><span class="sxs-lookup"><span data-stu-id="71094-129">Searches will now be 100% successful.</span></span> <span data-ttu-id="71094-130">오류 또는 오류는 정상적인 지원 채널을 따라야 합니다.</span><span class="sxs-lookup"><span data-stu-id="71094-130">Any failures or errors should follow normal support channels.</span></span> | <span data-ttu-id="71094-131">없음</span><span class="sxs-lookup"><span data-stu-id="71094-131">None</span></span> |
||||

### <a name="ediscovery-retention-policy"></a><span data-ttu-id="71094-132">eDiscovery 보존 정책</span><span class="sxs-lookup"><span data-stu-id="71094-132">eDiscovery Retention Policy</span></span>
<span data-ttu-id="71094-133">**다음에 적용됩니다.**  마이그레이션 전 단계의 일부로 보존 정책을 적용한 모든 고객</span><span class="sxs-lookup"><span data-stu-id="71094-133">**Applies to:**  All customers who applied a retention policy as part of the pre-migration steps</span></span>

| <span data-ttu-id="71094-134">Step(s)</span><span class="sxs-lookup"><span data-stu-id="71094-134">Step(s)</span></span> | <span data-ttu-id="71094-135">설명</span><span class="sxs-lookup"><span data-stu-id="71094-135">Description</span></span> | <span data-ttu-id="71094-136">영향</span><span class="sxs-lookup"><span data-stu-id="71094-136">Impact</span></span> |
|:-------|:-------|:-------|
| <span data-ttu-id="71094-137">마이그레이션 전 단계 중에 만들어진 조직 전체 보존 정책 제거</span><span class="sxs-lookup"><span data-stu-id="71094-137">Remove organization-wide retention policies that were created during pre-migration steps</span></span> | <span data-ttu-id="71094-138">고객은 마이그레이션 전 작업 중에 만들어진 조직 전체 보존 정책을 제거할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="71094-138">Customers can remove the organization-wide retention policies that were created during the customers' pre-migration work.</span></span> | <span data-ttu-id="71094-139">없음</span><span class="sxs-lookup"><span data-stu-id="71094-139">None</span></span> |
||||
