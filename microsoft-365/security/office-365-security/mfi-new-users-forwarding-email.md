---
title: 전자 메일을 전달하는 새 사용자
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: conceptual
ms.service: exchange-online
localization_priority: Normal
ms.assetid: ''
description: 관리자는 보안 & 준수 센터에서 새 사용자를 전달하는 인사이트를 사용하여 조직의 사용자가 새 도메인으로 메시지를 전달하는 시기를 조사하는 방법을 알아볼 수 있습니다.
ms.openlocfilehash: cb2e16d321e181916219e3425c26e59ebe31b866
ms.sourcegitcommit: e12fa502bc216f6083ef5666f693a04bb727d4df
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/20/2020
ms.locfileid: "46826984"
---
# <a name="new-users-forwarding-email-insight-in-the-security--compliance-center"></a><span data-ttu-id="11baa-103">보안 보안 및 준수 센터에서 전자 메일을 전달하는 & 정보</span><span class="sxs-lookup"><span data-stu-id="11baa-103">New users forwarding email insight in the Security & Compliance Center</span></span>

<span data-ttu-id="11baa-104">조직의 새 사용자 계정이 외부 도메인으로 전자 메일 메시지 전달을 과도하게 시작하면 의심스러운 것입니다.</span><span class="sxs-lookup"><span data-stu-id="11baa-104">It's suspicious when new user accounts in your organization suddenly start forwarding email messages to external domains.</span></span>

<span data-ttu-id="11baa-105">전달되는 **전자 메일 인사이트인** 새 도메인은 조직의 새로 만든 사용자가 외부 도메인으로 메시지를 전달하는 경우 해당 정보를 알리게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="11baa-105">The **New domains being forwarded email** insight notifies you when newly-created users in your organization are forwarding messages to external domains.</span></span> <span data-ttu-id="11baa-106">이 조건은 차단된 관리자 계정이 새 사용자를 만드는 데 사용됨을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="11baa-106">This condition could indicate compromised admin accounts were used to create the new users.</span></span> <span data-ttu-id="11baa-107">계정이 손상되었다고 의심되는 경우 [손상된 이메일 계정에 대한 응답을 참조하세요.](https://docs.microsoft.com/microsoft-365/security/office-365-security/responding-to-a-compromised-email-account)</span><span class="sxs-lookup"><span data-stu-id="11baa-107">If you suspect the accounts have been compromised, see [Responding to a compromised email account](https://docs.microsoft.com/microsoft-365/security/office-365-security/responding-to-a-compromised-email-account).</span></span>

<span data-ttu-id="11baa-108">이 인사이트는 문제가 검색될 때만 나타나며 전달 보고서 [페이지에 표시됩니다.](view-mail-flow-reports.md#forwarding-report)</span><span class="sxs-lookup"><span data-stu-id="11baa-108">This insight appears only when the issue is detected, and it appears on the [Forwarding report](view-mail-flow-reports.md#forwarding-report) page.</span></span>

![전자 메일을 전달하는 새 사용자](../../media/mfi-new-users-forwarding-email.png)

<span data-ttu-id="11baa-110">위로 창을 클릭하면 이 항목의 뒷부분에 설명된 것과 같이 전달된 메시지에 대한 자세한 정보를 [찾을](#forwarding-modifications-report) 수 있는 플라이 아웃이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="11baa-110">When you click on the widget, a flyout appears where you can find more details about the forwarded messages, including a link to the [Forwarding modifications report](#forwarding-modifications-report) as described later in this topic.</span></span>

![새 사용자를 전달하는 전자 메일 인사이트를 클릭한 후 표시되는 세부 정보 플라이아웃](../../media/mfi-new-users-forwarding-email-details.png)

<span data-ttu-id="11baa-112">또한 상위 인사이트 보기 영역(보고서 대시보드 또는)에서 **View all** **모든 정보 보기를 클릭하면 이 & 세부 정보 페이지에** **나타나도록** \> **할 수** <https://protection.office.com/insightdashboard> 있습니다.</span><span class="sxs-lookup"><span data-stu-id="11baa-112">You can also get to this details page when you select the insight after you click **View all** in the **Top insights & recommendations** area on (**Reports** \> **Dashboard** or <https://protection.office.com/insightdashboard>).</span></span>

<span data-ttu-id="11baa-113">정보 **링크와 연결된 See report insight** link를 클릭하면 다음 섹션에 설명된 바라면 **서정 수정 보고서로** 이동할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="11baa-113">You can click the **See report associated with insight** link to go to the **Forwarding modifications report** as described in the next section.</span></span>

## <a name="forwarding-modifications-report"></a><span data-ttu-id="11baa-114">문제 해결 보고서</span><span class="sxs-lookup"><span data-stu-id="11baa-114">Forwarding modifications report</span></span>

<span data-ttu-id="11baa-115">**전달 수정 보고서에는 조직의 보낸 사람으로부터** 자동으로 전달되는 메시지에 대한 세부 정보가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="11baa-115">The **Forwarding modifications report** shows details about messages that are being automatically forwarded from senders in your organization:</span></span>

- <span data-ttu-id="11baa-116">외부 도메인으로 메시지를 전달하는 새로 만든 계정입니다.</span><span class="sxs-lookup"><span data-stu-id="11baa-116">Newly-created accounts that are forwarding messages to external domains.</span></span>
- <span data-ttu-id="11baa-117">외부 도메인으로 메시지를 전달하는 계정(조직 내 다른 사람이 전달되지 않은 경우).</span><span class="sxs-lookup"><span data-stu-id="11baa-117">Accounts that are forwarding messages to external domains that have never been forwarded to by other senders in your organization.</span></span>

<span data-ttu-id="11baa-118">전달된 이러한 유형의 메시지는 보안 또는 규정 준수 위험에 부합될 수 있기이하며, 위험에 노출된 계정을 나타내기도 합니다.</span><span class="sxs-lookup"><span data-stu-id="11baa-118">These types of forwarded messages can pose a security or compliance risk, and might indicate compromised accounts.</span></span>

<span data-ttu-id="11baa-119">보고서에는 최대 90일 동안의 데이터가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="11baa-119">The report contains data for up to 90 days.</span></span> <span data-ttu-id="11baa-120">기본적으로 보고서는 지난 7일간의 데이터를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="11baa-120">By default, the report shows data for the last 7 days.</span></span>

<span data-ttu-id="11baa-121">이 보고서는 메일 흐름 대시보드 또는 [보고서 대시보드에서](mail-flow-insights-v2.md) 직접 사용할 [수 없습니다.](view-mail-flow-reports.md)</span><span class="sxs-lookup"><span data-stu-id="11baa-121">This report isn't directly available in the [Mail flow dashboard](mail-flow-insights-v2.md) or in the [Reports dashboard](view-mail-flow-reports.md).</span></span> <span data-ttu-id="11baa-122">새 사용자를 전달하는 **전자 메일 정보에서** 인사이트 **New users forwarding email** 보기 링크를 클릭하는 하는 외에도 다음을 통해 보고서에 액세스합니다.</span><span class="sxs-lookup"><span data-stu-id="11baa-122">In addition to clicking the **See report associated with insight** link in the **New users forwarding email** insight, you get to the report by:</span></span>

- <span data-ttu-id="11baa-123">전달 알림 **보고서 링크를** 클릭하여 전달된 전자 [메일인 경우의 세부 정보에서 전달 알림 보고서 링크를 클릭합니다.](mfi-new-domains-being-forwarded-email.md)</span><span class="sxs-lookup"><span data-stu-id="11baa-123">Clicking the **Forwarding notifications report** link in the details of the [New domains being forwarded email insight](mfi-new-domains-being-forwarded-email.md).</span></span>
- <span data-ttu-id="11baa-124">여는 <https://protection.office.com/reportv2?id=MailFlowNewForwarding> 중 .</span><span class="sxs-lookup"><span data-stu-id="11baa-124">Opening <https://protection.office.com/reportv2?id=MailFlowNewForwarding>.</span></span>

### <a name="report-view-for-the-forwarding-modifications-report"></a><span data-ttu-id="11baa-125">전달 수정 보고서에 대한 보고서 보기</span><span class="sxs-lookup"><span data-stu-id="11baa-125">Report view for the Forwarding modifications report</span></span>

<span data-ttu-id="11baa-126">보고서 보기에서는 다음 차트를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="11baa-126">The following charts are available in the report view:</span></span>

- <span data-ttu-id="11baa-127">**데이터 표시: 새 전달 사용자:**</span><span class="sxs-lookup"><span data-stu-id="11baa-127">**Show data for: New forwarding users**:</span></span>

  ![전달 수정 보고서의 새 전달 사용자 보기](../../media/forwarding-modifications-report-new-forwarding-users.png)

- <span data-ttu-id="11baa-129">**데이터 표시: 새 전달 도메인:**</span><span class="sxs-lookup"><span data-stu-id="11baa-129">**Show data for: New forwarding domains**:</span></span>

  ![전달 수정 보고서의 새로운 도메인 보기](../../media/forwarding-modifications-report-new-forwarded-domains.png)

<span data-ttu-id="11baa-131">보고서 보기에서 **필터를** 클릭한 경우 시작 날짜와 종료 날짜로 날짜 **범위를** 지정할 **수 있습니다.**</span><span class="sxs-lookup"><span data-stu-id="11baa-131">If you click **Filters** in a report view, you can specify a date range with **Start date** and **End date**.</span></span>

### <a name="details-table-view-for-the-forwarding-modifications-report"></a><span data-ttu-id="11baa-132">전달 수정 보고서에 대한 세부 정보 표 보기</span><span class="sxs-lookup"><span data-stu-id="11baa-132">Details table view for the Forwarding modifications report</span></span>

<span data-ttu-id="11baa-133">세부 정보 **표를 보기를**클릭하면 표시되는 정보는 검색 하고 있는 차트에 따라 달라지게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="11baa-133">If you click **View details table**, the information that's shown depends on the chart you were looking at:</span></span>

- <span data-ttu-id="11baa-134">**데이터 표시: 새 전달 사용자:**</span><span class="sxs-lookup"><span data-stu-id="11baa-134">**Show data for: New forwarding users**:</span></span>

  - <span data-ttu-id="11baa-135">**이름:** 보낸 사람의 전자 메일 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="11baa-135">**Name**: The email address of the sender.</span></span>
  - <span data-ttu-id="11baa-136">**전달 유형**</span><span class="sxs-lookup"><span data-stu-id="11baa-136">**Forwarding type**</span></span>
  - <span data-ttu-id="11baa-137">**받는 사람 주소**</span><span class="sxs-lookup"><span data-stu-id="11baa-137">**Recipient address**</span></span>
  - <span data-ttu-id="11baa-138">**세부 정보**</span><span class="sxs-lookup"><span data-stu-id="11baa-138">**Details**</span></span>
  - <span data-ttu-id="11baa-139">**개수**</span><span class="sxs-lookup"><span data-stu-id="11baa-139">**Count**</span></span>
  - <span data-ttu-id="11baa-140">**첫 번째 전달 날짜**</span><span class="sxs-lookup"><span data-stu-id="11baa-140">**First forward date**</span></span>

- <span data-ttu-id="11baa-141">**데이터 표시: 새 전달 도메인:**</span><span class="sxs-lookup"><span data-stu-id="11baa-141">**Show data for: New forwarding domains**:</span></span>

  - <span data-ttu-id="11baa-142">**이름:** 보낸 사람의 전자 메일 도메인입니다.</span><span class="sxs-lookup"><span data-stu-id="11baa-142">**Name**: The email domain of the sender.</span></span>
  - <span data-ttu-id="11baa-143">**전달 유형**</span><span class="sxs-lookup"><span data-stu-id="11baa-143">**Forwarding type**</span></span>
  - <span data-ttu-id="11baa-144">**받는 사람 주소**</span><span class="sxs-lookup"><span data-stu-id="11baa-144">**Recipient address**</span></span>
  - <span data-ttu-id="11baa-145">**세부 정보**</span><span class="sxs-lookup"><span data-stu-id="11baa-145">**Details**</span></span>
  - <span data-ttu-id="11baa-146">**개수**</span><span class="sxs-lookup"><span data-stu-id="11baa-146">**Count**</span></span>
  - <span data-ttu-id="11baa-147">**첫 번째 전달 날짜**</span><span class="sxs-lookup"><span data-stu-id="11baa-147">**First forward date**</span></span>

<span data-ttu-id="11baa-148">세부 정보 **보기에서 필터를** 클릭한 경우 시작 날짜와 종료 날짜로 날짜 **범위를** 지정할 **수 있습니다.**</span><span class="sxs-lookup"><span data-stu-id="11baa-148">If you click **Filters** in a details table view, you can specify a date range with **Start date** and **End date**.</span></span>

<span data-ttu-id="11baa-149">표에서 행을 선택하면 다음 정보와 함께 **세부** 정보 플라이아웃이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="11baa-149">If you select a row from the table, a **Details** flyout appears with the following information:</span></span>

- <span data-ttu-id="11baa-150">**이름:** 이 주소는 보낸 사람의 전자 메일 주소(표시 데이터 **보기: 새** 전달 사용자 보기) 또는 보낸 사람의 전자 메일 도메인(표시 **데이터: 새 전달 도메인 보기)입니다.**</span><span class="sxs-lookup"><span data-stu-id="11baa-150">**Name**: This is either the sender's email address (from **Show data for: New forwarding users** view) or the sender's email domain (from **Show data for: New forwarding domains** view).</span></span>
- <span data-ttu-id="11baa-151">**전달 유형**</span><span class="sxs-lookup"><span data-stu-id="11baa-151">**Forwarding type**</span></span>
- <span data-ttu-id="11baa-152">**받는 사람**</span><span class="sxs-lookup"><span data-stu-id="11baa-152">**Recipient**</span></span>
- <span data-ttu-id="11baa-153">**세부 정보**</span><span class="sxs-lookup"><span data-stu-id="11baa-153">**Details**</span></span>
- <span data-ttu-id="11baa-154">**개수**</span><span class="sxs-lookup"><span data-stu-id="11baa-154">**Count**</span></span>
- <span data-ttu-id="11baa-155">**시작 날짜**</span><span class="sxs-lookup"><span data-stu-id="11baa-155">**Start date**</span></span>
- <span data-ttu-id="11baa-156">**권장 사항:** 여기서는 링크를 클릭하여 Microsoft 365 관리 센터에서 사용자를 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="11baa-156">**Recommendation**: From here, you can click the link to manage the user in the Microsoft 365 admin center.</span></span>

![전달 수정 보고서의 새 전달 사용자 보기에 대한 세부 정보 표시에서 플라인 세부 정보](../../media/mfi-forwarding-modifications-report-new-forwarding-users-view-details-table-details.png)

<span data-ttu-id="11baa-158">보고서 보기로 돌아가려면 보고서 **보기를 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="11baa-158">To go back to the reports view, click **View report**.</span></span>

## <a name="related-topics"></a><span data-ttu-id="11baa-159">관련 항목</span><span class="sxs-lookup"><span data-stu-id="11baa-159">Related topics</span></span>

<span data-ttu-id="11baa-160">메일 흐름 대시보드의 기타 정보에 대한 내용은 규정 준수 센터의 [보안 흐름 정보를 & 참조하세요.](mail-flow-insights-v2.md)</span><span class="sxs-lookup"><span data-stu-id="11baa-160">For information about other insights in the Mail flow dashboard, see [Mail flow insights in the Security & Compliance Center](mail-flow-insights-v2.md).</span></span>
