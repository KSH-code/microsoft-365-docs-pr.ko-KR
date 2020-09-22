---
title: 메일 흐름 대시보드의 큐 통찰력
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: 37640c80-ce6f-47e2-afd1-bc1d3c50e637
description: 관리자는 보안 & 준수 센터의 메일 흐름 대시보드에서 큐 위젯을 사용 하 여 아웃 바운드 커넥터를 통해 온-프레미스 또는 파트너 조직으로의 실패 한 메일 흐름을 모니터링 하는 방법에 대해 알아봅니다.
ms.openlocfilehash: 3291a21828215d0a2a99c2226147bb1b748b8469
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/22/2020
ms.locfileid: "48199292"
---
# <a name="queues-insight-in-the-security--compliance-center"></a><span data-ttu-id="d4859-103">보안 & 준수 센터의 큐 통찰력</span><span class="sxs-lookup"><span data-stu-id="d4859-103">Queues insight in the Security & Compliance Center</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="d4859-104">커넥터를 사용 하 여 조직에서 온-프레미스 또는 파트너 전자 메일 서버로 메시지를 보낼 수 없는 경우 해당 메시지는 Microsoft 365에서 대기 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d4859-104">When messages can't be sent from your organization to your on-premises or partner email servers using connectors, the messages are queued in Microsoft 365.</span></span> <span data-ttu-id="d4859-105">이러한 상황을 일으키는 일반적인 예는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="d4859-105">Common examples that cause this condition are:</span></span>

- <span data-ttu-id="d4859-106">커넥터가 올바르게 구성 되지 않았습니다.</span><span class="sxs-lookup"><span data-stu-id="d4859-106">The connector is incorrectly configured.</span></span>
- <span data-ttu-id="d4859-107">온-프레미스 환경에 네트워킹이 나 방화벽이 변경 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="d4859-107">There have been networking or firewall changes in your on-premises environment.</span></span>

<span data-ttu-id="d4859-108">Microsoft 365는 24 시간 동안 배달을 계속 해 서 다시 시도 합니다.</span><span class="sxs-lookup"><span data-stu-id="d4859-108">Microsoft 365 will continue to retry to delivery for 24 hours.</span></span> <span data-ttu-id="d4859-109">24 시간 후에는 메시지가 만료 되어 배달 못 함 보고서 (Ndr 또는 바운스 메시지로도 알려짐)의 보낸 사람에 게 반환 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d4859-109">After 24 hours, the messages will expire and will be returned to the senders in non-delivery reports (also known as a NDRs or bounce messages).</span></span>

<span data-ttu-id="d4859-110">대기 중인 전자 메일 볼륨이 미리 정의 된 임계값을 초과 하는 경우 (기본값은 200 메시지), 다음 위치에서 정보를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d4859-110">If the queued email volume exceeds the pre-defined threshold (the default value is 200 messages), the information is available in the following locations:</span></span>

- <span data-ttu-id="d4859-111">**큐** 는 [보안 & 준수 센터](https://protection.office.com)의 [메일 흐름 대시보드에](mail-flow-insights-v2.md) 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d4859-111">The **Queues** insight in the [Mail flow dashboard](mail-flow-insights-v2.md) in the [Security & Compliance Center](https://protection.office.com).</span></span> <span data-ttu-id="d4859-112">자세한 내용은이 항목의 [메일 흐름 대시보드 섹션에 있는 큐 통찰력](#queues-insight-in-the-mail-flow-dashboard) 를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="d4859-112">For more information, see the [Queues insight in the Mail flow dashboard](#queues-insight-in-the-mail-flow-dashboard) section in this topic.</span></span>
  
- <span data-ttu-id="d4859-113">경고가 **최근 경고** 에 표시 됨 [보안 & 준수 센터](https://protection.office.com) (**경고** \> **대시보드** 또는)의 알림 대시보드 <https://protection.office.com/alertsdashboard></span><span class="sxs-lookup"><span data-stu-id="d4859-113">An alert is displayed in **Recent alerts** the Alerts dashboard in the [Security & Compliance Center](https://protection.office.com) (**Alerts** \> **Dashboard** or <https://protection.office.com/alertsdashboard>).</span></span>

  ![보안 & 준수 센터의 알림 대시보드의 최근 경고](../../media/mfi-queued-messages-alert.png)

- <span data-ttu-id="d4859-115">관리자는 **메시지가 지연**된 기본 경고 정책의 구성에 따라 전자 메일 알림을 받습니다.</span><span class="sxs-lookup"><span data-stu-id="d4859-115">Admins will receive an email notification based on the configuration of the default alert policy named **Messages have been delayed**.</span></span> <span data-ttu-id="d4859-116">이 경고에 대 한 알림 설정을 구성 하려면 다음 섹션을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="d4859-116">To configure the notification settings for this alert, see the next section.</span></span>

  <span data-ttu-id="d4859-117">경고 정책에 대 한 자세한 내용은 [Security & 준수 센터의 경고 정책](../../compliance/alert-policies.md)를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="d4859-117">For more information about alert policies, see [Alert policies in the Security & Compliance Center](../../compliance/alert-policies.md).</span></span>

## <a name="customize-queue-alerts"></a><span data-ttu-id="d4859-118">큐 알림 사용자 지정</span><span class="sxs-lookup"><span data-stu-id="d4859-118">Customize queue alerts</span></span>

1. <span data-ttu-id="d4859-119">[보안 & 준수 센터](https://protection.office.com)에서 **알림** \> **경고 정책** 으로 이동 하거나 엽니다 <https://protection.office.com/alertpolicies> .</span><span class="sxs-lookup"><span data-stu-id="d4859-119">In the [Security & Compliance Center](https://protection.office.com), go to **Alerts** \> **Alert policies** or open <https://protection.office.com/alertpolicies>.</span></span>

2. <span data-ttu-id="d4859-120">**경고 정책** 페이지에서 **메시지가 지연**된 정책을 찾아서 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="d4859-120">On the **Alert policies** page, find and select the policy named **Messages have been delayed**.</span></span>

3. <span data-ttu-id="d4859-121">메시지의 플라이 아웃이 **지연 된** 경우 알림을 켜거나 끄고 알림 설정을 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d4859-121">In the **Message have been delayed** flyout that opens, you can turn the alert on or off and configure the notification settings.</span></span>

   ![메시지가 지연 됨 경고 정책 세부 정보 보안 & 준수 센터](../../media/mfi-queued-messages-alert-policy.png)

   - <span data-ttu-id="d4859-123">**상태**: 알림을 설정 하거나 해제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d4859-123">**Status**: You can toggle the alert on or off.</span></span>

   - <span data-ttu-id="d4859-124">**전자 메일 받는 사람** 및 **일별 알림 제한**: **편집** 을 클릭 하 여 다음 설정을 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="d4859-124">**Email recipients** and **Daily notification limit**: Click **Edit** to configure the following settings:</span></span>

4. <span data-ttu-id="d4859-125">알림 설정을 구성 하려면 **편집**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="d4859-125">To configure the notification settings, click **Edit**.</span></span> <span data-ttu-id="d4859-126">표시 되는 정책 플라이 아웃 **편집** 에서 다음 설정을 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="d4859-126">In the **Edit policy** flyout that appears, configure the following settings:</span></span>

   - <span data-ttu-id="d4859-127">**전자 메일 알림 보내기**: 기본값은 on입니다.</span><span class="sxs-lookup"><span data-stu-id="d4859-127">**Send email notifications**: The default value is on.</span></span>
   - <span data-ttu-id="d4859-128">**전자 메일 받는 사람**: 기본값은 **tenantadmins**입니다.</span><span class="sxs-lookup"><span data-stu-id="d4859-128">**Email recipients**: The default value is **TenantAdmins**.</span></span>
   - <span data-ttu-id="d4859-129">**일별 알림 제한**: 기본값은 **제한이 없습니다**.</span><span class="sxs-lookup"><span data-stu-id="d4859-129">**Daily notification limit**: The default value is **No limit**.</span></span>
   - <span data-ttu-id="d4859-130">**임계값**: 기본값은 200입니다.</span><span class="sxs-lookup"><span data-stu-id="d4859-130">**Threshold**: The default value is 200.</span></span>

   ![메시지의 알림 설정이 지연 됨 경고 정책 세부 정보 보안 & 준수 센터](../../media/mfi-queued-messages-alert-policy-notification-settings.png)

5. <span data-ttu-id="d4859-132">작업이 완료 되 면 **저장** 후 **닫기를**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="d4859-132">When you're finished, click **Save** and **Close**.</span></span>

## <a name="queues-insight-in-the-mail-flow-dashboard"></a><span data-ttu-id="d4859-133">메일 흐름 대시보드의 큐 통찰력</span><span class="sxs-lookup"><span data-stu-id="d4859-133">Queues insight in the Mail flow dashboard</span></span>

<span data-ttu-id="d4859-134">대기 중인 메시지 볼륨이 임계값을 초과 하지 않고 경고가 생성 된 경우에도 [메일 흐름 대시보드에](mail-flow-insights-v2.md) **큐** 통찰력을 사용 하 여 1 시간 이상 대기 된 메시지를 확인 하 고 대기 중인 메시지 수가 너무 커지지 않으면 조치를 취할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d4859-134">Even if the queued message volume hasn't exceeded the threshold and generated an alert, you can still use the **Queues** insight in the [Mail flow dashboard](mail-flow-insights-v2.md) to see messages that have been queued for more than one hour, and take action before the number of queued messages becomes too large.</span></span>

![보안 & 준수 센터의 메일 흐름 대시보드의 큐 위젯](../../media/mfi-queues-widget.png)

<span data-ttu-id="d4859-136">위젯의 메시지 수를 클릭 하면 다음 정보와 함께 **대기 중인 메시지** 플라이 아웃이 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="d4859-136">If you click the number of messages on the widget, a **Messages queued** flyout appears with the following information:</span></span>

- <span data-ttu-id="d4859-137">**대기 중인 메시지 수**</span><span class="sxs-lookup"><span data-stu-id="d4859-137">**Number of queued messages**</span></span>
- <span data-ttu-id="d4859-138">**커넥터 이름**: Exchange 관리 센터 (EAC)에서 커넥터를 관리 하려면 커넥터 이름을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="d4859-138">**Connector name**: Click on the connector name to manage the connector in the Exchange admin center (EAC).</span></span>
- <span data-ttu-id="d4859-139">**큐 시작 시간**</span><span class="sxs-lookup"><span data-stu-id="d4859-139">**Queue started time**</span></span>
- <span data-ttu-id="d4859-140">**가장 오래 된 메시지가 만료 됨**</span><span class="sxs-lookup"><span data-stu-id="d4859-140">**Oldest messages expired**</span></span>
- <span data-ttu-id="d4859-141">**대상 서버**</span><span class="sxs-lookup"><span data-stu-id="d4859-141">**Destination server**</span></span>
- <span data-ttu-id="d4859-142">**마지막 IP 주소**</span><span class="sxs-lookup"><span data-stu-id="d4859-142">**Last IP address**</span></span>
- <span data-ttu-id="d4859-143">**마지막 오류**</span><span class="sxs-lookup"><span data-stu-id="d4859-143">**Last error**</span></span>
- <span data-ttu-id="d4859-144">**해결 방법**: 일반적인 문제 및 해결 방법을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d4859-144">**How to fix**: Common issues and solutions are available.</span></span> <span data-ttu-id="d4859-145">**지금 해결** 방법을 사용할 수 있는 경우에는이 링크를 클릭 하 여 문제를 해결 합니다.</span><span class="sxs-lookup"><span data-stu-id="d4859-145">If is a **Fix it now** link is available, click it to fix the problem.</span></span> <span data-ttu-id="d4859-146">그렇지 않으면 사용 가능한 링크를 클릭 하 여 오류 및 가능한 해결 방법에 대 한 자세한 내용을 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d4859-146">Otherwise, click on any available links for more information about the error and possible solutions.</span></span>

![메일 흐름 대시보드에서 큐 통찰력을 클릭 한 후의 세부 정보](../../media/mfi-queues-details.png)

<span data-ttu-id="d4859-148">메시지 세부 정보에서 **큐 보기** 를 클릭 하 여 경고를 **지연** 한 후에 동일한 플라이 아웃이 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d4859-148">The same flyout is displayed after you click **View queue** in the details of a **Messages have been delayed** alert.</span></span>

![보안 & 준수 센터에서 메시지의 알림 세부 정보가 지연 되었습니다.](../../media/mfi-queued-messages-alert-details.png)

## <a name="see-also"></a><span data-ttu-id="d4859-150">참고 항목</span><span class="sxs-lookup"><span data-stu-id="d4859-150">See also</span></span>

<span data-ttu-id="d4859-151">메일 흐름 대시보드의 다른 정보에 대 한 자세한 내용은 [Security & 준수 센터의 메일 흐름 정보](mail-flow-insights-v2.md)를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="d4859-151">For information about other insights in the Mail flow dashboard, see [Mail flow insights in the Security & Compliance Center](mail-flow-insights-v2.md).</span></span>
