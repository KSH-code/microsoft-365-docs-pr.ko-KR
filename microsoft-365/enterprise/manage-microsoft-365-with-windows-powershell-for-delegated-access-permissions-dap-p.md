---
title: DAP Microsoft 365 사용자 Windows PowerShell 관리
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
audience: Admin
ms.topic: hub-page
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- Ent_O365
- M365-subscription-management
f1.keywords:
- NOCSH
ms.custom: seo-marvel-apr2020
ms.assetid: be497751-596f-431d-b256-0a89d36a47ce
description: Syndication 및 클라우드 솔루션 공급자(CSP) 파트너가 Windows PowerShell 테넌트 관리를 Microsoft 365 방법
ms.openlocfilehash: 352a9a01414b94a1593de6a734151b687524fe7d
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/19/2021
ms.locfileid: "50909529"
---
# <a name="how-to-manage-microsoft-365-with-windows-powershell-for-delegated-access-permissions-partners"></a><span data-ttu-id="f3546-103">위임된 액세스 Microsoft 365 파트너용 Windows PowerShell 관리 방법</span><span class="sxs-lookup"><span data-stu-id="f3546-103">How to manage Microsoft 365 with Windows PowerShell for Delegated Access Permissions partners</span></span>

<span data-ttu-id="f3546-104">*이 문서는 Microsoft 365 Enterprise와 Office 365 Enterprise에 모두 적용됩니다.*</span><span class="sxs-lookup"><span data-stu-id="f3546-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="f3546-105">DAP(위임된 액세스 권한) 파트너는 Syndication 및 CSP(클라우드 솔루션 공급자) 파트너입니다.</span><span class="sxs-lookup"><span data-stu-id="f3546-105">Delegated Access Permission (DAP) partners are Syndication and Cloud Solution Providers (CSP) Partners.</span></span> <span data-ttu-id="f3546-106">대부분의 공급자는 네트워크 또는 통신 공급자입니다.</span><span class="sxs-lookup"><span data-stu-id="f3546-106">Many are network or telecom providers.</span></span> <span data-ttu-id="f3546-107">서비스 Microsoft 365 구독을 번들로 묶습니다.</span><span class="sxs-lookup"><span data-stu-id="f3546-107">They bundle Microsoft 365 subscriptions into their service offerings.</span></span> <span data-ttu-id="f3546-108">Microsoft 365 구독을 판매하는 경우 고객의 테넌트에 대한 AOBO(관리 대신 관리) 권한이 자동으로 부여되어 해당 테넌트에 대해 관리하고 보고할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f3546-108">When they sell a Microsoft 365 subscription, they're automatically granted Administer On Behalf Of (AOBO) permissions to the customer's tenancies so they can administer and report on those tenancies.</span></span> <span data-ttu-id="f3546-109">이러한 작업은 Microsoft 365 관리 센터에서 수행하기가 어렵습니다.</span><span class="sxs-lookup"><span data-stu-id="f3546-109">These tasks are difficult to do in the Microsoft 365 admin center.</span></span> <span data-ttu-id="f3546-110">PowerShell을 사용하여 PowerShell을 Microsoft 365 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f3546-110">It's much easier to use PowerShell for Microsoft 365 to do administrative tasks such as:</span></span>
- <span data-ttu-id="f3546-111">모든 고객 **TenantIds** 및 해당 도메인 나열</span><span class="sxs-lookup"><span data-stu-id="f3546-111">List all the customer **TenantIds** and their domains</span></span> 
- <span data-ttu-id="f3546-112">고객 테넌트의 모든 사용자 및 할당된 라이선스 식별</span><span class="sxs-lookup"><span data-stu-id="f3546-112">Identify all users in a customer tenancy and their assigned licenses</span></span>
> [!NOTE]
> <span data-ttu-id="f3546-113">일부 관리 작업은 PowerShell에서만 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f3546-113">Some administrative tasks can only be done in PowerShell.</span></span>

<span data-ttu-id="f3546-114">다음 문서에서는 Syndication 및 CSP 파트너가 PowerShell을 사용하여 고객 테넌트 관리 방법을 보여 주며,</span><span class="sxs-lookup"><span data-stu-id="f3546-114">The following articles show how Syndication and CSP partners use PowerShell to administer their customer tenancies:</span></span>
  
- [<span data-ttu-id="f3546-115">DAP(위임된 액세스 Microsoft 365)에 대한 Windows PowerShell 테넌트 관리</span><span class="sxs-lookup"><span data-stu-id="f3546-115">Manage Microsoft 365 tenants with Windows PowerShell for Delegated Access Permissions (DAP) partners</span></span>](manage-microsoft-365-tenants-with-windows-powershell-for-delegated-access-permissio.md)
    
- [<span data-ttu-id="f3546-116">DAP(위임된 액세스 권한) 파트너용 Windows PowerShell을 사용하여 클라이언트 테넌트에 도메인 추가</span><span class="sxs-lookup"><span data-stu-id="f3546-116">Add a domain to a client tenancy with Windows PowerShell for Delegated Access Permission (DAP) partners</span></span>](add-a-domain-to-a-client-tenancy-with-windows-powershell-for-delegated-access-pe.md)
    
- [<span data-ttu-id="f3546-117">Exchange Online PowerShell에 연결</span><span class="sxs-lookup"><span data-stu-id="f3546-117">Connect to Exchange Online PowerShell</span></span>](/powershell/exchange/connect-to-exchange-online-powershell)
    
- [<span data-ttu-id="f3546-118">DAP(위임된 액세스 권한) 파트너용 Windows PowerShell을 사용하여 고객 테넌트 보고 데이터 검색</span><span class="sxs-lookup"><span data-stu-id="f3546-118">Retrieve customer tenant reporting data with Windows PowerShell for Delegated Access Permissions (DAP) partners</span></span>](retrieve-customer-tenant-reporting-data-with-windows-powershell-for-delegated-ac.md)
