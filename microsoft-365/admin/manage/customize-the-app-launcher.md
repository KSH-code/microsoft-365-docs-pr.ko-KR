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
ms.custom:
- AdminSurgePortfolio
- okr_smb
search.appverid:
- BCS160
- MET150
- MOE150
- GEA150
ms.assetid: 1136115a-75af-4497-b693-640c4ce70bc6
description: '앱 시작 사이트에 사용자 지정 타일을 추가하여 전자 메일, 문서, 앱, SharePoint 사이트, 외부 사이트 및 기타 리소스에 대한 빠른 링크를 만들 수 있습니다. '
ms.openlocfilehash: 2bbcf64b807754aed199c441f6df028d5fe20a97
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/22/2021
ms.locfileid: "49926237"
---
# <a name="add-custom-tiles-to-the-app-launcher"></a><span data-ttu-id="63dde-103">앱 시작 관리자에 사용자 지정 타일 추가</span><span class="sxs-lookup"><span data-stu-id="63dde-103">Add custom tiles to the app launcher</span></span>

::: moniker range="o365-21vianet"

> [!NOTE]
> <span data-ttu-id="63dde-104">관리 센터가 변경되고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="63dde-104">The admin center is changing.</span></span> <span data-ttu-id="63dde-105">사용자의 환경이 여기에 설명된 세부 정보와 맞지 않는 경우에는 [새 Microsoft 365 관리 센터 정보](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="63dde-105">If your experience doesn't match the details presented here, see [About the new Microsoft 365 admin center](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).</span></span>

::: moniker-end

<span data-ttu-id="63dde-106">Microsoft 365에서 앱 시작 프로그램을 사용하여 전자 메일, 일정, 문서 및 앱에 쉽고 빠르게 접근할 수 있습니다(자세한[내용은).](https://support.microsoft.com/office/79f12104-6fed-442f-96a0-eb089a3f476a)</span><span class="sxs-lookup"><span data-stu-id="63dde-106">In Microsoft 365, you can quickly and easily get to your email, calendars, documents, and apps using the App launcher ([learn more](https://support.microsoft.com/office/79f12104-6fed-442f-96a0-eb089a3f476a)).</span></span> <span data-ttu-id="63dde-107">SharePoint 스토어 또는 Azure AD에서 추가한 사용자 지정 앱뿐만 [](https://support.microsoft.com/office/dd98e50e-d3db-4ecb-9bb7-82b189822d43) 아니라 Microsoft 365에서 다운로드하는 [앱입니다.](https://msdn.microsoft.com/office/office365/howto/connect-your-app-to-o365-app-launcher)</span><span class="sxs-lookup"><span data-stu-id="63dde-107">These are apps you get with Microsoft 365 as well as custom apps that you add from the [SharePoint Store](https://support.microsoft.com/office/dd98e50e-d3db-4ecb-9bb7-82b189822d43) or [Azure AD](https://msdn.microsoft.com/office/office365/howto/connect-your-app-to-o365-app-launcher).</span></span>
  
<span data-ttu-id="63dde-108">SharePoint 사이트, 외부 사이트, 레거시 앱 등을 가리키는 앱 시작 관리자에 사용자 지정 타일을 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="63dde-108">You can add your own custom tiles to the app launcher that point to SharePoint sites, external sites, legacy apps, and more.</span></span> <span data-ttu-id="63dde-109">사용자 지정 타일은 앱 시작 사용자의  모든 앱 아래에 나타나지만  홈 앱에 고정하고 사용자에게 동일한 작업을 하게 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="63dde-109">The custom tile appears under the app launcher's **All** apps, but you can pin it to the **Home** apps and instruct your users to do the same.</span></span> <span data-ttu-id="63dde-110">이렇게 하면 작업을 할 수 있는 관련 사이트, 앱 및 리소스를 쉽게 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="63dde-110">This makes it easy to find the relevant sites, apps, and resources to do your job.</span></span> <span data-ttu-id="63dde-111">아래 예제에서는 "Contoso Portal"이라는 사용자 지정 타일을 사용하여 조직의 SharePoint 인트라넷 사이트에 액세스합니다.</span><span class="sxs-lookup"><span data-stu-id="63dde-111">In the below example, a custom tile called "Contoso Portal" is used to access an organization's SharePoint intranet site.</span></span> 
  
![앱 시작 프로그램](../../media/7acc06cc-ac7a-4c6e-8ea7-81570a5bdbab.png)
  
## <a name="add-a-custom-tile-to-the-app-launcher"></a><span data-ttu-id="63dde-113">앱 시작러에 사용자 지정 타일 추가</span><span class="sxs-lookup"><span data-stu-id="63dde-113">Add a custom tile to the app launcher</span></span>

1. <span data-ttu-id="63dde-114">전역 관리자로 관리 센터에 로그인하고 설정 조직 설정으로 이동한 다음 조직 프로필  >   **탭을** 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="63dde-114">Sign in to the admin center as a Global Administrator, go to **Settings** > **Org Settings**, and choose the **Organization profile** tab.</span></span>
    
2. <span data-ttu-id="63dde-115">조직 프로필 **탭에서** 사용자 지정 **앱 시작 프로그램 타일을 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="63dde-115">On the **Organization profile** tab, choose **Custom app launcher tiles**.</span></span>
  
3. <span data-ttu-id="63dde-116">사용자 **지정 타일 추가를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="63dde-116">Select **Add a custom tile**.</span></span> 
  
4. <span data-ttu-id="63dde-117">새 **타일의 타일** 이름을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="63dde-117">Enter a **Tile name** for the new tile.</span></span> <span data-ttu-id="63dde-118">이름이 타일에 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="63dde-118">The name will appear in the tile.</span></span> 
    
5. <span data-ttu-id="63dde-119">타일에 **대한 웹 사이트의 URL을** 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="63dde-119">Enter a **URL of website** for the tile.</span></span> <span data-ttu-id="63dde-120">이 위치는 사용자가 앱 시작기에서 타일을 선택할 때 이동하게 하려는 위치입니다.</span><span class="sxs-lookup"><span data-stu-id="63dde-120">This is the location where you want your users to go when they select the tile on the app launcher.</span></span> <span data-ttu-id="63dde-121">URL에 HTTPS를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="63dde-121">Use HTTPS in the URL.</span></span><br/><span data-ttu-id="63dde-122">팁: SharePoint 사이트에 대한 타일을 만드는 경우 해당 사이트로 이동하여 URL을 복사한 다음 여기에 붙여넣습니다.</span><span class="sxs-lookup"><span data-stu-id="63dde-122">TIP: If you're creating a tile for a SharePoint site, navigate to that site, copy the URL, and paste it here.</span></span> <span data-ttu-id="63dde-123">기본 팀 사이트의 URL은 다음과 같습니다. `https://<company_name>.sharepoint.com`</span><span class="sxs-lookup"><span data-stu-id="63dde-123">The URL of your default team site looks like this: `https://<company_name>.sharepoint.com`</span></span> 
  
6. <span data-ttu-id="63dde-124">타일에 **대한 이미지 URL을** 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="63dde-124">Enter an **URL of the image** for the tile.</span></span> <span data-ttu-id="63dde-125">이미지가 내 앱 페이지 및 앱 시작에 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="63dde-125">The image appears on the My apps page and app launcher.</span></span><br/><span data-ttu-id="63dde-126">팁: 이미지는 60x60 픽셀로, 인증 없이 조직의 모든 사용자가 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="63dde-126">TIP: The image should be 60x60 pixels and be available to everyone in your organization without requiring authentication.</span></span>

7. <span data-ttu-id="63dde-127">타일에 **대한 설명을** 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="63dde-127">Enter a **Description** for the tile.</span></span> <span data-ttu-id="63dde-128">내 앱 페이지에서 타일을 선택하고 앱 세부 정보를 선택하면 **표시됩니다.**</span><span class="sxs-lookup"><span data-stu-id="63dde-128">You see this when you select the tile on the My apps page and select **App details**.</span></span> 
  
8. <span data-ttu-id="63dde-129">변경 **내용 저장을 선택하여** 사용자 지정 타일을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="63dde-129">Select **Save changes** to create the custom tile.</span></span> 
    
<span data-ttu-id="63dde-130">이제 사용자 지정 타일이 사용자와 사용자를  위한 모든 탭의 앱 시작러에 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="63dde-130">Your custom tile now appears in the app launcher on the **All** tab for you and your users.</span></span> 
  
## <a name="promote-the-tile-to-app-launcher"></a><span data-ttu-id="63dde-131">앱 시작러로 타일 승격</span><span class="sxs-lookup"><span data-stu-id="63dde-131">Promote the tile to App Launcher</span></span>

1. <span data-ttu-id="63dde-132">앱 시작 프로그램 아이콘을 선택하고 모든 **앱을 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="63dde-132">Select the app launcher icon and select the **All apps**.</span></span> 
    
2. <span data-ttu-id="63dde-133">앱에 대한 새 타일을 찾고, 타원을 선택하고, 시작사에 **고정을 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="63dde-133">Locate the new tile for your app, select the ellipsis, and choose **Pin to launcher**.</span></span>
  
    > [!NOTE]
    > <span data-ttu-id="63dde-134">이전 단계에서 만든 사용자 지정 타일이 없는 경우 Exchange Online 사서함이 할당되어 있으며 사서함에 한 번 이상 로그인해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="63dde-134">If you don't see the custom tile created in the previous steps, make sure you have an Exchange Online mailbox assigned to you and you've signed into your mailbox at least once.</span></span> <span data-ttu-id="63dde-135">이러한 단계는 Microsoft 365의 사용자 지정 타일에 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="63dde-135">These steps are required for custom tiles in Microsoft 365.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="63dde-136">사용자와 사용자 모두 내 앱 페이지에서 앱 시작 프로그램으로 사용자 지정 타일을 승격하기 위해 다음 단계를 수행해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="63dde-136">Both you and your users need to perform these steps to promote custom tiles from the My apps page to the app launcher.</span></span> 
  
## <a name="edit-or-delete-a-custom-tile"></a><span data-ttu-id="63dde-137">사용자 지정 타일 편집 또는 삭제</span><span class="sxs-lookup"><span data-stu-id="63dde-137">Edit or delete a custom tile</span></span>

1. <span data-ttu-id="63dde-138">관리 센터에서 설정 조직 프로필 탭으로  >    >   </a> 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="63dde-138">In the admin center, go to the **Settings** > **Org Settings** > **Organization profile**</a> tab.</span></span>
    
2. <span data-ttu-id="63dde-139">조직 프로필 **페이지에서** 조직의 사용자 지정 타일 추가 옆에 있는 **편집을** **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="63dde-139">On the **Organization profile** page, next to   **Add custom tiles for your organization**, select **Edit**.</span></span>

3. <span data-ttu-id="63dde-140">사용자 지정 타일의 **타일 이름,** **URL,** **설명** 또는 이미지 **URL을** [업데이트합니다(앱](#add-a-custom-tile-to-the-app-launcher)시작에 사용자 지정 타일 추가 참조).</span><span class="sxs-lookup"><span data-stu-id="63dde-140">Update the **Tile name**, **URL**, **Description**, or **Image URL** for the custom tile (see [Add a custom tile to the app launcher](#add-a-custom-tile-to-the-app-launcher)).</span></span>
    
4. <span data-ttu-id="63dde-141">Select **Update** \> **Close**.</span><span class="sxs-lookup"><span data-stu-id="63dde-141">Select **Update** \> **Close**.</span></span> 
    
<span data-ttu-id="63dde-142">사용자 지정 타일을 삭제하려면 사용자 지정 타일 **창에서** 타일을 선택하고 타일 **삭제를**  >  **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="63dde-142">To delete a custom tile, from the **Custom tiles** window, select the tile, select **Remove tile** > **Delete**.</span></span> 
  
## <a name="whats-next"></a><span data-ttu-id="63dde-143">다음 작업</span><span class="sxs-lookup"><span data-stu-id="63dde-143">What's next?</span></span>

<span data-ttu-id="63dde-144">앱 시작러에 타일을 추가하는 것 외에도 탐색 모음에 앱 시작 프로그램 타일을 추가할 수 있습니다(자세한[내용은).](https://support.microsoft.com/office/eb34a21b-52fa-4fbf-a8d5-146132242985)</span><span class="sxs-lookup"><span data-stu-id="63dde-144">In addition to adding tiles to the app launcher, you can add app launcher tiles to the navigation bar ([learn more](https://support.microsoft.com/office/eb34a21b-52fa-4fbf-a8d5-146132242985)).</span></span> <span data-ttu-id="63dde-145">조직의 브랜드에 맞게 Microsoft 365의 모양과 느낌을 사용자 지정하기 위해 [Microsoft 365](../setup/customize-your-organization-theme.md)테마 사용자 지정을 참조합니다.</span><span class="sxs-lookup"><span data-stu-id="63dde-145">To customize the look and feel of Microsoft 365 to match your organization's brand, see [Customize the Microsoft 365 theme](../setup/customize-your-organization-theme.md).</span></span>
  
