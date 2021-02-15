---
title: 예약 일정 삭제
ms.author: kwekua
author: kwekuako
manager: scotv
audience: Admin
ms.topic: article
ms.service: bookings
localization_priority: Normal
ms.assetid: 8c3a913c-2247-4519-894d-b6263eeb9920
description: Microsoft 365 관리 센터 또는 Windows PowerShell 예약 일정을 삭제합니다.
ms.openlocfilehash: 2fcb92cee18d709ef0e1fa3faa0246e622a9f9db
ms.sourcegitcommit: 0402d3275632fceda9137b6abc3ce48c8020172a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/17/2020
ms.locfileid: "49126652"
---
# <a name="delete-a-booking-calendar-in-bookings"></a><span data-ttu-id="7d333-103">Bookings에서 예약 일정 삭제</span><span class="sxs-lookup"><span data-stu-id="7d333-103">Delete a booking calendar in Bookings</span></span>

<span data-ttu-id="7d333-104">이 문서에서는 원치 않는 예약 일정을 삭제하는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="7d333-104">This article explains how you can delete an unwanted booking calendar.</span></span> <span data-ttu-id="7d333-105">Microsoft 365 관리 센터에서 예약 일정을 삭제하거나 PowerShell을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7d333-105">You can delete the booking calendar in the Microsoft 365 admin center or you can use PowerShell.</span></span> <span data-ttu-id="7d333-106">Bookings 일정은 Exchange Online의 사서함으로, 해당 사용자 계정을 삭제하여 예약 일정을 삭제합니다.</span><span class="sxs-lookup"><span data-stu-id="7d333-106">The Bookings calendar is a mailbox in Exchange Online so you delete the corresponding user account to delete the booking calendar.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="7d333-107">2017년 또는 그 전에 만든 모든 예약 일정은 이 항목의 PowerShell 지침을 사용하여 삭제해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7d333-107">All booking calendars that you created in 2017 or before must be deleted using the PowerShell instructions on this topic.</span></span> <span data-ttu-id="7d333-108">2018년 또는 그 이후에 만든 모든 예약 일정은 Microsoft 365 관리 센터에서 삭제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7d333-108">All booking calendars created in 2018 or after can be deleted in the Microsoft 365 admin center.</span></span>

<span data-ttu-id="7d333-109">예약 일정은 다음을 포함하여 예약 일정 및 데이터에 대한 모든 관련 정보가 저장되는 위치입니다.</span><span class="sxs-lookup"><span data-stu-id="7d333-109">The booking calendar is where all relevant information about that booking calendar and data are stored, including:</span></span>

- <span data-ttu-id="7d333-110">예약 일정을 만들 때 추가된 비즈니스 정보, 로고 및 작업 시간</span><span class="sxs-lookup"><span data-stu-id="7d333-110">Business information, logo, and working hours added when the booking calendar was created</span></span>
- <span data-ttu-id="7d333-111">예약 일정을 만들 때 추가된 관련 직원 및 서비스</span><span class="sxs-lookup"><span data-stu-id="7d333-111">Relevant staff and services added when the booking calendar was created</span></span>
- <span data-ttu-id="7d333-112">모든 예약 및 약속을 만든 후 예약 일정에 추가된 약속의 시간입니다.</span><span class="sxs-lookup"><span data-stu-id="7d333-112">All bookings and time off appointments added to the booking calendar once it was created.</span></span>

> [!WARNING]
> <span data-ttu-id="7d333-113">예약 일정이 삭제되면 이 추가 정보도 영구적으로 삭제되고 복구할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="7d333-113">Once a booking calendar is deleted, this additional information is also permanently deleted and can't be recovered.</span></span>

## <a name="delete-a-booking-calendar-in-the-microsoft-365-admin-center"></a><span data-ttu-id="7d333-114">Microsoft 365 관리 센터에서 예약 일정 삭제</span><span class="sxs-lookup"><span data-stu-id="7d333-114">Delete a booking calendar in the Microsoft 365 admin center</span></span>

1. <span data-ttu-id="7d333-115">Microsoft 365 관리 센터로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="7d333-115">Go to the Microsoft 365 admin center.</span></span>

1. <span data-ttu-id="7d333-116">관리 센터에서 **사용자** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="7d333-116">In the Admin center, select **Users**.</span></span>

   ![Microsoft 365 관리 센터의 사용자 UI 이미지](../media/bookings-admin-center-users.png)

1. <span data-ttu-id="7d333-118">**활성 사용자** 페이지에서 삭제할 사용자의 이름을 선택한 다음 **사용자 삭제** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="7d333-118">On the **Active Users** page, choose the names of the users that you want to delete, and then select **Delete user**.</span></span>

   ![Microsoft 365 관리 센터에서 사용자 UI 삭제 이미지](../media/bookings-delete-user.png)

## <a name="delete-a-booking-calendar-using-exchange-online-powershell"></a><span data-ttu-id="7d333-120">Exchange Online PowerShell을 사용하여 예약 일정 삭제</span><span class="sxs-lookup"><span data-stu-id="7d333-120">Delete a booking calendar using Exchange Online PowerShell</span></span>

<span data-ttu-id="7d333-121">Exchange [Online PowerShell에](https://docs.microsoft.com/powershell/exchange/exchange-online-powershell-v2?view=exchange-ps) 연결하기 위한 전제 및 지침은 Exchange Online PowerShell에 연결하기를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="7d333-121">See [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online-powershell-v2?view=exchange-ps) for prerequisites and guidance for connecting to Exchange Online PowerShell.</span></span>

<span data-ttu-id="7d333-122">이러한 단계를 수행하려면 "관리자 권한으로 실행" 옵션을 선택하여 실행한 활성 Microsoft PowerShell 명령 창을 사용하고 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7d333-122">To perform these steps, you must be using an active Microsoft PowerShell command window that you ran by choosing the “Run as administrator” option.</span></span>

1. <span data-ttu-id="7d333-123">다음 명령을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="7d333-123">Enter the following command:</span></span>

   ```PowerShell
    $user = get-credential
   ```

1. <span data-ttu-id="7d333-124">메시지가 표시되면 영구적으로 삭제할 예약 일정을 호스트하는 Microsoft 365 테넌트에 테넌트 관리자 자격 증명으로 로그온합니다.</span><span class="sxs-lookup"><span data-stu-id="7d333-124">When you are prompted, log on with tenant administrator credentials to the Microsoft 365 tenant that hosts the booking calendar you want to permanently delete.</span></span>

1. <span data-ttu-id="7d333-125">PowerShell 명령 프롬프트에 다음 명령을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="7d333-125">At the PowerShell command prompt, enter this command:</span></span>

   ```PowerShell
    $s = New-Pssession -ConnectionUri https://outlook.office365.com/powershell-liveid -Credential $user -Authentication basic -AllowRedirection -ConfigurationName Microsoft.Exchange
   ```

1. <span data-ttu-id="7d333-126">다음 명령을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="7d333-126">Enter the following command:</span></span>

   ```PowerShell
    Import-PSSession $s
   ```

1. <span data-ttu-id="7d333-127">이 명령이 처리된 후 다음 명령을 입력하여 테넌트의 예약 사서함 목록을 얻습니다.</span><span class="sxs-lookup"><span data-stu-id="7d333-127">Once this command is done processing, enter the following command to get a list of the booking mailboxes in your tenant:</span></span>

   ```PowerShell
    get-mailbox -RecipientTypeDetails Scheduling
   ```

1. <span data-ttu-id="7d333-128">다음 명령을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="7d333-128">Type the following command:</span></span>

   ```PowerShell
   remove-mailbox [BookingCalendarToDelete]
   ```

   > [!IMPORTANT]
   > <span data-ttu-id="7d333-129">영구적으로 삭제할 예약 사서함 별칭의 정확한 이름을 입력해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7d333-129">Be careful to type the exact name of the booking mailbox alias that you want to permanently delete.</span></span>

1. <span data-ttu-id="7d333-130">일정이 삭제된 것을 확인하려면 다음 명령을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="7d333-130">To verify that the calendar has been deleted, enter the following command:</span></span>

   ```PowerShell
    get-mailbox -RecipientTypeDetails Scheduling
   ```

   <span data-ttu-id="7d333-131">삭제된 달력은 출력에 나타나지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="7d333-131">The deleted calendar will not appear in the output.</span></span>
