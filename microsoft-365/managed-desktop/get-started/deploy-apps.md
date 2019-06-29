---
title: Microsoft Managed Desktop devices 용 앱 배포
description: Microsoft Managed Desktop 장치에 앱을 추가 및 배포 하기 위한 정보
keywords: Microsoft Managed Desktop, Microsoft 365, 서비스, 설명서, 앱, LOB (기간 업무) 앱, 업무용 앱
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.openlocfilehash: 5eac2e8c3023015bd034c51ad7e16a669a484772
ms.sourcegitcommit: 427c6459614d58f6ef7c74354ae1816423e22323
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/28/2019
ms.locfileid: "35390425"
---
# <a name="deploy-apps-to-microsoft-managed-desktop-devices"></a><span data-ttu-id="324de-104">Microsoft Managed Desktop 장치에 앱 배포</span><span class="sxs-lookup"><span data-stu-id="324de-104">Deploy apps to Microsoft Managed Desktop devices</span></span>
<span data-ttu-id="324de-105">Microsoft Managed Desktop 온 보 딩에는 사용자의 장치에 앱을 추가 및 배포 하는 작업이 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="324de-105">Part of onboarding to Microsoft Managed Desktop includes adding and deploying apps to your user’s devices.</span></span> <span data-ttu-id="324de-106">Microsoft Managed Desktop portal을 사용 하 고 나면 앱을 추가 및 배포할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="324de-106">Once you're using the Microsoft Managed Desktop portal, you can add and deploy your apps.</span></span> 

<span data-ttu-id="324de-107">전체 프로세스는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="324de-107">The overall process looks like this:</span></span>
1. <span data-ttu-id="324de-108">[Microsoft Managed Desktop portal에 앱 추가](#1) -이는 기존 LOB (기간 업무) 앱 이거나 Intune을 사용 하 여 동기화 한 Microsoft Store 비즈니스용 앱이 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="324de-108">[Add apps to Microsoft Managed Desktop portal](#1) - This can be existing line-of-business (LOB) apps, or apps from Microsoft Store for Business that you've synced with Intune.</span></span> 
2. <span data-ttu-id="324de-109">[앱 할당에 대 한 AZURE AD (Active Directory) 그룹 만들기](#2) -이러한 그룹을 사용 하 여 앱 할당을 관리 합니다.</span><span class="sxs-lookup"><span data-stu-id="324de-109">[Create Azure Active Directory (AD) groups for app assignment](#2) - You'll use these groups to manage app assignment.</span></span>
3. [<span data-ttu-id="324de-110">사용자에 게 앱 할당</span><span class="sxs-lookup"><span data-stu-id="324de-110">Assign apps to your users</span></span>](#3)

<span id="1" />

## <a name="step-1-add-apps-to-microsoft-managed-desktop-portal"></a><span data-ttu-id="324de-111">1 단계: Microsoft Managed Desktop portal에 앱 추가</span><span class="sxs-lookup"><span data-stu-id="324de-111">Step 1: Add apps to Microsoft Managed Desktop portal</span></span>
<span data-ttu-id="324de-112">[Win32 또는 WINDOWS MSI 기반 앱](#lob-apps)또는 [비즈니스용 Microsoft Store for Business Apps](#msfb-apps) 를 microsoft managed desktop에 추가한 다음이를 microsoft managed desktop 장치에 배포할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="324de-112">You can add [Win32, or Windows MSI-based apps](#lob-apps), or [Microsoft Store for Business apps](#msfb-apps) to Microsoft Managed Desktop, and then deploy them to Microsoft Managed Desktop devices.</span></span>

<span id="lob-apps">

###  <a name="win32-or-windows-msi-based-apps-to-microsoft-managed-desktop"></a><span data-ttu-id="324de-113">Microsoft Managed Desktop에 대 한 Win32 또는 Windows MSI 기반 앱</span><span class="sxs-lookup"><span data-stu-id="324de-113">Win32 or Windows MSI-based apps to Microsoft Managed Desktop</span></span>

<span data-ttu-id="324de-114">기간 업무 (LOB) 앱을 Microsoft Managed Desktop portal에 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="324de-114">You can add your line-of-business (LOB) apps to Microsoft Managed Desktop portal.</span></span> <span data-ttu-id="324de-115">Microsoft Managed Desktop 장치에 설치 된 앱에 대 한 요구 사항에 대 한 자세한 내용은 [Microsoft Managed desktop app 요구 사항을](https://docs.microsoft.com/microsoft-365/managed-desktop/service-description/mmd-app-requirements)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="324de-115">For information on requirements for apps installed on Microsoft Managed Desktop devices, see [Microsoft Managed Desktop app requirements](https://docs.microsoft.com/microsoft-365/managed-desktop/service-description/mmd-app-requirements).</span></span>

<span data-ttu-id="324de-116">이 절차에서는 추가 하려는 앱의 종류를 선택한 다음 앱 원본을 구성 및 업로드 합니다.</span><span class="sxs-lookup"><span data-stu-id="324de-116">In this procedure, you'll select which kind of app you want to add, and then configure and upload the app source.</span></span> 

<span data-ttu-id="324de-117">**Microsoft Managed Desktop portal에 LOB 앱 또는 Windows 앱을 추가 하려면**</span><span class="sxs-lookup"><span data-stu-id="324de-117">**To add your LOB app or Windows app to Microsoft Managed Desktop portal**</span></span>

<span data-ttu-id="324de-118">Microsoft Managed Desktop portal에 로그인 하거나 Intune에 로그인 한 다음 Microsoft Managed Desktop을 검색할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="324de-118">You can sign in to Microsoft Managed Desktop portal, or sign in to Intune and then search for Microsoft Managed Desktop.</span></span> <span data-ttu-id="324de-119">Microsoft Managed Desktop portal에 로그인을 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="324de-119">We'll show signing in to Microsoft Managed Desktop portal.</span></span> 

1.  <span data-ttu-id="324de-120">[Microsoft Managed 데스크톱 관리 포털](http://aka.ms/mmdportal)에 로그인 합니다.</span><span class="sxs-lookup"><span data-stu-id="324de-120">Sign in to [Microsoft Managed Desktop Admin portal](http://aka.ms/mmdportal).</span></span> 
2.  <span data-ttu-id="324de-121">**인벤토리에서** **앱**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="324de-121">Under **Inventory**, select **Apps**.</span></span>
3.  <span data-ttu-id="324de-122">앱 작업에서 **추가**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="324de-122">In the Apps workload, select **Add**.</span></span>
4.  <span data-ttu-id="324de-123">**앱 추가**에서 lob ( **기간 업무) 앱** 또는 **Windows 앱 (Win32)-미리 보기**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="324de-123">In **Add app**, select **Line-of-business app** or **Windows app (Win32) - preview**.</span></span>
    - <span data-ttu-id="324de-124">**기간 업무**(lob) 앱을 선택한 경우 lob (기간 업무) 앱 추가 및 구성에 대 한 지침을 보려면 [Microsoft Intune에 Windows lob (기간 업무) 앱 추가](https://docs.microsoft.com/intune/lob-apps-windows) 를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="324de-124">If you selected **Line-of-business app**, see [Add a Windows line-of-business app to Microsoft Intune](https://docs.microsoft.com/intune/lob-apps-windows) for instruction on adding and configuring line-of-business apps.</span></span>
    - <span data-ttu-id="324de-125">**Windows 앱 (Win32)-미리 보기**를 선택한 경우 windows 앱 추가 및 구성에 대 한 지침은 [win32 앱 관리](https://docs.microsoft.com/intune/apps-win32-app-management) 를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="324de-125">If you selected **Windows app (Win32) - preview**, see [Win32 app management](https://docs.microsoft.com/intune/apps-win32-app-management) for instruction on adding and configuring Windows apps.</span></span>

<span id="msfb-apps">

### <a name="microsoft-store-for-business-apps"></a><span data-ttu-id="324de-126">Microsoft Store for Business 앱</span><span class="sxs-lookup"><span data-stu-id="324de-126">Microsoft Store for Business apps</span></span>
<span data-ttu-id="324de-127">Microsoft Store for Business에 등록 하지 않은 경우 앱을 쇼핑 하면 등록할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="324de-127">If you haven't signed up with Microsoft Store for Business, you can sign up when you shop for apps.</span></span> <span data-ttu-id="324de-128">앱을 설치한 후에는 Microsoft Managed Desktop과 동기화 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="324de-128">After you have your apps, you can sync them with Microsoft Managed Desktop.</span></span> 

<span data-ttu-id="324de-129">**Microsoft Store for Business에서 앱을 구입 하려면**</span><span class="sxs-lookup"><span data-stu-id="324de-129">**To buy apps from the Microsoft Store for Business**</span></span>

1. <span data-ttu-id="324de-130">비즈니스용 microsoft 스토어 관리자 계정을 사용 하 여 [비즈니스용 Microsoft 스토어](https://businessstore.microsoft.com) 에 로그인 합니다.</span><span class="sxs-lookup"><span data-stu-id="324de-130">Sign in to [Microsoft Store for Business](https://businessstore.microsoft.com) with your Microsoft Store for Business Admin account.</span></span>
2. <span data-ttu-id="324de-131">**내 그룹의 상점을**선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="324de-131">Select **Shop for my group**.</span></span>
3. <span data-ttu-id="324de-132">검색을 사용 하 여 원하는 앱을 찾은 다음 앱을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="324de-132">Use Search to find that the app that you want, and select the app.</span></span>
4. <span data-ttu-id="324de-133">제품 정보에서 **앱 가져오기를**선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="324de-133">On the product details, select **Get the App**.</span></span> <span data-ttu-id="324de-134">Microsoft Store에서는 조직의 **제품 & 서비스** 에 앱을 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="324de-134">Microsoft Store adds the app to **Products & services** for your organization.</span></span>

<span data-ttu-id="324de-135">**Intune과 비즈니스용 Microsoft Store를 강제 동기화 하려면**</span><span class="sxs-lookup"><span data-stu-id="324de-135">**To force a sync between Intune and Microsoft Store for Business**</span></span>
1. <span data-ttu-id="324de-136">테 넌 트에 대 한 Intune 관리자 또는 전역 관리자로 [Azure 포털](https://portal.azure.com/) 에 로그인 합니다.</span><span class="sxs-lookup"><span data-stu-id="324de-136">Sign in to [Azure Portal](https://portal.azure.com/) as Intune Admin or Global Admin for your tenant</span></span>
2. <span data-ttu-id="324de-137">**모든 서비스 > Intune**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="324de-137">Select **All services > Intune**.</span></span> <span data-ttu-id="324de-138">Intune은 모니터링 + 관리 섹션에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="324de-138">Intune is in the Monitoring + Management section.</span></span>
3. <span data-ttu-id="324de-139">Intune 창에서 **클라이언트 앱**을 선택 하 고 **Microsoft Store for Business**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="324de-139">In the Intune pane, select **Client Apps**, and then select **Microsoft Store for Business**.</span></span>
4. <span data-ttu-id="324de-140">Intune을 사용 하 여 비즈니스 앱 용 Microsoft Store를 동기화 하려면 **사용** 을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="324de-140">Select **Enable** to sync your Microsoft Store for Business apps with Intune.</span></span>
    - <span data-ttu-id="324de-141">아직 설치 하지 않은 경우 Intune을 사용 하 여 Microsoft Store for Business 계정을 등록 및 연결 합니다.</span><span class="sxs-lookup"><span data-stu-id="324de-141">If you haven't already, sign up and associate your Microsoft Store for Business account with Intune</span></span>
    - <span data-ttu-id="324de-142">Microsoft Store for Business 앱이 Intune 콘솔에 표시 되는 언어 선택</span><span class="sxs-lookup"><span data-stu-id="324de-142">Select the language in which apps from the Microsoft Store for Business will be displayed in your Intune console</span></span>
    - <span data-ttu-id="324de-143">**동기화** 를 선택 하 여 비즈니스용 Microsoft 스토어 앱 for Intune을 동기화 합니다.</span><span class="sxs-lookup"><span data-stu-id="324de-143">Select **Sync** to sync your Microsoft Store for Business apps with Intune.</span></span>
    - <span data-ttu-id="324de-144">Microsoft Store for Business 및 Intune 간의 동기화가 활성 상태 인지 확인 합니다 (다음 단계).</span><span class="sxs-lookup"><span data-stu-id="324de-144">Verify that the sync between Microsoft Store for Business and Intune is active (next step).</span></span> 

<span data-ttu-id="324de-145">**Intune과 비즈니스용 Microsoft Store 간의 동기화가 활성 상태 인지 확인 하려면**</span><span class="sxs-lookup"><span data-stu-id="324de-145">**To verify that a sync between Intune and Microsoft Store for Business is active**</span></span>
1. <span data-ttu-id="324de-146">비즈니스용 microsoft 스토어 관리자 계정을 사용 하 여 [비즈니스용 Microsoft 스토어](https://businessstore.microsoft.com) 에 로그인 합니다.</span><span class="sxs-lookup"><span data-stu-id="324de-146">Sign in to [Microsoft Store for Business](https://businessstore.microsoft.com) with your Microsoft Store for Business Admin account.</span></span>
2. <span data-ttu-id="324de-147">**관리**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="324de-147">Select **Manage**.</span></span>
3. <span data-ttu-id="324de-148">**설정을** 선택 하 고 **배포**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="324de-148">Select **Settings** and then select **Distribute**.</span></span>
4. <span data-ttu-id="324de-149">**관리 도구**에서 Intune이 나열 되는지와 상태가 **활성**상태 인지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="324de-149">Under **Management tools**, verify that Intune is listed and that the status is **Active**.</span></span>  

<span id="2" />

## <a name="step-2-create-azure-ad-groups"></a><span data-ttu-id="324de-150">2 단계: Azure AD 그룹 만들기</span><span class="sxs-lookup"><span data-stu-id="324de-150">Step 2: Create Azure AD groups</span></span>

<span data-ttu-id="324de-151">각 앱에 대해 세 개의 Azure AD 그룹을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="324de-151">Create three Azure AD groups for each app.</span></span> <span data-ttu-id="324de-152">이 표에는 필요한 그룹 (사용 가능, 필수 및 제거)이 정리 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="324de-152">This table outlines the groups you'll need (Available, Required, and Uninstall).</span></span> 

<span data-ttu-id="324de-153">앱 할당 유형</span><span class="sxs-lookup"><span data-stu-id="324de-153">App assignment type</span></span> |   <span data-ttu-id="324de-154">그룹 사용</span><span class="sxs-lookup"><span data-stu-id="324de-154">Group use</span></span>   | <span data-ttu-id="324de-155">예제 Azure AD 이름</span><span class="sxs-lookup"><span data-stu-id="324de-155">Example Azure AD name</span></span>
--- | --- | ---
<span data-ttu-id="324de-156">사용할 수 있음</span><span class="sxs-lookup"><span data-stu-id="324de-156">Available</span></span> |  <span data-ttu-id="324de-157">이 앱은 회사 포털 앱 또는 웹 사이트에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="324de-157">The app will be available from Company Portal app or website.</span></span> | <span data-ttu-id="324de-158">MMD- *응용 프로그램 이름* -사용 가능</span><span class="sxs-lookup"><span data-stu-id="324de-158">MMD – *app name* – Available</span></span>
<span data-ttu-id="324de-159">필수</span><span class="sxs-lookup"><span data-stu-id="324de-159">Required</span></span> |  <span data-ttu-id="324de-160">앱이 선택한 그룹의 장치에 설치 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="324de-160">The app is installed on devices in the selected groups.</span></span> | <span data-ttu-id="324de-161">MMD- *응용 프로그램 이름* -필수</span><span class="sxs-lookup"><span data-stu-id="324de-161">MMD – *app name* – Required</span></span>
<span data-ttu-id="324de-162">Uninstall</span><span class="sxs-lookup"><span data-stu-id="324de-162">Uninstall</span></span> |  <span data-ttu-id="324de-163">창의 앱이 선택한 그룹의 장치에서 제거 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="324de-163">TThe app is uninstalled from devices in the selected groups.</span></span> | <span data-ttu-id="324de-164">MMD- *응용 프로그램 이름* -제거</span><span class="sxs-lookup"><span data-stu-id="324de-164">MMD – *app name* – Uninstall</span></span>

<span data-ttu-id="324de-165">이러한 그룹에 사용자를 추가 하 여 앱을 availabe, 앱을 설치 하거나, Microsoft Managed Desktop 장치에서 앱을 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="324de-165">Add your users to these groups to either make the app availabe, install the app, or remove the app from their Microsoft Managed Desktop device.</span></span> 

<span id="3" />

## <a name="step-3-assign-apps-to-your-users"></a><span data-ttu-id="324de-166">3 단계: 사용자에 게 앱 할당</span><span class="sxs-lookup"><span data-stu-id="324de-166">Step 3: Assign apps to your users</span></span>

<span data-ttu-id="324de-167">**사용자에 게 앱을 할당 하려면**</span><span class="sxs-lookup"><span data-stu-id="324de-167">**To assign the app to your users**</span></span>

1. <span data-ttu-id="324de-168">[Microsoft Managed 데스크톱 관리 포털](http://aka.ms/mmdportal)에 로그인 합니다.</span><span class="sxs-lookup"><span data-stu-id="324de-168">Sign in to [Microsoft Managed Desktop Admin portal](http://aka.ms/mmdportal).</span></span>
2. <span data-ttu-id="324de-169">관리 되는 데스크톱 창에서 **앱**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="324de-169">In Managed Desktop pane, select **Apps**.</span></span>
3. <span data-ttu-id="324de-170">앱 작업에서 사용자를 할당 하려는 앱을 선택 하 고 **사용자 그룹 할당**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="324de-170">In the Apps workload, select the app you want to assign users to and select **Assign users groups**.</span></span>
4. <span data-ttu-id="324de-171">특정 앱에 대해 할당 유형 (사용 가능, 필수, 제거)을 선택 하 고 적절 한 그룹을 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="324de-171">For the specific app, select an assignment type (Available, Required, Uninstall) and assign the appropriate group.</span></span>
5. <span data-ttu-id="324de-172">앱 할당 창에서 **확인**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="324de-172">In the Assign Apps pane, select **OK**.</span></span>

<!--# Preparing apps for Microsoft Managed Desktop

This topic is the target for 2 "Learn more" links in the Admin Portal (aka.ms/app-overview;app-package); also target for link from Online resources (aka.ms/app-overviewmmd-app-prep) do not delete.

Applications: supported/onboard/deployment
 
Microsoft and Microsoft Managed Desktop customers have equally critical, yet different responsibilities around applications used with Microsoft Managed Desktop.

## Microsoft responsibilities
**Office 365 apps**
Microsoft will provide full service for the deployment, update, and support of specific Office 365 apps. All users will receive the base set of Office 365 click to run, 64 bit version of applications included in the device’s image so that a user can quickly become productive. The Project and Visio applications in of the Office 365 suite are licensed separately.  Microsoft Managed Desktop will provide deployment groups allowing the IT Administrator to manage licenses and deploy these applications appropriately for their organization. Microsoft will support end users of these applications through the Microsoft Managed Desktop Support channels.

**Line-of-business apps**
Microsoft provides tooling for IT Administrators to manage and deploy their line-of-business (LOB) applications to end users as a part of the Intune product. Microsoft will support application deployment issues as detailed in [Line-of-business applications](#line-of-business-applications) 

**Deploy with Intune**
Intune will be linked to the **Microsoft Store for Business** during Microsoft Managed Desktop onboarding allowing procured apps to be deployed through Intune. Microsoft will also deploy the web-based version of the Company Portal to end users so that IT Administrators can provide a self-service experience for end users.

**App management**
Microsoft may identify restricted applications which are not suitable for the modern workplace because of their system impact. When such an application is identified Microsoft will notify the customer and that application will need to be removed from the tenant. 

For more information on restricted app behaviors and app requirements, see [Microsoft Managed Desktop app requirements](../service-description/mmd-app-requirements.md)

## Customer responsibilities
The Office 365 Suite is core to Microsoft’s productivity offerings and is included in the Microsoft 365 License for all Microsoft Managed Desktop users. While Microsoft deploys, updates, and supports Office Applications to Microsoft Managed Desktop Devices there are still some areas for which the customer is responsible.
- **Assign licenses** - Customers are responsible for assigning the appropriate licenses to end users for Office 365. 
- **Add users to security groups** - For customers with users who need Project or Visio, the IT administrator must add those users to the appropriate deployment groups. IT administrators are also responsible for managing end of life for those users. 
- **Deploy Office 365 Add Ons** - Customers are responsible for deploying any plugins to the Office 365 suite which are deemed necessary. 

Since line-of-business (LOB) apps are unique for each customer, customers are responsible for managing all applications within their organization not deployed by Microsoft. This includes:
- Deciding which apps are needed and who needs them
- Assigning apps to those users
- Create and maintain Azure Active Directory (AD) groups for managing app assignments 

The customer must upload LOB apps to Intune. They are then responsible for deploying, updating, and decommissioning those applications over their respective lifecycles, as well as managing support for these apps for their users.

## Office applications
As part of the Microsoft 365 E5 license, Office 365 Standard Suite (64 Bit) is deployed by Microsoft. 

For details, see [Microsoft Managed Desktop technologies](../intro/technologies.md) <!--- and the other applications licensed under Office 365 E5 may be deployed by the customer using Intune’s deployment tools.

## Line-of-business applications
This table summarizes responsibilities across the different phases for line-of-business (LOB) applications. 

Application work items |    Customer    | Microsoft
--- | --- | ---
**Onboarding apps** |  |
Identify applications needed for targeted user groups   | ![yes](images/checkmark.png)  |
Create and manage Azure AD groups for app deployment | ![yes](images/checkmark.png) |   
**App Packaging** |  |
Package apps to meet Intune deployment standards |  ![yes](images/checkmark.png) |  
Upload apps to Intune | ![yes](images/checkmark.png)     |
Test apps in Microsoft Managed Desktop environment |    ![yes](images/checkmark.png) |  
Test apps with end users    | ![yes](images/checkmark.png) |    
**Deployment** | |
Manage and assign users to applications  | ![yes](images/checkmark.png)  |
Intune deployment tools delivers application to remote clients| |   ![yes](images/checkmark.png)
Identify and deploy application updates through Intune | ![yes](images/checkmark.png)    |
Unistall and remove applications when they have been retired    | ![yes](images/checkmark.png) |    
**Management** | |
Procure and assign licenses |   ![yes](images/checkmark.png)     |
Provide end-user support for line-of-business apps  | ![yes](images/checkmark.png) |
Manage app settings remotely    | ![yes](images/checkmark.png) |

For information on LOB application requirements, see [Microsoft Managed Desktop application requirements](../service-description/mmd-app-requirements.md)


## Intune application deployment
Application management can be handled through the Microsoft Managed Desktop Admin portal, or through the Intune portal. Intune’s app management portal shows applications deployed for Windows, Android, and iOS. Microsoft Managed Desktop Admin portal limits the view to Windows 10 applications. Both are available through the Azure Portal. 
* [Intune app management basics](https://docs.microsoft.com/intune/app-management)
* [Add apps to Intune](https://docs.microsoft.com/intune/app-management)
   * [Add a line-of-business App](https://docs.microsoft.com/intune/lob-apps-windows)
   * [Add Win32 apps to Intune](https://docs.microsoft.com/intune/apps-win32-app-management)
   * [Add web applications](https://docs.microsoft.com/intune/web-app)
* [Deploy apps](https://docs.microsoft.com/intune/apps-deploy)
   * [Deploy apps to Windows 10](https://docs.microsoft.com/intune/apps-windows-10-app-deploy)
* Company Portal
   * [Deploy the Company Portal](https://docs.microsoft.com/intune/store-apps-company-portal-app)
   * [Configure the Company Portal app](https://docs.microsoft.com/intune/company-portal-app)-->
