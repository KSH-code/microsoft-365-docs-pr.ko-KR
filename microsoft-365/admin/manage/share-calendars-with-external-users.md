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
description: 사용자가 모임 및 약속을 위해 외부 사용자와 일정을 공유할 수 있도록 하는 방법을 배워야 합니다.
ms.openlocfilehash: 8204dc025f843953af13cba58fa0cf2e4d76de45
ms.sourcegitcommit: 222fb7fe2b26dde3d8591b61cc02113d6135012c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/06/2021
ms.locfileid: "49760057"
---
# <a name="share-calendars-with-external-users"></a><span data-ttu-id="0539b-103">외부 사용자와 일정 공유</span><span class="sxs-lookup"><span data-stu-id="0539b-103">Share calendars with external users</span></span>

<span data-ttu-id="0539b-104">사용자가 조직 외부의 사용자와 모임을 예약해야 하는 경우도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0539b-104">It's sometimes necessary for your users to schedule meetings with people outside your organization.</span></span> <span data-ttu-id="0539b-105">일반적인 모임 시간을 찾는 프로세스를 간소화하기 위해 Microsoft 365를 사용하면 이러한 사용자가 일정을 사용할 수 있도록 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0539b-105">To simplify the process of finding common meeting times, Microsoft 365 enables you to make calendars available to these people.</span></span> <span data-ttu-id="0539b-106">이러한 사용자는 조직의 사용자에 대해 무료 및 바쁘게 시간을 보아야 하지만 Microsoft 365 조직의 사용자 계정이 없는 사용자입니다.</span><span class="sxs-lookup"><span data-stu-id="0539b-106">These are people who need to see free and busy times for users in your organization, but don't have user accounts for your Microsoft 365 organization.</span></span>

<span data-ttu-id="0539b-107">Microsoft 365 관리 센터에서 조직의 모든 사용자에 대해 일정 공유를 사용하도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0539b-107">You can enable calendar sharing for all users in your organization in the Microsoft 365 admin center.</span></span> <span data-ttu-id="0539b-108">공유를 사용하도록 설정하면 사용자는 공유 기능을 Outlook Web App 조직 내부 또는 외부의 모든 사용자와 일정을 공유할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0539b-108">Once sharing is enabled, your users can use Outlook Web App to share their calendars with anyone inside or outside the organization.</span></span> <span data-ttu-id="0539b-109">조직 내부의 사람은 자신의 일정과 함께 공유 일정을 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0539b-109">People inside the organization can view the shared calendar along with their own calendar.</span></span> <span data-ttu-id="0539b-110">조직 외부의 사람들은 일정을 보는 데 사용할 수 있는 URL을 받게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0539b-110">People outside the organization will be sent a URL that they can use to view the calendar.</span></span> <span data-ttu-id="0539b-111">조직의 사용자는 공유할 때와 공유할 수 있는 정도를 결정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0539b-111">Users in your organization decide when to share and how much to share.</span></span>

> [!NOTE]
> <span data-ttu-id="0539b-112">Exchange Server 2013(온-프레미스 솔루션)을 사용하는 조직과 일정을 공유하려면 Exchange 관리자가 클라우드와의 인증 관계를 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0539b-112">If you want to share calendars with an organization that uses Exchange Server 2013 (an on-premises solution), the Exchange administrator will need to set up an authentication relationship with the cloud.</span></span> <span data-ttu-id="0539b-113">이를 페더임라고하며 최소 소프트웨어 요구 사항을 충족해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0539b-113">This is known as federation, and must meet minimum software requirements.</span></span> <span data-ttu-id="0539b-114">자세한 내용은 [공유](https://technet.microsoft.com/library/dd638083%28v=exchg.150%29.aspx)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="0539b-114">See [Sharing](https://technet.microsoft.com/library/dd638083%28v=exchg.150%29.aspx) for more information.</span></span>
  
## <a name="enable-calendar-sharing-using-the-microsoft-365-admin-center"></a><span data-ttu-id="0539b-115">Microsoft 365 관리 센터를 사용하여 일정 공유 사용</span><span class="sxs-lookup"><span data-stu-id="0539b-115">Enable calendar sharing using the Microsoft 365 admin center</span></span>

1. <span data-ttu-id="0539b-116">관리 센터에서 설정  \> **구성 설정으로 이동합니다.**</span><span class="sxs-lookup"><span data-stu-id="0539b-116">In the admin center, go to **Settings** \> **Org Settings**.</span></span>

2. <span data-ttu-id="0539b-117">서비스 **탭에서** 일정을 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="0539b-117">On the **Services** tab, select **Calendar**.</span></span>
  
3. <span data-ttu-id="0539b-118">일정 **페이지에서** 사용자가 Microsoft 365 또는 Exchange가 있는 조직 외부의 사용자와 일정을 공유할 수 있도록 할지 여부를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="0539b-118">On the **Calendar** page, choose whether you want to let users share their calendars with people outside of your organization who have Microsoft 365 or Exchange.</span></span> <span data-ttu-id="0539b-119">익명 사용자(자격 증명이 없는 사용자)가 전자 메일 초대를 통해 일정에 액세스할 수 있도록 허용할지 여부를 선택하십시오.</span><span class="sxs-lookup"><span data-stu-id="0539b-119">Choose whether you want to allow anonymous users (users without credentials) to access calendars via an email invitation.</span></span>

4. <span data-ttu-id="0539b-120">사용자가 사용할 수 있도록 할 일정 정보 유형을 선택하십시오.</span><span class="sxs-lookup"><span data-stu-id="0539b-120">Choose what type of calendar information to make available to users.</span></span> <span data-ttu-id="0539b-121">모든 정보를 허용하거나 시간만 또는 시간, 주제 및 위치로만 제한할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0539b-121">You can allow all information, or limit it to time only or time, subject, and location only.</span></span>

## <a name="invite-people-to-access-calendars"></a><span data-ttu-id="0539b-122">일정에 액세스할 수 있도록 사용자 초대</span><span class="sxs-lookup"><span data-stu-id="0539b-122">Invite people to access calendars</span></span>

<span data-ttu-id="0539b-123">공유를 사용하도록 설정하면 일정 소유자가 특정 사용자로 초대를 확장할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0539b-123">Once sharing is enabled, calendar owners can extend invitations to specific users.</span></span> <span data-ttu-id="0539b-124">자세한 내용은 [Outlook Web App에서 일정 공유](https://support.microsoft.com/office/7ecef8ae-139c-40d9-bae2-a23977ee58d5)를 참고하세요.</span><span class="sxs-lookup"><span data-stu-id="0539b-124">See [Sharing your calendar in Outlook Web App](https://support.microsoft.com/office/7ecef8ae-139c-40d9-bae2-a23977ee58d5) for instructions.</span></span>