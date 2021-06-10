---
title: Microsoft Defender 바이러스 백신 검색에 대한 수정 구성
description: 위협이 Microsoft Defender 바이러스 백신 감지할 때 어떤 작업을 해야 하는지와, 검지 폴더에 보관할 파일 보존 기간 구성
keywords: 수정, 수정, 제거, 위협, 검지, 검사, 복원
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: Normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 03/16/2021
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.topic: article
ms.openlocfilehash: 45886b94ec5ea11f01bfe23092eef4bd72691554
ms.sourcegitcommit: 51b316c23e070ab402a687f927e8fa01cb719c74
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/07/2021
ms.locfileid: "52274511"
---
# <a name="configure-remediation-for-microsoft-defender-antivirus-detections"></a><span data-ttu-id="64dc4-104">Microsoft Defender 바이러스 백신 검색에 대한 수정 구성</span><span class="sxs-lookup"><span data-stu-id="64dc4-104">Configure remediation for Microsoft Defender Antivirus detections</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="64dc4-105">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="64dc4-105">**Applies to:**</span></span>

- [<span data-ttu-id="64dc4-106">엔드포인트용 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="64dc4-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

<span data-ttu-id="64dc4-107">검색 Microsoft Defender 바이러스 백신 실행하면 검색된 위협을 수정하거나 제거하려고 시도합니다.</span><span class="sxs-lookup"><span data-stu-id="64dc4-107">When Microsoft Defender Antivirus runs a scan, it attempts to remediate or remove threats that are detected.</span></span> <span data-ttu-id="64dc4-108">특정 위협을 Microsoft Defender 바이러스 백신 방법, 수정 전에 복원 지점을 만들어야 하는지 여부 및 위협을 제거해야 하는 시점을 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="64dc4-108">You can configure how Microsoft Defender Antivirus should address certain threats, whether a restore point should be created before remediating, and when threats should be removed.</span></span>

<span data-ttu-id="64dc4-109">이 문서에서는 그룹 정책을 사용하여 이러한 설정을 구성하는 방법에 대해 설명하지만 [](/intune/device-restrictions-configure)를 사용하여 를 Microsoft Endpoint Configuration Manager [Microsoft Intune.](/configmgr/protect/deploy-use/endpoint-antimalware-policies#threat-overrides-settings)</span><span class="sxs-lookup"><span data-stu-id="64dc4-109">This article describes how to configure these settings by using Group Policy, but you can also use [Microsoft Endpoint Configuration Manager](/configmgr/protect/deploy-use/endpoint-antimalware-policies#threat-overrides-settings) and [Microsoft Intune](/intune/device-restrictions-configure).</span></span> 

<span data-ttu-id="64dc4-110">[ `Set-MpPreference` PowerShell cmdlet](/powershell/module/defender/set-mppreference) 또는 [ `MSFT_MpPreference` WMI](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal) 클래스를 사용하여 이러한 설정을 구성할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="64dc4-110">You can also use the [`Set-MpPreference` PowerShell cmdlet](/powershell/module/defender/set-mppreference) or [`MSFT_MpPreference` WMI class](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal) to configure these settings.</span></span>

## <a name="configure-remediation-options"></a><span data-ttu-id="64dc4-111">수정 옵션 구성</span><span class="sxs-lookup"><span data-stu-id="64dc4-111">Configure remediation options</span></span>

1. <span data-ttu-id="64dc4-112">그룹 정책 관리 컴퓨터에서 그룹 [](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))정책 관리 콘솔을 열고 구성할 그룹 정책 개체를 마우스 오른쪽 단추로 클릭하고 편집을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="64dc4-112">On your Group Policy management computer, open the [Group Policy Management Console](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)), right-click the Group Policy Object you want to configure and click **Edit**.</span></span>

2. <span data-ttu-id="64dc4-113">그룹 정책 **관리 편집기에서** 컴퓨터 **구성으로 이동하고** 관리 템플릿 **을 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="64dc4-113">In the **Group Policy Management Editor** go to **Computer configuration** and select **Administrative templates**.</span></span>

3. <span data-ttu-id="64dc4-114">트리를 확장하여 **Windows 구성 요소를 Microsoft Defender 바이러스 백신.**  >  </span><span class="sxs-lookup"><span data-stu-id="64dc4-114">Expand the tree to **Windows components** > **Microsoft Defender Antivirus**.</span></span> 

4. <span data-ttu-id="64dc4-115">아래 표를 사용하여 위치를 선택한 다음 필요한 경우 정책을 편집합니다.</span><span class="sxs-lookup"><span data-stu-id="64dc4-115">Using the table below, select a location, and then edit the policy as needed.</span></span> 

5. <span data-ttu-id="64dc4-116">**확인** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="64dc4-116">Select **OK**.</span></span>

|<span data-ttu-id="64dc4-117">위치</span><span class="sxs-lookup"><span data-stu-id="64dc4-117">Location</span></span> | <span data-ttu-id="64dc4-118">설정</span><span class="sxs-lookup"><span data-stu-id="64dc4-118">Setting</span></span> | <span data-ttu-id="64dc4-119">설명</span><span class="sxs-lookup"><span data-stu-id="64dc4-119">Description</span></span> | <span data-ttu-id="64dc4-120">기본 설정(구성되지 않은 경우)</span><span class="sxs-lookup"><span data-stu-id="64dc4-120">Default setting (if not configured)</span></span> |
|:---|:---|:---|:---|
|<span data-ttu-id="64dc4-121">검사</span><span class="sxs-lookup"><span data-stu-id="64dc4-121">Scan</span></span> | <span data-ttu-id="64dc4-122">시스템 복원 지점 만들기</span><span class="sxs-lookup"><span data-stu-id="64dc4-122">Create a system restore point</span></span> | <span data-ttu-id="64dc4-123">정리 또는 검사가 시도되기 전에 매일 시스템 복원 지점이 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="64dc4-123">A system restore point will be created each day before cleaning or scanning is attempted</span></span> | <span data-ttu-id="64dc4-124">사용 안 함</span><span class="sxs-lookup"><span data-stu-id="64dc4-124">Disabled</span></span>|
|<span data-ttu-id="64dc4-125">검사</span><span class="sxs-lookup"><span data-stu-id="64dc4-125">Scan</span></span> | <span data-ttu-id="64dc4-126">검사 기록 폴더에서 항목 제거 설정</span><span class="sxs-lookup"><span data-stu-id="64dc4-126">Turn on removal of items from scan history folder</span></span> | <span data-ttu-id="64dc4-127">검사 기록에 항목을 보관할 일 수 지정</span><span class="sxs-lookup"><span data-stu-id="64dc4-127">Specify how many days items should be kept in the scan history</span></span> | <span data-ttu-id="64dc4-128">30일</span><span class="sxs-lookup"><span data-stu-id="64dc4-128">30 days</span></span> |
|<span data-ttu-id="64dc4-129">루트</span><span class="sxs-lookup"><span data-stu-id="64dc4-129">Root</span></span> | <span data-ttu-id="64dc4-130">루틴 수정 끄기</span><span class="sxs-lookup"><span data-stu-id="64dc4-130">Turn off routine remediation</span></span> | <span data-ttu-id="64dc4-131">위협을 자동으로 Microsoft Defender 바이러스 백신 또는 끝점 사용자에게 어떤 작업을 해야 하는지 여부를 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="64dc4-131">You can specify whether Microsoft Defender Antivirus automatically remediates threats, or if it should ask the endpoint user what to do.</span></span> | <span data-ttu-id="64dc4-132">사용하지 않도록 설정(위협이 자동으로 수정)</span><span class="sxs-lookup"><span data-stu-id="64dc4-132">Disabled (threats are remediated automatically)</span></span> |
|<span data-ttu-id="64dc4-133">격리</span><span class="sxs-lookup"><span data-stu-id="64dc4-133">Quarantine</span></span> | <span data-ttu-id="64dc4-134">Quarantine 폴더에서 항목 제거 구성</span><span class="sxs-lookup"><span data-stu-id="64dc4-134">Configure removal of items from Quarantine folder</span></span> | <span data-ttu-id="64dc4-135">항목을 제거하기 전에 보관할 날짜 수 지정</span><span class="sxs-lookup"><span data-stu-id="64dc4-135">Specify how many days items should be kept in quarantine before being removed</span></span> | <span data-ttu-id="64dc4-136">90일</span><span class="sxs-lookup"><span data-stu-id="64dc4-136">90 days</span></span> |
|<span data-ttu-id="64dc4-137">위협</span><span class="sxs-lookup"><span data-stu-id="64dc4-137">Threats</span></span> | <span data-ttu-id="64dc4-138">감지 시 기본 작업을 수행하지 않을 위협 경고 수준 지정</span><span class="sxs-lookup"><span data-stu-id="64dc4-138">Specify threat alert levels at which default action should not be taken when detected</span></span> | <span data-ttu-id="64dc4-139">검색된 모든 위협에는 Microsoft Defender 바이러스 백신 수준(낮음, 중간, 높음 또는 심각)이 할당됩니다.</span><span class="sxs-lookup"><span data-stu-id="64dc4-139">Every threat that is detected by Microsoft Defender Antivirus is assigned a threat level (low, medium, high, or severe).</span></span> <span data-ttu-id="64dc4-140">이 설정을 사용하여 각 위협 수준에 대한 모든 위협을 수정하는 방법(분리, 제거 또는 무시)을 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="64dc4-140">You can use this setting to define how all threats for each of the threat levels should be remediated (quarantined, removed, or ignored)</span></span> | <span data-ttu-id="64dc4-141">해당 사항 없음</span><span class="sxs-lookup"><span data-stu-id="64dc4-141">Not applicable</span></span> |
|<span data-ttu-id="64dc4-142">위협</span><span class="sxs-lookup"><span data-stu-id="64dc4-142">Threats</span></span> | <span data-ttu-id="64dc4-143">검색 시 기본 작업을 수행하지 않을 위협 지정</span><span class="sxs-lookup"><span data-stu-id="64dc4-143">Specify threats upon which default action should not be taken when detected</span></span> | <span data-ttu-id="64dc4-144">특정 위협(위협 ID 사용)을 수정하는 방법을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="64dc4-144">Specify how specific threats (using their threat ID) should be remediated.</span></span> <span data-ttu-id="64dc4-145">특정 위협을 분리, 제거 또는 무시할지 여부를 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="64dc4-145">You can specify whether the specific threat should be quarantined, removed, or ignored</span></span> | <span data-ttu-id="64dc4-146">해당 사항 없음</span><span class="sxs-lookup"><span data-stu-id="64dc4-146">Not applicable</span></span> |

> [!IMPORTANT]
> <span data-ttu-id="64dc4-147">Microsoft Defender 바이러스 백신 요소를 기반으로 파일을 검색하고 수정합니다.</span><span class="sxs-lookup"><span data-stu-id="64dc4-147">Microsoft Defender Antivirus detects and remediates files based on many factors.</span></span> <span data-ttu-id="64dc4-148">경우에 따라 수정을 완료하려면 재부팅이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="64dc4-148">Sometimes, completing a remediation requires a reboot.</span></span> <span data-ttu-id="64dc4-149">검색이 나중에 가음성으로 확인된 경우에도 모든 추가 수정 단계가 완료되도록 재부팅을 완료해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="64dc4-149">Even if the detection is later determined to be a false positive, the reboot must be completed to ensure all additional remediation steps have been completed.</span></span>
>
> <span data-ttu-id="64dc4-150">가짓 긍정에 Microsoft Defender 바이러스 백신 파일을 검리한 특정 경우 장치를 다시 시작한 후 파일을 검지에서 복원할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="64dc4-150">If you are certain Microsoft Defender Antivirus quarantined a file based on a false positive, you can restore the file from quarantine after the device reboots.</span></span> <span data-ttu-id="64dc4-151">에서 [quarantined files in Microsoft Defender 바이러스 백신.](restore-quarantined-files-microsoft-defender-antivirus.md)</span><span class="sxs-lookup"><span data-stu-id="64dc4-151">See [Restore quarantined files in Microsoft Defender Antivirus](restore-quarantined-files-microsoft-defender-antivirus.md).</span></span>
> 
> <span data-ttu-id="64dc4-152">향후 이 문제를 방지하려면 검사에서 파일을 제외하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="64dc4-152">To avoid this problem in the future, you can exclude files from the scans.</span></span> <span data-ttu-id="64dc4-153">자세한 [내용은 Configure and validate exclusions for Microsoft Defender 바이러스 백신 참조.](configure-exclusions-microsoft-defender-antivirus.md)</span><span class="sxs-lookup"><span data-stu-id="64dc4-153">See [Configure and validate exclusions for Microsoft Defender Antivirus scans](configure-exclusions-microsoft-defender-antivirus.md).</span></span>

<span data-ttu-id="64dc4-154">자세한 [재구성](scheduled-catch-up-scans-microsoft-defender-antivirus.md#remed) 관련 설정에 대한 Microsoft Defender 바이러스 백신 필요한 예약된 전체 검사 구성을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="64dc4-154">Also see [Configure remediation-required scheduled full Microsoft Defender Antivirus scans](scheduled-catch-up-scans-microsoft-defender-antivirus.md#remed) for more remediation-related settings.</span></span>

## <a name="see-also"></a><span data-ttu-id="64dc4-155">참고 항목</span><span class="sxs-lookup"><span data-stu-id="64dc4-155">See also</span></span>

- [<span data-ttu-id="64dc4-156">Microsoft Defender 바이러스 백신 검사 옵션 구성</span><span class="sxs-lookup"><span data-stu-id="64dc4-156">Configure Microsoft Defender Antivirus scanning options</span></span>](configure-advanced-scan-types-microsoft-defender-antivirus.md)
- [<span data-ttu-id="64dc4-157">예약된 Microsoft Defender 바이러스 백신 구성</span><span class="sxs-lookup"><span data-stu-id="64dc4-157">Configure scheduled Microsoft Defender Antivirus scans</span></span>](scheduled-catch-up-scans-microsoft-defender-antivirus.md)
- [<span data-ttu-id="64dc4-158">요청 기반 Microsoft Defender 바이러스 백신 검사 구성 및 실행</span><span class="sxs-lookup"><span data-stu-id="64dc4-158">Configure and run on-demand Microsoft Defender Antivirus scans</span></span>](run-scan-microsoft-defender-antivirus.md)
- [<span data-ttu-id="64dc4-159">엔드포인트에 표시되는 알림 구성</span><span class="sxs-lookup"><span data-stu-id="64dc4-159">Configure the notifications that appear on endpoints</span></span>](configure-notifications-microsoft-defender-antivirus.md)
- [<span data-ttu-id="64dc4-160">최종 사용자 상호 작용 Microsoft Defender 바이러스 백신 구성</span><span class="sxs-lookup"><span data-stu-id="64dc4-160">Configure end-user Microsoft Defender Antivirus interaction</span></span>](configure-end-user-interaction-microsoft-defender-antivirus.md)
- [<span data-ttu-id="64dc4-161">사용자 지정, 시작 및 재구성 결과 Microsoft Defender 바이러스 백신 검토</span><span class="sxs-lookup"><span data-stu-id="64dc4-161">Customize, initiate, and review the results of Microsoft Defender Antivirus scans and remediation</span></span>](customize-run-review-remediate-scans-microsoft-defender-antivirus.md)
- [<span data-ttu-id="64dc4-162">Windows 10의 Microsoft Defender 바이러스 백신</span><span class="sxs-lookup"><span data-stu-id="64dc4-162">Microsoft Defender Antivirus in Windows 10</span></span>](microsoft-defender-antivirus-in-windows-10.md)