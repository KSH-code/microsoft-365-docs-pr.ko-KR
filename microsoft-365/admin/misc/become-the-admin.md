---
title: 내부 관리자 인계 수행
f1.keywords:
- CSH
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
ms.assetid: b9707ec8-2247-4e25-9bad-f11ddbc686e4
description: 전자 메일 및 도메인 소유권을 확인하여 해당 도메인에서 셀프 서비스 사용자 등록으로 만든 관리되지 않는 테넌트의 소유권을 Microsoft 365.
ms.openlocfilehash: aa44023ffdc2b59e4db024706323c5b872566260
ms.sourcegitcommit: 17f0aada83627d9defa0acf4db03a2d58e46842f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/24/2021
ms.locfileid: "52635989"
---
# <a name="perform-an-internal-admin-takeover"></a><span data-ttu-id="c9e0c-103">내부 관리자 인계 수행</span><span class="sxs-lookup"><span data-stu-id="c9e0c-103">Perform an internal admin takeover</span></span>

 <span data-ttu-id="c9e0c-104">원하는 정보를 찾지 못한 경우 **[도메인 FAQ를 확인](../setup/domains-faq.yml)** 하세요.</span><span class="sxs-lookup"><span data-stu-id="c9e0c-104">**[Check the Domains FAQ](../setup/domains-faq.yml)** if you don't find what you're looking for.</span></span> 

<span data-ttu-id="c9e0c-105">관리자인 경우 셀프 서비스 사용자 등록으로 만든 관리되지 않는 테넌트의 인계를 원할 경우 내부 관리자 인계를 통해 이 작업을 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c9e0c-105">If you are an admin and want to take over an unmanaged tenant created by a self-service user signup, you can do this with an internal admin takeover.</span></span>

> [!NOTE]
> <span data-ttu-id="c9e0c-106">Azure AD를 사용하는 모든 클라우드 서비스에 대한 셀프 서비스 등록은 사용자를 관리되지 않는 또는 "섀도" Azure AD 디렉터리에 추가하고 관리되지 않는 테넌트를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="c9e0c-106">A self-service sign up for any cloud service that uses Azure AD will add the user to an unmanaged or "shadow" Azure AD directory and create an unmanaged tenant.</span></span> <span data-ttu-id="c9e0c-107">관리되지 않는 테넌트는 전역 관리자가 없는 디렉터리입니다.</span><span class="sxs-lookup"><span data-stu-id="c9e0c-107">An unmanaged tenant is a directory without a global administrator.</span></span> <span data-ttu-id="c9e0c-108">테넌트가 관리되는지 또는 관리되지 않는지 확인 내용은 Determining Tenant Type (테넌트 유형 결정)을 [참조하시기 바랍니다.](/power-platform/admin/powerapps-gdpr-dsr-guide-systemlogs#determining-tenant-type)</span><span class="sxs-lookup"><span data-stu-id="c9e0c-108">To determine whether a tenant is managed or unmanaged, please see [Determining Tenant Type](/power-platform/admin/powerapps-gdpr-dsr-guide-systemlogs#determining-tenant-type).</span></span> 
  
## <a name="step-1-verify-your-email-address"></a><span data-ttu-id="c9e0c-109">1단계: 전자 메일 주소 확인</span><span class="sxs-lookup"><span data-stu-id="c9e0c-109">Step 1: Verify your email address</span></span>

> [!NOTE]
> <span data-ttu-id="c9e0c-110">테넌트에서 셀프 서비스가 사용하도록 설정된 경우 사용자는 자체적으로 무료 서비스(예: Power BI 구독할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c9e0c-110">If self-service is enabled in your tenant, users can subscribe to free services, such as Power BI, on their own.</span></span> <span data-ttu-id="c9e0c-111">이 단계에서는 셀프 서비스 사용자 구독이 관리자 권한으로 인계할 관리되지 않는 테넌트가 만들어졌다고 가정합니다. 첫 번째 단계에서는 관리되지 않는 테넌트에서 사용자 컨텍스트를 만들고 관리자 Power BI 방법을 보여 주게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c9e0c-111">These steps assume that a self-service user subscription has created the unmanaged tenant you want to take over as admin. In the first step you create a user context in the unmanaged tenant, using Power BI to illustrate the admin takeover path.</span></span>

1. <span data-ttu-id="c9e0c-112">등록하려면 Power BI 사이트로 이동하여 무료 [](https://powerbi.com) Power BI 시작 무료 평가판 시작(공유 대상 Power BI Pro  >   상자)을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="c9e0c-112">To sign up for Power BI, go to the [Power BI site](https://powerbi.com) and select **Start Free** > **Start free trial** (in Share with Power BI Pro box).</span></span> 

2. <span data-ttu-id="c9e0c-113">조직의 도메인 이름(예: )을 사용하는 사용자 계정으로 `powerbiadmin@contoso.com` 등록합니다.</span><span class="sxs-lookup"><span data-stu-id="c9e0c-113">Sign up with a user account that uses the domain name of your organization (like `powerbiadmin@contoso.com`).</span></span> <span data-ttu-id="c9e0c-114">계정이 이미 사용 중인 경우 현재 암호를 사용하여 로그인합니다.</span><span class="sxs-lookup"><span data-stu-id="c9e0c-114">If your account is already in use, sign in using your current password.</span></span>

3. <span data-ttu-id="c9e0c-115">전자 메일에서 확인 **코드를 확인하고** 코드를 입력하여 전자 메일 주소의 유효성을 검사합니다.</span><span class="sxs-lookup"><span data-stu-id="c9e0c-115">Check your email for the **verification code** and enter the code to validate your email address.</span></span>
    
## <a name="step-2-create-a-new-account"></a><span data-ttu-id="c9e0c-116">2단계: 새 계정 만들기</span><span class="sxs-lookup"><span data-stu-id="c9e0c-116">Step 2: Create a new account</span></span>

1. <span data-ttu-id="c9e0c-117">인증 코드를 입력하면 새 계정을 만들 수 있는 페이지로 이동됩니다.</span><span class="sxs-lookup"><span data-stu-id="c9e0c-117">When you enter the verification code, you'll be brought to a page where you can create a new account.</span></span> 
    
2. <span data-ttu-id="c9e0c-118">사용할 계정으로 사용자 이름 및 암호 필드를 입력한 다음 시작 을 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="c9e0c-118">Fill in the user name and password fields with the account that you want to use, then select **Start**.</span></span> 
    
## <a name="step-3-verify-domain-ownership-and-become-the-admin"></a><span data-ttu-id="c9e0c-119">3단계: 도메인 소유권 확인 및 관리자 되기</span><span class="sxs-lookup"><span data-stu-id="c9e0c-119">Step 3: Verify domain ownership and become the admin</span></span>

1. <span data-ttu-id="c9e0c-120">관리자 **되기 마법사가** 열립니다.</span><span class="sxs-lookup"><span data-stu-id="c9e0c-120">The **Become the admin** wizard will open.</span></span> <span data-ttu-id="c9e0c-121">마법사가 시작되지 않는 경우 관리 **타일을 찾아** 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="c9e0c-121">If the wizard doesn't start, look for the **Admin** tile and select it.</span></span> 

2. <span data-ttu-id="c9e0c-122">예, **관리자 를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="c9e0c-122">Select **Yes, I want to be the admin**.</span></span>

3. <span data-ttu-id="c9e0c-123">도메인 등록 기관에 TXT 레코드를 추가하여 인계할 도메인을 소유하고 있는지 확인해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c9e0c-123">Verify that you own the domain you want to take over by adding a TXT record to your domain registrar.</span></span> <span data-ttu-id="c9e0c-124">마법사는 추가할 TXT 레코드를 제공할 뿐만 아니라 등록 기관의 웹 사이트에 대한 링크와 단계별 지침에 대한 링크를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="c9e0c-124">The wizard will give you the TXT record to add, as well as provide a link to your registrar's website, and a link to step-by-step instructions.</span></span>
    
4. <span data-ttu-id="c9e0c-125">등록 기관 사이트에 TXT 레코드를 추가한 후 마법사로 돌아가서 레코드를 **추가했습니다.를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="c9e0c-125">Once you've added the TXT record to your registrar site, return to the wizard and select **Okay, I've added the record**.</span></span>
    
> [!NOTE]
> <span data-ttu-id="c9e0c-126">섀도 테넌트의 인계는 기존 정보나 서비스에 영향을 미치지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c9e0c-126">Taking over the shadow tenant will not impact any existing information or services.</span></span> <span data-ttu-id="c9e0c-127">그러나 도메인의 사용자가 라이선스가 필요한 서비스에 등록한 경우 관리자 역할의 일부로 해당 사용자에 대한 라이선스를 구입해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c9e0c-127">However, if any users in the domain have signed up for services that require a license, you'll be asked to buy licenses for them as part of taking over the admin role.</span></span> <span data-ttu-id="c9e0c-128">관리자 설정 프로세스가 완료되면 라이선스를 구입하거나 제거할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c9e0c-128">You can buy or remove licenses once the admin setup process is finished.</span></span>
  
## <a name="related-content"></a><span data-ttu-id="c9e0c-129">관련 콘텐츠</span><span class="sxs-lookup"><span data-stu-id="c9e0c-129">Related content</span></span>

<span data-ttu-id="c9e0c-130">YouTube: 사용자 및 사용자에 대한 IT 관리자 인계를 Power BI [3단계(Microsoft 365)\](https://www.youtube.com/watch?v=xt5EsrQBZZk)</span><span class="sxs-lookup"><span data-stu-id="c9e0c-130">YouTube: [3 steps to do an IT Admin Takeover for Power BI and Microsoft 365](https://www.youtube.com/watch?v=xt5EsrQBZZk) (video)\</span></span>
<span data-ttu-id="c9e0c-131">[Azure AD의 관리자](/azure/active-directory/users-groups-roles/domains-admin-takeover) 인계(문서)</span><span class="sxs-lookup"><span data-stu-id="c9e0c-131">[Admin takeover in Azure AD](/azure/active-directory/users-groups-roles/domains-admin-takeover) (article)</span></span>\
<span data-ttu-id="c9e0c-132">[조직에서 셀프 서비스](self-service-sign-up.md) 등록 사용(문서)</span><span class="sxs-lookup"><span data-stu-id="c9e0c-132">[Using self-service sign up in your organization](self-service-sign-up.md) (article)</span></span>\
<span data-ttu-id="c9e0c-133">[서비스 Power BI 역할](/power-bi/service-admin-role) 이해(문서)</span><span class="sxs-lookup"><span data-stu-id="c9e0c-133">[Understanding the Power BI service administrator role](/power-bi/service-admin-role) (article)</span></span>