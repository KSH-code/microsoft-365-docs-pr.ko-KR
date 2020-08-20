---
title: 내부 관리자 작업 수행
f1.keywords:
- CSH
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
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: b9707ec8-2247-4e25-9bad-f11ddbc686e4
description: Microsoft 365에서 관리되지 않는 테넌트를 수행하기 위해 전자 메일 및 도메인 소유권을 확인하는 방법을 알아봅니다.
ms.openlocfilehash: 9c1d98616b10737553060bcbad62df9b3b4c0c9a
ms.sourcegitcommit: 167c05cc6a776f62f0a0c2de5f3ffeb68c4a27ac
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/19/2020
ms.locfileid: "46814471"
---
# <a name="perform-an-internal-admin-takeover"></a><span data-ttu-id="56885-103">내부 관리자 작업 수행</span><span class="sxs-lookup"><span data-stu-id="56885-103">Perform an internal admin takeover</span></span>

 <span data-ttu-id="56885-104">원하는 정보를 찾지 못한 경우 **[도메인 FAQ를 확인](../setup/domains-faq.md)** 하세요.</span><span class="sxs-lookup"><span data-stu-id="56885-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span> 

<span data-ttu-id="56885-105">관리자이며 셀프 서비스 사용자 등록으로 만들어진 관리되지 않는 테넌트에 대한 수용하려면 내부 관리자 인수를 사용하여 이 작업을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="56885-105">If you are an admin and want to take over an unmanaged tenant created by a self-service user signup, you can do this with an internal admin takeover.</span></span>

> [!NOTE]
> <span data-ttu-id="56885-106">Azure AD를 사용하는 모든 클라우드 서비스에 대한 셀프 서비스 등록은 관리되지 않는 또는 "섀도" Azure AD 디렉터리에 사용자를 추가하고 관리되지 않는 테넌트를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="56885-106">A self-service sign up for any cloud service that uses Azure AD will add the user to an unmanaged or "shadow" Azure AD directory and create an unmanaged tenant.</span></span> <span data-ttu-id="56885-107">관리되지 않는 테넌트는 전역 관리자가 없는 디렉터리입니다.</span><span class="sxs-lookup"><span data-stu-id="56885-107">An unmanaged tenant is a directory without a global administrator.</span></span> <span data-ttu-id="56885-108">테넌트가 관리되는지, 관리되지 않는지 확인하려면 [테넌트 유형 확인을 참조하세요.](https://docs.microsoft.com/power-platform/admin/powerapps-gdpr-dsr-guide-systemlogs#determining-tenant-type)</span><span class="sxs-lookup"><span data-stu-id="56885-108">To determine whether a tenant is managed or unmanaged, please see [Determining Tenant Type](https://docs.microsoft.com/power-platform/admin/powerapps-gdpr-dsr-guide-systemlogs#determining-tenant-type).</span></span> 
  
## <a name="step-1-verify-your-email-address"></a><span data-ttu-id="56885-109">1단계: 전자 메일 주소 확인</span><span class="sxs-lookup"><span data-stu-id="56885-109">Step 1: Verify your email address</span></span>

> [!NOTE]
> <span data-ttu-id="56885-110">테넌트에서 셀프 서비스를 활성화한 경우 사용자는 자체적으로 Power BI와 같은 무료 서비스를 구독할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="56885-110">If self-service is enabled in your tenant, users can subscribe to free services, such as Power BI, on their own.</span></span> <span data-ttu-id="56885-111">이 단계에서는 셀프 서비스 사용자 구독에서 관리자로 수행하려는 관리되지 않는 테넌트를 만들었다고 가정합니다. 첫 번째 단계에서는 관리되지 않는 테넌트에서 사용자 컨텍스트를 만들고 Power BI를 사용하여 관리 인수 경로를 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="56885-111">These steps assume that a self-service user subscription has created the unmanaged tenant you want to take over as admin. In the first step you create a user context in the unmanaged tenant, using Power BI to illustrate the admin takeover path.</span></span>

1. <span data-ttu-id="56885-112">Power BI에 등록하려면 Power BI 사이트로 [이동하고 무료](https://powerbi.com) 시작 평가판(Power **Start Free**  >  **Start free trial** BI Pro를 사용하는 Share point)을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="56885-112">To sign up for Power BI, go to the [Power BI site](https://powerbi.com) and select **Start Free** > **Start free trial** (in Share with Power BI Pro box).</span></span> 

2. <span data-ttu-id="56885-113">조직의 도메인 이름(예: )을 사용하는 사용자 계정을 사용하여 `powerbiadmin@contoso.com` 등록합니다.</span><span class="sxs-lookup"><span data-stu-id="56885-113">Sign up with a user account that uses the domain name of your organization (like `powerbiadmin@contoso.com`).</span></span> <span data-ttu-id="56885-114">계정을 이미 사용 중이면 현재 암호를 사용하여 로그인합니다.</span><span class="sxs-lookup"><span data-stu-id="56885-114">If your account is already in use, sign in using your current password.</span></span>

3. <span data-ttu-id="56885-115">확인 코드가 **확인되는지 확인하고 코드를 입력하여 전자** 메일 주소를 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="56885-115">Check your email for the **verification code** and enter the code to validate your email address.</span></span>
    
## <a name="step-2-create-a-new-account"></a><span data-ttu-id="56885-116">2단계: 새 계정 만들기</span><span class="sxs-lookup"><span data-stu-id="56885-116">Step 2: Create a new account</span></span>

1. <span data-ttu-id="56885-117">확인 코드를 입력하면 새 계정을 만들 수 있는 페이지로 이동됩니다.</span><span class="sxs-lookup"><span data-stu-id="56885-117">When you enter the verification code, you'll be brought to a page where you can create a new account.</span></span> 
    
2. <span data-ttu-id="56885-118">사용할 계정으로 사용자 이름 및 암호 필드를 입력한 다음 시작을 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="56885-118">Fill in the user name and password fields with the account that you want to use, then select **Start**.</span></span> 
    
## <a name="step-3-verify-domain-ownership-and-become-the-admin"></a><span data-ttu-id="56885-119">3단계: 도메인 소유권 확인 및 관리자 입장</span><span class="sxs-lookup"><span data-stu-id="56885-119">Step 3: Verify domain ownership and become the admin</span></span>

1. <span data-ttu-id="56885-120">관리 **마법사가 열립니다.**</span><span class="sxs-lookup"><span data-stu-id="56885-120">The **Become the admin** wizard will open.</span></span> <span data-ttu-id="56885-121">마법사가 시작되지 않으면 관리 타일을 **검색하여** 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="56885-121">If the wizard doesn't start, look for the **Admin** tile and select it.</span></span> 

2. <span data-ttu-id="56885-122">예, **관리자가 고리입니다.**</span><span class="sxs-lookup"><span data-stu-id="56885-122">Select **Yes, I want to be the admin**.</span></span>

3. <span data-ttu-id="56885-123">도메인 등록 기관에 TXT 레코드를 추가하여 사용자가 수행할 도메인을 소유하고 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="56885-123">Verify that you own the domain you want to take over by adding a TXT record to your domain registrar.</span></span> <span data-ttu-id="56885-124">마법사는 추가할 TXT 레코드를 제공하고 등록 기관 웹 사이트에 대한 링크를 제공하고 단계별 지침 링크를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="56885-124">The wizard will give you the TXT record to add, as well as provide a link to your registrar's website, and a link to step-by-step instructions.</span></span>
    
4. <span data-ttu-id="56885-125">등록 기관 사이트에 TXT 레코드를 추가한 후 마법사로 돌아가 **확인을 선택하세요. 레코드를 추가한 것입니다.**</span><span class="sxs-lookup"><span data-stu-id="56885-125">Once you've added the TXT record to your registrar site, return to the wizard and select **Okay, I've added the record**.</span></span>
    
> [!NOTE]
> <span data-ttu-id="56885-126">섀도 테넌트에 대해 이동을 수행하더라도 기존 정보나 서비스에는 영향을 미치지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="56885-126">Taking over the shadow tenant will not impact any existing information or services.</span></span> <span data-ttu-id="56885-127">그러나 도메인에 라이선스가 필요한 서비스를 등록한 사용자가 있는 경우, 관리자 역할을 수행하라는 일부로 해당 사용자를 위한 라이선스를 구입하라는 메시지가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="56885-127">However, if any users in the domain have signed up for services that require a license, you'll be asked to buy licenses for them as part of taking over the admin role.</span></span> <span data-ttu-id="56885-128">관리 설정 프로세스가 완료되면 라이선스를 구입하거나 제거할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="56885-128">You can buy or remove licenses once the admin setup process is finished.</span></span>
  
## <a name="related-articles"></a><span data-ttu-id="56885-129">관련 문서</span><span class="sxs-lookup"><span data-stu-id="56885-129">Related articles</span></span>

<span data-ttu-id="56885-130">YouTube: [Power BI 및 Microsoft 365에 대한 IT 관리자 가리수행을 IT 관리자 조치를 수행하기 위한 3단계](https://www.youtube.com/watch?v=xt5EsrQBZZk)</span><span class="sxs-lookup"><span data-stu-id="56885-130">YouTube: [3 steps to do an IT Admin Takeover for Power BI and Microsoft 365](https://www.youtube.com/watch?v=xt5EsrQBZZk)</span></span>

[<span data-ttu-id="56885-131">Azure AD에서 관리자 관리</span><span class="sxs-lookup"><span data-stu-id="56885-131">Admin takeover in Azure AD</span></span>](https://docs.microsoft.com/azure/active-directory/users-groups-roles/domains-admin-takeover)

[<span data-ttu-id="56885-132">조직에서 셀프 서비스 등록 사용</span><span class="sxs-lookup"><span data-stu-id="56885-132">Using self-service sign up in your organization</span></span>](self-service-sign-up.md)
  
[<span data-ttu-id="56885-133">Power BI 서비스 관리자 역할 이해</span><span class="sxs-lookup"><span data-stu-id="56885-133">Understanding the Power BI service administrator role</span></span>](https://docs.microsoft.com/power-bi/service-admin-role)

