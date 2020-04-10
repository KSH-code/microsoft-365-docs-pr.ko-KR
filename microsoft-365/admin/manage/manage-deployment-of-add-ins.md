---
title: 관리 센터에서 Office 365 추가 기능의 배포 관리
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
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 737e8c86-be63-44d7-bf02-492fa7cd9c3f
description: 관리 센터에서 중앙 집중식 배포를 사용 하 여 조직의 사용자 및 그룹에 추가 기능을 배포 하는 방법을 알아봅니다.
ms.openlocfilehash: d0818a0f318ea260d8e39b6e3d76c1cd4efd7a88
ms.sourcegitcommit: 4a34b48584071e0c43c920bb35025e34cb4f5d15
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/09/2020
ms.locfileid: "43212012"
---
# <a name="manage-deployment-of-office-365-add-ins-in-the-microsoft-365-admin-center"></a><span data-ttu-id="f7b4c-103">Microsoft 365 관리 센터에서 Office 365 추가 기능 배포 관리</span><span class="sxs-lookup"><span data-stu-id="f7b4c-103">Manage deployment of Office 365 add-ins in the Microsoft 365 admin center</span></span>

<span data-ttu-id="f7b4c-104">Office 추가 기능을 사용하면 문서를 개인 설정하고 웹에서 정보에 액세스하는 방법을 간소화할 수 있습니다([Office 추가 기능 사용 시작](https://support.office.com/article/82e665c4-6700-4b56-a3f3-ef5441996862.aspx) 참조).</span><span class="sxs-lookup"><span data-stu-id="f7b4c-104">Office add-ins help you personalize your documents and streamline the way you access information on the web (see [Start using your Office Add-in](https://support.office.com/article/82e665c4-6700-4b56-a3f3-ef5441996862.aspx)).</span></span> <span data-ttu-id="f7b4c-105">관리자는 조직의 사용자를 위한 Office 추가 기능을 배포할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f7b4c-105">As an admin, you can deploy Office add-ins for the users in your organization.</span></span> <span data-ttu-id="f7b4c-106">Microsoft 365 관리 센터의 중앙 집중식 배포 기능을 사용 하 여이 작업을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f7b4c-106">You can do this using the Centralized Deployment feature in the Microsoft 365 admin center.</span></span>
  
<span data-ttu-id="f7b4c-107">중앙 집중식 배포는 대부분의 관리자가 조직 내에서 사용자 및 그룹에 추가 기능을 배포 하는 데 권장 되 고 기능이 풍부한 방법입니다.</span><span class="sxs-lookup"><span data-stu-id="f7b4c-107">Centralized Deployment is the recommended and most feature-rich way for most admins to deploy add-ins to users and groups within an organization.</span></span> <span data-ttu-id="f7b4c-108">조직에서 중앙 집중식 배포를 지원할 수 있는지를 확인하는 방법에 대한 자세한 내용은 [추가 기능의 중앙 집중식 배포가 Office 365 조직에서 작동하는지 확인](centralized-deployment-of-add-ins.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="f7b4c-108">For more information on how to determine if your organization can support Centralized Deployment, see [Determine if Centralized Deployment of add-ins works for your Office 365 organization](centralized-deployment-of-add-ins.md).</span></span>
  
<span data-ttu-id="f7b4c-109">중앙 집중식 배포는 다음과 같은 이점을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="f7b4c-109">Centralized Deployment provides the following benefits:</span></span>
  
- <span data-ttu-id="f7b4c-110">전역 관리자는 추가 기능을 사용자에 게 직접 할당 하거나, 그룹을 통해 여러 사용자에 게 또는 테 넌 트의 모든 사람에 게 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f7b4c-110">A Global admin can assign an add-in directly to a user, to multiple users via a group, or to everyone in the tenant.</span></span>
    
- <span data-ttu-id="f7b4c-p103">관련 Office 응용 프로그램이 시작되면 사용자를 위해 추가 기능이 자동으로 다운로드됩니다. 추가 기능이 추가 기능 명령을 지원하는 경우 추가 기능은 자동으로 Office 응용 프로그램 내의 리본에 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="f7b4c-p103">When the relevant Office application starts, the add-in automatically downloads for the user. If the add-in supports add-in commands, the add-in automatically appears in the Ribbon within the Office application.</span></span>
    
- <span data-ttu-id="f7b4c-113">관리자가 추가 기능을 해제 하거나 삭제 하거나, 사용자가 Azure Active Directory 또는 추가 기능이 할당 된 그룹에서 제거 된 경우에는 사용자에 게 더 이상 추가 기능이 나타나지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="f7b4c-113">Add-ins will no longer appear for users if the admin turns off or deletes the add-in, or if the user is removed from Azure Active Directory or from a group that the add-in is assigned to.</span></span>
    
> [!NOTE]
>  <span data-ttu-id="f7b4c-114">Word에서 Excel 및 PowerPoint는 [Sharepoint 앱 카탈로그](https://dev.office.com/docs/add-ins/publish/publish-task-pane-and-content-add-ins-to-an-add-in-catalog) 를 사용 하 여 Office 365 및/또는 sharepoint 추가 기능에 대 한 지원에 연결 하지 않고 온-프레미스 환경의 사용자에 게 추가 기능을 배포 합니다.</span><span class="sxs-lookup"><span data-stu-id="f7b4c-114">For Word, Excel and PowerPoint use a [SharePoint App Catalog](https://dev.office.com/docs/add-ins/publish/publish-task-pane-and-content-add-ins-to-an-add-in-catalog) to deploy add-ins to users in an on-premises environment with no connection to Office 365 and/or support for SharePoint add-ins required.</span></span> <span data-ttu-id="f7b4c-115">>  Outlook의 경우 Office 365에 연결하지 않고 온 - 프레미스 환경에서 배포하려면 Exchange 제어판을 사용하세요.</span><span class="sxs-lookup"><span data-stu-id="f7b4c-115">>  For Outlook use Exchange control panel to deploy in an on-premises environment without a connection to Office 365.</span></span> > 
  
## <a name="recommended-approach-for-deploying-office-add-ins"></a><span data-ttu-id="f7b4c-116">Office 추가 기능 배포에 권장되는 방법</span><span class="sxs-lookup"><span data-stu-id="f7b4c-116">Recommended approach for deploying Office add-ins</span></span>

<span data-ttu-id="f7b4c-p105">단계적 방법으로 추가 기능을 배포하면 추가 기능 배포가 원활하게 진행됩니다. 다음 계획이 권장됩니다.</span><span class="sxs-lookup"><span data-stu-id="f7b4c-p105">Consider rolling out add-ins in a phased approach to help ensure your add-in deployment goes smoothly. We recommend the following plan:</span></span>
  
1. <span data-ttu-id="f7b4c-p106">소수의 업무 관련자 및 IT 부서 구성원에게 추가 기능을 배포합니다. 배포가 성공적이었는지 평가하고, 성공적인 경우 2단계로 넘어갑니다.</span><span class="sxs-lookup"><span data-stu-id="f7b4c-p106">Roll-out the add-in to a small set of business stakeholders and members of the IT department. Evaluate if the deployment was successful, and if so, move on to step 2.</span></span>
    
2. <span data-ttu-id="f7b4c-p107">추가 기능을 사용하게 될 업무 내 더 많은 개인에게 배포합니다. 다시 결과를 평가하고 모든 사항이 순조롭게 진행된 경우 전체 배포의 다음 단계로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="f7b4c-p107">Roll-out to a larger set of individuals within the business who will be using the add-in. Again, evaluate results and, if all went well, go to the next step of a full deployment.</span></span>
    
3. <span data-ttu-id="f7b4c-123">사용자 대상 그룹에 전체 배포합니다.</span><span class="sxs-lookup"><span data-stu-id="f7b4c-123">Full rollout to target audience of users.</span></span>
    
<span data-ttu-id="f7b4c-124">대상 그룹의 크기에 따라 배포 단계를 추가하거나 제거할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f7b4c-124">Depending on the size of the target audience, you may want to add or remove roll-out steps.</span></span>
  
## <a name="deploy-an-office-add-in-using-the-admin-center"></a><span data-ttu-id="f7b4c-125">관리 센터를 사용 하 여 Office 추가 기능 배포</span><span class="sxs-lookup"><span data-stu-id="f7b4c-125">Deploy an Office add-in using the admin center</span></span>

<span data-ttu-id="f7b4c-126">시작하기 전에 [추가 기능의 중앙 집중식 배포가 Office 365 조직에서 작동하는지 확인](centralized-deployment-of-add-ins.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="f7b4c-126">Before you begin, see [Determine if Centralized Deployment of add-ins works for your Office 365 organization](centralized-deployment-of-add-ins.md).</span></span>

  
1. <span data-ttu-id="f7b4c-127">Microsoft 365 관리 센터에서 **설정** > **추가 기능** 페이지로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="f7b4c-127">In the Microsoft 365 admin center, go to the **Settings** > **Add-ins** page.</span></span>
    
2. <span data-ttu-id="f7b4c-128">페이지 맨 위에 있는 **추가 기능 배포** 를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="f7b4c-128">Select **Deploy Add-in** at the top of the page.</span></span> <span data-ttu-id="f7b4c-129">개요 페이지에서 **다음**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="f7b4c-129">On the overview page, select **Next**.</span></span>
    
3. <span data-ttu-id="f7b4c-130">옵션을 선택 하 고 지침을 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="f7b4c-130">Select an option and follow the instructions.</span></span>
  
4. <span data-ttu-id="f7b4c-131">Office 스토어에서 추가 기능을 추가 하는 옵션을 선택한 경우 이제 추가 기능을 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f7b4c-131">If you selected the option to add an add-in from the Office Store, you can now make your add-in selection.</span></span> <span data-ttu-id="f7b4c-132">**추천 항목**, **평가** 또는 **이름** 범주를 통해 사용 가능한 추가 기능을 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f7b4c-132">Notice that you can view available add-ins via categories of **Suggested for you**, **Rating**, or **Name**.</span></span> <span data-ttu-id="f7b4c-133">Office 스토어에서는 무료 추가 기능만 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f7b4c-133">Only free add-ins are available to add from the Office Store.</span></span> <span data-ttu-id="f7b4c-134">유료 추가 기능은 현재 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="f7b4c-134">Paid add-ins aren't supported currently.</span></span> <span data-ttu-id="f7b4c-135">추가 기능을 선택한 후에는 몇 가지 추가 약관에 동의 하 여 진행 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f7b4c-135">Once you've selected your add-in, you will need to agree to some additional terms and conditions in order to proceed.</span></span> <br/><br/> <span data-ttu-id="f7b4c-136">참고: Office 스토어 옵션을 사용 하면 사용자가 작업을 수행 하지 않고도 추가 기능에 대 한 업데이트 및 향상 기능을 자동으로 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f7b4c-136">NOTE: With the Office Store option, updates and enhancements to the add-in will automatically be made available to users without your intervention.</span></span>

5. <span data-ttu-id="f7b4c-137">다음 페이지에서 **모든 사용자**, **특정 사용자/그룹** 또는 **자신만** 을 선택 하 여 추가 기능을 배포할 사용자를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="f7b4c-137">On the next page, select **Everyone**, **Specific users/groups** or **Just me** to specify who the add-in is deployed to.</span></span> <span data-ttu-id="f7b4c-138">추가 기능을 배포할 사용자 또는 그룹을 찾으려면 검색 상자를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="f7b4c-138">Use the Search box to find the users or groups who you want to deploy the add-in to.</span></span> <br/><span data-ttu-id="f7b4c-139">참고: 추가 기능에 적용 되는 다른 상태에 대해 알아봅니다.</span><span class="sxs-lookup"><span data-stu-id="f7b4c-139">NOTE: Learn about the other states that apply to an add-in.</span></span> <span data-ttu-id="f7b4c-140">이 항목의 뒷부분에 나오는 [추가 기능 상태](#add-in-states)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="f7b4c-140">See [Add-in states](#add-in-states) later in this topic.</span></span>
  
6. <span data-ttu-id="f7b4c-141">**배포**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="f7b4c-141">Select **Deploy**.</span></span>
  
7. <span data-ttu-id="f7b4c-142">추가 기능이 배포 되 면 녹색 눈금이 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f7b4c-142">A green tick will appear when the add-in has been deployed.</span></span> <span data-ttu-id="f7b4c-143">페이지에 설명 된 지침에 따라 추가 기능이 성공적으로 배포 되었는지 테스트할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f7b4c-143">You can follow the on-page instructions to test that the add-in has deployed successfully.</span></span>

> [!NOTE]
> <span data-ttu-id="f7b4c-144">앱의 리본 메뉴에 추가 기능 아이콘이 표시 되도록 하려면 Office를 다시 열어야 할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f7b4c-144">Users may need to relaunch Office to see the add-in icon appear on the ribbon of app.</span></span> <span data-ttu-id="f7b4c-145">Outlook 추가 기능은 사용자의 리본에 표시 되는 데 최대 24 시간이 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f7b4c-145">Outlook add-ins can take up to 24 hours to appear on users' ribbons.</span></span>
    
8. <span data-ttu-id="f7b4c-146">완료 되 면 **다음**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="f7b4c-146">When finished, select **Next**.</span></span> <span data-ttu-id="f7b4c-147">자신에 게 배포한 경우 **추가 기능에 액세스할** 수 있는 사용자를 선택 하 여 다른 사용자에 게 배포 합니다.</span><span class="sxs-lookup"><span data-stu-id="f7b4c-147">If you've deployed to just yourself, you can select **Change who has access to add-in** in order to deploy to more users.</span></span>



<span data-ttu-id="f7b4c-148">사용자가 아닌 다른 조직의 구성원에 게 추가 기능을 배포한 경우 추가 기능의 배포를 효과적으로 알리기 위해 표시 된 지침을 따르세요.</span><span class="sxs-lookup"><span data-stu-id="f7b4c-148">If you've deployed the add-in to members of your organization other than yourself, follow the instructions displayed in order to effectively announce the deployment of the add-in.</span></span> <br/><span data-ttu-id="f7b4c-149">이제 Office 365에 추가 기능이 다른 앱과 함께 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="f7b4c-149">You now see your add-in along with other apps in Office 365.</span></span>
  
<span data-ttu-id="f7b4c-150">추가 기능을 배포한 사용자 및 그룹에 이제 추가 기능을 사용할 수 있다는 사실을 알려 주는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="f7b4c-150">It's a good idea to inform the users and groups who you deployed the add-in to so that they know that it's available.</span></span> <span data-ttu-id="f7b4c-151">추가 기능을 사용하는 경우 및 방법을 설명하고 추가 기능이 업무 수행에 어떻게 도움이 될 수 있는지를 설명하는 전자 메일을 해당 사용자 및 그룹에 보내는 것을 고려하세요.</span><span class="sxs-lookup"><span data-stu-id="f7b4c-151">Consider sending an email to them that describes when and how to use the add-in and explains how the add-in can help them do their job better.</span></span> <span data-ttu-id="f7b4c-152">사용자에 게 추가 기능에 문제가 있는 경우 도움이 될 수 있는 관련 도움말 콘텐츠 또는 Faq를 포함 하거나 연결 합니다.</span><span class="sxs-lookup"><span data-stu-id="f7b4c-152">Include or link to relevant Help content or FAQs that might help if users have any problems with the add-in.</span></span>
  
### <a name="considerations-when-assigning-an-add-in-to-users-and-groups"></a><span data-ttu-id="f7b4c-153">사용자 및 그룹에 추가 기능을 할당할 때 고려 사항</span><span class="sxs-lookup"><span data-stu-id="f7b4c-153">Considerations when assigning an add-in to users and groups</span></span>

<span data-ttu-id="f7b4c-p116">관리자는 모든 사용자 또는 특정 사용자 및 그룹에 추가 기능을 할당할 수 있습니다. 각 옵션은 다음과 같은 영향을 줍니다.</span><span class="sxs-lookup"><span data-stu-id="f7b4c-p116">Admins can assign an add-in to everyone or to specific users and groups. Each option has implications:</span></span>
  
- <span data-ttu-id="f7b4c-p117">**모두**: 이름에서 알 수 있듯이 이 옵션은 테넌트의 모든 사용자에게 추가 기능을 할당합니다. 이 옵션은 조직에 진정으로 범용인 추가 기능에 대해서만 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="f7b4c-p117">**Everyone**: As the name implies, this option assigns the add-in to every user in the tenant. Use this option sparingly and only for add-ins that are truly universal to your organization.</span></span> 
    
- <span data-ttu-id="f7b4c-p118">**사용자**: 추가 기능을 개별 사용자에게 할당하는 경우 새 사용자에게 추가 기능을 배포하려면 먼저 해당 사용자를 추가해야 합니다. 사용자 제거의 경우에도 마찬가지입니다.</span><span class="sxs-lookup"><span data-stu-id="f7b4c-p118">**Users**: If you assign an add-in to an individual user, then to deploy the add-in to a new user, you will need to first add that user. The same goes for removing users.</span></span> 
    
- <span data-ttu-id="f7b4c-p119">**그룹**: 추가 기능을 그룹에 할당하는 경우 그룹에 추가된 사용자에게는 자동으로 추가 기능이 할당됩니다. 또한 사용자가 그룹에서 제거되면 해당 사용자는 추가 기능에 대한 액세스 권한을 잃게 됩니다. 둘 중 어느 경우이든 관리자가 수행해야 할 추가 작업은 없습니다.</span><span class="sxs-lookup"><span data-stu-id="f7b4c-p119">**Groups**: If you assign an add-in to a group, users who are added to the group will automatically be assigned the add-in. And, when a user is removed from a group, the user loses access to the add-in. In either case, no additional action is required from you as the admin.</span></span> 

- <span data-ttu-id="f7b4c-163">**자신만: 추가**기능을 자신만에 게 할당 하면 사용자의 계정에만 추가 기능이 할당 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f7b4c-163">**Just me**: If you assign an add-in to just yourself, this assigns the add-in to only your account.</span></span> <span data-ttu-id="f7b4c-164">이 방법은 먼저 추가 기능을 테스트 하려는 경우에 유용 합니다.</span><span class="sxs-lookup"><span data-stu-id="f7b4c-164">This is ideal if you wish to test out the add-in first.</span></span>
    
<span data-ttu-id="f7b4c-165">조직에 적합 한 옵션은 구성에 따라 달라 집니다.</span><span class="sxs-lookup"><span data-stu-id="f7b4c-165">The option that is right for your organization depends on your configuration.</span></span> <span data-ttu-id="f7b4c-166">그러나 그룹을 통해 할당하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="f7b4c-166">However, we recommend making assignments via groups.</span></span> <span data-ttu-id="f7b4c-167">관리자의 입장에서는 할당된 사용자를 매번 변경하는 것보다 그룹을 사용하여 관리하고 해당 그룹의 구성원 자격을 관리하는 편이 더 쉽습니다.</span><span class="sxs-lookup"><span data-stu-id="f7b4c-167">As an admin, you might find it easier to manage add-ins using groups and control the membership of those groups rather than having to change the users assigned each time.</span></span> <span data-ttu-id="f7b4c-168">반면 액세스 권한을 극소수의 사용자만으로 제한하고, 따라서 특정 사용자에 대한 할당을 수행하려고 하는 경우가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f7b4c-168">On the other hand, in some situations, you may want to restrict access to a very small set of users and therefore make assignments to specific users.</span></span> <span data-ttu-id="f7b4c-169">이러한 경우에는 할당된 사용자를 수동으로 관리해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f7b4c-169">As a result, you will need to manage the assigned users manually.</span></span>
  
### <a name="add-in-states"></a><span data-ttu-id="f7b4c-170">추가 기능 상태</span><span class="sxs-lookup"><span data-stu-id="f7b4c-170">Add-in states</span></span>

<span data-ttu-id="f7b4c-171">관리자는 Microsoft 365 관리 센터에서 모든 사용자에 대해 배포 하는 추가 기능을 설정 하거나 해제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f7b4c-171">Admins can turn on or off the add-ins they deploy for all users from the Microsoft 365 admin center.</span></span>

1.    <span data-ttu-id="f7b4c-172">관리 센터에서 **설정** > **추가 기능** 페이지로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="f7b4c-172">In the admin center, go to the **Settings** > **Add-ins** page.</span></span> 
2.    <span data-ttu-id="f7b4c-173">배포 된 추가 기능을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="f7b4c-173">Select the deployed add-in.</span></span> 
3.    <span data-ttu-id="f7b4c-174">**상태** 전환을 클릭 하 여 추가 **기능을 설정 하거나** **해제**합니다.</span><span class="sxs-lookup"><span data-stu-id="f7b4c-174">Click the **Status** toggle to turn the add-in **On** or **Off**.</span></span> 
4.    <span data-ttu-id="f7b4c-175">변경 내용을 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="f7b4c-175">Save the changes.</span></span>  

<span data-ttu-id="f7b4c-176">세 가지 추가 기능 상태 중 하나를 사용할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f7b4c-176">One of three add-in states is also available.</span></span>
 
|<span data-ttu-id="f7b4c-177">**상태**</span><span class="sxs-lookup"><span data-stu-id="f7b4c-177">**State**</span></span>|<span data-ttu-id="f7b4c-178">**상태가 적용되는 경우**</span><span class="sxs-lookup"><span data-stu-id="f7b4c-178">**How the state occurs**</span></span>|<span data-ttu-id="f7b4c-179">**영향**</span><span class="sxs-lookup"><span data-stu-id="f7b4c-179">**Impact**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="f7b4c-180">**활성**</span><span class="sxs-lookup"><span data-stu-id="f7b4c-180">**Active**</span></span>  <br/> |<span data-ttu-id="f7b4c-181">관리자가 추가 기능을 업로드 하 고 사용자 또는 그룹에 할당 했습니다.</span><span class="sxs-lookup"><span data-stu-id="f7b4c-181">Admin uploaded the add-in and assigned it to users or groups.</span></span>  <br/> |<span data-ttu-id="f7b4c-182">추가 기능에 할당된 사용자 및 그룹은 관련 클라이언트에서 추가 기능을 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f7b4c-182">Users and groups assigned to the add-in see it in the relevant clients.</span></span>  <br/> |
|<span data-ttu-id="f7b4c-183">**해제됨**</span><span class="sxs-lookup"><span data-stu-id="f7b4c-183">**Turned off**</span></span>  <br/> |<span data-ttu-id="f7b4c-184">관리자가 추가 기능을 해제했습니다.</span><span class="sxs-lookup"><span data-stu-id="f7b4c-184">Admin turned off the add-in.</span></span>  <br/> |<span data-ttu-id="f7b4c-185">추가 기능에 할당된 사용자 및 그룹이 더 이상 추가 기능에 액세스할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="f7b4c-185">Users and groups assigned to the add-in no longer have access to it.</span></span>  <br/> <span data-ttu-id="f7b4c-186">추가 기능 상태가 **활성**으로 변경 되 면 사용자 및 그룹이 다시 액세스 하 게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f7b4c-186">If the add-in state is changed to **Active**, the users and groups will have access to it again.</span></span>  <br/> |
|<span data-ttu-id="f7b4c-187">**삭제됨**</span><span class="sxs-lookup"><span data-stu-id="f7b4c-187">**Deleted**</span></span>  <br/> |<span data-ttu-id="f7b4c-188">관리자가 추가 기능을 삭제했습니다.</span><span class="sxs-lookup"><span data-stu-id="f7b4c-188">Admin deleted the add-in.</span></span>  <br/> |<span data-ttu-id="f7b4c-189">추가 기능에 할당된 사용자 및 그룹이 더 이상 추가 기능에 액세스할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="f7b4c-189">Users and groups assigned the add-in no longer have access to it.</span></span>  <br/> |
   
<span data-ttu-id="f7b4c-190">추가 기능 중 아무도 사용 하지 않는 경우에는 삭제 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="f7b4c-190">Consider deleting an add-in if no one is using it any more.</span></span> <span data-ttu-id="f7b4c-191">추가 기능 해제는 1년 중 특정 시간에만 추가 기능이 사용되는 경우에 적합할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f7b4c-191">Turning off an add-in may make sense if an add-in is used only during specific times of the year.</span></span>
  
### <a name="security-of-office-add-ins"></a><span data-ttu-id="f7b4c-192">Office 추가 기능의 보안</span><span class="sxs-lookup"><span data-stu-id="f7b4c-192">Security of Office add-ins</span></span>

<span data-ttu-id="f7b4c-p123">Office 추가 기능은 추가 기능에 대한 일부 메타데이터를 포함하지만 무엇보다도 모든 코드와 논리가 포함된 웹 응용 프로그램을 가리키는 XML 매니페스트 파일을 결합합니다. 추가 기능의 기능은 다양할 수 있습니다. 예를 들어 추가 기능은 다음과 같은 작업을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f7b4c-p123">Office add-ins combine an XML manifest file that contains some metadata about the add-in, but most importantly points to a web application which contains all the code and logic. Add-ins can range in their capabilities. For example, add-ins can:</span></span>
  
- <span data-ttu-id="f7b4c-196">데이터를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="f7b4c-196">Display data.</span></span>
    
- <span data-ttu-id="f7b4c-197">사용자 문서를 읽어 상황에 맞는 서비스를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="f7b4c-197">Read a user's document to provide contextual services.</span></span>
    
- <span data-ttu-id="f7b4c-198">사용자 문서에서 데이터를 읽고 기록하여 해당 사용자에게 값을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="f7b4c-198">Read and write data to and from a user's document to provide value to that user.</span></span>
    
<span data-ttu-id="f7b4c-199">Office 추가 기능의 유형 및 기능에 대한 자세한 내용은 [Office 추가 기능 플랫폼 개요](https://go.microsoft.com/fwlink/p/?linkid=846362)에서, 특히 "Office 추가 기능 분석" 섹션을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="f7b4c-199">For more information about the types and capabilities of Office add-ins, see [Office Add-ins platform overview](https://go.microsoft.com/fwlink/p/?linkid=846362), especially the section "Anatomy of an Office Add-in."</span></span>
  
<span data-ttu-id="f7b4c-p124">사용자 문서를 조작하려면 추가 기능이 필요한 사용 권한을 매니페스트에서 선언해야 합니다. 5개 수준으로 이루어진 JavaScript API 액세스 권한 모델은 작업창 추가 기능의 사용자에게 개인 정보 및 보안의 토대를 제공합니다. Office 스토어에 있는 대부분의 추가 기능은 ReadWriteDocument 수준이며, 거의 모든 추가 기능이 최소한 ReadDocument 수준을 지원합니다. 사용 권한 수준에 대한 자세한 내용은 [콘텐츠 및 작업창 추가 기능에서 사용되는 API에 대한 사용 권한 요청](https://go.microsoft.com/fwlink/p/?linkid=848863)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="f7b4c-p124">To interact with the user's document, the add-in needs to declare what permission it needs in the manifest. A five-level JavaScript API access-permissions model provides the basis for privacy and security for users of task pane add-ins. The majority of the add-ins in the Office Store are level ReadWriteDocument with almost all add-ins supporting at least the ReadDocument level. For more information about the permission levels, see [Requesting permissions for API use in content and task pane add-ins](https://go.microsoft.com/fwlink/p/?linkid=848863).</span></span>
  
<span data-ttu-id="f7b4c-p125">매니페스트를 업데이트하는 경우 일반적으로 추가 기능의 아이콘과 텍스트가 변경됩니다. 추가 기능 명령이 변경될 때도 있습니다. 그러나 추가 기능에 대한 사용 권한은 변경되지 않습니다. 추가 기능에 대한 모든 코드와 논리가 실행되는 웹 응용 프로그램은 언제든지 변경될 수 있으며, 이것이 웹 응용 프로그램의 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="f7b4c-p125">When updating a manifest, the typical changes are to an add-in's icon and text. Occasionally, add-in commands change. However, the permissions of the add-in do not change. The web application where all the code and logic for the add-in runs can change at any time, which is the nature of web applications.</span></span>
  
<span data-ttu-id="f7b4c-207">추가 기능에 대한 업데이트는 다음과 같이 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="f7b4c-207">Updates for add-ins happen as follows:</span></span>
  
- <span data-ttu-id="f7b4c-p126">**LOB(기간 업무) 추가 기능:** 관리자가 명시적으로 매니페스트를 업로드한 이러한 경우에는 추가 기능을 위해 관리자가 새 매니페스트 파일을 업로드하여 메타데이터 변경 내용을 지원해야 합니다. 다음에 관련 Office 응용 프로그램을 시작하면 추가 기능이 업데이트됩니다. 웹 응용 프로그램은 언제든지 변경될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f7b4c-p126">**Line-of-business add-in:** In this case, where an admin explicitly uploaded a manifest, the add-in requires that the admin upload a new manifest file to support metadata changes. The next time the relevant Office applications start, the add-in will update. The web application can change at any time.</span></span> 

    > [!NOTE]
    > <span data-ttu-id="f7b4c-211">관리자는 업데이트를 수행 하는 데 필요한 LOB 추가 기능을 제거할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="f7b4c-211">Admin does not need to remove a LOB Add-in for doing an update.</span></span>   <span data-ttu-id="f7b4c-212">추가 기능 섹션에서 관리자는 LOB 추가 기능을 클릭 하 고 오른쪽 아래 모서리에 있는 **업데이트 단추** 를 선택 하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f7b4c-212">In the Add-ins section, Admin can simply click on the LOB Add-in and choose the **Update Button** in the bottom right corner.</span></span> <span data-ttu-id="f7b4c-213">새 추가 기능의 버전이 기존 추가 기능의 버전과 동일 하지 않은 경우에만 업데이트를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f7b4c-213">Update will work only if the version of the new add-in is greater than that of the existing add-in.</span></span>   
    
- <span data-ttu-id="f7b4c-p128">**Office 스토어 추가 기능:** 관리자가 Office 스토어에서 추가 기능을 선택한 경우 Office 스토어에서 추가 기능이 업데이트되면 나중에 중앙 집중식 배포에서도 추가 기능이 업데이트됩니다. 다음에 관련 Office 응용 프로그램을 시작하면 추가 기능이 업데이트됩니다. 웹 응용 프로그램은 언제든지 변경될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f7b4c-p128">**Office Store add-in:** When an admin selected an add-in from the Office Store, if an add-in updates in the Office Store, the add-in will update later in Centralized Deployment. The next time the relevant Office applications start, the add-in will update. The web application can change at any time.</span></span> 

### <a name="edit-add-in-access"></a><span data-ttu-id="f7b4c-217">추가 기능 액세스 편집</span><span class="sxs-lookup"><span data-stu-id="f7b4c-217">Edit Add-in access</span></span>

<span data-ttu-id="f7b4c-218">배포 후 관리자는 추가 기능에 대 한 사용자 액세스를 수정할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f7b4c-218">Post deployment, admins can also modify the user access to add-ins.</span></span>

1. <span data-ttu-id="f7b4c-219">관리 센터에서 **설정** > **서비스 & 추가** 기능 페이지로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="f7b4c-219">In the admin center, go to the **Settings** > **Services & add-ins** page.</span></span>

2. <span data-ttu-id="f7b4c-220">배포 된 추가 기능을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="f7b4c-220">Select the deployed add-in.</span></span>

3. <span data-ttu-id="f7b4c-221">**액세스 권한이 있는 사용자**아래에서 **편집** 을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="f7b4c-221">Click on **Edit** under **Who has Access**.</span></span>
4. <span data-ttu-id="f7b4c-222">변경 내용을 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="f7b4c-222">Save the changes.</span></span>
    
### <a name="prevent-add-in-downloads-by-turning-off-the-office-store-across-all-clients-except-outlook"></a><span data-ttu-id="f7b4c-223">모든 클라이언트로부터 Office 스토어를 꺼서 추가 기능 다운로드 방지 (Outlook 제외)</span><span class="sxs-lookup"><span data-stu-id="f7b4c-223">Prevent add-in downloads by turning off the Office Store across all clients (Except Outlook)</span></span>

> [!NOTE]
> <span data-ttu-id="f7b4c-224">Outlook 추가 기능 설치는 [다른 프로세스](https://technet.microsoft.com/library/jj943754%28v=exchg.150%29.aspx)를 통해 관리 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f7b4c-224">Outlook add-in installation is managed by a [different process](https://technet.microsoft.com/library/jj943754%28v=exchg.150%29.aspx).</span></span>

<span data-ttu-id="f7b4c-225">조직에서는 Office 스토어에서 새 Office 추가 기능을 다운로드 하지 못하도록 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f7b4c-225">As an organization you may wish to prevent the download of new Office add-ins from the Office Store.</span></span> <span data-ttu-id="f7b4c-226">이를 중앙 집중식 배포와 함께 사용 하 여 조직 내에서 사용자에 게 승인 된 추가 기능만 배포 되도록 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f7b4c-226">This can be used in conjunction with Centralized Deployment to ensure that only organization-approved add-ins are deployed to users within your organization.</span></span>
  
<span data-ttu-id="f7b4c-227">추가 기능 취득 기능을 해제 하려면</span><span class="sxs-lookup"><span data-stu-id="f7b4c-227">To turn off add-in acquisition:</span></span>
  
1. <span data-ttu-id="f7b4c-228">관리 센터 미리 보기에서 **설정** \> [서비스 &amp; 추가 기능](https://go.microsoft.com/fwlink/p/?linkid=2053743) 페이지로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="f7b4c-228">In the admin center, go to the **Settings** \> [Services &amp; add-ins](https://go.microsoft.com/fwlink/p/?linkid=2053743) page.</span></span>
    
3. <span data-ttu-id="f7b4c-229">**사용자가 소유한 앱 및 서비스를**선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="f7b4c-229">Select **User owned apps and services**.</span></span>
    
4. <span data-ttu-id="f7b4c-230">사용자가 Office 스토어에 액세스 하도록 허용 하는 옵션을 선택 취소 합니다.</span><span class="sxs-lookup"><span data-stu-id="f7b4c-230">Clear the option to let users access the Office store.</span></span>

<span data-ttu-id="f7b4c-231">이렇게 하면 모든 사용자가 저장소에서 다음 추가 기능을 취득할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="f7b4c-231">This will prevent all users from acquiring the following add-ins from the store.</span></span>
  
- <span data-ttu-id="f7b4c-232">Word, Excel 및 PowerPoint 2016의 추가 기능:</span><span class="sxs-lookup"><span data-stu-id="f7b4c-232">Add-ins for Word, Excel, and PowerPoint 2016 from:</span></span>
    
  - <span data-ttu-id="f7b4c-233">Windows</span><span class="sxs-lookup"><span data-stu-id="f7b4c-233">Windows</span></span>
    
  - <span data-ttu-id="f7b4c-234">Mac</span><span class="sxs-lookup"><span data-stu-id="f7b4c-234">Mac</span></span>
    
  - <span data-ttu-id="f7b4c-235">사무실</span><span class="sxs-lookup"><span data-stu-id="f7b4c-235">Office</span></span>
    
    
- <span data-ttu-id="f7b4c-236">**Appsource** 내에서 시작 하는 인수</span><span class="sxs-lookup"><span data-stu-id="f7b4c-236">Acquisitions starting within **AppSource**</span></span>
    
- <span data-ttu-id="f7b4c-237">Office 365 내의 추가 기능</span><span class="sxs-lookup"><span data-stu-id="f7b4c-237">Add-ins within Office 365</span></span>
    
<span data-ttu-id="f7b4c-238">저장소에 액세스 하려고 하는 사용자에 게는 **Office 스토어 추가 기능의 개별 가져오기를 차단 하도록 office 365가 구성 되어** 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f7b4c-238">A user who tries to access the store will see the following message: **Sorry, Office 365 has been configured to prevent individual acquisition of Office Store add-ins.**</span></span>
  
<span data-ttu-id="f7b4c-239">다음 버전에서는 Office 스토어의 기능 지원을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f7b4c-239">Support for turning off the Office Store is available in the following versions:</span></span>
  
- <span data-ttu-id="f7b4c-240">Windows: 16.0.9001-현재 사용 가능 합니다.</span><span class="sxs-lookup"><span data-stu-id="f7b4c-240">Windows: 16.0.9001 - Currently available.</span></span>
    
- <span data-ttu-id="f7b4c-241">Mac: 16.10.18011401-현재 사용 가능 합니다.</span><span class="sxs-lookup"><span data-stu-id="f7b4c-241">Mac: 16.10.18011401 - Currently available.</span></span>
    
- <span data-ttu-id="f7b4c-242">iOS: 2.9.18010804-현재 사용 가능 합니다.</span><span class="sxs-lookup"><span data-stu-id="f7b4c-242">iOS: 2.9.18010804 - Currently available.</span></span>
    
- <span data-ttu-id="f7b4c-243">웹-현재 사용 가능 합니다.</span><span class="sxs-lookup"><span data-stu-id="f7b4c-243">The web - Currently available.</span></span>
    
<span data-ttu-id="f7b4c-244">이는 관리자가 중앙 집중식 배포를 사용 하 여 Office 스토어에서 추가 기능을 할당 하는 것을 막지는 못합니다.</span><span class="sxs-lookup"><span data-stu-id="f7b4c-244">This does not prevent an administrator from using Centralized Deployment to assign an add-in from the Office Store.</span></span>
  
<span data-ttu-id="f7b4c-245">사용자가 Microsoft 계정으로 로그인 하지 못하게 하기 위해 조직 계정만 사용 하도록 로그온을 제한할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f7b4c-245">To prevent a user from signing in with a Microsoft account, you can restrict logon to use only the organizational account.</span></span> <span data-ttu-id="f7b4c-246">자세한 내용은 [여기](https://technet.microsoft.com/library/jj683102%28v=office.16%29.aspx)를 확인 하세요.</span><span class="sxs-lookup"><span data-stu-id="f7b4c-246">For more information, look [here](https://technet.microsoft.com/library/jj683102%28v=office.16%29.aspx).</span></span>
 
  
## <a name="minors-and-acquiring-add-ins-from-the-store"></a><span data-ttu-id="f7b4c-247">미성년자가을 사용 하 여 스토어에서 추가 기능 가져오기</span><span class="sxs-lookup"><span data-stu-id="f7b4c-247">Minors and acquiring add-ins from the Store</span></span>

<span data-ttu-id="f7b4c-248">GDPR (일반 데이터 보호 규정)은 실제 5 월 25 일 2018이 되는 유럽 연합 규정입니다.</span><span class="sxs-lookup"><span data-stu-id="f7b4c-248">The General Data Protection Regulation (GDPR) is a European Union regulation that becomes effective May 25, 2018.</span></span> <span data-ttu-id="f7b4c-249">사용자에 게 해당 데이터에 대 한 권한을 부여 하 고 보호 합니다.</span><span class="sxs-lookup"><span data-stu-id="f7b4c-249">It gives users rights to and protection of their data.</span></span> <span data-ttu-id="f7b4c-250">GDPR의 특징 중 하나는 미성년자가가 자신의 부모 또는 보호를 승인 하지 않은 파티에 개인 데이터를 보낼 수 없다는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="f7b4c-250">One of the aspects of the GDPR is that minors cannot have their personal data sent to parties that their parent or guardian hasn't approved.</span></span> <span data-ttu-id="f7b4c-251">약간만 정의 되는 특정 기간은 개인이 있는 지역에 따라 달라 집니다.</span><span class="sxs-lookup"><span data-stu-id="f7b4c-251">The specific age defined as a minor depends on the region where the individual is located.</span></span>
  
<span data-ttu-id="f7b4c-252">자녀 보호에 대 한 법적 규정이 있는 지역에는 미국, 대한민국, 영국 및 유럽 연합 등이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f7b4c-252">Regions that have statutory regulations about parental consent include the United States, South Korea, the United Kingdom, and the European Union.</span></span> <span data-ttu-id="f7b4c-253">이러한 지역의 경우 저장소에서 새 Office 추가 기능을 가져오는 작업과 이전에 획득 한 추가 기능을 실행 하는 것을 Azure Active Directory를 통해 차단 합니다.</span><span class="sxs-lookup"><span data-stu-id="f7b4c-253">For those regions, a minor will be blocked (via Azure Active Directory) from getting any new Office add-ins from the Store and running add-ins that were previously acquired.</span></span> <span data-ttu-id="f7b4c-254">법적 규정이 없는 국가의 경우에는 다운로드 제한이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="f7b4c-254">For countries without statutory regulations, there will be no download restrictions.</span></span>
  
<span data-ttu-id="f7b4c-255">사용자는 Azure Active Directory에 지정 된 데이터를 기반으로 하는 부 버전으로 확인 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f7b4c-255">A user is determined to be a minor based on data specified in Azure Active Directory.</span></span> <span data-ttu-id="f7b4c-256">테 넌 트 관리자는 해당 사용자의 법적 연령 그룹 및 자녀 보호를 선언 합니다.</span><span class="sxs-lookup"><span data-stu-id="f7b4c-256">The tenant admin is responsible for declaring the legal age group and the parental consent for that user.</span></span>
  
<span data-ttu-id="f7b4c-257">특정 추가 기능을 사용 하 여 부모/보호자를 consents 하는 경우 테 넌 트 관리자는 중앙 집중식 배포를 사용 하 여 사용자가 동의 하는 모든 미성년자가에 해당 추가 기능을 배포할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f7b4c-257">If the parent/guardian consents to a minor using a specific add-In, then the tenant admin can use centralized deployment to deploy that add-In to all minors who have consent.</span></span>
  
<span data-ttu-id="f7b4c-258">미성년자가에 대 한 GDPR을 준수 하려면 학교/조직에 Office의 다음 빌드 중 하나가 배포 되었는지 확인 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f7b4c-258">To be GDPR compliant for minors you need to ensure that one of following builds of Office is deployed in your school/organization.</span></span>
  
 <span data-ttu-id="f7b4c-259">**Word, Excel, PowerPoint 및 Project에 대해**다음을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="f7b4c-259">**For Word, Excel, PowerPoint, and Project**:</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="f7b4c-260">**플랫폼**</span><span class="sxs-lookup"><span data-stu-id="f7b4c-260">**Platform**</span></span> <br/> |<span data-ttu-id="f7b4c-261">**빌드 번호**</span><span class="sxs-lookup"><span data-stu-id="f7b4c-261">**Build number**</span></span> <br/> |
|<span data-ttu-id="f7b4c-262">Windows 용 매월 Office 2016 ProPlus</span><span class="sxs-lookup"><span data-stu-id="f7b4c-262">Office 2016 ProPlus Monthly for Windows</span></span>  <br/> |<span data-ttu-id="f7b4c-263">9001.2138</span><span class="sxs-lookup"><span data-stu-id="f7b4c-263">9001.2138</span></span>   <br/> |
|<span data-ttu-id="f7b4c-264">Office 2016 ProPlus 반기</span><span class="sxs-lookup"><span data-stu-id="f7b4c-264">Office 2016 ProPlus Semi-Annual</span></span>  <br/> |<span data-ttu-id="f7b4c-265">8431.2159</span><span class="sxs-lookup"><span data-stu-id="f7b4c-265">8431.2159</span></span>  <br/> |
|<span data-ttu-id="f7b4c-266">Windows 용 Office 2016</span><span class="sxs-lookup"><span data-stu-id="f7b4c-266">Office 2016 for Windows</span></span>  <br/> |<span data-ttu-id="f7b4c-267">16.0.4672.1000</span><span class="sxs-lookup"><span data-stu-id="f7b4c-267">16.0.4672.1000</span></span>  <br/> |
|<span data-ttu-id="f7b4c-268">Windows 용 Office 2013</span><span class="sxs-lookup"><span data-stu-id="f7b4c-268">Office 2013 for Windows</span></span>  <br/> |<span data-ttu-id="f7b4c-269">15.0.5023.1000</span><span class="sxs-lookup"><span data-stu-id="f7b4c-269">15.0.5023.1000</span></span>  <br/> |
|<span data-ttu-id="f7b4c-270">Office 2016 for Mac</span><span class="sxs-lookup"><span data-stu-id="f7b4c-270">Office 2016 for Mac</span></span>  <br/> |<span data-ttu-id="f7b4c-271">16.11.18020200</span><span class="sxs-lookup"><span data-stu-id="f7b4c-271">16.11.18020200</span></span>  <br/> |
|<span data-ttu-id="f7b4c-272">웹에 대 한 Office</span><span class="sxs-lookup"><span data-stu-id="f7b4c-272">Office for the web</span></span>  <br/> |<span data-ttu-id="f7b4c-273">해당 없음</span><span class="sxs-lookup"><span data-stu-id="f7b4c-273">N/A</span></span>  <br/> |
   
 <span data-ttu-id="f7b4c-274">**Outlook의 경우**:</span><span class="sxs-lookup"><span data-stu-id="f7b4c-274">**For Outlook**:</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="f7b4c-275">**플랫폼**</span><span class="sxs-lookup"><span data-stu-id="f7b4c-275">**Platform**</span></span> <br/> |<span data-ttu-id="f7b4c-276">**빌드 번호**</span><span class="sxs-lookup"><span data-stu-id="f7b4c-276">**Build number**</span></span> <br/> |
|<span data-ttu-id="f7b4c-277">Windows 용 Outlook 2016 (MSI)</span><span class="sxs-lookup"><span data-stu-id="f7b4c-277">Outlook 2016 for Windows (MSI)</span></span>  <br/> |<span data-ttu-id="f7b4c-278">TBD 만들기</span><span class="sxs-lookup"><span data-stu-id="f7b4c-278">Build No TBD</span></span>  <br/> |
|<span data-ttu-id="f7b4c-279">C2R (Windows 용 Outlook 2016)</span><span class="sxs-lookup"><span data-stu-id="f7b4c-279">Outlook 2016 for Windows (C2R)</span></span>  <br/> |<span data-ttu-id="f7b4c-280">16.0.9323.1000</span><span class="sxs-lookup"><span data-stu-id="f7b4c-280">16.0.9323.1000</span></span>  <br/> |
|<span data-ttu-id="f7b4c-281">Office 2016 for Mac</span><span class="sxs-lookup"><span data-stu-id="f7b4c-281">Office 2016 for Mac</span></span>  <br/> |<span data-ttu-id="f7b4c-282">16.0.9318.1000</span><span class="sxs-lookup"><span data-stu-id="f7b4c-282">16.0.9318.1000</span></span>  <br/> |
|<span data-ttu-id="f7b4c-283">IOS 용 Outlook 모바일</span><span class="sxs-lookup"><span data-stu-id="f7b4c-283">Outlook mobile for iOS</span></span>  <br/> |<span data-ttu-id="f7b4c-284">2.75.0</span><span class="sxs-lookup"><span data-stu-id="f7b4c-284">2.75.0</span></span>  <br/> |
|<span data-ttu-id="f7b4c-285">Android 용 Outlook 모바일</span><span class="sxs-lookup"><span data-stu-id="f7b4c-285">Outlook mobile for Android</span></span>  <br/> |<span data-ttu-id="f7b4c-286">2.2.145</span><span class="sxs-lookup"><span data-stu-id="f7b4c-286">2.2.145</span></span>  <br/> |
|<span data-ttu-id="f7b4c-287">Outlook.com</span><span class="sxs-lookup"><span data-stu-id="f7b4c-287">Outlook.com</span></span>  <br/> |<span data-ttu-id="f7b4c-288">해당 없음</span><span class="sxs-lookup"><span data-stu-id="f7b4c-288">N/A</span></span>  <br/> |
   
 <span data-ttu-id="f7b4c-289">**Office 2013 요구 사항**</span><span class="sxs-lookup"><span data-stu-id="f7b4c-289">**Office 2013 requirements**</span></span>
  
<span data-ttu-id="f7b4c-290">Windows 용 Word, Excel 및 PowerPoint 2013은 ADAL (Active Directory 인증 라이브러리)을 사용 하는 경우 동일한 사소한 검사를 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="f7b4c-290">Word, Excel, and PowerPoint 2013 for Windows will support the same minor checks if Active Directory Authentication Library (ADAL) is enabled.</span></span> <span data-ttu-id="f7b4c-291">다음에 설명 된 대로 준수에 대 한 두 가지 옵션이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f7b4c-291">There are two options for compliance, as explained next.</span></span>
  
- <span data-ttu-id="f7b4c-292">**ADAL을 사용 하도록 설정**합니다.</span><span class="sxs-lookup"><span data-stu-id="f7b4c-292">**Enable ADAL**.</span></span> <span data-ttu-id="f7b4c-293">이 문서에서는 office [365](https://support.office.com/article/776c0036-66fd-41cb-8928-5495c0f9168a)2013에 대해 ADAL을 사용 하도록 설정 하는 방법에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="f7b4c-293">This article explains how to enable ADAL for Office 2013: [Using Office 365 modern authentication with Office clients](https://support.office.com/article/776c0036-66fd-41cb-8928-5495c0f9168a).</span></span><br/><span data-ttu-id="f7b4c-294">또한 [Windows 장치에서 Office 2013에 대 한 최신 인증 사용](../security-and-compliance/enable-modern-authentication.md)에 설명 된 대로 ADAL을 사용 하도록 레지스트리 키를 설정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f7b4c-294">You also need to set the registry keys to enable ADAL as explained in [Enable Modern Authentication for Office 2013 on Windows devices](../security-and-compliance/enable-modern-authentication.md).</span></span><br/><span data-ttu-id="f7b4c-295">또한 Office 2013에 대 한 다음 4 월 업데이트를 설치 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f7b4c-295">Additionally, you need to install the following April updates for Office 2013:</span></span>
    
  - [<span data-ttu-id="f7b4c-296">Office 2013의 보안 업데이트에 대 한 설명: 2018 년 4 월 10 일</span><span class="sxs-lookup"><span data-stu-id="f7b4c-296">Description of the security update for Office 2013: April 10, 2018</span></span>](https://support.microsoft.com/help/4018330/description-of-the-security-update-for-office-2013-april-10-2018)
    
  - [<span data-ttu-id="f7b4c-297">4 월 3 일, 2018, Office 2013 업데이트 (KB4018333)</span><span class="sxs-lookup"><span data-stu-id="f7b4c-297">April 3, 2018, update for Office 2013 (KB4018333)</span></span>](https://support.microsoft.com/help/4018333/april-3-2018-update-for-office-2013-kb4018333)
    
- <span data-ttu-id="f7b4c-298">**ADAL을 사용 하지 않도록 설정**합니다.</span><span class="sxs-lookup"><span data-stu-id="f7b4c-298">**Don't enable ADAL**.</span></span> <span data-ttu-id="f7b4c-299">Office 2013에서 ADAL을 사용 하도록 설정할 수 없는 경우 그룹 정책을 사용 하 여 office 클라이언트에 대 한 저장소를 해제 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="f7b4c-299">If you're unable to enable ADAL in Office 2013, then our recommendation is to use Group Policy to turn off the Store for the office clients.</span></span> <span data-ttu-id="f7b4c-300">Office 용 앱 설정을 해제 하는 방법에 대 한 정보는 [여기](https://technet.microsoft.com/library/cc178992.aspx)에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f7b4c-300">Information on how to turn off the app for Office settings is located [here](https://technet.microsoft.com/library/cc178992.aspx).</span></span>
    
## <a name="end-user-experience-with-add-ins"></a><span data-ttu-id="f7b4c-301">추가 기능에 대한 최종 사용자 환경</span><span class="sxs-lookup"><span data-stu-id="f7b4c-301">End user experience with add-ins</span></span>

<span data-ttu-id="f7b4c-p137">이제 추가 기능을 배포했으므로 최종 사용자가 Office 응용 프로그램에서 사용을 시작할 수 있습니다([Office 추가 기능 사용 시작](https://support.office.com/article/82e665c4-6700-4b56-a3f3-ef5441996862.aspx) 참조). 추가 기능은 추가 기능에서 지원하는 모든 플랫폼에 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="f7b4c-p137">Now that you've deployed the add-in, your end users can start using it in their Office applications (see [Start using your Office Add-in](https://support.office.com/article/82e665c4-6700-4b56-a3f3-ef5441996862.aspx)). The add-in will appear on all platforms that the add-in supports.</span></span>
  
<span data-ttu-id="f7b4c-p138">추가 기능이 추가 기능 명령을 지원하는 경우 명령은 Office 리본에 나타납니다. 다음 예에서는 **인용 검색** 명령이 **인용** 추가 기능에 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="f7b4c-p138">If the add-in supports add-in commands, the commands appear on the Office ribbon. In the following example, the command **Search Citation** appears for the **Citations** add-in.</span></span> 

![검색 인용이 있는 Office 리본 메뉴](../../media/553b0c0a-65e9-4746-b3b0-8c1b81715a86.png)
  
<span data-ttu-id="f7b4c-307">배포 된 추가 기능이 추가 기능 명령을 지원 하지 않거나 배포한 모든 추가 기능을 보려는 경우 **내 추가 기능**을 통해 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f7b4c-307">If the deployed add-in doesn't support add-in commands or if you want to view all deployed add-ins, you can view them via **My Add-ins**.</span></span> 
  
### <a name="in-word-2016-excel-2016-or-powerpoint-2016"></a><span data-ttu-id="f7b4c-308">Word 2016, Excel 2016 또는 PowerPoint 2016의 경우</span><span class="sxs-lookup"><span data-stu-id="f7b4c-308">In Word 2016, Excel 2016, or PowerPoint 2016</span></span>

1. <span data-ttu-id="f7b4c-309">**내 추가 \> 기능 삽입을**선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="f7b4c-309">Select **Insert \> My Add-ins**.</span></span> 
    
2. <span data-ttu-id="f7b4c-310">Office 추가 기능 창에서 **관리자가 관리함** 탭을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="f7b4c-310">Select the **Admin Managed** tab in the Office Add-ins window.</span></span> 
    
3. <span data-ttu-id="f7b4c-311">이전에 배포한 추가 기능을 두 번 클릭합니다(이 예에서는 **인용** ).</span><span class="sxs-lookup"><span data-stu-id="f7b4c-311">Double-click the add-in you deployed earlier (in this example, **Citations** ).</span></span> <br/><span data-ttu-id="f7b4c-312">![Office 추가 기능 페이지의 관리 관리 탭](../../media/fd36ba81-9882-40f0-9fce-74f991aa97d5.png)</span><span class="sxs-lookup"><span data-stu-id="f7b4c-312">![Admin Managed tab of the Office Add-ins page](../../media/fd36ba81-9882-40f0-9fce-74f991aa97d5.png)</span></span>
  
### <a name="in-outlook"></a><span data-ttu-id="f7b4c-313">Outlook의 경우</span><span class="sxs-lookup"><span data-stu-id="f7b4c-313">In Outlook</span></span>

1. <span data-ttu-id="f7b4c-314">**홈** 리본에서 **추가 기능 가져오기를**선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="f7b4c-314">On the **Home** ribbon, select **Get Add-ins**.</span></span><br/><span data-ttu-id="f7b4c-315">![Outlook의 스토어 단추](../../media/getaddinsicon.png)</span><span class="sxs-lookup"><span data-stu-id="f7b4c-315">![Store button in Outlook](../../media/getaddinsicon.png)</span></span>
  
2. <span data-ttu-id="f7b4c-316">왼쪽 탐색 창에서 **관리-관리** 를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="f7b4c-316">Select **Admin-managed** in the left nav.</span></span>

## <a name="delete-the-add-in"></a><span data-ttu-id="f7b4c-317">추가 기능 삭제</span><span class="sxs-lookup"><span data-stu-id="f7b4c-317">Delete the add-in</span></span>

<span data-ttu-id="f7b4c-318">배포 된 추가 기능을 삭제할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f7b4c-318">You can also delete an add-in that was deployed.</span></span>

1. <span data-ttu-id="f7b4c-319">관리 센터에서 **설정** > **서비스 & 추가** 기능 페이지로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="f7b4c-319">In the admin center, go to the **Settings** > **Services & add-ins** page.</span></span>

2. <span data-ttu-id="f7b4c-320">배포 된 추가 기능을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="f7b4c-320">Select the deployed add-in.</span></span>

3. <span data-ttu-id="f7b4c-321">**추가 기능 삭제**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="f7b4c-321">Click on **Delete Add-In**.</span></span> <span data-ttu-id="f7b4c-322">오른쪽 아래 모서리에 있는 추가 기능 단추를 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="f7b4c-322">Remove the Add-in button on the bottom right corner.</span></span>
4. <span data-ttu-id="f7b4c-323">선택한 항목의 유효성을 검사 하 고 **추가 기능 제거**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="f7b4c-323">Validate your selections, and choose **Remove add-in**.</span></span>
  
## <a name="learn-more"></a><span data-ttu-id="f7b4c-324">자세한 정보</span><span class="sxs-lookup"><span data-stu-id="f7b4c-324">Learn more</span></span>

<span data-ttu-id="f7b4c-325">[Office 추가 기능](https://go.microsoft.com/fwlink/p/?linkid=846362)을 만들고 빌드하는 방법에 대해 자세히 알아보세요.</span><span class="sxs-lookup"><span data-stu-id="f7b4c-325">Learn more about creating and building [Office Add-ins](https://go.microsoft.com/fwlink/p/?linkid=846362).</span></span>
  
<span data-ttu-id="f7b4c-326">[중앙 집중식 배포 PowerShell cmdlet을 사용 하 여 추가 기능을 관리](https://support.office.com/article/94f4e86d-b8e5-42dd-b558-e6092f830ec9)합니다.</span><span class="sxs-lookup"><span data-stu-id="f7b4c-326">[Use Centralized Deployment PowerShell cmdlets to manage add-ins](https://support.office.com/article/94f4e86d-b8e5-42dd-b558-e6092f830ec9).</span></span>
  
[<span data-ttu-id="f7b4c-327">문제 해결: 사용자가 추가 기능을 볼 수 없음</span><span class="sxs-lookup"><span data-stu-id="f7b4c-327">Troubleshoot: User not seeing add-ins</span></span>](https://docs.microsoft.com/office365/troubleshoot/access-management/user-not-seeing-add-ins)
