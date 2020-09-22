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
ms.openlocfilehash: 588c30ca07684636661c7946b2418b75574c8cbd
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/22/2020
ms.locfileid: "48199220"
---
# <a name="view-email-security-reports-in-the-security--compliance-center"></a><span data-ttu-id="98c8b-104">보안 및 준수 센터의 전자 메일 보안 보고서 보기</span><span class="sxs-lookup"><span data-stu-id="98c8b-104">View email security reports in the Security & Compliance Center</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="98c8b-105">[보안 & 준수 센터](https://protection.office.com) 에서 다양 한 보고서를 사용할 수 있으며, Microsoft 365의 스팸 방지, 맬웨어 방지 및 암호화 기능과 같은 전자 메일 보안 기능이 조직을 보호 하는 방법을 확인 하는 데 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="98c8b-105">A variety of reports are available in the [Security & Compliance Center](https://protection.office.com) to help you see how email security features, such as anti-spam, anti-malware, and encryption features in Microsoft 365 are protecting your organization.</span></span> <span data-ttu-id="98c8b-106">[필요한 권한이](#what-permissions-are-needed-to-view-these-reports)있는 경우 **보고서** 대시보드로 이동 하 여 보안 & 준수 센터에서 이러한 보고서를 볼 수 있습니다 \> **Dashboard**.</span><span class="sxs-lookup"><span data-stu-id="98c8b-106">If you have the [necessary permissions](#what-permissions-are-needed-to-view-these-reports), you can view these reports in the Security & Compliance Center by going to **Reports** \> **Dashboard**.</span></span> <span data-ttu-id="98c8b-107">보고서 대시보드로 직접 이동 하려면를 엽니다 <https://protection.office.com/insightdashboard> .</span><span class="sxs-lookup"><span data-stu-id="98c8b-107">To go directly to the Reports dashboard, open <https://protection.office.com/insightdashboard>.</span></span>

![보안 & 준수 센터의 보고서 대시보드](../../media/6b213d34-adbb-44af-8549-be9a7e2db087.png)

## <a name="compromised-users-report"></a><span data-ttu-id="98c8b-109">손상 된 사용자 보고서</span><span class="sxs-lookup"><span data-stu-id="98c8b-109">Compromised users report</span></span>

> [!NOTE]
> <span data-ttu-id="98c8b-110">이 보고서는 Microsoft 365 조직에서 Exchange Online 사서함을 사용 하는 경우에 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="98c8b-110">This report is available in Microsoft 365 organizations with Exchange Online mailboxes.</span></span> <span data-ttu-id="98c8b-111">독립 실행형 EOP (Exchange Online Protection) 조직에서는이 기능을 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="98c8b-111">It's not available in standalone Exchange Online Protection (EOP) organizations.</span></span>

<span data-ttu-id="98c8b-112">**손상 된 사용자** 보고서에는 최근 7 일 이내에 **의심** 또는 **제한** 된 것으로 표시 된 사용자 계정 수가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="98c8b-112">The **Compromised users** report shows shows the number of user accounts that were marked as **Suspicious** or **Restricted** within the last 7 days.</span></span> <span data-ttu-id="98c8b-113">이러한 두 가지 상태의 계정은 문제가 있거나 심지어도 손상 됩니다.</span><span class="sxs-lookup"><span data-stu-id="98c8b-113">Accounts in either of these states are problematic or even compromised.</span></span> <span data-ttu-id="98c8b-114">자주 사용 하는 경우 보고서를 사용 하 여 의심 스러운 또는 제한 된 계정의 스파이크 및 추세를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="98c8b-114">With frequent use, you can use the report to spot spikes, and even trends, in suspicious or restricted accounts.</span></span> <span data-ttu-id="98c8b-115">사용자 손상에 대 한 자세한 내용은 [손상 된 전자 메일 계정에 응답](responding-to-a-compromised-email-account.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="98c8b-115">For more information about compromised users, see [Responding to a compromised email account](responding-to-a-compromised-email-account.md).</span></span>

![보고서 대시보드의 손상 된 사용자 위젯](../../media/compromised-users-report-widget.png)

<span data-ttu-id="98c8b-117">집계 보기는 최근 90 일 동안의 데이터를 표시 하 고, 자세히 보기에는 지난 30 일 동안의 데이터가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="98c8b-117">The aggregate view shows data for the last 90 days and the detail view shows data for the last 30 days.</span></span>

<span data-ttu-id="98c8b-118">보고서를 보려면 [보안 & 준수 센터](https://protection.office.com)를 열고 **보고서** \> **대시보드로** 이동한 다음 **손상 된 사용자**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="98c8b-118">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Compromised users**.</span></span> <span data-ttu-id="98c8b-119">보고서로 직접 이동 하려면를 엽니다 <https://protection.office.com/reportv2?id=CompromisedUsers> .</span><span class="sxs-lookup"><span data-stu-id="98c8b-119">To go directly to the report, open <https://protection.office.com/reportv2?id=CompromisedUsers>.</span></span>

<span data-ttu-id="98c8b-120">**필터** 를 클릭 하 고 다음 값 중 하나 이상을 선택 하 여 차트 및 세부 정보 테이블을 모두 필터링 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="98c8b-120">You can filter both the chart and the details table by clicking **Filters** and selecting one or more of the following values:</span></span>

- <span data-ttu-id="98c8b-121">**시작 날짜** 및 **끝 날짜**</span><span class="sxs-lookup"><span data-stu-id="98c8b-121">**Start date** and **End date**</span></span>

- <span data-ttu-id="98c8b-122">**의심 스러운**: 사용자 계정에서 의심 스러운 전자 메일을 보냈지만 전자 메일을 보낼 수 없게 되는 위험에 노출 됩니다.</span><span class="sxs-lookup"><span data-stu-id="98c8b-122">**Suspicious**: The user account has sent suspicious email and is at risk of being restricted from sending email.</span></span>

- <span data-ttu-id="98c8b-123">**제한**: 사용자 계정이 의심 스러운 높은 패턴으로 인해 전자 메일을 보내지 못하도록 제한 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="98c8b-123">**Restricted**: The user account has been restricted from sending email due to highly suspicious patterns.</span></span>

![손상 된 사용자 보고서의 보고서 보기](../../media/compromised-users-report-activity-view.png)

<span data-ttu-id="98c8b-125">**세부 정보 테이블 보기**를 클릭 하면 다음 세부 정보를 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="98c8b-125">If you click **View details table**, you can see the following details:</span></span>

- <span data-ttu-id="98c8b-126">**만든 시간**</span><span class="sxs-lookup"><span data-stu-id="98c8b-126">**Creation time**</span></span>
- <span data-ttu-id="98c8b-127">**사용자 ID**</span><span class="sxs-lookup"><span data-stu-id="98c8b-127">**User ID**</span></span>
- <span data-ttu-id="98c8b-128">**작업**</span><span class="sxs-lookup"><span data-stu-id="98c8b-128">**Action**</span></span>

<span data-ttu-id="98c8b-129">보고서 보기로 돌아가려면 **보고서 보기**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="98c8b-129">To go back to the report view, click **View report**.</span></span>

## <a name="encryption-report"></a><span data-ttu-id="98c8b-130">암호화 보고서</span><span class="sxs-lookup"><span data-stu-id="98c8b-130">Encryption report</span></span>

<span data-ttu-id="98c8b-131">**암호화 보고서** 는 EOP (exchange online의 사서함과 exchange online 사서함이 없는 독립 실행형 EOP 구독)에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="98c8b-131">The **Encryption report** is available in EOP (subscriptions with mailboxes in Exchange Online or standalone EOP without Exchange Online mailboxes).</span></span> <span data-ttu-id="98c8b-132">조직의 보안 팀은이 보고서의 정보를 사용 하 여 패턴을 식별 하 고 중요 한 전자 메일 메시지에 대 한 정책을 사전에 적용 하거나 조정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="98c8b-132">Your organization's security team can use information in this report to identify patterns and proactively apply or adjust policies for sensitive email messages.</span></span> <span data-ttu-id="98c8b-133">예제:</span><span class="sxs-lookup"><span data-stu-id="98c8b-133">For example:</span></span>

- <span data-ttu-id="98c8b-134">사용자가 암호화 한 전자 메일 메시지가 많은 경우 특정 사용 사례에 대 한 암호화를 자동화 하는 암호화 정책을 추가 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="98c8b-134">If you see a high number of email messages encrypted by users, you might want to add an encryption policy to automate encryption for certain use cases.</span></span> <span data-ttu-id="98c8b-135">자세한 내용은 [Microsoft 365에서 전자 메일 메시지를 암호화 하는 메일 흐름 규칙 정의](../../compliance/define-mail-flow-rules-to-encrypt-email.md)를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="98c8b-135">For more information, see [Define mail flow rules to encrypt email messages in Microsoft 365](../../compliance/define-mail-flow-rules-to-encrypt-email.md).</span></span>

- <span data-ttu-id="98c8b-136">사용할 수 있는 암호화 서식 파일의 수가 여러 개 있지만 아무도 사용 하지 않는 경우에는 사용자가 기능 교육을 필요로 하는지 여부를 탐색할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="98c8b-136">If you have a number of encryption templates available but no one is using them, you might explore whether users need feature training.</span></span>

<span data-ttu-id="98c8b-137">집계 보기는 최근 90 일에 대 한 필터링을 허용 하 고 세부 정보 보기는 10 일 동안 필터링을 허용 합니다.</span><span class="sxs-lookup"><span data-stu-id="98c8b-137">The aggregate view allows filtering for the last 90 days, while the detail view allows filtering for 10 days.</span></span>

<span data-ttu-id="98c8b-138">보고서를 보려면 [보안 & 준수 센터](https://protection.office.com)를 열고 **보고서** \> **대시보드로** 이동한 다음 **암호화 보고서**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="98c8b-138">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Encryption report**.</span></span> <span data-ttu-id="98c8b-139">보고서로 직접 이동 하려면를 엽니다 <https://protection.office.com/reportv2?id=EncryptionReport> .</span><span class="sxs-lookup"><span data-stu-id="98c8b-139">To go directly to the report, open <https://protection.office.com/reportv2?id=EncryptionReport>.</span></span>

<span data-ttu-id="98c8b-140">암호화에 대 한 자세한 내용은 [Microsoft 365의 전자 메일 암호화](../../compliance/email-encryption.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="98c8b-140">To learn more about encryption, see [Email encryption in Microsoft 365](../../compliance/email-encryption.md).</span></span>

### <a name="report-view-for-the-encryption-report"></a><span data-ttu-id="98c8b-141">암호화 보고서에 대 한 보고서 보기</span><span class="sxs-lookup"><span data-stu-id="98c8b-141">Report view for the Encryption report</span></span>

<span data-ttu-id="98c8b-142">차트에서 다음 필터를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="98c8b-142">You can use the following filters on the chart:</span></span>

- <span data-ttu-id="98c8b-143">**데이터 보기 기준: 메시지 암호화 보고서** 및 **아래로 나누기: 암호화 방법**: 다음과 같은 암호화 방법을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="98c8b-143">**View data by: Message Encryption Report** and **Break down by: Encryption method**: The following encryption methods are available:</span></span>

  - <span data-ttu-id="98c8b-144">**사용자별 암호화**</span><span class="sxs-lookup"><span data-stu-id="98c8b-144">**Encryption by user**</span></span>
  - <span data-ttu-id="98c8b-145">**정책에의 한 암호화**</span><span class="sxs-lookup"><span data-stu-id="98c8b-145">**Encryption by policy**</span></span>

  <span data-ttu-id="98c8b-146">**필터**를 클릭 하면 다음 필터를 사용 하 여 차트를 수정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="98c8b-146">If you click **Filters**, you can modify the chart with the following filters:</span></span>

  - <span data-ttu-id="98c8b-147">**시작 날짜** 및 **끝 날짜**</span><span class="sxs-lookup"><span data-stu-id="98c8b-147">**Start date** and **End date**</span></span>
  - <span data-ttu-id="98c8b-148">암호화 방법</span><span class="sxs-lookup"><span data-stu-id="98c8b-148">Encryption method.</span></span>
  - <span data-ttu-id="98c8b-149">암호화 서식 파일</span><span class="sxs-lookup"><span data-stu-id="98c8b-149">Encryption template.</span></span>

- <span data-ttu-id="98c8b-150">**데이터 보기 기준: 메시지 암호화 보고서** 및 **아래로 나누기: 암호화 서식 파일**: 다음과 같은 암호화 방법을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="98c8b-150">**View data by: Message Encryption Report** and **Break down by: Encryption template**: The following encryption methods are available:</span></span>

  - <span data-ttu-id="98c8b-151">**전달 금지**</span><span class="sxs-lookup"><span data-stu-id="98c8b-151">**Do not forward**</span></span>
  - <span data-ttu-id="98c8b-152">**암호화만**</span><span class="sxs-lookup"><span data-stu-id="98c8b-152">**Encrypt only**</span></span>
  - <span data-ttu-id="98c8b-153">**이전 OME**</span><span class="sxs-lookup"><span data-stu-id="98c8b-153">**OME previous**</span></span>
  - <span data-ttu-id="98c8b-154">**사용자 지정**</span><span class="sxs-lookup"><span data-stu-id="98c8b-154">**Custom**</span></span>

  <span data-ttu-id="98c8b-155">**필터**를 클릭 하면 다음 필터를 사용 하 여 차트를 수정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="98c8b-155">If you click **Filters**, you can modify the chart with the following filters:</span></span>

  - <span data-ttu-id="98c8b-156">**시작 날짜** 및 **끝 날짜**</span><span class="sxs-lookup"><span data-stu-id="98c8b-156">**Start date** and **End date**</span></span>
  - <span data-ttu-id="98c8b-157">암호화 방법</span><span class="sxs-lookup"><span data-stu-id="98c8b-157">Encryption method</span></span>
  - <span data-ttu-id="98c8b-158">암호화 서식 파일</span><span class="sxs-lookup"><span data-stu-id="98c8b-158">Encryption template</span></span>

- <span data-ttu-id="98c8b-159">**데이터 보기 기준: 상위 5 개 받는 사람 도메인**:이 보기에는 상위 5 개 받는 사람 도메인에 대 한 보낸 메시지 수가 표시 되는 원형 차트가 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="98c8b-159">**View data by: Top 5 recipient domains**: This view shows a pie chart with sent message counts for the top 5 recipient domains.</span></span>

  <span data-ttu-id="98c8b-160">**필터**를 클릭 하면 **시작 날짜** 와 **끝 날짜**를 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="98c8b-160">If you click **Filters**, you can select a **Start date** and **End date**.</span></span>

### <a name="details-table-view-for-the-encryption-report"></a><span data-ttu-id="98c8b-161">암호화 보고서에 대 한 세부 정보 테이블 보기</span><span class="sxs-lookup"><span data-stu-id="98c8b-161">Details table view for the Encryption report</span></span>

<span data-ttu-id="98c8b-162">**세부 정보 표 보기**를 클릭 하면 표시 되는 정보는 보고 있는 차트에 따라 달라 집니다.</span><span class="sxs-lookup"><span data-stu-id="98c8b-162">If you click **View details table**, the information that's shown depends on the chart you were looking at:</span></span>

- <span data-ttu-id="98c8b-163">**아래로 나누기: 암호화 방법** 또는 **아래로 나누기: 암호화 서식 파일**: 다음 정보가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="98c8b-163">**Break down by: Encryption method** or **Break down by: Encryption template**: The following information is shown:</span></span>

  - <span data-ttu-id="98c8b-164">**날짜**</span><span class="sxs-lookup"><span data-stu-id="98c8b-164">**Date**</span></span>
  - <span data-ttu-id="98c8b-165">**보낸 사람 주소**</span><span class="sxs-lookup"><span data-stu-id="98c8b-165">**Sender address**</span></span>
  - <span data-ttu-id="98c8b-166">**암호화 서식 파일**</span><span class="sxs-lookup"><span data-stu-id="98c8b-166">**Encryption template**</span></span>
  - <span data-ttu-id="98c8b-167">**암호화 방법**</span><span class="sxs-lookup"><span data-stu-id="98c8b-167">**Encryption method**</span></span>
  - <span data-ttu-id="98c8b-168">**받는 사람 주소**</span><span class="sxs-lookup"><span data-stu-id="98c8b-168">**Recipient address**</span></span>
  - <span data-ttu-id="98c8b-169">**제목**</span><span class="sxs-lookup"><span data-stu-id="98c8b-169">**Subject**</span></span>

- <span data-ttu-id="98c8b-170">**데이터 보기 기준: 상위 5 개 받는 사람 도메인**:</span><span class="sxs-lookup"><span data-stu-id="98c8b-170">**View data by: Top 5 recipient domains**:</span></span>

  - <span data-ttu-id="98c8b-171">**날짜**</span><span class="sxs-lookup"><span data-stu-id="98c8b-171">**Date**</span></span>
  - <span data-ttu-id="98c8b-172">**받는 사람 도메인**</span><span class="sxs-lookup"><span data-stu-id="98c8b-172">**Recipient domain**</span></span>
  - <span data-ttu-id="98c8b-173">**메시지 수**</span><span class="sxs-lookup"><span data-stu-id="98c8b-173">**Message count**</span></span>
  
<span data-ttu-id="98c8b-174">세부 정보 표 보기에서 **필터** 를 클릭 하면 다음 필터를 사용 하 여 결과를 수정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="98c8b-174">If you click **Filters** in a details table view, you can modify the results with the following filters:</span></span>

- <span data-ttu-id="98c8b-175">**시작 날짜** 및 **끝 날짜**</span><span class="sxs-lookup"><span data-stu-id="98c8b-175">**Start date** and **End date**</span></span>
- <span data-ttu-id="98c8b-176">암호화 방법</span><span class="sxs-lookup"><span data-stu-id="98c8b-176">Encryption method</span></span>
- <span data-ttu-id="98c8b-177">암호화 서식 파일</span><span class="sxs-lookup"><span data-stu-id="98c8b-177">Encryption template</span></span>

<span data-ttu-id="98c8b-178">보고서 보기로 돌아가려면 **보고서 보기**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="98c8b-178">To go back to the report view, click **View report**.</span></span>

## <a name="mailflow-status-report"></a><span data-ttu-id="98c8b-179">메일 흐름 상태 보고서</span><span class="sxs-lookup"><span data-stu-id="98c8b-179">Mailflow status report</span></span>

<span data-ttu-id="98c8b-180">**메일 흐름 status 보고서** 에는 맬웨어, 스팸, 피싱 및에 지 차단 된 메시지에 대 한 정보가 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="98c8b-180">The **Mailflow status report** contains information about malware, spam, phishing and edge blocked messages.</span></span> <span data-ttu-id="98c8b-181">자세한 내용은 [메일 흐름 status report](view-mail-flow-reports.md#mailflow-status-report)를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="98c8b-181">For more details, see [Mailflow status report](view-mail-flow-reports.md#mailflow-status-report).</span></span>

## <a name="malware-detections-in-email-report"></a><span data-ttu-id="98c8b-182">전자 메일 보고서에서 맬웨어 감지</span><span class="sxs-lookup"><span data-stu-id="98c8b-182">Malware detections in email report</span></span>

<span data-ttu-id="98c8b-183">**전자 메일 보고서에서** 검색 된 맬웨어는 들어오는 및 보내는 전자 메일 메시지의 맬웨어 감지에 대 한 정보를 표시 합니다 (Exchange Online PROTECTION 또는 EOP에서 감지한 맬웨어).</span><span class="sxs-lookup"><span data-stu-id="98c8b-183">The **Malware detections in email** report shows information about malware detections in incoming and outgoing email messages (malware detected by Exchange Online Protection or EOP).</span></span> <span data-ttu-id="98c8b-184">EOP의 맬웨어 보호에 대 한 자세한 내용은 [EOP의 맬웨어 방지 보호](anti-malware-protection.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="98c8b-184">For more information about malware protection in EOP, see [Anti-malware protection in EOP](anti-malware-protection.md).</span></span>

 <span data-ttu-id="98c8b-185">집계 보기 필터는 90 일을 허용 하 고 세부 정보 테이블 필터는 10 일 동안만 허용 합니다.</span><span class="sxs-lookup"><span data-stu-id="98c8b-185">The aggregate view filter allows for 90 days, while the details table filter only allows for 10 days.</span></span>

<span data-ttu-id="98c8b-186">보고서를 보려면 [보안 & 준수 센터](https://protection.office.com)를 열고 **보고서** \> **대시보드로** 이동한 후 **전자 메일로 맬웨어 감지**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="98c8b-186">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Malware detections in email**.</span></span> <span data-ttu-id="98c8b-187">보고서로 직접 이동 하려면를 엽니다 <https://protection.office.com/reportv2?id=MalwareDetections> .</span><span class="sxs-lookup"><span data-stu-id="98c8b-187">To go directly to the report, open <https://protection.office.com/reportv2?id=MalwareDetections>.</span></span>

![보고서 대시보드의 전자 메일 위젯에 있는 맬웨어 감지](../../media/malware-detections-widget.png)

<span data-ttu-id="98c8b-189">**필터** 를 클릭 하 고 다음을 선택 하 여 차트 및 세부 정보 테이블을 모두 필터링 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="98c8b-189">You can filter both the chart and the details table by clicking **Filters** and selecting:</span></span>

- <span data-ttu-id="98c8b-190">**시작 날짜** 및 **끝 날짜**</span><span class="sxs-lookup"><span data-stu-id="98c8b-190">**Start date** and **End date**</span></span>
- <span data-ttu-id="98c8b-191">**인바운드**</span><span class="sxs-lookup"><span data-stu-id="98c8b-191">**Inbound**</span></span>
- <span data-ttu-id="98c8b-192">**아웃 바운드**</span><span class="sxs-lookup"><span data-stu-id="98c8b-192">**Outbound**</span></span>

![전자 메일 보고서의 맬웨어 검색에서 보고서 보기](../../media/malware-detections-report-view.png)

<span data-ttu-id="98c8b-194">**세부 정보 테이블 보기**를 클릭 하면 다음 세부 정보를 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="98c8b-194">If you click **View details table**, you can see the following details:</span></span>

- <span data-ttu-id="98c8b-195">**날짜**</span><span class="sxs-lookup"><span data-stu-id="98c8b-195">**Date**</span></span>
- <span data-ttu-id="98c8b-196">**보낸 사람 주소**</span><span class="sxs-lookup"><span data-stu-id="98c8b-196">**Sender address**</span></span>
- <span data-ttu-id="98c8b-197">**받는 사람 주소**</span><span class="sxs-lookup"><span data-stu-id="98c8b-197">**Recipient address**</span></span>
- <span data-ttu-id="98c8b-198">**메시지 id**: 메시지 헤더의 **메시지 id** 헤더 필드에서 사용할 수 있으며 고유 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="98c8b-198">**Message ID**: Available in the **Message-ID** header field in the message header and should be unique.</span></span> <span data-ttu-id="98c8b-199">예를 들면 `<08f1e0f6806a47b4ac103961109ae6ef@server.domain>` 꺾쇠 괄호를 참고 하십시오.</span><span class="sxs-lookup"><span data-stu-id="98c8b-199">An example value is `<08f1e0f6806a47b4ac103961109ae6ef@server.domain>` (note the angle brackets).</span></span>
- <span data-ttu-id="98c8b-200">**제목**</span><span class="sxs-lookup"><span data-stu-id="98c8b-200">**Subject**</span></span>
- <span data-ttu-id="98c8b-201">**파일 이름**</span><span class="sxs-lookup"><span data-stu-id="98c8b-201">**Filename**</span></span>
- <span data-ttu-id="98c8b-202">**맬웨어 이름**</span><span class="sxs-lookup"><span data-stu-id="98c8b-202">**Malware name**</span></span>

<span data-ttu-id="98c8b-203">보고서 보기로 돌아가려면 **보고서 보기**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="98c8b-203">To go back to the report view, click **View report**.</span></span>

## <a name="sent-and-received-email-report"></a><span data-ttu-id="98c8b-204">보내고 받은 전자 메일 보고서</span><span class="sxs-lookup"><span data-stu-id="98c8b-204">Sent and received email report</span></span>

<span data-ttu-id="98c8b-205">**Sent and received 전자 메일** 보고서에는 맬웨어, 스팸, 메일 흐름 규칙 (전송 규칙이 라고도 함) 및 고급 맬웨어 검색 후 서비스가 서비스를 시작한 후에 대 한 정보가 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="98c8b-205">The **Sent and received email** report contains information about malware, spam, mail flow rules (also known as transport rules), and advanced malware detections after email enters the service.</span></span> <span data-ttu-id="98c8b-206">자세한 내용은 [Sent and received email report](view-mail-flow-reports.md#sent-and-received-email-report)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="98c8b-206">For more information, see [Sent and received email report](view-mail-flow-reports.md#sent-and-received-email-report).</span></span>

## <a name="spam-detections-report"></a><span data-ttu-id="98c8b-207">스팸 검색 보고서</span><span class="sxs-lookup"><span data-stu-id="98c8b-207">Spam detections report</span></span>

<span data-ttu-id="98c8b-208">**스팸 감지** 보고서에는 EOP에 의해 차단 된 스팸 전자 메일 메시지가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="98c8b-208">The **Spam detections** report shows spam email messages that were blocked by EOP.</span></span> <span data-ttu-id="98c8b-209">메시지는 받는 사람이 아닌 개별 단위로 계산 됩니다.</span><span class="sxs-lookup"><span data-stu-id="98c8b-209">Messages are counted individually, not per recipient.</span></span> <span data-ttu-id="98c8b-210">예를 들어 조직에서 100 받는 사람에 게 동일한 스팸 메시지를 전송 하면 하나의 메시지로 계산 됩니다.</span><span class="sxs-lookup"><span data-stu-id="98c8b-210">For example, if the same spam message was sent to 100 recipients in your organization, it counts as one message.</span></span>

<span data-ttu-id="98c8b-211">집계 보기는 90 일 필터링을 허용 하지만 details 테이블은 10 일 필터링을 허용 합니다.</span><span class="sxs-lookup"><span data-stu-id="98c8b-211">The aggregate view allows for 90 days filtering, while the details table allows for 10 days filtering.</span></span>

<span data-ttu-id="98c8b-212">보고서를 보려면 [보안 & 준수 센터](https://protection.office.com)를 열고 **보고서** \> **대시보드로** 이동한 후 **스팸 감지**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="98c8b-212">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Spam detections**.</span></span> <span data-ttu-id="98c8b-213">보고서로 직접 이동 하려면를 엽니다 <https://protection.office.com/reportv2?id=SpamDetections> .</span><span class="sxs-lookup"><span data-stu-id="98c8b-213">To go directly to the report, open <https://protection.office.com/reportv2?id=SpamDetections>.</span></span>

![보고서 대시보드의 스팸 감지 위젯](../../media/spam-detections-report-widget.png)

<span data-ttu-id="98c8b-215">스팸 방지 보호 기능에 대 한 자세한 내용은 [EOP의 스팸 방지 보호](anti-spam-protection.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="98c8b-215">For more information about anti-spam protection, see [Anti-spam protection in EOP](anti-spam-protection.md).</span></span>

### <a name="report-view-for-the-spam-detections-report"></a><span data-ttu-id="98c8b-216">스팸 감지 보고서에 대 한 보고서 보기</span><span class="sxs-lookup"><span data-stu-id="98c8b-216">Report view for the Spam detections report</span></span>

<span data-ttu-id="98c8b-217">보고서 보기에서는 다음과 같은 차트를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="98c8b-217">The following charts are available in the report view:</span></span>

- <span data-ttu-id="98c8b-218">**아래로 나누기: 작업**: 다음 이벤트 유형이 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="98c8b-218">**Break down by: Action**: The following event types are shown:</span></span>

  - <span data-ttu-id="98c8b-219">**스팸 콘텐츠 필터링 됨**</span><span class="sxs-lookup"><span data-stu-id="98c8b-219">**Spam content filtered**</span></span>
  - <span data-ttu-id="98c8b-220">**스팸 IP 차단**</span><span class="sxs-lookup"><span data-stu-id="98c8b-220">**Spam IP block**</span></span>
  - <span data-ttu-id="98c8b-221">**스팸 봉투 블록**</span><span class="sxs-lookup"><span data-stu-id="98c8b-221">**Spam envelope block**</span></span>
  - <span data-ttu-id="98c8b-222">**스팸 DBEB 필터**: dbeb (디렉터리 기반 edge 차단)</span><span class="sxs-lookup"><span data-stu-id="98c8b-222">**Spam DBEB filter**: Directory based edge blocking (DBEB)</span></span>

  <span data-ttu-id="98c8b-223">차트의 날짜 (데이터 요소)를 가리키면 해당 항목이 분류 되는 방식과 해당 일이 차단 된 항목의 수를 볼 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="98c8b-223">When you hover over a day (data point) in the chart, you can see how many items were blocked that day, as well as how those items are categorized.</span></span>

  ![스팸 감지 보고서의 작업 보기](../../media/spam-detections-report-action-view.png)

- <span data-ttu-id="98c8b-225">**나누기: 방향**: 다음 지침을 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="98c8b-225">**Break down by:Direction**: The following directions are shown:</span></span>

  - <span data-ttu-id="98c8b-226">**인바운드**</span><span class="sxs-lookup"><span data-stu-id="98c8b-226">**Inbound**</span></span>
  - <span data-ttu-id="98c8b-227">**아웃 바운드**</span><span class="sxs-lookup"><span data-stu-id="98c8b-227">**Outbound**</span></span>

  ![스팸 감지 보고서의 방향 보기](../../media/spam-detections-report-direction-view.png)

<span data-ttu-id="98c8b-229">보고서 보기에서 **필터** 를 클릭 하면 다음 필터를 사용 하 여 결과를 수정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="98c8b-229">If you click **Filters** in a report view, you can modify the results with the following filters:</span></span>

- <span data-ttu-id="98c8b-230">**시작 날짜** 및 **끝 날짜**</span><span class="sxs-lookup"><span data-stu-id="98c8b-230">**Start date** and **End date**</span></span>
- <span data-ttu-id="98c8b-231">방향 값</span><span class="sxs-lookup"><span data-stu-id="98c8b-231">Direction values</span></span>
- <span data-ttu-id="98c8b-232">이벤트 유형 값</span><span class="sxs-lookup"><span data-stu-id="98c8b-232">Event type values</span></span>

### <a name="details-table-view-for-the-spam-detections-report"></a><span data-ttu-id="98c8b-233">스팸 감지 보고서에 대 한 세부 정보 테이블 보기</span><span class="sxs-lookup"><span data-stu-id="98c8b-233">Details table view for the Spam detections report</span></span>

<span data-ttu-id="98c8b-234">모든 보고서 보기에서 **세부 정보 테이블 보기** 를 클릭 하면 다음과 같은 정보가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="98c8b-234">If you click **View details table** in any report view, the following information is shown:</span></span>

- <span data-ttu-id="98c8b-235">**날짜**</span><span class="sxs-lookup"><span data-stu-id="98c8b-235">**Date**</span></span>
- <span data-ttu-id="98c8b-236">**보낸 사람 주소**</span><span class="sxs-lookup"><span data-stu-id="98c8b-236">**Sender address**</span></span>
- <span data-ttu-id="98c8b-237">**받는 사람 주소**</span><span class="sxs-lookup"><span data-stu-id="98c8b-237">**Recipient address**</span></span>
- <span data-ttu-id="98c8b-238">**이벤트 유형**</span><span class="sxs-lookup"><span data-stu-id="98c8b-238">**Event type**</span></span>
- <span data-ttu-id="98c8b-239">**작업**</span><span class="sxs-lookup"><span data-stu-id="98c8b-239">**Action**</span></span>
- <span data-ttu-id="98c8b-240">**제목**</span><span class="sxs-lookup"><span data-stu-id="98c8b-240">**Subject**</span></span>

<span data-ttu-id="98c8b-241">세부 정보 테이블에서 **필터** 를 클릭 하면 다음 필터를 사용 하 여 결과를 수정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="98c8b-241">If you click **Filters** in a details table, you can modify the results with the following filters:</span></span>

- <span data-ttu-id="98c8b-242">**시작 날짜** 및 **끝 날짜**</span><span class="sxs-lookup"><span data-stu-id="98c8b-242">**Start date** and **End date**</span></span>
- <span data-ttu-id="98c8b-243">방향 값</span><span class="sxs-lookup"><span data-stu-id="98c8b-243">Direction values</span></span>
- <span data-ttu-id="98c8b-244">이벤트 유형 값</span><span class="sxs-lookup"><span data-stu-id="98c8b-244">Event type values</span></span>

<span data-ttu-id="98c8b-245">보고서 보기로 돌아가려면 **보고서 보기**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="98c8b-245">To go back to the report view, click **View report**.</span></span>

## <a name="spoof-detections-report"></a><span data-ttu-id="98c8b-246">스푸핑 감지 보고서</span><span class="sxs-lookup"><span data-stu-id="98c8b-246">Spoof detections report</span></span>

<span data-ttu-id="98c8b-247">**스푸핑** 감지 보고서에는 얼마나 많은 스푸핑 메일 메시지가 검색 되었는지, 즉 합법적인 비즈니스 이유로 인해 스푸핑 메일을 "양호" 한 것으로 간주 되는 메시지 들이 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="98c8b-247">The **Spoof detections** report shows how many spoof mail messages were detected, and of those, which ones were considered "good" (spoof mail done for legitimate business reasons).</span></span> <span data-ttu-id="98c8b-248">스푸핑에 대 한 자세한 내용은 [EOP에서 스푸핑 방지 보호](anti-spoofing-protection.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="98c8b-248">For more information about spoofing, see [Anti-spoofing protection in EOP](anti-spoofing-protection.md).</span></span>

<span data-ttu-id="98c8b-249">보고서의 집계 보기에서 90 일의 필터링을 허용 하 고 세부 정보 보기에서는 필터링을 10 일 동안만 허용 합니다.</span><span class="sxs-lookup"><span data-stu-id="98c8b-249">The aggregate view of the report allows for 90 days of filtering, while the detail view only allows for ten days of filtering.</span></span>

<span data-ttu-id="98c8b-250">보고서를 보려면 [보안 & 준수 센터](https://protection.office.com)를 열고 **보고서** \> **대시보드로** 이동한 후 검색을 **스푸핑**합니다 .를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="98c8b-250">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Spoof detections**.</span></span> <span data-ttu-id="98c8b-251">보고서로 직접 이동 하려면를 엽니다 <https://protection.office.com/reportv2?id=SpoofMailReport> .</span><span class="sxs-lookup"><span data-stu-id="98c8b-251">To go directly to the report, open <https://protection.office.com/reportv2?id=SpoofMailReport>.</span></span>

![보고서 대시보드의 스푸핑 감지 위젯](../../media/spoof-detections-widget.png)

<span data-ttu-id="98c8b-253">차트에서 일 (데이터 요소)을 가리키면 위장 메일 메시지의 수를 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="98c8b-253">When you hover over a day (data point) in the chart, you can see how many spoof mail messages came through.</span></span>

<span data-ttu-id="98c8b-254">**필터** 를 클릭 하 고 다음 값 중 하나 이상을 선택 하 여 차트 및 세부 정보 테이블을 모두 필터링 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="98c8b-254">You can filter both the chart and the details table by clicking **Filters** and selecting one or more of the following values:</span></span>

- <span data-ttu-id="98c8b-255">**시작 날짜** 및 **끝 날짜**</span><span class="sxs-lookup"><span data-stu-id="98c8b-255">**Start date** and **End date**</span></span>

- <span data-ttu-id="98c8b-256">**좋은 메일**</span><span class="sxs-lookup"><span data-stu-id="98c8b-256">**Good mail**</span></span>

- <span data-ttu-id="98c8b-257">**스팸으로 감지**</span><span class="sxs-lookup"><span data-stu-id="98c8b-257">**Caught as spam**</span></span>

![스푸핑 감지 보고서의 보고서 보기](../../media/spoof-detections-report-view.png)

<span data-ttu-id="98c8b-259">**세부 정보 테이블 보기**를 클릭 하면 다음 세부 정보를 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="98c8b-259">If you click **View details table**, you can see the following details:</span></span>

- <span data-ttu-id="98c8b-260">**날짜**</span><span class="sxs-lookup"><span data-stu-id="98c8b-260">**Date**</span></span>
- <span data-ttu-id="98c8b-261">**스푸핑된 보낸 사람**</span><span class="sxs-lookup"><span data-stu-id="98c8b-261">**Spoofed sender**</span></span>
- <span data-ttu-id="98c8b-262">**True 보낸 사람**</span><span class="sxs-lookup"><span data-stu-id="98c8b-262">**True sender**</span></span>
- <span data-ttu-id="98c8b-263">**보낸 사람 IP**</span><span class="sxs-lookup"><span data-stu-id="98c8b-263">**Sender IP**</span></span>
- <span data-ttu-id="98c8b-264">**작업**</span><span class="sxs-lookup"><span data-stu-id="98c8b-264">**Action**</span></span>
- <span data-ttu-id="98c8b-265">**메시지 수**</span><span class="sxs-lookup"><span data-stu-id="98c8b-265">**Message count**</span></span>

<span data-ttu-id="98c8b-266">보고서 보기로 돌아가려면 **보고서 보기**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="98c8b-266">To go back to the report view, click **View report**.</span></span>

## <a name="threat-protection-status-report"></a><span data-ttu-id="98c8b-267">위협 방지 상태 보고서</span><span class="sxs-lookup"><span data-stu-id="98c8b-267">Threat protection status report</span></span>

<span data-ttu-id="98c8b-268">**위협 방지 상태** 보고서는 EOP 및 OFFICE 365 ATP에서 모두 사용할 수 있습니다. 그러나 보고서에는 다양 한 데이터가 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="98c8b-268">The **Threat protection status** report is available in both EOP and Office 365 ATP; however, the reports contain different data.</span></span> <span data-ttu-id="98c8b-269">예를 들어 EOP 고객은 전자 메일로 감지 되었지만 [SharePoint Online, OneDrive 또는 Microsoft 팀에서 검색 된 악성 파일](atp-for-spo-odb-and-teams.md)에 대 한 정보는 볼 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="98c8b-269">For example, EOP customers can view information about malware detected in email, but not information about [malicious files detected in SharePoint Online, OneDrive, or Microsoft Teams](atp-for-spo-odb-and-teams.md).</span></span>

<span data-ttu-id="98c8b-270">이 보고서는 맬웨어 방지 엔진에 의해 차단 된 파일 또는 웹 사이트 주소 (Url)와 같은 악성 콘텐츠가 포함 된 전자 메일 메시지의 수를 제공 합니다 [(0 시간 자동 제거 (ZAP)](zero-hour-auto-purge.md)및 Atp [safe Links](atp-safe-links.md), [Atp 안전한 첨부 파일](atp-safe-attachments.md)및 [atp](set-up-anti-phishing-policies.md)기능).</span><span class="sxs-lookup"><span data-stu-id="98c8b-270">The report provides the count of email messages with malicious content, such as files or website addresses (URLs) that were blocked by the anti-malware engine, [zero-hour auto purge (ZAP)](zero-hour-auto-purge.md), and ATP features like [ATP Safe Links](atp-safe-links.md), [ATP Safe Attachments](atp-safe-attachments.md), and [ATP anti-phishing](set-up-anti-phishing-policies.md).</span></span> <span data-ttu-id="98c8b-271">이 정보를 사용 하 여 경향을 식별 하거나 조직 정책 조정이 필요한 지 여부를 결정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="98c8b-271">You can use this information to identify trends or determine whether organization policies need adjustment.</span></span> <span data-ttu-id="98c8b-272">메시지가 5 명의 받는 사람에 게 전송 되는 경우 메시지가 한 명의 메시지와 다르게 계산 된다는 것을 이해 하는 것이 중요 합니다.</span><span class="sxs-lookup"><span data-stu-id="98c8b-272">It's important to understand that if a message is sent to five recipients we count it as five different messages and not one message.</span></span>

<span data-ttu-id="98c8b-273">보고서를 보려면 [보안 & 준수 센터](https://protection.office.com)를 열고 **보고서** \> **대시보드로** 이동한 다음 **위협 방지 상태**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="98c8b-273">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Threat protection status**.</span></span> <span data-ttu-id="98c8b-274">보고서로 직접 이동 하려면 다음 Url 중 하나를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="98c8b-274">To go directly to the report, open one of the following URLs:</span></span>

- <span data-ttu-id="98c8b-275">Office 365 ATP: <https://protection.office.com/reportv2?id=ATPV2AggregateReport> 입니다.</span><span class="sxs-lookup"><span data-stu-id="98c8b-275">Office 365 ATP: <https://protection.office.com/reportv2?id=ATPV2AggregateReport>.</span></span>
- <span data-ttu-id="98c8b-276">EOP <https://protection.office.com/reportv2?id=ATPAggregateLightReport></span><span class="sxs-lookup"><span data-stu-id="98c8b-276">EOP: <https://protection.office.com/reportv2?id=ATPAggregateLightReport></span></span>

![보고서 대시보드의 위협 보호 상태 위젯](../../media/threat-protection-status-report-widget.png)

<span data-ttu-id="98c8b-278">기본적으로이 차트에는 최근 7 일간의 데이터가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="98c8b-278">By default, the chart shows data for the past 7 days.</span></span> <span data-ttu-id="98c8b-279">**필터**를 클릭 하면 90 일 날짜 범위 (평가판 구독을 30 일로 제한할 수 있음)를 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="98c8b-279">If you click **Filters**, you can select a 90 day date range (trial subscriptions might be limited to 30 days).</span></span> <span data-ttu-id="98c8b-280">세부 정보 테이블 보기에서는 30 일간 필터링을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="98c8b-280">The details table view allows filtering for 30 days.</span></span>

### <a name="report-view-for-the-threat-protection-status-report"></a><span data-ttu-id="98c8b-281">위협 보호 상태 보고서에 대 한 보고서 보기</span><span class="sxs-lookup"><span data-stu-id="98c8b-281">Report view for the Threat protection status report</span></span>

<span data-ttu-id="98c8b-282">다음 보기를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="98c8b-282">The following views are available:</span></span>

- <span data-ttu-id="98c8b-283">**데이터 보기 기준: 개요**: 다음 검색 정보가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="98c8b-283">**View data by: Overview**: The following detection information is shown:</span></span>

  - <span data-ttu-id="98c8b-284">**전자 메일 맬웨어**</span><span class="sxs-lookup"><span data-stu-id="98c8b-284">**Email malware**</span></span>
  - <span data-ttu-id="98c8b-285">**전자 메일 피싱**</span><span class="sxs-lookup"><span data-stu-id="98c8b-285">**Email phish**</span></span>
  - <span data-ttu-id="98c8b-286">**콘텐츠 맬웨어**</span><span class="sxs-lookup"><span data-stu-id="98c8b-286">**Content malware**</span></span>

  ![위협 보호 상태 보고서의 개요 보기](../../media/threat-protection-status-report-overview-view.png)

- <span data-ttu-id="98c8b-288">**데이터 보기 기준: 콘텐츠 \> 맬웨어**<sup>1</sup>: Office 365 ATP 조직에 대해 다음과 같은 정보가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="98c8b-288">**View data by: Content \> Malware**<sup>1</sup>: The following information is shown for Office 365 ATP organizations:</span></span>

  - <span data-ttu-id="98c8b-289">**맬웨어 방지 엔진**</span><span class="sxs-lookup"><span data-stu-id="98c8b-289">**Anti-malware engine**</span></span>
  - <span data-ttu-id="98c8b-290">**파일 샌드 박싱**</span><span class="sxs-lookup"><span data-stu-id="98c8b-290">**File detonation**</span></span>

  ![위협 방지 상태 보고서의 콘텐츠 맬웨어 보기](../../media/threat-protection-status-report-content-malware-view.png)

- <span data-ttu-id="98c8b-292">**아래로 나누기: 기술** 및 **데이터 보기 기준: 전자 메일 \> 피싱**: 다음 정보가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="98c8b-292">**Break down by: Detection technology** and **View data by: Email \> Phish**: The following information is shown:</span></span>

  - <span data-ttu-id="98c8b-293">**ATP 생성 URL 신뢰도**<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="98c8b-293">**ATP-generated URL reputation**<sup>1</sup></span></span>
  - <span data-ttu-id="98c8b-294">**고급 피싱 필터**</span><span class="sxs-lookup"><span data-stu-id="98c8b-294">**Advanced phish filter**</span></span>
  - <span data-ttu-id="98c8b-295">**스푸핑 방지: DMARC 오류**</span><span class="sxs-lookup"><span data-stu-id="98c8b-295">**Anti-spoof: DMARC failure**</span></span>
  - <span data-ttu-id="98c8b-296">**스푸핑 방지: 조직 내**</span><span class="sxs-lookup"><span data-stu-id="98c8b-296">**Anti-spoof: Intra-org**</span></span>
  - <span data-ttu-id="98c8b-297">**스푸핑 방지: 외부 도메인**</span><span class="sxs-lookup"><span data-stu-id="98c8b-297">**Anti-spoof: external domain**</span></span>
  - <span data-ttu-id="98c8b-298">**브랜드 가장**</span><span class="sxs-lookup"><span data-stu-id="98c8b-298">**Brand impersonation**</span></span>
  - <span data-ttu-id="98c8b-299">**도메인 가장**<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="98c8b-299">**Domain impersonation**<sup>1</sup></span></span>
  - <span data-ttu-id="98c8b-300">**EOP URL 신뢰도**</span><span class="sxs-lookup"><span data-stu-id="98c8b-300">**EOP URL reputation**</span></span>
  - <span data-ttu-id="98c8b-301">**일반 피싱 필터**</span><span class="sxs-lookup"><span data-stu-id="98c8b-301">**General phish filter**</span></span>
  - <span data-ttu-id="98c8b-302">**상대**</span><span class="sxs-lookup"><span data-stu-id="98c8b-302">**Others**</span></span>
  - <span data-ttu-id="98c8b-303">**피싱 ZAP**<sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="98c8b-303">**Phish ZAP**<sup>2</sup></span></span>
  - <span data-ttu-id="98c8b-304">**URL 샌드 박싱**<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="98c8b-304">**URL detonation**<sup>1</sup></span></span>
  - <span data-ttu-id="98c8b-305">**사용자 가장**<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="98c8b-305">**User impersonation**<sup>1</sup></span></span>

  ![위협 방지 상태 보고서의 피싱 전자 메일에 대 한 검색 기술 보기](../../media/threat-protection-status-report-phishing-detection-tech-view.png)

- <span data-ttu-id="98c8b-307">**아래로 나누기: 기술** 및 **데이터 보기 By: 전자 메일 \> 맬웨어**: 다음 정보가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="98c8b-307">**Break down by: Detection technology** and **View data by: Email \> Malware**: The following information is shown:</span></span>

  - <span data-ttu-id="98c8b-308">**ATP 생성 파일 신뢰도**<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="98c8b-308">**ATP-generated file reputation**<sup>1</sup></span></span>
  - <span data-ttu-id="98c8b-309">**맬웨어 방지 엔진**<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="98c8b-309">**Anti-malware engine**<sup>1</sup></span></span>
  - <span data-ttu-id="98c8b-310">**맬웨어 방지 정책 파일 형식 블록**</span><span class="sxs-lookup"><span data-stu-id="98c8b-310">**Anti-malware policy file type block**</span></span>
  - <span data-ttu-id="98c8b-311">**파일 샌드 박싱**<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="98c8b-311">**File detonation**<sup>1</sup></span></span>
  - <span data-ttu-id="98c8b-312">**악의적인 파일 신뢰도**</span><span class="sxs-lookup"><span data-stu-id="98c8b-312">**Malicious file reputation**</span></span>
  - <span data-ttu-id="98c8b-313">**맬웨어 ZAP**<sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="98c8b-313">**Malware ZAP**<sup>2</sup></span></span>
  - <span data-ttu-id="98c8b-314">**상대**</span><span class="sxs-lookup"><span data-stu-id="98c8b-314">**Others**</span></span>

  ![위협 방지 상태 보고서의 맬웨어 검색 기술 보기](../../media/threat-protection-status-report-malware-detection-tech-view.png)

- <span data-ttu-id="98c8b-316">**아래로 나누기: 정책 유형** 및 **보기 데이터를 다음으로 표시: 전자 메일 \> 피싱** 또는 **데이터 보기: 전자 메일 \> 맬웨어**: 다음 정보가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="98c8b-316">**Break down by: Policy type** and **View data by: Email \> Phish** or **View data by: Email \> Malware**: The following information is shown:</span></span>

  - <span data-ttu-id="98c8b-317">**맬웨어 방지**</span><span class="sxs-lookup"><span data-stu-id="98c8b-317">**Anti-malware**</span></span>
  - <span data-ttu-id="98c8b-318">**안전한 첨부 파일**<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="98c8b-318">**Safe Attachment**<sup>1</sup></span></span>
  - <span data-ttu-id="98c8b-319">**피싱**</span><span class="sxs-lookup"><span data-stu-id="98c8b-319">**Anti-phish**</span></span>
  - <span data-ttu-id="98c8b-320">**스팸 방지**</span><span class="sxs-lookup"><span data-stu-id="98c8b-320">**Anti-spam**</span></span>
  - <span data-ttu-id="98c8b-321">**메일 흐름 규칙** (전송 규칙이 라고도 함)</span><span class="sxs-lookup"><span data-stu-id="98c8b-321">**Mail flow rule** (also known as a transport rule)</span></span>
  - <span data-ttu-id="98c8b-322">**상대**</span><span class="sxs-lookup"><span data-stu-id="98c8b-322">**Others**</span></span>

  ![위협 보호 상태 보고서의 피싱 전자 메일에 대 한 정책 유형 보기입니다.](../../media/threat-protection-status-report-phishing-policy-type-view.png)

- <span data-ttu-id="98c8b-324">**아래로 나누기: 배달 상태** 및 **데이터 보기 기준: 전자 메일 \> 피싱** 또는 **데이터 보기: 전자 메일 \> 맬웨어**: 다음 정보가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="98c8b-324">**Break down by: Delivery status** and **View data by: Email \> Phish** or **View data by: Email \> Malware**: The following information is shown:</span></span>

  - <span data-ttu-id="98c8b-325">**배달 실패**</span><span class="sxs-lookup"><span data-stu-id="98c8b-325">**Delivery failed**</span></span>
  - <span data-ttu-id="98c8b-326">**끊김**</span><span class="sxs-lookup"><span data-stu-id="98c8b-326">**Dropped**</span></span>
  - <span data-ttu-id="98c8b-327">**받습니다**</span><span class="sxs-lookup"><span data-stu-id="98c8b-327">**Forwarded**</span></span>
  - <span data-ttu-id="98c8b-328">**호스팅된 사서함: 사용자 지정 폴더**</span><span class="sxs-lookup"><span data-stu-id="98c8b-328">**Hosted mailbox: Custom folder**</span></span>
  - <span data-ttu-id="98c8b-329">**호스팅된 사서함: 삭제 된 항목**</span><span class="sxs-lookup"><span data-stu-id="98c8b-329">**Hosted mailbox: Deleted items**</span></span>
  - <span data-ttu-id="98c8b-330">**호스팅된 사서함: 받은 편지함**</span><span class="sxs-lookup"><span data-stu-id="98c8b-330">**Hosted mailbox: Inbox**</span></span>
  - <span data-ttu-id="98c8b-331">**호스팅된 사서함: 정크**</span><span class="sxs-lookup"><span data-stu-id="98c8b-331">**Hosted mailbox: Junk**</span></span>
  - <span data-ttu-id="98c8b-332">**온-프레미스 서버: 배달 됨**</span><span class="sxs-lookup"><span data-stu-id="98c8b-332">**On-premises server: Delivered**</span></span>
  - <span data-ttu-id="98c8b-333">**격리**</span><span class="sxs-lookup"><span data-stu-id="98c8b-333">**Quarantine**</span></span>

  ![위협 보호 상태 보고서의 피싱 전자 메일에 대 한 배달 상태 보기](../../media/threat-protection-status-report-phishing-delivery-status-view.png)

<span data-ttu-id="98c8b-335"><sup>1</sup> OFFICE 365 ATP 전용</span><span class="sxs-lookup"><span data-stu-id="98c8b-335"><sup>1</sup> Office 365 ATP only</span></span>

<span data-ttu-id="98c8b-336"><sup>2</sup> 개 시간 자동 제거 (ZAP)는 독립 실행형 EOP에서 사용할 수 없습니다 (Exchange Online 사서함 에서만 작동 함).</span><span class="sxs-lookup"><span data-stu-id="98c8b-336"><sup>2</sup> Zero-hour auto purge (ZAP) isn't available in standalone EOP (it only works in Exchange Online mailboxes).</span></span>

<span data-ttu-id="98c8b-337">**필터**를 클릭 하면 다음 필터를 사용 하 여 보고서를 수정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="98c8b-337">If you click **Filters**, you can modify the report with the following filters:</span></span>

- <span data-ttu-id="98c8b-338">**시작 날짜** 및 **끝 날짜**</span><span class="sxs-lookup"><span data-stu-id="98c8b-338">**Start date** and **End date**</span></span>
- <span data-ttu-id="98c8b-339">검색 값</span><span class="sxs-lookup"><span data-stu-id="98c8b-339">Detection value</span></span>
- <span data-ttu-id="98c8b-340">**보호** (OFFICE 365 ATP만 해당): **ATP** 또는 **EOP**.</span><span class="sxs-lookup"><span data-stu-id="98c8b-340">**Protected by** (Office 365 ATP only): **ATP** or **EOP**.</span></span> <span data-ttu-id="98c8b-341">이 필터링 가능 속성은 **데이터 보기: 콘텐츠 \> 맬웨어로부터**사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="98c8b-341">Note that this filterable property isn't available in **View data by: Content \> Malware**.</span></span>

### <a name="details-table-view-for-the-threat-protection-status-report"></a><span data-ttu-id="98c8b-342">위협 보호 상태 보고서에 대 한 세부 정보 테이블 보기</span><span class="sxs-lookup"><span data-stu-id="98c8b-342">Details table view for the Threat protection status report</span></span>

<span data-ttu-id="98c8b-343">**세부 정보 표 보기**를 클릭 하면 표시 되는 정보는 보고 있는 차트에 따라 달라 집니다.</span><span class="sxs-lookup"><span data-stu-id="98c8b-343">If you click **View details table**, the information that's shown depends on the chart you were looking at:</span></span>

- <span data-ttu-id="98c8b-344">**데이터 보기 기준: 콘텐츠 \> 맬웨어**:</span><span class="sxs-lookup"><span data-stu-id="98c8b-344">**View data by: Content \> Malware**:</span></span>

  - <span data-ttu-id="98c8b-345">**날짜**</span><span class="sxs-lookup"><span data-stu-id="98c8b-345">**Date**</span></span>
  - <span data-ttu-id="98c8b-346">**위치**</span><span class="sxs-lookup"><span data-stu-id="98c8b-346">**Location**</span></span>
  - <span data-ttu-id="98c8b-347">**보낸 사람**</span><span class="sxs-lookup"><span data-stu-id="98c8b-347">**Directed by**</span></span>
  - <span data-ttu-id="98c8b-348">**맬웨어 이름**</span><span class="sxs-lookup"><span data-stu-id="98c8b-348">**Malware name**</span></span>

- <span data-ttu-id="98c8b-349">**데이터 보기 기준: 개요**: **뷰 정보 테이블** 단추를 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="98c8b-349">**View data by: Overview**: No **View details table** button is available.</span></span>

- <span data-ttu-id="98c8b-350">기타 모든 차트:</span><span class="sxs-lookup"><span data-stu-id="98c8b-350">All other charts:</span></span>

  - <span data-ttu-id="98c8b-351">**날짜**</span><span class="sxs-lookup"><span data-stu-id="98c8b-351">**Date**</span></span>
  - <span data-ttu-id="98c8b-352">**제목**</span><span class="sxs-lookup"><span data-stu-id="98c8b-352">**Subject**</span></span>
  - <span data-ttu-id="98c8b-353">**보낸 사람**</span><span class="sxs-lookup"><span data-stu-id="98c8b-353">**Sender**</span></span>
  - <span data-ttu-id="98c8b-354">**받는 사람**</span><span class="sxs-lookup"><span data-stu-id="98c8b-354">**Recipients**</span></span>
  - <span data-ttu-id="98c8b-355">**검색 기준**</span><span class="sxs-lookup"><span data-stu-id="98c8b-355">**Detected by**</span></span>
  - <span data-ttu-id="98c8b-356">**배달 상태**</span><span class="sxs-lookup"><span data-stu-id="98c8b-356">**Delivery status**</span></span>
  - <span data-ttu-id="98c8b-357">**손상 원본**</span><span class="sxs-lookup"><span data-stu-id="98c8b-357">**Source of compromise**</span></span>

<span data-ttu-id="98c8b-358">**필터**를 클릭 하면 다음 필터를 사용 하 여 보고서를 수정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="98c8b-358">If you click **Filters**, you can modify the report with the following filters:</span></span>

- <span data-ttu-id="98c8b-359">**시작 날짜** 및 **끝 날짜**</span><span class="sxs-lookup"><span data-stu-id="98c8b-359">**Start date** and **End date**</span></span>
- <span data-ttu-id="98c8b-360">검색 값</span><span class="sxs-lookup"><span data-stu-id="98c8b-360">Detection value</span></span>
- <span data-ttu-id="98c8b-361">**보호** (OFFICE 365 ATP만 해당): **ATP** 또는 **EOP**.</span><span class="sxs-lookup"><span data-stu-id="98c8b-361">**Protected by** (Office 365 ATP only): **ATP** or **EOP**.</span></span> <span data-ttu-id="98c8b-362">이 필터링 가능 속성은 **데이터 보기: 콘텐츠 \> 맬웨어로부터**사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="98c8b-362">Note that this filterable property isn't available in **View data by: Content \> Malware**.</span></span>

## <a name="top-malware-report"></a><span data-ttu-id="98c8b-363">주요 맬웨어 보고서</span><span class="sxs-lookup"><span data-stu-id="98c8b-363">Top malware report</span></span>

<span data-ttu-id="98c8b-364">**주요 맬웨어** 보고서에는 [EOP의 맬웨어 방지 보호](anti-malware-protection.md)기능에서 검색 된 다양 한 유형의 맬웨어가 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="98c8b-364">The **Top malware** report shows the various kinds of malware that was detected by [anti-malware protection in EOP](anti-malware-protection.md).</span></span>

<span data-ttu-id="98c8b-365">보고서를 보려면 [보안 & 준수 센터](https://protection.office.com)를 열고 **보고서** \> **대시보드로** 이동한 후에 **상위 맬웨어**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="98c8b-365">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Top malware**.</span></span> <span data-ttu-id="98c8b-366">보고서로 직접 이동 하려면를 엽니다 <https://protection.office.com/reportv2?id=TopMalware> .</span><span class="sxs-lookup"><span data-stu-id="98c8b-366">To go directly to the report, open <https://protection.office.com/reportv2?id=TopMalware>.</span></span>

![보고서 대시보드의 최상위 맬웨어 위젯](../../media/top-malware-report-widget.png)

<span data-ttu-id="98c8b-368">원형 차트의 쐐기형 위에 마우스를 가져가면 맬웨어 종류와 해당 맬웨어가 있는 것으로 검색 된 메시지의 수를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="98c8b-368">When you hover over a wedge in the pie chart, you can see the name of a kind of malware and how many messages were detected as having that malware.</span></span>

![주요 맬웨어 보고서 보기](../../media/top-malware-report-view.png)

<span data-ttu-id="98c8b-370">**세부 정보 테이블 보기**를 클릭 하면 다음 세부 정보를 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="98c8b-370">If you click **View details table**, you can see the following details:</span></span>

- <span data-ttu-id="98c8b-371">**주요 맬웨어**</span><span class="sxs-lookup"><span data-stu-id="98c8b-371">**Top malware**</span></span>
- <span data-ttu-id="98c8b-372">**개수**</span><span class="sxs-lookup"><span data-stu-id="98c8b-372">**Count**</span></span>

<span data-ttu-id="98c8b-373">보고서 보기 또는 세부 정보 테이블 보기에서 **필터** 를 클릭 하면 **시작 날짜** 및 **종료 날짜**와 함께 날짜 범위를 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="98c8b-373">If you click **Filters** in the report view or details table view, you can specify a date range with **Start date** and **End date**.</span></span>

## <a name="url-threat-protection-report"></a><span data-ttu-id="98c8b-374">URL 위협 방지 보고서</span><span class="sxs-lookup"><span data-stu-id="98c8b-374">URL threat protection report</span></span>

<span data-ttu-id="98c8b-375">**URL 위협 방지 보고서** 는 OFFICE 365 ATP (Advanced threat protection)에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="98c8b-375">The **URL threat protection report** is available in Office 365 Advanced Threat Protection (ATP).</span></span> <span data-ttu-id="98c8b-376">자세한 내용은 [URL threat protection report](view-reports-for-atp.md#url-threat-protection-report)를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="98c8b-376">For more information, see [URL threat protection report](view-reports-for-atp.md#url-threat-protection-report).</span></span>

## <a name="user-reported-messages-report"></a><span data-ttu-id="98c8b-377">사용자가 보고 한 메시지 보고서</span><span class="sxs-lookup"><span data-stu-id="98c8b-377">User-reported messages report</span></span>

<span data-ttu-id="98c8b-378">**사용자가 보고 한 메시지** 보고서에는 사용자가 [보고서 메시지 추가 기능](https://docs.microsoft.com/microsoft-365/security/office-365-security/enable-the-report-message-add-in)을 사용 하 여 정크 메일, 피싱 시도 또는 좋은 메일로 보고 한 전자 메일 메시지에 대 한 정보가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="98c8b-378">The **User-reported messages** report shows information about email messages that users have reported as junk, phishing attempts, or good mail by using the [Report Message add-in](https://docs.microsoft.com/microsoft-365/security/office-365-security/enable-the-report-message-add-in).</span></span>

<span data-ttu-id="98c8b-379">각 메시지에 대 한 자세한 내용은 스팸 정책 예외 또는 조직에 대해 구성 된 메일 흐름 규칙과 같은 배달 이유를 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="98c8b-379">Details are available for each message, including the delivery reason, such a spam policy exception or mail flow rule configured for your organization.</span></span> <span data-ttu-id="98c8b-380">세부 정보를 보려면 사용자-보고서 목록에서 항목을 선택한 다음 **요약** 및 **세부 정보** 탭에서 해당 정보를 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="98c8b-380">To view details, select an item in the user-reports list, and then view the information on the **Summary** and **Details** tabs.</span></span>

![사용자가 보고 한 메시지 보고서에는 사용자가 정크로 레이블이 지정 된 메시지, 정크 메일, 피싱 시도 등이 표시 됩니다.](../../media/ad5e9a3d-b833-419c-bcc9-3425d9604ead.png)

<span data-ttu-id="98c8b-382">이 보고서를 보려면 [보안 & 준수 센터](https://protection.office.com)에서 다음 중 하나를 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="98c8b-382">To view this report, in the [Security & Compliance Center](https://protection.office.com), do one of the following:</span></span>

- <span data-ttu-id="98c8b-383">**위협 관리** \> **대시보드** \> **사용자가 보고 한 메시지로**이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="98c8b-383">Go to **Threat management** \> **Dashboard** \> **User-reported messages**.</span></span>

- <span data-ttu-id="98c8b-384">**위협 관리** 로 이동 하 여 \> **Review** \> **사용자가 보고 한 메시지**를 검토 합니다.</span><span class="sxs-lookup"><span data-stu-id="98c8b-384">Go to **Threat management** \> **Review** \> **User-reported messages**.</span></span>

![보안 & 준수 센터에서 위협 관리 \> 검토 \> 사용자가 보고 한 메시지를 선택 합니다.](../../media/e372c57c-1414-4616-957b-bc933b8c8711.png)

> [!IMPORTANT]
> <span data-ttu-id="98c8b-386">사용자가 보고 한 메시지 보고서가 제대로 작동 하도록 하려면 Office 365 환경에 대해 **감사 로깅을 켜야 합니다** .</span><span class="sxs-lookup"><span data-stu-id="98c8b-386">In order for the User-reported messages report to work correctly, **audit logging must be turned on** for your Office 365 environment.</span></span> <span data-ttu-id="98c8b-387">이 작업은 일반적으로 Exchange Online에서 감사 로그 역할이 할당 된 사용자가 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="98c8b-387">This is typically done by someone who has the Audit Logs role assigned in Exchange Online.</span></span> <span data-ttu-id="98c8b-388">자세한 내용은 [Turn Microsoft 365 감사 로그 검색 설정 또는 해제](https://docs.microsoft.com/microsoft-365/compliance/turn-audit-log-search-on-or-off)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="98c8b-388">For more information, see [Turn Microsoft 365 audit log search on or off](https://docs.microsoft.com/microsoft-365/compliance/turn-audit-log-search-on-or-off).</span></span>

## <a name="what-permissions-are-needed-to-view-these-reports"></a><span data-ttu-id="98c8b-389">이러한 보고서를 표시 하는 데 필요한 사용 권한은 무엇입니까?</span><span class="sxs-lookup"><span data-stu-id="98c8b-389">What permissions are needed to view these reports?</span></span>

<span data-ttu-id="98c8b-390">보고서를 보고 사용 하려면 보안 & 준수 센터 **및** Exchange Online에서 지정 된 역할 그룹의 구성원 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="98c8b-390">To view and use the reports, you need to be a member of the specified role group in the Security & Compliance Center **and** in Exchange Online.</span></span>

- <span data-ttu-id="98c8b-391">보안 & 준수 센터에서 다음 역할 그룹 중 하나의 구성원 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="98c8b-391">In the Security & Compliance Center, you need to be a member of one of the following role groups:</span></span>

  <span data-ttu-id="98c8b-392">-조직 관리-보안 관리자 ( [Azure Active Directory 관리 센터](https://aad.portal.azure.com) 에서이 작업을 수행할 수도 있음)-보안 독자</span><span class="sxs-lookup"><span data-stu-id="98c8b-392">-Organization Management -Security Administrator (you can also do this in the [Azure Active Directory admin center](https://aad.portal.azure.com) -Security Reader</span></span>

  <span data-ttu-id="98c8b-393">자세한 내용은 [보안 및 준수 센터의 사용 권한](https://docs.microsoft.com/microsoft-365/security/office-365-security/permissions-in-the-security-and-compliance-center)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="98c8b-393">For more information, see [Permissions in the Security & Compliance Center](https://docs.microsoft.com/microsoft-365/security/office-365-security/permissions-in-the-security-and-compliance-center).</span></span>

- <span data-ttu-id="98c8b-394">Exchange Online에서 다음 역할 그룹 중 하나의 구성원 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="98c8b-394">In Exchange Online, you need to be a member of one of the following role groups:</span></span>

  <span data-ttu-id="98c8b-395">-조직 관리-보기 전용 조직 관리-보기 전용 받는 사람-준수 관리</span><span class="sxs-lookup"><span data-stu-id="98c8b-395">-Organization Management -View-only Organization Management -View-Only Recipients -Compliance Management</span></span>

<span data-ttu-id="98c8b-396">자세한 내용은 exchange online의 [사용 권한](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo) 및 [exchange online에서 역할 그룹 관리](https://docs.microsoft.com/Exchange/permissions-exo/role-groups)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="98c8b-396">For more information, see [Permissions in Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo) and [Manage role groups in Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/role-groups).</span></span>

## <a name="what-if-the-reports-arent-showing-data"></a><span data-ttu-id="98c8b-397">보고서에 데이터가 표시 되지 않으면 어떻게 하나요?</span><span class="sxs-lookup"><span data-stu-id="98c8b-397">What if the reports aren't showing data?</span></span>

<span data-ttu-id="98c8b-398">보고서에 데이터가 표시 되지 않는 경우 정책이 올바르게 설정 되어 있는지 다시 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="98c8b-398">If you are not seeing data in your reports, double-check that your policies are set up correctly.</span></span> <span data-ttu-id="98c8b-399">자세한 내용은 [위협 으로부터 보호](protect-against-threats.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="98c8b-399">To learn more, see [Protect against threats](protect-against-threats.md).</span></span>

## <a name="related-topics"></a><span data-ttu-id="98c8b-400">관련 항목</span><span class="sxs-lookup"><span data-stu-id="98c8b-400">Related topics</span></span>

[<span data-ttu-id="98c8b-401">EOP의 스팸 방지 및 맬웨어 방지 보호 기능</span><span class="sxs-lookup"><span data-stu-id="98c8b-401">Anti-spam and anti-malware protection in EOP</span></span>](anti-spam-and-anti-malware-protection.md)

[<span data-ttu-id="98c8b-402">보안 및 준수 센터의 스마트 보고서 및 인사이트</span><span class="sxs-lookup"><span data-stu-id="98c8b-402">Smart reports and insights in the Security & Compliance Center</span></span>](reports-and-insights-in-security-and-compliance.md)

[<span data-ttu-id="98c8b-403">보안 & 준수 센터에서 메일 흐름 보고서 보기</span><span class="sxs-lookup"><span data-stu-id="98c8b-403">View mail flow reports in the Security & Compliance Center</span></span>](view-mail-flow-reports.md)

[<span data-ttu-id="98c8b-404">Office 365 Advanced Threat Protection에 대 한 보고서 보기</span><span class="sxs-lookup"><span data-stu-id="98c8b-404">View reports for Office 365 Advanced Threat Protection</span></span>](view-reports-for-atp.md)
