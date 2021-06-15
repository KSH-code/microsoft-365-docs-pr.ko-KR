---
title: Microsoft Defender 바이러스 백신 서버에서 Windows 제외 구성
ms.reviewer: ''
manager: dansimp
description: Windows 서버에는 서버 역할에 따라 자동 제외가 포함됩니다. 사용자 지정 제외를 추가할 수도 있습니다.
keywords: 제외, 서버, 자동 제외, 자동, 사용자 지정, 검사, Microsoft Defender 바이러스 백신
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.technology: mde
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: Normal
author: denisebmsft
ms.author: deniseb
ms.topic: article
ms.custom: nextgen
ms.date: 02/10/2021
ms.openlocfilehash: 31d5c22d11a28c9604b2be3145ebd46715a6e5b3
ms.sourcegitcommit: be929f79751c0c52dfa6bd98a854432a0c63faf0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/14/2021
ms.locfileid: "52925518"
---
# <a name="configure-microsoft-defender-antivirus-exclusions-on-windows-server"></a><span data-ttu-id="f05de-105">Microsoft Defender 바이러스 백신 서버에서 Windows 제외 구성</span><span class="sxs-lookup"><span data-stu-id="f05de-105">Configure Microsoft Defender Antivirus exclusions on Windows Server</span></span>


<span data-ttu-id="f05de-106">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="f05de-106">**Applies to:**</span></span>

- [<span data-ttu-id="f05de-107">엔드포인트용 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="f05de-107">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

<span data-ttu-id="f05de-108">Microsoft Defender 바이러스 백신 및 Windows Server 2016 Windows Server 2019에서 지정한 서버 역할에 정의된 특정 제외에 자동으로 등록합니다.</span><span class="sxs-lookup"><span data-stu-id="f05de-108">Microsoft Defender Antivirus on Windows Server 2016 and Windows Server 2019 automatically enrolls you in certain exclusions, as defined by your specified server role.</span></span> <span data-ttu-id="f05de-109">이러한 제외는 Windows 보안 앱에 표시되는 표준 제외 [목록에는 나타나지 않습니다.](microsoft-defender-security-center-antivirus.md)</span><span class="sxs-lookup"><span data-stu-id="f05de-109">These exclusions do not appear in the standard exclusion lists that are shown in the [Windows Security app](microsoft-defender-security-center-antivirus.md).</span></span>

> [!NOTE]
> <span data-ttu-id="f05de-110">자동 제외는 RTP(실시간 보호) 검사에만 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="f05de-110">Automatic exclusions only apply to Real-time protection (RTP) scanning.</span></span> <span data-ttu-id="f05de-111">자동 제외는 전체/빠른 또는 수동 검사 중에 사용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="f05de-111">Automatic exclusions are not honored during a Full/Quick or On-demand scan.</span></span>

<span data-ttu-id="f05de-112">서버 역할 정의 자동 제외 외에도 사용자 지정 제외를 추가하거나 제거할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f05de-112">In addition to server role-defined automatic exclusions, you can add or remove custom exclusions.</span></span> <span data-ttu-id="f05de-113">이렇게 하여 다음 문서를 참조합니다.</span><span class="sxs-lookup"><span data-stu-id="f05de-113">To do that, refer to these articles:</span></span>
- [<span data-ttu-id="f05de-114">파일 이름, 확장명 및 폴더 위치를 기반으로 제외 구성 및 유효성 검사</span><span class="sxs-lookup"><span data-stu-id="f05de-114">Configure and validate exclusions based on file name, extension, and folder location</span></span>](configure-extension-file-exclusions-microsoft-defender-antivirus.md)
- [<span data-ttu-id="f05de-115">프로세스에서 연 파일에 대한 제외 구성 및 유효성 검사</span><span class="sxs-lookup"><span data-stu-id="f05de-115">Configure and validate exclusions for files opened by processes</span></span>](configure-process-opened-file-exclusions-microsoft-defender-antivirus.md)

## <a name="a-few-points-to-keep-in-mind"></a><span data-ttu-id="f05de-116">유의해야 할 몇 가지 지점</span><span class="sxs-lookup"><span data-stu-id="f05de-116">A few points to keep in mind</span></span>

<span data-ttu-id="f05de-117">다음과 같은 중요한 점에 유의하십시오.</span><span class="sxs-lookup"><span data-stu-id="f05de-117">Keep the following important points in mind:</span></span>

- <span data-ttu-id="f05de-118">사용자 지정 제외는 자동 제외보다 우선합니다.</span><span class="sxs-lookup"><span data-stu-id="f05de-118">Custom exclusions take precedence over automatic exclusions.</span></span>
- <span data-ttu-id="f05de-119">자동 제외는 RTP(실시간 보호) 검사에만 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="f05de-119">Automatic exclusions only apply to Real-time protection (RTP) scanning.</span></span> <span data-ttu-id="f05de-120">자동 제외는 전체/빠른 또는 수동 검사 중에 사용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="f05de-120">Automatic exclusions are not honored during a Full/Quick or On-demand scan.</span></span>
- <span data-ttu-id="f05de-121">사용자 지정 및 중복 제외는 자동 제외와 충돌하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="f05de-121">Custom and duplicate exclusions do not conflict with automatic exclusions.</span></span>
- <span data-ttu-id="f05de-122">Microsoft Defender 바이러스 백신 DISM(배포 이미지 서비스 및 관리) 도구를 사용하여 컴퓨터에 설치된 역할을 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="f05de-122">Microsoft Defender Antivirus uses the Deployment Image Servicing and Management (DISM) tools to determine which roles are installed on your computer.</span></span>

## <a name="opt-out-of-automatic-exclusions"></a><span data-ttu-id="f05de-123">자동 제외 옵트아웃</span><span class="sxs-lookup"><span data-stu-id="f05de-123">Opt out of automatic exclusions</span></span>

<span data-ttu-id="f05de-124">Windows Server 2016 및 Windows Server 2019에서 보안 인텔리전스 업데이트에서 제공된 미리 정의한 제외는 역할 또는 기능에 대한 기본 경로만 제외합니다.</span><span class="sxs-lookup"><span data-stu-id="f05de-124">In Windows Server 2016 and Windows Server 2019, the predefined exclusions delivered by Security intelligence updates only exclude the default paths for a role or feature.</span></span> <span data-ttu-id="f05de-125">사용자 지정 경로에 역할 또는 기능을 설치하거나 제외 집합을 수동으로 제어하려는 경우 보안 인텔리전스 업데이트에 제공된 자동 제외를 옵트아웃해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f05de-125">If you installed a role or feature in a custom path, or you want to manually control the set of exclusions, make sure to opt out of the automatic exclusions delivered in Security intelligence updates.</span></span> <span data-ttu-id="f05de-126">그러나 자동으로 제공되는 제외는 2019 및 2019 역할에 Windows Server 2016 최적화됩니다.</span><span class="sxs-lookup"><span data-stu-id="f05de-126">But keep in mind that the exclusions that are delivered automatically are optimized for Windows Server 2016 and 2019 roles.</span></span> <span data-ttu-id="f05de-127">제외 [권장 사항](configure-exclusions-microsoft-defender-antivirus.md#recommendations-for-defining-exclusions) 정의하기 전에 제외를 정의하는 방법을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="f05de-127">See [Recommendations for defining exclusions](configure-exclusions-microsoft-defender-antivirus.md#recommendations-for-defining-exclusions) before defining your exclusion lists.</span></span>

> [!WARNING]
> <span data-ttu-id="f05de-128">자동 제외를 옵트아웃하면 성능이 밝아지거나 데이터가 손상될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f05de-128">Opting out of automatic exclusions may adversely impact performance, or result in data corruption.</span></span> <span data-ttu-id="f05de-129">자동으로 전달되는 제외는 서버 2019 및 Windows Server 2016 Windows 최적화됩니다.</span><span class="sxs-lookup"><span data-stu-id="f05de-129">The exclusions that are delivered automatically are optimized for Windows Server 2016 and Windows Server 2019 roles.</span></span>

<span data-ttu-id="f05de-130">미리 정의한 제외는 기본 경로만 제외하기 때문에 NTDS 및 SYSVOL을 원래 경로와 다른 다른 드라이브 또는 경로로 이동하는 경우 여기에서 정보를 사용하여 제외를 수동으로 추가해야 [합니다.](configure-extension-file-exclusions-microsoft-defender-antivirus.md#configure-the-list-of-exclusions-based-on-folder-name-or-file-extension)</span><span class="sxs-lookup"><span data-stu-id="f05de-130">Because predefined exclusions only exclude **default paths**, if you move NTDS and SYSVOL to another drive or path that is *different from the original path*, you must add exclusions manually using the information [here](configure-extension-file-exclusions-microsoft-defender-antivirus.md#configure-the-list-of-exclusions-based-on-folder-name-or-file-extension) .</span></span>

<span data-ttu-id="f05de-131">그룹 정책, PowerShell cmdlet 및 WMI를 사용하여 자동 제외 목록을 사용하지 않도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f05de-131">You can disable the automatic exclusion lists with Group Policy, PowerShell cmdlets, and WMI.</span></span>

### <a name="use-group-policy-to-disable-the-auto-exclusions-list-on-windows-server-2016-and-windows-server-2019"></a><span data-ttu-id="f05de-132">그룹 정책을 사용하여 Windows Server 2016 Server 2019에서 Windows 사용하지 않도록 설정</span><span class="sxs-lookup"><span data-stu-id="f05de-132">Use Group Policy to disable the auto-exclusions list on Windows Server 2016 and Windows Server 2019</span></span>

1. <span data-ttu-id="f05de-133">그룹 정책 관리 컴퓨터에서 [그룹 정책 관리 콘솔](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc725752(v=ws.11))을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="f05de-133">On your Group Policy management computer, open the [Group Policy Management Console](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc725752(v=ws.11)).</span></span> <span data-ttu-id="f05de-134">구성할 그룹 정책 개체를 마우스 오른쪽 단추로 클릭한 다음 편집 을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="f05de-134">Right-click the Group Policy Object you want to configure, and then click **Edit**.</span></span>
2. <span data-ttu-id="f05de-135">그룹 정책 **관리 편집기에서** 컴퓨터 **구성으로 이동한** 다음 관리 템플릿 **을 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="f05de-135">In the **Group Policy Management Editor** go to **Computer configuration**, and then click **Administrative templates**.</span></span>
3. <span data-ttu-id="f05de-136">트리를 확장하여 **Windows 구성 요소 Microsoft Defender 바이러스 백신**  >    >  **확장합니다.**</span><span class="sxs-lookup"><span data-stu-id="f05de-136">Expand the tree to **Windows components** > **Microsoft Defender Antivirus** > **Exclusions**.</span></span>
4. <span data-ttu-id="f05de-137">자동 **제외** 해제를 두 번 클릭하고 옵션을 사용으로 **설정합니다.**</span><span class="sxs-lookup"><span data-stu-id="f05de-137">Double-click **Turn off Auto Exclusions**, and set the option to **Enabled**.</span></span> <span data-ttu-id="f05de-138">그런 다음 **확인** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="f05de-138">Then click **OK**.</span></span> 

### <a name="use-powershell-cmdlets-to-disable-the-auto-exclusions-list-on-windows-server-2016-and-2019"></a><span data-ttu-id="f05de-139">PowerShell cmdlet을 사용하여 Windows Server 2016 및 2019에서 자동 제외 목록을 사용하지 않도록 설정</span><span class="sxs-lookup"><span data-stu-id="f05de-139">Use PowerShell cmdlets to disable the auto-exclusions list on Windows Server 2016 and 2019</span></span>

<span data-ttu-id="f05de-140">다음 cmdlet을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="f05de-140">Use the following cmdlets:</span></span>

```PowerShell
Set-MpPreference -DisableAutoExclusions $true
```

<span data-ttu-id="f05de-141">자세한 내용은 다음 리소스를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="f05de-141">To learn more, see the following resources:</span></span>

- <span data-ttu-id="f05de-142">[PowerShell cmdlet을 사용하여](use-powershell-cmdlets-microsoft-defender-antivirus.md)를 구성하고 Microsoft Defender 바이러스 백신.</span><span class="sxs-lookup"><span data-stu-id="f05de-142">[Use PowerShell cmdlets to configure and run Microsoft Defender Antivirus](use-powershell-cmdlets-microsoft-defender-antivirus.md).</span></span>
- <span data-ttu-id="f05de-143">[에서 PowerShell을 Microsoft Defender 바이러스 백신.](/powershell/module/defender/)</span><span class="sxs-lookup"><span data-stu-id="f05de-143">[Use PowerShell with Microsoft Defender Antivirus](/powershell/module/defender/).</span></span>

### <a name="use-windows-management-instruction-wmi-to-disable-the-auto-exclusions-list-on-windows-server-2016-and-windows-server-2019"></a><span data-ttu-id="f05de-144">WMI(Windows Management Instruction)를 사용하여 Windows Server 2016 Server 2019에서 자동 Windows 사용하지 않도록 설정</span><span class="sxs-lookup"><span data-stu-id="f05de-144">Use Windows Management Instruction (WMI) to disable the auto-exclusions list on Windows Server 2016 and Windows Server 2019</span></span>

<span data-ttu-id="f05de-145">다음 속성에 MSFT_MpPreference [클래스의](/previous-versions/windows/desktop/defender/msft-mppreference) **Set** 메서드를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="f05de-145">Use the **Set** method of the [MSFT_MpPreference](/previous-versions/windows/desktop/defender/msft-mppreference) class for the following properties:</span></span>

```WMI
DisableAutoExclusions
```

<span data-ttu-id="f05de-146">자세한 정보 및 허용되는 매개 변수는 다음을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="f05de-146">See the following for more information and allowed parameters:</span></span>
- [<span data-ttu-id="f05de-147">Windows Defender WMIv2 API</span><span class="sxs-lookup"><span data-stu-id="f05de-147">Windows Defender WMIv2 APIs</span></span>](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)

## <a name="list-of-automatic-exclusions"></a><span data-ttu-id="f05de-148">자동 제외 목록</span><span class="sxs-lookup"><span data-stu-id="f05de-148">List of automatic exclusions</span></span>

<span data-ttu-id="f05de-149">다음 섹션에는 자동 제외 파일 경로 및 파일 형식과 함께 제공된 제외가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f05de-149">The following sections contain the exclusions that are delivered with automatic exclusions file paths and file types.</span></span>

### <a name="default-exclusions-for-all-roles"></a><span data-ttu-id="f05de-150">모든 역할에 대한 기본 제외</span><span class="sxs-lookup"><span data-stu-id="f05de-150">Default exclusions for all roles</span></span>

<span data-ttu-id="f05de-151">이 섹션에는 모든 역할 및 2019 역할에 Windows Server 2016 제외가 나열되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f05de-151">This section lists the default exclusions for all Windows Server 2016 and 2019 roles.</span></span>

> [!NOTE]
> <span data-ttu-id="f05de-152">기본 위치는 이 문서에 나와 있는 위치와 다를 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f05de-152">The default locations could be different than what's listed in this article.</span></span>

#### <a name="windows-tempedb-files"></a><span data-ttu-id="f05de-153">Windows "temp.edb" 파일</span><span class="sxs-lookup"><span data-stu-id="f05de-153">Windows "temp.edb" files</span></span>

- `%windir%\SoftwareDistribution\Datastore\*\tmp.edb`
- `%ProgramData%\Microsoft\Search\Data\Applications\Windows\*\*.log`

#### <a name="windows-update-files-or-automatic-update-files"></a><span data-ttu-id="f05de-154">Windows 파일 업데이트 또는 자동 업데이트 파일</span><span class="sxs-lookup"><span data-stu-id="f05de-154">Windows Update files or Automatic Update files</span></span>

- `%windir%\SoftwareDistribution\Datastore\*\Datastore.edb`
- `%windir%\SoftwareDistribution\Datastore\*\edb.chk`
- `%windir%\SoftwareDistribution\Datastore\*\edb\*.log`
- `%windir%\SoftwareDistribution\Datastore\*\Edb\*.jrs`
- `%windir%\SoftwareDistribution\Datastore\*\Res\*.log`

#### <a name="windows-security-files"></a><span data-ttu-id="f05de-155">Windows 보안 파일</span><span class="sxs-lookup"><span data-stu-id="f05de-155">Windows Security files</span></span>

- `%windir%\Security\database\*.chk`
- `%windir%\Security\database\*.edb`
- `%windir%\Security\database\*.jrs`
- `%windir%\Security\database\*.log`
- `%windir%\Security\database\*.sdb`

#### <a name="group-policy-files"></a><span data-ttu-id="f05de-156">그룹 정책 파일</span><span class="sxs-lookup"><span data-stu-id="f05de-156">Group Policy files</span></span>

- `%allusersprofile%\NTUser.pol`
- `%SystemRoot%\System32\GroupPolicy\Machine\registry.pol`
- `%SystemRoot%\System32\GroupPolicy\User\registry.pol`

#### <a name="wins-files"></a><span data-ttu-id="f05de-157">WINS 파일</span><span class="sxs-lookup"><span data-stu-id="f05de-157">WINS files</span></span>

- `%systemroot%\System32\Wins\*\*.chk`
- `%systemroot%\System32\Wins\*\*.log`
- `%systemroot%\System32\Wins\*\*.mdb`
- `%systemroot%\System32\LogFiles\`
- `%systemroot%\SysWow64\LogFiles\`

#### <a name="file-replication-service-frs-exclusions"></a><span data-ttu-id="f05de-158">FRS(파일 복제 서비스) 제외</span><span class="sxs-lookup"><span data-stu-id="f05de-158">File Replication Service (FRS) exclusions</span></span>

- <span data-ttu-id="f05de-159">FRS(파일 복제 서비스) 작업 폴더의 파일</span><span class="sxs-lookup"><span data-stu-id="f05de-159">Files in the File Replication Service (FRS) working folder.</span></span> <span data-ttu-id="f05de-160">FRS 작업 폴더가 레지스트리 키에 지정됩니다. `HKEY_LOCAL_MACHINE\System\CurrentControlSet\Services\NtFrs\Parameters\Working Directory`</span><span class="sxs-lookup"><span data-stu-id="f05de-160">The FRS working folder is specified in the registry key `HKEY_LOCAL_MACHINE\System\CurrentControlSet\Services\NtFrs\Parameters\Working Directory`</span></span>

  - `%windir%\Ntfrs\jet\sys\*\edb.chk`
  - `%windir%\Ntfrs\jet\*\Ntfrs.jdb`
  - `%windir%\Ntfrs\jet\log\*\*.log`

- <span data-ttu-id="f05de-161">FRS 데이터베이스 로그 파일입니다.</span><span class="sxs-lookup"><span data-stu-id="f05de-161">FRS Database log files.</span></span> <span data-ttu-id="f05de-162">FRS 데이터베이스 로그 파일 폴더가 레지스트리 키에 지정됩니다. `HKEY_LOCAL_MACHINE\System\CurrentControlSet\Services\Ntfrs\Parameters\DB Log File Directory`</span><span class="sxs-lookup"><span data-stu-id="f05de-162">The FRS Database log file folder is specified in the registry key `HKEY_LOCAL_MACHINE\System\CurrentControlSet\Services\Ntfrs\Parameters\DB Log File Directory`</span></span>

  - `%windir%\Ntfrs\*\Edb\*.log`

- <span data-ttu-id="f05de-163">FRS 준비 폴더입니다.</span><span class="sxs-lookup"><span data-stu-id="f05de-163">The FRS staging folder.</span></span> <span data-ttu-id="f05de-164">준비 폴더는 레지스트리 키에 지정됩니다. `HKEY_LOCAL_MACHINE\System\CurrentControlSet\Services\NtFrs\Parameters\Replica Sets\GUID\Replica Set Stage`</span><span class="sxs-lookup"><span data-stu-id="f05de-164">The staging folder is specified in the registry key `HKEY_LOCAL_MACHINE\System\CurrentControlSet\Services\NtFrs\Parameters\Replica Sets\GUID\Replica Set Stage`</span></span>

  - `%systemroot%\Sysvol\*\Ntfrs_cmp*\`

- <span data-ttu-id="f05de-165">FRS 사전 설치 폴더입니다.</span><span class="sxs-lookup"><span data-stu-id="f05de-165">The FRS preinstall folder.</span></span> <span data-ttu-id="f05de-166">이 폴더는 폴더에 의해 지정됩니다. `Replica_root\DO_NOT_REMOVE_NtFrs_PreInstall_Directory`</span><span class="sxs-lookup"><span data-stu-id="f05de-166">This folder is specified by the folder `Replica_root\DO_NOT_REMOVE_NtFrs_PreInstall_Directory`</span></span>

  - `%systemroot%\SYSVOL\domain\DO_NOT_REMOVE_NtFrs_PreInstall_Directory\*\Ntfrs*\`

- <span data-ttu-id="f05de-167">DFSR(분산 파일 시스템 복제) 데이터베이스 및 작업 폴더</span><span class="sxs-lookup"><span data-stu-id="f05de-167">The Distributed File System Replication (DFSR) database and working folders.</span></span> <span data-ttu-id="f05de-168">이러한 폴더는 레지스트리 키로 지정됩니다. `HKEY_LOCAL_MACHINE\System\CurrentControlSet\Services\DFSR\Parameters\Replication Groups\GUID\Replica Set Configuration File`</span><span class="sxs-lookup"><span data-stu-id="f05de-168">These folders are specified by the registry key `HKEY_LOCAL_MACHINE\System\CurrentControlSet\Services\DFSR\Parameters\Replication Groups\GUID\Replica Set Configuration File`</span></span>

  > [!NOTE]
  > <span data-ttu-id="f05de-169">사용자 지정 위치에 대한 자세한 내용은 자동 제외 옵트아웃을 [참조하세요.](#opt-out-of-automatic-exclusions)</span><span class="sxs-lookup"><span data-stu-id="f05de-169">For custom locations, see [Opt out of automatic exclusions](#opt-out-of-automatic-exclusions).</span></span>

  - `%systemdrive%\System Volume Information\DFSR\$db_normal$`
  - `%systemdrive%\System Volume Information\DFSR\FileIDTable_*`
  - `%systemdrive%\System Volume Information\DFSR\SimilarityTable_*`
  - `%systemdrive%\System Volume Information\DFSR\*.XML`
  - `%systemdrive%\System Volume Information\DFSR\$db_dirty$`
  - `%systemdrive%\System Volume Information\DFSR\$db_clean$`
  - `%systemdrive%\System Volume Information\DFSR\$db_lostl$`
  - `%systemdrive%\System Volume Information\DFSR\Dfsr.db`
  - `%systemdrive%\System Volume Information\DFSR\*.frx`
  - `%systemdrive%\System Volume Information\DFSR\*.log`
  - `%systemdrive%\System Volume Information\DFSR\Fsr*.jrs`
  - `%systemdrive%\System Volume Information\DFSR\Tmp.edb`

#### <a name="process-exclusions"></a><span data-ttu-id="f05de-170">프로세스 제외</span><span class="sxs-lookup"><span data-stu-id="f05de-170">Process exclusions</span></span>

- `%systemroot%\System32\dfsr.exe`
- `%systemroot%\System32\dfsrs.exe`

#### <a name="hyper-v-exclusions"></a><span data-ttu-id="f05de-171">Hyper-V 제외</span><span class="sxs-lookup"><span data-stu-id="f05de-171">Hyper-V exclusions</span></span>

<span data-ttu-id="f05de-172">다음 표에는 Hyper-V 설치할 때 자동으로 배달되는 파일 형식 제외, 폴더 제외 및 프로세스 제외가 나열되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f05de-172">The following table lists the file type exclusions, folder exclusions, and process exclusions that are delivered automatically when you install the Hyper-V role.</span></span>

|<span data-ttu-id="f05de-173">파일 형식 제외</span><span class="sxs-lookup"><span data-stu-id="f05de-173">File type exclusions</span></span> |<span data-ttu-id="f05de-174">폴더 제외</span><span class="sxs-lookup"><span data-stu-id="f05de-174">Folder exclusions</span></span>  | <span data-ttu-id="f05de-175">프로세스 제외</span><span class="sxs-lookup"><span data-stu-id="f05de-175">Process exclusions</span></span> |
|:--|:--|:--|
| `*.vhd` <br/> `*.vhdx` <br/> `*.avhd` <br/> `*.avhdx` <br/> `*.vsv` <br/> `*.iso` <br/> `*.rct` <br/> `*.vmcx` <br/> `*.vmrs` | `%ProgramData%\Microsoft\Windows\Hyper-V` <br/> `%ProgramFiles%\Hyper-V` <br/> `%SystemDrive%\ProgramData\Microsoft\Windows\Hyper-V\Snapshots` <br/> `%Public%\Documents\Hyper-V\Virtual Hard Disks` | `%systemroot%\System32\Vmms.exe` <br/> `%systemroot%\System32\Vmwp.exe` |

#### <a name="sysvol-files"></a><span data-ttu-id="f05de-176">SYSVOL 파일</span><span class="sxs-lookup"><span data-stu-id="f05de-176">SYSVOL files</span></span>

- `%systemroot%\Sysvol\Domain\*.adm`
- `%systemroot%\Sysvol\Domain\*.admx`
- `%systemroot%\Sysvol\Domain\*.adml`
- `%systemroot%\Sysvol\Domain\Registry.pol`
- `%systemroot%\Sysvol\Domain\*.aas`
- `%systemroot%\Sysvol\Domain\*.inf`
- `%systemroot%\Sysvol\Domain\*Scripts.ini`
- `%systemroot%\Sysvol\Domain\*.ins`
- `%systemroot%\Sysvol\Domain\Oscfilter.ini`


### <a name="active-directory-exclusions"></a><span data-ttu-id="f05de-177">Active Directory 제외</span><span class="sxs-lookup"><span data-stu-id="f05de-177">Active Directory exclusions</span></span>

<span data-ttu-id="f05de-178">이 섹션에는 Active Directory 도메인 서비스를 설치할 때 자동으로 배달되는 제외가 나열되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f05de-178">This section lists the exclusions that are delivered automatically when you install Active Directory Domain Services.</span></span>

#### <a name="ntds-database-files"></a><span data-ttu-id="f05de-179">NTDS 데이터베이스 파일</span><span class="sxs-lookup"><span data-stu-id="f05de-179">NTDS database files</span></span>

<span data-ttu-id="f05de-180">데이터베이스 파일이 레지스트리 키에 지정됩니다. `HKEY_LOCAL_MACHINE\System\CurrentControlSet\Services\NTDS\Parameters\DSA Database File`</span><span class="sxs-lookup"><span data-stu-id="f05de-180">The database files are specified in the registry key `HKEY_LOCAL_MACHINE\System\CurrentControlSet\Services\NTDS\Parameters\DSA Database File`</span></span>

- `%windir%\Ntds\ntds.dit`
- `%windir%\Ntds\ntds.pat`

#### <a name="the-ad-ds-transaction-log-files"></a><span data-ttu-id="f05de-181">AD DS 트랜잭션 로그 파일</span><span class="sxs-lookup"><span data-stu-id="f05de-181">The AD DS transaction log files</span></span>

<span data-ttu-id="f05de-182">트랜잭션 로그 파일이 레지스트리 키에 지정됩니다. `HKEY_LOCAL_MACHINE\System\CurrentControlSet\Services\NTDS\Parameters\Database Log Files Path`</span><span class="sxs-lookup"><span data-stu-id="f05de-182">The transaction log files are specified in the registry key `HKEY_LOCAL_MACHINE\System\CurrentControlSet\Services\NTDS\Parameters\Database Log Files Path`</span></span>

- `%windir%\Ntds\EDB*.log`
- `%windir%\Ntds\Res*.log`
- `%windir%\Ntds\Edb*.jrs`
- `%windir%\Ntds\Ntds*.pat`
- `%windir%\Ntds\TEMP.edb`

#### <a name="the-ntds-working-folder"></a><span data-ttu-id="f05de-183">NTDS 작업 폴더</span><span class="sxs-lookup"><span data-stu-id="f05de-183">The NTDS working folder</span></span>

<span data-ttu-id="f05de-184">이 폴더는 레지스트리 키에 지정됩니다. `HKEY_LOCAL_MACHINE\System\CurrentControlSet\Services\NTDS\Parameters\DSA Working Directory`</span><span class="sxs-lookup"><span data-stu-id="f05de-184">This folder is specified in the registry key `HKEY_LOCAL_MACHINE\System\CurrentControlSet\Services\NTDS\Parameters\DSA Working Directory`</span></span>

- `%windir%\Ntds\Temp.edb`
- `%windir%\Ntds\Edb.chk`

#### <a name="process-exclusions-for-ad-ds-and-ad-ds-related-support-files"></a><span data-ttu-id="f05de-185">AD DS 및 AD DS 관련 지원 파일에 대한 프로세스 제외</span><span class="sxs-lookup"><span data-stu-id="f05de-185">Process exclusions for AD DS and AD DS-related support files</span></span>

- `%systemroot%\System32\ntfrs.exe`
- `%systemroot%\System32\lsass.exe`

### <a name="dhcp-server-exclusions"></a><span data-ttu-id="f05de-186">DHCP 서버 제외</span><span class="sxs-lookup"><span data-stu-id="f05de-186">DHCP Server exclusions</span></span>

<span data-ttu-id="f05de-187">이 섹션에는 DHCP 서버 역할을 설치할 때 자동으로 배달되는 제외가 나열되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f05de-187">This section lists the exclusions that are delivered automatically when you install the DHCP Server role.</span></span> <span data-ttu-id="f05de-188">DHCP 서버 파일 위치는 레지스트리 키의 *DatabasePath,* *DhcpLogFilePath* 및 *BackupDatabasePath* 매개 변수에 의해 지정됩니다. `HKEY_LOCAL_MACHINE\System\CurrentControlSet\Services\DHCPServer\Parameters`</span><span class="sxs-lookup"><span data-stu-id="f05de-188">The DHCP Server file locations are specified by the *DatabasePath*, *DhcpLogFilePath*, and *BackupDatabasePath* parameters in the registry key `HKEY_LOCAL_MACHINE\System\CurrentControlSet\Services\DHCPServer\Parameters`</span></span>

- `%systemroot%\System32\DHCP\*\*.mdb`
- `%systemroot%\System32\DHCP\*\*.pat`
- `%systemroot%\System32\DHCP\*\*.log`
- `%systemroot%\System32\DHCP\*\*.chk`
- `%systemroot%\System32\DHCP\*\*.edb`

### <a name="dns-server-exclusions"></a><span data-ttu-id="f05de-189">DNS 서버 제외</span><span class="sxs-lookup"><span data-stu-id="f05de-189">DNS Server exclusions</span></span>

<span data-ttu-id="f05de-190">이 섹션에는 DNS 서버 역할을 설치할 때 자동으로 배달되는 파일 및 폴더 제외 및 프로세스 제외가 나열되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f05de-190">This section lists the file and folder exclusions and the process exclusions that are delivered automatically when you install the DNS Server role.</span></span>

#### <a name="file-and-folder-exclusions-for-the-dns-server-role"></a><span data-ttu-id="f05de-191">DNS 서버 역할에 대한 파일 및 폴더 제외</span><span class="sxs-lookup"><span data-stu-id="f05de-191">File and folder exclusions for the DNS Server role</span></span>

- `%systemroot%\System32\Dns\*\*.log`
- `%systemroot%\System32\Dns\*\*.dns`
- `%systemroot%\System32\Dns\*\*.scc`
- `%systemroot%\System32\Dns\*\BOOT`

#### <a name="process-exclusions-for-the-dns-server-role"></a><span data-ttu-id="f05de-192">DNS 서버 역할에 대한 프로세스 제외</span><span class="sxs-lookup"><span data-stu-id="f05de-192">Process exclusions for the DNS Server role</span></span>

- `%systemroot%\System32\dns.exe`

### <a name="file-and-storage-services-exclusions"></a><span data-ttu-id="f05de-193">파일 및 Storage 서비스 제외</span><span class="sxs-lookup"><span data-stu-id="f05de-193">File and Storage Services exclusions</span></span>

<span data-ttu-id="f05de-194">이 섹션에는 파일 및 Storage 서비스 역할을 설치할 때 자동으로 배달되는 파일 및 폴더 제외가 나열되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f05de-194">This section lists the file and folder exclusions that are delivered automatically when you install the File and Storage Services role.</span></span> <span data-ttu-id="f05de-195">아래에 나열된 제외에는 클러스터링 역할에 대한 제외가 포함되어 있지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="f05de-195">The exclusions listed below do not include exclusions for the Clustering role.</span></span>

- `%SystemDrive%\ClusterStorage`
- `%clusterserviceaccount%\Local Settings\Temp`
- `%SystemDrive%\mscs`

### <a name="print-server-exclusions"></a><span data-ttu-id="f05de-196">인쇄 서버 제외</span><span class="sxs-lookup"><span data-stu-id="f05de-196">Print Server exclusions</span></span>

<span data-ttu-id="f05de-197">이 섹션에는 인쇄 서버 역할을 설치할 때 자동으로 배달되는 파일 형식 제외, 폴더 제외 및 프로세스 제외가 나열되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f05de-197">This section lists the file type exclusions, folder exclusions, and the process exclusions that are delivered automatically when you install the Print Server role.</span></span>

#### <a name="file-type-exclusions"></a><span data-ttu-id="f05de-198">파일 형식 제외</span><span class="sxs-lookup"><span data-stu-id="f05de-198">File type exclusions</span></span>

- `*.shd`
- `*.spl`

#### <a name="folder-exclusions"></a><span data-ttu-id="f05de-199">폴더 제외</span><span class="sxs-lookup"><span data-stu-id="f05de-199">Folder exclusions</span></span>

<span data-ttu-id="f05de-200">이 폴더는 레지스트리 키에 지정됩니다. `HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\Print\Printers\DefaultSpoolDirectory`</span><span class="sxs-lookup"><span data-stu-id="f05de-200">This folder is specified in the registry key `HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\Print\Printers\DefaultSpoolDirectory`</span></span>

- `%system32%\spool\printers\*`

#### <a name="process-exclusions"></a><span data-ttu-id="f05de-201">프로세스 제외</span><span class="sxs-lookup"><span data-stu-id="f05de-201">Process exclusions</span></span>

- `spoolsv.exe`

### <a name="web-server-exclusions"></a><span data-ttu-id="f05de-202">웹 서버 제외</span><span class="sxs-lookup"><span data-stu-id="f05de-202">Web Server exclusions</span></span>

<span data-ttu-id="f05de-203">이 섹션에는 웹 서버 역할을 설치할 때 자동으로 배달되는 폴더 제외 및 프로세스 제외가 나열되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f05de-203">This section lists the folder exclusions and the process exclusions that are delivered automatically when you install the Web Server role.</span></span>

#### <a name="folder-exclusions"></a><span data-ttu-id="f05de-204">폴더 제외</span><span class="sxs-lookup"><span data-stu-id="f05de-204">Folder exclusions</span></span>

- `%SystemRoot%\IIS Temporary Compressed Files`
- `%SystemDrive%\inetpub\temp\IIS Temporary Compressed Files`
- `%SystemDrive%\inetpub\temp\ASP Compiled Templates`
- `%systemDrive%\inetpub\logs`
- `%systemDrive%\inetpub\wwwroot`

#### <a name="process-exclusions"></a><span data-ttu-id="f05de-205">프로세스 제외</span><span class="sxs-lookup"><span data-stu-id="f05de-205">Process exclusions</span></span>

- `%SystemRoot%\system32\inetsrv\w3wp.exe`
- `%SystemRoot%\SysWOW64\inetsrv\w3wp.exe`
- `%SystemDrive%\PHP5433\php-cgi.exe`

#### <a name="turning-off-scanning-of-files-in-the-sysvolsysvol-folder-or-the-sysvol_dfsrsysvol-folder"></a><span data-ttu-id="f05de-206">Sysvol\Sysvol 폴더 또는 SYSVOL_DFSR\Sysvol 폴더에서 파일 검색 끄기</span><span class="sxs-lookup"><span data-stu-id="f05de-206">Turning off scanning of files in the Sysvol\Sysvol folder or the SYSVOL_DFSR\Sysvol folder</span></span>

<span data-ttu-id="f05de-207">또는 폴더의 현재 위치와 모든 하위 폴더는 복제 데이터베이스 집합 루트의 파일 시스템 재분석 `Sysvol\Sysvol` `SYSVOL_DFSR\Sysvol` 대상입니다.</span><span class="sxs-lookup"><span data-stu-id="f05de-207">The current location of the `Sysvol\Sysvol` or `SYSVOL_DFSR\Sysvol` folder and all the subfolders is the file system reparse target of the replica set root.</span></span> <span data-ttu-id="f05de-208">및 폴더는 기본적으로 다음 `Sysvol\Sysvol` `SYSVOL_DFSR\Sysvol` 위치를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="f05de-208">The `Sysvol\Sysvol` and `SYSVOL_DFSR\Sysvol` folders use the following locations by default:</span></span>

- `%systemroot%\Sysvol\Domain`
- `%systemroot%\Sysvol_DFSR\Domain`

<span data-ttu-id="f05de-209">현재 활성 상태인 경로는 NETLOGON 공유에서 참조하며 다음 하위 키의 `SYSVOL` SysVol 값 이름으로 결정될 수 있습니다. `HKEY_LOCAL_MACHINE\SYSTEM\ControlSet001\Services\Netlogon\Parameters`</span><span class="sxs-lookup"><span data-stu-id="f05de-209">The path to the currently active `SYSVOL` is referenced by the NETLOGON share and can be determined by the SysVol value name in the following subkey: `HKEY_LOCAL_MACHINE\SYSTEM\ControlSet001\Services\Netlogon\Parameters`</span></span>

<span data-ttu-id="f05de-210">이 폴더와 모든 하위 폴더에서 다음 파일을 제외합니다.</span><span class="sxs-lookup"><span data-stu-id="f05de-210">Exclude the following files from this folder and all its subfolders:</span></span>

- `*.adm`
- `*.admx`
- `*.adml`
- `Registry.pol`
- `Registry.tmp`
- `*.aas`
- `*.inf`
- `Scripts.ini`
- `*.ins`
- `Oscfilter.ini`

### <a name="windows-server-update-services-exclusions"></a><span data-ttu-id="f05de-211">Windows Server Update Services 제외</span><span class="sxs-lookup"><span data-stu-id="f05de-211">Windows Server Update Services exclusions</span></span>

<span data-ttu-id="f05de-212">이 섹션에서는 WSUS(Windows Server Update Services) 역할을 설치할 때 자동으로 배달되는 폴더 제외를 나열합니다.</span><span class="sxs-lookup"><span data-stu-id="f05de-212">This section lists the folder exclusions that are delivered automatically when you install the Windows Server Update Services (WSUS) role.</span></span> <span data-ttu-id="f05de-213">WSUS 폴더는 레지스트리 키에 지정됩니다. `HKEY_LOCAL_MACHINE\Software\Microsoft\Update Services\Server\Setup`</span><span class="sxs-lookup"><span data-stu-id="f05de-213">The WSUS folder is specified in the registry key `HKEY_LOCAL_MACHINE\Software\Microsoft\Update Services\Server\Setup`</span></span>

- `%systemroot%\WSUS\WSUSContent`
- `%systemroot%\WSUS\UpdateServicesDBFiles`
- `%systemroot%\SoftwareDistribution\Datastore`
- `%systemroot%\SoftwareDistribution\Download`

## <a name="see-also"></a><span data-ttu-id="f05de-214">참고 항목</span><span class="sxs-lookup"><span data-stu-id="f05de-214">See also</span></span>

- [<span data-ttu-id="f05de-215">검사에 대한 제외 Microsoft Defender 바이러스 백신 유효성 검사</span><span class="sxs-lookup"><span data-stu-id="f05de-215">Configure and validate exclusions for Microsoft Defender Antivirus scans</span></span>](configure-exclusions-microsoft-defender-antivirus.md)
- [<span data-ttu-id="f05de-216">파일 이름, 확장명 및 폴더 위치를 기반으로 제외 구성 및 유효성 검사</span><span class="sxs-lookup"><span data-stu-id="f05de-216">Configure and validate exclusions based on file name, extension, and folder location</span></span>](configure-extension-file-exclusions-microsoft-defender-antivirus.md)
- [<span data-ttu-id="f05de-217">프로세스에서 연 파일에 대한 제외 구성 및 유효성 검사</span><span class="sxs-lookup"><span data-stu-id="f05de-217">Configure and validate exclusions for files opened by processes</span></span>](configure-process-opened-file-exclusions-microsoft-defender-antivirus.md)
- [<span data-ttu-id="f05de-218">제외 정의 시 피해야 하는 일반적인 실수</span><span class="sxs-lookup"><span data-stu-id="f05de-218">Common mistakes to avoid when defining exclusions</span></span>](common-exclusion-mistakes-microsoft-defender-antivirus.md)
- [<span data-ttu-id="f05de-219">사용자 지정, 시작 및 재구성 결과 Microsoft Defender 바이러스 백신 검토</span><span class="sxs-lookup"><span data-stu-id="f05de-219">Customize, initiate, and review the results of Microsoft Defender Antivirus scans and remediation</span></span>](customize-run-review-remediate-scans-microsoft-defender-antivirus.md)
- [<span data-ttu-id="f05de-220">Windows 10의 Microsoft Defender 바이러스 백신</span><span class="sxs-lookup"><span data-stu-id="f05de-220">Microsoft Defender Antivirus in Windows 10</span></span>](microsoft-defender-antivirus-in-windows-10.md)
