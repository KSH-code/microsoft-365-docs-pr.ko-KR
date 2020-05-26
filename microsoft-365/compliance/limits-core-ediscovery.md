---
title: 핵심 eDiscovery 사례의 제한
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- Strat_O365_IP
- M365-security-compliance
- SPO_Content
search.appverid:
- MOE150
- MET150
description: 이 문서에서는 Microsoft 365의 핵심 eDiscovery 사례에 대 한 제한 사항에 대해 설명 합니다.
ms.openlocfilehash: 00df8cff683701ce5ee38dca12b6f7af5b31c8b0
ms.sourcegitcommit: 40ec697e27b6c9a78f2b679c6f5a8875dacde943
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/23/2020
ms.locfileid: "44351899"
---
# <a name="limits-in-core-ediscovery"></a><span data-ttu-id="8b93f-103">핵심 eDiscovery의 제한 사항</span><span class="sxs-lookup"><span data-stu-id="8b93f-103">Limits in core eDiscovery</span></span>

<span data-ttu-id="8b93f-104">다음 표에서는 핵심 ediscovery 사례와 관련 된 핵심 eDiscovery 사례 및 보류에 대 한 제한을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="8b93f-104">The following table lists the limits for core eDiscovery cases and holds associated with a core eDiscovery case.</span></span> <span data-ttu-id="8b93f-105">핵심 eDiscovery에 대 한 자세한 내용은 [Core Ediscovery 개요](ediscovery-cases.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="8b93f-105">For more information about core eDiscovery, see [Overview of core eDiscovery](ediscovery-cases.md).</span></span>
    
  |<span data-ttu-id="8b93f-106">**제한 설명**</span><span class="sxs-lookup"><span data-stu-id="8b93f-106">**Description of limit**</span></span>|<span data-ttu-id="8b93f-107">**제한 유형**</span><span class="sxs-lookup"><span data-stu-id="8b93f-107">**Limit**</span></span>|
  |:-----|:-----|
  |<span data-ttu-id="8b93f-108">조직의 최대 사례 수</span><span class="sxs-lookup"><span data-stu-id="8b93f-108">Maximum number of cases for an organization</span></span>  <br/> |<span data-ttu-id="8b93f-109">제한 없음</span><span class="sxs-lookup"><span data-stu-id="8b93f-109">No limit</span></span>  <br/> |
  |<span data-ttu-id="8b93f-110">조직에 대 한 최대 사례 보존 수</span><span class="sxs-lookup"><span data-stu-id="8b93f-110">Maximum number of case holds for an organization</span></span>  <br/> |<span data-ttu-id="8b93f-111">10,000</span><span class="sxs-lookup"><span data-stu-id="8b93f-111">10,000</span></span>  <br/> |
  |<span data-ttu-id="8b93f-112">단일 케이스 보류의 최대 사서함 수</span><span class="sxs-lookup"><span data-stu-id="8b93f-112">Maximum number of mailboxes in a single case hold</span></span>  <br/> |<span data-ttu-id="8b93f-113">1,000</span><span class="sxs-lookup"><span data-stu-id="8b93f-113">1,000</span></span>  <br/> |
  |<span data-ttu-id="8b93f-114">단일 케이스 보류에서의 최대 SharePoint 및 비즈니스용 OneDrive 사이트 수</span><span class="sxs-lookup"><span data-stu-id="8b93f-114">Maximum number of SharePoint and OneDrive for Business sites in a single case hold</span></span>  <br/> |<span data-ttu-id="8b93f-115">100</span><span class="sxs-lookup"><span data-stu-id="8b93f-115">100</span></span>  <br/> |
  |<span data-ttu-id="8b93f-116">핵심 eDiscovery 홈 페이지에 표시 되는 최대 사례 수 및 사례 내의 보류, 검색 및 내보내기 탭에 표시 되는 최대 항목 수입니다.</span><span class="sxs-lookup"><span data-stu-id="8b93f-116">Maximum number of cases displayed on the core eDiscovery home page, and the maximum number of items displayed on the Holds, Searches, and Export tabs within a case.</span></span> <span data-ttu-id="8b93f-117"><sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="8b93f-117"><sup>1</sup></span></span> |<span data-ttu-id="8b93f-118">1,000</span><span class="sxs-lookup"><span data-stu-id="8b93f-118">1,000</span></span>|
  |||

   > [!NOTE]
   > <span data-ttu-id="8b93f-119"><sup>1</sup> 1000 개 보다 많은 사례, 보류 중, 검색 또는 내보내기의 목록을 보려면 해당 Office 365 Security & 준수 PowerShell cmdlet을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8b93f-119"><sup>1</sup> To view a list of more than 1,000 cases, holds, searches, or exports, you can use the corresponding Office 365 Security & Compliance PowerShell cmdlet:</span></span><br/> [<span data-ttu-id="8b93f-120">Remove-compliancecase</span><span class="sxs-lookup"><span data-stu-id="8b93f-120">Get-ComplianceCase</span></span>](https://docs.microsoft.com/powershell/module/exchange/get-compliancecase) <br/> [<span data-ttu-id="8b93f-121">New-caseholdpolicy</span><span class="sxs-lookup"><span data-stu-id="8b93f-121">Get-CaseHoldPolicy</span></span>](https://docs.microsoft.com/powershell/module/exchange/get-caseholdpolicy)<br/> [<span data-ttu-id="8b93f-122">Get-ComplianceSearch</span><span class="sxs-lookup"><span data-stu-id="8b93f-122">Get-ComplianceSearch</span></span>](https://docs.microsoft.com/powershell/module/exchange/get-compliancesearch)<br/> [<span data-ttu-id="8b93f-123">New-compliancesearchaction</span><span class="sxs-lookup"><span data-stu-id="8b93f-123">Get-ComplianceSearchAction</span></span>](https://docs.microsoft.com/powershell/module/exchange/get-compliancesearchaction)
