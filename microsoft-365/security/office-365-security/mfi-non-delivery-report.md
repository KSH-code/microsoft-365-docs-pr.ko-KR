---
title: 메일 흐름 대시보드의 배달 못 한 보고서
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
description: 관리자는 보안 & 준수 센터의 메일 흐름 대시보드에서 배달 못 함 세부 정보 보고서를 사용하여 조직의 보낸 사람이 전송하는 배달 못 함 보고서(NDR 또는 반송 메시지라고도 함)에서 가장 자주 발생하는 오류 코드를 모니터링하는 방법에 대해 학습할 수 있습니다.
ms.openlocfilehash: bdc2a2a16f76f4e6ada629c82b86423422ab56c9
ms.sourcegitcommit: e12fa502bc216f6083ef5666f693a04bb727d4df
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/20/2020
ms.locfileid: "46826920"
---
# <a name="non-delivery-report-in-the-security--compliance-center"></a><span data-ttu-id="8ee86-103">보안 및 준수 센터의 & 배달 못 계정 보고서</span><span class="sxs-lookup"><span data-stu-id="8ee86-103">Non-delivery report in the Security & Compliance Center</span></span>

<span data-ttu-id="8ee86-104">보안 & **준수 센터의 메일** 흐름 [대시보드에](mail-flow-insights-v2.md) 있는 배달 못 함 보고서는 조직의 사용자에 대한 배달 못 함 보고서(NDR 또는 반송 메시지라고도 함)에서 가장 많이 사용한 오류 코드를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="8ee86-104">The **Non-delivery report** in the [Mail flow dashboard](mail-flow-insights-v2.md) in the Security & Compliance Center shows the most-encountered error codes in non-delivery reports (also known as NDRs or bounce messages) for users in your organization.</span></span> <span data-ttu-id="8ee86-105">이 보고서에는 NDR의 세부 정보가 표시되므로 전자 메일 배달 문제를 해결할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8ee86-105">This report shows the details of NDRs so you can troubleshoot email delivery problems.</span></span>

![보안 메시지 웹 서비스의 보안 흐름 대시보드에 있는 배달 못 & 위과](../../media/mfi-non-delivery-report-widget.png)

## <a name="report-view-for-the-non-delivery-report"></a><span data-ttu-id="8ee86-107">배달 못 한 보고서 보기</span><span class="sxs-lookup"><span data-stu-id="8ee86-107">Report view for the Non-delivery report</span></span>

<span data-ttu-id="8ee86-108">배달 못 됨 **보고서 위산을** 클릭하면 배달 못 됨 **보고서로 가게 됩니다.**</span><span class="sxs-lookup"><span data-stu-id="8ee86-108">Clicking on the **Non-delivery report** widget will take you to the **Non-delivery report**.</span></span>

<span data-ttu-id="8ee86-109">기본적으로 모든 오류 코드에 대한 활동이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="8ee86-109">By default, the activity for all error codes is shown.</span></span> <span data-ttu-id="8ee86-110">데이터 **표시를 클릭한 경우**드롭다운에서 특정 오류 코드를 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8ee86-110">If you click **Show data for**, you can select a specific error code from the dropdown.</span></span>

<span data-ttu-id="8ee86-111">차트의 특정 날짜에서 특정 색(오류 코드)을 가리치면 오류의 총 메시지 수가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="8ee86-111">If you hover over a specific color (error code) on a specific day in the chart, you'll see the total number of messages for the error.</span></span>

![비허용 도메인 보고서의 보고서 보기](../../media/mfi-non-delivery-report-overview-view.png)

## <a name="details-table-view-for-the-non-delivery-report"></a><span data-ttu-id="8ee86-113">배달 못 한 보고서에 대한 세부 정보 표 보기</span><span class="sxs-lookup"><span data-stu-id="8ee86-113">Details table view for the Non-delivery report</span></span>

<span data-ttu-id="8ee86-114">보고서 보기에서 **세부 정보 표를** 클릭하면 다음 정보가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="8ee86-114">If you click **View details table** in a report view, the following information is shown:</span></span>

- <span data-ttu-id="8ee86-115">**날짜**</span><span class="sxs-lookup"><span data-stu-id="8ee86-115">**Date**</span></span>
- <span data-ttu-id="8ee86-116">**배달 못 한 보고서 코드**</span><span class="sxs-lookup"><span data-stu-id="8ee86-116">**Non-delivery report code**</span></span>
- <span data-ttu-id="8ee86-117">**개수**</span><span class="sxs-lookup"><span data-stu-id="8ee86-117">**Count**</span></span>
- <span data-ttu-id="8ee86-118">**샘플 메시지:** 영향을 받는 메시지 샘플의 메시지 ID</span><span class="sxs-lookup"><span data-stu-id="8ee86-118">**Sample messages**: The message IDs of a sample of affected messages.</span></span>

<span data-ttu-id="8ee86-119">세부 정보 **보기에서 필터를** 클릭한 경우 시작 날짜와 종료 날짜로 날짜 **범위를** 지정할 **수 있습니다.**</span><span class="sxs-lookup"><span data-stu-id="8ee86-119">If you click **Filters** in a details table view, you can specify a date range with **Start date** and **End date**.</span></span>

<span data-ttu-id="8ee86-120">특정 날짜 범위에 대한 보고서에 대한 정보를 한 명 이상의 받는 사람에게 전자 메일로 보내려면 요청 을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="8ee86-120">To email the report for a specific date range to one or more recipients, click **Request download**.</span></span>

<span data-ttu-id="8ee86-121">표에서 행을 선택하면 다음 정보와 함께 플라이아웃이 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="8ee86-121">When you select a row in the table, a flyout appears with the following information:</span></span>

- <span data-ttu-id="8ee86-122">**날짜**</span><span class="sxs-lookup"><span data-stu-id="8ee86-122">**Date**</span></span>
- <span data-ttu-id="8ee86-123">**배달 못 됨 보고서 코드 :** 링크를 클릭하면 특정 오류 코드의 원인 및 해결 방법에 대한 자세한 내용을 찾아알 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8ee86-123">**Non-delivery report code**: You can click on the link to find for more information about the causes and solutions for the specific error code.</span></span>
- <span data-ttu-id="8ee86-124">**개수**</span><span class="sxs-lookup"><span data-stu-id="8ee86-124">**Count**</span></span>
- <span data-ttu-id="8ee86-125">**샘플 메시지**: 샘플 메시지를 **표시하면 영향을** 받는 [메시지 샘플의](message-trace-scc.md) 메시지 추적 결과를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8ee86-125">**Sample messages**: You can click **View sample messages** to see the [message trace](message-trace-scc.md) results for a sample of the affected messages.</span></span>

![배달 못 한 보고서의 세부 정보 테이블 보기에서 행을 선택한 후 세부 정보 플라이아웃](../../media/mfi-non-delivery-report-details-flyout.png)

## <a name="related-topics"></a><span data-ttu-id="8ee86-127">관련 항목</span><span class="sxs-lookup"><span data-stu-id="8ee86-127">Related topics</span></span>

<span data-ttu-id="8ee86-128">메일 흐름 대시보드의 기타 정보에 대한 내용은 규정 준수 센터의 [보안 흐름 정보를 & 참조하세요.](mail-flow-insights-v2.md)</span><span class="sxs-lookup"><span data-stu-id="8ee86-128">For information about other insights in the Mail flow dashboard, see [Mail flow insights in the Security & Compliance Center](mail-flow-insights-v2.md).</span></span>
