---
title: Office 365 Advanced Threat Protection, 맬웨어 보고서, 피싱 보고서, 손상 된 계정, URL 보호 상태, 위협 보고, 보고 위협에 대 한 보고서 보기
ms.author: deniseb
author: denisebmsft
manager: dansimp
ms.date: 01/10/2020
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: e47e838c-d99e-4c0b-b9aa-e66c4fae902f
ms.collection:
- M365-security-compliance
description: 보안 &amp; 및 준수 센터에서 Office 365 Advanced Threat Protection에 대 한 보고서를 찾아서 사용 합니다.
ms.openlocfilehash: a03fc9e14017255faf8c1c7f58cf2baa65823962
ms.sourcegitcommit: 3401f90721e6f7c65152a31c5be1bb91bfe641c0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/11/2020
ms.locfileid: "41022397"
---
# <a name="view-reports-for-office-365-advanced-threat-protection"></a><span data-ttu-id="37fc4-103">Office 365 Advanced Threat Protection에 대 한 보고서 보기</span><span class="sxs-lookup"><span data-stu-id="37fc4-103">View reports for Office 365 Advanced Threat Protection</span></span>

<span data-ttu-id="37fc4-104">조직에 [Office 365 ATP (Advanced Threat Protection](office-365-atp.md) )가 있고 [필요한 사용 권한이](#what-permissions-are-needed-to-view-the-atp-reports)있는 경우 보안 &amp; 및 준수 센터에서 여러 ATP 보고서를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="37fc4-104">If your organization has [Office 365 Advanced Threat Protection](office-365-atp.md) (ATP) and you have the [necessary permissions](#what-permissions-are-needed-to-view-the-atp-reports), you can use several ATP reports in the Security &amp; Compliance Center.</span></span> <span data-ttu-id="37fc4-105">( **보고서** \> **대시보드로**이동 합니다.)</span><span class="sxs-lookup"><span data-stu-id="37fc4-105">(Go to **Reports** \> **Dashboard**.)</span></span>
  
![보안&amp; 규정 준수 센터 대시보드는 Advanced Threat Protection이 작업 중인 위치를 확인할 수 있도록 도와줍니다](../media/6b213d34-adbb-44af-8549-be9a7e2db087.png)
  
<span data-ttu-id="37fc4-107">ATP 보고서에는 다음이 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="37fc4-107">ATP reports include the following:</span></span>
- [<span data-ttu-id="37fc4-108">위협 방지 상태 보고서</span><span class="sxs-lookup"><span data-stu-id="37fc4-108">Threat Protection Status report</span></span>](#threat-protection-status-report)
- [<span data-ttu-id="37fc4-109">ATP 파일 형식 보고서</span><span class="sxs-lookup"><span data-stu-id="37fc4-109">ATP File Types report</span></span>](#atp-file-types-report)
- [<span data-ttu-id="37fc4-110">ATP 메시지 폐기 보고서</span><span class="sxs-lookup"><span data-stu-id="37fc4-110">ATP Message Disposition report</span></span>](#atp-message-disposition-report)
- <span data-ttu-id="37fc4-111">[실시간 검색 또는 탐색기](threat-explorer.md) (OFFICE 365 ATP 계획 1 또는 2 중 어떤 것이 있는지에 따라 다름)</span><span class="sxs-lookup"><span data-stu-id="37fc4-111">either [real-time detections or Explorer](threat-explorer.md) (depending on whether you have Office 365 ATP Plan 1 or 2)</span></span>
- <span data-ttu-id="37fc4-112">... [등](#additional-reports-to-view)이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="37fc4-112">... [and more](#additional-reports-to-view).</span></span> 

<span data-ttu-id="37fc4-113">이 문서를 읽으면 ATP 보고서에 대 한 개요를 확인 하 고 사용 하는 방법을 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="37fc4-113">Read this article to get an overview of ATP reports and how to use them.</span></span>
  
## <a name="threat-protection-status-report"></a><span data-ttu-id="37fc4-114">위협 방지 상태 보고서</span><span class="sxs-lookup"><span data-stu-id="37fc4-114">Threat Protection Status report</span></span>

<span data-ttu-id="37fc4-115">**위협 방지 상태** 보고서는 EOP ( [Exchange Online Protection](exchange-online-protection-overview.md) ) 및 [Office 365 ATP](office-365-atp.md)에 의해 감지 되어 차단 된 악의적인 콘텐츠와 악성 전자 메일에 대 한 정보를 함께 가져오는 단일 보기입니다.</span><span class="sxs-lookup"><span data-stu-id="37fc4-115">The **Threat Protection Status** report is a single view that brings together information about malicious content and malicious email detected and blocked by [Exchange Online Protection](exchange-online-protection-overview.md) (EOP) and [Office 365 ATP](office-365-atp.md).</span></span> <span data-ttu-id="37fc4-116">이 보고서는 시간에 따른 검색 (최대 90 일)을 확인 하는 데 유용 하며, 보안 관리자는 경향을 식별 하거나 정책 조정이 필요한 지 여부를 결정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="37fc4-116">This report is useful for viewing detections over time (up to 90 days), and it enables security administrators to identify trends or determine whether policies need adjustments.</span></span> 

<span data-ttu-id="37fc4-117">이 보고서는 맬웨어 방지 엔진에 의해 차단 된 파일 또는 웹 사이트 주소 (Url), [즉 제로 시간 자동 삭제 (ZAP)](zero-hour-auto-purge.md)및 Atp safe [Links](atp-safe-links.md), atp [안전한 첨부 파일](atp-safe-attachments.md), [atp 피싱 방지 기능과](atp-anti-phishing.md)같은 atp 기능을 사용 하 여 고유한 전자 메일 메시지의 집계 개수를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="37fc4-117">The report provides an aggregated count of unique email messages with malicious content, such as files or website addresses (URLs) that were blocked by the anti-malware engine, [zero-hour auto purge (ZAP)](zero-hour-auto-purge.md), and ATP features like [ATP Safe Links](atp-safe-links.md), [ATP Safe Attachments](atp-safe-attachments.md), and [ATP anti-phishing capabilities](atp-anti-phishing.md).</span></span> 

<span data-ttu-id="37fc4-118">이러한 정보를 필터링 하 고 breakdowns이 보고서의 정보를 보다 세부적으로 분류 하는 데 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="37fc4-118">Filters and breakdowns of the information allow for more granular categorizations of the information in this report.</span></span> <span data-ttu-id="37fc4-119">특히 *전자 메일 > 피싱* 및 *전자 메일 > 맬웨어 보기*에 대 한 ' 중단 기준 ' 메뉴가 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="37fc4-119">Specifically, there is a 'break down by' menu included for *Email > Phish* and *Email > Malware views*.</span></span> <span data-ttu-id="37fc4-120">그러면 다음과 같이 데이터를 분류 합니다.</span><span class="sxs-lookup"><span data-stu-id="37fc4-120">It will break down the data into:</span></span>

| |  |
|---------|---------|
|<span data-ttu-id="37fc4-121">검색 유형별</span><span class="sxs-lookup"><span data-stu-id="37fc4-121">By detection type</span></span>    | <span data-ttu-id="37fc4-122">이러한 위협을 파악 하는 데 도움이 되는 정책은 무엇입니까?</span><span class="sxs-lookup"><span data-stu-id="37fc4-122">What policy helped catch these threats?</span></span>         |
|<span data-ttu-id="37fc4-123">검색 기술</span><span class="sxs-lookup"><span data-stu-id="37fc4-123">By detection technology</span></span>     | <span data-ttu-id="37fc4-124">어떤 기본 Microsoft 기술이 위협을 포착 했습니까?</span><span class="sxs-lookup"><span data-stu-id="37fc4-124">What underlying Microsoft technology caught the threat?</span></span>        |
|<span data-ttu-id="37fc4-125">배달 상태별</span><span class="sxs-lookup"><span data-stu-id="37fc4-125">By delivery status</span></span>     | <span data-ttu-id="37fc4-126">위협으로 검색 된 전자 메일 메시지는 어떻게 되었습니까?</span><span class="sxs-lookup"><span data-stu-id="37fc4-126">What happened to the email messages detected as threats?</span></span>         |
| | |

> [!TIP]
> <span data-ttu-id="37fc4-127">전자 메일 > 피싱 | 맬웨어 보기에는 *ATP에서 생성 된 파일 신뢰도*, *파일 샌드 박싱*, *URL 샌드 박싱*, *스푸핑 방지: DMARC 실패*등의 범주를 포함 하 여 표시 되는 검색 기술에 대 한 자세한 breakdowns 있으며,이를 통해 조직에서 위협을 찾아낼 기능을 정확히 알 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="37fc4-127">Both the Email > Phish | Malware views have granular breakdowns for the detection technologies shown, with categories like *ATP-generated file reputation*, *File detonation*, *URL detonation*, *Anti-spoof: DMARC failure*, for example, helpful in pinpointing exactly which feature led your organization to catch threats.</span></span>

![' 나누기 기준 '이 표시 되는 위협 보호 상태 보고서 드롭다운](../media/tp-threatProtectStatRpt-BreakDownBy.png)

<span data-ttu-id="37fc4-129">이러한 보기는 단추 클릭 (전자 메일 > 피싱, 전자 메일 > 맬웨어 및 콘텐츠 > 맬웨어 보기)을 통해 내보낼 수 있는 옵션을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="37fc4-129">These views give you the option to export, via a button click (in Email > Phish, Email > Malware, and Content > Malware views).</span></span> <span data-ttu-id="37fc4-130">컴퓨터로 내보낸 집계 된 데이터를 Excel에서 열 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="37fc4-130">The aggregated data exported to your computer can be opened in Excel.</span></span>

![이 그래픽은 맬웨어 보기 메뉴의 옵션으로 내보내기, 만들기 일정 및 요청 보고서 간의 오른쪽을 보여 줍니다.](../media/tp-threatProtectStatRpt-BreakDownByExport.png)

<span data-ttu-id="37fc4-132">개요 및 전자 메일 보기에는 24 시간 (요청 다시)이 아닌 처리 시간 내에 정보가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="37fc4-132">The Overview and Emails views will display information within hours of processing rather than in 24 hours (demand re.</span></span> <span data-ttu-id="37fc4-133">여기에서 속도 향상은 명확한 신호입니다.</span><span class="sxs-lookup"><span data-stu-id="37fc4-133">increased speeds here has been a clear signal)!</span></span>

> [!NOTE]
> <span data-ttu-id="37fc4-134">[Office 365 ATP](office-365-atp.md) 또는 [Exchange Online Protection](exchange-online-protection-eop.md) (EOP)이 있는 고객은 위협 보호 상태 보고서를 사용할 수 있습니다. 그러나 ATP 고객에 대 한 위협 방지 상태 보고서에 표시 되는 정보에는 고객에 게 표시 될 수 있는 것과 다른 데이터가 포함 될 가능성이 EOP.</span><span class="sxs-lookup"><span data-stu-id="37fc4-134">A Threat Protection Status report is available to customers who have either [Office 365 ATP](office-365-atp.md) or [Exchange Online Protection](exchange-online-protection-eop.md) (EOP); however, the information that is displayed in the Threat Protection Status report for ATP customers will likely contain different data than what EOP customers might see.</span></span> <span data-ttu-id="37fc4-135">예를 들어 ATP 고객에 대 한 위협 방지 상태 보고서에는 [SharePoint Online, OneDrive 또는 Microsoft 팀에서 검색 된 악성 파일](atp-for-spo-odb-and-teams.md)에 대 한 정보가 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="37fc4-135">For example, the Threat Protection Status report for ATP customers will contain information about [malicious files detected in SharePoint Online, OneDrive, or Microsoft Teams](atp-for-spo-odb-and-teams.md).</span></span> <span data-ttu-id="37fc4-136">이러한 정보는 ATP와 관련 된 것 이므로, EOP가 아닌 고객은 위협 보호 상태 보고서에 해당 세부 정보를 볼 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="37fc4-136">Such information is specific to ATP, so customers who have EOP but not ATP will not see those details in their Threat Protection Status report.</span></span>
  
<span data-ttu-id="37fc4-137">위협 방지 상태 보고서를 보려면 [보안 &amp; 및 준수 센터](https://protection.office.com)에서 **보고서** \> **대시보드** \> **위협 보호 상태로**이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="37fc4-137">To view the Threat Protection Status report, in the [Security &amp; Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** \> **Threat Protection Status**.</span></span>
  
![ATP 위협 방지 상태 보고서](../media/6bdd41eb-62e0-423b-9fd4-d1d5baf0cbd5.png)
  
<span data-ttu-id="37fc4-139">하루 동안 자세한 상태를 보려면 그래프를 가리킵니다.</span><span class="sxs-lookup"><span data-stu-id="37fc4-139">To get detailed status for a day, hover over the graph.</span></span>
  
![ATP 위협 방지 상태 데이터 (일)](../media/d5c2c6ad-c002-4985-a032-c866e46fdea8.png)
  
<span data-ttu-id="37fc4-141">기본적으로 위협 방지 상태 보고서에는 최근 7 일간의 데이터가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="37fc4-141">By default, the Threat Protection Status report shows data for the past seven days.</span></span> <span data-ttu-id="37fc4-142">그러나 **필터** 를 선택 하 고 날짜 범위를 변경 하 여 데이터를 최대 90 일까 지 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="37fc4-142">However, you can choose **Filters** and change the date range to view data for up to 90 days.</span></span> <span data-ttu-id="37fc4-143">평가판 구독을 사용 하는 경우에는 30 일간의 데이터를 제한할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="37fc4-143">(If you are using a trial subscription, you might be limited to 30 days' of data.)</span></span>
  
![ATP 위협 방지 상태 필터](../media/4f703369-642b-402b-9758-b9c828283410.png)
  
<span data-ttu-id="37fc4-145">**데이터 보기 기준** 메뉴를 사용 하 여 보고서에 표시 되는 정보를 변경할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="37fc4-145">You can also use the **View data by** menu to change what information is displayed in the report.</span></span> 
  
![ATP 위협 방지 상태 보고서에 대 한 옵션 보기](../media/4959bf8c-d192-4542-b00b-184e101e7513.png)

## <a name="url-protection-status-report"></a><span data-ttu-id="37fc4-147">URL 보호 상태 보고서</span><span class="sxs-lookup"><span data-stu-id="37fc4-147">URL Protection Status report</span></span>

<span data-ttu-id="37fc4-148">이 보고서는 수집 된 데이터를 기반으로 하며, 클릭 당 검색 되는 위협, 즉 대부분의 다른 전자 메일 위협 관련 보고서는 메시지 데이터에 따라 결정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="37fc4-148">This report is based data collected, and threats detected, per click (whereas most other email threat related reports are per message data).</span></span> <span data-ttu-id="37fc4-149">이 보고서는 전자 메일 메시지 및 문서의 하이퍼링크에서 제공 되는 위협 (클릭 당)을 보여 주도록 디자인 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="37fc4-149">This report is designed to show threats that come from hyperlinks in email messages and documents, per click.</span></span> <span data-ttu-id="37fc4-150">다음과 같은 두 가지 보기가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="37fc4-150">There are two views:</span></span>

|  |  |
|---------|---------|
|<span data-ttu-id="37fc4-151">URL 보호 작업 클릭</span><span class="sxs-lookup"><span data-stu-id="37fc4-151">URL click protection action</span></span>   | <span data-ttu-id="37fc4-152">차단 되었지만 차단 되었지만 사용자가 간편 하 게 클릭 하 여 재정의 되 고 허용 되는 Url 수를 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="37fc4-152">See the number of URLs blocked, blocked but overridden with a click-through by a user, overridden with a click-through by a user, and allowed.</span></span>        |
|<span data-ttu-id="37fc4-153">URL 클릭 응용 프로그램</span><span class="sxs-lookup"><span data-stu-id="37fc4-153">URL click by application</span></span>     | <span data-ttu-id="37fc4-154">URL이 클릭 된 응용 프로그램을 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="37fc4-154">See the application from which the URL was clicked.</span></span>        |
|  |  |

<span data-ttu-id="37fc4-155">정보 테이블에서는 클릭 시간 및 사용자 정보에 대 한 자세한 정보를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="37fc4-155">In the details table, you'll be able to see more information regarding click time and user information.</span></span> <span data-ttu-id="37fc4-156">마지막으로, URL 보호 상태 보고서에는 ATP 안전한 링크 기능의 보호 기능이 표시 되므로 ATP 안전한 링크를 사용 하도록 설정한 고객만이 보고서에 반영 된 데이터를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="37fc4-156">Finally, keep in mind the URL Protection Status report shows the protection from ATP Safe Links feature, so only customers who have enabled ATP Safe Links will see data reflected on this report.</span></span>

> [!NOTE]
> <span data-ttu-id="37fc4-157">이는 *보호 추세 보고서*로, 데이터가 더 큰 데이터 집합의 추세를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="37fc4-157">This is a *protection trend report*, meaning data represents trends in a larger dataset.</span></span> <span data-ttu-id="37fc4-158">실시간으로 보고 기능을 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="37fc4-158">Reporting isn't available in real time here.</span></span> <span data-ttu-id="37fc4-159">실시간 URL에 대해 데이터를 클릭 하 고 계속 해 서 URL 추적을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="37fc4-159">For real time URL click data, please continue to use URL Trace.</span></span>

## <a name="compromised-users-report"></a><span data-ttu-id="37fc4-160">손상 된 사용자 보고서</span><span class="sxs-lookup"><span data-stu-id="37fc4-160">Compromised Users report</span></span>

<span data-ttu-id="37fc4-161">Exchange Online Protection을 사용 하는 모든 사용자가 사용할 수 있는이 보고서에는 의심 스러운 사용자나 제한 된 사용자로 표시 되는, 특히 계정으로 인해 사용자 계정에 문제가 있을 수 있음을 나타내는 상태 중 하나를 입력 하는 것이 좋습니다. 당한.</span><span class="sxs-lookup"><span data-stu-id="37fc4-161">This report, available to anyone with Exchange Online Protection, shows the number of user accounts marked as Suspicious or Restricted users, data particularly useful as accounts enter either of the states that indicate the user account may be problematic, or even compromised.</span></span> <span data-ttu-id="37fc4-162">자주 사용 하는 경우에는 손상 된 사용자 보고서가 스파이크를 볼 수 있으며, 의심 스러운 또는 제한 상태인 계정으로 증거를 제공 하면 보안 및 테 넌 트의 wellness에 문제가 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="37fc4-162">With frequent use, the Compromised User report can spot spikes, and even trends, in accounts marked in suspicious or restricted states, giving evidence there could be an issue with security and the wellness of your tenant.</span></span>

![손상 된 사용자가 Office 365에 표시 되는 대로 보고 합니다.](../media/tp-threatProtectStatRpt-CompromisedUserRpt.png)

## <a name="atp-file-types-report"></a><span data-ttu-id="37fc4-164">ATP 파일 형식 보고서</span><span class="sxs-lookup"><span data-stu-id="37fc4-164">ATP File Types report</span></span>

<span data-ttu-id="37fc4-165">**Atp 파일 형식** 보고서에는 [Atp 안전한 첨부 파일](atp-safe-attachments.md)에 의해 악의적으로 검색 된 파일 유형이 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="37fc4-165">The **ATP File Types** report shows you the type of files detected as malicious by [ATP Safe Attachments](atp-safe-attachments.md).</span></span>
  
<span data-ttu-id="37fc4-166">이 보고서를 보려면 [보안 &amp; 및 준수 센터](https://protection.office.com)에서 **보고서** \> **대시보드** \> **ATP 파일 형식**으로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="37fc4-166">To view this report, in the [Security &amp; Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** \> **ATP File Types**.</span></span>
  
![ATP 파일 형식 보고서](../media/6e3f5d33-79aa-4b2d-938c-6ef135d9e54c.png)
  
<span data-ttu-id="37fc4-168">특정 날짜를 마우스로 가리키면 [ATP 수신 허용 첨부 파일](atp-safe-attachments.md) 및 [Office 365의 스팸 &amp; 방지 바이러스 백신 보호 기능](anti-spam-and-anti-malware-protection.md)에서 검색 된 악의적인 파일의 유형을 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="37fc4-168">When you hover over a particular day, you can see the breakdown of types of malicious files that were detected by [ATP Safe Attachments](atp-safe-attachments.md) and [anti-spam &amp; anti-malware protection in Office 365](anti-spam-and-anti-malware-protection.md).</span></span>
  
![ATP 파일 형식 하루에 대 한 보고서 데이터](../media/10d18428-699a-41d2-a73e-be3a8214ada1.png)
  
## <a name="atp-message-disposition-report"></a><span data-ttu-id="37fc4-170">ATP 메시지 폐기 보고서</span><span class="sxs-lookup"><span data-stu-id="37fc4-170">ATP Message Disposition report</span></span>

<span data-ttu-id="37fc4-171">**ATP 메시지 처리** 보고서에는 악성 콘텐츠가 있는 것으로 검색 된 전자 메일 메시지에 대해 수행 된 작업이 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="37fc4-171">The **ATP Message Disposition** report shows you the actions that were taken for email messages that were detected as having malicious content.</span></span> 
  
<span data-ttu-id="37fc4-172">이 보고서를 보려면 [보안 &amp; 및 준수 센터](https://protection.office.com)에서 **보고서** \> **대시보드** \> **ATP 메시지 처리**로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="37fc4-172">To view this report, in the [Security &amp; Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** \> **ATP Message Disposition**.</span></span>
  
![ATP 메시지 처리 보고서](../media/b0ff65c4-53d3-496d-bafa-8937a5eb69e5.png)
  
<span data-ttu-id="37fc4-174">차트의 막대 위에 마우스를 올리면 해당 요일의 검색 된 전자 메일에 대해 수행한 작업을 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="37fc4-174">When you hover over a bar in the chart, you can see what actions were taken for detected email for that day.</span></span>
  
![ATP 메시지 처리 보고서 데이터 (일)](../media/68d2beb8-4b30-48c4-8ba6-5e8ab88ae456.png)
  
## <a name="additional-reports-to-view"></a><span data-ttu-id="37fc4-176">볼 수 있는 추가 보고서</span><span class="sxs-lookup"><span data-stu-id="37fc4-176">Additional reports to view</span></span>

<span data-ttu-id="37fc4-177">이 문서에서 설명 하는 ATP 보고서 외에도 다음 표에 설명 된 것 처럼 다른 몇 가지 보고서를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="37fc4-177">In addition to the ATP reports described in this article, several other reports are available, as described in the following table:</span></span>

|<span data-ttu-id="37fc4-178">보고서</span><span class="sxs-lookup"><span data-stu-id="37fc4-178">Report(s)</span></span>  |<span data-ttu-id="37fc4-179">세부 정보</span><span class="sxs-lookup"><span data-stu-id="37fc4-179">Details</span></span>  |
|---------|---------|
|<span data-ttu-id="37fc4-180">**탐색기** 또는 **실시간** 검색 (Office 365 ATP 계획 2 고객에 게 탐색기가 있습니다. Office 365 ATP 계획 1 고객은 실시간 검색을 합니다.</span><span class="sxs-lookup"><span data-stu-id="37fc4-180">**Explorer** or **real-time detections** (Office 365 ATP Plan 2 customers have Explorer; Office 365 ATP Plan 1 customers have real-time detections.)</span></span>| [<span data-ttu-id="37fc4-181">위협 탐색기 (실시간 검출)</span><span class="sxs-lookup"><span data-stu-id="37fc4-181">Threat Explorer (and real-time detections)</span></span>](threat-explorer.md)       |
|<span data-ttu-id="37fc4-182">상위 보낸 사람 및 받는 사람 보고서, 스푸핑 메일 보고서, 스팸 감지 보고서 등의 **전자 메일 보안 보고서**</span><span class="sxs-lookup"><span data-stu-id="37fc4-182">**Email security reports**, such as a Top Senders and Recipients report, a Spoof Mail report, and a Spam Detections report.</span></span> | [<span data-ttu-id="37fc4-183">보안 &amp; 및 준수 센터의 전자 메일 보안 보고서 보기</span><span class="sxs-lookup"><span data-stu-id="37fc4-183">View email security reports in the Security &amp; Compliance Center</span></span>](../../compliance/view-email-security-reports.md)        |
|<span data-ttu-id="37fc4-184">**ATP 안전한 링크 URL 추적** (PowerShell을 사용 하 여 생성 하는 보고서) 이 보고서는 지난 7 일 동안 ATP 안전한 링크 작업의 결과를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="37fc4-184">**ATP Safe Links URL trace** (This is a report you generate by using PowerShell.) This report shows the results of ATP Safe Links actions over the past seven (7) days.</span></span> |[<span data-ttu-id="37fc4-185">Get-UrlTrace cmdlet 참조</span><span class="sxs-lookup"><span data-stu-id="37fc4-185">Get-UrlTrace cmdlet reference</span></span>](https://docs.microsoft.com/powershell/module/exchange/advanced-threat-protection/get-urltrace) |
|<span data-ttu-id="37fc4-186">**EOP 및 ATP 결과** (PowerShell을 사용 하 여 생성 하는 사용자 지정 보고서)</span><span class="sxs-lookup"><span data-stu-id="37fc4-186">**EOP and ATP results** (This is a custom report you generate by using PowerShell).</span></span> <span data-ttu-id="37fc4-187">이 보고서에는 도메인, 날짜, 이벤트 유형, 방향, 동작 및 메시지 수와 같은 정보가 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="37fc4-187">This report contains information, such as Domain, Date, Event Type, Direction, Action, and Message Count.</span></span>  | [<span data-ttu-id="37fc4-188">MailTrafficATPReport cmdlet 참조</span><span class="sxs-lookup"><span data-stu-id="37fc4-188">Get-MailTrafficATPReport cmdlet reference</span></span>](https://docs.microsoft.com/powershell/module/exchange/advanced-threat-protection/get-mailtrafficatpreport) |
|<span data-ttu-id="37fc4-189">**EOP 및 ATP** 검색 (PowerShell을 사용 하 여 생성 하는 사용자 지정 보고서)</span><span class="sxs-lookup"><span data-stu-id="37fc4-189">**EOP and ATP detections** (This is a custom report you generate by using PowerShell).</span></span> <span data-ttu-id="37fc4-190">이 보고서에는 악성 파일 또는 Url, 피싱 시도, 가장 및 기타 잠재적 위협 (전자 메일 또는 파일)에 대 한 자세한 정보가 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="37fc4-190">This report contains details about malicious files or URLs, phishing attempts, impersonation, and other potential threats in email or files.</span></span>   | [<span data-ttu-id="37fc4-191">MailDetailATPReport cmdlet 참조</span><span class="sxs-lookup"><span data-stu-id="37fc4-191">Get-MailDetailATPReport cmdlet reference</span></span>](https://docs.microsoft.com/powershell/module/exchange/advanced-threat-protection/get-maildetailatpreport)        |

  
## <a name="what-permissions-are-needed-to-view-the-atp-reports"></a><span data-ttu-id="37fc4-192">ATP 보고서를 표시 하는 데 필요한 사용 권한은 무엇입니까?</span><span class="sxs-lookup"><span data-stu-id="37fc4-192">What permissions are needed to view the ATP reports?</span></span>

<span data-ttu-id="37fc4-193">이 문서에서 설명 하는 보고서를 보고 사용 하려면 **보안 &amp; 및 준수 센터와 Exchange 관리 센터 둘 다에 대해 적절 한 역할이 할당 되어 있어야 합니다**.</span><span class="sxs-lookup"><span data-stu-id="37fc4-193">In order to view and use the reports described in this article, **you must have an appropriate role assigned for both the Security &amp; Compliance Center and the Exchange admin center**.</span></span>

- <span data-ttu-id="37fc4-194">보안 &amp; 및 준수 센터에는 다음 역할 중 하나가 할당 되어 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="37fc4-194">For the Security &amp; Compliance Center, you must have one of the following roles assigned:</span></span>
    - <span data-ttu-id="37fc4-195">조직 관리</span><span class="sxs-lookup"><span data-stu-id="37fc4-195">Organization Management</span></span>
    - <span data-ttu-id="37fc4-196">보안 관리자 (Azure Active Directory 관리 센터[https://aad.portal.azure.com](https://aad.portal.azure.com)에서 할당할 수 있음)</span><span class="sxs-lookup"><span data-stu-id="37fc4-196">Security Administrator (this can be assigned in the Azure Active Directory admin center ([https://aad.portal.azure.com](https://aad.portal.azure.com)))</span></span>
    - <span data-ttu-id="37fc4-197">보안 읽기 권한자</span><span class="sxs-lookup"><span data-stu-id="37fc4-197">Security Reader</span></span>

- <span data-ttu-id="37fc4-198">Exchange Online의 경우 Exchange 관리 센터 ([https://outlook.office365.com/ecp](https://outlook.office365.com/ecp)) 또는 PowerShell Cmdlet ( [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/exchange-online-powershell)참조)에서 다음 역할 중 하나를 할당 받아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="37fc4-198">For Exchange Online, you must have one of the following roles assigned in either the Exchange admin center ([https://outlook.office365.com/ecp](https://outlook.office365.com/ecp)) or with PowerShell cmdlets (See [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/exchange-online-powershell)):</span></span>
    - <span data-ttu-id="37fc4-199">조직 관리</span><span class="sxs-lookup"><span data-stu-id="37fc4-199">Organization Management</span></span>
    - <span data-ttu-id="37fc4-200">보기 전용 조직 관리</span><span class="sxs-lookup"><span data-stu-id="37fc4-200">View-only Organization Management</span></span>
    - <span data-ttu-id="37fc4-201">보기 권한만 있는 받는 사람 역할</span><span class="sxs-lookup"><span data-stu-id="37fc4-201">View-Only Recipients role</span></span>
    - <span data-ttu-id="37fc4-202">준수 관리</span><span class="sxs-lookup"><span data-stu-id="37fc4-202">Compliance Management</span></span>

<span data-ttu-id="37fc4-203">자세한 내용은 다음 리소스를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="37fc4-203">To learn more, see the following resources:</span></span>

- [<span data-ttu-id="37fc4-204">Permissions in the Office 365 Security &amp; Compliance Center</span><span class="sxs-lookup"><span data-stu-id="37fc4-204">Permissions in the Office 365 Security &amp; Compliance Center</span></span>](permissions-in-the-security-and-compliance-center.md)

- [<span data-ttu-id="37fc4-205">Exchange Online의 기능 사용 권한</span><span class="sxs-lookup"><span data-stu-id="37fc4-205">Feature permissions in Exchange Online</span></span>](https://docs.microsoft.com/exchange/permissions-exo/feature-permissions)
   
## <a name="what-if-the-reports-arent-showing-data"></a><span data-ttu-id="37fc4-206">보고서에 데이터가 표시 되지 않으면 어떻게 하나요?</span><span class="sxs-lookup"><span data-stu-id="37fc4-206">What if the reports aren't showing data?</span></span>

<span data-ttu-id="37fc4-207">ATP 보고서에 데이터가 표시 되지 않는 경우 정책이 올바르게 설정 되어 있는지 다시 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="37fc4-207">If you are not seeing data in your ATP reports, double-check that your policies are set up correctly.</span></span> <span data-ttu-id="37fc4-208">조직에 atp 보호 기능을 적용 하려면 atp [안전한 링크 정책](set-up-atp-safe-links-policies.md) 및 [Atp 안전 첨부 파일 정책이](set-up-atp-safe-attachments-policies.md) 정의 되어 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="37fc4-208">Your organization must have [ATP Safe Links policies](set-up-atp-safe-links-policies.md) and [ATP Safe Attachments policies](set-up-atp-safe-attachments-policies.md) defined in order for ATP protection to be in place.</span></span> <span data-ttu-id="37fc4-209">또한 [Office 365에서 스팸 방지 및 맬웨어 방지 보호 기능을](anti-spam-and-anti-malware-protection.md)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="37fc4-209">Also see [Anti-spam and anti-malware protection in Office 365](anti-spam-and-anti-malware-protection.md).</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="37fc4-210">관련 항목</span><span class="sxs-lookup"><span data-stu-id="37fc4-210">Related topics</span></span>

[<span data-ttu-id="37fc4-211">Office 365 보안 &amp; 및 준수 센터의 보고서 및 정보</span><span class="sxs-lookup"><span data-stu-id="37fc4-211">Reports and insights in the Office 365 Security &amp; Compliance Center</span></span>](reports-and-insights-in-security-and-compliance.md)
  
[<span data-ttu-id="37fc4-212">보안 &amp; 및 준수 센터에서 보고서 일정 만들기</span><span class="sxs-lookup"><span data-stu-id="37fc4-212">Create a schedule for a report in the Security &amp; Compliance Center</span></span>](create-a-schedule-for-a-report.md)
  
[<span data-ttu-id="37fc4-213">보안 &amp; 및 준수 센터에서 사용자 지정 보고서 설정 및 다운로드</span><span class="sxs-lookup"><span data-stu-id="37fc4-213">Set up and download a custom report in the Security &amp; Compliance Center</span></span>](set-up-and-download-a-custom-report.md)
  

