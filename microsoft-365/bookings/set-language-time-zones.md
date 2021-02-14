---
title: Microsoft Bookings에서 언어 및 표준 시간대 설정
ms.author: kwekua
author: kwekuako
manager: scotv
audience: Admin
ms.topic: article
ms.service: bookings
localization_priority: Normal
ms.assetid: 94af3e22-aca6-4e91-8b91-1cd5a02a9ea8
description: Microsoft Bookings에서 언어 및 표준 시간대 설정을 변경합니다. 잘못된 시간대에 예약을 만든 경우 Bookings가 잘못된 표준 시간대로 설정될 수 있습니다.
ms.openlocfilehash: 3e7709666d6426b11c275e46a18d43e7b7ab3526
ms.sourcegitcommit: 7c0873d2a804f17697844fb13f1a100fabce86c4
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/18/2020
ms.locfileid: "47962434"
---
# <a name="set-language-and-time-zones-in-microsoft-bookings"></a><span data-ttu-id="61c0a-104">Microsoft Bookings에서 언어 및 표준 시간대 설정</span><span class="sxs-lookup"><span data-stu-id="61c0a-104">Set language and time zones in Microsoft Bookings</span></span>

<span data-ttu-id="61c0a-105">Microsoft Bookings를 사용 중이고 예약이 잘못된 시간으로 만들어진 경우 표준 시간대 설정을 변경해야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="61c0a-105">If you are using Microsoft Bookings and bookings are created at the wrong time, then your time zone settings might need to be changed.</span></span> <span data-ttu-id="61c0a-106">마찬가지로 일부 예약이 잘못된 언어인 경우 언어 설정을 변경해야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="61c0a-106">Likewise, if some bookings are in the wrong language, you might need to change your language settings.</span></span>

<span data-ttu-id="61c0a-107">Bookings에 대한 두 가지 언어 및 표준 시간대 설정이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="61c0a-107">There are two separate language and time zone settings for Bookings.</span></span> <span data-ttu-id="61c0a-108">첫 번째 설정은 예약 일정의 언어 및 표준 시간대를 제어하고 로그인한 사용자의 개인 일정에 대한 웹용 Outlook 설정을 사용하여 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="61c0a-108">The first setting controls the language and time zone of the booking calendar and is set using the Outlook on the web settings for the personal calendar of the logged-in user.</span></span> <span data-ttu-id="61c0a-109">두 번째 설정은 고객이 사용하는 셀프 서비스 예약 페이지에 영향을 주며 해당 페이지에 대한 언어 및 표준 시간대만 제어하는 "국가별 설정" 페이지를 사용하여 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="61c0a-109">The second setting affects the self-service booking page that your customers use and is set using a "regional settings" page that controls language and time zone only for that page.</span></span>

## <a name="setting-language-and-time-zone-for-a-booking-calendar"></a><span data-ttu-id="61c0a-110">예약 일정의 언어 및 표준 시간대 설정</span><span class="sxs-lookup"><span data-stu-id="61c0a-110">Setting language and time zone for a booking calendar</span></span>

<span data-ttu-id="61c0a-111">예약 일정은 로그인한 사용자의 언어 및 표준 시간대 설정을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="61c0a-111">The booking calendar uses the logged-in user’s language and time zone settings.</span></span> <span data-ttu-id="61c0a-112">예를 들어 로그인한 사용자의 표준 시간대를 동부 표준시(EST)로 설정하면 예약 일정에 기존 약속 시작 및 종료 시간이 EST로 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="61c0a-112">For example, If the logged-in user’s time zone is set to Eastern Standard Time (EST), then the booking calendar will show existing appointment start and end times in EST.</span></span> <span data-ttu-id="61c0a-113">이 표준 시간대는 원래 사용자의 Microsoft 365 및 웹 계정의 Outlook을 만들 때 설정되었습니다.</span><span class="sxs-lookup"><span data-stu-id="61c0a-113">This time zone was originally set when the user’s Microsoft 365 and Outlook on the web accounts were created.</span></span>

<span data-ttu-id="61c0a-114">예약 일정의 언어 및 표준 시간대를 설정하는 경우:</span><span class="sxs-lookup"><span data-stu-id="61c0a-114">To set the language and time zone for the booking calendar:</span></span>

1. <span data-ttu-id="61c0a-115">Microsoft 365에 로그인하고 방문 페이지(아래 스크린샷에 표시된 것) 또는 Microsoft 365 앱 시작러에서 Outlook 타일을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="61c0a-115">Log into Microsoft 365 and select the Outlook tile on the landing page (as shown in the screenshot below) or in the Microsoft 365 App Launcher.</span></span>

   ![Microsoft 365 방문 페이지의 Outlook 타일 이미지](../media/bookings-outlook-tile.png)

1. <span data-ttu-id="61c0a-117">Outlook이 열리면  화면의 오른쪽 위 모서리에 있는 기어 아이콘을 선택하여 개인 설정과 계정 설정을 연  다음 설정 패널 검색 상자에서 "표준 시간대"를 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="61c0a-117">After Outlook opens, select the **gear icon** in the upper, right-hand corner of the screen to open your personal and account settings, then search for “time zone” in the **Settings** panel search box.</span></span> <span data-ttu-id="61c0a-118">이 계정에 대한 현재 개인 언어 및 표준 시간대 설정을 표시하기 위해 패널이 업데이트됩니다.</span><span class="sxs-lookup"><span data-stu-id="61c0a-118">The panel will update to show your current personal language and time zone settings for this account.</span></span> <span data-ttu-id="61c0a-119">위에서 설명한 대로 이 설정은 예약 일정의 언어 및 표준 시간대도 제어합니다.</span><span class="sxs-lookup"><span data-stu-id="61c0a-119">As noted above, this setting also controls the language and time zone of the booking calendar.</span></span>

1. <span data-ttu-id="61c0a-120">언어 또는 현재 표준 시간대 상자에서 드롭다운  화살표를 선택하고 원하는 설정을 선택하여 언어 또는 표준 시간대를 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="61c0a-120">Change the language or time zone by selecting the drop-down arrow in the **Language or Current time zone** box and choosing the desired setting.</span></span>

1. <span data-ttu-id="61c0a-121">**저장** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="61c0a-121">Click **Save**.</span></span> <span data-ttu-id="61c0a-122">설정 패널이 닫히고, 웹용 Outlook이 다시 시작되고, 새 언어 및 표준 시간대 설정이 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="61c0a-122">The Settings panel closes, Outlook on the web restarts, and the new language and time zone settings are applied.</span></span>

## <a name="setting-the-language-and-time-zone-for-the-booking-page"></a><span data-ttu-id="61c0a-123">예약 페이지의 언어 및 표준 시간대 설정</span><span class="sxs-lookup"><span data-stu-id="61c0a-123">Setting the language and time zone for the booking page</span></span>

1. <span data-ttu-id="61c0a-124">Microsoft 365에서 앱 시작 프로그램을 선택한 다음 **Bookings를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="61c0a-124">In Microsoft 365, select the app launcher, and then select **Bookings**.</span></span>

1. <span data-ttu-id="61c0a-125">탐색 창에서 예약  페이지를 선택하고 언어 및 표준 시간대 **설정 변경을 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="61c0a-125">In the navigation pane, select **Booking page** and select **Change language and time zone settings**.</span></span>

   ![스크린샷: 언어 및 표준 시간대 설정 변경 링크](../media/bookings-region-language-timezone-settings.png)

1. <span data-ttu-id="61c0a-127">언어 및 현재 표준 시간대를 선택하고 확인을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="61c0a-127">Select your language and current time zone and choose OK.</span></span>

   ![스크린샷: 언어 및 표준 시간대 설정](../media/bookings-region-timezone-settings.png)
