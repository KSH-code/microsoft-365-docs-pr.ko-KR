---
title: 소송 보존 만들기
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid: MET150
ms.assetid: 39db1659-0b12-4243-a21c-2614512dcb44
description: 조사 중에 모든 사서함 콘텐츠를 보존하여 사서함을 소송 보존으로 설정하는 방법을 학습합니다.
ms.custom:
- seo-marvel-mar2020
- seo-marvel-apr2020
ms.openlocfilehash: 81d3bf7bba0aadbcd2d52b5f7707caeea96e26c1
ms.sourcegitcommit: 07dea2aa98daf0c4086f8590375167830027c802
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/13/2021
ms.locfileid: "51750062"
---
# <a name="create-a-litigation-hold"></a><span data-ttu-id="86202-103">소송 보존 만들기</span><span class="sxs-lookup"><span data-stu-id="86202-103">Create a Litigation Hold</span></span>

<span data-ttu-id="86202-104">사서함을 소송 보존에 두어 삭제된 항목 및 수정된 항목의 원래 버전을 포함하여 모든 사서함 콘텐츠를 보존할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="86202-104">You can place a mailbox on Litigation Hold to retain all mailbox content, including deleted items and the original versions of modified items.</span></span> <span data-ttu-id="86202-105">사용자 사서함을 소송 보존으로 설정하면 사용자의 보관 사서함(사용하도록 설정된 경우)의 콘텐츠도 보존됩니다.</span><span class="sxs-lookup"><span data-stu-id="86202-105">When you place a user mailbox on Litigation Hold, content in the user's archive mailbox (if it's enabled) is also retained.</span></span> <span data-ttu-id="86202-106">보류를 만들 때 삭제 및 수정된 항목이 지정된 기간 동안 보존된 다음 사서함에서 영구적으로 삭제될 수 있도록 보류 기간(시간 기반 보류라고도함)을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="86202-106">When you create a hold, you can specify a hold duration (also called a *time-based hold*) so that deleted and modified items are retained for a specified period and then permanently deleted from the mailbox.</span></span> <span data-ttu-id="86202-107">또는 콘텐츠를 무기한 보존(무한 보존)하거나 소송 보존이 제거될 때까지 보존할 수 있습니다. </span><span class="sxs-lookup"><span data-stu-id="86202-107">Or you can just retain content indefinitely (called an *infinite hold*) or until the Litigation Hold is removed.</span></span> <span data-ttu-id="86202-108">보류 기간을 지정하면 메시지를 받거나 사서함 항목이 만들어진 날짜부터 계산됩니다.</span><span class="sxs-lookup"><span data-stu-id="86202-108">If you do specify a hold duration period, it's calculated from the date a message is received or a mailbox item is created.</span></span> 
  
<span data-ttu-id="86202-109">소송 보류를 만들면 다음과 같은 상황이 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="86202-109">Here's what happens when you create a Litigation Hold.</span></span>
  
- <span data-ttu-id="86202-110">사용자가 영구적으로 삭제한 항목은 보존 기간 동안 사용자 사서함의 복구 가능한 항목 폴더에 보존됩니다.</span><span class="sxs-lookup"><span data-stu-id="86202-110">Items that are permanently deleted by the user are retained in the Recoverable Items folder in the user's mailbox for the duration of the hold.</span></span>

- <span data-ttu-id="86202-111">사용자가 복구할 수 있는 항목 폴더에서 제거한 항목은 보존 기간 동안 보존됩니다.</span><span class="sxs-lookup"><span data-stu-id="86202-111">Items that are purged from the Recoverable Items folder by the user are retained for the duration of the hold.</span></span>

- <span data-ttu-id="86202-112">복구 가능한 항목 폴더의 저장소 할당량은 30GB에서 110GB로 증가합니다.</span><span class="sxs-lookup"><span data-stu-id="86202-112">The storage quota for the Recoverable Items folder is increased from 30 GB to 110 GB.</span></span>

- <span data-ttu-id="86202-113">사용자의 기본 및 보관 사서함의 항목은 보존됩니다.</span><span class="sxs-lookup"><span data-stu-id="86202-113">Items in the user's primary and the archive mailboxes are retained</span></span>

## <a name="assign-an-exchange-online-plan-2-license"></a><span data-ttu-id="86202-114">계획 Exchange Online 라이선스 할당</span><span class="sxs-lookup"><span data-stu-id="86202-114">Assign an Exchange Online Plan 2 license</span></span>

<span data-ttu-id="86202-115">사서함에 Exchange Online 사서함을 소송 유지로 설정하려면 계획 2에 Exchange Online 할당해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="86202-115">To place an Exchange Online mailbox on Litigation Hold, it must be assigned an Exchange Online Plan 2 license.</span></span> <span data-ttu-id="86202-116">사서함에 Exchange Online 계획 1 라이선스가 할당된 경우 사서함을 보류하기 위해 별도의 Exchange Online Archiving 라이선스를 할당해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="86202-116">If a mailbox is assigned an Exchange Online Plan 1 license, you would have to assign it a separate Exchange Online Archiving license to place it on hold.</span></span>

> [!NOTE]
> <span data-ttu-id="86202-117">Office 365 Education 조직의 경우 추가 기능이 있는 Exchange Online 계획 1 라이선스가 포함된 Office 365 A1 구독에서 소송 보류가 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="86202-117">For Office 365 Education organizations, Litigation Hold is supported in Office 365 A1 subscriptions, which include an Exchange Online Plan 1 license with supplemental features.</span></span> <span data-ttu-id="86202-118">자세한 내용은 Exchange Online 서비스 설명의 "Exchange Online 기능" [섹션을 Office 365 Education 참조하세요.](/office365/servicedescriptions/office-365-platform-service-description/office-365-education#exchange-online-features)</span><span class="sxs-lookup"><span data-stu-id="86202-118">For more information, see the "Exchange Online features" section in the [Office 365 Education service description](/office365/servicedescriptions/office-365-platform-service-description/office-365-education#exchange-online-features).</span></span>

## <a name="place-a-mailbox-on-litigation-hold"></a><span data-ttu-id="86202-119">사서함을 소송 자료 보존으로 설정</span><span class="sxs-lookup"><span data-stu-id="86202-119">Place a mailbox on Litigation Hold</span></span>

<span data-ttu-id="86202-120">다음은 사서함 관리 센터를 사용하여 사서함을 소송 Exchange 단계입니다.</span><span class="sxs-lookup"><span data-stu-id="86202-120">Here are the steps to place a mailbox on Litigation Hold using the Exchange admin center.</span></span>

1. <span data-ttu-id="86202-121">으로 [https://outlook.office.com/ecp](https://outlook.office.com/ecp) 이동한 후 전역 관리자 계정을 사용하여 로그인합니다.</span><span class="sxs-lookup"><span data-stu-id="86202-121">Go to [https://outlook.office.com/ecp](https://outlook.office.com/ecp) and sign in using your global administrator account.</span></span>

2. <span data-ttu-id="86202-122">왼쪽 **탐색 > 사서함에** 있는 받는 사람을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="86202-122">Click **Recipients > Mailboxes** in the left navigation pane.</span></span>

3. <span data-ttu-id="86202-123">소송 보류에 추가하려는 사서함을 선택한 다음 편집 을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="86202-123">Select the mailbox that you want to place on Litigation Hold, and then click **Edit**.</span></span>

4. <span data-ttu-id="86202-124">사서함 속성 페이지에서 사서함 **기능을 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="86202-124">On the mailbox properties page, click **Mailbox features**.</span></span>
    
5. <span data-ttu-id="86202-125">소송 **보류: 사용** 안 함에서 사용 을 클릭하여 사서함을 소송 보류로 설정합니다. </span><span class="sxs-lookup"><span data-stu-id="86202-125">Under **Litigation hold: Disabled**, click **Enable** to place the mailbox on Litigation Hold.</span></span>
    
6. <span data-ttu-id="86202-126">소송 보류 페이지에서 **다음** 선택적 정보를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="86202-126">On the **Litigation hold** page, enter the following optional information:</span></span> 
    
    - <span data-ttu-id="86202-127">소송 보유 **기간(일)** - 이 상자를 사용하여 시간 기반 보류를 만들고 사서함이 소송 보류 중일 때 사서함 항목이 유지되는 기간을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="86202-127">**Litigation hold duration (days)** - Use this box to create a time-based hold and specify how long mailbox items are held when the mailbox is placed on Litigation Hold.</span></span> <span data-ttu-id="86202-128">기간은 사서함 항목이 수신되거나 만들어진 날짜부터 계산됩니다.</span><span class="sxs-lookup"><span data-stu-id="86202-128">The duration is calculated from the date a mailbox item is received or created.</span></span> <span data-ttu-id="86202-129">특정 항목에 대한 보존 기간이 만료되면 해당 항목이 더 이상 보존되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="86202-129">When the hold duration expires for a specific item, that item will no longer be preserved.</span></span> <span data-ttu-id="86202-130">이 상자를 비워 두면 항목은 무기한으로 또는 보류가 제거될 때까지 보존됩니다.</span><span class="sxs-lookup"><span data-stu-id="86202-130">If you leave this box blank, items are preserved indefinitely or until the hold is removed.</span></span> <span data-ttu-id="86202-131">기간을 지정하는 데 날짜를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="86202-131">Use days to specify the duration.</span></span>
    
    - <span data-ttu-id="86202-132">**참고** - 이 상자를 사용하여 사서함이 소송 보류 중임에 대해 사용자에게 알릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="86202-132">**Note** - Use this box to inform the user their mailbox is on Litigation Hold.</span></span> <span data-ttu-id="86202-133">이 메모는 2010 이상을 사용하는 경우 사용자 사서함의 계정 정보 페이지에 Outlook 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="86202-133">The note will appear on the Account Information page in the user's mailbox if they're using Outlook 2010 or later.</span></span> <span data-ttu-id="86202-134">이 페이지에 액세스하려면 사용자가 이 페이지에서 **파일을** 클릭할 수 Outlook.</span><span class="sxs-lookup"><span data-stu-id="86202-134">To access this page, users can click **File** in Outlook.</span></span>
    
    - <span data-ttu-id="86202-135">**URL** - 이 상자를 사용하여 사용자에게 소송 보류에 대한 자세한 정보를 웹 사이트로 안내합니다.</span><span class="sxs-lookup"><span data-stu-id="86202-135">**URL** - Use this box to direct the user to a website for more information about Litigation Hold.</span></span> <span data-ttu-id="86202-136">이 URL은 2010 이상을 사용하는 경우 사용자 사서함의 계정 정보 페이지에 Outlook 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="86202-136">This URL appears on the Account Information page in the user's mailbox if they are using Outlook 2010 or later.</span></span> <span data-ttu-id="86202-137">이 페이지에 액세스하려면 에서 **파일을** 클릭할 수 Outlook.</span><span class="sxs-lookup"><span data-stu-id="86202-137">To access this page, users can click **File** in Outlook..</span></span>

7. <span data-ttu-id="86202-138">소송 **보류** 페이지에서 저장을 클릭한 다음 사서함 **속성** 페이지에서 저장을 클릭합니다. </span><span class="sxs-lookup"><span data-stu-id="86202-138">Click **Save** on the **Litigation hold** page, and then click **Save** on the mailbox properties page.</span></span>

### <a name="create-a-litigation-hold-using-powershell"></a><span data-ttu-id="86202-139">PowerShell을 사용하여 소송 보류 만들기</span><span class="sxs-lookup"><span data-stu-id="86202-139">Create a Litigation Hold using PowerShell</span></span>

<span data-ttu-id="86202-140">PowerShell에서 다음 명령을 실행하여 소송 Exchange Online [수 있습니다.](/powershell/exchange/connect-to-exchange-online-powershell)</span><span class="sxs-lookup"><span data-stu-id="86202-140">You can also create a Litigation Hold by running the following command in [Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell):</span></span>

```powershell
Set-Mailbox <username> -LitigationHoldEnabled $true
```

<span data-ttu-id="86202-141">이전 명령은 보존 기간이 지정되지 않은 항목을 무기한 보존합니다.</span><span class="sxs-lookup"><span data-stu-id="86202-141">The previous command preserves items indefinitely because the hold duration isn't specified.</span></span> <span data-ttu-id="86202-142">시간 기반 보류를 만들기 위해 다음 명령을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="86202-142">To create a time-based hold, using the following command:</span></span>

```powershell
Set-Mailbox <username> -LitigationHoldEnabled $true -LitigationHoldDuration <number of days>
```

<span data-ttu-id="86202-143">자세한 내용은 [설정-사서함](/powershell/module/exchange/set-mailbox)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="86202-143">For more information, see [Set-Mailbox](/powershell/module/exchange/set-mailbox).</span></span>

## <a name="how-does-litigation-hold-work"></a><span data-ttu-id="86202-144">소송 보유는 어떻게 작동하나요?</span><span class="sxs-lookup"><span data-stu-id="86202-144">How does Litigation Hold work?</span></span>

<span data-ttu-id="86202-145">일반 삭제된 항목 워크플로에서는 사용자가 항목을 영구적으로 삭제(Shift + Delete)하거나 지우기 항목 폴더에서 삭제하면 사서함 항목이 복구 가능한 항목 폴더의 삭제 하위 폴더로 이동됩니다.</span><span class="sxs-lookup"><span data-stu-id="86202-145">In the normal deleted item workflow, a mailbox item is moved to the Deletions subfolder in the Recoverable Items folder when a user permanently deletes it (Shift + Delete) or deletes it from the Deleted Items folder.</span></span> <span data-ttu-id="86202-146">삭제 정책(보존 삭제 작업으로 구성된 보존 태그)도 보존 기간이 만료되면 항목을 삭제 하위폴더로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="86202-146">A deletion policy (which is a retention tag configured with a Delete retention action) also moves items to the Deletions subfolder when the retention period expires.</span></span> <span data-ttu-id="86202-147">사용자가 복구 가능한 항목 폴더의 항목을 제거하거나 항목에 대한 삭제된 항목 보존 기간이 만료되면 복구할 수 있는 항목 폴더의 제거 하위 폴더로 이동되고 영구 삭제로 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="86202-147">When a user purges an item in the Recoverable Items folder or when the deleted item retention period expires for an item, it's moved to the Purges subfolder in the Recoverable Items folder and marked for permanent deletion.</span></span> <span data-ttu-id="86202-148">다음에 MFA(관리되는 폴더 Exchange 도우미)에서 사서함이 처리될 때 제거됩니다.</span><span class="sxs-lookup"><span data-stu-id="86202-148">It will be purged from Exchange the next time the mailbox is processed by the Managed Folder Assistant (MFA).</span></span>

<span data-ttu-id="86202-149">사서함에 소송 보존이 설정되어 있는 경우 제거 하위폴더의 항목은 소송 보존에 지정된 보존 기간 동안 보존됩니다.</span><span class="sxs-lookup"><span data-stu-id="86202-149">When a mailbox is placed on Litigation Hold, items in the Purges subfolder are preserved for the hold duration specified by the Litigation Hold.</span></span> <span data-ttu-id="86202-150">보류 기간은 항목을 받거나 만든 원래 날짜부터 계산하며 제거 하위폴더의 항목을 보유하는 기간을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="86202-150">The hold duration is calculated from the original date an item was received or created, and defines how long items in the Purges subfolder are held.</span></span> <span data-ttu-id="86202-151">제거 하위폴더의 항목에 대한 보류 기간이 만료되면 항목이 영구적으로 삭제된 것으로 표시되고 다음에 MFA에서 Exchange 사서함이 제거됩니다.</span><span class="sxs-lookup"><span data-stu-id="86202-151">When the hold duration expires for an item in the Purges subfolder, the item is marked for permanent deletion and will be purged from Exchange the next time the mailbox is processed by the MFA.</span></span> <span data-ttu-id="86202-152">사서함에 무기한 보류가 설정되는 경우 항목은 제거 하위폴더에서 제거되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="86202-152">If an indefinite hold is placed on a mailbox, items will never be purged from the Purges subfolder.</span></span>

<span data-ttu-id="86202-153">다음 그림에서는 복구 가능한 항목 폴더 및 보류 워크플로 프로세스의 하위 폴더를 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="86202-153">The following illustration shows the subfolders in the Recoverable Items folders and the hold workflow process.</span></span>

![소송 보유 수명 주기](../media/LitigationHoldLifeCycle.png)

> [!NOTE]
> <span data-ttu-id="86202-155">eDiscovery 사례와 연결된 보류가 사서함에 배치된 경우 제거된 항목은 Deletions 하위폴더에서 DiscoveryHolds 하위폴더로 이동되고 eDiscovery 보류에서 사서함이 릴리스될 때까지 보존됩니다.</span><span class="sxs-lookup"><span data-stu-id="86202-155">If a hold associated with an eDiscovery case is placed on a mailbox, purged items are moved from the Deletions subfolder to the DiscoveryHolds subfolder and are preserved until the mailbox is released from the eDiscovery hold.</span></span>
