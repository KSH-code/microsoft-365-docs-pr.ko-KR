---
title: Microsoft Managed Desktop의 업데이트 처리 방법
description: 속도 및 안정성 간의 균형을은 데스크톱을 관리 하는 Microsoft를 최신 상태로 유지 합니다.
keywords: Microsoft 관리 되는 데스크톱, Microsoft 365 서비스, 설명서
ms.service: m365-md
author: trudyha
ms.localizationpriority: normal
ms.date: 01/09/2019
ms.openlocfilehash: bee6381b0f2b7b1e2d929329c3cf628ab7657678
ms.sourcegitcommit: e491c4713115610cbe13d2fbd0d65e1a41c34d62
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/16/2019
ms.locfileid: "26869825"
---
# <a name="how-updates-are-handled-in-microsoft-managed-desktop"></a><span data-ttu-id="4ce0a-104">Microsoft Managed Desktop의 업데이트 처리 방법</span><span class="sxs-lookup"><span data-stu-id="4ce0a-104">How updates are handled in Microsoft Managed Desktop</span></span>


<!--This topic is the target for a "Learn more" link in the Admin Portal (aka.ms/update-rings); do not delete.-->

<!--Update management -->

<span data-ttu-id="4ce0a-p101">Microsoft 관리 되는 데스크톱 현대 클라우드 기반 인프라를 모든 장치를 연결합니다. Windows, Office, 드라이버, 펌웨어 및 Microsoft 저장소 비즈니스 응용 프로그램 업데이트에 대 한 최신 상태로 유지 하는 속도 안정성을 가진 간의 균형을입니다. 배포 전화가 오면 운영 체제를 확인 하는데 사용 되 및 정책 안전한 방식으로 롤백됩니다.</span><span class="sxs-lookup"><span data-stu-id="4ce0a-p101">Microsoft Managed Desktop connects all devices to a modern cloud-based infrastructure. Keeping Windows, Office, drivers, firmware, and Microsoft Store for Business application updates up to date is a balance of speed and stability. Deployment rings will be used to ensure OS and policies are rolled out in a safe manner.</span></span> 

## <a name="update-groups"></a><span data-ttu-id="4ce0a-108">업데이트 그룹</span><span class="sxs-lookup"><span data-stu-id="4ce0a-108">Update groups</span></span>

<span data-ttu-id="4ce0a-109">Microsoft 관리 되는 데스크톱 4 개의 Azure AD 그룹을 사용 하 여 업데이트를 관리 하려면:</span><span class="sxs-lookup"><span data-stu-id="4ce0a-109">Microsoft Managed Desktop uses four Azure AD groups to manage updates:</span></span>

- <span data-ttu-id="4ce0a-p102">테스트: 테스팅 장치 테 넌 트의 나머지 부분을 통해 변경 된 내용의 배포 하기 전에 변경 내용을 유효성을 검사 하기 위한 것입니다. 이 연결의 장치는 문서화 된 최종 사용자 지원에 대 한 범위를 벗어났습니다.</span><span class="sxs-lookup"><span data-stu-id="4ce0a-p102">Test: Non-production devices intended to validate changes prior to deploying the changes across the rest of the tenant. Devices in this ring are out of scope for documented end user support.</span></span> 
- <span data-ttu-id="4ce0a-112">1: 소프트웨어 채택한 포함 장치 시험판 업데이트 될 수 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4ce0a-112">First: Contains early software adopters, and devices may be subject to pre-release updates.</span></span>
- <span data-ttu-id="4ce0a-p103">Fast: 안정성을 통해 우선 속도 순위를 지정 합니다. 광범위 한 그룹에 제공 되는 대로 전에 품질 문제를 검색 하는데 유용 합니다.</span><span class="sxs-lookup"><span data-stu-id="4ce0a-p103">Fast: Prioritizes speed over stability. Useful for detecting quality issues before they are offered to the Broad group.</span></span> 
- <span data-ttu-id="4ce0a-p104">한 광범위 한: 사용할 수 있는 기능 및 품질 업데이트가 있는 마지막 그룹입니다. 이 그룹 대부분의 사용자는 테 넌 트에 포함 하 고 따라서 안정성 배포의 속도 보다 우선 합니다.</span><span class="sxs-lookup"><span data-stu-id="4ce0a-p104">Broad: Last group to have feature and quality updates available. This group contains the majority of users in the tenant, and therefore favors stability over speed in deployment.</span></span>

<span data-ttu-id="4ce0a-p105">Microsoft는 업데이트는 누적 및 품질 또는 기능 업데이트도 분류할 수 있습니다. 자세한 내용은 참조 [Windows Update: FAQ](https://support.microsoft.com/help/12373/windows-update-faq)합니다.</span><span class="sxs-lookup"><span data-stu-id="4ce0a-p105">Updates released by Microsoft are cumulative and may be categorized as quality or feature updates. For more information, see [Windows Update: FAQ](https://support.microsoft.com/help/12373/windows-update-faq).</span></span> 

<span data-ttu-id="4ce0a-119">배포의 작동 방법 업데이트 하려면:</span><span class="sxs-lookup"><span data-stu-id="4ce0a-119">How update deployment works:</span></span>
- <span data-ttu-id="4ce0a-120">Microsoft 관리 되는 데스크톱에는 아래에 지정 된 일정에 따라 새 기능 또는 품질 업데이트를 배포 합니다.</span><span class="sxs-lookup"><span data-stu-id="4ce0a-120">Microsoft Managed Desktop deploys a new feature or quality update according the schedule specified below.</span></span>
- <span data-ttu-id="4ce0a-p106">Microsoft 관리 되는 데스크톱을 배포 하는 동안 흔적이 오류 또는 중단 (원격 분석 신호 및 최종 사용자 지원 시스템에 따라)에 대 한 모니터링 합니다. 모든 검색 되 면 다음 현재 및 미래의 모든 그룹에 배포 즉시 일시 중지 합니다.</span><span class="sxs-lookup"><span data-stu-id="4ce0a-p106">During deployment, Microsoft Managed Desktop monitors for signs of failure or disruption (based on telemetry signals and end-user support system). If any are detected, then the deployment to all current and future groups is immediately paused.</span></span>
    - <span data-ttu-id="4ce0a-123">예: 첫번째 그룹에 품질 업데이트를 배포 하는 동안 문제가 발견 되 면 다음 먼저, 빠른, 및 한 광범위 한 업데이트 배포 모두 일시 중지 됩니다 문제가 해결 될 때까지 합니다.</span><span class="sxs-lookup"><span data-stu-id="4ce0a-123">Example: if an issue is discovered while deploying a quality update to the First group, then update deployments to First, Fast, and Broad will all be paused until the issue is resolved.</span></span>
    - <span data-ttu-id="4ce0a-124">Microsoft 데스크톱 IT 관리자가 관리 하는 포털에서 티켓을 정리 하 여 호환성 문제를 보고 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4ce0a-124">Compatibility issues may be reported by filing a ticket in the Microsoft Managed Desktop IT Admin portal.</span></span>
- <span data-ttu-id="4ce0a-p107">기능 및 품질 업데이트 독립적으로 일시 됩니다. 일시 중지는 기본적으로 35 일 동안 적용 하지만 축소 또는 문제는 설정을 여부에 따라 확장 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4ce0a-p107">Feature and quality updates are paused independently. Pause is in effect for 35 days by default, but can be reduced or extended depending on whether the issue is remediated.</span></span>
- <span data-ttu-id="4ce0a-127">그룹을 해제 사용 하지 않으면 되 면 배포 아래의 일정에 따라 다시 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="4ce0a-127">Once the groups are un-paused, deployment resumes according to the schedule below.</span></span>
- <span data-ttu-id="4ce0a-128">이 배포 프로세스 각각에 대 한 시간 표시 막대 다르며 상황이 기능 및 품질을 모두 업데이트에 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4ce0a-128">This deployment process applies to both feature and quality updates, though the timeline varies for each.</span></span>

<table>
<tr><th colspan="5"><span data-ttu-id="4ce0a-129">배포 설정 업데이트</span><span class="sxs-lookup"><span data-stu-id="4ce0a-129">Update deployment settings</span></span></th></tr>
<tr><th><span data-ttu-id="4ce0a-130">업데이트 유형</span><span class="sxs-lookup"><span data-stu-id="4ce0a-130">Update type</span></span></th><th><span data-ttu-id="4ce0a-131">테스트</span><span class="sxs-lookup"><span data-stu-id="4ce0a-131">Test</span></span></th><th><span data-ttu-id="4ce0a-132">먼저</span><span class="sxs-lookup"><span data-stu-id="4ce0a-132">First</span></span></th><th><span data-ttu-id="4ce0a-133">빠른</span><span class="sxs-lookup"><span data-stu-id="4ce0a-133">Fast</span></span></th><th><span data-ttu-id="4ce0a-134">광범위 한</span><span class="sxs-lookup"><span data-stu-id="4ce0a-134">Broad</span></span></th></tr>
<tr><td><span data-ttu-id="4ce0a-135">운영 체제에 대 한 품질 업데이트</span><span class="sxs-lookup"><span data-stu-id="4ce0a-135">Quality updates for operating system</span></span></td><td><span data-ttu-id="4ce0a-136">0 일</span><span class="sxs-lookup"><span data-stu-id="4ce0a-136">0 days</span></span></td><td><span data-ttu-id="4ce0a-137">0 일</span><span class="sxs-lookup"><span data-stu-id="4ce0a-137">0 days</span></span></td><td><span data-ttu-id="4ce0a-138">0 일</span><span class="sxs-lookup"><span data-stu-id="4ce0a-138">0 days</span></span></td><td><span data-ttu-id="4ce0a-139">3 일</span><span class="sxs-lookup"><span data-stu-id="4ce0a-139">3 days</span></span></td></tr>
<tr><td><span data-ttu-id="4ce0a-140">운영 체제에 대 한 기능 업데이트</span><span class="sxs-lookup"><span data-stu-id="4ce0a-140">Feature updates for operating system</span></span></td><td><span data-ttu-id="4ce0a-141">0 일</span><span class="sxs-lookup"><span data-stu-id="4ce0a-141">0 days</span></span></td><td><span data-ttu-id="4ce0a-142">30일</span><span class="sxs-lookup"><span data-stu-id="4ce0a-142">30 days</span></span></td><td><span data-ttu-id="4ce0a-143">60일</span><span class="sxs-lookup"><span data-stu-id="4ce0a-143">60 days</span></span></td><td><span data-ttu-id="4ce0a-144">90일</span><span class="sxs-lookup"><span data-stu-id="4ce0a-144">90 days</span></span></td></tr>
<tr><td><span data-ttu-id="4ce0a-145">드라이버/펌웨어</span><span class="sxs-lookup"><span data-stu-id="4ce0a-145">Drivers/firmware</span></span></td><td colspan="4"><span data-ttu-id="4ce0a-146">품질 업데이트에 대 한 일정을 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="4ce0a-146">Follows the schedule for quality updates</span></span></td></tr>
<tr><td><span data-ttu-id="4ce0a-147">바이러스 백신 정의</span><span class="sxs-lookup"><span data-stu-id="4ce0a-147">Anti-virus definition</span></span></td><td colspan="4"><span data-ttu-id="4ce0a-148">각 검색을 사용 하 여 업데이트</span><span class="sxs-lookup"><span data-stu-id="4ce0a-148">Updated with each scan</span></span></td></tr>
</table>

<span data-ttu-id="4ce0a-p108">이러한 지연 기간 의도적으로 높은 수준의 보안 및 모든 사용자에 대 한 성능 표준을 보장 하기 위한 것입니다. 또한 모든 Microsoft 관리 되는 데스크톱 장치 및 다양 한 범위 및 업데이트의 영향에서 수집 되는 데이터에 따르면 Microsoft 관리 되는 데스크톱은 보유 ad에서 모든 배포 그룹에 대 한 위의 지연 기간의 길이 수정 하는 유연성 임시 기준입니다.</span><span class="sxs-lookup"><span data-stu-id="4ce0a-p108">These deferral periods are intentionally designed to ensure high security and performance standards for all users. Furthermore, based on data gathered across all Microsoft Managed Desktop devices and the varying scope and impact of updates, Microsoft Managed Desktop reserves flexibility to modify the length of the above deferral periods for any and all deployment groups on an ad hoc basis.</span></span>

## <a name="windows-insider-program"></a><span data-ttu-id="4ce0a-151">Windows 내부 인 프로그램</span><span class="sxs-lookup"><span data-stu-id="4ce0a-151">Windows Insider Program</span></span>

<span data-ttu-id="4ce0a-p109">데스크톱을 관리 하는 Microsoft Windows 내부 인 프로그램의 일부인 장치를 지원 하지 않습니다. Windows 내부 인 프로그램 시험판 Windows 소프트웨어의 유효성을 검사 하는데 하며 아닌 업무상 중요 한 장치에 대 한. 중요 한 Microsoft 계획 이지만, 프로덕션 환경에서 광범위 한 배포는 것이 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="4ce0a-p109">Microsoft Managed Desktop does not support devices that are part of the Windows Insider program. The Windows Insider program is used to validate pre-release Windows software and is intended for non-mission critical devices. While this is an important Microsoft initiative, it is not intended for broad deployment in production environments.</span></span> 

<span data-ttu-id="4ce0a-155">Windows 내부 인 빌드와 발견 된 모든 장치 테스트 그룹 상태로 및 업데이트 서비스 수준 계약 (Sla에 대 한 포함 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="4ce0a-155">Any devices found with Windows Insider builds will be put into the Test group and not be included for update service level agreements (SLAs.</span></span>

## <a name="bandwidth-management"></a><span data-ttu-id="4ce0a-156">대역폭 관리</span><span class="sxs-lookup"><span data-stu-id="4ce0a-156">Bandwidth management</span></span>

<span data-ttu-id="4ce0a-p110">배달 최적화는 모든 운영 체제 및 드라이버 업데이트에 사용 됩니다. 동료와 회사 네트워크 내에서 업데이트를 검색 하 여 Windows Update (WU) 서비스에서 다운로드 크기를 최소화 합니다.</span><span class="sxs-lookup"><span data-stu-id="4ce0a-p110">Delivery optimization is used for all operating system and driver updates. It minimizes the download size from the Windows Update (WU) service by seeking updates from peers within the corporate network.</span></span>


