---
title: 구성 관리자를 사용하여 Windows 10 장치 온보딩
description: Configuration Manager를 사용하여 장치에 구성 패키지를 배포하여 서비스에 온보드합니다.
keywords: sccm을 사용하여 장치 온보딩, 장치 관리, Windows ATP 장치 구성, 끝점 장치용 Microsoft Defender 구성
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.date: 02/07/2020
ms.technology: mde
ms.openlocfilehash: b477f302855cb5d4b00e0502bcfa9aa3aeb6b5c2
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/24/2021
ms.locfileid: "51165576"
---
# <a name="onboard-windows-10-devices-using-configuration-manager"></a><span data-ttu-id="344fc-104">구성 관리자를 사용하여 Windows 10 장치 온보딩</span><span class="sxs-lookup"><span data-stu-id="344fc-104">Onboard Windows 10 devices using Configuration Manager</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="344fc-105">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="344fc-105">**Applies to:**</span></span>

- [<span data-ttu-id="344fc-106">엔드포인트용 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="344fc-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="344fc-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="344fc-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)
- <span data-ttu-id="344fc-108">Microsoft Endpoint Configuration Manager 현재 분기</span><span class="sxs-lookup"><span data-stu-id="344fc-108">Microsoft Endpoint Configuration Manager current branch</span></span>
- <span data-ttu-id="344fc-109">System Center 2012 R2 Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="344fc-109">System Center 2012 R2 Configuration Manager</span></span>

><span data-ttu-id="344fc-110">Endpoint용 Defender를 경험하고 싶나요?</span><span class="sxs-lookup"><span data-stu-id="344fc-110">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="344fc-111">무료 평가판에 등록합니다.</span><span class="sxs-lookup"><span data-stu-id="344fc-111">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-configureendpointssccm-abovefoldlink)

## <a name="supported-client-operating-systems"></a><span data-ttu-id="344fc-112">지원되는 클라이언트 운영 체제</span><span class="sxs-lookup"><span data-stu-id="344fc-112">Supported client operating systems</span></span>

<span data-ttu-id="344fc-113">실행 중인 Configuration Manager 버전에 따라 다음 클라이언트 운영 체제를 온보드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="344fc-113">Based on the version of Configuration Manager you're running, the following client operating systems can be onboarded:</span></span>

#### <a name="configuration-manager-version-1910-and-prior"></a><span data-ttu-id="344fc-114">Configuration Manager 버전 1910 및 이전</span><span class="sxs-lookup"><span data-stu-id="344fc-114">Configuration Manager version 1910 and prior</span></span>

- <span data-ttu-id="344fc-115">Windows 10을 실행하는 클라이언트 컴퓨터</span><span class="sxs-lookup"><span data-stu-id="344fc-115">Clients computers running Windows 10</span></span> 

#### <a name="configuration-manager-version-2002-and-later"></a><span data-ttu-id="344fc-116">Configuration Manager 버전 2002 이상</span><span class="sxs-lookup"><span data-stu-id="344fc-116">Configuration Manager version 2002 and later</span></span>

<span data-ttu-id="344fc-117">Configuration Manager 버전 2002부터 다음 운영 체제를 온보드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="344fc-117">Starting in Configuration Manager version 2002, you can onboard the following operating systems:</span></span>

- <span data-ttu-id="344fc-118">Windows 8.1</span><span class="sxs-lookup"><span data-stu-id="344fc-118">Windows 8.1</span></span>
- <span data-ttu-id="344fc-119">Windows 10</span><span class="sxs-lookup"><span data-stu-id="344fc-119">Windows 10</span></span>
- <span data-ttu-id="344fc-120">Windows Server 2012 R2</span><span class="sxs-lookup"><span data-stu-id="344fc-120">Windows Server 2012 R2</span></span>
- <span data-ttu-id="344fc-121">Windows Server 2016</span><span class="sxs-lookup"><span data-stu-id="344fc-121">Windows Server 2016</span></span>
- <span data-ttu-id="344fc-122">Windows Server 2016 버전 1803 이상</span><span class="sxs-lookup"><span data-stu-id="344fc-122">Windows Server 2016, version 1803 or later</span></span>
- <span data-ttu-id="344fc-123">Windows Server 2019</span><span class="sxs-lookup"><span data-stu-id="344fc-123">Windows Server 2019</span></span>

>[!NOTE]
><span data-ttu-id="344fc-124">R2, Windows Server 2016 및 Windows Server 2019를 Windows Server 2012 방법에 대한 자세한 내용은 Windows 서버 온보드를 [참조하세요.](configure-server-endpoints.md)</span><span class="sxs-lookup"><span data-stu-id="344fc-124">For more information on how to onboard Windows Server 2012 R2, Windows Server 2016, and Windows Server 2019, see, [Onboard Windows servers](configure-server-endpoints.md).</span></span>



### <a name="onboard-devices-using-system-center-configuration-manager"></a><span data-ttu-id="344fc-125">System Center Configuration Manager를 사용하여 장치 온보드</span><span class="sxs-lookup"><span data-stu-id="344fc-125">Onboard devices using System Center Configuration Manager</span></span>


<span data-ttu-id="344fc-126">[![다양한 배포 경로를 보여 주며 PDF 이미지](images/onboard-config-mgr.png)](images/onboard-config-mgr.png#lightbox)</span><span class="sxs-lookup"><span data-stu-id="344fc-126">[![Image of the PDF showing the various deployment paths](images/onboard-config-mgr.png)](images/onboard-config-mgr.png#lightbox)</span></span>


<span data-ttu-id="344fc-127">[PDF](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/security/defender-endpoint/downloads/mdatp-deployment-strategy.pdf) 또는 [Visio를](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/security/defender-endpoint/downloads/mdatp-deployment-strategy.vsdx) 확인하여 끝점용 Microsoft Defender 배포의 다양한 경로를 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="344fc-127">Check out the [PDF](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/security/defender-endpoint/downloads/mdatp-deployment-strategy.pdf)  or  [Visio](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/security/defender-endpoint/downloads/mdatp-deployment-strategy.vsdx) to see the various paths in deploying Microsoft Defender for Endpoint.</span></span> 



1. <span data-ttu-id="344fc-128">서비스 온보더링 마법사에서 \*\* 다운로드한 Configuration Manager 구성 패키지 .zip 파일(WindowsDefenderATPOnboardingPackage.zip)을 열 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="344fc-128">Open the Configuration Manager configuration package .zip file (*WindowsDefenderATPOnboardingPackage.zip*) that you downloaded from the service onboarding wizard.</span></span> <span data-ttu-id="344fc-129">Microsoft Defender 보안 센터에서 패키지를 [다운로드할 수 있습니다.](https://securitycenter.windows.com/)</span><span class="sxs-lookup"><span data-stu-id="344fc-129">You can also get the package from [Microsoft Defender Security Center](https://securitycenter.windows.com/):</span></span>

    1. <span data-ttu-id="344fc-130">탐색 창에서 설정   >  **온보드 를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="344fc-130">In the navigation pane, select **Settings** > **Onboarding**.</span></span>
    
    1. <span data-ttu-id="344fc-131">운영 체제로 Windows 10을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="344fc-131">Select Windows 10 as the operating system.</span></span>

    1. <span data-ttu-id="344fc-132">배포 **방법 필드에서** **System Center Configuration Manager 2012/2012 R2/1511/1602 를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="344fc-132">In the **Deployment method** field, select **System Center Configuration Manager 2012/2012 R2/1511/1602**.</span></span>
    
    1. <span data-ttu-id="344fc-133">패키지 **다운로드 를** 선택하고 .zip 파일을 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="344fc-133">Select **Download package**, and save the .zip file.</span></span>

2. <span data-ttu-id="344fc-134">패키지를 배포할 네트워크 관리자가 액세스할 수 있는 공유 읽기 전용 위치에 .zip 파일의 내용을 추출합니다.</span><span class="sxs-lookup"><span data-stu-id="344fc-134">Extract the contents of the .zip file to a shared, read-only location that can be accessed by the network administrators who will deploy the package.</span></span> <span data-ttu-id="344fc-135">*이름이 WindowsDefenderATPOnboardingScript.cmd인 파일이 있습니다.*</span><span class="sxs-lookup"><span data-stu-id="344fc-135">You should have a file named *WindowsDefenderATPOnboardingScript.cmd*.</span></span>

3. <span data-ttu-id="344fc-136">R2 Configuration Manager의 패키지 및 프로그램 문서에 [System Center 2012 패키지를 배포합니다.](https://docs.microsoft.com/previous-versions/system-center/system-center-2012-R2/gg699369\(v=technet.10\))</span><span class="sxs-lookup"><span data-stu-id="344fc-136">Deploy the package by following the steps in the [Packages and Programs in System Center 2012 R2 Configuration Manager](https://docs.microsoft.com/previous-versions/system-center/system-center-2012-R2/gg699369\(v=technet.10\)) article.</span></span>

    <span data-ttu-id="344fc-137">a.</span><span class="sxs-lookup"><span data-stu-id="344fc-137">a.</span></span> <span data-ttu-id="344fc-138">패키지를 배포할 미리 정의한 장치 컬렉션을 선택하십시오.</span><span class="sxs-lookup"><span data-stu-id="344fc-138">Choose a predefined device collection to deploy the package to.</span></span>

> [!NOTE]
> <span data-ttu-id="344fc-139">Endpoint용 Defender는 [OOBE(첫 경험)](https://answers.microsoft.com/en-us/windows/wiki/windows_10/how-to-complete-the-windows-10-out-of-box/47e3f943-f000-45e3-8c5c-9d85a1a0cf87) 단계에서 온보딩을 지원하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="344fc-139">Defender for Endpoint doesn't support onboarding during the [Out-Of-Box Experience (OOBE)](https://answers.microsoft.com/en-us/windows/wiki/windows_10/how-to-complete-the-windows-10-out-of-box/47e3f943-f000-45e3-8c5c-9d85a1a0cf87) phase.</span></span> <span data-ttu-id="344fc-140">사용자가 Windows 설치 또는 업그레이드를 실행한 후 OOBE를 완료해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="344fc-140">Make sure users complete OOBE after running Windows installation or upgrading.</span></span>

>[!TIP]
> <span data-ttu-id="344fc-141">장치를 온보드한 후 검색 테스트를 실행하여 장치가 서비스에 제대로 온보드되었는지 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="344fc-141">After onboarding the device, you can choose to run a detection test to verify that an device is properly onboarded to the service.</span></span> <span data-ttu-id="344fc-142">자세한 내용은 새로 온보딩된 Endpoint 디바이스용 Defender에서 검색 테스트 [실행을 참조하세요.](run-detection-test.md)</span><span class="sxs-lookup"><span data-stu-id="344fc-142">For more information, see [Run a detection test on a newly onboarded Defender for Endpoint device](run-detection-test.md).</span></span>
>
> <span data-ttu-id="344fc-143">Configuration Manager 응용 프로그램에 검색 규칙을 만들어 장치가 지속적으로 온보더된지 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="344fc-143">Note that it is possible to create a detection rule on a Configuration Manager application to continuously check if a device has been onboarded.</span></span> <span data-ttu-id="344fc-144">응용 프로그램은 패키지 및 프로그램과 다른 유형의 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="344fc-144">An application is a different type of object than a package and program.</span></span>
> <span data-ttu-id="344fc-145">장치가 아직 온보드되지 않은 경우(보류 중인 OOBE 완료 또는 다른 이유로 인해) 규칙에서 상태 변경이 감지될 때까지 Configuration Manager가 디바이스를 다시 시도합니다.</span><span class="sxs-lookup"><span data-stu-id="344fc-145">If a device is not yet onboarded (due to pending OOBE completion or any other reason), Configuration Manager will retry to onboard the device until the rule detects the status change.</span></span>
> 
> <span data-ttu-id="344fc-146">이 동작은 "OnboardingState" 레지스트리 값(형식이 REG_DWORD) = 1이면 검색 규칙을 만들어 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="344fc-146">This behavior can be accomplished by creating a detection rule checking if the "OnboardingState" registry value (of type REG_DWORD) = 1.</span></span>
> <span data-ttu-id="344fc-147">이 레지스트리 값은 "HKLM\SOFTWARE\Microsoft\Windows Advanced Threat Protection\Status" 아래에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="344fc-147">This registry value is located under "HKLM\SOFTWARE\Microsoft\Windows Advanced Threat Protection\Status".</span></span>
<span data-ttu-id="344fc-148">자세한 내용은 [Configure Detection Methods in System Center 2012 R2 Configuration Manager을 참조하십시오.](https://docs.microsoft.com/previous-versions/system-center/system-center-2012-R2/gg682159\(v=technet.10\)#step-4-configure-detection-methods-to-indicate-the-presence-of-the-deployment-type)</span><span class="sxs-lookup"><span data-stu-id="344fc-148">For more information, see [Configure Detection Methods in System Center 2012 R2 Configuration Manager](https://docs.microsoft.com/previous-versions/system-center/system-center-2012-R2/gg682159\(v=technet.10\)#step-4-configure-detection-methods-to-indicate-the-presence-of-the-deployment-type).</span></span>

### <a name="configure-sample-collection-settings"></a><span data-ttu-id="344fc-149">샘플 수집 설정 구성</span><span class="sxs-lookup"><span data-stu-id="344fc-149">Configure sample collection settings</span></span>

<span data-ttu-id="344fc-150">각 디바이스에 대해 Microsoft Defender 보안 센터를 통해 요청이 있을 때 장치에서 샘플을 수집할 수 있는지 여부를 설명하는 구성 값을 설정하여 심층 분석을 위해 파일을 제출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="344fc-150">For each device, you can set a configuration value to state whether samples can be collected from the device when a request is made through Microsoft Defender Security Center to submit a file for deep analysis.</span></span>

>[!NOTE]
><span data-ttu-id="344fc-151">이러한 구성 설정은 일반적으로 Configuration Manager를 통해 수행됩니다.</span><span class="sxs-lookup"><span data-stu-id="344fc-151">These configuration settings are typically done through Configuration Manager.</span></span> 

<span data-ttu-id="344fc-152">Configuration Manager에서 구성 항목에 대한 준수 규칙을 설정하여 장치에서 샘플 공유 설정을 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="344fc-152">You can set a compliance rule for configuration item in Configuration Manager to change the sample share setting on a device.</span></span>

<span data-ttu-id="344fc-153">이 규칙은  불만이 있는지 확인하도록 대상 디바이스의 레지스트리 키 값을 설정하는 수정 준수 규칙 구성 항목입니다.</span><span class="sxs-lookup"><span data-stu-id="344fc-153">This rule should be a *remediating* compliance rule configuration item that sets the value of a registry key on targeted devices to make sure they’re complaint.</span></span>

<span data-ttu-id="344fc-154">구성은 다음 레지스트리 키 항목을 통해 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="344fc-154">The configuration is set through the following registry key entry:</span></span>

```console
Path: "HKLM\SOFTWARE\Policies\Microsoft\Windows Advanced Threat Protection"
Name: "AllowSampleCollection"
Value: 0 or 1
```

<span data-ttu-id="344fc-155">여기서,</span><span class="sxs-lookup"><span data-stu-id="344fc-155">Where:</span></span><br>
<span data-ttu-id="344fc-156">키 형식은 D-WORD입니다.</span><span class="sxs-lookup"><span data-stu-id="344fc-156">Key type is a D-WORD.</span></span> <br>
<span data-ttu-id="344fc-157">가능한 값은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="344fc-157">Possible values are:</span></span>
- <span data-ttu-id="344fc-158">0 - 이 장치에서 샘플 공유를 허용하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="344fc-158">0 - doesn't allow sample sharing  from this device</span></span>
- <span data-ttu-id="344fc-159">1 - 이 장치에서 모든 파일 형식을 공유할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="344fc-159">1 - allows sharing of all file types from this device</span></span>

<span data-ttu-id="344fc-160">레지스트리 키가 없는 경우의 기본값은 1입니다.</span><span class="sxs-lookup"><span data-stu-id="344fc-160">The default value in case the registry key doesn’t exist is 1.</span></span>

<span data-ttu-id="344fc-161">System Center Configuration Manager 규정 준수에 대한 자세한 내용은 System Center 2012 R2 Configuration Manager의 규정 준수 설정 [소개를 참조하세요.](https://docs.microsoft.com/previous-versions/system-center/system-center-2012-R2/gg682139\(v=technet.10\))</span><span class="sxs-lookup"><span data-stu-id="344fc-161">For more information about System Center Configuration Manager Compliance, see [Introduction to compliance settings in System Center 2012 R2 Configuration Manager](https://docs.microsoft.com/previous-versions/system-center/system-center-2012-R2/gg682139\(v=technet.10\)).</span></span>


## <a name="other-recommended-configuration-settings"></a><span data-ttu-id="344fc-162">기타 권장 구성 설정</span><span class="sxs-lookup"><span data-stu-id="344fc-162">Other recommended configuration settings</span></span>
<span data-ttu-id="344fc-163">장치를 서비스에 온보드한 후 다음과 같은 권장 구성 설정을 사용하여 포함된 위협 방지 기능을 활용하는 것이 중요합니다.</span><span class="sxs-lookup"><span data-stu-id="344fc-163">After onboarding devices to the service, it's important to take advantage of the included threat protection capabilities by enabling them with the following recommended configuration settings.</span></span>

### <a name="device-collection-configuration"></a><span data-ttu-id="344fc-164">장치 컬렉션 구성</span><span class="sxs-lookup"><span data-stu-id="344fc-164">Device collection configuration</span></span>
<span data-ttu-id="344fc-165">Endpoint Configuration Manager 버전 2002 이상을 사용하는 경우 서버 또는 다운 수준 클라이언트를 포함하기 위해 배포를 확장할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="344fc-165">If you're using Endpoint Configuration Manager, version 2002 or later, you can choose to broaden the deployment to include servers or down-level clients.</span></span>


### <a name="next-generation-protection-configuration"></a><span data-ttu-id="344fc-166">차세대 보호 구성</span><span class="sxs-lookup"><span data-stu-id="344fc-166">Next generation protection configuration</span></span>
<span data-ttu-id="344fc-167">권장되는 구성 설정은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="344fc-167">The following configuration settings are recommended:</span></span>

<span data-ttu-id="344fc-168">**스캔**</span><span class="sxs-lookup"><span data-stu-id="344fc-168">**Scan**</span></span> <br>
- <span data-ttu-id="344fc-169">USB 드라이브와 같은 이동식 저장 장치 검색: 예</span><span class="sxs-lookup"><span data-stu-id="344fc-169">Scan removable storage devices such as USB drives: Yes</span></span>

<span data-ttu-id="344fc-170">**실시간 보호**</span><span class="sxs-lookup"><span data-stu-id="344fc-170">**Real-time Protection**</span></span> <br>
- <span data-ttu-id="344fc-171">동작 모니터링 사용: 예</span><span class="sxs-lookup"><span data-stu-id="344fc-171">Enable Behavioral Monitoring: Yes</span></span>
- <span data-ttu-id="344fc-172">다운로드할 때 및 설치 전에 사용자방지 응용 프로그램으로부터 보호 사용: 예</span><span class="sxs-lookup"><span data-stu-id="344fc-172">Enable protection against Potentially Unwanted Applications at download and prior to installation: Yes</span></span>

<span data-ttu-id="344fc-173">**클라우드 보호 서비스**</span><span class="sxs-lookup"><span data-stu-id="344fc-173">**Cloud Protection Service**</span></span>
- <span data-ttu-id="344fc-174">클라우드 보호 서비스 멤버십 유형: 고급 멤버십</span><span class="sxs-lookup"><span data-stu-id="344fc-174">Cloud Protection Service membership type: Advanced membership</span></span>

<span data-ttu-id="344fc-175">**공격 표면 감소** 사용 가능한 모든 규칙을 감사로 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="344fc-175">**Attack surface reduction** Configure all available rules to Audit.</span></span>

>[!NOTE]
> <span data-ttu-id="344fc-176">이러한 활동을 차단하면 합법적인 비즈니스 프로세스가 중단될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="344fc-176">Blocking these activities may interrupt legitimate business processes.</span></span> <span data-ttu-id="344fc-177">가장 좋은 방법은 모든 것을 감사로 설정하고, 켜기에 안전한 설정을 식별한 다음, 가짓 긍정 검색이 없는 끝점에서 해당 설정을 사용하도록 설정하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="344fc-177">The best approach is setting everything to audit, identifying which ones are safe to turn on, and then enabling those settings on endpoints which do not have false positive detections.</span></span>


<span data-ttu-id="344fc-178">**네트워크 보호**</span><span class="sxs-lookup"><span data-stu-id="344fc-178">**Network protection**</span></span> <br>
<span data-ttu-id="344fc-179">감사 또는 차단 모드에서 네트워크 보호를 사용하도록 설정하기 전에 지원 페이지에서 얻을 수 있는 맬웨어 방지 플랫폼 업데이트를 설치해야 [합니다.](https://support.microsoft.com/en-us/help/4560203/windows-defender-anti-malware-platform-binaries-are-missing)</span><span class="sxs-lookup"><span data-stu-id="344fc-179">Prior to enabling network protection in audit or block mode, ensure that you've installed the antimalware platform update, which can be obtained from the [support page](https://support.microsoft.com/en-us/help/4560203/windows-defender-anti-malware-platform-binaries-are-missing).</span></span>


<span data-ttu-id="344fc-180">**제어된 폴더 액세스**</span><span class="sxs-lookup"><span data-stu-id="344fc-180">**Controlled folder access**</span></span><br>
<span data-ttu-id="344fc-181">감사 모드에서 기능을 30일 이상 사용하도록 설정</span><span class="sxs-lookup"><span data-stu-id="344fc-181">Enable the feature in audit mode for at least 30 days.</span></span> <span data-ttu-id="344fc-182">이 기간이 지난 후 검색을 검토하고 보호된 Director에 쓸 수 있는 응용 프로그램 목록을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="344fc-182">After this period, review detections and create a list of applications that are allowed to write to protected directories.</span></span>

<span data-ttu-id="344fc-183">자세한 내용은 제어된 폴더 [액세스 평가를 참조하세요.](evaluate-controlled-folder-access.md)</span><span class="sxs-lookup"><span data-stu-id="344fc-183">For more information, see [Evaluate controlled folder access](evaluate-controlled-folder-access.md).</span></span>


## <a name="offboard-devices-using-configuration-manager"></a><span data-ttu-id="344fc-184">Configuration Manager를 사용하여 디바이스 오프보드</span><span class="sxs-lookup"><span data-stu-id="344fc-184">Offboard devices using Configuration Manager</span></span>

<span data-ttu-id="344fc-185">보안상의 이유로, 오프보드 장치에 사용된 패키지는 다운로드한 날짜 30일 후에 만료됩니다.</span><span class="sxs-lookup"><span data-stu-id="344fc-185">For security reasons, the package used to Offboard devices will expire 30 days after the date it was downloaded.</span></span> <span data-ttu-id="344fc-186">장치에 전송된 만료된 오프보더 패키지는 거부됩니다.</span><span class="sxs-lookup"><span data-stu-id="344fc-186">Expired offboarding packages sent to a device will be rejected.</span></span> <span data-ttu-id="344fc-187">오프보더 패키지를 다운로드할 때 패키지 만료 날짜에 대한 알림을 하게 되고 패키지 이름에도 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="344fc-187">When downloading an offboarding package, you will be notified of the packages expiry date and it will also be included in the package name.</span></span>

> [!NOTE]
> <span data-ttu-id="344fc-188">온보드 및 오프보더 정책을 동일한 장치에 동시에 배포하면 안 됩니다. 그렇지 않으면 예측할 수 없는 충돌이 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="344fc-188">Onboarding and offboarding policies must not be deployed on the same device at the same time, otherwise this will cause unpredictable collisions.</span></span>

### <a name="offboard-devices-using-microsoft-endpoint-manager-current-branch"></a><span data-ttu-id="344fc-189">Microsoft Endpoint Manager 현재 분기를 사용하여 장치 오프보드</span><span class="sxs-lookup"><span data-stu-id="344fc-189">Offboard devices using Microsoft Endpoint Manager current branch</span></span>

<span data-ttu-id="344fc-190">Microsoft Endpoint Manager 현재 분기를 사용하는 경우 오프보링 구성 파일 [만들기를 참조합니다.](https://docs.microsoft.com/configmgr/protect/deploy-use/windows-defender-advanced-threat-protection#create-an-offboarding-configuration-file)</span><span class="sxs-lookup"><span data-stu-id="344fc-190">If you use Microsoft Endpoint Manager current branch, see [Create an offboarding configuration file](https://docs.microsoft.com/configmgr/protect/deploy-use/windows-defender-advanced-threat-protection#create-an-offboarding-configuration-file).</span></span>

### <a name="offboard-devices-using-system-center-2012-r2-configuration-manager"></a><span data-ttu-id="344fc-191">R2 Configuration Manager를 사용하여 System Center 2012 오프보드</span><span class="sxs-lookup"><span data-stu-id="344fc-191">Offboard devices using System Center 2012 R2 Configuration Manager</span></span>

1. <span data-ttu-id="344fc-192">Microsoft Defender 보안 센터에서 오프보딩 [패키지를 다운로드합니다.](https://securitycenter.windows.com/)</span><span class="sxs-lookup"><span data-stu-id="344fc-192">Get the offboarding package from [Microsoft Defender Security Center](https://securitycenter.windows.com/):</span></span>

    1. <span data-ttu-id="344fc-193">탐색 창에서 설정 **오프보링**  >   **을 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="344fc-193">In the navigation pane, select **Settings** >  **Offboarding**.</span></span>

    1. <span data-ttu-id="344fc-194">운영 체제로 Windows 10을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="344fc-194">Select Windows 10 as the operating system.</span></span>

    1. <span data-ttu-id="344fc-195">배포 **방법 필드에서** **System Center Configuration Manager 2012/2012 R2/1511/1602 를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="344fc-195">In the **Deployment method** field, select **System Center Configuration Manager 2012/2012 R2/1511/1602**.</span></span>
    
    1. <span data-ttu-id="344fc-196">패키지 **다운로드 를** 선택하고 .zip 파일을 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="344fc-196">Select **Download package**, and save the .zip file.</span></span>

2. <span data-ttu-id="344fc-197">패키지를 배포할 네트워크 관리자가 액세스할 수 있는 공유 읽기 전용 위치에 .zip 파일의 내용을 추출합니다.</span><span class="sxs-lookup"><span data-stu-id="344fc-197">Extract the contents of the .zip file to a shared, read-only location that can be accessed by the network administrators who will deploy the package.</span></span> <span data-ttu-id="344fc-198">이름이 *WindowsDefenderATPOffboardingScript_valid_until_YYYY-MM-DD.cmd 입니다.*</span><span class="sxs-lookup"><span data-stu-id="344fc-198">You should have a file named *WindowsDefenderATPOffboardingScript_valid_until_YYYY-MM-DD.cmd*.</span></span>

3. <span data-ttu-id="344fc-199">R2 Configuration Manager의 패키지 및 프로그램 문서에 [System Center 2012 패키지를 배포합니다.](https://docs.microsoft.com/previous-versions/system-center/system-center-2012-R2/gg699369\(v=technet.10\))</span><span class="sxs-lookup"><span data-stu-id="344fc-199">Deploy the package by following the steps in the [Packages and Programs in System Center 2012 R2 Configuration Manager](https://docs.microsoft.com/previous-versions/system-center/system-center-2012-R2/gg699369\(v=technet.10\)) article.</span></span>

    <span data-ttu-id="344fc-200">a.</span><span class="sxs-lookup"><span data-stu-id="344fc-200">a.</span></span> <span data-ttu-id="344fc-201">패키지를 배포할 미리 정의한 장치 컬렉션을 선택하십시오.</span><span class="sxs-lookup"><span data-stu-id="344fc-201">Choose a predefined device collection to deploy the package to.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="344fc-202">오프보더링을 통해 디바이스가 포털에 센서 데이터 전송을 중지하지만, 디바이스에서 전송한 모든 경고에 대한 참조를 포함하여 장치의 데이터는 최대 6개월 동안 보존됩니다.</span><span class="sxs-lookup"><span data-stu-id="344fc-202">Offboarding causes the device to stop sending sensor data to the portal but data from the device, including reference to any alerts it has had will be retained for up to 6 months.</span></span>


## <a name="monitor-device-configuration"></a><span data-ttu-id="344fc-203">장치 구성 모니터링</span><span class="sxs-lookup"><span data-stu-id="344fc-203">Monitor device configuration</span></span>

<span data-ttu-id="344fc-204">Microsoft Endpoint Manager 현재 분기를 사용하는 경우 Configuration Manager 콘솔에서 기본 제공 Defender for Endpoint 대시보드를 사용하세요.</span><span class="sxs-lookup"><span data-stu-id="344fc-204">If you're using Microsoft Endpoint Manager current branch, use the built-in Defender for Endpoint dashboard in the Configuration Manager console.</span></span> <span data-ttu-id="344fc-205">자세한 내용은 [Endpoint용 Defender - 모니터링을 참조하세요.](https://docs.microsoft.com/configmgr/protect/deploy-use/windows-defender-advanced-threat-protection#monitor)</span><span class="sxs-lookup"><span data-stu-id="344fc-205">For more information, see [Defender for Endpoint - Monitor](https://docs.microsoft.com/configmgr/protect/deploy-use/windows-defender-advanced-threat-protection#monitor).</span></span>

<span data-ttu-id="344fc-206">R2 구성 관리자를 System Center 2012 모니터링은 다음 두 부분으로 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="344fc-206">If you're using System Center 2012 R2 Configuration Manager, monitoring consists of two parts:</span></span>

1. <span data-ttu-id="344fc-207">구성 패키지가 올바르게 배포되어 네트워크의 디바이스에서 실행 중(또는 성공적으로 실행) 확인</span><span class="sxs-lookup"><span data-stu-id="344fc-207">Confirming the configuration package has been correctly deployed and is running (or has successfully run) on the devices in your network.</span></span>

2. <span data-ttu-id="344fc-208">장치가 Endpoint용 Defender 서비스를 준수하는지 확인합니다(장치가 온보딩 프로세스를 완료하고 서비스에 데이터를 계속 보고할 수 있도록 보장).</span><span class="sxs-lookup"><span data-stu-id="344fc-208">Checking that the devices are compliant with the Defender for Endpoint service (this ensures the device can complete the onboarding process and can continue to report data to the service).</span></span>

### <a name="confirm-the-configuration-package-has-been-correctly-deployed"></a><span data-ttu-id="344fc-209">구성 패키지가 올바르게 배포되어 있는지 확인</span><span class="sxs-lookup"><span data-stu-id="344fc-209">Confirm the configuration package has been correctly deployed</span></span>

1. <span data-ttu-id="344fc-210">Configuration Manager 콘솔에서  탐색 창 아래쪽의 모니터링을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="344fc-210">In the Configuration Manager console, click **Monitoring** at the bottom of the navigation pane.</span></span>

2. <span data-ttu-id="344fc-211">**개요를** 선택한 다음 배포 **를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="344fc-211">Select **Overview** and then **Deployments**.</span></span>

3. <span data-ttu-id="344fc-212">패키지 이름이 있는 배포에서 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="344fc-212">Select on the deployment with the package name.</span></span>

4. <span data-ttu-id="344fc-213">완료 통계 및 콘텐츠 **상태의** 상태 **표시기를 검토합니다.**</span><span class="sxs-lookup"><span data-stu-id="344fc-213">Review the status indicators under **Completion Statistics** and **Content Status**.</span></span>

    <span data-ttu-id="344fc-214">배포에 실패한 **경우(오류,** 요구 사항이 충족되지 않은 장치 **또는** 실패 상태인 **장치)** 장치 문제를 해결해야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="344fc-214">If there are failed deployments (devices with **Error**, **Requirements Not Met**, or **Failed statuses**), you may need to  troubleshoot the devices.</span></span> <span data-ttu-id="344fc-215">자세한 내용은 Endpoint 온보딩 문제에 [대한 Microsoft Defender 문제 해결을 참조하세요.](troubleshoot-onboarding.md)</span><span class="sxs-lookup"><span data-stu-id="344fc-215">For more information, see, [Troubleshoot Microsoft Defender for Endpoint onboarding issues](troubleshoot-onboarding.md).</span></span>

    ![오류 없는 성공적인 배포를 보여주는 Configuration Manager](images/sccm-deployment.png)

### <a name="check-that-the-devices-are-compliant-with-the-microsoft-defender-atp-service"></a><span data-ttu-id="344fc-217">장치가 Microsoft Defender ATP 서비스를 준수하는지 확인</span><span class="sxs-lookup"><span data-stu-id="344fc-217">Check that the devices are compliant with the Microsoft Defender ATP service</span></span>

<span data-ttu-id="344fc-218">R2 Configuration Manager에서 구성 항목에 대한 준수 규칙을 System Center 2012 배포를 모니터링할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="344fc-218">You can set a compliance rule for configuration item in System Center 2012 R2 Configuration Manager to monitor your deployment.</span></span>

<span data-ttu-id="344fc-219">이 규칙은  대상 디바이스에서 레지스트리 키 값을 모니터링하는 수정되지 않는 준수 규칙 구성 항목입니다.</span><span class="sxs-lookup"><span data-stu-id="344fc-219">This rule should be a *non-remediating* compliance rule configuration item that monitors the value of a registry key on targeted devices.</span></span>

<span data-ttu-id="344fc-220">다음 레지스트리 키 항목을 모니터링합니다.</span><span class="sxs-lookup"><span data-stu-id="344fc-220">Monitor the following registry key entry:</span></span>

```console
Path: "HKLM\SOFTWARE\Microsoft\Windows Advanced Threat Protection\Status"
Name: "OnboardingState"
Value: "1"
```

<span data-ttu-id="344fc-221">자세한 내용은 R2 Configuration Manager의 규정 준수 System Center 2012 [소개를 참조하세요.](https://docs.microsoft.com/previous-versions/system-center/system-center-2012-R2/gg682139\(v=technet.10\))</span><span class="sxs-lookup"><span data-stu-id="344fc-221">For more information, see [Introduction to compliance settings in System Center 2012 R2 Configuration Manager](https://docs.microsoft.com/previous-versions/system-center/system-center-2012-R2/gg682139\(v=technet.10\)).</span></span>

## <a name="related-topics"></a><span data-ttu-id="344fc-222">관련 항목</span><span class="sxs-lookup"><span data-stu-id="344fc-222">Related topics</span></span>
- [<span data-ttu-id="344fc-223">그룹 정책을 사용하여 Windows 10 장치 온보드</span><span class="sxs-lookup"><span data-stu-id="344fc-223">Onboard Windows 10 devices using Group Policy</span></span>](configure-endpoints-gp.md)
- [<span data-ttu-id="344fc-224">모바일 장치 관리 도구를 사용하여 Windows 10 장치 온보딩</span><span class="sxs-lookup"><span data-stu-id="344fc-224">Onboard Windows 10 devices using Mobile Device Management tools</span></span>](configure-endpoints-mdm.md)
- [<span data-ttu-id="344fc-225">로컬 스크립트를 사용하여 Windows 10 장치 온보딩</span><span class="sxs-lookup"><span data-stu-id="344fc-225">Onboard Windows 10 devices using a local script</span></span>](configure-endpoints-script.md)
- [<span data-ttu-id="344fc-226">비영구 가상 데스크톱 인프라(VDI) 장치 온보딩</span><span class="sxs-lookup"><span data-stu-id="344fc-226">Onboard non-persistent virtual desktop infrastructure (VDI) devices</span></span>](configure-endpoints-vdi.md)
- [<span data-ttu-id="344fc-227">새로 온보딩된 Microsoft Defender ATP 장치에서 검색 테스트 실행</span><span class="sxs-lookup"><span data-stu-id="344fc-227">Run a detection test on a newly onboarded Microsoft Defender ATP device</span></span>](run-detection-test.md)
- [<span data-ttu-id="344fc-228">끝점 온보딩 문제에 대한 Microsoft Defender 문제 해결</span><span class="sxs-lookup"><span data-stu-id="344fc-228">Troubleshoot Microsoft Defender for Endpoint onboarding issues</span></span>](troubleshoot-onboarding.md)
