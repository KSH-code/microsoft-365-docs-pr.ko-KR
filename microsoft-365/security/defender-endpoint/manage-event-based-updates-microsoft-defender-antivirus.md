---
title: 특정 Microsoft Defender 바이러스 백신 후 업데이트 적용
description: 시작 또는 Microsoft Defender 바이러스 백신 검색 보고서를 받은 후 보안 인텔리전스 업데이트를 적용하는 방법을 관리합니다.
keywords: 업데이트, 보호, 강제 업데이트, 이벤트, 시작, 최신 확인, 알림
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: normal
ms.topic: article
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 09/17/2018
ms.reviewer: pahuijbr
manager: dansimp
ms.technology: mde
ms.openlocfilehash: 82aff7adedc9e490520851ad8c8e87fad60abf0a
ms.sourcegitcommit: be929f79751c0c52dfa6bd98a854432a0c63faf0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/14/2021
ms.locfileid: "52926082"
---
# <a name="manage-event-based-forced-updates"></a><span data-ttu-id="5ae16-104">이벤트 기반 강제 업데이트 관리</span><span class="sxs-lookup"><span data-stu-id="5ae16-104">Manage event-based forced updates</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="5ae16-105">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="5ae16-105">**Applies to:**</span></span>

- [<span data-ttu-id="5ae16-106">엔드포인트용 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="5ae16-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

<span data-ttu-id="5ae16-107">Microsoft Defender 바이러스 백신 시작 시 또는 클라우드 제공 보호 서비스에서 특정 보고서를 받은 후와 같은 특정 이벤트가 발생하거나 업데이트가 발생하면 안 되는지 여부를 결정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5ae16-107">Microsoft Defender Antivirus allows you to determine if updates should (or should not) occur after certain events, such as at startup or after receiving specific reports from the cloud-delivered protection service.</span></span>

## <a name="check-for-protection-updates-before-running-a-scan"></a><span data-ttu-id="5ae16-108">검사를 실행하기 전에 보호 업데이트 확인</span><span class="sxs-lookup"><span data-stu-id="5ae16-108">Check for protection updates before running a scan</span></span>

<span data-ttu-id="5ae16-109">그룹 정책, Microsoft Endpoint Configuration Manager, PowerShell cmdlet 및 WMI를 사용하여 예약된 검사를 실행하기 전에 Microsoft Defender 바이러스 백신 업데이트를 강제로 확인하고 다운로드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5ae16-109">You can use Microsoft Endpoint Configuration Manager, Group Policy, PowerShell cmdlets, and WMI to force Microsoft Defender Antivirus to check and download protection updates before running a scheduled scan.</span></span>

### <a name="use-configuration-manager-to-check-for-protection-updates-before-running-a-scan"></a><span data-ttu-id="5ae16-110">Configuration Manager를 사용하여 검사를 실행하기 전에 보호 업데이트 확인</span><span class="sxs-lookup"><span data-stu-id="5ae16-110">Use Configuration Manager to check for protection updates before running a scan</span></span>

1. <span data-ttu-id="5ae16-111">Microsoft Endpoint Manager 콘솔에서 변경할 맬웨어 방지 정책을 열고(왼쪽의 탐색 창에서 자산 및 규정 준수를 클릭한 다음 개요 Endpoint Protection 맬웨어 방지 정책)   >    >  </span><span class="sxs-lookup"><span data-stu-id="5ae16-111">On your Microsoft Endpoint Manager console, open the antimalware policy you want to change (click **Assets and Compliance** in the navigation pane on the left, then expand the tree to **Overview** > **Endpoint Protection** > **Antimalware Policies**)</span></span>

2. <span data-ttu-id="5ae16-112">예약된 검사 **섹션으로 이동하여** 검사를 실행하기 전에 최신 보안 인텔리전스 업데이트 확인을  **예로 설정하세요.**</span><span class="sxs-lookup"><span data-stu-id="5ae16-112">Go to the **Scheduled scans** section and set **Check for the latest security intelligence updates before running a scan** to **Yes**.</span></span>

3. <span data-ttu-id="5ae16-113">**확인** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="5ae16-113">Click **OK**.</span></span>

4. <span data-ttu-id="5ae16-114">[평소와 같이 업데이트된 정책을 배포합니다.](/sccm/protect/deploy-use/endpoint-antimalware-policies#deploy-an-antimalware-policy-to-client-computers)</span><span class="sxs-lookup"><span data-stu-id="5ae16-114">[Deploy the updated policy as usual](/sccm/protect/deploy-use/endpoint-antimalware-policies#deploy-an-antimalware-policy-to-client-computers).</span></span>

### <a name="use-group-policy-to-check-for-protection-updates-before-running-a-scan"></a><span data-ttu-id="5ae16-115">그룹 정책을 사용하여 검사를 실행하기 전에 보호 업데이트 확인</span><span class="sxs-lookup"><span data-stu-id="5ae16-115">Use Group Policy to check for protection updates before running a scan</span></span>

1. <span data-ttu-id="5ae16-116">그룹 정책 관리 컴퓨터의 [](/previous-versions/windows/desktop/gpmc/group-policy-management-console-portal)그룹 정책 관리 콘솔을 열고 구성할 그룹 정책 개체를 마우스 오른쪽 단추로 클릭하고 편집을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="5ae16-116">On your Group Policy management machine, open the [Group Policy Management Console](/previous-versions/windows/desktop/gpmc/group-policy-management-console-portal), right-click the Group Policy Object you want to configure and click **Edit**.</span></span>

2. <span data-ttu-id="5ae16-117">그룹 정책 **관리 편집기를 사용하여 컴퓨터** **구성으로 이동하십시오.**</span><span class="sxs-lookup"><span data-stu-id="5ae16-117">Using the **Group Policy Management Editor** go to **Computer configuration**.</span></span>

3. <span data-ttu-id="5ae16-118">정책을 **클릭한** 다음 **관리 템플릿을 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="5ae16-118">Click **Policies** then **Administrative templates**.</span></span>

4. <span data-ttu-id="5ae16-119">검색에서 구성 **Windows**  >  **트리를 Microsoft Defender 바이러스 백신**  >  **확장합니다.**</span><span class="sxs-lookup"><span data-stu-id="5ae16-119">Expand the tree to **Windows components** > **Microsoft Defender Antivirus** > **Scan**.</span></span>

5. <span data-ttu-id="5ae16-120">예약된  검사를 실행하기 전에 최신 바이러스 및 스파이웨어 정의 확인을 두 번 클릭하고 옵션을 사용으로 **설정합니다.**</span><span class="sxs-lookup"><span data-stu-id="5ae16-120">Double-click **Check for the latest virus and spyware definitions before running a scheduled scan** and set the option to **Enabled**.</span></span>

6. <span data-ttu-id="5ae16-121">**확인** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="5ae16-121">Click **OK**.</span></span>

### <a name="use-powershell-cmdlets-to-check-for-protection-updates-before-running-a-scan"></a><span data-ttu-id="5ae16-122">검사를 실행하기 전에 PowerShell cmdlet을 사용하여 보호 업데이트 확인</span><span class="sxs-lookup"><span data-stu-id="5ae16-122">Use PowerShell cmdlets to check for protection updates before running a scan</span></span>

<span data-ttu-id="5ae16-123">다음 cmdlet을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="5ae16-123">Use the following cmdlets:</span></span>

```PowerShell
Set-MpPreference -CheckForSignaturesBeforeRunningScan
```

<span data-ttu-id="5ae16-124">자세한 내용은 [PowerShell cmdlet을 사용하여 Microsoft Defender 바이러스 백신 구성 및 실행](use-powershell-cmdlets-microsoft-defender-antivirus.md)과 [Defender cmdlet](/powershell/module/defender/index)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="5ae16-124">For more information, see [Use PowerShell cmdlets to configure and run Microsoft Defender Antivirus](use-powershell-cmdlets-microsoft-defender-antivirus.md) and [Defender cmdlets](/powershell/module/defender/index).</span></span>

### <a name="use-windows-management-instruction-wmi-to-check-for-protection-updates-before-running-a-scan"></a><span data-ttu-id="5ae16-125">WMI(Windows 관리 명령)를 사용하여 검사를 실행하기 전에 보호 업데이트를 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="5ae16-125">Use Windows Management Instruction (WMI) to check for protection updates before running a scan</span></span>

<span data-ttu-id="5ae16-126">다음 [  속성에 MSFT_MpPreference  ](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) 클래스의 Set 메서드를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="5ae16-126">Use the [**Set** method of the **MSFT_MpPreference**](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) class for the following properties:</span></span>

```WMI
CheckForSignaturesBeforeRunningScan
```

<span data-ttu-id="5ae16-127">자세한 내용은 [WMIv2 api Windows Defender 참조하세요.](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)</span><span class="sxs-lookup"><span data-stu-id="5ae16-127">For more information, see [Windows Defender WMIv2 APIs](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal).</span></span>

## <a name="check-for-protection-updates-on-startup"></a><span data-ttu-id="5ae16-128">시작 시 보호 업데이트 확인</span><span class="sxs-lookup"><span data-stu-id="5ae16-128">Check for protection updates on startup</span></span>

<span data-ttu-id="5ae16-129">그룹 정책을 사용하여 컴퓨터 시작 시 Microsoft Defender 바이러스 백신 보호 업데이트를 강제로 확인하고 다운로드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5ae16-129">You can use Group Policy to force Microsoft Defender Antivirus to check and download protection updates when the machine is started.</span></span>

1. <span data-ttu-id="5ae16-130">그룹 정책 관리 컴퓨터에서 그룹 [](/previous-versions/windows/desktop/gpmc/group-policy-management-console-portal)정책 관리 콘솔을 열고 구성할 그룹 정책 개체를 마우스 오른쪽 단추로 클릭하고 편집을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="5ae16-130">On your Group Policy management computer, open the [Group Policy Management Console](/previous-versions/windows/desktop/gpmc/group-policy-management-console-portal), right-click the Group Policy Object you want to configure and click **Edit**.</span></span>

2. <span data-ttu-id="5ae16-131">그룹 정책 **관리 편집기를 사용하여 컴퓨터** **구성으로 이동하십시오.**</span><span class="sxs-lookup"><span data-stu-id="5ae16-131">Using the **Group Policy Management Editor** go to **Computer configuration**.</span></span>

3. <span data-ttu-id="5ae16-132">정책을 **클릭한** 다음 **관리 템플릿을 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="5ae16-132">Click **Policies** then **Administrative templates**.</span></span>

4. <span data-ttu-id="5ae16-133">보안 인텔리전스 **Windows 구성 Microsoft Defender 바이러스 백신**  >    >  **확장합니다.**</span><span class="sxs-lookup"><span data-stu-id="5ae16-133">Expand the tree to **Windows components** > **Microsoft Defender Antivirus** > **Security Intelligence Updates**.</span></span>

5. <span data-ttu-id="5ae16-134">시작 시  최신 바이러스 및 스파이웨어 정의 확인을 두 번 클릭하고 옵션을 사용으로 **설정합니다.**</span><span class="sxs-lookup"><span data-stu-id="5ae16-134">Double-click **Check for the latest virus and spyware definitions on startup** and set the option to **Enabled**.</span></span> 

6. <span data-ttu-id="5ae16-135">**확인** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="5ae16-135">Click **OK**.</span></span>

<span data-ttu-id="5ae16-136">그룹 정책, PowerShell 또는 WMI를 사용하여 시작 시 업데이트를 Microsoft Defender 바이러스 백신 확인하도록 구성할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5ae16-136">You can also use Group Policy, PowerShell, or WMI to configure Microsoft Defender Antivirus to check for updates at startup even when it is not running.</span></span>

### <a name="use-group-policy-to-download-updates-when-microsoft-defender-antivirus-is-not-present"></a><span data-ttu-id="5ae16-137">그룹 정책을 사용하여 업데이트가 없는 Microsoft Defender 바이러스 백신 다운로드</span><span class="sxs-lookup"><span data-stu-id="5ae16-137">Use Group Policy to download updates when Microsoft Defender Antivirus is not present</span></span>

1. <span data-ttu-id="5ae16-138">그룹 정책 관리 컴퓨터의 [](/previous-versions/windows/desktop/gpmc/group-policy-management-console-portal)그룹 정책 관리 콘솔을 열고 구성할 그룹 정책 개체를 마우스 오른쪽 단추로 클릭하고 편집을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="5ae16-138">On your Group Policy management machine, open the [Group Policy Management Console](/previous-versions/windows/desktop/gpmc/group-policy-management-console-portal), right-click the Group Policy Object you want to configure and click **Edit**.</span></span>

2. <span data-ttu-id="5ae16-139">그룹 정책 **관리 편집기를 사용하여** 컴퓨터 **구성으로 이동하십시오.**</span><span class="sxs-lookup"><span data-stu-id="5ae16-139">Using the **Group Policy Management Editor**, go to **Computer configuration**.</span></span>

3. <span data-ttu-id="5ae16-140">정책을 **클릭한** 다음 **관리 템플릿을 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="5ae16-140">Click **Policies** then **Administrative templates**.</span></span>

4. <span data-ttu-id="5ae16-141">보안 인텔리전스 **Windows 구성 Microsoft Defender 바이러스 백신**  >    >  **확장합니다.**</span><span class="sxs-lookup"><span data-stu-id="5ae16-141">Expand the tree to **Windows components** > **Microsoft Defender Antivirus** > **Security Intelligence Updates**.</span></span>

5. <span data-ttu-id="5ae16-142">시작 시 보안 **인텔리전스** 업데이트 시작을 두 번 클릭하고 옵션을 사용으로 **설정합니다.**</span><span class="sxs-lookup"><span data-stu-id="5ae16-142">Double-click **Initiate security intelligence update on startup** and set the option to **Enabled**.</span></span>

6. <span data-ttu-id="5ae16-143">**확인** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="5ae16-143">Click **OK**.</span></span>

### <a name="use-powershell-cmdlets-to-download-updates-when-microsoft-defender-antivirus-is-not-present"></a><span data-ttu-id="5ae16-144">PowerShell cmdlet을 사용하여 업데이트가 없는 Microsoft Defender 바이러스 백신 다운로드</span><span class="sxs-lookup"><span data-stu-id="5ae16-144">Use PowerShell cmdlets to download updates when Microsoft Defender Antivirus is not present</span></span>

<span data-ttu-id="5ae16-145">다음 cmdlet을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="5ae16-145">Use the following cmdlets:</span></span>

```PowerShell
Set-MpPreference -SignatureDisableUpdateOnStartupWithoutEngine
```

<span data-ttu-id="5ae16-146">자세한 내용은 [PowerShell cmdlet을](use-powershell-cmdlets-microsoft-defender-antivirus.md) 사용하여 Microsoft Defender 바이러스 백신 및 [Defender cmdlet을](/powershell/module/defender/index) 사용하여 PowerShell을 사용하는 방법에 대한 자세한 Microsoft Defender 바이러스 백신.</span><span class="sxs-lookup"><span data-stu-id="5ae16-146">For more information, see [Use PowerShell cmdlets to manage Microsoft Defender Antivirus](use-powershell-cmdlets-microsoft-defender-antivirus.md) and [Defender cmdlets](/powershell/module/defender/index) for more information on how to use PowerShell with Microsoft Defender Antivirus.</span></span>

### <a name="use-windows-management-instruction-wmi-to-download-updates-when-microsoft-defender-antivirus-is-not-present"></a><span data-ttu-id="5ae16-147">WMI(Windows Management Instruction)를 사용하여 업데이트가 없는 Microsoft Defender 바이러스 백신 다운로드</span><span class="sxs-lookup"><span data-stu-id="5ae16-147">Use Windows Management Instruction (WMI) to download updates when Microsoft Defender Antivirus is not present</span></span>

<span data-ttu-id="5ae16-148">다음 [  속성에 MSFT_MpPreference  ](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) 클래스의 Set 메서드를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="5ae16-148">Use the [**Set** method of the **MSFT_MpPreference**](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) class for the following properties:</span></span>

```WMI
SignatureDisableUpdateOnStartupWithoutEngine
```

<span data-ttu-id="5ae16-149">자세한 내용은 [WMIv2 api Windows Defender 참조하세요.](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)</span><span class="sxs-lookup"><span data-stu-id="5ae16-149">For more information, see [Windows Defender WMIv2 APIs](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal).</span></span>

<a id="cloud-report-updates"></a>

## <a name="allow-ad-hoc-changes-to-protection-based-on-cloud-delivered-protection"></a><span data-ttu-id="5ae16-150">클라우드 제공 보호를 기반으로 보호에 대한 추가 변경 허용</span><span class="sxs-lookup"><span data-stu-id="5ae16-150">Allow ad hoc changes to protection based on cloud-delivered protection</span></span>

<span data-ttu-id="5ae16-151">Microsoft Defender AV는 클라우드 제공 보호를 기반으로 보호를 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5ae16-151">Microsoft Defender AV can make changes to its protection based on cloud-delivered protection.</span></span> <span data-ttu-id="5ae16-152">이러한 변경 내용은 일반 또는 예약된 보호 업데이트 외부에서 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5ae16-152">Such changes can occur outside of normal or scheduled protection updates.</span></span>

<span data-ttu-id="5ae16-153">클라우드 제공 보호를 사용하도록 설정한 경우 Microsoft Defender AV는 의심스러운 파일을 클라우드로 Windows Defender 전송합니다.</span><span class="sxs-lookup"><span data-stu-id="5ae16-153">If you have enabled cloud-delivered protection, Microsoft Defender AV will send files it is suspicious about to the Windows Defender cloud.</span></span> <span data-ttu-id="5ae16-154">클라우드 서비스에서 파일이 악성으로 보고되고 최근 보호 업데이트에서 파일이 검색된 경우 그룹 정책을 사용하여 해당 보호 업데이트를 자동으로 받도록 Microsoft Defender AV를 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5ae16-154">If the cloud service reports that the file is malicious, and the file is detected in a recent protection update, you can use Group Policy to configure Microsoft Defender AV to automatically receive that protection update.</span></span> <span data-ttu-id="5ae16-155">기타 중요한 보호 업데이트도 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5ae16-155">Other important protection updates can also be applied.</span></span>

### <a name="use-group-policy-to-automatically-download-recent-updates-based-on-cloud-delivered-protection"></a><span data-ttu-id="5ae16-156">그룹 정책을 사용하여 클라우드 제공 보호에 따라 최근 업데이트 자동 다운로드</span><span class="sxs-lookup"><span data-stu-id="5ae16-156">Use Group Policy to automatically download recent updates based on cloud-delivered protection</span></span>

1. <span data-ttu-id="5ae16-157">그룹 정책 관리 컴퓨터의 [](/previous-versions/windows/desktop/gpmc/group-policy-management-console-portal)그룹 정책 관리 콘솔을 열고 구성할 그룹 정책 개체를 마우스 오른쪽 단추로 클릭하고 편집을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="5ae16-157">On your Group Policy management machine, open the [Group Policy Management Console](/previous-versions/windows/desktop/gpmc/group-policy-management-console-portal), right-click the Group Policy Object you want to configure and click **Edit**.</span></span>

2. <span data-ttu-id="5ae16-158">그룹 정책 **관리 편집기를 사용하여 컴퓨터** **구성으로 이동하십시오.**</span><span class="sxs-lookup"><span data-stu-id="5ae16-158">Using the **Group Policy Management Editor** go to **Computer configuration**.</span></span>

3. <span data-ttu-id="5ae16-159">정책을 **클릭한** 다음 **관리 템플릿을 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="5ae16-159">Click **Policies** then **Administrative templates**.</span></span>

4. <span data-ttu-id="5ae16-160">보안 인텔리전스 **Windows 구성 Microsoft Defender 바이러스 백신**  >    >  **확장합니다.**</span><span class="sxs-lookup"><span data-stu-id="5ae16-160">Expand the tree to **Windows components** > **Microsoft Defender Antivirus** > **Security Intelligence Updates**.</span></span>

5. <span data-ttu-id="5ae16-161">**Microsoft MAPS에** 대한 보고서를 기반으로 하는 실시간 보안 인텔리전스 업데이트 허용을 두 번 클릭하고 옵션을 사용으로 **설정합니다.**</span><span class="sxs-lookup"><span data-stu-id="5ae16-161">Double-click **Allow real-time security intelligence updates based on reports to Microsoft MAPS** and set the option to **Enabled**.</span></span> <span data-ttu-id="5ae16-162">그런 다음 **확인** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="5ae16-162">Then click **OK**.</span></span>

6. <span data-ttu-id="5ae16-163">**알림에서 정의** 기반 보고서를 Microsoft MAPS에 사용하지 않도록 설정하고 옵션을 사용으로 **설정합니다.**</span><span class="sxs-lookup"><span data-stu-id="5ae16-163">**Allow notifications to disable definitions-based reports to Microsoft MAPS** and set the option to **Enabled**.</span></span> <span data-ttu-id="5ae16-164">그런 다음 **확인** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="5ae16-164">Then click **OK**.</span></span>
    
> [!NOTE]
> <span data-ttu-id="5ae16-165">**알림이 정의** 기반 보고서를 사용하지 않도록 설정하도록 허용하면 Microsoft MAPS에서 가짓 긍정 보고서를 유발하는 것으로 알려진 정의를 사용하지 않도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5ae16-165">**Allow notifications to disable definitions based reports** enables Microsoft MAPS to disable those definitions known to cause false-positive reports.</span></span> <span data-ttu-id="5ae16-166">이 기능이 작동하려면 Microsoft MAPS에 가입하도록 컴퓨터를 구성해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5ae16-166">You must configure your computer to join Microsoft MAPS for this function to work.</span></span>

## <a name="see-also"></a><span data-ttu-id="5ae16-167">참고 항목</span><span class="sxs-lookup"><span data-stu-id="5ae16-167">See also</span></span>

- [<span data-ttu-id="5ae16-168">배포 Microsoft Defender 바이러스 백신</span><span class="sxs-lookup"><span data-stu-id="5ae16-168">Deploy Microsoft Defender Antivirus</span></span>](deploy-manage-report-microsoft-defender-antivirus.md)
- [<span data-ttu-id="5ae16-169">업데이트 Microsoft Defender 바이러스 백신 관리하고 기준 적용</span><span class="sxs-lookup"><span data-stu-id="5ae16-169">Manage Microsoft Defender Antivirus updates and apply baselines</span></span>](manage-updates-baselines-microsoft-defender-antivirus.md)
- [<span data-ttu-id="5ae16-170">보호 업데이트를 다운로드하고 적용해야 하는 경우 관리</span><span class="sxs-lookup"><span data-stu-id="5ae16-170">Manage when protection updates should be downloaded and applied</span></span>](manage-protection-update-schedule-microsoft-defender-antivirus.md)
- [<span data-ttu-id="5ae16-171">최신이 지난 끝점에 대한 업데이트 관리</span><span class="sxs-lookup"><span data-stu-id="5ae16-171">Manage updates for endpoints that are out of date</span></span>](manage-outdated-endpoints-microsoft-defender-antivirus.md)
- [<span data-ttu-id="5ae16-172">모바일 장치 및 VM(가상 머신)에 대한 업데이트 관리</span><span class="sxs-lookup"><span data-stu-id="5ae16-172">Manage updates for mobile devices and virtual machines (VMs)</span></span>](manage-updates-mobile-devices-vms-microsoft-defender-antivirus.md)
- [<span data-ttu-id="5ae16-173">Windows 10의 Microsoft Defender 바이러스 백신</span><span class="sxs-lookup"><span data-stu-id="5ae16-173">Microsoft Defender Antivirus in Windows 10</span></span>](microsoft-defender-antivirus-in-windows-10.md)