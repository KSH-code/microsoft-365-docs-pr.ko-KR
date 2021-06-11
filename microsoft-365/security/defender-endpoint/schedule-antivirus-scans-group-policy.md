---
title: 그룹 정책을 사용하여 바이러스 백신 검사 예약
description: 그룹 정책을 사용하여 바이러스 백신 검사 설정
keywords: 빠른 검사, 전체 검사, 일정, 그룹 정책, 바이러스 백신
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: Normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 06/09/2021
ms.reviewer: pauhijbr, ksarens
manager: dansimp
ms.technology: mde
ms.topic: how-to
ms.openlocfilehash: 6f6018ec8b514234ab4f98e3d5416b472ff88739
ms.sourcegitcommit: 337e8d8a2fee112d799edd8a0e04b3a2f124f900
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/10/2021
ms.locfileid: "52879748"
---
# <a name="schedule-antivirus-scans-using-group-policy"></a><span data-ttu-id="5e4cd-104">그룹 정책을 사용하여 바이러스 백신 검사 예약</span><span class="sxs-lookup"><span data-stu-id="5e4cd-104">Schedule antivirus scans using Group Policy</span></span>

<span data-ttu-id="5e4cd-105">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="5e4cd-105">**Applies to:**</span></span>

- [<span data-ttu-id="5e4cd-106">엔드포인트용 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="5e4cd-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

<span data-ttu-id="5e4cd-107">이 문서에서는 그룹 정책을 사용하여 예약된 검색을 구성하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="5e4cd-107">This article describes how to configure scheduled scans using Group Policy.</span></span> <span data-ttu-id="5e4cd-108">검사 예약 및 검사 유형에 대한 자세한 내용은 [Configure scheduled quick or full Microsoft Defender 바이러스 백신 scan을 참조합니다.](schedule-antivirus-scans.md)</span><span class="sxs-lookup"><span data-stu-id="5e4cd-108">To learn more about scheduling scans and about scan types, see [Configure scheduled quick or full Microsoft Defender Antivirus scans](schedule-antivirus-scans.md).</span></span> 

## <a name="configure-antivirus-scans-using-group-policy"></a><span data-ttu-id="5e4cd-109">그룹 정책을 사용하여 바이러스 백신 검사 구성</span><span class="sxs-lookup"><span data-stu-id="5e4cd-109">Configure antivirus scans using Group Policy</span></span>

1. <span data-ttu-id="5e4cd-110">그룹 정책 관리 컴퓨터의 그룹 정책 편집기에서 컴퓨터 구성 관리 템플릿 및 구성 요소 Windows   >    >    >  **검사로**  >  **Microsoft Defender 바이러스 백신 합니다.**</span><span class="sxs-lookup"><span data-stu-id="5e4cd-110">On your Group Policy management machine, in the Group Policy Editor, go to **Computer configuration** > **Administrative Templates** > **Windows Components** > **Microsoft Defender Antivirus** > **Scan**.</span></span>

2. <span data-ttu-id="5e4cd-111">구성할 그룹 정책 개체를 마우스 오른쪽 단추로 클릭한 다음 편집 **을 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="5e4cd-111">Right-click the Group Policy Object you want to configure, and then select **Edit**.</span></span>

3. <span data-ttu-id="5e4cd-112">그룹 정책 개체에 대한 설정을 지정하고 확인 을 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="5e4cd-112">Specify settings for the Group Policy Object, and then select **OK**.</span></span> 

4. <span data-ttu-id="5e4cd-113">구성할 각 설정에 대해 1-4단계를 반복합니다.</span><span class="sxs-lookup"><span data-stu-id="5e4cd-113">Repeat steps 1-4 for each setting you want to configure.</span></span>

5. <span data-ttu-id="5e4cd-114">일반적으로와 같은 그룹 정책 개체를 배포합니다.</span><span class="sxs-lookup"><span data-stu-id="5e4cd-114">Deploy your Group Policy Object as you normally do.</span></span> <span data-ttu-id="5e4cd-115">그룹 정책 개체에 대한 도움이 필요한 경우 그룹 정책 개체 [만들기를 참조합니다.](/windows/security/threat-protection/windows-firewall/create-a-group-policy-object)</span><span class="sxs-lookup"><span data-stu-id="5e4cd-115">If you need help with Group Policy Objects, see [Create a Group Policy Object](/windows/security/threat-protection/windows-firewall/create-a-group-policy-object).</span></span>

> [!TIP]
> <span data-ttu-id="5e4cd-116">보호 업데이트를 다운로드 [및](manage-protection-update-schedule-microsoft-defender-antivirus.md) 적용해야 하는 경우 관리 및 사용자가 정책 설정을 로컬로 수정할 수 있도록 허용 안 하도록 허용 항목을 [참조하세요.](configure-local-policy-overrides-microsoft-defender-antivirus.md)</span><span class="sxs-lookup"><span data-stu-id="5e4cd-116">See the [Manage when protection updates should be downloaded and applied](manage-protection-update-schedule-microsoft-defender-antivirus.md) and [Prevent or allow users to locally modify policy settings](configure-local-policy-overrides-microsoft-defender-antivirus.md) topics.</span></span>

## <a name="group-policy-settings-for-scheduling-scans"></a><span data-ttu-id="5e4cd-117">검사의 그룹 정책 설정</span><span class="sxs-lookup"><span data-stu-id="5e4cd-117">Group Policy settings for scheduling scans</span></span>

| <span data-ttu-id="5e4cd-118">위치</span><span class="sxs-lookup"><span data-stu-id="5e4cd-118">Location</span></span> | <span data-ttu-id="5e4cd-119">설정</span><span class="sxs-lookup"><span data-stu-id="5e4cd-119">Setting</span></span> | <span data-ttu-id="5e4cd-120">설명</span><span class="sxs-lookup"><span data-stu-id="5e4cd-120">Description</span></span> | <span data-ttu-id="5e4cd-121">기본 설정(구성되지 않은 경우)</span><span class="sxs-lookup"><span data-stu-id="5e4cd-121">Default setting (if not configured)</span></span> |
|:---|:---|:---|:---|
| <span data-ttu-id="5e4cd-122">검사</span><span class="sxs-lookup"><span data-stu-id="5e4cd-122">Scan</span></span> | <span data-ttu-id="5e4cd-123">예약된 검사에 사용할 검사 유형 지정</span><span class="sxs-lookup"><span data-stu-id="5e4cd-123">Specify the scan type to use for a scheduled scan</span></span> | <span data-ttu-id="5e4cd-124">빠른 검사</span><span class="sxs-lookup"><span data-stu-id="5e4cd-124">Quick scan</span></span> |
| <span data-ttu-id="5e4cd-125">검사</span><span class="sxs-lookup"><span data-stu-id="5e4cd-125">Scan</span></span> | <span data-ttu-id="5e4cd-126">예약된 검색을 실행할 날짜 지정</span><span class="sxs-lookup"><span data-stu-id="5e4cd-126">Specify the day of the week to run a scheduled scan</span></span> | <span data-ttu-id="5e4cd-127">검색을 실행할 날짜를 지정하거나 지정하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="5e4cd-127">Specify the day (or never) to run a scan.</span></span> | <span data-ttu-id="5e4cd-128">공개하지 않음</span><span class="sxs-lookup"><span data-stu-id="5e4cd-128">Never</span></span> |
| <span data-ttu-id="5e4cd-129">검사</span><span class="sxs-lookup"><span data-stu-id="5e4cd-129">Scan</span></span> | <span data-ttu-id="5e4cd-130">예약된 검색을 실행할 시간 지정</span><span class="sxs-lookup"><span data-stu-id="5e4cd-130">Specify the time of day to run a scheduled scan</span></span> | <span data-ttu-id="5e4cd-131">자정 이후의 시간(분)을 지정합니다(예: **60** :a.m.).</span><span class="sxs-lookup"><span data-stu-id="5e4cd-131">Specify the number of minutes after midnight (for example, enter **60** for 1 a.m.).</span></span> | <span data-ttu-id="5e4cd-132">2:a.m.</span><span class="sxs-lookup"><span data-stu-id="5e4cd-132">2 a.m.</span></span> |
| <span data-ttu-id="5e4cd-133">루트</span><span class="sxs-lookup"><span data-stu-id="5e4cd-133">Root</span></span> | <span data-ttu-id="5e4cd-134">예약된 작업 시간 임의로</span><span class="sxs-lookup"><span data-stu-id="5e4cd-134">Randomize scheduled task times</span></span> |<span data-ttu-id="5e4cd-135">이 Microsoft Defender 바이러스 백신 검사 시작 시간을 0시간에서 4시간 사이의 간격으로 임의로 임의로 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="5e4cd-135">In Microsoft Defender Antivirus, randomize the start time of the scan to any interval from 0 to 4 hours.</span></span> <p><span data-ttu-id="5e4cd-136">[SCEP에서](/mem/intune/protect/certificates-scep-configure)임의로 스캔을 30분을 더하거나 30분을 더한 간격으로 임의로 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="5e4cd-136">In [SCEP](/mem/intune/protect/certificates-scep-configure), randomize scans to any interval plus or minus 30 minutes.</span></span> <span data-ttu-id="5e4cd-137">이는 가상 컴퓨터 또는 VDI 배포에서 유용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5e4cd-137">This can be useful in virtual machines or VDI deployments.</span></span> | <span data-ttu-id="5e4cd-138">사용</span><span class="sxs-lookup"><span data-stu-id="5e4cd-138">Enabled</span></span> |

## <a name="group-policy-settings-for-scheduling-scans-for-when-an-endpoint-is-not-in-use"></a><span data-ttu-id="5e4cd-139">끝점이 사용되지 않는 경우 검색을 위한 그룹 정책 설정</span><span class="sxs-lookup"><span data-stu-id="5e4cd-139">Group Policy settings for scheduling scans for when an endpoint is not in use</span></span>

| <span data-ttu-id="5e4cd-140">위치</span><span class="sxs-lookup"><span data-stu-id="5e4cd-140">Location</span></span> | <span data-ttu-id="5e4cd-141">설정</span><span class="sxs-lookup"><span data-stu-id="5e4cd-141">Setting</span></span> | <span data-ttu-id="5e4cd-142">설명</span><span class="sxs-lookup"><span data-stu-id="5e4cd-142">Description</span></span> | <span data-ttu-id="5e4cd-143">기본 설정(구성되지 않은 경우)</span><span class="sxs-lookup"><span data-stu-id="5e4cd-143">Default setting (if not configured)</span></span> |
|:---|:---|:---|:---|
| <span data-ttu-id="5e4cd-144">검사</span><span class="sxs-lookup"><span data-stu-id="5e4cd-144">Scan</span></span> | <span data-ttu-id="5e4cd-145">컴퓨터가 사용 중이지만 사용 중이 아닌 경우만 예약된 검사 시작</span><span class="sxs-lookup"><span data-stu-id="5e4cd-145">Start the scheduled scan only when computer is on but not in use</span></span> | <span data-ttu-id="5e4cd-146">컴퓨터가 설정되지만 사용되지 않는 한 예약된 검사는 실행되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="5e4cd-146">Scheduled scans will not run, unless the computer is on but not in use</span></span> | <span data-ttu-id="5e4cd-147">사용</span><span class="sxs-lookup"><span data-stu-id="5e4cd-147">Enabled</span></span> |

> [!NOTE]
> <span data-ttu-id="5e4cd-148">끝점이 사용되지 않는 시간을 위해 검색을 예약하는 경우 검색은 CPU 스로틀 구성을 적용하지 못하며 가능한 한 빨리 검색을 완료하기 위해 사용 가능한 리소스를 최대한 활용합니다.</span><span class="sxs-lookup"><span data-stu-id="5e4cd-148">When you schedule scans for times when endpoints are not in use, scans do not honor the CPU throttling configuration and will take full advantage of the resources available to complete the scan as fast as possible.</span></span>

## <a name="group-policy-settings-for-scheduling-remediation-required-scans"></a><span data-ttu-id="5e4cd-149">재구성 필요 검사 예약을 위한 그룹 정책 설정</span><span class="sxs-lookup"><span data-stu-id="5e4cd-149">Group Policy settings for scheduling remediation-required scans</span></span>

| <span data-ttu-id="5e4cd-150">위치</span><span class="sxs-lookup"><span data-stu-id="5e4cd-150">Location</span></span> | <span data-ttu-id="5e4cd-151">설정</span><span class="sxs-lookup"><span data-stu-id="5e4cd-151">Setting</span></span> | <span data-ttu-id="5e4cd-152">설명</span><span class="sxs-lookup"><span data-stu-id="5e4cd-152">Description</span></span> | <span data-ttu-id="5e4cd-153">기본 설정(구성되지 않은 경우)</span><span class="sxs-lookup"><span data-stu-id="5e4cd-153">Default setting (if not configured)</span></span> |
|---|---|---|---|
| <span data-ttu-id="5e4cd-154">수정</span><span class="sxs-lookup"><span data-stu-id="5e4cd-154">Remediation</span></span> | <span data-ttu-id="5e4cd-155">재구성 완료를 위해 예약된 전체 검사 실행을 위해 주중 날짜 지정</span><span class="sxs-lookup"><span data-stu-id="5e4cd-155">Specify the day of the week to run a scheduled full scan to complete remediation</span></span> | <span data-ttu-id="5e4cd-156">검색을 실행할 날짜를 지정하거나 지정하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="5e4cd-156">Specify the day (or never) to run a scan.</span></span> | <span data-ttu-id="5e4cd-157">공개하지 않음</span><span class="sxs-lookup"><span data-stu-id="5e4cd-157">Never</span></span> |
| <span data-ttu-id="5e4cd-158">수정</span><span class="sxs-lookup"><span data-stu-id="5e4cd-158">Remediation</span></span> | <span data-ttu-id="5e4cd-159">재구성 완료를 위해 예약된 전체 검사 실행 시간을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="5e4cd-159">Specify the time of day to run a scheduled full scan to complete remediation</span></span> | <span data-ttu-id="5e4cd-160">자정 이후의 시간(분)을 지정합니다(예: **60** :a.m.)</span><span class="sxs-lookup"><span data-stu-id="5e4cd-160">Specify the number of minutes after midnight (for example, enter **60** for 1 a.m.)</span></span> | <span data-ttu-id="5e4cd-161">2:a.m.</span><span class="sxs-lookup"><span data-stu-id="5e4cd-161">2 a.m.</span></span> |

## <a name="group-policy-settings-for-scheduling-daily-scans"></a><span data-ttu-id="5e4cd-162">매일 검색을 위한 그룹 정책 설정</span><span class="sxs-lookup"><span data-stu-id="5e4cd-162">Group Policy settings for scheduling daily scans</span></span>

| <span data-ttu-id="5e4cd-163">위치</span><span class="sxs-lookup"><span data-stu-id="5e4cd-163">Location</span></span> | <span data-ttu-id="5e4cd-164">설정</span><span class="sxs-lookup"><span data-stu-id="5e4cd-164">Setting</span></span> | <span data-ttu-id="5e4cd-165">설명</span><span class="sxs-lookup"><span data-stu-id="5e4cd-165">Description</span></span> | <span data-ttu-id="5e4cd-166">기본 설정(구성되지 않은 경우)</span><span class="sxs-lookup"><span data-stu-id="5e4cd-166">Default setting (if not configured)</span></span> |
|:---|:---|:---|:---|
| <span data-ttu-id="5e4cd-167">검사</span><span class="sxs-lookup"><span data-stu-id="5e4cd-167">Scan</span></span> | <span data-ttu-id="5e4cd-168">매일 빠른 검색을 실행할 간격 지정</span><span class="sxs-lookup"><span data-stu-id="5e4cd-168">Specify the interval to run quick scans per day</span></span> | <span data-ttu-id="5e4cd-169">다음 빠른 검사 전에 경과해야 하는 시간을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="5e4cd-169">Specify how many hours should elapse before the next quick scan.</span></span> <span data-ttu-id="5e4cd-170">예를 들어 2시간마다 실행을 위해 **2를** 입력하고, 하루 한 번씩 **24를 입력합니다.**</span><span class="sxs-lookup"><span data-stu-id="5e4cd-170">For example, to run every two hours, enter **2**, for once a day, enter **24**.</span></span> <span data-ttu-id="5e4cd-171">**0을 입력하여** 매일 빠른 검색을 실행하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="5e4cd-171">Enter **0** to never run a daily quick scan.</span></span> | <span data-ttu-id="5e4cd-172">공개하지 않음</span><span class="sxs-lookup"><span data-stu-id="5e4cd-172">Never</span></span> |
| <span data-ttu-id="5e4cd-173">검사</span><span class="sxs-lookup"><span data-stu-id="5e4cd-173">Scan</span></span> | <span data-ttu-id="5e4cd-174">매일 빠른 검사에 대한 시간 지정</span><span class="sxs-lookup"><span data-stu-id="5e4cd-174">Specify the time for a daily quick scan</span></span> | <span data-ttu-id="5e4cd-175">자정 이후의 시간(분)을 지정합니다(예: **60** :a.m.)</span><span class="sxs-lookup"><span data-stu-id="5e4cd-175">Specify the number of minutes after midnight (for example, enter **60** for 1 a.m.)</span></span> | <span data-ttu-id="5e4cd-176">2:a.m.</span><span class="sxs-lookup"><span data-stu-id="5e4cd-176">2 a.m.</span></span> |

## <a name="group-policy-settings-for-scheduling-scans-after-protection-updates"></a><span data-ttu-id="5e4cd-177">보호 업데이트 후 검색을 위한 그룹 정책 설정</span><span class="sxs-lookup"><span data-stu-id="5e4cd-177">Group Policy settings for scheduling scans after protection updates</span></span>

| <span data-ttu-id="5e4cd-178">위치</span><span class="sxs-lookup"><span data-stu-id="5e4cd-178">Location</span></span> | <span data-ttu-id="5e4cd-179">설정</span><span class="sxs-lookup"><span data-stu-id="5e4cd-179">Setting</span></span> | <span data-ttu-id="5e4cd-180">설명</span><span class="sxs-lookup"><span data-stu-id="5e4cd-180">Description</span></span> | <span data-ttu-id="5e4cd-181">기본 설정(구성되지 않은 경우)</span><span class="sxs-lookup"><span data-stu-id="5e4cd-181">Default setting (if not configured)</span></span>|
|:---|:---|:---|:---|
| <span data-ttu-id="5e4cd-182">서명 업데이트</span><span class="sxs-lookup"><span data-stu-id="5e4cd-182">Signature updates</span></span> | <span data-ttu-id="5e4cd-183">보안 인텔리전스 업데이트 후 검사 켜기</span><span class="sxs-lookup"><span data-stu-id="5e4cd-183">Turn on scan after Security intelligence update</span></span> | <span data-ttu-id="5e4cd-184">검사는 새 보호 업데이트가 다운로드된 직후에 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="5e4cd-184">A scan will occur immediately after a new protection update is downloaded</span></span> | <span data-ttu-id="5e4cd-185">사용</span><span class="sxs-lookup"><span data-stu-id="5e4cd-185">Enabled</span></span> |

