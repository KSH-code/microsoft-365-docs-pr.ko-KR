---
title: 2단계. 첫 번째 인시던트 수정
description: Defender에서 첫 번째 인시던트 수정을 시작하는 Microsoft 365 방법.
keywords: 인시던트, 경고, 조사, 상관 관계, 공격, 컴퓨터, 장치, 사용자, ID, ID, 사서함, 전자 메일, 365, Microsoft, m365, 인시던트 대응, 사이버 공격
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.technology: m365d
ms.openlocfilehash: 2fe6c5b1b0feea2163c0a2bcc871921a885abb85
ms.sourcegitcommit: 05f40904f8278f53643efa76a907968b5c662d9a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/30/2021
ms.locfileid: "52114990"
---
# <a name="step-2-remediate-your-first-incident"></a><span data-ttu-id="8cdf0-105">2단계.</span><span class="sxs-lookup"><span data-stu-id="8cdf0-105">Step 2.</span></span> <span data-ttu-id="8cdf0-106">첫 번째 인시던트 수정</span><span class="sxs-lookup"><span data-stu-id="8cdf0-106">Remediate your first incident</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="8cdf0-107">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="8cdf0-107">**Applies to:**</span></span>
- <span data-ttu-id="8cdf0-108">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="8cdf0-108">Microsoft 365 Defender</span></span>

<span data-ttu-id="8cdf0-109">Microsoft 365 Defender는 검색 및 분석 기능을 제공하는 것은 물론 맬웨어를 방지하고 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="8cdf0-109">Microsoft 365 Defender not only provides detection and analysis capabilities but also provides containment and eradication of malware.</span></span> <span data-ttu-id="8cdf0-110">포함에는 공격의 영향을 줄이는 단계가 포함되어 있는 반면, 제거는 공격자 활동의 모든 추적을 네트워크에서 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="8cdf0-110">Containment includes steps to reduce the impact of the attack while eradication ensures all traces of attacker activity are removed from the network.</span></span>  <span data-ttu-id="8cdf0-111">Microsoft 365 Defender는 운영 체제 및 공격 유형에 따라 자동 수정하도록 구성할 수 있는 몇 가지 수정 작업을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="8cdf0-111">Microsoft 365 Defender offers several remediation actions which can be configured to auto-remediate depending on your operating system and the attack type.</span></span>

<span data-ttu-id="8cdf0-112">Microsoft 365 Defender는 분석가가 수동으로 시작할 수 있는 몇 가지 수정 작업을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="8cdf0-112">Microsoft 365 Defender offers several remediation actions that analysts can manually initiate.</span></span> <span data-ttu-id="8cdf0-113">작업은 디바이스의 작업과 파일에 대한 작업의 두 범주로 구분됩니다.</span><span class="sxs-lookup"><span data-stu-id="8cdf0-113">Actions are separated into two categories, Actions on devices and Actions on files.</span></span> <span data-ttu-id="8cdf0-114">일부 작업을 사용하여 위협을 즉시 중지하고 다른 작업은 추가 포렌식 분석을 지원할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8cdf0-114">Some actions can be used to immediately stop the threat while other actions assist in further forensic analysis.</span></span>

## <a name="actions-on-devices"></a><span data-ttu-id="8cdf0-115">디바이스에 대한 작업</span><span class="sxs-lookup"><span data-stu-id="8cdf0-115">Actions on devices</span></span>

- <span data-ttu-id="8cdf0-116">**장치 격리** - 이 활동은 모든 네트워크 트래픽(인터넷 및 내부)을 즉시 차단하여 맬웨어 확산을 최소화하고 악의적인 행위자가 공격을 계속할 수 없는 한 분석가가 분석을 계속할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="8cdf0-116">**Isolate the device** - This activity immediately blocks all network traffic (internet and internal) to minimize the spread of malware and allow analysts to continue analysis without a malicious actor being able to continue an attack.</span></span> <span data-ttu-id="8cdf0-117">허용되는 유일한 연결은 Id용 Microsoft Defender 서비스 클라우드에 대한 것입니다. 따라서 Id에 대한 Microsoft Defender가 디바이스를 계속 모니터링할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8cdf0-117">The only connection allowed is to the Microsoft Defender for Identity service cloud so Microsoft Defender for Identity can continue to monitor the device.</span></span> 
- <span data-ttu-id="8cdf0-118">**앱 실행** 제한 - 응용 프로그램의 실행을 제한하기 위해 Microsoft에서 발급한 인증서로 서명된 파일만 실행할 수 있는 코드 무결성 정책이 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="8cdf0-118">**Restrict app execution** - To restrict an application from running, a code integrity policy is applied that only allows files to run if they are signed by a Microsoft-issued certificate.</span></span> <span data-ttu-id="8cdf0-119">이 제한 방법은 공격자가 손상된 장치를 제어하고 추가 악의적인 활동을 수행하지 못하게 방지하는 데 도움이 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8cdf0-119">This method of restriction can help prevent an attacker from controlling compromised devices and performing further malicious activities.</span></span>
- <span data-ttu-id="8cdf0-120">**바이러스 백신 검사** 실행 - Microsoft Defender 바이러스 백신 바이러스 백신이 활성 바이러스 백신 솔루션인지 여부에 따라 다른 바이러스 백신 솔루션과 함께 검사가 실행될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8cdf0-120">**Run Antivirus scan** - A Microsoft Defender Antivirus scan can run alongside other antivirus solutions, whether Defender Antivirus is the active antivirus solution or not.</span></span> <span data-ttu-id="8cdf0-121">다른 바이러스 백신 공급업체 제품이 기본 끝점 보호 솔루션인 경우 수동 모드에서 Defender 바이러스 백신을 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8cdf0-121">If another antivirus vendor product is the primary endpoint protection solution, you can run Defender Antivirus in Passive mode.</span></span>
- <span data-ttu-id="8cdf0-122">**자동화된 조사 시작** - 장치에서 새로운 일반 목적의 자동화된 조사를 시작할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8cdf0-122">**Initiate automated investigation** - You can start a new general purpose automated investigation on the device.</span></span> <span data-ttu-id="8cdf0-123">조사가 실행되는 동안 장치에서 생성된 다른 모든 경고는 해당 조사가 완료될 때까지 진행 중인 자동화된 조사에 추가됩니다.</span><span class="sxs-lookup"><span data-stu-id="8cdf0-123">While an investigation is running, any other alert generated from the device will be added to an ongoing automated investigation until that investigation is completed.</span></span> <span data-ttu-id="8cdf0-124">또한 다른 장치에서 동일한 위협이 있는 경우 해당 장치가 조사에 추가됩니다.</span><span class="sxs-lookup"><span data-stu-id="8cdf0-124">In addition, if the same threat is seen on other devices, those devices are added to the investigation.</span></span>
- <span data-ttu-id="8cdf0-125">**실시간 응답** 시작 - 실시간 응답은 원격 셸 연결을 사용하여 장치에 즉시 액세스할 수 있는 기능입니다.</span><span class="sxs-lookup"><span data-stu-id="8cdf0-125">**Initiate live response** - Live response is a capability that gives you instantaneous access to a device by using a remote shell connection.</span></span> <span data-ttu-id="8cdf0-126">이를 통해 심층 조사 작업을 수행하고 즉각적인 대응 조치를 취하여 식별된 위협을 실시간으로 즉시 포함할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8cdf0-126">This gives you the ability to do in-depth investigative work and take immediate response actions to promptly contain identified threats in real time.</span></span> <span data-ttu-id="8cdf0-127">실시간 대응은 사용자가 법의적 데이터를 수집하고, 스크립트를 실행하고, 분석을 위해 의심스러운 엔터티를 보내고, 위협을 수정하고, 새로운 위협에 대한 사전 대응적 헌팅을 할 수 있도록 하여 조사를 강화하도록 고안된 것입니다.</span><span class="sxs-lookup"><span data-stu-id="8cdf0-127">Live response is designed to enhance investigations by enabling you to collect forensic data, run scripts, send suspicious entities for analysis, remediate threats, and proactively hunt for emerging threats.</span></span>
- <span data-ttu-id="8cdf0-128">**조사 패키지 수집** - 조사 또는 응답 프로세스의 일부로 장치에서 조사 패키지를 수집할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8cdf0-128">**Collect investigation package** - As part of the investigation or response process, you can collect an investigation package from a device.</span></span> <span data-ttu-id="8cdf0-129">조사 패키지를 수집하면 장치의 현재 상태를 식별하고 공격자가 사용하는 도구와 기술을 추가로 이해할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8cdf0-129">By collecting the investigation package, you can identify the current state of the device and further understand the tools and techniques used by the attacker.</span></span> 
- <span data-ttu-id="8cdf0-130">**위협 전문가(장치** 및 파일에 대한 작업 모두에서 사용 가능) - Microsoft 위협 전문가에게 이미 손상된 장치 또는 잠재적으로 손상된 장치에 대한 자세한 정보를 얻을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8cdf0-130">**Consult a threat expert** (available in both Actions on devices and files) - You can consult a Microsoft threat expert for more insights regarding potentially compromised devices or devices that are already compromised.</span></span> <span data-ttu-id="8cdf0-131">Microsoft 위협 전문가는 시기적용하고 정확한 대응을 위해 Microsoft Defender 보안 센터 직접 참여할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8cdf0-131">Microsoft threat experts can be engaged directly from within the Microsoft Defender Security Center for a timely and accurate response.</span></span> 

## <a name="actions-on-files"></a><span data-ttu-id="8cdf0-132">파일에 대한 작업</span><span class="sxs-lookup"><span data-stu-id="8cdf0-132">Actions on files</span></span>

- <span data-ttu-id="8cdf0-133">파일 중지 및 **Quarantine** - 이 작업으로는 실행 중인 프로세스를 중지하고, 파일을 검지하고, 레지스트리 키와 같은 영구 데이터를 삭제하는 작업이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="8cdf0-133">**Stop and quarantine file** - This action includes stopping running processes, quarantining files, and deleting persistent data, such as any registry keys.</span></span> <span data-ttu-id="8cdf0-134">이 작업은 지난 30일 동안 Windows 10 버전 1703 이상이 있는 장치에 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="8cdf0-134">This action takes effect on devices with Windows 10, version 1703 or later, where the file was observed in the last 30 days.</span></span> 
- <span data-ttu-id="8cdf0-135">**파일을 차단하거나** 허용하는 표시기 추가 - 잠재적으로 악의적인 파일 또는 의심되는 맬웨어를 금지하여 조직에서 공격이 더 이상 전파되지 않도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="8cdf0-135">**Add indicators to block or allow file** - Prevent further propagation of an attack in your organization by banning potentially malicious files or suspected malware.</span></span> <span data-ttu-id="8cdf0-136">이 작업을 수행하면 조직의 장치에서 파일을 읽거나 쓰거나 실행할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="8cdf0-136">This operation will prevent the file from being read, written, or executed on devices in your organization.</span></span>
- <span data-ttu-id="8cdf0-137">**파일 다운로드** 또는 수집 - 이 작업을 통해 분석가가 암호로 보호된 파일 보관 파일로 파일을 .zip 추가 분석을 위해 파일을 다운로드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8cdf0-137">**Download or collect file** – This action allows analysts to download a file in a password protected .zip archive file for further analysis by the organization.</span></span>
- <span data-ttu-id="8cdf0-138">**심층 분석** - 이 작업은 안전하고 완벽하게 계측된 클라우드 환경에서 파일을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="8cdf0-138">**Deep analysis** – This action executes a file in a secure, fully instrumented cloud environment.</span></span> <span data-ttu-id="8cdf0-139">심층 분석 결과에는 파일의 활동, 관찰된 동작 및 연결된 아티팩트(예: 삭제된 파일, 레지스트리 수정, IP 주소와의 통신)가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="8cdf0-139">Deep analysis results show the file's activities, observed behaviors, and associated artifacts, such as dropped files, registry modifications, and communication with IP addresses.</span></span> 

<span data-ttu-id="8cdf0-140">인시던트 [감지,](first-incident-analyze.md#analyze-your-first-incident)분석 및 분석의 예제를 계속 진행하면 분석가가 다음 작업을 사용하여 이 인시던트를 재구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8cdf0-140">Continuing the example in [Detect, triage, and analyze incidents](first-incident-analyze.md#analyze-your-first-incident), an analyst can remediate this incident with these actions:</span></span>

1. <span data-ttu-id="8cdf0-141">사용자 계정 암호 즉시 다시 설정</span><span class="sxs-lookup"><span data-stu-id="8cdf0-141">Immediately reset the user account password</span></span>
2. <span data-ttu-id="8cdf0-142">심층 분석이 완료될 Microsoft 365 Defender에서 장치 격리</span><span class="sxs-lookup"><span data-stu-id="8cdf0-142">Isolate the device in Microsoft 365 Defender until deep analysis is complete</span></span>
3. <span data-ttu-id="8cdf0-143">악의적인 파일이 해당 파일에서 SharePoint</span><span class="sxs-lookup"><span data-stu-id="8cdf0-143">Ensure the malicious file was quarantined from SharePoint</span></span>
4. <span data-ttu-id="8cdf0-144">맬웨어의 영향을 받은 끝점 확인</span><span class="sxs-lookup"><span data-stu-id="8cdf0-144">Check which endpoints were affected by malware</span></span>
5. <span data-ttu-id="8cdf0-145">시스템 다시 구성</span><span class="sxs-lookup"><span data-stu-id="8cdf0-145">Rebuild systems</span></span>
6. <span data-ttu-id="8cdf0-146">다른 사용자에 대한 Microsoft Cloud App Security 경고 확인</span><span class="sxs-lookup"><span data-stu-id="8cdf0-146">Check for similar Microsoft Cloud App Security alerts for other users</span></span>
7. <span data-ttu-id="8cdf0-147">끝점용 Microsoft Defender에서 Tor IP 주소를 차단하는 사용자 지정 표시기 만들기</span><span class="sxs-lookup"><span data-stu-id="8cdf0-147">Create a custom indicator in Microsoft Defender for Endpoint to block a Tor IP address</span></span>
8. <span data-ttu-id="8cdf0-148">다음 이미지에 Microsoft Cloud App Security 이러한 유형의 경고에 대한 거버넌스 작업을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="8cdf0-148">Create a governance action in Microsoft Cloud App Security for this type of alert such as those shown in the following image:</span></span>

   :::image type="content" source="../../media/first-incident-remediate/first-incident-mcas-governance.png" alt-text="Microsoft Cloud App Security 거버넌스 작업의 예"::: 
 
<span data-ttu-id="8cdf0-150">대부분의 수정 작업은 Defender에서 적용하고 추적할 Microsoft 365 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8cdf0-150">Most of the remediation actions can be applied and tracked in Microsoft 365 Defender.</span></span> 

## <a name="using-playbooks"></a><span data-ttu-id="8cdf0-151">Playbook 사용</span><span class="sxs-lookup"><span data-stu-id="8cdf0-151">Using Playbooks</span></span>

<span data-ttu-id="8cdf0-152">또한 playbook을 사용하여 자동화된 수정을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8cdf0-152">In addition, automated remediation can be created using playbooks.</span></span> <span data-ttu-id="8cdf0-153">현재 [Microsoft에는](https://github.com/microsoft/Microsoft-Cloud-App-Security/tree/master/Playbooks) 다음과 같은 시나리오에 GitHub 플레이북을 제공하는 Playbook 템플릿이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8cdf0-153">Currently, Microsoft has [Playbook templates on GitHub](https://github.com/microsoft/Microsoft-Cloud-App-Security/tree/master/Playbooks) that provide playbooks for the following scenarios:</span></span>

- <span data-ttu-id="8cdf0-154">사용자 유효성 검사를 요청한 후 중요한 파일 공유 제거</span><span class="sxs-lookup"><span data-stu-id="8cdf0-154">Remove sensitive file sharing after requesting user validation</span></span>
- <span data-ttu-id="8cdf0-155">소수의 국가 자동 세분화 경고</span><span class="sxs-lookup"><span data-stu-id="8cdf0-155">Auto-triage infrequent country alerts</span></span>
- <span data-ttu-id="8cdf0-156">계정을 사용 안 하게 하기 전에 관리자 작업 요청</span><span class="sxs-lookup"><span data-stu-id="8cdf0-156">Request for manager action before disabling an account</span></span>
- <span data-ttu-id="8cdf0-157">악의적인 받은 편지함 규칙을 사용하지 않도록 설정</span><span class="sxs-lookup"><span data-stu-id="8cdf0-157">Disable malicious inbox rules</span></span>

<span data-ttu-id="8cdf0-158">플레이북은 Power Automate 트리거되면 사용자 지정 로봇 프로세스 자동화 흐름을 만들어 특정 활동을 자동화합니다.</span><span class="sxs-lookup"><span data-stu-id="8cdf0-158">Playbooks use Power Automate to create custom robotic process automation flows to automate certain activities once specific criteria have been triggered.</span></span> <span data-ttu-id="8cdf0-159">조직은 기존 템플릿에서 또는 처음부터 플레이북을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8cdf0-159">Organizations can create playbooks either from existing templates or from scratch.</span></span> 

<span data-ttu-id="8cdf0-160">다음은 예입니다.</span><span class="sxs-lookup"><span data-stu-id="8cdf0-160">Here's an example.</span></span>
 
:::image type="content" source="../../media/first-incident-remediate/first-incident-power-automate.png" alt-text="사용자 지정 Power Automate 자동화 흐름의 예"::: 
 
<span data-ttu-id="8cdf0-162">인시던트 사후 [](first-incident-post.md) 검토 중에 Playbook을 만들어 더 빠른 수정 작업을 위해 인시던트에서 수정 작업을 만들 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8cdf0-162">Playbooks can also be created during [post-incident review](first-incident-post.md) to create remediation actions from incidents for faster remediation actions.</span></span> 

## <a name="next-step"></a><span data-ttu-id="8cdf0-163">다음 단계</span><span class="sxs-lookup"><span data-stu-id="8cdf0-163">Next step</span></span>

<span data-ttu-id="8cdf0-164">[![3단계: 인시던트에 대한 인시던트 사후 검토를 수행하는 방법 학습](../../media/first-incident-overview/first-incident-path-step3.png)](first-incident-post.md)</span><span class="sxs-lookup"><span data-stu-id="8cdf0-164">[![Step 3: Learn how to perform a post-incident review of an incident](../../media/first-incident-overview/first-incident-path-step3.png)](first-incident-post.md)</span></span>

<span data-ttu-id="8cdf0-165">인시던트에 [대한 인시던트 사후](first-incident-post.md)검토를 수행하는 방법을 학습합니다.</span><span class="sxs-lookup"><span data-stu-id="8cdf0-165">Learn how to [perform a post-incident review of an incident](first-incident-post.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="8cdf0-166">참고 항목</span><span class="sxs-lookup"><span data-stu-id="8cdf0-166">See also</span></span>

- [<span data-ttu-id="8cdf0-167">인시던트 개요</span><span class="sxs-lookup"><span data-stu-id="8cdf0-167">Incidents overview</span></span>](incidents-overview.md)
- [<span data-ttu-id="8cdf0-168">인시던트 분석</span><span class="sxs-lookup"><span data-stu-id="8cdf0-168">Analyze incidents</span></span>](investigate-incidents.md)
- [<span data-ttu-id="8cdf0-169">인시던트 관리</span><span class="sxs-lookup"><span data-stu-id="8cdf0-169">Manage incidents</span></span>](manage-incidents.md)
