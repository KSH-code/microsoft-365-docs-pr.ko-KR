---
title: 핵심 eDiscovery 사례의 제한
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: reference
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- Strat_O365_IP
- M365-security-compliance
- SPO_Content
search.appverid:
- MOE150
- MET150
description: 이 문서에서는 핵심 eDiscovery 사례의 제한에 대해 Microsoft 365.
ms.openlocfilehash: e7b1013abd9fd94748baf3b83dd04efbc3831a1d
ms.sourcegitcommit: efb932db63ad3ab4af4b585428d567d069410e4e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2021
ms.locfileid: "52311427"
---
# <a name="limits-in-core-ediscovery"></a><span data-ttu-id="d1d1d-103">Core eDiscovery의 제한</span><span class="sxs-lookup"><span data-stu-id="d1d1d-103">Limits in Core eDiscovery</span></span>

<span data-ttu-id="d1d1d-104">다음 표에는 핵심 eDiscovery 사례 및 핵심 eDiscovery 사례와 관련된 보류에 대한 제한이 나열됩니다.</span><span class="sxs-lookup"><span data-stu-id="d1d1d-104">The following table lists the limits for core eDiscovery cases and holds associated with a core eDiscovery case.</span></span> <span data-ttu-id="d1d1d-105">Core eDiscovery에 대한 자세한 내용은 [Core eDiscovery 개요를 참조하세요.](./get-started-core-ediscovery.md)</span><span class="sxs-lookup"><span data-stu-id="d1d1d-105">For more information about Core eDiscovery, see [Overview of Core eDiscovery](./get-started-core-ediscovery.md).</span></span>
    
  | <span data-ttu-id="d1d1d-106">제한 설명</span><span class="sxs-lookup"><span data-stu-id="d1d1d-106">Description of limit</span></span> | <span data-ttu-id="d1d1d-107">제한 유형</span><span class="sxs-lookup"><span data-stu-id="d1d1d-107">Limit</span></span> |
  |:-----|:-----|
  |<span data-ttu-id="d1d1d-108">조직의 최대 사례 수입니다.</span><span class="sxs-lookup"><span data-stu-id="d1d1d-108">Maximum number of cases for an organization.</span></span>  <br/> |<span data-ttu-id="d1d1d-109">제한 없음</span><span class="sxs-lookup"><span data-stu-id="d1d1d-109">No limit</span></span>  <br/> |
  |<span data-ttu-id="d1d1d-110">조직의 최대 케이스 보류 수입니다.</span><span class="sxs-lookup"><span data-stu-id="d1d1d-110">Maximum number of case holds for an organization.</span></span>  <br/> |<span data-ttu-id="d1d1d-111">10,000</span><span class="sxs-lookup"><span data-stu-id="d1d1d-111">10,000</span></span>  <br/> |
  |<span data-ttu-id="d1d1d-112">단일 케이스 보류의 최대 사서함 수입니다.</span><span class="sxs-lookup"><span data-stu-id="d1d1d-112">Maximum number of mailboxes in a single case hold.</span></span> <span data-ttu-id="d1d1d-113">이 제한에는 사용자 사서함의 총 합계와 Microsoft 365, Microsoft Teams 및 그룹과 연결된 Yammer 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="d1d1d-113">This limit includes the combined total of user mailboxes, and the mailboxes associated with Microsoft 365 Groups, Microsoft Teams, and Yammer Groups.</span></span>  <br/> |<span data-ttu-id="d1d1d-114">1,000</span><span class="sxs-lookup"><span data-stu-id="d1d1d-114">1,000</span></span>  <br/> |
  |<span data-ttu-id="d1d1d-115">단일 케이스 보류의 최대 사이트 수입니다.</span><span class="sxs-lookup"><span data-stu-id="d1d1d-115">Maximum number of sites in a single case hold.</span></span> <span data-ttu-id="d1d1d-116">이 제한에는 비즈니스용 OneDrive, SharePoint 사이트, Microsoft 365 그룹, Microsoft Teams 및 Yammer 그룹과 연결된 사이트가 Yammer 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="d1d1d-116">This limit includes the combined total of OneDrive for Business sites, SharePoint sites, and the sites associated with Microsoft 365 Groups, Microsoft Teams, and Yammer Groups.</span></span>  <br/> |<span data-ttu-id="d1d1d-117">100</span><span class="sxs-lookup"><span data-stu-id="d1d1d-117">100</span></span>  <br/> |
  |<span data-ttu-id="d1d1d-118">핵심 eDiscovery 홈 페이지에 표시되는 최대 사례 수와 케이스 내의 보류, 검색 및 내보내기 탭에 표시되는 최대 항목 수입니다.</span><span class="sxs-lookup"><span data-stu-id="d1d1d-118">Maximum number of cases displayed on the core eDiscovery home page, and the maximum number of items displayed on the Holds, Searches, and Export tabs within a case.</span></span> <span data-ttu-id="d1d1d-119"><sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="d1d1d-119"><sup>1</sup></span></span> |<span data-ttu-id="d1d1d-120">1,000</span><span class="sxs-lookup"><span data-stu-id="d1d1d-120">1,000</span></span>|
  |||

   > [!NOTE]
   > <span data-ttu-id="d1d1d-121"><sup>1</sup> 1,000개가 넘는 사례, 보류, 검색 또는 내보내기 목록을 표시하기 위해 해당 Office 365 Security & 준수 PowerShell cmdlet을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d1d1d-121"><sup>1</sup> To view a list of more than 1,000 cases, holds, searches, or exports, you can use the corresponding Office 365 Security & Compliance PowerShell cmdlets:</span></span>
   > 
   > - [<span data-ttu-id="d1d1d-122">Get-ComplianceCase</span><span class="sxs-lookup"><span data-stu-id="d1d1d-122">Get-ComplianceCase</span></span>](/powershell/module/exchange/get-compliancecase)
   > - [<span data-ttu-id="d1d1d-123">Get-CaseHoldPolicy</span><span class="sxs-lookup"><span data-stu-id="d1d1d-123">Get-CaseHoldPolicy</span></span>](/powershell/module/exchange/get-caseholdpolicy)
   > - [<span data-ttu-id="d1d1d-124">Get-ComplianceSearch</span><span class="sxs-lookup"><span data-stu-id="d1d1d-124">Get-ComplianceSearch</span></span>](/powershell/module/exchange/get-compliancesearch)
   > - [<span data-ttu-id="d1d1d-125">Get-ComplianceSearchAction</span><span class="sxs-lookup"><span data-stu-id="d1d1d-125">Get-ComplianceSearchAction</span></span>](/powershell/module/exchange/get-compliancesearchaction)

<span data-ttu-id="d1d1d-126">Core eDiscovery 사례와 연결된 검색 및 내보내기와 관련된 제한에 대한 자세한 내용은 [Limits for Content search and Core eDiscovery을 참조하십시오.](limits-for-content-search.md)</span><span class="sxs-lookup"><span data-stu-id="d1d1d-126">For more information about limits related to searches and exports associated with a Core eDiscovery case, see [Limits for Content search and Core eDiscovery](limits-for-content-search.md).</span></span>