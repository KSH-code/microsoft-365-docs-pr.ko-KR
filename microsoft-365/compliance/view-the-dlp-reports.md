---
title: 데이터 손실 방지에 대한 보고서 보기
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: 6/7/2018
audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.collection:
- M365-security-compliance
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.custom: seo-marvel-apr2020
description: Office 365의 DLP 보고서를 사용하여 DLP 정책 일치, 재지정 또는 가짓 긍정 수를 보고 시간이 경과에 따라 추세인지 또는 하락 추세인지를 볼 수 있습니다.
ms.openlocfilehash: 742f0ef0334e714c7f31cbc2f97559993454f6b7
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/19/2021
ms.locfileid: "50928392"
---
# <a name="view-the-reports-for-data-loss-prevention"></a><span data-ttu-id="27d24-103">데이터 손실 방지에 대한 보고서 보기</span><span class="sxs-lookup"><span data-stu-id="27d24-103">View the reports for data loss prevention</span></span>

<span data-ttu-id="27d24-104">DLP(데이터 손실 방지) 정책을 만든 후 의도한 것만큼 작동하고 규정 준수를 유지하도록 도와주는지 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="27d24-104">After you create your data loss prevention (DLP) policies, you'll want to verify that they're working as you intended and helping you to stay compliant.</span></span> <span data-ttu-id="27d24-105">보안 및 준수 센터의 DLP 보고서를 사용하면 &amp; 다음을 빠르게 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="27d24-105">With the DLP reports in the Security &amp; Compliance Center, you can quickly view:</span></span>
  
- <span data-ttu-id="27d24-106">**DLP 정책 일치** 이 보고서에는 시간이 지날 때 일치하는 DLP 정책의 수가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="27d24-106">**DLP policy matches** This report shows the count of DLP policy matches over time.</span></span> <span data-ttu-id="27d24-107">날짜, 위치, 정책 또는 작업을 사용하여 보고서를 필터링할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="27d24-107">You can filter the report by date, location, policy, or action.</span></span> <span data-ttu-id="27d24-108">이 보고서를 사용하여 다음을 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="27d24-108">You can use this report to:</span></span> 
    
  - <span data-ttu-id="27d24-109">테스트 모드에서 실행할 때 DLP 정책을 조정하거나 구체화합니다.</span><span class="sxs-lookup"><span data-stu-id="27d24-109">Tune or refine your DLP policies as you run them in test mode.</span></span> <span data-ttu-id="27d24-110">콘텐츠와 일치하는 특정 규칙을 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="27d24-110">You can view the specific rule that matched the content.</span></span>
    
  - <span data-ttu-id="27d24-111">특정 기간에 초점을 맞추고 스파이크 및 추세의 이유를 이해합니다.</span><span class="sxs-lookup"><span data-stu-id="27d24-111">Focus on specific time periods and understand the reasons for spikes and trends.</span></span>
    
  - <span data-ttu-id="27d24-112">조직의 DLP 정책을 위반하는 비즈니스 프로세스를 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="27d24-112">Discover business processes that violate your organization's DLP policies.</span></span>
    
  - <span data-ttu-id="27d24-113">콘텐츠에 적용되는 작업을 파악하여 DLP 정책이 비즈니스에 미치는 영향을 이해합니다.</span><span class="sxs-lookup"><span data-stu-id="27d24-113">Understand any business impact of the DLP policies by seeing what actions are being applied to content.</span></span>
    
  - <span data-ttu-id="27d24-114">해당 정책에 대한 일치 항목을 표시하여 특정 DLP 정책에 대한 준수를 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="27d24-114">Verify compliance with a specific DLP policy by showing any matches for that policy.</span></span>
    
  - <span data-ttu-id="27d24-115">상위 사용자 목록을 보고 조직의 인시던트에 기여하는 사용자를 반복합니다.</span><span class="sxs-lookup"><span data-stu-id="27d24-115">View a list of top users and repeat users who are contributing to incidents in your organization.</span></span>
    
  - <span data-ttu-id="27d24-116">조직의 상위 중요한 정보 유형 목록을 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="27d24-116">View a list of the top types of sensitive information in your organization.</span></span>
    
- <span data-ttu-id="27d24-117">**DLP 인시던트** 또한 이 보고서에는 정책 일치 보고서와 같이 시간이 지날 때의 정책 일치도 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="27d24-117">**DLP incidents** This report also shows policy matches over time, like the policy matches report.</span></span> <span data-ttu-id="27d24-118">그러나 정책 일치 보고서에는 규칙 수준에서 일치하는 일치가 표시 됩니다. 예를 들어 전자 메일이 세 가지 다른 규칙과 일치하는 경우 정책 일치 보고서에는 세 개의 서로 다른 행 항목이 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="27d24-118">However, the policy matches report shows matches at a rule level; for example, if an email matched three different rules, the policy matches report shows three different line items.</span></span> <span data-ttu-id="27d24-119">반면 인시던트 보고서에는 항목 수준에서 일치하는 항목이 표시됩니다. 예를 들어 전자 메일이 세 가지 다른 규칙과 일치하는 경우 인시던트 보고서에는 해당 콘텐츠에 대한 단일 행 항목이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="27d24-119">By contrast, the incidents report shows matches at an item level; for example, if an email matched three different rules, the incidents report shows a single line item for that piece of content.</span></span> 
    
  <span data-ttu-id="27d24-120">보고서 수는 다르게 집계하기 때문에 특정 규칙과 일치하는 일치를 식별하고 DLP 정책을 미세 조정하는 데 정책 일치 보고서가 더 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="27d24-120">Because the report counts are aggregated differently, the policy matches report is better for identifying matches with specific rules and fine tuning DLP policies.</span></span> <span data-ttu-id="27d24-121">인시던트 보고서는 DLP 정책에 문제가 있는 특정 콘텐츠를 식별하는 데 더 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="27d24-121">The incidents report is better for identifying specific pieces of content that are problematic for your DLP policies.</span></span>
    
- <span data-ttu-id="27d24-122">**DLP 가긍성** 및 다시 시정 DLP 정책에서 사용자가 정책을 다시 설정하거나 가짓 긍정을 보고할 수 있도록 허용하는 경우 이 보고서에는 시간이 지날 때 이러한 인스턴스의 수가 표시될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="27d24-122">**DLP false positives and overrides** If your DLP policy allows users to override it or report a false positive, this report shows a count of such instances over time.</span></span> <span data-ttu-id="27d24-123">날짜, 위치 또는 정책에 따라 보고서를 필터링할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="27d24-123">You can filter the report by date, location, or policy.</span></span> <span data-ttu-id="27d24-124">이 보고서를 사용하여 다음을 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="27d24-124">You can use this report to:</span></span> 
    
  - <span data-ttu-id="27d24-125">많은 수의 가음성으로 이어지는 정책을 확인하여 DLP 정책을 조정하거나 구체화합니다.</span><span class="sxs-lookup"><span data-stu-id="27d24-125">Tune or refine your DLP policies by seeing which policies incur a high number of false positives.</span></span>
    
  - <span data-ttu-id="27d24-126">사용자가 정책을재지하여 정책 팁을 해결할 때 제출한 사정을 밝습니다.</span><span class="sxs-lookup"><span data-stu-id="27d24-126">View the justifications submitted by users when they resolve a policy tip by overriding the policy.</span></span>
    
  - <span data-ttu-id="27d24-127">많은 수의 사용자 재지정을 통해 DLP 정책이 유효한 비즈니스 프로세스와 충돌하는 위치를 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="27d24-127">Discover where DLP policies conflict with valid business processes by incurring a high number of user overrides.</span></span>
    
<span data-ttu-id="27d24-128">모든 DLP 보고서는 가장 최근 4개월 기간의 데이터를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="27d24-128">All DLP reports can show data from the most recent four-month time period.</span></span> <span data-ttu-id="27d24-129">가장 최근 데이터가 보고서에 표시되는 데 최대 24시간이 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="27d24-129">The most recent data can take up to 24 hours to appear in the reports.</span></span>
  
<span data-ttu-id="27d24-130">이러한 보고서는 보안 및 준수 센터 보고서 대시보드 &amp; \> **에서 찾을 수** \> **있습니다.**</span><span class="sxs-lookup"><span data-stu-id="27d24-130">You can find these reports in the Security &amp; Compliance Center \> **Reports** \> **Dashboard**.</span></span>
  
![DLP 정책 일치 보고서](../media/117d20c9-d379-403f-ad68-1f5cd6c4e5cf.png)
  
## <a name="view-the-justification-submitted-by-a-user-for-an-override"></a><span data-ttu-id="27d24-132">사용자가 제출한 정당성에 대한 검토</span><span class="sxs-lookup"><span data-stu-id="27d24-132">View the justification submitted by a user for an override</span></span>

<span data-ttu-id="27d24-133">DLP 정책에서 사용자가 이를 다시 설정하는 것을 허용하는 경우 가짓 긍정 및 다시 설정 보고서를 사용하여 정책 팁에서 사용자가 제출한 텍스트를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="27d24-133">If your DLP policy allows users to override it, you can use the false positive and override report to view the text submitted by users in the policy tip.</span></span>
  
![DLP 가 긍정 및 다시 정당성 보고서의 세부 정보 필드](../media/e11e3126-026d-4e77-a16d-74a0686d1fa3.png)
  
## <a name="take-action-on-insights-and-recommendations"></a><span data-ttu-id="27d24-135">인사이트 및 권장 사항에 대한 조치 수행</span><span class="sxs-lookup"><span data-stu-id="27d24-135">Take action on insights and recommendations</span></span>

<span data-ttu-id="27d24-136">보고서에는 빨간색 경고 아이콘을 클릭하여 잠재적인 문제에 대한 세부 정보를 보고 가능한 수정 조치를 취할 수 있는 인사이트 및 권장 사항이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="27d24-136">Reports can show insights and recommendations where you can click the red warning icon to see details about potential issues and take possible remedial action.</span></span>
  
![인사이트 아이콘을 클릭하여 수행할 세부 정보 및 작업을 볼 수 있습니다.](../media/51782036-7299-4960-8175-75c2b1637159.png)
  
## <a name="permissions-for-dlp-reports"></a><span data-ttu-id="27d24-138">DLP 보고서에 대한 사용 권한</span><span class="sxs-lookup"><span data-stu-id="27d24-138">Permissions for DLP reports</span></span>

<span data-ttu-id="27d24-139">보안 및 준수 센터에서 DLP 보고서를 & 다음을 할당해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="27d24-139">To view DLP reports in the Security & Compliance Center, you have to be assigned the:</span></span>

- <span data-ttu-id="27d24-140">Exchange **관리** 센터의 보안 읽기 관리자 역할</span><span class="sxs-lookup"><span data-stu-id="27d24-140">**Security Reader** role in the Exchange admin center.</span></span> <span data-ttu-id="27d24-141">기본적으로 이 역할은 Exchange 관리 센터의 조직 관리 및 보안 읽기 관리자 역할 그룹에 할당됩니다.</span><span class="sxs-lookup"><span data-stu-id="27d24-141">By default, this role is assigned to the Organization Management and Security Reader role groups in the Exchange admin center.</span></span>

- <span data-ttu-id="27d24-142">**보안 및 준수** 센터의 보기 전용 DLP 준수 &.</span><span class="sxs-lookup"><span data-stu-id="27d24-142">**View-Only DLP Compliance Management** role in the Security & Compliance Center.</span></span> <span data-ttu-id="27d24-143">기본적으로 이 역할은 보안 및 준수 센터의 준수 관리자, 조직 관리, 보안 관리자 및 보안 읽기 권한자 & 할당됩니다.</span><span class="sxs-lookup"><span data-stu-id="27d24-143">By default, this role is assigned to the Compliance Administrator, Organization Management, Security Administrator, and Security Reader role groups in the Security & Compliance Center.</span></span>

- <span data-ttu-id="27d24-144">**Exchange 관리 센터에서** 보기 전용 받는 사람 역할</span><span class="sxs-lookup"><span data-stu-id="27d24-144">**View-Only Recipients** role in the Exchange admin center.</span></span> <span data-ttu-id="27d24-145">기본적으로 이 역할은 Exchange 관리 센터의 준수 관리, View-Only 관리 역할 그룹에 할당됩니다.</span><span class="sxs-lookup"><span data-stu-id="27d24-145">By default, this role is assigned to the Compliance Management, Organization Management, and View-Only Organization Management role groups in the Exchange admin center.</span></span>

## <a name="find-the-cmdlets-for-the-dlp-reports"></a><span data-ttu-id="27d24-146">DLP 보고서의 cmdlet 찾기</span><span class="sxs-lookup"><span data-stu-id="27d24-146">Find the cmdlets for the DLP reports</span></span>

<span data-ttu-id="27d24-147">대부분의 보안 &amp; 준수 센터용 cmdlet을 사용하려면 다음의 단계를 따르십시오:</span><span class="sxs-lookup"><span data-stu-id="27d24-147">To use most of the cmdlets for the Security &amp; Compliance Center, you need to:</span></span>
  
1. [<span data-ttu-id="27d24-148">원격 &amp; PowerShell을 사용하여 보안 및 준수 센터에 연결</span><span class="sxs-lookup"><span data-stu-id="27d24-148">Connect to the Security &amp; Compliance Center using remote PowerShell</span></span>](/powershell/exchange/connect-to-scc-powershell&amp;clcid=0x409)
    
2. <span data-ttu-id="27d24-149">다음 보안 및 준수 센터 [ &amp; cmdlet 사용](/powershell/exchange/exchange-online-powershell)</span><span class="sxs-lookup"><span data-stu-id="27d24-149">Use any of these [Security &amp; Compliance Center cmdlets](/powershell/exchange/exchange-online-powershell)</span></span>
    
<span data-ttu-id="27d24-150">하지만 DLP 보고서에서는 Exchange Online을 포함한 Office 365에서 데이터를 가져와야 합니다.</span><span class="sxs-lookup"><span data-stu-id="27d24-150">However, DLP reports need pull data from across Office 365, including Exchange Online.</span></span> <span data-ttu-id="27d24-151">이러한 이유로 DLP 보고서의 cmdlet은 보안 및 준수 센터 Powershell이 아닌 Exchange Online &amp; Powershell에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="27d24-151">For this reason, the cmdlets for the DLP reports are available in Exchange Online Powershell—not in Security &amp; Compliance Center Powershell.</span></span> <span data-ttu-id="27d24-152">따라서 DLP 보고서용 cmdlet을 사용하려면 다음의 단계가 필요합니다:</span><span class="sxs-lookup"><span data-stu-id="27d24-152">Therefore, to use the cmdlets for the DLP reports, you need to:</span></span>
  
1. [<span data-ttu-id="27d24-153">원격 PowerShell을 사용하여 Exchange Online에 연결</span><span class="sxs-lookup"><span data-stu-id="27d24-153">Connect to Exchange Online using remote PowerShell</span></span>](/powershell/exchange/connect-to-exchange-online-powershell)
    
2. <span data-ttu-id="27d24-154">다음과 같은 DLP 보고서용 cmdlet 중 하나 사용</span><span class="sxs-lookup"><span data-stu-id="27d24-154">Use any of these cmdlets for the DLP reports:</span></span>
    
      - [<span data-ttu-id="27d24-155">Get-DlpDetectionsReport</span><span class="sxs-lookup"><span data-stu-id="27d24-155">Get-DlpDetectionsReport</span></span>](/powershell/module/exchange/get-dlpdetectionsreport)
    
      - [<span data-ttu-id="27d24-156">Get-DlpDetailReport</span><span class="sxs-lookup"><span data-stu-id="27d24-156">Get-DlpDetailReport</span></span>](/powershell/module/exchange/get-dlpdetailreport)
