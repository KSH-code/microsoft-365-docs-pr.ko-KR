---
title: EOP에서 역할 그룹 관리
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: how-to
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: 125834f4-1024-4325-ad5a-d2573cfb005e
description: 관리자는 Exchange Online Protection에서 EAC(Exchange 관리 센터)의 사용 권한을 할당하거나 제거하는 방법을 통해 자세히 설명할 수 있습니다.
ms.openlocfilehash: 8d452eb85d59bbe82cc6685d652617bc857c1ddf
ms.sourcegitcommit: e12fa502bc216f6083ef5666f693a04bb727d4df
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/20/2020
ms.locfileid: "46825692"
---
# <a name="manage-role-groups-in-standalone-eop"></a><span data-ttu-id="69dab-103">독립 실행형 EOP에서 역할 그룹 관리</span><span class="sxs-lookup"><span data-stu-id="69dab-103">Manage role groups in standalone EOP</span></span>

<span data-ttu-id="69dab-104">Exchange Online 사서함이 없는 독립 실행형 EOP(Exchange Online Protection) 조직에서는 EAC(Exchange 관리 센터)를 사용하여 역할 그룹에 사용자를 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="69dab-104">In standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, you can use the Exchange admin center (EAC) to add users to role groups.</span></span> <span data-ttu-id="69dab-105">한 사용자를 역할 그룹에 추가하면 특정 관리 작업을 수행할 수 있는 권한이 부여됩니다.</span><span class="sxs-lookup"><span data-stu-id="69dab-105">Adding a users to a role group gives the user permissions to do specific admin tasks.</span></span> <span data-ttu-id="69dab-106">역할 그룹에서 사용자를 제거할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="69dab-106">You can also remove users from role groups.</span></span>

<span data-ttu-id="69dab-107">역할 및 역할 그룹에 대한 자세한 내용은 독립 [실행형 EOP의 사용 권한을 참조하십시오.](feature-permissions-in-eop.md)</span><span class="sxs-lookup"><span data-stu-id="69dab-107">For more information about roles and role groups, see [Permissions in standalone EOP](feature-permissions-in-eop.md).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="69dab-108">시작하기 전에 알아야 할 내용은 무엇인가요?</span><span class="sxs-lookup"><span data-stu-id="69dab-108">What do you need to know before you begin?</span></span>

- <span data-ttu-id="69dab-109">EAC(Exchange 관리 센터)를 열려면 [Exchange 관리 센터를 독립 실행형 EOP로 묶어보세요.](exchange-admin-center-in-exchange-online-protection-eop.md)</span><span class="sxs-lookup"><span data-stu-id="69dab-109">To open the Exchange admin center (EAC), see [Exchange admin center in standalone EOP](exchange-admin-center-in-exchange-online-protection-eop.md).</span></span>

- <span data-ttu-id="69dab-110">독립 실행형 EOP PowerShell을 열려면 [Exchange Online Protection PowerShell에 연결을 참조하세요.](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell)</span><span class="sxs-lookup"><span data-stu-id="69dab-110">To open standalone EOP PowerShell, see [Connect to Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="69dab-111">이 절차를 수행하려면 먼저 사용 권한을 할당받아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="69dab-111">You need to be assigned permissions before you can perform these procedures.</span></span> <span data-ttu-id="69dab-112">특히 OrganizationManagement(전역 관리자) 역할 그룹에 할당된 역할 관리 역할이 기본적으로 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="69dab-112">Specifically, you need the Role Management role, which is assigned to the OrganizationManagement (global admins) role group by default.</span></span> <span data-ttu-id="69dab-113">자세한 내용은 독립 [실행형 EOP의 사용 권한을 참조하고](feature-permissions-in-eop.md) [EAC를 사용하여 역할 그룹의 구성원 목록을 수정합니다.](manage-admin-role-group-permissions-in-eop.md#use-the-eac-modify-the-list-of-members-in-role-groups)</span><span class="sxs-lookup"><span data-stu-id="69dab-113">For more information, see [Permissions in standalone EOP](feature-permissions-in-eop.md) and [Use the EAC modify the list of members in role groups](manage-admin-role-group-permissions-in-eop.md#use-the-eac-modify-the-list-of-members-in-role-groups).</span></span>

- <span data-ttu-id="69dab-114">이 항목의 절차에 적용할 수 있는 바로 가기 키에 대한 자세한 내용은 [Exchange Online에서 Exchange 관리 센터에 대 한 바로 가기 키를 참조 하십시오.](https://docs.microsoft.com/Exchange/accessibility/keyboard-shortcuts-in-admin-center)</span><span class="sxs-lookup"><span data-stu-id="69dab-114">For information about keyboard shortcuts that may apply to the procedures in this topic, see [Keyboard shortcuts for the Exchange admin center in Exchange Online](https://docs.microsoft.com/Exchange/accessibility/keyboard-shortcuts-in-admin-center).</span></span>

> [!TIP]
> <span data-ttu-id="69dab-115">문제가 있나요?</span><span class="sxs-lookup"><span data-stu-id="69dab-115">Having problems?</span></span> <span data-ttu-id="69dab-116">[Exchange Online Protection](https://go.microsoft.com/fwlink/p/?linkId=285351) 포럼에서 도움을 요청하세요.</span><span class="sxs-lookup"><span data-stu-id="69dab-116">Ask for help in the [Exchange Online Protection](https://go.microsoft.com/fwlink/p/?linkId=285351) forum.</span></span>

## <a name="use-the-eac-to-manage-role-groups"></a><span data-ttu-id="69dab-117">EAC를 사용하여 역할 그룹 관리</span><span class="sxs-lookup"><span data-stu-id="69dab-117">Use the EAC to manage role groups</span></span>

### <a name="use-the-eac-to-view-role-groups"></a><span data-ttu-id="69dab-118">EAC를 사용하여 역할 그룹 보기</span><span class="sxs-lookup"><span data-stu-id="69dab-118">Use the EAC to view role groups</span></span>

1. <span data-ttu-id="69dab-119">EAC에서 사용 권한 **Permissions** 관리자 \> **역할로 이동합니다.**</span><span class="sxs-lookup"><span data-stu-id="69dab-119">In the EAC, go to **Permissions** \> **Admin roles**.</span></span> <span data-ttu-id="69dab-120">조직의 모든 역할 그룹이 여기에 나열됩니다.</span><span class="sxs-lookup"><span data-stu-id="69dab-120">All of the role groups in your organization are listed here.</span></span>

2. <span data-ttu-id="69dab-121">역할 그룹을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="69dab-121">Select a role group.</span></span> <span data-ttu-id="69dab-122">세부 정보 창에는 **Description**역할 **그룹의 이름,** **설명,** 할당된 **역할 및 관리되는** 역할이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="69dab-122">The Details pane shows the **Name**, **Description**, **Assigned roles**, and **Managed by** of the role group.</span></span> <span data-ttu-id="69dab-123">또한 편집 아이콘을 클릭하여 이 정보를 **볼** ![ 수 ](../../media/ITPro-EAC-EditIcon.png) 있습니다.</span><span class="sxs-lookup"><span data-stu-id="69dab-123">You can also see this information by clicking **Edit** ![Edit icon](../../media/ITPro-EAC-EditIcon.png).</span></span>

### <a name="use-the-eac-to-create-role-groups"></a><span data-ttu-id="69dab-124">EAC를 사용하여 역할 그룹 만들기</span><span class="sxs-lookup"><span data-stu-id="69dab-124">Use the EAC to create role groups</span></span>

<span data-ttu-id="69dab-125">새 역할 그룹을 만들 때, 모든 설정을 그 자체로 구성할 수 있습니다(그룹을 만드는 중이나 그룹을 만든 이후에).</span><span class="sxs-lookup"><span data-stu-id="69dab-125">When you create a new role group, you can configure all of the settings yourself (during the creation of the group or after).</span></span> <span data-ttu-id="69dab-126">또는 기존 역할 그룹을 복사하여 수정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="69dab-126">Or, you can copy an existing role group and modify it.</span></span>

1. <span data-ttu-id="69dab-127">EAC에서 사용 권한 **Permissions** 관리자 \> **역할로 이동한**후 다음 단계 중 하나를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="69dab-127">In the EAC, go to **Permissions** \> **Admin roles**, and then do one of the following steps:</span></span>

   - <span data-ttu-id="69dab-128">**수동으로 새 역할 그룹 만들기:** 추가 **아이콘을** ![ ](../../media/ITPro-EAC-AddIcon.png) 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="69dab-128">**Manually create a new role group**: Click **Add** ![Add icon](../../media/ITPro-EAC-AddIcon.png).</span></span>

   - <span data-ttu-id="69dab-129">**기존 역할 그룹 복사:** 복사할 역할 그룹을 선택한 다음 복사 아이콘을 **Copy** ![ ](../../media/ITPro-EAC-CopyIcon.png) 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="69dab-129">**Copy an existing role group**: Select the role group that you want to copy and then click **Copy** ![Copy icon](../../media/ITPro-EAC-CopyIcon.png).</span></span>

2. <span data-ttu-id="69dab-130">표시되는 **새 역할 그룹** 창에서 다음 설정을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="69dab-130">In the **New role group** window that appears, configure the following settings:</span></span>

    - <span data-ttu-id="69dab-131">**이름:** 역할 그룹의 고유한 이름을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="69dab-131">**Name**: Enter a unique name for the role group.</span></span>

    - <span data-ttu-id="69dab-132">**설명:** 역할 그룹에 대한 선택적 설명을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="69dab-132">**Description**: Enter an optional description for the role group.</span></span>

    - <span data-ttu-id="69dab-133">**역할:** 추가 **아이콘** ![ 추가ITPro-EAC-RemoveIcon.gif제거 ](../../media/ITPro-EAC-AddIcon.png) **아이콘을**ITPro-EAC-RemoveIcon.gif역할 그룹에 ![ ](../../media/ITPro-EAC-RemoveIcon.gif) 할당된 역할을 선택하거나 수정합니다.</span><span class="sxs-lookup"><span data-stu-id="69dab-133">**Roles**: Click **Add** ![Add icon](../../media/ITPro-EAC-AddIcon.png) or **Remove** ![ITPro-EAC-RemoveIcon.gif](../../media/ITPro-EAC-RemoveIcon.gif) to select or modify the roles that are assigned to the role group.</span></span>

    - <span data-ttu-id="69dab-134">**구성원:** 추가 **아이콘 추가** ![ ](../../media/ITPro-EAC-AddIcon.png) 또는 제거 **아이콘을** ![ITPro-EAC-RemoveIcon.gif구성원 ](../../media/ITPro-EAC-RemoveIcon.gif) 수정합니다.</span><span class="sxs-lookup"><span data-stu-id="69dab-134">**Members**: Click **Add** ![Add icon](../../media/ITPro-EAC-AddIcon.png) or **Remove** ![ITPro-EAC-RemoveIcon.gif](../../media/ITPro-EAC-RemoveIcon.gif) to modify the role group membership.</span></span>

3. <span data-ttu-id="69dab-135">작업이 끝나면 Save를 **클릭하여** 역할 그룹을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="69dab-135">When you're finished, click **Save** to create the role group.</span></span>

### <a name="use-the-eac-to-modify-role-groups"></a><span data-ttu-id="69dab-136">EAC를 사용하여 역할 그룹 수정</span><span class="sxs-lookup"><span data-stu-id="69dab-136">Use the EAC to modify role groups</span></span>

<span data-ttu-id="69dab-137">EAC에서 사용 권한 **Permissions** 관리자 \> **역할로 이동하고**수정할 역할 그룹을 선택한 다음 편집 아이콘을 **Edit** ![ ](../../media/ITPro-EAC-EditIcon.png) 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="69dab-137">In the EAC, go to **Permissions** \> **Admin roles**, select the role group you want to modify, and then click **Edit** ![Edit icon](../../media/ITPro-EAC-EditIcon.png).</span></span>

<span data-ttu-id="69dab-138">역할 그룹을 만들 때와 같은 옵션을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="69dab-138">The same options are available when you modify role groups as when you create role groups.</span></span> <span data-ttu-id="69dab-139">다음을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="69dab-139">You can:</span></span>

- <span data-ttu-id="69dab-140">이름과 설명을 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="69dab-140">Change the name and description.</span></span>

- <span data-ttu-id="69dab-141">관리 역할을 추가 및 제거합니다(역할 할당 만들기 또는 제거).</span><span class="sxs-lookup"><span data-stu-id="69dab-141">Add and remove management roles (create or remove role assignments).</span></span>

- <span data-ttu-id="69dab-142">구성원을 추가 및 제거할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="69dab-142">Add and remove members.</span></span>

<span data-ttu-id="69dab-143">**참고:** 일부 역할 그룹(예: 조직 관리)은 그룹에서 제거할 수 있는 역할을 제한합니다.</span><span class="sxs-lookup"><span data-stu-id="69dab-143">**Note**: Some role groups (for example, Organization Management) restrict the roles that you can remove from group.</span></span>

#### <a name="use-the-eac-modify-the-list-of-members-in-role-groups"></a><span data-ttu-id="69dab-144">EAC를 사용하여 역할 그룹의 구성원 목록 수정</span><span class="sxs-lookup"><span data-stu-id="69dab-144">Use the EAC modify the list of members in role groups</span></span>

1. <span data-ttu-id="69dab-145">EAC에서 사용 **권한** 관리자 \> **역할로 이동하고**수정할 역할 그룹을 선택한 다음 편집 아이콘을 **클릭합니다.** ![ ](../../media/ITPro-EAC-EditIcon.png)</span><span class="sxs-lookup"><span data-stu-id="69dab-145">In the EAC, go to **Permissions** \> **Admin roles**, select the role group that you want to modify, and then click **Edit** ![Edit icon](../../media/ITPro-EAC-EditIcon.png).</span></span>

2. <span data-ttu-id="69dab-146">열리는 역할 그룹 속성 페이지의 **구성원** 섹션에서 다음 단계 중 하나를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="69dab-146">In the role group properties page that opens, in the **Members** section, do either of the following steps:</span></span>

   - <span data-ttu-id="69dab-147">추가 **아이콘을** ![ 클릭합니다. ](../../media/ITPro-EAC-AddIcon.png)</span><span class="sxs-lookup"><span data-stu-id="69dab-147">Click **Add** ![Add Icon](../../media/ITPro-EAC-AddIcon.png).</span></span> <span data-ttu-id="69dab-148">나타나는 페이지에서 추가하려는 사용자를 찾은 다음 \*\*-200번 클릭하고 >. \*\*</span><span class="sxs-lookup"><span data-stu-id="69dab-148">In the page that appears, find the user that wou want to add, and then click **add ->**.</span></span> <span data-ttu-id="69dab-149">사용자를 선택한 다음 **추가 ->** 여러 번 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="69dab-149">Select users and click **add ->** many times as necessary.</span></span> <span data-ttu-id="69dab-150">작업을 마친 후 **확인**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="69dab-150">When you're finished, click **OK**.</span></span>

   - <span data-ttu-id="69dab-151">제거할 사용자를 선택한 다음 제거 아이콘 **Remove** 제거를 ![ ](../../media/ITPro-EAC-RemoveIcon.gif) 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="69dab-151">Select the users that you want to remove, and then click **Remove** ![Remove icon](../../media/ITPro-EAC-RemoveIcon.gif).</span></span>

3. <span data-ttu-id="69dab-152">작업을 마쳤으면 **저장**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="69dab-152">When you're finished, click **Save**.</span></span>

   > [!NOTE]
   > <span data-ttu-id="69dab-153">구성원을 역할 그룹에 추가하거나 역할 그룹에서 제거한 후 사용자가 관리 권한 변경 내용을 확인하려면 로그아웃했다가 다시 로그인해야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="69dab-153">Users may have to sign out and sign in again to see the change in their administrative rights after you add or remove members from the role group.</span></span>

### <a name="use-the-eac-to-remove-role-groups"></a><span data-ttu-id="69dab-154">EAC를 사용하여 역할 그룹 제거</span><span class="sxs-lookup"><span data-stu-id="69dab-154">Use the EAC to remove role groups</span></span>

<span data-ttu-id="69dab-155">기본 제공 역할 그룹은 제거할 수 없지만 사용자가 만든 사용자 지정 역할 그룹을 제거할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="69dab-155">You can't remove built-in role groups, but you can remove custom role groups that you've created.</span></span>

1. <span data-ttu-id="69dab-156">EAC에서 사용 권한 **Permissions** 관리자 \> **역할로 이동합니다.**</span><span class="sxs-lookup"><span data-stu-id="69dab-156">In the EAC, go to **Permissions** \> **Admin roles**.</span></span>

2. <span data-ttu-id="69dab-157">제거할 역할 그룹을 선택한 다음 삭제 **아이콘을** ![ ](../../media/ITPro-EAC-DeleteIcon.png) 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="69dab-157">Select the role group you want to remove and then click **Delete** ![Delete icon](../../media/ITPro-EAC-DeleteIcon.png).</span></span>

3. <span data-ttu-id="69dab-158">표시되는 **확인** 창에서 예를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="69dab-158">Click **Yes** in the confirmation window that appears.</span></span>

## <a name="use-powershell-to-manage-role-groups"></a><span data-ttu-id="69dab-159">PowerShell을 사용하여 역할 그룹 관리</span><span class="sxs-lookup"><span data-stu-id="69dab-159">Use PowerShell to manage role groups</span></span>

### <a name="use-standalone-eop-powershell-to-view-role-groups"></a><span data-ttu-id="69dab-160">독립 실행형 EOP PowerShell을 사용하여 역할 그룹 보기</span><span class="sxs-lookup"><span data-stu-id="69dab-160">Use standalone EOP PowerShell to view role groups</span></span>

<span data-ttu-id="69dab-161">역할 그룹을 보기 위해 다음 구문을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="69dab-161">To view a role group, use the following syntax:</span></span>

```PowerShell
Get-RoleGroup [-Identity "<Role Group Name>"] [-Filter <Filter>]
```

<span data-ttu-id="69dab-162">이 예에서는 모든 역할 그룹의 요약 목록을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="69dab-162">This example returns a summary list of all role groups.</span></span>

```PowerShell
Get-RoleGroup
```

<span data-ttu-id="69dab-163">이 예에서는 Recipient Administrators라는 역할 그룹에 대한 세부 정보를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="69dab-163">This example returns detailed information for the role group named Recipient Administrators.</span></span>

```PowerShell
Get-RoleGroup -Identity "Recipient Administrators" | Format-List
```

<span data-ttu-id="69dab-164">이 예에서는 Julia사용자가 구성원인 모든 역할 그룹을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="69dab-164">This example returns all role groups where the user Julia is a member.</span></span> <span data-ttu-id="69dab-165">다음 명령을 실행하여 찾을 수 있는 프리미어의 경우 DN(DistinguishedName) 값을 `Get-User -Identity Julia | Format-List DistinguishedName` 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="69dab-165">You need to use the DistinguishedName (DN) value for Julia, which you can find by running the command: `Get-User -Identity Julia | Format-List DistinguishedName`.</span></span>

```PowerShell
Get-RoleGroup -Filter "Members -eq 'CN=Julia,OU=contoso.onmicrosoft.com,OU=Microsoft Exchange Hosted Organizations,DC=NAMPR001,DC=PROD,DC=OUTLOOK,DC=COM'"
```

<span data-ttu-id="69dab-166">구문과 매개 변수에 대한 자세한 내용은 [Get-RoleGroup를 참조하십시오.](https://docs.microsoft.com/powershell/module/exchange/Get-RoleGroup)</span><span class="sxs-lookup"><span data-stu-id="69dab-166">For detailed syntax and parameter information, see [Get-RoleGroup](https://docs.microsoft.com/powershell/module/exchange/Get-RoleGroup).</span></span>

### <a name="use-standalone-eop-powershell-to-create-role-groups"></a><span data-ttu-id="69dab-167">독립 실행형 EOP PowerShell을 사용하여 역할 그룹 만들기</span><span class="sxs-lookup"><span data-stu-id="69dab-167">Use standalone EOP PowerShell to create role groups</span></span>

<span data-ttu-id="69dab-168">새 역할 그룹을 만들 때, (그룹 을 만들 때 또는 그룹 을 만드는 동안 중이나 후에) 모든 설정을 수동으로 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="69dab-168">When you create a new role group, you can configure all of the settings manually (during the creation of the group or after).</span></span> <span data-ttu-id="69dab-169">또는 기존 역할 그룹을 복사하여 수정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="69dab-169">Or, you can copy an existing role group and modify it.</span></span>

- <span data-ttu-id="69dab-170">새 역할 그룹을 수동으로 만들려면 다음 구문을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="69dab-170">To manually create a new role group, use the following syntax:</span></span>

  ```PowerShell
  New-RoleGroup -Name "Unique Name" -Description "Descriptive text" -Roles <"Role1","Role2"...>
  ```

  - <span data-ttu-id="69dab-171">_Roles 매개_ 변수는 다음 구문을 사용하여 역할 그룹에 할당할 관리 역할을 `"Role1","Role1",..."RoleN"` 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="69dab-171">The _Roles_ parameter specifies the management roles to assign to the role group by using the following syntax `"Role1","Role1",..."RoleN"`.</span></span> <span data-ttu-id="69dab-172">**Get-ManagementRole** cmdlet을 사용하여 사용 가능한 역할을 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="69dab-172">You can see the available roles by using the **Get-ManagementRole** cmdlet.</span></span>

  - <span data-ttu-id="69dab-173">_Members 매개_ 변수는 다음 구문을 사용하여 역할 그룹의 구성원을 `"Member1","Member2",..."MemberN"` 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="69dab-173">The _Members_ parameter specifies the members of the role group by using the following syntax: `"Member1","Member2",..."MemberN"`.</span></span> <span data-ttu-id="69dab-174">사용자, 메일 사용이 가능한 USG(유니버설 보안 그룹) 또는 기타 역할 그룹(보안 주체)을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="69dab-174">You can specify users, mail-enabled universal security groups (USGs), or other role groups (security principals).</span></span>

  <span data-ttu-id="69dab-175">이 예에서는 다음 설정으로 "Limited Recipient Management"라는 새 역할 그룹을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="69dab-175">This example creates a new role group named "Limited Recipient Management" with the following settings:</span></span>

  - <span data-ttu-id="69dab-176">역할 그룹에는 Mail Recipients 역할이 할당됩니다.</span><span class="sxs-lookup"><span data-stu-id="69dab-176">The Mail Recipients role is assigned to the role group.</span></span>

  - <span data-ttu-id="69dab-177">사용자 Kim과 Martin이 구성원으로 추가됩니다.</span><span class="sxs-lookup"><span data-stu-id="69dab-177">The users Kim and Martin are added as members.</span></span>

  ```PowerShell
  New-RoleGroup -Name "Limited Recipient Management" -Roles "Mail Recipients" -Members "Kim","Martin"
  ```

- <span data-ttu-id="69dab-178">기존 역할 그룹을 복사하려면 다음 단계를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="69dab-178">To copy an existing role group, do the following steps:</span></span>

  1. <span data-ttu-id="69dab-179">다음 구문을 사용하여 복사할 역할 그룹을 변수에 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="69dab-179">Store the role group that you want to copy in a variable using the following syntax:</span></span>

     ```PowerShell
     $RoleGroup = Get-RoleGroup "<Existing Role Group Name>"
     ```

  2. <span data-ttu-id="69dab-180">다음 구문을 사용하여 새 역할 그룹을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="69dab-180">Create the new role group using the following syntax:</span></span>

     ```PowerShell
     New-RoleGroup -Name "<Unique Name>" -Roles $RoleGroup.Roles [-Members <Members>]
     ```

     <span data-ttu-id="69dab-181">_Members 매개_ 변수는 다음 구문을 사용하여 역할 그룹의 구성원을 `"Member1","Member2",..."MemberN"` 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="69dab-181">The _Members_ parameter specifies the members of the role group by using the following syntax: `"Member1","Member2",..."MemberN"`.</span></span> <span data-ttu-id="69dab-182">사용자, 메일 사용이 가능한 USG(유니버설 보안 그룹) 또는 기타 역할 그룹(보안 주체)을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="69dab-182">You can specify users, mail-enabled universal security groups (USGs), or other role groups (security principals).</span></span>

     <span data-ttu-id="69dab-183">이 예에서는 Organization Management 역할 그룹을 "Limited Organization Management"라는 새 역할 그룹에 복사합니다.</span><span class="sxs-lookup"><span data-stu-id="69dab-183">This example copies the Organization Management role group to the new role group named "Limited Organization Management".</span></span> <span data-ttu-id="69dab-184">역할 그룹 구성원은 Isabelle, Carter 및 Lukas입니다.</span><span class="sxs-lookup"><span data-stu-id="69dab-184">The role group members are Isabelle, Carter, and Lukas.</span></span>

     ```PowerShell
     $RoleGroup = Get-RoleGroup "Organization Management"
     New-RoleGroup "Limited Organization Management" -Roles $RoleGroup.Roles -Members "Isabelle","Carter","Lukas"
     ```

<span data-ttu-id="69dab-185">구문과 매개 변수에 대한 자세한 내용은 [New-RoleGroup.](https://docs.microsoft.com/powershell/module/exchange/New-RoleGroup)</span><span class="sxs-lookup"><span data-stu-id="69dab-185">For detailed syntax and parameter information, [New-RoleGroup](https://docs.microsoft.com/powershell/module/exchange/New-RoleGroup).</span></span>

### <a name="use-standalone-eop-powershell-modify-the-list-of-members-in-role-groups"></a><span data-ttu-id="69dab-186">역할 그룹의 구성원 목록 목록 수정 독립 실행형 EOP PowerShell 사용</span><span class="sxs-lookup"><span data-stu-id="69dab-186">Use standalone EOP PowerShell modify the list of members in role groups</span></span>

- <span data-ttu-id="69dab-187">**Add-RoleGroupMember 및** **Remove-RoleGroupMember** cmdlet은 한 번에 하나의 개별 구성원을 추가하거나 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="69dab-187">The **Add-RoleGroupMember** and **Remove-RoleGroupMember** cmdlets add or remove individual members one at a time.</span></span> <span data-ttu-id="69dab-188">**Update-RoleGroupMember** cmdlet을 사용하면 기존 구성원 목록을 바꾸거나 수정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="69dab-188">The **Update-RoleGroupMember** cmdlet can replace or modify the existing list of members.</span></span>

- <span data-ttu-id="69dab-189">역할 그룹의 구성원은 사용자, 메일 사용이 가능한 USG(유니버설 보안 그룹) 또는 다른 역할 그룹(보안 주체)일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="69dab-189">The members of a role group can be users, mail-enabled universal security groups (USGs), or other role groups (security principals).</span></span>

<span data-ttu-id="69dab-190">역할 그룹의 구성원을 수정하려면 다음 구문을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="69dab-190">To modify the members of a role group, use the following syntax:</span></span>

```PowerShell
Update-RoleGroupMember -Identity "<Role Group Name>" -Members <Members>
```

- <span data-ttu-id="69dab-191">기존 _구성원_ 목록을 지정한 값으로 바꿀 때는 다음 구문을 `"Member1","Member2",..."MemberN"` 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="69dab-191">To _replace_ the existing list of members with the values you specify, use the following syntax: `"Member1","Member2",..."MemberN"`.</span></span>

- <span data-ttu-id="69dab-192">기존 _구성원 목록을 선택적으로_ 수정하려면 다음 구문을 사용합니다. `@{Add="Member1","Member2"...; Remove="Member3","Member4"...}`</span><span class="sxs-lookup"><span data-stu-id="69dab-192">To _selectively modify_ the existing list of members, use the following syntax: `@{Add="Member1","Member2"...; Remove="Member3","Member4"...}`.</span></span>

<span data-ttu-id="69dab-193">이 예에서는 Help Desk 역할 그룹의 현재 구성원을 지정된 사용자로 바합니다.</span><span class="sxs-lookup"><span data-stu-id="69dab-193">This example replaces all current members of the Help Desk role group with the specified users.</span></span>

```PowerShell
Update-RoleGroupMember -Identity "Help Desk" -Members "Gabriela Laureano","Hyun-Ae Rim","Jacob Berger"
```

<span data-ttu-id="69dab-194">다음은 Help Desk 역할 그룹의 구성원 목록에서 Daigoro Akai를 추가하고 Valeria Barrio를 제거하는 예제입니다.</span><span class="sxs-lookup"><span data-stu-id="69dab-194">This example adds Daigoro Akai and removes Valeria Barrio from the list of members on the Help Desk role group.</span></span>

```PowerShell
Update-RoleGroupMember -Identity "Help Desk" -Members @{Add="Daigoro Akai"; Remove="Valeria Barrios"}
```

<span data-ttu-id="69dab-195">구문과 매개 변수에 대한 자세한 내용은 [Update-RoleGroupMember를 참조하십시오.](https://docs.microsoft.com/powershell/module/exchange/Update-RoleGroupMember)</span><span class="sxs-lookup"><span data-stu-id="69dab-195">For detailed syntax and parameter information, see [Update-RoleGroupMember](https://docs.microsoft.com/powershell/module/exchange/Update-RoleGroupMember).</span></span>

### <a name="use-standalone-eop-powershell-to-remove-role-groups"></a><span data-ttu-id="69dab-196">독립 실행형 EOP PowerShell을 사용하여 역할 그룹 제거</span><span class="sxs-lookup"><span data-stu-id="69dab-196">Use standalone EOP PowerShell to remove role groups</span></span>

<span data-ttu-id="69dab-197">기본 제공 역할 그룹은 제거할 수 없지만 사용자가 만든 사용자 지정 역할 그룹을 제거할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="69dab-197">You can't remove built-in role groups, but you can remove custom role groups that you've created.</span></span>

<span data-ttu-id="69dab-198">사용자 지정 역할 그룹을 제거하려면 다음 구문을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="69dab-198">To remove a custom role group, use the following syntax:</span></span>

```PowerShell
Remove-RoleGroup -Identity "<Role Group Name>" [-BypassSecurityGroupManagerCheck]
```

<span data-ttu-id="69dab-199">이 예에서는 Training Administrators 역할 그룹을 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="69dab-199">This example removes the Training Administrators role group.</span></span>

```PowerShell
Remove-RoleGroup -Identity "Training Administrators"
```

<span data-ttu-id="69dab-200">구문과 매개 변수에 대한 자세한 내용은 [Remove-RoleGroup](https://docs.microsoft.com/powershell/module/exchange/Remove-RoleGroup)를 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="69dab-200">For detailed syntax and parameter information, see [Remove-RoleGroup](https://docs.microsoft.com/powershell/module/exchange/Remove-RoleGroup).</span></span>

### <a name="how-do-you-know-these-procedures-worked"></a><span data-ttu-id="69dab-201">이 절차가 제대로 수행되었는지 어떻게 확인하나요?</span><span class="sxs-lookup"><span data-stu-id="69dab-201">How do you know these procedures worked?</span></span>

<span data-ttu-id="69dab-202">역할 그룹이 성공적으로 복사되었는지 확인하려면 다음 단계 중 하나를 수행하십시오.</span><span class="sxs-lookup"><span data-stu-id="69dab-202">To verify that you've successfully copied a role group, do either of the following steps:</span></span>

- <span data-ttu-id="69dab-203">EAC에서 사용 권한 **Permissions** 관리자 \> **역할로 이동한**후 역할 그룹이 나열되는지 또는 나열되지 않았는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="69dab-203">In the EAC, go to **Permissions** \> **Admin roles**, and verify the role group is listed (or not listed).</span></span> <span data-ttu-id="69dab-204">역할 그룹을 선택한 다음 세부 정보 창에서 설정을 확인하거나 편집 아이콘을 **클릭하여** ![ ](../../media/ITPro-EAC-EditIcon.png) 설정을 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="69dab-204">Select the role group, and verify the settings in the Details pane or click **Edit** ![Edit icon](../../media/ITPro-EAC-EditIcon.png) to verify the settings.</span></span>

- <span data-ttu-id="69dab-205">Exchange Online PowerShell에서 역할 그룹의 이름으로 바꾸고, 다음 명령을 실행하여 역할 그룹이 존재하는지(또는 존재하지 \<Role Group Name\> 않는지)를 확인하고 설정을 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="69dab-205">In Exchange Online PowerShell, replace \<Role Group Name\> with the name of the role group, and run the following command to verify the role group exists (or doesn't exist) and verify the settings:</span></span>

    ```PowerShell
    Get-RoleGroup -Identity "<Role Group Name>" | Format-List
    ```
