---
title: 메일 흐름 대시보드의 큐 정보
f1.keywords:
- NOCSH
ms.author: siosulli
author: siosulli
manager: dansimp
audience: ITPro
ms.topic: conceptual
localization_priority: Normal
ms.assetid: 37640c80-ce6f-47e2-afd1-bc1d3c50e637
description: 관리자는 보안 및 준수 센터의 메일 흐름 대시보드에서 큐 위젯을 사용하여 아웃바운드 커넥터를 통해 해당 & 또는 파트너 조직으로의 실패한 메일 흐름을 모니터링하는 방법을 배울 수 있습니다.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 14cadd0e8611fbbc65c3bdc9849beebf3a3eb34d
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51071228"
---
# <a name="queues-insight-in-the-security--compliance-center"></a><span data-ttu-id="4f400-103">보안 및 준수 센터의 & 큐</span><span class="sxs-lookup"><span data-stu-id="4f400-103">Queues insight in the Security & Compliance Center</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="4f400-104">**적용 대상**</span><span class="sxs-lookup"><span data-stu-id="4f400-104">**Applies to**</span></span>
- [<span data-ttu-id="4f400-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="4f400-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="4f400-106">Office 365용 Microsoft Defender 플랜 1 및 플랜 2</span><span class="sxs-lookup"><span data-stu-id="4f400-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="4f400-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="4f400-107">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

<span data-ttu-id="4f400-108">커넥터를 사용하여 조직에서 사용자 조직 또는 파트너 전자 메일 서버로 메시지를 보낼 수 없는 경우 메시지는 Microsoft 365에서 대기됩니다.</span><span class="sxs-lookup"><span data-stu-id="4f400-108">When messages can't be sent from your organization to your on-premises or partner email servers using connectors, the messages are queued in Microsoft 365.</span></span> <span data-ttu-id="4f400-109">이 조건을 발생하게 하는 일반적인 예는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="4f400-109">Common examples that cause this condition are:</span></span>

- <span data-ttu-id="4f400-110">커넥터가 잘못 구성되었습니다.</span><span class="sxs-lookup"><span data-stu-id="4f400-110">The connector is incorrectly configured.</span></span>
- <span data-ttu-id="4f400-111">사내 환경에서 네트워킹 또는 방화벽이 변경되었습니다.</span><span class="sxs-lookup"><span data-stu-id="4f400-111">There have been networking or firewall changes in your on-premises environment.</span></span>

<span data-ttu-id="4f400-112">Microsoft 365는 24시간 동안 계속 배달을 다시 시도합니다.</span><span class="sxs-lookup"><span data-stu-id="4f400-112">Microsoft 365 will continue to retry to delivery for 24 hours.</span></span> <span data-ttu-id="4f400-113">24시간이 지난 후 메시지는 만료되고 배달되지 않는 보고서(NDRs 또는 반송 메시지라고도 알려지음)의 보낸 사람에 반환됩니다.</span><span class="sxs-lookup"><span data-stu-id="4f400-113">After 24 hours, the messages will expire and will be returned to the senders in non-delivery reports (also known as a NDRs or bounce messages).</span></span>

<span data-ttu-id="4f400-114">대기 중인 전자 메일 볼륨이 미리 정의된 임계값(기본값은 200개 메시지)을 초과하면 다음 위치에서 정보를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4f400-114">If the queued email volume exceeds the pre-defined threshold (the default value is 200 messages), the information is available in the following locations:</span></span>

- <span data-ttu-id="4f400-115">보안 **및** 준수 [](mail-flow-insights-v2.md) 센터의 메일 흐름 대시보드에서 & [정보를 제공합니다.](https://protection.office.com)</span><span class="sxs-lookup"><span data-stu-id="4f400-115">The **Queues** insight in the [Mail flow dashboard](mail-flow-insights-v2.md) in the [Security & Compliance Center](https://protection.office.com).</span></span> <span data-ttu-id="4f400-116">자세한 내용은 이 [](#queues-insight-in-the-mail-flow-dashboard) 문서의 메일 흐름 대시보드 섹션에서 큐 정보를 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="4f400-116">For more information, see the [Queues insight in the Mail flow dashboard](#queues-insight-in-the-mail-flow-dashboard) section in this article.</span></span>

- <span data-ttu-id="4f400-117">경고는 보안  및 준수 센터(경고 대시보드 [또는 )의 최근 경고 &](https://protection.office.com)  \> **표시됩니다.** <https://protection.office.com/alertsdashboard></span><span class="sxs-lookup"><span data-stu-id="4f400-117">An alert is displayed in **Recent alerts** the Alerts dashboard in the [Security & Compliance Center](https://protection.office.com) (**Alerts** \> **Dashboard** or <https://protection.office.com/alertsdashboard>).</span></span>

  ![보안 및 준수 센터의 경고 대시보드에서 & 최근 알림](../../media/mfi-queued-messages-alert.png)

- <span data-ttu-id="4f400-119">관리자는 메시지가 지연되었습니다라는 기본 경고 정책의 구성에 따라 전자 메일 **알림을 받게 됩니다.**</span><span class="sxs-lookup"><span data-stu-id="4f400-119">Admins will receive an email notification based on the configuration of the default alert policy named **Messages have been delayed**.</span></span> <span data-ttu-id="4f400-120">이 경고에 대한 알림 설정을 구성하려면 다음 섹션을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="4f400-120">To configure the notification settings for this alert, see the next section.</span></span>

  <span data-ttu-id="4f400-121">경고 정책에 대한 자세한 내용은 보안 및 준수 센터의 경고 [& 참조하세요.](../../compliance/alert-policies.md)</span><span class="sxs-lookup"><span data-stu-id="4f400-121">For more information about alert policies, see [Alert policies in the Security & Compliance Center](../../compliance/alert-policies.md).</span></span>

## <a name="customize-queue-alerts"></a><span data-ttu-id="4f400-122">큐 경고 사용자 지정</span><span class="sxs-lookup"><span data-stu-id="4f400-122">Customize queue alerts</span></span>

1. <span data-ttu-id="4f400-123">보안 & [규정](https://protection.office.com)준수 센터에서 경고  경고 정책으로 \> **이동하거나** 을 를 열 수 <https://protection.office.com/alertpolicies> 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4f400-123">In the [Security & Compliance Center](https://protection.office.com), go to **Alerts** \> **Alert policies** or open <https://protection.office.com/alertpolicies>.</span></span>

2. <span data-ttu-id="4f400-124">경고 **정책 페이지에서** 메시지가 지연된 정책을 **찾아 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="4f400-124">On the **Alert policies** page, find and select the policy named **Messages have been delayed**.</span></span>

3. <span data-ttu-id="4f400-125">메시지가 **지연된** 플라이아웃이 열리면 알림을 켜거나 끄고 알림 설정을 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4f400-125">In the **Message have been delayed** flyout that opens, you can turn the alert on or off and configure the notification settings.</span></span>

   ![메시지가 지연된 경고 정책 세부 정보 보안 & 규정 준수 센터](../../media/mfi-queued-messages-alert-policy.png)

   - <span data-ttu-id="4f400-127">**상태:** 경고를 설정하거나 해제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4f400-127">**Status**: You can toggle the alert on or off.</span></span>

   - <span data-ttu-id="4f400-128">**전자 메일 받는 사람** 및 **일별 알림** 제한: 편집을 클릭하여 다음 설정을 구성합니다. </span><span class="sxs-lookup"><span data-stu-id="4f400-128">**Email recipients** and **Daily notification limit**: Click **Edit** to configure the following settings:</span></span>

4. <span data-ttu-id="4f400-129">알림 설정을 구성하려면 편집 을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="4f400-129">To configure the notification settings, click **Edit**.</span></span> <span data-ttu-id="4f400-130">나타나는 **정책 편집** 플라이아웃에서 다음 설정을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="4f400-130">In the **Edit policy** flyout that appears, configure the following settings:</span></span>

   - <span data-ttu-id="4f400-131">**전자 메일 알림 보내기:** 기본값은 설정되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4f400-131">**Send email notifications**: The default value is on.</span></span>
   - <span data-ttu-id="4f400-132">**전자 메일 받는 사람:** 기본값은 **TenantAdmins입니다.**</span><span class="sxs-lookup"><span data-stu-id="4f400-132">**Email recipients**: The default value is **TenantAdmins**.</span></span>
   - <span data-ttu-id="4f400-133">**일별 알림 제한:** 기본값은 **제한 없음입니다.**</span><span class="sxs-lookup"><span data-stu-id="4f400-133">**Daily notification limit**: The default value is **No limit**.</span></span>
   - <span data-ttu-id="4f400-134">**임계값:** 기본값은 200입니다.</span><span class="sxs-lookup"><span data-stu-id="4f400-134">**Threshold**: The default value is 200.</span></span>

   ![메시지의 알림 설정이 지연된 경고 정책 세부 정보 보안 & 규정 준수 센터](../../media/mfi-queued-messages-alert-policy-notification-settings.png)

5. <span data-ttu-id="4f400-136">완료되면 저장 및 **닫기 를** **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="4f400-136">When you're finished, click **Save** and **Close**.</span></span>

## <a name="queues-insight-in-the-mail-flow-dashboard"></a><span data-ttu-id="4f400-137">메일 흐름 대시보드의 큐 정보</span><span class="sxs-lookup"><span data-stu-id="4f400-137">Queues insight in the Mail flow dashboard</span></span>

<span data-ttu-id="4f400-138">대기 중인 메시지 볼륨이 임계값을 초과하고 경고를 생성하지 않은 경우에도 메일 흐름 대시보드의 **큐** 정보를 사용하여 1시간 넘게 대기 중인 메시지를 보고 대기 중인 메시지 수가 너무 커지기 전에 조치를 취할 수 있습니다. [](mail-flow-insights-v2.md)</span><span class="sxs-lookup"><span data-stu-id="4f400-138">Even if the queued message volume hasn't exceeded the threshold and generated an alert, you can still use the **Queues** insight in the [Mail flow dashboard](mail-flow-insights-v2.md) to see messages that have been queued for more than one hour, and take action before the number of queued messages becomes too large.</span></span>

![보안 및 준수 센터의 메일 흐름 대시보드에서 & 위젯](../../media/mfi-queues-widget.png)

<span data-ttu-id="4f400-140">위젯에서 메시지 수를 클릭하면 메시지 대기  플라이아웃이 다음 정보와 함께 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="4f400-140">If you click the number of messages on the widget, a **Messages queued** flyout appears with the following information:</span></span>

- <span data-ttu-id="4f400-141">**대기 중인 메시지 수**</span><span class="sxs-lookup"><span data-stu-id="4f400-141">**Number of queued messages**</span></span>
- <span data-ttu-id="4f400-142">**커넥터 이름:** 커넥터 이름을 클릭하여 EAC(Exchange 관리 센터)에서 커넥터를 관리합니다.</span><span class="sxs-lookup"><span data-stu-id="4f400-142">**Connector name**: Click on the connector name to manage the connector in the Exchange admin center (EAC).</span></span>
- <span data-ttu-id="4f400-143">**큐 시작 시간**</span><span class="sxs-lookup"><span data-stu-id="4f400-143">**Queue started time**</span></span>
- <span data-ttu-id="4f400-144">**만료된 가장 오래된 메시지**</span><span class="sxs-lookup"><span data-stu-id="4f400-144">**Oldest messages expired**</span></span>
- <span data-ttu-id="4f400-145">**대상 서버**</span><span class="sxs-lookup"><span data-stu-id="4f400-145">**Destination server**</span></span>
- <span data-ttu-id="4f400-146">**마지막 IP 주소**</span><span class="sxs-lookup"><span data-stu-id="4f400-146">**Last IP address**</span></span>
- <span data-ttu-id="4f400-147">**마지막 오류**</span><span class="sxs-lookup"><span data-stu-id="4f400-147">**Last error**</span></span>
- <span data-ttu-id="4f400-148">**해결 방법:** 일반적인 문제 및 해결 방법을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4f400-148">**How to fix**: Common issues and solutions are available.</span></span> <span data-ttu-id="4f400-149">지금 수정 **링크를** 사용할 수 있는 경우 해당 링크를 클릭하여 문제를 해결합니다.</span><span class="sxs-lookup"><span data-stu-id="4f400-149">If is a **Fix it now** link is available, click it to fix the problem.</span></span> <span data-ttu-id="4f400-150">그렇지 않은 경우 사용 가능한 모든 링크를 클릭하여 오류 및 가능한 해결 방법과 관련한 자세한 정보를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="4f400-150">Otherwise, click on any available links for more information about the error and possible solutions.</span></span>

![메일 흐름 대시보드에서 큐 정보를 클릭한 후의 세부 정보](../../media/mfi-queues-details.png)

<span data-ttu-id="4f400-152">지연된 메시지의 세부 정보에서 큐 보기를 클릭하면 동일한 **플라이아웃이** 표시됩니다. </span><span class="sxs-lookup"><span data-stu-id="4f400-152">The same flyout is displayed after you click **View queue** in the details of a **Messages have been delayed** alert.</span></span>

![보안 및 준수 센터에서 메시지가 지연된 & 세부 정보](../../media/mfi-queued-messages-alert-details.png)

## <a name="see-also"></a><span data-ttu-id="4f400-154">참고 항목</span><span class="sxs-lookup"><span data-stu-id="4f400-154">See also</span></span>

<span data-ttu-id="4f400-155">메일 흐름 대시보드의 다른 인사이트에 대한 자세한 내용은 보안 및 준수 센터의 메일 [흐름 & 참조하세요.](mail-flow-insights-v2.md)</span><span class="sxs-lookup"><span data-stu-id="4f400-155">For information about other insights in the Mail flow dashboard, see [Mail flow insights in the Security & Compliance Center](mail-flow-insights-v2.md).</span></span>
