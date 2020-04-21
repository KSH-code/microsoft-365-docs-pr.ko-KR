---
title: Microsoft의 Network Solutions에서 DNS 레코드 만들기
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
- Adm_NonTOC
- Adm_O365_Setup
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 1dc55f9f-5309-450f-acc3-b2b4119c8be3
description: 도메인을 확인 하 고 전자 메일, 비즈니스용 Skype Online 및 Microsoft 용 네트워크 솔루션의 기타 서비스에 대 한 DNS 레코드를 설정 하는 방법을 알아봅니다.
ms.openlocfilehash: e7ce1dd633aa916643f3dcbf7900fa7831608e78
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/21/2020
ms.locfileid: "43629302"
---
# <a name="create-dns-records-at-network-solutions-for-microsoft"></a><span data-ttu-id="ba92f-103">Microsoft의 Network Solutions에서 DNS 레코드 만들기</span><span class="sxs-lookup"><span data-stu-id="ba92f-103">Create DNS records at Network Solutions for Microsoft</span></span>

 <span data-ttu-id="ba92f-104">**원하는 정보는 찾지 못한 경우 [도메인 질문과 대답을 확인](../setup/domains-faq.md)** 하세요.</span><span class="sxs-lookup"><span data-stu-id="ba92f-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="ba92f-105">DNS 호스팅 공급자로 Network Solutions를 사용하고 있는 경우, 이 문서에 나와 있는 단계를 따라 도메인을 확인하고 전자 메일, 비즈니스용 Skype Online 등에 대한 DNS 레코드를 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="ba92f-105">If Network Solutions is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Skype for Business Online, and so on.</span></span>
  
<span data-ttu-id="ba92f-106">다음은 추가할 기본 레코드입니다.</span><span class="sxs-lookup"><span data-stu-id="ba92f-106">These are the main records to add.</span></span> <span data-ttu-id="ba92f-107">아래 단계를 따르거나 [비디오를 시청하세요](https://support.office.com/article/Video-Create-DNS-records-at-Network-Solutions-for-Office-365-c49698c2-6991-47fb-b5ac-18e49a505099?ui=en-US&amp;rs=en-US&amp;ad=US).</span><span class="sxs-lookup"><span data-stu-id="ba92f-107">Follow the steps below or [watch the video](https://support.office.com/article/Video-Create-DNS-records-at-Network-Solutions-for-Office-365-c49698c2-6991-47fb-b5ac-18e49a505099?ui=en-US&amp;rs=en-US&amp;ad=US).</span></span> 
  
- [<span data-ttu-id="ba92f-108">확인을 위해 TXT 레코드 추가</span><span class="sxs-lookup"><span data-stu-id="ba92f-108">Add a TXT record for verification</span></span>](#add-a-txt-record-for-verification)
    
- [<span data-ttu-id="ba92f-109">도메인에 대 한 전자 메일이 Microsoft에 제공 되도록 MX 레코드를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="ba92f-109">Add an MX record so email for your domain will come to Microsoft</span></span>](#add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft)
    
- [<span data-ttu-id="ba92f-110">Microsoft에 필요한 CNAME 레코드 추가</span><span class="sxs-lookup"><span data-stu-id="ba92f-110">Add the CNAME records that are required for Microsoft</span></span>](#add-the-cname-records-that-are-required-for-microsoft)
    
- [<span data-ttu-id="ba92f-111">전자 메일 스팸 방지에 유용한 SPF용 TXT 레코드 추가</span><span class="sxs-lookup"><span data-stu-id="ba92f-111">Add a TXT record for SPF to help prevent email spam</span></span>](#add-a-txt-record-for-spf-to-help-prevent-email-spam)
    
- [<span data-ttu-id="ba92f-112">Microsoft에 필요한 두 개의 SRV 레코드를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="ba92f-112">Add the two SRV records that are required for Microsoft</span></span>](#add-the-two-srv-records-that-are-required-for-microsoft)
    
<span data-ttu-id="ba92f-113">네트워크 솔루션에서 이러한 레코드를 추가 하 고 나면 도메인이 Microsoft 서비스에서 작동 하도록 설정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ba92f-113">After you add these records at Network Solutions, your domain will be set up to work with Microsoft services.</span></span>
  
<span data-ttu-id="ba92f-114">Microsoft의 웹 사이트에 대 한 호스트 및 DNS에 대 한 자세한 내용은 [microsoft에서 공개 웹 사이트 사용](https://support.office.com/article/choose-a-public-website-3325d50e-d131-403c-a278-7f3296fe33a9)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="ba92f-114">To learn about webhosting and DNS for websites with Microsoft, see [Use a public website with Microsoft](https://support.office.com/article/choose-a-public-website-3325d50e-d131-403c-a278-7f3296fe33a9).</span></span>
  
> [!NOTE]
>  <span data-ttu-id="ba92f-p102">일반적으로 DNS 변경 내용을 적용하는 데 15분 정도 걸립니다. 그러나 변경한 내용이 인터넷의 DNS 시스템 전체에 업데이트되는 데에는 시간이 오래 걸릴 수 있습니다. DNS 레코드를 추가한 후 메일 흐름이나 기타 문제가 있는 경우 [도메인 이름 또는 DNS 레코드 변경 후 발생한 문제 해결](../get-help-with-domains/find-and-fix-issues.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="ba92f-p102">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="ba92f-118">확인을 위해 TXT 레코드 추가</span><span class="sxs-lookup"><span data-stu-id="ba92f-118">Add a TXT record for verification</span></span>
<span data-ttu-id="ba92f-119"><a name="BKMK_verify"> </a></span><span class="sxs-lookup"><span data-stu-id="ba92f-119"><a name="BKMK_verify"> </a></span></span>

<span data-ttu-id="ba92f-120">Microsoft에서 도메인을 사용 하기 전에 사용자가 소유 하 고 있는지 확인 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ba92f-120">Before you use your domain with Microsoft, we have to make sure that you own it.</span></span> <span data-ttu-id="ba92f-121">도메인 등록 기관에서 계정에 로그인 하 고 DNS 레코드를 만들 수 있는 기능은 Microsoft에 도메인을 소유 하 고 있음을 증명 합니다.</span><span class="sxs-lookup"><span data-stu-id="ba92f-121">Your ability to log in to your account at your domain registrar and create the DNS record proves to Microsoft that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="ba92f-p104">이 레코드는 사용자가 도메인을 소유하고 있는지 확인하는 데만 사용되며 그 밖에 아무런 영향도 주지 않습니다. 원하는 경우 나중에 삭제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ba92f-p104">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
<span data-ttu-id="ba92f-124">아래 단계를 따르거나 [비디오를 시청하세요(0:47에 시작)](https://support.office.com/article/Video-Create-DNS-records-at-Network-Solutions-for-Office-365-c49698c2-6991-47fb-b5ac-18e49a505099?ui=en-US&amp;rs=en-US&amp;ad=US).</span><span class="sxs-lookup"><span data-stu-id="ba92f-124">Follow the steps below or [watch the video (start at 0:47)](https://support.office.com/article/Video-Create-DNS-records-at-Network-Solutions-for-Office-365-c49698c2-6991-47fb-b5ac-18e49a505099?ui=en-US&amp;rs=en-US&amp;ad=US).</span></span>
  
1. <span data-ttu-id="ba92f-125">시작하려면 [이 링크](https://www.networksolutions.com/manage-it)를 사용하여 Network Solutions의 도메인 페이지로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="ba92f-125">To get started, go to your domains page at Network Solutions by using [this link](https://www.networksolutions.com/manage-it).</span></span> <span data-ttu-id="ba92f-126">로그인하라는 메시지가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="ba92f-126">You'll be prompted to log in.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="ba92f-127">**로그인** 단추를 선택 하기 전에 로그인 **:** 드롭다운 목록에서 **내 도메인 이름 관리** 를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="ba92f-127">Before you select the **Login** button, first choose **Manage My Domain Names** in the **Log In to:** drop-down list.</span></span> 
  
    ![Manage My Domain Names(내 도메인 이름 관리)를 선택하고 Network Solutions에 로그인합니다.](../../media/fda7d4a1-9445-4086-be9c-87c6983ef2aa.png)
  
2. <span data-ttu-id="ba92f-129">수정하려는 도메인 이름 옆의 확인란을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="ba92f-129">Select the check box next to the name of the domain that you are modifying.</span></span>
    
    ![도메인에 대한 확인란을 선택합니다.](../../media/2c13d2ba-4a31-44da-812c-2cc90900a183.png)
  
3. <span data-ttu-id="ba92f-131">**DNS 편집**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="ba92f-131">Select **Edit DNS**.</span></span>
    
    ![DNS 편집을 선택 합니다.](../../media/9d7c269f-48d1-442c-9d7b-63bd384a36a9.png)
  
4. <span data-ttu-id="ba92f-133">**고급 DNS 레코드 관리**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="ba92f-133">Select **Manage Advanced DNS Records**.</span></span>
    
    <span data-ttu-id="ba92f-134">(You may have to scroll down.)</span><span class="sxs-lookup"><span data-stu-id="ba92f-134">(You may have to scroll down.)</span></span>
    
    ![고급 DNS 레코드 관리 선택](../../media/fd2956d6-eec3-47ea-b60a-266bab14f51f.png)
  
5. <span data-ttu-id="ba92f-136">아래쪽 **텍스트 (Txt 레코드)** 구역으로 스크롤한 다음 **txt 레코드 편집**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="ba92f-136">Scroll down to the **Text (TXT Records)** section, and then select **Edit TXT Records**.</span></span>
    
    ![TXT 레코드 편집을 선택 합니다.](../../media/240a01d6-750a-4da6-8554-641b571e4b71.png)
  
6. <span data-ttu-id="ba92f-138">새 레코드의 상자에서 다음 표의 값을 입력하거나 복사하여 붙여넣습니다.</span><span class="sxs-lookup"><span data-stu-id="ba92f-138">In the boxes for the new record, type or copy and paste the values in the following table.</span></span>
    
    |<span data-ttu-id="ba92f-139">**Host**</span><span class="sxs-lookup"><span data-stu-id="ba92f-139">**Host**</span></span>|<span data-ttu-id="ba92f-140">**TTL**</span><span class="sxs-lookup"><span data-stu-id="ba92f-140">**TTL**</span></span>|<span data-ttu-id="ba92f-141">**텍스트**</span><span class="sxs-lookup"><span data-stu-id="ba92f-141">**Text**</span></span>|
    |:-----|:-----|:-----|
    |@  <br/> <span data-ttu-id="ba92f-142">(The system will change this value to **@ (None)** when you save the record.)</span><span class="sxs-lookup"><span data-stu-id="ba92f-142">(The system will change this value to **@ (None)** when you save the record.)</span></span>  <br/> |<span data-ttu-id="ba92f-143">3600</span><span class="sxs-lookup"><span data-stu-id="ba92f-143">3600</span></span>  <br/> |<span data-ttu-id="ba92f-144">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="ba92f-144">MS=ms *XXXXXXXX*</span></span>  <br/> <span data-ttu-id="ba92f-145">**참고:** 이 값은 예시입니다.</span><span class="sxs-lookup"><span data-stu-id="ba92f-145">**Note:** This is an example.</span></span> <span data-ttu-id="ba92f-146">표에서 특정 **대상 또는 지점** 값을 사용 하 여 여기서 주소를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="ba92f-146">Use your specific **Destination or Points to Address** value here, from the table.</span></span>  [<span data-ttu-id="ba92f-147">이 값을 찾는 방법</span><span class="sxs-lookup"><span data-stu-id="ba92f-147">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)   |
       
    ![새 레코드의 상자에 값을 입력 하거나 붙여넣습니다.](../../media/8a76daab-b6ff-4c82-ba68-192b24fbb934.png)
  
7. <span data-ttu-id="ba92f-149">**계속**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="ba92f-149">Select **Continue**.</span></span>
    
    ![계속을 선택](../../media/89e7fb38-b4d9-4949-a1bb-d0dd10b361e0.png)
  
8. <span data-ttu-id="ba92f-151">**변경 내용 저장**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="ba92f-151">Select **Save Changes**.</span></span>
    
    ![변경 내용 저장을 선택 합니다.](../../media/bd4d7cd0-c8a3-497a-b080-cfd5a5c60dc5.png)
  
9. <span data-ttu-id="ba92f-153">방금 만든 레코드가 인터넷에서 업데이트될 수 있도록 몇 분 정도 기다립니다.</span><span class="sxs-lookup"><span data-stu-id="ba92f-153">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="ba92f-154">도메인 등록 기관 사이트에서 레코드를 추가 했으므로 이제 Microsoft로 이동 하 여 레코드를 요청 합니다.</span><span class="sxs-lookup"><span data-stu-id="ba92f-154">Now that you've added the record at your domain registrar's site, you'll go back to Microsoft and request the record.</span></span>
  
<span data-ttu-id="ba92f-155">Microsoft에서 올바른 TXT 레코드를 찾으면 도메인이 확인 된 것입니다.</span><span class="sxs-lookup"><span data-stu-id="ba92f-155">When Microsoft finds the correct TXT record, your domain is verified.</span></span>

1. <span data-ttu-id="ba92f-156">I관리 센터에서 \*\* 설정 \*\* \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank"> 도메인 </a> 페이지로 이동하십시오.</span><span class="sxs-lookup"><span data-stu-id="ba92f-156">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>
    
2. <span data-ttu-id="ba92f-157">**도메인** 페이지에서 확인 중인 도메인을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="ba92f-157">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
    
  
3. <span data-ttu-id="ba92f-158">**설정** 페이지에서 **설정 시작**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="ba92f-158">On the **Setup** page, select **Start setup**.</span></span>
    
    
  
4. <span data-ttu-id="ba92f-159">**도메인 확인** 페이지에서 **확인**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="ba92f-159">On the **Verify domain** page, select **Verify**.</span></span>
    
    
  
> [!NOTE]
>  <span data-ttu-id="ba92f-p107">일반적으로 DNS 변경 내용을 적용하는 데 15분 정도 걸립니다. 그러나 변경한 내용이 인터넷의 DNS 시스템 전체에 업데이트되는 데에는 시간이 오래 걸릴 수 있습니다. DNS 레코드를 추가한 후 메일 흐름이나 기타 문제가 있는 경우 [도메인 이름 또는 DNS 레코드 변경 후 발생한 문제 해결](../get-help-with-domains/find-and-fix-issues.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="ba92f-p107">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft"></a><span data-ttu-id="ba92f-163">도메인에 대 한 전자 메일이 Microsoft에 제공 되도록 MX 레코드를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="ba92f-163">Add an MX record so email for your domain will come to Microsoft</span></span>
<span data-ttu-id="ba92f-164"><a name="BKMK_add_MX"> </a></span><span class="sxs-lookup"><span data-stu-id="ba92f-164"><a name="BKMK_add_MX"> </a></span></span>

<span data-ttu-id="ba92f-165">아래 단계를 따르거나 [비디오를 시청하세요(3:51에 시작)](https://support.office.com/article/Video-Create-DNS-records-at-Network-Solutions-for-Office-365-c49698c2-6991-47fb-b5ac-18e49a505099?ui=en-US&amp;rs=en-US&amp;ad=US).</span><span class="sxs-lookup"><span data-stu-id="ba92f-165">Follow the steps below or [watch the video (start at 3:51)](https://support.office.com/article/Video-Create-DNS-records-at-Network-Solutions-for-Office-365-c49698c2-6991-47fb-b5ac-18e49a505099?ui=en-US&amp;rs=en-US&amp;ad=US).</span></span>
  
1. <span data-ttu-id="ba92f-166">시작하려면 [이 링크](https://www.networksolutions.com/manage-it)를 사용하여 Network Solutions의 도메인 페이지로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="ba92f-166">To get started, go to your domains page at Network Solutions by using [this link](https://www.networksolutions.com/manage-it).</span></span> <span data-ttu-id="ba92f-167">로그인하라는 메시지가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="ba92f-167">You'll be prompted to log in.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="ba92f-168">**로그인** 단추를 선택 하기 전에 로그인 **:** 드롭다운 목록에서 **내 도메인 이름 관리** 를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="ba92f-168">Before you select the **Login** button, first choose **Manage My Domain Names** in the **Log In to:** drop-down list.</span></span> 
  
    ![Manage My Domain Names(내 도메인 이름 관리)를 선택하고 Network Solutions에 로그인합니다.](../../media/fda7d4a1-9445-4086-be9c-87c6983ef2aa.png)
  
2. <span data-ttu-id="ba92f-170">수정하려는 도메인 이름 옆의 확인란을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="ba92f-170">Select the check box next to the name of the domain that you are modifying.</span></span>
    
    ![도메인에 대한 확인란을 선택합니다.](../../media/2c13d2ba-4a31-44da-812c-2cc90900a183.png)
  
3. <span data-ttu-id="ba92f-172">**DNS 편집**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="ba92f-172">Select **Edit DNS**.</span></span>
    
    ![DNS 편집을 선택 합니다.](../../media/9d7c269f-48d1-442c-9d7b-63bd384a36a9.png)
  
4. <span data-ttu-id="ba92f-174">**고급 DNS 레코드 관리**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="ba92f-174">Select **Manage Advanced DNS Records**.</span></span>
    
    <span data-ttu-id="ba92f-175">(You may have to scroll down.)</span><span class="sxs-lookup"><span data-stu-id="ba92f-175">(You may have to scroll down.)</span></span>
    
    ![고급 DNS 레코드 관리 선택](../../media/fd2956d6-eec3-47ea-b60a-266bab14f51f.png)
  
5. <span data-ttu-id="ba92f-177">**메일 서버 (Mx 레코드)** 섹션이 될 때까지 아래로 스크롤한 다음 **mx 레코드 편집**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="ba92f-177">Scroll down to the **Mail Servers (MX Records)** section, and then select **Edit MX Records**.</span></span>
    
    ![MX 레코드 편집을 선택 합니다.](../../media/74b4e412-9073-4d2d-8710-fe340b223798.png)
  
6. <span data-ttu-id="ba92f-179">새 레코드의 상자에서 다음 표의 값을 입력하거나 복사하여 붙여넣습니다.</span><span class="sxs-lookup"><span data-stu-id="ba92f-179">In the boxes for the new record, type or copy and paste the values from the following table.</span></span>
    
    |<span data-ttu-id="ba92f-180">**Priority(우선 순위)**</span><span class="sxs-lookup"><span data-stu-id="ba92f-180">**Priority**</span></span>|<span data-ttu-id="ba92f-181">**TTL**</span><span class="sxs-lookup"><span data-stu-id="ba92f-181">**TTL**</span></span>|<span data-ttu-id="ba92f-182">**메일 서버**</span><span class="sxs-lookup"><span data-stu-id="ba92f-182">**Mail Server**</span></span>|
    |:-----|:-----|:-----|
    |<span data-ttu-id="ba92f-183">10 </span><span class="sxs-lookup"><span data-stu-id="ba92f-183">10</span></span>  <br/> <span data-ttu-id="ba92f-184">우선 순위에 대한 자세한 내용은 [MX 우선 순위란?](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="ba92f-184">For more information about priority, see [What is MX priority?](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx)</span></span> <br/> |<span data-ttu-id="ba92f-185">3600</span><span class="sxs-lookup"><span data-stu-id="ba92f-185">3600</span></span>  <br/> | <span data-ttu-id="ba92f-186">*\<domain-key\>*  .mail.protection.outlook.com.</span><span class="sxs-lookup"><span data-stu-id="ba92f-186">*\<domain-key\>*  .mail.protection.outlook.com.</span></span>  <br/> <span data-ttu-id="ba92f-187">**이 값은 마침표(.)로 끝나야 합니다.**</span><span class="sxs-lookup"><span data-stu-id="ba92f-187">**This value MUST end with a period (.)**</span></span> <br/> <span data-ttu-id="ba92f-188">**참고:** Microsoft 계정에서 \* \<도메인 키\> \* 를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="ba92f-188">**Note:** Get your  *\<domain-key\>*  from your Microsoft account.</span></span> [<span data-ttu-id="ba92f-189">이 값을 찾는 방법</span><span class="sxs-lookup"><span data-stu-id="ba92f-189">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |
       
    ![새 레코드의 상자에 값을 입력 하거나 붙여넣습니다.](../../media/0bb96872-cc6e-4dfa-a649-fb7efbbf0012.png)
  
7. <span data-ttu-id="ba92f-191">**계속**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="ba92f-191">Select **Continue**.</span></span>
    
    ![계속을 선택](../../media/963f758b-e79d-4452-8340-7eba8a3972c9.png)
  
8. <span data-ttu-id="ba92f-193">**변경 내용 저장**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="ba92f-193">Select **Save Changes**.</span></span>
    
    ![변경 내용 저장을 선택 합니다.](../../media/7c2f784a-6dee-4364-866c-ad7202ef1fc2.png)
  
9. <span data-ttu-id="ba92f-195">다른 MX 레코드가 있으면 각 레코드에 대한 **삭제**를 선택하여 레코드를 모두 삭제합니다.</span><span class="sxs-lookup"><span data-stu-id="ba92f-195">If there are any other MX records, delete all of them by selecting **Delete** for each record.</span></span> 
    
    ![Select the Delete check box for other MX records](../../media/709d6133-9f5d-490a-a91e-95e21ca94695.png)
  
10. <span data-ttu-id="ba92f-197">모두 선택 되 면 **계속**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="ba92f-197">When they are all selected, select **Continue**.</span></span>
    
    ![계속을 선택](../../media/4710f988-0bbc-4ba7-bf31-ca2392b2900e.png)
  
11. <span data-ttu-id="ba92f-199">**변경 내용 저장**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="ba92f-199">Select **Save Changes**.</span></span>
    
    ![변경 내용 저장을 선택 합니다.](../../media/24432ec6-666b-4612-9488-37c06437959b.png)
  
## <a name="add-the-cname-records-that-are-required-for-microsoft"></a><span data-ttu-id="ba92f-201">Microsoft에 필요한 CNAME 레코드 추가</span><span class="sxs-lookup"><span data-stu-id="ba92f-201">Add the CNAME records that are required for Microsoft</span></span>
<span data-ttu-id="ba92f-202"><a name="BKMK_add_CNAME"> </a></span><span class="sxs-lookup"><span data-stu-id="ba92f-202"><a name="BKMK_add_CNAME"> </a></span></span>

<span data-ttu-id="ba92f-203">아래 단계를 따르거나 [비디오를 시청하세요(4:43에 시작)](https://support.office.com/article/Video-Create-DNS-records-at-Network-Solutions-for-Office-365-c49698c2-6991-47fb-b5ac-18e49a505099?ui=en-US&amp;rs=en-US&amp;ad=US).</span><span class="sxs-lookup"><span data-stu-id="ba92f-203">Follow the steps below or [watch the video (start at 4:43)](https://support.office.com/article/Video-Create-DNS-records-at-Network-Solutions-for-Office-365-c49698c2-6991-47fb-b5ac-18e49a505099?ui=en-US&amp;rs=en-US&amp;ad=US).</span></span>
  
1. <span data-ttu-id="ba92f-204">시작하려면 [이 링크](https://www.networksolutions.com/manage-it)를 사용하여 Network Solutions의 도메인 페이지로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="ba92f-204">To get started, go to your domains page at Network Solutions by using [this link](https://www.networksolutions.com/manage-it).</span></span> <span data-ttu-id="ba92f-205">로그인하라는 메시지가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="ba92f-205">You'll be prompted to log in.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="ba92f-206">**로그인** 단추를 선택 하기 전에 로그인 **:** 드롭다운 목록에서 **내 도메인 이름 관리** 를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="ba92f-206">Before you select the **Login** button, first choose **Manage My Domain Names** in the **Log In to:** drop-down list.</span></span> 
  
    ![Manage My Domain Names(내 도메인 이름 관리)를 선택하고 Network Solutions에 로그인합니다.](../../media/fda7d4a1-9445-4086-be9c-87c6983ef2aa.png)
  
2. <span data-ttu-id="ba92f-208">수정하려는 도메인 이름 옆의 확인란을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="ba92f-208">Select the check box next to the name of the domain that you are modifying.</span></span>
    
    ![도메인에 대한 확인란을 선택합니다.](../../media/2c13d2ba-4a31-44da-812c-2cc90900a183.png)
  
3. <span data-ttu-id="ba92f-210">**DNS 편집**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="ba92f-210">Select **Edit DNS**.</span></span>
    
    ![DNS 편집을 선택 합니다.](../../media/9d7c269f-48d1-442c-9d7b-63bd384a36a9.png)
  
4. <span data-ttu-id="ba92f-212">**고급 DNS 레코드 관리**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="ba92f-212">Select **Manage Advanced DNS Records**.</span></span>
    
    <span data-ttu-id="ba92f-213">(You may have to scroll down.)</span><span class="sxs-lookup"><span data-stu-id="ba92f-213">(You may have to scroll down.)</span></span>
    
    ![고급 DNS 레코드 관리 선택](../../media/fd2956d6-eec3-47ea-b60a-266bab14f51f.png)
  
5. <span data-ttu-id="ba92f-215">아래로 스크롤하여 **호스트 별칭 (CNAME 레코드)** 섹션으로 스크롤한 다음 **CNAME 레코드 편집**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="ba92f-215">Scroll down to the **Host Aliases (CNAME Records)** section, and then select **Edit CNAME Records**.</span></span>
    
    ![호스트 별칭 아래에서 CNAME 레코드 편집을 선택 합니다.](../../media/2d0a4666-8d40-48f4-886c-64a5157baaf5.png)
  
6. <span data-ttu-id="ba92f-217">네 개의 새 레코드 상자에서 다음 표의 값을 입력하거나 복사하여 붙여넣습니다.</span><span class="sxs-lookup"><span data-stu-id="ba92f-217">In the boxes for the four new records, type or copy and paste the values from the following table.</span></span>
    
    |<span data-ttu-id="ba92f-218">**별칭**</span><span class="sxs-lookup"><span data-stu-id="ba92f-218">**Alias**</span></span>|<span data-ttu-id="ba92f-219">**TTL**</span><span class="sxs-lookup"><span data-stu-id="ba92f-219">**TTL**</span></span>|<span data-ttu-id="ba92f-220">**호스트 이름 참조**</span><span class="sxs-lookup"><span data-stu-id="ba92f-220">**Refers to Host Name**</span></span>|<span data-ttu-id="ba92f-221">**기타 호스트          ( **기타 호스트** 옵션 단추 선택)**</span><span class="sxs-lookup"><span data-stu-id="ba92f-221">**Other Host          (select the **Other Host** option button)**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="ba92f-222">autodiscover</span><span class="sxs-lookup"><span data-stu-id="ba92f-222">autodiscover</span></span>  <br/> |<span data-ttu-id="ba92f-223">3600</span><span class="sxs-lookup"><span data-stu-id="ba92f-223">3600</span></span>  <br/> |<span data-ttu-id="ba92f-224">(설정 없음)</span><span class="sxs-lookup"><span data-stu-id="ba92f-224">(No setting)</span></span>  <br/> |<span data-ttu-id="ba92f-225">autodiscover.outlook.com</span><span class="sxs-lookup"><span data-stu-id="ba92f-225">autodiscover.outlook.com.</span></span>  <br/> <span data-ttu-id="ba92f-226">**This value MUST end with a period (.)**</span><span class="sxs-lookup"><span data-stu-id="ba92f-226">**This value MUST end with a period (.)**</span></span> <br/> |
    |<span data-ttu-id="ba92f-227">sip</span><span class="sxs-lookup"><span data-stu-id="ba92f-227">sip</span></span>  <br/> |<span data-ttu-id="ba92f-228">3600</span><span class="sxs-lookup"><span data-stu-id="ba92f-228">3600</span></span>  <br/> |<span data-ttu-id="ba92f-229">(설정 없음)</span><span class="sxs-lookup"><span data-stu-id="ba92f-229">(No setting)</span></span>  <br/> |<span data-ttu-id="ba92f-230">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="ba92f-230">sipdir.online.lync.com.</span></span>  <br/> <span data-ttu-id="ba92f-231">**This value MUST end with a period (.)**</span><span class="sxs-lookup"><span data-stu-id="ba92f-231">**This value MUST end with a period (.)**</span></span> <br/> |
    |<span data-ttu-id="ba92f-232">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="ba92f-232">lyncdiscover</span></span>  <br/> |<span data-ttu-id="ba92f-233">3600</span><span class="sxs-lookup"><span data-stu-id="ba92f-233">3600</span></span>  <br/> |<span data-ttu-id="ba92f-234">(설정 없음)</span><span class="sxs-lookup"><span data-stu-id="ba92f-234">(No setting)</span></span>  <br/> |<span data-ttu-id="ba92f-235">webdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="ba92f-235">webdir.online.lync.com.</span></span>  <br/> <span data-ttu-id="ba92f-236">**This value MUST end with a period (.)**</span><span class="sxs-lookup"><span data-stu-id="ba92f-236">**This value MUST end with a period (.)**</span></span> <br/> |
    |<span data-ttu-id="ba92f-237">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="ba92f-237">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="ba92f-238">3600</span><span class="sxs-lookup"><span data-stu-id="ba92f-238">3600</span></span>  <br/> |<span data-ttu-id="ba92f-239">(설정 없음)</span><span class="sxs-lookup"><span data-stu-id="ba92f-239">(No setting)</span></span>  <br/> |<span data-ttu-id="ba92f-240">enterpriseregistration.windows.net</span><span class="sxs-lookup"><span data-stu-id="ba92f-240">enterpriseregistration.windows.net</span></span>  <br/> <span data-ttu-id="ba92f-241">**이 값은 마침표(.)로 끝나야 합니다.**</span><span class="sxs-lookup"><span data-stu-id="ba92f-241">**This value MUST end with a period (.)**</span></span> <br/> |
    |<span data-ttu-id="ba92f-242">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="ba92f-242">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="ba92f-243">3600</span><span class="sxs-lookup"><span data-stu-id="ba92f-243">3600</span></span>  <br/> |<span data-ttu-id="ba92f-244">(설정 없음)</span><span class="sxs-lookup"><span data-stu-id="ba92f-244">(No setting)</span></span>  <br/> |<span data-ttu-id="ba92f-245">enterpriseenrollment-s.manage.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="ba92f-245">enterpriseenrollment-s.manage.microsoft.com</span></span>  <br/> <span data-ttu-id="ba92f-246">**This value MUST end with a period (.)**</span><span class="sxs-lookup"><span data-stu-id="ba92f-246">**This value MUST end with a period (.)**</span></span> <br/> |
    
    ![새 레코드 값 입력 또는 붙여넣기](../../media/5ce0b30c-b46c-4778-aa5a-fb5e2f0961c1.png)
  
7. <span data-ttu-id="ba92f-248">필요한 CNAME 레코드를 모두 추가한 경우 **계속**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="ba92f-248">When you have added all of the CNAME records that you need, select **Continue**.</span></span>
    
    ![계속을 선택](../../media/4978bd8b-f6a6-458d-9522-ad612b301c4a.png)
  
8. <span data-ttu-id="ba92f-250">**변경 내용 저장**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="ba92f-250">Select **Save Changes**.</span></span>
    
    ![변경 내용 저장을 선택 합니다.](../../media/f005c38a-0d8d-4c61-bec6-15e60c89aa5a.png)
  
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="ba92f-252">전자 메일 스팸 방지에 유용한 SPF용 TXT 레코드 추가</span><span class="sxs-lookup"><span data-stu-id="ba92f-252">Add a TXT record for SPF to help prevent email spam</span></span>
<span data-ttu-id="ba92f-253"><a name="BKMK_add_TXT"> </a></span><span class="sxs-lookup"><span data-stu-id="ba92f-253"><a name="BKMK_add_TXT"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="ba92f-254">도메인 한 개의 SPF에 둘 이상의 TXT 레코드가 있을 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="ba92f-254">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="ba92f-255">도메인에 둘 이상의 SPF 레코드가 있는 경우 전자 메일 오류를 비롯하여 배달 및 스팸 분류 문제가 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ba92f-255">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="ba92f-256">도메인에 대 한 SPF 레코드가 이미 있는 경우 Microsoft에 대해 새로 만들지 마십시오.</span><span class="sxs-lookup"><span data-stu-id="ba92f-256">If you already have an SPF record for your domain, don't create a new one for Microsoft.</span></span> <span data-ttu-id="ba92f-257">대신, 두 값 집합을 모두 포함 하는 *단일* SPF 레코드가 있도록 현재 레코드에 필수 Microsoft 값을 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="ba92f-257">Instead, add the required Microsoft values to the current record so that you have a  *single*  SPF record that includes both sets of values.</span></span> 
  
<span data-ttu-id="ba92f-258">아래 단계를 따르거나 [비디오를 시청하세요(5:35에 시작)](https://support.office.com/article/Video-Create-DNS-records-at-Network-Solutions-for-Office-365-c49698c2-6991-47fb-b5ac-18e49a505099?ui=en-US&amp;rs=en-US&amp;ad=US).</span><span class="sxs-lookup"><span data-stu-id="ba92f-258">Follow the steps below or [watch the video (start at 5:35)](https://support.office.com/article/Video-Create-DNS-records-at-Network-Solutions-for-Office-365-c49698c2-6991-47fb-b5ac-18e49a505099?ui=en-US&amp;rs=en-US&amp;ad=US).</span></span>
  
1. <span data-ttu-id="ba92f-259">시작하려면 [이 링크](https://www.networksolutions.com/manage-it)를 사용하여 Network Solutions의 도메인 페이지로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="ba92f-259">To get started, go to your domains page at Network Solutions by using [this link](https://www.networksolutions.com/manage-it).</span></span> <span data-ttu-id="ba92f-260">로그인하라는 메시지가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="ba92f-260">You'll be prompted to log in.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="ba92f-261">**로그인** 단추를 선택 하기 전에 로그인 **:** 드롭다운 목록에서 **내 도메인 이름 관리** 를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="ba92f-261">Before you select the **Login** button, first choose **Manage My Domain Names** in the **Log In to:** drop-down list.</span></span> 
  
    ![Manage My Domain Names(내 도메인 이름 관리)를 선택하고 Network Solutions에 로그인합니다.](../../media/fda7d4a1-9445-4086-be9c-87c6983ef2aa.png)
  
2. <span data-ttu-id="ba92f-263">수정하려는 도메인 이름 옆의 확인란을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="ba92f-263">Select the check box next to the name of the domain that you are modifying.</span></span>
    
    ![도메인에 대한 확인란을 선택합니다.](../../media/2c13d2ba-4a31-44da-812c-2cc90900a183.png)
  
3. <span data-ttu-id="ba92f-265">**DNS 편집**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="ba92f-265">Select **Edit DNS**.</span></span>
    
    ![DNS 편집을 선택 합니다.](../../media/9d7c269f-48d1-442c-9d7b-63bd384a36a9.png)
  
4. <span data-ttu-id="ba92f-267">**고급 DNS 레코드 관리**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="ba92f-267">Select **Manage Advanced DNS Records**.</span></span>
    
    <span data-ttu-id="ba92f-268">(You may have to scroll down.)</span><span class="sxs-lookup"><span data-stu-id="ba92f-268">(You may have to scroll down.)</span></span>
    
    ![고급 DNS 레코드 관리 선택](../../media/fd2956d6-eec3-47ea-b60a-266bab14f51f.png)
  
5. <span data-ttu-id="ba92f-270">아래쪽 **텍스트 (Txt 레코드)** 구역으로 스크롤한 다음 **txt 레코드 편집**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="ba92f-270">Scroll down to the **Text (TXT Records)** section, and then select **Edit TXT Records**.</span></span>
    
    ![텍스트 아래에서 TXT 레코드 편집을 선택 합니다.](../../media/a69a2631-6da2-4e81-99ab-9a9ab9b30b07.png)
  
6. <span data-ttu-id="ba92f-272">새 레코드의 상자에서 다음 값을 입력하거나 복사하여 붙여 넣습니다.</span><span class="sxs-lookup"><span data-stu-id="ba92f-272">In the boxes for the new record, type or copy and paste the following values.</span></span>
    
    |<span data-ttu-id="ba92f-273">**호스트**</span><span class="sxs-lookup"><span data-stu-id="ba92f-273">**Host**</span></span>|<span data-ttu-id="ba92f-274">**TTL**</span><span class="sxs-lookup"><span data-stu-id="ba92f-274">**TTL**</span></span>|<span data-ttu-id="ba92f-275">**텍스트**</span><span class="sxs-lookup"><span data-stu-id="ba92f-275">**Text**</span></span>|
    |:-----|:-----|:-----|
    |@  <br/> <span data-ttu-id="ba92f-276">(The system will change this value to **@ (None)** when you save the record.)</span><span class="sxs-lookup"><span data-stu-id="ba92f-276">(The system will change this value to **@ (None)** when you save the record.)</span></span>  <br/> |<span data-ttu-id="ba92f-277">3600</span><span class="sxs-lookup"><span data-stu-id="ba92f-277">3600</span></span>  <br/> |<span data-ttu-id="ba92f-278">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="ba92f-278">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/> <span data-ttu-id="ba92f-279">**참고:** 모든 공백이 올바르게 유지되도록 이 항목을 복사하여 붙여 넣는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="ba92f-279">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span> |
       
    ![새 레코드에 대 한 값 입력 또는 붙여넣기](../../media/11564eca-e2ee-4f17-af2b-a00eb7c157db.png)
  
7. <span data-ttu-id="ba92f-281">**계속**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="ba92f-281">Select **Continue**.</span></span>
    
    ![계속을 선택](../../media/482a8dae-0c79-47c4-8bd8-87965683de24.png)
  
8. <span data-ttu-id="ba92f-283">**변경 내용 저장**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="ba92f-283">Select **Save Changes**.</span></span>
    
    ![변경 내용 저장을 선택 합니다.](../../media/600b8c6d-184f-4213-a50e-8f119ebf3ff0.png)
  
## <a name="add-the-two-srv-records-that-are-required-for-microsoft"></a><span data-ttu-id="ba92f-285">Microsoft에 필요한 두 개의 SRV 레코드를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="ba92f-285">Add the two SRV records that are required for Microsoft</span></span>
<span data-ttu-id="ba92f-286"><a name="BKMK_add_SRV"> </a></span><span class="sxs-lookup"><span data-stu-id="ba92f-286"><a name="BKMK_add_SRV"> </a></span></span>

<span data-ttu-id="ba92f-287">아래 단계를 따르거나 [비디오를 시청하세요(6:18에 시작)](https://support.office.com/article/Video-Create-DNS-records-at-Network-Solutions-for-Office-365-c49698c2-6991-47fb-b5ac-18e49a505099?ui=en-US&amp;rs=en-US&amp;ad=US).</span><span class="sxs-lookup"><span data-stu-id="ba92f-287">Follow the steps below or [watch the video (start at 6:18)](https://support.office.com/article/Video-Create-DNS-records-at-Network-Solutions-for-Office-365-c49698c2-6991-47fb-b5ac-18e49a505099?ui=en-US&amp;rs=en-US&amp;ad=US).</span></span>
  
1. <span data-ttu-id="ba92f-p113">시작하려면 [이 링크](https://www.networksolutions.com/manage-it)를 사용하여 Network Solutions의 도메인 페이지로 이동합니다. 로그인하라는 메시지가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="ba92f-p113">To get started, go to your domains page at Network Solutions by using [this link](https://www.networksolutions.com/manage-it). You'll be prompted to log in.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="ba92f-290">**로그인** 단추를 선택 하기 전에 로그인 **:** 드롭다운 목록에서 **내 도메인 이름 관리** 를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="ba92f-290">Before you select the **Login** button, first choose **Manage My Domain Names** in the **Log In to:** drop-down list.</span></span> 
  
    ![Manage My Domain Names(내 도메인 이름 관리)를 선택하고 Network Solutions에 로그인합니다.](../../media/fda7d4a1-9445-4086-be9c-87c6983ef2aa.png)
  
2. <span data-ttu-id="ba92f-292">수정하려는 도메인 이름 옆의 확인란을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="ba92f-292">Select the check box next to the name of the domain that you are modifying.</span></span>
    
    ![도메인에 대한 확인란을 선택합니다.](../../media/2c13d2ba-4a31-44da-812c-2cc90900a183.png)
  
3. <span data-ttu-id="ba92f-294">**DNS 편집**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="ba92f-294">Select **Edit DNS**.</span></span>
    
    ![DNS 편집을 선택 합니다.](../../media/9d7c269f-48d1-442c-9d7b-63bd384a36a9.png)
  
4. <span data-ttu-id="ba92f-296">**고급 DNS 레코드 관리**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="ba92f-296">Select **Manage Advanced DNS Records**.</span></span>
    
    <span data-ttu-id="ba92f-297">(You may have to scroll down.)</span><span class="sxs-lookup"><span data-stu-id="ba92f-297">(You may have to scroll down.)</span></span>
    
    ![고급 DNS 레코드 관리 선택](../../media/fd2956d6-eec3-47ea-b60a-266bab14f51f.png)
  
5. <span data-ttu-id="ba92f-299">아래로 스크롤하여 **서비스 (Srv 레코드)** 섹션을 찾은 다음 **srv 레코드 편집**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="ba92f-299">Scroll down to the **Service (SRV Records)** section, and then select **Edit SRV Records**.</span></span>
    
    ![서비스 아래에서 SRV 레코드 편집을 선택 합니다.](../../media/9a9248ea-5de5-4e16-9364-f7600fa371f5.png)
  
6. <span data-ttu-id="ba92f-301">두 개의 새 레코드 상자에서 다음 표의 값을 입력하거나 복사하여 붙여넣습니다.</span><span class="sxs-lookup"><span data-stu-id="ba92f-301">In the boxes for the two new records, type or copy and paste the values from the following table.</span></span>
    
    <span data-ttu-id="ba92f-302">(드롭다운 목록에서 **서비스** 및 **프로토콜** 값을 선택합니다.)</span><span class="sxs-lookup"><span data-stu-id="ba92f-302">(Choose the **Service** and **Protocol** values from the drop-down lists.)</span></span> 
    
    |<span data-ttu-id="ba92f-303">**서비스**</span><span class="sxs-lookup"><span data-stu-id="ba92f-303">**Service**</span></span>|<span data-ttu-id="ba92f-304">**프로토콜**</span><span class="sxs-lookup"><span data-stu-id="ba92f-304">**Protocol**</span></span>|<span data-ttu-id="ba92f-305">**TTL**</span><span class="sxs-lookup"><span data-stu-id="ba92f-305">**TTL**</span></span>|<span data-ttu-id="ba92f-306">**Priority(우선 순위)**</span><span class="sxs-lookup"><span data-stu-id="ba92f-306">**Priority**</span></span>|<span data-ttu-id="ba92f-307">**Weight(가중치)**</span><span class="sxs-lookup"><span data-stu-id="ba92f-307">**Weight**</span></span>|<span data-ttu-id="ba92f-308">**Port(포트)**</span><span class="sxs-lookup"><span data-stu-id="ba92f-308">**Port**</span></span>|<span data-ttu-id="ba92f-309">**대상**</span><span class="sxs-lookup"><span data-stu-id="ba92f-309">**Target**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="ba92f-310">_sip</span><span class="sxs-lookup"><span data-stu-id="ba92f-310">_sip</span></span>  <br/> |<span data-ttu-id="ba92f-311">_tls</span><span class="sxs-lookup"><span data-stu-id="ba92f-311">_tls</span></span>  <br/> |<span data-ttu-id="ba92f-312">3600</span><span class="sxs-lookup"><span data-stu-id="ba92f-312">3600</span></span>  <br/> |<span data-ttu-id="ba92f-313">100</span><span class="sxs-lookup"><span data-stu-id="ba92f-313">100</span></span>  <br/> |<span data-ttu-id="ba92f-314">1 </span><span class="sxs-lookup"><span data-stu-id="ba92f-314">1</span></span>  <br/> |<span data-ttu-id="ba92f-315">443</span><span class="sxs-lookup"><span data-stu-id="ba92f-315">443</span></span>  <br/> |<span data-ttu-id="ba92f-316">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="ba92f-316">sipdir.online.lync.com.</span></span>  <br/> <span data-ttu-id="ba92f-317">**이 값은 마침표(.)로 끝나야 합니다.**</span><span class="sxs-lookup"><span data-stu-id="ba92f-317">**This value MUST end with a period (.)**</span></span> <br/> |
    |<span data-ttu-id="ba92f-318">_sipfederationtls</span><span class="sxs-lookup"><span data-stu-id="ba92f-318">_sipfederationtls</span></span>  <br/> |<span data-ttu-id="ba92f-319">_tcp</span><span class="sxs-lookup"><span data-stu-id="ba92f-319">_tcp</span></span>  <br/> |<span data-ttu-id="ba92f-320">3600</span><span class="sxs-lookup"><span data-stu-id="ba92f-320">3600</span></span>  <br/> |<span data-ttu-id="ba92f-321">100</span><span class="sxs-lookup"><span data-stu-id="ba92f-321">100</span></span>  <br/> |<span data-ttu-id="ba92f-322">1 </span><span class="sxs-lookup"><span data-stu-id="ba92f-322">1</span></span>  <br/> |<span data-ttu-id="ba92f-323">5061</span><span class="sxs-lookup"><span data-stu-id="ba92f-323">5061</span></span>  <br/> |<span data-ttu-id="ba92f-324">sipfed.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="ba92f-324">sipfed.online.lync.com.</span></span>  <br/> <span data-ttu-id="ba92f-325">**This value MUST end with a period (.)**</span><span class="sxs-lookup"><span data-stu-id="ba92f-325">**This value MUST end with a period (.)**</span></span> <br/> |
       
    ![새 레코드 값 입력 또는 붙여넣기](../../media/86968d1c-8e43-4e61-aeaa-37fc7d7ef7a7.png)
  
7. <span data-ttu-id="ba92f-327">**계속**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="ba92f-327">Select **Continue**.</span></span>
    
    ![계속을 선택](../../media/bfe2c778-5d2b-4bb6-a79d-c3ff9caf9e1e.png)
  
8. <span data-ttu-id="ba92f-329">**변경 내용 저장**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="ba92f-329">Select **Save Changes**.</span></span>
    
    ![변경 내용 저장을 선택 합니다.](../../media/6d323126-0ebe-45ab-8567-c234711d84c7.png)
  
> [!NOTE]
>  <span data-ttu-id="ba92f-p114">일반적으로 DNS 변경 내용을 적용하는 데 15분 정도 걸립니다. 그러나 변경한 내용이 인터넷의 DNS 시스템 전체에 업데이트되는 데에는 시간이 오래 걸릴 수 있습니다. DNS 레코드를 추가한 후 메일 흐름이나 기타 문제가 있는 경우 [도메인 이름 또는 DNS 레코드 변경 후 발생한 문제 해결](../get-help-with-domains/find-and-fix-issues.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="ba92f-p114">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
