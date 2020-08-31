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
description: 조직의 사용자에 대 한 Office 스크립트 설정을 관리 하는 방법을 알아봅니다.
ms.openlocfilehash: 12a80f277f6d17a8e7f5228f6948e70b7a93be11
ms.sourcegitcommit: 97ef8f846939c3d31bb0638edf07bb89463ace0b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/28/2020
ms.locfileid: "47300839"
---
# <a name="manage-office-scripts-settings"></a><span data-ttu-id="8a082-103">Office 스크립트 설정 관리</span><span class="sxs-lookup"><span data-stu-id="8a082-103">Manage Office Scripts settings</span></span>

<span data-ttu-id="8a082-104">Office 스크립트를 사용 하면 사용자가 웹에서 Excel에서 스크립트를 기록, 편집 및 실행 하 여 작업을 자동화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8a082-104">Office Scripts‎ allows users to automate tasks by recording, editing, and running scripts in ‎Excel‎ on the web.</span></span> <span data-ttu-id="8a082-105">Office 스크립트는 전원 자동화와 함께 작동 하며, 사용자는 Excel Online (Business) 커넥터를 사용 하 여 통합 문서에서 스크립트를 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="8a082-105">‎Office Scripts‎ works with Power Automate, and users run scripts on workbooks by using the ‎Excel‎ Online (Business) connector.</span></span> <span data-ttu-id="8a082-106">Microsoft 365 관리자는 Microsoft 365 관리 센터에서 Office 스크립트 설정을 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8a082-106">Microsoft 365 admins can manage Office Scripts settings from the Microsoft 365 admin center.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="8a082-107">시작하기 전에</span><span class="sxs-lookup"><span data-stu-id="8a082-107">Before you begin</span></span>

- <span data-ttu-id="8a082-108">Office 스크립트 설정을 관리 하려면 전역 관리자 여야 합니다. 자세한 내용은 [관리 역할 정보](../add-users/about-admin-roles.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="8a082-108">To manage Office Scripts settings, you must be a Global admin. For more information, see [About admin roles](../add-users/about-admin-roles.md).</span></span>

- <span data-ttu-id="8a082-109">조직의 사용자에 게 다음 계획 중 하 나와 같은 Office 데스크톱 앱에 대 한 액세스를 포함 하는 Microsoft 365 또는 Office 365 상업용 또는 .EDU 계획에 대 한 유효한 라이선스가 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="8a082-109">Ensure users in your organization have a valid license for a Microsoft 365 or Office 365 commercial or EDU plan that includes access to Office desktop apps, such as one of the following plans:</span></span>

    - <span data-ttu-id="8a082-110">Microsoft 365 Business Standard</span><span class="sxs-lookup"><span data-stu-id="8a082-110">Microsoft 365 Business Standard</span></span>
    - <span data-ttu-id="8a082-111">비즈니스용 Microsoft 365 앱</span><span class="sxs-lookup"><span data-stu-id="8a082-111">Microsoft 365 Apps for business</span></span>
    - <span data-ttu-id="8a082-112">엔터프라이즈용 Microsoft 365 앱</span><span class="sxs-lookup"><span data-stu-id="8a082-112">Microsoft 365 Apps for enterprise</span></span>
    - <span data-ttu-id="8a082-113">Office 365 E3</span><span class="sxs-lookup"><span data-stu-id="8a082-113">Office 365 E3</span></span>
    - <span data-ttu-id="8a082-114">Office 365 E5</span><span class="sxs-lookup"><span data-stu-id="8a082-114">Office 365 E5</span></span>
    - <span data-ttu-id="8a082-115">Office 365 A3</span><span class="sxs-lookup"><span data-stu-id="8a082-115">Office 365 A3</span></span>
    - <span data-ttu-id="8a082-116">Office 365 A5</span><span class="sxs-lookup"><span data-stu-id="8a082-116">Office 365 A5</span></span>

## <a name="manage-availability-of-office-scripts-and-sharing-of-scripts"></a><span data-ttu-id="8a082-117">Office 스크립트 사용 가능 여부 관리 및 스크립트 공유</span><span class="sxs-lookup"><span data-stu-id="8a082-117">Manage availability of Office Scripts and sharing of scripts</span></span>

1. <span data-ttu-id="8a082-118">Microsoft 365 관리 센터에서 **Settings** \> **Org settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2053743" target="_blank">Services</a> 탭으로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="8a082-118">In the Microsoft 365 admin center, go to the **Settings** \> **Org settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2053743" target="_blank">Services</a> tab.</span></span>

2. <span data-ttu-id="8a082-119">**Office 스크립트**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="8a082-119">Select **Office Scripts**.</span></span>

3. <span data-ttu-id="8a082-120">Office 스크립트는 기본적으로 설정 되어 있으며 조직의 모든 사용자가 기능에 액세스 하 고 스크립트를 공유할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8a082-120">Office Scripts is turned on by default, and everyone in your organization can access and use the feature and share scripts.</span></span> <span data-ttu-id="8a082-121">조직에 대해 Office 스크립트를 해제 하려면 **사용자가 웹에서 Excel에서 작업 자동화** 확인란의 선택을 취소 합니다.</span><span class="sxs-lookup"><span data-stu-id="8a082-121">To turn off Office Scripts for your organization, clear the **Let users automate their tasks in Excel on the web** check box.</span></span>

4. <span data-ttu-id="8a082-122">이전에 조직에 대해 Office 스크립트를 해제 한 경우 다시 설정 하려면 **사용자가 웹에서 Excel에서 작업을 자동화 하도록 허용**을 선택 하 고 다음 기능에 액세스 하 여 사용할 수 있는 사용자를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="8a082-122">If you previously turned off Office Scripts for your organization and you want to turn it back on, select **Let users automate their tasks in Excel on the web**, and then specify who can access and use the feature:</span></span>

    - <span data-ttu-id="8a082-123">조직의 모든 사용자가 Office 스크립트에 액세스 하 고 사용할 수 있도록 허용 하려면 **모든 사람** (기본값)을 선택 된 채로 두세요.</span><span class="sxs-lookup"><span data-stu-id="8a082-123">To allow all users in your organization to access and use Office Scripts, leave **Everyone** (the default) selected.</span></span> 

    - <span data-ttu-id="8a082-124">특정 그룹의 구성원만 Office 스크립트에 액세스 하 고 사용할 수 있도록 하려면 **특정 그룹**을 선택한 다음 그룹의 이름 또는 전자 메일 별칭을 입력 하 여 허용 목록에 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="8a082-124">To allow only members of a specific group to access and use Office Scripts, select **Specific group**, and then enter the name or email alias of the group to add it to the allow list.</span></span> <span data-ttu-id="8a082-125">허용 목록에는 그룹을 하나만 추가할 수 있으며 다음 형식 중 하나 여야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8a082-125">You may add only one group to the allow list, and it must be one of the following types:</span></span>
        - <span data-ttu-id="8a082-126">Microsoft 365 그룹</span><span class="sxs-lookup"><span data-stu-id="8a082-126">Microsoft 365 group</span></span>
        - <span data-ttu-id="8a082-127">메일 그룹</span><span class="sxs-lookup"><span data-stu-id="8a082-127">Distribution group</span></span>
        - <span data-ttu-id="8a082-128">보안 그룹</span><span class="sxs-lookup"><span data-stu-id="8a082-128">Security group</span></span>
        - <span data-ttu-id="8a082-129">메일 사용 가능 보안 그룹</span><span class="sxs-lookup"><span data-stu-id="8a082-129">Mail-enabled security group</span></span>
    
        <span data-ttu-id="8a082-130">다양 한 유형의 그룹에 대 한 자세한 내용은 [Compare groups](../create-groups/compare-groups.md)를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="8a082-130">To learn more about the different types of groups, see [Compare groups](../create-groups/compare-groups.md).</span></span>

5. <span data-ttu-id="8a082-131">Office 스크립트에 대 한 액세스 권한이 있는 사용자가 자신의 스크립트를 조직의 다른 사용자와 공유할 수 있도록 허용 하려면 **Office 스크립트 액세스 권한이 있는 사용자에 게 조직의 다른 사용자와 스크립트를 공유**하도록 합니다 .를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="8a082-131">To allow users with access to Office Scripts to share their scripts with others in your organization, select **Let users with access to Office Scripts share their scripts with others in the organization**.</span></span> <span data-ttu-id="8a082-132">조직 외부에서 스크립트를 공유 하는 것은 허용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="8a082-132">Sharing scripts outside of an organization is not allowed.</span></span>
 
    > [!NOTE]
    > <span data-ttu-id="8a082-133">나중에 조직의 스크립트 공유 기능을 해제 하는 경우 사용자는 이전에 공유 된 스크립트를 계속 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8a082-133">If you later turn off script sharing for your organization, users will still be able to run previously-shared scripts.</span></span>
 
6. <span data-ttu-id="8a082-134">Office 스크립트에 대 한 액세스 권한이 있는 사용자가 스크립트를 공유할 수 있도록 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="8a082-134">Specify which users with access to Office Scripts can share their scripts:</span></span>
    
    - <span data-ttu-id="8a082-135">Office 스크립트에 액세스 하는 모든 사용자가 자신의 스크립트를 공유할 수 있도록 하려면 모든 **사람** (기본값)을 선택 된 상태로 유지 합니다.</span><span class="sxs-lookup"><span data-stu-id="8a082-135">To allow all users with access to Office Scripts to share their scripts, leave **Everyone** (the default) selected.</span></span>

    - <span data-ttu-id="8a082-136">Office 스크립트에 대 한 액세스 권한이 있는 특정 그룹의 구성원만 스크립트를 공유할 수 있도록 하려면 **특정 그룹**을 선택한 다음 그룹의 이름이 나 전자 메일 별칭을 입력 하 여 허용 목록에 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="8a082-136">To allow only members of a specific group with access to Office Scripts to share their scripts, select **Specific group**, and then enter the name or email alias of the group to add it to the allow list.</span></span> <span data-ttu-id="8a082-137">허용 목록에는 그룹을 하나만 추가할 수 있으며 다음 형식 중 하나 여야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8a082-137">You may add only one group to the allow list, and it must be one of the following types:</span></span>
        - <span data-ttu-id="8a082-138">Microsoft 365 그룹</span><span class="sxs-lookup"><span data-stu-id="8a082-138">Microsoft 365 group</span></span>
        - <span data-ttu-id="8a082-139">메일 그룹</span><span class="sxs-lookup"><span data-stu-id="8a082-139">Distribution group</span></span>
        - <span data-ttu-id="8a082-140">보안 그룹</span><span class="sxs-lookup"><span data-stu-id="8a082-140">Security group</span></span>
        - <span data-ttu-id="8a082-141">메일 사용 가능 보안 그룹</span><span class="sxs-lookup"><span data-stu-id="8a082-141">Mail-enabled security group</span></span>
    
        <span data-ttu-id="8a082-142">다양 한 유형의 그룹에 대 한 자세한 내용은 [Compare groups](../create-groups/compare-groups.md)를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="8a082-142">To learn more about the different types of groups, see [Compare groups](../create-groups/compare-groups.md).</span></span>

7. <span data-ttu-id="8a082-143">**저장**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="8a082-143">Select **Save**.</span></span>

    <span data-ttu-id="8a082-144">Office Script 설정 변경 사항을 적용 하려면 최대 48 시간이 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8a082-144">It can take up to 48 hours for changes to Office Script settings to take effect.</span></span>

## <a name="next-steps"></a><span data-ttu-id="8a082-145">다음 단계</span><span class="sxs-lookup"><span data-stu-id="8a082-145">Next steps</span></span>

<span data-ttu-id="8a082-146">Office 스크립트는 전원 자동화와 함께 작동 하기 때문에 사용자가 Office 스크립트를 사용 하는 동안 기존 DLP (데이터 손실 방지) 정책을 검토 하 여 조직의 데이터가 보호 된 상태로 유지 되도록 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="8a082-146">Because Office Scripts works with Power Automate, we recommend that you review your existing data loss prevention (DLP) policies to ensure your organization's data remains protected while users use ‎Office Scripts‎.</span></span> <span data-ttu-id="8a082-147">자세한 내용은 [DLP (데이터 손실 방지) 정책을](/power-automate/prevent-data-loss)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="8a082-147">For more information, see [Data loss prevention (DLP) policies](/power-automate/prevent-data-loss).</span></span>

## <a name="related-content"></a><span data-ttu-id="8a082-148">관련 콘텐츠</span><span class="sxs-lookup"><span data-stu-id="8a082-148">Related content</span></span>

<span data-ttu-id="8a082-149">[Office 스크립트 기술 설명서](/office/dev/scripts/) (링크 페이지) </span><span class="sxs-lookup"><span data-stu-id="8a082-149">[Office Scripts technical documentation](/office/dev/scripts/) (link page)</span></span>\
<span data-ttu-id="8a082-150">[Excel의 Office 스크립트 소개](https://support.microsoft.com/office/9fbe283d-adb8-4f13-a75b-a81c6baf163a) (문서) </span><span class="sxs-lookup"><span data-stu-id="8a082-150">[Introduction to Office Scripts in Excel](https://support.microsoft.com/office/9fbe283d-adb8-4f13-a75b-a81c6baf163a) (article)</span></span>\
<span data-ttu-id="8a082-151">[Excel에서 웹에 대 한 Office 스크립트 공유](https://support.microsoft.com/office/226eddbc-3a44-4540-acfe-fccda3d1122b) (문서) </span><span class="sxs-lookup"><span data-stu-id="8a082-151">[Sharing Office Scripts in Excel for the Web](https://support.microsoft.com/office/226eddbc-3a44-4540-acfe-fccda3d1122b) (article)</span></span>\
<span data-ttu-id="8a082-152">[웹에서 Excel의 Office 스크립트 기록, 편집 및 만들기](/office/dev/scripts/tutorials/excel-tutorial) (문서)</span><span class="sxs-lookup"><span data-stu-id="8a082-152">[Record, edit, and create Office Scripts in Excel on the web](/office/dev/scripts/tutorials/excel-tutorial) (article)</span></span>