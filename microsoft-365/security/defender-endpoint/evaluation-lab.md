---
title: 끝점용 Microsoft Defender 평가 랩
description: 끝점용 Microsoft Defender 기능에 대해 알아보고, 공격 시뮬레이션을 실행하고, 위협을 방지, 감지 및 수정하는 방법을 알아보십시오.
keywords: 끝점에 대한 Microsoft Defender 평가, 평가, 랩, 시뮬레이션, windows 10, windows server 2019, 평가 랩
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
ms.openlocfilehash: f6ef1d3dbc111e5d10bf4d3c42dfd08e5e9d63e3
ms.sourcegitcommit: e8f5d88f0fe54620308d3bec05263568f9da2931
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/03/2021
ms.locfileid: "52730630"
---
# <a name="microsoft-defender-for-endpoint-evaluation-lab"></a><span data-ttu-id="9afa8-104">끝점용 Microsoft Defender 평가 랩</span><span class="sxs-lookup"><span data-stu-id="9afa8-104">Microsoft Defender for Endpoint evaluation lab</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="9afa8-105">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="9afa8-105">**Applies to:**</span></span>
- [<span data-ttu-id="9afa8-106">엔드포인트용 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="9afa8-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)
- [<span data-ttu-id="9afa8-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="9afa8-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="9afa8-108">끝점용 Microsoft Defender를 경험하고 싶나요?</span><span class="sxs-lookup"><span data-stu-id="9afa8-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="9afa8-109">무료 평가판에 등록합니다.</span><span class="sxs-lookup"><span data-stu-id="9afa8-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-enablesiem-abovefoldlink)


<span data-ttu-id="9afa8-110">포괄적인 보안 제품 평가를 수행하려면 포괄적인 공격 시뮬레이션을 실제로 수행하기 전에 번거로우는 환경 및 장치 구성을 요구하는 복잡한 프로세스가 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9afa8-110">Conducting a comprehensive security product evaluation can be a complex process requiring cumbersome environment and device configuration before an end-to-end attack simulation can actually be done.</span></span> <span data-ttu-id="9afa8-111">복잡성을 더하는 것은 평가 중에 시뮬레이션 활동, 경고 및 결과가 반영되는 위치를 추적해야 하는 과제입니다.</span><span class="sxs-lookup"><span data-stu-id="9afa8-111">Adding to the complexity is the challenge of tracking where the simulation activities, alerts, and results are reflected during the evaluation.</span></span>

<span data-ttu-id="9afa8-112">끝점용 Microsoft Defender 평가 랩은 플랫폼의 기능을 평가하고 시뮬레이션을 실행하고, 실행 중인 예방, 탐지 및 수정 기능을 보는 데 집중할 수 있도록 장치 및 환경 구성의 복잡한 문제를 없애기 위해 설계되었습니다.</span><span class="sxs-lookup"><span data-stu-id="9afa8-112">The Microsoft Defender for Endpoint evaluation lab is designed to eliminate the complexities of device and environment configuration so that you can  focus on evaluating the capabilities of the platform, running simulations, and seeing the prevention, detection, and remediation features in action.</span></span>

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RE4qLUM]

<span data-ttu-id="9afa8-113">간소화된 설정 환경을 사용하면 자체 테스트 시나리오 및 미리 만들어진 시뮬레이션을 실행하여 끝점용 Defender의 수행 방법을 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9afa8-113">With the simplified set-up experience, you can focus on running your own test scenarios and the pre-made simulations to see how Defender for Endpoint performs.</span></span> 

<span data-ttu-id="9afa8-114">자동화된 조사, 고급 헌팅 및 위협 분석과 같은 플랫폼의 강력한 기능에 대한 모든 권한을 가지게 되므로 Endpoint용 Defender가 제공하는 포괄적인 보호 스택을 테스트할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9afa8-114">You'll have full access to the powerful capabilities of the platform such as automated investigations, advanced hunting, and threat analytics, allowing you to test the comprehensive protection stack that Defender for Endpoint offers.</span></span> 

<span data-ttu-id="9afa8-115">최신 OS 버전과 올바른 보안 구성 요소를 설치하고 Office 2019 Standard를 설치하도록 미리 구성된 Windows 10 또는 Windows Server 2019 장치를 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9afa8-115">You can add Windows 10 or Windows Server 2019 devices that come pre-configured to have the latest OS versions and the right security components in place as well as Office 2019 Standard installed.</span></span>

<span data-ttu-id="9afa8-116">위협 시뮬레이터를 설치할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9afa8-116">You can also install threat simulators.</span></span> <span data-ttu-id="9afa8-117">Endpoint용 Defender는 업계를 선도하는 위협 시뮬레이션 플랫폼과 파트너가 되어 포털을 떠나지 않고도 끝점용 Defender 기능을 테스트할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9afa8-117">Defender for Endpoint has partnered with industry leading threat simulation platforms to help you test out the Defender for Endpoint capabilities without having to leave the portal.</span></span>

 <span data-ttu-id="9afa8-118">원하는 시뮬레이터를 설치하고, 평가 랩 내에서 시나리오를 실행하고, 플랫폼의 기능을 즉시 확인하여 추가 비용도 무료로 모두 편리하게 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9afa8-118">Install your preferred simulator, run scenarios within the evaluation lab, and instantly see how the platform performs - all conveniently available at no extra cost to you.</span></span> <span data-ttu-id="9afa8-119">또한 시뮬레이션 카탈로그에서 액세스하고 실행할 수 있는 다양한 시뮬레이션에 편리하게 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9afa8-119">You'll also have convenient access to wide array of simulations which you can access and run from the simulations catalog.</span></span>
    

## <a name="before-you-begin"></a><span data-ttu-id="9afa8-120">시작하기 전에</span><span class="sxs-lookup"><span data-stu-id="9afa8-120">Before you begin</span></span>
<span data-ttu-id="9afa8-121">평가 랩에 액세스하려면 [](minimum-requirements.md#licensing-requirements) 라이선스 요구 사항을 충족하거나 끝점용 Microsoft Defender에 대한 평가판 액세스 권한이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="9afa8-121">You'll need to fulfill the [licensing requirements](minimum-requirements.md#licensing-requirements) or have trial access to Microsoft Defender for Endpoint to access the evaluation lab.</span></span>

<span data-ttu-id="9afa8-122">다음에 대한 **보안 설정** 관리 권한이 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9afa8-122">You must have **Manage security settings** permissions to:</span></span>
- <span data-ttu-id="9afa8-123">랩 만들기</span><span class="sxs-lookup"><span data-stu-id="9afa8-123">Create the lab</span></span>
- <span data-ttu-id="9afa8-124">장치 만들기</span><span class="sxs-lookup"><span data-stu-id="9afa8-124">Create devices</span></span>
- <span data-ttu-id="9afa8-125">암호 다시 설정</span><span class="sxs-lookup"><span data-stu-id="9afa8-125">Reset password</span></span>
- <span data-ttu-id="9afa8-126">시뮬레이션 만들기</span><span class="sxs-lookup"><span data-stu-id="9afa8-126">Create simulations</span></span> 
 
<span data-ttu-id="9afa8-127">RBAC(역할 기반 액세스 제어)를 사용하도록 설정하고 하나 이상의 컴퓨터 그룹을 만든 경우 사용자는 모든 컴퓨터 그룹에 액세스할 수 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9afa8-127">If you enabled role-based access control (RBAC) and created at least a one machine group, users must have access to All machine groups.</span></span>

<span data-ttu-id="9afa8-128">자세한 내용은 역할 만들기 [및 관리를 참조하세요.](user-roles.md)</span><span class="sxs-lookup"><span data-stu-id="9afa8-128">For more information, see [Create and manage roles](user-roles.md).</span></span>

<span data-ttu-id="9afa8-129">끝점용 Microsoft Defender를 경험하고 싶나요?</span><span class="sxs-lookup"><span data-stu-id="9afa8-129">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="9afa8-130">무료 평가판에 등록합니다.</span><span class="sxs-lookup"><span data-stu-id="9afa8-130">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-main-abovefoldlink)


## <a name="get-started-with-the-lab"></a><span data-ttu-id="9afa8-131">랩 시작</span><span class="sxs-lookup"><span data-stu-id="9afa8-131">Get started with the lab</span></span>
<span data-ttu-id="9afa8-132">메뉴에서 랩에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9afa8-132">You can access the lab from the menu.</span></span> <span data-ttu-id="9afa8-133">탐색 메뉴에서 평가판 및 자습서> **평가 랩 을 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="9afa8-133">In the navigation menu, select **Evaluation and tutorials > Evaluation lab**.</span></span>

![메뉴의 평가 랩 이미지](images/evaluation-lab-menu.png)

>[!NOTE]
>- <span data-ttu-id="9afa8-135">선택한 환경 구조의 유형에 따라 정품 인증일로부터 지정된 시간 동안 디바이스를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9afa8-135">Depending the type of environment structure you select, devices will be available for the specified number of hours from the day of activation.</span></span>
>- <span data-ttu-id="9afa8-136">각 환경은 제한된 테스트 장치 집합으로 프로비전됩니다.</span><span class="sxs-lookup"><span data-stu-id="9afa8-136">Each environment is provisioned with a limited set of test devices.</span></span> <span data-ttu-id="9afa8-137">프로비전된 장치를 사용한 후 삭제한 경우 더 많은 디바이스를 요청할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9afa8-137">When you've used up the provisioned devices and have deleted them, you can request for more devices.</span></span> 
>- <span data-ttu-id="9afa8-138">한 달에 한 번씩 랩 리소스를 요청할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9afa8-138">You can request for lab resources once a month.</span></span> 

<span data-ttu-id="9afa8-139">이미 랩이 있나요?</span><span class="sxs-lookup"><span data-stu-id="9afa8-139">Already have a lab?</span></span> <span data-ttu-id="9afa8-140">새 위협 시뮬레이터를 사용하도록 설정하고 활성 장치를 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9afa8-140">Make sure to enable the new threat simulators and have active devices.</span></span>

## <a name="setup-the-evaluation-lab"></a><span data-ttu-id="9afa8-141">평가 랩 설정</span><span class="sxs-lookup"><span data-stu-id="9afa8-141">Setup the evaluation lab</span></span>

1. <span data-ttu-id="9afa8-142">탐색 창에서 평가 및 자습서 **평가** 랩  >  을 선택한 다음 설치 **랩 을 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="9afa8-142">In the navigation pane, select **Evaluation and tutorials** > **Evaluation lab**, then select **Setup lab**.</span></span>

    ![평가 랩 시작 페이지의 이미지](images/evaluation-lab-setup.png)

2. <span data-ttu-id="9afa8-144">평가 요구에 따라 더 긴 기간 동안 더 적은 장치 또는 더 짧은 기간 동안 더 많은 장치를 사용하여 환경을 설정하기로 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9afa8-144">Depending on your evaluation needs, you can choose to setup an environment with fewer devices for a longer period or more devices for a shorter period.</span></span> <span data-ttu-id="9afa8-145">기본 설정 랩 구성을 선택한 후 다음 을 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="9afa8-145">Select your preferred lab configuration then select **Next**.</span></span>

    ![랩 구성 옵션의 이미지](images/lab-creation-page.png) 


3. <span data-ttu-id="9afa8-147">(선택 사항) 랩에 위협 시뮬레이터를 설치하도록 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9afa8-147">(Optional) You can choose to install threat simulators in the lab.</span></span> 

    ![설치 시뮬레이터 에이전트의 이미지](images/install-agent.png)

    >[!IMPORTANT]
    ><span data-ttu-id="9afa8-149">먼저 약관 및 정보 공유 설명에 동의하고 동의해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9afa8-149">You'll first need to accept and provide consent to the terms and information sharing statements.</span></span> 

4. <span data-ttu-id="9afa8-150">사용할 위협 시뮬레이션 에이전트를 선택하고 세부 정보를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="9afa8-150">Select the threat simulation agent you'd like to use and enter your details.</span></span> <span data-ttu-id="9afa8-151">나중에 위협 시뮬레이터를 설치하도록 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9afa8-151">You can also choose to install threat simulators at a later time.</span></span> <span data-ttu-id="9afa8-152">랩 설치 중에 위협 시뮬레이션 에이전트를 설치하도록 선택한 경우 추가한 장치에 위협 시뮬레이션 에이전트를 편리하게 설치하는 이점을 즐길 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9afa8-152">If you choose to install threat simulation agents during the lab setup, you'll enjoy the benefit of having them conveniently installed on the devices you add.</span></span>  
    
    ![요약 페이지 이미지](images/lab-setup-summary.png)

5.  <span data-ttu-id="9afa8-154">요약을 검토하고 설치 **랩을 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="9afa8-154">Review the summary and select **Setup lab**.</span></span>  

<span data-ttu-id="9afa8-155">랩 설정 프로세스가 완료되면 디바이스를 추가하고 시뮬레이션을 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9afa8-155">After the lab setup process is complete, you can add devices and run simulations.</span></span> 


## <a name="add-devices"></a><span data-ttu-id="9afa8-156">장치 추가</span><span class="sxs-lookup"><span data-stu-id="9afa8-156">Add devices</span></span>
<span data-ttu-id="9afa8-157">환경에 장치를 추가하면 끝점용 Defender가 연결 세부 정보가 있는 잘 구성된 장치를 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="9afa8-157">When you add a device to your environment, Defender for Endpoint sets up a well-configured device with connection details.</span></span> <span data-ttu-id="9afa8-158">Server 2019 Windows 10 또는 Windows 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9afa8-158">You can add Windows 10 or Windows Server 2019 devices.</span></span>

<span data-ttu-id="9afa8-159">장치는 최신 버전의 OS 및 Office 2019 Standard 및 Java, PysIntenals 등의 기타 앱으로 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="9afa8-159">The device will be configured with the most up-to-date version of the OS and Office 2019 Standard as well as other apps such as Java, Python, and SysIntenals.</span></span> 

<span data-ttu-id="9afa8-160">랩 설정 중에 위협 시뮬레이터를 추가하기로 선택한 경우 모든 장치에 추가하는 장치에 위협 시뮬레이터 에이전트가 설치됩니다.</span><span class="sxs-lookup"><span data-stu-id="9afa8-160">If you chose to add a threat simulator during the lab setup, all devices will have the threat simulator agent installed in the devices that you add.</span></span>

<span data-ttu-id="9afa8-161">권장되는 Windows 보안 구성 요소가 켜져 감사 모드로 켜져 있는 경우 장치에서 자동으로 테넌트에 온보드됩니다.</span><span class="sxs-lookup"><span data-stu-id="9afa8-161">The device will automatically be onboarded to your tenant with the recommended Windows security components turned on and in audit mode - with no effort on your side.</span></span> 

<span data-ttu-id="9afa8-162">테스트 장치에 미리 구성된 보안 구성 요소는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="9afa8-162">The following security components are pre-configured in the test devices:</span></span>

- [<span data-ttu-id="9afa8-163">공격 표면 감소</span><span class="sxs-lookup"><span data-stu-id="9afa8-163">Attack surface reduction</span></span>](attack-surface-reduction.md)
- [<span data-ttu-id="9afa8-164">차단 시 차단</span><span class="sxs-lookup"><span data-stu-id="9afa8-164">Block at first sight</span></span>](configure-block-at-first-sight-microsoft-defender-antivirus.md)
- [<span data-ttu-id="9afa8-165">제어된 폴더 액세스</span><span class="sxs-lookup"><span data-stu-id="9afa8-165">Controlled folder access</span></span>](controlled-folders.md)
- [<span data-ttu-id="9afa8-166">악용 방지</span><span class="sxs-lookup"><span data-stu-id="9afa8-166">Exploit protection</span></span>](enable-exploit-protection.md)
- [<span data-ttu-id="9afa8-167">네트워크 보호</span><span class="sxs-lookup"><span data-stu-id="9afa8-167">Network protection</span></span>](network-protection.md)
- [<span data-ttu-id="9afa8-168">잠재적으로 원치 않는 응용 프로그램 검색</span><span class="sxs-lookup"><span data-stu-id="9afa8-168">Potentially unwanted application detection</span></span>](detect-block-potentially-unwanted-apps-microsoft-defender-antivirus.md)
- [<span data-ttu-id="9afa8-169">클라우드 제공 보호</span><span class="sxs-lookup"><span data-stu-id="9afa8-169">Cloud-delivered protection</span></span>](cloud-protection-microsoft-defender-antivirus.md)
- [<span data-ttu-id="9afa8-170">Microsoft Defender SmartScreen</span><span class="sxs-lookup"><span data-stu-id="9afa8-170">Microsoft Defender SmartScreen</span></span>](/windows/security/threat-protection/microsoft-defender-smartscreen/microsoft-defender-smartscreen-overview)

>[!NOTE]
> <span data-ttu-id="9afa8-171">Microsoft Defender 바이러스 백신 설정됩니다(감사 모드 아미기).</span><span class="sxs-lookup"><span data-stu-id="9afa8-171">Microsoft Defender Antivirus will be on (not in audit mode).</span></span> <span data-ttu-id="9afa8-172">사용자가 Microsoft Defender 바이러스 백신 실행을 차단하는 경우 디바이스에서 실시간 보호를 해제할 수 Windows 보안.</span><span class="sxs-lookup"><span data-stu-id="9afa8-172">If Microsoft Defender Antivirus blocks you from running your simulation, you can turn off real-time protection on the device through Windows Security.</span></span> <span data-ttu-id="9afa8-173">자세한 내용은 [Always-On 보호 구성을 참조하세요.](configure-real-time-protection-microsoft-defender-antivirus.md)</span><span class="sxs-lookup"><span data-stu-id="9afa8-173">For more information, see [Configure always-on protection](configure-real-time-protection-microsoft-defender-antivirus.md).</span></span>

<span data-ttu-id="9afa8-174">자동화된 조사 설정은 테넌트 설정에 따라 달라집니다.</span><span class="sxs-lookup"><span data-stu-id="9afa8-174">Automated investigation settings will be dependent on tenant settings.</span></span> <span data-ttu-id="9afa8-175">기본적으로 반자동으로 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="9afa8-175">It will be configured to be semi-automated by default.</span></span> <span data-ttu-id="9afa8-176">자세한 내용은 자동화된 조사 [개요를 참조하세요.](automated-investigations.md)</span><span class="sxs-lookup"><span data-stu-id="9afa8-176">For more information, see [Overview of Automated investigations](automated-investigations.md).</span></span>

>[!NOTE]
><span data-ttu-id="9afa8-177">테스트 장치에 대한 연결은 RDP를 사용하여 수행됩니다.</span><span class="sxs-lookup"><span data-stu-id="9afa8-177">The connection to the test devices is done using RDP.</span></span> <span data-ttu-id="9afa8-178">방화벽 설정에서 RDP 연결을 허용하는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="9afa8-178">Make sure that your firewall settings allow RDP connections.</span></span>

1. <span data-ttu-id="9afa8-179">대시보드에서 장치 **추가 를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="9afa8-179">From the dashboard, select **Add device**.</span></span> 

2. <span data-ttu-id="9afa8-180">추가할 디바이스 유형을 선택하십시오.</span><span class="sxs-lookup"><span data-stu-id="9afa8-180">Choose the type of device to add.</span></span> <span data-ttu-id="9afa8-181">Server 2019를 추가하거나 Windows 10 Windows 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9afa8-181">You can choose to add Windows 10 or Windows Server 2019.</span></span>

    ![디바이스 옵션을 사용하여 랩 설정의 이미지](images/add-machine-options.png)


    >[!NOTE]
    ><span data-ttu-id="9afa8-183">장치 만들기 프로세스에 문제가 있는 경우 알림을 보게 되고 새 요청을 제출해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9afa8-183">If something goes wrong with the device creation process, you'll be notified and you'll need to submit a new request.</span></span> <span data-ttu-id="9afa8-184">장치 만들기가 실패하면 전체 허용 할당량에 대해 계산되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="9afa8-184">If the device creation fails, it will not be counted against the overall allowed quota.</span></span> 

3. <span data-ttu-id="9afa8-185">연결 세부 정보가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="9afa8-185">The connection details are displayed.</span></span> <span data-ttu-id="9afa8-186">**디바이스의** 암호를 저장하려면 복사를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="9afa8-186">Select **Copy** to save the password for the device.</span></span>

    >[!NOTE]
    ><span data-ttu-id="9afa8-187">암호는 한 번만 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="9afa8-187">The password is only displayed once.</span></span> <span data-ttu-id="9afa8-188">나중에 사용하기 위해 저장해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9afa8-188">Be sure to save it for later use.</span></span>

    ![연결 세부 정보를 사용하여 추가된 디바이스의 이미지](images/add-machine-eval-lab.png)

4. <span data-ttu-id="9afa8-190">디바이스 설정이 시작됩니다.</span><span class="sxs-lookup"><span data-stu-id="9afa8-190">Device set up begins.</span></span> <span data-ttu-id="9afa8-191">약 30분 정도 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9afa8-191">This can take up to approximately 30 minutes.</span></span> 

5. <span data-ttu-id="9afa8-192">장치 탭을 선택하여 테스트 장치의 상태, 위험 및 노출 수준, 시뮬레이터 설치 상태를 볼 **수** 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9afa8-192">See the status of test devices, the risk and exposure levels, and the status of simulator installations by selecting the **Devices** tab.</span></span> 

    ![장치 탭의 이미지](images/machines-tab.png)
    

    > [!TIP]
    > <span data-ttu-id="9afa8-194">시뮬레이터 **상태** 열에서 정보 아이콘 위에 마우스를 여 에이전트의 설치 상태를 알 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9afa8-194">In the **Simulator status** column, you can hover over the information icon to know the installation status of an agent.</span></span>

## <a name="request-for-more-devices"></a><span data-ttu-id="9afa8-195">추가 장치 요청</span><span class="sxs-lookup"><span data-stu-id="9afa8-195">Request for more devices</span></span>
<span data-ttu-id="9afa8-196">모든 기존 장치를 사용 및 삭제하는 경우 더 많은 디바이스를 요청할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9afa8-196">When all existing devices are used and deleted, you can request for more devices.</span></span> <span data-ttu-id="9afa8-197">한 달에 한 번씩 랩 리소스를 요청할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9afa8-197">You can request for lab resources once a month.</span></span> 


1. <span data-ttu-id="9afa8-198">평가 랩 대시보드에서 추가 장치 **요청을 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="9afa8-198">From the evaluation lab dashboard, select **Request for more devices**.</span></span>

   ![더 많은 장치에 대한 요청 이미지](images/request-more-devices.png)

2. <span data-ttu-id="9afa8-200">구성을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="9afa8-200">Choose your configuration.</span></span> 
3. <span data-ttu-id="9afa8-201">요청을 제출합니다.</span><span class="sxs-lookup"><span data-stu-id="9afa8-201">Submit the request.</span></span> 

<span data-ttu-id="9afa8-202">요청이 성공적으로 제출된 경우 녹색 확인 배너와 마지막 제출 날짜가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="9afa8-202">When the request is submitted successfully you'll see a green confirmation banner and the date of the last submission.</span></span>
 
<span data-ttu-id="9afa8-203">요청의 상태는 몇 시간  후 승인되는 사용자 작업 탭에서 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9afa8-203">You can find the status of your request in the **User Actions** tab, which will be approved in a matter of hours.</span></span>

<span data-ttu-id="9afa8-204">승인되면 요청된 장치가 랩 설정에 추가되어 더 많은 디바이스를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9afa8-204">When approved, the requested devices will be added to your lab set up and you’ll be able to create more devices.</span></span> 


> [!TIP]
> <span data-ttu-id="9afa8-205">랩을 좀 더 잘 진행하기 위해 시뮬레이션 라이브러리를 체크 아웃하는 것을 잊지 마세요.</span><span class="sxs-lookup"><span data-stu-id="9afa8-205">To get more out of your lab, don’t forget to check out our simulations library.</span></span>

## <a name="simulate-attack-scenarios"></a><span data-ttu-id="9afa8-206">공격 시나리오 시뮬레이트</span><span class="sxs-lookup"><span data-stu-id="9afa8-206">Simulate attack scenarios</span></span>
<span data-ttu-id="9afa8-207">테스트 장치를 사용하여 연결하여 자체 공격 시뮬레이션을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="9afa8-207">Use the test devices to run your own attack simulations by connecting to them.</span></span> 

<span data-ttu-id="9afa8-208">다음을 사용하여 공격 시나리오를 시뮬레이트할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9afa8-208">You can simulate attack scenarios using:</span></span>
- <span data-ttu-id="9afa8-209">["직접" 공격 시나리오](https://securitycenter.windows.com/tutorials)</span><span class="sxs-lookup"><span data-stu-id="9afa8-209">The ["Do It Yourself" attack scenarios](https://securitycenter.windows.com/tutorials)</span></span>
- <span data-ttu-id="9afa8-210">위협 시뮬레이터</span><span class="sxs-lookup"><span data-stu-id="9afa8-210">Threat simulators</span></span>

<span data-ttu-id="9afa8-211">고급 [헌팅을](advanced-hunting-overview.md) 사용하여 데이터 및 [위협](threat-analytics.md) 분석을 쿼리하여 새로운 위협에 대한 보고서를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9afa8-211">You can also use [Advanced hunting](advanced-hunting-overview.md) to query data and [Threat analytics](threat-analytics.md) to view reports about emerging threats.</span></span>

### <a name="do-it-yourself-attack-scenarios"></a><span data-ttu-id="9afa8-212">직접 공격 시나리오</span><span class="sxs-lookup"><span data-stu-id="9afa8-212">Do-it-yourself attack scenarios</span></span>
<span data-ttu-id="9afa8-213">미리 만든 시뮬레이션을 찾고 있는 경우 ["직접 실행"](https://securitycenter.windows.com/tutorials)공격 시나리오를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9afa8-213">If you are looking for a pre-made simulation, you can use our ["Do It Yourself" attack scenarios](https://securitycenter.windows.com/tutorials).</span></span> <span data-ttu-id="9afa8-214">이러한 스크립트는 안전하고 문서화되어 있으며 사용하기 쉽습니다.</span><span class="sxs-lookup"><span data-stu-id="9afa8-214">These scripts are safe, documented, and easy to use.</span></span> <span data-ttu-id="9afa8-215">이러한 시나리오는 끝점 기능에 대한 Defender를 반영하고 조사 환경을 진행합니다.</span><span class="sxs-lookup"><span data-stu-id="9afa8-215">These scenarios will reflect Defender for Endpoint capabilities and walk you through investigation experience.</span></span>


>[!NOTE]
><span data-ttu-id="9afa8-216">테스트 장치에 대한 연결은 RDP를 사용하여 수행됩니다.</span><span class="sxs-lookup"><span data-stu-id="9afa8-216">The connection to the test devices is done using RDP.</span></span> <span data-ttu-id="9afa8-217">방화벽 설정에서 RDP 연결을 허용하는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="9afa8-217">Make sure that your firewall settings allow RDP connections.</span></span>

1. <span data-ttu-id="9afa8-218">커넥트 를 선택하여 장치에 연결하고 를 선택하여 **공격 시뮬레이션을 커넥트.**</span><span class="sxs-lookup"><span data-stu-id="9afa8-218">Connect to your device and run an attack simulation by selecting **Connect**.</span></span> 

    ![테스트 장치에 대한 연결 단추의 이미지](images/test-machine-table.png)

2. <span data-ttu-id="9afa8-220">RDP 파일을 저장하고 를 선택하여 **커넥트.**</span><span class="sxs-lookup"><span data-stu-id="9afa8-220">Save the RDP file and launch it by selecting **Connect**.</span></span>

    ![원격 데스크톱 연결의 이미지](images/remote-connection.png)

    >[!NOTE]
    ><span data-ttu-id="9afa8-222">초기 설정 중에 암호 복사본을 저장하지 않은 경우 메뉴에서 암호 다시  설정을 선택하여 암호를 다시 설정할 수 있습니다. 암호 재설정 ![ 이미지](images/reset-password-test-machine.png)</span><span class="sxs-lookup"><span data-stu-id="9afa8-222">If you don't have a copy of the password saved during the initial setup, you can reset the password by selecting **Reset password** from the menu: ![Image of reset password](images/reset-password-test-machine.png)</span></span><br>
    > <span data-ttu-id="9afa8-223">디바이스의 상태가 "암호 재설정 실행"으로 변경되면 몇 분 후에 새 암호가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="9afa8-223">The device will change it’s state to “Executing password reset", then you’ll be presented with your new password in a few minutes.</span></span>

3. <span data-ttu-id="9afa8-224">디바이스를 만들 때 표시된 암호를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="9afa8-224">Enter the password that was displayed during the device creation step.</span></span> 

   ![자격 증명을 입력할 창의 이미지](images/enter-password.png)

4. <span data-ttu-id="9afa8-226">장치에서 Do-it-yourself 공격 시뮬레이션을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="9afa8-226">Run Do-it-yourself attack simulations on the device.</span></span> 


### <a name="threat-simulator-scenarios"></a><span data-ttu-id="9afa8-227">위협 시뮬레이터 시나리오</span><span class="sxs-lookup"><span data-stu-id="9afa8-227">Threat simulator scenarios</span></span>
<span data-ttu-id="9afa8-228">랩 설정 중에 지원되는 위협 시뮬레이터를 설치하도록 선택한 경우 평가 랩 디바이스에서 기본 제공 시뮬레이션을 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9afa8-228">If you chose to install any of the supported threat simulators during the lab setup, you can run the built-in simulations on the evaluation lab devices.</span></span> 


<span data-ttu-id="9afa8-229">타사 플랫폼을 사용하여 위협 시뮬레이션을 실행하는 것은 테스트 환경의 범위 내에서 끝점 기능에 대한 Microsoft Defender를 평가하는 좋은 방법입니다.</span><span class="sxs-lookup"><span data-stu-id="9afa8-229">Running threat simulations using third-party platforms is a good way to evaluate Microsoft Defender for Endpoint capabilities within the confines of a lab environment.</span></span>

>[!NOTE]
><span data-ttu-id="9afa8-230">시뮬레이션을 실행하기 전에 다음 요구 사항을 충족하는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="9afa8-230">Before you can run simulations, ensure the following requirements are met:</span></span>
>- <span data-ttu-id="9afa8-231">디바이스를 평가 랩에 추가해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9afa8-231">Devices must be added to the evaluation lab</span></span>
>- <span data-ttu-id="9afa8-232">위협 시뮬레이터를 평가 랩에 설치해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9afa8-232">Threat simulators must be installed in the evaluation lab</span></span>

1. <span data-ttu-id="9afa8-233">포털에서 시뮬레이션 **만들기를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="9afa8-233">From the portal select **Create simulation**.</span></span>

2. <span data-ttu-id="9afa8-234">위협 시뮬레이터를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="9afa8-234">Select a threat simulator.</span></span>

    ![위협 시뮬레이터 선택 이미지](images/select-simulator.png)

3. <span data-ttu-id="9afa8-236">시뮬레이션을 선택하거나 시뮬레이션 갤러리를 살펴보고 사용 가능한 시뮬레이션을 탐색합니다.</span><span class="sxs-lookup"><span data-stu-id="9afa8-236">Choose a simulation or look through the simulation gallery to browse through the available simulations.</span></span> 

    <span data-ttu-id="9afa8-237">시뮬레이션 갤러리는 다음에서 얻을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9afa8-237">You can get to the simulation gallery from:</span></span>
    - <span data-ttu-id="9afa8-238">시뮬레이션 개요 타일의 주 평가 **대시보드 또는**</span><span class="sxs-lookup"><span data-stu-id="9afa8-238">The main evaluation dashboard in the **Simulations overview** tile or</span></span>
    - <span data-ttu-id="9afa8-239">탐색 창 평가 및 자습서 시뮬레이션을 탐색하여  >  **자습서를 &** 시뮬레이션 **카탈로그를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="9afa8-239">By navigating from the navigation pane **Evaluation and tutorials** > **Simulation & tutorials**, then select **Simulations catalog**.</span></span>

4. <span data-ttu-id="9afa8-240">시뮬레이션을 실행할 디바이스를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="9afa8-240">Select the devices where you'd like to run the simulation on.</span></span>

5. <span data-ttu-id="9afa8-241">시뮬레이션 **만들기를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="9afa8-241">Select **Create simulation**.</span></span>

6. <span data-ttu-id="9afa8-242">시뮬레이션 탭을 선택하여 시뮬레이션 **진행률을 니다.** 시뮬레이션 상태, 활성 경고 및 기타 세부 정보를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9afa8-242">View the progress of a simulation by selecting the **Simulations** tab. View the simulation state, active alerts, and other details.</span></span> 

    ![시뮬레이션 탭의 이미지](images/simulations-tab.png)
    
<span data-ttu-id="9afa8-244">시뮬레이션을 실행한 후 랩 진행률 표시줄을 살펴보고 자동화된 조사 및 수정을 트리거한 **Endpoint용 Microsoft Defender를** 살펴보는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="9afa8-244">After running your simulations, we encourage you to walk through the lab progress bar and explore **Microsoft Defender for Endpoint triggered an automated investigation and remediation**.</span></span> <span data-ttu-id="9afa8-245">기능에서 수집 및 분석한 증거를 확인해 보아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9afa8-245">Check out the evidence collected and analyzed by the feature.</span></span>

<span data-ttu-id="9afa8-246">풍부한 쿼리 언어 및 원시 원격 분석을 사용하여 고급 헌팅을 통해 공격 증거를 헌팅하고 위협 분석에 문서화되어 있는 전 세계 위협을 확인해보십시오.</span><span class="sxs-lookup"><span data-stu-id="9afa8-246">Hunt for attack evidence through advanced hunting by using the rich query language and raw telemetry and check out some world-wide threats documented in Threat analytics.</span></span>


## <a name="simulation-gallery"></a><span data-ttu-id="9afa8-247">시뮬레이션 갤러리</span><span class="sxs-lookup"><span data-stu-id="9afa8-247">Simulation gallery</span></span>
<span data-ttu-id="9afa8-248">끝점용 Microsoft Defender는 다양한 위협 시뮬레이션 플랫폼과 파트너가 되어 포털 내에서 바로 플랫폼의 기능을 테스트할 수 있는 편리한 액세스 권한을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="9afa8-248">Microsoft Defender for Endpoint has partnered with various threat simulation platforms to give you convenient access to test the capabilities of the platform right from the within the portal.</span></span> 

<span data-ttu-id="9afa8-249">메뉴에서 시뮬레이션 및 자습서 시뮬레이션 카탈로그로 진행하여 사용 가능한 모든  >   시뮬레이션을 시청합니다.</span><span class="sxs-lookup"><span data-stu-id="9afa8-249">View all the available simulations by going to  **Simulations and tutorials** > **Simulations catalog**  from the menu.</span></span> 

<span data-ttu-id="9afa8-250">지원되는 타사 위협 시뮬레이션 에이전트 목록이 나열되어 있으며, 자세한 설명과 함께 특정 유형의 시뮬레이션이 카탈로그에 제공됩니다.</span><span class="sxs-lookup"><span data-stu-id="9afa8-250">A list of supported third-party threat simulation agents are listed, and specific types of simulations along with detailed descriptions are provided on the catalog.</span></span> 

<span data-ttu-id="9afa8-251">카탈로그에서 사용 가능한 시뮬레이션을 편리하게 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9afa8-251">You can conveniently run any available simulation right from the catalog.</span></span>  


![시뮬레이션 카탈로그 이미지](images/simulations-catalog.png)

<span data-ttu-id="9afa8-253">각 시뮬레이션에는 공격 시나리오에 대한 자세한 설명과 사용되는 MITRE 공격 기술 및 실행한 샘플 고급 헌팅 쿼리와 같은 참조가 함께 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="9afa8-253">Each simulation comes with an in-depth description of the attack scenario and references such as the MITRE attack techniques used and sample Advanced hunting queries you run.</span></span>

<span data-ttu-id="9afa8-254">**예:** 
 ![ 시뮬레이션 설명 세부 정보의 이미지1](images/simulation-details-aiq.png)</span><span class="sxs-lookup"><span data-stu-id="9afa8-254">**Examples:**
![Image of simulation description details1](images/simulation-details-aiq.png)</span></span>


![시뮬레이션 설명 세부 정보의 이미지2](images/simulation-details-sb.png)


## <a name="evaluation-report"></a><span data-ttu-id="9afa8-256">평가 보고서</span><span class="sxs-lookup"><span data-stu-id="9afa8-256">Evaluation report</span></span>
<span data-ttu-id="9afa8-257">랩 보고서에는 디바이스에서 수행된 시뮬레이션의 결과가 요약됩니다.</span><span class="sxs-lookup"><span data-stu-id="9afa8-257">The lab reports summarize the results of the simulations conducted on the devices.</span></span>

![평가 보고서의 이미지](images/eval-report.png)

<span data-ttu-id="9afa8-259">다음을 빠르게 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9afa8-259">At a glance, you'll quickly be able to see:</span></span>
- <span data-ttu-id="9afa8-260">트리거된 인시던트</span><span class="sxs-lookup"><span data-stu-id="9afa8-260">Incidents that were triggered</span></span>
- <span data-ttu-id="9afa8-261">생성된 경고</span><span class="sxs-lookup"><span data-stu-id="9afa8-261">Generated alerts</span></span>
- <span data-ttu-id="9afa8-262">노출 수준에 대한 평가</span><span class="sxs-lookup"><span data-stu-id="9afa8-262">Assessments on exposure level</span></span> 
- <span data-ttu-id="9afa8-263">관찰된 위협 범주</span><span class="sxs-lookup"><span data-stu-id="9afa8-263">Threat categories observed</span></span>
- <span data-ttu-id="9afa8-264">검색 원본</span><span class="sxs-lookup"><span data-stu-id="9afa8-264">Detection sources</span></span>
- <span data-ttu-id="9afa8-265">자동화된 조사</span><span class="sxs-lookup"><span data-stu-id="9afa8-265">Automated investigations</span></span>


## <a name="provide-feedback"></a><span data-ttu-id="9afa8-266">피드백 제공</span><span class="sxs-lookup"><span data-stu-id="9afa8-266">Provide feedback</span></span>
<span data-ttu-id="9afa8-267">사용자 의견은 고급 공격으로부터 환경을 보호하는 데 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9afa8-267">Your feedback helps us get better in protecting your environment from advanced attacks.</span></span> <span data-ttu-id="9afa8-268">제품 기능 및 평가 결과에서 경험과 노출을 공유합니다.</span><span class="sxs-lookup"><span data-stu-id="9afa8-268">Share your experience and impressions from product capabilities and evaluation results.</span></span>

<span data-ttu-id="9afa8-269">피드백 제공 을 선택하여 의견을 **알려주세요.**</span><span class="sxs-lookup"><span data-stu-id="9afa8-269">Let us know what you think, by selecting **Provide feedback**.</span></span>

![피드백 제공 이미지](images/send-us-feedback-eval-lab.png)
