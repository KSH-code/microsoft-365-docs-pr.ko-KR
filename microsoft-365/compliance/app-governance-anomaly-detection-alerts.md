---
title: 이상 탐지 경고 조사
f1.keywords:
- NOCSH
ms.author: v-tophillips
author: v-tophillips
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.collection: m365-security-compliance
localization_priority: Priority
search.appverid:
- MOE150
- MET150
description: 이상 탐지 경고를 조사합니다.
ms.openlocfilehash: 6797cdcbfd2a2d3c32768a158a5f8cd0fc579d56
ms.sourcegitcommit: 41c7f7bd5c808ee5ceca0f6efe13d4e67da0262b
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/14/2021
ms.locfileid: "53420473"
---
# <a name="investigate-anomaly-detection-alerts"></a><span data-ttu-id="73ec8-103">이상 탐지 경고 조사</span><span class="sxs-lookup"><span data-stu-id="73ec8-103">Investigate anomaly detection alerts</span></span>

 <span data-ttu-id="73ec8-104">Microsoft 앱 거버넌스는 악의적인 활동에 대한 보안 탐지 및 경고를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="73ec8-104">Microsoft app governance provides security detections and alerts for malicious activities.</span></span> <span data-ttu-id="73ec8-105">이 가이드의 목적은 각 경고에 대한 일반적이고 실용적인 정보를 제공하여 조사 및 수정 작업에 도움이 되는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="73ec8-105">The purpose of this guide is to provide you with general and practical information on each alert, to help with your investigation and remediation tasks.</span></span> <span data-ttu-id="73ec8-106">이 가이드에는 경고를 트리거하는 조건에 관한 일반적인 정보가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="73ec8-106">Included in this guide is general information about the conditions for triggering alerts.</span></span> <span data-ttu-id="73ec8-107">이상 탐지는 본질적으로 결정론적이지 않으므로 일반적인 상황에서 벗어나는 동작이 있을 때만 트리거됩니다.</span><span class="sxs-lookup"><span data-stu-id="73ec8-107">Because anomaly detections are non-deterministic by nature, they're only triggered when there's behavior that deviates from the norm.</span></span> <span data-ttu-id="73ec8-108">마지막으로 일부 경고는 미리 보기 상태일 수 있으므로 업데이트된 경고 상태에 관한 공식 설명서를 정기적으로 검토합니다.</span><span class="sxs-lookup"><span data-stu-id="73ec8-108">Finally, some alerts may be in preview, so regularly review the official documentation for updated alert status.</span></span>

## <a name="mitre-attck"></a><span data-ttu-id="73ec8-109">MITRE ATT&CK</span><span class="sxs-lookup"><span data-stu-id="73ec8-109">MITRE ATT&CK</span></span>

<span data-ttu-id="73ec8-110">Microsoft 앱 거버넌스 경고와 친숙한 MITRE ATT&CK 행렬 간의 관계를 더욱 쉽게 매핑할 수 있도록 해당 MITRE ATT&CK 전술별로 경고를 분류했습니다.</span><span class="sxs-lookup"><span data-stu-id="73ec8-110">To make it easier to map the relationship between Microsoft app governance alerts and the familiar MITRE ATT&CK Matrix, we've categorized the alerts by their corresponding MITRE ATT&CK tactic.</span></span> <span data-ttu-id="73ec8-111">이 추가 참조를 사용하면 Microsoft 응용 프로그램 보안 및 거버넌스 경고가 트리거될 때 사용 중일 가능성이 있는 의심스러운 공격 기술을 더 쉽게 이해할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="73ec8-111">This additional reference makes it easier to understand the suspected attacks technique potentially in use when Microsoft Application Security and Governance alert is triggered.</span></span>

<span data-ttu-id="73ec8-112">이 가이드에서는 다음 범주에서 Microsoft 앱 거버넌스 경고를 조사하고 수정하는 방법에 관한 정보를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="73ec8-112">This guide provides information about investigating and remediating Microsoft app governance alerts in the following categories.</span></span>

- <span data-ttu-id="73ec8-113">초기 액세스</span><span class="sxs-lookup"><span data-stu-id="73ec8-113">Initial Access</span></span>
- <span data-ttu-id="73ec8-114">실행</span><span class="sxs-lookup"><span data-stu-id="73ec8-114">Execution</span></span>
- <span data-ttu-id="73ec8-115">지속성</span><span class="sxs-lookup"><span data-stu-id="73ec8-115">Persistence</span></span>
- <span data-ttu-id="73ec8-116">권한 상승</span><span class="sxs-lookup"><span data-stu-id="73ec8-116">Privilege Escalation</span></span>
- <span data-ttu-id="73ec8-117">방어 회피</span><span class="sxs-lookup"><span data-stu-id="73ec8-117">Defense Evasion</span></span>
- <span data-ttu-id="73ec8-118">자격 증명 액세스</span><span class="sxs-lookup"><span data-stu-id="73ec8-118">Credential Access</span></span>
- <span data-ttu-id="73ec8-119">컬렉션</span><span class="sxs-lookup"><span data-stu-id="73ec8-119">Collection</span></span>
- <span data-ttu-id="73ec8-120">유출</span><span class="sxs-lookup"><span data-stu-id="73ec8-120">Exfiltration</span></span>
- <span data-ttu-id="73ec8-121">영향</span><span class="sxs-lookup"><span data-stu-id="73ec8-121">Impact</span></span>

## <a name="security-alert-classifications"></a><span data-ttu-id="73ec8-122">보안 경고 분류</span><span class="sxs-lookup"><span data-stu-id="73ec8-122">Security alert classifications</span></span>

<span data-ttu-id="73ec8-123">적절한 조사에 따라 모든 Microsoft 앱 거버넌스 경고를 다음 활동 유형 중 하나로 분류할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="73ec8-123">Following proper investigation, all Microsoft app governance alerts can be classified as one of the following activity types:</span></span>

- <span data-ttu-id="73ec8-124">TP(True Positive): 확인된 악성 활동에 대한 경고입니다.</span><span class="sxs-lookup"><span data-stu-id="73ec8-124">True positive (TP): An alert on a confirmed malicious activity.</span></span>
- <span data-ttu-id="73ec8-125">B-TP(Benign True Positive): 침투 테스트 또는 기타 권한이 있는 의심스러운 작업과 같이 의심스럽지만 악의적이지는 않은 활동에 대한 경고입니다.</span><span class="sxs-lookup"><span data-stu-id="73ec8-125">Benign true positive (B-TP): An alert on suspicious but not malicious activity, such as a penetration test or other authorized suspicious action.</span></span>
- <span data-ttu-id="73ec8-126">FP(False Positive): 악의적이 아닌 활동에 대한 경고입니다.</span><span class="sxs-lookup"><span data-stu-id="73ec8-126">False positive (FP): An alert on a non-malicious activity.</span></span>

## <a name="general-investigation-steps"></a><span data-ttu-id="73ec8-127">일반적인 조사 단계</span><span class="sxs-lookup"><span data-stu-id="73ec8-127">General investigation steps</span></span>

<span data-ttu-id="73ec8-128">모든 유형의 경고를 조사할 때 다음 일반 지침을 사용하여 권장 조치를 적용하기 전에 잠재적 위협을 보다 명확하게 이해합니다.</span><span class="sxs-lookup"><span data-stu-id="73ec8-128">Use the following general guidelines when investigating any type of alert to gain a clearer understanding of the potential threat before applying the recommended action.</span></span>

- <span data-ttu-id="73ec8-129">앱 심각도 수준을 검토하고 테넌트의 나머지 앱과 비교합니다.</span><span class="sxs-lookup"><span data-stu-id="73ec8-129">Review the App severity level and compare with the rest of the app in your tenant.</span></span> <span data-ttu-id="73ec8-130">이 검토는 테넌트에서 더 큰 위험을 초래하는 앱을 식별하는 데 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="73ec8-130">This review will help you identify which Apps in your tenant pose the greater risk.</span></span>
- <span data-ttu-id="73ec8-131">TP를 식별하는 경우 모든 앱 활동을 검토하여 영향을 파악합니다.</span><span class="sxs-lookup"><span data-stu-id="73ec8-131">If you identify a TP, review all the App activities to gain an understanding of the impact.</span></span> <span data-ttu-id="73ec8-132">예를 들어 다음 앱 정보를 검토합니다.</span><span class="sxs-lookup"><span data-stu-id="73ec8-132">For example, review the following App information:</span></span>

  - <span data-ttu-id="73ec8-133">액세스 권한이 부여된 범위</span><span class="sxs-lookup"><span data-stu-id="73ec8-133">Scopes granted access</span></span>
  - <span data-ttu-id="73ec8-134">평소와 다른 행동</span><span class="sxs-lookup"><span data-stu-id="73ec8-134">Unusual behavior</span></span>  
  - <span data-ttu-id="73ec8-135">IP 주소 및 위치</span><span class="sxs-lookup"><span data-stu-id="73ec8-135">IP address and location</span></span>

## <a name="initial-access-alerts"></a><span data-ttu-id="73ec8-136">초기 액세스 경고</span><span class="sxs-lookup"><span data-stu-id="73ec8-136">Initial access alerts</span></span>

<span data-ttu-id="73ec8-137">이 섹션에서는 악의적인 앱이 조직에서 기반을 유지하려고 할 수 있음을 나타내는 경고에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="73ec8-137">This section describes alerts indicating that a malicious app may be attempting to maintain their foothold in your organization.</span></span>  

### <a name="encoded-app-name-with-suspicious-consent-scopes"></a><span data-ttu-id="73ec8-138">의심스러운 동의 범위가 있는 인코딩된 앱 이름</span><span class="sxs-lookup"><span data-stu-id="73ec8-138">Encoded app name with suspicious consent scopes</span></span>

<span data-ttu-id="73ec8-139">**심각도:** 보통</span><span class="sxs-lookup"><span data-stu-id="73ec8-139">**Severity:** Medium</span></span>

<span data-ttu-id="73ec8-140">**설명**: 이 탐지는 유니코드 또는 인코딩된 문자와 같이 문자가 있고, 의심스러운 동의 범위를 요청하며, Graph API를 통해 사용자 메일 폴더에 액세스하는 OAuth 앱을 식별합니다.</span><span class="sxs-lookup"><span data-stu-id="73ec8-140">**Description**: This detection identifies OAuth apps with characters, such as Unicode or Encoded characters, requested for suspicious consent scopes and that accessed users mail folders through the Graph API.</span></span> <span data-ttu-id="73ec8-141">이 경고는 악의적 앱이 잘 알려지고 신뢰할 수 있는 앱으로 가장하여 사용자가 악의적 앱에 동의하게 하려는 악의적 사용자의 시도를 나타낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="73ec8-141">This alert can indicate an attempt to camouflage a malicious app as a known and trusted app so that adversaries can mislead the users into consenting to the malicious app.</span></span>

<span data-ttu-id="73ec8-142">**TP일까요, FP일까요?**</span><span class="sxs-lookup"><span data-stu-id="73ec8-142">**TP or FP?**</span></span>

- <span data-ttu-id="73ec8-143">**TP**: OAuth 앱이 알 수 없는 원본에서 전달된 의심스러운 범위를 가진 표시 이름을 인코딩했음을 확인할 수 있다면 TP(True Positive)를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="73ec8-143">**TP**: If you can confirm that the OAuth app has Encoded the display name with suspicious scopes delivered from unknown source, then a true positive is indicated.</span></span>  

  <span data-ttu-id="73ec8-144">**권장 작업**: 이 앱에서 요청하고, 사용자가 액세스를 허용할 수 있는 권한 수준을 검토합니다.</span><span class="sxs-lookup"><span data-stu-id="73ec8-144">**Recommended action**: Review the level of permission requested by this app and which users granted access.</span></span> <span data-ttu-id="73ec8-145">조사 결과에 따라 이 앱에 대한 액세스를 금지하도록 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="73ec8-145">Based on your investigation you can choose to ban access to this app.</span></span>

  <span data-ttu-id="73ec8-146">앱에 대한 액세스를 금지하려면 OAuth 앱 페이지에서 금지하려는 앱이 표시되는 행의 금지 아이콘을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="73ec8-146">To ban access to the app, on the OAuth apps page, on the row in which the app you want to ban appears, select the ban icon.</span></span> <span data-ttu-id="73ec8-147">사용자에게 사용자가 설치하고 권한을 부여한 앱이 금지되었음을 알릴지 여부를 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="73ec8-147">You can choose whether you want to tell users the app they installed and authorized has been banned.</span></span> <span data-ttu-id="73ec8-148">이 알림을 통해 사용자는 앱이 비활성화되고 연결된 앱에 액세스할 수 없음을 알 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="73ec8-148">The notification lets users know the app will be disabled and they will not have access to the connected app.</span></span> <span data-ttu-id="73ec8-149">사용자에게 알리지 않으려면 대화 상자에서 이 금지된 앱에 액세스 권한을 부여한 사용자에게 알리기를 선택 취소합니다.</span><span class="sxs-lookup"><span data-stu-id="73ec8-149">If you do not want them to know, unselect Notify users who granted access to this banned app in the dialog.</span></span> <span data-ttu-id="73ec8-150">앱 사용자에게 앱이 사용 금지될 것임을 알리는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="73ec8-150">We recommend that you let the app users know their app is about to be banned from use.</span></span>

- <span data-ttu-id="73ec8-151">**FP**: 앱에 인코딩된 이름이 있지만 조직에서 정당한 비즈니스 용도가 있음을 확인할 수 있는 경우.</span><span class="sxs-lookup"><span data-stu-id="73ec8-151">**FP**: If you are to confirm that the app has an encoded name but has a legitimate business use in the organization.</span></span>

  <span data-ttu-id="73ec8-152">**권장 작업**: 경고를 해제합니다.</span><span class="sxs-lookup"><span data-stu-id="73ec8-152">**Recommended action**: Dismiss the alert.</span></span>

#### <a name="understand-the-scope-of-the-breach"></a><span data-ttu-id="73ec8-153">위반 범위 이해하기</span><span class="sxs-lookup"><span data-stu-id="73ec8-153">Understand the scope of the breach</span></span>

<span data-ttu-id="73ec8-154">[위험한 OAuth 앱을 조사](/cloud-app-security/investigate-risky-oauth)하는 방법에 관한 자습서를 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="73ec8-154">Follow the tutorial on how to [investigate risky OAuth apps](/cloud-app-security/investigate-risky-oauth).</span></span>

### <a name="oauth-app-with-read-scopes-have-suspicious-reply-url"></a><span data-ttu-id="73ec8-155">읽기 범위가 있는 OAuth 앱에 의심스러운 회신 URL이 있음</span><span class="sxs-lookup"><span data-stu-id="73ec8-155">OAuth App with read Scopes have suspicious Reply URL</span></span>

<span data-ttu-id="73ec8-156">**심각도**: 보통</span><span class="sxs-lookup"><span data-stu-id="73ec8-156">**Severity**: Medium</span></span>

<span data-ttu-id="73ec8-157">**설명**: 이 탐지는 User.Read, People.Read, Contacts.Read, Mail.Read, Contacts.Read.Shared 등 읽기 범위가 있고, Graph API를 통해 의심스러운 회신 URL로 리디렉션하는 OAuth 앱을 식별합니다.</span><span class="sxs-lookup"><span data-stu-id="73ec8-157">**Description**: This detection identifies an OAuth app with only Read scopes such as User.Read, People.Read, Contacts.Read, Mail.Read, Contacts.Read.Shared redirects to suspicious Reply URL through Graph API.</span></span> <span data-ttu-id="73ec8-158">이 활동은 읽기 범위 등 권한이 적은 악성 앱이 사용자 계정 정찰을 수행하는 데 악용될 수 있음을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="73ec8-158">This activity attempts to indicate that malicious app with less privilege permission (such as Read scopes) could be exploited to conduct users account reconnaissance.</span></span>

<span data-ttu-id="73ec8-159">**TP일까요, FP일까요?**</span><span class="sxs-lookup"><span data-stu-id="73ec8-159">**TP or FP?**</span></span>

- <span data-ttu-id="73ec8-160">**TP**: 읽기 범위가 있는 OAuth 앱이 알 수 없는 원본에서 전달되었고, 의심스러운 URL로 리디렉션된다는 사실을 확인할 수 있다면 TP(True Positive)를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="73ec8-160">**TP**: If you’re able to confirm that the OAuth app with read scope is delivered from an unknown source, and redirects to a suspicious URL, then a true positive is indicated.</span></span>

  <span data-ttu-id="73ec8-161">**권장 작업**: 앱에서 요청한 회신 URL과 범위를 검토합니다.</span><span class="sxs-lookup"><span data-stu-id="73ec8-161">**Recommended action**: Review the Reply URL and scopes requested by the app.</span></span> <span data-ttu-id="73ec8-162">조사 결과에 따라 이 앱에 대한 액세스를 금지하도록 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="73ec8-162">Based on your investigation you can choose to ban access to this app.</span></span> <span data-ttu-id="73ec8-163">이 앱에서 요청하고, 사용자가 액세스를 허용한 권한 수준을 검토합니다.</span><span class="sxs-lookup"><span data-stu-id="73ec8-163">Review the level of permission requested by this app and which users have granted access.</span></span>

  <span data-ttu-id="73ec8-164">앱에 대한 액세스를 금지하려면 OAuth 앱 페이지에서 금지하려는 앱이 표시되는 행의 금지 아이콘을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="73ec8-164">To ban access to the app, on the OAuth apps page, on the row in which the app you want to ban appears, select the ban icon.</span></span> <span data-ttu-id="73ec8-165">사용자에게 사용자가 설치하고 권한을 부여한 앱이 금지되었음을 알릴지 여부를 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="73ec8-165">You can choose whether you want to tell users the app they installed and authorized has been banned.</span></span> <span data-ttu-id="73ec8-166">이 알림을 통해 사용자는 앱이 비활성화되고 연결된 앱에 액세스할 수 없음을 알 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="73ec8-166">The notification lets users know the app will be disabled and they will not have access to the connected app.</span></span> <span data-ttu-id="73ec8-167">사용자에게 알리지 않으려면 대화 상자에서 이 금지된 앱에 액세스 권한을 부여한 사용자에게 알리기를 선택 취소합니다.</span><span class="sxs-lookup"><span data-stu-id="73ec8-167">If you do not want them to know, unselect Notify users who granted access to this banned app in the dialog.</span></span> <span data-ttu-id="73ec8-168">앱 사용자에게 앱이 사용 금지될 것임을 알리는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="73ec8-168">We recommend that you let the app users know their app is about to be banned from use.</span></span>

- <span data-ttu-id="73ec8-169">**B-TP**: 조사 후 앱에 조직 내 정당한 비즈니스 용도가 있음을 확인할 수 있는 경우.</span><span class="sxs-lookup"><span data-stu-id="73ec8-169">**B-TP**: If after investigation, you can confirm that the app has a legitimate business use in the organization.</span></span>

  <span data-ttu-id="73ec8-170">**권장 작업**: 경고를 해제합니다.</span><span class="sxs-lookup"><span data-stu-id="73ec8-170">**Recommended action**: Dismiss the alert.</span></span>

#### <a name="understand-the-scope-of-the-breach"></a><span data-ttu-id="73ec8-171">위반 범위 이해하기</span><span class="sxs-lookup"><span data-stu-id="73ec8-171">Understand the scope of the breach</span></span> 

1. <span data-ttu-id="73ec8-172">앱에서 수행한 모든 활동을 검토합니다.</span><span class="sxs-lookup"><span data-stu-id="73ec8-172">Review all activities done by the app.</span></span>
1. <span data-ttu-id="73ec8-173">앱이 의심스럽다고 생각되는 경우 다른 앱 스토어에서 앱의 이름 및 회신 URL을 조사하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="73ec8-173">If you suspect that an app is suspicious, we recommend that you investigate the app’s name and Reply URL in different app stores.</span></span> <span data-ttu-id="73ec8-174">앱 스토어를 확인할 때 다음 앱 유형에 집중합니다.</span><span class="sxs-lookup"><span data-stu-id="73ec8-174">When checking app stores, focus on the following types of apps:</span></span>
   - <span data-ttu-id="73ec8-175">최근에 만든 앱</span><span class="sxs-lookup"><span data-stu-id="73ec8-175">Apps that have been created recently.</span></span>
   - <span data-ttu-id="73ec8-176">의심스러운 회신 URL이 있는 앱</span><span class="sxs-lookup"><span data-stu-id="73ec8-176">Apps with a suspicious Reply URL</span></span>
   - <span data-ttu-id="73ec8-177">최근에 업데이트되지 않은 앱.</span><span class="sxs-lookup"><span data-stu-id="73ec8-177">Apps that haven't been recently updated.</span></span> <span data-ttu-id="73ec8-178">업데이트가 없다는 건 앱이 더 이상 지원되지 않는다는 뜻일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="73ec8-178">Lack of updates might indicate the app is no longer supported.</span></span>
1. <span data-ttu-id="73ec8-179">여전히 앱이 의심스럽다면 앱 이름과 게시자 이름, 회신 URL을 온라인에서 조사할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="73ec8-179">If you still suspect that an app is suspicious, you can research the app name, publisher name, and reply URL online</span></span>  

## <a name="persistence-alerts"></a><span data-ttu-id="73ec8-180">지속성 경고</span><span class="sxs-lookup"><span data-stu-id="73ec8-180">Persistence alerts</span></span>

<span data-ttu-id="73ec8-181">이 섹션에서는 악의적인 행위자가 조직에서 기반을 유지하려고 할 수 있음을 나타내는 경고에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="73ec8-181">This section describes alerts indicating that a malicious actor may be attempting to maintain their foothold in your organization.</span></span>

### <a name="app-with-suspicious-oauth-scope-creates-inbox-rule"></a><span data-ttu-id="73ec8-182">의심스러운 OAuth 범위가 있는 앱이 받은 편지함 규칙을 만듦</span><span class="sxs-lookup"><span data-stu-id="73ec8-182">App with Suspicious OAuth scope creates Inbox Rule</span></span>  

<span data-ttu-id="73ec8-183">**심각도**: 보통</span><span class="sxs-lookup"><span data-stu-id="73ec8-183">**Severity**: Medium</span></span>

<span data-ttu-id="73ec8-184">**MITRE ID**: T1137.005, T1114</span><span class="sxs-lookup"><span data-stu-id="73ec8-184">**MITRE ID’s**: T1137.005, T1114</span></span>  

<span data-ttu-id="73ec8-185">이 탐지는 의심스러운 범위에 동의하고, 의심스러운 받은 편지함 규칙을 만든 다음 Graph API를 통해 사용자 메일 폴더 및 메시지에 액세스하는 OAuth 앱을 식별합니다.</span><span class="sxs-lookup"><span data-stu-id="73ec8-185">This detection identifies an OAuth App that consented to suspicious scopes, creates a suspicious inbox rule, and then accessed users mail folders and messages through the Graph API.</span></span> <span data-ttu-id="73ec8-186">모든 전자 메일 또는 특정 전자 메일 다른 전자 메일 계정으로 전달과 같은 받은 편지함 규칙, 전자 메일에 액세스하고 다른 전자 메일 계정에 보내기 위한 그래프 호출은 조직의 정보를 유출하려는 시도일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="73ec8-186">Inbox rules, such as forwarding all or specific emails to another email account, and Graph calls to access emails and send to another email account, may be an attempt to exfiltrate information from your organization.</span></span>  

<span data-ttu-id="73ec8-187">**TP일까요, FP일까요?**</span><span class="sxs-lookup"><span data-stu-id="73ec8-187">**TP or FP?**</span></span>

- <span data-ttu-id="73ec8-188">**TP**: 알 수 없는 원본에서 전달된 의심스러운 범위를 가진 OAuth 타사 앱이 받은 편지함 규칙을 만들었다는 사실을 확인할 수 있다면 TP(True Positive)를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="73ec8-188">**TP**: If you can confirm that inbox rule was created by an OAuth third-party app with suspicious scopes delivered from an unknown source, then a true positive is indicated.</span></span>

  <span data-ttu-id="73ec8-189">**권장 작업**: 앱을 사용하지 않도록 설정 및 제거하고, 암호를 다시 설정하고, 받은 편지함 규칙을 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="73ec8-189">**Recommended action**:  Disable and remove the app, reset the password, and remove the inbox rule.</span></span>

  <span data-ttu-id="73ec8-190">Azure Active Directory를 사용하여 암호를 다시 설정하는 방법에 대한 자습서와 받은 편지함 규칙을 제거하는 방법에 대한 자습서 지침을 따르세요.</span><span class="sxs-lookup"><span data-stu-id="73ec8-190">Follow the tutorial on how to Reset a password using Azure Active Directory and follow the tutorial on how to remove the inbox rule.</span></span>

- <span data-ttu-id="73ec8-191">**FP**: 앱이 정당한 이유로 새 또는 개인 외부 전자 메일 계정에 받은 편지함 규칙을 만들었음을 확인할 수 있는 경우.</span><span class="sxs-lookup"><span data-stu-id="73ec8-191">**FP**: If you can confirm that app created an inbox rule to a new or personal external email account for legitimate reasons.</span></span>

  <span data-ttu-id="73ec8-192">**권장 작업**: 경고를 해제합니다.</span><span class="sxs-lookup"><span data-stu-id="73ec8-192">**Recommended action**: Dismiss the alert.</span></span>

#### <a name="understand-the-scope-of-the-breach"></a><span data-ttu-id="73ec8-193">위반 범위 이해하기</span><span class="sxs-lookup"><span data-stu-id="73ec8-193">Understand the scope of the breach</span></span>

1. <span data-ttu-id="73ec8-194">앱에서 수행한 모든 활동을 검토합니다.</span><span class="sxs-lookup"><span data-stu-id="73ec8-194">Review all activities done by the app.</span></span>
1. <span data-ttu-id="73ec8-195">앱에서 승인한 범위를 검토합니다.</span><span class="sxs-lookup"><span data-stu-id="73ec8-195">Review the scopes granted by the app.</span></span>
1. <span data-ttu-id="73ec8-196">앱에서 만든 받은 편지함 규칙 작업과 조건을 검토합니다.</span><span class="sxs-lookup"><span data-stu-id="73ec8-196">Review the inbox rule action and condition created by the app.</span></span>

## <a name="collection-alerts"></a><span data-ttu-id="73ec8-197">컬렉션 경고</span><span class="sxs-lookup"><span data-stu-id="73ec8-197">Collection alerts</span></span>

<span data-ttu-id="73ec8-198">이 섹션에서는 악의적인 행위자가 조직에서 목적을 이루기 위한 관련 데이터를 수집하려는 시도를 나타내는 경고에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="73ec8-198">This section describes alerts indicating that a malicious actor may be attempting to gather data of interest to their goal from your organization.</span></span>

### <a name="app-made-anomalous-graph-calls-to-read-e-mail"></a><span data-ttu-id="73ec8-199">앱에서 전자 메일을 읽기 위해 비정상적인 그래프 호출을 수행함</span><span class="sxs-lookup"><span data-stu-id="73ec8-199">App made anomalous Graph calls to read e-mail</span></span>

<span data-ttu-id="73ec8-200">**심각도**: 보통</span><span class="sxs-lookup"><span data-stu-id="73ec8-200">**Severity**: Medium</span></span>

<span data-ttu-id="73ec8-201">**MITRE ID**: T1114</span><span class="sxs-lookup"><span data-stu-id="73ec8-201">**MITRE ID**: T1114</span></span>

<span data-ttu-id="73ec8-202">이 탐지는 LOB(Line of Business) OAuth 앱이 Graph API를 통해 비정상적이고 많은 양의 사용자 메일 폴더 및 메시지에 액세스하는 경우를 식별하며, 이는 조직의 보안 위반 시도를 나타낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="73ec8-202">This detection identifies when Line of Business (LOB) OAuth App accesses an unusual and high volume of user's mail folders and messages through the Graph API, which can indicate an attempted breach of your organization.</span></span>

<span data-ttu-id="73ec8-203">**TP일까요, FP일까요?**</span><span class="sxs-lookup"><span data-stu-id="73ec8-203">**TP or FP?**</span></span>

- <span data-ttu-id="73ec8-204">**TP**: LOB(Line of Business)가 비정상적인 그래프 활동을 수행했다는 사실을 확인할 수 있다면 TP(True Positive)를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="73ec8-204">**TP**: If you can confirm that the unusual graph activity was performed by the Line of Business (LOB) OAuth App, then a true positive is indicated.</span></span>

  <span data-ttu-id="73ec8-205">**권장 작업**: 일시적으로 앱을 사용하지 않도록 설정하고 암호를 다시 설정한 다음 앱을 다시 사용하도록 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="73ec8-205">**Recommend actions**: Temporarily disable the app and reset the password and then re-enable the app.</span></span>

  <span data-ttu-id="73ec8-206">Azure Active Directory를 사용하여 암호를 다시 설정하는 방법에 대한 자습서 지침을 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="73ec8-206">Follow the tutorial on how to Reset a password using Azure Active Directory.</span></span>

- <span data-ttu-id="73ec8-207">**FP**: 앱이 비정상적으로 많은 양의 그래프 호출을 수행하는 게 정상이라는 사실을 확인할 수 있는 경우.</span><span class="sxs-lookup"><span data-stu-id="73ec8-207">**FP**: If you can confirm that the app is intended to do unusually high volume of graph calls.</span></span>

  <span data-ttu-id="73ec8-208">**권장 작업**: 경고를 해제합니다.</span><span class="sxs-lookup"><span data-stu-id="73ec8-208">**Recommended action**: Dismiss the alert.</span></span>

#### <a name="understand-the-scope-of-the-breach"></a><span data-ttu-id="73ec8-209">위반 범위 이해하기</span><span class="sxs-lookup"><span data-stu-id="73ec8-209">Understand the scope of the breach</span></span>

1. <span data-ttu-id="73ec8-210">이 앱에서 수행한 이벤트에 대한 활동 로그를 검토하여 전자 메일을 읽고 사용자의 중요한 전자 메일 정보를 수집하려는 기타 그래프 활동을 이해합니다.</span><span class="sxs-lookup"><span data-stu-id="73ec8-210">Review the activity log for events performed by this app to gain a better understanding of other Graph activities to read emails and attempt to collect users sensitive email information.</span></span>
1. <span data-ttu-id="73ec8-211">앱에 추가되는 예기치 않은 자격 증명을 모니터링합니다.</span><span class="sxs-lookup"><span data-stu-id="73ec8-211">Monitor for unexpected credential being added to the app.</span></span>
