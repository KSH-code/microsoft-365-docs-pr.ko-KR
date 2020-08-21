---
title: 메일 흐름 대시보드의 SMTP 인증 클라이언트 정보 및 보고
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: ''
ms.custom:
- seo-marvel-apr2020
description: 관리자는 보안 & 준수 센터의 메일 흐름 대시보드에서 SMTP 인증 인사이트를 사용하고 보고서에 대해 SMTP AUTH(인증된 SMTP)를 사용하여 전자 메일 메시지를 보내는 조직의 전자 메일 보낸 사람을 모니터링하는 방법을 알아보세요.
ms.openlocfilehash: 65e5569bcd79caef071ee2103d18a4e985c19dbb
ms.sourcegitcommit: e12fa502bc216f6083ef5666f693a04bb727d4df
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/20/2020
ms.locfileid: "46826872"
---
# <a name="smtp-auth-clients-insight-and-report-in-the-security--compliance-center"></a><span data-ttu-id="fc5d2-103">보안 장치 준수 센터에서 SMTP & 보고</span><span class="sxs-lookup"><span data-stu-id="fc5d2-103">SMTP Auth clients insight and report in the Security & Compliance Center</span></span>

<span data-ttu-id="fc5d2-104">메일 **흐름 대시보드 및** 관련 SMTP [Mail flow dashboard](mail-flow-insights-v2.md) 인증 클라이언트 보고서는 [조직의](#smtp-auth-clients-report) 사용자 또는 시스템 계정별 SMTP AUTH 클라이언트 전송 프로토콜 사용을 강조합니다.</span><span class="sxs-lookup"><span data-stu-id="fc5d2-104">The **SMTP Auth clients** insight in the [Mail flow dashboard](mail-flow-insights-v2.md) and the associated [SMTP Auth clients report](#smtp-auth-clients-report) highlight the use of the SMTP AUTH client submission protocol by users or system accounts in your organization.</span></span> <span data-ttu-id="fc5d2-105">smtp.office365.com 끝점을 사용하는 이 레거시 프로토콜은 기본 인증만 제공하며, 해커뮤니티에서 전자 메일을 보내는 데 사용된다는 의심이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fc5d2-105">This legacy protocol (which uses the endpoint smtp.office365.com) only offers Basic authentication, and is susceptible to being used by compromised accounts to send email.</span></span> <span data-ttu-id="fc5d2-106">인사이트 및 보고서를 통해 SMTP AUTH 전자 메일 전송에 대한 비정상적 활동을 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fc5d2-106">The insight and report allow you to check for unusual activity for SMTP AUTH email submissions.</span></span> <span data-ttu-id="fc5d2-107">또한 SMTP AUTH를 사용하는 클라이언트 또는 장치에 대한 TLS 사용 현황 데이터도 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="fc5d2-107">It also shows the TLS usage data for clients or devices using SMTP AUTH.</span></span>

<span data-ttu-id="fc5d2-108">위록은 지난 7일 동안 SMTP Auth 프로토콜을 사용한 사용자 또는 서비스 계정의 수를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="fc5d2-108">The widget indicates the number of users or service accounts that have used the SMTP Auth protocol in the last 7 days.</span></span>

![준수 센터의 보안 흐름 대시보드에서 SMTP & 위산](../../media/mfi-smtp-auth-clients-report-widget.png)

<span data-ttu-id="fc5d2-110">위쪽에서 메시지 수를 클릭하면 SMTP Auth **클라이언트 플라이아웃이** 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="fc5d2-110">If you click the number of messages on the widget, an **SMTP Auth clients** flyout appears.</span></span> <span data-ttu-id="fc5d2-111">플라이아웃에서는 지난 한 주 동안의 TLS 사용량 및 볼륨을 집계적으로 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="fc5d2-111">The flyout provides an aggregated view of the TLS usage and volumes for the last week.</span></span>

![메일 흐름 대시보드에서 SMTP 인증 클라이언트 위산을 클릭한 후의 세부 정보 플라이아웃](../../media/mfi-smtp-auth-clients-report-details.png)

<span data-ttu-id="fc5d2-113">다음 섹션에 **설명된 바와 같이 SMTP** 인증 클라이언트 보고서 링크를 클릭하여 SMTP 인증 클라이언트 보고서로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="fc5d2-113">You can click the **SMTP Auth clients report** link to go to the SMTP Auth clients report as described in the next section.</span></span>

## <a name="smtp-auth-clients-report"></a><span data-ttu-id="fc5d2-114">SMTP 인증 클라이언트 보고서</span><span class="sxs-lookup"><span data-stu-id="fc5d2-114">SMTP Auth clients report</span></span>

### <a name="report-view-for-the-smtp-auth-clients-report"></a><span data-ttu-id="fc5d2-115">SMTP 인증 클라이언트 보고서 보고서 보기</span><span class="sxs-lookup"><span data-stu-id="fc5d2-115">Report view for the SMTP Auth clients report</span></span>

<span data-ttu-id="fc5d2-116">기본적으로 보고서는 지난 7일간의 데이터를 표시하지만 지난 90일 동안 데이터를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fc5d2-116">By default, the report shows data for the last 7 days, but data is available for the last 90 days.</span></span>

<span data-ttu-id="fc5d2-117">개요 섹션에는 다음 차트가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="fc5d2-117">The overview section contains the following charts:</span></span>

- <span data-ttu-id="fc5d2-118">**데이터 보기: 보내는 사람:** 기본적으로 차트는 모든 도메인에서 보낸 SMTP Auth 클라이언트**Show data for: All sender domains** 메시지 수를 표시합니다(기본적으로 모든 보낸 사람 도메인이 선택됨).</span><span class="sxs-lookup"><span data-stu-id="fc5d2-118">**View data by: Sending volume**: By default, the chart shows the number of SMTP Auth client messages that were sent from all domains (**Show data for: All sender domains** is selected by default).</span></span> <span data-ttu-id="fc5d2-119">특정 보낸 사람 도메인에 대한 표시 **Show data for** 데이터를 클릭하고 드롭다운 목록에서 보낸 사람 도메인을 선택하여 결과를 특정 보낸 사람 도메인으로 필터링할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fc5d2-119">You can filter the results to a specific sender domain by clicking **Show data for** and selecting the sender domain from the dropdown list.</span></span> <span data-ttu-id="fc5d2-120">특정 데이터 요소(일)를 가리치면 메시지 수가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="fc5d2-120">If you hover a specific data point (day), the number of messages is shown.</span></span>

  ![보안 및 준수 센터의 SMTP 인증 클라이언트 & 보내기](../../media/mfi-smtp-auth-clients-report-sending-volume-view.png)

- <span data-ttu-id="fc5d2-122">**데이터 보기: TLS 사용**: 이 차트는 선택한 기간 동안 모든 SMTP 인증 클라이언트 메시지에 대한 TLS 사용 비율을 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="fc5d2-122">**View data by: TLS Usage**: The chart shows the percentage of TLS usage for all SMTP Auth client messages during the selected time period.</span></span> <span data-ttu-id="fc5d2-123">이 차트를 통해 아직 이전 버전의 TLS를 사용하는 사용자 및 시스템 계정에 대해 확인하고 작업을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fc5d2-123">This chart allows you to identify and take action on users and system accounts that are still using older versions of TLS.</span></span>

  ![준수 센터의 보안 서비스 테이블에 있는 SMTP Auth 클라이언트의 TLS 사용 &](../../media/mfi-smtp-auth-clients-report-tls-usage-view.png)

<span data-ttu-id="fc5d2-125">보고서 보기에서 **필터를** 클릭한 경우 시작 날짜와 종료 날짜로 날짜 **범위를** 지정할 **수 있습니다.**</span><span class="sxs-lookup"><span data-stu-id="fc5d2-125">If you click **Filters** in a report view, you can specify a date range with **Start date** and **End date**.</span></span>

<span data-ttu-id="fc5d2-126">요청 **보고서를 클릭하여** 자세한 버전의 보고서를 전자 메일 메시지로 받습니다.</span><span class="sxs-lookup"><span data-stu-id="fc5d2-126">Click **Request report** to receive a more detailed version of the report in an email message.</span></span> <span data-ttu-id="fc5d2-127">날짜 범위 및 보고서를 받을 받는 사람을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fc5d2-127">You can specify the date range and the recipients to receive the report.</span></span>

### <a name="details-table-view-for-the-smtp-auth-clients-report"></a><span data-ttu-id="fc5d2-128">SMTP 인증 클라이언트 보고서의 세부 정보 표 보기</span><span class="sxs-lookup"><span data-stu-id="fc5d2-128">Details table view for the SMTP Auth clients report</span></span>

<span data-ttu-id="fc5d2-129">세부 정보 **표를 보기를**클릭하면 표시되는 정보는 검색 하고 있는 차트에 따라 달라지게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="fc5d2-129">If you click **View details table**, the information that's shown depends on the chart you were looking at:</span></span>

- <span data-ttu-id="fc5d2-130">**데이터 가져오기: 전송:** 테이블에 다음 정보가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="fc5d2-130">**View data by: Sending volume**: The following information is shown in a table:</span></span>

  - <span data-ttu-id="fc5d2-131">**보낸 사람 주소**</span><span class="sxs-lookup"><span data-stu-id="fc5d2-131">**Sender address**</span></span>
  - <span data-ttu-id="fc5d2-132">**메시지 수**</span><span class="sxs-lookup"><span data-stu-id="fc5d2-132">**Message count**</span></span>

  <span data-ttu-id="fc5d2-133">행을 선택하면 동일한 세부 정보가 플라이아웃에 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="fc5d2-133">If you select a row, the same details are shown in a flyout.</span></span>

- <span data-ttu-id="fc5d2-134">**데이터 보기: TLS 사용 현황:** 표에는 다음정보가 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fc5d2-134">**View data by: TLS Usage**: The following information is shown in a table:</span></span>

  - <span data-ttu-id="fc5d2-135">**보낸 사람 주소**</span><span class="sxs-lookup"><span data-stu-id="fc5d2-135">**Sender address**</span></span>
  - <span data-ttu-id="fc5d2-136">**TLS1.0%**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="fc5d2-136">**TLS1.0%**<sup>\*</sup></span></span>
  - <span data-ttu-id="fc5d2-137">**TLS1.1%**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="fc5d2-137">**TLS1.1%**<sup>\*</sup></span></span>
  - <span data-ttu-id="fc5d2-138">**TLS1.2%**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="fc5d2-138">**TLS1.2%**<sup>\*</sup></span></span>
  - <span data-ttu-id="fc5d2-139">**메시지 수**</span><span class="sxs-lookup"><span data-stu-id="fc5d2-139">**Message count**</span></span>

  <span data-ttu-id="fc5d2-140"><sup>\*</sup> 이 열에는 보낸 사람이 보낸 메시지의 백분율과 개수가 모두 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="fc5d2-140"><sup>\*</sup> This column shows both the percentage and number of messages from the sender.</span></span>

<span data-ttu-id="fc5d2-141">세부 정보 **보기에서 필터를** 클릭한 경우 시작 날짜와 종료 날짜로 날짜 **범위를** 지정할 **수 있습니다.**</span><span class="sxs-lookup"><span data-stu-id="fc5d2-141">If you click **Filters** in a details table view, you can specify a date range with **Start date** and **End date**.</span></span>

<span data-ttu-id="fc5d2-142">행을 선택하는 경우 다음과 유사한 세부 정보가 플라이아웃에 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="fc5d2-142">If you select a row, similar details are shown in a flyout:</span></span>

![SMTP 인증 클라이언트 보고서의 TLS 사용 현황 보기에 대한 세부 정보 표에서 가기 플라이아웃](../../media/mfi-smtp-auth-clients-report-tls-usage-view-view-details-table-details.png)

<span data-ttu-id="fc5d2-144">요청 **보고서를 클릭하여** 자세한 버전의 보고서를 전자 메일 메시지로 받습니다.</span><span class="sxs-lookup"><span data-stu-id="fc5d2-144">Click **Request report** to receive a more detailed version of the report in an email message.</span></span> <span data-ttu-id="fc5d2-145">날짜 범위 및 보고서를 받을 받는 사람을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fc5d2-145">You can specify the date range and the recipients to receive the report.</span></span>

<span data-ttu-id="fc5d2-146">보고서 보기로 돌아가려면 보고서 **보기를 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="fc5d2-146">To go back to the reports view, click **View report**.</span></span>

## <a name="related-topics"></a><span data-ttu-id="fc5d2-147">관련 항목</span><span class="sxs-lookup"><span data-stu-id="fc5d2-147">Related topics</span></span>

<span data-ttu-id="fc5d2-148">메일 흐름 대시보드의 기타 정보에 대한 내용은 규정 준수 센터의 [보안 흐름 정보를 & 참조하세요.](mail-flow-insights-v2.md)</span><span class="sxs-lookup"><span data-stu-id="fc5d2-148">For information about other insights in the Mail flow dashboard, see [Mail flow insights in the Security & Compliance Center](mail-flow-insights-v2.md).</span></span>
