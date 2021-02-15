---
title: AWS(Amazon Web Services)에서 이름 서버 변경
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
- Adm_O365_Setup
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 0ddbe33c-81ea-4c02-8db9-e71d3810c0ec
description: 'AWS(Amazon Web Services)에서 DNS 레코드를 관리하기 위해 Microsoft를 설정하는 방법을 알아보십시오. '
ms.openlocfilehash: 4700557c40973ab051cced81c129197a826964ab
ms.sourcegitcommit: 0a8b0186cc041db7341e57f375d0d010b7682b7d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/11/2020
ms.locfileid: "49658455"
---
# <a name="change-nameservers-to-set-up-microsoft-with-amazon-web-services-aws"></a><span data-ttu-id="f91e7-103">AWS(Amazon Web Services)에서 이름 서버 변경</span><span class="sxs-lookup"><span data-stu-id="f91e7-103">Change nameservers to set up Microsoft with Amazon Web Services (AWS)</span></span>

 <span data-ttu-id="f91e7-104">원하는 정보를 찾지 못한 경우 **[도메인 FAQ를 확인](../setup/domains-faq.yml)** 하세요.</span><span class="sxs-lookup"><span data-stu-id="f91e7-104">**[Check the Domains FAQ](../setup/domains-faq.yml)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="f91e7-105">Microsoft에서 DNS 레코드를 관리하게 하려는 경우 다음 지침을 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="f91e7-105">Follow these instructions if you want Microsoft to manage your DNS records for you.</span></span> <span data-ttu-id="f91e7-106">원하는 경우 [AWS에서 모든 Microsoft DNS 레코드를 관리할 수](create-dns-records-at-aws.md)있습니다.</span><span class="sxs-lookup"><span data-stu-id="f91e7-106">(If you prefer, you can [manage all your Microsoft DNS records at AWS](create-dns-records-at-aws.md).)</span></span>
  
    
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="f91e7-107">확인을 위해 TXT 레코드 추가</span><span class="sxs-lookup"><span data-stu-id="f91e7-107">Add a TXT record for verification</span></span>

<span data-ttu-id="f91e7-p102">Microsoft에서 사용자 도메인을 사용하려면 먼저 도메인을 소유하고 있어야 합니다. 도메인 등록 기관에서 사용자의 계정으로 로그인하고 DNS 레코드를 만들 수 있으면 Microsoft에 도메인을 소유하고 있음을 증명할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f91e7-p102">Before you use your domain with Microsoft, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Microsoft that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="f91e7-p103">이 레코드는 사용자가 도메인을 소유하고 있는지 확인하는 데만 사용되며 그 밖에 아무런 영향도 주지 않습니다. 원하는 경우 나중에 삭제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f91e7-p103">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
1. <span data-ttu-id="f91e7-p104">시작하려면 [이 링크](https://console.aws.amazon.com/route53/home)를 사용하여 AWS의 도메인 페이지로 이동합니다. 먼저 로그인하라는 메시지가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="f91e7-p104">To get started, go to your domains page at AWS by using [this link](https://console.aws.amazon.com/route53/home). You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="f91e7-114">리소스 **페이지에서** 호스팅된 **영역 선택**</span><span class="sxs-lookup"><span data-stu-id="f91e7-114">On the **Resources** page, select **Hosted Zones**.</span></span>
    
3. <span data-ttu-id="f91e7-115">호스팅된 **영역** 페이지의 도메인 **이름** 열에서 편집할 도메인의 이름을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="f91e7-115">On the **Hosted Zones** page, in the **Domain Name** column, select the name of the domain that you want to edit.</span></span> 
    
4. <span data-ttu-id="f91e7-116">레코드 **집합 만들기를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="f91e7-116">Select **Create Record Set**.</span></span>
    
5. <span data-ttu-id="f91e7-117">In the **Create Record Set** area, in the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="f91e7-117">In the **Create Record Set** area, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="f91e7-118">(Choose the **Type** and **Routing Policy** values from the drop-down lists.)</span><span class="sxs-lookup"><span data-stu-id="f91e7-118">(Choose the **Type** and **Routing Policy** values from the drop-down lists.)</span></span> 
    
    > [!TIP]
    > <span data-ttu-id="f91e7-p105">The quotation marks required by the onscreen instructions are supplied automatically. You don't need to type them manually.</span><span class="sxs-lookup"><span data-stu-id="f91e7-p105">The quotation marks required by the onscreen instructions are supplied automatically. You don't need to type them manually.</span></span> 
  
|||||||
|:-----|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="f91e7-121">**이름**</span><span class="sxs-lookup"><span data-stu-id="f91e7-121">**Name**</span></span> <br/> |<span data-ttu-id="f91e7-122">**Type(종류)**</span><span class="sxs-lookup"><span data-stu-id="f91e7-122">**Type**</span></span> <br/> |<span data-ttu-id="f91e7-123">**별칭**</span><span class="sxs-lookup"><span data-stu-id="f91e7-123">**Alias**</span></span> <br/> |<span data-ttu-id="f91e7-124">**TTL(초)**</span><span class="sxs-lookup"><span data-stu-id="f91e7-124">**TTL (Seconds)**</span></span> <br/> |<span data-ttu-id="f91e7-125">**값**</span><span class="sxs-lookup"><span data-stu-id="f91e7-125">**Value**</span></span> <br/> |<span data-ttu-id="f91e7-126">**라우팅 정책**</span><span class="sxs-lookup"><span data-stu-id="f91e7-126">**Routing Policy**</span></span> <br/> |
|<span data-ttu-id="f91e7-127">(이 필드는 비워 두기)</span><span class="sxs-lookup"><span data-stu-id="f91e7-127">(Leave this field empty)</span></span>  <br/> |<span data-ttu-id="f91e7-128">TXT - Text</span><span class="sxs-lookup"><span data-stu-id="f91e7-128">TXT - Text</span></span>  <br/> |<span data-ttu-id="f91e7-129">아니요</span><span class="sxs-lookup"><span data-stu-id="f91e7-129">No</span></span>  <br/> |<span data-ttu-id="f91e7-130">300</span><span class="sxs-lookup"><span data-stu-id="f91e7-130">300</span></span>  <br/> |<span data-ttu-id="f91e7-131">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="f91e7-131">MS=ms *XXXXXXXX*</span></span> <br/> <span data-ttu-id="f91e7-132">**참고:** 이 값은 예시입니다.</span><span class="sxs-lookup"><span data-stu-id="f91e7-132">**Note:** This is an example.</span></span> <span data-ttu-id="f91e7-133">여기에는 표에 있는 특정 **대상 또는 주소 가리키기** 값을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="f91e7-133">Use your specific **Destination or Points to Address** value here, from the table.</span></span> [<span data-ttu-id="f91e7-134">이 값을 찾는 방법</span><span class="sxs-lookup"><span data-stu-id="f91e7-134">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)  <br/>  |<span data-ttu-id="f91e7-135">Simple(단순형)</span><span class="sxs-lookup"><span data-stu-id="f91e7-135">Simple</span></span> <br/> |
   
6. <span data-ttu-id="f91e7-136">**만들기** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="f91e7-136">Select **Create**.</span></span>
    
7. <span data-ttu-id="f91e7-137">방금 만든 레코드가 인터넷에서 업데이트될 수 있도록 몇 분 정도 기다립니다.</span><span class="sxs-lookup"><span data-stu-id="f91e7-137">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="f91e7-138">이제 도메인 등록 기관의 사이트에 레코드를 추가한 후 Microsoft로 돌아가서 레코드에 대한 검색을 요청합니다.</span><span class="sxs-lookup"><span data-stu-id="f91e7-138">Now that you've added the record at your domain registrar's site, you'll go back to Microsoft and request a search for the record.</span></span>
  
<span data-ttu-id="f91e7-139">Microsoft에서 올바른 TXT 레코드를 찾으면 도메인이 확인된 것입니다.</span><span class="sxs-lookup"><span data-stu-id="f91e7-139">When Microsoft finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="f91e7-140">Microsoft 관리 센터에서 **설정** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">도메인</a> 페이지로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="f91e7-140">In the Microsoft admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

    
2. <span data-ttu-id="f91e7-141">**도메인** 페이지에서 확인 중인 도메인을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="f91e7-141">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
3. <span data-ttu-id="f91e7-142">**설정** 페이지에서 **설정 시작** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="f91e7-142">On the **Setup** page, select **Start setup**.</span></span>
    
4. <span data-ttu-id="f91e7-143">**도메인 확인** 페이지에서 **확인** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="f91e7-143">On the **Verify domain** page, select **Verify**.</span></span>
    
> [!NOTE]
> <span data-ttu-id="f91e7-144">Typically it takes about 15 minutes for DNS changes to take effect.</span><span class="sxs-lookup"><span data-stu-id="f91e7-144">Typically it takes about 15 minutes for DNS changes to take effect.</span></span> <span data-ttu-id="f91e7-145">그러나 변경한 내용이 인터넷의 DNS 시스템 전체에 업데이트되는 데에는 시간이 오래 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f91e7-145">However, it can occasionally take longer for a change you've made to update across the Internet's DNS system.</span></span> <span data-ttu-id="f91e7-146">DNS 레코드를 추가한 후 메일 흐름 또는 기타 문제가 발생하는 경우 [도메인 또는 DNS 레코드를 추가한 후 문제 찾기 및 해결하기](../get-help-with-domains/find-and-fix-issues.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="f91e7-146">If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="change-your-domains-nameserver-ns-records"></a><span data-ttu-id="f91e7-147">도메인의 NS(이름 서버) 레코드 변경</span><span class="sxs-lookup"><span data-stu-id="f91e7-147">Change your domain's nameserver (NS) records</span></span>

<span data-ttu-id="f91e7-148">Microsoft에서 도메인 설정을 완료하려면 도메인 등록 기관에서 Microsoft 기본 및 보조 이름 서버를 지점으로 도메인의 NS 레코드를 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="f91e7-148">To complete setting up your domain with Microsoft, you change your domain's NS records at your domain registrar to point to the Microsoft primary and secondary name servers.</span></span> <span data-ttu-id="f91e7-149">이렇게 하면 도메인의 DNS 레코드가 자동으로 업데이트됩니다.</span><span class="sxs-lookup"><span data-stu-id="f91e7-149">This sets up Microsoft to update the domain's DNS records for you.</span></span> <span data-ttu-id="f91e7-150">전자 메일, 비즈니스용 Skype Online, 공개 웹 사이트가 사용자의 도메인을 사용하도록 모든 레코드가 자동으로 추가되고 모든 설정이 완료됩니다.</span><span class="sxs-lookup"><span data-stu-id="f91e7-150">We'll add all records so that email, Skype for Business Online, and your public website work with your domain, and you'll be all set.</span></span>
  
> [!CAUTION]
> <span data-ttu-id="f91e7-151">Microsoft 이름 서버를 설정하기 위해 도메인의 NS 레코드를 변경하면 현재 도메인과 연결된 모든 서비스가 영향을 받는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="f91e7-151">When you change your domain's NS records to point to the Microsoft name servers, all the services that are currently associated with your domain are affected.</span></span> <span data-ttu-id="f91e7-152">예를 들어 도메인으로 전송된 모든 전자 메일(예: rob@ *your_domain*  .com)은 이 변경 후에 Microsoft로 전송됩니다.</span><span class="sxs-lookup"><span data-stu-id="f91e7-152">For example, all email sent to your domain (like rob@ *your_domain*  .com) will start coming to Microsoft after you make this change.</span></span> 
  
> [!IMPORTANT]
>  <span data-ttu-id="f91e7-153">다음 절차에서는 목록에서 원치 않는 다른 이름 서스터를 삭제하는 방법과 올바른 이름servers가 목록에 없는 경우 추가하는 방법도 보여 주며,</span><span class="sxs-lookup"><span data-stu-id="f91e7-153">The following procedure will show you how to delete any other, unwanted nameservers from the list, and also how to add the correct nameservers if they are not already listed.</span></span> <span data-ttu-id="f91e7-154">> 이 섹션의 단계를 완료하면 다음 네 가지 이름만 나열됩니다. > ns1.bdm.microsoftonline.com > ns2.bdm.microsoftonline.com > ns3.bdm.microsoftonline.com > ns4.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="f91e7-154">>  When you have completed the steps in this section, the only nameservers that should be listed are these four: >  ns1.bdm.microsoftonline.com >  ns2.bdm.microsoftonline.com >  ns3.bdm.microsoftonline.com >  ns4.bdm.microsoftonline.com</span></span> 
  
1. <span data-ttu-id="f91e7-155">시작하려면 [이 링크](https://console.aws.amazon.com/route53/home)를 사용하여 AWS의 도메인 페이지로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="f91e7-155">To get started, go to your domains page at AWS by using [this link](https://console.aws.amazon.com/route53/home).</span></span> <span data-ttu-id="f91e7-156">먼저 로그인하라는 메시지가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="f91e7-156">You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="f91e7-157">리소스 **페이지에서** 호스팅된 **영역 선택**</span><span class="sxs-lookup"><span data-stu-id="f91e7-157">On the **Resources** page, select **Hosted Zones**.</span></span>
    
3. <span data-ttu-id="f91e7-158">호스팅된 **영역** 페이지의 도메인 **이름** 열에서 편집할 도메인의 이름을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="f91e7-158">On the **Hosted Zones** page, in the **Domain Name** column, select the name of the domain that you want to edit.</span></span> 
    
4. <span data-ttu-id="f91e7-159">**이름 서버** 레코드 집합을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="f91e7-159">Select the **Nameserver** record set.</span></span> 
    
    ![Select the recordset](../../media/24e618e4-0a16-43a2-9886-f4f5dac79374.png)
  
5. <span data-ttu-id="f91e7-161">**NS - Name server(NS - 이름 서버)** 레코드 집합의 **Value(값)** 상자에서 모든 이름 서버를 선택한 다음 키보드의 **Delete** 키를 눌러 모든 이름 서버를 삭제합니다.</span><span class="sxs-lookup"><span data-stu-id="f91e7-161">In the **NS - Name server** record set in the **Value** box, delete all of the nameservers by selecting them all and then pressing the **Delete** key on your keyboard.</span></span> 
    
    > [!CAUTION]
    > <span data-ttu-id="f91e7-162">Follow these steps only if you have existing nameservers other than the four correct nameservers.</span><span class="sxs-lookup"><span data-stu-id="f91e7-162">Follow these steps only if you have existing nameservers other than the four correct nameservers.</span></span> <span data-ttu-id="f91e7-163">즉, 이름이 **ns1.bdm.microsoftonline.com,** ns2.bdm.microsoftonline.com, ns3.bdm.microsoftonline.com  또는 ns4.bdm.microsoftonline.com **이름** 없는 모든 현재 이름 ns4.bdm.microsoftonline.com 삭제합니다.</span><span class="sxs-lookup"><span data-stu-id="f91e7-163">(That is, delete only any current nameservers that are  *not*  named **ns1.bdm.microsoftonline.com**, **ns2.bdm.microsoftonline.com**, **ns3.bdm.microsoftonline.com**, or **ns4.bdm.microsoftonline.com**.)</span></span> 
  
    ![Select and delete all of the nameservers in the Value box](../../media/ecf1e897-fa7d-4abc-b00b-bf55b8ed2139.png)
  
6. <span data-ttu-id="f91e7-165">**TTL(초):** 영역에서 **1h(1시간)를** 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="f91e7-165">In the **TTL (Seconds):** area, select **1h** (1 Hour).</span></span> 
    
    ![1시간 동안 1H 선택](../../media/c70070e1-4bde-41a7-b271-9d22c475edf6.png)
  
7. <span data-ttu-id="f91e7-167">계속해서 **NS - Name server**(NS - 이름 서버) 레코드 집합의 **Value**(값) 상자에 다음 표의 **First line**(첫 줄)에 있는 값을 입력하거나 복사하여 붙여넣고 키보드의 **Enter** 키를 누른 후 다음 **line**(줄)에 있는 값을 입력하거나 복사하여 붙여넣습니다.</span><span class="sxs-lookup"><span data-stu-id="f91e7-167">Still in the **NS - Name server** record set, in the **Value** box, type or copy and paste the **First line** value from the following table, then press the **Enter** key on your keyboard and type or copy and paste the next **line** value.</span></span> 
    
    > [!IMPORTANT]
    > <span data-ttu-id="f91e7-168">이름 서버 값은 다음 그림과 같이 *Value(값)* 상자 안의 각기 다른 줄에  **있어야 합니다**  .</span><span class="sxs-lookup"><span data-stu-id="f91e7-168">Each nameserver value  *must*  be on its own separate line within the **Value** box, as shown in the following illustration.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="f91e7-169">**첫 줄**</span><span class="sxs-lookup"><span data-stu-id="f91e7-169">**First line**</span></span> <br/> |<span data-ttu-id="f91e7-170">ns1.bdm.microsoftonline.com.</span><span class="sxs-lookup"><span data-stu-id="f91e7-170">ns1.bdm.microsoftonline.com.</span></span>  <br/> <span data-ttu-id="f91e7-171">**이 값은 마침표(.)로 끝나야 합니다.**</span><span class="sxs-lookup"><span data-stu-id="f91e7-171">**This value MUST end with a period (.)**</span></span> <br/> |
|<span data-ttu-id="f91e7-172">**둘째 줄**</span><span class="sxs-lookup"><span data-stu-id="f91e7-172">**Second line**</span></span> <br/> |<span data-ttu-id="f91e7-173">ns2.bdm.microsoftonline.com.</span><span class="sxs-lookup"><span data-stu-id="f91e7-173">ns2.bdm.microsoftonline.com.</span></span>  <br/> <span data-ttu-id="f91e7-174">**이 값은 마침표(.)로 끝나야 합니다.**</span><span class="sxs-lookup"><span data-stu-id="f91e7-174">**This value MUST end with a period (.)**</span></span> <br/> |
|<span data-ttu-id="f91e7-175">**셋째 줄**</span><span class="sxs-lookup"><span data-stu-id="f91e7-175">**Third line**</span></span> <br/> |<span data-ttu-id="f91e7-176">ns3.bdm.microsoftonline.com.</span><span class="sxs-lookup"><span data-stu-id="f91e7-176">ns3.bdm.microsoftonline.com.</span></span>  <br/> <span data-ttu-id="f91e7-177">**이 값은 마침표(.)로 끝나야 합니다.**</span><span class="sxs-lookup"><span data-stu-id="f91e7-177">**This value MUST end with a period (.)**</span></span> <br/> |
|<span data-ttu-id="f91e7-178">**넷째 줄**</span><span class="sxs-lookup"><span data-stu-id="f91e7-178">**Fourth line**</span></span> <br/> |<span data-ttu-id="f91e7-179">ns4.bdm.microsoftonline.com.</span><span class="sxs-lookup"><span data-stu-id="f91e7-179">ns4.bdm.microsoftonline.com.</span></span>  <br/> <span data-ttu-id="f91e7-180">**이 값은 마침표(.)로 끝나야 합니다.**</span><span class="sxs-lookup"><span data-stu-id="f91e7-180">**This value MUST end with a period (.)**</span></span> <br/> |
   
   ![값 상자에 첫 줄 값을 입력하거나 붙여넣습니다.](../../media/b63f41e0-51ef-4ab2-a4b8-ee7380e5ab35.png)
  
8. <span data-ttu-id="f91e7-182">레코드 **저장 집합을 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="f91e7-182">Select **Save Record Set**.</span></span>
    
    ![레코드 저장 집합 선택](../../media/ab3c0558-bb7c-41e4-871e-ea82f1553476.png)
  
> [!NOTE]
> <span data-ttu-id="f91e7-184">Your nameserver record updates may take up to several hours to update across the Internet's DNS system.</span><span class="sxs-lookup"><span data-stu-id="f91e7-184">Your nameserver record updates may take up to several hours to update across the Internet's DNS system.</span></span> <span data-ttu-id="f91e7-185">그런 다음 Microsoft 전자 메일 및 기타 서비스가 모두 도메인에서 작동하게 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="f91e7-185">Then your Microsoft email and other services will be all set to work with your domain.</span></span> 
