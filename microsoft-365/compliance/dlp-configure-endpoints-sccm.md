---
title: 구성 관리자를 사용하여 Windows 10 장치 온보딩
f1.keywords: NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
search.appverid:
- MET150
description: Configuration Manager를 사용하여 장치에 구성 패키지를 배포하여 서비스에 온보드합니다.
ms.openlocfilehash: d2db35e50d31a0a19076965da6dcecf9cfeef826
ms.sourcegitcommit: 48195345b21b409b175d68acdc25d9f2fc4fc5f1
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/30/2021
ms.locfileid: "53226900"
---
# <a name="onboard-windows-10-devices-using-configuration-manager"></a><span data-ttu-id="c06ae-103">구성 관리자를 사용하여 Windows 10 장치 온보딩</span><span class="sxs-lookup"><span data-stu-id="c06ae-103">Onboard Windows 10 devices using Configuration Manager</span></span>

<span data-ttu-id="c06ae-104">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="c06ae-104">**Applies to:**</span></span>

- [<span data-ttu-id="c06ae-105">Microsoft 365 끝점 DLP(데이터 손실 방지)</span><span class="sxs-lookup"><span data-stu-id="c06ae-105">Microsoft 365 Endpoint data loss prevention (DLP)</span></span>](./endpoint-dlp-learn-about.md)
- <span data-ttu-id="c06ae-106">System Center 2012 R2 Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="c06ae-106">System Center 2012 R2 Configuration Manager</span></span>

### <a name="onboard-devices-using-system-center-configuration-manager"></a><span data-ttu-id="c06ae-107">장치를 사용하여 온보드 System Center Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="c06ae-107">Onboard devices using System Center Configuration Manager</span></span>

1. <span data-ttu-id="c06ae-108">서비스 온보더링 마법사에서 \*\* 다운로드한 .zip(DeviceComplianceOnboardingPackage.zip)를 구성 관리자 구성 패키지 패키지를 열 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c06ae-108">Open the Configuration Manager configuration package .zip file (*DeviceComplianceOnboardingPackage.zip*) that you downloaded from the service onboarding wizard.</span></span> <span data-ttu-id="c06ae-109">Microsoft 준수 센터에서 [패키지를 다운로드할 수 있습니다.](https://compliance.microsoft.com/)</span><span class="sxs-lookup"><span data-stu-id="c06ae-109">You can also get the package from [Microsoft Compliance center](https://compliance.microsoft.com/).</span></span>

2. <span data-ttu-id="c06ae-110">탐색 창에서 장치 **온보 설정**  >  **를**  >  **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="c06ae-110">In the navigation pane, select **Settings** > **Device Onboarding** > **Onboarding**.</span></span>

3. <span data-ttu-id="c06ae-111">배포 **방법 필드에서** **2012/Microsoft Endpoint Configuration Manager R2/1511/1602를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="c06ae-111">In the **Deployment method** field, select **Microsoft Endpoint Configuration Manager 2012/2012 R2/1511/1602**.</span></span>

4. <span data-ttu-id="c06ae-112">패키지 **다운로드를** 선택하고 파일 .zip 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="c06ae-112">Select **Download package**, and save the .zip file.</span></span>

5. <span data-ttu-id="c06ae-113">패키지를 배포할 네트워크 관리자가 액세스할 수 있는 .zip 공유 읽기 전용 위치로 파일 파일의 내용을 추출합니다.</span><span class="sxs-lookup"><span data-stu-id="c06ae-113">Extract the contents of the .zip file to a shared, read-only location that can be accessed by the network administrators who will deploy the package.</span></span> <span data-ttu-id="c06ae-114">*DeviceComplianceOnboardingScript.cmd라는 파일이 필요합니다.*</span><span class="sxs-lookup"><span data-stu-id="c06ae-114">You should have a file named *DeviceComplianceOnboardingScript.cmd*.</span></span>

6. <span data-ttu-id="c06ae-115">System Center [R2 Configuration Manager](/previous-versions/system-center/system-center-2012-R2/gg699369(v=technet.10)) 문서의 단계에 따라 패키지를 배포합니다.</span><span class="sxs-lookup"><span data-stu-id="c06ae-115">Deploy the package by following the steps in the [Packages and Programs in System Center 2012 R2 Configuration Manager](/previous-versions/system-center/system-center-2012-R2/gg699369(v=technet.10)) article.</span></span>

7. <span data-ttu-id="c06ae-116">패키지를 배포할 미리 정의한 장치 컬렉션을 선택하십시오.</span><span class="sxs-lookup"><span data-stu-id="c06ae-116">Choose a predefined device collection to deploy the package to.</span></span>

> [!NOTE]
> <span data-ttu-id="c06ae-117">Microsoft 365 끝점 데이터 손실 방지는 [OOBE(첫](https://answers.microsoft.com/en-us/windows/wiki/windows_10/how-to-complete-the-windows-10-out-of-box/47e3f943-f000-45e3-8c5c-9d85a1a0cf87) 번째 경험) 단계 동안의 온보더링을 지원하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c06ae-117">Microsoft 365 Endpoint data loss prevention doesn't support onboarding during the [Out-Of-Box Experience (OOBE)](https://answers.microsoft.com/en-us/windows/wiki/windows_10/how-to-complete-the-windows-10-out-of-box/47e3f943-f000-45e3-8c5c-9d85a1a0cf87) phase.</span></span> <span data-ttu-id="c06ae-118">설치 또는 업그레이드를 실행한 후 사용자가 OOBE를 Windows 합니다.</span><span class="sxs-lookup"><span data-stu-id="c06ae-118">Make sure users complete OOBE after running Windows installation or upgrading.</span></span>

> [!TIP]
> <span data-ttu-id="c06ae-119">장치를 온보드한 후 검색 테스트를 실행하여 장치가 서비스에 제대로 온보드되었는지 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c06ae-119">After onboarding the device, you can choose to run a detection test to verify that an device is properly onboarded to the service.</span></span> <span data-ttu-id="c06ae-120">자세한 내용은 새로 온보딩된 끝점 디바이스용 Microsoft Defender에서 검색 테스트 [실행을 참조하세요.](/windows/security/threat-protection/microsoft-defender-atp/run-detection-test)</span><span class="sxs-lookup"><span data-stu-id="c06ae-120">For more information, see [Run a detection test on a newly onboarded Microsoft Defender for Endpoint device](/windows/security/threat-protection/microsoft-defender-atp/run-detection-test).</span></span>
>
> <span data-ttu-id="c06ae-121">Configuration Manager 응용 프로그램에 검색 규칙을 만들어 장치가 지속적으로 온보더된지 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c06ae-121">Note that it is possible to create a detection rule on a Configuration Manager application to continuously check if a device has been onboarded.</span></span> <span data-ttu-id="c06ae-122">응용 프로그램은 패키지 및 프로그램과 다른 유형의 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="c06ae-122">An application is a different type of object than a package and program.</span></span>
> <span data-ttu-id="c06ae-123">장치가 아직 온보드되지 않은 경우(보류 중인 OOBE 완료 또는 다른 이유로 인해) 규칙에서 상태 변경이 감지될 때까지 Configuration Manager가 디바이스를 다시 시도합니다.</span><span class="sxs-lookup"><span data-stu-id="c06ae-123">If a device is not yet onboarded (due to pending OOBE completion or any other reason), Configuration Manager will retry to onboard the device until the rule detects the status change.</span></span>
>
> <span data-ttu-id="c06ae-124">이 동작은 "OnboardingState" 레지스트리 값(형식이 REG_DWORD) = 1이면 검색 규칙을 만들어 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c06ae-124">This behavior can be accomplished by creating a detection rule checking if the "OnboardingState" registry value (of type REG_DWORD) = 1.</span></span>
> <span data-ttu-id="c06ae-125">이 레지스트리 값은 "HKLM\SOFTWARE\Microsoft\Windows Advanced Threat Protection\Status" 아래에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c06ae-125">This registry value is located under "HKLM\SOFTWARE\Microsoft\Windows Advanced Threat Protection\Status".</span></span>
<span data-ttu-id="c06ae-126">자세한 내용은 [Configure Detection Methods in System Center 2012 R2 Configuration Manager을 참조하십시오.](/previous-versions/system-center/system-center-2012-R2/gg682159(v=technet.10)#step-4-configure-detection-methods-to-indicate-the-presence-of-the-deployment-type)</span><span class="sxs-lookup"><span data-stu-id="c06ae-126">For more information, see [Configure Detection Methods in System Center 2012 R2 Configuration Manager](/previous-versions/system-center/system-center-2012-R2/gg682159(v=technet.10)#step-4-configure-detection-methods-to-indicate-the-presence-of-the-deployment-type).</span></span>

### <a name="configure-sample-collection-settings"></a><span data-ttu-id="c06ae-127">샘플 수집 설정 구성</span><span class="sxs-lookup"><span data-stu-id="c06ae-127">Configure sample collection settings</span></span>

<span data-ttu-id="c06ae-128">각 디바이스에 대해 심층 분석을 위해 파일을 제출하기 위해 요청을 할 때 장치에서 샘플을 수집할 수 있는지 여부를 Microsoft Defender 보안 센터 구성 값을 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c06ae-128">For each device, you can set a configuration value to state whether samples can be collected from the device when a request is made through Microsoft Defender Security Center to submit a file for deep analysis.</span></span>

> [!NOTE]
> <span data-ttu-id="c06ae-129">이러한 구성 설정은 일반적으로 Configuration Manager를 통해 수행됩니다.</span><span class="sxs-lookup"><span data-stu-id="c06ae-129">These configuration settings are typically done through Configuration Manager.</span></span>

<span data-ttu-id="c06ae-130">Configuration Manager에서 구성 항목에 대한 준수 규칙을 설정하여 장치에서 샘플 공유 설정을 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c06ae-130">You can set a compliance rule for configuration item in Configuration Manager to change the sample share setting on a device.</span></span>

<span data-ttu-id="c06ae-131">이 규칙은  불만이 있는지 확인하도록 대상 디바이스의 레지스트리 키 값을 설정하는 수정 준수 규칙 구성 항목입니다.</span><span class="sxs-lookup"><span data-stu-id="c06ae-131">This rule should be a *remediating* compliance rule configuration item that sets the value of a registry key on targeted devices to make sure they’re complaint.</span></span>

<span data-ttu-id="c06ae-132">구성은 다음 레지스트리 키 항목을 통해 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="c06ae-132">The configuration is set through the following registry key entry:</span></span>

```
Path: “HKLM\SOFTWARE\Policies\Microsoft\Windows Advanced Threat Protection”
Name: "AllowSampleCollection"
Value: 0 or 1
```
<span data-ttu-id="c06ae-133">여기서,</span><span class="sxs-lookup"><span data-stu-id="c06ae-133">Where:</span></span><br>
<span data-ttu-id="c06ae-134">키 형식은 D-WORD입니다.</span><span class="sxs-lookup"><span data-stu-id="c06ae-134">Key type is a D-WORD.</span></span> <br>
<span data-ttu-id="c06ae-135">가능한 값은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="c06ae-135">Possible values are:</span></span>
- <span data-ttu-id="c06ae-136">0 - 이 장치에서 샘플 공유를 허용하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c06ae-136">0 - doesn't allow sample sharing  from this device</span></span>
- <span data-ttu-id="c06ae-137">1 - 이 장치에서 모든 파일 형식을 공유할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c06ae-137">1 - allows sharing of all file types from this device</span></span>

<span data-ttu-id="c06ae-138">레지스트리 키가 없는 경우의 기본값은 1입니다.</span><span class="sxs-lookup"><span data-stu-id="c06ae-138">The default value in case the registry key doesn’t exist is 1.</span></span>

<span data-ttu-id="c06ae-139">규정 준수에 System Center Configuration Manager 대한 자세한 내용은 [System Center 2012 R2 Configuration Manager의](/previous-versions/system-center/system-center-2012-R2/gg682139(v=technet.10))규정 준수 설정 소개를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="c06ae-139">For more information about System Center Configuration Manager Compliance, see [Introduction to compliance settings in System Center 2012 R2 Configuration Manager](/previous-versions/system-center/system-center-2012-R2/gg682139(v=technet.10)).</span></span>


## <a name="other-recommended-configuration-settings"></a><span data-ttu-id="c06ae-140">기타 권장 구성 설정</span><span class="sxs-lookup"><span data-stu-id="c06ae-140">Other recommended configuration settings</span></span>
<span data-ttu-id="c06ae-141">장치를 서비스에 온보드한 후 다음과 같은 권장 구성 설정을 사용하여 포함된 위협 방지 기능을 활용하는 것이 중요합니다.</span><span class="sxs-lookup"><span data-stu-id="c06ae-141">After onboarding devices to the service, it's important to take advantage of the included threat protection capabilities by enabling them with the following recommended configuration settings.</span></span>

### <a name="device-collection-configuration"></a><span data-ttu-id="c06ae-142">장치 컬렉션 구성</span><span class="sxs-lookup"><span data-stu-id="c06ae-142">Device collection configuration</span></span>
<span data-ttu-id="c06ae-143">Endpoint Configuration Manager 버전 2002 이상을 사용하는 경우 서버 또는 다운 수준 클라이언트를 포함하기 위해 배포를 확장할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c06ae-143">If you're using Endpoint Configuration Manager, version 2002 or later, you can choose to broaden the deployment to include servers or down-level clients.</span></span>


### <a name="next-generation-protection-configuration"></a><span data-ttu-id="c06ae-144">차세대 보호 구성</span><span class="sxs-lookup"><span data-stu-id="c06ae-144">Next generation protection configuration</span></span>

<span data-ttu-id="c06ae-145">권장되는 구성 설정은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="c06ae-145">The following configuration settings are recommended:</span></span>

<span data-ttu-id="c06ae-146">**스캔**</span><span class="sxs-lookup"><span data-stu-id="c06ae-146">**Scan**</span></span>

- <span data-ttu-id="c06ae-147">USB 드라이브와 같은 이동식 저장 장치 검색: 예</span><span class="sxs-lookup"><span data-stu-id="c06ae-147">Scan removable storage devices such as USB drives: Yes</span></span>

<span data-ttu-id="c06ae-148">**실시간 보호**</span><span class="sxs-lookup"><span data-stu-id="c06ae-148">**Real-time Protection**</span></span>

- <span data-ttu-id="c06ae-149">동작 모니터링 사용: 예</span><span class="sxs-lookup"><span data-stu-id="c06ae-149">Enable Behavioral Monitoring: Yes</span></span>
- <span data-ttu-id="c06ae-150">다운로드할 때 및 설치 전에 사용자방지 응용 프로그램으로부터 보호 사용: 예</span><span class="sxs-lookup"><span data-stu-id="c06ae-150">Enable protection against Potentially Unwanted Applications at download and prior to installation: Yes</span></span>

<span data-ttu-id="c06ae-151">**클라우드 보호 서비스**</span><span class="sxs-lookup"><span data-stu-id="c06ae-151">**Cloud Protection Service**</span></span>

- <span data-ttu-id="c06ae-152">클라우드 보호 서비스 멤버십 유형: 고급 멤버십</span><span class="sxs-lookup"><span data-stu-id="c06ae-152">Cloud Protection Service membership type: Advanced membership</span></span>

<span data-ttu-id="c06ae-153">**공격 표면 감소** 사용 가능한 모든 규칙을 감사로 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="c06ae-153">**Attack surface reduction** Configure all available rules to Audit.</span></span>

> [!NOTE]
> <span data-ttu-id="c06ae-154">이러한 활동을 차단하면 합법적인 비즈니스 프로세스가 중단될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c06ae-154">Blocking these activities may interrupt legitimate business processes.</span></span> <span data-ttu-id="c06ae-155">가장 좋은 방법은 모든 것을 감사로 설정하고, 켜기에 안전한 설정을 식별한 다음, 가짓 긍정 검색이 없는 끝점에서 해당 설정을 사용하도록 설정하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="c06ae-155">The best approach is setting everything to audit, identifying which ones are safe to turn on, and then enabling those settings on endpoints which do not have false positive detections.</span></span>

<span data-ttu-id="c06ae-156">**네트워크 보호**</span><span class="sxs-lookup"><span data-stu-id="c06ae-156">**Network protection**</span></span>

<span data-ttu-id="c06ae-157">감사 또는 차단 모드에서 네트워크 보호를 사용하도록 설정하기 전에 지원 페이지에서 얻을 수 있는 맬웨어 방지 플랫폼 업데이트를 설치해야 [합니다.](https://support.microsoft.com/en-us/help/4560203/windows-defender-anti-malware-platform-binaries-are-missing)</span><span class="sxs-lookup"><span data-stu-id="c06ae-157">Prior to enabling network protection in audit or block mode, ensure that you've installed the antimalware platform update, which can be obtained from the [support page](https://support.microsoft.com/en-us/help/4560203/windows-defender-anti-malware-platform-binaries-are-missing).</span></span>


<span data-ttu-id="c06ae-158">**제어된 폴더 액세스**</span><span class="sxs-lookup"><span data-stu-id="c06ae-158">**Controlled folder access**</span></span>

<span data-ttu-id="c06ae-159">감사 모드에서 기능을 30일 이상 사용하도록 설정</span><span class="sxs-lookup"><span data-stu-id="c06ae-159">Enable the feature in audit mode for at least 30 days.</span></span> <span data-ttu-id="c06ae-160">이 기간이 지난 후 검색을 검토하고 보호된 Director에 쓸 수 있는 응용 프로그램 목록을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="c06ae-160">After this period, review detections and create a list of applications that are allowed to write to protected directories.</span></span>

<span data-ttu-id="c06ae-161">자세한 내용은 제어된 폴더 [액세스 평가를 참조하세요.](/windows/security/threat-protection/microsoft-defender-atp/evaluate-controlled-folder-access)</span><span class="sxs-lookup"><span data-stu-id="c06ae-161">For more information, see [Evaluate controlled folder access](/windows/security/threat-protection/microsoft-defender-atp/evaluate-controlled-folder-access).</span></span>


## <a name="offboard-devices-using-configuration-manager"></a><span data-ttu-id="c06ae-162">Configuration Manager를 사용하여 디바이스 오프보드</span><span class="sxs-lookup"><span data-stu-id="c06ae-162">Offboard devices using Configuration Manager</span></span>

<span data-ttu-id="c06ae-163">보안상의 이유로, 오프보드 장치에 사용된 패키지는 다운로드한 날짜 30일 후에 만료됩니다.</span><span class="sxs-lookup"><span data-stu-id="c06ae-163">For security reasons, the package used to Offboard devices will expire 30 days after the date it was downloaded.</span></span> <span data-ttu-id="c06ae-164">장치에 전송된 만료된 오프보더 패키지는 거부됩니다.</span><span class="sxs-lookup"><span data-stu-id="c06ae-164">Expired offboarding packages sent to a device will be rejected.</span></span> <span data-ttu-id="c06ae-165">오프보더 패키지를 다운로드할 때 패키지 만료 날짜에 대한 알림을 하게 되고 패키지 이름에도 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="c06ae-165">When downloading an offboarding package, you will be notified of the packages expiry date and it will also be included in the package name.</span></span>

> [!NOTE]
> <span data-ttu-id="c06ae-166">온보드 및 오프보더 정책을 동일한 장치에 동시에 배포하면 안 됩니다. 그렇지 않으면 예측할 수 없는 충돌이 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c06ae-166">Onboarding and offboarding policies must not be deployed on the same device at the same time, otherwise this will cause unpredictable collisions.</span></span>

### <a name="offboard-devices-using-microsoft-endpoint-configuration-manager-current-branch"></a><span data-ttu-id="c06ae-167">현재 분기를 사용하여 Microsoft Endpoint Configuration Manager 오프보드</span><span class="sxs-lookup"><span data-stu-id="c06ae-167">Offboard devices using Microsoft Endpoint Configuration Manager current branch</span></span>

<span data-ttu-id="c06ae-168">현재 분기를 Microsoft Endpoint Configuration Manager 경우 [오프보링 구성 파일 만들기를 참조합니다.](/configmgr/protect/deploy-use/windows-defender-advanced-threat-protection#create-an-offboarding-configuration-file)</span><span class="sxs-lookup"><span data-stu-id="c06ae-168">If you use Microsoft Endpoint Configuration Manager current branch, see [Create an offboarding configuration file](/configmgr/protect/deploy-use/windows-defender-advanced-threat-protection#create-an-offboarding-configuration-file).</span></span>

### <a name="offboard-devices-using-system-center-2012-r2-configuration-manager"></a><span data-ttu-id="c06ae-169">System Center 2012 R2 Configuration Manager를 사용하여 장치 오프보드</span><span class="sxs-lookup"><span data-stu-id="c06ae-169">Offboard devices using System Center 2012 R2 Configuration Manager</span></span>

1. <span data-ttu-id="c06ae-170">Microsoft 준수 센터에서 오프보더 [패키지를 다운로드합니다.](https://compliance.microsoft.com/)</span><span class="sxs-lookup"><span data-stu-id="c06ae-170">Get the offboarding package from [Microsoft Compliance center](https://compliance.microsoft.com/):</span></span>

2. <span data-ttu-id="c06ae-171">탐색 창에서 장치 **온보 설정** 해제를  >    >  **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="c06ae-171">In the navigation pane, select **Settings** >  **Device onboarding**> **Offboarding**.</span></span>

3. <span data-ttu-id="c06ae-172">운영 Windows 10 로 실행을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="c06ae-172">Select Windows 10 as the operating system.</span></span>

4. <span data-ttu-id="c06ae-173">배포 **방법 필드에서** **2012/Microsoft Endpoint Configuration Manager R2/1511/1602를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="c06ae-173">In the **Deployment method** field, select **Microsoft Endpoint Configuration Manager 2012/2012 R2/1511/1602**.</span></span>

5. <span data-ttu-id="c06ae-174">패키지 **다운로드를** 선택하고 파일 .zip 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="c06ae-174">Select **Download package**, and save the .zip file.</span></span>

6. <span data-ttu-id="c06ae-175">패키지를 배포할 네트워크 관리자가 액세스할 수 있는 .zip 공유 읽기 전용 위치로 파일 파일의 내용을 추출합니다.</span><span class="sxs-lookup"><span data-stu-id="c06ae-175">Extract the contents of the .zip file to a shared, read-only location that can be accessed by the network administrators who will deploy the package.</span></span> <span data-ttu-id="c06ae-176">이름이 *DeviceComplianceOffboardingScript_valid_until_YYYY-MM-DD.cmd 입니다.*</span><span class="sxs-lookup"><span data-stu-id="c06ae-176">You should have a file named *DeviceComplianceOffboardingScript_valid_until_YYYY-MM-DD.cmd*.</span></span>

7. <span data-ttu-id="c06ae-177">System Center [R2 Configuration Manager](/previous-versions/system-center/system-center-2012-R2/gg699369(v=technet.10)) 문서의 단계에 따라 패키지를 배포합니다.</span><span class="sxs-lookup"><span data-stu-id="c06ae-177">Deploy the package by following the steps in the [Packages and Programs in System Center 2012 R2 Configuration Manager](/previous-versions/system-center/system-center-2012-R2/gg699369(v=technet.10)) article.</span></span>

8. <span data-ttu-id="c06ae-178">패키지를 배포할 미리 정의한 장치 컬렉션을 선택하십시오.</span><span class="sxs-lookup"><span data-stu-id="c06ae-178">Choose a predefined device collection to deploy the package to.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="c06ae-179">오프보더링을 통해 디바이스가 포털에 센서 데이터 전송을 중지하지만, 디바이스에서 전송한 모든 경고에 대한 참조를 포함하여 장치의 데이터는 최대 6개월 동안 보존됩니다.</span><span class="sxs-lookup"><span data-stu-id="c06ae-179">Offboarding causes the device to stop sending sensor data to the portal but data from the device, including reference to any alerts it has had will be retained for up to 6 months.</span></span>


## <a name="monitor-device-configuration"></a><span data-ttu-id="c06ae-180">장치 구성 모니터링</span><span class="sxs-lookup"><span data-stu-id="c06ae-180">Monitor device configuration</span></span>

<span data-ttu-id="c06ae-181">현재 분기를 Microsoft Endpoint Configuration Manager Configuration Manager 콘솔에서 기본 제공 Microsoft Defender for Endpoint 대시보드를 사용하세요.</span><span class="sxs-lookup"><span data-stu-id="c06ae-181">If you're using Microsoft Endpoint Configuration Manager current branch, use the built-in Microsoft Defender for Endpoint dashboard in the Configuration Manager console.</span></span> <span data-ttu-id="c06ae-182">자세한 내용은 [Microsoft Defender Advanced Threat Protection - 모니터링을 참조하세요.](/configmgr/protect/deploy-use/windows-defender-advanced-threat-protection#monitor)</span><span class="sxs-lookup"><span data-stu-id="c06ae-182">For more information, see [Microsoft Defender Advanced Threat Protection - Monitor](/configmgr/protect/deploy-use/windows-defender-advanced-threat-protection#monitor).</span></span>

<span data-ttu-id="c06ae-183">2012 R2 System Center 사용하는 경우 모니터링은 다음 두 부분으로 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="c06ae-183">If you're using System Center 2012 R2 Configuration Manager, monitoring consists of two parts:</span></span>

1. <span data-ttu-id="c06ae-184">구성 패키지가 올바르게 배포되어 네트워크의 디바이스에서 실행 중(또는 성공적으로 실행) 확인</span><span class="sxs-lookup"><span data-stu-id="c06ae-184">Confirming the configuration package has been correctly deployed and is running (or has successfully run) on the devices in your network.</span></span>

2. <span data-ttu-id="c06ae-185">장치가 Microsoft 365 끝점 데이터 손실 방지 서비스를 준수하는지 확인합니다(장치가 온보더링 프로세스를 완료하고 서비스에 데이터를 계속 보고할 수 있도록 보장).</span><span class="sxs-lookup"><span data-stu-id="c06ae-185">Checking that the devices are compliant with the Microsoft 365 Endpoint data loss prevention service (this ensures the device can complete the onboarding process and can continue to report data to the service).</span></span>

### <a name="confirm-the-configuration-package-has-been-correctly-deployed"></a><span data-ttu-id="c06ae-186">구성 패키지가 올바르게 배포되어 있는지 확인</span><span class="sxs-lookup"><span data-stu-id="c06ae-186">Confirm the configuration package has been correctly deployed</span></span>

1. <span data-ttu-id="c06ae-187">Configuration Manager 콘솔에서  탐색 창 아래쪽의 모니터링을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="c06ae-187">In the Configuration Manager console, click **Monitoring** at the bottom of the navigation pane.</span></span>

2. <span data-ttu-id="c06ae-188">**개요를** 선택한 다음 배포 **를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="c06ae-188">Select **Overview** and then **Deployments**.</span></span>

3. <span data-ttu-id="c06ae-189">패키지 이름이 있는 배포에서 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="c06ae-189">Select on the deployment with the package name.</span></span>

4. <span data-ttu-id="c06ae-190">완료 통계 및 콘텐츠 **상태의** 상태 **표시기를 검토합니다.**</span><span class="sxs-lookup"><span data-stu-id="c06ae-190">Review the status indicators under **Completion Statistics** and **Content Status**.</span></span>

    <span data-ttu-id="c06ae-191">배포에 실패한 **경우(오류,** 요구 사항이 충족되지 않은 장치 **또는** 실패 상태인 **장치)** 장치 문제를 해결해야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c06ae-191">If there are failed deployments (devices with **Error**, **Requirements Not Met**, or **Failed statuses**), you may need to  troubleshoot the devices.</span></span> <span data-ttu-id="c06ae-192">자세한 내용은 Microsoft [Defender Advanced Threat Protection 온보딩 문제 해결을 참조하세요.](/windows/security/threat-protection/microsoft-defender-atp/troubleshoot-onboarding)</span><span class="sxs-lookup"><span data-stu-id="c06ae-192">For more information, see, [Troubleshoot Microsoft Defender Advanced Threat Protection onboarding issues](/windows/security/threat-protection/microsoft-defender-atp/troubleshoot-onboarding).</span></span>

    ![오류 없는 성공적인 배포를 보여주는 Configuration Manager](../media/sccm-deployment.png)

### <a name="check-that-the-devices-are-compliant-with-the-microsoft-365-endpoint-data-loss-prevention-service"></a><span data-ttu-id="c06ae-194">장치가 끝점 데이터 손실 방지 Microsoft 365 준수하는지 확인</span><span class="sxs-lookup"><span data-stu-id="c06ae-194">Check that the devices are compliant with the Microsoft 365 Endpoint data loss prevention service</span></span>

<span data-ttu-id="c06ae-195">System Center 2012 R2 Configuration Manager에서 구성 항목에 대한 준수 규칙을 설정하여 배포를 모니터링할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c06ae-195">You can set a compliance rule for configuration item in System Center 2012 R2 Configuration Manager to monitor your deployment.</span></span>

> [!NOTE]
> <span data-ttu-id="c06ae-196">이 절차 및 레지스트리 항목은 Endpoint DLP 및 Advanced Threat Protection에 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="c06ae-196">This procedure and registry entry applies to Endpoint DLP as well as Advanced Threat Protection.</span></span>

<span data-ttu-id="c06ae-197">이 규칙은  대상 디바이스에서 레지스트리 키 값을 모니터링하는 수정되지 않는 준수 규칙 구성 항목입니다.</span><span class="sxs-lookup"><span data-stu-id="c06ae-197">This rule should be a *non-remediating* compliance rule configuration item that monitors the value of a registry key on targeted devices.</span></span>

<span data-ttu-id="c06ae-198">다음 레지스트리 키 항목을 모니터링합니다.</span><span class="sxs-lookup"><span data-stu-id="c06ae-198">Monitor the following registry key entry:</span></span>
```
Path: “HKLM\SOFTWARE\Microsoft\Windows Advanced Threat Protection\Status”
Name: “OnboardingState”
Value: “1”
```
<span data-ttu-id="c06ae-199">자세한 내용은 [System Center 2012 R2 Configuration Manager의](/previous-versions/system-center/system-center-2012-R2/gg682139(v=technet.10))규정 준수 설정 소개를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="c06ae-199">For more information, see [Introduction to compliance settings in System Center 2012 R2 Configuration Manager](/previous-versions/system-center/system-center-2012-R2/gg682139(v=technet.10)).</span></span>

## <a name="related-topics"></a><span data-ttu-id="c06ae-200">관련 항목</span><span class="sxs-lookup"><span data-stu-id="c06ae-200">Related topics</span></span>
- [<span data-ttu-id="c06ae-201">그룹 정책을 Windows 10 장치 온보드</span><span class="sxs-lookup"><span data-stu-id="c06ae-201">Onboard Windows 10 devices using Group Policy</span></span>](dlp-configure-endpoints-gp.md)
- [<span data-ttu-id="c06ae-202">모바일 장치 관리 도구를 사용하여 Windows 10 장치 온보딩</span><span class="sxs-lookup"><span data-stu-id="c06ae-202">Onboard Windows 10 devices using Mobile Device Management tools</span></span>](dlp-configure-endpoints-mdm.md)
- [<span data-ttu-id="c06ae-203">로컬 스크립트를 사용하여 Windows 10 장치 온보딩</span><span class="sxs-lookup"><span data-stu-id="c06ae-203">Onboard Windows 10 devices using a local script</span></span>](dlp-configure-endpoints-script.md)
- [<span data-ttu-id="c06ae-204">비영구 VDI(가상 데스크톱 인프라) 장치 온보딩</span><span class="sxs-lookup"><span data-stu-id="c06ae-204">Onboard non-persistent virtual desktop infrastructure (VDI) devices</span></span>](dlp-configure-endpoints-vdi.md)
- [<span data-ttu-id="c06ae-205">새로 온보딩된 엔드포인트 디바이스용 Microsoft Defender에서 검색 테스트 실행</span><span class="sxs-lookup"><span data-stu-id="c06ae-205">Run a detection test on a newly onboarded Microsoft Defender for Endpoint device</span></span>](/windows/security/threat-protection/microsoft-defender-atp/run-detection-test)
- [<span data-ttu-id="c06ae-206">Microsoft Defender Advanced Threat Protection 온보딩 문제 해결</span><span class="sxs-lookup"><span data-stu-id="c06ae-206">Troubleshoot Microsoft Defender Advanced Threat Protection onboarding issues</span></span>](/windows/security/threat-protection/microsoft-defender-atp/troubleshoot-onboarding)