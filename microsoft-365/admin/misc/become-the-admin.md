---
title: 내부 관리 인수 수행
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
description: Microsoft 365에서 관리 되지 않는 테 넌 트를 사용 하도록 전자 메일 및 도메인 소유권을 확인 하는 방법을 알아봅니다.
ms.openlocfilehash: 4c2dcdb0f6c4f6b795d9579c8796e9668ed2ed05
ms.sourcegitcommit: 2d59b24b877487f3b84aefdc7b1e200a21009999
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/27/2020
ms.locfileid: "44399449"
---
# <a name="perform-an-internal-admin-takeover"></a><span data-ttu-id="71618-103">내부 관리 인수 수행</span><span class="sxs-lookup"><span data-stu-id="71618-103">Perform an internal admin takeover</span></span>

 <span data-ttu-id="71618-104">원하는 정보를 찾지 못한 경우 **[도메인 FAQ를 확인](../setup/domains-faq.md)** 하세요.</span><span class="sxs-lookup"><span data-stu-id="71618-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span> 

<span data-ttu-id="71618-105">관리자 인 경우 셀프 서비스 사용자 등록으로 만든 관리 되지 않는 테 넌 트를 사용 하려는 경우에는 내부 관리자 인수을 사용 하 여이 작업을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="71618-105">If you are an admin and want to take over an unmanaged tenant created by a self-service user signup, you can do this with an internal admin takeover.</span></span>

> [!NOTE]
> <span data-ttu-id="71618-106">Azure AD를 사용 하는 모든 클라우드 서비스에 대 한 셀프 서비스 등록은 관리 되지 않거나 "섀도" Azure AD 디렉터리에 사용자를 추가 하 고 관리 되지 않는 테 넌 트를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="71618-106">A self-service sign up for any cloud service that uses Azure AD will add the user to an unmanaged or "shadow" Azure AD directory and create an unmanaged tenant.</span></span> <span data-ttu-id="71618-107">관리 되지 않는 테 넌 트는 전역 관리자가 없는 디렉터리입니다.</span><span class="sxs-lookup"><span data-stu-id="71618-107">An unmanaged tenant is a directory without a global administrator.</span></span> <span data-ttu-id="71618-108">테 넌 트가 관리 또는 관리 되지 않는지 여부를 확인 하려면 [테 넌 트 유형 확인](https://docs.microsoft.com/power-platform/admin/powerapps-gdpr-dsr-guide-systemlogs#determining-tenant-type)을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="71618-108">To determine whether a tenant is managed or unmanaged, please see [Determining Tenant Type](https://docs.microsoft.com/power-platform/admin/powerapps-gdpr-dsr-guide-systemlogs#determining-tenant-type).</span></span> 
  
## <a name="step-1-verify-your-email-address"></a><span data-ttu-id="71618-109">1 단계: 전자 메일 주소 확인</span><span class="sxs-lookup"><span data-stu-id="71618-109">Step 1: Verify your email address</span></span>

> [!NOTE]
> <span data-ttu-id="71618-110">테 넌 트에서 셀프 서비스를 사용 하도록 설정한 경우 사용자는 Power BI와 같은 무료 서비스를 자체에 등록할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="71618-110">If self-service is enabled in your tenant, users can subscribe to free services, such as Power BI, on their own.</span></span> <span data-ttu-id="71618-111">이 단계에서는 셀프 서비스 사용자 구독이 관리자로 수행 하려는 관리 되지 않는 테 넌 트를 만든 것으로 가정 합니다. 첫 번째 단계에서는 관리자 인수 경로를 보여 주기 위해 Power BI를 사용 하 여 관리 되지 않는 테 넌 트에서 사용자 컨텍스트를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="71618-111">These steps assume that a self-service user subscription has created the unmanaged tenant you want to take over as admin. In the first step you create a user context in the unmanaged tenant, using Power BI to illustrate the admin takeover path.</span></span>

1. <span data-ttu-id="71618-112">Power bi에 등록 하려면 [power bi 사이트로](https://powerbi.com) 이동한 후 **무료**  >  **시작 무료 평가판** 시작 (power bi Pro를 사용 하 여 공유)을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="71618-112">To sign up for Power BI, go to the [Power BI site](https://powerbi.com) and select **Start Free** > **Start free trial** (in Share with Power BI Pro box).</span></span> 

2. <span data-ttu-id="71618-113">조직의 도메인 이름을 사용 하는 사용자 계정으로 등록 합니다 (like `powerbiadmin@contoso.com` ).</span><span class="sxs-lookup"><span data-stu-id="71618-113">Sign up with a user account that uses the domain name of your organization (like `powerbiadmin@contoso.com`).</span></span> <span data-ttu-id="71618-114">계정이 이미 사용 중인 경우 현재 암호를 사용 하 여 로그인 합니다.</span><span class="sxs-lookup"><span data-stu-id="71618-114">If your account is already in use, sign in using your current password.</span></span>

3. <span data-ttu-id="71618-115">전자 메일에서 **확인 코드** 를 확인 하 고 코드를 입력 하 여 전자 메일 주소를 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="71618-115">Check your email for the **verification code** and enter the code to validate your email address.</span></span>
    
## <a name="step-2-create-a-new-account"></a><span data-ttu-id="71618-116">2 단계: 새 계정 만들기</span><span class="sxs-lookup"><span data-stu-id="71618-116">Step 2: Create a new account</span></span>

1. <span data-ttu-id="71618-117">확인 코드를 입력 하면 새 계정을 만들 수 있는 페이지로 전환 됩니다.</span><span class="sxs-lookup"><span data-stu-id="71618-117">When you enter the verification code, you'll be brought to a page where you can create a new account.</span></span> 
    
2. <span data-ttu-id="71618-118">사용할 계정으로 사용자 이름 및 암호 필드를 입력 한 다음 **시작**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="71618-118">Fill in the user name and password fields with the account that you want to use, then select **Start**.</span></span> 
    
## <a name="step-3-verify-domain-ownership-and-become-the-admin"></a><span data-ttu-id="71618-119">3 단계: 도메인 소유권 확인 및 관리자 되기</span><span class="sxs-lookup"><span data-stu-id="71618-119">Step 3: Verify domain ownership and become the admin</span></span>

1. <span data-ttu-id="71618-120">**관리자가 되기** 시작 마법사가 열립니다.</span><span class="sxs-lookup"><span data-stu-id="71618-120">The **Become the admin** wizard will open.</span></span> <span data-ttu-id="71618-121">마법사가 시작 되지 않으면 **관리** 타일을 찾아 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="71618-121">If the wizard doesn't start, look for the **Admin** tile and select it.</span></span> 

2. <span data-ttu-id="71618-122">**예, 관리자에 게**싶습니다 .를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="71618-122">Select **Yes, I want to be the admin**.</span></span>

3. <span data-ttu-id="71618-123">도메인 등록 기관에 TXT 레코드를 추가 하 여 수행할 도메인을 소유 하 고 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="71618-123">Verify that you own the domain you want to take over by adding a TXT record to your domain registrar.</span></span> <span data-ttu-id="71618-124">마법사가 추가할 TXT 레코드를 제공 하 고, 등록자 웹 사이트에 대 한 링크 및 단계별 지침 링크를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="71618-124">The wizard will give you the TXT record to add, as well as provide a link to your registrar's website, and a link to step-by-step instructions.</span></span>
    
4. <span data-ttu-id="71618-125">사용자가 등록자 사이트에 TXT 레코드를 추가 했으면 마법사로 돌아간 다음 확인을 선택 하 **여 레코드를 추가 했다고 가정**합니다.</span><span class="sxs-lookup"><span data-stu-id="71618-125">Once you've added the TXT record to your registrar site, return to the wizard and select **Okay, I've added the record**.</span></span>
    
> [!NOTE]
> <span data-ttu-id="71618-126">섀도 테 넌 트를 이용 해도 기존 정보나 서비스에는 영향을 주지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="71618-126">Taking over the shadow tenant will not impact any existing information or services.</span></span> <span data-ttu-id="71618-127">그러나 도메인의 사용자가 라이선스를 요구 하는 서비스에 등록 된 경우 관리자 역할을 수행 하는 동안 라이선스를 구입 하 라는 메시지가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="71618-127">However, if any users in the domain have signed up for services that require a license, you'll be asked to buy licenses for them as part of taking over the admin role.</span></span> <span data-ttu-id="71618-128">관리자 설정 프로세스가 완료 되 면 라이선스를 추가 하거나 제거할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="71618-128">You can add or remove licenses once the admin setup process is finished.</span></span> 
  
## <a name="related-articles"></a><span data-ttu-id="71618-129">관련 문서</span><span class="sxs-lookup"><span data-stu-id="71618-129">Related articles</span></span>

<span data-ttu-id="71618-130">YouTube: [POWER BI 및 Microsoft 365에 대 한 IT 관리자 인수를 수행 하는 3 단계](https://www.youtube.com/watch?v=xt5EsrQBZZk)</span><span class="sxs-lookup"><span data-stu-id="71618-130">YouTube: [3 steps to do an IT Admin Takeover for Power BI and Microsoft 365](https://www.youtube.com/watch?v=xt5EsrQBZZk)</span></span>

[<span data-ttu-id="71618-131">Azure AD의 관리 인수</span><span class="sxs-lookup"><span data-stu-id="71618-131">Admin takeover in Azure AD</span></span>](https://docs.microsoft.com/azure/active-directory/users-groups-roles/domains-admin-takeover)

[<span data-ttu-id="71618-132">도메인 도움말 보기</span><span class="sxs-lookup"><span data-stu-id="71618-132">Get help with domains</span></span>](../get-help-with-domains/get-help-with-domains.md)

[<span data-ttu-id="71618-133">조직에서 셀프 서비스 등록 사용</span><span class="sxs-lookup"><span data-stu-id="71618-133">Using self-service sign up in your organization</span></span>](self-service-sign-up.md)
  
[<span data-ttu-id="71618-134">Power BI 서비스 관리자 역할 이해</span><span class="sxs-lookup"><span data-stu-id="71618-134">Understanding the Power BI service administrator role</span></span>](https://docs.microsoft.com/power-bi/service-admin-role)

