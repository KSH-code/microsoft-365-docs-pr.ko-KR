---
title: 특정 프로세스에서 연 파일에 대한 제외 구성
description: 특정 프로세스에서 파일을 연 경우 검사에서 파일을 제외할 수 있습니다.
keywords: Microsoft Defender 바이러스 백신, 프로세스, 제외, 파일, 검사
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.openlocfilehash: 94375bc843c6512616d49345bcc9e7f63899a708
ms.sourcegitcommit: 7a339c9f7039825d131b39481ddf54c57b021b11
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2021
ms.locfileid: "51765086"
---
# <a name="configure-exclusions-for-files-opened-by-processes"></a><span data-ttu-id="f390b-104">프로세스에서 연 파일에 대한 제외 구성</span><span class="sxs-lookup"><span data-stu-id="f390b-104">Configure exclusions for files opened by processes</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="f390b-105">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="f390b-105">**Applies to:**</span></span>

- <span data-ttu-id="f390b-106">[엔드포인트용 Microsoft Defender](/microsoft-365/security/defender-endpoint/) </span><span class="sxs-lookup"><span data-stu-id="f390b-106">[Microsoft Defender for Endpoint](/microsoft-365/security/defender-endpoint/)</span></span>

<span data-ttu-id="f390b-107">특정 프로세스에서 연 파일을 Microsoft Defender 바이러스 백신 검사에서 제외할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f390b-107">You can exclude files that have been opened by specific processes from Microsoft Defender Antivirus scans.</span></span> <span data-ttu-id="f390b-108">제외 [목록을 정의하기](configure-exclusions-microsoft-defender-antivirus.md#recommendations-for-defining-exclusions) 전에 제외를 정의하기 위한 권장 사항을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="f390b-108">See [Recommendations for defining exclusions](configure-exclusions-microsoft-defender-antivirus.md#recommendations-for-defining-exclusions) before defining your exclusion lists.</span></span>

<span data-ttu-id="f390b-109">이 문서에서는 제외 목록을 구성하는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="f390b-109">This article describes how to configure exclusion lists.</span></span> 

## <a name="examples-of-exclusions"></a><span data-ttu-id="f390b-110">제외의 예</span><span class="sxs-lookup"><span data-stu-id="f390b-110">Examples of exclusions</span></span>

|<span data-ttu-id="f390b-111">제외</span><span class="sxs-lookup"><span data-stu-id="f390b-111">Exclusion</span></span> | <span data-ttu-id="f390b-112">예제</span><span class="sxs-lookup"><span data-stu-id="f390b-112">Example</span></span> |
|---|---|
|<span data-ttu-id="f390b-113">특정 파일 이름을 사용 하 고 모든 프로세스에서 열 수 있는 컴퓨터의 모든 파일</span><span class="sxs-lookup"><span data-stu-id="f390b-113">Any file on the machine that is opened by any process with a specific file name</span></span> | <span data-ttu-id="f390b-114">다음을 `test.exe` 통해 연 파일은 제외됩니다.</span><span class="sxs-lookup"><span data-stu-id="f390b-114">Specifying `test.exe` would exclude files opened by:</span></span> <br/>`c:\sample\test.exe`<br/>`d:\internal\files\test.exe` |  
|<span data-ttu-id="f390b-115">특정 폴더의 모든 프로세스에서 연 컴퓨터의 모든 파일</span><span class="sxs-lookup"><span data-stu-id="f390b-115">Any file on the machine that is opened by any process under a specific folder</span></span> | <span data-ttu-id="f390b-116">다음을 `c:\test\sample\*` 통해 연 파일은 제외됩니다.</span><span class="sxs-lookup"><span data-stu-id="f390b-116">Specifying `c:\test\sample\*` would exclude files opened by:</span></span><br/>`c:\test\sample\test.exe`<br/>`c:\test\sample\test2.exe`<br/>`c:\test\sample\utility.exe` | 
|<span data-ttu-id="f390b-117">특정 폴더의 특정 프로세스에서 연 컴퓨터의 모든 파일</span><span class="sxs-lookup"><span data-stu-id="f390b-117">Any file on the machine that is opened by a specific process in a specific folder</span></span> | <span data-ttu-id="f390b-118">지정하면 `c:\test\process.exe` 열 때만 열 수 있는 파일 제외 `c:\test\process.exe`</span><span class="sxs-lookup"><span data-stu-id="f390b-118">Specifying `c:\test\process.exe` would exclude files only opened by `c:\test\process.exe`</span></span> |


<span data-ttu-id="f390b-119">프로세스 제외 목록에 프로세스를 추가하면 Microsoft Defender 바이러스 백신은 파일이 있는 위치와 상관없이 해당 프로세스에서 연 파일을 검색하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="f390b-119">When you add a process to the process exclusion list, Microsoft Defender Antivirus won't scan files opened by that process, no matter where the files are located.</span></span> <span data-ttu-id="f390b-120">그러나 프로세스 자체는 파일 제외 목록에도 추가되지 않은 경우 [검사됩니다.](configure-extension-file-exclusions-microsoft-defender-antivirus.md)</span><span class="sxs-lookup"><span data-stu-id="f390b-120">The process itself, however, will be scanned unless it has also been added to the [file exclusion list](configure-extension-file-exclusions-microsoft-defender-antivirus.md).</span></span>

<span data-ttu-id="f390b-121">제외는 항상 실시간 보호 및 모니터링에만 [적용됩니다.](configure-real-time-protection-microsoft-defender-antivirus.md)</span><span class="sxs-lookup"><span data-stu-id="f390b-121">The exclusions only apply to [always-on real-time protection and monitoring](configure-real-time-protection-microsoft-defender-antivirus.md).</span></span> <span data-ttu-id="f390b-122">예약된 검사나 요구 시 검사에는 적용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="f390b-122">They don't apply to scheduled or on-demand scans.</span></span>

<span data-ttu-id="f390b-123">제외 목록에 대한 그룹 정책으로 **변경한** 내용은 Windows 보안 앱의 목록에 [표시됩니다.](microsoft-defender-security-center-antivirus.md)</span><span class="sxs-lookup"><span data-stu-id="f390b-123">Changes made with Group Policy to the exclusion lists **will show** in the lists in the [Windows Security app](microsoft-defender-security-center-antivirus.md).</span></span> <span data-ttu-id="f390b-124">그러나 Windows 보안 앱의  변경 내용은 그룹 정책 목록에는 표시되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="f390b-124">However, changes made in the Windows Security app **will not show** in the Group Policy lists.</span></span>

<span data-ttu-id="f390b-125">그룹 정책, Microsoft Endpoint Configuration Manager, Microsoft Intune 및 Windows 보안 앱에서 제외 목록을 추가, 제거 및 검토할 수 있으며, 와일드카드를 사용하여 목록을 추가로 사용자 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f390b-125">You can add, remove, and review the lists for exclusions in Group Policy, Microsoft Endpoint Configuration Manager, Microsoft Intune, and with the Windows Security app, and you can use wildcards to further customize the lists.</span></span>

<span data-ttu-id="f390b-126">PowerShell cmdlet 및 WMI를 사용하여 목록 검토를 포함하여 제외 목록을 구성할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f390b-126">You can also use PowerShell cmdlets and WMI to configure the exclusion lists, including reviewing your lists.</span></span>

<span data-ttu-id="f390b-127">기본적으로 목록에 대한 로컬 변경 내용(관리자 권한이 있는 사용자, PowerShell 및 WMI로 변경한 내용은 그룹 정책, Configuration Manager 또는 Intune에서 정의하고 배포한 목록)과 병합됩니다.</span><span class="sxs-lookup"><span data-stu-id="f390b-127">By default, local changes made to the lists (by users with administrator privileges; changes made with PowerShell and WMI) will be merged with the lists as defined (and deployed) by Group Policy, Configuration Manager, or Intune.</span></span> <span data-ttu-id="f390b-128">충돌이 있는 경우 그룹 정책 목록이 우선합니다.</span><span class="sxs-lookup"><span data-stu-id="f390b-128">The Group Policy lists will take precedence in the case of conflicts.</span></span>

<span data-ttu-id="f390b-129">로컬 [및](configure-local-policy-overrides-microsoft-defender-antivirus.md#merge-lists) 전역으로 정의된 제외 목록이 병합되는 방법을 구성하여 로컬 변경 내용이 관리되는 배포 설정을 다시 정의할 수 있도록 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f390b-129">You can [configure how locally and globally defined exclusions lists are merged](configure-local-policy-overrides-microsoft-defender-antivirus.md#merge-lists) to allow local changes to override managed deployment settings.</span></span>

## <a name="configure-the-list-of-exclusions-for-files-opened-by-specified-processes"></a><span data-ttu-id="f390b-130">지정된 프로세스에서 연 파일의 제외 목록 구성</span><span class="sxs-lookup"><span data-stu-id="f390b-130">Configure the list of exclusions for files opened by specified processes</span></span>

### <a name="use-microsoft-intune-to-exclude-files-that-have-been-opened-by-specified-processes-from-scans"></a><span data-ttu-id="f390b-131">Microsoft Intune을 사용하여 지정된 프로세스에서 연 파일을 검사에서 제외</span><span class="sxs-lookup"><span data-stu-id="f390b-131">Use Microsoft Intune to exclude files that have been opened by specified processes from scans</span></span>

<span data-ttu-id="f390b-132">자세한 [내용은 Microsoft Intune의](/intune/device-restrictions-configure) 장치 제한 설정 구성 및 [Intune에서 Windows 10에](/intune/device-restrictions-windows-10#microsoft-defender-antivirus) 대한 Microsoft Defender 바이러스 백신 장치 제한 설정을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="f390b-132">See [Configure device restriction settings in Microsoft Intune](/intune/device-restrictions-configure) and [Microsoft Defender Antivirus device restriction settings for Windows 10 in Intune](/intune/device-restrictions-windows-10#microsoft-defender-antivirus) for more details.</span></span>

### <a name="use-microsoft-endpoint-manager-to-exclude-files-that-have-been-opened-by-specified-processes-from-scans"></a><span data-ttu-id="f390b-133">Microsoft Endpoint Manager를 사용하여 지정된 프로세스에서 연 파일을 검사에서 제외</span><span class="sxs-lookup"><span data-stu-id="f390b-133">Use Microsoft Endpoint Manager to exclude files that have been opened by specified processes from scans</span></span>

<span data-ttu-id="f390b-134">Microsoft Endpoint Manager(현재 분기)를 구성하는 방법에 대한 자세한 내용은 맬웨어 방지 정책을 만들고 배포하는 [방법:](/configmgr/protect/deploy-use/endpoint-antimalware-policies#exclusion-settings) 제외 설정을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="f390b-134">See [How to create and deploy antimalware policies: Exclusion settings](/configmgr/protect/deploy-use/endpoint-antimalware-policies#exclusion-settings) for details on configuring Microsoft Endpoint Manager (current branch).</span></span>

### <a name="use-group-policy-to-exclude-files-that-have-been-opened-by-specified-processes-from-scans"></a><span data-ttu-id="f390b-135">그룹 정책을 사용하여 지정된 프로세스에서 연 파일을 검사에서 제외</span><span class="sxs-lookup"><span data-stu-id="f390b-135">Use Group Policy to exclude files that have been opened by specified processes from scans</span></span>

1. <span data-ttu-id="f390b-136">그룹 정책 관리 컴퓨터에서 그룹 [](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))정책 관리 콘솔을 열고 구성할 그룹 정책 개체를 마우스 오른쪽 단추로 클릭하고 편집을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="f390b-136">On your Group Policy management computer, open the [Group Policy Management Console](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)), right-click the Group Policy Object you want to configure and click **Edit**.</span></span>

2. <span data-ttu-id="f390b-137">그룹 정책 **관리 편집기에서** 컴퓨터 **구성으로 이동하여** 관리 템플릿 **을 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="f390b-137">In the **Group Policy Management Editor** go to **Computer configuration** and click **Administrative templates**.</span></span>

3. <span data-ttu-id="f390b-138">Microsoft Defender 바이러스 백신 > Windows 구성 > **확장합니다.**</span><span class="sxs-lookup"><span data-stu-id="f390b-138">Expand the tree to **Windows components > Microsoft Defender Antivirus > Exclusions**.</span></span>

4. <span data-ttu-id="f390b-139">프로세스 **제외를** 두 번 클릭하고 제외를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="f390b-139">Double-click **Process Exclusions** and add the exclusions:</span></span>

    1. <span data-ttu-id="f390b-140">옵션을 사용으로 **설정합니다.**</span><span class="sxs-lookup"><span data-stu-id="f390b-140">Set the option to **Enabled**.</span></span>
    2. <span data-ttu-id="f390b-141">옵션 **섹션에서** **표시...를 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="f390b-141">Under the **Options** section, click **Show...**.</span></span>
    3. <span data-ttu-id="f390b-142">값 이름 열 아래에 각 프로세스를 자체 **줄에 입력합니다.**</span><span class="sxs-lookup"><span data-stu-id="f390b-142">Enter each process on its own line under the **Value name** column.</span></span> <span data-ttu-id="f390b-143">다양한 유형의 프로세스 제외에 대한 예제 표를 참조합니다.</span><span class="sxs-lookup"><span data-stu-id="f390b-143">See the example table for the different types of process exclusions.</span></span>  <span data-ttu-id="f390b-144">모든 프로세스의 값 **열에** **0을** 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="f390b-144">Enter **0** in the **Value** column for all processes.</span></span>

5. <span data-ttu-id="f390b-145">**확인** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="f390b-145">Click **OK**.</span></span>

### <a name="use-powershell-cmdlets-to-exclude-files-that-have-been-opened-by-specified-processes-from-scans"></a><span data-ttu-id="f390b-146">PowerShell cmdlet을 사용하여 지정된 프로세스에서 연 파일을 검사에서 제외</span><span class="sxs-lookup"><span data-stu-id="f390b-146">Use PowerShell cmdlets to exclude files that have been opened by specified processes from scans</span></span>

<span data-ttu-id="f390b-147">PowerShell을 사용하여 프로세스에서 연 파일에 대한 제외를 추가하거나 제거하려면 매개 변수와 함께 세 개의 cmdlet을 조합하여 사용해야 `-ExclusionProcess` 합니다.</span><span class="sxs-lookup"><span data-stu-id="f390b-147">Using PowerShell to add or remove exclusions for files that have been opened by processes requires using a combination of three cmdlets with the `-ExclusionProcess` parameter.</span></span> <span data-ttu-id="f390b-148">cmdlet은 [모두 Defender 모듈에 있습니다.](/powershell/module/defender/)</span><span class="sxs-lookup"><span data-stu-id="f390b-148">The cmdlets are all in the [Defender module](/powershell/module/defender/).</span></span>

<span data-ttu-id="f390b-149">cmdlet의 형식은 다음입니다.</span><span class="sxs-lookup"><span data-stu-id="f390b-149">The format for the cmdlets is:</span></span>

```PowerShell
<cmdlet> -ExclusionProcess "<item>"
```

<span data-ttu-id="f390b-150">다음을 다음으로 \<cmdlet> 허용합니다.</span><span class="sxs-lookup"><span data-stu-id="f390b-150">The following are allowed as the \<cmdlet>:</span></span>

|<span data-ttu-id="f390b-151">구성 작업</span><span class="sxs-lookup"><span data-stu-id="f390b-151">Configuration action</span></span> | <span data-ttu-id="f390b-152">PowerShell cmdlet</span><span class="sxs-lookup"><span data-stu-id="f390b-152">PowerShell cmdlet</span></span> |
|---|---|
|<span data-ttu-id="f390b-153">목록 만들기 또는 덮어 덮어 사용</span><span class="sxs-lookup"><span data-stu-id="f390b-153">Create or overwrite the list</span></span> | `Set-MpPreference` |
|<span data-ttu-id="f390b-154">목록에 추가</span><span class="sxs-lookup"><span data-stu-id="f390b-154">Add to the list</span></span> | `Add-MpPreference` |
|<span data-ttu-id="f390b-155">목록에서 항목 제거</span><span class="sxs-lookup"><span data-stu-id="f390b-155">Remove items from the list</span></span> | `Remove-MpPreference` |

>[!IMPORTANT]
><span data-ttu-id="f390b-156">또는 를 사용하여 목록을 만든 경우 cmdlet을 다시 사용하여 기존 목록을 덮어 `Set-MpPreference` `Add-MpPreference` `Set-MpPreference` 덮어 니다.</span><span class="sxs-lookup"><span data-stu-id="f390b-156">If you have created a list, either with `Set-MpPreference` or `Add-MpPreference`, using the `Set-MpPreference` cmdlet again will overwrite the existing list.</span></span>

<span data-ttu-id="f390b-157">예를 들어 다음 코드는 Microsoft Defender AV 검사에서 지정된 프로세스에서 연 파일을 제외합니다.</span><span class="sxs-lookup"><span data-stu-id="f390b-157">For example, the following code snippet would cause Microsoft Defender AV scans to exclude any file that is opened by the specified process:</span></span>

```PowerShell
Add-MpPreference -ExclusionProcess "c:\internal\test.exe"
```

<span data-ttu-id="f390b-158">Microsoft Defender 바이러스 백신에서 PowerShell을 사용하는 방법에 대한 자세한 내용은 PowerShell cmdlet 및 Microsoft Defender 바이러스 백신 [cmdlet으로](/powershell/module/defender)바이러스 백신 관리를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="f390b-158">For more information on how to use PowerShell with Microsoft Defender Antivirus, see Manage antivirus with PowerShell cmdlets and [Microsoft Defender Antivirus cmdlets](/powershell/module/defender).</span></span>

### <a name="use-windows-management-instruction-wmi-to-exclude-files-that-have-been-opened-by-specified-processes-from-scans"></a><span data-ttu-id="f390b-159">WMI(Windows Management Instruction)를 사용하여 지정된 프로세스에서 연 파일을 검사에서 제외</span><span class="sxs-lookup"><span data-stu-id="f390b-159">Use Windows Management Instruction (WMI) to exclude files that have been opened by specified processes from scans</span></span>

<span data-ttu-id="f390b-160">다음 속성에 대해 MSFT_MpPreference 클래스의 [  **Set,** **Add** 및 **Remove**](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) 메서드를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f390b-160">Use the [**Set**, **Add**, and **Remove** methods of the **MSFT_MpPreference**](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) class for the following properties:</span></span>

```WMI
ExclusionProcess
```

<span data-ttu-id="f390b-161">**Set,** **Add** 및 **Remove는** PowerShell에서 , 및 의 사용과 `Set-MpPreference` `Add-MpPreference` `Remove-MpPreference` 유사합니다.</span><span class="sxs-lookup"><span data-stu-id="f390b-161">The use of **Set**, **Add**, and **Remove** is analogous to their counterparts in PowerShell: `Set-MpPreference`, `Add-MpPreference`, and `Remove-MpPreference`.</span></span>

<span data-ttu-id="f390b-162">자세한 정보 및 허용되는 매개 변수는 [WMIv2 api Windows Defender 참조하세요.](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)</span><span class="sxs-lookup"><span data-stu-id="f390b-162">For more information and allowed parameters, see  [Windows Defender WMIv2 APIs](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal).</span></span>

### <a name="use-the-windows-security-app-to-exclude-files-that-have-been-opened-by-specified-processes-from-scans"></a><span data-ttu-id="f390b-163">Windows 보안 앱을 사용하여 지정된 프로세스에서 연 파일을 검사에서 제외</span><span class="sxs-lookup"><span data-stu-id="f390b-163">Use the Windows Security app to exclude files that have been opened by specified processes from scans</span></span>

<span data-ttu-id="f390b-164">지침은 Windows 보안 앱에서 제외 [추가를](microsoft-defender-security-center-antivirus.md) 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="f390b-164">See [Add exclusions in the Windows Security app](microsoft-defender-security-center-antivirus.md) for instructions.</span></span>

## <a name="use-wildcards-in-the-process-exclusion-list"></a><span data-ttu-id="f390b-165">프로세스 제외 목록에서 와일드카드 사용</span><span class="sxs-lookup"><span data-stu-id="f390b-165">Use wildcards in the process exclusion list</span></span>

<span data-ttu-id="f390b-166">프로세스 제외 목록에서 와일드카드를 사용하는 것은 다른 제외 목록에서 사용하는 경우와 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="f390b-166">The use of wildcards in the process exclusion list is different from their use in other exclusion lists.</span></span>

<span data-ttu-id="f390b-167">특히 물음표() 와일드카드를 사용할 수 없습니다. 그리고 전체 경로의 끝에만 물음표( ) 와일드카드를 사용할 `?` `*` 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f390b-167">In particular, you cannot use the question mark (`?`) wildcard, and the asterisk (`*`) wildcard can only be used at the end of a complete path.</span></span> <span data-ttu-id="f390b-168">프로세스 제외 목록에서 항목을 정의할 때 환경 변수(예: )를 와일드카드로 사용할 `%ALLUSERSPROFILE%` 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f390b-168">You can still use environment variables (such as `%ALLUSERSPROFILE%`) as wildcards when defining items in the process exclusion list.</span></span>

<span data-ttu-id="f390b-169">다음 표에서는 프로세스 제외 목록에서 와일드카드를 사용하는 방법에 대해 설명하고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f390b-169">The following table describes how the wildcards can be used in the process exclusion list:</span></span>

|<span data-ttu-id="f390b-170">와일드카드</span><span class="sxs-lookup"><span data-stu-id="f390b-170">Wildcard</span></span> | <span data-ttu-id="f390b-171">예제 사용</span><span class="sxs-lookup"><span data-stu-id="f390b-171">Example use</span></span> | <span data-ttu-id="f390b-172">일치 예제</span><span class="sxs-lookup"><span data-stu-id="f390b-172">Example matches</span></span> |
|:---|:---|:---|
|<span data-ttu-id="f390b-173">`*` (asterisk)</span><span class="sxs-lookup"><span data-stu-id="f390b-173">`*` (asterisk)</span></span> <br/><br/> <span data-ttu-id="f390b-174">문자 수에 따라 바꾸기</span><span class="sxs-lookup"><span data-stu-id="f390b-174">Replaces any number of characters</span></span> | `C:\MyData\*` | <span data-ttu-id="f390b-175">모든 파일에서 연 파일 `C:\MyData\file.exe`</span><span class="sxs-lookup"><span data-stu-id="f390b-175">Any file opened by `C:\MyData\file.exe`</span></span> |
|<span data-ttu-id="f390b-176">환경 변수</span><span class="sxs-lookup"><span data-stu-id="f390b-176">Environment variables</span></span> <br/><br/> <span data-ttu-id="f390b-177">제외를 평가할 때 정의된 변수가 경로로 채워지기</span><span class="sxs-lookup"><span data-stu-id="f390b-177">The defined variable is populated as a path when the exclusion is evaluated</span></span> | `%ALLUSERSPROFILE%\CustomLogFiles\file.exe` | <span data-ttu-id="f390b-178">모든 파일에서 연 파일 `C:\ProgramData\CustomLogFiles\file.exe`</span><span class="sxs-lookup"><span data-stu-id="f390b-178">Any file opened by `C:\ProgramData\CustomLogFiles\file.exe`</span></span> |

## <a name="review-the-list-of-exclusions"></a><span data-ttu-id="f390b-179">제외 목록 검토</span><span class="sxs-lookup"><span data-stu-id="f390b-179">Review the list of exclusions</span></span>

<span data-ttu-id="f390b-180">MpCmdRun, PowerShell, [Microsoft Endpoint Configuration Manager,](/configmgr/protect/deploy-use/endpoint-antimalware-policies#exclusion-settings) [Intune](/intune/device-restrictions-configure)또는 Windows 보안 앱으로 제외 목록의 항목을 검색할 [수 있습니다.](microsoft-defender-security-center-antivirus.md)</span><span class="sxs-lookup"><span data-stu-id="f390b-180">You can retrieve the items in the exclusion list with MpCmdRun, PowerShell, [Microsoft Endpoint Configuration Manager](/configmgr/protect/deploy-use/endpoint-antimalware-policies#exclusion-settings), [Intune](/intune/device-restrictions-configure), or the [Windows Security app](microsoft-defender-security-center-antivirus.md).</span></span>

<span data-ttu-id="f390b-181">PowerShell을 사용하는 경우 다음 두 가지 방법으로 목록을 검색할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f390b-181">If you use PowerShell, you can retrieve the list in two ways:</span></span>

- <span data-ttu-id="f390b-182">모든 Microsoft Defender 바이러스 백신 기본 설정의 상태를 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="f390b-182">Retrieve the status of all Microsoft Defender Antivirus preferences.</span></span> <span data-ttu-id="f390b-183">각 목록은 별도의 줄에 표시되지만 각 목록 내의 항목이 같은 줄로 결합됩니다.</span><span class="sxs-lookup"><span data-stu-id="f390b-183">Each of the lists will be displayed on separate lines, but the items within each list will be combined into the same line.</span></span>
- <span data-ttu-id="f390b-184">모든 기본 설정의 상태를 변수에 기록하고 해당 변수를 사용하여 관심 있는 특정 목록만 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="f390b-184">Write the status of all preferences to a variable, and use that variable to only call the specific list you are interested in.</span></span> <span data-ttu-id="f390b-185">각 `Add-MpPreference` 사용은 새 줄에 기록됩니다.</span><span class="sxs-lookup"><span data-stu-id="f390b-185">Each use of `Add-MpPreference` is written to a new line.</span></span>

### <a name="validate-the-exclusion-list-by-using-mpcmdrun"></a><span data-ttu-id="f390b-186">MpCmdRun을 사용하여 제외 목록 유효성 검사</span><span class="sxs-lookup"><span data-stu-id="f390b-186">Validate the exclusion list by using MpCmdRun</span></span>

<span data-ttu-id="f390b-187">전용 명령줄 도구에서 제외를 확인하려면 mpcmdrun.exe[명령을 ](./command-line-arguments-microsoft-defender-antivirus.md?branch=v-anbic-wdav-new-mpcmdrun-options)사용합니다.</span><span class="sxs-lookup"><span data-stu-id="f390b-187">To check exclusions with the dedicated [command-line tool mpcmdrun.exe](./command-line-arguments-microsoft-defender-antivirus.md?branch=v-anbic-wdav-new-mpcmdrun-options), use the following command:</span></span>

```DOS
MpCmdRun.exe -CheckExclusion -path <path>
```

> [!NOTE]
> <span data-ttu-id="f390b-188">MpCmdRun에서 제외를 확인하려면 Microsoft Defender Antivirus CAMP 버전 4.18.1812.3(2018년 12월에 출시) 이상이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="f390b-188">Checking exclusions with MpCmdRun requires Microsoft Defender Antivirus CAMP version 4.18.1812.3 (released in December 2018) or later.</span></span>


### <a name="review-the-list-of-exclusions-alongside-all-other-microsoft-defender-antivirus-preferences-by-using-powershell"></a><span data-ttu-id="f390b-189">PowerShell을 사용하여 다른 모든 Microsoft Defender 바이러스 백신 기본 설정과 함께 제외 목록 검토</span><span class="sxs-lookup"><span data-stu-id="f390b-189">Review the list of exclusions alongside all other Microsoft Defender Antivirus preferences by using PowerShell</span></span>

<span data-ttu-id="f390b-190">다음 cmdlet을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="f390b-190">Use the following cmdlet:</span></span>

```PowerShell
Get-MpPreference
```

<span data-ttu-id="f390b-191">Microsoft Defender 바이러스 백신과 함께 PowerShell을 사용하는 방법에 대한 자세한 내용은 [PowerShell cmdlet을](use-powershell-cmdlets-microsoft-defender-antivirus.md) 사용하여 Microsoft Defender 바이러스 백신 및 [Defender cmdlet](/powershell/module/defender) 구성 및 실행을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="f390b-191">See [Use PowerShell cmdlets to configure and run Microsoft Defender Antivirus](use-powershell-cmdlets-microsoft-defender-antivirus.md) and [Defender cmdlets](/powershell/module/defender) for more information on how to use PowerShell with Microsoft Defender Antivirus.</span></span>

### <a name="retrieve-a-specific-exclusions-list-by-using-powershell"></a><span data-ttu-id="f390b-192">PowerShell을 사용하여 특정 제외 목록 검색</span><span class="sxs-lookup"><span data-stu-id="f390b-192">Retrieve a specific exclusions list by using PowerShell</span></span>

<span data-ttu-id="f390b-193">다음 코드 코드 코드를 사용하여 각 줄을 별도의 명령으로 입력합니다. **WDAVprefs를** 변수의 이름을 지정하려는 레이블로 대체합니다.</span><span class="sxs-lookup"><span data-stu-id="f390b-193">Use the following code snippet (enter each line as a separate command); replace **WDAVprefs** with whatever label you want to name the variable:</span></span>

```PowerShell
$WDAVprefs = Get-MpPreference
$WDAVprefs.ExclusionProcess
```

<span data-ttu-id="f390b-194">Microsoft Defender 바이러스 백신과 함께 PowerShell을 사용하는 방법에 대한 자세한 내용은 [PowerShell cmdlet을](use-powershell-cmdlets-microsoft-defender-antivirus.md) 사용하여 Microsoft Defender 바이러스 백신 및 [Defender cmdlet](/powershell/module/defender) 구성 및 실행을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="f390b-194">See [Use PowerShell cmdlets to configure and run Microsoft Defender Antivirus](use-powershell-cmdlets-microsoft-defender-antivirus.md) and [Defender cmdlets](/powershell/module/defender) for more information on how to use PowerShell with Microsoft Defender Antivirus.</span></span>

## <a name="related-articles"></a><span data-ttu-id="f390b-195">관련 문서</span><span class="sxs-lookup"><span data-stu-id="f390b-195">Related articles</span></span>

- [<span data-ttu-id="f390b-196">Microsoft Defender 바이러스 백신 검사에서 제외 구성 및 유효성 검사</span><span class="sxs-lookup"><span data-stu-id="f390b-196">Configure and validate exclusions in Microsoft Defender Antivirus scans</span></span>](configure-exclusions-microsoft-defender-antivirus.md)
- [<span data-ttu-id="f390b-197">파일 이름, 확장명 및 폴더 위치를 기반으로 제외 구성 및 유효성 검사</span><span class="sxs-lookup"><span data-stu-id="f390b-197">Configure and validate exclusions based on file name, extension, and folder location</span></span>](configure-extension-file-exclusions-microsoft-defender-antivirus.md)
- [<span data-ttu-id="f390b-198">Windows Server에서 Microsoft Defender 바이러스 백신 제외 구성</span><span class="sxs-lookup"><span data-stu-id="f390b-198">Configure Microsoft Defender Antivirus exclusions on Windows Server</span></span>](configure-server-exclusions-microsoft-defender-antivirus.md)
- [<span data-ttu-id="f390b-199">제외를 정의할 때 피해야 하는 일반적인 실수</span><span class="sxs-lookup"><span data-stu-id="f390b-199">Common mistakes to avoid when defining exclusions</span></span>](common-exclusion-mistakes-microsoft-defender-antivirus.md)
- [<span data-ttu-id="f390b-200">Microsoft Defender 바이러스 백신 검사 및 수정 사용자 지정, 시작 및 결과 검토</span><span class="sxs-lookup"><span data-stu-id="f390b-200">Customize, initiate, and review the results of Microsoft Defender Antivirus scans and remediation</span></span>](customize-run-review-remediate-scans-microsoft-defender-antivirus.md)
- [<span data-ttu-id="f390b-201">Windows 10의 Microsoft Defender 바이러스 백신</span><span class="sxs-lookup"><span data-stu-id="f390b-201">Microsoft Defender Antivirus in Windows 10</span></span>](microsoft-defender-antivirus-in-windows-10.md)