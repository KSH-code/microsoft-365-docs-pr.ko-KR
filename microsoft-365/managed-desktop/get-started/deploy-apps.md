---
title: 장치에 앱 배포
description: Microsoft Managed Desktop 디바이스에 앱을 추가하고 배포하기 위한 정보입니다.
keywords: Microsoft Managed Desktop, Microsoft 365, 서비스, 설명서, 앱, LOB 앱
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: 8bfc53d46bdcb91c16e9f4a1ddbc8ab3f6dfb47e
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/19/2021
ms.locfileid: "50922029"
---
# <a name="deploy-apps-to-devices"></a><span data-ttu-id="92ee8-104">장치에 앱 배포</span><span class="sxs-lookup"><span data-stu-id="92ee8-104">Deploy apps to devices</span></span>
<span data-ttu-id="92ee8-105">Microsoft Managed Desktop에 대한 온보드의 일부로 사용자의 장치에 앱을 추가하고 배포하는 것이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="92ee8-105">Part of onboarding to Microsoft Managed Desktop includes adding and deploying apps to your user's devices.</span></span> <span data-ttu-id="92ee8-106">Microsoft Managed Desktop 포털을 사용하고 나면 앱을 추가하고 배포할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="92ee8-106">Once you're using the Microsoft Managed Desktop portal, you can add and deploy your apps.</span></span> 

<span data-ttu-id="92ee8-107">전체 프로세스는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="92ee8-107">The overall process looks like this:</span></span>
1. <span data-ttu-id="92ee8-108">[Microsoft Managed Desktop](#1) 포털에 앱 추가 - 기존 LOB(LOB) 앱 또는 Intune과 동기화한 비즈니스용 Microsoft Store의 앱일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="92ee8-108">[Add apps to Microsoft Managed Desktop portal](#1) - This can be existing line-of-business (LOB) apps, or apps from Microsoft Store for Business that you've synced with Intune.</span></span> 
2. <span data-ttu-id="92ee8-109">[앱 할당을 위한 Azure AD(Active Directory)](#2) 그룹 만들기 - 이러한 그룹을 사용하여 앱 할당을 관리합니다.</span><span class="sxs-lookup"><span data-stu-id="92ee8-109">[Create Azure Active Directory (AD) groups for app assignment](#2) - You'll use these groups to manage app assignment.</span></span>
3. [<span data-ttu-id="92ee8-110">사용자에게 앱 할당</span><span class="sxs-lookup"><span data-stu-id="92ee8-110">Assign apps to your users</span></span>](#3)

<span id="1" />

## <a name="step-1-add-apps-to-microsoft-managed-desktop-portal"></a><span data-ttu-id="92ee8-111">1단계: Microsoft Managed Desktop 포털에 앱 추가</span><span class="sxs-lookup"><span data-stu-id="92ee8-111">Step 1: Add apps to Microsoft Managed Desktop portal</span></span>
<span data-ttu-id="92ee8-112">[Win32 또는 Windows MSI](#lob-apps)기반 앱 또는 [비즈니스용 Microsoft Store](#msfb-apps) 앱을 Microsoft Managed Desktop에 추가한 다음 Microsoft Managed Desktop 디바이스에 배포할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="92ee8-112">You can add [Win32, or Windows MSI-based apps](#lob-apps), or [Microsoft Store for Business apps](#msfb-apps) to Microsoft Managed Desktop, and then deploy them to Microsoft Managed Desktop devices.</span></span>

<span id="lob-apps">

###  <a name="win32-or-windows-msi-based-apps-to-microsoft-managed-desktop"></a><span data-ttu-id="92ee8-113">Microsoft Managed Desktop으로의 Win32 또는 Windows MSI 기반 앱</span><span class="sxs-lookup"><span data-stu-id="92ee8-113">Win32 or Windows MSI-based apps to Microsoft Managed Desktop</span></span>

<span data-ttu-id="92ee8-114">LOB(LOB) 앱을 Microsoft Managed Desktop 포털에 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="92ee8-114">You can add your line-of-business (LOB) apps to Microsoft Managed Desktop portal.</span></span> <span data-ttu-id="92ee8-115">Microsoft Managed Desktop 장치에 설치된 앱의 요구 사항에 대한 자세한 내용은 Microsoft Managed Desktop 앱 요구 [사항을 참조하세요.](../service-description/mmd-app-requirements.md)</span><span class="sxs-lookup"><span data-stu-id="92ee8-115">For information on requirements for apps installed on Microsoft Managed Desktop devices, see [Microsoft Managed Desktop app requirements](../service-description/mmd-app-requirements.md).</span></span>

<span data-ttu-id="92ee8-116">이 절차에서는 추가할 앱 종류를 선택한 다음 앱 원본을 구성 및 업로드합니다.</span><span class="sxs-lookup"><span data-stu-id="92ee8-116">In this procedure, you'll select which kind of app you want to add, and then configure and upload the app source.</span></span> 

<span data-ttu-id="92ee8-117">**LOB 앱 또는 Windows 앱을 Microsoft Managed Desktop 포털에 추가**</span><span class="sxs-lookup"><span data-stu-id="92ee8-117">**To add your LOB app or Windows app to Microsoft Managed Desktop portal**</span></span>

<span data-ttu-id="92ee8-118">Microsoft Managed Desktop 포털에 로그인하거나 Intune에 로그인한 다음 Microsoft Managed Desktop을 검색할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="92ee8-118">You can sign in to Microsoft Managed Desktop portal, or sign in to Intune and then search for Microsoft Managed Desktop.</span></span> <span data-ttu-id="92ee8-119">Microsoft Managed Desktop 포털에 로그인하는 것이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="92ee8-119">We'll show signing in to Microsoft Managed Desktop portal.</span></span> 

1.    <span data-ttu-id="92ee8-120">[Microsoft Managed Desktop Admin Portal에 로그인합니다.](https://aka.ms/mmdportal)</span><span class="sxs-lookup"><span data-stu-id="92ee8-120">Sign in to [Microsoft Managed Desktop Admin portal](https://aka.ms/mmdportal).</span></span> 
2.    <span data-ttu-id="92ee8-121">**인벤토리에서** 앱을 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="92ee8-121">Under **Inventory**, select **Apps**.</span></span>
3.    <span data-ttu-id="92ee8-122">앱 작업에서 추가를 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="92ee8-122">In the Apps workload, select **Add**.</span></span>
4.    <span data-ttu-id="92ee8-123">앱 **추가에서** **LINE-OF-BUSINESS 앱** 또는 Windows 앱(Win32)을 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="92ee8-123">In **Add app**, select **Line-of-business app** or **Windows app (Win32)**.</span></span>
    - <span data-ttu-id="92ee8-124">업무 앱 추가 및 구성에 대한 지침은 MICROSOFT [Intune에 Windows](/intune/lob-apps-windows) **LINE-OF-BUSINESS** 앱 추가를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="92ee8-124">If you selected **Line-of-business app**, see [Add a Windows line-of-business app to Microsoft Intune](/intune/lob-apps-windows) for instruction on adding and configuring line-of-business apps.</span></span>
    - <span data-ttu-id="92ee8-125">**Windows 앱(Win32)을** 선택한 경우 Windows 앱 추가 및 구성에 대한 지침은 [Win32](/intune/apps-win32-app-management) 앱 관리를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="92ee8-125">If you selected **Windows app (Win32)**, see [Win32 app management](/intune/apps-win32-app-management) for instruction on adding and configuring Windows apps.</span></span>

<span id="msfb-apps">

### <a name="microsoft-store-for-business-apps"></a><span data-ttu-id="92ee8-126">비즈니스용 Microsoft Store 앱</span><span class="sxs-lookup"><span data-stu-id="92ee8-126">Microsoft Store for Business apps</span></span>
<span data-ttu-id="92ee8-127">비즈니스용 Microsoft Store에 등록하지 않은 경우 앱을 구매할 때 등록할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="92ee8-127">If you haven't signed up with Microsoft Store for Business, you can sign up when you shop for apps.</span></span> <span data-ttu-id="92ee8-128">앱을 다운로드한 후 Microsoft Managed Desktop과 동기화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="92ee8-128">After you have your apps, you can sync them with Microsoft Managed Desktop.</span></span> 

<span data-ttu-id="92ee8-129">**비즈니스용 Microsoft Store에서 앱을 구입하는 경우**</span><span class="sxs-lookup"><span data-stu-id="92ee8-129">**To buy apps from the Microsoft Store for Business**</span></span>

1. <span data-ttu-id="92ee8-130">비즈니스용 [Microsoft Store](https://businessstore.microsoft.com) 관리자 계정으로 비즈니스용 Microsoft Store에 로그인합니다.</span><span class="sxs-lookup"><span data-stu-id="92ee8-130">Sign in to [Microsoft Store for Business](https://businessstore.microsoft.com) with your Microsoft Store for Business Admin account.</span></span>
2. <span data-ttu-id="92ee8-131">내 **그룹에 대한 쇼핑 을 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="92ee8-131">Select **Shop for my group**.</span></span>
3. <span data-ttu-id="92ee8-132">검색을 사용하여 원하는 앱을 찾고 앱을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="92ee8-132">Use Search to find that the app that you want, and select the app.</span></span>
4. <span data-ttu-id="92ee8-133">제품 세부 정보에서 앱 **다운로드를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="92ee8-133">On the product details, select **Get the App**.</span></span> <span data-ttu-id="92ee8-134">Microsoft Store는 조직의 제품에 **앱을** 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="92ee8-134">Microsoft Store adds the app to **Your products** for your organization.</span></span>

<span data-ttu-id="92ee8-135">**Intune과 비즈니스용 Microsoft Store 간에 동기화를 강제로 설정**</span><span class="sxs-lookup"><span data-stu-id="92ee8-135">**To force a sync between Intune and Microsoft Store for Business**</span></span>
1. <span data-ttu-id="92ee8-136">Microsoft Endpoint Manager 관리 센터에 [로그인합니다.](https://go.microsoft.com/fwlink/?linkid=2109431)</span><span class="sxs-lookup"><span data-stu-id="92ee8-136">Sign in to the [Microsoft Endpoint Manager admin center](https://go.microsoft.com/fwlink/?linkid=2109431).</span></span>
2. <span data-ttu-id="92ee8-137">**테넌트 관리**  >  **커넥터 및 토큰**  >  **비즈니스용 Microsoft Store 를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="92ee8-137">Select **Tenant administration** > **Connectors and tokens** > **Microsoft Store for Business**.</span></span>
3. <span data-ttu-id="92ee8-138">**동기화를** 선택하여 Microsoft Store에서 구입한 앱을 Intune으로 다운로드합니다.</span><span class="sxs-lookup"><span data-stu-id="92ee8-138">Select **Sync** to get the apps you've purchased from the Microsoft Store into Intune.</span></span>

<span data-ttu-id="92ee8-139">**Intune과 비즈니스용 Microsoft Store 간의 동기화가 활성 상태인지 확인**</span><span class="sxs-lookup"><span data-stu-id="92ee8-139">**To verify that a sync between Intune and Microsoft Store for Business is active**</span></span>
1. <span data-ttu-id="92ee8-140">비즈니스용 [Microsoft Store](https://businessstore.microsoft.com) 관리자 계정으로 비즈니스용 Microsoft Store에 로그인합니다.</span><span class="sxs-lookup"><span data-stu-id="92ee8-140">Sign in to [Microsoft Store for Business](https://businessstore.microsoft.com) with your Microsoft Store for Business Admin account.</span></span>
2. <span data-ttu-id="92ee8-141">관리를 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="92ee8-141">Select **Manage**.</span></span>
3. <span data-ttu-id="92ee8-142">설정을 **선택한** 다음 배포를 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="92ee8-142">Select **Settings** and then select **Distribute**.</span></span>
4. <span data-ttu-id="92ee8-143">관리 **도구에서** Intune이 나열되어 있으며 상태가 활성 상태인지 **확인**</span><span class="sxs-lookup"><span data-stu-id="92ee8-143">Under **Management tools**, verify that Intune is listed and that the status is **Active**.</span></span>  

<span id="2" />

## <a name="step-2-create-azure-ad-groups"></a><span data-ttu-id="92ee8-144">2단계: Azure AD 그룹 만들기</span><span class="sxs-lookup"><span data-stu-id="92ee8-144">Step 2: Create Azure AD groups</span></span>

<span data-ttu-id="92ee8-145">각 앱에 대해 3개의 Azure AD 그룹을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="92ee8-145">Create three Azure AD groups for each app.</span></span> <span data-ttu-id="92ee8-146">이 표에서는 필요한 그룹(사용 가능, 필수 및 제거)에 대해 간략하게 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="92ee8-146">This table outlines the groups you'll need (Available, Required, and Uninstall).</span></span> 

<span data-ttu-id="92ee8-147">앱 할당 유형</span><span class="sxs-lookup"><span data-stu-id="92ee8-147">App assignment type</span></span> |    <span data-ttu-id="92ee8-148">그룹 사용</span><span class="sxs-lookup"><span data-stu-id="92ee8-148">Group use</span></span>    | <span data-ttu-id="92ee8-149">예제 Azure AD 이름</span><span class="sxs-lookup"><span data-stu-id="92ee8-149">Example Azure AD name</span></span>
--- | --- | ---
<span data-ttu-id="92ee8-150">사용할 수 있음</span><span class="sxs-lookup"><span data-stu-id="92ee8-150">Available</span></span> |  <span data-ttu-id="92ee8-151">앱은 회사 포털 앱 또는 웹 사이트에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="92ee8-151">The app will be available from Company Portal app or website.</span></span> | <span data-ttu-id="92ee8-152">MMD – *앱 이름* - 사용 가능</span><span class="sxs-lookup"><span data-stu-id="92ee8-152">MMD – *app name* – Available</span></span>
<span data-ttu-id="92ee8-153">필수</span><span class="sxs-lookup"><span data-stu-id="92ee8-153">Required</span></span> |  <span data-ttu-id="92ee8-154">앱이 선택한 그룹의 장치에 설치됩니다.</span><span class="sxs-lookup"><span data-stu-id="92ee8-154">The app is installed on devices in the selected groups.</span></span> | <span data-ttu-id="92ee8-155">MMD – *앱 이름* - 필수</span><span class="sxs-lookup"><span data-stu-id="92ee8-155">MMD – *app name* – Required</span></span>
<span data-ttu-id="92ee8-156">Uninstall</span><span class="sxs-lookup"><span data-stu-id="92ee8-156">Uninstall</span></span> |  <span data-ttu-id="92ee8-157">선택한 그룹의 장치에서 앱이 제거됩니다.</span><span class="sxs-lookup"><span data-stu-id="92ee8-157">The app is uninstalled from devices in the selected groups.</span></span> | <span data-ttu-id="92ee8-158">MMD – *앱 이름* – 제거</span><span class="sxs-lookup"><span data-stu-id="92ee8-158">MMD – *app name* – Uninstall</span></span>

<span data-ttu-id="92ee8-159">이러한 그룹에 사용자를 추가하여 앱을 사용할 수 있도록 설정하거나, 앱을 설치하거나, Microsoft Managed Desktop 장치에서 앱을 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="92ee8-159">Add your users to these groups to either make the app available, install the app, or remove the app from their Microsoft Managed Desktop device.</span></span> 

<span id="3" />

## <a name="step-3-assign-apps-to-your-users"></a><span data-ttu-id="92ee8-160">3단계: 사용자에게 앱 할당</span><span class="sxs-lookup"><span data-stu-id="92ee8-160">Step 3: Assign apps to your users</span></span>

<span data-ttu-id="92ee8-161">**사용자에게 앱을 할당하기 위해**</span><span class="sxs-lookup"><span data-stu-id="92ee8-161">**To assign the app to your users**</span></span>

1. <span data-ttu-id="92ee8-162">[Microsoft Managed Desktop Admin Portal에 로그인합니다.](https://aka.ms/mmdportal)</span><span class="sxs-lookup"><span data-stu-id="92ee8-162">Sign in to [Microsoft Managed Desktop Admin portal](https://aka.ms/mmdportal).</span></span>
2. <span data-ttu-id="92ee8-163">관리되는 데스크톱 창에서 앱을 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="92ee8-163">In Managed Desktop pane, select **Apps**.</span></span>
3. <span data-ttu-id="92ee8-164">앱 작업 부하에서 사용자를 할당할 앱을 선택하고 사용자 그룹 **할당을 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="92ee8-164">In the Apps workload, select the app you want to assign users to and select **Assign users groups**.</span></span>
4. <span data-ttu-id="92ee8-165">특정 앱에 대해 할당 유형(사용 가능, 필수, 제거)을 선택하고 적절한 그룹을 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="92ee8-165">For the specific app, select an assignment type (Available, Required, Uninstall) and assign the appropriate group.</span></span>
5. <span data-ttu-id="92ee8-166">앱 할당 창에서 확인 을 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="92ee8-166">In the Assign Apps pane, select **OK**.</span></span>


## <a name="steps-to-get-started-with-microsoft-managed-desktop"></a><span data-ttu-id="92ee8-167">Microsoft Managed Desktop을 시작하기 위한 단계</span><span class="sxs-lookup"><span data-stu-id="92ee8-167">Steps to get started with Microsoft Managed Desktop</span></span>

1. [<span data-ttu-id="92ee8-168">관리 포털에서 관리자 연락처 추가 및 확인</span><span class="sxs-lookup"><span data-stu-id="92ee8-168">Add and verify admin contacts in the Admin portal</span></span>](add-admin-contacts.md)
2. [<span data-ttu-id="92ee8-169">조건부 액세스 조정</span><span class="sxs-lookup"><span data-stu-id="92ee8-169">Adjust conditional access</span></span>](conditional-access.md)
3. [<span data-ttu-id="92ee8-170">라이선스 할당</span><span class="sxs-lookup"><span data-stu-id="92ee8-170">Assign licenses</span></span>](assign-licenses.md)
4. [<span data-ttu-id="92ee8-171">Intune 회사 포털 배포</span><span class="sxs-lookup"><span data-stu-id="92ee8-171">Deploy Intune Company Portal</span></span>](company-portal.md)
5. [<span data-ttu-id="92ee8-172">엔터프라이즈 상태 로밍 사용</span><span class="sxs-lookup"><span data-stu-id="92ee8-172">Enable Enterprise State Roaming</span></span>](enterprise-state-roaming.md)
6. [<span data-ttu-id="92ee8-173">장치 설정</span><span class="sxs-lookup"><span data-stu-id="92ee8-173">Set up devices</span></span>](set-up-devices.md)
7. [<span data-ttu-id="92ee8-174">사용자들이 장치를 사용할 수 있도록 준비시키기</span><span class="sxs-lookup"><span data-stu-id="92ee8-174">Get your users ready to use devices</span></span>](get-started-devices.md)
8. <span data-ttu-id="92ee8-175">앱 배포(이 항목)</span><span class="sxs-lookup"><span data-stu-id="92ee8-175">Deploy apps (this topic)</span></span>


<!--# Preparing apps for Microsoft Managed Desktop

This topic is the target for 2 "Learn more" links in the Admin Portal (aka.ms/app-overview;app-package); also target for link from Online resources (aka.ms/app-overviewmmd-app-prep) do not delete.

-->