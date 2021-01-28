---
title: 전자 메일을 전달하는 새 사용자
f1.keywords:
- NOCSH
ms.author: siosulli
author: siosulli
manager: dansimp
audience: ITPro
ms.topic: conceptual
localization_priority: Normal
ms.assetid: ''
description: 관리자는 보안 및 준수 센터에서 새 사용자 전달 전자 메일 정보를 사용하여 조직의 사용자가 새 도메인으로 메시지를 전달하는 & 조사하는 방법을 배울 수 있습니다.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: af991cb0af20a0f48bc5283d4e4fb26ea75d6ba6
ms.sourcegitcommit: 537e513a4a232a01e44ecbc76d86a8bcaf142482
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/27/2021
ms.locfileid: "50029873"
---
# <a name="new-users-forwarding-email-insight-in-the-security--compliance-center"></a><span data-ttu-id="9fa89-103">보안 및 준수 센터에서 전자 메일을 전달하는 & 사용자</span><span class="sxs-lookup"><span data-stu-id="9fa89-103">New users forwarding email insight in the Security & Compliance Center</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="9fa89-104">조직의 새 사용자 계정이 갑자기 외부 도메인에 전자 메일 메시지를 전달하기 시작하면 의심스러우게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9fa89-104">It's suspicious when new user accounts in your organization suddenly start forwarding email messages to external domains.</span></span>

<span data-ttu-id="9fa89-105">Security **&** 준수 센터에서 전달되는 [](https://protection.office.com) 새 도메인은 조직에서 새로 만든 사용자가 외부 도메인으로 메시지를 전달할 때 사용자에게 이를 통보합니다.</span><span class="sxs-lookup"><span data-stu-id="9fa89-105">The **New domains being forwarded email** insight in the [Security & Compliance Center](https://protection.office.com) notifies you when newly-created users in your organization are forwarding messages to external domains.</span></span> <span data-ttu-id="9fa89-106">이 조건은 손상된 관리자 계정을 사용하여 새 사용자를 만들었다는 것을 나타낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9fa89-106">This condition could indicate compromised admin accounts were used to create the new users.</span></span> <span data-ttu-id="9fa89-107">계정이 손상된 것으로 의심되는 경우 손상된 전자 메일 계정에 응답을 [참조하세요.](responding-to-a-compromised-email-account.md)</span><span class="sxs-lookup"><span data-stu-id="9fa89-107">If you suspect the accounts have been compromised, see [Responding to a compromised email account](responding-to-a-compromised-email-account.md).</span></span>

<span data-ttu-id="9fa89-108">이 인사이트는 문제가 검색된 경우만 표시되고 전달 보고서 페이지에 [표시됩니다.](view-mail-flow-reports.md#forwarding-report)</span><span class="sxs-lookup"><span data-stu-id="9fa89-108">This insight appears only when the issue is detected, and it appears on the [Forwarding report](view-mail-flow-reports.md#forwarding-report) page.</span></span>

![전자 메일을 전달하는 새 사용자](../../media/mfi-new-users-forwarding-email.png)

<span data-ttu-id="9fa89-110">위젯을 클릭하면 이 문서 나중에 설명하는 전달 수정 보고서에 대한 링크를 포함하여 전달된 [](#forwarding-modifications-report) 메시지에 대한 자세한 정보를 찾을 수 있는 플라이아웃이 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="9fa89-110">When you click on the widget, a flyout appears where you can find more details about the forwarded messages, including a link to the [Forwarding modifications report](#forwarding-modifications-report) as described later in this article.</span></span>

![새 사용자 전달 전자 메일 정보를 클릭한 후 나타나는 세부 정보 플라이아웃](../../media/mfi-new-users-forwarding-email-details.png)

<span data-ttu-id="9fa89-112">상위 인사이트 및 추천 영역(보고서 대시보드 또는  **)에서** 모두 보기를 클릭한 후 인사이트를 선택한 & 세부 정보 페이지로 이동될 **수도** \>  <https://protection.office.com/insightdashboard> 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9fa89-112">You can also get to this details page when you select the insight after you click **View all** in the **Top insights & recommendations** area on (**Reports** \> **Dashboard** or <https://protection.office.com/insightdashboard>).</span></span>

<span data-ttu-id="9fa89-113">다음 섹션에  설명된 바와 같이 인사이트  링크와 연결된 보고서 보기를 클릭하여 전달 수정 보고서로 이동하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9fa89-113">You can click the **See report associated with insight** link to go to the **Forwarding modifications report** as described in the next section.</span></span>

## <a name="forwarding-modifications-report"></a><span data-ttu-id="9fa89-114">수정 내용 전달 보고서</span><span class="sxs-lookup"><span data-stu-id="9fa89-114">Forwarding modifications report</span></span>

<span data-ttu-id="9fa89-115">전달 **수정 보고서에는** 조직의 보낸 사람이 자동으로 전달하는 메시지에 대한 세부 정보가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="9fa89-115">The **Forwarding modifications report** shows details about messages that are being automatically forwarded from senders in your organization:</span></span>

- <span data-ttu-id="9fa89-116">외부 도메인으로 메시지를 전달하는 새로 만든 계정입니다.</span><span class="sxs-lookup"><span data-stu-id="9fa89-116">Newly-created accounts that are forwarding messages to external domains.</span></span>
- <span data-ttu-id="9fa89-117">조직의 다른 보낸 사람이 전달한 적이 없는 외부 도메인으로 메시지를 전달하는 계정입니다.</span><span class="sxs-lookup"><span data-stu-id="9fa89-117">Accounts that are forwarding messages to external domains that have never been forwarded to by other senders in your organization.</span></span>

<span data-ttu-id="9fa89-118">이러한 유형의 전달된 메시지는 보안 또는 규정 준수 위험을 내포할 수 있으며 계정 손상을 나타낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9fa89-118">These types of forwarded messages can pose a security or compliance risk, and might indicate compromised accounts.</span></span>

<span data-ttu-id="9fa89-119">보고서에는 최대 90일간의 데이터가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9fa89-119">The report contains data for up to 90 days.</span></span> <span data-ttu-id="9fa89-120">기본적으로 보고서에는 지난 7일간의 데이터가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="9fa89-120">By default, the report shows data for the last 7 days.</span></span>

<span data-ttu-id="9fa89-121">이 보고서는 메일 흐름 [](mail-flow-insights-v2.md) 대시보드 또는 보고서 대시보드에서 직접 사용할 [수 없습니다.](view-mail-flow-reports.md)</span><span class="sxs-lookup"><span data-stu-id="9fa89-121">This report isn't directly available in the [Mail flow dashboard](mail-flow-insights-v2.md) or in the [Reports dashboard](view-mail-flow-reports.md).</span></span> <span data-ttu-id="9fa89-122">전자 메일 정보를  전달하는 새 사용자의 인사이트 링크와 연결된 보고서 보기를 클릭하는 것 외에도 다음을 통해 보고서에 연결됩니다. </span><span class="sxs-lookup"><span data-stu-id="9fa89-122">In addition to clicking the **See report associated with insight** link in the **New users forwarding email** insight, you get to the report by:</span></span>

- <span data-ttu-id="9fa89-123">전자 메일 **정보를** 전달할 새 도메인의 세부 정보에서 전달 알림 보고서 [링크를 클릭합니다.](mfi-new-domains-being-forwarded-email.md)</span><span class="sxs-lookup"><span data-stu-id="9fa89-123">Clicking the **Forwarding notifications report** link in the details of the [New domains being forwarded email insight](mfi-new-domains-being-forwarded-email.md).</span></span>
- <span data-ttu-id="9fa89-124">여는 <https://protection.office.com/reportv2?id=MailFlowNewForwarding> 중입니다.</span><span class="sxs-lookup"><span data-stu-id="9fa89-124">Opening <https://protection.office.com/reportv2?id=MailFlowNewForwarding>.</span></span>

### <a name="report-view-for-the-forwarding-modifications-report"></a><span data-ttu-id="9fa89-125">전달 수정 보고서에 대한 보고서 보기</span><span class="sxs-lookup"><span data-stu-id="9fa89-125">Report view for the Forwarding modifications report</span></span>

<span data-ttu-id="9fa89-126">보고서 보기에서 사용할 수 있는 차트는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="9fa89-126">The following charts are available in the report view:</span></span>

- <span data-ttu-id="9fa89-127">**데이터 표시: 새** 전달 사용자:</span><span class="sxs-lookup"><span data-stu-id="9fa89-127">**Show data for: New forwarding users**:</span></span>

  ![전달 수정 보고서의 새 전달 사용자 보기](../../media/forwarding-modifications-report-new-forwarding-users.png)

- <span data-ttu-id="9fa89-129">**데이터 표시: 새** 전달 도메인:</span><span class="sxs-lookup"><span data-stu-id="9fa89-129">**Show data for: New forwarding domains**:</span></span>

  ![전달 수정 보고서의 새 전달된 도메인 보기](../../media/forwarding-modifications-report-new-forwarded-domains.png)

<span data-ttu-id="9fa89-131">보고서 보기에서 **필터를** 클릭하면 시작 날짜와 종료  날짜가 있는 날짜 범위를 **지정할 수 있습니다.**</span><span class="sxs-lookup"><span data-stu-id="9fa89-131">If you click **Filters** in a report view, you can specify a date range with **Start date** and **End date**.</span></span>

### <a name="details-table-view-for-the-forwarding-modifications-report"></a><span data-ttu-id="9fa89-132">전달 수정 보고서에 대한 세부 정보 테이블 보기</span><span class="sxs-lookup"><span data-stu-id="9fa89-132">Details table view for the Forwarding modifications report</span></span>

<span data-ttu-id="9fa89-133">세부 **정보** 표 보기를 클릭하면 표시되는 정보는 보고 있는 차트에 따라 다를 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9fa89-133">If you click **View details table**, the information that's shown depends on the chart you were looking at:</span></span>

- <span data-ttu-id="9fa89-134">**데이터 표시: 새** 전달 사용자:</span><span class="sxs-lookup"><span data-stu-id="9fa89-134">**Show data for: New forwarding users**:</span></span>

  - <span data-ttu-id="9fa89-135">**이름**: 보낸 사람 전자 메일 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="9fa89-135">**Name**: The email address of the sender.</span></span>
  - <span data-ttu-id="9fa89-136">**전달 유형**</span><span class="sxs-lookup"><span data-stu-id="9fa89-136">**Forwarding type**</span></span>
  - <span data-ttu-id="9fa89-137">**받는 사람 주소**</span><span class="sxs-lookup"><span data-stu-id="9fa89-137">**Recipient address**</span></span>
  - <span data-ttu-id="9fa89-138">**세부 정보**</span><span class="sxs-lookup"><span data-stu-id="9fa89-138">**Details**</span></span>
  - <span data-ttu-id="9fa89-139">**개수**</span><span class="sxs-lookup"><span data-stu-id="9fa89-139">**Count**</span></span>
  - <span data-ttu-id="9fa89-140">**첫 번째 전달 날짜**</span><span class="sxs-lookup"><span data-stu-id="9fa89-140">**First forward date**</span></span>

- <span data-ttu-id="9fa89-141">**데이터 표시: 새** 전달 도메인:</span><span class="sxs-lookup"><span data-stu-id="9fa89-141">**Show data for: New forwarding domains**:</span></span>

  - <span data-ttu-id="9fa89-142">**이름:** 보낸 사람 전자 메일 도메인입니다.</span><span class="sxs-lookup"><span data-stu-id="9fa89-142">**Name**: The email domain of the sender.</span></span>
  - <span data-ttu-id="9fa89-143">**전달 유형**</span><span class="sxs-lookup"><span data-stu-id="9fa89-143">**Forwarding type**</span></span>
  - <span data-ttu-id="9fa89-144">**받는 사람 주소**</span><span class="sxs-lookup"><span data-stu-id="9fa89-144">**Recipient address**</span></span>
  - <span data-ttu-id="9fa89-145">**세부 정보**</span><span class="sxs-lookup"><span data-stu-id="9fa89-145">**Details**</span></span>
  - <span data-ttu-id="9fa89-146">**개수**</span><span class="sxs-lookup"><span data-stu-id="9fa89-146">**Count**</span></span>
  - <span data-ttu-id="9fa89-147">**첫 번째 전달 날짜**</span><span class="sxs-lookup"><span data-stu-id="9fa89-147">**First forward date**</span></span>

<span data-ttu-id="9fa89-148">세부 정보 표 보기에서 **필터를** 클릭하면 시작 날짜와  종료 날짜가 있는 날짜 범위를 **지정할 수 있습니다.**</span><span class="sxs-lookup"><span data-stu-id="9fa89-148">If you click **Filters** in a details table view, you can specify a date range with **Start date** and **End date**.</span></span>

<span data-ttu-id="9fa89-149">표에서 행을 선택하면 세부  정보 플라이아웃이 다음 정보와 함께 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="9fa89-149">If you select a row from the table, a **Details** flyout appears with the following information:</span></span>

- <span data-ttu-id="9fa89-150">**이름:** 이 주소는 보낸 사람 전자 메일 주소(데이터 **표시:** 새 전달 사용자 보기에서) 또는 보낸 사람 전자 메일 도메인(데이터 **표시:** 새 전달 도메인 보기에서)입니다.</span><span class="sxs-lookup"><span data-stu-id="9fa89-150">**Name**: This is either the sender's email address (from **Show data for: New forwarding users** view) or the sender's email domain (from **Show data for: New forwarding domains** view).</span></span>
- <span data-ttu-id="9fa89-151">**전달 유형**</span><span class="sxs-lookup"><span data-stu-id="9fa89-151">**Forwarding type**</span></span>
- <span data-ttu-id="9fa89-152">**받는 사람**</span><span class="sxs-lookup"><span data-stu-id="9fa89-152">**Recipient**</span></span>
- <span data-ttu-id="9fa89-153">**세부 정보**</span><span class="sxs-lookup"><span data-stu-id="9fa89-153">**Details**</span></span>
- <span data-ttu-id="9fa89-154">**개수**</span><span class="sxs-lookup"><span data-stu-id="9fa89-154">**Count**</span></span>
- <span data-ttu-id="9fa89-155">**시작 날짜**</span><span class="sxs-lookup"><span data-stu-id="9fa89-155">**Start date**</span></span>
- <span data-ttu-id="9fa89-156">**권장 사항:** 여기에서 링크를 클릭하여 Microsoft 365 관리 센터에서 사용자를 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9fa89-156">**Recommendation**: From here, you can click the link to manage the user in the Microsoft 365 admin center.</span></span>

![전달 수정 보고서의 새 전달 사용자 보기에 대한 세부 정보 테이블의 세부 정보 플라이아웃](../../media/mfi-forwarding-modifications-report-new-forwarding-users-view-details-table-details.png)

<span data-ttu-id="9fa89-158">보고서 보기로 돌아가려면 보고서 **보기를 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="9fa89-158">To go back to the reports view, click **View report**.</span></span>

## <a name="related-topics"></a><span data-ttu-id="9fa89-159">관련 항목</span><span class="sxs-lookup"><span data-stu-id="9fa89-159">Related topics</span></span>

<span data-ttu-id="9fa89-160">메일 흐름 대시보드의 다른 인사이트에 대한 자세한 내용은 보안 및 준수 센터의 메일 [흐름 & 참조하세요.](mail-flow-insights-v2.md)</span><span class="sxs-lookup"><span data-stu-id="9fa89-160">For information about other insights in the Mail flow dashboard, see [Mail flow insights in the Security & Compliance Center](mail-flow-insights-v2.md).</span></span>
