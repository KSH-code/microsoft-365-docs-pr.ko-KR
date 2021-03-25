---
title: macOS용 Microsoft Defender ATP 수동 배포
description: 명령줄에서 macOS용 Microsoft Defender ATP를 수동으로 설치합니다.
keywords: microsoft, defender, atp, mac, 설치, 배포, 제거, intune, jamf, macos, 카탈로나, mojave, high sierra
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: b2629eb3d13e6eb908644dfcade46a7ac2768637
ms.sourcegitcommit: 6f2288e0c863496dfd0ee38de754bd43096ab3e1
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/24/2021
ms.locfileid: "51187448"
---
# <a name="manual-deployment-for-microsoft-defender-for-endpoint-for-macos"></a><span data-ttu-id="39b40-104">MacOS용 끝점용 Microsoft Defender 수동 배포</span><span class="sxs-lookup"><span data-stu-id="39b40-104">Manual deployment for Microsoft Defender for Endpoint for macOS</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="39b40-105">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="39b40-105">**Applies to:**</span></span>
- [<span data-ttu-id="39b40-106">엔드포인트용 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="39b40-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="39b40-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="39b40-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="39b40-108">Endpoint용 Defender를 경험하고 싶나요?</span><span class="sxs-lookup"><span data-stu-id="39b40-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="39b40-109">무료 평가판에 등록합니다.</span><span class="sxs-lookup"><span data-stu-id="39b40-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-investigateip-abovefoldlink)

<span data-ttu-id="39b40-110">이 항목에서는 MacOS용 끝점용 Microsoft Defender를 수동으로 배포하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="39b40-110">This topic describes how to deploy Microsoft Defender for Endpoint for macOS manually.</span></span> <span data-ttu-id="39b40-111">배포를 성공적으로 수행하려면 다음 단계를 모두 완료해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="39b40-111">A successful deployment requires the completion of all of the following steps:</span></span>
- [<span data-ttu-id="39b40-112">설치 및 온보더링 패키지 다운로드</span><span class="sxs-lookup"><span data-stu-id="39b40-112">Download installation and onboarding packages</span></span>](#download-installation-and-onboarding-packages)
- [<span data-ttu-id="39b40-113">응용 프로그램 설치(macOS 10.15 및 이전 버전)</span><span class="sxs-lookup"><span data-stu-id="39b40-113">Application installation (macOS 10.15 and older versions)</span></span>](#application-installation-macos-1015-and-older-versions)
- [<span data-ttu-id="39b40-114">응용 프로그램 설치(macOS 11 이상 버전)</span><span class="sxs-lookup"><span data-stu-id="39b40-114">Application installation (macOS 11 and newer versions)</span></span>](#application-installation-macos-11-and-newer-versions)
- [<span data-ttu-id="39b40-115">클라이언트 구성</span><span class="sxs-lookup"><span data-stu-id="39b40-115">Client configuration</span></span>](#client-configuration)

## <a name="prerequisites-and-system-requirements"></a><span data-ttu-id="39b40-116">선행 조건 및 시스템 요구 사항</span><span class="sxs-lookup"><span data-stu-id="39b40-116">Prerequisites and system requirements</span></span>

<span data-ttu-id="39b40-117">시작하기 전에 [MacOS용 끝점용 Microsoft Defender](microsoft-defender-endpoint-mac.md) 주 페이지를 참조하여 현재 소프트웨어 버전에 대한 선행 조건 및 시스템 요구 사항에 대한 설명을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="39b40-117">Before you get started, see [the main Microsoft Defender for Endpoint for macOS page](microsoft-defender-endpoint-mac.md) for a description of prerequisites and system requirements for the current software version.</span></span>

## <a name="download-installation-and-onboarding-packages"></a><span data-ttu-id="39b40-118">설치 및 온보더링 패키지 다운로드</span><span class="sxs-lookup"><span data-stu-id="39b40-118">Download installation and onboarding packages</span></span>

<span data-ttu-id="39b40-119">Microsoft Defender 보안 센터에서 설치 및 온보딩 패키지를 다운로드합니다.</span><span class="sxs-lookup"><span data-stu-id="39b40-119">Download the installation and onboarding packages from Microsoft Defender Security Center:</span></span>

1. <span data-ttu-id="39b40-120">Microsoft Defender 보안 센터에서 설정 > 장치 관리 > **로 이동합니다.**</span><span class="sxs-lookup"><span data-stu-id="39b40-120">In Microsoft Defender Security Center, go to **Settings > Device Management > Onboarding**.</span></span>
2. <span data-ttu-id="39b40-121">페이지의 섹션 1에서 운영 체제를 **macOS로** 설정하고 배포 방법을 **로컬 스크립트로 설정합니다.**</span><span class="sxs-lookup"><span data-stu-id="39b40-121">In Section 1 of the page, set operating system to **macOS** and Deployment method to **Local script**.</span></span>
3. <span data-ttu-id="39b40-122">페이지의 섹션 2에서 설치 패키지 **다운로드를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="39b40-122">In Section 2 of the page, select **Download installation package**.</span></span> <span data-ttu-id="39b40-123">로컬 디렉터리에 wdav.pkg로 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="39b40-123">Save it as wdav.pkg to a local directory.</span></span>
4. <span data-ttu-id="39b40-124">페이지의 섹션 2에서 **온보더링 패키지 다운로드를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="39b40-124">In Section 2 of the page, select **Download onboarding package**.</span></span> <span data-ttu-id="39b40-125">동일한 디렉터리에 WindowsDefenderATPOnboardingPackage.zip 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="39b40-125">Save it as WindowsDefenderATPOnboardingPackage.zip to the same directory.</span></span>

    ![Microsoft Defender 보안 센터 스크린샷](images/atp-portal-onboarding-page.png)

5. <span data-ttu-id="39b40-127">명령 프롬프트에서 두 개의 파일이 있는지 확인해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="39b40-127">From a command prompt, verify that you have the two files.</span></span>
    
## <a name="application-installation-macos-1015-and-older-versions"></a><span data-ttu-id="39b40-128">응용 프로그램 설치(macOS 10.15 및 이전 버전)</span><span class="sxs-lookup"><span data-stu-id="39b40-128">Application installation (macOS 10.15 and older versions)</span></span>

<span data-ttu-id="39b40-129">이 프로세스를 완료하려면 디바이스에 관리자 권한이 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="39b40-129">To complete this process, you must have admin privileges on the device.</span></span>

1. <span data-ttu-id="39b40-130">Finder에서 다운로드한 wdav.pkg로 이동한 다음 을 열어 립니다.</span><span class="sxs-lookup"><span data-stu-id="39b40-130">Navigate to the downloaded wdav.pkg in Finder and open it.</span></span>

    ![앱 설치 스크린샷1](/windows/security/threat-protection/microsoft-defender-antivirus/images/mdatp-28-appinstall)

2. <span data-ttu-id="39b40-132">계속을 **선택하고** 사용 조건에 동의하고 메시지가 표시될 때 암호를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="39b40-132">Select **Continue**, agree with the License terms, and enter the password when prompted.</span></span>

    ![앱 설치 스크린샷2](/windows/security/threat-protection/microsoft-defender-antivirus/images/mdatp-29-appinstalllogin)

   > [!IMPORTANT]
   > <span data-ttu-id="39b40-134">Microsoft에서 드라이버를 설치할 수 있도록 허용하라는 메시지가 표시됩니다("시스템 확장 차단" 또는 "설치가 보류 중입니다." 또는 둘 다).</span><span class="sxs-lookup"><span data-stu-id="39b40-134">You will be prompted to allow a driver from Microsoft to be installed (either "System Extension Blocked" or "Installation is on hold" or both.</span></span> <span data-ttu-id="39b40-135">드라이버를 설치할 수 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="39b40-135">The driver must be allowed to be installed.</span></span>

   ![앱 설치 스크린샷3](/windows/security/threat-protection/microsoft-defender-antivirus/images/mdatp-30-systemextension)

3. <span data-ttu-id="39b40-137">보안 **기본 설정 열기** 또는 보안 및 개인 > 시스템 기본 & **를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="39b40-137">Select **Open Security Preferences** or **Open System Preferences > Security & Privacy**.</span></span> <span data-ttu-id="39b40-138">허용을 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="39b40-138">Select **Allow**:</span></span>

    ![보안 및 개인 정보 창 스크린샷](/windows/security/threat-protection/microsoft-defender-antivirus/images/mdatp-31-securityprivacysettings)

   <span data-ttu-id="39b40-140">설치가 진행됩니다.</span><span class="sxs-lookup"><span data-stu-id="39b40-140">The installation proceeds.</span></span>

   > [!CAUTION]
   > <span data-ttu-id="39b40-141">허용을 **선택하지** 않은 경우 5분 후에 설치가 진행됩니다.</span><span class="sxs-lookup"><span data-stu-id="39b40-141">If you don't select **Allow**, the installation will proceed after 5 minutes.</span></span> <span data-ttu-id="39b40-142">끝점용 Microsoft Defender가 로드되지만 실시간 보호와 같은 일부 기능은 사용하지 않도록 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="39b40-142">Microsoft Defender for Endpoint will be loaded, but some features, such as real-time protection, will be disabled.</span></span> <span data-ttu-id="39b40-143">이 [문제를 해결하는 방법에](mac-support-kext.md) 대한 자세한 내용은 커널 확장 문제 해결을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="39b40-143">See [Troubleshoot kernel extension issues](mac-support-kext.md) for information on how to resolve this.</span></span>

> [!NOTE]
> <span data-ttu-id="39b40-144">macOS는 끝점용 Microsoft Defender를 처음 설치할 때 디바이스 재부팅을 요청할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="39b40-144">macOS may request to reboot the device upon the first installation of Microsoft Defender for Endpoint.</span></span> <span data-ttu-id="39b40-145">실시간 보호는 장치를 다시부팅해야 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="39b40-145">Real-time protection will not be available until the device is rebooted.</span></span>

## <a name="application-installation-macos-11-and-newer-versions"></a><span data-ttu-id="39b40-146">응용 프로그램 설치(macOS 11 이상 버전)</span><span class="sxs-lookup"><span data-stu-id="39b40-146">Application installation (macOS 11 and newer versions)</span></span>

<span data-ttu-id="39b40-147">이 프로세스를 완료하려면 디바이스에 관리자 권한이 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="39b40-147">To complete this process, you must have admin privileges on the device.</span></span>

1. <span data-ttu-id="39b40-148">Finder에서 다운로드한 wdav.pkg로 이동한 다음 을 열어 립니다.</span><span class="sxs-lookup"><span data-stu-id="39b40-148">Navigate to the downloaded wdav.pkg in Finder and open it.</span></span>

    ![앱 설치 스크린샷4](images/big-sur-install-1.png)

2. <span data-ttu-id="39b40-150">계속을 **선택하고** 사용 조건에 동의하고 메시지가 표시될 때 암호를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="39b40-150">Select **Continue**, agree with the License terms, and enter the password when prompted.</span></span>

3. <span data-ttu-id="39b40-151">설치 프로세스가 끝나면 제품에서 사용하는 시스템 확장을 승인하기 위해 승격됩니다.</span><span class="sxs-lookup"><span data-stu-id="39b40-151">At the end of the installation process, you will be promoted to approve the system extensions used by the product.</span></span> <span data-ttu-id="39b40-152">보안 **기본 설정 열기 를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="39b40-152">Select **Open Security Preferences**.</span></span>

    ![시스템 확장 승인](images/big-sur-install-2.png)

4. <span data-ttu-id="39b40-154">보안 및 **개인 & 창에서** 허용을 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="39b40-154">From the **Security & Privacy** window, select **Allow**.</span></span>

    ![시스템 확장 보안 기본 설정1](images/big-sur-install-3.png)

5. <span data-ttu-id="39b40-156">Mac용 끝점용 Microsoft Defender와 함께 & 배포된 모든 시스템 확장에 대해 3단계를 반복합니다.</span><span class="sxs-lookup"><span data-stu-id="39b40-156">Repeat steps 3 & 4 for all system extensions distributed with Microsoft Defender for Endpoint for Mac.</span></span>

6. <span data-ttu-id="39b40-157">끝점 검색 및 응답 기능의 일부로, Mac용 끝점용 Microsoft Defender는 소켓 트래픽을 검사하고 이 정보를 Microsoft Defender 보안 센터 포털에 보고합니다.</span><span class="sxs-lookup"><span data-stu-id="39b40-157">As part of the Endpoint Detection and Response capabilities, Microsoft Defender for Endpoint for Mac inspects socket traffic and reports this information to the Microsoft Defender Security Center portal.</span></span> <span data-ttu-id="39b40-158">네트워크 트래픽을 필터링할 수 있는 끝점에 대한 Microsoft Defender 사용 권한을 부여하라는 메시지가 표시될 때 허용을 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="39b40-158">When prompted to grant Microsoft Defender for Endpoint permissions to filter network traffic, select **Allow**.</span></span>

    ![시스템 확장 보안 기본 설정2](images/big-sur-install-4.png)

7. <span data-ttu-id="39b40-160">시스템 **기본 설정** 보안 & 개인 정보 보호 탭으로  >   이동합니다. Microsoft Defender ATP 및 **Microsoft Defender ATP**  끝점 보안 확장에 모든 디스크 액세스 권한을 **부여합니다.** </span><span class="sxs-lookup"><span data-stu-id="39b40-160">Open **System Preferences** > **Security & Privacy** and navigate to the **Privacy** tab. Grant **Full Disk Access** permission to **Microsoft Defender ATP** and **Microsoft Defender ATP Endpoint Security Extension**.</span></span>

    ![전체 디스크 액세스](images/big-sur-install-5.png)

## <a name="client-configuration"></a><span data-ttu-id="39b40-162">클라이언트 구성</span><span class="sxs-lookup"><span data-stu-id="39b40-162">Client configuration</span></span>

1. <span data-ttu-id="39b40-163">macOS용 끝점용 Microsoft Defender를 MicrosoftDefenderATPOnboardingMacOs.py 디바이스에 wdav.pkg 및 파일을 복사합니다.</span><span class="sxs-lookup"><span data-stu-id="39b40-163">Copy wdav.pkg and MicrosoftDefenderATPOnboardingMacOs.py to the device where you deploy Microsoft Defender for Endpoint for macOS.</span></span>

    <span data-ttu-id="39b40-164">클라이언트 장치가 orgId와 연결되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="39b40-164">The client device is not associated with orgId.</span></span> <span data-ttu-id="39b40-165">*orgId 특성은* 비어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="39b40-165">Note that the *orgId* attribute is blank.</span></span>

    ```bash
    mdatp health --field org_id
    ```

2. <span data-ttu-id="39b40-166">Python 스크립트를 실행하여 구성 파일을 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="39b40-166">Run the Python script to install the configuration file:</span></span>

    ```bash
    /usr/bin/python MicrosoftDefenderATPOnboardingMacOs.py
    ```

3. <span data-ttu-id="39b40-167">이제 장치가 조직과 연결되어 있는지 확인하고 유효한 *orgId를 보고합니다.*</span><span class="sxs-lookup"><span data-stu-id="39b40-167">Verify that the device is now associated with your organization and reports a valid *orgId*:</span></span>

    ```bash
    mdatp health --field org_id
    ```

<span data-ttu-id="39b40-168">설치 후 오른쪽 위 모서리의 macOS 상태 표시줄에 Microsoft Defender 아이콘이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="39b40-168">After installation, you'll see the Microsoft Defender icon in the macOS status bar in the top-right corner.</span></span>

   ![상태 표시줄의 Microsoft Defender 아이콘 스크린샷](/windows/security/threat-protection/microsoft-defender-antivirus/images/mdatp-icon-bar)
   

## <a name="how-to-allow-full-disk-access"></a><span data-ttu-id="39b40-170">전체 디스크 액세스를 허용하는 방법</span><span class="sxs-lookup"><span data-stu-id="39b40-170">How to Allow Full Disk Access</span></span>

> [!CAUTION]
> <span data-ttu-id="39b40-171">macOS 10.15(카탈로니아)에는 새로운 보안 및 개인 정보 보호 향상 기능이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="39b40-171">macOS 10.15 (Catalina) contains new security and privacy enhancements.</span></span> <span data-ttu-id="39b40-172">이 버전부터 응용 프로그램은 기본적으로 명시적 동의 없이 디스크의 특정 위치(예: 문서, 다운로드, 데스크톱 등)에 액세스할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="39b40-172">Beginning with this version, by default, applications are not able to access certain locations on disk (such as Documents, Downloads, Desktop, etc.) without explicit consent.</span></span> <span data-ttu-id="39b40-173">이 동의가 없는 경우 끝점용 Microsoft Defender는 장치를 완전히 보호할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="39b40-173">In the absence of this consent, Microsoft Defender for Endpoint is not able to fully protect your device.</span></span>

<span data-ttu-id="39b40-174">동의를 부여하기 위해 시스템 기본 설정 -> 보안 & 개인 정보 -> 개인 정보 -> 전체 디스크 액세스를 열 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="39b40-174">To grant consent, open System Preferences -> Security & Privacy -> Privacy -> Full Disk Access.</span></span> <span data-ttu-id="39b40-175">대화 상자 아래쪽에서 잠금 아이콘을 클릭하여 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="39b40-175">Click the lock icon to make changes (bottom of the dialog box).</span></span> <span data-ttu-id="39b40-176">끝점용 Microsoft Defender를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="39b40-176">Select Microsoft Defender for Endpoint.</span></span>

## <a name="logging-installation-issues"></a><span data-ttu-id="39b40-177">로깅 설치 문제</span><span class="sxs-lookup"><span data-stu-id="39b40-177">Logging installation issues</span></span>

<span data-ttu-id="39b40-178">오류가 [발생할](mac-resources.md#logging-installation-issues) 때 설치 관리자에 의해 생성된 자동으로 생성된 로그를 찾는 방법에 대한 자세한 내용은 설치 문제 로깅을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="39b40-178">See [Logging installation issues](mac-resources.md#logging-installation-issues) for more information on how to find the automatically generated log that is created by the installer when an error occurs.</span></span>

## <a name="uninstallation"></a><span data-ttu-id="39b40-179">제거</span><span class="sxs-lookup"><span data-stu-id="39b40-179">Uninstallation</span></span>

<span data-ttu-id="39b40-180">클라이언트 [장치에서](mac-resources.md#uninstalling) macOS용 끝점용 Microsoft Defender를 제거하는 방법에 대한 자세한 내용은 제거를 참조합니다.</span><span class="sxs-lookup"><span data-stu-id="39b40-180">See [Uninstalling](mac-resources.md#uninstalling) for details on how to remove Microsoft Defender for Endpoint for macOS from client devices.</span></span>
