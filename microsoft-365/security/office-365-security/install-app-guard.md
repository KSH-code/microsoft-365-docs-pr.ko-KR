---
title: 관리자를 위한 Office 365용 Application Guard(공개 미리 보기)
keywords: application guard, 보호, 격리, 격리된 컨테이너, 하드웨어 격리
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
description: 하드웨어 기반의 최신 버전을 다운로드합니다. 악용 또는 악의적인 링크와 같은 현재 및 새로운 공격이 직원 생산성 및 엔터프라이즈 보안을 방해하지 않도록 방지합니다.
ms.openlocfilehash: f5a5feb14db75c5baccecf0c6afafe0c42517224
ms.sourcegitcommit: 9833f95ab6ab95aea20d68a277246dca2223f93d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/11/2021
ms.locfileid: "49794511"
---
# <a name="application-guard-for-office-public-preview-for-admins"></a><span data-ttu-id="4064a-105">관리자를 위한 Office용 Application Guard(공개 미리 보기)</span><span class="sxs-lookup"><span data-stu-id="4064a-105">Application Guard for Office (public preview) for admins</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="4064a-106">**적용된 사항은 다음입니다.** Microsoft 365용 Word, Excel 및 PowerPoint, Windows 10 Enterprise</span><span class="sxs-lookup"><span data-stu-id="4064a-106">**Applies to:** Word, Excel, and PowerPoint for Microsoft 365, Windows 10 Enterprise</span></span>

> [!IMPORTANT]
> <span data-ttu-id="4064a-107">일부 정보는 상업적으로 출시되기 전에 상당수 수정될 수 있는 미리 판매된 제품과 관련이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4064a-107">Some information relates to a prereleased product which may be substantially modified before it's commercially released.</span></span> <span data-ttu-id="4064a-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span><span class="sxs-lookup"><span data-stu-id="4064a-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span></span>

<span data-ttu-id="4064a-109">Microsoft Defender Application Guard for Office(Office용 Application Guard)는 신뢰할 수 없는 파일이 신뢰할 수 있는 리소스에 액세스하지 못하게 하여 새로운 공격으로부터 엔터프라이즈를 안전하게 보호합니다.</span><span class="sxs-lookup"><span data-stu-id="4064a-109">Microsoft Defender Application Guard for Office (Application Guard for Office) helps prevent untrusted files from accessing trusted resources, keeping your enterprise safe from new and emerging attacks.</span></span> <span data-ttu-id="4064a-110">이 문서에서는 관리자에게 Office용 Application Guard의 미리 보기에 대한 디바이스를 설정하는 데 대해 간행합니다.</span><span class="sxs-lookup"><span data-stu-id="4064a-110">This article walks admins through setting up devices for a preview of Application Guard for Office.</span></span> <span data-ttu-id="4064a-111">디바이스에서 Office용 Application Guard를 사용하도록 설정하기 위한 시스템 요구 사항 및 설치 단계에 대한 정보를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="4064a-111">It provides information about system requirements and installation steps to enable Application Guard for Office on a device.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="4064a-112">필수 구성 요소</span><span class="sxs-lookup"><span data-stu-id="4064a-112">Prerequisites</span></span>

### <a name="minimum-hardware-requirements"></a><span data-ttu-id="4064a-113">최소 하드웨어 요구 사항</span><span class="sxs-lookup"><span data-stu-id="4064a-113">Minimum hardware requirements</span></span>

* <span data-ttu-id="4064a-114">**CPU**: 64비트, 4코어(실제 또는 가상), 가상화 확장(Intel VT-x OR AMD-V), Core i5 동등 이상 권장</span><span class="sxs-lookup"><span data-stu-id="4064a-114">**CPU**: 64-bit, 4 cores (physical or virtual), virtualization extensions   (Intel VT-x OR AMD-V), Core i5 equivalent or higher recommended</span></span>
* <span data-ttu-id="4064a-115">**실제 메모리:** 8GB RAM</span><span class="sxs-lookup"><span data-stu-id="4064a-115">**Physical memory**: 8-GB RAM</span></span>
* <span data-ttu-id="4064a-116">**하드 디스크**: 시스템 드라이브에 10GB의 사용 공간(SSD 권장)</span><span class="sxs-lookup"><span data-stu-id="4064a-116">**Hard disk**: 10 GB of free space on the system drive (SSD recommended)</span></span>

### <a name="minimum-software-requirements"></a><span data-ttu-id="4064a-117">최소 소프트웨어 요구 사항</span><span class="sxs-lookup"><span data-stu-id="4064a-117">Minimum software requirements</span></span>

* <span data-ttu-id="4064a-118">**Windows 10:** Windows 10 Enterprise 버전, 클라이언트 빌드 버전 2004(20H1) 빌드 19041</span><span class="sxs-lookup"><span data-stu-id="4064a-118">**Windows 10**: Windows 10 Enterprise edition, Client Build version 2004 (20H1) build 19041</span></span>
* <span data-ttu-id="4064a-119">**Office**: Office 베타 채널 빌드 버전 2008 16.0.13212 이상</span><span class="sxs-lookup"><span data-stu-id="4064a-119">**Office**: Office Beta Channel Build version 2008 16.0.13212 or later</span></span>
* <span data-ttu-id="4064a-120">**업데이트 패키지:** Windows 10 월별 누적 보안 업데이트 [KB4571756](https://support.microsoft.com/help/4571756/windows-10-update-KB4571756)</span><span class="sxs-lookup"><span data-stu-id="4064a-120">**Update package**: Windows 10 cumulative monthly security updates [KB4571756](https://support.microsoft.com/help/4571756/windows-10-update-KB4571756)</span></span>

<span data-ttu-id="4064a-121">자세한 시스템 요구 사항은 [Microsoft Defender Application Guard의 시스템 요구 사항을 참조하세요.](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-application-guard/reqs-md-app-guard)</span><span class="sxs-lookup"><span data-stu-id="4064a-121">For detailed system requirements, refer to [System requirements for Microsoft Defender Application Guard](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-application-guard/reqs-md-app-guard).</span></span> <span data-ttu-id="4064a-122">Office Insider Preview 빌드에 대한 자세한 내용은 Office Insider Build 배포 [시작을 참조합니다.](https://insider.office.com/business/deploy)</span><span class="sxs-lookup"><span data-stu-id="4064a-122">To learn more about Office Insider Preview builds, refer to [Getting started on deploying Office Insider builds](https://insider.office.com/business/deploy).</span></span>

### <a name="licensing-requirements"></a><span data-ttu-id="4064a-123">라이선스 요구 사항</span><span class="sxs-lookup"><span data-stu-id="4064a-123">Licensing requirements</span></span>

* <span data-ttu-id="4064a-124">Microsoft 365 E5 또는 Microsoft 365 E5 보안</span><span class="sxs-lookup"><span data-stu-id="4064a-124">Microsoft 365 E5 or Microsoft 365 E5 Security</span></span>

## <a name="deploy-application-guard-for-office"></a><span data-ttu-id="4064a-125">Office용 Application Guard 배포</span><span class="sxs-lookup"><span data-stu-id="4064a-125">Deploy Application Guard for Office</span></span>

### <a name="enable-application-guard-for-office"></a><span data-ttu-id="4064a-126">Office용 Application Guard 사용</span><span class="sxs-lookup"><span data-stu-id="4064a-126">Enable Application Guard for Office</span></span>

1. <span data-ttu-id="4064a-127">Windows 10 월별 누적 보안 업데이트 **KB4571756을 다운로드하여 설치합니다.**</span><span class="sxs-lookup"><span data-stu-id="4064a-127">Download and install **Windows 10 cumulative monthly security updates KB4571756**.</span></span>

2. <span data-ttu-id="4064a-128">Windows **기능에서 Microsoft Defender Application Guard를** 선택하고 확인을 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="4064a-128">Select **Microsoft Defender Application Guard** under Windows Features and  select **OK**.</span></span> <span data-ttu-id="4064a-129">Application Guard 기능을 사용하도록 설정하면 시스템을 다시 시작하라는 메시지가 표시될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4064a-129">Enabling the Application Guard feature will prompt a system reboot.</span></span> <span data-ttu-id="4064a-130">지금 다시 시작하거나 3단계 후에 다시 시작하게 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4064a-130">You can choose to reboot now or after step 3.</span></span>

   ![AG를 보여 주며 Windows 기능 대화 상자](../../media/ag03-deploy.png)

   <span data-ttu-id="4064a-132">관리자 권한으로 다음 PowerShell 명령을 실행하여 이 기능을 사용할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4064a-132">The feature can also be enabled by running the following PowerShell command as administrator:</span></span>

   ```powershell
   Enable-WindowsOptionalFeature -online -FeatureName Windows-Defender-ApplicationGuard
   ```

3. <span data-ttu-id="4064a-133">컴퓨터 구성 관리 템플릿 Windows 구성 요소 Microsoft Defender Application Guard에 있는 관리 모드 그룹 정책에서 **\\ Microsoft \\ \\ Defender Application Guard를 찾아 봐야 합니다.**</span><span class="sxs-lookup"><span data-stu-id="4064a-133">Look for the Microsoft Defender Application Guard in Managed Mode group policy located at **Computer Configuration\\Administrative Templates\\Windows Components\\Microsoft Defender Application Guard**.</span></span> <span data-ttu-id="4064a-134">옵션에서 값을 **2** 또는 **3으로** 설정한 다음 확인 또는 적용을 선택하여 이 **정책을** **켜야 합니다.**</span><span class="sxs-lookup"><span data-stu-id="4064a-134">Turn this policy on by setting the value under Options as **2** or **3** then selecting **OK** or **Apply**.</span></span>

   ![관리 모드에서 AG 켜기](../../media/ag04-deploy.png)

   <span data-ttu-id="4064a-136">또는 해당 CSP 정책을 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4064a-136">Alternatively, you can set the corresponding CSP policy:</span></span>

   > <span data-ttu-id="4064a-137">OMA-URI: **./Device/Vendor/MSFT/WindowsDefenderApplicationGuard/Settings/AllowWindowsDefenderApplicationGuard**</span><span class="sxs-lookup"><span data-stu-id="4064a-137">OMA-URI: **./Device/Vendor/MSFT/WindowsDefenderApplicationGuard/Settings/AllowWindowsDefenderApplicationGuard**</span></span> <br> <span data-ttu-id="4064a-138">데이터 형식: **정수**</span><span class="sxs-lookup"><span data-stu-id="4064a-138">Data type: **Integer**</span></span> <br> <span data-ttu-id="4064a-139">값: **2**</span><span class="sxs-lookup"><span data-stu-id="4064a-139">Value: **2**</span></span>

4. <span data-ttu-id="4064a-140">시스템을 다시부팅합니다.</span><span class="sxs-lookup"><span data-stu-id="4064a-140">Reboot the system.</span></span>

### <a name="set-diagnostics--feedback-to-send-full-data"></a><span data-ttu-id="4064a-141">전체 데이터를 & 진단 및 피드백 설정</span><span class="sxs-lookup"><span data-stu-id="4064a-141">Set Diagnostics & feedback to send full data</span></span>

<span data-ttu-id="4064a-142">이 단계에서는 문제를 식별하고 해결하는 데 필요한 데이터가 Microsoft에 도달하는지 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4064a-142">This step ensures that the data necessary to identify and fix problems is reaching Microsoft.</span></span> <span data-ttu-id="4064a-143">Windows 장치에서 진단을 사용하도록 설정하려면 다음 단계를 따르세요.</span><span class="sxs-lookup"><span data-stu-id="4064a-143">Follow these steps to enable diagnostics on your Windows device:</span></span>

1. <span data-ttu-id="4064a-144">시작 **메뉴에서** 설정을 니다.</span><span class="sxs-lookup"><span data-stu-id="4064a-144">Open **Settings** from the Start menu.</span></span>

   ![시작 메뉴](../../media/ag05-diagnostic.png)

2. <span data-ttu-id="4064a-146">**Windows 설정에서** 개인 정보를 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="4064a-146">On **Windows Settings**, select **Privacy**.</span></span>

   ![Windows 설정 메뉴](../../media/ag06-diagnostic.png)

3. <span data-ttu-id="4064a-148">개인 정보 보호에서 **진단** 및 & 선택적 진단 **데이터를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="4064a-148">Under Privacy, select **Diagnostics & feedback** and select **Optional diagnostic data**.</span></span>

   ![진단 및 피드백 메뉴](../../media/ag07a-diagnostic.png)

<span data-ttu-id="4064a-150">Windows 진단 설정 구성에 대한 자세한 내용은 조직에서 Windows 진단 데이터 [구성을 참조하세요.](https://docs.microsoft.com/windows/privacy/configure-windows-diagnostic-data-in-your-organization#enterprise-management)</span><span class="sxs-lookup"><span data-stu-id="4064a-150">For more on configuring Windows diagnostic settings, refer to [Configuring Windows diagnostic data in your organization](https://docs.microsoft.com/windows/privacy/configure-windows-diagnostic-data-in-your-organization#enterprise-management).</span></span>

### <a name="confirm-that-application-guard-for-office-is-enabled-and-working"></a><span data-ttu-id="4064a-151">Office용 Application Guard가 사용하도록 설정되어 있으며 작동하고 있는지 확인</span><span class="sxs-lookup"><span data-stu-id="4064a-151">Confirm that Application Guard for Office is enabled and working</span></span>

<span data-ttu-id="4064a-152">Office용 Application Guard를 사용하도록 설정되어 있는지 확인하기 전에 정책이 배포된 장치에서 Word, Excel 또는 PowerPoint를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="4064a-152">Before confirming that the Application Guard for Office is enabled, launch Word, Excel, or PowerPoint on a device where the policies have been deployed.</span></span> <span data-ttu-id="4064a-153">Office가 정품 인증되어 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="4064a-153">Make sure Office is activated.</span></span> <span data-ttu-id="4064a-154">먼저 작업 ID를 사용하여 Office 제품을 정품 인증해야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4064a-154">You may need to use your work identity to activate the Office product first.</span></span>

<span data-ttu-id="4064a-155">Office용 Application Guard가 사용하도록 설정되어 있는지 확인을 위해 Word, Excel 또는 PowerPoint를 시작하고 트러설되지 않은 문서를 열 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4064a-155">To confirm that Application Guard for Office is now enabled, launch Word, Excel, or PowerPoint and open an untrusted document.</span></span> <span data-ttu-id="4064a-156">예를 들어 인터넷에서 다운로드한 문서나 조직 외부의 사람이 전자 메일 첨부 파일을 열 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4064a-156">For example, you can open a document downloaded from the internet or an email attachment from someone outside your organization.</span></span>

<span data-ttu-id="4064a-157">On the first launch of an untrusted file, you may see an Office splash screen like the one below.</span><span class="sxs-lookup"><span data-stu-id="4064a-157">On the first launch of an untrusted file, you may see an Office splash screen like the one below.</span></span> <span data-ttu-id="4064a-158">Office용 Application Guard가 활성화되고 파일이 열리면서 이 시간이 표시될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4064a-158">It might show for some time while Application Guard for Office is being activated and the file is being opened.</span></span> <span data-ttu-id="4064a-159">이후에는 트러설이 없는 파일을 더 빠르게 실행해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4064a-159">Subsequent launches of untrusted files should be faster.</span></span>

![Office 앱 시작 화면](../../media/ag08-confirm.png)

<span data-ttu-id="4064a-161">파일을 열면 Office용 Application Guard에서 파일이 열렸다는 몇 가지 시각적 표시기가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="4064a-161">Upon being opened, the file should display a few visual indicators that the file was opened inside Application Guard for Office:</span></span>

* <span data-ttu-id="4064a-162">리본 메뉴의 콜아웃</span><span class="sxs-lookup"><span data-stu-id="4064a-162">A callout in the ribbon</span></span>

  ![작은 App Guard 메모를 표시하는 Doc 파일](../../media/ag09-confirm.png)

* <span data-ttu-id="4064a-164">작업 표시줄에 방패가 있는 응용 프로그램 아이콘</span><span class="sxs-lookup"><span data-stu-id="4064a-164">The application icon with a shield in the taskbar</span></span>

  ![작업 표시줄의 아이콘](../../media/ag12-limitations.png)

## <a name="configure-application-guard-for-office"></a><span data-ttu-id="4064a-166">Office용 Application Guard 구성</span><span class="sxs-lookup"><span data-stu-id="4064a-166">Configure Application Guard for Office</span></span>

<span data-ttu-id="4064a-167">Office는 Office용 Application Guard의 기능을 구성할 수 있도록 다음과 같은 정책을 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="4064a-167">Office supports the following policies to enable you to configure the capabilities of Application Guard for Office.</span></span> <span data-ttu-id="4064a-168">이러한 정책은 그룹 정책 또는 Office 클라우드 정책 서비스를 통해 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4064a-168">These policies can be configured through Group policies or through the Office cloud policy service.</span></span>

> [!NOTE]
> <span data-ttu-id="4064a-169">이러한 정책은 곧 제공될 예정입니다.</span><span class="sxs-lookup"><span data-stu-id="4064a-169">These policies will become available soon.</span></span>
> <span data-ttu-id="4064a-170">또한 이러한 정책을 구성하면 Office용 Application Guard에서 연 파일에 대해 일부 기능을 사용하지 않도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4064a-170">Also, configuring these policies can disable some functionalities for files opened in Application Guard for Office.</span></span>

|<span data-ttu-id="4064a-171">정책</span><span class="sxs-lookup"><span data-stu-id="4064a-171">Policy</span></span>|<span data-ttu-id="4064a-172">설명</span><span class="sxs-lookup"><span data-stu-id="4064a-172">Description</span></span>|
|---|---|
|<span data-ttu-id="4064a-173">Office에 Application Guard를 사용하지 않도록 설정</span><span class="sxs-lookup"><span data-stu-id="4064a-173">Disable Application Guard for Office</span></span>|<span data-ttu-id="4064a-174">이 정책을 사용하도록 설정하면 Word, Excel 및 PowerPoint에서 Office용 Application Guard 대신 보호된 보기의 고리 컨테이너를 사용하도록 강제로 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="4064a-174">Enabling this policy will force Word, Excel, and PowerPoint to use the Protected View isolation container instead of Application Guard for Office.</span></span> <span data-ttu-id="4064a-175">이 정책은 Edge를 사용하도록 설정한 채로 두는 데 문제가 있는 경우 Office용 Application Guard를 일시적으로 사용하지 않도록 설정하는 데 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4064a-175">This policy can be used to temporarily disable Application Guard for Office when there are issues in leaving it enabled for Edge.</span></span>|
|<span data-ttu-id="4064a-176">Application Guard에서 연 문서에 대해 복사/붙여넣기 사용 안</span><span class="sxs-lookup"><span data-stu-id="4064a-176">Disable copy/paste for documents opened in Application Guard</span></span>|<span data-ttu-id="4064a-177">이 정책을 사용하도록 설정하면 사용자가 Office용 Application Guard에서 연 문서의 콘텐츠를 복사하여 외부에서 연 문서에 붙여넣을 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="4064a-177">Enabling this policy will prevent a user from copying and pasting content from a document opened in Application Guard for Office to a document opened outside it.</span></span>|
|<span data-ttu-id="4064a-178">사용자가 파일에서 Application Guard 보호를 제거하지 못하게 방지</span><span class="sxs-lookup"><span data-stu-id="4064a-178">Prevent users from removing Application Guard protection on files</span></span>|<span data-ttu-id="4064a-179">이 정책을 사용하면 Application Guard 보호를 사용하지 않도록 설정하거나 Application Guard 외부에서 파일을 여는 옵션이 제거됩니다(Office 응용 프로그램 환경 내에서).</span><span class="sxs-lookup"><span data-stu-id="4064a-179">Enabling this policy will remove the option (within the Office application experience) to disable Application Guard protection or open a file outside Application Guard.</span></span> <p> <span data-ttu-id="4064a-180">**참고:** 사용자는 파일에서 웹 표시 속성을 수동으로 제거하거나 문서를 신뢰할 수 있는 위치로 이동하여 이 정책을 무시할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4064a-180">**Note:** Users can still bypass this policy by manually removing the mark-of-the-web property from the file or by moving a document to a Trusted location.</span></span>|
|<span data-ttu-id="4064a-181">Application Guard에서 연 문서에서 인쇄 제한</span><span class="sxs-lookup"><span data-stu-id="4064a-181">Restrict printing from documents opened in Application Guard</span></span>|<span data-ttu-id="4064a-182">이 정책을 사용하도록 설정하면 사용자가 Office용 Application Guard에서 연 파일에서 인쇄할 수 있는 프린터가 제한됩니다.</span><span class="sxs-lookup"><span data-stu-id="4064a-182">Enabling this policy will limit printers a user can print to from a file opened in Application Guard for Office.</span></span> <span data-ttu-id="4064a-183">예를 들어 이 정책을 사용하여 사용자가 PDF로만 인쇄하도록 제한할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4064a-183">For example, you can use this policy to restrict users to only print to PDF.</span></span>|
|<span data-ttu-id="4064a-184">Application Guard에서 연 문서에 대한 카메라 및 마이크 액세스 끄기</span><span class="sxs-lookup"><span data-stu-id="4064a-184">Turn off camera and microphone access for documents opened in Application Guard</span></span>|<span data-ttu-id="4064a-185">이 정책을 사용하도록 설정하면 Office용 Application Guard 내에서 카메라 및 마이크에 대한 Office 액세스가 제거됩니다.</span><span class="sxs-lookup"><span data-stu-id="4064a-185">Enabling this policy will remove Office access to Camera and Microphone inside Application Guard for Office.</span></span>|
|

> [!NOTE]
> <span data-ttu-id="4064a-186">다음 정책을 적용하려면 사용자가 로그오프했다가 Windows에 다시 로그인해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4064a-186">The following policies will require the user to log off and re-login to Windows to take effect:</span></span>
>
> * <span data-ttu-id="4064a-187">Application Guard에서 연 문서에 대해 복사/붙여넣기 사용 안</span><span class="sxs-lookup"><span data-stu-id="4064a-187">Disable copy/paste for documents opened in Application Guard</span></span>
> * <span data-ttu-id="4064a-188">Application Guard에서 연 문서에 대한 인쇄 제한</span><span class="sxs-lookup"><span data-stu-id="4064a-188">Restrict printing for documents opened in Application Guard</span></span>
> * <span data-ttu-id="4064a-189">Application Guard에서 연 문서에 대한 카메라 및 마이크 액세스 끄기</span><span class="sxs-lookup"><span data-stu-id="4064a-189">Turn off camera and mic access to documents opened in Application Guard</span></span>

## <a name="submit-feedback"></a><span data-ttu-id="4064a-190">피드백 제출</span><span class="sxs-lookup"><span data-stu-id="4064a-190">Submit feedback</span></span>

### <a name="submit-feedback-via-feedback-hub"></a><span data-ttu-id="4064a-191">피드백 허브를 통해 피드백 제출</span><span class="sxs-lookup"><span data-stu-id="4064a-191">Submit feedback via Feedback Hub</span></span>

<span data-ttu-id="4064a-192">Office용 Application Guard를 시작하면 피드백 허브를 통해 피드백을 제출하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="4064a-192">If you encounter any issues when launching Application Guard for Office, you are encouraged to submit your feedback via Feedback Hub:</span></span>

1. <span data-ttu-id="4064a-193">피드백 허브 **앱을 열고** 로그인합니다.</span><span class="sxs-lookup"><span data-stu-id="4064a-193">Open the **Feedback Hub app** and sign in.</span></span>

2. <span data-ttu-id="4064a-194">Application Guard를 시작하는 동안 오류 대화 상자가 표시된 경우 오류 대화 상자에서 **Microsoft에** 보고를 선택하여 새 피드백 제출을 시작하십시오.</span><span class="sxs-lookup"><span data-stu-id="4064a-194">If you get an error dialog while launching Application Guard, select **Report to Microsoft** in the error dialog to start a new feedback submission.</span></span> <span data-ttu-id="4064a-195">그렇지 않은 경우 Application Guard에 대한 올바른 범주를 선택한 다음 오른쪽 상단 근처에서 + 새 피드백 <https://aka.ms/mdagoffice-fb> 추가를 선택합니다. </span><span class="sxs-lookup"><span data-stu-id="4064a-195">Otherwise, navigate to <https://aka.ms/mdagoffice-fb> to select the correct category for Application Guard, then select **+ Add new feedback** near the top right.</span></span>

3. <span data-ttu-id="4064a-196">아직 **입력하지** 않은 경우 피드백 요약 상자에 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="4064a-196">Fill in the **Summarize your feedback** box if it isn't already filled in for you.</span></span>

4. <span data-ttu-id="4064a-197">자세한 설명 **상자에** 경험한 문제와 수행한 단계에 대한 자세한 설명을 입력하고 다음을 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="4064a-197">Fill in the **Explain in more detail** box with a detailed description of the issue you experienced and what steps you took, then select **Next**.</span></span>

5. <span data-ttu-id="4064a-198">문제 옆의 거품을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="4064a-198">Select the bubble next to Problem.</span></span> <span data-ttu-id="4064a-199">선택한 범주가 보안 및 개인 정보 **\> 보호 Microsoft Defender Application Guard (Office)이고** 다음을 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="4064a-199">Make sure the category selected is **Security and Privacy \> Microsoft Defender Application Guard – Office**, then select **Next**.</span></span>

6. <span data-ttu-id="4064a-200">새 **피드백을 선택하고** 다음을 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="4064a-200">Select **New feedback**, then **Next**.</span></span>

7. <span data-ttu-id="4064a-201">이 문제의 추적을 수집합니다.</span><span class="sxs-lookup"><span data-stu-id="4064a-201">Collect traces about the issue:</span></span>

   1. <span data-ttu-id="4064a-202">내 문제 **다시 시작 타일을 확장합니다.**</span><span class="sxs-lookup"><span data-stu-id="4064a-202">Expand the **Recreate my problem** tile.</span></span>

   2. <span data-ttu-id="4064a-203">Application Guard가 실행되는 동안 발생하는 문제가 발생하면 Application Guard 인스턴스를 런타이저를 열어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4064a-203">If the issue you're experiencing occurs while Application Guard is running, open an Application Guard instance.</span></span> <span data-ttu-id="4064a-204">이렇게 하면 Application Guard 컨테이너 내에서 추가 추적을 수집할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4064a-204">Doing this allows additional traces to be collected from within the Application Guard container.</span></span>

   3. <span data-ttu-id="4064a-205">**녹음/녹화 시작을** 선택하고 타일이 회전을 중지할 때까지 기다렸다가 기록 *중지를 선택합니다.*</span><span class="sxs-lookup"><span data-stu-id="4064a-205">Select **Start recording** and wait for the tile to stop spinning and say *Stop recording*.</span></span>

   4. <span data-ttu-id="4064a-206">Application Guard에서 문제를 완전히 재현합니다.</span><span class="sxs-lookup"><span data-stu-id="4064a-206">Fully reproduce the issue with Application Guard.</span></span> <span data-ttu-id="4064a-207">여기에는 Application Guard 인스턴스를 시작하려고 시도하고 실패할 때까지 기다리거나 실행 중인 Application Guard 인스턴스에서 문제를 재현하는 것이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="4064a-207">This might include attempting to launch an Application Guard instance and waiting until it fails, or reproducing an issue in a running Application Guard instance.</span></span>

   5. <span data-ttu-id="4064a-208">녹음 중지 **타일을** 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="4064a-208">Select the **Stop recording** tile.</span></span>

   6. <span data-ttu-id="4064a-209">컨테이너 진단도 수집할 수 있도록 제출 후 몇 분까지 실행 중인 Application Guard 인스턴스/s를 열어 두십시오.</span><span class="sxs-lookup"><span data-stu-id="4064a-209">Keep any running Application Guard instance/s open, even until a few minutes after submission, so that container diagnostics can also be collected.</span></span>

8. <span data-ttu-id="4064a-210">문제와 관련된 스크린샷 또는 파일을 첨부합니다.</span><span class="sxs-lookup"><span data-stu-id="4064a-210">Attach any relevant screenshots or files related to the problem.</span></span>

9. <span data-ttu-id="4064a-211">**전송** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="4064a-211">Select **Submit**.</span></span>

### <a name="submit-feedback-via-office-customer-voice"></a><span data-ttu-id="4064a-212">Office Customer Voice를 통해 피드백 제출</span><span class="sxs-lookup"><span data-stu-id="4064a-212">Submit feedback via Office Customer Voice</span></span>

<span data-ttu-id="4064a-213">Office 문서를 Application Guard에서 열 때 문제가 발생하는 경우 Office 내에서 피드백을 제출할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4064a-213">You may also submit feedback from within Office if the issue happens when Office documents are opened in Application Guard.</span></span> <span data-ttu-id="4064a-214">피드백을 [제출할 수 있는 Office Insider Handbook을](https://insider.office.com/handbook) 참조합니다.</span><span class="sxs-lookup"><span data-stu-id="4064a-214">Refer to the [Office Insider Handbook](https://insider.office.com/handbook) for submitting feedback.</span></span>

## <a name="integration-with-microsoft-defender-for-endpoint-and-microsoft-defender-for-office-365"></a><span data-ttu-id="4064a-215">끝점용 Microsoft Defender 및 Office 365용 Microsoft Defender와의 통합</span><span class="sxs-lookup"><span data-stu-id="4064a-215">Integration with Microsoft Defender for Endpoint and Microsoft Defender for Office 365</span></span>

<span data-ttu-id="4064a-216">Office용 Application Guard는 격리된 환경에서 일어나는 악의적인 활동에 대한 모니터링 및 경고를 제공하기 위해 끝점용 Microsoft Defender와 통합되었습니다.</span><span class="sxs-lookup"><span data-stu-id="4064a-216">Application Guard for Office is integrated with Microsoft Defender for Endpoint to provide monitoring and alerting on malicious activity happening in the isolated environment.</span></span>

<span data-ttu-id="4064a-217">끝점용 Microsoft Defender는 엔터프라이즈 네트워크가 고급 위협을 방지, 감지, 조사 및 대응하도록 설계된 보안 플랫폼입니다.</span><span class="sxs-lookup"><span data-stu-id="4064a-217">Microsoft Defender for Endpoint is a security platform designed to help enterprise networks prevent, detect, investigate, and respond to advanced threats.</span></span> <span data-ttu-id="4064a-218">이 플랫폼에 대한 자세한 내용은 [끝점용 Microsoft Defender 페이지를 방문하세요.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp)</span><span class="sxs-lookup"><span data-stu-id="4064a-218">For more details about this platform, visit the [Microsoft Defender for Endpoint](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp) page.</span></span> <span data-ttu-id="4064a-219">끝점용 Microsoft Defender 서비스에 대한 온보딩 장치에서 이 플랫폼에 디바이스를 [온보딩하는 방법을 자세히 알아보시고,](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/onboard-configure)</span><span class="sxs-lookup"><span data-stu-id="4064a-219">Learn more about onboarding devices to this platform at [Onboard devices to the Microsoft Defender for Endpoint service](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/onboard-configure).</span></span>

<span data-ttu-id="4064a-220">끝점용 Defender와 함께 작동하도록 Office 365용 Microsoft Defender를 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4064a-220">You can also configure Microsoft Defender for Office 365 to work with Defender for Endpoint.</span></span> <span data-ttu-id="4064a-221">[끝점용 Microsoft Defender와 Office 365용 Defender 통합을 참조합니다.](integrate-office-365-ti-with-wdatp.md)</span><span class="sxs-lookup"><span data-stu-id="4064a-221">Refer to [Integrate Defender for Office 365 with Microsoft Defender for Endpoint](integrate-office-365-ti-with-wdatp.md).</span></span>

## <a name="limitations-and-considerations"></a><span data-ttu-id="4064a-222">제한 사항 및 고려 사항</span><span class="sxs-lookup"><span data-stu-id="4064a-222">Limitations and considerations</span></span>

* <span data-ttu-id="4064a-223">Office용 Application Guard는 신뢰할 수 없는 문서가 컴퓨터에 있는 신뢰할 수 있는 회사 리소스, 인트라넷, 사용자의 ID 및 임의 파일에 액세스하지 않는 것을 격리하는 제한된 모드입니다.</span><span class="sxs-lookup"><span data-stu-id="4064a-223">Application Guard for Office is a restricted mode that isolates untrusted documents from accessing trusted corporate resources, intranet, the user's identity, and arbitrary files present on the computer.</span></span> <span data-ttu-id="4064a-224">따라서 사용자가 이러한 액세스에 종속된 기능에 액세스(예: 디스크에 로컬 파일에서 그림 삽입)에 액세스하면 오류가 발생하고 아래와 같은 프롬프트가 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="4064a-224">As a result, if a user tries to access a feature that has a dependency on such access, for example, inserting a picture from a local file on disk, it will fail and produce a prompt like the one below.</span></span> <span data-ttu-id="4064a-225">신뢰할 수 없는 문서가 신뢰할 수 있는 리소스에 액세스할 수 있도록 설정하려면 사용자가 문서에서 Application Guard 보호를 제거해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4064a-225">To enable an untrusted document to access trusted resources, users must remove Application Guard protection from the document.</span></span>

  ![안전한 유지를 위해 이 기능을 사용할 수 없는 경우를 설명하는 대화 상자](../../media/ag10-limitations.png)

  > [!NOTE]
  > <span data-ttu-id="4064a-227">사용자가 파일과 해당 원본을 신뢰하거나 출처를 신뢰할 수 있는 경우 보호 기능을 제거해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4064a-227">Advise users to only remove protection if they trust the file and its source or where it came from.</span></span>

* <span data-ttu-id="4064a-228">Office용 Application Guard에서는 매크로 및 ActiveX 컨트롤과 같은 문서의 활성 콘텐츠가 사용하지 않도록 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="4064a-228">Active content in documents like macros and ActiveX controls are disabled in Application Guard for Office.</span></span> <span data-ttu-id="4064a-229">사용자가 활성 콘텐츠를 사용하도록 설정하려면 Application Guard 보호를 제거해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4064a-229">Users need to remove Application Guard protection to enable active content.</span></span>

* <span data-ttu-id="4064a-230">다른 조직에서 네트워크 공유 또는 OneDrive, 비즈니스용 OneDrive 또는 SharePoint Online에서 공유된 파일에서 연 트러버설 파일이 Application Guard에서 읽기 전용으로 열립니다.</span><span class="sxs-lookup"><span data-stu-id="4064a-230">Untrusted files opened from network shares or files shared from OneDrive, OneDrive for Business, or SharePoint Online from a different organization open as read-only in Application Guard.</span></span> <span data-ttu-id="4064a-231">사용자는 이러한 파일의 로컬 복사본을 저장하여 컨테이너에서 작업을 계속하거나 보호 기능을 제거하여 원본 파일을 직접 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4064a-231">Users can save a local copy of such files to continue working in the container or remove protection to directly work with the original file.</span></span>

* <span data-ttu-id="4064a-232">IRM(정보 권한 관리)으로 보호되는 파일은 계속 보호된 보기에서 열립니다.</span><span class="sxs-lookup"><span data-stu-id="4064a-232">Files that are protected by Information Rights Management (IRM) continue to open in Protected View.</span></span>

* <span data-ttu-id="4064a-233">Office용 Application Guard에서 Office 응용 프로그램에 대한 사용자 지정은 사용자가 로그오프했다가 다시 로그인하거나 장치를 다시 시작한 후에도 지속되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="4064a-233">Any customizations to Office applications in Application Guard for Office will not persist after a user logs off and logs back in or reboots the device.</span></span>

* <span data-ttu-id="4064a-234">UIA 프레임워크를 사용하는 접근성 도구만 Office용 Application Guard에서 연 파일에 대한 접근성 있는 환경을 제공할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4064a-234">Only Accessibility tools that use the UIA framework can provide an accessible experience for files opened in Application Guard for Office.</span></span>

* <span data-ttu-id="4064a-235">설치 후 Application Guard를 처음 시작하려면 네트워크 연결이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="4064a-235">Network connectivity is required for the first launch of Application Guard after installation.</span></span> <span data-ttu-id="4064a-236">이는 Application Guard에서 라이선스의 유효성을 검사하는 데 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="4064a-236">This is required for Application Guard to validate the license.</span></span>

* <span data-ttu-id="4064a-237">문서의 정보 섹션에서 *마지막* 수정한 사용자 속성은 WDAGUtilityAccount를 사용자로 표시할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4064a-237">In the document's info section, the *Last Modified By* property may display WDAGUtilityAccount as the user.</span></span> <span data-ttu-id="4064a-238">데스크톱 사용자의 ID가 Application Guard 컨테이너 내에서 공유되지 않는 경우 Application Guard에 구성된 익명 사용자입니다.</span><span class="sxs-lookup"><span data-stu-id="4064a-238">This is the anonymous user configured in Application Guard given that the desktop user's identity is not shared inside the Application Guard container.</span></span>

## <a name="performance-optimizations-for-application-guard"></a><span data-ttu-id="4064a-239">Application Guard에 대한 성능 최적화</span><span class="sxs-lookup"><span data-stu-id="4064a-239">Performance optimizations for Application Guard</span></span>

<span data-ttu-id="4064a-240">이 섹션에서는 Office용 Application Guard에서 사용되는 성능 최적화에 대해 간략하게 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="4064a-240">This section provides an overview of the performance optimizations used in Application Guard for Office.</span></span> <span data-ttu-id="4064a-241">이 정보는 Application Guard를 사용하도록 설정한 경우 관리자가 Office 또는 전체 시스템 성능과 관련된 사용자의 보고서를 진단하는 데 도움이 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4064a-241">This information can help administrators diagnose reports from users related to the performance of Office or the overall system when Application Guard is enabled.</span></span>

<span data-ttu-id="4064a-242">Application Guard는 가상화된 컨테이너를 사용하여 시스템에서 트러운 문서를 분리합니다.</span><span class="sxs-lookup"><span data-stu-id="4064a-242">Application Guard uses a virtualized container to isolate untrusted documents away from the system.</span></span> <span data-ttu-id="4064a-243">컨테이너를 만들고 Application Guard 컨테이너를 설정하여 Office 문서를 열 때 성능 오버헤드가 발생합니다. 이로인하여 사용자가 트러운 문서를 열 때 사용자 환경에 부정적인 영향을 줄 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4064a-243">The process of creating a container and setting up the Application Guard container to open Office documents has a performance overhead that might negatively impact user experience when users open an  untrusted document.</span></span>

<span data-ttu-id="4064a-244">사용자에게 예상되는 파일 열기 환경을 제공하기 위해 Application Guard는 논리를 사용하여 시스템에서 다음 경험적이 충족될 때 컨테이너를 미리 생성합니다. 사용자가 지난 28일 동안 보호된 보기 또는 Application Guard에서 파일을 열었다는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="4064a-244">To provide users with the expected file opening experience, Application Guard uses logic to pre-create a container when the following heuristic is met on a system: A user has opened a file in either Protected View or Application Guard in the past 28 days.</span></span>

<span data-ttu-id="4064a-245">이 이 이론이 충족될 경우 Office는 사용자가 Windows에 로그인한 후 사용자에 대한 Application Guard 컨테이너를 미리 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="4064a-245">When this heuristic is met, Office will pre-create an Application Guard container for the user after they log in to Windows.</span></span> <span data-ttu-id="4064a-246">이 사전 만들기 작업이 진행 중이면 시스템에서 성능이 저하될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4064a-246">When this pre-create operation is in progress, the system may experience slow performance.</span></span> <span data-ttu-id="4064a-247">이 작업은 작업이 완료되면 즉시 해결됩니다.</span><span class="sxs-lookup"><span data-stu-id="4064a-247">This will resolve as soon as the operation completes.</span></span>

> [!NOTE]
> <span data-ttu-id="4064a-248">컨테이너를 미리 만드는 데 사용되는 힌트는 사용자가 컨테이너를 사용할 때 Office 응용 프로그램에 의해 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="4064a-248">The hints needed for the heuristic used to pre-create the container are generated by Office applications as a user uses them.</span></span> <span data-ttu-id="4064a-249">Application Guard가 사용하도록 설정된 새 시스템에 Office를 설치하는 경우 Office는 사용자가 시스템에서 트러프되지 않은 문서를 처음 열 때까지 컨테이너를 미리 만들지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="4064a-249">If a user installs Office on a new system where Application Guard is enabled, Office will not pre-create the container until after the first time a user opens an untrusted document on the system.</span></span> <span data-ttu-id="4064a-250">사용자는 이 첫 번째 파일을 Application Guard에서 여는 데 시간이 더 오래 걸리는 것으로 관찰합니다.</span><span class="sxs-lookup"><span data-stu-id="4064a-250">The user will observe that this first file takes longer to open in Application Guard.</span></span>

## <a name="known-issues-in-preview"></a><span data-ttu-id="4064a-251">미리 보기의 알려진 문제</span><span class="sxs-lookup"><span data-stu-id="4064a-251">Known issues in preview</span></span>

* <span data-ttu-id="4064a-252">웹 링크(또는 )를 클릭하면 `http` `https` 브라우저가 열립니다.</span><span class="sxs-lookup"><span data-stu-id="4064a-252">Clicking on web links (`http` or `https`) does not open the browser.</span></span>
* <span data-ttu-id="4064a-253">.NET 업데이트로 인해 Application Guard에서 파일이 열리지 못합니다.</span><span class="sxs-lookup"><span data-stu-id="4064a-253">.NET updates cause files to fail to open in Application Guard.</span></span> <span data-ttu-id="4064a-254">이 문제가 발생하면 사용자는 장치를 다시부팅할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4064a-254">As a workaround, users can reboot their device when this issue is encountered.</span></span> <span data-ttu-id="4064a-255">Application Guard 또는 Windows 샌드박스를 열고자 할 때 오류 [Windows Defender 자세히 알아보는 것이 좋습니다.](https://support.microsoft.com/help/4575917/receiving-an-error-message-when-attempting-to-open-windows-defender-ap)</span><span class="sxs-lookup"><span data-stu-id="4064a-255">Learn more about the issue at [Receiving an error message when attempting to open Windows Defender Application Guard or Windows Sandbox](https://support.microsoft.com/help/4575917/receiving-an-error-message-when-attempting-to-open-windows-defender-ap).</span></span>
