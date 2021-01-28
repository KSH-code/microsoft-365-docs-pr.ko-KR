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
description: 하드웨어 기반의 최신 버전을 다운로드합니다. 악용 또는 악의적인 링크와 같은 현재 및 새로운 공격이 직원 생산성 및 엔터프라이즈 보안을 방해하지 않도록 방지합니다.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 9a9c9270f61661982108da518d1bf24d2a717b6a
ms.sourcegitcommit: 537e513a4a232a01e44ecbc76d86a8bcaf142482
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/27/2021
ms.locfileid: "50029729"
---
# <a name="application-guard-for-office-for-admins"></a><span data-ttu-id="ef663-105">관리자용 Office용 Application Guard</span><span class="sxs-lookup"><span data-stu-id="ef663-105">Application Guard for Office for admins</span></span>

<span data-ttu-id="ef663-106">**적용된 사항은 다음에 해당합니다.** Microsoft 365용 Word, Excel 및 PowerPoint, Windows 10 Enterprise</span><span class="sxs-lookup"><span data-stu-id="ef663-106">**Applies to:** Word, Excel, and PowerPoint for Microsoft 365, Windows 10 Enterprise</span></span>

<span data-ttu-id="ef663-107">Microsoft Defender Application Guard for Office(Application Guard for Office)를 사용하면 신뢰할 수 없는 파일이 신뢰할 수 있는 리소스에 액세스하지 못하게 하여 엔터프라이즈를 새로운 공격으로부터 안전하게 보호할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ef663-107">Microsoft Defender Application Guard for Office (Application Guard for Office) helps prevent untrusted files from accessing trusted resources, keeping your enterprise safe from new and emerging attacks.</span></span> <span data-ttu-id="ef663-108">이 문서에서는 관리자에게 Office용 Application Guard의 미리 보기에 대한 디바이스를 설정하는 데 대해 간행합니다.</span><span class="sxs-lookup"><span data-stu-id="ef663-108">This article walks admins through setting up devices for a preview of Application Guard for Office.</span></span> <span data-ttu-id="ef663-109">디바이스에서 Office용 Application Guard를 사용하도록 설정하기 위한 시스템 요구 사항 및 설치 단계에 대한 정보를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="ef663-109">It provides information about system requirements and installation steps to enable Application Guard for Office on a device.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="ef663-110">필수 구성 요소</span><span class="sxs-lookup"><span data-stu-id="ef663-110">Prerequisites</span></span>

### <a name="minimum-hardware-requirements"></a><span data-ttu-id="ef663-111">최소 하드웨어 요구 사항</span><span class="sxs-lookup"><span data-stu-id="ef663-111">Minimum hardware requirements</span></span>

* <span data-ttu-id="ef663-112">**CPU**: 64비트, 4코어(물리적 또는 가상), 가상화 확장(Intel VT-x OR AMD-V), Core i5 동등 이상 권장</span><span class="sxs-lookup"><span data-stu-id="ef663-112">**CPU**: 64-bit, 4 cores (physical or virtual), virtualization extensions   (Intel VT-x OR AMD-V), Core i5 equivalent or higher recommended</span></span>
* <span data-ttu-id="ef663-113">**실제 메모리:** 8GB RAM</span><span class="sxs-lookup"><span data-stu-id="ef663-113">**Physical memory**: 8-GB RAM</span></span>
* <span data-ttu-id="ef663-114">**하드 디스크**: 시스템 드라이브에 10GB의 사용 공간(SSD 권장)</span><span class="sxs-lookup"><span data-stu-id="ef663-114">**Hard disk**: 10 GB of free space on the system drive (SSD recommended)</span></span>

### <a name="minimum-software-requirements"></a><span data-ttu-id="ef663-115">최소 소프트웨어 요구 사항</span><span class="sxs-lookup"><span data-stu-id="ef663-115">Minimum software requirements</span></span>

* <span data-ttu-id="ef663-116">**Windows 10:** Windows 10 Enterprise 버전, 클라이언트 빌드 버전 2004(20H1) 빌드 19041 이상</span><span class="sxs-lookup"><span data-stu-id="ef663-116">**Windows 10**: Windows 10 Enterprise edition, Client Build version 2004 (20H1) build 19041 or later</span></span>
* <span data-ttu-id="ef663-117">**Office**: Office 현재 채널 빌드 버전 2011 16.0.13530.10000 이상</span><span class="sxs-lookup"><span data-stu-id="ef663-117">**Office**: Office Current Channel Build version 2011 16.0.13530.10000 or later</span></span>
* <span data-ttu-id="ef663-118">**업데이트 패키지:** Windows 10 월별 누적 보안 업데이트 [KB4571756](https://support.microsoft.com/help/4571756/windows-10-update-KB4571756)</span><span class="sxs-lookup"><span data-stu-id="ef663-118">**Update package**: Windows 10 cumulative monthly security update [KB4571756](https://support.microsoft.com/help/4571756/windows-10-update-KB4571756)</span></span>

<span data-ttu-id="ef663-119">자세한 시스템 요구 사항은 [Microsoft Defender Application Guard의 시스템 요구 사항을 참조하세요.](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-application-guard/reqs-md-app-guard)</span><span class="sxs-lookup"><span data-stu-id="ef663-119">For detailed system requirements, refer to [System requirements for Microsoft Defender Application Guard](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-application-guard/reqs-md-app-guard).</span></span> <span data-ttu-id="ef663-120">Office 업데이트 채널에 대한 자세한 내용은 [Microsoft 365](https://docs.microsoft.com/deployoffice/overview-update-channels)업데이트 채널 개요를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="ef663-120">To learn more about Office update channels, see [Overview of update channels for Microsoft 365](https://docs.microsoft.com/deployoffice/overview-update-channels).</span></span>

### <a name="licensing-requirements"></a><span data-ttu-id="ef663-121">라이선스 요구 사항</span><span class="sxs-lookup"><span data-stu-id="ef663-121">Licensing requirements</span></span>

* <span data-ttu-id="ef663-122">Microsoft 365 E5 또는 Microsoft 365 E5 보안</span><span class="sxs-lookup"><span data-stu-id="ef663-122">Microsoft 365 E5 or Microsoft 365 E5 Security</span></span>

## <a name="deploy-application-guard-for-office"></a><span data-ttu-id="ef663-123">Office용 Application Guard 배포</span><span class="sxs-lookup"><span data-stu-id="ef663-123">Deploy Application Guard for Office</span></span>

### <a name="enable-application-guard-for-office"></a><span data-ttu-id="ef663-124">Office용 Application Guard 사용</span><span class="sxs-lookup"><span data-stu-id="ef663-124">Enable Application Guard for Office</span></span>

1. <span data-ttu-id="ef663-125">Windows 10 월별 누적 보안 업데이트 **KB4571756을 다운로드하여 설치합니다.**</span><span class="sxs-lookup"><span data-stu-id="ef663-125">Download and install **Windows 10 cumulative monthly security updates KB4571756**.</span></span>

2. <span data-ttu-id="ef663-126">Windows **기능에서 Microsoft Defender Application Guard를** 선택하고 확인을 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="ef663-126">Select **Microsoft Defender Application Guard** under Windows Features and  select **OK**.</span></span> <span data-ttu-id="ef663-127">Application Guard 기능을 사용하도록 설정하면 시스템을 다시 시작하라는 메시지가 표시될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ef663-127">Enabling the Application Guard feature will prompt a system reboot.</span></span> <span data-ttu-id="ef663-128">지금 다시 시작하거나 3단계 후에 다시 시작하게 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ef663-128">You can choose to reboot now or after step 3.</span></span>

   ![AG를 보여 주며 Windows 기능 대화 상자](../../media/ag03-deploy.png)

   <span data-ttu-id="ef663-130">관리자 권한으로 다음 PowerShell 명령을 실행하여 이 기능을 사용할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ef663-130">The feature can also be enabled by running the following PowerShell command as administrator:</span></span>

   ```powershell
   Enable-WindowsOptionalFeature -online -FeatureName Windows-Defender-ApplicationGuard
   ```

3. <span data-ttu-id="ef663-131">컴퓨터 구성 관리 템플릿 Windows 구성 요소 **Microsoft Defender Application Guard의** 그룹 정책인 관리 모드에서 **Microsoft \\ \\ \\ Defender Application Guard를 검색합니다.**</span><span class="sxs-lookup"><span data-stu-id="ef663-131">Search for **Microsoft Defender Application Guard in Managed Mode**, a group policy in **Computer Configuration\\Administrative Templates\\Windows Components\\Microsoft Defender Application Guard**.</span></span> <span data-ttu-id="ef663-132">옵션에서 값을 **2** 또는 **3으로** 설정한 다음 확인 또는 적용을 선택하여 이 **정책을** **켜야 합니다.**</span><span class="sxs-lookup"><span data-stu-id="ef663-132">Turn on this policy by setting the value under Options as **2** or **3**, and then selecting **OK** or **Apply**.</span></span>

   ![관리 모드에서 AG 켜기](../../media/ag04-deploy.png)

   <span data-ttu-id="ef663-134">대신 해당 CSP 정책을 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ef663-134">Instead, you can set the corresponding CSP policy:</span></span>

   > <span data-ttu-id="ef663-135">OMA-URI: **./Device/Vendor/MSFT/WindowsDefenderApplicationGuard/Settings/AllowWindowsDefenderApplicationGuard**</span><span class="sxs-lookup"><span data-stu-id="ef663-135">OMA-URI: **./Device/Vendor/MSFT/WindowsDefenderApplicationGuard/Settings/AllowWindowsDefenderApplicationGuard**</span></span> <br> <span data-ttu-id="ef663-136">데이터 형식: **정수**</span><span class="sxs-lookup"><span data-stu-id="ef663-136">Data type: **Integer**</span></span> <br> <span data-ttu-id="ef663-137">값: **2**</span><span class="sxs-lookup"><span data-stu-id="ef663-137">Value: **2**</span></span>

4. <span data-ttu-id="ef663-138">시스템을 다시 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="ef663-138">Restart the system.</span></span>

### <a name="set-diagnostics--feedback-to-send-full-data"></a><span data-ttu-id="ef663-139">전체 데이터를 & 진단 및 피드백 설정</span><span class="sxs-lookup"><span data-stu-id="ef663-139">Set Diagnostics & feedback to send full data</span></span>

<span data-ttu-id="ef663-140">이 단계를 통해 문제를 식별하고 해결하는 데 필요한 데이터가 Microsoft에 도달하게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ef663-140">This step ensures that the data necessary to identify and fix problems is reaching Microsoft.</span></span> <span data-ttu-id="ef663-141">Windows 장치에서 진단을 사용하도록 설정하려면 다음 단계를 따르세요.</span><span class="sxs-lookup"><span data-stu-id="ef663-141">Follow these steps to enable diagnostics on your Windows device:</span></span>

1. <span data-ttu-id="ef663-142">시작 **메뉴에서** 설정을 니다.</span><span class="sxs-lookup"><span data-stu-id="ef663-142">Open **Settings** from the Start menu.</span></span>

   ![시작 메뉴](../../media/ag05-diagnostic.png)

2. <span data-ttu-id="ef663-144">**Windows 설정에서** 개인 정보를 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="ef663-144">On **Windows Settings**, select **Privacy**.</span></span>

   ![Windows 설정 메뉴](../../media/ag06-diagnostic.png)

3. <span data-ttu-id="ef663-146">개인 정보 보호에서 **진단** 및 & 선택적 진단 **데이터를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="ef663-146">Under Privacy, select **Diagnostics & feedback** and select **Optional diagnostic data**.</span></span>

   ![진단 및 피드백 메뉴](../../media/ag07a-diagnostic.png)

<span data-ttu-id="ef663-148">Windows 진단 설정 구성에 대한 자세한 내용은 조직에서 Windows 진단 데이터 [구성을 참조하세요.](https://docs.microsoft.com/windows/privacy/configure-windows-diagnostic-data-in-your-organization#enterprise-management)</span><span class="sxs-lookup"><span data-stu-id="ef663-148">For more on configuring Windows diagnostic settings, refer to [Configuring Windows diagnostic data in your organization](https://docs.microsoft.com/windows/privacy/configure-windows-diagnostic-data-in-your-organization#enterprise-management).</span></span>

### <a name="confirm-that-application-guard-for-office-is-enabled-and-working"></a><span data-ttu-id="ef663-149">Office용 Application Guard가 사용하도록 설정되어 있으며 작동하고 있는지 확인</span><span class="sxs-lookup"><span data-stu-id="ef663-149">Confirm that Application Guard for Office is enabled and working</span></span>

<span data-ttu-id="ef663-150">Office용 Application Guard를 사용하도록 설정되어 있는지 확인하기 전에 정책이 배포된 장치에서 Word, Excel 또는 PowerPoint를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="ef663-150">Before confirming that Application Guard for Office is enabled, launch Word, Excel, or PowerPoint on a device where the policies have been deployed.</span></span> <span data-ttu-id="ef663-151">Office가 정품 인증되어 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="ef663-151">Make sure Office is activated.</span></span> <span data-ttu-id="ef663-152">먼저 작업 ID를 사용하여 Office 제품을 정품 인증해야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ef663-152">You may need to use your work identity to activate the Office product first.</span></span>

<span data-ttu-id="ef663-153">Office용 Application Guard를 사용하도록 설정되어 있는지 확인을 위해 Word, Excel 또는 PowerPoint를 실행한 다음, 트러설되지 않은 문서를 여는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="ef663-153">To confirm that Application Guard for Office is enabled, launch Word, Excel, or PowerPoint, and then open an untrusted document.</span></span> <span data-ttu-id="ef663-154">예를 들어 인터넷에서 다운로드한 문서나 조직 외부의 사용자가 전자 메일 첨부 파일을 열 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ef663-154">For example, you can open a document that was downloaded from the internet or an email attachment from someone outside your organization.</span></span>

<span data-ttu-id="ef663-155">처음에 불안정한 파일을 열면 다음 예와 같이 Office 시작 화면이 표시될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ef663-155">When you first open an untrusted file, you may see an Office splash screen like the following example.</span></span> <span data-ttu-id="ef663-156">Office용 Application Guard가 활성화되고 파일이 열리면서 일부 시간 동안 표시될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ef663-156">It might be displayed for some time while Application Guard for Office is being activated and the file is being opened.</span></span> <span data-ttu-id="ef663-157">이후에는 더 빠르게 파일을 열 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ef663-157">Subsequent openings of untrusted files should be faster.</span></span>

![Office 앱 시작 화면](../../media/ag08-confirm.png)

<span data-ttu-id="ef663-159">파일을 열면 Office용 Application Guard에서 파일이 열렸다는 몇 가지 시각적 표시기가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="ef663-159">Upon being opened, the file should display a few visual indicators that the file was opened inside Application Guard for Office:</span></span>

* <span data-ttu-id="ef663-160">리본 메뉴의 콜아웃</span><span class="sxs-lookup"><span data-stu-id="ef663-160">A callout in the ribbon</span></span>

  ![작은 App Guard 메모를 표시하는 Doc 파일](../../media/ag09-confirm.png)

* <span data-ttu-id="ef663-162">작업 표시줄에 방패가 있는 응용 프로그램 아이콘</span><span class="sxs-lookup"><span data-stu-id="ef663-162">The application icon with a shield in the taskbar</span></span>

  ![작업 표시줄의 아이콘](../../media/ag12-limitations.png)

## <a name="configure-application-guard-for-office"></a><span data-ttu-id="ef663-164">Office용 Application Guard 구성</span><span class="sxs-lookup"><span data-stu-id="ef663-164">Configure Application Guard for Office</span></span>

<span data-ttu-id="ef663-165">Office는 Office용 Application Guard의 기능을 구성할 수 있도록 다음과 같은 정책을 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="ef663-165">Office supports the following policies to enable you to configure the capabilities of Application Guard for Office.</span></span> <span data-ttu-id="ef663-166">이러한 정책은 그룹 정책 또는 Office 클라우드 정책 서비스를 통해 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ef663-166">These policies can be configured through Group policies or through the Office cloud policy service.</span></span>

> [!NOTE]
> <span data-ttu-id="ef663-167">이러한 정책을 구성하면 Office용 Application Guard에서 연 파일에 대해 일부 기능을 사용하지 않도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ef663-167">Configuring these policies can disable some functionalities for files opened in Application Guard for Office.</span></span>

|<span data-ttu-id="ef663-168">정책</span><span class="sxs-lookup"><span data-stu-id="ef663-168">Policy</span></span>|<span data-ttu-id="ef663-169">설명</span><span class="sxs-lookup"><span data-stu-id="ef663-169">Description</span></span>|
|---|---|
|<span data-ttu-id="ef663-170">Office용 Application Guard를 사용하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="ef663-170">Don't use Application Guard for Office</span></span>|<span data-ttu-id="ef663-171">이 정책을 사용하도록 설정하면 Word, Excel 및 PowerPoint에서 Office용 Application Guard 대신 보호된 보기의 고리 컨테이너를 사용하도록 강제로 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="ef663-171">Enabling this policy will force Word, Excel, and PowerPoint to use the Protected View isolation container instead of Application Guard for Office.</span></span> <span data-ttu-id="ef663-172">이 정책은 Microsoft Edge를 사용하도록 설정한 채로 두는 데 문제가 있는 경우 Office용 Application Guard를 일시적으로 사용하지 않도록 설정하는 데 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ef663-172">This policy can be used to temporarily disable Application Guard for Office when there are issues in leaving it enabled for Microsoft Edge.</span></span>|
|<span data-ttu-id="ef663-173">Office 컨테이너 사전 생성을 위한 Application Guard 구성</span><span class="sxs-lookup"><span data-stu-id="ef663-173">Configure Application Guard for Office container pre-creation</span></span>|<span data-ttu-id="ef663-174">이 정책은 런타임 성능 향상을 위해 Office 컨테이너용 Application Guard가 트러설되지 않은 파일을 확인하는 데 미리 만들어 있는지 여부를 판단합니다.</span><span class="sxs-lookup"><span data-stu-id="ef663-174">This policy determines if the Application Guard for Office container, for isolating untrusted files, is pre-created for improved run-time performance.</span></span> <span data-ttu-id="ef663-175">이 설정을 사용하면 컨테이너를 계속 미리 만들거나 Office에서 기본 제공 이후 컨테이너를 미리 만들 수 있도록 할 일 수를 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ef663-175">If you enable this setting, you can specify the number of days to continue pre-creating a container or let the Office built-in heuristic pre-create the container.</span></span>
|<span data-ttu-id="ef663-176">Office용 Application Guard에서 연 Office 문서의 복사/붙여넣기 허용 안</span><span class="sxs-lookup"><span data-stu-id="ef663-176">Don't allow copy/paste for Office documents opened in Application Guard for Office</span></span>|<span data-ttu-id="ef663-177">이 정책을 사용하도록 설정하면 사용자가 Office용 Application Guard에서 연 문서의 콘텐츠를 복사하여 외부에서 연 문서에 붙여넣을 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="ef663-177">Enabling this policy will prevent a user from copying and pasting content from a document opened in Application Guard for Office to a document opened outside of it.</span></span>|
|<span data-ttu-id="ef663-178">Office용 Application Guard에서 하드웨어 가속 사용 안</span><span class="sxs-lookup"><span data-stu-id="ef663-178">Disable hardware acceleration in Application Guard for Office</span></span>|<span data-ttu-id="ef663-179">이 정책은 Office용 Application Guard가 하드웨어 가속을 사용하여 그래픽을 렌더링하는지 여부를 제어합니다.</span><span class="sxs-lookup"><span data-stu-id="ef663-179">This policy controls whether Application Guard for Office uses hardware acceleration to render graphics.</span></span> <span data-ttu-id="ef663-180">이 설정을 사용하면 Office용 Application Guard는 소프트웨어 기반(CPU) 렌더링을 사용하며 타사 그래픽 드라이버를 로드하거나 연결된 그래픽 하드웨어와 상호 작용하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="ef663-180">If you enable this setting, Application Guard for Office uses software-based (CPU) rendering and won't load any third-party graphics drivers or interact with any connected graphics hardware.</span></span>
|<span data-ttu-id="ef663-181">Office용 Application Guard에서 지원되지 않는 파일 형식 보호 해제</span><span class="sxs-lookup"><span data-stu-id="ef663-181">Disable unsupported file types protection in Application Guard for Office</span></span>|<span data-ttu-id="ef663-182">이 정책은 Office용 Application Guard가 지원되지 않는 파일 형식이 열리지 못하도록 차단할지 아니면 보호된 보기로 리디렉션할지 여부를 제어합니다.</span><span class="sxs-lookup"><span data-stu-id="ef663-182">This policy controls whether Application Guard for Office will block unsupported file types from being opened or if it will enable the redirection to Protected View.</span></span>
|<span data-ttu-id="ef663-183">Office용 Application Guard에서 연 문서에 대한 카메라 및 마이크 액세스 끄기</span><span class="sxs-lookup"><span data-stu-id="ef663-183">Turn off camera and microphone access for documents opened in Application Guard for Office</span></span>|<span data-ttu-id="ef663-184">이 정책을 사용하도록 설정하면 Office용 Application Guard 내부의 카메라 및 마이크에 대한 Office 액세스가 제거됩니다.</span><span class="sxs-lookup"><span data-stu-id="ef663-184">Enabling this policy will remove Office access to the camera and microphone inside Application Guard for Office.</span></span>|
|<span data-ttu-id="ef663-185">Office용 Application Guard에서 연 문서에서 인쇄 제한</span><span class="sxs-lookup"><span data-stu-id="ef663-185">Restrict printing from documents opened in Application Guard for Office</span></span>|<span data-ttu-id="ef663-186">이 정책을 사용하도록 설정하면 사용자가 Office용 Application Guard에서 연 파일에서 인쇄할 수 있는 프린터가 제한됩니다.</span><span class="sxs-lookup"><span data-stu-id="ef663-186">Enabling this policy will limit the printers that a user can print to from a file opened in Application Guard for Office.</span></span> <span data-ttu-id="ef663-187">예를 들어 이 정책을 사용하여 사용자가 PDF로만 인쇄하도록 제한할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ef663-187">For example, you can use this policy to restrict users to only print to PDF.</span></span>|
|<span data-ttu-id="ef663-188">사용자가 파일에서 Office 보호를 위한 Application Guard를 제거하지 못하게 방지</span><span class="sxs-lookup"><span data-stu-id="ef663-188">Prevent users from removing Application Guard for Office protection on files</span></span>|<span data-ttu-id="ef663-189">이 정책을 사용하면 Office 응용 프로그램 환경 내에서 Office 보호용 Application Guard를 사용하지 않도록 설정하거나 Office용 Application Guard 외부에서 파일을 여는 옵션이 제거됩니다.</span><span class="sxs-lookup"><span data-stu-id="ef663-189">Enabling this policy will remove the option (within the Office application experience) to disable Application Guard for Office protection or to open a file outside Application Guard for Office.</span></span> <p> <span data-ttu-id="ef663-190">**참고:** 사용자는 파일에서 웹 속성 표시를 수동으로 제거하거나 문서를 신뢰할 수 있는 위치로 이동하여 이 정책을 무시할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ef663-190">**Note:** Users can still bypass this policy by manually removing the mark-of-the-web property from the file or by moving a document to a Trusted location.</span></span>|
|

> [!NOTE]
> <span data-ttu-id="ef663-191">다음 정책을 적용하려면 사용자가 로그인한 후 Windows에 다시 로그인해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ef663-191">The following policies will require the user to sign out and sign in again to Windows to take effect:</span></span>
>
> * <span data-ttu-id="ef663-192">Office용 Application Guard에서 연 문서에 대해 복사/붙여넣기 사용 안</span><span class="sxs-lookup"><span data-stu-id="ef663-192">Disable copy/paste for documents opened in Application Guard for Office</span></span>
> * <span data-ttu-id="ef663-193">Office용 Application Guard에서 연 문서에 대한 인쇄 제한</span><span class="sxs-lookup"><span data-stu-id="ef663-193">Restrict printing for documents opened in Application Guard for Office</span></span>
> * <span data-ttu-id="ef663-194">Office용 Application Guard에서 연 문서에 대한 카메라 및 마이크 액세스 끄기</span><span class="sxs-lookup"><span data-stu-id="ef663-194">Turn off camera and mic access to documents opened in Application Guard for Office</span></span>

## <a name="submit-feedback"></a><span data-ttu-id="ef663-195">피드백 제출</span><span class="sxs-lookup"><span data-stu-id="ef663-195">Submit feedback</span></span>

### <a name="submit-feedback-via-feedback-hub"></a><span data-ttu-id="ef663-196">피드백 허브를 통해 피드백 제출</span><span class="sxs-lookup"><span data-stu-id="ef663-196">Submit feedback via Feedback Hub</span></span>

<span data-ttu-id="ef663-197">Office용 Application Guard를 시작하면 피드백 허브를 통해 피드백을 제출하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="ef663-197">If you encounter any issues when launching Application Guard for Office, you're encouraged to submit your feedback via Feedback Hub:</span></span>

1. <span data-ttu-id="ef663-198">피드백 허브 **앱을 열고** 로그인합니다.</span><span class="sxs-lookup"><span data-stu-id="ef663-198">Open the **Feedback Hub app** and sign in.</span></span>

2. <span data-ttu-id="ef663-199">Application Guard를 시작하는 동안 오류 대화 상자가 표시된 경우 오류 대화 상자에서 **Microsoft에** 보고를 선택하여 새 피드백 제출을 시작하십시오.</span><span class="sxs-lookup"><span data-stu-id="ef663-199">If you get an error dialog while launching Application Guard, select **Report to Microsoft** in the error dialog to start a new feedback submission.</span></span> <span data-ttu-id="ef663-200">그렇지 않은 경우 Application Guard에 대한 올바른 범주를 선택한 다음 오른쪽 상단 근처에 새 피드백 <https://aka.ms/mdagoffice-fb> **+ &nbsp;** 추가를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="ef663-200">Otherwise, navigate to <https://aka.ms/mdagoffice-fb> to select the correct category for Application Guard, then select **+&nbsp;Add new feedback** near the top right.</span></span>

3. <span data-ttu-id="ef663-201">아직 입력하지 않은  경우 피드백 요약 상자에 요약을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="ef663-201">Enter a summary in the **Summarize your feedback** box if it isn't already filled in for you.</span></span>

4. <span data-ttu-id="ef663-202">경험한 문제와 자세한 설명 상자에 수행한 단계에  대한 자세한 설명을 입력하고 다음을 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="ef663-202">Enter a detailed description of the issue that you experienced and what steps you took in the **Explain in more detail** box, then select **Next**.</span></span>

5. <span data-ttu-id="ef663-203">문제 옆의 거품을 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="ef663-203">Select the bubble next to **Problem**.</span></span> <span data-ttu-id="ef663-204">선택한 범주가 보안 및 개인 정보 **\> 보호 Microsoft Defender Application Guard (Office)이고** 다음을 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="ef663-204">Make sure the category selected is **Security and Privacy \> Microsoft Defender Application Guard – Office**, then select **Next**.</span></span>

6. <span data-ttu-id="ef663-205">새 **피드백을 선택하고** 다음을 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="ef663-205">Select **New feedback**, then **Next**.</span></span>

7. <span data-ttu-id="ef663-206">이 문제의 추적을 수집합니다.</span><span class="sxs-lookup"><span data-stu-id="ef663-206">Collect traces about the issue:</span></span>

   1. <span data-ttu-id="ef663-207">내 문제 **다시 시작 타일을 확장합니다.**</span><span class="sxs-lookup"><span data-stu-id="ef663-207">Expand the **Recreate my problem** tile.</span></span>

   2. <span data-ttu-id="ef663-208">Application Guard가 실행되는 동안 문제가 발생하는 경우 Application Guard 인스턴스를 런타이저합니다.</span><span class="sxs-lookup"><span data-stu-id="ef663-208">If the issue you're experiencing occurs while Application Guard is running, open an Application Guard instance.</span></span> <span data-ttu-id="ef663-209">인스턴스를 열면 Application Guard 컨테이너 내에서 추가 추적을 수집할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ef663-209">Opening an instance allows additional traces to be collected from within the Application Guard container.</span></span>

   3. <span data-ttu-id="ef663-210">**녹음/녹화 시작을** 선택하고 타일이 회전을 중지할 때까지 기다렸다가 기록 *중지를 선택합니다.*</span><span class="sxs-lookup"><span data-stu-id="ef663-210">Select **Start recording**, and wait for the tile to stop spinning and say *Stop recording*.</span></span>

   4. <span data-ttu-id="ef663-211">Application Guard에서 문제를 완전히 재현합니다.</span><span class="sxs-lookup"><span data-stu-id="ef663-211">Fully reproduce the issue with Application Guard.</span></span> <span data-ttu-id="ef663-212">다시 생성에는 Application Guard 인스턴스를 시작하려고 시도하고 실패할 때까지 기다리거나 실행 중인 Application Guard 인스턴스에서 문제를 재현하는 것이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="ef663-212">Reproduction might include attempting to launch an Application Guard instance and waiting until it fails, or reproducing an issue in a running Application Guard instance.</span></span>

   5. <span data-ttu-id="ef663-213">녹음 중지 **타일을** 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="ef663-213">Select the **Stop recording** tile.</span></span>

   6. <span data-ttu-id="ef663-214">컨테이너 진단도 수집할 수 있도록, 제출 후 몇 분 동안에도 실행 중인 Application Guard 인스턴스를 열어 두십시오.</span><span class="sxs-lookup"><span data-stu-id="ef663-214">Keep any running Application Guard instance(s) open, even for a few minutes after submission, so that container diagnostics can also be collected.</span></span>

8. <span data-ttu-id="ef663-215">문제와 관련된 스크린샷 또는 파일을 첨부합니다.</span><span class="sxs-lookup"><span data-stu-id="ef663-215">Attach any relevant screenshots or files related to the problem.</span></span>

9. <span data-ttu-id="ef663-216">**전송** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="ef663-216">Select **Submit**.</span></span>

### <a name="submit-feedback-via-office-customer-voice"></a><span data-ttu-id="ef663-217">Office Customer Voice를 통해 피드백 제출</span><span class="sxs-lookup"><span data-stu-id="ef663-217">Submit feedback via Office Customer Voice</span></span>

<span data-ttu-id="ef663-218">Office 문서를 Application Guard에서 열 때 문제가 발생하는 경우 Office 내에서 피드백을 제출할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ef663-218">You may also submit feedback from within Office if the issue happens when Office documents are opened in Application Guard.</span></span> <span data-ttu-id="ef663-219">피드백을 [제출할 수 있는 Office Insider Handbook을](https://insider.office.com/handbook) 참조합니다.</span><span class="sxs-lookup"><span data-stu-id="ef663-219">Refer to the [Office Insider Handbook](https://insider.office.com/handbook) for submitting feedback.</span></span>

## <a name="integration-with-microsoft-defender-for-endpoint-and-microsoft-defender-for-office-365"></a><span data-ttu-id="ef663-220">끝점용 Microsoft Defender 및 Office 365용 Microsoft Defender와의 통합</span><span class="sxs-lookup"><span data-stu-id="ef663-220">Integration with Microsoft Defender for Endpoint and Microsoft Defender for Office 365</span></span>

<span data-ttu-id="ef663-221">Office용 Application Guard는 격리된 환경에서 발생하는 악성 활동에 대한 모니터링 및 경고를 제공하기 위해 끝점용 Microsoft Defender와 통합되었습니다.</span><span class="sxs-lookup"><span data-stu-id="ef663-221">Application Guard for Office is integrated with Microsoft Defender for Endpoint to provide monitoring and alerting on malicious activity that happens in the isolated environment.</span></span>

<span data-ttu-id="ef663-222">끝점용 Microsoft Defender는 엔터프라이즈 네트워크가 고급 위협을 방지, 감지, 조사 및 대응하도록 설계된 보안 플랫폼입니다.</span><span class="sxs-lookup"><span data-stu-id="ef663-222">Microsoft Defender for Endpoint is a security platform designed to help enterprise networks prevent, detect, investigate, and respond to advanced threats.</span></span> <span data-ttu-id="ef663-223">이 플랫폼에 대한 자세한 내용은 [끝점용 Microsoft Defender를 참조합니다.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp)</span><span class="sxs-lookup"><span data-stu-id="ef663-223">For more details about this platform, see [Microsoft Defender for Endpoint](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp).</span></span> <span data-ttu-id="ef663-224">이 플랫폼에 장치 온보딩에 대한 자세한 내용은 끝점용 Microsoft Defender 서비스에 장치 온보딩을 [참조합니다.](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/onboard-configure)</span><span class="sxs-lookup"><span data-stu-id="ef663-224">To learn more about onboarding devices to this platform, see [Onboard devices to the Microsoft Defender for Endpoint service](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/onboard-configure).</span></span>

<span data-ttu-id="ef663-225">끝점용 Defender와 함께 작동하도록 Office 365용 Microsoft Defender를 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ef663-225">You can also configure Microsoft Defender for Office 365 to work with Defender for Endpoint.</span></span> <span data-ttu-id="ef663-226">자세한 내용은 [끝점용 Microsoft Defender와 Office 365용 Defender 통합을 참조하세요.](integrate-office-365-ti-with-wdatp.md)</span><span class="sxs-lookup"><span data-stu-id="ef663-226">For more info, refer to [Integrate Defender for Office 365 with Microsoft Defender for Endpoint](integrate-office-365-ti-with-wdatp.md).</span></span>

## <a name="limitations-and-considerations"></a><span data-ttu-id="ef663-227">제한 사항 및 고려 사항</span><span class="sxs-lookup"><span data-stu-id="ef663-227">Limitations and considerations</span></span>

* <span data-ttu-id="ef663-228">Office용 Application Guard는 신뢰할 수 있는 회사 리소스, 인트라넷, 사용자의 ID 및 컴퓨터의 임의 파일에 액세스할 수 없는 신뢰할 수 없는 문서를 격리하는 제한된 모드입니다.</span><span class="sxs-lookup"><span data-stu-id="ef663-228">Application Guard for Office is a restricted mode that isolates untrusted documents so that they can't access trusted corporate resources, an intranet, the user's identity, and arbitrary files on the computer.</span></span> <span data-ttu-id="ef663-229">따라서 사용자가 이러한 액세스에 종속된 기능(예: 디스크에 로컬 파일에서 그림 삽입)에 액세스하면 액세스가 실패하고 다음 예제와 같은 프롬프트가 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="ef663-229">As a result, if a user tries to access a feature that has a dependency on such access—for example, inserting a picture from a local file on disk—the access will fail and produce a prompt like the following example.</span></span> <span data-ttu-id="ef663-230">신뢰할 수 없는 문서가 신뢰할 수 있는 리소스에 액세스할 수 있도록 설정하려면 사용자가 문서에서 Application Guard 보호를 제거해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ef663-230">To enable an untrusted document to access trusted resources, users must remove Application Guard protection from the document.</span></span>

  ![안전한 유지를 위해 이 기능을 사용할 수 없는 경우를 설명하는 대화 상자](../../media/ag10-limitations.png)

  > [!NOTE]
  > <span data-ttu-id="ef663-232">사용자가 파일과 해당 원본을 신뢰하거나 출처를 신뢰할 수 있는 경우 보호 기능을 제거해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ef663-232">Advise users to only remove protection if they trust the file and its source or where it came from.</span></span>

* <span data-ttu-id="ef663-233">Office용 Application Guard에서는 매크로 및 ActiveX 컨트롤과 같은 문서의 활성 콘텐츠가 사용하지 않도록 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="ef663-233">Active content in documents like macros and ActiveX controls are disabled in Application Guard for Office.</span></span> <span data-ttu-id="ef663-234">사용자가 활성 콘텐츠를 사용하도록 설정하려면 Application Guard 보호를 제거해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ef663-234">Users need to remove Application Guard protection to enable active content.</span></span>

* <span data-ttu-id="ef663-235">다른 조직의 OneDrive, 비즈니스용 OneDrive 또는 SharePoint Online에서 공유되는 네트워크 공유 또는 파일에서 트러버설이 없는 파일은 Application Guard에서 읽기 전용으로 열립니다.</span><span class="sxs-lookup"><span data-stu-id="ef663-235">Untrusted files from network shares or files shared from OneDrive, OneDrive for Business, or SharePoint Online from a different organization open as read-only in Application Guard.</span></span> <span data-ttu-id="ef663-236">사용자는 이러한 파일의 로컬 복사본을 저장하여 컨테이너에서 작업을 계속하거나 보호 기능을 제거하여 원본 파일을 직접 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ef663-236">Users can save a local copy of such files to continue working in the container or remove protection to directly work with the original file.</span></span>

* <span data-ttu-id="ef663-237">IRM(정보 권한 관리)으로 보호되는 파일은 기본적으로 차단됩니다.</span><span class="sxs-lookup"><span data-stu-id="ef663-237">Files that are protected by Information Rights Management (IRM) are blocked by default.</span></span> <span data-ttu-id="ef663-238">사용자가 이러한 파일을 보호된 보기에서 열기 위해 관리자는 조직의 지원되지 않는 파일 형식에 대한 정책 설정을 구성해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ef663-238">If users want to open such files in Protected View, an administrator must configure policy settings for unsupported file types for the organization.</span></span>

* <span data-ttu-id="ef663-239">Office용 Application Guard의 Office 응용 프로그램에 대한 사용자 지정은 사용자가 로그인한 후 또는 장치가 다시 시작된 후에도 지속되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="ef663-239">Any customizations to Office applications in Application Guard for Office won't persist after a user signs out and signs in again or after the device restarts.</span></span>

* <span data-ttu-id="ef663-240">UIA 프레임워크를 사용하는 접근성 도구만 Office용 Application Guard에서 열 수 있는 파일에 대한 접근성 환경을 제공할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ef663-240">Only Accessibility tools that use the UIA framework can provide an accessible experience for files opened in Application Guard for Office.</span></span>

* <span data-ttu-id="ef663-241">설치 후 Application Guard를 처음 시작하려면 네트워크 연결이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="ef663-241">Network connectivity is required for the first launch of Application Guard after installation.</span></span> <span data-ttu-id="ef663-242">Application Guard에서 라이선스의 유효성을 검사하려면 연결이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="ef663-242">Connectivity is required for Application Guard to validate the license.</span></span>

* <span data-ttu-id="ef663-243">문서의 정보 섹션에서 *마지막으로* 수정한 By 속성은 **WDAGUtilityAccount를** 사용자로 표시할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ef663-243">In the document's info section, the *Last Modified By* property may display **WDAGUtilityAccount** as the user.</span></span> <span data-ttu-id="ef663-244">WDAGUtilityAccount는 Application Guard에 구성된 익명 사용자입니다.</span><span class="sxs-lookup"><span data-stu-id="ef663-244">WDAGUtilityAccount is the anonymous user configured in Application Guard.</span></span> <span data-ttu-id="ef663-245">데스크톱 사용자의 ID는 Application Guard 컨테이너 내에서 공유되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="ef663-245">The desktop user's identity isn't shared inside the Application Guard container.</span></span>

## <a name="performance-optimizations-for-application-guard-for-office"></a><span data-ttu-id="ef663-246">Office용 Application Guard의 성능 최적화</span><span class="sxs-lookup"><span data-stu-id="ef663-246">Performance optimizations for Application Guard for Office</span></span>

<span data-ttu-id="ef663-247">이 섹션에서는 Office용 Application Guard에서 사용되는 성능 최적화에 대해 간략하게 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="ef663-247">This section provides an overview of the performance optimizations used in Application Guard for Office.</span></span> <span data-ttu-id="ef663-248">이 정보는 Application Guard를 사용하도록 설정한 경우 관리자가 Office 또는 전체 시스템 성능과 관련된 사용자의 보고서를 진단하는 데 도움이 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ef663-248">This information can help administrators diagnose reports from users related to the performance of Office or the overall system when Application Guard is enabled.</span></span>

<span data-ttu-id="ef663-249">Application Guard는 가상화된 컨테이너를 사용하여 시스템에서 트러스되지 않은 문서를 격리합니다.</span><span class="sxs-lookup"><span data-stu-id="ef663-249">Application Guard uses a virtualized container to isolate untrusted documents away from the system.</span></span> <span data-ttu-id="ef663-250">컨테이너를 만들고 Application Guard 컨테이너를 설정하여 Office 문서를 열 때 성능 오버헤드가 발생합니다. 이로인하여 사용자가 트러운 문서를 열 때 사용자 환경이 부정적인 영향을 줄 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ef663-250">The process of creating a container and setting up the Application Guard container to open Office documents has a performance overhead that might negatively affect user experience when users open an untrusted document.</span></span>

<span data-ttu-id="ef663-251">사용자에게 예상되는 파일 열기 환경을 제공하기 위해 Application Guard는 논리를 사용하여 시스템에서 다음 경험적이 충족될 때 컨테이너를 미리 생성합니다. 사용자가 지난 28일 동안 보호된 보기 또는 Application Guard에서 파일을 열었다는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="ef663-251">To provide users with the expected file-opening experience, Application Guard uses logic to pre-create a container when the following heuristic is met on a system: A user has opened a file in either Protected View or Application Guard in the past 28 days.</span></span>

<span data-ttu-id="ef663-252">이 이 이론이 충족될 경우 Office는 사용자가 Windows에 로그인한 후 사용자에 대한 Application Guard 컨테이너를 미리 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="ef663-252">When this heuristic is met, Office will pre-create an Application Guard container for the user after they sign in to Windows.</span></span> <span data-ttu-id="ef663-253">이 사전 만들기 작업이 진행 중이면 시스템에서 성능이 느려질 수 있지만 작업이 완료되면 즉시 효과가 해결됩니다.</span><span class="sxs-lookup"><span data-stu-id="ef663-253">While this pre-create operation is in progress, the system may experience slow performance, but the effect will resolve as soon as the operation completes.</span></span>

> [!NOTE]
> <span data-ttu-id="ef663-254">컨테이너를 미리 만드는 데 필요한 힌트는 사용자가 컨테이너를 사용할 때 Office 응용 프로그램에 의해 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="ef663-254">The hints needed for the heuristic to pre-create the container are generated by Office applications as a user uses them.</span></span> <span data-ttu-id="ef663-255">Application Guard가 사용하도록 설정된 새 시스템에 Office를 설치하는 경우 Office는 사용자가 시스템에서 트러프되지 않은 문서를 처음 열 때까지 컨테이너를 미리 만들지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="ef663-255">If a user installs Office on a new system where Application Guard is enabled, Office will not pre-create the container until after the first time a user opens an untrusted document on the system.</span></span> <span data-ttu-id="ef663-256">사용자는 이 첫 번째 파일을 Application Guard에서 여는 데 시간이 더 오래 걸리는 것으로 관찰합니다.</span><span class="sxs-lookup"><span data-stu-id="ef663-256">The user will observe that this first file takes longer to open in Application Guard.</span></span>

## <a name="known-issues"></a><span data-ttu-id="ef663-257">알려진 문제</span><span class="sxs-lookup"><span data-stu-id="ef663-257">Known issues</span></span>

* <span data-ttu-id="ef663-258">웹 링크(또는 )를 선택하면 `http` `https` 브라우저가 열립니다.</span><span class="sxs-lookup"><span data-stu-id="ef663-258">Selecting web links (`http` or `https`) doesn't open the browser.</span></span>
* <span data-ttu-id="ef663-259">현재 Application Guard를 사용하여 연 Office 문서에 RTF(서식 있는 텍스트) 콘텐츠 또는 이미지를 붙여 넣는 것은 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="ef663-259">Pasting rich text format (RTF) content or images in Office documents opened with Application Guard isn't supported at this time.</span></span>
* <span data-ttu-id="ef663-260">.NET 업데이트로 인해 Application Guard에서 파일이 열리지 못합니다.</span><span class="sxs-lookup"><span data-stu-id="ef663-260">Updates to .NET cause files to fail to open in Application Guard.</span></span> <span data-ttu-id="ef663-261">이 해결로 사용자는 이 오류가 발생하면 장치를 다시 시작할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ef663-261">As a workaround, users can restart their device when they come across this failure.</span></span> <span data-ttu-id="ef663-262">Application Guard 또는 Windows 샌드박스를 열 때 오류 Windows Defender 자세한 [정보를 제공합니다.](https://support.microsoft.com/help/4575917/receiving-an-error-message-when-attempting-to-open-windows-defender-ap)</span><span class="sxs-lookup"><span data-stu-id="ef663-262">Learn more about the issue at [Receiving an error message when attempting to open Windows Defender Application Guard or Windows Sandbox](https://support.microsoft.com/help/4575917/receiving-an-error-message-when-attempting-to-open-windows-defender-ap).</span></span>
