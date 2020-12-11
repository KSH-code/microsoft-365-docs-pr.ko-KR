---
title: 조직에서 사서함에 대한 보관 및 삭제 정책 설정하기
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- Strat_O365_IP
- M365-security-compliance
search.appverid:
- MOE150
- MED150
- MBS150
- BCS160
- MET150
ms.assetid: ec3587e4-7b4a-40fb-8fb8-8aa05aeae2ce
ms.custom: seo-marvel-apr2020
description: 항목을 사용자의 보관 사서함으로 자동으로 이동하는 Microsoft 365에서 보관 및 삭제 정책을 만드는 방법을 알아보고
ms.openlocfilehash: 5e8675c1cc6e1df4c22e55648e1655798bae5e5b
ms.sourcegitcommit: 21b0ea5715e20b4ab13719eb18c97fadb49b563d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/11/2020
ms.locfileid: "49624780"
---
# <a name="set-up-an-archive-and-deletion-policy-for-mailboxes-in-your-organization"></a><span data-ttu-id="dcd35-103">조직에서 사서함에 대한 보관 및 삭제 정책 설정하기</span><span class="sxs-lookup"><span data-stu-id="dcd35-103">Set up an archive and deletion policy for mailboxes in your organization</span></span>

<span data-ttu-id="dcd35-104">Microsoft 365에서 관리자는 항목을 사용자의 보관 사서함으로 자동으로 이동하고 사서함에서 항목을 자동으로 삭제하는 보관 및 삭제 정책을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dcd35-104">In Microsoft 365, admins can create an archiving and deletion policy that automatically moves items to a user's archive mailbox and automatically deletes items from the mailbox.</span></span> <span data-ttu-id="dcd35-105">관리자는 사서함에 할당된 보존 정책을 만들고 특정 기간이 지난 후 항목을 사용자의 보관 사서함으로 이동하고 특정 보존 기간에 도달한 후에도 사서함에서 항목을 삭제합니다.</span><span class="sxs-lookup"><span data-stu-id="dcd35-105">The admin does this by creating a retention policy that's assigned to mailboxes, and moves items to a user's archive mailbox after a certain period of time and that also deletes items from the mailbox after they reach a certain age limit.</span></span> <span data-ttu-id="dcd35-106">이동 또는 삭제되는 항목과 이 경우를 결정하는 실제 규칙을 보존 태그라고 합니다.</span><span class="sxs-lookup"><span data-stu-id="dcd35-106">The actual rules that determine what items are moved or deleted and when that happens are called retention tags.</span></span> <span data-ttu-id="dcd35-107">보존 태그는 보존 정책에 연결되어 사용자 사서함에 차례로 할당됩니다.</span><span class="sxs-lookup"><span data-stu-id="dcd35-107">Retention tags are linked to a retention policy, that in turn is assigned to a user's mailbox.</span></span> <span data-ttu-id="dcd35-108">보존 태그는 사용자 사서함의 개별 메시지 및 폴더에 보존 설정을 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="dcd35-108">A retention tag applies retention settings to individual messages and folders in a user's mailbox.</span></span> <span data-ttu-id="dcd35-109">사서함에 메시지가 남아 있는 기간 및 메시지가 지정된 보존 기간에 도달하면 수행되는 작업을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="dcd35-109">It defines how long a message remains in the mailbox and what action is taken when the message reaches the specified retention age.</span></span> <span data-ttu-id="dcd35-110">메시지가 보존 기간에 도달하면 사용자의 보관 사서함으로 이동되거나 삭제됩니다.</span><span class="sxs-lookup"><span data-stu-id="dcd35-110">When a message reaches its retention age, it's either moved to the user's archive mailbox or it's deleted.</span></span>
  
<span data-ttu-id="dcd35-111">이 문서의 단계에서는 Alpine House라는 인명 조직에 대한 보관 및 보존 정책을 설정할 것입니다.</span><span class="sxs-lookup"><span data-stu-id="dcd35-111">The steps in this article will set up an archiving and retention policy for a fictitious organization named Alpine House.</span></span> <span data-ttu-id="dcd35-112">이 정책을 설정하는 작업에는 다음 작업이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="dcd35-112">Setting up this policy includes the following tasks:</span></span>
  
- <span data-ttu-id="dcd35-113">조직의 모든 사용자에 대해 보관 사서함을 사용하도록 설정</span><span class="sxs-lookup"><span data-stu-id="dcd35-113">Enabling an archive mailbox for every user in the organization.</span></span> <span data-ttu-id="dcd35-114">이렇게 하면 사용자에게 사서함 저장소가 추가되어 보존 정책이 항목을 보관 사서함으로 이동할 수 있도록 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="dcd35-114">This gives users addition mailbox storage, and is required so that a retention policy can move items to the archive mailbox.</span></span> <span data-ttu-id="dcd35-115">또한 항목을 보관 사서함으로 이동하여 보관 정보를 저장할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dcd35-115">It also lets a user store archival information by moving items to their archive mailbox.</span></span>

- <span data-ttu-id="dcd35-116">다음을 하는 세 가지 사용자 지정 보존 태그 만들기</span><span class="sxs-lookup"><span data-stu-id="dcd35-116">Creating three custom retention tags that do the following:</span></span>

  - <span data-ttu-id="dcd35-117">3년이 지난 항목은 사용자의 보관 사서함으로 자동으로 이동됩니다.</span><span class="sxs-lookup"><span data-stu-id="dcd35-117">Automatically moves items that are 3 years old to the user's archive mailbox.</span></span> <span data-ttu-id="dcd35-118">항목을 보관 사서함으로 이동하면 사용자의 기본 사서함에 공간을 비우게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="dcd35-118">Moving items to the archive mailbox frees up space in a user's primary mailbox.</span></span>

  - <span data-ttu-id="dcd35-119">지우기 항목 폴더에서 5년 된 항목을 자동으로 삭제합니다.</span><span class="sxs-lookup"><span data-stu-id="dcd35-119">Automatically deletes items that are 5 years old from the Deleted Items folder.</span></span> <span data-ttu-id="dcd35-120">이렇게 하여 사용자의 기본 사서함에 공간을 비울 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dcd35-120">This also frees up space in the user's primary mailbox.</span></span> <span data-ttu-id="dcd35-121">사용자는 필요한 경우 이러한 항목을 복구할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dcd35-121">User's will have the opportunity to recover these items if necessary.</span></span> <span data-ttu-id="dcd35-122">자세한 내용은 추가 정보 [](#more-information) 섹션의 각주를 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="dcd35-122">See the footnote in the [More information](#more-information) section for more details.</span></span> 

  - <span data-ttu-id="dcd35-123">기본 사서함과 보관 사서함 모두에서 7년 된 항목을 자동으로(영구적으로) 삭제합니다.</span><span class="sxs-lookup"><span data-stu-id="dcd35-123">Automatically (and permanently) deletes items that are 7 years old from both the primary and archive mailbox.</span></span> <span data-ttu-id="dcd35-124">규정 준수 규정 때문에 일부 조직에서는 특정 기간 동안 전자 메일을 보존해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="dcd35-124">Because of compliance regulations, some organization's are required to retain email for a certain period of time.</span></span> <span data-ttu-id="dcd35-125">이 기간이 만료되면 조직에서 이러한 항목 사용자 사서함을 영구적으로 제거할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dcd35-125">After this time period expires, an organization might want to permanently remove these items user mailboxes.</span></span>

- <span data-ttu-id="dcd35-126">새 보존 정책을 만들고 새 사용자 지정 보존 태그를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="dcd35-126">Creating a new retention policy and adding the new custom retention tags to it.</span></span> <span data-ttu-id="dcd35-127">또한 새 보존 정책에 기본 제공 보존 태그를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="dcd35-127">Additionally, you'll also add built-in retention tags to the new retention policy.</span></span> <span data-ttu-id="dcd35-128">여기에는 사용자가 사서함의 항목에 할당할 수 있는 개인 태그가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="dcd35-128">This includes personal tags that users can assign to items in their mailbox.</span></span> <span data-ttu-id="dcd35-129">또한 사용자의 기본 사서함에 있는 복구 가능한 항목 폴더의 항목을 보관 사서함의 복구 가능한 항목 폴더로 이동하는 보존 태그를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="dcd35-129">You'll also add a retention tag that moves items from the Recoverable Items folder in the user's primary mailbox to the Recoverable Items folder in their archive mailbox.</span></span> <span data-ttu-id="dcd35-130">이렇게 하면 사서함이 보류된 경우 사용자의 복구 가능한 항목 폴더에서 공간을 비우는 데 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="dcd35-130">This helps free up space in a user's Recoverable Items folder when their mailbox is placed on hold.</span></span>

<span data-ttu-id="dcd35-131">이 문서의 일부 또는 전체 단계를 수행하여 조직 내 사서함에 대한 보관 및 삭제 정책을 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dcd35-131">You can follow some or all of the steps in this article to set up an archive and deletion policy for mailboxes in your own organization.</span></span> <span data-ttu-id="dcd35-132">조직의 모든 사서함에서 구현하기 전에 몇 개의 사서함에서 이 프로세스를 테스트하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="dcd35-132">We recommend that you test this process on a few mailboxes before implementing it on all mailboxes in your organization.</span></span>
  
## <a name="before-you-set-up-an-archive-and-deletion-policy"></a><span data-ttu-id="dcd35-133">보관함 및 삭제 정책을 설정하기 전에</span><span class="sxs-lookup"><span data-stu-id="dcd35-133">Before you set up an archive and deletion policy</span></span>

- <span data-ttu-id="dcd35-134">이 항목의 단계를 수행하기 위해 조직의 전역 관리자로 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="dcd35-134">You have to be a global administrator in your organization to perform the steps in this topic.</span></span> 

- <span data-ttu-id="dcd35-135">새 사용자 계정을 만들고 사용자에게 Exchange Online 라이선스를 할당하면 사용자에 대해 사서함이 자동으로 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="dcd35-135">When you create a new user account and assign the user an Exchange Online license, a mailbox is automatically created for the user.</span></span> <span data-ttu-id="dcd35-136">사서함을 만들면 기본 MRM 정책이라는 기본 보존 정책이 자동으로 할당됩니다.</span><span class="sxs-lookup"><span data-stu-id="dcd35-136">When the mailbox is created, it's automatically assigned a default retention policy, named Default MRM Policy.</span></span> <span data-ttu-id="dcd35-137">이 문서에서는 새 보존 정책을 만든 다음 사용자 사서함에 할당하여 기본 MRM 정책을 대체합니다.</span><span class="sxs-lookup"><span data-stu-id="dcd35-137">In this article, you will create a new retention policy and then assign it to user mailboxes, replacing the Default MRM policy.</span></span> <span data-ttu-id="dcd35-138">사서함에는 한 번만 보존 정책이 할당될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dcd35-138">A mailbox can have only one retention policy assigned to it at any one time.</span></span>

- <span data-ttu-id="dcd35-139">Exchange Online의 보존 태그 및 보존 정책에 대한 자세한 내용은 보존 태그 [및 보존 정책을 참조하세요.](https://go.microsoft.com/fwlink/p/?LinkId=404424)</span><span class="sxs-lookup"><span data-stu-id="dcd35-139">To learn more about retention tags and retention policies in Exchange Online, see [Retention tags and retention policies](https://go.microsoft.com/fwlink/p/?LinkId=404424).</span></span>

## <a name="step-1-enable-archive-mailboxes-for-users"></a><span data-ttu-id="dcd35-140">1단계: 사용자에 대해 보관 사서함 사용</span><span class="sxs-lookup"><span data-stu-id="dcd35-140">Step 1: Enable archive mailboxes for users</span></span>

<span data-ttu-id="dcd35-141">첫 번째 단계는 조직의 각 사용자에 대해 보관 사서함을 사용하도록 설정하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="dcd35-141">The first step is to enable the archive mailbox for each user in your organization.</span></span> <span data-ttu-id="dcd35-142">보존 기간이 만료된 후 "보관함으로 이동" 보존 작업이 있는 보존 태그가 항목을 이동할 수 있도록 사용자의 보관 사서함을 사용하도록 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="dcd35-142">A user's archive mailbox has to be enabled so that a retention tag with a "Move to Archive" retention action can move the item after the retention age expires.</span></span>
  
> [!NOTE]
> <span data-ttu-id="dcd35-143">프로세스를 완료하기 전에 특정 시점에 보관 사서함을 사용하도록 설정하는 한 이 프로세스 중에 보관 사서함을 사용하도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dcd35-143">You can enable archive mailboxes any time during this process, just as long as they're enabled at some point before you complete the process.</span></span> <span data-ttu-id="dcd35-144">보관 사서함을 사용하도록 설정하지 않은 경우 보관함 또는 삭제 정책이 할당된 항목에 대해 아무 작업도 수행되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="dcd35-144">If an archive mailbox isn't enabled, no action is taken on any items that have an archive or deletion policy assigned to it.</span></span>
  
1. <span data-ttu-id="dcd35-145">[https://protection.office.com](https://protection.office.com)으로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="dcd35-145">Go to [https://protection.office.com](https://protection.office.com).</span></span>

2. <span data-ttu-id="dcd35-146">전역 관리자 계정을 사용하여 로그인합니다.</span><span class="sxs-lookup"><span data-stu-id="dcd35-146">Sign in using your global administrator account.</span></span>
    
3. <span data-ttu-id="dcd35-147">보안 및 & 센터에서 정보 **거버넌스 보관으로** \> **이동하십시오.**</span><span class="sxs-lookup"><span data-stu-id="dcd35-147">In the Security & Compliance Center, go to **Information governance** \> **Archive**.</span></span>

    <span data-ttu-id="dcd35-148">조직의 사서함 목록과 해당 보관 사서함을 사용할 수 있는지 여부가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="dcd35-148">A list of the mailboxes in your organization is displayed and whether the corresponding archive mailbox is enabled or disabled.</span></span>

4. <span data-ttu-id="dcd35-149">목록의 첫 번째 사서함을 클릭하고 **Shift** 키를 잡고 목록에서 마지막 사서함을 클릭하여 모든 사서함을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="dcd35-149">Select all the mailboxes by clicking on the first one in the list, holding down the **Shift** key, and then clicking the last one in the list.</span></span>

    > [!TIP]
    > <span data-ttu-id="dcd35-150">이 단계에서는 보관 사서함이 사용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="dcd35-150">This step assumes that no archive mailboxes are enabled.</span></span> <span data-ttu-id="dcd35-151">보관함이 사용하도록 설정된 사서함이 있는 경우 **Ctrl** 키를 유지하고 사용하지 않도록 설정된 보관 사서함이 있는 각 사서함을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="dcd35-151">If you have any mailboxes with the archive enabled, hold down the **Ctrl** key and click each mailbox that has a disabled archive mailbox.</span></span> <span data-ttu-id="dcd35-152">또는 보관 사서함  열 헤더를 클릭하여 보관 사서함을 보다 쉽게 선택할 수 있도록 보관 사서함을 사용할지 여부를 기준으로 행을 정렬할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dcd35-152">Or you can click the **Archive mailbox** column header to sort the rows based on whether the archive mailbox is enabled or disabled to make it easier to select mailboxes.</span></span>
  
5. <span data-ttu-id="dcd35-153">세부 정보 창의 대량 편집 **아래에서** 사용 **을 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="dcd35-153">In the details pane, under **Bulk Edit**, click **Enable**.</span></span>

    <span data-ttu-id="dcd35-154">2년이 지난 항목은 새 보관 사서함으로 이동될 것임에 대한 경고가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="dcd35-154">A warning is displayed saying that items that are older than two years will be moved to the new archive mailbox.</span></span> <span data-ttu-id="dcd35-155">이는 새 사용자 사서함을 만들 때 할당된 기본 보존 정책에 보존 기간이 2년인 보관 기본 정책 태그가 있기 때문에입니다.</span><span class="sxs-lookup"><span data-stu-id="dcd35-155">This is because the default retention policy that's assigned a new user mailbox when it's created has an archive default policy tag that has a retention age of 2 years.</span></span> <span data-ttu-id="dcd35-156">2단계에서 만들 사용자 지정 보관 기본 정책 태그의 보존 기간은 3년입니다.</span><span class="sxs-lookup"><span data-stu-id="dcd35-156">The custom archive default policy tag that you'll create in Step 2 has a retention age of 3 years.</span></span> <span data-ttu-id="dcd35-157">즉, 3년 이상 된 항목이 보관 사서함으로 이동됩니다.</span><span class="sxs-lookup"><span data-stu-id="dcd35-157">That means items that are 3 years or older will be moved to the archive mailbox.</span></span>

6. <span data-ttu-id="dcd35-158">**예를** 클릭하여 경고 메시지를 닫고 선택한 각 사서함에 대해 보관 사서함을 사용하도록 설정하는 프로세스를 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="dcd35-158">Click **Yes** to close the warning message and start the process to enable the archive mailbox for each selected mailbox.</span></span>

7. <span data-ttu-id="dcd35-159">프로세스가 완료되면 새로 고침을 **클릭하여** 보관 페이지의 ![ 목록을 ](../media/165fb3ad-38a8-4dd9-9e76-296aefd96334.png) **업데이트합니다.**</span><span class="sxs-lookup"><span data-stu-id="dcd35-159">When the process is complete, click **Refresh** ![refresh](../media/165fb3ad-38a8-4dd9-9e76-296aefd96334.png) to update the list on the **Archive** page.</span></span>

    <span data-ttu-id="dcd35-160">보관 사서함은 조직의 모든 사용자에 대해 사용하도록 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="dcd35-160">The archive mailbox is enabled for all user's in your organization.</span></span>

    ![보관 사서함이 사용하도록 설정된 사서함 목록](../media/61a7cb97-1bed-4808-aa5f-b6b761cfa8de.png)

## <a name="step-2-create-new-retention-tags-for-the-archive-and-deletion-policies"></a><span data-ttu-id="dcd35-162">2단계: 보관 및 삭제 정책에 대한 새 보존 태그 만들기</span><span class="sxs-lookup"><span data-stu-id="dcd35-162">Step 2: Create new retention tags for the archive and deletion policies</span></span>

<span data-ttu-id="dcd35-163">이 단계에서는 이전에 설명한 세 가지 사용자 지정 보존 태그를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="dcd35-163">In this step, you'll create the three custom retention tags that were previously described.</span></span>
  
- <span data-ttu-id="dcd35-164">알파인 하우스 3년 후 보관함으로 이동(사용자 지정 보관 정책)</span><span class="sxs-lookup"><span data-stu-id="dcd35-164">Alpine House 3 Year Move to Archive (custom archive policy)</span></span>

- <span data-ttu-id="dcd35-165">알파인 하우스 7년 영구 삭제(사용자 지정 삭제 정책)</span><span class="sxs-lookup"><span data-stu-id="dcd35-165">Alpine House 7 Year Permanently Delete (custom deletion policy)</span></span>

- <span data-ttu-id="dcd35-166">Alpine House Deleted Items 5 Years Delete and Allow Recovery (custom tag for the Deleted Items folder)</span><span class="sxs-lookup"><span data-stu-id="dcd35-166">Alpine House Deleted Items 5 Years Delete and Allow Recovery (custom tag for the Deleted Items folder)</span></span>

<span data-ttu-id="dcd35-167">새 보존 태그를 만들하려면 Exchange Online 조직에서 EAC(Exchange 관리 센터)를 사용하게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="dcd35-167">To create new retention tags, you'll use the Exchange admin center (EAC) in your Exchange Online organization.</span></span> <span data-ttu-id="dcd35-168">EAC의 클래식 버전을 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="dcd35-168">Be sure to use the classic version of the EAC.</span></span>
  
1. <span data-ttu-id="dcd35-169">이동하여 [https://admin.protection.outlook.com/ecp/](https://admin.protection.outlook.com/ecp/) 자격 증명을 사용하여 로그인합니다.</span><span class="sxs-lookup"><span data-stu-id="dcd35-169">Go to [https://admin.protection.outlook.com/ecp/](https://admin.protection.outlook.com/ecp/) and sign in using your credentials.</span></span>
  
2. <span data-ttu-id="dcd35-170">EAC에서 준수 **관리** 보존  >  **태그로 이동**</span><span class="sxs-lookup"><span data-stu-id="dcd35-170">In the EAC, go to **Compliance management** > **Retention tags**</span></span>

    <span data-ttu-id="dcd35-171">조직의 보존 태그 목록이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="dcd35-171">A list of the retention tags for your organization is displayed.</span></span>

### <a name="create-a-custom-archive-default-policy-tag"></a><span data-ttu-id="dcd35-172">사용자 지정 보관 기본 정책 태그 만들기</span><span class="sxs-lookup"><span data-stu-id="dcd35-172">Create a custom archive default policy tag</span></span>
  
<span data-ttu-id="dcd35-173">먼저 3년 후에 항목을 보관 사서함으로 이동하는 사용자 지정 보관 기본 정책 태그(DPT)를 만들어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="dcd35-173">First, you'll create a custom archive default policy tag (DPT) that will move items to the archive mailbox after 3 years.</span></span>
  
1. <span data-ttu-id="dcd35-174">보존 태그 **페이지에서** 새 태그 **새** 아이콘을 클릭한 다음 전체 사서함에 자동으로 ![ ](../media/457cd93f-22c2-4571-9f83-1b129bcfb58e.gif) **적용(기본값)을 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="dcd35-174">On the **Retention tags** page, click **New tag**![New icon](../media/457cd93f-22c2-4571-9f83-1b129bcfb58e.gif), and then select **applied automatically to entire mailbox (default)**.</span></span>

2. <span data-ttu-id="dcd35-175">전체 **사서함(기본값) 페이지에** 자동으로 적용된 새 태그에서 다음 필드를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="dcd35-175">On the **New tag applied automatically to entire mailbox (default)** page, complete the following fields:</span></span> 

    ![새 보관 기본 정책 태그를 만드는 설정](../media/41c0a43c-9c72-44e0-8947-da0831896432.png)
  
   1. <span data-ttu-id="dcd35-177">**이름** 새 보존 태그의 이름을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="dcd35-177">**Name** Type a name for the new retention tag.</span></span> 

   2. <span data-ttu-id="dcd35-178">**보존 작업** 보존 **기간이** 만료되면 항목을 보관 사서함으로 이동하려면 보관함으로 이동을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="dcd35-178">**Retention action** Select **Move to Archive** to move items to the archive mailbox when the retention period expires.</span></span>

   3. <span data-ttu-id="dcd35-179">**보존 기간** 항목이 다음 기간(일)에 도달하면 선택한 다음 보존 기간을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="dcd35-179">**Retention period** Select **When the item reaches the following age (in days)**, and then enter the duration of the retention period.</span></span> <span data-ttu-id="dcd35-180">이 시나리오에서는 항목이 1095일(3년) 후에 보관 사서함으로 이동됩니다.</span><span class="sxs-lookup"><span data-stu-id="dcd35-180">For this scenario, items will be moved to the archive mailbox after 1095 days (3 years).</span></span>

   4. <span data-ttu-id="dcd35-181">**설명(선택** 사항) 사용자 지정 보존 태그의 용도를 설명하는 설명을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="dcd35-181">**Comment** (Optional) Type a comment that explains the purpose of the custom retention tag.</span></span>

3. <span data-ttu-id="dcd35-182">**저장을** 클릭하여 사용자 지정 보관 DPT를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dcd35-182">Click **Save** to create the custom archive DPT.</span></span>

    <span data-ttu-id="dcd35-183">새 보관 DPT는 보존 태그 목록에 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="dcd35-183">The new archive DPT is displayed in the list of retention tags.</span></span>

### <a name="create-a-custom-deletion-default-policy-tag"></a><span data-ttu-id="dcd35-184">사용자 지정 지우기 기본 정책 태그 만들기</span><span class="sxs-lookup"><span data-stu-id="dcd35-184">Create a custom deletion default policy tag</span></span>
  
<span data-ttu-id="dcd35-185">다음으로 다른 사용자 지정 DPT를 만들지만 이 정책은 7년 후에 항목을 영구적으로 삭제하는 삭제 정책입니다.</span><span class="sxs-lookup"><span data-stu-id="dcd35-185">Next, you'll create another custom DPT but this one will be a deletion policy that permanently deletes items after 7 years.</span></span>
  
1. <span data-ttu-id="dcd35-186">보존 태그 **페이지에서** 새 태그 **새** 아이콘을 클릭한 다음 전체 사서함에 자동으로 ![ ](../media/457cd93f-22c2-4571-9f83-1b129bcfb58e.gif) **적용(기본값)을 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="dcd35-186">On the **Retention tags** page, click **New tag**![New icon](../media/457cd93f-22c2-4571-9f83-1b129bcfb58e.gif), and then select **applied automatically to entire mailbox (default)**.</span></span>

2. <span data-ttu-id="dcd35-187">전체 **사서함(기본값) 페이지에** 자동으로 적용된 새 태그에서 다음 필드를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="dcd35-187">On the **New tag applied automatically to entire mailbox (default)** page, complete the following fields:</span></span> 

    ![새 지우기 기본 정책 태그를 만드는 설정](../media/f1f0ff62-eec9-4824-8e7c-d93dcfb09a79.png)
  
   1. <span data-ttu-id="dcd35-189">**이름** 새 보존 태그의 이름을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="dcd35-189">**Name** Type a name for the new retention tag.</span></span> 

   2. <span data-ttu-id="dcd35-190">**보존 작업** 보존 **기간이** 만료될 때 사서함에서 항목을 제거하려면 영구 삭제를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="dcd35-190">**Retention action** Select **Permanently Delete** to purge items from the mailbox when the retention period expires.</span></span>

   3. <span data-ttu-id="dcd35-191">**보존 기간** 항목이 다음 기간(일)에 도달하면 선택한 다음 보존 기간을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="dcd35-191">**Retention period** Select **When the item reaches the following age (in days)**, and then enter the duration of the retention period.</span></span> <span data-ttu-id="dcd35-192">이 시나리오에서는 2555일(7년) 후에 항목이 제거됩니다.</span><span class="sxs-lookup"><span data-stu-id="dcd35-192">For this scenario, items will be purged after 2555 days (7 years).</span></span>

   4. <span data-ttu-id="dcd35-193">**설명(선택** 사항) 사용자 지정 보존 태그의 용도를 설명하는 설명을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="dcd35-193">**Comment** (Optional) Type a comment that explains the purpose of the custom retention tag.</span></span> 

3. <span data-ttu-id="dcd35-194">**저장을** 클릭하여 사용자 지정 지우기 DPT를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dcd35-194">Click **Save** to create the custom deletion DPT.</span></span> 

    <span data-ttu-id="dcd35-195">새 삭제 DPT는 보존 태그 목록에 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="dcd35-195">The new deletion DPT is displayed in the list of retention tags.</span></span>

### <a name="create-a-custom-retention-policy-tag-for-the-deleted-items-folder"></a><span data-ttu-id="dcd35-196">지우기 항목 폴더에 대한 사용자 지정 보존 정책 태그 만들기</span><span class="sxs-lookup"><span data-stu-id="dcd35-196">Create a custom retention policy tag for the Deleted Items folder</span></span>
  
<span data-ttu-id="dcd35-197">마지막으로 만들 보존 태그는 지우기 항목 폴더에 대한 RPT(사용자 지정 보존 정책 태그)입니다.</span><span class="sxs-lookup"><span data-stu-id="dcd35-197">The last retention tag that you'll create is a custom retention policy tag (RPT) for the Deleted Items folder.</span></span> <span data-ttu-id="dcd35-198">이 태그는 5년 후에 지우기 항목 폴더의 항목을 삭제하고 사용자가 지우기 항목 복구 도구를 사용하여 항목을 복구할 수 있는 복구 기간을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="dcd35-198">This tag will delete items in the Deleted Items folder after 5 years, and provides a recovery period when users can use the Recover Deleted Items tool to recover an item.</span></span>
  
1. <span data-ttu-id="dcd35-199">보존 태그 **페이지에서** 새  태그 새 아이콘을 클릭한 다음 기본 폴더에 자동으로 ![ ](../media/457cd93f-22c2-4571-9f83-1b129bcfb58e.gif) **적용된 태그를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="dcd35-199">On the **Retention tags** page, click **New tag** ![New icon](../media/457cd93f-22c2-4571-9f83-1b129bcfb58e.gif), and then select **applied automatically to a default folder**.</span></span>

2. <span data-ttu-id="dcd35-200">기본 폴더 페이지에 자동으로 적용된 **새** 태그에서 다음 필드를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="dcd35-200">On the **New tag applied automatically to a default folder** page, complete the following fields:</span></span>

    ![지우기 항목 폴더에 대한 새 보존 정책 태그를 만드는 설정](../media/6f3104bd-5edb-48ac-884d-5fe13d81dd1d.png)
  
   1. <span data-ttu-id="dcd35-202">**이름** 새 보존 태그의 이름을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="dcd35-202">**Name** Type a name for the new retention tag.</span></span> 

   2. <span data-ttu-id="dcd35-203">**다음 기본 폴더에 이 태그 적용** 드롭다운 목록에서 **지우기 항목을 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="dcd35-203">**Apply this tag to the following default folder** In the drop-down list, select **Deleted Items**.</span></span>

   3. <span data-ttu-id="dcd35-204">**보존 작업** 보존 **기간이** 만료될 때 항목을 삭제하려면 삭제 및 복구 허용을 선택하지만 사용자가 삭제된 항목 보존 기간(기본적으로 14일) 내에 삭제된 항목을 복구할 수 있도록 허용합니다.</span><span class="sxs-lookup"><span data-stu-id="dcd35-204">**Retention action** Select **Delete and Allow Recovery** to delete items when the retention period expires, but allow users to recover a deleted item within the deleted item retention period (which by default is 14 days).</span></span>

   4. <span data-ttu-id="dcd35-205">**보존 기간** 항목이 다음 기간(일)에 도달하면 선택한 다음 보존 기간을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="dcd35-205">**Retention period** Select **When the item reaches the following age (in days)**, and then enter the duration of the retention period.</span></span> <span data-ttu-id="dcd35-206">이 시나리오에서는 1825일(5년) 후에 항목이 삭제됩니다.</span><span class="sxs-lookup"><span data-stu-id="dcd35-206">For this scenario, items will be deleted after 1825 days (5 years).</span></span>

   5. <span data-ttu-id="dcd35-207">**설명(선택** 사항) 사용자 지정 보존 태그의 용도를 설명하는 설명을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="dcd35-207">**Comment** (Optional) Type a comment that explains the purpose of the custom retention tag.</span></span> 

3. <span data-ttu-id="dcd35-208">**저장을** 클릭하여 지우기 항목 폴더에 대한 사용자 지정 RPT를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dcd35-208">Click **Save** to create the custom RPT for the Deleted Items folder.</span></span>

    <span data-ttu-id="dcd35-209">새 RPT는 보존 태그 목록에 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="dcd35-209">The new RPT is displayed in the list of retention tags.</span></span>

## <a name="step-3-create-a-new-retention-policy"></a><span data-ttu-id="dcd35-210">3단계: 새 보존 정책 만들기</span><span class="sxs-lookup"><span data-stu-id="dcd35-210">Step 3: Create a new retention policy</span></span>

<span data-ttu-id="dcd35-211">사용자 지정 보존 태그를 만든 후 다음 단계는 새 보존 정책을 만들고 보존 태그를 추가하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="dcd35-211">After you create the custom retention tags, the next step is to create a new retention policy and add the retention tags.</span></span> <span data-ttu-id="dcd35-212">2단계에서 만든 세 가지 사용자 지정 보존 태그와 첫 번째 섹션에서 언급한 기본 제공 태그를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="dcd35-212">You'll add the three custom retention tags that you created in Step 2, and the built-in tags that were mentioned in the first section.</span></span> <span data-ttu-id="dcd35-213">4단계에서는 이 새 보존 정책을 사용자 사서함에 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="dcd35-213">In Step 4, you'll assign this new retention policy to user mailboxes.</span></span>
  
1. <span data-ttu-id="dcd35-214">EAC에서 준수 관리 보존  >  **정책으로 이동 합니다.**</span><span class="sxs-lookup"><span data-stu-id="dcd35-214">In the EAC, go to **Compliance management** > **Retention policies**.</span></span>

2. <span data-ttu-id="dcd35-215">보존 정책 **페이지에서** 새 **아이콘을** ![ ](../media/457cd93f-22c2-4571-9f83-1b129bcfb58e.gif) 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="dcd35-215">On the **Retention policies** page, click **New** ![New icon](../media/457cd93f-22c2-4571-9f83-1b129bcfb58e.gif).</span></span>

3. <span data-ttu-id="dcd35-216">이름 **상자에** 새 보존 정책의 이름을 입력합니다. 예: **Alpine House Archive and Deletion Policy**.</span><span class="sxs-lookup"><span data-stu-id="dcd35-216">In the **Name** box, type a name for the new retention policy; for example, **Alpine House Archive and Deletion Policy**.</span></span>

4. <span data-ttu-id="dcd35-217">보존 **태그 아래에서** 새로 **추가** ![ 아이콘을 ](../media/457cd93f-22c2-4571-9f83-1b129bcfb58e.gif) 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="dcd35-217">Under **Retention tags**, click **Add** ![New icon](../media/457cd93f-22c2-4571-9f83-1b129bcfb58e.gif).</span></span>

    <span data-ttu-id="dcd35-218">조직의 보존 태그 목록이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="dcd35-218">A list of the retention tags in your organization is displayed.</span></span> <span data-ttu-id="dcd35-219">2단계에서 만든 사용자 지정 태그가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="dcd35-219">Note the custom tags that you created in Step 2 are displayed.</span></span>

5. <span data-ttu-id="dcd35-220">다음 스크린샷에 강조 표시된 9개 보존 태그를 추가합니다(이러한 태그는 추가 정보 섹션에서 자세히 [설명되어](#more-information) 있습니다).</span><span class="sxs-lookup"><span data-stu-id="dcd35-220">Add the 9 retention tags that are highlighted in the following screenshot (these tags are described in more detail in the [More information](#more-information) section).</span></span> <span data-ttu-id="dcd35-221">보존 태그를 추가하려면 해당 태그를 선택하고 추가를 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="dcd35-221">To add a retention tag, select it and then click **Add**.</span></span>

    ![새 보존 정책에 보존 태그 추가](../media/d8e87176-0716-4238-9e6a-7c4af35541dc.png)
  
    > [!TIP]
    > <span data-ttu-id="dcd35-223">**Ctrl** 키를 잡고 각 태그를 클릭하여 여러 보존 태그를 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dcd35-223">You can select multiple retention tags by holding down the **Ctrl** key and then clicking each tag.</span></span> 
  
6. <span data-ttu-id="dcd35-224">보존 태그를 추가한 후 확인을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="dcd35-224">After you've added the retention tags, click **OK**.</span></span>

7. <span data-ttu-id="dcd35-225">새 보존 **정책 페이지에서** 저장을 **클릭하여** 새 정책을 만드십시오.</span><span class="sxs-lookup"><span data-stu-id="dcd35-225">On the **New retention policy** page, click **Save** to create the new policy.</span></span>

    <span data-ttu-id="dcd35-226">새 보존 정책이 목록에 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="dcd35-226">The new retention policy is displayed in the list.</span></span> <span data-ttu-id="dcd35-227">세부 정보 창에 연결된 보존 태그를 표시하려면 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="dcd35-227">Select it to display the retention tags linked to it in the details pane.</span></span>

    ![새 보존 정책 및 연결된 보존 태그 목록](../media/63bc45e6-110b-4dc9-a85f-8eb1961a8258.png)
  
## <a name="step-4-assign-the-new-retention-policy-to-user-mailboxes"></a><span data-ttu-id="dcd35-229">4단계: 사용자 사서함에 새 보존 정책 할당</span><span class="sxs-lookup"><span data-stu-id="dcd35-229">Step 4: Assign the new retention policy to user mailboxes</span></span>

<span data-ttu-id="dcd35-230">새 사서함을 만들면 기본 MRM 정책이라는 보존 정책이 기본적으로 할당됩니다.</span><span class="sxs-lookup"><span data-stu-id="dcd35-230">When a new mailbox is created, a retention policy named Default MRM policy is assigned to it by default.</span></span> <span data-ttu-id="dcd35-231">이 단계에서는 3단계에서 만든 새 보존 정책을 조직의 사용자 사서함에 할당하여 이 보존 정책(사서함에 하나의 보존 정책만 할당할 수 있기 때문에)을 대체합니다.</span><span class="sxs-lookup"><span data-stu-id="dcd35-231">In this step, you'll replace this retention policy (because a mailbox can have only one retention policy assigned to it) by assigning the new retention policy that you created in Step 3 to the user mailboxes in your organization.</span></span> <span data-ttu-id="dcd35-232">이 단계에서는 조직의 모든 사서함에 새 정책을 할당할 것으로 가정합니다.</span><span class="sxs-lookup"><span data-stu-id="dcd35-232">This step assumes that you'll assign the new policy to all mailboxes in your organization.</span></span>
  
1. <span data-ttu-id="dcd35-233">EAC에서 **받는** 사람  >  **사서함으로 이동 합니다.**</span><span class="sxs-lookup"><span data-stu-id="dcd35-233">In the EAC, go to **Recipients** > **Mailboxes**.</span></span>

    <span data-ttu-id="dcd35-234">조직의 모든 사용자 사서함 목록이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="dcd35-234">A list of all user mailboxes in your organization is displayed.</span></span>

2. <span data-ttu-id="dcd35-235">목록의 첫 번째 사서함을 클릭하고 **Shift** 키를 잡고 목록에서 마지막 사서함을 클릭하여 모든 사서함을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="dcd35-235">Select all the mailboxes by clicking on the first one in the list, holding down the **Shift** key, and then clicking the last one in the list.</span></span> 

3. <span data-ttu-id="dcd35-236">EAC 오른쪽의 세부 정보 창에서 대량 편집 **아래에서** 추가 옵션을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="dcd35-236">In the details pane on the right side of the EAC, under **Bulk Edit**, click **More options**.</span></span>

4. <span data-ttu-id="dcd35-237">**보존 정책** 에서 **업데이트** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="dcd35-237">Under **Retention Policy**, click **Update**.</span></span>

5. <span data-ttu-id="dcd35-238">보존 정책 **대량** 할당 페이지의 보존 정책 선택 **드롭다운** 목록에서 3단계에서 만든 보존 정책을 선택합니다. 예: **Alpine House Archive and Retention Policy**.</span><span class="sxs-lookup"><span data-stu-id="dcd35-238">On the **Bulk assign retention policy** page, in the **Select the retention policy** drop-down list, select the retention policy that you created in Step 3; for example, **Alpine House Archive and Retention Policy**.</span></span>

6. <span data-ttu-id="dcd35-239">**저장을** 클릭하여 새 보존 정책 할당을 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="dcd35-239">Click **Save** to save the new retention policy assignment.</span></span>

7. <span data-ttu-id="dcd35-240">새 보존 정책이 사서함에 할당되어 있는지 확인하기 위해 다음을 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dcd35-240">To verify that the new retention policy was assigned to mailboxes, you can do the following:</span></span>

   1. <span data-ttu-id="dcd35-241">사서함 페이지에서 사서함을 **선택하고** 편집을  ![ ](../media/d7dc7e5f-17a1-4eb9-b42d-487db59e2e21.png) 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="dcd35-241">Select a mailbox on the **Mailboxes** page, and then click **Edit** ![Edit](../media/d7dc7e5f-17a1-4eb9-b42d-487db59e2e21.png).</span></span>

   2. <span data-ttu-id="dcd35-242">선택한 사용자의 사서함 속성 페이지에서 사서함 **기능을 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="dcd35-242">On the mailbox properties page for the selected user, click **Mailbox features**.</span></span>

   <span data-ttu-id="dcd35-243">사서함에 할당된 새 정책의 이름이 보존  정책 드롭다운 목록에 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="dcd35-243">The name of the new policy assigned to the mailbox is displayed in the **Retention policy** drop-down list.</span></span>

## <a name="optional-step-5-run-the-managed-folder-assistant-to-apply-the-new-settings"></a><span data-ttu-id="dcd35-244">(선택 사항) 5단계: 관리되는 폴더 도우미를 실행하여 새 설정 적용</span><span class="sxs-lookup"><span data-stu-id="dcd35-244">(Optional) Step 5: Run the Managed Folder Assistant to apply the new settings</span></span>

<span data-ttu-id="dcd35-245">4단계에서 사서함에 새 보존 정책을 적용한 후 Exchange Online에서 새 보존 설정을 사서함에 적용하는 데 최대 7일이 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dcd35-245">After you apply the new retention policy to mailboxes in Step 4, it can take up to 7 days in Exchange Online for the new retention settings to be applied to the mailboxes.</span></span> <span data-ttu-id="dcd35-246">관리되는 폴더 도우미라는 프로세스가 7일마다 한 번 이상 사서함을 처리하기 때문에입니다. </span><span class="sxs-lookup"><span data-stu-id="dcd35-246">This is because a process called the *Managed Folder Assistant* processes mailboxes at least once every 7 days.</span></span> <span data-ttu-id="dcd35-247">관리되는 폴더 도우미가 실행될 때까지 기다리지 않고 Exchange Online PowerShell에서 **Start-ManagedFolderAssistant** cmdlet을 실행하여 강제로 이 일이 발생하게 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dcd35-247">Instead of waiting for the Managed Folder Assistant to run, you can force this to happen by running the **Start-ManagedFolderAssistant** cmdlet in Exchange Online PowerShell.</span></span>

 <span data-ttu-id="dcd35-248">**관리되는 폴더 도우미를 실행하면 어떻게 하나요?**</span><span class="sxs-lookup"><span data-stu-id="dcd35-248">**What happens when you run the Managed Folder Assistant?**</span></span> <span data-ttu-id="dcd35-249">사서함의 항목을 검사하고 보존이 적용되는지 여부를 확인하여 보존 정책의 설정을 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="dcd35-249">It applies the settings in the retention policy by inspecting items in the mailbox and determining whether they're subject to retention.</span></span> <span data-ttu-id="dcd35-250">그런 다음 적절한 보존 태그를 사용하여 보존이 적용된 항목을 스탬프 처리한 다음 보존 기간이 지난 항목에 대해 지정된 보존 작업을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="dcd35-250">It then stamps items subject to retention with the appropriate retention tag, and then takes the specified retention action on items past their retention age.</span></span>
  
<span data-ttu-id="dcd35-251">다음은 Exchange Online PowerShell에 연결한 다음 조직의 모든 사서함에서 관리되는 폴더 도우미를 실행하기 위한 단계입니다.</span><span class="sxs-lookup"><span data-stu-id="dcd35-251">Here are the steps to connect to Exchange Online PowerShell, and then run the Managed Folder Assistant on every mailbox in your organization.</span></span>

1. <span data-ttu-id="dcd35-252">[Exchange Online PowerShell에 연결합니다](https://go.microsoft.com/fwlink/p/?LinkId=517283).</span><span class="sxs-lookup"><span data-stu-id="dcd35-252">[Connect to Exchange Online PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=517283).</span></span>
  
2. <span data-ttu-id="dcd35-253">다음 두 명령을 실행하여 조직의 모든 사용자 사서함에 대해 관리되는 폴더 도우미를 시작할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dcd35-253">Run the following two commands to start the Managed Folder Assistant for all user mailboxes in your organization.</span></span>

    ```powershell
    $Mailboxes = Get-Mailbox -ResultSize Unlimited -Filter {RecipientTypeDetails -eq "UserMailbox"}
    ```

    ```powershell
    $Mailboxes.Identity | Start-ManagedFolderAssistant
    ```

<span data-ttu-id="dcd35-254">모두 완료되었습니다.</span><span class="sxs-lookup"><span data-stu-id="dcd35-254">That's it!</span></span> <span data-ttu-id="dcd35-255">Alpine House 조직에 대한 보관 및 삭제 정책을 설정했습니다.</span><span class="sxs-lookup"><span data-stu-id="dcd35-255">You've set up an archive and deletion policy for the Alpine House organization.</span></span>

> [!NOTE]
> <span data-ttu-id="dcd35-256">앞서 설명한 것 처럼 관리되는 폴더 도우미는 적어도 7일마다 한 번씩 사서함을 처리합니다.</span><span class="sxs-lookup"><span data-stu-id="dcd35-256">As previously stated, the Managed Folder Assistant processes mailboxes at least once every 7 days.</span></span> <span data-ttu-id="dcd35-257">따라서 관리되는 폴더 도우미가 사서함을 더 자주 처리될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dcd35-257">So it's possible that a mailbox can be processed by the Managed Folder Assistant more frequently.</span></span> <span data-ttu-id="dcd35-258">또한 다음에 관리되는 폴더 도우미가 사서함을 처리하면 관리자가 예측할 수 없습니다. 이는 수동으로 실행해야 하는 이유 중 하나입니다.</span><span class="sxs-lookup"><span data-stu-id="dcd35-258">Also, admins can't predict the next time a mailbox is processed by the Managed Folder Assistant, which is one reason why you may want to run it manually.</span></span> <span data-ttu-id="dcd35-259">그러나 관리되는 폴더 도우미가 새 보존 설정을 사서함에 적용하지 못하게 일시적으로 방지하려면 명령을 실행하여 관리되는 폴더 도우미가 사서함을 처리하지 못하게 일시적으로 사용하지 않도록 설정할 수 `Set-Mailbox -ElcProcessingDisabled $true` 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dcd35-259">However, if you want to temporarily prevent the Managed Folder Assistant from applying the new retention settings to a mailbox, you can run the `Set-Mailbox -ElcProcessingDisabled $true` command to temporarily disable the the Managed Folder Assistant from processing a mailbox.</span></span> <span data-ttu-id="dcd35-260">사서함에 대해 관리되는 폴더 도우미를 다시 사용하도록 설정하려면 명령을 `Set-Mailbox -ElcProcessingDisabled $false` 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="dcd35-260">To re-enable the Managed Folder Assistant for a mailbox, run the `Set-Mailbox -ElcProcessingDisabled $false` command.</span></span> <span data-ttu-id="dcd35-261">마지막으로, 사서함 사용자가 사용하지 않도록 설정한 계정이 있는 경우 해당 사서함에 대한 보관 작업을 보관할 이동 항목을 처리하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="dcd35-261">Finally, if a mailbox user has a disabled account, we will not process the move items to archive action for that mailbox.</span></span>
  
## <a name="optional-step-6-make-the-new-retention-policy-the-default-for-your-organization"></a><span data-ttu-id="dcd35-262">(선택 사항) 6단계: 새 보존 정책을 조직의 기본값으로 설정</span><span class="sxs-lookup"><span data-stu-id="dcd35-262">(Optional) Step 6: Make the new retention policy the default for your organization</span></span>

<span data-ttu-id="dcd35-263">4단계에서 기존 사서함에 새 보존 정책을 할당해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="dcd35-263">In Step 4, you have to assign the new retention policy to existing mailboxes.</span></span> <span data-ttu-id="dcd35-264">하지만 새 보존 정책이 향후 만들어지도록 Exchange Online을 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dcd35-264">But you can configure Exchange Online so that the new retention policy is assigned to new mailboxes that are created in the future.</span></span> <span data-ttu-id="dcd35-265">이 작업을 위해 Exchange Online PowerShell을 사용하여 조직의 기본 사서함 계획을 업데이트합니다.</span><span class="sxs-lookup"><span data-stu-id="dcd35-265">You do this by using Exchange Online PowerShell to update your organization's default mailbox plan.</span></span> <span data-ttu-id="dcd35-266">사서함 *계획은* 새 사서함의 속성을 자동으로 구성하는 템플릿입니다.</span><span class="sxs-lookup"><span data-stu-id="dcd35-266">A *mailbox plan* is a template that automatically configures properties on new mailboxes.</span></span>  <span data-ttu-id="dcd35-267">이 선택적 단계에서는 사서함 계획에 할당된 현재 보존 정책(기본적으로 기본 MRM 정책)을 3단계에서 만든 보존 정책으로 바꿀 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dcd35-267">In this optional step, you can replace the current retention policy that's assigned to the mailbox plan (by default, the Default MRM Policy) with the retention policy that you created in Step 3.</span></span> <span data-ttu-id="dcd35-268">사서함 계획을 업데이트하면 새 보존 정책이 새 사서함에 할당됩니다.</span><span class="sxs-lookup"><span data-stu-id="dcd35-268">After you update the mailbox plan, the new retention policy will be assigned to new mailboxes.</span></span>

1. <span data-ttu-id="dcd35-269">[Exchange Online PowerShell에 연결합니다](https://go.microsoft.com/fwlink/p/?LinkId=517283).</span><span class="sxs-lookup"><span data-stu-id="dcd35-269">[Connect to Exchange Online PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=517283).</span></span>

2. <span data-ttu-id="dcd35-270">다음 명령을 실행하여 조직의 사서함 계획에 대한 정보를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="dcd35-270">Run the following command to display information about the mailbox plans in your organization.</span></span>

    ```powershell
    Get-MailboxPlan | Format-Table DisplayName,RetentionPolicy,IsDefault
    ```

    <span data-ttu-id="dcd35-271">기본값으로 설정된 사서함 계획을 유의합니다.</span><span class="sxs-lookup"><span data-stu-id="dcd35-271">Note the mailbox plan that's set as the default.</span></span>

3. <span data-ttu-id="dcd35-272">다음 명령을 실행하여 3단계에서 만든 새 보존 정책(예: **알파인** 하우스 보관함 및 보존 정책)을 기본 사서함 계획에 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="dcd35-272">Run the following command to assign the new retention policy that you created in Step 3 (for example, **Alpine House Archive and Retention Policy**) to the default mailbox plan.</span></span> <span data-ttu-id="dcd35-273">이 예에서는 기본 사서함 계획의 이름이 **ExchangeOnlineEnterprise로 가정합니다.**</span><span class="sxs-lookup"><span data-stu-id="dcd35-273">This example assumes the name of the default mailbox plan is **ExchangeOnlineEnterprise**.</span></span>

    ```powershell
    Set-MailboxPlan "ExchangeOnlineEnterprise" -RetentionPolicy "Alpine House Archive and Retention Policy"
    ```

4. <span data-ttu-id="dcd35-274">2단계의 명령을 다시 실행하여 기본 사서함 계획에 할당된 보존 정책이 변경되어 있는지 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dcd35-274">You can rerun the command in step 2 to verify that the retention policy assigned to the default mailbox plan was changed.</span></span>

## <a name="more-information"></a><span data-ttu-id="dcd35-275">추가 정보</span><span class="sxs-lookup"><span data-stu-id="dcd35-275">More information</span></span>

- <span data-ttu-id="dcd35-276">보존 기간은 어떻게 계산되나요?</span><span class="sxs-lookup"><span data-stu-id="dcd35-276">How is retention age calculated?</span></span> <span data-ttu-id="dcd35-277">사서함 항목의 보존 기간은 전송되지 않지만 사용자가 만든 초안 메시지와 같은 항목에 대한 배달 날짜 또는 생성 날짜를 통해 계산됩니다.</span><span class="sxs-lookup"><span data-stu-id="dcd35-277">The retention age of mailbox items is calculated from the date of delivery or the date of creation for items such as draft messages that aren't sent but are created by the user.</span></span> <span data-ttu-id="dcd35-278">관리되는 폴더 도우미가 사서함의 항목을 처리할 때 보존 태그가 있는 모든 항목의 시작 날짜 및 만료 날짜에 삭제 및 복구 허용 또는 영구 삭제 보존 작업으로 스탬프 처리합니다.</span><span class="sxs-lookup"><span data-stu-id="dcd35-278">When the Managed Folder Assistant processes items in a mailbox, it stamps a start date and an expiration date for all items that have retention tags with the Delete and Allow Recovery or Permanently Delete retention action.</span></span> <span data-ttu-id="dcd35-279">보관 태그가 있는 항목은 이동 날짜로 스탬프가 지정됩니다.</span><span class="sxs-lookup"><span data-stu-id="dcd35-279">Items that have an archive tag are stamped with a move date.</span></span> 

- <span data-ttu-id="dcd35-280">다음 표에서는 이 항목의 단계를 수행하여 만든 사용자 지정 보존 정책에 추가되는 각 보존 태그에 대한 자세한 정보를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="dcd35-280">The following table provides more information about each retention tag that is added to the custom retention policy that was created by following the steps in this topic.</span></span>

    | <span data-ttu-id="dcd35-281">보존 태그</span><span class="sxs-lookup"><span data-stu-id="dcd35-281">Retention tag</span></span> | <span data-ttu-id="dcd35-282">이 태그가 하는 일</span><span class="sxs-lookup"><span data-stu-id="dcd35-282">What this tag does</span></span> | <span data-ttu-id="dcd35-283">기본 제공 여부 또는 사용자 지정 여부</span><span class="sxs-lookup"><span data-stu-id="dcd35-283">Built-in or custom?</span></span> | <span data-ttu-id="dcd35-284">유형</span><span class="sxs-lookup"><span data-stu-id="dcd35-284">Type</span></span> |
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="dcd35-285">알파인 하우스 3년 후 보관함으로 이동</span><span class="sxs-lookup"><span data-stu-id="dcd35-285">Alpine House 3 Year Move to Archive</span></span>  <br/> |<span data-ttu-id="dcd35-286">1095일(3년) 이전의 항목을 보관 사서함으로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="dcd35-286">Moves items that are 1095 days (3 years) old to the archive mailbox.</span></span>  <br/> |<span data-ttu-id="dcd35-287">사용자 [지정(2단계: 보관](#step-2-create-new-retention-tags-for-the-archive-and-deletion-policies)및 삭제 정책에 대한 새 보존 태그 만들기 참조)</span><span class="sxs-lookup"><span data-stu-id="dcd35-287">Custom (See [Step 2: Create new retention tags for the archive and deletion policies](#step-2-create-new-retention-tags-for-the-archive-and-deletion-policies))</span></span>  <br/> |<span data-ttu-id="dcd35-288">기본 정책 태그(보관) 이 태그는 전체 사서함에 자동으로 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="dcd35-288">Default Policy Tag (archive); this tag is automatically applied to the entire mailbox.</span></span>  <br/> |
    |<span data-ttu-id="dcd35-289">알파인 하우스 7년 영구 삭제</span><span class="sxs-lookup"><span data-stu-id="dcd35-289">Alpine House 7 Year Permanently Delete</span></span>  <br/> |<span data-ttu-id="dcd35-290">기본 사서함 또는 보관 사서함의 항목은 7년이 지난 경우 영구적으로 삭제합니다.</span><span class="sxs-lookup"><span data-stu-id="dcd35-290">Permanently deletes items in the primary mailbox or the archive mailbox when they are 7 years old.</span></span>  <br/> |<span data-ttu-id="dcd35-291">사용자 [지정(2단계: 보관](#step-2-create-new-retention-tags-for-the-archive-and-deletion-policies)및 삭제 정책에 대한 새 보존 태그 만들기 참조)</span><span class="sxs-lookup"><span data-stu-id="dcd35-291">Custom (See [Step 2: Create new retention tags for the archive and deletion policies](#step-2-create-new-retention-tags-for-the-archive-and-deletion-policies))</span></span>  <br/> |<span data-ttu-id="dcd35-292">기본 정책 태그(지우기); 이 태그는 전체 사서함에 자동으로 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="dcd35-292">Default Policy Tag (deletion); this tag is automatically applied to the entire mailbox.</span></span>  <br/> |
    |<span data-ttu-id="dcd35-293">알파인 하우스 삭제된 항목 5년 삭제 및 복구 허용</span><span class="sxs-lookup"><span data-stu-id="dcd35-293">Alpine House Deleted Items 5 Years Delete and Allow Recovery</span></span>  <br/> |<span data-ttu-id="dcd35-294">지우기 항목 폴더에서 5년 된 항목을 삭제합니다.</span><span class="sxs-lookup"><span data-stu-id="dcd35-294">Deletes items from the Deleted Items folder that are 5 years old.</span></span> <span data-ttu-id="dcd35-295">사용자는 삭제 후 최대 14일 동안 이러한 항목을 복구할 수 있습니다.<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="dcd35-295">Users can recover these items for up 14 days after they're deleted.<sup>\*</sup></span></span> <br/> |<span data-ttu-id="dcd35-296">사용자 [지정(2단계: 보관](#step-2-create-new-retention-tags-for-the-archive-and-deletion-policies)및 삭제 정책에 대한 새 보존 태그 만들기 참조)</span><span class="sxs-lookup"><span data-stu-id="dcd35-296">Custom (See [Step 2: Create new retention tags for the archive and deletion policies](#step-2-create-new-retention-tags-for-the-archive-and-deletion-policies))</span></span>  <br/> |<span data-ttu-id="dcd35-297">보존 정책 태그(삭제된 항목); 이 태그는 지우기 항목 폴더의 항목에 자동으로 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="dcd35-297">Retention Policy Tag (Deleted Items); this tag is automatically applied to items in the Deleted items folder.</span></span>  <br/> |
    |<span data-ttu-id="dcd35-298">복구 가능한 항목 14일 보관함으로 이동</span><span class="sxs-lookup"><span data-stu-id="dcd35-298">Recoverable Items 14 days Move to Archive</span></span>  <br/> |<span data-ttu-id="dcd35-299">14일 동안 복구 가능한 항목 폴더에 있는 항목을 보관 사서함의 복구 가능한 항목 폴더로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="dcd35-299">Moves items that have been in the Recoverable Items folder for 14 days to the Recoverable Items folder in the archive mailbox.</span></span>  <br/> |<span data-ttu-id="dcd35-300">기본 제공</span><span class="sxs-lookup"><span data-stu-id="dcd35-300">Built-in</span></span>  <br/> |<span data-ttu-id="dcd35-301">보존 정책 태그(복구 가능한 항목) 이 태그는 복구 가능한 항목 폴더의 항목에 자동으로 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="dcd35-301">Retention Policy Tag (Recoverable Items); this tag is automatically applied to items in the Recoverable Items folder.</span></span>  <br/> |
    |<span data-ttu-id="dcd35-302">정크 메일</span><span class="sxs-lookup"><span data-stu-id="dcd35-302">Junk Email</span></span>  <br/> |<span data-ttu-id="dcd35-303">30일 동안 정크 메일 폴더에 있는 항목을 영구적으로 삭제합니다.</span><span class="sxs-lookup"><span data-stu-id="dcd35-303">Permanently deletes items that have been in the Junk Email folder for 30 days.</span></span> <span data-ttu-id="dcd35-304">사용자는 삭제 후 최대 14일 동안 이러한 항목을 복구할 수 있습니다.<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="dcd35-304">Users can recover these items for up 14 days after they're deleted.<sup>\*</sup></span></span> <br/> |<span data-ttu-id="dcd35-305">기본 제공</span><span class="sxs-lookup"><span data-stu-id="dcd35-305">Built-in</span></span>  <br/> |<span data-ttu-id="dcd35-306">보존 정책 태그(정크 메일); 이 태그는 정크 메일 폴더의 항목에 자동으로 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="dcd35-306">Retention Policy Tag (Junk Email); this tag is automatically applied to items in Junk Email folder.</span></span>  <br/> |
    |<span data-ttu-id="dcd35-307">1개월 삭제</span><span class="sxs-lookup"><span data-stu-id="dcd35-307">1 Month Delete</span></span>  <br/> |<span data-ttu-id="dcd35-308">30일이 지난 항목을 영구적으로 삭제합니다.</span><span class="sxs-lookup"><span data-stu-id="dcd35-308">Permanently deletes items that are 30 days old.</span></span> <span data-ttu-id="dcd35-309">사용자는 삭제 후 최대 14일 동안 이러한 항목을 복구할 수 있습니다.<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="dcd35-309">Users can recover these items for up 14 days after they're deleted.<sup>\*</sup></span></span> <br/> |<span data-ttu-id="dcd35-310">기본 제공</span><span class="sxs-lookup"><span data-stu-id="dcd35-310">Built-in</span></span>  <br/> |<span data-ttu-id="dcd35-311">개인; 이 태그는 사용자가 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dcd35-311">Personal; this tag can be applied by users.</span></span>  <br/> |
    |<span data-ttu-id="dcd35-312">1년 삭제</span><span class="sxs-lookup"><span data-stu-id="dcd35-312">1 Year Delete</span></span>  <br/> |<span data-ttu-id="dcd35-313">365일이 지난 항목을 영구적으로 삭제합니다.</span><span class="sxs-lookup"><span data-stu-id="dcd35-313">Permanently deletes items that are 365 days old.</span></span> <span data-ttu-id="dcd35-314">사용자는 삭제 후 최대 14일 동안 이러한 항목을 복구할 수 있습니다.<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="dcd35-314">Users can recover these items for up 14 days after they're deleted.<sup>\*</sup></span></span> <br/> |<span data-ttu-id="dcd35-315">기본 제공</span><span class="sxs-lookup"><span data-stu-id="dcd35-315">Built-in</span></span>  <br/> |<span data-ttu-id="dcd35-316">개인; 이 태그는 사용자가 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dcd35-316">Personal; this tag can be applied by users.</span></span>  <br/> |
    |<span data-ttu-id="dcd35-317">삭제 안</span><span class="sxs-lookup"><span data-stu-id="dcd35-317">Never Delete</span></span>  <br/> |<span data-ttu-id="dcd35-318">이 태그는 보존 정책에 의해 항목이 삭제되지 않도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="dcd35-318">This tag prevents items from being deleted by a retention policy.</span></span>  <br/> |<span data-ttu-id="dcd35-319">기본 제공</span><span class="sxs-lookup"><span data-stu-id="dcd35-319">Built-in</span></span>  <br/> |<span data-ttu-id="dcd35-320">개인; 이 태그는 사용자가 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dcd35-320">Personal; this tag can be applied by users.</span></span>  <br/> |
    |<span data-ttu-id="dcd35-321">개인 1년 후 보관함으로 이동</span><span class="sxs-lookup"><span data-stu-id="dcd35-321">Personal 1 year move to archive</span></span>  <br/> |<span data-ttu-id="dcd35-322">1년 후 항목을 보관 사서함으로 Moves items.</span><span class="sxs-lookup"><span data-stu-id="dcd35-322">Moves items to the archive mailbox after 1 year.</span></span>  <br/> |<span data-ttu-id="dcd35-323">기본 제공</span><span class="sxs-lookup"><span data-stu-id="dcd35-323">Built-in</span></span>  <br/> |<span data-ttu-id="dcd35-324">개인; 이 태그는 사용자가 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dcd35-324">Personal; this tag can be applied by users.</span></span>  <br/> |

    > <span data-ttu-id="dcd35-325"><sup>\*</sup> 사용자는 Outlook 및 웹용 Outlook(이전의 Outlook Web App)에서 지우기 항목 복구 도구를 사용하여 삭제된 항목 보존 기간(Exchange Online에서 기본적으로 14일)의 삭제된 항목을 복구할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dcd35-325"><sup>\*</sup> Users can use the Recover Deleted Items tool in Outlook and Outlook on the web (formerly known as Outlook Web App) to recover a deleted item within the deleted item retention period, which by default is 14 days in Exchange Online.</span></span> <span data-ttu-id="dcd35-326">관리자는 이 Windows PowerShell 사용하여 삭제된 항목 보존 기간을 최대 30일로 늘일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dcd35-326">An administrator can use Windows PowerShell to increase the deleted item retention period to a maximum of 30 days.</span></span> <span data-ttu-id="dcd35-327">자세한 내용은 다음을 참조하십시오. [Windows용 Outlook에서](https://support.office.com/article/49e81f3c-c8f4-4426-a0b9-c0fd751d48ce) 삭제된 항목 복구 및 [Exchange Online의](https://www.microsoft.com/?ref=go) 사서함에 대한 삭제된 항목 보존 기간 변경</span><span class="sxs-lookup"><span data-stu-id="dcd35-327">For more information, see: [Recover deleted items in Outlook for Windows](https://support.office.com/article/49e81f3c-c8f4-4426-a0b9-c0fd751d48ce) and [Change the deleted item retention period for a mailbox in Exchange Online](https://www.microsoft.com/?ref=go)</span></span>
  
- <span data-ttu-id="dcd35-328">복구할 수 있는 항목 **14일 이동** 보존 태그를 사용하면 사용자의 기본 사서함에 있는 복구 가능한 항목 폴더의 저장소 공간을 비우는 데 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="dcd35-328">Using the **Recoverable Items 14 days Move to Archive** retention tag helps free up storage space in the Recoverable Items folder in the user's primary mailbox.</span></span> <span data-ttu-id="dcd35-329">이는 사용자의 사서함이 보류 상태일 때, 즉 사용자의 사서함이 영구적으로 삭제되지 않는 경우 유용합니다.</span><span class="sxs-lookup"><span data-stu-id="dcd35-329">This is useful when a user's mailbox is placed on hold, which means nothing is ever permanently deleted the user's mailbox.</span></span> <span data-ttu-id="dcd35-330">항목을 보관 사서함으로 이동하지 않으면 기본 사서함의 복구 가능한 항목 폴더에 대한 저장소 할당량에 도달할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dcd35-330">Without moving items to the archive mailbox, it's possible the storage quota for the Recoverable Items folder in the primary mailbox will be reached.</span></span> <span data-ttu-id="dcd35-331">이 문제를 방지하는 방법에 대한 자세한 내용은 보류된 사서함에 대한 복구 가능한 항목 할당량 [늘리기 항목을 참조하십시오.](https://go.microsoft.com/fwlink/p/?LinkId=786479)</span><span class="sxs-lookup"><span data-stu-id="dcd35-331">For more information about this and how to avoid it, see [Increase the Recoverable Items quota for mailboxes on hold](https://go.microsoft.com/fwlink/p/?LinkId=786479).</span></span>
