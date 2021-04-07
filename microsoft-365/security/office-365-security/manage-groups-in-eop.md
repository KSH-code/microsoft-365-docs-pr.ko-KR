---
title: EOP에서 그룹 관리
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: how-to
localization_priority: Normal
ms.assetid: 212e68ac-6330-47e9-a169-6cf5e2f21e13
ms.custom:
- seo-marvel-apr2020
description: 독립 실행형 EOP(Exchange Online Protection) 조직의 관리자는 EAC(Exchange 관리 센터) 및 독립 실행형 EOP(Exchange Online Protection) PowerShell에서 메일 그룹 및 메일 사용이 가능한 보안 그룹을 만들고 수정하고 제거하는 방법을 배울 수 있습니다.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: b9d83f2fb59ee8f8d2d3035045ed438d5ba45851
ms.sourcegitcommit: 7ee50882cb4ed37794a3cd82dac9b2f9e0a1f14a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/06/2021
ms.locfileid: "51599572"
---
# <a name="manage-groups-in-eop"></a><span data-ttu-id="57817-103">EOP에서 그룹 관리</span><span class="sxs-lookup"><span data-stu-id="57817-103">Manage groups in EOP</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="57817-104">**적용 대상**</span><span class="sxs-lookup"><span data-stu-id="57817-104">**Applies to**</span></span>
-  [<span data-ttu-id="57817-105">Exchange Online Protection 독립 실행형</span><span class="sxs-lookup"><span data-stu-id="57817-105">Exchange Online Protection standalone</span></span>](exchange-online-protection-overview.md)

<span data-ttu-id="57817-106">Exchange Online 사서함이 없는 독립 실행형 EOP(Exchange Online Protection) 조직에서는 다음과 같은 유형의 그룹을 만들고 수정하고 제거할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="57817-106">In standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, you can create, modify, and remove the following types of groups:</span></span>

- <span data-ttu-id="57817-107">**메일 그룹:** 메일 사용자 또는 기타 메일 그룹의 모음입니다.</span><span class="sxs-lookup"><span data-stu-id="57817-107">**Distribution groups**: A collection of mail users or other distribution groups.</span></span> <span data-ttu-id="57817-108">예를 들어 공통 관심 영역으로 전자 메일을 보내거나 받거나 보내야 하는 팀 또는 기타 애드 호크 그룹이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="57817-108">For example, teams or other ad hoc groups who need to receive or send email in a common area of interest.</span></span> <span data-ttu-id="57817-109">메일 그룹은 전자 메일 메시지를 배포하는 데만 사용할 수 있으며 보안 주체가 아니며 할당된 사용 권한을 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="57817-109">Distribution groups are exclusively for distributing email messages, and are not security principals (they can't have permissions assigned to them).</span></span>

- <span data-ttu-id="57817-110">**메일 사용이 가능한 보안 그룹:** 관리자 역할에 대한 액세스 권한이 필요한 메일 사용자 및 기타 보안 그룹 모음입니다.</span><span class="sxs-lookup"><span data-stu-id="57817-110">**Mail-enabled security groups**: A collection of mail users and other security groups who need access permissions for admin roles.</span></span> <span data-ttu-id="57817-111">예를 들어 특정 사용자 그룹에 스팸 방지 및 맬웨어 방지 설정을 구성할 수 있도록 관리자 권한을 부여할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="57817-111">For example, you might want to give specific group of users admin permissions so they can configure anti-spam and anti-malware settings.</span></span>

    > [!NOTE]
    >
    > - <span data-ttu-id="57817-112">기본적으로 새 메일 사용이 가능한 보안 그룹은 외부(확인되지 않은) 보낸 사람이 보낸 메시지를 거부합니다.</span><span class="sxs-lookup"><span data-stu-id="57817-112">By default, new mail-enabled security groups reject messages from external (unauthenticated) senders.</span></span>
    >
    > - <span data-ttu-id="57817-113">메일 사용이 가능한 보안 그룹에 메일 그룹을 추가하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="57817-113">Don't add distribution groups to mail-enabled security groups.</span></span>

<span data-ttu-id="57817-114">EAC(Exchange 관리 센터) 및 독립 실행형 EOP PowerShell에서 그룹을 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="57817-114">You can manage groups in the Exchange admin center (EAC) and in standalone EOP PowerShell.</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="57817-115">시작하기 전에 알아야 할 사항은 무엇인가요?</span><span class="sxs-lookup"><span data-stu-id="57817-115">What do you need to know before you begin?</span></span>

- <span data-ttu-id="57817-116">Exchange 관리 센터를 열하려면 독립 실행형 [EOP의 Exchange 관리 센터를 참조하세요.](exchange-admin-center-in-exchange-online-protection-eop.md)</span><span class="sxs-lookup"><span data-stu-id="57817-116">To open the Exchange admin center, see [Exchange admin center in standalone EOP](exchange-admin-center-in-exchange-online-protection-eop.md).</span></span>

- <span data-ttu-id="57817-117">독립 실행형 EOP PowerShell에 연결하려면 [Exchange Online Protection PowerShell에 연결](/powershell/exchange/connect-to-exchange-online-protection-powershell)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="57817-117">To connect to standalone EOP PowerShell, see [Connect to Exchange Online Protection PowerShell](/powershell/exchange/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="57817-118">독립 실행형 EOP PowerShell에서 그룹을 관리하는 경우 스로틀이 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="57817-118">When you manage groups in standalone EOP PowerShell, you might encounter throttling.</span></span> <span data-ttu-id="57817-119">이 문서의 PowerShell 프로시저에서는 명령 결과가 표시되기 몇 분 전에 전파가 지연되는 일괄 처리 방법을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="57817-119">The PowerShell procedures in this article use a batch processing method that results in a propagation delay of a few minutes before the results of the commands are visible.</span></span>

- <span data-ttu-id="57817-120">이 문서의 절차를 수행하려면 먼저 Exchange Online Protection에서 사용 권한을 할당해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="57817-120">You need to be assigned permissions in Exchange Online Protection before you can do the procedures in this article.</span></span> <span data-ttu-id="57817-121">특히 조직 관리  및 받는 사람 관리 역할  그룹에 기본적으로 할당되는 메일 그룹 **역할이** 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="57817-121">Specifically, you need the **Distribution Groups** role, which is assigned to the **Organization Management** and **Recipient Management** role groups by default.</span></span> <span data-ttu-id="57817-122">자세한 내용은 독립 실행형 [EOP의](feature-permissions-in-eop.md) 사용 권한 및 EAC를 사용하여 역할 그룹의 구성원 목록 [수정을 참조하세요.](manage-admin-role-group-permissions-in-eop.md#use-the-eac-modify-the-list-of-members-in-role-groups)</span><span class="sxs-lookup"><span data-stu-id="57817-122">For more information, see [Permissions in standalone EOP](feature-permissions-in-eop.md) and [Use the EAC modify the list of members in role groups](manage-admin-role-group-permissions-in-eop.md#use-the-eac-modify-the-list-of-members-in-role-groups).</span></span>

- <span data-ttu-id="57817-123">이 문서의 절차에 적용할 수 있는 바로 가기 키에 대한 자세한 내용은 Exchange Online의 Exchange 관리 센터에 대한 바로 가기 키를 [참조하세요.](/Exchange/accessibility/keyboard-shortcuts-in-admin-center)</span><span class="sxs-lookup"><span data-stu-id="57817-123">For information about keyboard shortcuts that may apply to the procedures in this article, see [Keyboard shortcuts for the Exchange admin center in Exchange Online](/Exchange/accessibility/keyboard-shortcuts-in-admin-center).</span></span>

> [!TIP]
> <span data-ttu-id="57817-124">문제가 있나요?</span><span class="sxs-lookup"><span data-stu-id="57817-124">Having problems?</span></span> <span data-ttu-id="57817-125">[Exchange Online Protection](https://social.technet.microsoft.com/Forums/forefront/home?forum=FOPE) 포럼에서 도움을 요청하세요.</span><span class="sxs-lookup"><span data-stu-id="57817-125">Ask for help in the [Exchange Online Protection](https://social.technet.microsoft.com/Forums/forefront/home?forum=FOPE) forum.</span></span>

## <a name="use-the-exchange-admin-center-to-manage-distribution-groups"></a><span data-ttu-id="57817-126">Exchange 관리 센터를 사용하여 메일 그룹 관리</span><span class="sxs-lookup"><span data-stu-id="57817-126">Use the Exchange admin center to manage distribution groups</span></span>

### <a name="use-the-eac-to-create-groups"></a><span data-ttu-id="57817-127">EAC를 사용하여 그룹 만들기</span><span class="sxs-lookup"><span data-stu-id="57817-127">Use the EAC to create groups</span></span>

1. <span data-ttu-id="57817-128">EAC에서 받는 사람 **그룹 으로** \> **이동 합니다.**</span><span class="sxs-lookup"><span data-stu-id="57817-128">In the EAC, go to **Recipients** \> **Groups**.</span></span>

2. <span data-ttu-id="57817-129">새로 **추가 아이콘** ![ ](../../media/ITPro-EAC-AddIcon.png) 을 클릭하고 다음 옵션 중 하나를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="57817-129">Click **New** ![New icon](../../media/ITPro-EAC-AddIcon.png), and then select one of the following options:</span></span>

   - <span data-ttu-id="57817-130">**메일 그룹**</span><span class="sxs-lookup"><span data-stu-id="57817-130">**Distribution group**</span></span>

   - <span data-ttu-id="57817-131">**메일 사용 가능 보안 그룹**</span><span class="sxs-lookup"><span data-stu-id="57817-131">**Mail-enabled security group**</span></span>

3. <span data-ttu-id="57817-132">새 그룹 페이지가 열리면 다음 설정을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="57817-132">In the new group page that opens, configure the following settings.</span></span> <span data-ttu-id="57817-133">으로 표시된 <sup>\*</sup> 설정은 필수입니다.</span><span class="sxs-lookup"><span data-stu-id="57817-133">Settings marked with an <sup>\*</sup> are required.</span></span>

   - <span data-ttu-id="57817-134"><sup>\*</sup>**표시 이름:** 이 이름은 조직의 주소 책, 이 그룹에 전자 메일을 보낼 때의 To:  줄 및 EAC의 그룹 목록에 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="57817-134"><sup>\*</sup>**Display name**: This name appears in your organization's address book, on the To: line when email is sent to this group, and in the **Groups** list in the EAC.</span></span> <span data-ttu-id="57817-135">표시 이름은 필수일 수 있으며 고유해야 하며, 사용자가 인식할 수 있도록 사용자에게 친숙해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="57817-135">The display name is required, must be unique, and should be user-friendly so people recognize what it is.</span></span>

   - <span data-ttu-id="57817-136"><sup>\*</sup>**별칭:** 이 상자에 그룹의 별칭 이름을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="57817-136"><sup>\*</sup>**Alias**: Use this box to type the name of the alias for the group.</span></span> <span data-ttu-id="57817-137">별칭은 64자까지 사용할 수 있으며 고유해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="57817-137">The alias can't exceed 64 characters and must be unique.</span></span> <span data-ttu-id="57817-138">사용자가 전자 메일 메시지의 To 줄에 별칭을 입력하면 그룹의 표시 이름으로 확인됩니다.</span><span class="sxs-lookup"><span data-stu-id="57817-138">When a user types the alias in the To line of an email message, it resolves to the group's display name.</span></span>

   - <span data-ttu-id="57817-139"><sup>\*</sup>**전자 메일 주소:** 전자 메일 주소는 @ 기호 왼쪽의 별칭과 오른쪽에 있는 도메인으로 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="57817-139"><sup>\*</sup>**Email address**: The email address consists of the alias on the left side of the at (@) symbol, and a domain on the right side.</span></span> <span data-ttu-id="57817-140">기본적으로 별칭 값은  별칭 값에 사용되지만 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="57817-140">By default, the value of **Alias** is used for the alias value, but you can change it.</span></span> <span data-ttu-id="57817-141">도메인 값에 대해 드롭다운을 클릭하고 조직에서 허용 도메인을 선택하고 허용합니다.</span><span class="sxs-lookup"><span data-stu-id="57817-141">For the domain value, click the drop down and select and accepted domain in your organization.</span></span>

   - <span data-ttu-id="57817-142">**설명:** 이 설명은 주소부와 EAC의 세부 정보 창에 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="57817-142">**Description**: This description appears in the address book and in the Details pane in the EAC.</span></span>

   - <span data-ttu-id="57817-143"><sup>\*</sup>**소유자:** 그룹 소유자가 그룹 구성원을 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="57817-143"><sup>\*</sup>**Owners**: A group owner can manage group membership.</span></span> <span data-ttu-id="57817-144">기본적으로 그룹을 만든 사람이 소유자가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="57817-144">By default, the person who creates a group is the owner.</span></span> <span data-ttu-id="57817-145">모든 그룹에는 한 명 이상의 소유자가 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="57817-145">All groups must have at least one owner.</span></span>

     <span data-ttu-id="57817-146">소유자를 추가하려면 추가 **아이콘 추가를** ![ ](../../media/ITPro-EAC-AddIcon.png) 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="57817-146">To add owners, click **Add** ![Add icon](../../media/ITPro-EAC-AddIcon.png).</span></span> <span data-ttu-id="57817-147">나타나는 대화 상자에서 받는 사람 또는 그룹을 찾아 선택한 다음 **->.**</span><span class="sxs-lookup"><span data-stu-id="57817-147">In the dialog that appears, find and select a recipient or group, and then click **add ->**.</span></span> <span data-ttu-id="57817-148">필요한 만큼 이 단계를 반복합니다.</span><span class="sxs-lookup"><span data-stu-id="57817-148">Repeat this step as many times as necessary.</span></span> <span data-ttu-id="57817-149">작업을 마친 후 **확인** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="57817-149">When you're finished, click **OK**.</span></span>

     <span data-ttu-id="57817-150">소유자를 제거하려면 소유자를 선택한 다음 제거 아이콘 **를** ![ ](../../media/ITPro-EAC-RemoveIcon.gif) 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="57817-150">To remove an owner, select the owner, and then click **Remove** ![Remove icon](../../media/ITPro-EAC-RemoveIcon.gif).</span></span>

   - <span data-ttu-id="57817-151">**구성원:** 그룹 구성원을 추가 및 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="57817-151">**Members**: Add and remove group members.</span></span>

     <span data-ttu-id="57817-152">구성원을 추가하려면 추가 **아이콘 를** ![ ](../../media/ITPro-EAC-AddIcon.png) 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="57817-152">To add members, click **Add** ![Add icon](../../media/ITPro-EAC-AddIcon.png).</span></span> <span data-ttu-id="57817-153">나타나는 대화 상자에서 받는 사람 또는 그룹을 찾아 선택한 다음 **->.**</span><span class="sxs-lookup"><span data-stu-id="57817-153">In the dialog that appears, find and select a recipient or group, and then click **add ->**.</span></span> <span data-ttu-id="57817-154">필요한 만큼 이 단계를 반복합니다.</span><span class="sxs-lookup"><span data-stu-id="57817-154">Repeat this step as many times as necessary.</span></span> <span data-ttu-id="57817-155">작업을 마친 후 **확인** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="57817-155">When you're finished, click **OK**.</span></span>

     <span data-ttu-id="57817-156">구성원을 제거하려면 구성원을 선택한 다음 제거 아이콘 **를** ![ ](../../media/ITPro-EAC-RemoveIcon.gif) 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="57817-156">To remove a member, select the member, and then click **Remove** ![Remove icon](../../media/ITPro-EAC-RemoveIcon.gif).</span></span>

4. <span data-ttu-id="57817-157">완료되면 저장을 클릭하여 **메일** 그룹을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="57817-157">When you're finished, click **Save** to create the distribution group.</span></span>

### <a name="use-the-eac-to-modify-distribution-groups"></a><span data-ttu-id="57817-158">EAC를 사용하여 메일 그룹 수정</span><span class="sxs-lookup"><span data-stu-id="57817-158">Use the EAC to modify distribution groups</span></span>

1. <span data-ttu-id="57817-159">EAC에서 받는 사람 **그룹 으로** \> **이동 합니다.**</span><span class="sxs-lookup"><span data-stu-id="57817-159">In the EAC, go to **Recipients** \> **Groups**.</span></span>

2. <span data-ttu-id="57817-160">그룹 목록에서 수정할 메일 그룹 또는 메일 사용이 가능한 보안 그룹을 선택하고  편집 편집 아이콘 ![ 을 ](../../media/ITPro-EAC-AddIcon.png) 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="57817-160">In the list of groups, select the distribution group or mail-enabled security group that you want to modify, and then click **Edit** ![Edit icon](../../media/ITPro-EAC-AddIcon.png).</span></span>

3. <span data-ttu-id="57817-161">메일 그룹 속성 페이지가 열리면 다음 탭 중 하나를 클릭하여 속성을 보거나 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="57817-161">On the distribution group properties page that opens, click one of the following tabs to view or change properties.</span></span>

   <span data-ttu-id="57817-162">작업을 마쳤으면 **저장** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="57817-162">When you're finished, click **Save**.</span></span>

#### <a name="general"></a><span data-ttu-id="57817-163">일반 사항</span><span class="sxs-lookup"><span data-stu-id="57817-163">General</span></span>

<span data-ttu-id="57817-164">이 탭을 사용하여 그룹에 대한 기본 정보를 보거나 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="57817-164">Use this tab to view or change basic information about the group.</span></span>

- <span data-ttu-id="57817-165">**표시 이름:** 이 이름은 주소 목록, 이 그룹에 전자 메일을 보낼 때의 To 줄 및 그룹 목록에 **표시됩니다.**</span><span class="sxs-lookup"><span data-stu-id="57817-165">**Display name**: This name appears in the address book, on the To line when email is sent to this group, and in the **Groups list**.</span></span> <span data-ttu-id="57817-166">표시 이름은 필수이며 다른 사람들이 알아 볼 수 있도록 친숙한 형태로 지정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="57817-166">The display name is required and should be user-friendly so people recognize what it is.</span></span> <span data-ttu-id="57817-167">또한 도메인 내에서 고유해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="57817-167">It also has to be unique in your domain.</span></span>

  <span data-ttu-id="57817-168">그룹 명명 규칙을 구현한 경우에는 표시 이름이 정책에 정의된 명명 규칙을 따라야 합니다.</span><span class="sxs-lookup"><span data-stu-id="57817-168">If you've implemented a group naming policy, the display name has to conform to the naming format defined by the policy.</span></span>

- <span data-ttu-id="57817-169">**별칭:** 전자 메일 주소에서 @ 기호 왼쪽에 나타나는 부분입니다.</span><span class="sxs-lookup"><span data-stu-id="57817-169">**Alias**: This is the portion of the email address that appears to the left of the at (@) symbol.</span></span> <span data-ttu-id="57817-170">별칭을 변경하면 그룹의 기본 SMTP 주소도 변경되며 새 별칭을 포함하게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="57817-170">If you change the alias, the primary SMTP address for the group will also be changed, and contain the new alias.</span></span> <span data-ttu-id="57817-171">또한 이전 별칭을 사용한 전자 메일 주소는 그룹의 프록시 주소로 남아 있습니다.</span><span class="sxs-lookup"><span data-stu-id="57817-171">Also, the email address with the previous alias will be kept as a proxy address for the group.</span></span>

- <span data-ttu-id="57817-172">**전자 메일 주소:** 전자 메일 주소는 @ 기호 왼쪽의 별칭과 오른쪽에 있는 도메인으로 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="57817-172">**Email address**: The email address consists of the alias on the left side of the at (@) symbol, and a domain on the right side.</span></span> <span data-ttu-id="57817-173">기본적으로 별칭 값은  별칭 값에 사용되지만 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="57817-173">By default, the value of **Alias** is used for the alias value, but you can change it.</span></span> <span data-ttu-id="57817-174">도메인 값에 대해 드롭다운을 클릭하고 조직에서 허용 도메인을 선택하고 허용합니다.</span><span class="sxs-lookup"><span data-stu-id="57817-174">For the domain value, click the drop down and select and accepted domain in your organization.</span></span>

- <span data-ttu-id="57817-175">**설명:** 이 설명은 주소부와 EAC의 세부 정보 창에 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="57817-175">**Description**: This description appears in the address book and in the Details pane in the EAC.</span></span>

#### <a name="ownership"></a><span data-ttu-id="57817-176">소유권</span><span class="sxs-lookup"><span data-stu-id="57817-176">Ownership</span></span>

<span data-ttu-id="57817-177">이 탭을 사용하여 그룹 소유자를 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="57817-177">Use this tab to assign group owners.</span></span> <span data-ttu-id="57817-178">그룹 소유자는 그룹 구성원을 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="57817-178">A group owner can manage group membership.</span></span> <span data-ttu-id="57817-179">기본적으로 그룹을 만든 사람이 소유자가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="57817-179">By default, the person who creates a group is the owner.</span></span> <span data-ttu-id="57817-180">모든 그룹에는 한 명 이상의 소유자가 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="57817-180">All groups must have at least one owner.</span></span>

<span data-ttu-id="57817-181">소유자를 추가하려면 추가 **아이콘 추가를** ![ ](../../media/ITPro-EAC-AddIcon.png) 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="57817-181">To add owners, click **Add** ![Add icon](../../media/ITPro-EAC-AddIcon.png).</span></span> <span data-ttu-id="57817-182">나타나는 대화 상자에서 받는 사람을 찾아 선택한 다음 **->.**</span><span class="sxs-lookup"><span data-stu-id="57817-182">In the dialog that appears, find and select a recipient, and then click **add ->**.</span></span> <span data-ttu-id="57817-183">필요한 만큼 이 단계를 반복합니다.</span><span class="sxs-lookup"><span data-stu-id="57817-183">Repeat this step as many times as necessary.</span></span> <span data-ttu-id="57817-184">작업을 마친 후 **확인** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="57817-184">When you're finished, click **OK**.</span></span>

<span data-ttu-id="57817-185">소유자를 제거하려면 소유자를 선택한 다음 제거 아이콘 **를** ![ ](../../media/ITPro-EAC-RemoveIcon.gif) 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="57817-185">To remove an owner, select the owner, and then click **Remove** ![Remove icon](../../media/ITPro-EAC-RemoveIcon.gif).</span></span>

#### <a name="membership"></a><span data-ttu-id="57817-186">구성원</span><span class="sxs-lookup"><span data-stu-id="57817-186">Membership</span></span>

<span data-ttu-id="57817-187">이 탭을 사용하여 그룹 구성원을 추가하거나 제거할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="57817-187">Use this tab to add or remove group members.</span></span> <span data-ttu-id="57817-188">그룹 소유자는 그룹의 구성원일 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="57817-188">Group owners don't need to be members of the group.</span></span>

<span data-ttu-id="57817-189">구성원을 추가하려면 추가 **아이콘 를** ![ ](../../media/ITPro-EAC-AddIcon.png) 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="57817-189">To add members, click **Add** ![Add icon](../../media/ITPro-EAC-AddIcon.png).</span></span> <span data-ttu-id="57817-190">나타나는 대화 상자에서 받는 사람 또는 그룹을 찾아 선택한 다음 **->.**</span><span class="sxs-lookup"><span data-stu-id="57817-190">In the dialog that appears, find and select a recipient or group, and then click **add ->**.</span></span> <span data-ttu-id="57817-191">필요한 만큼 이 단계를 반복합니다.</span><span class="sxs-lookup"><span data-stu-id="57817-191">Repeat this step as many times as necessary.</span></span> <span data-ttu-id="57817-192">작업을 마친 후 **확인** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="57817-192">When you're finished, click **OK**.</span></span>

<span data-ttu-id="57817-193">구성원을 제거하려면 구성원을 선택한 다음 제거 아이콘 **를** ![ ](../../media/ITPro-EAC-RemoveIcon.gif) 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="57817-193">To remove a member, select the member, and then click **Remove** ![Remove icon](../../media/ITPro-EAC-RemoveIcon.gif).</span></span>

### <a name="use-the-eac-to-remove-groups"></a><span data-ttu-id="57817-194">EAC를 사용하여 그룹 제거</span><span class="sxs-lookup"><span data-stu-id="57817-194">Use the EAC to remove groups</span></span>

1. <span data-ttu-id="57817-195">EAC에서 받는 사람 **그룹 으로** \> **이동 합니다.**</span><span class="sxs-lookup"><span data-stu-id="57817-195">In the EAC, go to **Recipients** \> **Groups**.</span></span>

2. <span data-ttu-id="57817-196">그룹 목록에서 제거할 메일 그룹을 선택하고 제거 아이콘 **를** ![ ](../../media/ITPro-EAC-RemoveIcon.gif) 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="57817-196">In the list of groups, select the distribution group that you want to remove, and then click **Remove** ![Remove icon](../../media/ITPro-EAC-RemoveIcon.gif).</span></span>

## <a name="use-powershell-to-manage-groups"></a><span data-ttu-id="57817-197">PowerShell을 사용하여 그룹 관리</span><span class="sxs-lookup"><span data-stu-id="57817-197">Use PowerShell to manage groups</span></span>

### <a name="use-standalone-eop-powershell-to-view-groups"></a><span data-ttu-id="57817-198">독립 실행형 EOP PowerShell을 사용하여 그룹 보기</span><span class="sxs-lookup"><span data-stu-id="57817-198">Use standalone EOP PowerShell to view groups</span></span>

<span data-ttu-id="57817-199">독립 실행형 EOP PowerShell에서 모든 메일 그룹 및 메일 사용이 가능한 보안 그룹의 요약 목록을 반환하기 위해 다음 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="57817-199">To return a summary list of all distribution groups and mail-enabled security groups in standalone EOP PowerShell, run the following command:</span></span>

```powershell
Get-Recipient -RecipientType MailUniversalDistributionGroup,MailUniversalSecurityGroup -ResultSize unlimited
```

<span data-ttu-id="57817-200">그룹 구성원 목록을 반환하기 위해 그룹의 이름, 별칭 또는 전자 메일 주소로 바꾸고 다음 \<GroupIdentity\> 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="57817-200">To return the list of group members, replace \<GroupIdentity\> with the name, alias, or email address of the group, and run the following command:</span></span>

```powershell
Get-DistributionGroupMember -Identity <GroupIdentity>
```

<span data-ttu-id="57817-201">구문과 매개 변수에 대한 자세한 내용은 [Get-Recipient](/powershell/module/exchange/get-recipient) 및 [Get-DistributionGroupMember를 참조하십시오.](/powershell/module/exchange/get-distributiongroupmember)</span><span class="sxs-lookup"><span data-stu-id="57817-201">For detailed syntax and parameter information, see [Get-Recipient](/powershell/module/exchange/get-recipient) and [Get-DistributionGroupMember](/powershell/module/exchange/get-distributiongroupmember).</span></span>

### <a name="use-standalone-eop-powershell-to-create-groups"></a><span data-ttu-id="57817-202">독립 실행형 EOP PowerShell을 사용하여 그룹 만들기</span><span class="sxs-lookup"><span data-stu-id="57817-202">Use standalone EOP PowerShell to create groups</span></span>

<span data-ttu-id="57817-203">독립 실행형 EOP PowerShell에서 메일 그룹 또는 메일 사용이 가능한 보안 그룹을 만들 경우 다음 구문을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="57817-203">To create distribution groups or mail-enabled security groups in standalone EOP PowerShell, use the following syntax:</span></span>

```PowerShell
New-EOPDistributionGroup -Name "<Unique Name>" -ManagedBy @("UserOrGroup1","UserOrGroup2",..."UserOrGroupN">) [-Alias <text>] [-DisplayName "<Descriptive Name>"] [-Members @("UserOrGroup1","UserOrGroup2",..."UserOrGroupN">)] [-Notes "<Optional Text>"] [-PrimarySmtpAddress <SmtpAddress>] [-Type <Distribution | Security>]
```

<span data-ttu-id="57817-204">**참고:**</span><span class="sxs-lookup"><span data-stu-id="57817-204">**Notes**:</span></span>

- <span data-ttu-id="57817-205">_Name 매개_ 변수는 필수입니다. 최대 길이는 64자입니다.</span><span class="sxs-lookup"><span data-stu-id="57817-205">The _Name_ parameter is required, has a maximum length of 64 characters, and must be unique.</span></span> <span data-ttu-id="57817-206">_DisplayName_ 매개 변수를 사용하지 않는 경우에는 _Name_ 매개 변수의 값이 표시 이름에 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="57817-206">If you don't use the _DisplayName_ parameter, the value of the _Name_ parameter is used for the display name.</span></span>

- <span data-ttu-id="57817-207">_Alias_ 매개 변수를 사용하지 않는 경우 _Name_ 매개 변수가 별칭 값에 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="57817-207">If you don't use the _Alias_ parameter, the _Name_ parameter is used for the alias value.</span></span> <span data-ttu-id="57817-208">공백이 제거되고, 미지원 문자는 물음표(?)로 변환됩니다.</span><span class="sxs-lookup"><span data-stu-id="57817-208">Spaces are removed and unsupported characters are converted to question marks (?).</span></span>

- <span data-ttu-id="57817-209">_PrimarySmtpAddress_ 매개 변수를 사용하지 않는 경우 _PrimarySmtpAddress_ 매개 변수에 별칭 값이 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="57817-209">If you don't use the _PrimarySmtpAddress_ parameter, the alias value is used in the _PrimarySmtpAddress_ parameter.</span></span>

- <span data-ttu-id="57817-210">_Type_ 매개 변수를 사용하지 않는 경우 기본값은 Distribution입니다.</span><span class="sxs-lookup"><span data-stu-id="57817-210">If you don't use the _Type_ parameter, the default value is Distribution.</span></span>

<span data-ttu-id="57817-211">이 예에서는 지정된 속성을 사용하여 IT Administrators라는 메일 그룹을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="57817-211">This example creates a distribution group named IT Administrators with the specified properties.</span></span>

```PowerShell
New-EOPDistributionGroup -Name "IT Administrators" -Alias itadmin -Members @("michelle@contoso.com","laura@contoso.com","julia@contoso.com") -ManagedBy "chris@contoso.com"
```

<span data-ttu-id="57817-212">구문과 매개 변수에 대한 자세한 내용은 [New-EOPDistributionGroup을 참조하십시오.](/powershell/module/exchange/New-EOPDistributionGroup)</span><span class="sxs-lookup"><span data-stu-id="57817-212">For detailed syntax and parameter information, see [New-EOPDistributionGroup](/powershell/module/exchange/New-EOPDistributionGroup).</span></span>

### <a name="use-standalone-eop-powershell-to-modify-groups"></a><span data-ttu-id="57817-213">독립 실행형 EOP PowerShell을 사용하여 그룹 수정</span><span class="sxs-lookup"><span data-stu-id="57817-213">Use standalone EOP PowerShell to modify groups</span></span>

<span data-ttu-id="57817-214">독립 실행형 EOP PowerShell에서 그룹을 수정하려면 다음 구문을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="57817-214">To modify groups in standalone EOP PowerShell, use the following syntax:</span></span>

```powershell
Set-EOPDistributionGroup -Identity <GroupIdentity> [-Alias <Text>] [-DisplayName <Text>] [-ManagedBy @("User1","User2",..."UserN")] [-PrimarySmtpAddress <SmtpAddress>]

```powershell
Update-EOPDistributionGroupMember -Identity <GroupIdentity> -Members @("User1","User2",..."UserN")
```

<span data-ttu-id="57817-215">이 예에서는 Seattle Employees 그룹의 기본 SMTP 주소(회신 주소)를 변경하여 sea.employees@contoso.com.</span><span class="sxs-lookup"><span data-stu-id="57817-215">This example uses changes the primary SMTP address (also called the reply address) for the Seattle Employees group to sea.employees@contoso.com.</span></span>

```PowerShell
Set-EOPDistributionGroup "Seattle Employees" -PrimarySmtpAddress "sea.employees@contoso.com"
```

<span data-ttu-id="57817-216">이 예에서는 보안 팀 그룹의 현재 구성원을 Kitty Petersen 및 Tyson Fawcett로 바 대체합니다.</span><span class="sxs-lookup"><span data-stu-id="57817-216">This example replaces the current members of the Security Team group with Kitty Petersen and Tyson Fawcett.</span></span>

```powershell
Update-EOPDistributionGroupMember -Identity "Security Team" -Members @("Kitty Petersen","Tyson Fawcett")
```

<span data-ttu-id="57817-217">이 예에서는 그룹의 현재 구성원을 보존하면서 Security Team이라는 그룹에 Tyson Fawcett라는 새 사용자를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="57817-217">This example adds a new user named Tyson Fawcett to the group named Security Team while preserving the current members of the group.</span></span>

```powershell
$CurrentMemberObjects = Get-DistributionGroupMember "Security Team"
$CurrentMemberNames = $CurrentMemberObjects | % {$_.name}
$CurrentMemberNames += "Tyson Fawcett"
Update-EOPDistributionGroupMember -Identity "Security Team" -Members $CurrentMemberNames
```

<span data-ttu-id="57817-218">구문과 매개 변수에 대한 자세한 내용은 [Set-EOPDistributionGroup](/powershell/module/exchange/set-eopdistributiongroup) 및 [Update-EOPDistributionGroupMember를 참조하십시오.](/powershell/module/exchange/update-eopdistributiongroupmember)</span><span class="sxs-lookup"><span data-stu-id="57817-218">For detailed syntax and parameter information, see [Set-EOPDistributionGroup](/powershell/module/exchange/set-eopdistributiongroup) and [Update-EOPDistributionGroupMember](/powershell/module/exchange/update-eopdistributiongroupmember).</span></span>

### <a name="remove-a-group-using-remote-windows-powershell"></a><span data-ttu-id="57817-219">원격 제어를 사용하여 그룹 Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="57817-219">Remove a group using remote Windows PowerShell</span></span>

<span data-ttu-id="57817-220">이 예에서는 IT Administrators라는 메일 그룹을 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="57817-220">This example uses removes the distribution group named IT Administrators.</span></span>

```PowerShell
Remove-EOPDistributionGroup -Identity "IT Administrators"
```

<span data-ttu-id="57817-221">구문과 매개 변수에 대한 자세한 내용은 [Remove-EOPDistributionGroup을 참조하십시오.](/powershell/module/exchange/remove-eopdistributiongroup)</span><span class="sxs-lookup"><span data-stu-id="57817-221">For detailed syntax and parameter information, see [Remove-EOPDistributionGroup](/powershell/module/exchange/remove-eopdistributiongroup).</span></span>

## <a name="how-do-you-know-these-procedures-worked"></a><span data-ttu-id="57817-222">이 절차가 제대로 수행되었는지 어떻게 확인하나요?</span><span class="sxs-lookup"><span data-stu-id="57817-222">How do you know these procedures worked?</span></span>

<span data-ttu-id="57817-223">메일 그룹 또는 메일 사용이 가능한 보안 그룹을 성공적으로 만들거나 수정하거나 제거한 경우 다음 단계를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="57817-223">To verify that you've successfully created, modified, or removed a distribution group or a mail-enabled security group, do any of the following steps:</span></span>

- <span data-ttu-id="57817-224">EAC에서 받는 사람 **그룹 으로** \> **이동 합니다.**</span><span class="sxs-lookup"><span data-stu-id="57817-224">In the EAC, go to **Recipients** \> **Groups**.</span></span> <span data-ttu-id="57817-225">그룹이 나열되어 있는지 또는 나열되지 않는지 확인하고 그룹 유형 **값을** 검증합니다.</span><span class="sxs-lookup"><span data-stu-id="57817-225">Verify that the group is listed (or not listed), and verify the **Group Type** value.</span></span> <span data-ttu-id="57817-226">그룹을 선택하고 세부 정보 창에서 정보를 보거나  편집 편집 아이콘을 클릭하여 설정을 ![ ](../../media/ITPro-EAC-AddIcon.png) 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="57817-226">Select the group and view the information in the Details pane, or click **Edit** ![Edit icon](../../media/ITPro-EAC-AddIcon.png) to view the settings.</span></span>

- <span data-ttu-id="57817-227">독립 실행형 EOP PowerShell에서 다음 명령을 실행하여 그룹이 나열되어 있는지(또는 목록에 없는지) 확인</span><span class="sxs-lookup"><span data-stu-id="57817-227">In standalone EOP PowerShell, run the following command to verify the group is listed (or isn't listed):</span></span>

  ```PowerShell
  Get-Recipient -RecipientType MailUniversalDistributionGroup,MailUniversalSecurityGroup -ResultSize unlimited
  ```

- <span data-ttu-id="57817-228">그룹의 이름, 별칭 또는 전자 메일 주소로 바꾸고 다음 명령을 실행하여 \<GroupIdentity\> 설정을 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="57817-228">Replace \<GroupIdentity\> with the name, alias, or email address of the group and run the following command to verify the settings:</span></span>

  ```PowerShell
  Get-Recipient -Identity <GroupIdentity> | Format-List
  ```

- <span data-ttu-id="57817-229">그룹 구성원을 확인하거나 그룹의 이름, 별칭 또는 전자 메일 주소로 바꾸고 다음 \<GroupIdentity\> 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="57817-229">To view the group members, replace \<GroupIdentity\> with the name, alias, or email address of the group and run the following command:</span></span>

  ```PowerShell
  Get-DistributionGroupMember -Identity "<GroupIdentity>"
  ```