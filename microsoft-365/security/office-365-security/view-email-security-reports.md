---
title: 전자 메일 보안 보고서 보기 보안 & 준수 센터, 손상 된 사용자, 암호화, 위협 방지 상태, 맬웨어 감지, 상위 맬웨어, 스팸 감지, 보낸 날짜, 받은 전자 메일, 사용자가 보고 한 메시지, 읽기 보고서, 검색, 보안 데이터, 보안 정보
f1.keywords:
- NOCSH
ms.author: tracyp
author: msfttracyp
manager: dansimp
ms.date: 01/16/2020
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 3a137e28-1174-42d5-99af-f18868b43e86
ms.collection:
- M365-security-compliance
description: 조직의 전자 메일 보안 보고서를 찾아서 사용 하는 방법에 대해 알아봅니다. 보안 & 준수 센터에서 전자 메일 보안 보고서를 사용할 수 있습니다.
ms.openlocfilehash: d99186e4f3a2831eb794d31a33fa4d56af2cc7a4
ms.sourcegitcommit: 9ed3283dd6dd959faeca5c22613f9126261b9590
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/16/2020
ms.locfileid: "43529076"
---
# <a name="view-email-security-reports-in-the-security--compliance-center"></a><span data-ttu-id="8e6ec-104">보안 및 준수 센터의 전자 메일 보안 보고서 보기</span><span class="sxs-lookup"><span data-stu-id="8e6ec-104">View email security reports in the Security & Compliance Center</span></span>

<span data-ttu-id="8e6ec-105">[보안 & 준수 센터](https://protection.office.com) 에서 다양 한 보고서를 사용할 수 있으며, Office 365의 스팸 방지, 맬웨어 방지 및 암호화 기능과 같은 전자 메일 보안 기능이 조직을 보호 하는 방법을 확인 하는 데 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8e6ec-105">A variety of reports are available in the [Security & Compliance Center](https://protection.office.com) to help you see how email security features, such as anti-spam, anti-malware, and encryption features in Office 365 are protecting your organization.</span></span> <span data-ttu-id="8e6ec-106">[필요한 권한이](#what-permissions-are-needed-to-view-these-reports)있는 경우 **보고서** \> **대시보드로**이동 하 여 보안 & 준수 센터에서 이러한 보고서를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8e6ec-106">If you have the [necessary permissions](#what-permissions-are-needed-to-view-these-reports), you can view these reports in the Security & Compliance Center by going to **Reports** \> **Dashboard**.</span></span>

![보안 & 준수 센터의 보고서 대시보드](../../media/6b213d34-adbb-44af-8549-be9a7e2db087.png)

<span data-ttu-id="8e6ec-108">전자 메일 보안 보고서에는 다음이 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8e6ec-108">Your email security reports include the following:</span></span>

- <span data-ttu-id="8e6ec-109">[URL 위협 방지 보고서](#url-threat-protection-report-new) (**신규!**)</span><span class="sxs-lookup"><span data-stu-id="8e6ec-109">[URL Threat Protection report](#url-threat-protection-report-new) (**NEW!**)</span></span>
- [<span data-ttu-id="8e6ec-110">손상 된 사용자 보고서</span><span class="sxs-lookup"><span data-stu-id="8e6ec-110">Compromised Users report</span></span>](#compromised-users-report)
- [<span data-ttu-id="8e6ec-111">암호화 보고서</span><span class="sxs-lookup"><span data-stu-id="8e6ec-111">Encryption report</span></span>](#encryption-report)
- [<span data-ttu-id="8e6ec-112">위협 방지 상태 보고서</span><span class="sxs-lookup"><span data-stu-id="8e6ec-112">Threat Protection Status report</span></span>](#threat-protection-status-report)
- [<span data-ttu-id="8e6ec-113">맬웨어 감지 보고서</span><span class="sxs-lookup"><span data-stu-id="8e6ec-113">Malware Detections report</span></span>](#malware-detections-report)
- [<span data-ttu-id="8e6ec-114">주요 맬웨어 보고서</span><span class="sxs-lookup"><span data-stu-id="8e6ec-114">Top Malware report</span></span>](#top-malware-report)
- [<span data-ttu-id="8e6ec-115">상위 보낸 사람 및 받는 사람 보고서</span><span class="sxs-lookup"><span data-stu-id="8e6ec-115">Top Senders and Recipients report</span></span>](#top-senders-and-recipients-report)
- [<span data-ttu-id="8e6ec-116">스푸핑 감지 보고서</span><span class="sxs-lookup"><span data-stu-id="8e6ec-116">Spoof Detections report</span></span>](#spoof-detections-report)
- [<span data-ttu-id="8e6ec-117">스팸 감지 보고서</span><span class="sxs-lookup"><span data-stu-id="8e6ec-117">Spam Detections report</span></span>](#spam-detections-report)
- [<span data-ttu-id="8e6ec-118">보내고 받은 전자 메일 보고서</span><span class="sxs-lookup"><span data-stu-id="8e6ec-118">Sent and received email report</span></span>](#sent-and-received-email-report)
- [<span data-ttu-id="8e6ec-119">사용자가 보고 한 메시지 보고서</span><span class="sxs-lookup"><span data-stu-id="8e6ec-119">User-reported messages report</span></span>](#user-reported-messages-report)

## <a name="url-threat-protection-report-new"></a><span data-ttu-id="8e6ec-120">URL 위협 방지 보고서 (**신규!**)</span><span class="sxs-lookup"><span data-stu-id="8e6ec-120">URL Threat Protection report (**NEW!**)</span></span>

<span data-ttu-id="8e6ec-121">URL 위협 방지 보고서는 다음 사용자에 게 제공 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8e6ec-121">The URL Threat Protection report is available to anyone with:</span></span>

- <span data-ttu-id="8e6ec-122">Exchange Online Protection *및* Advanced Threat protection 추가 기능 (계획 1 *또는* 계획 2)</span><span class="sxs-lookup"><span data-stu-id="8e6ec-122">An Exchange Online Protection, *and* Advanced Threat Protection add-on (Plan 1 *or* Plan 2)</span></span>
- <span data-ttu-id="8e6ec-123">Microsoft 365 E5 구독</span><span class="sxs-lookup"><span data-stu-id="8e6ec-123">A Microsoft 365 E5 subscription</span></span>

<span data-ttu-id="8e6ec-124">두 개의 집계 된 보기가 있는 ' 클릭 중심 ' 보고서입니다.</span><span class="sxs-lookup"><span data-stu-id="8e6ec-124">This is a 'click-centric' report that has two aggregated views.</span></span>

1. <span data-ttu-id="8e6ec-125">첫 번째 보기는 테 넌 트 내의 사용자에의 한 URL 클릭 수와 클릭 결과를 표시 하는 데 초점을 맞춘 *URL 클릭 방지 작업*입니다.</span><span class="sxs-lookup"><span data-stu-id="8e6ec-125">The first view is by *URL click-protection action*, which is focused on showing the number of URL clicks by users within the tenant, and the result of the click.</span></span> <span data-ttu-id="8e6ec-126">여기에서 클릭은 사용자가 악성 웹 사이트에 대 한 차단 페이지를 클릭 한 것을 나타냅니다 (안전한 링크 정책 내의 관리자가이 기능을 사용 하지 않도록 설정할 수 있음).</span><span class="sxs-lookup"><span data-stu-id="8e6ec-126">A click here indicates that the user has clicked through the block page to the malicious website (this can be disabled by the administrator within a Safe Links policy).</span></span>

2. <span data-ttu-id="8e6ec-127">두 번째 보기는 *url 클릭 응용 프로그램*, 즉 전자 메일 클라이언트나 Microsoft Word 등에서 현재 안전한 링크를 지 원하는 여러 응용 프로그램에서 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="8e6ec-127">The second view is *URL click by applications*, which shows the number of URLs click in different applications that support Safe Links today, such as in an email client or in Microsoft Word.</span></span> <span data-ttu-id="8e6ec-128">두 집계 보기의 데이터는 모두 4 시간 마다 한 번씩 새로 고쳐집니다.</span><span class="sxs-lookup"><span data-stu-id="8e6ec-128">Data in both aggregated views are refreshed once every 4 hours.</span></span>

<span data-ttu-id="8e6ec-129">URL Threat Protection 보고서의 details table은 테 넌 트 내에서 일어나는 모든 클릭에 대 한 거의 실시간 보기를 제공 하며, *사용자 이름*, *URL*, *네트워크 메시지 ID* (URL이 전자 메일에서 클릭 한 경우), 조사 및 분석에 유용한 기타 정보를 포함 하는 조사 정보</span><span class="sxs-lookup"><span data-stu-id="8e6ec-129">The details table of the URL Threat Protection report provides a near-real-time view of all clicks that happen within the tenant, and it includes investigative information such as *username*, *URL*, the *network message ID* (if the URL was clicked from an email), and other valuable pieces of information useful for investigations and analyses.</span></span>

<span data-ttu-id="8e6ec-130">기본적으로 보고서에는 안전한 링크에 의해 차단 된 Url의 클릭에 대 한 데이터만 표시 되지만, 필터에서 *허용 되는 url* 선택을 통해 모든 URL을 클릭 하는 데 필요한 정보도 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8e6ec-130">By default, the report only shows data on clicks from URLs that were blocked by Safe Links, but it is also possible to see information for all URL clicks through selecting *Allowed URLs* checkbox in the filters.</span></span>

<span data-ttu-id="8e6ec-131">이 보고서에는 적용 된 안전한 링크 정책이 사용자가 클릭 하 여 *추적 하지 않음* 옵션을 선택한 경우 사용자의 클릭 데이터는 포함 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="8e6ec-131">This report will not have data of clicks from users where the Safe Links policy applied has the *Do not track user clicks* option selected.</span></span>

![실행 중인 URL 위협 방지 보고서의 그래픽입니다.](../../media/tp-URLThreatProRpt1.PNG)

## <a name="compromised-users-report"></a><span data-ttu-id="8e6ec-133">손상 된 사용자 보고서</span><span class="sxs-lookup"><span data-stu-id="8e6ec-133">Compromised Users report</span></span>

<span data-ttu-id="8e6ec-134">Exchange Online Protection을 사용 하는 모든 사용자가 사용할 수 있는이 보고서에는 의심 스러운 사용자나 제한 된 사용자로 표시 되는, 데이터가 특히 계정으로 사용 하면 사용자 계정을 나타내는 상태 중 일부를 입력 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="8e6ec-134">This report, available to anyone with Exchange Online Protection, shows the number of user accounts marked as Suspicious or Restricted users, data particularly useful as accounts enter either of the states that indicate the user account may be problematic, or even compromised.</span></span> <span data-ttu-id="8e6ec-135">자주 사용 하는 경우에는 손상 된 사용자 보고서가 스파이크를 볼 수 있으며, 의심 스러운 또는 제한 상태인 계정으로 증거를 제공 하면 보안 및 테 넌 트의 wellness에 문제가 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8e6ec-135">With frequent use, the Compromised User report can spot spikes, and even trends, in accounts marked in suspicious or restricted states, giving evidence there could be an issue with security and the wellness of your tenant.</span></span>

![손상 된 사용자가 Office 365에 표시 되는 대로 보고 합니다.](../../media/tp-threatProtectStatRpt-CompromisedUserRpt.png)

## <a name="encryption-report"></a><span data-ttu-id="8e6ec-137">암호화 보고서</span><span class="sxs-lookup"><span data-stu-id="8e6ec-137">Encryption report</span></span>

<span data-ttu-id="8e6ec-138">**암호화 보고서** 에는 조직의 정책 또는 최종 사용자 컨트롤을 통해 암호화 된 전자 메일 메시지에 대 한 정보가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8e6ec-138">The **Encryption report** shows information about email messages that were encrypted, either through your organization's policies, or through end-user controls.</span></span> <span data-ttu-id="8e6ec-139">조직의 보안 팀은이 보고서의 정보를 사용 하 여 패턴을 식별 하 고 중요 한 전자 메일 메시지에 대 한 정책을 사전에 적용 하거나 조정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8e6ec-139">Your organization's security team can use information in this report to identify patterns and proactively apply or adjust policies for sensitive email messages.</span></span>

<span data-ttu-id="8e6ec-140">이 보고서를 보려면 보안 & 준수 센터에서 **보고서** \> **대시보드** \> **암호화 보고서**로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="8e6ec-140">To view this report, in the Security & Compliance Center, go to **Reports** \> **Dashboard** \> **Encryption report**.</span></span>

![암호화 보고서](../../media/encryptionreport-defaultview.png)

<span data-ttu-id="8e6ec-142">보고서를 처음 열면 전자 메일 메시지에 사용 되는 암호화 방법에 대 한 데이터가 이전의 7 일 (7)로 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8e6ec-142">When the report first opens, you'll see data about encryption methods used on email messages for the past seven (7) days.</span></span> <span data-ttu-id="8e6ec-143">화면 오른쪽 위 모서리에 있는 **필터** 를 클릭 하 여 보고서에 표시 되는 날짜 범위 및 세부 정보를 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8e6ec-143">You can change the date range and the details that are displayed in the report by clicking **Filters** in the upper right corner of the screen.</span></span>

![암호화 보고서 필터](../../media/encryptionreport-filters.png)

<span data-ttu-id="8e6ec-145">또한 **아래로 나누기** 메뉴를 사용 하 여 암호화 서식 파일 (또는 방법)을 통해 데이터를 볼 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8e6ec-145">You can also use the **Break down by** menu to view data by encryption template (or method).</span></span>

![암호화 방법 또는 서식 파일](../../media/encryptionreport-breakdownby.png)

<span data-ttu-id="8e6ec-147">또한 **데이터 보기 기준** 메뉴를 사용 하 여 상위 5 개 받는 사람 도메인에 대 한 암호화 된 메시지 수를 확인 하기 위해 보기를 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8e6ec-147">And, you can use the **View data by** menu to change the view to see counts of encrypted messages to the top five recipient domains.</span></span>

![암호화 보고서 데이터 보기 별 메뉴](../../media/encryptionreport-viewdataby.png)

<span data-ttu-id="8e6ec-149">새 암호화 보고서를 유연 하 게 사용 하 여 추세를 확인 하 고 적절 한 조치를 취할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8e6ec-149">With the flexibility of the new Encryption report, you can view trends and take appropriate actions.</span></span> <span data-ttu-id="8e6ec-150">예를 들어 사용자가 암호화 한 전자 메일 메시지가 많은 경우 특정 사용 사례에 대 한 암호화를 자동화 하는 암호화 정책을 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8e6ec-150">For example, if you see a high number of email messages encrypted by users, you might want to add an encryption policy to automate encryption for certain use cases.</span></span> <span data-ttu-id="8e6ec-151">도움말을 보려면 [Office 365에서 전자 메일 메시지를 암호화 하는 메일 흐름 규칙 정의](../../compliance/define-mail-flow-rules-to-encrypt-email.md)를 참조 하세요. 또 다른 예로, 사용할 수 있는 암호화 서식 파일이 있지만 아무도 사용 하지 않는 경우에는 사용자가 해당 기능에 대 한 교육을 받아야 하는지 여부를 탐색할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8e6ec-151">(To get help with that, see [Define mail flow rules to encrypt email messages in Office 365](../../compliance/define-mail-flow-rules-to-encrypt-email.md).) As another example, if you have a number of encryption templates available but no one is using them, you might explore whether users need training for that feature.</span></span>

<span data-ttu-id="8e6ec-152">이 보고서를 사용 하면 조직의 보안 및 규정 준수 팀이 메시지 암호화를 사용 하는 방법과 추가 작업이 필요한 지 여부를 모니터링할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8e6ec-152">Use this report enables your organization's security and compliance team to monitor how message encryption is being used, and whether further actions are needed.</span></span> <span data-ttu-id="8e6ec-153">암호화에 대 한 자세한 내용은 [Office 365의 전자 메일 암호화](../../compliance/email-encryption.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="8e6ec-153">To learn more about encryption, see [Email encryption in Office 365](../../compliance/email-encryption.md).</span></span>

## <a name="threat-protection-status-report"></a><span data-ttu-id="8e6ec-154">위협 방지 상태 보고서</span><span class="sxs-lookup"><span data-stu-id="8e6ec-154">Threat Protection Status report</span></span>

<span data-ttu-id="8e6ec-155">**위협 방지 상태** 보고서는 Exchange Online Protection에서 검색 하 여 차단한 악성 전자 메일을 보여 주는 스마트 보고서입니다.</span><span class="sxs-lookup"><span data-stu-id="8e6ec-155">The **Threat Protection Status** report is a smart report that shows malicious email that was detected and blocked by Exchange Online Protection.</span></span> <span data-ttu-id="8e6ec-156">이 보고서는 맬웨어 또는 시간에 따른 피싱 시도 (최대 90 일)로 식별 된 전자 메일을 확인 하는 데 유용 하며, 보안 관리자가 경향을 식별 하거나 정책 조정이 필요한 지 여부를 결정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8e6ec-156">This report is useful for viewing email identified as malware or a phishing attempt over time (up to 90 days), and it enables security administrators to identify trends or determine whether policies need adjustments.</span></span>

> [!NOTE]
> <span data-ttu-id="8e6ec-157">[Office 365 ATP](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp) 또는 [Exchange Online Protection](https://docs.microsoft.com/microsoft-365/security/office-365-security/what-is-eop) (EOP)이 있는 고객은 위협 보호 상태 보고서를 사용할 수 있습니다. 그러나 ATP 고객에 대 한 위협 방지 상태 보고서에 표시 되는 정보에는 고객에 게 표시 될 수 있는 것과 다른 데이터가 포함 될 가능성이 EOP.</span><span class="sxs-lookup"><span data-stu-id="8e6ec-157">A Threat Protection Status report is available to customers who have either [Office 365 ATP](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp) or [Exchange Online Protection](https://docs.microsoft.com/microsoft-365/security/office-365-security/what-is-eop) (EOP); however, the information that is displayed in the Threat Protection Status report for ATP customers will likely contain different data than what EOP customers might see.</span></span> <span data-ttu-id="8e6ec-158">예를 들어 EOP 고객은 전자 메일로 검색 된 맬웨어에 대 한 정보를 볼 수 있지만, [SharePoint Online, OneDrive 또는 Microsoft 팀에서 검색 된 악성 파일](https://docs.microsoft.com/microsoft-365/security/office-365-security/atp-for-spo-odb-and-teams)에 대 한 정보는 ATP 관련 기능입니다.</span><span class="sxs-lookup"><span data-stu-id="8e6ec-158">For example, EOP customers can view information about malware detected in email, but not information about [malicious files detected in SharePoint Online, OneDrive, or Microsoft Teams](https://docs.microsoft.com/microsoft-365/security/office-365-security/atp-for-spo-odb-and-teams), an ATP-specific capability.</span></span> <span data-ttu-id="8e6ec-159">[ATP 보고서에 대해 자세히 알아보세요](https://docs.microsoft.com/microsoft-365/security/office-365-security/view-reports-for-atp).</span><span class="sxs-lookup"><span data-stu-id="8e6ec-159">([Learn more about ATP reports](https://docs.microsoft.com/microsoft-365/security/office-365-security/view-reports-for-atp).)</span></span>

<span data-ttu-id="8e6ec-160">이 보고서를 보려면 [보안 & 준수 센터](https://protection.office.com)에서 **보고서** \> **대시보드** \> **위협 보호 상태로**이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="8e6ec-160">To view this report, in the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** \> **Threat Protection Status**.</span></span>

![위협 방지 상태 보고서](../../media/0ff86e12-c2b2-4d89-92a5-cefb054dc070.png)

<span data-ttu-id="8e6ec-162">위협 방지 상태 보고서를 처음 열면 보고서에는 기본적으로 이전의 7 일간의 데이터가 표시 됩니다. 그러나 **필터** 를 클릭 하 고 날짜 범위를 최대 90 일 정도 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8e6ec-162">When you first open the Threat Protection Status report, the report shows data for the past seven days by default; however, you can click **Filters** and change the date range for up to 90 days of detail.</span></span> <span data-ttu-id="8e6ec-163">평가판 구독을 사용 하는 경우에는 30 일간의 데이터를 제한할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8e6ec-163">(If you are using a trial subscription, you might be limited to 30 days' of data.)</span></span>

<span data-ttu-id="8e6ec-164">이 보고서는 조직의 [Exchange Online 보호 기능과](https://docs.microsoft.com/microsoft-365/security/office-365-security/eop-features)장기적인 추세에 대 한 영향을 확인 하는 데 유용 합니다.</span><span class="sxs-lookup"><span data-stu-id="8e6ec-164">This report is useful for viewing the effectiveness and impact of your organization's [Exchange Online Protection features](https://docs.microsoft.com/microsoft-365/security/office-365-security/eop-features), and for longer-term trending.</span></span>

![위협 보호 상태 보고서 필터](../../media/ab6b6b8d-e97a-4c3a-8fb1-c4940dcb7a07.png)

<span data-ttu-id="8e6ec-166">또한 해로운 것으로 확인 된 전자 메일, 피싱 시도로 식별 되는 전자 메일 또는 맬웨어로 식별 된 전자 메일에 대 한 데이터를 볼 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8e6ec-166">You can also choose whether to view data for email identified as malicious, email identified as a phishing attempts, or email identified as containing malware.</span></span>

![위협 보호 상태 보고서 보기 옵션](../../media/d429ecd7-cb7a-4c99-8d27-79a2832cf467.png)

## <a name="malware-detections-report"></a><span data-ttu-id="8e6ec-168">맬웨어 감지 보고서</span><span class="sxs-lookup"><span data-stu-id="8e6ec-168">Malware Detections report</span></span>

<span data-ttu-id="8e6ec-169">**맬웨어 감지** 보고서에는 조직에 대 한 맬웨어를 포함 하는 것으로 검색 된 수신 및 발신 메시지의 수가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8e6ec-169">The **Malware Detections** report shows how many incoming and outgoing messages were detected as containing malware for your organization.</span></span>

<span data-ttu-id="8e6ec-170">이 보고서를 보려면 [보안 & 준수 센터](https://protection.office.com)에서 **보고서** \> **대시보드** \> **맬웨어 감지**로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="8e6ec-170">To view this report, in the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** \> **Malware Detections**.</span></span>

![맬웨어 감지 보고서 예](../../media/a1ba61a3-565a-46d6-b0d5-6a6cff6b31d7.png)

<span data-ttu-id="8e6ec-172">[위협 방지 상태 보고서](#threat-protection-status-report)와 같은 다른 보고서와 마찬가지로 보고서에는 최근 7 일간의 데이터가 기본적으로 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8e6ec-172">Similar to other reports, like the [Threat Protection Status report](#threat-protection-status-report), the report displays data for the past seven days by default.</span></span> <span data-ttu-id="8e6ec-173">그러나 **필터** 를 선택 하 여 날짜 범위를 변경할 수는 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8e6ec-173">However, you can choose **Filters** to change the date range.</span></span>

## <a name="top-malware-report"></a><span data-ttu-id="8e6ec-174">주요 맬웨어 보고서</span><span class="sxs-lookup"><span data-stu-id="8e6ec-174">Top Malware report</span></span>

<span data-ttu-id="8e6ec-175">**주요 맬웨어** 보고서에는 [Exchange Online](https://docs.microsoft.com/microsoft-365/security/office-365-security/eop-features)에서 검색 된 다양 한 유형의 맬웨어가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8e6ec-175">The **Top Malware** report shows the various kinds of malware that was detected by [Exchange Online](https://docs.microsoft.com/microsoft-365/security/office-365-security/eop-features).</span></span>

<span data-ttu-id="8e6ec-176">이 보고서를 보려면 [보안 & 준수 센터](https://protection.office.com)에서 **보고서** \> **대시보드** \> **최상위 맬웨어로**이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="8e6ec-176">To view this report, in the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** \> **Top Malware**.</span></span>

![SCC-EOP 최상위 맬웨어](../../media/763330b3-f56e-4ba4-b0bb-051500ae950a.png)

<span data-ttu-id="8e6ec-178">원형 차트의 쐐기형 위에 마우스를 가져가면 맬웨어 종류와 해당 맬웨어가 있는 것으로 검색 된 메시지의 수를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8e6ec-178">When you hover over a wedge in the pie chart, you can see the name of a kind of malware and how many messages were detected as having that malware.</span></span>

<span data-ttu-id="8e6ec-179">보고서를 클릭 하거나 탭 하 여 새 브라우저 창에서 보고서를 열 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8e6ec-179">Click (or tap) the report to open it in a new browser window, where you can get a more detailed view of the report.</span></span>

![이 보고서에는 조직에 대해 검색 된 최상위 맬웨어가 표시 됩니다.](../../media/3fded224-fb31-4713-86f2-8afce5ce2991.png)

<span data-ttu-id="8e6ec-181">이 차트 아래에는 검색 된 맬웨어 목록과 해당 맬웨어가 있는 것으로 검색 한 메시지 수가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8e6ec-181">Below the chart, you'll see a list of detected malware and how many messages were detected as having that malware.</span></span>

## <a name="top-senders-and-recipients-report"></a><span data-ttu-id="8e6ec-182">상위 보낸 사람 및 받는 사람 보고서</span><span class="sxs-lookup"><span data-stu-id="8e6ec-182">Top Senders and Recipients report</span></span>

<span data-ttu-id="8e6ec-183">**상위 보낸 사람 및 받는 사람** 보고서는 상위 전자 메일 보낸 사람을 표시 하는 원형 차트입니다.</span><span class="sxs-lookup"><span data-stu-id="8e6ec-183">The **Top Senders and Recipients** report is a pie chart showing your top email senders.</span></span>

<span data-ttu-id="8e6ec-184">이 보고서를 보려면 [보안 & 준수 센터](https://protection.office.com)에서 **보고서** \> **대시보드** \> **최상위 보낸 사람 및 받는 사람**으로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="8e6ec-184">To view this report, in the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** \> **Top Senders and Recipients**.</span></span>

![이 보고서를 보려면 보안 & 준수 센터에서 보고서 \> 대시보드 \> 최상위 보낸 사람 및 받는 사람으로 이동 합니다.](../../media/b5506b5c-2420-4a5a-9ea3-d654294ac838.png)

<span data-ttu-id="8e6ec-186">원형 차트의 쐐기형 위에 마우스를 올리면 보내거나 받은 메시지 수가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8e6ec-186">When you hover over a wedge in the pie chart, you can see a count of messages sent or received.</span></span>

<span data-ttu-id="8e6ec-187">보고서를 클릭 하거나 탭 하 여 새 브라우저 창에서 보고서를 열 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8e6ec-187">Click (or tap) the report to open it in a new browser window, where you can get a more detailed view of the report.</span></span>

<span data-ttu-id="8e6ec-188">**데이터 표시** 순서 목록을 사용 하 여 상위 보낸 사람, 받는 사람, 스팸 및 맬웨어 받는 사람에 대 한 데이터를 볼 지 여부를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="8e6ec-188">Use the **Show data for** list to choose whether to view data for top senders, receivers, spam recipients, and malware recipients.</span></span> <span data-ttu-id="8e6ec-189">[Exchange Online Protection](https://docs.microsoft.com/microsoft-365/security/office-365-security/what-is-eop)에서 검색 된 맬웨어를 받은 사용자도 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8e6ec-189">You can also see who received malware that was detected by [Exchange Online Protection](https://docs.microsoft.com/microsoft-365/security/office-365-security/what-is-eop).</span></span>

![데이터 표시 목록을 사용 하 여 특정 정보 보기](../../media/bd91449f-7d42-4749-8666-7b44044049b8.png)

<span data-ttu-id="8e6ec-191">차트 아래에는 지정 된 기간 동안 보내거나 받은 메시지 수와 함께 맨 위에 있는 전자 메일 보낸 사람 또는 받는 사람이 표시 되는 사람을 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8e6ec-191">Below the chart, you'll see who the top email senders or recipients were, along with a count of messages sent or received for the given time period.</span></span>

## <a name="spoof-detections-report"></a><span data-ttu-id="8e6ec-192">스푸핑 감지 보고서</span><span class="sxs-lookup"><span data-stu-id="8e6ec-192">Spoof Detections report</span></span>

<span data-ttu-id="8e6ec-193">**스푸핑** 감지 보고서에는 얼마나 많은 스푸핑 메일 메시지가 검색 되었는지, 즉 합법적인 비즈니스 이유로 인해 스푸핑 메일을 "양호" 한 것으로 간주 되는 메시지 들이 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8e6ec-193">The **Spoof Detections** report shows how many spoof mail messages were detected, and of those, which ones were considered "good" (spoof mail done for legitimate business reasons).</span></span>

<span data-ttu-id="8e6ec-194">이 보고서를 보려면 [보안 & 준수 센터](https://protection.office.com)에서 **보고서** \> **대시보드** \> **스푸핑 메일로**이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="8e6ec-194">To view this report, in the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** \> **Spoof Mail**.</span></span>

![보안 & 준수 센터에서 보고서 \> 대시보드 \> 위장 메일로 이동 합니다.](../../media/0427e85c-9e40-4225-a0f0-e21a4e8b0e44.png)

<span data-ttu-id="8e6ec-196">차트에서 특정 날짜를 마우스로 가리키면 위장 메일 메시지의 수를 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8e6ec-196">When you hover over a day in the chart, you can see how many spoof mail messages came through.</span></span>

<span data-ttu-id="8e6ec-197">보고서를 클릭 하거나 탭 하 여 새 브라우저 창에서 보고서를 열 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8e6ec-197">Click (or tap) the report to open it in a new browser window, where you can get a more detailed view of the report.</span></span> <span data-ttu-id="8e6ec-198">스푸핑 방지 보호에 대 한 자세한 내용은 [Office 365에서 스푸핑 방지 보호](anti-spoofing-protection.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="8e6ec-198">To learn more about anti-spoof protection, see [Anti-spoofing protection in Office 365](anti-spoofing-protection.md).</span></span>

## <a name="spam-detections-report"></a><span data-ttu-id="8e6ec-199">스팸 감지 보고서</span><span class="sxs-lookup"><span data-stu-id="8e6ec-199">Spam Detections report</span></span>

<span data-ttu-id="8e6ec-200">**스팸 감지** 보고서에는 Exchange Online에서 차단 된 모든 스팸 콘텐츠가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8e6ec-200">The **Spam Detections** report shows all the spam content blocked by Exchange Online.</span></span> <span data-ttu-id="8e6ec-201">메시지는 받는 사람이 아닌 메시지당 계산 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8e6ec-201">Messages are counted per message, and not per recipient.</span></span> <span data-ttu-id="8e6ec-202">예를 들어 조직에서 100 받는 사람에 게 전자 메일 메시지를 보낸 경우에는 하나의 메시지로 계산 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8e6ec-202">For example, if an email message was sent to 100 recipients in your organization, it is counted as one message.</span></span>

<span data-ttu-id="8e6ec-203">이 보고서를 보려면 [보안 & 준수 센터](https://protection.office.com)에서 **보고서** \> **대시보드** \> **스팸 감지**로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="8e6ec-203">To view this report, in the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** \> **Spam Detections**.</span></span>

![이 보고서를 보려면 보안 & 준수 센터에서 보고서 \> 대시보드 \> EOP 스팸 감지로 이동 합니다.](../../media/028cff3c-79ce-4ec0-8f0f-ec32ac28243a.png)

<span data-ttu-id="8e6ec-205">차트에서 특정 날짜를 가리키면 해당 항목을 분류 한 방법 뿐 아니라 해당 요일이 차단 된 항목의 개수를 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8e6ec-205">When you hover over a day in the chart, you can see how many items were blocked that day, as well as how those items are categorized.</span></span> <span data-ttu-id="8e6ec-206">예를 들어 필터링 된 스팸 메시지 수와 IP (인터넷 프로토콜) 주소에서 가져온 항목 수를 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8e6ec-206">For example, you can see how many spam messages were filtered, and how many items came from a blocked Internet Protocol (IP) address.</span></span>

<span data-ttu-id="8e6ec-207">보고서를 클릭 하거나 탭 하 여 새 브라우저 창에서 보고서를 열 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8e6ec-207">Click (or tap) the report to open it in a new browser window, where you can get a more detailed view of the report.</span></span>

![스팸 감지 보고서는 차단 되거나 필터링 된 스팸 메시지의 수를 알려 줍니다.](../../media/370ec67d-eb30-4863-bfcf-68a41be02295.png)

<span data-ttu-id="8e6ec-209">차트 아래에 검색 된 스팸 항목 목록이 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8e6ec-209">Below the chart, you'll see a list of spam items that were detected.</span></span> <span data-ttu-id="8e6ec-210">항목을 선택 하 여 스팸 항목이 인바운드 인지, 아웃 바운드 인지, 메시지 ID 및 받는 사람과 같은 추가 정보를 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="8e6ec-210">Select an item to view additional information, such as whether the spam item was inbound or outbound, its message ID, and its recipient.</span></span> <span data-ttu-id="8e6ec-211">스팸 방지 보호 기능에 대 한 자세한 내용은 [Office 365 전자 메일 스팸 방지 보호](https://docs.microsoft.com/microsoft-365/security/office-365-security/anti-spam-and-anti-malware-protection)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="8e6ec-211">To learn more about anti-spam protection, see [Office 365 email anti-spam protection](https://docs.microsoft.com/microsoft-365/security/office-365-security/anti-spam-and-anti-malware-protection).</span></span>

## <a name="sent-and-received-email-report"></a><span data-ttu-id="8e6ec-212">보내고 받은 전자 메일 보고서</span><span class="sxs-lookup"><span data-stu-id="8e6ec-212">Sent and received email report</span></span>

<span data-ttu-id="8e6ec-213">**Sent and received email** 보고서는 스팸 감지, 맬웨어 및 "양호"로 식별 된 전자 메일을 포함 하 여 수신 및 발신 전자 메일에 대 한 정보를 표시 하는 스마트 보고서입니다.</span><span class="sxs-lookup"><span data-stu-id="8e6ec-213">The **Sent and received email** report is a smart report that shows information about incoming and outgoing email, including spam detections, malware, and email identified as "good."</span></span>

<span data-ttu-id="8e6ec-214">이 보고서를 보려면 [보안 & 준수 센터](https://protection.office.com)에서 **보고서** \> **대시보드** \> **보내기 및 받기 전자 메일로**이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="8e6ec-214">To view this report, in the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** \> **Sent and received email**.</span></span>

![이 보고서를 보려면 보안 & 준수 센터에서 보고서 \> 대시보드 \> 보내기 및 받기 전자 메일로 이동 합니다.](../../media/0e710ed0-1b0e-4dac-8796-94a01a710f3a.png)

<span data-ttu-id="8e6ec-216">차트에서 특정 날짜를 가리키면 메시지 수와 해당 메시지가 분류 되는 방식을 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8e6ec-216">When you hover over a day in the chart, you can see how many messages came in, and how those messages are categorized.</span></span> <span data-ttu-id="8e6ec-217">예를 들어 맬웨어가 있는 것으로 검색 된 메시지의 수와 스팸으로 식별 된 횟수를 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8e6ec-217">For example, you can see how many messages were detected as containing malware, and how many were identified as spam.</span></span>

<span data-ttu-id="8e6ec-218">보고서를 클릭 하거나 탭 하 여 새 브라우저 창에서 보고서를 열 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8e6ec-218">Click (or tap) the report to open it in a new browser window, where you can get a more detailed view of the report.</span></span>

<span data-ttu-id="8e6ec-219">**아래로 나누기** 목록을 사용 하 여 유형별로 정보를 보거나 방향 (수신 및 송신)을 기준으로 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8e6ec-219">You can use the **Break down by** list to view information by type or by direction (incoming and outgoing).</span></span>

![문자 또는 방향에 따라 정보를 보려면 아래로 나누기 목록을 사용 합니다.](../../media/a5b30c94-d75f-4bfc-851a-cb155685b177.png)

<span data-ttu-id="8e6ec-221">차트 아래에는 **GoodMail**, **spamcontentfiltered**등의 전자 메일 범주 목록이 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8e6ec-221">Below the chart, you'll see a list of email categories, such as **GoodMail**, **SpamContentFiltered**, and so on.</span></span> <span data-ttu-id="8e6ec-222">맬웨어에 대해 수행 된 작업과 같은 추가 정보와 전자 메일이 들어오거나 나가는 지를 보려면 범주를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="8e6ec-222">Select a category to view additional information, such as actions that were taken for malware, and whether email was incoming or outgoing.</span></span>

![이 보고서는 맬웨어 방지, 스팸 방지 및 기타 메시지 감지에 대해 알려줍니다.](../../media/9ea4b606-f27a-46ee-97a7-be018e2b839c.png)

<span data-ttu-id="8e6ec-224">전자 메일 인텔리전스에 대 한 자세한 내용은 [Mail flow intelligence In Office 365](https://docs.microsoft.com/microsoft-365/security/office-365-security/mail-flow-intelligence-in-office-365)을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="8e6ec-224">To learn more about email intelligence, see [Mail flow intelligence in Office 365](https://docs.microsoft.com/microsoft-365/security/office-365-security/mail-flow-intelligence-in-office-365).</span></span>

## <a name="user-reported-messages-report"></a><span data-ttu-id="8e6ec-225">사용자가 보고 한 메시지 보고서</span><span class="sxs-lookup"><span data-stu-id="8e6ec-225">User-reported messages report</span></span>

<span data-ttu-id="8e6ec-226">**사용자가 보고 한 메시지** 보고서에는 사용자가 [보고서 메시지 추가 기능](https://docs.microsoft.com/microsoft-365/security/office-365-security/enable-the-report-message-add-in)을 사용 하 여 정크 메일, 피싱 시도 또는 좋은 메일로 보고 한 전자 메일 메시지에 대 한 정보가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8e6ec-226">The **User-reported messages** report shows information about email messages that users have reported as junk, phishing attempts, or good mail by using the [Report Message add-in](https://docs.microsoft.com/microsoft-365/security/office-365-security/enable-the-report-message-add-in).</span></span>

<span data-ttu-id="8e6ec-227">각 메시지에 대 한 자세한 내용은 스팸 정책 예외 또는 조직에 대해 구성 된 메일 흐름 규칙과 같은 배달 이유를 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="8e6ec-227">Details are available for each message, including the delivery reason, such a spam policy exception or mail flow rule configured for your organization.</span></span> <span data-ttu-id="8e6ec-228">세부 정보를 보려면 사용자-보고서 목록에서 항목을 선택한 다음 **요약** 및 **세부 정보** 탭에서 해당 정보를 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="8e6ec-228">To view details, select an item in the user-reports list, and then view the information on the **Summary** and **Details** tabs.</span></span>

![사용자가 보고 한 메시지 보고서에는 사용자가 정크로 레이블이 지정 된 메시지, 정크 메일, 피싱 시도 등이 표시 됩니다.](../../media/ad5e9a3d-b833-419c-bcc9-3425d9604ead.png)

<span data-ttu-id="8e6ec-230">이 보고서를 보려면 [보안 & 준수 센터](https://protection.office.com)에서 다음 중 하나를 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="8e6ec-230">To view this report, in the [Security & Compliance Center](https://protection.office.com), do one of the following:</span></span>

- <span data-ttu-id="8e6ec-231">**위협 관리** \> **대시보드** \> **사용자가 보고 한 메시지로**이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="8e6ec-231">Go to **Threat management** \> **Dashboard** \> **User-reported messages**.</span></span>

- <span data-ttu-id="8e6ec-232">**위협 관리** \> 로 이동 하 여 **사용자가 보고 한 메시지**를 **검토** \> 합니다.</span><span class="sxs-lookup"><span data-stu-id="8e6ec-232">Go to **Threat management** \> **Review** \> **User-reported messages**.</span></span>

![보안 & 준수 센터에서 위협 관리 \> 검토 \> 사용자가 보고 한 메시지를 선택 합니다.](../../media/e372c57c-1414-4616-957b-bc933b8c8711.png)

> [!IMPORTANT]
> <span data-ttu-id="8e6ec-234">사용자가 보고 한 메시지 보고서가 제대로 작동 하도록 하려면 Office 365 환경에 대해 **감사 로깅을 켜야 합니다** .</span><span class="sxs-lookup"><span data-stu-id="8e6ec-234">In order for the User-reported messages report to work correctly, **audit logging must be turned on** for your Office 365 environment.</span></span> <span data-ttu-id="8e6ec-235">이 작업은 일반적으로 Exchange Online에서 감사 로그 역할이 할당 된 사용자가 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="8e6ec-235">This is typically done by someone who has the Audit Logs role assigned in Exchange Online.</span></span> <span data-ttu-id="8e6ec-236">자세한 내용은 [Office 365 감사 로그 검색 설정 또는 해제](https://docs.microsoft.com/microsoft-365/compliance/turn-audit-log-search-on-or-off)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="8e6ec-236">For more information, see [Turn Office 365 audit log search on or off](https://docs.microsoft.com/microsoft-365/compliance/turn-audit-log-search-on-or-off).</span></span>

## <a name="what-permissions-are-needed-to-view-these-reports"></a><span data-ttu-id="8e6ec-237">이러한 보고서를 표시 하는 데 필요한 사용 권한은 무엇입니까?</span><span class="sxs-lookup"><span data-stu-id="8e6ec-237">What permissions are needed to view these reports?</span></span>

<span data-ttu-id="8e6ec-238">이 문서에서 설명 하는 보고서를 보고 사용 하려면 **보안 & 준수 센터와 Exchange 관리 센터 둘 다에 대해 적절 한 역할이 할당 되어 있어야 합니다**.</span><span class="sxs-lookup"><span data-stu-id="8e6ec-238">In order to view and use the reports described in this article, **you must have an appropriate role assigned for both the Security & Compliance Center and the Exchange admin center**.</span></span>

- <span data-ttu-id="8e6ec-239">보안 & 준수 센터에는 다음 역할 중 하나가 할당 되어 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8e6ec-239">For the Security & Compliance Center, you must have one of the following roles assigned:</span></span>

  <span data-ttu-id="8e6ec-240">-조직 관리-보안 관리자 (Azure Active Directory 관리 센터에서 할당할 수 있음[https://aad.portal.azure.com](https://aad.portal.azure.com))-보안 독자</span><span class="sxs-lookup"><span data-stu-id="8e6ec-240">-Organization Management -Security Administrator (this can be assigned in the Azure Active Directory admin center ([https://aad.portal.azure.com](https://aad.portal.azure.com)) -Security Reader</span></span>

- <span data-ttu-id="8e6ec-241">Exchange Online의 경우 Exchange 관리 센터 ([https://outlook.office365.com/ecp](https://outlook.office365.com/ecp)) 또는 PowerShell Cmdlet ( [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/exchange-online-powershell?view=exchange-ps)참조)에서 다음 역할 중 하나를 할당 받아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8e6ec-241">For Exchange Online, you must have one of the following roles assigned in either the Exchange admin center ([https://outlook.office365.com/ecp](https://outlook.office365.com/ecp)) or with PowerShell cmdlets (See [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/exchange-online-powershell?view=exchange-ps)):</span></span>

  <span data-ttu-id="8e6ec-242">-조직 관리-보기 전용 조직 관리-보기 권한만 있는 받는 사람 역할-준수 관리</span><span class="sxs-lookup"><span data-stu-id="8e6ec-242">-Organization Management -View-only Organization Management -View-Only Recipients role -Compliance Management</span></span>

<span data-ttu-id="8e6ec-243">자세한 내용은 다음 리소스를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="8e6ec-243">To learn more, see the following resources:</span></span>

- [<span data-ttu-id="8e6ec-244">Office 365 보안 및 준수 센터의 사용 권한</span><span class="sxs-lookup"><span data-stu-id="8e6ec-244">Permissions in the Office 365 Security & Compliance Center</span></span>](https://docs.microsoft.com/microsoft-365/security/office-365-security/permissions-in-the-security-and-compliance-center)

- [<span data-ttu-id="8e6ec-245">Exchange Online의 기능 사용 권한</span><span class="sxs-lookup"><span data-stu-id="8e6ec-245">Feature permissions in Exchange Online</span></span>](https://docs.microsoft.com/exchange/permissions-exo/feature-permissions)

## <a name="what-if-the-reports-arent-showing-data"></a><span data-ttu-id="8e6ec-246">보고서에 데이터가 표시 되지 않으면 어떻게 하나요?</span><span class="sxs-lookup"><span data-stu-id="8e6ec-246">What if the reports aren't showing data?</span></span>

<span data-ttu-id="8e6ec-247">보고서에 데이터가 표시 되지 않는 경우 정책이 올바르게 설정 되어 있는지 다시 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="8e6ec-247">If you are not seeing data in your reports, double-check that your policies are set up correctly.</span></span> <span data-ttu-id="8e6ec-248">자세한 내용은 [Office 365에서 위협 으로부터 보호](https://docs.microsoft.com/microsoft-365/security/office-365-security/protect-against-threats)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="8e6ec-248">To learn more, see [Protect against threats in Office 365](https://docs.microsoft.com/microsoft-365/security/office-365-security/protect-against-threats).</span></span>

## <a name="related-topics"></a><span data-ttu-id="8e6ec-249">관련 항목</span><span class="sxs-lookup"><span data-stu-id="8e6ec-249">Related topics</span></span>

[<span data-ttu-id="8e6ec-250">Office 365 이메일 스팸 방지 보호</span><span class="sxs-lookup"><span data-stu-id="8e6ec-250">Office 365 Email Anti-Spam Protection</span></span>](https://docs.microsoft.com/microsoft-365/security/office-365-security/anti-spam-and-anti-malware-protection)

[<span data-ttu-id="8e6ec-251">Office 365 보안 & 준수 센터의 보고서 및 정보</span><span class="sxs-lookup"><span data-stu-id="8e6ec-251">Reports and insights in the Office 365 Security & Compliance Center</span></span>](https://docs.microsoft.com/microsoft-365/security/office-365-security/reports-and-insights-in-security-and-compliance)

[<span data-ttu-id="8e6ec-252">보안 & 준수 센터에서 보고서에 대 한 일정 만들기</span><span class="sxs-lookup"><span data-stu-id="8e6ec-252">Create a schedule for a report in the Security & Compliance Center</span></span>](https://docs.microsoft.com/microsoft-365/security/office-365-security/create-a-schedule-for-a-report)

[<span data-ttu-id="8e6ec-253">보안 & 준수 센터에서 사용자 지정 보고서 설정 및 다운로드</span><span class="sxs-lookup"><span data-stu-id="8e6ec-253">Set up and download a custom report in the Security & Compliance Center</span></span>](https://docs.microsoft.com/microsoft-365/security/office-365-security/set-up-and-download-a-custom-report)
