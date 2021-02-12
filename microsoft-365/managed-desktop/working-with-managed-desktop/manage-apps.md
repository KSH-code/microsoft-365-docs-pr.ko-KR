---
title: Microsoft Managed Desktop에서 앱 관리
description: Microsoft Managed Desktop 장치에 배포된 업무용 앱을 업데이트하는 방법에 대한 정보
keywords: Microsoft Managed Desktop, Microsoft 365, 서비스, 문서
ms.service: m365-md
author: jaimeo
f1.keywords:
- NOCSH
ms.author: jaimeo
ms.localizationpriority: normal
ms.date: 01/18/2019
ms.collection: M365-modern-desktop
ms.openlocfilehash: 1a6b91ab5b4523f4b980dab0c25af41a9d614189
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/29/2020
ms.locfileid: "41600685"
---
# <a name="manage-line-of-business-apps-in-microsoft-managed-desktop"></a><span data-ttu-id="f7c23-104">Microsoft Managed Desktop에서 업무용 앱 관리</span><span class="sxs-lookup"><span data-stu-id="f7c23-104">Manage line-of-business apps in Microsoft Managed Desktop</span></span>

<!--Application management -->

<span data-ttu-id="f7c23-105">Microsoft Managed Desktop에 온보드하고 Microsoft Managed Desktop 디바이스에 배포한 앱의 앱 업데이트를 관리하는 몇 가지 방법이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f7c23-105">There are a couple of ways to manage app updates for apps that you've onboarded to Microsoft Managed Desktop and deployed to your Microsoft Managed Desktop devices.</span></span> <span data-ttu-id="f7c23-106">Microsoft Managed Desktop 포털 또는 Intune에서 앱을 업데이트할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f7c23-106">You can make app updates in Microsoft Managed Desktop portal, or Intune.</span></span> 

<span id="update-app-mmd" />

## <a name="update-line-of-business-apps-in-microsoft-managed-desktop"></a><span data-ttu-id="f7c23-107">Microsoft Managed Desktop에서 업무 앱 업데이트</span><span class="sxs-lookup"><span data-stu-id="f7c23-107">Update line-of-business apps in Microsoft Managed Desktop</span></span>

<span data-ttu-id="f7c23-108">**Microsoft Managed Desktop 포털에서 업무용 앱을 업데이트합니다.**</span><span class="sxs-lookup"><span data-stu-id="f7c23-108">**To update your line-of-business apps in Microsoft Managed Desktop portal**</span></span>
1. <span data-ttu-id="f7c23-109">[Microsoft Managed Desktop 관리 포털에 로그인합니다.](https://aka.ms/mmdportal)</span><span class="sxs-lookup"><span data-stu-id="f7c23-109">Sign in to [Microsoft Managed Desktop Admin portal](https://aka.ms/mmdportal).</span></span>
2. <span data-ttu-id="f7c23-110">**인벤토리에서** 앱을 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="f7c23-110">Under **Inventory**, select **Apps**.</span></span>  
3. <span data-ttu-id="f7c23-111">업데이트할 앱을 선택하고 편집을 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="f7c23-111">Select the app you want to updates, and then select **Edit**.</span></span>
4. <span data-ttu-id="f7c23-112">**관리에서** 속성을 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="f7c23-112">Under **Manage**, select **Properties**.</span></span> 
5. <span data-ttu-id="f7c23-113">앱 **패키지 파일을 클릭한** 다음 새 앱 패키지 파일을 업로드합니다.</span><span class="sxs-lookup"><span data-stu-id="f7c23-113">Click **App package file**, and then browse to upload a new app package file.</span></span>
6. <span data-ttu-id="f7c23-114">앱 **패키지 파일을 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="f7c23-114">Select **App package file**.</span></span>
7. <span data-ttu-id="f7c23-115">폴더 아이콘을 선택하고 업데이트된 앱 파일의 위치로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="f7c23-115">Select the folder icon and browse to the location of your updated app file.</span></span> <span data-ttu-id="f7c23-116">**열기** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="f7c23-116">Select **Open**.</span></span> <span data-ttu-id="f7c23-117">앱 정보가 패키지 정보로 업데이트됩니다.</span><span class="sxs-lookup"><span data-stu-id="f7c23-117">The app information is updated with the package information.</span></span>
8. <span data-ttu-id="f7c23-118">앱 **버전이** 업데이트된 앱 패키지를 반영하는지 확인</span><span class="sxs-lookup"><span data-stu-id="f7c23-118">Verify that **App version** reflects the updated app package.</span></span> 

<span data-ttu-id="f7c23-119">업데이트된 앱이 사용자의 장치에 배포됩니다.</span><span class="sxs-lookup"><span data-stu-id="f7c23-119">The updated app will be deployed to your user's devices.</span></span>

<span id="update-app-intune" />

## <a name="update-line-of-business-apps-in-intune"></a><span data-ttu-id="f7c23-120">Intune에서 업무용 앱 업데이트</span><span class="sxs-lookup"><span data-stu-id="f7c23-120">Update line-of-business apps in Intune</span></span>

<span data-ttu-id="f7c23-121">**Intune에서 업무용 앱을 업데이트하는 경우**</span><span class="sxs-lookup"><span data-stu-id="f7c23-121">**To update your line-of-business apps in Intune**</span></span>
1. <span data-ttu-id="f7c23-122">[Azure Portal에 로그인합니다.](https://portal.azure.com)</span><span class="sxs-lookup"><span data-stu-id="f7c23-122">Sign in to [Azure portal](https://portal.azure.com).</span></span>
2. <span data-ttu-id="f7c23-123">모든 **서비스**  >  **Intune을 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="f7c23-123">Select **All Services** > **Intune**.</span></span> <span data-ttu-id="f7c23-124">Intune은 모니터링 + 관리 **섹션에** 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f7c23-124">Intune is in the **Monitoring + Management** section.</span></span>
3. <span data-ttu-id="f7c23-125">앱에 **대해 > 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="f7c23-125">Select **Client Apps > Apps**.</span></span>
4. <span data-ttu-id="f7c23-126">앱 목록에서 앱을 찾아 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="f7c23-126">Find and select your app in the list of apps.</span></span>
5. <span data-ttu-id="f7c23-127">개요 **블레이드에서** 속성을 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="f7c23-127">In the **Overview** blade, select **Properties**.</span></span>
6. <span data-ttu-id="f7c23-128">앱 **패키지 파일을 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="f7c23-128">Select **App package file**.</span></span>
7. <span data-ttu-id="f7c23-129">폴더 아이콘을 선택하고 업데이트된 앱 파일의 위치로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="f7c23-129">Select the folder icon and browse to the location of your updated app file.</span></span> <span data-ttu-id="f7c23-130">**열기** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="f7c23-130">Select **Open**.</span></span> <span data-ttu-id="f7c23-131">앱 정보가 패키지 정보로 업데이트됩니다.</span><span class="sxs-lookup"><span data-stu-id="f7c23-131">The app information is updated with the package information.</span></span>
8. <span data-ttu-id="f7c23-132">앱 **버전이** 업데이트된 앱 패키지를 반영하는지 확인</span><span class="sxs-lookup"><span data-stu-id="f7c23-132">Verify that **App version** reflects the updated app package.</span></span>

<span id="roll-back-app-mmd" />

## <a name="roll-back-an-app-to-a-previous-version"></a><span data-ttu-id="f7c23-133">이전 버전으로 앱 롤백</span><span class="sxs-lookup"><span data-stu-id="f7c23-133">Roll back an app to a previous version</span></span>

<span data-ttu-id="f7c23-134">새 버전의 앱을 배포할 때 오류가 발견되면 이전 버전으로 롤백할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f7c23-134">If there's an error found when a new version of an app is deployed, you can roll back to a previous version.</span></span> <span data-ttu-id="f7c23-135">여기에 설명된 프로세스는 **유형이 Windows MSI(LINE-OF-BUSINESS)** 앱 또는 Windows 앱(Win **32)으로** 나열된 앱에 대한 것입니다. 미리 보기</span><span class="sxs-lookup"><span data-stu-id="f7c23-135">The process outlined here is for apps where type is listed as **Windows MSI line-of-business app** or **Windows app (Win 32) - preview**</span></span>

<span data-ttu-id="f7c23-136">**업무용 앱을 이전 버전으로 롤백**</span><span class="sxs-lookup"><span data-stu-id="f7c23-136">**To roll back a line-of-business app to a previous version**</span></span>

1. <span data-ttu-id="f7c23-137">[Microsoft Managed Desktop 관리 포털에 로그인합니다.](https://aka.ms/mmdportal)</span><span class="sxs-lookup"><span data-stu-id="f7c23-137">Sign in to [Microsoft Managed Desktop Admin portal](https://aka.ms/mmdportal).</span></span>
2. <span data-ttu-id="f7c23-138">**인벤토리에서** 앱을 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="f7c23-138">Under **Inventory**, select **Apps**.</span></span>  
3. <span data-ttu-id="f7c23-139">롤백해야 하는 앱을 선택하고 편집을 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="f7c23-139">Select the app you need to roll back, and then select **Edit**.</span></span>
4. <span data-ttu-id="f7c23-140">**관리에서** 속성을 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="f7c23-140">Under **Manage**, select **Properties**.</span></span> 
    - <span data-ttu-id="f7c23-141">**Windows MSI 업무** 앱 앱의 경우 앱 정보를 선택한 다음 앱 버전 무시에서 **예를** **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="f7c23-141">For **Windows MSI line-of-business app** apps, select **App information**, and then under **Ignore app version**, select **Yes**.</span></span>
    - <span data-ttu-id="f7c23-142">**Windows 앱(Win 32) -** 미리 보기 앱, 앱 **정보** 선택, 검색 규칙 **선택,** 추가를 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="f7c23-142">For **Windows app (Win 32) - preview** apps, select **App information**, select **Detection rules**, and then select **Add**.</span></span> 
    <span data-ttu-id="f7c23-143">MSI 규칙이 있는 경우 **MSI** 제품 버전 확인이 아니요로 설정되어 있는지 **확인해야 합니다.**</span><span class="sxs-lookup"><span data-stu-id="f7c23-143">If there is an MSI rule, verify that **MSI product version check** is set to **No**.</span></span>
5. <span data-ttu-id="f7c23-144">[이전 버전의](../get-started/deploy-apps.md) 앱 원본 파일을 Microsoft Managed Desktop Admin Portal에 업로드합니다.</span><span class="sxs-lookup"><span data-stu-id="f7c23-144">[Upload a previous version of the app source file](../get-started/deploy-apps.md) to Microsoft Managed Desktop Admin portal.</span></span>  

