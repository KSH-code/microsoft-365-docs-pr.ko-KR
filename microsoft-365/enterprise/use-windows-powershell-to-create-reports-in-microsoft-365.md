---
title: PowerShell을 사용하여 Microsoft 365 보고서 만들기
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 07/17/2020
audience: ITPro
ms.topic: hub-page
ms.service: o365-administration
localization_priority: Normal
ms.collection: Ent_O365
f1.keywords:
- CSH
ms.custom:
- Ent_Office_Other
- seo-marvel-apr2020
ms.assetid: 1ea4d4ec-af89-496f-9678-701867f5a6fc
description: '요약: Microsoft 365용 PowerShell을 사용하여 Microsoft 365 관리 센터에서 생성할 수 없는 보고서를 만들 수 있습니다.'
ms.openlocfilehash: 10000f62b1d6a747cf0373623c6038b080666e1a
ms.sourcegitcommit: 66b8fc1d8ba4f17487cd2004ac19cf2fff472f3d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/24/2020
ms.locfileid: "48753981"
---
# <a name="use-powershell-to-create-reports-for-microsoft-365"></a><span data-ttu-id="fd0bd-103">PowerShell을 사용하여 Microsoft 365 보고서 만들기</span><span class="sxs-lookup"><span data-stu-id="fd0bd-103">Use PowerShell to create reports for Microsoft 365</span></span>

<span data-ttu-id="fd0bd-104">*이 문서는 Microsoft 365 Enterprise와 Office 365 Enterprise에 모두 적용됩니다.*</span><span class="sxs-lookup"><span data-stu-id="fd0bd-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="fd0bd-105">Microsoft 365 관리 센터에서는 다양한 보고서를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fd0bd-105">Many different reports are available in the Microsoft 365 admin center.</span></span> <span data-ttu-id="fd0bd-106">그러나 이러한 보고서는 너무 많은 정보만 제공하고 경우에 따라 더 많은 정보가 필요할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fd0bd-106">But these reports only provide so much information, and sometimes you need more.</span></span> <span data-ttu-id="fd0bd-107">Microsoft 365용 PowerShell이 필요한 경우입니다.</span><span class="sxs-lookup"><span data-stu-id="fd0bd-107">That's when you need PowerShell for Microsoft 365.</span></span>
  
<span data-ttu-id="fd0bd-108">다음 문서에서는 Microsoft 365용 PowerShell을 사용하여 Microsoft 365 테넌트에서 정보를 다운로드하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="fd0bd-108">These articles describe how to use PowerShell for Microsoft 365 to get information from your Microsoft 365 tenant:</span></span>
  
- <span data-ttu-id="fd0bd-109">Microsoft 365용 PowerShell을 사용하여 보고 시작:</span><span class="sxs-lookup"><span data-stu-id="fd0bd-109">Get started with reporting using PowerShell for Microsoft 365:</span></span>
    
  - [<span data-ttu-id="fd0bd-110">Microsoft 365 용 PowerShell을 사용해야 하는 이유</span><span class="sxs-lookup"><span data-stu-id="fd0bd-110">Why you need to use PowerShell for Microsoft 365</span></span>](https://technet.microsoft.com/library/dn568034.aspx#reveal)
    
    
- <span data-ttu-id="fd0bd-111">사용자 계정 및 라이선스에 대한 보고서:</span><span class="sxs-lookup"><span data-stu-id="fd0bd-111">Reports for user accounts and licenses:</span></span>
    
  - [<span data-ttu-id="fd0bd-112">PowerShell을 통해 Microsoft 365 라이선스 및 서비스 보기</span><span class="sxs-lookup"><span data-stu-id="fd0bd-112">View Microsoft 365 licenses and services with PowerShell</span></span>](view-licenses-and-services-with-microsoft-365-powershell.md)
    
  - [<span data-ttu-id="fd0bd-113">PowerShell을 통해 Microsoft 365 라이선스 및 허가되지 않은 사용자 보기</span><span class="sxs-lookup"><span data-stu-id="fd0bd-113">View Microsoft 365 licensed and unlicensed users with PowerShell</span></span>](view-licensed-and-unlicensed-users-with-microsoft-365-powershell.md)
    
  - [<span data-ttu-id="fd0bd-114">PowerShell을 통해 Microsoft 365 계정 라이선스 및 서비스 세부 정보 보기</span><span class="sxs-lookup"><span data-stu-id="fd0bd-114">View Microsoft 365 account license and service details with PowerShell</span></span>](view-account-license-and-service-details-with-microsoft-365-powershell.md)
    
  - [<span data-ttu-id="fd0bd-115">PowerShell을 통해 Microsoft 365 사용자 계정 보기</span><span class="sxs-lookup"><span data-stu-id="fd0bd-115">View Microsoft 365 user accounts with PowerShell</span></span>](view-user-accounts-with-microsoft-365-powershell.md)
    
- <span data-ttu-id="fd0bd-116">SharePoint Online용 보고서:</span><span class="sxs-lookup"><span data-stu-id="fd0bd-116">Reports for SharePoint Online:</span></span>
    
  - [<span data-ttu-id="fd0bd-117">SharePoint Online 관리 셸 시작하기</span><span class="sxs-lookup"><span data-stu-id="fd0bd-117">Get started with SharePoint Online Management Shell</span></span>](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online)
    
  - [<span data-ttu-id="fd0bd-118">Get-SPOSiteGroup - 지정된 사이트 모음의 모든 그룹</span><span class="sxs-lookup"><span data-stu-id="fd0bd-118">Get-SPOSiteGroup - Gets all the groups on a specified site collection</span></span>](https://technet.microsoft.com/library/122f4099-c78d-4cce-bab0-4343b04596ae.aspx)
    
- <span data-ttu-id="fd0bd-119">Exchange Online용 보고서:</span><span class="sxs-lookup"><span data-stu-id="fd0bd-119">Reports for Exchange Online:</span></span>
    
  - [<span data-ttu-id="fd0bd-120">Exchange Online PowerShell을 사용하여 사서함 표시</span><span class="sxs-lookup"><span data-stu-id="fd0bd-120">Use Exchange Online PowerShell to display mailbox</span></span>](https://technet.microsoft.com/library/13843002-56ca-4b75-81c5-84386522b01b.aspx)
    
    
## <a name="related-articlesl"></a><span data-ttu-id="fd0bd-121">관련 문서</span><span class="sxs-lookup"><span data-stu-id="fd0bd-121">Related articlesl</span></span>

[<span data-ttu-id="fd0bd-122">PowerShell로 Microsoft 365 관리</span><span class="sxs-lookup"><span data-stu-id="fd0bd-122">Manage Microsoft 365 with PowerShell</span></span>](manage-microsoft-365-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="fd0bd-123">Microsoft 365용 PowerShell 시작</span><span class="sxs-lookup"><span data-stu-id="fd0bd-123">Get started with PowerShell for Microsoft 365</span></span>](getting-started-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="fd0bd-124">PowerShell을 사용하여 SharePoint 관리</span><span class="sxs-lookup"><span data-stu-id="fd0bd-124">Manage SharePoint with PowerShell</span></span>](manage-sharepoint-online-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="fd0bd-125">PowerShell로 Microsoft 365 사용자 계정, 라이선스 및 그룹 관리</span><span class="sxs-lookup"><span data-stu-id="fd0bd-125">Manage Microsoft 365 user accounts, licenses, and groups with PowerShell</span></span>](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)
  