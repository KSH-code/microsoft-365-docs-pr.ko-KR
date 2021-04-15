---
title: 확장명, 이름 또는 위치를 기준으로 제외 구성 및 유효성 검사
description: 파일 확장명, 파일 이름 또는 위치에 따라 Microsoft Defender 바이러스 백신 검사에서 파일을 제외합니다.
keywords: 제외, 파일, 확장명, 파일 형식, 폴더 이름, 파일 이름, 검사
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
localization_priority: normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.openlocfilehash: 338dc249bcd4e092f5a2be39e3d045d094ed957a
ms.sourcegitcommit: 7a339c9f7039825d131b39481ddf54c57b021b11
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2021
ms.locfileid: "51765218"
---
# <a name="configure-and-validate-exclusions-based-on-file-extension-and-folder-location"></a><span data-ttu-id="84f51-104">파일 확장명 및 폴더 위치에 따라 제외 구성 및 유효성 검사</span><span class="sxs-lookup"><span data-stu-id="84f51-104">Configure and validate exclusions based on file extension and folder location</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="84f51-105">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="84f51-105">**Applies to:**</span></span>

- <span data-ttu-id="84f51-106">[엔드포인트용 Microsoft Defender](/microsoft-365/security/defender-endpoint/) </span><span class="sxs-lookup"><span data-stu-id="84f51-106">[Microsoft Defender for Endpoint](/microsoft-365/security/defender-endpoint/)</span></span>

> [!IMPORTANT]
> <span data-ttu-id="84f51-107">Microsoft Defender 바이러스 백신 제외는 끝점 감지 및 [응답(EDR),](/microsoft-365/security/defender-endpoint/overview-endpoint-detection-response) [ASR(공격](/microsoft-365/security/defender-endpoint/attack-surface-reduction)표면 축소) 규칙 및 제어된 폴더 액세스 등 다른 끝점용 Microsoft Defender 기능에 적용되지 [않습니다.](/microsoft-365/security/defender-endpoint/controlled-folders)</span><span class="sxs-lookup"><span data-stu-id="84f51-107">Microsoft Defender Antivirus exclusions don't apply to other Microsoft Defender for Endpoint capabilities, including [endpoint detection and response (EDR)](/microsoft-365/security/defender-endpoint/overview-endpoint-detection-response), [attack surface reduction (ASR) rules](/microsoft-365/security/defender-endpoint/attack-surface-reduction), and [controlled folder access](/microsoft-365/security/defender-endpoint/controlled-folders).</span></span> <span data-ttu-id="84f51-108">이 문서에 설명된 방법을 사용하여 제외하는 파일은 여전히 EDR 경고 및 기타 검색을 트리거할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="84f51-108">Files that you exclude using the methods described in this article can still trigger EDR alerts and other detections.</span></span> <span data-ttu-id="84f51-109">파일을 광범위하게 제외하려면 끝점 사용자 지정 표시기용 Microsoft [Defender에 추가합니다.](/microsoft-365/security/defender-endpoint/manage-indicators)</span><span class="sxs-lookup"><span data-stu-id="84f51-109">To exclude files broadly, add them to the Microsoft Defender for Endpoint [custom indicators](/microsoft-365/security/defender-endpoint/manage-indicators).</span></span>

## <a name="exclusion-lists"></a><span data-ttu-id="84f51-110">제외 목록</span><span class="sxs-lookup"><span data-stu-id="84f51-110">Exclusion lists</span></span>

<span data-ttu-id="84f51-111">제외 목록을 수정하여 Microsoft Defender 바이러스 백신 검사에서 특정 파일을 제외할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="84f51-111">You can exclude certain files from Microsoft Defender Antivirus scans by modifying exclusion lists.</span></span> <span data-ttu-id="84f51-112">**일반적으로 제외를** 적용할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="84f51-112">**Generally, you shouldn't need to apply exclusions**.</span></span> <span data-ttu-id="84f51-113">Microsoft Defender 바이러스 백신에는 알려진 운영 체제 동작 및 일반적인 관리 파일(예: 엔터프라이즈 관리, 데이터베이스 관리 및 기타 엔터프라이즈 시나리오 및 상황에 사용되는 파일)을 기반으로 하는 많은 자동 제외가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="84f51-113">Microsoft Defender Antivirus includes many automatic exclusions based on known operating system behaviors and typical management files, such as those used in enterprise management, database management, and other enterprise scenarios and situations.</span></span>

> [!NOTE]
> <span data-ttu-id="84f51-114">제외는 PUA(잠재적으로 원치 않는 앱) 검색에도 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="84f51-114">Exclusions apply to Potentially Unwanted Apps (PUA) detections as well.</span></span>

> [!NOTE]
> <span data-ttu-id="84f51-115">자동 제외는 Windows Server 2016 이상에만 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="84f51-115">Automatic exclusions apply only to Windows Server 2016 and above.</span></span> <span data-ttu-id="84f51-116">이러한 제외는 Windows 보안 앱과 PowerShell에서 표시되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="84f51-116">These exclusions are not visible in the Windows Security app and in PowerShell.</span></span>

<span data-ttu-id="84f51-117">이 문서에서는 파일 및 폴더에 대한 제외 목록을 구성하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="84f51-117">This article  describes how to configure exclusion lists for the files and folders.</span></span> <span data-ttu-id="84f51-118">제외 [목록을 정의하기](configure-exclusions-microsoft-defender-antivirus.md#recommendations-for-defining-exclusions) 전에 제외를 정의하기 위한 권장 사항을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="84f51-118">See [Recommendations for defining exclusions](configure-exclusions-microsoft-defender-antivirus.md#recommendations-for-defining-exclusions) before defining your exclusion lists.</span></span>

| <span data-ttu-id="84f51-119">제외</span><span class="sxs-lookup"><span data-stu-id="84f51-119">Exclusion</span></span> | <span data-ttu-id="84f51-120">예제</span><span class="sxs-lookup"><span data-stu-id="84f51-120">Examples</span></span> | <span data-ttu-id="84f51-121">제외 목록</span><span class="sxs-lookup"><span data-stu-id="84f51-121">Exclusion list</span></span> |
|:---|:---|:---|
|<span data-ttu-id="84f51-122">특정 확장명을 사용 하는 모든 파일</span><span class="sxs-lookup"><span data-stu-id="84f51-122">Any file with a specific extension</span></span> | <span data-ttu-id="84f51-123">지정된 확장명을 사용 하는 모든 파일, 컴퓨터의 아무 곳이나.</span><span class="sxs-lookup"><span data-stu-id="84f51-123">All files with the specified extension, anywhere on the machine.</span></span> <p> <span data-ttu-id="84f51-124">유효한 구문: `.test` 및 `test`</span><span class="sxs-lookup"><span data-stu-id="84f51-124">Valid syntax: `.test` and `test`</span></span>  | <span data-ttu-id="84f51-125">확장 제외</span><span class="sxs-lookup"><span data-stu-id="84f51-125">Extension exclusions</span></span> |
|<span data-ttu-id="84f51-126">특정 폴더 아래에 있는 모든 파일</span><span class="sxs-lookup"><span data-stu-id="84f51-126">Any file under a specific folder</span></span> | <span data-ttu-id="84f51-127">폴더 아래에 있는 `c:\test\sample` 모든 파일</span><span class="sxs-lookup"><span data-stu-id="84f51-127">All files under the `c:\test\sample` folder</span></span> | <span data-ttu-id="84f51-128">파일 및 폴더 제외</span><span class="sxs-lookup"><span data-stu-id="84f51-128">File and folder exclusions</span></span> |
| <span data-ttu-id="84f51-129">특정 폴더의 특정 파일</span><span class="sxs-lookup"><span data-stu-id="84f51-129">A specific file in a specific folder</span></span> | <span data-ttu-id="84f51-130">파일만 `c:\sample\sample.test`</span><span class="sxs-lookup"><span data-stu-id="84f51-130">The file `c:\sample\sample.test` only</span></span> | <span data-ttu-id="84f51-131">파일 및 폴더 제외</span><span class="sxs-lookup"><span data-stu-id="84f51-131">File and folder exclusions</span></span> |
| <span data-ttu-id="84f51-132">특정 프로세스</span><span class="sxs-lookup"><span data-stu-id="84f51-132">A specific process</span></span> | <span data-ttu-id="84f51-133">실행 파일 `c:\test\process.exe`</span><span class="sxs-lookup"><span data-stu-id="84f51-133">The executable file `c:\test\process.exe`</span></span> | <span data-ttu-id="84f51-134">파일 및 폴더 제외</span><span class="sxs-lookup"><span data-stu-id="84f51-134">File and folder exclusions</span></span> |

<span data-ttu-id="84f51-135">제외 목록에는 다음과 같은 특성이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="84f51-135">Exclusion lists have the following characteristics:</span></span>

- <span data-ttu-id="84f51-136">폴더 제외는 하위 폴더가 재분석 지점이 없는 한 해당 폴더 아래에 있는 모든 파일 및 폴더에 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="84f51-136">Folder exclusions apply to all files and folders under that folder, unless the subfolder is a reparse point.</span></span> <span data-ttu-id="84f51-137">재분석 지점 하위폴더는 별도로 제외해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="84f51-137">Reparse point subfolders must be excluded separately.</span></span>
- <span data-ttu-id="84f51-138">경로 또는 폴더가 정의되어 있지 않은 경우 파일 확장명은 정의된 확장명을 적용하는 모든 파일 이름에 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="84f51-138">File extensions apply to any file name with the defined extension if a path or folder is not defined.</span></span>

> [!IMPORTANT]
> - <span data-ttu-id="84f51-139">와일드카드(예: Asterisk( )를 사용하는 경우 제외 규칙이 해석된 \* 방식이 변경됩니다.</span><span class="sxs-lookup"><span data-stu-id="84f51-139">Using wildcards such as the asterisk (\*) will alter how the exclusion rules are interpreted.</span></span> <span data-ttu-id="84f51-140">와일드카드 작동 방식에 대한 중요한 정보는 파일 이름 및 폴더 경로 또는 확장명 제외 목록에서 와일드카드 사용 섹션을 참조하세요. [](#use-wildcards-in-the-file-name-and-folder-path-or-extension-exclusion-lists)</span><span class="sxs-lookup"><span data-stu-id="84f51-140">See the [Use wildcards in the file name and folder path or extension exclusion lists](#use-wildcards-in-the-file-name-and-folder-path-or-extension-exclusion-lists) section for important information about how wildcards work.</span></span>
> - <span data-ttu-id="84f51-141">매핑된 네트워크 드라이브는 제외할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="84f51-141">You cannot exclude mapped network drives.</span></span> <span data-ttu-id="84f51-142">실제 네트워크 경로를 지정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="84f51-142">You must specify the actual network path.</span></span>
> - <span data-ttu-id="84f51-143">Microsoft Defender 바이러스 백신 서비스가 시작된 후 만들어지며 제외 목록에 추가된 재분석 지점인 폴더는 포함되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="84f51-143">Folders that are reparse points that are created after the Microsoft Defender Antivirus service starts and that have been added to the exclusion list will not be included.</span></span> <span data-ttu-id="84f51-144">새 재분석 지점이 유효한 제외 대상으로 인식될 수 있는 경우 서비스를 다시 시작(Windows 다시 시작)해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="84f51-144">You must restart the service (by restarting Windows) for new reparse points to be recognized as a valid exclusion target.</span></span>

<span data-ttu-id="84f51-145">특정 프로세스에서 연 파일을 제외하려면 프로세스에서 연 파일에 대한 제외 구성 및 [유효성 검사를 참조합니다.](configure-process-opened-file-exclusions-microsoft-defender-antivirus.md)</span><span class="sxs-lookup"><span data-stu-id="84f51-145">To exclude files opened by a specific process, see [Configure and validate exclusions for files opened by processes](configure-process-opened-file-exclusions-microsoft-defender-antivirus.md).</span></span>

<span data-ttu-id="84f51-146">제외는 예약된 [검사,](scheduled-catch-up-scans-microsoft-defender-antivirus.md)요구 시 [](run-scan-microsoft-defender-antivirus.md)검사 및 실시간 보호에 [적용됩니다.](configure-real-time-protection-microsoft-defender-antivirus.md)</span><span class="sxs-lookup"><span data-stu-id="84f51-146">The exclusions apply to [scheduled scans](scheduled-catch-up-scans-microsoft-defender-antivirus.md), [on-demand scans](run-scan-microsoft-defender-antivirus.md), and [real-time protection](configure-real-time-protection-microsoft-defender-antivirus.md).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="84f51-147">그룹 정책으로 변경된 제외 **목록은** Windows 보안 앱의 목록에 [표시됩니다.](microsoft-defender-security-center-antivirus.md)</span><span class="sxs-lookup"><span data-stu-id="84f51-147">Exclusion list changes made with Group Policy **will show** in the lists in the [Windows Security app](microsoft-defender-security-center-antivirus.md).</span></span>
> <span data-ttu-id="84f51-148">Windows 보안 앱의 변경 **내용은 그룹** 정책 목록에 표시되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="84f51-148">Changes made in the Windows Security app **will not show** in the Group Policy lists.</span></span>

<span data-ttu-id="84f51-149">기본적으로 PowerShell 및 WMI를 통해 변경한 내용을 포함하여 관리자 권한이 있는 사용자에 의해 목록에 대한 로컬 변경 내용은 그룹 정책, Configuration Manager 또는 Intune에서 정의(및 배포)된 목록과 병합됩니다.</span><span class="sxs-lookup"><span data-stu-id="84f51-149">By default, local changes made to the lists (by users with administrator privileges, including changes made with PowerShell and WMI) will be merged with the lists as defined (and deployed) by Group Policy, Configuration Manager, or Intune.</span></span> <span data-ttu-id="84f51-150">충돌이 있는 경우 그룹 정책 목록이 우선합니다.</span><span class="sxs-lookup"><span data-stu-id="84f51-150">The Group Policy lists take precedence when there are conflicts.</span></span>

<span data-ttu-id="84f51-151">로컬 [및](configure-local-policy-overrides-microsoft-defender-antivirus.md#merge-lists) 전역으로 정의된 제외 목록이 병합되는 방법을 구성하여 로컬 변경 내용이 관리되는 배포 설정을 다시 정의할 수 있도록 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="84f51-151">You can [configure how locally and globally defined exclusions lists are merged](configure-local-policy-overrides-microsoft-defender-antivirus.md#merge-lists) to allow local changes to override managed deployment settings.</span></span>

## <a name="configure-the-list-of-exclusions-based-on-folder-name-or-file-extension"></a><span data-ttu-id="84f51-152">폴더 이름 또는 파일 확장명에 따라 제외 목록 구성</span><span class="sxs-lookup"><span data-stu-id="84f51-152">Configure the list of exclusions based on folder name or file extension</span></span>

### <a name="use-intune-to-configure-file-name-folder-or-file-extension-exclusions"></a><span data-ttu-id="84f51-153">Intune을 사용하여 파일 이름, 폴더 또는 파일 확장명 제외 구성</span><span class="sxs-lookup"><span data-stu-id="84f51-153">Use Intune to configure file name, folder, or file extension exclusions</span></span>

<span data-ttu-id="84f51-154">다음 문서를 참조합니다.</span><span class="sxs-lookup"><span data-stu-id="84f51-154">See the following articles:</span></span>
- [<span data-ttu-id="84f51-155">Microsoft Intune에서 장치 제한 설정 구성</span><span class="sxs-lookup"><span data-stu-id="84f51-155">Configure device restriction settings in Microsoft Intune</span></span>](/intune/device-restrictions-configure)
- [<span data-ttu-id="84f51-156">Intune의 Windows 10에 대한 Microsoft Defender 바이러스 백신 장치 제한 설정</span><span class="sxs-lookup"><span data-stu-id="84f51-156">Microsoft Defender Antivirus device restriction settings for Windows 10 in Intune</span></span>](/intune/device-restrictions-windows-10#microsoft-defender-antivirus)

### <a name="use-configuration-manager-to-configure-file-name-folder-or-file-extension-exclusions"></a><span data-ttu-id="84f51-157">Configuration Manager를 사용하여 파일 이름, 폴더 또는 파일 확장명 제외 구성</span><span class="sxs-lookup"><span data-stu-id="84f51-157">Use Configuration Manager to configure file name, folder, or file extension exclusions</span></span>

<span data-ttu-id="84f51-158">Microsoft Endpoint Manager(현재 분기)를 구성하는 방법에 대한 자세한 내용은 맬웨어 방지 정책을 만들고 배포하는 [방법:](/configmgr/protect/deploy-use/endpoint-antimalware-policies#exclusion-settings) 제외 설정을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="84f51-158">See [How to create and deploy antimalware policies: Exclusion settings](/configmgr/protect/deploy-use/endpoint-antimalware-policies#exclusion-settings) for details on configuring Microsoft Endpoint Manager (current branch).</span></span>

### <a name="use-group-policy-to-configure-folder-or-file-extension-exclusions"></a><span data-ttu-id="84f51-159">그룹 정책을 사용하여 폴더 또는 파일 확장명 제외 구성</span><span class="sxs-lookup"><span data-stu-id="84f51-159">Use Group Policy to configure folder or file extension exclusions</span></span>

>[!NOTE]
><span data-ttu-id="84f51-160">파일의 정식 경로를 지정하면 해당 파일만 제외됩니다.</span><span class="sxs-lookup"><span data-stu-id="84f51-160">If you specify a fully qualified path to a file, then only that file is excluded.</span></span> <span data-ttu-id="84f51-161">제외에 폴더가 정의되어 있는 경우 해당 폴더의 모든 파일 및 하위 폴더는 제외됩니다.</span><span class="sxs-lookup"><span data-stu-id="84f51-161">If a folder is defined in the exclusion, then all files and subdirectories under that folder are excluded.</span></span>

1. <span data-ttu-id="84f51-162">그룹 정책 관리 컴퓨터에서 그룹 [](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))정책 관리 콘솔을 열고 구성할 그룹 정책 개체를 마우스 오른쪽 단추로 클릭하고 편집을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="84f51-162">On your Group Policy management computer, open the [Group Policy Management Console](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)), right-click the Group Policy Object you want to configure and click **Edit**.</span></span>

2. <span data-ttu-id="84f51-163">그룹 정책 **관리 편집기에서** 컴퓨터 **구성으로 이동하고** 관리 템플릿 **을 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="84f51-163">In the **Group Policy Management Editor** go to **Computer configuration** and select **Administrative templates**.</span></span>

3. <span data-ttu-id="84f51-164">**Windows** 구성 요소 Microsoft Defender 바이러스 백신 제외까지  >    >  **트리를 확장합니다.**</span><span class="sxs-lookup"><span data-stu-id="84f51-164">Expand the tree to **Windows components** > **Microsoft Defender Antivirus** > **Exclusions**.</span></span>

4. <span data-ttu-id="84f51-165">편집할 **경로** 제외 설정을 열고 제외를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="84f51-165">Open the **Path Exclusions** setting for editing, and add your exclusions.</span></span>

    1. <span data-ttu-id="84f51-166">옵션을 사용으로 **설정합니다.**</span><span class="sxs-lookup"><span data-stu-id="84f51-166">Set the option to **Enabled**.</span></span>
    1. <span data-ttu-id="84f51-167">옵션 **섹션에서** 표시를 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="84f51-167">Under the **Options** section, click **Show**.</span></span>
    1. <span data-ttu-id="84f51-168">값 이름 열 아래에 각 폴더를 자체 **줄에 지정합니다.**</span><span class="sxs-lookup"><span data-stu-id="84f51-168">Specify each folder on its own line under the **Value name** column.</span></span>
    1. <span data-ttu-id="84f51-169">파일을 지정하는 경우 드라이브 문자, 폴더 경로, 파일 이름 및 확장명을 포함하여 파일의 정식 경로를 입력해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="84f51-169">If you are specifying a file, ensure that you enter a fully qualified path to the file, including the drive letter, folder path, file name, and extension.</span></span> <span data-ttu-id="84f51-170">값 **열에 0을** **입력합니다.**</span><span class="sxs-lookup"><span data-stu-id="84f51-170">Enter **0** in the **Value** column.</span></span>

5. <span data-ttu-id="84f51-171">**확인** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="84f51-171">Choose **OK**.</span></span>

6. <span data-ttu-id="84f51-172">편집할 **확장 제외** 설정을 열고 제외를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="84f51-172">Open the **Extension Exclusions** setting for editing and add your exclusions.</span></span>

    1. <span data-ttu-id="84f51-173">옵션을 사용으로 **설정합니다.**</span><span class="sxs-lookup"><span data-stu-id="84f51-173">Set the option to **Enabled**.</span></span>
    1. <span data-ttu-id="84f51-174">옵션 **섹션에서** 표시를 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="84f51-174">Under the **Options** section, select **Show**.</span></span>
    1. <span data-ttu-id="84f51-175">값 이름 열 아래에 각 파일 확장명을 자체 **줄에 입력합니다.**</span><span class="sxs-lookup"><span data-stu-id="84f51-175">Enter each file extension on its own line under the **Value name** column.</span></span>  <span data-ttu-id="84f51-176">값 **열에 0을** **입력합니다.**</span><span class="sxs-lookup"><span data-stu-id="84f51-176">Enter **0** in the **Value** column.</span></span>

7. <span data-ttu-id="84f51-177">**확인** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="84f51-177">Choose **OK**.</span></span>

<a id="ps"></a>

### <a name="use-powershell-cmdlets-to-configure-file-name-folder-or-file-extension-exclusions"></a><span data-ttu-id="84f51-178">PowerShell cmdlet을 사용하여 파일 이름, 폴더 또는 파일 확장명 제외 구성</span><span class="sxs-lookup"><span data-stu-id="84f51-178">Use PowerShell cmdlets to configure file name, folder, or file extension exclusions</span></span>

<span data-ttu-id="84f51-179">PowerShell을 사용하여 확장명, 위치 또는 파일 이름에 따라 파일의 제외를 추가하거나 제거하려면 세 개의 cmdlet과 적절한 제외 목록 매개 변수의 조합을 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="84f51-179">Using PowerShell to add or remove exclusions for files based on the extension, location, or file name requires using a combination of three cmdlets and the appropriate exclusion list parameter.</span></span> <span data-ttu-id="84f51-180">cmdlet은 [모두 Defender 모듈에 있습니다.](/powershell/module/defender/)</span><span class="sxs-lookup"><span data-stu-id="84f51-180">The cmdlets are all in the [Defender module](/powershell/module/defender/).</span></span>

<span data-ttu-id="84f51-181">cmdlet의 형식은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="84f51-181">The format for the cmdlets is as follows:</span></span>

```PowerShell
<cmdlet> -<exclusion list> "<item>"
```

<span data-ttu-id="84f51-182">다음을 다음으로 `<cmdlet>` 허용합니다.</span><span class="sxs-lookup"><span data-stu-id="84f51-182">The following are allowed as the `<cmdlet>`:</span></span>

| <span data-ttu-id="84f51-183">구성 작업</span><span class="sxs-lookup"><span data-stu-id="84f51-183">Configuration action</span></span> | <span data-ttu-id="84f51-184">PowerShell cmdlet</span><span class="sxs-lookup"><span data-stu-id="84f51-184">PowerShell cmdlet</span></span> |
|:---|:---|
|<span data-ttu-id="84f51-185">목록 만들기 또는 덮어 덮어 사용</span><span class="sxs-lookup"><span data-stu-id="84f51-185">Create or overwrite the list</span></span> | `Set-MpPreference` |
|<span data-ttu-id="84f51-186">목록에 추가</span><span class="sxs-lookup"><span data-stu-id="84f51-186">Add to the list</span></span> | `Add-MpPreference` |
|<span data-ttu-id="84f51-187">목록에서 항목 제거</span><span class="sxs-lookup"><span data-stu-id="84f51-187">Remove item from the list</span></span> | `Remove-MpPreference` |

<span data-ttu-id="84f51-188">다음을 다음으로 `<exclusion list>` 허용합니다.</span><span class="sxs-lookup"><span data-stu-id="84f51-188">The following are allowed as the `<exclusion list>`:</span></span>

| <span data-ttu-id="84f51-189">제외 유형</span><span class="sxs-lookup"><span data-stu-id="84f51-189">Exclusion type</span></span> | <span data-ttu-id="84f51-190">PowerShell 매개 변수</span><span class="sxs-lookup"><span data-stu-id="84f51-190">PowerShell parameter</span></span> |
|:---|:---|
| <span data-ttu-id="84f51-191">파일 확장명을 지정한 모든 파일</span><span class="sxs-lookup"><span data-stu-id="84f51-191">All files with a specified file extension</span></span> | `-ExclusionExtension` |
| <span data-ttu-id="84f51-192">폴더의 모든 파일(하위 폴더의 파일 포함) 또는 특정 파일</span><span class="sxs-lookup"><span data-stu-id="84f51-192">All files under a folder (including files in subdirectories), or a specific file</span></span> | `-ExclusionPath` |

> [!IMPORTANT]
> <span data-ttu-id="84f51-193">또는 를 사용하여 목록을 만든 경우 cmdlet을 다시 사용하여 기존 목록을 덮어 `Set-MpPreference` `Add-MpPreference` `Set-MpPreference` 덮어 니다.</span><span class="sxs-lookup"><span data-stu-id="84f51-193">If you have created a list, either with `Set-MpPreference` or `Add-MpPreference`, using the `Set-MpPreference` cmdlet again will overwrite the existing list.</span></span>

<span data-ttu-id="84f51-194">예를 들어 다음 코드는 Microsoft Defender 바이러스 백신 검사에서 파일 확장명을 사용하여 모든 파일을 `.test` 제외합니다.</span><span class="sxs-lookup"><span data-stu-id="84f51-194">For example, the following code snippet would cause Microsoft Defender Antivirus scans to exclude any file with the `.test` file extension:</span></span>

```PowerShell
Add-MpPreference -ExclusionExtension ".test"
```

<span data-ttu-id="84f51-195">자세한 내용은 [PowerShell cmdlet을](use-powershell-cmdlets-microsoft-defender-antivirus.md) 사용하여 Microsoft Defender 바이러스 백신 및 Defender cmdlet 구성 및 [실행을 참조하세요.](/powershell/module/defender/)</span><span class="sxs-lookup"><span data-stu-id="84f51-195">For more information, see [Use PowerShell cmdlets to configure and run Microsoft Defender Antivirus](use-powershell-cmdlets-microsoft-defender-antivirus.md) and [Defender cmdlets](/powershell/module/defender/).</span></span>

### <a name="use-windows-management-instruction-wmi-to-configure-file-name-folder-or-file-extension-exclusions"></a><span data-ttu-id="84f51-196">WMI(Windows Management Instruction)를 사용하여 파일 이름, 폴더 또는 파일 확장명 제외 구성</span><span class="sxs-lookup"><span data-stu-id="84f51-196">Use Windows Management Instruction (WMI) to configure file name, folder, or file extension exclusions</span></span>

<span data-ttu-id="84f51-197">다음 속성에 대해 MSFT_MpPreference 클래스의 [  **Set,** **Add** 및 **Remove**](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) 메서드를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="84f51-197">Use the [**Set**, **Add**, and **Remove** methods of the **MSFT_MpPreference**](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) class for the following properties:</span></span>

```WMI
ExclusionExtension
ExclusionPath
```

<span data-ttu-id="84f51-198">**Set,** **Add** 및 **Remove는** PowerShell에서 , 및 의 사용과 `Set-MpPreference` `Add-MpPreference` `Remove-MpPreference` 유사합니다.</span><span class="sxs-lookup"><span data-stu-id="84f51-198">The use of **Set**, **Add**, and **Remove** is analogous to their counterparts in PowerShell: `Set-MpPreference`, `Add-MpPreference`, and `Remove-MpPreference`.</span></span>

<span data-ttu-id="84f51-199">자세한 내용은 [WMIv2 api Windows Defender 참조하세요.](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)</span><span class="sxs-lookup"><span data-stu-id="84f51-199">For more information, see [Windows Defender WMIv2 APIs](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal).</span></span>

<a id="man-tools"></a>

### <a name="use-the-windows-security-app-to-configure-file-name-folder-or-file-extension-exclusions"></a><span data-ttu-id="84f51-200">Windows 보안 앱을 사용하여 파일 이름, 폴더 또는 파일 확장명 제외 구성</span><span class="sxs-lookup"><span data-stu-id="84f51-200">Use the Windows Security app to configure file name, folder, or file extension exclusions</span></span>

<span data-ttu-id="84f51-201">지침은 Windows 보안 앱에서 제외 [추가를](microsoft-defender-security-center-antivirus.md) 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="84f51-201">See [Add exclusions in the Windows Security app](microsoft-defender-security-center-antivirus.md) for instructions.</span></span>

<a id="wildcards"></a>

## <a name="use-wildcards-in-the-file-name-and-folder-path-or-extension-exclusion-lists"></a><span data-ttu-id="84f51-202">파일 이름 및 폴더 경로 또는 확장명 제외 목록에 와일드카드 사용</span><span class="sxs-lookup"><span data-stu-id="84f51-202">Use wildcards in the file name and folder path or extension exclusion lists</span></span>

<span data-ttu-id="84f51-203">파일 이름 또는 폴더 경로 제외 목록에서 항목을 정의할 때 추가, 물음표 또는 환경 변수(예: )를 와일드카드로 사용할 `*` `?` 수 `%ALLUSERSPROFILE%` 있습니다.</span><span class="sxs-lookup"><span data-stu-id="84f51-203">You can use the asterisk `*`, question mark `?`, or environment variables (such as `%ALLUSERSPROFILE%`) as wildcards when defining items in the file name or folder path exclusion list.</span></span> <span data-ttu-id="84f51-204">이러한 와일드카드가 해석되는 방식은 다른 앱 및 언어에서 일반적인 사용법과 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="84f51-204">The way in which these wildcards are interpreted differs from their usual usage in other apps and languages.</span></span> <span data-ttu-id="84f51-205">특정 제한 사항을 이해하기 위해 이 섹션을 읽어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="84f51-205">Make sure to read this section to understand their specific limitations.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="84f51-206">이러한 와일드카드에 대한 주요 제한 사항 및 사용 시나리오가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="84f51-206">There are key limitations and usage scenarios for these wildcards:</span></span>
> - <span data-ttu-id="84f51-207">환경 변수 사용은 컴퓨터 변수 및 NT AUTHORITY\SYSTEM 계정으로 실행되는 프로세스에 적용할 수 있는 변수로 제한됩니다.</span><span class="sxs-lookup"><span data-stu-id="84f51-207">Environment variable usage is limited to machine variables and those applicable to processes running as an NT AUTHORITY\SYSTEM account.</span></span>
> - <span data-ttu-id="84f51-208">드라이브 문자 대신 와일드카드를 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="84f51-208">You cannot use a wildcard in place of a drive letter.</span></span>
> - <span data-ttu-id="84f51-209">폴더 제외의 추가 표시는 단일 `*` 폴더를 위한 것입니다.</span><span class="sxs-lookup"><span data-stu-id="84f51-209">An asterisk `*` in a folder exclusion stands in place for a single folder.</span></span> <span data-ttu-id="84f51-210">여러 인스턴스를 사용하여 지정되지 않은 이름을 사용하여 여러 개의 중첩된 폴더를 `\*\` 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="84f51-210">Use multiple instances of `\*\` to indicate multiple nested folders with unspecified names.</span></span>

<span data-ttu-id="84f51-211">다음 표에서는 와일드카드를 사용하는 방법을 설명하고 몇 가지 예를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="84f51-211">The following table describes how the wildcards can be used and provides some examples.</span></span>


|<span data-ttu-id="84f51-212">와일드카드</span><span class="sxs-lookup"><span data-stu-id="84f51-212">Wildcard</span></span>  |<span data-ttu-id="84f51-213">예제</span><span class="sxs-lookup"><span data-stu-id="84f51-213">Examples</span></span>  |
|:---------|:---------|
|<span data-ttu-id="84f51-214">`*` (asterisk)</span><span class="sxs-lookup"><span data-stu-id="84f51-214">`*` (asterisk)</span></span> <p> <span data-ttu-id="84f51-215">파일 **이름** 및 파일 확장명 포함에서, 추가 기능은 모든 문자를 대체하며 인수에 정의된 마지막 폴더의 파일에만 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="84f51-215">In **file name and file extension inclusions**, the asterisk replaces any number of characters, and only applies to files in the last folder defined in the argument.</span></span> <p> <span data-ttu-id="84f51-216">폴더 **제외에서는** 단일 폴더를 대체하는 추가 표시가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="84f51-216">In **folder exclusions**, the asterisk replaces a single folder.</span></span> <span data-ttu-id="84f51-217">여러 개의 폴더 슬래시를 사용하여 여러 개의 `*` `\` 중첩된 폴더를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="84f51-217">Use multiple `*` with folder slashes `\` to indicate multiple nested folders.</span></span> <span data-ttu-id="84f51-218">와일드 카드 및 명명된 폴더 수와 일치하면 모든 하위 폴더도 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="84f51-218">After matching the number of wild carded and named folders, all subfolders are also included.</span></span>   | <span data-ttu-id="84f51-219">`C:\MyData\*.txt` 포함 `C:\MyData\notes.txt`</span><span class="sxs-lookup"><span data-stu-id="84f51-219">`C:\MyData\*.txt` includes `C:\MyData\notes.txt`</span></span> <p> <span data-ttu-id="84f51-220">`C:\somepath\*\Data` 파일 및 해당 하위폴더와 해당 하위폴더를 `C:\somepath\Archives\Data` `C:\somepath\Authorized\Data` 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="84f51-220">`C:\somepath\*\Data` includes any file in `C:\somepath\Archives\Data` and its subfolders, and `C:\somepath\Authorized\Data` and its subfolders</span></span> <p> <span data-ttu-id="84f51-221">`C:\Serv\*\*\Backup` 파일 및 해당 하위폴더와 해당 `C:\Serv\Primary\Denied\Backup` `C:\Serv\Secondary\Allowed\Backup` 하위폴더를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="84f51-221">`C:\Serv\*\*\Backup` includes any file in `C:\Serv\Primary\Denied\Backup` and its subfolders and `C:\Serv\Secondary\Allowed\Backup` and its subfolders</span></span>     |
|<span data-ttu-id="84f51-222">`?` (물음표)</span><span class="sxs-lookup"><span data-stu-id="84f51-222">`?` (question mark)</span></span>  <p> <span data-ttu-id="84f51-223">파일 **이름** 및 파일 확장명 포함에서 물음표는 단일 문자를 대체하며 인수에 정의된 마지막 폴더의 파일에만 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="84f51-223">In **file name and file extension inclusions**, the question mark replaces a single character, and only applies to files in the last folder defined in the argument.</span></span> <p> <span data-ttu-id="84f51-224">폴더 **제외에서** 물음표는 폴더 이름의 단일 문자를 대체합니다.</span><span class="sxs-lookup"><span data-stu-id="84f51-224">In **folder exclusions**, the question mark replaces a single character in a folder name.</span></span> <span data-ttu-id="84f51-225">와일드 카드 및 명명된 폴더 수와 일치하면 모든 하위 폴더도 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="84f51-225">After matching the number of wild carded and named folders, all subfolders are also included.</span></span>   |<span data-ttu-id="84f51-226">`C:\MyData\my?.zip` 포함 `C:\MyData\my1.zip`</span><span class="sxs-lookup"><span data-stu-id="84f51-226">`C:\MyData\my?.zip` includes `C:\MyData\my1.zip`</span></span> <p> <span data-ttu-id="84f51-227">`C:\somepath\?\Data` 모든 파일 포함 및 해당 `C:\somepath\P\Data` 하위폴더</span><span class="sxs-lookup"><span data-stu-id="84f51-227">`C:\somepath\?\Data` includes any file in `C:\somepath\P\Data` and its subfolders</span></span>  <p> <span data-ttu-id="84f51-228">`C:\somepath\test0?\Data` 은 모든 파일과 해당 `C:\somepath\test01\Data` 하위폴더를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="84f51-228">`C:\somepath\test0?\Data` would include any file in `C:\somepath\test01\Data` and its subfolders</span></span>          |
|<span data-ttu-id="84f51-229">환경 변수</span><span class="sxs-lookup"><span data-stu-id="84f51-229">Environment variables</span></span> <p> <span data-ttu-id="84f51-230">제외를 평가할 때 정의된 변수가 경로로 채워지는 경우</span><span class="sxs-lookup"><span data-stu-id="84f51-230">The defined variable is populated as a path when the exclusion is evaluated.</span></span>          |<span data-ttu-id="84f51-231">`%ALLUSERSPROFILE%\CustomLogFiles` 다음을 포함합니다. `C:\ProgramData\CustomLogFiles\Folder1\file1.txt`</span><span class="sxs-lookup"><span data-stu-id="84f51-231">`%ALLUSERSPROFILE%\CustomLogFiles` would include `C:\ProgramData\CustomLogFiles\Folder1\file1.txt`</span></span>         |
        

> [!IMPORTANT]
> <span data-ttu-id="84f51-232">파일 제외 인수와 폴더 제외 인수를 함께 사용하면 규칙은 일치하는 폴더의 파일 인수 일치에서 중지하고 하위 폴더에서 파일 일치를 검색하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="84f51-232">If you mix a file exclusion argument with a folder exclusion argument, the rules will stop at the file argument match in the matched folder, and will not look for file matches in any subfolders.</span></span>
> <span data-ttu-id="84f51-233">예를 들어 폴더에서 규칙 인수 를 사용하여 "date"로 시작하는 모든 파일을 `c:\data\final\marked` `c:\data\review\marked` 제외할 수 `c:\data\*\marked\date*` 있습니다.</span><span class="sxs-lookup"><span data-stu-id="84f51-233">For example, you can exclude all files that start with "date" in the folders `c:\data\final\marked` and `c:\data\review\marked` by using the rule argument `c:\data\*\marked\date*`.</span></span>
> <span data-ttu-id="84f51-234">그러나 이 인수는 또는 의 하위 폴더에 있는 파일과 일치하지 `c:\data\final\marked` `c:\data\review\marked` 않습니다.</span><span class="sxs-lookup"><span data-stu-id="84f51-234">This argument, however, will not match any files in subfolders under `c:\data\final\marked` or `c:\data\review\marked`.</span></span>

<a id="review"></a>

### <a name="system-environment-variables"></a><span data-ttu-id="84f51-235">시스템 환경 변수</span><span class="sxs-lookup"><span data-stu-id="84f51-235">System environment variables</span></span>

<span data-ttu-id="84f51-236">다음 표에서는 시스템 계정 환경 변수를 나열하고 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="84f51-236">The following table lists and describes the system account environment variables.</span></span> 

| <span data-ttu-id="84f51-237">이 시스템 환경 변수...</span><span class="sxs-lookup"><span data-stu-id="84f51-237">This system environment variable...</span></span> | <span data-ttu-id="84f51-238">리디렉션</span><span class="sxs-lookup"><span data-stu-id="84f51-238">Redirects to this</span></span> |
|:--|:--|
| `%APPDATA%`| `C:\Users\UserName.DomainName\AppData\Roaming` |
| `%APPDATA%\Microsoft\Internet Explorer\Quick Launch` | `C:\Windows\System32\config\systemprofile\AppData\Roaming\Microsoft\Internet Explorer\Quick Launch` |
| `%APPDATA%\Microsoft\Windows\Start Menu` | `C:\Windows\System32\config\systemprofile\AppData\Roaming\Microsoft\Windows\Start Menu` |
| `%APPDATA%\Microsoft\Windows\Start Menu\Programs` | `C:\Windows\System32\config\systemprofile\AppData\Roaming\Microsoft\Windows\Start Menu\Programs` |
| `%LOCALAPPDATA%` | `C:\Windows\System32\config\systemprofile\AppData\Local` |
| `%ProgramData%` | `C:\ProgramData` |
| `%ProgramFiles%` | `C:\Program Files` |
| `%ProgramFiles%\Common Files` | `C:\Program Files\Common Files` |
| `%ProgramFiles%\Windows Sidebar\Gadgets` | `C:\Program Files\Windows Sidebar\Gadgets` |
| `%ProgramFiles%\Common Files` | `C:\Program Files\Common Files` |
| `%ProgramFiles(x86)%` | `C:\Program Files (x86)` |
| `%ProgramFiles(x86)%\Common Files` | `C:\Program Files (x86)\Common Files` |
| `%SystemDrive%` | `C:` |
| `%SystemDrive%\Program Files` | `C:\Program Files` |
| `%SystemDrive%\Program Files (x86)` | `C:\Program Files (x86)` |
| `%SystemDrive%\Users` | `C:\Users` |
| `%SystemDrive%\Users\Public` | `C:\Users\Public` |
| `%SystemRoot%` | `C:\Windows` |
| `%windir%` | `C:\Windows` |
| `%windir%\Fonts` | `C:\Windows\Fonts` |
| `%windir%\Resources` | `C:\Windows\Resources` |
| `%windir%\resources\0409` | `C:\Windows\resources\0409` |
| `%windir%\system32` | `C:\Windows\System32` |
| `%ALLUSERSPROFILE%` | `C:\ProgramData` |
| `%ALLUSERSPROFILE%\Application Data` | `C:\ProgramData\Application Data` |
| `%ALLUSERSPROFILE%\Documents` | `C:\ProgramData\Documents` |
| `%ALLUSERSPROFILE%\Documents\My Music\Sample Music` | `C:\ProgramData\Documents\My Music\Sample Music` |
| `%ALLUSERSPROFILE%\Documents\My Music` | `C:\ProgramData\Documents\My Music` |
| `%ALLUSERSPROFILE%\Documents\My Pictures` | `C:\ProgramData\Documents\My Pictures` |
| `%ALLUSERSPROFILE%\Documents\My Pictures\Sample Pictures` | `C:\ProgramData\Documents\My Pictures\Sample Pictures` |
| `%ALLUSERSPROFILE%\Documents\My Videos` | `C:\ProgramData\Documents\My Videos` |
| `%ALLUSERSPROFILE%\Microsoft\Windows\DeviceMetadataStore` | `C:\ProgramData\Microsoft\Windows\DeviceMetadataStore` |
| `%ALLUSERSPROFILE%\Microsoft\Windows\GameExplorer` | `C:\ProgramData\Microsoft\Windows\GameExplorer` |
| `%ALLUSERSPROFILE%\Microsoft\Windows\Ringtones` | `C:\ProgramData\Microsoft\Windows\Ringtones` |
| `%ALLUSERSPROFILE%\Microsoft\Windows\Start Menu` | `C:\ProgramData\Microsoft\Windows\Start Menu` |
| `%ALLUSERSPROFILE%\Microsoft\Windows\Start Menu\Programs` | `C:\ProgramData\Microsoft\Windows\Start Menu\Programs` |
| `%ALLUSERSPROFILE%\Microsoft\Windows\Start Menu\Programs\Administrative Tools` | `C:\ProgramData\Microsoft\Windows\Start Menu\Programs\Administrative Tools` |
| `%ALLUSERSPROFILE%\Microsoft\Windows\Start Menu\Programs\StartUp` | `C:\ProgramData\Microsoft\Windows\Start Menu\Programs\StartUp` |
| `%ALLUSERSPROFILE%\Microsoft\Windows\Templates` | `C:\ProgramData\Microsoft\Windows\Templates` |
| `%ALLUSERSPROFILE%\Start Menu` | `C:\ProgramData\Start Menu` |
| `%ALLUSERSPROFILE%\Start Menu\Programs` | <span data-ttu-id="84f51-239">C:\ProgramData\Start Menu\Programs</span><span class="sxs-lookup"><span data-stu-id="84f51-239">C:\ProgramData\Start Menu\Programs</span></span> |
| `%ALLUSERSPROFILE%\Start Menu\Programs\Administrative Tools` | `C:\ProgramData\Start Menu\Programs\Administrative Tools` | 
| `%ALLUSERSPROFILE%\Templates` | `C:\ProgramData\Templates` |
| `%LOCALAPPDATA%\Microsoft\Windows\ConnectedSearch\Templates` | `C:\Windows\System32\config\systemprofile\AppData\Local\Microsoft\Windows\ConnectedSearch\Templates` |
| `%LOCALAPPDATA%\Microsoft\Windows\History` | `C:\Windows\System32\config\systemprofile\AppData\Local\Microsoft\Windows\History` |
| `%PUBLIC%` | `C:\Users\Public` |
| `%PUBLIC%\AccountPictures` | `C:\Users\Public\AccountPictures` |
| `%PUBLIC%\Desktop` | `C:\Users\Public\Desktop` |
| `%PUBLIC%\Documents` | `C:\Users\Public\Documents` |
| `%PUBLIC%\Downloads` | `C:\Users\Public\Downloads` |
| `%PUBLIC%\Music\Sample Music` | `C:\Users\Public\Music\Sample Music` |
| `%PUBLIC%\Music\Sample Playlists` | `C:\Users\Public\Music\Sample Playlists` |
| `%PUBLIC%\Pictures\Sample Pictures` | `C:\Users\Public\Pictures\Sample Pictures` |
| `%PUBLIC%\RecordedTV.library-ms` | `C:\Users\Public\RecordedTV.library-ms` |
| `%PUBLIC%\Videos` | `C:\Users\Public\Videos` |
| `%PUBLIC%\Videos\Sample Videos` | `C:\Users\Public\Videos\Sample Videos` | 
| `%USERPROFILE%` | `C:\Windows\System32\config\systemprofile` |
| `%USERPROFILE%\AppData\Local` | `C:\Windows\System32\config\systemprofile\AppData\Local` |
| `%USERPROFILE%\AppData\LocalLow` | `C:\Windows\System32\config\systemprofile\AppData\LocalLow` |
| `%USERPROFILE%\AppData\Roaming` | `C:\Windows\System32\config\systemprofile\AppData\Roaming` |


## <a name="review-the-list-of-exclusions"></a><span data-ttu-id="84f51-240">제외 목록 검토</span><span class="sxs-lookup"><span data-stu-id="84f51-240">Review the list of exclusions</span></span>

<span data-ttu-id="84f51-241">다음 방법 중 하나를 사용하여 제외 목록의 항목을 검색할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="84f51-241">You can retrieve the items in the exclusion list using one of the following methods:</span></span>
- [<span data-ttu-id="84f51-242">Intune</span><span class="sxs-lookup"><span data-stu-id="84f51-242">Intune</span></span>](/intune/deploy-use/help-secure-windows-pcs-with-endpoint-protection-for-microsoft-intune)
- [<span data-ttu-id="84f51-243">Microsoft Endpoint Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="84f51-243">Microsoft Endpoint Configuration Manager</span></span>](/configmgr/protect/deploy-use/endpoint-antimalware-policies)
- <span data-ttu-id="84f51-244">MpCmdRun</span><span class="sxs-lookup"><span data-stu-id="84f51-244">MpCmdRun</span></span>
- <span data-ttu-id="84f51-245">PowerShell</span><span class="sxs-lookup"><span data-stu-id="84f51-245">PowerShell</span></span>
- [<span data-ttu-id="84f51-246">Windows 보안 앱</span><span class="sxs-lookup"><span data-stu-id="84f51-246">Windows Security app</span></span>](microsoft-defender-security-center-antivirus.md)

>[!IMPORTANT]
><span data-ttu-id="84f51-247">그룹 정책으로 변경된 제외 **목록은** Windows 보안 앱의 목록에 [표시됩니다.](microsoft-defender-security-center-antivirus.md)</span><span class="sxs-lookup"><span data-stu-id="84f51-247">Exclusion list changes made with Group Policy **will show** in the lists in the [Windows Security app](microsoft-defender-security-center-antivirus.md).</span></span>
>
><span data-ttu-id="84f51-248">Windows 보안 앱의 변경 **내용은 그룹** 정책 목록에 표시되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="84f51-248">Changes made in the Windows Security app **will not show** in the Group Policy lists.</span></span>

<span data-ttu-id="84f51-249">PowerShell을 사용하는 경우 다음 두 가지 방법으로 목록을 검색할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="84f51-249">If you use PowerShell, you can retrieve the list in two ways:</span></span>

- <span data-ttu-id="84f51-250">모든 Microsoft Defender 바이러스 백신 기본 설정의 상태를 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="84f51-250">Retrieve the status of all Microsoft Defender Antivirus preferences.</span></span> <span data-ttu-id="84f51-251">각 목록은 별도의 줄에 표시되지만 각 목록 내의 항목이 같은 줄로 결합됩니다.</span><span class="sxs-lookup"><span data-stu-id="84f51-251">Each list is displayed on separate lines, but the items within each list are combined into the same line.</span></span>
- <span data-ttu-id="84f51-252">모든 기본 설정의 상태를 변수에 기록하고 해당 변수를 사용하여 관심 있는 특정 목록만 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="84f51-252">Write the status of all preferences to a variable, and use that variable to only call the specific list you are interested in.</span></span> <span data-ttu-id="84f51-253">각 `Add-MpPreference` 사용은 새 줄에 기록됩니다.</span><span class="sxs-lookup"><span data-stu-id="84f51-253">Each use of `Add-MpPreference` is written to a new line.</span></span>

### <a name="validate-the-exclusion-list-by-using-mpcmdrun"></a><span data-ttu-id="84f51-254">MpCmdRun을 사용하여 제외 목록 유효성 검사</span><span class="sxs-lookup"><span data-stu-id="84f51-254">Validate the exclusion list by using MpCmdRun</span></span>

<span data-ttu-id="84f51-255">전용 명령줄 도구에서 제외를 확인하려면 mpcmdrun.exe[명령을 ](./command-line-arguments-microsoft-defender-antivirus.md?branch=v-anbic-wdav-new-mpcmdrun-options)사용합니다.</span><span class="sxs-lookup"><span data-stu-id="84f51-255">To check exclusions with the dedicated [command-line tool mpcmdrun.exe](./command-line-arguments-microsoft-defender-antivirus.md?branch=v-anbic-wdav-new-mpcmdrun-options), use the following command:</span></span>

```DOS
Start, CMD (Run as admin)
cd "%programdata%\microsoft\windows defender\platform"
cd 4.18.1812.3 (Where 4.18.1812.3 is this month's MDAV "Platform Update".)
MpCmdRun.exe -CheckExclusion -path <path>
```

>[!NOTE]
><span data-ttu-id="84f51-256">MpCmdRun에서 제외를 확인하려면 Microsoft Defender Antivirus CAMP 버전 4.18.1812.3(2018년 12월에 출시) 이상이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="84f51-256">Checking exclusions with MpCmdRun requires Microsoft Defender Antivirus CAMP version 4.18.1812.3 (released in December 2018) or later.</span></span>

### <a name="review-the-list-of-exclusions-alongside-all-other-microsoft-defender-antivirus-preferences-by-using-powershell"></a><span data-ttu-id="84f51-257">PowerShell을 사용하여 다른 모든 Microsoft Defender 바이러스 백신 기본 설정과 함께 제외 목록 검토</span><span class="sxs-lookup"><span data-stu-id="84f51-257">Review the list of exclusions alongside all other Microsoft Defender Antivirus preferences by using PowerShell</span></span>

<span data-ttu-id="84f51-258">다음 cmdlet을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="84f51-258">Use the following cmdlet:</span></span>

```PowerShell
Get-MpPreference
```

<span data-ttu-id="84f51-259">다음 예제에서는 목록에 포함된 항목이 `ExclusionExtension` 강조 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="84f51-259">In the following example, the items contained in the `ExclusionExtension` list are highlighted:</span></span>

![다른 기본 설정과 함께 Get-MpPreference 목록을 표시하는 PowerShell 출력](images/defender/wdav-powershell-get-exclusions-all.png)

<span data-ttu-id="84f51-261">자세한 내용은 [PowerShell cmdlet을](use-powershell-cmdlets-microsoft-defender-antivirus.md) 사용하여 Microsoft Defender 바이러스 백신 및 Defender cmdlet 구성 및 [실행을 참조하세요.](/powershell/module/defender/)</span><span class="sxs-lookup"><span data-stu-id="84f51-261">For more information, see [Use PowerShell cmdlets to configure and run Microsoft Defender Antivirus](use-powershell-cmdlets-microsoft-defender-antivirus.md) and [Defender cmdlets](/powershell/module/defender/).</span></span>

### <a name="retrieve-a-specific-exclusions-list-by-using-powershell"></a><span data-ttu-id="84f51-262">PowerShell을 사용하여 특정 제외 목록 검색</span><span class="sxs-lookup"><span data-stu-id="84f51-262">Retrieve a specific exclusions list by using PowerShell</span></span>

<span data-ttu-id="84f51-263">다음 코드 코드 코드를 사용하여 각 줄을 별도의 명령으로 입력합니다. **WDAVprefs를** 변수의 이름을 지정하려는 레이블로 대체합니다.</span><span class="sxs-lookup"><span data-stu-id="84f51-263">Use the following code snippet (enter each line as a separate command); replace **WDAVprefs** with whatever label you want to name the variable:</span></span>

```PowerShell
$WDAVprefs = Get-MpPreference
$WDAVprefs.ExclusionExtension
$WDAVprefs.ExclusionPath
```

<span data-ttu-id="84f51-264">다음 예제에서는 cmdlet을 사용할 때마다 목록을 새 `Add-MpPreference` 줄로 분할합니다.</span><span class="sxs-lookup"><span data-stu-id="84f51-264">In the following example, the list is split into new lines for each use of the `Add-MpPreference` cmdlet:</span></span>

![제외 목록의 항목만 표시하는 PowerShell 출력](images/defender/wdav-powershell-get-exclusions-variable.png)

<span data-ttu-id="84f51-266">자세한 내용은 [PowerShell cmdlet을](use-powershell-cmdlets-microsoft-defender-antivirus.md) 사용하여 Microsoft Defender 바이러스 백신 및 Defender cmdlet 구성 및 [실행을 참조하세요.](/powershell/module/defender/)</span><span class="sxs-lookup"><span data-stu-id="84f51-266">For more information, see [Use PowerShell cmdlets to configure and run Microsoft Defender Antivirus](use-powershell-cmdlets-microsoft-defender-antivirus.md) and [Defender cmdlets](/powershell/module/defender/).</span></span>

<a id="validate"></a>

## <a name="validate-exclusions-lists-with-the-eicar-test-file"></a><span data-ttu-id="84f51-267">EICAR 테스트 파일을 사용하여 제외 목록 유효성 검사</span><span class="sxs-lookup"><span data-stu-id="84f51-267">Validate exclusions lists with the EICAR test file</span></span>

<span data-ttu-id="84f51-268">cmdlet 또는 .NET WebClient 클래스와 함께 PowerShell을 사용하여 테스트 파일을 다운로드하여 제외 목록이 작동하고 있는지 확인할 `Invoke-WebRequest` 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="84f51-268">You can validate that your exclusion lists are working by using PowerShell with either the `Invoke-WebRequest` cmdlet or the .NET WebClient class to download a test file.</span></span>

<span data-ttu-id="84f51-269">다음 PowerShell 코드 자르기에서 test.txt제외 규칙을 준수하는 파일로 대체합니다.</span><span class="sxs-lookup"><span data-stu-id="84f51-269">In the following PowerShell snippet, replace *test.txt* with a file that conforms to your exclusion rules.</span></span> <span data-ttu-id="84f51-270">예를 들어 확장을 제외한 `.testing` 경우 를 로 `test.txt` 바) `test.testing` 합니다.</span><span class="sxs-lookup"><span data-stu-id="84f51-270">For example, if you have excluded the `.testing` extension, replace `test.txt` with `test.testing`.</span></span> <span data-ttu-id="84f51-271">경로를 테스트하는 경우 해당 경로 내에서 cmdlet을 실행해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="84f51-271">If you are testing a path, ensure you run the cmdlet within that path.</span></span>

```PowerShell
Invoke-WebRequest "http://www.eicar.org/download/eicar.com.txt" -OutFile "test.txt"
```

<span data-ttu-id="84f51-272">Microsoft Defender 바이러스 백신에서 맬웨어를 보고하면 규칙이 작동하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="84f51-272">If Microsoft Defender Antivirus reports malware, then the rule is not working.</span></span> <span data-ttu-id="84f51-273">맬웨어에 대한 보고서가 없는 경우 다운로드한 파일이 있으면 제외가 작동하고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="84f51-273">If there is no report of malware and the downloaded file exists, then the exclusion is working.</span></span> <span data-ttu-id="84f51-274">파일을 열어 [EICAR](http://www.eicar.org/86-0-Intended-use.html)테스트 파일 웹 사이트에 설명된 내용과 동일한지 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="84f51-274">You can open the file to confirm the contents are the same as what is described on the [EICAR test file website](http://www.eicar.org/86-0-Intended-use.html).</span></span>

<span data-ttu-id="84f51-275">또한 cmdlet과 같이 .NET WebClient 클래스를 호출하여 테스트 파일을 다운로드하는 다음 PowerShell 코드를 사용할 수도 있습니다.c:\test.txt파일을 유효성을 검사하는 규칙에 따라 파일로 `Invoke-WebRequest` 대체합니다. </span><span class="sxs-lookup"><span data-stu-id="84f51-275">You can also use the following PowerShell code, which calls the .NET WebClient class to download the test file - as with the `Invoke-WebRequest` cmdlet; replace *c:\test.txt* with a file that conforms to the rule you are validating:</span></span>

```PowerShell
$client = new-object System.Net.WebClient
$client.DownloadFile("http://www.eicar.org/download/eicar.com.txt","c:\test.txt")
```

<span data-ttu-id="84f51-276">인터넷에 액세스할 수 없는 경우 다음 PowerShell 명령을 사용하여 새 텍스트 파일에 EICAR 문자열을 작성하여 자체 EICAR 테스트 파일을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="84f51-276">If you do not have Internet access, you can create your own EICAR test file by writing the EICAR string to a new text file with the following PowerShell command:</span></span>

```PowerShell
[io.file]::WriteAllText("test.txt",'X5O!P%@AP[4\PZX54(P^)7CC)7}$EICAR-STANDARD-ANTIVIRUS-TEST-FILE!$H+H*')
```

<span data-ttu-id="84f51-277">또한 문자열을 빈 텍스트 파일에 복사하여 파일 이름이나 제외하려는 폴더에 저장할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="84f51-277">You can also copy the string into a blank text file and attempt to save it with the file name or in the folder you are attempting to exclude.</span></span>

## <a name="related-topics"></a><span data-ttu-id="84f51-278">관련 항목</span><span class="sxs-lookup"><span data-stu-id="84f51-278">Related topics</span></span>

- [<span data-ttu-id="84f51-279">Microsoft Defender 바이러스 백신 검사에서 제외 구성 및 유효성 검사</span><span class="sxs-lookup"><span data-stu-id="84f51-279">Configure and validate exclusions in Microsoft Defender Antivirus scans</span></span>](configure-exclusions-microsoft-defender-antivirus.md)
- [<span data-ttu-id="84f51-280">프로세스에서 연 파일에 대한 제외 구성 및 유효성 검사</span><span class="sxs-lookup"><span data-stu-id="84f51-280">Configure and validate exclusions for files opened by processes</span></span>](configure-process-opened-file-exclusions-microsoft-defender-antivirus.md)
- [<span data-ttu-id="84f51-281">Windows Server에서 Microsoft Defender 바이러스 백신 제외 구성</span><span class="sxs-lookup"><span data-stu-id="84f51-281">Configure Microsoft Defender Antivirus exclusions on Windows Server</span></span>](configure-server-exclusions-microsoft-defender-antivirus.md)
- [<span data-ttu-id="84f51-282">제외를 정의할 때 피해야 하는 일반적인 실수</span><span class="sxs-lookup"><span data-stu-id="84f51-282">Common mistakes to avoid when defining exclusions</span></span>](common-exclusion-mistakes-microsoft-defender-antivirus.md)
