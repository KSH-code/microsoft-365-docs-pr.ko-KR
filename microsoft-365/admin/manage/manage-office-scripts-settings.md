---
title: Office 스크립트 설정 관리
f1.keywords:
- NOCSH
ms.author: sharik
author: SKjerland
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
search.appverid: MET150
description: 조직의 사용자에 대한 Office 스크립트 설정을 관리하는 방법을 알아보세요.
ms.openlocfilehash: e0cb52c4a8f48ff2310c83ffce61e08a0236ed59
ms.sourcegitcommit: 0936f075a1205b8f8a71a7dd7761a2e2ce6167b3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/19/2021
ms.locfileid: "52572312"
---
# <a name="manage-office-scripts-settings"></a><span data-ttu-id="5ff6c-103">Office 스크립트 설정 관리</span><span class="sxs-lookup"><span data-stu-id="5ff6c-103">Manage Office Scripts settings</span></span>

<span data-ttu-id="5ff6c-104">[Office 스크립트를](/office/dev/scripts)사용하면 웹에서 Excel 스크립트를 녹화, 편집 및 실행하여 작업을 자동화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5ff6c-104">[Office Scripts](/office/dev/scripts)‎ allows users to automate tasks by recording, editing, and running scripts in ‎Excel‎ on the web.</span></span> <span data-ttu-id="5ff6c-105">Office 스크립트는 Power Automate 함께 작동하며 사용자는 Excel 온라인(비즈니스) 커넥터를 사용하여 통합 문서에서 스크립트를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="5ff6c-105">‎Office Scripts‎ works with Power Automate, and users run scripts on workbooks by using the ‎Excel‎ Online (Business) connector.</span></span> <span data-ttu-id="5ff6c-106">Microsoft 365 관리자는 Microsoft 365 관리자 센터에서 Office 스크립트 설정을 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5ff6c-106">Microsoft 365 admins can manage Office Scripts settings from the Microsoft 365 admin center.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="5ff6c-107">시작하기 전에</span><span class="sxs-lookup"><span data-stu-id="5ff6c-107">Before you begin</span></span>

- <span data-ttu-id="5ff6c-108">Office 스크립트 설정을 관리하려면 글로벌 관리자여야 합니다. 자세한 내용은 [관리자 역할 정보](../add-users/about-admin-roles.md)중을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="5ff6c-108">To manage Office Scripts settings, you must be a Global admin. For more information, see [About admin roles](../add-users/about-admin-roles.md).</span></span>

- <span data-ttu-id="5ff6c-109">조직의 사용자가 다음 계획 중 하나와 같은 Office 데스크톱 앱에 대한 액세스를 포함하는 Microsoft 365 또는 Office 365 상업용 또는 EDU 계획에 대한 유효한 라이선스를 가지고 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="5ff6c-109">Ensure users in your organization have a valid license for a Microsoft 365 or Office 365 commercial or EDU plan that includes access to Office desktop apps, such as one of the following plans:</span></span>

    - <span data-ttu-id="5ff6c-110">Microsoft 365 Business Standard</span><span class="sxs-lookup"><span data-stu-id="5ff6c-110">Microsoft 365 Business Standard</span></span>
    - <span data-ttu-id="5ff6c-111">비즈니스용 Microsoft 365 앱</span><span class="sxs-lookup"><span data-stu-id="5ff6c-111">Microsoft 365 Apps for business</span></span>
    - <span data-ttu-id="5ff6c-112">엔터프라이즈용 Microsoft 365 앱</span><span class="sxs-lookup"><span data-stu-id="5ff6c-112">Microsoft 365 Apps for enterprise</span></span>
    - <span data-ttu-id="5ff6c-113">Office 365 E3</span><span class="sxs-lookup"><span data-stu-id="5ff6c-113">Office 365 E3</span></span>
    - <span data-ttu-id="5ff6c-114">Office 365 E5</span><span class="sxs-lookup"><span data-stu-id="5ff6c-114">Office 365 E5</span></span>
    - <span data-ttu-id="5ff6c-115">Office 365 A3</span><span class="sxs-lookup"><span data-stu-id="5ff6c-115">Office 365 A3</span></span>
    - <span data-ttu-id="5ff6c-116">Office 365 A5</span><span class="sxs-lookup"><span data-stu-id="5ff6c-116">Office 365 A5</span></span>

## <a name="manage-availability-of-office-scripts-and-sharing-of-scripts"></a><span data-ttu-id="5ff6c-117">Office 스크립트의 가용성 관리 및 스크립트 공유</span><span class="sxs-lookup"><span data-stu-id="5ff6c-117">Manage availability of Office Scripts and sharing of scripts</span></span>

1. <span data-ttu-id="5ff6c-118">Microsoft 365 관리 센터에서 **설정** \> **조직 설정** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2053743" target="_blank">서비스</a> 탭으로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="5ff6c-118">In the Microsoft 365 admin center, go to the **Settings** \> **Org settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2053743" target="_blank">Services</a> tab.</span></span>

2. <span data-ttu-id="5ff6c-119">**Office 스크립트를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="5ff6c-119">Select **Office Scripts**.</span></span>

3. <span data-ttu-id="5ff6c-120">Office 스크립트는 기본적으로 켜져 있으며 조직의 모든 사용자가 기능에 액세스하여 사용하고 스크립트를 공유할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5ff6c-120">Office Scripts is turned on by default, and everyone in your organization can access and use the feature and share scripts.</span></span> <span data-ttu-id="5ff6c-121">조직에 대한 스크립트Office 끄려면 사용자가 **확인란에서 작업을 자동화할 웹용 Excel** 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5ff6c-121">To turn off Office Scripts for your organization, clear the **Let users automate their tasks in Excel on the web** check box.</span></span>

4. <span data-ttu-id="5ff6c-122">이전에 조직에 대한 스크립트Office를 끄고 다시 켜려면 **사용자가 웹용 Excel 작업을 자동화한** 다음 기능에 액세스하고 사용할 수 있는 사용자를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="5ff6c-122">If you previously turned off Office Scripts for your organization and you want to turn it back on, select **Let users automate their tasks in Excel on the web**, and then specify who can access and use the feature:</span></span>

    - <span data-ttu-id="5ff6c-123">조직의 모든 사용자가 Office 스크립트에 액세스하고 사용할 수 있도록 하려면 모든 사람(기본값)을 선택해제합니다. </span><span class="sxs-lookup"><span data-stu-id="5ff6c-123">To allow all users in your organization to access and use Office Scripts, leave **Everyone** (the default) selected.</span></span>

    - <span data-ttu-id="5ff6c-124">특정 그룹의 구성원만 Office 스크립트에 액세스하고 사용할 수 있도록 하려면 **특정 그룹을** 선택한 다음 그룹의 이름이나 이메일 별칭을 입력하여 허용 목록에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="5ff6c-124">To allow only members of a specific group to access and use Office Scripts, select **Specific group**, and then enter the name or email alias of the group to add it to the allow list.</span></span> <span data-ttu-id="5ff6c-125">허용 목록에 하나의 그룹만 추가할 수 있으며 다음 유형 중 하나여야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5ff6c-125">You may add only one group to the allow list, and it must be one of the following types:</span></span>
        - <span data-ttu-id="5ff6c-126">Microsoft 365 그룹</span><span class="sxs-lookup"><span data-stu-id="5ff6c-126">Microsoft 365 group</span></span>
        - <span data-ttu-id="5ff6c-127">배포 그룹</span><span class="sxs-lookup"><span data-stu-id="5ff6c-127">Distribution group</span></span>
        - <span data-ttu-id="5ff6c-128">보안 그룹</span><span class="sxs-lookup"><span data-stu-id="5ff6c-128">Security group</span></span>
        - <span data-ttu-id="5ff6c-129">메일 사용 가능 보안 그룹</span><span class="sxs-lookup"><span data-stu-id="5ff6c-129">Mail-enabled security group</span></span>
    
        <span data-ttu-id="5ff6c-130">다양한 유형의 그룹에 대해 자세히 알아보려면 [그룹 비교를](../create-groups/compare-groups.md)참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="5ff6c-130">To learn more about the different types of groups, see [Compare groups](../create-groups/compare-groups.md).</span></span>

5. <span data-ttu-id="5ff6c-131">스크립트에 Office 액세스할 수 있는 사용자가 조직의 다른 사용자와 스크립트를 공유할 수 있도록 **하려면 Office 스크립트에 액세스할 수 있는 사용자가 조직의 다른 사용자와 스크립트를 공유하도록** 합니다.</span><span class="sxs-lookup"><span data-stu-id="5ff6c-131">To allow users with access to Office Scripts to share their scripts with others in your organization, select **Let users with access to Office Scripts share their scripts with others in the organization**.</span></span> <span data-ttu-id="5ff6c-132">조직 외부의 스크립트를 공유하는 것은 허용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="5ff6c-132">Sharing scripts outside of an organization is not allowed.</span></span>
 
    > [!NOTE]
    > <span data-ttu-id="5ff6c-133">나중에 조직에 대한 스크립트 공유를 해제하면 사용자는 이전에 공유된 스크립트를 계속 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5ff6c-133">If you later turn off script sharing for your organization, users will still be able to run previously-shared scripts.</span></span>
 
6. <span data-ttu-id="5ff6c-134">스크립트에 액세스할 수 Office 있는 사용자를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="5ff6c-134">Specify which users with access to Office Scripts can share their scripts:</span></span>
    
    - <span data-ttu-id="5ff6c-135">Office 스크립트에 액세스할 수 있는 모든 사용자가 스크립트를 공유할 수 있도록 하려면 모든 사용자(기본값)를 선택해제합니다. </span><span class="sxs-lookup"><span data-stu-id="5ff6c-135">To allow all users with access to Office Scripts to share their scripts, leave **Everyone** (the default) selected.</span></span>

    - <span data-ttu-id="5ff6c-136">스크립트에 액세스할 Office 액세스할 수 있는 특정 그룹의 구성원만 스크립트를 공유할 수 있도록 하려면 **특정 그룹을** 선택한 다음 그룹의 이름 또는 이메일 별칭을 입력하여 허용 목록에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="5ff6c-136">To allow only members of a specific group with access to Office Scripts to share their scripts, select **Specific group**, and then enter the name or email alias of the group to add it to the allow list.</span></span> <span data-ttu-id="5ff6c-137">허용 목록에 하나의 그룹만 추가할 수 있으며 다음 유형 중 하나여야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5ff6c-137">You may add only one group to the allow list, and it must be one of the following types:</span></span>
        - <span data-ttu-id="5ff6c-138">Microsoft 365 그룹</span><span class="sxs-lookup"><span data-stu-id="5ff6c-138">Microsoft 365 group</span></span>
        - <span data-ttu-id="5ff6c-139">배포 그룹</span><span class="sxs-lookup"><span data-stu-id="5ff6c-139">Distribution group</span></span>
        - <span data-ttu-id="5ff6c-140">보안 그룹</span><span class="sxs-lookup"><span data-stu-id="5ff6c-140">Security group</span></span>
        - <span data-ttu-id="5ff6c-141">메일 사용 가능 보안 그룹</span><span class="sxs-lookup"><span data-stu-id="5ff6c-141">Mail-enabled security group</span></span>
    
        <span data-ttu-id="5ff6c-142">다양한 유형의 그룹에 대해 자세히 알아보려면 [그룹 비교를](../create-groups/compare-groups.md)참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="5ff6c-142">To learn more about the different types of groups, see [Compare groups](../create-groups/compare-groups.md).</span></span>

7. <span data-ttu-id="5ff6c-143">사용자가 Power Automate 흐름 내에서 Office 스크립트를 실행할 수 있도록 하려면 **Office 스크립트에 액세스할 수 있는 사용자가 Power Automate 스크립트를 실행하도록 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="5ff6c-143">To allow users to run their Office Scripts inside Power Automate flows, select **Let users with access to Office Scripts run their scripts with Power Automate**.</span></span> <span data-ttu-id="5ff6c-144">이를 통해 사용자는 [Excel 온라인(비즈니스) 커넥터의](/connectors/excelonlinebusiness) **실행 스크립트** 옵션으로 흐름 단계를 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5ff6c-144">This allows users to add flow steps with the [Excel Online (Business) Connector's](/connectors/excelonlinebusiness) **Run script** option.</span></span>

    - <span data-ttu-id="5ff6c-145">스크립트에 액세스할 수 Office 있는 모든 사용자가 흐름에서 스크립트를 사용하도록 허용하려면 모든 사람(기본값)을 선택합니다. </span><span class="sxs-lookup"><span data-stu-id="5ff6c-145">To allow all users with access to Office Scripts to use their scripts in flows, leave **Everyone** (the default) selected.</span></span>

    - <span data-ttu-id="5ff6c-146">스크립트에 액세스할 수 Office 특정 그룹의 구성원만 흐름에서 스크립트를 사용하도록 허용하려면 **특정 그룹을** 선택한 다음 그룹의 이름 또는 이메일 별칭을 입력하여 허용 목록에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="5ff6c-146">To allow only members of a specific group with access to Office Scripts to use their scripts in flows, select **Specific group**, and then enter the name or email alias of the group to add it to the allow list.</span></span> <span data-ttu-id="5ff6c-147">허용 목록에 하나의 그룹만 추가할 수 있으며 다음 유형 중 하나여야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5ff6c-147">You may add only one group to the allow list, and it must be one of the following types:</span></span>
        - <span data-ttu-id="5ff6c-148">Microsoft 365 그룹</span><span class="sxs-lookup"><span data-stu-id="5ff6c-148">Microsoft 365 group</span></span>
        - <span data-ttu-id="5ff6c-149">배포 그룹</span><span class="sxs-lookup"><span data-stu-id="5ff6c-149">Distribution group</span></span>
        - <span data-ttu-id="5ff6c-150">보안 그룹</span><span class="sxs-lookup"><span data-stu-id="5ff6c-150">Security group</span></span>
        - <span data-ttu-id="5ff6c-151">메일 사용 가능 보안 그룹</span><span class="sxs-lookup"><span data-stu-id="5ff6c-151">Mail-enabled security group</span></span>

        <span data-ttu-id="5ff6c-152">다양한 유형의 그룹에 대해 자세히 알아보려면 [그룹 비교를](../create-groups/compare-groups.md)참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="5ff6c-152">To learn more about the different types of groups, see [Compare groups](../create-groups/compare-groups.md).</span></span>

    - <span data-ttu-id="5ff6c-153">Power Automate Office 스크립트를 사용하는 방법에 대해 자세히 알아보려면 [Power Automate Office 스크립트 실행을](/office/dev/scripts/develop/power-automate-integration)참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="5ff6c-153">To learn more about using Office Scripts with Power Automate, see [Run Office Scripts with Power Automate](/office/dev/scripts/develop/power-automate-integration).</span></span>

8. <span data-ttu-id="5ff6c-154">**저장** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="5ff6c-154">Select **Save**.</span></span>

    <span data-ttu-id="5ff6c-155">스크립트 설정을 Office 변경하려면 최대 48시간이 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5ff6c-155">It can take up to 48 hours for changes to Office Scripts settings to take effect.</span></span>

## <a name="next-steps"></a><span data-ttu-id="5ff6c-156">다음 단계</span><span class="sxs-lookup"><span data-stu-id="5ff6c-156">Next steps</span></span>

<span data-ttu-id="5ff6c-157">Office 스크립트는 Power Automate 함께 작동하므로 사용자가 스크립트를 Office 사용하는 동안 조직의 데이터가 보호되도록 기존 DLP(데이터 손실 방지) 정책을 검토하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="5ff6c-157">Because Office Scripts works with Power Automate, we recommend that you review your existing data loss prevention (DLP) policies to ensure your organization's data remains protected while users use ‎Office Scripts‎.</span></span> <span data-ttu-id="5ff6c-158">자세한 내용은 [DLP(데이터 손실 방지) 정책을](/power-automate/prevent-data-loss)참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="5ff6c-158">For more information, see [Data loss prevention (DLP) policies](/power-automate/prevent-data-loss).</span></span>

## <a name="related-content"></a><span data-ttu-id="5ff6c-159">관련 콘텐츠</span><span class="sxs-lookup"><span data-stu-id="5ff6c-159">Related content</span></span>

<span data-ttu-id="5ff6c-160">[Office 스크립트 기술 설명서(링크](/office/dev/scripts/) 페이지)</span><span class="sxs-lookup"><span data-stu-id="5ff6c-160">[Office Scripts technical documentation](/office/dev/scripts/) (link page)</span></span>\
<span data-ttu-id="5ff6c-161">[Excel Office 스크립트](https://support.microsoft.com/office/9fbe283d-adb8-4f13-a75b-a81c6baf163a) 소개(기사)</span><span class="sxs-lookup"><span data-stu-id="5ff6c-161">[Introduction to Office Scripts in Excel](https://support.microsoft.com/office/9fbe283d-adb8-4f13-a75b-a81c6baf163a) (article)</span></span>\
<span data-ttu-id="5ff6c-162">[웹(문서)에 대한 Excel Office 스크립트 공유\](https://support.microsoft.com/office/226eddbc-3a44-4540-acfe-fccda3d1122b)</span><span class="sxs-lookup"><span data-stu-id="5ff6c-162">[Sharing Office Scripts in Excel for the Web](https://support.microsoft.com/office/226eddbc-3a44-4540-acfe-fccda3d1122b) (article)\</span></span>
<span data-ttu-id="5ff6c-163">[웹용 Excel Office 스크립트를 기록, 편집 및](/office/dev/scripts/tutorials/excel-tutorial) 만듭니다(문서)</span><span class="sxs-lookup"><span data-stu-id="5ff6c-163">[Record, edit, and create Office Scripts in Excel on the web](/office/dev/scripts/tutorials/excel-tutorial) (article)</span></span>
