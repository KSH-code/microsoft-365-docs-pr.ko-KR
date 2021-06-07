---
title: Microsoft 365 끝점용 Microsoft Defender
description: 보안 센터에서 Microsoft Defender 보안 센터 변경된 Microsoft 365 정보
keywords: Microsoft 365 보안 센터, microsoft Defender for Office 365, Endpoint용 Microsoft Defender, MDO, MDE, 단일 창, 수렴형 포털, 보안 포털, Defender 보안 포털
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
localization_priority: Normal
f1.keywords:
- NOCSH
ms.author: dansimp
author: dansimp
manager: dansimp
ms.date: 04/21/2021
audience: ITPro
ms.topic: article
search.appverid:
- MOE150
- MET150
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.openlocfilehash: 487fc87c613d7321e3ae608097d98d2c90f8874e
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/04/2021
ms.locfileid: "52771912"
---
# <a name="microsoft-defender-for-endpoint-in-the-microsoft-365-security-center"></a><span data-ttu-id="faccb-104">Microsoft 365 끝점용 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="faccb-104">Microsoft Defender for Endpoint in the Microsoft 365 security center</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="faccb-105">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="faccb-105">**Applies to:**</span></span>

- [<span data-ttu-id="faccb-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="faccb-106">Microsoft 365 Defender</span></span>](microsoft-365-defender.md)
- [<span data-ttu-id="faccb-107">엔드포인트용 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="faccb-107">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="faccb-108">Office 365용 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="faccb-108">Microsoft Defender for Office 365</span></span>](/microsoft-365/security/office-365-security/defender-for-office-365)

## <a name="quick-reference"></a><span data-ttu-id="faccb-109">빠른 참조</span><span class="sxs-lookup"><span data-stu-id="faccb-109">Quick reference</span></span>

<span data-ttu-id="faccb-110">아래 이미지와 아래 표에는 보안 센터와 Microsoft Defender 보안 센터 탐색의 Microsoft 365 나열되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="faccb-110">The image and the table below lists the changes in navigation between the Microsoft Defender Security Center and the Microsoft 365 security center.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="faccb-111">![이동한 위치의 이미지](../../media/mde-m3d-security-center.png)</span><span class="sxs-lookup"><span data-stu-id="faccb-111">![Image of what moved to where](../../media/mde-m3d-security-center.png)</span></span>

| <span data-ttu-id="faccb-112">Microsoft Defender 보안 센터</span><span class="sxs-lookup"><span data-stu-id="faccb-112">Microsoft Defender Security Center</span></span> | <span data-ttu-id="faccb-113">Microsoft 365 보안 센터</span><span class="sxs-lookup"><span data-stu-id="faccb-113">Microsoft 365 security center</span></span> |
|---------|---------|
| <span data-ttu-id="faccb-114">대시보드</span><span class="sxs-lookup"><span data-stu-id="faccb-114">Dashboards</span></span> <ul><li><span data-ttu-id="faccb-115">보안 운영</span><span class="sxs-lookup"><span data-stu-id="faccb-115">Security Operations</span></span></li><li><span data-ttu-id="faccb-116">위협 분석</span><span class="sxs-lookup"><span data-stu-id="faccb-116">Threat Analytics</span></span></li></ul>  |<span data-ttu-id="faccb-117">홈</span><span class="sxs-lookup"><span data-stu-id="faccb-117">Home</span></span> <ul><li><span data-ttu-id="faccb-118">위협 분석</span><span class="sxs-lookup"><span data-stu-id="faccb-118">Threat analytics</span></span></li></ul>   |
| <span data-ttu-id="faccb-119">인시던트</span><span class="sxs-lookup"><span data-stu-id="faccb-119">Incidents</span></span> | <span data-ttu-id="faccb-120">인시던트 & 경고</span><span class="sxs-lookup"><span data-stu-id="faccb-120">Incidents & alerts</span></span> |
| <span data-ttu-id="faccb-121">장치 인벤토리</span><span class="sxs-lookup"><span data-stu-id="faccb-121">Device inventory</span></span> | <span data-ttu-id="faccb-122">장치 인벤토리</span><span class="sxs-lookup"><span data-stu-id="faccb-122">Device inventory</span></span> |
| <span data-ttu-id="faccb-123">경고 큐</span><span class="sxs-lookup"><span data-stu-id="faccb-123">Alerts queue</span></span> | <span data-ttu-id="faccb-124">인시던트 & 경고</span><span class="sxs-lookup"><span data-stu-id="faccb-124">Incidents & alerts</span></span> |
| <span data-ttu-id="faccb-125">자동화된 조사</span><span class="sxs-lookup"><span data-stu-id="faccb-125">Automated investigations</span></span> | <span data-ttu-id="faccb-126">작업 센터</span><span class="sxs-lookup"><span data-stu-id="faccb-126">Action center</span></span> |
| <span data-ttu-id="faccb-127">고급 헌팅</span><span class="sxs-lookup"><span data-stu-id="faccb-127">Advanced hunting</span></span> | <span data-ttu-id="faccb-128">헌팅</span><span class="sxs-lookup"><span data-stu-id="faccb-128">Hunting</span></span> |
| <span data-ttu-id="faccb-129">보고서</span><span class="sxs-lookup"><span data-stu-id="faccb-129">Reports</span></span> | <span data-ttu-id="faccb-130">보고서</span><span class="sxs-lookup"><span data-stu-id="faccb-130">Reports</span></span> |
| <span data-ttu-id="faccb-131">파트너 & API</span><span class="sxs-lookup"><span data-stu-id="faccb-131">Partners & APIs</span></span> | <span data-ttu-id="faccb-132">파트너 & API</span><span class="sxs-lookup"><span data-stu-id="faccb-132">Partners & APIs</span></span> |
| <span data-ttu-id="faccb-133">위협 & 취약성 관리</span><span class="sxs-lookup"><span data-stu-id="faccb-133">Threat & Vulnerability Management</span></span> | <span data-ttu-id="faccb-134">취약성 관리</span><span class="sxs-lookup"><span data-stu-id="faccb-134">Vulnerability management</span></span> |
| <span data-ttu-id="faccb-135">평가 및 자습서</span><span class="sxs-lookup"><span data-stu-id="faccb-135">Evaluation and tutorials</span></span> | <span data-ttu-id="faccb-136">평가판 & 자습서</span><span class="sxs-lookup"><span data-stu-id="faccb-136">Evaluation & tutorials</span></span> |
| <span data-ttu-id="faccb-137">구성 관리</span><span class="sxs-lookup"><span data-stu-id="faccb-137">Configuration management</span></span> | <span data-ttu-id="faccb-138">구성 관리</span><span class="sxs-lookup"><span data-stu-id="faccb-138">Configuration management</span></span> |
| <span data-ttu-id="faccb-139">설정</span><span class="sxs-lookup"><span data-stu-id="faccb-139">Settings</span></span> | <span data-ttu-id="faccb-140">설정</span><span class="sxs-lookup"><span data-stu-id="faccb-140">Settings</span></span> | 

<span data-ttu-id="faccb-141">향상된 Microsoft 365 보안 센터는 전자 메일, 공동 [작업,](overview-security-center.md) ID 및 장치 위협을 보호, 감지, 조사 및 대응하는 보안 [https://security.microsoft.com](https://security.microsoft.com) 기능을 결합합니다.</span><span class="sxs-lookup"><span data-stu-id="faccb-141">The improved [Microsoft 365 security center](overview-security-center.md) at [https://security.microsoft.com](https://security.microsoft.com) combines security capabilities that protect, detect, investigate, and respond to email, collaboration, identity, and device threats.</span></span> <span data-ttu-id="faccb-142">이 보안 센터는 보안 및 규정 준수 센터를 비롯한 기존 Microsoft Microsoft Defender 보안 센터 기능을 Office 365 & 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="faccb-142">This security center brings together functionality from existing Microsoft security portals, including Microsoft Defender Security Center and the Office 365 Security & Compliance center.</span></span>

<span data-ttu-id="faccb-143">이 문서의 내용에 익숙한 Microsoft Defender 보안 센터 이 문서는 향상된 보안 센터의 일부 변경 및 Microsoft 365 설명하는 데 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="faccb-143">If you're familiar with the Microsoft Defender Security Center, this article helps describe some of the changes and improvements in the improved Microsoft 365 security center.</span></span> <span data-ttu-id="faccb-144">그러나 인식해야 할 몇 가지 새 요소와 업데이트된 요소가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="faccb-144">However there are some new and updated elements to be aware of.</span></span>

<span data-ttu-id="faccb-145">지금까지는 Microsoft Defender 보안 센터 [](/windows/security/threat-protection/microsoft-defender-atp/portal-overview) Microsoft Defender for Endpoint의 홈입니다.</span><span class="sxs-lookup"><span data-stu-id="faccb-145">Historically, the [Microsoft Defender Security Center](/windows/security/threat-protection/microsoft-defender-atp/portal-overview) has been the home for Microsoft Defender for Endpoint.</span></span> <span data-ttu-id="faccb-146">Enterprise 보안 팀은 이를 사용하여 잠재적인 지속적인 위협 활동 또는 데이터 위반에 대한 경고를 모니터링하고 대응하는 데 도움을 주었다.</span><span class="sxs-lookup"><span data-stu-id="faccb-146">Enterprise security teams have used it to monitor and help responding to alerts of potential advanced persistent threat activity or data breaches.</span></span> <span data-ttu-id="faccb-147">포털 수를 줄이기 위해 Microsoft 365 보안 센터는 Microsoft ID, 데이터, 장치, 앱 및 인프라에서 보안을 모니터링하고 관리할 수 있는 홈이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="faccb-147">To help reduce the number of portals, the Microsoft 365 security center will be the home for monitoring and managing security across your Microsoft identities, data, devices, apps, and infrastructure.</span></span>

<span data-ttu-id="faccb-148">Microsoft 365 보안 센터의 끝점용 Microsoft Defender는 Microsoft Defender 보안 센터에서 액세스 권한을 부여하는 동일한 방식으로 [MSSP(관리되는](/windows/security/threat-protection/microsoft-defender-atp/grant-mssp-access) 보안 서비스 공급자)에 대한 액세스 권한을 [부여할 수 있도록 지원합니다.](mssp-access.md)</span><span class="sxs-lookup"><span data-stu-id="faccb-148">Microsoft Defender for Endpoint in the Microsoft 365 security center supports [granting access to managed security service providers (MSSPs)](/windows/security/threat-protection/microsoft-defender-atp/grant-mssp-access) in the same way [access is granted in the Microsoft Defender security center](mssp-access.md).</span></span>


> [!IMPORTANT]
> <span data-ttu-id="faccb-149">보안 센터에 Microsoft 365 내용은 현재 구독에 따라 다를 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="faccb-149">What you see in the Microsoft 365 security center depends on your current subscriptions.</span></span> <span data-ttu-id="faccb-150">예를 들어 Microsoft Defender for Office 365 라이선스가 없는 경우 전자 메일 & 공동 작업 섹션이 표시되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="faccb-150">For example, if you don't have a license for Microsoft Defender for Office 365, then the Email & Collaboration section will not be shown.</span></span>

>[!Note]
><span data-ttu-id="faccb-151">새 통합 포털은 다음에 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="faccb-151">The new unified portal is not available for:</span></span>
>- <span data-ttu-id="faccb-152">US 정부 커뮤니티 클라우드(GCC)</span><span class="sxs-lookup"><span data-stu-id="faccb-152">US Government Community Cloud (GCC)</span></span>
>- <span data-ttu-id="faccb-153">US 정부 커뮤니티 클라우드 High(GCC High)</span><span class="sxs-lookup"><span data-stu-id="faccb-153">US Government Community Cloud High (GCC High)</span></span>
>- <span data-ttu-id="faccb-154">미 국방부</span><span class="sxs-lookup"><span data-stu-id="faccb-154">US Department of Defense</span></span>
>- <span data-ttu-id="faccb-155">상업용 라이선스가 있는 모든 미국 정부 기관</span><span class="sxs-lookup"><span data-stu-id="faccb-155">All US government institutions with commercial licenses</span></span>

<span data-ttu-id="faccb-156">향상된 보안 센터를 Microsoft 365 살펴보아야 [https://security.microsoft.com](https://security.microsoft.com) 합니다.</span><span class="sxs-lookup"><span data-stu-id="faccb-156">Take a look at the improved Microsoft 365 security center: [https://security.microsoft.com](https://security.microsoft.com).</span></span>

<span data-ttu-id="faccb-157">이점에 대한 자세한 정보: [Microsoft 365 보안 센터 개요](overview-security-center.md)</span><span class="sxs-lookup"><span data-stu-id="faccb-157">Learn more about the benefits: [Overview of the Microsoft 365 security center](overview-security-center.md)</span></span>

## <a name="whats-changed"></a><span data-ttu-id="faccb-158">변경된 기능</span><span class="sxs-lookup"><span data-stu-id="faccb-158">What's changed</span></span>

<span data-ttu-id="faccb-159">이 표는 보안 센터와 Microsoft Defender 보안 센터 보안 센터 간의 변경 Microsoft 365 참조입니다.</span><span class="sxs-lookup"><span data-stu-id="faccb-159">This table is a quick reference of the changes between the Microsoft Defender Security Center and the Microsoft 365 security center.</span></span>

### <a name="alerts-and-actions"></a><span data-ttu-id="faccb-160">경고 및 작업</span><span class="sxs-lookup"><span data-stu-id="faccb-160">Alerts and actions</span></span>

| <span data-ttu-id="faccb-161">영역</span><span class="sxs-lookup"><span data-stu-id="faccb-161">Area</span></span> | <span data-ttu-id="faccb-162">변경 설명</span><span class="sxs-lookup"><span data-stu-id="faccb-162">Description of change</span></span> |
|---------|---------|
| [<span data-ttu-id="faccb-163">인시던트 & 경고</span><span class="sxs-lookup"><span data-stu-id="faccb-163">Incidents & alerts</span></span>](incidents-overview.md)  | <span data-ttu-id="faccb-164">보안 Microsoft 365 센터에서 모든 끝점, 전자 메일 및 ID에서 인시던트 및 알림을 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="faccb-164">In the Microsoft 365 security center, you can manage incidents and alerts across all of your endpoints, email, and identities.</span></span> <span data-ttu-id="faccb-165">관련 이벤트를 보다 쉽게 찾을 수 있도록 환경을 수렴했습니다.</span><span class="sxs-lookup"><span data-stu-id="faccb-165">We've converged the experience to help you find related events more easily.</span></span> <span data-ttu-id="faccb-166">자세한 내용은 인시던트 [개요를 참조하세요.](incidents-overview.md)</span><span class="sxs-lookup"><span data-stu-id="faccb-166">For more information, see [Incidents Overview](incidents-overview.md).</span></span>   |
| [<span data-ttu-id="faccb-167">헌팅</span><span class="sxs-lookup"><span data-stu-id="faccb-167">Hunting</span></span>](advanced-hunting-overview.md)  |  <span data-ttu-id="faccb-168">ID 및 전자 메일 테이블을 포함하도록 끝점용 Microsoft Defender에서 만든 사용자 지정 검색 규칙을 수정하면 자동으로 해당 사용자 지정 Microsoft 365 이동됩니다.</span><span class="sxs-lookup"><span data-stu-id="faccb-168">Modifying custom detection rules created in Microsoft Defender for Endpoint to include identity and email tables automatically moves them to Microsoft 365 Defender.</span></span> <span data-ttu-id="faccb-169">해당 경고는 Defender에 Microsoft 365 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="faccb-169">Their corresponding alerts will also appear in Microsoft 365 Defender.</span></span> <span data-ttu-id="faccb-170">이러한 변경 내용에 대한 자세한 내용은 사용자 지정 검색 규칙 [마이그레이션을 참조합니다.](advanced-hunting-migrate-from-mde.md#migrate-custom-detection-rules)</span><span class="sxs-lookup"><span data-stu-id="faccb-170">For more details about these changes, read [Migrate custom detection rules](advanced-hunting-migrate-from-mde.md#migrate-custom-detection-rules).</span></span> <br><br><span data-ttu-id="faccb-171">고급 `DeviceAlertEvents` 헌팅 표는 Defender에서 사용할 Microsoft 365 없습니다.</span><span class="sxs-lookup"><span data-stu-id="faccb-171">The `DeviceAlertEvents` table for advanced hunting isn't available in Microsoft 365 Defender.</span></span> <span data-ttu-id="faccb-172">Microsoft 365 Defender에서 장치별 경고 정보를 쿼리하려면 및 테이블을 사용하여 다양한 원본 집합의 추가 정보를 `AlertInfo` `AlertEvidence` 수용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="faccb-172">To query device-specific alert information in Microsoft 365 Defender, you can use the `AlertInfo` and `AlertEvidence` tables to accommodate even more information from a diverse set of sources.</span></span> <span data-ttu-id="faccb-173">[DeviceAlertEvents](advanced-hunting-migrate-from-mde.md#write-queries-without-devicealertevents)없이 쓰기 쿼리를 수행하여 다음 장치 관련 쿼리를 작성합니다.</span><span class="sxs-lookup"><span data-stu-id="faccb-173">Craft your next device-related query by following [Write queries without DeviceAlertEvents](advanced-hunting-migrate-from-mde.md#write-queries-without-devicealertevents).</span></span>|
|[<span data-ttu-id="faccb-174">작업 센터</span><span class="sxs-lookup"><span data-stu-id="faccb-174">Action center</span></span>](m365d-action-center.md)    | <span data-ttu-id="faccb-175">자동화된 조사 및 수정 조치에 따라 수행된 보류 중인 작업 및 완료된 작업을 나열합니다.</span><span class="sxs-lookup"><span data-stu-id="faccb-175">Lists pending and completed actions that were taken following automated investigations and remediation actions.</span></span> <span data-ttu-id="faccb-176">이전의 알림 센터에는 Microsoft Defender 보안 센터 조치에 대한 보류 중 및 완료된 조치가 나열되어 있으며 자동화된 조사에는 경고 및 상태가 나열되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="faccb-176">Formerly, the Action center in the Microsoft Defender Security Center listed pending and completed actions for remediation actions taken on devices only, while Automated investigations listed alerts and status.</span></span> <span data-ttu-id="faccb-177">향상된 Microsoft 365 보안 센터에서 알림 센터는 전자 메일, 장치 및 사용자 전반에 걸쳐 재구성 작업 및 조사를 한 위치에 모습니다.</span><span class="sxs-lookup"><span data-stu-id="faccb-177">In the  improved Microsoft 365 security center, the Action center brings together remediation actions and investigations across email, devices, and users—all in one location.</span></span>  |
| [<span data-ttu-id="faccb-178">위협 분석</span><span class="sxs-lookup"><span data-stu-id="faccb-178">Threat analytics</span></span>](threat-analytics.md) |  <span data-ttu-id="faccb-179">탐색 모음의 위쪽으로 이동하여 보다 쉽게 검색하고 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="faccb-179">Moved to the top of the navigation bar for easier discovery and use.</span></span> <span data-ttu-id="faccb-180">이제 끝점과 전자 메일 및 공동 작업 둘 다에 대한 위협 정보를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="faccb-180">Now includes threat information for both endpoints and email and collaboration.</span></span>    |

### <a name="endpoints"></a><span data-ttu-id="faccb-181">끝점</span><span class="sxs-lookup"><span data-stu-id="faccb-181">Endpoints</span></span>

| <span data-ttu-id="faccb-182">영역</span><span class="sxs-lookup"><span data-stu-id="faccb-182">Area</span></span> | <span data-ttu-id="faccb-183">변경 설명</span><span class="sxs-lookup"><span data-stu-id="faccb-183">Description of change</span></span> |
|---------|---------|
|<span data-ttu-id="faccb-184">검색</span><span class="sxs-lookup"><span data-stu-id="faccb-184">Search</span></span>   |  <span data-ttu-id="faccb-185">제목 대신 끝점용 Microsoft Defender 검색 표시줄이 끝점 섹션에서 이동됩니다.</span><span class="sxs-lookup"><span data-stu-id="faccb-185">Instead of being in the heading, Microsoft Defender for Endpoint search bar is moving under the Endpoints section.</span></span> <span data-ttu-id="faccb-186">장치, 파일, 사용자, URL, IP, 취약성, 소프트웨어 및 권장 사항을 계속 검색할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="faccb-186">You can continue to search for devices, files, users, URLs, IPs, vulnerabilities, software, and recommendations.</span></span>  |
|[<span data-ttu-id="faccb-187">Dashboard</span><span class="sxs-lookup"><span data-stu-id="faccb-187">Dashboard</span></span>](/windows/security/threat-protection/microsoft-defender-atp/security-operations-dashboard)   |  <span data-ttu-id="faccb-188">보안 작업 대시보드입니다.</span><span class="sxs-lookup"><span data-stu-id="faccb-188">This is your security operations dashboard.</span></span> <span data-ttu-id="faccb-189">트리거된 활성 경고 수, 위험에 노출된 장치, 위험 상태의 사용자 및 경고, 장치 및 사용자에 대한 심각도 수준에 대한 개요를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="faccb-189">See an overview of how many active alerts were triggered, which devices are at risk, which users are at risk, and severity level for alerts, devices, and users.</span></span> <span data-ttu-id="faccb-190">또한 센서 문제가 있는 장치, 전반적인 서비스 상태 및 해결되지 않은 경고가 감지된 방법을 볼 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="faccb-190">You can also see if any devices have sensor issues, your overall service health, and how any unresolved alerts were detected.</span></span> |
|<span data-ttu-id="faccb-191">장치 인벤토리</span><span class="sxs-lookup"><span data-stu-id="faccb-191">Device inventory</span></span> | <span data-ttu-id="faccb-192">변경 내용이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="faccb-192">No changes.</span></span> |
|[<span data-ttu-id="faccb-193">취약성 관리</span><span class="sxs-lookup"><span data-stu-id="faccb-193">Vulnerability management</span></span>](/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt)    |    <span data-ttu-id="faccb-194">이름이 탐색 창에 맞게 단축됩니다.</span><span class="sxs-lookup"><span data-stu-id="faccb-194">Name was shortened to fit in the navigation pane.</span></span> <span data-ttu-id="faccb-195">이 섹션은 모든 페이지가 위협 및 취약성 관리 섹션과 동일합니다.</span><span class="sxs-lookup"><span data-stu-id="faccb-195">It's the same as the threat and vulnerability management section, with all the pages underneath.</span></span>     |
| <span data-ttu-id="faccb-196">파트너 및 API</span><span class="sxs-lookup"><span data-stu-id="faccb-196">Partners and APIs</span></span> | <span data-ttu-id="faccb-197">변경 내용이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="faccb-197">No changes.</span></span> |
| <span data-ttu-id="faccb-198">평가판 & 자습서</span><span class="sxs-lookup"><span data-stu-id="faccb-198">Evaluations & tutorials</span></span>    |     <span data-ttu-id="faccb-199">새로운 테스트 및 학습 기능.</span><span class="sxs-lookup"><span data-stu-id="faccb-199">New testing and learning capabilities.</span></span>     |
| <span data-ttu-id="faccb-200">구성 관리</span><span class="sxs-lookup"><span data-stu-id="faccb-200">Configuration management</span></span>   |  <span data-ttu-id="faccb-201">변경 내용이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="faccb-201">No changes.</span></span>  |

> [!NOTE]
> <span data-ttu-id="faccb-202">**자동 조사 및 수정은** 이제 인시던트의 일부입니다.</span><span class="sxs-lookup"><span data-stu-id="faccb-202">**Automatic investigation and remediation** is now a part of  incidents.</span></span> <span data-ttu-id="faccb-203">인시던트 및 조사 탭에서 **자동화된 조사 및 수정 이벤트를 > 있습니다.**</span><span class="sxs-lookup"><span data-stu-id="faccb-203">You can see Automated  investigation and remediation events in the **Incident > Investigation** tab.</span></span>

> [!TIP]
> <span data-ttu-id="faccb-204">디바이스 검색은 끝점 및 검색에서 > 수행됩니다.</span><span class="sxs-lookup"><span data-stu-id="faccb-204">Device search is done from Endpoints > Search.</span></span>

### <a name="access-and-reporting"></a><span data-ttu-id="faccb-205">액세스 및 보고</span><span class="sxs-lookup"><span data-stu-id="faccb-205">Access and reporting</span></span>

| <span data-ttu-id="faccb-206">영역</span><span class="sxs-lookup"><span data-stu-id="faccb-206">Area</span></span> | <span data-ttu-id="faccb-207">변경 설명</span><span class="sxs-lookup"><span data-stu-id="faccb-207">Description of change</span></span> |
|---------|---------|
| <span data-ttu-id="faccb-208">보고서</span><span class="sxs-lookup"><span data-stu-id="faccb-208">Reports</span></span>  | <span data-ttu-id="faccb-209">위협 방지, 장치 상태 및 규정 & 취약한 장치를 비롯한 엔드포인트 및 전자 메일 공동 작업용 보고서를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="faccb-209">See reports for endpoints and email & collaboration, including Threat protection, Device health and compliance, and Vulnerable devices.</span></span> |
| <span data-ttu-id="faccb-210">상태</span><span class="sxs-lookup"><span data-stu-id="faccb-210">Health</span></span>  |  <span data-ttu-id="faccb-211">현재 Microsoft 365 관리 센터의 "서비스 상태" [페이지로 연결됩니다.](https://admin.microsoft.com/)</span><span class="sxs-lookup"><span data-stu-id="faccb-211">Currently links out to the "Service health" page in the [Microsoft 365 admin center](https://admin.microsoft.com/).</span></span> |
| <span data-ttu-id="faccb-212">설정</span><span class="sxs-lookup"><span data-stu-id="faccb-212">Settings</span></span> |  <span data-ttu-id="faccb-213">보안 센터, Microsoft 365, Microsoft 365, 전자 메일 &, ID 및 장치 검색에 대한 설정을 관리합니다.</span><span class="sxs-lookup"><span data-stu-id="faccb-213">Manage your settings for the Microsoft 365 security center, Microsoft 365 Defender, Endpoints, Email & collaboration, Identities, and Device discovery.</span></span>   |

## <a name="microsoft-365-security-navigation-and-capabilities"></a><span data-ttu-id="faccb-214">Microsoft 365 탐색 및 기능</span><span class="sxs-lookup"><span data-stu-id="faccb-214">Microsoft 365 security navigation and capabilities</span></span>

<span data-ttu-id="faccb-215">왼쪽 탐색 또는 빠른 실행 표시줄이 친숙하게 개선됩니다.</span><span class="sxs-lookup"><span data-stu-id="faccb-215">The left navigation, or quick launch bar, will look familiar.</span></span> <span data-ttu-id="faccb-216">그러나 이 보안 센터에는 몇 가지 새 요소와 업데이트된 요소가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="faccb-216">However, there are some new and updated elements in this security center.</span></span>

### <a name="incidents-and-alerts"></a><span data-ttu-id="faccb-217">인시던트 및 경고</span><span class="sxs-lookup"><span data-stu-id="faccb-217">Incidents and alerts</span></span>

<span data-ttu-id="faccb-218">전자 메일, 장치 및 ID의 인시던트 및 경고 관리를 통합합니다.</span><span class="sxs-lookup"><span data-stu-id="faccb-218">Brings together incident and alert management across your email, devices, and identities.</span></span> <span data-ttu-id="faccb-219">경고 페이지에서는 공격 신호를 결합하여 자세한 스토리를 생성하여 경고에 대한 전체 컨텍스트를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="faccb-219">The alert page provides full context to the alert by combining attack signals to construct a detailed story.</span></span> <span data-ttu-id="faccb-220">이제 새로운 통합 환경을 통해 여러 작업 부하에서 일관된 경고를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="faccb-220">A new, unified experience now brings together a consistent view of alerts across workloads.</span></span> <span data-ttu-id="faccb-221">효과적인 작업을 빠르게 심사하고, 조사하고, 진행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="faccb-221">You can quickly triage, investigate, and take effective action.</span></span>

- [<span data-ttu-id="faccb-222">인시던트에 대해 자세히 알아보기</span><span class="sxs-lookup"><span data-stu-id="faccb-222">Learn more about incidents</span></span>](incidents-overview.md)
- [<span data-ttu-id="faccb-223">경고 관리에 대한 자세한 정보</span><span class="sxs-lookup"><span data-stu-id="faccb-223">Learn more about managing alerts</span></span>](investigate-alerts.md)

![경고 및 작업 빠른 실행 표시줄](../../media/converge-1-alerts-and-actions.png)

### <a name="hunting"></a><span data-ttu-id="faccb-225">헌팅</span><span class="sxs-lookup"><span data-stu-id="faccb-225">Hunting</span></span>

<span data-ttu-id="faccb-226">[고급 헌팅 쿼리](advanced-hunting-overview.md)를 사용하여 엔드포인트, Office 365 사서함 등에서의 위협, 맬웨어 및 악의적인 활동을 사전에 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="faccb-226">Proactively search for threats, malware, and malicious activity across your endpoints, Office 365 mailboxes, and more by using [advanced hunting queries](advanced-hunting-overview.md).</span></span> <span data-ttu-id="faccb-227">이러한 강력한 쿼리를 사용하여 알려진 위협과 잠재적인 위협에 대한 위협 지표 및 엔터티를 찾고 검토할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="faccb-227">These powerful queries can be used to locate and review threat indicators and entities for both known and potential threats.</span></span>

<span data-ttu-id="faccb-228">[고급 헌팅](custom-detection-rules.md) 쿼리를 통해 사용자 지정 검색 규칙을 구축하면 위반 활동 및 잘못 구성된 장치를 표시하는 이벤트를 사전 예방적으로 감시할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="faccb-228">[Custom detection rules](custom-detection-rules.md) can be built from advanced hunting queries to help you proactively watch for events that might be indicative of breach activity and misconfigured devices.</span></span>


### <a name="action-center"></a><span data-ttu-id="faccb-229">작업 센터</span><span class="sxs-lookup"><span data-stu-id="faccb-229">Action center</span></span>

<span data-ttu-id="faccb-230">작업 센터에서는 자동화된 조사 및 응답 기능으로 만든 조사가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="faccb-230">Action center shows you the investigations created by automated investigation and response capabilities.</span></span> <span data-ttu-id="faccb-231">Microsoft 365 Defender의 자동화된 자동 복구에서 특정 이벤트에 자동으로 응답하여 보안 팀을 도울 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="faccb-231">This automated, self-healing in Microsoft 365 Defender can help security teams by automatically responding to specific events.</span></span>

<span data-ttu-id="faccb-232">[자세한 내용은 Action Center를 통해 자세히 알아보실 수 있습니다.](m365d-action-center.md)</span><span class="sxs-lookup"><span data-stu-id="faccb-232">[Learn more about the Action center](m365d-action-center.md).</span></span>

### <a name="threat-analytics"></a><span data-ttu-id="faccb-233">위협 분석</span><span class="sxs-lookup"><span data-stu-id="faccb-233">Threat Analytics</span></span>

<span data-ttu-id="faccb-234">전문적인 Microsoft 보안 연구원으로부터 위협 인텔리전스를 받을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="faccb-234">Get threat intelligence from expert Microsoft security researchers.</span></span> <span data-ttu-id="faccb-235">위협 분석은 새로운 위협에 직면할 때 보안 팀이 더 효율적으로 대처할 수 있도록 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="faccb-235">Threat Analytics helps security teams be more efficient when facing emerging threats.</span></span> <span data-ttu-id="faccb-236">위협 분석의 포함 항목:</span><span class="sxs-lookup"><span data-stu-id="faccb-236">Threat Analytics includes:</span></span>

- <span data-ttu-id="faccb-237">Office 365용 Microsoft Defender의 전자 메일 관련 감지 및 완화.</span><span class="sxs-lookup"><span data-stu-id="faccb-237">Email-related detections and mitigations from Microsoft Defender for Office 365.</span></span> <span data-ttu-id="faccb-238">이 외에도 엔드포인트용 Microsoft Defender에서 이미 사용 가능한 엔드포인트 데이터도 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="faccb-238">This is in addition to the endpoint data already available from Microsoft Defender for Endpoint.</span></span>
- <span data-ttu-id="faccb-239">위협과 관련된 인시던트 보기.</span><span class="sxs-lookup"><span data-stu-id="faccb-239">Incidents view related to the threats.</span></span>
- <span data-ttu-id="faccb-240">보고서에서 실행 가능한 정보를 빠르게 식별하고 사용할 수 있는 향상된 환경.</span><span class="sxs-lookup"><span data-stu-id="faccb-240">Enhanced experience for quickly identifying and using actionable information in the reports.</span></span>

<span data-ttu-id="faccb-241">보안 센터의 왼쪽 위 탐색 모음에서 위협 분석에 액세스할 Microsoft 365 또는 조직의 최상위 위협을 표시하는 전용 대시보드 카드에서 위협 분석에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="faccb-241">You can access threat analytics either from the upper left navigation bar in the Microsoft 365 security center, or from a dedicated dashboard card that shows the top threats for your organization.</span></span>

<span data-ttu-id="faccb-242">위협 분석을 사용하여 새로운 위협을 추적하고 [대응하는 방법에 대해 자세히 알아보십시오.](./threat-analytics.md)</span><span class="sxs-lookup"><span data-stu-id="faccb-242">Learn more about how to [track and respond to emerging threats with threat analytics](./threat-analytics.md).</span></span>

### <a name="endpoints-section"></a><span data-ttu-id="faccb-243">Endpoints 섹션</span><span class="sxs-lookup"><span data-stu-id="faccb-243">Endpoints section</span></span>

<span data-ttu-id="faccb-244">조직의 끝점 보안을 보고 관리합니다.</span><span class="sxs-lookup"><span data-stu-id="faccb-244">View and manage the security of endpoints in your organization.</span></span> <span data-ttu-id="faccb-245">해당 응용 Microsoft Defender 보안 센터 익숙해 보이게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="faccb-245">If you've used the Microsoft Defender Security Center, it will look familiar.</span></span>

![끝점 빠른 실행 표시줄](../../media/converge-2-endpoints.png)

### <a name="access-and-reports"></a><span data-ttu-id="faccb-247">액세스 및 보고서</span><span class="sxs-lookup"><span data-stu-id="faccb-247">Access and reports</span></span>

<span data-ttu-id="faccb-248">보고서를 보고, 설정을 변경하고, 사용자 역할을 수정합니다.</span><span class="sxs-lookup"><span data-stu-id="faccb-248">View reports, change your settings, and modify user roles.</span></span>

![액세스 및 보고 빠른 시작 표시줄](../../media/converge-4-access-and-reporting-new.png)

### <a name="siem-api-connections"></a><span data-ttu-id="faccb-250">SIEM API 연결</span><span class="sxs-lookup"><span data-stu-id="faccb-250">SIEM API connections</span></span>

<span data-ttu-id="faccb-251">Endpoint [SIEM API용 Defender를](../defender-endpoint/enable-siem-integration.md)사용하는 경우 계속 진행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="faccb-251">If you use the [Defender for Endpoint SIEM API](../defender-endpoint/enable-siem-integration.md), you can continue to do so.</span></span> <span data-ttu-id="faccb-252">API 페이로드에 경고 페이지 또는 보안 포털의 인시던트 페이지를 Microsoft 365 추가했습니다.</span><span class="sxs-lookup"><span data-stu-id="faccb-252">We’ve added new links on the API payload that point to the alert page or the incident page in the Microsoft 365 security portal.</span></span> <span data-ttu-id="faccb-253">새 API 필드에는 LinkToMTP 및 IncidentLinkToMTP가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="faccb-253">New API fields include LinkToMTP and IncidentLinkToMTP.</span></span> <span data-ttu-id="faccb-254">자세한 내용은 [끝점용 Microsoft Defender에서](./microsoft-365-security-mde-redirection.md)보안 센터로 계정 Microsoft 365 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="faccb-254">For more information, see [Redirecting accounts from Microsoft Defender for Endpoint to the Microsoft 365 security center](./microsoft-365-security-mde-redirection.md).</span></span>

### <a name="email-alerts"></a><span data-ttu-id="faccb-255">전자 메일 알림</span><span class="sxs-lookup"><span data-stu-id="faccb-255">Email alerts</span></span>

<span data-ttu-id="faccb-256">Endpoint용 Defender에 대한 전자 메일 알림을 계속 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="faccb-256">You can continue to use email alerts for Defender for Endpoint.</span></span> <span data-ttu-id="faccb-257">전자 메일에 보안 센터의 경고 페이지 또는 인시던트 페이지를 Microsoft 365 추가했습니다.</span><span class="sxs-lookup"><span data-stu-id="faccb-257">We've added new links in the emails that point to the alert page or the incident page in the Microsoft 365 security center.</span></span> <span data-ttu-id="faccb-258">자세한 내용은 [끝점용 Microsoft Defender에서](./microsoft-365-security-mde-redirection.md)보안 센터로 계정 Microsoft 365 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="faccb-258">For more information, see [Redirecting accounts from Microsoft Defender for Endpoint to the Microsoft 365 security center](./microsoft-365-security-mde-redirection.md).</span></span>

### <a name="managed-security-service-providers-mssp"></a><span data-ttu-id="faccb-259">MSSP(관리되는 보안 서비스 공급자)</span><span class="sxs-lookup"><span data-stu-id="faccb-259">Managed Security Service Providers (MSSP)</span></span>

<span data-ttu-id="faccb-260">동일한 검색 세션에서 동시에 여러 테넌트에 로그인하는 것은 현재 통합 포털에서 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="faccb-260">Logging in to multiple tenants simultaneously in the same browsing session is currently not supported in the unified portal.</span></span> <span data-ttu-id="faccb-261">문제가 해결될 때까지 이 기능을 유지 관리하기 위해 [이전의 Microsoft Defender for Endpoint](microsoft-365-security-mde-redirection.md#can-i-go-back-to-using-the-former-portal)포털로 되전하여 자동 리디렉션을 옵트아웃(opt-out)할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="faccb-261">You can opt-out of the automatic redirection by [reverting to the former Microsoft Defender for Endpoint portal](microsoft-365-security-mde-redirection.md#can-i-go-back-to-using-the-former-portal), to maintain this functionality until the issue is resolved.</span></span>

## <a name="related-information"></a><span data-ttu-id="faccb-262">관련 정보</span><span class="sxs-lookup"><span data-stu-id="faccb-262">Related information</span></span>

- [<span data-ttu-id="faccb-263">Microsoft 365 보안 센터</span><span class="sxs-lookup"><span data-stu-id="faccb-263">Microsoft 365 security center</span></span>](overview-security-center.md)
- [<span data-ttu-id="faccb-264">Microsoft 365 끝점용 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="faccb-264">Microsoft Defender for Endpoint in the Microsoft 365 security center</span></span>](microsoft-365-security-center-mde.md)
- [<span data-ttu-id="faccb-265">끝점용 Microsoft Defender에서 보안 센터로 Microsoft 365 리디렉션</span><span class="sxs-lookup"><span data-stu-id="faccb-265">Redirecting accounts from Microsoft Defender for Endpoint to the Microsoft 365 security center</span></span>](microsoft-365-security-mde-redirection.md)
