---
title: 관리 센터에서 추가 기능 관리
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_NonTOC
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 737e8c86-be63-44d7-bf02-492fa7cd9c3f
description: 중앙 집중식 추가 기능을 사용하여 조직의 사용자 및 그룹에 추가 기능을 배포하는 방법을 학습합니다.
ms.openlocfilehash: 0750b6c9b91bc5cbd67d227fadb304bfc6cf7537
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/19/2021
ms.locfileid: "50915401"
---
# <a name="manage-add-ins-in-the-admin-center"></a><span data-ttu-id="164e5-103">관리 센터에서 추가 기능 관리</span><span class="sxs-lookup"><span data-stu-id="164e5-103">Manage add-ins in the admin center</span></span>

::: moniker range="o365-21vianet"

> [!NOTE]
> <span data-ttu-id="164e5-104">관리 센터가 변경되고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="164e5-104">The admin center is changing.</span></span> <span data-ttu-id="164e5-105">사용자의 환경이 여기에 설명된 세부 정보와 맞지 않는 경우에는 [새 Microsoft 365 관리 센터 정보](../microsoft-365-admin-center-preview.md?preserve-view=true&view=o365-21vianet)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="164e5-105">If your experience doesn't match the details presented here, see [About the new Microsoft 365 admin center](../microsoft-365-admin-center-preview.md?preserve-view=true&view=o365-21vianet).</span></span>

::: moniker-end

<span data-ttu-id="164e5-106">Office 추가 기능을 사용하면 문서를 개인 설정하고 웹의 정보에 액세스하는 방법을 간소화할 수 있습니다(Office 추가 기능 사용 시작 [참조).](https://support.microsoft.com/office/82e665c4-6700-4b56-a3f3-ef5441996862)</span><span class="sxs-lookup"><span data-stu-id="164e5-106">Office add-ins help you personalize your documents and streamline the way you access information on the web (see [Start using your Office add-in](https://support.microsoft.com/office/82e665c4-6700-4b56-a3f3-ef5441996862)).</span></span> 

<span data-ttu-id="164e5-107">관리자가 조직의 사용자에 대해 추가 기능을 배포한 후 추가 기능을 해제하거나 설정하고, 추가 기능 액세스 권한을 편집, 삭제 및 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="164e5-107">After an admin deploys add-ins for users in an organization, the admin can turn add-ins off or on, edit, delete, and manage access to the add-ins.</span></span>

<span data-ttu-id="164e5-108">관리 센터에서 추가 기능을 설치하는 데 대한 자세한 내용은 관리 센터에서 추가 기능 [배포를 참조하세요.](./manage-deployment-of-add-ins.md)</span><span class="sxs-lookup"><span data-stu-id="164e5-108">For more information about installing add-ins from the admin center, see [Deploy add-ins in the admin center](./manage-deployment-of-add-ins.md).</span></span>
  
## <a name="add-in-states"></a><span data-ttu-id="164e5-109">추가 기능 상태</span><span class="sxs-lookup"><span data-stu-id="164e5-109">Add-in states</span></span>

<span data-ttu-id="164e5-110">추가 기능의 상태는 **On** 또는 **Off 상태일 수** 있습니다.</span><span class="sxs-lookup"><span data-stu-id="164e5-110">An add-in can be in either the **On** or **Off** state.</span></span>
  
|<span data-ttu-id="164e5-111">**상태**</span><span class="sxs-lookup"><span data-stu-id="164e5-111">**State**</span></span>|<span data-ttu-id="164e5-112">**상태가 적용되는 경우**</span><span class="sxs-lookup"><span data-stu-id="164e5-112">**How the state occurs**</span></span>|<span data-ttu-id="164e5-113">**영향**</span><span class="sxs-lookup"><span data-stu-id="164e5-113">**Impact**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="164e5-114">**활성**</span><span class="sxs-lookup"><span data-stu-id="164e5-114">**Active**</span></span>  <br/> |<span data-ttu-id="164e5-115">관리자가 추가 기능을 업로드하고 사용자 또는 그룹에 할당했습니다.</span><span class="sxs-lookup"><span data-stu-id="164e5-115">Admin uploaded the add-in and assigned it to users or groups.</span></span>  <br/> |<span data-ttu-id="164e5-116">추가 기능에 할당된 사용자 및 그룹은 관련 클라이언트에서 추가 기능을 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="164e5-116">Users and groups assigned to the add-in see it in the relevant clients.</span></span>  <br/> |
|<span data-ttu-id="164e5-117">**해제됨**</span><span class="sxs-lookup"><span data-stu-id="164e5-117">**Turned off**</span></span>  <br/> |<span data-ttu-id="164e5-118">관리자가 추가 기능을 해제했습니다.</span><span class="sxs-lookup"><span data-stu-id="164e5-118">Admin turned off the add-in.</span></span>  <br/> |<span data-ttu-id="164e5-119">추가 기능에 할당된 사용자 및 그룹이 더 이상 추가 기능에 액세스할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="164e5-119">Users and groups assigned to the add-in no longer have access to it.</span></span>  <br/> <span data-ttu-id="164e5-120">추가 기능 상태가 활성으로 변경되면 사용자 및 그룹이 추가 기능에 다시 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="164e5-120">If the add-in state is changed to Active, the users and groups will have access to it again.</span></span>  <br/> |
|<span data-ttu-id="164e5-121">**삭제됨**</span><span class="sxs-lookup"><span data-stu-id="164e5-121">**Deleted**</span></span>  <br/> |<span data-ttu-id="164e5-122">관리자가 추가 기능을 삭제했습니다.</span><span class="sxs-lookup"><span data-stu-id="164e5-122">Admin deleted the add-in.</span></span>  <br/> |<span data-ttu-id="164e5-123">추가 기능에 할당된 사용자 및 그룹이 더 이상 추가 기능에 액세스할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="164e5-123">Users and groups assigned the add-in no longer have access to it.</span></span>  <br/> |
   
<span data-ttu-id="164e5-124">더 이상 추가 기능을 사용하는 사용자가 없는 경우 추가 기능을 삭제하는 것이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="164e5-124">Consider deleting an add-in if no one is using it anymore.</span></span> <span data-ttu-id="164e5-125">예를 들어 추가 기능을 해제하면 특정 연도의 특정 시간 동안에만 추가 기능을 사용하는 것이 나을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="164e5-125">For example, turning off an add-in might make sense if an add-in is used only during specific times of the year.</span></span>

## <a name="delete-an-add-in"></a><span data-ttu-id="164e5-126">추가 기능 삭제</span><span class="sxs-lookup"><span data-stu-id="164e5-126">Delete an add-in</span></span>

<span data-ttu-id="164e5-127">배포된 추가 기능을 삭제할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="164e5-127">You can also delete an add-in that was deployed.</span></span>

1. <span data-ttu-id="164e5-128">관리 센터에서 설정 서비스 및 &  >  **페이지로 이동합니다.**</span><span class="sxs-lookup"><span data-stu-id="164e5-128">In the admin center, go to the **Settings** > **Services & add-ins** page.</span></span>

     > [!NOTE]
    > <span data-ttu-id="164e5-129">관리 센터가 통합 앱으로 배포 환경으로 업데이트되고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="164e5-129">The admin center is getting updated to deployment experience with Integrated Apps .</span></span> <span data-ttu-id="164e5-130">위의 단계가 없는 경우 설정 통합 앱으로 이동하여 중앙 집중식 배포  >  **섹션으로 이동합니다.**</span><span class="sxs-lookup"><span data-stu-id="164e5-130">If you don't see the above steps, go to Centralized Deployment section by going to **Settings** > **Integrated apps**.</span></span> <span data-ttu-id="164e5-131">On the top of the **Integrated apps** page, choose **Add-ins**.</span><span class="sxs-lookup"><span data-stu-id="164e5-131">On the top of the **Integrated apps** page, choose **Add-ins**.</span></span>

2. <span data-ttu-id="164e5-132">배포된 추가 기능을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="164e5-132">Select the deployed add-in.</span></span>

3. <span data-ttu-id="164e5-133">추가 기능 **삭제 를 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="164e5-133">Click on **Delete Add-In**.</span></span> <span data-ttu-id="164e5-134">오른쪽 아래 모서리에 있는 추가 기능 단추를 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="164e5-134">Remove the Add-in button on the bottom right corner.</span></span>

4. <span data-ttu-id="164e5-135">선택의 유효성을 검사하고 추가 기능 **제거 를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="164e5-135">Validate your selections, and choose **Remove add-in**.</span></span>

## <a name="edit-add-in-access"></a><span data-ttu-id="164e5-136">추가 기능 액세스 편집</span><span class="sxs-lookup"><span data-stu-id="164e5-136">Edit add-in access</span></span>

<span data-ttu-id="164e5-137">배포 후 관리자는 추가 기능의 사용자 액세스를 관리할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="164e5-137">Post deployment, admins can also manage user access to add-ins.</span></span>

1. <span data-ttu-id="164e5-138">관리 센터에서 설정 서비스 및 &  >  **페이지로 이동합니다.**</span><span class="sxs-lookup"><span data-stu-id="164e5-138">In the admin center, go to the **Settings** > **Services & add-ins** page.</span></span>

     > [!NOTE]
    > <span data-ttu-id="164e5-139">관리 센터가 통합 앱으로 배포 환경으로 업데이트되고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="164e5-139">The admin center is getting updated to deployment experience with Integrated Apps .</span></span> <span data-ttu-id="164e5-140">위의 단계가 없는 경우 설정 통합 앱으로 이동하여 중앙 집중식 배포  >  **섹션으로 이동합니다.**</span><span class="sxs-lookup"><span data-stu-id="164e5-140">If you don't see the above steps, go to Centralized Deployment section by going to **Settings** > **Integrated apps**.</span></span> <span data-ttu-id="164e5-141">On the top of the **Integrated apps** page, choose **Add-ins**.</span><span class="sxs-lookup"><span data-stu-id="164e5-141">On the top of the **Integrated apps** page, choose **Add-ins**.</span></span>

2. <span data-ttu-id="164e5-142">배포된 추가 기능을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="164e5-142">Select the deployed add-in.</span></span>

3. <span data-ttu-id="164e5-143">액세스 권한이 **있는** **사용자 아래에서 편집을 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="164e5-143">Click on **Edit** under **Who has Access**.</span></span>

4. <span data-ttu-id="164e5-144">변경 내용을 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="164e5-144">Save the changes.</span></span>

## <a name="prevent-add-in-downloads-by-turning-off-the-office-store-across-all-clients-except-outlook"></a><span data-ttu-id="164e5-145">모든 클라이언트에서 Office 스토어를 해제하여 추가 기능 다운로드 방지(Outlook 제외)</span><span class="sxs-lookup"><span data-stu-id="164e5-145">Prevent add-in downloads by turning off the Office Store across all clients (Except Outlook)</span></span>

> [!NOTE]
> <span data-ttu-id="164e5-146">Outlook 추가 기능 설치는 다른 프로세스로 [관리됩니다.](/exchange/clients-and-mobile-in-exchange-online/add-ins-for-outlook/specify-who-can-install-and-manage-add-ins)</span><span class="sxs-lookup"><span data-stu-id="164e5-146">Outlook add-in installation is managed by a [different process](/exchange/clients-and-mobile-in-exchange-online/add-ins-for-outlook/specify-who-can-install-and-manage-add-ins).</span></span>

<span data-ttu-id="164e5-147">조직에서는 Office 스토어에서 새 Office 추가 기능을 다운로드하지 못하게 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="164e5-147">As an organization you may wish to prevent the download of new Office add-ins from the Office Store.</span></span> <span data-ttu-id="164e5-148">중앙 집중식 배포와 함께 사용하면 조직에서 승인한 추가 기능만 조직 내의 사용자에게 배포할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="164e5-148">This can be used in conjunction with Centralized Deployment to ensure that only organization-approved add-ins are deployed to users within your organization.</span></span>
  
<span data-ttu-id="164e5-149">**추가 기능 취득을 끄기 위해**</span><span class="sxs-lookup"><span data-stu-id="164e5-149">**To turn off add-in acquisition**</span></span>
  
1. <span data-ttu-id="164e5-150">관리 센터 미리 보기에서 **설정** \> [서비스 &amp; 추가 기능](https://go.microsoft.com/fwlink/p/?linkid=2053743) 페이지로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="164e5-150">In the admin center, go to the **Settings** \> [Services &amp; add-ins](https://go.microsoft.com/fwlink/p/?linkid=2053743) page.</span></span>

     > [!NOTE]
    > <span data-ttu-id="164e5-151">관리 센터가 통합 앱으로 배포 환경으로 업데이트되고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="164e5-151">The admin center is getting updated to deployment experience with Integrated Apps .</span></span> <span data-ttu-id="164e5-152">위의 단계가 없는 경우 설정 통합 앱으로 이동하여 중앙 집중식 배포  >  **섹션으로 이동합니다.**</span><span class="sxs-lookup"><span data-stu-id="164e5-152">If you don't see the above steps, go to Centralized Deployment section by going to **Settings** > **Integrated apps**.</span></span> <span data-ttu-id="164e5-153">On the top of the **Integrated apps** page, choose **Add-ins**.</span><span class="sxs-lookup"><span data-stu-id="164e5-153">On the top of the **Integrated apps** page, choose **Add-ins**.</span></span>
    
3. <span data-ttu-id="164e5-154">사용자 **소유 앱 및 서비스를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="164e5-154">Select **User owned apps and services**.</span></span>
    
4. <span data-ttu-id="164e5-155">사용자가 Office 스토어에 액세스할 수 있도록 하는 옵션을 선택 취소합니다.</span><span class="sxs-lookup"><span data-stu-id="164e5-155">Clear the option to let users access the Office store.</span></span>

<span data-ttu-id="164e5-156">이렇게 하면 모든 사용자가 스토어에서 다음 추가 기능을 다운로드할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="164e5-156">This will prevent all users from acquiring the following add-ins from the store.</span></span>
  
- <span data-ttu-id="164e5-157">다음의 Word, Excel 및 PowerPoint 2016용 추가 기능</span><span class="sxs-lookup"><span data-stu-id="164e5-157">Add-ins for Word, Excel, and PowerPoint 2016 from:</span></span>
    
  - <span data-ttu-id="164e5-158">Windows</span><span class="sxs-lookup"><span data-stu-id="164e5-158">Windows</span></span>
    
  - <span data-ttu-id="164e5-159">Mac</span><span class="sxs-lookup"><span data-stu-id="164e5-159">Mac</span></span>
    
  - <span data-ttu-id="164e5-160">사무실</span><span class="sxs-lookup"><span data-stu-id="164e5-160">Office</span></span>
    
    
- <span data-ttu-id="164e5-161">**AppSource** 내에서 시작하여 취득</span><span class="sxs-lookup"><span data-stu-id="164e5-161">Acquisitions starting within **AppSource**</span></span>
    
- <span data-ttu-id="164e5-162">Microsoft 365 내의 추가 기능</span><span class="sxs-lookup"><span data-stu-id="164e5-162">Add-ins within Microsoft 365</span></span>
    
<span data-ttu-id="164e5-163">스토어에 액세스하는 사용자에게는 Office 스토어 추가 기능의 개별 취득을 방지하도록 **Microsoft 365가 구성됩니다.**</span><span class="sxs-lookup"><span data-stu-id="164e5-163">A user who tries to access the store will see the following message: **Sorry, Microsoft 365 has been configured to prevent individual acquisition of Office Store add-ins.**</span></span>
  
<span data-ttu-id="164e5-164">Office 스토어 끄기 지원은 다음 버전에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="164e5-164">Support for turning off the Office Store is available in the following versions:</span></span>
  
- <span data-ttu-id="164e5-165">Windows: 16.0.9001 - 현재 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="164e5-165">Windows: 16.0.9001 - Currently available.</span></span>
    
- <span data-ttu-id="164e5-166">Mac: 16.10.18011401 - 현재 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="164e5-166">Mac: 16.10.18011401 - Currently available.</span></span>
    
- <span data-ttu-id="164e5-167">iOS: 2.9.18010804 - 현재 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="164e5-167">iOS: 2.9.18010804 - Currently available.</span></span>
    
- <span data-ttu-id="164e5-168">웹 - 현재 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="164e5-168">The web - Currently available.</span></span>
    
<span data-ttu-id="164e5-169">이렇게 해서 관리자가 중앙 집중식 배포를 사용하여 Office 스토어에서 추가 기능을 할당할 수 있는 것은 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="164e5-169">This does not prevent an administrator from using Centralized Deployment to assign an add-in from the Office Store.</span></span>
  
<span data-ttu-id="164e5-170">사용자가 Microsoft 계정으로 로그인하지 못하도록 조직 계정만 사용하도록 로그온을 제한할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="164e5-170">To prevent a user from signing in with a Microsoft account, you can restrict logon to use only the organizational account.</span></span> <span data-ttu-id="164e5-171">자세한 내용은 [Office 2016의 ID, 인증](/DeployOffice/security/identity-authentication-and-authorization-in-office)및 권한 부여를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="164e5-171">For more information, see [Identity, authentication, and authorization in Office 2016](/DeployOffice/security/identity-authentication-and-authorization-in-office).</span></span>  

> [!NOTE]
> <span data-ttu-id="164e5-172">사용자가 Office 스토어에 액세스하지 못하게 하면 테스트용 Office 추가 기능을 [테스트용으로 로드할 수 없습니다.](/office/dev/add-ins/testing/create-a-network-shared-folder-catalog-for-task-pane-and-content-add-ins)</span><span class="sxs-lookup"><span data-stu-id="164e5-172">Preventing users from accessing the office store will also prevent them from [Sideloading Office Add-ins for testing](/office/dev/add-ins/testing/create-a-network-shared-folder-catalog-for-task-pane-and-content-add-ins).</span></span>

## <a name="more-about-the-end-user-experience-with-add-ins"></a><span data-ttu-id="164e5-173">추가 기능을 사용할 수 있는 최종 사용자 경험에 대한 자세한 내용은</span><span class="sxs-lookup"><span data-stu-id="164e5-173">More about the end user experience with add-ins</span></span>

<span data-ttu-id="164e5-174">추가 기능을 배포한 후 최종 사용자는 Office 응용 프로그램에서 추가 기능을 사용할 수 있습니다(Office 추가 기능 사용 시작 [참조).](https://support.microsoft.com/office/82e665c4-6700-4b56-a3f3-ef5441996862)</span><span class="sxs-lookup"><span data-stu-id="164e5-174">After you deploy an add-in, your end users can start using it in their Office applications (see [Start using your Office Add-in](https://support.microsoft.com/office/82e665c4-6700-4b56-a3f3-ef5441996862)).</span></span> <span data-ttu-id="164e5-175">추가 기능은 추가 기능에서 지원하는 모든 플랫폼에 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="164e5-175">The add-in appears on all platforms that the add-in supports.</span></span>
  
<span data-ttu-id="164e5-p110">추가 기능이 추가 기능 명령을 지원하는 경우 명령은 Office 리본에 나타납니다. 다음 예에서는 **인용 검색** 명령이 **인용** 추가 기능에 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="164e5-p110">If the add-in supports add-in commands, the commands appear on the Office ribbon. In the following example, the command **Search Citation** appears for the **Citations** add-in.</span></span> 

![검색 인설이 있는 Office 리본 메뉴](../../media/553b0c0a-65e9-4746-b3b0-8c1b81715a86.png)
  
<span data-ttu-id="164e5-179">배포된 추가 기능에서 추가 기능 명령을 지원하지 않는 경우 또는 배포된 모든 추가 기능을 보거나 내 추가 기능을 통해 볼 **수 있습니다.**</span><span class="sxs-lookup"><span data-stu-id="164e5-179">If the deployed add-in doesn't support add-in commands or if you want to view all deployed add-ins, you can view them via **My Add-ins**.</span></span> 
  
### <a name="in-word-2016-excel-2016-or-powerpoint-2016"></a><span data-ttu-id="164e5-180">Word 2016, Excel 2016 또는 PowerPoint 2016의 경우</span><span class="sxs-lookup"><span data-stu-id="164e5-180">In Word 2016, Excel 2016, or PowerPoint 2016</span></span>

1. <span data-ttu-id="164e5-181">내 **추가 \> 기능 삽입을 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="164e5-181">Select **Insert \> My Add-ins**.</span></span> 
    
2. <span data-ttu-id="164e5-182">Office 추가 기능 창에서 **관리자가 관리함** 탭을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="164e5-182">Select the **Admin Managed** tab in the Office Add-ins window.</span></span> 
    
3. <span data-ttu-id="164e5-183">이전에 배포한 추가 기능을 두 번 클릭합니다(이 예에서는 **인용** ).</span><span class="sxs-lookup"><span data-stu-id="164e5-183">Double-click the add-in you deployed earlier (in this example, **Citations** ).</span></span> <br/><span data-ttu-id="164e5-184">![Office 추가 기능 페이지의 관리 탭](../../media/fd36ba81-9882-40f0-9fce-74f991aa97d5.png)</span><span class="sxs-lookup"><span data-stu-id="164e5-184">![Admin Managed tab of the Office Add-ins page](../../media/fd36ba81-9882-40f0-9fce-74f991aa97d5.png)</span></span>
  
### <a name="in-outlook"></a><span data-ttu-id="164e5-185">Outlook의 경우</span><span class="sxs-lookup"><span data-stu-id="164e5-185">In Outlook</span></span>

1. <span data-ttu-id="164e5-186">홈 **리본에서** 추가 기능 **사용 을 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="164e5-186">On the **Home** ribbon, select **Get Add-ins**.</span></span><br/><span data-ttu-id="164e5-187">![Outlook의 스토어 단추](../../media/getaddinsicon.png)</span><span class="sxs-lookup"><span data-stu-id="164e5-187">![Store button in Outlook](../../media/getaddinsicon.png)</span></span>
  
2. <span data-ttu-id="164e5-188">왼쪽 **내비게이트에서** 관리자 관리 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="164e5-188">Select **Admin-managed** in the left nav.</span></span> 

## <a name="learn-more"></a><span data-ttu-id="164e5-189">자세한 정보</span><span class="sxs-lookup"><span data-stu-id="164e5-189">Learn more</span></span>

[<span data-ttu-id="164e5-190">관리 센터에서 추가 기능 배포</span><span class="sxs-lookup"><span data-stu-id="164e5-190">Deploy add-ins in the admin center</span></span>](./manage-deployment-of-add-ins.md)

<span data-ttu-id="164e5-191">[Office 추가 기능](/office/dev/add-ins/overview/office-add-ins)을 만들고 빌드하는 방법에 대해 자세히 알아보세요.</span><span class="sxs-lookup"><span data-stu-id="164e5-191">Learn more about creating and building [Office Add-ins](/office/dev/add-ins/overview/office-add-ins).</span></span>
  
<span data-ttu-id="164e5-192">[중앙 집중식 배포 PowerShell cmdlet을](../../enterprise/use-the-centralized-deployment-powershell-cmdlets-to-manage-add-ins.md)사용하여 추가 기능을 관리합니다.</span><span class="sxs-lookup"><span data-stu-id="164e5-192">[Use Centralized Deployment PowerShell cmdlets to manage add-ins](../../enterprise/use-the-centralized-deployment-powershell-cmdlets-to-manage-add-ins.md).</span></span>
  
[<span data-ttu-id="164e5-193">문제 해결: 사용자가 추가 기능을 볼 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="164e5-193">Troubleshoot: User not seeing add-ins</span></span>](/office365/troubleshoot/access-management/user-not-seeing-add-ins)

[<span data-ttu-id="164e5-194">Microsoft Store에서 미성년자 및 추가 기능 다운로드</span><span class="sxs-lookup"><span data-stu-id="164e5-194">Minors and acquiring add-ins from the Microsoft Store</span></span>](./minors-and-acquiring-addins-from-the-store.md)