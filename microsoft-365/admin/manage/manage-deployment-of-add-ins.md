---
title: 관리 센터에서 추가 기능 배포
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
ms.custom:
- AdminSurgePortfolio
- okr_smb
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 737e8c86-be63-44d7-bf02-492fa7cd9c3f
description: 관리 센터에서 중앙 집중식 배포를 사용하여 조직의 사용자 및 그룹에 추가 기능을 배포하는 방법을 설명합니다.
ms.openlocfilehash: ef7237f20780cb67bc84561ad8617dd8da6f8b82
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/22/2021
ms.locfileid: "49926357"
---
# <a name="deploy-add-ins-in-the-admin-center"></a><span data-ttu-id="dfde1-103">관리 센터에서 추가 기능 배포</span><span class="sxs-lookup"><span data-stu-id="dfde1-103">Deploy add-ins in the admin center</span></span>

::: moniker range="o365-21vianet"

> [!NOTE]
> <span data-ttu-id="dfde1-104">관리 센터가 변경되고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dfde1-104">The admin center is changing.</span></span> <span data-ttu-id="dfde1-105">사용자의 환경이 여기에 설명된 세부 정보와 맞지 않는 경우에는 [새 Microsoft 365 관리 센터 정보](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="dfde1-105">If your experience doesn't match the details presented here, see [About the new Microsoft 365 admin center](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).</span></span>

::: moniker-end

<span data-ttu-id="dfde1-106">Office 추가 기능을 사용하면 문서를 개인 설정하고 웹에서 정보에 액세스하는 방법을 간소화할 수 있습니다([Office 추가 기능 사용 시작](https://support.microsoft.com/office/82e665c4-6700-4b56-a3f3-ef5441996862) 참조).</span><span class="sxs-lookup"><span data-stu-id="dfde1-106">Office add-ins help you personalize your documents and streamline the way you access information on the web (see [Start using your Office Add-in](https://support.microsoft.com/office/82e665c4-6700-4b56-a3f3-ef5441996862)).</span></span> <span data-ttu-id="dfde1-107">관리자는 Microsoft 365 관리 센터의 중앙 집중식 배포 기능을 사용하여 조직의 사용자를 위한 Office 추가 기능을 배포할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dfde1-107">As an admin, you can deploy Office add-ins for the users in your organization by using the Centralized Deployment feature in the Microsoft 365 admin center.</span></span> <span data-ttu-id="dfde1-108">중앙 집중식 배포는 대부분의 관리자가 조직 내에서 사용자 및 그룹에 추가 기능을 배포하는 데 권장되는 가장 다양한 기능입니다.</span><span class="sxs-lookup"><span data-stu-id="dfde1-108">Centralized Deployment is the recommended and most feature-rich way for most admins to deploy add-ins to users and groups within an organization.</span></span> 

<span data-ttu-id="dfde1-109">조직에서 중앙 집중식 배포를 지원할 수 있는지 확인하는 방법에 대한 자세한 내용은 추가 기능의 중앙 집중식 배포가 조직에 [적합한지 확인을 참조하십시오.](centralized-deployment-of-add-ins.md)</span><span class="sxs-lookup"><span data-stu-id="dfde1-109">For more information on how to determine if your organization can support Centralized Deployment, see [Determine if Centralized Deployment of add-ins works for your organization](centralized-deployment-of-add-ins.md).</span></span>

<span data-ttu-id="dfde1-110">배포 후 추가 기능 관리에 대한 자세한 내용은 관리 센터에서 추가 기능 [관리를 참조하세요.](manage-addins-in-the-admin-center.md)</span><span class="sxs-lookup"><span data-stu-id="dfde1-110">To learn more about managing add-ins after deployment, see [Manage add-ins in the admin center](manage-addins-in-the-admin-center.md)</span></span>
  
> [!NOTE]
>  <span data-ttu-id="dfde1-111">Word, Excel 및 PowerPoint의 경우 SharePoint 앱 카탈로그를 사용하여 Microsoft 365 및/또는 [SharePoint](https://dev.office.com/docs/add-ins/publish/publish-task-pane-and-content-add-ins-to-an-add-in-catalog) 추가 기능 지원에 연결되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="dfde1-111">For Word, Excel and PowerPoint use a [SharePoint App Catalog](https://dev.office.com/docs/add-ins/publish/publish-task-pane-and-content-add-ins-to-an-add-in-catalog) to deploy add-ins to users in an on-premises environment with no connection to Microsoft 365 and/or support for SharePoint add-ins required.</span></span> <span data-ttu-id="dfde1-112">Outlook의 경우 Exchange 제어판을 사용하여 Microsoft 365에 연결하지 않고도 Exchange 제어판을 사용하여프레미스 환경에 배포합니다.</span><span class="sxs-lookup"><span data-stu-id="dfde1-112">For Outlook use Exchange control panel to deploy in an on-premises environment without a connection to Microsoft 365.</span></span>
  
## <a name="recommended-approach-for-deploying-office-add-ins"></a><span data-ttu-id="dfde1-113">Office 추가 기능 배포에 권장되는 방법</span><span class="sxs-lookup"><span data-stu-id="dfde1-113">Recommended approach for deploying Office add-ins</span></span>

<span data-ttu-id="dfde1-114">단계적 접근 방식을 사용하여 추가 기능을 롤아웃하는 경우 다음을 사용하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="dfde1-114">To roll out add-ins by using a phased approach, we recommend the following:</span></span>
  
1. <span data-ttu-id="dfde1-115">소수의 비즈니스 이해 관계자와 IT 부서 구성원에게 추가 기능을 롤아웃합니다.</span><span class="sxs-lookup"><span data-stu-id="dfde1-115">Roll out the add-in to a small set of business stakeholders and members of the IT department.</span></span> <span data-ttu-id="dfde1-116">배포에 성공하면 2단계로 이동하십시오.</span><span class="sxs-lookup"><span data-stu-id="dfde1-116">If the deployment is successful, move to step 2.</span></span>
    
2. <span data-ttu-id="dfde1-117">추가 기능을 비즈니스 내 더 많은 개인에게 롤아웃합니다.</span><span class="sxs-lookup"><span data-stu-id="dfde1-117">Roll out the add-in to more individuals within the business.</span></span> <span data-ttu-id="dfde1-118">다시 결과를 평가하고 성공하면 전체 배포를 계속합니다.</span><span class="sxs-lookup"><span data-stu-id="dfde1-118">Again, evaluate the results and, if successful, continue with full deployment.</span></span>
    
3. <span data-ttu-id="dfde1-119">모든 사용자에게 전체 롤아웃을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="dfde1-119">Perform a full rollout to all users.</span></span>
    
<span data-ttu-id="dfde1-120">대상 대상의 크기에 따라 롤아웃 단계를 추가하거나 제거할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dfde1-120">Depending on the size of the target audience, you can add or remove roll-out steps.</span></span>
  
## <a name="deploy-an-office-add-in-using-the-admin-center"></a><span data-ttu-id="dfde1-121">관리 센터를 사용하여 Office 추가 기능 배포</span><span class="sxs-lookup"><span data-stu-id="dfde1-121">Deploy an Office add-in using the admin center</span></span>

<span data-ttu-id="dfde1-122">시작하기 전에 추가 기능의 중앙 집중식 배포가 조직에 [적합한지 확인을 참조합니다.](centralized-deployment-of-add-ins.md)</span><span class="sxs-lookup"><span data-stu-id="dfde1-122">Before you begin, see [Determine if Centralized Deployment of add-ins works for your organization](centralized-deployment-of-add-ins.md).</span></span>
  
1. <span data-ttu-id="dfde1-123">관리 센터에서 설정 추가  \> **기능 페이지로** 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="dfde1-123">In the admin center, go to the **Settings** \> **Add-ins** page.</span></span> <span data-ttu-id="dfde1-124">추가 기능 페이지가  없는 경우 설정 통합  앱 추가 \>  \> **기능 페이지로** 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="dfde1-124">If you don't see the **Add-in** Page, go to the **Settings** \> **Integrated apps** \> **Add-ins** page.</span></span>
    
2. <span data-ttu-id="dfde1-125">페이지 **맨 위에 있는** 추가 기능 배포를 선택하고 다음을 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="dfde1-125">Select **Deploy Add-in** at the top of the page, and then select **Next**.</span></span>
 
    > [!NOTE]
    > <span data-ttu-id="dfde1-126">관리 센터가 통합 앱을 사용하여 배포 환경으로 업데이트되고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dfde1-126">The admin center is getting updated to deployment experience with Integrated Apps .</span></span> <span data-ttu-id="dfde1-127">위의 단계가 없는 경우 설정 통합 앱으로 이동하여 중앙 집중식 배포  >  **섹션으로 이동합니다.**</span><span class="sxs-lookup"><span data-stu-id="dfde1-127">If you don't see the above steps, go to Centralized Deployment section by going to **Settings** > **Integrated apps**.</span></span> <span data-ttu-id="dfde1-128">통합 앱 페이지  위쪽에서 추가 기능을 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="dfde1-128">On the top of the **Integrated apps** page, choose **Add-ins**.</span></span>
    
3. <span data-ttu-id="dfde1-129">옵션을 선택하고 지침을 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="dfde1-129">Select an option and follow the instructions.</span></span>
  
4. <span data-ttu-id="dfde1-130">Office 스토어에서 추가 기능을 추가하는 옵션을 선택한 경우 추가 기능을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="dfde1-130">If you selected the option to add an add-in from the Office Store, make your add-in selection.</span></span> </br>

    <span data-ttu-id="dfde1-131">추천, 평점 또는 이름과 같은  **범주별로** 사용 가능한 추가 기능을 볼 수 **있습니다.**</span><span class="sxs-lookup"><span data-stu-id="dfde1-131">You can view available add-ins by categories: **Suggested for you**, **Rating**, or **Name**.</span></span> <span data-ttu-id="dfde1-132">Office 스토어에서는 무료 추가 기능만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dfde1-132">Only free add-ins are available from the Office Store.</span></span> <span data-ttu-id="dfde1-133">유료 추가 기능은 현재 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="dfde1-133">Paid add-ins aren't supported currently.</span></span> <span data-ttu-id="dfde1-134">추가 기능을 선택한 후 계속할 사용 약관에 동의합니다.</span><span class="sxs-lookup"><span data-stu-id="dfde1-134">After you select an add-in, accept the terms and conditions to proceed.</span></span> <br/> 

    > [!NOTE] 
    > <span data-ttu-id="dfde1-135">Office 스토어 옵션을 사용하면 업데이트 및 향상된 기능이 사용자에게 자동으로 배포됩니다.</span><span class="sxs-lookup"><span data-stu-id="dfde1-135">With the Office Store option, updates and enhancements are automatically deployed to users.</span></span>

5. <span data-ttu-id="dfde1-136">다음 페이지에서 **모든** 사용자, 특정 **사용자/그룹을** 선택하거나 추가 기능을 배포할 사용자를 지정합니다. </span><span class="sxs-lookup"><span data-stu-id="dfde1-136">On the next page, select **Everyone**, **Specific users/groups**, or **Just me** to specify who the add-in is deployed to.</span></span> <span data-ttu-id="dfde1-137">검색 상자를 사용하여 특정 사용자 또는 그룹을 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dfde1-137">Use the Search box to find specific users or groups.</span></span> <br/>

    > [!NOTE] 
    > <span data-ttu-id="dfde1-138">추가 기능에 적용되는 다른 상태는 추가 기능 [상태(추가 기능)를 참조합니다.](https://docs.microsoft.com/microsoft-365/admin/manage/manage-addins-in-the-admin-center.md)</span><span class="sxs-lookup"><span data-stu-id="dfde1-138">To learn about other states that apply to an add-in, see [Add-in states](https://docs.microsoft.com/microsoft-365/admin/manage/manage-addins-in-the-admin-center.md).</span></span>
  
6. <span data-ttu-id="dfde1-139">배포를 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="dfde1-139">Select **Deploy**.</span></span>
  
7. <span data-ttu-id="dfde1-140">추가 기능을 배포할 때 녹색 틱이 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="dfde1-140">A green tick appears when the add-in is deployed.</span></span> <span data-ttu-id="dfde1-141">페이지 지침에 따라 추가 기능을 테스트합니다.</span><span class="sxs-lookup"><span data-stu-id="dfde1-141">Follow the on-page instructions to test the add-in.</span></span>

    > [!NOTE]
    > <span data-ttu-id="dfde1-142">사용자는 앱 리본에서 추가 기능 아이콘을 보기 위해 Office를 다시 실행해야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dfde1-142">Users might need to relaunch Office to view the add-in icon on the app ribbon.</span></span> <span data-ttu-id="dfde1-143">Outlook 추가 기능을 앱 리본 메뉴에 표시하는 데 최대 24시간이 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dfde1-143">Outlook add-ins can take up to 24 hours to appear on app ribbons.</span></span>
    
8. <span data-ttu-id="dfde1-144">완료되면 다음을 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="dfde1-144">When finished, select **Next**.</span></span> <span data-ttu-id="dfde1-145">직접 배포한 경우 추가 기능 액세스  권한이 있는 사용자 변경을 선택하여 더 많은 사용자에게 배포할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dfde1-145">If you've deployed to just yourself, you can select **Change who has access to add-in** to deploy to more users.</span></span>

    <span data-ttu-id="dfde1-146">조직의 다른 구성원에게 추가 기능을 배포한 경우 지침에 따라 추가 기능 배포를 발표합니다.</span><span class="sxs-lookup"><span data-stu-id="dfde1-146">If you've deployed the add-in to other members of your organization, follow the instructions to announce the deployment of the add-in.</span></span> <br/>
  
    <span data-ttu-id="dfde1-147">배포된 추가 기능을 사용할 수 있도록 사용자 및 그룹에 알리는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="dfde1-147">It's good practice to inform users and groups that the deployed add-in is available.</span></span> <span data-ttu-id="dfde1-148">추가 기능을 사용하는 경우와 사용 방법을 설명하는 전자 메일을 보내는 것이 고려됩니다.</span><span class="sxs-lookup"><span data-stu-id="dfde1-148">Consider sending an email that describes when and how to use the add-in.</span></span> <span data-ttu-id="dfde1-149">추가 기능 관련 문제가 있는 경우 사용자에게 도움이 될 수 있는 도움말 콘텐츠 또는 FAQ를 포함하거나 연결합니다.</span><span class="sxs-lookup"><span data-stu-id="dfde1-149">Include or link to Help content or FAQs that might help users if they have problems with the add-in.</span></span>
  
### <a name="considerations-when-assigning-an-add-in-to-users-and-groups"></a><span data-ttu-id="dfde1-150">사용자 및 그룹에 추가 기능을 할당할 때 고려 사항</span><span class="sxs-lookup"><span data-stu-id="dfde1-150">Considerations when assigning an add-in to users and groups</span></span>

<span data-ttu-id="dfde1-151">관리자는 모든 사용자 또는 특정 사용자 및 그룹에 추가 기능을 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dfde1-151">Admins can assign an add-in to everyone or to specific users and groups.</span></span> <span data-ttu-id="dfde1-152">각 옵션은 다음과 같은 영향을 줍니다.</span><span class="sxs-lookup"><span data-stu-id="dfde1-152">Each option has implications:</span></span>
  
- <span data-ttu-id="dfde1-153">**모든 사람** 이 옵션은 조직의 모든 사용자에게 추가 기능을 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="dfde1-153">**Everyone** This option assigns the add-in to every user in the organization.</span></span> <span data-ttu-id="dfde1-154">이 옵션은 조직에 진정으로 범용인 추가 기능에 대해서만 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="dfde1-154">Use this option sparingly and only for add-ins that are truly universal to your organization.</span></span> 
    
- <span data-ttu-id="dfde1-155">**사용자** 개별 사용자에게 추가 기능을 할당한 다음 새 사용자에게 추가 기능을 배포하는 경우 먼저 새 사용자를 추가해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="dfde1-155">**Users** If you assign an add-in to an individual user, and then deploy the add-in to a new user, you must first add the new user.</span></span>
    
- <span data-ttu-id="dfde1-156">**그룹** 그룹에 추가 기능을 할당하면 그룹에 추가된 사용자에게 자동으로 추가 기능을 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="dfde1-156">**Groups** If you assign an add-in to a group, users who are added to the group are automatically assigned the add-in.</span></span> <span data-ttu-id="dfde1-157">사용자가 그룹에서 제거되면 사용자는 추가 기능 액세스 권한을 잃게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="dfde1-157">When a user is removed from a group, the user loses access to the add-in.</span></span> <span data-ttu-id="dfde1-158">어느 경우든 관리자에게 추가 작업이 필요하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="dfde1-158">In either case, no additional action is required from the admin.</span></span> 

- <span data-ttu-id="dfde1-159">**나만** 추가 기능을 직접 할당하는 경우 추가 기능 테스트에 적합한 계정에만 추가 기능을 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="dfde1-159">**Just me** If you assign an add-in to just yourself, the add-in is assigned to only your account, which is ideal for testing the add-in.</span></span>
    
<span data-ttu-id="dfde1-160">조직에 적합한 옵션은 구성에 따라 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="dfde1-160">The right option for your organization depends on your configuration.</span></span> <span data-ttu-id="dfde1-161">그러나 그룹을 사용하여 할당하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="dfde1-161">However, we recommend making assignments by using groups.</span></span> <span data-ttu-id="dfde1-162">관리자는 매회 개별 사용자를 할당하는 대신 그룹을 사용하고 해당 그룹의 구성원을 제어하여 추가 기능을 더 쉽게 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dfde1-162">As an admin, you might find it easier to manage add-ins by using groups and controlling the membership of those groups rather than assigning individual users each time.</span></span> <span data-ttu-id="dfde1-163">경우에 따라 사용자를 수동으로 할당하여 특정 사용자에게 할당하여 소수의 사용자 집합에 대한 액세스를 제한할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dfde1-163">In some situations, you might want to restrict access to a small set of users by making assignments to specific users by assigning users manually.</span></span>
  
## <a name="more-about-office-add-ins-security"></a><span data-ttu-id="dfde1-164">Office 추가 기능 보안에 대한 자세한 정보</span><span class="sxs-lookup"><span data-stu-id="dfde1-164">More about Office add-ins security</span></span>

<span data-ttu-id="dfde1-p118">Office 추가 기능은 추가 기능에 대한 일부 메타데이터를 포함하지만 무엇보다도 모든 코드와 논리가 포함된 웹 응용 프로그램을 가리키는 XML 매니페스트 파일을 결합합니다. 추가 기능의 기능은 다양할 수 있습니다. 예를 들어 추가 기능은 다음과 같은 작업을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dfde1-p118">Office add-ins combine an XML manifest file that contains some metadata about the add-in, but most importantly points to a web application which contains all the code and logic. Add-ins can range in their capabilities. For example, add-ins can:</span></span>
  
- <span data-ttu-id="dfde1-168">데이터를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="dfde1-168">Display data.</span></span>
    
- <span data-ttu-id="dfde1-169">사용자 문서를 읽어 상황에 맞는 서비스를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="dfde1-169">Read a user's document to provide contextual services.</span></span>
    
- <span data-ttu-id="dfde1-170">사용자 문서에서 데이터를 읽고 기록하여 해당 사용자에게 값을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="dfde1-170">Read and write data to and from a user's document to provide value to that user.</span></span>
    
<span data-ttu-id="dfde1-171">Office 추가 기능의 유형 및 기능에 대한 자세한 내용은 [Office 추가 기능 플랫폼 개요](https://docs.microsoft.com/office/dev/add-ins/overview/office-add-ins)에서, 특히 "Office 추가 기능 분석" 섹션을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="dfde1-171">For more information about the types and capabilities of Office add-ins, see [Office Add-ins platform overview](https://docs.microsoft.com/office/dev/add-ins/overview/office-add-ins), especially the section "Anatomy of an Office Add-in."</span></span>
  
<span data-ttu-id="dfde1-p119">사용자 문서를 조작하려면 추가 기능이 필요한 사용 권한을 매니페스트에서 선언해야 합니다. 5개 수준으로 이루어진 JavaScript API 액세스 권한 모델은 작업창 추가 기능의 사용자에게 개인 정보 및 보안의 토대를 제공합니다. Office 스토어에 있는 대부분의 추가 기능은 ReadWriteDocument 수준이며, 거의 모든 추가 기능이 최소한 ReadDocument 수준을 지원합니다. 사용 권한 수준에 대한 자세한 내용은 [콘텐츠 및 작업창 추가 기능에서 사용되는 API에 대한 사용 권한 요청](https://docs.microsoft.com/office/dev/add-ins/develop/requesting-permissions-for-api-use-in-content-and-task-pane-add-ins)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="dfde1-p119">To interact with the user's document, the add-in needs to declare what permission it needs in the manifest. A five-level JavaScript API access-permissions model provides the basis for privacy and security for users of task pane add-ins. The majority of the add-ins in the Office Store are level ReadWriteDocument with almost all add-ins supporting at least the ReadDocument level. For more information about the permission levels, see [Requesting permissions for API use in content and task pane add-ins](https://docs.microsoft.com/office/dev/add-ins/develop/requesting-permissions-for-api-use-in-content-and-task-pane-add-ins).</span></span>
  
<span data-ttu-id="dfde1-p120">매니페스트를 업데이트하는 경우 일반적으로 추가 기능의 아이콘과 텍스트가 변경됩니다. 추가 기능 명령이 변경될 때도 있습니다. 그러나 추가 기능에 대한 사용 권한은 변경되지 않습니다. 추가 기능에 대한 모든 코드와 논리가 실행되는 웹 응용 프로그램은 언제든지 변경될 수 있으며, 이것이 웹 응용 프로그램의 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="dfde1-p120">When updating a manifest, the typical changes are to an add-in's icon and text. Occasionally, add-in commands change. However, the permissions of the add-in do not change. The web application where all the code and logic for the add-in runs can change at any time, which is the nature of web applications.</span></span>
  
<span data-ttu-id="dfde1-179">추가 기능에 대한 업데이트는 다음과 같이 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="dfde1-179">Updates for add-ins happen as follows:</span></span>
  
- <span data-ttu-id="dfde1-p121">**LOB(기간 업무) 추가 기능:** 관리자가 명시적으로 매니페스트를 업로드한 이러한 경우에는 추가 기능을 위해 관리자가 새 매니페스트 파일을 업로드하여 메타데이터 변경 내용을 지원해야 합니다. 다음에 관련 Office 응용 프로그램을 시작하면 추가 기능이 업데이트됩니다. 웹 응용 프로그램은 언제든지 변경될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dfde1-p121">**Line-of-business add-in:** In this case, where an admin explicitly uploaded a manifest, the add-in requires that the admin upload a new manifest file to support metadata changes. The next time the relevant Office applications start, the add-in will update. The web application can change at any time.</span></span> 

    > [!NOTE]
    > <span data-ttu-id="dfde1-183">관리자는 업데이트를 수행하기 위해 LOB 추가 기능을 제거할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="dfde1-183">Admin does not need to remove a LOB Add-in for doing an update.</span></span>   <span data-ttu-id="dfde1-184">추가 기능 섹션에서 관리자는 LOB 추가 기능을 클릭하고 오른쪽 아래에  있는 업데이트 단추를 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dfde1-184">In the Add-ins section, Admin can simply click on the LOB Add-in and choose the **Update Button** in the bottom right corner.</span></span> <span data-ttu-id="dfde1-185">업데이트는 새 추가 기능의 버전이 기존 추가 기능의 버전보다 큰 경우만 작동됩니다.</span><span class="sxs-lookup"><span data-stu-id="dfde1-185">Update will work only if the version of the new add-in is greater than that of the existing add-in.</span></span>   
    
- <span data-ttu-id="dfde1-p123">**Office 스토어 추가 기능:** 관리자가 Office 스토어에서 추가 기능을 선택한 경우 Office 스토어에서 추가 기능이 업데이트되면 나중에 중앙 집중식 배포에서도 추가 기능이 업데이트됩니다. 다음에 관련 Office 응용 프로그램을 시작하면 추가 기능이 업데이트됩니다. 웹 응용 프로그램은 언제든지 변경될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dfde1-p123">**Office Store add-in:** When an admin selected an add-in from the Office Store, if an add-in updates in the Office Store, the add-in will update later in Centralized Deployment. The next time the relevant Office applications start, the add-in will update. The web application can change at any time.</span></span> 
  
## <a name="learn-more"></a><span data-ttu-id="dfde1-189">자세히 알아보기</span><span class="sxs-lookup"><span data-stu-id="dfde1-189">Learn more</span></span>

[<span data-ttu-id="dfde1-190">관리 센터에서 추가 기능 관리</span><span class="sxs-lookup"><span data-stu-id="dfde1-190">Manage add-ins in the admin center</span></span>](manage-addins-in-the-admin-center.md)

<span data-ttu-id="dfde1-191">[첫 번째 Word 작업 창 추가 기능을 빌드합니다.](https://docs.microsoft.com/office/dev/add-ins/quickstarts/word-quickstart?tabs=yeomangenerator)</span><span class="sxs-lookup"><span data-stu-id="dfde1-191">[Build your first Word task pane add-in](https://docs.microsoft.com/office/dev/add-ins/quickstarts/word-quickstart?tabs=yeomangenerator).</span></span>

[<span data-ttu-id="dfde1-192">미성년자 및 스토어에서 추가 기능 다운로드</span><span class="sxs-lookup"><span data-stu-id="dfde1-192">Minors and acquiring add-ins from the store</span></span>](minors-and-acquiring-addins-from-the-store.md)
  
[<span data-ttu-id="dfde1-193">중앙 집중식 배포 PowerShell cmdlet을 사용하여 추가 기능 관리</span><span class="sxs-lookup"><span data-stu-id="dfde1-193">Use Centralized Deployment PowerShell cmdlets to manage add-ins</span></span>](https://docs.microsoft.com/microsoft-365/enterprise/use-the-centralized-deployment-powershell-cmdlets-to-manage-add-ins)
  
[<span data-ttu-id="dfde1-194">문제 해결: 사용자가 추가 기능을 볼 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="dfde1-194">Troubleshoot: User not seeing add-ins</span></span>](https://docs.microsoft.com/office365/troubleshoot/access-management/user-not-seeing-add-ins)
