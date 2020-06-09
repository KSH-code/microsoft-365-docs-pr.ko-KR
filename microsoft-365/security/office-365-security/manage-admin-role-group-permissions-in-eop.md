---
title: EOP에서 역할 그룹 관리
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: 125834f4-1024-4325-ad5a-d2573cfb005e
description: 관리자는 Exchange Online Protection의 EAC (Exchange 관리 센터)에서 사용 권한을 할당 하거나 제거 하는 방법을 확인할 수 있습니다.
ms.openlocfilehash: 3555d3bd7fa4c53802eb214747735223cccc21e5
ms.sourcegitcommit: 73b2426001dc5a3f4b857366ef51e877db549098
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/09/2020
ms.locfileid: "44616517"
---
# <a name="manage-role-groups-in-standalone-eop"></a><span data-ttu-id="38aa9-103">독립 실행형 EOP에서 역할 그룹 관리</span><span class="sxs-lookup"><span data-stu-id="38aa9-103">Manage role groups in standalone EOP</span></span>

<span data-ttu-id="38aa9-104">Exchange Online 사서함이 없는 독립 실행형 EOP (Exchange Online Protection) 조직에서는 EAC (Exchange 관리 센터)를 사용 하 여 역할 그룹에 사용자를 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="38aa9-104">In standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, you can use the Exchange admin center (EAC) to add users to role groups.</span></span> <span data-ttu-id="38aa9-105">역할 그룹에 사용자를 추가 하면 특정 관리 작업을 수행할 수 있는 권한이 사용자에 게 제공 됩니다.</span><span class="sxs-lookup"><span data-stu-id="38aa9-105">Adding a users to a role group gives the user permissions to do specific admin tasks.</span></span> <span data-ttu-id="38aa9-106">역할 그룹에서 사용자를 제거할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="38aa9-106">You can also remove users from role groups.</span></span>

<span data-ttu-id="38aa9-107">역할 및 역할 그룹에 대 한 자세한 내용은 [Permissions in 독립 실행형 EOP](feature-permissions-in-eop.md)을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="38aa9-107">For more information about roles and role groups, see [Permissions in standalone EOP](feature-permissions-in-eop.md).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="38aa9-108">시작하기 전에 알아야 할 내용</span><span class="sxs-lookup"><span data-stu-id="38aa9-108">What do you need to know before you begin?</span></span>

- <span data-ttu-id="38aa9-109">EAC (Exchange 관리 센터)를 열려면 [독립 실행형 EOP에서 exchange 관리 센터](exchange-admin-center-in-exchange-online-protection-eop.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="38aa9-109">To open the Exchange admin center (EAC), see [Exchange admin center in standalone EOP](exchange-admin-center-in-exchange-online-protection-eop.md).</span></span>

- <span data-ttu-id="38aa9-110">독립 실행형 EOP PowerShell을 열려면 [Exchange Online Protection PowerShell에 연결](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="38aa9-110">To open standalone EOP PowerShell, see [Connect to Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="38aa9-111">이 절차를 수행하려면 먼저 사용 권한을 할당받아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="38aa9-111">You need to be assigned permissions before you can perform these procedures.</span></span> <span data-ttu-id="38aa9-112">특히 OrganizationManagement (전역 관리자) 역할 그룹에 기본적으로 할당 되는 역할 관리 역할이 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="38aa9-112">Specifically, you need the Role Management role, which is assigned to the OrganizationManagement (global admins) role group by default.</span></span> <span data-ttu-id="38aa9-113">자세한 내용은 [권한 독립 실행형 EOP의 사용 권한을](feature-permissions-in-eop.md) 참조 하 고 [EAC를 사용 하 여 역할 그룹의 구성원 목록을 수정](manage-admin-role-group-permissions-in-eop.md#use-the-eac-modify-the-list-of-members-in-role-groups)합니다.</span><span class="sxs-lookup"><span data-stu-id="38aa9-113">For more information, see [Permissions in standalone EOP](feature-permissions-in-eop.md) and [Use the EAC modify the list of members in role groups](manage-admin-role-group-permissions-in-eop.md#use-the-eac-modify-the-list-of-members-in-role-groups).</span></span>

- <span data-ttu-id="38aa9-114">이 항목의 절차에 적용할 수 있는 바로 가기 키에 대 한 자세한 내용은 [Exchange Online에서 exchange 관리 센터에 대 한 바로 가기 키](https://docs.microsoft.com/Exchange/accessibility/keyboard-shortcuts-in-admin-center)를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="38aa9-114">For information about keyboard shortcuts that may apply to the procedures in this topic, see [Keyboard shortcuts for the Exchange admin center in Exchange Online](https://docs.microsoft.com/Exchange/accessibility/keyboard-shortcuts-in-admin-center).</span></span>

> [!TIP]
> <span data-ttu-id="38aa9-115">문제가 있습니까?</span><span class="sxs-lookup"><span data-stu-id="38aa9-115">Having problems?</span></span> <span data-ttu-id="38aa9-116">[Exchange Online Protection](https://go.microsoft.com/fwlink/p/?linkId=285351) 포럼에서 도움을 요청 하세요.</span><span class="sxs-lookup"><span data-stu-id="38aa9-116">Ask for help in the [Exchange Online Protection](https://go.microsoft.com/fwlink/p/?linkId=285351) forum.</span></span>

## <a name="use-the-eac-to-manage-role-groups"></a><span data-ttu-id="38aa9-117">EAC를 사용 하 여 역할 그룹 관리</span><span class="sxs-lookup"><span data-stu-id="38aa9-117">Use the EAC to manage role groups</span></span>

### <a name="use-the-eac-to-view-role-groups"></a><span data-ttu-id="38aa9-118">EAC를 사용 하 여 역할 그룹 보기</span><span class="sxs-lookup"><span data-stu-id="38aa9-118">Use the EAC to view role groups</span></span>

1. <span data-ttu-id="38aa9-119">EAC에서 **사용 권한** \> **관리자 역할로**이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="38aa9-119">In the EAC, go to **Permissions** \> **Admin roles**.</span></span> <span data-ttu-id="38aa9-120">조직의 모든 역할 그룹이 여기에 나열됩니다.</span><span class="sxs-lookup"><span data-stu-id="38aa9-120">All of the role groups in your organization are listed here.</span></span>

2. <span data-ttu-id="38aa9-121">역할 그룹을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="38aa9-121">Select a role group.</span></span> <span data-ttu-id="38aa9-122">세부 정보 창에는 역할 그룹에 따라 이름, **설명**, **할당 된 역할**및 **관리 되** 는 **이름이**표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="38aa9-122">The Details pane shows the **Name**, **Description**, **Assigned roles**, and **Managed by** of the role group.</span></span> <span data-ttu-id="38aa9-123">편집 아이콘 **편집** 을 클릭 하 여이 정보를 볼 수도 있습니다 ![ ](../../media/ITPro-EAC-EditIcon.png) .</span><span class="sxs-lookup"><span data-stu-id="38aa9-123">You can also see this information by clicking **Edit** ![Edit icon](../../media/ITPro-EAC-EditIcon.png).</span></span>

### <a name="use-the-eac-to-create-role-groups"></a><span data-ttu-id="38aa9-124">EAC를 사용 하 여 역할 그룹 만들기</span><span class="sxs-lookup"><span data-stu-id="38aa9-124">Use the EAC to create role groups</span></span>

<span data-ttu-id="38aa9-125">새 역할 그룹을 만들 때는 그룹을 만드는 중 또는 이후에 모든 설정을 직접 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="38aa9-125">When you create a new role group, you can configure all of the settings yourself (during the creation of the group or after).</span></span> <span data-ttu-id="38aa9-126">또는 기존 역할 그룹을 복사 하 여 수정할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="38aa9-126">Or, you can copy an existing role group and modify it.</span></span>

1. <span data-ttu-id="38aa9-127">EAC에서 **사용 권한** \> **관리자 역할로**이동한 후 다음 단계 중 하나를 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="38aa9-127">In the EAC, go to **Permissions** \> **Admin roles**, and then do one of the following steps:</span></span>

   - <span data-ttu-id="38aa9-128">**새 역할 그룹을 수동으로 만들기**: 추가 아이콘 **추가** 를 클릭 ![ ](../../media/ITPro-EAC-AddIcon.png) 합니다.</span><span class="sxs-lookup"><span data-stu-id="38aa9-128">**Manually create a new role group**: Click **Add** ![Add icon](../../media/ITPro-EAC-AddIcon.png).</span></span>

   - <span data-ttu-id="38aa9-129">**기존 역할 그룹 복사**: 복사할 역할 그룹을 선택한 다음 복사본 복사 아이콘 **를 클릭** ![ ](../../media/ITPro-EAC-CopyIcon.png) 합니다.</span><span class="sxs-lookup"><span data-stu-id="38aa9-129">**Copy an existing role group**: Select the role group that you want to copy and then click **Copy** ![Copy icon](../../media/ITPro-EAC-CopyIcon.png).</span></span>

2. <span data-ttu-id="38aa9-130">**새 역할 그룹** 창이 나타나면 다음 설정을 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="38aa9-130">In the **New role group** window that appears, configure the following settings:</span></span>

    - <span data-ttu-id="38aa9-131">**이름**: 역할 그룹의 고유한 이름을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="38aa9-131">**Name**: Enter a unique name for the role group.</span></span>

    - <span data-ttu-id="38aa9-132">**설명**: 역할 그룹에 대 한 설명을 입력 합니다 (선택 사항).</span><span class="sxs-lookup"><span data-stu-id="38aa9-132">**Description**: Enter an optional description for the role group.</span></span>

    - <span data-ttu-id="38aa9-133">**역할**: **추가** ![ 아이콘 추가 ](../../media/ITPro-EAC-AddIcon.png) 또는 ITPro-EAC-RemoveIcon **제거** ![ 를 클릭 하 여 ](../../media/ITPro-EAC-RemoveIcon.gif) 역할 그룹에 할당 된 역할을 선택 하거나 수정 합니다.</span><span class="sxs-lookup"><span data-stu-id="38aa9-133">**Roles**: Click **Add** ![Add icon](../../media/ITPro-EAC-AddIcon.png) or **Remove** ![ITPro-EAC-RemoveIcon.gif](../../media/ITPro-EAC-RemoveIcon.gif) to select or modify the roles that are assigned to the role group.</span></span>

    - <span data-ttu-id="38aa9-134">**구성원**: **add** ![ icon 추가 ](../../media/ITPro-EAC-AddIcon.png) 또는 **제거** ![ 를 클릭 하 여 ](../../media/ITPro-EAC-RemoveIcon.gif) 역할 그룹 구성원을 수정 ITPro-EAC-RemoveIcon.</span><span class="sxs-lookup"><span data-stu-id="38aa9-134">**Members**: Click **Add** ![Add icon](../../media/ITPro-EAC-AddIcon.png) or **Remove** ![ITPro-EAC-RemoveIcon.gif](../../media/ITPro-EAC-RemoveIcon.gif) to modify the role group membership.</span></span>

3. <span data-ttu-id="38aa9-135">작업이 끝나면 **저장** 을 클릭 하 여 역할 그룹을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="38aa9-135">When you're finished, click **Save** to create the role group.</span></span>

### <a name="use-the-eac-to-modify-role-groups"></a><span data-ttu-id="38aa9-136">EAC를 사용 하 여 역할 그룹 수정</span><span class="sxs-lookup"><span data-stu-id="38aa9-136">Use the EAC to modify role groups</span></span>

<span data-ttu-id="38aa9-137">EAC에서 **사용 권한** \> **관리자 역할로**이동 하 여 수정 하려는 역할 그룹을 선택한 다음 편집 아이콘 **편집** 을 클릭 ![ ](../../media/ITPro-EAC-EditIcon.png) 합니다.</span><span class="sxs-lookup"><span data-stu-id="38aa9-137">In the EAC, go to **Permissions** \> **Admin roles**, select the role group you want to modify, and then click **Edit** ![Edit icon](../../media/ITPro-EAC-EditIcon.png).</span></span>

<span data-ttu-id="38aa9-138">역할 그룹을 만들 때와 마찬가지로 역할 그룹을 수정 하는 경우에도 동일한 옵션을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="38aa9-138">The same options are available when you modify role groups as when you create role groups.</span></span> <span data-ttu-id="38aa9-139">다음을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="38aa9-139">You can:</span></span>

- <span data-ttu-id="38aa9-140">이름 및 설명을 변경 합니다.</span><span class="sxs-lookup"><span data-stu-id="38aa9-140">Change the name and description.</span></span>

- <span data-ttu-id="38aa9-141">관리 역할 추가 및 제거 (역할 할당 만들기 또는 제거)</span><span class="sxs-lookup"><span data-stu-id="38aa9-141">Add and remove management roles (create or remove role assignments).</span></span>

- <span data-ttu-id="38aa9-142">구성원을 추가 및 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="38aa9-142">Add and remove members.</span></span>

<span data-ttu-id="38aa9-143">**참고**: 조직 관리와 같은 일부 역할 그룹은 그룹에서 제거할 수 있는 역할을 제한 합니다.</span><span class="sxs-lookup"><span data-stu-id="38aa9-143">**Note**: Some role groups (for example, Organization Management) restrict the roles that you can remove from group.</span></span>

#### <a name="use-the-eac-modify-the-list-of-members-in-role-groups"></a><span data-ttu-id="38aa9-144">EAC를 사용 하 여 역할 그룹의 구성원 목록 수정</span><span class="sxs-lookup"><span data-stu-id="38aa9-144">Use the EAC modify the list of members in role groups</span></span>

1. <span data-ttu-id="38aa9-145">EAC에서 **사용 권한** \> **관리자 역할로**이동 하 여 수정 하려는 역할 그룹을 선택한 다음 편집 아이콘 **편집** 을 클릭 ![ ](../../media/ITPro-EAC-EditIcon.png) 합니다.</span><span class="sxs-lookup"><span data-stu-id="38aa9-145">In the EAC, go to **Permissions** \> **Admin roles**, select the role group that you want to modify, and then click **Edit** ![Edit icon](../../media/ITPro-EAC-EditIcon.png).</span></span>

2. <span data-ttu-id="38aa9-146">역할 그룹 속성 페이지가 열리면 **Memebers** 섹션에서 다음 단계 중 하나를 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="38aa9-146">In the role group properties page that opens, in the **Memebers** section, do either of the following steps:</span></span>

   - <span data-ttu-id="38aa9-147">**Add** ![ 추가 아이콘 추가를 클릭 ](../../media/ITPro-EAC-AddIcon.png) 합니다.</span><span class="sxs-lookup"><span data-stu-id="38aa9-147">Click **Add** ![Add Icon](../../media/ITPro-EAC-AddIcon.png).</span></span> <span data-ttu-id="38aa9-148">표시 된 페이지에서 wou를 추가 하려는 사용자를 찾은 다음 **추가 >** 를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="38aa9-148">In the page that appears, find the user that wou want to add, and then click **add ->**.</span></span> <span data-ttu-id="38aa9-149">사용자를 선택 하 고 필요에 따라 **추가->** 여러 번을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="38aa9-149">Select users and click **add ->** many times as necessary.</span></span> <span data-ttu-id="38aa9-150">작업을 마친 후 **확인**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="38aa9-150">When you're finished, click **OK**.</span></span>

   - <span data-ttu-id="38aa9-151">제거할 사용자를 선택 하 고 제거 아이콘 **제거** 를 클릭 ![ ](../../media/ITPro-EAC-RemoveIcon.gif) 합니다.</span><span class="sxs-lookup"><span data-stu-id="38aa9-151">Select the users that you want to remove, and then click **Remove** ![Remove icon](../../media/ITPro-EAC-RemoveIcon.gif).</span></span>

3. <span data-ttu-id="38aa9-152">작업을 마쳤으면 **저장**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="38aa9-152">When you're finished, click **Save**.</span></span>

   > [!NOTE]
   > <span data-ttu-id="38aa9-153">구성원을 역할 그룹에 추가하거나 역할 그룹에서 제거한 후 사용자가 관리 권한 변경 내용을 확인하려면 로그아웃했다가 다시 로그인해야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="38aa9-153">Users may have to sign out and sign in again to see the change in their administrative rights after you add or remove members from the role group.</span></span>

### <a name="use-the-eac-to-remove-role-groups"></a><span data-ttu-id="38aa9-154">EAC를 사용 하 여 역할 그룹 제거</span><span class="sxs-lookup"><span data-stu-id="38aa9-154">Use the EAC to remove role groups</span></span>

<span data-ttu-id="38aa9-155">기본 제공 역할 그룹을 제거할 수는 없지만 만든 사용자 지정 역할 그룹을 제거할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="38aa9-155">You can't remove built-in role groups, but you can remove custom role groups that you've created.</span></span>

1. <span data-ttu-id="38aa9-156">EAC에서 **사용 권한** \> **관리자 역할로**이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="38aa9-156">In the EAC, go to **Permissions** \> **Admin roles**.</span></span>

2. <span data-ttu-id="38aa9-157">제거할 역할 그룹을 선택한 다음 삭제 아이콘 삭제를 클릭 **Delete** ![ ](../../media/ITPro-EAC-DeleteIcon.png) 합니다.</span><span class="sxs-lookup"><span data-stu-id="38aa9-157">Select the role group you want to remove and then click **Delete** ![Delete icon](../../media/ITPro-EAC-DeleteIcon.png).</span></span>

3. <span data-ttu-id="38aa9-158">확인 창이 나타나면 **예** 를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="38aa9-158">Click **Yes** in the confirmation window that appears.</span></span>

## <a name="use-powershell-to-manage-role-groups"></a><span data-ttu-id="38aa9-159">PowerShell을 사용 하 여 역할 그룹 관리</span><span class="sxs-lookup"><span data-stu-id="38aa9-159">Use PowerShell to manage role groups</span></span>

### <a name="use-standalone-eop-powershell-to-view-role-groups"></a><span data-ttu-id="38aa9-160">독립 실행형 EOP PowerShell을 사용 하 여 역할 그룹 보기</span><span class="sxs-lookup"><span data-stu-id="38aa9-160">Use standalone EOP PowerShell to view role groups</span></span>

<span data-ttu-id="38aa9-161">역할 그룹을 보려면 다음 구문을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="38aa9-161">To view a role group, use the following syntax:</span></span>

```PowerShell
Get-RoleGroup [-Identity "<Role Group Name>"] [-Filter <Filter>]
```

<span data-ttu-id="38aa9-162">이 예에서는 모든 역할 그룹의 요약 목록을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="38aa9-162">This example returns a summary list of all role groups.</span></span>

```PowerShell
Get-RoleGroup
```

<span data-ttu-id="38aa9-163">이 예에서는 받는 사람 관리자 라는 역할 그룹에 대 한 자세한 정보를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="38aa9-163">This example returns detailed information for the role group named Recipient Administrators.</span></span>

```PowerShell
Get-RoleGroup -Identity "Recipient Administrators" | Format-List
```

<span data-ttu-id="38aa9-164">이 예제에서는 사용자 줄리아가 구성원 인 모든 역할 그룹을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="38aa9-164">This example returns all role groups where the user Julia is a member.</span></span> <span data-ttu-id="38aa9-165">다음 명령을 실행 하 여 찾을 수 있는 줄리아에는 DistinguishedName (DN) 값을 사용 해야 `Get-User -Identity Julia | Format-List DistinguishedName` 합니다.</span><span class="sxs-lookup"><span data-stu-id="38aa9-165">You need to use the DistinguishedName (DN) value for Julia, which you can find by running the command: `Get-User -Identity Julia | Format-List DistinguishedName`.</span></span>

```PowerShell
Get-RoleGroup -Filter "Members -eq 'CN=Julia,OU=contoso.onmicrosoft.com,OU=Microsoft Exchange Hosted Organizations,DC=NAMPR001,DC=PROD,DC=OUTLOOK,DC=COM'"
```

<span data-ttu-id="38aa9-166">구문과 매개 변수에 대 한 자세한 내용은 ' [Get-RoleGroup](https://docs.microsoft.com/powershell/module/exchange/Get-RoleGroup)'을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="38aa9-166">For detailed syntax and parameter information, see [Get-RoleGroup](https://docs.microsoft.com/powershell/module/exchange/Get-RoleGroup).</span></span>

### <a name="use-standalone-eop-powershell-to-create-role-groups"></a><span data-ttu-id="38aa9-167">독립 실행형 EOP PowerShell을 사용 하 여 역할 그룹 만들기</span><span class="sxs-lookup"><span data-stu-id="38aa9-167">Use standalone EOP PowerShell to create role groups</span></span>

<span data-ttu-id="38aa9-168">새 역할 그룹을 만들 때 모든 설정을 수동으로 구성할 수 있습니다 (그룹을 만드는 동안 또는 이후에).</span><span class="sxs-lookup"><span data-stu-id="38aa9-168">When you create a new role group, you can configure all of the settings manually (during the creation of the group or after).</span></span> <span data-ttu-id="38aa9-169">또는 기존 역할 그룹을 복사 하 여 수정할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="38aa9-169">Or, you can copy an existing role group and modify it.</span></span>

- <span data-ttu-id="38aa9-170">새 역할 그룹을 수동으로 만들려면 다음 구문을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="38aa9-170">To manually create a new role group, use the following syntax:</span></span>

  ```PowerShell
  New-RoleGroup -Name "Unique Name" -Description "Descriptive text" -Roles <"Role1","Role2"...>
  ```

  - <span data-ttu-id="38aa9-171">_Roles_ 매개 변수는 다음 구문을 사용 하 여 역할 그룹에 할당할 관리 역할을 지정 합니다 `"Role1","Role1",..."RoleN"` .</span><span class="sxs-lookup"><span data-stu-id="38aa9-171">The _Roles_ parameter specifies the management roles to assign to the role group by using the following syntax `"Role1","Role1",..."RoleN"`.</span></span> <span data-ttu-id="38aa9-172">**Get-ManagementRole** cmdlet을 사용 하 여 사용 가능한 역할을 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="38aa9-172">You can see the available roles by using the **Get-ManagementRole** cmdlet.</span></span>

  - <span data-ttu-id="38aa9-173">_Members_ 매개 변수는 다음 구문을 사용 하 여 역할 그룹의 구성원을 지정 합니다 `"Member1","Member2",..."MemberN"` .</span><span class="sxs-lookup"><span data-stu-id="38aa9-173">The _Members_ parameter specifies the members of the role group by using the following syntax: `"Member1","Member2",..."MemberN"`.</span></span> <span data-ttu-id="38aa9-174">사용자, 메일 사용이 가능한 유니버설 보안 그룹 (Usg) 또는 기타 역할 그룹 (보안 주체)을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="38aa9-174">You can specify users, mail-enabled universal security groups (USGs), or other role groups (security principals).</span></span>

  <span data-ttu-id="38aa9-175">이 예에서는 다음 설정을 사용 하 여 "제한 된 받는 사람 관리" 라는 새 역할 그룹을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="38aa9-175">This example creates a new role group named "Limited Recipient Management" with the following settings:</span></span>

  - <span data-ttu-id="38aa9-176">역할 그룹에는 Mail Recipients 역할이 할당됩니다.</span><span class="sxs-lookup"><span data-stu-id="38aa9-176">The Mail Recipients role is assigned to the role group.</span></span>

  - <span data-ttu-id="38aa9-177">사용자 Kim 및 Martin는 구성원으로 추가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="38aa9-177">The users Kim and Martin are added as members.</span></span>

  ```PowerShell
  New-RoleGroup -Name "Limited Recipient Management" -Roles "Mail Recipients" -Members "Kim","Martin"
  ```

- <span data-ttu-id="38aa9-178">기존 역할 그룹을 복사 하려면 다음 단계를 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="38aa9-178">To copy an existing role group, do the following steps:</span></span>

  1. <span data-ttu-id="38aa9-179">다음 구문을 사용 하 여 복사할 역할 그룹을 변수에 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="38aa9-179">Store the role group that you want to copy in a variable using the following syntax:</span></span>

     ```PowerShell
     $RoleGroup = Get-RoleGroup "<Existing Role Group Name>"
     ```

  2. <span data-ttu-id="38aa9-180">다음 구문을 사용 하 여 새 역할 그룹을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="38aa9-180">Create the new role group using the following syntax:</span></span>

     ```PowerShell
     New-RoleGroup -Name "<Unique Name>" -Roles $RoleGroup.Roles [-Members <Members>]
     ```

     <span data-ttu-id="38aa9-181">_Members_ 매개 변수는 다음 구문을 사용 하 여 역할 그룹의 구성원을 지정 합니다 `"Member1","Member2",..."MemberN"` .</span><span class="sxs-lookup"><span data-stu-id="38aa9-181">The _Members_ parameter specifies the members of the role group by using the following syntax: `"Member1","Member2",..."MemberN"`.</span></span> <span data-ttu-id="38aa9-182">사용자, 메일 사용이 가능한 유니버설 보안 그룹 (Usg) 또는 기타 역할 그룹 (보안 주체)을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="38aa9-182">You can specify users, mail-enabled universal security groups (USGs), or other role groups (security principals).</span></span>

     <span data-ttu-id="38aa9-183">이 예에서는 조직 관리 역할 그룹을 "제한 된 조직 관리" 라는 새 역할 그룹으로 복사 합니다.</span><span class="sxs-lookup"><span data-stu-id="38aa9-183">This example copies the Organization Management role group to the new role group named "Limited Organization Management".</span></span> <span data-ttu-id="38aa9-184">역할 그룹 구성원은 Isabelle, Carter 및 Lukas입니다.</span><span class="sxs-lookup"><span data-stu-id="38aa9-184">The role group members are Isabelle, Carter, and Lukas.</span></span>

     ```PowerShell
     $RoleGroup = Get-RoleGroup "Organization Management"
     New-RoleGroup "Limited Organization Management" -Roles $RoleGroup.Roles -Members "Isabelle","Carter","Lukas"
     ```

<span data-ttu-id="38aa9-185">구문 및 매개 변수에 대 한 자세한 내용은 [새-RoleGroup를 사용](https://docs.microsoft.com/powershell/module/exchange/New-RoleGroup)하십시오.</span><span class="sxs-lookup"><span data-stu-id="38aa9-185">For detailed syntax and parameter information, [New-RoleGroup](https://docs.microsoft.com/powershell/module/exchange/New-RoleGroup).</span></span>

### <a name="use-standalone-eop-powershell-modify-the-list-of-members-in-role-groups"></a><span data-ttu-id="38aa9-186">독립 실행형 EOP PowerShell 사용 역할 그룹의 구성원 목록을 수정 합니다.</span><span class="sxs-lookup"><span data-stu-id="38aa9-186">Use standalone EOP PowerShell modify the list of members in role groups</span></span>

- <span data-ttu-id="38aa9-187">**추가-rolegroupmember** 및 **Remove-rolegroupmember** cmdlet은 한 번에 하나씩 개별 구성원을 추가 하거나 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="38aa9-187">The **Add-RoleGroupMember** and **Remove-RoleGroupMember** cmdlets add or remove individual members one at a time.</span></span> <span data-ttu-id="38aa9-188">**업데이트-RoleGroupMember** cmdlet은 기존 구성원 목록을 대체 하거나 수정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="38aa9-188">The **Update-RoleGroupMember** cmdlet can replace or modify the existing list of members.</span></span>

- <span data-ttu-id="38aa9-189">역할 그룹의 구성원은 사용자, 메일 사용이 가능한 유니버설 보안 그룹 (Usg) 또는 다른 역할 그룹 (보안 주체)이 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="38aa9-189">The members of a role group can be users, mail-enabled universal security groups (USGs), or other role groups (security principals).</span></span>

<span data-ttu-id="38aa9-190">역할 그룹의 구성원을 수정 하려면 다음 구문을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="38aa9-190">To modify the members of a role group, use the following syntax:</span></span>

```PowerShell
Update-RoleGroupMember -Identity "<Role Group Name>" -Members <Members>
```

- <span data-ttu-id="38aa9-191">기존 구성원 목록을 지정한 값으로 _바꾸려면_ 다음 구문을 사용 `"Member1","Member2",..."MemberN"` 합니다.</span><span class="sxs-lookup"><span data-stu-id="38aa9-191">To _replace_ the existing list of members with the values you specify, use the following syntax: `"Member1","Member2",..."MemberN"`.</span></span>

- <span data-ttu-id="38aa9-192">기존 구성원 목록을 _선택적으로 수정_ 하려면 다음 구문을 사용 `@{Add="Member1","Member2"...; Remove="Member3","Member4"...}` 합니다.</span><span class="sxs-lookup"><span data-stu-id="38aa9-192">To _selectively modify_ the existing list of members, use the following syntax: `@{Add="Member1","Member2"...; Remove="Member3","Member4"...}`.</span></span>

<span data-ttu-id="38aa9-193">이 예에서는 Help Desk 역할 그룹의 현재 구성원을 모두 지정한 사용자로 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="38aa9-193">This example replaces all current members of the Help Desk role group with the specified users.</span></span>

```PowerShell
Update-RoleGroupMember -Identity "Help Desk" -Members "Gabriela Laureano","Hyun-Ae Rim","Jacob Berger"
```

<span data-ttu-id="38aa9-194">이 예에서는 Daigoro Akai를 추가 하 고 Help Desk 역할 그룹의 구성원 목록에서 Valeria Barrio를 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="38aa9-194">This example adds Daigoro Akai and removes Valeria Barrio from the list of members on the Help Desk role group.</span></span>

```PowerShell
Update-RoleGroupMember -Identity "Help Desk" -Members @{Add="Daigoro Akai"; Remove="Valeria Barrios"}
```

<span data-ttu-id="38aa9-195">구문 및 매개 변수에 대 한 자세한 내용은 [업데이트-RoleGroupMember](https://docs.microsoft.com/powershell/module/exchange/Update-RoleGroupMember)를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="38aa9-195">For detailed syntax and parameter information, see [Update-RoleGroupMember](https://docs.microsoft.com/powershell/module/exchange/Update-RoleGroupMember).</span></span>

### <a name="use-standalone-eop-powershell-to-remove-role-groups"></a><span data-ttu-id="38aa9-196">독립 실행형 EOP PowerShell을 사용 하 여 역할 그룹 제거</span><span class="sxs-lookup"><span data-stu-id="38aa9-196">Use standalone EOP PowerShell to remove role groups</span></span>

<span data-ttu-id="38aa9-197">기본 제공 역할 그룹을 제거할 수는 없지만 만든 사용자 지정 역할 그룹을 제거할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="38aa9-197">You can't remove built-in role groups, but you can remove custom role groups that you've created.</span></span>

<span data-ttu-id="38aa9-198">사용자 지정 역할 그룹을 제거 하려면 다음 구문을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="38aa9-198">To remove a custom role group, use the following syntax:</span></span>

```PowerShell
Remove-RoleGroup -Identity "<Role Group Name>" [-BypassSecurityGroupManagerCheck]
```

<span data-ttu-id="38aa9-199">이 예에서는 Training Administrators 역할 그룹을 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="38aa9-199">This example removes the Training Administrators role group.</span></span>

```PowerShell
Remove-RoleGroup -Identity "Training Administrators"
```

<span data-ttu-id="38aa9-200">구문과 매개 변수에 대한 자세한 내용은 [Remove-RoleGroup](https://docs.microsoft.com/powershell/module/exchange/Remove-RoleGroup)를 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="38aa9-200">For detailed syntax and parameter information, see [Remove-RoleGroup](https://docs.microsoft.com/powershell/module/exchange/Remove-RoleGroup).</span></span>

### <a name="how-do-you-know-these-procedures-worked"></a><span data-ttu-id="38aa9-201">이 절차가 제대로 수행되었는지 어떻게 확인하나요?</span><span class="sxs-lookup"><span data-stu-id="38aa9-201">How do you know these procedures worked?</span></span>

<span data-ttu-id="38aa9-202">역할 그룹이 성공적으로 복사 되었는지 확인 하려면 다음 단계 중 하나를 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="38aa9-202">To verify that you've successfully copied a role group, do either of the following steps:</span></span>

- <span data-ttu-id="38aa9-203">EAC에서 **사용 권한** \> **관리자 역할로**이동 하 여 해당 역할 그룹이 나열 되는지 확인 합니다 (또는 나열 되지 않음).</span><span class="sxs-lookup"><span data-stu-id="38aa9-203">In the EAC, go to **Permissions** \> **Admin roles**, and verify the role group is listed (or not listed).</span></span> <span data-ttu-id="38aa9-204">역할 그룹을 선택 하 고 세부 정보 창에서 설정을 확인 하거나 편집 아이콘 **편집** ![ 을 클릭 ](../../media/ITPro-EAC-EditIcon.png) 하 여 설정을 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="38aa9-204">Select the role group, and verify the settings in the Details pane or click **Edit** ![Edit icon](../../media/ITPro-EAC-EditIcon.png) to verify the settings.</span></span>

- <span data-ttu-id="38aa9-205">Exchange Online PowerShell에서 \<Role Group Name\> 역할 그룹의 이름으로 바꾸고 다음 명령을 실행 하 여 역할 그룹이 존재 하는지 확인 하 고 (또는 존재 하지 않음) 설정을 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="38aa9-205">In Exchange Online PowerShell, replace \<Role Group Name\> with the name of the role group, and run the following command to verify the role group exists (or doesn't exist) and verify the settings:</span></span>

    ```PowerShell
    Get-RoleGroup -Identity "<Role Group Name>" | Format-List
    ```
