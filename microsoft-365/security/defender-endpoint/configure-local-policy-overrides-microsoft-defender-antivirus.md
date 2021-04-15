---
title: Microsoft Defender AV 설정에 대한 로컬 오버라이드 구성
description: 사용자가 Microsoft Defender AV에서 로컬로 설정을 변경하지 못하도록 설정하거나 사용하지 않도록 설정
keywords: 로컬 오버라이드, 로컬 정책, 그룹 정책, gpo, 잠금, 병합, 목록
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 02/13/2020
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.openlocfilehash: f3c2b7ae70f42cb7ffc2deef1786ad43e65f33b6
ms.sourcegitcommit: 7a339c9f7039825d131b39481ddf54c57b021b11
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2021
ms.locfileid: "51764642"
---
# <a name="prevent-or-allow-users-to-locally-modify-microsoft-defender-antivirus-policy-settings"></a><span data-ttu-id="faa5a-104">사용자가 Microsoft Defender 바이러스 백신 정책 설정을 로컬로 수정하지 못하도록 차단 또는 허용</span><span class="sxs-lookup"><span data-stu-id="faa5a-104">Prevent or allow users to locally modify Microsoft Defender Antivirus policy settings</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="faa5a-105">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="faa5a-105">**Applies to:**</span></span>

- <span data-ttu-id="faa5a-106">[엔드포인트용 Microsoft Defender](/microsoft-365/security/defender-endpoint/) </span><span class="sxs-lookup"><span data-stu-id="faa5a-106">[Microsoft Defender for Endpoint](/microsoft-365/security/defender-endpoint/)</span></span>

<span data-ttu-id="faa5a-107">기본적으로 그룹 정책 개체를 통해 네트워크의 끝점으로 배포되는 Microsoft Defender 바이러스 백신 설정은 사용자가 로컬로 설정을 변경하지 못하게 합니다.</span><span class="sxs-lookup"><span data-stu-id="faa5a-107">By default, Microsoft Defender Antivirus settings that are deployed via a Group Policy Object to the endpoints in your network will prevent users from locally changing the settings.</span></span> <span data-ttu-id="faa5a-108">경우에 따라 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="faa5a-108">You can change this in some instances.</span></span>

<span data-ttu-id="faa5a-109">예를 들어 특정 사용자 그룹(예: 보안 연구원 및 위협 조사자)이 사용하는 끝점에서 개별 설정을 추가로 제어하도록 허용해야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="faa5a-109">For example, it may be necessary to allow certain user groups (such as security researchers and threat investigators) further control over individual settings on the endpoints they use.</span></span>

## <a name="configure-local-overrides-for-microsoft-defender-antivirus-settings"></a><span data-ttu-id="faa5a-110">Microsoft Defender 바이러스 백신 설정에 대한 로컬 오버라이드 구성</span><span class="sxs-lookup"><span data-stu-id="faa5a-110">Configure local overrides for Microsoft Defender Antivirus settings</span></span>

<span data-ttu-id="faa5a-111">이러한 정책의 기본 설정은 **사용 안 입니다.**</span><span class="sxs-lookup"><span data-stu-id="faa5a-111">The default setting for these policies is **Disabled**.</span></span>

<span data-ttu-id="faa5a-112">사용으로 설정된 경우 끝점의 사용자는 [Windows 보안](microsoft-defender-security-center-antivirus.md) 앱, 로컬 그룹 정책 설정 및 PowerShell cmdlet(해당되는 경우)과 관련된 설정을 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="faa5a-112">If they are set to **Enabled**, users on endpoints can make changes to the associated setting with the [Windows Security](microsoft-defender-security-center-antivirus.md) app, local Group Policy settings, and PowerShell cmdlets (where appropriate).</span></span>

<span data-ttu-id="faa5a-113">다음 표에는 연결된 기능 또는 설정에 대한 각 정책 정책 설정 및 구성 지침이 나열되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="faa5a-113">The following table lists each of the override policy setting and the configuration instructions for the associated feature or setting.</span></span>

<span data-ttu-id="faa5a-114">이러한 설정을 구성하려면</span><span class="sxs-lookup"><span data-stu-id="faa5a-114">To configure these settings:</span></span>

1. <span data-ttu-id="faa5a-115">그룹 정책 관리 컴퓨터에서 그룹 [](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))정책 관리 콘솔을 열고 구성할 그룹 정책 개체를 마우스 오른쪽 단추로 클릭하고 편집을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="faa5a-115">On your Group Policy management computer, open the [Group Policy Management Console](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)), right-click the Group Policy Object you want to configure and click **Edit**.</span></span>

2. <span data-ttu-id="faa5a-116">그룹 정책 **관리 편집기에서** 컴퓨터 **구성으로 이동하여** 관리 템플릿 **을 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="faa5a-116">In the **Group Policy Management Editor** go to **Computer configuration** and click **Administrative templates**.</span></span>

3. <span data-ttu-id="faa5a-117">**Microsoft Defender** 바이러스 백신을 > Windows 구성  요소로 트리를 확장한 다음 아래 표에 지정된 위치를 확장합니다.</span><span class="sxs-lookup"><span data-stu-id="faa5a-117">Expand the tree to **Windows components > Microsoft Defender Antivirus** and then the **Location** specified in the table below.</span></span>

4. <span data-ttu-id="faa5a-118">아래 표에 지정된 정책 **설정을** 두 번 클릭하고 옵션을 원하는 구성으로 설정하십시오.</span><span class="sxs-lookup"><span data-stu-id="faa5a-118">Double-click the policy **Setting** as specified in the table below, and set the option to your desired configuration.</span></span> <span data-ttu-id="faa5a-119">확인 **을** 클릭하고 다른 설정에 대해 반복합니다.</span><span class="sxs-lookup"><span data-stu-id="faa5a-119">Click **OK**, and repeat for any other settings.</span></span>

5. <span data-ttu-id="faa5a-120">그룹 정책 개체를 평소와 같이 배포합니다.</span><span class="sxs-lookup"><span data-stu-id="faa5a-120">Deploy the Group Policy Object as usual.</span></span>

<span data-ttu-id="faa5a-121">위치</span><span class="sxs-lookup"><span data-stu-id="faa5a-121">Location</span></span> | <span data-ttu-id="faa5a-122">설정</span><span class="sxs-lookup"><span data-stu-id="faa5a-122">Setting</span></span> | <span data-ttu-id="faa5a-123">문서</span><span class="sxs-lookup"><span data-stu-id="faa5a-123">Article</span></span>
---|---|---|---
<span data-ttu-id="faa5a-124">MAPS</span><span class="sxs-lookup"><span data-stu-id="faa5a-124">MAPS</span></span> | <span data-ttu-id="faa5a-125">Microsoft MAPS에 보고하기 위한 로컬 설정 오버라이드 구성</span><span class="sxs-lookup"><span data-stu-id="faa5a-125">Configure local setting override for reporting to Microsoft MAPS</span></span> | [<span data-ttu-id="faa5a-126">클라우드 제공 보호 사용</span><span class="sxs-lookup"><span data-stu-id="faa5a-126">Enable cloud-delivered protection</span></span>](enable-cloud-protection-microsoft-defender-antivirus.md)
<span data-ttu-id="faa5a-127">격리</span><span class="sxs-lookup"><span data-stu-id="faa5a-127">Quarantine</span></span> | <span data-ttu-id="faa5a-128">Quarantine 폴더에서 항목 제거를 위한 로컬 설정 오버라이드 구성</span><span class="sxs-lookup"><span data-stu-id="faa5a-128">Configure local setting override for the removal of items from Quarantine folder</span></span> | [<span data-ttu-id="faa5a-129">검사에 대한 수정 구성</span><span class="sxs-lookup"><span data-stu-id="faa5a-129">Configure remediation for scans</span></span>](configure-remediation-microsoft-defender-antivirus.md)
<span data-ttu-id="faa5a-130">실시간 보호</span><span class="sxs-lookup"><span data-stu-id="faa5a-130">Real-time protection</span></span> | <span data-ttu-id="faa5a-131">컴퓨터의 파일 및 프로그램 활동 모니터링에 대한 로컬 설정 다시 설정 구성</span><span class="sxs-lookup"><span data-stu-id="faa5a-131">Configure local setting override for monitoring file and program activity on your computer</span></span> | [<span data-ttu-id="faa5a-132">Microsoft Defender 바이러스 백신 항상 보호 및 모니터링 사용 및 구성</span><span class="sxs-lookup"><span data-stu-id="faa5a-132">Enable and configure Microsoft Defender Antivirus always-on protection and monitoring</span></span>](configure-real-time-protection-microsoft-defender-antivirus.md)
<span data-ttu-id="faa5a-133">실시간 보호</span><span class="sxs-lookup"><span data-stu-id="faa5a-133">Real-time protection</span></span> | <span data-ttu-id="faa5a-134">들어오는 파일 및 나올 파일 활동에 대한 모니터링을 위한 로컬 설정 오버라이드 구성</span><span class="sxs-lookup"><span data-stu-id="faa5a-134">Configure local setting override for monitoring for incoming and outgoing file activity</span></span> | [<span data-ttu-id="faa5a-135">Microsoft Defender 바이러스 백신 항상 보호 및 모니터링 사용 및 구성</span><span class="sxs-lookup"><span data-stu-id="faa5a-135">Enable and configure Microsoft Defender Antivirus always-on protection and monitoring</span></span>](configure-real-time-protection-microsoft-defender-antivirus.md)
<span data-ttu-id="faa5a-136">실시간 보호</span><span class="sxs-lookup"><span data-stu-id="faa5a-136">Real-time protection</span></span> | <span data-ttu-id="faa5a-137">다운로드한 모든 파일 및 첨부 파일을 검사하기 위한 로컬 설정 다시 설정 구성</span><span class="sxs-lookup"><span data-stu-id="faa5a-137">Configure local setting override for scanning all downloaded files and attachments</span></span> | [<span data-ttu-id="faa5a-138">Microsoft Defender 바이러스 백신 항상 보호 및 모니터링 사용 및 구성</span><span class="sxs-lookup"><span data-stu-id="faa5a-138">Enable and configure Microsoft Defender Antivirus always-on protection and monitoring</span></span>](configure-real-time-protection-microsoft-defender-antivirus.md)
<span data-ttu-id="faa5a-139">실시간 보호</span><span class="sxs-lookup"><span data-stu-id="faa5a-139">Real-time protection</span></span> | <span data-ttu-id="faa5a-140">동작 모니터링 켜기에 대한 로컬 설정 다시 설정 구성</span><span class="sxs-lookup"><span data-stu-id="faa5a-140">Configure local setting override for turn on behavior monitoring</span></span> | [<span data-ttu-id="faa5a-141">Microsoft Defender 바이러스 백신 항상 보호 및 모니터링 사용 및 구성</span><span class="sxs-lookup"><span data-stu-id="faa5a-141">Enable and configure Microsoft Defender Antivirus always-on protection and monitoring</span></span>](configure-real-time-protection-microsoft-defender-antivirus.md)
<span data-ttu-id="faa5a-142">실시간 보호</span><span class="sxs-lookup"><span data-stu-id="faa5a-142">Real-time protection</span></span> | <span data-ttu-id="faa5a-143">실시간 보호를 켜도록 로컬 설정 다시 설정 구성</span><span class="sxs-lookup"><span data-stu-id="faa5a-143">Configure local setting override to turn on real-time protection</span></span> | [<span data-ttu-id="faa5a-144">Microsoft Defender 바이러스 백신 항상 보호 및 모니터링 사용 및 구성</span><span class="sxs-lookup"><span data-stu-id="faa5a-144">Enable and configure Microsoft Defender Antivirus always-on protection and monitoring</span></span>](configure-real-time-protection-microsoft-defender-antivirus.md)
<span data-ttu-id="faa5a-145">수정</span><span class="sxs-lookup"><span data-stu-id="faa5a-145">Remediation</span></span> | <span data-ttu-id="faa5a-146">재구성 완료를 위해 예약된 전체 검색을 실행하도록 하루 중 시간의 로컬 설정 재지정 구성</span><span class="sxs-lookup"><span data-stu-id="faa5a-146">Configure local setting override for the time of day to run a scheduled full scan to complete remediation</span></span> | [<span data-ttu-id="faa5a-147">검사에 대한 수정 구성</span><span class="sxs-lookup"><span data-stu-id="faa5a-147">Configure remediation for scans</span></span>](configure-remediation-microsoft-defender-antivirus.md)
<span data-ttu-id="faa5a-148">검사</span><span class="sxs-lookup"><span data-stu-id="faa5a-148">Scan</span></span> | <span data-ttu-id="faa5a-149">최대 CPU 사용률에 대한 로컬 설정 오버라이드 구성</span><span class="sxs-lookup"><span data-stu-id="faa5a-149">Configure local setting override for maximum percentage of CPU utilization</span></span> | [<span data-ttu-id="faa5a-150">검사 구성 및 실행</span><span class="sxs-lookup"><span data-stu-id="faa5a-150">Configure and run scans</span></span>](run-scan-microsoft-defender-antivirus.md)
<span data-ttu-id="faa5a-151">검사</span><span class="sxs-lookup"><span data-stu-id="faa5a-151">Scan</span></span> | <span data-ttu-id="faa5a-152">일정 검사 일에 대한 로컬 설정 오버라이드 구성</span><span class="sxs-lookup"><span data-stu-id="faa5a-152">Configure local setting override for schedule scan day</span></span> | [<span data-ttu-id="faa5a-153">예약된 검사 구성</span><span class="sxs-lookup"><span data-stu-id="faa5a-153">Configure scheduled scans</span></span>](scheduled-catch-up-scans-microsoft-defender-antivirus.md)
<span data-ttu-id="faa5a-154">검사</span><span class="sxs-lookup"><span data-stu-id="faa5a-154">Scan</span></span> | <span data-ttu-id="faa5a-155">예약된 빠른 검사 시간을 위한 로컬 설정 재지정 구성</span><span class="sxs-lookup"><span data-stu-id="faa5a-155">Configure local setting override for scheduled quick scan time</span></span> | [<span data-ttu-id="faa5a-156">예약된 검사 구성</span><span class="sxs-lookup"><span data-stu-id="faa5a-156">Configure scheduled scans</span></span>](scheduled-catch-up-scans-microsoft-defender-antivirus.md)
<span data-ttu-id="faa5a-157">검사</span><span class="sxs-lookup"><span data-stu-id="faa5a-157">Scan</span></span> | <span data-ttu-id="faa5a-158">예약된 검사 시간의 로컬 설정 오버라이드 구성</span><span class="sxs-lookup"><span data-stu-id="faa5a-158">Configure local setting override for scheduled scan time</span></span> | [<span data-ttu-id="faa5a-159">예약된 검사 구성</span><span class="sxs-lookup"><span data-stu-id="faa5a-159">Configure scheduled scans</span></span>](scheduled-catch-up-scans-microsoft-defender-antivirus.md)
<span data-ttu-id="faa5a-160">검사</span><span class="sxs-lookup"><span data-stu-id="faa5a-160">Scan</span></span> | <span data-ttu-id="faa5a-161">예약된 검사에 사용할 검사 유형에 대한 로컬 설정 오버라이드 구성</span><span class="sxs-lookup"><span data-stu-id="faa5a-161">Configure local setting override for the scan type to use for a scheduled scan</span></span> | [<span data-ttu-id="faa5a-162">예약된 검사 구성</span><span class="sxs-lookup"><span data-stu-id="faa5a-162">Configure scheduled scans</span></span>](scheduled-catch-up-scans-microsoft-defender-antivirus.md)

<a id="merge-lists"></a>

## <a name="configure-how-locally-and-globally-defined-threat-remediation-and-exclusions-lists-are-merged"></a><span data-ttu-id="faa5a-163">로컬 및 전역으로 정의된 위협 수정 및 제외 목록 병합 방법 구성</span><span class="sxs-lookup"><span data-stu-id="faa5a-163">Configure how locally and globally defined threat remediation and exclusions lists are merged</span></span>

<span data-ttu-id="faa5a-164">로컬로 정의된 목록을 전역적으로 정의된 목록과 결합하거나 병합하는 방법을 구성할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="faa5a-164">You can also configure how locally defined lists are combined or merged with globally defined lists.</span></span> <span data-ttu-id="faa5a-165">이 설정은 제외 [목록,](configure-exclusions-microsoft-defender-antivirus.md)지정된 [](configure-remediation-microsoft-defender-antivirus.md)수정 목록 및 공격 표면 감소에 [적용됩니다.](/windows/security/threat-protection/microsoft-defender-atp/attack-surface-reduction)</span><span class="sxs-lookup"><span data-stu-id="faa5a-165">This setting applies to [exclusion lists](configure-exclusions-microsoft-defender-antivirus.md), [specified remediation lists](configure-remediation-microsoft-defender-antivirus.md), and [attack surface reduction](/windows/security/threat-protection/microsoft-defender-atp/attack-surface-reduction).</span></span>

<span data-ttu-id="faa5a-166">기본적으로 로컬 그룹 정책 및 Windows 보안 앱에 구성된 목록은 네트워크에 배포한 적절한 그룹 정책 개체에 정의된 목록과 병합됩니다.</span><span class="sxs-lookup"><span data-stu-id="faa5a-166">By default, lists that have been configured in local group policy and the Windows Security app are merged with lists that are defined by the appropriate Group Policy Object that you have deployed on your network.</span></span> <span data-ttu-id="faa5a-167">충돌이 있는 경우 전역으로 정의된 목록이 우선합니다.</span><span class="sxs-lookup"><span data-stu-id="faa5a-167">Where there are conflicts, the globally-defined list takes precedence.</span></span>

<span data-ttu-id="faa5a-168">이 설정을 사용하지 않도록 설정하면 전역으로 정의된 목록(예: 배포된 GOS의 목록)만 사용되도록 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="faa5a-168">You can disable this setting to ensure that only globally-defined lists (such as those from any deployed GPOs) are used.</span></span>

### <a name="use-group-policy-to-disable-local-list-merging"></a><span data-ttu-id="faa5a-169">그룹 정책을 사용하여 로컬 목록의RG(로컬 목록)를 사용하지 않도록 설정</span><span class="sxs-lookup"><span data-stu-id="faa5a-169">Use Group Policy to disable local list merging</span></span>

1. <span data-ttu-id="faa5a-170">그룹 정책 관리 컴퓨터에서 그룹 [](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))정책 관리 콘솔을 열고 구성할 그룹 정책 개체를 마우스 오른쪽 단추로 클릭하고 편집을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="faa5a-170">On your Group Policy management computer, open the [Group Policy Management Console](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)), right-click the Group Policy Object you want to configure and click **Edit**.</span></span>

2. <span data-ttu-id="faa5a-171">그룹 정책 **관리 편집기에서** 컴퓨터 **구성으로 이동하여** 관리 템플릿 **을 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="faa5a-171">In the **Group Policy Management Editor** go to **Computer configuration** and click **Administrative templates**.</span></span>

3. <span data-ttu-id="faa5a-172">Microsoft Defender 바이러스 백신을 사용하여 Windows > **확장합니다.**</span><span class="sxs-lookup"><span data-stu-id="faa5a-172">Expand the tree to **Windows components > Microsoft Defender Antivirus**.</span></span>

4. <span data-ttu-id="faa5a-173">목록에 대해 **로컬 관리자 병합** 동작 구성을 두 번 클릭하고 옵션을 사용 안 **하도록 설정 합니다.**</span><span class="sxs-lookup"><span data-stu-id="faa5a-173">Double-click **Configure local administrator merge behavior for lists** and set the option to **Disabled**.</span></span> <span data-ttu-id="faa5a-174">**확인** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="faa5a-174">Click **OK**.</span></span>

> [!NOTE]
> <span data-ttu-id="faa5a-175">로컬 목록의 선택을 해제하면 제어된 폴더 액세스 설정이 다시 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="faa5a-175">If you disable local list merging, it will override controlled folder access settings.</span></span> <span data-ttu-id="faa5a-176">또한 로컬 관리자가 설정한 보호된 폴더 또는 허용된 앱을 모두 어버합니다.</span><span class="sxs-lookup"><span data-stu-id="faa5a-176">It also overrides any protected folders or allowed apps set by the local administrator.</span></span> <span data-ttu-id="faa5a-177">제어된 폴더 액세스 설정에 대한 자세한 내용은 Windows 보안에서 차단된 [앱 허용을 참조하세요.](https://support.microsoft.com/help/4046851/windows-10-allow-blocked-app-windows-security)</span><span class="sxs-lookup"><span data-stu-id="faa5a-177">For more information about controlled folder access settings, see [Allow a blocked app in Windows Security](https://support.microsoft.com/help/4046851/windows-10-allow-blocked-app-windows-security).</span></span>

## <a name="related-topics"></a><span data-ttu-id="faa5a-178">관련 항목</span><span class="sxs-lookup"><span data-stu-id="faa5a-178">Related topics</span></span>

- [<span data-ttu-id="faa5a-179">Windows 10의 Microsoft Defender 바이러스 백신</span><span class="sxs-lookup"><span data-stu-id="faa5a-179">Microsoft Defender Antivirus in Windows 10</span></span>](microsoft-defender-antivirus-in-windows-10.md)
- [<span data-ttu-id="faa5a-180">Microsoft Defender 바이러스 백신과 최종 사용자 상호 작용 구성</span><span class="sxs-lookup"><span data-stu-id="faa5a-180">Configure end-user interaction with Microsoft Defender Antivirus</span></span>](configure-end-user-interaction-microsoft-defender-antivirus.md)