---
title: 공격 시뮬레이션 교육 배포 고려 사항 및 FAQ
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: how-to
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: ''
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.custom:
- seo-marvel-apr2020
description: 관리자는 계획 2 조직용 Microsoft Defender 또는 Microsoft 365 E5 시뮬레이션 및 교육과 관련하여 배포 고려 사항과 Office 365 정보를 배울 수 있습니다.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: f404e2a47756a611135fc70026bf0cce3eec62c4
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/25/2021
ms.locfileid: "51205212"
---
# <a name="attack-simulation-training-deployment-considerations-and-faq"></a><span data-ttu-id="fca17-103">공격 시뮬레이션 교육 배포 고려 사항 및 FAQ</span><span class="sxs-lookup"><span data-stu-id="fca17-103">Attack simulation training deployment considerations and FAQ</span></span>

<span data-ttu-id="fca17-104">공격 시뮬레이션 교육은 이제 일반적으로 [사용할 수 있습니다.](https://techcommunity.microsoft.com/t5/microsoft-security-and/attack-simulation-training-in-microsoft-defender-for-office-365/ba-p/2037291)</span><span class="sxs-lookup"><span data-stu-id="fca17-104">Attack simulation training is now [generally available](https://techcommunity.microsoft.com/t5/microsoft-security-and/attack-simulation-training-in-microsoft-defender-for-office-365/ba-p/2037291).</span></span> <span data-ttu-id="fca17-105">공격 시뮬레이션 교육은 Microsoft 365 E5 또는 Microsoft Defender for Office 365 계획 2 조직이 실제 피싱 페이로드를 통해 강화된 피싱 시뮬레이션을 생성 및 관리할 수 있도록 하여 소셜 엔지니어링 위험을 측정하고 관리할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="fca17-105">Attack simulation training enables Microsoft 365 E5 or Microsoft Defender for Office 365 Plan 2 organizations to measure and manage social engineering risk by allowing the creation and management of phishing simulations that are powered by real-world, de-weaponized phishing payloads.</span></span> <span data-ttu-id="fca17-106">Terranova 보안과 협력하여 제공된 하이퍼 대상 교육은 지식을 개선하고 직원의 행동을 변경하는 데 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="fca17-106">Hyper-targeted training, delivered in partnership with Terranova security, helps improve knowledge and change employee behavior.</span></span>

<span data-ttu-id="fca17-107">공격 시뮬레이션 교육을 시작하는 데 대한 자세한 내용은 공격 시뮬레이션 교육 사용 [시작을 참조하세요.](attack-simulation-training-get-started.md)</span><span class="sxs-lookup"><span data-stu-id="fca17-107">For more information about getting started with Attack simulation training, see [Get started using Attack simulation training](attack-simulation-training-get-started.md).</span></span>

<span data-ttu-id="fca17-108">전체 시뮬레이션 만들기 및 예약 환경은 자유 흐름과 마찰 없이 설계된 반면, 엔터프라이즈 규모에서 시뮬레이션을 실행하려면 계획이 필요한 경우가 종종 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fca17-108">While the whole simulation creation and scheduling experience has been designed to be free-flowing and frictionless, running simulations at an enterprise scale often requires planning.</span></span> <span data-ttu-id="fca17-109">이 문서는 고객이 자체 환경에서 시뮬레이션을 실행할 때 직면하는 특정 문제를 해결할 수 있도록 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="fca17-109">This article helps address specific challenges that we see as our customers run simulations in their own environments.</span></span>

## <a name="issues-with-end-user-experiences"></a><span data-ttu-id="fca17-110">최종 사용자 환경의 문제</span><span class="sxs-lookup"><span data-stu-id="fca17-110">Issues with end user experiences</span></span>

### <a name="phishing-simulation-urls-blocked-by-google-safe-browsing"></a><span data-ttu-id="fca17-111">Google Safe Browsing에서 차단된 피싱 시뮬레이션 URL</span><span class="sxs-lookup"><span data-stu-id="fca17-111">Phishing simulation URLs blocked by Google Safe Browsing</span></span>

<span data-ttu-id="fca17-112">URL 신뢰도 서비스는 공격 시뮬레이션 교육에 사용되는 하나 이상의 URL을 안전하지 않은 것으로 식별할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fca17-112">A URL reputation service might identify one or more of the URLs that are used by Attack simulation training as unsafe.</span></span> <span data-ttu-id="fca17-113">Google Chrome의 Google 안전한 브라우징은 기만 사이트 미리 메시지를 사용하여 시뮬레이션된 피싱 URL **중 일부를 차단합니다.**</span><span class="sxs-lookup"><span data-stu-id="fca17-113">Google Safe Browsing in Google Chrome blocks some of the simulated phishing URLs with a **Deceptive site ahead** message.</span></span> <span data-ttu-id="fca17-114">항상 시뮬레이션 URL을 허용하기 위해 많은 URL 신뢰도 공급업체와 협력하고 있습니다. 그러나 항상 전체 범위가 있는 것은 아니며,</span><span class="sxs-lookup"><span data-stu-id="fca17-114">While we work with many URL reputation vendors to always allow our simulation URLs, we don't always have full coverage.</span></span>

![Google Chrome에서 기만적 사이트 미리 경고](../../media/attack-sim-chrome-deceptive-site-message.png)

<span data-ttu-id="fca17-116">이 문제는 이 문제의 영향을 Microsoft Edge.</span><span class="sxs-lookup"><span data-stu-id="fca17-116">Note that this issue does not affect Microsoft Edge.</span></span>

<span data-ttu-id="fca17-117">계획 단계의 일부로 피싱 캠페인에서 URL을 사용하기 전에 지원되는 웹 브라우저에서 URL의 가용성을 확인하십시오.</span><span class="sxs-lookup"><span data-stu-id="fca17-117">As part of the planning phase, be sure to check the availability of the URL in your supported web browsers before you use the URL in a phishing campaign.</span></span> <span data-ttu-id="fca17-118">Google Safe Browsing에서 URL을 차단하는 [](https://support.google.com/chrome/a/answer/7532419) 경우 Google의 이 지침을 따라 URL에 대한 액세스를 허용합니다.</span><span class="sxs-lookup"><span data-stu-id="fca17-118">If the URLs are blocked by Google Safe Browsing, [follow this guidance](https://support.google.com/chrome/a/answer/7532419) from Google to allow access to the URLs.</span></span>

<span data-ttu-id="fca17-119">공격 [시뮬레이션](attack-simulation-training-get-started.md) 교육에서 현재 사용되는 URL 목록에 대한 공격 시뮬레이션 교육 사용 시작을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="fca17-119">Refer to [Get started using Attack simulation training](attack-simulation-training-get-started.md) for the list of URLs that are currently used by Attack simulation training.</span></span>

### <a name="phishing-simulation-and-admin-urls-blocked-by-network-proxy-solutions-and-filter-drivers"></a><span data-ttu-id="fca17-120">네트워크 프록시 솔루션 및 필터 드라이버에 의해 차단되는 피싱 시뮬레이션 및 관리자 URL</span><span class="sxs-lookup"><span data-stu-id="fca17-120">Phishing simulation and admin URLs blocked by network proxy solutions and filter drivers</span></span>

<span data-ttu-id="fca17-121">피싱 시뮬레이션 URL과 관리자 URL은 모두 중간 보안 장치 또는 필터에 의해 차단되거나 삭제될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fca17-121">Both phishing simulation URLs and admin URLs might be blocked or dropped by your intermediate security devices or filters.</span></span> <span data-ttu-id="fca17-122">예:</span><span class="sxs-lookup"><span data-stu-id="fca17-122">For example:</span></span>

- <span data-ttu-id="fca17-123">방화벽</span><span class="sxs-lookup"><span data-stu-id="fca17-123">Firewalls</span></span>
- <span data-ttu-id="fca17-124">WAF(웹 응용 프로그램 방화벽) 솔루션</span><span class="sxs-lookup"><span data-stu-id="fca17-124">Web Application Firewall (WAF) solutions</span></span>
- <span data-ttu-id="fca17-125">타사 필터 드라이버(예: 커널 모드 필터)</span><span class="sxs-lookup"><span data-stu-id="fca17-125">Third-party filter drivers (for example, kernel mode filters)</span></span>

<span data-ttu-id="fca17-126">이 계층에서 차단되는 고객은 거의 없는 반면에 이 문제가 발생했습니다.</span><span class="sxs-lookup"><span data-stu-id="fca17-126">While we have seen few customers being blocked at this layer, it does happen.</span></span> <span data-ttu-id="fca17-127">문제가 발생하는 경우 필요한 경우 보안 장치 또는 필터의 검색을 무시하기 위해 다음 URL을 구성하는 것이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fca17-127">If you encounter problems, consider configuring the following URLs to bypass scanning by your security devices or filters as required:</span></span>

- <span data-ttu-id="fca17-128">공격 시뮬레이션 교육 시작에 설명된 시뮬레이션된 피싱 [URL입니다.](attack-simulation-training-get-started.md)</span><span class="sxs-lookup"><span data-stu-id="fca17-128">The simulated phishing URLs as described in [Get started using Attack simulation training](attack-simulation-training-get-started.md).</span></span>
- <https://security.microsoft.com/attacksimulator>
- <https://security.microsoft.com/attacksimulationreport>
- <https://security.microsoft.com/trainingassignments>

### <a name="simulation-messages-not-delivered-to-all-targeted-users"></a><span data-ttu-id="fca17-129">모든 대상 사용자에게 배달되지 않는 시뮬레이션 메시지</span><span class="sxs-lookup"><span data-stu-id="fca17-129">Simulation messages not delivered to all targeted users</span></span>

<span data-ttu-id="fca17-130">실제로 시뮬레이션 전자 메일 메시지를 받는 사용자 수가 시뮬레이션 대상 사용자 수보다 적을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fca17-130">It's possible that the number of users who actually receive the simulation email messages is less than the number of users who were targeted by the simulation.</span></span> <span data-ttu-id="fca17-131">대상 유효성 검사의 일부로 제외되는 사용자 유형은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="fca17-131">The following types of users will be excluded as part of target validation:</span></span>

- <span data-ttu-id="fca17-132">받는 사람 전자 메일 주소가 잘못되었습니다.</span><span class="sxs-lookup"><span data-stu-id="fca17-132">Invalid recipient email addresses.</span></span>
- <span data-ttu-id="fca17-133">게스트 사용자.</span><span class="sxs-lookup"><span data-stu-id="fca17-133">Guest users.</span></span>
- <span data-ttu-id="fca17-134">Azure AD(Azure Ad)에서 더 이상 Azure Active Directory 사용자입니다.</span><span class="sxs-lookup"><span data-stu-id="fca17-134">Users that are no longer active in Azure Active Directory (Azure AD).</span></span>

<span data-ttu-id="fca17-135">유효한 사서함이 있는 게스트가 아닌 유효한 사용자만 시뮬레이션에 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="fca17-135">Only valid, non-guest users with a valid mailbox will be included in simulations.</span></span> <span data-ttu-id="fca17-136">메일 그룹 또는 메일 사용이 가능한 보안 그룹을 사용하여 사용자를 대상으로 지정하는 경우 Exchange Online [PowerShell에서](/powershell/exchange/connect-to-exchange-online-powershell) [Get-DistributionGroupMember](/powershell/module/exchange/get-distributiongroupmember) cmdlet을 사용하여 메일 그룹 구성원을 보고 유효성을 검사할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fca17-136">If you use distribution groups or mail-enabled security groups to target users, you can use the [Get-DistributionGroupMember](/powershell/module/exchange/get-distributiongroupmember) cmdlet in [Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell) to view and validate distribution group members.</span></span>

## <a name="issues-with-attack-simulation-training-reporting"></a><span data-ttu-id="fca17-137">공격 시뮬레이션 교육 보고 관련 문제</span><span class="sxs-lookup"><span data-stu-id="fca17-137">Issues with Attack simulation training reporting</span></span>

### <a name="attack-simulation-training-reports-do-not-contain-any-activity-details"></a><span data-ttu-id="fca17-138">공격 시뮬레이션 교육 보고서에는 활동 세부 정보가 포함되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="fca17-138">Attack simulation training reports do not contain any activity details</span></span>

<span data-ttu-id="fca17-139">공격 시뮬레이션 교육에는 직원의 위협 준비 진행 상황을 알려주는 풍부한 실행 가능한 인사이트가 함께 제공될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fca17-139">Attack simulation training comes with rich, actionable insights that keep you informed of the threat readiness progress of your employees.</span></span> <span data-ttu-id="fca17-140">공격 시뮬레이션 교육 보고서에 데이터가 채워지지 않은 경우 조직에서 감사 로그 검색이 켜져 있는지(기본적으로 켜져 있는지) 확인해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="fca17-140">If Attack simulation training reports are not populated with data, verify that audit log search is turned on in your organization (it's on by default).</span></span>

<span data-ttu-id="fca17-141">감사 로그 검색은 이벤트를 캡처, 기록 및 다시 읽을 수 있도록 공격 시뮬레이션 교육에 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="fca17-141">Audit log search is required by Attack simulation training so events can be captured, recorded, and read back.</span></span> <span data-ttu-id="fca17-142">감사 로그 검색을 끄면 공격 시뮬레이션 교육에 다음과 같은 결과가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="fca17-142">Turning off audit log search has the following consequences for Attack simulation training:</span></span>

- <span data-ttu-id="fca17-143">일부 보고서에서는 보고 데이터를 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="fca17-143">Reporting data is not available across all reports.</span></span> <span data-ttu-id="fca17-144">보고서가 비어 있는 것으로 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="fca17-144">The reports will appear empty.</span></span>
- <span data-ttu-id="fca17-145">데이터를 사용할 수 없는 경우 교육 배정이 차단됩니다.</span><span class="sxs-lookup"><span data-stu-id="fca17-145">Training assignments are blocked, because data is not available.</span></span>

<span data-ttu-id="fca17-146">감사 로그 검색을 설정하려면 감사 로그 검색 켜기 또는 [끄기 를 참조합니다.](../../compliance/turn-audit-log-search-on-or-off.md)</span><span class="sxs-lookup"><span data-stu-id="fca17-146">To turn on audit log search, see [Turn audit log search on or off](../../compliance/turn-audit-log-search-on-or-off.md).</span></span>

> [!NOTE]
> <span data-ttu-id="fca17-147">또한 사용자에게 E5 라이선스가 할당되지 않은 경우 빈 활동 세부 정보가 발생할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fca17-147">Empty activity details can also be caused by no E5 licenses being assigned to users.</span></span> <span data-ttu-id="fca17-148">보고 이벤트가 캡처 및 기록되도록 활성 사용자에게 하나 이상의 E5 라이선스가 할당되어 있는지 확인</span><span class="sxs-lookup"><span data-stu-id="fca17-148">Verify at least one E5 license is assigned to an active user to ensure that reporting events are captured and recorded.</span></span>

### <a name="simulation-reports-are-not-updated-immediately"></a><span data-ttu-id="fca17-149">시뮬레이션 보고서가 즉시 업데이트되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="fca17-149">Simulation reports are not updated immediately</span></span>

<span data-ttu-id="fca17-150">자세한 시뮬레이션 보고서는 캠페인을 시작한 직후에 업데이트되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="fca17-150">Detailed simulation reports are not updated immediately after you launch a campaign.</span></span> <span data-ttu-id="fca17-151">걱정하지 마세요. 이 동작은 예상됩니다.</span><span class="sxs-lookup"><span data-stu-id="fca17-151">Don't worry; this behavior is expected.</span></span>

<span data-ttu-id="fca17-152">모든 시뮬레이션 캠페인에는 수명 주기가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fca17-152">Every simulation campaign has a lifecycle.</span></span> <span data-ttu-id="fca17-153">처음 만들 때 시뮬레이션은 **예약된 상태입니다.**</span><span class="sxs-lookup"><span data-stu-id="fca17-153">When first created, the simulation is in the **Scheduled** state.</span></span> <span data-ttu-id="fca17-154">시뮬레이션이 시작되면 진행 중 **상태로 전환됩니다.**</span><span class="sxs-lookup"><span data-stu-id="fca17-154">When the simulation starts, it transitions to the **In progress** state.</span></span> <span data-ttu-id="fca17-155">완료되면 시뮬레이션이 **완료된 상태로 전환됩니다.**</span><span class="sxs-lookup"><span data-stu-id="fca17-155">When completed, the simulation transitions to the **Completed** state.</span></span>

<span data-ttu-id="fca17-156">시뮬레이션이 예약된  상태일 때 시뮬레이션 보고서는 대부분 비어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fca17-156">While a simulation is in the **Scheduled** state, the simulation reports will be mostly empty.</span></span> <span data-ttu-id="fca17-157">이 단계에서 시뮬레이션 엔진은 대상 사용자 전자 메일 주소를 확인하거나, 메일 그룹을 확장하고, 목록에서 게스트 사용자를 제거하는 등입니다.</span><span class="sxs-lookup"><span data-stu-id="fca17-157">During this stage, the simulation engine is resolving the target user email addresses, expanding distribution groups, removing guest users from the list, etc.:</span></span>

![예약된 상태의 보고](../../media/attack-sim-empty-reporting.png)

<span data-ttu-id="fca17-159">시뮬레이션이 진행 중 **단계에 들어오면** 보고에 들어가기 시작하는 정보를 알 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fca17-159">Once the simulation enters the **In progress** stage, you will notice information starting to trickle into the reporting:</span></span>

![진행 중 상태의 보고](../../media/attack-sim-in-progress.png)

<span data-ttu-id="fca17-161">진행 중 상태로 전환한 후 개별 시뮬레이션 보고서가 업데이트되는 데 최대 30분이 걸릴 **수** 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fca17-161">It can take up to 30 minutes for the individual simulation reports to update after the transition to the **In progress** state.</span></span> <span data-ttu-id="fca17-162">시뮬레이션이 **Completed** 상태가 될 때까지 보고서 데이터가 계속 빌드됩니다.</span><span class="sxs-lookup"><span data-stu-id="fca17-162">The report data continues to build until the simulation reaches the **Completed** state.</span></span> <span data-ttu-id="fca17-163">보고 업데이트는 다음과 같은 간격으로 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="fca17-163">Reporting updates occur at the following intervals:</span></span>

- <span data-ttu-id="fca17-164">처음 60분마다 10분마다.</span><span class="sxs-lookup"><span data-stu-id="fca17-164">Every 10 minutes for the first 60 minutes.</span></span>
- <span data-ttu-id="fca17-165">60분 후 2일까지 15분마다</span><span class="sxs-lookup"><span data-stu-id="fca17-165">Every 15 minutes after 60 minutes until 2 days.</span></span>
- <span data-ttu-id="fca17-166">2일 후 7일까지 30분마다</span><span class="sxs-lookup"><span data-stu-id="fca17-166">Every 30 minutes after 2 days until 7 days.</span></span>
- <span data-ttu-id="fca17-167">7일 후 60분마다</span><span class="sxs-lookup"><span data-stu-id="fca17-167">Every 60 minutes after 7 days.</span></span>

<span data-ttu-id="fca17-168">개요 페이지의  위젯은 시간 경과에 따라 조직의 시뮬레이션 기반 보안 자세에 대한 빠른 스냅숏을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="fca17-168">Widgets on the **Overview** page provide a quick snapshot of your organization's simulation-based security posture over time.</span></span> <span data-ttu-id="fca17-169">이러한 위젯은 시간 경과에 따라 전반적인 보안 자세와 여정을 반영하기 때문에 각 시뮬레이션 캠페인이 완료된 후 업데이트됩니다.</span><span class="sxs-lookup"><span data-stu-id="fca17-169">Because these widgets reflect your overall security posture and journey over time, they're updated after each simulation campaign is completed.</span></span>

> [!NOTE]
> <span data-ttu-id="fca17-170">다양한 보고 페이지에서 **내보내기** 옵션을 사용하여 데이터를 추출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fca17-170">You can use the **Export** option on the various reporting pages to extract data.</span></span>

### <a name="messages-reported-as-phishing-by-users-arent-appearing-in-simulation-reports"></a><span data-ttu-id="fca17-171">사용자가 피싱으로 보고한 메시지가 시뮬레이션 보고서에 나타나지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="fca17-171">Messages reported as phishing by users aren't appearing in simulation reports</span></span>

<span data-ttu-id="fca17-172">공격 시뮬레이터 교육의 시뮬레이션 보고서는 사용자 활동에 대한 세부 정보를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="fca17-172">Simulation reports in Attack simulator training provide details on user activity.</span></span> <span data-ttu-id="fca17-173">예:</span><span class="sxs-lookup"><span data-stu-id="fca17-173">For example:</span></span>

- <span data-ttu-id="fca17-174">메시지의 링크를 클릭한 사용자입니다.</span><span class="sxs-lookup"><span data-stu-id="fca17-174">Users who clicked on the link in the message.</span></span>
- <span data-ttu-id="fca17-175">자격 증명을 포기한 사용자입니다.</span><span class="sxs-lookup"><span data-stu-id="fca17-175">Users who gave up their credentials.</span></span>
- <span data-ttu-id="fca17-176">메시지를 피싱으로 보고한 사용자입니다.</span><span class="sxs-lookup"><span data-stu-id="fca17-176">Users who reported the message as phishing.</span></span>

<span data-ttu-id="fca17-177">피싱으로 보고된 메시지가 공격 시뮬레이션 교육 시뮬레이션 보고서에 캡처되지 않은 경우 보고된 메시지의 Microsoft로의 배달을 차단하는 Exchange 메일 흐름 규칙(전송 규칙)이 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fca17-177">If messages that users reported as phishing aren't captured in Attack simulation training simulation reports, there might be an Exchange mail flow rule (also known as a transport rule) that's blocking the delivery of the reported messages to Microsoft.</span></span> <span data-ttu-id="fca17-178">메일 흐름 규칙이 다음 전자 메일 주소로의 배달을 차단하지 않는지 확인</span><span class="sxs-lookup"><span data-stu-id="fca17-178">Verify that any mail flow rules aren't blocking delivery to the following email addresses:</span></span>

- <span data-ttu-id="fca17-179">junk@office365.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="fca17-179">junk@office365.microsoft.com</span></span>
- <span data-ttu-id="fca17-180">abuse@messaging.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="fca17-180">abuse@messaging.microsoft.com</span></span>
- <span data-ttu-id="fca17-181">phish@office365.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="fca17-181">phish@office365.microsoft.com</span></span>
- <span data-ttu-id="fca17-182">junk@office365.microsoft.com \_</span><span class="sxs-lookup"><span data-stu-id="fca17-182">not\_junk@office365.microsoft.com</span></span>

## <a name="other-frequently-asked-questions"></a><span data-ttu-id="fca17-183">기타 질문과 대답</span><span class="sxs-lookup"><span data-stu-id="fca17-183">Other frequently asked questions</span></span>

### <a name="q-what-is-the-recommended-method-to-target-users-for-simulation-campaigns"></a><span data-ttu-id="fca17-184">Q: 시뮬레이션 캠페인을 대상으로 지정하는 데 권장되는 방법은 무엇입니까?</span><span class="sxs-lookup"><span data-stu-id="fca17-184">Q: What is the recommended method to target users for simulation campaigns?</span></span>

<span data-ttu-id="fca17-185">A: 대상 사용자에게 다음과 같은 몇 가지 옵션을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fca17-185">A: Several options are available to target users:</span></span>

- <span data-ttu-id="fca17-186">모든 사용자를 포함합니다(현재 사용자가 40,000명 미만인 조직에서 사용 가능).</span><span class="sxs-lookup"><span data-stu-id="fca17-186">Include all users (currently available to organizations with less than 40,000 users).</span></span>
- <span data-ttu-id="fca17-187">특정 사용자를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="fca17-187">Choose specific users.</span></span>
- <span data-ttu-id="fca17-188">CSV 파일에서 사용자를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="fca17-188">Select users from a CSV file.</span></span>
- <span data-ttu-id="fca17-189">Azure AD 그룹 기반 대상 지정.</span><span class="sxs-lookup"><span data-stu-id="fca17-189">Azure AD group-based targeting.</span></span>

<span data-ttu-id="fca17-190">Azure AD 그룹에서 대상 사용자를 식별하는 캠페인을 일반적으로 더 쉽게 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fca17-190">We've found that campaigns where the targeted users are identified by Azure AD groups are generally easier to manage.</span></span>

### <a name="q-are-there-any-limits-in-targeting-users-while-importing-from-a-csv-or-adding-users"></a><span data-ttu-id="fca17-191">Q: CSV에서 가져오거나 사용자를 추가하는 동안 사용자를 대상으로 지정하는 데 제한이 있습니까?</span><span class="sxs-lookup"><span data-stu-id="fca17-191">Q: Are there any limits in targeting users while importing from a CSV or adding users?</span></span>

<span data-ttu-id="fca17-192">A: CSV 파일에서 받는 사람을 가져오거나 시뮬레이션에 개별 받는 사람을 추가하는 제한은 40,000개입니다.</span><span class="sxs-lookup"><span data-stu-id="fca17-192">A: The limit for importing recipients from a CSV file or adding individual recipients to a simulation is 40,000.</span></span>

<span data-ttu-id="fca17-193">받는 사람은 개별 사용자 또는 그룹일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fca17-193">A recipient can be an individual user or a group.</span></span> <span data-ttu-id="fca17-194">그룹에는 수백 또는 수천 명의 받는 사람이 포함될 수 있으므로 개별 사용자 수에 대한 실제 제한이 설정되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="fca17-194">A group might contain hundreds or thousands of recipients, so an actual limit isn't placed on the number of individual users.</span></span>

<span data-ttu-id="fca17-195">큰 CSV 파일을 관리하거나 개별 받는 사람을 여러 개 추가하는 것이 번거로우면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="fca17-195">Managing a large CSV file or adding many individual recipients can be cumbersome.</span></span> <span data-ttu-id="fca17-196">Azure AD 그룹을 사용하여 시뮬레이션의 전체 관리를 간소화합니다.</span><span class="sxs-lookup"><span data-stu-id="fca17-196">Using Azure AD groups will simplify the overall management of the simulation.</span></span>

### <a name="q-does-microsoft-provide-payloads-in-other-languages"></a><span data-ttu-id="fca17-197">Q: Microsoft에서 다른 언어로 페이로드를 제공합니까?</span><span class="sxs-lookup"><span data-stu-id="fca17-197">Q: Does Microsoft provide payloads in other languages?</span></span>

<span data-ttu-id="fca17-198">A: 현재 사용할 수 있는 지역화된 페이로드는 5개입니다.</span><span class="sxs-lookup"><span data-stu-id="fca17-198">A: Currently, there are 5 localized payloads available.</span></span> <span data-ttu-id="fca17-199">기존 페이로드를 다른 언어로 직접 또는 기계 번역하면 부정확성 및 줄어든다는 사실이 발견했습니다.</span><span class="sxs-lookup"><span data-stu-id="fca17-199">We've noticed than any direct or machine translations of existing payloads to other languages will lead to inaccuracies and decreased relevance.</span></span>

<span data-ttu-id="fca17-200">즉, 사용자 지정 페이로드 제작 환경을 사용하여 원하는 언어로 직접 페이로드를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fca17-200">That being said, you can create your own payload in the language of your choice using the custom payload authoring experience.</span></span> <span data-ttu-id="fca17-201">또한 특정 지리에서 사용자를 대상으로 지정하는 데 사용된 기존 페이로드를 수집하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="fca17-201">We also strongly recommend that you harvest existing payloads that were used to target users in a specific geography.</span></span> <span data-ttu-id="fca17-202">즉, 공격자가 콘텐츠를 지역화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fca17-202">In other words, let the attackers localize the content for you.</span></span>

### <a name="q-how-can-i-switch-to-other-languages-for-my-admin-portal-and-training-experience"></a><span data-ttu-id="fca17-203">Q: 관리자 포털 및 교육 환경을 위해 다른 언어로 전환하려면 어떻게 하나요?</span><span class="sxs-lookup"><span data-stu-id="fca17-203">Q: How can I switch to other languages for my admin portal and training experience?</span></span>

<span data-ttu-id="fca17-204">A: Microsoft 365 Office 365 사용자 계정에 대해 언어 구성이 구체화되어 중앙 집중화됩니다.</span><span class="sxs-lookup"><span data-stu-id="fca17-204">A: In Microsoft 365 or Office 365, language configuration is specific and centralized for each user account.</span></span> <span data-ttu-id="fca17-205">언어 설정을 변경하는 방법에 대한 지침은 비즈니스용 Microsoft 365 표시 언어 및 표준 [시간대 변경을 참조하세요.](https://support.microsoft.com/office/6f238bff-5252-441e-b32b-655d5d85d15b)</span><span class="sxs-lookup"><span data-stu-id="fca17-205">For instructions on how to change your language setting, see [Change your display language and time zone in Microsoft 365 for Business](https://support.microsoft.com/office/6f238bff-5252-441e-b32b-655d5d85d15b).</span></span>

<span data-ttu-id="fca17-206">구성 변경 내용이 모든 서비스에서 동기화하는 데 최대 30분이 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fca17-206">Note that the configuration change might take up to 30 minutes to synchronize across all services.</span></span>

### <a name="q-can-i-trigger-a-test-simulation-to-understand-what-it-looks-like-prior-to-launching-a-full-fledged-campaign"></a><span data-ttu-id="fca17-207">Q: 본격적인 캠페인을 시작하기 전에 테스트 시뮬레이션을 트리거하여 어떻게 보이는지 이해할 수 있나요?</span><span class="sxs-lookup"><span data-stu-id="fca17-207">Q: Can I trigger a test simulation to understand what it looks like prior to launching a full-fledged campaign?</span></span>

<span data-ttu-id="fca17-208">A: 예!</span><span class="sxs-lookup"><span data-stu-id="fca17-208">A: Yes you can!</span></span> <span data-ttu-id="fca17-209">마법사의 **마지막** 시뮬레이션 검토 페이지에서 새 시뮬레이션을 만들 수 있습니다. 테스트 보내기 옵션이 **있습니다.**</span><span class="sxs-lookup"><span data-stu-id="fca17-209">On the very last **Review Simulation** page in the wizard to create a new simulation, there's an option to **Send a test**.</span></span> <span data-ttu-id="fca17-210">이 옵션은 현재 로그인한 사용자에게 샘플 피싱 시뮬레이션 메시지를 전송합니다.</span><span class="sxs-lookup"><span data-stu-id="fca17-210">This option will send a sample phishing simulation message to the currently logged in user.</span></span> <span data-ttu-id="fca17-211">받은 편지함에서 피싱 메시지의 유효성을 검사한 후 시뮬레이션을 제출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fca17-211">After you validate the phishing message in your Inbox, you can submit the simulation.</span></span>

![시뮬레이션 검토 페이지에서 테스트 단추 보내기](../../media/attack-sim-review-simulation-page.png)

### <a name="q-can-i-target-users-that-belong-to-a-different-tenant-as-part-of-the-same-simulation-campaign"></a><span data-ttu-id="fca17-213">Q: 동일한 시뮬레이션 캠페인의 일부로 다른 테넌트에 속한 사용자를 대상으로 할 수 있나요?</span><span class="sxs-lookup"><span data-stu-id="fca17-213">Q: Can I target users that belong to a different tenant as part of the same simulation campaign?</span></span>

<span data-ttu-id="fca17-214">A: 아니요.</span><span class="sxs-lookup"><span data-stu-id="fca17-214">A: No.</span></span> <span data-ttu-id="fca17-215">현재 테넌트 간 시뮬레이션은 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="fca17-215">Currently, cross-tenant simulations are not supported.</span></span> <span data-ttu-id="fca17-216">모든 대상 사용자가 동일한 테넌트에 있는지 확인</span><span class="sxs-lookup"><span data-stu-id="fca17-216">Verify that all of your targeted users are in the same tenant.</span></span> <span data-ttu-id="fca17-217">테넌트 간 사용자 또는 게스트 사용자는 시뮬레이션 캠페인에서 제외됩니다.</span><span class="sxs-lookup"><span data-stu-id="fca17-217">Any cross-tenant users or guest users will be excluded from the simulation campaign.</span></span>

### <a name="q-how-does-region-aware-delivery-work"></a><span data-ttu-id="fca17-218">Q: 지역 인식 배달은 어떻게 작동하나요?</span><span class="sxs-lookup"><span data-stu-id="fca17-218">Q: How does region aware delivery work?</span></span>

<span data-ttu-id="fca17-219">A: 지역 인식 배달은 대상 사용자 사서함의 TimeZone 특성과 '이전' 논리를 사용하여 메시지를 배달할 시기를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="fca17-219">A: Region aware delivery uses the TimeZone attribute of the targeted user's mailbox and 'not before' logic to determine when to deliver the message.</span></span> <span data-ttu-id="fca17-220">예를 들어 다음 시나리오를 고려합니다.</span><span class="sxs-lookup"><span data-stu-id="fca17-220">For example, consider the following scenario:</span></span>

- <span data-ttu-id="fca17-221">태평양 표준 시간대(UTC-8)의 오전 7:00에 관리자는 캠페인을 만들고 같은 날 오전 9시에 시작을 예약합니다.</span><span class="sxs-lookup"><span data-stu-id="fca17-221">At 7:00 AM in the Pacific time zone (UTC-8), an admin creates and schedules a campaign to start at 9:00 AM on the same day.</span></span>
- <span data-ttu-id="fca17-222">UserA는 동부 표준 시간대(UTC-5)에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fca17-222">UserA is in the Eastern time zone (UTC-5).</span></span>
- <span data-ttu-id="fca17-223">UserB는 태평양 표준 시간대에도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fca17-223">UserB is also in the Pacific time zone.</span></span>

<span data-ttu-id="fca17-224">같은 날 오전 9시에 시뮬레이션 메시지가 UserB로 전송됩니다.</span><span class="sxs-lookup"><span data-stu-id="fca17-224">At 9:00 AM on the same day, the simulation message is sent to UserB.</span></span> <span data-ttu-id="fca17-225">태평양 표준시(태평양 표준시)는 동부 표준시 오후 12시이기 때문에 지역 인식 배달을 사용할 경우 메시지는 같은 날에 UserA로 전송되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="fca17-225">With region-aware delivery, the message is not sent to UserA on the same day, because 9:00 AM Pacific time is 12:00 PM Eastern time.</span></span> <span data-ttu-id="fca17-226">대신 메시지는 다음 날 동부 시간으로 오전 9시에 UserA로 전송됩니다.</span><span class="sxs-lookup"><span data-stu-id="fca17-226">Instead, the message is sent to UserA at 9:00 AM Eastern time on the following day.</span></span>

<span data-ttu-id="fca17-227">따라서 지역 인식 배달이 설정된 캠페인의 초기 실행 시 시뮬레이션 메시지가 특정 표준 시간대의 사용자에게만 전송된 것으로 표시될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fca17-227">So, on the initial run of a campaign with region aware delivery enabled, it might appear that the simulation message was sent only to users in a specific time zone.</span></span> <span data-ttu-id="fca17-228">그러나 시간이 지나고 더 많은 사용자가 범위로 들어오면 대상 사용자가 늘어나게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="fca17-228">But, as time passes and more users come into scope, the targeted users will increase.</span></span>