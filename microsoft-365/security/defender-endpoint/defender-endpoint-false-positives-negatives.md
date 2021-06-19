---
title: Endpoint용 Microsoft Defender에서 가양성/가음성 처리
description: 끝점용 Microsoft Defender에서 가짓 긍정 또는 거짓 부정을 처리하는 방법을 학습합니다.
keywords: antivirus, exception, exclusion, Microsoft Defender for Endpoint, false positive, false negative, blocked file, blocked url
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.technology: mde
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
- m365solution-scenario
- m365scenario-fpfn
ms.topic: how-to
ms.reviewer: ramarom, evaldm, isco, mabraitm, chriggs, yonghree, jcedola
ms.custom: FPFN
ms.openlocfilehash: d3821f4f1f581da5353ee33bd406af8558c0e903
ms.sourcegitcommit: c70067b4ef9c6f8f04aca68c35bb5141857c4e4b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/19/2021
ms.locfileid: "53029960"
---
# <a name="address-false-positivesnegatives-in-microsoft-defender-for-endpoint"></a><span data-ttu-id="7b8a0-104">Endpoint용 Microsoft Defender에서 가양성/가음성 처리</span><span class="sxs-lookup"><span data-stu-id="7b8a0-104">Address false positives/negatives in Microsoft Defender for Endpoint</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="7b8a0-105">**적용 대상**</span><span class="sxs-lookup"><span data-stu-id="7b8a0-105">**Applies to**</span></span>

- [<span data-ttu-id="7b8a0-106">엔드포인트용 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="7b8a0-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2146806)

<span data-ttu-id="7b8a0-107">끝점 보호 솔루션에서 가짓 긍정은 엔터티가 실제로 위협이 아닌 경우에도 악성으로 검색되고 식별된 파일 또는 프로세스와 같은 엔터티입니다.</span><span class="sxs-lookup"><span data-stu-id="7b8a0-107">In endpoint protection solutions, a false positive is an entity, such as a file or a process, that was detected and identified as malicious, even though the entity isn't actually a threat.</span></span> <span data-ttu-id="7b8a0-108">거짓 부정은 실제로 악의적이어도 위협으로 검색되지 않은 엔터티입니다.</span><span class="sxs-lookup"><span data-stu-id="7b8a0-108">A false negative is an entity that was not detected as a threat, even though it actually is malicious.</span></span> <span data-ttu-id="7b8a0-109">끝점용 Microsoft Defender를 포함하여 모든 위협 방지 솔루션에서 [가긍성/부정이](microsoft-defender-endpoint.md)발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7b8a0-109">False positives/negatives can occur with any threat protection solution, including [Microsoft Defender for Endpoint](microsoft-defender-endpoint.md).</span></span>

![끝점용 Defender의 가짓 긍정 및 음수 정의](images/false-positives-overview.png)

<span data-ttu-id="7b8a0-111">다행히 이러한 종류의 문제를 해결하고 줄이기 위한 단계를 수행하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="7b8a0-111">Fortunately, steps can be taken to address and reduce these kinds of issues.</span></span> <span data-ttu-id="7b8a0-112">Microsoft 365 Defender(이전의 Microsoft Defender 보안 센터)에 가음성/부정이 표시될 경우 보안 운영에서 다음 프로세스를 사용하여 이를 해결하기 위한 단계를 취할 수 있습니다. [](microsoft-defender-security-center.md)</span><span class="sxs-lookup"><span data-stu-id="7b8a0-112">If you're seeing false positives/negatives in [Microsoft 365 Defender](microsoft-defender-security-center.md) (formerly the Microsoft Defender Security Center), your security operations can take steps to address them by using the following process:</span></span>

1. [<span data-ttu-id="7b8a0-113">경고 검토 및 분류</span><span class="sxs-lookup"><span data-stu-id="7b8a0-113">Review and classify alerts</span></span>](#part-1-review-and-classify-alerts)
2. [<span data-ttu-id="7b8a0-114">수행된 수정 작업 검토</span><span class="sxs-lookup"><span data-stu-id="7b8a0-114">Review remediation actions that were taken</span></span>](#part-2-review-remediation-actions)
3. [<span data-ttu-id="7b8a0-115">제외 검토 및 정의</span><span class="sxs-lookup"><span data-stu-id="7b8a0-115">Review and define exclusions</span></span>](#part-3-review-or-define-exclusions)
4. [<span data-ttu-id="7b8a0-116">분석을 위해 엔터티 제출</span><span class="sxs-lookup"><span data-stu-id="7b8a0-116">Submit an entity for analysis</span></span>](#part-4-submit-a-file-for-analysis)
5. [<span data-ttu-id="7b8a0-117">위협 방지 설정 검토 및 조정</span><span class="sxs-lookup"><span data-stu-id="7b8a0-117">Review and adjust your threat protection settings</span></span>](#part-5-review-and-adjust-your-threat-protection-settings)

<span data-ttu-id="7b8a0-118">이 문서에 설명된 작업을 수행한 후에도 여전히 가짓 긍정/음의 문제가 있는 경우 도움을 받을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7b8a0-118">You can get help if you still have issues with false positives/negatives after performing the tasks described in this article.</span></span> <span data-ttu-id="7b8a0-119">도움이 [필요한 경우를 참조하세요.](#still-need-help)</span><span class="sxs-lookup"><span data-stu-id="7b8a0-119">See [Still need help?](#still-need-help)</span></span>

![가음성 및 부정을 해결하기 위한 단계](images/false-positives-step-diagram.png)

> [!NOTE]
> <span data-ttu-id="7b8a0-121">이 문서는 [끝점용 Microsoft Defender를](microsoft-defender-endpoint.md)사용하는 보안 운영자 및 보안 관리자를 위한 지침입니다.</span><span class="sxs-lookup"><span data-stu-id="7b8a0-121">This article is intended as guidance for security operators and security administrators who are using [Microsoft Defender for Endpoint](microsoft-defender-endpoint.md).</span></span>

## <a name="part-1-review-and-classify-alerts"></a><span data-ttu-id="7b8a0-122">1부: 경고 검토 및 분류</span><span class="sxs-lookup"><span data-stu-id="7b8a0-122">Part 1: Review and classify alerts</span></span>

<span data-ttu-id="7b8a0-123">악의적 [](alerts.md) 또는 의심스러운 것으로 감지된 것으로 감지된 것으로서 트리거된 경고가 표시되면 해당 엔터티에 대한 경고를 표시하지 않을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7b8a0-123">If you see an [alert](alerts.md) that was triggered because something was detected as malicious or suspicious that should not have been, you can suppress the alert for that entity.</span></span> <span data-ttu-id="7b8a0-124">또한 반드시 가음성일 필요는 없지만 이의를 표시하지 않는 경고를 표시하지 않을 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7b8a0-124">You can also suppress alerts that are not necessarily false positives, but are unimportant.</span></span> <span data-ttu-id="7b8a0-125">경고도 분류하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="7b8a0-125">We recommend that you classify alerts as well.</span></span>

<span data-ttu-id="7b8a0-126">경고를 관리하고 참/거짓 긍정을 분류하면 위협 방지 솔루션을 교육하는 데 도움이 되고 시간 경과에 따라 가짓 긍정 또는 거짓 부정 수를 줄일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7b8a0-126">Managing your alerts and classifying true/false positives helps to train your threat protection solution and can reduce the number of false positives or false negatives over time.</span></span> <span data-ttu-id="7b8a0-127">이러한 단계를 수행하면 보안 팀이 우선 순위가 높은 작업 항목에 집중할 수 있도록 보안 작업 대시보드에서 노이즈를 줄이는 데도 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="7b8a0-127">Taking these steps also helps reduce noise in your security operations dashboard so that your security team can focus on higher priority work items.</span></span>

### <a name="determine-whether-an-alert-is-accurate"></a><span data-ttu-id="7b8a0-128">경고가 정확한지 확인</span><span class="sxs-lookup"><span data-stu-id="7b8a0-128">Determine whether an alert is accurate</span></span>

<span data-ttu-id="7b8a0-129">경고를 분류하거나 표시하지 말고 경고가 정확한지, 가음성인지 또는 양성인지 여부를 결정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7b8a0-129">Before you classify or suppress an alert, determine whether the alert is accurate, a false positive, or benign.</span></span>

1. <span data-ttu-id="7b8a0-130">Microsoft 365 Defender 포털()로 <https://security.microsoft.com> 이동하여 로그인합니다.</span><span class="sxs-lookup"><span data-stu-id="7b8a0-130">Go to the Microsoft 365 Defender portal (<https://security.microsoft.com>) and sign in.</span></span>

2. <span data-ttu-id="7b8a0-131">탐색 창에서 경고 큐 **를 선택 합니다.**</span><span class="sxs-lookup"><span data-stu-id="7b8a0-131">In the navigation pane, choose **Alerts queue**.</span></span>

3. <span data-ttu-id="7b8a0-132">경고에 대한 자세한 내용을 확인하려면 경고를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="7b8a0-132">Select an alert to more details about the alert.</span></span> <span data-ttu-id="7b8a0-133">[(Endpoint에 대한 Microsoft Defender의 경고 검토를 참조합니다.)](review-alerts.md)</span><span class="sxs-lookup"><span data-stu-id="7b8a0-133">(See [Review alerts in Microsoft Defender for Endpoint](review-alerts.md).)</span></span>

4. <span data-ttu-id="7b8a0-134">경고 상태에 따라 다음 표에 설명된 단계를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="7b8a0-134">Depending on the alert status, take the steps described in the following table:</span></span>

<br>

****

|<span data-ttu-id="7b8a0-135">경고 상태</span><span class="sxs-lookup"><span data-stu-id="7b8a0-135">Alert status</span></span>|<span data-ttu-id="7b8a0-136">수행할 작업</span><span class="sxs-lookup"><span data-stu-id="7b8a0-136">What to do</span></span>|
|---|---|
|<span data-ttu-id="7b8a0-137">경고가 정확합니다.</span><span class="sxs-lookup"><span data-stu-id="7b8a0-137">The alert is accurate</span></span>|<span data-ttu-id="7b8a0-138">경고를 할당한 다음 추가로 [조사합니다.](investigate-alerts.md)</span><span class="sxs-lookup"><span data-stu-id="7b8a0-138">Assign the alert, and then [investigate it](investigate-alerts.md) further.</span></span>|
|<span data-ttu-id="7b8a0-139">경고가 가긍성입니다.</span><span class="sxs-lookup"><span data-stu-id="7b8a0-139">The alert is a false positive</span></span>|<ol><li><span data-ttu-id="7b8a0-140">[경고를 가의](#classify-an-alert) 긍정으로 분류합니다.</span><span class="sxs-lookup"><span data-stu-id="7b8a0-140">[Classify the alert](#classify-an-alert) as a false positive.</span></span></li><li><span data-ttu-id="7b8a0-141">[경고를 표시하지 않습니다.](#suppress-an-alert)</span><span class="sxs-lookup"><span data-stu-id="7b8a0-141">[Suppress the alert](#suppress-an-alert).</span></span></li><li><span data-ttu-id="7b8a0-142">[끝점용](#indicators-for-microsoft-defender-for-endpoint) Microsoft Defender에 대한 표시기를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="7b8a0-142">[Create an indicator](#indicators-for-microsoft-defender-for-endpoint) for Microsoft Defender for Endpoint.</span></span></li><li><span data-ttu-id="7b8a0-143">[분석을 위해 Microsoft에 파일을 제출합니다.](#part-4-submit-a-file-for-analysis)</span><span class="sxs-lookup"><span data-stu-id="7b8a0-143">[Submit a file to Microsoft for analysis](#part-4-submit-a-file-for-analysis).</span></span></li></ol>|
|<span data-ttu-id="7b8a0-144">경고는 정확하지만 양성(미미한)</span><span class="sxs-lookup"><span data-stu-id="7b8a0-144">The alert is accurate, but benign (unimportant)</span></span>|<span data-ttu-id="7b8a0-145">[경고를](#classify-an-alert) 실제 양의 경고로 분류한 다음 [경고를 표시하지 않습니다.](#suppress-an-alert)</span><span class="sxs-lookup"><span data-stu-id="7b8a0-145">[Classify the alert](#classify-an-alert) as a true positive, and then [suppress the alert](#suppress-an-alert).</span></span>|
|||

### <a name="classify-an-alert"></a><span data-ttu-id="7b8a0-146">경고 분류</span><span class="sxs-lookup"><span data-stu-id="7b8a0-146">Classify an alert</span></span>

<span data-ttu-id="7b8a0-147">알림은 알림에서 가짓 긍정 또는 참 긍정으로 분류될 Microsoft 365 Defender.</span><span class="sxs-lookup"><span data-stu-id="7b8a0-147">Alerts can be classified as false positives or true positives in Microsoft 365 Defender.</span></span> <span data-ttu-id="7b8a0-148">경고를 분류하면 시간이 지날수록 더 많은 참 경고와 더 적은 거짓 경고를 볼 수 있도록 끝점에 대해 Microsoft Defender를 교육하는 데 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="7b8a0-148">Classifying alerts helps train Microsoft Defender for Endpoint so that, over time, you'll see more true alerts and fewer false alerts.</span></span>

1. <span data-ttu-id="7b8a0-149">Microsoft 365 Defender 포털()로 <https://security.microsoft.com> 이동하여 로그인합니다.</span><span class="sxs-lookup"><span data-stu-id="7b8a0-149">Go to the Microsoft 365 Defender portal (<https://security.microsoft.com>) and sign in.</span></span>

2. <span data-ttu-id="7b8a0-150">경고 **큐 를** 선택한 다음 경고를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="7b8a0-150">Select **Alerts queue**, and then select an alert.</span></span>

3. <span data-ttu-id="7b8a0-151">선택한 경고에 대해 **작업** 관리  >  **경고 를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="7b8a0-151">For the selected alert, select **Actions** > **Manage alert**.</span></span> <span data-ttu-id="7b8a0-152">플라이아웃 창이 열립니다.</span><span class="sxs-lookup"><span data-stu-id="7b8a0-152">A flyout pane opens.</span></span>

4. <span data-ttu-id="7b8a0-153">경고 **관리 섹션에서** True 경고 또는 **거짓 경고** **를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="7b8a0-153">In the **Manage alert** section, select either **True alert** or **False alert**.</span></span> <span data-ttu-id="7b8a0-154">(False **경고를 사용하여** 가음성 분류)</span><span class="sxs-lookup"><span data-stu-id="7b8a0-154">(Use **False alert** to classify a false positive.)</span></span>

> [!TIP]
> <span data-ttu-id="7b8a0-155">경고 표시 안 에 대한 자세한 내용은 [Endpoint 경고에 대한 Microsoft Defender 관리를 참조하세요.](/microsoft-365/security/defender-endpoint/manage-alerts)</span><span class="sxs-lookup"><span data-stu-id="7b8a0-155">For more information about suppressing alerts, see [Manage Microsoft Defender for Endpoint alerts](/microsoft-365/security/defender-endpoint/manage-alerts).</span></span> <span data-ttu-id="7b8a0-156">또한 조직에서 SIEM(보안 정보 및 이벤트 관리) 서버를 사용하는 경우 제거 규칙도 정의해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7b8a0-156">And, if your organization is using a security information and event management (SIEM) server, make sure to define a suppression rule there, too.</span></span>

### <a name="suppress-an-alert"></a><span data-ttu-id="7b8a0-157">경고 표시 안</span><span class="sxs-lookup"><span data-stu-id="7b8a0-157">Suppress an alert</span></span>

<span data-ttu-id="7b8a0-158">가음성 또는 참 긍정이지만 미미한 이벤트에 대한 경고가 있는 경우 경고를 표시하지 Microsoft 365 Defender.</span><span class="sxs-lookup"><span data-stu-id="7b8a0-158">If you have alerts that are either false positives or that are true positives but for unimportant events, you can suppress those alerts in Microsoft 365 Defender.</span></span> <span data-ttu-id="7b8a0-159">경고를 표시하지는 것은 보안 작업 대시보드에서 노이즈를 줄이는 데 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="7b8a0-159">Suppressing alerts helps reduce noise in your security operations dashboard.</span></span>

1. <span data-ttu-id="7b8a0-160">Microsoft 365 Defender 포털()로 <https://security.microsoft.com> 이동하여 로그인합니다.</span><span class="sxs-lookup"><span data-stu-id="7b8a0-160">Go to the Microsoft 365 Defender portal (<https://security.microsoft.com>) and sign in.</span></span>

2. <span data-ttu-id="7b8a0-161">탐색 창에서 경고 큐 **를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="7b8a0-161">In the navigation pane, select **Alerts queue**.</span></span>

3. <span data-ttu-id="7b8a0-162">세부 정보 창을 열기 위해 표시하지하려는 **경고를** 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="7b8a0-162">Select an alert that you want to suppress to open its **Details** pane.</span></span>

4. <span data-ttu-id="7b8a0-163">세부 **정보 창에서** 타원(**...**)을 선택한 다음 제거 **규칙 만들기 를 선택 합니다.**</span><span class="sxs-lookup"><span data-stu-id="7b8a0-163">In the **Details** pane, choose the ellipsis (**...**), and then **Create a suppression rule**.</span></span>

5. <span data-ttu-id="7b8a0-164">제거 규칙에 대한 모든 설정을 지정한 다음 저장 을 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="7b8a0-164">Specify all the settings for your suppression rule, and then choose **Save**.</span></span>

> [!TIP]
> <span data-ttu-id="7b8a0-165">제거 규칙에 대한 도움이 필요하세요?</span><span class="sxs-lookup"><span data-stu-id="7b8a0-165">Need help with suppression rules?</span></span> <span data-ttu-id="7b8a0-166">경고 [표시 안 를 참조하고 새 제거 규칙 만들기를 참조합니다.](/microsoft-365/security/defender-endpoint/manage-alerts#suppress-an-alert-and-create-a-new-suppression-rule)</span><span class="sxs-lookup"><span data-stu-id="7b8a0-166">See [Suppress an alert and create a new suppression rule](/microsoft-365/security/defender-endpoint/manage-alerts#suppress-an-alert-and-create-a-new-suppression-rule).</span></span>

## <a name="part-2-review-remediation-actions"></a><span data-ttu-id="7b8a0-167">2부: 재구성 작업 검토</span><span class="sxs-lookup"><span data-stu-id="7b8a0-167">Part 2: Review remediation actions</span></span>

<span data-ttu-id="7b8a0-168">[파일을 검지로](manage-auto-investigation.md#remediation-actions)보내거나 프로세스를 중지하는 등의 수정 작업은 위협으로 감지된 엔터티(예: 파일)에 대해 수행됩니다.</span><span class="sxs-lookup"><span data-stu-id="7b8a0-168">[Remediation actions](manage-auto-investigation.md#remediation-actions), such as sending a file to quarantine or stopping a process, are taken on entities (such as files) that are detected as threats.</span></span> <span data-ttu-id="7b8a0-169">자동화된 조사 및 다음 작업을 통해 여러 유형의 Microsoft Defender 바이러스 백신.</span><span class="sxs-lookup"><span data-stu-id="7b8a0-169">Several types of remediation actions occur automatically through automated investigation and Microsoft Defender Antivirus:</span></span>

- <span data-ttu-id="7b8a0-170">파일 Quarantine a file</span><span class="sxs-lookup"><span data-stu-id="7b8a0-170">Quarantine a file</span></span>
- <span data-ttu-id="7b8a0-171">레지스트리 키 제거</span><span class="sxs-lookup"><span data-stu-id="7b8a0-171">Remove a registry key</span></span>
- <span data-ttu-id="7b8a0-172">프로세스 숨기기</span><span class="sxs-lookup"><span data-stu-id="7b8a0-172">Kill a process</span></span>
- <span data-ttu-id="7b8a0-173">서비스 중지</span><span class="sxs-lookup"><span data-stu-id="7b8a0-173">Stop a service</span></span>
- <span data-ttu-id="7b8a0-174">드라이버를 사용하지 않도록 설정</span><span class="sxs-lookup"><span data-stu-id="7b8a0-174">Disable a driver</span></span>
- <span data-ttu-id="7b8a0-175">예약된 작업 제거</span><span class="sxs-lookup"><span data-stu-id="7b8a0-175">Remove a scheduled task</span></span>

<span data-ttu-id="7b8a0-176">바이러스 백신 검사 시작 또는 조사 패키지 수집과 같은 기타 작업은 수동 또는 [라이브 응답을 통해 수행됩니다.](live-response.md)</span><span class="sxs-lookup"><span data-stu-id="7b8a0-176">Other actions, such as starting an antivirus scan or collecting an investigation package, occur manually or through [Live Response](live-response.md).</span></span> <span data-ttu-id="7b8a0-177">Live Response를 통해 수행된 작업은 다시 수행할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="7b8a0-177">Actions taken through Live Response cannot be undone.</span></span>

<span data-ttu-id="7b8a0-178">알림을 검토한 후 다음 단계는 수정 작업을 [검토하는 것입니다.](manage-auto-investigation.md)</span><span class="sxs-lookup"><span data-stu-id="7b8a0-178">After you have reviewed your alerts, your next step is to [review remediation actions](manage-auto-investigation.md).</span></span> <span data-ttu-id="7b8a0-179">가짓 긍정으로 인해 작업이 수행된 경우 대부분의 종류의 수정 작업을 취소할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7b8a0-179">If any actions were taken as a result of false positives, you can undo most kinds of remediation actions.</span></span> <span data-ttu-id="7b8a0-180">특히 다음을 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7b8a0-180">Specifically, you can:</span></span>

- [<span data-ttu-id="7b8a0-181">작업 센터에서 고지된 파일 복원</span><span class="sxs-lookup"><span data-stu-id="7b8a0-181">Restore a quarantined file from the Action Center</span></span>](#restore-a-quarantined-file-from-the-action-center)
- [<span data-ttu-id="7b8a0-182">한 번씩 여러 작업 취소</span><span class="sxs-lookup"><span data-stu-id="7b8a0-182">Undo multiple actions at one time</span></span>](#undo-multiple-actions-at-one-time)
- <span data-ttu-id="7b8a0-183">여러 장치에서 파일을 [검지에서 제거합니다.](#remove-a-file-from-quarantine-across-multiple-devices)</span><span class="sxs-lookup"><span data-stu-id="7b8a0-183">[Remove a file from quarantine across multiple devices](#remove-a-file-from-quarantine-across-multiple-devices).</span></span>  <span data-ttu-id="7b8a0-184">및</span><span class="sxs-lookup"><span data-stu-id="7b8a0-184">and</span></span>
- [<span data-ttu-id="7b8a0-185">격리로부터 파일 복원</span><span class="sxs-lookup"><span data-stu-id="7b8a0-185">Restore file from quarantine</span></span>](#restore-file-from-quarantine)

<span data-ttu-id="7b8a0-186">가짓 긍정의 결과로 수행된 작업의 검토 및 취소가 완료되면 계속 검토하거나 [제외를 정의합니다.](#part-3-review-or-define-exclusions)</span><span class="sxs-lookup"><span data-stu-id="7b8a0-186">When you're done reviewing and undoing actions that were taken as a result of false positives, proceed to [review or define exclusions](#part-3-review-or-define-exclusions).</span></span>

### <a name="review-completed-actions"></a><span data-ttu-id="7b8a0-187">완료된 작업 검토</span><span class="sxs-lookup"><span data-stu-id="7b8a0-187">Review completed actions</span></span>

1. <span data-ttu-id="7b8a0-188">Go to the Action center ( <https://security.microsoft.com/action-center> ) and sign in.</span><span class="sxs-lookup"><span data-stu-id="7b8a0-188">Go to the Action center (<https://security.microsoft.com/action-center>) and sign in.</span></span>

2. <span data-ttu-id="7b8a0-189">사용 기록 **탭을** 선택하여 수행된 작업 목록을 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7b8a0-189">Select the **History** tab to view a list of actions that were taken.</span></span>

3. <span data-ttu-id="7b8a0-190">항목을 선택하여 수행된 수정 조치에 대한 자세한 정보를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7b8a0-190">Select an item to view more details about the remediation action that was taken.</span></span>

### <a name="restore-a-quarantined-file-from-the-action-center"></a><span data-ttu-id="7b8a0-191">작업 센터에서 고지된 파일 복원</span><span class="sxs-lookup"><span data-stu-id="7b8a0-191">Restore a quarantined file from the Action Center</span></span>

1. <span data-ttu-id="7b8a0-192">Go to the Action center ( <https://security.microsoft.com/action-center> ) and sign in.</span><span class="sxs-lookup"><span data-stu-id="7b8a0-192">Go to the Action center (<https://security.microsoft.com/action-center>) and sign in.</span></span>

2. <span data-ttu-id="7b8a0-193">사용 **기록 탭에서** 실행 취소할 작업을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="7b8a0-193">On the **History** tab, select an action that you want to undo.</span></span>

3. <span data-ttu-id="7b8a0-194">플라이아웃 창에서 **취소를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="7b8a0-194">In the flyout pane, select **Undo**.</span></span> <span data-ttu-id="7b8a0-195">이 메서드를 사용하여 작업을 취소할 수 없는 경우 실행 취소 **단추가 표시되지** 않습니다.</span><span class="sxs-lookup"><span data-stu-id="7b8a0-195">If the action cannot be undone with this method, you will not see an **Undo** button.</span></span> <span data-ttu-id="7b8a0-196">자세한 내용은 완료된 작업 [취소를 참조합니다.](manage-auto-investigation.md#undo-completed-actions)</span><span class="sxs-lookup"><span data-stu-id="7b8a0-196">(To learn more, see [Undo completed actions](manage-auto-investigation.md#undo-completed-actions).)</span></span>

### <a name="undo-multiple-actions-at-one-time"></a><span data-ttu-id="7b8a0-197">한 번씩 여러 작업 취소</span><span class="sxs-lookup"><span data-stu-id="7b8a0-197">Undo multiple actions at one time</span></span>

1. <span data-ttu-id="7b8a0-198">Go to the Action center ( <https://security.microsoft.com/action-center> ) and sign in.</span><span class="sxs-lookup"><span data-stu-id="7b8a0-198">Go to the Action center (<https://security.microsoft.com/action-center>) and sign in.</span></span>

2. <span data-ttu-id="7b8a0-199">사용 **기록 탭에서** 취소할 작업을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="7b8a0-199">On the **History** tab, select the actions that you want to undo.</span></span>

3. <span data-ttu-id="7b8a0-200">화면 오른쪽 창에서 **취소를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="7b8a0-200">In the pane on the right side of the screen, select **Undo**.</span></span>

### <a name="remove-a-file-from-quarantine-across-multiple-devices"></a><span data-ttu-id="7b8a0-201">여러 장치에서 파일 제거</span><span class="sxs-lookup"><span data-stu-id="7b8a0-201">Remove a file from quarantine across multiple devices</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="7b8a0-202">![파일 격리](images/autoir-quarantine-file-1.png)</span><span class="sxs-lookup"><span data-stu-id="7b8a0-202">![Quarantine file](images/autoir-quarantine-file-1.png)</span></span>

1. <span data-ttu-id="7b8a0-203">Go to the Action center ( <https://security.microsoft.com/action-center> ) and sign in.</span><span class="sxs-lookup"><span data-stu-id="7b8a0-203">Go to the Action center (<https://security.microsoft.com/action-center>) and sign in.</span></span>

2. <span data-ttu-id="7b8a0-204">사용 기록 **탭에서** 작업 유형이 **Quarantine** file인 파일을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="7b8a0-204">On the **History** tab, select a file that has the Action type **Quarantine file**.</span></span>

3. <span data-ttu-id="7b8a0-205">화면 오른쪽 창에서 이 파일의 X **추가** 인스턴스에 적용을 선택한 다음 실행 **취소를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="7b8a0-205">In the pane on the right side of the screen, select **Apply to X more instances of this file**, and then select **Undo**.</span></span>

### <a name="restore-file-from-quarantine"></a><span data-ttu-id="7b8a0-206">격리로부터 파일 복원</span><span class="sxs-lookup"><span data-stu-id="7b8a0-206">Restore file from quarantine</span></span>

<span data-ttu-id="7b8a0-207">조사 후에 파일이 정리된 것으로 판단되면 파일을 롤백하고 검지에서 제거할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7b8a0-207">You can roll back and remove a file from quarantine if you've determined that it's clean after an investigation.</span></span> <span data-ttu-id="7b8a0-208">파일이 중단된 각 디바이스에서 다음 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="7b8a0-208">Run the following command on each device where the file was quarantined.</span></span>

1. <span data-ttu-id="7b8a0-209">디바이스에서 상승된 명령줄 프롬프트를 니다.</span><span class="sxs-lookup"><span data-stu-id="7b8a0-209">Open an elevated command–line prompt on the device:</span></span>
   1. <span data-ttu-id="7b8a0-210">**시작**(으)로 이동하고 _cmd_ 를 입력하십시오.</span><span class="sxs-lookup"><span data-stu-id="7b8a0-210">Go to **Start** and type _cmd_.</span></span>
   2. <span data-ttu-id="7b8a0-211">명령 **프롬프트를 마우스 오른쪽 단추로 클릭하고** **관리자 권한으로 실행을 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="7b8a0-211">Right–click **Command prompt** and select **Run as administrator**.</span></span>

2. <span data-ttu-id="7b8a0-212">다음 명령을 입력하고 **Enter를 누를 수 있습니다.**</span><span class="sxs-lookup"><span data-stu-id="7b8a0-212">Enter the following command, and press **Enter**:</span></span>

    ```console
    "ProgramFiles%\Windows Defender\MpCmdRun.exe" –Restore –Name EUS:Win32/CustomEnterpriseBlock –All
    ```

    > [!IMPORTANT]
    > <span data-ttu-id="7b8a0-213">일부 시나리오에서는 **ThreatName이** 로 표시될 수 `EUS:Win32/CustomEnterpriseBlock!cl` 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7b8a0-213">In some scenarios, the **ThreatName** may appear as `EUS:Win32/CustomEnterpriseBlock!cl`.</span></span> <span data-ttu-id="7b8a0-214">Endpoint용 Defender는 지난 30일 동안 이 장치에서 차단된 모든 사용자 지정 차단 파일을 복원합니다.</span><span class="sxs-lookup"><span data-stu-id="7b8a0-214">Defender for Endpoint will restore all custom blocked files that were quarantined on this device in the last 30 days.</span></span>
    >
    > <span data-ttu-id="7b8a0-215">잠재적인 네트워크 위협으로 고지된 파일은 복구할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="7b8a0-215">A file that was quarantined as a potential network threat might not be recoverable.</span></span> <span data-ttu-id="7b8a0-216">사용자가 파일을 검지 후에 복원하려고 시도하면 해당 파일에 액세스할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="7b8a0-216">If a user attempts to restore the file after quarantine, that file might not be accessible.</span></span> <span data-ttu-id="7b8a0-217">시스템에 파일에 액세스하기 위한 네트워크 자격 증명이 더 이상 필요하기 때문일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7b8a0-217">This can be due to the system no longer having network credentials to access the file.</span></span> <span data-ttu-id="7b8a0-218">일반적으로 시스템 또는 공유 폴더에 일시적으로 로그온하고 액세스 토큰이 만료된 결과입니다.</span><span class="sxs-lookup"><span data-stu-id="7b8a0-218">Typically, this is a result of a temporary log on to a system or shared folder and the access tokens expired.</span></span>

3. <span data-ttu-id="7b8a0-219">화면 오른쪽 창에서 이 파일의 X **추가** 인스턴스에 적용을 선택한 다음 실행 **취소를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="7b8a0-219">In the pane on the right side of the screen, select **Apply to X more instances of this file**, and then select **Undo**.</span></span>

## <a name="part-3-review-or-define-exclusions"></a><span data-ttu-id="7b8a0-220">3부: 제외 검토 또는 정의</span><span class="sxs-lookup"><span data-stu-id="7b8a0-220">Part 3: Review or define exclusions</span></span>

<span data-ttu-id="7b8a0-221">제외는 수정 작업의 예외로 지정하는 파일 또는 URL과 같은 엔터티입니다.</span><span class="sxs-lookup"><span data-stu-id="7b8a0-221">An exclusion is an entity, such as a file or URL, that you specify as an exception to remediation actions.</span></span> <span data-ttu-id="7b8a0-222">제외된 엔터티는 계속 검색될 수 있지만 이 엔터티에 대해 수정 작업이 수행되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="7b8a0-222">The excluded entity can still get detected, but no remediation actions are taken on that entity.</span></span> <span data-ttu-id="7b8a0-223">즉, 검색된 파일 또는 프로세스가 중지되거나, 끝점용 Microsoft Defender에 의해 중지, 제거 또는 변경되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="7b8a0-223">That is, the detected file or process won't be stopped, sent to quarantine, removed, or otherwise changed by Microsoft Defender for Endpoint.</span></span>

<span data-ttu-id="7b8a0-224">끝점용 Microsoft Defender에서 제외를 정의하기 위해 다음 작업을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="7b8a0-224">To define exclusions across Microsoft Defender for Endpoint, perform the following tasks:</span></span>

- [<span data-ttu-id="7b8a0-225">사용자에 대한 제외 Microsoft Defender 바이러스 백신</span><span class="sxs-lookup"><span data-stu-id="7b8a0-225">Define exclusions for Microsoft Defender Antivirus</span></span>](#exclusions-for-microsoft-defender-antivirus)
- [<span data-ttu-id="7b8a0-226">끝점용 Microsoft Defender에 대한 "허용" 표시기 만들기</span><span class="sxs-lookup"><span data-stu-id="7b8a0-226">Create "allow" indicators for Microsoft Defender for Endpoint</span></span>](#indicators-for-microsoft-defender-for-endpoint)

> [!NOTE]
> <span data-ttu-id="7b8a0-227">Microsoft Defender 바이러스 백신 제외는 다른 끝점용 Microsoft Defender 기능이 아닌 바이러스 백신 보호에만 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="7b8a0-227">Microsoft Defender Antivirus exclusions apply only to antivirus protection, not across other Microsoft Defender for Endpoint capabilities.</span></span> <span data-ttu-id="7b8a0-228">파일을 광범위하게 제외하려면 끝점용 Microsoft Defender에 [](/microsoft-365/security/defender-endpoint/manage-indicators) 대한 Microsoft Defender 바이러스 백신 및 사용자 지정 표시기를 제외합니다.</span><span class="sxs-lookup"><span data-stu-id="7b8a0-228">To exclude files broadly, use exclusions for Microsoft Defender Antivirus and [custom indicators](/microsoft-365/security/defender-endpoint/manage-indicators) for Microsoft Defender for Endpoint.</span></span>

<span data-ttu-id="7b8a0-229">이 섹션의 절차에서는 제외 및 표시기를 정의하는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="7b8a0-229">The procedures in this section describe how to define exclusions and indicators.</span></span>

### <a name="exclusions-for-microsoft-defender-antivirus"></a><span data-ttu-id="7b8a0-230">Microsoft Defender 바이러스 백신</span><span class="sxs-lookup"><span data-stu-id="7b8a0-230">Exclusions for Microsoft Defender Antivirus</span></span>

<span data-ttu-id="7b8a0-231">일반적으로는 사용자에 대한 제외를 정의할 필요가 Microsoft Defender 바이러스 백신.</span><span class="sxs-lookup"><span data-stu-id="7b8a0-231">In general, you should not need to define exclusions for Microsoft Defender Antivirus.</span></span> <span data-ttu-id="7b8a0-232">제외는 반드시 정의해야 합니다. 그리고 가을의 결과로 생성되는 파일, 폴더, 프로세스 및 프로세스에서 연 파일만 포함해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7b8a0-232">Make sure that you define exclusions sparingly, and that you only include the files, folders, processes, and process-opened files that are resulting in false positives.</span></span> <span data-ttu-id="7b8a0-233">또한 정의된 제외를 정기적으로 검토해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7b8a0-233">In addition, make sure to review your defined exclusions regularly.</span></span> <span data-ttu-id="7b8a0-234">바이러스 백신 제외 [Microsoft Endpoint Manager](/mem/endpoint-manager-overview) 정의하거나 편집하는 것이 좋습니다. 그러나 그룹 정책과 같은 다른 [](/azure/active-directory-domain-services/manage-group-policy) 방법을 사용할 수 [있습니다(끝점용 Microsoft Defender 관리 참조).](manage-atp-post-migration.md)</span><span class="sxs-lookup"><span data-stu-id="7b8a0-234">We recommend using [Microsoft Endpoint Manager](/mem/endpoint-manager-overview) to define or edit your antivirus exclusions; however, you can use other methods, such as [Group Policy](/azure/active-directory-domain-services/manage-group-policy) (see [Manage Microsoft Defender for Endpoint](manage-atp-post-migration.md)).</span></span>

> [!TIP]
> <span data-ttu-id="7b8a0-235">바이러스 백신 제외에 대한 도움이 필요하세요?</span><span class="sxs-lookup"><span data-stu-id="7b8a0-235">Need help with antivirus exclusions?</span></span> <span data-ttu-id="7b8a0-236">자세한 [내용은 Configure and validate exclusions for Microsoft Defender 바이러스 백신 참조.](configure-exclusions-microsoft-defender-antivirus.md)</span><span class="sxs-lookup"><span data-stu-id="7b8a0-236">See [Configure and validate exclusions for Microsoft Defender Antivirus scans](configure-exclusions-microsoft-defender-antivirus.md).</span></span>

#### <a name="use-microsoft-endpoint-manager-to-manage-antivirus-exclusions-for-existing-policies"></a><span data-ttu-id="7b8a0-237">이 Microsoft Endpoint Manager 사용하여 바이러스 백신 제외 관리(기존 정책의 경우)</span><span class="sxs-lookup"><span data-stu-id="7b8a0-237">Use Microsoft Endpoint Manager to manage antivirus exclusions (for existing policies)</span></span>

1. <span data-ttu-id="7b8a0-238">Microsoft Endpoint Manager 관리 센터()로 이동하여 <https://endpoint.microsoft.com> 로그인합니다.</span><span class="sxs-lookup"><span data-stu-id="7b8a0-238">Go to the Microsoft Endpoint Manager admin center (<https://endpoint.microsoft.com>) and sign in.</span></span>

2. <span data-ttu-id="7b8a0-239">끝점 **보안 바이러스 백신** 을 선택한 다음 기존 정책을  >  선택합니다.</span><span class="sxs-lookup"><span data-stu-id="7b8a0-239">Choose **Endpoint security** > **Antivirus**, and then select an existing policy.</span></span> <span data-ttu-id="7b8a0-240">기존 정책이 없는 경우 또는 새 정책을 만들 수 있는 경우 다음 절차로 [건너뛰어도 됩니다.](#use-microsoft-endpoint-manager-to-create-a-new-antivirus-policy-with-exclusions)</span><span class="sxs-lookup"><span data-stu-id="7b8a0-240">(If you don't have an existing policy, or you want to create a new policy, skip to [the next procedure](#use-microsoft-endpoint-manager-to-create-a-new-antivirus-policy-with-exclusions)).</span></span>

3. <span data-ttu-id="7b8a0-241">속성 **을** 선택하고 구성 설정 **옆에** 있는 편집 **을 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="7b8a0-241">Choose **Properties**, and next to **Configuration settings**, choose **Edit**.</span></span>

4. <span data-ttu-id="7b8a0-242">제외 **Microsoft Defender 바이러스 백신** 확장한 다음 제외를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="7b8a0-242">Expand **Microsoft Defender Antivirus Exclusions** and then specify your exclusions.</span></span>

5. <span data-ttu-id="7b8a0-243">검토 **+ 저장 을** 선택한 다음 저장 을 **선택 합니다.**</span><span class="sxs-lookup"><span data-stu-id="7b8a0-243">Choose **Review + save**, and then choose **Save**.</span></span>

#### <a name="use-microsoft-endpoint-manager-to-create-a-new-antivirus-policy-with-exclusions"></a><span data-ttu-id="7b8a0-244">다음 Microsoft Endpoint Manager 사용하여 제외가 있는 새 바이러스 백신 정책 만들기</span><span class="sxs-lookup"><span data-stu-id="7b8a0-244">Use Microsoft Endpoint Manager to create a new antivirus policy with exclusions</span></span>

1. <span data-ttu-id="7b8a0-245">Microsoft Endpoint Manager 관리 센터()로 이동하여 <https://endpoint.microsoft.com> 로그인합니다.</span><span class="sxs-lookup"><span data-stu-id="7b8a0-245">Go to the Microsoft Endpoint Manager admin center (<https://endpoint.microsoft.com>) and sign in.</span></span>

2. <span data-ttu-id="7b8a0-246">끝점 **보안 바이러스**  >  **백신**  >  **+ 정책 만들기 를 선택 합니다.**</span><span class="sxs-lookup"><span data-stu-id="7b8a0-246">Choose **Endpoint security** > **Antivirus** > **+ Create Policy**.</span></span>

3. <span data-ttu-id="7b8a0-247">플랫폼(예: Windows 10 이상, **macOS** **또는** Windows 10 및 Windows **서버)을 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="7b8a0-247">Select a platform (such as **Windows 10 and later**, **macOS**, or **Windows 10 and Windows Server**).</span></span>

4. <span data-ttu-id="7b8a0-248">**프로필에서** 제외 **Microsoft Defender 바이러스 백신** 를 선택한 다음 만들기 를 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="7b8a0-248">For **Profile**, select **Microsoft Defender Antivirus exclusions**, and then choose **Create**.</span></span>

5. <span data-ttu-id="7b8a0-249">프로필의 이름과 설명을 지정하고 다음 을 **선택하십시오.**</span><span class="sxs-lookup"><span data-stu-id="7b8a0-249">Specify a name and description for the profile, and then choose **Next**.</span></span>

6. <span data-ttu-id="7b8a0-250">구성 **설정 탭에서** 바이러스 백신 제외를 지정하고 다음 을 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="7b8a0-250">On the **Configuration settings** tab, specify your antivirus exclusions, and then choose **Next**.</span></span>

7. <span data-ttu-id="7b8a0-251">조직에서  범위 태그를 사용하는 경우 범위 태그 탭에서 만들 정책의 범위 태그를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="7b8a0-251">On the **Scope tags** tab, if you are using scope tags in your organization, specify scope tags for the policy you are creating.</span></span> <span data-ttu-id="7b8a0-252">범위 [태그를 참조합니다.](/mem/intune/fundamentals/scope-tags)</span><span class="sxs-lookup"><span data-stu-id="7b8a0-252">(See [Scope tags](/mem/intune/fundamentals/scope-tags).)</span></span>

8. <span data-ttu-id="7b8a0-253">할당 **탭에서** 정책을 적용할 사용자 및 그룹을 지정하고 다음 을 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="7b8a0-253">On the **Assignments** tab, specify the users and groups to whom your policy should be applied, and then choose **Next**.</span></span> <span data-ttu-id="7b8a0-254">할당에 대한 도움이 필요한 경우 에서 사용자 및 장치 프로필 [할당을 Microsoft Intune.](/mem/intune/configuration/device-profile-assign)</span><span class="sxs-lookup"><span data-stu-id="7b8a0-254">(If you need help with assignments, see [Assign user and device profiles in Microsoft Intune](/mem/intune/configuration/device-profile-assign).)</span></span>

9. <span data-ttu-id="7b8a0-255">검토 **+ 만들기 탭에서** 설정을 검토한 다음 만들기 를 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="7b8a0-255">On the **Review + create** tab, review the settings, and then choose **Create**.</span></span>

### <a name="indicators-for-microsoft-defender-for-endpoint"></a><span data-ttu-id="7b8a0-256">끝점용 Microsoft Defender 표시기</span><span class="sxs-lookup"><span data-stu-id="7b8a0-256">Indicators for Microsoft Defender for Endpoint</span></span>

<span data-ttu-id="7b8a0-257">[지표(특히](/microsoft-365/security/defender-endpoint/manage-indicators) 손상 표시기 또는 IoC)를 사용하면 보안 운영 팀이 엔터티의 검색, 방지 및 제외를 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7b8a0-257">[Indicators](/microsoft-365/security/defender-endpoint/manage-indicators) (specifically, indicators of compromise, or IoCs) enable your security operations team to define the detection, prevention, and exclusion of entities.</span></span> <span data-ttu-id="7b8a0-258">예를 들어 끝점용 Microsoft Defender의 검사 및 수정 작업에서 생략할 특정 파일을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7b8a0-258">For example, you can specify certain files to be omitted from scans and remediation actions in Microsoft Defender for Endpoint.</span></span> <span data-ttu-id="7b8a0-259">또는 표시기를 사용하여 특정 파일, IP 주소 또는 URL에 대한 알림을 생성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7b8a0-259">Or, indicators can be used to generate alerts for certain files, IP addresses, or URLs.</span></span>

<span data-ttu-id="7b8a0-260">엔터티를 끝점용 Microsoft Defender에 대한 제외로 지정하기 위해 해당 엔터티에 대한 "허용" 표시기를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="7b8a0-260">To specify entities as exclusions for Microsoft Defender for Endpoint, create "allow" indicators for those entities.</span></span> <span data-ttu-id="7b8a0-261">끝점용 Microsoft Defender의 이러한 "허용" 표시기는 차세대 [](overview-endpoint-detection-response.md) [보호,](microsoft-defender-antivirus-in-windows-10.md)엔드포인트 감지 및 응답 및 자동화된 조사 & [적용됩니다.](/microsoft-365/security/defender-endpoint/automated-investigations)</span><span class="sxs-lookup"><span data-stu-id="7b8a0-261">Such "allow" indicators in Microsoft Defender for Endpoint apply to [next-generation protection](microsoft-defender-antivirus-in-windows-10.md), [endpoint detection and response](overview-endpoint-detection-response.md), and [automated investigation & remediation](/microsoft-365/security/defender-endpoint/automated-investigations).</span></span>

<span data-ttu-id="7b8a0-262">다음에 대해 "허용" 표시기를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7b8a0-262">"Allow" indicators can be created for:</span></span>

- [<span data-ttu-id="7b8a0-263">파일</span><span class="sxs-lookup"><span data-stu-id="7b8a0-263">Files</span></span>](#indicators-for-files)
- [<span data-ttu-id="7b8a0-264">IP 주소, URL 및 도메인</span><span class="sxs-lookup"><span data-stu-id="7b8a0-264">IP addresses, URLs, and domains</span></span>](#indicators-for-ip-addresses-urls-or-domains)
- [<span data-ttu-id="7b8a0-265">응용 프로그램 인증서</span><span class="sxs-lookup"><span data-stu-id="7b8a0-265">Application certificates</span></span>](#indicators-for-application-certificates)

![지표 유형 다이어그램](images/false-positives-indicators.png)

#### <a name="indicators-for-files"></a><span data-ttu-id="7b8a0-267">파일에 대한 표시기</span><span class="sxs-lookup"><span data-stu-id="7b8a0-267">Indicators for files</span></span>

<span data-ttu-id="7b8a0-268">실행 파일과 같은 파일에 [대한 "허용"](/microsoft-365/security/defender-endpoint/indicator-file)표시기를 만들면 조직에서 사용하는 파일이 차단되지 않도록 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7b8a0-268">When you [create an "allow" indicator for a file, such as an executable](/microsoft-365/security/defender-endpoint/indicator-file), it helps prevent files that your organization is using from being blocked.</span></span> <span data-ttu-id="7b8a0-269">파일에는 PE(이식 가능한 실행 파일) 파일(예: 및 파일)이 `.exe` `.dll` 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="7b8a0-269">Files can include portable executable (PE) files, such as `.exe` and `.dll` files.</span></span>

<span data-ttu-id="7b8a0-270">파일에 대한 표시기를 만들기 전에 다음 요구 사항을 충족하는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="7b8a0-270">Before you create indicators for files, make sure the following requirements are met:</span></span>

- <span data-ttu-id="7b8a0-271">Microsoft Defender 바이러스 백신 클라우드 기반 보호를 사용하도록 구성됩니다(클라우드 기반 보호 [관리 참조).](/windows/security/threat-protection/microsoft-defender-antivirus/deploy-manage-report-microsoft-defender-antivirus)</span><span class="sxs-lookup"><span data-stu-id="7b8a0-271">Microsoft Defender Antivirus is configured with cloud-based protection enabled (see [Manage cloud-based protection](/windows/security/threat-protection/microsoft-defender-antivirus/deploy-manage-report-microsoft-defender-antivirus))</span></span>
- <span data-ttu-id="7b8a0-272">맬웨어 방지 클라이언트 버전은 4.18.1901.x 이상입니다.</span><span class="sxs-lookup"><span data-stu-id="7b8a0-272">Antimalware client version is 4.18.1901.x or later</span></span>
- <span data-ttu-id="7b8a0-273">디바이스에서 Windows 10 버전 1703 이상이 실행되고 있습니다. Windows Server 2016; 또는 Windows Server 2019</span><span class="sxs-lookup"><span data-stu-id="7b8a0-273">Devices are running Windows 10, version 1703 or later; Windows Server 2016; or Windows Server 2019</span></span>
- <span data-ttu-id="7b8a0-274">차단 [또는 허용 기능이 켜져 있습니다.](/microsoft-365/security/defender-endpoint/advanced-features)</span><span class="sxs-lookup"><span data-stu-id="7b8a0-274">The [Block or allow feature is turned on](/microsoft-365/security/defender-endpoint/advanced-features)</span></span>

#### <a name="indicators-for-ip-addresses-urls-or-domains"></a><span data-ttu-id="7b8a0-275">IP 주소, URL 또는 도메인에 대한 표시기</span><span class="sxs-lookup"><span data-stu-id="7b8a0-275">Indicators for IP addresses, URLs, or domains</span></span>

<span data-ttu-id="7b8a0-276">IP 주소, URL 또는 도메인에 [대한 "허용"](/microsoft-365/security/defender-endpoint/indicator-ip-domain)표시기를 만들면 조직에서 사용하는 사이트 또는 IP 주소가 차단되지 않도록 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7b8a0-276">When you [create an "allow" indicator for an IP address, URL, or domain](/microsoft-365/security/defender-endpoint/indicator-ip-domain), it helps prevent the sites or IP addresses your organization uses from being blocked.</span></span>

<span data-ttu-id="7b8a0-277">IP 주소, URL 또는 도메인에 대한 표시기를 만들기 전에 다음 요구 사항을 충족하는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="7b8a0-277">Before you create indicators for IP addresses, URLs, or domains, make sure the following requirements are met:</span></span>

- <span data-ttu-id="7b8a0-278">끝점용 Defender의 네트워크 보호는 차단 모드에서 사용하도록 설정됩니다(네트워크 [보호 사용 참조).](/microsoft-365/security/defender-endpoint/enable-network-protection)</span><span class="sxs-lookup"><span data-stu-id="7b8a0-278">Network protection in Defender for Endpoint is enabled in block mode (see [Enable network protection](/microsoft-365/security/defender-endpoint/enable-network-protection))</span></span>
- <span data-ttu-id="7b8a0-279">맬웨어 방지 클라이언트 버전은 4.18.1906.x 이상입니다.</span><span class="sxs-lookup"><span data-stu-id="7b8a0-279">Antimalware client version is 4.18.1906.x or later</span></span>
- <span data-ttu-id="7b8a0-280">디바이스가 Windows 10 버전 1709 이상이 실행되고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7b8a0-280">Devices are running Windows 10, version 1709, or later</span></span>

<span data-ttu-id="7b8a0-281">사용자 지정 네트워크 표시기는 의 에서 [Microsoft 365 Defender.](microsoft-defender-security-center.md)</span><span class="sxs-lookup"><span data-stu-id="7b8a0-281">Custom network indicators are turned on in the [Microsoft 365 Defender](microsoft-defender-security-center.md).</span></span> <span data-ttu-id="7b8a0-282">자세한 내용은 고급 기능을 [참조합니다.](/microsoft-365/security/defender-endpoint/advanced-features)</span><span class="sxs-lookup"><span data-stu-id="7b8a0-282">To learn more, see [Advanced features](/microsoft-365/security/defender-endpoint/advanced-features).</span></span>

#### <a name="indicators-for-application-certificates"></a><span data-ttu-id="7b8a0-283">응용 프로그램 인증서 표시기</span><span class="sxs-lookup"><span data-stu-id="7b8a0-283">Indicators for application certificates</span></span>

<span data-ttu-id="7b8a0-284">응용 프로그램 [인증서에 대한 "허용"](/microsoft-365/security/defender-endpoint/indicator-certificates)표시기를 만들면 조직에서 사용하는 응용 프로그램(예: 내부 개발 응용 프로그램)이 차단되지 않도록 방지할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7b8a0-284">When you [create an "allow" indicator for an application certificate](/microsoft-365/security/defender-endpoint/indicator-certificates), it helps prevent applications, such as internally developed applications, that your organization uses from being blocked.</span></span> <span data-ttu-id="7b8a0-285">`.CER` 또는 `.PEM` 파일 확장명을 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="7b8a0-285">`.CER` or `.PEM` file extensions are supported.</span></span>

<span data-ttu-id="7b8a0-286">응용 프로그램 인증서에 대한 표시기를 만들기 전에 다음 요구 사항을 충족하는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="7b8a0-286">Before you create indicators for application certificates, make sure the following requirements are met:</span></span>

- <span data-ttu-id="7b8a0-287">Microsoft Defender 바이러스 백신 클라우드 기반 보호를 사용하도록 구성됩니다(클라우드 기반 보호 [관리 참조).](deploy-manage-report-microsoft-defender-antivirus.md)</span><span class="sxs-lookup"><span data-stu-id="7b8a0-287">Microsoft Defender Antivirus is configured with cloud-based protection enabled (see [Manage cloud-based protection](deploy-manage-report-microsoft-defender-antivirus.md))</span></span>
- <span data-ttu-id="7b8a0-288">맬웨어 방지 클라이언트 버전은 4.18.1901.x 이상입니다.</span><span class="sxs-lookup"><span data-stu-id="7b8a0-288">Antimalware client version is 4.18.1901.x or later</span></span>
- <span data-ttu-id="7b8a0-289">디바이스에서 Windows 10 버전 1703 이상이 실행되고 있습니다. Windows Server 2016; 또는 Windows Server 2019</span><span class="sxs-lookup"><span data-stu-id="7b8a0-289">Devices are running Windows 10, version 1703 or later; Windows Server 2016; or Windows Server 2019</span></span>
- <span data-ttu-id="7b8a0-290">바이러스 및 위협 방지 정의가 최신입니다.</span><span class="sxs-lookup"><span data-stu-id="7b8a0-290">Virus and threat protection definitions are up to date</span></span>

> [!TIP]
> <span data-ttu-id="7b8a0-291">지표를 만들 때 하나씩 정의하거나 한 번씩 여러 항목을 가져올 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7b8a0-291">When you create indicators, you can define them one by one, or import multiple items at once.</span></span> <span data-ttu-id="7b8a0-292">단일 테넌트에 대한 표시기는 15,000개로 제한됩니다.</span><span class="sxs-lookup"><span data-stu-id="7b8a0-292">Keep in mind there's a limit of 15,000 indicators for a single tenant.</span></span> <span data-ttu-id="7b8a0-293">또한 파일 해시 정보와 같은 특정 세부 정보를 먼저 수집해야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7b8a0-293">And, you might need to gather certain details first, such as file hash information.</span></span> <span data-ttu-id="7b8a0-294">표시기를 만들기 전에 선행 준비 상태를 [검토해야 합니다.](manage-indicators.md)</span><span class="sxs-lookup"><span data-stu-id="7b8a0-294">Make sure to review the prerequisites before you [create indicators](manage-indicators.md).</span></span>

## <a name="part-4-submit-a-file-for-analysis"></a><span data-ttu-id="7b8a0-295">4부: 분석을 위해 파일 제출</span><span class="sxs-lookup"><span data-stu-id="7b8a0-295">Part 4: Submit a file for analysis</span></span>

<span data-ttu-id="7b8a0-296">분석을 위해 파일 및 파일 없는 검색과 같은 엔터티를 Microsoft에 제출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7b8a0-296">You can submit entities, such as files and fileless detections, to Microsoft for analysis.</span></span> <span data-ttu-id="7b8a0-297">Microsoft 보안 연구원은 모든 제출을 분석하고 해당 결과를 통해 Microsoft Defender에 Endpoint 위협 방지 기능을 알릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7b8a0-297">Microsoft security researchers analyze all submissions, and their results help inform Microsoft Defender for Endpoint threat protection capabilities.</span></span> <span data-ttu-id="7b8a0-298">제출 사이트에서 로그인하면 제출을 추적할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7b8a0-298">When you sign in at the submission site, you can track your submissions.</span></span>

### <a name="submit-a-file-for-analysis"></a><span data-ttu-id="7b8a0-299">분석을 위해 파일 제출</span><span class="sxs-lookup"><span data-stu-id="7b8a0-299">Submit a file for analysis</span></span>

<span data-ttu-id="7b8a0-300">악성으로 잘못 감지되거나 누락된 파일이 있는 경우 다음 단계에 따라 분석을 위해 파일을 제출합니다.</span><span class="sxs-lookup"><span data-stu-id="7b8a0-300">If you have a file that was either wrongly detected as malicious or was missed, follow these steps to submit the file for analysis.</span></span>

1. <span data-ttu-id="7b8a0-301">분석을 위해 파일 [제출에 대한 지침을 검토합니다.](/windows/security/threat-protection/intelligence/submission-guide)</span><span class="sxs-lookup"><span data-stu-id="7b8a0-301">Review the guidelines here: [Submit files for analysis](/windows/security/threat-protection/intelligence/submission-guide).</span></span>

2. <span data-ttu-id="7b8a0-302">Microsoft 보안 인텔리전스 제출 사이트( )를 방문하고 <https://www.microsoft.com/wdsi/filesubmission> 파일을 제출합니다.</span><span class="sxs-lookup"><span data-stu-id="7b8a0-302">Visit the Microsoft Security Intelligence submission site (<https://www.microsoft.com/wdsi/filesubmission>), and submit your file(s).</span></span>

### <a name="submit-a-fileless-detection-for-analysis"></a><span data-ttu-id="7b8a0-303">분석을 위해 파일 없는 검색 제출</span><span class="sxs-lookup"><span data-stu-id="7b8a0-303">Submit a fileless detection for analysis</span></span>

<span data-ttu-id="7b8a0-304">동작에 따라 맬웨어로 검색된 파일도 없는 경우 분석을 위해 파일을 `Mpsupport.cab` 제출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7b8a0-304">If something was detected as malware based on behavior, and you don't have a file, you can submit your `Mpsupport.cab` file for analysis.</span></span> <span data-ttu-id="7b8a0-305">Microsoft 맬웨어 보호.cab유틸리티(Command-Line 유틸리티) 도구를 사용하여 MPCmdRun.exe 파일을 Windows 10. </span><span class="sxs-lookup"><span data-stu-id="7b8a0-305">You can get the *.cab* file by using the Microsoft Malware Protection Command-Line Utility (MPCmdRun.exe) tool on Windows 10.</span></span>

1. <span data-ttu-id="7b8a0-306">로 ` C:\ProgramData\Microsoft\Windows Defender\Platform\<version>` 이동한 다음 관리자 `MpCmdRun.exe` 권한으로 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="7b8a0-306">Go to ` C:\ProgramData\Microsoft\Windows Defender\Platform\<version>`, and then run `MpCmdRun.exe` as an administrator.</span></span>

2. <span data-ttu-id="7b8a0-307">를 `mpcmdrun.exe -GetFiles` 입력한 다음 **Enter를 누르고 를 입력합니다.**</span><span class="sxs-lookup"><span data-stu-id="7b8a0-307">Type `mpcmdrun.exe -GetFiles`, and then press **Enter**.</span></span>

   <span data-ttu-id="7b8a0-308">다양한 .cab 로그가 포함된 파일 생성</span><span class="sxs-lookup"><span data-stu-id="7b8a0-308">A .cab file is generated that contains various diagnostic logs.</span></span> <span data-ttu-id="7b8a0-309">파일의 위치는 명령 프롬프트 출력에 지정됩니다.</span><span class="sxs-lookup"><span data-stu-id="7b8a0-309">The location of the file is specified in the output of the command prompt.</span></span> <span data-ttu-id="7b8a0-310">기본적으로 위치는 `C:\ProgramData\Microsoft\Microsoft Defender\Support\MpSupportFiles.cab` 입니다.</span><span class="sxs-lookup"><span data-stu-id="7b8a0-310">By default, the location is `C:\ProgramData\Microsoft\Microsoft Defender\Support\MpSupportFiles.cab`.</span></span>

3. <span data-ttu-id="7b8a0-311">분석을 위해 파일 [제출에 대한 지침을 검토합니다.](/windows/security/threat-protection/intelligence/submission-guide)</span><span class="sxs-lookup"><span data-stu-id="7b8a0-311">Review the guidelines here: [Submit files for analysis](/windows/security/threat-protection/intelligence/submission-guide).</span></span>

4. <span data-ttu-id="7b8a0-312">Microsoft 보안 인텔리전스 제출 사이트( <https://www.microsoft.com/wdsi/filesubmission> )를 방문하고 .cab 제출합니다.</span><span class="sxs-lookup"><span data-stu-id="7b8a0-312">Visit the Microsoft Security Intelligence submission site (<https://www.microsoft.com/wdsi/filesubmission>), and submit your .cab files.</span></span>

### <a name="what-happens-after-a-file-is-submitted"></a><span data-ttu-id="7b8a0-313">파일이 제출된 후 어떻게 하나요?</span><span class="sxs-lookup"><span data-stu-id="7b8a0-313">What happens after a file is submitted?</span></span>

<span data-ttu-id="7b8a0-314">제출은 분석가가 사례 처리를 시작하기 전에 최신 판정을 제공하기 위해 시스템에서 즉시 검사됩니다.</span><span class="sxs-lookup"><span data-stu-id="7b8a0-314">Your submission is immediately scanned by our systems to give you the latest determination even before an analyst starts handling your case.</span></span> <span data-ttu-id="7b8a0-315">분석가가 파일을 이미 제출하고 처리한 것일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7b8a0-315">It's possible that a file might have already been submitted and processed by an analyst.</span></span> <span data-ttu-id="7b8a0-316">이러한 경우 신속하게 결정됩니다.</span><span class="sxs-lookup"><span data-stu-id="7b8a0-316">In those cases, a determination is made quickly.</span></span>

<span data-ttu-id="7b8a0-317">아직 처리되지 않은 제출의 경우 다음과 같이 분석 우선 순위가 지정됩니다.</span><span class="sxs-lookup"><span data-stu-id="7b8a0-317">For submissions that were not already processed, they are prioritized for analysis as follows:</span></span>

- <span data-ttu-id="7b8a0-318">많은 컴퓨터에 영향을 줄 가능성이 있는 보급된 파일에는 더 높은 우선 순위가 부여됩니다.</span><span class="sxs-lookup"><span data-stu-id="7b8a0-318">Prevalent files with the potential to impact large numbers of computers are given a higher priority.</span></span>
- <span data-ttu-id="7b8a0-319">인증된 고객, 특히 유효한 [SAID(Software Assurance ID)가](https://www.microsoft.com/licensing/licensing-programs/software-assurance-default.aspx)있는 엔터프라이즈 고객에게는 높은 우선 순위가 부여됩니다.</span><span class="sxs-lookup"><span data-stu-id="7b8a0-319">Authenticated customers, especially enterprise customers with valid [Software Assurance IDs (SAIDs)](https://www.microsoft.com/licensing/licensing-programs/software-assurance-default.aspx), are given a higher priority.</span></span>
- <span data-ttu-id="7b8a0-320">SAID 소유자가 우선 순위가 높은 것으로 플래그를 지정한 제출은 즉시 주의를 기울입니다.</span><span class="sxs-lookup"><span data-stu-id="7b8a0-320">Submissions flagged as high priority by SAID holders are given immediate attention.</span></span>

<span data-ttu-id="7b8a0-321">제출에 대한 업데이트를 확인하거나 제출 사이트 [에서 Microsoft 보안 인텔리전스 로그인합니다.](https://www.microsoft.com/wdsi/filesubmission)</span><span class="sxs-lookup"><span data-stu-id="7b8a0-321">To check for updates regarding your submission, sign in at the [Microsoft Security Intelligence submission site](https://www.microsoft.com/wdsi/filesubmission).</span></span>

> [!TIP]
> <span data-ttu-id="7b8a0-322">자세한 내용은 분석을 위해 [파일 제출을 참조합니다.](/windows/security/threat-protection/intelligence/submission-guide#how-does-microsoft-prioritize-submissions)</span><span class="sxs-lookup"><span data-stu-id="7b8a0-322">To learn more, see [Submit files for analysis](/windows/security/threat-protection/intelligence/submission-guide#how-does-microsoft-prioritize-submissions).</span></span>

## <a name="part-5-review-and-adjust-your-threat-protection-settings"></a><span data-ttu-id="7b8a0-323">5부: 위협 방지 설정 검토 및 조정</span><span class="sxs-lookup"><span data-stu-id="7b8a0-323">Part 5: Review and adjust your threat protection settings</span></span>

<span data-ttu-id="7b8a0-324">끝점용 Microsoft Defender는 다양한 기능 및 기능에 대한 설정을 미세 조정하는 기능을 포함하여 다양한 옵션을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="7b8a0-324">Microsoft Defender for Endpoint offers a wide variety of options, including the ability to fine-tune settings for various features and capabilities.</span></span> <span data-ttu-id="7b8a0-325">많은 가의 긍정이 있는 경우 조직의 위협 방지 설정을 검토해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7b8a0-325">If you're getting numerous false positives, make sure to review your organization's threat protection settings.</span></span> <span data-ttu-id="7b8a0-326">다음을 조정해야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7b8a0-326">You might need to make some adjustments to:</span></span>

- [<span data-ttu-id="7b8a0-327">클라우드 제공 보호</span><span class="sxs-lookup"><span data-stu-id="7b8a0-327">Cloud-delivered protection</span></span>](#cloud-delivered-protection)
- [<span data-ttu-id="7b8a0-328">잠재적으로 원치 않는 응용 프로그램에 대한 수정</span><span class="sxs-lookup"><span data-stu-id="7b8a0-328">Remediation for potentially unwanted applications</span></span>](#remediation-for-potentially-unwanted-applications)
- [<span data-ttu-id="7b8a0-329">자동화된 조사 및 수정</span><span class="sxs-lookup"><span data-stu-id="7b8a0-329">Automated investigation and remediation</span></span>](#automated-investigation-and-remediation)

### <a name="cloud-delivered-protection"></a><span data-ttu-id="7b8a0-330">클라우드 제공 보호</span><span class="sxs-lookup"><span data-stu-id="7b8a0-330">Cloud-delivered protection</span></span>

<span data-ttu-id="7b8a0-331">클라우드 제공 보호 수준에 대한 Microsoft Defender 바이러스 백신.</span><span class="sxs-lookup"><span data-stu-id="7b8a0-331">Check your cloud-delivered protection level for Microsoft Defender Antivirus.</span></span> <span data-ttu-id="7b8a0-332">기본적으로 클라우드 제공 보호는 구성되지 않습니다.로 설정되어 있습니다. 이는 대부분의 조직에 대한 일반적인 보호 수준에 해당합니다. </span><span class="sxs-lookup"><span data-stu-id="7b8a0-332">By default, cloud-delivered protection is set to **Not configured**, which corresponds to a normal level of protection for most organizations.</span></span> <span data-ttu-id="7b8a0-333">클라우드 제공 보호가 **높음,** **높음 +** 또는 허용 오차가 **0으로** 설정된 경우 가음성 수가 더 높을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7b8a0-333">If your cloud-delivered protection is set to **High**, **High +**, or **Zero tolerance**, you might experience a higher number of false positives.</span></span>

> [!TIP]
> <span data-ttu-id="7b8a0-334">클라우드 제공 보호 구성에 대한 자세한 내용은 클라우드 제공 보호 수준 [지정을 참조합니다.](/windows/security/threat-protection/microsoft-defender-antivirus/specify-cloud-protection-level-microsoft-defender-antivirus)</span><span class="sxs-lookup"><span data-stu-id="7b8a0-334">To learn more about configuring your cloud-delivered protection, see [Specify the cloud-delivered protection level](/windows/security/threat-protection/microsoft-defender-antivirus/specify-cloud-protection-level-microsoft-defender-antivirus).</span></span>

<span data-ttu-id="7b8a0-335">클라우드 제공 보호 [Microsoft Endpoint Manager](/mem/endpoint-manager-overview) 편집하거나 설정하는 것이 좋습니다. 그러나 그룹 정책과 같은 다른 [](/azure/active-directory-domain-services/manage-group-policy) 방법을 사용할 수 [있습니다(끝점용 Microsoft Defender 관리 참조).](manage-atp-post-migration.md)</span><span class="sxs-lookup"><span data-stu-id="7b8a0-335">We recommend using [Microsoft Endpoint Manager](/mem/endpoint-manager-overview) to edit or set your cloud-delivered protection settings; however, you can use other methods, such as [Group Policy](/azure/active-directory-domain-services/manage-group-policy) (see [Manage Microsoft Defender for Endpoint](manage-atp-post-migration.md)).</span></span>

#### <a name="use-microsoft-endpoint-manager-to-review-and-edit-cloud-delivered-protection-settings-for-existing-policies"></a><span data-ttu-id="7b8a0-336">이 Microsoft Endpoint Manager 사용하여 클라우드 제공 보호 설정 검토 및 편집(기존 정책의 경우)</span><span class="sxs-lookup"><span data-stu-id="7b8a0-336">Use Microsoft Endpoint Manager to review and edit cloud-delivered protection settings (for existing policies)</span></span>

1. <span data-ttu-id="7b8a0-337">Microsoft Endpoint Manager 관리 센터()로 이동하여 <https://endpoint.microsoft.com> 로그인합니다.</span><span class="sxs-lookup"><span data-stu-id="7b8a0-337">Go to the Microsoft Endpoint Manager admin center (<https://endpoint.microsoft.com>) and sign in.</span></span>

2. <span data-ttu-id="7b8a0-338">끝점 **보안 바이러스 백신을**  >  **선택한** 다음 기존 정책을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="7b8a0-338">Choose **Endpoint security** > **Antivirus** and then select an existing policy.</span></span> <span data-ttu-id="7b8a0-339">기존 정책이 없는 경우 또는 새 정책을 만들 수 있는 경우 다음 절차로 [건너뛰어도 됩니다.](#use-microsoft-endpoint-manager-to-set-cloud-delivered-protection-settings-for-a-new-policy)</span><span class="sxs-lookup"><span data-stu-id="7b8a0-339">(If you don't have an existing policy, or you want to create a new policy, skip to [the next procedure](#use-microsoft-endpoint-manager-to-set-cloud-delivered-protection-settings-for-a-new-policy)).</span></span>

3. <span data-ttu-id="7b8a0-340">**관리에서** 속성을 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="7b8a0-340">Under **Manage**, select **Properties**.</span></span> <span data-ttu-id="7b8a0-341">그런 다음 구성 설정 **옆에 있는** 편집 을 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="7b8a0-341">Then, next to **Configuration settings**, choose **Edit**.</span></span>

4. <span data-ttu-id="7b8a0-342">클라우드 **보호를 확장하고** 클라우드 제공 보호 수준 행에서 현재 설정을 **검토합니다.**</span><span class="sxs-lookup"><span data-stu-id="7b8a0-342">Expand **Cloud protection**, and review your current setting in the **Cloud-delivered protection level** row.</span></span> <span data-ttu-id="7b8a0-343">클라우드 제공 보호를 구성되지 않은으로 설정하는 것이 좋습니다. 이 기능은 강력한 보호 기능을 제공하는 동시에 가긍성의 확률을 줄입니다. </span><span class="sxs-lookup"><span data-stu-id="7b8a0-343">We recommend setting cloud-delivered protection to **Not configured**, which provides strong protection while reducing the chances of getting false positives.</span></span>

5. <span data-ttu-id="7b8a0-344">검토 **+ 저장 을** 선택한 다음 저장 **을 선택 합니다.**</span><span class="sxs-lookup"><span data-stu-id="7b8a0-344">Choose **Review + save**, and then **Save**.</span></span>

#### <a name="use-microsoft-endpoint-manager-to-set-cloud-delivered-protection-settings-for-a-new-policy"></a><span data-ttu-id="7b8a0-345">새 Microsoft Endpoint Manager 사용하여 클라우드 제공 보호 설정 설정</span><span class="sxs-lookup"><span data-stu-id="7b8a0-345">Use Microsoft Endpoint Manager to set cloud-delivered protection settings (for a new policy)</span></span>

1. <span data-ttu-id="7b8a0-346">Microsoft Endpoint Manager 관리 센터()로 이동하여 <https://endpoint.microsoft.com> 로그인합니다.</span><span class="sxs-lookup"><span data-stu-id="7b8a0-346">Go to the Microsoft Endpoint Manager admin center (<https://endpoint.microsoft.com>) and sign in.</span></span>

2. <span data-ttu-id="7b8a0-347">끝점 **보안 바이러스**  >  **백신**  >  **+ 정책 만들기 를 선택 합니다.**</span><span class="sxs-lookup"><span data-stu-id="7b8a0-347">Choose **Endpoint security** > **Antivirus** > **+ Create policy**.</span></span>

3. <span data-ttu-id="7b8a0-348">플랫폼의 경우 옵션을 선택하고 프로필에서 바이러스  백신 또는 Microsoft Defender 바이러스 백신 선택합니다(특정 옵션은 플랫폼에 대해 선택한 대상에 따라 **다를 수** 있습니다.    그런 다음 만들기 **를 선택.**</span><span class="sxs-lookup"><span data-stu-id="7b8a0-348">For **Platform**, select an option, and then for **Profile**, select **Antivirus** or **Microsoft Defender Antivirus** (the specific option depends on what you selected for **Platform**.) Then choose **Create**.</span></span>

4. <span data-ttu-id="7b8a0-349">기본 **탭에서** 정책의 이름과 설명을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="7b8a0-349">On the **Basics** tab, specify a name and description for the policy.</span></span> <span data-ttu-id="7b8a0-350">그런 후 **다음** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="7b8a0-350">Then choose **Next**.</span></span>

5. <span data-ttu-id="7b8a0-351">구성 **설정 탭에서** 클라우드 **보호를** 확장하고 다음 설정을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="7b8a0-351">On the **Configuration settings** tab, expand **Cloud protection**, and specify the following settings:</span></span>
   - <span data-ttu-id="7b8a0-352">클라우드 **제공 보호 켜기 를** **예로 설정**</span><span class="sxs-lookup"><span data-stu-id="7b8a0-352">Set **Turn on cloud-delivered protection** to **Yes**.</span></span>
   - <span data-ttu-id="7b8a0-353">**클라우드 제공 보호 켜기** 를 **구성되지 않음** 으로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="7b8a0-353">Set **Cloud-delivered protection level** to **Not configured**.</span></span> <span data-ttu-id="7b8a0-354">(이 수준은 기본적으로 강력한 수준의 보호를 제공하면서 가음성의 확률을 줄입니다.)</span><span class="sxs-lookup"><span data-stu-id="7b8a0-354">(This level provides a strong level of protection by default while reducing the chances of getting false positives.)</span></span>

6. <span data-ttu-id="7b8a0-355">조직에서  범위 태그를 사용하는 경우 범위 태그 탭에서 정책의 범위 태그를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="7b8a0-355">On the **Scope tags** tab, if you are using scope tags in your organization, specify scope tags for the policy.</span></span> <span data-ttu-id="7b8a0-356">범위 [태그를 참조합니다.](/mem/intune/fundamentals/scope-tags)</span><span class="sxs-lookup"><span data-stu-id="7b8a0-356">(See [Scope tags](/mem/intune/fundamentals/scope-tags).)</span></span>

7. <span data-ttu-id="7b8a0-357">할당 **탭에서** 정책을 적용할 사용자 및 그룹을 지정하고 다음 을 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="7b8a0-357">On the **Assignments** tab, specify the users and groups to whom your policy should be applied, and then choose **Next**.</span></span> <span data-ttu-id="7b8a0-358">할당에 대한 도움이 필요한 경우 에서 사용자 및 장치 프로필 [할당을 Microsoft Intune.](/mem/intune/configuration/device-profile-assign)</span><span class="sxs-lookup"><span data-stu-id="7b8a0-358">(If you need help with assignments, see [Assign user and device profiles in Microsoft Intune](/mem/intune/configuration/device-profile-assign).)</span></span>

8. <span data-ttu-id="7b8a0-359">검토 **+ 만들기 탭에서** 설정을 검토한 다음 만들기 를 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="7b8a0-359">On the **Review + create** tab, review the settings, and then choose **Create**.</span></span>

### <a name="remediation-for-potentially-unwanted-applications"></a><span data-ttu-id="7b8a0-360">잠재적으로 원치 않는 응용 프로그램에 대한 수정</span><span class="sxs-lookup"><span data-stu-id="7b8a0-360">Remediation for potentially unwanted applications</span></span>

<span data-ttu-id="7b8a0-361">PUA(사용자 없이도 사용 가능한 응용 프로그램)는 장치가 느리게 실행되거나 예기치 않은 광고를 표시하거나 예기치 않게 또는 원치 않는 다른 소프트웨어를 설치할 수 있는 소프트웨어 범주입니다.</span><span class="sxs-lookup"><span data-stu-id="7b8a0-361">Potentially unwanted applications (PUA) are a category of software that can cause devices to run slowly, display unexpected ads, or install other software that might be unexpected or unwanted.</span></span> <span data-ttu-id="7b8a0-362">PUA의 예로는 광고 소프트웨어, 번들링 소프트웨어 및 보안 제품과 다르게 행동하는 피하기 소프트웨어가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7b8a0-362">Examples of PUA include advertising software, bundling software, and evasion software that behaves differently with security products.</span></span> <span data-ttu-id="7b8a0-363">PUA는 맬웨어로 간주되지는 않습니다. 그러나 일부 소프트웨어의 일부는 동작 및 신뢰도에 따라 PUA입니다.</span><span class="sxs-lookup"><span data-stu-id="7b8a0-363">Although PUA is not considered malware, some kinds of software are PUA based on their behavior and reputation.</span></span>

> [!TIP]
> <span data-ttu-id="7b8a0-364">PUA에 대한 자세한 내용은 잠재적으로 원치 않는 응용 프로그램 검색 및 [차단을 참조합니다.](/windows/security/threat-protection/microsoft-defender-antivirus/detect-block-potentially-unwanted-apps-microsoft-defender-antivirus)</span><span class="sxs-lookup"><span data-stu-id="7b8a0-364">To learn more about PUA, see [Detect and block potentially unwanted applications](/windows/security/threat-protection/microsoft-defender-antivirus/detect-block-potentially-unwanted-apps-microsoft-defender-antivirus).</span></span>

<span data-ttu-id="7b8a0-365">조직에서 사용하는 앱에 따라 PUA 보호 설정의 결과로 가극적 긍정을 가지게 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7b8a0-365">Depending on the apps your organization is using, you might be getting false positives as a result of your PUA protection settings.</span></span> <span data-ttu-id="7b8a0-366">필요한 경우 한 동안 감사 모드에서 PUA 보호를 실행하거나 조직의 디바이스 하위 집합에 PUA 보호를 적용하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="7b8a0-366">If necessary, consider running PUA protection in audit mode for a while, or apply PUA protection to a subset of devices in your organization.</span></span> <span data-ttu-id="7b8a0-367">PUA 보호는 MICROSOFT EDGE 및 사용자에 대해 구성할 수 Microsoft Defender 바이러스 백신.</span><span class="sxs-lookup"><span data-stu-id="7b8a0-367">PUA protection can be configured for the Microsoft Edge browser and for Microsoft Defender Antivirus.</span></span>

<span data-ttu-id="7b8a0-368">PUA [보호](/mem/endpoint-manager-overview) Microsoft Endpoint Manager 편집하거나 설정하는 것이 좋습니다. 그러나 그룹 정책과 같은 다른 [](/azure/active-directory-domain-services/manage-group-policy) 방법을 사용할 수 [있습니다(끝점용 Microsoft Defender 관리 참조).](manage-atp-post-migration.md)</span><span class="sxs-lookup"><span data-stu-id="7b8a0-368">We recommend using [Microsoft Endpoint Manager](/mem/endpoint-manager-overview) to edit or set PUA protection settings; however, you can use other methods, such as [Group Policy](/azure/active-directory-domain-services/manage-group-policy) (see [Manage Microsoft Defender for Endpoint](manage-atp-post-migration.md)).</span></span>

#### <a name="use-microsoft-endpoint-manager-to-edit-pua-protection-for-existing-configuration-profiles"></a><span data-ttu-id="7b8a0-369">추가 Microsoft Endpoint Manager 사용하여 PUA 보호 편집(기존 구성 프로필의 경우)</span><span class="sxs-lookup"><span data-stu-id="7b8a0-369">Use Microsoft Endpoint Manager to edit PUA protection (for existing configuration profiles)</span></span>

1. <span data-ttu-id="7b8a0-370">Microsoft Endpoint Manager 관리 센터()로 이동하여 <https://endpoint.microsoft.com> 로그인합니다.</span><span class="sxs-lookup"><span data-stu-id="7b8a0-370">Go to the Microsoft Endpoint Manager admin center (<https://endpoint.microsoft.com>) and sign in.</span></span>

2. <span data-ttu-id="7b8a0-371">장치   >  **구성 프로필을 선택한** 다음 기존 정책을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="7b8a0-371">Choose **Devices** > **Configuration profiles**, and then select an existing policy.</span></span> <span data-ttu-id="7b8a0-372">기존 정책이 없는 경우 또는 새 정책을 만들 수 있는 경우 다음 절차로 [건너뛰어도 됩니다.](#use-microsoft-endpoint-manager-to-set-pua-protection-for-a-new-configuration-profile)</span><span class="sxs-lookup"><span data-stu-id="7b8a0-372">(If you don't have an existing policy, or you want to create a new policy, skip to [the next procedure](#use-microsoft-endpoint-manager-to-set-pua-protection-for-a-new-configuration-profile).)</span></span>

3. <span data-ttu-id="7b8a0-373">관리에서 **속성 을** 선택한 다음 구성 설정 옆에 **있는** 편집 을 **선택합니다.** </span><span class="sxs-lookup"><span data-stu-id="7b8a0-373">Under **Manage**, choose **Properties**, and then, next to **Configuration settings**, choose **Edit**.</span></span>

4. <span data-ttu-id="7b8a0-374">구성 **설정 탭에서** 아래로 스크롤하여 **을** Microsoft Defender 바이러스 백신.</span><span class="sxs-lookup"><span data-stu-id="7b8a0-374">On the **Configuration settings** tab, scroll down and expand **Microsoft Defender Antivirus**.</span></span>

5. <span data-ttu-id="7b8a0-375">잠재적으로 **원치 않는 응용 프로그램 검색을** 감사로 **설정**</span><span class="sxs-lookup"><span data-stu-id="7b8a0-375">Set **Detect potentially unwanted applications** to **Audit**.</span></span> <span data-ttu-id="7b8a0-376">(이 기능을 해제할 수 있지만 감사 모드를 사용하면 검색을 볼 수 있습니다.)</span><span class="sxs-lookup"><span data-stu-id="7b8a0-376">(You can turn it off, but by using audit mode, you will be able to see detections.)</span></span>

6. <span data-ttu-id="7b8a0-377">검토 **+ 저장 을** 선택한 다음 저장 을 **선택 합니다.**</span><span class="sxs-lookup"><span data-stu-id="7b8a0-377">Choose **Review + save**, and then choose **Save**.</span></span>

#### <a name="use-microsoft-endpoint-manager-to-set-pua-protection-for-a-new-configuration-profile"></a><span data-ttu-id="7b8a0-378">추가 Microsoft Endpoint Manager 사용하여 PUA 보호 설정(새 구성 프로필용)</span><span class="sxs-lookup"><span data-stu-id="7b8a0-378">Use Microsoft Endpoint Manager to set PUA protection (for a new configuration profile)</span></span>

1. <span data-ttu-id="7b8a0-379">Microsoft Endpoint Manager 관리 센터()로 이동하여 <https://endpoint.microsoft.com> 로그인합니다.</span><span class="sxs-lookup"><span data-stu-id="7b8a0-379">Go to the Microsoft Endpoint Manager admin center (<https://endpoint.microsoft.com>) and sign in.</span></span>

2. <span data-ttu-id="7b8a0-380">장치 **구성**  >  **프로필**  >  **+ 프로필 만들기 를 선택하세요.**</span><span class="sxs-lookup"><span data-stu-id="7b8a0-380">Choose **Devices** > **Configuration profiles** > **+ Create profile**.</span></span>

3. <span data-ttu-id="7b8a0-381">플랫폼의 경우 Windows 10 **이상을** 선택하고 **프로필에** 대해 장치 제한 **을 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="7b8a0-381">For the **Platform**, choose **Windows 10 and later**, and for **Profile**, select **Device restrictions**.</span></span>

4. <span data-ttu-id="7b8a0-382">기본 **탭에서** 정책의 이름과 설명을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="7b8a0-382">On the **Basics** tab, specify a name and description for your policy.</span></span> <span data-ttu-id="7b8a0-383">그런 후 **다음** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="7b8a0-383">Then choose **Next**.</span></span>

5. <span data-ttu-id="7b8a0-384">구성 **설정 탭에서** 아래로 스크롤하여 **을** Microsoft Defender 바이러스 백신.</span><span class="sxs-lookup"><span data-stu-id="7b8a0-384">On the **Configuration settings** tab, scroll down and expand **Microsoft Defender Antivirus**.</span></span>

6. <span data-ttu-id="7b8a0-385">잠재적으로 **원치 않는 응용 프로그램 검색을** **감사로** 설정하고 다음 을 **선택 합니다.**</span><span class="sxs-lookup"><span data-stu-id="7b8a0-385">Set **Detect potentially unwanted applications** to **Audit**, and then choose **Next**.</span></span> <span data-ttu-id="7b8a0-386">PUA 보호를 해제할 수 있지만 감사 모드를 사용하면 검색을 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7b8a0-386">(You can turn off PUA protection, but by using audit mode, you will be able to see detections.)</span></span>

7. <span data-ttu-id="7b8a0-387">할당 **탭에서** 정책을 적용할 사용자 및 그룹을 지정하고 다음 을 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="7b8a0-387">On the **Assignments** tab, specify the users and groups to whom your policy should be applied, and then choose **Next**.</span></span> <span data-ttu-id="7b8a0-388">할당에 대한 도움이 필요한 경우 에서 사용자 및 장치 프로필 [할당을 Microsoft Intune.](/mem/intune/configuration/device-profile-assign)</span><span class="sxs-lookup"><span data-stu-id="7b8a0-388">(If you need help with assignments, see [Assign user and device profiles in Microsoft Intune](/mem/intune/configuration/device-profile-assign).)</span></span>

8. <span data-ttu-id="7b8a0-389">적용 **가능성 규칙** 탭에서 정책을 포함하거나 제외할 OS 버전을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="7b8a0-389">On the **Applicability Rules** tab, specify the OS editions or versions to include or exclude from the policy.</span></span> <span data-ttu-id="7b8a0-390">예를 들어 특정 에디션 버전이 있는 모든 디바이스에 적용될 정책을 Windows 10.</span><span class="sxs-lookup"><span data-stu-id="7b8a0-390">For example, you can set the policy to be applied to all devices certain editions of Windows 10.</span></span> <span data-ttu-id="7b8a0-391">그런 후 **다음** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="7b8a0-391">Then choose **Next**.</span></span>

9. <span data-ttu-id="7b8a0-392">검토 **+ 만들기 탭에서** 설정을 검토한 다음 만들기를 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="7b8a0-392">On the **Review + create** tab, review your settings, and, and then choose **Create**.</span></span>

### <a name="automated-investigation-and-remediation"></a><span data-ttu-id="7b8a0-393">자동화된 조사 및 수정</span><span class="sxs-lookup"><span data-stu-id="7b8a0-393">Automated investigation and remediation</span></span>

<span data-ttu-id="7b8a0-394">[자동화된 조사](automated-investigations.md) 및 수정(AIR) 기능은 경고를 검사하고 위반을 해결하기 위해 즉각적인 조치를 취하도록 고안되었습니다.</span><span class="sxs-lookup"><span data-stu-id="7b8a0-394">[Automated investigation and remediation](automated-investigations.md) (AIR) capabilities are designed to examine alerts and take immediate action to resolve breaches.</span></span> <span data-ttu-id="7b8a0-395">경고가 트리거되고 자동화된 조사가 실행되면 조사된 각 증거 조각에 대한 판결이 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="7b8a0-395">As alerts are triggered, and an automated investigation runs, a verdict is generated for each piece of evidence investigated.</span></span> <span data-ttu-id="7b8a0-396">판정은 *악성,* *의심스러운* 또는 *위협이 없음일 수 있습니다.*</span><span class="sxs-lookup"><span data-stu-id="7b8a0-396">Verdicts can be *Malicious*, *Suspicious*, or *No threats found*.</span></span>

<span data-ttu-id="7b8a0-397">조직에 설정된 [](/microsoft-365/security/defender-endpoint/automation-levels) 자동화 수준 및 기타 보안 설정에 따라 악의적 또는 의심스러운 것으로  간주되는 아티팩트에 대해 수정 *작업이 수행됩니다.*</span><span class="sxs-lookup"><span data-stu-id="7b8a0-397">Depending on the [level of automation](/microsoft-365/security/defender-endpoint/automation-levels) set for your organization and other security settings, remediation actions are taken on artifacts that are considered to be *Malicious* or *Suspicious*.</span></span> <span data-ttu-id="7b8a0-398">경우에 따라 수정 작업이 자동으로 수행됩니다. 다른 경우에는 보안 운영 팀의 승인만 수행되거나 수동으로 수정 작업이 수행됩니다.</span><span class="sxs-lookup"><span data-stu-id="7b8a0-398">In some cases, remediation actions occur automatically; in other cases, remediation actions are taken manually or only upon approval by your security operations team.</span></span>

- <span data-ttu-id="7b8a0-399">[자동화 수준에 대해 자세히 알아보시다.](/microsoft-365/security/defender-endpoint/automation-levels) 그런 다음</span><span class="sxs-lookup"><span data-stu-id="7b8a0-399">[Learn more about automation levels](/microsoft-365/security/defender-endpoint/automation-levels); and then</span></span>
- <span data-ttu-id="7b8a0-400">[끝점용 Defender에서 AIR 기능을 구성합니다.](/microsoft-365/security/defender-endpoint/configure-automated-investigations-remediation)</span><span class="sxs-lookup"><span data-stu-id="7b8a0-400">[Configure AIR capabilities in Defender for Endpoint](/microsoft-365/security/defender-endpoint/configure-automated-investigations-remediation).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="7b8a0-401">자동화된 조사 및 *수정을 위해* 전체 자동화를 사용하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="7b8a0-401">We recommend using *Full automation* for automated investigation and remediation.</span></span> <span data-ttu-id="7b8a0-402">가극적이기 때문에 이러한 기능을 해제하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="7b8a0-402">Don't turn these capabilities off because of a false positive.</span></span> <span data-ttu-id="7b8a0-403">대신 ["허용"](#indicators-for-microsoft-defender-for-endpoint)표시기를 사용하여 예외를 정의하고 자동화된 조사 및 수정을 설정하여 적절한 조치를 자동으로 취하도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="7b8a0-403">Instead, use ["allow" indicators to define exceptions](#indicators-for-microsoft-defender-for-endpoint), and keep automated investigation and remediation set to take appropriate actions automatically.</span></span> <span data-ttu-id="7b8a0-404">이 [지침에 따라](automation-levels.md#levels-of-automation) 보안 운영 팀이 처리해야 하는 경고 수를 줄일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7b8a0-404">Following [this guidance](automation-levels.md#levels-of-automation) helps reduce the number of alerts your security operations team must handle.</span></span>

## <a name="still-need-help"></a><span data-ttu-id="7b8a0-405">아직 해결되지 않았습니까?</span><span class="sxs-lookup"><span data-stu-id="7b8a0-405">Still need help?</span></span>

<span data-ttu-id="7b8a0-406">이 문서의 모든 단계를 수행한 후 여전히 도움이 필요한 경우 기술 지원에 문의하세요.</span><span class="sxs-lookup"><span data-stu-id="7b8a0-406">If you have worked through all the steps in this article and still need help, contact technical support.</span></span>

1. <span data-ttu-id="7b8a0-407">다음으로 Microsoft 365 Defender <https://security.microsoft.com> ( ) 로 이동하고 로그인합니다.</span><span class="sxs-lookup"><span data-stu-id="7b8a0-407">Go to Microsoft 365 Defender (<https://security.microsoft.com>) and sign in.</span></span>

2. <span data-ttu-id="7b8a0-408">오른쪽 위 모서리에서 물음표(**?**)를 선택한 다음 Microsoft 지원 **을 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="7b8a0-408">In the upper right corner, select the question mark (**?**), and then select **Microsoft support**.</span></span>

3. <span data-ttu-id="7b8a0-409">지원 **도우미 창에서** 문제를 설명한 다음 메시지를 보내십시오.</span><span class="sxs-lookup"><span data-stu-id="7b8a0-409">In the **Support Assistant** window, describe your issue, and then send your message.</span></span> <span data-ttu-id="7b8a0-410">서비스 요청을 열 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7b8a0-410">From there, you can open a service request.</span></span>

## <a name="see-also"></a><span data-ttu-id="7b8a0-411">참고 항목</span><span class="sxs-lookup"><span data-stu-id="7b8a0-411">See also</span></span>

[<span data-ttu-id="7b8a0-412">끝점용 Microsoft Defender 관리</span><span class="sxs-lookup"><span data-stu-id="7b8a0-412">Manage Microsoft Defender for Endpoint</span></span>](manage-atp-post-migration.md)

[<span data-ttu-id="7b8a0-413">포털 Microsoft 365 Defender 개요</span><span class="sxs-lookup"><span data-stu-id="7b8a0-413">Overview of Microsoft 365 Defender portal</span></span>](/microsoft-365/security/defender-endpoint/use)
