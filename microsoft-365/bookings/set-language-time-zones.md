---
title: Microsoft 예약에서 언어 및 표준 시간대 설정
ms.author: kwekua
author: kwekuako
manager: scotv
audience: Admin
ms.topic: article
ms.service: bookings
localization_priority: Normal
ms.assetid: 94af3e22-aca6-4e91-8b91-1cd5a02a9ea8
description: Microsoft 예약에서 언어 및 표준 시간대 설정을 변경 합니다. 예약이 잘못 된 시간에 생성 되는 경우 예약이 잘못 된 표준 시간대에 대해 설정 될 수 있습니다.
ms.openlocfilehash: 07e5dde2a896610ee079063943aff24ec69ba721
ms.sourcegitcommit: 41fd71ec7175ea3b94f5d3ea1ae2c8fb8dc84227
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/09/2020
ms.locfileid: "47419924"
---
# <a name="set-language-and-time-zones-in-microsoft-bookings"></a><span data-ttu-id="1391b-104">Microsoft 예약에서 언어 및 표준 시간대 설정</span><span class="sxs-lookup"><span data-stu-id="1391b-104">Set language and time zones in Microsoft Bookings</span></span>

<span data-ttu-id="1391b-105">Microsoft 예약을 사용 하는 경우 예약을 잘못 된 시간에 만든 경우 표준 시간대 설정을 변경 해야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1391b-105">If you are using Microsoft Bookings and bookings are created at the wrong time, then your time zone settings might need to be changed.</span></span> <span data-ttu-id="1391b-106">마찬가지로 일부 예약이 잘못 된 언어로 되어 있는 경우 언어 설정을 변경 해야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1391b-106">Likewise, if some bookings are in the wrong language, you might need to change your language settings.</span></span>

<span data-ttu-id="1391b-107">예약에는 두 가지 개별 언어 및 표준 시간대 설정이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1391b-107">There are two separate language and time zone settings for Bookings.</span></span> <span data-ttu-id="1391b-108">첫 번째 설정은 예약 일정의 언어 및 표준 시간대를 제어 하 고 로그인 한 사용자의 개인 일정에 대 한 웹 설정에서 Outlook을 사용 하 여 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="1391b-108">The first setting controls the language and time zone of the booking calendar and is set using the Outlook on the web settings for the personal calendar of the logged-in user.</span></span> <span data-ttu-id="1391b-109">두 번째 설정은 고객이 사용 하 고 해당 페이지의 언어 및 표준 시간대를 제어 하는 "국가별 설정" 페이지를 사용 하 여 설정 되는 셀프 서비스 예약 페이지에 영향을 줍니다.</span><span class="sxs-lookup"><span data-stu-id="1391b-109">The second setting affects the self-service booking page that your customers use and is set using a "regional settings" page that controls language and time zone only for that page.</span></span>

> [!NOTE]
> <span data-ttu-id="1391b-110">Microsoft 365 Business Standard, Microsoft 365 A3 또는 Microsoft 365 A5 구독이 있는 고객의 경우 기본적으로 예약이 설정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1391b-110">Bookings is turned on by default for customers who have the Microsoft 365 Business Standard, Microsoft 365 A3, or Microsoft 365 A5 subscriptions.</span></span> <span data-ttu-id="1391b-111">Office 365 Enterprise E3 및 Office 365 Enterprise E5가 있는 고객 에게도 예약을 사용할 수 있지만 기본적으로이 기능은 해제 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1391b-111">Bookings is also available to customers who have Office 365 Enterprise E3 and Office 365 Enterprise E5, but it is turned off by default.</span></span> <span data-ttu-id="1391b-112">시작 하려면 [Microsoft 예약에 대 한 get 액세스](get-access.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="1391b-112">To get started, see [Get access to Microsoft Bookings](get-access.md).</span></span> <span data-ttu-id="1391b-113">예약을 설정 하거나 해제 하려면 [조직에 대해 예약 설정 또는 해제](turn-bookings-on-or-off.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="1391b-113">To turn Bookings on or off, see [Turn Bookings on or off for your organization](turn-bookings-on-or-off.md).</span></span>

## <a name="setting-language-and-time-zone-for-a-booking-calendar"></a><span data-ttu-id="1391b-114">예약 일정에 언어 및 표준 시간대 설정</span><span class="sxs-lookup"><span data-stu-id="1391b-114">Setting language and time zone for a booking calendar</span></span>

<span data-ttu-id="1391b-115">예약 일정은 로그인 한 사용자의 언어 및 표준 시간대 설정을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="1391b-115">The booking calendar uses the logged-in user’s language and time zone settings.</span></span> <span data-ttu-id="1391b-116">예를 들어 로그인 한 사용자의 표준 시간대가 EST (동부 Standard Time)로 설정 되어 있으면 예약 일정에는 EST의 기존 약속 시작 시간 및 종료 시간이 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1391b-116">For example, If the logged-in user’s time zone is set to Eastern Standard Time (EST), then the booking calendar will show existing appointment start and end times in EST.</span></span> <span data-ttu-id="1391b-117">이 표준 시간대는 원래 사용자의 Microsoft 365 및 웹 계정의 Outlook을 만들었을 때 설정 된 것입니다.</span><span class="sxs-lookup"><span data-stu-id="1391b-117">This time zone was originally set when the user’s Microsoft 365 and Outlook on the web accounts were created.</span></span>

<span data-ttu-id="1391b-118">예약 일정의 언어 및 표준 시간대를 설정 하려면 다음을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="1391b-118">To set the language and time zone for the booking calendar:</span></span>

1. <span data-ttu-id="1391b-119">Microsoft 365에 로그인 하 고 랜딩 페이지 (아래 스크린샷 참조) 또는 Microsoft 365 앱 시작 관리자에서 Outlook 타일을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="1391b-119">Log into Microsoft 365 and select the Outlook tile on the landing page (as shown in the screenshot below) or in the Microsoft 365 App Launcher.</span></span>

   ![Microsoft 365 방문 페이지의 Outlook 타일 이미지](../media/bookings-outlook-tile.png)

1. <span data-ttu-id="1391b-121">Outlook이 열리면 화면 오른쪽 위 모서리에 있는 **기어 아이콘** 을 선택 하 여 개인 및 계정 설정을 연 다음 **설정** 패널 검색 상자에서 "표준 시간대"를 검색 합니다.</span><span class="sxs-lookup"><span data-stu-id="1391b-121">After Outlook opens, select the **gear icon** in the upper, right-hand corner of the screen to open your personal and account settings, then search for “time zone” in the **Settings** panel search box.</span></span> <span data-ttu-id="1391b-122">이 계정에 대 한 현재 개인 언어 및 표준 시간대 설정이 표시 되도록 패널이 업데이트 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1391b-122">The panel will update to show your current personal language and time zone settings for this account.</span></span> <span data-ttu-id="1391b-123">위에서 설명한 것 처럼이 설정은 예약 일정의 언어 및 표준 시간대를 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="1391b-123">As noted above, this setting also controls the language and time zone of the booking calendar.</span></span>

1. <span data-ttu-id="1391b-124">**언어 또는 현재 표준 시간대** 상자에서 드롭다운 화살표를 선택 하 고 원하는 설정을 선택 하 여 언어 또는 표준 시간대를 변경 합니다.</span><span class="sxs-lookup"><span data-stu-id="1391b-124">Change the language or time zone by selecting the drop-down arrow in the **Language or Current time zone** box and choosing the desired setting.</span></span>

1. <span data-ttu-id="1391b-125">**저장**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="1391b-125">Click **Save**.</span></span> <span data-ttu-id="1391b-126">설정 패널이 닫히고, 웹에서 Outlook이 다시 시작 되 고, 새 언어 및 표준 시간대 설정이 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1391b-126">The Settings panel closes, Outlook on the web restarts, and the new language and time zone settings are applied.</span></span>

## <a name="setting-the-language-and-time-zone-for-the-booking-page"></a><span data-ttu-id="1391b-127">예약 페이지의 언어 및 표준 시간대 설정</span><span class="sxs-lookup"><span data-stu-id="1391b-127">Setting the language and time zone for the booking page</span></span>

1. <span data-ttu-id="1391b-128">Microsoft 365에서 앱 시작 관리자를 선택한 다음 **예약**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="1391b-128">In Microsoft 365, select the app launcher, and then select **Bookings**.</span></span>

1. <span data-ttu-id="1391b-129">탐색 창에서 **예약 페이지** 를 선택 하 고 **언어 및 표준 시간대 설정 변경을**선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="1391b-129">In the navigation pane, select **Booking page** and select **Change language and time zone settings**.</span></span>

   ![스크린샷: 언어 및 표준 시간대 설정 변경 링크](../media/bookings-region-language-timezone-settings.png)

1. <span data-ttu-id="1391b-131">언어 및 현재 표준 시간대를 선택 하 고 확인을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="1391b-131">Select your language and current time zone and choose OK.</span></span>

   ![스크린샷: 언어 및 표준 시간대 설정](../media/bookings-region-timezone-settings.png)
