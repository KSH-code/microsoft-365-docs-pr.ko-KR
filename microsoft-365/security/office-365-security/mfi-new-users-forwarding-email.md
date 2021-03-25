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
description: 관리자는 보안 및 준수 센터에서 새 사용자 전달 전자 메일 정보를 사용하여 조직의 사용자가 메시지를 새 도메인으로 전달하는 & 조사하는 방법을 배울 수 있습니다.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 807df82ca80e851554db7b8f373a5ca4af02a391
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/25/2021
ms.locfileid: "51206196"
---
# <a name="new-users-forwarding-email-insight-in-the-security--compliance-center"></a><span data-ttu-id="3a965-103">보안 및 준수 센터에서 전자 메일 정보를 전달하는 & 사용자</span><span class="sxs-lookup"><span data-stu-id="3a965-103">New users forwarding email insight in the Security & Compliance Center</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="3a965-104">**적용 대상**</span><span class="sxs-lookup"><span data-stu-id="3a965-104">**Applies to**</span></span>
- [<span data-ttu-id="3a965-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="3a965-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="3a965-106">Office 365용 Microsoft Defender 플랜 1 및 플랜 2</span><span class="sxs-lookup"><span data-stu-id="3a965-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="3a965-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="3a965-107">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

<span data-ttu-id="3a965-108">조직의 새 사용자 계정이 갑자기 외부 도메인에 전자 메일 메시지를 전달하기 시작하면 의심스러운 일입니다.</span><span class="sxs-lookup"><span data-stu-id="3a965-108">It's suspicious when new user accounts in your organization suddenly start forwarding email messages to external domains.</span></span>

<span data-ttu-id="3a965-109">보안 **&** 준수 센터에서 전달되는 [](https://protection.office.com) 새 도메인은 조직에서 새로 만든 사용자가 외부 도메인으로 메시지를 전달할 때 이를 사용자에게 통보합니다.</span><span class="sxs-lookup"><span data-stu-id="3a965-109">The **New domains being forwarded email** insight in the [Security & Compliance Center](https://protection.office.com) notifies you when newly-created users in your organization are forwarding messages to external domains.</span></span> <span data-ttu-id="3a965-110">이 조건은 손상된 관리자 계정을 사용하여 새 사용자를 만들었다는 것을 나타낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3a965-110">This condition could indicate compromised admin accounts were used to create the new users.</span></span> <span data-ttu-id="3a965-111">계정이 손상된 것으로 의심되는 경우 손상된 전자 메일 계정에 응답을 [참조하세요.](responding-to-a-compromised-email-account.md)</span><span class="sxs-lookup"><span data-stu-id="3a965-111">If you suspect the accounts have been compromised, see [Responding to a compromised email account](responding-to-a-compromised-email-account.md).</span></span>

<span data-ttu-id="3a965-112">이 인사이트는 문제가 검색된 경우만 표시되고 전달 보고서 페이지에 [표시됩니다.](view-mail-flow-reports.md#forwarding-report)</span><span class="sxs-lookup"><span data-stu-id="3a965-112">This insight appears only when the issue is detected, and it appears on the [Forwarding report](view-mail-flow-reports.md#forwarding-report) page.</span></span>

![전자 메일을 전달하는 새 사용자](../../media/mfi-new-users-forwarding-email.png)

<span data-ttu-id="3a965-114">위젯을 클릭하면 이 문서 나중에 설명된 전달 수정 보고서에 대한 링크를 포함하여 전달된 [](#forwarding-modifications-report) 메시지에 대한 자세한 정보를 찾을 수 있는 플라이아웃이 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="3a965-114">When you click on the widget, a flyout appears where you can find more details about the forwarded messages, including a link to the [Forwarding modifications report](#forwarding-modifications-report) as described later in this article.</span></span>

![새 사용자 전달 전자 메일 정보를 클릭한 후 나타나는 세부 정보 플라이아웃](../../media/mfi-new-users-forwarding-email-details.png)

<span data-ttu-id="3a965-116">또한 ( 보고서 대시보드 또는 **)의** 상위 인사이트 및 추천 영역에 있는 모든 정보 보기를 클릭한 & 세부 정보 페이지로 이동될 **수도**  \>  <https://protection.office.com/insightdashboard> 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3a965-116">You can also get to this details page when you select the insight after you click **View all** in the **Top insights & recommendations** area on (**Reports** \> **Dashboard** or <https://protection.office.com/insightdashboard>).</span></span>

<span data-ttu-id="3a965-117">다음 섹션에  설명된 바와 같이 인사이트와 연결된 보고서 보기 링크를 클릭하여 전달 수정 보고서로 이동하면 됩니다. </span><span class="sxs-lookup"><span data-stu-id="3a965-117">You can click the **See report associated with insight** link to go to the **Forwarding modifications report** as described in the next section.</span></span>

## <a name="forwarding-modifications-report"></a><span data-ttu-id="3a965-118">수정 내용 전달 보고서</span><span class="sxs-lookup"><span data-stu-id="3a965-118">Forwarding modifications report</span></span>

<span data-ttu-id="3a965-119">전달 **수정 보고서에는** 조직의 보낸 사람이 자동으로 전달하는 메시지에 대한 세부 정보가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="3a965-119">The **Forwarding modifications report** shows details about messages that are being automatically forwarded from senders in your organization:</span></span>

- <span data-ttu-id="3a965-120">외부 도메인으로 메시지를 전달하는 새로 만든 계정입니다.</span><span class="sxs-lookup"><span data-stu-id="3a965-120">Newly-created accounts that are forwarding messages to external domains.</span></span>
- <span data-ttu-id="3a965-121">조직의 다른 보낸 사람이 전달한 적이 없는 외부 도메인으로 메시지를 전달하는 계정입니다.</span><span class="sxs-lookup"><span data-stu-id="3a965-121">Accounts that are forwarding messages to external domains that have never been forwarded to by other senders in your organization.</span></span>

<span data-ttu-id="3a965-122">이러한 유형의 전달된 메시지는 보안 또는 규정 준수 위험을 내포할 수 있으며 계정 손상을 나타낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3a965-122">These types of forwarded messages can pose a security or compliance risk, and might indicate compromised accounts.</span></span>

<span data-ttu-id="3a965-123">보고서에는 최대 90일간의 데이터가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3a965-123">The report contains data for up to 90 days.</span></span> <span data-ttu-id="3a965-124">기본적으로 보고서에는 지난 7일간의 데이터가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="3a965-124">By default, the report shows data for the last 7 days.</span></span>

<span data-ttu-id="3a965-125">이 보고서는 메일 흐름 [](mail-flow-insights-v2.md) 대시보드 또는 보고서 대시보드에서 직접 사용할 [수 없습니다.](view-mail-flow-reports.md)</span><span class="sxs-lookup"><span data-stu-id="3a965-125">This report isn't directly available in the [Mail flow dashboard](mail-flow-insights-v2.md) or in the [Reports dashboard](view-mail-flow-reports.md).</span></span> <span data-ttu-id="3a965-126">새 사용자 전달  전자 메일 인사이트에서  인사이트와 연결된 보고서 보기 링크를 클릭하는 것 외에도 다음을 통해 보고서에 연결됩니다.</span><span class="sxs-lookup"><span data-stu-id="3a965-126">In addition to clicking the **See report associated with insight** link in the **New users forwarding email** insight, you get to the report by:</span></span>

- <span data-ttu-id="3a965-127">전달되는  새 도메인의 세부 정보에서 전달 알림 보고서 [링크를 클릭합니다.](mfi-new-domains-being-forwarded-email.md)</span><span class="sxs-lookup"><span data-stu-id="3a965-127">Clicking the **Forwarding notifications report** link in the details of the [New domains being forwarded email insight](mfi-new-domains-being-forwarded-email.md).</span></span>
- <span data-ttu-id="3a965-128">를 <https://protection.office.com/reportv2?id=MailFlowNewForwarding> 열기.</span><span class="sxs-lookup"><span data-stu-id="3a965-128">Opening <https://protection.office.com/reportv2?id=MailFlowNewForwarding>.</span></span>

### <a name="report-view-for-the-forwarding-modifications-report"></a><span data-ttu-id="3a965-129">전달 수정 보고서에 대한 보고서 보기</span><span class="sxs-lookup"><span data-stu-id="3a965-129">Report view for the Forwarding modifications report</span></span>

<span data-ttu-id="3a965-130">보고서 보기에서는 다음 차트를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3a965-130">The following charts are available in the report view:</span></span>

- <span data-ttu-id="3a965-131">**데이터 표시: 새** 전달 사용자:</span><span class="sxs-lookup"><span data-stu-id="3a965-131">**Show data for: New forwarding users**:</span></span>

  ![전달 수정 내용 보고서의 새 전달 사용자 보기](../../media/forwarding-modifications-report-new-forwarding-users.png)

- <span data-ttu-id="3a965-133">**데이터 표시: 새** 전달 도메인 :</span><span class="sxs-lookup"><span data-stu-id="3a965-133">**Show data for: New forwarding domains**:</span></span>

  ![전달 수정 내용 보고서의 새 전달된 도메인 보기](../../media/forwarding-modifications-report-new-forwarded-domains.png)

<span data-ttu-id="3a965-135">보고서 보기에서 **필터를** 클릭하면 시작 날짜 및  종료 날짜로 날짜 범위를 **지정할 수 있습니다.**</span><span class="sxs-lookup"><span data-stu-id="3a965-135">If you click **Filters** in a report view, you can specify a date range with **Start date** and **End date**.</span></span>

### <a name="details-table-view-for-the-forwarding-modifications-report"></a><span data-ttu-id="3a965-136">전달 수정 보고서의 세부 정보 테이블 보기</span><span class="sxs-lookup"><span data-stu-id="3a965-136">Details table view for the Forwarding modifications report</span></span>

<span data-ttu-id="3a965-137">세부 정보 **표 보기를** 클릭하면 표시되는 정보가 보고 있는 차트에 따라 다를 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3a965-137">If you click **View details table**, the information that's shown depends on the chart you were looking at:</span></span>

- <span data-ttu-id="3a965-138">**데이터 표시: 새** 전달 사용자:</span><span class="sxs-lookup"><span data-stu-id="3a965-138">**Show data for: New forwarding users**:</span></span>

  - <span data-ttu-id="3a965-139">**이름:** 보낸 사람 전자 메일 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="3a965-139">**Name**: The email address of the sender.</span></span>
  - <span data-ttu-id="3a965-140">**전달 유형**</span><span class="sxs-lookup"><span data-stu-id="3a965-140">**Forwarding type**</span></span>
  - <span data-ttu-id="3a965-141">**받는 사람 주소**</span><span class="sxs-lookup"><span data-stu-id="3a965-141">**Recipient address**</span></span>
  - <span data-ttu-id="3a965-142">**세부 정보**</span><span class="sxs-lookup"><span data-stu-id="3a965-142">**Details**</span></span>
  - <span data-ttu-id="3a965-143">**개수**</span><span class="sxs-lookup"><span data-stu-id="3a965-143">**Count**</span></span>
  - <span data-ttu-id="3a965-144">**첫 번째 전달 날짜**</span><span class="sxs-lookup"><span data-stu-id="3a965-144">**First forward date**</span></span>

- <span data-ttu-id="3a965-145">**데이터 표시: 새** 전달 도메인 :</span><span class="sxs-lookup"><span data-stu-id="3a965-145">**Show data for: New forwarding domains**:</span></span>

  - <span data-ttu-id="3a965-146">**이름:** 보낸 사람에 대한 전자 메일 도메인입니다.</span><span class="sxs-lookup"><span data-stu-id="3a965-146">**Name**: The email domain of the sender.</span></span>
  - <span data-ttu-id="3a965-147">**전달 유형**</span><span class="sxs-lookup"><span data-stu-id="3a965-147">**Forwarding type**</span></span>
  - <span data-ttu-id="3a965-148">**받는 사람 주소**</span><span class="sxs-lookup"><span data-stu-id="3a965-148">**Recipient address**</span></span>
  - <span data-ttu-id="3a965-149">**세부 정보**</span><span class="sxs-lookup"><span data-stu-id="3a965-149">**Details**</span></span>
  - <span data-ttu-id="3a965-150">**개수**</span><span class="sxs-lookup"><span data-stu-id="3a965-150">**Count**</span></span>
  - <span data-ttu-id="3a965-151">**첫 번째 전달 날짜**</span><span class="sxs-lookup"><span data-stu-id="3a965-151">**First forward date**</span></span>

<span data-ttu-id="3a965-152">세부 정보 테이블 보기에서 **필터를** 클릭하면 시작 날짜  및 종료 날짜로 날짜 범위를 **지정할 수 있습니다.**</span><span class="sxs-lookup"><span data-stu-id="3a965-152">If you click **Filters** in a details table view, you can specify a date range with **Start date** and **End date**.</span></span>

<span data-ttu-id="3a965-153">표에서 행을 선택하면 세부  정보 플라이아웃이 다음 정보와 함께 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="3a965-153">If you select a row from the table, a **Details** flyout appears with the following information:</span></span>

- <span data-ttu-id="3a965-154">**이름:** 이 주소는 보낸 사람 전자 메일  주소(데이터 표시: 새 전달 사용자 보기에서) 또는 보낸 사람 전자 메일 도메인(데이터 **표시:** 새 전달 도메인 보기에서)입니다.</span><span class="sxs-lookup"><span data-stu-id="3a965-154">**Name**: This is either the sender's email address (from **Show data for: New forwarding users** view) or the sender's email domain (from **Show data for: New forwarding domains** view).</span></span>
- <span data-ttu-id="3a965-155">**전달 유형**</span><span class="sxs-lookup"><span data-stu-id="3a965-155">**Forwarding type**</span></span>
- <span data-ttu-id="3a965-156">**받는 사람**</span><span class="sxs-lookup"><span data-stu-id="3a965-156">**Recipient**</span></span>
- <span data-ttu-id="3a965-157">**세부 정보**</span><span class="sxs-lookup"><span data-stu-id="3a965-157">**Details**</span></span>
- <span data-ttu-id="3a965-158">**개수**</span><span class="sxs-lookup"><span data-stu-id="3a965-158">**Count**</span></span>
- <span data-ttu-id="3a965-159">**시작 날짜**</span><span class="sxs-lookup"><span data-stu-id="3a965-159">**Start date**</span></span>
- <span data-ttu-id="3a965-160">**권장 사항:** 여기에서 링크를 클릭하여 Microsoft 365 관리 센터에서 사용자를 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3a965-160">**Recommendation**: From here, you can click the link to manage the user in the Microsoft 365 admin center.</span></span>

![전달 수정 보고서의 새 전달 사용자 보기의 세부 정보 테이블에서 플라이아웃 세부 정보](../../media/mfi-forwarding-modifications-report-new-forwarding-users-view-details-table-details.png)

<span data-ttu-id="3a965-162">보고서 보기로 돌아가려면 보고서 **보기 를 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="3a965-162">To go back to the reports view, click **View report**.</span></span>

## <a name="related-topics"></a><span data-ttu-id="3a965-163">관련 항목</span><span class="sxs-lookup"><span data-stu-id="3a965-163">Related topics</span></span>

<span data-ttu-id="3a965-164">메일 흐름 대시보드의 다른 인사이트에 대한 자세한 내용은 보안 및 준수 센터의 메일 [흐름 & 참조하세요.](mail-flow-insights-v2.md)</span><span class="sxs-lookup"><span data-stu-id="3a965-164">For information about other insights in the Mail flow dashboard, see [Mail flow insights in the Security & Compliance Center](mail-flow-insights-v2.md).</span></span>
