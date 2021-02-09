---
title: 메일 흐름 대시보드의 SMTPAuth 클라이언트 인사이트 및 보고서
f1.keywords:
- NOCSH
ms.author: siosulli
author: siosulli
manager: dansimp
audience: ITPro
ms.topic: conceptual
localization_priority: Normal
ms.assetid: ''
ms.custom:
- seo-marvel-apr2020
description: 관리자는 보안 & 준수 센터의 메일 흐름 대시보드에서 SMTP 인증 정보를 사용하여 전자 메일 메시지를 보내는 조직 내 전자 메일 보낸 사람(SMTP AUTH)을 모니터링하는 방법을 배울 수 있습니다.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 3476ee2f9388245fb105a0910fa7b7d11ec3aeee
ms.sourcegitcommit: e920e68c8d0eac8b152039b52cfc139d478a67b3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/09/2021
ms.locfileid: "50150246"
---
# <a name="smtp-auth-clients-insight-and-report-in-the-security--compliance-center"></a><span data-ttu-id="3b4ee-103">보안 및 준수 센터의 SMTP & 인사이트 및 보고</span><span class="sxs-lookup"><span data-stu-id="3b4ee-103">SMTP Auth clients insight and report in the Security & Compliance Center</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="3b4ee-104">**적용 대상**</span><span class="sxs-lookup"><span data-stu-id="3b4ee-104">**Applies to**</span></span>
- [<span data-ttu-id="3b4ee-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="3b4ee-105">Exchange Online Protection</span></span>](https://go.microsoft.com/fwlink/?linkid=2148611)
- [<span data-ttu-id="3b4ee-106">Microsoft Defender for Office 365 요금제 1 및 계획 2</span><span class="sxs-lookup"><span data-stu-id="3b4ee-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](https://go.microsoft.com/fwlink/?linkid=2148715)
- [<span data-ttu-id="3b4ee-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="3b4ee-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

<span data-ttu-id="3b4ee-108">메일 흐름 대시보드의 **SMTP** [](mail-flow-insights-v2.md) 인증 클라이언트 정보 및 보안 & 준수 센터의 [](https://protection.office.com) 관련 [SMTP](#smtp-auth-clients-report) 인증 클라이언트 보고서에서는 조직의 사용자 또는 시스템 계정이 SMTP AUTH 클라이언트 전송 프로토콜의 사용을 강조합니다.</span><span class="sxs-lookup"><span data-stu-id="3b4ee-108">The **SMTP Auth clients** insight in the [Mail flow dashboard](mail-flow-insights-v2.md) and the associated [SMTP Auth clients report](#smtp-auth-clients-report) in the [Security & Compliance Center](https://protection.office.com) highlight the use of the SMTP AUTH client submission protocol by users or system accounts in your organization.</span></span> <span data-ttu-id="3b4ee-109">이 레거시 프로토콜(끝점 smtp.office365.com 사용)은 기본 인증만 제공하며 손상된 계정에서 전자 메일을 보내기 위해 사용될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3b4ee-109">This legacy protocol (which uses the endpoint smtp.office365.com) only offers Basic authentication, and is susceptible to being used by compromised accounts to send email.</span></span> <span data-ttu-id="3b4ee-110">인사이트 및 보고서를 통해 SMTP AUTH 전자 메일 전송에 대한 비정상적인 활동을 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3b4ee-110">The insight and report allow you to check for unusual activity for SMTP AUTH email submissions.</span></span> <span data-ttu-id="3b4ee-111">또한 SMTP AUTH를 사용하는 클라이언트 또는 장치의 TLS 사용 현황 데이터도 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="3b4ee-111">It also shows the TLS usage data for clients or devices using SMTP AUTH.</span></span>

<span data-ttu-id="3b4ee-112">위젯은 지난 7일 동안 SMTP 인증 프로토콜을 사용한 사용자 또는 서비스 계정의 수를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="3b4ee-112">The widget indicates the number of users or service accounts that have used the SMTP Auth protocol in the last 7 days.</span></span>

![보안 및 준수 센터의 메일 흐름 대시보드에서 SMTP & 위젯](../../media/mfi-smtp-auth-clients-report-widget.png)

<span data-ttu-id="3b4ee-114">위젯에서 메시지 수를 클릭하면 **SMTPAuth** 클라이언트 플라이아웃이 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="3b4ee-114">If you click the number of messages on the widget, an **SMTP Auth clients** flyout appears.</span></span> <span data-ttu-id="3b4ee-115">플라이아웃은 지난 주에 대한 TLS 사용량 및 볼륨의 집계된 보기를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="3b4ee-115">The flyout provides an aggregated view of the TLS usage and volumes for the last week.</span></span>

![메일 흐름 대시보드에서 SMTPAuth 클라이언트 위젯을 클릭한 후 세부 정보 플라이아웃](../../media/mfi-smtp-auth-clients-report-details.png)

<span data-ttu-id="3b4ee-117">다음 섹션에 설명된 SMTPAuth 클라이언트 보고서로 이동하려면 **SMTP Auth** 클라이언트 보고서 링크를 클릭할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3b4ee-117">You can click the **SMTP Auth clients report** link to go to the SMTP Auth clients report as described in the next section.</span></span>

## <a name="smtp-auth-clients-report"></a><span data-ttu-id="3b4ee-118">SMTP 인증 클라이언트 보고서</span><span class="sxs-lookup"><span data-stu-id="3b4ee-118">SMTP Auth clients report</span></span>

### <a name="report-view-for-the-smtp-auth-clients-report"></a><span data-ttu-id="3b4ee-119">SMTPAuth 클라이언트 보고서에 대한 보고서 보기</span><span class="sxs-lookup"><span data-stu-id="3b4ee-119">Report view for the SMTP Auth clients report</span></span>

<span data-ttu-id="3b4ee-120">기본적으로 보고서에는 지난 7일간의 데이터가 표시되지만 지난 90일 동안의 데이터를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3b4ee-120">By default, the report shows data for the last 7 days, but data is available for the last 90 days.</span></span>

<span data-ttu-id="3b4ee-121">개요 섹션에는 다음 차트가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3b4ee-121">The overview section contains the following charts:</span></span>

- <span data-ttu-id="3b4ee-122">**볼륨 보내기:** 기본적으로 차트에는 모든 도메인에서 전송된 SMTPAuth 클라이언트 메시지 수가 표시됩니다( 데이터 **표시:** 모든 보낸 사람 도메인은 기본적으로 선택되어 있습니다).</span><span class="sxs-lookup"><span data-stu-id="3b4ee-122">**View data by: Sending volume**: By default, the chart shows the number of SMTP Auth client messages that were sent from all domains (**Show data for: All sender domains** is selected by default).</span></span> <span data-ttu-id="3b4ee-123">데이터 표시를 클릭하고 드롭다운 목록에서  보낸 사람 도메인을 선택하여 결과를 특정 보낸 사람 도메인으로 필터링할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3b4ee-123">You can filter the results to a specific sender domain by clicking **Show data for** and selecting the sender domain from the dropdown list.</span></span> <span data-ttu-id="3b4ee-124">특정 데이터 포인트(일)를 마우스로 마우스로 대면 메시지 수가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="3b4ee-124">If you hover a specific data point (day), the number of messages is shown.</span></span>

  ![보안 및 준수 센터의 SMTP & 볼륨 보기 보내기](../../media/mfi-smtp-auth-clients-report-sending-volume-view.png)

- <span data-ttu-id="3b4ee-126">**데이터 보기: TLS** 사용법: 차트는 선택한 기간 동안 모든 SMTPAuth 클라이언트 메시지에 대한 TLS 사용 백분율을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="3b4ee-126">**View data by: TLS Usage**: The chart shows the percentage of TLS usage for all SMTP Auth client messages during the selected time period.</span></span> <span data-ttu-id="3b4ee-127">이 차트를 사용하면 여전히 이전 버전의 TLS를 사용하는 사용자 및 시스템 계정을 식별하고 조치를 취할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3b4ee-127">This chart allows you to identify and take action on users and system accounts that are still using older versions of TLS.</span></span>

  ![보안 및 준수 센터의 SMTP & 클라이언트의 TLS 사용 현황 보기](../../media/mfi-smtp-auth-clients-report-tls-usage-view.png)

<span data-ttu-id="3b4ee-129">보고서 보기에서 **필터를** 클릭하면 시작 날짜와 종료  날짜가 있는 날짜 범위를 **지정할 수 있습니다.**</span><span class="sxs-lookup"><span data-stu-id="3b4ee-129">If you click **Filters** in a report view, you can specify a date range with **Start date** and **End date**.</span></span>

<span data-ttu-id="3b4ee-130">보고서 **요청 보고서를** 클릭하여 전자 메일 메시지에 보다 자세한 버전의 보고서를 받습니다.</span><span class="sxs-lookup"><span data-stu-id="3b4ee-130">Click **Request report** to receive a more detailed version of the report in an email message.</span></span> <span data-ttu-id="3b4ee-131">보고서를 받을 날짜 범위와 받는 사람을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3b4ee-131">You can specify the date range and the recipients to receive the report.</span></span>

### <a name="details-table-view-for-the-smtp-auth-clients-report"></a><span data-ttu-id="3b4ee-132">SMTPAuth 클라이언트 보고서에 대한 세부 정보 테이블 보기</span><span class="sxs-lookup"><span data-stu-id="3b4ee-132">Details table view for the SMTP Auth clients report</span></span>

<span data-ttu-id="3b4ee-133">세부 **정보** 표 보기를 클릭하면 표시되는 정보는 보고 있는 차트에 따라 다를 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3b4ee-133">If you click **View details table**, the information that's shown depends on the chart you were looking at:</span></span>

- <span data-ttu-id="3b4ee-134">**데이터 보기: 볼륨 보내기:** 다음 정보가 표에 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3b4ee-134">**View data by: Sending volume**: The following information is shown in a table:</span></span>

  - <span data-ttu-id="3b4ee-135">**보낸 사람 주소**</span><span class="sxs-lookup"><span data-stu-id="3b4ee-135">**Sender address**</span></span>
  - <span data-ttu-id="3b4ee-136">**메시지 수**</span><span class="sxs-lookup"><span data-stu-id="3b4ee-136">**Message count**</span></span>

  <span data-ttu-id="3b4ee-137">행을 선택하면 플라이아웃에 동일한 세부 정보가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="3b4ee-137">If you select a row, the same details are shown in a flyout.</span></span>

- <span data-ttu-id="3b4ee-138">**데이터 보기: TLS 사용법:** 다음 정보가 표에 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3b4ee-138">**View data by: TLS Usage**: The following information is shown in a table:</span></span>

  - <span data-ttu-id="3b4ee-139">**보낸 사람 주소**</span><span class="sxs-lookup"><span data-stu-id="3b4ee-139">**Sender address**</span></span>
  - <span data-ttu-id="3b4ee-140">**TLS1.0%**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="3b4ee-140">**TLS1.0%**<sup>\*</sup></span></span>
  - <span data-ttu-id="3b4ee-141">**TLS1.1%**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="3b4ee-141">**TLS1.1%**<sup>\*</sup></span></span>
  - <span data-ttu-id="3b4ee-142">**TLS1.2%**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="3b4ee-142">**TLS1.2%**<sup>\*</sup></span></span>
  - <span data-ttu-id="3b4ee-143">**메시지 수**</span><span class="sxs-lookup"><span data-stu-id="3b4ee-143">**Message count**</span></span>

  <span data-ttu-id="3b4ee-144"><sup>\*</sup> 이 열에는 보낸 사람이 보낸 메시지의 백분율과 수가 모두 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="3b4ee-144"><sup>\*</sup> This column shows both the percentage and number of messages from the sender.</span></span>

<span data-ttu-id="3b4ee-145">세부 정보 표 보기에서 **필터를** 클릭하면 시작 날짜와  종료 날짜가 있는 날짜 범위를 **지정할 수 있습니다.**</span><span class="sxs-lookup"><span data-stu-id="3b4ee-145">If you click **Filters** in a details table view, you can specify a date range with **Start date** and **End date**.</span></span>

<span data-ttu-id="3b4ee-146">행을 선택하면 플라이아웃에 유사한 세부 정보가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="3b4ee-146">If you select a row, similar details are shown in a flyout:</span></span>

![SMTPAuth 클라이언트 보고서의 TLS 사용 현황 보기 세부 정보 테이블에서 세부 정보 플라이아웃](../../media/mfi-smtp-auth-clients-report-tls-usage-view-view-details-table-details.png)

<span data-ttu-id="3b4ee-148">보고서 **요청 보고서를** 클릭하여 전자 메일 메시지에 보다 자세한 버전의 보고서를 받습니다.</span><span class="sxs-lookup"><span data-stu-id="3b4ee-148">Click **Request report** to receive a more detailed version of the report in an email message.</span></span> <span data-ttu-id="3b4ee-149">보고서를 받을 날짜 범위와 받는 사람을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3b4ee-149">You can specify the date range and the recipients to receive the report.</span></span>

<span data-ttu-id="3b4ee-150">보고서 보기로 돌아가려면 보고서 **보기를 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="3b4ee-150">To go back to the reports view, click **View report**.</span></span>

## <a name="related-topics"></a><span data-ttu-id="3b4ee-151">관련 주제</span><span class="sxs-lookup"><span data-stu-id="3b4ee-151">Related topics</span></span>

<span data-ttu-id="3b4ee-152">메일 흐름 대시보드의 다른 인사이트에 대한 자세한 내용은 보안 및 준수 센터의 메일 [흐름 & 참조하세요.](mail-flow-insights-v2.md)</span><span class="sxs-lookup"><span data-stu-id="3b4ee-152">For information about other insights in the Mail flow dashboard, see [Mail flow insights in the Security & Compliance Center](mail-flow-insights-v2.md).</span></span>
