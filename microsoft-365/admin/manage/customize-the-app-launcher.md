---
title: 앱 시작 관리자에 사용자 지정 타일 추가
f1.keywords:
- CSH
ms.author: twerner
author: twernermsft
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
- GEA150
ms.assetid: 1136115a-75af-4497-b693-640c4ce70bc6
description: '앱 시작 관리자에 사용자 지정 타일을 추가 하 여 전자 메일, 문서, 앱, SharePoint 사이트, 외부 사이트 및 기타 리소스에 대 한 빠른 연결을 만듭니다. '
ms.openlocfilehash: 7220f0be8ad6605b7ad6d30000fde6411948c996
ms.sourcegitcommit: 659adf65d88ee44f643c471e6202396f1ffb6576
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/17/2020
ms.locfileid: "44780136"
---
# <a name="add-custom-tiles-to-the-app-launcher"></a><span data-ttu-id="00de9-103">앱 시작 관리자에 사용자 지정 타일 추가</span><span class="sxs-lookup"><span data-stu-id="00de9-103">Add custom tiles to the app launcher</span></span>

::: moniker range="o365-21vianet"

> [!NOTE]
> <span data-ttu-id="00de9-104">관리 센터가 변경되고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="00de9-104">The admin center is changing.</span></span> <span data-ttu-id="00de9-105">사용자의 환경이 여기에 설명된 세부 정보와 맞지 않는 경우에는 [새 Microsoft 365 관리 센터 정보](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="00de9-105">If your experience doesn't match the details presented here, see [About the new Microsoft 365 admin center](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).</span></span>

::: moniker-end

<span data-ttu-id="00de9-106">Microsoft 365에서는 앱 시작 관리자를 사용 하 여 전자 메일, 일정, 문서 및 앱을 쉽고 빠르게 가져올 수 있습니다 ([자세한 정보](https://support.microsoft.com/office/79f12104-6fed-442f-96a0-eb089a3f476a)).</span><span class="sxs-lookup"><span data-stu-id="00de9-106">In Microsoft 365, you can quickly and easily get to your email, calendars, documents, and apps using the App launcher ([learn more](https://support.microsoft.com/office/79f12104-6fed-442f-96a0-eb089a3f476a)).</span></span> <span data-ttu-id="00de9-107">Microsoft 365에서 제공 하는 앱과 [SharePoint 스토어](https://support.microsoft.com/office/dd98e50e-d3db-4ecb-9bb7-82b189822d43) 또는 [Azure AD](https://msdn.microsoft.com/office/office365/howto/connect-your-app-to-o365-app-launcher)에서 추가한 사용자 지정 앱이 여기에 해당 됩니다.</span><span class="sxs-lookup"><span data-stu-id="00de9-107">These are apps you get with Microsoft 365 as well as custom apps that you add from the [SharePoint Store](https://support.microsoft.com/office/dd98e50e-d3db-4ecb-9bb7-82b189822d43) or [Azure AD](https://msdn.microsoft.com/office/office365/howto/connect-your-app-to-o365-app-launcher).</span></span>
  
<span data-ttu-id="00de9-108">SharePoint 사이트, 외부 사이트, 레거시 앱 등을 가리키는 앱 시작 관리자에 사용자 지정 타일을 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="00de9-108">You can add your own custom tiles to the app launcher that point to SharePoint sites, external sites, legacy apps, and more.</span></span> <span data-ttu-id="00de9-109">사용자 지정 타일은 앱 시작 관리자의 **모든** 앱 아래에 표시 되지만,이를 **홈** 앱에 고정 하 고 사용자가 동일한 작업을 수행 하도록 지시할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="00de9-109">The custom tile appears under the app launcher's **All** apps, but you can pin it to the **Home** apps and instruct your users to do the same.</span></span> <span data-ttu-id="00de9-110">이렇게 하면 작업을 수행 하기 위해 관련 사이트, 앱 및 리소스를 쉽게 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="00de9-110">This makes it easy to find the relevant sites, apps, and resources to do your job.</span></span> <span data-ttu-id="00de9-111">아래 예제에서는 조직의 SharePoint 인트라넷 사이트에 액세스 하는 데 "Contoso Portal" 이라는 사용자 지정 타일을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="00de9-111">In the below example, a custom tile called "Contoso Portal" is used to access an organization's SharePoint intranet site.</span></span> 
  
![앱 시작 관리자](../../media/7acc06cc-ac7a-4c6e-8ea7-81570a5bdbab.png)
  
## <a name="add-a-custom-tile-to-the-app-launcher"></a><span data-ttu-id="00de9-113">앱 시작 관리자에 사용자 지정 타일 추가</span><span class="sxs-lookup"><span data-stu-id="00de9-113">Add a custom tile to the app launcher</span></span>

1. <span data-ttu-id="00de9-114">관리 센터에서 **설정**  >  **조직 설정** 으로 이동 하 여 **조직 프로필** 탭을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="00de9-114">In the admin center, go to the **Settings** > **Org Settings** and choose **Organization profile** tab.</span></span>
    
2. <span data-ttu-id="00de9-115">**조직 프로필** 탭에서 **사용자 지정 앱 시작 관리자 타일**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="00de9-115">On the **Organization profile** tab, choose **Custom app launcher tiles**.</span></span>
  
3. <span data-ttu-id="00de9-116">**사용자 지정 타일 추가를**선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="00de9-116">Select **Add a custom tile**.</span></span> 
  
4. <span data-ttu-id="00de9-117">새 타일의 **타일 이름을** 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="00de9-117">Enter a **Tile name** for the new tile.</span></span> <span data-ttu-id="00de9-118">이름이 타일에 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="00de9-118">The name will appear in the tile.</span></span> 
    
5. <span data-ttu-id="00de9-119">타일에 대 한 **웹 사이트의 URL** 을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="00de9-119">Enter a **URL of website** for the tile.</span></span> <span data-ttu-id="00de9-120">앱 시작 관리자에서 타일을 선택할 때 사용자가 이동 하도록 할 위치입니다.</span><span class="sxs-lookup"><span data-stu-id="00de9-120">This is the location where you want your users to go when they select the tile on the app launcher.</span></span> <span data-ttu-id="00de9-121">URL에 HTTPS를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="00de9-121">Use HTTPS in the URL.</span></span><br/><span data-ttu-id="00de9-122">팁: SharePoint 사이트에 대 한 타일을 만드는 경우 해당 사이트로 이동 하 여 URL을 복사한 다음 여기에 붙여 넣습니다.</span><span class="sxs-lookup"><span data-stu-id="00de9-122">TIP: If you're creating a tile for a SharePoint site, navigate to that site, copy the URL, and paste it here.</span></span> <span data-ttu-id="00de9-123">기본 팀 사이트의 URL은 다음과 같습니다.`https://<company_name>.sharepoint.com`</span><span class="sxs-lookup"><span data-stu-id="00de9-123">The URL of your default team site looks like this: `https://<company_name>.sharepoint.com`</span></span> 
  
6. <span data-ttu-id="00de9-124">타일 **이미지의 URL** 을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="00de9-124">Enter an **URL of the image** for the tile.</span></span> <span data-ttu-id="00de9-125">이 이미지는 내 앱 페이지와 앱 시작 관리자에 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="00de9-125">The image appears on the My apps page and app launcher.</span></span><br/><span data-ttu-id="00de9-126">팁: 이미지는 60x60 픽셀 이어야 하며, 인증을 요구 하지 않고 조직의 모든 사용자가 사용할 수 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="00de9-126">TIP: The image should be 60x60 pixels and be available to everyone in your organization without requiring authentication.</span></span>

7. <span data-ttu-id="00de9-127">타일에 대 한 **설명을** 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="00de9-127">Enter a **Description** for the tile.</span></span> <span data-ttu-id="00de9-128">내 앱 페이지에서 타일을 선택 하 고 **앱 세부 정보**를 선택 하면이 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="00de9-128">You see this when you select the tile on the My apps page and select **App details**.</span></span> 
  
8. <span data-ttu-id="00de9-129">**변경 내용 저장** 을 선택 하 여 사용자 지정 타일을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="00de9-129">Select **Save changes** to create the custom tile.</span></span> 
    
<span data-ttu-id="00de9-130">이제 사용자 지정 타일이 사용자의 **모든** 탭에 있는 앱 시작 관리자에 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="00de9-130">Your custom tile now appears in the app launcher on the **All** tab for you and your users.</span></span> 
  
## <a name="promote-the-tile-to-app-launcher"></a><span data-ttu-id="00de9-131">앱 시작 관리자에 게 타일 승격</span><span class="sxs-lookup"><span data-stu-id="00de9-131">Promote the tile to App Launcher</span></span>

1. <span data-ttu-id="00de9-132">앱 시작 관리자 아이콘을 선택 하 고 **모든 앱**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="00de9-132">Select the app launcher icon and select the **All apps**.</span></span> 
    
2. <span data-ttu-id="00de9-133">앱에 대 한 새 타일을 찾은 다음 줄임표를 선택 하 고 **시작 관리자에 고정**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="00de9-133">Locate the new tile for your app, select the ellipsis, and choose **Pin to launcher**.</span></span>
  
    > [!NOTE]
    > <span data-ttu-id="00de9-134">이전 단계에서 만든 사용자 지정 타일이 보이지 않는 경우 Exchange Online 사서함이 사용자에 게 할당 되어 있고 사서함에 적어도 한 번 로그인 되어 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="00de9-134">If you don't see the custom tile created in the previous steps, make sure you have an Exchange Online mailbox assigned to you and you've signed into your mailbox at least once.</span></span> <span data-ttu-id="00de9-135">이러한 단계는 Microsoft 365의 사용자 지정 타일에 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="00de9-135">These steps are required for custom tiles in Microsoft 365.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="00de9-136">사용자와 사용자는이 단계를 수행 하 여 내 앱 페이지에서 앱 시작 관리자에 게 지정 된 타일을 승격 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="00de9-136">Both you and your users need to perform these steps to promote custom tiles from the My apps page to the app launcher.</span></span> 
  
## <a name="edit-or-delete-a-custom-tile"></a><span data-ttu-id="00de9-137">사용자 지정 타일 편집 또는 삭제</span><span class="sxs-lookup"><span data-stu-id="00de9-137">Edit or delete a custom tile</span></span>

1. <span data-ttu-id="00de9-138">관리 센터에서 **Settings**  >  **Org settings**  >  **조직 프로필** 설정 탭으로 이동 </a> 합니다.</span><span class="sxs-lookup"><span data-stu-id="00de9-138">In the admin center, go to the **Settings** > **Org Settings** > **Organization profile**</a> tab.</span></span>
    
2. <span data-ttu-id="00de9-139">**조직 프로필** 페이지에서 **조직의 사용자 지정 타일 추가**옆에 있는 **편집**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="00de9-139">On the **Organization profile** page, next to   **Add custom tiles for your organization**, select **Edit**.</span></span>

3. <span data-ttu-id="00de9-140">사용자 지정 타일의 **타일 이름**, **URL**, **설명**또는 **이미지 URL** 을 업데이트 합니다 ( [앱 시작 관리자에 사용자 지정 타일 추가](#add-a-custom-tile-to-the-app-launcher)참조).</span><span class="sxs-lookup"><span data-stu-id="00de9-140">Update the **Tile name**, **URL**, **Description**, or **Image URL** for the custom tile (see [Add a custom tile to the app launcher](#add-a-custom-tile-to-the-app-launcher)).</span></span>
    
4. <span data-ttu-id="00de9-141">**업데이트** \> **닫기를**선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="00de9-141">Select **Update** \> **Close**.</span></span> 
    
<span data-ttu-id="00de9-142">사용자 지정 타일을 삭제 하려면 **사용자 지정 타일** 창에서 타일을 선택 하 고 **타일**  >  **삭제**제거를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="00de9-142">To delete a custom tile, from the **Custom tiles** window, select the tile, select **Remove tile** > **Delete**.</span></span> 
  
## <a name="whats-next"></a><span data-ttu-id="00de9-143">다음 작업</span><span class="sxs-lookup"><span data-stu-id="00de9-143">What's next?</span></span>

<span data-ttu-id="00de9-144">앱 시작 관리자에 타일을 추가 하는 것 외에, 탐색 모음에 앱 시작 관리자 타일을 추가할 수 있습니다 ([자세한 정보](https://support.microsoft.com/office/eb34a21b-52fa-4fbf-a8d5-146132242985)).</span><span class="sxs-lookup"><span data-stu-id="00de9-144">In addition to adding tiles to the app launcher, you can add app launcher tiles to the navigation bar ([learn more](https://support.microsoft.com/office/eb34a21b-52fa-4fbf-a8d5-146132242985)).</span></span> <span data-ttu-id="00de9-145">조직의 브랜드에 맞게 Microsoft 365의 모양과 느낌을 사용자 지정 하려면 [microsoft 365 테마 사용자 지정](../setup/customize-your-organization-theme.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="00de9-145">To customize the look and feel of Microsoft 365 to match your organization's brand, see [Customize the Microsoft 365 theme](../setup/customize-your-organization-theme.md).</span></span>
  

