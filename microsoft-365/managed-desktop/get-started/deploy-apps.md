---
title: 장치에 앱 배포
description: Microsoft Managed Desktop 장치에 앱을 추가 및 배포 하기 위한 정보
keywords: Microsoft Managed Desktop, Microsoft 365, 서비스, 설명서, 앱, LOB (기간 업무) 앱, 업무용 앱
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: 2eb8b984550f301af9d99e738f6db4623aa2cc86
ms.sourcegitcommit: 6647055154002c7d3b8f7ce25ad53c9636bc8066
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2020
ms.locfileid: "48769109"
---
# <a name="deploy-apps-to-devices"></a><span data-ttu-id="c6f0e-104">장치에 앱 배포</span><span class="sxs-lookup"><span data-stu-id="c6f0e-104">Deploy apps to devices</span></span>
<span data-ttu-id="c6f0e-105">Microsoft Managed Desktop 온 보 딩에는 사용자의 장치에 앱을 추가 및 배포 하는 작업이 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c6f0e-105">Part of onboarding to Microsoft Managed Desktop includes adding and deploying apps to your user's devices.</span></span> <span data-ttu-id="c6f0e-106">Microsoft Managed Desktop portal을 사용 하 고 나면 앱을 추가 및 배포할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c6f0e-106">Once you're using the Microsoft Managed Desktop portal, you can add and deploy your apps.</span></span> 

<span data-ttu-id="c6f0e-107">전체 프로세스는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="c6f0e-107">The overall process looks like this:</span></span>
1. <span data-ttu-id="c6f0e-108">[Microsoft Managed Desktop portal에 앱 추가](#1) -이는 기존 LOB (기간 업무) 앱 이거나 Intune을 사용 하 여 동기화 한 Microsoft Store 비즈니스용 앱이 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c6f0e-108">[Add apps to Microsoft Managed Desktop portal](#1) - This can be existing line-of-business (LOB) apps, or apps from Microsoft Store for Business that you've synced with Intune.</span></span> 
2. <span data-ttu-id="c6f0e-109">[앱 할당에 대 한 AZURE AD (Active Directory) 그룹 만들기](#2) -이러한 그룹을 사용 하 여 앱 할당을 관리 합니다.</span><span class="sxs-lookup"><span data-stu-id="c6f0e-109">[Create Azure Active Directory (AD) groups for app assignment](#2) - You'll use these groups to manage app assignment.</span></span>
3. [<span data-ttu-id="c6f0e-110">사용자에 게 앱 할당</span><span class="sxs-lookup"><span data-stu-id="c6f0e-110">Assign apps to your users</span></span>](#3)

<span id="1" />

## <a name="step-1-add-apps-to-microsoft-managed-desktop-portal"></a><span data-ttu-id="c6f0e-111">1 단계: Microsoft Managed Desktop portal에 앱 추가</span><span class="sxs-lookup"><span data-stu-id="c6f0e-111">Step 1: Add apps to Microsoft Managed Desktop portal</span></span>
<span data-ttu-id="c6f0e-112">[Win32 또는 WINDOWS MSI 기반 앱](#lob-apps)또는 [비즈니스용 Microsoft Store for Business Apps](#msfb-apps) 를 microsoft managed desktop에 추가한 다음이를 microsoft managed desktop 장치에 배포할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c6f0e-112">You can add [Win32, or Windows MSI-based apps](#lob-apps), or [Microsoft Store for Business apps](#msfb-apps) to Microsoft Managed Desktop, and then deploy them to Microsoft Managed Desktop devices.</span></span>

<span id="lob-apps">

###  <a name="win32-or-windows-msi-based-apps-to-microsoft-managed-desktop"></a><span data-ttu-id="c6f0e-113">Microsoft Managed Desktop에 대 한 Win32 또는 Windows MSI 기반 앱</span><span class="sxs-lookup"><span data-stu-id="c6f0e-113">Win32 or Windows MSI-based apps to Microsoft Managed Desktop</span></span>

<span data-ttu-id="c6f0e-114">기간 업무 (LOB) 앱을 Microsoft Managed Desktop portal에 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c6f0e-114">You can add your line-of-business (LOB) apps to Microsoft Managed Desktop portal.</span></span> <span data-ttu-id="c6f0e-115">Microsoft Managed Desktop 장치에 설치 된 앱에 대 한 요구 사항에 대 한 자세한 내용은 [Microsoft Managed desktop app 요구 사항을](https://docs.microsoft.com/microsoft-365/managed-desktop/service-description/mmd-app-requirements)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="c6f0e-115">For information on requirements for apps installed on Microsoft Managed Desktop devices, see [Microsoft Managed Desktop app requirements](https://docs.microsoft.com/microsoft-365/managed-desktop/service-description/mmd-app-requirements).</span></span>

<span data-ttu-id="c6f0e-116">이 절차에서는 추가 하려는 앱의 종류를 선택한 다음 앱 원본을 구성 및 업로드 합니다.</span><span class="sxs-lookup"><span data-stu-id="c6f0e-116">In this procedure, you'll select which kind of app you want to add, and then configure and upload the app source.</span></span> 

<span data-ttu-id="c6f0e-117">**Microsoft Managed Desktop portal에 LOB 앱 또는 Windows 앱을 추가 하려면**</span><span class="sxs-lookup"><span data-stu-id="c6f0e-117">**To add your LOB app or Windows app to Microsoft Managed Desktop portal**</span></span>

<span data-ttu-id="c6f0e-118">Microsoft Managed Desktop portal에 로그인 하거나 Intune에 로그인 한 다음 Microsoft Managed Desktop을 검색할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c6f0e-118">You can sign in to Microsoft Managed Desktop portal, or sign in to Intune and then search for Microsoft Managed Desktop.</span></span> <span data-ttu-id="c6f0e-119">Microsoft Managed Desktop portal에 로그인을 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="c6f0e-119">We'll show signing in to Microsoft Managed Desktop portal.</span></span> 

1.    <span data-ttu-id="c6f0e-120">[Microsoft Managed 데스크톱 관리 포털](https://aka.ms/mmdportal)에 로그인 합니다.</span><span class="sxs-lookup"><span data-stu-id="c6f0e-120">Sign in to [Microsoft Managed Desktop Admin portal](https://aka.ms/mmdportal).</span></span> 
2.    <span data-ttu-id="c6f0e-121">**인벤토리에서** **앱** 을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="c6f0e-121">Under **Inventory** , select **Apps** .</span></span>
3.    <span data-ttu-id="c6f0e-122">앱 작업에서 **추가** 를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="c6f0e-122">In the Apps workload, select **Add** .</span></span>
4.    <span data-ttu-id="c6f0e-123">**앱 추가** 에서 lob ( **기간 업무) 앱** 또는 **Windows 앱 (Win32)** 을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="c6f0e-123">In **Add app** , select **Line-of-business app** or **Windows app (Win32)** .</span></span>
    - <span data-ttu-id="c6f0e-124">**기간 업무** (lob) 앱을 선택한 경우 lob (기간 업무) 앱 추가 및 구성에 대 한 지침을 보려면 [Microsoft Intune에 Windows lob (기간 업무) 앱 추가](https://docs.microsoft.com/intune/lob-apps-windows) 를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="c6f0e-124">If you selected **Line-of-business app** , see [Add a Windows line-of-business app to Microsoft Intune](https://docs.microsoft.com/intune/lob-apps-windows) for instruction on adding and configuring line-of-business apps.</span></span>
    - <span data-ttu-id="c6f0e-125">**Windows 앱 (win32)** 을 선택한 경우 windows 앱 추가 및 구성에 대 한 지침은 [win32 앱 관리](https://docs.microsoft.com/intune/apps-win32-app-management) 를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="c6f0e-125">If you selected **Windows app (Win32)** , see [Win32 app management](https://docs.microsoft.com/intune/apps-win32-app-management) for instruction on adding and configuring Windows apps.</span></span>

<span id="msfb-apps">

### <a name="microsoft-store-for-business-apps"></a><span data-ttu-id="c6f0e-126">Microsoft Store for Business 앱</span><span class="sxs-lookup"><span data-stu-id="c6f0e-126">Microsoft Store for Business apps</span></span>
<span data-ttu-id="c6f0e-127">Microsoft Store for Business에 등록 하지 않은 경우 앱을 쇼핑 하면 등록할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c6f0e-127">If you haven't signed up with Microsoft Store for Business, you can sign up when you shop for apps.</span></span> <span data-ttu-id="c6f0e-128">앱을 설치한 후에는 Microsoft Managed Desktop과 동기화 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c6f0e-128">After you have your apps, you can sync them with Microsoft Managed Desktop.</span></span> 

<span data-ttu-id="c6f0e-129">**Microsoft Store for Business에서 앱을 구입 하려면**</span><span class="sxs-lookup"><span data-stu-id="c6f0e-129">**To buy apps from the Microsoft Store for Business**</span></span>

1. <span data-ttu-id="c6f0e-130">비즈니스용 microsoft 스토어 관리자 계정을 사용 하 여 [비즈니스용 Microsoft 스토어](https://businessstore.microsoft.com) 에 로그인 합니다.</span><span class="sxs-lookup"><span data-stu-id="c6f0e-130">Sign in to [Microsoft Store for Business](https://businessstore.microsoft.com) with your Microsoft Store for Business Admin account.</span></span>
2. <span data-ttu-id="c6f0e-131">**내 그룹의 상점을** 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="c6f0e-131">Select **Shop for my group** .</span></span>
3. <span data-ttu-id="c6f0e-132">검색을 사용 하 여 원하는 앱을 찾은 다음 앱을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="c6f0e-132">Use Search to find that the app that you want, and select the app.</span></span>
4. <span data-ttu-id="c6f0e-133">제품 정보에서 **앱 가져오기를** 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="c6f0e-133">On the product details, select **Get the App** .</span></span> <span data-ttu-id="c6f0e-134">Microsoft Store에서는 조직의 **제품** 에 앱이 추가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c6f0e-134">Microsoft Store adds the app to **Your products** for your organization.</span></span>

<span data-ttu-id="c6f0e-135">**Intune과 비즈니스용 Microsoft Store를 강제 동기화 하려면**</span><span class="sxs-lookup"><span data-stu-id="c6f0e-135">**To force a sync between Intune and Microsoft Store for Business**</span></span>
1. <span data-ttu-id="c6f0e-136">[Microsoft Endpoint Manager 관리 센터](https://go.microsoft.com/fwlink/?linkid=2109431)에 로그인 합니다.</span><span class="sxs-lookup"><span data-stu-id="c6f0e-136">Sign in to the [Microsoft Endpoint Manager admin center](https://go.microsoft.com/fwlink/?linkid=2109431).</span></span>
2. <span data-ttu-id="c6f0e-137">비즈니스용 **테 넌 트 관리**  >  **커넥터 및 토큰**  >  **Microsoft Store** 를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="c6f0e-137">Select **Tenant administration** > **Connectors and tokens** > **Microsoft Store for Business** .</span></span>
3. <span data-ttu-id="c6f0e-138">**동기화** 를 선택 하 여 Microsoft Store에서 구입한 앱을 Intune으로 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="c6f0e-138">Select **Sync** to get the apps you've purchased from the Microsoft Store into Intune.</span></span>

<span data-ttu-id="c6f0e-139">**Intune과 비즈니스용 Microsoft Store 간의 동기화가 활성 상태 인지 확인 하려면**</span><span class="sxs-lookup"><span data-stu-id="c6f0e-139">**To verify that a sync between Intune and Microsoft Store for Business is active**</span></span>
1. <span data-ttu-id="c6f0e-140">비즈니스용 microsoft 스토어 관리자 계정을 사용 하 여 [비즈니스용 Microsoft 스토어](https://businessstore.microsoft.com) 에 로그인 합니다.</span><span class="sxs-lookup"><span data-stu-id="c6f0e-140">Sign in to [Microsoft Store for Business](https://businessstore.microsoft.com) with your Microsoft Store for Business Admin account.</span></span>
2. <span data-ttu-id="c6f0e-141">**관리** 를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="c6f0e-141">Select **Manage** .</span></span>
3. <span data-ttu-id="c6f0e-142">**설정을** 선택 하 고 **배포** 를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="c6f0e-142">Select **Settings** and then select **Distribute** .</span></span>
4. <span data-ttu-id="c6f0e-143">**관리 도구** 에서 Intune이 나열 되는지와 상태가 **활성** 상태 인지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="c6f0e-143">Under **Management tools** , verify that Intune is listed and that the status is **Active** .</span></span>  

<span id="2" />

## <a name="step-2-create-azure-ad-groups"></a><span data-ttu-id="c6f0e-144">2 단계: Azure AD 그룹 만들기</span><span class="sxs-lookup"><span data-stu-id="c6f0e-144">Step 2: Create Azure AD groups</span></span>

<span data-ttu-id="c6f0e-145">각 앱에 대해 세 개의 Azure AD 그룹을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="c6f0e-145">Create three Azure AD groups for each app.</span></span> <span data-ttu-id="c6f0e-146">이 표에는 필요한 그룹 (사용 가능, 필수 및 제거)이 정리 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c6f0e-146">This table outlines the groups you'll need (Available, Required, and Uninstall).</span></span> 

<span data-ttu-id="c6f0e-147">앱 할당 유형</span><span class="sxs-lookup"><span data-stu-id="c6f0e-147">App assignment type</span></span> |    <span data-ttu-id="c6f0e-148">그룹 사용</span><span class="sxs-lookup"><span data-stu-id="c6f0e-148">Group use</span></span>    | <span data-ttu-id="c6f0e-149">예제 Azure AD 이름</span><span class="sxs-lookup"><span data-stu-id="c6f0e-149">Example Azure AD name</span></span>
--- | --- | ---
<span data-ttu-id="c6f0e-150">사용할 수 있음</span><span class="sxs-lookup"><span data-stu-id="c6f0e-150">Available</span></span> |  <span data-ttu-id="c6f0e-151">이 앱은 회사 포털 앱 또는 웹 사이트에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c6f0e-151">The app will be available from Company Portal app or website.</span></span> | <span data-ttu-id="c6f0e-152">MMD- *응용 프로그램 이름* -사용 가능</span><span class="sxs-lookup"><span data-stu-id="c6f0e-152">MMD – *app name* – Available</span></span>
<span data-ttu-id="c6f0e-153">필수</span><span class="sxs-lookup"><span data-stu-id="c6f0e-153">Required</span></span> |  <span data-ttu-id="c6f0e-154">앱이 선택한 그룹의 장치에 설치 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c6f0e-154">The app is installed on devices in the selected groups.</span></span> | <span data-ttu-id="c6f0e-155">MMD- *응용 프로그램 이름* -필수</span><span class="sxs-lookup"><span data-stu-id="c6f0e-155">MMD – *app name* – Required</span></span>
<span data-ttu-id="c6f0e-156">Uninstall</span><span class="sxs-lookup"><span data-stu-id="c6f0e-156">Uninstall</span></span> |  <span data-ttu-id="c6f0e-157">앱이 선택한 그룹의 장치에서 제거 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="c6f0e-157">The app is uninstalled from devices in the selected groups.</span></span> | <span data-ttu-id="c6f0e-158">MMD- *응용 프로그램 이름* -제거</span><span class="sxs-lookup"><span data-stu-id="c6f0e-158">MMD – *app name* – Uninstall</span></span>

<span data-ttu-id="c6f0e-159">이러한 그룹에 사용자를 추가 하 여 앱을 사용할 수 있도록 설정 하거나, 앱을 설치 하거나, Microsoft Managed Desktop 장치에서 앱을 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="c6f0e-159">Add your users to these groups to either make the app available, install the app, or remove the app from their Microsoft Managed Desktop device.</span></span> 

<span id="3" />

## <a name="step-3-assign-apps-to-your-users"></a><span data-ttu-id="c6f0e-160">3 단계: 사용자에 게 앱 할당</span><span class="sxs-lookup"><span data-stu-id="c6f0e-160">Step 3: Assign apps to your users</span></span>

<span data-ttu-id="c6f0e-161">**사용자에 게 앱을 할당 하려면**</span><span class="sxs-lookup"><span data-stu-id="c6f0e-161">**To assign the app to your users**</span></span>

1. <span data-ttu-id="c6f0e-162">[Microsoft Managed 데스크톱 관리 포털](https://aka.ms/mmdportal)에 로그인 합니다.</span><span class="sxs-lookup"><span data-stu-id="c6f0e-162">Sign in to [Microsoft Managed Desktop Admin portal](https://aka.ms/mmdportal).</span></span>
2. <span data-ttu-id="c6f0e-163">관리 되는 데스크톱 창에서 **앱** 을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="c6f0e-163">In Managed Desktop pane, select **Apps** .</span></span>
3. <span data-ttu-id="c6f0e-164">앱 작업에서 사용자를 할당 하려는 앱을 선택 하 고 **사용자 그룹 할당** 을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="c6f0e-164">In the Apps workload, select the app you want to assign users to and select **Assign users groups** .</span></span>
4. <span data-ttu-id="c6f0e-165">특정 앱에 대해 할당 유형 (사용 가능, 필수, 제거)을 선택 하 고 적절 한 그룹을 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="c6f0e-165">For the specific app, select an assignment type (Available, Required, Uninstall) and assign the appropriate group.</span></span>
5. <span data-ttu-id="c6f0e-166">앱 할당 창에서 **확인** 을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="c6f0e-166">In the Assign Apps pane, select **OK** .</span></span>


## <a name="steps-to-get-started-with-microsoft-managed-desktop"></a><span data-ttu-id="c6f0e-167">Microsoft Managed Desktop을 시작하기 위한 단계</span><span class="sxs-lookup"><span data-stu-id="c6f0e-167">Steps to get started with Microsoft Managed Desktop</span></span>

1. [<span data-ttu-id="c6f0e-168">관리 포털에서 관리자 연락처 추가 및 확인</span><span class="sxs-lookup"><span data-stu-id="c6f0e-168">Add and verify admin contacts in the Admin portal</span></span>](add-admin-contacts.md)
2. [<span data-ttu-id="c6f0e-169">조건부 액세스 조정</span><span class="sxs-lookup"><span data-stu-id="c6f0e-169">Adjust conditional access</span></span>](conditional-access.md)
3. [<span data-ttu-id="c6f0e-170">라이선스 할당</span><span class="sxs-lookup"><span data-stu-id="c6f0e-170">Assign licenses</span></span>](assign-licenses.md)
4. [<span data-ttu-id="c6f0e-171">Intune 회사 포털 배포</span><span class="sxs-lookup"><span data-stu-id="c6f0e-171">Deploy Intune Company Portal</span></span>](company-portal.md)
5. [<span data-ttu-id="c6f0e-172">엔터프라이즈 상태 로밍 사용</span><span class="sxs-lookup"><span data-stu-id="c6f0e-172">Enable Enterprise State Roaming</span></span>](enterprise-state-roaming.md)
6. [<span data-ttu-id="c6f0e-173">장치 설정</span><span class="sxs-lookup"><span data-stu-id="c6f0e-173">Set up devices</span></span>](set-up-devices.md)
7. [<span data-ttu-id="c6f0e-174">사용자들이 장치를 사용할 수 있도록 준비시키기</span><span class="sxs-lookup"><span data-stu-id="c6f0e-174">Get your users ready to use devices</span></span>](get-started-devices.md)
8. <span data-ttu-id="c6f0e-175">앱 배포 (이 항목)</span><span class="sxs-lookup"><span data-stu-id="c6f0e-175">Deploy apps (this topic)</span></span>


<!--# Preparing apps for Microsoft Managed Desktop

This topic is the target for 2 "Learn more" links in the Admin Portal (aka.ms/app-overview;app-package); also target for link from Online resources (aka.ms/app-overviewmmd-app-prep) do not delete.

-->
