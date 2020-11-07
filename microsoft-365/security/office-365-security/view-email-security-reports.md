---
title: 보안 및 준수 센터의 전자 메일 보안 보고서 보기
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 3a137e28-1174-42d5-99af-f18868b43e86
ms.collection:
- M365-security-compliance
description: 조직의 전자 메일 보안 보고서를 찾아서 사용 하는 방법에 대해 알아봅니다. 보안 & 준수 센터에서 전자 메일 보안 보고서를 사용할 수 있습니다.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: fafb499e40c0014a85c9566b3e5aadf2751202a1
ms.sourcegitcommit: 36795a6735cd3fc678c7d5db71ddc97fac3f6f8a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/06/2020
ms.locfileid: "48941478"
---
# <a name="view-email-security-reports-in-the-security--compliance-center"></a><span data-ttu-id="939d2-104">보안 및 준수 센터의 전자 메일 보안 보고서 보기</span><span class="sxs-lookup"><span data-stu-id="939d2-104">View email security reports in the Security & Compliance Center</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="939d2-105">[보안 & 준수 센터](https://protection.office.com) 에서 다양 한 보고서를 사용할 수 있으며, Microsoft 365의 스팸 방지, 맬웨어 방지 및 암호화 기능과 같은 전자 메일 보안 기능이 조직을 보호 하는 방법을 확인 하는 데 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="939d2-105">A variety of reports are available in the [Security & Compliance Center](https://protection.office.com) to help you see how email security features, such as anti-spam, anti-malware, and encryption features in Microsoft 365 are protecting your organization.</span></span> <span data-ttu-id="939d2-106">[필요한 권한이](#what-permissions-are-needed-to-view-these-reports)있는 경우 **보고서** 대시보드로 이동 하 여 보안 & 준수 센터에서 이러한 보고서를 볼 수 있습니다 \> **Dashboard**.</span><span class="sxs-lookup"><span data-stu-id="939d2-106">If you have the [necessary permissions](#what-permissions-are-needed-to-view-these-reports), you can view these reports in the Security & Compliance Center by going to **Reports** \> **Dashboard**.</span></span> <span data-ttu-id="939d2-107">보고서 대시보드로 직접 이동 하려면를 엽니다 <https://protection.office.com/insightdashboard> .</span><span class="sxs-lookup"><span data-stu-id="939d2-107">To go directly to the Reports dashboard, open <https://protection.office.com/insightdashboard>.</span></span>

![보안 & 준수 센터의 보고서 대시보드](../../media/6b213d34-adbb-44af-8549-be9a7e2db087.png)

## <a name="compromised-users-report"></a><span data-ttu-id="939d2-109">손상 된 사용자 보고서</span><span class="sxs-lookup"><span data-stu-id="939d2-109">Compromised users report</span></span>

> [!NOTE]
> <span data-ttu-id="939d2-110">이 보고서는 Microsoft 365 조직에서 Exchange Online 사서함을 사용 하는 경우에 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="939d2-110">This report is available in Microsoft 365 organizations with Exchange Online mailboxes.</span></span> <span data-ttu-id="939d2-111">독립 실행형 EOP (Exchange Online Protection) 조직에서는이 기능을 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="939d2-111">It's not available in standalone Exchange Online Protection (EOP) organizations.</span></span>

<span data-ttu-id="939d2-112">**손상 된 사용자** 보고서에는 최근 7 일 이내에 **의심** 또는 **제한** 된 것으로 표시 된 사용자 계정 수가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="939d2-112">The **Compromised users** report shows shows the number of user accounts that were marked as **Suspicious** or **Restricted** within the last 7 days.</span></span> <span data-ttu-id="939d2-113">이러한 두 가지 상태의 계정은 문제가 있거나 심지어도 손상 됩니다.</span><span class="sxs-lookup"><span data-stu-id="939d2-113">Accounts in either of these states are problematic or even compromised.</span></span> <span data-ttu-id="939d2-114">자주 사용 하는 경우 보고서를 사용 하 여 의심 스러운 또는 제한 된 계정의 스파이크 및 추세를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="939d2-114">With frequent use, you can use the report to spot spikes, and even trends, in suspicious or restricted accounts.</span></span> <span data-ttu-id="939d2-115">사용자 손상에 대 한 자세한 내용은 [손상 된 전자 메일 계정에 응답](responding-to-a-compromised-email-account.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="939d2-115">For more information about compromised users, see [Responding to a compromised email account](responding-to-a-compromised-email-account.md).</span></span>

![보고서 대시보드의 손상 된 사용자 위젯](../../media/compromised-users-report-widget.png)

<span data-ttu-id="939d2-117">집계 보기는 최근 90 일 동안의 데이터를 표시 하 고, 자세히 보기에는 지난 30 일 동안의 데이터가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="939d2-117">The aggregate view shows data for the last 90 days and the detail view shows data for the last 30 days.</span></span>

<span data-ttu-id="939d2-118">보고서를 보려면 [보안 & 준수 센터](https://protection.office.com)를 열고 **보고서** \> **대시보드로** 이동한 다음 **손상 된 사용자** 를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="939d2-118">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Compromised users**.</span></span> <span data-ttu-id="939d2-119">보고서로 직접 이동 하려면를 엽니다 <https://protection.office.com/reportv2?id=CompromisedUsers> .</span><span class="sxs-lookup"><span data-stu-id="939d2-119">To go directly to the report, open <https://protection.office.com/reportv2?id=CompromisedUsers>.</span></span>

<span data-ttu-id="939d2-120">**필터** 를 클릭 하 고 다음 값 중 하나 이상을 선택 하 여 차트 및 세부 정보 테이블을 모두 필터링 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="939d2-120">You can filter both the chart and the details table by clicking **Filters** and selecting one or more of the following values:</span></span>

- <span data-ttu-id="939d2-121">**시작 날짜** 및 **끝 날짜**</span><span class="sxs-lookup"><span data-stu-id="939d2-121">**Start date** and **End date**</span></span>

- <span data-ttu-id="939d2-122">**의심 스러운** : 사용자 계정에서 의심 스러운 전자 메일을 보냈지만 전자 메일을 보낼 수 없게 되는 위험에 노출 됩니다.</span><span class="sxs-lookup"><span data-stu-id="939d2-122">**Suspicious** : The user account has sent suspicious email and is at risk of being restricted from sending email.</span></span>

- <span data-ttu-id="939d2-123">**제한** : 사용자 계정이 의심 스러운 높은 패턴으로 인해 전자 메일을 보내지 못하도록 제한 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="939d2-123">**Restricted** : The user account has been restricted from sending email due to highly suspicious patterns.</span></span>

![손상 된 사용자 보고서의 보고서 보기](../../media/compromised-users-report-activity-view.png)

<span data-ttu-id="939d2-125">**세부 정보 테이블 보기** 를 클릭 하면 다음 세부 정보를 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="939d2-125">If you click **View details table** , you can see the following details:</span></span>

- <span data-ttu-id="939d2-126">**만든 시간**</span><span class="sxs-lookup"><span data-stu-id="939d2-126">**Creation time**</span></span>
- <span data-ttu-id="939d2-127">**사용자 ID**</span><span class="sxs-lookup"><span data-stu-id="939d2-127">**User ID**</span></span>
- <span data-ttu-id="939d2-128">**작업**</span><span class="sxs-lookup"><span data-stu-id="939d2-128">**Action**</span></span>

<span data-ttu-id="939d2-129">보고서 보기로 돌아가려면 **보고서 보기** 를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="939d2-129">To go back to the report view, click **View report**.</span></span>

## <a name="encryption-report"></a><span data-ttu-id="939d2-130">암호화 보고서</span><span class="sxs-lookup"><span data-stu-id="939d2-130">Encryption report</span></span>

<span data-ttu-id="939d2-131">**암호화 보고서** 는 EOP (exchange online의 사서함과 exchange online 사서함이 없는 독립 실행형 EOP 구독)에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="939d2-131">The **Encryption report** is available in EOP (subscriptions with mailboxes in Exchange Online or standalone EOP without Exchange Online mailboxes).</span></span> <span data-ttu-id="939d2-132">조직의 보안 팀은이 보고서의 정보를 사용 하 여 패턴을 식별 하 고 중요 한 전자 메일 메시지에 대 한 정책을 사전에 적용 하거나 조정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="939d2-132">Your organization's security team can use information in this report to identify patterns and proactively apply or adjust policies for sensitive email messages.</span></span> <span data-ttu-id="939d2-133">예제:</span><span class="sxs-lookup"><span data-stu-id="939d2-133">For example:</span></span>

- <span data-ttu-id="939d2-134">사용자가 암호화 한 전자 메일 메시지가 많은 경우 특정 사용 사례에 대 한 암호화를 자동화 하는 암호화 정책을 추가 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="939d2-134">If you see a high number of email messages encrypted by users, you might want to add an encryption policy to automate encryption for certain use cases.</span></span> <span data-ttu-id="939d2-135">자세한 내용은 [Microsoft 365에서 전자 메일 메시지를 암호화 하는 메일 흐름 규칙 정의](../../compliance/define-mail-flow-rules-to-encrypt-email.md)를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="939d2-135">For more information, see [Define mail flow rules to encrypt email messages in Microsoft 365](../../compliance/define-mail-flow-rules-to-encrypt-email.md).</span></span>

- <span data-ttu-id="939d2-136">사용할 수 있는 암호화 서식 파일의 수가 여러 개 있지만 아무도 사용 하지 않는 경우에는 사용자가 기능 교육을 필요로 하는지 여부를 탐색할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="939d2-136">If you have a number of encryption templates available but no one is using them, you might explore whether users need feature training.</span></span>

<span data-ttu-id="939d2-137">집계 보기는 최근 90 일에 대 한 필터링을 허용 하 고 세부 정보 보기는 10 일 동안 필터링을 허용 합니다.</span><span class="sxs-lookup"><span data-stu-id="939d2-137">The aggregate view allows filtering for the last 90 days, while the detail view allows filtering for 10 days.</span></span>

<span data-ttu-id="939d2-138">보고서를 보려면 [보안 & 준수 센터](https://protection.office.com)를 열고 **보고서** \> **대시보드로** 이동한 다음 **암호화 보고서** 를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="939d2-138">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Encryption report**.</span></span> <span data-ttu-id="939d2-139">보고서로 직접 이동 하려면를 엽니다 <https://protection.office.com/reportv2?id=EncryptionReport> .</span><span class="sxs-lookup"><span data-stu-id="939d2-139">To go directly to the report, open <https://protection.office.com/reportv2?id=EncryptionReport>.</span></span>

<span data-ttu-id="939d2-140">암호화에 대 한 자세한 내용은 [Microsoft 365의 전자 메일 암호화](../../compliance/email-encryption.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="939d2-140">To learn more about encryption, see [Email encryption in Microsoft 365](../../compliance/email-encryption.md).</span></span>

### <a name="report-view-for-the-encryption-report"></a><span data-ttu-id="939d2-141">암호화 보고서에 대 한 보고서 보기</span><span class="sxs-lookup"><span data-stu-id="939d2-141">Report view for the Encryption report</span></span>

<span data-ttu-id="939d2-142">차트에서 다음 필터를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="939d2-142">You can use the following filters on the chart:</span></span>

- <span data-ttu-id="939d2-143">**데이터 보기 기준: 메시지 암호화 보고서** 및 **아래로 나누기: 암호화 방법** : 다음과 같은 암호화 방법을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="939d2-143">**View data by: Message Encryption Report** and **Break down by: Encryption method** : The following encryption methods are available:</span></span>

  - <span data-ttu-id="939d2-144">**사용자별 암호화**</span><span class="sxs-lookup"><span data-stu-id="939d2-144">**Encryption by user**</span></span>
  - <span data-ttu-id="939d2-145">**정책에의 한 암호화**</span><span class="sxs-lookup"><span data-stu-id="939d2-145">**Encryption by policy**</span></span>

  <span data-ttu-id="939d2-146">**필터** 를 클릭 하면 다음 필터를 사용 하 여 차트를 수정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="939d2-146">If you click **Filters** , you can modify the chart with the following filters:</span></span>

  - <span data-ttu-id="939d2-147">**시작 날짜** 및 **끝 날짜**</span><span class="sxs-lookup"><span data-stu-id="939d2-147">**Start date** and **End date**</span></span>
  - <span data-ttu-id="939d2-148">암호화 방법</span><span class="sxs-lookup"><span data-stu-id="939d2-148">Encryption method.</span></span>
  - <span data-ttu-id="939d2-149">암호화 서식 파일</span><span class="sxs-lookup"><span data-stu-id="939d2-149">Encryption template.</span></span>

- <span data-ttu-id="939d2-150">**데이터 보기 기준: 메시지 암호화 보고서** 및 **아래로 나누기: 암호화 서식 파일** : 다음과 같은 암호화 방법을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="939d2-150">**View data by: Message Encryption Report** and **Break down by: Encryption template** : The following encryption methods are available:</span></span>

  - <span data-ttu-id="939d2-151">**전달 금지**</span><span class="sxs-lookup"><span data-stu-id="939d2-151">**Do not forward**</span></span>
  - <span data-ttu-id="939d2-152">**암호화만**</span><span class="sxs-lookup"><span data-stu-id="939d2-152">**Encrypt only**</span></span>
  - <span data-ttu-id="939d2-153">**이전 OME**</span><span class="sxs-lookup"><span data-stu-id="939d2-153">**OME previous**</span></span>
  - <span data-ttu-id="939d2-154">**사용자 지정**</span><span class="sxs-lookup"><span data-stu-id="939d2-154">**Custom**</span></span>

  <span data-ttu-id="939d2-155">**필터** 를 클릭 하면 다음 필터를 사용 하 여 차트를 수정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="939d2-155">If you click **Filters** , you can modify the chart with the following filters:</span></span>

  - <span data-ttu-id="939d2-156">**시작 날짜** 및 **끝 날짜**</span><span class="sxs-lookup"><span data-stu-id="939d2-156">**Start date** and **End date**</span></span>
  - <span data-ttu-id="939d2-157">암호화 방법</span><span class="sxs-lookup"><span data-stu-id="939d2-157">Encryption method</span></span>
  - <span data-ttu-id="939d2-158">암호화 서식 파일</span><span class="sxs-lookup"><span data-stu-id="939d2-158">Encryption template</span></span>

- <span data-ttu-id="939d2-159">**데이터 보기 기준: 상위 5 개 받는 사람 도메인** :이 보기에는 상위 5 개 받는 사람 도메인에 대 한 보낸 메시지 수가 표시 되는 원형 차트가 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="939d2-159">**View data by: Top 5 recipient domains** : This view shows a pie chart with sent message counts for the top 5 recipient domains.</span></span>

  <span data-ttu-id="939d2-160">**필터** 를 클릭 하면 **시작 날짜** 와 **끝 날짜** 를 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="939d2-160">If you click **Filters** , you can select a **Start date** and **End date**.</span></span>

### <a name="details-table-view-for-the-encryption-report"></a><span data-ttu-id="939d2-161">암호화 보고서에 대 한 세부 정보 테이블 보기</span><span class="sxs-lookup"><span data-stu-id="939d2-161">Details table view for the Encryption report</span></span>

<span data-ttu-id="939d2-162">**세부 정보 표 보기** 를 클릭 하면 표시 되는 정보는 보고 있는 차트에 따라 달라 집니다.</span><span class="sxs-lookup"><span data-stu-id="939d2-162">If you click **View details table** , the information that's shown depends on the chart you were looking at:</span></span>

- <span data-ttu-id="939d2-163">**아래로 나누기: 암호화 방법** 또는 **아래로 나누기: 암호화 서식 파일** : 다음 정보가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="939d2-163">**Break down by: Encryption method** or **Break down by: Encryption template** : The following information is shown:</span></span>

  - <span data-ttu-id="939d2-164">**날짜**</span><span class="sxs-lookup"><span data-stu-id="939d2-164">**Date**</span></span>
  - <span data-ttu-id="939d2-165">**보낸 사람 주소**</span><span class="sxs-lookup"><span data-stu-id="939d2-165">**Sender address**</span></span>
  - <span data-ttu-id="939d2-166">**암호화 서식 파일**</span><span class="sxs-lookup"><span data-stu-id="939d2-166">**Encryption template**</span></span>
  - <span data-ttu-id="939d2-167">**암호화 방법**</span><span class="sxs-lookup"><span data-stu-id="939d2-167">**Encryption method**</span></span>
  - <span data-ttu-id="939d2-168">**받는 사람 주소**</span><span class="sxs-lookup"><span data-stu-id="939d2-168">**Recipient address**</span></span>
  - <span data-ttu-id="939d2-169">**제목**</span><span class="sxs-lookup"><span data-stu-id="939d2-169">**Subject**</span></span>

- <span data-ttu-id="939d2-170">**데이터 보기 기준: 상위 5 개 받는 사람 도메인** :</span><span class="sxs-lookup"><span data-stu-id="939d2-170">**View data by: Top 5 recipient domains** :</span></span>

  - <span data-ttu-id="939d2-171">**날짜**</span><span class="sxs-lookup"><span data-stu-id="939d2-171">**Date**</span></span>
  - <span data-ttu-id="939d2-172">**받는 사람 도메인**</span><span class="sxs-lookup"><span data-stu-id="939d2-172">**Recipient domain**</span></span>
  - <span data-ttu-id="939d2-173">**메시지 수**</span><span class="sxs-lookup"><span data-stu-id="939d2-173">**Message count**</span></span>
  
<span data-ttu-id="939d2-174">세부 정보 표 보기에서 **필터** 를 클릭 하면 다음 필터를 사용 하 여 결과를 수정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="939d2-174">If you click **Filters** in a details table view, you can modify the results with the following filters:</span></span>

- <span data-ttu-id="939d2-175">**시작 날짜** 및 **끝 날짜**</span><span class="sxs-lookup"><span data-stu-id="939d2-175">**Start date** and **End date**</span></span>
- <span data-ttu-id="939d2-176">암호화 방법</span><span class="sxs-lookup"><span data-stu-id="939d2-176">Encryption method</span></span>
- <span data-ttu-id="939d2-177">암호화 서식 파일</span><span class="sxs-lookup"><span data-stu-id="939d2-177">Encryption template</span></span>

<span data-ttu-id="939d2-178">보고서 보기로 돌아가려면 **보고서 보기** 를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="939d2-178">To go back to the report view, click **View report**.</span></span>

## <a name="mailflow-status-report"></a><span data-ttu-id="939d2-179">메일 흐름 상태 보고서</span><span class="sxs-lookup"><span data-stu-id="939d2-179">Mailflow status report</span></span>

<span data-ttu-id="939d2-180">**메일 흐름 status 보고서** 에는 맬웨어, 스팸, 피싱 및에 지 차단 된 메시지에 대 한 정보가 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="939d2-180">The **Mailflow status report** contains information about malware, spam, phishing and edge blocked messages.</span></span> <span data-ttu-id="939d2-181">자세한 내용은 [메일 흐름 status report](view-mail-flow-reports.md#mailflow-status-report)를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="939d2-181">For more details, see [Mailflow status report](view-mail-flow-reports.md#mailflow-status-report).</span></span>

## <a name="malware-detections-in-email-report"></a><span data-ttu-id="939d2-182">전자 메일 보고서에서 맬웨어 감지</span><span class="sxs-lookup"><span data-stu-id="939d2-182">Malware detections in email report</span></span>

<span data-ttu-id="939d2-183">**전자 메일 보고서에서** 검색 된 맬웨어는 들어오는 및 보내는 전자 메일 메시지의 맬웨어 감지에 대 한 정보를 표시 합니다 (Exchange Online PROTECTION 또는 EOP에서 감지한 맬웨어).</span><span class="sxs-lookup"><span data-stu-id="939d2-183">The **Malware detections in email** report shows information about malware detections in incoming and outgoing email messages (malware detected by Exchange Online Protection or EOP).</span></span> <span data-ttu-id="939d2-184">EOP의 맬웨어 보호에 대 한 자세한 내용은 [EOP의 맬웨어 방지 보호](anti-malware-protection.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="939d2-184">For more information about malware protection in EOP, see [Anti-malware protection in EOP](anti-malware-protection.md).</span></span>

 <span data-ttu-id="939d2-185">집계 보기 필터는 90 일을 허용 하 고 세부 정보 테이블 필터는 10 일 동안만 허용 합니다.</span><span class="sxs-lookup"><span data-stu-id="939d2-185">The aggregate view filter allows for 90 days, while the details table filter only allows for 10 days.</span></span>

<span data-ttu-id="939d2-186">보고서를 보려면 [보안 & 준수 센터](https://protection.office.com)를 열고 **보고서** \> **대시보드로** 이동한 후 **전자 메일로 맬웨어 감지** 를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="939d2-186">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Malware detections in email**.</span></span> <span data-ttu-id="939d2-187">보고서로 직접 이동 하려면를 엽니다 <https://protection.office.com/reportv2?id=MalwareDetections> .</span><span class="sxs-lookup"><span data-stu-id="939d2-187">To go directly to the report, open <https://protection.office.com/reportv2?id=MalwareDetections>.</span></span>

![보고서 대시보드의 전자 메일 위젯에 있는 맬웨어 감지](../../media/malware-detections-widget.png)

<span data-ttu-id="939d2-189">**필터** 를 클릭 하 고 다음을 선택 하 여 차트 및 세부 정보 테이블을 모두 필터링 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="939d2-189">You can filter both the chart and the details table by clicking **Filters** and selecting:</span></span>

- <span data-ttu-id="939d2-190">**시작 날짜** 및 **끝 날짜**</span><span class="sxs-lookup"><span data-stu-id="939d2-190">**Start date** and **End date**</span></span>
- <span data-ttu-id="939d2-191">**인바운드**</span><span class="sxs-lookup"><span data-stu-id="939d2-191">**Inbound**</span></span>
- <span data-ttu-id="939d2-192">**아웃 바운드**</span><span class="sxs-lookup"><span data-stu-id="939d2-192">**Outbound**</span></span>

![전자 메일 보고서의 맬웨어 검색에서 보고서 보기](../../media/malware-detections-report-view.png)

<span data-ttu-id="939d2-194">**세부 정보 테이블 보기** 를 클릭 하면 다음 세부 정보를 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="939d2-194">If you click **View details table** , you can see the following details:</span></span>

- <span data-ttu-id="939d2-195">**날짜**</span><span class="sxs-lookup"><span data-stu-id="939d2-195">**Date**</span></span>
- <span data-ttu-id="939d2-196">**보낸 사람 주소**</span><span class="sxs-lookup"><span data-stu-id="939d2-196">**Sender address**</span></span>
- <span data-ttu-id="939d2-197">**받는 사람 주소**</span><span class="sxs-lookup"><span data-stu-id="939d2-197">**Recipient address**</span></span>
- <span data-ttu-id="939d2-198">**메시지 id** : 메시지 헤더의 **메시지 id** 헤더 필드에서 사용할 수 있으며 고유 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="939d2-198">**Message ID** : Available in the **Message-ID** header field in the message header and should be unique.</span></span> <span data-ttu-id="939d2-199">예를 들면 `<08f1e0f6806a47b4ac103961109ae6ef@server.domain>` 꺾쇠 괄호를 참고 하십시오.</span><span class="sxs-lookup"><span data-stu-id="939d2-199">An example value is `<08f1e0f6806a47b4ac103961109ae6ef@server.domain>` (note the angle brackets).</span></span>
- <span data-ttu-id="939d2-200">**제목**</span><span class="sxs-lookup"><span data-stu-id="939d2-200">**Subject**</span></span>
- <span data-ttu-id="939d2-201">**파일 이름**</span><span class="sxs-lookup"><span data-stu-id="939d2-201">**Filename**</span></span>
- <span data-ttu-id="939d2-202">**맬웨어 이름**</span><span class="sxs-lookup"><span data-stu-id="939d2-202">**Malware name**</span></span>

<span data-ttu-id="939d2-203">보고서 보기로 돌아가려면 **보고서 보기** 를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="939d2-203">To go back to the report view, click **View report**.</span></span>

## <a name="sent-and-received-email-report"></a><span data-ttu-id="939d2-204">보내고 받은 전자 메일 보고서</span><span class="sxs-lookup"><span data-stu-id="939d2-204">Sent and received email report</span></span>

<span data-ttu-id="939d2-205">**Sent and received 전자 메일** 보고서에는 맬웨어, 스팸, 메일 흐름 규칙 (전송 규칙이 라고도 함) 및 고급 맬웨어 검색 후 서비스가 서비스를 시작한 후에 대 한 정보가 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="939d2-205">The **Sent and received email** report contains information about malware, spam, mail flow rules (also known as transport rules), and advanced malware detections after email enters the service.</span></span> <span data-ttu-id="939d2-206">자세한 내용은 [Sent and received email report](view-mail-flow-reports.md#sent-and-received-email-report)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="939d2-206">For more information, see [Sent and received email report](view-mail-flow-reports.md#sent-and-received-email-report).</span></span>

## <a name="spam-detections-report"></a><span data-ttu-id="939d2-207">스팸 검색 보고서</span><span class="sxs-lookup"><span data-stu-id="939d2-207">Spam detections report</span></span>

<span data-ttu-id="939d2-208">**스팸 감지** 보고서에는 EOP에 의해 차단 된 스팸 전자 메일 메시지가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="939d2-208">The **Spam detections** report shows spam email messages that were blocked by EOP.</span></span> <span data-ttu-id="939d2-209">메시지는 받는 사람이 아닌 개별 단위로 계산 됩니다.</span><span class="sxs-lookup"><span data-stu-id="939d2-209">Messages are counted individually, not per recipient.</span></span> <span data-ttu-id="939d2-210">예를 들어 조직에서 100 받는 사람에 게 동일한 스팸 메시지를 전송 하면 하나의 메시지로 계산 됩니다.</span><span class="sxs-lookup"><span data-stu-id="939d2-210">For example, if the same spam message was sent to 100 recipients in your organization, it counts as one message.</span></span>

<span data-ttu-id="939d2-211">집계 보기는 90 일 필터링을 허용 하지만 details 테이블은 10 일 필터링을 허용 합니다.</span><span class="sxs-lookup"><span data-stu-id="939d2-211">The aggregate view allows for 90 days filtering, while the details table allows for 10 days filtering.</span></span>

<span data-ttu-id="939d2-212">보고서를 보려면 [보안 & 준수 센터](https://protection.office.com)를 열고 **보고서** \> **대시보드로** 이동한 후 **스팸 감지** 를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="939d2-212">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Spam detections**.</span></span> <span data-ttu-id="939d2-213">보고서로 직접 이동 하려면를 엽니다 <https://protection.office.com/reportv2?id=SpamDetections> .</span><span class="sxs-lookup"><span data-stu-id="939d2-213">To go directly to the report, open <https://protection.office.com/reportv2?id=SpamDetections>.</span></span>

![보고서 대시보드의 스팸 감지 위젯](../../media/spam-detections-report-widget.png)

<span data-ttu-id="939d2-215">스팸 방지 보호 기능에 대 한 자세한 내용은 [EOP의 스팸 방지 보호](anti-spam-protection.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="939d2-215">For more information about anti-spam protection, see [Anti-spam protection in EOP](anti-spam-protection.md).</span></span>

### <a name="report-view-for-the-spam-detections-report"></a><span data-ttu-id="939d2-216">스팸 감지 보고서에 대 한 보고서 보기</span><span class="sxs-lookup"><span data-stu-id="939d2-216">Report view for the Spam detections report</span></span>

<span data-ttu-id="939d2-217">보고서 보기에서는 다음과 같은 차트를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="939d2-217">The following charts are available in the report view:</span></span>

- <span data-ttu-id="939d2-218">**아래로 나누기: 작업** : 다음 이벤트 유형이 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="939d2-218">**Break down by: Action** : The following event types are shown:</span></span>

  - <span data-ttu-id="939d2-219">**스팸 콘텐츠 필터링 됨**</span><span class="sxs-lookup"><span data-stu-id="939d2-219">**Spam content filtered**</span></span>
  - <span data-ttu-id="939d2-220">**스팸 IP 차단**</span><span class="sxs-lookup"><span data-stu-id="939d2-220">**Spam IP block**</span></span>
  - <span data-ttu-id="939d2-221">**스팸 봉투 블록**</span><span class="sxs-lookup"><span data-stu-id="939d2-221">**Spam envelope block**</span></span>
  - <span data-ttu-id="939d2-222">**스팸 DBEB 필터** : dbeb (디렉터리 기반 edge 차단)</span><span class="sxs-lookup"><span data-stu-id="939d2-222">**Spam DBEB filter** : Directory based edge blocking (DBEB)</span></span>

  <span data-ttu-id="939d2-223">차트의 날짜 (데이터 요소)를 가리키면 해당 항목이 분류 되는 방식과 해당 일이 차단 된 항목의 수를 볼 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="939d2-223">When you hover over a day (data point) in the chart, you can see how many items were blocked that day, as well as how those items are categorized.</span></span>

  ![스팸 감지 보고서의 작업 보기](../../media/spam-detections-report-action-view.png)

- <span data-ttu-id="939d2-225">**나누기: 방향** : 다음 지침을 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="939d2-225">**Break down by: Direction** : The following directions are shown:</span></span>

  - <span data-ttu-id="939d2-226">**인바운드**</span><span class="sxs-lookup"><span data-stu-id="939d2-226">**Inbound**</span></span>
  - <span data-ttu-id="939d2-227">**아웃 바운드**</span><span class="sxs-lookup"><span data-stu-id="939d2-227">**Outbound**</span></span>

  ![스팸 감지 보고서의 방향 보기](../../media/spam-detections-report-direction-view.png)

<span data-ttu-id="939d2-229">보고서 보기에서 **필터** 를 클릭 하면 다음 필터를 사용 하 여 결과를 수정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="939d2-229">If you click **Filters** in a report view, you can modify the results with the following filters:</span></span>

- <span data-ttu-id="939d2-230">**시작 날짜** 및 **끝 날짜**</span><span class="sxs-lookup"><span data-stu-id="939d2-230">**Start date** and **End date**</span></span>
- <span data-ttu-id="939d2-231">방향 값</span><span class="sxs-lookup"><span data-stu-id="939d2-231">Direction values</span></span>
- <span data-ttu-id="939d2-232">이벤트 유형 값</span><span class="sxs-lookup"><span data-stu-id="939d2-232">Event type values</span></span>

### <a name="details-table-view-for-the-spam-detections-report"></a><span data-ttu-id="939d2-233">스팸 감지 보고서에 대 한 세부 정보 테이블 보기</span><span class="sxs-lookup"><span data-stu-id="939d2-233">Details table view for the Spam detections report</span></span>

<span data-ttu-id="939d2-234">모든 보고서 보기에서 **세부 정보 테이블 보기** 를 클릭 하면 다음과 같은 정보가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="939d2-234">If you click **View details table** in any report view, the following information is shown:</span></span>

- <span data-ttu-id="939d2-235">**날짜**</span><span class="sxs-lookup"><span data-stu-id="939d2-235">**Date**</span></span>
- <span data-ttu-id="939d2-236">**보낸 사람 주소**</span><span class="sxs-lookup"><span data-stu-id="939d2-236">**Sender address**</span></span>
- <span data-ttu-id="939d2-237">**받는 사람 주소**</span><span class="sxs-lookup"><span data-stu-id="939d2-237">**Recipient address**</span></span>
- <span data-ttu-id="939d2-238">**이벤트 유형**</span><span class="sxs-lookup"><span data-stu-id="939d2-238">**Event type**</span></span>
- <span data-ttu-id="939d2-239">**작업**</span><span class="sxs-lookup"><span data-stu-id="939d2-239">**Action**</span></span>
- <span data-ttu-id="939d2-240">**제목**</span><span class="sxs-lookup"><span data-stu-id="939d2-240">**Subject**</span></span>

<span data-ttu-id="939d2-241">세부 정보 테이블에서 **필터** 를 클릭 하면 다음 필터를 사용 하 여 결과를 수정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="939d2-241">If you click **Filters** in a details table, you can modify the results with the following filters:</span></span>

- <span data-ttu-id="939d2-242">**시작 날짜** 및 **끝 날짜**</span><span class="sxs-lookup"><span data-stu-id="939d2-242">**Start date** and **End date**</span></span>
- <span data-ttu-id="939d2-243">방향 값</span><span class="sxs-lookup"><span data-stu-id="939d2-243">Direction values</span></span>
- <span data-ttu-id="939d2-244">이벤트 유형 값</span><span class="sxs-lookup"><span data-stu-id="939d2-244">Event type values</span></span>

<span data-ttu-id="939d2-245">보고서 보기로 돌아가려면 **보고서 보기** 를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="939d2-245">To go back to the report view, click **View report**.</span></span>

## <a name="spoof-detections-report"></a><span data-ttu-id="939d2-246">스푸핑 감지 보고서</span><span class="sxs-lookup"><span data-stu-id="939d2-246">Spoof detections report</span></span>

<span data-ttu-id="939d2-247">**스푸핑** 감지 보고서에는 얼마나 많은 스푸핑 메일 메시지가 검색 되었는지, 즉 합법적인 비즈니스 이유로 인해 스푸핑 메일을 "양호" 한 것으로 간주 되는 메시지 들이 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="939d2-247">The **Spoof detections** report shows how many spoof mail messages were detected, and of those, which ones were considered "good" (spoof mail done for legitimate business reasons).</span></span> <span data-ttu-id="939d2-248">스푸핑에 대 한 자세한 내용은 [EOP에서 스푸핑 방지 보호](anti-spoofing-protection.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="939d2-248">For more information about spoofing, see [Anti-spoofing protection in EOP](anti-spoofing-protection.md).</span></span>

<span data-ttu-id="939d2-249">보고서의 집계 보기에서 90 일의 필터링을 허용 하 고 세부 정보 보기에서는 필터링을 10 일 동안만 허용 합니다.</span><span class="sxs-lookup"><span data-stu-id="939d2-249">The aggregate view of the report allows for 90 days of filtering, while the detail view only allows for ten days of filtering.</span></span>

<span data-ttu-id="939d2-250">보고서를 보려면 [보안 & 준수 센터](https://protection.office.com)를 열고 **보고서** \> **대시보드로** 이동한 후 검색을 **스푸핑** 합니다 .를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="939d2-250">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Spoof detections**.</span></span> <span data-ttu-id="939d2-251">보고서로 직접 이동 하려면를 엽니다 <https://protection.office.com/reportv2?id=SpoofMailReport> .</span><span class="sxs-lookup"><span data-stu-id="939d2-251">To go directly to the report, open <https://protection.office.com/reportv2?id=SpoofMailReport>.</span></span>

![보고서 대시보드의 스푸핑 감지 위젯](../../media/spoof-detections-widget.png)

<span data-ttu-id="939d2-253">차트에서 일 (데이터 요소)을 가리키면 위장 메일 메시지의 수를 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="939d2-253">When you hover over a day (data point) in the chart, you can see how many spoof mail messages came through.</span></span>

<span data-ttu-id="939d2-254">**필터** 를 클릭 하 고 다음 값 중 하나 이상을 선택 하 여 차트 및 세부 정보 테이블을 모두 필터링 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="939d2-254">You can filter both the chart and the details table by clicking **Filters** and selecting one or more of the following values:</span></span>

- <span data-ttu-id="939d2-255">**시작 날짜** 및 **끝 날짜**</span><span class="sxs-lookup"><span data-stu-id="939d2-255">**Start date** and **End date**</span></span>

- <span data-ttu-id="939d2-256">**좋은 메일**</span><span class="sxs-lookup"><span data-stu-id="939d2-256">**Good mail**</span></span>

- <span data-ttu-id="939d2-257">**스팸으로 감지**</span><span class="sxs-lookup"><span data-stu-id="939d2-257">**Caught as spam**</span></span>

![스푸핑 감지 보고서의 보고서 보기](../../media/spoof-detections-report-view.png)

<span data-ttu-id="939d2-259">**세부 정보 테이블 보기** 를 클릭 하면 다음 세부 정보를 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="939d2-259">If you click **View details table** , you can see the following details:</span></span>

- <span data-ttu-id="939d2-260">**날짜**</span><span class="sxs-lookup"><span data-stu-id="939d2-260">**Date**</span></span>
- <span data-ttu-id="939d2-261">**스푸핑된 보낸 사람**</span><span class="sxs-lookup"><span data-stu-id="939d2-261">**Spoofed sender**</span></span>
- <span data-ttu-id="939d2-262">**True 보낸 사람**</span><span class="sxs-lookup"><span data-stu-id="939d2-262">**True sender**</span></span>
- <span data-ttu-id="939d2-263">**보낸 사람 IP**</span><span class="sxs-lookup"><span data-stu-id="939d2-263">**Sender IP**</span></span>
- <span data-ttu-id="939d2-264">**작업**</span><span class="sxs-lookup"><span data-stu-id="939d2-264">**Action**</span></span>
- <span data-ttu-id="939d2-265">**메시지 수**</span><span class="sxs-lookup"><span data-stu-id="939d2-265">**Message count**</span></span>

<span data-ttu-id="939d2-266">보고서 보기로 돌아가려면 **보고서 보기** 를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="939d2-266">To go back to the report view, click **View report**.</span></span>

## <a name="threat-protection-status-report"></a><span data-ttu-id="939d2-267">위협 방지 상태 보고서</span><span class="sxs-lookup"><span data-stu-id="939d2-267">Threat protection status report</span></span>

<span data-ttu-id="939d2-268">**위협 방지 상태** 보고서는 EOP 및 Microsoft Defender for Office 365에서 모두 사용할 수 있습니다. 그러나 보고서에는 다양 한 데이터가 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="939d2-268">The **Threat protection status** report is available in both EOP and Microsoft Defender for Office 365; however, the reports contain different data.</span></span> <span data-ttu-id="939d2-269">예를 들어 EOP 고객은 전자 메일로 검색 된 맬웨어에 대 한 정보를 볼 수 있지만, [SharePoint, OneDrive 또는 Microsoft 팀에서 ATP가 검색 한 악성 파일](atp-for-spo-odb-and-teams.md)에 대 한 정보가 표시 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="939d2-269">For example, EOP customers can view information about malware detected in email, but not information about [malicious files detected by ATP for SharePoint, OneDrive, or Microsoft Teams](atp-for-spo-odb-and-teams.md).</span></span>

<span data-ttu-id="939d2-270">[이](zero-hour-auto-purge.md)보고서는 맬웨어 방지 엔진에 의해 차단 된 파일 또는 웹 사이트 주소 (url), [안전한 링크](atp-safe-links.md), [안전한 첨부 파일](atp-safe-attachments.md), [피싱 방지](set-up-anti-phishing-policies.md)등의 Office 365 기능에 대 한 악성 콘텐츠가 포함 된 전자 메일 메시지의 수를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="939d2-270">The report provides the count of email messages with malicious content, such as files or website addresses (URLs) that were blocked by the anti-malware engine, [zero-hour auto purge (ZAP)](zero-hour-auto-purge.md), and Defender for Office 365 features like [Safe Links](atp-safe-links.md), [Safe Attachments](atp-safe-attachments.md), and [Anti-phishing](set-up-anti-phishing-policies.md).</span></span> <span data-ttu-id="939d2-271">이 정보를 사용 하 여 경향을 식별 하거나 조직 정책 조정이 필요한 지 여부를 결정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="939d2-271">You can use this information to identify trends or determine whether organization policies need adjustment.</span></span> <span data-ttu-id="939d2-272">메시지가 5 명의 받는 사람에 게 전송 되는 경우 메시지가 한 명의 메시지와 다르게 계산 된다는 것을 이해 하는 것이 중요 합니다.</span><span class="sxs-lookup"><span data-stu-id="939d2-272">It's important to understand that if a message is sent to five recipients we count it as five different messages and not one message.</span></span>

<span data-ttu-id="939d2-273">보고서를 보려면 [보안 & 준수 센터](https://protection.office.com)를 열고 **보고서** \> **대시보드로** 이동한 다음 **위협 방지 상태** 를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="939d2-273">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Threat protection status**.</span></span> <span data-ttu-id="939d2-274">보고서로 직접 이동 하려면 다음 Url 중 하나를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="939d2-274">To go directly to the report, open one of the following URLs:</span></span>

- <span data-ttu-id="939d2-275">Office 용 Microsoft Defender 365: <https://protection.office.com/reportv2?id=TPSAggregateReportATP></span><span class="sxs-lookup"><span data-stu-id="939d2-275">Microsoft Defender for Office 365: <https://protection.office.com/reportv2?id=TPSAggregateReportATP></span></span>
- <span data-ttu-id="939d2-276">EOP <https://protection.office.com/reportv2?id=TPSAggregateReport></span><span class="sxs-lookup"><span data-stu-id="939d2-276">EOP: <https://protection.office.com/reportv2?id=TPSAggregateReport></span></span>

![보고서 대시보드의 위협 보호 상태 위젯](../../media/threat-protection-status-report-widget.png)

<span data-ttu-id="939d2-278">기본적으로이 차트에는 최근 7 일간의 데이터가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="939d2-278">By default, the chart shows data for the past 7 days.</span></span> <span data-ttu-id="939d2-279">**필터** 를 클릭 하면 90 일 날짜 범위 (평가판 구독을 30 일로 제한할 수 있음)를 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="939d2-279">If you click **Filters** , you can select a 90 day date range (trial subscriptions might be limited to 30 days).</span></span> <span data-ttu-id="939d2-280">세부 정보 테이블 보기에서는 30 일간 필터링을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="939d2-280">The details table view allows filtering for 30 days.</span></span>

### <a name="report-view-for-the-threat-protection-status-report"></a><span data-ttu-id="939d2-281">위협 보호 상태 보고서에 대 한 보고서 보기</span><span class="sxs-lookup"><span data-stu-id="939d2-281">Report view for the Threat protection status report</span></span>

<span data-ttu-id="939d2-282">다음 보기를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="939d2-282">The following views are available:</span></span>

- <span data-ttu-id="939d2-283">**데이터 보기 기준: 개요** : 다음 검색 정보가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="939d2-283">**View data by: Overview** : The following detection information is shown:</span></span>

  - <span data-ttu-id="939d2-284">**전자 메일 맬웨어**</span><span class="sxs-lookup"><span data-stu-id="939d2-284">**Email malware**</span></span>
  - <span data-ttu-id="939d2-285">**전자 메일 피싱**</span><span class="sxs-lookup"><span data-stu-id="939d2-285">**Email phish**</span></span>
  - <span data-ttu-id="939d2-286">**콘텐츠 맬웨어**</span><span class="sxs-lookup"><span data-stu-id="939d2-286">**Content malware**</span></span>

  ![위협 보호 상태 보고서의 개요 보기](../../media/threat-protection-status-report-overview-view.png)

- <span data-ttu-id="939d2-288">**데이터 보기 기준: 콘텐츠 \> 맬웨어**<sup>1</sup>: Office 365 조 직 용 Microsoft Defender에 대 한 다음 정보가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="939d2-288">**View data by: Content \> Malware**<sup>1</sup>: The following information is shown for Microsoft Defender for Office 365 organizations:</span></span>

  - <span data-ttu-id="939d2-289">**맬웨어 방지 엔진** : 맬웨어 방지를 통해 Sharepoint Online, OneDrive 및 팀의 악성 파일을 포착 합니다.</span><span class="sxs-lookup"><span data-stu-id="939d2-289">**Anti-malware engine** : Catches of malicious files in Sharepoint Online, OneDrive, and Teams by anti-malware.</span></span>
  - <span data-ttu-id="939d2-290">**파일 샌드 박싱** : 안전한 첨부 파일을 통해 Sharepoint Online, OneDrive 및 팀의 악의적인 파일을 샌드 박싱 합니다.</span><span class="sxs-lookup"><span data-stu-id="939d2-290">**File detonation** : Detonation of malicious files in Sharepoint Online, OneDrive, and Teams by Safe Attachments.</span></span>

  ![위협 방지 상태 보고서의 콘텐츠 맬웨어 보기](../../media/threat-protection-status-report-content-malware-view.png)

- <span data-ttu-id="939d2-292">**데이터 보기 기준: 메시지 재정의** : 다음과 같은 재정의 이유 정보가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="939d2-292">**View data by: Message Override** : The following override reason information is shown:</span></span>

  - <span data-ttu-id="939d2-293">**온-프레미스 건너뛰기**</span><span class="sxs-lookup"><span data-stu-id="939d2-293">**On-premises skip**</span></span>
  - <span data-ttu-id="939d2-294">**IP 허용**</span><span class="sxs-lookup"><span data-stu-id="939d2-294">**IP Allow**</span></span>
  - <span data-ttu-id="939d2-295">**메일 흐름 규칙**</span><span class="sxs-lookup"><span data-stu-id="939d2-295">**Mail flow rule**</span></span>
  - <span data-ttu-id="939d2-296">**보낸 사람 허용**</span><span class="sxs-lookup"><span data-stu-id="939d2-296">**Sender allow**</span></span>
  - <span data-ttu-id="939d2-297">**도메인 허용**</span><span class="sxs-lookup"><span data-stu-id="939d2-297">**Domain allow**</span></span>
  - <span data-ttu-id="939d2-298">**ZAP을 사용할 수 없음**</span><span class="sxs-lookup"><span data-stu-id="939d2-298">**ZAP not enabled**</span></span>
  - <span data-ttu-id="939d2-299">**정크 메일 폴더 사용 안 함**</span><span class="sxs-lookup"><span data-stu-id="939d2-299">**Junk Mail folder not enabled**</span></span>
  - <span data-ttu-id="939d2-300">**사용자가 안전한 보낸 사람**</span><span class="sxs-lookup"><span data-stu-id="939d2-300">**User Safe Sender**</span></span>
  - <span data-ttu-id="939d2-301">**사용자 안전 도메인**</span><span class="sxs-lookup"><span data-stu-id="939d2-301">**User Safe Domain**</span></span>

  ![위협 방지 상태 보고서의 메시지 재정의 보기](../../media/threat-protection-status-report-message-override-view.png)

- <span data-ttu-id="939d2-303">**아래로 나누기: 기술** 및 **데이터 보기 기준: 전자 메일 \> 피싱** : 다음 정보가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="939d2-303">**Break down by: Detection technology** and **View data by: Email \> Phish** : The following information is shown:</span></span>

  - <span data-ttu-id="939d2-304">**ATP 생성 URL 신뢰도**<sup>1</sup>: defender for office 365 detonations (다른 defender for office 365 고객)에서 생성 된 악의적 URL 신뢰도입니다.</span><span class="sxs-lookup"><span data-stu-id="939d2-304">**ATP-generated URL reputation**<sup>1</sup>: Malicious URL reputation generated from Defender for Office 365 detonations in other Defender for Office 365 customers.</span></span>
  - <span data-ttu-id="939d2-305">**Advanced 피싱 filter** : 시스템 학습을 기반으로 하는 피싱 신호입니다.</span><span class="sxs-lookup"><span data-stu-id="939d2-305">**Advanced phish filter** : Phishing signals based on machine learning.</span></span>
  - <span data-ttu-id="939d2-306">**스푸핑 방지-DMARC 오류** : 메시지에서 DMARC 인증 오류가 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="939d2-306">**Anti-spoof - DMARC failure** : DMARC authentication failure on messages.</span></span>
  - <span data-ttu-id="939d2-307">**스푸핑 방지-조직 내** : 보낸 사람이 받는 사람 도메인을 스푸핑 하려고 합니다.</span><span class="sxs-lookup"><span data-stu-id="939d2-307">**Anti-spoof - intra-org** : Sender is trying to spoof the recipient domain.</span></span>
  - <span data-ttu-id="939d2-308">**스푸핑 방지-외부 도메인** : 보낸 사람이 다른 도메인을 위장 하려고 합니다.</span><span class="sxs-lookup"><span data-stu-id="939d2-308">**Anti-spoof - external domain** : Sender is trying to spoof some other domain.</span></span>
  - <span data-ttu-id="939d2-309">**브랜드 가장** : 보낸 사람을 기반으로 하는 잘 알려진 브랜드의 가장입니다.</span><span class="sxs-lookup"><span data-stu-id="939d2-309">**Brand impersonation** : Impersonation of well-known brands based on senders.</span></span>
  - <span data-ttu-id="939d2-310">**도메인 가장**<sup>1</sup>: 고객이 소유 하거나 정의한 도메인의 가장입니다.</span><span class="sxs-lookup"><span data-stu-id="939d2-310">**Domain impersonation**<sup>1</sup>: Impersonation of domains that the customer owns or defines.</span></span>
  - <span data-ttu-id="939d2-311">**EOP URL 신뢰도** : 악의적인 url 신뢰도</span><span class="sxs-lookup"><span data-stu-id="939d2-311">**EOP URL reputation** : Malicious URL reputation.</span></span>
  - <span data-ttu-id="939d2-312">**General 피싱 filter** : 분석가 규칙을 기반으로 하는 피싱 신호입니다.</span><span class="sxs-lookup"><span data-stu-id="939d2-312">**General phish filter** : Phishing signals based on analyst rules.</span></span> 
  - <span data-ttu-id="939d2-313">**상대**</span><span class="sxs-lookup"><span data-stu-id="939d2-313">**Others**</span></span>
  - <span data-ttu-id="939d2-314">**피싱 ZAP**<sup>2</sup>: 제로 시간 피싱 메시지를 자동으로 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="939d2-314">**Phish ZAP**<sup>2</sup>: Zero hour auto purge phishing messages.</span></span>
  - <span data-ttu-id="939d2-315">**URL 샌드 박싱**<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="939d2-315">**URL detonation**<sup>1</sup></span></span>
  - <span data-ttu-id="939d2-316">**사용자 가장**<sup>1</sup>: 관리자가 정의 하거나 사서함 인텔리전스를 통해 배운 사용자의 가장입니다.</span><span class="sxs-lookup"><span data-stu-id="939d2-316">**User impersonation**<sup>1</sup>: Impersonation of users defined by admin or learned through mailbox intelligence.</span></span>

  ![위협 방지 상태 보고서의 피싱 전자 메일에 대 한 검색 기술 보기](../../media/threat-protection-status-report-phishing-detection-tech-view.png)

- <span data-ttu-id="939d2-318">**아래로 나누기: 기술** 및 **데이터 보기 By: 전자 메일 \> 맬웨어** : 다음 정보가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="939d2-318">**Break down by: Detection technology** and **View data by: Email \> Malware** : The following information is shown:</span></span>

  - <span data-ttu-id="939d2-319">**ATP 생성 파일 신뢰도**<sup>1</sup>: Defender에서 Office 365 detonations에 대해 생성 하는 모든 악의적 파일 신뢰도입니다.</span><span class="sxs-lookup"><span data-stu-id="939d2-319">**ATP-generated file reputation**<sup>1</sup>: All malicious file reputation generated by Defender for Office 365 detonations.</span></span>
  - <span data-ttu-id="939d2-320">**맬웨어 방지 엔진**<sup>1</sup>: 맬웨어 방지 엔진에서 검색 합니다.</span><span class="sxs-lookup"><span data-stu-id="939d2-320">**Anti-malware engine**<sup>1</sup>: Detection from anti-malware engines.</span></span>
  - <span data-ttu-id="939d2-321">**맬웨어 방지 정책 파일 형식 블록** : 메시지에서 식별 된 악의적인 파일의 유형으로 인해 필터링 된 전자 메일 메시지입니다.</span><span class="sxs-lookup"><span data-stu-id="939d2-321">**Anti-malware policy file type block** : These are email messages filtered out due to the type of malicious file identified in the message.</span></span>
  - <span data-ttu-id="939d2-322">**File 샌드 박싱**<sup>1</sup>: 샌드 박싱 파일은 안전한 첨부 파일로 catch 합니다.</span><span class="sxs-lookup"><span data-stu-id="939d2-322">**File detonation**<sup>1</sup>: File detonation catches by Safe Attachments.</span></span>  
  - <span data-ttu-id="939d2-323">**악의적인 파일 신뢰도**</span><span class="sxs-lookup"><span data-stu-id="939d2-323">**Malicious file reputation**</span></span>
  - <span data-ttu-id="939d2-324">**맬웨어 ZAP**<sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="939d2-324">**Malware ZAP**<sup>2</sup></span></span>
  - <span data-ttu-id="939d2-325">**상대**</span><span class="sxs-lookup"><span data-stu-id="939d2-325">**Others**</span></span>

  ![위협 방지 상태 보고서의 맬웨어 검색 기술 보기](../../media/threat-protection-status-report-malware-detection-tech-view.png)

- <span data-ttu-id="939d2-327">**아래로 나누기: 정책 유형** 및 **보기 데이터를 다음으로 표시: 전자 메일 \> 피싱** 또는 **데이터 보기: 전자 메일 \> 맬웨어** : 다음 정보가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="939d2-327">**Break down by: Policy type** and **View data by: Email \> Phish** or **View data by: Email \> Malware** : The following information is shown:</span></span>

  - <span data-ttu-id="939d2-328">**맬웨어 방지**</span><span class="sxs-lookup"><span data-stu-id="939d2-328">**Anti-malware**</span></span>
  - <span data-ttu-id="939d2-329">**안전한 첨부 파일**<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="939d2-329">**Safe Attachment**<sup>1</sup></span></span>
  - <span data-ttu-id="939d2-330">**피싱**</span><span class="sxs-lookup"><span data-stu-id="939d2-330">**Anti-phish**</span></span>
  - <span data-ttu-id="939d2-331">**스팸 방지**</span><span class="sxs-lookup"><span data-stu-id="939d2-331">**Anti-spam**</span></span>
  - <span data-ttu-id="939d2-332">**메일 흐름 규칙** (전송 규칙이 라고도 함)</span><span class="sxs-lookup"><span data-stu-id="939d2-332">**Mail flow rule** (also known as a transport rule)</span></span>
  - <span data-ttu-id="939d2-333">**상대**</span><span class="sxs-lookup"><span data-stu-id="939d2-333">**Others**</span></span>

  ![위협 보호 상태 보고서의 피싱 전자 메일에 대 한 정책 유형 보기입니다.](../../media/threat-protection-status-report-phishing-policy-type-view.png)

- <span data-ttu-id="939d2-335">**아래로 나누기: 배달 상태** 및 **데이터 보기 기준: 전자 메일 \> 피싱** 또는 **데이터 보기: 전자 메일 \> 맬웨어** : 다음 정보가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="939d2-335">**Break down by: Delivery status** and **View data by: Email \> Phish** or **View data by: Email \> Malware** : The following information is shown:</span></span>

  - <span data-ttu-id="939d2-336">**배달 실패**</span><span class="sxs-lookup"><span data-stu-id="939d2-336">**Delivery failed**</span></span>
  - <span data-ttu-id="939d2-337">**끊김**</span><span class="sxs-lookup"><span data-stu-id="939d2-337">**Dropped**</span></span>
  - <span data-ttu-id="939d2-338">**받습니다**</span><span class="sxs-lookup"><span data-stu-id="939d2-338">**Forwarded**</span></span>
  - <span data-ttu-id="939d2-339">**호스팅된 사서함: 사용자 지정 폴더**</span><span class="sxs-lookup"><span data-stu-id="939d2-339">**Hosted mailbox: Custom folder**</span></span>
  - <span data-ttu-id="939d2-340">**호스팅된 사서함: 삭제 된 항목**</span><span class="sxs-lookup"><span data-stu-id="939d2-340">**Hosted mailbox: Deleted items**</span></span>
  - <span data-ttu-id="939d2-341">**호스팅된 사서함: 받은 편지함**</span><span class="sxs-lookup"><span data-stu-id="939d2-341">**Hosted mailbox: Inbox**</span></span>
  - <span data-ttu-id="939d2-342">**호스팅된 사서함: 정크**</span><span class="sxs-lookup"><span data-stu-id="939d2-342">**Hosted mailbox: Junk**</span></span>
  - <span data-ttu-id="939d2-343">**온-프레미스 서버: 배달 됨**</span><span class="sxs-lookup"><span data-stu-id="939d2-343">**On-premises server: Delivered**</span></span>
  - <span data-ttu-id="939d2-344">**격리**</span><span class="sxs-lookup"><span data-stu-id="939d2-344">**Quarantine**</span></span>

  ![위협 보호 상태 보고서의 피싱 전자 메일에 대 한 배달 상태 보기](../../media/threat-protection-status-report-phishing-delivery-status-view.png)

<span data-ttu-id="939d2-346"><sup>1</sup> Defender for Office 365 전용</span><span class="sxs-lookup"><span data-stu-id="939d2-346"><sup>1</sup> Defender for Office 365 only</span></span>

<span data-ttu-id="939d2-347"><sup>2</sup> 개 시간 자동 제거 (ZAP)는 독립 실행형 EOP에서 사용할 수 없습니다 (Exchange Online 사서함 에서만 작동 함).</span><span class="sxs-lookup"><span data-stu-id="939d2-347"><sup>2</sup> Zero-hour auto purge (ZAP) isn't available in standalone EOP (it only works in Exchange Online mailboxes).</span></span>

<span data-ttu-id="939d2-348">**필터** 를 클릭 하는 경우 사용 가능한 필터는 보고 있는 차트에 따라 달라 집니다.</span><span class="sxs-lookup"><span data-stu-id="939d2-348">If you click **Filters** , the filters available depends on the chart you were looking at:</span></span>

<span data-ttu-id="939d2-349">**콘텐츠 \> 맬웨어** 는 **시작 날짜** 및 **종료 날짜** 및 **검색** 값을 기준으로 보고서를 수정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="939d2-349">For **Content \> Malware** , you can modify the report by **Start date** and **End date** , and the **Detection** value.</span></span>

<span data-ttu-id="939d2-350">**메시지 재정의** 에 대해 다음 필터를 사용 하 여 보고서를 수정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="939d2-350">For **Message Override** , you can modify the report with the following filters:</span></span>

- <span data-ttu-id="939d2-351">**시작 날짜** 및 **끝 날짜**</span><span class="sxs-lookup"><span data-stu-id="939d2-351">**Start date** and **End date**</span></span>
- <span data-ttu-id="939d2-352">**재정의 이유**</span><span class="sxs-lookup"><span data-stu-id="939d2-352">**Override Reason**</span></span>
- <span data-ttu-id="939d2-353">**Tag** : 태그를 기준으로 필터링 하 여 특정 태그가 적용 된 사용자 또는 그룹을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="939d2-353">**Tag** : filter by tag to return users or groups that have had a specific tag applied.</span></span> <span data-ttu-id="939d2-354">사용자 태그에 대 한 자세한 내용은 [user tags](user-tags.md)를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="939d2-354">For more information about user tags, see [User tags](user-tags.md).</span></span>
- <span data-ttu-id="939d2-355">**도메인**</span><span class="sxs-lookup"><span data-stu-id="939d2-355">**Domain**</span></span>

<span data-ttu-id="939d2-356">다른 모든 보기에 대해 다음 필터를 사용 하 여 보고서를 수정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="939d2-356">For all other views, you can modify the report with the following filters:</span></span>

- <span data-ttu-id="939d2-357">**시작 날짜** 및 **끝 날짜**</span><span class="sxs-lookup"><span data-stu-id="939d2-357">**Start date** and **End date**</span></span>
- <span data-ttu-id="939d2-358">**감지**</span><span class="sxs-lookup"><span data-stu-id="939d2-358">**Detection**</span></span>
- <span data-ttu-id="939d2-359">**Protected by** : **ATP** 또는 **EOP**</span><span class="sxs-lookup"><span data-stu-id="939d2-359">**Protected by** : **ATP** or **EOP**</span></span>
- <span data-ttu-id="939d2-360">**Tag** : 태그를 기준으로 필터링 하 여 특정 태그가 적용 된 사용자 또는 그룹을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="939d2-360">**Tag** : filter by tag to return users or groups that have had a specific tag applied.</span></span> <span data-ttu-id="939d2-361">사용자 태그에 대 한 자세한 내용은 [user tags](user-tags.md)를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="939d2-361">For more information about user tags, see [User tags](user-tags.md).</span></span>
- <span data-ttu-id="939d2-362">**도메인**</span><span class="sxs-lookup"><span data-stu-id="939d2-362">**Domain**</span></span>

### <a name="details-table-view-for-the-threat-protection-status-report"></a><span data-ttu-id="939d2-363">위협 보호 상태 보고서에 대 한 세부 정보 테이블 보기</span><span class="sxs-lookup"><span data-stu-id="939d2-363">Details table view for the Threat protection status report</span></span>

<span data-ttu-id="939d2-364">**세부 정보 표 보기** 를 클릭 하면 표시 되는 정보는 보고 있는 차트에 따라 달라 집니다.</span><span class="sxs-lookup"><span data-stu-id="939d2-364">If you click **View details table** , the information that's shown depends on the chart you were looking at:</span></span>

- <span data-ttu-id="939d2-365">**데이터 보기 기준: 콘텐츠 \> 맬웨어** :</span><span class="sxs-lookup"><span data-stu-id="939d2-365">**View data by: Content \> Malware** :</span></span>

  - <span data-ttu-id="939d2-366">**날짜**</span><span class="sxs-lookup"><span data-stu-id="939d2-366">**Date**</span></span>
  - <span data-ttu-id="939d2-367">**위치**</span><span class="sxs-lookup"><span data-stu-id="939d2-367">**Location**</span></span>
  - <span data-ttu-id="939d2-368">**보낸 사람**</span><span class="sxs-lookup"><span data-stu-id="939d2-368">**Directed by**</span></span>
  - <span data-ttu-id="939d2-369">**맬웨어 이름**</span><span class="sxs-lookup"><span data-stu-id="939d2-369">**Malware name**</span></span>

<span data-ttu-id="939d2-370">이 보기에서 **필터** 를 클릭 하면 **시작 날짜** 및 **끝 날짜** 및 **검색** 값을 기준으로 보고서를 수정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="939d2-370">If you click **Filters** in this view, you can modify the report by **Start date** and **End date** , and the **Detection** value.</span></span>

- <span data-ttu-id="939d2-371">**데이터 보기 기준: 메시지 재정의** :</span><span class="sxs-lookup"><span data-stu-id="939d2-371">**View data by: Message Override** :</span></span>

  - <span data-ttu-id="939d2-372">**날짜**</span><span class="sxs-lookup"><span data-stu-id="939d2-372">**Date**</span></span>
  - <span data-ttu-id="939d2-373">**제목**</span><span class="sxs-lookup"><span data-stu-id="939d2-373">**Subject**</span></span>
  - <span data-ttu-id="939d2-374">**보낸 사람**</span><span class="sxs-lookup"><span data-stu-id="939d2-374">**Sender**</span></span>
  - <span data-ttu-id="939d2-375">**받는 사람**</span><span class="sxs-lookup"><span data-stu-id="939d2-375">**Recipients**</span></span>
  - <span data-ttu-id="939d2-376">**검색 기준**</span><span class="sxs-lookup"><span data-stu-id="939d2-376">**Detected by**</span></span>
  - <span data-ttu-id="939d2-377">**재정의 이유**</span><span class="sxs-lookup"><span data-stu-id="939d2-377">**Override Reason**</span></span>
  - <span data-ttu-id="939d2-378">**손상 원본**</span><span class="sxs-lookup"><span data-stu-id="939d2-378">**Source of Compromise**</span></span>
  - <span data-ttu-id="939d2-379">**태그**</span><span class="sxs-lookup"><span data-stu-id="939d2-379">**Tags**</span></span>

<span data-ttu-id="939d2-380">이 보기에서 **필터** 를 클릭 하면 다음 필터를 사용 하 여 보고서를 수정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="939d2-380">If you click **Filters** in this view, you can modify the report with the following filters:</span></span>

- <span data-ttu-id="939d2-381">**시작 날짜** 및 **끝 날짜**</span><span class="sxs-lookup"><span data-stu-id="939d2-381">**Start date** and **End date**</span></span>
- <span data-ttu-id="939d2-382">**재정의 이유**</span><span class="sxs-lookup"><span data-stu-id="939d2-382">**Override Reason**</span></span>
- <span data-ttu-id="939d2-383">**Tag** : 태그를 기준으로 필터링 하 여 특정 태그가 적용 된 사용자 또는 그룹을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="939d2-383">**Tag** : filter by tag to return users or groups that have had a specific tag applied.</span></span> <span data-ttu-id="939d2-384">사용자 태그에 대 한 자세한 내용은 [user tags](user-tags.md)를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="939d2-384">For more information about user tags, see [User tags](user-tags.md).</span></span>
- <span data-ttu-id="939d2-385">**도메인**</span><span class="sxs-lookup"><span data-stu-id="939d2-385">**Domain**</span></span>
- <span data-ttu-id="939d2-386">**받는 사람** (이 필터링 가능한 속성은 세부 정보 테이블 보기 에서만 사용 가능)</span><span class="sxs-lookup"><span data-stu-id="939d2-386">**Recipients** (Note that this filterable property is only available in the details table view)</span></span>

<span data-ttu-id="939d2-387">**데이터 보기 기준: 개요** : **뷰 정보 테이블** 단추를 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="939d2-387">**View data by: Overview** : No **View details table** button is available.</span></span>

- <span data-ttu-id="939d2-388">기타 모든 차트:</span><span class="sxs-lookup"><span data-stu-id="939d2-388">All other charts:</span></span>

  - <span data-ttu-id="939d2-389">**날짜**</span><span class="sxs-lookup"><span data-stu-id="939d2-389">**Date**</span></span>
  - <span data-ttu-id="939d2-390">**제목**</span><span class="sxs-lookup"><span data-stu-id="939d2-390">**Subject**</span></span>
  - <span data-ttu-id="939d2-391">**보낸 사람**</span><span class="sxs-lookup"><span data-stu-id="939d2-391">**Sender**</span></span>
  - <span data-ttu-id="939d2-392">**받는 사람**</span><span class="sxs-lookup"><span data-stu-id="939d2-392">**Recipients**</span></span>
  - <span data-ttu-id="939d2-393">**검색 기준**</span><span class="sxs-lookup"><span data-stu-id="939d2-393">**Detected by**</span></span>
  - <span data-ttu-id="939d2-394">**배달 상태**</span><span class="sxs-lookup"><span data-stu-id="939d2-394">**Delivery Status**</span></span>
  - <span data-ttu-id="939d2-395">**손상 원본**</span><span class="sxs-lookup"><span data-stu-id="939d2-395">**Source of Compromise**</span></span>
  - <span data-ttu-id="939d2-396">**태그**</span><span class="sxs-lookup"><span data-stu-id="939d2-396">**Tags**</span></span>

<span data-ttu-id="939d2-397">**필터** 를 클릭 하면 다음 필터를 사용 하 여 보고서를 수정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="939d2-397">If you click **Filters** , you can modify the report with the following filters:</span></span>

- <span data-ttu-id="939d2-398">**시작 날짜** 및 **끝 날짜**</span><span class="sxs-lookup"><span data-stu-id="939d2-398">**Start date** and **End date**</span></span>
- <span data-ttu-id="939d2-399">**감지**</span><span class="sxs-lookup"><span data-stu-id="939d2-399">**Detection**</span></span>
- <span data-ttu-id="939d2-400">**보호** : Office 365 또는 **EOP** **용 Defender**</span><span class="sxs-lookup"><span data-stu-id="939d2-400">**Protected by** : **Defender for Office 365** or **EOP**</span></span>
- <span data-ttu-id="939d2-401">**Tag** : 태그를 기준으로 필터링 하 여 특정 태그가 적용 된 사용자 또는 그룹을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="939d2-401">**Tag** : filter by tag to return users or groups that have had a specific tag applied.</span></span> <span data-ttu-id="939d2-402">사용자 태그에 대 한 자세한 내용은 [user tags](user-tags.md)를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="939d2-402">For more information about user tags, see [User tags](user-tags.md).</span></span>
- <span data-ttu-id="939d2-403">**도메인**</span><span class="sxs-lookup"><span data-stu-id="939d2-403">**Domain**</span></span>
- <span data-ttu-id="939d2-404">**받는 사람** (이 필터링 가능한 속성은 세부 정보 테이블 보기 에서만 사용 가능)</span><span class="sxs-lookup"><span data-stu-id="939d2-404">**Recipients** (Note that this filterable property is only available in the details table view)</span></span>

## <a name="top-malware-report"></a><span data-ttu-id="939d2-405">주요 맬웨어 보고서</span><span class="sxs-lookup"><span data-stu-id="939d2-405">Top malware report</span></span>

<span data-ttu-id="939d2-406">**주요 맬웨어** 보고서에는 [EOP의 맬웨어 방지 보호](anti-malware-protection.md)기능에서 검색 된 다양 한 유형의 맬웨어가 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="939d2-406">The **Top malware** report shows the various kinds of malware that was detected by [anti-malware protection in EOP](anti-malware-protection.md).</span></span>

<span data-ttu-id="939d2-407">보고서를 보려면 [보안 & 준수 센터](https://protection.office.com)를 열고 **보고서** \> **대시보드로** 이동한 후에 **상위 맬웨어** 를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="939d2-407">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Top malware**.</span></span> <span data-ttu-id="939d2-408">보고서로 직접 이동 하려면를 엽니다 <https://protection.office.com/reportv2?id=TopMalware> .</span><span class="sxs-lookup"><span data-stu-id="939d2-408">To go directly to the report, open <https://protection.office.com/reportv2?id=TopMalware>.</span></span>

![보고서 대시보드의 최상위 맬웨어 위젯](../../media/top-malware-report-widget.png)

<span data-ttu-id="939d2-410">원형 차트의 쐐기형 위에 마우스를 가져가면 맬웨어 종류와 해당 맬웨어가 있는 것으로 검색 된 메시지의 수를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="939d2-410">When you hover over a wedge in the pie chart, you can see the name of a kind of malware and how many messages were detected as having that malware.</span></span>

![주요 맬웨어 보고서 보기](../../media/top-malware-report-view.png)

<span data-ttu-id="939d2-412">**세부 정보 테이블 보기** 를 클릭 하면 다음 세부 정보를 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="939d2-412">If you click **View details table** , you can see the following details:</span></span>

- <span data-ttu-id="939d2-413">**주요 맬웨어**</span><span class="sxs-lookup"><span data-stu-id="939d2-413">**Top malware**</span></span>
- <span data-ttu-id="939d2-414">**개수**</span><span class="sxs-lookup"><span data-stu-id="939d2-414">**Count**</span></span>

<span data-ttu-id="939d2-415">보고서 보기 또는 세부 정보 테이블 보기에서 **필터** 를 클릭 하면 **시작 날짜** 및 **종료 날짜** 와 함께 날짜 범위를 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="939d2-415">If you click **Filters** in the report view or details table view, you can specify a date range with **Start date** and **End date**.</span></span>

## <a name="url-threat-protection-report"></a><span data-ttu-id="939d2-416">URL 위협 방지 보고서</span><span class="sxs-lookup"><span data-stu-id="939d2-416">URL threat protection report</span></span>

<span data-ttu-id="939d2-417">**URL 위협 방지 보고서** 는 Microsoft Defender for Office 365에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="939d2-417">The **URL threat protection report** is available in Microsoft Defender for Office 365.</span></span> <span data-ttu-id="939d2-418">자세한 내용은 [URL threat protection report](view-reports-for-atp.md#url-threat-protection-report)를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="939d2-418">For more information, see [URL threat protection report](view-reports-for-atp.md#url-threat-protection-report).</span></span>

## <a name="user-reported-messages-report"></a><span data-ttu-id="939d2-419">사용자가 보고 한 메시지 보고서</span><span class="sxs-lookup"><span data-stu-id="939d2-419">User-reported messages report</span></span>

<span data-ttu-id="939d2-420">**사용자가 보고 한 메시지** 보고서에는 사용자가 [보고서 메시지 추가 기능](https://docs.microsoft.com/microsoft-365/security/office-365-security/enable-the-report-message-add-in)을 사용 하 여 정크 메일, 피싱 시도 또는 좋은 메일로 보고 한 전자 메일 메시지에 대 한 정보가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="939d2-420">The **User-reported messages** report shows information about email messages that users have reported as junk, phishing attempts, or good mail by using the [Report Message add-in](https://docs.microsoft.com/microsoft-365/security/office-365-security/enable-the-report-message-add-in).</span></span>

<span data-ttu-id="939d2-421">각 메시지에 대 한 자세한 내용은 스팸 정책 예외 또는 조직에 대해 구성 된 메일 흐름 규칙과 같은 배달 이유를 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="939d2-421">Details are available for each message, including the delivery reason, such a spam policy exception or mail flow rule configured for your organization.</span></span> <span data-ttu-id="939d2-422">세부 정보를 보려면 사용자-보고서 목록에서 항목을 선택한 다음 **요약** 및 **세부 정보** 탭에서 해당 정보를 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="939d2-422">To view details, select an item in the user-reports list, and then view the information on the **Summary** and **Details** tabs.</span></span>

![User-Reported 메시지 보고서에는 사용자가 정크로 레이블이 지정 된 메시지, 정크 메일, 피싱 시도 등이 표시 됩니다.](../../media/ad5e9a3d-b833-419c-bcc9-3425d9604ead.png)

<span data-ttu-id="939d2-424">이 보고서를 보려면 [보안 & 준수 센터](https://protection.office.com)에서 다음 중 하나를 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="939d2-424">To view this report, in the [Security & Compliance Center](https://protection.office.com), do one of the following:</span></span>

- <span data-ttu-id="939d2-425">**위협 관리** \> **대시보드** \> **사용자가 보고 한 메시지로** 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="939d2-425">Go to **Threat management** \> **Dashboard** \> **User-reported messages**.</span></span>

- <span data-ttu-id="939d2-426">**위협 관리** 로 이동 하 여 \> **Review** \> **사용자가 보고 한 메시지** 를 검토 합니다.</span><span class="sxs-lookup"><span data-stu-id="939d2-426">Go to **Threat management** \> **Review** \> **User-reported messages**.</span></span>

![보안 & 준수 센터에서 위협 관리 \> 검토 \> 사용자가 보고 한 메시지를 선택 합니다.](../../media/e372c57c-1414-4616-957b-bc933b8c8711.png)

> [!IMPORTANT]
> <span data-ttu-id="939d2-428">사용자가 보고 한 메시지 보고서가 제대로 작동 하도록 하려면 Office 365 환경에 대해 **감사 로깅을 켜야 합니다** .</span><span class="sxs-lookup"><span data-stu-id="939d2-428">In order for the User-reported messages report to work correctly, **audit logging must be turned on** for your Office 365 environment.</span></span> <span data-ttu-id="939d2-429">이 작업은 일반적으로 Exchange Online에서 감사 로그 역할이 할당 된 사용자가 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="939d2-429">This is typically done by someone who has the Audit Logs role assigned in Exchange Online.</span></span> <span data-ttu-id="939d2-430">자세한 내용은 [Turn Microsoft 365 감사 로그 검색 설정 또는 해제](https://docs.microsoft.com/microsoft-365/compliance/turn-audit-log-search-on-or-off)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="939d2-430">For more information, see [Turn Microsoft 365 audit log search on or off](https://docs.microsoft.com/microsoft-365/compliance/turn-audit-log-search-on-or-off).</span></span>

## <a name="what-permissions-are-needed-to-view-these-reports"></a><span data-ttu-id="939d2-431">이러한 보고서를 표시 하는 데 필요한 사용 권한은 무엇입니까?</span><span class="sxs-lookup"><span data-stu-id="939d2-431">What permissions are needed to view these reports?</span></span>

<span data-ttu-id="939d2-432">보고서를 보고 사용 하려면 보안 & 준수 센터 **및** Exchange Online에서 지정 된 역할 그룹의 구성원 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="939d2-432">To view and use the reports, you need to be a member of the specified role group in the Security & Compliance Center **and** in Exchange Online.</span></span>

- <span data-ttu-id="939d2-433">보안 & 준수 센터에서 다음 역할 그룹 중 하나의 구성원 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="939d2-433">In the Security & Compliance Center, you need to be a member of one of the following role groups:</span></span>

  <span data-ttu-id="939d2-434">-조직 관리-보안 관리자 ( [Azure Active Directory 관리 센터](https://aad.portal.azure.com) 에서이 작업을 수행할 수도 있음)-보안 독자</span><span class="sxs-lookup"><span data-stu-id="939d2-434">-Organization Management -Security Administrator (you can also do this in the [Azure Active Directory admin center](https://aad.portal.azure.com) -Security Reader</span></span>

  <span data-ttu-id="939d2-435">자세한 내용은 [보안 및 준수 센터의 사용 권한](https://docs.microsoft.com/microsoft-365/security/office-365-security/permissions-in-the-security-and-compliance-center)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="939d2-435">For more information, see [Permissions in the Security & Compliance Center](https://docs.microsoft.com/microsoft-365/security/office-365-security/permissions-in-the-security-and-compliance-center).</span></span>

- <span data-ttu-id="939d2-436">Exchange Online에서 다음 역할 그룹 중 하나의 구성원 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="939d2-436">In Exchange Online, you need to be a member of one of the following role groups:</span></span>

  <span data-ttu-id="939d2-437">-조직 관리-보기 전용 조직 관리-보기 전용 받는 사람-준수 관리</span><span class="sxs-lookup"><span data-stu-id="939d2-437">-Organization Management -View-only Organization Management -View-Only Recipients -Compliance Management</span></span>

<span data-ttu-id="939d2-438">자세한 내용은 exchange online의 [사용 권한](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo) 및 [exchange online에서 역할 그룹 관리](https://docs.microsoft.com/Exchange/permissions-exo/role-groups)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="939d2-438">For more information, see [Permissions in Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo) and [Manage role groups in Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/role-groups).</span></span>

## <a name="what-if-the-reports-arent-showing-data"></a><span data-ttu-id="939d2-439">보고서에 데이터가 표시 되지 않으면 어떻게 하나요?</span><span class="sxs-lookup"><span data-stu-id="939d2-439">What if the reports aren't showing data?</span></span>

<span data-ttu-id="939d2-440">보고서에 데이터가 표시 되지 않는 경우 정책이 올바르게 설정 되어 있는지 다시 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="939d2-440">If you are not seeing data in your reports, double-check that your policies are set up correctly.</span></span> <span data-ttu-id="939d2-441">자세한 내용은 [위협 으로부터 보호](protect-against-threats.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="939d2-441">To learn more, see [Protect against threats](protect-against-threats.md).</span></span>

## <a name="related-topics"></a><span data-ttu-id="939d2-442">관련 항목</span><span class="sxs-lookup"><span data-stu-id="939d2-442">Related topics</span></span>

[<span data-ttu-id="939d2-443">EOP의 스팸 방지 및 맬웨어 방지 보호 기능</span><span class="sxs-lookup"><span data-stu-id="939d2-443">Anti-spam and anti-malware protection in EOP</span></span>](anti-spam-and-anti-malware-protection.md)

[<span data-ttu-id="939d2-444">보안 및 준수 센터의 스마트 보고서 및 인사이트</span><span class="sxs-lookup"><span data-stu-id="939d2-444">Smart reports and insights in the Security & Compliance Center</span></span>](reports-and-insights-in-security-and-compliance.md)

[<span data-ttu-id="939d2-445">보안 & 준수 센터에서 메일 흐름 보고서 보기</span><span class="sxs-lookup"><span data-stu-id="939d2-445">View mail flow reports in the Security & Compliance Center</span></span>](view-mail-flow-reports.md)

[<span data-ttu-id="939d2-446">Office 365 용 Defender에 대 한 보고서 보기</span><span class="sxs-lookup"><span data-stu-id="939d2-446">View reports for Defender for Office 365</span></span>](view-reports-for-atp.md)
