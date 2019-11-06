---
title: Office 365 Business Premium에서 Microsoft 365 Business로 업그레이드
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Adm_O365
- M365-subscription-management
ms.custom:
- Core_O365Admin_Migration
- MiniMaven
- MSB365
- OKR_SMB_M365
search.appverid:
- BCS160
- MET150
ms.assetid: 5b4ba843-24b8-4526-8e1f-f9b9eab89d06
description: Office 365 Business Premium에서 Microsoft 365 Business로 비즈니스를 업그레이드 하는 단계입니다.
ms.openlocfilehash: 1e337b908f848da1d33cbd8e662652550d302b14
ms.sourcegitcommit: 0fa897d06b664c0ed005817752da1426d4ee17cb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/06/2019
ms.locfileid: "38002132"
---
# <a name="upgrade-to-microsoft-365-business-from-office-365-business-premium"></a><span data-ttu-id="1b5ab-103">Office 365 Business Premium에서 Microsoft 365 Business로 업그레이드</span><span class="sxs-lookup"><span data-stu-id="1b5ab-103">Upgrade to Microsoft 365 Business from Office 365 Business Premium</span></span>

<span data-ttu-id="1b5ab-104">Office 365 Business Premium과 같은 [비즈니스용 office 365](https://products.office.com/compare-all-microsoft-office-products-4-column?activetab=tab:primaryr2)이 있는 경우 Microsoft 365 business로 쉽게 업그레이드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1b5ab-104">If you have an [Office 365 for business subscription](https://products.office.com/compare-all-microsoft-office-products-4-column?activetab=tab:primaryr2), for example, Office 365 Business Premium, you can easily upgrade to Microsoft 365 Business.</span></span> <span data-ttu-id="1b5ab-105">다음을 추가 하려는 경우 Microsoft 365 Business로 업그레이드 합니다.</span><span class="sxs-lookup"><span data-stu-id="1b5ab-105">Upgrade to Microsoft 365 Business if you want to add:</span></span> 
- <span data-ttu-id="1b5ab-106">Windows 10 Pro (Windows 8 이상을 실행 하는 Pc에 대 한)</span><span class="sxs-lookup"><span data-stu-id="1b5ab-106">Windows 10 Pro (to PCs running Windows 8 or later)</span></span>
- <span data-ttu-id="1b5ab-107">장치에서 비즈니스 데이터를 관리 하는 간단한 컨트롤</span><span class="sxs-lookup"><span data-stu-id="1b5ab-107">Simple controls that manage business data on devices</span></span>
- <span data-ttu-id="1b5ab-108">고급 보안 기능</span><span class="sxs-lookup"><span data-stu-id="1b5ab-108">Advanced security capabilities.</span></span>
<span data-ttu-id="1b5ab-109">Microsoft 365 Business ( [Microsoft.com](https://www.microsoft.com/microsoft-365/business) )에 대 한 자세한 정보</span><span class="sxs-lookup"><span data-stu-id="1b5ab-109">Find out more about Microsoft 365 Business at [Microsoft.com](https://www.microsoft.com/microsoft-365/business)</span></span>

## <a name="whats-the-difference-between-office-365-business-premium-and-microsoft-365-business"></a><span data-ttu-id="1b5ab-110">Office 365 Business Premium과 Microsoft 365 Business의 차이점은 무엇 인가요?</span><span class="sxs-lookup"><span data-stu-id="1b5ab-110">What's the difference between Office 365 Business Premium and Microsoft 365 Business?</span></span>
<span data-ttu-id="1b5ab-111">[Microsoft 365 비즈니스 서비스 설명](https://docs.microsoft.com/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-business-service-description)에 이러한 두 요금제를 나란히 비교 하 여 추가 했습니다.</span><span class="sxs-lookup"><span data-stu-id="1b5ab-111">We've added a side-by-side comparison of these two plans to the [Microsoft 365 Business service description](https://docs.microsoft.com/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-business-service-description).</span></span> 

1. <span data-ttu-id="1b5ab-112">새 라이선스를 구매한 후이를 처음 시작 하면 Microsoft 365 Business 설치 배너가 관리 센터 위에 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1b5ab-112">Once you have purchased new licenses, and this is the first time you did, the setup banner for Microsoft 365 Business will display on top of the admin center.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="1b5ab-113">설치 배너는 새 사용자를 추가 하 고 새 도메인을 마이그레이션 하 고 새로운 사용자를 위해 전자 메일을 마이그레이션할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1b5ab-113">The setup banner is an opportunity to add new users, a new domain, and migrate email for new users.</span></span> <span data-ttu-id="1b5ab-114">이 작업을 수행 하지 않으려면 마법사를 계속 진행 하 여 관리 홈 페이지에서 사라지게 할 기본 옵션을 선택 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1b5ab-114">If you don't plan to do any, you should still go through the wizard and choose default options to make it disappear from the admin home page.</span></span> 
  
   ![Microsoft 365 Business에서 설정 시작을 선택 하 여 배너를 설정할 준비가 되었습니다.](media/8d3b0d97-7cca-497f-9364-4b00ad670209.png)
  
    <span data-ttu-id="1b5ab-116">**설정 시작**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="1b5ab-116">Choose **Start setup**.</span></span>
    
2. <span data-ttu-id="1b5ab-117">**로그인 및 전자 메일 개인 설정** 페이지에서이 기회를 사용 하 여 구독에 다른 도메인을 추가 하려는 경우 **이미 소유한 도메인 연결** 을 선택 하 여 도메인을 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1b5ab-117">On the **Personalize your sign-in and email** page, you can add a domain by choosing **Connect a domain you already own** if you want to use this opportunity to add another domain to your subscription.</span></span> 
    
    <span data-ttu-id="1b5ab-118">이미 도메인을 설정한 경우 두 번째 필드에는 **전자 메일 및 로그인에 대 한** _도메인 이름을_ \> **계속 사용** \<한다는 메시지가 표시 됩니다.  </span><span class="sxs-lookup"><span data-stu-id="1b5ab-118">If you have already set up a domain, the second field will indicate that and will say **Continue using** \<  _your domain name_\> **for email and signing in**.</span></span> <span data-ttu-id="1b5ab-119">구독을 사용 하 여 도메인을 설정 하지 않은 경우 **계속 해 서** \< **전자 메일 및 로그인에 대 한** _회사 name.onmicrosoft.com_ \> 사용 됩니다.  </span><span class="sxs-lookup"><span data-stu-id="1b5ab-119">If you haven't set up a domain with you subscription, it will say **Continue using** \<  _your company name.onmicrosoft.com_\> **for email and signing in**.</span></span>
    
    <span data-ttu-id="1b5ab-120">
            **다음**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="1b5ab-120">Choose **Next**.</span></span>
    
    ![로그인 및 전자 메일 개인 설정 페이지에서 도메인 추가를 선택 하거나 사용 중이 던 사용자를 사용 합니다.](media/c3f5cfb2-1189-4d2f-803b-c9feb008a7a3.png)
  
3. <span data-ttu-id="1b5ab-122">새 **사용자 추가** 페이지에서 Microsoft 365 비즈니스 라이선스를 할당 하려는 새 직원이 있는 경우 새 사용자를 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1b5ab-122">On the **Add new users** page, you can add new users, if you have new employees that you want to assign the Microsoft 365 Business licenses to.</span></span> 
    
    <span data-ttu-id="1b5ab-123">새 직원을 추가 하 여 기존 사용자에 게 라이선스를 할당 하지 않으려면 **다음**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="1b5ab-123">If you don't have new employees to add and want to assign licences to existing users, choose **Next**.</span></span>
    
4. <span data-ttu-id="1b5ab-124">**전자 메일 메시지 마이그레이션** 페이지에서 3 단계에서 추가한 새 사용자에 대 한 전자 메일을 마이그레이션하도록 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1b5ab-124">On the **Migrate email messages** page you can choose to migrate email for any of the new users you added in step 3.</span></span> <span data-ttu-id="1b5ab-125">또한이 단계를 건너뛸 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1b5ab-125">You can skip this step also.</span></span> <span data-ttu-id="1b5ab-126">
            **다음**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="1b5ab-126">Choose **Next**.</span></span>
    
5. <span data-ttu-id="1b5ab-127">마지막 페이지에서 **관리 센터로 이동을**선택 하 고 설치를 계속 합니다.</span><span class="sxs-lookup"><span data-stu-id="1b5ab-127">On the last page, choose **go to the admin center**, and continue setup there.</span></span>
    
6. <span data-ttu-id="1b5ab-128">관리 센터에서 **사용자** \> **활성 사용자**로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="1b5ab-128">In the admin center, go to **Users** \> **Active users**.</span></span>
    
7. <span data-ttu-id="1b5ab-129">**Microsoft 365 Business** license를 할당 하려는 사용자를 선택 하 고 **제품 라이선스**옆에 있는 **편집** 을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="1b5ab-129">Select the user to whom you want to assign the **Microsoft 365 Business** license to, and then choose **Edit** next to **Product Licenses**.</span></span>
    
    ![사용자 카드에서 제품 라이선스 옆에 있는 편집을 선택 합니다.](media/be0fe2d8-7ff8-447c-88f6-d212ed78451c.png)
  
## <a name="before-you-get-started"></a><span data-ttu-id="1b5ab-131">시작 하기 전에</span><span class="sxs-lookup"><span data-stu-id="1b5ab-131">Before you get started</span></span>

- <span data-ttu-id="1b5ab-132">**업그레이드를 선택 해야 하는 경우**</span><span class="sxs-lookup"><span data-stu-id="1b5ab-132">**When should I choose upgrade?**</span></span> <span data-ttu-id="1b5ab-133">단일 계획에 할당 된 **모든 사용자** 를 업그레이드 하려는 경우에는 업그레이드를 선택 하는 것이 적절 합니다.</span><span class="sxs-lookup"><span data-stu-id="1b5ab-133">Upgrade is the right choice when you want to upgrade **all users** assigned to a single plan.</span></span> <span data-ttu-id="1b5ab-134">업그레이드를 선택 하면 모든 요금제 사용자가 동시에 다른 요금제로 전환 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1b5ab-134">When you choose upgrade, all plan users get switched to another plan at the same time.</span></span> <span data-ttu-id="1b5ab-135">단일 계획에 할당 된 모든 사용자를 업그레이드 하지 않으려면 새 요금제 (이 경우 Microsoft 365 Business)에 대 한 라이선스를 구입 하 고 업그레이드할 각 사용자에 게 [개별적으로 라이선스를 할당](https://docs.microsoft.com/office365/admin/manage/assign-licenses-to-users) 합니다.</span><span class="sxs-lookup"><span data-stu-id="1b5ab-135">If you don't want to upgrade everyone assigned to a single plan, buy licenses for the new plan (in this case Microsoft 365 Business), and [assign those licenses individually](https://docs.microsoft.com/office365/admin/manage/assign-licenses-to-users) to each user that you want to upgrade.</span></span> 
- <span data-ttu-id="1b5ab-136">**일부 추가 기능은 업그레이드를 방해할 수 있음** 업그레이드를 시작 하려고 할 때 계속 진행할 수 없는 추가 기능을 사용 하는 경우에는 추가 기능을 먼저 제거한 다음 나중에 다시 추가 합니다 (필요한 경우).</span><span class="sxs-lookup"><span data-stu-id="1b5ab-136">**Some add-ons might prevent upgrade** If you try to start an upgrade and you have an add-on that prevents you from continuing, you can remove the add-on first, and then add it back later - if you still need it.</span></span> 
- <span data-ttu-id="1b5ab-137">**요금제를 선불 경우** 선불 계획에는 간단한 업그레이드 경로가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="1b5ab-137">**If you prepaid your plan** There isn't a straightforward upgrade path for prepaid plans.</span></span> <span data-ttu-id="1b5ab-138">상점에서 구매한 제품 ID를 사용 하 여 요금제를 설정 했기 때문에 선불 요금제가 있는지 여부를 알 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1b5ab-138">You'll know if you have a prepaid plan because you set up your plan using a product ID that you might have purchased in a store.</span></span> <span data-ttu-id="1b5ab-139">파트너에 게 문의 하 여 Microsoft store로 이동 하거나 선불 요금제가 만료 되어 새 요금제로 전환할 때까지 기다립니다.</span><span class="sxs-lookup"><span data-stu-id="1b5ab-139">Contact a partner, go to the Microsoft store, or wait until your prepaid plan expires to switch to a new plan.</span></span>

## <a name="upgrade-to-microsoft-365-business"></a><span data-ttu-id="1b5ab-140">Microsoft 365 Business로 업그레이드</span><span class="sxs-lookup"><span data-stu-id="1b5ab-140">Upgrade to Microsoft 365 Business</span></span>
<span data-ttu-id="1b5ab-141">[새 관리 센터](https://docs.microsoft.com/office365/admin/microsoft-365-admin-center-preview)에서 다음 단계를 수행 하 여 라이선스를 구입 합니다.</span><span class="sxs-lookup"><span data-stu-id="1b5ab-141">Buy your licenses by following these steps in the [new admin center](https://docs.microsoft.com/office365/admin/microsoft-365-admin-center-preview):</span></span>
1. <span data-ttu-id="1b5ab-142">에서 <a href="https://go.microsoft.com/fwlink/p/?linkid=837890" target="_blank">https://admin.microsoft.com</a>관리 센터에 로그인 합니다.</span><span class="sxs-lookup"><span data-stu-id="1b5ab-142">Sign into the admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=837890" target="_blank">https://admin.microsoft.com</a>.</span></span>
2. <span data-ttu-id="1b5ab-143">탐색 창으로 이동 하 여 **결제** \> **제품 & 서비스**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="1b5ab-143">Go to the navigation pane and select **Billing** \> **Products & Services**.</span></span> <span data-ttu-id="1b5ab-144">Office 365 구독을 찾아 선택 하 여 세부 정보를 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="1b5ab-144">Find your Office 365 subscription and select it to view the details.</span></span> 

    ![스크린샷에서는 관리 센터에서 구독을 찾아서 선택 하는 방법을 보여 줍니다.](media/FindYourSubscription.png)

3. <span data-ttu-id="1b5ab-146">다음 페이지에서 **업그레이드**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="1b5ab-146">On the next page, select **Upgrade**.</span></span> 

      ![스크린샷에는 관리 센터에서 업그레이드를 선택할 수 있는 위치가 표시 됩니다.](media/SelectUpgrade.png)

  > [!NOTE]
  > <span data-ttu-id="1b5ab-148">"Azure Active Directory의 그룹 기반 라이선싱으로 구독을 업그레이드 하는 것이 지원 되지 않습니다." 라는 메시지가 표시 되 면 대규모 조직이 없다면이를 무시 해도 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1b5ab-148">If you see a message that says "Upgrading your subscription is not supported with group-based licensing in Azure Active Directory", you can safely ignore this unless you have a very large organization.</span></span> <span data-ttu-id="1b5ab-149">이 옵션을 선택한 조직은 그룹 기반 라이선싱을 사용 하 고 있음을 알 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1b5ab-149">Organizations who have selected this option will be aware that they're using group-based licensing.</span></span>

4. <span data-ttu-id="1b5ab-150">다음으로 업그레이드할 수 있는 Office 요금제 목록을 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1b5ab-150">Next, you can view a list of Office plans that you can upgrade to.</span></span> <span data-ttu-id="1b5ab-151">이 경우 Microsoft 365 비즈니스 계획을 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="1b5ab-151">In this case, find the Microsoft 365 Business plan.</span></span> <span data-ttu-id="1b5ab-152">이 요금제에 포함 된 모든 Office 앱 및 서비스를 보려면 아래로 스크롤할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1b5ab-152">You can scroll down if you want to see all the Office apps and services that are included with this plan.</span></span> <span data-ttu-id="1b5ab-153">**Microsoft 365 business**에서 **업그레이드** 를 선택 하 여 microsoft 365 Business를 카트에 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="1b5ab-153">Under **Microsoft 365 Business**, select **Upgrade** to add Microsoft 365 Business to your cart.</span></span>
5. <span data-ttu-id="1b5ab-154">카트에:</span><span class="sxs-lookup"><span data-stu-id="1b5ab-154">In the cart:</span></span>
    1. <span data-ttu-id="1b5ab-155">현재 모든 사용자에 대 한 라이선스를 카트에 자동으로 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="1b5ab-155">We'll automatically include licenses for all your current users to the cart.</span></span> <span data-ttu-id="1b5ab-156">라이선스가 더 필요 하거나 덜 필요한 경우 [라이선스를 개별적으로 구입](https://docs.microsoft.com/office365/admin/manage/assign-licenses-to-users)하 여 할당 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1b5ab-156">If you need more, or less licenses, you'll need to [buy and assign those licenses individually](https://docs.microsoft.com/office365/admin/manage/assign-licenses-to-users).</span></span>  
    2. <span data-ttu-id="1b5ab-157">유료 또는 연별 비용을 조정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1b5ab-157">You can adjust how you'd like to pay - monthly or yearly.</span></span> <span data-ttu-id="1b5ab-158">드롭다운 메뉴를 선택 하 여 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="1b5ab-158">Select the drop-down menu to make your choice.</span></span>
6. <span data-ttu-id="1b5ab-159">이 계정에 대 한 결제 방법을 포함 하 여 구매 요약이 표시 되는 **체크아웃으로 이동을** 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="1b5ab-159">Select **Go to Checkout** where you'll see a summary of your purchase, including the payment method for this account.</span></span> <span data-ttu-id="1b5ab-160">프로 모션 코드 (있는 경우)를 추가할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1b5ab-160">You can also add a promo code here if you have one.</span></span>
7. <span data-ttu-id="1b5ab-161">구매를 완료 하려면 **주문을** 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="1b5ab-161">Select **Place order** to complete your purchase.</span></span>
<span data-ttu-id="1b5ab-162">새 서비스 계획을 설정 하는 데 몇 분 정도 걸립니다.</span><span class="sxs-lookup"><span data-stu-id="1b5ab-162">It takes Microsoft a few minutes to set up your new service plans.</span></span> <span data-ttu-id="1b5ab-163">진행 상황을 확인 하려면 **업그레이드 상태 확인**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="1b5ab-163">To check on progress, select **Check upgrade status**.</span></span> 
1. <span data-ttu-id="1b5ab-164">계획이 준비 되 면 관리 센터에서 몇 가지 추가 설치 단계를 완료 해야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1b5ab-164">Once your plan is ready, you might need to complete some additional setup steps in the admin center.</span></span> <span data-ttu-id="1b5ab-165">탐색 창에서 **Home** 을 선택 하 여 추가 설정 단계를 완료 합니다.</span><span class="sxs-lookup"><span data-stu-id="1b5ab-165">In the navigation pane, select **Home** to complete any additional setup steps.</span></span>

> [!NOTE]
> <span data-ttu-id="1b5ab-166">더 이상 필요 하지 않은 Ofifce 365 라이선스에 대 한 자세한 환불을 받게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1b5ab-166">You'll receive a prorated refund for the Ofifce 365 licenses that you no longer need.</span></span> <span data-ttu-id="1b5ab-167">새 요금제를 설정한 후 2 일 이내에 은행 계좌 또는 신용 카드 요금이 부과 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1b5ab-167">Your bank account or credit card will be charged about two days after you set up the new plan.</span></span>
  
## <a name="protect-user-devices-and-files"></a><span data-ttu-id="1b5ab-168">사용자 장치 및 파일 보호</span><span class="sxs-lookup"><span data-stu-id="1b5ab-168">Protect user devices and files</span></span>

<span data-ttu-id="1b5ab-169">Microsoft 365 비즈니스 라이선스가 할당 되었으므로 장치 및 파일 보호를 시작 하기 위한 단계를 완료 합니다.</span><span class="sxs-lookup"><span data-stu-id="1b5ab-169">Now that Microsoft 365 Business licenses have been assigned, complete steps to start protecting devices and files.</span></span> <span data-ttu-id="1b5ab-170">관리 센터 탐색 창에 포함 된 몇 가지 새 옵션을 사용 하 게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1b5ab-170">You'll be using some new options included in the admin center navigation pane.</span></span>
  
1. <span data-ttu-id="1b5ab-171">관리 센터의 탐색 창에서 **장치** \> **정책**으로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="1b5ab-171">In the admin center, in the navigation pane, go to **Devices** \> **Policies**.</span></span>
    
2. <span data-ttu-id="1b5ab-172">**장치 정책** 페이지에서 **추가**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="1b5ab-172">On the **Device policies** page, select **Add**.</span></span>
    
3. <span data-ttu-id="1b5ab-173">**정책 추가** 창에서 정책 이름 (예: 작업 파일 보호)을 지정 하 고 드롭다운에서 **정책 유형을** 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="1b5ab-173">In the **Add policy** pane give the policy a name (for example, Protect work files), and then choose a **Policy type** from the drop-down.</span></span> 
    
    <span data-ttu-id="1b5ab-174">Windows 10과 함께 Android 및 iPhone 장치에서 파일을 보호 하기 위한 응용 프로그램 정책을 설정 하 고 Windows 10 장치를 소유한 회사에 대 한 장치 구성 정책을 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1b5ab-174">You can set up application policies for protecting files on Android and iPhone devices, as well as Windows 10, and you can set up device configuration policies for company owned Windows 10 devices.</span></span> <span data-ttu-id="1b5ab-175">자세한 내용은 다음 링크를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="1b5ab-175">See the following links for details:</span></span>
    
  - [<span data-ttu-id="1b5ab-176">Android 또는 iOS 장치에서 앱 보호 설정 설정하기</span><span class="sxs-lookup"><span data-stu-id="1b5ab-176">Set app protection settings for Android or iOS devices</span></span>](app-protection-settings-for-android-and-ios.md)
    
  - [<span data-ttu-id="1b5ab-177">Windows 10 장치에서 응용 프로그램 보호 설정 설정하기</span><span class="sxs-lookup"><span data-stu-id="1b5ab-177">Set application protection settings for Windows 10 devices</span></span>](protection-settings-for-windows-10-devices.md)
    
  - [<span data-ttu-id="1b5ab-178">Windows 10 Pc에 대 한 장치 보호 설정 설정</span><span class="sxs-lookup"><span data-stu-id="1b5ab-178">Set device protection settings for Windows 10 PCs</span></span>](protection-settings-for-windows-10-pcs.md)
    
  
4. <span data-ttu-id="1b5ab-179">정책을 설정한 후에는 사용자와 직원이 장치를 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1b5ab-179">After you set up policies, you and your employees can set up devices:</span></span>
    
  - <span data-ttu-id="1b5ab-180">Windows 장치에서 Windows Pro Creator 업데이트를 아직 사용 하지 않는 경우 windows [Pro 크리에이터 업데이트로 업그레이드](upgrade-to-windows-pro-creators-update.md)해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1b5ab-180">If your Windows devices aren't already using the Windows Pro Creator update, you'll need to [upgrade them to Windows Pro Creators Update](upgrade-to-windows-pro-creators-update.md).</span></span>
    
  - <span data-ttu-id="1b5ab-181">Windows 장치에 대 한 단계는 [Microsoft 365 비즈니스 사용자를 위해 windows 장치 설정을](set-up-windows-devices.md) 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="1b5ab-181">See [Set up Windows devices for Microsoft 365 Business users](set-up-windows-devices.md) for steps for Windows devices.</span></span> 
    
  - <span data-ttu-id="1b5ab-182">Android 휴대폰 및 Iphone에 대 한 단계는 [Microsoft 365 비즈니스 사용자를 위한 모바일 장치 설정을](set-up-mobile-devices.md) 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="1b5ab-182">See [Set up mobile devices for Microsoft 365 Business users](set-up-mobile-devices.md) for steps for Android phones and iPhones.</span></span> 



