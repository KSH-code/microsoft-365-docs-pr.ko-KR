---
title: 구성원이 그룹을 대신 하거나 다른 사람 이름으로 보내기 허용
ms.reviewer: arvaradh
f1.keywords: NOCSH
ms.author: mikeplum
author: MikePlumleyMSFT
manager: pamgreen
audience: Admin
ms.topic: get-started-article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 0ad41414-0cc6-4b97-90fb-06bec7bcf590
description: 구성원이 microsoft 365 그룹으로 전자 메일을 보내거나 Microsoft 365 그룹을 대신 하 여 전자 메일을 보낼 수 있도록 하는 방법을 알아봅니다.
ms.openlocfilehash: ce4527321468ee01864177fc1a607fab6a474481
ms.sourcegitcommit: 5476c2578400894640ae74bfe8e93c3319f685bd
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/06/2020
ms.locfileid: "44049390"
---
# <a name="allow-members-to-send-as-or-send-on-behalf-of-a-group"></a><span data-ttu-id="3b489-103">구성원이 그룹을 대신 하거나 다른 사람 이름으로 보내기 허용</span><span class="sxs-lookup"><span data-stu-id="3b489-103">Allow members to send as or send on behalf of a Group</span></span>

<span data-ttu-id="3b489-104">**다른 사람 이름으로 보내기** 또는 **대신 보내기** 권한을 부여 받은 Microsoft 365 그룹의 구성원은 그룹으로 또는 그룹을 대신 하 여 전자 메일을 보낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3b489-104">A member of a Microsoft 365 group who has been granted **Send as** or **Send on behalf** permissions can send email as the group, or on behalf of the group.</span></span> <span data-ttu-id="3b489-105">이 항목에서는 관리자가 이러한 사용 권한을 설정 하는 방법에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="3b489-105">This topic explains how an admin can set these permissions.</span></span>
  
<span data-ttu-id="3b489-106">예를 들어 Megan Bowen가 Microsoft 365 그룹 **교육** 의 일부인 경우 그룹에 **다른 사람 이름으로 보내기** 권한이 있는 경우 전자 메일을 그룹으로 보내면 전자 메일을 보낸 **교육** 그룹과 같이 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3b489-106">For example, if Megan Bowen is part of the **Training** Microsoft 365 group, and has **Send as** permissions on the group, if she sends an email as the group, it will look like the **Training** group sent the email.</span></span> 
  
<span data-ttu-id="3b489-107">**대신 보내기** 권한을 사용 하면 사용자가 Microsoft 365 그룹을 대신 하 여 전자 메일을 보낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3b489-107">The **Send on Behalf** permission lets a user send email on behalf of a Microsoft 365 group.</span></span> <span data-ttu-id="3b489-108">예를 들어 Alex Wilber이 **마케팅** Microsoft 365 그룹에 속해 있고 **대신 보내기** 권한을가지고 있고 전자 메일을 그룹으로 보내는 경우 전자 메일은 **마케팅을 대신 하 여 Alex Wilber에서**보낸 것 처럼 보입니다.</span><span class="sxs-lookup"><span data-stu-id="3b489-108">For example, if Alex Wilber is a part of the **Marketing** Microsoft 365 group, and has **Send on Behalf** permissions and sends an email as the group, the email looks like it was sent by **Alex Wilber on behalf of Marketing**.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="3b489-109">특정 사용자에 대해 **다른 사람 이름으로 보내기** 또는 **대신 보내기** 를 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3b489-109">You can configure **Send as** or **Send on behalf** for a given user, but not both.</span></span> <span data-ttu-id="3b489-110">둘 다를 구성 하는 경우 기본적 **으로로 보내기가**설정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3b489-110">If you configure both, it will default to **Send as**.</span></span>

> [!TIP]
> <span data-ttu-id="3b489-111">Outlook 및 웹용 Outlook을 사용 하 여 그룹에서 전자 메일을 보내는 방법에 대 한 자세한 내용은 [Microsoft 365 그룹에서 전자 메일 보내기를](https://support.office.com/article/0f4964af-aec6-484b-a65c-0434df8cdb6b.aspx) 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="3b489-111">See [Send email from or on behalf of a Microsoft 365 group](https://support.office.com/article/0f4964af-aec6-484b-a65c-0434df8cdb6b.aspx) to learn how to use Outlook and Outlook on the Web to send email from a group.</span></span>
    
## <a name="allow-members-to-send-email-as-a-group"></a><span data-ttu-id="3b489-112">구성원이 그룹으로 전자 메일을 보낼 수 있도록 허용</span><span class="sxs-lookup"><span data-stu-id="3b489-112">Allow members to send email as a group</span></span>

<span data-ttu-id="3b489-113">이 섹션에서는 사용자가 Exchange Online의 EAC ( [exchange 관리 센터](https://go.microsoft.com/fwlink/p/?linkid=2059104) )에서 그룹으로 전자 메일을 보내도록 허용 하는 방법에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="3b489-113">This section explains how to allow users to send email as a group in the [Exchange admin center](https://go.microsoft.com/fwlink/p/?linkid=2059104) (EAC) in Exchange Online.</span></span>
  
1. <span data-ttu-id="3b489-114"><a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">Exchange 관리 센터</a>에서 **받는 사람** \> **그룹**으로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="3b489-114">In the <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">Exchange admin center</a>, go to **Recipients** \> **Groups**.</span></span>
    
2. <span data-ttu-id="3b489-115">사용자 **Edit**![에 게 보낼 수](../../media/0cfcb590-dc51-4b4f-9276-bb2ce300d87e.png) 있도록 허용할 그룹에서 그룹 편집 아이콘 편집을 선택 합니다.  </span><span class="sxs-lookup"><span data-stu-id="3b489-115">Select **Edit**  ![Edit group icon](../../media/0cfcb590-dc51-4b4f-9276-bb2ce300d87e.png) on Group that you want to allow users to send as.</span></span> 
    
3. <span data-ttu-id="3b489-116">**그룹 위임을**선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="3b489-116">Select **group delegation**.</span></span>
    
4. <span data-ttu-id="3b489-117">**다른 이름으로 보내기** 섹션에서 그룹으로 **+** 보낼 사용자를 추가 하려면 서명을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="3b489-117">In the **Send As** section, select the **+** sign to add the users that you want to send as the Group.</span></span> 
    
    ![Microsoft 365 그룹으로 보낼 사용자를 추가 하려면 더하기 기호를 선택 합니다.](../../media/1df167f6-1eff-4f98-9ecd-4230fab46557.png)
  
5. <span data-ttu-id="3b489-119">목록에서 사용자를 검색 하거나 선택 하려면 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="3b489-119">Type to search or pick a user from the list.</span></span> <span data-ttu-id="3b489-120">**확인** 및 **저장**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="3b489-120">Select **OK** and **Save**.</span></span>
    
    ![목록에서 사용자를 검색 하거나 선택 하려면 입력 합니다.](../../media/522919cf-664c-4a25-8076-c51c8c9fbe43.png)
  
## <a name="allow-members-to-send-email-on-behalf-of-a-group"></a><span data-ttu-id="3b489-122">구성원이 그룹을 대신 하 여 전자 메일을 보낼 수 있도록 허용</span><span class="sxs-lookup"><span data-stu-id="3b489-122">Allow members to send email on behalf of a group</span></span>

<span data-ttu-id="3b489-123">이 섹션에서는 사용자가 Exchange Online의 EAC (Exchange 관리 센터)에서 그룹을 대신 하 여 전자 메일을 보내도록 허용 하는 방법에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="3b489-123">This section explains how to allow users to send email on behalf of a group in the Exchange admin center (EAC) in Exchange Online.</span></span>
  
1. <span data-ttu-id="3b489-124"><a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">Exchange 관리 센터</a>에서 **받는 사람** \> **그룹**으로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="3b489-124">In the <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">Exchange admin center</a>, go to **Recipients** \> **Groups**.</span></span>
    
2. <span data-ttu-id="3b489-125">사용자에 게 보낼 수](../../media/0cfcb590-dc51-4b4f-9276-bb2ce300d87e.png) 있도록 허용할 그룹에서 ![ **그룹 편집 아이콘을 선택 합니다** .</span><span class="sxs-lookup"><span data-stu-id="3b489-125">Select **Edit** ![Edit group icon](../../media/0cfcb590-dc51-4b4f-9276-bb2ce300d87e.png) on the Group that you want to allow users to send as.</span></span> 
    
3. <span data-ttu-id="3b489-126">**그룹 위임을**선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="3b489-126">Select **group delegation**.</span></span>
    
4. <span data-ttu-id="3b489-127">대신 보내기 섹션에서 그룹으로 보낼 사용자를 **+** 추가 하려면 서명을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="3b489-127">In the Send on Behalf section, select the **+** sign to add the users that you want to send as the Group.</span></span> 
    
    ![Microsoft 365 그룹으로 보낼 사용자를 추가 하려면 더하기 기호를 선택 합니다.](../../media/2bae0579-8907-4d6b-8920-ddd6555897b4.png)
  
5. <span data-ttu-id="3b489-129">목록에서 사용자를 검색 하거나 선택 하려면 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="3b489-129">Type to search or pick a user from the list.</span></span> <span data-ttu-id="3b489-130">**확인** 및 **저장**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="3b489-130">Select **OK** and **Save**.</span></span>
    
    ![목록에서 사용자를 검색 하거나 선택 하려면 입력 합니다.](../../media/522919cf-664c-4a25-8076-c51c8c9fbe43.png)

## <a name="related-articles"></a><span data-ttu-id="3b489-132">관련 문서</span><span class="sxs-lookup"><span data-stu-id="3b489-132">Related articles</span></span>

[<span data-ttu-id="3b489-133">Microsoft 365 그룹에 대 한 자세한 정보</span><span class="sxs-lookup"><span data-stu-id="3b489-133">Learn more about Microsoft 365 groups</span></span>](https://support.office.com/article/learn-about-office-365-groups-b565caa1-5c40-40ef-9915-60fdb2d97fa2)

[<span data-ttu-id="3b489-134">Add-recipientpermission 추가</span><span class="sxs-lookup"><span data-stu-id="3b489-134">Add-RecipientPermission</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=723960)

[<span data-ttu-id="3b489-135">Remove-unifiedgroup</span><span class="sxs-lookup"><span data-stu-id="3b489-135">Set-UnifiedGroup</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=616189)
