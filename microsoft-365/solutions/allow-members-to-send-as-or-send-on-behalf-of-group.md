---
title: 구성원이 그룹으로 보내거나 그룹을 대신하여 보내기 허용
ms.reviewer: arvaradh
f1.keywords: NOCSH
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: Admin
ms.topic: get-started-article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- m365solution-collabgovernance
search.appverid:
- MET150
ms.assetid: 0ad41414-0cc6-4b97-90fb-06bec7bcf590
description: 그룹 구성원이 Microsoft 365 그룹으로 전자 메일을 보내거나 Microsoft 365 그룹을 대신하여 전자 메일을 보낼 수 있도록 허용하는 방법을 학습합니다.
ms.openlocfilehash: 44a0a7a690c8faa9fe00732e8154f36aa5a6fe6f
ms.sourcegitcommit: 3d48e198e706f22ac903b346cadda06b2368dd1e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/11/2021
ms.locfileid: "50727082"
---
# <a name="allow-members-to-send-as-or-send-on-behalf-of-a-group"></a><span data-ttu-id="200be-103">구성원이 그룹으로 보내거나 그룹을 대신하여 보내기 허용</span><span class="sxs-lookup"><span data-stu-id="200be-103">Allow members to send as or send on behalf of a group</span></span>

<span data-ttu-id="200be-104">다른 사람으로 보내기 또는 대신 보내기  권한이 부여된 Microsoft 365 그룹의 구성원은 그룹으로 또는 그룹을 대신하여 전자 메일을 보낼 수 있습니다. </span><span class="sxs-lookup"><span data-stu-id="200be-104">A member of a Microsoft 365 group who has been granted **Send as** or **Send on behalf** permissions can send email as the group, or on behalf of the group.</span></span> <span data-ttu-id="200be-105">그룹의 게스트에게 이러한 사용 권한을 부여할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="200be-105">(Guests in the group cannot be granted these permissions.)</span></span>

<span data-ttu-id="200be-106">이 문서에서는 전역 또는 Exchange 관리자가 이러한 사용 권한을 설정하는 방법에 대해 설명하고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="200be-106">This article explains how a global or Exchange administrator can set these permissions.</span></span>
  
<span data-ttu-id="200be-107">예를 들어 Megan Bowen이 **교육** Microsoft 365 그룹의  일부이고 그룹에 대한 다른 사람으로 보내기 권한이 있는 경우 그룹으로  전자 메일을 보내는 경우 교육 그룹이 전자 메일을 보낸 것 같습니다.</span><span class="sxs-lookup"><span data-stu-id="200be-107">For example, if Megan Bowen is part of the **Training** Microsoft 365 group, and has **Send as** permissions on the group, if she sends an email as the group, it will look like the **Training** group sent the email.</span></span> 
  
<span data-ttu-id="200be-108">대신 **보내기 권한을** 사용하면 사용자가 Microsoft 365 그룹을 대신하여 전자 메일을 보낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="200be-108">The **Send on Behalf** permission lets a user send email on behalf of a Microsoft 365 group.</span></span> <span data-ttu-id="200be-109">예를 들어 Alex Wilber가 **마케팅** Microsoft 365 그룹의 일부인 경우 대신 보내기 권한이 있으며 그룹으로 전자 메일을 보내는 경우 전자 메일은 **Alex Wilber가 마케팅을** 대신하여 보낸 것 같습니다. </span><span class="sxs-lookup"><span data-stu-id="200be-109">For example, if Alex Wilber is a part of the **Marketing** Microsoft 365 group, and has **Send on Behalf** permissions and sends an email as the group, the email looks like it was sent by **Alex Wilber on behalf of Marketing**.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="200be-110">특정 **사용자에 대해 다른 사람으로** 보내기 또는 대신 보내기 를 구성할 수 있지만 둘 다 구성할 수 없습니다. </span><span class="sxs-lookup"><span data-stu-id="200be-110">You can configure **Send as** or **Send on behalf** for a given user, but not both.</span></span> <span data-ttu-id="200be-111">둘 다 구성하는 경우 기본적으로 다른 사람으로 **보내기 으로 설정됩니다.**</span><span class="sxs-lookup"><span data-stu-id="200be-111">If you configure both, it will default to **Send as**.</span></span>

> [!TIP]
> <span data-ttu-id="200be-112">Outlook 및 웹용 Outlook을 사용하여 그룹에서 전자 메일을 보내는 방법에 대한 자세한 내용은 [Microsoft 365](https://support.microsoft.com/office/0f4964af-aec6-484b-a65c-0434df8cdb6b) 그룹에서 전자 메일 보내기 또는 대신 보내기를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="200be-112">See [Send email from or on behalf of a Microsoft 365 group](https://support.microsoft.com/office/0f4964af-aec6-484b-a65c-0434df8cdb6b) to learn how to use Outlook and Outlook on the Web to send email from a group.</span></span>
    
## <a name="allow-members-to-send-email-as-a-group"></a><span data-ttu-id="200be-113">구성원이 전자 메일을 그룹으로 보낼 수 있도록 허용</span><span class="sxs-lookup"><span data-stu-id="200be-113">Allow members to send email as a group</span></span>

<span data-ttu-id="200be-114">이 섹션에서는 사용자가 [Exchange](https://go.microsoft.com/fwlink/p/?linkid=2059104) Online의 EAC(Exchange 관리 센터)에서 그룹으로 전자 메일을 보낼 수 있도록 허용하는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="200be-114">This section explains how to allow users to send email as a group in the [Exchange admin center](https://go.microsoft.com/fwlink/p/?linkid=2059104) (EAC) in Exchange Online.</span></span>
  
1. <span data-ttu-id="200be-115">Exchange <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">관리 센터에서</a>받는 사람 **그룹으로** \> **이동하세요.**</span><span class="sxs-lookup"><span data-stu-id="200be-115">In the <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">Exchange admin center</a>, go to **Recipients** \> **Groups**.</span></span>
    
2. <span data-ttu-id="200be-116">사용자가 **다른 사람으로** 보낼 수 있도록 허용할 그룹에서 그룹 편집 아이콘 ![ ](../media/0cfcb590-dc51-4b4f-9276-bb2ce300d87e.png) 편집을 선택합니다.  </span><span class="sxs-lookup"><span data-stu-id="200be-116">Select **Edit**  ![Edit group icon](../media/0cfcb590-dc51-4b4f-9276-bb2ce300d87e.png) on the group that you want to allow users to send as.</span></span> 
    
3. <span data-ttu-id="200be-117">그룹 **위임 을 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="200be-117">Select **group delegation**.</span></span>
    
4. <span data-ttu-id="200be-118">다른 **사람으로 보내기 섹션에서** 그룹으로 보낼 사용자를 추가하려면 **+** 기호를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="200be-118">In the **Send As** section, select the **+** sign to add the users that you want to send as the Group.</span></span> 
    
    ![다른 사람으로 보내기 대화 상자 스크린샷](../media/1df167f6-1eff-4f98-9ecd-4230fab46557.png)
  
5. <span data-ttu-id="200be-120">목록에서 사용자를 검색하거나 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="200be-120">Type to search or pick a user from the list.</span></span> <span data-ttu-id="200be-121">확인 **및** **저장을 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="200be-121">Select **OK** and **Save**.</span></span>
    
    ![목록에서 사용자를 검색하거나 선택하기 위해 입력](../media/522919cf-664c-4a25-8076-c51c8c9fbe43.png)
  
## <a name="allow-members-to-send-email-on-behalf-of-a-group"></a><span data-ttu-id="200be-123">구성원이 그룹을 대신하여 전자 메일을 보낼 수 있도록 허용</span><span class="sxs-lookup"><span data-stu-id="200be-123">Allow members to send email on behalf of a group</span></span>

<span data-ttu-id="200be-124">이 섹션에서는 사용자가 Exchange Online의 EAC(Exchange 관리 센터)에서 그룹을 대신하여 전자 메일을 보낼 수 있도록 허용하는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="200be-124">This section explains how to allow users to send email on behalf of a group in the Exchange admin center (EAC) in Exchange Online.</span></span>
  
1. <span data-ttu-id="200be-125">Exchange <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">관리 센터에서</a>받는 사람 **그룹으로** \> **이동하세요.**</span><span class="sxs-lookup"><span data-stu-id="200be-125">In the <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">Exchange admin center</a>, go to **Recipients** \> **Groups**.</span></span>
    
2. <span data-ttu-id="200be-126">사용자가 **다른 사람으로** 보낼 수 있도록 허용할 그룹에서 그룹 편집 아이콘 ![ ](../media/0cfcb590-dc51-4b4f-9276-bb2ce300d87e.png) 편집을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="200be-126">Select **Edit** ![Edit group icon](../media/0cfcb590-dc51-4b4f-9276-bb2ce300d87e.png) on the group that you want to allow users to send as.</span></span> 
    
3. <span data-ttu-id="200be-127">그룹 **위임 을 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="200be-127">Select **group delegation**.</span></span>
    
4. <span data-ttu-id="200be-128">대신 보내기 섹션에서 그룹으로 보낼 사용자를 추가하려면 **+** 기호를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="200be-128">In the Send on Behalf section, select the **+** sign to add the users that you want to send as the Group.</span></span> 
    
    ![대화 상자 대신 보내기 스크린샷](../media/2bae0579-8907-4d6b-8920-ddd6555897b4.png)
  
5. <span data-ttu-id="200be-130">목록에서 사용자를 검색하거나 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="200be-130">Type to search or pick a user from the list.</span></span> <span data-ttu-id="200be-131">확인 **및** **저장을 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="200be-131">Select **OK** and **Save**.</span></span>
    
    ![목록에서 사용자를 검색하거나 선택하기 위해 입력](../media/522919cf-664c-4a25-8076-c51c8c9fbe43.png)

## <a name="related-articles"></a><span data-ttu-id="200be-133">관련 문서</span><span class="sxs-lookup"><span data-stu-id="200be-133">Related articles</span></span>

[<span data-ttu-id="200be-134">공동 작업 거버넌스 계획 단계별</span><span class="sxs-lookup"><span data-stu-id="200be-134">Collaboration governance planning step-by-step</span></span>](collaboration-governance-overview.md#collaboration-governance-planning-step-by-step)

[<span data-ttu-id="200be-135">공동 작업 거버넌스 계획 만들기</span><span class="sxs-lookup"><span data-stu-id="200be-135">Create your collaboration governance plan</span></span>](collaboration-governance-first.md)

[<span data-ttu-id="200be-136">Microsoft 365 그룹에 대해 자세히 알아보시다</span><span class="sxs-lookup"><span data-stu-id="200be-136">Learn more about Microsoft 365 groups</span></span>](https://support.microsoft.com/office/b565caa1-5c40-40ef-9915-60fdb2d97fa2)

[<span data-ttu-id="200be-137">Add-RecipientPermission</span><span class="sxs-lookup"><span data-stu-id="200be-137">Add-RecipientPermission</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=723960)

[<span data-ttu-id="200be-138">Set-UnifiedGroup</span><span class="sxs-lookup"><span data-stu-id="200be-138">Set-UnifiedGroup</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=616189)
