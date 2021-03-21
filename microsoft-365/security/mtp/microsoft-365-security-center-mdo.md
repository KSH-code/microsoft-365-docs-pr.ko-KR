---
title: Microsoft 365 보안 센터의 Office 365용 Microsoft Defender
description: Office 365 보안 및 규정 준수 센터에서 Microsoft 365 보안 센터로의 변경에 대해 자세히 알아보겠습니다.
keywords: Microsoft 365 보안, Microsoft 365 보안 센터 시작하기, OATP, MDATP, MDO, MDE, 단일 창 방식, 새로운 보안 포털, 새로운 Defender 보안 포털
ms.date: 02/02/2021
ms.author: tracyp
author: msfttracyp
manager: dansimp
audience: Admin
ms.topic: overview
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.prod: m365-security
ms.technology: m365d
ms.openlocfilehash: a31927c11d2cfdf808abff1aeb02879ca3e84130
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/19/2021
ms.locfileid: "50906832"
---
# <a name="microsoft-defender-for-office-365-in-the-microsoft-365-security-center"></a><span data-ttu-id="c0d13-104">Microsoft 365 보안 센터의 Office 365용 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="c0d13-104">Microsoft Defender for Office 365 in the Microsoft 365 security center</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

[!INCLUDE [Prerelease](../includes/prerelease.md)]

<span data-ttu-id="c0d13-105">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="c0d13-105">**Applies to:**</span></span>
- [<span data-ttu-id="c0d13-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="c0d13-106">Microsoft 365 Defender</span></span>](./microsoft-threat-protection.md)
- [<span data-ttu-id="c0d13-107">엔드포인트용 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="c0d13-107">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2146631)
- [<span data-ttu-id="c0d13-108">Office 365용 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="c0d13-108">Microsoft Defender for Office 365</span></span>](../office-365-security/office-365-atp.md)

<span data-ttu-id="c0d13-109">[https://security.microsoft.com](https://security.microsoft.com)의 개선된 [Microsoft 365 보안 센터](./overview-security-center.md)는 Microsoft Defender 보안 센터와 Office 365 보안 및 준수 센터 등의 기존 Microsoft 보안 포털의 보안 기능을 결합합니다.</span><span class="sxs-lookup"><span data-stu-id="c0d13-109">The improved [Microsoft 365 security center](./overview-security-center.md) at [https://security.microsoft.com](https://security.microsoft.com) combines security capabilities from existing Microsoft security portals, including Microsoft Defender Security Center and the Office 365 Security & Compliance Center.</span></span> <span data-ttu-id="c0d13-110">이 개선된 센터는 보안 팀이 더 효과적이고 효율적으로 위협으로부터 조직을 보호하는 데 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c0d13-110">This improved center helps security teams protect their organization from threats more effectively and efficiently.</span></span>

<span data-ttu-id="c0d13-111">Office 365 보안 및 규정 준수 포털(protection.office.com)에 익숙한 경우 이 문서에서는 Microsoft 365 보안 센터의 몇 가지 변경 및 개선 사항을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="c0d13-111">If you are familiar with the Office 365 Security and Compliance portal (protection.office.com), this article describes some of the changes and improvements in the Microsoft 365 security center.</span></span>

<span data-ttu-id="c0d13-112">이점에 대한 자세한 정보: [Microsoft 365 보안 센터 개요](overview-security-center.md)</span><span class="sxs-lookup"><span data-stu-id="c0d13-112">Learn more about the benefits: [Overview of the Microsoft 365 security center](overview-security-center.md)</span></span>

<span data-ttu-id="c0d13-113">규정 준수 관련 항목을 찾고 있는 경우 [Microsoft 365 규정 준수 센터](https://compliance.microsoft.com/homepage)를 방문하세요.</span><span class="sxs-lookup"><span data-stu-id="c0d13-113">If you are looking for compliance-related items, visit the [Microsoft 365 compliance center](https://compliance.microsoft.com/homepage).</span></span>

## <a name="whats-changed"></a><span data-ttu-id="c0d13-114">변경된 기능</span><span class="sxs-lookup"><span data-stu-id="c0d13-114">What's changed</span></span>

<span data-ttu-id="c0d13-115">이 표는 **보안 및 규정 준수 센터** 및 **Microsoft 365 보안** 포털 간에 변경이 발생한 전자 메일 및 공동 작업 영역의 빠른 참조입니다.</span><span class="sxs-lookup"><span data-stu-id="c0d13-115">This table is a quick reference of Email & Collaboration areas where change has occurred between the **Security & Compliance center** and the **Microsoft 365 Security** portal.</span></span> <span data-ttu-id="c0d13-116">이러한 영역에 대해 자세히 읽으려면 링크를 클릭하세요.</span><span class="sxs-lookup"><span data-stu-id="c0d13-116">Click the links to read more about these areas.</span></span>

|<span data-ttu-id="c0d13-117">**영역**</span><span class="sxs-lookup"><span data-stu-id="c0d13-117">**Area**</span></span>  |<span data-ttu-id="c0d13-118">**변경 설명**</span><span class="sxs-lookup"><span data-stu-id="c0d13-118">**Description of change**</span></span>  |
|---------|---------|
| [<span data-ttu-id="c0d13-119">전자 메일 엔터티 페이지</span><span class="sxs-lookup"><span data-stu-id="c0d13-119">Email entity page</span></span>](../office-365-security/mdo-email-entity-page.md) | <span data-ttu-id="c0d13-120">이 페이지는 여러 페이지나 보기에 흩어진 전자 메일 정보를 **통합** 합니다.</span><span class="sxs-lookup"><span data-stu-id="c0d13-120">This page **unifies** email information that had been scattered across different pages or views in the past.</span></span> <span data-ttu-id="c0d13-121">위협과 추세 조사가 *중앙화* 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c0d13-121">Investigating email for threats and trends is *centralized*.</span></span> <span data-ttu-id="c0d13-122">헤더 정보 및 전자 메일 미리 보기는 같은 전자 메일 페이지에서 다른 유용한 전자 메일 관련 정보와 함께 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c0d13-122">Header information and email preview are accessible through the same email page, along with other useful email-related information.</span></span> <span data-ttu-id="c0d13-123">마찬가지로 악성 파일 첨부 파일 또는 URL에 대한 데토네이션 상태는 같은 페이지의 탭에서 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c0d13-123">Likewise, the detonation status for malicious file attachments or URLs can be found on a tab of the same page.</span></span> <span data-ttu-id="c0d13-124">전자 메일 엔터티 페이지를 통해 관리자와 보안 운영 팀이 전자 메일 위협과 해당 상태를 빠르게 파악한 다음 처리를 신속하게 결정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c0d13-124">The Email entity page empowers admins and security operations teams to understand an email threat and its status, fast, and then act quickly determine handling.</span></span>  |
| [<span data-ttu-id="c0d13-125">조사</span><span class="sxs-lookup"><span data-stu-id="c0d13-125">Investigation</span></span>](../office-365-security/office-365-air.md#changes-are-coming-soon-in-your-security-center) | <span data-ttu-id="c0d13-126">[Office 365용 Defender](../office-365-security/office-365-atp.md) 및 [엔드포인트용 Defender](/windows/security/threat-protection/microsoft-defender-atp/automated-investigations)의 AIR 기능을 결합합니다.</span><span class="sxs-lookup"><span data-stu-id="c0d13-126">Brings together AIR capabilities in [Defender for Office 365](../office-365-security/office-365-atp.md) and [Defender for Endpoint](/windows/security/threat-protection/microsoft-defender-atp/automated-investigations).</span></span> <span data-ttu-id="c0d13-127">이러한 업데이트 및 개선 사항을 통해 보안 운영 팀에서는 전자 메일, 공동 작업 콘텐츠, 사용자 계정 및 장치 전체에서 자동 조사 및 수정 작업에 대한 세부 정보를 한 장소에서 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c0d13-127">With these updates and improvements, your security operations team will be able to view details about automated investigations and remediation actions across your email, collaboration content, user accounts, and devices, all in one place.</span></span>  | 
| [<span data-ttu-id="c0d13-128">경고 보기</span><span class="sxs-lookup"><span data-stu-id="c0d13-128">Alert view</span></span>](../../compliance/alert-policies.md) | <span data-ttu-id="c0d13-129">이제 Office 보안 및 규정 준수 센터의 **경고 보기** 플라이아웃 창에 Microsoft 365 보안 센터에 대한 링크가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="c0d13-129">The **View alerts** flyout pane in the Office Security and Compliance center now includes links to the Microsoft 365 security center.</span></span> <span data-ttu-id="c0d13-130">**경고 열기 페이지** 링크를 클릭하면 Microsoft 365 보안 센터가 열립니다.</span><span class="sxs-lookup"><span data-stu-id="c0d13-130">Click on the **Open Alert Page** link and the Microsoft 365 security center opens.</span></span> <span data-ttu-id="c0d13-131">경고 큐에서 Office 365 경고를 클릭하여 **경고보기** 페이지에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c0d13-131">You can access the **View alerts** page by clicking on any Office 365 alert in the Alerts queue.</span></span> |
| [<span data-ttu-id="c0d13-132">공격 시뮬레이션 교육</span><span class="sxs-lookup"><span data-stu-id="c0d13-132">Attack Simulation training</span></span>](../office-365-security/attack-simulation-training-insights.md)   | <span data-ttu-id="c0d13-133">공격 시뮬레이션 교육을 사용하여 조직에서 현실적인 공격 시나리오를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="c0d13-133">Use Attack Simulation training to run realistic attack scenarios in your organization.</span></span> <span data-ttu-id="c0d13-134">이렇게 시뮬레이션된 공격은 실제 공격이 조직에 영향을 미치기 전에 인력을 교육하는 데 도움이 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c0d13-134">These simulated attacks can help train your workforce before a real attack impacts your organization.</span></span> <span data-ttu-id="c0d13-135">공격 시뮬레이션 교육에는 추가 옵션, 향상된 보고서 및 향상된 교육 흐름이 포함되어 공격 시뮬레이션 및 교육 시나리오를 더 쉽게 전달하고 관리할 수 있도록 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="c0d13-135">Attack simulation training includes, more options, enhanced reports, and improved training flows help make your attack simulation and training scenarios easier to deliver and manage.</span></span>  |

<span data-ttu-id="c0d13-136">변경 내용이 없는 영역:</span><span class="sxs-lookup"><span data-stu-id="c0d13-136">No changes to these areas:</span></span>
- [<span data-ttu-id="c0d13-137">탐색기</span><span class="sxs-lookup"><span data-stu-id="c0d13-137">Explorer</span></span>](../office-365-security/threat-explorer.md)
- [<span data-ttu-id="c0d13-138">정책 및 규칙</span><span class="sxs-lookup"><span data-stu-id="c0d13-138">Policies & Rules</span></span>](../../compliance/alert-policies.md)
- [<span data-ttu-id="c0d13-139">캠페인</span><span class="sxs-lookup"><span data-stu-id="c0d13-139">Campaign</span></span>](../office-365-security/campaigns.md)
- [<span data-ttu-id="c0d13-140">제출</span><span class="sxs-lookup"><span data-stu-id="c0d13-140">Submissions</span></span>](../office-365-security/admin-submission.md)
- [<span data-ttu-id="c0d13-141">검토</span><span class="sxs-lookup"><span data-stu-id="c0d13-141">Review</span></span>](./mtp-action-center.md)
- [<span data-ttu-id="c0d13-142">위협 추적기</span><span class="sxs-lookup"><span data-stu-id="c0d13-142">Threat Tracker</span></span>](../office-365-security/threat-trackers.md)

<span data-ttu-id="c0d13-143">또한 이 문서 아래에 있는 **관련 정보** 섹션을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="c0d13-143">Also, check the **Related Information** section at the bottom of this article.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="c0d13-144">Microsoft 365 보안 포털(https://security.microsoft.com)에서 https://securitycenter.windows.com 및 https://protection.office.com보안 기능을 결합합니다.</span><span class="sxs-lookup"><span data-stu-id="c0d13-144">The Microsoft 365 Security portal (https://security.microsoft.com) combines security features in https://securitycenter.windows.com, and https://protection.office.com.</span></span> <span data-ttu-id="c0d13-145">그러나 표시되는 내용은 구독에 따라 다를 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c0d13-145">However, what you see will depend on your subscription.</span></span> <span data-ttu-id="c0d13-146">예를 들어 독립 실행형 구독으로 Office 365용 Microsoft Defender 플랜 1 또는 2만 있는 경우 엔드포인트용 보안과 관련된 기능이 표시되지 않으며 Office용 Defender 플랜 1 고객에게는 위협 분석과 같은 항목이 표시되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c0d13-146">If you only have Microsoft Defender for Office 365 Plan 1 or 2, as standalone subscriptions, for example, you won't see capabilities around Security for Endpoints and Defender for Office Plan 1 customers won't see items such as Threat Analytics.</span></span>

## <a name="microsoft-365-security-center-home-page"></a><span data-ttu-id="c0d13-147">Microsoft 365 보안 센터 홈페이지</span><span class="sxs-lookup"><span data-stu-id="c0d13-147">Microsoft 365 security center Home page</span></span>

<span data-ttu-id="c0d13-148">포털 홈페이지에 표시되는 사항:</span><span class="sxs-lookup"><span data-stu-id="c0d13-148">The Home page of the portal surfaces:</span></span>

- <span data-ttu-id="c0d13-149">보안 점수 등급</span><span class="sxs-lookup"><span data-stu-id="c0d13-149">Secure Score ratings</span></span>
- <span data-ttu-id="c0d13-150">위험에 노출된 사용자 및 장치 수</span><span class="sxs-lookup"><span data-stu-id="c0d13-150">the number of users and devices at risk</span></span>
- <span data-ttu-id="c0d13-151">활성 인시던트 목록</span><span class="sxs-lookup"><span data-stu-id="c0d13-151">active incident lists</span></span>
- <span data-ttu-id="c0d13-152">권한이 있는 OAuth 앱 목록</span><span class="sxs-lookup"><span data-stu-id="c0d13-152">lists of privileged OAuth apps</span></span>
- <span data-ttu-id="c0d13-153">장치 상태 데이터</span><span class="sxs-lookup"><span data-stu-id="c0d13-153">device health data</span></span>
- <span data-ttu-id="c0d13-154">Microsoft 보안 인텔리전스 Twitter 피드의 트윗</span><span class="sxs-lookup"><span data-stu-id="c0d13-154">tweets from Microsoft’s security intelligence twitter feed</span></span>
- <span data-ttu-id="c0d13-155">더 자세한 요약 정보</span><span class="sxs-lookup"><span data-stu-id="c0d13-155">and more summary information</span></span>

<span data-ttu-id="c0d13-156">**안내 받기** 를 사용하여 엔드포인트와 전자 메일 및 공동 작업 페이지를 빠르게 둘러보세요.</span><span class="sxs-lookup"><span data-stu-id="c0d13-156">Using the **Guided tour** you can take a quick tour of Endpoint or Email & collaboration pages.</span></span> <span data-ttu-id="c0d13-157">여기에 표시될 내용은 Office 365용 Defender 및/또는 엔드포인트용 Defender에 대한 라이선스가 있는지 여부에 따라 다를 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c0d13-157">Note that what you see here will depend on if you have license for Defender for Office 365 and/or Defender for Endpoint.</span></span>  

<span data-ttu-id="c0d13-158">또한 비교를 위해 **Office 365 보안 및 규정 준수 센터** 링크도 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c0d13-158">Also included is a link to the **Office 365 Security and Compliance center** for comparison.</span></span> <span data-ttu-id="c0d13-159">마지막 링크는 최근 업데이트를 설명하는 **새로운 기능** 페이지로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="c0d13-159">The last link is to the **What's New** page that describes recent updates.</span></span>

## <a name="improved-capabilities"></a><span data-ttu-id="c0d13-160">향상된 기능</span><span class="sxs-lookup"><span data-stu-id="c0d13-160">Improved capabilities</span></span>

<span data-ttu-id="c0d13-161">왼쪽 탐색 또는 빠른 실행 표시줄이 친숙하게 개선됩니다.</span><span class="sxs-lookup"><span data-stu-id="c0d13-161">The left navigation, or quick launch bar, will look familiar.</span></span> <span data-ttu-id="c0d13-162">그러나 이 보안 센터에는 몇 가지 새 요소와 업데이트된 요소가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c0d13-162">However, there are some new and updated elements in this security center.</span></span>

### <a name="incidents-and-alerts"></a><span data-ttu-id="c0d13-163">인시던트 및 경고</span><span class="sxs-lookup"><span data-stu-id="c0d13-163">Incidents and alerts</span></span>
<span data-ttu-id="c0d13-164">전자 메일, 장치 및 ID의 인시던트 및 경고 관리를 통합합니다.</span><span class="sxs-lookup"><span data-stu-id="c0d13-164">Brings together incident and alert management across your email, devices, and identities.</span></span> <span data-ttu-id="c0d13-165">이제 조사 노드에서 경고를 확인할 수 있으며 경고를 통해 공격을 더욱 폭넓게 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c0d13-165">Alerts are now available under the Investigation node, and help provide a broader view of an attack.</span></span> <span data-ttu-id="c0d13-166">경고 페이지에서는 공격 신호를 결합하여 자세한 내용을 구성하여 경고의 전체 컨텍스트를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="c0d13-166">The alert page provides full context to the alert, by combining attack signals to construct a detailed story.</span></span> <span data-ttu-id="c0d13-167">이전에는 경고가 서로 다른 작업 부하에 지정되었습니다.</span><span class="sxs-lookup"><span data-stu-id="c0d13-167">Previously, alerts were specific to different workloads.</span></span> <span data-ttu-id="c0d13-168">이제 새로운 통합 환경을 통해 여러 작업 부하에서 일관된 경고를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c0d13-168">A new, unified experience now brings together a consistent view of alerts across workloads.</span></span> <span data-ttu-id="c0d13-169">효과적인 작업을 빠르게 심사하고, 조사하고, 진행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c0d13-169">You can quickly triage, investigate, and take effective action.</span></span>

- [<span data-ttu-id="c0d13-170">조사에 대한 자세한 정보</span><span class="sxs-lookup"><span data-stu-id="c0d13-170">Learn more about Investigations</span></span>](incidents-overview.md)
- [<span data-ttu-id="c0d13-171">경고 관리에 대한 자세한 정보</span><span class="sxs-lookup"><span data-stu-id="c0d13-171">Learn more about managing alerts</span></span>](/windows/security/threat-protection/microsoft-defender-atp/review-alerts)

![경고 및 작업 빠른 실행 표시줄](../../media/converge-1-alerts-and-actions.png)


### <a name="hunting"></a><span data-ttu-id="c0d13-173">헌팅</span><span class="sxs-lookup"><span data-stu-id="c0d13-173">Hunting</span></span>
<span data-ttu-id="c0d13-174">[고급 헌팅 쿼리](advanced-hunting-overview.md)를 사용하여 엔드포인트, Office 365 사서함 등에서의 위협, 맬웨어 및 악의적인 활동을 사전에 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="c0d13-174">Proactively search for threats, malware, and malicious activity across your endpoints, Office 365 mailboxes, and more by using [advanced hunting queries](advanced-hunting-overview.md).</span></span> <span data-ttu-id="c0d13-175">이러한 강력한 쿼리를 사용하여 알려진 위협과 잠재적 위협에 대한 위협 표시기 및 엔터티를 찾고 검토할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c0d13-175">These powerful queries can be used to  locate and review threat indicators and entities for both known and potential threats.</span></span>

<span data-ttu-id="c0d13-176">고급 헌팅 쿼리를 통해 만든 [사용자 지정 검색 규칙](/windows/security/threat-protection/microsoft-defender-atp/custom-detection-rules)은 위반 활동과 잘못 구성된 장치를 나타내는 이벤트를 사전 예방적으로 조사하는 데 도움이 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c0d13-176">[Custom detection rules](/windows/security/threat-protection/microsoft-defender-atp/custom-detection-rules)  can be built from advanced hunting queries to help you proactively watch for events that might be indicative of breach activity and misconfigured devices.</span></span>

### <a name="action-center"></a><span data-ttu-id="c0d13-177">작업 센터</span><span class="sxs-lookup"><span data-stu-id="c0d13-177">Action center</span></span>

<span data-ttu-id="c0d13-178">작업 센터에서는 자동화된 조사 및 응답 기능으로 만든 조사가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="c0d13-178">Action center shows you the investigations created by automated investigation and response capabilities.</span></span> <span data-ttu-id="c0d13-179">Microsoft 365 Defender의 자동화된 자동 복구에서 특정 이벤트에 자동으로 응답하여 보안 팀을 도울 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c0d13-179">This automated, self-healing in Microsoft 365 Defender can help security teams by automatically responding to specific events.</span></span>

[<span data-ttu-id="c0d13-180">알림 센터에 대한 자세한 정보 알아보기</span><span class="sxs-lookup"><span data-stu-id="c0d13-180">Learn more about Action Center</span></span>](mtp-action-center.md)

#### <a name="threat-analytics"></a><span data-ttu-id="c0d13-181">위협 분석</span><span class="sxs-lookup"><span data-stu-id="c0d13-181">Threat Analytics</span></span>
<span data-ttu-id="c0d13-182">전문적인 Microsoft 보안 연구원으로부터 위협 인텔리전스를 받을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c0d13-182">Get threat intelligence from expert Microsoft security researchers.</span></span> <span data-ttu-id="c0d13-183">위협 분석은 새로운 위협에 직면할 때 보안 팀이 더 효율적으로 대처할 수 있도록 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="c0d13-183">Threat Analytics helps security teams be more efficient when facing emerging threats.</span></span> <span data-ttu-id="c0d13-184">위협 분석의 포함 항목:</span><span class="sxs-lookup"><span data-stu-id="c0d13-184">Threat Analytics includes:</span></span>

- <span data-ttu-id="c0d13-185">Office 365용 Microsoft Defender의 전자 메일 관련 감지 및 완화.</span><span class="sxs-lookup"><span data-stu-id="c0d13-185">Email-related detections and mitigations from Microsoft Defender for Office 365.</span></span> <span data-ttu-id="c0d13-186">이 외에도 엔드포인트용 Microsoft Defender에서 이미 사용 가능한 엔드포인트 데이터도 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c0d13-186">This is in addition to the endpoint data already available from Microsoft Defender for Endpoint.</span></span>
- <span data-ttu-id="c0d13-187">위협과 관련된 인시던트 보기.</span><span class="sxs-lookup"><span data-stu-id="c0d13-187">Incidents view related to the threats.</span></span> 
- <span data-ttu-id="c0d13-188">보고서에서 실행 가능한 정보를 빠르게 식별하고 사용할 수 있는 향상된 환경.</span><span class="sxs-lookup"><span data-stu-id="c0d13-188">Enhanced experience for quickly identifying and using actionable information in the reports.</span></span> <span data-ttu-id="c0d13-189">Microsoft 365 보안 센터의 왼쪽 위 탐색 표시줄에서 또는 조직의 가장 큰 위협을 표시하는 전용 대시보드 카드에서 위협 분석에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c0d13-189">You can access Threat analytics either from the upper left navigation bar in the Microsoft 365 security center, or from a dedicated dashboard card that shows the top threats for your organization.</span></span> 

<span data-ttu-id="c0d13-190">[위협 분석을 통해 새로운 위협을 추적 및 대처](./threat-analytics.md)하는 방법에 대해 자세히 알아보기</span><span class="sxs-lookup"><span data-stu-id="c0d13-190">Learn more about how to [track and respond to emerging threats with threat analytics](./threat-analytics.md)</span></span>

### <a name="email--collaboration"></a><span data-ttu-id="c0d13-191">전자 메일 및 공동 작업</span><span class="sxs-lookup"><span data-stu-id="c0d13-191">Email & collaboration</span></span>

<span data-ttu-id="c0d13-192">사용자의 전자 메일 위협을 추적 및 조사, 캠페인 추적 등.</span><span class="sxs-lookup"><span data-stu-id="c0d13-192">Track and investigate threats to your users' email, track campaigns, and more.</span></span> <span data-ttu-id="c0d13-193">Office 365 보안 및 규정 준수 센터를 사용하는 경우 이 방법이 익숙할 것입니다.</span><span class="sxs-lookup"><span data-stu-id="c0d13-193">If you've used the Office 365 Security and Compliance center, this will be familiar.</span></span>

:::image type="content" source="../../media/converge-3-email-and-collab-new.png" alt-text="Microsoft 365 보안 센터의 왼쪽에 있는 전자 메일 및 공동 작업(또는 MSDO)의 빠른 실행 메뉴입니다.":::

### <a name="access-and-reports"></a><span data-ttu-id="c0d13-195">액세스 및 보고서</span><span class="sxs-lookup"><span data-stu-id="c0d13-195">Access and Reports</span></span>

<span data-ttu-id="c0d13-196">보고서를 보고, 설정을 변경하고, 사용자 역할을 수정합니다.</span><span class="sxs-lookup"><span data-stu-id="c0d13-196">View reports, change your settings, and modify user roles.</span></span>

:::image type="content" source="../../media/converge-4-access-and-reporting-new.png" alt-text="Microsoft 365 보안 센터 사용 권한 및 보고에 대한 빠른 실행 메뉴는 보안 센터의 왼쪽에 있습니다.":::


> [!NOTE]
> <span data-ttu-id="c0d13-198">Office 365용 Defender 사용자의 경우 이제 Microsoft 365 보안 센터: https://security.microsoft.com/threatpolicy에서 도메인키 식별 메일(DKIM) 키를 *관리 및 회전* 하거나 **정책 및 규칙 > 위협 정책 > DKIM** 를 탐색할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c0d13-198">For Defender for Office 365 users, you can now *manage and rotate* DomainKeys Identified Mail (DKIM) keys through the Microsoft 365 security center: https://security.microsoft.com/threatpolicy, or navigate to **Policy & rules > Threat policies > DKIM**.</span></span>

## <a name="advanced-hunting-example-for-microsoft-defender-for-office-365"></a><span data-ttu-id="c0d13-199">Office 365용 Microsoft Defender의 고급 검색 예제</span><span class="sxs-lookup"><span data-stu-id="c0d13-199">Advanced Hunting example for Microsoft Defender for Office 365</span></span>
<span data-ttu-id="c0d13-200">고급 검색을 사용하여 전자 메일 위협 검색을 시작하고 싶으세요?</span><span class="sxs-lookup"><span data-stu-id="c0d13-200">Want to get started searching for email threats using advanced hunting?</span></span> <span data-ttu-id="c0d13-201">다음 방법을 사용해 보세요.</span><span class="sxs-lookup"><span data-stu-id="c0d13-201">Try this:</span></span>

<span data-ttu-id="c0d13-202">[Office 365용 Microsoft Defender](../office-365-security/office-365-atp.md#getting-started) 문서의 [시작](../office-365-security/office-365-atp.md) 섹션에는 다음과 같은 논리적 초기 구성 덩어리가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c0d13-202">The [Getting Started](../office-365-security/office-365-atp.md#getting-started) section of the [Microsoft Defender for Office 365 article](../office-365-security/office-365-atp.md) has logical early configuration chunks that look like this:</span></span>

1. <span data-ttu-id="c0d13-203">이름에 '방지'가 포함된 모든 항목 구성</span><span class="sxs-lookup"><span data-stu-id="c0d13-203">Configure everything with 'anti' in the name.</span></span>
- <span data-ttu-id="c0d13-204">밸웨어 방지</span><span class="sxs-lookup"><span data-stu-id="c0d13-204">anti-malware</span></span>
- <span data-ttu-id="c0d13-205">피싱 방지</span><span class="sxs-lookup"><span data-stu-id="c0d13-205">anti-phishing</span></span>
- <span data-ttu-id="c0d13-206">스팸 방지</span><span class="sxs-lookup"><span data-stu-id="c0d13-206">anti-spam</span></span>
2. <span data-ttu-id="c0d13-207">이름에 '안전한'을 사용하여 모든 항목 설정</span><span class="sxs-lookup"><span data-stu-id="c0d13-207">Set up everything with 'safe' in the name.</span></span>
- <span data-ttu-id="c0d13-208">안전한 링크</span><span class="sxs-lookup"><span data-stu-id="c0d13-208">safe links</span></span>
- <span data-ttu-id="c0d13-209">안전한 첨부 파일</span><span class="sxs-lookup"><span data-stu-id="c0d13-209">safe attachments</span></span>
3. <span data-ttu-id="c0d13-210">작업을 방어할 때 (예:</span><span class="sxs-lookup"><span data-stu-id="c0d13-210">Defend the workloads (ex.</span></span> <span data-ttu-id="c0d13-211">SharePoint Online, OneDrive 및 Teams)</span><span class="sxs-lookup"><span data-stu-id="c0d13-211">SharePoint Online, OneDrive, and Teams)</span></span>
4. <span data-ttu-id="c0d13-212">ZAP로 보호</span><span class="sxs-lookup"><span data-stu-id="c0d13-212">Protect with Zero-Hour auto purge</span></span>

<span data-ttu-id="c0d13-213">[링크](../office-365-security/protect-against-threats.md)를 통해 바로 시작하여 첫날에 구성을 시작하세요.</span><span class="sxs-lookup"><span data-stu-id="c0d13-213">Along with a [link](../office-365-security/protect-against-threats.md) to jump right in and get configuration going on Day 1.</span></span>

<span data-ttu-id="c0d13-214">**시작** 의 마지막 단계는 ZAP라고도 하는 **제로 아워 자동 제거** 를 사용해 사용자를 보호하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="c0d13-214">The last step in **Getting Started** is protecting users with **Zero-Hour auto purge**, also known as ZAP.</span></span> <span data-ttu-id="c0d13-215">배달 후에 의심스러운 메일이나 악의적인 메일에 대한 제로 아워 자동 제거가 성공적이었는지 알아보는 것은 매우 중요할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c0d13-215">Knowing if your efforts to ZAP a suspicious or malicious mail, post-delivery, were successful can be very important.</span></span>

<span data-ttu-id="c0d13-216">Kusto 쿼리 언어로 빠르게 검색하여 문제를 검색할 수 있다는 점은 이러한 두 보안 센터의 수렴한 이점입니다.</span><span class="sxs-lookup"><span data-stu-id="c0d13-216">Quickly navigating to Kusto query language to hunt for issues is an advantage of converging these two security centers.</span></span> <span data-ttu-id="c0d13-217">보안 팀은 [여기](https://security.microsoft.com/advanced-hunting)에서 **헌팅** > **고급 헌팅** 에서 다음 단계를 진행하여 ZAP 누락을 모니터링할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c0d13-217">Security teams can monitor ZAP misses by taking their next steps [here](https://security.microsoft.com/advanced-hunting), under **Hunting** > **Advanced Hunting**.</span></span>

1. <span data-ttu-id="c0d13-218">고급 헌팅 페이지에서 쿼리를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="c0d13-218">On the Advanced Hunting page, click Query.</span></span>
1. <span data-ttu-id="c0d13-219">다음 쿼리를 쿼리 창에 복사합니다.</span><span class="sxs-lookup"><span data-stu-id="c0d13-219">Copy the query below into the query window.</span></span>
1. <span data-ttu-id="c0d13-220">쿼리 실행을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="c0d13-220">Select Run query.</span></span>


```kusto
EmailPostDeliveryEvents 
| where Timestamp > ago(7d)
//List malicious emails that were not zapped successfullyconverge-2-endpoints-new.png
| where ActionType has "ZAP" and ActionResult == "Error"
| project ZapTime = Timestamp, ActionType, NetworkMessageId , RecipientEmailAddress 
//Get logon activity of recipients using RecipientEmailAddress and AccountUpn
| join kind=inner IdentityLogonEvents on $left.RecipientEmailAddress == $right.AccountUpn
| where Timestamp between ((ZapTime-24h) .. (ZapTime+24h))
//Show only pertinent info, such as account name, the app or service, protocol, the target device, and type of logon
| project ZapTime, ActionType, NetworkMessageId , RecipientEmailAddress, AccountUpn, 
LogonTime = Timestamp, AccountDisplayName, Application, Protocol, DeviceName, LogonType
```

:::image type="content" source="../../media/converge-13-advanced-hunt-an-email-zap-new.png" alt-text="(헌팅 아래) 고급 헌팅 페이지의 쿼리 패널 상단에서 쿼리를 선택하고 Kusto 쿼리를 실행해 지난 7일간의 ZAP 작업을 캡처합니다.":::

<span data-ttu-id="c0d13-222">이 쿼리의 데이터는 쿼리 자체 아래에 있는 결과 패널에 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="c0d13-222">The data from this query will appear in the results panel below the query itself.</span></span> <span data-ttu-id="c0d13-223">결과에는 사용자 지정 가능한 결과 집합의 'DeviceName', 'AccountDisplayName', 'ZapTime' 같은 정보가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="c0d13-223">Results include information like 'DeviceName', 'AccountDisplayName', and 'ZapTime' in a customizable result set.</span></span> <span data-ttu-id="c0d13-224">레코드에 대한 결과를 내보낼 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c0d13-224">Results can also be exported for your records.</span></span> <span data-ttu-id="c0d13-225">쿼리가 다시 필요하면 **저장** > **다른 이름으로 저장** 을 선택하고 쿼리 목록, 공유 또는 커뮤니티 쿼리에 쿼리를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="c0d13-225">If the query is one you'll need again, select **Save** > **Save As** and add the query to your list of queries, shared, or community queries.</span></span>

## <a name="related-information"></a><span data-ttu-id="c0d13-226">관련 정보</span><span class="sxs-lookup"><span data-stu-id="c0d13-226">Related information</span></span>
- [<span data-ttu-id="c0d13-227">Microsoft 365 보안 센터의 Office 365용 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="c0d13-227">Microsoft Defender for Office 365 in the Microsoft 365 security center</span></span>](microsoft-365-security-center-mdo.md)
- [<span data-ttu-id="c0d13-228">알림 센터</span><span class="sxs-lookup"><span data-stu-id="c0d13-228">The Action center</span></span>](./mtp-action-center.md)
- [<span data-ttu-id="c0d13-229">전자 메일 및 공동 작업 경고</span><span class="sxs-lookup"><span data-stu-id="c0d13-229">Email & collaboration alerts</span></span>](../../compliance/alert-policies.md#default-alert-policies)
- [<span data-ttu-id="c0d13-230">장치, 전자 메일, 앱 및 ID에 대한 위협 검색</span><span class="sxs-lookup"><span data-stu-id="c0d13-230">Hunt for threats across devices, emails, apps, and identities</span></span>](./advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="c0d13-231">사용자 지정 검색 규칙</span><span class="sxs-lookup"><span data-stu-id="c0d13-231">Custom detection rules</span></span>](/windows/security/threat-protection/microsoft-defender-atp/custom-detection-rules)
- <span data-ttu-id="c0d13-232">[피싱 공격 시뮬레이션 만들기](../office-365-security/attack-simulation-training.md) 및 [직원교육을 위한 페이로드 만들기](../office-365-security/attack-simulation-training-payloads.md)</span><span class="sxs-lookup"><span data-stu-id="c0d13-232">[Create a phishing attack simulation](../office-365-security/attack-simulation-training.md) and [create a payload for training your people](../office-365-security/attack-simulation-training-payloads.md)</span></span>