---
title: 엔드포인트 보안 기준에 대한 Microsoft Defender 준수 강화
description: 끝점용 Microsoft Defender 보안 기준은 최적의 보호를 제공하도록 보안 제어를 설정합니다.
keywords: Intune 관리, 끝점용 Microsoft Defender, Microsoft Defender, 끝점 ASR용 Microsoft Defender, 보안 기준
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
ms.topic: article
ms.technology: mde
ms.openlocfilehash: fbdc0d02d4c5ba5cfda9773e62082217ba4f8c4e
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/21/2021
ms.locfileid: "51933604"
---
# <a name="increase-compliance-to-the-microsoft-defender-for-endpoint-security-baseline"></a><span data-ttu-id="cb656-104">엔드포인트 보안 기준에 대한 Microsoft Defender 준수 강화</span><span class="sxs-lookup"><span data-stu-id="cb656-104">Increase compliance to the Microsoft Defender for Endpoint security baseline</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="cb656-105">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="cb656-105">**Applies to:**</span></span>
- [<span data-ttu-id="cb656-106">엔드포인트용 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="cb656-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="cb656-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="cb656-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="cb656-108">Endpoint용 Defender를 경험하고 싶나요?</span><span class="sxs-lookup"><span data-stu-id="cb656-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="cb656-109">무료 평가판에 등록합니다.</span><span class="sxs-lookup"><span data-stu-id="cb656-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-onboardconfigure-abovefoldlink)

<span data-ttu-id="cb656-110">보안 기준은 보안 전문가와 전문가 Windows 시스템 관리자의 지침에 따라 보안 기능이 구성되도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="cb656-110">Security baselines ensure that security features are configured according to guidance from both security experts and expert Windows system administrators.</span></span> <span data-ttu-id="cb656-111">배포 시 엔드포인트용 Defender 보안 기준은 엔드포인트 보안 컨트롤에 대한 Defender를 설정하여 최적의 보호를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="cb656-111">When deployed, the Defender for Endpoint security baseline sets Defender for Endpoint security controls to provide optimal protection.</span></span>

<span data-ttu-id="cb656-112">보안 기준 및 구성 프로필을 사용하여 Intune에 보안 기준이 할당되는 방법을 이해하려면 이 [FAQ를 읽어 하세요.](https://docs.microsoft.com/intune/security-baselines#q--a)</span><span class="sxs-lookup"><span data-stu-id="cb656-112">To understand security baselines and how they are assigned on Intune using configuration profiles, [read this FAQ](https://docs.microsoft.com/intune/security-baselines#q--a).</span></span>

<span data-ttu-id="cb656-113">보안 기준에 대한 규정 준수를 배포하고 추적하기 전에 다음을 진행합니다.</span><span class="sxs-lookup"><span data-stu-id="cb656-113">Before you can deploy and track compliance to security baselines:</span></span>
- [<span data-ttu-id="cb656-114">Intune 관리에 장치 등록</span><span class="sxs-lookup"><span data-stu-id="cb656-114">Enroll your devices to Intune management</span></span>](configure-machines.md#enroll-devices-to-intune-management)
- [<span data-ttu-id="cb656-115">필요한 사용 권한이 있는지 확인</span><span class="sxs-lookup"><span data-stu-id="cb656-115">Ensure you have the necessary permissions</span></span>](configure-machines.md#obtain-required-permissions)

## <a name="compare-the-microsoft-defender-for-endpoint-and-the-windows-intune-security-baselines"></a><span data-ttu-id="cb656-116">끝점용 Microsoft Defender 및 Windows Intune 보안 기준 비교</span><span class="sxs-lookup"><span data-stu-id="cb656-116">Compare the Microsoft Defender for Endpoint and the Windows Intune security baselines</span></span>
<span data-ttu-id="cb656-117">Windows Intune 보안 기준은 브라우저 설정, PowerShell 설정, Microsoft Defender 바이러스 백신과 같은 일부 보안 기능에 대한 설정을 포함하여 Windows를 실행하는 장치를 안전하게 구성하는 데 필요한 포괄적인 권장 설정 집합을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="cb656-117">The Windows Intune security baseline provides a comprehensive set of recommended settings needed to securely configure devices running Windows, including browser settings, PowerShell settings, as well as settings for some security features like Microsoft Defender Antivirus.</span></span> <span data-ttu-id="cb656-118">반면 끝점용 Defender 기준은 끝점 검색 및 응답(EDR)에 대한 설정과 Windows Intune 보안 기준에 있는 설정을 포함하여 끝점 스택에 대한 Defender의 모든 보안 컨트롤을 최적화하는 설정을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="cb656-118">In contrast, the Defender for Endpoint baseline provides settings that optimize all the security controls in the Defender for Endpoint stack, including settings for endpoint detection and response (EDR) as well as settings also found in the Windows Intune security baseline.</span></span> <span data-ttu-id="cb656-119">각 기준에 대한 자세한 내용은 다음을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="cb656-119">For more information about each baseline, see:</span></span>

- [<span data-ttu-id="cb656-120">Intune에 대한 Windows 보안 기준 설정</span><span class="sxs-lookup"><span data-stu-id="cb656-120">Windows security baseline settings for Intune</span></span>](https://docs.microsoft.com/intune/security-baseline-settings-windows)
- [<span data-ttu-id="cb656-121">Intune에 대한 끝점 기준 설정에 대한 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="cb656-121">Microsoft Defender for Endpoint baseline settings for Intune</span></span>](https://docs.microsoft.com/intune/security-baseline-settings-defender-atp)

<span data-ttu-id="cb656-122">끝점용 Defender에 온보딩된 장치는 초기에 Windows를 보호하기 위한 Windows Intune 보안 기준과 끝점 보안 컨트롤에 대한 Defender를 최적으로 구성하기 위해 위에 계층화된 끝점용 보안 기준의 두 기준을 모두 배포하는 것이 가장 이상적입니다.</span><span class="sxs-lookup"><span data-stu-id="cb656-122">Ideally, devices onboarded to Defender for Endpoint are deployed both baselines: the Windows Intune security baseline to initially secure Windows and then the Defender for Endpoint security baseline layered on top to optimally configure the Defender for Endpoint security controls.</span></span> <span data-ttu-id="cb656-123">위험 및 위협에 대한 최신 데이터를 사용하여 기준이 발전함에 따라 충돌을 최소화하기 위해 항상 출시되는 즉시 모든 제품에 최신 버전의 기준을 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="cb656-123">To benefit from the latest data on risks and threats and to minimize conflicts as baselines evolve, always apply the latest versions of the baselines across all products as soon as they are released.</span></span>

>[!NOTE]
><span data-ttu-id="cb656-124">끝점용 Defender 보안 기준은 실제 장치에 최적화되어 있으며 현재 VM(가상 컴퓨터) 또는 VDI 끝점에서 사용하지 않는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="cb656-124">The Defender for Endpoint security baseline has been optimized for physical devices and is currently not recommended for use on virtual machine (VMs) or VDI endpoints.</span></span> <span data-ttu-id="cb656-125">특정 기준 설정은 가상화된 환경에서 원격 대화형 세션에 영향을 줄 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cb656-125">Certain baseline settings can impact remote interactive sessions on virtualized environments.</span></span>

## <a name="monitor-compliance-to-the-defender-for-endpoint-security-baseline"></a><span data-ttu-id="cb656-126">끝점 보안 기준에 대한 Defender 준수 모니터링</span><span class="sxs-lookup"><span data-stu-id="cb656-126">Monitor compliance to the Defender for Endpoint security baseline</span></span>

<span data-ttu-id="cb656-127">장치 **구성 관리의** 보안 기준 카드는 끝점 보안 기준에 대한 Defender가 할당된 Windows 10 장치에서 규정 준수에 대한 개요를 제공합니다. [](configure-machines.md)</span><span class="sxs-lookup"><span data-stu-id="cb656-127">The **Security baseline** card on [device configuration management](configure-machines.md) provides an overview of compliance across Windows 10 devices that have been assigned the Defender for Endpoint security baseline.</span></span>

<span data-ttu-id="cb656-128">![보안 기준 카드](images/secconmgmt_baseline_card.png)</span><span class="sxs-lookup"><span data-stu-id="cb656-128">![Security baseline card](images/secconmgmt_baseline_card.png)</span></span><br>
<span data-ttu-id="cb656-129">*엔드포인트 보안 기준에 대한 Defender 준수를 보여주는 카드*</span><span class="sxs-lookup"><span data-stu-id="cb656-129">*Card showing compliance to the Defender for Endpoint security baseline*</span></span>

<span data-ttu-id="cb656-130">각 디바이스에는 다음 상태 유형 중 하나가 부여됩니다.</span><span class="sxs-lookup"><span data-stu-id="cb656-130">Each device is given one of the following status types:</span></span>

- <span data-ttu-id="cb656-131">**기준 일치**- 장치 설정이 기준의 모든 설정과 일치</span><span class="sxs-lookup"><span data-stu-id="cb656-131">**Matches baseline**—device settings match all the settings in the baseline</span></span>
- <span data-ttu-id="cb656-132">**기준과 일치하지 않습니다.** 하나 이상의 장치 설정이 기준과 일치하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="cb656-132">**Does not match baseline**—at least one device setting doesn't match the baseline</span></span>
- <span data-ttu-id="cb656-133">**잘못 구성**- 하나 이상의 기준 설정이 장치에 제대로 구성되지 않은 상태 및 충돌, 오류 또는 보류 중인 상태</span><span class="sxs-lookup"><span data-stu-id="cb656-133">**Misconfigured**—at least one baseline setting isn't properly configured on the device and is in a conflict, error, or pending state</span></span>
- <span data-ttu-id="cb656-134">**해당되지 않습니다.** 장치에 하나 이상의 기준 설정이 적용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="cb656-134">**Not applicable**—At least one baseline setting isn't applicable on the device</span></span>

<span data-ttu-id="cb656-135">특정 장치를 검토하려면 카드에서 보안 **기준 구성을** 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="cb656-135">To review specific devices, select **Configure security baseline** on the card.</span></span> <span data-ttu-id="cb656-136">이렇게하면 Intune 장치 관리로 연결됩니다.</span><span class="sxs-lookup"><span data-stu-id="cb656-136">This takes you to Intune device management.</span></span> <span data-ttu-id="cb656-137">이 목록에서 디바이스 **이름 및 상태에** 대한 장치 상태를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="cb656-137">From there, select **Device status** for the names and statuses of the devices.</span></span>

>[!NOTE]
><span data-ttu-id="cb656-138">장치 구성 관리 페이지에 표시된 집계된 데이터와 Intune의 개요 화면에 표시되는 데이터가 불일치할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cb656-138">You might experience discrepancies in aggregated data displayed on the device configuration management page and those displayed on overview screens in Intune.</span></span>

## <a name="review-and-assign-the-microsoft-defender-for-endpoint-security-baseline"></a><span data-ttu-id="cb656-139">끝점용 Microsoft Defender 보안 기준 검토 및 할당</span><span class="sxs-lookup"><span data-stu-id="cb656-139">Review and assign the Microsoft Defender for Endpoint security baseline</span></span>

<span data-ttu-id="cb656-140">장치 구성 관리는 특별히 끝점 보안 기준에 대한 Microsoft Defender가 할당된 Windows 10 장치의 기준 준수만 모니터링합니다.</span><span class="sxs-lookup"><span data-stu-id="cb656-140">Device configuration management monitors baseline compliance only of Windows 10 devices that have been specifically assigned the Microsoft Defender for Endpoint security baseline.</span></span> <span data-ttu-id="cb656-141">Intune 장치 관리에서 기준을 편리하게 검토하고 장치에 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cb656-141">You can conveniently review the baseline and assign it to devices on Intune device management.</span></span>

1. <span data-ttu-id="cb656-142">**Intune** 장치 관리로 이동하려면 보안 기준 카드에서 보안 기준 구성을 선택합니다. </span><span class="sxs-lookup"><span data-stu-id="cb656-142">Select **Configure security baseline** on the **Security baseline** card to go to Intune device management.</span></span> <span data-ttu-id="cb656-143">유사한 기준 준수 개요가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="cb656-143">A similar overview of baseline compliance is displayed.</span></span>

   >[!TIP]
   > <span data-ttu-id="cb656-144">또는 Microsoft Defender ATP 기준에 대한 모든 서비스> Intune > 장치 보안 > Microsoft Azure Portal에서 끝점용 **Defender 보안 기준으로 >** 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cb656-144">Alternatively, you can navigate to the Defender for Endpoint security baseline in the Microsoft Azure portal from **All services > Intune > Device security > Security baselines > Microsoft Defender ATP baseline**.</span></span>


2. <span data-ttu-id="cb656-145">새 프로필을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cb656-145">Create a new profile.</span></span>

   <span data-ttu-id="cb656-146">![Intune의 끝점용 Microsoft Defender 보안 기준 개요](images/secconmgmt_baseline_intuneprofile1.png)</span><span class="sxs-lookup"><span data-stu-id="cb656-146">![Microsoft Defender for Endpoint security baseline overview on Intune](images/secconmgmt_baseline_intuneprofile1.png)</span></span><br>
   <span data-ttu-id="cb656-147">*Intune의 끝점용 Microsoft Defender 보안 기준 개요*</span><span class="sxs-lookup"><span data-stu-id="cb656-147">*Microsoft Defender for Endpoint security baseline overview on Intune*</span></span>

3. <span data-ttu-id="cb656-148">프로필을 만들 때 기준에 따라 특정 설정을 검토하고 조정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cb656-148">During profile creation, you can review and adjust specific settings on the baseline.</span></span>

   <span data-ttu-id="cb656-149">![Intune에서 프로필을 만들 때 보안 기준 옵션](images/secconmgmt_baseline_intuneprofile2.png)</span><span class="sxs-lookup"><span data-stu-id="cb656-149">![Security baseline options during profile creation on Intune](images/secconmgmt_baseline_intuneprofile2.png)</span></span><br>
   <span data-ttu-id="cb656-150">*Intune에서 프로필을 만들 때 보안 기준 옵션*</span><span class="sxs-lookup"><span data-stu-id="cb656-150">*Security baseline options during profile creation on Intune*</span></span>

4. <span data-ttu-id="cb656-151">프로필을 적절한 장치 그룹에 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="cb656-151">Assign the profile to the appropriate device group.</span></span>

   <span data-ttu-id="cb656-152">![Intune의 보안 기준 프로필](images/secconmgmt_baseline_intuneprofile3.png)</span><span class="sxs-lookup"><span data-stu-id="cb656-152">![Security baseline profiles on Intune](images/secconmgmt_baseline_intuneprofile3.png)</span></span><br>
   <span data-ttu-id="cb656-153">*Intune에서 보안 기준 프로필 할당*</span><span class="sxs-lookup"><span data-stu-id="cb656-153">*Assigning the security baseline profile on Intune*</span></span>

5. <span data-ttu-id="cb656-154">프로필을 만들어 저장하고 할당된 장치 그룹에 배포합니다.</span><span class="sxs-lookup"><span data-stu-id="cb656-154">Create the profile to save it and deploy it to the assigned device group.</span></span>

   <span data-ttu-id="cb656-155">![Intune에서 보안 기준 할당](images/secconmgmt_baseline_intuneprofile4.png)</span><span class="sxs-lookup"><span data-stu-id="cb656-155">![Assigning the security baseline on Intune](images/secconmgmt_baseline_intuneprofile4.png)</span></span><br>
   <span data-ttu-id="cb656-156">*Intune에서 보안 기준 프로필 만들기*</span><span class="sxs-lookup"><span data-stu-id="cb656-156">*Creating the security baseline profile on Intune*</span></span>

>[!TIP]
><span data-ttu-id="cb656-157">Intune의 보안 기준은 장치를 포괄적으로 보호하고 보호하는 편리한 방법을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="cb656-157">Security baselines on Intune provide a convenient way to comprehensively secure and protect your devices.</span></span> <span data-ttu-id="cb656-158">[Intune의 보안 기준에 대해 자세히 알아보시고](https://docs.microsoft.com/intune/security-baselines)</span><span class="sxs-lookup"><span data-stu-id="cb656-158">[Learn more about security baselines on Intune](https://docs.microsoft.com/intune/security-baselines).</span></span>

><span data-ttu-id="cb656-159">끝점용 Microsoft Defender를 경험하고 싶나요?</span><span class="sxs-lookup"><span data-stu-id="cb656-159">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="cb656-160">무료 평가판에 등록합니다.</span><span class="sxs-lookup"><span data-stu-id="cb656-160">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-onboardconfigure-belowfoldlink)

## <a name="related-topics"></a><span data-ttu-id="cb656-161">관련 항목</span><span class="sxs-lookup"><span data-stu-id="cb656-161">Related topics</span></span>
- [<span data-ttu-id="cb656-162">장치가 올바르게 구성되어 있는지 확인</span><span class="sxs-lookup"><span data-stu-id="cb656-162">Ensure your devices are configured properly</span></span>](configure-machines.md)
- [<span data-ttu-id="cb656-163">끝점용 Microsoft Defender에 장치 온보딩</span><span class="sxs-lookup"><span data-stu-id="cb656-163">Get devices onboarded to Microsoft Defender for Endpoint</span></span>](configure-machines-onboarding.md)
- [<span data-ttu-id="cb656-164">ASR 규칙 배포 및 검색 최적화</span><span class="sxs-lookup"><span data-stu-id="cb656-164">Optimize ASR rule deployment and detections</span></span>](configure-machines-asr.md)
