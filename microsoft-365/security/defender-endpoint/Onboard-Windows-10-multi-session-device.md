---
title: Windows Virtual Desktop에서 Windows 10 다중 세션 장치 온보딩
description: 이 문서에서 Windows Virtual Desktop에서 Windows 10 다중 세션 장치 온보드에 대해 자세히 읽어 주세요.
keywords: Windows Virtual Desktop, WVD, microsoft defender, endpoint, onboard
search.product: eADQiWindows 10XVcnh
ms.prod: w10
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: Normal
audience: ITPro
ms.topic: article
author: dansimp
ms.author: dansimp
ms.custom: nextgen
ms.reviewer: ''
manager: dansimp
ms.openlocfilehash: 0ef80e2aaccbf25a79083c2f95ea7399e30ea651
ms.sourcegitcommit: 7a339c9f7039825d131b39481ddf54c57b021b11
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2021
ms.locfileid: "51764320"
---
# <a name="onboard-windows-10-multi-session-devices-in-windows-virtual-desktop"></a><span data-ttu-id="3cf64-104">Windows Virtual Desktop에서 Windows 10 다중 세션 장치 온보딩</span><span class="sxs-lookup"><span data-stu-id="3cf64-104">Onboard Windows 10 multi-session devices in Windows Virtual Desktop</span></span> 
<span data-ttu-id="3cf64-105">6분 읽기</span><span class="sxs-lookup"><span data-stu-id="3cf64-105">6 minutes to read</span></span> 

<span data-ttu-id="3cf64-106">적용 대상:</span><span class="sxs-lookup"><span data-stu-id="3cf64-106">Applies to:</span></span> 
- <span data-ttu-id="3cf64-107">WVD(Windows Virtual Desktop)에서 실행되는 Windows 10 다중 세션</span><span class="sxs-lookup"><span data-stu-id="3cf64-107">Windows 10 multi-session running on Windows Virtual Desktop (WVD)</span></span> 

<span data-ttu-id="3cf64-108">끝점용 Microsoft Defender는 VDI 및 Windows Virtual Desktop 세션 모두 모니터링을 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="3cf64-108">Microsoft Defender for Endpoint supports monitoring both VDI and Windows Virtual Desktop sessions.</span></span> <span data-ttu-id="3cf64-109">조직의 요구에 따라 VDI 또는 Windows Virtual Desktop 세션을 구현하여 직원이 관리되지 않는 디바이스, 원격 위치 또는 유사한 시나리오에서 회사 데이터 및 앱에 액세스하는 데 도움이 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3cf64-109">Depending on your organization's needs, you might need to implement VDI or Windows Virtual Desktop sessions to help your employees access corporate data and apps from an unmanaged device, remote location, or similar scenario.</span></span> <span data-ttu-id="3cf64-110">끝점용 Microsoft Defender를 사용하여 이러한 가상 컴퓨터를 모니터링하여 이상한 활동을 모니터링할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3cf64-110">With Microsoft Defender for Endpoint, you can monitor these virtual machines for anomalous activity.</span></span>

 ## <a name="before-you-begin"></a><span data-ttu-id="3cf64-111">시작하기 전에</span><span class="sxs-lookup"><span data-stu-id="3cf64-111">Before you begin</span></span>
<span data-ttu-id="3cf64-112">비영구 [VDI에](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/configure-endpoints-vdi#onboard-non-persistent-virtual-desktop-infrastructure-vdi-devices-1)대한 고려 사항을 잘 알고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3cf64-112">Familiarize yourself with the [considerations for non-persistent VDI](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/configure-endpoints-vdi#onboard-non-persistent-virtual-desktop-infrastructure-vdi-devices-1).</span></span> <span data-ttu-id="3cf64-113">[Windows Virtual Desktop은](https://docs.microsoft.com/azure/virtual-desktop/overview) 비영구 옵션을 제공하지는 않는 반면, 새 호스트를 프로비전하고 컴퓨터를 다시 재배포하는 데 사용할 수 있는 골든 Windows 이미지를 사용하는 방법을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="3cf64-113">While [Windows Virtual Desktop](https://docs.microsoft.com/azure/virtual-desktop/overview) doesn't provide non-persistence options, it does provide ways to use a golden Windows image that can be used to provision new hosts and redeploy machines.</span></span> <span data-ttu-id="3cf64-114">이렇게 하면 환경의 변동성이 증가하고 끝점 포털의 Microsoft Defender 포털에서 만들어지고 유지 관리되는 항목에 영향을 주어 보안 분석가의 가시성이 감소할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3cf64-114">This increases volatility in the environment and thus impacts what entries are created and maintained in the Microsoft Defender for Endpoint portal, potentially reducing visibility for your security analysts.</span></span>

> [!NOTE]
> <span data-ttu-id="3cf64-115">선택한 온보딩 방법에 따라 장치가 끝점용 Microsoft Defender 포털에 다음 중 한 가지로 표시될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3cf64-115">Depending on your choice of onboarding method, devices can appear in Microsoft Defender for Endpoint portal as either:</span></span> 
> - <span data-ttu-id="3cf64-116">각 가상 데스크톱에 대한 단일 항목</span><span class="sxs-lookup"><span data-stu-id="3cf64-116">Single entry for each virtual desktop</span></span> 
> - <span data-ttu-id="3cf64-117">각 가상 데스크톱에 대한 여러 항목</span><span class="sxs-lookup"><span data-stu-id="3cf64-117">Multiple entries for each virtual desktop</span></span> 

<span data-ttu-id="3cf64-118">Microsoft는 가상 데스크톱당 단일 항목으로 Windows Virtual Desktop을 온보드하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="3cf64-118">Microsoft recommends onboarding Windows Virtual Desktop as a single entry per virtual desktop.</span></span> <span data-ttu-id="3cf64-119">이렇게 하면 Microsoft Defender 끝점 포털의 조사 환경이 컴퓨터 이름을 기반으로 한 디바이스의 컨텍스트에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3cf64-119">This ensures that the investigation experience in the Microsoft Defender Endpoint portal is in the context of one device based on the machine name.</span></span> <span data-ttu-id="3cf64-120">WVD 호스트를 자주 삭제하고 다시 배포하는 조직에서는 동일한 컴퓨터의 여러 개체가 끝점용 Microsoft Defender 포털에서 만들어질 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="3cf64-120">Organizations that frequently delete and redeploy WVD hosts should strongly consider using this method as it prevents multiple objects for the same machine from being created in the Microsoft Defender for Endpoint portal.</span></span> <span data-ttu-id="3cf64-121">이로 인해 인시던트 조사 시 혼동을 피할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3cf64-121">This can lead to confusion when investigating incidents.</span></span> <span data-ttu-id="3cf64-122">테스트 또는 비휘발성 환경의 경우 다르게 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3cf64-122">For test or non-volatile environments, you may opt to choose differently.</span></span> 

<span data-ttu-id="3cf64-123">WVD 골든 이미지에 끝점용 Microsoft Defender 온보딩 스크립트를 추가하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="3cf64-123">Microsoft recommends adding the Microsoft Defender for Endpoint onboarding script to the WVD golden image.</span></span> <span data-ttu-id="3cf64-124">이렇게 하면 이 온보딩 스크립트가 첫 번째 부팅 시 즉시 실행됩니다.</span><span class="sxs-lookup"><span data-stu-id="3cf64-124">This way, you can be sure that this onboarding script runs immediately at first boot.</span></span> <span data-ttu-id="3cf64-125">이 스크립트는 WVD 골든 이미지에서 프로비전된 모든 WVD 컴퓨터의 첫 번째 부팅 시 시작 스크립트로 실행됩니다.</span><span class="sxs-lookup"><span data-stu-id="3cf64-125">It's executed as a startup script at first boot on all the WVD machines that are provisioned from the WVD golden image.</span></span> <span data-ttu-id="3cf64-126">그러나 수정하지 않고 갤러리 이미지 중 하나를 사용하는 경우 스크립트를 공유 위치에 두고 로컬 또는 도메인 그룹 정책에서 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="3cf64-126">However, if you're using one of the gallery images without modification, place the script in a shared location and call it from either local or domain group policy.</span></span> 

> [!NOTE]
> <span data-ttu-id="3cf64-127">WVD 골든 이미지에서 VDI 온보딩 시작 스크립트의 배치 및 구성은 WVD가 시작되면 실행되는 시작 스크립트로 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="3cf64-127">The placement and configuration of the VDI onboarding startup script on the WVD golden image configures it as a startup script that runs when the WVD starts.</span></span> <span data-ttu-id="3cf64-128">실제 WVD 골든 이미지를 온보드하는 것은 권장되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="3cf64-128">It's NOT recommended to onboard the actual WVD golden image.</span></span> <span data-ttu-id="3cf64-129">또 다른 고려 사항은 스크립트를 실행하는 데 사용되는 메서드입니다.</span><span class="sxs-lookup"><span data-stu-id="3cf64-129">Another consideration is the method used to run the script.</span></span> <span data-ttu-id="3cf64-130">세션을 받는 데 사용할 수 있는 컴퓨터와 서비스에 대한 장치 온보드 간의 시간을 줄이기 위해 가능한 한 시작/프로비저닝 프로세스 초기에 실행해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3cf64-130">It should run as early in the startup/provisioning process as possible to reduce the time between the machine being available to receive sessions and the device onboarding to the service.</span></span> <span data-ttu-id="3cf64-131">아래 시나리오 1에서는 & 2를 고려합니다.</span><span class="sxs-lookup"><span data-stu-id="3cf64-131">Below scenarios 1 & 2 take this into account.</span></span>

### <a name="scenarios"></a><span data-ttu-id="3cf64-132">시나리오</span><span class="sxs-lookup"><span data-stu-id="3cf64-132">Scenarios</span></span>
<span data-ttu-id="3cf64-133">WVD 호스트 컴퓨터는 여러 가지 방법으로 온보드합니다.</span><span class="sxs-lookup"><span data-stu-id="3cf64-133">There are several ways to onboard a WVD host machine:</span></span>

- <span data-ttu-id="3cf64-134">시작 중에 골든 이미지 또는 공유 위치에서 스크립트를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="3cf64-134">Run the script in the golden image (or from a shared location) during startup.</span></span>
- <span data-ttu-id="3cf64-135">관리 도구를 사용하여 스크립트를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="3cf64-135">Use a management tool to run the script.</span></span>

#### <a name="scenario-1-using-local-group-policy"></a><span data-ttu-id="3cf64-136">*시나리오 1: 로컬 그룹 정책 사용*</span><span class="sxs-lookup"><span data-stu-id="3cf64-136">*Scenario 1: Using local group policy*</span></span>
<span data-ttu-id="3cf64-137">이 시나리오에서는 스크립트를 골든 이미지에 배치하고 로컬 그룹 정책을 사용하여 부팅 프로세스 초기에 실행해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3cf64-137">This scenario requires placing the script in a golden image and uses local group policy to run early in the boot process.</span></span>

<span data-ttu-id="3cf64-138">비영구적 가상 데스크톱 인프라 VDI 디바이스 [온보드의 지침을 사용하세요.](configure-endpoints-vdi.md#onboard-non-persistent-virtual-desktop-infrastructure-vdi-devices-1)</span><span class="sxs-lookup"><span data-stu-id="3cf64-138">Use the instructions in [Onboard non-persistent virtual desktop infrastructure VDI devices](configure-endpoints-vdi.md#onboard-non-persistent-virtual-desktop-infrastructure-vdi-devices-1).</span></span>

<span data-ttu-id="3cf64-139">각 디바이스에 대한 단일 항목에 대한 지침을 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="3cf64-139">Follow the instructions for a single entry for each device.</span></span>

#### <a name="scenario-2-using-domain-group-policy"></a><span data-ttu-id="3cf64-140">*시나리오 2: 도메인 그룹 정책 사용*</span><span class="sxs-lookup"><span data-stu-id="3cf64-140">*Scenario 2: Using domain group policy*</span></span>
<span data-ttu-id="3cf64-141">이 시나리오에서는 중앙에 있는 스크립트를 사용하고 도메인 기반 그룹 정책을 사용하여 스크립트를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="3cf64-141">This scenario uses a centrally located script and runs it using a domain-based group policy.</span></span> <span data-ttu-id="3cf64-142">또한 골든 이미지에 스크립트를 추가하고 동일한 방식으로 실행할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3cf64-142">You can also place the script in the golden image and run it in the same way.</span></span>

<span data-ttu-id="3cf64-143">**WindowsDefenderATPOnboardingPackage.zip 보안 센터에서 Windows Defender 다운로드**</span><span class="sxs-lookup"><span data-stu-id="3cf64-143">**Download the WindowsDefenderATPOnboardingPackage.zip file from the Windows Defender Security Center**</span></span>

1. <span data-ttu-id="3cf64-144">VDI 구성 패키지 .zip 파일(WindowsDefenderATPOnboardingPackage.zip) 열기</span><span class="sxs-lookup"><span data-stu-id="3cf64-144">Open the VDI configuration package .zip file (WindowsDefenderATPOnboardingPackage.zip)</span></span>  

    1. <span data-ttu-id="3cf64-145">Microsoft Defender 보안 센터 탐색 창에서 설정   >  **온보딩 을 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="3cf64-145">In the Microsoft Defender Security Center navigation pane, select **Settings** > **Onboarding**.</span></span> 
    1. <span data-ttu-id="3cf64-146">운영 체제로 Windows 10을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="3cf64-146">Select Windows 10 as the operating system.</span></span> 
    1. <span data-ttu-id="3cf64-147">배포 **방법 필드에서** 비영구 끝점에 대한 VDI 온보딩 스크립트를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="3cf64-147">In the **Deployment method** field, select VDI onboarding scripts for non-persistent endpoints.</span></span> 
    1. <span data-ttu-id="3cf64-148">패키지 **다운로드를 클릭하고** .zip 파일을 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="3cf64-148">Click **Download package** and save the .zip file.</span></span> 

2. <span data-ttu-id="3cf64-149">.zip 파일의 내용을 장치에서 액세스할 수 있는 공유 읽기 전용 위치에 추출합니다.</span><span class="sxs-lookup"><span data-stu-id="3cf64-149">Extract the contents of the .zip file to a shared, read-only location that can be accessed by the device.</span></span> <span data-ttu-id="3cf64-150">**OptionalParamsPolicy라는** 폴더와 **WindowsDefenderATPOnboardingScript.cmd** 및 **Onboard-NonPersistentMachine.ps1.**</span><span class="sxs-lookup"><span data-stu-id="3cf64-150">You should have a folder called **OptionalParamsPolicy** and the files **WindowsDefenderATPOnboardingScript.cmd** and **Onboard-NonPersistentMachine.ps1**.</span></span>

<span data-ttu-id="3cf64-151">**그룹 정책 관리 콘솔을 사용하여 가상 컴퓨터 시작 시 스크립트 실행**</span><span class="sxs-lookup"><span data-stu-id="3cf64-151">**Use Group Policy management console to run the script when the virtual machine starts**</span></span>

1. <span data-ttu-id="3cf64-152">GPMC(그룹 정책 관리 콘솔)를 열고 구성할 GPO(그룹 정책 개체)를 마우스 오른쪽 단추로 클릭하고 편집을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="3cf64-152">Open the Group Policy Management Console (GPMC), right-click the Group Policy Object (GPO) you want to configure and click **Edit**.</span></span>

2. <span data-ttu-id="3cf64-153">그룹 정책 관리 편집기에서 컴퓨터 **구성** 기본 설정 \>  \> **제어판 설정으로 이동합니다.**</span><span class="sxs-lookup"><span data-stu-id="3cf64-153">In the Group Policy Management Editor, go to **Computer configuration** \> **Preferences** \> **Control panel settings**.</span></span> 

3. <span data-ttu-id="3cf64-154">예약된 **작업을 마우스 오른쪽** 단추로 클릭하고 새로 **고침을** 클릭한 다음 직접 **실행** 작업(Windows 7 이상)을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="3cf64-154">Right-click **Scheduled tasks**, click **New**, and then click **Immediate Task** (At least Windows 7).</span></span> 

4. <span data-ttu-id="3cf64-155">작업 창이 열리면 일반 **탭으로** 이동됩니다. 보안 **옵션에서** 사용자 또는 **그룹 변경을 클릭하고** SYSTEM을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="3cf64-155">In the Task window that opens, go to the **General** tab. Under **Security options** click **Change User or Group** and type SYSTEM.</span></span> <span data-ttu-id="3cf64-156">이름 **확인을 클릭한** 다음 확인을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="3cf64-156">Click **Check Names** and then click OK.</span></span> <span data-ttu-id="3cf64-157">작업이 실행될 사용자 계정으로 NT AUTHORITY\SYSTEM이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="3cf64-157">NT AUTHORITY\SYSTEM appears as the user account the task will run as.</span></span> 

5. <span data-ttu-id="3cf64-158">사용자가 **로그온되어** 있는지 여부에 따라  실행을 선택하고 가장 높은 권한으로 실행 확인란을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="3cf64-158">Select **Run whether user is logged on or not** and check the **Run with highest privileges** check box.</span></span> 

6. <span data-ttu-id="3cf64-159">작업 **탭으로** 이동하여 새로 고기를 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="3cf64-159">Go to the **Actions** tab and click **New**.</span></span> <span data-ttu-id="3cf64-160">작업 **필드에서 프로그램** 시작이 선택되어 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="3cf64-160">Ensure that **Start a program** is selected in the Action field.</span></span> <span data-ttu-id="3cf64-161">다음을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="3cf64-161">Enter the following:</span></span> 

   `Action = "Start a program"`

   `Program/Script = C:\WINDOWS\system32\WindowsPowerShell\v1.0\powershell.exe`

   `Add Arguments (optional) = -ExecutionPolicy Bypass -command "& \\Path\To\Onboard-NonPersistentMachine.ps1"`

   <span data-ttu-id="3cf64-162">그런 다음 **확인을 선택하고** 열려 있는 GPMC 창을 닫습니다.</span><span class="sxs-lookup"><span data-stu-id="3cf64-162">Then select **OK** and close any open GPMC windows.</span></span>

#### <a name="scenario-3-onboarding-using-management-tools"></a><span data-ttu-id="3cf64-163">*시나리오 3: 관리 도구를 사용한 온보드*</span><span class="sxs-lookup"><span data-stu-id="3cf64-163">*Scenario 3: Onboarding using management tools*</span></span>

<span data-ttu-id="3cf64-164">관리 도구를 사용하여 컴퓨터를 관리하려면 Microsoft Endpoint Configuration Manager를 사용하여 장치를 온보드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3cf64-164">If you plan to manage your machines using a management tool, you can onboard devices with Microsoft Endpoint Configuration Manager.</span></span>

<span data-ttu-id="3cf64-165">자세한 내용은 Configuration Manager를 사용하여 [Windows 10 장치 온보드를 참조하세요.](configure-endpoints-sccm.md)</span><span class="sxs-lookup"><span data-stu-id="3cf64-165">For more information, see [Onboard Windows 10 devices using Configuration Manager](configure-endpoints-sccm.md).</span></span>

> [!WARNING]
> <span data-ttu-id="3cf64-166">공격 표면 감소 [](attack-surface-reduction.md)규칙을 사용하려면["PSExec](attack-surface-reduction.md#block-process-creations-originating-from-psexec-and-wmi-commands)및 WMI 명령에서 시작된 프로세스 만들기 차단" 규칙은 Microsoft Endpoint Configuration Manager를 통한 관리와 비호환적이기 때문에 사용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="3cf64-166">If you plan to use [Attack Surface reduction Rules](attack-surface-reduction.md), note that the rule “[Block process creations originating from PSExec and WMI commands](attack-surface-reduction.md#block-process-creations-originating-from-psexec-and-wmi-commands)" should not be used, because that rule is incompatible with management through Microsoft Endpoint Configuration Manager.</span></span> <span data-ttu-id="3cf64-167">이 규칙은 Configuration Manager 클라이언트가 올바르게 작동하기 위해 사용하는 WMI 명령을 차단합니다.</span><span class="sxs-lookup"><span data-stu-id="3cf64-167">The rule blocks WMI commands that the Configuration Manager client uses to function correctly.</span></span> 

> [!TIP]
> <span data-ttu-id="3cf64-168">장치를 온보드한 후 검색 테스트를 실행하여 장치가 서비스에 제대로 온보드되었는지 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3cf64-168">After onboarding the device, you can choose to run a detection test to verify that the device is properly onboarded to the service.</span></span> <span data-ttu-id="3cf64-169">자세한 내용은 새로 온보딩된 끝점 디바이스용 Microsoft Defender에서 검색 테스트 [실행을 참조하세요.](run-detection-test.md)</span><span class="sxs-lookup"><span data-stu-id="3cf64-169">For more information, see [Run a detection test on a newly onboarded Microsoft Defender for Endpoint device](run-detection-test.md).</span></span> 

#### <a name="tagging-your-machines-when-building-your-golden-image"></a><span data-ttu-id="3cf64-170">골든 이미지를 구축할 때 컴퓨터 태그 지정</span><span class="sxs-lookup"><span data-stu-id="3cf64-170">Tagging your machines when building your golden image</span></span> 

<span data-ttu-id="3cf64-171">온보더링의 일부로 Microsoft 보안 센터에서 WVD 컴퓨터를 보다 쉽게 차별화할 수 있도록 컴퓨터 태그를 설정하는 것을 고려할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3cf64-171">As part of your onboarding, you may want to consider setting a machine tag to can differentiate WVD machines more easily in the Microsoft Security Center.</span></span> <span data-ttu-id="3cf64-172">자세한 내용은 레지스트리 키 값을 설정하여 장치 태그 [추가를 참조하세요.](machine-tags.md#add-device-tags-by-setting-a-registry-key-value)</span><span class="sxs-lookup"><span data-stu-id="3cf64-172">For more information, see [Add device tags by setting a registry key value](machine-tags.md#add-device-tags-by-setting-a-registry-key-value).</span></span> 

#### <a name="other-recommended-configuration-settings"></a><span data-ttu-id="3cf64-173">기타 권장 구성 설정</span><span class="sxs-lookup"><span data-stu-id="3cf64-173">Other recommended configuration settings</span></span> 

<span data-ttu-id="3cf64-174">골든 이미지를 구축할 때 초기 보호 설정도 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3cf64-174">When building your golden image, you may want to configure initial protection settings as well.</span></span> <span data-ttu-id="3cf64-175">자세한 내용은 기타 권장 구성 [설정을 참조하세요.](configure-endpoints-gp.md#other-recommended-configuration-settings)</span><span class="sxs-lookup"><span data-stu-id="3cf64-175">For more information, see [Other recommended configuration settings](configure-endpoints-gp.md#other-recommended-configuration-settings).</span></span> 

<span data-ttu-id="3cf64-176">또한 FSlogix 사용자 프로필을 사용하는 경우 다음 파일을 항상 보호에서 제외하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="3cf64-176">Also, if you're using FSlogix user profiles, we recommend you exclude the following files from always-on protection:</span></span> 

<span data-ttu-id="3cf64-177">**파일 제외:**</span><span class="sxs-lookup"><span data-stu-id="3cf64-177">**Exclude Files:**</span></span> 

`%ProgramFiles%\FSLogix\Apps\frxdrv.sys`

`%ProgramFiles%\FSLogix\Apps\frxdrvvt.sys`

`%ProgramFiles%\FSLogix\Apps\frxccd.sys`

`%TEMP%\*.VHD`

`%TEMP%\*.VHDX`

`%Windir%\TEMP\*.VHD`

`%Windir%\TEMP\*.VHDX`

`\\storageaccount.file.core.windows.net\share\*\*.VHD`

`\\storageaccount.file.core.windows.net\share\*\*.VHDX`

<span data-ttu-id="3cf64-178">**프로세스 제외:**</span><span class="sxs-lookup"><span data-stu-id="3cf64-178">**Exclude Processes:**</span></span>

`%ProgramFiles%\FSLogix\Apps\frxccd.exe`

`%ProgramFiles%\FSLogix\Apps\frxccds.exe`

`%ProgramFiles%\FSLogix\Apps\frxsvc.exe`

#### <a name="licensing-requirements"></a><span data-ttu-id="3cf64-179">라이선스 요구 사항</span><span class="sxs-lookup"><span data-stu-id="3cf64-179">Licensing requirements</span></span> 

<span data-ttu-id="3cf64-180">라이선스에 대한 참고 사항: Windows 10 Enterprise 다중 세션을 사용하는 경우 요구 사항에 따라 모든 사용자가 끝점용 Microsoft Defender(사용자당), Windows Enterprise E5, Microsoft 365 보안 또는 Microsoft 365 E5를 통해 라이선스를 취득하도록 선택하거나 Azure Defender를 통해 VM을 라이선스가 부여하도록 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3cf64-180">Note on licensing: When using Windows 10 Enterprise multi-session, depending on your requirements, you can choose to either have all users licensed through Microsoft Defender for Endpoint (per user), Windows Enterprise E5, Microsoft 365 Security, or Microsoft 365 E5, or have the VM licensed through Azure Defender.</span></span>
<span data-ttu-id="3cf64-181">끝점용 Microsoft Defender의 라이선스 요구 사항은 라이선스 요구 [사항 에서 찾을 수 있습니다.](minimum-requirements.md#licensing-requirements)</span><span class="sxs-lookup"><span data-stu-id="3cf64-181">Licensing requirements for Microsoft Defender for endpoint can be found at: [Licensing requirements](minimum-requirements.md#licensing-requirements).</span></span>
