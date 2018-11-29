---
title: Microsoft Managed Desktop의 업데이트 처리 방법
description: 속도 및 안정성 간의 균형을은 데스크톱을 관리 하는 Microsoft를 최신 상태로 유지 합니다.
keywords: Microsoft 관리 되는 데스크톱, Microsoft 365 서비스, 설명서
ms.service: m365-md
author: jdeckerms
ms.localizationpriority: normal
ms.date: 09/24/2018
ms.openlocfilehash: 513e03b7d703e0a9f78281ddac764d8a29ed5c8f
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/28/2018
ms.locfileid: "26869825"
---
# <a name="how-updates-are-handled-in-microsoft-managed-desktop"></a><span data-ttu-id="c35a7-104">Microsoft Managed Desktop의 업데이트 처리 방법</span><span class="sxs-lookup"><span data-stu-id="c35a7-104">How updates are handled in Microsoft Managed Desktop</span></span>


<!--This topic is the target for a "Learn more" link in the Admin Portal (aka.ms/update-rings); do not delete.-->

<!--Update management -->

<span data-ttu-id="c35a7-p101">Microsoft 관리 되는 데스크톱 현대 클라우드 기반 인프라를 모든 장치를 연결합니다. Windows, Office, 드라이버, 펌웨어 및 Microsoft 저장소 비즈니스 응용 프로그램 업데이트에 대 한 최신 상태로 유지 하는 속도 안정성을 가진 간의 균형을입니다. 배포 전화가 오면 운영 체제를 확인 하는데 사용 되 및 정책 안전한 방식으로 롤백됩니다.</span><span class="sxs-lookup"><span data-stu-id="c35a7-p101">Microsoft Managed Desktop connects all devices to a modern cloud-based infrastructure. Keeping Windows, Office, drivers, firmware, and Microsoft Store for Business application updates up to date is a balance of speed and stability. Deployment rings will be used to ensure OS and policies are rolled out in a safe manner.</span></span> 

## <a name="update-rings"></a><span data-ttu-id="c35a7-108">전화가 올 업데이트</span><span class="sxs-lookup"><span data-stu-id="c35a7-108">Update rings</span></span>

<span data-ttu-id="c35a7-109">Microsoft 관리 되는 데스크톱 4 개의 Azure AD 그룹을 사용 하 여 업데이트를 관리 하려면:</span><span class="sxs-lookup"><span data-stu-id="c35a7-109">Microsoft Managed Desktop uses four Azure AD groups to manage updates:</span></span>

- <span data-ttu-id="c35a7-110">테스트: 테스트 링은만 및으로 설계 된 테스트 고객 테 넌 트에 대 한 변경 내용의 유효성을 검사 합니다.</span><span class="sxs-lookup"><span data-stu-id="c35a7-110">Test: The test ring is only designed for test and validation of changes made in the customer tenant.</span></span>  
- <span data-ttu-id="c35a7-111">1: 먼저 것을 초기 소프트웨어를 설치 하 고 일부 시험판 업데이트 되도록 하는 제한 된 기술 전문 사용자가 사용 하 여는 초기 테스트 링 되도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="c35a7-111">First: First is intended to be an early test ring with limited tech savvy users that are willing to install software early and be subject to some pre-release updates.</span></span>
- <span data-ttu-id="c35a7-p102">Fast: fast 링은 다양 한 사용자는 기대할입니다.  이 연결에 대 한 목표 장치 업데이트 된 소프트웨어 배달의 빠른 속도와 보안을 유지 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="c35a7-p102">Fast: The fast ring is where we would expect a large set of users.  The goal for this ring is to keep devices updated and secure with a quick pace of software delivery.</span></span>  
- <span data-ttu-id="c35a7-p103">저속 연결은 품질 및 기능 업데이트 로그 아웃 균형 있게 신중 roll 광범위 한:입니다.  빠른 여전히 전달 품질 업데이트 속도 하지만 즉시 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c35a7-p103">Broad: The slow ring is a balanced conservative roll out of quality and feature updates.  Quality updates are still delivered at a fast pace, but not immediately.</span></span> 

<span data-ttu-id="c35a7-116">연결 시스템에서 업데이트 품질, 분류 됩니다 또는 업데이트 기능:</span><span class="sxs-lookup"><span data-stu-id="c35a7-116">The updates in the ring system are categorized as quality, or feature updates:</span></span>
- <span data-ttu-id="c35a7-p104">품질 업데이트 중요, 보안 및 드라이버 업데이트를 포함 합니다.  이 일반적으로 월별 업데이트가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c35a7-p104">Quality updates include security, critical, and driver updates.  These are usually monthly updates.</span></span> 
- <span data-ttu-id="c35a7-119">기능 업데이트 포함 뿐 아니라 보안 및 품질 수정 하지만 중요 한 기능 추가 및 변경 합니다. 연간 해제 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c35a7-119">Feature updates contain not only security and quality revisions, but also significant feature additions and changes; they are released semi-annually.</span></span> 

<span data-ttu-id="c35a7-120">링 프로 모션의 작동 방식:</span><span class="sxs-lookup"><span data-stu-id="c35a7-120">How ring promotion works:</span></span>
- <span data-ttu-id="c35a7-121">Microsoft 관리 되는 데스크톱에는 아래에 지정 된 일정에 따라 새 기능 또는 품질 업데이트를 배포 합니다.</span><span class="sxs-lookup"><span data-stu-id="c35a7-121">Microsoft Managed Desktop deploys a new feature or quality update according the schedule specified below.</span></span>
- <span data-ttu-id="c35a7-122">배포 시 Microsoft 관리 되는 데스크톱 오류 또는 기타 중단 원격 분석 신호 및 최종 사용자 지원 시스템); (통해 흔적이 대 한 모니터링 모든 검색 되 면 다음 배포 모든 현재 및 미래의 고리를 즉시 일시 중지 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="c35a7-122">During deployment, Microsoft Managed Desktop monitors for signs of failure or other disruption (via telemetry signals and our end-user support system); if any are detected, then the deployment to all current and future rings is immediately paused.</span></span>
    - <span data-ttu-id="c35a7-123">예: 첫번째 링에 품질 업데이트를 배포 하는 동안 문제가 발견 되 면 다음 먼저, Fast, 및 한 광범위 한 모든 일시 중지 됩니다 문제가 해결 될 때까지 합니다.</span><span class="sxs-lookup"><span data-stu-id="c35a7-123">Example: if an issue is discovered while deploying a quality update to the First ring, then First, Fast, and Broad will all be paused until the issue is resolved.</span></span>
    - <span data-ttu-id="c35a7-124">Microsoft 데스크톱 IT 관리자가 관리 하는 포털에서 티켓을 정리 하 여 호환성 문제를 보고 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c35a7-124">Compatibility issues may be reported by filing a ticket in the Microsoft Managed Desktop IT Admin portal.</span></span>
- <span data-ttu-id="c35a7-p105">기능 및 품질 업데이트 독립적으로 일시 됩니다.  일시 중지는 기본적으로 35 일 동안 적용 하지만 축소 하거나이 문제는 설정을 여부에 따라 확장 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c35a7-p105">Feature and quality updates are paused independently.  Pause is in effect for 35 days by default but can be reduced or extended depending on whether the issue is remediated.</span></span>
- <span data-ttu-id="c35a7-127">일단 고리는 사용 하지 않는 되 면 배포 아래의 일정에 따라 다시 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="c35a7-127">Once the rings are un-paused, deployment resumes according to the schedule below.</span></span>
- <span data-ttu-id="c35a7-128">이 프로 모션 프로세스 각각에 대 한 시간 표시 막대 다르며 상황이 기능 및 품질을 모두 업데이트에 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c35a7-128">This promotion process applies to both feature and quality updates, though the timeline varies for each.</span></span>

<table>
<tr><th colspan="5"><span data-ttu-id="c35a7-129">이 울리고 지연 설정</span><span class="sxs-lookup"><span data-stu-id="c35a7-129">Rings and deferral settings</span></span></th></tr>
<tr><th><span data-ttu-id="c35a7-130">업데이트 유형</span><span class="sxs-lookup"><span data-stu-id="c35a7-130">Update type</span></span></th><th><span data-ttu-id="c35a7-131">테스트 연결</span><span class="sxs-lookup"><span data-stu-id="c35a7-131">Test ring</span></span></th><th><span data-ttu-id="c35a7-132">먼저</span><span class="sxs-lookup"><span data-stu-id="c35a7-132">First</span></span></th><th><span data-ttu-id="c35a7-133">빠른</span><span class="sxs-lookup"><span data-stu-id="c35a7-133">Fast</span></span></th><th><span data-ttu-id="c35a7-134">광범위 한</span><span class="sxs-lookup"><span data-stu-id="c35a7-134">Broad</span></span></th></tr>
<tr><td><span data-ttu-id="c35a7-135">운영 체제에 대 한 품질 업데이트</span><span class="sxs-lookup"><span data-stu-id="c35a7-135">Quality updates for operating system</span></span></td><td><span data-ttu-id="c35a7-136">0 일</span><span class="sxs-lookup"><span data-stu-id="c35a7-136">0 days</span></span></td><td><span data-ttu-id="c35a7-137">0 일</span><span class="sxs-lookup"><span data-stu-id="c35a7-137">0 days</span></span></td><td><span data-ttu-id="c35a7-138">1일</span><span class="sxs-lookup"><span data-stu-id="c35a7-138">1 day</span></span></td><td><span data-ttu-id="c35a7-139">5일</span><span class="sxs-lookup"><span data-stu-id="c35a7-139">5 days</span></span></td></tr>
<tr><td><span data-ttu-id="c35a7-140">운영 체제에 대 한 기능 업데이트</span><span class="sxs-lookup"><span data-stu-id="c35a7-140">Feature updates for operating system</span></span></td><td><span data-ttu-id="c35a7-141">부분적으로 연간 채널 (대상) + 0 일</span><span class="sxs-lookup"><span data-stu-id="c35a7-141">Semi-annual channel (targeted) + 0 days</span></span></td><td><span data-ttu-id="c35a7-142">부분적으로 연간 채널 (대상) + 30 일</span><span class="sxs-lookup"><span data-stu-id="c35a7-142">Semi-annual channel (targeted) + 30 days</span></span></td><td><span data-ttu-id="c35a7-143">부분적으로 연간 채널 (대상) + 60 일</span><span class="sxs-lookup"><span data-stu-id="c35a7-143">Semi-annual channel (targeted) + 60 days</span></span></td><td><span data-ttu-id="c35a7-144">부분적으로 연간 채널 + 30 일</span><span class="sxs-lookup"><span data-stu-id="c35a7-144">Semi-annual channel + 30 days</span></span></td></tr>
<tr><td><span data-ttu-id="c35a7-145">드라이버/펌웨어</span><span class="sxs-lookup"><span data-stu-id="c35a7-145">Drivers/firmware</span></span></td><td colspan="4"><span data-ttu-id="c35a7-146">품질 업데이트에 대 한 일정을 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="c35a7-146">Follows the schedule for quality updates</span></span></td></tr>
<tr><td><span data-ttu-id="c35a7-147">바이러스 백신 정의</span><span class="sxs-lookup"><span data-stu-id="c35a7-147">Anti-virus definition</span></span></td><td colspan="4"><span data-ttu-id="c35a7-148">각 검색을 사용 하 여 업데이트</span><span class="sxs-lookup"><span data-stu-id="c35a7-148">Updated with each scan</span></span></td></tr>
<tr><td><span data-ttu-id="c35a7-149">실행 하려면 office 계산할 수 있어 더하기를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="c35a7-149">Office Pro-Plus click to run</span></span></td><td colspan="4"><span data-ttu-id="c35a7-150">부분적으로 연간 채널에 정렬</span><span class="sxs-lookup"><span data-stu-id="c35a7-150">Aligned with semi-annual channel</span></span></td></tr>
</table>


## <a name="windows-insider-program"></a><span data-ttu-id="c35a7-151">Windows 내부 인 프로그램</span><span class="sxs-lookup"><span data-stu-id="c35a7-151">Windows Insider Program</span></span>

<span data-ttu-id="c35a7-p106">데스크톱을 관리 하는 Microsoft Windows 내부 인 프로그램의 일부인 장치를 지원 하지 않습니다. 이 프로그램 시험판 Windows 소프트웨어의 유효성을 검사 하는데 하며 아닌 업무상 중요 한 장치에 대 한. 중요 한 Microsoft 계획 이지만, 프로덕션 환경에서 광범위 한 배포는 것이 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="c35a7-p106">Microsoft Managed Desktop does not support devices that are part of the Windows Insider program. This program is used to validate pre-release Windows software and is intended for non-mission critical devices. While this is an important Microsoft initiative, it is not intended for broad deployment in production environments.</span></span> 

<span data-ttu-id="c35a7-155">Windows 내부 인 빌드와 발견 된 모든 장치 테스트 링 상태로 및 업데이트 Sla에 포함 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c35a7-155">Any devices found with Windows Insider builds will be put into the Test ring and not be included for update SLAs.</span></span>

## <a name="bandwidth-management"></a><span data-ttu-id="c35a7-156">대역폭 관리</span><span class="sxs-lookup"><span data-stu-id="c35a7-156">Bandwidth management</span></span>

<span data-ttu-id="c35a7-p107">배달 최적화는 모든 운영 체제 및 드라이버 업데이트에 사용 됩니다. 동료와 회사 네트워크 내에서 업데이트를 검색 하 여 Windows Update (WU) 서비스에서 다운로드 크기를 최소화 합니다.</span><span class="sxs-lookup"><span data-stu-id="c35a7-p107">Delivery optimization is used for all operating system and driver updates. It minimizes the download size from the Windows Update (WU) service by seeking updates from peers within the corporate network.</span></span>


