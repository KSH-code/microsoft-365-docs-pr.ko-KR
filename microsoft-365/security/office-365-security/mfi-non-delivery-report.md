---
title: 메일 흐름 대시보드의 배달되지 않은 보고서
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
description: 관리자는 보안 & 준수 센터의 메일 흐름 대시보드에서 배달되지 않는 세부 정보 보고서를 사용하여 조직의 보낸 사람으로부터 배달되지 않는 보고서(NDR 또는 반송 메시지라고도 알려)에서 가장 자주 발생하는 오류 코드를 모니터링하는 방법을 배울 수 있습니다.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 0e31e7dfcbd3c0cacaa6020464ed315f466a849b
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/18/2021
ms.locfileid: "50287892"
---
# <a name="non-delivery-report-in-the-security--compliance-center"></a><span data-ttu-id="16342-103">보안 및 준수 센터의 & 보고서</span><span class="sxs-lookup"><span data-stu-id="16342-103">Non-delivery report in the Security & Compliance Center</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="16342-104">**적용 대상**</span><span class="sxs-lookup"><span data-stu-id="16342-104">**Applies to**</span></span>
- [<span data-ttu-id="16342-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="16342-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="16342-106">Office 365용 Microsoft Defender 플랜 1 및 플랜 2</span><span class="sxs-lookup"><span data-stu-id="16342-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](office-365-atp.md)
- [<span data-ttu-id="16342-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="16342-107">Microsoft 365 Defender</span></span>](../mtp/microsoft-threat-protection.md)

<span data-ttu-id="16342-108">Security  [&](https://protection.office.com) 준수 센터의 메일 흐름 대시보드에서 배달되지 않는 보고서에는 조직의 사용자에 대해 배달되지 않는 보고서(NDR 또는 반송 메시지라고도 합니다)에서 가장 많이 발생하는 오류 코드가 표시됩니다. [](mail-flow-insights-v2.md)</span><span class="sxs-lookup"><span data-stu-id="16342-108">The **Non-delivery report** in the [Mail flow dashboard](mail-flow-insights-v2.md) in the [Security & Compliance Center](https://protection.office.com) shows the most-encountered error codes in non-delivery reports (also known as NDRs or bounce messages) for users in your organization.</span></span> <span data-ttu-id="16342-109">이 보고서에는 전자 메일 배달 문제를 해결할 수 있도록 NDRS의 세부 정보가 표시되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="16342-109">This report shows the details of NDRs so you can troubleshoot email delivery problems.</span></span>

![보안 및 준수 센터의 메일 흐름 대시보드에서 배달 & 위젯](../../media/mfi-non-delivery-report-widget.png)

## <a name="report-view-for-the-non-delivery-report"></a><span data-ttu-id="16342-111">배달되지 않은 보고서에 대한 보고서 보기</span><span class="sxs-lookup"><span data-stu-id="16342-111">Report view for the Non-delivery report</span></span>

<span data-ttu-id="16342-112">배달하지 않는 보고서 **위젯을** 클릭하면 배달 수 없는 **보고서로 전송됩니다.**</span><span class="sxs-lookup"><span data-stu-id="16342-112">Clicking on the **Non-delivery report** widget will take you to the **Non-delivery report**.</span></span>

<span data-ttu-id="16342-113">기본적으로 모든 오류 코드에 대한 활동이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="16342-113">By default, the activity for all error codes is shown.</span></span> <span data-ttu-id="16342-114">데이터 **표시를 클릭하면** 드롭다운에서 특정 오류 코드를 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="16342-114">If you click **Show data for**, you can select a specific error code from the dropdown.</span></span>

<span data-ttu-id="16342-115">차트에서 특정 일에 특정 색(오류 코드)을 마우스로 마우스로 대면 오류에 대한 총 메시지 수가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="16342-115">If you hover over a specific color (error code) on a specific day in the chart, you'll see the total number of messages for the error.</span></span>

![허용되지 않는 도메인 보고서의 보고서 보기](../../media/mfi-non-delivery-report-overview-view.png)

## <a name="details-table-view-for-the-non-delivery-report"></a><span data-ttu-id="16342-117">배달하지 않는 보고서에 대한 세부 정보 테이블 보기</span><span class="sxs-lookup"><span data-stu-id="16342-117">Details table view for the Non-delivery report</span></span>

<span data-ttu-id="16342-118">보고서 **보기에서** 세부 정보 표 보기를 클릭하면 다음 정보가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="16342-118">If you click **View details table** in a report view, the following information is shown:</span></span>

- <span data-ttu-id="16342-119">**날짜**</span><span class="sxs-lookup"><span data-stu-id="16342-119">**Date**</span></span>
- <span data-ttu-id="16342-120">**배달되지 않는 보고서 코드**</span><span class="sxs-lookup"><span data-stu-id="16342-120">**Non-delivery report code**</span></span>
- <span data-ttu-id="16342-121">**개수**</span><span class="sxs-lookup"><span data-stu-id="16342-121">**Count**</span></span>
- <span data-ttu-id="16342-122">**샘플 메시지:** 영향을 받는 메시지 샘플의 메시지 ID</span><span class="sxs-lookup"><span data-stu-id="16342-122">**Sample messages**: The message IDs of a sample of affected messages.</span></span>

<span data-ttu-id="16342-123">세부 정보 표 보기에서 **필터를** 클릭하면 시작 날짜와  종료 날짜가 있는 날짜 범위를 **지정할 수 있습니다.**</span><span class="sxs-lookup"><span data-stu-id="16342-123">If you click **Filters** in a details table view, you can specify a date range with **Start date** and **End date**.</span></span>

<span data-ttu-id="16342-124">특정 날짜 범위에 대한 보고서를 한명 이상의 받는 사람에게 전자 메일로 보내려면 다운로드 **요청을 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="16342-124">To email the report for a specific date range to one or more recipients, click **Request download**.</span></span>

<span data-ttu-id="16342-125">표에서 행을 선택하면 다음 정보가 있는 플라이아웃이 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="16342-125">When you select a row in the table, a flyout appears with the following information:</span></span>

- <span data-ttu-id="16342-126">**날짜**</span><span class="sxs-lookup"><span data-stu-id="16342-126">**Date**</span></span>
- <span data-ttu-id="16342-127">**배달 못지 않은 보고서 코드:** 링크를 클릭하여 특정 오류 코드의 원인 및 해결 방법을 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="16342-127">**Non-delivery report code**: You can click on the link to find for more information about the causes and solutions for the specific error code.</span></span>
- <span data-ttu-id="16342-128">**개수**</span><span class="sxs-lookup"><span data-stu-id="16342-128">**Count**</span></span>
- <span data-ttu-id="16342-129">**샘플 메시지:** 샘플  메시지 보기를 클릭하여 [](message-trace-scc.md) 영향을 받는 메시지의 샘플에 대한 메시지 추적 결과를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="16342-129">**Sample messages**: You can click **View sample messages** to see the [message trace](message-trace-scc.md) results for a sample of the affected messages.</span></span>

![배달하지 않는 보고서의 세부 정보 테이블 보기에서 행을 선택한 후 세부 정보 플라이아웃](../../media/mfi-non-delivery-report-details-flyout.png)

## <a name="related-topics"></a><span data-ttu-id="16342-131">관련 항목</span><span class="sxs-lookup"><span data-stu-id="16342-131">Related topics</span></span>

<span data-ttu-id="16342-132">메일 흐름 대시보드의 다른 인사이트에 대한 자세한 내용은 보안 및 준수 센터의 메일 [흐름 & 참조하세요.](mail-flow-insights-v2.md)</span><span class="sxs-lookup"><span data-stu-id="16342-132">For information about other insights in the Mail flow dashboard, see [Mail flow insights in the Security & Compliance Center](mail-flow-insights-v2.md).</span></span>
