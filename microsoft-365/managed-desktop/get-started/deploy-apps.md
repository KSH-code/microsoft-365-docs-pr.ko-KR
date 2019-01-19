---
title: Microsoft 관리 되는 데스크톱 장치에 대 한 앱 배포
description: 추가 (영문) 및 Microsoft 관리 되는 데스크톱 장치에 앱을 배포에 대 한 정보를 제공 합니다.
keywords: Microsoft 관리 되는 데스크톱, Microsoft 365, 서비스, 설명서, 앱, 비즈니스 라인 앱, LOB 응용 프로그램
ms.service: m365-md
author: trudyha
ms.localizationpriority: normal
ms.date: 01/17/2019
ms.openlocfilehash: 65d45be5ddb21d8f2cac876a1c8f93b2bbddf7b8
ms.sourcegitcommit: 0fc00286d7dc8cafddf9d17a98a375503b9551e6
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/18/2019
ms.locfileid: "29341615"
---
# <a name="deploy-apps-to-microsoft-managed-desktop-devices"></a><span data-ttu-id="f7381-104">Microsoft 관리 되는 데스크톱 장치에 앱을 배포 합니다.</span><span class="sxs-lookup"><span data-stu-id="f7381-104">Deploy apps to Microsoft Managed Desktop devices</span></span>
<span data-ttu-id="f7381-p101">Microsoft 관리 되는 데스크톱에 온 보 딩 부분에서는 사용자의 장치에 앱을 배포 하 고 추가 (영문)를 포함 합니다. Microsoft 관리 되는 데스크톱 포털을 사용 하는 추가 하 고 앱을 배포할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f7381-p101">Part of onboarding to Microsoft Managed Desktop includes adding and deploying apps to your user’s devices. Once you're using the Microsoft Managed Desktop portal, you can add and deploy your apps.</span></span> 

<span data-ttu-id="f7381-107">전체 프로세스는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="f7381-107">The overall process looks like this:</span></span>
1. <span data-ttu-id="f7381-108">[Microsoft 관리 되는 데스크톱 포털에 추가 앱](#1) -비즈니스 라인 (lob 기간 업무) 응용 프로그램이 또는 Intune 사용한 동기화 했을 때 비즈니스를 위한 Microsoft 저장소에서 앱이 기존 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f7381-108">[Add apps to Microsoft Managed Desktop portal](#1) - This can be existing line-of-business (LOB) apps, or apps from Microsoft Store for Business that you've synced with Intune.</span></span> 
2. <span data-ttu-id="f7381-109">[응용 프로그램 할당에 대 한 만들기 Azure Active Directory (AD) 그룹](#2) -app 배정 관리 이러한 그룹을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="f7381-109">[Create Azure Active Directory (AD) groups for app assignment](#2) - You'll use these groups to manage app assignment.</span></span>
3. [<span data-ttu-id="f7381-110">앱 사용자에 게 할당</span><span class="sxs-lookup"><span data-stu-id="f7381-110">Assign apps to your users</span></span>](#3)

<span id="1" />

## <a name="step-1-add-apps-to-microsoft-managed-desktop-portal"></a><span data-ttu-id="f7381-111">1 단계: 관리 되는 데스크톱 Microsoft 포털에 앱 추가</span><span class="sxs-lookup"><span data-stu-id="f7381-111">Step 1: Add apps to Microsoft Managed Desktop portal</span></span>
<span data-ttu-id="f7381-112">Microsoft 관리 되는 데스크톱에 [Win32 또는 Windows MSI 기반 앱](#lob-apps), 또는 [비즈니스 응용 프로그램에 대 한 Microsoft 저장소](#msfb-apps) 를 추가할 수 있으며 Microsoft 관리 되는 데스크톱 장치에 배포 합니다.</span><span class="sxs-lookup"><span data-stu-id="f7381-112">You can add [Win32, or Windows MSI-based apps](#lob-apps), or [Microsoft Store for Business apps](#msfb-apps) to Microsoft Managed Desktop, and then deploy them to Microsoft Managed Desktop devices.</span></span>

<span id="lob-apps">

###  <a name="win32-or-windows-msi-based-apps-to-microsoft-managed-desktop"></a><span data-ttu-id="f7381-113">Win32 또는 Windows MSI 기반 앱을 Microsoft 데스크톱 관리</span><span class="sxs-lookup"><span data-stu-id="f7381-113">Win32 or Windows MSI-based apps to Microsoft Managed Desktop</span></span>

<span data-ttu-id="f7381-p102">Microsoft 관리 되는 데스크톱 포털에 비즈니스 라인 (lob 기간 업무) 응용 프로그램을 추가할 수 있습니다. Microsoft 관리 되는 데스크톱 장치에 설치 된 앱에 대 한 요구 사항에 대 한 정보를 [Microsoft 관리 되는 데스크톱 응용 프로그램 요구 사항](https://docs.microsoft.com/microsoft-365/managed-desktop/service-description/mmd-app-requirements)을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="f7381-p102">You can add your line-of-business (LOB) apps to Microsoft Managed Desktop portal. For information on requirements for apps installed on Microsoft Managed Desktop devices, see [Microsoft Managed Desktop app requirements](https://docs.microsoft.com/microsoft-365/managed-desktop/service-description/mmd-app-requirements).</span></span>

<span data-ttu-id="f7381-116">이 절차를 추가 하 고 다음 구성 및 응용 프로그램 소스를 업로드 하려는 응용 프로그램의 종류를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="f7381-116">In this procedure, you'll select which kind of app you want to add, and then configure and upload the app source.</span></span> 

<span data-ttu-id="f7381-117">**Microsoft 관리 되는 데스크톱 포털에 LOB 응용 프로그램 또는 Windows 응용 프로그램을 추가 하려면**</span><span class="sxs-lookup"><span data-stu-id="f7381-117">**To add your LOB app or Windows app to Microsoft Managed Desktop portal**</span></span>

<span data-ttu-id="f7381-p103">Microsoft 관리 되는 데스크톱 포털에 로그인 하 고 또는 Intune에 로그인 하 고, Microsoft 관리 되는 데스크톱에 대 한 다음 검색 수 있습니다. Microsoft 관리 되는 데스크톱 포털에 로그인 살펴보겠습니다.</span><span class="sxs-lookup"><span data-stu-id="f7381-p103">You can sign in to Microsoft Managed Desktop portal, or sign in to Intune and then search for Microsoft Managed Desktop. We'll show signing in to Microsoft Managed Desktop portal.</span></span> 

1.  <span data-ttu-id="f7381-120">[Microsoft 관리 되는 데스크톱 관리 포털](http://aka.ms/mmdportal)에 로그인 합니다.</span><span class="sxs-lookup"><span data-stu-id="f7381-120">Sign in to [Microsoft Managed Desktop Admin portal](http://aka.ms/mmdportal).</span></span> 
2.  <span data-ttu-id="f7381-121">**재고** **앱**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="f7381-121">Under **Inventory**, select **Apps**.</span></span>
3.  <span data-ttu-id="f7381-122">앱 작업에서 **추가**선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="f7381-122">In the Apps workload, select **Add**.</span></span>
4.  <span data-ttu-id="f7381-123">**추가 응용 프로그램** **비즈니스 라인 응용 프로그램** 또는 **Windows 응용 프로그램 (Win32)-미리 보기**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="f7381-123">In **Add app**, select **Line-of-business app** or **Windows app (Win32) - preview**.</span></span>
    - <span data-ttu-id="f7381-124">**비즈니스 라인 응용 프로그램**을 선택한 경우 추가 (영문) 및 비즈니스 라인 앱 구성에 대 한 지침은 [Microsoft Intune 하는 Windows 비즈니스 라인 앱 추가](https://docs.microsoft.com/intune/lob-apps-windows) 참조 합니다.</span><span class="sxs-lookup"><span data-stu-id="f7381-124">If you selected **Line-of-business app**, see [Add a Windows line-of-business app to Microsoft Intune](https://docs.microsoft.com/intune/lob-apps-windows) for instruction on adding and configuring line-of-business apps.</span></span>
    - <span data-ttu-id="f7381-125">**Windows 응용 프로그램 (Win32)-미리 보기**를 선택한 경우 추가 (영문) 및 Windows 앱 구성에 대 한 지침은 [Win32 응용 프로그램 관리](https://docs.microsoft.com/intune/apps-win32-app-management) 를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="f7381-125">If you selected **Windows app (Win32) - preview**, see [Win32 app management](https://docs.microsoft.com/intune/apps-win32-app-management) for instruction on adding and configuring Windows apps.</span></span>

<span id="msfb-apps">

### <a name="microsoft-store-for-business-apps"></a><span data-ttu-id="f7381-126">비즈니스 응용 프로그램에 대 한 Microsoft 저장소</span><span class="sxs-lookup"><span data-stu-id="f7381-126">Microsoft Store for Business apps</span></span>
<span data-ttu-id="f7381-p104">비즈니스를 위한 Microsoft 저장소와 가입 하지 않은 경우 앱에 대 한 쇼핑을 할 때 서명할 수 있습니다. 앱을 설치한 후 Microsoft 관리 데스크톱과 동기화 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f7381-p104">If you haven't signed up with Microsoft Store for Business, you can sign up when you shop for apps. After you have your apps, you can sync them with Microsoft Managed Desktop.</span></span> 

<span data-ttu-id="f7381-129">**비즈니스를 위한 Microsoft 스토어의 앱 구입**</span><span class="sxs-lookup"><span data-stu-id="f7381-129">**To buy apps from the Microsoft Store for Business**</span></span>

1. <span data-ttu-id="f7381-130">[비즈니스를 위한 Microsoft 저장소](https://businessstore.microsoft.com) 를 비즈니스 관리자 계정에 대 한 Microsoft 저장소와에 로그인 합니다.</span><span class="sxs-lookup"><span data-stu-id="f7381-130">Sign in to [Microsoft Store for Business](https://businessstore.microsoft.com) with your Microsoft Store for Business Admin account.</span></span>
2. <span data-ttu-id="f7381-131">**내 그룹에 대 한 상점**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="f7381-131">Select **Shop for my group**.</span></span>
3. <span data-ttu-id="f7381-132">검색을 사용 하 여 원하는 앱을 파악 하 고 응용 프로그램을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="f7381-132">Use Search to find that the app that you want, and select the app.</span></span>
4. <span data-ttu-id="f7381-p105">제품 세부 정보에서 **앱**을 선택 합니다. Microsoft 저장소를 사용 하면 **제품 & 서비스** 에 앱을 추가 하는 조직에 대 한입니다.</span><span class="sxs-lookup"><span data-stu-id="f7381-p105">On the product details, select **Get the App**. Microsoft Store adds the app to **Products & services** for your organization.</span></span>

<span data-ttu-id="f7381-135">**Intune 및 비즈니스를 위한 Microsoft 저장소 간의 동기화를 강제로 실행 하려면**</span><span class="sxs-lookup"><span data-stu-id="f7381-135">**To force a sync between Intune and Microsoft Store for Business**</span></span>
1. <span data-ttu-id="f7381-136">테 넌 트에 대 한 Intune 관리자 또는 전역 관리자도 [Azure 포털](https://portal.azure.com/) 로그인</span><span class="sxs-lookup"><span data-stu-id="f7381-136">Sign in to [Azure Portal](https://portal.azure.com/) as Intune Admin or Global Admin for your tenant</span></span>
2. <span data-ttu-id="f7381-p106">**모든 서비스 gt_ Intune를**선택 합니다. Intune 모니터링 + 관리에는 섹션입니다.</span><span class="sxs-lookup"><span data-stu-id="f7381-p106">Select **All services > Intune**. Intune is in the Monitoring + Management section.</span></span>
3. <span data-ttu-id="f7381-139">Intune 창에서 **클라이언트 응용 프로그램**선택 하 고 **비즈니스를 위한 Microsoft 저장소**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="f7381-139">In the Intune pane, select **Client Apps**, and then select **Microsoft Store for Business**.</span></span>
4. <span data-ttu-id="f7381-140">Intune 사용한 비즈니스 응용 프로그램에 대 한 사용자 Microsoft 저장소를 동기화 할 **사용** 을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="f7381-140">Select **Enable** to sync your Microsoft Store for Business apps with Intune.</span></span>
    - <span data-ttu-id="f7381-141">이미 하지 않은 경우 로그인 및 연결 Microsoft 저장 Intune 사용한 비즈니스 계정에 대 한</span><span class="sxs-lookup"><span data-stu-id="f7381-141">If you haven't already, sign up and associate your Microsoft Store for Business account with Intune</span></span>
    - <span data-ttu-id="f7381-142">Intune 콘솔에서 비즈니스를 위한 Microsoft 스토어 앱 표시 될 언어를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="f7381-142">Select the language in which apps from the Microsoft Store for Business will be displayed in your Intune console</span></span>
    - <span data-ttu-id="f7381-143">Intune 사용한 비즈니스 응용 프로그램에 대 한 사용자 Microsoft 저장소를 동기화 할 **동기화** 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="f7381-143">Select **Sync** to sync your Microsoft Store for Business apps with Intune.</span></span>
    - <span data-ttu-id="f7381-144">비즈니스를 위한 Microsoft 저장소와 Intune 간에 동기화 활성화 되었는지 확인 (다음 단계).</span><span class="sxs-lookup"><span data-stu-id="f7381-144">Verify that the sync between Microsoft Store for Business and Intune is active (next step).</span></span> 

<span data-ttu-id="f7381-145">**Intune 및 비즈니스를 위한 Microsoft 저장소 간의 동기화를 활성화 되었는지 확인 하려면**</span><span class="sxs-lookup"><span data-stu-id="f7381-145">**To verify that a sync between Intune and Microsoft Store for Business is active**</span></span>
1. <span data-ttu-id="f7381-146">[비즈니스를 위한 Microsoft 저장소](https://businessstore.microsoft.com) 를 비즈니스 관리자 계정에 대 한 Microsoft 저장소와에 로그인 합니다.</span><span class="sxs-lookup"><span data-stu-id="f7381-146">Sign in to [Microsoft Store for Business](https://businessstore.microsoft.com) with your Microsoft Store for Business Admin account.</span></span>
2. <span data-ttu-id="f7381-147">**관리**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="f7381-147">Select **Manage**.</span></span>
3. <span data-ttu-id="f7381-148">**설정** 을 선택 하 고 **배포**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="f7381-148">Select **Settings** and then select **Distribute**.</span></span>
4. <span data-ttu-id="f7381-149">**관리 도구**Intune 표시 되 고 **활성**상태 인지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="f7381-149">Under **Management tools**, verify that Intune is listed and that the status is **Active**.</span></span>  

<span id="2" />

## <a name="step-2-create-azure-ad-groups"></a><span data-ttu-id="f7381-150">2 단계: Azure AD 그룹 만들기</span><span class="sxs-lookup"><span data-stu-id="f7381-150">Step 2: Create Azure AD groups</span></span>

<span data-ttu-id="f7381-p107">각 응용 프로그램에 대 한 세 Azure AD 그룹을 만듭니다. 이 표에서 필요한 그룹을 대략적으로 보여줍니다 (대화 가능, 필요한 한 제거)를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="f7381-p107">Create three Azure AD groups for each app. This table outlines the groups you'll need (Available, Required, and Uninstall).</span></span> 

<span data-ttu-id="f7381-153">App 배정 종류</span><span class="sxs-lookup"><span data-stu-id="f7381-153">App assignment type</span></span> |   <span data-ttu-id="f7381-154">그룹 사용</span><span class="sxs-lookup"><span data-stu-id="f7381-154">Group use</span></span>   | <span data-ttu-id="f7381-155">예제 Azure AD 이름</span><span class="sxs-lookup"><span data-stu-id="f7381-155">Example Azure AD name</span></span>
--- | --- | ---
<span data-ttu-id="f7381-156">사용 가능</span><span class="sxs-lookup"><span data-stu-id="f7381-156">Available</span></span> |  <span data-ttu-id="f7381-157">응용 프로그램은 회사 포털 응용 프로그램 또는 웹 사이트에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f7381-157">The app will be available from Company Portal app or website.</span></span> | <span data-ttu-id="f7381-158">MMD- *응용 프로그램 이름* -가능</span><span class="sxs-lookup"><span data-stu-id="f7381-158">MMD – *app name* – Available</span></span>
<span data-ttu-id="f7381-159">필수</span><span class="sxs-lookup"><span data-stu-id="f7381-159">Required</span></span> |  <span data-ttu-id="f7381-160">앱이 선택된 된 그룹에 장치에 설치 합니다.</span><span class="sxs-lookup"><span data-stu-id="f7381-160">The app is installed on devices in the selected groups.</span></span> | <span data-ttu-id="f7381-161">MMD- *응용 프로그램 이름* -필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="f7381-161">MMD – *app name* – Required</span></span>
<span data-ttu-id="f7381-162">선택하여</span><span class="sxs-lookup"><span data-stu-id="f7381-162">Uninstall</span></span> |  <span data-ttu-id="f7381-163">삭제할 app은 선택한 그룹에 장치에서 제거 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f7381-163">TThe app is uninstalled from devices in the selected groups.</span></span> | <span data-ttu-id="f7381-164">MMD- *응용 프로그램 이름* -제거</span><span class="sxs-lookup"><span data-stu-id="f7381-164">MMD – *app name* – Uninstall</span></span>

<span data-ttu-id="f7381-165">App 사용할 수 있는 확인, 앱을 설치 하거나 자신의 데스크톱을 관리 하는 Microsoft 장치에서 응용 프로그램을 제거 하려면 이러한 그룹에 사용자를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="f7381-165">Add your users to these groups to either make the app availabe, install the app, or remove the app from their Microsoft Managed Desktop device.</span></span> 

<span id="3" />

## <a name="step-3-assign-apps-to-your-users"></a><span data-ttu-id="f7381-166">3 단계: 응용 프로그램을 사용자에 게 할당</span><span class="sxs-lookup"><span data-stu-id="f7381-166">Step 3: Assign apps to your users</span></span>

<span data-ttu-id="f7381-167">**응용 프로그램 사용자에 게 할당 하려면**</span><span class="sxs-lookup"><span data-stu-id="f7381-167">**To assign the app to your users**</span></span>

1. <span data-ttu-id="f7381-168">[Microsoft 관리 되는 데스크톱 관리 포털](http://aka.ms/mmdportal)에 로그인 합니다.</span><span class="sxs-lookup"><span data-stu-id="f7381-168">Sign in to [Microsoft Managed Desktop Admin portal](http://aka.ms/mmdportal).</span></span>
2. <span data-ttu-id="f7381-169">관리 되는 데스크톱 창에서 **앱**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="f7381-169">In Managed Desktop pane, select **Apps**.</span></span>
3. <span data-ttu-id="f7381-170">앱 작업에서 **사용자 그룹에 할당**을 선택 하 고 사용자에 게 할당 하려는 앱을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="f7381-170">In the Apps workload, select the app you want to assign users to and select **Assign users groups**.</span></span>
4. <span data-ttu-id="f7381-171">특정 응용 프로그램에 대 한 배정 종류 (대화 가능, 필요한 제거)를 선택 하 고 적절 한 그룹을 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="f7381-171">For the specific app, select an assignment type (Available, Required, Uninstall) and assign the appropriate group.</span></span>
5. <span data-ttu-id="f7381-172">앱 할당 창에서 **확인**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="f7381-172">In the Assign Apps pane, select **OK**.</span></span>

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