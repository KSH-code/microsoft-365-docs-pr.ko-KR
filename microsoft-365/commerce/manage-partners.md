---
title: 솔루션 공급자 작업
ms.author: cmcatee
author: cmcatee-MSFT
manager: mnirkhe
audience: Admin
ms.topic: article
ms.service: o365-administration <!-- need to figure out what this value should be -->
localization_priority: Normal
ms.collection:
- commerce <!-- probably need to change this -->
ms.custom: ''
search.appverid:
- MET150
description: Microsoft 공인 솔루션 공급자와 협력 하 여 조직 또는 학교에 대 한 제품 및 서비스를 구매 하 고 관리할 수 있습니다.
keywords: 파트너, 솔루션 공급자
ms.openlocfilehash: bb78e1a704529fd2d12ff49639913fe80b75be7a
ms.sourcegitcommit: a7edd3840226e67e82126bb9dee423b3458fef4d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/16/2019
ms.locfileid: "36994079"
---
# <a name="working-with-solution-providers-in-microsoft-store-for-business"></a><span data-ttu-id="da2fe-104">비즈니스를 위한 Microsoft Store에서 솔루션 공급자 작업</span><span class="sxs-lookup"><span data-stu-id="da2fe-104">Working with solution providers in Microsoft Store for Business</span></span>

<span data-ttu-id="da2fe-105">Microsoft 공인 솔루션 공급자와 협력 하 여 조직 또는 학교에 대 한 제품 및 서비스를 구매 하 고 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="da2fe-105">You can work with Microsoft-certified solution providers to purchase and manage products and services for your organization or school.</span></span> <span data-ttu-id="da2fe-106">설정 작업을 수행 하는 데 필요한 몇 가지 단계가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="da2fe-106">There's a few steps involved in getting the things set up.</span></span> 

<span data-ttu-id="da2fe-107">프로세스는 다음과 같이 진행 됩니다.</span><span class="sxs-lookup"><span data-stu-id="da2fe-107">The process goes like this:</span></span>
- <span data-ttu-id="da2fe-108">관리자 비즈니스용 Microsoft Store에서 **솔루션 공급자 찾기를** 사용 하 여 솔루션 공급자를 찾고 연결 합니다.</span><span class="sxs-lookup"><span data-stu-id="da2fe-108">Admins find and contact a solution provider using **Find a solution provider** in Microsoft Store for Business.</span></span> 
- <span data-ttu-id="da2fe-109">솔루션 공급자는 파트너 센터의 요청을 솔루션 공급자가 되기 위해 고객에 게 보냅니다.</span><span class="sxs-lookup"><span data-stu-id="da2fe-109">Solution providers send a request from Partner center to customers to become their solution provider.</span></span>
- <span data-ttu-id="da2fe-110">고객은 Microsoft Store for Business의 초대를 수락 하 고 솔루션 공급자의 작업을 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="da2fe-110">Customers accept the invitation in Microsoft Store for Business and start working with the solution provider.</span></span>
- <span data-ttu-id="da2fe-111">고객은 Microsoft Store for Business의 파트너와의 관계 설정을 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="da2fe-111">Customers can manage settings for the relationship with Partner in Microsoft Store for Business.</span></span> 

## <a name="what-can-a-solution-provider-do-for-my-organization-or-school"></a><span data-ttu-id="da2fe-112">조직 또는 학교에서 솔루션 공급자가 수행할 수 있는 작업은 무엇 인가요?</span><span class="sxs-lookup"><span data-stu-id="da2fe-112">What can a solution provider do for my organization or school?</span></span>

<span data-ttu-id="da2fe-113">솔루션 공급자가 사용 하는 방법에는 여러 가지가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="da2fe-113">There are several ways that a solution provider can work with you.</span></span> <span data-ttu-id="da2fe-114">솔루션 공급자는 사용자와 파트너의 작업 요청을 보낼 때 이러한 항목 중 하나를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="da2fe-114">Solution providers will choose one of these when they send their request to work as a partner with you.</span></span>

| <span data-ttu-id="da2fe-115">Solution provider 함수</span><span class="sxs-lookup"><span data-stu-id="da2fe-115">Solution provider function</span></span> | <span data-ttu-id="da2fe-116">설명</span><span class="sxs-lookup"><span data-stu-id="da2fe-116">Description</span></span> | 
| ------ | ------------------- | 
| <span data-ttu-id="da2fe-117">판매처</span><span class="sxs-lookup"><span data-stu-id="da2fe-117">Reseller</span></span> | <span data-ttu-id="da2fe-118">솔루션 공급자 조직 또는 학교에 Microsoft 제품을 판매 합니다.</span><span class="sxs-lookup"><span data-stu-id="da2fe-118">Solution providers sell Microsoft products to your organization or school.</span></span> |
| <span data-ttu-id="da2fe-119">위임 된 관리자</span><span class="sxs-lookup"><span data-stu-id="da2fe-119">Delegated administrator</span></span> | <span data-ttu-id="da2fe-120">솔루션 공급자 조직 또는 학교에 대 한 제품 및 서비스를 관리 합니다.</span><span class="sxs-lookup"><span data-stu-id="da2fe-120">Solution provider manages products and services for your organization or school.</span></span> <span data-ttu-id="da2fe-121">Azure Active Directory (AD)에서는 파트너가 테 넌 트에 대 한 전역 관리자가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="da2fe-121">In Azure Active Directory (AD), the Partner will be a Global Administrator for tenant.</span></span> <span data-ttu-id="da2fe-122">이를 통해 사용자 계정 만들기, 라이선스 할당 및 관리, 암호 다시 설정 등의 서비스를 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="da2fe-122">This allows them to manage services like creating user accounts, assigning and managing licenses, and password resets.</span></span> |
| <span data-ttu-id="da2fe-123">대리점 & 위임 된 관리자</span><span class="sxs-lookup"><span data-stu-id="da2fe-123">Reseller & delegated administrator</span></span> | <span data-ttu-id="da2fe-124">조직 또는 학교에 Microsoft 제품 및 서비스를 판매 및 관리 하는 솔루션 공급자입니다.</span><span class="sxs-lookup"><span data-stu-id="da2fe-124">Solution providers that sell and manage Microsoft products and services to your organization or school.</span></span> |
| <span data-ttu-id="da2fe-125">Partner</span><span class="sxs-lookup"><span data-stu-id="da2fe-125">Partner</span></span> | <span data-ttu-id="da2fe-126">솔루션 공급자에 게 테 넌 트의 사용자 계정을 제공 하 고 다른 Microsoft 서비스를 대신 하 여 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="da2fe-126">You can give your solution provider a user account in your tenant, and they work on your behalf with other Microsoft services.</span></span> |
| <span data-ttu-id="da2fe-127">MPSA (Microsoft Products & Services 계약) 파트너</span><span class="sxs-lookup"><span data-stu-id="da2fe-127">Microsoft Products & Services Agreement (MPSA) partner</span></span> | <span data-ttu-id="da2fe-128">MPSA 프로그램을 통해 여러 솔루션 공급자를 사용 하는 경우 파트너에 게 각 사용자의 구매를 확인 하도록 허용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="da2fe-128">If you've worked with multiple solution providers through the MPSA program, you can allow partners to see purchases made by each other.</span></span> |
| <span data-ttu-id="da2fe-129">OEM PC 파트너</span><span class="sxs-lookup"><span data-stu-id="da2fe-129">OEM PC partner</span></span> | <span data-ttu-id="da2fe-130">솔루션 공급자는 [Autopilot을 사용 하 여 관리](https://docs.microsoft.com/microsoft-store/add-profile-to-devices)하는 pc에 대 한 장치 id를 업로드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="da2fe-130">Solution providers can upload device IDs for PCs that you're [managing with Autopilot](https://docs.microsoft.com/microsoft-store/add-profile-to-devices).</span></span>   |
| <span data-ttu-id="da2fe-131">LOB (기간 업무) 파트너</span><span class="sxs-lookup"><span data-stu-id="da2fe-131">Line-of-business (LOB) partner</span></span> | <span data-ttu-id="da2fe-132">솔루션 공급자는 조직 또는 학교에 해당 하는 LOB 앱을 개발, 제출 및 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="da2fe-132">Solution providers can develop, submit, and manage LOB apps specific for your organization or school.</span></span> |

## <a name="find-a-solution-provider"></a><span data-ttu-id="da2fe-133">솔루션 공급자 찾기</span><span class="sxs-lookup"><span data-stu-id="da2fe-133">Find a solution provider</span></span>

<span data-ttu-id="da2fe-134">Microsoft Store for Business 및 교육부에서 파트너를 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="da2fe-134">You can find partner in Microsoft Store for Business and Education.</span></span> 

1. <span data-ttu-id="da2fe-135">[Microsoft store For Business](https://businessstore.microsoft.com/) 또는 [Microsoft store for 교육용](https://educationstore.microsoft.com/)으로 로그인 합니다.</span><span class="sxs-lookup"><span data-stu-id="da2fe-135">Sign in to [Microsoft Store for Business](https://businessstore.microsoft.com/) or [Microsoft Store for Education](https://educationstore.microsoft.com/).</span></span>
2. <span data-ttu-id="da2fe-136">**솔루션 공급자 찾기를**선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="da2fe-136">Select **Find a solution provider**.</span></span>
<!---
    ![Image shows Find a solution provider option in Microsoft Store for Business.](images/msfb-find-partner.png)
-->
3. <span data-ttu-id="da2fe-137">목록을 구체화 하거나 솔루션 공급자를 검색 합니다.</span><span class="sxs-lookup"><span data-stu-id="da2fe-137">Refine the list, or search for a solution provider.</span></span> 
<!---
    ![Image shows Find a solution provider option in Microsoft Store for Business.](images/msfb-provider-list.png)
-->
4. <span data-ttu-id="da2fe-138">작업할 솔루션 공급자를 찾았으면 **연락처**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="da2fe-138">When you find a solution provider you're interested in working with, click **Contact**.</span></span>
5. <span data-ttu-id="da2fe-139">양식을 완성 하 고 보냅니다.</span><span class="sxs-lookup"><span data-stu-id="da2fe-139">Complete and send the form.</span></span>

<span data-ttu-id="da2fe-140">솔루션 공급자는 사용자와 함께 연락을 받게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="da2fe-140">The solution provider will get in touch with you.</span></span> <span data-ttu-id="da2fe-141">이러한 항목에 대해 자세히 알아볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="da2fe-141">You'll have a chance to learn more about them.</span></span> <span data-ttu-id="da2fe-142">솔루션 공급자에 대 한 작업을 결정 하면 파트너 센터에서 전자 메일 초대를 받게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="da2fe-142">If you decide to work with the solution provider, they will send you an email invitation from Partner Center.</span></span> 

## <a name="work-with-a-solution-provider"></a><span data-ttu-id="da2fe-143">솔루션 공급자와 작업</span><span class="sxs-lookup"><span data-stu-id="da2fe-143">Work with a solution provider</span></span>

<span data-ttu-id="da2fe-144">솔루션 공급자를 찾아서 사용 하도록 결정 하면 파트너 센터에서 함께 작업할 수 있는 초대장이 전송 됩니다.</span><span class="sxs-lookup"><span data-stu-id="da2fe-144">Once you've found a solution provider and decided to work with them, they'll send you an invitation to work together from Partner Center.</span></span> <span data-ttu-id="da2fe-145">Microsoft Store for Business 또는 교육용 경우 초대를 수락 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="da2fe-145">In Microsoft Store for Business or Education, you'll need to accept the invitation.</span></span> <span data-ttu-id="da2fe-146">그런 다음 해당 사용 권한을 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="da2fe-146">After that, you can manage their permissions.</span></span>

<span data-ttu-id="da2fe-147">**솔루션 공급자 초대를 수락 하려면**</span><span class="sxs-lookup"><span data-stu-id="da2fe-147">**To accept a solution provider invitation**</span></span>
1. <span data-ttu-id="da2fe-148">**전자 메일 연결 팔 로우** -솔루션 공급자의 솔루션 공급자 초대를 수락 하는 링크가 포함 된 전자 메일을 받습니다.</span><span class="sxs-lookup"><span data-stu-id="da2fe-148">**Follow email link** - You'll receive an email with a link to accept the solution provider invitation from your solution provider.</span></span> <span data-ttu-id="da2fe-149">이 링크를 사용 하 여 Microsoft Store for Business 또는 교육용으로 이동할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="da2fe-149">The link will take you to Microsoft Store for Business or Education.</span></span>
2. <span data-ttu-id="da2fe-150">**초대 수락** **파트너 초대**허용에서 초대를 수락 하 고, Microsoft 클라우드 계약의 약관에 동의한 다음, 솔루션 공급자의 작업을 시작할 수 있는 **권한을** 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="da2fe-150">**Accept invitation** - On **Accept Partner Invitation**, select **Authorize** to accept the invitation, accept terms of the Microsoft Cloud Agreement, and start working with the solution provider.</span></span> 
<!---
![Image shows accepting an invitation from a solution provider in Microsoft Store for Business.](images/msft-accept-partner.png)
--> 
## <a name="delegate-admin-privileges"></a><span data-ttu-id="da2fe-151">관리자 권한 위임</span><span class="sxs-lookup"><span data-stu-id="da2fe-151">Delegate admin privileges</span></span>

<span data-ttu-id="da2fe-152">솔루션 공급자의 요청에 따라 초대를 수락 하는 과정에는 솔루션 공급자에 게 위임 된 관리자 권한을 부여 하는 것에 대 한 동의 (합의)가 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="da2fe-152">Depending on the request made by the solution provider, part of accepting the invitation will include agreeing to give delegated admin privileges to the solution provider.</span></span> <span data-ttu-id="da2fe-153">솔루션 공급자 요청이 위임 된 관리자 역할을 하는 경우에이 작업이 수행 됩니다.</span><span class="sxs-lookup"><span data-stu-id="da2fe-153">This will happen when the solution provider request includes acting as a delegated administrator.</span></span> <span data-ttu-id="da2fe-154">자세한 내용은 [AZURE AD에서 위임 된 관리 권한을](https://docs.microsoft.com/partner-center/customers_revoke_admin_privileges#delegated-admin-privileges-in-azure-ad)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="da2fe-154">For more information, see [Delegated admin privileges in Azure AD](https://docs.microsoft.com/partner-center/customers_revoke_admin_privileges#delegated-admin-privileges-in-azure-ad).</span></span> 

<span data-ttu-id="da2fe-155">솔루션 공급자에 게 관리자 권한을 위임 하지 않으려면 초대를 수락 하는 대신 취소 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="da2fe-155">If you don't want to delegate admin privileges to the solution provider, you'll need to cancel the invitation instead of accepting it.</span></span> 

<span data-ttu-id="da2fe-156">솔루션 공급자에 게 관리자 권한을 위임 하는 경우 나중에이를 제거할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="da2fe-156">If you delegate admin privileges to a solution provider, you can remove that later.</span></span> 

<span data-ttu-id="da2fe-157">**대리인 관리 권한을 제거 하려면**</span><span class="sxs-lookup"><span data-stu-id="da2fe-157">**To remove delegate admin privileges**</span></span>
1. <span data-ttu-id="da2fe-158">[Microsoft store For Business](https://businessstore.microsoft.com/) 또는 [Microsoft store for 교육용](https://educationstore.microsoft.com/)으로 로그인 합니다.</span><span class="sxs-lookup"><span data-stu-id="da2fe-158">Sign in to [Microsoft Store for Business](https://businessstore.microsoft.com/) or [Microsoft Store for Education](https://educationstore.microsoft.com/).</span></span>
2. <span data-ttu-id="da2fe-159">**파트너** 선택</span><span class="sxs-lookup"><span data-stu-id="da2fe-159">Select **Partner**</span></span>
3. <span data-ttu-id="da2fe-160">관리할 파트너를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="da2fe-160">Choose the Partner you want to manage.</span></span>
4. <span data-ttu-id="da2fe-161">**위임 된 사용 권한 제거**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="da2fe-161">Select **Remove Delegated Permissions**.</span></span> 

<span data-ttu-id="da2fe-162">이 경우에도 해당 솔루션 공급자는 대리점과 같은 방식으로 작업할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="da2fe-162">The solution provider will still be able to work with you, for example, as a Reseller.</span></span> 
