---
title: 예약 달력 삭제
ms.author: kwekua
author: kwekuako
manager: scotv
audience: Admin
ms.topic: article
ms.service: bookings
localization_priority: Normal
ms.assetid: 8c3a913c-2247-4519-894d-b6263eeb9920
description: Microsoft 365 관리 센터 또는 Windows PowerShell을 사용 하 여 예약 일정을 삭제할 수 있습니다.
ms.openlocfilehash: 3a1cb1c54f60247ab72056b3e39b56b0981228b7
ms.sourcegitcommit: eb3c30d53a5434d8bad7c8f48a5612f3e2675945
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/09/2020
ms.locfileid: "47422445"
---
# <a name="delete-a-booking-calendar-in-bookings"></a><span data-ttu-id="ab2a2-103">예약에서 예약 달력 삭제</span><span class="sxs-lookup"><span data-stu-id="ab2a2-103">Delete a booking calendar in Bookings</span></span>

<span data-ttu-id="ab2a2-104">이 문서에서는 원하지 않는 예약 일정을 삭제 하는 방법에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="ab2a2-104">This article explains how you can delete an unwanted booking calendar.</span></span> <span data-ttu-id="ab2a2-105">Microsoft 365 관리 센터에서 예약 일정을 삭제 하거나 PowerShell을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ab2a2-105">You can delete the booking calendar in the Microsoft 365 admin center or you can use PowerShell.</span></span> <span data-ttu-id="ab2a2-106">예약 일정은 Exchange Online의 사서함 이므로 해당 사용자 계정을 삭제 하 여 예약 일정을 삭제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ab2a2-106">The Bookings calendar is a mailbox in Exchange Online so you delete the corresponding user account to delete the booking calendar.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="ab2a2-107">2017 이상에서 만든 모든 예약 일정은이 항목의 PowerShell 지침을 사용 하 여 삭제 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ab2a2-107">All booking calendars that you created in 2017 or before must be deleted using the PowerShell instructions on this topic.</span></span> <span data-ttu-id="ab2a2-108">2018 또는 이후에 만든 모든 예약 일정은 Microsoft 365 관리 센터에서 삭제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ab2a2-108">All booking calendars created in 2018 or after can be deleted in the Microsoft 365 admin center.</span></span>

<span data-ttu-id="ab2a2-109">예약 일정은 다음과 같은 해당 예약 일정과 데이터에 대 한 모든 관련 정보가 저장 되는 위치입니다.</span><span class="sxs-lookup"><span data-stu-id="ab2a2-109">The booking calendar is where all relevant information about that booking calendar and data are stored, including:</span></span>

- <span data-ttu-id="ab2a2-110">예약 일정을 만들 때 추가 된 회사 정보, 로고 및 근무 시간</span><span class="sxs-lookup"><span data-stu-id="ab2a2-110">Business information, logo, and working hours added when the booking calendar was created</span></span>
- <span data-ttu-id="ab2a2-111">예약 일정을 만들 때 추가 된 관련 직원 및 서비스</span><span class="sxs-lookup"><span data-stu-id="ab2a2-111">Relevant staff and services added when the booking calendar was created</span></span>
- <span data-ttu-id="ab2a2-112">예약 된 모든 예약 및 휴가 약속이 만들어진 일정에 추가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ab2a2-112">All bookings and time off appointments added to the booking calendar once it was created.</span></span>

> [!WARNING]
> <span data-ttu-id="ab2a2-113">예약 일정이 삭제 되 면이 추가 정보도 영구적으로 삭제 되며 복구할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="ab2a2-113">Once a booking calendar is deleted, this additional information is also permanently deleted and can't be recovered.</span></span>

## <a name="delete-a-booking-calendar-in-the-microsoft-365-admin-center"></a><span data-ttu-id="ab2a2-114">Microsoft 365 관리 센터에서 예약 달력 삭제</span><span class="sxs-lookup"><span data-stu-id="ab2a2-114">Delete a booking calendar in the Microsoft 365 admin center</span></span>

1. <span data-ttu-id="ab2a2-115">Microsoft 365 관리 센터로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="ab2a2-115">Go to the Microsoft 365 admin center.</span></span>

1. <span data-ttu-id="ab2a2-116">관리 센터에서 **사용자** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="ab2a2-116">In the Admin center, select **Users**.</span></span>

   ![Microsoft 365 관리 센터의 사용자 UI의 이미지](../media/bookings-admin-center-users.png)

1. <span data-ttu-id="ab2a2-118">**활성 사용자** 페이지에서 삭제할 사용자의 이름을 선택한 다음 **사용자 삭제**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="ab2a2-118">On the **Active Users** page, choose the names of the users that you want to delete, and then select **Delete user**.</span></span>

   ![Microsoft 365 관리 센터의 사용자 UI 삭제 이미지](../media/bookings-delete-user.png)

## <a name="delete-a-booking-calendar-using-exchange-online-powershell"></a><span data-ttu-id="ab2a2-120">Exchange Online PowerShell을 사용 하 여 예약 달력 삭제</span><span class="sxs-lookup"><span data-stu-id="ab2a2-120">Delete a booking calendar using Exchange Online PowerShell</span></span>

<span data-ttu-id="ab2a2-121">필수 구성 요소는 exchange [Online powershell에 연결](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell) 및 Exchange online powershell에 연결 하기 위한 지침을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="ab2a2-121">See [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell) for prerequisites and guidance for connecting to Exchange Online PowerShell.</span></span>

<span data-ttu-id="ab2a2-122">이 단계를 수행 하려면 "관리자 권한으로 실행" 옵션을 선택 하 여 실행 한 활성 Microsoft PowerShell 명령 창을 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ab2a2-122">To perform these steps, you must be using an active Microsoft PowerShell command window that you ran by choosing the “Run as administrator” option.</span></span>

1. <span data-ttu-id="ab2a2-123">다음 명령을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="ab2a2-123">Enter the following command:</span></span>

   ```PowerShell
    $user = get-credential
   ```

1. <span data-ttu-id="ab2a2-124">메시지가 표시 되 면 영구적으로 삭제 하려는 예약 일정을 호스트 하는 Microsoft 365 테 넌 트에 테 넌 트 관리자 자격 증명을 사용 하 여 로그온 합니다.</span><span class="sxs-lookup"><span data-stu-id="ab2a2-124">When you are prompted, log on with tenant administrator credentials to the Microsoft 365 tenant that hosts the booking calendar you want to permanently delete.</span></span>

1. <span data-ttu-id="ab2a2-125">PowerShell 명령 프롬프트에 다음 명령을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="ab2a2-125">At the PowerShell command prompt, enter this command:</span></span>

   ```PowerShell
    $s = New-Pssession -ConnectionUri https://outlook.office365.com/powershell-liveid -Credential $user -Authentication basic -AllowRedirection -ConfigurationName Microsoft.Exchange
   ```

1. <span data-ttu-id="ab2a2-126">다음 명령을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="ab2a2-126">Enter the following command:</span></span>

   ```PowerShell
    Import-PSSession $s
   ```

1. <span data-ttu-id="ab2a2-127">이 명령 처리가 완료 되 면 다음 명령을 입력 하 여 테 넌 트의 예약 사서함 목록을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="ab2a2-127">Once this command is done processing, enter the following command to get a list of the booking mailboxes in your tenant:</span></span>

   ```PowerShell
    get-mailbox -RecipientTypeDetails Scheduling
   ```

1. <span data-ttu-id="ab2a2-128">다음 명령을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="ab2a2-128">Type the following command:</span></span>

   ```PowerShell
   remove-mailbox [BookingCalendarToDelete]
   ```

   > [!IMPORTANT]
   > <span data-ttu-id="ab2a2-129">영구적으로 삭제 하려는 예약 사서함 별칭의 정확한 이름을 입력 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="ab2a2-129">Be careful to type the exact name of the booking mailbox alias that you want to permanently delete.</span></span>

1. <span data-ttu-id="ab2a2-130">일정이 삭제 되었는지 확인 하려면 다음 명령을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="ab2a2-130">To verify that the calendar has been deleted, enter the following command:</span></span>

   ```PowerShell
    get-mailbox -RecipientTypeDetails Scheduling
   ```

   <span data-ttu-id="ab2a2-131">삭제 된 달력이 출력에 표시 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="ab2a2-131">The deleted calendar will not appear in the output.</span></span>
