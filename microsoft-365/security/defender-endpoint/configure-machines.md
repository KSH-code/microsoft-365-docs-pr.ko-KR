---
title: 장치가 올바르게 구성되어 있는지 확인
description: 장치를 적절히 구성하여 위협에 대한 전반적인 탄력성을 높이고 공격을 감지하고 대응할 수 있는 기능을 향상시킵니다.
keywords: 온보드, Intune 관리, 끝점용 Microsoft Defender, Microsoft Defender, Windows Defender, 공격 표면 감소, ASR, 보안 기준
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: lomayor
author: lomayor
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: dccc623bfa6c3f5e8fe4d88ccfafd66d3e53482a
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/08/2021
ms.locfileid: "52840901"
---
# <a name="ensure-your-devices-are-configured-properly"></a><span data-ttu-id="10b50-104">장치가 올바르게 구성되어 있는지 확인</span><span class="sxs-lookup"><span data-stu-id="10b50-104">Ensure your devices are configured properly</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="10b50-105">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="10b50-105">**Applies to:**</span></span>
- [<span data-ttu-id="10b50-106">엔드포인트용 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="10b50-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="10b50-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="10b50-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="10b50-108">Endpoint용 Defender를 경험하고 싶나요?</span><span class="sxs-lookup"><span data-stu-id="10b50-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="10b50-109">무료 평가판에 등록합니다.</span><span class="sxs-lookup"><span data-stu-id="10b50-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-onboardconfigure-abovefoldlink)

<span data-ttu-id="10b50-110">적절히 구성된 장치를 사용하면 위협에 대한 전반적인 탄력성을 높이고 공격을 감지하고 대응할 수 있는 기능을 향상시킬 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="10b50-110">With properly configured devices, you can boost overall resilience against threats and enhance your capability to detect and respond to attacks.</span></span> <span data-ttu-id="10b50-111">보안 구성 관리는 디바이스를 보장하는 데 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="10b50-111">Security configuration management helps ensure that your devices:</span></span>

- <span data-ttu-id="10b50-112">끝점용 Microsoft Defender에 온보딩</span><span class="sxs-lookup"><span data-stu-id="10b50-112">Onboard to Microsoft Defender for Endpoint</span></span>
- <span data-ttu-id="10b50-113">끝점 보안 기준 구성에 대한 Defender 충족 또는 초과</span><span class="sxs-lookup"><span data-stu-id="10b50-113">Meet or exceed the Defender for Endpoint security baseline configuration</span></span>
- <span data-ttu-id="10b50-114">전략적 공격 표면 완화가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="10b50-114">Have strategic attack surface mitigations in place</span></span>

<span data-ttu-id="10b50-115">탐색 **메뉴에서** 구성 관리를 클릭하여 장치 구성 관리 페이지를 열 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="10b50-115">Click **Configuration management** from the navigation menu to open the Device configuration management page.</span></span>

<span data-ttu-id="10b50-116">![보안 구성 관리 페이지](images/secconmgmt_main.png)</span><span class="sxs-lookup"><span data-stu-id="10b50-116">![Security configuration management page](images/secconmgmt_main.png)</span></span><br>
<span data-ttu-id="10b50-117">*장치 구성 관리 페이지*</span><span class="sxs-lookup"><span data-stu-id="10b50-117">*Device configuration management page*</span></span>

<span data-ttu-id="10b50-118">조직 수준에서 구성 상태를 추적하고, 보안 센터 및 Microsoft Intune 및 Microsoft 365 보안 센터의 장치 관리 페이지에 대한 직접적인 딥 링크를 통해 불량 온보더링 범위, 규정 준수 문제 및 최적화된 공격 표면 완화에 대응하여 신속하게 조치를 취할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="10b50-118">You can track configuration status at an organizational level and quickly take action in response to poor onboarding coverage, compliance issues, and poorly optimized attack surface mitigations through direct, deep links to device management pages on Microsoft Intune and Microsoft 365 security center.</span></span>

<span data-ttu-id="10b50-119">이렇게 하면 다음을 통해 혜택을 받을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="10b50-119">In doing so, you benefit from:</span></span>
- <span data-ttu-id="10b50-120">디바이스에서 이벤트를 포괄적으로 확인</span><span class="sxs-lookup"><span data-stu-id="10b50-120">Comprehensive visibility of the events on your devices</span></span>
- <span data-ttu-id="10b50-121">원시 이벤트를 처리하고 위반 활동 및 위협 표시기를 식별하기 위한 강력한 위협 인텔리전스 및 강력한 장치 학습 기술</span><span class="sxs-lookup"><span data-stu-id="10b50-121">Robust threat intelligence and powerful device learning technologies for processing raw events and identifying the breach activity and threat indicators</span></span>
- <span data-ttu-id="10b50-122">악의적인 위험 요소 설치, 시스템 파일 및 프로세스의 하이재킹, 데이터 유출 및 기타 위협 활동의 설치를 효율적으로 중지하도록 구성된 전체 보안 기능 스택</span><span class="sxs-lookup"><span data-stu-id="10b50-122">A full stack of security features configured to efficiently stop the installation of malicious implants, hijacking of system files and process, data exfiltration, and other threat activities</span></span>
- <span data-ttu-id="10b50-123">생산성에 대한 영향을 최소화하면서 위협 활동에 대한 전략적 방어를 극대화하는 최적화된 공격 표면 완화</span><span class="sxs-lookup"><span data-stu-id="10b50-123">Optimized attack surface mitigations, maximizing strategic defenses against threat activity while minimizing impact to productivity</span></span>

## <a name="enroll-devices-to-intune-management"></a><span data-ttu-id="10b50-124">Intune 관리에 장치 등록</span><span class="sxs-lookup"><span data-stu-id="10b50-124">Enroll devices to Intune management</span></span>

<span data-ttu-id="10b50-125">장치 구성 관리는 Intune 장치 관리와 밀접하게 작동하여 조직의 디바이스 인벤토리 및 기준 보안 구성을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="10b50-125">Device configuration management works closely with Intune device management to establish the inventory of the devices in your organization and the baseline security configuration.</span></span> <span data-ttu-id="10b50-126">Intune 관리 디바이스에서 구성 문제를 추적하고 관리할 Windows 10 있습니다.</span><span class="sxs-lookup"><span data-stu-id="10b50-126">You will be able to track and manage configuration issues on Intune-managed Windows 10 devices.</span></span>

<span data-ttu-id="10b50-127">장치가 올바르게 구성되었는지 확인하려면 먼저 Intune 관리에 등록합니다.</span><span class="sxs-lookup"><span data-stu-id="10b50-127">Before you can ensure your devices are configured properly, enroll them to Intune management.</span></span> <span data-ttu-id="10b50-128">Intune 등록은 강력하며 장치용 여러 등록 Windows 10 있습니다.</span><span class="sxs-lookup"><span data-stu-id="10b50-128">Intune enrollment is robust and has several enrollment options for Windows 10 devices.</span></span> <span data-ttu-id="10b50-129">Intune 등록 옵션에 대한 자세한 내용은 장치 등록 [설정에 대해 Windows 읽어 보십시오.](/intune/windows-enroll)</span><span class="sxs-lookup"><span data-stu-id="10b50-129">For more information about Intune enrollment options, read about [setting up enrollment for Windows devices](/intune/windows-enroll).</span></span>

>[!NOTE]
><span data-ttu-id="10b50-130">Intune에 Windows 등록하려면 관리자에게 라이선스가 이미 할당되어 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="10b50-130">To enroll Windows devices to Intune, administrators must have already been assigned licenses.</span></span> <span data-ttu-id="10b50-131">[장치 등록에 대한 라이선스 할당에 대해 읽어 읽습니다.](/intune/licenses-assign)</span><span class="sxs-lookup"><span data-stu-id="10b50-131">[Read about assigning licenses for device enrollment](/intune/licenses-assign).</span></span>

>[!TIP] 
><span data-ttu-id="10b50-132">Intune을 통해 장치 관리를 최적화하려면 [끝점용 Defender에 Intune을 연결합니다.](/intune/advanced-threat-protection#enable-windows-defender-atp-in-intune)</span><span class="sxs-lookup"><span data-stu-id="10b50-132">To optimize device management through Intune, [connect Intune to Defender for Endpoint](/intune/advanced-threat-protection#enable-windows-defender-atp-in-intune).</span></span>

## <a name="obtain-required-permissions"></a><span data-ttu-id="10b50-133">필요한 사용 권한 얻기</span><span class="sxs-lookup"><span data-stu-id="10b50-133">Obtain required permissions</span></span>
<span data-ttu-id="10b50-134">기본적으로 Azure AD에서 전역 관리자 또는 Intune 서비스 관리자 역할이 할당된 사용자만 장치를 온보드하고 보안 기준을 배포하는 데 필요한 장치 구성 프로필을 관리하고 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="10b50-134">By default, only users who have been assigned the Global Administrator or the Intune Service Administrator role on Azure AD can manage and assign the device configuration profiles needed for onboarding devices and deploying the security baseline.</span></span>

<span data-ttu-id="10b50-135">다른 역할이 할당된 경우 필요한 사용 권한이 있는지 확인</span><span class="sxs-lookup"><span data-stu-id="10b50-135">If you have been assigned other roles, ensure you have the necessary permissions:</span></span>

- <span data-ttu-id="10b50-136">장치 구성에 대한 모든 권한</span><span class="sxs-lookup"><span data-stu-id="10b50-136">Full permissions to device configurations</span></span>
- <span data-ttu-id="10b50-137">보안 기준에 대한 모든 권한</span><span class="sxs-lookup"><span data-stu-id="10b50-137">Full permissions to security baselines</span></span>
- <span data-ttu-id="10b50-138">장치 준수 정책에 대한 읽기 권한</span><span class="sxs-lookup"><span data-stu-id="10b50-138">Read permissions to device compliance policies</span></span>
- <span data-ttu-id="10b50-139">조직에 대한 읽기 권한</span><span class="sxs-lookup"><span data-stu-id="10b50-139">Read permissions to the organization</span></span>

<span data-ttu-id="10b50-140">![intune에 대한 필수 권한](images/secconmgmt_intune_permissions.png)</span><span class="sxs-lookup"><span data-stu-id="10b50-140">![Required permissions on intune](images/secconmgmt_intune_permissions.png)</span></span><br>
<span data-ttu-id="10b50-141">*Intune에 대한 장치 구성 권한*</span><span class="sxs-lookup"><span data-stu-id="10b50-141">*Device configuration permissions on Intune*</span></span>

>[!TIP] 
><span data-ttu-id="10b50-142">Intune에 대한 사용 권한을 할당하는 데 대한 자세한 내용은 사용자 지정 [역할 만들기를 읽어 보아야 합니다.](/intune/create-custom-role#to-create-a-custom-role)</span><span class="sxs-lookup"><span data-stu-id="10b50-142">To learn more about assigning permissions on Intune, [read about creating custom roles](/intune/create-custom-role#to-create-a-custom-role).</span></span>

## <a name="in-this-section"></a><span data-ttu-id="10b50-143">이 섹션의 내용</span><span class="sxs-lookup"><span data-stu-id="10b50-143">In this section</span></span>
<span data-ttu-id="10b50-144">항목</span><span class="sxs-lookup"><span data-stu-id="10b50-144">Topic</span></span> | <span data-ttu-id="10b50-145">설명</span><span class="sxs-lookup"><span data-stu-id="10b50-145">Description</span></span>
:---|:---
[<span data-ttu-id="10b50-146">끝점용 Defender에 장치 온보딩</span><span class="sxs-lookup"><span data-stu-id="10b50-146">Get devices onboarded to Defender for Endpoint</span></span>](configure-machines-onboarding.md)| <span data-ttu-id="10b50-147">Intune 관리 장치의 온보더링 상태를 추적하고 Intune을 통해 더 많은 장치를 온보드합니다.</span><span class="sxs-lookup"><span data-stu-id="10b50-147">Track onboarding status of Intune-managed devices and onboard more devices through Intune.</span></span> 
[<span data-ttu-id="10b50-148">엔드포인트 보안 기준에 대한 Defender 준수 강화</span><span class="sxs-lookup"><span data-stu-id="10b50-148">Increase compliance to the Defender for Endpoint security baseline</span></span>](configure-machines-security-baseline.md) | <span data-ttu-id="10b50-149">기준 준수 및 비준수 추적</span><span class="sxs-lookup"><span data-stu-id="10b50-149">Track baseline compliance and noncompliance.</span></span> <span data-ttu-id="10b50-150">더 많은 Intune 관리 장치에 보안 기준을 배포합니다.</span><span class="sxs-lookup"><span data-stu-id="10b50-150">Deploy the security baseline to more Intune-managed devices.</span></span>
[<span data-ttu-id="10b50-151">ASR 규칙 배포 및 검색 최적화</span><span class="sxs-lookup"><span data-stu-id="10b50-151">Optimize ASR rule deployment and detections</span></span>](configure-machines-asr.md) | <span data-ttu-id="10b50-152">규칙 배포를 검토하고 보안 센터에서 영향 분석 도구를 사용하여 Microsoft 365 조정합니다.</span><span class="sxs-lookup"><span data-stu-id="10b50-152">Review rule deployment and tweak detections using impact analysis tools in Microsoft 365 security center.</span></span>

><span data-ttu-id="10b50-153">Endpoint용 Defender를 경험하고 싶나요?</span><span class="sxs-lookup"><span data-stu-id="10b50-153">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="10b50-154">무료 평가판에 등록합니다.</span><span class="sxs-lookup"><span data-stu-id="10b50-154">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-onboardconfigure-belowfoldlink)
