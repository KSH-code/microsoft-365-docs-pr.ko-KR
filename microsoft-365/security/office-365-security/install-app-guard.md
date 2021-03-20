---
title: 관리자용 Office 365용 Application Guard
keywords: application guard, 보호, 격리, 격리된 컨테이너, 하드웨어 격리
f1.keywords:
- NOCSH
ms.author: maccruz
author: schmurky
manager: dansimp
audience: ITPro
ms.topic: article
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.collection: M365-security-compliance
description: 하드웨어 기반의 최신 고리형을 다운로드합니다. 악용 또는 악의적인 링크와 같은 현재 및 새로운 공격이 직원 생산성과 엔터프라이즈 보안을 방해하지 않도록 방지합니다.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: a13196080aa0084411b737bfc157bbdb4b243a40
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/19/2021
ms.locfileid: "50907171"
---
# <a name="application-guard-for-office-for-admins"></a><span data-ttu-id="b0132-105">관리자용 Office용 Application Guard</span><span class="sxs-lookup"><span data-stu-id="b0132-105">Application Guard for Office for admins</span></span>

<span data-ttu-id="b0132-106">**다음에 적용됩니다.** Microsoft 365용 Word, Excel 및 PowerPoint, Windows 10 Enterprise</span><span class="sxs-lookup"><span data-stu-id="b0132-106">**Applies to:** Word, Excel, and PowerPoint for Microsoft 365, Windows 10 Enterprise</span></span>

<span data-ttu-id="b0132-107">Microsoft Defender Application Guard for Office(Office용 Application Guard)는 신뢰할 수 없는 파일이 신뢰할 수 있는 리소스에 액세스하지 못하게 하여 새로운 공격으로부터 엔터프라이즈를 안전하게 보호합니다.</span><span class="sxs-lookup"><span data-stu-id="b0132-107">Microsoft Defender Application Guard for Office (Application Guard for Office) helps prevent untrusted files from accessing trusted resources, keeping your enterprise safe from new and emerging attacks.</span></span> <span data-ttu-id="b0132-108">이 문서에서는 관리자에게 Office용 Application Guard의 미리 보기에 대한 디바이스 설정을 진행합니다.</span><span class="sxs-lookup"><span data-stu-id="b0132-108">This article walks admins through setting up devices for a preview of Application Guard for Office.</span></span> <span data-ttu-id="b0132-109">디바이스에서 Office용 Application Guard를 사용하도록 설정하기 위한 시스템 요구 사항 및 설치 단계에 대한 정보를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="b0132-109">It provides information about system requirements and installation steps to enable Application Guard for Office on a device.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="b0132-110">필수 구성 요소</span><span class="sxs-lookup"><span data-stu-id="b0132-110">Prerequisites</span></span>

### <a name="minimum-hardware-requirements"></a><span data-ttu-id="b0132-111">최소 하드웨어 요구 사항</span><span class="sxs-lookup"><span data-stu-id="b0132-111">Minimum hardware requirements</span></span>

* <span data-ttu-id="b0132-112">**CPU**: 64비트, 4코어(실제 또는 가상), 가상화 확장(Intel VT-x OR AMD-V), Core i5 이상 권장</span><span class="sxs-lookup"><span data-stu-id="b0132-112">**CPU**: 64-bit, 4 cores (physical or virtual), virtualization extensions (Intel VT-x OR AMD-V), Core i5 equivalent or higher recommended</span></span>
* <span data-ttu-id="b0132-113">**실제 메모리:** 8GB RAM</span><span class="sxs-lookup"><span data-stu-id="b0132-113">**Physical memory**: 8-GB RAM</span></span>
* <span data-ttu-id="b0132-114">**하드 디스크:** 시스템 드라이브에 10GB의 사용 공간(SSD 권장)</span><span class="sxs-lookup"><span data-stu-id="b0132-114">**Hard disk**: 10 GB of free space on the system drive (SSD recommended)</span></span>

### <a name="minimum-software-requirements"></a><span data-ttu-id="b0132-115">최소 소프트웨어 요구 사항</span><span class="sxs-lookup"><span data-stu-id="b0132-115">Minimum software requirements</span></span>

* <span data-ttu-id="b0132-116">**Windows 10:** Windows 10 Enterprise 버전, 클라이언트 빌드 버전 2004(20H1) 빌드 19041 이상</span><span class="sxs-lookup"><span data-stu-id="b0132-116">**Windows 10**: Windows 10 Enterprise edition, Client Build version 2004 (20H1) build 19041 or later</span></span>
* <span data-ttu-id="b0132-117">**Office**: Office 현재 채널 빌드 버전 2011 16.0.13530.10000 이상.</span><span class="sxs-lookup"><span data-stu-id="b0132-117">**Office**: Office Current Channel Build version 2011 16.0.13530.10000 or later.</span></span> <span data-ttu-id="b0132-118">32비트 및 64비트 버전의 Office가 모두 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="b0132-118">Both 32-bit and 64-bit versions of Office are supported.</span></span>
* <span data-ttu-id="b0132-119">**업데이트 패키지:** Windows 10 월별 누적 보안 업데이트 [KB4571756](https://support.microsoft.com/help/4571756/windows-10-update-KB4571756)</span><span class="sxs-lookup"><span data-stu-id="b0132-119">**Update package**: Windows 10 cumulative monthly security update [KB4571756](https://support.microsoft.com/help/4571756/windows-10-update-KB4571756)</span></span>

<span data-ttu-id="b0132-120">자세한 시스템 요구 사항은 [Microsoft Defender Application Guard의 시스템 요구 사항을 참조하세요.](/windows/security/threat-protection/microsoft-defender-application-guard/reqs-md-app-guard)</span><span class="sxs-lookup"><span data-stu-id="b0132-120">For detailed system requirements, refer to [System requirements for Microsoft Defender Application Guard](/windows/security/threat-protection/microsoft-defender-application-guard/reqs-md-app-guard).</span></span> <span data-ttu-id="b0132-121">Office 업데이트 채널에 대한 자세한 내용은 Microsoft 365 업데이트 채널 [개요를 참조하세요.](/deployoffice/overview-update-channels)</span><span class="sxs-lookup"><span data-stu-id="b0132-121">To learn more about Office update channels, see [Overview of update channels for Microsoft 365](/deployoffice/overview-update-channels).</span></span>

### <a name="licensing-requirements"></a><span data-ttu-id="b0132-122">라이선스 요구 사항</span><span class="sxs-lookup"><span data-stu-id="b0132-122">Licensing requirements</span></span>

* <span data-ttu-id="b0132-123">Microsoft 365 E5 또는 Microsoft 365 E5 보안</span><span class="sxs-lookup"><span data-stu-id="b0132-123">Microsoft 365 E5 or Microsoft 365 E5 Security</span></span>

## <a name="deploy-application-guard-for-office"></a><span data-ttu-id="b0132-124">Office용 Application Guard 배포</span><span class="sxs-lookup"><span data-stu-id="b0132-124">Deploy Application Guard for Office</span></span>

### <a name="enable-application-guard-for-office"></a><span data-ttu-id="b0132-125">Office에 Application Guard 사용</span><span class="sxs-lookup"><span data-stu-id="b0132-125">Enable Application Guard for Office</span></span>

1. <span data-ttu-id="b0132-126">Windows 10 월별 누적 보안 업데이트 **KB4571756를 다운로드하여 설치합니다.**</span><span class="sxs-lookup"><span data-stu-id="b0132-126">Download and install **Windows 10 cumulative monthly security updates KB4571756**.</span></span>

2. <span data-ttu-id="b0132-127">Windows **기능에서 Microsoft Defender Application Guard를** 선택하고 확인 을 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="b0132-127">Select **Microsoft Defender Application Guard** under Windows Features and  select **OK**.</span></span> <span data-ttu-id="b0132-128">Application Guard 기능을 사용하도록 설정하면 시스템 재부팅이 묻습니다.</span><span class="sxs-lookup"><span data-stu-id="b0132-128">Enabling the Application Guard feature will prompt a system reboot.</span></span> <span data-ttu-id="b0132-129">지금 다시 시작하거나 3단계 후에 재부팅할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b0132-129">You can choose to reboot now or after step 3.</span></span>

   ![AG를 보여 주며 Windows 기능 대화 상자](../../media/ag03-deploy.png)

   <span data-ttu-id="b0132-131">다음 PowerShell 명령을 관리자 권한으로 실행하여 이 기능을 사용할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b0132-131">The feature can also be enabled by running the following PowerShell command as administrator:</span></span>

   ```powershell
   Enable-WindowsOptionalFeature -online -FeatureName Windows-Defender-ApplicationGuard
   ```

3. <span data-ttu-id="b0132-132">컴퓨터 구성 관리 템플릿 Windows 구성 요소 **Microsoft Defender Application Guard의** 그룹 정책인 관리 모드에서 Microsoft **\\ \\ \\ Defender Application Guard를 검색합니다.**</span><span class="sxs-lookup"><span data-stu-id="b0132-132">Search for **Microsoft Defender Application Guard in Managed Mode**, a group policy in **Computer Configuration\\Administrative Templates\\Windows Components\\Microsoft Defender Application Guard**.</span></span> <span data-ttu-id="b0132-133">옵션에서 값을 2 또는 **3으로** 설정한 다음 확인 또는 적용 **을** 선택하여 이 **정책을** **켜야 합니다.**</span><span class="sxs-lookup"><span data-stu-id="b0132-133">Turn on this policy by setting the value under Options as **2** or **3**, and then selecting **OK** or **Apply**.</span></span>

   ![관리 모드에서 AG 켜기](../../media/ag04-deploy.png)

   <span data-ttu-id="b0132-135">대신 해당 CSP 정책을 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b0132-135">Instead, you can set the corresponding CSP policy:</span></span>

   > <span data-ttu-id="b0132-136">OMA-URI: **./Device/Vendor/MSFT/WindowsDefenderApplicationGuard/Settings/AllowWindowsDefenderApplicationGuard**</span><span class="sxs-lookup"><span data-stu-id="b0132-136">OMA-URI: **./Device/Vendor/MSFT/WindowsDefenderApplicationGuard/Settings/AllowWindowsDefenderApplicationGuard**</span></span> <br> <span data-ttu-id="b0132-137">데이터 형식: **정수**</span><span class="sxs-lookup"><span data-stu-id="b0132-137">Data type: **Integer**</span></span> <br> <span data-ttu-id="b0132-138">값: **2**</span><span class="sxs-lookup"><span data-stu-id="b0132-138">Value: **2**</span></span>

4. <span data-ttu-id="b0132-139">시스템을 다시 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="b0132-139">Restart the system.</span></span>

### <a name="set-diagnostics--feedback-to-send-full-data"></a><span data-ttu-id="b0132-140">진단 & 피드백을 설정하여 전체 데이터 보내기</span><span class="sxs-lookup"><span data-stu-id="b0132-140">Set Diagnostics & feedback to send full data</span></span>

<span data-ttu-id="b0132-141">이 단계를 통해 문제를 식별하고 해결하는 데 필요한 데이터가 Microsoft에 도달하는지 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b0132-141">This step ensures that the data necessary to identify and fix problems is reaching Microsoft.</span></span> <span data-ttu-id="b0132-142">Windows 장치에서 진단을 사용하도록 설정하려면 다음 단계를 따르세요.</span><span class="sxs-lookup"><span data-stu-id="b0132-142">Follow these steps to enable diagnostics on your Windows device:</span></span>

1. <span data-ttu-id="b0132-143">시작 **메뉴에서** 설정을 니다.</span><span class="sxs-lookup"><span data-stu-id="b0132-143">Open **Settings** from the Start menu.</span></span>

   ![시작 메뉴](../../media/ag05-diagnostic.png)

2. <span data-ttu-id="b0132-145">**Windows 설정에서** 개인 정보를 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="b0132-145">On **Windows Settings**, select **Privacy**.</span></span>

   ![Windows 설정 메뉴](../../media/ag06-diagnostic.png)

3. <span data-ttu-id="b0132-147">개인 정보 보호에서 진단 및 **& 선택적** **진단 데이터를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="b0132-147">Under Privacy, select **Diagnostics & feedback** and select **Optional diagnostic data**.</span></span>

   ![진단 및 피드백 메뉴](../../media/ag07a-diagnostic.png)

<span data-ttu-id="b0132-149">Windows 진단 설정 구성에 대한 자세한 내용은 조직에서 Windows 진단 [데이터 구성을 참조하세요.](/windows/privacy/configure-windows-diagnostic-data-in-your-organization#enterprise-management)</span><span class="sxs-lookup"><span data-stu-id="b0132-149">For more on configuring Windows diagnostic settings, refer to [Configuring Windows diagnostic data in your organization](/windows/privacy/configure-windows-diagnostic-data-in-your-organization#enterprise-management).</span></span>

### <a name="confirm-that-application-guard-for-office-is-enabled-and-working"></a><span data-ttu-id="b0132-150">Office용 Application Guard가 사용하도록 설정되어 있으며 작동하고 있는지 확인</span><span class="sxs-lookup"><span data-stu-id="b0132-150">Confirm that Application Guard for Office is enabled and working</span></span>

<span data-ttu-id="b0132-151">Office용 Application Guard를 사용하도록 설정되어 있는지 확인하기 전에 정책이 배포된 장치에서 Word, Excel 또는 PowerPoint를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="b0132-151">Before confirming that Application Guard for Office is enabled, launch Word, Excel, or PowerPoint on a device where the policies have been deployed.</span></span> <span data-ttu-id="b0132-152">Office가 정품 인증되어 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="b0132-152">Make sure Office is activated.</span></span> <span data-ttu-id="b0132-153">먼저 작업 ID를 사용하여 Office 제품을 정품 인증해야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b0132-153">You may need to use your work identity to activate the Office product first.</span></span>

<span data-ttu-id="b0132-154">Office용 Application Guard를 사용하도록 설정되어 있는지 확인하기 위해 Word, Excel 또는 PowerPoint를 시작한 다음, 트러설되지 않은 문서를 여는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="b0132-154">To confirm that Application Guard for Office is enabled, launch Word, Excel, or PowerPoint, and then open an untrusted document.</span></span> <span data-ttu-id="b0132-155">예를 들어 인터넷에서 다운로드한 문서나 조직 외부의 사용자가 전자 메일 첨부 파일을 열 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b0132-155">For example, you can open a document that was downloaded from the internet or an email attachment from someone outside your organization.</span></span>

<span data-ttu-id="b0132-156">처음에 트러설이 없는 파일을 열면 다음 예와 같이 Office 시작 화면이 표시될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b0132-156">When you first open an untrusted file, you may see an Office splash screen like the following example.</span></span> <span data-ttu-id="b0132-157">Office용 Application Guard가 활성화되고 파일이 열리면서 일부 시간 동안 표시될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b0132-157">It might be displayed for some time while Application Guard for Office is being activated and the file is being opened.</span></span> <span data-ttu-id="b0132-158">이후에는 더 빠르게 파일을 열 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b0132-158">Subsequent openings of untrusted files should be faster.</span></span>

![Office 앱 시작 화면](../../media/ag08-confirm.png)

<span data-ttu-id="b0132-160">파일을 열면 파일이 Office용 Application Guard 내에서 열렸다는 몇 가지 시각적 표시기가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="b0132-160">Upon being opened, the file should display a few visual indicators that the file was opened inside Application Guard for Office:</span></span>

* <span data-ttu-id="b0132-161">리본 메뉴의 콜아웃</span><span class="sxs-lookup"><span data-stu-id="b0132-161">A callout in the ribbon</span></span>

  ![작은 App Guard 메모를 표시하는 Doc 파일](../../media/ag09-confirm.png)

* <span data-ttu-id="b0132-163">작업 표시줄에 방패가 있는 응용 프로그램 아이콘</span><span class="sxs-lookup"><span data-stu-id="b0132-163">The application icon with a shield in the taskbar</span></span>

  ![작업 표시줄의 아이콘](../../media/ag12-limitations.png)

## <a name="configure-application-guard-for-office"></a><span data-ttu-id="b0132-165">Office용 Application Guard 구성</span><span class="sxs-lookup"><span data-stu-id="b0132-165">Configure Application Guard for Office</span></span>

<span data-ttu-id="b0132-166">Office에서는 Office용 Application Guard의 기능을 구성할 수 있도록 다음 정책을 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="b0132-166">Office supports the following policies to enable you to configure the capabilities of Application Guard for Office.</span></span> <span data-ttu-id="b0132-167">이러한 정책은 그룹 정책 또는 Office 클라우드 정책 서비스를 통해 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b0132-167">These policies can be configured through Group policies or through the Office cloud policy service.</span></span>

> [!NOTE]
> <span data-ttu-id="b0132-168">이러한 정책을 구성하면 Office용 Application Guard에서 연 파일에 대해 일부 기능을 사용하지 않도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b0132-168">Configuring these policies can disable some functionalities for files opened in Application Guard for Office.</span></span>

|<span data-ttu-id="b0132-169">정책</span><span class="sxs-lookup"><span data-stu-id="b0132-169">Policy</span></span>|<span data-ttu-id="b0132-170">설명</span><span class="sxs-lookup"><span data-stu-id="b0132-170">Description</span></span>|
|---|---|
|<span data-ttu-id="b0132-171">Office에 Application Guard를 사용하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="b0132-171">Don't use Application Guard for Office</span></span>|<span data-ttu-id="b0132-172">이 정책을 사용하도록 설정하면 Word, Excel 및 PowerPoint에서 Office용 Application Guard 대신 보호된 보기의 고리 컨테이너를 사용하도록 강제로 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="b0132-172">Enabling this policy will force Word, Excel, and PowerPoint to use the Protected View isolation container instead of Application Guard for Office.</span></span> <span data-ttu-id="b0132-173">이 정책은 Microsoft Edge를 사용하도록 설정한 채로 두는 데 문제가 있는 경우 Office용 Application Guard를 일시적으로 사용하지 않도록 설정하는 데 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b0132-173">This policy can be used to temporarily disable Application Guard for Office when there are issues in leaving it enabled for Microsoft Edge.</span></span>|
|<span data-ttu-id="b0132-174">Office 컨테이너 사전 만들기를 위한 Application Guard 구성</span><span class="sxs-lookup"><span data-stu-id="b0132-174">Configure Application Guard for Office container pre-creation</span></span>|<span data-ttu-id="b0132-175">이 정책은 향상된 런타임 성능을 위해 Office 컨테이너용 Application Guard(트러크되지 않은 파일)를 미리 만들어야 하는지 여부를 판정합니다.</span><span class="sxs-lookup"><span data-stu-id="b0132-175">This policy determines if the Application Guard for Office container, for isolating untrusted files, is pre-created for improved run-time performance.</span></span> <span data-ttu-id="b0132-176">이 설정을 사용하면 컨테이너를 미리 만들기 전까지 계속할 일 수를 지정하거나 Office에서 기본 제공된 이후로 컨테이너를 미리 만들 수 있도록 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b0132-176">If you enable this setting, you can specify the number of days to continue pre-creating a container or let the Office built-in heuristic pre-create the container.</span></span>
|<span data-ttu-id="b0132-177">Office용 Application Guard에서 연 Office 문서의 복사/붙여넣기 허용 안 하도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="b0132-177">Don't allow copy/paste for Office documents opened in Application Guard for Office</span></span>|<span data-ttu-id="b0132-178">이 정책을 사용하도록 설정하면 사용자가 Office용 Application Guard에서 연 문서의 콘텐츠를 복사하여 외부에서 연 문서에 붙여넣을 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="b0132-178">Enabling this policy will prevent a user from copying and pasting content from a document opened in Application Guard for Office to a document opened outside of it.</span></span>|
|<span data-ttu-id="b0132-179">Office용 Application Guard에서 하드웨어 가속을 사용하지 않도록 설정</span><span class="sxs-lookup"><span data-stu-id="b0132-179">Disable hardware acceleration in Application Guard for Office</span></span>|<span data-ttu-id="b0132-180">이 정책은 Office용 Application Guard에서 하드웨어 가속을 사용하여 그래픽을 렌더링할지 여부를 제어합니다.</span><span class="sxs-lookup"><span data-stu-id="b0132-180">This policy controls whether Application Guard for Office uses hardware acceleration to render graphics.</span></span> <span data-ttu-id="b0132-181">이 설정을 사용하면 Office용 Application Guard는 소프트웨어 기반(CPU) 렌더링을 사용하며 타사 그래픽 드라이버를 로드하거나 연결된 그래픽 하드웨어와 상호 작용하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="b0132-181">If you enable this setting, Application Guard for Office uses software-based (CPU) rendering and won't load any third-party graphics drivers or interact with any connected graphics hardware.</span></span>
|<span data-ttu-id="b0132-182">Office용 Application Guard에서 지원되지 않는 파일 형식 보호 해제</span><span class="sxs-lookup"><span data-stu-id="b0132-182">Disable unsupported file types protection in Application Guard for Office</span></span>|<span data-ttu-id="b0132-183">이 정책은 Office용 Application Guard가 지원되지 않는 파일 형식이 열리지 못하도록 차단할지 아니면 보호된 보기로 리디렉션할지 여부를 제어합니다.</span><span class="sxs-lookup"><span data-stu-id="b0132-183">This policy controls whether Application Guard for Office will block unsupported file types from being opened or if it will enable the redirection to Protected View.</span></span>
|<span data-ttu-id="b0132-184">Office용 Application Guard에서 연 문서에 대한 카메라 및 마이크 액세스 끄기</span><span class="sxs-lookup"><span data-stu-id="b0132-184">Turn off camera and microphone access for documents opened in Application Guard for Office</span></span>|<span data-ttu-id="b0132-185">이 정책을 사용하도록 설정하면 Office용 Application Guard 내부의 카메라 및 마이크에 대한 Office 액세스가 제거됩니다.</span><span class="sxs-lookup"><span data-stu-id="b0132-185">Enabling this policy will remove Office access to the camera and microphone inside Application Guard for Office.</span></span>|
|<span data-ttu-id="b0132-186">Office용 Application Guard에서 연 문서에서 인쇄 제한</span><span class="sxs-lookup"><span data-stu-id="b0132-186">Restrict printing from documents opened in Application Guard for Office</span></span>|<span data-ttu-id="b0132-187">이 정책을 사용하도록 설정하면 사용자가 Office용 Application Guard에서 연 파일에서 인쇄할 수 있는 프린터가 제한됩니다.</span><span class="sxs-lookup"><span data-stu-id="b0132-187">Enabling this policy will limit the printers that a user can print to from a file opened in Application Guard for Office.</span></span> <span data-ttu-id="b0132-188">예를 들어 이 정책을 사용하여 사용자가 PDF로만 인쇄하도록 제한할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b0132-188">For example, you can use this policy to restrict users to only print to PDF.</span></span>|
|<span data-ttu-id="b0132-189">사용자가 파일에서 Office 보호를 위해 Application Guard를 제거하지 못하게 방지</span><span class="sxs-lookup"><span data-stu-id="b0132-189">Prevent users from removing Application Guard for Office protection on files</span></span>|<span data-ttu-id="b0132-190">이 정책을 사용하면 Office 응용 프로그램 환경 내에서 Office 보호를 위해 Application Guard를 사용하지 않도록 설정하거나 Office용 Application Guard 외부에서 파일을 여는 옵션이 제거됩니다.</span><span class="sxs-lookup"><span data-stu-id="b0132-190">Enabling this policy will remove the option (within the Office application experience) to disable Application Guard for Office protection or to open a file outside Application Guard for Office.</span></span> <p> <span data-ttu-id="b0132-191">**참고:** 사용자는 파일에서 웹 표시 속성을 수동으로 제거하거나 문서를 신뢰할 수 있는 위치로 이동하여 이 정책을 무시할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b0132-191">**Note:** Users can still bypass this policy by manually removing the mark-of-the-web property from the file or by moving a document to a Trusted location.</span></span>|
|

> [!NOTE]
> <span data-ttu-id="b0132-192">다음 정책을 적용하려면 사용자가 로그인한 후 Windows에 다시 로그인해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b0132-192">The following policies will require the user to sign out and sign in again to Windows to take effect:</span></span>
>
> * <span data-ttu-id="b0132-193">Office용 Application Guard에서 연 문서에 대해 복사/붙여넣기 사용 안</span><span class="sxs-lookup"><span data-stu-id="b0132-193">Disable copy/paste for documents opened in Application Guard for Office</span></span>
> * <span data-ttu-id="b0132-194">Office용 Application Guard에서 열 수 있는 문서에 대한 인쇄 제한</span><span class="sxs-lookup"><span data-stu-id="b0132-194">Restrict printing for documents opened in Application Guard for Office</span></span>
> * <span data-ttu-id="b0132-195">Office용 Application Guard에서 연 문서에 대한 카메라 및 마이크 액세스 끄기</span><span class="sxs-lookup"><span data-stu-id="b0132-195">Turn off camera and mic access to documents opened in Application Guard for Office</span></span>

## <a name="submit-feedback"></a><span data-ttu-id="b0132-196">피드백 제출</span><span class="sxs-lookup"><span data-stu-id="b0132-196">Submit feedback</span></span>

### <a name="submit-feedback-via-feedback-hub"></a><span data-ttu-id="b0132-197">피드백 허브를 통해 피드백 제출</span><span class="sxs-lookup"><span data-stu-id="b0132-197">Submit feedback via Feedback Hub</span></span>

<span data-ttu-id="b0132-198">Office용 Application Guard를 시작하면 문제가 발생하는 경우 피드백 허브를 통해 피드백을 제출하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="b0132-198">If you encounter any issues when launching Application Guard for Office, you're encouraged to submit your feedback via Feedback Hub:</span></span>

1. <span data-ttu-id="b0132-199">피드백 허브 **앱을 열고** 로그인합니다.</span><span class="sxs-lookup"><span data-stu-id="b0132-199">Open the **Feedback Hub app** and sign in.</span></span>

2. <span data-ttu-id="b0132-200">Application Guard를 시작하는 동안 오류 대화 상자가 발생하는 경우 오류 대화 상자에서 **Microsoft에 보고를** 선택하여 새 피드백 제출을 시작하십시오.</span><span class="sxs-lookup"><span data-stu-id="b0132-200">If you get an error dialog while launching Application Guard, select **Report to Microsoft** in the error dialog to start a new feedback submission.</span></span> <span data-ttu-id="b0132-201">그렇지 않은 경우 Application Guard에 대한 올바른 범주를 선택한 다음 오른쪽 상단 근처에서 새 <https://aka.ms/mdagoffice-fb> **+ &nbsp; 피드백** 추가를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="b0132-201">Otherwise, navigate to <https://aka.ms/mdagoffice-fb> to select the correct category for Application Guard, then select **+&nbsp;Add new feedback** near the top right.</span></span>

3. <span data-ttu-id="b0132-202">사용자 의견이 아직  입력되지 않은 경우 요약 상자에 요약을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="b0132-202">Enter a summary in the **Summarize your feedback** box if it isn't already filled in for you.</span></span>

4. <span data-ttu-id="b0132-203">경험한 문제 및 자세한 내용 설명 상자에 수행한  단계에 대한 자세한 설명을 입력하고 다음 을 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="b0132-203">Enter a detailed description of the issue that you experienced and what steps you took in the **Explain in more detail** box, then select **Next**.</span></span>

5. <span data-ttu-id="b0132-204">문제 옆에 있는 거품을 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="b0132-204">Select the bubble next to **Problem**.</span></span> <span data-ttu-id="b0132-205">선택한 범주가 보안 및 개인 정보 **\> 보호 Microsoft Defender Application Guard - Office인지 확인한 후** 다음 을 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="b0132-205">Make sure the category selected is **Security and Privacy \> Microsoft Defender Application Guard – Office**, then select **Next**.</span></span>

6. <span data-ttu-id="b0132-206">새 **피드백,** 다음 을 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="b0132-206">Select **New feedback**, then **Next**.</span></span>

7. <span data-ttu-id="b0132-207">이 문제의 추적을 수집합니다.</span><span class="sxs-lookup"><span data-stu-id="b0132-207">Collect traces about the issue:</span></span>

   1. <span data-ttu-id="b0132-208">내 문제 **다시 발생 타일을 확장합니다.**</span><span class="sxs-lookup"><span data-stu-id="b0132-208">Expand the **Recreate my problem** tile.</span></span>

   2. <span data-ttu-id="b0132-209">Application Guard가 실행되는 동안 발생하는 문제가 발생하면 Application Guard 인스턴스를 여는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="b0132-209">If the issue you're experiencing occurs while Application Guard is running, open an Application Guard instance.</span></span> <span data-ttu-id="b0132-210">인스턴스를 열면 Application Guard 컨테이너 내에서 추가 추적을 수집할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b0132-210">Opening an instance allows additional traces to be collected from within the Application Guard container.</span></span>

   3. <span data-ttu-id="b0132-211">녹음 **시작 을** 선택하고 타일이 회전을 중지할 때까지 기다렸다가 기록 *중지라고 말합니다.*</span><span class="sxs-lookup"><span data-stu-id="b0132-211">Select **Start recording**, and wait for the tile to stop spinning and say *Stop recording*.</span></span>

   4. <span data-ttu-id="b0132-212">Application Guard에서 문제를 완전히 재현합니다.</span><span class="sxs-lookup"><span data-stu-id="b0132-212">Fully reproduce the issue with Application Guard.</span></span> <span data-ttu-id="b0132-213">다시 생성에는 Application Guard 인스턴스를 시작하려고 시도하고 실패할 때까지 기다리거나 실행 중인 Application Guard 인스턴스에서 문제를 재현하는 것이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="b0132-213">Reproduction might include attempting to launch an Application Guard instance and waiting until it fails, or reproducing an issue in a running Application Guard instance.</span></span>

   5. <span data-ttu-id="b0132-214">녹음 중지 **타일을** 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="b0132-214">Select the **Stop recording** tile.</span></span>

   6. <span data-ttu-id="b0132-215">컨테이너 진단을 수집할 수 있도록 제출 후 몇 분 동안에도 실행 중인 Application Guard 인스턴스를 열어 웁니다.</span><span class="sxs-lookup"><span data-stu-id="b0132-215">Keep any running Application Guard instance(s) open, even for a few minutes after submission, so that container diagnostics can also be collected.</span></span>

8. <span data-ttu-id="b0132-216">문제와 관련된 스크린샷 또는 파일을 첨부합니다.</span><span class="sxs-lookup"><span data-stu-id="b0132-216">Attach any relevant screenshots or files related to the problem.</span></span>

9. <span data-ttu-id="b0132-217">**전송** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="b0132-217">Select **Submit**.</span></span>

### <a name="submit-feedback-via-office-customer-voice"></a><span data-ttu-id="b0132-218">Office Customer Voice를 통해 피드백 제출</span><span class="sxs-lookup"><span data-stu-id="b0132-218">Submit feedback via Office Customer Voice</span></span>

<span data-ttu-id="b0132-219">Office 문서를 Application Guard에서 열 때 문제가 발생하는 경우 Office 내에서 피드백을 제출할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b0132-219">You may also submit feedback from within Office if the issue happens when Office documents are opened in Application Guard.</span></span> <span data-ttu-id="b0132-220">피드백을 제출할 수 있는 [Office Insider Handbook을](https://insider.office.com/handbook) 참조합니다.</span><span class="sxs-lookup"><span data-stu-id="b0132-220">Refer to the [Office Insider Handbook](https://insider.office.com/handbook) for submitting feedback.</span></span>

## <a name="integration-with-microsoft-defender-for-endpoint-and-microsoft-defender-for-office-365"></a><span data-ttu-id="b0132-221">Endpoint용 Microsoft Defender 및 Office 365용 Microsoft Defender와의 통합</span><span class="sxs-lookup"><span data-stu-id="b0132-221">Integration with Microsoft Defender for Endpoint and Microsoft Defender for Office 365</span></span>

<span data-ttu-id="b0132-222">Office용 Application Guard는 격리된 환경에서 발생하는 악의적인 활동에 대한 모니터링 및 경고를 제공하기 위해 끝점용 Microsoft Defender와 통합되었습니다.</span><span class="sxs-lookup"><span data-stu-id="b0132-222">Application Guard for Office is integrated with Microsoft Defender for Endpoint to provide monitoring and alerting on malicious activity that happens in the isolated environment.</span></span>

<span data-ttu-id="b0132-223">끝점용 Microsoft Defender는 엔터프라이즈 네트워크가 고급 위협을 방지, 감지, 조사 및 대응하는 데 도움이 하도록 설계된 보안 플랫폼입니다.</span><span class="sxs-lookup"><span data-stu-id="b0132-223">Microsoft Defender for Endpoint is a security platform designed to help enterprise networks prevent, detect, investigate, and respond to advanced threats.</span></span> <span data-ttu-id="b0132-224">이 플랫폼에 대한 자세한 내용은 [끝점용 Microsoft Defender를 참조합니다.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp)</span><span class="sxs-lookup"><span data-stu-id="b0132-224">For more details about this platform, see [Microsoft Defender for Endpoint](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp).</span></span> <span data-ttu-id="b0132-225">이 플랫폼에 장치 온보딩에 대한 자세한 내용은 [끝점 서비스용 Microsoft Defender에](/windows/security/threat-protection/microsoft-defender-atp/onboard-configure)장치 온보딩을 참조합니다.</span><span class="sxs-lookup"><span data-stu-id="b0132-225">To learn more about onboarding devices to this platform, see [Onboard devices to the Microsoft Defender for Endpoint service](/windows/security/threat-protection/microsoft-defender-atp/onboard-configure).</span></span>

<span data-ttu-id="b0132-226">끝점용 Defender와 함께 작동하도록 Office 365용 Microsoft Defender를 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b0132-226">You can also configure Microsoft Defender for Office 365 to work with Defender for Endpoint.</span></span> <span data-ttu-id="b0132-227">자세한 내용은 Office [365용 Defender와 끝점용 Microsoft Defender 통합을 참조하세요.](integrate-office-365-ti-with-wdatp.md)</span><span class="sxs-lookup"><span data-stu-id="b0132-227">For more info, refer to [Integrate Defender for Office 365 with Microsoft Defender for Endpoint](integrate-office-365-ti-with-wdatp.md).</span></span>

## <a name="limitations-and-considerations"></a><span data-ttu-id="b0132-228">제한 사항 및 고려 사항</span><span class="sxs-lookup"><span data-stu-id="b0132-228">Limitations and considerations</span></span>

* <span data-ttu-id="b0132-229">Office용 Application Guard는 신뢰할 수 있는 회사 리소스, 인트라넷, 사용자의 ID 및 컴퓨터의 임의 파일에 액세스할 수 없는 신뢰할 수 없는 문서를 격리하는 제한된 모드입니다.</span><span class="sxs-lookup"><span data-stu-id="b0132-229">Application Guard for Office is a restricted mode that isolates untrusted documents so that they can't access trusted corporate resources, an intranet, the user's identity, and arbitrary files on the computer.</span></span> <span data-ttu-id="b0132-230">따라서 사용자가 디스크에 로컬 파일에서 그림을 삽입하는 등 액세스에 종속된 기능에 액세스하면 액세스가 실패하고 다음 예제와 같은 프롬프트가 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="b0132-230">As a result, if a user tries to access a feature that has a dependency on such access—for example, inserting a picture from a local file on disk—the access will fail and produce a prompt like the following example.</span></span> <span data-ttu-id="b0132-231">신뢰할 수 없는 문서가 신뢰할 수 있는 리소스에 액세스할 수 있도록 설정하려면 사용자가 문서에서 Application Guard 보호를 제거해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b0132-231">To enable an untrusted document to access trusted resources, users must remove Application Guard protection from the document.</span></span>

  ![안전한 유지를 위해 이 기능을 사용할 수 없는 경우를 설명하는 대화 상자](../../media/ag10-limitations.png)

  > [!NOTE]
  > <span data-ttu-id="b0132-233">사용자가 파일과 해당 원본을 신뢰할 수 있는 경우 또는 보호가 어디에서 왔는지만 보호를 제거해보는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="b0132-233">Advise users to only remove protection if they trust the file and its source or where it came from.</span></span>

* <span data-ttu-id="b0132-234">Office용 Application Guard에서 매크로 및 ActiveX 같은 문서의 활성 콘텐츠를 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="b0132-234">Active content in documents like macros and ActiveX controls are disabled in Application Guard for Office.</span></span> <span data-ttu-id="b0132-235">사용자가 활성 콘텐츠를 사용하도록 설정하려면 Application Guard 보호를 제거해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b0132-235">Users need to remove Application Guard protection to enable active content.</span></span>

* <span data-ttu-id="b0132-236">다른 조직에서 네트워크 공유 또는 OneDrive, 비즈니스용 OneDrive 또는 SharePoint Online에서 공유한 파일 또는 네트워크 공유의 트러치되지 않은 파일은 Application Guard에서 읽기 전용으로 열립니다.</span><span class="sxs-lookup"><span data-stu-id="b0132-236">Untrusted files from network shares or files shared from OneDrive, OneDrive for Business, or SharePoint Online from a different organization open as read-only in Application Guard.</span></span> <span data-ttu-id="b0132-237">사용자는 이러한 파일의 로컬 복사본을 저장하여 컨테이너에서 작업을 계속하거나 보호 기능을 제거하여 원본 파일을 직접 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b0132-237">Users can save a local copy of such files to continue working in the container or remove protection to directly work with the original file.</span></span>

* <span data-ttu-id="b0132-238">IRM(정보 권한 관리)으로 보호되는 파일은 기본적으로 차단됩니다.</span><span class="sxs-lookup"><span data-stu-id="b0132-238">Files that are protected by Information Rights Management (IRM) are blocked by default.</span></span> <span data-ttu-id="b0132-239">사용자가 이러한 파일을 보호된 보기에서 열기 위해 관리자는 조직에서 지원되지 않는 파일 형식에 대한 정책 설정을 구성해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b0132-239">If users want to open such files in Protected View, an administrator must configure policy settings for unsupported file types for the organization.</span></span>

* <span data-ttu-id="b0132-240">Office용 Application Guard의 Office 응용 프로그램에 대한 사용자 지정은 사용자가 로그인한 후 또는 장치가 다시 시작된 후에도 지속되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="b0132-240">Any customizations to Office applications in Application Guard for Office won't persist after a user signs out and signs in again or after the device restarts.</span></span>

* <span data-ttu-id="b0132-241">UIA 프레임워크를 사용하는 접근성 도구만 Office용 Application Guard에서 열 수 있는 파일에 액세스할 수 있는 환경을 제공할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b0132-241">Only Accessibility tools that use the UIA framework can provide an accessible experience for files opened in Application Guard for Office.</span></span>

* <span data-ttu-id="b0132-242">설치 후 Application Guard를 처음 시작하려면 네트워크 연결이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="b0132-242">Network connectivity is required for the first launch of Application Guard after installation.</span></span> <span data-ttu-id="b0132-243">라이선스의 유효성을 검사하려면 Application Guard에 연결해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b0132-243">Connectivity is required for Application Guard to validate the license.</span></span>

* <span data-ttu-id="b0132-244">문서의 정보 섹션에서 *마지막* 수정한 사용자 속성에 **WDAGUtilityAccount가** 사용자로 표시될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b0132-244">In the document's info section, the *Last Modified By* property may display **WDAGUtilityAccount** as the user.</span></span> <span data-ttu-id="b0132-245">WDAGUtilityAccount는 Application Guard에 구성된 익명 사용자입니다.</span><span class="sxs-lookup"><span data-stu-id="b0132-245">WDAGUtilityAccount is the anonymous user configured in Application Guard.</span></span> <span data-ttu-id="b0132-246">데스크톱 사용자의 ID는 Application Guard 컨테이너 내에서 공유되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="b0132-246">The desktop user's identity isn't shared inside the Application Guard container.</span></span>

## <a name="performance-optimizations-for-application-guard-for-office"></a><span data-ttu-id="b0132-247">Office용 Application Guard의 성능 최적화</span><span class="sxs-lookup"><span data-stu-id="b0132-247">Performance optimizations for Application Guard for Office</span></span>

<span data-ttu-id="b0132-248">이 섹션에서는 Office용 Application Guard에서 사용되는 성능 최적화에 대한 개요를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="b0132-248">This section provides an overview of the performance optimizations used in Application Guard for Office.</span></span> <span data-ttu-id="b0132-249">이 정보는 관리자가 Application Guard를 사용하도록 설정한 경우 Office의 성능 또는 전체 시스템과 관련된 사용자의 보고서를 진단하는 데 도움이 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b0132-249">This information can help administrators diagnose reports from users related to the performance of Office or the overall system when Application Guard is enabled.</span></span>

<span data-ttu-id="b0132-250">Application Guard는 가상화된 컨테이너를 사용하여 시스템에서 트러운 문서를 격리합니다.</span><span class="sxs-lookup"><span data-stu-id="b0132-250">Application Guard uses a virtualized container to isolate untrusted documents away from the system.</span></span> <span data-ttu-id="b0132-251">Office 문서를 열기 위해 컨테이너를 만들고 Application Guard 컨테이너를 설정하는 프로세스에서는 사용자가 트러프되지 않은 문서를 열 때 사용자 경험에 부정적인 영향을 줄 수 있는 성능 오버헤드가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b0132-251">The process of creating a container and setting up the Application Guard container to open Office documents has a performance overhead that might negatively affect user experience when users open an untrusted document.</span></span>

<span data-ttu-id="b0132-252">사용자에게 예상되는 파일 열기 환경을 제공하기 위해 Application Guard는 시스템에서 다음 경험적이 충족될 때 논리를 사용하여 컨테이너를 미리 만들 수 있습니다. 사용자가 지난 28일 동안 보호된 보기 또는 Application Guard에서 파일을 열었다는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="b0132-252">To provide users with the expected file-opening experience, Application Guard uses logic to pre-create a container when the following heuristic is met on a system: A user has opened a file in either Protected View or Application Guard in the past 28 days.</span></span>

<span data-ttu-id="b0132-253">이 언어가 충족될 경우 Office는 사용자가 Windows에 로그인한 후 사용자에 대한 Application Guard 컨테이너를 미리 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="b0132-253">When this heuristic is met, Office will pre-create an Application Guard container for the user after they sign in to Windows.</span></span> <span data-ttu-id="b0132-254">이 사전 만들기 작업이 진행 중이면 시스템에서 성능이 느려질 수 있지만 작업이 완료되면 즉시 효과가 해결됩니다.</span><span class="sxs-lookup"><span data-stu-id="b0132-254">While this pre-create operation is in progress, the system may experience slow performance, but the effect will resolve as soon as the operation completes.</span></span>

> [!NOTE]
> <span data-ttu-id="b0132-255">사용자가 컨테이너를 미리 만드는 데 필요한 힌트는 사용자가 컨테이너를 사용할 때 Office 응용 프로그램에 의해 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="b0132-255">The hints needed for the heuristic to pre-create the container are generated by Office applications as a user uses them.</span></span> <span data-ttu-id="b0132-256">사용자가 Application Guard를 사용하도록 설정된 새 시스템에 Office를 설치하는 경우 Office는 사용자가 시스템에서 처음으로 트러프되지 않은 문서를 열 때까지 컨테이너를 미리 만들지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="b0132-256">If a user installs Office on a new system where Application Guard is enabled, Office will not pre-create the container until after the first time a user opens an untrusted document on the system.</span></span> <span data-ttu-id="b0132-257">사용자는 Application Guard에서 이 첫 번째 파일을 여는 데 시간이 더 오래 걸리는 것으로 관찰합니다.</span><span class="sxs-lookup"><span data-stu-id="b0132-257">The user will observe that this first file takes longer to open in Application Guard.</span></span>

## <a name="known-issues"></a><span data-ttu-id="b0132-258">알려진 문제</span><span class="sxs-lookup"><span data-stu-id="b0132-258">Known issues</span></span>

* <span data-ttu-id="b0132-259">웹 링크(또는 )를 선택하면 `http` `https` 브라우저가 열립니다.</span><span class="sxs-lookup"><span data-stu-id="b0132-259">Selecting web links (`http` or `https`) doesn't open the browser.</span></span>
* <span data-ttu-id="b0132-260">현재 Application Guard를 사용하여 연 Office 문서의 RTF(서식 있는 텍스트) 콘텐츠 또는 이미지를 붙여 넣는 것은 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="b0132-260">Pasting rich text format (RTF) content or images in Office documents opened with Application Guard isn't supported at this time.</span></span>
* <span data-ttu-id="b0132-261">.NET을 업데이트하면 Application Guard에서 파일이 열리지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="b0132-261">Updates to .NET cause files to fail to open in Application Guard.</span></span> <span data-ttu-id="b0132-262">이 해결로 사용자는 이 오류가 발생하면 장치를 다시 시작할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b0132-262">As a workaround, users can restart their device when they come across this failure.</span></span> <span data-ttu-id="b0132-263">자세한 내용은 Application Guard 또는 Windows 샌드박스를 열 때 오류 [Windows Defender 수신을 통해 자세히 알아보실 수 있습니다.](https://support.microsoft.com/help/4575917/receiving-an-error-message-when-attempting-to-open-windows-defender-ap)</span><span class="sxs-lookup"><span data-stu-id="b0132-263">Learn more about the issue at [Receiving an error message when attempting to open Windows Defender Application Guard or Windows Sandbox](https://support.microsoft.com/help/4575917/receiving-an-error-message-when-attempting-to-open-windows-defender-ap).</span></span>