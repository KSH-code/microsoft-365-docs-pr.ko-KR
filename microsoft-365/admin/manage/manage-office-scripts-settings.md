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
description: 조직의 사용자에 대한 Office 스크립트 설정을 관리하는 방법에 대해 자세히 알아보습니다.
ms.openlocfilehash: 75d0a9d9e98652fc11eab7e8a7d6c826be031f6e
ms.sourcegitcommit: 50f10d83fa21db8572adab90784146e5231e3321
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/30/2021
ms.locfileid: "50058426"
---
# <a name="manage-office-scripts-settings"></a><span data-ttu-id="8e373-103">Office 스크립트 설정 관리</span><span class="sxs-lookup"><span data-stu-id="8e373-103">Manage Office Scripts settings</span></span>

<span data-ttu-id="8e373-104">Office 스크립트를 사용하면 웹에서 Excel에서 스크립트를 기록, 편집 및 실행하여 작업을 자동화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8e373-104">Office Scripts‎ allows users to automate tasks by recording, editing, and running scripts in ‎Excel‎ on the web.</span></span> <span data-ttu-id="8e373-105">Office 스크립트는 Power Automate와 함께 작동하며 사용자는 Excel Online(비즈니스) 커넥터를 사용하여 통합 문서에서 스크립트를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="8e373-105">‎Office Scripts‎ works with Power Automate, and users run scripts on workbooks by using the ‎Excel‎ Online (Business) connector.</span></span> <span data-ttu-id="8e373-106">Microsoft 365 관리자는 Microsoft 365 관리 센터에서 Office 스크립트 설정을 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8e373-106">Microsoft 365 admins can manage Office Scripts settings from the Microsoft 365 admin center.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="8e373-107">시작하기 전에</span><span class="sxs-lookup"><span data-stu-id="8e373-107">Before you begin</span></span>

- <span data-ttu-id="8e373-108">Office 스크립트 설정을 관리하려면 전역 관리자 되어야 합니다. 자세한 내용은 관리자 [역할에 대한 정보를 참조하세요.](../add-users/about-admin-roles.md)</span><span class="sxs-lookup"><span data-stu-id="8e373-108">To manage Office Scripts settings, you must be a Global admin. For more information, see [About admin roles](../add-users/about-admin-roles.md).</span></span>

- <span data-ttu-id="8e373-109">조직의 사용자에게 다음 계획 중 하나와 같은 Office 데스크톱 앱에 대한 액세스가 포함된 Microsoft 365 또는 Office 365 상업용 또는 EDU 요금제에 대한 유효한 라이선스가 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8e373-109">Ensure users in your organization have a valid license for a Microsoft 365 or Office 365 commercial or EDU plan that includes access to Office desktop apps, such as one of the following plans:</span></span>

    - <span data-ttu-id="8e373-110">Microsoft 365 Business Standard</span><span class="sxs-lookup"><span data-stu-id="8e373-110">Microsoft 365 Business Standard</span></span>
    - <span data-ttu-id="8e373-111">비즈니스용 Microsoft 365 앱</span><span class="sxs-lookup"><span data-stu-id="8e373-111">Microsoft 365 Apps for business</span></span>
    - <span data-ttu-id="8e373-112">엔터프라이즈용 Microsoft 365 앱</span><span class="sxs-lookup"><span data-stu-id="8e373-112">Microsoft 365 Apps for enterprise</span></span>
    - <span data-ttu-id="8e373-113">Office 365 E3</span><span class="sxs-lookup"><span data-stu-id="8e373-113">Office 365 E3</span></span>
    - <span data-ttu-id="8e373-114">Office 365 E5</span><span class="sxs-lookup"><span data-stu-id="8e373-114">Office 365 E5</span></span>
    - <span data-ttu-id="8e373-115">Office 365 A3</span><span class="sxs-lookup"><span data-stu-id="8e373-115">Office 365 A3</span></span>
    - <span data-ttu-id="8e373-116">Office 365 A5</span><span class="sxs-lookup"><span data-stu-id="8e373-116">Office 365 A5</span></span>

## <a name="manage-availability-of-office-scripts-and-sharing-of-scripts"></a><span data-ttu-id="8e373-117">Office 스크립트의 가용성 및 스크립트 공유 관리</span><span class="sxs-lookup"><span data-stu-id="8e373-117">Manage availability of Office Scripts and sharing of scripts</span></span>

1. <span data-ttu-id="8e373-118">Microsoft 365 관리 센터에서 설정  \> **Org 설정** 서비스 \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2053743" target="_blank">탭으로</a> 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="8e373-118">In the Microsoft 365 admin center, go to the **Settings** \> **Org settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2053743" target="_blank">Services</a> tab.</span></span>

2. <span data-ttu-id="8e373-119">**Office 스크립트를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="8e373-119">Select **Office Scripts**.</span></span>

3. <span data-ttu-id="8e373-120">Office 스크립트는 기본적으로 설정되어 있으며 조직의 모든 사람이 해당 기능에 액세스하여 사용하여 스크립트를 공유할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8e373-120">Office Scripts is turned on by default, and everyone in your organization can access and use the feature and share scripts.</span></span> <span data-ttu-id="8e373-121">조직에 대한 Office 스크립트를 해제하기 위해 사용자가 **웹에서 Excel에서** 작업을 자동화할 수 있도록 선택을 취소합니다.</span><span class="sxs-lookup"><span data-stu-id="8e373-121">To turn off Office Scripts for your organization, clear the **Let users automate their tasks in Excel on the web** check box.</span></span>

4. <span data-ttu-id="8e373-122">이전에 조직의 Office 스크립트를 해제한 후 다시 설정하려면 사용자가 **웹에서 Excel에서** 작업을 자동화할 수 있도록 선택한 다음 기능에 액세스하고 사용할 수 있는 사용자를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="8e373-122">If you previously turned off Office Scripts for your organization and you want to turn it back on, select **Let users automate their tasks in Excel on the web**, and then specify who can access and use the feature:</span></span>

    - <span data-ttu-id="8e373-123">조직의 모든 사용자가 Office 스크립트에 액세스하고 사용할  수 있도록 허용하기 위해 모든 사용자(기본값)를 선택된 그대로 두면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8e373-123">To allow all users in your organization to access and use Office Scripts, leave **Everyone** (the default) selected.</span></span>

    - <span data-ttu-id="8e373-124">특정 그룹의 구성원만 Office 스크립트에 액세스하고 사용할 수 있도록 허용하려면 특정 그룹을 선택한 다음 그룹의 이름 또는 전자 메일 별칭을 입력하여 허용 목록에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="8e373-124">To allow only members of a specific group to access and use Office Scripts, select **Specific group**, and then enter the name or email alias of the group to add it to the allow list.</span></span> <span data-ttu-id="8e373-125">허용 목록에 그룹 하나만 추가할 수 있으며 다음 유형 중 하나에 해당해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8e373-125">You may add only one group to the allow list, and it must be one of the following types:</span></span>
        - <span data-ttu-id="8e373-126">Microsoft 365 그룹</span><span class="sxs-lookup"><span data-stu-id="8e373-126">Microsoft 365 group</span></span>
        - <span data-ttu-id="8e373-127">메일 그룹</span><span class="sxs-lookup"><span data-stu-id="8e373-127">Distribution group</span></span>
        - <span data-ttu-id="8e373-128">보안 그룹</span><span class="sxs-lookup"><span data-stu-id="8e373-128">Security group</span></span>
        - <span data-ttu-id="8e373-129">메일 사용 가능 보안 그룹</span><span class="sxs-lookup"><span data-stu-id="8e373-129">Mail-enabled security group</span></span>
    
        <span data-ttu-id="8e373-130">다양한 유형의 그룹에 대한 자세한 내용은 [그룹 비교를 참조합니다.](../create-groups/compare-groups.md)</span><span class="sxs-lookup"><span data-stu-id="8e373-130">To learn more about the different types of groups, see [Compare groups](../create-groups/compare-groups.md).</span></span>

5. <span data-ttu-id="8e373-131">Office 스크립트에 액세스할 수 있는 사용자가 조직의 다른 사용자와 스크립트를 공유할 수 있도록 허용하려면 Office 스크립트에 액세스할 수 있는 사용자가 조직의 다른 사용자와 스크립트를 공유할 수 있도록 **합니다.**</span><span class="sxs-lookup"><span data-stu-id="8e373-131">To allow users with access to Office Scripts to share their scripts with others in your organization, select **Let users with access to Office Scripts share their scripts with others in the organization**.</span></span> <span data-ttu-id="8e373-132">조직 외부의 스크립트 공유는 허용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="8e373-132">Sharing scripts outside of an organization is not allowed.</span></span>
 
    > [!NOTE]
    > <span data-ttu-id="8e373-133">나중에 조직에 대한 스크립트 공유를 해제하는 경우 사용자는 이전에 공유한 스크립트를 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8e373-133">If you later turn off script sharing for your organization, users will still be able to run previously-shared scripts.</span></span>
 
6. <span data-ttu-id="8e373-134">Office 스크립트에 액세스할 수 있는 사용자를 지정하여 스크립트를 공유할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8e373-134">Specify which users with access to Office Scripts can share their scripts:</span></span>
    
    - <span data-ttu-id="8e373-135">Office 스크립트에 액세스할 수 있는 모든 사용자가 스크립트를  공유할 수 있도록 허용하기 위해 모든 사용자(기본값)를 선택된 그대로 남겨 두면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8e373-135">To allow all users with access to Office Scripts to share their scripts, leave **Everyone** (the default) selected.</span></span>

    - <span data-ttu-id="8e373-136">Office 스크립트에 액세스할 수 있는 특정 그룹의 구성원만 스크립트를 공유할 수 있도록 허용하려면 특정 그룹을 선택한 다음 그룹의 이름 또는 전자 메일 별칭을 입력하여 허용 목록에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="8e373-136">To allow only members of a specific group with access to Office Scripts to share their scripts, select **Specific group**, and then enter the name or email alias of the group to add it to the allow list.</span></span> <span data-ttu-id="8e373-137">허용 목록에 그룹 하나만 추가할 수 있으며 다음 유형 중 하나에 해당해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8e373-137">You may add only one group to the allow list, and it must be one of the following types:</span></span>
        - <span data-ttu-id="8e373-138">Microsoft 365 그룹</span><span class="sxs-lookup"><span data-stu-id="8e373-138">Microsoft 365 group</span></span>
        - <span data-ttu-id="8e373-139">메일 그룹</span><span class="sxs-lookup"><span data-stu-id="8e373-139">Distribution group</span></span>
        - <span data-ttu-id="8e373-140">보안 그룹</span><span class="sxs-lookup"><span data-stu-id="8e373-140">Security group</span></span>
        - <span data-ttu-id="8e373-141">메일 사용 가능 보안 그룹</span><span class="sxs-lookup"><span data-stu-id="8e373-141">Mail-enabled security group</span></span>
    
        <span data-ttu-id="8e373-142">다양한 유형의 그룹에 대한 자세한 내용은 [그룹 비교를 참조합니다.](../create-groups/compare-groups.md)</span><span class="sxs-lookup"><span data-stu-id="8e373-142">To learn more about the different types of groups, see [Compare groups](../create-groups/compare-groups.md).</span></span>

7. <span data-ttu-id="8e373-143">사용자가 Power Automate 흐름 내에서 Office 스크립트를 실행할 수 있도록 허용하려면 Office 스크립트에 액세스할 수 있는 사용자가 Power Automate를 사용하여 스크립트를 실행하도록 **허용을 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="8e373-143">To allow users to run their Office Scripts inside Power Automate flows, select **Let users with access to Office Scripts run their scripts with Power Automate**.</span></span> <span data-ttu-id="8e373-144">이를 통해 사용자는 [Excel Online(비즈니스) 커넥터의](/connectors/excelonlinebusiness) 실행 스크립트 옵션을 사용하여 흐름 단계를 추가할 **수** 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8e373-144">This allows users to add flow steps with the [Excel Online (Business) Connector's](/connectors/excelonlinebusiness) **Run script** option.</span></span>

    - <span data-ttu-id="8e373-145">Office 스크립트에 액세스할 수 있는 모든 사용자가 흐름에서 스크립트를  사용할 수 있도록 허용하기 위해 모든 사용자(기본값)를 선택된 그대로 남겨 두면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8e373-145">To allow all users with access to Office Scripts to use their scripts in flows, leave **Everyone** (the default) selected.</span></span>

    - <span data-ttu-id="8e373-146">Office 스크립트에 액세스할 수 있는 특정 그룹의 구성원만 흐름에서 스크립트를 사용할 수 있도록 허용하려면 특정 그룹을 선택한 다음 그룹의 이름 또는 전자 메일 별칭을 입력하여 허용 목록에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="8e373-146">To allow only members of a specific group with access to Office Scripts to use their scripts in flows, select **Specific group**, and then enter the name or email alias of the group to add it to the allow list.</span></span> <span data-ttu-id="8e373-147">허용 목록에 그룹 하나만 추가할 수 있으며 다음 유형 중 하나에 해당해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8e373-147">You may add only one group to the allow list, and it must be one of the following types:</span></span>
        - <span data-ttu-id="8e373-148">Microsoft 365 그룹</span><span class="sxs-lookup"><span data-stu-id="8e373-148">Microsoft 365 group</span></span>
        - <span data-ttu-id="8e373-149">메일 그룹</span><span class="sxs-lookup"><span data-stu-id="8e373-149">Distribution group</span></span>
        - <span data-ttu-id="8e373-150">보안 그룹</span><span class="sxs-lookup"><span data-stu-id="8e373-150">Security group</span></span>
        - <span data-ttu-id="8e373-151">메일 사용 가능 보안 그룹</span><span class="sxs-lookup"><span data-stu-id="8e373-151">Mail-enabled security group</span></span>

        <span data-ttu-id="8e373-152">다양한 유형의 그룹에 대한 자세한 내용은 [그룹 비교를 참조합니다.](../create-groups/compare-groups.md)</span><span class="sxs-lookup"><span data-stu-id="8e373-152">To learn more about the different types of groups, see [Compare groups](../create-groups/compare-groups.md).</span></span>

    - <span data-ttu-id="8e373-153">데이터 손실 방지 정책이 영향을 미칠 수 있는 방법을 포함하여 Power Automate에서 Office 스크립트를 사용하는 방법에 대한 자세한 내용은 [Power Automate를](/office/dev/scripts/develop/power-automate-integration)사용하여 Office 스크립트 실행을 참조합니다.</span><span class="sxs-lookup"><span data-stu-id="8e373-153">To learn more about using Office Scripts with Power Automate, including how your data loss prevention policies may be impacted, see [Run Office Scripts with Power Automate](/office/dev/scripts/develop/power-automate-integration).</span></span>

8. <span data-ttu-id="8e373-154">**저장** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="8e373-154">Select **Save**.</span></span>

    <span data-ttu-id="8e373-155">Office 스크립트 설정 변경 내용을 적용하는 데 최대 48시간이 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8e373-155">It can take up to 48 hours for changes to Office Scripts settings to take effect.</span></span>

## <a name="next-steps"></a><span data-ttu-id="8e373-156">다음 단계</span><span class="sxs-lookup"><span data-stu-id="8e373-156">Next steps</span></span>

<span data-ttu-id="8e373-157">Office 스크립트는 Power Automate와 함께 작동하기 때문에 사용자가 Office 스크립트를 사용하는 동안 조직의 데이터가 보호되도록 기존 DLP(데이터 손실 방지) 정책을 검토하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="8e373-157">Because Office Scripts works with Power Automate, we recommend that you review your existing data loss prevention (DLP) policies to ensure your organization's data remains protected while users use ‎Office Scripts‎.</span></span> <span data-ttu-id="8e373-158">자세한 내용은 [DLP(데이터 손실 방지) 정책을 참조하세요.](/power-automate/prevent-data-loss)</span><span class="sxs-lookup"><span data-stu-id="8e373-158">For more information, see [Data loss prevention (DLP) policies](/power-automate/prevent-data-loss).</span></span>

## <a name="related-content"></a><span data-ttu-id="8e373-159">관련 콘텐츠</span><span class="sxs-lookup"><span data-stu-id="8e373-159">Related content</span></span>

<span data-ttu-id="8e373-160">[Office 스크립트 기술 설명서(링크](/office/dev/scripts/) 페이지)</span><span class="sxs-lookup"><span data-stu-id="8e373-160">[Office Scripts technical documentation](/office/dev/scripts/) (link page)</span></span>\
<span data-ttu-id="8e373-161">[Excel의 Office 스크립트](https://support.microsoft.com/office/9fbe283d-adb8-4f13-a75b-a81c6baf163a) 소개(문서)</span><span class="sxs-lookup"><span data-stu-id="8e373-161">[Introduction to Office Scripts in Excel](https://support.microsoft.com/office/9fbe283d-adb8-4f13-a75b-a81c6baf163a) (article)</span></span>\
<span data-ttu-id="8e373-162">[Excel에서 웹용 Office 스크립트](https://support.microsoft.com/office/226eddbc-3a44-4540-acfe-fccda3d1122b) 공유(문서)</span><span class="sxs-lookup"><span data-stu-id="8e373-162">[Sharing Office Scripts in Excel for the Web](https://support.microsoft.com/office/226eddbc-3a44-4540-acfe-fccda3d1122b) (article)</span></span>\
<span data-ttu-id="8e373-163">[웹에서 Excel에서 Office 스크립트 기록,](/office/dev/scripts/tutorials/excel-tutorial) 편집 및 만들기(문서)</span><span class="sxs-lookup"><span data-stu-id="8e373-163">[Record, edit, and create Office Scripts in Excel on the web](/office/dev/scripts/tutorials/excel-tutorial) (article)</span></span>
