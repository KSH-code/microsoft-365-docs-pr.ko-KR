---
title: Configuration Manager를 사용 하는 온보드 Windows 10 장치
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
description: Configuration Manager를 사용 하 여 장치에 구성 패키지를 배포 하 여 서비스에 등록 되도록 합니다.
ms.openlocfilehash: ea1b0cba10dc3e7120192e0c0ee87e2e354f1cc2
ms.sourcegitcommit: 6647055154002c7d3b8f7ce25ad53c9636bc8066
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2020
ms.locfileid: "48769476"
---
# <a name="onboard-windows-10-devices-using-configuration-manager"></a><span data-ttu-id="68cdf-103">Configuration Manager를 사용 하는 온보드 Windows 10 장치</span><span class="sxs-lookup"><span data-stu-id="68cdf-103">Onboard Windows 10 devices using Configuration Manager</span></span>

<span data-ttu-id="68cdf-104">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="68cdf-104">**Applies to:**</span></span>

- [<span data-ttu-id="68cdf-105">Microsoft 365 Endpoint data 손실 방지 (DLP)</span><span class="sxs-lookup"><span data-stu-id="68cdf-105">Microsoft 365 Endpoint data loss prevention (DLP)</span></span>](/microsoft-365/compliance/endpoint-dlp-learn-about)
- <span data-ttu-id="68cdf-106">System Center 2012 R2 Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="68cdf-106">System Center 2012 R2 Configuration Manager</span></span>

### <a name="onboard-devices-using-system-center-configuration-manager"></a><span data-ttu-id="68cdf-107">System Center Configuration Manager를 사용 하는 온보드 장치</span><span class="sxs-lookup"><span data-stu-id="68cdf-107">Onboard devices using System Center Configuration Manager</span></span>

1. <span data-ttu-id="68cdf-108">서비스 온 보 딩 마법사에서 다운로드 한 Configuration Manager 구성 패키지 .zip 파일 ( *DeviceComplianceOnboardingPackage.zip* )을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="68cdf-108">Open the Configuration Manager configuration package .zip file ( *DeviceComplianceOnboardingPackage.zip* ) that you downloaded from the service onboarding wizard.</span></span> <span data-ttu-id="68cdf-109">[Microsoft 준수 센터](https://compliance.microsoft.com/)에서 패키지를 가져올 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="68cdf-109">You can also get the package from [Microsoft Compliance center](https://compliance.microsoft.com/).</span></span>

2. <span data-ttu-id="68cdf-110">탐색 창에서 **설정**  >  **장치 온 보**  >  **딩 온** 을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="68cdf-110">In the navigation pane, select **Settings** > **Device Onboarding** > **Onboarding** .</span></span>

3. <span data-ttu-id="68cdf-111">**배포 방법** 필드에서 **Microsoft Endpoint Configuration Manager 2012/2012 R2/1511/1602** 을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="68cdf-111">In the **Deployment method** field, select **Microsoft Endpoint Configuration Manager 2012/2012 R2/1511/1602** .</span></span>
 
4. <span data-ttu-id="68cdf-112">**패키지 다운로드** 를 선택 하 고 .zip 파일을 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="68cdf-112">Select **Download package** , and save the .zip file.</span></span>

5. <span data-ttu-id="68cdf-113">패키지를 배포할 네트워크 관리자가 액세스할 수 있는 공유, 읽기 전용 위치에 .zip 파일의 내용을 추출 합니다.</span><span class="sxs-lookup"><span data-stu-id="68cdf-113">Extract the contents of the .zip file to a shared, read-only location that can be accessed by the network administrators who will deploy the package.</span></span> <span data-ttu-id="68cdf-114">*Devicecomplianceonboardingscript* 라는 파일이 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="68cdf-114">You should have a file named *DeviceComplianceOnboardingScript.cmd* .</span></span>

6. <span data-ttu-id="68cdf-115">[System Center 2012 R2 Configuration Manager 문서의 패키지 및 프로그램](https://docs.microsoft.com/previous-versions/system-center/system-center-2012-R2/gg699369\(v=technet.10\)) 에 나와 있는 단계에 따라 패키지를 배포 합니다.</span><span class="sxs-lookup"><span data-stu-id="68cdf-115">Deploy the package by following the steps in the [Packages and Programs in System Center 2012 R2 Configuration Manager](https://docs.microsoft.com/previous-versions/system-center/system-center-2012-R2/gg699369\(v=technet.10\)) article.</span></span>

7. <span data-ttu-id="68cdf-116">패키지를 배포할 미리 정의 된 장치 모음을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="68cdf-116">Choose a predefined device collection to deploy the package to.</span></span>

> [!NOTE]
> <span data-ttu-id="68cdf-117">Microsoft 365 Endpoint data 손실 방지는 [OOBE (기본 제공 경험)](https://answers.microsoft.com/en-us/windows/wiki/windows_10/how-to-complete-the-windows-10-out-of-box/47e3f943-f000-45e3-8c5c-9d85a1a0cf87) 단계 중에 온 보 딩을 지원 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="68cdf-117">Microsoft 365 Endpoint data loss prevention doesn't support onboarding during the [Out-Of-Box Experience (OOBE)](https://answers.microsoft.com/en-us/windows/wiki/windows_10/how-to-complete-the-windows-10-out-of-box/47e3f943-f000-45e3-8c5c-9d85a1a0cf87) phase.</span></span> <span data-ttu-id="68cdf-118">Windows 설치 또는 업그레이드를 실행 한 후 사용자에 게 OOBE가 완료 되었는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="68cdf-118">Make sure users complete OOBE after running Windows installation or upgrading.</span></span>

>[!TIP]
> <span data-ttu-id="68cdf-119">장치를 온 보 딩 한 후에는 검색 테스트를 실행 하 여 장치가 제대로 등록 서비스에 올바르게 작동 하는지 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="68cdf-119">After onboarding the device, you can choose to run a detection test to verify that an device is properly onboarded to the service.</span></span> <span data-ttu-id="68cdf-120">자세한 내용은 [새로 등록 Microsoft DEFENDER ATP 장치에서 검색 테스트 실행](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/run-detection-test)을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="68cdf-120">For more information, see [Run a detection test on a newly onboarded Microsoft Defender ATP device](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/run-detection-test).</span></span>
>
> <span data-ttu-id="68cdf-121">장치가 등록 된 경우 Configuration Manager 응용 프로그램에 대 한 검색 규칙이 계속 해 서 확인 되도록 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="68cdf-121">Note that it is possible to create a detection rule on a Configuration Manager application to continuously check if a device has been onboarded.</span></span> <span data-ttu-id="68cdf-122">응용 프로그램은 패키지와 프로그램에 해당 하는 것과 다른 유형의 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="68cdf-122">An application is a different type of object than a package and program.</span></span>
> <span data-ttu-id="68cdf-123">장치가 아직 등록 되지 않은 경우 (OOBE 완료 또는 기타 이유로 인해) Configuration Manager는 규칙이 상태 변경을 감지할 때까지 장치를 다시 활성화 합니다.</span><span class="sxs-lookup"><span data-stu-id="68cdf-123">If a device is not yet onboarded (due to pending OOBE completion or any other reason), Configuration Manager will retry to onboard the device until the rule detects the status change.</span></span>
> 
> <span data-ttu-id="68cdf-124">"OnboardingState" 레지스트리 값 (REG_DWORD 유형) = 1 인 경우 검색 규칙 확인을 만들어이 동작을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="68cdf-124">This behavior can be accomplished by creating a detection rule checking if the "OnboardingState" registry value (of type REG_DWORD) = 1.</span></span>
> <span data-ttu-id="68cdf-125">이 레지스트리 값은 "HKLM\SOFTWARE\Microsoft\Windows Advanced Threat Protection\Status" 아래에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="68cdf-125">This registry value is located under "HKLM\SOFTWARE\Microsoft\Windows Advanced Threat Protection\Status".</span></span>
<span data-ttu-id="68cdf-126">자세한 내용은 [System Center 2012 R2 Configuration Manager에서 검색 방법 구성을](https://docs.microsoft.com/previous-versions/system-center/system-center-2012-R2/gg682159\(v=technet.10\)#step-4-configure-detection-methods-to-indicate-the-presence-of-the-deployment-type)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="68cdf-126">For more information, see [Configure Detection Methods in System Center 2012 R2 Configuration Manager](https://docs.microsoft.com/previous-versions/system-center/system-center-2012-R2/gg682159\(v=technet.10\)#step-4-configure-detection-methods-to-indicate-the-presence-of-the-deployment-type).</span></span>

### <a name="configure-sample-collection-settings"></a><span data-ttu-id="68cdf-127">예제 모음 설정 구성</span><span class="sxs-lookup"><span data-stu-id="68cdf-127">Configure sample collection settings</span></span>

<span data-ttu-id="68cdf-128">각 장치에 대해 구성 값을 설정 하 여 Microsoft Defender 보안 센터를 통해 요청을 수행할 때 심층 분석을 위해 파일을 전송 하도록 장치에서 샘플을 수집할 수 있는지 여부를 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="68cdf-128">For each device, you can set a configuration value to state whether samples can be collected from the device when a request is made through Microsoft Defender Security Center to submit a file for deep analysis.</span></span>

>[!NOTE]
><span data-ttu-id="68cdf-129">이러한 구성 설정은 일반적으로 Configuration Manager를 통해 수행 됩니다.</span><span class="sxs-lookup"><span data-stu-id="68cdf-129">These configuration settings are typically done through Configuration Manager.</span></span> 

<span data-ttu-id="68cdf-130">구성 관리자에서 구성 항목에 대 한 준수 규칙을 설정 하 여 장치에 대 한 예제 공유 설정을 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="68cdf-130">You can set a compliance rule for configuration item in Configuration Manager to change the sample share setting on a device.</span></span>

<span data-ttu-id="68cdf-131">이 규칙은 대상 장치에 대 한 레지스트리 키의 값을 설정 하는 *수정* 규정 준수 규칙 구성 항목 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="68cdf-131">This rule should be a *remediating* compliance rule configuration item that sets the value of a registry key on targeted devices to make sure they’re complaint.</span></span>

<span data-ttu-id="68cdf-132">구성은 다음 레지스트리 키 항목을 통해 설정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="68cdf-132">The configuration is set through the following registry key entry:</span></span>

```
Path: “HKLM\SOFTWARE\Policies\Microsoft\Windows Advanced Threat Protection”
Name: "AllowSampleCollection"
Value: 0 or 1
```
<span data-ttu-id="68cdf-133">여기서,</span><span class="sxs-lookup"><span data-stu-id="68cdf-133">Where:</span></span><br>
<span data-ttu-id="68cdf-134">키 유형이 D 단어입니다.</span><span class="sxs-lookup"><span data-stu-id="68cdf-134">Key type is a D-WORD.</span></span> <br>
<span data-ttu-id="68cdf-135">가능한 값은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="68cdf-135">Possible values are:</span></span>
- <span data-ttu-id="68cdf-136">0-이 장치에서의 예제 공유 허용 안 합니다.</span><span class="sxs-lookup"><span data-stu-id="68cdf-136">0 - doesn't allow sample sharing  from this device</span></span>
- <span data-ttu-id="68cdf-137">1-이 장치에서 모든 파일 형식을 공유할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="68cdf-137">1 - allows sharing of all file types from this device</span></span>

<span data-ttu-id="68cdf-138">레지스트리 키가 없는 경우의 기본값은 1입니다.</span><span class="sxs-lookup"><span data-stu-id="68cdf-138">The default value in case the registry key doesn’t exist is 1.</span></span>

<span data-ttu-id="68cdf-139">System Center Configuration Manager 준수에 대 한 자세한 내용은 [System center 2012 R2 Configuration Manager의 준수 설정 소개](https://docs.microsoft.com/previous-versions/system-center/system-center-2012-R2/gg682139\(v=technet.10\))를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="68cdf-139">For more information about System Center Configuration Manager Compliance, see [Introduction to compliance settings in System Center 2012 R2 Configuration Manager](https://docs.microsoft.com/previous-versions/system-center/system-center-2012-R2/gg682139\(v=technet.10\)).</span></span>


## <a name="other-recommended-configuration-settings"></a><span data-ttu-id="68cdf-140">기타 권장 되는 구성 설정</span><span class="sxs-lookup"><span data-stu-id="68cdf-140">Other recommended configuration settings</span></span>
<span data-ttu-id="68cdf-141">서비스에 온 보 딩 장치를 설치한 후에는 다음과 같은 권장 구성 설정을 사용 하 여 포함 된 위협 방지 기능을 활용 하는 것이 중요 합니다.</span><span class="sxs-lookup"><span data-stu-id="68cdf-141">After onboarding devices to the service, it's important to take advantage of the included threat protection capabilities by enabling them with the following recommended configuration settings.</span></span>

### <a name="device-collection-configuration"></a><span data-ttu-id="68cdf-142">장치 모음 구성</span><span class="sxs-lookup"><span data-stu-id="68cdf-142">Device collection configuration</span></span>
<span data-ttu-id="68cdf-143">끝점 구성 관리자, 버전 2002 이상을 사용 중인 경우에는 서버 또는 하위 수준 클라이언트를 포함 하도록 배포를 넓힐 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="68cdf-143">If you're using Endpoint Configuration Manager, version 2002 or later, you can choose to broaden the deployment to include servers or down-level clients.</span></span>


### <a name="next-generation-protection-configuration"></a><span data-ttu-id="68cdf-144">차세대 보호 구성</span><span class="sxs-lookup"><span data-stu-id="68cdf-144">Next generation protection configuration</span></span>

<span data-ttu-id="68cdf-145">권장 되는 구성 설정은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="68cdf-145">The following configuration settings are recommended:</span></span>

<span data-ttu-id="68cdf-146">**스캔**</span><span class="sxs-lookup"><span data-stu-id="68cdf-146">**Scan**</span></span>

- <span data-ttu-id="68cdf-147">USB 드라이브와 같은 이동식 저장 장치 검사: 예</span><span class="sxs-lookup"><span data-stu-id="68cdf-147">Scan removable storage devices such as USB drives: Yes</span></span>

<span data-ttu-id="68cdf-148">**실시간 보호**</span><span class="sxs-lookup"><span data-stu-id="68cdf-148">**Real-time Protection**</span></span>

- <span data-ttu-id="68cdf-149">동작 모니터링 사용: 예</span><span class="sxs-lookup"><span data-stu-id="68cdf-149">Enable Behavioral Monitoring: Yes</span></span>
- <span data-ttu-id="68cdf-150">다운로드 및 설치 전에 잠재적으로 원치 않는 응용 프로그램에 대 한 보호 사용: 예</span><span class="sxs-lookup"><span data-stu-id="68cdf-150">Enable protection against Potentially Unwanted Applications at download and prior to installation: Yes</span></span>

<span data-ttu-id="68cdf-151">**클라우드 보호 서비스**</span><span class="sxs-lookup"><span data-stu-id="68cdf-151">**Cloud Protection Service**</span></span>

- <span data-ttu-id="68cdf-152">클라우드 보호 서비스 멤버 자격 유형: 고급 멤버 자격</span><span class="sxs-lookup"><span data-stu-id="68cdf-152">Cloud Protection Service membership type: Advanced membership</span></span>

<span data-ttu-id="68cdf-153">**공격 노출 영역 감소** 사용 가능한 모든 규칙을 감사 하도록 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="68cdf-153">**Attack surface reduction** Configure all available rules to Audit.</span></span>

>[!NOTE]
> <span data-ttu-id="68cdf-154">이러한 활동을 차단 하면 합법적인 비즈니스 프로세스가 중단 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="68cdf-154">Blocking these activities may interrupt legitimate business processes.</span></span> <span data-ttu-id="68cdf-155">가장 좋은 방법은 모든 내용을 감사로 설정 하 여 안전 하 게 켤 수 있는 것을 식별 한 다음 가양성 검색을 수행 하지 않는 끝점에서 해당 설정을 사용 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="68cdf-155">The best approach is setting everything to audit, identifying which ones are safe to turn on, and then enabling those settings on endpoints which do not have false positive detections.</span></span>

<span data-ttu-id="68cdf-156">**네트워크 보호**</span><span class="sxs-lookup"><span data-stu-id="68cdf-156">**Network protection**</span></span>

<span data-ttu-id="68cdf-157">감사 또는 차단 모드에서 네트워크 보호를 사용 하도록 설정 하기 전에 [지원 페이지](https://support.microsoft.com/en-us/help/4560203/windows-defender-anti-malware-platform-binaries-are-missing)에서 구할 수 있는 맬웨어 방지 플랫폼 업데이트를 설치 했는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="68cdf-157">Prior to enabling network protection in audit or block mode, ensure that you've installed the antimalware platform update, which can be obtained from the [support page](https://support.microsoft.com/en-us/help/4560203/windows-defender-anti-malware-platform-binaries-are-missing).</span></span>


<span data-ttu-id="68cdf-158">**제어 되는 폴더 액세스**</span><span class="sxs-lookup"><span data-stu-id="68cdf-158">**Controlled folder access**</span></span>

<span data-ttu-id="68cdf-159">최소 30 일 동안 감사 모드에서 기능을 사용 하도록 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="68cdf-159">Enable the feature in audit mode for at least 30 days.</span></span> <span data-ttu-id="68cdf-160">이 기간 후에 검색을 검토 하 고 보호 된 디렉터리에 쓸 수 있는 응용 프로그램 목록을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="68cdf-160">After this period, review detections and create a list of applications that are allowed to write to protected directories.</span></span>

<span data-ttu-id="68cdf-161">자세한 내용은 제어 되는 [폴더 액세스 평가](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/evaluate-controlled-folder-access)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="68cdf-161">For more information, see [Evaluate controlled folder access](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/evaluate-controlled-folder-access).</span></span>


## <a name="offboard-devices-using-configuration-manager"></a><span data-ttu-id="68cdf-162">Offboard 장치 사용 구성 관리자</span><span class="sxs-lookup"><span data-stu-id="68cdf-162">Offboard devices using Configuration Manager</span></span>

<span data-ttu-id="68cdf-163">보안상의 이유로, 보드 장치에 사용 된 패키지는 다운로드 한 날짜 로부터 30 일 후에 만료 됩니다.</span><span class="sxs-lookup"><span data-stu-id="68cdf-163">For security reasons, the package used to Offboard devices will expire 30 days after the date it was downloaded.</span></span> <span data-ttu-id="68cdf-164">만료 된 오프 보 딩 패키지가 장치로 전송 됩니다.</span><span class="sxs-lookup"><span data-stu-id="68cdf-164">Expired offboarding packages sent to a device will be rejected.</span></span> <span data-ttu-id="68cdf-165">오프 보 딩 패키지를 다운로드 하면 패키지 만료 날짜에 대 한 알림을 받게 되며 패키지 이름에도 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="68cdf-165">When downloading an offboarding package, you will be notified of the packages expiry date and it will also be included in the package name.</span></span>

> [!NOTE]
> <span data-ttu-id="68cdf-166">온 보 딩 및 오프 보 딩 정책은 동시에 같은 장치에 배포 해서는 안 되며 그렇지 않으면 예기치 않은 충돌이 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="68cdf-166">Onboarding and offboarding policies must not be deployed on the same device at the same time, otherwise this will cause unpredictable collisions.</span></span>

### <a name="offboard-devices-using-microsoft-endpoint-configuration-manager-current-branch"></a><span data-ttu-id="68cdf-167">Microsoft Endpoint Configuration Manager 현재 분기를 사용 하는 offboard 장치</span><span class="sxs-lookup"><span data-stu-id="68cdf-167">Offboard devices using Microsoft Endpoint Configuration Manager current branch</span></span>

<span data-ttu-id="68cdf-168">Microsoft Endpoint Configuration Manager 현재 분기를 사용 하는 경우에 [는 오프 보 딩 구성 파일 만들기](https://docs.microsoft.com/configmgr/protect/deploy-use/windows-defender-advanced-threat-protection#create-an-offboarding-configuration-file)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="68cdf-168">If you use Microsoft Endpoint Configuration Manager current branch, see [Create an offboarding configuration file](https://docs.microsoft.com/configmgr/protect/deploy-use/windows-defender-advanced-threat-protection#create-an-offboarding-configuration-file).</span></span>

### <a name="offboard-devices-using-system-center-2012-r2-configuration-manager"></a><span data-ttu-id="68cdf-169">System Center 2012 R2 Configuration Manager를 사용 하는 offboard 장치</span><span class="sxs-lookup"><span data-stu-id="68cdf-169">Offboard devices using System Center 2012 R2 Configuration Manager</span></span>

1. <span data-ttu-id="68cdf-170">[Microsoft 준수 센터](https://compliance.microsoft.com/)에서 오프 보 딩 패키지를 다운로드 합니다.</span><span class="sxs-lookup"><span data-stu-id="68cdf-170">Get the offboarding package from [Microsoft Compliance center](https://compliance.microsoft.com/):</span></span>

2. <span data-ttu-id="68cdf-171">탐색 창에서 **설정**  >   **장치 온 보** 딩을 선택 >  **Offboarding** 합니다.</span><span class="sxs-lookup"><span data-stu-id="68cdf-171">In the navigation pane, select **Settings** >  **Device onboarding**> **Offboarding** .</span></span>

3. <span data-ttu-id="68cdf-172">운영 체제로 Windows 10을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="68cdf-172">Select Windows 10 as the operating system.</span></span>

4. <span data-ttu-id="68cdf-173">**배포 방법** 필드에서 **Microsoft Endpoint Configuration Manager 2012/2012 R2/1511/1602** 을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="68cdf-173">In the **Deployment method** field, select **Microsoft Endpoint Configuration Manager 2012/2012 R2/1511/1602** .</span></span>
    
5. <span data-ttu-id="68cdf-174">**패키지 다운로드** 를 선택 하 고 .zip 파일을 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="68cdf-174">Select **Download package** , and save the .zip file.</span></span>

6. <span data-ttu-id="68cdf-175">패키지를 배포할 네트워크 관리자가 액세스할 수 있는 공유, 읽기 전용 위치에 .zip 파일의 내용을 추출 합니다.</span><span class="sxs-lookup"><span data-stu-id="68cdf-175">Extract the contents of the .zip file to a shared, read-only location that can be accessed by the network administrators who will deploy the package.</span></span> <span data-ttu-id="68cdf-176">*DeviceComplianceOffboardingScript_valid_until_YYYY-MM-DD* 라는 파일이 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="68cdf-176">You should have a file named *DeviceComplianceOffboardingScript_valid_until_YYYY-MM-DD.cmd* .</span></span>

7. <span data-ttu-id="68cdf-177">[System Center 2012 R2 Configuration Manager 문서의 패키지 및 프로그램](https://docs.microsoft.com/previous-versions/system-center/system-center-2012-R2/gg699369\(v=technet.10\)) 에 나와 있는 단계에 따라 패키지를 배포 합니다.</span><span class="sxs-lookup"><span data-stu-id="68cdf-177">Deploy the package by following the steps in the [Packages and Programs in System Center 2012 R2 Configuration Manager](https://docs.microsoft.com/previous-versions/system-center/system-center-2012-R2/gg699369\(v=technet.10\)) article.</span></span>

8. <span data-ttu-id="68cdf-178">패키지를 배포할 미리 정의 된 장치 모음을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="68cdf-178">Choose a predefined device collection to deploy the package to.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="68cdf-179">오프 보 딩은 장치에서 포털에 센서 데이터를 전송 하지 않고 장치에서 가져온 데이터에 대 한 참조를 포함 하 여 최대 6 개월 동안 보존 되도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="68cdf-179">Offboarding causes the device to stop sending sensor data to the portal but data from the device, including reference to any alerts it has had will be retained for up to 6 months.</span></span>


## <a name="monitor-device-configuration"></a><span data-ttu-id="68cdf-180">장치 구성 모니터링</span><span class="sxs-lookup"><span data-stu-id="68cdf-180">Monitor device configuration</span></span>

<span data-ttu-id="68cdf-181">Microsoft Endpoint Configuration Manager 현재 분기를 사용 중인 경우 Configuration Manager 콘솔에서 기본 제공 되는 Microsoft Defender ATP 대시보드를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="68cdf-181">If you're using Microsoft Endpoint Configuration Manager current branch, use the built-in Microsoft Defender ATP dashboard in the Configuration Manager console.</span></span> <span data-ttu-id="68cdf-182">자세한 내용은 [Microsoft Defender Advanced Threat Protection-모니터](https://docs.microsoft.com/configmgr/protect/deploy-use/windows-defender-advanced-threat-protection#monitor)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="68cdf-182">For more information, see [Microsoft Defender Advanced Threat Protection - Monitor](https://docs.microsoft.com/configmgr/protect/deploy-use/windows-defender-advanced-threat-protection#monitor).</span></span>

<span data-ttu-id="68cdf-183">System Center 2012 R2 Configuration Manager를 사용 하는 경우 모니터링은 다음 두 부분으로 구성 됩니다.</span><span class="sxs-lookup"><span data-stu-id="68cdf-183">If you're using System Center 2012 R2 Configuration Manager, monitoring consists of two parts:</span></span>

1. <span data-ttu-id="68cdf-184">네트워크의 장치에서 구성 패키지가 올바르게 배포 되었으며 실행 중이거나 성공적으로 실행 되 고 있는지 확인</span><span class="sxs-lookup"><span data-stu-id="68cdf-184">Confirming the configuration package has been correctly deployed and is running (or has successfully run) on the devices in your network.</span></span>

2. <span data-ttu-id="68cdf-185">장치가 Microsoft 365 끝점 데이터 손실 방지 서비스와 호환 되는지 확인 (장치에서 온 보 딩 프로세스를 완료 하 여 서비스에 대 한 데이터를 계속 보고할 수 있는지 확인)</span><span class="sxs-lookup"><span data-stu-id="68cdf-185">Checking that the devices are compliant with the Microsoft 365 Endpoint data loss prevention service (this ensures the device can complete the onboarding process and can continue to report data to the service).</span></span>

### <a name="confirm-the-configuration-package-has-been-correctly-deployed"></a><span data-ttu-id="68cdf-186">구성 패키지가 올바르게 배포 되었는지 확인</span><span class="sxs-lookup"><span data-stu-id="68cdf-186">Confirm the configuration package has been correctly deployed</span></span>

1. <span data-ttu-id="68cdf-187">Configuration Manager 콘솔의 탐색 창 아래쪽에서 **모니터링** 을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="68cdf-187">In the Configuration Manager console, click **Monitoring** at the bottom of the navigation pane.</span></span>

2. <span data-ttu-id="68cdf-188">**개요** 를 선택한 다음 **배포** 를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="68cdf-188">Select **Overview** and then **Deployments** .</span></span>

3. <span data-ttu-id="68cdf-189">패키지 이름을 사용 하 여 배포를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="68cdf-189">Select on the deployment with the package name.</span></span>

4. <span data-ttu-id="68cdf-190">**완료 통계** 및 **콘텐츠 상태** 에서 상태 표시기를 검토 합니다.</span><span class="sxs-lookup"><span data-stu-id="68cdf-190">Review the status indicators under **Completion Statistics** and **Content Status** .</span></span>

    <span data-ttu-id="68cdf-191">배포에 실패 한 경우 ( **오류가 발생** 한 장치, **요구 사항이 충족 되지** 않거나 **실패 한 상태** )가 있으면 장치 문제를 해결 해야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="68cdf-191">If there are failed deployments (devices with **Error** , **Requirements Not Met** , or **Failed statuses** ), you may need to  troubleshoot the devices.</span></span> <span data-ttu-id="68cdf-192">자세한 내용은 [Microsoft Defender Advanced Threat Protection 온 보 딩 문제 해결](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/troubleshoot-onboarding)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="68cdf-192">For more information, see, [Troubleshoot Microsoft Defender Advanced Threat Protection onboarding issues](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/troubleshoot-onboarding).</span></span>

    ![오류 없이 성공적인 배포를 보여 주는 Configuration Manager](../media/sccm-deployment.png)

### <a name="check-that-the-devices-are-compliant-with-the-microsoft-365-endpoint-data-loss-prevention-service"></a><span data-ttu-id="68cdf-194">장치가 Microsoft 365 끝점 데이터 손실 방지 서비스와 호환 되는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="68cdf-194">Check that the devices are compliant with the Microsoft 365 Endpoint data loss prevention service</span></span>

<span data-ttu-id="68cdf-195">System Center 2012 R2 Configuration Manager에서 구성 항목에 대 한 준수 규칙을 설정 하 여 배포를 모니터링할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="68cdf-195">You can set a compliance rule for configuration item in System Center 2012 R2 Configuration Manager to monitor your deployment.</span></span>

> [!NOTE]
> <span data-ttu-id="68cdf-196">이 절차와 레지스트리 항목은 Advanced Threat Protection 뿐만 아니라 끝점 DLP에도 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="68cdf-196">This procedure and registry entry applies to Endpoint DLP as well as Advanced Threat Protection.</span></span>

<span data-ttu-id="68cdf-197">이 규칙은 대상 장치에서 레지스트리 키의 값을 모니터링 하는 *비 수정* 규정 준수 규칙 구성 항목 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="68cdf-197">This rule should be a *non-remediating* compliance rule configuration item that monitors the value of a registry key on targeted devices.</span></span>

<span data-ttu-id="68cdf-198">다음 레지스트리 키 항목을 모니터링 합니다.</span><span class="sxs-lookup"><span data-stu-id="68cdf-198">Monitor the following registry key entry:</span></span>
```
Path: “HKLM\SOFTWARE\Microsoft\Windows Advanced Threat Protection\Status”
Name: “OnboardingState”
Value: “1”
```
<span data-ttu-id="68cdf-199">자세한 내용은 [System Center 2012 R2 Configuration Manager의 준수 설정 소개](https://docs.microsoft.com/previous-versions/system-center/system-center-2012-R2/gg682139\(v=technet.10\))를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="68cdf-199">For more information, see [Introduction to compliance settings in System Center 2012 R2 Configuration Manager](https://docs.microsoft.com/previous-versions/system-center/system-center-2012-R2/gg682139\(v=technet.10\)).</span></span>

## <a name="related-topics"></a><span data-ttu-id="68cdf-200">관련 항목</span><span class="sxs-lookup"><span data-stu-id="68cdf-200">Related topics</span></span>
- [<span data-ttu-id="68cdf-201">그룹 정책을 사용 하는 온보드 Windows 10 장치</span><span class="sxs-lookup"><span data-stu-id="68cdf-201">Onboard Windows 10 devices using Group Policy</span></span>](dlp-configure-endpoints-gp.md)
- [<span data-ttu-id="68cdf-202">모바일 장치 관리 도구를 사용 하는 온보드 Windows 10 장치</span><span class="sxs-lookup"><span data-stu-id="68cdf-202">Onboard Windows 10 devices using Mobile Device Management tools</span></span>](dlp-configure-endpoints-mdm.md)
- [<span data-ttu-id="68cdf-203">로컬 스크립트를 사용 하는 온보드 Windows 10 장치</span><span class="sxs-lookup"><span data-stu-id="68cdf-203">Onboard Windows 10 devices using a local script</span></span>](dlp-configure-endpoints-script.md)
- [<span data-ttu-id="68cdf-204">온보드 VDI (가상 데스크톱 인프라) 장치 (비영구)</span><span class="sxs-lookup"><span data-stu-id="68cdf-204">Onboard non-persistent virtual desktop infrastructure (VDI) devices</span></span>](dlp-configure-endpoints-vdi.md)
- [<span data-ttu-id="68cdf-205">새로 등록 Microsoft Defender ATP 장치에서 검색 테스트 실행</span><span class="sxs-lookup"><span data-stu-id="68cdf-205">Run a detection test on a newly onboarded Microsoft Defender ATP device</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/run-detection-test)
- [<span data-ttu-id="68cdf-206">Microsoft Defender Advanced Threat Protection 온 보 딩 문제 해결</span><span class="sxs-lookup"><span data-stu-id="68cdf-206">Troubleshoot Microsoft Defender Advanced Threat Protection onboarding issues</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/troubleshoot-onboarding)
