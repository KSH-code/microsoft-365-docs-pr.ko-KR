---
title: 앱에서 앱 Microsoft Managed Desktop
description: 디바이스에 배포된 업무용 앱을 업데이트하는 Microsoft Managed Desktop 정보
keywords: Microsoft Managed Desktop, Microsoft 365, 서비스, 문서
ms.service: m365-md
author: jaimeo
f1.keywords:
- NOCSH
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.localizationpriority: normal
ms.date: 01/18/2019
ms.collection: M365-modern-desktop
ms.openlocfilehash: b016d8458b4b4cc9f6b684d3b8a3c0a1e1322fef
ms.sourcegitcommit: be929f79751c0c52dfa6bd98a854432a0c63faf0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/14/2021
ms.locfileid: "52925410"
---
# <a name="manage-line-of-business-apps-in-microsoft-managed-desktop"></a><span data-ttu-id="b70da-104">Microsoft Managed Desktop에서 업무용 앱 관리</span><span class="sxs-lookup"><span data-stu-id="b70da-104">Manage line-of-business apps in Microsoft Managed Desktop</span></span>

<!--Application management -->

<span data-ttu-id="b70da-105">앱에 온보드하고 앱 디바이스에 배포한 앱에 대한 앱 업데이트를 Microsoft Managed Desktop 두 가지 Microsoft Managed Desktop 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b70da-105">There are a couple of ways to manage app updates for apps that you've onboarded to Microsoft Managed Desktop and deployed to your Microsoft Managed Desktop devices.</span></span> <span data-ttu-id="b70da-106">포털 또는 Intune에서 앱을 Microsoft Managed Desktop 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b70da-106">You can make app updates in Microsoft Managed Desktop portal, or Intune.</span></span> 

<span id="update-app-mmd" />

## <a name="update-line-of-business-apps-in-microsoft-managed-desktop"></a><span data-ttu-id="b70da-107">2016년 12월에 업무용 앱을 Microsoft Managed Desktop</span><span class="sxs-lookup"><span data-stu-id="b70da-107">Update line-of-business apps in Microsoft Managed Desktop</span></span>

<span data-ttu-id="b70da-108">**포털에서 업무용 앱을 Microsoft Managed Desktop**</span><span class="sxs-lookup"><span data-stu-id="b70da-108">**To update your line-of-business apps in Microsoft Managed Desktop portal**</span></span>
1. <span data-ttu-id="b70da-109">관리자 포털 [Microsoft Managed Desktop 로그인합니다.](https://aka.ms/mmdportal)</span><span class="sxs-lookup"><span data-stu-id="b70da-109">Sign in to [Microsoft Managed Desktop Admin portal](https://aka.ms/mmdportal).</span></span>
2. <span data-ttu-id="b70da-110">**인벤토리에서** 앱을 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="b70da-110">Under **Inventory**, select **Apps**.</span></span>  
3. <span data-ttu-id="b70da-111">업데이트할 앱을 선택하고 편집 을 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="b70da-111">Select the app you want to updates, and then select **Edit**.</span></span>
4. <span data-ttu-id="b70da-112">**관리에서** 속성을 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="b70da-112">Under **Manage**, select **Properties**.</span></span> 
5. <span data-ttu-id="b70da-113">앱 **패키지 파일을 클릭한** 다음 새 앱 패키지 파일을 업로드합니다.</span><span class="sxs-lookup"><span data-stu-id="b70da-113">Click **App package file**, and then browse to upload a new app package file.</span></span>
6. <span data-ttu-id="b70da-114">앱 **패키지 파일을 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="b70da-114">Select **App package file**.</span></span>
7. <span data-ttu-id="b70da-115">폴더 아이콘을 선택하고 업데이트된 앱 파일의 위치로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="b70da-115">Select the folder icon and browse to the location of your updated app file.</span></span> <span data-ttu-id="b70da-116">**열기** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="b70da-116">Select **Open**.</span></span> <span data-ttu-id="b70da-117">앱 정보가 패키지 정보로 업데이트됩니다.</span><span class="sxs-lookup"><span data-stu-id="b70da-117">The app information is updated with the package information.</span></span>
8. <span data-ttu-id="b70da-118">앱 **버전이 업데이트된** 앱 패키지를 반영하는지 확인</span><span class="sxs-lookup"><span data-stu-id="b70da-118">Verify that **App version** reflects the updated app package.</span></span> 

<span data-ttu-id="b70da-119">업데이트된 앱이 사용자의 디바이스에 배포됩니다.</span><span class="sxs-lookup"><span data-stu-id="b70da-119">The updated app will be deployed to your user's devices.</span></span>

<span id="update-app-intune" />

## <a name="update-line-of-business-apps-in-intune"></a><span data-ttu-id="b70da-120">Intune에서 업무용 앱 업데이트</span><span class="sxs-lookup"><span data-stu-id="b70da-120">Update line-of-business apps in Intune</span></span>

<span data-ttu-id="b70da-121">**Intune에서 업무용 앱을 업데이트하는 경우**</span><span class="sxs-lookup"><span data-stu-id="b70da-121">**To update your line-of-business apps in Intune**</span></span>
1. <span data-ttu-id="b70da-122">[Azure Portal에 로그인합니다.](https://portal.azure.com)</span><span class="sxs-lookup"><span data-stu-id="b70da-122">Sign in to [Azure portal](https://portal.azure.com).</span></span>
2. <span data-ttu-id="b70da-123">모든 **서비스**  >  **Intune을 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="b70da-123">Select **All Services** > **Intune**.</span></span> <span data-ttu-id="b70da-124">Intune은 **모니터링 + 관리 섹션에** 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b70da-124">Intune is in the **Monitoring + Management** section.</span></span>
3. <span data-ttu-id="b70da-125">클라이언트 **앱 및 > 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="b70da-125">Select **Client Apps > Apps**.</span></span>
4. <span data-ttu-id="b70da-126">앱 목록에서 앱을 찾아 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="b70da-126">Find and select your app in the list of apps.</span></span>
5. <span data-ttu-id="b70da-127">개요 **블레이드에서** 속성을 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="b70da-127">In the **Overview** blade, select **Properties**.</span></span>
6. <span data-ttu-id="b70da-128">앱 **패키지 파일을 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="b70da-128">Select **App package file**.</span></span>
7. <span data-ttu-id="b70da-129">폴더 아이콘을 선택하고 업데이트된 앱 파일의 위치로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="b70da-129">Select the folder icon and browse to the location of your updated app file.</span></span> <span data-ttu-id="b70da-130">**열기** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="b70da-130">Select **Open**.</span></span> <span data-ttu-id="b70da-131">앱 정보가 패키지 정보로 업데이트됩니다.</span><span class="sxs-lookup"><span data-stu-id="b70da-131">The app information is updated with the package information.</span></span>
8. <span data-ttu-id="b70da-132">앱 **버전이 업데이트된** 앱 패키지를 반영하는지 확인</span><span class="sxs-lookup"><span data-stu-id="b70da-132">Verify that **App version** reflects the updated app package.</span></span>

<span id="roll-back-app-mmd" />

## <a name="roll-back-an-app-to-a-previous-version"></a><span data-ttu-id="b70da-133">이전 버전으로 앱 롤백</span><span class="sxs-lookup"><span data-stu-id="b70da-133">Roll back an app to a previous version</span></span>

<span data-ttu-id="b70da-134">새 버전의 앱을 배포할 때 오류가 발견되면 이전 버전으로 롤백할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b70da-134">If there's an error found when a new version of an app is deployed, you can roll back to a previous version.</span></span> <span data-ttu-id="b70da-135">여기에 설명된 프로세스는 **유형이 MSI** 업무용 앱 또는 Windows 앱(Win **32)** - 미리 보기로 Windows 앱에 대한 프로세스입니다.</span><span class="sxs-lookup"><span data-stu-id="b70da-135">The process outlined here is for apps where type is listed as **Windows MSI line-of-business app** or **Windows app (Win 32) - preview**</span></span>

<span data-ttu-id="b70da-136">**업무용 앱을 이전 버전으로 롤백**</span><span class="sxs-lookup"><span data-stu-id="b70da-136">**To roll back a line-of-business app to a previous version**</span></span>

1. <span data-ttu-id="b70da-137">관리자 포털 [Microsoft Managed Desktop 로그인합니다.](https://aka.ms/mmdportal)</span><span class="sxs-lookup"><span data-stu-id="b70da-137">Sign in to [Microsoft Managed Desktop Admin portal](https://aka.ms/mmdportal).</span></span>
2. <span data-ttu-id="b70da-138">**인벤토리에서** 앱을 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="b70da-138">Under **Inventory**, select **Apps**.</span></span>  
3. <span data-ttu-id="b70da-139">롤백해야 하는 앱을 선택하고 편집 을 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="b70da-139">Select the app you need to roll back, and then select **Edit**.</span></span>
4. <span data-ttu-id="b70da-140">**관리에서** 속성을 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="b70da-140">Under **Manage**, select **Properties**.</span></span> 
    - <span data-ttu-id="b70da-141">MSI **Windows** 앱 앱의 경우 앱 정보를 선택하고 앱 버전 무시에서 **예를** **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="b70da-141">For **Windows MSI line-of-business app** apps, select **App information**, and then under **Ignore app version**, select **Yes**.</span></span>
    - <span data-ttu-id="b70da-142">앱 **Windows (Win 32) -** 앱 미리 보기, 앱 **정보,** 검색 규칙, 추가를 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="b70da-142">For **Windows app (Win 32) - preview** apps, select **App information**, select **Detection rules**, and then select **Add**.</span></span> 
    <span data-ttu-id="b70da-143">MSI 규칙이 있는 경우 **MSI** 제품 버전 확인이 아니요로 설정되어 있는지 **확인해야 합니다.**</span><span class="sxs-lookup"><span data-stu-id="b70da-143">If there is an MSI rule, verify that **MSI product version check** is set to **No**.</span></span>
5. <span data-ttu-id="b70da-144">[업로드 이전](../get-started/deploy-apps.md) 버전의 앱 원본 파일을 관리 포털에 Microsoft Managed Desktop 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b70da-144">[Upload a previous version of the app source file](../get-started/deploy-apps.md) to Microsoft Managed Desktop Admin portal.</span></span>  

