---
title: 끝점 경고에 대한 Microsoft Defender 관리
description: 경고 상태를 변경하고, 경고를 숨기기 위한 제거 규칙을 만들고, 설명을 제출하고, 경고 관리 메뉴를 사용하여 개별 경고에 대한 변경 기록을 검토합니다.
keywords: 경고 관리, 관리, 경고, 상태, 신규, 진행 중, 해결, 경고 해결, 제거, 제거, 규칙, 컨텍스트, 기록, 설명, 변경
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: f03c2209b369e6fb9e001452c53073daeb5fe1c6
ms.sourcegitcommit: 6f2288e0c863496dfd0ee38de754bd43096ab3e1
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/24/2021
ms.locfileid: "51187004"
---
# <a name="manage-microsoft-defender-for-endpoint-alerts"></a><span data-ttu-id="25b6f-104">끝점 경고에 대한 Microsoft Defender 관리</span><span class="sxs-lookup"><span data-stu-id="25b6f-104">Manage Microsoft Defender for Endpoint alerts</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="25b6f-105">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="25b6f-105">**Applies to:**</span></span>
- [<span data-ttu-id="25b6f-106">엔드포인트용 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="25b6f-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="25b6f-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="25b6f-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)


> <span data-ttu-id="25b6f-108">Endpoint용 Defender를 경험하고 싶나요?</span><span class="sxs-lookup"><span data-stu-id="25b6f-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="25b6f-109">무료 평가판에 등록합니다.</span><span class="sxs-lookup"><span data-stu-id="25b6f-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-managealerts-abovefoldlink)

<span data-ttu-id="25b6f-110">Endpoint용 Defender는 경고를 통해 가능한 악성 이벤트, 특성 및 상황 정보를 알리고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="25b6f-110">Defender for Endpoint notifies you of possible malicious events, attributes, and contextual information through alerts.</span></span> <span data-ttu-id="25b6f-111">보안 작업 대시보드에는 새 경고에 대한 요약이 표시되고 경고 큐의 모든 경고에 액세스할 **수 있습니다.**</span><span class="sxs-lookup"><span data-stu-id="25b6f-111">A summary of new alerts is displayed in the **Security operations dashboard**, and you can access all alerts in the **Alerts queue**.</span></span>

<span data-ttu-id="25b6f-112">경고 큐 또는 개별 장치에 대한 장치 페이지의 경고  탭에서 경고를 선택하여 경고를 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="25b6f-112">You can manage alerts by selecting an alert in the **Alerts queue**, or the **Alerts** tab of the Device page for an individual device.</span></span>

<span data-ttu-id="25b6f-113">이러한 위치 중 하나에서 경고를 선택하면 경고 관리 **창이 표시됩니다.**</span><span class="sxs-lookup"><span data-stu-id="25b6f-113">Selecting an alert in either of those places brings up the **Alert management pane**.</span></span>

![경고 관리 창 및 경고 큐의 이미지](images/atp-alerts-selected.png)

## <a name="link-to-another-incident"></a><span data-ttu-id="25b6f-115">다른 인시던트에 연결</span><span class="sxs-lookup"><span data-stu-id="25b6f-115">Link to another incident</span></span>
<span data-ttu-id="25b6f-116">경고에서 새 인시던트 또는 기존 인시던트에 대한 링크를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="25b6f-116">You can create a new incident from the alert or link to an existing incident.</span></span> 

## <a name="assign-alerts"></a><span data-ttu-id="25b6f-117">경고 할당</span><span class="sxs-lookup"><span data-stu-id="25b6f-117">Assign alerts</span></span>
<span data-ttu-id="25b6f-118">알림이 아직 할당되지 않은 경우  사용자에게 할당을 선택하여 사용자에게 알림을 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="25b6f-118">If an alert is not yet assigned, you can select **Assign to me** to assign the alert to yourself.</span></span>


## <a name="suppress-alerts"></a><span data-ttu-id="25b6f-119">경고 표시 안</span><span class="sxs-lookup"><span data-stu-id="25b6f-119">Suppress alerts</span></span>
<span data-ttu-id="25b6f-120">Microsoft Defender 보안 센터에 경고가 나타나지 못하게 해야 하는 시나리오가 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="25b6f-120">There might be scenarios where you need to suppress alerts from appearing in Microsoft Defender Security Center.</span></span> <span data-ttu-id="25b6f-121">Endpoint용 Defender를 사용하면 조직의 알려진 도구 또는 프로세스와 같이 무해한 것으로 알려진 특정 경고에 대한 제거 규칙을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="25b6f-121">Defender for Endpoint lets you create suppression rules for specific alerts that are known to be innocuous such as known tools or processes in your organization.</span></span>

<span data-ttu-id="25b6f-122">제거 규칙은 기존 경고에서 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="25b6f-122">Suppression rules can be created from an existing alert.</span></span> <span data-ttu-id="25b6f-123">필요한 경우 사용하지 않도록 설정하고 다시 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="25b6f-123">They can be disabled and reenabled if needed.</span></span>

<span data-ttu-id="25b6f-124">제거 규칙을 만들면 규칙이 만들어진 시점부터 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="25b6f-124">When a suppression rule is created, it will take effect from the point when the rule is created.</span></span> <span data-ttu-id="25b6f-125">이 규칙은 규칙을 만들기 전에 큐에 이미 있는 기존 경고에 영향을 주지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="25b6f-125">The rule will not affect existing alerts already in the queue, prior to the rule creation.</span></span> <span data-ttu-id="25b6f-126">규칙은 규칙을 만든 후 설정된 조건을 충족하는 경고에만 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="25b6f-126">The rule will only be applied on alerts that satisfy the conditions set after the rule is created.</span></span>

<span data-ttu-id="25b6f-127">제거 규칙에 대한 두 가지 컨텍스트 중 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="25b6f-127">There are two contexts for a suppression rule that you can choose from:</span></span>

- <span data-ttu-id="25b6f-128">**이 장치에서 경고 표시 안 하세요.**</span><span class="sxs-lookup"><span data-stu-id="25b6f-128">**Suppress alert on this device**</span></span>
- <span data-ttu-id="25b6f-129">**조직에서 경고 표시 안 하게**</span><span class="sxs-lookup"><span data-stu-id="25b6f-129">**Suppress alert in my organization**</span></span>

<span data-ttu-id="25b6f-130">규칙의 컨텍스트를 통해 포털에 표시될 수 있는 정보를 조정하고 포털에 실제 보안 알림만 표시되도록 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="25b6f-130">The context of the rule lets you tailor what gets surfaced into the portal and ensure that only real security alerts are surfaced into the portal.</span></span>

<span data-ttu-id="25b6f-131">다음 표의 예제를 사용하여 제거 규칙에 대한 컨텍스트를 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="25b6f-131">You can use the examples in the following table to help you choose the context for a suppression rule:</span></span>

| <span data-ttu-id="25b6f-132">**컨텍스트**</span><span class="sxs-lookup"><span data-stu-id="25b6f-132">**Context**</span></span>                           | <span data-ttu-id="25b6f-133">**정의**</span><span class="sxs-lookup"><span data-stu-id="25b6f-133">**Definition**</span></span>                                                                                                                                              | <span data-ttu-id="25b6f-134">**예제 시나리오**</span><span class="sxs-lookup"><span data-stu-id="25b6f-134">**Example scenarios**</span></span>                                                                                                                                                                                                  |
|:--------------------------------------|:------------------------------------------------------------------------------------------------------------------------------------------------------------|:-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| <span data-ttu-id="25b6f-135">**이 장치에서 경고 표시 안 하세요.**</span><span class="sxs-lookup"><span data-stu-id="25b6f-135">**Suppress alert on this device**</span></span>    | <span data-ttu-id="25b6f-136">경고 제목이 같고 해당 특정 디바이스에서만 경고가 표시되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="25b6f-136">Alerts with the same alert title and on that specific device only will be suppressed.</span></span> <br /><br /><span data-ttu-id="25b6f-137">해당 장치의 다른 모든 경고는 억제되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="25b6f-137">All other alerts on that device will not be suppressed.</span></span> | <ul><li><span data-ttu-id="25b6f-138">보안 연구원이 조직의 다른 장치를 공격하는 데 사용된 악성 스크립트를 조사하고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="25b6f-138">A security researcher is investigating a malicious script that has been used to attack other devices in your organization.</span></span></li><li><span data-ttu-id="25b6f-139">개발자는 정기적으로 팀을 위한 PowerShell 스크립트를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="25b6f-139">A developer regularly creates PowerShell scripts for their team.</span></span></li></ul> |
| <span data-ttu-id="25b6f-140">**조직에서 경고 표시 안 하게**</span><span class="sxs-lookup"><span data-stu-id="25b6f-140">**Suppress alert in my organization**</span></span> | <span data-ttu-id="25b6f-141">모든 장치에서 동일한 경고 제목이 있는 경고는 표시되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="25b6f-141">Alerts with the same alert title on any device will be suppressed.</span></span>                                                                                         | <ul><li><span data-ttu-id="25b6f-142">조직의 모든 사람이 무해한 관리 도구를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="25b6f-142">A benign administrative tool is used by everyone in your organization.</span></span></li></ul>                                                                                                                               |

### <a name="suppress-an-alert-and-create-a-new-suppression-rule"></a><span data-ttu-id="25b6f-143">경고를 표시하지하고 새 제거 규칙을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="25b6f-143">Suppress an alert and create a new suppression rule:</span></span>
<span data-ttu-id="25b6f-144">경고가 제거되거나 해결된 경우를 제어하는 사용자 지정 규칙을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="25b6f-144">Create custom rules to control when alerts are suppressed, or resolved.</span></span> <span data-ttu-id="25b6f-145">경고 제목, 손상 표시기 및 조건을 지정하여 경고가 억제되는 경우의 컨텍스트를 제어할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="25b6f-145">You can control the context for when an alert is suppressed by specifying the alert title, Indicator of compromise, and the conditions.</span></span> <span data-ttu-id="25b6f-146">컨텍스트를 지정한 후 경고에 대한 작업 및 범위를 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="25b6f-146">After specifying the context, you’ll be able to configure the action and scope on the alert.</span></span> 

1. <span data-ttu-id="25b6f-147">표시하지 말아야 할 경고를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="25b6f-147">Select the alert you'd like to suppress.</span></span> <span data-ttu-id="25b6f-148">그러면 경고 관리 **창이** 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="25b6f-148">This brings up the **Alert management** pane.</span></span>

2.  <span data-ttu-id="25b6f-149">제거 **규칙 만들기 를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="25b6f-149">Select **Create a suppression rule**.</span></span>

    <span data-ttu-id="25b6f-150">이러한 특성을 사용하여 제거 조건을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="25b6f-150">You can create a suppression condition using these attributes.</span></span> <span data-ttu-id="25b6f-151">각 조건 사이에 AND 연산자가 적용되어 모든 조건이 충족될 때만 제거가 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="25b6f-151">An AND operator is applied between each condition, so suppression occurs only if all conditions are met.</span></span>
    
    * <span data-ttu-id="25b6f-152">파일 SHA1</span><span class="sxs-lookup"><span data-stu-id="25b6f-152">File SHA1</span></span>
    * <span data-ttu-id="25b6f-153">파일 이름 - 와일드카드 지원</span><span class="sxs-lookup"><span data-stu-id="25b6f-153">File name - wildcard supported</span></span>
    * <span data-ttu-id="25b6f-154">폴더 경로 - 와일드카드 지원</span><span class="sxs-lookup"><span data-stu-id="25b6f-154">Folder path - wildcard supported</span></span>
    * <span data-ttu-id="25b6f-155">IP 주소</span><span class="sxs-lookup"><span data-stu-id="25b6f-155">IP address</span></span>
    * <span data-ttu-id="25b6f-156">URL - 와일드카드 지원</span><span class="sxs-lookup"><span data-stu-id="25b6f-156">URL - wildcard supported</span></span>
    * <span data-ttu-id="25b6f-157">명령줄 - 와일드카드 지원</span><span class="sxs-lookup"><span data-stu-id="25b6f-157">Command line - wildcard supported</span></span>

3. <span data-ttu-id="25b6f-158">**IOC 트리거 를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="25b6f-158">Select the **Triggering IOC**.</span></span>
    
4. <span data-ttu-id="25b6f-159">경고에 대한 작업 및 범위를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="25b6f-159">Specify the action and scope on the alert.</span></span> <br>
   <span data-ttu-id="25b6f-160">경고를 자동으로 해결하거나 포털에서 숨길 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="25b6f-160">You can automatically resolve an alert or hide it from the portal.</span></span> <span data-ttu-id="25b6f-161">자동으로 해결되는 경고는 경고 큐, 경고 페이지 및 장치 타임라인의 해결된 섹션에 표시되며 Endpoint API용 Defender에서 해결된 것으로 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="25b6f-161">Alerts that are automatically resolved will appear in the resolved section of the alerts queue, alert page, and device timeline and will appear as resolved across Defender for Endpoint APIs.</span></span> <br><br> <span data-ttu-id="25b6f-162">숨김으로 표시된 경고는 장치의 연결된 경고와 대시보드에서 모두 전체 시스템에서 제거되지 않습니다. 끝점 API용 Defender에서 스트리밍되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="25b6f-162">Alerts that are marked as hidden will be suppressed from the entire system, both on the device's associated alerts and from the dashboard and will not be streamed across Defender for Endpoint APIs.</span></span>


5. <span data-ttu-id="25b6f-163">규칙 이름과 설명을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="25b6f-163">Enter a rule name and a comment.</span></span>

6. <span data-ttu-id="25b6f-164">**저장** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="25b6f-164">Click **Save**.</span></span>

#### <a name="view-the-list-of-suppression-rules"></a><span data-ttu-id="25b6f-165">제거 규칙 목록 보기</span><span class="sxs-lookup"><span data-stu-id="25b6f-165">View the list of suppression rules</span></span>

1. <span data-ttu-id="25b6f-166">탐색 창에서 설정 **경고**  >  **제거 를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="25b6f-166">In the navigation pane, select **Settings** > **Alert suppression**.</span></span>

2. <span data-ttu-id="25b6f-167">제거 규칙 목록에는 조직의 사용자가 만든 모든 규칙이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="25b6f-167">The list of suppression rules shows all the rules that users in your organization have created.</span></span>

<span data-ttu-id="25b6f-168">제거 규칙 관리에 대한 자세한 내용은 제거 규칙 [관리를 참조하세요.](manage-suppression-rules.md)</span><span class="sxs-lookup"><span data-stu-id="25b6f-168">For more information on managing suppression rules, see [Manage suppression rules](manage-suppression-rules.md)</span></span>

## <a name="change-the-status-of-an-alert"></a><span data-ttu-id="25b6f-169">경고 상태 변경</span><span class="sxs-lookup"><span data-stu-id="25b6f-169">Change the status of an alert</span></span>

<span data-ttu-id="25b6f-170">조사가 진행될 때 상태를 변경하여 경고(신규, 진행 중 또는 해결된 경고)를 분류할 수 있습니다. </span><span class="sxs-lookup"><span data-stu-id="25b6f-170">You can categorize alerts (as **New**, **In Progress**, or **Resolved**) by changing their status as your investigation progresses.</span></span> <span data-ttu-id="25b6f-171">이렇게 하면 팀이 경고에 대응하는 방법을 구성하고 관리하는 데 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="25b6f-171">This helps you organize and manage how your team can respond to alerts.</span></span>

<span data-ttu-id="25b6f-172">예를 들어 팀 리더는  모든 새 알림을 검토하고 추가  분석을 위해 진행 중인 경고 큐에 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="25b6f-172">For example, a team leader can review all **New** alerts, and decide to assign them to the **In Progress** queue for further analysis.</span></span>

<span data-ttu-id="25b6f-173">또는 경고가 무관한 장치(예: 보안 관리자에 속한 장치)에서 발생하거나 이전 경고를 통해 처리되고 있는 경우 해결된 경고를 해결된 큐에 할당할 수 있습니다. </span><span class="sxs-lookup"><span data-stu-id="25b6f-173">Alternatively, the team leader might assign the alert to the **Resolved** queue if they know the alert is benign, coming from a device that is irrelevant (such as one belonging to a security administrator), or is being dealt with through an earlier alert.</span></span>



## <a name="alert-classification"></a><span data-ttu-id="25b6f-174">경고 분류</span><span class="sxs-lookup"><span data-stu-id="25b6f-174">Alert classification</span></span>
<span data-ttu-id="25b6f-175">분류를 설정하지 못하게 선택하거나 경고가 실제 경고인지 또는 거짓 경고인지를 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="25b6f-175">You can choose not to set a classification, or specify whether an alert is a true alert or a false alert.</span></span> <span data-ttu-id="25b6f-176">참 긍정/가성의 분류를 제공하는 것이 중요합니다.</span><span class="sxs-lookup"><span data-stu-id="25b6f-176">It's important to provide the classification of true positive/false positive.</span></span> <span data-ttu-id="25b6f-177">이 분류는 경고 품질을 모니터링하고 경고의 정확도를 향상하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="25b6f-177">This classification is used to monitor alert quality, and make alerts more accurate.</span></span> <span data-ttu-id="25b6f-178">"결정" 필드는 "참 긍정" 분류에 대한 추가 고화성을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="25b6f-178">The "determination" field defines additional fidelity for a "true positive" classification.</span></span> 

## <a name="add-comments-and-view-the-history-of-an-alert"></a><span data-ttu-id="25b6f-179">설명 추가 및 경고 기록 보기</span><span class="sxs-lookup"><span data-stu-id="25b6f-179">Add comments and view the history of an alert</span></span>
<span data-ttu-id="25b6f-180">경고에 대한 설명을 추가하고 기록 이벤트를 보고 경고에 대한 이전 변경 내용을 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="25b6f-180">You can add comments and view historical events about an alert to see previous changes made to the alert.</span></span>

<span data-ttu-id="25b6f-181">경고가 변경될 때마다 해당 경고가 설명 및 기록 섹션에 **기록됩니다.**</span><span class="sxs-lookup"><span data-stu-id="25b6f-181">Whenever a change or comment is made to an alert, it is recorded in the **Comments and history** section.</span></span>

<span data-ttu-id="25b6f-182">추가된 메모는 창에 바로 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="25b6f-182">Added comments instantly appear on the pane.</span></span>


## <a name="related-topics"></a><span data-ttu-id="25b6f-183">관련 항목</span><span class="sxs-lookup"><span data-stu-id="25b6f-183">Related topics</span></span>
- [<span data-ttu-id="25b6f-184">제거 규칙 관리</span><span class="sxs-lookup"><span data-stu-id="25b6f-184">Manage suppression rules</span></span>](manage-suppression-rules.md)
- [<span data-ttu-id="25b6f-185">끝점 경고 큐에 대한 Microsoft Defender 보기 및 구성</span><span class="sxs-lookup"><span data-stu-id="25b6f-185">View and organize the Microsoft Defender for Endpoint Alerts queue</span></span>](alerts-queue.md)
- [<span data-ttu-id="25b6f-186">끝점 경고에 대한 Microsoft Defender 조사</span><span class="sxs-lookup"><span data-stu-id="25b6f-186">Investigate Microsoft Defender for Endpoint alerts</span></span>](investigate-alerts.md)
- [<span data-ttu-id="25b6f-187">끝점 경고에 대한 Microsoft Defender와 관련된 파일 조사</span><span class="sxs-lookup"><span data-stu-id="25b6f-187">Investigate a file associated with a Microsoft Defender for Endpoint alert</span></span>](investigate-files.md)
- [<span data-ttu-id="25b6f-188">Microsoft Defender for Endpoint Devices 목록에서 장치 조사</span><span class="sxs-lookup"><span data-stu-id="25b6f-188">Investigate devices in the Microsoft Defender for Endpoint Devices list</span></span>](investigate-machines.md)
- [<span data-ttu-id="25b6f-189">끝점 경고에 대한 Microsoft Defender와 연결된 IP 주소 조사</span><span class="sxs-lookup"><span data-stu-id="25b6f-189">Investigate an IP address associated with a Microsoft Defender for Endpoint alert</span></span>](investigate-ip.md)
- [<span data-ttu-id="25b6f-190">끝점 경고에 대한 Microsoft Defender와 연결된 도메인 조사</span><span class="sxs-lookup"><span data-stu-id="25b6f-190">Investigate a domain associated with a Microsoft Defender for Endpoint alert</span></span>](investigate-domain.md)
- [<span data-ttu-id="25b6f-191">끝점용 Microsoft Defender에서 사용자 계정 조사</span><span class="sxs-lookup"><span data-stu-id="25b6f-191">Investigate a user account in Microsoft Defender for Endpoint</span></span>](investigate-user.md)
