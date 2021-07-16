---
title: Microsoft 365 검색에서 테넌트 격리
ms.author: robmazz
author: robmazz
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- Strat_O365_IP
- M365-security-compliance
f1.keywords:
- NOCSH
description: 이 문서에서는 테넌트 분리가 검색에서 테넌트 데이터를 분리하는 방법에 대한 Microsoft 365 있습니다.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 3416afdeceaa7000b516ec89b4a2a1e59d8708d0
ms.sourcegitcommit: 27addd4dac07926528b788215d2dcd0e46301eb1
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/16/2021
ms.locfileid: "53464115"
---
# <a name="tenant-isolation-in-microsoft-365-search"></a><span data-ttu-id="8cb6e-103">Microsoft 365 검색에서 테넌트 격리</span><span class="sxs-lookup"><span data-stu-id="8cb6e-103">Tenant Isolation in Microsoft 365 Search</span></span>

<span data-ttu-id="8cb6e-104">SharePoint 온라인 검색은 공유 데이터 구조의 효율성과 테넌트 간의 정보 누출을 방지하는 테넌트 분리 모델을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="8cb6e-104">SharePoint Online search uses a tenant separation model that balances the efficiency of shared data structures with protection against information leaking between tenants.</span></span> <span data-ttu-id="8cb6e-105">이 모델을 사용하여 검색 기능은 다음을 방지합니다.</span><span class="sxs-lookup"><span data-stu-id="8cb6e-105">With this model, we prevent the Search features from:</span></span>

- <span data-ttu-id="8cb6e-106">다른 테넌트의 문서가 포함된 쿼리 결과 반환</span><span class="sxs-lookup"><span data-stu-id="8cb6e-106">Returning query results that contain documents from other tenants</span></span>
- <span data-ttu-id="8cb6e-107">숙련된 사용자가 다른 테넌트에 대한 정보를 유추할 수 있는 충분한 정보를 쿼리 결과에 노출</span><span class="sxs-lookup"><span data-stu-id="8cb6e-107">Exposing sufficient information in query results that a skilled user could infer information about other tenants</span></span>
- <span data-ttu-id="8cb6e-108">다른 테넌트의 Schema 또는 설정 표시</span><span class="sxs-lookup"><span data-stu-id="8cb6e-108">Showing schema or settings from another tenant</span></span>
- <span data-ttu-id="8cb6e-109">테넌트 간 분석 처리 정보 혼합 또는 잘못된 테넌트의 결과 저장</span><span class="sxs-lookup"><span data-stu-id="8cb6e-109">Mixing analytics processing information between tenants or store results in the wrong tenant</span></span>
- <span data-ttu-id="8cb6e-110">다른 테넌트의 사전 항목 사용</span><span class="sxs-lookup"><span data-stu-id="8cb6e-110">Using dictionary entries from another tenant</span></span>

<span data-ttu-id="8cb6e-111">각 테넌트 데이터 형식에 대해 코드에서 하나 이상의 보호 계층을 사용하여 실수로 정보가 누출되는 것을 방지합니다.</span><span class="sxs-lookup"><span data-stu-id="8cb6e-111">For each type of tenant data, we use one or more layers of protection in the code to prevent accidental leaking of information.</span></span> <span data-ttu-id="8cb6e-112">가장 중요한 데이터는 단일 결함으로 인해 정보 누출 또는 실제 정보 누출이 발생하지 않는 가장 중요한 보호 계층이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8cb6e-112">The most critical data has the most layers of protection to make sure that a single defect doesn't result in actual or perceived information leakage.</span></span>

## <a name="tenant-separation-for-the-search-index"></a><span data-ttu-id="8cb6e-113">검색 인덱스에 대한 테넌트 분리</span><span class="sxs-lookup"><span data-stu-id="8cb6e-113">Tenant Separation for the Search Index</span></span>

<span data-ttu-id="8cb6e-114">검색 인덱스는 인덱스 구성 요소를 호스팅하는 서버의 디스크에 저장되고 테넌트는 인덱스 파일을 공유합니다.</span><span class="sxs-lookup"><span data-stu-id="8cb6e-114">The search index is stored on disk in the servers hosting the index components and the tenants share the index files.</span></span> <span data-ttu-id="8cb6e-115">테넌트의 인덱싱된 문서는 해당 테넌트에 대한 쿼리에만 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="8cb6e-115">A tenant's indexed documents are visible only for queries for that tenant.</span></span> <span data-ttu-id="8cb6e-116">세 가지 독립적인 메커니즘은 정보 누출을 방지합니다.</span><span class="sxs-lookup"><span data-stu-id="8cb6e-116">Three independent mechanisms prevent information leakage:</span></span>

- <span data-ttu-id="8cb6e-117">테넌트 ID 필터링</span><span class="sxs-lookup"><span data-stu-id="8cb6e-117">Tenant ID filtering</span></span>
- <span data-ttu-id="8cb6e-118">테넌트 ID 용어 prefixing</span><span class="sxs-lookup"><span data-stu-id="8cb6e-118">Tenant ID term prefixing</span></span>
- <span data-ttu-id="8cb6e-119">ACL 검사</span><span class="sxs-lookup"><span data-stu-id="8cb6e-119">ACL checks</span></span>

<span data-ttu-id="8cb6e-120">세 가지 메커니즘 모두 검색이 잘못된 테넌트에 문서를 반환하기 위해 실패해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8cb6e-120">All three mechanisms would have to fail for Search to return documents to the wrong tenant.</span></span>

## <a name="tenant-id-filtering-and-tenant-id-term-prefixing"></a><span data-ttu-id="8cb6e-121">테넌트 ID 필터링 및 테넌트 ID 용어 Prefixing</span><span class="sxs-lookup"><span data-stu-id="8cb6e-121">Tenant ID Filtering and Tenant ID Term Prefixing</span></span>

<span data-ttu-id="8cb6e-122">검색에는 테넌트 ID가 있는 전체 텍스트 인덱스에서 인덱싱된 모든 용어가 사전으로 추가됩니다.</span><span class="sxs-lookup"><span data-stu-id="8cb6e-122">Search prefixes every term that is indexed in the full-text index with the tenant ID.</span></span> <span data-ttu-id="8cb6e-123">예를 들어 ID가 "*123*"인 테넌트에 대해 *"foo"라는* 용어가 인덱싱된 경우 전체 텍스트 인덱스의 항목은 "*123foo입니다.*"</span><span class="sxs-lookup"><span data-stu-id="8cb6e-123">For example, when the term "*foo*" is indexed for a tenant with an ID of "*123*", the entry in the full-text index is "*123foo.*"</span></span>

<span data-ttu-id="8cb6e-124">모든 쿼리는 테넌트 ID 필터링이라는 프로세스를 사용하여 테넌트 ID를 포함하기 위해 변환됩니다.</span><span class="sxs-lookup"><span data-stu-id="8cb6e-124">Every query is converted to include the tenant ID using a process called tenant ID filtering.</span></span> <span data-ttu-id="8cb6e-125">예를 들어 쿼리 "*foo*"는 "<*guid>.* *foo* AND *tenantID*:<*guid>"입니다.* 여기서 <*guid*> 쿼리를 수행하는 테넌트입니다.</span><span class="sxs-lookup"><span data-stu-id="8cb6e-125">For example, the query "*foo*" is converted to "<*guid*>.*foo* AND *tenantID*:<*guid*>", where <*guid*> represents the tenant performing the query.</span></span> <span data-ttu-id="8cb6e-126">이 쿼리 변환은 각 인덱스 노드 내에서 발생하며 쿼리와 콘텐츠 처리 모두 해당 노드에 영향을 줄 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="8cb6e-126">This query conversion occurs within each index node and neither query nor content processing can influence it.</span></span> <span data-ttu-id="8cb6e-127">테넌트 ID는 모든 쿼리에 추가되는 것이기 때문에 한 테넌트에서 최상의 일치 순위를 보고 다른 테넌트의 용어 빈도를 유추할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="8cb6e-127">Because the tenant ID is added to every query, the frequency of a term in other tenants can't be inferred by looking at best match ranking in one tenant.</span></span>

<span data-ttu-id="8cb6e-128">테넌트 ID 용어의 prefixing은 전체 텍스트 인덱스에서만 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="8cb6e-128">Tenant ID term prefixing occurs only in the full-text index.</span></span> <span data-ttu-id="8cb6e-129">"*title:foo*"와 같은 필드가 있는 검색은 용어에 테넌트 ID가 미리 추가되지 않은 가상 검색 인덱스로 이동됩니다.</span><span class="sxs-lookup"><span data-stu-id="8cb6e-129">Fielded searches, such as "*title:foo*", go to a synthetic search index where terms aren't prefixed by tenant ID.</span></span> <span data-ttu-id="8cb6e-130">대신 필드 검색에는 필드 이름이 사전으로 추가됩니다.</span><span class="sxs-lookup"><span data-stu-id="8cb6e-130">Instead, fielded searches are prefixed with the field name.</span></span> <span data-ttu-id="8cb6e-131">예를 들어 쿼리 "*title:foo*"는 "*fields.title:foo AND fields.tenantID*:<*guid>."*</span><span class="sxs-lookup"><span data-stu-id="8cb6e-131">For example, the query "*title:foo*" is converted to "*fields.title:foo AND fields.tenantID*:<*guid*>."</span></span> <span data-ttu-id="8cb6e-132">용어의 빈도는 가상 검색 인덱스의 적중 순위에 영향을 주지 않습니다. 따라서 용어 prefixing으로 테넌트 구분이 필요하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="8cb6e-132">Because the frequency of a term doesn't influence ranking of hits in the synthetic search index, there's no need for tenant separation by term prefixing.</span></span> <span data-ttu-id="8cb6e-133">"*title:foo*"와 같은 필드 검색의 경우 테넌트 콘텐츠 분리는 쿼리 변환별 테넌트 ID 필터링에 따라 달라 집니다.</span><span class="sxs-lookup"><span data-stu-id="8cb6e-133">For a fielded search like "*title:foo*", tenant content separation depends on tenant ID filtering by query conversion.</span></span>

## <a name="document-access-control-list-checks"></a><span data-ttu-id="8cb6e-134">문서 액세스 제어 목록 검사</span><span class="sxs-lookup"><span data-stu-id="8cb6e-134">Document Access Control List Checks</span></span>

<span data-ttu-id="8cb6e-135">검색은 검색 인덱스에 저장된 ACL을 통해 문서에 대한 액세스를 제어합니다.</span><span class="sxs-lookup"><span data-stu-id="8cb6e-135">Search controls access to documents through ACLs that are saved in the search index.</span></span> <span data-ttu-id="8cb6e-136">모든 항목은 특수 ACL 필드의 용어 집합으로 인덱싱됩니다.</span><span class="sxs-lookup"><span data-stu-id="8cb6e-136">Every item is indexed with a set of terms in a special ACL field.</span></span> <span data-ttu-id="8cb6e-137">ACL 필드에는 문서를 볼 수 있는 그룹 또는 사용자당 하나의 용어가 들어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8cb6e-137">The ACL field contains one term per group or user that can view the document.</span></span> <span data-ttu-id="8cb6e-138">모든 쿼리에는 인증된 사용자가 속한 각 그룹에 대해 하나씩 ACE(액세스 제어 항목) 용어 목록이 추가됩니다.</span><span class="sxs-lookup"><span data-stu-id="8cb6e-138">Every query is augmented with a list of access control entry (ACE) terms, one for each group to which the authenticated user belongs.</span></span>

<span data-ttu-id="8cb6e-139">예를 들어 "<*guid>.* *foo AND tenantID*:<*guid>"* "<*guid>.* *foo AND tenantID*:<*guid* >  *AND* (*docACL:* < *ace1* OR >  *docACL*:<*ace2* OR >  *docACL*:<*ace3* >  *...*)"</span><span class="sxs-lookup"><span data-stu-id="8cb6e-139">For example, a query like "<*guid*>.*foo AND tenantID*:<*guid*>" becomes: "<*guid*>.*foo AND tenantID*:<*guid*> *AND* (*docACL:*<*ace1*> *OR docACL*:<*ace2*> *OR docACL*:<*ace3*> *...*)"</span></span>

<span data-ttu-id="8cb6e-140">사용자 및 그룹 식별자 및 따라서 AES는 고유하기 때문에 일부 사용자에게만 표시되는 문서의 테넌트 간에 추가 보안 수준을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="8cb6e-140">Because user and group identifiers and hence ACEs are unique, this provides an extra level of security between tenants for documents that are only visible to some users.</span></span> <span data-ttu-id="8cb6e-141">테넌트의 일반 사용자에게 액세스 권한을 부여하는 특수 "외부 사용자를 제외한 모든 사용자" ACE의 경우에도 마찬가지입니다.</span><span class="sxs-lookup"><span data-stu-id="8cb6e-141">The same is the case for the special "Everyone except external users" ACE that grants access to regular users in the tenant.</span></span> <span data-ttu-id="8cb6e-142">그러나 "모든 사용자"에 대한 AES는 모든 테넌트에 대해 동일하기 때문에 공용 문서에 대한 테넌트 분리는 테넌트 ID 필터링에 따라 달라 습니다.</span><span class="sxs-lookup"><span data-stu-id="8cb6e-142">But since ACEs for "Everyone" are the same for all tenants, tenant separation for public documents depends on tenant ID filtering.</span></span> <span data-ttu-id="8cb6e-143">AES 거부도 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="8cb6e-143">Deny ACEs are also supported.</span></span> <span data-ttu-id="8cb6e-144">쿼리 보강은 거부 ACE와 일치하는 일치가 있는 경우 결과에서 문서를 제거하는 절을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="8cb6e-144">The query augmentation adds a clause that removes a document from the result when there is a match with a deny ACE.</span></span>

<span data-ttu-id="8cb6e-145">검색 Exchange Online 인덱스는 온라인에서와 같은 테넌트 ID(구독 ID) 대신 개별 사용자 사서함의 사서함 ID에 SharePoint 분할됩니다.</span><span class="sxs-lookup"><span data-stu-id="8cb6e-145">In Exchange Online search, the index is partitioned on mailbox ID for individual user's mailboxes instead of tenant ID (subscription ID) as in SharePoint Online.</span></span> <span data-ttu-id="8cb6e-146">분할 메커니즘은 SharePoint Online과 동일하지만 ACL 필터링은 없습니다.</span><span class="sxs-lookup"><span data-stu-id="8cb6e-146">The partitioning mechanism is the same as SharePoint Online, but there is no ACL filtering.</span></span>
