---
title: DNS 레코드를 만드는 데 필요한 정보 수집
f1.keywords:
- NOCSH
ms.author: pebaum
author: pebaum
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
- Adm_O365_Setup
ms.custom:
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
- GEA150
ms.assetid: 77f90d4a-dc7f-4f09-8972-c1b03ea85a67
description: 도메인을 Microsoft 365 DNS 레코드를 만드는 데 필요한 값/정보를 수집합니다.
ms.openlocfilehash: def9fbe201e158f1e071a67caeaf29ed26732f97
ms.sourcegitcommit: a4c93a4c7d7db08fe3b032b58d5c7dbbb9476e90
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/02/2021
ms.locfileid: "53256846"
---
# <a name="gather-the-information-you-need-to-create-dns-records"></a><span data-ttu-id="af2aa-103">DNS 레코드를 만드는 데 필요한 정보 수집</span><span class="sxs-lookup"><span data-stu-id="af2aa-103">Gather the information you need to create DNS records</span></span>

 <span data-ttu-id="af2aa-104">원하는 정보를 찾지 못한 경우 **[도메인 FAQ를 확인](../setup/domains-faq.yml)** 하세요.</span><span class="sxs-lookup"><span data-stu-id="af2aa-104">**[Check the Domains FAQ](../setup/domains-faq.yml)** if you don't find what you're looking for.</span></span> 
  
### <a name="step-1-find-the-txt-record-value-and-verify"></a><span data-ttu-id="af2aa-105">1단계: TXT 레코드 값 찾기 및 확인</span><span class="sxs-lookup"><span data-stu-id="af2aa-105">Step 1: Find the TXT record value and verify</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="af2aa-106">In the Microsoft 365 관리 센터, go to the **설정** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span><span class="sxs-lookup"><span data-stu-id="af2aa-106">In the Microsoft 365 admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="af2aa-107">I관리 센터에서 **설정** > <a href="https://go.microsoft.com/fwlink/p/?linkid=854615" target="_blank"> 도메인</a> 페이지로 이동하십시오.</span><span class="sxs-lookup"><span data-stu-id="af2aa-107">In the admin center, go to the **Settings** > <a href="https://go.microsoft.com/fwlink/p/?linkid=854615" target="_blank">Domains</a> page.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="af2aa-108">I관리 센터에서 **설정** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2007048" target="_blank"> 도메인</a> 페이지로 이동하십시오.</span><span class="sxs-lookup"><span data-stu-id="af2aa-108">In the admin center, go to the **Settings** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2007048" target="_blank">Domains</a> page.</span></span>

::: moniker-end
    
2. <span data-ttu-id="af2aa-109">On the **Domains** page, select your domain, then select **Start setup**.</span><span class="sxs-lookup"><span data-stu-id="af2aa-109">On the **Domains** page, select your domain, then select **Start setup**.</span></span> <span data-ttu-id="af2aa-110">추가해야 하는 특정 값을 확인하려면 도메인 설정 마법사로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="af2aa-110">You'll go back to the domains setup wizard to see the specific value you need to add.</span></span>
    
3. <span data-ttu-id="af2aa-111">도메인 확인 **페이지에서** 도메인의 DNS 레코드에 **TXT 레코드** 추가를 선택하고 계속을 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="af2aa-111">On the **Domain Verification** page, select **Add a TXT record to the domain's DNS records**, then select **Continue**.</span></span>
    
4. <span data-ttu-id="af2aa-112">표시된 **TXT 값을 복사합니다.**</span><span class="sxs-lookup"><span data-stu-id="af2aa-112">Copy the **TXT value** shown.</span></span> <span data-ttu-id="af2aa-113">**MS=msXXXXXXXXX는** 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="af2aa-113">It looks like this: **MS=msXXXXXXXX**.</span></span> 
    
5. <span data-ttu-id="af2aa-114">도메인을 [연결하려면 DNS](create-dns-records-at-any-dns-hosting-provider.md)레코드 추가로 이동한 다음 단계에 따라 DNS 호스트의 웹 사이트에서 레코드를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="af2aa-114">Go to [Add DNS records to connect your domain](create-dns-records-at-any-dns-hosting-provider.md), and follow the steps to add records at your DNS host's website.</span></span>
    
6. <span data-ttu-id="af2aa-115">DNS 호스트에서 TXT 레코드(또는 MX 레코드)를 만들기 위한 단계를 수행한 다음 도메인이 DNS 호스트에서 다시 Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="af2aa-115">Follow the steps for creating the TXT record (or MX record) at your DNS host, then verify the domain back in Microsoft 365.</span></span>

7. <span data-ttu-id="af2aa-116">도메인이 도메인에서 확인되면 DNS 호스트에서 TXT 레코드(또는 MX 레코드)를 Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="af2aa-116">Remove the TXT record (or MX record) from your DNS host once the domain is verified in Microsoft 365.</span></span>
    
### <a name="step-2-find-the-mx-record-value-for-email-and-more"></a><span data-ttu-id="af2aa-117">2단계: 전자 메일에 대한 MX 레코드 값 찾기</span><span class="sxs-lookup"><span data-stu-id="af2aa-117">Step 2: Find the MX record value for email and more</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="af2aa-118">In the Microsoft 365 관리 센터, go to the **설정** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span><span class="sxs-lookup"><span data-stu-id="af2aa-118">In the Microsoft 365 admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

::: moniker-end
    
::: moniker range="o365-germany"

1. <span data-ttu-id="af2aa-119">I관리 센터에서 **설정** > <a href="https://go.microsoft.com/fwlink/p/?linkid=854615" target="_blank"> 도메인</a> 페이지로 이동하십시오.</span><span class="sxs-lookup"><span data-stu-id="af2aa-119">In the admin center, go to the **Settings** > <a href="https://go.microsoft.com/fwlink/p/?linkid=854615" target="_blank">Domains</a> page.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="af2aa-120">I관리 센터에서 **설정** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2007048" target="_blank"> 도메인</a> 페이지로 이동하십시오.</span><span class="sxs-lookup"><span data-stu-id="af2aa-120">In the admin center, go to the **Settings** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2007048" target="_blank">Domains</a> page.</span></span>

::: moniker-end
    
2. <span data-ttu-id="af2aa-121">**도메인** 페이지에서 도메인을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="af2aa-121">On the **Domains** page, select your domain.</span></span>
    
3. <span data-ttu-id="af2aa-122">CHOOSE **Manage DNS**, select More **Options** Add your  >  **own DNS** and select **Continue** to see the DNS records to add.</span><span class="sxs-lookup"><span data-stu-id="af2aa-122">Choose  **Manage DNS**, select **More Options** > **Add your own DNS** and select **Continue** to see the DNS records to add.</span></span>
    
    <span data-ttu-id="af2aa-123">DNS 호스트에서 변경하는 동안 이 정보를 사용할 수 있도록 유지하여 값을 복사하고 붙여 넣을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="af2aa-123">You'll want to keep this information available while you make changes at your DNS host, so you can copy and paste the values.</span></span>
    
    <span data-ttu-id="af2aa-124">이 페이지에 나열되는 DNS 레코드 그룹은 **도메인 용도** 아래에 나열된 선택 사항에 따라 달라집니다.</span><span class="sxs-lookup"><span data-stu-id="af2aa-124">The groups of DNS records that are listed on the page depend on your choices listed under **Domain purpose**.</span></span>
    
4. <span data-ttu-id="af2aa-125">도메인을 [연결하려면 DNS](create-dns-records-at-any-dns-hosting-provider.md)레코드 추가로 이동한 다음 단계에 따라 DNS 호스트의 웹 사이트에서 레코드를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="af2aa-125">Go to [Add DNS records to connect your domain](create-dns-records-at-any-dns-hosting-provider.md), and follow the steps to add records at your DNS host's website.</span></span>

5. <span data-ttu-id="af2aa-126">DNS 호스트에서 레코드를 만들기 위한 단계를 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="af2aa-126">Follow the steps for creating the records at your DNS host.</span></span>

## <a name="related-content"></a><span data-ttu-id="af2aa-127">관련 콘텐츠</span><span class="sxs-lookup"><span data-stu-id="af2aa-127">Related content</span></span>

<span data-ttu-id="af2aa-128">[도메인 FAQ](../setup/domains-faq.yml)(문서)</span><span class="sxs-lookup"><span data-stu-id="af2aa-128">[Domains FAQ](../setup/domains-faq.yml) (article)</span></span>\
<span data-ttu-id="af2aa-129">[도메인 또는 DNS 레코드를 추가한 후 문제 찾기 및 수정](find-and-fix-issues.md)(문서)</span><span class="sxs-lookup"><span data-stu-id="af2aa-129">[Find and fix issues after adding your domain or DNS records](find-and-fix-issues.md) (article)</span></span>\
<span data-ttu-id="af2aa-130">[도메인 관리](index.yml)(링크 페이지)</span><span class="sxs-lookup"><span data-stu-id="af2aa-130">[Manage domains](index.yml) (link page)</span></span>