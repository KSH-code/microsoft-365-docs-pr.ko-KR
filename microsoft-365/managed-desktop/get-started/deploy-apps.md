---
title: 장치에 앱 배포
description: Microsoft Managed Desktop 장치에 앱을 추가 및 배포 하기 위한 정보
keywords: Microsoft Managed Desktop, Microsoft 365, 서비스, 설명서, 앱, LOB (기간 업무) 앱, 업무용 앱
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.openlocfilehash: 5f1e2bd2440b5c38c958d3182684e87643f2e853
ms.sourcegitcommit: 3d37043c0447359c952dc99026c219dd69f6fb8d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/06/2019
ms.locfileid: "38012029"
---
# <a name="deploy-apps-to-devices"></a><span data-ttu-id="30969-104">장치에 앱 배포</span><span class="sxs-lookup"><span data-stu-id="30969-104">Deploy apps to devices</span></span>
<span data-ttu-id="30969-105">Microsoft Managed Desktop 온 보 딩에는 사용자의 장치에 앱을 추가 및 배포 하는 작업이 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="30969-105">Part of onboarding to Microsoft Managed Desktop includes adding and deploying apps to your user’s devices.</span></span> <span data-ttu-id="30969-106">Microsoft Managed Desktop portal을 사용 하 고 나면 앱을 추가 및 배포할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="30969-106">Once you're using the Microsoft Managed Desktop portal, you can add and deploy your apps.</span></span> 

<span data-ttu-id="30969-107">전체 프로세스는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="30969-107">The overall process looks like this:</span></span>
1. <span data-ttu-id="30969-108">[Microsoft Managed Desktop portal에 앱 추가](#1) -이는 기존 LOB (기간 업무) 앱 이거나 Intune을 사용 하 여 동기화 한 Microsoft Store 비즈니스용 앱이 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="30969-108">[Add apps to Microsoft Managed Desktop portal](#1) - This can be existing line-of-business (LOB) apps, or apps from Microsoft Store for Business that you've synced with Intune.</span></span> 
2. <span data-ttu-id="30969-109">[앱 할당에 대 한 AZURE AD (Active Directory) 그룹 만들기](#2) -이러한 그룹을 사용 하 여 앱 할당을 관리 합니다.</span><span class="sxs-lookup"><span data-stu-id="30969-109">[Create Azure Active Directory (AD) groups for app assignment](#2) - You'll use these groups to manage app assignment.</span></span>
3. [<span data-ttu-id="30969-110">사용자에 게 앱 할당</span><span class="sxs-lookup"><span data-stu-id="30969-110">Assign apps to your users</span></span>](#3)

<span id="1" />

## <a name="step-1-add-apps-to-microsoft-managed-desktop-portal"></a><span data-ttu-id="30969-111">1 단계: Microsoft Managed Desktop portal에 앱 추가</span><span class="sxs-lookup"><span data-stu-id="30969-111">Step 1: Add apps to Microsoft Managed Desktop portal</span></span>
<span data-ttu-id="30969-112">[Win32 또는 WINDOWS MSI 기반 앱](#lob-apps)또는 [비즈니스용 Microsoft Store for Business Apps](#msfb-apps) 를 microsoft managed desktop에 추가한 다음이를 microsoft managed desktop 장치에 배포할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="30969-112">You can add [Win32, or Windows MSI-based apps](#lob-apps), or [Microsoft Store for Business apps](#msfb-apps) to Microsoft Managed Desktop, and then deploy them to Microsoft Managed Desktop devices.</span></span>

<span id="lob-apps">

###  <a name="win32-or-windows-msi-based-apps-to-microsoft-managed-desktop"></a><span data-ttu-id="30969-113">Microsoft Managed Desktop에 대 한 Win32 또는 Windows MSI 기반 앱</span><span class="sxs-lookup"><span data-stu-id="30969-113">Win32 or Windows MSI-based apps to Microsoft Managed Desktop</span></span>

<span data-ttu-id="30969-114">기간 업무 (LOB) 앱을 Microsoft Managed Desktop portal에 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="30969-114">You can add your line-of-business (LOB) apps to Microsoft Managed Desktop portal.</span></span> <span data-ttu-id="30969-115">Microsoft Managed Desktop 장치에 설치 된 앱에 대 한 요구 사항에 대 한 자세한 내용은 [Microsoft Managed desktop app 요구 사항을](https://docs.microsoft.com/microsoft-365/managed-desktop/service-description/mmd-app-requirements)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="30969-115">For information on requirements for apps installed on Microsoft Managed Desktop devices, see [Microsoft Managed Desktop app requirements](https://docs.microsoft.com/microsoft-365/managed-desktop/service-description/mmd-app-requirements).</span></span>

<span data-ttu-id="30969-116">이 절차에서는 추가 하려는 앱의 종류를 선택한 다음 앱 원본을 구성 및 업로드 합니다.</span><span class="sxs-lookup"><span data-stu-id="30969-116">In this procedure, you'll select which kind of app you want to add, and then configure and upload the app source.</span></span> 

<span data-ttu-id="30969-117">**Microsoft Managed Desktop portal에 LOB 앱 또는 Windows 앱을 추가 하려면**</span><span class="sxs-lookup"><span data-stu-id="30969-117">**To add your LOB app or Windows app to Microsoft Managed Desktop portal**</span></span>

<span data-ttu-id="30969-118">Microsoft Managed Desktop portal에 로그인 하거나 Intune에 로그인 한 다음 Microsoft Managed Desktop을 검색할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="30969-118">You can sign in to Microsoft Managed Desktop portal, or sign in to Intune and then search for Microsoft Managed Desktop.</span></span> <span data-ttu-id="30969-119">Microsoft Managed Desktop portal에 로그인을 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="30969-119">We'll show signing in to Microsoft Managed Desktop portal.</span></span> 

1.  <span data-ttu-id="30969-120">[Microsoft Managed 데스크톱 관리 포털](https://aka.ms/mmdportal)에 로그인 합니다.</span><span class="sxs-lookup"><span data-stu-id="30969-120">Sign in to [Microsoft Managed Desktop Admin portal](https://aka.ms/mmdportal).</span></span> 
2.  <span data-ttu-id="30969-121">**인벤토리에서** **앱**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="30969-121">Under **Inventory**, select **Apps**.</span></span>
3.  <span data-ttu-id="30969-122">앱 작업에서 **추가**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="30969-122">In the Apps workload, select **Add**.</span></span>
4.  <span data-ttu-id="30969-123">**앱 추가**에서 lob ( **기간 업무) 앱** 또는 **Windows 앱 (Win32)** 을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="30969-123">In **Add app**, select **Line-of-business app** or **Windows app (Win32)**.</span></span>
    - <span data-ttu-id="30969-124">**기간 업무**(lob) 앱을 선택한 경우 lob (기간 업무) 앱 추가 및 구성에 대 한 지침을 보려면 [Microsoft Intune에 Windows lob (기간 업무) 앱 추가](https://docs.microsoft.com/intune/lob-apps-windows) 를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="30969-124">If you selected **Line-of-business app**, see [Add a Windows line-of-business app to Microsoft Intune](https://docs.microsoft.com/intune/lob-apps-windows) for instruction on adding and configuring line-of-business apps.</span></span>
    - <span data-ttu-id="30969-125">**Windows 앱 (win32)** 을 선택한 경우 windows 앱 추가 및 구성에 대 한 지침은 [win32 앱 관리](https://docs.microsoft.com/intune/apps-win32-app-management) 를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="30969-125">If you selected **Windows app (Win32)**, see [Win32 app management](https://docs.microsoft.com/intune/apps-win32-app-management) for instruction on adding and configuring Windows apps.</span></span>

<span id="msfb-apps">

### <a name="microsoft-store-for-business-apps"></a><span data-ttu-id="30969-126">Microsoft Store for Business 앱</span><span class="sxs-lookup"><span data-stu-id="30969-126">Microsoft Store for Business apps</span></span>
<span data-ttu-id="30969-127">Microsoft Store for Business에 등록 하지 않은 경우 앱을 쇼핑 하면 등록할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="30969-127">If you haven't signed up with Microsoft Store for Business, you can sign up when you shop for apps.</span></span> <span data-ttu-id="30969-128">앱을 설치한 후에는 Microsoft Managed Desktop과 동기화 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="30969-128">After you have your apps, you can sync them with Microsoft Managed Desktop.</span></span> 

<span data-ttu-id="30969-129">**Microsoft Store for Business에서 앱을 구입 하려면**</span><span class="sxs-lookup"><span data-stu-id="30969-129">**To buy apps from the Microsoft Store for Business**</span></span>

1. <span data-ttu-id="30969-130">비즈니스용 microsoft 스토어 관리자 계정을 사용 하 여 [비즈니스용 Microsoft 스토어](https://businessstore.microsoft.com) 에 로그인 합니다.</span><span class="sxs-lookup"><span data-stu-id="30969-130">Sign in to [Microsoft Store for Business](https://businessstore.microsoft.com) with your Microsoft Store for Business Admin account.</span></span>
2. <span data-ttu-id="30969-131">**내 그룹의 상점을**선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="30969-131">Select **Shop for my group**.</span></span>
3. <span data-ttu-id="30969-132">검색을 사용 하 여 원하는 앱을 찾은 다음 앱을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="30969-132">Use Search to find that the app that you want, and select the app.</span></span>
4. <span data-ttu-id="30969-133">제품 정보에서 **앱 가져오기를**선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="30969-133">On the product details, select **Get the App**.</span></span> <span data-ttu-id="30969-134">Microsoft Store에서는 조직의 **제품 & 서비스** 에 앱을 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="30969-134">Microsoft Store adds the app to **Products & services** for your organization.</span></span>

<span data-ttu-id="30969-135">**Intune과 비즈니스용 Microsoft Store를 강제 동기화 하려면**</span><span class="sxs-lookup"><span data-stu-id="30969-135">**To force a sync between Intune and Microsoft Store for Business**</span></span>
1. <span data-ttu-id="30969-136">테 넌 트에 대 한 Intune 관리자 또는 전역 관리자로 [Azure 포털](https://portal.azure.com/) 에 로그인 합니다.</span><span class="sxs-lookup"><span data-stu-id="30969-136">Sign in to [Azure Portal](https://portal.azure.com/) as Intune Admin or Global Admin for your tenant</span></span>
2. <span data-ttu-id="30969-137">**모든 서비스 > Intune**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="30969-137">Select **All services > Intune**.</span></span> <span data-ttu-id="30969-138">Intune은 모니터링 + 관리 섹션에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="30969-138">Intune is in the Monitoring + Management section.</span></span>
3. <span data-ttu-id="30969-139">Intune 창에서 **클라이언트 앱**을 선택 하 고 **Microsoft Store for Business**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="30969-139">In the Intune pane, select **Client Apps**, and then select **Microsoft Store for Business**.</span></span>
4. <span data-ttu-id="30969-140">Intune을 사용 하 여 비즈니스 앱 용 Microsoft Store를 동기화 하려면 **사용** 을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="30969-140">Select **Enable** to sync your Microsoft Store for Business apps with Intune.</span></span>
    - <span data-ttu-id="30969-141">아직 설치 하지 않은 경우 Intune을 사용 하 여 Microsoft Store for Business 계정을 등록 및 연결 합니다.</span><span class="sxs-lookup"><span data-stu-id="30969-141">If you haven't already, sign up and associate your Microsoft Store for Business account with Intune</span></span>
    - <span data-ttu-id="30969-142">Microsoft Store for Business 앱이 Intune 콘솔에 표시 되는 언어 선택</span><span class="sxs-lookup"><span data-stu-id="30969-142">Select the language in which apps from the Microsoft Store for Business will be displayed in your Intune console</span></span>
    - <span data-ttu-id="30969-143">**동기화** 를 선택 하 여 비즈니스용 Microsoft 스토어 앱 for Intune을 동기화 합니다.</span><span class="sxs-lookup"><span data-stu-id="30969-143">Select **Sync** to sync your Microsoft Store for Business apps with Intune.</span></span>
    - <span data-ttu-id="30969-144">Microsoft Store for Business 및 Intune 간의 동기화가 활성 상태 인지 확인 합니다 (다음 단계).</span><span class="sxs-lookup"><span data-stu-id="30969-144">Verify that the sync between Microsoft Store for Business and Intune is active (next step).</span></span> 

<span data-ttu-id="30969-145">**Intune과 비즈니스용 Microsoft Store 간의 동기화가 활성 상태 인지 확인 하려면**</span><span class="sxs-lookup"><span data-stu-id="30969-145">**To verify that a sync between Intune and Microsoft Store for Business is active**</span></span>
1. <span data-ttu-id="30969-146">비즈니스용 microsoft 스토어 관리자 계정을 사용 하 여 [비즈니스용 Microsoft 스토어](https://businessstore.microsoft.com) 에 로그인 합니다.</span><span class="sxs-lookup"><span data-stu-id="30969-146">Sign in to [Microsoft Store for Business](https://businessstore.microsoft.com) with your Microsoft Store for Business Admin account.</span></span>
2. <span data-ttu-id="30969-147">**관리**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="30969-147">Select **Manage**.</span></span>
3. <span data-ttu-id="30969-148">**설정을** 선택 하 고 **배포**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="30969-148">Select **Settings** and then select **Distribute**.</span></span>
4. <span data-ttu-id="30969-149">**관리 도구**에서 Intune이 나열 되는지와 상태가 **활성**상태 인지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="30969-149">Under **Management tools**, verify that Intune is listed and that the status is **Active**.</span></span>  

<span id="2" />

## <a name="step-2-create-azure-ad-groups"></a><span data-ttu-id="30969-150">2 단계: Azure AD 그룹 만들기</span><span class="sxs-lookup"><span data-stu-id="30969-150">Step 2: Create Azure AD groups</span></span>

<span data-ttu-id="30969-151">각 앱에 대해 세 개의 Azure AD 그룹을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="30969-151">Create three Azure AD groups for each app.</span></span> <span data-ttu-id="30969-152">이 표에는 필요한 그룹 (사용 가능, 필수 및 제거)이 정리 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="30969-152">This table outlines the groups you'll need (Available, Required, and Uninstall).</span></span> 

<span data-ttu-id="30969-153">앱 할당 유형</span><span class="sxs-lookup"><span data-stu-id="30969-153">App assignment type</span></span> |   <span data-ttu-id="30969-154">그룹 사용</span><span class="sxs-lookup"><span data-stu-id="30969-154">Group use</span></span>   | <span data-ttu-id="30969-155">예제 Azure AD 이름</span><span class="sxs-lookup"><span data-stu-id="30969-155">Example Azure AD name</span></span>
--- | --- | ---
<span data-ttu-id="30969-156">사용할 수 있음</span><span class="sxs-lookup"><span data-stu-id="30969-156">Available</span></span> |  <span data-ttu-id="30969-157">이 앱은 회사 포털 앱 또는 웹 사이트에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="30969-157">The app will be available from Company Portal app or website.</span></span> | <span data-ttu-id="30969-158">MMD- *응용 프로그램 이름* -사용 가능</span><span class="sxs-lookup"><span data-stu-id="30969-158">MMD – *app name* – Available</span></span>
<span data-ttu-id="30969-159">필수</span><span class="sxs-lookup"><span data-stu-id="30969-159">Required</span></span> |  <span data-ttu-id="30969-160">앱이 선택한 그룹의 장치에 설치 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="30969-160">The app is installed on devices in the selected groups.</span></span> | <span data-ttu-id="30969-161">MMD- *응용 프로그램 이름* -필수</span><span class="sxs-lookup"><span data-stu-id="30969-161">MMD – *app name* – Required</span></span>
<span data-ttu-id="30969-162">Uninstall</span><span class="sxs-lookup"><span data-stu-id="30969-162">Uninstall</span></span> |  <span data-ttu-id="30969-163">창의 앱이 선택한 그룹의 장치에서 제거 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="30969-163">TThe app is uninstalled from devices in the selected groups.</span></span> | <span data-ttu-id="30969-164">MMD- *응용 프로그램 이름* -제거</span><span class="sxs-lookup"><span data-stu-id="30969-164">MMD – *app name* – Uninstall</span></span>

<span data-ttu-id="30969-165">이러한 그룹에 사용자를 추가 하 여 앱을 availabe, 앱을 설치 하거나, Microsoft Managed Desktop 장치에서 앱을 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="30969-165">Add your users to these groups to either make the app availabe, install the app, or remove the app from their Microsoft Managed Desktop device.</span></span> 

<span id="3" />

## <a name="step-3-assign-apps-to-your-users"></a><span data-ttu-id="30969-166">3 단계: 사용자에 게 앱 할당</span><span class="sxs-lookup"><span data-stu-id="30969-166">Step 3: Assign apps to your users</span></span>

<span data-ttu-id="30969-167">**사용자에 게 앱을 할당 하려면**</span><span class="sxs-lookup"><span data-stu-id="30969-167">**To assign the app to your users**</span></span>

1. <span data-ttu-id="30969-168">[Microsoft Managed 데스크톱 관리 포털](https://aka.ms/mmdportal)에 로그인 합니다.</span><span class="sxs-lookup"><span data-stu-id="30969-168">Sign in to [Microsoft Managed Desktop Admin portal](https://aka.ms/mmdportal).</span></span>
2. <span data-ttu-id="30969-169">관리 되는 데스크톱 창에서 **앱**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="30969-169">In Managed Desktop pane, select **Apps**.</span></span>
3. <span data-ttu-id="30969-170">앱 작업에서 사용자를 할당 하려는 앱을 선택 하 고 **사용자 그룹 할당**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="30969-170">In the Apps workload, select the app you want to assign users to and select **Assign users groups**.</span></span>
4. <span data-ttu-id="30969-171">특정 앱에 대해 할당 유형 (사용 가능, 필수, 제거)을 선택 하 고 적절 한 그룹을 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="30969-171">For the specific app, select an assignment type (Available, Required, Uninstall) and assign the appropriate group.</span></span>
5. <span data-ttu-id="30969-172">앱 할당 창에서 **확인**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="30969-172">In the Assign Apps pane, select **OK**.</span></span>


## <a name="steps-to-get-started-with-microsoft-managed-desktop"></a><span data-ttu-id="30969-173">Microsoft Managed Desktop을 시작 하기 위한 단계</span><span class="sxs-lookup"><span data-stu-id="30969-173">Steps to get started with Microsoft Managed Desktop</span></span>

1. [<span data-ttu-id="30969-174">관리 포털에서 관리자 연락처 추가 및 확인</span><span class="sxs-lookup"><span data-stu-id="30969-174">Add and verify admin contacts in the Admin portal</span></span>](add-admin-contacts.md)
2. [<span data-ttu-id="30969-175">조건부 액세스 조정</span><span class="sxs-lookup"><span data-stu-id="30969-175">Adjust conditional access</span></span>](conditional-access.md)
3. [<span data-ttu-id="30969-176">라이선스 할당</span><span class="sxs-lookup"><span data-stu-id="30969-176">Assign licenses</span></span>](assign-licenses.md)
4. [<span data-ttu-id="30969-177">Intune 회사 포털 배포</span><span class="sxs-lookup"><span data-stu-id="30969-177">Deploy Intune Company Portal</span></span>](company-portal.md)
5. [<span data-ttu-id="30969-178">엔터프라이즈 상태 로밍 사용</span><span class="sxs-lookup"><span data-stu-id="30969-178">Enable Enterprise State Roaming</span></span>](enterprise-state-roaming.md)
6. [<span data-ttu-id="30969-179">장치 설정</span><span class="sxs-lookup"><span data-stu-id="30969-179">Set up devices</span></span>](set-up-devices.md)
7. [<span data-ttu-id="30969-180">사용자들이 장치를 사용할 수 있도록 준비시키기</span><span class="sxs-lookup"><span data-stu-id="30969-180">Get your users ready to use devices</span></span>](get-started-devices.md)
8. <span data-ttu-id="30969-181">앱 배포 (이 항목)</span><span class="sxs-lookup"><span data-stu-id="30969-181">Deploy apps (this topic)</span></span>


<!--# Preparing apps for Microsoft Managed Desktop

This topic is the target for 2 "Learn more" links in the Admin Portal (aka.ms/app-overview;app-package); also target for link from Online resources (aka.ms/app-overviewmmd-app-prep) do not delete.

-->
