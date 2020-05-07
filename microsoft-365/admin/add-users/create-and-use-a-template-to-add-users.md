---
title: 서식 파일을 만들고 사용하여 사용자 추가
f1.keywords:
- NOCSH
ms.author: v-sharos
author: shars
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
- MSStore_Link
search.appverid:
- MET150
- MOE150
description: 여러 사용자를 추가할 때 템플릿을 만들고 사용 하 여 시간을 절약 하 고 설정을 표준화할 수 있습니다.
ms.openlocfilehash: a39ad3df7928e45f7cb93a13c6ffc40111f2ee48
ms.sourcegitcommit: 7ff75a0f45371b247d975fc61cfa286f5b6f42f6
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/07/2020
ms.locfileid: "44140655"
---
# <a name="create-and-use-a-template-to-add-users"></a><span data-ttu-id="13ac1-103">서식 파일을 만들고 사용하여 사용자 추가</span><span class="sxs-lookup"><span data-stu-id="13ac1-103">Create and use a template to add users</span></span>

::: moniker range="o365-21vianet"

> [!NOTE]
> <span data-ttu-id="13ac1-104">관리 센터가 변경 되는 중입니다.</span><span class="sxs-lookup"><span data-stu-id="13ac1-104">The admin center is changing.</span></span> <span data-ttu-id="13ac1-105">환경이 여기에 나와 있는 세부 정보와 일치 하지 않으면 [새 Microsoft 365 관리 센터 정보](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="13ac1-105">If your experience doesn't match the details presented here, see [About the new Microsoft 365 admin center](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).</span></span>

::: moniker-end

<span data-ttu-id="13ac1-106">여러 사용자를 추가할 때 템플릿을 만들고 사용 하 여 시간을 절약 하 고 설정을 표준화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="13ac1-106">You can create and use a template to save time and standardize settings when you are adding multiple users.</span></span> <span data-ttu-id="13ac1-107">서식 파일은 사용자가 같은 역할을 하 고 동일한 위치에서 작업을 수행 하 고 동일한 소프트웨어를 필요로 하는 것과 같은 여러 일반 속성을 공유 하는 경우에 특히 유용 합니다.</span><span class="sxs-lookup"><span data-stu-id="13ac1-107">Templates are particularly useful if you have users who share many common properties, like those who have the same role and work at the same location and those who require the same software.</span></span> <span data-ttu-id="13ac1-108">예를 들어 같은 사무실에서 근무 하는 지원 엔지니어 팀이 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="13ac1-108">For example, you might have a team of support engineers who work in the same office.</span></span>  

## <a name="create-a-template"></a><span data-ttu-id="13ac1-109">서식 파일 만들기</span><span class="sxs-lookup"><span data-stu-id="13ac1-109">Create a template</span></span>

<span data-ttu-id="13ac1-110">서식 파일 만들기&mdash;쉬운 사용자**활성 사용자** > **사용자 서식 파일** **을 선택한** > 다음 드롭다운 목록에서 **서식 파일 추가** 를 선택 하거나 새 사용자를 추가할 수 있으며, 완료 되 면 항목을 서식 파일로 저장 하는 옵션을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="13ac1-110">Templates are easy to create&mdash;you can select **Users** > **Active users** > **User templates**, and then select **Add a template** from the drop-down list, or you can add a new user and when you are finished, you will have the option of saving the entry as a template.</span></span>

<span data-ttu-id="13ac1-111">사용자를 추가한 후에 템플릿을 만들면 다음 설정에 대해 선택한 값이 서식 파일에 저장 됩니다.</span><span class="sxs-lookup"><span data-stu-id="13ac1-111">When you create a template after adding a user, the values you choose for the following settings are saved in the template:</span></span>

- <span data-ttu-id="13ac1-112">Domain name</span><span class="sxs-lookup"><span data-stu-id="13ac1-112">Domain name</span></span>
- <span data-ttu-id="13ac1-113">암호 설정 선택: 암호를 만들거나 자동 생성 하도록 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="13ac1-113">Password settings choice: you can choose to create passwords or have them auto-generated</span></span>
- <span data-ttu-id="13ac1-114">일회용 암호 선택: 사용자가 처음 로그인 후 새 암호를 만들도록 요구할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="13ac1-114">One-time password choice: you can require the user to create a new password after first sign in</span></span>
- <span data-ttu-id="13ac1-115">라이선스 위치</span><span class="sxs-lookup"><span data-stu-id="13ac1-115">License location</span></span>
- <span data-ttu-id="13ac1-116">라이선스 선택 사항</span><span class="sxs-lookup"><span data-stu-id="13ac1-116">License choices</span></span>
- <span data-ttu-id="13ac1-117">응용 프로그램 선택</span><span class="sxs-lookup"><span data-stu-id="13ac1-117">Application choices</span></span>
- <span data-ttu-id="13ac1-118">역할</span><span class="sxs-lookup"><span data-stu-id="13ac1-118">Role</span></span>
- <span data-ttu-id="13ac1-119">**작업 프로필**, **부서**, **사무실**, **사무실 전화**및 **주소** 와 같은 대부분의 프로필 정보</span><span class="sxs-lookup"><span data-stu-id="13ac1-119">Most profile information, such as **Job profile**, **Department**, **Office**, **Office phone**, and **Street address**</span></span> 

<span data-ttu-id="13ac1-120">다음 정보는 사용자가 고유 하며 서식 파일에 저장 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="13ac1-120">The following information is user-specific and isn't saved in the template:</span></span>

- <span data-ttu-id="13ac1-121">성과 이름</span><span class="sxs-lookup"><span data-stu-id="13ac1-121">First and last name</span></span>
- <span data-ttu-id="13ac1-122">DN(고유 이름)</span><span class="sxs-lookup"><span data-stu-id="13ac1-122">Display name</span></span>
- <span data-ttu-id="13ac1-123">사용자 이름</span><span class="sxs-lookup"><span data-stu-id="13ac1-123">User name</span></span>
- <span data-ttu-id="13ac1-124">전자 메일의 암호 및 암호 전자 메일이 전송 되는 사람을 보낼 선택 사항</span><span class="sxs-lookup"><span data-stu-id="13ac1-124">Choice to send the password in email and who the password email is sent to</span></span>
- <span data-ttu-id="13ac1-125">휴대폰 번호</span><span class="sxs-lookup"><span data-stu-id="13ac1-125">Mobile phone number</span></span>

<span data-ttu-id="13ac1-126">섹션 내에서 설정에 대 한 정보를 입력 하지 않도록 선택 하면 해당 값은 비어 있으며 해당 설정이 서식 파일에 표시 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="13ac1-126">If you choose not to enter information for a setting within a section, that value will be blank and that setting will not display in the template.</span></span> <span data-ttu-id="13ac1-127">예를 들어 **직함** 을 비워 두면 서식 파일을 검토 하 고 서식 파일을 사용할 때 **직함이** 전혀 표시 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="13ac1-127">For example, if you leave **Job title** blank, when you review your template and when you use your template, **Job title** will not appear at all.</span></span> <span data-ttu-id="13ac1-128">모든 **프로필** 섹션 설정을 비워 두면 **프로필** 섹션에 최종 서식 파일에 아무 것 **도 제공** 되지 않은 상태로 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="13ac1-128">If you leave all the **Profile** section settings blank, the **Profile** section will display **None provided** in your final template.</span></span>

<span data-ttu-id="13ac1-129">**서식 파일 추가** 옵션을 선택 하 여 서식 파일을 만들 때 완료할 값을 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="13ac1-129">When you create a template by selecting the **Add a template** option, you can choose which values to complete.</span></span> <span data-ttu-id="13ac1-130">비어 있는 모든 요소는 서식 파일에 **제공 된** 것으로 표시 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="13ac1-130">Anything that is left blank will appear as **None provided** in the template.</span></span>

## <a name="use-a-template-to-add-a-user"></a><span data-ttu-id="13ac1-131">서식 파일을 사용 하 여 사용자 추가</span><span class="sxs-lookup"><span data-stu-id="13ac1-131">Use a template to add a user</span></span>

<span data-ttu-id="13ac1-132">기존 서식 파일을 사용 하 여 사용자를 추가 하려면 다음을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="13ac1-132">To use an existing template to add a user:</span></span>

1. <span data-ttu-id="13ac1-133">관리 센터에서 **사용자** > **활성 사용자**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="13ac1-133">In the admin center, select **Users** > **Active users**.</span></span>

2. <span data-ttu-id="13ac1-134">**사용자 서식 파일**을 선택한 다음 드롭다운 목록에서 서식 파일을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="13ac1-134">Select **User templates**, and then select a template from the drop-down list.</span></span> <span data-ttu-id="13ac1-135">이 목록에는 사용자가 만든 템플릿만 포함 되 고 다른 관리자가 만든 서식 파일은 들어 있지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="13ac1-135">(The list will contain only the templates that you created, not those created by other admins.)</span></span>

 > [!NOTE]
 > <span data-ttu-id="13ac1-136">**사용자 서식** > **파일을**선택 하 고 서식 파일을 선택한 다음 **서식 파일 사용**을 선택 하 여 사용자를 추가 하는 방법으로도 서식 파일을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="13ac1-136">You can also use a template to add a user by selecting **User templates** > **Manage templates**, selecting a template, and then selecting **Use template**.</span></span>

3. <span data-ttu-id="13ac1-137">단계에 따라 선택한 서식 파일에서 사용자를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="13ac1-137">Follow the steps to create a user from the template you selected.</span></span>

> [!NOTE]
> <span data-ttu-id="13ac1-138">추가 하는 사용자가 사용할 수 있는 라이선스가 충분 하지 않은 경우 지불 정보를 사용할 수 있는 경우 기존 결제 정보를 사용 하 여 다른 라이선스를 구입 하려고 합니다.</span><span class="sxs-lookup"><span data-stu-id="13ac1-138">If you have insufficient licenses available for a user that you add, and your payment information is available, we will attempt to purchase another license using your existing payment information.</span></span> <span data-ttu-id="13ac1-139">결제 정보를 사용할 수 없는 경우 사용자는 라이선스가 없는 사용자로 작성 됩니다.</span><span class="sxs-lookup"><span data-stu-id="13ac1-139">If your payment information is unavailable, the user will be created as an unlicensed user.</span></span>

## <a name="manage-templates"></a><span data-ttu-id="13ac1-140">서식 파일 관리</span><span class="sxs-lookup"><span data-stu-id="13ac1-140">Manage templates</span></span>

<span data-ttu-id="13ac1-141">더 이상 필요 없는 템플릿을 쉽게 삭제 하 고 새 서식 파일을 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="13ac1-141">You can easily delete templates you no longer need and add new ones.</span></span> <span data-ttu-id="13ac1-142">서식 파일을 삭제 하려면 다음을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="13ac1-142">To delete a template:</span></span>

1. <span data-ttu-id="13ac1-143">관리 센터에서 **사용자** > **활성 사용자**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="13ac1-143">In the admin center, select **Users** > **Active users**.</span></span>

2. <span data-ttu-id="13ac1-144">**서식 파일**을 선택한 다음 드롭다운 목록에서 **템플릿 관리** 를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="13ac1-144">Select **Templates**, and then select **Manage templates** from the drop-down list.</span></span>

3. <span data-ttu-id="13ac1-145">서식 파일 목록이 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="13ac1-145">A list of templates will appear.</span></span> <span data-ttu-id="13ac1-146">다음 중 하나를 수행 하 여 서식 파일을 삭제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="13ac1-146">You can delete a template by doing any of the following:</span></span>
    - <span data-ttu-id="13ac1-147">서식 파일을 하나 이상 선택 하 고 **삭제**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="13ac1-147">Select one or more templates, and then select **Delete**.</span></span> 
    - <span data-ttu-id="13ac1-148">서식 파일 이름 오른쪽에 있는 세 개의 점을 선택 하 고 **삭제**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="13ac1-148">Select the three dots to the right of the template name, and then select **Delete**.</span></span>
    - <span data-ttu-id="13ac1-149">서식 파일 이름을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="13ac1-149">Select the template name.</span></span> <span data-ttu-id="13ac1-150">서식 파일 세부 정보가 화면 오른쪽에 표시 되 면 **서식 파일 삭제**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="13ac1-150">When the template details appear on the right side of your screen, select **Delete template**.</span></span>

## <a name="related-articles"></a><span data-ttu-id="13ac1-151">관련 문서</span><span class="sxs-lookup"><span data-stu-id="13ac1-151">Related articles</span></span>

[<span data-ttu-id="13ac1-152">사용자를 개별적으로 또는 대량으로 Microsoft 365에 추가</span><span class="sxs-lookup"><span data-stu-id="13ac1-152">Add users individually or in bulk to Microsoft 365</span></span>](add-users.md)

[<span data-ttu-id="13ac1-153">Microsoft 365에서 이전 직원을 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="13ac1-153">Remove a former employee from Microsoft 365</span></span>](remove-former-employee.md)
  
