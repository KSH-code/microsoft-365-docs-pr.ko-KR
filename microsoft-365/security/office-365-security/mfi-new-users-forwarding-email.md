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
description: 관리자는 보안 & 준수 센터에서 전자 메일을 전달 하는 새 사용자를 사용 하 여 조직의 사용자가 새 도메인으로 메시지를 전달 하는 경우 조사 하는 방법을 배울 수 있습니다.
ms.openlocfilehash: 42f8c536f8a8a1421d97726c7af432c01d053b05
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/22/2020
ms.locfileid: "48200658"
---
# <a name="new-users-forwarding-email-insight-in-the-security--compliance-center"></a><span data-ttu-id="843b0-103">보안 & 준수 센터에서 전자 메일을 전달 하는 새 사용자</span><span class="sxs-lookup"><span data-stu-id="843b0-103">New users forwarding email insight in the Security & Compliance Center</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="843b0-104">조직의 새 사용자 계정이 갑자기 외부 도메인으로 전자 메일 메시지를 전달 하기 시작 하면 의심 스러운 것입니다.</span><span class="sxs-lookup"><span data-stu-id="843b0-104">It's suspicious when new user accounts in your organization suddenly start forwarding email messages to external domains.</span></span>

<span data-ttu-id="843b0-105">[보안 & 준수 센터](https://protection.office.com) 에 **전달 되는 새 도메인** 은 조직에서 새로 만든 사용자가 외부 도메인으로 메시지를 전달 하는 경우 사용자에 게 알려 줍니다.</span><span class="sxs-lookup"><span data-stu-id="843b0-105">The **New domains being forwarded email** insight in the [Security & Compliance Center](https://protection.office.com) notifies you when newly-created users in your organization are forwarding messages to external domains.</span></span> <span data-ttu-id="843b0-106">이 조건은 손상 된 관리자 계정을 사용 하 여 새 사용자를 만드는 것을 나타낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="843b0-106">This condition could indicate compromised admin accounts were used to create the new users.</span></span> <span data-ttu-id="843b0-107">계정이 손상 된 것으로 의심 되는 경우 [손상 된 전자 메일 계정에 응답](https://docs.microsoft.com/microsoft-365/security/office-365-security/responding-to-a-compromised-email-account)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="843b0-107">If you suspect the accounts have been compromised, see [Responding to a compromised email account](https://docs.microsoft.com/microsoft-365/security/office-365-security/responding-to-a-compromised-email-account).</span></span>

<span data-ttu-id="843b0-108">이 통찰력은 문제가 검색 된 경우에만 나타나며 [전달 보고서](view-mail-flow-reports.md#forwarding-report) 페이지에 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="843b0-108">This insight appears only when the issue is detected, and it appears on the [Forwarding report](view-mail-flow-reports.md#forwarding-report) page.</span></span>

![전자 메일을 전달하는 새 사용자](../../media/mfi-new-users-forwarding-email.png)

<span data-ttu-id="843b0-110">위젯을 클릭 하면이 항목의 뒷부분에 설명 된 대로 [전달 수정 보고서](#forwarding-modifications-report) 에 대 한 링크를 포함 하 여 전달 된 메시지에 대 한 자세한 정보를 확인할 수 있는 플라이 아웃이 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="843b0-110">When you click on the widget, a flyout appears where you can find more details about the forwarded messages, including a link to the [Forwarding modifications report](#forwarding-modifications-report) as described later in this topic.</span></span>

![전자 메일 통찰력을 전달 하는 새 사용자를 클릭 하면 나타나는 세부 정보 플라이 아웃](../../media/mfi-new-users-forwarding-email-details.png)

<span data-ttu-id="843b0-112">**보고서** 대시보드 또는 사이트의 **최상위 insights & 추천** 영역에서 **모두 보기** 를 클릭 한 후에는이 세부 정보 페이지로 이동할 수도 있습니다 \> **Dashboard** <https://protection.office.com/insightdashboard> .</span><span class="sxs-lookup"><span data-stu-id="843b0-112">You can also get to this details page when you select the insight after you click **View all** in the **Top insights & recommendations** area on (**Reports** \> **Dashboard** or <https://protection.office.com/insightdashboard>).</span></span>

<span data-ttu-id="843b0-113">다음 섹션에서 설명 하는 것 처럼 **전달 수정 보고서** 로 이동 하려면 **자세한 정보 표시 링크와 연결 된 보고서 보기** 를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="843b0-113">You can click the **See report associated with insight** link to go to the **Forwarding modifications report** as described in the next section.</span></span>

## <a name="forwarding-modifications-report"></a><span data-ttu-id="843b0-114">전달 수정 보고서</span><span class="sxs-lookup"><span data-stu-id="843b0-114">Forwarding modifications report</span></span>

<span data-ttu-id="843b0-115">**전달 수정 보고서** 에는 조직의 보낸 사람이 자동으로 전달 되는 메시지에 대 한 세부 정보가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="843b0-115">The **Forwarding modifications report** shows details about messages that are being automatically forwarded from senders in your organization:</span></span>

- <span data-ttu-id="843b0-116">외부 도메인으로 메시지를 전달 하는 새로 만든 계정입니다.</span><span class="sxs-lookup"><span data-stu-id="843b0-116">Newly-created accounts that are forwarding messages to external domains.</span></span>
- <span data-ttu-id="843b0-117">조직의 다른 보낸 사람이 전달 하지 않은 외부 도메인으로 메시지를 전달 하는 계정입니다.</span><span class="sxs-lookup"><span data-stu-id="843b0-117">Accounts that are forwarding messages to external domains that have never been forwarded to by other senders in your organization.</span></span>

<span data-ttu-id="843b0-118">이러한 유형의 전달 메시지는 보안 또는 준수 위험을 초래할 수 있으며, 손상 된 계정을 나타낼 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="843b0-118">These types of forwarded messages can pose a security or compliance risk, and might indicate compromised accounts.</span></span>

<span data-ttu-id="843b0-119">보고서에 포함 된 데이터는 최대 90 일입니다.</span><span class="sxs-lookup"><span data-stu-id="843b0-119">The report contains data for up to 90 days.</span></span> <span data-ttu-id="843b0-120">기본적으로 보고서에는 최근 7 일간의 데이터가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="843b0-120">By default, the report shows data for the last 7 days.</span></span>

<span data-ttu-id="843b0-121">이 보고서는 [메일 흐름 대시보드](mail-flow-insights-v2.md) 또는 [보고서 대시보드에서](view-mail-flow-reports.md)직접 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="843b0-121">This report isn't directly available in the [Mail flow dashboard](mail-flow-insights-v2.md) or in the [Reports dashboard](view-mail-flow-reports.md).</span></span> <span data-ttu-id="843b0-122">**전자 메일을 전달 하는 새 사용자** 의 **통찰력 링크와 연결 된 보고서 보기** 를 클릭 하는 것 외에 다음과 같은 방법으로 보고서에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="843b0-122">In addition to clicking the **See report associated with insight** link in the **New users forwarding email** insight, you get to the report by:</span></span>

- <span data-ttu-id="843b0-123">[전달 되는 새 도메인](mfi-new-domains-being-forwarded-email.md)의 세부 정보에서 **전달 알림 보고서** 링크를 클릭 하 여 전자 메일을 파악 합니다.</span><span class="sxs-lookup"><span data-stu-id="843b0-123">Clicking the **Forwarding notifications report** link in the details of the [New domains being forwarded email insight](mfi-new-domains-being-forwarded-email.md).</span></span>
- <span data-ttu-id="843b0-124">열기 <https://protection.office.com/reportv2?id=MailFlowNewForwarding> 입니다.</span><span class="sxs-lookup"><span data-stu-id="843b0-124">Opening <https://protection.office.com/reportv2?id=MailFlowNewForwarding>.</span></span>

### <a name="report-view-for-the-forwarding-modifications-report"></a><span data-ttu-id="843b0-125">전달 수정 보고서에 대 한 보고서 보기</span><span class="sxs-lookup"><span data-stu-id="843b0-125">Report view for the Forwarding modifications report</span></span>

<span data-ttu-id="843b0-126">보고서 보기에서는 다음과 같은 차트를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="843b0-126">The following charts are available in the report view:</span></span>

- <span data-ttu-id="843b0-127">**데이터 표시: 새 전달 사용자**:</span><span class="sxs-lookup"><span data-stu-id="843b0-127">**Show data for: New forwarding users**:</span></span>

  ![전달 수정 보고서의 새 전달 사용자 보기](../../media/forwarding-modifications-report-new-forwarding-users.png)

- <span data-ttu-id="843b0-129">**데이터 표시: 새 전달 도메인**:</span><span class="sxs-lookup"><span data-stu-id="843b0-129">**Show data for: New forwarding domains**:</span></span>

  ![전달 수정 보고서의 새 전달 된 도메인 보기](../../media/forwarding-modifications-report-new-forwarded-domains.png)

<span data-ttu-id="843b0-131">보고서 보기에서 **필터** 를 클릭 하면 **시작 날짜** 및 **종료 날짜**와 함께 날짜 범위를 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="843b0-131">If you click **Filters** in a report view, you can specify a date range with **Start date** and **End date**.</span></span>

### <a name="details-table-view-for-the-forwarding-modifications-report"></a><span data-ttu-id="843b0-132">전달 수정 보고서에 대 한 세부 정보 테이블 보기</span><span class="sxs-lookup"><span data-stu-id="843b0-132">Details table view for the Forwarding modifications report</span></span>

<span data-ttu-id="843b0-133">**세부 정보 표 보기**를 클릭 하면 표시 되는 정보는 보고 있는 차트에 따라 달라 집니다.</span><span class="sxs-lookup"><span data-stu-id="843b0-133">If you click **View details table**, the information that's shown depends on the chart you were looking at:</span></span>

- <span data-ttu-id="843b0-134">**데이터 표시: 새 전달 사용자**:</span><span class="sxs-lookup"><span data-stu-id="843b0-134">**Show data for: New forwarding users**:</span></span>

  - <span data-ttu-id="843b0-135">**이름**: 보낸 사람의 전자 메일 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="843b0-135">**Name**: The email address of the sender.</span></span>
  - <span data-ttu-id="843b0-136">**전달 유형**</span><span class="sxs-lookup"><span data-stu-id="843b0-136">**Forwarding type**</span></span>
  - <span data-ttu-id="843b0-137">**받는 사람 주소**</span><span class="sxs-lookup"><span data-stu-id="843b0-137">**Recipient address**</span></span>
  - <span data-ttu-id="843b0-138">**세부 정보**</span><span class="sxs-lookup"><span data-stu-id="843b0-138">**Details**</span></span>
  - <span data-ttu-id="843b0-139">**개수**</span><span class="sxs-lookup"><span data-stu-id="843b0-139">**Count**</span></span>
  - <span data-ttu-id="843b0-140">**첫 번째 전달 날짜**</span><span class="sxs-lookup"><span data-stu-id="843b0-140">**First forward date**</span></span>

- <span data-ttu-id="843b0-141">**데이터 표시: 새 전달 도메인**:</span><span class="sxs-lookup"><span data-stu-id="843b0-141">**Show data for: New forwarding domains**:</span></span>

  - <span data-ttu-id="843b0-142">**이름**: 보낸 사람의 전자 메일 도메인입니다.</span><span class="sxs-lookup"><span data-stu-id="843b0-142">**Name**: The email domain of the sender.</span></span>
  - <span data-ttu-id="843b0-143">**전달 유형**</span><span class="sxs-lookup"><span data-stu-id="843b0-143">**Forwarding type**</span></span>
  - <span data-ttu-id="843b0-144">**받는 사람 주소**</span><span class="sxs-lookup"><span data-stu-id="843b0-144">**Recipient address**</span></span>
  - <span data-ttu-id="843b0-145">**세부 정보**</span><span class="sxs-lookup"><span data-stu-id="843b0-145">**Details**</span></span>
  - <span data-ttu-id="843b0-146">**개수**</span><span class="sxs-lookup"><span data-stu-id="843b0-146">**Count**</span></span>
  - <span data-ttu-id="843b0-147">**첫 번째 전달 날짜**</span><span class="sxs-lookup"><span data-stu-id="843b0-147">**First forward date**</span></span>

<span data-ttu-id="843b0-148">세부 정보 표 보기에서 **필터** 를 클릭 하면 **시작 날짜** 및 **종료 날짜**와 함께 날짜 범위를 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="843b0-148">If you click **Filters** in a details table view, you can specify a date range with **Start date** and **End date**.</span></span>

<span data-ttu-id="843b0-149">표에서 행을 선택 하면 다음과 같은 정보가 포함 된 **세부 정보** 플라이 아웃이 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="843b0-149">If you select a row from the table, a **Details** flyout appears with the following information:</span></span>

- <span data-ttu-id="843b0-150">**Name**: 보낸 사람의 전자 메일 주소 ( **새 착신 전환 사용자** 보기) 또는 보낸 사람의 전자 메일 도메인 ( **데이터 표시 위치: 새 포워딩 도메인** 보기)입니다.</span><span class="sxs-lookup"><span data-stu-id="843b0-150">**Name**: This is either the sender's email address (from **Show data for: New forwarding users** view) or the sender's email domain (from **Show data for: New forwarding domains** view).</span></span>
- <span data-ttu-id="843b0-151">**전달 유형**</span><span class="sxs-lookup"><span data-stu-id="843b0-151">**Forwarding type**</span></span>
- <span data-ttu-id="843b0-152">**받는 사람**</span><span class="sxs-lookup"><span data-stu-id="843b0-152">**Recipient**</span></span>
- <span data-ttu-id="843b0-153">**세부 정보**</span><span class="sxs-lookup"><span data-stu-id="843b0-153">**Details**</span></span>
- <span data-ttu-id="843b0-154">**개수**</span><span class="sxs-lookup"><span data-stu-id="843b0-154">**Count**</span></span>
- <span data-ttu-id="843b0-155">**시작 날짜**</span><span class="sxs-lookup"><span data-stu-id="843b0-155">**Start date**</span></span>
- <span data-ttu-id="843b0-156">**권장 사항**: 여기서는 Microsoft 365 관리 센터에서 사용자를 관리 하기 위한 링크를 클릭할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="843b0-156">**Recommendation**: From here, you can click the link to manage the user in the Microsoft 365 admin center.</span></span>

![전달 수정 보고서의 새 전달 사용자 보기의 세부 정보 테이블에서 정보 플라이 아웃](../../media/mfi-forwarding-modifications-report-new-forwarding-users-view-details-table-details.png)

<span data-ttu-id="843b0-158">보고서 보기로 돌아가려면 **보고서 보기**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="843b0-158">To go back to the reports view, click **View report**.</span></span>

## <a name="related-topics"></a><span data-ttu-id="843b0-159">관련 항목</span><span class="sxs-lookup"><span data-stu-id="843b0-159">Related topics</span></span>

<span data-ttu-id="843b0-160">메일 흐름 대시보드의 다른 정보에 대 한 자세한 내용은 [Security & 준수 센터의 메일 흐름 정보](mail-flow-insights-v2.md)를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="843b0-160">For information about other insights in the Mail flow dashboard, see [Mail flow insights in the Security & Compliance Center](mail-flow-insights-v2.md).</span></span>
