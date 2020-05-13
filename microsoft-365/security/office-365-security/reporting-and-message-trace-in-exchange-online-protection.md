---
title: 보고 및 메시지 추적
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: f40253f2-50a1-426e-9979-be74ba74cb61
ms.custom:
- seo-marvel-apr2020
description: 이 문서에서는 Microsoft EOP (Exchange Online Protection) 관리자가 사용할 수 있는 보고서 및 문제 해결 도구에 대해 알아봅니다.
ms.openlocfilehash: af41f1d3b6ccc7632b392f58c36344239200f915
ms.sourcegitcommit: 93c0088d272cd45f1632a1dcaf04159f234abccd
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/12/2020
ms.locfileid: "44206445"
---
# <a name="reporting-and-message-trace-in-eop"></a><span data-ttu-id="5fe15-103">EOP의 보고 및 메시지 추적</span><span class="sxs-lookup"><span data-stu-id="5fe15-103">Reporting and message trace in EOP</span></span>

<span data-ttu-id="5fe15-104">Exchange online 사서함이 없는 exchange Online 또는 독립 실행형 EOP (Exchange Online Protection) 조직의 사서함이 있는 Microsoft 365 조직 EOP에서는 조직의 전반적인 상태를 확인 하는 데 도움이 되는 다양 한 보고서를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="5fe15-104">In Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, EOP offers many different reports that can help you determine the overall status and health of your organization.</span></span> <span data-ttu-id="5fe15-105">받는 사람에게 메시지가 도착하지 않는 등 특정 이벤트에 대한 문제를 해결할 수 있는 도구와 규정 준수 요구 사항을 지원하는 감사 보고서도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5fe15-105">There are also tools to help you troubleshoot specific events (such as a message not arriving to its intended recipients), and auditing reports to aid with compliance requirements.</span></span>

## <a name="usage-reports"></a><span data-ttu-id="5fe15-106">사용 현황 보고서</span><span class="sxs-lookup"><span data-stu-id="5fe15-106">Usage reports</span></span>

<span data-ttu-id="5fe15-107">**Microsoft 365 groups activity**: 만들어지고 사용 되는 microsoft 365 그룹 수에 대 한 정보를 봅니다.</span><span class="sxs-lookup"><span data-stu-id="5fe15-107">**Microsoft 365 groups activity**: View information about the number of Microsoft 365 groups that are created and used.</span></span>

<span data-ttu-id="5fe15-108">**전자 메일 활동**: 전체 조직에서 전송, 수신 및 읽은 메시지 수와 특정 사용자에 대 한 정보를 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="5fe15-108">**Email activity**: View information about the number of messages sent, received and read in your whole organization, and by specific users.</span></span>

<span data-ttu-id="5fe15-109">**전자 메일 앱 사용 현황**: 사용 되는 전자 메일 앱에 대 한 정보를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5fe15-109">**Email app usage**: View information about the email apps that are used.</span></span> <span data-ttu-id="5fe15-110">여기에는 각 앱에 대 한 총 연결 수와 연결 중인 Outlook의 버전이 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="5fe15-110">This include the total number of connections for each app, and the versions of Outlook that are connecting.</span></span>

<span data-ttu-id="5fe15-111">**사서함 사용량**: 사서함에 사용 되는 저장소, 할당량 소비, 항목 수 및 마지막 활동 (보내기 또는 읽기 작업)에 대 한 정보를 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="5fe15-111">**Mailbox usage**: View information about storage used, quota consumption, item count, and last activity (send or read activity) for mailboxes.</span></span>

<span data-ttu-id="5fe15-112">자세한 내용은 다음 리소스를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="5fe15-112">See the following resources for more information:</span></span>

- [<span data-ttu-id="5fe15-113">관리 센터의 microsoft 365 보고서-Microsoft 365 그룹</span><span class="sxs-lookup"><span data-stu-id="5fe15-113">Microsoft 365 Reports in the admin center - Microsoft 365 groups</span></span>](https://docs.microsoft.com/office365/admin/activity-reports/office-365-groups)

- [<span data-ttu-id="5fe15-114">관리 센터의 Microsoft 365 보고서-전자 메일 활동</span><span class="sxs-lookup"><span data-stu-id="5fe15-114">Microsoft 365 Reports in the admin center - Email activity</span></span>](https://docs.microsoft.com/office365/admin/activity-reports/email-activity)

- [<span data-ttu-id="5fe15-115">관리 센터의 Microsoft 365 보고서-전자 메일 앱 사용 현황</span><span class="sxs-lookup"><span data-stu-id="5fe15-115">Microsoft 365 Reports in the admin center - Email apps usage</span></span>](https://docs.microsoft.com/office365/admin/activity-reports/email-apps-usage)

- [<span data-ttu-id="5fe15-116">관리 센터의 Microsoft 365 보고서-사서함 사용량</span><span class="sxs-lookup"><span data-stu-id="5fe15-116">Microsoft 365 Reports in the admin center - Mailbox usage</span></span>](https://docs.microsoft.com/office365/admin/activity-reports/mailbox-usage)

## <a name="security--compliance-reports-in-the-microsoft-365-admin-center"></a><span data-ttu-id="5fe15-117">Microsoft 365 관리 센터의 보안 & 준수 보고서</span><span class="sxs-lookup"><span data-stu-id="5fe15-117">Security & compliance reports in the Microsoft 365 admin center</span></span>

<span data-ttu-id="5fe15-118">이러한 향상 된 보고서는 요약 정보와 자세한 정보를 드릴 다운 하는 기능을 포함 하는 EOP 관리자에 게 대화형 보고 환경을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="5fe15-118">These enhanced reports provide an interactive reporting experience for EOP admins, which includes summary information, and the ability to drill down for more details.</span></span>

<span data-ttu-id="5fe15-119">**Atp (Advanced Threat Protection)**: atp에 속하는 안전한 링크 및 안전한 첨부 파일에 대 한 정보를 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="5fe15-119">**Advanced Threat Protection (ATP)**: View information about safe links and safe attachments that are part of ATP.</span></span>

<span data-ttu-id="5fe15-120">**EOP**: 조직에서 보내고 보낸 맬웨어 감지, 스푸핑된 메일, 스팸 감지 및 메일 흐름에 대 한 정보를 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="5fe15-120">**EOP**: View information about malware detections, spoofed mail, spam detections, and mail flow to and from your organization.</span></span>

[<span data-ttu-id="5fe15-121">Office 365 Advanced Threat Protection에 대 한 보고서 보기</span><span class="sxs-lookup"><span data-stu-id="5fe15-121">View reports for Office 365 Advanced Threat Protection</span></span>](view-reports-for-atp.md)

## <a name="custom-reports-using-microsoft-graph"></a><span data-ttu-id="5fe15-122">Microsoft Graph를 사용한 사용자 지정 보고서</span><span class="sxs-lookup"><span data-stu-id="5fe15-122">Custom reports using Microsoft Graph</span></span>

<span data-ttu-id="5fe15-123">Microsoft Graph를 사용 하 여 관리 센터에서 사용할 수 있는 보고서를 프로그래밍 방식으로 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="5fe15-123">Programmatically create reports that are available in the admin center by using Microsoft Graph.</span></span> <span data-ttu-id="5fe15-124">자세한 내용은 microsoft graph [개요](https://docs.microsoft.com/graph/overview) 및 [Office 365 사용 현황 보고서](https://docs.microsoft.com/graph/api/resources/report)사용 (영문)을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="5fe15-124">For more information, see [Overview of Microsoft Graph](https://docs.microsoft.com/graph/overview) and [Working with Office 365 usage reports in Microsoft Graph](https://docs.microsoft.com/graph/api/resources/report).</span></span>

## <a name="message-trace"></a><span data-ttu-id="5fe15-125">Message trace</span><span class="sxs-lookup"><span data-stu-id="5fe15-125">Message trace</span></span>

<span data-ttu-id="5fe15-126">EOP를 통과하는 전자 메일 메시지를 추적합니다.</span><span class="sxs-lookup"><span data-stu-id="5fe15-126">Follows email messages as they travel through EOP.</span></span> <span data-ttu-id="5fe15-127">이를 통해 서비스에서 전자 메일 메시지를 수신, 거부, 지연 또는 배달했는지 여부를 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5fe15-127">You can determine if an email message was received, rejected, deferred, or delivered by the service.</span></span> <span data-ttu-id="5fe15-128">또한 최종 상태에 도달 하기 전에 메시지에 대해 수행 된 작업을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="5fe15-128">It also shows what actions were taken on the message before it reached its final status.</span></span>

<span data-ttu-id="5fe15-129">이 정보를 사용 하 여 사용자의 질문에 효과적으로 응답 하 고, 메일 흐름 문제를 해결 하며, 정책 변경을 확인 하 고, 기술 지원 서비스에 문의 하 여 도움을 받을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5fe15-129">You can use this information to efficiently answer your user's questions, troubleshoot mail flow issues, validate policy changes, and alleviates the need to contact technical support for assistance.</span></span>

<span data-ttu-id="5fe15-130">[보안 & 준수 센터의 메시지 추적](message-trace-scc.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="5fe15-130">See [Message trace in the Security & Compliance Center](message-trace-scc.md).</span></span>

## <a name="audit-logging"></a><span data-ttu-id="5fe15-131">감사 로깅</span><span class="sxs-lookup"><span data-stu-id="5fe15-131">Audit logging</span></span>

<span data-ttu-id="5fe15-132">조직 관리자가 변경한 특정 내용을 추적합니다.</span><span class="sxs-lookup"><span data-stu-id="5fe15-132">Tracks specific changes made by admins to your organization.</span></span> <span data-ttu-id="5fe15-133">이러한 보고서를 사용하면 구성 문제를 해결하거나 보안 또는 규정 준수 관련 문제의 원인을 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5fe15-133">These reports can help you troubleshoot configuration issues or find the cause of security or compliance-related problems.</span></span> <span data-ttu-id="5fe15-134">[EOP의 감사 보고서를](auditing-reports-in-eop.md)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="5fe15-134">See [Auditing reports in EOP](auditing-reports-in-eop.md).</span></span>

## <a name="reporting-and-message-trace-data-availability-and-latency"></a><span data-ttu-id="5fe15-135">보고 및 메시지 추적 데이터 사용 가능 여부 및 대기 시간</span><span class="sxs-lookup"><span data-stu-id="5fe15-135">Reporting and message trace data availability and latency</span></span>

<span data-ttu-id="5fe15-136">다음 표에는 EOP 보고 및 메시지 추적 데이터를 사용할 수 있는 시기와 기간에 대한 설명이 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5fe15-136">The following table describes when EOP reporting and message trace data is available and for how long.</span></span>

||||
|:-----|:-----|:-----|
|<span data-ttu-id="5fe15-137">**보고서 유형**</span><span class="sxs-lookup"><span data-stu-id="5fe15-137">**Report type**</span></span>|<span data-ttu-id="5fe15-138">**데이터 사용 가능 기간(확인 기간)**</span><span class="sxs-lookup"><span data-stu-id="5fe15-138">**Data available for (look back period)**</span></span>|<span data-ttu-id="5fe15-139">**대기 시간**</span><span class="sxs-lookup"><span data-stu-id="5fe15-139">**Latency**</span></span>|
|<span data-ttu-id="5fe15-140">메일 보호 요약 보고서</span><span class="sxs-lookup"><span data-stu-id="5fe15-140">Mail protection summary reports</span></span>|<span data-ttu-id="5fe15-141">90일</span><span class="sxs-lookup"><span data-stu-id="5fe15-141">90 days</span></span>|<span data-ttu-id="5fe15-p106">메시지 데이터 집계는 대부분 24~48시간 이내에 완료됩니다. 일부 사소한 증분 집계 변경의 경우 5일까지 소요될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5fe15-p106">Message data aggregation is mostly complete within 24-48 hours. Some minor incremental aggregated changes may occur for up to 5 days.</span></span>|
|<span data-ttu-id="5fe15-144">메일 보호 세부 정보 보고서</span><span class="sxs-lookup"><span data-stu-id="5fe15-144">Mail protection detail reports</span></span>|<span data-ttu-id="5fe15-145">90일</span><span class="sxs-lookup"><span data-stu-id="5fe15-145">90 days</span></span>|<span data-ttu-id="5fe15-p107">7일 미만의 세부 데이터는 24시간 이내에 표시되지만 48시간이 될 때까지 완료되지 않을 수 있습니다. 일부 사소한 증분 변경의 경우 5일까지 소요될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5fe15-p107">For detail data that's less than 7 days old, data should appear within 24 hours but may not be complete until 48 hours. Some minor incremental changes may occur for up to 5 days.</span></span> <br/><br/> <span data-ttu-id="5fe15-148">7일이 지난 메시지에 대한 상세 보고서를 보려면 결과가 표시되는 데 최대 몇 시간이 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5fe15-148">To view detail reports for messages that are greater than 7 days old, results may take up to a few hours.</span></span>|
|<span data-ttu-id="5fe15-149">메시지 추적 데이터</span><span class="sxs-lookup"><span data-stu-id="5fe15-149">Message trace data</span></span>|<span data-ttu-id="5fe15-150">90일</span><span class="sxs-lookup"><span data-stu-id="5fe15-150">90 days</span></span>|<span data-ttu-id="5fe15-151">7일 미만의 메시지에 대해 메시지 추적을 실행하면 메시지가 5~30분 이내에 표시되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5fe15-151">When you run a message trace for messages that are less than 7 days old, the messages should appear within 5-30 minutes.</span></span><br/><br/> <span data-ttu-id="5fe15-152">7일이 지난 메시지에 대해 메시지 추적을 실행하면 결과가 표시되는 데 최대 몇 시간이 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5fe15-152">When you run a message trace for messages that are greater than 7 days old, results may take up to a few hours.</span></span>|
|

> [!NOTE]
> <span data-ttu-id="5fe15-153">데이터 사용 가능 여부 및 대기 시간은 관리 센터 또는 원격 PowerShell을 통해 요청 된 경우와 동일 합니다.</span><span class="sxs-lookup"><span data-stu-id="5fe15-153">Data availability and latency is the same whether requested via the admin center or remote PowerShell.</span></span>
