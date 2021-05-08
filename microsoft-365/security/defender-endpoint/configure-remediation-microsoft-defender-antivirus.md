---
title: Microsoft Defender 바이러스 백신 검색에 대한 수정 구성
description: 위협을 감지할 때 Microsoft Defender 바이러스 백신이 어떤 작업을 해야 하는지, 그리고 분리된 파일을 검지 폴더에 보존해야 하는 기간 구성
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
# <a name="configure-remediation-for-microsoft-defender-antivirus-detections"></a><span data-ttu-id="47f2a-104">Microsoft Defender 바이러스 백신 검색에 대한 수정 구성</span><span class="sxs-lookup"><span data-stu-id="47f2a-104">Configure remediation for Microsoft Defender Antivirus detections</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="47f2a-105">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="47f2a-105">**Applies to:**</span></span>

- [<span data-ttu-id="47f2a-106">엔드포인트용 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="47f2a-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

<span data-ttu-id="47f2a-107">Microsoft Defender 바이러스 백신이 검색을 실행하면 감지된 위협을 수정하거나 제거하려고 시도합니다.</span><span class="sxs-lookup"><span data-stu-id="47f2a-107">When Microsoft Defender Antivirus runs a scan, it attempts to remediate or remove threats that are detected.</span></span> <span data-ttu-id="47f2a-108">Microsoft Defender 바이러스 백신이 특정 위협을 어떻게 해결해야 하는지, 수정하기 전에 복원 지점을 만들어야 하는지 여부 및 위협을 제거해야 하는 시점을 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="47f2a-108">You can configure how Microsoft Defender Antivirus should address certain threats, whether a restore point should be created before remediating, and when threats should be removed.</span></span>

<span data-ttu-id="47f2a-109">이 문서에서는 그룹 정책을 사용하여 이러한 설정을 구성하는 방법에 대해 설명하지만 [Microsoft Endpoint Configuration Manager](/configmgr/protect/deploy-use/endpoint-antimalware-policies#threat-overrides-settings) 및 Microsoft [Intune을](/intune/device-restrictions-configure)사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="47f2a-109">This article describes how to configure these settings by using Group Policy, but you can also use [Microsoft Endpoint Configuration Manager](/configmgr/protect/deploy-use/endpoint-antimalware-policies#threat-overrides-settings) and [Microsoft Intune](/intune/device-restrictions-configure).</span></span> 

<span data-ttu-id="47f2a-110">[ `Set-MpPreference` PowerShell cmdlet](/powershell/module/defender/set-mppreference) 또는 [ `MSFT_MpPreference` WMI](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal) 클래스를 사용하여 이러한 설정을 구성할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="47f2a-110">You can also use the [`Set-MpPreference` PowerShell cmdlet](/powershell/module/defender/set-mppreference) or [`MSFT_MpPreference` WMI class](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal) to configure these settings.</span></span>

## <a name="configure-remediation-options"></a><span data-ttu-id="47f2a-111">수정 옵션 구성</span><span class="sxs-lookup"><span data-stu-id="47f2a-111">Configure remediation options</span></span>

1. <span data-ttu-id="47f2a-112">그룹 정책 관리 컴퓨터에서 그룹 [](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))정책 관리 콘솔을 열고 구성할 그룹 정책 개체를 마우스 오른쪽 단추로 클릭하고 편집을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="47f2a-112">On your Group Policy management computer, open the [Group Policy Management Console](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)), right-click the Group Policy Object you want to configure and click **Edit**.</span></span>

2. <span data-ttu-id="47f2a-113">그룹 정책 **관리 편집기에서** 컴퓨터 **구성으로 이동하고** 관리 템플릿 **을 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="47f2a-113">In the **Group Policy Management Editor** go to **Computer configuration** and select **Administrative templates**.</span></span>

3. <span data-ttu-id="47f2a-114">Windows 구성 요소 Microsoft Defender **바이러스 백신까지**  >  **트리를 확장합니다.**</span><span class="sxs-lookup"><span data-stu-id="47f2a-114">Expand the tree to **Windows components** > **Microsoft Defender Antivirus**.</span></span> 

4. <span data-ttu-id="47f2a-115">아래 표를 사용하여 위치를 선택한 다음 필요한 경우 정책을 편집합니다.</span><span class="sxs-lookup"><span data-stu-id="47f2a-115">Using the table below, select a location, and then edit the policy as needed.</span></span> 

5. <span data-ttu-id="47f2a-116">**확인** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="47f2a-116">Select **OK**.</span></span>

|<span data-ttu-id="47f2a-117">위치</span><span class="sxs-lookup"><span data-stu-id="47f2a-117">Location</span></span> | <span data-ttu-id="47f2a-118">설정</span><span class="sxs-lookup"><span data-stu-id="47f2a-118">Setting</span></span> | <span data-ttu-id="47f2a-119">설명</span><span class="sxs-lookup"><span data-stu-id="47f2a-119">Description</span></span> | <span data-ttu-id="47f2a-120">기본 설정(구성되지 않은 경우)</span><span class="sxs-lookup"><span data-stu-id="47f2a-120">Default setting (if not configured)</span></span> |
|:---|:---|:---|:---|
|<span data-ttu-id="47f2a-121">검사</span><span class="sxs-lookup"><span data-stu-id="47f2a-121">Scan</span></span> | <span data-ttu-id="47f2a-122">시스템 복원 지점 만들기</span><span class="sxs-lookup"><span data-stu-id="47f2a-122">Create a system restore point</span></span> | <span data-ttu-id="47f2a-123">정리 또는 검사가 시도되기 전에 매일 시스템 복원 지점이 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="47f2a-123">A system restore point will be created each day before cleaning or scanning is attempted</span></span> | <span data-ttu-id="47f2a-124">사용 안 함</span><span class="sxs-lookup"><span data-stu-id="47f2a-124">Disabled</span></span>|
|<span data-ttu-id="47f2a-125">검사</span><span class="sxs-lookup"><span data-stu-id="47f2a-125">Scan</span></span> | <span data-ttu-id="47f2a-126">검사 기록 폴더에서 항목 제거 설정</span><span class="sxs-lookup"><span data-stu-id="47f2a-126">Turn on removal of items from scan history folder</span></span> | <span data-ttu-id="47f2a-127">검사 기록에 항목을 보관할 일 수 지정</span><span class="sxs-lookup"><span data-stu-id="47f2a-127">Specify how many days items should be kept in the scan history</span></span> | <span data-ttu-id="47f2a-128">30일</span><span class="sxs-lookup"><span data-stu-id="47f2a-128">30 days</span></span> |
|<span data-ttu-id="47f2a-129">루트</span><span class="sxs-lookup"><span data-stu-id="47f2a-129">Root</span></span> | <span data-ttu-id="47f2a-130">루틴 수정 끄기</span><span class="sxs-lookup"><span data-stu-id="47f2a-130">Turn off routine remediation</span></span> | <span data-ttu-id="47f2a-131">Microsoft Defender 바이러스 백신이 위협을 자동으로 수정하는지 또는 끝점 사용자에게 어떤 작업을 해야 하는지 여부를 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="47f2a-131">You can specify whether Microsoft Defender Antivirus automatically remediates threats, or if it should ask the endpoint user what to do.</span></span> | <span data-ttu-id="47f2a-132">사용하지 않도록 설정(위협이 자동으로 수정)</span><span class="sxs-lookup"><span data-stu-id="47f2a-132">Disabled (threats are remediated automatically)</span></span> |
|<span data-ttu-id="47f2a-133">격리</span><span class="sxs-lookup"><span data-stu-id="47f2a-133">Quarantine</span></span> | <span data-ttu-id="47f2a-134">Quarantine 폴더에서 항목 제거 구성</span><span class="sxs-lookup"><span data-stu-id="47f2a-134">Configure removal of items from Quarantine folder</span></span> | <span data-ttu-id="47f2a-135">항목을 제거하기 전에 보관할 날짜 수 지정</span><span class="sxs-lookup"><span data-stu-id="47f2a-135">Specify how many days items should be kept in quarantine before being removed</span></span> | <span data-ttu-id="47f2a-136">90일</span><span class="sxs-lookup"><span data-stu-id="47f2a-136">90 days</span></span> |
|<span data-ttu-id="47f2a-137">위협</span><span class="sxs-lookup"><span data-stu-id="47f2a-137">Threats</span></span> | <span data-ttu-id="47f2a-138">감지 시 기본 작업을 수행하지 않을 위협 경고 수준 지정</span><span class="sxs-lookup"><span data-stu-id="47f2a-138">Specify threat alert levels at which default action should not be taken when detected</span></span> | <span data-ttu-id="47f2a-139">Microsoft Defender 바이러스 백신에서 감지되는 모든 위협에는 위협 수준(낮음, 중간, 높음 또는 심각)이 할당됩니다.</span><span class="sxs-lookup"><span data-stu-id="47f2a-139">Every threat that is detected by Microsoft Defender Antivirus is assigned a threat level (low, medium, high, or severe).</span></span> <span data-ttu-id="47f2a-140">이 설정을 사용하여 각 위협 수준에 대한 모든 위협을 수정하는 방법(분리, 제거 또는 무시)을 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="47f2a-140">You can use this setting to define how all threats for each of the threat levels should be remediated (quarantined, removed, or ignored)</span></span> | <span data-ttu-id="47f2a-141">해당 사항 없음</span><span class="sxs-lookup"><span data-stu-id="47f2a-141">Not applicable</span></span> |
|<span data-ttu-id="47f2a-142">위협</span><span class="sxs-lookup"><span data-stu-id="47f2a-142">Threats</span></span> | <span data-ttu-id="47f2a-143">검색 시 기본 작업을 수행하지 않을 위협 지정</span><span class="sxs-lookup"><span data-stu-id="47f2a-143">Specify threats upon which default action should not be taken when detected</span></span> | <span data-ttu-id="47f2a-144">특정 위협(위협 ID 사용)을 수정하는 방법을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="47f2a-144">Specify how specific threats (using their threat ID) should be remediated.</span></span> <span data-ttu-id="47f2a-145">특정 위협을 분리, 제거 또는 무시할지 여부를 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="47f2a-145">You can specify whether the specific threat should be quarantined, removed, or ignored</span></span> | <span data-ttu-id="47f2a-146">해당 사항 없음</span><span class="sxs-lookup"><span data-stu-id="47f2a-146">Not applicable</span></span> |

> [!IMPORTANT]
> <span data-ttu-id="47f2a-147">Microsoft Defender 바이러스 백신은 여러 요인에 따라 파일을 검색하고 수정합니다.</span><span class="sxs-lookup"><span data-stu-id="47f2a-147">Microsoft Defender Antivirus detects and remediates files based on many factors.</span></span> <span data-ttu-id="47f2a-148">경우에 따라 수정을 완료하려면 재부팅이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="47f2a-148">Sometimes, completing a remediation requires a reboot.</span></span> <span data-ttu-id="47f2a-149">검색이 나중에 가음성으로 확인된 경우에도 모든 추가 수정 단계가 완료되도록 재부팅을 완료해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="47f2a-149">Even if the detection is later determined to be a false positive, the reboot must be completed to ensure all additional remediation steps have been completed.</span></span>
>
> <span data-ttu-id="47f2a-150">특정 Microsoft Defender 바이러스 백신이 가변 긍정에 따라 파일을 검지한 경우 장치를 다시 시작한 후 파일을 검지에서 복원할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="47f2a-150">If you are certain Microsoft Defender Antivirus quarantined a file based on a false positive, you can restore the file from quarantine after the device reboots.</span></span> <span data-ttu-id="47f2a-151">Microsoft Defender 바이러스 [백신에서 quarantined 파일 복원을 참조합니다.](restore-quarantined-files-microsoft-defender-antivirus.md)</span><span class="sxs-lookup"><span data-stu-id="47f2a-151">See [Restore quarantined files in Microsoft Defender Antivirus](restore-quarantined-files-microsoft-defender-antivirus.md).</span></span>
> 
> <span data-ttu-id="47f2a-152">향후 이 문제를 방지하려면 검사에서 파일을 제외하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="47f2a-152">To avoid this problem in the future, you can exclude files from the scans.</span></span> <span data-ttu-id="47f2a-153">Microsoft Defender 바이러스 백신 검사에 대한 제외 구성 [및 유효성 검사를 참조합니다.](configure-exclusions-microsoft-defender-antivirus.md)</span><span class="sxs-lookup"><span data-stu-id="47f2a-153">See [Configure and validate exclusions for Microsoft Defender Antivirus scans](configure-exclusions-microsoft-defender-antivirus.md).</span></span>

<span data-ttu-id="47f2a-154">또한 [수정이](scheduled-catch-up-scans-microsoft-defender-antivirus.md#remed) 필요한 예약된 전체 Microsoft Defender 바이러스 백신 검사 구성을 참조하여 수정 관련 설정을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="47f2a-154">Also see [Configure remediation-required scheduled full Microsoft Defender Antivirus scans](scheduled-catch-up-scans-microsoft-defender-antivirus.md#remed) for more remediation-related settings.</span></span>

## <a name="see-also"></a><span data-ttu-id="47f2a-155">참고 항목</span><span class="sxs-lookup"><span data-stu-id="47f2a-155">See also</span></span>

- [<span data-ttu-id="47f2a-156">Microsoft Defender 바이러스 백신 검사 옵션 구성</span><span class="sxs-lookup"><span data-stu-id="47f2a-156">Configure Microsoft Defender Antivirus scanning options</span></span>](configure-advanced-scan-types-microsoft-defender-antivirus.md)
- [<span data-ttu-id="47f2a-157">예약된 Microsoft Defender 바이러스 백신 검사 구성</span><span class="sxs-lookup"><span data-stu-id="47f2a-157">Configure scheduled Microsoft Defender Antivirus scans</span></span>](scheduled-catch-up-scans-microsoft-defender-antivirus.md)
- [<span data-ttu-id="47f2a-158">요청 기반 Microsoft Defender 바이러스 백신 검사 구성 및 실행</span><span class="sxs-lookup"><span data-stu-id="47f2a-158">Configure and run on-demand Microsoft Defender Antivirus scans</span></span>](run-scan-microsoft-defender-antivirus.md)
- [<span data-ttu-id="47f2a-159">끝점에 나타나는 알림 구성</span><span class="sxs-lookup"><span data-stu-id="47f2a-159">Configure the notifications that appear on endpoints</span></span>](configure-notifications-microsoft-defender-antivirus.md)
- [<span data-ttu-id="47f2a-160">최종 사용자 Microsoft Defender 바이러스 백신 상호 작용 구성</span><span class="sxs-lookup"><span data-stu-id="47f2a-160">Configure end-user Microsoft Defender Antivirus interaction</span></span>](configure-end-user-interaction-microsoft-defender-antivirus.md)
- [<span data-ttu-id="47f2a-161">Microsoft Defender 바이러스 백신 검사 및 수정 사용자 지정, 시작 및 결과 검토</span><span class="sxs-lookup"><span data-stu-id="47f2a-161">Customize, initiate, and review the results of Microsoft Defender Antivirus scans and remediation</span></span>](customize-run-review-remediate-scans-microsoft-defender-antivirus.md)
- [<span data-ttu-id="47f2a-162">Windows 10의 Microsoft Defender 바이러스 백신</span><span class="sxs-lookup"><span data-stu-id="47f2a-162">Microsoft Defender Antivirus in Windows 10</span></span>](microsoft-defender-antivirus-in-windows-10.md)