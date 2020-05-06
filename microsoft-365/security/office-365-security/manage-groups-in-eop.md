---
title: EOP에서 그룹 관리
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
ms.assetid: 212e68ac-6330-47e9-a169-6cf5e2f21e13
ms.custom:
- seo-marvel-apr2020
description: 이 문서에서는 EOP (Exchange Online Protection)에서 Exchange 조직에 대 한 메일 사용 가능 그룹을 만들고 관리 하는 방법을 알아봅니다.
ms.openlocfilehash: 37825175e3332e975065a3807c6ed9d5096b1a7f
ms.sourcegitcommit: a45cf8b887587a1810caf9afa354638e68ec5243
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/05/2020
ms.locfileid: "44034405"
---
# <a name="manage-groups-in-eop"></a><span data-ttu-id="358aa-103">EOP에서 그룹 관리</span><span class="sxs-lookup"><span data-stu-id="358aa-103">Manage groups in EOP</span></span>

 <span data-ttu-id="358aa-p101">EOP(Exchange Online Protection)를 사용하여 Exchange 조직에 메일 사용 가능 그룹을 만들 수 있습니다. 또한 구성원 자격, 전자 메일 주소 및 그룹의 기타 측면을 지정하는 그룹 속성을 정의하거나 업데이트할 수도 있습니다. 필요에 따라 메일 그룹 및 보안 그룹을 만들 수 있습니다. 이러한 그룹은 EAC(Exchange 관리 센터)를 사용하거나 원격 Windows PowerShell을 통해 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="358aa-p101">You can use Exchange Online Protection (EOP) to create mail-enabled groups for an Exchange organization. You can also use EOP to define or update group properties that specify membership, email addresses, and other aspects of groups. You can create distribution groups and security groups, depending on your needs. These groups can be created by using the Exchange admin center (EAC) or via remote Windows PowerShell.</span></span>

## <a name="types-of-mail-enabled-groups"></a><span data-ttu-id="358aa-108">메일 사용 가능 그룹의 유형</span><span class="sxs-lookup"><span data-stu-id="358aa-108">Types of mail-enabled groups</span></span>

<span data-ttu-id="358aa-109">Exchange 조직에 대해 다음과 같은 두 가지 유형의 그룹을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="358aa-109">You can create two types of groups for your Exchange organization:</span></span>

- <span data-ttu-id="358aa-110">메일 그룹은 일반적인 관심 영역과 관련 하 여 전자 메일을 받거나 보내야 하는 팀 또는 기타 특별 그룹 같은 전자 메일 사용자의 모음입니다.</span><span class="sxs-lookup"><span data-stu-id="358aa-110">Distribution groups are collections of email users, such as a team or other ad hoc group, who need to receive or send email regarding a common area of interest.</span></span> <span data-ttu-id="358aa-111">메일 그룹은 전자 메일 메시지 배포 전용으로 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="358aa-111">Distribution groups are exclusively for distributing email messages.</span></span> <span data-ttu-id="358aa-112">EOP에서 메일 그룹은 보안 컨텍스트 유무에 관계없이 모든 메일 사용 가능 그룹을 의미합니다.</span><span class="sxs-lookup"><span data-stu-id="358aa-112">In EOP, a distribution group refers to any mail-enabled group, whether or not it has a security context.</span></span>

- <span data-ttu-id="358aa-113">보안 그룹은 관리자 역할에 대 한 액세스 권한이 필요한 전자 메일 사용자의 모음입니다.</span><span class="sxs-lookup"><span data-stu-id="358aa-113">Security groups are collections of email users who need access permissions for Admin roles.</span></span> <span data-ttu-id="358aa-114">예를 들어 특정 사용자 그룹에게 스팸 방지 및 맬웨어 방지 설정을 구성할 수 있도록 관리자 역할 권한을 제공할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="358aa-114">For example, you might want to give specific group of users admin role permissions so they can configure anti-spam and anti-malware settings.</span></span>

    > [!NOTE]
    > <span data-ttu-id="358aa-p104">기본적으로 모든 새로운 메일 사용이 가능한 보안 그룹을 사용하려면 모든 보낸 사람에 대한 인증이 필요합니다. 따라서 외부 보낸 사람은 메일 사용이 가능한 보안 그룹에 메시지를 보낼 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="358aa-p104">By default, all new mail-enabled security groups require that all senders be authenticated. This prevents external senders from sending messages to mail-enabled security groups.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="358aa-117">시작하기 전에</span><span class="sxs-lookup"><span data-stu-id="358aa-117">Before you begin</span></span>

- <span data-ttu-id="358aa-p105">이러한 절차를 수행하려면 먼저 사용 권한을 할당받아야 합니다. 필요한 사용 권한을 확인하려면 다음을 참조하세요. [EOP의 기능 사용 권한](feature-permissions-in-eop.md) 항목의 "메일 그룹 및 보안 그룹" 항목</span><span class="sxs-lookup"><span data-stu-id="358aa-p105">You need to be assigned permissions before you can perform this procedure or procedures. To see what permissions you need, see the "Distribution Groups and Security Groups" entry in the [Feature permissions in EOP](feature-permissions-in-eop.md) topic.</span></span>

- <span data-ttu-id="358aa-120">Exchange 관리 센터를 열려면 exchange [Online Protection의 exchange 관리 센터](exchange-admin-center-in-exchange-online-protection-eop.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="358aa-120">To open the Exchange admin center, see [Exchange admin center in Exchange Online Protection](exchange-admin-center-in-exchange-online-protection-eop.md).</span></span>

- <span data-ttu-id="358aa-121">Exchange Online Protection PowerShell cmdlet을 사용 하 여 그룹을 만들고 관리할 때 제한이 발생할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="358aa-121">Be aware that when creating and managing groups by using Exchange Online Protection PowerShell cmdlets, you may encounter throttling.</span></span>

- <span data-ttu-id="358aa-122">이 항목의 PowerShell 절차에서는 일괄 처리 방법을 사용 하 여 명령 결과가 표시 되기까지 몇 분 정도 전파 지연을 발생 시킵니다.</span><span class="sxs-lookup"><span data-stu-id="358aa-122">The PowerShell procedures in this topic use a batch processing method that results in a propagation delay of a few minutes before the results of the commands are visible.</span></span>

- <span data-ttu-id="358aa-123">Windows PowerShell을 사용하여 Exchange Online Protection에 연결하는 방법에 대한 자세한 내용은 [Exchange Online Protection PowerShell에 연결](https://docs.microsoft.com/powershell/exchange/exchange-eop/connect-to-exchange-online-protection-powershell)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="358aa-123">To learn how to use Windows PowerShell to connect to Exchange Online Protection, see [Connect to Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-eop/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="358aa-124">이 항목의 절차에 적용할 수 있는 바로 가기 키에 대 한 자세한 내용은 [Exchange Online에서 exchange 관리 센터에 대 한 바로 가기 키](https://docs.microsoft.com/Exchange/accessibility/keyboard-shortcuts-in-admin-center)를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="358aa-124">For information about keyboard shortcuts that may apply to the procedures in this topic, see [Keyboard shortcuts for the Exchange admin center in Exchange Online](https://docs.microsoft.com/Exchange/accessibility/keyboard-shortcuts-in-admin-center).</span></span>

> [!TIP]
> <span data-ttu-id="358aa-125">문제가 있습니까?</span><span class="sxs-lookup"><span data-stu-id="358aa-125">Having problems?</span></span> <span data-ttu-id="358aa-126">[Exchange Online Protection](https://go.microsoft.com/fwlink/p/?linkId=285351) 포럼에서 도움을 요청 하세요.</span><span class="sxs-lookup"><span data-stu-id="358aa-126">Ask for help in the [Exchange Online Protection](https://go.microsoft.com/fwlink/p/?linkId=285351) forum.</span></span>

## <a name="create-a-group-in-the-eac"></a><span data-ttu-id="358aa-127">EAC에서 그룹 만들기</span><span class="sxs-lookup"><span data-stu-id="358aa-127">Create a group in the EAC</span></span>

1. <span data-ttu-id="358aa-128">EAC에서 **받는 사람** \> **그룹**으로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="358aa-128">In the EAC, go to **Recipients** \> **Groups**.</span></span>

2. <span data-ttu-id="358aa-129">필요 **New** ![에 따라 새](../../media/ITPro-EAC-AddIcon.gif)추가 아이콘을 클릭 한 다음 **메일 그룹** 또는 **보안 그룹**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="358aa-129">Click **New** ![Add Icon](../../media/ITPro-EAC-AddIcon.gif), and then click **Distribution group** or **Security group**, depending on your needs.</span></span>

3. <span data-ttu-id="358aa-130">**새 메일 그룹** 또는 **새 보안 그룹** 페이지에서 다음 설정을 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="358aa-130">On the **New distribution group** or **New security group** page, configure the following settings:</span></span>

   - <span data-ttu-id="358aa-131">**표시 이름**: 조직에서 고유 하며 EOP 사용자에 게 의미가 있는 표시 이름을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="358aa-131">**Display name**: Type a display name that's unique to your organization and meaningful to EOP users.</span></span> <span data-ttu-id="358aa-132">표시 이름은 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="358aa-132">The display name is required.</span></span>

   - <span data-ttu-id="358aa-133">**별칭**: 조직에서 고유한 그룹 별칭 (최대 64 자)을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="358aa-133">**Alias**: Type a group alias of up to 64 characters that's unique to your organization.</span></span> <span data-ttu-id="358aa-134">EOP 사용자가 전자 메일 메시지의 받는 사람: 줄에 입력하는 별칭은 그룹의 표시 이름으로 확인됩니다.</span><span class="sxs-lookup"><span data-stu-id="358aa-134">EOP users type the alias in the To: line of email messages and the alias resolves to the group's display name.</span></span> <span data-ttu-id="358aa-135">별칭을 변경하는 경우 그룹의 기본 SMTP 주소도 변경되며 새 별칭이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="358aa-135">If you change the alias, the primary SMTP address for the group also changes and will contain the new alias.</span></span> <span data-ttu-id="358aa-136">별칭은 필수 입력 필드입니다.</span><span class="sxs-lookup"><span data-stu-id="358aa-136">The alias is required.</span></span>

   - <span data-ttu-id="358aa-137">**설명**: 사용자가 그룹의 용도를 파악할 수 있도록 그룹에 대 한 설명을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="358aa-137">**Description**: Type a description of the group so that people will know the purpose of the group.</span></span>

   - <span data-ttu-id="358aa-138">**소유자**: 기본적으로 그룹을 만든 사람이 소유자입니다.</span><span class="sxs-lookup"><span data-stu-id="358aa-138">**Owners**: By default, the person who creates the group is the owner.</span></span> <span data-ttu-id="358aa-139">추가 아이콘](../../media/ITPro-EAC-AddIcon.gif) **추가** ![를 선택 하 여 소유자를 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="358aa-139">You can add an owner by choosing **Add** ![Add Icon](../../media/ITPro-EAC-AddIcon.gif).</span></span> <span data-ttu-id="358aa-140">모든 그룹에는 한 명 이상의 소유자가 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="358aa-140">All groups must have at least one owner.</span></span>

     > [!NOTE]
     > <span data-ttu-id="358aa-141">소유자는 그룹의 구성원이 아니어도 됩니다.</span><span class="sxs-lookup"><span data-stu-id="358aa-141">Owners don't have to be members of the group.</span></span>

   - <span data-ttu-id="358aa-142">**구성원**:이 섹션을 사용 하 여 그룹 구성원을 추가 하 고 사용자가 그룹에 가입 하거나 탈퇴 하는 데 승인이 필요한 지 여부를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="358aa-142">**Members**: Use this section to add group members and to specify whether approval is required for people to join or leave the group.</span></span> <span data-ttu-id="358aa-143">그룹에 구성원을 추가 하려면 ![추가](../../media/ITPro-EAC-AddIcon.gif)아이콘 **추가를 클릭 합니다** .</span><span class="sxs-lookup"><span data-stu-id="358aa-143">To add members to the group, click **Add** ![Add Icon](../../media/ITPro-EAC-AddIcon.gif).</span></span>

4. <span data-ttu-id="358aa-144">**확인**을 클릭하여 원래 페이지로 돌아갑니다.</span><span class="sxs-lookup"><span data-stu-id="358aa-144">Click **OK** to return to the original page.</span></span>

5. <span data-ttu-id="358aa-p111">작업을 마치면 **저장**을 클릭하여 그룹을 만듭니다. 그러면 새 그룹이 그룹 목록에 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="358aa-p111">When you've finished, click **Save** to create the group. The new group should appear in the list of groups.</span></span>

## <a name="edit-or-remove-a-group-in-the-eac"></a><span data-ttu-id="358aa-147">EAC에서 그룹 편집 또는 제거</span><span class="sxs-lookup"><span data-stu-id="358aa-147">Edit or remove a group in the EAC</span></span>

1. <span data-ttu-id="358aa-148">EAC에서 **받는 사람** \> **그룹**으로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="358aa-148">In the EAC, navigate to **Recipients** \> **Groups**.</span></span>

2. <span data-ttu-id="358aa-149">다음 단계 중 하나를 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="358aa-149">Do one of the following steps:</span></span>

   - <span data-ttu-id="358aa-150">그룹을 편집 하려면 그룹 목록에서 보거나 변경 하려는 그룹을 클릭 한 다음 편집 아이콘](../../media/ITPro-EAC-EditIcon.gif) **편집** ![을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="358aa-150">To edit a group: In the list of groups, click the group that you want to view or change, and then click **Edit** ![Edit icon](../../media/ITPro-EAC-EditIcon.gif).</span></span> <span data-ttu-id="358aa-151">일반 설정을 업데이트 하 고, 그룹 소유자를 추가 또는 제거 하 고, 필요에 따라 그룹 구성원을 추가 또는 제거할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="358aa-151">You can update general settings, add or remove group owners, and add or remove group members as needed.</span></span>

   - <span data-ttu-id="358aa-152">그룹을 제거 하려면 그룹을 선택 하 고 제거 **Remove** ![아이콘](../../media/ITPro-EAC-RemoveIcon.gif)제거를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="358aa-152">To remove a group: Select the group and click **Remove** ![Remove icon](../../media/ITPro-EAC-RemoveIcon.gif).</span></span>

3. <span data-ttu-id="358aa-153">변경을 마치면 **저장**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="358aa-153">When you're finished making your changes, click **Save**.</span></span>

## <a name="create-edit-or-remove-a-group-using-remote-windows-powershell"></a><span data-ttu-id="358aa-154">원격 Windows PowerShell을 사용하여 그룹 만들기, 편집 또는 제거</span><span class="sxs-lookup"><span data-stu-id="358aa-154">Create, edit, or remove a group using remote Windows PowerShell</span></span>

<span data-ttu-id="358aa-155">이 섹션에서는 Exchange Online Protection PowerShell에서 그룹을 만들고 속성을 변경 하는 방법에 대 한 정보를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="358aa-155">This section provides information about creating groups and changing their properties in Exchange Online Protection PowerShell.</span></span> <span data-ttu-id="358aa-156">또한 기존 그룹을 제거하는 방법도 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="358aa-156">It also shows how to remove an existing group.</span></span>

### <a name="create-a-group-using-remote-windows-powershell"></a><span data-ttu-id="358aa-157">원격 Windows PowerShell을 사용 하 여 그룹 만들기</span><span class="sxs-lookup"><span data-stu-id="358aa-157">Create a group using remote Windows PowerShell</span></span>

<span data-ttu-id="358aa-p114">이 예제에서는 [New-EOPDistributionGroup](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/New-EOPDistributionGroup) cmdlet을 사용하여 별칭이 itadmin이고 이름이 IT Administrators인 메일 그룹을 만듭니다. 또한 사용자를 그룹의 구성원으로 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="358aa-p114">This example uses the [New-EOPDistributionGroup](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/New-EOPDistributionGroup) cmdlet to create a distribution group with an alias of itadmin and the name IT Administrators. It also adds users as members of the group.</span></span>

```PowerShell
New-EOPDistributionGroup -Type Distribution -Name "IT Administrators" -Alias itadmin -Members @("Member1","Member2","Member3") -ManagedBy Member1
```

<span data-ttu-id="358aa-160">**참고**: 메일 그룹 대신 보안 그룹을 만들려면 `Security` *Type* 매개 변수의 값을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="358aa-160">**Note**: To create a security group instead of a distribution group, use the value `Security` for the *Type* parameter.</span></span>

<span data-ttu-id="358aa-161">IT Administrators 그룹을 성공적으로 만들었는지 확인 하려면 다음 명령을 실행 하 여 새 그룹에 대 한 정보를 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="358aa-161">To verify that you've successfully created the IT Administrators group, run the following command to display information about the new group:</span></span>

```PowerShell
Get-Recipient "IT Administrators" | Format-List
```

<span data-ttu-id="358aa-162">구문과 매개 변수에 대 한 자세한 내용은 [Get-Recipient](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/Get-Recipient)를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="358aa-162">For detailed syntax and parameter information, see [Get-Recipient](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/Get-Recipient).</span></span>

<span data-ttu-id="358aa-163">그룹의 구성원 목록을 가져오려면 다음 명령을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="358aa-163">To get a list of members in the group, run the following command:</span></span>

```PowerShell
Get-DistributionGroupMember "IT Administrators"
```

<span data-ttu-id="358aa-164">구문과 매개 변수에 대 한 자세한 내용은 [get-distributiongroupmember](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/get-distributiongroupmember)를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="358aa-164">For detailed syntax and parameter information, see [Get-DistributionGroupMember](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/get-distributiongroupmember).</span></span>

<span data-ttu-id="358aa-165">모든 그룹의 전체 목록을 보려면 다음 명령을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="358aa-165">To get a full list of all your groups, run the following command:</span></span>

```PowerShell
Get-Recipient -RecipientType "MailUniversalDistributionGroup" | Format-Table | more
```

### <a name="change-the-properties-of-a-group-using-remote-windows-powershell"></a><span data-ttu-id="358aa-166">원격 Windows PowerShell을 사용 하 여 그룹의 속성 변경</span><span class="sxs-lookup"><span data-stu-id="358aa-166">Change the properties of a group using remote Windows PowerShell</span></span>

<span data-ttu-id="358aa-167">EAC 대신 PowerShell을 사용 하는 경우의 이점은 여러 그룹의 속성을 변경할 수 있다는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="358aa-167">An advantage of using PowerShell instead of the EAC is the ability to change properties for multiple groups.</span></span>

<span data-ttu-id="358aa-168">다음은 Exchange Online Protection PowerShell을 사용 하 여 그룹 속성을 변경 하는 몇 가지 예입니다.</span><span class="sxs-lookup"><span data-stu-id="358aa-168">Here are some examples of using Exchange Online Protection PowerShell to change group properties.</span></span>

<span data-ttu-id="358aa-169">이 예에서는 시애틀 Employees 그룹에 대 한 기본 SMTP 주소 (회신 주소 라고도 함)가 sea.employees@contoso.com로 변경 됩니다.</span><span class="sxs-lookup"><span data-stu-id="358aa-169">This example uses changes the primary SMTP address (also called the reply address) for the Seattle Employees group to sea.employees@contoso.com.</span></span>

```PowerShell
Set-EOPDistributionGroup "Seattle Employees" -PrimarysmptAddress "sea.employees@contoso.com"
```

<span data-ttu-id="358aa-170">구문 및 매개 변수에 대 한 자세한 내용은 [set-eopdistributiongroup](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/set-eopdistributiongroup)를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="358aa-170">For detailed syntax and parameter information, see [Set-EOPDistributionGroup](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/set-eopdistributiongroup).</span></span>

<span data-ttu-id="358aa-171">그룹의 속성을 성공적으로 변경 했는지 확인 하려면 다음 명령을 실행 하 여 새 값을 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="358aa-171">To verify that you've successfully changed the properties for the group, run the following command to verify the new value:</span></span>

```PowerShell
Get-Recipient "Seattle Employees" | Format-List "PrimarySmtpAddress"
```

<span data-ttu-id="358aa-172">이 예에서는 시애틀 Employees 그룹의 모든 구성원을 업데이트 합니다.</span><span class="sxs-lookup"><span data-stu-id="358aa-172">This example updates all the members of the Seattle Employees group.</span></span> <span data-ttu-id="358aa-173">모든 구성원은 쉼표로 구분합니다.</span><span class="sxs-lookup"><span data-stu-id="358aa-173">Use a comma to separate all members.</span></span>

```PowerShell
Update-EOPDistributionGroupMember -Identity "Seattle Employees" -Members @("Member1","Member2","Member3","Member4","Member5")
```

<span data-ttu-id="358aa-174">구문과 매개 변수에 대 한 자세한 내용은 [에서는 update-eopdistributiongroupmember](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/update-eopdistributiongroupmember)를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="358aa-174">For detailed syntax and parameter information, see [Update-EOPDistributionGroupMember](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/update-eopdistributiongroupmember).</span></span>

<span data-ttu-id="358aa-175">시애틀 직원 그룹의 모든 구성원 목록을 가져오려면 다음 명령을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="358aa-175">To get the list of all the members in the group Seattle Employees, run the following command:</span></span>

```PowerShell
Get-DistributionGroupMember "Seattle Employees"
```

### <a name="remove-a-group-using-remote-windows-powershell"></a><span data-ttu-id="358aa-176">원격 Windows PowerShell을 사용 하 여 그룹 제거</span><span class="sxs-lookup"><span data-stu-id="358aa-176">Remove a group using remote Windows PowerShell</span></span>

<span data-ttu-id="358aa-177">이 예에서는 IT Administrators 라는 메일 그룹을 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="358aa-177">This example uses removes the distribution group named IT Administrators.</span></span>

```PowerShell
Remove-EOPDistributionGroup -Identity "IT Administrators"
```

<span data-ttu-id="358aa-178">구문과 매개 변수에 대 한 자세한 내용은 [set-eopdistributiongroup](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/remove-eopdistributiongroup)를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="358aa-178">For detailed syntax and parameter information, see [Remove-EOPDistributionGroup](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/remove-eopdistributiongroup).</span></span>

<span data-ttu-id="358aa-179">그룹이 제거 되었는지 확인 하려면 다음 명령을 실행 하 여 그룹 (이 경우 "It Administrators")이 삭제 되었는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="358aa-179">To verify that the group was removed, run the following command, and confirm that the group (in this case "It Administrators") was deleted.</span></span>

```PowerShell
Get-Recipient -RecipientType "MailUniversalDistributionGroup"
```
