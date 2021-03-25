---
title: 관리 센터를 방문하여 수정 작업 보기
description: 관리 센터를 사용하여 자동화된 조사 후 세부 정보 및 결과 보기
keywords: action, center, autoir, automated, investigation, response, remediation
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: deniseb
author: denisebmsft
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: how-to
ms.reviewer: ramarom, evaldm, isco, mabraitm, chriggs
ms.date: 01/28/2021
ms.technology: mde
ms.openlocfilehash: 6caa1cfe08a20aa824d85966c104a25988b8be53
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/24/2021
ms.locfileid: "51165360"
---
# <a name="visit-the-action-center-to-see-remediation-actions"></a><span data-ttu-id="84216-104">관리 센터를 방문하여 수정 작업 보기</span><span class="sxs-lookup"><span data-stu-id="84216-104">Visit the Action center to see remediation actions</span></span>

<span data-ttu-id="84216-105">자동화된 조사가 진행되는 동안 및 이후에 위협 감지에 대한 수정 작업이 식별됩니다.</span><span class="sxs-lookup"><span data-stu-id="84216-105">During and after an automated investigation, remediation actions for threat detections are identified.</span></span> <span data-ttu-id="84216-106">특정 위협 및 조직에 대해 [Microsoft Defender for Endpoint가](https://docs.microsoft.com/windows/security/threat-protection) 구성된 방식에 따라 일부 수정 작업이 자동으로 수행되고 다른 작업은 승인을 요구합니다.</span><span class="sxs-lookup"><span data-stu-id="84216-106">Depending on the particular threat and how [Microsoft Defender for Endpoint](https://docs.microsoft.com/windows/security/threat-protection) is configured for your organization, some remediation actions are taken automatically, and others require approval.</span></span> <span data-ttu-id="84216-107">조직의 보안 운영 팀에 참여하는 경우 관리 센터에서 보류 중 [](manage-auto-investigation.md#remediation-actions) 및 완료된 수정 작업을 볼 **수 있습니다.**</span><span class="sxs-lookup"><span data-stu-id="84216-107">If you're part of your organization's security operations team, you can view pending and completed [remediation actions](manage-auto-investigation.md#remediation-actions) in the **Action center**.</span></span> 


<span data-ttu-id="84216-108">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="84216-108">**Applies to:**</span></span>
- [<span data-ttu-id="84216-109">엔드포인트용 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="84216-109">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="84216-110">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="84216-110">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

## <a name="new-a-unified-action-center"></a><span data-ttu-id="84216-111">(NEW!) 통합된 동작 센터</span><span class="sxs-lookup"><span data-stu-id="84216-111">(NEW!) A unified Action center</span></span>


<span data-ttu-id="84216-112">새로운 통합된 통합 동작 센터( )를 발표하게 [https://security.microsoft.com/action-center](https://security.microsoft.com/action-center) 됩니다.</span><span class="sxs-lookup"><span data-stu-id="84216-112">We are pleased to announce a new, unified Action center ([https://security.microsoft.com/action-center](https://security.microsoft.com/action-center))!</span></span>

:::image type="content" source="images/mde-action-center-unified.png" alt-text="Microsoft 365 보안 센터의 관리 센터":::

<span data-ttu-id="84216-114">다음 표에서는 새로운 통합된 작업 센터와 이전 작업 센터를 비교합니다.</span><span class="sxs-lookup"><span data-stu-id="84216-114">The following table compares the new, unified Action center to the previous Action center.</span></span>

|<span data-ttu-id="84216-115">새로운 통합된 동작 센터</span><span class="sxs-lookup"><span data-stu-id="84216-115">The new, unified Action center</span></span>  |<span data-ttu-id="84216-116">이전 작업 센터</span><span class="sxs-lookup"><span data-stu-id="84216-116">The previous Action center</span></span>  |
|---------|---------|
|<span data-ttu-id="84216-117">장치 및 전자 메일에 대해 보류 중인 작업과 완료된 작업을 한 위치에 나열합니다.</span><span class="sxs-lookup"><span data-stu-id="84216-117">Lists pending and completed actions for devices and email in one location</span></span> <br/><span data-ttu-id="84216-118">([Endpoint용 Microsoft Defender](microsoft-defender-advanced-threat-protection.md) 및 [Office 365용 Microsoft Defender](https://docs.microsoft.com/microsoft-365/security/defender-365-security/office-365-atp))</span><span class="sxs-lookup"><span data-stu-id="84216-118">([Microsoft Defender for Endpoint](microsoft-defender-advanced-threat-protection.md) plus [Microsoft Defender for Office 365](https://docs.microsoft.com/microsoft-365/security/defender-365-security/office-365-atp))</span></span>|<span data-ttu-id="84216-119">장치에 대한 보류 중인 작업 및 완료된 작업 목록</span><span class="sxs-lookup"><span data-stu-id="84216-119">Lists pending and completed actions for devices</span></span> <br/> <span data-ttu-id="84216-120">[(끝점용 Microsoft Defender만 해당)](microsoft-defender-advanced-threat-protection.md)</span><span class="sxs-lookup"><span data-stu-id="84216-120">([Microsoft Defender for Endpoint](microsoft-defender-advanced-threat-protection.md) only)</span></span>   |
|<span data-ttu-id="84216-121">에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="84216-121">Is located at:</span></span><br/>[https://security.microsoft.com/action-center](https://security.microsoft.com/action-center)         |<span data-ttu-id="84216-122">에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="84216-122">Is located at:</span></span><br/>[https://securitycenter.windows.com/action-center](https://securitycenter.windows.com/action-center)     |
| <span data-ttu-id="84216-123">Microsoft 365 보안 센터에서 관리 **센터 를 선택 합니다.**</span><span class="sxs-lookup"><span data-stu-id="84216-123">In the Microsoft 365 security center, choose **Action center**.</span></span> <p>:::image type="content" source="images/action-center-nav-new.png" alt-text="Microsoft 365 보안 센터의 관리 센터로"::: | <span data-ttu-id="84216-125">Microsoft Defender 보안 센터에서 **자동화된** 조사 관리  >  **센터 를 선택 합니다.**</span><span class="sxs-lookup"><span data-stu-id="84216-125">In the Microsoft Defender Security Center, choose **Automated investigations** > **Action center**.</span></span> <p>:::image type="content" source="images/action-center-nav-old.png" alt-text="Microsoft Defender 보안 센터에서 관리 센터로":::  |

<span data-ttu-id="84216-127">통합 관리 센터는 끝점용 Defender 및 Office 365용 Defender에 대한 수정 작업을 통합합니다.</span><span class="sxs-lookup"><span data-stu-id="84216-127">The unified Action center brings together remediation actions across Defender for Endpoint and Defender for Office 365.</span></span> <span data-ttu-id="84216-128">모든 수정 작업에 대한 공통 언어를 정의하고 통합 조사 환경을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="84216-128">It defines a common language for all remediation actions, and provides a unified investigation experience.</span></span> 

<span data-ttu-id="84216-129">적절한 사용 권한 및 다음 구독 중 하나 이상이 있는 경우 통합 관리 센터를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="84216-129">You can use the unified Action center if you have appropriate permissions and one or more of the following subscriptions:</span></span>
- [<span data-ttu-id="84216-130">엔드포인트용 Defender</span><span class="sxs-lookup"><span data-stu-id="84216-130">Defender for Endpoint</span></span>](microsoft-defender-advanced-threat-protection.md)
- [<span data-ttu-id="84216-131">Office 365용 Defender</span><span class="sxs-lookup"><span data-stu-id="84216-131">Defender for Office 365</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-365-security/office-365-atp)
- [<span data-ttu-id="84216-132">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="84216-132">Microsoft 365 Defender</span></span>](https://docs.microsoft.com/microsoft-365/security/mtp/microsoft-threat-protection) 

> [!TIP]
> <span data-ttu-id="84216-133">자세한 내용은 요구 사항을 [참조하세요.](https://docs.microsoft.com/microsoft-365/security/mtp/prerequisites)</span><span class="sxs-lookup"><span data-stu-id="84216-133">To learn more, see [Requirements](https://docs.microsoft.com/microsoft-365/security/mtp/prerequisites).</span></span>

## <a name="using-the-action-center"></a><span data-ttu-id="84216-134">동작 센터 사용</span><span class="sxs-lookup"><span data-stu-id="84216-134">Using the Action center</span></span>

<span data-ttu-id="84216-135">개선된 Microsoft 365 보안 센터의 통합 관리 센터로 가기:</span><span class="sxs-lookup"><span data-stu-id="84216-135">To get to the unified Action center in the improved Microsoft 365 security center:</span></span>
1. <span data-ttu-id="84216-136">Microsoft 365 보안 센터()로 이동하여 [https://security.microsoft.com](https://security.microsoft.com) 로그인합니다.</span><span class="sxs-lookup"><span data-stu-id="84216-136">Go to the Microsoft 365 security center ([https://security.microsoft.com](https://security.microsoft.com)) and sign in.</span></span>
2. <span data-ttu-id="84216-137">탐색 창에서 작업 센터 **를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="84216-137">In the navigation pane, select **Action center**.</span></span> 

<span data-ttu-id="84216-138">작업 센터를 방문하면 보류 중인 작업 및 **기록의 두 개의 탭이** **표시됩니다.**</span><span class="sxs-lookup"><span data-stu-id="84216-138">When you visit the Action center, you see two tabs: **Pending actions** and **History**.</span></span> <span data-ttu-id="84216-139">다음 표에서는 각 탭에 표시하는 내용을 요약하여 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="84216-139">The following table summarizes what you'll see on each tab:</span></span>

|<span data-ttu-id="84216-140">Tab</span><span class="sxs-lookup"><span data-stu-id="84216-140">Tab</span></span>  |<span data-ttu-id="84216-141">설명</span><span class="sxs-lookup"><span data-stu-id="84216-141">Description</span></span>  |
|---------|---------|
|<span data-ttu-id="84216-142">**보류 중**</span><span class="sxs-lookup"><span data-stu-id="84216-142">**Pending**</span></span>     | <span data-ttu-id="84216-143">주의가 필요한 작업 목록을 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="84216-143">Displays a list of actions that require attention.</span></span> <span data-ttu-id="84216-144">작업을 한 번씩 승인하거나 거부하거나 동일한 유형의 작업(예: 파일 **Quarantine file)이** 있는 경우 여러 작업을 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="84216-144">You can approve or reject actions one at a time, or select multiple actions if they have the same type of action (such as **Quarantine file**).</span></span> <br/><span data-ttu-id="84216-145">**팁:** 자동화된 [](manage-auto-investigation.md) 조사가 제시간에 완료될 수 있도록 가능한 한 빨리 보류 중인 작업을 검토하고 승인(또는 거부)해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="84216-145">**TIP**: Make sure to [review and approve (or reject) pending actions](manage-auto-investigation.md) as soon as possible so that your automated investigations can complete in a timely manner.</span></span> |
|<span data-ttu-id="84216-146">**기록**</span><span class="sxs-lookup"><span data-stu-id="84216-146">**History**</span></span>     | <span data-ttu-id="84216-147">다음을 수행한 작업에 대한 감사 로그 역할을 합니다.</span><span class="sxs-lookup"><span data-stu-id="84216-147">Serves as an audit log for actions that were taken, such as:</span></span> <br/><span data-ttu-id="84216-148">- 자동화된 조사의 결과로 수행된 수정 작업</span><span class="sxs-lookup"><span data-stu-id="84216-148">- Remediation actions that were taken as a result of automated investigations</span></span> <br><span data-ttu-id="84216-149">- 보안 운영 팀에서 승인한 수정 작업</span><span class="sxs-lookup"><span data-stu-id="84216-149">- Remediation actions that were approved by your security operations team</span></span>  <br/><span data-ttu-id="84216-150">- 실행된 명령 및 라이브 응답 세션 중에 적용된 수정 작업</span><span class="sxs-lookup"><span data-stu-id="84216-150">- Commands that were run and remediation actions that were applied during Live Response sessions</span></span>  <br/><span data-ttu-id="84216-151">- Microsoft Defender 바이러스 백신의 위협 방지 기능에 의해 수행된 수정 작업</span><span class="sxs-lookup"><span data-stu-id="84216-151">- Remediation actions that were taken by threat protection features in Microsoft Defender Antivirus</span></span>  <p><span data-ttu-id="84216-152">특정 작업을 취소하는 방법을 제공합니다(완료된 작업 취소 [참조).](manage-auto-investigation.md#undo-completed-actions)</span><span class="sxs-lookup"><span data-stu-id="84216-152">Provides a way to undo certain actions (see [Undo completed actions](manage-auto-investigation.md#undo-completed-actions)).</span></span>       |

<span data-ttu-id="84216-153">관리 센터에서 데이터를 사용자 지정, 정렬, 필터링 및 내보낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="84216-153">You can customize, sort, filter, and export data in the Action center.</span></span>

:::image type="content" source="images/new-action-center-columnsfilters.png" alt-text="작업 센터의 열 및 필터":::

- <span data-ttu-id="84216-155">열 제목을 선택하여 항목을 오차 또는 내선 순서로 정렬합니다.</span><span class="sxs-lookup"><span data-stu-id="84216-155">Select a column heading to sort items in ascending or descending order.</span></span>
- <span data-ttu-id="84216-156">기간 필터를 사용하여 지난 일, 주, 30일 또는 6개월의 데이터를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="84216-156">Use the time period filter to view data for the past day, week, 30 days, or 6 months.</span></span>
- <span data-ttu-id="84216-157">보하려는 열을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="84216-157">Choose the columns that you want to view.</span></span>
- <span data-ttu-id="84216-158">각 데이터 페이지에 포함할 항목 수를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="84216-158">Specify how many items to include on each page of data.</span></span>
- <span data-ttu-id="84216-159">필터를 사용하여 보 원하는 항목만 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="84216-159">Use filters to view just the items you want to see.</span></span>
- <span data-ttu-id="84216-160">내보내기 **를** 선택하여 결과를 .csv 파일로 내보낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="84216-160">Select **Export** to export results to a .csv file.</span></span> 

## <a name="next-steps"></a><span data-ttu-id="84216-161">다음 단계</span><span class="sxs-lookup"><span data-stu-id="84216-161">Next steps</span></span>

- [<span data-ttu-id="84216-162">수정 작업 보기 및 승인</span><span class="sxs-lookup"><span data-stu-id="84216-162">View and approve remediation actions</span></span>](manage-auto-investigation.md)
- [<span data-ttu-id="84216-163">대화형 가이드를 참조하세요. Endpoint용 Microsoft Defender로 위협 조사 및 수정</span><span class="sxs-lookup"><span data-stu-id="84216-163">See the interactive guide: Investigate and remediate threats with Microsoft Defender for Endpoint</span></span>](https://aka.ms/MDATP-IR-Interactive-Guide)
 
## <a name="see-also"></a><span data-ttu-id="84216-164">참고 항목</span><span class="sxs-lookup"><span data-stu-id="84216-164">See also</span></span>

- [<span data-ttu-id="84216-165">끝점용 Microsoft Defender에서 가짓 긍정/음수 해결</span><span class="sxs-lookup"><span data-stu-id="84216-165">Address false positives/negatives in Microsoft Defender for Endpoint</span></span>](defender-endpoint-false-positives-negatives.md)
