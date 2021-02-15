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
description: 이 문서에서는 Microsoft 365의 핵심 eDiscovery 사례에 대한 제한에 대해 설명하고 있습니다.
ms.openlocfilehash: 43d267acdb0c1fee0202c74832b376e066241d7c
ms.sourcegitcommit: 495b66b77d6dbe6d69e5b06b304089e4e476e568
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49799665"
---
# <a name="limits-in-core-ediscovery"></a><span data-ttu-id="b660f-103">Core eDiscovery의 제한</span><span class="sxs-lookup"><span data-stu-id="b660f-103">Limits in Core eDiscovery</span></span>

<span data-ttu-id="b660f-104">다음 표에는 핵심 eDiscovery 사례 및 핵심 eDiscovery 사례와 연결된 보류에 대한 제한이 나열됩니다.</span><span class="sxs-lookup"><span data-stu-id="b660f-104">The following table lists the limits for core eDiscovery cases and holds associated with a core eDiscovery case.</span></span> <span data-ttu-id="b660f-105">Core eDiscovery에 대한 자세한 내용은 [Core eDiscovery 개요를 참조하세요.](ediscovery-cases.md)</span><span class="sxs-lookup"><span data-stu-id="b660f-105">For more information about Core eDiscovery, see [Overview of Core eDiscovery](ediscovery-cases.md).</span></span>
    
  | <span data-ttu-id="b660f-106">제한 설명</span><span class="sxs-lookup"><span data-stu-id="b660f-106">Description of limit</span></span> | <span data-ttu-id="b660f-107">제한</span><span class="sxs-lookup"><span data-stu-id="b660f-107">Limit</span></span> |
  |:-----|:-----|
  |<span data-ttu-id="b660f-108">조직의 최대 사례 수</span><span class="sxs-lookup"><span data-stu-id="b660f-108">Maximum number of cases for an organization</span></span>  <br/> |<span data-ttu-id="b660f-109">제한 없음</span><span class="sxs-lookup"><span data-stu-id="b660f-109">No limit</span></span>  <br/> |
  |<span data-ttu-id="b660f-110">조직의 최대 케이스 보류 수</span><span class="sxs-lookup"><span data-stu-id="b660f-110">Maximum number of case holds for an organization</span></span>  <br/> |<span data-ttu-id="b660f-111">10,000</span><span class="sxs-lookup"><span data-stu-id="b660f-111">10,000</span></span>  <br/> |
  |<span data-ttu-id="b660f-112">단일 케이스 보류의 최대 사서함 수</span><span class="sxs-lookup"><span data-stu-id="b660f-112">Maximum number of mailboxes in a single case hold</span></span>  <br/> |<span data-ttu-id="b660f-113">1,000</span><span class="sxs-lookup"><span data-stu-id="b660f-113">1,000</span></span>  <br/> |
  |<span data-ttu-id="b660f-114">단일 케이스 보류의 최대 SharePoint 및 비즈니스용 OneDrive 사이트 수</span><span class="sxs-lookup"><span data-stu-id="b660f-114">Maximum number of SharePoint and OneDrive for Business sites in a single case hold</span></span>  <br/> |<span data-ttu-id="b660f-115">100</span><span class="sxs-lookup"><span data-stu-id="b660f-115">100</span></span>  <br/> |
  |<span data-ttu-id="b660f-116">핵심 eDiscovery 홈 페이지에 표시되는 최대 사례 수와 케이스 내의 보류, 검색 및 내보내기 탭에 표시되는 최대 항목 수입니다.</span><span class="sxs-lookup"><span data-stu-id="b660f-116">Maximum number of cases displayed on the core eDiscovery home page, and the maximum number of items displayed on the Holds, Searches, and Export tabs within a case.</span></span> <span data-ttu-id="b660f-117"><sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="b660f-117"><sup>1</sup></span></span> |<span data-ttu-id="b660f-118">1,000</span><span class="sxs-lookup"><span data-stu-id="b660f-118">1,000</span></span>|
  |||

   > [!NOTE]
   > <span data-ttu-id="b660f-119"><sup>1</sup> 1,000개가 넘는 사례, 보류, 검색 또는 내보내기 목록을 표시하기 위해 해당 Office 365 보안 & PowerShell cmdlet을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b660f-119"><sup>1</sup> To view a list of more than 1,000 cases, holds, searches, or exports, you can use the corresponding Office 365 Security & Compliance PowerShell cmdlets:</span></span>
   > 
   > - [<span data-ttu-id="b660f-120">Get-ComplianceCase</span><span class="sxs-lookup"><span data-stu-id="b660f-120">Get-ComplianceCase</span></span>](https://docs.microsoft.com/powershell/module/exchange/get-compliancecase)
   > - [<span data-ttu-id="b660f-121">Get-CaseHoldPolicy</span><span class="sxs-lookup"><span data-stu-id="b660f-121">Get-CaseHoldPolicy</span></span>](https://docs.microsoft.com/powershell/module/exchange/get-caseholdpolicy)
   > - [<span data-ttu-id="b660f-122">Get-ComplianceSearch</span><span class="sxs-lookup"><span data-stu-id="b660f-122">Get-ComplianceSearch</span></span>](https://docs.microsoft.com/powershell/module/exchange/get-compliancesearch)
   > - [<span data-ttu-id="b660f-123">Get-ComplianceSearchAction</span><span class="sxs-lookup"><span data-stu-id="b660f-123">Get-ComplianceSearchAction</span></span>](https://docs.microsoft.com/powershell/module/exchange/get-compliancesearchaction)

<span data-ttu-id="b660f-124">Core eDiscovery 사례와 연결된 콘텐츠 검색 및 내보내기와 관련된 제한에 대한 자세한 내용은 콘텐츠 검색 및 [Core eDiscovery에](limits-for-content-search.md)대한 제한을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="b660f-124">For more information about limits related to content searches and exports associated with a Core eDiscovery case, see [Limits for Content Search and Core eDiscovery](limits-for-content-search.md).</span></span>