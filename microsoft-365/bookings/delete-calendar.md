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
description: Microsoft 365 관리 센터 또는 예약 Windows PowerShell 일정을 삭제합니다.
ms.openlocfilehash: 1f8df15eafac7867f7ae852e344e1c5730362598
ms.sourcegitcommit: 375168ee66be862cf3b00f2733c7be02e63408cf
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/04/2021
ms.locfileid: "50454208"
---
# <a name="delete-a-booking-calendar-in-bookings"></a><span data-ttu-id="b33eb-103">Bookings에서 예약 일정 삭제</span><span class="sxs-lookup"><span data-stu-id="b33eb-103">Delete a booking calendar in Bookings</span></span>

<span data-ttu-id="b33eb-104">이 문서에서는 원치 않는 예약 일정을 삭제하는 방법에 대해 설명하고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b33eb-104">This article explains how you can delete an unwanted booking calendar.</span></span> <span data-ttu-id="b33eb-105">Microsoft 365 관리 센터에서 예약 일정을 삭제하거나 PowerShell을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b33eb-105">You can delete the booking calendar in the Microsoft 365 admin center or you can use PowerShell.</span></span> <span data-ttu-id="b33eb-106">Bookings 일정은 Exchange Online의 사서함으로, 해당 사용자 계정을 삭제하여 예약 일정을 삭제합니다.</span><span class="sxs-lookup"><span data-stu-id="b33eb-106">The Bookings calendar is a mailbox in Exchange Online so you delete the corresponding user account to delete the booking calendar.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="b33eb-107">2017년 또는 그 전에 만든 모든 예약 일정은 이 항목의 PowerShell 지침을 사용하여 삭제해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b33eb-107">All booking calendars that you created in 2017 or before must be deleted using the PowerShell instructions on this topic.</span></span> <span data-ttu-id="b33eb-108">2018년 또는 그 이후에 만들어진 모든 예약 일정은 Microsoft 365 관리 센터에서 삭제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b33eb-108">All booking calendars created in 2018 or after can be deleted in the Microsoft 365 admin center.</span></span>

<span data-ttu-id="b33eb-109">예약 일정은 다음을 포함하여 예약 일정 및 데이터에 대한 모든 관련 정보가 저장되는 위치입니다.</span><span class="sxs-lookup"><span data-stu-id="b33eb-109">The booking calendar is where all relevant information about that booking calendar and data are stored, including:</span></span>

- <span data-ttu-id="b33eb-110">예약 일정을 만들 때 추가된 업무 정보, 로고 및 작업 시간</span><span class="sxs-lookup"><span data-stu-id="b33eb-110">Business information, logo, and working hours added when the booking calendar was created</span></span>
- <span data-ttu-id="b33eb-111">예약 일정을 만들 때 추가된 관련 직원 및 서비스</span><span class="sxs-lookup"><span data-stu-id="b33eb-111">Relevant staff and services added when the booking calendar was created</span></span>
- <span data-ttu-id="b33eb-112">예약 일정을 만든 후 예약 일정에 추가된 모든 예약 및 약속이 벗어났습니다.</span><span class="sxs-lookup"><span data-stu-id="b33eb-112">All bookings and time off appointments added to the booking calendar once it was created.</span></span>

> [!WARNING]
> <span data-ttu-id="b33eb-113">예약 일정이 삭제되면 이 추가 정보도 영구적으로 삭제되고 복구할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="b33eb-113">Once a booking calendar is deleted, this additional information is also permanently deleted and can't be recovered.</span></span>

## <a name="delete-a-booking-calendar-in-the-microsoft-365-admin-center"></a><span data-ttu-id="b33eb-114">Microsoft 365 관리 센터에서 예약 일정 삭제</span><span class="sxs-lookup"><span data-stu-id="b33eb-114">Delete a booking calendar in the Microsoft 365 admin center</span></span>

1. <span data-ttu-id="b33eb-115">Microsoft 365 관리 센터로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="b33eb-115">Go to the Microsoft 365 admin center.</span></span>

1. <span data-ttu-id="b33eb-116">관리 센터에서 **사용자** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="b33eb-116">In the Admin center, select **Users**.</span></span>

   ![Microsoft 365 관리 센터의 사용자 UI 이미지](../media/bookings-admin-center-users.png)

1. <span data-ttu-id="b33eb-118">**활성 사용자** 페이지에서 삭제할 사용자의 이름을 선택한 다음 **사용자 삭제** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="b33eb-118">On the **Active Users** page, choose the names of the users that you want to delete, and then select **Delete user**.</span></span>

   ![Microsoft 365 관리 센터에서 사용자 UI 삭제 이미지](../media/bookings-delete-user.png)

## <a name="delete-a-booking-calendar-using-exchange-online-powershell"></a><span data-ttu-id="b33eb-120">Exchange Online PowerShell을 사용하여 예약 일정 삭제</span><span class="sxs-lookup"><span data-stu-id="b33eb-120">Delete a booking calendar using Exchange Online PowerShell</span></span>

<span data-ttu-id="b33eb-121">Exchange [Online PowerShell에](https://docs.microsoft.com/powershell/exchange/exchange-online-powershell-v2?view=exchange-ps) 연결하기 위한 사전 및 지침은 Exchange Online PowerShell에 연결을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="b33eb-121">See [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online-powershell-v2?view=exchange-ps) for prerequisites and guidance for connecting to Exchange Online PowerShell.</span></span>

<span data-ttu-id="b33eb-122">이러한 단계를 수행하려면 "관리자 권한으로 실행" 옵션을 선택하여 실행한 활성 Microsoft PowerShell 명령 창을 사용하고 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b33eb-122">To perform these steps, you must be using an active Microsoft PowerShell command window that you ran by choosing the “Run as administrator” option.</span></span>

1. <span data-ttu-id="b33eb-123">PowerShell 창에서 다음 명령을 실행하여 EXO V2 모듈을 로드합니다.</span><span class="sxs-lookup"><span data-stu-id="b33eb-123">In a PowerShell window, load the EXO V2 module by running the following command:</span></span>

   ```powershell
   Import-Module ExchangeOnlineManagement
   ```

   > [!NOTE]
   > <span data-ttu-id="b33eb-124">[EXO V2 모듈을 이미 설치](https://docs.microsoft.com/powershell/exchange/exchange-online-powershell-v2?view=exchange-ps#install-and-maintain-the-exo-v2-module)한 경우 이전 명령은 기록된 대로 작동합니다.</span><span class="sxs-lookup"><span data-stu-id="b33eb-124">If you've already [installed the EXO V2 module](https://docs.microsoft.com/powershell/exchange/exchange-online-powershell-v2?view=exchange-ps#install-and-maintain-the-exo-v2-module), the previous command will work as written.</span></span>
   
2. <span data-ttu-id="b33eb-125">실행해야 하는 명령은 다음 구문을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="b33eb-125">The command that you need to run uses the following syntax:</span></span>

   ```powershell
   Connect-ExchangeOnline -UserPrincipalName <UPN> 
   ```

   - <span data-ttu-id="b33eb-126">_\<UPN\>_ 은(는) 사용자 계정 이름 형식(예: `john@contoso.com`)의 계정입니다.</span><span class="sxs-lookup"><span data-stu-id="b33eb-126">_\<UPN\>_ is your account in user principal name format (for example, `john@contoso.com`).</span></span>

3. <span data-ttu-id="b33eb-127">메시지가 표시되면 영구적으로 삭제할 예약 일정을 호스트하는 Microsoft 365 테넌트에 테넌트 관리자 자격 증명으로 로그온합니다.</span><span class="sxs-lookup"><span data-stu-id="b33eb-127">When you are prompted, log on with tenant administrator credentials to the Microsoft 365 tenant that hosts the booking calendar you want to permanently delete.</span></span>

4. <span data-ttu-id="b33eb-128">이 명령의 처리가 완료되면 다음 명령을 입력하여 테넌트의 예약 사서함 목록을 얻습니다.</span><span class="sxs-lookup"><span data-stu-id="b33eb-128">Once this command is done processing, enter the following command to get a list of the booking mailboxes in your tenant:</span></span>

   ```powershell
   Get-EXOMailbox -RecipientTypeDetails Scheduling
   ```

5. <span data-ttu-id="b33eb-129">다음 명령을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="b33eb-129">Type the following command:</span></span>

   ```powershell
   remove-mailbox [BookingCalendarToDelete]
   ```

   > [!IMPORTANT]
   > <span data-ttu-id="b33eb-130">영구적으로 삭제할 예약 사서함 별칭의 정확한 이름을 입력해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b33eb-130">Be careful to type the exact name of the booking mailbox alias that you want to permanently delete.</span></span>

6. <span data-ttu-id="b33eb-131">일정이 삭제된 것을 확인하려면 다음 명령을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="b33eb-131">To verify that the calendar has been deleted, enter the following command:</span></span>

   ```powershell
    Get-EXOMailbox -RecipientTypeDetails Scheduling
   ```

   <span data-ttu-id="b33eb-132">삭제된 달력은 출력에 나타나지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="b33eb-132">The deleted calendar will not appear in the output.</span></span>
