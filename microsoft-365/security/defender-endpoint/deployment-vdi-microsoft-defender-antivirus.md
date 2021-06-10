---
title: Microsoft Defender 바이러스 백신 가상 데스크톱 인프라 배포 가이드
description: 보호와 성능 Microsoft Defender 바이러스 백신 균형을 유지하기 위해 가상 데스크톱 환경에 배포하는 방법을 학습합니다.
keywords: vdi, hyper-v, vm, 가상 컴퓨터, windows defender, 바이러스 백신, av, 가상 데스크톱, rds, 원격 데스크톱
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
localization_priority: Normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 12/28/2020
ms.reviewer: jesquive
manager: dansimp
ms.technology: mde
ms.topic: article
ms.openlocfilehash: 4ecd14e055646804d81e22da7c192988cf1e6f6f
ms.sourcegitcommit: 51b316c23e070ab402a687f927e8fa01cb719c74
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/07/2021
ms.locfileid: "52275255"
---
# <a name="deployment-guide-for-microsoft-defender-antivirus-in-a-virtual-desktop-infrastructure-vdi-environment"></a><span data-ttu-id="a8752-104">VDI(가상 데스크톱 인프라) 환경에서 Microsoft Defender 바이러스 백신의 배포 가이드</span><span class="sxs-lookup"><span data-stu-id="a8752-104">Deployment guide for Microsoft Defender Antivirus in a virtual desktop infrastructure (VDI) environment</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="a8752-105">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="a8752-105">**Applies to:**</span></span>

- [<span data-ttu-id="a8752-106">엔드포인트용 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="a8752-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

<span data-ttu-id="a8752-107">표준 사내 또는 하드웨어 구성 외에도 RDS(원격 데스크톱) Microsoft Defender 바이러스 백신 VDI(가상 데스크톱 인프라) 환경에서도 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a8752-107">In addition to standard on-premises or hardware configurations, you can also use Microsoft Defender Antivirus in a remote desktop (RDS) or virtual desktop infrastructure (VDI) environment.</span></span>

<span data-ttu-id="a8752-108">Windows [및](/azure/virtual-desktop) VDI 지원에 대한 자세한 내용은 Microsoft 원격 데스크톱 가상 데스크톱 설명서를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="a8752-108">See [Windows Virtual Desktop Documentation](/azure/virtual-desktop) for more details on Microsoft Remote Desktop Services and VDI support.</span></span>

<span data-ttu-id="a8752-109">Azure 기반 가상 컴퓨터의 경우 [Azure Defender에서 Endpoint Protection 설치를 참조하세요.](/azure/security-center/security-center-install-endpoint-protection)</span><span class="sxs-lookup"><span data-stu-id="a8752-109">For Azure-based virtual machines, see [Install Endpoint Protection in Azure Defender](/azure/security-center/security-center-install-endpoint-protection).</span></span>

<span data-ttu-id="a8752-110">VIS에서 실행되는 VM에 업데이트를 쉽게 배포할 수 있는 기능을 사용하여 이 가이드를 단축하여 빠르고 쉽게 컴퓨터의 업데이트를 다운로드하는 방법에 대해 중점적으로 설명했습니다.</span><span class="sxs-lookup"><span data-stu-id="a8752-110">With the ability to easily deploy updates to VMs running in VDIs, we've shortened this guide to focus on how you can get updates on your machines quickly and easily.</span></span> <span data-ttu-id="a8752-111">업데이트가 호스트 서버의 구성 요소 비트로 확장된 다음 켜져 있는 경우 VM으로 직접 다운로드하기에 골든 이미지를 정기적으로 만들고 봉인할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="a8752-111">You no longer need to create and seal golden images on a periodic basis, as updates are expanded into their component bits on the host server and then downloaded directly to the VM when it's turned on.</span></span>

<span data-ttu-id="a8752-112">이 가이드에서는 다음 방법을 포함하여 최적의 보호 및 성능을 위해 VM을 구성하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="a8752-112">This guide describes how to configure your VMs for optimal protection and performance, including how to:</span></span>

- [<span data-ttu-id="a8752-113">보안 인텔리전스 업데이트에 대한 전용 VDI 파일 공유 설정</span><span class="sxs-lookup"><span data-stu-id="a8752-113">Set up a dedicated VDI file share for security intelligence updates</span></span>](#set-up-a-dedicated-vdi-file-share)
- [<span data-ttu-id="a8752-114">예약된 검사 임의화</span><span class="sxs-lookup"><span data-stu-id="a8752-114">Randomize scheduled scans</span></span>](#randomize-scheduled-scans)
- [<span data-ttu-id="a8752-115">빠른 검사 사용</span><span class="sxs-lookup"><span data-stu-id="a8752-115">Use quick scans</span></span>](#use-quick-scans)
- [<span data-ttu-id="a8752-116">알림 방지</span><span class="sxs-lookup"><span data-stu-id="a8752-116">Prevent notifications</span></span>](#prevent-notifications)
- [<span data-ttu-id="a8752-117">업데이트할 때마다 검사가 발생하지 않도록 설정</span><span class="sxs-lookup"><span data-stu-id="a8752-117">Disable scans from occurring after every update</span></span>](#disable-scans-after-an-update)
- [<span data-ttu-id="a8752-118">한동안 오프라인 상태인 기한이 지난 컴퓨터 또는 컴퓨터 검색</span><span class="sxs-lookup"><span data-stu-id="a8752-118">Scan out-of-date machines or machines that have been offline for a while</span></span>](#scan-vms-that-have-been-offline)
- [<span data-ttu-id="a8752-119">제외 적용</span><span class="sxs-lookup"><span data-stu-id="a8752-119">Apply exclusions</span></span>](#exclusions)

<span data-ttu-id="a8752-120">성능 테스트 및 자체 VDI에서 바이러스 백신 성능을 테스트하는 방법에 대한 지침과 함께 새로운 공유 보안 [인텔리전스](https://demo.wd.microsoft.com/Content/wdav-testing-vdi-ssu.pdf)업데이트 기능을 Microsoft Defender 바이러스 백신 가상 데스크톱 인프라에서 백서 응용 프로그램을 다운로드할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a8752-120">You can also download the whitepaper [Microsoft Defender Antivirus on Virtual Desktop Infrastructure](https://demo.wd.microsoft.com/Content/wdav-testing-vdi-ssu.pdf), which looks at the new shared security intelligence update feature, alongside performance testing and guidance on how you can test antivirus performance on your own VDI.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="a8752-121">VDI는 Windows Server 2012 또는 Windows Server 2016 호스트할 수 있습니다. 이전 버전의 VDI에서는 사용할 수 없는 보호 기술 및 기능이 늘어나기 때문에 VM(가상 컴퓨터)은 Windows 10 1607 이상을 실행해야 Windows.</span><span class="sxs-lookup"><span data-stu-id="a8752-121">Although the VDI can be hosted on Windows Server 2012 or Windows Server 2016, the virtual machines (VMs) should be running Windows 10, 1607 at a minimum, due to increased protection technologies and features that are unavailable in earlier versions of Windows.</span></span><br/><span data-ttu-id="a8752-122">Microsoft Defender AV가 Insider Preview, 빌드 18323 이상에서 가상 Windows 10 성능 및 기능이 개선되었습니다.</span><span class="sxs-lookup"><span data-stu-id="a8752-122">There are performance and feature improvements to the way in which Microsoft Defender AV operates on virtual machines in Windows 10 Insider Preview, build 18323 (and later).</span></span> <span data-ttu-id="a8752-123">Insider Preview 빌드를 사용하려면 이 가이드에서 확인할 것입니다. 이 버전을 지정하지 않으면 최상의 보호 및 성능을 위해 필요한 최소 버전은 Windows 10 1607입니다.</span><span class="sxs-lookup"><span data-stu-id="a8752-123">We'll identify in this guide if you need to be using an Insider Preview build; if it isn't specified, then the minimum required version for the best protection and performance is Windows 10 1607.</span></span>

## <a name="set-up-a-dedicated-vdi-file-share"></a><span data-ttu-id="a8752-124">전용 VDI 파일 공유 설정</span><span class="sxs-lookup"><span data-stu-id="a8752-124">Set up a dedicated VDI file share</span></span>

<span data-ttu-id="a8752-125">Windows 10 버전 1903에서는 호스트 컴퓨터로 다운로드한 보안 인텔리전스 업데이트의 포장을 풀어 개별 컴퓨터의 이전 CPU, 디스크 및 메모리 리소스를 절약하는 공유 보안 인텔리전스 기능을 도입했습니다.</span><span class="sxs-lookup"><span data-stu-id="a8752-125">In Windows 10, version 1903, we introduced the shared security intelligence feature, which offloads the unpackaging of downloaded security intelligence updates onto a host machine—thus saving previous CPU, disk, and memory resources on individual machines.</span></span> <span data-ttu-id="a8752-126">이 기능은 이전 버전 1703 이상에서 Windows 10 기능이 지원되었습니다.</span><span class="sxs-lookup"><span data-stu-id="a8752-126">This feature has been backported and now works in Windows 10 version 1703 and above.</span></span> <span data-ttu-id="a8752-127">이 기능은 그룹 정책 또는 PowerShell을 사용하여 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a8752-127">You can set this feature with a Group Policy, or PowerShell.</span></span>

### <a name="use-group-policy-to-enable-the-shared-security-intelligence-feature"></a><span data-ttu-id="a8752-128">그룹 정책을 사용하여 공유 보안 인텔리전스 기능을 사용하도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a8752-128">Use Group Policy to enable the shared security intelligence feature:</span></span>

1. <span data-ttu-id="a8752-129">그룹 정책 관리 컴퓨터에서 그룹 정책 관리 콘솔을 열고 구성할 그룹 정책 개체를 마우스 오른쪽 단추로 클릭한 다음 편집을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="a8752-129">On your Group Policy management computer, open the Group Policy Management Console, right-click the Group Policy Object you want to configure, and then click **Edit**.</span></span>

2. <span data-ttu-id="a8752-130">그룹 정책 **관리 편집기에서** 컴퓨터 **구성으로 이동하십시오.**</span><span class="sxs-lookup"><span data-stu-id="a8752-130">In the **Group Policy Management Editor** go to **Computer configuration**.</span></span>

3. <span data-ttu-id="a8752-131">관리 **템플릿 을 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="a8752-131">Click **Administrative templates**.</span></span>

4. <span data-ttu-id="a8752-132">보안 인텔리전스 **Windows 구성 Microsoft Defender 바이러스 백신**  >    >  **확장합니다.**</span><span class="sxs-lookup"><span data-stu-id="a8752-132">Expand the tree to **Windows components** > **Microsoft Defender Antivirus** > **Security Intelligence Updates**.</span></span>

5. <span data-ttu-id="a8752-133">VDI 클라이언트의 보안 인텔리전스 위치 정의를 두 번 **클릭한** 다음 옵션을 사용으로 **설정합니다.**</span><span class="sxs-lookup"><span data-stu-id="a8752-133">Double-click **Define security intelligence location for VDI clients**, and then set the option to **Enabled**.</span></span> <span data-ttu-id="a8752-134">필드가 자동으로 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="a8752-134">A field automatically appears.</span></span>

6. <span data-ttu-id="a8752-135">Enter `\\<sharedlocation\>\wdav-update` (이 값에 대한 도움말은 다운로드 및 포장 [풀기 참조).](#download-and-unpackage-the-latest-updates)</span><span class="sxs-lookup"><span data-stu-id="a8752-135">Enter `\\<sharedlocation\>\wdav-update` (for help with this value, see [Download and unpackage](#download-and-unpackage-the-latest-updates)).</span></span>

7. <span data-ttu-id="a8752-136">**확인** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="a8752-136">Click **OK**.</span></span>

8. <span data-ttu-id="a8752-137">테스트할 VM에 GPO를 배포합니다.</span><span class="sxs-lookup"><span data-stu-id="a8752-137">Deploy the GPO to the VMs you want to test.</span></span>

### <a name="use-powershell-to-enable-the-shared-security-intelligence-feature"></a><span data-ttu-id="a8752-138">PowerShell을 사용하여 공유 보안 인텔리전스 기능을 사용하도록 설정</span><span class="sxs-lookup"><span data-stu-id="a8752-138">Use PowerShell to enable the shared security intelligence feature</span></span>

<span data-ttu-id="a8752-139">다음 cmdlet을 사용하여 기능을 사용하도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a8752-139">Use the following cmdlet to enable the feature.</span></span> <span data-ttu-id="a8752-140">그런 다음 일반적으로 PowerShell 기반 구성 정책을 VM에 푸시할 때 이 정책을 푸시해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a8752-140">You’ll need to then push this as you normally would push PowerShell-based configuration policies onto the VMs:</span></span>

```PowerShell
Set-MpPreference -SharedSignaturesPath \\<shared location>\wdav-update
```

<span data-ttu-id="a8752-141">사용할 [내용은 다운로드](#download-and-unpackage-the-latest-updates) 및 포장 풀기 \<shared location\> 섹션을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="a8752-141">See the [Download and unpackage](#download-and-unpackage-the-latest-updates) section for what the \<shared location\> will be.</span></span>

## <a name="download-and-unpackage-the-latest-updates"></a><span data-ttu-id="a8752-142">최신 업데이트 다운로드 및 포장 풀기</span><span class="sxs-lookup"><span data-stu-id="a8752-142">Download and unpackage the latest updates</span></span>

<span data-ttu-id="a8752-143">이제 새 업데이트 다운로드 및 설치를 시작할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a8752-143">Now you can get started on downloading and installing new updates.</span></span> <span data-ttu-id="a8752-144">아래에서 샘플 PowerShell 스크립트를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a8752-144">We’ve created a sample PowerShell script for you below.</span></span> <span data-ttu-id="a8752-145">이 스크립트는 새 업데이트를 다운로드하고 VM을 준비하는 가장 쉬운 방법입니다.</span><span class="sxs-lookup"><span data-stu-id="a8752-145">This script is the easiest way to download new updates and get them ready for your VMs.</span></span> <span data-ttu-id="a8752-146">그런 다음 예약된 작업을 사용하여 관리 컴퓨터의 특정 시간에서 실행될 스크립트를 설정해야 합니다. 또는 Azure, Intune 또는 SCCM에서 PowerShell 스크립트를 사용하는 데 익숙한 경우 해당 스크립트를 사용할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a8752-146">You should then set the script to run at a certain time on the management machine by using a scheduled task (or, if you’re familiar with using PowerShell scripts in Azure, Intune, or SCCM, you could also use those scripts).</span></span>

```PowerShell
$vdmpathbase = "$env:systemdrive\wdav-update\{00000000-0000-0000-0000-"
$vdmpathtime = Get-Date -format "yMMddHHmmss"
$vdmpath = $vdmpathbase + $vdmpathtime + '}'
$vdmpackage = $vdmpath + '\mpam-fe.exe'

New-Item -ItemType Directory -Force -Path $vdmpath | Out-Null

Invoke-WebRequest -Uri 'https://go.microsoft.com/fwlink/?LinkID=121721&arch=x64' -OutFile $vdmpackage

cmd /c "cd $vdmpath & c: & mpam-fe.exe /x"
```

<span data-ttu-id="a8752-147">예약된 작업을 하루 한 번 실행하여 패키지를 다운로드하고 패키지를 언팩할 때마다 VM이 새 업데이트를 받게 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a8752-147">You can set a scheduled task to run once a day so that whenever the package is downloaded and unpacked then the VMs will receive the new update.</span></span> <span data-ttu-id="a8752-148">하루 한 번부터 시작하는 것이 되지만 영향을 이해하기 위해 빈도를 늘리거나 줄이면서 실험해 보아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a8752-148">We suggest starting with once a day—but you should experiment with increasing or decreasing the frequency to understand the impact.</span></span> 

<span data-ttu-id="a8752-149">보안 인텔리전스 패키지는 일반적으로 3~4시간마다 한 번씩 게시됩니다.</span><span class="sxs-lookup"><span data-stu-id="a8752-149">Security intelligence packages are typically published once every three to four hours.</span></span> <span data-ttu-id="a8752-150">빈도를 4시간보다 짧게 설정하면 관리 컴퓨터의 네트워크 오버헤드가 증가하여 이점이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="a8752-150">Setting a frequency shorter than four hours isn’t advised because it will increase the network overhead on your management machine for no benefit.</span></span>

### <a name="set-a-scheduled-task-to-run-the-powershell-script"></a><span data-ttu-id="a8752-151">PowerShell 스크립트를 실행하기 위해 예약된 작업 설정</span><span class="sxs-lookup"><span data-stu-id="a8752-151">Set a scheduled task to run the PowerShell script</span></span>

1. <span data-ttu-id="a8752-152">관리 컴퓨터의 시작 메뉴를 열고 **작업 스케줄러 를 입력합니다.**</span><span class="sxs-lookup"><span data-stu-id="a8752-152">On the management machine, open the Start menu and type **Task Scheduler**.</span></span> <span data-ttu-id="a8752-153">작업을 열고 작업 **만들기... 를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="a8752-153">Open it and select **Create task…**</span></span> <span data-ttu-id="a8752-154">을(를) 왼쪽 패널에 표시</span><span class="sxs-lookup"><span data-stu-id="a8752-154">on the side panel.</span></span>

2. <span data-ttu-id="a8752-155">보안 인텔리전스 **unpacker로 이름을 입력합니다.**</span><span class="sxs-lookup"><span data-stu-id="a8752-155">Enter the name as **Security intelligence unpacker**.</span></span> <span data-ttu-id="a8752-156">트리거 **탭으로** 이동하십시오. 새로 **추가...를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="a8752-156">Go to the **Trigger** tab. Select **New…**</span></span><span data-ttu-id="a8752-157"> > **매일** 을 선택하고 **확인 을 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="a8752-157"> > **Daily**, and select **OK**.</span></span>

3. <span data-ttu-id="a8752-158">작업 **탭으로** 이동하십시오. 새로 **추가...를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="a8752-158">Go to the **Actions** tab. Select **New…**</span></span> <span data-ttu-id="a8752-159">프로그램/스크립트 필드에 **PowerShell을** **입력합니다.**</span><span class="sxs-lookup"><span data-stu-id="a8752-159">Enter **PowerShell** in the **Program/Script** field.</span></span> <span data-ttu-id="a8752-160">인수 `-ExecutionPolicy Bypass c:\wdav-update\vdmdlunpack.ps1` **추가 필드에 입력합니다.**</span><span class="sxs-lookup"><span data-stu-id="a8752-160">Enter `-ExecutionPolicy Bypass c:\wdav-update\vdmdlunpack.ps1` in the **Add arguments** field.</span></span> <span data-ttu-id="a8752-161">**확인** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="a8752-161">Select **OK**.</span></span>

4. <span data-ttu-id="a8752-162">원하는 경우 추가 설정을 구성하도록 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a8752-162">You can choose to configure additional settings if you wish.</span></span>

5. <span data-ttu-id="a8752-163">**확인을** 선택하여 예약된 작업을 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="a8752-163">Select **OK** to save the scheduled task.</span></span>
 
<span data-ttu-id="a8752-164">작업을 마우스 오른쪽 단추로 클릭하고 실행을 클릭하여 수동으로 업데이트를 시작할 **수 있습니다.**</span><span class="sxs-lookup"><span data-stu-id="a8752-164">You can initiate the update manually by right-clicking on the task and clicking **Run**.</span></span>

### <a name="download-and-unpackage-manually"></a><span data-ttu-id="a8752-165">수동으로 다운로드 및 포장 풀기</span><span class="sxs-lookup"><span data-stu-id="a8752-165">Download and unpackage manually</span></span>

<span data-ttu-id="a8752-166">모든 작업을 수동으로 수행하려면 스크립트의 동작을 복제하기 위해 수행해야 할 작업을 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="a8752-166">If you would prefer to do everything manually, here's what to do to replicate the script’s behavior:</span></span>

1. <span data-ttu-id="a8752-167">인텔리전스 업데이트를 저장하기 위해 라는 시스템 루트에 새 폴더를 만들 수 있습니다(예: `wdav_update` 폴더 `c:\wdav_update` 만들기).</span><span class="sxs-lookup"><span data-stu-id="a8752-167">Create a new folder on the system root called `wdav_update` to store intelligence updates, for example, create the folder `c:\wdav_update`.</span></span>

2. <span data-ttu-id="a8752-168">GUID 이름으로 wdav_update 하위폴더 만들기 `{00000000-0000-0000-0000-000000000000}`</span><span class="sxs-lookup"><span data-stu-id="a8752-168">Create a subfolder under *wdav_update* with a GUID name, such as `{00000000-0000-0000-0000-000000000000}`</span></span>

<span data-ttu-id="a8752-169">예를 들면 다음과 같습니다. `c:\wdav_update\{00000000-0000-0000-0000-000000000000}`</span><span class="sxs-lookup"><span data-stu-id="a8752-169">Here's an example: `c:\wdav_update\{00000000-0000-0000-0000-000000000000}`</span></span>

   > [!NOTE]
   > <span data-ttu-id="a8752-170">스크립트에서 GUID의 마지막 12자리 숫자가 매월 새 폴더가 만들어지기 위해 파일을 다운로드한 연도, 월, 일 및 시간으로 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="a8752-170">In the script we set it so the last 12 digits of the GUID are the year, month, day, and time when the file was downloaded so that a new folder is created each time.</span></span> <span data-ttu-id="a8752-171">파일을 매시간 동일한 폴더로 다운로드할 수 있도록 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a8752-171">You can change this so that the file is downloaded to the same folder each time.</span></span>

3. <span data-ttu-id="a8752-172">GUID 폴더로 보안 인텔리전스 [https://www.microsoft.com/wdsi/definitions](https://www.microsoft.com/wdsi/definitions)  패키지를 다운로드합니다.</span><span class="sxs-lookup"><span data-stu-id="a8752-172">Download a security intelligence package from [https://www.microsoft.com/wdsi/definitions](https://www.microsoft.com/wdsi/definitions)  into the GUID folder.</span></span> <span data-ttu-id="a8752-173">파일의 이름을 로 지정해야 `mpam-fe.exe` 합니다.</span><span class="sxs-lookup"><span data-stu-id="a8752-173">The file should be named `mpam-fe.exe`.</span></span>

4. <span data-ttu-id="a8752-174">cmd 프롬프트 창을 열고 만든 GUID 폴더로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="a8752-174">Open a cmd prompt window and navigate to the GUID folder you created.</span></span> <span data-ttu-id="a8752-175">**/X** 추출 명령을 사용하여 파일을 추출합니다(예: `mpam-fe.exe /X` ).</span><span class="sxs-lookup"><span data-stu-id="a8752-175">Use the **/X** extraction command to extract the files, for example `mpam-fe.exe /X`.</span></span>

   > [!NOTE]
   > <span data-ttu-id="a8752-176">VM은 추출된 업데이트 패키지를 통해 새 GUID 폴더를 만들 때마다 또는 기존 폴더가 추출된 새 패키지로 업데이트될 때마다 업데이트된 패키지를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="a8752-176">The VMs will pick up the updated package whenever a new GUID folder is created with an extracted update package or whenever an existing folder is updated with a new extracted package.</span></span>

## <a name="randomize-scheduled-scans"></a><span data-ttu-id="a8752-177">예약된 검사 임의화</span><span class="sxs-lookup"><span data-stu-id="a8752-177">Randomize scheduled scans</span></span>

<span data-ttu-id="a8752-178">실시간 보호 및 검사 외에도 예약된 [검사가 실행됩니다.](configure-real-time-protection-microsoft-defender-antivirus.md)</span><span class="sxs-lookup"><span data-stu-id="a8752-178">Scheduled scans run in addition to [real-time protection and scanning](configure-real-time-protection-microsoft-defender-antivirus.md).</span></span>

<span data-ttu-id="a8752-179">검사 자체의 시작 시간은 예약된 검사 **정책(ScheduleDay,** **ScheduleTime** 및 **ScheduleQuickScanTime)을 기반으로 합니다.**</span><span class="sxs-lookup"><span data-stu-id="a8752-179">The start time of the scan itself is still based on the scheduled scan policy (**ScheduleDay**, **ScheduleTime**, and **ScheduleQuickScanTime**).</span></span> <span data-ttu-id="a8752-180">임의 설정으로 인해 Microsoft Defender 바이러스 백신 설정된 시간부터 4시간 이내에 각 컴퓨터의 검색이 시작됩니다.</span><span class="sxs-lookup"><span data-stu-id="a8752-180">Randomization will cause Microsoft Defender Antivirus to start a scan on each machine within a 4-hour window from the time set for the scheduled scan.</span></span>

<span data-ttu-id="a8752-181">예약된 [검사에](scheduled-catch-up-scans-microsoft-defender-antivirus.md) 사용할 수 있는 다른 구성 옵션에 대한 검사 예약을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="a8752-181">See [Schedule scans](scheduled-catch-up-scans-microsoft-defender-antivirus.md) for other configuration options available for scheduled scans.</span></span>

## <a name="use-quick-scans"></a><span data-ttu-id="a8752-182">빠른 검사 사용</span><span class="sxs-lookup"><span data-stu-id="a8752-182">Use quick scans</span></span>

<span data-ttu-id="a8752-183">예약된 검사 중에 수행할 검사 유형을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a8752-183">You can specify the type of scan that should be performed during a scheduled scan.</span></span> <span data-ttu-id="a8752-184">빠른 검사는 맬웨어가 활성화해야 하는 모든 장소를 검색하도록 디자인된 기본 접근 방식입니다.</span><span class="sxs-lookup"><span data-stu-id="a8752-184">Quick scans are the preferred approach as they are designed to look in all places where malware needs to reside to be active.</span></span> <span data-ttu-id="a8752-185">다음 절차에서는 그룹 정책을 사용하여 빠른 검색을 설정하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="a8752-185">The following procedure describes how to set up quick scans using Group Policy.</span></span>

1. <span data-ttu-id="a8752-186">그룹 정책 편집기에서 검사에서 관리 템플릿 Windows  >  **구성**  >  **Microsoft Defender 바이러스 백신**  >  **로 이동하십시오.**</span><span class="sxs-lookup"><span data-stu-id="a8752-186">In your Group Policy Editor, go to **Administrative templates** > **Windows components** > **Microsoft Defender Antivirus** > **Scan**.</span></span>

2. <span data-ttu-id="a8752-187">예약된 **검사에** 사용할 검사 유형 지정을 선택한 다음 정책 설정을 편집합니다.</span><span class="sxs-lookup"><span data-stu-id="a8752-187">Select **Specify the scan type to use for a scheduled scan** and then edit the policy setting.</span></span>

3. <span data-ttu-id="a8752-188">정책을 **사용으로 설정하고** 옵션 에서 빠른 검사 **를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="a8752-188">Set the policy to **Enabled**, and then under **Options**, select  **Quick scan**.</span></span>

4. <span data-ttu-id="a8752-189">**확인** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="a8752-189">Select **OK**.</span></span> 

5. <span data-ttu-id="a8752-190">평소와 같이 그룹 정책 개체를 배포합니다.</span><span class="sxs-lookup"><span data-stu-id="a8752-190">Deploy your Group Policy object as you usually do.</span></span>

## <a name="prevent-notifications"></a><span data-ttu-id="a8752-191">알림 방지</span><span class="sxs-lookup"><span data-stu-id="a8752-191">Prevent notifications</span></span>

<span data-ttu-id="a8752-192">경우에 따라 Microsoft Defender 바이러스 백신 전송되거나 여러 세션에서 유지될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a8752-192">Sometimes, Microsoft Defender Antivirus notifications may be sent to or persist across multiple sessions.</span></span> <span data-ttu-id="a8752-193">이 문제를 최소화하기 위해 사용자 인터페이스를 Microsoft Defender 바이러스 백신 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a8752-193">In order to minimize this problem, you can lock down the Microsoft Defender Antivirus user interface.</span></span> <span data-ttu-id="a8752-194">다음 절차에서는 그룹 정책을 사용하여 알림을 표시하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="a8752-194">The following procedure describes how to suppress notifications with Group Policy.</span></span>

1. <span data-ttu-id="a8752-195">그룹 정책 편집기에서 클라이언트 **인터페이스의** Windows 구성  >  **Microsoft Defender 바이러스 백신**  >  **로 이동하십시오.**</span><span class="sxs-lookup"><span data-stu-id="a8752-195">In your Group Policy Editor, go to **Windows components** > **Microsoft Defender Antivirus** > **Client Interface**.</span></span>

2. <span data-ttu-id="a8752-196">모든 **알림 표시 안 를 선택한** 다음 정책 설정을 편집합니다.</span><span class="sxs-lookup"><span data-stu-id="a8752-196">Select **Suppress all notifications** and then edit the policy settings.</span></span> 

3. <span data-ttu-id="a8752-197">정책을 **사용으로 설정하고** 확인 을 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="a8752-197">Set the policy to **Enabled**, and then select **OK**.</span></span>

4. <span data-ttu-id="a8752-198">평소와 같이 그룹 정책 개체를 배포합니다.</span><span class="sxs-lookup"><span data-stu-id="a8752-198">Deploy your Group Policy object as you usually do.</span></span>

<span data-ttu-id="a8752-199">알림을 표시하지 Microsoft Defender 바이러스 백신 검사가 수행되거나 수정 작업이 수행될 Windows 10 알림 센터에 알림이 표시되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="a8752-199">Suppressing notifications prevents notifications from Microsoft Defender Antivirus from showing up in the Action Center on Windows 10 when scans are done or remediation actions are taken.</span></span> <span data-ttu-id="a8752-200">그러나 보안 운영 팀의 검색 결과는 [https://securitycenter.windows.com](https://securitycenter.windows.com) Microsoft Defender 보안 센터( ).</span><span class="sxs-lookup"><span data-stu-id="a8752-200">However, your security operations team will see the results of the scan in the Microsoft Defender Security Center ([https://securitycenter.windows.com](https://securitycenter.windows.com)).</span></span>

> [!TIP]
> <span data-ttu-id="a8752-201">관리 센터를 Windows 10 다음 단계 중 하나를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="a8752-201">To open the Action Center on Windows 10, take one of the following steps:</span></span>
> - <span data-ttu-id="a8752-202">작업 표시줄의 오른쪽 끝에서 작업 센터 아이콘을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="a8752-202">On the right end of the taskbar, select the Action Center icon.</span></span>
> - <span data-ttu-id="a8752-203">로고 Windows 단추 + A를 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="a8752-203">Press the Windows logo key button + A.</span></span>
> - <span data-ttu-id="a8752-204">터치 스크린 디바이스에서 화면 오른쪽 가장자리에서 스와이프합니다.</span><span class="sxs-lookup"><span data-stu-id="a8752-204">On a touchscreen device, swipe in from the right edge of the screen.</span></span>

## <a name="disable-scans-after-an-update"></a><span data-ttu-id="a8752-205">업데이트 후 검사 사용 안</span><span class="sxs-lookup"><span data-stu-id="a8752-205">Disable scans after an update</span></span>

<span data-ttu-id="a8752-206">업데이트 후 검색을 사용할 수 않도록 하면 업데이트를 받은 후 검사가 실행되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="a8752-206">Disabling a scan after an update will prevent a scan from occurring after receiving an update.</span></span> <span data-ttu-id="a8752-207">빠른 검사도 실행한 경우 기본 이미지를 만들 때 이 설정을 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a8752-207">You can apply this setting when creating the base image if you have also run a quick scan.</span></span> <span data-ttu-id="a8752-208">이렇게 하면 새로 업데이트된 VM이 기본 이미지를 만들 때 이미 검사한 검사로 다시 검색하지 못하게 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a8752-208">This way, you can prevent the newly updated VM from performing a scan again (as you've already scanned it when you created the base image).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="a8752-209">업데이트 후 검색을 실행하면 최신 보안 인텔리전스 업데이트로 VM을 보호하는 데 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a8752-209">Running scans after an update will help ensure your VMs are protected with the latest Security intelligence updates.</span></span> <span data-ttu-id="a8752-210">이 옵션을 설정하면 VM의 보호 수준이 낮아지며, 기본 이미지를 처음 만들거나 배포할 때만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a8752-210">Disabling this option will reduce the protection level of your VMs and should only be used when first creating or deploying the base image.</span></span>

1. <span data-ttu-id="a8752-211">그룹 정책 편집기에서 보안 **인텔리전스 Windows 구성**  >  **Microsoft Defender 바이러스 백신**  >  **로 이동하세요.**</span><span class="sxs-lookup"><span data-stu-id="a8752-211">In your Group Policy Editor, go to **Windows components** > **Microsoft Defender Antivirus** > **Security Intelligence Updates**.</span></span>

2. <span data-ttu-id="a8752-212">보안 **인텔리전스 업데이트 후 검사 켜기 를 선택한** 다음 정책 설정을 편집합니다.</span><span class="sxs-lookup"><span data-stu-id="a8752-212">Select **Turn on scan after security intelligence update** and then edit the policy setting.</span></span>

3. <span data-ttu-id="a8752-213">정책을 사용 안 **으로 설정**</span><span class="sxs-lookup"><span data-stu-id="a8752-213">Set the policy to **Disabled**.</span></span>

4. <span data-ttu-id="a8752-214">**확인** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="a8752-214">Select **OK**.</span></span>

5. <span data-ttu-id="a8752-215">평소와 같이 그룹 정책 개체를 배포합니다.</span><span class="sxs-lookup"><span data-stu-id="a8752-215">Deploy your Group Policy object as you usually do.</span></span>

<span data-ttu-id="a8752-216">이 정책은 업데이트 후 즉시 검사가 실행되지 않도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="a8752-216">This policy prevents a scan from running immediately after an update.</span></span>

## <a name="scan-vms-that-have-been-offline"></a><span data-ttu-id="a8752-217">오프라인 상태인 VM 검사</span><span class="sxs-lookup"><span data-stu-id="a8752-217">Scan VMs that have been offline</span></span>

1. <span data-ttu-id="a8752-218">그룹 정책 편집기에서 검사에서 Windows **구성**  >  **Microsoft Defender 바이러스 백신**  >  **로 이동하십시오.**</span><span class="sxs-lookup"><span data-stu-id="a8752-218">In your Group Policy Editor, go to to **Windows components** > **Microsoft Defender Antivirus** > **Scan**.</span></span>

2. <span data-ttu-id="a8752-219">빠른 **추가 검사 켜기 를 선택한** 다음 정책 설정을 편집합니다.</span><span class="sxs-lookup"><span data-stu-id="a8752-219">Select **Turn on catch-up quick scan** and then edit the policy setting.</span></span>

3. <span data-ttu-id="a8752-220">정책을 사용으로 **설정합니다.**</span><span class="sxs-lookup"><span data-stu-id="a8752-220">Set the policy to **Enabled**.</span></span>

4. <span data-ttu-id="a8752-221">**확인** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="a8752-221">Select **OK**.</span></span>

5. <span data-ttu-id="a8752-222">일반적으로 그룹 정책 개체를 배포합니다.</span><span class="sxs-lookup"><span data-stu-id="a8752-222">Deploy your Group Policy Object as you usually do.</span></span>

<span data-ttu-id="a8752-223">이 정책은 VM이 연속으로 두 개 이상의 예약된 검사가 누락된 경우 강제로 검색을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="a8752-223">This policy forces a scan if the VM has missed two or more consecutive scheduled scans.</span></span>

## <a name="enable-headless-ui-mode"></a><span data-ttu-id="a8752-224">헤드리스 UI 모드 사용</span><span class="sxs-lookup"><span data-stu-id="a8752-224">Enable headless UI mode</span></span>

1. <span data-ttu-id="a8752-225">그룹 정책 편집기에서 클라이언트 **인터페이스의** Windows 구성  >  **Microsoft Defender 바이러스 백신**  >  **로 이동하십시오.**</span><span class="sxs-lookup"><span data-stu-id="a8752-225">In your Group Policy Editor, go to **Windows components** > **Microsoft Defender Antivirus** > **Client Interface**.</span></span>

2. <span data-ttu-id="a8752-226">헤드리스 **UI 모드 사용 을 선택하고** 정책을 편집합니다.</span><span class="sxs-lookup"><span data-stu-id="a8752-226">Select **Enable headless UI mode** and edit the policy.</span></span>

3. <span data-ttu-id="a8752-227">정책을 사용으로 **설정합니다.**</span><span class="sxs-lookup"><span data-stu-id="a8752-227">Set the policy to **Enabled**.</span></span>

4. <span data-ttu-id="a8752-228">**확인** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="a8752-228">Click **OK**.</span></span>

5. <span data-ttu-id="a8752-229">일반적으로 그룹 정책 개체를 배포합니다.</span><span class="sxs-lookup"><span data-stu-id="a8752-229">Deploy your Group Policy Object as you usually do.</span></span>
 
<span data-ttu-id="a8752-230">이 정책은 조직의 Microsoft Defender 바이러스 백신 사용자 인터페이스 전체를 숨길 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a8752-230">This policy hides the entire Microsoft Defender Antivirus user interface from end users in your organization.</span></span>

## <a name="exclusions"></a><span data-ttu-id="a8752-231">제외</span><span class="sxs-lookup"><span data-stu-id="a8752-231">Exclusions</span></span>

<span data-ttu-id="a8752-232">제외는 필요에 맞게 추가, 제거 또는 사용자 지정될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a8752-232">Exclusions can be added, removed, or customized to suit your needs.</span></span>

<span data-ttu-id="a8752-233">자세한 내용은 [Configure Microsoft Defender 바이러스 백신 exclusions on Windows 참조하세요.](configure-exclusions-microsoft-defender-antivirus.md)</span><span class="sxs-lookup"><span data-stu-id="a8752-233">For more information, see [Configure Microsoft Defender Antivirus exclusions on Windows Server](configure-exclusions-microsoft-defender-antivirus.md).</span></span>

## <a name="additional-resources"></a><span data-ttu-id="a8752-234">추가 리소스</span><span class="sxs-lookup"><span data-stu-id="a8752-234">Additional resources</span></span>

- [<span data-ttu-id="a8752-235">기술 Community 블로그: 비영구 Microsoft Defender 바이러스 백신 VDI 컴퓨터용 구성</span><span class="sxs-lookup"><span data-stu-id="a8752-235">Tech Community Blog: Configuring Microsoft Defender Antivirus for non-persistent VDI machines</span></span>](https://techcommunity.microsoft.com/t5/microsoft-defender-for-endpoint/configuring-microsoft-defender-antivirus-for-non-persistent-vdi/ba-p/1489633)
- [<span data-ttu-id="a8752-236">원격 데스크톱 서비스 및 VDI의 TechNet 포럼</span><span class="sxs-lookup"><span data-stu-id="a8752-236">TechNet forums on Remote Desktop Services and VDI</span></span>](https://social.technet.microsoft.com/Forums/windowsserver/en-US/home?forum=winserverTS)
- [<span data-ttu-id="a8752-237">SignatureDownloadCustomTask PowerShell 스크립트</span><span class="sxs-lookup"><span data-stu-id="a8752-237">SignatureDownloadCustomTask PowerShell script</span></span>](https://www.powershellgallery.com/packages/SignatureDownloadCustomTask/1.4)