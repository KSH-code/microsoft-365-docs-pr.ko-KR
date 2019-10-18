---
title: Office 365 Business Premium에서 Microsoft 365 Business로 마이그레이션
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
description: Microsoft 365 Business로 비즈니스를 이동 하는 방법을 알아봅니다.
ms.openlocfilehash: ae9ca0fe97916fdae6104a6edbb04efba5d9299e
ms.sourcegitcommit: bd52f7b662887f552f90c46f69d6a2a42fb66914
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2019
ms.locfileid: "37575881"
---
# <a name="migrate-to-microsoft-365-business-from-office-365-business-premium"></a><span data-ttu-id="806e0-103">Office 365 Business Premium에서 Microsoft 365 Business로 마이그레이션</span><span class="sxs-lookup"><span data-stu-id="806e0-103">Migrate to Microsoft 365 Business from Office 365 Business Premium</span></span>

<span data-ttu-id="806e0-104">Office 365 Business Premium과 같은 비즈니스용 Office 365이 이미 있는 경우 Microsoft 365 Business에 라이선스를 쉽게 추가 하 고 일부 또는 모든 사용자에 게 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="806e0-104">If you already have an Office 365 for business subscription, for example, Office 365 Business Premium, you can easily add licenses to Microsoft 365 Business, and assign them to some, or all users.</span></span>
  
> [!NOTE]
> <span data-ttu-id="806e0-105">[요금제 전환](https://support.office.com/article/73318661-8f33-478b-bcc7-fb8d69dbb22a?.aspx#switchbutton) 단추를 사용 하 여 Microsoft 365 Business로 업그레이드할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="806e0-105">You can't use the [Switch plans](https://support.office.com/article/73318661-8f33-478b-bcc7-fb8d69dbb22a?.aspx#switchbutton) button to upgrade to Microsoft 365 Business yet.</span></span> 
  
## <a name="add-microsoft-365-business-licenses"></a><span data-ttu-id="806e0-106">Microsoft 365 Business 라이선스 추가</span><span class="sxs-lookup"><span data-stu-id="806e0-106">Add Microsoft 365 Business licenses</span></span>

<span data-ttu-id="806e0-107">두 가지 방법으로 Microsoft 365 비즈니스를 받을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="806e0-107">You have two ways to get Microsoft 365 Business.</span></span> <span data-ttu-id="806e0-108">파트너는 [microsoft의 파트너 센터](get-microsoft-365-business.md)에서 Microsoft 365 Business를 구매할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="806e0-108">A partner can purchase Microsoft 365 Business for you from [Microsoft Partner Center](get-microsoft-365-business.md).</span></span> <span data-ttu-id="806e0-109">또한 파트너는 Microsoft 365 Business로 전환 하는 데도 도움이 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="806e0-109">Your partner can also help you transition to Microsoft 365 Business.</span></span>
  
<span data-ttu-id="806e0-110">자체 구독을 관리 하는 경우 sales에 [연락](https://www.microsoft.com/microsoft-365/business) 하 여 Microsoft 365 비즈니스 라이선스를 구입할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="806e0-110">If you manage your own subscription, you can [contact sales](https://www.microsoft.com/microsoft-365/business) to purchase Microsoft 365 Business licenses.</span></span> 
  
<span data-ttu-id="806e0-111">파트너를 사용 하 여 작업을 시작 하는 방법은 [구독 관리자 파트너 추가, 변경 또는 삭제](https://support.office.com/article/f86e8177-936e-491e-9024-44dea2b296ff) 를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="806e0-111">See [Add, change, or delete a subscription advisor partner](https://support.office.com/article/f86e8177-936e-491e-9024-44dea2b296ff) to find out how you can start working with a partner.</span></span> 
  
<span data-ttu-id="806e0-112">라이선스을 구매 하기 위한 링크가 제공 되는 경우 아래와 같은 마법사를 진행 합니다.</span><span class="sxs-lookup"><span data-stu-id="806e0-112">If you are given a link to purchase your licences, you will walk through a wizard like the one below.</span></span> <span data-ttu-id="806e0-113">**예를 선택 하 고 내 계정에 추가**합니다.</span><span class="sxs-lookup"><span data-stu-id="806e0-113">Choose **Yes, add it to my account**.</span></span> <span data-ttu-id="806e0-114">라이선스 수 및 결제 방법도 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="806e0-114">You can also pick the number of licences and the method of payment.</span></span>
  
![Microsoft 365 Business direct 구매 링크에서 현재 계정에 추가를 선택 하거나 새 계정을 등록 합니다.](media/8bc54fd1-9cab-44d5-af91-c471e89aea46.png)
  
## <a name="assign-microsoft-365-licenses"></a><span data-ttu-id="806e0-116">Microsoft 365 라이선스 할당</span><span class="sxs-lookup"><span data-stu-id="806e0-116">Assign Microsoft 365 licenses</span></span>

1. <span data-ttu-id="806e0-117">새 라이선스를 구매한 후이를 처음 시작 하면 Microsoft 365 Business 설치 배너가 관리 센터 위에 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="806e0-117">Once you have purchased new licenses, and this is the first time you did, the setup banner for Microsoft 365 Business will display on top of the admin center.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="806e0-118">설치 배너는 새 사용자를 추가 하 고 새 도메인을 마이그레이션 하 고 새로운 사용자를 위해 전자 메일을 마이그레이션할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="806e0-118">The setup banner is an opportunity to add new users, a new domain, and migrate email for new users.</span></span> <span data-ttu-id="806e0-119">이 작업을 수행 하지 않으려면 마법사를 계속 진행 하 여 관리 홈 페이지에서 사라지게 할 기본 옵션을 선택 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="806e0-119">If you don't plan to do any, you should still go through the wizard and choose default options to make it disappear from the admin home page.</span></span> 
  
   ![Microsoft 365 Business에서 설정 시작을 선택 하 여 배너를 설정할 준비가 되었습니다.](media/8d3b0d97-7cca-497f-9364-4b00ad670209.png)
  
    <span data-ttu-id="806e0-121">**설정 시작**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="806e0-121">Choose **Start setup**.</span></span>
    
2. <span data-ttu-id="806e0-122">**로그인 및 전자 메일 개인 설정** 페이지에서이 기회를 사용 하 여 구독에 다른 도메인을 추가 하려는 경우 **이미 소유한 도메인 연결** 을 선택 하 여 도메인을 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="806e0-122">On the **Personalize your sign-in and email** page, you can add a domain by choosing **Connect a domain you already own** if you want to use this opportunity to add another domain to your subscription.</span></span> 
    
    <span data-ttu-id="806e0-123">이미 도메인을 설정한 경우 두 번째 필드에는 **전자 메일 및 로그인에 대 한** _도메인 이름을_ \> **계속 사용** \<한다는 메시지가 표시 됩니다.  </span><span class="sxs-lookup"><span data-stu-id="806e0-123">If you have already set up a domain, the second field will indicate that and will say **Continue using** \<  _your domain name_\> **for email and signing in**.</span></span> <span data-ttu-id="806e0-124">구독을 사용 하 여 도메인을 설정 하지 않은 경우 **계속 해 서** \< **전자 메일 및 로그인에 대 한** _회사 name.onmicrosoft.com_ \> 사용 됩니다.  </span><span class="sxs-lookup"><span data-stu-id="806e0-124">If you haven't set up a domain with you subscription, it will say **Continue using** \<  _your company name.onmicrosoft.com_\> **for email and signing in**.</span></span>
    
    <span data-ttu-id="806e0-125">
            **다음**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="806e0-125">Choose **Next**.</span></span>
    
    ![로그인 및 전자 메일 개인 설정 페이지에서 도메인 추가를 선택 하거나 사용 중이 던 사용자를 사용 합니다.](media/c3f5cfb2-1189-4d2f-803b-c9feb008a7a3.png)
  
3. <span data-ttu-id="806e0-127">새 **사용자 추가** 페이지에서 Microsoft 365 비즈니스 라이선스를 할당 하려는 새 직원이 있는 경우 새 사용자를 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="806e0-127">On the **Add new users** page, you can add new users, if you have new employees that you want to assign the Microsoft 365 Business licenses to.</span></span> 
    
    <span data-ttu-id="806e0-128">새 직원을 추가 하 여 기존 사용자에 게 라이선스를 할당 하지 않으려면 **다음**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="806e0-128">If you don't have new employees to add and want to assign licences to existing users, choose **Next**.</span></span>
    
4. <span data-ttu-id="806e0-129">\* \* 전자 메일 메시지 마이그레이션 \* \* 페이지에서 3 단계에서 추가한 새 사용자에 대 한 전자 메일을 마이그레이션하도록 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="806e0-129">On the \*\* Migrate email messages \*\* page you can choose to migrate email for any of the new users you added in step 3.</span></span> <span data-ttu-id="806e0-130">또한이 단계를 건너뛸 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="806e0-130">You can skip this step also.</span></span> <span data-ttu-id="806e0-131">
            **다음**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="806e0-131">Choose **Next**.</span></span>
    
5. <span data-ttu-id="806e0-132">마지막 페이지에서 **관리 센터로 이동을**선택 하 고 설치를 계속 합니다.</span><span class="sxs-lookup"><span data-stu-id="806e0-132">On the last page, choose **go to the admin center**, and continue setup there.</span></span>
    
6. <span data-ttu-id="806e0-133">관리 센터에서 **사용자** \> **활성 사용자**로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="806e0-133">In the admin center, go to **Users** \> **Active users**.</span></span>
    
7. <span data-ttu-id="806e0-134">**Microsoft 365 Business** license를 할당 하려는 사용자를 선택 하 고 **제품 라이선스**옆에 있는 **편집** 을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="806e0-134">Select the user to whom you want to assign the **Microsoft 365 Business** license to, and then choose **Edit** next to **Product Licenses**.</span></span>
    
    ![사용자 카드에서 제품 라이선스 옆에 있는 편집을 선택 합니다.](media/be0fe2d8-7ff8-447c-88f6-d212ed78451c.png)
  
8. <span data-ttu-id="806e0-136">**제품 라이선스** 의 **Microsoft 365 Business** for **Save** **to** \> a를 선택한 다음 **종료**합니다.</span><span class="sxs-lookup"><span data-stu-id="806e0-136">In **Product licenses** slide **Microsoft 365 Business** to **On** \> **Save**, and then **Close**.</span></span>
    
<span data-ttu-id="806e0-137">Microsoft 365 비즈니스에 대 한 초기 라이선스를 구매한 후에는 이제 **결제** \> **구매 서비스**에 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="806e0-137">Once you have purchased the initial license for Microsoft 365 Business, you can now also add more in **Billing** \> **Purchase services**.</span></span> <span data-ttu-id="806e0-138">**서비스 구매** 페이지에서 **Microsoft 365 Business** 카드의 줄임표를 클릭 한 다음 **라이선스 수량 변경을** 선택 하 여 더 구매할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="806e0-138">On the **Purchase services** page you can click on the ellipses on the **Microsoft 365 Business** card, and choose **Change license quantity** to purchase more.</span></span> 
  
## <a name="protect-user-devices-and-files"></a><span data-ttu-id="806e0-139">사용자 장치 및 파일 보호</span><span class="sxs-lookup"><span data-stu-id="806e0-139">Protect user devices and files</span></span>

<span data-ttu-id="806e0-140">Microsoft 365 Business에 대 한 라이선스를 할당 한 후에는 사용자의 장치 및 파일을 보호 하기 시작할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="806e0-140">After you have assigned licenses to Microsoft 365 Business, you can start protecting the users' devices and files.</span></span>
  
1. <span data-ttu-id="806e0-141">관리 센터의 왼쪽 탐색 창에서 **장치** \> **정책**으로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="806e0-141">In the admin center, in the left nav, go to **Devices** \> **Policies**.</span></span>
    
2. <span data-ttu-id="806e0-142">**장치 정책** 페이지에서 **추가**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="806e0-142">On the **Device policies** page, choose **Add**.</span></span>
    
3. <span data-ttu-id="806e0-143">정책 **추가** 창에서 정책에 이름을 지정 하 고 드롭다운에서 **정책 유형을** 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="806e0-143">In the **Add policy** pane give the policy a name, and then choose a **Policy type** from the drop-down.</span></span> 
    
    <span data-ttu-id="806e0-144">Windows 10과 함께 Android 및 iPhone 장치에서 파일을 보호 하기 위한 응용 프로그램 정책을 설정 하 고 Windows 10 장치를 소유한 회사에 대 한 장치 구성 정책을 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="806e0-144">You can set up application policies for protecting files on Android and iPhone devices, as well as Windows 10, and you can set up device configuration policies for company owned Windows 10 devices.</span></span> <span data-ttu-id="806e0-145">자세한 내용은 다음 링크를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="806e0-145">See the following links for details:</span></span>
    
  - [<span data-ttu-id="806e0-146">Android 또는 iOS 장치에서 앱 보호 설정 설정하기</span><span class="sxs-lookup"><span data-stu-id="806e0-146">Set app protection settings for Android or iOS devices</span></span>](app-protection-settings-for-android-and-ios.md)
    
  - [<span data-ttu-id="806e0-147">Windows 10 장치에서 응용 프로그램 보호 설정 설정하기</span><span class="sxs-lookup"><span data-stu-id="806e0-147">Set application protection settings for Windows 10 devices</span></span>](protection-settings-for-windows-10-devices.md)
    
  - [<span data-ttu-id="806e0-148">Windows 10 Pc에 대 한 장치 보호 설정 설정</span><span class="sxs-lookup"><span data-stu-id="806e0-148">Set device protection settings for Windows 10 PCs</span></span>](protection-settings-for-windows-10-pcs.md)
    
   ![정책 추가 창에 이름을 입력 하 고 드롭다운 메뉴에서 정책 유형을 선택 합니다.](media/76ef37e4-1d18-4f34-8a0f-391ab1d0ae2b.png)
  
4. <span data-ttu-id="806e0-150">정책을 설정 하면 사용자와 직원이 장치를 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="806e0-150">Once you set up policies, you and your employees can set up devices:</span></span>
    
  - <span data-ttu-id="806e0-151">Windows Pro Creator update가 아직 없는 경우에는 windows [Pro 크리에이터 업데이트로 업그레이드](upgrade-to-windows-pro-creators-update.md)해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="806e0-151">If your Windows aren't already on Windows Pro Creator update, you will need to [upgrade them to Windows Pro Creators Update](upgrade-to-windows-pro-creators-update.md).</span></span>
    
  - <span data-ttu-id="806e0-152">Windows 장치에 대 한 단계는 [Microsoft 365 비즈니스 사용자를 위해 windows 장치 설정을](set-up-windows-devices.md) 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="806e0-152">See [Set up Windows devices for Microsoft 365 Business users](set-up-windows-devices.md) for steps for Windows devices.</span></span> 
    
  - <span data-ttu-id="806e0-153">Android 휴대폰 및 Iphone에 대 한 단계는 [Microsoft 365 비즈니스 사용자를 위한 모바일 장치 설정을](set-up-mobile-devices.md) 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="806e0-153">See [Set up mobile devices for Microsoft 365 Business users](set-up-mobile-devices.md) for steps for Android phones and iPhones.</span></span> 
    
5. <span data-ttu-id="806e0-154">Office 클라이언트 앱을 자동으로 설치 하려면 office [클라이언트 배포 준비 Microsoft 365 Business](prepare-for-office-client-deployment.md) 및 [Windows 10 장치에서 Office를 자동으로 설치 또는 제거](auto-install-or-uninstall-office.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="806e0-154">To automatically install Office client apps, see [Prepare for Office client deployment by Microsoft 365 Business](prepare-for-office-client-deployment.md) and [Automatically install or uninstall Office on Windows 10 devices](auto-install-or-uninstall-office.md).</span></span>
    


