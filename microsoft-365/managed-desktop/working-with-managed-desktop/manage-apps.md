---
title: Microsoft Managed Desktop에서 앱 관리
description: Microsoft Managed Desktop 장치에 배포 되는 기간 업무 (lob) 앱 업데이트 방법에 대 한 정보
keywords: Microsoft Managed Desktop, Microsoft 365, 서비스, 설명서
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.date: 01/18/2019
ms.collection: M365-modern-desktop
ms.openlocfilehash: 425ba674ca9911e4c93bda4fc9ad61cec7fb85b7
ms.sourcegitcommit: 3d37043c0447359c952dc99026c219dd69f6fb8d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/06/2019
ms.locfileid: "38012413"
---
# <a name="manage-line-of-business-apps-in-microsoft-managed-desktop"></a><span data-ttu-id="4cba0-104">Microsoft Managed Desktop에서 기간 업무 (lob) 앱 관리</span><span class="sxs-lookup"><span data-stu-id="4cba0-104">Manage line-of-business apps in Microsoft Managed Desktop</span></span>

<!--Application management -->

<span data-ttu-id="4cba0-105">Microsoft Managed Desktop에 등록 Microsoft Managed Desktop 장치에 배포 된 앱에 대 한 앱 업데이트를 관리 하는 방법에는 몇 가지가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4cba0-105">There are a couple of ways to manage app updates for apps that you've onboarded to Microsoft Managed Desktop and deployed to your Microsoft Managed Desktop devices.</span></span> <span data-ttu-id="4cba0-106">Microsoft Managed Desktop portal 또는 Intune에서 앱 업데이트를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4cba0-106">You can make app updates in Microsoft Managed Desktop portal, or Intune.</span></span> 

<span id="update-app-mmd" />

## <a name="update-line-of-business-apps-in-microsoft-managed-desktop"></a><span data-ttu-id="4cba0-107">Microsoft Managed Desktop에서 기간 업무 (lob) 앱 업데이트</span><span class="sxs-lookup"><span data-stu-id="4cba0-107">Update line-of-business apps in Microsoft Managed Desktop</span></span>

<span data-ttu-id="4cba0-108">**Microsoft Managed Desktop portal에서 기간 업무 (lob) 앱을 업데이트 하려면**</span><span class="sxs-lookup"><span data-stu-id="4cba0-108">**To update your line-of-business apps in Microsoft Managed Desktop portal**</span></span>
1. <span data-ttu-id="4cba0-109">[Microsoft Managed 데스크톱 관리 포털](https://aka.ms/mmdportal)에 로그인 합니다.</span><span class="sxs-lookup"><span data-stu-id="4cba0-109">Sign in to [Microsoft Managed Desktop Admin portal](https://aka.ms/mmdportal).</span></span>
2. <span data-ttu-id="4cba0-110">**인벤토리에서** **앱**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="4cba0-110">Under **Inventory**, select **Apps**.</span></span>  
3. <span data-ttu-id="4cba0-111">업데이트할 앱을 선택 하 고 **편집**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="4cba0-111">Select the app you want to updates, and then select **Edit**.</span></span>
4. <span data-ttu-id="4cba0-112">**관리**에서 **속성**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="4cba0-112">Under **Manage**, select **Properties**.</span></span> 
5. <span data-ttu-id="4cba0-113">**앱 패키지 파일**을 클릭 한 다음 새 앱 패키지 파일을 찾아서 업로드 합니다.</span><span class="sxs-lookup"><span data-stu-id="4cba0-113">Click **App package file**, and then browse to upload a new app package file.</span></span>
6. <span data-ttu-id="4cba0-114">**앱 패키지 파일**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="4cba0-114">Select **App package file**.</span></span>
7. <span data-ttu-id="4cba0-115">폴더 아이콘을 선택 하 고 업데이트 된 앱 파일의 위치를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="4cba0-115">Select the folder icon and browse to the location of your updated app file.</span></span> <span data-ttu-id="4cba0-116">**열기**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="4cba0-116">Select **Open**.</span></span> <span data-ttu-id="4cba0-117">앱 정보가 패키지 정보로 업데이트 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4cba0-117">The app information is updated with the package information.</span></span>
8. <span data-ttu-id="4cba0-118">**앱 버전이** 업데이트 된 앱 패키지를 반영 하는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="4cba0-118">Verify that **App version** reflects the updated app package.</span></span> 

<span data-ttu-id="4cba0-119">업데이트 된 앱이 사용자의 장치에 배포 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4cba0-119">The updated app will be deployed to your user's devices.</span></span>

<span id="update-app-intune" />

## <a name="update-line-of-business-apps-in-intune"></a><span data-ttu-id="4cba0-120">Intune에서 기간 업무 (lob) 앱 업데이트</span><span class="sxs-lookup"><span data-stu-id="4cba0-120">Update line-of-business apps in Intune</span></span>

<span data-ttu-id="4cba0-121">**Intune에서 기간 업무 (lob) 앱을 업데이트 하려면**</span><span class="sxs-lookup"><span data-stu-id="4cba0-121">**To update your line-of-business apps in Intune**</span></span>
1. <span data-ttu-id="4cba0-122">[Azure 포털](https://azure.portal.com)에 로그인 합니다.</span><span class="sxs-lookup"><span data-stu-id="4cba0-122">Sign in to [Azure portal](https://azure.portal.com).</span></span>
2. <span data-ttu-id="4cba0-123">**모든 서비스** > **Intune**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="4cba0-123">Select **All Services** > **Intune**.</span></span> <span data-ttu-id="4cba0-124">Intune은 **모니터링 + 관리** 섹션에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4cba0-124">Intune is in the **Monitoring + Management** section.</span></span>
3. <span data-ttu-id="4cba0-125">**클라이언트 앱 > 앱**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="4cba0-125">Select **Client Apps > Apps**.</span></span>
4. <span data-ttu-id="4cba0-126">앱 목록에서 앱을 찾아 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="4cba0-126">Find and select your app in the list of apps.</span></span>
5. <span data-ttu-id="4cba0-127">**개요** 블레이드에서 **속성**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="4cba0-127">In the **Overview** blade, select **Properties**.</span></span>
6. <span data-ttu-id="4cba0-128">**앱 패키지 파일**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="4cba0-128">Select **App package file**.</span></span>
7. <span data-ttu-id="4cba0-129">폴더 아이콘을 선택 하 고 업데이트 된 앱 파일의 위치를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="4cba0-129">Select the folder icon and browse to the location of your updated app file.</span></span> <span data-ttu-id="4cba0-130">**열기**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="4cba0-130">Select **Open**.</span></span> <span data-ttu-id="4cba0-131">앱 정보가 패키지 정보로 업데이트 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4cba0-131">The app information is updated with the package information.</span></span>
8. <span data-ttu-id="4cba0-132">**앱 버전이** 업데이트 된 앱 패키지를 반영 하는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="4cba0-132">Verify that **App version** reflects the updated app package.</span></span>

<span id="roll-back-app-mmd" />

## <a name="roll-back-an-app-to-a-previous-version"></a><span data-ttu-id="4cba0-133">앱을 이전 버전으로 롤백</span><span class="sxs-lookup"><span data-stu-id="4cba0-133">Roll back an app to a previous version</span></span>

<span data-ttu-id="4cba0-134">새 버전의 앱이 배포 될 때 오류가 발견 되는 경우 이전 버전으로 롤백할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4cba0-134">If there's an error found when a new version of an app is deployed, you can roll back to a previous version.</span></span> <span data-ttu-id="4cba0-135">여기에 설명 된 프로세스는 유형이 **WINDOWS MSI lob (기간 업무) 앱** 또는 **Windows app (Win 32)-preview** 로 나열 된 앱에 대 한 것입니다.</span><span class="sxs-lookup"><span data-stu-id="4cba0-135">The process outlined here is for apps where type is listed as **Windows MSI line-of-business app** or **Windows app (Win 32) - preview**</span></span>

<span data-ttu-id="4cba0-136">**기간 업무 (lob) 앱을 이전 버전으로 롤백하는 방법**</span><span class="sxs-lookup"><span data-stu-id="4cba0-136">**To roll back a line-of-business app to a previous version**</span></span>

1. <span data-ttu-id="4cba0-137">[Microsoft Managed 데스크톱 관리 포털](https://aka.ms/mmdportal)에 로그인 합니다.</span><span class="sxs-lookup"><span data-stu-id="4cba0-137">Sign in to [Microsoft Managed Desktop Admin portal](https://aka.ms/mmdportal).</span></span>
2. <span data-ttu-id="4cba0-138">**인벤토리에서** **앱**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="4cba0-138">Under **Inventory**, select **Apps**.</span></span>  
3. <span data-ttu-id="4cba0-139">롤백하는 데 필요한 앱을 선택 하 고 **편집**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="4cba0-139">Select the app you need to roll back, and then select **Edit**.</span></span>
4. <span data-ttu-id="4cba0-140">**관리**에서 **속성**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="4cba0-140">Under **Manage**, select **Properties**.</span></span> 
    - <span data-ttu-id="4cba0-141">**WINDOWS MSI lob (기간 업무) 앱** 앱의 경우 **앱 정보**를 선택 하 고 **응용 프로그램 버전 무시**에서 **예**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="4cba0-141">For **Windows MSI line-of-business app** apps, select **App information**, and then under **Ignore app version**, select **Yes**.</span></span>
    - <span data-ttu-id="4cba0-142">**Windows 앱 (Win 32)-미리 보기** 앱에서 **앱 정보**를 선택 하 고 **검색 규칙**을 선택한 다음 **추가**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="4cba0-142">For **Windows app (Win 32) - preview** apps, select **App information**, select **Detection rules**, and then select **Add**.</span></span> 
    <span data-ttu-id="4cba0-143">MSI 규칙이 있는 경우 **msi 제품 버전 확인** 이 **아니요로**설정 되어 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="4cba0-143">If there is an MSI rule, verify that **MSI product version check** is set to **No**.</span></span>
5. <span data-ttu-id="4cba0-144">[이전 버전의 앱 원본 파일](../get-started/deploy-apps.md) 을 Microsoft Managed Desktop administration Portal에 업로드 합니다.</span><span class="sxs-lookup"><span data-stu-id="4cba0-144">[Upload a previous version of the app source file](../get-started/deploy-apps.md) to Microsoft Managed Desktop Admin portal.</span></span>  

