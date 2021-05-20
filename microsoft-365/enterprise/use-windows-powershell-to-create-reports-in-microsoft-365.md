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
description: '요약: Microsoft 365 PowerShell을 사용하여 Microsoft 365 관리 센터에서 생성할 수 없는 보고서를 만듭니다.'
ms.openlocfilehash: 9e3b90dcdd32f80125175ad2e15a852db51e17f8
ms.sourcegitcommit: 0936f075a1205b8f8a71a7dd7761a2e2ce6167b3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/19/2021
ms.locfileid: "52572744"
---
# <a name="use-powershell-to-create-reports-for-microsoft-365"></a><span data-ttu-id="867b2-103">PowerShell을 사용하여 Microsoft 365 보고서 만들기</span><span class="sxs-lookup"><span data-stu-id="867b2-103">Use PowerShell to create reports for Microsoft 365</span></span>

<span data-ttu-id="867b2-104">*이 문서는 Microsoft 365 Enterprise와 Office 365 Enterprise에 모두 적용됩니다.*</span><span class="sxs-lookup"><span data-stu-id="867b2-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="867b2-105">Microsoft 365 관리자 센터에서 다양한 보고서를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="867b2-105">Many different reports are available in the Microsoft 365 admin center.</span></span> <span data-ttu-id="867b2-106">그러나 이러한 보고서는 너무 많은 정보를 제공하며 때로는 더 많은 정보가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="867b2-106">But these reports only provide so much information, and sometimes you need more.</span></span> <span data-ttu-id="867b2-107">Microsoft 365 위해 PowerShell이 필요할 때입니다.</span><span class="sxs-lookup"><span data-stu-id="867b2-107">That's when you need PowerShell for Microsoft 365.</span></span>
  
<span data-ttu-id="867b2-108">이 문서에서는 Microsoft 365 PowerShell을 사용하여 Microsoft 365 테넌트의 정보를 얻는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="867b2-108">These articles describe how to use PowerShell for Microsoft 365 to get information from your Microsoft 365 tenant:</span></span>
  
- <span data-ttu-id="867b2-109">Microsoft 365 위해 PowerShell을 사용하여 보고부터 시작하십시오.</span><span class="sxs-lookup"><span data-stu-id="867b2-109">Get started with reporting using PowerShell for Microsoft 365:</span></span>
    
  - [<span data-ttu-id="867b2-110">Microsoft 365 용 PowerShell을 사용해야 하는 이유</span><span class="sxs-lookup"><span data-stu-id="867b2-110">Why you need to use PowerShell for Microsoft 365</span></span>](./why-you-need-to-use-microsoft-365-powershell.md)
    
    
- <span data-ttu-id="867b2-111">사용자 계정 및 라이선스에 대한 보고서:</span><span class="sxs-lookup"><span data-stu-id="867b2-111">Reports for user accounts and licenses:</span></span>
    
  - [<span data-ttu-id="867b2-112">PowerShell을 통해 Microsoft 365 라이선스 및 서비스 보기</span><span class="sxs-lookup"><span data-stu-id="867b2-112">View Microsoft 365 licenses and services with PowerShell</span></span>](view-licenses-and-services-with-microsoft-365-powershell.md)
    
  - [<span data-ttu-id="867b2-113">PowerShell을 통해 라이선스 및 무면허 사용자 Microsoft 365 보기</span><span class="sxs-lookup"><span data-stu-id="867b2-113">View Microsoft 365 licensed and unlicensed users with PowerShell</span></span>](view-licensed-and-unlicensed-users-with-microsoft-365-powershell.md)
    
  - [<span data-ttu-id="867b2-114">PowerShell을 통해 계정 라이선스 및 서비스 세부 정보를 Microsoft 365 보기</span><span class="sxs-lookup"><span data-stu-id="867b2-114">View Microsoft 365 account license and service details with PowerShell</span></span>](view-account-license-and-service-details-with-microsoft-365-powershell.md)
    
  - [<span data-ttu-id="867b2-115">PowerShell으로 Microsoft 365 사용자 계정 보기</span><span class="sxs-lookup"><span data-stu-id="867b2-115">View Microsoft 365 user accounts with PowerShell</span></span>](view-user-accounts-with-microsoft-365-powershell.md)
    
- <span data-ttu-id="867b2-116">SharePoint Online용 보고서:</span><span class="sxs-lookup"><span data-stu-id="867b2-116">Reports for SharePoint Online:</span></span>
    
  - [<span data-ttu-id="867b2-117">SharePoint Online 관리 셸 시작하기</span><span class="sxs-lookup"><span data-stu-id="867b2-117">Get started with SharePoint Online Management Shell</span></span>](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online)
    
  - [<span data-ttu-id="867b2-118">Get-SPOSiteGroup - 지정된 사이트 컬렉션에서 모든 그룹을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="867b2-118">Get-SPOSiteGroup - Gets all the groups on a specified site collection</span></span>](/powershell/module/sharepoint-online/get-spositegroup)
    
- <span data-ttu-id="867b2-119">Exchange Online용 보고서:</span><span class="sxs-lookup"><span data-stu-id="867b2-119">Reports for Exchange Online:</span></span>
    
  - [<span data-ttu-id="867b2-120">Exchange Online PowerShell을 사용하여 사서함을 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="867b2-120">Use Exchange Online PowerShell to display mailbox</span></span>](/exchange/recipients-in-exchange-online/manage-user-mailboxes/use-powershell-to-display-mailbox-information)
    
    
## <a name="related-articles"></a><span data-ttu-id="867b2-121">관련 문서</span><span class="sxs-lookup"><span data-stu-id="867b2-121">Related articles</span></span>

[<span data-ttu-id="867b2-122">PowerShell로 Microsoft 365 관리</span><span class="sxs-lookup"><span data-stu-id="867b2-122">Manage Microsoft 365 with PowerShell</span></span>](manage-microsoft-365-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="867b2-123">Microsoft 365용 PowerShell 시작</span><span class="sxs-lookup"><span data-stu-id="867b2-123">Get started with PowerShell for Microsoft 365</span></span>](getting-started-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="867b2-124">PowerShell으로 SharePoint 관리</span><span class="sxs-lookup"><span data-stu-id="867b2-124">Manage SharePoint with PowerShell</span></span>](manage-sharepoint-online-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="867b2-125">PowerShell로 Microsoft 365 사용자 계정, 라이선스 및 그룹 관리</span><span class="sxs-lookup"><span data-stu-id="867b2-125">Manage Microsoft 365 user accounts, licenses, and groups with PowerShell</span></span>](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)
