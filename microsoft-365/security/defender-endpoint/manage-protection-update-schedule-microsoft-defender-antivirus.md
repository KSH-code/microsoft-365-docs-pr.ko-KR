---
title: Microsoft Defender 바이러스 백신 보호 업데이트 예약
description: 보호 업데이트를 다운로드해야 하는 시기에 대한 일, 시간 및 간격 예약
keywords: 업데이트, 보안 기준, 업데이트 예약
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
search.appverid: met150
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: normal
ms.topic: article
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.reviewer: pahuijbr
manager: dansimp
ms.technology: mde
ms.openlocfilehash: abb656586d6a7bd779b109fcad3c777016fef980
ms.sourcegitcommit: be929f79751c0c52dfa6bd98a854432a0c63faf0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/14/2021
ms.locfileid: "52926058"
---
# <a name="manage-the-schedule-for-when-protection-updates-should-be-downloaded-and-applied"></a><span data-ttu-id="b85c3-104">보호 업데이트를 다운로드하여 적용해야 하는 경우에 대한 예약 관리</span><span class="sxs-lookup"><span data-stu-id="b85c3-104">Manage the schedule for when protection updates should be downloaded and applied</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="b85c3-105">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="b85c3-105">**Applies to:**</span></span>

- [<span data-ttu-id="b85c3-106">엔드포인트용 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="b85c3-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

<span data-ttu-id="b85c3-107">Microsoft Defender 바이러스 백신 업데이트를 찾아 다운로드해야 하는 경우를 결정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b85c3-107">Microsoft Defender Antivirus lets you determine when it should look for and download updates.</span></span>

<span data-ttu-id="b85c3-108">다음을 통해 끝점에 대한 업데이트를 예약할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b85c3-108">You can schedule updates for your endpoints by:</span></span> 

- <span data-ttu-id="b85c3-109">보호 업데이트를 확인할 날짜 지정</span><span class="sxs-lookup"><span data-stu-id="b85c3-109">Specifying the day of the week to check for protection updates</span></span> 
- <span data-ttu-id="b85c3-110">보호 업데이트를 확인할 간격 지정</span><span class="sxs-lookup"><span data-stu-id="b85c3-110">Specifying the interval to check for protection updates</span></span>
- <span data-ttu-id="b85c3-111">보호 업데이트를 확인할 시간 지정</span><span class="sxs-lookup"><span data-stu-id="b85c3-111">Specifying the time to check for protection updates</span></span>

<span data-ttu-id="b85c3-112">또한 각 끝점에서 보호 업데이트를 확인하고 다운로드하는 시간을 임의로 정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b85c3-112">You can also randomize the times when each endpoint checks and downloads protection updates.</span></span> <span data-ttu-id="b85c3-113">자세한 내용은 [Schedule scans](scheduled-catch-up-scans-microsoft-defender-antivirus.md) 항목을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="b85c3-113">See the [Schedule scans](scheduled-catch-up-scans-microsoft-defender-antivirus.md) topic for more information.</span></span>

## <a name="use-configuration-manager-to-schedule-protection-updates"></a><span data-ttu-id="b85c3-114">Configuration Manager를 사용하여 보호 업데이트 예약</span><span class="sxs-lookup"><span data-stu-id="b85c3-114">Use Configuration Manager to schedule protection updates</span></span>

1.  <span data-ttu-id="b85c3-115">Microsoft Endpoint Manager 콘솔에서 변경할 맬웨어 방지 정책을 열고(왼쪽의 탐색 창에서 자산 및 규정 준수를 클릭한 다음 개요 Endpoint Protection 맬웨어 방지 정책)   >    >  </span><span class="sxs-lookup"><span data-stu-id="b85c3-115">On your Microsoft Endpoint Manager console, open the antimalware policy you want to change (click **Assets and Compliance** in the navigation pane on the left, then expand the tree to **Overview** > **Endpoint Protection** > **Antimalware Policies**)</span></span>

2.  <span data-ttu-id="b85c3-116">보안 **인텔리전스 업데이트 섹션으로** 이동하세요.</span><span class="sxs-lookup"><span data-stu-id="b85c3-116">Go to the **Security intelligence updates** section.</span></span>

3. <span data-ttu-id="b85c3-117">특정 시기에 업데이트를 확인하고 다운로드하려면</span><span class="sxs-lookup"><span data-stu-id="b85c3-117">To check and download updates at a certain time:</span></span>
      1. <span data-ttu-id="b85c3-118">특정 Endpoint Protection **보안** 인텔리전스 업데이트 **확인...을 0으로 설정하세요.**</span><span class="sxs-lookup"><span data-stu-id="b85c3-118">Set **Check for Endpoint Protection security intelligence updates at a specific interval...** to **0**.</span></span>
      2. <span data-ttu-id="b85c3-119">매일 **Endpoint Protection 보안 인텔리전스** 업데이트 확인...을 업데이트 확인 시간으로 설정하세요.</span><span class="sxs-lookup"><span data-stu-id="b85c3-119">Set **Check for Endpoint Protection security intelligence updates daily at...** to the time when updates should be checked.</span></span>
      <span data-ttu-id="b85c3-120">3</span><span class="sxs-lookup"><span data-stu-id="b85c3-120">3</span></span>
4. <span data-ttu-id="b85c3-121">지속적인 간격으로 업데이트를 확인하고 다운로드하려면 특정 간격으로 Endpoint Protection 보안 인텔리전스 업데이트 **확인...을** 업데이트 간에 발생해야 하는 시간으로 설정하세요.</span><span class="sxs-lookup"><span data-stu-id="b85c3-121">To check and download updates on a continual interval, Set **Check for Endpoint Protection security intelligence updates at a specific interval...** to the number of hours that should occur between updates.</span></span>

5.  <span data-ttu-id="b85c3-122">[평소와 같이 업데이트된 정책을 배포합니다.](/sccm/protect/deploy-use/endpoint-antimalware-policies#deploy-an-antimalware-policy-to-client-computers)</span><span class="sxs-lookup"><span data-stu-id="b85c3-122">[Deploy the updated policy as usual](/sccm/protect/deploy-use/endpoint-antimalware-policies#deploy-an-antimalware-policy-to-client-computers).</span></span>

## <a name="use-group-policy-to-schedule-protection-updates"></a><span data-ttu-id="b85c3-123">그룹 정책을 사용하여 보호 업데이트 예약</span><span class="sxs-lookup"><span data-stu-id="b85c3-123">Use Group Policy to schedule protection updates</span></span>

> [!IMPORTANT]
> <span data-ttu-id="b85c3-124">기본적으로 Microsoft Defender 바이러스 백신 검사 시간이 15분 전에 업데이트가 확인됩니다.</span><span class="sxs-lookup"><span data-stu-id="b85c3-124">By default, Microsoft Defender Antivirus will check for an update 15 minutes before the time of any scheduled scans.</span></span> <span data-ttu-id="b85c3-125">이러한 설정을 사용하도록 설정하면 해당 기본값이 다시 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="b85c3-125">Enabling these settings will override that default.</span></span>

1.  <span data-ttu-id="b85c3-126">그룹 정책 관리 컴퓨터의 [](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))그룹 정책 관리 콘솔을 열고 구성할 그룹 정책 개체를 마우스 오른쪽 단추로 클릭하고 편집을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="b85c3-126">On your Group Policy management machine, open the [Group Policy Management Console](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)), right-click the Group Policy Object you want to configure and click **Edit**.</span></span>

3.  <span data-ttu-id="b85c3-127">그룹 정책 **관리 편집기에서** 컴퓨터 **구성으로 이동하십시오.**</span><span class="sxs-lookup"><span data-stu-id="b85c3-127">In the **Group Policy Management Editor** go to **Computer configuration**.</span></span>

4.  <span data-ttu-id="b85c3-128">정책을 **클릭한** 다음 **관리 템플릿을 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="b85c3-128">Click **Policies** then **Administrative templates**.</span></span>

5.  <span data-ttu-id="b85c3-129">서명 **인텔리전스 Windows 구성 Microsoft Defender 바이러스 백신** 구성 요소를  >    >  **확장하고** 다음 설정을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="b85c3-129">Expand the tree to **Windows components** > **Microsoft Defender Antivirus** > **Signature Intelligence Updates** and configure the following settings:</span></span>

    1. <span data-ttu-id="b85c3-130">보안 인텔리전스 업데이트를 확인할 날짜 지정 설정을 두 번 클릭하고 옵션을 사용으로 **설정합니다.** </span><span class="sxs-lookup"><span data-stu-id="b85c3-130">Double-click the **Specify the day of the week to check for security intelligence updates** setting and set the option to **Enabled**.</span></span> <span data-ttu-id="b85c3-131">업데이트를 확인할 주 중일을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="b85c3-131">Enter the day of the week to check for updates.</span></span> <span data-ttu-id="b85c3-132">**확인** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="b85c3-132">Click **OK**.</span></span>
    2. <span data-ttu-id="b85c3-133">보안 인텔리전스 업데이트를 확인할 간격 지정 설정을 두 번 클릭하고 옵션을 사용으로 **설정합니다.** </span><span class="sxs-lookup"><span data-stu-id="b85c3-133">Double-click the **Specify the interval to check for security intelligence updates** setting and set the option to **Enabled**.</span></span> <span data-ttu-id="b85c3-134">업데이트 사이의 시간을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="b85c3-134">Enter the number of hours between updates.</span></span> <span data-ttu-id="b85c3-135">**확인** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="b85c3-135">Click **OK**.</span></span>
    3. <span data-ttu-id="b85c3-136">보안 인텔리전스 업데이트를 확인할 시간 지정 설정을 두 번 클릭하고 옵션을 사용으로 **설정합니다.** </span><span class="sxs-lookup"><span data-stu-id="b85c3-136">Double-click the **Specify the time to check for security intelligence updates** setting and set the option to **Enabled**.</span></span> <span data-ttu-id="b85c3-137">업데이트를 확인할 시간을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="b85c3-137">Enter the time when updates should be checked.</span></span> <span data-ttu-id="b85c3-138">시간은 끝점의 로컬 시간을 기반으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="b85c3-138">The time is based on the local time of the endpoint.</span></span> <span data-ttu-id="b85c3-139">**확인** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="b85c3-139">Click **OK**.</span></span>


## <a name="use-powershell-cmdlets-to-schedule-protection-updates"></a><span data-ttu-id="b85c3-140">PowerShell cmdlet을 사용하여 보호 업데이트 예약</span><span class="sxs-lookup"><span data-stu-id="b85c3-140">Use PowerShell cmdlets to schedule protection updates</span></span>

<span data-ttu-id="b85c3-141">다음 cmdlet을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="b85c3-141">Use the following cmdlets:</span></span>

```PowerShell
Set-MpPreference -SignatureScheduleDay
Set-MpPreference -SignatureScheduleTime
Set-MpPreference -SignatureUpdateInterval
```

<span data-ttu-id="b85c3-142">PowerShell과 함께 PowerShell을 사용하는 방법에 대한 자세한 내용은 [PowerShell cmdlet을](use-powershell-cmdlets-microsoft-defender-antivirus.md) 사용하여 Microsoft Defender 바이러스 백신 및 [Defender cmdlet을](/powershell/module/defender/) 구성하고 실행을 Microsoft Defender 바이러스 백신.</span><span class="sxs-lookup"><span data-stu-id="b85c3-142">See [Use PowerShell cmdlets to configure and run Microsoft Defender Antivirus](use-powershell-cmdlets-microsoft-defender-antivirus.md)  and [Defender cmdlets](/powershell/module/defender/) for more information on how to use PowerShell with Microsoft Defender Antivirus.</span></span>

## <a name="use-windows-management-instruction-wmi-to-schedule-protection-updates"></a><span data-ttu-id="b85c3-143">WMI(Windows 관리 명령)를 사용하여 보호 업데이트 예약</span><span class="sxs-lookup"><span data-stu-id="b85c3-143">Use Windows Management Instruction (WMI) to schedule protection updates</span></span>

<span data-ttu-id="b85c3-144">다음 [  속성에 MSFT_MpPreference  ](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) 클래스의 Set 메서드를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="b85c3-144">Use the [**Set** method of the **MSFT_MpPreference**](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) class for the following properties:</span></span>

```WMI
SignatureScheduleDay
SignatureScheduleTime
SignatureUpdateInterval
```

<span data-ttu-id="b85c3-145">자세한 정보 및 허용되는 매개 변수는 다음을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="b85c3-145">See the following for more information and allowed parameters:</span></span>
- [<span data-ttu-id="b85c3-146">Windows Defender WMIv2 API</span><span class="sxs-lookup"><span data-stu-id="b85c3-146">Windows Defender WMIv2 APIs</span></span>](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)


## <a name="related-articles"></a><span data-ttu-id="b85c3-147">관련 문서</span><span class="sxs-lookup"><span data-stu-id="b85c3-147">Related articles</span></span>

- [<span data-ttu-id="b85c3-148">배포 Microsoft Defender 바이러스 백신</span><span class="sxs-lookup"><span data-stu-id="b85c3-148">Deploy Microsoft Defender Antivirus</span></span>](deploy-manage-report-microsoft-defender-antivirus.md)
- [<span data-ttu-id="b85c3-149">업데이트 Microsoft Defender 바이러스 백신 관리하고 기준 적용</span><span class="sxs-lookup"><span data-stu-id="b85c3-149">Manage Microsoft Defender Antivirus updates and apply baselines</span></span>](manage-updates-baselines-microsoft-defender-antivirus.md)
- [<span data-ttu-id="b85c3-150">최신이 지난 끝점에 대한 업데이트 관리</span><span class="sxs-lookup"><span data-stu-id="b85c3-150">Manage updates for endpoints that are out of date</span></span>](manage-outdated-endpoints-microsoft-defender-antivirus.md)
- [<span data-ttu-id="b85c3-151">이벤트 기반 강제 업데이트 관리</span><span class="sxs-lookup"><span data-stu-id="b85c3-151">Manage event-based forced updates</span></span>](manage-event-based-updates-microsoft-defender-antivirus.md)
- [<span data-ttu-id="b85c3-152">모바일 장치 및 VM(가상 머신)에 대한 업데이트 관리</span><span class="sxs-lookup"><span data-stu-id="b85c3-152">Manage updates for mobile devices and virtual machines (VMs)</span></span>](manage-updates-mobile-devices-vms-microsoft-defender-antivirus.md)
- [<span data-ttu-id="b85c3-153">Windows 10의 Microsoft Defender 바이러스 백신</span><span class="sxs-lookup"><span data-stu-id="b85c3-153">Microsoft Defender Antivirus in Windows 10</span></span>](microsoft-defender-antivirus-in-windows-10.md)