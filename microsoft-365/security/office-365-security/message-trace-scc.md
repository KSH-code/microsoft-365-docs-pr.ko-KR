---
title: 보안 및 준수 센터의 메시지 추적
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: how-to
localization_priority: Normal
ms.assetid: 3e64f99d-ac33-4aba-91c5-9cb4ca476803
ms.custom:
- seo-marvel-apr2020
description: 관리자는 보안 및 준수 센터에서 메시지 추적을 & 메시지에 대해 어떤 일이 벌어졌다는 것을 알 수 있습니다.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 587e111a71b321c131d0e63a0510ec7e1afa289a
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/19/2021
ms.locfileid: "50929399"
---
# <a name="message-trace-in-the-security--compliance-center"></a><span data-ttu-id="fee88-103">보안 및 준수 센터의 메시지 추적</span><span class="sxs-lookup"><span data-stu-id="fee88-103">Message trace in the Security & Compliance Center</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="fee88-104">**적용 대상**</span><span class="sxs-lookup"><span data-stu-id="fee88-104">**Applies to**</span></span>
- [<span data-ttu-id="fee88-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="fee88-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="fee88-106">Office 365용 Microsoft Defender 플랜 1 및 플랜 2</span><span class="sxs-lookup"><span data-stu-id="fee88-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](office-365-atp.md)
- [<span data-ttu-id="fee88-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="fee88-107">Microsoft 365 Defender</span></span>](../mtp/microsoft-threat-protection.md)

## <a name="message-trace-features"></a><span data-ttu-id="fee88-108">메시지 추적 기능</span><span class="sxs-lookup"><span data-stu-id="fee88-108">Message trace features</span></span>

<span data-ttu-id="fee88-109">보안 및 준수 & 메시지 추적은 Exchange Online 조직을 통과하는 전자 메일 메시지를 추적합니다.</span><span class="sxs-lookup"><span data-stu-id="fee88-109">Message trace in the Security & Compliance Center follows email messages as they travel through your Exchange Online organization.</span></span> <span data-ttu-id="fee88-110">서비스에서 메시지를 수신, 거부, 지연 또는 배달할지 여부를 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fee88-110">You can determine if a message was received, rejected, deferred, or delivered by the service.</span></span> <span data-ttu-id="fee88-111">또한 최종 상태에 도달하기 전에 메시지에 대해 수행된 작업도 보여 주며,</span><span class="sxs-lookup"><span data-stu-id="fee88-111">It also shows what actions were taken on the message before it reached its final status.</span></span>

<span data-ttu-id="fee88-112">보안 및 준수 & 메시지 추적은 EAC(Exchange 관리 센터)에서 사용할 수 있는 원래 메시지 추적을 개선합니다.</span><span class="sxs-lookup"><span data-stu-id="fee88-112">Message trace in the Security & Compliance Center improves upon the original message trace that was available in the Exchange admin center (EAC).</span></span> <span data-ttu-id="fee88-113">메시지 추적의 정보를 사용하여 메시지에 대해 진행된 문제에 대한 사용자 질문에 효율적으로 답변하고, 메일 흐름 문제를 해결하고, 정책 변경의 유효성을 검사할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fee88-113">You can use the information from message trace to efficiently answer user questions about what happened to messages, troubleshoot mail flow issues, and validate policy changes.</span></span>

> [!NOTE]
>
> - <span data-ttu-id="fee88-114">메시지 추적을 사용하려면 조직 관리, 규정 준수 관리 또는 Help Desk 역할 그룹의 구성원이 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="fee88-114">To do a message trace, you need to be a member of the Organization Management, Compliance Management or Help Desk role groups.</span></span> <span data-ttu-id="fee88-115">자세한 내용은 [보안 및 준수 센터의 사용 권한](permissions-in-the-security-and-compliance-center.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="fee88-115">For more information, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>
>
> - <span data-ttu-id="fee88-116">결과에 표시되는 최대 메시지 수는 선택한 보고서 유형에 따라 다릅니다(자세한 [](#choose-report-type) 내용은 보고서 유형 선택 섹션 참조).</span><span class="sxs-lookup"><span data-stu-id="fee88-116">The maximum number of messages that are displayed in the results depends on the report type you selected (see the [Choose report type](#choose-report-type) section for details).</span></span> <span data-ttu-id="fee88-117">Exchange Online PowerShell 또는 독립 실행형 EOP PowerShell의 [Get-HistoricalSearch](/powershell/module/exchange/get-historicalsearch) cmdlet은 결과에 모든 메시지를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="fee88-117">The [Get-HistoricalSearch](/powershell/module/exchange/get-historicalsearch) cmdlet in Exchange Online PowerShell or standalone EOP PowerShell returns all messages in the results.</span></span>

## <a name="open-message-trace"></a><span data-ttu-id="fee88-118">메시지 추적 열기</span><span class="sxs-lookup"><span data-stu-id="fee88-118">Open message trace</span></span>

1. <span data-ttu-id="fee88-119">에서 보안 & 준수 센터를 열 수 <https://protection.office.com> 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fee88-119">Open the Security & Compliance Center at <https://protection.office.com>.</span></span>

2. <span data-ttu-id="fee88-120">메일 **흐름을 확장한** 다음 메시지 추적 **을 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="fee88-120">Expand **Mail flow**, and then select **Message trace**.</span></span>

## <a name="message-trace-page"></a><span data-ttu-id="fee88-121">메시지 추적 페이지</span><span class="sxs-lookup"><span data-stu-id="fee88-121">Message trace page</span></span>

<span data-ttu-id="fee88-122">여기에서 추적 시작 단추를 클릭하여 새 기본 **추적을 시작할 수** 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fee88-122">From here you can start a new default trace by clicking on the **Start a trace** button.</span></span> <span data-ttu-id="fee88-123">이렇게 하면 지난 2일 동안의 모든 보낸 사람 및 받는 사람에 대한 모든 메시지가 검색됩니다.</span><span class="sxs-lookup"><span data-stu-id="fee88-123">This will search for all messages for all senders and recipients for the last two days.</span></span> <span data-ttu-id="fee88-124">또는 사용 가능한 쿼리 범주에서 저장된 쿼리 중 하나를 사용하여 현재 쿼리를 실행하거나 자체 쿼리의 시작점으로 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fee88-124">Or you can use one of the stored queries from the available query categories and either run them as-is or use them as starting points for your own queries:</span></span>

- <span data-ttu-id="fee88-125">**기본 쿼리:** Microsoft 365에서 제공하는 기본 제공 쿼리입니다.</span><span class="sxs-lookup"><span data-stu-id="fee88-125">**Default queries**: Built-in queries provided by Microsoft 365.</span></span>

- <span data-ttu-id="fee88-126">**사용자 지정 쿼리:** 향후 사용을 위해 조직의 관리자가 저장한 쿼리입니다.</span><span class="sxs-lookup"><span data-stu-id="fee88-126">**Custom queries**: Queries saved by admins in your organization for future use.</span></span>

- <span data-ttu-id="fee88-127">**자동 검색 쿼리:** 최근 10개가 실행된 쿼리입니다.</span><span class="sxs-lookup"><span data-stu-id="fee88-127">**Autosaved queries**: The last ten most recently run queries.</span></span> <span data-ttu-id="fee88-128">이 목록을 사용하면 벗어났을 때 쉽게 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fee88-128">This list makes it simple to pick up where you left off.</span></span>

<span data-ttu-id="fee88-129">또한 이 페이지에는  제출한 요청에 대한 다운로드 가능한 보고서 섹션과 다운로드 가능한 보고서가 있는 경우 보고서 자체도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fee88-129">Also on this page is a **Downloadable reports** section for the requests you've submitted, as well as the reports themselves when they're are available for download.</span></span>

## <a name="options-for-a-new-message-trace"></a><span data-ttu-id="fee88-130">새 메시지 추적에 대한 옵션</span><span class="sxs-lookup"><span data-stu-id="fee88-130">Options for a new message trace</span></span>

### <a name="filter-by-senders-and-recipients"></a><span data-ttu-id="fee88-131">보낸 사람 및 받는 사람에 따라 필터링</span><span class="sxs-lookup"><span data-stu-id="fee88-131">Filter by senders and recipients</span></span>

<span data-ttu-id="fee88-132">기본값은 **모든** 보낸 사람 및 모든 받는 사람이지만 다음 필드를 사용하여 결과를 필터링할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fee88-132">The default values are **All senders** and **All recipients**, but you can use the following fields to filter the results:</span></span>

- <span data-ttu-id="fee88-133">**사용자:** 이 필드를 클릭하여 조직에서 보낸 사람 한명 이상을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="fee88-133">**By these people**: Click in this field to select one or more senders from your organization.</span></span> <span data-ttu-id="fee88-134">또한 이름을 입력하기 시작하면 검색 페이지가 어떻게 행동하는지와 마찬가지로 목록의 항목이 입력한 항목별로 필터링됩니다.</span><span class="sxs-lookup"><span data-stu-id="fee88-134">You can also start to type a name and the items in the list will be filtered by what you've typed, much like how a search page behaves.</span></span>

- <span data-ttu-id="fee88-135">**받는 사람:** 이 필드를 클릭하여 조직에서 하나 이상의 받는 사람을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="fee88-135">**To these people**: Click in this field to select one or more recipients in your organization.</span></span>

> [!NOTE]
>
> - <span data-ttu-id="fee88-136">외부 보낸 사람 및 받는 사람의 전자 메일 주소를 입력할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fee88-136">You can also type the email addresses of external senders and recipients.</span></span> <span data-ttu-id="fee88-137">와일드카드는 지원되지만(예: ) 같은 필드에 여러 와일드카드 항목을 동시에 사용할 `*@contoso.com` 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="fee88-137">Wildcards are supported (for example, `*@contoso.com`), but you can't use multiple wildcard entries in the same field at the same time.</span></span>
>
> - <span data-ttu-id="fee88-138">여러 보낸 사람 또는 받는 사람 목록을 세미코론()으로 구분하여 붙여넣을 수 `;` 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fee88-138">You can paste multiple senders or recipients lists separated by semicolons (`;`).</span></span> <span data-ttu-id="fee88-139">공백( `\s` ), 캐리지 리턴( `\r` ) 또는 다음 `\n` 줄()을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="fee88-139">spaces (`\s`), carriage returns (`\r`), or next lines (`\n`).</span></span>

### <a name="time-range"></a><span data-ttu-id="fee88-140">시간 범위</span><span class="sxs-lookup"><span data-stu-id="fee88-140">Time range</span></span>

<span data-ttu-id="fee88-141">기본값은 **2일이지만** 날짜/시간 범위를 최대 90일로 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fee88-141">The default value is **2 days**, but you can specify date/time ranges of up to 90 days.</span></span> <span data-ttu-id="fee88-142">날짜/시간 범위를 사용하는 경우 다음 문제를 고려합니다.</span><span class="sxs-lookup"><span data-stu-id="fee88-142">When you use date/time ranges, consider these issues:</span></span>

- <span data-ttu-id="fee88-143">기본적으로 시간 줄을 사용하여 **슬라이더** 보기에서 시간 범위를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="fee88-143">By default, you select the time range in **Slider** view using a time line.</span></span> <span data-ttu-id="fee88-144">표시되는 일 또는 시간 설정만 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fee88-144">You can only select the day or time settings that are displayed.</span></span> <span data-ttu-id="fee88-145">사이 값을 선택하려고 하면 시작/끝 거품이 가장 가까운 표시된 설정에 맞추게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="fee88-145">Trying to select an in-between value will snap the start/end bubble to the nearest displayed setting.</span></span>

  ![보안 및 준수 센터의 새 메시지 추적에 있는 & 시간 범위](../../media/55a9e9c1-f7d5-4047-b217-824e8b976bcb.png)

  <span data-ttu-id="fee88-147">그러나 시작 날짜 및  종료 날짜 값(시간 포함)을 지정할 수 있는 사용자 지정  보기로 전환할 수도 있으며, 날짜/시간 범위의 표준 시간대를 선택할 수도 있습니다.  </span><span class="sxs-lookup"><span data-stu-id="fee88-147">But, you can also switch to **Custom** view where you can specify the **Start date** and **End date** values (including times), and you can also select the **Time zone** for the date/time range.</span></span> <span data-ttu-id="fee88-148">표준 시간대 **설정은** 쿼리 입력과 쿼리 결과에 모두 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="fee88-148">Note that the **Time zone** setting applies to both your query inputs and your query results.</span></span>

  ![보안 및 준수 센터의 새 메시지 추적에 & 시간 범위](../../media/ed4c8d50-9ea5-4694-93f9-ee3ab6660b4f.png)

  <span data-ttu-id="fee88-150">10일 이하의 경우 결과를 요약 보고서로 즉시 사용할 **수** 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fee88-150">For 10 days or less, the results are available instantly as a **Summary** report.</span></span> <span data-ttu-id="fee88-151">10일보다 약간 더 큰 시간 범위를 지정하면 다운로드 가능한 CSV 파일(확장된 요약 또는 확장  보고서)로만  사용할 수 있는 결과가 지연됩니다.</span><span class="sxs-lookup"><span data-stu-id="fee88-151">If you specify a time range that's even slightly greater than 10 days, the results will be delayed as they are only available as a downloadable CSV file ( **Enhanced summary** or **Extended** reports).</span></span>

  <span data-ttu-id="fee88-152">다양한 보고서 유형에 대한 자세한 내용은 이 문서의 보고서 유형 선택 [섹션을](#choose-report-type) 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="fee88-152">For more information about the different report types, see the [Choose report type](#choose-report-type) section in this article.</span></span>

  > [!NOTE]
  > <span data-ttu-id="fee88-153">향상된 요약 및 확장된 보고서는 보관된 메시지 추적 데이터를 사용하여 준비됩니다. 보고서를 다운로드할 수 있는 데 최대 몇 시간이 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fee88-153">Enhanced summary and Extended reports are prepared using archived message trace data, and it can take up to several hours before your report is available for download.</span></span> <span data-ttu-id="fee88-154">동시에 보고서 요청을 제출한 다른 관리자의 수에 따라 대기 중인 요청에 대한 처리가 시작되기 전에 지연이 확인될 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fee88-154">Depending on how many other admins have also submitted report requests around the same time, you might also notice a delay before processing starts for your queued request.</span></span>

- <span data-ttu-id="fee88-155">쿼리를 **슬라이더** 보기에 저장하면 상대 시간 범위(예: 오늘부터 3일)가 절약됩니다.</span><span class="sxs-lookup"><span data-stu-id="fee88-155">Saving a query in **Slider** view saves the relative time range (for example, 3 days from today).</span></span> <span data-ttu-id="fee88-156">쿼리를 **사용자** 지정 보기에 저장하면 절대 날짜/시간 범위가 저장됩니다(예: 2018-05-06 13:00 ~ 2018-05-08 18:00).</span><span class="sxs-lookup"><span data-stu-id="fee88-156">Saving a query in **Custom** view saves the absolute date/time range (for example, 2018-05-06 13:00 to 2018-05-08 18:00).</span></span>

### <a name="more-search-options"></a><span data-ttu-id="fee88-157">추가 검색 옵션</span><span class="sxs-lookup"><span data-stu-id="fee88-157">More search options</span></span>

#### <a name="delivery-status"></a><span data-ttu-id="fee88-158">배달 상태</span><span class="sxs-lookup"><span data-stu-id="fee88-158">Delivery status</span></span>

<span data-ttu-id="fee88-159">기본값 모두를 **선택된** 그대로 두거나 다음 값 중 하나를 선택하여 결과를 필터링할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fee88-159">You can leave the default value **All** selected, or you can select one of the following values to filter the results:</span></span>

- <span data-ttu-id="fee88-160">**배달된** 메시지: 메시지가 의도한 대상에 배달된 경우</span><span class="sxs-lookup"><span data-stu-id="fee88-160">**Delivered**: The message was successfully delivered to the intended destination.</span></span>

- <span data-ttu-id="fee88-161">**보류 중:** 메시지 배달을 시도하거나 다시 시도 중입니다.</span><span class="sxs-lookup"><span data-stu-id="fee88-161">**Pending**: Delivery of the message is being attempted or re-attempted.</span></span>

- <span data-ttu-id="fee88-162">**확장:** 그룹의 개별 구성원에게 배달하기 전에 메일 그룹 받는 사람이 확장됩니다.</span><span class="sxs-lookup"><span data-stu-id="fee88-162">**Expanded**: A distribution group recipient was expanded before delivery to the individual members of the group.</span></span>

- <span data-ttu-id="fee88-163">**실패:** 메시지가 배달되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="fee88-163">**Failed**: The message was not delivered.</span></span>

- <span data-ttu-id="fee88-164">**Quarantined**: 메시지가 스팸, 대량 메일 또는 피싱으로 확인되었습니다.</span><span class="sxs-lookup"><span data-stu-id="fee88-164">**Quarantined**: The message was quarantined (as spam, bulk mail, or phishing).</span></span> <span data-ttu-id="fee88-165">자세한 내용은 [EOP에서 Quarantined email messages를 참조하세요.](quarantine-email-messages.md)</span><span class="sxs-lookup"><span data-stu-id="fee88-165">For more information, see [Quarantined email messages in EOP](quarantine-email-messages.md).</span></span>

- <span data-ttu-id="fee88-166">**스팸으로 필터링:** 메시지가 스팸으로 식별되어 거부되거나 차단되었습니다(고지되지 않은 경우).</span><span class="sxs-lookup"><span data-stu-id="fee88-166">**Filtered as spam**: The message was identified spam, and was rejected or blocked (not quarantined).</span></span>

- <span data-ttu-id="fee88-167">**상태 확인:** 메시지는 최근에 Microsoft 365에서 수신했지만 다른 상태 데이터를 아직 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="fee88-167">**Getting status:** The message was recently received by Microsoft 365, but no other status data is yet available.</span></span> <span data-ttu-id="fee88-168">몇 분 후에 다시 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="fee88-168">Check back in a few minutes.</span></span>

> [!NOTE]
> <span data-ttu-id="fee88-169">**Pending,** **Quarantined** 및 **Filter as spam** 값은 10일 미만의 검색에만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fee88-169">The values **Pending,** **Quarantined**, and **Filter as spam** are only available for searches less than 10 days.</span></span> <span data-ttu-id="fee88-170">또한 실제 상태와 보고된 배달 상태 간에는 5~10분이 지연될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fee88-170">Also, there might be a 5 to 10 minute delay between the actual and reported delivery status.</span></span>

#### <a name="message-id"></a><span data-ttu-id="fee88-171">메시지 ID</span><span class="sxs-lookup"><span data-stu-id="fee88-171">Message ID</span></span>

<span data-ttu-id="fee88-172">이 ID는 메시지 헤더의 **Message-ID:** 헤더 필드에 있는 인터넷 메시지 ID(클라이언트 ID라고도 합니다.</span><span class="sxs-lookup"><span data-stu-id="fee88-172">This is the internet message ID (also known as the Client ID) that's found in the **Message-ID:** header field in the message header.</span></span> <span data-ttu-id="fee88-173">사용자는 이 값을 제공하여 특정 메시지를 조사할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fee88-173">Users can give you this value to investigate specific messages.</span></span>

<span data-ttu-id="fee88-174">이 값은 메시지 수명을 나타내는 상수입니다.</span><span class="sxs-lookup"><span data-stu-id="fee88-174">This value is constant for the lifetime of the message.</span></span> <span data-ttu-id="fee88-175">Microsoft 365 또는 Exchange에서 만든 메시지의 경우 값은 형식입니다(앵글 `<GUID@ServerFQDN>` 괄호( \< \> ).</span><span class="sxs-lookup"><span data-stu-id="fee88-175">For messages created in Microsoft 365 or Exchange, the value is in the format `<GUID@ServerFQDN>`, including the angle brackets (\< \>).</span></span> <span data-ttu-id="fee88-176">예를 들면 `<d9683b4c-127b-413a-ae2e-fa7dfb32c69d@DM3NAM06BG401.Eop-nam06.prod.protection.outlook.com>`와 같습니다.</span><span class="sxs-lookup"><span data-stu-id="fee88-176">For example, `<d9683b4c-127b-413a-ae2e-fa7dfb32c69d@DM3NAM06BG401.Eop-nam06.prod.protection.outlook.com>`.</span></span> <span data-ttu-id="fee88-177">다른 메시징 시스템에서는 다른 구문이나 값을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fee88-177">Other messaging systems might use different syntax or values.</span></span> <span data-ttu-id="fee88-178">이 값은 고유해야 하지만 모든 전자 메일 시스템이 이 요구 사항을 엄격하게 따르는 것은 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="fee88-178">This value is supposed to be unique, but not all email systems strictly follow this requirement.</span></span> <span data-ttu-id="fee88-179">**Message-ID:** 헤더 필드가 존재하지 않는 경우 또는 외부 원본에서 들어오는 메시지에 대해 비어 있으면 임의의 값이 할당됩니다.</span><span class="sxs-lookup"><span data-stu-id="fee88-179">If the **Message-ID:** header field doesn't exist or is blank for incoming messages from external sources, an arbitrary value is assigned.</span></span>

<span data-ttu-id="fee88-180">메시지 **ID를** 사용하여 결과를 필터링하는 경우 괄호를 포함하여 전체 문자열을 포함해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="fee88-180">When you use **Message ID** to filter the results, be sure to include the full string, including any angle brackets.</span></span>

#### <a name="direction"></a><span data-ttu-id="fee88-181">Direction</span><span class="sxs-lookup"><span data-stu-id="fee88-181">Direction</span></span>

<span data-ttu-id="fee88-182">기본값 모두를 선택된 그대로 두거나  인바운드(조직의 받는 사람에게 보낸 메시지) 또는  아웃바운드(조직의 사용자가 보낸 메시지)를 선택하여 결과를 필터링할 수 있습니다. </span><span class="sxs-lookup"><span data-stu-id="fee88-182">You can leave the default value **All** selected, or you can select **Inbound** (messages sent to recipients in your organization) or **Outbound** (messages sent from users in your organization) to filter the results.</span></span>

#### <a name="original-client-ip-address"></a><span data-ttu-id="fee88-183">원래 클라이언트 IP 주소</span><span class="sxs-lookup"><span data-stu-id="fee88-183">Original client IP address</span></span>

<span data-ttu-id="fee88-184">클라이언트 IP 주소로 결과를 제출하여 많은 양의 스팸 또는 맬웨어를 전송하는 해킹된 컴퓨터를 조사할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fee88-184">You can filer the results by client IP address to investigate hacked computers that are sending large amounts of spam or malware.</span></span> <span data-ttu-id="fee88-185">메시지가 보낸 사람이 여러 명인 것 같지만 같은 컴퓨터에서 모든 메시지를 생성하고 있을 가능성이 습니다.</span><span class="sxs-lookup"><span data-stu-id="fee88-185">Although the messages might appear to come from multiple senders, it's likely that the same computer is generating all of the messages.</span></span>

> [!NOTE]
> <span data-ttu-id="fee88-186">클라이언트 IP 주소 정보는 10일 동안만 사용할 수  있으며 고급 요약  또는 확장 보고서(다운로드 가능한 CSV 파일)에서만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fee88-186">The client IP address information is only available for 10 days, and is only available in the **Enhanced summary** or **Extended** reports (downloadable CSV files).</span></span>

### <a name="choose-report-type"></a><span data-ttu-id="fee88-187">보고서 유형 선택</span><span class="sxs-lookup"><span data-stu-id="fee88-187">Choose report type</span></span>

<span data-ttu-id="fee88-188">사용 가능한 보고서 유형은 다음입니다.</span><span class="sxs-lookup"><span data-stu-id="fee88-188">The available report types are:</span></span>

- <span data-ttu-id="fee88-189">**요약:** 시간 범위가 10일 미만으로 추가 필터링 옵션이 필요 없는 경우 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fee88-189">**Summary**: Available if the time range is less than 10 days, and requires no additional filtering options.</span></span> <span data-ttu-id="fee88-190">검색을 클릭한 직후에 결과를 사용할 수 **있습니다.**</span><span class="sxs-lookup"><span data-stu-id="fee88-190">The results are available almost immediately after you click **Search**.</span></span> <span data-ttu-id="fee88-191">보고서는 최대 20000개 결과를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="fee88-191">The report returns up to 20000 results.</span></span>

- <span data-ttu-id="fee88-192">**확장된** 요약 또는 **확장:** 이러한 보고서는 다운로드 가능한 CSV 파일로만 사용할 수 있으며 시간 범위에 관계없이 하나 이상의 필터링 옵션이 필요 **합니다.** 이러한 사용자에 의해 **,** 다음 사용자 또는 메시지 **ID**.</span><span class="sxs-lookup"><span data-stu-id="fee88-192">**Enhanced summary** or **Extended**: These reports are only available as downloadable CSV files, and require one or more of the following filtering options regardless of the time range: **By these people**, **To these people**, or **Message ID**.</span></span> <span data-ttu-id="fee88-193">보낸 사람 또는 받는 사람에 대해 와일드카드를 사용할 수 \* 있습니다(예: @contoso.com).</span><span class="sxs-lookup"><span data-stu-id="fee88-193">You can use wildcards for the senders or the recipients (for example, \*@contoso.com).</span></span> <span data-ttu-id="fee88-194">고급 요약 보고서는 최대 50000개 결과를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="fee88-194">The Enhanced summary report returns up to 50000 results.</span></span> <span data-ttu-id="fee88-195">Extended 보고서는 최대 1,000개 결과를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="fee88-195">The Extended report returns up to 1000 results.</span></span>

> [!NOTE]
>
> - <span data-ttu-id="fee88-196">향상된 요약 및 확장된 보고서는 보관된 메시지 추적 데이터를 사용하여 준비됩니다. 보고서를 다운로드할 수 있는 데 최대 몇 시간이 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fee88-196">Enhanced summary and Extended reports are prepared using archived message trace data, and it can take up to several hours before your report is available to download.</span></span> <span data-ttu-id="fee88-197">동시에 보고서 요청을 제출한 다른 관리자의 수에 따라 대기 중인 요청이 처리되기 전에 지연이 확인될 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fee88-197">Depending on how many other admins have also submitted report requests around the same time, you might also notice a delay before your queued request starts to be processed.</span></span>
>
> - <span data-ttu-id="fee88-198">날짜/시간 범위에 대해 고급 요약 또는 확장 보고서를 선택할 수 있는 반면 일반적으로 보관된 데이터의 최근 4시간은 이러한 두 가지 유형의 보고서에 아직 제공되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="fee88-198">While you can select an Enhanced summary or Extended report for any date/time range, commonly the last four hours of archived data will not yet be available for these two types of reports.</span></span>
>
> - <span data-ttu-id="fee88-199">다운로드 가능한 보고서의 최대 크기는 500MB입니다.</span><span class="sxs-lookup"><span data-stu-id="fee88-199">The maximum size for a downloadable report is 500 MB.</span></span> <span data-ttu-id="fee88-200">다운로드 가능한 보고서가 500MB를 초과하면 Excel 또는 메모장에서 보고서를 열 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="fee88-200">If a downloadable report exceeds 500 MB, you can't open the report in Excel or Notepad.</span></span>

<span data-ttu-id="fee88-201">다음을 클릭하면 선택한 필터링 옵션, 보고서의 고유한 제목(편집 가능) 제목 및 메시지 추적이 완료될 때 알림을 받는 전자 메일 주소(편집 가능하고 조직의 허용 도메인 중 하나에 있어야 합니다)가 나열되는 요약 페이지가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="fee88-201">When you click **Next**, you're presented with a summary page that lists the filtering options that you selected, a unique (editable) title for the report, and the email address that receives the notification when the message trace completes (also editable, and must be in one of your organization's accepted domains).</span></span> <span data-ttu-id="fee88-202">보고서 **준비를** 클릭하여 메시지 추적을 제출합니다.</span><span class="sxs-lookup"><span data-stu-id="fee88-202">Click **Prepare report** to submit the message trace.</span></span> <span data-ttu-id="fee88-203">기본 메시지 추적 **페이지에서** 다운로드 가능한 보고서 섹션에서 보고서의 **상태를 확인할 수** 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fee88-203">On the main **Message trace** page, you can see the status of the report in the **Downloadable reports** section.</span></span>

<span data-ttu-id="fee88-204">다양한 보고서 유형에서 반환되는 정보에 대한 자세한 내용은 다음 섹션을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="fee88-204">For more information about the information that's returned in the different report types, see the next section.</span></span>

## <a name="message-trace-results"></a><span data-ttu-id="fee88-205">메시지 추적 결과</span><span class="sxs-lookup"><span data-stu-id="fee88-205">Message trace results</span></span>

<span data-ttu-id="fee88-206">각 보고서 유형은 서로 다른 수준의 정보를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="fee88-206">The different report types return different levels of information.</span></span> <span data-ttu-id="fee88-207">다양한 보고서에서 사용할 수 있는 정보는 다음 섹션에 설명되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fee88-207">The information that's available in the different reports is described in the following sections.</span></span>

### <a name="summary-report-output"></a><span data-ttu-id="fee88-208">요약 보고서 출력</span><span class="sxs-lookup"><span data-stu-id="fee88-208">Summary report output</span></span>

<span data-ttu-id="fee88-209">메시지 추적을 실행하고 나면 결과가 나열되고, 내선 날짜/시간(가장 최근에 먼저)별로 정렬됩니다.</span><span class="sxs-lookup"><span data-stu-id="fee88-209">After running the message trace, the results will be listed, sorted by descending date/time (most recent first).</span></span>

![보안 및 준수 센터의 메시지 추적에 대한 & 보고서 결과](../../media/0664bafe-0b03-477b-b571-0b046ac8c977.png)

<span data-ttu-id="fee88-211">요약 보고서에는 다음 정보가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fee88-211">The summary report contains the following information:</span></span>

- <span data-ttu-id="fee88-212">**날짜:** 구성된 UTC 표준 시간대를 사용하여 서비스에서 메시지를 받은 날짜 및 시간입니다.</span><span class="sxs-lookup"><span data-stu-id="fee88-212">**Date**: The date and time at which the message was received by the service, using the configured UTC time zone.</span></span>

- <span data-ttu-id="fee88-213">**보낸 사람**: 보낸 사람(별칭 도메인)의 *전자 메일* @ *주소입니다.*</span><span class="sxs-lookup"><span data-stu-id="fee88-213">**Sender**: The email address of the sender (*alias*@*domain*).</span></span>

- <span data-ttu-id="fee88-214">**받는** 사람: 받는 사람 또는 받는 사람의 전자 메일 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="fee88-214">**Recipient**: The email address of the recipient or recipients.</span></span> <span data-ttu-id="fee88-215">여러 받는 사람에게 보낸 메시지의 경우 받는 사람당 한 줄이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fee88-215">For a message sent to multiple recipients, there's one line per recipient.</span></span> <span data-ttu-id="fee88-216">받는 사람이 메일 그룹, 동적 메일 그룹 또는 메일 사용이 가능한 보안 그룹인 경우 그룹이 첫 번째 받는 사람이 되거나 그룹의 각 구성원이 별도의 줄에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fee88-216">If the recipient is a distribution group, dynamic distribution group, or mail-enabled security group, the group will be the first recipient, and then each member of the group is on a separate line.</span></span>

- <span data-ttu-id="fee88-217">**제목:** 메시지의 제목: 필드의 처음  256자입니다.</span><span class="sxs-lookup"><span data-stu-id="fee88-217">**Subject**: The first 256 characters of the message's **Subject:** field.</span></span>

- <span data-ttu-id="fee88-218">**상태:** 이러한 값은 배달 상태 [섹션에 설명되어](#delivery-status) 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fee88-218">**Status**: These values are described in the [Delivery status](#delivery-status) section.</span></span>

<span data-ttu-id="fee88-219">기본적으로 처음 250개 결과가 로드되어 쉽게 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fee88-219">By default, the first 250 results are loaded and readily available.</span></span> <span data-ttu-id="fee88-220">아래로 스크롤하면 다음 결과 일괄 처리가 로드될 때 약간의 일시 중지가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fee88-220">When you scroll down, there's a slight pause as the next batch of results are loaded.</span></span> <span data-ttu-id="fee88-221">스크롤하는 대신 모두 로드를  클릭하여 최대 10,000개까지 모든 결과를 로드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fee88-221">Instead of scrolling, you can click **Load all** to load all of the results up to a maximum of 10,000.</span></span>

<span data-ttu-id="fee88-222">열 헤더를 클릭하여 결과를 해당 열의 값에 따라 오차 또는 내선 순서로 정렬할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fee88-222">You can click on the column headers to sort the results by the values in that column in ascending or descending order.</span></span>

<span data-ttu-id="fee88-223">결과 **필터링을 클릭하여** 결과를 하나 이상의 열로 필터링할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fee88-223">You can click **Filter results** to filter the results by one or more columns.</span></span>

<span data-ttu-id="fee88-224">결과 내보내기, 모든 결과 내보내기, 로드된 결과  내보내기 또는 선택한 내보내기 를 선택하여 하나 이상의 행을 선택한 후 결과를 내보낼 **수 있습니다.**</span><span class="sxs-lookup"><span data-stu-id="fee88-224">You can export the results after you've selected one or more rows by clicking **Export results** and then selecting **Export all results**, **Export loaded results**, or **Export selected**.</span></span>

#### <a name="find-related-records-for-this-message"></a><span data-ttu-id="fee88-225">이 메시지에 대한 관련 레코드 찾기</span><span class="sxs-lookup"><span data-stu-id="fee88-225">Find related records for this message</span></span>

<span data-ttu-id="fee88-226">관련 메시지 레코드는 동일한 메시지 ID를 공유하는 레코드입니다.</span><span class="sxs-lookup"><span data-stu-id="fee88-226">Related message records are records that shared the same Message ID.</span></span> <span data-ttu-id="fee88-227">두 사용자 간에 전송된 단일 메시지라도 여러 레코드를 생성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fee88-227">Remember, even a single message sent between two people can generate multiple records.</span></span> <span data-ttu-id="fee88-228">메일 그룹 확장, 전달, 메일 흐름 규칙(전송 규칙) 등의 영향을 받는 경우 레코드 수가 증가합니다.</span><span class="sxs-lookup"><span data-stu-id="fee88-228">The number of records increases when the message is affected by distribution group expansion, forwarding, mail flow rules (also known as transport rules), etc.</span></span>

<span data-ttu-id="fee88-229">행의 확인란을 선택한 후 나타나는 관련 찾기 단추를 클릭하거나  기타 옵션 이 메시지에 대한  기타 관련 레코드 찾기를 선택하여 메시지에 대한 관련 레코드를 찾을 ![ 수 ](../../media/1ea52bbf-9d00-48ce-9362-307f7f6fb7fe.png) \> **있습니다.**</span><span class="sxs-lookup"><span data-stu-id="fee88-229">After you select a row's check box, you can find related records for the message by clicking the **Find related** button that appears, or by selecting **More options** ![More](../../media/1ea52bbf-9d00-48ce-9362-307f7f6fb7fe.png) \> **Find related records for this message**).</span></span>

<span data-ttu-id="fee88-230">메시지 ID에 대한 자세한 내용은 이 문서 앞부분의 메시지 ID 섹션을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="fee88-230">For more information about the Message ID, see the Message ID section earlier in this article.</span></span>

#### <a name="message-trace-details"></a><span data-ttu-id="fee88-231">메시지 추적 세부 정보</span><span class="sxs-lookup"><span data-stu-id="fee88-231">Message trace details</span></span>

<span data-ttu-id="fee88-232">요약 보고서 출력에서는 다음 방법 중 하나를 사용하여 메시지에 대한 세부 정보를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fee88-232">In the summary report output, you can view details about a message by using either of the following methods:</span></span>

- <span data-ttu-id="fee88-233">행을 선택합니다. 확인란을 제외한 행의 아무 곳이나 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="fee88-233">Select the row (click anywhere in the row except the check box).</span></span>

- <span data-ttu-id="fee88-234">행의 확인란을 선택하고 **추가 옵션 추가 메시지** 세부 정보 ![ 보기 ](../../media/1ea52bbf-9d00-48ce-9362-307f7f6fb7fe.png) \> **를 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="fee88-234">Select the row's check box and click **More options** ![More](../../media/1ea52bbf-9d00-48ce-9362-307f7f6fb7fe.png) \> **View message details**.</span></span>

   ![요약 보고서 메시지 추적 결과에서 행을 두 번 클릭한 후의 세부 정보 보안 & 준수 센터](../../media/e50ee7cd-810a-4c06-8b58-e56ffd7028d1.png)

<span data-ttu-id="fee88-236">메시지 추적 세부 정보에는 요약 보고서에 없는 다음과 같은 추가 정보가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fee88-236">The message trace details contain the following additional information that's not present in the summary report:</span></span>

- <span data-ttu-id="fee88-237">**메시지 이벤트:** 이 섹션에는 서비스에서 메시지에 대해 수행한 작업을 분류하는 데 도움이 되는 분류가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fee88-237">**Message events**: This section contains classifications that help categorize the actions that the service takes on messages.</span></span> <span data-ttu-id="fee88-238">**발생할 수 있는** 몇 가지 흥미로운 이벤트는 다음입니다.</span><span class="sxs-lookup"><span data-stu-id="fee88-238">**Some of the more interesting events** that you might encounter are:</span></span>

  - <span data-ttu-id="fee88-239">**수신:** 서비스에서 메시지를 수신했습니다.</span><span class="sxs-lookup"><span data-stu-id="fee88-239">**Receive**: The message was received by the service.</span></span>

  - <span data-ttu-id="fee88-240">**보내기**: 서비스가 메시지를 보냈습니다.</span><span class="sxs-lookup"><span data-stu-id="fee88-240">**Send**: The message was sent by the service.</span></span>

  - <span data-ttu-id="fee88-241">**실패:** 메시지를 배달하지 못했습니다.</span><span class="sxs-lookup"><span data-stu-id="fee88-241">**Fail**: The message failed to be delivered.</span></span>

  - <span data-ttu-id="fee88-242">**배달:** 메시지가 사서함에 배달된 경우</span><span class="sxs-lookup"><span data-stu-id="fee88-242">**Deliver**: The message was delivered to a mailbox.</span></span>

  - <span data-ttu-id="fee88-243">**확장:** 메시지가 확장된 메일 그룹으로 전송됩니다.</span><span class="sxs-lookup"><span data-stu-id="fee88-243">**Expand**: The message was sent to a distribution group that was expanded.</span></span>

  - <span data-ttu-id="fee88-244">**전송:** 콘텐츠 변환, 메시지 받는 사람 제한 또는 에이전트로 인하여 받는 사람이 전환된 메시지로 이동했습니다.</span><span class="sxs-lookup"><span data-stu-id="fee88-244">**Transfer**: Recipients were moved to a bifurcated message because of content conversion, message recipient limits, or agents.</span></span>

  - <span data-ttu-id="fee88-245">**지연:** 메시지 배달이 연기된 후 나중에 다시 시도할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fee88-245">**Defer**: The message delivery was postponed and might be re-attempted later.</span></span>

  - <span data-ttu-id="fee88-246">**해결된 메시지:** Active Directory 검색을 기반으로 메시지가 새 받는 사람 주소로 리디렉션되었습니다.</span><span class="sxs-lookup"><span data-stu-id="fee88-246">**Resolved**: The message was redirected to a new recipient address based on an Active Directory look up.</span></span> <span data-ttu-id="fee88-247">이 경우 원본 받는 사람 주소가 메시지 추적에 별도의 행으로 표시되고 메시지의 최종 배달 상태가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="fee88-247">When this happens, the original recipient address is listed in a separate row in the message trace along with the final delivery status for the message.</span></span>

  > [!NOTE]
  > 
  > - <span data-ttu-id="fee88-248">배달되지 않은 메시지가 배달된 경우 메시지 추적에 여러 **Event** 항목이 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="fee88-248">An uneventful message that's successfully delivered will generate multiple **Event** entries in the message trace.</span></span>
  > 
  > - <span data-ttu-id="fee88-249">이 목록은 전체 목록으로만 사용되지는 않습니다.</span><span class="sxs-lookup"><span data-stu-id="fee88-249">This list is not meant to be exhaustive.</span></span> <span data-ttu-id="fee88-250">추가 이벤트에 대한 자세한 내용은 메시지 추적 로그의 이벤트 [유형을 참조하세요.](/Exchange/mail-flow/transport-logs/message-tracking#event-types-in-the-message-tracking-log)</span><span class="sxs-lookup"><span data-stu-id="fee88-250">For descriptions of more events, see [Event types in the message tracking log](/Exchange/mail-flow/transport-logs/message-tracking#event-types-in-the-message-tracking-log).</span></span> <span data-ttu-id="fee88-251">이 링크는 Exchange Server(Exchange Server Exchange) 항목입니다.</span><span class="sxs-lookup"><span data-stu-id="fee88-251">Note that this link is an Exchange Server (on-premises Exchange) topic.</span></span>

- <span data-ttu-id="fee88-252">**추가 정보:** 이 섹션에는 다음과 같은 세부 정보가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fee88-252">**More information**: This section contains the following details:</span></span>

  - <span data-ttu-id="fee88-253">**메시지 ID:** 이 값은 이 문서 앞부분의 메시지 [ID](#message-id) 섹션에서 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="fee88-253">**Message ID**: This value is described in the [Message ID](#message-id) section earlier in this article.</span></span> <span data-ttu-id="fee88-254">예를 들면 `<d9683b4c-127b-413a-ae2e-fa7dfb32c69d@DM3NAM06BG401.Eop-nam06.prod.protection.outlook.com>`와 같습니다.</span><span class="sxs-lookup"><span data-stu-id="fee88-254">For example, `<d9683b4c-127b-413a-ae2e-fa7dfb32c69d@DM3NAM06BG401.Eop-nam06.prod.protection.outlook.com>`.</span></span>

  - <span data-ttu-id="fee88-255">**메시지 크기**   첨부 파일 등을 비롯한 메시지 크기(KB)입니다.</span><span class="sxs-lookup"><span data-stu-id="fee88-255">**Message size**</span></span>

  - <span data-ttu-id="fee88-256">**보낸 IP:** 메시지를 보낸 컴퓨터의 IP 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="fee88-256">**From IP**: The IP address of the computer that sent the message.</span></span> <span data-ttu-id="fee88-257">Exchange Online에서 전송되는 아웃바운드 메시지의 경우 이 값은 비어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fee88-257">For outbound messages sent from Exchange Online, this value is blank.</span></span>

  - <span data-ttu-id="fee88-258">**TO IP:** 서비스에서 메시지를 배달하려고 시도한 IP 주소 또는 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="fee88-258">**To IP**: The IP address or addresses where the service attempted to deliver the message.</span></span> <span data-ttu-id="fee88-259">메시지에 받는 사람이 여러 명인 경우 이러한 받는 사람이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="fee88-259">If the message has multiple recipients, these are displayed.</span></span> <span data-ttu-id="fee88-260">Exchange Online으로 전송되는 인바운드 메시지의 경우 이 값은 비어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fee88-260">For inbound messages sent to Exchange Online, this value is blank.</span></span>

### <a name="enhanced-summary-reports"></a><span data-ttu-id="fee88-261">향상된 요약 보고서</span><span class="sxs-lookup"><span data-stu-id="fee88-261">Enhanced summary reports</span></span>

<span data-ttu-id="fee88-262">사용 가능(완료) 향상된 요약 보고서는  다운로드 가능한 보고서 섹션의 시작 메시지 추적에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fee88-262">Available (completed) Enhanced summary reports are available in the **Downloadable reports** section at the beginning message trace.</span></span> <span data-ttu-id="fee88-263">보고서에서 사용할 수 있는 정보는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="fee88-263">The following information is available in the report:</span></span>

- <span data-ttu-id="fee88-264">**origin_timestamp**: 구성된 UTC 표준 시간대를 사용하여 서비스에서 메시지를 처음 수신한 날짜 및 <sup>\*</sup> 시간입니다.</span><span class="sxs-lookup"><span data-stu-id="fee88-264">**origin_timestamp**<sup>\*</sup>: The date and time when the message was initially received by the service, using the configured UTC time zone.</span></span>

- <span data-ttu-id="fee88-265">**sender_address**: 보낸 사람 전자 메일 주소(*별칭* @ *도메인 )입니다.*</span><span class="sxs-lookup"><span data-stu-id="fee88-265">**sender_address**: The sender's email address (*alias*@*domain*).</span></span>

- <span data-ttu-id="fee88-266">**Recipient_status**: 받는 사람에게 메시지를 배달한 상태입니다.</span><span class="sxs-lookup"><span data-stu-id="fee88-266">**Recipient_status**: The status of the delivery of the message to the recipient.</span></span> <span data-ttu-id="fee88-267">메시지가 여러 받는 사람에게 전송된 경우 모든 받는 사람 및 각 받는 사람에 대한 해당 상태가 다음 형식으로 \<*email address*\> ## \<*status*\> 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="fee88-267">If the message was sent to multiple recipients, it will show all the recipients and the corresponding status for each, in the format: \<*email address*\>##\<*status*\>.</span></span> <span data-ttu-id="fee88-268">예를 들어 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="fee88-268">For example:</span></span>

  - <span data-ttu-id="fee88-269">**##Receive 보내기란** 서비스에 의해 메시지가 수신되어 의도한 대상에 전송된 것일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fee88-269">**##Receive, Send** means the message was received by the service and was sent to the intended destination.</span></span>

  - <span data-ttu-id="fee88-270">**##Receive 실패는** 서비스에서 메시지를 받았지만 의도한 대상으로의 배달이 실패했다는 의미입니다.</span><span class="sxs-lookup"><span data-stu-id="fee88-270">**##Receive, Fail** means the message was received by the service but delivery to the intended destination failed.</span></span>

  - <span data-ttu-id="fee88-271">**##Receive 배달은** 서비스에 의해 메시지가 수신되어 받는 사람의 사서함으로 배달된 것입니다.</span><span class="sxs-lookup"><span data-stu-id="fee88-271">**##Receive, Deliver** means the message was received by the service and was delivered to the recipient's mailbox.</span></span>

- <span data-ttu-id="fee88-272">**message_subject**: 메시지의 제목 필드의 처음 256자입니다. </span><span class="sxs-lookup"><span data-stu-id="fee88-272">**message_subject**: The first 256 characters of the message's **Subject** field.</span></span>

- <span data-ttu-id="fee88-273">**total_bytes**: 첨부 파일을 포함하여 메시지의 크기(bytes)입니다.</span><span class="sxs-lookup"><span data-stu-id="fee88-273">**total_bytes**: The size of the message in bytes, including attachments.</span></span>

- <span data-ttu-id="fee88-274">**message_id**: 이 값은 이 문서 앞부분의 메시지 [ID](#message-id) 섹션에서 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="fee88-274">**message_id**: This value is described in the [Message ID](#message-id) section earlier in this article.</span></span> <span data-ttu-id="fee88-275">예를 들면 `<d9683b4c-127b-413a-ae2e-fa7dfb32c69d@DM3NAM06BG401.Eop-nam06.prod.protection.outlook.com>`와 같습니다.</span><span class="sxs-lookup"><span data-stu-id="fee88-275">For example, `<d9683b4c-127b-413a-ae2e-fa7dfb32c69d@DM3NAM06BG401.Eop-nam06.prod.protection.outlook.com>`.</span></span>

- <span data-ttu-id="fee88-276">**network_message_id**: 순환 또는 메일 그룹 확장으로 인해 만들어질 수 있는 메시지의 모든 복사본에서 유지되는 고유한 메시지 ID 값입니다.</span><span class="sxs-lookup"><span data-stu-id="fee88-276">**network_message_id**: A unique message ID value that persists across all copies of the message that might be created due to bifurcation or distribution group expansion.</span></span> <span data-ttu-id="fee88-277">값의 예로는 를 들 수 `1341ac7b13fb42ab4d4408cf7f55890f` 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fee88-277">An example value is `1341ac7b13fb42ab4d4408cf7f55890f`.</span></span>

- <span data-ttu-id="fee88-278">**original_client_ip**: 보낸 사람 클라이언트의 IP 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="fee88-278">**original_client_ip**: The IP address of the sender's client.</span></span>

- <span data-ttu-id="fee88-279">**directionality:** 메시지가 조직에 전송된 인바운드 메시지(1)인지 또는 조직에서 보낸 아웃바운드 메시지(2)를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="fee88-279">**directionality**: Indicates whether the message was sent inbound (1) to your organization, or whether it was sent outbound (2) from your organization.</span></span>

- <span data-ttu-id="fee88-280">**connector_id**: 원본 또는 대상 커넥터의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="fee88-280">**connector_id**: The name of the source or destination connector.</span></span> <span data-ttu-id="fee88-281">Exchange Online의 커넥터에 대한 자세한 내용은 [Office 365에서](/Exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow)커넥터를 사용하여 메일 흐름 구성을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="fee88-281">For more information about connectors in Exchange Online, see [Configure mail flow using connectors in Office 365](/Exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow).</span></span>

- <span data-ttu-id="fee88-282">**delivery_priority**: 메시지가 높음, 낮음 또는 보통 우선 순위로 <sup>\*</sup>   **전송된지 여부입니다.**</span><span class="sxs-lookup"><span data-stu-id="fee88-282">**delivery_priority**<sup>\*</sup>: Whether the message was sent with **High**, **Low**, or **Normal** priority.</span></span>

<span data-ttu-id="fee88-283"><sup>\*</sup> 이러한 속성은 고급 요약 보고서에서만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fee88-283"><sup>\*</sup> These properties are only available in Enhanced summary reports.</span></span>

### <a name="extended-reports"></a><span data-ttu-id="fee88-284">확장 보고서</span><span class="sxs-lookup"><span data-stu-id="fee88-284">Extended reports</span></span>

<span data-ttu-id="fee88-285">사용 가능(완료) 확장 보고서는  메시지 추적 시작 부분의 다운로드 가능한 보고서 섹션에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fee88-285">Available (completed) Extended reports are available in the **Downloadable reports** section at the beginning of message trace.</span></span> <span data-ttu-id="fee88-286">확장 요약 보고서의 모든 정보는 확장된 보고서에서 사용할 수 있습니다(확장된 보고서와 origin_timestamp **delivery_priority).**</span><span class="sxs-lookup"><span data-stu-id="fee88-286">Virtually all of the information from an Enhanced summary report is available in an Extended report (with the exception of **origin_timestamp** and **delivery_priority**).</span></span> <span data-ttu-id="fee88-287">다음 추가 정보는 확장 보고서에서만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fee88-287">The following additional information is only available in an Extended report:</span></span>

- <span data-ttu-id="fee88-288">**client_ip**: 메시지를 전송한 전자 메일 서버 또는 메시징 클라이언트의 IP 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="fee88-288">**client_ip**: The IP address of the email server or messaging client that submitted the message.</span></span>

- <span data-ttu-id="fee88-289">**client_hostname**: 메시지를 전송한 전자 메일 서버 또는 메시징 클라이언트의 호스트 이름 또는 FQDN입니다.</span><span class="sxs-lookup"><span data-stu-id="fee88-289">**client_hostname**: The host name or FQDN of the email server or messaging client that submitted the message.</span></span>

- <span data-ttu-id="fee88-290">**server_ip**: 원본 또는 대상 서버의 IP 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="fee88-290">**server_ip**: The IP address of the source or destination server.</span></span>

- <span data-ttu-id="fee88-291">**server_hostname**: 대상 서버의 호스트 이름 또는 FQDN입니다.</span><span class="sxs-lookup"><span data-stu-id="fee88-291">**server_hostname**: The host name or FQDN of the destination server.</span></span>

- <span data-ttu-id="fee88-292">**source_context**: 원본 필드와 관련된 추가 **정보입니다.**</span><span class="sxs-lookup"><span data-stu-id="fee88-292">**source_context**: Extra information associated with the **source** field.</span></span> <span data-ttu-id="fee88-293">예를 들어 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="fee88-293">For example:</span></span>

  - `Protocol Filter Agent`

  - `3489061114359050000`

- <span data-ttu-id="fee88-294">**source**: 이벤트를 담당하는 Exchange Online 구성 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="fee88-294">**source**: The Exchange Online component that's responsible for the event.</span></span> <span data-ttu-id="fee88-295">예를 들어 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="fee88-295">For example:</span></span>

  - `AGENT`

  - `MAILBOXRULE`

  - `SMTP`

- <span data-ttu-id="fee88-296">**event_id**: 이 메시지에 대한 관련 레코드 찾기 섹션에 설명된 **Message** 이벤트 [값에 해당합니다.](#find-related-records-for-this-message)</span><span class="sxs-lookup"><span data-stu-id="fee88-296">**event_id**: These correspond to the **Message event** values that are explained in the [Find related records for this message](#find-related-records-for-this-message) section.</span></span>

- <span data-ttu-id="fee88-297">**internal_message_id**: 현재 메시지를 처리 중인 Exchange Online 서버에서 할당한 메시지 식별자입니다.</span><span class="sxs-lookup"><span data-stu-id="fee88-297">**internal_message_id**: A message identifier that's assigned by the Exchange Online server that's currently processing the message.</span></span>

- <span data-ttu-id="fee88-298">**recipient_address**: 메시지 받는 사람의 전자 메일 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="fee88-298">**recipient_address**: The email addresses of the message's recipients.</span></span> <span data-ttu-id="fee88-299">전자 메일 주소가 여러 개인 경우 세미콜론(;)으로 구분합니다.</span><span class="sxs-lookup"><span data-stu-id="fee88-299">Multiple email addresses are separated by the semicolon character (;).</span></span>

- <span data-ttu-id="fee88-300">**recipient_count**: 메시지의 총 받는 사람 수입니다.</span><span class="sxs-lookup"><span data-stu-id="fee88-300">**recipient_count**: The total number of recipients in the message.</span></span>

- <span data-ttu-id="fee88-301">**related_recipient_address**: , 및 이벤트와 함께 메시지와 연결된 다른 받는 사람 전자 메일 주소를 표시하는 데 `EXPAND` `REDIRECT` `RESOLVE` 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="fee88-301">**related_recipient_address**: Used with `EXPAND`, `REDIRECT`, and `RESOLVE` events to display other recipient email addresses that are associated with the message.</span></span>

- <span data-ttu-id="fee88-302">**reference**: 이 필드에는 특정 유형의 이벤트에 대한 추가 정보가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fee88-302">**reference**: This field contains additional information for specific types of events.</span></span> <span data-ttu-id="fee88-303">예를 들어 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="fee88-303">For example:</span></span>

  - <span data-ttu-id="fee88-304">**DSN:** 이 이벤트 이후에 DSN이 생성된 경우 연결된 배달 상태 알림의 message_id 값(DSN, 배달하지 않은 보고서, NDR 또는 반송 메시지라고도 알려지기)의 보고서 링크가 들어 있습니다. </span><span class="sxs-lookup"><span data-stu-id="fee88-304">**DSN**: Contains the report link, which is the **message_id** value of the associated delivery status notification (also known as a DSN, non-delivery report, NDR, or bounce message) if a DSN is generated subsequent to this event.</span></span> <span data-ttu-id="fee88-305">DSN 메시지인 경우 이 필드에는  DSN이 message_id 원래 메시지의 message_id 값이 들어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fee88-305">If this is a DSN message, this field contains the **message_id** value of the original message that the DSN was generated for.</span></span>

  - <span data-ttu-id="fee88-306">**EXPAND**: 관련 **related_recipient_address** 값 포함</span><span class="sxs-lookup"><span data-stu-id="fee88-306">**EXPAND**: Contains the **related_recipient_address** value of the related messages.</span></span>

  - <span data-ttu-id="fee88-307">**RECEIVE**: 받은 **편지함 message_id** 같은 다른 프로세스에서 메시지를 생성한 경우 관련 메시지의 message_id 값을 포함할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fee88-307">**RECEIVE**: Might contain the **message_id** value of the related message if the message was generated by other processes (for example, Inbox rules).</span></span>

  - <span data-ttu-id="fee88-308">**SEND**: DSN **internal_message_id** 값 포함</span><span class="sxs-lookup"><span data-stu-id="fee88-308">**SEND**: Contains the **internal_message_id** value of any DSN messages.</span></span>

  - <span data-ttu-id="fee88-309">**TRANSFER**:  internal_message_id 변환, 메시지 받는 사람 제한 또는 에이전트와 같은 포크되는 메시지의 값입니다.</span><span class="sxs-lookup"><span data-stu-id="fee88-309">**TRANSFER**: Contains the **internal_message_id** value of the message that's being forked (for example, by content conversion, message recipient limits, or agents).</span></span>

  - <span data-ttu-id="fee88-310">**MAILBOXRULE**:  internal_message_id 인바운드 메시지를 생성하는 인바운드 메시지의 값입니다.</span><span class="sxs-lookup"><span data-stu-id="fee88-310">**MAILBOXRULE**: Contains the **internal_message_id** value of the inbound message that caused the Inbox rule to generate the outbound message.</span></span>

    <span data-ttu-id="fee88-311">다른 유형의 이벤트의 경우 일반적으로 이 필드는 비어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fee88-311">For other types of events, this field is usually blank.</span></span>

- <span data-ttu-id="fee88-312">**return_path**: 메시지를 보낸 **MAIL FROM** 명령으로 지정된 반환 전자 메일 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="fee88-312">**return_path**: The return email address specified by the **MAIL FROM** command that sent the message.</span></span> <span data-ttu-id="fee88-313">이 필드는 비어 있는 것이 아니라 로 나타내는 null 보낸 사람 주소 값을 사용할 수 `<>` 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fee88-313">Although this field is never empty, it can have the null sender address value represented as `<>`.</span></span>

- <span data-ttu-id="fee88-314">**message_info**: 메시지에 대한 추가 정보입니다.</span><span class="sxs-lookup"><span data-stu-id="fee88-314">**message_info**: Additional information about the message.</span></span> <span data-ttu-id="fee88-315">예를 들어 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="fee88-315">For example:</span></span>

  - <span data-ttu-id="fee88-316">메시지 발신 날짜-시간(UTC for `DELIVER` and `SEND` events)입니다.</span><span class="sxs-lookup"><span data-stu-id="fee88-316">The message origination date-time in UTC for `DELIVER` and `SEND` events.</span></span> <span data-ttu-id="fee88-317">원본 날짜-시간은 메시지가 Exchange Online 조직에 처음 들어온 시간입니다.</span><span class="sxs-lookup"><span data-stu-id="fee88-317">The origination date-time is the time when the message first entered the Exchange Online organization.</span></span> <span data-ttu-id="fee88-318">UTC 날짜-시간은 ISO 8601 날짜-시간 형식으로 표시됩니다. 여기서 = 년, = 월, 일은 시간 구성 요소의 시작을 `yyyy-mm-ddThh:mm:ss.fffZ` 나타내며, 시간, = 분, = 초, = 초의 분수 및 UTC를 나타내는 또 다른 `yyyy` `mm` `dd` `T` `hh` `mm` `ss` `fff` `Z` `Zulu` 방법인 을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="fee88-318">The UTC date-time is represented in the ISO 8601 date-time format: `yyyy-mm-ddThh:mm:ss.fffZ`, where `yyyy` = year, `mm` = month, `dd` = day, `T` indicates the beginning of the time component, `hh` = hour, `mm` = minute, `ss` = second, `fff` = fractions of a second, and `Z` signifies `Zulu`, which is another way to denote UTC.</span></span>

  - <span data-ttu-id="fee88-319">인증 오류입니다.</span><span class="sxs-lookup"><span data-stu-id="fee88-319">Authentication errors.</span></span> <span data-ttu-id="fee88-320">예를 들어 인증 오류가 발생할 때 사용된 인증의 값과 유형이 표시될 `11a` 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fee88-320">For example, you might see the value `11a` and the type of authentication that was used when the authentication error occurred.</span></span>

- <span data-ttu-id="fee88-321">**tenant_id**: Exchange Online 조직(예: )을 나타내는 GUID `39238e87-b5ab-4ef6-a559-af54c6b07b42` 값입니다.</span><span class="sxs-lookup"><span data-stu-id="fee88-321">**tenant_id**: A GUID value that represents the Exchange Online organization (for example, `39238e87-b5ab-4ef6-a559-af54c6b07b42`).</span></span>

- <span data-ttu-id="fee88-322">**original_server_ip**: 원본 서버의 IP 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="fee88-322">**original_server_ip**: The IP address of the original server.</span></span>

- <span data-ttu-id="fee88-323">**custom_data**: 특정 이벤트 유형과 관련된 데이터가 들어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fee88-323">**custom_data**: Contains data related to specific event types.</span></span> <span data-ttu-id="fee88-324">자세한 내용은 다음 섹션을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="fee88-324">For more information, see the following sections.</span></span>

#### <a name="custom_data-values"></a><span data-ttu-id="fee88-325">custom_data 값</span><span class="sxs-lookup"><span data-stu-id="fee88-325">custom_data values</span></span>

<span data-ttu-id="fee88-326">**이벤트의** custom_data 필드는 다양한 Exchange Online 에이전트가 메시지 처리 세부 정보를 `AGENTINFO` 기록하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="fee88-326">The **custom_data** field for an `AGENTINFO` event is used by a variety of Exchange Online agents to log message processing details.</span></span> <span data-ttu-id="fee88-327">다음 섹션에서는 좀 더 흥미로운 에이전트에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="fee88-327">Some of the more interesting agents are described in the following sections.</span></span>

#### <a name="spam-filter-agent"></a><span data-ttu-id="fee88-328">스팸 필터 에이전트</span><span class="sxs-lookup"><span data-stu-id="fee88-328">Spam filter agent</span></span>

<span data-ttu-id="fee88-329">시작 **custom_data** 스팸 필터 에이전트의 `S:SFA` 값입니다.</span><span class="sxs-lookup"><span data-stu-id="fee88-329">A **custom_data** value that starts with `S:SFA` is from the spam filter agent.</span></span> <span data-ttu-id="fee88-330">다음 표에는 주요 세부 정보가 설명되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fee88-330">The key details are described in the following table:</span></span>

****

|<span data-ttu-id="fee88-331">값</span><span class="sxs-lookup"><span data-stu-id="fee88-331">Value</span></span>|<span data-ttu-id="fee88-332">설명</span><span class="sxs-lookup"><span data-stu-id="fee88-332">Description</span></span>|
|---|---|
|`SFV=NSPM`|<span data-ttu-id="fee88-333">메시지가 스팸이 아닌 것으로 표시되었으며 받는 사람에게 전송되었습니다.</span><span class="sxs-lookup"><span data-stu-id="fee88-333">The message was marked as non-spam and was sent to the intended recipients.</span></span>|
|`SFV=SPM`|<span data-ttu-id="fee88-334">메시지가 스팸 방지 필터링(콘텐츠 필터링)에 의해 스팸으로 표시되었습니다.</span><span class="sxs-lookup"><span data-stu-id="fee88-334">The message was marked as spam by anti-spam filtering (also known as content filtering).</span></span>|
|`SFV=BLK`|<span data-ttu-id="fee88-335">수신 거부된 보낸 사람이 보낸 메시지이므로 필터링을 건너뛰었으며 메시지가 차단되었습니다.</span><span class="sxs-lookup"><span data-stu-id="fee88-335">Filtering was skipped and the message was blocked because it originated from a blocked sender.</span></span>|
|`SFV=SKS`|<span data-ttu-id="fee88-336">스팸 방지 필터링에서 처리하기 전에 메시지가 스팸으로 표시되었습니다.</span><span class="sxs-lookup"><span data-stu-id="fee88-336">The message was marked as spam prior to being processed by anti-spam filtering.</span></span> <span data-ttu-id="fee88-337">메일 흐름 규칙(전송 규칙이라고도 함)과 일치하여 스팸으로 자동 표시되고 모든 추가 필터링을 무시하는 메시지가 여기에 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="fee88-337">This includes messages where the message matched a mail flow rule (also known as a transport rule) to automatically mark it as spam and bypass all additional filtering.</span></span>|
|`SCL=<number>`|<span data-ttu-id="fee88-338">다양한 SCL 값 및 해당 값의 의미에 대한 자세한 내용은 스팸 지수 [를 참조하세요.](spam-confidence-levels.md)</span><span class="sxs-lookup"><span data-stu-id="fee88-338">For more information about the different SCL values and what they mean, see [Spam confidence levels](spam-confidence-levels.md).</span></span>|
|`PCL=<number>`|<span data-ttu-id="fee88-339">메시지의 PCL(피싱 지수) 값입니다.</span><span class="sxs-lookup"><span data-stu-id="fee88-339">The Phishing Confidence Level (PCL) value of the message.</span></span> <span data-ttu-id="fee88-340">이러한 값은 스팸 지수 에 설명된 SCL 값과 동일한 [방식으로 해석될 수 있습니다.](spam-confidence-levels.md)</span><span class="sxs-lookup"><span data-stu-id="fee88-340">These can be interpreted the same way as the SCL values documented in [Spam confidence levels](spam-confidence-levels.md).</span></span>|
|`DI=SB`|<span data-ttu-id="fee88-341">메시지의 보낸 사람이 차단되었습니다.</span><span class="sxs-lookup"><span data-stu-id="fee88-341">The sender of the message was blocked.</span></span>|
|`DI=SQ`|<span data-ttu-id="fee88-342">메시지가 격리되었습니다.</span><span class="sxs-lookup"><span data-stu-id="fee88-342">The message was quarantined.</span></span>|
|`DI=SD`|<span data-ttu-id="fee88-343">메시지가 삭제되었습니다.</span><span class="sxs-lookup"><span data-stu-id="fee88-343">The message was deleted.</span></span>|
|`DI=SJ`|<span data-ttu-id="fee88-344">메시지가 받는 사람의 정크 메일 폴더로 전송되었습니다.</span><span class="sxs-lookup"><span data-stu-id="fee88-344">The message was sent to the recipient's Junk Email folder.</span></span>|
|`DI=SN`|<span data-ttu-id="fee88-345">메시지가 일반 아웃바운드 배달 풀을 통해 라우팅되었습니다.</span><span class="sxs-lookup"><span data-stu-id="fee88-345">The message was routed through the normal outbound delivery pool.</span></span>|
|`DI=SO`|<span data-ttu-id="fee88-346">메시지가 위험 수준이 높은 배달 풀을 통해 라우팅되었습니다.</span><span class="sxs-lookup"><span data-stu-id="fee88-346">The message was routed through the higher risk delivery pool.</span></span> <span data-ttu-id="fee88-347">자세한 내용은 [아웃바운드 메시지의 고위험 전송 풀](high-risk-delivery-pool-for-outbound-messages.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="fee88-347">For more information, see [High-risk delivery pool for outbound messages](high-risk-delivery-pool-for-outbound-messages.md).</span></span>|
|`SFS=[a]|SFS=[b]`|<span data-ttu-id="fee88-348">스팸 규칙이 일치했음을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="fee88-348">This denotes that spam rules were matched.</span></span>|
|`IPV=CAL`|<span data-ttu-id="fee88-349">연결 필터의 IP 허용 목록에 IP 주소가 지정되어 있어 메시지가 스팸 필터를 통과하도록 허용되었습니다.</span><span class="sxs-lookup"><span data-stu-id="fee88-349">The message was allowed through the spam filters because the IP address was specified in an IP Allow list in the connection filter.</span></span>|
|`H=<EHLOstring>`|<span data-ttu-id="fee88-350">연결 전자 메일 서버의 HELO 또는 EHLO 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="fee88-350">The HELO or EHLO string of the connecting email server.</span></span>|
|`PTR=<ReverseDNS>`|<span data-ttu-id="fee88-351">보내는 IP 주소의 PTR 레코드로, 역방향 DNS 주소라고도 합니다.</span><span class="sxs-lookup"><span data-stu-id="fee88-351">The PTR record of the sending IP address, also known as the reverse DNS address.</span></span>|
|

<span data-ttu-id="fee88-352">스팸으로 **custom_data** 메시지의 값을 다음과 같이 설정하는 예는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="fee88-352">An example **custom_data** value for a message that's filtered for spam like this:</span></span>

`S:SFA=SUM|SFV=SPM|IPV=CAL|SRV=BULK|SFS=470454002|SFS=349001|SCL=9|SCORE=-1|LIST=0|DI=SN|RD=ftmail.inc.com|H=ftmail.inc.com|CIP=98.129.140.74|SFP=1501|ASF=1|CTRY=US|CLTCTRY=|LANG=en|LAT=287|LAT=260|LAT=18;`

#### <a name="malware-filter-agent"></a><span data-ttu-id="fee88-353">맬웨어 필터 에이전트</span><span class="sxs-lookup"><span data-stu-id="fee88-353">Malware filter agent</span></span>

<span data-ttu-id="fee88-354">시작 **custom_data** 맬웨어 필터 `S:AMA` 에이전트의 값입니다.</span><span class="sxs-lookup"><span data-stu-id="fee88-354">A **custom_data** value that starts with `S:AMA` is from the malware filter agent.</span></span> <span data-ttu-id="fee88-355">다음 표에는 주요 세부 정보가 설명되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fee88-355">The key details are described in the following table:</span></span>

****

|<span data-ttu-id="fee88-356">값</span><span class="sxs-lookup"><span data-stu-id="fee88-356">Value</span></span>|<span data-ttu-id="fee88-357">설명</span><span class="sxs-lookup"><span data-stu-id="fee88-357">Description</span></span>|
|---|---|
|<span data-ttu-id="fee88-358">`AMA=SUM|v=1|` 또는 `AMA=EV|v=1`</span><span class="sxs-lookup"><span data-stu-id="fee88-358">`AMA=SUM|v=1|` or `AMA=EV|v=1`</span></span>|<span data-ttu-id="fee88-359">메시지에 맬웨어가 포함된 것으로 확인되었습니다.</span><span class="sxs-lookup"><span data-stu-id="fee88-359">The message was determined to contain malware.</span></span> <span data-ttu-id="fee88-360">`SUM` 은 맬웨어를 검색할 수 있는 엔진 수를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="fee88-360">`SUM` indicates the malware could've been detected by any number of engines.</span></span> <span data-ttu-id="fee88-361">`EV` 맬웨어가 특정 엔진에 의해 검색된 것일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fee88-361">`EV` indicates the malware was detected by a specific engine.</span></span> <span data-ttu-id="fee88-362">맬웨어가 엔진에서 검색되면 후속 작업이 트리거됩니다.</span><span class="sxs-lookup"><span data-stu-id="fee88-362">When malware is detected by an engine this triggers the subsequent actions.</span></span>|
|`Action=r`|<span data-ttu-id="fee88-363">메시지가 대체되었습니다.</span><span class="sxs-lookup"><span data-stu-id="fee88-363">The message was replaced.</span></span>|
|`Action=p`|<span data-ttu-id="fee88-364">메시지가 무시되었습니다.</span><span class="sxs-lookup"><span data-stu-id="fee88-364">The message was bypassed.</span></span>|
|`Action=d`|<span data-ttu-id="fee88-365">메시지가 지연되었습니다.</span><span class="sxs-lookup"><span data-stu-id="fee88-365">The message was deferred.</span></span>|
|`Action=s`|<span data-ttu-id="fee88-366">메시지가 삭제되었습니다.</span><span class="sxs-lookup"><span data-stu-id="fee88-366">The message was deleted.</span></span>|
|`Action=st`|<span data-ttu-id="fee88-367">메시지가 무시되었습니다.</span><span class="sxs-lookup"><span data-stu-id="fee88-367">The message was bypassed.</span></span>|
|`Action=sy`|<span data-ttu-id="fee88-368">메시지가 무시되었습니다.</span><span class="sxs-lookup"><span data-stu-id="fee88-368">The message was bypassed.</span></span>|
|`Action=ni`|<span data-ttu-id="fee88-369">메시지가 거부되었습니다.</span><span class="sxs-lookup"><span data-stu-id="fee88-369">The message was rejected.</span></span>|
|`Action=ne`|<span data-ttu-id="fee88-370">메시지가 거부되었습니다.</span><span class="sxs-lookup"><span data-stu-id="fee88-370">The message was rejected.</span></span>|
|`Action=b`|<span data-ttu-id="fee88-371">메시지가 차단되었습니다.</span><span class="sxs-lookup"><span data-stu-id="fee88-371">The message was blocked.</span></span>|
|`Name=<malware>`|<span data-ttu-id="fee88-372">검색된 맬웨어의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="fee88-372">The name of the malware that was detected.</span></span>|
|`File=<filename>`|<span data-ttu-id="fee88-373">맬웨어가 포함된 파일의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="fee88-373">The name of the file that contained the malware.</span></span>|
|

<span data-ttu-id="fee88-374">**맬웨어가 custom_data** 메시지의 값에 대한 예는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="fee88-374">An example **custom_data** value for a message that contains malware looks like this:</span></span>

`S:AMA=SUM|v=1|action=b|error=|atch=1;S:AMA=EV|engine=M|v=1|sig=1.155.974.0|name=DOS/Test_File|file=filename;S:AMA=EV|engine=A|v=1|sig=201707282038|name=Test_File|file=filename`

#### <a name="transport-rule-agent"></a><span data-ttu-id="fee88-375">전송 규칙 에이전트</span><span class="sxs-lookup"><span data-stu-id="fee88-375">Transport Rule agent</span></span>

<span data-ttu-id="fee88-376">시작 **custom_data** 값은 메일 흐름 규칙(전송 규칙)에 대한 전송 규칙 `S:TRA` 에이전트의 값입니다.</span><span class="sxs-lookup"><span data-stu-id="fee88-376">A **custom_data** value that starts with`S:TRA` is from the Transport Rule agent for mail flow rules (also known as transport rules).</span></span> <span data-ttu-id="fee88-377">다음 표에는 주요 세부 정보가 설명되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fee88-377">The key details are described in the following table:</span></span>

****

|<span data-ttu-id="fee88-378">값</span><span class="sxs-lookup"><span data-stu-id="fee88-378">Value</span></span>|<span data-ttu-id="fee88-379">설명</span><span class="sxs-lookup"><span data-stu-id="fee88-379">Description</span></span>|
|---|---|
|`ETR|ruleId=<guid>`|<span data-ttu-id="fee88-380">일치된 규칙 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="fee88-380">The rule ID that was matched.</span></span>|
|`St=<datetime>`|<span data-ttu-id="fee88-381">규칙 일치가 발생한 날짜 및 시간(UTC)입니다.</span><span class="sxs-lookup"><span data-stu-id="fee88-381">The date and time in UTC when the rule match occurred.</span></span>|
|`Action=<ActionDefinition>`|<span data-ttu-id="fee88-382">적용된 작업입니다.</span><span class="sxs-lookup"><span data-stu-id="fee88-382">The action that was applied.</span></span> <span data-ttu-id="fee88-383">사용 가능한 작업 목록은 [Exchange Online의 메일 흐름 규칙 작업을 참조하세요.](/exchange/security-and-compliance/mail-flow-rules/mail-flow-rule-actions)</span><span class="sxs-lookup"><span data-stu-id="fee88-383">For a list of available actions, see [Mail flow rule actions in Exchange Online](/exchange/security-and-compliance/mail-flow-rules/mail-flow-rule-actions).</span></span>|
|`Mode=<Mode>`|<span data-ttu-id="fee88-384">규칙의 모드입니다.</span><span class="sxs-lookup"><span data-stu-id="fee88-384">The mode of the rule.</span></span> <span data-ttu-id="fee88-385">유효한 값은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="fee88-385">Valid values are:</span></span><ul><li><span data-ttu-id="fee88-386">**적용**: 규칙에 대한 모든 작업이 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="fee88-386">**Enforce**: All actions on the rule will be enforced.</span></span></li><li><span data-ttu-id="fee88-387">**정책 팁을 통해 테스트:** 모든 정책 팁 작업이 전송되지만 다른 적용 작업은 실행되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="fee88-387">**Test with Policy Tips:**: Any Policy Tip actions will be sent, but other enforcement actions will not be acted on.</span></span></li><li><span data-ttu-id="fee88-388">**정책 팁이** 없는 테스트: 작업이 로그 파일에 나열되지만 보낸 사람이 어떤 식으로도 알림을 보내지 않고 적용 작업이 실행되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="fee88-388">**Test without Policy Tips**: Actions will be listed in a log file, but senders will not be notified in any way, and enforcement actions will not be acted on.</span></span></li></ul>|
|

<span data-ttu-id="fee88-389">메일 **custom_data** 조건과 일치하는 메시지의 값을 설정하는 예는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="fee88-389">An example **custom_data** value for a messages that matches the conditions of a mail flow rule looks like this:</span></span>

`S:TRA=ETR|ruleId=19a25eb2-3e43-4896-ad9e-47b6c359779d|st=7/17/2017 12:31:25 AM|action=ApplyHtmlDisclaimer|sev=1|mode=Enforce`