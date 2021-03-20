---
title: Microsoft 365 보안 센터의 끝점용 Microsoft Defender
description: Microsoft Defender 보안 센터에서 Microsoft 365 보안 센터로의 변경 내용에 대해 자세히 알아보기
keywords: Microsoft 365 보안 센터, OATP, MDATP, MDO, MDE, 단일 창, 수렴형 포털, 보안 포털, Defender 보안 포털 시작
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.author: ellevin
author: levinec
manager: dansimp
audience: ITPro
ms.topic: article
search.appverid:
- MOE150
- MET150
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.openlocfilehash: e33a38ae1b5b6bd341d8a274b56c0da44ec1017d
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/19/2021
ms.locfileid: "50910897"
---
# <a name="microsoft-defender-for-endpoint-in-the-microsoft-365-security-center"></a><span data-ttu-id="6af01-104">Microsoft 365 보안 센터의 끝점용 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="6af01-104">Microsoft Defender for Endpoint in the Microsoft 365 security center</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

[!INCLUDE [Prerelease](../includes/prerelease.md)]

<span data-ttu-id="6af01-105">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="6af01-105">**Applies to:**</span></span>

- [<span data-ttu-id="6af01-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="6af01-106">Microsoft 365 Defender</span></span>](./microsoft-threat-protection.md)
- [<span data-ttu-id="6af01-107">엔드포인트용 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="6af01-107">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2146631)
- [<span data-ttu-id="6af01-108">Office 365용 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="6af01-108">Microsoft Defender for Office 365</span></span>](../office-365-security/office-365-atp.md)

<span data-ttu-id="6af01-109">개선된 [Microsoft 365](overview-security-center.md) 보안 센터는 전자 메일, 공동 작업, ID 및 장치 위협을 보호, 감지, 조사 및 대응하는 보안 [https://security.microsoft.com](https://security.microsoft.com) 기능을 결합합니다.</span><span class="sxs-lookup"><span data-stu-id="6af01-109">The improved [Microsoft 365 security center](overview-security-center.md) at [https://security.microsoft.com](https://security.microsoft.com) combines security capabilities that protect, detect, investigate, and respond to email, collaboration, identity, and device threats.</span></span> <span data-ttu-id="6af01-110">이 보안 센터는 Microsoft Defender 보안 센터 및 Office 365 보안 및 준수 센터를 포함하여 기존 Microsoft 보안 포털의 & 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="6af01-110">This security center brings together functionality from existing Microsoft security portals, including Microsoft Defender Security Center and the Office 365 Security & Compliance center.</span></span>

<span data-ttu-id="6af01-111">Microsoft Defender 보안 센터에 익숙한 경우 이 문서는 개선된 Microsoft 365 보안 센터의 일부 변경 및 개선 사항을 설명하는 데 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6af01-111">If you're familiar with the Microsoft Defender Security Center, this article helps describe some of the changes and improvements in the improved Microsoft 365 security center.</span></span> <span data-ttu-id="6af01-112">그러나 인식해야 할 몇 가지 새 요소와 업데이트된 요소가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6af01-112">However there are some new and updated elements to be aware of.</span></span>

<span data-ttu-id="6af01-113">지금까지 Microsoft [Defender 보안](/windows/security/threat-protection/microsoft-defender-atp/portal-overview) 센터는 끝점용 Microsoft Defender의 홈입니다.</span><span class="sxs-lookup"><span data-stu-id="6af01-113">Historically, the [Microsoft Defender Security Center](/windows/security/threat-protection/microsoft-defender-atp/portal-overview) has been the home for Microsoft Defender for Endpoint.</span></span> <span data-ttu-id="6af01-114">엔터프라이즈 보안 팀은 이 기능을 사용하여 잠재적인 고급 영구 위협 활동 또는 데이터 위반에 대한 경고를 모니터링하고 대응하는 데 도움을 주었다.</span><span class="sxs-lookup"><span data-stu-id="6af01-114">Enterprise security teams have used it to monitor and help responding to alerts of potential advanced persistent threat activity or data breaches.</span></span> <span data-ttu-id="6af01-115">포털 수를 줄이기 위해 Microsoft 365 보안 센터는 Microsoft ID, 데이터, 장치, 앱 및 인프라 전체의 보안을 모니터링하고 관리할 수 있는 홈이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6af01-115">To help reduce the number of portals, the Microsoft 365 security center will be the home for monitoring and managing security across your Microsoft identities, data, devices, apps, and infrastructure.</span></span>

<span data-ttu-id="6af01-116">Microsoft 365 보안 센터의 끝점용 Microsoft Defender는 Microsoft Defender 보안 센터에서 액세스 권한을 부여하는 방식으로 관리되는 보안 서비스 [공급자(MSSP)에](/windows/security/threat-protection/microsoft-defender-atp/grant-mssp-access) 대한 액세스 권한을 [부여할 수 있도록 지원합니다.](mssp-access.md)</span><span class="sxs-lookup"><span data-stu-id="6af01-116">Microsoft Defender for Endpoint in the Microsoft 365 security center supports [granting access to managed security service providers (MSSPs)](/windows/security/threat-protection/microsoft-defender-atp/grant-mssp-access) in the same way [access is granted in the Microsoft Defender security center](mssp-access.md).</span></span>


> [!IMPORTANT]
> <span data-ttu-id="6af01-117">Microsoft 365 보안 센터에 표시하는 내용은 현재 구독에 따라 다를 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6af01-117">What you see in the Microsoft 365 security center depends on your current subscriptions.</span></span> <span data-ttu-id="6af01-118">예를 들어 Office 365용 Microsoft Defender 라이선스가 없는 경우 전자 메일 & 공동 작업 섹션이 표시되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="6af01-118">For example, if you don't have a license for Microsoft Defender for Office 365, then the Email & Collaboration section will not be shown.</span></span>

>[!Note]
><span data-ttu-id="6af01-119">새 통합 포털은 다음에 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="6af01-119">The new unified portal is not available for:</span></span>
>- <span data-ttu-id="6af01-120">미국 GCC(정부 커뮤니티 클라우드)</span><span class="sxs-lookup"><span data-stu-id="6af01-120">US Government Community Cloud (GCC)</span></span>
>- <span data-ttu-id="6af01-121">미국 GCC(Government Community Cloud High)</span><span class="sxs-lookup"><span data-stu-id="6af01-121">US Government Community Cloud High (GCC High)</span></span>
>- <span data-ttu-id="6af01-122">미 국방부</span><span class="sxs-lookup"><span data-stu-id="6af01-122">US Department of Defense</span></span>
>- <span data-ttu-id="6af01-123">상업용 라이선스가 있는 모든 미국 정부 기관</span><span class="sxs-lookup"><span data-stu-id="6af01-123">All US government institutions with commercial licenses</span></span>

<span data-ttu-id="6af01-124">향상된 Microsoft 365 보안 센터를 살펴보아야 [https://security.microsoft.com](https://security.microsoft.com) 합니다. .</span><span class="sxs-lookup"><span data-stu-id="6af01-124">Take a look at the improved Microsoft 365 security center: [https://security.microsoft.com](https://security.microsoft.com).</span></span>

<span data-ttu-id="6af01-125">이점에 대해 자세히 알아보시고 Microsoft 365 보안 센터 [개요를 참조하세요.](overview-security-center.md)</span><span class="sxs-lookup"><span data-stu-id="6af01-125">Learn more about the benefits: [Overview of the Microsoft 365 security center](overview-security-center.md)</span></span>

## <a name="whats-changed"></a><span data-ttu-id="6af01-126">변경된 것</span><span class="sxs-lookup"><span data-stu-id="6af01-126">What's changed</span></span>

<span data-ttu-id="6af01-127">이 표는 Microsoft Defender 보안 센터와 Microsoft 365 보안 센터 간의 변경 내용에 대한 빠른 참조입니다.</span><span class="sxs-lookup"><span data-stu-id="6af01-127">This table is a quick reference of the changes between the Microsoft Defender Security Center and the Microsoft 365 security center.</span></span>

### <a name="alerts-and-actions"></a><span data-ttu-id="6af01-128">경고 및 작업</span><span class="sxs-lookup"><span data-stu-id="6af01-128">Alerts and actions</span></span>

|<span data-ttu-id="6af01-129">**영역**</span><span class="sxs-lookup"><span data-stu-id="6af01-129">**Area**</span></span>  |<span data-ttu-id="6af01-130">**변경 설명**</span><span class="sxs-lookup"><span data-stu-id="6af01-130">**Description of change**</span></span>  |
|---------|---------|
| [<span data-ttu-id="6af01-131">인시던트 & 경고</span><span class="sxs-lookup"><span data-stu-id="6af01-131">Incidents & alerts</span></span>](incidents-overview.md)  | <span data-ttu-id="6af01-132">Microsoft 365 보안 센터에서 모든 끝점, 전자 메일 및 ID에서 인시던트 및 알림을 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6af01-132">In the Microsoft 365 security center, you can manage incidents and alerts across all of your endpoints, email, and identities.</span></span> <span data-ttu-id="6af01-133">관련 이벤트를 보다 쉽게 찾을 수 있도록 환경을 수렴했습니다.</span><span class="sxs-lookup"><span data-stu-id="6af01-133">We've converged the experience to help you find related events more easily.</span></span> <span data-ttu-id="6af01-134">자세한 내용은 인시던트 [개요를 참조하세요.](incidents-overview.md)</span><span class="sxs-lookup"><span data-stu-id="6af01-134">For more information, see [Incidents Overview](incidents-overview.md).</span></span>   |
| [<span data-ttu-id="6af01-135">헌팅</span><span class="sxs-lookup"><span data-stu-id="6af01-135">Hunting</span></span>](advanced-hunting-overview.md)  |  <span data-ttu-id="6af01-136">ID 및 전자 메일 테이블을 포함하도록 끝점용 Microsoft Defender에서 만든 사용자 지정 검색 규칙을 수정하면 자동으로 Microsoft 365 Defender로 이동됩니다.</span><span class="sxs-lookup"><span data-stu-id="6af01-136">Modifying custom detection rules created in Microsoft Defender for Endpoint to include identity and email tables automatically moves them to Microsoft 365 Defender.</span></span> <span data-ttu-id="6af01-137">해당 경고는 Microsoft 365 Defender에도 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="6af01-137">Their corresponding alerts will also appear in Microsoft 365 Defender.</span></span> <span data-ttu-id="6af01-138">이러한 변경 내용에 대한 자세한 내용은 사용자 지정 검색 규칙 [마이그레이션을 참조합니다.](advanced-hunting-migrate-from-mdatp.md#migrate-custom-detection-rules)</span><span class="sxs-lookup"><span data-stu-id="6af01-138">For more details about these changes, read [Migrate custom detection rules](advanced-hunting-migrate-from-mdatp.md#migrate-custom-detection-rules).</span></span> <br><br><span data-ttu-id="6af01-139">`DeviceAlertEvents`Microsoft 365 Defender에서는 고급 헌팅 표를 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="6af01-139">The `DeviceAlertEvents` table for advanced hunting isn't available in Microsoft 365 Defender.</span></span> <span data-ttu-id="6af01-140">Microsoft 365 Defender에서 장치별 경고 정보를 쿼리하려면 및 테이블을 사용하여 다양한 소스 집합의 추가 정보를 `AlertInfo` `AlertEvidence` 수용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6af01-140">To query device-specific alert information in Microsoft 365 Defender, you can use the `AlertInfo` and `AlertEvidence` tables to accommodate even more information from a diverse set of sources.</span></span> <span data-ttu-id="6af01-141">[DeviceAlertEvents](advanced-hunting-migrate-from-mdatp.md#write-queries-without-devicealertevents)없이 쓰기 쿼리를 수행하여 다음 장치 관련 쿼리를 작성합니다.</span><span class="sxs-lookup"><span data-stu-id="6af01-141">Craft your next device-related query by following [Write queries without DeviceAlertEvents](advanced-hunting-migrate-from-mdatp.md#write-queries-without-devicealertevents).</span></span>|
|[<span data-ttu-id="6af01-142">Action Center</span><span class="sxs-lookup"><span data-stu-id="6af01-142">Action center</span></span>](mtp-action-center.md)    | <span data-ttu-id="6af01-143">자동화된 조사 및 수정 조치에 따라 수행된 보류 중인 작업 및 완료된 작업을 나열합니다.</span><span class="sxs-lookup"><span data-stu-id="6af01-143">Lists pending and completed actions that were taken following automated investigations and remediation actions.</span></span> <span data-ttu-id="6af01-144">이전의 Microsoft Defender 보안 센터의 알림 센터에는 장치에서만 수행된 수정 작업에 대한 보류 중 및 완료된 작업이 나열되어 있으며, 자동화된 조사에는 경고 및 상태가 나열되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6af01-144">Formerly, the Action center in the Microsoft Defender Security Center listed pending and completed actions for remediation actions taken on devices only, while Automated investigations listed alerts and status.</span></span> <span data-ttu-id="6af01-145">개선된 Microsoft 365 보안 센터에서 알림 센터는 전자 메일, 장치 및 사용자에 대한 수정 작업과 조사를 한 위치에 모습니다.</span><span class="sxs-lookup"><span data-stu-id="6af01-145">In the  improved Microsoft 365 security center, the Action center brings together remediation actions and investigations across email, devices, and users—all in one location.</span></span>  |
| [<span data-ttu-id="6af01-146">위협 분석</span><span class="sxs-lookup"><span data-stu-id="6af01-146">Threat analytics</span></span>](threat-analytics.md) |  <span data-ttu-id="6af01-147">탐색 모음의 위쪽으로 이동하여 보다 쉽게 검색하고 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6af01-147">Moved to the top of the navigation bar for easier discovery and use.</span></span> <span data-ttu-id="6af01-148">이제 끝점과 전자 메일 및 공동 작업 둘 다에 대한 위협 정보를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="6af01-148">Now includes threat information for both endpoints and email and collaboration.</span></span>    |

### <a name="endpoints"></a><span data-ttu-id="6af01-149">끝점</span><span class="sxs-lookup"><span data-stu-id="6af01-149">Endpoints</span></span>

|<span data-ttu-id="6af01-150">**영역**</span><span class="sxs-lookup"><span data-stu-id="6af01-150">**Area**</span></span>  |<span data-ttu-id="6af01-151">**변경 설명**</span><span class="sxs-lookup"><span data-stu-id="6af01-151">**Description of change**</span></span>  |
|---------|---------|
|<span data-ttu-id="6af01-152">검색</span><span class="sxs-lookup"><span data-stu-id="6af01-152">Search</span></span>   |  <span data-ttu-id="6af01-153">제목 대신 끝점용 Microsoft Defender 검색 표시줄이 끝점 섹션에서 이동됩니다.</span><span class="sxs-lookup"><span data-stu-id="6af01-153">Instead of being in the heading, Microsoft Defender for Endpoint search bar is moving under the Endpoints section.</span></span> <span data-ttu-id="6af01-154">장치, 파일, 사용자, URL, IP, 취약성, 소프트웨어 및 권장 사항을 계속 검색할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6af01-154">You can continue to search for devices, files, users, URLs, IPs, vulnerabilities, software, and recommendations.</span></span>  |
|[<span data-ttu-id="6af01-155">Dashboard</span><span class="sxs-lookup"><span data-stu-id="6af01-155">Dashboard</span></span>](/windows/security/threat-protection/microsoft-defender-atp/security-operations-dashboard)   |  <span data-ttu-id="6af01-156">보안 작업 대시보드입니다.</span><span class="sxs-lookup"><span data-stu-id="6af01-156">This is your security operations dashboard.</span></span> <span data-ttu-id="6af01-157">트리거된 활성 경고 수, 위험에 노출된 장치, 위험 상태의 사용자 및 경고, 장치 및 사용자에 대한 심각도 수준에 대한 개요를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="6af01-157">See an overview of how many active alerts were triggered, which devices are at risk, which users are at risk, and severity level for alerts, devices, and users.</span></span> <span data-ttu-id="6af01-158">또한 센서 문제가 있는 장치, 전반적인 서비스 상태 및 해결되지 않은 경고가 감지된 방법을 볼 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6af01-158">You can also see if any devices have sensor issues, your overall service health, and how any unresolved alerts were detected.</span></span> |
|<span data-ttu-id="6af01-159">장치 인벤토리</span><span class="sxs-lookup"><span data-stu-id="6af01-159">Device inventory</span></span> | <span data-ttu-id="6af01-160">변경 내용이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="6af01-160">No changes.</span></span> |
|[<span data-ttu-id="6af01-161">취약성 관리</span><span class="sxs-lookup"><span data-stu-id="6af01-161">Vulnerability management</span></span>](/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt)    |    <span data-ttu-id="6af01-162">이름이 탐색 창에 맞게 단축됩니다.</span><span class="sxs-lookup"><span data-stu-id="6af01-162">Name was shortened to fit in the navigation pane.</span></span> <span data-ttu-id="6af01-163">모든 페이지가 아래에 있는 위협 및 취약성 관리 섹션과 동일합니다.</span><span class="sxs-lookup"><span data-stu-id="6af01-163">It's the same as the threat and vulnerability management section, with all the pages underneath.</span></span>     |
| <span data-ttu-id="6af01-164">파트너 및 API</span><span class="sxs-lookup"><span data-stu-id="6af01-164">Partners and APIs</span></span> | <span data-ttu-id="6af01-165">변경 내용이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="6af01-165">No changes.</span></span> |
| <span data-ttu-id="6af01-166">평가판 & 자습서</span><span class="sxs-lookup"><span data-stu-id="6af01-166">Evaluations & tutorials</span></span>    |     <span data-ttu-id="6af01-167">새로운 테스트 및 학습 기능.</span><span class="sxs-lookup"><span data-stu-id="6af01-167">New testing and learning capabilities.</span></span>     |
| <span data-ttu-id="6af01-168">구성 관리</span><span class="sxs-lookup"><span data-stu-id="6af01-168">Configuration management</span></span>   |  <span data-ttu-id="6af01-169">변경 내용이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="6af01-169">No changes.</span></span>  |

> [!NOTE]
> <span data-ttu-id="6af01-170">**자동 조사 및 수정은** 이제 인시던트의 일부입니다.</span><span class="sxs-lookup"><span data-stu-id="6af01-170">**Automatic investigation and remediation** is now a part of  incidents.</span></span> <span data-ttu-id="6af01-171">인시던트 및 조사 탭에서 **자동화된 조사 및 수정 이벤트를 > 있습니다.**</span><span class="sxs-lookup"><span data-stu-id="6af01-171">You can see Automated  investigation and remediation events in the **Incident > Investigation** tab.</span></span>

### <a name="access-and-reporting"></a><span data-ttu-id="6af01-172">액세스 및 보고</span><span class="sxs-lookup"><span data-stu-id="6af01-172">Access and reporting</span></span>

|<span data-ttu-id="6af01-173">**영역**</span><span class="sxs-lookup"><span data-stu-id="6af01-173">**Area**</span></span>  |<span data-ttu-id="6af01-174">**변경 설명**</span><span class="sxs-lookup"><span data-stu-id="6af01-174">**Description of change**</span></span>  |
|---------|---------|
| <span data-ttu-id="6af01-175">보고서</span><span class="sxs-lookup"><span data-stu-id="6af01-175">Reports</span></span>  | <span data-ttu-id="6af01-176">위협 방지, 장치 상태 및 규정 & 취약한 장치를 비롯한 엔드포인트 및 전자 메일 공동 작업용 보고서를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="6af01-176">See reports for endpoints and email & collaboration, including Threat protection, Device health and compliance, and Vulnerable devices.</span></span> |
| <span data-ttu-id="6af01-177">상태</span><span class="sxs-lookup"><span data-stu-id="6af01-177">Health</span></span>  |  <span data-ttu-id="6af01-178">현재 Microsoft 365 관리 센터의 "서비스 상태" [페이지로 연결됩니다.](https://admin.microsoft.com/)</span><span class="sxs-lookup"><span data-stu-id="6af01-178">Currently links out to the "Service health" page in the [Microsoft 365 admin center](https://admin.microsoft.com/).</span></span> |
| <span data-ttu-id="6af01-179">설정</span><span class="sxs-lookup"><span data-stu-id="6af01-179">Settings</span></span> |  <span data-ttu-id="6af01-180">Microsoft 365 보안 센터, Microsoft 365 Defender, 끝점, 전자 메일 &, ID 및 장치 검색에 대한 설정을 관리합니다.</span><span class="sxs-lookup"><span data-stu-id="6af01-180">Manage your settings for the Microsoft 365 security center, Microsoft 365 Defender, Endpoints, Email & collaboration, Identities, and Device discovery.</span></span>   |

## <a name="microsoft-365-security-navigation-and-capabilities"></a><span data-ttu-id="6af01-181">Microsoft 365 보안 탐색 및 기능</span><span class="sxs-lookup"><span data-stu-id="6af01-181">Microsoft 365 security navigation and capabilities</span></span>

<span data-ttu-id="6af01-182">왼쪽 탐색 또는 빠른 실행 표시줄은 친숙한 모양입니다.</span><span class="sxs-lookup"><span data-stu-id="6af01-182">The left navigation, or quick launch bar, will look familiar.</span></span> <span data-ttu-id="6af01-183">그러나 이 보안 센터에는 몇 가지 신규 및 업데이트된 요소가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6af01-183">However, there are some new and updated elements in this security center.</span></span>

### <a name="incidents-and-alerts"></a><span data-ttu-id="6af01-184">인시던트 및 경고</span><span class="sxs-lookup"><span data-stu-id="6af01-184">Incidents and alerts</span></span>

<span data-ttu-id="6af01-185">전자 메일, 장치 및 ID에 걸쳐 인시던트 및 경고 관리를 함께 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="6af01-185">Brings together incident and alert management across your email, devices, and identities.</span></span> <span data-ttu-id="6af01-186">경고 페이지에서는 공격 신호를 결합하여 자세한 스토리를 생성하여 경고에 대한 전체 컨텍스트를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="6af01-186">The alert page provides full context to the alert by combining attack signals to construct a detailed story.</span></span> <span data-ttu-id="6af01-187">새로운 통합 환경은 이제 워크로드 전반에 걸쳐 일관된 경고 보기를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="6af01-187">A new, unified experience now brings together a consistent view of alerts across workloads.</span></span> <span data-ttu-id="6af01-188">신속하게 조사하고 효과적인 조치를 취할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6af01-188">You can quickly triage, investigate, and take effective action.</span></span>

- [<span data-ttu-id="6af01-189">인시던트에 대해 자세히 알아보기</span><span class="sxs-lookup"><span data-stu-id="6af01-189">Learn more about incidents</span></span>](incidents-overview.md)
- [<span data-ttu-id="6af01-190">경고 관리에 대해 자세히 알아보시다</span><span class="sxs-lookup"><span data-stu-id="6af01-190">Learn more about managing alerts</span></span>](investigate-alerts.md)

![경고 및 작업 빠른 실행 표시줄](../../media/converge-1-alerts-and-actions.png)

### <a name="hunting"></a><span data-ttu-id="6af01-192">헌팅</span><span class="sxs-lookup"><span data-stu-id="6af01-192">Hunting</span></span>

<span data-ttu-id="6af01-193">고급 헌팅 쿼리를 사용하여 끝점, Office 365 사서함 등에서 위협, 맬웨어 및 악의적인 활동을 사전 [검색합니다.](advanced-hunting-overview.md)</span><span class="sxs-lookup"><span data-stu-id="6af01-193">Proactively search for threats, malware, and malicious activity across your endpoints, Office 365 mailboxes, and more by using [advanced hunting queries](advanced-hunting-overview.md).</span></span> <span data-ttu-id="6af01-194">이러한 강력한 쿼리를 사용하여 알려진 위협과 잠재적인 위협에 대한 위협 지표 및 엔터티를 찾고 검토할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6af01-194">These powerful queries can be used to locate and review threat indicators and entities for both known and potential threats.</span></span>

<span data-ttu-id="6af01-195">[고급 헌팅](custom-detection-rules.md) 쿼리를 통해 사용자 지정 검색 규칙을 구축하면 위반 활동 및 잘못 구성된 장치를 표시하는 이벤트를 사전 예방적으로 감시할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6af01-195">[Custom detection rules](custom-detection-rules.md) can be built from advanced hunting queries to help you proactively watch for events that might be indicative of breach activity and misconfigured devices.</span></span>


### <a name="action-center"></a><span data-ttu-id="6af01-196">Action Center</span><span class="sxs-lookup"><span data-stu-id="6af01-196">Action center</span></span>

<span data-ttu-id="6af01-197">관리 센터에는 자동화된 조사 및 응답 기능으로 만든 조사가 표시되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6af01-197">Action center shows you the investigations created by automated investigation and response capabilities.</span></span> <span data-ttu-id="6af01-198">Microsoft 365 Defender의 이 자동 자동 복구는 특정 이벤트에 자동으로 응답하여 보안 팀에 도움이 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6af01-198">This automated, self-healing in Microsoft 365 Defender can help security teams by automatically responding to specific events.</span></span>

[<span data-ttu-id="6af01-199">알림 센터에 대한 자세한 정보 알아보기</span><span class="sxs-lookup"><span data-stu-id="6af01-199">Learn more about the Action center</span></span>](mtp-action-center.md)

### <a name="threat-analytics"></a><span data-ttu-id="6af01-200">위협 분석</span><span class="sxs-lookup"><span data-stu-id="6af01-200">Threat Analytics</span></span>

<span data-ttu-id="6af01-201">전문가 Microsoft 보안 연구자로부터 위협 인텔리전스를 얻습니다.</span><span class="sxs-lookup"><span data-stu-id="6af01-201">Get threat intelligence from expert Microsoft security researchers.</span></span> <span data-ttu-id="6af01-202">위협 분석은 새로운 위협에 직면할 때 보안 팀의 효율성을 향상시킵니다.</span><span class="sxs-lookup"><span data-stu-id="6af01-202">Threat Analytics helps security teams be more efficient when facing emerging threats.</span></span> <span data-ttu-id="6af01-203">위협 분석에는 다음이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="6af01-203">Threat Analytics includes:</span></span>

- <span data-ttu-id="6af01-204">Office 365용 Microsoft Defender의 전자 메일 관련 검색 및 완화</span><span class="sxs-lookup"><span data-stu-id="6af01-204">Email-related detections and mitigations from Microsoft Defender for Office 365.</span></span> <span data-ttu-id="6af01-205">이는 끝점용 Microsoft Defender에서 이미 사용할 수 있는 끝점 데이터 외에 추가됩니다.</span><span class="sxs-lookup"><span data-stu-id="6af01-205">This is in addition to the endpoint data already available from Microsoft Defender for Endpoint.</span></span>
- <span data-ttu-id="6af01-206">인시던트는 위협과 관련된 보기입니다.</span><span class="sxs-lookup"><span data-stu-id="6af01-206">Incidents view related to the threats.</span></span>
- <span data-ttu-id="6af01-207">보고서에서 실행 가능한 정보를 빠르게 식별하고 사용할 수 있는 향상된 환경.</span><span class="sxs-lookup"><span data-stu-id="6af01-207">Enhanced experience for quickly identifying and using actionable information in the reports.</span></span>

<span data-ttu-id="6af01-208">Microsoft 365 보안 센터의 왼쪽 위 탐색 모음 또는 조직의 가장 큰 위협을 표시하는 전용 대시보드 카드에서 위협 분석에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6af01-208">You can access threat analytics either from the upper left navigation bar in the Microsoft 365 security center, or from a dedicated dashboard card that shows the top threats for your organization.</span></span>

<span data-ttu-id="6af01-209">위협 분석을 사용하여 새로운 위협을 추적하고 [대응하는 방법에 대해 자세히 알아보십시오.](./threat-analytics.md)</span><span class="sxs-lookup"><span data-stu-id="6af01-209">Learn more about how to [track and respond to emerging threats with threat analytics](./threat-analytics.md)</span></span>

### <a name="endpoints-section"></a><span data-ttu-id="6af01-210">Endpoints 섹션</span><span class="sxs-lookup"><span data-stu-id="6af01-210">Endpoints section</span></span>

<span data-ttu-id="6af01-211">조직의 끝점 보안을 보고 관리합니다.</span><span class="sxs-lookup"><span data-stu-id="6af01-211">View and manage the security of endpoints in your organization.</span></span> <span data-ttu-id="6af01-212">Microsoft Defender 보안 센터를 사용한 경우 익숙해 보이게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6af01-212">If you've used the Microsoft Defender Security Center, it will look familiar.</span></span>

![끝점 빠른 실행 표시줄](../../media/converge-2-endpoints.png)

### <a name="access-and-reports"></a><span data-ttu-id="6af01-214">액세스 및 보고서</span><span class="sxs-lookup"><span data-stu-id="6af01-214">Access and reports</span></span>

<span data-ttu-id="6af01-215">보고서를 보고, 설정을 변경하고, 사용자 역할을 수정합니다.</span><span class="sxs-lookup"><span data-stu-id="6af01-215">View reports, change your settings, and modify user roles.</span></span>

![액세스 및 보고 빠른 시작 표시줄](../../media/converge-4-access-and-reporting-new.png)

### <a name="siem-api-connections"></a><span data-ttu-id="6af01-217">SIEM API 연결</span><span class="sxs-lookup"><span data-stu-id="6af01-217">SIEM API connections</span></span>

<span data-ttu-id="6af01-218">Endpoint [SIEM API용 Defender를](/windows/security/threat-protection/microsoft-defender-atp/enable-siem-integration.md)사용하는 경우 계속 진행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6af01-218">If you use the [Defender for Endpoint SIEM API](/windows/security/threat-protection/microsoft-defender-atp/enable-siem-integration.md), you can continue to do so.</span></span> <span data-ttu-id="6af01-219">Microsoft 365 보안 포털의 경고 페이지 또는 인시던트 페이지를 지점하는 API 페이로드에 새 링크가 추가되었습니다.</span><span class="sxs-lookup"><span data-stu-id="6af01-219">We’ve added new links on the API payload that point to the alert page or the incident page in the Microsoft 365 security portal.</span></span> <span data-ttu-id="6af01-220">새 API 필드에는 LinkToMTP 및 IncidentLinkToMTP가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="6af01-220">New API fields include LinkToMTP and IncidentLinkToMTP.</span></span> <span data-ttu-id="6af01-221">자세한 내용은 [끝점용 Microsoft Defender에서 Microsoft 365 보안 센터로 계정 리디렉션을 참조하세요.](./microsoft-365-security-mde-redirection.md)</span><span class="sxs-lookup"><span data-stu-id="6af01-221">For more information, see [Redirecting accounts from Microsoft Defender for Endpoint to the Microsoft 365 security center](./microsoft-365-security-mde-redirection.md).</span></span>

### <a name="email-alerts"></a><span data-ttu-id="6af01-222">전자 메일 알림</span><span class="sxs-lookup"><span data-stu-id="6af01-222">Email alerts</span></span>

<span data-ttu-id="6af01-223">Endpoint용 Defender에 대한 전자 메일 알림을 계속 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6af01-223">You can continue to use email alerts for Defender for Endpoint.</span></span> <span data-ttu-id="6af01-224">Microsoft 365 보안 센터의 경고 페이지 또는 인시던트 페이지를 알리는 새 링크가 전자 메일에 추가되었습니다.</span><span class="sxs-lookup"><span data-stu-id="6af01-224">We've added new links in the emails that point to the alert page or the incident page in the Microsoft 365 security center.</span></span> <span data-ttu-id="6af01-225">자세한 내용은 [끝점용 Microsoft Defender에서 Microsoft 365 보안 센터로 계정 리디렉션을 참조하세요.](./microsoft-365-security-mde-redirection.md)</span><span class="sxs-lookup"><span data-stu-id="6af01-225">For more information, see [Redirecting accounts from Microsoft Defender for Endpoint to the Microsoft 365 security center](./microsoft-365-security-mde-redirection.md).</span></span>

## <a name="related-information"></a><span data-ttu-id="6af01-226">관련 정보</span><span class="sxs-lookup"><span data-stu-id="6af01-226">Related information</span></span>

- [<span data-ttu-id="6af01-227">Microsoft 365 보안 센터</span><span class="sxs-lookup"><span data-stu-id="6af01-227">Microsoft 365 security center</span></span>](overview-security-center.md)
- [<span data-ttu-id="6af01-228">Microsoft 365 보안 센터의 끝점용 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="6af01-228">Microsoft Defender for Endpoint in the Microsoft 365 security center</span></span>](microsoft-365-security-center-mde.md)
- [<span data-ttu-id="6af01-229">끝점용 Microsoft Defender에서 Microsoft 365 보안 센터로 계정 리디렉션</span><span class="sxs-lookup"><span data-stu-id="6af01-229">Redirecting accounts from Microsoft Defender for Endpoint to the Microsoft 365 security center</span></span>](microsoft-365-security-mde-redirection.md)