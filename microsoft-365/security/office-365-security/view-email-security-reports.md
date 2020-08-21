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
description: 조직의 전자 메일 보안 보고서를 찾아 사용하는 방법에 대해 알아봅니다. 규정 준수 센터의 보안 센터에서 전자 & 보고서를 사용할 수 있습니다.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 2b714d9dc4e3ca143d2cb2d7164f8c3c737d1928
ms.sourcegitcommit: e12fa502bc216f6083ef5666f693a04bb727d4df
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/20/2020
ms.locfileid: "46826508"
---
# <a name="view-email-security-reports-in-the-security--compliance-center"></a><span data-ttu-id="e78f7-104">보안 및 준수 센터의 전자 메일 보안 보고서 보기</span><span class="sxs-lookup"><span data-stu-id="e78f7-104">View email security reports in the Security & Compliance Center</span></span>

<span data-ttu-id="e78f7-105">보안 & 준수 센터에서는 Microsoft 365의 [스팸](https://protection.office.com) 방지, 맬웨어 방지 및 암호화 기능과 같은 전자 메일 보안 기능이 조직을 보호하는 방식을 확인하는 데 도움이 되는 다양한 보고서가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e78f7-105">A variety of reports are available in the [Security & Compliance Center](https://protection.office.com) to help you see how email security features, such as anti-spam, anti-malware, and encryption features in Microsoft 365 are protecting your organization.</span></span> <span data-ttu-id="e78f7-106">필요한 권한이 있는 [경우 보고서 대시보드로](#what-permissions-are-needed-to-view-these-reports)이동하여 보안 센터에서 & **Reports** 수 \> **있습니다.**</span><span class="sxs-lookup"><span data-stu-id="e78f7-106">If you have the [necessary permissions](#what-permissions-are-needed-to-view-these-reports), you can view these reports in the Security & Compliance Center by going to **Reports** \> **Dashboard**.</span></span> <span data-ttu-id="e78f7-107">보고서 대시보드로 직접 이동하려면 <https://protection.office.com/insightdashboard> .</span><span class="sxs-lookup"><span data-stu-id="e78f7-107">To go directly to the Reports dashboard, open <https://protection.office.com/insightdashboard>.</span></span>

![Security Center의 보고서 & 대시보드](../../media/6b213d34-adbb-44af-8549-be9a7e2db087.png)

## <a name="compromised-users-report"></a><span data-ttu-id="e78f7-109">위검토된 사용자 보고서</span><span class="sxs-lookup"><span data-stu-id="e78f7-109">Compromised users report</span></span>

> [!NOTE]
> <span data-ttu-id="e78f7-110">Exchange Online 사서함이 있는 Microsoft 365 조직에서 이 보고서를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e78f7-110">This report is available in Microsoft 365 organizations with Exchange Online mailboxes.</span></span> <span data-ttu-id="e78f7-111">독립 실행형 EOP(Exchange Online Protection) 조직에서는 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="e78f7-111">It's not available in standalone Exchange Online Protection (EOP) organizations.</span></span>

<span data-ttu-id="e78f7-112">**위험에 당한 사용자 보고서에는** 지난 7일 동안 의심스러운 것으로 표시되거나 **Suspicious** **제한된 사용자 계정 수가** 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="e78f7-112">The **Compromised users** report shows shows the number of user accounts that were marked as **Suspicious** or **Restricted** within the last 7 days.</span></span> <span data-ttu-id="e78f7-113">이러한 상태 중 하나의 계정은 문제가 있거나 모두 노출됩니다.</span><span class="sxs-lookup"><span data-stu-id="e78f7-113">Accounts in either of these states are problematic or even compromised.</span></span> <span data-ttu-id="e78f7-114">자주 사용할 경우 보고서를 사용하여 의심스러운 스파이크나 제한된 계정에서 스파이크를 비출 수 있을지를 의심하고 추세를 일상할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e78f7-114">With frequent use, you can use the report to spot spikes, and even trends, in suspicious or restricted accounts.</span></span> <span data-ttu-id="e78f7-115">손상된 사용자에 대한 자세한 내용은 [손상된 전자 메일 계정에 응답을 참조하세요.](responding-to-a-compromised-email-account.md)</span><span class="sxs-lookup"><span data-stu-id="e78f7-115">For more information about compromised users, see [Responding to a compromised email account](responding-to-a-compromised-email-account.md).</span></span>

![보고서 대시보드에서 위검토된 사용자 위산](../../media/compromised-users-report-widget.png)

<span data-ttu-id="e78f7-117">집계 보기에는 지난 90일동안의 데이터가 표시되고 세부 정보 보기에는 지난 30일동안의 데이터가 표시될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e78f7-117">The aggregate view shows data for the last 90 days and the detail view shows data for the last 30 days.</span></span>

<span data-ttu-id="e78f7-118">보고서를 보려면 준수 [센터에서 & 다음](https://protection.office.com)보고서 **대시보드로** \> **이동하여** **위험한 사용자를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="e78f7-118">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Compromised users**.</span></span> <span data-ttu-id="e78f7-119">보고서로 직접 이동하려면 <https://protection.office.com/reportv2?id=CompromisedUsers> .</span><span class="sxs-lookup"><span data-stu-id="e78f7-119">To go directly to the report, open <https://protection.office.com/reportv2?id=CompromisedUsers>.</span></span>

<span data-ttu-id="e78f7-120">필터를 클릭하고 다음 값 중에서 하나 이상을 **선택하여** 차트 및 세부 정보 표를 모두 필터링할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e78f7-120">You can filter both the chart and the details table by clicking **Filters** and selecting one or more of the following values:</span></span>

- <span data-ttu-id="e78f7-121">**시작 날짜** **및 끝 날짜**</span><span class="sxs-lookup"><span data-stu-id="e78f7-121">**Start date** and **End date**</span></span>

- <span data-ttu-id="e78f7-122">**의심스러운 경우:** 사용자 계정이 의심스러운 전자 메일을 전송하며 전자 메일을 보내지 않을 위험성이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e78f7-122">**Suspicious**: The user account has sent suspicious email and is at risk of being restricted from sending email.</span></span>

- <span data-ttu-id="e78f7-123">**제한됨:** 사용자 계정이 고의된 패턴으로 인해 메일을 보내지 않도록 제한되었습니다.</span><span class="sxs-lookup"><span data-stu-id="e78f7-123">**Restricted**: The user account has been restricted from sending email due to highly suspicious patterns.</span></span>

![위검토된 사용자 보고서의 보고서 보기](../../media/compromised-users-report-activity-view.png)

<span data-ttu-id="e78f7-125">세부 정보 **표를 보기를 클릭한 경우에는**다음 세부 정보를 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e78f7-125">If you click **View details table**, you can see the following details:</span></span>

- <span data-ttu-id="e78f7-126">**작성 시간**</span><span class="sxs-lookup"><span data-stu-id="e78f7-126">**Creation time**</span></span>
- <span data-ttu-id="e78f7-127">**사용자 ID**</span><span class="sxs-lookup"><span data-stu-id="e78f7-127">**User ID**</span></span>
- <span data-ttu-id="e78f7-128">**작업**</span><span class="sxs-lookup"><span data-stu-id="e78f7-128">**Action**</span></span>

<span data-ttu-id="e78f7-129">보고서 보기로 돌아가려면 보고서 **보기를 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="e78f7-129">To go back to the report view, click **View report**.</span></span>

## <a name="encryption-report"></a><span data-ttu-id="e78f7-130">암호화 보고서</span><span class="sxs-lookup"><span data-stu-id="e78f7-130">Encryption report</span></span>

<span data-ttu-id="e78f7-131">암호화 **보고서는** EOP(Exchange Online 사서함이 있는 구독 또는 Exchange Online 사서함이 없는 독립 실행형 EOP 구독)에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e78f7-131">The **Encryption report** is available in EOP (subscriptions with mailboxes in Exchange Online or standalone EOP without Exchange Online mailboxes).</span></span> <span data-ttu-id="e78f7-132">조직의 보안 팀은 이 보고서의 정보를 사용하여 중요한 전자 메일 메시지에 대한 패턴을 식별하고 정책을 적예로 적용하거나 조정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e78f7-132">Your organization's security team can use information in this report to identify patterns and proactively apply or adjust policies for sensitive email messages.</span></span> <span data-ttu-id="e78f7-133">예제:</span><span class="sxs-lookup"><span data-stu-id="e78f7-133">For example:</span></span>

- <span data-ttu-id="e78f7-134">사용자가 암호화하는 전자 메일 메시지가 다수 인 경우 특정 사용 사례에 대한 암호화를 자동화하는 암호화 정책을 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e78f7-134">If you see a high number of email messages encrypted by users, you might want to add an encryption policy to automate encryption for certain use cases.</span></span> <span data-ttu-id="e78f7-135">자세한 내용은 [Microsoft 365에서 전자 메일 메시지를 암호화하기 위한 메일의 흐름 규정을 참조하세요.](../../compliance/define-mail-flow-rules-to-encrypt-email.md)</span><span class="sxs-lookup"><span data-stu-id="e78f7-135">For more information, see [Define mail flow rules to encrypt email messages in Microsoft 365](../../compliance/define-mail-flow-rules-to-encrypt-email.md).</span></span>

- <span data-ttu-id="e78f7-136">사용할 수 있는 암호화 템플릿이 여러 개 있지만 아무도 사용하는 사용자가 없는 경우 사용자가 기능 교육이 필요한지 여부를 알게 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e78f7-136">If you have a number of encryption templates available but no one is using them, you might explore whether users need feature training.</span></span>

<span data-ttu-id="e78f7-137">집계 보기에서는 지난 90일 동안의 필터링이 가능한 한 세부 정보 보기에서 10일 동안 필터링할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e78f7-137">The aggregate view allows filtering for the last 90 days, while the detail view allows filtering for 10 days.</span></span>

<span data-ttu-id="e78f7-138">보고서를 보려면 준수 센터에서 [보안 & 보고서](https://protection.office.com)대시보드로 **이동한** \> **후 암호화** **보고서를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="e78f7-138">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Encryption report**.</span></span> <span data-ttu-id="e78f7-139">보고서로 직접 이동하려면 <https://protection.office.com/reportv2?id=EncryptionReport> .</span><span class="sxs-lookup"><span data-stu-id="e78f7-139">To go directly to the report, open <https://protection.office.com/reportv2?id=EncryptionReport>.</span></span>

<span data-ttu-id="e78f7-140">암호화에 대한 자세한 내용은 [Microsoft 365에서 전자 메일 암호화를 참조하세요.](../../compliance/email-encryption.md)</span><span class="sxs-lookup"><span data-stu-id="e78f7-140">To learn more about encryption, see [Email encryption in Microsoft 365](../../compliance/email-encryption.md).</span></span>

### <a name="report-view-for-the-encryption-report"></a><span data-ttu-id="e78f7-141">암호화 보고서 보기</span><span class="sxs-lookup"><span data-stu-id="e78f7-141">Report view for the Encryption report</span></span>

<span data-ttu-id="e78f7-142">다음 필터를 차트에 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e78f7-142">You can use the following filters on the chart:</span></span>

- <span data-ttu-id="e78f7-143">**데이터 보기: 메시지 암호화 보고서 및 분석** **방법: 다음과 같은**암호화 방법을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e78f7-143">**View data by: Message Encryption Report** and **Break down by: Encryption method**: The following encryption methods are available:</span></span>

  - <span data-ttu-id="e78f7-144">**사용자별 암호화**</span><span class="sxs-lookup"><span data-stu-id="e78f7-144">**Encryption by user**</span></span>
  - <span data-ttu-id="e78f7-145">**정책에 의한 암호화**</span><span class="sxs-lookup"><span data-stu-id="e78f7-145">**Encryption by policy**</span></span>

  <span data-ttu-id="e78f7-146">필터를 **클릭하면 다음**필터를 사용하여 차트를 수정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e78f7-146">If you click **Filters**, you can modify the chart with the following filters:</span></span>

  - <span data-ttu-id="e78f7-147">**시작 날짜** **및 끝 날짜**</span><span class="sxs-lookup"><span data-stu-id="e78f7-147">**Start date** and **End date**</span></span>
  - <span data-ttu-id="e78f7-148">암호화 방법.</span><span class="sxs-lookup"><span data-stu-id="e78f7-148">Encryption method.</span></span>
  - <span data-ttu-id="e78f7-149">암호화 서식 파일.</span><span class="sxs-lookup"><span data-stu-id="e78f7-149">Encryption template.</span></span>

- <span data-ttu-id="e78f7-150">**데이터 보기: 메시지 암호화 보고서 및 분석** **방법: 암호화 템플릿: 다음과**같은 암호화 방법을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e78f7-150">**View data by: Message Encryption Report** and **Break down by: Encryption template**: The following encryption methods are available:</span></span>

  - <span data-ttu-id="e78f7-151">**전달 안 합니다.**</span><span class="sxs-lookup"><span data-stu-id="e78f7-151">**Do not forward**</span></span>
  - <span data-ttu-id="e78f7-152">**Encrypt only(암호화만 암호화)**</span><span class="sxs-lookup"><span data-stu-id="e78f7-152">**Encrypt only**</span></span>
  - <span data-ttu-id="e78f7-153">**OME 이전**</span><span class="sxs-lookup"><span data-stu-id="e78f7-153">**OME previous**</span></span>
  - <span data-ttu-id="e78f7-154">**사용자 지정**</span><span class="sxs-lookup"><span data-stu-id="e78f7-154">**Custom**</span></span>

  <span data-ttu-id="e78f7-155">필터를 **클릭하면 다음**필터를 사용하여 차트를 수정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e78f7-155">If you click **Filters**, you can modify the chart with the following filters:</span></span>

  - <span data-ttu-id="e78f7-156">**시작 날짜** **및 끝 날짜**</span><span class="sxs-lookup"><span data-stu-id="e78f7-156">**Start date** and **End date**</span></span>
  - <span data-ttu-id="e78f7-157">암호화 방법</span><span class="sxs-lookup"><span data-stu-id="e78f7-157">Encryption method</span></span>
  - <span data-ttu-id="e78f7-158">암호화 템플릿</span><span class="sxs-lookup"><span data-stu-id="e78f7-158">Encryption template</span></span>

- <span data-ttu-id="e78f7-159">**보기: 상위 5개의 받는 사람 도메인:** 이 보기에는 보낸 메시지 수가 상위 5명의 받는 사람 도메인에 대한 배달 보고서 수가 포함된 원형 차트가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="e78f7-159">**View data by: Top 5 recipient domains**: This view shows a pie chart with sent message counts for the top 5 recipient domains.</span></span>

  <span data-ttu-id="e78f7-160">필터를 **클릭하면 시작**날짜와 종료 **날짜를** 선택할 **수 있습니다.**</span><span class="sxs-lookup"><span data-stu-id="e78f7-160">If you click **Filters**, you can select a **Start date** and **End date**.</span></span>

### <a name="details-table-view-for-the-encryption-report"></a><span data-ttu-id="e78f7-161">암호화 보고서의 세부 정보 표 보기</span><span class="sxs-lookup"><span data-stu-id="e78f7-161">Details table view for the Encryption report</span></span>

<span data-ttu-id="e78f7-162">세부 정보 **표를 보기를**클릭하면 표시되는 정보는 검색 하고 있는 차트에 따라 달라지게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e78f7-162">If you click **View details table**, the information that's shown depends on the chart you were looking at:</span></span>

- <span data-ttu-id="e78f7-163">**분석: 암호화 방법 또는 분석** **방법: 암호화 서식 파일을**제공합니다. 암호화 서식 파일은 다음과 같은 정보를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="e78f7-163">**Break down by: Encryption method** or **Break down by: Encryption template**: The following information is shown:</span></span>

  - <span data-ttu-id="e78f7-164">**날짜**</span><span class="sxs-lookup"><span data-stu-id="e78f7-164">**Date**</span></span>
  - <span data-ttu-id="e78f7-165">**보낸 사람 주소**</span><span class="sxs-lookup"><span data-stu-id="e78f7-165">**Sender address**</span></span>
  - <span data-ttu-id="e78f7-166">**암호화 템플릿**</span><span class="sxs-lookup"><span data-stu-id="e78f7-166">**Encryption template**</span></span>
  - <span data-ttu-id="e78f7-167">**암호화 방법**</span><span class="sxs-lookup"><span data-stu-id="e78f7-167">**Encryption method**</span></span>
  - <span data-ttu-id="e78f7-168">**받는 사람 주소**</span><span class="sxs-lookup"><span data-stu-id="e78f7-168">**Recipient address**</span></span>
  - <span data-ttu-id="e78f7-169">**제목**</span><span class="sxs-lookup"><span data-stu-id="e78f7-169">**Subject**</span></span>

- <span data-ttu-id="e78f7-170">**데이터 보기: 받는 사람 5개를 지정합니다.**</span><span class="sxs-lookup"><span data-stu-id="e78f7-170">**View data by: Top 5 recipient domains**:</span></span>

  - <span data-ttu-id="e78f7-171">**날짜**</span><span class="sxs-lookup"><span data-stu-id="e78f7-171">**Date**</span></span>
  - <span data-ttu-id="e78f7-172">**받는 사람 도메인**</span><span class="sxs-lookup"><span data-stu-id="e78f7-172">**Recipient domain**</span></span>
  - <span data-ttu-id="e78f7-173">**메시지 수**</span><span class="sxs-lookup"><span data-stu-id="e78f7-173">**Message count**</span></span>
  
<span data-ttu-id="e78f7-174">세부 정보 표 **보기에서** 필터를 클릭한 경우 다음 필터를 사용하여 결과를 수정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e78f7-174">If you click **Filters** in a details table view, you can modify the results with the following filters:</span></span>

- <span data-ttu-id="e78f7-175">**시작 날짜** **및 끝 날짜**</span><span class="sxs-lookup"><span data-stu-id="e78f7-175">**Start date** and **End date**</span></span>
- <span data-ttu-id="e78f7-176">암호화 방법</span><span class="sxs-lookup"><span data-stu-id="e78f7-176">Encryption method</span></span>
- <span data-ttu-id="e78f7-177">암호화 템플릿</span><span class="sxs-lookup"><span data-stu-id="e78f7-177">Encryption template</span></span>

<span data-ttu-id="e78f7-178">보고서 보기로 돌아가려면 보고서 **보기를 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="e78f7-178">To go back to the report view, click **View report**.</span></span>

## <a name="mailflow-status-report"></a><span data-ttu-id="e78f7-179">메일 흐름 상태 보고서</span><span class="sxs-lookup"><span data-stu-id="e78f7-179">Mailflow status report</span></span>

<span data-ttu-id="e78f7-180">메일 **흐름 상태 보고서에는 맬웨어,** 스팸, 피싱 및 Edge 차단 메시지에 대한 정보가 들어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e78f7-180">The **Mailflow status report** contains information about malware, spam, phishing and edge blocked messages.</span></span> <span data-ttu-id="e78f7-181">자세한 내용은 메일 흐름 상태 [보고서를 참조하세요.](view-mail-flow-reports.md#mailflow-status-report)</span><span class="sxs-lookup"><span data-stu-id="e78f7-181">For more details, see [Mailflow status report](view-mail-flow-reports.md#mailflow-status-report).</span></span>

## <a name="malware-detections-in-email-report"></a><span data-ttu-id="e78f7-182">전자 메일 보고서의 맬웨어 검색</span><span class="sxs-lookup"><span data-stu-id="e78f7-182">Malware detections in email report</span></span>

<span data-ttu-id="e78f7-183">전자 **메일 보고서의 맬웨어 검색 에서는** 수신 및 보내는 전자 메일 메시지(Exchange Online Protection 또는 EOP에서 검색되는 맬웨어)에서 맬웨어 검색에 대한 정보를 보여 주는 정보가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="e78f7-183">The **Malware detections in email** report shows information about malware detections in incoming and outgoing email messages (malware detected by Exchange Online Protection or EOP).</span></span> <span data-ttu-id="e78f7-184">EOP의 맬웨어 보호 기능에 대한 자세한 내용은 [EOP에서 맬웨어 방지 보호 기능을 참조하세요.](anti-malware-protection.md)</span><span class="sxs-lookup"><span data-stu-id="e78f7-184">For more information about malware protection in EOP, see [Anti-malware protection in EOP](anti-malware-protection.md).</span></span>

 <span data-ttu-id="e78f7-185">집계 보기 필터에서는 90일간을 사용할 수 있지만, 세부 정보 표시 테이블 필터는 10일 동안만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e78f7-185">The aggregate view filter allows for 90 days, while the details table filter only allows for 10 days.</span></span>

<span data-ttu-id="e78f7-186">보고서를 보려면 보안 및 감사 [& 센터를 연 다음](https://protection.office.com)보고서 대시보드로 **Reports** \> **이동한** 후 전자 **메일의 맬웨어 검색을 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="e78f7-186">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Malware detections in email**.</span></span> <span data-ttu-id="e78f7-187">보고서로 직접 이동하려면 <https://protection.office.com/reportv2?id=MalwareDetections> .</span><span class="sxs-lookup"><span data-stu-id="e78f7-187">To go directly to the report, open <https://protection.office.com/reportv2?id=MalwareDetections>.</span></span>

![보고서 대시보드에서 전자 메일 위로 스서비스의 맬웨어 감지](../../media/malware-detections-widget.png)

<span data-ttu-id="e78f7-189">필터를 클릭하고 필터를 선택한 다음을 선택하여 차트 및 세부 **정보 표를 모두 필터링할** 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e78f7-189">You can filter both the chart and the details table by clicking **Filters** and selecting:</span></span>

- <span data-ttu-id="e78f7-190">**시작 날짜** **및 끝 날짜**</span><span class="sxs-lookup"><span data-stu-id="e78f7-190">**Start date** and **End date**</span></span>
- <span data-ttu-id="e78f7-191">**인바운드**</span><span class="sxs-lookup"><span data-stu-id="e78f7-191">**Inbound**</span></span>
- <span data-ttu-id="e78f7-192">**아웃바운드**</span><span class="sxs-lookup"><span data-stu-id="e78f7-192">**Outbound**</span></span>

![전자 메일 보고서의 맬웨어 검색에 보고서 보기](../../media/malware-detections-report-view.png)

<span data-ttu-id="e78f7-194">세부 정보 **표를 보기를 클릭한 경우에는**다음 세부 정보를 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e78f7-194">If you click **View details table**, you can see the following details:</span></span>

- <span data-ttu-id="e78f7-195">**날짜**</span><span class="sxs-lookup"><span data-stu-id="e78f7-195">**Date**</span></span>
- <span data-ttu-id="e78f7-196">**보낸 사람 주소**</span><span class="sxs-lookup"><span data-stu-id="e78f7-196">**Sender address**</span></span>
- <span data-ttu-id="e78f7-197">**받는 사람 주소**</span><span class="sxs-lookup"><span data-stu-id="e78f7-197">**Recipient address**</span></span>
- <span data-ttu-id="e78f7-198">**메시지 ID**: 메시지 헤더의 **메시지 ID 헤더** 필드에서 사용할 수 있고 고유해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e78f7-198">**Message ID**: Available in the **Message-ID** header field in the message header and should be unique.</span></span> <span data-ttu-id="e78f7-199">괄성에 `<08f1e0f6806a47b4ac103961109ae6ef@server.domain>` 주의해야 합니다(</span><span class="sxs-lookup"><span data-stu-id="e78f7-199">An example value is `<08f1e0f6806a47b4ac103961109ae6ef@server.domain>` (note the angle brackets).</span></span>
- <span data-ttu-id="e78f7-200">**제목**</span><span class="sxs-lookup"><span data-stu-id="e78f7-200">**Subject**</span></span>
- <span data-ttu-id="e78f7-201">**파일 이름**</span><span class="sxs-lookup"><span data-stu-id="e78f7-201">**Filename**</span></span>
- <span data-ttu-id="e78f7-202">**맬웨어 이름**</span><span class="sxs-lookup"><span data-stu-id="e78f7-202">**Malware name**</span></span>

<span data-ttu-id="e78f7-203">보고서 보기로 돌아가려면 보고서 **보기를 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="e78f7-203">To go back to the report view, click **View report**.</span></span>

## <a name="sent-and-received-email-report"></a><span data-ttu-id="e78f7-204">보낸 메일 및 받은 전자 메일 보고서</span><span class="sxs-lookup"><span data-stu-id="e78f7-204">Sent and received email report</span></span>

<span data-ttu-id="e78f7-205">보낸 **및 받은 전자 메일 보고서에는** 맬웨어, 스팸, 메일 흐름 규칙(전송 규칙이라고도 함) 및 전자 메일이 서비스를 받은 후의 고급 맬웨어 검색에 대한 정보가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e78f7-205">The **Sent and received email** report contains information about malware, spam, mail flow rules (also known as transport rules), and advanced malware detections after email enters the service.</span></span> <span data-ttu-id="e78f7-206">자세한 내용은 보낸 및 [받은 전자 메일 보고서를 참조하세요.](view-mail-flow-reports.md#sent-and-received-email-report)</span><span class="sxs-lookup"><span data-stu-id="e78f7-206">For more information, see [Sent and received email report](view-mail-flow-reports.md#sent-and-received-email-report).</span></span>

## <a name="spam-detections-report"></a><span data-ttu-id="e78f7-207">스팸 검색 보고서</span><span class="sxs-lookup"><span data-stu-id="e78f7-207">Spam detections report</span></span>

<span data-ttu-id="e78f7-208">스팸 **검색 보고서에는** EOP에서 차단된 스팸 전자 메일 메시지가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="e78f7-208">The **Spam detections** report shows spam email messages that were blocked by EOP.</span></span> <span data-ttu-id="e78f7-209">메시지는 받는 사람별가 아치지 않은 개별적으로 계산됩니다.</span><span class="sxs-lookup"><span data-stu-id="e78f7-209">Messages are counted individually, not per recipient.</span></span> <span data-ttu-id="e78f7-210">예를 들어 동일한 스팸 메시지를 조직의 받는 사람 100명에게 전송한 경우 한 메시지로 계산됩니다.</span><span class="sxs-lookup"><span data-stu-id="e78f7-210">For example, if the same spam message was sent to 100 recipients in your organization, it counts as one message.</span></span>

<span data-ttu-id="e78f7-211">집계 보기를 사용하면 90일 동안 필터링이 가능한 한 세부 정보 표시에는 10일 필터링이 허용됩니다.</span><span class="sxs-lookup"><span data-stu-id="e78f7-211">The aggregate view allows for 90 days filtering, while the details table allows for 10 days filtering.</span></span>

<span data-ttu-id="e78f7-212">보고서를 보려면 보안 및 [준수 센터를 & 보고서](https://protection.office.com) **대시보드로** \> **이동하여 스팸** **검색을 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="e78f7-212">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Spam detections**.</span></span> <span data-ttu-id="e78f7-213">보고서로 직접 이동하려면 <https://protection.office.com/reportv2?id=SpamDetections> .</span><span class="sxs-lookup"><span data-stu-id="e78f7-213">To go directly to the report, open <https://protection.office.com/reportv2?id=SpamDetections>.</span></span>

![보고서 대시보드의 스팸 감지 위산 위과](../../media/spam-detections-report-widget.png)

<span data-ttu-id="e78f7-215">스팸 방지 보호 기능에 대한 자세한 내용은 [EOP의 스팸 방지 보호 기능을 참조하세요.](anti-spam-protection.md)</span><span class="sxs-lookup"><span data-stu-id="e78f7-215">For more information about anti-spam protection, see [Anti-spam protection in EOP](anti-spam-protection.md).</span></span>

### <a name="report-view-for-the-spam-detections-report"></a><span data-ttu-id="e78f7-216">스팸 검색 보고서 보기</span><span class="sxs-lookup"><span data-stu-id="e78f7-216">Report view for the Spam detections report</span></span>

<span data-ttu-id="e78f7-217">보고서 보기에서는 다음 차트를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e78f7-217">The following charts are available in the report view:</span></span>

- <span data-ttu-id="e78f7-218">**분석: 작업:** 다음과 같은 이벤트 유형이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="e78f7-218">**Break down by: Action**: The following event types are shown:</span></span>

  - <span data-ttu-id="e78f7-219">**스팸 콘텐츠 필터링됨**</span><span class="sxs-lookup"><span data-stu-id="e78f7-219">**Spam content filtered**</span></span>
  - <span data-ttu-id="e78f7-220">**스팸 IP 블록**</span><span class="sxs-lookup"><span data-stu-id="e78f7-220">**Spam IP block**</span></span>
  - <span data-ttu-id="e78f7-221">**스팸 봉투 블록**</span><span class="sxs-lookup"><span data-stu-id="e78f7-221">**Spam envelope block**</span></span>
  - <span data-ttu-id="e78f7-222">**스팸 DBEB 필터**: DBEB(디렉터리 기반 Edge 차단)</span><span class="sxs-lookup"><span data-stu-id="e78f7-222">**Spam DBEB filter**: Directory based edge blocking (DBEB)</span></span>

  <span data-ttu-id="e78f7-223">차트에서 하루(데이터 요소)을 가리치하면 해당 날짜에 차단된 항목 및 분류된 항목의 수를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e78f7-223">When you hover over a day (data point) in the chart, you can see how many items were blocked that day, as well as how those items are categorized.</span></span>

  ![스팸 검색 보고서의 작업 보기](../../media/spam-detections-report-action-view.png)

- <span data-ttu-id="e78f7-225">**아래로 나누기:** 다음지는 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="e78f7-225">**Break down by:Direction**: The following directions are shown:</span></span>

  - <span data-ttu-id="e78f7-226">**인바운드**</span><span class="sxs-lookup"><span data-stu-id="e78f7-226">**Inbound**</span></span>
  - <span data-ttu-id="e78f7-227">**아웃바운드**</span><span class="sxs-lookup"><span data-stu-id="e78f7-227">**Outbound**</span></span>

  ![스팸 감지 보고서 내의 방향 보기](../../media/spam-detections-report-direction-view.png)

<span data-ttu-id="e78f7-229">보고서 보기에서 **필터를** 클릭한 경우 다음 필터를 사용하여 결과를 수정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e78f7-229">If you click **Filters** in a report view, you can modify the results with the following filters:</span></span>

- <span data-ttu-id="e78f7-230">**시작 날짜** **및 끝 날짜**</span><span class="sxs-lookup"><span data-stu-id="e78f7-230">**Start date** and **End date**</span></span>
- <span data-ttu-id="e78f7-231">방향 값</span><span class="sxs-lookup"><span data-stu-id="e78f7-231">Direction values</span></span>
- <span data-ttu-id="e78f7-232">이벤트 유형 값</span><span class="sxs-lookup"><span data-stu-id="e78f7-232">Event type values</span></span>

### <a name="details-table-view-for-the-spam-detections-report"></a><span data-ttu-id="e78f7-233">스팸 검색 보고서의 세부 정보 표 보기</span><span class="sxs-lookup"><span data-stu-id="e78f7-233">Details table view for the Spam detections report</span></span>

<span data-ttu-id="e78f7-234">보고서 보기에서 **세부 정보 표를** 보기를 클릭하면 다음 정보가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="e78f7-234">If you click **View details table** in any report view, the following information is shown:</span></span>

- <span data-ttu-id="e78f7-235">**날짜**</span><span class="sxs-lookup"><span data-stu-id="e78f7-235">**Date**</span></span>
- <span data-ttu-id="e78f7-236">**보낸 사람 주소**</span><span class="sxs-lookup"><span data-stu-id="e78f7-236">**Sender address**</span></span>
- <span data-ttu-id="e78f7-237">**받는 사람 주소**</span><span class="sxs-lookup"><span data-stu-id="e78f7-237">**Recipient address**</span></span>
- <span data-ttu-id="e78f7-238">**이벤트 유형**</span><span class="sxs-lookup"><span data-stu-id="e78f7-238">**Event type**</span></span>
- <span data-ttu-id="e78f7-239">**작업**</span><span class="sxs-lookup"><span data-stu-id="e78f7-239">**Action**</span></span>
- <span data-ttu-id="e78f7-240">**제목**</span><span class="sxs-lookup"><span data-stu-id="e78f7-240">**Subject**</span></span>

<span data-ttu-id="e78f7-241">세부 정보 **표에서 필터를** 클릭한 경우 다음 필터를 사용하여 결과를 수정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e78f7-241">If you click **Filters** in a details table, you can modify the results with the following filters:</span></span>

- <span data-ttu-id="e78f7-242">**시작 날짜** **및 끝 날짜**</span><span class="sxs-lookup"><span data-stu-id="e78f7-242">**Start date** and **End date**</span></span>
- <span data-ttu-id="e78f7-243">방향 값</span><span class="sxs-lookup"><span data-stu-id="e78f7-243">Direction values</span></span>
- <span data-ttu-id="e78f7-244">이벤트 유형 값</span><span class="sxs-lookup"><span data-stu-id="e78f7-244">Event type values</span></span>

<span data-ttu-id="e78f7-245">보고서 보기로 돌아가려면 보고서 **보기를 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="e78f7-245">To go back to the report view, click **View report**.</span></span>

## <a name="spoof-detections-report"></a><span data-ttu-id="e78f7-246">스푸핑 감지 보고서</span><span class="sxs-lookup"><span data-stu-id="e78f7-246">Spoof detections report</span></span>

<span data-ttu-id="e78f7-247">**스푸핑 탐지 보고서에는** 검색된 스푸핑 메일 메시지의 수와 스푸핑 메일이 "좋은" 스푸핑하여 어떤 스푸핑도 가능합니다(합법적인 사업상의 이유로 스푸핑된 메일).</span><span class="sxs-lookup"><span data-stu-id="e78f7-247">The **Spoof detections** report shows how many spoof mail messages were detected, and of those, which ones were considered "good" (spoof mail done for legitimate business reasons).</span></span> <span data-ttu-id="e78f7-248">스푸핑에 대한 자세한 내용은 [EOP의 스푸핑 방지 보호 기능을 참조하세요.](anti-spoofing-protection.md)</span><span class="sxs-lookup"><span data-stu-id="e78f7-248">For more information about spoofing, see [Anti-spoofing protection in EOP](anti-spoofing-protection.md).</span></span>

<span data-ttu-id="e78f7-249">보고서의 집계 보기에서는 90일 동안의 필터링이 허용되는 한편, 세부 정보 보기에는 10일 동안만 필터링이 허용됩니다.</span><span class="sxs-lookup"><span data-stu-id="e78f7-249">The aggregate view of the report allows for 90 days of filtering, while the detail view only allows for ten days of filtering.</span></span>

<span data-ttu-id="e78f7-250">보고서를 보려면 준수 센터에서 [&, 보고서](https://protection.office.com) **대시보드로** \> **이동하여 스푸핑** **감지를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="e78f7-250">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Spoof detections**.</span></span> <span data-ttu-id="e78f7-251">보고서로 직접 이동하려면 <https://protection.office.com/reportv2?id=SpoofMailReport> .</span><span class="sxs-lookup"><span data-stu-id="e78f7-251">To go directly to the report, open <https://protection.office.com/reportv2?id=SpoofMailReport>.</span></span>

![보고서 대시보드의 스푸핑 감지 위산](../../media/spoof-detections-widget.png)

<span data-ttu-id="e78f7-253">차트에서 하루(데이터 요소)을 가리치면 특정 스푸핑 메일 메시지의 수를 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e78f7-253">When you hover over a day (data point) in the chart, you can see how many spoof mail messages came through.</span></span>

<span data-ttu-id="e78f7-254">필터를 클릭하고 다음 값 중에서 하나 이상을 **선택하여** 차트 및 세부 정보 표를 모두 필터링할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e78f7-254">You can filter both the chart and the details table by clicking **Filters** and selecting one or more of the following values:</span></span>

- <span data-ttu-id="e78f7-255">**시작 날짜** **및 끝 날짜**</span><span class="sxs-lookup"><span data-stu-id="e78f7-255">**Start date** and **End date**</span></span>

- <span data-ttu-id="e78f7-256">**정상 메일**</span><span class="sxs-lookup"><span data-stu-id="e78f7-256">**Good mail**</span></span>

- <span data-ttu-id="e78f7-257">**스팸으로 Caught**</span><span class="sxs-lookup"><span data-stu-id="e78f7-257">**Caught as spam**</span></span>

![스푸핑 감지 보고서의 보고서 보기](../../media/spoof-detections-report-view.png)

<span data-ttu-id="e78f7-259">세부 정보 **표를 보기를 클릭한 경우에는**다음 세부 정보를 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e78f7-259">If you click **View details table**, you can see the following details:</span></span>

- <span data-ttu-id="e78f7-260">**날짜**</span><span class="sxs-lookup"><span data-stu-id="e78f7-260">**Date**</span></span>
- <span data-ttu-id="e78f7-261">**스푸핑된 보낸 사람**</span><span class="sxs-lookup"><span data-stu-id="e78f7-261">**Spoofed sender**</span></span>
- <span data-ttu-id="e78f7-262">**True - 한 사람**</span><span class="sxs-lookup"><span data-stu-id="e78f7-262">**True sender**</span></span>
- <span data-ttu-id="e78f7-263">**보낸 사람 IP**</span><span class="sxs-lookup"><span data-stu-id="e78f7-263">**Sender IP**</span></span>
- <span data-ttu-id="e78f7-264">**작업**</span><span class="sxs-lookup"><span data-stu-id="e78f7-264">**Action**</span></span>
- <span data-ttu-id="e78f7-265">**메시지 수**</span><span class="sxs-lookup"><span data-stu-id="e78f7-265">**Message count**</span></span>

<span data-ttu-id="e78f7-266">보고서 보기로 돌아가려면 보고서 **보기를 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="e78f7-266">To go back to the report view, click **View report**.</span></span>

## <a name="threat-protection-status-report"></a><span data-ttu-id="e78f7-267">위협 방지 상태 보고서</span><span class="sxs-lookup"><span data-stu-id="e78f7-267">Threat protection status report</span></span>

<span data-ttu-id="e78f7-268">위협 **방지 상태 보고서는** EOP와 Office 365 ATP에서 모두 사용할 수 있습니다. 그러나 보고서에는 서로 다른 데이터가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e78f7-268">The **Threat protection status** report is available in both EOP and Office 365 ATP; however, the reports contain different data.</span></span> <span data-ttu-id="e78f7-269">예를 들어, EOP 고객은 전자 메일로 검색된 맬웨어에 대한 정보는 볼 수 있지만 [SharePoint Online, OneDrive 또는 Microsoft Teams에서](atp-for-spo-odb-and-teams.md)검색된 악성 파일에 대한 정보는 볼 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="e78f7-269">For example, EOP customers can view information about malware detected in email, but not information about [malicious files detected in SharePoint Online, OneDrive, or Microsoft Teams](atp-for-spo-odb-and-teams.md).</span></span>

<span data-ttu-id="e78f7-270">이 보고서에서는 맬웨어 방지 엔진, [ZAP(제로](zero-hour-auto-purge.md)아우스 자동 제거) 및 ATP 안전 링크, [ATP](atp-safe-attachments.md)안전 첨부 파일 및 ATP 피싱 방지와 같은 [ATP](atp-safe-links.md)기능과 같은 악의적인 콘텐츠가 포함된 고유한 전자 메일 [메시지의 집계된 개수를 제공합니다.](set-up-anti-phishing-policies.md)</span><span class="sxs-lookup"><span data-stu-id="e78f7-270">The report provides an aggregated count of unique email messages with malicious content, such as files or website addresses (URLs) that were blocked by the anti-malware engine, [zero-hour auto purge (ZAP)](zero-hour-auto-purge.md), and ATP features like [ATP Safe Links](atp-safe-links.md), [ATP Safe Attachments](atp-safe-attachments.md), and [ATP anti-phishing](set-up-anti-phishing-policies.md).</span></span> <span data-ttu-id="e78f7-271">이 정보를 사용하여 추세를 확인하거나 조직 정책을 조정해야 하는지를 결정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e78f7-271">You can use this information to identify trends or determine whether organization policies need adjustment.</span></span>

<span data-ttu-id="e78f7-272">보고서를 보려면 보안 센터에서 [보안 & 보고서](https://protection.office.com)대시보드로 **Reports** \> **이동하여 위협 방지** **상태를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="e78f7-272">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Threat protection status**.</span></span> <span data-ttu-id="e78f7-273">보고서로 직접 이동하려면 다음 URL 중 하나를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="e78f7-273">To go directly to the report, open one of the following URLs:</span></span>

- <span data-ttu-id="e78f7-274">Office 365 ATP: <https://protection.office.com/reportv2?id=ATPV2AggregateReport> .</span><span class="sxs-lookup"><span data-stu-id="e78f7-274">Office 365 ATP: <https://protection.office.com/reportv2?id=ATPV2AggregateReport>.</span></span>
- <span data-ttu-id="e78f7-275">EOP: <https://protection.office.com/reportv2?id=ATPAggregateLightReport></span><span class="sxs-lookup"><span data-stu-id="e78f7-275">EOP: <https://protection.office.com/reportv2?id=ATPAggregateLightReport></span></span>

![보고서 대시보드의 위협 방지 상태 위구](../../media/threat-protection-status-report-widget.png)

<span data-ttu-id="e78f7-277">기본적으로 차트는 지난 7일간의 데이터를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="e78f7-277">By default, the chart shows data for the past 7 days.</span></span> <span data-ttu-id="e78f7-278">필터를 **클릭하는 경우**90일 날짜 범위를 선택할 수 있습니다(평가판 구독은 30일로 제한될 수 있습니다).</span><span class="sxs-lookup"><span data-stu-id="e78f7-278">If you click **Filters**, you can select a 90 day date range (trial subscriptions might be limited to 30 days).</span></span> <span data-ttu-id="e78f7-279">세부 정보 표 보기에서는 30일 동안 필터링할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e78f7-279">The details table view allows filtering for 30 days.</span></span>

### <a name="report-view-for-the-threat-protection-status-report"></a><span data-ttu-id="e78f7-280">위협 방지 상태 보고서 보고서 보기</span><span class="sxs-lookup"><span data-stu-id="e78f7-280">Report view for the Threat protection status report</span></span>

<span data-ttu-id="e78f7-281">다음과 같은 보기를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e78f7-281">The following views are available:</span></span>

- <span data-ttu-id="e78f7-282">**다음 단계별로 데이터 보기:** 개요: 다음 검색 정보가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="e78f7-282">**View data by: Overview**: The following detection information is shown:</span></span>

  - <span data-ttu-id="e78f7-283">**전자 메일 맬웨어**</span><span class="sxs-lookup"><span data-stu-id="e78f7-283">**Email malware**</span></span>
  - <span data-ttu-id="e78f7-284">**전자 메일 피싱**</span><span class="sxs-lookup"><span data-stu-id="e78f7-284">**Email phish**</span></span>
  - <span data-ttu-id="e78f7-285">**콘텐츠 맬웨어**</span><span class="sxs-lookup"><span data-stu-id="e78f7-285">**Content malware**</span></span>

  ![위협 방지 상태 보고서의 개요 보기](../../media/threat-protection-status-report-overview-view.png)

- <span data-ttu-id="e78f7-287">**다음을 참조: Content(데이터 보기) \> 맬웨어**<sup>1:</sup>Office 365 ATP 조직에 대한 다음 정보가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="e78f7-287">**View data by: Content \> Malware**<sup>1</sup>: The following information is shown for Office 365 ATP organizations:</span></span>

  - <span data-ttu-id="e78f7-288">**맬웨어 방지 엔진**</span><span class="sxs-lookup"><span data-stu-id="e78f7-288">**Anti-malware engine**</span></span>
  - <span data-ttu-id="e78f7-289">**파일 소수자**</span><span class="sxs-lookup"><span data-stu-id="e78f7-289">**File detonation**</span></span>

  ![위협 방지 상태 보고서의 콘텐츠 맬웨어 보기](../../media/threat-protection-status-report-content-malware-view.png)

- <span data-ttu-id="e78f7-291">**분석: 검색 기술 및 데이터 보기:** **이메일 \> 피싱: 다음**정보가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="e78f7-291">**Break down by: Detection technology** and **View data by: Email \> Phish**: The following information is shown:</span></span>

  - <span data-ttu-id="e78f7-292">**ATP에서 생성된 URL 신뢰도**<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="e78f7-292">**ATP-generated URL reputation**<sup>1</sup></span></span>
  - <span data-ttu-id="e78f7-293">**고급 피싱 필터**</span><span class="sxs-lookup"><span data-stu-id="e78f7-293">**Advanced phish filter**</span></span>
  - <span data-ttu-id="e78f7-294">**스푸핑 방지: DMARC 실패**</span><span class="sxs-lookup"><span data-stu-id="e78f7-294">**Anti-spoof: DMARC failure**</span></span>
  - <span data-ttu-id="e78f7-295">**스푸핑 방지: 구성 내**</span><span class="sxs-lookup"><span data-stu-id="e78f7-295">**Anti-spoof: Intra-org**</span></span>
  - <span data-ttu-id="e78f7-296">**스푸핑 방지: 외부 도메인**</span><span class="sxs-lookup"><span data-stu-id="e78f7-296">**Anti-spoof: external domain**</span></span>
  - <span data-ttu-id="e78f7-297">**브랜드 가장**</span><span class="sxs-lookup"><span data-stu-id="e78f7-297">**Brand impersonation**</span></span>
  - <span data-ttu-id="e78f7-298">**도메인 가장**<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="e78f7-298">**Domain impersonation**<sup>1</sup></span></span>
  - <span data-ttu-id="e78f7-299">**EOP URL 신뢰도**</span><span class="sxs-lookup"><span data-stu-id="e78f7-299">**EOP URL reputation**</span></span>
  - <span data-ttu-id="e78f7-300">**일반 피싱 필터**</span><span class="sxs-lookup"><span data-stu-id="e78f7-300">**General phish filter**</span></span>
  - <span data-ttu-id="e78f7-301">**기타**</span><span class="sxs-lookup"><span data-stu-id="e78f7-301">**Others**</span></span>
  - <span data-ttu-id="e78f7-302">**피싱 ZAP**<sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="e78f7-302">**Phish ZAP**<sup>2</sup></span></span>
  - <span data-ttu-id="e78f7-303">**URL 표시**<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="e78f7-303">**URL detonation**<sup>1</sup></span></span>
  - <span data-ttu-id="e78f7-304">**사용자 가장**<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="e78f7-304">**User impersonation**<sup>1</sup></span></span>

  ![위협 방지 상태 보고서에서 피싱 전자 메일에 대한 감지 기술 보기](../../media/threat-protection-status-report-phishing-detection-tech-view.png)

- <span data-ttu-id="e78f7-306">**분석: 검색 기술 및 데이터 보기:** \*\*이메일 맬웨어: \> \*\*다음 정보가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="e78f7-306">**Break down by: Detection technology** and **View data by: Email \> Malware**: The following information is shown:</span></span>

  - <span data-ttu-id="e78f7-307">**ATP에서 생성한 파일 평명도**<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="e78f7-307">**ATP-generated file reputation**<sup>1</sup></span></span>
  - <span data-ttu-id="e78f7-308">**맬웨어 방지 엔진**<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="e78f7-308">**Anti-malware engine**<sup>1</sup></span></span>
  - <span data-ttu-id="e78f7-309">**맬웨어 방지 정책 파일 형식 차단**</span><span class="sxs-lookup"><span data-stu-id="e78f7-309">**Anti-malware policy file type block**</span></span>
  - <span data-ttu-id="e78f7-310">**파일 소수**<sup>자전</sup></span><span class="sxs-lookup"><span data-stu-id="e78f7-310">**File detonation**<sup>1</sup></span></span>
  - <span data-ttu-id="e78f7-311">**악성 파일 평뢰도**</span><span class="sxs-lookup"><span data-stu-id="e78f7-311">**Malicious file reputation**</span></span>
  - <span data-ttu-id="e78f7-312">**맬웨어 ZAP**<sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="e78f7-312">**Malware ZAP**<sup>2</sup></span></span>
  - <span data-ttu-id="e78f7-313">**기타**</span><span class="sxs-lookup"><span data-stu-id="e78f7-313">**Others**</span></span>

  ![위협 방지 상태 보고서에서 맬웨어에 대한 검색 기술 보기](../../media/threat-protection-status-report-malware-detection-tech-view.png)

- <span data-ttu-id="e78f7-315">**분석: 다음 단계에 따라 정책 유형** 및 **데이터 보기: 전자 메일 \> 피싱** 또는 **데이터 \> 보기:** 다음 정보가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="e78f7-315">**Break down by: Policy type** and **View data by: Email \> Phish** or **View data by: Email \> Malware**: The following information is shown:</span></span>

  - <span data-ttu-id="e78f7-316">**맬웨어 방지**</span><span class="sxs-lookup"><span data-stu-id="e78f7-316">**Anti-malware**</span></span>
  - <span data-ttu-id="e78f7-317">**안전한 첨부 파일**<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="e78f7-317">**Safe Attachment**<sup>1</sup></span></span>
  - <span data-ttu-id="e78f7-318">**피싱 방지**</span><span class="sxs-lookup"><span data-stu-id="e78f7-318">**Anti-phish**</span></span>
  - <span data-ttu-id="e78f7-319">**스팸 방지**</span><span class="sxs-lookup"><span data-stu-id="e78f7-319">**Anti-spam**</span></span>
  - <span data-ttu-id="e78f7-320">**메일 흐름 규칙(전송** 규칙이라고도 함)</span><span class="sxs-lookup"><span data-stu-id="e78f7-320">**Mail flow rule** (also known as a transport rule)</span></span>
  - <span data-ttu-id="e78f7-321">**기타**</span><span class="sxs-lookup"><span data-stu-id="e78f7-321">**Others**</span></span>

  ![위협 방지 상태 보고서에서 피싱 전자 메일에 대한 정책 유형 보기](../../media/threat-protection-status-report-phishing-policy-type-view.png)

- <span data-ttu-id="e78f7-323">**단계별로 분석: 전자 메일 피싱** \*\*또는 \> \*\* 데이터 보기: 전자 메일 \*\*맬웨어: \> \*\*다음 정보가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="e78f7-323">**Break down by: Delivery status** and **View data by: Email \> Phish** or **View data by: Email \> Malware**: The following information is shown:</span></span>

  - <span data-ttu-id="e78f7-324">**배달하지 못함**</span><span class="sxs-lookup"><span data-stu-id="e78f7-324">**Delivery failed**</span></span>
  - <span data-ttu-id="e78f7-325">**놓기**</span><span class="sxs-lookup"><span data-stu-id="e78f7-325">**Dropped**</span></span>
  - <span data-ttu-id="e78f7-326">**Forwarded**</span><span class="sxs-lookup"><span data-stu-id="e78f7-326">**Forwarded**</span></span>
  - <span data-ttu-id="e78f7-327">**호스트된 사서함: 사용자 지정 폴더**</span><span class="sxs-lookup"><span data-stu-id="e78f7-327">**Hosted mailbox: Custom folder**</span></span>
  - <span data-ttu-id="e78f7-328">**Hosted mailbox: 삭제된 항목**</span><span class="sxs-lookup"><span data-stu-id="e78f7-328">**Hosted mailbox: Deleted items**</span></span>
  - <span data-ttu-id="e78f7-329">**호스트된 사서함: 받은 편지함**</span><span class="sxs-lookup"><span data-stu-id="e78f7-329">**Hosted mailbox: Inbox**</span></span>
  - <span data-ttu-id="e78f7-330">**Hosted mailbox: Junk**</span><span class="sxs-lookup"><span data-stu-id="e78f7-330">**Hosted mailbox: Junk**</span></span>
  - <span data-ttu-id="e78f7-331">**온-프레미스 서버: 전달됨**</span><span class="sxs-lookup"><span data-stu-id="e78f7-331">**On-premises server: Delivered**</span></span>
  - <span data-ttu-id="e78f7-332">**격리**</span><span class="sxs-lookup"><span data-stu-id="e78f7-332">**Quarantine**</span></span>

  ![위협 방지 상태 보고서에서 피싱 전자 메일에 대한 배달 상태 보기](../../media/threat-protection-status-report-phishing-delivery-status-view.png)

<span data-ttu-id="e78f7-334"><sup>1</sup> Office 365 ATP만</span><span class="sxs-lookup"><span data-stu-id="e78f7-334"><sup>1</sup> Office 365 ATP only</span></span>

<span data-ttu-id="e78f7-335"><sup>독립</sup> 실행형 EOP에서는 2시간제 자동 제거(ZAP)를 사용할 수 없습니다(Exchange Online 사서함에서만 작동).</span><span class="sxs-lookup"><span data-stu-id="e78f7-335"><sup>2</sup> Zero-hour auto purge (ZAP) isn't available in standalone EOP (it only works in Exchange Online mailboxes).</span></span>

<span data-ttu-id="e78f7-336">필터를 **클릭하면 다음과**같은 필터를 사용하여 보고서를 수정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e78f7-336">If you click **Filters**, you can modify the report with the following filters:</span></span>

- <span data-ttu-id="e78f7-337">**시작 날짜** **및 끝 날짜**</span><span class="sxs-lookup"><span data-stu-id="e78f7-337">**Start date** and **End date**</span></span>
- <span data-ttu-id="e78f7-338">검색 값</span><span class="sxs-lookup"><span data-stu-id="e78f7-338">Detection value</span></span>
- <span data-ttu-id="e78f7-339">**보호(Office** 365 ATP만 해당): **ATP 또는** **EOP**</span><span class="sxs-lookup"><span data-stu-id="e78f7-339">**Protected by** (Office 365 ATP only): **ATP** or **EOP**.</span></span> <span data-ttu-id="e78f7-340">콘텐츠 맬웨어: 데이터 보기에서는 필터링 가능한 **속성을 사용할 수 \> 없습니다.**</span><span class="sxs-lookup"><span data-stu-id="e78f7-340">Note that this filterable property isn't available in **View data by: Content \> Malware**.</span></span>

### <a name="details-table-view-for-the-threat-protection-status-report"></a><span data-ttu-id="e78f7-341">위협 방지 상태 보고서의 세부 정보 표 보기</span><span class="sxs-lookup"><span data-stu-id="e78f7-341">Details table view for the Threat protection status report</span></span>

<span data-ttu-id="e78f7-342">세부 정보 **표를 보기를**클릭하면 표시되는 정보는 검색 하고 있는 차트에 따라 달라지게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e78f7-342">If you click **View details table**, the information that's shown depends on the chart you were looking at:</span></span>

- <span data-ttu-id="e78f7-343">**다음을 참조: Content(데이터 보기) \> 맬웨어**:</span><span class="sxs-lookup"><span data-stu-id="e78f7-343">**View data by: Content \> Malware**:</span></span>

  - <span data-ttu-id="e78f7-344">**날짜**</span><span class="sxs-lookup"><span data-stu-id="e78f7-344">**Date**</span></span>
  - <span data-ttu-id="e78f7-345">**위치**</span><span class="sxs-lookup"><span data-stu-id="e78f7-345">**Location**</span></span>
  - <span data-ttu-id="e78f7-346">**지시문**</span><span class="sxs-lookup"><span data-stu-id="e78f7-346">**Directed by**</span></span>
  - <span data-ttu-id="e78f7-347">**맬웨어 이름**</span><span class="sxs-lookup"><span data-stu-id="e78f7-347">**Malware name**</span></span>

- <span data-ttu-id="e78f7-348">**View data by: Overview**: No **View details table** button is available.</span><span class="sxs-lookup"><span data-stu-id="e78f7-348">**View data by: Overview**: No **View details table** button is available.</span></span>

- <span data-ttu-id="e78f7-349">기타 모든 차트:</span><span class="sxs-lookup"><span data-stu-id="e78f7-349">All other charts:</span></span>

  - <span data-ttu-id="e78f7-350">**날짜**</span><span class="sxs-lookup"><span data-stu-id="e78f7-350">**Date**</span></span>
  - <span data-ttu-id="e78f7-351">**제목**</span><span class="sxs-lookup"><span data-stu-id="e78f7-351">**Subject**</span></span>
  - <span data-ttu-id="e78f7-352">**보낸 사람**</span><span class="sxs-lookup"><span data-stu-id="e78f7-352">**Sender**</span></span>
  - <span data-ttu-id="e78f7-353">**받는 사람**</span><span class="sxs-lookup"><span data-stu-id="e78f7-353">**Recipients**</span></span>
  - <span data-ttu-id="e78f7-354">**감지함**</span><span class="sxs-lookup"><span data-stu-id="e78f7-354">**Detected by**</span></span>
  - <span data-ttu-id="e78f7-355">**배달 상태**</span><span class="sxs-lookup"><span data-stu-id="e78f7-355">**Delivery status**</span></span>
  - <span data-ttu-id="e78f7-356">**위출 출스**</span><span class="sxs-lookup"><span data-stu-id="e78f7-356">**Source of compromise**</span></span>

<span data-ttu-id="e78f7-357">필터를 **클릭하면 다음과**같은 필터를 사용하여 보고서를 수정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e78f7-357">If you click **Filters**, you can modify the report with the following filters:</span></span>

- <span data-ttu-id="e78f7-358">**시작 날짜** **및 끝 날짜**</span><span class="sxs-lookup"><span data-stu-id="e78f7-358">**Start date** and **End date**</span></span>
- <span data-ttu-id="e78f7-359">검색 값</span><span class="sxs-lookup"><span data-stu-id="e78f7-359">Detection value</span></span>
- <span data-ttu-id="e78f7-360">**보호(Office** 365 ATP만 해당): **ATP 또는** **EOP**</span><span class="sxs-lookup"><span data-stu-id="e78f7-360">**Protected by** (Office 365 ATP only): **ATP** or **EOP**.</span></span> <span data-ttu-id="e78f7-361">콘텐츠 맬웨어: 데이터 보기에서는 필터링 가능한 **속성을 사용할 수 \> 없습니다.**</span><span class="sxs-lookup"><span data-stu-id="e78f7-361">Note that this filterable property isn't available in **View data by: Content \> Malware**.</span></span>

## <a name="top-malware-report"></a><span data-ttu-id="e78f7-362">상위 맬웨어 보고서</span><span class="sxs-lookup"><span data-stu-id="e78f7-362">Top malware report</span></span>

<span data-ttu-id="e78f7-363">상위 **맬웨어 보고서는** EOP의 맬웨어 방지 보호에서 검색된 다양한 종류의 [맬웨어를 보여주는 기능입니다.](anti-malware-protection.md)</span><span class="sxs-lookup"><span data-stu-id="e78f7-363">The **Top malware** report shows the various kinds of malware that was detected by [anti-malware protection in EOP](anti-malware-protection.md).</span></span>

<span data-ttu-id="e78f7-364">보고서를 보려면 규정 준수 센터에서 [보안 & 보고서](https://protection.office.com)대시보드로 **이동한** \> **후 상위** **맬웨어를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="e78f7-364">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Top malware**.</span></span> <span data-ttu-id="e78f7-365">보고서로 직접 이동하려면 <https://protection.office.com/reportv2?id=TopMalware> .</span><span class="sxs-lookup"><span data-stu-id="e78f7-365">To go directly to the report, open <https://protection.office.com/reportv2?id=TopMalware>.</span></span>

![보고서 대시보드의 상위 맬웨어 위조](../../media/top-malware-report-widget.png)

<span data-ttu-id="e78f7-367">원형 차트에서 WEDGE를 가리치면 맬웨어의 이름을 보고 해당 맬웨어가 포함된 경우 감지된 메시지 수를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e78f7-367">When you hover over a wedge in the pie chart, you can see the name of a kind of malware and how many messages were detected as having that malware.</span></span>

![상위 맬웨어 보고서 보기](../../media/top-malware-report-view.png)

<span data-ttu-id="e78f7-369">세부 정보 **표를 보기를 클릭한 경우에는**다음 세부 정보를 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e78f7-369">If you click **View details table**, you can see the following details:</span></span>

- <span data-ttu-id="e78f7-370">**상위 맬웨어**</span><span class="sxs-lookup"><span data-stu-id="e78f7-370">**Top malware**</span></span>
- <span data-ttu-id="e78f7-371">**개수**</span><span class="sxs-lookup"><span data-stu-id="e78f7-371">**Count**</span></span>

<span data-ttu-id="e78f7-372">보고서 보기 **나서 보기 보기에서** 필터를 클릭하는 경우 시작 날짜와 종료 날짜로 날짜 **범위를** 지정할 **수 있습니다.**</span><span class="sxs-lookup"><span data-stu-id="e78f7-372">If you click **Filters** in the report view or details table view, you can specify a date range with **Start date** and **End date**.</span></span>

## <a name="url-threat-protection-report"></a><span data-ttu-id="e78f7-373">URL 위협 방지 보고서</span><span class="sxs-lookup"><span data-stu-id="e78f7-373">URL threat protection report</span></span>

<span data-ttu-id="e78f7-374">**URL 위협 방지 보고서는** Office 365 ATP(Advanced Threat Protection)에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e78f7-374">The **URL threat protection report** is available in Office 365 Advanced Threat Protection (ATP).</span></span> <span data-ttu-id="e78f7-375">자세한 내용은 URL 위협 [방지 보고서를 참조하세요.](view-reports-for-atp.md#url-threat-protection-report)</span><span class="sxs-lookup"><span data-stu-id="e78f7-375">For more information, see [URL threat protection report](view-reports-for-atp.md#url-threat-protection-report).</span></span>

## <a name="user-reported-messages-report"></a><span data-ttu-id="e78f7-376">사용자가 보고한 메시지 보고서</span><span class="sxs-lookup"><span data-stu-id="e78f7-376">User-reported messages report</span></span>

<span data-ttu-id="e78f7-377">사용자가 **보고한 메시지 보고서에는** 사용자가 보고서 메시지 추가 기능을 사용하여 정크 메일, 피싱 시도 또는 좋은 메일로 보고한 전자 [메일 메시지에 대한 정보가 표시됩니다.](https://docs.microsoft.com/microsoft-365/security/office-365-security/enable-the-report-message-add-in)</span><span class="sxs-lookup"><span data-stu-id="e78f7-377">The **User-reported messages** report shows information about email messages that users have reported as junk, phishing attempts, or good mail by using the [Report Message add-in](https://docs.microsoft.com/microsoft-365/security/office-365-security/enable-the-report-message-add-in).</span></span>

<span data-ttu-id="e78f7-378">배달 상시 예정(스팸 정책 예외 또는 조직에 대해 구성된 메일 흐름 규칙과 같은 배달 이유 포함)에 대해 정보가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="e78f7-378">Details are available for each message, including the delivery reason, such a spam policy exception or mail flow rule configured for your organization.</span></span> <span data-ttu-id="e78f7-379">세부 정보를 보려면 사용자 보고서 목록에서 항목을 선택한 다음 요약 및 세부 정보 **탭에서 정보를** **확인합니다.**</span><span class="sxs-lookup"><span data-stu-id="e78f7-379">To view details, select an item in the user-reports list, and then view the information on the **Summary** and **Details** tabs.</span></span>

![사용자 보고 메시지 보고서에는 정크 메일 또는 피싱 시도가 아님으로 지정된 메시지가 표시됩니다.](../../media/ad5e9a3d-b833-419c-bcc9-3425d9604ead.png)

<span data-ttu-id="e78f7-381">이 보고서를 보려면 보안 [서비스 & 센터에서](https://protection.office.com)다음 중 하나를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="e78f7-381">To view this report, in the [Security & Compliance Center](https://protection.office.com), do one of the following:</span></span>

- <span data-ttu-id="e78f7-382">위협 **관리 대시보드** \> **Dashboard** \> **사용자가 보고한 메시지로 이동합니다.**</span><span class="sxs-lookup"><span data-stu-id="e78f7-382">Go to **Threat management** \> **Dashboard** \> **User-reported messages**.</span></span>

- <span data-ttu-id="e78f7-383">위협 **관리 사용자가** \> **보고한** \> **메시지로 이동합니다.**</span><span class="sxs-lookup"><span data-stu-id="e78f7-383">Go to **Threat management** \> **Review** \> **User-reported messages**.</span></span>

![In the Security & Compliance Center, choose Threat management \> Review \> User reported messages](../../media/e372c57c-1414-4616-957b-bc933b8c8711.png)

> [!IMPORTANT]
> <span data-ttu-id="e78f7-385">사용자가 보고한 메시지 보고가 제대로 작동하려면 Office 365 **환경에 대해 감사** 로깅을 설정되어 있는 상태가 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e78f7-385">In order for the User-reported messages report to work correctly, **audit logging must be turned on** for your Office 365 environment.</span></span> <span data-ttu-id="e78f7-386">일반적으로 감사 로그 역할이 Exchange Online에 할당된 누누가 이 작업을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="e78f7-386">This is typically done by someone who has the Audit Logs role assigned in Exchange Online.</span></span> <span data-ttu-id="e78f7-387">자세한 내용은 [Microsoft 365 감사 로그 검색 설정 또는 해제를 참조하세요.](https://docs.microsoft.com/microsoft-365/compliance/turn-audit-log-search-on-or-off)</span><span class="sxs-lookup"><span data-stu-id="e78f7-387">For more information, see [Turn Microsoft 365 audit log search on or off](https://docs.microsoft.com/microsoft-365/compliance/turn-audit-log-search-on-or-off).</span></span>

## <a name="what-permissions-are-needed-to-view-these-reports"></a><span data-ttu-id="e78f7-388">이러한 보고서를 보는 데 필요한 권한은 무엇입니까?</span><span class="sxs-lookup"><span data-stu-id="e78f7-388">What permissions are needed to view these reports?</span></span>

<span data-ttu-id="e78f7-389">보고서를 보고 사용하려면 준수 센터 및 Exchange Online에서 보안 그룹의 & **합니다.**</span><span class="sxs-lookup"><span data-stu-id="e78f7-389">To view and use the reports, you need to be a member of the specified role group in the Security & Compliance Center **and** in Exchange Online.</span></span>

- <span data-ttu-id="e78f7-390">새 & 센터에서 다음 역할 그룹 중 하나의 구성원이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e78f7-390">In the Security & Compliance Center, you need to be a member of one of the following role groups:</span></span>

  <span data-ttu-id="e78f7-391">-Organization Management -Security Administrator (Azure Active Directory 관리 센터에서도 이 [작업을 수행할 수 있나요)](https://aad.portal.azure.com) - 보안 읽기 권한자</span><span class="sxs-lookup"><span data-stu-id="e78f7-391">-Organization Management -Security Administrator (you can also do this in the [Azure Active Directory admin center](https://aad.portal.azure.com) -Security Reader</span></span>

  <span data-ttu-id="e78f7-392">자세한 내용은 [보안 및 준수 센터의 사용 권한](https://docs.microsoft.com/microsoft-365/security/office-365-security/permissions-in-the-security-and-compliance-center)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="e78f7-392">For more information, see [Permissions in the Security & Compliance Center](https://docs.microsoft.com/microsoft-365/security/office-365-security/permissions-in-the-security-and-compliance-center).</span></span>

- <span data-ttu-id="e78f7-393">Exchange Online에서는 다음 역할 그룹 중 하나의 구성원이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e78f7-393">In Exchange Online, you need to be a member of one of the following role groups:</span></span>

  <span data-ttu-id="e78f7-394">-Organization Management -View-only Organization Management -View-Only Recipients -Compliance Management</span><span class="sxs-lookup"><span data-stu-id="e78f7-394">-Organization Management -View-only Organization Management -View-Only Recipients -Compliance Management</span></span>

<span data-ttu-id="e78f7-395">자세한 내용은 [Exchange Online의 사용 권한을 사용하고](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo) [Exchange Online의 역할 그룹 관리를 참조하세요.](https://docs.microsoft.com/Exchange/permissions-exo/role-groups)</span><span class="sxs-lookup"><span data-stu-id="e78f7-395">For more information, see [Permissions in Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo) and [Manage role groups in Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/role-groups).</span></span>

## <a name="what-if-the-reports-arent-showing-data"></a><span data-ttu-id="e78f7-396">보고서에 데이터가 표시되지 않는 경우 어떻게 해야 할까요?</span><span class="sxs-lookup"><span data-stu-id="e78f7-396">What if the reports aren't showing data?</span></span>

<span data-ttu-id="e78f7-397">보고서에 데이터가 표시되지 않으면 정책이 올바르게 설정되었는지 다시 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="e78f7-397">If you are not seeing data in your reports, double-check that your policies are set up correctly.</span></span> <span data-ttu-id="e78f7-398">자세한 내용은 [위협으로부터 보호를 참조하세요.](protect-against-threats.md)</span><span class="sxs-lookup"><span data-stu-id="e78f7-398">To learn more, see [Protect against threats](protect-against-threats.md).</span></span>

## <a name="related-topics"></a><span data-ttu-id="e78f7-399">관련 항목</span><span class="sxs-lookup"><span data-stu-id="e78f7-399">Related topics</span></span>

[<span data-ttu-id="e78f7-400">EOP의 스팸 방지 및 맬웨어 방지 보호 기능</span><span class="sxs-lookup"><span data-stu-id="e78f7-400">Anti-spam and anti-malware protection in EOP</span></span>](anti-spam-and-anti-malware-protection.md)

[<span data-ttu-id="e78f7-401">보안 및 준수 센터의 스마트 보고서 및 인사이트</span><span class="sxs-lookup"><span data-stu-id="e78f7-401">Smart reports and insights in the Security & Compliance Center</span></span>](reports-and-insights-in-security-and-compliance.md)

[<span data-ttu-id="e78f7-402">보안 및 준수 센터에서 & 보고서 보기</span><span class="sxs-lookup"><span data-stu-id="e78f7-402">View mail flow reports in the Security & Compliance Center</span></span>](view-mail-flow-reports.md)

[<span data-ttu-id="e78f7-403">Office 365 Advanced Threat Protection 보고서 보기</span><span class="sxs-lookup"><span data-stu-id="e78f7-403">View reports for Office 365 Advanced Threat Protection</span></span>](view-reports-for-atp.md)
