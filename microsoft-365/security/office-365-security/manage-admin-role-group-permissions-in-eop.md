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
localization_priority: Normal
ms.assetid: 125834f4-1024-4325-ad5a-d2573cfb005e
description: 관리자는 Exchange Online Protection의 EAC(Exchange 관리 센터)에서 사용 권한을 할당하거나 제거하는 방법을 배울 수 있습니다.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 5e712c47d49508934ec7dd2438beff00eb6e1a20
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/25/2021
ms.locfileid: "51206276"
---
# <a name="manage-role-groups-in-standalone-eop"></a><span data-ttu-id="f48e1-103">독립 실행형 EOP에서 역할 그룹 관리</span><span class="sxs-lookup"><span data-stu-id="f48e1-103">Manage role groups in standalone EOP</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="f48e1-104">**적용 대상**</span><span class="sxs-lookup"><span data-stu-id="f48e1-104">**Applies to**</span></span>
-  [<span data-ttu-id="f48e1-105">Exchange Online Protection 독립 실행형</span><span class="sxs-lookup"><span data-stu-id="f48e1-105">Exchange Online Protection standalone</span></span>](exchange-online-protection-overview.md)

<span data-ttu-id="f48e1-106">Exchange Online 사서함이 없는 독립 실행형 EOP(Exchange Online Protection) 조직에서는 EAC(Exchange 관리 센터)를 사용하여 역할 그룹에 사용자를 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f48e1-106">In standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, you can use the Exchange admin center (EAC) to add users to role groups.</span></span> <span data-ttu-id="f48e1-107">역할 그룹에 사용자를 추가하면 사용자에게 특정 관리 작업을 수행할 수 있는 권한이 부여됩니다.</span><span class="sxs-lookup"><span data-stu-id="f48e1-107">Adding a users to a role group gives the user permissions to do specific admin tasks.</span></span> <span data-ttu-id="f48e1-108">역할 그룹에서 사용자를 제거할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f48e1-108">You can also remove users from role groups.</span></span>

<span data-ttu-id="f48e1-109">역할 및 역할 그룹에 대한 자세한 내용은 독립 실행형 [EOP의 사용 권한을 참조하세요.](feature-permissions-in-eop.md)</span><span class="sxs-lookup"><span data-stu-id="f48e1-109">For more information about roles and role groups, see [Permissions in standalone EOP](feature-permissions-in-eop.md).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="f48e1-110">시작하기 전에 알아야 할 내용</span><span class="sxs-lookup"><span data-stu-id="f48e1-110">What do you need to know before you begin?</span></span>

- <span data-ttu-id="f48e1-111">EAC(Exchange 관리 센터)를 열하려면 독립 실행형 [EOP의 Exchange 관리 센터를 참조하세요.](exchange-admin-center-in-exchange-online-protection-eop.md)</span><span class="sxs-lookup"><span data-stu-id="f48e1-111">To open the Exchange admin center (EAC), see [Exchange admin center in standalone EOP](exchange-admin-center-in-exchange-online-protection-eop.md).</span></span>

- <span data-ttu-id="f48e1-112">독립 실행형 EOP PowerShell을 열기 위해 [Exchange Online Protection PowerShell에 연결을 참조하세요.](/powershell/exchange/connect-to-exchange-online-protection-powershell)</span><span class="sxs-lookup"><span data-stu-id="f48e1-112">To open standalone EOP PowerShell, see [Connect to Exchange Online Protection PowerShell](/powershell/exchange/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="f48e1-113">이 문서의 절차를 수행하려면 먼저 Exchange Online Protection에서 사용 권한을 할당해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f48e1-113">You need to be assigned permissions in Exchange Online Protection before you can do the procedures in this article.</span></span> <span data-ttu-id="f48e1-114">특히 조직 관리  역할 그룹에 기본적으로 할당되는 역할 관리 **역할이** 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="f48e1-114">Specifically, you need the **Role Management** role, which is assigned to the **Organization Management** role group by default.</span></span> <span data-ttu-id="f48e1-115">자세한 내용은 독립 실행형 [EOP의](feature-permissions-in-eop.md) 사용 권한 및 EAC를 사용하여 역할 그룹의 구성원 목록 [수정을 참조하세요.](manage-admin-role-group-permissions-in-eop.md#use-the-eac-modify-the-list-of-members-in-role-groups)</span><span class="sxs-lookup"><span data-stu-id="f48e1-115">For more information, see [Permissions in standalone EOP](feature-permissions-in-eop.md) and [Use the EAC modify the list of members in role groups](manage-admin-role-group-permissions-in-eop.md#use-the-eac-modify-the-list-of-members-in-role-groups).</span></span>

- <span data-ttu-id="f48e1-116">이 문서의 절차에 적용할 수 있는 바로 가기 키에 대한 자세한 내용은 Exchange Online의 Exchange 관리 센터에 대한 바로 가기 키를 [참조하세요.](/Exchange/accessibility/keyboard-shortcuts-in-admin-center)</span><span class="sxs-lookup"><span data-stu-id="f48e1-116">For information about keyboard shortcuts that may apply to the procedures in this article, see [Keyboard shortcuts for the Exchange admin center in Exchange Online](/Exchange/accessibility/keyboard-shortcuts-in-admin-center).</span></span>

> [!TIP]
> <span data-ttu-id="f48e1-117">문제가 있나요?</span><span class="sxs-lookup"><span data-stu-id="f48e1-117">Having problems?</span></span> <span data-ttu-id="f48e1-118">[Exchange Online Protection](https://social.technet.microsoft.com/Forums/forefront/home?forum=FOPE) 포럼에서 도움을 요청하세요.</span><span class="sxs-lookup"><span data-stu-id="f48e1-118">Ask for help in the [Exchange Online Protection](https://social.technet.microsoft.com/Forums/forefront/home?forum=FOPE) forum.</span></span>

## <a name="use-the-eac-to-manage-role-groups"></a><span data-ttu-id="f48e1-119">EAC를 사용하여 역할 그룹 관리</span><span class="sxs-lookup"><span data-stu-id="f48e1-119">Use the EAC to manage role groups</span></span>

### <a name="use-the-eac-to-view-role-groups"></a><span data-ttu-id="f48e1-120">EAC를 사용하여 역할 그룹 보기</span><span class="sxs-lookup"><span data-stu-id="f48e1-120">Use the EAC to view role groups</span></span>

1. <span data-ttu-id="f48e1-121">EAC에서 사용 권한  관리자 \> **역할로 이동하세요.**</span><span class="sxs-lookup"><span data-stu-id="f48e1-121">In the EAC, go to **Permissions** \> **Admin roles**.</span></span> <span data-ttu-id="f48e1-122">조직의 모든 역할 그룹이 여기에 나열됩니다.</span><span class="sxs-lookup"><span data-stu-id="f48e1-122">All of the role groups in your organization are listed here.</span></span>

2. <span data-ttu-id="f48e1-123">역할 그룹을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="f48e1-123">Select a role group.</span></span> <span data-ttu-id="f48e1-124">세부 정보 창에는 역할 그룹의 **이름,** **설명,** **할당된** 역할 및 관리 **역할이** 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="f48e1-124">The Details pane shows the **Name**, **Description**, **Assigned roles**, and **Managed by** of the role group.</span></span> <span data-ttu-id="f48e1-125">편집 편집 아이콘 을 클릭하여 이 **정보를 볼** ![ 수도 ](../../media/ITPro-EAC-EditIcon.png) 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f48e1-125">You can also see this information by clicking **Edit** ![Edit icon](../../media/ITPro-EAC-EditIcon.png).</span></span>

### <a name="use-the-eac-to-create-role-groups"></a><span data-ttu-id="f48e1-126">EAC를 사용하여 역할 그룹 만들기</span><span class="sxs-lookup"><span data-stu-id="f48e1-126">Use the EAC to create role groups</span></span>

<span data-ttu-id="f48e1-127">새 역할 그룹을 만들 때 모든 설정을 직접 구성할 수 있습니다(그룹을 만드는 동안 또는 이후에).</span><span class="sxs-lookup"><span data-stu-id="f48e1-127">When you create a new role group, you can configure all of the settings yourself (during the creation of the group or after).</span></span> <span data-ttu-id="f48e1-128">또는 기존 역할 그룹을 복사하여 수정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f48e1-128">Or, you can copy an existing role group and modify it.</span></span>

1. <span data-ttu-id="f48e1-129">EAC에서 사용 권한  관리자 역할로 이동한 후 다음 단계 중 \> 하나를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="f48e1-129">In the EAC, go to **Permissions** \> **Admin roles**, and then do one of the following steps:</span></span>

   - <span data-ttu-id="f48e1-130">**수동으로 새 역할 그룹 만들기**: 추가 아이콘 **추가를** ![ ](../../media/ITPro-EAC-AddIcon.png) 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="f48e1-130">**Manually create a new role group**: Click **Add** ![Add icon](../../media/ITPro-EAC-AddIcon.png).</span></span>

   - <span data-ttu-id="f48e1-131">**기존 역할 그룹 복사:** 복사할 역할 그룹을 선택한 다음 복사 아이콘 **복사를** ![ ](../../media/ITPro-EAC-CopyIcon.png) 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="f48e1-131">**Copy an existing role group**: Select the role group that you want to copy and then click **Copy** ![Copy icon](../../media/ITPro-EAC-CopyIcon.png).</span></span>

2. <span data-ttu-id="f48e1-132">나타나는 **새 역할 그룹** 창에서 다음 설정을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="f48e1-132">In the **New role group** window that appears, configure the following settings:</span></span>

    - <span data-ttu-id="f48e1-133">**이름:** 역할 그룹의 고유한 이름을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="f48e1-133">**Name**: Enter a unique name for the role group.</span></span>

    - <span data-ttu-id="f48e1-134">**설명:** 역할 그룹에 대한 선택적 설명을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="f48e1-134">**Description**: Enter an optional description for the role group.</span></span>

    - <span data-ttu-id="f48e1-135">**역할:** **추가 아이콘 추가** 또는 제거 아이콘 제거를 클릭하여 역할 그룹에 할당된 역할을 선택하거나 ![ ](../../media/ITPro-EAC-AddIcon.png)  ![ ](../../media/ITPro-EAC-RemoveIcon.gif) 수정합니다.</span><span class="sxs-lookup"><span data-stu-id="f48e1-135">**Roles**: Click **Add** ![Add icon](../../media/ITPro-EAC-AddIcon.png) or **Remove** ![Remove icon](../../media/ITPro-EAC-RemoveIcon.gif) to select or modify the roles that are assigned to the role group.</span></span>

    - <span data-ttu-id="f48e1-136">**구성원:** **추가 아이콘 추가** 또는 제거 아이콘 제거를 클릭하여 역할 그룹 ![ ](../../media/ITPro-EAC-AddIcon.png)  ![ ](../../media/ITPro-EAC-RemoveIcon.gif) 구성원을 수정합니다.</span><span class="sxs-lookup"><span data-stu-id="f48e1-136">**Members**: Click **Add** ![Add icon](../../media/ITPro-EAC-AddIcon.png) or **Remove** ![Remove icon](../../media/ITPro-EAC-RemoveIcon.gif) to modify the role group membership.</span></span>

3. <span data-ttu-id="f48e1-137">완료되면 저장을 **클릭하여** 역할 그룹을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f48e1-137">When you're finished, click **Save** to create the role group.</span></span>

### <a name="use-the-eac-to-modify-role-groups"></a><span data-ttu-id="f48e1-138">EAC를 사용하여 역할 그룹 수정</span><span class="sxs-lookup"><span data-stu-id="f48e1-138">Use the EAC to modify role groups</span></span>

<span data-ttu-id="f48e1-139">EAC에서 사용 권한  관리자 역할로 이동하여 수정할 역할 그룹을 선택한 다음 편집 편집 아이콘 \>   ![ 을 ](../../media/ITPro-EAC-EditIcon.png) 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="f48e1-139">In the EAC, go to **Permissions** \> **Admin roles**, select the role group you want to modify, and then click **Edit** ![Edit icon](../../media/ITPro-EAC-EditIcon.png).</span></span>

<span data-ttu-id="f48e1-140">역할 그룹을 만들 때와 역할 그룹을 수정할 때도 동일한 옵션을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f48e1-140">The same options are available when you modify role groups as when you create role groups.</span></span> <span data-ttu-id="f48e1-141">다음을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f48e1-141">You can:</span></span>

- <span data-ttu-id="f48e1-142">이름과 설명을 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="f48e1-142">Change the name and description.</span></span>

- <span data-ttu-id="f48e1-143">관리 역할을 추가 및 제거합니다(역할 할당 만들기 또는 제거).</span><span class="sxs-lookup"><span data-stu-id="f48e1-143">Add and remove management roles (create or remove role assignments).</span></span>

- <span data-ttu-id="f48e1-144">구성원을 추가 및 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="f48e1-144">Add and remove members.</span></span>

<span data-ttu-id="f48e1-145">**참고:** 조직 관리와 같은 일부 역할 그룹은 그룹에서 제거할 수 있는 역할을 제한합니다.</span><span class="sxs-lookup"><span data-stu-id="f48e1-145">**Note**: Some role groups (for example, Organization Management) restrict the roles that you can remove from group.</span></span>

#### <a name="use-the-eac-modify-the-list-of-members-in-role-groups"></a><span data-ttu-id="f48e1-146">EAC를 사용하여 역할 그룹의 구성원 목록 수정</span><span class="sxs-lookup"><span data-stu-id="f48e1-146">Use the EAC modify the list of members in role groups</span></span>

1. <span data-ttu-id="f48e1-147">EAC에서 사용 권한  관리자 역할로 이동하여 수정할 역할 그룹을 선택한 다음 편집 편집 아이콘 \>   ![ 을 ](../../media/ITPro-EAC-EditIcon.png) 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="f48e1-147">In the EAC, go to **Permissions** \> **Admin roles**, select the role group that you want to modify, and then click **Edit** ![Edit icon](../../media/ITPro-EAC-EditIcon.png).</span></span>

2. <span data-ttu-id="f48e1-148">열 수 있는 역할 그룹 속성 페이지의 **구성원** 섹션에서 다음 단계 중 하나를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="f48e1-148">In the role group properties page that opens, in the **Members** section, do either of the following steps:</span></span>

   - <span data-ttu-id="f48e1-149">아이콘 **추가를** ![ ](../../media/ITPro-EAC-AddIcon.png) 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="f48e1-149">Click **Add** ![Add Icon](../../media/ITPro-EAC-AddIcon.png).</span></span> <span data-ttu-id="f48e1-150">나타나는 페이지에서 wou를 추가할 사용자를 찾은 다음 추가 **->.**</span><span class="sxs-lookup"><span data-stu-id="f48e1-150">In the page that appears, find the user that wou want to add, and then click **add ->**.</span></span> <span data-ttu-id="f48e1-151">사용자를 선택하고 필요한 경우 **>추가를** 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="f48e1-151">Select users and click **add ->** many times as necessary.</span></span> <span data-ttu-id="f48e1-152">작업을 마친 후 **확인** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="f48e1-152">When you're finished, click **OK**.</span></span>

   - <span data-ttu-id="f48e1-153">제거할 사용자를 선택한 다음 제거 아이콘 **를** ![ ](../../media/ITPro-EAC-RemoveIcon.gif) 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="f48e1-153">Select the users that you want to remove, and then click **Remove** ![Remove icon](../../media/ITPro-EAC-RemoveIcon.gif).</span></span>

3. <span data-ttu-id="f48e1-154">작업을 마친 후 **저장** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="f48e1-154">When you're finished, click **Save**.</span></span>

   > [!NOTE]
   > <span data-ttu-id="f48e1-155">구성원을 역할 그룹에 추가하거나 역할 그룹에서 제거한 후 사용자가 관리 권한 변경 내용을 확인하려면 로그아웃했다가 다시 로그인해야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f48e1-155">Users may have to sign out and sign in again to see the change in their administrative rights after you add or remove members from the role group.</span></span>

### <a name="use-the-eac-to-remove-role-groups"></a><span data-ttu-id="f48e1-156">EAC를 사용하여 역할 그룹 제거</span><span class="sxs-lookup"><span data-stu-id="f48e1-156">Use the EAC to remove role groups</span></span>

<span data-ttu-id="f48e1-157">기본 제공 역할 그룹을 제거할 수 없지만 만든 사용자 지정 역할 그룹을 제거할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f48e1-157">You can't remove built-in role groups, but you can remove custom role groups that you've created.</span></span>

1. <span data-ttu-id="f48e1-158">EAC에서 사용 권한  관리자 \> **역할로 이동하세요.**</span><span class="sxs-lookup"><span data-stu-id="f48e1-158">In the EAC, go to **Permissions** \> **Admin roles**.</span></span>

2. <span data-ttu-id="f48e1-159">제거할 역할 그룹을 선택한 다음 삭제 **삭제** 아이콘 ![ 을 ](../../media/ITPro-EAC-DeleteIcon.png) 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="f48e1-159">Select the role group you want to remove and then click **Delete** ![Delete icon](../../media/ITPro-EAC-DeleteIcon.png).</span></span>

3. <span data-ttu-id="f48e1-160">나타나는  확인 창에서 예를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="f48e1-160">Click **Yes** in the confirmation window that appears.</span></span>

## <a name="use-powershell-to-manage-role-groups"></a><span data-ttu-id="f48e1-161">PowerShell을 사용하여 역할 그룹 관리</span><span class="sxs-lookup"><span data-stu-id="f48e1-161">Use PowerShell to manage role groups</span></span>

### <a name="use-standalone-eop-powershell-to-view-role-groups"></a><span data-ttu-id="f48e1-162">독립 실행형 EOP PowerShell을 사용하여 역할 그룹 보기</span><span class="sxs-lookup"><span data-stu-id="f48e1-162">Use standalone EOP PowerShell to view role groups</span></span>

<span data-ttu-id="f48e1-163">역할 그룹을 보기 위해 다음 구문을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="f48e1-163">To view a role group, use the following syntax:</span></span>

```PowerShell
Get-RoleGroup [-Identity "<Role Group Name>"] [-Filter <Filter>]
```

<span data-ttu-id="f48e1-164">이 예에서는 모든 역할 그룹의 요약 목록을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="f48e1-164">This example returns a summary list of all role groups.</span></span>

```PowerShell
Get-RoleGroup
```

<span data-ttu-id="f48e1-165">이 예에서는 Recipient Administrators라는 역할 그룹에 대한 자세한 정보를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="f48e1-165">This example returns detailed information for the role group named Recipient Administrators.</span></span>

```PowerShell
Get-RoleGroup -Identity "Recipient Administrators" | Format-List
```

<span data-ttu-id="f48e1-166">이 예에서는 사용자 Julia가 구성원인 모든 역할 그룹을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="f48e1-166">This example returns all role groups where the user Julia is a member.</span></span> <span data-ttu-id="f48e1-167">다음 명령을 실행하여 찾을 수 있는 Julia에 대해 DN(DistinguishedName) 값을 사용해야 `Get-User -Identity Julia | Format-List DistinguishedName` 합니다.</span><span class="sxs-lookup"><span data-stu-id="f48e1-167">You need to use the DistinguishedName (DN) value for Julia, which you can find by running the command: `Get-User -Identity Julia | Format-List DistinguishedName`.</span></span>

```PowerShell
Get-RoleGroup -Filter "Members -eq 'CN=Julia,OU=contoso.onmicrosoft.com,OU=Microsoft Exchange Hosted Organizations,DC=NAMPR001,DC=PROD,DC=OUTLOOK,DC=COM'"
```

<span data-ttu-id="f48e1-168">구문과 매개 변수에 대한 자세한 내용은 [Get-RoleGroup을 참조하십시오.](/powershell/module/exchange/Get-RoleGroup)</span><span class="sxs-lookup"><span data-stu-id="f48e1-168">For detailed syntax and parameter information, see [Get-RoleGroup](/powershell/module/exchange/Get-RoleGroup).</span></span>

### <a name="use-standalone-eop-powershell-to-create-role-groups"></a><span data-ttu-id="f48e1-169">독립 실행형 EOP PowerShell을 사용하여 역할 그룹 만들기</span><span class="sxs-lookup"><span data-stu-id="f48e1-169">Use standalone EOP PowerShell to create role groups</span></span>

<span data-ttu-id="f48e1-170">새 역할 그룹을 만들 때 모든 설정을 수동으로 구성할 수 있습니다(그룹을 만드는 동안 또는 이후에).</span><span class="sxs-lookup"><span data-stu-id="f48e1-170">When you create a new role group, you can configure all of the settings manually (during the creation of the group or after).</span></span> <span data-ttu-id="f48e1-171">또는 기존 역할 그룹을 복사하여 수정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f48e1-171">Or, you can copy an existing role group and modify it.</span></span>

- <span data-ttu-id="f48e1-172">새 역할 그룹을 수동으로 만들하려면 다음 구문을 사용하세요.</span><span class="sxs-lookup"><span data-stu-id="f48e1-172">To manually create a new role group, use the following syntax:</span></span>

  ```PowerShell
  New-RoleGroup -Name "Unique Name" -Description "Descriptive text" -Roles <"Role1","Role2"...>
  ```

  - <span data-ttu-id="f48e1-173">Roles _매개_ 변수는 다음 구문을 사용하여 역할 그룹에 할당할 관리 역할을 `"Role1","Role1",..."RoleN"` 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="f48e1-173">The _Roles_ parameter specifies the management roles to assign to the role group by using the following syntax `"Role1","Role1",..."RoleN"`.</span></span> <span data-ttu-id="f48e1-174">**Get-ManagementRole** cmdlet을 사용하여 사용 가능한 역할을 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f48e1-174">You can see the available roles by using the **Get-ManagementRole** cmdlet.</span></span>

  - <span data-ttu-id="f48e1-175">_Members 매개_ 변수는 다음 구문을 사용하여 역할 그룹의 구성원을 `"Member1","Member2",..."MemberN"` 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="f48e1-175">The _Members_ parameter specifies the members of the role group by using the following syntax: `"Member1","Member2",..."MemberN"`.</span></span> <span data-ttu-id="f48e1-176">사용자, 메일 사용이 가능한 USG(유니버설 보안 그룹) 또는 기타 역할 그룹(보안 주체)을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f48e1-176">You can specify users, mail-enabled universal security groups (USGs), or other role groups (security principals).</span></span>

  <span data-ttu-id="f48e1-177">이 예에서는 다음 설정을 사용하여 "Limited Recipient Management"라는 새 역할 그룹을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="f48e1-177">This example creates a new role group named "Limited Recipient Management" with the following settings:</span></span>

  - <span data-ttu-id="f48e1-178">역할 그룹에는 Mail Recipients 역할이 할당됩니다.</span><span class="sxs-lookup"><span data-stu-id="f48e1-178">The Mail Recipients role is assigned to the role group.</span></span>

  - <span data-ttu-id="f48e1-179">사용자 Kim과 Martin이 구성원으로 추가됩니다.</span><span class="sxs-lookup"><span data-stu-id="f48e1-179">The users Kim and Martin are added as members.</span></span>

  ```PowerShell
  New-RoleGroup -Name "Limited Recipient Management" -Roles "Mail Recipients" -Members "Kim","Martin"
  ```

- <span data-ttu-id="f48e1-180">기존 역할 그룹을 복사하기 위해 다음 단계를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="f48e1-180">To copy an existing role group, do the following steps:</span></span>

  1. <span data-ttu-id="f48e1-181">다음 구문을 사용하여 복사할 역할 그룹을 변수에 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="f48e1-181">Store the role group that you want to copy in a variable using the following syntax:</span></span>

     ```PowerShell
     $RoleGroup = Get-RoleGroup "<Existing Role Group Name>"
     ```

  2. <span data-ttu-id="f48e1-182">다음 구문을 사용하여 새 역할 그룹을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f48e1-182">Create the new role group using the following syntax:</span></span>

     ```PowerShell
     New-RoleGroup -Name "<Unique Name>" -Roles $RoleGroup.Roles [-Members <Members>]
     ```

     <span data-ttu-id="f48e1-183">_Members 매개_ 변수는 다음 구문을 사용하여 역할 그룹의 구성원을 `"Member1","Member2",..."MemberN"` 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="f48e1-183">The _Members_ parameter specifies the members of the role group by using the following syntax: `"Member1","Member2",..."MemberN"`.</span></span> <span data-ttu-id="f48e1-184">사용자, 메일 사용이 가능한 USG(유니버설 보안 그룹) 또는 기타 역할 그룹(보안 주체)을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f48e1-184">You can specify users, mail-enabled universal security groups (USGs), or other role groups (security principals).</span></span>

     <span data-ttu-id="f48e1-185">이 예에서는 Organization Management 역할 그룹을 "Limited Organization Management"라는 새 역할 그룹에 복사합니다.</span><span class="sxs-lookup"><span data-stu-id="f48e1-185">This example copies the Organization Management role group to the new role group named "Limited Organization Management".</span></span> <span data-ttu-id="f48e1-186">역할 그룹 구성원은 Isabelle, Carter 및 Lukas입니다.</span><span class="sxs-lookup"><span data-stu-id="f48e1-186">The role group members are Isabelle, Carter, and Lukas.</span></span>

     ```PowerShell
     $RoleGroup = Get-RoleGroup "Organization Management"
     New-RoleGroup "Limited Organization Management" -Roles $RoleGroup.Roles -Members "Isabelle","Carter","Lukas"
     ```

<span data-ttu-id="f48e1-187">구문과 매개 변수에 대한 자세한 내용은 [New-RoleGroup 을 참조하십시오.](/powershell/module/exchange/New-RoleGroup)</span><span class="sxs-lookup"><span data-stu-id="f48e1-187">For detailed syntax and parameter information, [New-RoleGroup](/powershell/module/exchange/New-RoleGroup).</span></span>

### <a name="use-standalone-eop-powershell-modify-the-list-of-members-in-role-groups"></a><span data-ttu-id="f48e1-188">독립 실행형 EOP PowerShell 사용 역할 그룹의 구성원 목록 수정</span><span class="sxs-lookup"><span data-stu-id="f48e1-188">Use standalone EOP PowerShell modify the list of members in role groups</span></span>

- <span data-ttu-id="f48e1-189">**Add-RoleGroupMember** 및 **Remove-RoleGroupMember** cmdlet은 개별 구성원을 한 번씩 추가하거나 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="f48e1-189">The **Add-RoleGroupMember** and **Remove-RoleGroupMember** cmdlets add or remove individual members one at a time.</span></span> <span data-ttu-id="f48e1-190">**Update-RoleGroupMember** cmdlet은 기존 구성원 목록을 대체하거나 수정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f48e1-190">The **Update-RoleGroupMember** cmdlet can replace or modify the existing list of members.</span></span>

- <span data-ttu-id="f48e1-191">역할 그룹의 구성원은 사용자, 메일 사용이 가능한 USG(유니버설 보안 그룹) 또는 기타 역할 그룹(보안 주체)일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f48e1-191">The members of a role group can be users, mail-enabled universal security groups (USGs), or other role groups (security principals).</span></span>

<span data-ttu-id="f48e1-192">역할 그룹의 구성원을 수정하려면 다음 구문을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="f48e1-192">To modify the members of a role group, use the following syntax:</span></span>

```PowerShell
Update-RoleGroupMember -Identity "<Role Group Name>" -Members <Members>
```

- <span data-ttu-id="f48e1-193">기존 _구성원_ 목록을 지정한 값으로 바꾸기 위해 다음 구문을 `"Member1","Member2",..."MemberN"` 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="f48e1-193">To _replace_ the existing list of members with the values you specify, use the following syntax: `"Member1","Member2",..."MemberN"`.</span></span>

- <span data-ttu-id="f48e1-194">기존 _구성원 목록을_ 선택적으로 수정하려면 다음 구문을 사용하세요. `@{Add="Member1","Member2"...; Remove="Member3","Member4"...}` .</span><span class="sxs-lookup"><span data-stu-id="f48e1-194">To _selectively modify_ the existing list of members, use the following syntax: `@{Add="Member1","Member2"...; Remove="Member3","Member4"...}`.</span></span>

<span data-ttu-id="f48e1-195">이 예에서는 Help Desk 역할 그룹의 모든 현재 구성원을 지정된 사용자로 바 대체합니다.</span><span class="sxs-lookup"><span data-stu-id="f48e1-195">This example replaces all current members of the Help Desk role group with the specified users.</span></span>

```PowerShell
Update-RoleGroupMember -Identity "Help Desk" -Members "Gabriela Laureano","Hyun-Ae Rim","Jacob Berger"
```

<span data-ttu-id="f48e1-196">이 예에서는 Daigoro Akai를 추가하고 Help Desk 역할 그룹의 구성원 목록에서 Valeria Barrio를 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="f48e1-196">This example adds Daigoro Akai and removes Valeria Barrio from the list of members on the Help Desk role group.</span></span>

```PowerShell
Update-RoleGroupMember -Identity "Help Desk" -Members @{Add="Daigoro Akai"; Remove="Valeria Barrios"}
```

<span data-ttu-id="f48e1-197">구문과 매개 변수에 대한 자세한 내용은 [Update-RoleGroupMember 를 참조하십시오.](/powershell/module/exchange/Update-RoleGroupMember)</span><span class="sxs-lookup"><span data-stu-id="f48e1-197">For detailed syntax and parameter information, see [Update-RoleGroupMember](/powershell/module/exchange/Update-RoleGroupMember).</span></span>

### <a name="use-standalone-eop-powershell-to-remove-role-groups"></a><span data-ttu-id="f48e1-198">독립 실행형 EOP PowerShell을 사용하여 역할 그룹 제거</span><span class="sxs-lookup"><span data-stu-id="f48e1-198">Use standalone EOP PowerShell to remove role groups</span></span>

<span data-ttu-id="f48e1-199">기본 제공 역할 그룹을 제거할 수 없지만 만든 사용자 지정 역할 그룹을 제거할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f48e1-199">You can't remove built-in role groups, but you can remove custom role groups that you've created.</span></span>

<span data-ttu-id="f48e1-200">사용자 지정 역할 그룹을 제거하려면 다음 구문을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="f48e1-200">To remove a custom role group, use the following syntax:</span></span>

```PowerShell
Remove-RoleGroup -Identity "<Role Group Name>" [-BypassSecurityGroupManagerCheck]
```

<span data-ttu-id="f48e1-201">이 예에서는 Training Administrators 역할 그룹을 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="f48e1-201">This example removes the Training Administrators role group.</span></span>

```PowerShell
Remove-RoleGroup -Identity "Training Administrators"
```

<span data-ttu-id="f48e1-202">구문과 매개 변수에 대한 자세한 내용은 [Remove-RoleGroup](/powershell/module/exchange/Remove-RoleGroup)를 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="f48e1-202">For detailed syntax and parameter information, see [Remove-RoleGroup](/powershell/module/exchange/Remove-RoleGroup).</span></span>

### <a name="how-do-you-know-these-procedures-worked"></a><span data-ttu-id="f48e1-203">이 절차가 제대로 수행되었는지 어떻게 확인하나요?</span><span class="sxs-lookup"><span data-stu-id="f48e1-203">How do you know these procedures worked?</span></span>

<span data-ttu-id="f48e1-204">역할 그룹을 성공적으로 복사한지 확인하기 위해 다음 단계 중 하나를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="f48e1-204">To verify that you've successfully copied a role group, do either of the following steps:</span></span>

- <span data-ttu-id="f48e1-205">EAC에서 사용 권한  관리자 역할로 이동하여 역할 그룹이 나열되어 있는지(나열되지 \> 않은지) 확인해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f48e1-205">In the EAC, go to **Permissions** \> **Admin roles**, and verify the role group is listed (or not listed).</span></span> <span data-ttu-id="f48e1-206">역할 그룹을 선택하고 세부 정보 창에서 설정을 확인하거나  편집 편집 아이콘을 클릭하여 ![ 설정을 ](../../media/ITPro-EAC-EditIcon.png) 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="f48e1-206">Select the role group, and verify the settings in the Details pane or click **Edit** ![Edit icon](../../media/ITPro-EAC-EditIcon.png) to verify the settings.</span></span>

- <span data-ttu-id="f48e1-207">Exchange Online PowerShell에서 역할 그룹의 이름으로 바꾸고 다음 명령을 실행하여 역할 그룹이 존재하거나 존재하지 않는지 확인하고 설정을 \<Role Group Name\> 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="f48e1-207">In Exchange Online PowerShell, replace \<Role Group Name\> with the name of the role group, and run the following command to verify the role group exists (or doesn't exist) and verify the settings:</span></span>

    ```PowerShell
    Get-RoleGroup -Identity "<Role Group Name>" | Format-List
    ```