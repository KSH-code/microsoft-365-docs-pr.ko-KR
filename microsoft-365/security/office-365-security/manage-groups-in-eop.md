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
description: EOP (독립 실행형 Exchange Online Protection) 조직의 관리자는 EAC (Exchange 관리 센터) 및 EOP (독립 실행형 Exchange Online Protection) PowerShell에서 메일 그룹을 만들고, 수정 하 고, 제거 하는 방법을 알 수 있습니다.
ms.openlocfilehash: fc3f3807216b269a9868e87c5ec784d75385f878
ms.sourcegitcommit: 93c0088d272cd45f1632a1dcaf04159f234abccd
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/12/2020
ms.locfileid: "44209022"
---
# <a name="manage-groups-in-eop"></a><span data-ttu-id="c1c6e-103">EOP에서 그룹 관리</span><span class="sxs-lookup"><span data-stu-id="c1c6e-103">Manage groups in EOP</span></span>

<span data-ttu-id="c1c6e-104">Exchange Online 사서함이 없는 독립 실행형 EOP (Exchange Online Protection) 조직에서는 다음과 같은 유형의 그룹을 만들고, 수정 하 고, 제거할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c1c6e-104">In standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, you can create, modify, and remove the following types of groups:</span></span>

- <span data-ttu-id="c1c6e-105">**메일 그룹**: 메일 사용자 또는 기타 메일 그룹 모음입니다.</span><span class="sxs-lookup"><span data-stu-id="c1c6e-105">**Distribution groups**: A collection of mail users or other distribution groups.</span></span> <span data-ttu-id="c1c6e-106">예를 들어 일반적인 관심 영역에서 전자 메일을 수신 하거나 보내야 하는 팀 또는 기타 특별 그룹을 들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c1c6e-106">For example, teams or other ad hoc groups who need to receive or send email in a common area of interest.</span></span> <span data-ttu-id="c1c6e-107">전자 메일 메시지를 배포 하는 데 단독으로 사용 되는 메일 그룹은 보안 주체가 아니라 해당 사용자에 게 할당 권한을 부여할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="c1c6e-107">Distribution groups are exclusively for distributing email messages, and are not security principals (they can't have permissions assigned to them).</span></span>

- <span data-ttu-id="c1c6e-108">**메일 사용이 가능한 보안 그룹**: 관리 역할에 대 한 액세스 권한이 필요한 메일 사용자 및 기타 보안 그룹 모음입니다.</span><span class="sxs-lookup"><span data-stu-id="c1c6e-108">**Mail-enabled security groups**: A collection of mail users and other security groups who need access permissions for admin roles.</span></span> <span data-ttu-id="c1c6e-109">예를 들어 특정 사용자 그룹에 게 스팸 방지 및 맬웨어 방지 설정을 구성할 수 있도록 관리자 권한을 부여할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c1c6e-109">For example, you might want to give specific group of users admin permissions so they can configure anti-spam and anti-malware settings.</span></span>

    > [!NOTE]
    > <ul><li><span data-ttu-id="c1c6e-110">기본적으로 새로운 메일 사용이 가능한 보안 그룹은 인증 되지 않은 외부 보낸 사람의 메시지를 거부 합니다.</span><span class="sxs-lookup"><span data-stu-id="c1c6e-110">By default, new mail-enabled security groups reject messages from external (unauthenticated) senders.</span></span></li><li><span data-ttu-id="c1c6e-111">메일 사용이 가능한 보안 그룹에 메일 그룹을 추가 하지 마세요.</span><span class="sxs-lookup"><span data-stu-id="c1c6e-111">Don't add distribution groups to mail-enabled security groups.</span></span></li></ul><span data-ttu-id="c1c6e-112">.</span><span class="sxs-lookup"><span data-stu-id="c1c6e-112">.</span></span>

<span data-ttu-id="c1c6e-113">EAC (Exchange 관리 센터) 및 독립 실행형 EOP PowerShell에서 그룹을 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c1c6e-113">You can manage groups in the Exchange admin center (EAC) and in standalone EOP PowerShell.</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="c1c6e-114">시작하기 전에 알아야 할 사항은 무엇인가요?</span><span class="sxs-lookup"><span data-stu-id="c1c6e-114">What do you need to know before you begin?</span></span>

- <span data-ttu-id="c1c6e-115">Exchange 관리 센터를 열려면 [독립 실행형 EOP에서 exchange 관리 센터](exchange-admin-center-in-exchange-online-protection-eop.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="c1c6e-115">To open the Exchange admin center, see [Exchange admin center in standalone EOP](exchange-admin-center-in-exchange-online-protection-eop.md).</span></span>

- <span data-ttu-id="c1c6e-116">독립 실행형 EOP PowerShell에 연결 하려면 [Exchange Online Protection PowerShell에 연결](https://docs.microsoft.com/powershell/exchange/exchange-eop/connect-to-exchange-online-protection-powershell)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="c1c6e-116">To connect to standalone EOP PowerShell, see [Connect to Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-eop/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="c1c6e-117">독립 실행형 EOP PowerShell에서 그룹을 관리 하는 경우 제한이 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c1c6e-117">When you manage groups in standalone EOP PowerShell, you might encounter throttling.</span></span> <span data-ttu-id="c1c6e-118">이 항목의 PowerShell 절차에서는 일괄 처리 방법을 사용 하 여 명령 결과가 표시 되기까지 몇 분 정도 전파 지연을 발생 시킵니다.</span><span class="sxs-lookup"><span data-stu-id="c1c6e-118">The PowerShell procedures in this topic use a batch processing method that results in a propagation delay of a few minutes before the results of the commands are visible.</span></span>

- <span data-ttu-id="c1c6e-119">이 절차를 수행하려면 먼저 사용 권한을 할당받아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c1c6e-119">You need to be assigned permissions before you can perform these procedures.</span></span> <span data-ttu-id="c1c6e-120">특히 OrganizationManagement (전역 관리자) 및 RecipientManagement 역할 그룹에 기본적으로 할당 되는 메일 그룹 역할이 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="c1c6e-120">Specifically, you need the Distribution Groups role, which is assigned to the OrganizationManagement (global admins) and RecipientManagement role groups by default.</span></span> <span data-ttu-id="c1c6e-121">자세한 내용은 [권한 독립 실행형 EOP의 사용 권한을](feature-permissions-in-eop.md) 참조 하 고 [EAC를 사용 하 여 역할 그룹의 구성원 목록을 수정](manage-admin-role-group-permissions-in-eop.md#use-the-eac-modify-the-list-of-members-in-role-groups)합니다.</span><span class="sxs-lookup"><span data-stu-id="c1c6e-121">For more information, see [Permissions in standalone EOP](feature-permissions-in-eop.md) and [Use the EAC modify the list of members in role groups](manage-admin-role-group-permissions-in-eop.md#use-the-eac-modify-the-list-of-members-in-role-groups).</span></span>

- <span data-ttu-id="c1c6e-122">이 항목의 절차에 적용할 수 있는 바로 가기 키에 대 한 자세한 내용은 [Exchange Online에서 exchange 관리 센터에 대 한 바로 가기 키](https://docs.microsoft.com/Exchange/accessibility/keyboard-shortcuts-in-admin-center)를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="c1c6e-122">For information about keyboard shortcuts that may apply to the procedures in this topic, see [Keyboard shortcuts for the Exchange admin center in Exchange Online](https://docs.microsoft.com/Exchange/accessibility/keyboard-shortcuts-in-admin-center).</span></span>

> [!TIP]
> <span data-ttu-id="c1c6e-123">문제가 있습니까?</span><span class="sxs-lookup"><span data-stu-id="c1c6e-123">Having problems?</span></span> <span data-ttu-id="c1c6e-124">[Exchange Online Protection](https://go.microsoft.com/fwlink/p/?linkId=285351) 포럼에서 도움을 요청 하세요.</span><span class="sxs-lookup"><span data-stu-id="c1c6e-124">Ask for help in the [Exchange Online Protection](https://go.microsoft.com/fwlink/p/?linkId=285351) forum.</span></span>

## <a name="use-the-exchange-admin-center-to-manage-distribution-groups"></a><span data-ttu-id="c1c6e-125">Exchange 관리 센터를 사용 하 여 메일 그룹 관리</span><span class="sxs-lookup"><span data-stu-id="c1c6e-125">Use the Exchange admin center to manage distribution groups</span></span>

### <a name="use-the-eac-to-create-groups"></a><span data-ttu-id="c1c6e-126">EAC를 사용 하 여 그룹 만들기</span><span class="sxs-lookup"><span data-stu-id="c1c6e-126">Use the EAC to create groups</span></span>

1. <span data-ttu-id="c1c6e-127">EAC에서 **받는 사람** \> **그룹**으로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="c1c6e-127">In the EAC, go to **Recipients** \> **Groups**.</span></span>

2. <span data-ttu-id="c1c6e-128">**새로** ![ 만들기 아이콘 ](../../media/ITPro-EAC-AddIcon.png) 을 클릭 하 고 다음 옵션 중 하나를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="c1c6e-128">Click **New** ![New icon](../../media/ITPro-EAC-AddIcon.png), and then select one of the following options:</span></span>

   - <span data-ttu-id="c1c6e-129">**메일 그룹**</span><span class="sxs-lookup"><span data-stu-id="c1c6e-129">**Distribution group**</span></span>

   - <span data-ttu-id="c1c6e-130">**메일 사용 가능 보안 그룹**</span><span class="sxs-lookup"><span data-stu-id="c1c6e-130">**Mail-enabled security group**</span></span>

3. <span data-ttu-id="c1c6e-131">새 그룹 페이지가 열리면 다음 설정을 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="c1c6e-131">In the new group page that opens, configure the following settings.</span></span> <span data-ttu-id="c1c6e-132">로 표시 된 설정은 <sup>\*</sup> 필수입니다.</span><span class="sxs-lookup"><span data-stu-id="c1c6e-132">Settings marked with an <sup>\*</sup> are required.</span></span>

   - <span data-ttu-id="c1c6e-133"><sup>\*</sup>**표시 이름**:이 이름은 조직의 주소록, 받는 사람: 줄 (이 그룹에 전자 메일을 보낸 경우) 및 EAC의 **그룹** 목록에 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c1c6e-133"><sup>\*</sup>**Display name**: This name appears in your organization's address book, on the To: line when email is sent to this group, and in the **Groups** list in the EAC.</span></span> <span data-ttu-id="c1c6e-134">표시 이름은 필수 이며 고유 해야 하며, 사용자가 해당 항목을 인식할 수 있도록 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c1c6e-134">The display name is required, must be unique, and should be user-friendly so people recognize what it is.</span></span>

   - <span data-ttu-id="c1c6e-135"><sup>\*</sup>**별칭**:이 상자에 그룹의 별칭 이름을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="c1c6e-135"><sup>\*</sup>**Alias**: Use this box to type the name of the alias for the group.</span></span> <span data-ttu-id="c1c6e-136">별칭은 64 자를 초과할 수 없으며 고유 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c1c6e-136">The alias can't exceed 64 characters and must be unique.</span></span> <span data-ttu-id="c1c6e-137">사용자가 전자 메일 메시지의 To 줄에 별칭을 입력 하면 그룹의 표시 이름으로 확인 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c1c6e-137">When a user types the alias in the To line of an email message, it resolves to the group's display name.</span></span>

   - <span data-ttu-id="c1c6e-138"><sup>\*</sup>**전자 메일 주소**: 전자 메일 주소는 @ 기호 왼쪽의 별칭 및 오른쪽에 있는 도메인으로 구성 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c1c6e-138"><sup>\*</sup>**Email address**: The email address consists of the alias on the left side of the at (@) symbol, and a domain on the right side.</span></span> <span data-ttu-id="c1c6e-139">**별칭 값** 은 기본적으로 별칭 값에 사용 되지만 변경할 수는 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c1c6e-139">By default, the value of **Alias** is used for the alias value, but you can change it.</span></span> <span data-ttu-id="c1c6e-140">도메인 값의 경우 조직에서 드롭다운 및 선택 및 허용 도메인을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="c1c6e-140">For the domain value, click the drop down and select and accepted domain in your organization.</span></span>

   - <span data-ttu-id="c1c6e-141">**설명**:이 설명은 주소록과 EAC의 세부 정보 창에 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="c1c6e-141">**Description**: This description appears in the address book and in the Details pane in the EAC.</span></span>

   - <span data-ttu-id="c1c6e-142"><sup>\*</sup>**소유자**: 그룹 소유자는 그룹 구성원을 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c1c6e-142"><sup>\*</sup>**Owners**: A group owner can manage group membership.</span></span> <span data-ttu-id="c1c6e-143">기본적으로 그룹을 만든 사람이 소유자가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c1c6e-143">By default, the person who creates a group is the owner.</span></span> <span data-ttu-id="c1c6e-144">모든 그룹에는 한 명 이상의 소유자가 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c1c6e-144">All groups must have at least one owner.</span></span>

     <span data-ttu-id="c1c6e-145">소유자를 추가 하려면 추가 아이콘 **추가를 클릭** ![ ](../../media/ITPro-EAC-AddIcon.png) 합니다.</span><span class="sxs-lookup"><span data-stu-id="c1c6e-145">To add owners, click **Add** ![Add icon](../../media/ITPro-EAC-AddIcon.png).</span></span> <span data-ttu-id="c1c6e-146">대화 상자가 나타나면 받는 사람 또는 그룹을 찾아 선택한 다음 **추가 >** 를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="c1c6e-146">In the dialog that appears, find and select a recipient or group, and then click **add ->**.</span></span> <span data-ttu-id="c1c6e-147">필요한 만큼 이 단계를 반복합니다.</span><span class="sxs-lookup"><span data-stu-id="c1c6e-147">Repeat this step as many times as necessary.</span></span> <span data-ttu-id="c1c6e-148">작업을 마친 후 **확인**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="c1c6e-148">When you're finished, click **OK**.</span></span>

     <span data-ttu-id="c1c6e-149">소유자를 제거 하려면 소유자를 선택 하 고 제거 아이콘 **제거** 를 클릭 ![ ](../../media/ITPro-EAC-RemoveIcon.gif) 합니다.</span><span class="sxs-lookup"><span data-stu-id="c1c6e-149">To remove an owner, select the owner, and then click **Remove** ![Remove icon](../../media/ITPro-EAC-RemoveIcon.gif).</span></span>

   - <span data-ttu-id="c1c6e-150">**구성원**: 그룹 구성원을 추가 및 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="c1c6e-150">**Members**: Add and remove group members.</span></span>

     <span data-ttu-id="c1c6e-151">구성원을 추가 하려면 추가 아이콘 **추가를 클릭** ![ ](../../media/ITPro-EAC-AddIcon.png) 합니다.</span><span class="sxs-lookup"><span data-stu-id="c1c6e-151">To add members, click **Add** ![Add icon](../../media/ITPro-EAC-AddIcon.png).</span></span> <span data-ttu-id="c1c6e-152">대화 상자가 나타나면 받는 사람 또는 그룹을 찾아 선택한 다음 **추가 >** 를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="c1c6e-152">In the dialog that appears, find and select a recipient or group, and then click **add ->**.</span></span> <span data-ttu-id="c1c6e-153">필요한 만큼 이 단계를 반복합니다.</span><span class="sxs-lookup"><span data-stu-id="c1c6e-153">Repeat this step as many times as necessary.</span></span> <span data-ttu-id="c1c6e-154">작업을 마친 후 **확인**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="c1c6e-154">When you're finished, click **OK**.</span></span>

     <span data-ttu-id="c1c6e-155">구성원을 제거 하려면 구성원을 선택 하 고 제거 아이콘 **제거** 를 클릭 ![ ](../../media/ITPro-EAC-RemoveIcon.gif) 합니다.</span><span class="sxs-lookup"><span data-stu-id="c1c6e-155">To remove a member, select the member, and then click **Remove** ![Remove icon](../../media/ITPro-EAC-RemoveIcon.gif).</span></span>

4. <span data-ttu-id="c1c6e-156">작업이 끝나면 **저장** 을 클릭 하 여 메일 그룹을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="c1c6e-156">When you're finished, click **Save** to create the distribution group.</span></span>

### <a name="use-the-eac-to-modify-distribution-groups"></a><span data-ttu-id="c1c6e-157">EAC를 사용 하 여 메일 그룹 수정</span><span class="sxs-lookup"><span data-stu-id="c1c6e-157">Use the EAC to modify distribution groups</span></span>

1. <span data-ttu-id="c1c6e-158">EAC에서 **받는 사람** \> **그룹**으로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="c1c6e-158">In the EAC, go to **Recipients** \> **Groups**.</span></span>

2. <span data-ttu-id="c1c6e-159">그룹 목록에서 수정 하려는 메일 그룹을 선택 하 고 편집 아이콘 **편집** 을 클릭 ![ ](../../media/ITPro-EAC-AddIcon.png) 합니다.</span><span class="sxs-lookup"><span data-stu-id="c1c6e-159">In the list of groups, select the distribution group or mail-enabled security group that you want to modify, and then click **Edit** ![Edit icon](../../media/ITPro-EAC-AddIcon.png).</span></span>

3. <span data-ttu-id="c1c6e-160">메일 그룹 속성 페이지가 열리면 다음 탭 중 하나를 클릭 하 여 속성을 보거나 변경 합니다.</span><span class="sxs-lookup"><span data-stu-id="c1c6e-160">On the distribution group properties page that opens, click one of the following tabs to view or change properties.</span></span>

   <span data-ttu-id="c1c6e-161">작업을 마쳤으면 **저장**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="c1c6e-161">When you're finished, click **Save**.</span></span>

#### <a name="general"></a><span data-ttu-id="c1c6e-162">일반</span><span class="sxs-lookup"><span data-stu-id="c1c6e-162">General</span></span>

<span data-ttu-id="c1c6e-163">이 탭을 사용 하 여 그룹에 대 한 기본 정보를 보거나 변경 합니다.</span><span class="sxs-lookup"><span data-stu-id="c1c6e-163">Use this tab to view or change basic information about the group.</span></span>

- <span data-ttu-id="c1c6e-164">**표시 이름**:이 이름은 주소록,이 그룹으로 전자 메일을 보내는 경우 받는 사람 줄, **그룹 목록**에 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c1c6e-164">**Display name**: This name appears in the address book, on the To line when email is sent to this group, and in the **Groups list**.</span></span> <span data-ttu-id="c1c6e-165">표시 이름은 필수이며 다른 사람들이 알아 볼 수 있도록 친숙한 형태로 지정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c1c6e-165">The display name is required and should be user-friendly so people recognize what it is.</span></span> <span data-ttu-id="c1c6e-166">또한 도메인 내에서 고유해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c1c6e-166">It also has to be unique in your domain.</span></span>

  <span data-ttu-id="c1c6e-167">그룹 명명 규칙을 구현한 경우에는 표시 이름이 정책에 정의된 명명 규칙을 따라야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c1c6e-167">If you've implemented a group naming policy, the display name has to conform to the naming format defined by the policy.</span></span>

- <span data-ttu-id="c1c6e-168">**별칭**: 전자 메일 주소에서 @ 기호 왼쪽에 표시 되는 부분입니다.</span><span class="sxs-lookup"><span data-stu-id="c1c6e-168">**Alias**: This is the portion of the email address that appears to the left of the at (@) symbol.</span></span> <span data-ttu-id="c1c6e-169">별칭을 변경하면 그룹의 기본 SMTP 주소도 변경되며 새 별칭을 포함하게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c1c6e-169">If you change the alias, the primary SMTP address for the group will also be changed, and contain the new alias.</span></span> <span data-ttu-id="c1c6e-170">또한 이전 별칭을 사용한 전자 메일 주소는 그룹의 프록시 주소로 남아 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c1c6e-170">Also, the email address with the previous alias will be kept as a proxy address for the group.</span></span>

- <span data-ttu-id="c1c6e-171">**전자 메일 주소**: 전자 메일 주소는 @ 기호 왼쪽의 별칭 및 오른쪽에 있는 도메인으로 구성 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c1c6e-171">**Email address**: The email address consists of the alias on the left side of the at (@) symbol, and a domain on the right side.</span></span> <span data-ttu-id="c1c6e-172">**별칭 값** 은 기본적으로 별칭 값에 사용 되지만 변경할 수는 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c1c6e-172">By default, the value of **Alias** is used for the alias value, but you can change it.</span></span> <span data-ttu-id="c1c6e-173">도메인 값의 경우 조직에서 드롭다운 및 선택 및 허용 도메인을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="c1c6e-173">For the domain value, click the drop down and select and accepted domain in your organization.</span></span>

- <span data-ttu-id="c1c6e-174">**설명**:이 설명은 주소록과 EAC의 세부 정보 창에 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="c1c6e-174">**Description**: This description appears in the address book and in the Details pane in the EAC.</span></span>

#### <a name="ownership"></a><span data-ttu-id="c1c6e-175">소유권</span><span class="sxs-lookup"><span data-stu-id="c1c6e-175">Ownership</span></span>

<span data-ttu-id="c1c6e-176">이 탭을 사용 하 여 그룹 소유자를 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="c1c6e-176">Use this tab to assign group owners.</span></span> <span data-ttu-id="c1c6e-177">그룹 소유자는 그룹 구성원을 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c1c6e-177">A group owner can manage group membership.</span></span> <span data-ttu-id="c1c6e-178">기본적으로 그룹을 만든 사람이 소유자가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c1c6e-178">By default, the person who creates a group is the owner.</span></span> <span data-ttu-id="c1c6e-179">모든 그룹에는 한 명 이상의 소유자가 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c1c6e-179">All groups must have at least one owner.</span></span>

<span data-ttu-id="c1c6e-180">소유자를 추가 하려면 추가 아이콘 **추가를 클릭** ![ ](../../media/ITPro-EAC-AddIcon.png) 합니다.</span><span class="sxs-lookup"><span data-stu-id="c1c6e-180">To add owners, click **Add** ![Add icon](../../media/ITPro-EAC-AddIcon.png).</span></span> <span data-ttu-id="c1c6e-181">대화 상자가 나타나면 받는 사람을 찾아 선택 하 고 **추가 >** 를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="c1c6e-181">In the dialog that appears, find and select a recipient, and then click **add ->**.</span></span> <span data-ttu-id="c1c6e-182">필요한 만큼 이 단계를 반복합니다.</span><span class="sxs-lookup"><span data-stu-id="c1c6e-182">Repeat this step as many times as necessary.</span></span> <span data-ttu-id="c1c6e-183">작업을 마친 후 **확인**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="c1c6e-183">When you're finished, click **OK**.</span></span>

<span data-ttu-id="c1c6e-184">소유자를 제거 하려면 소유자를 선택 하 고 제거 아이콘 **제거** 를 클릭 ![ ](../../media/ITPro-EAC-RemoveIcon.gif) 합니다.</span><span class="sxs-lookup"><span data-stu-id="c1c6e-184">To remove an owner, select the owner, and then click **Remove** ![Remove icon](../../media/ITPro-EAC-RemoveIcon.gif).</span></span>

#### <a name="membership"></a><span data-ttu-id="c1c6e-185">구성원</span><span class="sxs-lookup"><span data-stu-id="c1c6e-185">Membership</span></span>

<span data-ttu-id="c1c6e-186">이 탭을 사용 하 여 그룹 구성원을 추가 하거나 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="c1c6e-186">Use this tab to add or remove group members.</span></span> <span data-ttu-id="c1c6e-187">그룹 소유자는 그룹의 구성원이 아니어도 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c1c6e-187">Group owners don't need to be members of the group.</span></span>

<span data-ttu-id="c1c6e-188">구성원을 추가 하려면 추가 아이콘 **추가를 클릭** ![ ](../../media/ITPro-EAC-AddIcon.png) 합니다.</span><span class="sxs-lookup"><span data-stu-id="c1c6e-188">To add members, click **Add** ![Add icon](../../media/ITPro-EAC-AddIcon.png).</span></span> <span data-ttu-id="c1c6e-189">대화 상자가 나타나면 받는 사람 또는 그룹을 찾아 선택한 다음 **추가 >** 를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="c1c6e-189">In the dialog that appears, find and select a recipient or group, and then click **add ->**.</span></span> <span data-ttu-id="c1c6e-190">필요한 만큼 이 단계를 반복합니다.</span><span class="sxs-lookup"><span data-stu-id="c1c6e-190">Repeat this step as many times as necessary.</span></span> <span data-ttu-id="c1c6e-191">작업을 마친 후 **확인**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="c1c6e-191">When you're finished, click **OK**.</span></span>

<span data-ttu-id="c1c6e-192">구성원을 제거 하려면 구성원을 선택 하 고 제거 아이콘 **제거** 를 클릭 ![ ](../../media/ITPro-EAC-RemoveIcon.gif) 합니다.</span><span class="sxs-lookup"><span data-stu-id="c1c6e-192">To remove a member, select the member, and then click **Remove** ![Remove icon](../../media/ITPro-EAC-RemoveIcon.gif).</span></span>

### <a name="use-the-eac-to-remove-groups"></a><span data-ttu-id="c1c6e-193">EAC를 사용 하 여 그룹 제거</span><span class="sxs-lookup"><span data-stu-id="c1c6e-193">Use the EAC to remove groups</span></span>

1. <span data-ttu-id="c1c6e-194">EAC에서 **받는 사람** \> **그룹**으로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="c1c6e-194">In the EAC, go to **Recipients** \> **Groups**.</span></span>

2. <span data-ttu-id="c1c6e-195">그룹 목록에서 제거할 메일 그룹을 선택 하 고 제거 아이콘 **제거** 를 클릭 ![ ](../../media/ITPro-EAC-RemoveIcon.gif) 합니다.</span><span class="sxs-lookup"><span data-stu-id="c1c6e-195">In the list of groups, select the distribution group that you want to remove, and then click **Remove** ![Remove icon](../../media/ITPro-EAC-RemoveIcon.gif).</span></span>

## <a name="use-powershell-to-manage-groups"></a><span data-ttu-id="c1c6e-196">PowerShell을 사용 하 여 그룹 관리</span><span class="sxs-lookup"><span data-stu-id="c1c6e-196">Use PowerShell to manage groups</span></span>

### <a name="use-standalone-eop-powershell-to-view-groups"></a><span data-ttu-id="c1c6e-197">독립 실행형 EOP PowerShell을 사용 하 여 그룹 보기</span><span class="sxs-lookup"><span data-stu-id="c1c6e-197">Use standalone EOP PowerShell to view groups</span></span>

<span data-ttu-id="c1c6e-198">독립 실행형 EOP PowerShell에서 모든 메일 그룹 및 메일 사용이 가능한 보안 그룹의 요약 목록을 반환 하려면 다음 명령을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="c1c6e-198">To return a summary list of all distribution groups and mail-enabled security groups in standalone EOP PowerShell, run the following command:</span></span>

```powershell
Get-Recipient -RecipientType MailUniversalDistributionGroup,MailUniversalSecurityGroup -ResultSize unlimited
```

<span data-ttu-id="c1c6e-199">그룹 구성원 목록을 반환 하려면 \< groupidentity를 \> 그룹의 이름, 별칭 또는 전자 메일 주소로 바꾸고 다음 명령을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="c1c6e-199">To return the list of group members, replace \<GroupIdentity\> with the name, alias, or email address of the group, and run the following command:</span></span>

```powershell
Get-DistributionGroupMember -Identity <GroupIdentity>
```

<span data-ttu-id="c1c6e-200">구문과 매개 변수에 대 한 자세한 내용은 Get-distributiongroupmember 및 get [-](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/get-distributiongroupmember) [Recipient](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/get-recipient) 를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="c1c6e-200">For detailed syntax and parameter information, see [Get-Recipient](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/get-recipient) and [Get-DistributionGroupMember](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/get-distributiongroupmember).</span></span>

### <a name="use-standalone-eop-powershell-to-create-groups"></a><span data-ttu-id="c1c6e-201">독립 실행형 EOP PowerShell을 사용 하 여 그룹 만들기</span><span class="sxs-lookup"><span data-stu-id="c1c6e-201">Use standalone EOP PowerShell to create groups</span></span>

<span data-ttu-id="c1c6e-202">독립 실행형 EOP PowerShell에서 메일 그룹 또는 메일 사용이 가능한 보안 그룹을 만들려면 다음 구문을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="c1c6e-202">To create distribution groups or mail-enabled security groups in standalone EOP PowerShell, use the following syntax:</span></span>

```PowerShell
New-EOPDistributionGroup -Name "<Unique Name>" -ManagedBy @("UserOrGroup1","UserOrGroup2",..."UserOrGroupN">) [-Alias <text>] [-DisplayName "<Descriptive Name>"] [-Members @("UserOrGroup1","UserOrGroup2",..."UserOrGroupN">)] [-Notes "<Optional Text>"] [-PrimarySmtpAddress <SmtpAddress>] [-Type <Distribution | Security>]
```

<span data-ttu-id="c1c6e-203">**참고**:</span><span class="sxs-lookup"><span data-stu-id="c1c6e-203">**Notes**:</span></span>

- <span data-ttu-id="c1c6e-204">_Name_ 매개 변수는 필수 이며, 최대 길이는 64 자 이며 고유 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c1c6e-204">The _Name_ parameter is required, has a maximum length of 64 characters, and must be unique.</span></span> <span data-ttu-id="c1c6e-205">_DisplayName_ 매개 변수를 사용하지 않는 경우에는 _Name_ 매개 변수의 값이 표시 이름에 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="c1c6e-205">If you don't use the _DisplayName_ parameter, the value of the _Name_ parameter is used for the display name.</span></span>

- <span data-ttu-id="c1c6e-206">_Alias_ 매개 변수를 사용 하지 않는 경우에는 _Name_ 매개 변수가 별칭 값에 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c1c6e-206">If you don't use the _Alias_ parameter, the _Name_ parameter is used for the alias value.</span></span> <span data-ttu-id="c1c6e-207">공백은 제거 되 고 지원 되지 않는 문자는 물음표 (?)로 변환 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c1c6e-207">Spaces are removed and unsupported characters are converted to question marks (?).</span></span>

- <span data-ttu-id="c1c6e-208">_PrimarySmtpAddress_ 매개 변수를 사용 하지 않으면 별칭 값은 _PrimarySmtpAddress_ 매개 변수에 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c1c6e-208">If you don't use the _PrimarySmtpAddress_ parameter, the alias value is used in the _PrimarySmtpAddress_ parameter.</span></span>

- <span data-ttu-id="c1c6e-209">_Type_ 매개 변수를 사용 하지 않으면 기본값은 분포입니다.</span><span class="sxs-lookup"><span data-stu-id="c1c6e-209">If you don't use the _Type_ parameter, the default value is Distribution.</span></span>

<span data-ttu-id="c1c6e-210">이 예에서는 지정 된 속성을 사용 하 여 IT 관리자 라는 메일 그룹을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="c1c6e-210">This example creates a distribution group named IT Administrators with the specified properties.</span></span>

```PowerShell
New-EOPDistributionGroup -Name "IT Administrators" -Alias itadmin -Members @("michelle@contoso.com","laura@contoso.com","julia@contoso.com") -ManagedBy "chris@contoso.com"
```

<span data-ttu-id="c1c6e-211">구문과 매개 변수에 대 한 자세한 내용은 [set-eopdistributiongroup](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/New-EOPDistributionGroup)를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="c1c6e-211">For detailed syntax and parameter information, see [New-EOPDistributionGroup](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/New-EOPDistributionGroup).</span></span>

### <a name="use-standalone-eop-powershell-to-modify-groups"></a><span data-ttu-id="c1c6e-212">독립 실행형 EOP PowerShell을 사용 하 여 그룹 수정</span><span class="sxs-lookup"><span data-stu-id="c1c6e-212">Use standalone EOP PowerShell to modify groups</span></span>

<span data-ttu-id="c1c6e-213">독립 실행형 EOP PowerShell에서 그룹을 수정 하려면 다음 구문을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="c1c6e-213">To modify groups in standalone EOP PowerShell, use the following syntax:</span></span>

```powershell
Set-EOPDistributionGroup -Identity <GroupIdentity> [-Alias <Text>] [-DisplayName <Text>] [-ManagedBy @("User1","User2",..."UserN")] [-PrimarySmtpAddress <SmtpAddress>]

```powershell
Update-EOPDistributionGroupMember -Identity <GroupIdentity> -Members @("User1","User2",..."UserN")
```

<span data-ttu-id="c1c6e-214">이 예에서는 시애틀 Employees 그룹에 대 한 기본 SMTP 주소 (회신 주소 라고도 함)가 sea.employees@contoso.com로 변경 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c1c6e-214">This example uses changes the primary SMTP address (also called the reply address) for the Seattle Employees group to sea.employees@contoso.com.</span></span>

```PowerShell
Set-EOPDistributionGroup "Seattle Employees" -PrimarysmptAddress "sea.employees@contoso.com"
```

<span data-ttu-id="c1c6e-215">이 예에서는 보안 팀 그룹의 현재 구성원을 Kitty Petersen 및 Tyson Fawcett로 바꿉니다로 대체 합니다.</span><span class="sxs-lookup"><span data-stu-id="c1c6e-215">This example replaces the current members of the Security Team group with Kitty Petersen and Tyson Fawcett.</span></span>

```powershell
Update-EOPDistributionGroupMember -Identity "Security Team" -Members @("Kitty Petersen","Tyson Fawcett")
```

<span data-ttu-id="c1c6e-216">이 예에서는 Tyson Fawcett로 바꿉니다 라는 새 사용자를 Security Team 이라는 그룹에 추가 하 고 해당 그룹의 현재 구성원을 유지 합니다.</span><span class="sxs-lookup"><span data-stu-id="c1c6e-216">This example adds a new user named Tyson Fawcett to the group named Security Team while preserving the current members of the group.</span></span>

```powershell
$CurrentMemberObjects = Get-DistributionGroupMember "Security Team"
$CurrentMemberNames = $CurrentMemberObjects | % {$_.name}
$CurrentMemberNames += "Tyson Fawcett"
Update-EOPDistributionGroupMember -Identity "Security Team" -Members $CurrentMemberNames
```

<span data-ttu-id="c1c6e-217">구문 및 매개 변수에 대 한 자세한 내용은 [set-eopdistributiongroup](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/set-eopdistributiongroup) 및 [Update-에서는 update-eopdistributiongroupmember](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/update-eopdistributiongroupmember)를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="c1c6e-217">For detailed syntax and parameter information, see [Set-EOPDistributionGroup](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/set-eopdistributiongroup) and [Update-EOPDistributionGroupMember](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/update-eopdistributiongroupmember).</span></span>

### <a name="remove-a-group-using-remote-windows-powershell"></a><span data-ttu-id="c1c6e-218">원격 Windows PowerShell을 사용 하 여 그룹 제거</span><span class="sxs-lookup"><span data-stu-id="c1c6e-218">Remove a group using remote Windows PowerShell</span></span>

<span data-ttu-id="c1c6e-219">이 예에서는 IT Administrators 라는 메일 그룹을 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="c1c6e-219">This example uses removes the distribution group named IT Administrators.</span></span>

```PowerShell
Remove-EOPDistributionGroup -Identity "IT Administrators"
```

<span data-ttu-id="c1c6e-220">구문과 매개 변수에 대 한 자세한 내용은 [set-eopdistributiongroup](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/remove-eopdistributiongroup)를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="c1c6e-220">For detailed syntax and parameter information, see [Remove-EOPDistributionGroup](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/remove-eopdistributiongroup).</span></span>

## <a name="how-do-you-know-these-procedures-worked"></a><span data-ttu-id="c1c6e-221">이 절차가 제대로 수행되었는지 어떻게 확인하나요?</span><span class="sxs-lookup"><span data-stu-id="c1c6e-221">How do you know these procedures worked?</span></span>

<span data-ttu-id="c1c6e-222">메일 그룹을 성공적으로 만들거나, 수정 하거나, 제거 했는지 확인 하려면 다음 단계 중 하나를 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="c1c6e-222">To verify that you've successfully created, modified, or removed a distribution group or a mail-enabled security group, do any of the following steps:</span></span>

- <span data-ttu-id="c1c6e-223">EAC에서 **받는 사람** \> **그룹**으로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="c1c6e-223">In the EAC, go to **Recipients** \> **Groups**.</span></span> <span data-ttu-id="c1c6e-224">그룹이 나열 되는지, 목록에 표시 되지 않았는지, **그룹 유형** 값을 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="c1c6e-224">Verify that the group is listed (or not listed), and verify the **Group Type** value.</span></span> <span data-ttu-id="c1c6e-225">그룹을 선택 하 고 세부 정보 창에서 정보를 보거나 편집 아이콘 **편집** ![ 을 클릭 ](../../media/ITPro-EAC-AddIcon.png) 하 여 설정을 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="c1c6e-225">Select the group and view the information in the Details pane, or click **Edit** ![Edit icon](../../media/ITPro-EAC-AddIcon.png) to view the settings.</span></span>

- <span data-ttu-id="c1c6e-226">독립 실행형 EOP PowerShell에서 다음 명령을 실행 하 여 그룹이 나열 되는지 확인 합니다 (또는 나열 되지 않음).</span><span class="sxs-lookup"><span data-stu-id="c1c6e-226">In standalone EOP PowerShell, run the following command to verify the group is listed (or isn't listed):</span></span>

  ```PowerShell
  Get-Recipient -RecipientType MailUniversalDistributionGroup,MailUniversalSecurityGroup -ResultSize unlimited
  ```

- <span data-ttu-id="c1c6e-227">\<Groupidentity를 \> 그룹의 이름, 별칭 또는 전자 메일 주소로 바꾸고 다음 명령을 실행 하 여 설정을 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="c1c6e-227">Replace \<GroupIdentity\> with the name, alias, or email address of the group and run the following command to verify the settings:</span></span>

  ```PowerShell
  Get-Recipient -Identity <GroupIdentity> | Format-List
  ```

- <span data-ttu-id="c1c6e-228">그룹 구성원을 보려면 \< groupidentity를 \> 그룹의 이름, 별칭 또는 전자 메일 주소로 바꾸고 다음 명령을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="c1c6e-228">To view the group members, replace \<GroupIdentity\> with the name, alias, or email address of the group and run the following command:</span></span>

  ```PowerShell
  Get-DistributionGroupMember -Identity "<GroupIdentity>"
  ```
