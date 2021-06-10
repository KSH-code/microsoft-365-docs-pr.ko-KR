---
title: DNS 레코드를 업데이트하여 현재 호스팅 공급자에 웹 사이트 유지
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
- Adm_NonTOC
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
- GEA150
ms.assetid: 2c4cf347-b897-45c1-a71f-210bdc8f1061
description: 사용자 지정 도메인에 대한 DNS 레코드를 관리하기 위해 Microsoft를 설정한 경우 트래픽을 Microsoft 외부에 호스트된 기존 공개 웹 사이트로 라우팅하는 방법을 학습합니다.
ms.openlocfilehash: 2a1559bbb902375bbc363180cdb4f98ec2b3a939
ms.sourcegitcommit: 0936f075a1205b8f8a71a7dd7761a2e2ce6167b3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/19/2021
ms.locfileid: "52572144"
---
# <a name="update-dns-records-to-keep-your-website-with-your-current-hosting-provider"></a><span data-ttu-id="2d76e-103">DNS 레코드를 업데이트하여 현재 호스팅 공급자에 웹 사이트 유지</span><span class="sxs-lookup"><span data-stu-id="2d76e-103">Update DNS records to keep your website with your current hosting provider</span></span>

 <span data-ttu-id="2d76e-104">**DNS 호스팅 공급자에서 도메인의 Microsoft** 레코드를 관리하는 경우 이 항목의 단계에 대해 걱정할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="2d76e-104">**If you manage your domain's Microsoft records at your DNS hosting provider**, you don't have to worry about the steps in this topic.</span></span> <span data-ttu-id="2d76e-105">웹 사이트 위치가 그대로 유지되며 사용자가 계속해서 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2d76e-105">Your website stays where it is and people can still get to it.</span></span> 
  
 <span data-ttu-id="2d76e-106">**Microsoft에서 DNS** 레코드 를 관리하는 경우 Microsoft 외부에 호스트된 기존 공개 웹 사이트로 트래픽을 라우팅하려면 Microsoft에 도메인을 추가한 후 다음을 합니다.</span><span class="sxs-lookup"><span data-stu-id="2d76e-106">**If Microsoft manages your DNS records**, to route traffic to an existing public website hosted outside of Microsoft, after you add your domain to Microsoft, do the following:</span></span> 
  
## <a name="update-dns-records-in-the-microsoft-365-admin-center"></a><span data-ttu-id="2d76e-107">Microsoft 365 관리 센터에서 DNS 레코드 업데이트</span><span class="sxs-lookup"><span data-stu-id="2d76e-107">Update DNS records in the Microsoft 365 admin center</span></span>
1. <span data-ttu-id="2d76e-108">I관리 센터에서 **설정** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank"> 도메인</a> 페이지로 이동하십시오.</span><span class="sxs-lookup"><span data-stu-id="2d76e-108">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

1. <span data-ttu-id="2d76e-109">On the **Domains** page, select the domain and then choose **DNS Records**.</span><span class="sxs-lookup"><span data-stu-id="2d76e-109">On the **Domains** page, select the domain and then choose **DNS Records**.</span></span>

1. <span data-ttu-id="2d76e-110">**+ 레코드 추가를 선택하고** 다음을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="2d76e-110">Select **+ Add record** and enter the following:</span></span> 
    
   - <span data-ttu-id="2d76e-111">형식 **입력:** **A(주소)**</span><span class="sxs-lookup"><span data-stu-id="2d76e-111">For **type** enter: **A (Address)**</span></span>
    
   - <span data-ttu-id="2d76e-112">**호스트 이름 또는 별칭** 에는 **@** 을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="2d76e-112">For **Host name or Alias**, type the following: **@**</span></span>
    
   - <span data-ttu-id="2d76e-113">**IP 주소** 에는 현재 호스팅되는 웹 사이트의 고정 IP 주소를 입력합니다(예: 172.16.140.1).</span><span class="sxs-lookup"><span data-stu-id="2d76e-113">For **IP Address**, type the static IP address for your website where it's currently hosted (for example, 172.16.140.1).</span></span> 
    
   <span data-ttu-id="2d76e-p102">이 IP 주소는  *동적*  IP 주소가 아니라 웹 사이트의  *고정*  IP 주소여야 합니다. 웹 사이트가 호스트되는 사이트에서 공개 웹 사이트의 고정 IP 주소를 가져올 수 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="2d76e-p102">This must be a  *static*  IP address for the website, not a  *dynamic*  IP address. Check with site where your website is hosted to make sure you can get a static IP address for your public website.</span></span> 
    
1. <span data-ttu-id="2d76e-116">**저장** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="2d76e-116">Select **Save**.</span></span> 
    
<span data-ttu-id="2d76e-117">추가로, 고객이 쉽게 사용자의 웹 사이트를 찾을 수 있도록 CNAME 레코드를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2d76e-117">In addition, you can create a CNAME record to help customers find your website.</span></span>
  
1. <span data-ttu-id="2d76e-118">**+ 레코드 추가를 선택하고** 다음을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="2d76e-118">Select **+ Add record** and enter the following:</span></span> 
    
   - <span data-ttu-id="2d76e-119">형식 **입력:** **CNAME(별칭)**</span><span class="sxs-lookup"><span data-stu-id="2d76e-119">For **type** enter: **CNAME (Alias)**</span></span>
    
   - <span data-ttu-id="2d76e-120">**호스트 이름 또는 별칭** 에는 **www** 를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="2d76e-120">For **Host name or Alias**, type the following: **www**</span></span>
    
   - <span data-ttu-id="2d76e-121">**대상 주소** 에 웹 사이트의 FQDN(정규화된 도메인 이름)을 contoso.com과 같이 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="2d76e-121">For **Points to address**, type the fully qualified domain name (FQDN) for your website (for example, contoso.com).</span></span> 
    
2. <span data-ttu-id="2d76e-122">**저장** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="2d76e-122">Select **Save**.</span></span> 
    
<span data-ttu-id="2d76e-123">끝으로 다음을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="2d76e-123">Finally, do the following:</span></span>
  
<span data-ttu-id="2d76e-124">[Microsoft를 지점으로 도메인의 NS](../get-help-with-domains/set-up-your-domain-host-specific-instructions.md) 레코드를 업데이트합니다.</span><span class="sxs-lookup"><span data-stu-id="2d76e-124">[Update your domain's NS records](../get-help-with-domains/set-up-your-domain-host-specific-instructions.md) to point to Microsoft.</span></span> 
  
<span data-ttu-id="2d76e-125">NS 레코드가 Microsoft를 지점으로 업데이트하면 도메인이 모두 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="2d76e-125">When the NS records have been updated to point to Microsoft, your domain is all set up.</span></span> <span data-ttu-id="2d76e-126">전자 메일이 Microsoft로 라우팅되고, 웹 사이트 주소에 대한 트래픽이 현재 웹 사이트 호스트로 계속 이동됩니다.</span><span class="sxs-lookup"><span data-stu-id="2d76e-126">Email will be routed to Microsoft, and traffic to your website address will continue to go to your current website host.</span></span>
