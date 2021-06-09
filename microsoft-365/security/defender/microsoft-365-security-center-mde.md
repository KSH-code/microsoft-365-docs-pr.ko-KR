---
title: Microsoft Defender for Endpoint in Microsoft 365 Defender
description: Defender에서 변경된 Microsoft Defender 보안 센터 Microsoft 365 자세히 알아보기
keywords: Microsoft 365 Defender, microsoft Defender for Office 365, Endpoint용 Microsoft Defender, MDO, MDE, 보안 포털, Defender 보안 포털 시작
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
ms.openlocfilehash: b43b7c99c6585e8610d34f3c4e5b372fb1c829a2
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/08/2021
ms.locfileid: "52842629"
---
# <a name="microsoft-defender-for-endpoint-in-microsoft-365-defender"></a><span data-ttu-id="f8476-104">Microsoft Defender for Endpoint in Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="f8476-104">Microsoft Defender for Endpoint in Microsoft 365 Defender</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="f8476-105">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="f8476-105">**Applies to:**</span></span>

- [<span data-ttu-id="f8476-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="f8476-106">Microsoft 365 Defender</span></span>](microsoft-365-defender.md)
- [<span data-ttu-id="f8476-107">엔드포인트용 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="f8476-107">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)

## <a name="quick-reference"></a><span data-ttu-id="f8476-108">빠른 참조</span><span class="sxs-lookup"><span data-stu-id="f8476-108">Quick reference</span></span>

<span data-ttu-id="f8476-109">아래 이미지와 아래 표에는 Defender와 Microsoft Defender 보안 센터 탐색 Microsoft 365 나열되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f8476-109">The image and the table below lists the changes in navigation between the Microsoft Defender Security Center and Microsoft 365 Defender.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="f8476-110">![이동한 위치의 이미지](../../media/mde-m3d-security-center.png)</span><span class="sxs-lookup"><span data-stu-id="f8476-110">![Image of what moved to where](../../media/mde-m3d-security-center.png)</span></span>

| <span data-ttu-id="f8476-111">Microsoft Defender 보안 센터</span><span class="sxs-lookup"><span data-stu-id="f8476-111">Microsoft Defender Security Center</span></span> | <span data-ttu-id="f8476-112">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="f8476-112">Microsoft 365 Defender</span></span> |
|---------|---------|
| <span data-ttu-id="f8476-113">대시보드</span><span class="sxs-lookup"><span data-stu-id="f8476-113">Dashboards</span></span> <ul><li><span data-ttu-id="f8476-114">보안 운영</span><span class="sxs-lookup"><span data-stu-id="f8476-114">Security Operations</span></span></li><li><span data-ttu-id="f8476-115">위협 분석</span><span class="sxs-lookup"><span data-stu-id="f8476-115">Threat Analytics</span></span></li></ul>  |<span data-ttu-id="f8476-116">홈</span><span class="sxs-lookup"><span data-stu-id="f8476-116">Home</span></span> <ul><li><span data-ttu-id="f8476-117">위협 분석</span><span class="sxs-lookup"><span data-stu-id="f8476-117">Threat analytics</span></span></li></ul>   |
| <span data-ttu-id="f8476-118">인시던트</span><span class="sxs-lookup"><span data-stu-id="f8476-118">Incidents</span></span> | <span data-ttu-id="f8476-119">인시던트 & 경고</span><span class="sxs-lookup"><span data-stu-id="f8476-119">Incidents & alerts</span></span> |
| <span data-ttu-id="f8476-120">장치 인벤토리</span><span class="sxs-lookup"><span data-stu-id="f8476-120">Device inventory</span></span> | <span data-ttu-id="f8476-121">장치 인벤토리</span><span class="sxs-lookup"><span data-stu-id="f8476-121">Device inventory</span></span> |
| <span data-ttu-id="f8476-122">경고 큐</span><span class="sxs-lookup"><span data-stu-id="f8476-122">Alerts queue</span></span> | <span data-ttu-id="f8476-123">인시던트 & 경고</span><span class="sxs-lookup"><span data-stu-id="f8476-123">Incidents & alerts</span></span> |
| <span data-ttu-id="f8476-124">자동화된 조사</span><span class="sxs-lookup"><span data-stu-id="f8476-124">Automated investigations</span></span> | <span data-ttu-id="f8476-125">작업 센터</span><span class="sxs-lookup"><span data-stu-id="f8476-125">Action center</span></span> |
| <span data-ttu-id="f8476-126">고급 헌팅</span><span class="sxs-lookup"><span data-stu-id="f8476-126">Advanced hunting</span></span> | <span data-ttu-id="f8476-127">헌팅</span><span class="sxs-lookup"><span data-stu-id="f8476-127">Hunting</span></span> |
| <span data-ttu-id="f8476-128">보고서</span><span class="sxs-lookup"><span data-stu-id="f8476-128">Reports</span></span> | <span data-ttu-id="f8476-129">보고서</span><span class="sxs-lookup"><span data-stu-id="f8476-129">Reports</span></span> |
| <span data-ttu-id="f8476-130">파트너 & API</span><span class="sxs-lookup"><span data-stu-id="f8476-130">Partners & APIs</span></span> | <span data-ttu-id="f8476-131">파트너 & API</span><span class="sxs-lookup"><span data-stu-id="f8476-131">Partners & APIs</span></span> |
| <span data-ttu-id="f8476-132">위협 & 취약성 관리</span><span class="sxs-lookup"><span data-stu-id="f8476-132">Threat & Vulnerability Management</span></span> | <span data-ttu-id="f8476-133">취약성 관리</span><span class="sxs-lookup"><span data-stu-id="f8476-133">Vulnerability management</span></span> |
| <span data-ttu-id="f8476-134">평가 및 자습서</span><span class="sxs-lookup"><span data-stu-id="f8476-134">Evaluation and tutorials</span></span> | <span data-ttu-id="f8476-135">평가판 & 자습서</span><span class="sxs-lookup"><span data-stu-id="f8476-135">Evaluation & tutorials</span></span> |
| <span data-ttu-id="f8476-136">구성 관리</span><span class="sxs-lookup"><span data-stu-id="f8476-136">Configuration management</span></span> | <span data-ttu-id="f8476-137">구성 관리</span><span class="sxs-lookup"><span data-stu-id="f8476-137">Configuration management</span></span> |
| <span data-ttu-id="f8476-138">설정</span><span class="sxs-lookup"><span data-stu-id="f8476-138">Settings</span></span> | <span data-ttu-id="f8476-139">설정</span><span class="sxs-lookup"><span data-stu-id="f8476-139">Settings</span></span> | 

<span data-ttu-id="f8476-140">향상된 Microsoft 365 [Defender는](overview-security-center.md) 전자 메일, 공동 작업, ID 및 장치 위협을 보호, 감지, 조사 및 대응하는 보안 [https://security.microsoft.com](https://security.microsoft.com) 기능을 결합합니다.</span><span class="sxs-lookup"><span data-stu-id="f8476-140">The improved [Microsoft 365 Defender](overview-security-center.md) at [https://security.microsoft.com](https://security.microsoft.com) combines security capabilities that protect, detect, investigate, and respond to email, collaboration, identity, and device threats.</span></span> <span data-ttu-id="f8476-141">이를 통해 보안 및 규정 준수 센터를 비롯한 기존 Microsoft Microsoft Defender 보안 센터 기능을 Office 365 & 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f8476-141">This  brings together functionality from existing Microsoft security portals, including Microsoft Defender Security Center and the Office 365 Security & Compliance center.</span></span>

<span data-ttu-id="f8476-142">이 문서의 내용에 익숙한 Microsoft Defender 보안 센터 이 문서는 Microsoft 365 Defender에서 일부 변경 및 개선된 기능을 설명하는 데 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f8476-142">If you're familiar with the Microsoft Defender Security Center, this article helps describe some of the changes and improvements in Microsoft 365 Defender.</span></span> <span data-ttu-id="f8476-143">그러나 인식해야 할 몇 가지 새 요소와 업데이트된 요소가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f8476-143">However there are some new and updated elements to be aware of.</span></span>

<span data-ttu-id="f8476-144">지금까지는 Microsoft Defender 보안 센터 [](/windows/security/threat-protection/microsoft-defender-atp/portal-overview) Microsoft Defender for Endpoint의 홈입니다.</span><span class="sxs-lookup"><span data-stu-id="f8476-144">Historically, the [Microsoft Defender Security Center](/windows/security/threat-protection/microsoft-defender-atp/portal-overview) has been the home for Microsoft Defender for Endpoint.</span></span> <span data-ttu-id="f8476-145">Enterprise 보안 팀은 이를 사용하여 잠재적인 지속적인 위협 활동 또는 데이터 위반에 대한 경고를 모니터링하고 대응하는 데 도움을 주었다.</span><span class="sxs-lookup"><span data-stu-id="f8476-145">Enterprise security teams have used it to monitor and help responding to alerts of potential advanced persistent threat activity or data breaches.</span></span> <span data-ttu-id="f8476-146">포털 수를 줄이기 위해 Microsoft 365 Defender는 Microsoft ID, 데이터, 장치, 앱 및 인프라에서 보안을 모니터링하고 관리하기 위한 홈이 될 것입니다.</span><span class="sxs-lookup"><span data-stu-id="f8476-146">To help reduce the number of portals, Microsoft 365 Defender will be the home for monitoring and managing security across your Microsoft identities, data, devices, apps, and infrastructure.</span></span>

<span data-ttu-id="f8476-147">Microsoft 365 Defender for Endpoint는 Microsoft Defender 보안 센터에서 액세스 권한을 부여하는 동일한 방식으로 [MSSP(관리되는](/windows/security/threat-protection/microsoft-defender-atp/grant-mssp-access) 보안 서비스 공급자)에 대한 액세스 권한을 [부여할 수](mssp-access.md)있도록 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="f8476-147">Microsoft Defender for Endpoint in Microsoft 365 Defender supports [granting access to managed security service providers (MSSPs)](/windows/security/threat-protection/microsoft-defender-atp/grant-mssp-access) in the same way [access is granted in the Microsoft Defender security center](mssp-access.md).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="f8476-148">Defender에 Microsoft 365 표시하는 내용은 현재 구독에 따라 다를 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f8476-148">What you see in Microsoft 365 Defender depends on your current subscriptions.</span></span> <span data-ttu-id="f8476-149">예를 들어 Microsoft Defender for Office 365 라이선스가 없는 경우 전자 메일 & 공동 작업 섹션이 표시되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="f8476-149">For example, if you don't have a license for Microsoft Defender for Office 365, then the Email & Collaboration section will not be shown.</span></span>

> [!Note]
> <span data-ttu-id="f8476-150">Microsoft 365 Defender는 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="f8476-150">Microsoft 365 Defender is not available for:</span></span>
>- <span data-ttu-id="f8476-151">US 정부 커뮤니티 클라우드(GCC)</span><span class="sxs-lookup"><span data-stu-id="f8476-151">US Government Community Cloud (GCC)</span></span>
>- <span data-ttu-id="f8476-152">US 정부 커뮤니티 클라우드 High(GCC High)</span><span class="sxs-lookup"><span data-stu-id="f8476-152">US Government Community Cloud High (GCC High)</span></span>
>- <span data-ttu-id="f8476-153">미 국방부</span><span class="sxs-lookup"><span data-stu-id="f8476-153">US Department of Defense</span></span>
>- <span data-ttu-id="f8476-154">상업용 라이선스가 있는 모든 미국 정부 기관</span><span class="sxs-lookup"><span data-stu-id="f8476-154">All US government institutions with commercial licenses</span></span>

<span data-ttu-id="f8476-155">Defender: Microsoft 365 살펴보아야 할 수 [https://security.microsoft.com](https://security.microsoft.com) 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f8476-155">Take a look at Microsoft 365 Defender: [https://security.microsoft.com](https://security.microsoft.com).</span></span>

<span data-ttu-id="f8476-156">혜택에 대해 자세히 알아보시고, [Microsoft 365 Defender 개요를 참조하세요.](overview-security-center.md)</span><span class="sxs-lookup"><span data-stu-id="f8476-156">Learn more about the benefits: [Overview of Microsoft 365 Defender](overview-security-center.md)</span></span>

## <a name="whats-changed"></a><span data-ttu-id="f8476-157">변경된 기능</span><span class="sxs-lookup"><span data-stu-id="f8476-157">What's changed</span></span>

<span data-ttu-id="f8476-158">이 표에서는 Defender와 Microsoft Defender 보안 센터 Microsoft 365 참조합니다.</span><span class="sxs-lookup"><span data-stu-id="f8476-158">This table is a quick reference of the changes between the Microsoft Defender Security Center and Microsoft 365 Defender.</span></span>

### <a name="alerts-and-actions"></a><span data-ttu-id="f8476-159">경고 및 작업</span><span class="sxs-lookup"><span data-stu-id="f8476-159">Alerts and actions</span></span>

| <span data-ttu-id="f8476-160">영역</span><span class="sxs-lookup"><span data-stu-id="f8476-160">Area</span></span> | <span data-ttu-id="f8476-161">변경 설명</span><span class="sxs-lookup"><span data-stu-id="f8476-161">Description of change</span></span> |
|---------|---------|
| [<span data-ttu-id="f8476-162">인시던트 & 경고</span><span class="sxs-lookup"><span data-stu-id="f8476-162">Incidents & alerts</span></span>](incidents-overview.md)  | <span data-ttu-id="f8476-163">Microsoft 365 Defender에서 모든 끝점, 전자 메일 및 ID에서 인시던트 및 경고를 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f8476-163">In Microsoft 365 Defender, you can manage incidents and alerts across all of your endpoints, email, and identities.</span></span> <span data-ttu-id="f8476-164">관련 이벤트를 보다 쉽게 찾을 수 있도록 환경을 수렴했습니다.</span><span class="sxs-lookup"><span data-stu-id="f8476-164">We've converged the experience to help you find related events more easily.</span></span> <span data-ttu-id="f8476-165">자세한 내용은 인시던트 [개요를 참조하세요.](incidents-overview.md)</span><span class="sxs-lookup"><span data-stu-id="f8476-165">For more information, see [Incidents Overview](incidents-overview.md).</span></span>   |
| [<span data-ttu-id="f8476-166">헌팅</span><span class="sxs-lookup"><span data-stu-id="f8476-166">Hunting</span></span>](advanced-hunting-overview.md)  |  <span data-ttu-id="f8476-167">ID 및 전자 메일 테이블을 포함하도록 끝점용 Microsoft Defender에서 만든 사용자 지정 검색 규칙을 수정하면 자동으로 해당 사용자 지정 Microsoft 365 이동됩니다.</span><span class="sxs-lookup"><span data-stu-id="f8476-167">Modifying custom detection rules created in Microsoft Defender for Endpoint to include identity and email tables automatically moves them to Microsoft 365 Defender.</span></span> <span data-ttu-id="f8476-168">해당 경고는 Defender에 Microsoft 365 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="f8476-168">Their corresponding alerts will also appear in Microsoft 365 Defender.</span></span> <span data-ttu-id="f8476-169">이러한 변경 내용에 대한 자세한 내용은 사용자 지정 검색 규칙 [마이그레이션을 참조합니다.](advanced-hunting-migrate-from-mde.md#migrate-custom-detection-rules)</span><span class="sxs-lookup"><span data-stu-id="f8476-169">For more details about these changes, read [Migrate custom detection rules](advanced-hunting-migrate-from-mde.md#migrate-custom-detection-rules).</span></span> <br><br><span data-ttu-id="f8476-170">고급 `DeviceAlertEvents` 헌팅 표는 Defender에서 사용할 Microsoft 365 없습니다.</span><span class="sxs-lookup"><span data-stu-id="f8476-170">The `DeviceAlertEvents` table for advanced hunting isn't available in Microsoft 365 Defender.</span></span> <span data-ttu-id="f8476-171">Microsoft 365 Defender에서 장치별 경고 정보를 쿼리하려면 및 테이블을 사용하여 다양한 원본 집합의 추가 정보를 `AlertInfo` `AlertEvidence` 수용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f8476-171">To query device-specific alert information in Microsoft 365 Defender, you can use the `AlertInfo` and `AlertEvidence` tables to accommodate even more information from a diverse set of sources.</span></span> <span data-ttu-id="f8476-172">[DeviceAlertEvents](advanced-hunting-migrate-from-mde.md#write-queries-without-devicealertevents)없이 쓰기 쿼리를 수행하여 다음 장치 관련 쿼리를 작성합니다.</span><span class="sxs-lookup"><span data-stu-id="f8476-172">Craft your next device-related query by following [Write queries without DeviceAlertEvents](advanced-hunting-migrate-from-mde.md#write-queries-without-devicealertevents).</span></span>|
|[<span data-ttu-id="f8476-173">작업 센터</span><span class="sxs-lookup"><span data-stu-id="f8476-173">Action center</span></span>](m365d-action-center.md)    | <span data-ttu-id="f8476-174">자동화된 조사 및 수정 조치에 따라 수행된 보류 중인 작업 및 완료된 작업을 나열합니다.</span><span class="sxs-lookup"><span data-stu-id="f8476-174">Lists pending and completed actions that were taken following automated investigations and remediation actions.</span></span> <span data-ttu-id="f8476-175">이전의 알림 센터에는 Microsoft Defender 보안 센터 조치에 대한 보류 중 및 완료된 조치가 나열되어 있으며 자동화된 조사에는 경고 및 상태가 나열되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f8476-175">Formerly, the Action center in the Microsoft Defender Security Center listed pending and completed actions for remediation actions taken on devices only, while Automated investigations listed alerts and status.</span></span> <span data-ttu-id="f8476-176">향상된 Microsoft 365 Defender에서 알림 센터는 전자 메일, 장치 및 사용자 전반에 걸쳐 재구성 작업과 조사를 한 위치에 모습니다.</span><span class="sxs-lookup"><span data-stu-id="f8476-176">In the  improved Microsoft 365 Defender, the Action center brings together remediation actions and investigations across email, devices, and users—all in one location.</span></span>  |
| [<span data-ttu-id="f8476-177">위협 분석</span><span class="sxs-lookup"><span data-stu-id="f8476-177">Threat analytics</span></span>](threat-analytics.md) |  <span data-ttu-id="f8476-178">탐색 모음의 위쪽으로 이동하여 보다 쉽게 검색하고 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f8476-178">Moved to the top of the navigation bar for easier discovery and use.</span></span> <span data-ttu-id="f8476-179">이제 끝점과 전자 메일 및 공동 작업 둘 다에 대한 위협 정보를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="f8476-179">Now includes threat information for both endpoints and email and collaboration.</span></span>    |

### <a name="endpoints"></a><span data-ttu-id="f8476-180">끝점</span><span class="sxs-lookup"><span data-stu-id="f8476-180">Endpoints</span></span>

| <span data-ttu-id="f8476-181">영역</span><span class="sxs-lookup"><span data-stu-id="f8476-181">Area</span></span> | <span data-ttu-id="f8476-182">변경 설명</span><span class="sxs-lookup"><span data-stu-id="f8476-182">Description of change</span></span> |
|---------|---------|
|<span data-ttu-id="f8476-183">검색</span><span class="sxs-lookup"><span data-stu-id="f8476-183">Search</span></span>   |  <span data-ttu-id="f8476-184">제목 대신 끝점용 Microsoft Defender 검색 표시줄이 끝점 섹션에서 이동됩니다.</span><span class="sxs-lookup"><span data-stu-id="f8476-184">Instead of being in the heading, Microsoft Defender for Endpoint search bar is moving under the Endpoints section.</span></span> <span data-ttu-id="f8476-185">장치, 파일, 사용자, URL, IP, 취약성, 소프트웨어 및 권장 사항을 계속 검색할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f8476-185">You can continue to search for devices, files, users, URLs, IPs, vulnerabilities, software, and recommendations.</span></span>  |
|[<span data-ttu-id="f8476-186">Dashboard</span><span class="sxs-lookup"><span data-stu-id="f8476-186">Dashboard</span></span>](/windows/security/threat-protection/microsoft-defender-atp/security-operations-dashboard)   |  <span data-ttu-id="f8476-187">보안 작업 대시보드입니다.</span><span class="sxs-lookup"><span data-stu-id="f8476-187">This is your security operations dashboard.</span></span> <span data-ttu-id="f8476-188">트리거된 활성 경고 수, 위험에 노출된 장치, 위험 상태의 사용자 및 경고, 장치 및 사용자에 대한 심각도 수준에 대한 개요를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="f8476-188">See an overview of how many active alerts were triggered, which devices are at risk, which users are at risk, and severity level for alerts, devices, and users.</span></span> <span data-ttu-id="f8476-189">또한 센서 문제가 있는 장치, 전반적인 서비스 상태 및 해결되지 않은 경고가 감지된 방법을 볼 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f8476-189">You can also see if any devices have sensor issues, your overall service health, and how any unresolved alerts were detected.</span></span> |
|<span data-ttu-id="f8476-190">장치 인벤토리</span><span class="sxs-lookup"><span data-stu-id="f8476-190">Device inventory</span></span> | <span data-ttu-id="f8476-191">변경 내용이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="f8476-191">No changes.</span></span> |
|[<span data-ttu-id="f8476-192">취약성 관리</span><span class="sxs-lookup"><span data-stu-id="f8476-192">Vulnerability management</span></span>](/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt)    |    <span data-ttu-id="f8476-193">이름이 탐색 창에 맞게 단축됩니다.</span><span class="sxs-lookup"><span data-stu-id="f8476-193">Name was shortened to fit in the navigation pane.</span></span> <span data-ttu-id="f8476-194">이 섹션은 모든 페이지가 위협 및 취약성 관리 섹션과 동일합니다.</span><span class="sxs-lookup"><span data-stu-id="f8476-194">It's the same as the threat and vulnerability management section, with all the pages underneath.</span></span>     |
| <span data-ttu-id="f8476-195">파트너 및 API</span><span class="sxs-lookup"><span data-stu-id="f8476-195">Partners and APIs</span></span> | <span data-ttu-id="f8476-196">변경 내용이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="f8476-196">No changes.</span></span> |
| <span data-ttu-id="f8476-197">평가판 & 자습서</span><span class="sxs-lookup"><span data-stu-id="f8476-197">Evaluations & tutorials</span></span>    |     <span data-ttu-id="f8476-198">새로운 테스트 및 학습 기능.</span><span class="sxs-lookup"><span data-stu-id="f8476-198">New testing and learning capabilities.</span></span>     |
| <span data-ttu-id="f8476-199">구성 관리</span><span class="sxs-lookup"><span data-stu-id="f8476-199">Configuration management</span></span>   |  <span data-ttu-id="f8476-200">변경 내용이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="f8476-200">No changes.</span></span>  |

> [!NOTE]
> <span data-ttu-id="f8476-201">**자동 조사 및 수정은** 이제 인시던트의 일부입니다.</span><span class="sxs-lookup"><span data-stu-id="f8476-201">**Automatic investigation and remediation** is now a part of  incidents.</span></span> <span data-ttu-id="f8476-202">인시던트 및 조사 탭에서 **자동화된 조사 및 수정 이벤트를 > 있습니다.**</span><span class="sxs-lookup"><span data-stu-id="f8476-202">You can see Automated  investigation and remediation events in the **Incident > Investigation** tab.</span></span>

> [!TIP]
> <span data-ttu-id="f8476-203">디바이스 검색은 끝점 및 검색에서 > 수행됩니다.</span><span class="sxs-lookup"><span data-stu-id="f8476-203">Device search is done from Endpoints > Search.</span></span>

### <a name="access-and-reporting"></a><span data-ttu-id="f8476-204">액세스 및 보고</span><span class="sxs-lookup"><span data-stu-id="f8476-204">Access and reporting</span></span>

| <span data-ttu-id="f8476-205">영역</span><span class="sxs-lookup"><span data-stu-id="f8476-205">Area</span></span> | <span data-ttu-id="f8476-206">변경 설명</span><span class="sxs-lookup"><span data-stu-id="f8476-206">Description of change</span></span> |
|---------|---------|
| <span data-ttu-id="f8476-207">보고서</span><span class="sxs-lookup"><span data-stu-id="f8476-207">Reports</span></span>  | <span data-ttu-id="f8476-208">위협 방지, 장치 상태 및 규정 & 취약한 장치를 비롯한 엔드포인트 및 전자 메일 공동 작업용 보고서를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="f8476-208">See reports for endpoints and email & collaboration, including Threat protection, Device health and compliance, and Vulnerable devices.</span></span> |
| <span data-ttu-id="f8476-209">상태</span><span class="sxs-lookup"><span data-stu-id="f8476-209">Health</span></span>  |  <span data-ttu-id="f8476-210">현재 Microsoft 365 관리 센터의 "서비스 상태" [페이지로 연결됩니다.](https://admin.microsoft.com/)</span><span class="sxs-lookup"><span data-stu-id="f8476-210">Currently links out to the "Service health" page in the [Microsoft 365 admin center](https://admin.microsoft.com/).</span></span> |
| <span data-ttu-id="f8476-211">설정</span><span class="sxs-lookup"><span data-stu-id="f8476-211">Settings</span></span> |  <span data-ttu-id="f8476-212">Defender, 끝점, 전자 Microsoft 365 메일 &, ID 및 장치 검색에 대한 설정을 관리합니다.</span><span class="sxs-lookup"><span data-stu-id="f8476-212">Manage your settings for Microsoft 365 Defender, Endpoints, Email & collaboration, Identities, and Device discovery.</span></span>   |

## <a name="microsoft-365-security-navigation-and-capabilities"></a><span data-ttu-id="f8476-213">Microsoft 365 탐색 및 기능</span><span class="sxs-lookup"><span data-stu-id="f8476-213">Microsoft 365 security navigation and capabilities</span></span>

<span data-ttu-id="f8476-214">왼쪽 탐색 또는 빠른 실행 표시줄이 친숙하게 개선됩니다.</span><span class="sxs-lookup"><span data-stu-id="f8476-214">The left navigation, or quick launch bar, will look familiar.</span></span> <span data-ttu-id="f8476-215">그러나 이 보안 센터에는 몇 가지 새 요소와 업데이트된 요소가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f8476-215">However, there are some new and updated elements in this security center.</span></span>

### <a name="incidents-and-alerts"></a><span data-ttu-id="f8476-216">인시던트 및 경고</span><span class="sxs-lookup"><span data-stu-id="f8476-216">Incidents and alerts</span></span>

<span data-ttu-id="f8476-217">전자 메일, 장치 및 ID의 인시던트 및 경고 관리를 통합합니다.</span><span class="sxs-lookup"><span data-stu-id="f8476-217">Brings together incident and alert management across your email, devices, and identities.</span></span> <span data-ttu-id="f8476-218">경고 페이지에서는 공격 신호를 결합하여 자세한 스토리를 생성하여 경고에 대한 전체 컨텍스트를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="f8476-218">The alert page provides full context to the alert by combining attack signals to construct a detailed story.</span></span> <span data-ttu-id="f8476-219">이제 새로운 통합 환경을 통해 여러 작업 부하에서 일관된 경고를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f8476-219">A new, unified experience now brings together a consistent view of alerts across workloads.</span></span> <span data-ttu-id="f8476-220">효과적인 작업을 빠르게 심사하고, 조사하고, 진행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f8476-220">You can quickly triage, investigate, and take effective action.</span></span>

- [<span data-ttu-id="f8476-221">인시던트에 대해 자세히 알아보기</span><span class="sxs-lookup"><span data-stu-id="f8476-221">Learn more about incidents</span></span>](incidents-overview.md)
- [<span data-ttu-id="f8476-222">경고 관리에 대한 자세한 정보</span><span class="sxs-lookup"><span data-stu-id="f8476-222">Learn more about managing alerts</span></span>](investigate-alerts.md)

![경고 및 작업 빠른 실행 표시줄](../../media/converge-1-alerts-and-actions.png)

### <a name="hunting"></a><span data-ttu-id="f8476-224">헌팅</span><span class="sxs-lookup"><span data-stu-id="f8476-224">Hunting</span></span>

<span data-ttu-id="f8476-225">[고급 헌팅 쿼리](advanced-hunting-overview.md)를 사용하여 엔드포인트, Office 365 사서함 등에서의 위협, 맬웨어 및 악의적인 활동을 사전에 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="f8476-225">Proactively search for threats, malware, and malicious activity across your endpoints, Office 365 mailboxes, and more by using [advanced hunting queries](advanced-hunting-overview.md).</span></span> <span data-ttu-id="f8476-226">이러한 강력한 쿼리를 사용하여 알려진 위협과 잠재적인 위협에 대한 위협 지표 및 엔터티를 찾고 검토할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f8476-226">These powerful queries can be used to locate and review threat indicators and entities for both known and potential threats.</span></span>

<span data-ttu-id="f8476-227">[고급 헌팅](custom-detection-rules.md) 쿼리를 통해 사용자 지정 검색 규칙을 구축하면 위반 활동 및 잘못 구성된 장치를 표시하는 이벤트를 사전 예방적으로 감시할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f8476-227">[Custom detection rules](custom-detection-rules.md) can be built from advanced hunting queries to help you proactively watch for events that might be indicative of breach activity and misconfigured devices.</span></span>


### <a name="action-center"></a><span data-ttu-id="f8476-228">작업 센터</span><span class="sxs-lookup"><span data-stu-id="f8476-228">Action center</span></span>

<span data-ttu-id="f8476-229">작업 센터에서는 자동화된 조사 및 응답 기능으로 만든 조사가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="f8476-229">Action center shows you the investigations created by automated investigation and response capabilities.</span></span> <span data-ttu-id="f8476-230">Microsoft 365 Defender의 자동화된 자동 복구에서 특정 이벤트에 자동으로 응답하여 보안 팀을 도울 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f8476-230">This automated, self-healing in Microsoft 365 Defender can help security teams by automatically responding to specific events.</span></span>

<span data-ttu-id="f8476-231">[자세한 내용은 Action Center를 통해 자세히 알아보실 수 있습니다.](m365d-action-center.md)</span><span class="sxs-lookup"><span data-stu-id="f8476-231">[Learn more about the Action center](m365d-action-center.md).</span></span>

### <a name="threat-analytics"></a><span data-ttu-id="f8476-232">위협 분석</span><span class="sxs-lookup"><span data-stu-id="f8476-232">Threat Analytics</span></span>

<span data-ttu-id="f8476-233">전문적인 Microsoft 보안 연구원으로부터 위협 인텔리전스를 받을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f8476-233">Get threat intelligence from expert Microsoft security researchers.</span></span> <span data-ttu-id="f8476-234">위협 분석은 새로운 위협에 직면할 때 보안 팀이 더 효율적으로 대처할 수 있도록 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="f8476-234">Threat Analytics helps security teams be more efficient when facing emerging threats.</span></span> <span data-ttu-id="f8476-235">위협 분석의 포함 항목:</span><span class="sxs-lookup"><span data-stu-id="f8476-235">Threat Analytics includes:</span></span>

- <span data-ttu-id="f8476-236">Office 365용 Microsoft Defender의 전자 메일 관련 감지 및 완화.</span><span class="sxs-lookup"><span data-stu-id="f8476-236">Email-related detections and mitigations from Microsoft Defender for Office 365.</span></span> <span data-ttu-id="f8476-237">이 외에도 엔드포인트용 Microsoft Defender에서 이미 사용 가능한 엔드포인트 데이터도 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f8476-237">This is in addition to the endpoint data already available from Microsoft Defender for Endpoint.</span></span>
- <span data-ttu-id="f8476-238">위협과 관련된 인시던트 보기.</span><span class="sxs-lookup"><span data-stu-id="f8476-238">Incidents view related to the threats.</span></span>
- <span data-ttu-id="f8476-239">보고서에서 실행 가능한 정보를 빠르게 식별하고 사용할 수 있는 향상된 환경.</span><span class="sxs-lookup"><span data-stu-id="f8476-239">Enhanced experience for quickly identifying and using actionable information in the reports.</span></span>

<span data-ttu-id="f8476-240">Microsoft 365 Defender의 왼쪽 위 탐색 모음 또는 조직의 최상위 위협을 보여줄 수 있는 전용 대시보드 카드에서 위협 분석에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f8476-240">You can access threat analytics either from the upper left navigation bar in Microsoft 365 Defender, or from a dedicated dashboard card that shows the top threats for your organization.</span></span>

<span data-ttu-id="f8476-241">위협 분석을 사용하여 새로운 위협을 추적하고 [대응하는 방법에 대해 자세히 알아보십시오.](./threat-analytics.md)</span><span class="sxs-lookup"><span data-stu-id="f8476-241">Learn more about how to [track and respond to emerging threats with threat analytics](./threat-analytics.md).</span></span>

### <a name="endpoints-section"></a><span data-ttu-id="f8476-242">Endpoints 섹션</span><span class="sxs-lookup"><span data-stu-id="f8476-242">Endpoints section</span></span>

<span data-ttu-id="f8476-243">조직의 끝점 보안을 보고 관리합니다.</span><span class="sxs-lookup"><span data-stu-id="f8476-243">View and manage the security of endpoints in your organization.</span></span> <span data-ttu-id="f8476-244">해당 응용 Microsoft Defender 보안 센터 익숙해 보이게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f8476-244">If you've used the Microsoft Defender Security Center, it will look familiar.</span></span>

![끝점 빠른 실행 표시줄](../../media/converge-2-endpoints.png)

### <a name="access-and-reports"></a><span data-ttu-id="f8476-246">액세스 및 보고서</span><span class="sxs-lookup"><span data-stu-id="f8476-246">Access and reports</span></span>

<span data-ttu-id="f8476-247">보고서를 보고, 설정을 변경하고, 사용자 역할을 수정합니다.</span><span class="sxs-lookup"><span data-stu-id="f8476-247">View reports, change your settings, and modify user roles.</span></span>

![액세스 및 보고 빠른 시작 표시줄](../../media/converge-4-access-and-reporting-new.png)

### <a name="siem-api-connections"></a><span data-ttu-id="f8476-249">SIEM API 연결</span><span class="sxs-lookup"><span data-stu-id="f8476-249">SIEM API connections</span></span>

<span data-ttu-id="f8476-250">Endpoint [SIEM API용 Defender를](../defender-endpoint/enable-siem-integration.md)사용하는 경우 계속 진행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f8476-250">If you use the [Defender for Endpoint SIEM API](../defender-endpoint/enable-siem-integration.md), you can continue to do so.</span></span> <span data-ttu-id="f8476-251">API 페이로드에 경고 페이지 또는 보안 포털의 인시던트 페이지를 Microsoft 365 추가했습니다.</span><span class="sxs-lookup"><span data-stu-id="f8476-251">We’ve added new links on the API payload that point to the alert page or the incident page in the Microsoft 365 security portal.</span></span> <span data-ttu-id="f8476-252">새 API 필드에는 LinkToMTP 및 IncidentLinkToMTP가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="f8476-252">New API fields include LinkToMTP and IncidentLinkToMTP.</span></span> <span data-ttu-id="f8476-253">자세한 내용은 [Endpoint용 Microsoft Defender에서 Microsoft Defender로](./microsoft-365-security-mde-redirection.md)계정 리디렉션을 Microsoft 365 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="f8476-253">For more information, see [Redirecting accounts from Microsoft Defender for Endpoint to Microsoft 365 Defender](./microsoft-365-security-mde-redirection.md).</span></span>

### <a name="email-alerts"></a><span data-ttu-id="f8476-254">전자 메일 알림</span><span class="sxs-lookup"><span data-stu-id="f8476-254">Email alerts</span></span>

<span data-ttu-id="f8476-255">Endpoint용 Defender에 대한 전자 메일 알림을 계속 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f8476-255">You can continue to use email alerts for Defender for Endpoint.</span></span> <span data-ttu-id="f8476-256">Microsoft 365 Defender의 경고 페이지 또는 인시던트 페이지를 Microsoft 365 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f8476-256">We've added new links in the emails that point to the alert page or the incident page in Microsoft 365 Defender.</span></span> <span data-ttu-id="f8476-257">자세한 내용은 [Endpoint용 Microsoft Defender에서 Microsoft Defender로](./microsoft-365-security-mde-redirection.md)계정 리디렉션을 Microsoft 365 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="f8476-257">For more information, see [Redirecting accounts from Microsoft Defender for Endpoint to Microsoft 365 Defender](./microsoft-365-security-mde-redirection.md).</span></span>

### <a name="managed-security-service-providers-mssp"></a><span data-ttu-id="f8476-258">MSSP(관리되는 보안 서비스 공급자)</span><span class="sxs-lookup"><span data-stu-id="f8476-258">Managed Security Service Providers (MSSP)</span></span>

<span data-ttu-id="f8476-259">동일한 검색 세션에서 동시에 여러 테넌트에 로그인하는 것은 현재 통합 포털에서 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="f8476-259">Logging in to multiple tenants simultaneously in the same browsing session is currently not supported in the unified portal.</span></span> <span data-ttu-id="f8476-260">문제가 해결될 때까지 이 기능을 유지 관리하기 위해 [이전의 Microsoft Defender for Endpoint](microsoft-365-security-mde-redirection.md#can-i-go-back-to-using-the-former-portal)포털로 되전하여 자동 리디렉션을 옵트아웃(opt-out)할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f8476-260">You can opt-out of the automatic redirection by [reverting to the former Microsoft Defender for Endpoint portal](microsoft-365-security-mde-redirection.md#can-i-go-back-to-using-the-former-portal), to maintain this functionality until the issue is resolved.</span></span>

## <a name="related-information"></a><span data-ttu-id="f8476-261">관련 정보</span><span class="sxs-lookup"><span data-stu-id="f8476-261">Related information</span></span>

- [<span data-ttu-id="f8476-262">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="f8476-262">Microsoft 365 Defender</span></span>](overview-security-center.md)
- [<span data-ttu-id="f8476-263">Microsoft Defender for Endpoint in Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="f8476-263">Microsoft Defender for Endpoint in Microsoft 365 Defender</span></span>](microsoft-365-security-center-mde.md)
- [<span data-ttu-id="f8476-264">끝점용 Microsoft Defender에서 Microsoft 365 리디렉션</span><span class="sxs-lookup"><span data-stu-id="f8476-264">Redirecting accounts from Microsoft Defender for Endpoint to Microsoft 365 Defender</span></span>](microsoft-365-security-mde-redirection.md)
