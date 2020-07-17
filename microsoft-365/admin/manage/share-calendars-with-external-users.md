---
title: 외부 사용자와 일정 공유
f1.keywords:
- NOCSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom:
- MSStore_Link
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: fb00dd4e-2d5f-4e8d-8ff4-94b2cf002bdd
description: '사용자가 모임 및 약속을 위해 외부 사용자와 일정을 공유할 수 있도록 하는 방법을 알아봅니다. '
ms.openlocfilehash: 972e8376ae3d71b11205d4a6611dc6900c063ffe
ms.sourcegitcommit: 659adf65d88ee44f643c471e6202396f1ffb6576
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/17/2020
ms.locfileid: "44780064"
---
# <a name="share-calendars-with-external-users"></a><span data-ttu-id="cff51-103">외부 사용자와 일정 공유</span><span class="sxs-lookup"><span data-stu-id="cff51-103">Share calendars with external users</span></span>

<span data-ttu-id="cff51-104">조직 외부의 사용자와 모임을 예약 해야 하는 경우가 많습니다.</span><span class="sxs-lookup"><span data-stu-id="cff51-104">It's often necessary to schedule meetings with people outside your organization.</span></span> <span data-ttu-id="cff51-105">상호 agreeable 모임 시간을 간편 하 게 찾기 위해 Microsoft 365에서는 약속 있음/없음 시간을 확인 해야 하지만 Microsoft 365 환경에 대 한 사용자 계정이 없는 "외부 사용자"에 게 달력을 사용할 수 있도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cff51-105">To simplify the process of finding mutually agreeable meeting times, Microsoft 365 enables you to make calendars available to "external users," those who need to see free/busy time but don't have user accounts for your Microsoft 365 environment.</span></span>
  
<span data-ttu-id="cff51-106">일정 공유는 전역 설정으로, 관리자가 테 넌 트의 모든 사용자에 대해 사용 하도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cff51-106">Calendar sharing is a global setting, meaning that you, the admin, can enable it for all users in the tenant.</span></span> <span data-ttu-id="cff51-107">공유가 설정되면 사용자는 Outlook Web App을 사용하여 자신의 일정을 조직 안팎의 모든 사람과 공유할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cff51-107">Once sharing is enabled, users can use Outlook Web App to share their calendars with anyone inside or outside the organization.</span></span> <span data-ttu-id="cff51-108">조직 내 사람들은 공유된 일정을 자신의 일정과 나란히 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cff51-108">People inside the organization can view the shared calendar side-by-side with their own.</span></span> <span data-ttu-id="cff51-109">조직 외부의 사람들은 일정을 보는 데 사용할 수 있는 URL을 받게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="cff51-109">People outside the organization will be sent a URL that they can use to view the calendar.</span></span> <span data-ttu-id="cff51-110">사용자는 공유 시기, 공유 수준, 일정을 비공개로 유지할 기간을 결정합니다.</span><span class="sxs-lookup"><span data-stu-id="cff51-110">Users decide when to share, how much to share, and when to keep their calendars private.</span></span>
  
> [!NOTE]
> <span data-ttu-id="cff51-p103">Exchange Server 2013(온-프레미스 솔루션)을 사용하는 조직과 일정을 공유하려면 Exchange 관리자가 클라우드와의 인증 관계를 설정해야 합니다. 이를 "페더레이션"이라고 하며 최소 소프트웨어 요구 사항을 충족해야 합니다. 자세한 내용은 [공유](https://technet.microsoft.com/library/dd638083%28v=exchg.150%29.aspx)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="cff51-p103">If you want to share calendars with an organization that uses Exchange Server 2013 (an on-premises solution), the Exchange administrator will need to set up an authentication relationship with the cloud. This is known as "federation" and must meet minimum software requirements. See [Sharing](https://technet.microsoft.com/library/dd638083%28v=exchg.150%29.aspx) for more information.</span></span> 
  
## <a name="enable-calendar-sharing-using-the-microsoft-365-admin-center"></a><span data-ttu-id="cff51-114">Microsoft 365 관리 센터를 사용 하 여 일정 공유를 사용 하도록 설정</span><span class="sxs-lookup"><span data-stu-id="cff51-114">Enable calendar sharing using the Microsoft 365 admin center</span></span>

1. <span data-ttu-id="cff51-115">관리 센터에서 **설정** \> **조직 설정**으로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="cff51-115">In the admin center, go to **Settings** \> **Org Settings**.</span></span> 
    
2. <span data-ttu-id="cff51-116">**서비스** 탭에서 **일정**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="cff51-116">On the **Services** tab, select **Calendar**.</span></span>
  
3. <span data-ttu-id="cff51-117">열리는 **일정** 페이지에서 사용자가 Microsoft 365 또는 Exchange를 사용 하는 조직 외부의 사용자와 일정을 공유할 수 있도록 할지 여부를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="cff51-117">On the **Calendar** page that opens, choose whether you want to let your users share their calendars with people outside of your organization who have Microsoft 365 or Exchange.</span></span>
    
4. <span data-ttu-id="cff51-118">익명 사용자 (로그온 자격 증명이 없는 사용자)에 게 전자 메일 초대를 통해 일정에 액세스 하도록 허용할지 여부를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="cff51-118">Choose whether you want to allow anonymous users (users without logon credentials) to access calendars via an email invitation.</span></span>

5. <span data-ttu-id="cff51-119">사용자에 게 제공할 일정 정보 유형을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="cff51-119">Choose what type of calendar information to make available to users.</span></span> <span data-ttu-id="cff51-120">모든 정보를 허용 하거나 시간, 제목 및 위치만으로 제한할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cff51-120">You can allow all information, or limit it to time only or time, subject, and location only.</span></span>

    
## <a name="invite-people-to-access-calendars"></a><span data-ttu-id="cff51-121">일정에 액세스할 수 있도록 사용자 초대</span><span class="sxs-lookup"><span data-stu-id="cff51-121">Invite people to access calendars</span></span>

<span data-ttu-id="cff51-p105">테넌트에 공유가 설정되면 일정 소유자는 특정 사용자로 초대를 확장할 수 있습니다. 자세한 내용은 [Outlook Web App에서 일정 공유](https://support.microsoft.com/office/7ecef8ae-139c-40d9-bae2-a23977ee58d5)를 참고하세요.</span><span class="sxs-lookup"><span data-stu-id="cff51-p105">Once sharing is enabled for the tenant, calendar owners can extend invitations to specific users. See [Sharing your calendar in Outlook Web App](https://support.microsoft.com/office/7ecef8ae-139c-40d9-bae2-a23977ee58d5) for instructions.</span></span> 
  
