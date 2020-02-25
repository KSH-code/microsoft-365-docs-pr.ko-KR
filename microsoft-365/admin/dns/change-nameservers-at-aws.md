---
title: AWS(Amazon Web Services)에서 이름 서버를 변경하여 Office 365 설정
f1.keywords:
- NOCSH
ms.author: pebaum
author: pebaum
manager: mnirkhe
audience: Admin
ms.topic: get-started-article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_NonTOC
- Adm_O365_Setup
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 0ddbe33c-81ea-4c02-8db9-e71d3810c0ec
description: 'AWS (Amazon Web Services)에서 DNS 레코드를 관리 하기 위해 Office 365을 설정 하는 방법을 알아봅니다. '
ms.openlocfilehash: 08deba83738ba0e530e719cd6fd57bee423df5e0
ms.sourcegitcommit: ca2b58ef8f5be24f09e73620b74a1ffcf2d4c290
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/24/2020
ms.locfileid: "42246763"
---
# <a name="change-nameservers-to-set-up-office-365-with-amazon-web-services-aws"></a><span data-ttu-id="0671d-103">AWS(Amazon Web Services)에서 이름 서버를 변경하여 Office 365 설정</span><span class="sxs-lookup"><span data-stu-id="0671d-103">Change nameservers to set up Office 365 with Amazon Web Services (AWS)</span></span>

 <span data-ttu-id="0671d-104">**원하는 정보는 찾지 못한 경우 [도메인 질문과 대답을 확인](../setup/domains-faq.md)** 하세요.</span><span class="sxs-lookup"><span data-stu-id="0671d-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="0671d-p101">Office 365에서 Office 365 DNS 레코드를 관리하려는 경우 다음 지침을 따릅니다. 원하는 경우 [모든 Office 365 DNS 레코드를 AWS에서 관리](create-dns-records-at-aws.md)할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0671d-p101">Follow these instructions if you want Office 365 to manage your Office 365 DNS records for you. (If you prefer, you can [manage all your Office 365 DNS records at AWS](create-dns-records-at-aws.md).)</span></span>
  
    
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="0671d-107">확인을 위해 TXT 레코드 추가</span><span class="sxs-lookup"><span data-stu-id="0671d-107">Add a TXT record for verification</span></span>

<span data-ttu-id="0671d-p102">Office 365에서 사용자 도메인을 사용하려면 먼저 도메인을 소유하고 있어야 합니다. 도메인 등록 기관에서 사용자의 계정으로 로그인하고 DNS 레코드를 만들 수 있으면 Office 365에 도메인을 소유하고 있음을 증명할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0671d-p102">Before you use your domain with Office 365, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Office 365 that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="0671d-p103">이 레코드는 사용자가 도메인을 소유하고 있는지 확인하는 데만 사용되며 그 밖에 아무런 영향도 주지 않습니다. 원하는 경우 나중에 삭제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0671d-p103">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
1. <span data-ttu-id="0671d-p104">시작하려면 [이 링크](https://console.aws.amazon.com/route53/home)를 사용하여 AWS의 도메인 페이지로 이동합니다. 먼저 로그인하라는 메시지가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="0671d-p104">To get started, go to your domains page at AWS by using [this link](https://console.aws.amazon.com/route53/home). You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="0671d-114">**리소스** 페이지에서 **호스트 된 영역**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="0671d-114">On the **Resources** page, select **Hosted Zones**.</span></span>
    
3. <span data-ttu-id="0671d-115">**호스팅된 영역** 페이지의 **Domain Name (도메인 이름** ) 열에서 편집 하려는 도메인의 이름을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="0671d-115">On the **Hosted Zones** page, in the **Domain Name** column, select the name of the domain that you want to edit.</span></span> 
    
4. <span data-ttu-id="0671d-116">**레코드 집합 만들기**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="0671d-116">Select **Create Record Set**.</span></span>
    
5. <span data-ttu-id="0671d-117">In the **Create Record Set** area, in the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="0671d-117">In the **Create Record Set** area, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="0671d-118">(Choose the **Type** and **Routing Policy** values from the drop-down lists.)</span><span class="sxs-lookup"><span data-stu-id="0671d-118">(Choose the **Type** and **Routing Policy** values from the drop-down lists.)</span></span> 
    
    > [!TIP]
    > <span data-ttu-id="0671d-p105">The quotation marks required by the onscreen instructions are supplied automatically. You don't need to type them manually.</span><span class="sxs-lookup"><span data-stu-id="0671d-p105">The quotation marks required by the onscreen instructions are supplied automatically. You don't need to type them manually.</span></span> 
  
|||||||
|:-----|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="0671d-121">**이름**</span><span class="sxs-lookup"><span data-stu-id="0671d-121">**Name**</span></span> <br/> |<span data-ttu-id="0671d-122">**종류**</span><span class="sxs-lookup"><span data-stu-id="0671d-122">**Type**</span></span> <br/> |<span data-ttu-id="0671d-123">**별칭**</span><span class="sxs-lookup"><span data-stu-id="0671d-123">**Alias**</span></span> <br/> |<span data-ttu-id="0671d-124">**TTL(초)**</span><span class="sxs-lookup"><span data-stu-id="0671d-124">**TTL (Seconds)**</span></span> <br/> |<span data-ttu-id="0671d-125">**값**</span><span class="sxs-lookup"><span data-stu-id="0671d-125">**Value**</span></span> <br/> |<span data-ttu-id="0671d-126">**라우팅 정책**</span><span class="sxs-lookup"><span data-stu-id="0671d-126">**Routing Policy**</span></span> <br/> |
|<span data-ttu-id="0671d-127">(이 필드는 비워 둡니다.)</span><span class="sxs-lookup"><span data-stu-id="0671d-127">(Leave this field empty)</span></span>  <br/> |<span data-ttu-id="0671d-128">TXT - Text</span><span class="sxs-lookup"><span data-stu-id="0671d-128">TXT - Text</span></span>  <br/> |<span data-ttu-id="0671d-129">아니요</span><span class="sxs-lookup"><span data-stu-id="0671d-129">No</span></span>  <br/> |<span data-ttu-id="0671d-130">300</span><span class="sxs-lookup"><span data-stu-id="0671d-130">300</span></span>  <br/> |<span data-ttu-id="0671d-131">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="0671d-131">MS=ms *XXXXXXXX*</span></span> <br/> <span data-ttu-id="0671d-132">**참고:** 예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="0671d-132">**Note:** This is an example.</span></span> <span data-ttu-id="0671d-133">여기에는 Office 365의 표에 있는 특정 **대상 또는 주소 가리키기** 값을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="0671d-133">Use your specific **Destination or Points to Address** value here, from the table in Office 365.</span></span> [<span data-ttu-id="0671d-134">이 값을 찾는 방법</span><span class="sxs-lookup"><span data-stu-id="0671d-134">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)  <br/>  |<span data-ttu-id="0671d-135">Simple(단순형)</span><span class="sxs-lookup"><span data-stu-id="0671d-135">Simple</span></span> <br/> |
   
6. <span data-ttu-id="0671d-136">**만들기**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="0671d-136">Select **Create**.</span></span>
    
7. <span data-ttu-id="0671d-137">방금 만든 레코드가 인터넷에서 업데이트될 수 있도록 몇 분 정도 기다립니다.</span><span class="sxs-lookup"><span data-stu-id="0671d-137">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="0671d-138">Now that you've added the record at your domain registrar's site, you'll go back to Office 365 and request Office 365 to look for the record.</span><span class="sxs-lookup"><span data-stu-id="0671d-138">Now that you've added the record at your domain registrar's site, you'll go back to Office 365 and request Office 365 to look for the record.</span></span>
  
<span data-ttu-id="0671d-139">When Office 365 finds the correct TXT record, your domain is verified.</span><span class="sxs-lookup"><span data-stu-id="0671d-139">When Office 365 finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="0671d-140">관리 센터에서 **설정** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">도메인</a> 페이지로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="0671d-140">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

    
2. <span data-ttu-id="0671d-141">**도메인** 페이지에서 확인 하려는 도메인을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="0671d-141">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
3. <span data-ttu-id="0671d-142">**설정** 페이지에서 **설정 시작**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="0671d-142">On the **Setup** page, select **Start setup**.</span></span>
    
4. <span data-ttu-id="0671d-143">**도메인 확인** 페이지에서 **확인**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="0671d-143">On the **Verify domain** page, select **Verify**.</span></span>
    
> [!NOTE]
> <span data-ttu-id="0671d-144">Typically it takes about 15 minutes for DNS changes to take effect.</span><span class="sxs-lookup"><span data-stu-id="0671d-144">Typically it takes about 15 minutes for DNS changes to take effect.</span></span> <span data-ttu-id="0671d-145">However, it can occasionally take longer for a change you've made to update across the Internet's DNS system.</span><span class="sxs-lookup"><span data-stu-id="0671d-145">However, it can occasionally take longer for a change you've made to update across the Internet's DNS system.</span></span> <span data-ttu-id="0671d-146">DNS 레코드를 추가한 후 메일 흐름 또는 기타 문제에 문제가 있는 경우 [Office 365에서 도메인 또는 DNS 레코드를 추가한 후 문제 찾기 및 해결](../get-help-with-domains/find-and-fix-issues.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="0671d-146">If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records in Office 365](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="change-your-domains-nameserver-ns-records"></a><span data-ttu-id="0671d-147">도메인의 NS(이름 서버) 레코드 변경</span><span class="sxs-lookup"><span data-stu-id="0671d-147">Change your domain's nameserver (NS) records</span></span>

<span data-ttu-id="0671d-p108">Office 365에서 도메인 설정을 완료하려면 도메인 등록 기관에서 도메인의 NS 레코드가 Office 365 기본 및 보조 이름 서버를 가리키도록 변경합니다. 이렇게 하면 Office 365가 사용자 대신 도메인의 DNS 레코드를 업데이트하도록 설정됩니다. 전자 메일, 비즈니스용 Skype Online, 공개 웹 사이트가 사용자의 도메인을 사용하도록 모든 레코드가 자동으로 추가되고 모든 설정이 완료됩니다.</span><span class="sxs-lookup"><span data-stu-id="0671d-p108">To complete setting up your domain with Office 365, you change your domain's NS records at your domain registrar to point to the Office 365 primary and secondary name servers. This sets up Office 365 to update the domain's DNS records for you. We'll add all records so that email, Skype for Business Online, and your public website work with your domain, and you'll be all set.</span></span>
  
> [!CAUTION]
> <span data-ttu-id="0671d-p109">Office 365 이름 서버를 가리키도록 도메인 NS 레코드를 변경하면 현재 도메인에 연결되는 모든 서비스가 영향을 받습니다. 예를 들어 이 변경 내용을 적용하면 사용자의 도메인(예: rob@ *사용자_도메인*  .com)으로 보낸 전자 메일이 Office 365로 수신됩니다.</span><span class="sxs-lookup"><span data-stu-id="0671d-p109">When you change your domain's NS records to point to the Office 365 name servers, all the services that are currently associated with your domain are affected. For example, all email sent to your domain (like rob@ *your_domain*  .com) will start coming to Office 365 after you make this change.</span></span> 
  
> [!IMPORTANT]
>  <span data-ttu-id="0671d-153">다음 절차에서는 목록에서 원치 않는 이름 서버를 삭제 하는 방법 및 올바른 이름 서버가 나열 되어 있지 않은 경우 추가 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="0671d-153">The following procedure will show you how to delete any other, unwanted nameservers from the list, and also how to add the correct nameservers if they are not already listed.</span></span> <span data-ttu-id="0671d-154">>이 섹션의 단계를 완료 한 후에는 > ns1.bdm.microsoftonline.com > ns2.bdm.microsoftonline.com > ns3.bdm.microsoftonline.com > ns4.bdm.microsoftonline.com와 같은 4 가지 이름 서버를 나열 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0671d-154">>  When you have completed the steps in this section, the only nameservers that should be listed are these four: >  ns1.bdm.microsoftonline.com >  ns2.bdm.microsoftonline.com >  ns3.bdm.microsoftonline.com >  ns4.bdm.microsoftonline.com</span></span> 
  
1. <span data-ttu-id="0671d-155">시작하려면 [이 링크](https://console.aws.amazon.com/route53/home)를 사용하여 AWS의 도메인 페이지로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="0671d-155">To get started, go to your domains page at AWS by using [this link](https://console.aws.amazon.com/route53/home).</span></span> <span data-ttu-id="0671d-156">먼저 로그인하라는 메시지가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="0671d-156">You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="0671d-157">**리소스** 페이지에서 **호스트 된 영역**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="0671d-157">On the **Resources** page, select **Hosted Zones**.</span></span>
    
3. <span data-ttu-id="0671d-158">**호스팅된 영역** 페이지의 **Domain Name (도메인 이름** ) 열에서 편집 하려는 도메인의 이름을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="0671d-158">On the **Hosted Zones** page, in the **Domain Name** column, select the name of the domain that you want to edit.</span></span> 
    
4. <span data-ttu-id="0671d-159">**이름 서버** 레코드 집합을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="0671d-159">Select the **Nameserver** record set.</span></span> 
    
    ![Select the recordset](../media/24e618e4-0a16-43a2-9886-f4f5dac79374.png)
  
5. <span data-ttu-id="0671d-161">**NS - Name server(NS - 이름 서버)** 레코드 집합의 **Value(값)** 상자에서 모든 이름 서버를 선택한 다음 키보드의 **Delete** 키를 눌러 모든 이름 서버를 삭제합니다.</span><span class="sxs-lookup"><span data-stu-id="0671d-161">In the **NS - Name server** record set in the **Value** box, delete all of the nameservers by selecting them all and then pressing the **Delete** key on your keyboard.</span></span> 
    
    > [!CAUTION]
    > <span data-ttu-id="0671d-162">Follow these steps only if you have existing nameservers other than the four correct nameservers.</span><span class="sxs-lookup"><span data-stu-id="0671d-162">Follow these steps only if you have existing nameservers other than the four correct nameservers.</span></span> <span data-ttu-id="0671d-163">(즉, **ns1.bdm.microsoftonline.com**, **ns2.bdm.microsoftonline.com**, **ns3.bdm.microsoftonline.com**또는 **ns4.bdm.microsoftonline.com**로 이름이 지정 *되지* 않은 현재 이름 서버 삭제 합니다.)</span><span class="sxs-lookup"><span data-stu-id="0671d-163">(That is, delete only any current nameservers that are  *not*  named **ns1.bdm.microsoftonline.com**, **ns2.bdm.microsoftonline.com**, **ns3.bdm.microsoftonline.com**, or **ns4.bdm.microsoftonline.com**.)</span></span> 
  
    ![Select and delete all of the nameservers in the Value box](../media/ecf1e897-fa7d-4abc-b00b-bf55b8ed2139.png)
  
6. <span data-ttu-id="0671d-165">**TTL (초):** 영역에서 **1H** (1 시간)을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="0671d-165">In the **TTL (Seconds):** area, select **1h** (1 Hour).</span></span> 
    
    ![1 시간 동안 1H 선택](../media/c70070e1-4bde-41a7-b271-9d22c475edf6.png)
  
7. <span data-ttu-id="0671d-167">계속해서 **NS - Name server**(NS - 이름 서버) 레코드 집합의 **Value**(값) 상자에 다음 표의 **First line**(첫 줄)에 있는 값을 입력하거나 복사하여 붙여넣고 키보드의 **Enter** 키를 누른 후 다음 **line**(줄)에 있는 값을 입력하거나 복사하여 붙여넣습니다.</span><span class="sxs-lookup"><span data-stu-id="0671d-167">Still in the **NS - Name server** record set, in the **Value** box, type or copy and paste the **First line** value from the following table, then press the **Enter** key on your keyboard and type or copy and paste the next **line** value.</span></span> 
    
    > [!IMPORTANT]
    > <span data-ttu-id="0671d-168">이름 서버 값은 다음 그림과 같이 *Value(값)* 상자 안의 각기 다른 줄에  **있어야 합니다**  .</span><span class="sxs-lookup"><span data-stu-id="0671d-168">Each nameserver value  *must*  be on its own separate line within the **Value** box, as shown in the following illustration.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="0671d-169">**첫 줄**</span><span class="sxs-lookup"><span data-stu-id="0671d-169">**First line**</span></span> <br/> |<span data-ttu-id="0671d-170">ns1.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="0671d-170">ns1.bdm.microsoftonline.com.</span></span>  <br/> <span data-ttu-id="0671d-171">**This value MUST end with a period (.)**</span><span class="sxs-lookup"><span data-stu-id="0671d-171">**This value MUST end with a period (.)**</span></span> <br/> |
|<span data-ttu-id="0671d-172">**둘째 줄**</span><span class="sxs-lookup"><span data-stu-id="0671d-172">**Second line**</span></span> <br/> |<span data-ttu-id="0671d-173">ns2.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="0671d-173">ns2.bdm.microsoftonline.com.</span></span>  <br/> <span data-ttu-id="0671d-174">**This value MUST end with a period (.)**</span><span class="sxs-lookup"><span data-stu-id="0671d-174">**This value MUST end with a period (.)**</span></span> <br/> |
|<span data-ttu-id="0671d-175">**셋째 줄**</span><span class="sxs-lookup"><span data-stu-id="0671d-175">**Third line**</span></span> <br/> |<span data-ttu-id="0671d-176">ns3.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="0671d-176">ns3.bdm.microsoftonline.com.</span></span>  <br/> <span data-ttu-id="0671d-177">**이 값은 마침표(.)로 끝나야 합니다.**</span><span class="sxs-lookup"><span data-stu-id="0671d-177">**This value MUST end with a period (.)**</span></span> <br/> |
|<span data-ttu-id="0671d-178">**넷째 줄**</span><span class="sxs-lookup"><span data-stu-id="0671d-178">**Fourth line**</span></span> <br/> |<span data-ttu-id="0671d-179">ns4.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="0671d-179">ns4.bdm.microsoftonline.com.</span></span>  <br/> <span data-ttu-id="0671d-180">**이 값은 마침표(.)로 끝나야 합니다.**</span><span class="sxs-lookup"><span data-stu-id="0671d-180">**This value MUST end with a period (.)**</span></span> <br/> |
   
   ![값 상자에 첫 번째 줄 값 입력 또는 붙여넣기](../media/b63f41e0-51ef-4ab2-a4b8-ee7380e5ab35.png)
  
8. <span data-ttu-id="0671d-182">**레코드 집합 저장**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="0671d-182">Select **Save Record Set**.</span></span>
    
    ![레코드 집합 저장을 선택 합니다.](../media/ab3c0558-bb7c-41e4-871e-ea82f1553476.png)
  
> [!NOTE]
> <span data-ttu-id="0671d-p113">이름 서버 레코드 업데이트가 인터넷의 DNS 시스템 전체에 업데이트되기까지 몇 시간이 걸릴 수 있습니다. 그 후에는 Office 365 전자 메일 및 기타 서비스가 모두 사용자의 도메인을 사용하도록 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="0671d-p113">Your nameserver record updates may take up to several hours to update across the Internet's DNS system. Then your Office 365 email and other services will be all set to work with your domain.</span></span> 
