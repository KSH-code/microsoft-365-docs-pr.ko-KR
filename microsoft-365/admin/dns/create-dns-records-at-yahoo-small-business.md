---
title: Yahoo! Microsoft 용 Small Business
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
ms.assetid: 034bd7bc-b098-4c4d-8a93-4d74ff24532a
description: 전자 메일, 비즈니스용 Skype Online 및 Yahoo!의 기타 서비스에 대해 도메인을 확인 하 고 DNS 레코드를 설정 하는 방법을 알아봅니다. Microsoft에는 Small Business가 있습니다.
ms.openlocfilehash: 12efa8f7056f0d06cbf78b2486ea67dc85d2e705
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/21/2020
ms.locfileid: "43629158"
---
# <a name="create-dns-records-at-yahoo-small-business-for-microsoft"></a><span data-ttu-id="e6807-105">Yahoo!</span><span class="sxs-lookup"><span data-stu-id="e6807-105">Create DNS records at Yahoo!</span></span> <span data-ttu-id="e6807-106">Microsoft 용 Small Business</span><span class="sxs-lookup"><span data-stu-id="e6807-106">Small Business for Microsoft</span></span>

 <span data-ttu-id="e6807-107">**원하는 정보는 찾지 못한 경우 [도메인 질문과 대답을 확인](../setup/domains-faq.md)** 하세요.</span><span class="sxs-lookup"><span data-stu-id="e6807-107">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="e6807-p104">Yahoo! Small Business가 DNS 호스팅 공급자였다면 이제 공급자가 Aabaco Small Business라는 점에 유의해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e6807-p104">If Yahoo! Small Business has been your DNS hosting provider, you should be aware that your provider is now Aabaco Small Business.</span></span>
  
<span data-ttu-id="e6807-110">이 문서에 나와 있는 단계를 따라 Aabaco에서 계정을 만들어 DNS의 변경을 적용하고 도메인을 갱신할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e6807-110">Follow the steps in this article to create an account at Aabaco, where you can make DNS changes and renew your domain or domains.</span></span>
  
<span data-ttu-id="e6807-111">[DNS 레코드를 만들기](../get-help-with-domains/create-dns-records-at-any-dns-hosting-provider.md)전에 Aabaco 계정을 만들어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e6807-111">You must create your Aabaco account before you can [create DNS records](../get-help-with-domains/create-dns-records-at-any-dns-hosting-provider.md).</span></span>

  
## <a name="create-an-aabaco-small-business-account"></a><span data-ttu-id="e6807-112">Aabaco Small Business 계정 만들기</span><span class="sxs-lookup"><span data-stu-id="e6807-112">Create an Aabaco Small Business account</span></span>

1. <span data-ttu-id="e6807-113">시작 하려면 [이 링크](https://www.luminate.com/services/)를 사용 하 여 aabaco의 도메인 페이지로 이동 하 여 **Aabaco Small Business 계정 설정을**선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="e6807-113">To get started, go to your domains page at Aabaco by using [this link](https://www.luminate.com/services/), and select **Setup your Aabaco Small Business account**.</span></span>
    
    ![Aabaco Small Business 계정 설정을 선택 합니다.](../../media/d708f272-d42f-40a1-9aaf-d05d8cfd55cf.png)
  
2. <span data-ttu-id="e6807-115">Yahoo!</span><span class="sxs-lookup"><span data-stu-id="e6807-115">Provide your Yahoo!</span></span> <span data-ttu-id="e6807-116">Small Business **Email/YAHOO ID**를 선택한 다음 **I 로봇이 아닌**경우를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="e6807-116">Small Business **Email/Yahoo ID**, and then select **I'm not a robot**.</span></span>
    
    ![Select I am not a robot](../../media/ded4b5dd-4e04-4baa-ae31-8426b5799151.png)
  
3. <span data-ttu-id="e6807-118">**시작**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="e6807-118">Select **Get started**.</span></span>
    
    ![시작을 선택 합니다.](../../media/6674707d-c222-4f0d-bec4-229d39ab2499.png)
  
4. <span data-ttu-id="e6807-p106">Yahoo! Small Business 전자 메일 계정에 로그인하여 Aabaco Small Business에서 새 전자 메일을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="e6807-p106">Sign in to your Yahoo! Small Business email account and open the new email from Aabaco Small Business.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="e6807-122">필요한 경우 **You've got mail**(메일 도착) 페이지에서 **resend the email link**(전자 메일 다시 보내기 링크)를 선택하여 메시지를 다시 보냅니다.</span><span class="sxs-lookup"><span data-stu-id="e6807-122">Resend the message, if necessary, by choosing the **resend the email link** on the **You've got mail** page.</span></span> 
  
    ![The You've got mail page](../../media/2e02fc30-6cca-40d6-bb64-131a41b4a369.png)
  
5. <span data-ttu-id="e6807-124">Aabaco 전자 메일 **주소 확인** 전자 메일 메시지를 계속 하려면 **전자 메일 확인**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="e6807-124">In the Aabaco **Confirm your email address to continue setup** email message, select **Confirm email**.</span></span>
    
    ![전자 메일 확인을 선택 합니다.](../../media/eb5f5526-6f90-4a10-83a7-5249a1ebd562.png)
  
6. <span data-ttu-id="e6807-126">**Choose your password**(암호 선택) 페이지에서 Aabaco 계정에 사용할 암호를 입력하거나 복사하여 붙여넣습니다.</span><span class="sxs-lookup"><span data-stu-id="e6807-126">On the **Choose your password** page, type or copy and paste the password that you want to use for your Aabaco account.</span></span> 
    
    > [!NOTE]
    > <span data-ttu-id="e6807-p107">Yahoo! Small Business 계정에서 사용한 동일한 암호를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e6807-p107">You can use the same password that you used with your Yahoo! Small Business account.</span></span> 
  
    ![The Choose your password page](../../media/cc592345-72d1-4a41-9410-a1f3345cfd1d.png)
  
7. <span data-ttu-id="e6807-130">동의 **함**을 선택 하 고 **암호 만들기**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="e6807-130">Select **I agree to the terms and conditions**, and then select **Create password**.</span></span>
    
    ![암호 만들기 선택](../../media/434aa6a3-076e-4abf-a9cf-31145786e819.png)
  
8. <span data-ttu-id="e6807-p108">Yahoo! Small Business 전자 메일 계정에 로그인하여 Aabaco Small Business에서 새 전자 메일을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="e6807-p108">Sign in to your Yahoo! Small Business email account, and then open the new email from Aabaco Small Business.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="e6807-p109">필요한 경우 **You're almost done!**(거의 다 되었습니다!) 페이지에서 **resend the email link**(전자 메일 다시 보내기 링크)를 선택하여 메시지를 다시 보냅니다.</span><span class="sxs-lookup"><span data-stu-id="e6807-p109">Resend the message, if necessary, by choosing the **resend the email link** on the **You're almost done!** page.</span></span> 
  
    ![The You're almost done page](../../media/1a4142a3-e140-48a8-9c80-aa126ff08179.png)
  
9. <span data-ttu-id="e6807-137">Aabaco에서 **거의** 모든 전자 메일 메시지에서 **내 계정 활성화**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="e6807-137">In the Aabaco **You're almost there** email message, select **Activate my account**.</span></span>
    
    ![계정 정품 인증을 선택 합니다.](../../media/e76d5edc-d8ba-4d8d-872d-d916716c3618.png)
  
10. <span data-ttu-id="e6807-139">Aabaco Small Business 계정에 로그인합니다.</span><span class="sxs-lookup"><span data-stu-id="e6807-139">Sign in to your Aabaco Small Business account.</span></span>
    
    ![The sign-in page for Aabaco Small Business](../../media/4ef3cfc3-26da-4e03-932b-9346ef217848.png)
  
<span data-ttu-id="e6807-141">Aabaco 계정을 만들었으므로 이제 [Microsoft에 대해 Aabaco Small Business에서 DNS 레코드를 만들](../get-help-with-domains/create-dns-records-at-any-dns-hosting-provider.md)수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e6807-141">Now that you have created your Aabaco account, you can [Create DNS records at Aabaco Small Business for Microsoft](../get-help-with-domains/create-dns-records-at-any-dns-hosting-provider.md).</span></span>
  
