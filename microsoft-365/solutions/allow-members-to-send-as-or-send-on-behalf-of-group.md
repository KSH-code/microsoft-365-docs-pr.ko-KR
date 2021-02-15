---
title: 구성원이 그룹으로 보내거나 그룹을 대신하여 보낼 수 있도록 허용
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
description: 구성원이 Microsoft 365 그룹으로 전자 메일을 보내거나 Microsoft 365 그룹을 대신하여 전자 메일을 보낼 수 있도록 허용하는 방법을 배워야 합니다.
ms.openlocfilehash: 6dff559eceec1b719f31d577d7fff8f604636a47
ms.sourcegitcommit: 47de4402174c263ae8d70c910ca068a7581d04ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/12/2020
ms.locfileid: "49663586"
---
# <a name="allow-members-to-send-as-or-send-on-behalf-of-a-group"></a><span data-ttu-id="ff6c2-103">구성원이 그룹으로 보내거나 그룹을 대신하여 보낼 수 있도록 허용</span><span class="sxs-lookup"><span data-stu-id="ff6c2-103">Allow members to send as or send on behalf of a group</span></span>

<span data-ttu-id="ff6c2-104">다른 사람으로 보내기 또는 대신 보내기  권한이 부여된 Microsoft 365 그룹의 구성원은 그룹으로 또는 그룹을 대신하여 전자 메일을 보낼 수 있습니다. </span><span class="sxs-lookup"><span data-stu-id="ff6c2-104">A member of a Microsoft 365 group who has been granted **Send as** or **Send on behalf** permissions can send email as the group, or on behalf of the group.</span></span> <span data-ttu-id="ff6c2-105">이 문서에서는 전역 또는 Exchange 관리자가 이러한 권한을 설정하는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="ff6c2-105">This article explains how a global or Exchange administrator can set these permissions.</span></span>
  
<span data-ttu-id="ff6c2-106">예를 들어 Megan Bowen이 **교육** Microsoft 365 그룹의  일부이고 그룹에 대한 권한으로 보내기 권한을 가지는 경우 그룹으로  전자 메일을 보내는 경우 교육 그룹이 전자 메일을 보낸 것 같습니다.</span><span class="sxs-lookup"><span data-stu-id="ff6c2-106">For example, if Megan Bowen is part of the **Training** Microsoft 365 group, and has **Send as** permissions on the group, if she sends an email as the group, it will look like the **Training** group sent the email.</span></span> 
  
<span data-ttu-id="ff6c2-107">대신 **보내기** 권한을 사용하면 Microsoft 365 그룹 대신 전자 메일을 보낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ff6c2-107">The **Send on Behalf** permission lets a user send email on behalf of a Microsoft 365 group.</span></span> <span data-ttu-id="ff6c2-108">예를 들어 Alex Wilber가 마케팅 **Microsoft** 365 그룹의 일부로, 대신 보내기 권한을 가지고 그룹으로 전자 메일을 보내는 경우 이 전자 메일은 마케팅을 대신하여 **Alex Wilber가** 보낸 것 같습니다. </span><span class="sxs-lookup"><span data-stu-id="ff6c2-108">For example, if Alex Wilber is a part of the **Marketing** Microsoft 365 group, and has **Send on Behalf** permissions and sends an email as the group, the email looks like it was sent by **Alex Wilber on behalf of Marketing**.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="ff6c2-109">특정 사용자에 대해  **다른** 사람으로 보내기 또는 대신 보내기 구성할 수 있지만 둘 다 구성할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="ff6c2-109">You can configure **Send as** or **Send on behalf** for a given user, but not both.</span></span> <span data-ttu-id="ff6c2-110">두 가지를 모두 구성하는 경우 기본적으로 "다른 사람으로 **보내기"가 사용됩니다.**</span><span class="sxs-lookup"><span data-stu-id="ff6c2-110">If you configure both, it will default to **Send as**.</span></span>

> [!TIP]
> <span data-ttu-id="ff6c2-111">Outlook 및 웹용 Outlook을 사용하여 그룹에서 전자 메일을 보내는 방법에 대한 자세한 내용은 Microsoft 365 그룹 또는 [Microsoft 365](https://support.microsoft.com/office/0f4964af-aec6-484b-a65c-0434df8cdb6b) 그룹 대신 전자 메일 보내기를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="ff6c2-111">See [Send email from or on behalf of a Microsoft 365 group](https://support.microsoft.com/office/0f4964af-aec6-484b-a65c-0434df8cdb6b) to learn how to use Outlook and Outlook on the Web to send email from a group.</span></span>
    
## <a name="allow-members-to-send-email-as-a-group"></a><span data-ttu-id="ff6c2-112">구성원이 그룹으로 전자 메일을 보낼 수 있도록 허용</span><span class="sxs-lookup"><span data-stu-id="ff6c2-112">Allow members to send email as a group</span></span>

<span data-ttu-id="ff6c2-113">이 섹션에서는 사용자가 [Exchange](https://go.microsoft.com/fwlink/p/?linkid=2059104) Online의 EAC(Exchange 관리 센터)에서 그룹으로 전자 메일을 보낼 수 있도록 허용하는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="ff6c2-113">This section explains how to allow users to send email as a group in the [Exchange admin center](https://go.microsoft.com/fwlink/p/?linkid=2059104) (EAC) in Exchange Online.</span></span>
  
1. <span data-ttu-id="ff6c2-114">Exchange 관리 <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">센터에서</a>받는 사람 **그룹으로** \> **이동 합니다.**</span><span class="sxs-lookup"><span data-stu-id="ff6c2-114">In the <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">Exchange admin center</a>, go to **Recipients** \> **Groups**.</span></span>
    
2. <span data-ttu-id="ff6c2-115">사용자가 **다른 사람으로** 보낼 수 있도록 허용할 그룹 편집 ![ ](../media/0cfcb590-dc51-4b4f-9276-bb2ce300d87e.png) 아이콘을 선택합니다.  </span><span class="sxs-lookup"><span data-stu-id="ff6c2-115">Select **Edit**  ![Edit group icon](../media/0cfcb590-dc51-4b4f-9276-bb2ce300d87e.png) on the group that you want to allow users to send as.</span></span> 
    
3. <span data-ttu-id="ff6c2-116">그룹 **위임 선택.**</span><span class="sxs-lookup"><span data-stu-id="ff6c2-116">Select **group delegation**.</span></span>
    
4. <span data-ttu-id="ff6c2-117">다른 **사람으로** 보내기 섹션에서 그룹으로 보낼 사용자를 **+** 추가하는 기호를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="ff6c2-117">In the **Send As** section, select the **+** sign to add the users that you want to send as the Group.</span></span> 
    
    ![다른 사람으로 보내기 대화 상자 스크린샷](../media/1df167f6-1eff-4f98-9ecd-4230fab46557.png)
  
5. <span data-ttu-id="ff6c2-119">목록에서 사용자를 검색하거나 선택하기 위해 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="ff6c2-119">Type to search or pick a user from the list.</span></span> <span data-ttu-id="ff6c2-120">확인을 **선택하고** **저장합니다.**</span><span class="sxs-lookup"><span data-stu-id="ff6c2-120">Select **OK** and **Save**.</span></span>
    
    ![목록에서 사용자를 검색하거나 선택할 입력](../media/522919cf-664c-4a25-8076-c51c8c9fbe43.png)
  
## <a name="allow-members-to-send-email-on-behalf-of-a-group"></a><span data-ttu-id="ff6c2-122">구성원이 그룹을 대신하여 전자 메일을 보낼 수 있도록 허용</span><span class="sxs-lookup"><span data-stu-id="ff6c2-122">Allow members to send email on behalf of a group</span></span>

<span data-ttu-id="ff6c2-123">이 섹션에서는 사용자가 Exchange Online의 EAC(Exchange 관리 센터)에서 그룹을 대신하여 전자 메일을 보낼 수 있도록 허용하는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="ff6c2-123">This section explains how to allow users to send email on behalf of a group in the Exchange admin center (EAC) in Exchange Online.</span></span>
  
1. <span data-ttu-id="ff6c2-124">Exchange 관리 <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">센터에서</a>받는 사람 **그룹으로** \> **이동 합니다.**</span><span class="sxs-lookup"><span data-stu-id="ff6c2-124">In the <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">Exchange admin center</a>, go to **Recipients** \> **Groups**.</span></span>
    
2. <span data-ttu-id="ff6c2-125">사용자가 **다른 사람으로** 보낼 수 있도록 허용할 그룹 편집 ![ ](../media/0cfcb590-dc51-4b4f-9276-bb2ce300d87e.png) 아이콘을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="ff6c2-125">Select **Edit** ![Edit group icon](../media/0cfcb590-dc51-4b4f-9276-bb2ce300d87e.png) on the group that you want to allow users to send as.</span></span> 
    
3. <span data-ttu-id="ff6c2-126">그룹 **위임 선택.**</span><span class="sxs-lookup"><span data-stu-id="ff6c2-126">Select **group delegation**.</span></span>
    
4. <span data-ttu-id="ff6c2-127">대신 보내기 섹션에서 그룹으로 보낼 사용자를 추가할 기호를 **+** 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="ff6c2-127">In the Send on Behalf section, select the **+** sign to add the users that you want to send as the Group.</span></span> 
    
    ![대화 상자 대신 보내기 스크린샷](../media/2bae0579-8907-4d6b-8920-ddd6555897b4.png)
  
5. <span data-ttu-id="ff6c2-129">목록에서 사용자를 검색하거나 선택하기 위해 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="ff6c2-129">Type to search or pick a user from the list.</span></span> <span data-ttu-id="ff6c2-130">확인을 **선택하고** **저장합니다.**</span><span class="sxs-lookup"><span data-stu-id="ff6c2-130">Select **OK** and **Save**.</span></span>
    
    ![목록에서 사용자를 검색하거나 선택할 입력](../media/522919cf-664c-4a25-8076-c51c8c9fbe43.png)

## <a name="related-articles"></a><span data-ttu-id="ff6c2-132">관련 문서</span><span class="sxs-lookup"><span data-stu-id="ff6c2-132">Related articles</span></span>

[<span data-ttu-id="ff6c2-133">공동 작업 거버넌스 계획 단계별</span><span class="sxs-lookup"><span data-stu-id="ff6c2-133">Collaboration governance planning step-by-step</span></span>](collaboration-governance-overview.md#collaboration-governance-planning-step-by-step)

[<span data-ttu-id="ff6c2-134">공동 작업 거버넌스 계획 만들기</span><span class="sxs-lookup"><span data-stu-id="ff6c2-134">Create your collaboration governance plan</span></span>](collaboration-governance-first.md)

[<span data-ttu-id="ff6c2-135">Microsoft 365 그룹에 대한 자세한 내용은</span><span class="sxs-lookup"><span data-stu-id="ff6c2-135">Learn more about Microsoft 365 groups</span></span>](https://support.microsoft.com/office/b565caa1-5c40-40ef-9915-60fdb2d97fa2)

[<span data-ttu-id="ff6c2-136">Add-RecipientPermission</span><span class="sxs-lookup"><span data-stu-id="ff6c2-136">Add-RecipientPermission</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=723960)

[<span data-ttu-id="ff6c2-137">Set-UnifiedGroup</span><span class="sxs-lookup"><span data-stu-id="ff6c2-137">Set-UnifiedGroup</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=616189)
