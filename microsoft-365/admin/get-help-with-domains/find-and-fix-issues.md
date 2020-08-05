---
title: 도메인 또는 DNS 레코드를 추가한 후 문제 찾기 및 해결
f1.keywords:
- NOCSH
ms.author: pebaum
author: pebaum
manager: mnirkhe
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
- Adm_O365_Setup
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
- GEA150
ms.assetid: 40398b0b-bdd0-4afd-ab5e-b5ae6b7990bf
description: DNS 레코드가 올바르게 설정 되어 있는지 확인 하 여 사용자 지정 도메인을 설정 하는 동안 실행 한 문제를 추적 하는 방법을 설명 합니다.
ms.openlocfilehash: 0a315be243395940146479e05de2c7044a5a36ab
ms.sourcegitcommit: d988faa292c2661ffea43c7161aef92b2b4b99bc
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/04/2020
ms.locfileid: "46560254"
---
# <a name="find-and-fix-issues-after-adding-your-domain-or-dns-records"></a><span data-ttu-id="b05e6-103">도메인 또는 DNS 레코드를 추가한 후 문제 찾기 및 해결</span><span class="sxs-lookup"><span data-stu-id="b05e6-103">Find and fix issues after adding your domain or DNS records</span></span>

 <span data-ttu-id="b05e6-104">원하는 정보를 찾지 못한 경우 **[도메인 FAQ를 확인](../setup/domains-faq.md)** 하세요.</span><span class="sxs-lookup"><span data-stu-id="b05e6-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="b05e6-105">도메인을 Microsoft 365에서 작동 하도록 설정 하는 것은 어려울 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b05e6-105">Getting your domain set up to work with Microsoft 365 can be challenging.</span></span> <span data-ttu-id="b05e6-106">DNS 시스템은 번거로우며, 도메인에 대한 DNS 설정은 전자 메일처럼 중요한 비즈니스 활동에 영향을 줍니다.</span><span class="sxs-lookup"><span data-stu-id="b05e6-106">The DNS system is nitpicky to work with, and the DNS setup for your domain affects important business activities, like email!</span></span>

> [!NOTE]
> <span data-ttu-id="b05e6-107">해당 상태를 확인 하 여 도메인에 문제가 있는지 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b05e6-107">You can check for problems with your domain by checking its status.</span></span> <span data-ttu-id="b05e6-108">**설치**  >  **도메인** 으로 이동 하 여 **상태** 열에서 알림을 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="b05e6-108">Go to **Setup** > **Domains** and view the notifications in the **Status** column.</span></span> <span data-ttu-id="b05e6-109">문제가 표시 되 면 추가 작업 (점 3 개)을 선택한 다음 **상태 확인**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="b05e6-109">If you see an issue, select More actions (three dots), and then choose **Check health**.</span></span> <span data-ttu-id="b05e6-110">열리는 창에는 도메인에서 발생 하는 문제에 대 한 설명이 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b05e6-110">The pane that opens will describe any issues occurring with your domain.</span></span>
  
## <a name="whats-going-on"></a><span data-ttu-id="b05e6-111">무슨 일이죠?</span><span class="sxs-lookup"><span data-stu-id="b05e6-111">What's going on?</span></span>

- [<span data-ttu-id="b05e6-112">도메인을 확인할 수 없습니까?</span><span class="sxs-lookup"><span data-stu-id="b05e6-112">Can't verify your domain?</span></span>](#cant-verify-your-domain)
    
- [<span data-ttu-id="b05e6-113">Outlook이 작동 하지 않습니까?</span><span class="sxs-lookup"><span data-stu-id="b05e6-113">Outlook isn't working?</span></span>](#outlook-isnt-working)
    
- [<span data-ttu-id="b05e6-114">모든 사용자의 전자 메일이 Microsoft 365로 전환 되었으며 전자 메일만 전환 하려고 했습니까?</span><span class="sxs-lookup"><span data-stu-id="b05e6-114">Everyone's email got switched to Microsoft 365 and you only wanted YOUR email to switch?</span></span>](#everyones-email-got-switched-to-microsoft-365-and-you-only-wanted-your-email-to-switch)

- [<span data-ttu-id="b05e6-115">비영리 또는 학교 계정 상태를 확인할 수 없습니까?</span><span class="sxs-lookup"><span data-stu-id="b05e6-115">Can't confirm non-profit or school account status?</span></span>](#cant-confirm-non-profit-or-school-account-status)

- [<span data-ttu-id="b05e6-116">도메인에서 서비스가 작동 하지 않습니까?</span><span class="sxs-lookup"><span data-stu-id="b05e6-116">Services not working with your domain?</span></span>](#services-not-working-with-your-domain)
    
- [<span data-ttu-id="b05e6-117">웹 사이트에 대 한 액세스가 작동 하지 않습니까?</span><span class="sxs-lookup"><span data-stu-id="b05e6-117">Accessing your website isn't working?</span></span>](#accessing-your-website-isnt-working)

## <a name="cant-verify-your-domain"></a><span data-ttu-id="b05e6-118">도메인을 확인할 수 없나요?</span><span class="sxs-lookup"><span data-stu-id="b05e6-118">Can't verify your domain?</span></span>
<span data-ttu-id="b05e6-119"><a name="BKMK_verify"> </a></span><span class="sxs-lookup"><span data-stu-id="b05e6-119"><a name="BKMK_verify"> </a></span></span>

<span data-ttu-id="b05e6-120">다음과 같이 몇 가지 일반적인 이유 때문에 도메인 확인이 예상대로 작동하지 않을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b05e6-120">There are a couple of common reasons that domain verification doesn't work as it should:</span></span>
  
1. <span data-ttu-id="b05e6-p103">**확인 레코드 값이 올바르지 않습니다.** 여러 번 확인하면서 DNS 호스트의 TXT 확인 레코드에 정확한 값을 복사하여 붙여넣으세요. 한 가지 일반적인 문제는 레코드의 "MS =" 부분을 포함하지 않는 경우입니다. 누락하지 않도록 주의하세요!</span><span class="sxs-lookup"><span data-stu-id="b05e6-p103">**The verification record value isn't quite correct.** Doublecheck that you've copied and pasted the exact value into the TXT verification record at your DNS host. One common issue is not including the "MS=" part of the record. We need that too!</span></span> 
    
2. <span data-ttu-id="b05e6-125">**레코드가 저장되지 않았습니다.**</span><span class="sxs-lookup"><span data-stu-id="b05e6-125">**The record hasn't been saved.**</span></span> <span data-ttu-id="b05e6-126">일부 DNS 호스트에서는 영역 파일(DNS 레코드가 저장되는 위치)이 인터넷을 통해 업데이트되도록 저장하는 추가 단계를 진행해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b05e6-126">At some DNS hosts, you have to take an extra step to save the zone file (where the DNS record is stored) so that it will update across the Internet.</span></span> <span data-ttu-id="b05e6-127">Microsoft 365에서 레코드를 보고 확인할 수 있도록 변경 내용을 저장 했는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="b05e6-127">Make sure you've saved your changes so Microsoft 365 can see and verify the record.</span></span> 
    
3. <span data-ttu-id="b05e6-128">**레코드가 인터넷에서 업데이트되지 않았습니다.**</span><span class="sxs-lookup"><span data-stu-id="b05e6-128">**The record hasn't updated across the Internet.**</span></span> <span data-ttu-id="b05e6-129">일반적으로 Microsoft에서 새 레코드를 확인하는 데 몇 분 정도면 되지만 경우에 따라 몇 시간이 걸릴 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b05e6-129">It typically only takes a few minutes for us to be able to see the new record, but occasionally it can take as long as a few hours.</span></span> 
    
## <a name="outlook-isnt-working"></a><span data-ttu-id="b05e6-130">Outlook이 작동하지 않나요?</span><span class="sxs-lookup"><span data-stu-id="b05e6-130">Outlook isn't working?</span></span>
<span data-ttu-id="b05e6-131"><a name="BKMK_OutlookBroken"> </a></span><span class="sxs-lookup"><span data-stu-id="b05e6-131"><a name="BKMK_OutlookBroken"> </a></span></span>

<span data-ttu-id="b05e6-132">도메인에 대해 MX 레코드 및 기타 DNS 레코드를 올바르게 설정했으나 메일이 작동하지 않는 경우 [Outlook 문제 해결](https://docs.microsoft.com/exchange/troubleshoot/outlook-connectivity/outlook-connection-issues)을 도와드리겠습니다.</span><span class="sxs-lookup"><span data-stu-id="b05e6-132">If you've set up your MX record and other DNS records correctly for your domain, but mail doesn't work, let us help you [fix your Outlook problems](https://docs.microsoft.com/exchange/troubleshoot/outlook-connectivity/outlook-connection-issues).</span></span>
  
## <a name="everyones-email-got-switched-to-microsoft-365-and-you-only-wanted-your-email-to-switch"></a><span data-ttu-id="b05e6-133">모든 사용자의 전자 메일이 Microsoft 365로 전환 되었으며 전자 메일만 전환 하려고 했습니까?</span><span class="sxs-lookup"><span data-stu-id="b05e6-133">Everyone's email got switched to Microsoft 365 and you only wanted YOUR email to switch?</span></span>
<span data-ttu-id="b05e6-134"><a name="BKMK_EmailSwitched"> </a></span><span class="sxs-lookup"><span data-stu-id="b05e6-134"><a name="BKMK_EmailSwitched"> </a></span></span>

<span data-ttu-id="b05e6-135">Microsoft 365에 도메인을 추가 하면 일반적으로 Microsoft 365을 가리키도록 도메인의 MX 레코드가 365 업데이트 되 고, 해당 도메인으로 전송 된 모든 전자 메일은 Microsoft 365로 시작 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b05e6-135">When you add your domain to Microsoft 365, typically your domain's MX record is updated (by you or Microsoft 365) to point to Microsoft 365, and ALL email sent to that domain will start coming to Microsoft 365.</span></span> <span data-ttu-id="b05e6-136">MX 레코드를 변경 하기 전에 도메인에 전자 메일이 있는 모든 사용자에 대해 Microsoft 365에서 사서함을 만들었는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="b05e6-136">Make sure you've created mailboxes in Microsoft 365 for everyone who has email on your domain BEFORE you change the MX record.</span></span>
  
<span data-ttu-id="b05e6-137">도메인의 모든 사용자에 대 한 전자 메일을 Microsoft 365로 이동 하지 않을 경우 어떻게 하나요?</span><span class="sxs-lookup"><span data-stu-id="b05e6-137">What if you don't want to move email for everyone on your domain to Microsoft 365?</span></span> <span data-ttu-id="b05e6-138">[대신 몇 개의 전자 메일 주소만 사용 하 여 Microsoft 365를 파일럿 하는](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq)단계를 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b05e6-138">You can take steps to [pilot Microsoft 365 with just a few email addresses instead](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq).</span></span>
  
## <a name="cant-confirm-non-profit-or-school-account-status"></a><span data-ttu-id="b05e6-139">비영리 또는 학교 계정 상태를 확인할 수 없습니까?</span><span class="sxs-lookup"><span data-stu-id="b05e6-139">Can't confirm non-profit or school account status?</span></span>
<span data-ttu-id="b05e6-140"><a name="BKMK_validateAcct"> </a></span><span class="sxs-lookup"><span data-stu-id="b05e6-140"><a name="BKMK_validateAcct"> </a></span></span>

<span data-ttu-id="b05e6-141">조직의 도메인을 확인 하 고 서비스를 설정 하지 않은 경우를 비롯 한 몇 가지 시나리오가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b05e6-141">There are a couple of scenarios when you just need to verify your organization's domain and not set up any services.</span></span> <span data-ttu-id="b05e6-142">예를 들어 조직에 학교 구독에 대 한 자격을 부여할 수 있도록 Microsoft 365를 입증 합니다.</span><span class="sxs-lookup"><span data-stu-id="b05e6-142">For example, to prove to Microsoft 365 that your organization qualifies for a school subscription.</span></span>
  
<span data-ttu-id="b05e6-143">[Microsoft 365 도메인에서 소유권, 비영리 또는 교육 상태를 증명 하거나 Yammer를 활성화](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq) 하 여 필요한 모든 단계를 완료 했는지 확인의 지침을 확인 하세요.</span><span class="sxs-lookup"><span data-stu-id="b05e6-143">Check out the guidance in [Verify your Microsoft 365 domain to prove ownership, nonprofit or education status, or to activate Yammer](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq) to make sure you've completed all the required steps.</span></span> <span data-ttu-id="b05e6-144">각 상황에서 다소 차이가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b05e6-144">It's a little different for each situation.</span></span> 
  
## <a name="services-not-working-with-your-domain"></a><span data-ttu-id="b05e6-145">도메인에서 서비스가 작동하지 않나요?</span><span class="sxs-lookup"><span data-stu-id="b05e6-145">Services not working with your domain?</span></span>
<span data-ttu-id="b05e6-146"><a name="BKMK_Test"> </a></span><span class="sxs-lookup"><span data-stu-id="b05e6-146"><a name="BKMK_Test"> </a></span></span>

<span data-ttu-id="b05e6-147">Microsoft에서는 도메인의 DNS 설정 문제를 해결할 수 있도록 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="b05e6-147">We can help you track down issues with your domain's DNS setup.</span></span> <span data-ttu-id="b05e6-148">Microsoft 365의 도메인 문제 해결사는 문제를 해결 해야 하는 레코드와 레코드를 설정 해야 하는 항목을 정확히 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="b05e6-148">The domains troubleshooter in Microsoft 365 will show you any records that need fixing, and exactly what the records need to be set to.</span></span> 

> [!TIP]
> <span data-ttu-id="b05e6-149">DNS를 올바르게 설정했지만 데스크톱의 Outlook에서 메일이 작동하지 않나요?</span><span class="sxs-lookup"><span data-stu-id="b05e6-149">Got your DNS set up correctly, but mail doesn't work in Outlook on your desktop?</span></span> <span data-ttu-id="b05e6-150">[Microsoft 365와 함께 제공 될 수 있는 다른 메일 흐름 시나리오](https://docs.microsoft.com/exchange/mail-flow-best-practices/mail-flow-best-practices) 를 확인 하 여 비즈니스에 맞게 올바르게 설정 되었는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="b05e6-150">Check out the [different mail flow scenarios you can have with Microsoft 365](https://docs.microsoft.com/exchange/mail-flow-best-practices/mail-flow-best-practices) to make sure you've got things set up correctly for your business.</span></span> <span data-ttu-id="b05e6-151">또는 전자 메일과 관련된 추가 문제 해결 도움말을 [Outlook 문제 해결](https://docs.microsoft.com/exchange/troubleshoot/outlook-connectivity/outlook-connection-issues)에서 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="b05e6-151">Or get more troubleshooting help with email here: [Fix Outlook problems](https://docs.microsoft.com/exchange/troubleshoot/outlook-connectivity/outlook-connection-issues).</span></span> 
  
## <a name="accessing-your-website-isnt-working"></a><span data-ttu-id="b05e6-152">웹 사이트에 액세스할 수 없나요?</span><span class="sxs-lookup"><span data-stu-id="b05e6-152">Accessing your website isn't working?</span></span>
<span data-ttu-id="b05e6-153"><a name="BKMK_Website"> </a></span><span class="sxs-lookup"><span data-stu-id="b05e6-153"><a name="BKMK_Website"> </a></span></span>

<span data-ttu-id="b05e6-154">DNS 문제를 해결한 경우에도 여전히 문제가 있는 경우 다음 방법 중 하나를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="b05e6-154">If you've fixed any DNS issues and you're still having trouble, try one of the following.</span></span>
  
- <span data-ttu-id="b05e6-155">다른 사용자가 www.mydomain.com의 내 웹 사이트에 연결할 수 없는 경우: [웹 사이트 문제 추적](https://docs.microsoft.com/microsoft-365/admin/setup/add-domain)</span><span class="sxs-lookup"><span data-stu-id="b05e6-155">People can't get to your website at www.mydomain.com: [Track down website issues](https://docs.microsoft.com/microsoft-365/admin/setup/add-domain)</span></span>
    
- <span data-ttu-id="b05e6-156">웹 사이트를 가리키도록 A 레코드 또는 CNAME 레코드를 업데이트할 수 없음: [Microsoft 365에서 사용자 지정 DNS 레코드 업데이트](../dns/add-or-edit-custom-dns-records.md)</span><span class="sxs-lookup"><span data-stu-id="b05e6-156">You can't update your A record or CNAME record to point to your website: [Update custom DNS records in Microsoft 365](../dns/add-or-edit-custom-dns-records.md)</span></span>
    
