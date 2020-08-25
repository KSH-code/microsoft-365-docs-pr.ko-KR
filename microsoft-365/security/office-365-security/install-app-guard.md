---
title: 관리자를 위한 Application Guard for Office 365 (공용 미리 보기)
keywords: 응용 프로그램 보호, 보호, 격리, 격리 된 컨테이너, 하드웨어 격리
f1.keywords:
- NOCSH
ms.author: maccruz
author: schmurky
manager: dansimp
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.collection: M365-security-compliance
description: 하드웨어 기반 격리의 최신 버전을 다운로드 합니다. 악용 또는 악성 링크와 같은 현재 및 신흥 공격을 방지 하 여 직원의 생산성 및 기업 보안을 방해 하지 않도록 합니다.
ms.openlocfilehash: d0a89e8f8874c9ad298bf862384019b9e1ace0bf
ms.sourcegitcommit: 787b198765565d54ee73972f664bdbd5023d666b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/24/2020
ms.locfileid: "46867485"
---
# <a name="application-guard-for-office-public-preview-for-admins"></a><span data-ttu-id="f831b-105">관리자를 위한 Application Guard for Office (공용 미리 보기)</span><span class="sxs-lookup"><span data-stu-id="f831b-105">Application Guard for Office (public preview) for admins</span></span>


<span data-ttu-id="f831b-106">**적용 대상:** Word, Excel 및 PowerPoint for Microsoft 365, Windows 10 Enterprise</span><span class="sxs-lookup"><span data-stu-id="f831b-106">**Applies to:** Word, Excel, and PowerPoint for Microsoft 365, Windows 10 Enterprise</span></span>

>[!IMPORTANT]
><span data-ttu-id="f831b-107">일부 정보는 상업적으로 출시 되기 전에 크게 수정 될 수 있는 prereleased 제품과 관련 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f831b-107">Some information relates to a prereleased product which may be substantially modified before it's commercially released.</span></span> <span data-ttu-id="f831b-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span><span class="sxs-lookup"><span data-stu-id="f831b-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span></span>


<span data-ttu-id="f831b-109">Microsoft Defender Application Guard for Office (Application Guard for office)를 사용 하면 신뢰할 수 없는 파일이 신뢰할 수 있는 리소스에 액세스 하지 못하도록 방지 하 여 기업이 새로운 공격 으로부터 안전 하 게 보호 되도록 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f831b-109">Microsoft Defender Application Guard for Office (Application Guard for Office) helps prevent untrusted files from accessing trusted resources, keeping your enterprise safe from new and emerging attacks.</span></span> <span data-ttu-id="f831b-110">이 문서에서는 Office 용 응용 프로그램 보호를 미리 볼 장치를 설정 하는 관리자를 안내 합니다.</span><span class="sxs-lookup"><span data-stu-id="f831b-110">This article walks admins through setting up devices for a preview of Application Guard for Office.</span></span> <span data-ttu-id="f831b-111">장치에서 Office 용 Application Guard를 사용 하도록 설정 하는 시스템 요구 사항 및 설치 단계에 대 한 정보를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="f831b-111">It provides information about system requirements and installation steps to enable Application Guard for Office on a device.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="f831b-112">필수 구성 요소</span><span class="sxs-lookup"><span data-stu-id="f831b-112">Prerequisites</span></span>

### <a name="minimum-hardware-requirements"></a><span data-ttu-id="f831b-113">최소 하드웨어 요구 사항</span><span class="sxs-lookup"><span data-stu-id="f831b-113">Minimum hardware requirements</span></span>

* <span data-ttu-id="f831b-114">**CPU**: 64 비트, 4 코어 (실제 또는 가상), 가상화 확장 (Intel VT-x 또는 AMD-V), 핵심 i5가 동일 하거나 더 권장 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f831b-114">**CPU**: 64-bit, 4 cores (physical or virtual), virtualization extensions   (Intel VT-x OR AMD-V), Core i5 equivalent or higher recommended</span></span>
* <span data-ttu-id="f831b-115">**실제 메모리**: 8gb RAM</span><span class="sxs-lookup"><span data-stu-id="f831b-115">**Physical memory**: 8-GB RAM</span></span>
* <span data-ttu-id="f831b-116">**하드 디스크**: 시스템 드라이브에 10gb의 사용 가능한 공간 (SSD 권장)</span><span class="sxs-lookup"><span data-stu-id="f831b-116">**Hard disk**: 10 GB of free space on the system drive (SSD recommended)</span></span>

### <a name="minimum-software-requirements"></a><span data-ttu-id="f831b-117">최소 소프트웨어 요구 사항</span><span class="sxs-lookup"><span data-stu-id="f831b-117">Minimum software requirements</span></span>

* <span data-ttu-id="f831b-118">**Windows 10**: Windows 10 Enterprise Edition, 클라이언트 빌드 버전 2004 (20H1) 빌드 19041</span><span class="sxs-lookup"><span data-stu-id="f831b-118">**Windows 10**: Windows 10 Enterprise edition, Client Build version 2004 (20H1) build 19041</span></span>
* <span data-ttu-id="f831b-119">**Office**: Office 베타 채널 빌드 버전 2008 16.0.13212 이상</span><span class="sxs-lookup"><span data-stu-id="f831b-119">**Office**: Office Beta Channel Build version 2008 16.0.13212 or later</span></span>
* <span data-ttu-id="f831b-120">**업데이트 패키지**: Windows 10 누적 월별 보안 업데이트 [KB4566782](https://support.microsoft.com/help/4566782/windows-10-update-kb4566782)</span><span class="sxs-lookup"><span data-stu-id="f831b-120">**Update package**: Windows 10 cumulative monthly security updates [KB4566782](https://support.microsoft.com/help/4566782/windows-10-update-kb4566782)</span></span> 

<span data-ttu-id="f831b-121">시스템 요구 사항에 대 한 자세한 내용은 [Microsoft Defender Application Guard에 대 한 시스템 요구 사항을](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-application-guard/reqs-md-app-guard)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="f831b-121">For detailed system requirements, refer to [System requirements for Microsoft Defender Application Guard](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-application-guard/reqs-md-app-guard).</span></span> <span data-ttu-id="f831b-122">Office Insider Preview 빌드에 대 한 자세한 내용은 [Office 참가자 빌드 배포 시작](https://insider.office.com/business/deploy)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="f831b-122">To learn more about Office Insider Preview builds, refer to [Getting started on deploying Office Insider builds](https://insider.office.com/business/deploy).</span></span>

### <a name="licensing-requirements"></a><span data-ttu-id="f831b-123">라이선스 요구 사항</span><span class="sxs-lookup"><span data-stu-id="f831b-123">Licensing requirements</span></span>
* <span data-ttu-id="f831b-124">Microsoft 365 E5 또는 Microsoft 365 E5 보안</span><span class="sxs-lookup"><span data-stu-id="f831b-124">Microsoft 365 E5 or Microsoft 365 E5 Security</span></span>

## <a name="deploy-application-guard-for-office"></a><span data-ttu-id="f831b-125">Office 용 응용 프로그램 보호 배포</span><span class="sxs-lookup"><span data-stu-id="f831b-125">Deploy Application Guard for Office</span></span>

### <a name="enable-application-guard-for-office"></a><span data-ttu-id="f831b-126">Office 용 응용 프로그램 보호 사용</span><span class="sxs-lookup"><span data-stu-id="f831b-126">Enable Application Guard for Office</span></span>

1.  <span data-ttu-id="f831b-127">**Windows 10 누적 월별 보안 업데이트 KB4566782**를 다운로드 하 여 설치 합니다.</span><span class="sxs-lookup"><span data-stu-id="f831b-127">Download and install **Windows 10 cumulative monthly security updates KB4566782**.</span></span> 

2. <span data-ttu-id="f831b-128">[**Office 기능 지원 패키지를 다운로드 하 고 응용 프로그램 보호를**](https://download.microsoft.com/download/e/4/c/e4c1180a-fcff-462a-8324-4151c44973a8/Windows%20Preview%20-%20WDAG%20Office%20070920%2001.msi)설치 합니다.</span><span class="sxs-lookup"><span data-stu-id="f831b-128">Download and install [**Application Guard for Office Feature enablement package**](https://download.microsoft.com/download/e/4/c/e4c1180a-fcff-462a-8324-4151c44973a8/Windows%20Preview%20-%20WDAG%20Office%20070920%2001.msi).</span></span> <span data-ttu-id="f831b-129">이 패키지는 **컴퓨터 구성 \ 관리 템플릿**아래에 "KB4559004 Issue 001 Preview" 라는 그룹 정책을 설치 합니다.</span><span class="sxs-lookup"><span data-stu-id="f831b-129">This package installs a group policy called "KB4559004 Issue 001 Preview" under **Computer Configuration\Administrative Templates**.</span></span> <span data-ttu-id="f831b-130">이 그룹 정책을 **사용**으로 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="f831b-130">Set this group policy  to **Enabled**.</span></span>
     <span data-ttu-id="f831b-131">![로컬 그룹 정책 편집기](../../media/ag01-deploy.png)</span><span class="sxs-lookup"><span data-stu-id="f831b-131">![Local Group Policy Editor](../../media/ag01-deploy.png)</span></span>

     ![KB4559004 Issue 001 Preview](../../media/ag02-deploy.png)

    <span data-ttu-id="f831b-133">다음과 같은 reg 키를 직접 설정할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f831b-133">You can also directly set the following reg keys:</span></span> 
    
    ```
    reg add HKLM\SYSTEM\CurrentControlSet\Policies\Microsoft\FeatureManagement\Overrides /v 3457697930 /t REG_DWORD /d 1 
    ```
    ```
    reg add HKLM\SYSTEM\CurrentControlSet\Policies\Microsoft\FeatureManagement\Overrides /v 94539402 /t REG_DWORD /d 1 
    ```
    <span data-ttu-id="f831b-134">그런 다음 다음 PowerShell 명령을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="f831b-134">Then, run this PowerShell command:</span></span> 
    
    ```powershell
    Get-ScheduledTask -TaskName "ReconcileFeatures" -TaskPath "\Microsoft\Windows\Flighting\FeatureConfig\" | Start-ScheduledTask 
    ```

3.  <span data-ttu-id="f831b-135">Windows 기능에서 **Microsoft Defender Application Guard** 를 선택 하 고 **확인을**선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="f831b-135">Select **Microsoft Defender Application Guard** under Windows Features and select **OK**.</span></span> <span data-ttu-id="f831b-136">응용 프로그램 보호 기능을 사용 하도록 설정 하면 시스템을 다시 부팅 하 라는 메시지가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f831b-136">Enabling the Application Guard feature will prompt a system reboot.</span></span> <span data-ttu-id="f831b-137">지금 또는 4 단계를 수행한 후에 다시 부팅 하도록 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f831b-137">You can choose to reboot now or after step 4.</span></span>

    ![AG가 표시 된 Windows 기능 대화 상자](../../media/ag03-deploy.png)
    
    <span data-ttu-id="f831b-139">다음 PowerShell 명령을 관리자 권한으로 실행 하 여이 기능을 사용 하도록 설정할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f831b-139">The feature can also be enabled by running the following PowerShell command as administrator:</span></span> 

    ```powershell
    Enable-WindowsOptionalFeature -online -FeatureName Windows-Defender-ApplicationGuard 
    ```

4.  <span data-ttu-id="f831b-140">**컴퓨터 구성 \\ 관리 템플릿 \\ Windows 구성 요소 \\ microsoft defender Application Guard**에 있는 관리 되는 모드 그룹 정책에서 microsoft defender application guard를 찾아보십시오.</span><span class="sxs-lookup"><span data-stu-id="f831b-140">Look for the Microsoft Defender Application Guard in Managed Mode group policy located at **Computer Configuration\\Administrative Templates\\Windows Components\\Microsoft Defender Application Guard**.</span></span> <span data-ttu-id="f831b-141">옵션 아래의 값을 **2** 또는 **3** 으로 설정 하 고 **확인** 또는 **적용**을 선택 하 여이 정책을 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="f831b-141">Turn this policy on by setting the value under Options as **2** or **3** then selecting **OK** or **Apply**.</span></span>

    ![관리 모드에서 AG 설정](../../media/ag04-deploy.png)
  
    <span data-ttu-id="f831b-143">또는 해당 하는 CSP 정책을 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f831b-143">Alternatively, you can set the corresponding CSP policy:</span></span> 

    <span data-ttu-id="f831b-144">OMA-URI: **./Device/Vendor/MSFT/WindowsDefenderApplicationGuard/Settings/AllowWindowsDefenderApplicationGuard** 
    </span><span class="sxs-lookup"><span data-stu-id="f831b-144">OMA-URI: **./Device/Vendor/MSFT/WindowsDefenderApplicationGuard/Settings/AllowWindowsDefenderApplicationGuard** 
    </span></span><br><span data-ttu-id="f831b-145">데이터 형식: **정수** 
</span><span class="sxs-lookup"><span data-stu-id="f831b-145">Data type: **Integer** 
</span></span><br><span data-ttu-id="f831b-146">값: **2**</span><span class="sxs-lookup"><span data-stu-id="f831b-146">Value: **2**</span></span>


5.  <span data-ttu-id="f831b-147">시스템을 재부팅 합니다.</span><span class="sxs-lookup"><span data-stu-id="f831b-147">Reboot the system.</span></span>

### <a name="set-diagnostics--feedback-to-send-full-data"></a><span data-ttu-id="f831b-148">전체 데이터를 보낼 수 있도록 진단 & 피드백 설정</span><span class="sxs-lookup"><span data-stu-id="f831b-148">Set Diagnostics & feedback to send full data</span></span>

<span data-ttu-id="f831b-149">이 단계를 수행 하면 문제를 식별 하 고 해결 하는 데 필요한 데이터가 Microsoft에 도달 하 게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f831b-149">This step ensures that the data necessary to identify and fix problems is reaching Microsoft.</span></span> <span data-ttu-id="f831b-150">다음 단계에 따라 Windows 장치에서 진단을 사용 하도록 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="f831b-150">Follow these steps to enable diagnostics on your Windows device:</span></span>

1.  <span data-ttu-id="f831b-151">시작 메뉴에서 **설정을** 엽니다.</span><span class="sxs-lookup"><span data-stu-id="f831b-151">Open **Settings** from the Start menu.</span></span>

    ![시작 메뉴](../../media/ag05-diagnostic.png)

2.  <span data-ttu-id="f831b-153">**Windows 설정**에서 **개인 정보**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="f831b-153">On **Windows Settings**, select **Privacy**.</span></span>

    ![Windows 설정 메뉴](../../media/ag06-diagnostic.png)

3.  <span data-ttu-id="f831b-155">개인 정보 아래에서 **진단 & 피드백** 을 선택 하 고 **선택적 진단 데이터**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="f831b-155">Under Privacy, select **Diagnostics & feedback** and select **Optional diagnostic data**.</span></span>

    ![진단 및 피드백 메뉴](../../media/ag07a-diagnostic.png)

<span data-ttu-id="f831b-157">Windows 진단 설정 구성에 대 한 자세한 내용은 [조직에서 windows 진단 데이터 구성을](https://docs.microsoft.com/windows/privacy/configure-windows-diagnostic-data-in-your-organization#enterprise-management)참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="f831b-157">For more on configuring Windows diagnostic settings, refer to [Configuring Windows diagnostic data in your organization](https://docs.microsoft.com/windows/privacy/configure-windows-diagnostic-data-in-your-organization#enterprise-management).</span></span>

### <a name="confirm-that-application-guard-for-office-is-enabled-and-working"></a><span data-ttu-id="f831b-158">Office 용 Application Guard가 사용 하도록 설정 및 작동 하는지 확인</span><span class="sxs-lookup"><span data-stu-id="f831b-158">Confirm that Application Guard for Office is enabled and working</span></span>

<span data-ttu-id="f831b-159">Office 용 응용 프로그램 보호가 사용 하도록 설정 되어 있는지 확인 하기 전에 정책이 배포 된 장치에서 Word, Excel 또는 PowerPoint를 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="f831b-159">Before confirming that the Application Guard for Office is enabled, launch Word, Excel, or PowerPoint on a device where the policies have been deployed.</span></span> <span data-ttu-id="f831b-160">Office가 정품 인증 되었는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="f831b-160">Make sure Office is activated.</span></span> <span data-ttu-id="f831b-161">먼저 회사 id를 사용 하 여 Office 제품을 정품 인증 해야 할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f831b-161">You may need to use your work identity to activate the Office product first.</span></span>

<span data-ttu-id="f831b-162">이제 Office 용 Application Guard가 사용 하도록 설정 되어 있는지 확인 하려면 Word, Excel 또는 PowerPoint를 실행 하 고 신뢰할 수 없는 문서를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="f831b-162">To confirm that Application Guard for Office is now enabled, launch Word, Excel, or PowerPoint and open an untrusted document.</span></span> <span data-ttu-id="f831b-163">예를 들어 인터넷에서 다운로드 한 문서를 열거나 조직 외부의 사용자가 보낸 전자 메일 첨부 파일을 열 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f831b-163">For example, you can open a document downloaded from the internet or an email attachment from someone outside your organization.</span></span>

<span data-ttu-id="f831b-164">신뢰할 수 없는 파일을 처음 실행할 때 아래와 같은 Office 시작 화면이 표시 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f831b-164">On the first launch of an untrusted file, you may see an Office splash screen like the one below.</span></span> <span data-ttu-id="f831b-165">Office 용 Application Guard가 활성화 되 고 파일이 열리는 동안 잠시 동안 표시 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f831b-165">It might show for some time while Application Guard for Office is being activated and the file is being opened.</span></span> <span data-ttu-id="f831b-166">이후에 신뢰할 수 없는 파일을 시작 하는 것이 더 빠릅니다.</span><span class="sxs-lookup"><span data-stu-id="f831b-166">Subsequent launches of untrusted files should be faster.</span></span>

![Office 앱 시작 화면](../../media/ag08-confirm.png)


<span data-ttu-id="f831b-168">파일이 열릴 때 파일에는 Office 용 Application Guard에서 파일을 연 몇 가지 시각적 표시기가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f831b-168">Upon being opened, the file should display a few visual indicators that the file was opened inside Application Guard for Office:</span></span>

* <span data-ttu-id="f831b-169">리본 메뉴의 설명선</span><span class="sxs-lookup"><span data-stu-id="f831b-169">A callout in the ribbon</span></span>

    ![Small App 보호 메모를 보여 주는 문서 파일](../../media/ag09-confirm.png)
* <span data-ttu-id="f831b-171">작업 표시줄의 방패를 포함 하는 응용 프로그램 아이콘</span><span class="sxs-lookup"><span data-stu-id="f831b-171">The application icon with a shield in the taskbar</span></span> 

    ![작업 표시줄의 아이콘](../../media/ag12-limitations.png)



## <a name="configure-application-guard-for-office"></a><span data-ttu-id="f831b-173">Office 용 응용 프로그램 보호 구성</span><span class="sxs-lookup"><span data-stu-id="f831b-173">Configure Application Guard for Office</span></span>
<span data-ttu-id="f831b-174">Office는 다음 정책을 지원 하 여 Office 용 응용 프로그램 보호 기능을 구성할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="f831b-174">Office supports the following policies to enable you to configure the capabilities of Application Guard for Office.</span></span> <span data-ttu-id="f831b-175">이러한 정책은 그룹 정책 또는 Office 클라우드 정책 서비스를 통해 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f831b-175">These policies can be configured through Group policies or through the Office cloud policy service.</span></span> 

>[!NOTE] 
> <span data-ttu-id="f831b-176">이러한 정책은 곧 제공 될 예정입니다.</span><span class="sxs-lookup"><span data-stu-id="f831b-176">These policies will become available soon.</span></span>
><span data-ttu-id="f831b-177">또한 이러한 정책을 구성 하면 Office 용 Application Guard에서 열린 파일에 대 한 일부 기능을 사용 하지 않도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f831b-177">Also, configuring these policies can disable some functionalities for files opened in Application Guard for Office.</span></span>

| <span data-ttu-id="f831b-178">정책</span><span class="sxs-lookup"><span data-stu-id="f831b-178">Policy</span></span>                                                                          | <span data-ttu-id="f831b-179">설명</span><span class="sxs-lookup"><span data-stu-id="f831b-179">Description</span></span>                                                                                                                                                                                                                                                                                             |
|---------------------------------------------------------------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| <span data-ttu-id="f831b-180">Office 용 Application Guard 사용 안 함</span><span class="sxs-lookup"><span data-stu-id="f831b-180">Disable Application Guard for Office</span></span>                                            | <span data-ttu-id="f831b-181">이 정책을 사용 하도록 설정 하면 Word, Excel 및 PowerPoint가 Office 용 응용 프로그램 보호 대신 보호 된 보기 격리 컨테이너를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="f831b-181">Enabling this policy will force Word, Excel, and PowerPoint to use the Protected View isolation container instead of Application Guard for Office.</span></span> <span data-ttu-id="f831b-182">이 정책을 사용 하 여에 지에 문제가 있는 경우 Office 용 Application Guard를 일시적으로 사용 하지 않도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f831b-182">This policy can be used to temporarily disable Application Guard for Office when there are issues in leaving it enabled for Edge.</span></span>                                  |
| <span data-ttu-id="f831b-183">Application Guard에서 연 문서에 대해 복사/붙여넣기 사용 안 함</span><span class="sxs-lookup"><span data-stu-id="f831b-183">Disable copy/paste for documents opened in Application Guard</span></span>                    | <span data-ttu-id="f831b-184">이 정책을 사용 하도록 설정 하면 사용자가 Office 용 Application Guard에서 연 문서의 콘텐츠를 복사 하 여 해당 문서 외부에서 열린 문서에 붙여 넣을 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="f831b-184">Enabling this policy will prevent a user from copying and pasting content from a document opened in Application Guard for Office to a document opened outside it.</span></span>                                                                                                                                   |
| <span data-ttu-id="f831b-185">사용자가 파일에서 Application Guard 보호를 제거 하지 못하도록 차단</span><span class="sxs-lookup"><span data-stu-id="f831b-185">Prevent users from removing Application Guard protection on files</span></span>               | <span data-ttu-id="f831b-186">이 정책을 사용 하면 응용 프로그램 보호 기능을 사용 하지 않도록 설정 하거나 응용 프로그램 보호 외부에서 파일을 열 수 있는 옵션 (Office 응용 프로그램 환경 내)이 제거 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f831b-186">Enabling this policy will remove the option (within the Office application experience) to disable Application Guard protection or open a file outside Application Guard.</span></span> <br><br><span data-ttu-id="f831b-187">**참고:** 사용자는 파일에서 웹 표시 속성을 수동으로 제거 하거나 문서를 신뢰할 수 있는 위치로 이동 하 여이 정책을 계속 무시할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f831b-187">**Note:** Users can still bypass this policy by manually removing the mark-of-the-web property from the file or by moving a document to a Trusted location.</span></span> |
| <span data-ttu-id="f831b-188">Application Guard에서 연 문서에서 인쇄 제한</span><span class="sxs-lookup"><span data-stu-id="f831b-188">Restrict printing from documents opened in Application Guard</span></span>                    | <span data-ttu-id="f831b-189">이 정책을 사용 하면 사용자가 Office 용 Application Guard에서 연 파일에서 인쇄할 수 있는 프린터가 제한 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f831b-189">Enabling this policy will limit printers a user can print to from a file opened in Application Guard for Office.</span></span> <span data-ttu-id="f831b-190">예를 들어이 정책을 사용 하 여 사용자가 PDF로만 인쇄 하도록 제한할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f831b-190">For example, you can use this policy to restrict users to only print to PDF.</span></span>                              |
| <span data-ttu-id="f831b-191">Application Guard에서 열린 문서에 대해 카메라 및 마이크 액세스 끄기</span><span class="sxs-lookup"><span data-stu-id="f831b-191">Turn off camera and microphone access for documents opened in Application Guard</span></span> | <span data-ttu-id="f831b-192">이 정책을 사용 하면 Office 용 응용 프로그램 보호 내의 카메라 및 마이크에 대 한 Office 액세스가 제거 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f831b-192">Enabling this policy will remove Office access to Camera and Microphone inside Application Guard for Office.</span></span>                                                                                                                                                                                                     |
>[!NOTE] 
><span data-ttu-id="f831b-193">다음 정책을 적용 하려면 사용자가 로그 오프 하 고 Windows에 다시 로그인 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f831b-193">The following policies will require the user to log off and re-login to Windows to take effect:</span></span>
> 
> *  <span data-ttu-id="f831b-194">Application Guard에서 연 문서에 대해 복사/붙여넣기 사용 안 함</span><span class="sxs-lookup"><span data-stu-id="f831b-194">Disable copy/paste for documents opened in Application Guard</span></span>
>*  <span data-ttu-id="f831b-195">Application Guard에서 열린 문서에 대해 인쇄 제한</span><span class="sxs-lookup"><span data-stu-id="f831b-195">Restrict printing for documents opened in Application Guard</span></span>
> *  <span data-ttu-id="f831b-196">Application Guard에서 열린 문서에 대 한 카메라 및 마이크 액세스 끄기</span><span class="sxs-lookup"><span data-stu-id="f831b-196">Turn off camera and mic access to documents opened in Application Guard</span></span>


## <a name="submit-feedback"></a><span data-ttu-id="f831b-197">의견 제출</span><span class="sxs-lookup"><span data-stu-id="f831b-197">Submit feedback</span></span>

### <a name="submit-feedback-via-feedback-hub"></a><span data-ttu-id="f831b-198">피드백 허브를 통해 피드백 제출</span><span class="sxs-lookup"><span data-stu-id="f831b-198">Submit feedback via Feedback Hub</span></span>

<span data-ttu-id="f831b-199">Office 용 응용 프로그램 보호를 시작할 때 문제가 발생 하면 피드백 허브를 통해 피드백을 제출 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="f831b-199">If you encounter any issues when launching Application Guard for Office, you are encouraged to submit your feedback via Feedback Hub:</span></span>

1.  <span data-ttu-id="f831b-200">**의견 허브 앱** 을 열고 로그인 합니다.</span><span class="sxs-lookup"><span data-stu-id="f831b-200">Open the **Feedback Hub app** and sign in.</span></span>

2.  <span data-ttu-id="f831b-201">Application Guard를 시작 하는 동안 오류 대화 상자가 나타나면 오류 대화 상자에서 **Microsoft에 보고** 를 선택 하 여 새 피드백 제출을 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="f831b-201">If you get an error dialog while launching Application Guard, select **Report to Microsoft** in the error dialog to start a new feedback submission.</span></span> <span data-ttu-id="f831b-202">그렇지 않은 경우로 이동 하 여 <https://aka.ms/wdagoffice-fb> 응용 프로그램 보호를 위한 올바른 범주를 선택한 다음 + 오른쪽 상단에 **새 의견 추가** 를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="f831b-202">Otherwise, navigate to <https://aka.ms/wdagoffice-fb> to select the correct category for Application Guard, then select **+ Add new feedback** near the top right.</span></span>

3.  <span data-ttu-id="f831b-203">사용자 의견을 **요약** 상자에 입력 합니다 (아직 채워져 있지 않은 경우).</span><span class="sxs-lookup"><span data-stu-id="f831b-203">Fill in the **Summarize your feedback** box if it isn’t already filled in for you.</span></span>

4.  <span data-ttu-id="f831b-204">발생 한 문제에 대 한 자세한 설명과, 수행한 단계를 **자세히 설명 하** 고 **다음**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="f831b-204">Fill in the **Explain in more detail** box with a detailed description of the issue you experienced and what steps you took, then select **Next**.</span></span>

5.  <span data-ttu-id="f831b-205">문제 옆에 있는 거품을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="f831b-205">Select the bubble next to Problem.</span></span> <span data-ttu-id="f831b-206">선택한 범주가 **보안 및 개인 정보 \> Microsoft Defender application Guard**인지 확인 하 고 **다음**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="f831b-206">Make sure the category selected is **Security and Privacy \> Microsoft Defender Application Guard – Office**, then select **Next**.</span></span>

6.  <span data-ttu-id="f831b-207">**새 의견**을 선택한 후 **다음**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="f831b-207">Select **New feedback**, then **Next**.</span></span>

7.  <span data-ttu-id="f831b-208">문제에 대 한 추적을 수집 합니다.</span><span class="sxs-lookup"><span data-stu-id="f831b-208">Collect traces about the issue:</span></span>

    1. <span data-ttu-id="f831b-209">**내 문제 다시 만들기** 타일을 확장 합니다.</span><span class="sxs-lookup"><span data-stu-id="f831b-209">Expand the **Recreate my problem** tile.</span></span>

    2.  <span data-ttu-id="f831b-210">응용 프로그램 보호가 실행 되는 동안 문제가 발생 하면 Application Guard 인스턴스를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="f831b-210">If the issue you’re experiencing occurs while Application Guard is running, open an Application Guard instance.</span></span> <span data-ttu-id="f831b-211">이렇게 하면 응용 프로그램 보호 컨테이너 내에서 추가 추적을 수집할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f831b-211">Doing this allows additional traces to be collected from within the Application Guard container.</span></span>

    3.  <span data-ttu-id="f831b-212">**녹음 시작** 을 선택 하 고 타일이 회전을 중지할 때까지 기다린 후 *녹음 중지*를 말합니다.</span><span class="sxs-lookup"><span data-stu-id="f831b-212">Select **Start recording** and wait for the tile to stop spinning and say *Stop recording*.</span></span>

    4.  <span data-ttu-id="f831b-213">Application Guard에서 문제를 완전히 재현 합니다.</span><span class="sxs-lookup"><span data-stu-id="f831b-213">Fully reproduce the issue with Application Guard.</span></span> <span data-ttu-id="f831b-214">여기에는 응용 프로그램 보호 인스턴스를 시작 하 고 오류가 발생할 때까지 기다리거나 실행 중인 Application Guard 인스턴스에서 문제를 재현할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f831b-214">This might include attempting to launch an Application Guard instance and waiting until it fails, or reproducing an issue in a running Application Guard instance.</span></span>

    5.  <span data-ttu-id="f831b-215">**녹음 중지** 타일을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="f831b-215">Select the **Stop recording** tile.</span></span>

    6.  <span data-ttu-id="f831b-216">제출 후 몇 분까지 실행 되는 모든 응용 프로그램 보호 인스턴스를 열린 상태로 유지 하 여 컨테이너 진단을도 수집할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="f831b-216">Keep any running Application Guard instance/s open, even until a few minutes after submission, so that container diagnostics can also be collected.</span></span>

8.  <span data-ttu-id="f831b-217">문제와 관련 된 모든 관련 스크린샷 또는 파일을 첨부 합니다.</span><span class="sxs-lookup"><span data-stu-id="f831b-217">Attach any relevant screenshots or files related to the problem.</span></span>

9.  <span data-ttu-id="f831b-218">**전송**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="f831b-218">Select **Submit**.</span></span>



### <a name="submit-feedback-via-office-customer-voice"></a><span data-ttu-id="f831b-219">Office 고객 음성을 통해 사용자 의견 제출</span><span class="sxs-lookup"><span data-stu-id="f831b-219">Submit feedback via Office Customer Voice</span></span>

<span data-ttu-id="f831b-220">Office 문서를 Application Guard에서 열면 문제가 발생 하는 경우 Office 내에서 사용자 의견을 제출할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f831b-220">You may also submit feedback from within Office if the issue happens when Office documents are opened in Application Guard.</span></span> <span data-ttu-id="f831b-221">의견을 제출 하려면 [Office 참가자](https://insider.office.com/handbook) 소개 서를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="f831b-221">Refer to the [Office Insider Handbook](https://insider.office.com/handbook) for submitting feedback.</span></span>

## <a name="integration-with-microsoft-defender-atp-and-office-atp"></a><span data-ttu-id="f831b-222">Microsoft Defender ATP 및 Office ATP와의 통합</span><span class="sxs-lookup"><span data-stu-id="f831b-222">Integration with Microsoft Defender ATP and Office ATP</span></span>

<span data-ttu-id="f831b-223">Office 용 application Guard는 Microsoft의 ATP (고급 위협 보호)와 통합 되어 격리 된 환경에서 악의적인 작업에 대 한 모니터링 및 경고를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="f831b-223">Application Guard for Office is integrated with Microsoft Defender Advance Threat Protection (ATP) to provide monitoring and alerting on malicious activity happening in the isolated environment.</span></span>

<span data-ttu-id="f831b-224">Microsoft Defender ATP는 엔터프라이즈 네트워크가 고급 위협에 대해 예방, 감지, 조사 및 대응 하는 데 도움이 되는 보안 플랫폼입니다.</span><span class="sxs-lookup"><span data-stu-id="f831b-224">Microsoft Defender ATP is a security platform designed to help enterprise networks prevent, detect, investigate, and respond to advanced threats.</span></span> <span data-ttu-id="f831b-225">이 플랫폼에 대 한 자세한 내용을 보려면 [Microsoft Defender Advanced Threat Protection](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp) 페이지를 방문 하세요.</span><span class="sxs-lookup"><span data-stu-id="f831b-225">For more details about this platform, visit the [Microsoft Defender Advanced Threat Protection](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp) page.</span></span> <span data-ttu-id="f831b-226">이 플랫폼의 온 보 딩 장치에 대 한 자세한 내용은 [온보드 장치에서 Microsoft DEFENDER ATP 서비스에](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/onboard-configure)대해 알아보세요.</span><span class="sxs-lookup"><span data-stu-id="f831b-226">Learn more about onboarding devices to this platform at [Onboard devices to the Microsoft Defender ATP service](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/onboard-configure).</span></span>

<span data-ttu-id="f831b-227">Microsoft Defender ATP와 함께 작동 하도록 Office 365 ATP를 구성할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f831b-227">You can also configure Office 365 ATP to work with Microsoft Defender ATP.</span></span> <span data-ttu-id="f831b-228">[Office 365 ATP와 Microsoft DEFENDER Atp 통합](https://docs.microsoft.com/microsoft-365/security/office-365-security/integrate-office-365-ti-with-wdatp?view=o365-worldwide)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="f831b-228">Refer to [Integrate Office 365 ATP with Microsoft Defender ATP](https://docs.microsoft.com/microsoft-365/security/office-365-security/integrate-office-365-ti-with-wdatp?view=o365-worldwide).</span></span>

## <a name="limitations-and-considerations"></a><span data-ttu-id="f831b-229">제한 및 고려 사항</span><span class="sxs-lookup"><span data-stu-id="f831b-229">Limitations and considerations</span></span>

* <span data-ttu-id="f831b-230">Office 용 application Guard는 신뢰할 수 없는 문서와 트러스트 된 회사 리소스, 인트라넷, 사용자의 id 및 컴퓨터에 있는 임의의 파일에 액세스 하는 기능을 격리 하는 제한 모드입니다.</span><span class="sxs-lookup"><span data-stu-id="f831b-230">Application Guard for Office is a restricted mode that isolates untrusted documents from accessing trusted corporate resources, intranet, the user's identity, and arbitrary files present on the computer.</span></span> <span data-ttu-id="f831b-231">따라서 사용자가 디스크에 있는 로컬 파일에서 그림을 삽입 하는 등 해당 액세스에 대 한 종속성이 있는 기능에 액세스 하려고 하면 오류가 발생 하 고 아래와 같은 메시지가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f831b-231">As a result, if a user tries to access a feature that has a dependency on such access, for example, inserting a picture from a local file on disk, it will fail and produce a prompt like the one below.</span></span> <span data-ttu-id="f831b-232">신뢰할 수 없는 문서에서 트러스트 된 리소스에 액세스할 수 있도록 하려면 사용자가 문서에서 Application Guard 보호를 제거 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f831b-232">To enable an untrusted document to access trusted resources, users must remove Application Guard protection from the document.</span></span>

    ![안전 하 게 유지 하는 데 도움이 되는 대화 상자는 사용할 수 없습니다.](../../media/ag10-limitations.png)

    >[!NOTE]    
    ><span data-ttu-id="f831b-234">파일 및 해당 원본 또는 출처를 신뢰 하는 경우에만 보호를 제거 하도록 사용자에 게 알립니다.</span><span class="sxs-lookup"><span data-stu-id="f831b-234">Advise users to only remove protection if they trust the file and its source or where it came from.</span></span>

* <span data-ttu-id="f831b-235">Office 용 Application Guard에서 매크로 및 ActiveX 컨트롤과 같은 문서의 활성 콘텐츠를 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="f831b-235">Active content in documents like macros and ActiveX controls are disabled in Application Guard for Office.</span></span> <span data-ttu-id="f831b-236">사용자가 활성 콘텐츠를 사용 하도록 하려면 Application Guard 보호를 제거 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f831b-236">Users need to remove Application Guard protection to enable active content.</span></span>

* <span data-ttu-id="f831b-237">네트워크 공유에서 열린 신뢰할 수 없는 파일 또는 OneDrive에서 공유 된 파일, 비즈니스용 OneDrive 또는 다른 조직에서 SharePoint Online은 Application Guard에서 읽기 전용으로 열립니다.</span><span class="sxs-lookup"><span data-stu-id="f831b-237">Untrusted files opened from network shares or files shared from OneDrive, OneDrive for Business, or SharePoint Online from a different organization open as read-only in Application Guard.</span></span> <span data-ttu-id="f831b-238">사용자는 이러한 파일의 로컬 복사본을 저장 하 여 계속 해 서 컨테이너에서 작업 하거나 원본 파일을 직접 사용 하도록 보호 기능을 제거할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f831b-238">Users can save a local copy of such files to continue working in the container or remove protection to directly work with the original file.</span></span>

* <span data-ttu-id="f831b-239">IRM (정보 권한 관리)으로 보호 되는 파일은 제한 된 보기에서 계속 열립니다.</span><span class="sxs-lookup"><span data-stu-id="f831b-239">Files that are protected by Information Rights Management (IRM) continue to   open in Protected View.</span></span>
* <span data-ttu-id="f831b-240">Office 용 Application Guard에서 Office 응용 프로그램에 대 한 모든 사용자 지정은 사용자가 로그 오프 한 후 다시 로그인 하거나 장치를 부팅 한 후에 유지 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="f831b-240">Any customizations to Office applications in Application Guard for Office will not persist after a user logs off and logs back in or reboots the device.</span></span> 

* <span data-ttu-id="f831b-241">UIA framework를 사용 하는 접근성 도구 에서만 Office 용 Application Guard에서 연 파일에 대 한 액세스 가능 환경을 제공할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f831b-241">Only Accessibility tools that use the UIA framework can provide an accessible experience for files opened in Application Guard for Office.</span></span>

* <span data-ttu-id="f831b-242">설치 후 응용 프로그램 보호를 처음 시작할 때 네트워크 연결이 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="f831b-242">Network connectivity is required for the first launch of Application Guard after installation.</span></span> <span data-ttu-id="f831b-243">이는 응용 프로그램 보호를 통해 라이선스의 유효성을 검사 하는 데 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="f831b-243">This is required for Application Guard to validate the license.</span></span>
* <span data-ttu-id="f831b-244">문서 정보 섹션에서 *마지막으로 수정한 사람* 속성은 사용자로 서 Wdag유틸리티 계정을 표시할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f831b-244">In the document's info section, the *Last Modified By* property may display WDAGUtilityAccount as the user.</span></span> <span data-ttu-id="f831b-245">데스크톱 사용자의 id가 Application Guard 컨테이너 내에서 공유 되지 않는 경우 Application Guard에 구성 된 익명 사용자입니다.</span><span class="sxs-lookup"><span data-stu-id="f831b-245">This is the anonymous user configured in Application Guard given that the desktop user's identity is not shared inside the Application Guard container.</span></span> 

## <a name="performance-optimizations-for-application-guard"></a><span data-ttu-id="f831b-246">응용 프로그램 보호에 대 한 성능 최적화</span><span class="sxs-lookup"><span data-stu-id="f831b-246">Performance optimizations for Application Guard</span></span> 

<span data-ttu-id="f831b-247">이 섹션에서는 Office 용 Application Guard에서 사용 되는 성능 최적화의 개요를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="f831b-247">This section provides an overview of the performance optimizations used in Application Guard for Office.</span></span> <span data-ttu-id="f831b-248">이 정보는 관리자가 응용 프로그램 가드가 사용 하도록 설정 된 경우 Office의 성능과 전체 시스템에 관련 된 사용자의 보고서를 진단 하는 데 도움이 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f831b-248">This information can help administrators diagnose reports from users related to the performance of Office or the overall system when Application Guard is enabled.</span></span> 

<span data-ttu-id="f831b-249">Application Guard는 가상화 된 컨테이너를 사용 하 여 신뢰할 수 없는 문서를 시스템에서 분리 합니다.</span><span class="sxs-lookup"><span data-stu-id="f831b-249">Application Guard uses a virtualized container to isolate untrusted documents away from the system.</span></span> <span data-ttu-id="f831b-250">컨테이너를 만들고 응용 프로그램 보호 컨테이너를 설정 하 여 Office 문서를 열도록 하면 사용자가 신뢰할 수 없는 문서를 열 때 사용자 환경에 부정적인 영향을 줄 수 있는 성능 오버 헤드가 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="f831b-250">The process of creating a container and setting up the Application Guard container to open Office documents has a performance overhead that might negatively impact user experience when users open an  untrusted document.</span></span> 


<span data-ttu-id="f831b-251">사용자에 게 예상 되는 파일 열기 환경을 제공 하기 위해 응용 프로그램 가드는 시스템에서 다음 휴리스틱이 충족 될 때 논리를 사용 하 여 컨테이너를 미리 만들고, 사용자가 제한 된 보기 또는 이전 28 일 동안 응용 프로그램 가드에서 파일을 열었습니다.</span><span class="sxs-lookup"><span data-stu-id="f831b-251">To provide users with the expected file opening experience, Application Guard uses logic to pre-create a container when the following heuristic is met on a system: A user has opened a file in either Protected View or Application Guard in the past 28 days.</span></span> 

<span data-ttu-id="f831b-252">이 경험적 접근이 충족 되 면 Office는 Windows에 로그인 한 후 사용자에 대 한 응용 프로그램 보호 컨테이너를 미리 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="f831b-252">When this heuristic is met, Office will pre-create an Application Guard container for the user after they log in to Windows.</span></span> <span data-ttu-id="f831b-253">이 미리 만들기 작업을 진행 중인 경우 시스템 성능이 저하 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f831b-253">When this pre-create operation is in progress, the system may experience slow performance.</span></span> <span data-ttu-id="f831b-254">이 작업은 작업이 완료 되는 즉시 해결 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f831b-254">This will resolve as soon as the operation completes.</span></span> 


>[!NOTE] 
><span data-ttu-id="f831b-255">컨테이너를 미리 만들기 위해 사용 하는 추론에 필요한 힌트는 사용자가 사용 하는 Office 응용 프로그램에 의해 생성 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f831b-255">The hints needed for the heuristic used to pre-create the container are generated by Office applications as a user uses them.</span></span> <span data-ttu-id="f831b-256">사용자가 응용 프로그램 보호를 사용할 수 있는 새 시스템에 Office를 설치 하는 경우 Office에서는 사용자가 시스템에서 신뢰할 수 없는 문서를 처음으로 열 때까지 컨테이너를 미리 만들지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="f831b-256">If a user installs Office on a new system where Application Guard is enabled, Office will not pre-create the container until after the first time a user opens an untrusted document on the system.</span></span> <span data-ttu-id="f831b-257">사용자가 응용 프로그램 보호에서이 첫 번째 파일을 여는 데 시간이 오래 걸리는 것을 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f831b-257">The user will observe that this first file takes longer to open in Application Guard.</span></span> 

## <a name="known-issues-in-preview"></a><span data-ttu-id="f831b-258">미리 보기의 알려진 문제</span><span class="sxs-lookup"><span data-stu-id="f831b-258">Known issues in preview</span></span>

* <span data-ttu-id="f831b-259">웹 링크 (또는)를 클릭 하면 ```http``` ```https``` 브라우저가 열리지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="f831b-259">Clicking on web links (```http``` or ```https```) does not open the browser.</span></span> 
* <span data-ttu-id="f831b-260">.NET 업데이트가 응용 프로그램 보호에서 파일이 열리지 않게 합니다.</span><span class="sxs-lookup"><span data-stu-id="f831b-260">.NET updates cause files to fail to open in Application Guard.</span></span> <span data-ttu-id="f831b-261">이 문제를 해결 하기 위해 사용자는이 문제가 발생 했을 때 장치를 다시 부팅할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f831b-261">As a workaround, users can reboot their device when this issue is encountered.</span></span>
    <span data-ttu-id="f831b-262">[Windows Defender Application Guard 또는 Windows 샌드박스를 열려고 할 때 오류 메시지가 수신 될 때 발생](https://support.microsoft.com/help/4575917/receiving-an-error-message-when-attempting-to-open-windows-defender-ap)하는 문제에 대해 자세히 알아보세요.</span><span class="sxs-lookup"><span data-stu-id="f831b-262">Learn more about the issue at [Receiving an error message when attempting to open Windows Defender Application Guard or Windows Sandbox](https://support.microsoft.com/help/4575917/receiving-an-error-message-when-attempting-to-open-windows-defender-ap).</span></span>
