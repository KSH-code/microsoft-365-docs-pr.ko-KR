---
title: Microsoft Defender 보안 센터 표준 시간대 설정
description: 여기에 포함된 정보를 사용하여 Microsoft Defender 보안 센터 표준 시간대 설정을 구성하고 라이선스 정보를 볼 수 있습니다.
keywords: 설정, Microsoft Defender, 사이버 보안 위협 인텔리전스, 고급 위협 방지, 표준 시간대, utc, 현지 시간, 라이선스
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: e395420b92c29977f1c802d1c10683492c1aba10
ms.sourcegitcommit: d4604e333507c6f57d5bf327531a241b649052de
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/31/2021
ms.locfileid: "51470468"
---
# <a name="microsoft-defender-security-center-time-zone-settings"></a><span data-ttu-id="506eb-104">Microsoft Defender 보안 센터 표준 시간대 설정</span><span class="sxs-lookup"><span data-stu-id="506eb-104">Microsoft Defender Security Center time zone settings</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="506eb-105">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="506eb-105">**Applies to:**</span></span>
- [<span data-ttu-id="506eb-106">엔드포인트용 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="506eb-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)


><span data-ttu-id="506eb-107">끝점용 Microsoft Defender를 경험하고 싶나요?</span><span class="sxs-lookup"><span data-stu-id="506eb-107">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="506eb-108">무료 평가판에 등록합니다.</span><span class="sxs-lookup"><span data-stu-id="506eb-108">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-settings-abovefoldlink)

<span data-ttu-id="506eb-109">표준 시간대 **메뉴** 표준 시간대 설정 아이콘1을 사용하여 표준 시간대를 구성하고 라이선스 ![ 정보를 ](images/atp-time-zone.png) 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="506eb-109">Use the **Time zone** menu ![Time zone settings icon1](images/atp-time-zone.png) to configure the time zone and view license information.</span></span>

## <a name="time-zone-settings"></a><span data-ttu-id="506eb-110">표준 시간대 설정</span><span class="sxs-lookup"><span data-stu-id="506eb-110">Time zone settings</span></span>
<span data-ttu-id="506eb-111">시간 측면은 인식된 사이버 공격과 실제 사이버 공격의 평가 및 분석에서 중요합니다.</span><span class="sxs-lookup"><span data-stu-id="506eb-111">The aspect of time is important in the assessment and analysis of perceived and actual cyberattacks.</span></span>

<span data-ttu-id="506eb-112">사이버 포렌식 조사는 종종 타임스탬프를 통해 일련의 이벤트를 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="506eb-112">Cyberforensic investigations often rely on time stamps to piece together the sequence of events.</span></span> <span data-ttu-id="506eb-113">시스템이 올바른 표준 시간대 설정을 반영하는 것이 중요합니다.</span><span class="sxs-lookup"><span data-stu-id="506eb-113">It’s important that your system reflects the correct time zone settings.</span></span>

<span data-ttu-id="506eb-114">끝점용 Microsoft Defender는 UTC(협정 세계시) 또는 현지 시간을 표시할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="506eb-114">Microsoft Defender for Endpoint can display either Coordinated Universal Time (UTC) or local time.</span></span>

<span data-ttu-id="506eb-115">현재 표준 시간대 설정은 끝점용 Microsoft Defender 메뉴에 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="506eb-115">Your current time zone setting is shown in the Microsoft Defender for Endpoint menu.</span></span> <span data-ttu-id="506eb-116">표준 시간대 메뉴에서 표시된 표준 시간대를 **변경할 수** 있습니다.</span><span class="sxs-lookup"><span data-stu-id="506eb-116">You can change the displayed time zone in the **Time zone** menu.</span></span>

![표준 시간대 설정 아이콘2](images/atp-time-zone-menu.png)<span data-ttu-id="506eb-118">.</span><span class="sxs-lookup"><span data-stu-id="506eb-118">.</span></span>

### <a name="utc-time-zone"></a><span data-ttu-id="506eb-119">UTC 표준 시간대</span><span class="sxs-lookup"><span data-stu-id="506eb-119">UTC time zone</span></span>
<span data-ttu-id="506eb-120">Microsoft Defender for Endpoint는 기본적으로 UTC 시간을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="506eb-120">Microsoft Defender for Endpoint uses UTC time by default.</span></span>

<span data-ttu-id="506eb-121">끝점 표준 시간대에 대한 Microsoft Defender를 UTC로 설정하면 모든 사용자에 대한 모든 시스템 타임스탬프(경고, 이벤트 등)가 UTC로 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="506eb-121">Setting the Microsoft Defender for Endpoint time zone to UTC will display all system timestamps (alerts, events, and others) in UTC for all users.</span></span> <span data-ttu-id="506eb-122">이를 통해 전 세계 여러 위치에서 작업하는 보안 분석가가 이벤트를 조사하는 동안 동일한 타임스탬프를 사용하는 데 도움이 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="506eb-122">This can help security analysts working in different locations across the globe to use the same time stamps while investigating events.</span></span>

### <a name="local-time-zone"></a><span data-ttu-id="506eb-123">현지 표준 시간대</span><span class="sxs-lookup"><span data-stu-id="506eb-123">Local time zone</span></span>
<span data-ttu-id="506eb-124">끝점용 Microsoft Defender가 현지 표준 시간대 설정을 사용하게 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="506eb-124">You can choose to have Microsoft Defender for Endpoint use local time zone settings.</span></span> <span data-ttu-id="506eb-125">모든 경고 및 이벤트는 현지 표준 시간대를 사용하여 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="506eb-125">All alerts and events will be displayed using your local time zone.</span></span>

<span data-ttu-id="506eb-126">로컬 표준 시간대는 장치의 국가별 설정에서 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="506eb-126">The local time zone is taken from your device’s regional settings.</span></span> <span data-ttu-id="506eb-127">국가별 설정을 변경하면 끝점용 Microsoft Defender 표준 시간대도 변경됩니다.</span><span class="sxs-lookup"><span data-stu-id="506eb-127">If you change your regional settings, the Microsoft Defender for Endpoint time zone will also change.</span></span> <span data-ttu-id="506eb-128">이 설정을 선택하면 끝점용 Microsoft Defender에 표시되는 타임스탬프가 모든 끝점 사용자에 대한 현지 시간으로 정렬됩니다.</span><span class="sxs-lookup"><span data-stu-id="506eb-128">Choosing this setting means that the timestamps displayed in Microsoft Defender for Endpoint will be aligned to local time for all Microsoft Defender for Endpoint users.</span></span> <span data-ttu-id="506eb-129">다른 전역 위치에 있는 분석가에게는 이제 해당 국가별 설정에 따라 끝점용 Microsoft Defender 경고가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="506eb-129">Analysts located in different global locations will now see the Microsoft Defender for Endpoint alerts according to their regional settings.</span></span>

<span data-ttu-id="506eb-130">분석가가 단일 위치에 있는 경우 현지 시간을 사용하기로 선택하는 것이 유용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="506eb-130">Choosing to use local time can be useful if the analysts are located in a single location.</span></span> <span data-ttu-id="506eb-131">이 경우 로컬 사용자가 의심스러운 전자 메일 링크를 클릭한 경우와 같은 현지 시간으로 이벤트를 보다 쉽게 상관 관계화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="506eb-131">In this case it might be easier to correlate events to local time, for example – when a local user clicked on a suspicious email link.</span></span>

### <a name="set-the-time-zone"></a><span data-ttu-id="506eb-132">표준 시간대 설정</span><span class="sxs-lookup"><span data-stu-id="506eb-132">Set the time zone</span></span>
<span data-ttu-id="506eb-133">끝점용 Microsoft Defender 표준 시간대는 기본적으로 UTC로 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="506eb-133">The Microsoft Defender for Endpoint time zone is set by default to UTC.</span></span>
<span data-ttu-id="506eb-134">표준 시간대를 설정하면 모든 끝점 보기에 대한 Microsoft Defender의 시간도 변경됩니다.</span><span class="sxs-lookup"><span data-stu-id="506eb-134">Setting the time zone also changes the times for all Microsoft Defender for Endpoint views.</span></span>
<span data-ttu-id="506eb-135">표준 시간대를 설정하는 경우:</span><span class="sxs-lookup"><span data-stu-id="506eb-135">To set the time zone:</span></span>

1. <span data-ttu-id="506eb-136">표준 시간대 **메뉴** 표준 시간대 ![ 설정 아이콘3을 ](images/atp-time-zone.png) 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="506eb-136">Click the **Time zone** menu ![Time zone settings icon3](images/atp-time-zone.png).</span></span>
2. <span data-ttu-id="506eb-137">**Timezone UTC indicator(시간 표시기)를** 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="506eb-137">Select the **Timezone UTC** indicator.</span></span>
3. <span data-ttu-id="506eb-138">표준 **시간대 UTC** 또는 로컬 표준 시간대(예: -7:00)를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="506eb-138">Select **Timezone UTC** or your local time zone, for example -7:00.</span></span>

### <a name="regional-settings"></a><span data-ttu-id="506eb-139">국가별 설정</span><span class="sxs-lookup"><span data-stu-id="506eb-139">Regional settings</span></span>
<span data-ttu-id="506eb-140">끝점용 Microsoft Defender에 다른 날짜 형식을 적용하려면 IE(Internet Explorer) 및 Microsoft Edge(Edge)에 대한 국가별 설정을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="506eb-140">To apply different date formats for Microsoft Defender for Endpoint, use regional settings for Internet Explorer (IE) and Microsoft Edge (Edge).</span></span> <span data-ttu-id="506eb-141">Google Chrome과 같은 다른 브라우저를 사용하는 경우 필요한 단계에 따라 해당 브라우저의 시간 및 날짜 설정을 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="506eb-141">If you're using another browser such as Google Chrome, follow the required steps to change the time and date settings for that browser.</span></span> 


<span data-ttu-id="506eb-142">**Internet Explorer(IE) 및 Microsoft Edge**</span><span class="sxs-lookup"><span data-stu-id="506eb-142">**Internet Explorer (IE) and Microsoft Edge**</span></span>

<span data-ttu-id="506eb-143">IE 및 Microsoft  Edge는 제어판의 **시계,** 언어 및 지역 옵션에 구성된 지역 설정을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="506eb-143">IE and Microsoft Edge use the **Region** settings configured in the **Clocks, Language, and Region** option in the Control panel.</span></span> 


#### <a name="known-issues-with-regional-formats"></a><span data-ttu-id="506eb-144">지역별 형식의 알려진 문제</span><span class="sxs-lookup"><span data-stu-id="506eb-144">Known issues with regional formats</span></span>

<span data-ttu-id="506eb-145">**날짜 및 시간 형식**</span><span class="sxs-lookup"><span data-stu-id="506eb-145">**Date and time formats**</span></span><br>
<span data-ttu-id="506eb-146">시간 및 날짜 형식에 몇 가지 알려진 문제가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="506eb-146">There are some known issues with the time and date formats.</span></span> <span data-ttu-id="506eb-147">지원되는 형식이 아닌 다른 형식으로 국가별 설정을 구성하는 경우 포털에 설정이 올바르게 반영되지 않을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="506eb-147">If you configure your regional settings to anything other than the supported formats, the portal may not correctly reflect your settings.</span></span>

<span data-ttu-id="506eb-148">다음 날짜 및 시간 형식이 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="506eb-148">The following date and time formats are supported:</span></span>
- <span data-ttu-id="506eb-149">날짜 형식 MM/dd/yyyy</span><span class="sxs-lookup"><span data-stu-id="506eb-149">Date format MM/dd/yyyy</span></span>
- <span data-ttu-id="506eb-150">날짜 형식 dd/MM/yyyy</span><span class="sxs-lookup"><span data-stu-id="506eb-150">Date format dd/MM/yyyy</span></span>
- <span data-ttu-id="506eb-151">시간 형식 hh:mm:ss(12시간 형식)</span><span class="sxs-lookup"><span data-stu-id="506eb-151">Time format hh:mm:ss (12 hour format)</span></span>

<span data-ttu-id="506eb-152">다음 날짜 및 시간 형식은 현재 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="506eb-152">The following date and time formats are currently not supported:</span></span>
- <span data-ttu-id="506eb-153">날짜 형식 yyyy-MM-dd</span><span class="sxs-lookup"><span data-stu-id="506eb-153">Date format yyyy-MM-dd</span></span>
- <span data-ttu-id="506eb-154">날짜 형식 dd-MMM-yy</span><span class="sxs-lookup"><span data-stu-id="506eb-154">Date format dd-MMM-yy</span></span>
- <span data-ttu-id="506eb-155">날짜 형식 dd/MM/yy</span><span class="sxs-lookup"><span data-stu-id="506eb-155">Date format dd/MM/yy</span></span>
- <span data-ttu-id="506eb-156">날짜 형식 MM/dd/yy</span><span class="sxs-lookup"><span data-stu-id="506eb-156">Date format MM/dd/yy</span></span>
- <span data-ttu-id="506eb-157">날짜 형식(yy)</span><span class="sxs-lookup"><span data-stu-id="506eb-157">Date format with yy.</span></span> <span data-ttu-id="506eb-158">yyyy만 표시</span><span class="sxs-lookup"><span data-stu-id="506eb-158">Will only show yyyy.</span></span>
- <span data-ttu-id="506eb-159">시간 형식 HH:mm:ss(24시간 형식)</span><span class="sxs-lookup"><span data-stu-id="506eb-159">Time format HH:mm:ss (24 hour format)</span></span>

<span data-ttu-id="506eb-160">**숫자에 사용되는 소수 기호**</span><span class="sxs-lookup"><span data-stu-id="506eb-160">**Decimal symbol used in numbers**</span></span><br>
<span data-ttu-id="506eb-161">사용되는 소수점 기호는 지역 설정의 숫자 형식 설정에서 콤보가 선택되어 있는 경우에도 항상 **점입니다.** </span><span class="sxs-lookup"><span data-stu-id="506eb-161">Decimal symbol used is always a dot, even if a comma is selected in  the **Numbers** format settings in **Region** settings.</span></span> <span data-ttu-id="506eb-162">예를 들어 15,5K는 15.5K로 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="506eb-162">For example, 15,5K is displayed as 15.5K.</span></span>


