---
title: SMTP 인증 클라이언트의 메일 흐름 대시보드 이해 및 보고
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
description: 관리자는 보안 & 준수 센터의 메일 흐름 대시보드에서 SMTP 인증 통찰력 및 보고서를 사용 하 여 인증 된 SMTP (SMTP 인증)를 사용 하는 조직의 전자 메일 보낸 사람을 모니터링 하 여 전자 메일 메시지를 보내는 방법을 확인할 수 있습니다.
ms.openlocfilehash: 4123edcfa08e31217dcd6a29186492bc036fa7a0
ms.sourcegitcommit: 9ce9001aa41172152458da27c1c52825355f426d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/03/2020
ms.locfileid: "47357437"
---
# <a name="smtp-auth-clients-insight-and-report-in-the-security--compliance-center"></a><span data-ttu-id="d1405-103">SMTP 인증 클라이언트에서 보안 & 준수 센터의 통찰력 및 보고</span><span class="sxs-lookup"><span data-stu-id="d1405-103">SMTP Auth clients insight and report in the Security & Compliance Center</span></span>

<span data-ttu-id="d1405-104">[보안 & 준수 센터](https://protection.office.com) 의 [메일 흐름 대시보드](mail-flow-insights-v2.md) 및 연결 된 [smtp 인증 클라이언트 보고서](#smtp-auth-clients-report) 에 있는 **smtp 인증 클라이언트** 는 조직의 사용자 또는 시스템 계정에의 한 smtp 인증 클라이언트 전송 프로토콜 사용을 강조 합니다.</span><span class="sxs-lookup"><span data-stu-id="d1405-104">The **SMTP Auth clients** insight in the [Mail flow dashboard](mail-flow-insights-v2.md) and the associated [SMTP Auth clients report](#smtp-auth-clients-report) in the [Security & Compliance Center](https://protection.office.com) highlight the use of the SMTP AUTH client submission protocol by users or system accounts in your organization.</span></span> <span data-ttu-id="d1405-105">끝점 smtp.office365.com를 사용 하는이 레거시 프로토콜은 기본 인증만 제공 하며 손상 된 계정에서 전자 메일을 보내기 위해 사용 하는 것이 취약 합니다.</span><span class="sxs-lookup"><span data-stu-id="d1405-105">This legacy protocol (which uses the endpoint smtp.office365.com) only offers Basic authentication, and is susceptible to being used by compromised accounts to send email.</span></span> <span data-ttu-id="d1405-106">통찰력 및 보고서를 사용 하면 SMTP 인증 전자 메일 전송에 대 한 비정상적인 활동을 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d1405-106">The insight and report allow you to check for unusual activity for SMTP AUTH email submissions.</span></span> <span data-ttu-id="d1405-107">또한 SMTP 인증을 사용 하는 클라이언트나 장치에 대 한 TLS 사용 현황 데이터를 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="d1405-107">It also shows the TLS usage data for clients or devices using SMTP AUTH.</span></span>

<span data-ttu-id="d1405-108">위젯은 지난 7 일 이내에 SMTP 인증 프로토콜을 사용한 사용자 또는 서비스 계정 수를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="d1405-108">The widget indicates the number of users or service accounts that have used the SMTP Auth protocol in the last 7 days.</span></span>

![보안 & 준수 센터의 메일 흐름 대시보드에 있는 SMTP 인증 클라이언트 위젯](../../media/mfi-smtp-auth-clients-report-widget.png)

<span data-ttu-id="d1405-110">위젯의 메시지 수를 클릭 하면 **SMTP 인증 클라이언트** 플라이 아웃이 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="d1405-110">If you click the number of messages on the widget, an **SMTP Auth clients** flyout appears.</span></span> <span data-ttu-id="d1405-111">플라이 아웃은 지난 주에 대 한 TLS 사용 및 볼륨의 집계 된 보기를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="d1405-111">The flyout provides an aggregated view of the TLS usage and volumes for the last week.</span></span>

![메일 흐름 대시보드에서 SMTP 인증 클라이언트 위젯을 클릭 한 후의 세부 정보 플라이 아웃](../../media/mfi-smtp-auth-clients-report-details.png)

<span data-ttu-id="d1405-113">**Smtp 인증 클라이언트 보고서** 링크를 클릭 하 여 다음 섹션에 설명 된 대로 smtp 인증 클라이언트 보고서로 이동할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d1405-113">You can click the **SMTP Auth clients report** link to go to the SMTP Auth clients report as described in the next section.</span></span>

## <a name="smtp-auth-clients-report"></a><span data-ttu-id="d1405-114">SMTP 인증 클라이언트 보고서</span><span class="sxs-lookup"><span data-stu-id="d1405-114">SMTP Auth clients report</span></span>

### <a name="report-view-for-the-smtp-auth-clients-report"></a><span data-ttu-id="d1405-115">SMTP 인증 클라이언트 보고서에 대 한 보고서 보기</span><span class="sxs-lookup"><span data-stu-id="d1405-115">Report view for the SMTP Auth clients report</span></span>

<span data-ttu-id="d1405-116">기본적으로 보고서에는 최근 7 일 동안의 데이터가 표시 되지만 최근 90 일 동안 데이터를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d1405-116">By default, the report shows data for the last 7 days, but data is available for the last 90 days.</span></span>

<span data-ttu-id="d1405-117">Overview (개요) 섹션에는 다음 차트가 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d1405-117">The overview section contains the following charts:</span></span>

- <span data-ttu-id="d1405-118">**데이터 보기 기준: 보내는 볼륨**: 기본적으로 차트에는 모든 도메인에서 전송 된 SMTP 인증 클라이언트 메시지의 수가 표시 됩니다 (기본적으로**모든 보낸 사람 도메인** 을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="d1405-118">**View data by: Sending volume**: By default, the chart shows the number of SMTP Auth client messages that were sent from all domains (**Show data for: All sender domains** is selected by default).</span></span> <span data-ttu-id="d1405-119">드롭다운 목록에서 **데이터 표시** 를 클릭 하 고 보낸 사람 도메인을 선택 하 여 결과를 특정 보낸 사람 도메인으로 필터링 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d1405-119">You can filter the results to a specific sender domain by clicking **Show data for** and selecting the sender domain from the dropdown list.</span></span> <span data-ttu-id="d1405-120">특정 데이터 요소 (일)를 가리키면 메시지 수가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d1405-120">If you hover a specific data point (day), the number of messages is shown.</span></span>

  ![보안 & 준수 센터의 SMTP 인증 클라이언트 보고서에서 보내는 볼륨 보기](../../media/mfi-smtp-auth-clients-report-sending-volume-view.png)

- <span data-ttu-id="d1405-122">**데이터 보기 기준: TLS 사용**: 차트에는 선택한 기간 동안 모든 SMTP 인증 클라이언트 메시지의 TLS 사용 백분율이 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d1405-122">**View data by: TLS Usage**: The chart shows the percentage of TLS usage for all SMTP Auth client messages during the selected time period.</span></span> <span data-ttu-id="d1405-123">이 차트에서는 이전 버전의 TLS를 계속 사용 하는 사용자 및 시스템 계정을 식별 하 고 작업을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d1405-123">This chart allows you to identify and take action on users and system accounts that are still using older versions of TLS.</span></span>

  ![보안 & 준수 센터의 SMTP 인증 클라이언트 보고서의 TLS 사용 보기](../../media/mfi-smtp-auth-clients-report-tls-usage-view.png)

<span data-ttu-id="d1405-125">보고서 보기에서 **필터** 를 클릭 하면 **시작 날짜** 및 **종료 날짜**와 함께 날짜 범위를 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d1405-125">If you click **Filters** in a report view, you can specify a date range with **Start date** and **End date**.</span></span>

<span data-ttu-id="d1405-126">자세한 보고서 버전을 전자 메일 메시지로 받으려면 **요청 보고서** 를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="d1405-126">Click **Request report** to receive a more detailed version of the report in an email message.</span></span> <span data-ttu-id="d1405-127">보고서를 받을 날짜 범위 및 받는 사람을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d1405-127">You can specify the date range and the recipients to receive the report.</span></span>

### <a name="details-table-view-for-the-smtp-auth-clients-report"></a><span data-ttu-id="d1405-128">SMTP 인증 클라이언트 보고서에 대 한 세부 정보 테이블 보기</span><span class="sxs-lookup"><span data-stu-id="d1405-128">Details table view for the SMTP Auth clients report</span></span>

<span data-ttu-id="d1405-129">**세부 정보 표 보기**를 클릭 하면 표시 되는 정보는 보고 있는 차트에 따라 달라 집니다.</span><span class="sxs-lookup"><span data-stu-id="d1405-129">If you click **View details table**, the information that's shown depends on the chart you were looking at:</span></span>

- <span data-ttu-id="d1405-130">**데이터 보기 기준: 보내는 볼륨**: 다음 정보가 테이블에 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d1405-130">**View data by: Sending volume**: The following information is shown in a table:</span></span>

  - <span data-ttu-id="d1405-131">**보낸 사람 주소**</span><span class="sxs-lookup"><span data-stu-id="d1405-131">**Sender address**</span></span>
  - <span data-ttu-id="d1405-132">**메시지 수**</span><span class="sxs-lookup"><span data-stu-id="d1405-132">**Message count**</span></span>

  <span data-ttu-id="d1405-133">행을 선택 하면 같은 세부 정보가 플라이 아웃에 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d1405-133">If you select a row, the same details are shown in a flyout.</span></span>

- <span data-ttu-id="d1405-134">**데이터 보기 기준: TLS 사용**: 테이블에 다음 정보가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d1405-134">**View data by: TLS Usage**: The following information is shown in a table:</span></span>

  - <span data-ttu-id="d1405-135">**보낸 사람 주소**</span><span class="sxs-lookup"><span data-stu-id="d1405-135">**Sender address**</span></span>
  - <span data-ttu-id="d1405-136">**TLS 1.0%**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="d1405-136">**TLS1.0%**<sup>\*</sup></span></span>
  - <span data-ttu-id="d1405-137">**TLS 1.1%**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="d1405-137">**TLS1.1%**<sup>\*</sup></span></span>
  - <span data-ttu-id="d1405-138">**TLS 1.2%**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="d1405-138">**TLS1.2%**<sup>\*</sup></span></span>
  - <span data-ttu-id="d1405-139">**메시지 수**</span><span class="sxs-lookup"><span data-stu-id="d1405-139">**Message count**</span></span>

  <span data-ttu-id="d1405-140"><sup>\*</sup> 이 열에는 보낸 사람의 메시지 비율과 수와 개수가 모두 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d1405-140"><sup>\*</sup> This column shows both the percentage and number of messages from the sender.</span></span>

<span data-ttu-id="d1405-141">세부 정보 표 보기에서 **필터** 를 클릭 하면 **시작 날짜** 및 **종료 날짜**와 함께 날짜 범위를 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d1405-141">If you click **Filters** in a details table view, you can specify a date range with **Start date** and **End date**.</span></span>

<span data-ttu-id="d1405-142">행을 선택 하는 경우 플라이 아웃에 다음과 유사한 세부 정보가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d1405-142">If you select a row, similar details are shown in a flyout:</span></span>

![SMTP 인증 클라이언트 보고서의 TLS 사용 보기 세부 정보 테이블에서 정보 플라이 아웃](../../media/mfi-smtp-auth-clients-report-tls-usage-view-view-details-table-details.png)

<span data-ttu-id="d1405-144">자세한 보고서 버전을 전자 메일 메시지로 받으려면 **요청 보고서** 를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="d1405-144">Click **Request report** to receive a more detailed version of the report in an email message.</span></span> <span data-ttu-id="d1405-145">보고서를 받을 날짜 범위 및 받는 사람을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d1405-145">You can specify the date range and the recipients to receive the report.</span></span>

<span data-ttu-id="d1405-146">보고서 보기로 돌아가려면 **보고서 보기**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="d1405-146">To go back to the reports view, click **View report**.</span></span>

## <a name="related-topics"></a><span data-ttu-id="d1405-147">관련 항목</span><span class="sxs-lookup"><span data-stu-id="d1405-147">Related topics</span></span>

<span data-ttu-id="d1405-148">메일 흐름 대시보드의 다른 정보에 대 한 자세한 내용은 [Security & 준수 센터의 메일 흐름 정보](mail-flow-insights-v2.md)를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="d1405-148">For information about other insights in the Mail flow dashboard, see [Mail flow insights in the Security & Compliance Center](mail-flow-insights-v2.md).</span></span>
