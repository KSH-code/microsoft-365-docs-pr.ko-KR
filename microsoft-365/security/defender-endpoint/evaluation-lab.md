---
title: 끝점용 Microsoft Defender 평가 랩
description: 끝점용 Microsoft Defender 기능에 대해 알아보고, 공격 시뮬레이션을 실행하고, 위협을 방지, 감지 및 수정하는 방법을 알아보십시오.
keywords: mdatp 평가, 평가, 랩, 시뮬레이션, windows 10, windows server 2019, 평가 랩
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365solution-evalutatemtp
ms.topic: article
ms.technology: mde
ms.openlocfilehash: ead616b7af3df05f4c0c5755ad779f0251555734
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51074583"
---
# <a name="microsoft-defender-for-endpoint-evaluation-lab"></a><span data-ttu-id="fe046-104">끝점용 Microsoft Defender 평가 랩</span><span class="sxs-lookup"><span data-stu-id="fe046-104">Microsoft Defender for Endpoint evaluation lab</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="fe046-105">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="fe046-105">**Applies to:**</span></span>
- [<span data-ttu-id="fe046-106">엔드포인트용 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="fe046-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)
- [<span data-ttu-id="fe046-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="fe046-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="fe046-108">끝점용 Microsoft Defender를 경험하고 싶나요?</span><span class="sxs-lookup"><span data-stu-id="fe046-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="fe046-109">무료 평가판에 등록합니다.</span><span class="sxs-lookup"><span data-stu-id="fe046-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-enablesiem-abovefoldlink)


<span data-ttu-id="fe046-110">포괄적인 보안 제품 평가를 수행하려면 포괄적인 공격 시뮬레이션을 실제로 수행하기 전에 번거로우는 환경 및 장치 구성을 요구하는 복잡한 프로세스가 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fe046-110">Conducting a comprehensive security product evaluation can be a complex process requiring cumbersome environment and device configuration before an end-to-end attack simulation can actually be done.</span></span> <span data-ttu-id="fe046-111">복잡성을 더하는 것은 평가 중에 시뮬레이션 활동, 경고 및 결과가 반영되는 위치를 추적해야 하는 과제입니다.</span><span class="sxs-lookup"><span data-stu-id="fe046-111">Adding to the complexity is the challenge of tracking where the simulation activities, alerts, and results are reflected during the evaluation.</span></span>

<span data-ttu-id="fe046-112">끝점용 Microsoft Defender 평가 랩은 플랫폼의 기능을 평가하고 시뮬레이션을 실행하고, 실행 중인 예방, 탐지 및 수정 기능을 보는 데 집중할 수 있도록 장치 및 환경 구성의 복잡한 문제를 없애기 위해 설계되었습니다.</span><span class="sxs-lookup"><span data-stu-id="fe046-112">The Microsoft Defender for Endpoint evaluation lab is designed to eliminate the complexities of device and environment configuration so that you can  focus on evaluating the capabilities of the platform, running simulations, and seeing the prevention, detection, and remediation features in action.</span></span>

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RE4qLUM]

<span data-ttu-id="fe046-113">간소화된 설정 환경을 사용하면 자체 테스트 시나리오 및 미리 만들어진 시뮬레이션을 실행하여 끝점용 Defender의 수행 방법을 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fe046-113">With the simplified set-up experience, you can focus on running your own test scenarios and the pre-made simulations to see how Defender for Endpoint performs.</span></span> 

<span data-ttu-id="fe046-114">자동화된 조사, 고급 헌팅 및 위협 분석과 같은 플랫폼의 강력한 기능에 대한 모든 권한을 가지게 되므로 Endpoint용 Defender가 제공하는 포괄적인 보호 스택을 테스트할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fe046-114">You'll have full access to the powerful capabilities of the platform such as automated investigations, advanced hunting, and threat analytics, allowing you to test the comprehensive protection stack that Defender for Endpoint offers.</span></span> 

<span data-ttu-id="fe046-115">Office 2019 Standard뿐만 아니라 최신 OS 버전 및 올바른 보안 구성 요소를 설치하도록 미리 구성된 Windows 10 또는 Windows Server 2019 장치를 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fe046-115">You can add Windows 10 or Windows Server 2019 devices that come pre-configured to have the latest OS versions and the right security components in place as well as Office 2019 Standard installed.</span></span>

<span data-ttu-id="fe046-116">위협 시뮬레이터를 설치할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fe046-116">You can also install threat simulators.</span></span> <span data-ttu-id="fe046-117">Endpoint용 Defender는 업계를 선도하는 위협 시뮬레이션 플랫폼과 파트너가 되어 포털을 떠나지 않고도 끝점용 Defender 기능을 테스트할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fe046-117">Defender for Endpoint has partnered with industry leading threat simulation platforms to help you test out the Defender for Endpoint capabilities without having to leave the portal.</span></span>

 <span data-ttu-id="fe046-118">원하는 시뮬레이터를 설치하고, 평가 랩 내에서 시나리오를 실행하고, 플랫폼의 기능을 즉시 확인하여 추가 비용도 무료로 모두 편리하게 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fe046-118">Install your preferred simulator, run scenarios within the evaluation lab, and instantly see how the platform performs - all conveniently available at no extra cost to you.</span></span> <span data-ttu-id="fe046-119">또한 시뮬레이션 카탈로그에서 액세스하고 실행할 수 있는 다양한 시뮬레이션에 편리하게 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fe046-119">You'll also have convenient access to wide array of simulations which you can access and run from the simulations catalog.</span></span>
    

## <a name="before-you-begin"></a><span data-ttu-id="fe046-120">시작하기 전에</span><span class="sxs-lookup"><span data-stu-id="fe046-120">Before you begin</span></span>
<span data-ttu-id="fe046-121">평가 랩에 액세스하려면 [](minimum-requirements.md#licensing-requirements) 라이선스 요구 사항을 충족하거나 끝점용 Microsoft Defender에 대한 평가판 액세스 권한이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="fe046-121">You'll need to fulfill the [licensing requirements](minimum-requirements.md#licensing-requirements) or have trial access to Microsoft Defender for Endpoint to access the evaluation lab.</span></span>

<span data-ttu-id="fe046-122">다음에 대한 **보안 설정** 관리 권한이 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="fe046-122">You must have **Manage security settings** permissions to:</span></span>
- <span data-ttu-id="fe046-123">랩 만들기</span><span class="sxs-lookup"><span data-stu-id="fe046-123">Create the lab</span></span>
- <span data-ttu-id="fe046-124">장치 만들기</span><span class="sxs-lookup"><span data-stu-id="fe046-124">Create devices</span></span>
- <span data-ttu-id="fe046-125">암호 다시 설정</span><span class="sxs-lookup"><span data-stu-id="fe046-125">Reset password</span></span>
- <span data-ttu-id="fe046-126">시뮬레이션 만들기</span><span class="sxs-lookup"><span data-stu-id="fe046-126">Create simulations</span></span> 
 
<span data-ttu-id="fe046-127">RBAC(역할 기반 액세스 제어)를 사용하도록 설정하고 하나 이상의 컴퓨터 그룹을 만든 경우 사용자는 모든 컴퓨터 그룹에 액세스할 수 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="fe046-127">If you enabled role-based access control (RBAC) and created at least a one machine group, users must have access to All machine groups.</span></span>

<span data-ttu-id="fe046-128">자세한 내용은 역할 만들기 [및 관리를 참조하세요.](user-roles.md)</span><span class="sxs-lookup"><span data-stu-id="fe046-128">For more information, see [Create and manage roles](user-roles.md).</span></span>

<span data-ttu-id="fe046-129">끝점용 Microsoft Defender를 경험하고 싶나요?</span><span class="sxs-lookup"><span data-stu-id="fe046-129">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="fe046-130">무료 평가판에 등록합니다.</span><span class="sxs-lookup"><span data-stu-id="fe046-130">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-main-abovefoldlink)


## <a name="get-started-with-the-lab"></a><span data-ttu-id="fe046-131">랩 시작</span><span class="sxs-lookup"><span data-stu-id="fe046-131">Get started with the lab</span></span>
<span data-ttu-id="fe046-132">메뉴에서 랩에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fe046-132">You can access the lab from the menu.</span></span> <span data-ttu-id="fe046-133">탐색 메뉴에서 평가판 및 자습서> **평가 랩 을 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="fe046-133">In the navigation menu, select **Evaluation and tutorials > Evaluation lab**.</span></span>

![메뉴의 평가 랩 이미지](images/evaluation-lab-menu.png)

>[!NOTE]
>- <span data-ttu-id="fe046-135">각 환경은 제한된 테스트 장치 집합으로 프로비전됩니다.</span><span class="sxs-lookup"><span data-stu-id="fe046-135">Each environment is provisioned with a limited set of test devices.</span></span>
>- <span data-ttu-id="fe046-136">선택한 환경 구조의 유형에 따라 정품 인증일로부터 지정된 시간 동안 디바이스를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fe046-136">Depending the type of environment structure you select, devices will be available for the specified number of hours from the day of activation.</span></span>
>- <span data-ttu-id="fe046-137">프로비전된 장치를 사용한 경우 새 장치가 제공되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="fe046-137">When you've used up the provisioned devices, no new devices are provided.</span></span> <span data-ttu-id="fe046-138">삭제된 장치는 사용 가능한 테스트 장치 수를 새로 고치지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="fe046-138">A deleted device does not refresh the available test device count.</span></span>
>- <span data-ttu-id="fe046-139">제한된 리소스가 제공된 경우 장치를 신중하게 사용하는 것이 가장 쉽습니다.</span><span class="sxs-lookup"><span data-stu-id="fe046-139">Given the limited resources, it’s advisable to use the devices carefully.</span></span>

<span data-ttu-id="fe046-140">이미 랩이 있나요?</span><span class="sxs-lookup"><span data-stu-id="fe046-140">Already have a lab?</span></span> <span data-ttu-id="fe046-141">새 위협 시뮬레이터를 사용하도록 설정하고 활성 장치를 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="fe046-141">Make sure to enable the new threat simulators and have active devices.</span></span>

## <a name="setup-the-evaluation-lab"></a><span data-ttu-id="fe046-142">평가 랩 설정</span><span class="sxs-lookup"><span data-stu-id="fe046-142">Setup the evaluation lab</span></span>

1. <span data-ttu-id="fe046-143">탐색 창에서 평가 및 자습서 **평가** 랩  >  을 선택한 다음 설치 **랩 을 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="fe046-143">In the navigation pane, select **Evaluation and tutorials** > **Evaluation lab**, then select **Setup lab**.</span></span>

    ![평가 랩 시작 페이지의 이미지](images/evaluation-lab-setup.png)

2. <span data-ttu-id="fe046-145">평가 요구에 따라 더 긴 기간 동안 더 적은 장치 또는 더 짧은 기간 동안 더 많은 장치를 사용하여 환경을 설정하기로 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fe046-145">Depending on your evaluation needs, you can choose to setup an environment with fewer devices for a longer period or more devices for a shorter period.</span></span> <span data-ttu-id="fe046-146">기본 설정 랩 구성을 선택한 후 다음 을 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="fe046-146">Select your preferred lab configuration then select **Next**.</span></span>

    ![랩 구성 옵션의 이미지](images/lab-creation-page.png) 


3. <span data-ttu-id="fe046-148">(선택 사항) 랩에 위협 시뮬레이터를 설치하도록 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fe046-148">(Optional) You can choose to install threat simulators in the lab.</span></span> 

    ![설치 시뮬레이터 에이전트의 이미지](images/install-agent.png)

    >[!IMPORTANT]
    ><span data-ttu-id="fe046-150">먼저 약관 및 정보 공유 설명에 동의하고 동의해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="fe046-150">You'll first need to accept and provide consent to the terms and information sharing statements.</span></span> 

4. <span data-ttu-id="fe046-151">사용할 위협 시뮬레이션 에이전트를 선택하고 세부 정보를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="fe046-151">Select the threat simulation agent you'd like to use and enter your details.</span></span> <span data-ttu-id="fe046-152">나중에 위협 시뮬레이터를 설치하도록 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fe046-152">You can also choose to install threat simulators at a later time.</span></span> <span data-ttu-id="fe046-153">랩 설치 중에 위협 시뮬레이션 에이전트를 설치하도록 선택한 경우 추가한 장치에 위협 시뮬레이션 에이전트를 편리하게 설치하는 이점을 즐길 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fe046-153">If you choose to install threat simulation agents during the lab setup, you'll enjoy the benefit of having them conveniently installed on the devices you add.</span></span>  
    
    ![요약 페이지 이미지](images/lab-setup-summary.png)

5.  <span data-ttu-id="fe046-155">요약을 검토하고 설치 **랩을 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="fe046-155">Review the summary and select **Setup lab**.</span></span>  

<span data-ttu-id="fe046-156">랩 설정 프로세스가 완료되면 디바이스를 추가하고 시뮬레이션을 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fe046-156">After the lab setup process is complete, you can add devices and run simulations.</span></span> 


## <a name="add-devices"></a><span data-ttu-id="fe046-157">장치 추가</span><span class="sxs-lookup"><span data-stu-id="fe046-157">Add devices</span></span>
<span data-ttu-id="fe046-158">환경에 장치를 추가하면 끝점용 Defender가 연결 세부 정보가 있는 잘 구성된 장치를 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="fe046-158">When you add a device to your environment, Defender for Endpoint sets up a well-configured device with connection details.</span></span> <span data-ttu-id="fe046-159">Windows 10 또는 Windows Server 2019 장치를 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fe046-159">You can add Windows 10 or Windows Server 2019 devices.</span></span>

<span data-ttu-id="fe046-160">장치는 최신 버전의 OS 및 Office 2019 Standard 및 Java, Python 및 SysIntenals와 같은 기타 앱으로 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="fe046-160">The device will be configured with the most up-to-date version of the OS and Office 2019 Standard as well as other apps such as Java, Python, and SysIntenals.</span></span> 

   >[!TIP]
   > <span data-ttu-id="fe046-161">랩에 더 많은 디바이스가 필요하세요?</span><span class="sxs-lookup"><span data-stu-id="fe046-161">Need more devices in your lab?</span></span> <span data-ttu-id="fe046-162">지원 티켓을 제출하여 요청이 끝점용 Defender 팀에서 검토하게 합니다.</span><span class="sxs-lookup"><span data-stu-id="fe046-162">Submit a support ticket to have your request reviewed by the Defender for Endpoint team.</span></span> 

<span data-ttu-id="fe046-163">랩 설정 중에 위협 시뮬레이터를 추가하기로 선택한 경우 모든 장치에 추가하는 장치에 위협 시뮬레이터 에이전트가 설치됩니다.</span><span class="sxs-lookup"><span data-stu-id="fe046-163">If you chose to add a threat simulator during the lab setup, all devices will have the threat simulator agent installed in the devices that you add.</span></span>

<span data-ttu-id="fe046-164">장치가 권장되는 Windows 보안 구성 요소를 켜고 감사 모드로 켜져 있는 테넌트에 자동으로 온보드됩니다. 즉, 사용자 쪽에서 아무 노력도 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="fe046-164">The device will automatically be onboarded to your tenant with the recommended Windows security components turned on and in audit mode - with no effort on your side.</span></span> 

<span data-ttu-id="fe046-165">테스트 장치에 미리 구성된 보안 구성 요소는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="fe046-165">The following security components are pre-configured in the test devices:</span></span>

- [<span data-ttu-id="fe046-166">공격 표면 감소</span><span class="sxs-lookup"><span data-stu-id="fe046-166">Attack surface reduction</span></span>](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-exploit-guard/attack-surface-reduction-exploit-guard)
- [<span data-ttu-id="fe046-167">차단 시 차단</span><span class="sxs-lookup"><span data-stu-id="fe046-167">Block at first sight</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/configure-block-at-first-sight-microsoft-defender-antivirus)
- [<span data-ttu-id="fe046-168">제어된 폴더 액세스</span><span class="sxs-lookup"><span data-stu-id="fe046-168">Controlled folder access</span></span>](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-exploit-guard/controlled-folders-exploit-guard)
- [<span data-ttu-id="fe046-169">Exploit Protection</span><span class="sxs-lookup"><span data-stu-id="fe046-169">Exploit protection</span></span>](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-exploit-guard/enable-exploit-protection)
- [<span data-ttu-id="fe046-170">네트워크 보호</span><span class="sxs-lookup"><span data-stu-id="fe046-170">Network protection</span></span>](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-exploit-guard/network-protection-exploit-guard)
- [<span data-ttu-id="fe046-171">잠재적으로 원치 않는 응용 프로그램 검색</span><span class="sxs-lookup"><span data-stu-id="fe046-171">Potentially unwanted application detection</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/detect-block-potentially-unwanted-apps-microsoft-defender-antivirus)
- [<span data-ttu-id="fe046-172">클라우드 제공 보호</span><span class="sxs-lookup"><span data-stu-id="fe046-172">Cloud-delivered protection</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/utilize-microsoft-cloud-protection-microsoft-defender-antivirus)
- [<span data-ttu-id="fe046-173">Microsoft Defender SmartScreen</span><span class="sxs-lookup"><span data-stu-id="fe046-173">Microsoft Defender SmartScreen</span></span>](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-smartscreen/windows-defender-smartscreen-overview)

>[!NOTE]
> <span data-ttu-id="fe046-174">Microsoft Defender 바이러스 백신이 설정됩니다(감사 모드 아미타임).</span><span class="sxs-lookup"><span data-stu-id="fe046-174">Microsoft Defender Antivirus will be on (not in audit mode).</span></span> <span data-ttu-id="fe046-175">Microsoft Defender 바이러스 백신이 시뮬레이션을 실행하지 못하게 차단하는 경우 Windows 보안을 통해 디바이스에서 실시간 보호를 해제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fe046-175">If Microsoft Defender Antivirus blocks you from running your simulation, you can turn off real-time protection on the device through Windows Security.</span></span> <span data-ttu-id="fe046-176">자세한 내용은 [Always-On 보호 구성을 참조하세요.](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/configure-real-time-protection-microsoft-defender-antivirus)</span><span class="sxs-lookup"><span data-stu-id="fe046-176">For more information, see [Configure always-on protection](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/configure-real-time-protection-microsoft-defender-antivirus).</span></span>

<span data-ttu-id="fe046-177">자동화된 조사 설정은 테넌트 설정에 따라 달라집니다.</span><span class="sxs-lookup"><span data-stu-id="fe046-177">Automated investigation settings will be dependent on tenant settings.</span></span> <span data-ttu-id="fe046-178">기본적으로 반자동으로 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="fe046-178">It will be configured to be semi-automated by default.</span></span> <span data-ttu-id="fe046-179">자세한 내용은 자동화된 조사 [개요를 참조하세요.](automated-investigations.md)</span><span class="sxs-lookup"><span data-stu-id="fe046-179">For more information, see [Overview of Automated investigations](automated-investigations.md).</span></span>

>[!NOTE]
><span data-ttu-id="fe046-180">테스트 장치에 대한 연결은 RDP를 사용하여 수행됩니다.</span><span class="sxs-lookup"><span data-stu-id="fe046-180">The connection to the test devices is done using RDP.</span></span> <span data-ttu-id="fe046-181">방화벽 설정에서 RDP 연결을 허용하는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="fe046-181">Make sure that your firewall settings allow RDP connections.</span></span>

1. <span data-ttu-id="fe046-182">대시보드에서 장치 **추가 를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="fe046-182">From the dashboard, select **Add device**.</span></span> 

2. <span data-ttu-id="fe046-183">추가할 디바이스 유형을 선택하십시오.</span><span class="sxs-lookup"><span data-stu-id="fe046-183">Choose the type of device to add.</span></span> <span data-ttu-id="fe046-184">Windows 10 또는 Windows Server 2019를 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fe046-184">You can choose to add Windows 10 or Windows Server 2019.</span></span>

    ![디바이스 옵션을 사용하여 랩 설정의 이미지](images/add-machine-options.png)


    >[!NOTE]
    ><span data-ttu-id="fe046-186">장치 만들기 프로세스에 문제가 있는 경우 알림을 보게 되고 새 요청을 제출해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="fe046-186">If something goes wrong with the device creation process, you'll be notified and you'll need to submit a new request.</span></span> <span data-ttu-id="fe046-187">장치 만들기가 실패하면 전체 허용 할당량에 대해 계산되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="fe046-187">If the device creation fails, it will not be counted against the overall allowed quota.</span></span> 

3. <span data-ttu-id="fe046-188">연결 세부 정보가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="fe046-188">The connection details are displayed.</span></span> <span data-ttu-id="fe046-189">**디바이스의** 암호를 저장하려면 복사를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="fe046-189">Select **Copy** to save the password for the device.</span></span>

    >[!NOTE]
    ><span data-ttu-id="fe046-190">암호는 한 번만 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="fe046-190">The password is only displayed once.</span></span> <span data-ttu-id="fe046-191">나중에 사용하기 위해 저장해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="fe046-191">Be sure to save it for later use.</span></span>

    ![연결 세부 정보를 사용하여 추가된 디바이스의 이미지](images/add-machine-eval-lab.png)

4. <span data-ttu-id="fe046-193">디바이스 설정이 시작됩니다.</span><span class="sxs-lookup"><span data-stu-id="fe046-193">Device set up begins.</span></span> <span data-ttu-id="fe046-194">약 30분 정도 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fe046-194">This can take up to approximately 30 minutes.</span></span> 

5. <span data-ttu-id="fe046-195">장치 탭을 선택하여 테스트 장치의 상태, 위험 및 노출 수준, 시뮬레이터 설치 상태를 볼 **수** 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fe046-195">See the status of test devices, the risk and exposure levels, and the status of simulator installations by selecting the **Devices** tab.</span></span> 

    ![장치 탭의 이미지](images/machines-tab.png)
    

    >[!TIP]
    ><span data-ttu-id="fe046-197">시뮬레이터 **상태** 열에서 정보 아이콘 위에 마우스를 여 에이전트의 설치 상태를 알 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fe046-197">In the **Simulator status** column, you can hover over the information icon to know the installation status of an agent.</span></span>



## <a name="simulate-attack-scenarios"></a><span data-ttu-id="fe046-198">공격 시나리오 시뮬레이트</span><span class="sxs-lookup"><span data-stu-id="fe046-198">Simulate attack scenarios</span></span>
<span data-ttu-id="fe046-199">테스트 장치를 사용하여 연결하여 자체 공격 시뮬레이션을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="fe046-199">Use the test devices to run your own attack simulations by connecting to them.</span></span> 

<span data-ttu-id="fe046-200">다음을 사용하여 공격 시나리오를 시뮬레이트할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fe046-200">You can simulate attack scenarios using:</span></span>
- <span data-ttu-id="fe046-201">["직접" 공격 시나리오](https://securitycenter.windows.com/tutorials)</span><span class="sxs-lookup"><span data-stu-id="fe046-201">The ["Do It Yourself" attack scenarios](https://securitycenter.windows.com/tutorials)</span></span>
- <span data-ttu-id="fe046-202">위협 시뮬레이터</span><span class="sxs-lookup"><span data-stu-id="fe046-202">Threat simulators</span></span>

<span data-ttu-id="fe046-203">고급 [헌팅을](advanced-hunting-query-language.md) 사용하여 데이터 및 [위협](threat-analytics.md) 분석을 쿼리하여 새로운 위협에 대한 보고서를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fe046-203">You can also use [Advanced hunting](advanced-hunting-query-language.md) to query data and [Threat analytics](threat-analytics.md) to view reports about emerging threats.</span></span>

### <a name="do-it-yourself-attack-scenarios"></a><span data-ttu-id="fe046-204">직접 공격 시나리오</span><span class="sxs-lookup"><span data-stu-id="fe046-204">Do-it-yourself attack scenarios</span></span>
<span data-ttu-id="fe046-205">미리 만든 시뮬레이션을 찾고 있는 경우 ["직접 실행"](https://securitycenter.windows.com/tutorials)공격 시나리오를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fe046-205">If you are looking for a pre-made simulation, you can use our ["Do It Yourself" attack scenarios](https://securitycenter.windows.com/tutorials).</span></span> <span data-ttu-id="fe046-206">이러한 스크립트는 안전하고 문서화되어 있으며 사용하기 쉽습니다.</span><span class="sxs-lookup"><span data-stu-id="fe046-206">These scripts are safe, documented, and easy to use.</span></span> <span data-ttu-id="fe046-207">이러한 시나리오는 끝점 기능에 대한 Defender를 반영하고 조사 환경을 진행합니다.</span><span class="sxs-lookup"><span data-stu-id="fe046-207">These scenarios will reflect Defender for Endpoint capabilities and walk you through investigation experience.</span></span>


>[!NOTE]
><span data-ttu-id="fe046-208">테스트 장치에 대한 연결은 RDP를 사용하여 수행됩니다.</span><span class="sxs-lookup"><span data-stu-id="fe046-208">The connection to the test devices is done using RDP.</span></span> <span data-ttu-id="fe046-209">방화벽 설정에서 RDP 연결을 허용하는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="fe046-209">Make sure that your firewall settings allow RDP connections.</span></span>

1. <span data-ttu-id="fe046-210">장치에 연결하고 연결을 선택하여 공격 시뮬레이션을 **실행합니다.**</span><span class="sxs-lookup"><span data-stu-id="fe046-210">Connect to your device and run an attack simulation by selecting **Connect**.</span></span> 

    ![테스트 장치에 대한 연결 단추의 이미지](images/test-machine-table.png)

2. <span data-ttu-id="fe046-212">RDP 파일을 저장하고 연결을 선택하여 **실행합니다.**</span><span class="sxs-lookup"><span data-stu-id="fe046-212">Save the RDP file and launch it by selecting **Connect**.</span></span>

    ![원격 데스크톱 연결의 이미지](images/remote-connection.png)

    >[!NOTE]
    ><span data-ttu-id="fe046-214">초기 설정 중에 암호 복사본을 저장하지 않은 경우 메뉴에서 암호 다시  설정을 선택하여 암호를 다시 설정할 수 있습니다. 암호 재설정 ![ 이미지](images/reset-password-test-machine.png)</span><span class="sxs-lookup"><span data-stu-id="fe046-214">If you don't have a copy of the password saved during the initial setup, you can reset the password by selecting **Reset password** from the menu: ![Image of reset password](images/reset-password-test-machine.png)</span></span><br>
    > <span data-ttu-id="fe046-215">디바이스의 상태가 "암호 재설정 실행"으로 변경되면 몇 분 후에 새 암호가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="fe046-215">The device will change it’s state to “Executing password reset", then you’ll be presented with your new password in a few minutes.</span></span>

3. <span data-ttu-id="fe046-216">디바이스를 만들 때 표시된 암호를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="fe046-216">Enter the password that was displayed during the device creation step.</span></span> 

   ![자격 증명을 입력할 창의 이미지](images/enter-password.png)

4. <span data-ttu-id="fe046-218">장치에서 Do-it-yourself 공격 시뮬레이션을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="fe046-218">Run Do-it-yourself attack simulations on the device.</span></span> 


### <a name="threat-simulator-scenarios"></a><span data-ttu-id="fe046-219">위협 시뮬레이터 시나리오</span><span class="sxs-lookup"><span data-stu-id="fe046-219">Threat simulator scenarios</span></span>
<span data-ttu-id="fe046-220">랩 설정 중에 지원되는 위협 시뮬레이터를 설치하도록 선택한 경우 평가 랩 디바이스에서 기본 제공 시뮬레이션을 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fe046-220">If you chose to install any of the supported threat simulators during the lab setup, you can run the built-in simulations on the evaluation lab devices.</span></span> 


<span data-ttu-id="fe046-221">타사 플랫폼을 사용하여 위협 시뮬레이션을 실행하는 것은 테스트 환경의 범위 내에서 끝점 기능에 대한 Microsoft Defender를 평가하는 좋은 방법입니다.</span><span class="sxs-lookup"><span data-stu-id="fe046-221">Running threat simulations using third-party platforms is a good way to evaluate Microsoft Defender for Endpoint capabilities within the confines of a lab environment.</span></span>

>[!NOTE]
><span data-ttu-id="fe046-222">시뮬레이션을 실행하기 전에 다음 요구 사항을 충족하는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="fe046-222">Before you can run simulations, ensure the following requirements are met:</span></span>
>- <span data-ttu-id="fe046-223">디바이스를 평가 랩에 추가해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="fe046-223">Devices must be added to the evaluation lab</span></span>
>- <span data-ttu-id="fe046-224">위협 시뮬레이터를 평가 랩에 설치해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="fe046-224">Threat simulators must be installed in the evaluation lab</span></span>

1. <span data-ttu-id="fe046-225">포털에서 시뮬레이션 **만들기를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="fe046-225">From the portal select **Create simulation**.</span></span>

2. <span data-ttu-id="fe046-226">위협 시뮬레이터를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="fe046-226">Select a threat simulator.</span></span>

    ![위협 시뮬레이터 선택 이미지](images/select-simulator.png)

3. <span data-ttu-id="fe046-228">시뮬레이션을 선택하거나 시뮬레이션 갤러리를 살펴보고 사용 가능한 시뮬레이션을 탐색합니다.</span><span class="sxs-lookup"><span data-stu-id="fe046-228">Choose a simulation or look through the simulation gallery to browse through the available simulations.</span></span> 

    <span data-ttu-id="fe046-229">시뮬레이션 갤러리는 다음에서 얻을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fe046-229">You can get to the simulation gallery from:</span></span>
    - <span data-ttu-id="fe046-230">시뮬레이션 개요 타일의 주 평가 **대시보드 또는**</span><span class="sxs-lookup"><span data-stu-id="fe046-230">The main evaluation dashboard in the **Simulations overview** tile or</span></span>
    - <span data-ttu-id="fe046-231">탐색 창 평가 및 자습서 시뮬레이션을 탐색하여  >  **자습서를 &** 시뮬레이션 **카탈로그를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="fe046-231">By navigating from the navigation pane **Evaluation and tutorials** > **Simulation & tutorials**, then select **Simulations catalog**.</span></span>

4. <span data-ttu-id="fe046-232">시뮬레이션을 실행할 디바이스를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="fe046-232">Select the devices where you'd like to run the simulation on.</span></span>

5. <span data-ttu-id="fe046-233">시뮬레이션 **만들기를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="fe046-233">Select **Create simulation**.</span></span>

6. <span data-ttu-id="fe046-234">시뮬레이션 탭을 선택하여 시뮬레이션 **진행률을 니다.** 시뮬레이션 상태, 활성 경고 및 기타 세부 정보를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fe046-234">View the progress of a simulation by selecting the **Simulations** tab. View the simulation state, active alerts, and other details.</span></span> 

    ![시뮬레이션 탭의 이미지](images/simulations-tab.png)
    
<span data-ttu-id="fe046-236">시뮬레이션을 실행한 후 랩 진행률 표시줄을 살펴보고 자동화된 조사 및 수정을 트리거한 **Endpoint용 Microsoft Defender를** 살펴보는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="fe046-236">After running your simulations, we encourage you to walk through the lab progress bar and explore **Microsoft Defender for Endpoint triggered an automated investigation and remediation**.</span></span> <span data-ttu-id="fe046-237">기능에서 수집 및 분석한 증거를 확인해 보아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="fe046-237">Check out the evidence collected and analyzed by the feature.</span></span>

<span data-ttu-id="fe046-238">풍부한 쿼리 언어 및 원시 원격 분석을 사용하여 고급 헌팅을 통해 공격 증거를 헌팅하고 위협 분석에 문서화되어 있는 전 세계 위협을 확인해보십시오.</span><span class="sxs-lookup"><span data-stu-id="fe046-238">Hunt for attack evidence through advanced hunting by using the rich query language and raw telemetry and check out some world-wide threats documented in Threat analytics.</span></span>


## <a name="simulation-gallery"></a><span data-ttu-id="fe046-239">시뮬레이션 갤러리</span><span class="sxs-lookup"><span data-stu-id="fe046-239">Simulation gallery</span></span>
<span data-ttu-id="fe046-240">끝점용 Microsoft Defender는 다양한 위협 시뮬레이션 플랫폼과 파트너가 되어 포털 내에서 바로 플랫폼의 기능을 테스트할 수 있는 편리한 액세스 권한을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="fe046-240">Microsoft Defender for Endpoint has partnered with various threat simulation platforms to give you convenient access to test the capabilities of the platform right from the within the portal.</span></span> 

<span data-ttu-id="fe046-241">메뉴에서 시뮬레이션 및 자습서 시뮬레이션 카탈로그로 진행하여 사용 가능한 모든  >   시뮬레이션을 시청합니다.</span><span class="sxs-lookup"><span data-stu-id="fe046-241">View all the available simulations by going to  **Simulations and tutorials** > **Simulations catalog**  from the menu.</span></span> 

<span data-ttu-id="fe046-242">지원되는 타사 위협 시뮬레이션 에이전트 목록이 나열되어 있으며, 자세한 설명과 함께 특정 유형의 시뮬레이션이 카탈로그에 제공됩니다.</span><span class="sxs-lookup"><span data-stu-id="fe046-242">A list of supported third-party threat simulation agents are listed, and specific types of simulations along with detailed descriptions are provided on the catalog.</span></span> 

<span data-ttu-id="fe046-243">카탈로그에서 사용 가능한 시뮬레이션을 편리하게 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fe046-243">You can conveniently run any available simulation right from the catalog.</span></span>  


![시뮬레이션 카탈로그 이미지](images/simulations-catalog.png)

<span data-ttu-id="fe046-245">각 시뮬레이션에는 공격 시나리오에 대한 자세한 설명과 사용되는 MITRE 공격 기술 및 실행한 샘플 고급 헌팅 쿼리와 같은 참조가 함께 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="fe046-245">Each simulation comes with an in-depth description of the attack scenario and references such as the MITRE attack techniques used and sample Advanced hunting queries you run.</span></span>

<span data-ttu-id="fe046-246">**예:** 
 ![ 시뮬레이션 설명 세부 정보의 이미지1](images/simulation-details-aiq.png)</span><span class="sxs-lookup"><span data-stu-id="fe046-246">**Examples:**
![Image of simulation description details1](images/simulation-details-aiq.png)</span></span>


![시뮬레이션 설명 세부 정보의 이미지2](images/simulation-details-sb.png)


## <a name="evaluation-report"></a><span data-ttu-id="fe046-248">평가 보고서</span><span class="sxs-lookup"><span data-stu-id="fe046-248">Evaluation report</span></span>
<span data-ttu-id="fe046-249">랩 보고서에는 디바이스에서 수행된 시뮬레이션의 결과가 요약됩니다.</span><span class="sxs-lookup"><span data-stu-id="fe046-249">The lab reports summarize the results of the simulations conducted on the devices.</span></span>

![평가 보고서의 이미지](images/eval-report.png)

<span data-ttu-id="fe046-251">다음을 빠르게 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fe046-251">At a glance, you'll quickly be able to see:</span></span>
- <span data-ttu-id="fe046-252">트리거된 인시던트</span><span class="sxs-lookup"><span data-stu-id="fe046-252">Incidents that were triggered</span></span>
- <span data-ttu-id="fe046-253">생성된 경고</span><span class="sxs-lookup"><span data-stu-id="fe046-253">Generated alerts</span></span>
- <span data-ttu-id="fe046-254">노출 수준에 대한 평가</span><span class="sxs-lookup"><span data-stu-id="fe046-254">Assessments on exposure level</span></span> 
- <span data-ttu-id="fe046-255">관찰된 위협 범주</span><span class="sxs-lookup"><span data-stu-id="fe046-255">Threat categories observed</span></span>
- <span data-ttu-id="fe046-256">검색 원본</span><span class="sxs-lookup"><span data-stu-id="fe046-256">Detection sources</span></span>
- <span data-ttu-id="fe046-257">자동화된 조사</span><span class="sxs-lookup"><span data-stu-id="fe046-257">Automated investigations</span></span>


## <a name="provide-feedback"></a><span data-ttu-id="fe046-258">피드백 제공</span><span class="sxs-lookup"><span data-stu-id="fe046-258">Provide feedback</span></span>
<span data-ttu-id="fe046-259">사용자 의견은 고급 공격으로부터 환경을 보호하는 데 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="fe046-259">Your feedback helps us get better in protecting your environment from advanced attacks.</span></span> <span data-ttu-id="fe046-260">제품 기능 및 평가 결과에서 경험과 노출을 공유합니다.</span><span class="sxs-lookup"><span data-stu-id="fe046-260">Share your experience and impressions from product capabilities and evaluation results.</span></span>

<span data-ttu-id="fe046-261">피드백 제공 을 선택하여 의견을 **알려주세요.**</span><span class="sxs-lookup"><span data-stu-id="fe046-261">Let us know what you think, by selecting **Provide feedback**.</span></span>

![피드백 제공 이미지](images/send-us-feedback-eval-lab.png)
