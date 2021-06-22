---
title: 관리자를 위한 Office 365 Application Guard
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
ms.openlocfilehash: 39d6a9c3a3c3a5e2c736025a26c22588f9f08bb0
ms.sourcegitcommit: fa9efab24a84f71fec7d001f2ad8949125fa8eee
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/22/2021
ms.locfileid: "53055268"
---
# <a name="application-guard-for-office-for-admins"></a><span data-ttu-id="b306d-105">관리자를 위한 Office Application Guard</span><span class="sxs-lookup"><span data-stu-id="b306d-105">Application Guard for Office for admins</span></span>

<span data-ttu-id="b306d-106">**다음에 적용됩니다.** Word, Excel 및 Microsoft 365용 PowerPoint Windows 10 Enterprise</span><span class="sxs-lookup"><span data-stu-id="b306d-106">**Applies to:** Word, Excel, and PowerPoint for Microsoft 365, Windows 10 Enterprise</span></span>

<span data-ttu-id="b306d-107">Microsoft Defender Application Guard (Office Application Guard for Office)를 사용하면 신뢰할 수 없는 파일이 신뢰할 수 있는 리소스에 액세스하지 못하게 하여 엔터프라이즈를 새로운 공격으로부터 안전하게 보호할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b306d-107">Microsoft Defender Application Guard for Office (Application Guard for Office) helps prevent untrusted files from accessing trusted resources, keeping your enterprise safe from new and emerging attacks.</span></span> <span data-ttu-id="b306d-108">이 문서에서는 관리자에게 응용 프로그램 보호의 미리 보기를 위해 디바이스를 설정하는 Office.</span><span class="sxs-lookup"><span data-stu-id="b306d-108">This article walks admins through setting up devices for a preview of Application Guard for Office.</span></span> <span data-ttu-id="b306d-109">디바이스에서 Application Guard를 사용하도록 설정하기 위한 시스템 요구 사항 및 설치 Office 정보를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="b306d-109">It provides information about system requirements and installation steps to enable Application Guard for Office on a device.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="b306d-110">필수 구성 요소</span><span class="sxs-lookup"><span data-stu-id="b306d-110">Prerequisites</span></span>

### <a name="minimum-hardware-requirements"></a><span data-ttu-id="b306d-111">최소 하드웨어 요구 사항</span><span class="sxs-lookup"><span data-stu-id="b306d-111">Minimum hardware requirements</span></span>

* <span data-ttu-id="b306d-112">**CPU**: 64비트, 4코어(실제 또는 가상), 가상화 확장(Intel VT-x OR AMD-V), Core i5 이상 권장</span><span class="sxs-lookup"><span data-stu-id="b306d-112">**CPU**: 64-bit, 4 cores (physical or virtual), virtualization extensions (Intel VT-x OR AMD-V), Core i5 equivalent or higher recommended</span></span>
* <span data-ttu-id="b306d-113">**실제 메모리:** 8GB RAM</span><span class="sxs-lookup"><span data-stu-id="b306d-113">**Physical memory**: 8-GB RAM</span></span>
* <span data-ttu-id="b306d-114">**하드 디스크:** 시스템 드라이브에 10GB의 사용 공간(SSD 권장)</span><span class="sxs-lookup"><span data-stu-id="b306d-114">**Hard disk**: 10 GB of free space on the system drive (SSD recommended)</span></span>

### <a name="minimum-software-requirements"></a><span data-ttu-id="b306d-115">최소 소프트웨어 요구 사항</span><span class="sxs-lookup"><span data-stu-id="b306d-115">Minimum software requirements</span></span>

* <span data-ttu-id="b306d-116">**Windows 10**: Windows 10 Enterprise 버전, 클라이언트 빌드 버전 2004(20H1) 빌드 19041 이상</span><span class="sxs-lookup"><span data-stu-id="b306d-116">**Windows 10**: Windows 10 Enterprise edition, Client Build version 2004 (20H1) build 19041 or later</span></span>
* <span data-ttu-id="b306d-117">**Office**: Office 채널 및 월별 Enterprise 채널 빌드 버전 2011 16.0.13530.10000 이상을 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="b306d-117">**Office**: Office Current Channel and Monthly Enterprise Channel, Build version 2011 16.0.13530.10000 or later.</span></span> <span data-ttu-id="b306d-118">32비트 및 64비트 버전의 Office 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="b306d-118">Both 32-bit and 64-bit versions of Office are supported.</span></span>
* <span data-ttu-id="b306d-119">**업데이트 패키지:** Windows 10 월별 누적 보안 업데이트 [KB4571756](https://support.microsoft.com/help/4571756/windows-10-update-KB4571756)</span><span class="sxs-lookup"><span data-stu-id="b306d-119">**Update package**: Windows 10 cumulative monthly security update [KB4571756](https://support.microsoft.com/help/4571756/windows-10-update-KB4571756)</span></span>

<span data-ttu-id="b306d-120">자세한 시스템 요구 사항은 에 대한 시스템 요구 [Microsoft Defender Application Guard.](/windows/security/threat-protection/microsoft-defender-application-guard/reqs-md-app-guard)</span><span class="sxs-lookup"><span data-stu-id="b306d-120">For detailed system requirements, refer to [System requirements for Microsoft Defender Application Guard](/windows/security/threat-protection/microsoft-defender-application-guard/reqs-md-app-guard).</span></span> <span data-ttu-id="b306d-121">또한 가상화 기술을 사용하도록 설정하는 방법에 대한 컴퓨터 제조업체 가이드를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="b306d-121">Also, please refer to your computer manufacturer's guides on how to enable virtualization technology.</span></span>
<span data-ttu-id="b306d-122">업데이트 채널에 대한 Office 자세한 내용은 에 대한 업데이트 채널 [개요를 Microsoft 365.](/deployoffice/overview-update-channels)</span><span class="sxs-lookup"><span data-stu-id="b306d-122">To learn more about Office update channels, see [Overview of update channels for Microsoft 365](/deployoffice/overview-update-channels).</span></span>

### <a name="licensing-requirements"></a><span data-ttu-id="b306d-123">라이선스 요구사항</span><span class="sxs-lookup"><span data-stu-id="b306d-123">Licensing requirements</span></span>

* <span data-ttu-id="b306d-124">Microsoft 365 E5 Microsoft 365 E5 Security</span><span class="sxs-lookup"><span data-stu-id="b306d-124">Microsoft 365 E5 or Microsoft 365 E5 Security</span></span>

## <a name="deploy-application-guard-for-office"></a><span data-ttu-id="b306d-125">응용 프로그램용 Application Guard Office</span><span class="sxs-lookup"><span data-stu-id="b306d-125">Deploy Application Guard for Office</span></span>

### <a name="enable-application-guard-for-office"></a><span data-ttu-id="b306d-126">응용 프로그램에 대해 Application Guard를 Office</span><span class="sxs-lookup"><span data-stu-id="b306d-126">Enable Application Guard for Office</span></span>

1. <span data-ttu-id="b306d-127">월별 **누적 Windows 10 업데이트 KB4571756을** 다운로드하여 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="b306d-127">Download and install **Windows 10 cumulative monthly security updates KB4571756**.</span></span>

2. <span data-ttu-id="b306d-128">기능 **Microsoft Defender Application Guard** 아래에서 Windows 선택하고 확인 을 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="b306d-128">Select **Microsoft Defender Application Guard** under Windows Features and  select **OK**.</span></span> <span data-ttu-id="b306d-129">Application Guard 기능을 사용하도록 설정하면 시스템 재부팅이 묻습니다.</span><span class="sxs-lookup"><span data-stu-id="b306d-129">Enabling the Application Guard feature will prompt a system reboot.</span></span> <span data-ttu-id="b306d-130">지금 다시 시작하거나 3단계 후에 재부팅할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b306d-130">You can choose to reboot now or after step 3.</span></span>

   ![Windows AG를 보여 주며 기능 대화 상자](../../media/ag03-deploy.png)

   <span data-ttu-id="b306d-132">다음 PowerShell 명령을 관리자 권한으로 실행하여 이 기능을 사용할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b306d-132">The feature can also be enabled by running the following PowerShell command as administrator:</span></span>

   ```powershell
   Enable-WindowsOptionalFeature -online -FeatureName Windows-Defender-ApplicationGuard
   ```

3. <span data-ttu-id="b306d-133">관리 **모드에서** Microsoft Defender Application Guard 검색합니다. 컴퓨터 구성 관리 템플릿 및 구성 요소 Windows **그룹 \\ \\ \\ Microsoft Defender Application Guard.**</span><span class="sxs-lookup"><span data-stu-id="b306d-133">Search for **Microsoft Defender Application Guard in Managed Mode**, a group policy in **Computer Configuration\\Administrative Templates\\Windows Components\\Microsoft Defender Application Guard**.</span></span> <span data-ttu-id="b306d-134">옵션에서 값을 2 또는 **3으로** 설정한 다음 확인 또는 적용 **을** 선택하여 이 **정책을** **켜야 합니다.**</span><span class="sxs-lookup"><span data-stu-id="b306d-134">Turn on this policy by setting the value under Options as **2** or **3**, and then selecting **OK** or **Apply**.</span></span>

   ![관리 모드에서 AG 켜기](../../media/ag04-deploy.png)

   <span data-ttu-id="b306d-136">대신 해당 CSP 정책을 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b306d-136">Instead, you can set the corresponding CSP policy:</span></span>

   > <span data-ttu-id="b306d-137">OMA-URI: **./Device/Vendor/MSFT/WindowsDefenderApplicationGuard/설정/AllowWindowsDefenderApplicationGuard**</span><span class="sxs-lookup"><span data-stu-id="b306d-137">OMA-URI: **./Device/Vendor/MSFT/WindowsDefenderApplicationGuard/Settings/AllowWindowsDefenderApplicationGuard**</span></span> <br> <span data-ttu-id="b306d-138">데이터 형식: **정수**</span><span class="sxs-lookup"><span data-stu-id="b306d-138">Data type: **Integer**</span></span> <br> <span data-ttu-id="b306d-139">값: **2**</span><span class="sxs-lookup"><span data-stu-id="b306d-139">Value: **2**</span></span>

4. <span data-ttu-id="b306d-140">시스템을 다시 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="b306d-140">Restart the system.</span></span>

### <a name="set-diagnostics--feedback-to-send-full-data"></a><span data-ttu-id="b306d-141">진단 & 피드백을 설정하여 전체 데이터 보내기</span><span class="sxs-lookup"><span data-stu-id="b306d-141">Set Diagnostics & feedback to send full data</span></span>

> [!NOTE]
> <span data-ttu-id="b306d-142">이 요구 사항이 필요하지는 않습니다. 그러나 선택적 진단 데이터를 구성하면 보고된 문제를 진단하는 데 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b306d-142">This is not required, however, configuring optional diagnostics data will help diagnose reported issues.</span></span>

<span data-ttu-id="b306d-143">이 단계를 통해 문제를 식별하고 해결하는 데 필요한 데이터가 Microsoft에 도달하는지 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b306d-143">This step ensures that the data necessary to identify and fix problems is reaching Microsoft.</span></span> <span data-ttu-id="b306d-144">디바이스에서 진단을 사용하도록 설정하려면 다음 Windows 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="b306d-144">Follow these steps to enable diagnostics on your Windows device:</span></span>

1. <span data-ttu-id="b306d-145">창에서 **설정** 열 시작 메뉴.</span><span class="sxs-lookup"><span data-stu-id="b306d-145">Open **Settings** from the Start menu.</span></span>

   ![시작 메뉴](../../media/ag05-diagnostic.png)

2. <span data-ttu-id="b306d-147">에서 **Windows 설정** 개인 정보를 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="b306d-147">On **Windows Settings**, select **Privacy**.</span></span>

   ![Windows 설정 메뉴](../../media/ag06-diagnostic.png)

3. <span data-ttu-id="b306d-149">개인 정보 보호에서 진단 및 **& 선택적** **진단 데이터를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="b306d-149">Under Privacy, select **Diagnostics & feedback** and select **Optional diagnostic data**.</span></span>

   ![진단 및 피드백 메뉴](../../media/ag07a-diagnostic.png)

<span data-ttu-id="b306d-151">진단 설정을 구성하는 Windows 자세한 내용은 조직에서 Windows 진단 데이터 구성을 [참조하세요.](/windows/privacy/configure-windows-diagnostic-data-in-your-organization#enterprise-management)</span><span class="sxs-lookup"><span data-stu-id="b306d-151">For more on configuring Windows diagnostic settings, refer to [Configuring Windows diagnostic data in your organization](/windows/privacy/configure-windows-diagnostic-data-in-your-organization#enterprise-management).</span></span>

### <a name="confirm-that-application-guard-for-office-is-enabled-and-working"></a><span data-ttu-id="b306d-152">응용 프로그램용 Application Guard가 Office 사용 및 작동 확인</span><span class="sxs-lookup"><span data-stu-id="b306d-152">Confirm that Application Guard for Office is enabled and working</span></span>

<span data-ttu-id="b306d-153">정책에 대한 Application Guard가 Office 사용하도록 설정되어 있는지 확인하기 전에 정책이 배포된 Excel 또는 PowerPoint Word를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="b306d-153">Before confirming that Application Guard for Office is enabled, launch Word, Excel, or PowerPoint on a device where the policies have been deployed.</span></span> <span data-ttu-id="b306d-154">활성화된 Office 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="b306d-154">Make sure Office is activated.</span></span> <span data-ttu-id="b306d-155">먼저 작업 ID를 사용하여 Office 정품 인증해야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b306d-155">You may need to use your work identity to activate the Office product first.</span></span>

<span data-ttu-id="b306d-156">응용 프로그램에 대한 Application Guard가 Office Word, Excel 또는 PowerPoint 시작한 다음, 트러설되지 않은 문서를 여는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="b306d-156">To confirm that Application Guard for Office is enabled, launch Word, Excel, or PowerPoint, and then open an untrusted document.</span></span> <span data-ttu-id="b306d-157">예를 들어 인터넷에서 다운로드한 문서나 조직 외부의 사용자가 전자 메일 첨부 파일을 열 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b306d-157">For example, you can open a document that was downloaded from the internet or an email attachment from someone outside your organization.</span></span>

<span data-ttu-id="b306d-158">처음에 트러설이 없는 파일을 열면 다음 예제와 Office 시작 화면이 표시될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b306d-158">When you first open an untrusted file, you may see an Office splash screen like the following example.</span></span> <span data-ttu-id="b306d-159">이 파일은 응용 프로그램에 대한 Application Guard가 활성화되고 Office 파일이 열리면서 몇 시간 동안 표시될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b306d-159">It might be displayed for some time while Application Guard for Office is being activated and the file is being opened.</span></span> <span data-ttu-id="b306d-160">이후에는 더 빠르게 파일을 열 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b306d-160">Subsequent openings of untrusted files should be faster.</span></span>

![Office 앱 시작 화면](../../media/ag08-confirm.png)

<span data-ttu-id="b306d-162">파일을 열면 파일에 다음을 위해 Application Guard 내에서 파일이 열렸다는 몇 가지 시각적 표시기가 Office.</span><span class="sxs-lookup"><span data-stu-id="b306d-162">Upon being opened, the file should display a few visual indicators that the file was opened inside Application Guard for Office:</span></span>

* <span data-ttu-id="b306d-163">리본 메뉴의 콜아웃</span><span class="sxs-lookup"><span data-stu-id="b306d-163">A callout in the ribbon</span></span>

  ![작은 App Guard 메모를 표시하는 Doc 파일](../../media/ag09-confirm.png)

* <span data-ttu-id="b306d-165">작업 표시줄에 방패가 있는 응용 프로그램 아이콘</span><span class="sxs-lookup"><span data-stu-id="b306d-165">The application icon with a shield in the taskbar</span></span>

  ![작업 표시줄의 아이콘](../../media/ag12-limitations.png)

## <a name="configure-application-guard-for-office"></a><span data-ttu-id="b306d-167">사용자에 대해 Application Guard Office</span><span class="sxs-lookup"><span data-stu-id="b306d-167">Configure Application Guard for Office</span></span>

<span data-ttu-id="b306d-168">Office 응용 프로그램에 대해 Application Guard의 기능을 구성할 수 있도록 다음 정책을 Office.</span><span class="sxs-lookup"><span data-stu-id="b306d-168">Office supports the following policies to enable you to configure the capabilities of Application Guard for Office.</span></span> <span data-ttu-id="b306d-169">이러한 정책은 그룹 정책 또는 클라우드 정책 서비스 를 통해 Office [수 있습니다.](/DeployOffice/overview-office-cloud-policy-service)</span><span class="sxs-lookup"><span data-stu-id="b306d-169">These policies can be configured through Group policies or through the [Office cloud policy service](/DeployOffice/overview-office-cloud-policy-service).</span></span>


> [!NOTE]
> <span data-ttu-id="b306d-170">이러한 정책을 구성하면 응용 프로그램 보호에서 열 수 있는 파일의 일부 기능을 사용하지 않도록 설정할 수 Office.</span><span class="sxs-lookup"><span data-stu-id="b306d-170">Configuring these policies can disable some functionalities for files opened in Application Guard for Office.</span></span>

|<span data-ttu-id="b306d-171">정책</span><span class="sxs-lookup"><span data-stu-id="b306d-171">Policy</span></span>|<span data-ttu-id="b306d-172">설명</span><span class="sxs-lookup"><span data-stu-id="b306d-172">Description</span></span>|
|---|---|
|<span data-ttu-id="b306d-173">응용 프로그램에 Application Guard를 사용하지 Office</span><span class="sxs-lookup"><span data-stu-id="b306d-173">Don't use Application Guard for Office</span></span>|<span data-ttu-id="b306d-174">이 정책을 사용하도록 설정하면 Word, Excel 및 PowerPoint 컨테이너에 대해 Application Guard 대신 보호된 보기 Office.</span><span class="sxs-lookup"><span data-stu-id="b306d-174">Enabling this policy will force Word, Excel, and PowerPoint to use the Protected View isolation container instead of Application Guard for Office.</span></span> <span data-ttu-id="b306d-175">이 정책은 응용 프로그램에 대해 사용하도록 설정된 Office 때 응용 프로그램에 대해 Application Guard를 일시적으로 사용하지 않도록 설정하는 데 사용할 수 Microsoft Edge.</span><span class="sxs-lookup"><span data-stu-id="b306d-175">This policy can be used to temporarily disable Application Guard for Office when there are issues in leaving it enabled for Microsoft Edge.</span></span>|
|<span data-ttu-id="b306d-176">컨테이너 사전 Office Application Guard 구성</span><span class="sxs-lookup"><span data-stu-id="b306d-176">Configure Application Guard for Office container pre-creation</span></span>|<span data-ttu-id="b306d-177">이 정책은 런타시 성능 향상을 위해 Office 파일을 확인하는 응용 프로그램 컨테이너에 대한 Application Guard가 미리 만들어질지 여부를 판단합니다.</span><span class="sxs-lookup"><span data-stu-id="b306d-177">This policy determines if the Application Guard for Office container, for isolating untrusted files, is pre-created for improved run-time performance.</span></span> <span data-ttu-id="b306d-178">이 설정을 사용하도록 설정하는 경우 컨테이너를 계속 미리 만들 일 수를 지정하거나 컨테이너를 기본 제공 Office 미리 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b306d-178">If you enable this setting, you can specify the number of days to continue pre-creating a container or let the Office built-in heuristic pre-create the container.</span></span>
|<span data-ttu-id="b306d-179">응용 프로그램 보호에서 열 수 있는 Office 복사/붙여넣기 허용 안 Office</span><span class="sxs-lookup"><span data-stu-id="b306d-179">Don't allow copy/paste for Office documents opened in Application Guard for Office</span></span>|<span data-ttu-id="b306d-180">이 정책을 사용하도록 설정하면 사용자가 Application Guard에서 연 문서의 콘텐츠를 복사하여 외부에서 연 문서에 Office 복사하여 붙여넣을 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="b306d-180">Enabling this policy will prevent a user from copying and pasting content from a document opened in Application Guard for Office to a document opened outside of it.</span></span>|
|<span data-ttu-id="b306d-181">Application Guard에서 하드웨어 가속을 사용하지 않도록 Office</span><span class="sxs-lookup"><span data-stu-id="b306d-181">Disable hardware acceleration in Application Guard for Office</span></span>|<span data-ttu-id="b306d-182">이 정책은 하드웨어 가속을 사용하여 그래픽을 Office Application Guard를 사용할지 여부를 제어합니다.</span><span class="sxs-lookup"><span data-stu-id="b306d-182">This policy controls whether Application Guard for Office uses hardware acceleration to render graphics.</span></span> <span data-ttu-id="b306d-183">이 설정을 사용하면 Office Application Guard는 소프트웨어 기반(CPU) 렌더링을 사용하며 타사 그래픽 드라이버를 로드하거나 연결된 그래픽 하드웨어와 상호 작용하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="b306d-183">If you enable this setting, Application Guard for Office uses software-based (CPU) rendering and won't load any third-party graphics drivers or interact with any connected graphics hardware.</span></span>
|<span data-ttu-id="b306d-184">Application Guard에서 지원되지 않는 파일 형식 보호를 사용하지 않도록 Office</span><span class="sxs-lookup"><span data-stu-id="b306d-184">Disable unsupported file types protection in Application Guard for Office</span></span>|<span data-ttu-id="b306d-185">이 정책은 Office Application Guard가 지원되지 않는 파일 형식을 열지 못하도록 차단할지 아니면 보호된 보기로 리디렉션할지 여부를 제어합니다.</span><span class="sxs-lookup"><span data-stu-id="b306d-185">This policy controls whether Application Guard for Office will block unsupported file types from being opened or if it will enable the redirection to Protected View.</span></span>
|<span data-ttu-id="b306d-186">Application Guard에서 열고 있는 문서에 대한 카메라 및 마이크 액세스를 Office</span><span class="sxs-lookup"><span data-stu-id="b306d-186">Turn off camera and microphone access for documents opened in Application Guard for Office</span></span>|<span data-ttu-id="b306d-187">이 정책을 사용하도록 설정하면 Office Application Guard 내부의 카메라 및 마이크에 대한 액세스 권한이 Office.</span><span class="sxs-lookup"><span data-stu-id="b306d-187">Enabling this policy will remove Office access to the camera and microphone inside Application Guard for Office.</span></span>|
|<span data-ttu-id="b306d-188">응용 프로그램 보호에서 열 수 있는 문서에서 인쇄를 Office</span><span class="sxs-lookup"><span data-stu-id="b306d-188">Restrict printing from documents opened in Application Guard for Office</span></span>|<span data-ttu-id="b306d-189">이 정책을 사용하도록 설정하면 사용자가 응용 프로그램 보호에서 열 수 있는 파일에서 인쇄할 수 있는 프린터가 Office.</span><span class="sxs-lookup"><span data-stu-id="b306d-189">Enabling this policy will limit the printers that a user can print to from a file opened in Application Guard for Office.</span></span> <span data-ttu-id="b306d-190">예를 들어 이 정책을 사용하여 사용자가 PDF로만 인쇄하도록 제한할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b306d-190">For example, you can use this policy to restrict users to only print to PDF.</span></span>|
|<span data-ttu-id="b306d-191">사용자가 파일 보호를 위해 Application Guard를 Office 방지</span><span class="sxs-lookup"><span data-stu-id="b306d-191">Prevent users from removing Application Guard for Office protection on files</span></span>|<span data-ttu-id="b306d-192">이 정책을 사용하면 Office 응용 프로그램 환경 내에서 Application Guard를 사용하지 않도록 설정하거나 Office 보호를 위해 Application Guard 외부에서 파일을 열 수 있는 옵션이 Office.</span><span class="sxs-lookup"><span data-stu-id="b306d-192">Enabling this policy will remove the option (within the Office application experience) to disable Application Guard for Office protection or to open a file outside Application Guard for Office.</span></span> <p> <span data-ttu-id="b306d-193">**참고:** 사용자는 파일에서 웹 표시 속성을 수동으로 제거하거나 문서를 신뢰할 수 있는 위치로 이동하여 이 정책을 무시할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b306d-193">**Note:** Users can still bypass this policy by manually removing the mark-of-the-web property from the file or by moving a document to a Trusted location.</span></span>|
|

> [!NOTE]
> <span data-ttu-id="b306d-194">다음 정책을 적용하려면 사용자가 로그인한 후 다시 Windows 합니다.</span><span class="sxs-lookup"><span data-stu-id="b306d-194">The following policies will require the user to sign out and sign in again to Windows to take effect:</span></span>
>
> * <span data-ttu-id="b306d-195">Application Guard에서 열 수 있는 문서에 대해 복사/붙여넣기 사용 안 Office</span><span class="sxs-lookup"><span data-stu-id="b306d-195">Disable copy/paste for documents opened in Application Guard for Office</span></span>
> * <span data-ttu-id="b306d-196">Application Guard에서 열 수 있는 문서에 대해 인쇄를 Office</span><span class="sxs-lookup"><span data-stu-id="b306d-196">Restrict printing for documents opened in Application Guard for Office</span></span>
> * <span data-ttu-id="b306d-197">Application Guard에서 열 수 있는 문서에 대한 카메라 및 마이크 액세스를 Office</span><span class="sxs-lookup"><span data-stu-id="b306d-197">Turn off camera and mic access to documents opened in Application Guard for Office</span></span>

## <a name="submit-feedback"></a><span data-ttu-id="b306d-198">피드백 제출</span><span class="sxs-lookup"><span data-stu-id="b306d-198">Submit feedback</span></span>

### <a name="submit-feedback-via-feedback-hub"></a><span data-ttu-id="b306d-199">피드백 허브를 통해 피드백 제출</span><span class="sxs-lookup"><span data-stu-id="b306d-199">Submit feedback via Feedback Hub</span></span>

<span data-ttu-id="b306d-200">사용자에 대해 Application Guard를 Office 발생하는 경우 피드백 허브를 통해 피드백을 제출하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="b306d-200">If you encounter any issues when launching Application Guard for Office, you're encouraged to submit your feedback via Feedback Hub:</span></span>

1. <span data-ttu-id="b306d-201">피드백 허브 **앱을 열고** 로그인합니다.</span><span class="sxs-lookup"><span data-stu-id="b306d-201">Open the **Feedback Hub app** and sign in.</span></span>

2. <span data-ttu-id="b306d-202">Application Guard를 시작하는 동안 오류 대화 상자가 발생하는 경우 오류 대화 상자에서 **Microsoft에 보고를** 선택하여 새 피드백 제출을 시작하십시오.</span><span class="sxs-lookup"><span data-stu-id="b306d-202">If you get an error dialog while launching Application Guard, select **Report to Microsoft** in the error dialog to start a new feedback submission.</span></span> <span data-ttu-id="b306d-203">그렇지 않은 경우 Application Guard에 대한 올바른 범주를 선택한 다음 오른쪽 상단 근처에서 새 <https://aka.ms/mdagoffice-fb> **+ &nbsp; 피드백** 추가를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="b306d-203">Otherwise, navigate to <https://aka.ms/mdagoffice-fb> to select the correct category for Application Guard, then select **+&nbsp;Add new feedback** near the top right.</span></span>

3. <span data-ttu-id="b306d-204">사용자 의견이 아직  입력되지 않은 경우 요약 상자에 요약을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="b306d-204">Enter a summary in the **Summarize your feedback** box if it isn't already filled in for you.</span></span>

4. <span data-ttu-id="b306d-205">경험한 문제 및 자세한 내용 설명 상자에 수행한  단계에 대한 자세한 설명을 입력하고 다음 을 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="b306d-205">Enter a detailed description of the issue that you experienced and what steps you took in the **Explain in more detail** box, then select **Next**.</span></span>

5. <span data-ttu-id="b306d-206">문제 옆에 있는 거품을 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="b306d-206">Select the bubble next to **Problem**.</span></span> <span data-ttu-id="b306d-207">선택한 범주가 보안 및 개인 정보 보호 Microsoft Defender Application Guard – Office 있는지 확인한 후 다음 **\> 을** **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="b306d-207">Make sure the category selected is **Security and Privacy \> Microsoft Defender Application Guard – Office**, then select **Next**.</span></span>

6. <span data-ttu-id="b306d-208">새 **피드백,** 다음 을 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="b306d-208">Select **New feedback**, then **Next**.</span></span>

7. <span data-ttu-id="b306d-209">이 문제의 추적을 수집합니다.</span><span class="sxs-lookup"><span data-stu-id="b306d-209">Collect traces about the issue:</span></span>

   1. <span data-ttu-id="b306d-210">내 문제 **다시 발생 타일을 확장합니다.**</span><span class="sxs-lookup"><span data-stu-id="b306d-210">Expand the **Recreate my problem** tile.</span></span>

   2. <span data-ttu-id="b306d-211">Application Guard가 실행되는 동안 발생하는 문제가 발생하면 Application Guard 인스턴스를 여는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="b306d-211">If the issue you're experiencing occurs while Application Guard is running, open an Application Guard instance.</span></span> <span data-ttu-id="b306d-212">인스턴스를 열면 Application Guard 컨테이너 내에서 추가 추적을 수집할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b306d-212">Opening an instance allows additional traces to be collected from within the Application Guard container.</span></span>

   3. <span data-ttu-id="b306d-213">녹음 **시작 을** 선택하고 타일이 회전을 중지할 때까지 기다렸다가 기록 *중지라고 말합니다.*</span><span class="sxs-lookup"><span data-stu-id="b306d-213">Select **Start recording**, and wait for the tile to stop spinning and say *Stop recording*.</span></span>

   4. <span data-ttu-id="b306d-214">Application Guard에서 문제를 완전히 재현합니다.</span><span class="sxs-lookup"><span data-stu-id="b306d-214">Fully reproduce the issue with Application Guard.</span></span> <span data-ttu-id="b306d-215">다시 생성에는 Application Guard 인스턴스를 시작하려고 시도하고 실패할 때까지 기다리거나 실행 중인 Application Guard 인스턴스에서 문제를 재현하는 것이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="b306d-215">Reproduction might include attempting to launch an Application Guard instance and waiting until it fails, or reproducing an issue in a running Application Guard instance.</span></span>

   5. <span data-ttu-id="b306d-216">녹음 중지 **타일을** 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="b306d-216">Select the **Stop recording** tile.</span></span>

   6. <span data-ttu-id="b306d-217">컨테이너 진단을 수집할 수 있도록 제출 후 몇 분 동안에도 실행 중인 Application Guard 인스턴스를 열어 웁니다.</span><span class="sxs-lookup"><span data-stu-id="b306d-217">Keep any running Application Guard instance(s) open, even for a few minutes after submission, so that container diagnostics can also be collected.</span></span>

8. <span data-ttu-id="b306d-218">문제와 관련된 스크린샷 또는 파일을 첨부합니다.</span><span class="sxs-lookup"><span data-stu-id="b306d-218">Attach any relevant screenshots or files related to the problem.</span></span>

9. <span data-ttu-id="b306d-219">**전송** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="b306d-219">Select **Submit**.</span></span>

### <a name="submit-feedback-via-office-customer-voice"></a><span data-ttu-id="b306d-220">고객 음성을 통해 Office 제출</span><span class="sxs-lookup"><span data-stu-id="b306d-220">Submit feedback via Office Customer Voice</span></span>

<span data-ttu-id="b306d-221">또한 Application Guard에서 문서를 열 때 문제가 Office 피드백을 Office 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b306d-221">You may also submit feedback from within Office if the issue happens when Office documents are opened in Application Guard.</span></span> <span data-ttu-id="b306d-222">피드백을 [제출하는 Office](https://insider.office.com/handbook) 자세한 내용은 내부자 참고자용 문서입니다.</span><span class="sxs-lookup"><span data-stu-id="b306d-222">Refer to the [Office Insider Handbook](https://insider.office.com/handbook) for submitting feedback.</span></span>

## <a name="integration-with-microsoft-defender-for-endpoint-and-microsoft-defender-for-office-365"></a><span data-ttu-id="b306d-223">Endpoint용 Microsoft Defender 및 Microsoft Defender for Office 365</span><span class="sxs-lookup"><span data-stu-id="b306d-223">Integration with Microsoft Defender for Endpoint and Microsoft Defender for Office 365</span></span>

<span data-ttu-id="b306d-224">Application Guard for Office Microsoft Defender for Endpoint와 통합되어 격리된 환경에서 발생하는 악의적인 활동에 대한 모니터링 및 경고를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="b306d-224">Application Guard for Office is integrated with Microsoft Defender for Endpoint to provide monitoring and alerting on malicious activity that happens in the isolated environment.</span></span>

<span data-ttu-id="b306d-225">[금고 Microsoft E365 E5의](/microsoft-365/security/office-365-security/safe-docs) 문서는 Microsoft Defender for Endpoint를 사용하여 Application Guard에서 열 수 있는 문서를 검색하는 Office.</span><span class="sxs-lookup"><span data-stu-id="b306d-225">[Safe Documents in Microsoft E365 E5](/microsoft-365/security/office-365-security/safe-docs) is a feature that uses Microsoft Defender for Endpoint to scan documents opened in Application Guard for Office.</span></span> <span data-ttu-id="b306d-226">추가 보호 계층을 위해 사용자는 검사 결과가 결정될 때까지 Office 응용 프로그램 보호를 떠날 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="b306d-226">For an additional layer of protection, users can't leave Application Guard for Office until the results of the scan have been determined.</span></span>

<span data-ttu-id="b306d-227">끝점용 Microsoft Defender는 엔터프라이즈 네트워크가 고급 위협을 방지, 감지, 조사 및 대응하는 데 도움이 하도록 설계된 보안 플랫폼입니다.</span><span class="sxs-lookup"><span data-stu-id="b306d-227">Microsoft Defender for Endpoint is a security platform designed to help enterprise networks prevent, detect, investigate, and respond to advanced threats.</span></span> <span data-ttu-id="b306d-228">이 플랫폼에 대한 자세한 내용은 [끝점용 Microsoft Defender를 참조합니다.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp)</span><span class="sxs-lookup"><span data-stu-id="b306d-228">For more details about this platform, see [Microsoft Defender for Endpoint](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp).</span></span> <span data-ttu-id="b306d-229">이 플랫폼에 장치 온보딩에 대한 자세한 내용은 [끝점 서비스용 Microsoft Defender에](/windows/security/threat-protection/microsoft-defender-atp/onboard-configure)장치 온보딩을 참조합니다.</span><span class="sxs-lookup"><span data-stu-id="b306d-229">To learn more about onboarding devices to this platform, see [Onboard devices to the Microsoft Defender for Endpoint service](/windows/security/threat-protection/microsoft-defender-atp/onboard-configure).</span></span>

<span data-ttu-id="b306d-230">끝점용 Defender와 함께 작동하도록 Microsoft Defender를 Office 365 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b306d-230">You can also configure Microsoft Defender for Office 365 to work with Defender for Endpoint.</span></span> <span data-ttu-id="b306d-231">자세한 내용은 [Endpoint용 Microsoft Defender와 Office 365 Defender 통합을 참조하세요.](integrate-office-365-ti-with-mde.md)</span><span class="sxs-lookup"><span data-stu-id="b306d-231">For more info, refer to [Integrate Defender for Office 365 with Microsoft Defender for Endpoint](integrate-office-365-ti-with-mde.md).</span></span>

## <a name="limitations-and-considerations"></a><span data-ttu-id="b306d-232">제한 사항 및 고려 사항</span><span class="sxs-lookup"><span data-stu-id="b306d-232">Limitations and considerations</span></span>

* <span data-ttu-id="b306d-233">Office Application Guard는 신뢰할 수 있는 회사 리소스, 인트라넷, 사용자의 ID 및 컴퓨터의 임의 파일에 액세스할 수 없는 신뢰할 수 없는 문서를 격리하는 보호 모드입니다.</span><span class="sxs-lookup"><span data-stu-id="b306d-233">Application Guard for Office is a protected mode that isolates untrusted documents so that they can't access trusted corporate resources, an intranet, the user's identity, and arbitrary files on the computer.</span></span> <span data-ttu-id="b306d-234">따라서 사용자가 디스크에 로컬 파일에서 그림을 삽입하는 등 액세스에 종속된 기능에 액세스하면 액세스가 실패하고 다음 예제와 같은 프롬프트가 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="b306d-234">As a result, if a user tries to access a feature that has a dependency on such access—for example, inserting a picture from a local file on disk—the access will fail and produce a prompt like the following example.</span></span> <span data-ttu-id="b306d-235">신뢰할 수 없는 문서가 신뢰할 수 있는 리소스에 액세스할 수 있도록 설정하려면 사용자가 문서에서 Application Guard 보호를 제거해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b306d-235">To enable an untrusted document to access trusted resources, users must remove Application Guard protection from the document.</span></span>

  ![안전한 유지를 위해 이 기능을 사용할 수 없는 경우를 설명하는 대화 상자](../../media/ag10-limitations.png)

  > [!NOTE]
  > <span data-ttu-id="b306d-237">사용자가 파일과 해당 원본을 신뢰할 수 있는 경우 또는 보호가 어디에서 왔는지만 보호를 제거해보는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="b306d-237">Advise users to only remove protection if they trust the file and its source or where it came from.</span></span>

* <span data-ttu-id="b306d-238">매크로 및 ActiveX 같은 문서의 활성 콘텐츠는 Application Guard에서 사용할 수 Office.</span><span class="sxs-lookup"><span data-stu-id="b306d-238">Active content in documents like macros and ActiveX controls are disabled in Application Guard for Office.</span></span> <span data-ttu-id="b306d-239">사용자가 활성 콘텐츠를 사용하도록 설정하려면 Application Guard 보호를 제거해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b306d-239">Users need to remove Application Guard protection to enable active content.</span></span>

* <span data-ttu-id="b306d-240">다른 조직의 네트워크 공유 또는 OneDrive, 비즈니스용 OneDrive 또는 SharePoint Online에서 공유하는 파일 또는 네트워크 공유의 트러설되지 않은 파일은 Application Guard에서 읽기 전용으로 열립니다.</span><span class="sxs-lookup"><span data-stu-id="b306d-240">Untrusted files from network shares or files shared from OneDrive, OneDrive for Business, or SharePoint Online from a different organization open as read-only in Application Guard.</span></span> <span data-ttu-id="b306d-241">사용자는 이러한 파일의 로컬 복사본을 저장하여 컨테이너에서 작업을 계속하거나 보호 기능을 제거하여 원본 파일을 직접 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b306d-241">Users can save a local copy of such files to continue working in the container or remove protection to directly work with the original file.</span></span>

* <span data-ttu-id="b306d-242">IRM(정보 권한 관리)으로 보호되는 파일은 기본적으로 차단됩니다.</span><span class="sxs-lookup"><span data-stu-id="b306d-242">Files that are protected by Information Rights Management (IRM) are blocked by default.</span></span> <span data-ttu-id="b306d-243">사용자가 이러한 파일을 보호된 보기에서 열기 위해 관리자는 조직에서 지원되지 않는 파일 형식에 대한 정책 설정을 구성해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b306d-243">If users want to open such files in Protected View, an administrator must configure policy settings for unsupported file types for the organization.</span></span>

* <span data-ttu-id="b306d-244">Office 응용 프로그램에 대한 사용자 지정은 Office 사용자가 로그인한 후 또는 장치를 다시 시작한 후에도 지속되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="b306d-244">Any customizations to Office applications in Application Guard for Office won't persist after a user signs out and signs in again or after the device restarts.</span></span>

* <span data-ttu-id="b306d-245">UIA 프레임워크를 사용하는 접근성 도구만 Application Guard에서 열 수 있는 파일에 액세스할 수 있는 환경을 Office.</span><span class="sxs-lookup"><span data-stu-id="b306d-245">Only Accessibility tools that use the UIA framework can provide an accessible experience for files opened in Application Guard for Office.</span></span>

* <span data-ttu-id="b306d-246">설치 후 Application Guard를 처음 시작하려면 네트워크 연결이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="b306d-246">Network connectivity is required for the first launch of Application Guard after installation.</span></span> <span data-ttu-id="b306d-247">라이선스의 유효성을 검사하려면 Application Guard에 연결해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b306d-247">Connectivity is required for Application Guard to validate the license.</span></span>

* <span data-ttu-id="b306d-248">문서의 정보 섹션에서 *마지막* 수정한 사용자 속성에 **WDAGUtilityAccount가** 사용자로 표시될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b306d-248">In the document's info section, the *Last Modified By* property may display **WDAGUtilityAccount** as the user.</span></span> <span data-ttu-id="b306d-249">WDAGUtilityAccount는 Application Guard에 구성된 익명 사용자입니다.</span><span class="sxs-lookup"><span data-stu-id="b306d-249">WDAGUtilityAccount is the anonymous user configured in Application Guard.</span></span> <span data-ttu-id="b306d-250">데스크톱 사용자의 ID는 Application Guard 컨테이너 내에서 공유되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="b306d-250">The desktop user's identity isn't shared inside the Application Guard container.</span></span>

## <a name="performance-optimizations-for-application-guard-for-office"></a><span data-ttu-id="b306d-251">응용 프로그램용 Application Guard에 대한 성능 Office</span><span class="sxs-lookup"><span data-stu-id="b306d-251">Performance optimizations for Application Guard for Office</span></span>

<span data-ttu-id="b306d-252">이 섹션에서는 Application Guard에서 사용되는 성능 최적화에 대한 개요를 Office.</span><span class="sxs-lookup"><span data-stu-id="b306d-252">This section provides an overview of the performance optimizations used in Application Guard for Office.</span></span> <span data-ttu-id="b306d-253">이 정보는 관리자가 Application Guard를 사용하도록 설정한 경우 전체 시스템 또는 Office 성능과 관련된 사용자의 보고서를 진단하는 데 도움이 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b306d-253">This information can help administrators diagnose reports from users related to the performance of Office or the overall system when Application Guard is enabled.</span></span>

<span data-ttu-id="b306d-254">Application Guard는 가상화된 컨테이너를 사용하여 시스템에서 트러운 문서를 격리합니다.</span><span class="sxs-lookup"><span data-stu-id="b306d-254">Application Guard uses a virtualized container to isolate untrusted documents away from the system.</span></span> <span data-ttu-id="b306d-255">컨테이너를 만들고 Application Guard 컨테이너를 설정하여 Office 문서가 열리면 성능 오버헤드가 발생합니다. 이로인하여 사용자가 해당 문서를 열 때 사용자 경험에 부정적인 영향을 줄 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b306d-255">The process of creating a container and setting up the Application Guard container to open Office documents has a performance overhead that might negatively affect user experience when users open an untrusted document.</span></span>

<span data-ttu-id="b306d-256">사용자에게 예상되는 파일 열기 환경을 제공하기 위해 Application Guard는 시스템에서 다음 경험적이 충족될 때 논리를 사용하여 컨테이너를 미리 만들 수 있습니다. 사용자가 지난 28일 동안 보호된 보기 또는 Application Guard에서 파일을 열었다는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="b306d-256">To provide users with the expected file-opening experience, Application Guard uses logic to pre-create a container when the following heuristic is met on a system: A user has opened a file in either Protected View or Application Guard in the past 28 days.</span></span>

<span data-ttu-id="b306d-257">이 언어가 충족되는 경우 Office 로그인한 후 사용자에 대한 Application Guard 컨테이너를 미리 Windows.</span><span class="sxs-lookup"><span data-stu-id="b306d-257">When this heuristic is met, Office will pre-create an Application Guard container for the user after they sign in to Windows.</span></span> <span data-ttu-id="b306d-258">이 사전 만들기 작업이 진행 중이면 시스템에서 성능이 느려질 수 있지만 작업이 완료되면 즉시 효과가 해결됩니다.</span><span class="sxs-lookup"><span data-stu-id="b306d-258">While this pre-create operation is in progress, the system may experience slow performance, but the effect will resolve as soon as the operation completes.</span></span>

> [!NOTE]
> <span data-ttu-id="b306d-259">사용자가 컨테이너를 미리 만드는 데 필요한 힌트는 사용자가 컨테이너를 Office 응용 프로그램에 의해 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="b306d-259">The hints needed for the heuristic to pre-create the container are generated by Office applications as a user uses them.</span></span> <span data-ttu-id="b306d-260">Application Guard가 Office 새 시스템에 설치하는 경우 사용자가 시스템에서 Office 문서를 처음으로 열 때까지 컨테이너를 미리 만들지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="b306d-260">If a user installs Office on a new system where Application Guard is enabled, Office will not pre-create the container until after the first time a user opens an untrusted document on the system.</span></span> <span data-ttu-id="b306d-261">사용자는 Application Guard에서 이 첫 번째 파일을 여는 데 시간이 더 오래 걸리는 것으로 관찰합니다.</span><span class="sxs-lookup"><span data-stu-id="b306d-261">The user will observe that this first file takes longer to open in Application Guard.</span></span>

## <a name="known-issues"></a><span data-ttu-id="b306d-262">알려진 문제</span><span class="sxs-lookup"><span data-stu-id="b306d-262">Known issues</span></span>

* <span data-ttu-id="b306d-263">웹 링크(또는 )를 선택하면 `http` `https` 브라우저가 열립니다.</span><span class="sxs-lookup"><span data-stu-id="b306d-263">Selecting web links (`http` or `https`) doesn't open the browser.</span></span>
* <span data-ttu-id="b306d-264">복사-붙여넣기 보호 정책의 기본 설정은 텍스트에만 클립보드 액세스를 사용하도록 설정하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="b306d-264">The default setting for copy-paste protection policy is to enable clipboard access to text only.</span></span>
* <span data-ttu-id="b306d-265">지원되지 않는 파일 형식 보호 정책의 기본 설정은 암호화되거나 IRM(정보 권한 관리)을 설정한 것으로, 지원되지 않는 지원되지 않는 파일 형식을 열지 못하게 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="b306d-265">The default setting for unsupported file types protection policy is to block opening untrusted unsupported file types that are encrypted or have Information Rights Management (IRM) set.</span></span> <span data-ttu-id="b306d-266">여기에는 암호화를 Microsoft Information Protection 민감도 레이블이 있는 파일이 포함됩니다(기밀 또는 기밀).</span><span class="sxs-lookup"><span data-stu-id="b306d-266">This includes files that have Microsoft Information Protection sensitivity labels using encryption (confidential or highly confidential).</span></span>
* <span data-ttu-id="b306d-267">CSV 및 HTML 파일은 현재 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="b306d-267">CSV and HTML files are not supported at this time.</span></span>
* <span data-ttu-id="b306d-268">현재 NTFS Office 볼륨에 대한 Application Guard가 작동하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="b306d-268">Application Guard for Office currently does not work with NTFS compressed volumes.</span></span> <span data-ttu-id="b306d-269">"오류"가 ERROR_VIRTUAL_DISK_LIMITATION 볼륨 압축을 다.</span><span class="sxs-lookup"><span data-stu-id="b306d-269">If you are seeing an error "ERROR_VIRTUAL_DISK_LIMITATION" please try uncompressing the volume.</span></span>
* <span data-ttu-id="b306d-270">.NET을 업데이트하면 Application Guard에서 파일이 열리지 못할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b306d-270">Updates to .NET might cause files to fail to open in Application Guard.</span></span> <span data-ttu-id="b306d-271">이 해결로 사용자는 이 오류가 발생하면 장치를 다시 시작할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b306d-271">As a workaround, users can restart their device when they come across this failure.</span></span> <span data-ttu-id="b306d-272">자세한 내용은 샌드박스 또는 샌드박스를 열 때 오류 Windows Defender Application Guard [Windows 합니다.](https://support.microsoft.com/help/4575917/receiving-an-error-message-when-attempting-to-open-windows-defender-ap)</span><span class="sxs-lookup"><span data-stu-id="b306d-272">Learn more about the issue at [Receiving an error message when attempting to open Windows Defender Application Guard or Windows Sandbox](https://support.microsoft.com/help/4575917/receiving-an-error-message-when-attempting-to-open-windows-defender-ap).</span></span>
* <span data-ttu-id="b306d-273">자세한 내용은 [질문과 대답 - Microsoft Defender Application Guard 참조하세요.](/windows/security/threat-protection/microsoft-defender-application-guard/faq-md-app-guard)</span><span class="sxs-lookup"><span data-stu-id="b306d-273">Please see [Frequently asked questions - Microsoft Defender Application Guard for additional information.](/windows/security/threat-protection/microsoft-defender-application-guard/faq-md-app-guard)</span></span> 
