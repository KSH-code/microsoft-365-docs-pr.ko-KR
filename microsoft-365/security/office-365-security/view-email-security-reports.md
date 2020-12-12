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
description: 조직에 대한 전자 메일 보안 보고서를 찾아 사용하는 방법에 대해 자세히 알아보습니다. 전자 메일 보안 보고서는 보안 및 준수 센터에서 & 있습니다.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: e98e59d39744d67427a272f456a03fc123034aa7
ms.sourcegitcommit: 0a8b0186cc041db7341e57f375d0d010b7682b7d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/11/2020
ms.locfileid: "49659480"
---
# <a name="view-email-security-reports-in-the-security--compliance-center"></a><span data-ttu-id="08b13-104">보안 및 준수 센터의 전자 메일 보안 보고서 보기</span><span class="sxs-lookup"><span data-stu-id="08b13-104">View email security reports in the Security & Compliance Center</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="08b13-105">Microsoft 365의 스팸 [방지&](https://protection.office.com) 맬웨어 방지 및 암호화 기능과 같은 전자 메일 보안 기능이 조직을 보호하는 방법을 볼 수 있도록 보안 및 준수 센터에서 다양한 보고서를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="08b13-105">A variety of reports are available in the [Security & Compliance Center](https://protection.office.com) to help you see how email security features, such as anti-spam, anti-malware, and encryption features in Microsoft 365 are protecting your organization.</span></span> <span data-ttu-id="08b13-106">필요한 사용 [](#what-permissions-are-needed-to-view-these-reports)권한이 있는 경우 보고서 대시보드로 & 보안 및 준수 센터에서 이러한 보고서를 볼 **수** \> **있습니다.**</span><span class="sxs-lookup"><span data-stu-id="08b13-106">If you have the [necessary permissions](#what-permissions-are-needed-to-view-these-reports), you can view these reports in the Security & Compliance Center by going to **Reports** \> **Dashboard**.</span></span> <span data-ttu-id="08b13-107">보고서 대시보드로 직접 이동하기 위해 를 <https://protection.office.com/insightdashboard> 열습니다.</span><span class="sxs-lookup"><span data-stu-id="08b13-107">To go directly to the Reports dashboard, open <https://protection.office.com/insightdashboard>.</span></span>

![보안 및 준수 & 대시보드 보고](../../media/6b213d34-adbb-44af-8549-be9a7e2db087.png)

## <a name="compromised-users-report"></a><span data-ttu-id="08b13-109">손상된 사용자 보고서</span><span class="sxs-lookup"><span data-stu-id="08b13-109">Compromised users report</span></span>

> [!NOTE]
> <span data-ttu-id="08b13-110">이 보고서는 Exchange Online 사서함이 있는 Microsoft 365 조직에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="08b13-110">This report is available in Microsoft 365 organizations with Exchange Online mailboxes.</span></span> <span data-ttu-id="08b13-111">독립 실행형 EOP(Exchange Online Protection) 조직에서는 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="08b13-111">It's not available in standalone Exchange Online Protection (EOP) organizations.</span></span>

<span data-ttu-id="08b13-112">손상된 **사용자 보고서에는** 지난 7일 이내에  의심스러우거나  제한된 것으로 표시된 사용자 계정의 수가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="08b13-112">The **Compromised users** report shows shows the number of user accounts that were marked as **Suspicious** or **Restricted** within the last 7 days.</span></span> <span data-ttu-id="08b13-113">이러한 상태 중 하나에 있는 계정은 문제가 발생하거나 손상된 상태입니다.</span><span class="sxs-lookup"><span data-stu-id="08b13-113">Accounts in either of these states are problematic or even compromised.</span></span> <span data-ttu-id="08b13-114">자주 사용할 경우 보고서를 사용하여 의심스러우거나 제한된 계정에서 스파이크 및 추세를 파악할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="08b13-114">With frequent use, you can use the report to spot spikes, and even trends, in suspicious or restricted accounts.</span></span> <span data-ttu-id="08b13-115">손상된 사용자에 대한 자세한 내용은 손상된 전자 메일 계정에 응답을 [참조하세요.](responding-to-a-compromised-email-account.md)</span><span class="sxs-lookup"><span data-stu-id="08b13-115">For more information about compromised users, see [Responding to a compromised email account](responding-to-a-compromised-email-account.md).</span></span>

![보고서 대시보드에서 손상된 사용자 위젯](../../media/compromised-users-report-widget.png)

<span data-ttu-id="08b13-117">집계 보기는 지난 90일 동안의 데이터를 표시하고 세부 정보 보기에는 지난 30일간의 데이터가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="08b13-117">The aggregate view shows data for the last 90 days and the detail view shows data for the last 30 days.</span></span>

<span data-ttu-id="08b13-118">보고서를 표시하려면 보안 & 준수 센터를 열고 [보고서](https://protection.office.com)대시보드로 이동하여 손상된  \>  **사용자를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="08b13-118">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Compromised users**.</span></span> <span data-ttu-id="08b13-119">보고서로 직접 이동하기 위해 를 열 수 <https://protection.office.com/reportv2?id=CompromisedUsers> 있습니다.</span><span class="sxs-lookup"><span data-stu-id="08b13-119">To go directly to the report, open <https://protection.office.com/reportv2?id=CompromisedUsers>.</span></span>

<span data-ttu-id="08b13-120">필터를 클릭하고 다음 값 중 하나  이상을 선택하여 차트와 세부 정보 테이블을 모두 필터링할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="08b13-120">You can filter both the chart and the details table by clicking **Filters** and selecting one or more of the following values:</span></span>

- <span data-ttu-id="08b13-121">**시작 날짜** 및 **종료 날짜**</span><span class="sxs-lookup"><span data-stu-id="08b13-121">**Start date** and **End date**</span></span>

- <span data-ttu-id="08b13-122">**의심스러운**: 사용자 계정이 의심스러운 전자 메일을 보냈고 전자 메일을 보내지 못하도록 제한될 위험이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="08b13-122">**Suspicious**: The user account has sent suspicious email and is at risk of being restricted from sending email.</span></span>

- <span data-ttu-id="08b13-123">**제한**: 사용자 계정이 의심스러운 패턴으로 인해 전자 메일을 보내지 못하도록 제한되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="08b13-123">**Restricted**: The user account has been restricted from sending email due to highly suspicious patterns.</span></span>

![손상된 사용자 보고서의 보고서 보기](../../media/compromised-users-report-activity-view.png)

<span data-ttu-id="08b13-125">세부 정보 표 보기를 **클릭하면** 다음 세부 정보를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="08b13-125">If you click **View details table**, you can see the following details:</span></span>

- <span data-ttu-id="08b13-126">**만들기 시간**</span><span class="sxs-lookup"><span data-stu-id="08b13-126">**Creation time**</span></span>
- <span data-ttu-id="08b13-127">**사용자 ID**</span><span class="sxs-lookup"><span data-stu-id="08b13-127">**User ID**</span></span>
- <span data-ttu-id="08b13-128">**작업**</span><span class="sxs-lookup"><span data-stu-id="08b13-128">**Action**</span></span>

<span data-ttu-id="08b13-129">보고서 보기로 돌아가려면 보고서 **보기를 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="08b13-129">To go back to the report view, click **View report**.</span></span>

## <a name="encryption-report"></a><span data-ttu-id="08b13-130">암호화 보고서</span><span class="sxs-lookup"><span data-stu-id="08b13-130">Encryption report</span></span>

<span data-ttu-id="08b13-131">암호화 **보고서는** EOP(Exchange Online 사서함이 있는 구독 또는 Exchange Online 사서함이 없는 독립 실행형 EOP)에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="08b13-131">The **Encryption report** is available in EOP (subscriptions with mailboxes in Exchange Online or standalone EOP without Exchange Online mailboxes).</span></span> <span data-ttu-id="08b13-132">조직의 보안 팀은 이 보고서의 정보를 사용하여 패턴을 식별하고 중요한 전자 메일 메시지에 대한 정책을 자동으로 적용하거나 조정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="08b13-132">Your organization's security team can use information in this report to identify patterns and proactively apply or adjust policies for sensitive email messages.</span></span> <span data-ttu-id="08b13-133">예를 들어,</span><span class="sxs-lookup"><span data-stu-id="08b13-133">For example:</span></span>

- <span data-ttu-id="08b13-134">사용자가 암호화한 전자 메일 메시지가 많은 경우 암호화 정책을 추가하여 특정 사용 사례에 대한 암호화를 자동화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="08b13-134">If you see a high number of email messages encrypted by users, you might want to add an encryption policy to automate encryption for certain use cases.</span></span> <span data-ttu-id="08b13-135">자세한 내용은 [Microsoft 365에서](../../compliance/define-mail-flow-rules-to-encrypt-email.md)전자 메일 메시지를 암호화하는 메일 흐름 규칙 정의를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="08b13-135">For more information, see [Define mail flow rules to encrypt email messages in Microsoft 365](../../compliance/define-mail-flow-rules-to-encrypt-email.md).</span></span>

- <span data-ttu-id="08b13-136">여러 암호화 템플릿을 사용할 수 있지만 아무도 사용하지 않을 경우 사용자에게 기능 교육이 필요한지 여부를 탐색할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="08b13-136">If you have a number of encryption templates available but no one is using them, you might explore whether users need feature training.</span></span>

<span data-ttu-id="08b13-137">집계 보기에서는 지난 90일 동안의 필터링을 허용하고 세부 정보 보기에서는 10일 동안 필터링을 허용합니다.</span><span class="sxs-lookup"><span data-stu-id="08b13-137">The aggregate view allows filtering for the last 90 days, while the detail view allows filtering for 10 days.</span></span>

<span data-ttu-id="08b13-138">보고서를 표시하려면 보안 및 준수 [센터를 &](https://protection.office.com) **보고서** 대시보드로 이동하여 암호화 \>  **보고서를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="08b13-138">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Encryption report**.</span></span> <span data-ttu-id="08b13-139">보고서로 직접 이동하기 위해 를 열 수 <https://protection.office.com/reportv2?id=EncryptionReport> 있습니다.</span><span class="sxs-lookup"><span data-stu-id="08b13-139">To go directly to the report, open <https://protection.office.com/reportv2?id=EncryptionReport>.</span></span>

<span data-ttu-id="08b13-140">암호화에 대한 자세한 내용은 [Microsoft 365의](../../compliance/email-encryption.md)전자 메일 암호화를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="08b13-140">To learn more about encryption, see [Email encryption in Microsoft 365](../../compliance/email-encryption.md).</span></span>

### <a name="report-view-for-the-encryption-report"></a><span data-ttu-id="08b13-141">암호화 보고서에 대한 보고서 보기</span><span class="sxs-lookup"><span data-stu-id="08b13-141">Report view for the Encryption report</span></span>

<span data-ttu-id="08b13-142">차트에서 다음 필터를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="08b13-142">You can use the following filters on the chart:</span></span>

- <span data-ttu-id="08b13-143">**다음을 통해 데이터 보기: 메시지** 암호화 보고서 및 세분화 **방법: 암호화** 방법: 다음 암호화 방법을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="08b13-143">**View data by: Message Encryption Report** and **Break down by: Encryption method**: The following encryption methods are available:</span></span>

  - <span data-ttu-id="08b13-144">**사용자에 의해 암호화**</span><span class="sxs-lookup"><span data-stu-id="08b13-144">**Encryption by user**</span></span>
  - <span data-ttu-id="08b13-145">**정책에 따라 암호화**</span><span class="sxs-lookup"><span data-stu-id="08b13-145">**Encryption by policy**</span></span>

  <span data-ttu-id="08b13-146">필터를 **클릭하면** 다음 필터를 사용하여 차트를 수정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="08b13-146">If you click **Filters**, you can modify the chart with the following filters:</span></span>

  - <span data-ttu-id="08b13-147">**시작 날짜** 및 **종료 날짜**</span><span class="sxs-lookup"><span data-stu-id="08b13-147">**Start date** and **End date**</span></span>
  - <span data-ttu-id="08b13-148">암호화 방법</span><span class="sxs-lookup"><span data-stu-id="08b13-148">Encryption method.</span></span>
  - <span data-ttu-id="08b13-149">암호화 서식 파일.</span><span class="sxs-lookup"><span data-stu-id="08b13-149">Encryption template.</span></span>

- <span data-ttu-id="08b13-150">**다음을 통해 데이터 보기: 메시지 암호화 보고서** 및 다음으로 세분화: **암호화** 템플릿: 다음 암호화 방법을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="08b13-150">**View data by: Message Encryption Report** and **Break down by: Encryption template**: The following encryption methods are available:</span></span>

  - <span data-ttu-id="08b13-151">**전달하지 않습니다.**</span><span class="sxs-lookup"><span data-stu-id="08b13-151">**Do not forward**</span></span>
  - <span data-ttu-id="08b13-152">**암호화만**</span><span class="sxs-lookup"><span data-stu-id="08b13-152">**Encrypt only**</span></span>
  - <span data-ttu-id="08b13-153">**OME 이전**</span><span class="sxs-lookup"><span data-stu-id="08b13-153">**OME previous**</span></span>
  - <span data-ttu-id="08b13-154">**사용자 지정**</span><span class="sxs-lookup"><span data-stu-id="08b13-154">**Custom**</span></span>

  <span data-ttu-id="08b13-155">필터를 **클릭하면** 다음 필터를 사용하여 차트를 수정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="08b13-155">If you click **Filters**, you can modify the chart with the following filters:</span></span>

  - <span data-ttu-id="08b13-156">**시작 날짜** 및 **종료 날짜**</span><span class="sxs-lookup"><span data-stu-id="08b13-156">**Start date** and **End date**</span></span>
  - <span data-ttu-id="08b13-157">암호화 방법</span><span class="sxs-lookup"><span data-stu-id="08b13-157">Encryption method</span></span>
  - <span data-ttu-id="08b13-158">암호화 템플릿</span><span class="sxs-lookup"><span data-stu-id="08b13-158">Encryption template</span></span>

- <span data-ttu-id="08b13-159">**데이터 보기: 상위 5개** 받는 사람 도메인: 이 보기에는 상위 5개 받는 사람 도메인에 대해 보낸 메시지 수가 있는 파이 차트가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="08b13-159">**View data by: Top 5 recipient domains**: This view shows a pie chart with sent message counts for the top 5 recipient domains.</span></span>

  <span data-ttu-id="08b13-160">필터를 **클릭하면** 시작 날짜와  종료 날짜를 **선택할 수 있습니다.**</span><span class="sxs-lookup"><span data-stu-id="08b13-160">If you click **Filters**, you can select a **Start date** and **End date**.</span></span>

### <a name="details-table-view-for-the-encryption-report"></a><span data-ttu-id="08b13-161">암호화 보고서에 대한 세부 정보 테이블 보기</span><span class="sxs-lookup"><span data-stu-id="08b13-161">Details table view for the Encryption report</span></span>

<span data-ttu-id="08b13-162">세부 **정보** 표 보기를 클릭하면 표시되는 정보는 보고 있는 차트에 따라 다를 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="08b13-162">If you click **View details table**, the information that's shown depends on the chart you were looking at:</span></span>

- <span data-ttu-id="08b13-163">**다음을 통해 세분화할** 수 있습니다. 암호화 방법 또는 세분화: **암호화** 템플릿: 다음 정보가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="08b13-163">**Break down by: Encryption method** or **Break down by: Encryption template**: The following information is shown:</span></span>

  - <span data-ttu-id="08b13-164">**날짜**</span><span class="sxs-lookup"><span data-stu-id="08b13-164">**Date**</span></span>
  - <span data-ttu-id="08b13-165">**보낸 사람 주소**</span><span class="sxs-lookup"><span data-stu-id="08b13-165">**Sender address**</span></span>
  - <span data-ttu-id="08b13-166">**암호화 템플릿**</span><span class="sxs-lookup"><span data-stu-id="08b13-166">**Encryption template**</span></span>
  - <span data-ttu-id="08b13-167">**암호화 방법**</span><span class="sxs-lookup"><span data-stu-id="08b13-167">**Encryption method**</span></span>
  - <span data-ttu-id="08b13-168">**받는 사람 주소**</span><span class="sxs-lookup"><span data-stu-id="08b13-168">**Recipient address**</span></span>
  - <span data-ttu-id="08b13-169">**제목**</span><span class="sxs-lookup"><span data-stu-id="08b13-169">**Subject**</span></span>

- <span data-ttu-id="08b13-170">**다음을 통해 데이터 보기: 상위 5개 받는 사람 도메인:**</span><span class="sxs-lookup"><span data-stu-id="08b13-170">**View data by: Top 5 recipient domains**:</span></span>

  - <span data-ttu-id="08b13-171">**날짜**</span><span class="sxs-lookup"><span data-stu-id="08b13-171">**Date**</span></span>
  - <span data-ttu-id="08b13-172">**받는 사람 도메인**</span><span class="sxs-lookup"><span data-stu-id="08b13-172">**Recipient domain**</span></span>
  - <span data-ttu-id="08b13-173">**메시지 수**</span><span class="sxs-lookup"><span data-stu-id="08b13-173">**Message count**</span></span>

<span data-ttu-id="08b13-174">세부 정보 테이블 보기에서 **필터를** 클릭하면 다음 필터를 사용하여 결과를 수정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="08b13-174">If you click **Filters** in a details table view, you can modify the results with the following filters:</span></span>

- <span data-ttu-id="08b13-175">**시작 날짜** 및 **종료 날짜**</span><span class="sxs-lookup"><span data-stu-id="08b13-175">**Start date** and **End date**</span></span>
- <span data-ttu-id="08b13-176">암호화 방법</span><span class="sxs-lookup"><span data-stu-id="08b13-176">Encryption method</span></span>
- <span data-ttu-id="08b13-177">암호화 템플릿</span><span class="sxs-lookup"><span data-stu-id="08b13-177">Encryption template</span></span>

<span data-ttu-id="08b13-178">보고서 보기로 돌아가려면 보고서 **보기를 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="08b13-178">To go back to the report view, click **View report**.</span></span>

## <a name="mailflow-status-report"></a><span data-ttu-id="08b13-179">메일 흐름 상태 보고서</span><span class="sxs-lookup"><span data-stu-id="08b13-179">Mailflow status report</span></span>

<span data-ttu-id="08b13-180">메일 **흐름 상태 보고서에는** 맬웨어, 스팸, 피싱 및 Edge 차단 메시지에 대한 정보가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="08b13-180">The **Mailflow status report** contains information about malware, spam, phishing and edge blocked messages.</span></span> <span data-ttu-id="08b13-181">자세한 내용은 메일 흐름 상태 [보고서를 참조합니다.](view-mail-flow-reports.md#mailflow-status-report)</span><span class="sxs-lookup"><span data-stu-id="08b13-181">For more details, see [Mailflow status report](view-mail-flow-reports.md#mailflow-status-report).</span></span>

## <a name="malware-detections-in-email-report"></a><span data-ttu-id="08b13-182">전자 메일 보고서의 맬웨어 검색</span><span class="sxs-lookup"><span data-stu-id="08b13-182">Malware detections in email report</span></span>

<span data-ttu-id="08b13-183">전자 **메일 보고서의** 맬웨어 검색은 들어오는 전자 메일 메시지와 보낸 전자 메일 메시지의 맬웨어 검색에 대한 정보를 보여줍니다(Exchange Online Protection 또는 EOP에서 검색된 맬웨어).</span><span class="sxs-lookup"><span data-stu-id="08b13-183">The **Malware detections in email** report shows information about malware detections in incoming and outgoing email messages (malware detected by Exchange Online Protection or EOP).</span></span> <span data-ttu-id="08b13-184">EOP의 맬웨어 보호에 대한 자세한 내용은 EOP의 맬웨어 [방지 보호 기능을 참조하세요.](anti-malware-protection.md)</span><span class="sxs-lookup"><span data-stu-id="08b13-184">For more information about malware protection in EOP, see [Anti-malware protection in EOP](anti-malware-protection.md).</span></span>

 <span data-ttu-id="08b13-185">집계 보기 필터는 90일 동안 허용되는 반면 세부 정보 테이블 필터는 10일 동안만 허용됩니다.</span><span class="sxs-lookup"><span data-stu-id="08b13-185">The aggregate view filter allows for 90 days, while the details table filter only allows for 10 days.</span></span>

<span data-ttu-id="08b13-186">보고서를 확인하려면 보안 & 준수 센터를 열고  보고서 대시보드로 이동한 다음 전자 [메일에서](https://protection.office.com) \>  **맬웨어** 검색을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="08b13-186">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Malware detections in email**.</span></span> <span data-ttu-id="08b13-187">보고서로 직접 이동하기 위해 를 열 수 <https://protection.office.com/reportv2?id=MalwareDetections> 있습니다.</span><span class="sxs-lookup"><span data-stu-id="08b13-187">To go directly to the report, open <https://protection.office.com/reportv2?id=MalwareDetections>.</span></span>

![보고서 대시보드의 전자 메일 위젯에서 맬웨어 감지](../../media/malware-detections-widget.png)

<span data-ttu-id="08b13-189">필터를 클릭하고 다음을 선택하여 차트와 세부 정보 테이블을 **모두** 필터링할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="08b13-189">You can filter both the chart and the details table by clicking **Filters** and selecting:</span></span>

- <span data-ttu-id="08b13-190">**시작 날짜** 및 **종료 날짜**</span><span class="sxs-lookup"><span data-stu-id="08b13-190">**Start date** and **End date**</span></span>
- <span data-ttu-id="08b13-191">**인바운드**</span><span class="sxs-lookup"><span data-stu-id="08b13-191">**Inbound**</span></span>
- <span data-ttu-id="08b13-192">**아웃바운드**</span><span class="sxs-lookup"><span data-stu-id="08b13-192">**Outbound**</span></span>

![전자 메일 보고서의 맬웨어 검색 보고서 보기](../../media/malware-detections-report-view.png)

<span data-ttu-id="08b13-194">세부 정보 표 보기를 **클릭하면** 다음 세부 정보를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="08b13-194">If you click **View details table**, you can see the following details:</span></span>

- <span data-ttu-id="08b13-195">**날짜**</span><span class="sxs-lookup"><span data-stu-id="08b13-195">**Date**</span></span>
- <span data-ttu-id="08b13-196">**보낸 사람 주소**</span><span class="sxs-lookup"><span data-stu-id="08b13-196">**Sender address**</span></span>
- <span data-ttu-id="08b13-197">**받는 사람 주소**</span><span class="sxs-lookup"><span data-stu-id="08b13-197">**Recipient address**</span></span>
- <span data-ttu-id="08b13-198">**메시지 ID:** 메시지 헤더의 **Message-ID** 헤더 필드에서 사용할 수 있으며 고유해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="08b13-198">**Message ID**: Available in the **Message-ID** header field in the message header and should be unique.</span></span> <span data-ttu-id="08b13-199">값의 예로는 괄호를 `<08f1e0f6806a47b4ac103961109ae6ef@server.domain>` 들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="08b13-199">An example value is `<08f1e0f6806a47b4ac103961109ae6ef@server.domain>` (note the angle brackets).</span></span>
- <span data-ttu-id="08b13-200">**제목**</span><span class="sxs-lookup"><span data-stu-id="08b13-200">**Subject**</span></span>
- <span data-ttu-id="08b13-201">**파일 이름**</span><span class="sxs-lookup"><span data-stu-id="08b13-201">**Filename**</span></span>
- <span data-ttu-id="08b13-202">**맬웨어 이름**</span><span class="sxs-lookup"><span data-stu-id="08b13-202">**Malware name**</span></span>

<span data-ttu-id="08b13-203">보고서 보기로 돌아가려면 보고서 **보기를 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="08b13-203">To go back to the report view, click **View report**.</span></span>

## <a name="mail-latency-report"></a><span data-ttu-id="08b13-204">메일 대기 시간 보고서</span><span class="sxs-lookup"><span data-stu-id="08b13-204">Mail latency report</span></span>

<span data-ttu-id="08b13-205">메일 **대기 시간 보고서에는** 조직 내에서 발생된 메일 배달 및 확인 대기 시간에 대한 정보가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="08b13-205">The **Mail latency report** contains information on the mail delivery and detonation latency experienced within your organization.</span></span> <span data-ttu-id="08b13-206">자세한 내용은 메일 대기 [시간 보고서를 참조하십시오.](view-reports-for-atp.md#mail-latency-report)</span><span class="sxs-lookup"><span data-stu-id="08b13-206">For more information, see [Mail latency report](view-reports-for-atp.md#mail-latency-report).</span></span>

## <a name="sent-and-received-email-report"></a><span data-ttu-id="08b13-207">보낸 메일 및 받은 전자 메일 보고서</span><span class="sxs-lookup"><span data-stu-id="08b13-207">Sent and received email report</span></span>

<span data-ttu-id="08b13-208">**보내고** 받은 전자 메일 보고서에는 맬웨어, 스팸, 메일 흐름 규칙(전송 규칙) 및 전자 메일이 서비스에 들어오면 고급 맬웨어 검색에 대한 정보가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="08b13-208">The **Sent and received email** report contains information about malware, spam, mail flow rules (also known as transport rules), and advanced malware detections after email enters the service.</span></span> <span data-ttu-id="08b13-209">자세한 내용은 보낸 전자 메일 보고서 및 받은 전자 [메일 보고서를 참조하세요.](view-mail-flow-reports.md#sent-and-received-email-report)</span><span class="sxs-lookup"><span data-stu-id="08b13-209">For more information, see [Sent and received email report](view-mail-flow-reports.md#sent-and-received-email-report).</span></span>

## <a name="spam-detections-report"></a><span data-ttu-id="08b13-210">스팸 검색 보고서</span><span class="sxs-lookup"><span data-stu-id="08b13-210">Spam detections report</span></span>

<span data-ttu-id="08b13-211">스팸 **검색 보고서에는** EOP에서 차단된 스팸 전자 메일 메시지가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="08b13-211">The **Spam detections** report shows spam email messages that were blocked by EOP.</span></span> <span data-ttu-id="08b13-212">메시지는 받는 사람당 계산이 아니라 개별적으로 계산됩니다.</span><span class="sxs-lookup"><span data-stu-id="08b13-212">Messages are counted individually, not per recipient.</span></span> <span data-ttu-id="08b13-213">예를 들어 조직의 받는 사람 100명에게 동일한 스팸 메시지를 보낸 경우 하나의 메시지로 계산됩니다.</span><span class="sxs-lookup"><span data-stu-id="08b13-213">For example, if the same spam message was sent to 100 recipients in your organization, it counts as one message.</span></span>

<span data-ttu-id="08b13-214">집계 보기에서는 90일 필터링이 허용되는 반면 세부 정보 테이블에서는 10일 필터링을 허용합니다.</span><span class="sxs-lookup"><span data-stu-id="08b13-214">The aggregate view allows for 90 days filtering, while the details table allows for 10 days filtering.</span></span>

<span data-ttu-id="08b13-215">보고서를 표시하려면 보안 및 준수 [&](https://protection.office.com)보고서 대시보드로  이동하여 스팸 \>  **검색을 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="08b13-215">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Spam detections**.</span></span> <span data-ttu-id="08b13-216">보고서로 직접 이동하기 위해 를 열 수 <https://protection.office.com/reportv2?id=SpamDetections> 있습니다.</span><span class="sxs-lookup"><span data-stu-id="08b13-216">To go directly to the report, open <https://protection.office.com/reportv2?id=SpamDetections>.</span></span>

![보고서 대시보드의 스팸 검색 위젯](../../media/spam-detections-report-widget.png)

<span data-ttu-id="08b13-218">스팸 방지 보호에 대한 자세한 내용은 EOP의 스팸 방지 [보호 기능을 참조하세요.](anti-spam-protection.md)</span><span class="sxs-lookup"><span data-stu-id="08b13-218">For more information about anti-spam protection, see [Anti-spam protection in EOP](anti-spam-protection.md).</span></span>

### <a name="report-view-for-the-spam-detections-report"></a><span data-ttu-id="08b13-219">스팸 검색 보고서에 대한 보고서 보기</span><span class="sxs-lookup"><span data-stu-id="08b13-219">Report view for the Spam detections report</span></span>

<span data-ttu-id="08b13-220">보고서 보기에서는 다음 차트를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="08b13-220">The following charts are available in the report view:</span></span>

- <span data-ttu-id="08b13-221">**작업별: 다음** 이벤트 유형이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="08b13-221">**Break down by: Action**: The following event types are shown:</span></span>

  - <span data-ttu-id="08b13-222">**필터링된 스팸 콘텐츠**</span><span class="sxs-lookup"><span data-stu-id="08b13-222">**Spam content filtered**</span></span>
  - <span data-ttu-id="08b13-223">**스팸 IP 블록**</span><span class="sxs-lookup"><span data-stu-id="08b13-223">**Spam IP block**</span></span>
  - <span data-ttu-id="08b13-224">**스팸 봉투 블록**</span><span class="sxs-lookup"><span data-stu-id="08b13-224">**Spam envelope block**</span></span>
  - <span data-ttu-id="08b13-225">**스팸 DBEB 필터:** DBEB(디렉터리 기반 Edge 차단)</span><span class="sxs-lookup"><span data-stu-id="08b13-225">**Spam DBEB filter**: Directory based edge blocking (DBEB)</span></span>

  <span data-ttu-id="08b13-226">차트에서 하루(데이터 포인트)에 마우스를 대면 해당 일자에 차단된 항목 수와 해당 항목이 분류되는 방법을 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="08b13-226">When you hover over a day (data point) in the chart, you can see how many items were blocked that day, as well as how those items are categorized.</span></span>

  ![스팸 검색 보고서의 작업 보기](../../media/spam-detections-report-action-view.png)

- <span data-ttu-id="08b13-228">**세분화하여: 방향:** 다음 길안이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="08b13-228">**Break down by: Direction**: The following directions are shown:</span></span>

  - <span data-ttu-id="08b13-229">**인바운드**</span><span class="sxs-lookup"><span data-stu-id="08b13-229">**Inbound**</span></span>
  - <span data-ttu-id="08b13-230">**아웃바운드**</span><span class="sxs-lookup"><span data-stu-id="08b13-230">**Outbound**</span></span>

  ![스팸 검색 보고서의 방향 보기](../../media/spam-detections-report-direction-view.png)

<span data-ttu-id="08b13-232">보고서 보기에서 **필터를** 클릭하면 다음 필터를 사용하여 결과를 수정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="08b13-232">If you click **Filters** in a report view, you can modify the results with the following filters:</span></span>

- <span data-ttu-id="08b13-233">**시작 날짜** 및 **종료 날짜**</span><span class="sxs-lookup"><span data-stu-id="08b13-233">**Start date** and **End date**</span></span>
- <span data-ttu-id="08b13-234">방향 값</span><span class="sxs-lookup"><span data-stu-id="08b13-234">Direction values</span></span>
- <span data-ttu-id="08b13-235">이벤트 유형 값</span><span class="sxs-lookup"><span data-stu-id="08b13-235">Event type values</span></span>

### <a name="details-table-view-for-the-spam-detections-report"></a><span data-ttu-id="08b13-236">스팸 검색 보고서에 대한 세부 정보 테이블 보기</span><span class="sxs-lookup"><span data-stu-id="08b13-236">Details table view for the Spam detections report</span></span>

<span data-ttu-id="08b13-237">보고서 **보기에서** 세부 정보 표 보기를 클릭하면 다음 정보가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="08b13-237">If you click **View details table** in any report view, the following information is shown:</span></span>

- <span data-ttu-id="08b13-238">**날짜**</span><span class="sxs-lookup"><span data-stu-id="08b13-238">**Date**</span></span>
- <span data-ttu-id="08b13-239">**보낸 사람 주소**</span><span class="sxs-lookup"><span data-stu-id="08b13-239">**Sender address**</span></span>
- <span data-ttu-id="08b13-240">**받는 사람 주소**</span><span class="sxs-lookup"><span data-stu-id="08b13-240">**Recipient address**</span></span>
- <span data-ttu-id="08b13-241">**이벤트 유형**</span><span class="sxs-lookup"><span data-stu-id="08b13-241">**Event type**</span></span>
- <span data-ttu-id="08b13-242">**작업**</span><span class="sxs-lookup"><span data-stu-id="08b13-242">**Action**</span></span>
- <span data-ttu-id="08b13-243">**제목**</span><span class="sxs-lookup"><span data-stu-id="08b13-243">**Subject**</span></span>

<span data-ttu-id="08b13-244">세부 정보 표에서 **필터를** 클릭하면 다음 필터를 사용하여 결과를 수정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="08b13-244">If you click **Filters** in a details table, you can modify the results with the following filters:</span></span>

- <span data-ttu-id="08b13-245">**시작 날짜** 및 **종료 날짜**</span><span class="sxs-lookup"><span data-stu-id="08b13-245">**Start date** and **End date**</span></span>
- <span data-ttu-id="08b13-246">방향 값</span><span class="sxs-lookup"><span data-stu-id="08b13-246">Direction values</span></span>
- <span data-ttu-id="08b13-247">이벤트 유형 값</span><span class="sxs-lookup"><span data-stu-id="08b13-247">Event type values</span></span>

<span data-ttu-id="08b13-248">보고서 보기로 돌아가려면 보고서 **보기를 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="08b13-248">To go back to the report view, click **View report**.</span></span>

## <a name="spoof-detections-report"></a><span data-ttu-id="08b13-249">스푸핑 검색 보고서</span><span class="sxs-lookup"><span data-stu-id="08b13-249">Spoof detections report</span></span>

<span data-ttu-id="08b13-250">**스푸핑** 검색 보고서에는 검색된 스푸핑 메일 메시지의 수와 "양호한" 것으로 간주된 스푸핑 메일 메시지(합법적인 비즈니스 이유로 수행된 스푸핑 메일)가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="08b13-250">The **Spoof detections** report shows how many spoof mail messages were detected, and of those, which ones were considered "good" (spoof mail done for legitimate business reasons).</span></span> <span data-ttu-id="08b13-251">스푸핑에 대한 자세한 내용은 EOP의 스푸핑 방지 보호 기능을 [참조하세요.](anti-spoofing-protection.md)</span><span class="sxs-lookup"><span data-stu-id="08b13-251">For more information about spoofing, see [Anti-spoofing protection in EOP](anti-spoofing-protection.md).</span></span>

<span data-ttu-id="08b13-252">보고서의 집계 보기는 90일 동안 필터링할 수 있는 반면 세부 정보 보기는 10일의 필터링만 허용합니다.</span><span class="sxs-lookup"><span data-stu-id="08b13-252">The aggregate view of the report allows for 90 days of filtering, while the detail view only allows for ten days of filtering.</span></span>

<span data-ttu-id="08b13-253">보고서를 보고 보안 및 준수 [센터를 &](https://protection.office.com)보고서  대시보드로 이동하여 스푸핑 검색을 \>  **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="08b13-253">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Spoof detections**.</span></span> <span data-ttu-id="08b13-254">보고서로 직접 이동하기 위해 를 열 수 <https://protection.office.com/reportv2?id=SpoofMailReport> 있습니다.</span><span class="sxs-lookup"><span data-stu-id="08b13-254">To go directly to the report, open <https://protection.office.com/reportv2?id=SpoofMailReport>.</span></span>

![보고서 대시보드에서 스푸핑 감지 위젯](../../media/spoof-detections-widget.png)

<span data-ttu-id="08b13-256">차트에서 하루(데이터 포인트)에 마우스를 대면 스푸핑 메일 메시지의 수를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="08b13-256">When you hover over a day (data point) in the chart, you can see how many spoof mail messages came through.</span></span>

<span data-ttu-id="08b13-257">필터를 클릭하고 다음 값 중 하나  이상을 선택하여 차트와 세부 정보 테이블을 모두 필터링할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="08b13-257">You can filter both the chart and the details table by clicking **Filters** and selecting one or more of the following values:</span></span>

- <span data-ttu-id="08b13-258">**시작 날짜** 및 **종료 날짜**</span><span class="sxs-lookup"><span data-stu-id="08b13-258">**Start date** and **End date**</span></span>

- <span data-ttu-id="08b13-259">**좋은 메일**</span><span class="sxs-lookup"><span data-stu-id="08b13-259">**Good mail**</span></span>

- <span data-ttu-id="08b13-260">**스팸으로 검색**</span><span class="sxs-lookup"><span data-stu-id="08b13-260">**Caught as spam**</span></span>

![스푸핑 검색 보고서의 보고서 보기](../../media/spoof-detections-report-view.png)

<span data-ttu-id="08b13-262">세부 정보 표 보기를 **클릭하면** 다음 세부 정보를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="08b13-262">If you click **View details table**, you can see the following details:</span></span>

- <span data-ttu-id="08b13-263">**날짜**</span><span class="sxs-lookup"><span data-stu-id="08b13-263">**Date**</span></span>
- <span data-ttu-id="08b13-264">**스푸핑된 보낸 사람**</span><span class="sxs-lookup"><span data-stu-id="08b13-264">**Spoofed sender**</span></span>
- <span data-ttu-id="08b13-265">**True 보낸 사람**</span><span class="sxs-lookup"><span data-stu-id="08b13-265">**True sender**</span></span>
- <span data-ttu-id="08b13-266">**보낸 사람 IP**</span><span class="sxs-lookup"><span data-stu-id="08b13-266">**Sender IP**</span></span>
- <span data-ttu-id="08b13-267">**작업**</span><span class="sxs-lookup"><span data-stu-id="08b13-267">**Action**</span></span>
- <span data-ttu-id="08b13-268">**메시지 수**</span><span class="sxs-lookup"><span data-stu-id="08b13-268">**Message count**</span></span>

<span data-ttu-id="08b13-269">보고서 보기로 돌아가려면 보고서 **보기를 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="08b13-269">To go back to the report view, click **View report**.</span></span>

## <a name="threat-protection-status-report"></a><span data-ttu-id="08b13-270">위협 방지 상태 보고서</span><span class="sxs-lookup"><span data-stu-id="08b13-270">Threat protection status report</span></span>

<span data-ttu-id="08b13-271">위협 **방지 상태 보고서는** EOP와 Office 365용 Microsoft Defender에서 모두 사용할 수 있습니다. 그러나 보고서에는 다른 데이터가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="08b13-271">The **Threat protection status** report is available in both EOP and Microsoft Defender for Office 365; however, the reports contain different data.</span></span> <span data-ttu-id="08b13-272">예를 들어 EOP 고객은 전자 메일에서 검색된 맬웨어에 대한 정보를 볼 수 있지만 [SharePoint, OneDrive](atp-for-spo-odb-and-teams.md)또는 Microsoft Teams에 대해 ATP에서 검색한 악성 파일에 대한 정보는 볼 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="08b13-272">For example, EOP customers can view information about malware detected in email, but not information about malicious files detected by [ATP for SharePoint, OneDrive, or Microsoft Teams](atp-for-spo-odb-and-teams.md).</span></span>

<span data-ttu-id="08b13-273">이 보고서는 맬웨어 방지 엔진에 의해 차단된 파일 또는 웹 사이트 주소(URL), [ZAP(제로](zero-hour-auto-purge.md)아워 자동 비우기) 및 Office 365용 Defender(예: 안전 [링크,](atp-safe-links.md)안전한 첨부 파일 및 피싱 방지)와 같은 악성 콘텐츠가 있는 전자 메일 메시지 수를 [제공합니다.](set-up-anti-phishing-policies.md) [](atp-safe-attachments.md)</span><span class="sxs-lookup"><span data-stu-id="08b13-273">The report provides the count of email messages with malicious content, such as files or website addresses (URLs) that were blocked by the anti-malware engine, [zero-hour auto purge (ZAP)](zero-hour-auto-purge.md), and Defender for Office 365 features like [Safe Links](atp-safe-links.md), [Safe Attachments](atp-safe-attachments.md), and [Anti-phishing](set-up-anti-phishing-policies.md).</span></span> <span data-ttu-id="08b13-274">이 정보를 사용하여 추세를 식별하거나 조직 정책에 조정이 필요한지 여부를 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="08b13-274">You can use this information to identify trends or determine whether organization policies need adjustment.</span></span>

<span data-ttu-id="08b13-275">**참고:** 받는 사람 5명에게 메시지가 전송된 경우 하나의 메시지가 아니라 5개의 다른 메시지로 계산됩니다.</span><span class="sxs-lookup"><span data-stu-id="08b13-275">**Note**: It's important to understand that if a message is sent to five recipients we count it as five different messages and not one message.</span></span>

<span data-ttu-id="08b13-276">보고서를 확인하려면 보안 & 준수 센터를 열고  보고서 [대시보드로](https://protection.office.com)이동하여 위협 방지 상태를 \>  **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="08b13-276">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Threat protection status**.</span></span> <span data-ttu-id="08b13-277">보고서로 직접 이동하기 위해 다음 URL 중 하나를 열 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="08b13-277">To go directly to the report, open one of the following URLs:</span></span>

- <span data-ttu-id="08b13-278">Office 365용 Microsoft Defender: <https://protection.office.com/reportv2?id=TPSAggregateReportATP></span><span class="sxs-lookup"><span data-stu-id="08b13-278">Microsoft Defender for Office 365: <https://protection.office.com/reportv2?id=TPSAggregateReportATP></span></span>
- <span data-ttu-id="08b13-279">EOP: <https://protection.office.com/reportv2?id=TPSAggregateReport></span><span class="sxs-lookup"><span data-stu-id="08b13-279">EOP: <https://protection.office.com/reportv2?id=TPSAggregateReport></span></span>

![보고서 대시보드의 위협 방지 상태 위젯](../../media/threat-protection-status-report-widget.png)

<span data-ttu-id="08b13-281">기본적으로 차트에는 지난 7일간의 데이터가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="08b13-281">By default, the chart shows data for the past 7 days.</span></span> <span data-ttu-id="08b13-282">필터를 클릭하면 90일 날짜 범위를 선택할 수 있습니다(평가판 구독은 30일로 제한될 수 있습니다).</span><span class="sxs-lookup"><span data-stu-id="08b13-282">If you click **Filters**, you can select a 90 day date range (trial subscriptions might be limited to 30 days).</span></span> <span data-ttu-id="08b13-283">세부 정보 테이블 보기를 사용하면 30일 동안 필터링할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="08b13-283">The details table view allows filtering for 30 days.</span></span>

### <a name="report-view-for-the-threat-protection-status-report"></a><span data-ttu-id="08b13-284">위협 방지 상태 보고서에 대한 보고서 보기</span><span class="sxs-lookup"><span data-stu-id="08b13-284">Report view for the Threat protection status report</span></span>

<span data-ttu-id="08b13-285">다음 보기를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="08b13-285">The following views are available:</span></span>

- <span data-ttu-id="08b13-286">**데이터 보기: 개요:** 다음 검색 정보가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="08b13-286">**View data by: Overview**: The following detection information is shown:</span></span>

  - <span data-ttu-id="08b13-287">**전자 메일 맬웨어**</span><span class="sxs-lookup"><span data-stu-id="08b13-287">**Email malware**</span></span>
  - <span data-ttu-id="08b13-288">**전자 메일 피싱**</span><span class="sxs-lookup"><span data-stu-id="08b13-288">**Email phish**</span></span>
  - <span data-ttu-id="08b13-289">**콘텐츠 맬웨어**</span><span class="sxs-lookup"><span data-stu-id="08b13-289">**Content malware**</span></span>

  ![위협 방지 상태 보고서의 개요 보기](../../media/threat-protection-status-report-overview-view.png)

- <span data-ttu-id="08b13-291">**데이터 보기: \> 콘텐츠 맬웨어**<sup>1:</sup>Office 365 조직용 Microsoft Defender에 대한 다음 정보가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="08b13-291">**View data by: Content \> Malware**<sup>1</sup>: The following information is shown for Microsoft Defender for Office 365 organizations:</span></span>

  - <span data-ttu-id="08b13-292">**맬웨어** 방지 엔진 : [Microsoft 365의](virus-detection-in-spo.md)기본 제공 바이러스 감지로 Sharepoint, OneDrive 및 Microsoft Teams에서 악성 파일이 검색되었습니다.</span><span class="sxs-lookup"><span data-stu-id="08b13-292">**Anti-malware engine**: Malicious files detected in Sharepoint, OneDrive, and Microsoft Teams by the [built-in virus detection in Microsoft 365](virus-detection-in-spo.md).</span></span>
  - <span data-ttu-id="08b13-293">**파일 검색:** [ATP에서 Sharepoint, OneDrive](atp-for-spo-odb-and-teams.md)및 Microsoft Teams에 대해 검색된 악성 파일.</span><span class="sxs-lookup"><span data-stu-id="08b13-293">**File detonation**: Malicious files detected by [ATP for Sharepoint, OneDrive, and Microsoft Teams](atp-for-spo-odb-and-teams.md).</span></span>

  ![위협 방지 상태 보고서의 콘텐츠 맬웨어 보기](../../media/threat-protection-status-report-content-malware-view.png)

- <span data-ttu-id="08b13-295">**데이터 보기: 메시지 오버라이드:** 다음과 같은 이유 정보가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="08b13-295">**View data by: Message Override**: The following override reason information is shown:</span></span>

  - <span data-ttu-id="08b13-296">**On-premises skip**</span><span class="sxs-lookup"><span data-stu-id="08b13-296">**On-premises skip**</span></span>
  - <span data-ttu-id="08b13-297">**IP 허용**</span><span class="sxs-lookup"><span data-stu-id="08b13-297">**IP Allow**</span></span>
  - <span data-ttu-id="08b13-298">**메일 흐름 규칙**</span><span class="sxs-lookup"><span data-stu-id="08b13-298">**Mail flow rule**</span></span>
  - <span data-ttu-id="08b13-299">**보낸 사람 허용**</span><span class="sxs-lookup"><span data-stu-id="08b13-299">**Sender allow**</span></span>
  - <span data-ttu-id="08b13-300">**도메인 허용**</span><span class="sxs-lookup"><span data-stu-id="08b13-300">**Domain allow**</span></span>
  - <span data-ttu-id="08b13-301">**ZAP를 사용할 수 없습니다.**</span><span class="sxs-lookup"><span data-stu-id="08b13-301">**ZAP not enabled**</span></span>
  - <span data-ttu-id="08b13-302">**정크 메일 폴더를 사용할 수 없습니다.**</span><span class="sxs-lookup"><span data-stu-id="08b13-302">**Junk Mail folder not enabled**</span></span>
  - <span data-ttu-id="08b13-303">**사용자 안전한 보낸 사람**</span><span class="sxs-lookup"><span data-stu-id="08b13-303">**User Safe Sender**</span></span>
  - <span data-ttu-id="08b13-304">**사용자 안전 도메인**</span><span class="sxs-lookup"><span data-stu-id="08b13-304">**User Safe Domain**</span></span>

  ![위협 방지 상태 보고서의 메시지 오버라이드 보기](../../media/threat-protection-status-report-message-override-view.png)

- <span data-ttu-id="08b13-306">**검색 기술 및** 데이터 보기: 전자 메일 **\> 피싱:** 다음 정보가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="08b13-306">**Break down by: Detection technology** and **View data by: Email \> Phish**: The following information is shown:</span></span>

  - <span data-ttu-id="08b13-307">**ATP 생성 URL 신뢰도**<sup>1:</sup>다른 Microsoft 365 고객의 Office 365 확인을 위해 Defender에서 생성된 악성 URL 신뢰도입니다.</span><span class="sxs-lookup"><span data-stu-id="08b13-307">**ATP-generated URL reputation**<sup>1</sup>: Malicious URL reputation generated from Defender for Office 365 detonations in other Microsoft 365 customers.</span></span>
  - <span data-ttu-id="08b13-308">**고급 피싱 필터:** 기계 학습을 기반으로 하는 피싱 신호입니다.</span><span class="sxs-lookup"><span data-stu-id="08b13-308">**Advanced phish filter**: Phishing signals based on machine learning.</span></span>
  - <span data-ttu-id="08b13-309">**스푸핑 방지 - DMARC 실패:** 메시지에 대한 DMARC 인증 실패.</span><span class="sxs-lookup"><span data-stu-id="08b13-309">**Anti-spoof - DMARC failure**: DMARC authentication failure on messages.</span></span>
  - <span data-ttu-id="08b13-310">**스푸핑** 방지 - 도메인 내 : 보낸 사람이 받는 사람 도메인을 스푸핑하려고 합니다.</span><span class="sxs-lookup"><span data-stu-id="08b13-310">**Anti-spoof - intra-org**: Sender is trying to spoof the recipient domain.</span></span>
  - <span data-ttu-id="08b13-311">**스푸핑** 방지 - 외부 도메인 : 보낸 사람이 다른 도메인을 스푸핑하려고 합니다.</span><span class="sxs-lookup"><span data-stu-id="08b13-311">**Anti-spoof - external domain**: Sender is trying to spoof some other domain.</span></span>
  - <span data-ttu-id="08b13-312">**브랜드 가장:** 보낸 사람 기반의 잘 알려진 브랜드 가장.</span><span class="sxs-lookup"><span data-stu-id="08b13-312">**Brand impersonation**: Impersonation of well-known brands based on senders.</span></span>
  - <span data-ttu-id="08b13-313">**도메인 가장**<sup>1:</sup>고객이 소유하거나 정의하는 도메인을 가장합니다.</span><span class="sxs-lookup"><span data-stu-id="08b13-313">**Domain impersonation**<sup>1</sup>: Impersonation of domains that the customer owns or defines.</span></span>
  - <span data-ttu-id="08b13-314">**EOP URL 신뢰도**: 악의적인 URL 신뢰도</span><span class="sxs-lookup"><span data-stu-id="08b13-314">**EOP URL reputation**: Malicious URL reputation.</span></span>
  - <span data-ttu-id="08b13-315">**일반 피싱 필터:** 분석가 규칙에 기반한 피싱 신호입니다.</span><span class="sxs-lookup"><span data-stu-id="08b13-315">**General phish filter**: Phishing signals based on analyst rules.</span></span>
  - <span data-ttu-id="08b13-316">**기타**</span><span class="sxs-lookup"><span data-stu-id="08b13-316">**Others**</span></span>
  - <span data-ttu-id="08b13-317">**피싱 ZAP**<sup>2:</sup>피싱 메시지의 0시간 자동 제거</span><span class="sxs-lookup"><span data-stu-id="08b13-317">**Phish ZAP**<sup>2</sup>: Zero hour auto purge of phishing messages.</span></span>
  - <span data-ttu-id="08b13-318">**URL 확인**<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="08b13-318">**URL detonation**<sup>1</sup></span></span>
  - <span data-ttu-id="08b13-319">**사용자 가장**<sup>1:</sup>관리자가 정의하거나 사서함 인텔리전스를 통해 학습한 사용자를 가장합니다.</span><span class="sxs-lookup"><span data-stu-id="08b13-319">**User impersonation**<sup>1</sup>: Impersonation of users defined by admin or learned through mailbox intelligence.</span></span>

  ![위협 방지 상태 보고서의 피싱 전자 메일에 대한 검색 기술 보기](../../media/threat-protection-status-report-phishing-detection-tech-view.png)

- <span data-ttu-id="08b13-321">**검색 기술 및** 데이터 보기: 전자 메일 맬웨어: 다음 정보가 표시됩니다. **\>**</span><span class="sxs-lookup"><span data-stu-id="08b13-321">**Break down by: Detection technology** and **View data by: Email \> Malware**: The following information is shown:</span></span>

  - <span data-ttu-id="08b13-322">**ATP 생성 파일** 신뢰도 <sup>1:</sup>Office 365에서 Defender에서 생성한 모든 악성 파일 신뢰도.</span><span class="sxs-lookup"><span data-stu-id="08b13-322">**ATP-generated file reputation**<sup>1</sup>: All malicious file reputation generated by Defender for Office 365 detonations.</span></span>
  - <span data-ttu-id="08b13-323">**맬웨어 방지 엔진**<sup>1: 맬웨어</sup>방지 엔진에서 검색.</span><span class="sxs-lookup"><span data-stu-id="08b13-323">**Anti-malware engine**<sup>1</sup>: Detection from anti-malware engines.</span></span>
  - <span data-ttu-id="08b13-324">**맬웨어** 방지 정책 파일 형식 블록: 메시지에 식별된 악성 파일 유형으로 인해 필터링된 전자 메일 메시지입니다.</span><span class="sxs-lookup"><span data-stu-id="08b13-324">**Anti-malware policy file type block**: These are email messages filtered out due to the type of malicious file identified in the message.</span></span>
  - <span data-ttu-id="08b13-325">**파일 검색**<sup>1:</sup>안전한 첨부 파일로 검색</span><span class="sxs-lookup"><span data-stu-id="08b13-325">**File detonation**<sup>1</sup>: Detection by Safe Attachments.</span></span>
  - <span data-ttu-id="08b13-326">**악성 파일 신뢰도**</span><span class="sxs-lookup"><span data-stu-id="08b13-326">**Malicious file reputation**</span></span>
  - <span data-ttu-id="08b13-327">**맬웨어 ZAP**<sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="08b13-327">**Malware ZAP**<sup>2</sup></span></span>
  - <span data-ttu-id="08b13-328">**기타**</span><span class="sxs-lookup"><span data-stu-id="08b13-328">**Others**</span></span>

  ![위협 방지 상태 보고서의 맬웨어에 대한 검색 기술 보기](../../media/threat-protection-status-report-malware-detection-tech-view.png)

- <span data-ttu-id="08b13-330">**정책 유형 및** 데이터 보기: 전자 메일 피싱 또는 데이터 **보기: \>** 전자 메일 **\> 맬웨어:** 다음 정보가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="08b13-330">**Break down by: Policy type** and **View data by: Email \> Phish** or **View data by: Email \> Malware**: The following information is shown:</span></span>

  - <span data-ttu-id="08b13-331">**맬웨어 방지**</span><span class="sxs-lookup"><span data-stu-id="08b13-331">**Anti-malware**</span></span>
  - <span data-ttu-id="08b13-332">**안전한 첨부 파일**<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="08b13-332">**Safe Attachments**<sup>1</sup></span></span>
  - <span data-ttu-id="08b13-333">**피싱 방지**</span><span class="sxs-lookup"><span data-stu-id="08b13-333">**Anti-phish**</span></span>
  - <span data-ttu-id="08b13-334">**스팸 방지**</span><span class="sxs-lookup"><span data-stu-id="08b13-334">**Anti-spam**</span></span>
  - <span data-ttu-id="08b13-335">**메일 흐름 규칙(전송** 규칙으로도 알려지기)</span><span class="sxs-lookup"><span data-stu-id="08b13-335">**Mail flow rule** (also known as a transport rule)</span></span>
  - <span data-ttu-id="08b13-336">**기타**</span><span class="sxs-lookup"><span data-stu-id="08b13-336">**Others**</span></span>

  ![위협 방지 상태 보고서의 피싱 전자 메일에 대한 정책 유형 보기](../../media/threat-protection-status-report-phishing-policy-type-view.png)

- <span data-ttu-id="08b13-338">**다음으로** 세분화: 배달 상태 및 데이터 보기: 전자 메일 **\> 피싱** 또는 데이터 보기: 전자 메일 **\> 맬웨어:** 다음 정보가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="08b13-338">**Break down by: Delivery status** and **View data by: Email \> Phish** or **View data by: Email \> Malware**: The following information is shown:</span></span>

  - <span data-ttu-id="08b13-339">**배달 실패**</span><span class="sxs-lookup"><span data-stu-id="08b13-339">**Delivery failed**</span></span>
  - <span data-ttu-id="08b13-340">**삭제**</span><span class="sxs-lookup"><span data-stu-id="08b13-340">**Dropped**</span></span>
  - <span data-ttu-id="08b13-341">**전달된 경우**</span><span class="sxs-lookup"><span data-stu-id="08b13-341">**Forwarded**</span></span>
  - <span data-ttu-id="08b13-342">**호스트된 사서함: 사용자 지정 폴더**</span><span class="sxs-lookup"><span data-stu-id="08b13-342">**Hosted mailbox: Custom folder**</span></span>
  - <span data-ttu-id="08b13-343">**호스트된 사서함: 삭제된 항목**</span><span class="sxs-lookup"><span data-stu-id="08b13-343">**Hosted mailbox: Deleted items**</span></span>
  - <span data-ttu-id="08b13-344">**호스트된 사서함: 받은 편지함**</span><span class="sxs-lookup"><span data-stu-id="08b13-344">**Hosted mailbox: Inbox**</span></span>
  - <span data-ttu-id="08b13-345">**호스트된 사서함: 정크 메일함**</span><span class="sxs-lookup"><span data-stu-id="08b13-345">**Hosted mailbox: Junk**</span></span>
  - <span data-ttu-id="08b13-346">**On-premises server: Delivered**</span><span class="sxs-lookup"><span data-stu-id="08b13-346">**On-premises server: Delivered**</span></span>
  - <span data-ttu-id="08b13-347">**격리**</span><span class="sxs-lookup"><span data-stu-id="08b13-347">**Quarantine**</span></span>

  ![위협 방지 상태 보고서에서 피싱 전자 메일의 배달 상태 보기](../../media/threat-protection-status-report-phishing-delivery-status-view.png)

<span data-ttu-id="08b13-349"><sup>1</sup> Office 365용 Defender만</span><span class="sxs-lookup"><span data-stu-id="08b13-349"><sup>1</sup> Defender for Office 365 only</span></span>

<span data-ttu-id="08b13-350"><sup>2</sup> ZAP(제로 아워 자동 비우기)는 독립 실행형 EOP에서 사용할 수 없습니다(Exchange Online 사서함에서만 작동).</span><span class="sxs-lookup"><span data-stu-id="08b13-350"><sup>2</sup> Zero-hour auto purge (ZAP) isn't available in standalone EOP (it only works in Exchange Online mailboxes).</span></span>

<span data-ttu-id="08b13-351">필터를 클릭하면 사용 가능한 필터는 보고 있는 차트에 따라 달라 습니다.</span><span class="sxs-lookup"><span data-stu-id="08b13-351">If you click **Filters**, the filters available depends on the chart you were looking at:</span></span>

- <span data-ttu-id="08b13-352">콘텐츠 **맬웨어를 \>** 통해 데이터 보기:  시작 날짜 및 종료 날짜 및 검색 값으로 보고서를 수정할 **수** 있습니다.</span><span class="sxs-lookup"><span data-stu-id="08b13-352">For **View data by: Content \> Malware**, you can modify the report by **Start date** and **End date**, and the **Detection** value.</span></span>

- <span data-ttu-id="08b13-353">데이터 **보기의 경우 다음** 필터를 사용하여 보고서를 수정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="08b13-353">For **View data by: Message Override**, you can modify the report with the following filters:</span></span>

  - <span data-ttu-id="08b13-354">**시작 날짜** 및 **종료 날짜**</span><span class="sxs-lookup"><span data-stu-id="08b13-354">**Start date** and **End date**</span></span>
  - <span data-ttu-id="08b13-355">**이유 오버라이드**</span><span class="sxs-lookup"><span data-stu-id="08b13-355">**Override Reason**</span></span>
  - <span data-ttu-id="08b13-356">**태그:** 지정된 사용자 태그가 적용된 사용자 또는 그룹(우선 순위 계정 포함)을 사용하여 결과를 필터링합니다.</span><span class="sxs-lookup"><span data-stu-id="08b13-356">**Tag**: Filter the results by users or groups that have had the specified user tag applied (including priority accounts).</span></span> <span data-ttu-id="08b13-357">사용자 태그에 대한 자세한 내용은 [사용자 태그를 참조하세요.](user-tags.md)</span><span class="sxs-lookup"><span data-stu-id="08b13-357">For more information about user tags, see [User tags](user-tags.md).</span></span>
  - <span data-ttu-id="08b13-358">**도메인**</span><span class="sxs-lookup"><span data-stu-id="08b13-358">**Domain**</span></span>

- <span data-ttu-id="08b13-359">다른 모든 보기의 경우 다음 필터를 사용하여 보고서를 수정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="08b13-359">For all other views, you can modify the report with the following filters:</span></span>

  - <span data-ttu-id="08b13-360">**시작 날짜** 및 **종료 날짜**</span><span class="sxs-lookup"><span data-stu-id="08b13-360">**Start date** and **End date**</span></span>
  - <span data-ttu-id="08b13-361">**감지**</span><span class="sxs-lookup"><span data-stu-id="08b13-361">**Detection**</span></span>
  - <span data-ttu-id="08b13-362">**보호:** **ATP** 또는 **EOP**</span><span class="sxs-lookup"><span data-stu-id="08b13-362">**Protected by**: **ATP** or **EOP**</span></span>
  - <span data-ttu-id="08b13-363">**태그:** 지정된 사용자 태그가 적용된 사용자 또는 그룹(우선 순위 계정 포함)을 사용하여 결과를 필터링합니다.</span><span class="sxs-lookup"><span data-stu-id="08b13-363">**Tag**: Filter the results by users or groups that have had the specified user tag applied (including priority accounts).</span></span> <span data-ttu-id="08b13-364">사용자 태그에 대한 자세한 내용은 [사용자 태그를 참조하세요.](user-tags.md)</span><span class="sxs-lookup"><span data-stu-id="08b13-364">For more information about user tags, see [User tags](user-tags.md).</span></span>
  - <span data-ttu-id="08b13-365">**도메인**</span><span class="sxs-lookup"><span data-stu-id="08b13-365">**Domain**</span></span>

### <a name="details-table-view-for-the-threat-protection-status-report"></a><span data-ttu-id="08b13-366">위협 방지 상태 보고서에 대한 세부 정보 테이블 보기</span><span class="sxs-lookup"><span data-stu-id="08b13-366">Details table view for the Threat protection status report</span></span>

<span data-ttu-id="08b13-367">세부 **정보** 표 보기를 클릭하면 표시되는 정보는 보고 있는 차트에 따라 다를 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="08b13-367">If you click **View details table**, the information that's shown depends on the chart you were looking at:</span></span>

- <span data-ttu-id="08b13-368">**데이터 보기: 개요:** 세부 **정보 테이블** 보기 단추를 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="08b13-368">**View data by: Overview**: No **View details table** button is available.</span></span>

- <span data-ttu-id="08b13-369">**데이터 보기: \> 콘텐츠 맬웨어**:</span><span class="sxs-lookup"><span data-stu-id="08b13-369">**View data by: Content \> Malware**:</span></span>

  - <span data-ttu-id="08b13-370">**날짜**</span><span class="sxs-lookup"><span data-stu-id="08b13-370">**Date**</span></span>
  - <span data-ttu-id="08b13-371">**위치**</span><span class="sxs-lookup"><span data-stu-id="08b13-371">**Location**</span></span>
  - <span data-ttu-id="08b13-372">**지시**</span><span class="sxs-lookup"><span data-stu-id="08b13-372">**Directed by**</span></span>
  - <span data-ttu-id="08b13-373">**맬웨어 이름**</span><span class="sxs-lookup"><span data-stu-id="08b13-373">**Malware name**</span></span>

  <span data-ttu-id="08b13-374">이 보기에서 **필터를** 클릭하면 시작 날짜와  종료 날짜 및 검색 값으로 보고서를 **수정할** **수** 있습니다.</span><span class="sxs-lookup"><span data-stu-id="08b13-374">If you click **Filters** in this view, you can modify the report by **Start date** and **End date**, and the **Detection** value.</span></span>

- <span data-ttu-id="08b13-375">**데이터 보기: 메시지 오버라이드:**</span><span class="sxs-lookup"><span data-stu-id="08b13-375">**View data by: Message Override**:</span></span>

  - <span data-ttu-id="08b13-376">**날짜**</span><span class="sxs-lookup"><span data-stu-id="08b13-376">**Date**</span></span>
  - <span data-ttu-id="08b13-377">**제목**</span><span class="sxs-lookup"><span data-stu-id="08b13-377">**Subject**</span></span>
  - <span data-ttu-id="08b13-378">**보낸 사람**</span><span class="sxs-lookup"><span data-stu-id="08b13-378">**Sender**</span></span>
  - <span data-ttu-id="08b13-379">**받는 사람**</span><span class="sxs-lookup"><span data-stu-id="08b13-379">**Recipients**</span></span>
  - <span data-ttu-id="08b13-380">**검색한 경우**</span><span class="sxs-lookup"><span data-stu-id="08b13-380">**Detected by**</span></span>
  - <span data-ttu-id="08b13-381">**이유 오버라이드**</span><span class="sxs-lookup"><span data-stu-id="08b13-381">**Override Reason**</span></span>
  - <span data-ttu-id="08b13-382">**손상의 원본**</span><span class="sxs-lookup"><span data-stu-id="08b13-382">**Source of Compromise**</span></span>
  - <span data-ttu-id="08b13-383">**태그**</span><span class="sxs-lookup"><span data-stu-id="08b13-383">**Tags**</span></span>

  <span data-ttu-id="08b13-384">이 보기에서 **필터를** 클릭하면 다음 필터를 사용하여 보고서를 수정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="08b13-384">If you click **Filters** in this view, you can modify the report with the following filters:</span></span>

  - <span data-ttu-id="08b13-385">**시작 날짜** 및 **종료 날짜**</span><span class="sxs-lookup"><span data-stu-id="08b13-385">**Start date** and **End date**</span></span>
  - <span data-ttu-id="08b13-386">**이유 오버라이드**</span><span class="sxs-lookup"><span data-stu-id="08b13-386">**Override Reason**</span></span>
  - <span data-ttu-id="08b13-387">**태그:** 지정된 사용자 태그가 적용된 사용자 또는 그룹(우선 순위 계정 포함)을 사용하여 결과를 필터링합니다.</span><span class="sxs-lookup"><span data-stu-id="08b13-387">**Tag**: Filter the results by users or groups that have had the specified user tag applied (including priority accounts).</span></span> <span data-ttu-id="08b13-388">사용자 태그에 대한 자세한 내용은 [사용자 태그를 참조하세요.](user-tags.md)</span><span class="sxs-lookup"><span data-stu-id="08b13-388">For more information about user tags, see [User tags](user-tags.md).</span></span>
  - <span data-ttu-id="08b13-389">**도메인**</span><span class="sxs-lookup"><span data-stu-id="08b13-389">**Domain**</span></span>
  - <span data-ttu-id="08b13-390">**받는 사람(이** 필터링 가능한 속성은 세부 정보 표 보기에서만 사용할 수 있습니다.)</span><span class="sxs-lookup"><span data-stu-id="08b13-390">**Recipients** (Note that this filterable property is only available in the details table view)</span></span>

- <span data-ttu-id="08b13-391">다른 모든 차트:</span><span class="sxs-lookup"><span data-stu-id="08b13-391">All other charts:</span></span>

  - <span data-ttu-id="08b13-392">**날짜**</span><span class="sxs-lookup"><span data-stu-id="08b13-392">**Date**</span></span>
  - <span data-ttu-id="08b13-393">**제목**</span><span class="sxs-lookup"><span data-stu-id="08b13-393">**Subject**</span></span>
  - <span data-ttu-id="08b13-394">**보낸 사람**</span><span class="sxs-lookup"><span data-stu-id="08b13-394">**Sender**</span></span>
  - <span data-ttu-id="08b13-395">**받는 사람**</span><span class="sxs-lookup"><span data-stu-id="08b13-395">**Recipients**</span></span>
  - <span data-ttu-id="08b13-396">**검색한 경우**</span><span class="sxs-lookup"><span data-stu-id="08b13-396">**Detected by**</span></span>
  - <span data-ttu-id="08b13-397">**배달 상태**</span><span class="sxs-lookup"><span data-stu-id="08b13-397">**Delivery Status**</span></span>
  - <span data-ttu-id="08b13-398">**손상의 원본**</span><span class="sxs-lookup"><span data-stu-id="08b13-398">**Source of Compromise**</span></span>
  - <span data-ttu-id="08b13-399">**태그**</span><span class="sxs-lookup"><span data-stu-id="08b13-399">**Tags**</span></span>

  <span data-ttu-id="08b13-400">필터를 **클릭하면** 다음 필터를 사용하여 보고서를 수정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="08b13-400">If you click **Filters**, you can modify the report with the following filters:</span></span>

  - <span data-ttu-id="08b13-401">**시작 날짜** 및 **종료 날짜**</span><span class="sxs-lookup"><span data-stu-id="08b13-401">**Start date** and **End date**</span></span>
  - <span data-ttu-id="08b13-402">**감지**</span><span class="sxs-lookup"><span data-stu-id="08b13-402">**Detection**</span></span>
  - <span data-ttu-id="08b13-403">**보호:** **Office 365** 또는 **EOP용 Defender**</span><span class="sxs-lookup"><span data-stu-id="08b13-403">**Protected by**: **Defender for Office 365** or **EOP**</span></span>
  - <span data-ttu-id="08b13-404">**태그:** 지정된 사용자 태그가 적용된 사용자 또는 그룹(우선 순위 계정 포함)을 사용하여 결과를 필터링합니다.</span><span class="sxs-lookup"><span data-stu-id="08b13-404">**Tag**: Filter the results by users or groups that have had the specified user tag applied (including priority accounts).</span></span> <span data-ttu-id="08b13-405">사용자 태그에 대한 자세한 내용은 [사용자 태그를 참조하세요.](user-tags.md)</span><span class="sxs-lookup"><span data-stu-id="08b13-405">For more information about user tags, see [User tags](user-tags.md).</span></span>
  - <span data-ttu-id="08b13-406">**도메인**</span><span class="sxs-lookup"><span data-stu-id="08b13-406">**Domain**</span></span>
  - <span data-ttu-id="08b13-407">**받는 사람(이** 필터링 가능한 속성은 세부 정보 표 보기에서만 사용할 수 있습니다.)</span><span class="sxs-lookup"><span data-stu-id="08b13-407">**Recipients** (Note that this filterable property is only available in the details table view)</span></span>

## <a name="top-malware-report"></a><span data-ttu-id="08b13-408">상위 맬웨어 보고서</span><span class="sxs-lookup"><span data-stu-id="08b13-408">Top malware report</span></span>

<span data-ttu-id="08b13-409">상위 **맬웨어** 보고서는 [EOP에서](anti-malware-protection.md)맬웨어 방지 보호 기능으로 검색된 다양한 종류의 맬웨어를 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="08b13-409">The **Top malware** report shows the various kinds of malware that was detected by [anti-malware protection in EOP](anti-malware-protection.md).</span></span>

<span data-ttu-id="08b13-410">보고서를 표시하려면 보안 및 준수 [센터를 &](https://protection.office.com)보고서  대시보드로 이동하여 상위 맬웨어를 \>  **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="08b13-410">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Top malware**.</span></span> <span data-ttu-id="08b13-411">보고서로 직접 이동하기 위해 를 열 수 <https://protection.office.com/reportv2?id=TopMalware> 있습니다.</span><span class="sxs-lookup"><span data-stu-id="08b13-411">To go directly to the report, open <https://protection.office.com/reportv2?id=TopMalware>.</span></span>

![보고서 대시보드의 상위 맬웨어 위젯](../../media/top-malware-report-widget.png)

<span data-ttu-id="08b13-413">파이 차트에서 에지 위에 마우스를 대면 맬웨어의 종류 이름과 해당 맬웨어가 있는 것으로 감지된 메시지 수를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="08b13-413">When you hover over a wedge in the pie chart, you can see the name of a kind of malware and how many messages were detected as having that malware.</span></span>

![상위 맬웨어 보고서 보기](../../media/top-malware-report-view.png)

<span data-ttu-id="08b13-415">세부 정보 표 보기를 **클릭하면** 다음 세부 정보를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="08b13-415">If you click **View details table**, you can see the following details:</span></span>

- <span data-ttu-id="08b13-416">**상위 맬웨어**</span><span class="sxs-lookup"><span data-stu-id="08b13-416">**Top malware**</span></span>
- <span data-ttu-id="08b13-417">**개수**</span><span class="sxs-lookup"><span data-stu-id="08b13-417">**Count**</span></span>

<span data-ttu-id="08b13-418">보고서 보기 또는 세부 정보 테이블 보기에서 **필터를** 클릭하면 시작  날짜와 종료 날짜가 있는 날짜 범위를 **지정할 수 있습니다.**</span><span class="sxs-lookup"><span data-stu-id="08b13-418">If you click **Filters** in the report view or details table view, you can specify a date range with **Start date** and **End date**.</span></span>

## <a name="url-threat-protection-report"></a><span data-ttu-id="08b13-419">URL 위협 방지 보고서</span><span class="sxs-lookup"><span data-stu-id="08b13-419">URL threat protection report</span></span>

<span data-ttu-id="08b13-420">**URL 위협 방지 보고서는** Microsoft Defender for Office 365에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="08b13-420">The **URL threat protection report** is available in Microsoft Defender for Office 365.</span></span> <span data-ttu-id="08b13-421">자세한 내용은 URL 위협 방지 [보고서를 참조하세요.](view-reports-for-atp.md#url-threat-protection-report)</span><span class="sxs-lookup"><span data-stu-id="08b13-421">For more information, see [URL threat protection report](view-reports-for-atp.md#url-threat-protection-report).</span></span>

## <a name="user-reported-messages-report"></a><span data-ttu-id="08b13-422">사용자가 보고한 메시지 보고서</span><span class="sxs-lookup"><span data-stu-id="08b13-422">User-reported messages report</span></span>

<span data-ttu-id="08b13-423">사용자 **보고** 메시지 보고서에는 사용자가 보고서 메시지 추가 기능을 사용하여 정크 메일, 피싱 시도 또는 양호한 메일로 보고한 전자 메일 메시지에 대한 정보가 [표시됩니다.](enable-the-report-message-add-in.md)</span><span class="sxs-lookup"><span data-stu-id="08b13-423">The **User-reported messages** report shows information about email messages that users have reported as junk, phishing attempts, or good mail by using the [Report Message add-in](enable-the-report-message-add-in.md).</span></span>

<span data-ttu-id="08b13-424">조직에 대해 구성된 스팸 정책 예외 또는 메일 흐름 규칙과 같은 배달 이유를 포함하여 각 메시지에 대한 세부 정보를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="08b13-424">Details are available for each message, including the delivery reason, such a spam policy exception or mail flow rule configured for your organization.</span></span> <span data-ttu-id="08b13-425">세부 정보를 확인하려면 사용자 보고서 목록에서 항목을 선택한 다음 요약  및 세부 정보 탭에서 정보를 **볼** 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="08b13-425">To view details, select an item in the user-reports list, and then view the information on the **Summary** and **Details** tabs.</span></span>

![User-Reported 메시지 보고서에는 정크 메일이 아닌 정크 메일 또는 피싱 시도로 레이블이 지정되어 있는 메시지가 표시됩니다.](../../media/ad5e9a3d-b833-419c-bcc9-3425d9604ead.png)

<span data-ttu-id="08b13-427">이 보고서를 보시고 보안 & [준수 센터에서](https://protection.office.com)다음 중 하나를 합니다.</span><span class="sxs-lookup"><span data-stu-id="08b13-427">To view this report, in the [Security & Compliance Center](https://protection.office.com), do one of the following:</span></span>

- <span data-ttu-id="08b13-428">위협  관리 \> **대시보드 사용자가** \> **보고한 메시지로 이동하십시오.**</span><span class="sxs-lookup"><span data-stu-id="08b13-428">Go to **Threat management** \> **Dashboard** \> **User-reported messages**.</span></span>

- <span data-ttu-id="08b13-429">위협  관리 \> **검토 사용자가** \> **보고한 메시지로 이동하십시오.**</span><span class="sxs-lookup"><span data-stu-id="08b13-429">Go to **Threat management** \> **Review** \> **User-reported messages**.</span></span>

![보안 및 & 센터에서 위협 관리 \> 검토 \> 사용자가 보고한 메시지를 선택](../../media/e372c57c-1414-4616-957b-bc933b8c8711.png)

> [!IMPORTANT]
> <span data-ttu-id="08b13-431">사용자 보고 메시지 보고서가 제대로 작동하려면  Office 365 환경에 대해 감사 로깅을 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="08b13-431">In order for the User-reported messages report to work correctly, **audit logging must be turned on** for your Office 365 environment.</span></span> <span data-ttu-id="08b13-432">이 작업은 일반적으로 Exchange Online에 할당된 감사 로그 역할이 있는 사용자가 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="08b13-432">This is typically done by someone who has the Audit Logs role assigned in Exchange Online.</span></span> <span data-ttu-id="08b13-433">자세한 내용은 Microsoft 365 감사 로그 검색 설정 또는 [해제를 참조하세요.](https://docs.microsoft.com/microsoft-365/compliance/turn-audit-log-search-on-or-off)</span><span class="sxs-lookup"><span data-stu-id="08b13-433">For more information, see [Turn Microsoft 365 audit log search on or off](https://docs.microsoft.com/microsoft-365/compliance/turn-audit-log-search-on-or-off).</span></span>

## <a name="what-permissions-are-needed-to-view-these-reports"></a><span data-ttu-id="08b13-434">이러한 보고서를 보는 데 필요한 사용 권한은 무엇입니까?</span><span class="sxs-lookup"><span data-stu-id="08b13-434">What permissions are needed to view these reports?</span></span>

<span data-ttu-id="08b13-435">이 문서에 설명된 보고서를 보고 사용하려면 Security & 준수 센터에서 다음 역할 그룹 중 하나에 & 합니다.</span><span class="sxs-lookup"><span data-stu-id="08b13-435">In order to view and use the reports described in this article, you need to be a member of one of the following role groups in the Security & Compliance Center:</span></span>

- <span data-ttu-id="08b13-436">**조직 관리**</span><span class="sxs-lookup"><span data-stu-id="08b13-436">**Organization Management**</span></span>
- <span data-ttu-id="08b13-437">**보안 관리자**</span><span class="sxs-lookup"><span data-stu-id="08b13-437">**Security Administrator**</span></span>
- <span data-ttu-id="08b13-438">**보안 읽기**</span><span class="sxs-lookup"><span data-stu-id="08b13-438">**Security Reader**</span></span>
- <span data-ttu-id="08b13-439">**전역 읽기**</span><span class="sxs-lookup"><span data-stu-id="08b13-439">**Global Reader**</span></span>

<span data-ttu-id="08b13-440">자세한 내용은 [보안 및 준수 센터의 사용 권한](permissions-in-the-security-and-compliance-center.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="08b13-440">For more information, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

<span data-ttu-id="08b13-441">**참고:** Microsoft 365 관리 센터에서 해당 Azure Active Directory 역할에 사용자를 추가하면 사용자에게 보안  & 준수 센터의 필요한 사용 권한과 Microsoft 365의 다른 기능에 대한 사용 권한이 부여됩니다.</span><span class="sxs-lookup"><span data-stu-id="08b13-441">**Note**: Adding users to the corresponding Azure Active Directory role in the Microsoft 365 admin center gives users the required permissions in the Security & Compliance Center _and_ permissions for other features in Microsoft 365.</span></span> <span data-ttu-id="08b13-442">자세한 내용은 [관리자 역할 정보](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="08b13-442">For more information, see [About admin roles](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles).</span></span>

## <a name="what-if-the-reports-arent-showing-data"></a><span data-ttu-id="08b13-443">보고서에 데이터가 표시되지 않는 경우 어떻게 하나요?</span><span class="sxs-lookup"><span data-stu-id="08b13-443">What if the reports aren't showing data?</span></span>

<span data-ttu-id="08b13-444">보고서에 데이터가 없는 경우 정책이 올바르게 설정되어 있지 않은지 다시 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="08b13-444">If you are not seeing data in your reports, double-check that your policies are set up correctly.</span></span> <span data-ttu-id="08b13-445">자세한 내용은 [위협으로부터 보호를 참조합니다.](protect-against-threats.md)</span><span class="sxs-lookup"><span data-stu-id="08b13-445">To learn more, see [Protect against threats](protect-against-threats.md).</span></span>

## <a name="related-topics"></a><span data-ttu-id="08b13-446">관련 항목</span><span class="sxs-lookup"><span data-stu-id="08b13-446">Related topics</span></span>

[<span data-ttu-id="08b13-447">EOP의 스팸 방지 및 맬웨어 방지 보호 기능</span><span class="sxs-lookup"><span data-stu-id="08b13-447">Anti-spam and anti-malware protection in EOP</span></span>](anti-spam-and-anti-malware-protection.md)

[<span data-ttu-id="08b13-448">보안 및 준수 센터의 스마트 보고서 및 인사이트</span><span class="sxs-lookup"><span data-stu-id="08b13-448">Smart reports and insights in the Security & Compliance Center</span></span>](reports-and-insights-in-security-and-compliance.md)

[<span data-ttu-id="08b13-449">보안 및 준수 센터에서 & 흐름 보고서 보기</span><span class="sxs-lookup"><span data-stu-id="08b13-449">View mail flow reports in the Security & Compliance Center</span></span>](view-mail-flow-reports.md)

[<span data-ttu-id="08b13-450">Office 365용 Defender에 대한 보고서 보기</span><span class="sxs-lookup"><span data-stu-id="08b13-450">View reports for Defender for Office 365</span></span>](view-reports-for-atp.md)
