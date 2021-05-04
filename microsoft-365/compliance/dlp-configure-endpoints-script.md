---
title: 로컬 스크립트를 사용하여 Windows 10 장치 온보딩
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
description: 로컬 스크립트를 사용하여 장치에 구성 패키지를 배포하여 서비스에 온보딩합니다.
ms.openlocfilehash: e9efa76af72f9169bdec1acf35d72066ac0a776e
ms.sourcegitcommit: 55791ddab9ae484f76b30f0470eec8a4cf7b46d1
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/20/2021
ms.locfileid: "51893309"
---
# <a name="onboard-windows-10-devices-using-a-local-script"></a><span data-ttu-id="97d3d-103">로컬 스크립트를 사용하여 Windows 10 장치 온보딩</span><span class="sxs-lookup"><span data-stu-id="97d3d-103">Onboard Windows 10 devices using a local script</span></span>

<span data-ttu-id="97d3d-104">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="97d3d-104">**Applies to:**</span></span>

- [<span data-ttu-id="97d3d-105">Microsoft 365 끝점 DLP(데이터 손실 방지)</span><span class="sxs-lookup"><span data-stu-id="97d3d-105">Microsoft 365 Endpoint data loss prevention (DLP)</span></span>](./endpoint-dlp-learn-about.md)

<span data-ttu-id="97d3d-106">개별 장치를 수동으로 온보드하여 끝점 데이터 Microsoft 365 방지할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="97d3d-106">You can also manually onboard individual devices to Microsoft 365 Endpoint data loss prevention.</span></span> <span data-ttu-id="97d3d-107">네트워크의 모든 장치를 온보드하기 전에 서비스를 테스트할 때 이 작업을 먼저 수행해야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="97d3d-107">You might want to do this first when testing the service before you commit to onboarding all devices in your network.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="97d3d-108">이 스크립트는 최대 10대의 장치에서 사용하기 위해 최적화되었습니다.</span><span class="sxs-lookup"><span data-stu-id="97d3d-108">This script has been optimized for use on up to 10 devices.</span></span>
>
> <span data-ttu-id="97d3d-109">대규모로 배포하기 위해 다른 [배포 옵션을 사용하세요.](dlp-configure-endpoints.md)</span><span class="sxs-lookup"><span data-stu-id="97d3d-109">To deploy at scale, use [other deployment options](dlp-configure-endpoints.md).</span></span> <span data-ttu-id="97d3d-110">예를 들어 그룹 정책을 사용하여 온보딩 스크립트를 온보딩 장치에서 사용할 수 있는 스크립트를 사용하여 프로덕션의 10개가 넘는 디바이스에 배포할 [Windows 10 있습니다.](dlp-configure-endpoints-gp.md)</span><span class="sxs-lookup"><span data-stu-id="97d3d-110">For example, you can deploy an onboarding script to more than 10 devices in production with the script available in [Onboard Windows 10 devices using Group Policy](dlp-configure-endpoints-gp.md).</span></span>

## <a name="onboard-devices"></a><span data-ttu-id="97d3d-111">온보딩 장치</span><span class="sxs-lookup"><span data-stu-id="97d3d-111">Onboard devices</span></span>
 
1.  <span data-ttu-id="97d3d-112">서비스 온보더링 마법사에서 .zip \*\* 다운로드한 GP 구성 패키지 파일(DeviceComplianceOnboardingPackage.zip)을 열 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="97d3d-112">Open the GP configuration package .zip file (*DeviceComplianceOnboardingPackage.zip*) that you downloaded from the service onboarding wizard.</span></span> <span data-ttu-id="97d3d-113">Microsoft 규정 준수 센터에서 [패키지를 다운로드할 수 있습니다.](https://compliance.microsoft.com)</span><span class="sxs-lookup"><span data-stu-id="97d3d-113">You can also get the package from [Microsoft Compliance center](https://compliance.microsoft.com)</span></span>

2. <span data-ttu-id="97d3d-114">탐색 창에서 장치 **설정**  >  **를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="97d3d-114">In the navigation pane, select **Settings** > **Device onboarding**.</span></span>

3. <span data-ttu-id="97d3d-115">배포 **방법 필드에서** 로컬 스크립트 **를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="97d3d-115">In the **Deployment method** field, select **Local Script**.</span></span>

4. <span data-ttu-id="97d3d-116">패키지 **다운로드를** 클릭하고 파일 .zip 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="97d3d-116">Click **Download package** and save the .zip file.</span></span>
  
5. <span data-ttu-id="97d3d-117">온보더할 디바이스의 위치(예: 데스크톱)에 구성 패키지의 내용을 추출합니다.</span><span class="sxs-lookup"><span data-stu-id="97d3d-117">Extract the contents of the configuration package to a location on the device you want to onboard (for example, the Desktop).</span></span> <span data-ttu-id="97d3d-118">*이름이 DeviceOnboardingScript.cmd인 파일이 필요합니다.*</span><span class="sxs-lookup"><span data-stu-id="97d3d-118">You should have a file named *DeviceOnboardingScript.cmd*.</span></span>

6.  <span data-ttu-id="97d3d-119">디바이스에서 상승된 명령줄 프롬프트를 열고 스크립트를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="97d3d-119">Open an elevated command-line prompt on the device and run the script:</span></span>

7.  <span data-ttu-id="97d3d-120">**시작**(으)로 이동하고 **cmd** 를 입력하십시오.</span><span class="sxs-lookup"><span data-stu-id="97d3d-120">Go to **Start** and type **cmd**.</span></span>

8.  <span data-ttu-id="97d3d-121">**명령 프롬프트** 을(를) 마우스 오른쪽 버튼으로 클릭하고 **관리자**(으)로 실행을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="97d3d-121">Right-click **Command prompt** and select **Run as administrator**.</span></span>

    ![관리자 권한으로 실행을 설정하는 창 시작 메뉴](../media/dlp-run-as-admin.png)

9.  <span data-ttu-id="97d3d-123">스크립트 파일의 위치를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="97d3d-123">Type the location of the script file.</span></span> <span data-ttu-id="97d3d-124">바탕 화면에 파일을 복사한 경우 *%userprofile%\Desktop\WindowsDefenderATPOnboardingScript.cmd를 입력합니다.*</span><span class="sxs-lookup"><span data-stu-id="97d3d-124">If you copied the file to the desktop, type: *%userprofile%\Desktop\WindowsDefenderATPOnboardingScript.cmd*</span></span>

10.  <span data-ttu-id="97d3d-125">Enter 키를 **누르거나** 확인을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="97d3d-125">Press the **Enter** key or click **OK**.</span></span>

<span data-ttu-id="97d3d-126">장치가 규격을 확인하고 센서 데이터를 올바르게 보고하는지 수동으로 확인할 수 있는 방법에 대한 자세한 내용은 온보더링 문제 [해결을 Microsoft Defender Advanced Threat Protection 참조하세요.](/windows/security/threat-protection/microsoft-defender-atp/troubleshoot-onboarding)</span><span class="sxs-lookup"><span data-stu-id="97d3d-126">For information on how you can manually validate that the device is compliant and correctly reports sensor data see, [Troubleshoot Microsoft Defender Advanced Threat Protection onboarding issues](/windows/security/threat-protection/microsoft-defender-atp/troubleshoot-onboarding).</span></span>

## <a name="offboard-devices-using-a-local-script"></a><span data-ttu-id="97d3d-127">로컬 스크립트를 사용하여 디바이스 오프보딩</span><span class="sxs-lookup"><span data-stu-id="97d3d-127">Offboard devices using a local script</span></span>
<span data-ttu-id="97d3d-128">보안상의 이유로, 오프보드 장치에 사용된 패키지는 다운로드한 날짜 30일 후에 만료됩니다.</span><span class="sxs-lookup"><span data-stu-id="97d3d-128">For security reasons, the package used to Offboard devices will expire 30 days after the date it was downloaded.</span></span> <span data-ttu-id="97d3d-129">장치로 전송된 만료된 오프보더 패키지는 거부됩니다.</span><span class="sxs-lookup"><span data-stu-id="97d3d-129">Expired offboarding packages sent to an device will be rejected.</span></span> <span data-ttu-id="97d3d-130">오프보더 패키지를 다운로드할 때 패키지 만료 날짜에 대한 알림을 하게 되고 패키지 이름에도 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="97d3d-130">When downloading an offboarding package you will be notified of the packages expiry date and it will also be included in the package name.</span></span>

> [!NOTE]
> <span data-ttu-id="97d3d-131">온보드 및 오프보더 정책을 동일한 장치에 동시에 배포하면 안 됩니다. 그렇지 않으면 예측할 수 없는 충돌이 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="97d3d-131">Onboarding and offboarding policies must not be deployed on the same device at the same time, otherwise this will cause unpredictable collisions.</span></span>

1. <span data-ttu-id="97d3d-132">Microsoft 준수 센터에서 [오프보더 패키지 다운로드](https://compliance.microsoft.com)</span><span class="sxs-lookup"><span data-stu-id="97d3d-132">Get the offboarding package from [Microsoft Compliance center](https://compliance.microsoft.com)</span></span>

2. <span data-ttu-id="97d3d-133">탐색 창에서 장치 **설정**  >  **를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="97d3d-133">In the navigation pane, select **Settings** > **Device offboarding**.</span></span>

3. <span data-ttu-id="97d3d-134">배포 **방법 필드에서** 로컬 스크립트 **를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="97d3d-134">In the **Deployment method** field, select **Local Script**.</span></span>

4. <span data-ttu-id="97d3d-135">패키지 **다운로드를** 클릭하고 파일 .zip 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="97d3d-135">Click **Download package** and save the .zip file.</span></span>

5. <span data-ttu-id="97d3d-136">디바이스에서 액세스할 수 .zip 읽기 전용 공유 위치로 파일 콘텐츠의 추출</span><span class="sxs-lookup"><span data-stu-id="97d3d-136">Extract the contents of the .zip file to a shared, read-only location that can be accessed by the devices.</span></span> <span data-ttu-id="97d3d-137">이름이 *DeviceComplianceOffboardingScript_valid_until_YYYY-MM-DD.cmd 입니다.*</span><span class="sxs-lookup"><span data-stu-id="97d3d-137">You should have a file named *DeviceComplianceOffboardingScript_valid_until_YYYY-MM-DD.cmd*.</span></span>

6.  <span data-ttu-id="97d3d-138">디바이스에서 상승된 명령줄 프롬프트를 열고 스크립트를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="97d3d-138">Open an elevated command-line prompt on the device and run the script:</span></span>

7.  <span data-ttu-id="97d3d-139">**시작**(으)로 이동하고 **cmd** 를 입력하십시오.</span><span class="sxs-lookup"><span data-stu-id="97d3d-139">Go to **Start** and type **cmd**.</span></span>

8.  <span data-ttu-id="97d3d-140">**명령 프롬프트** 을(를) 마우스 오른쪽 버튼으로 클릭하고 **관리자**(으)로 실행을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="97d3d-140">Right-click **Command prompt** and select **Run as administrator**.</span></span>

    ![관리자 권한으로 실행을 설정하는 창 시작 메뉴](../media/dlp-run-as-admin.png)

9.  <span data-ttu-id="97d3d-142">스크립트 파일의 위치를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="97d3d-142">Type the location of the script file.</span></span> <span data-ttu-id="97d3d-143">바탕 화면에 파일을 복사한 경우 *%userprofile%\Desktop\WindowsDefenderATPOffboardingScript_valid_until_YYYY-MM-DD.cmd를 입력합니다.*</span><span class="sxs-lookup"><span data-stu-id="97d3d-143">If you copied the file to the desktop, type: *%userprofile%\Desktop\WindowsDefenderATPOffboardingScript_valid_until_YYYY-MM-DD.cmd*</span></span>

10.  <span data-ttu-id="97d3d-144">Enter 키를 **누르거나** 확인을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="97d3d-144">Press the **Enter** key or click **OK**.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="97d3d-145">오프보더링을 통해 디바이스가 포털에 센서 데이터 전송을 중지합니다.</span><span class="sxs-lookup"><span data-stu-id="97d3d-145">Offboarding causes the device to stop sending sensor data to the portal.</span></span>


## <a name="monitor-device-configuration"></a><span data-ttu-id="97d3d-146">장치 구성 모니터링</span><span class="sxs-lookup"><span data-stu-id="97d3d-146">Monitor device configuration</span></span>
<span data-ttu-id="97d3d-147">[온보딩 문제 해결](()의 다양한 확인 단계를 수행하여 스크립트가 성공적으로 완료되고 에이전트가 실행되고 있는지 https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/troubleshoot-onboarding) 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="97d3d-147">You can follow the different verification steps in the [Troubleshoot onboarding issues]((https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/troubleshoot-onboarding) to verify that the script completed successfully and the agent is running.</span></span>

<span data-ttu-id="97d3d-148">모니터링은 포털에서 직접 수행하거나 다른 배포 도구를 사용하여 수행될 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="97d3d-148">Monitoring can also be done directly on the portal, or by using the different deployment tools.</span></span>

### <a name="monitor-devices-using-the-portal"></a><span data-ttu-id="97d3d-149">포털을 사용하여 장치 모니터링</span><span class="sxs-lookup"><span data-stu-id="97d3d-149">Monitor devices using the portal</span></span>
1. <span data-ttu-id="97d3d-150">준수 [Microsoft 365 로 이동합니다.](https://compliance.microsoft.com)</span><span class="sxs-lookup"><span data-stu-id="97d3d-150">Go to [Microsoft 365 Compliance center](https://compliance.microsoft.com).</span></span>

2. <span data-ttu-id="97d3d-151">장치 **설정**  >  **장치를**  >  **선택하세요.**</span><span class="sxs-lookup"><span data-stu-id="97d3d-151">Choose **Settings** > **Device onboarding** > **Devices**.</span></span>

3. <span data-ttu-id="97d3d-152">장치가 나타나는지 확인</span><span class="sxs-lookup"><span data-stu-id="97d3d-152">Verify that devices are appearing.</span></span>


## <a name="related-topics"></a><span data-ttu-id="97d3d-153">관련 항목</span><span class="sxs-lookup"><span data-stu-id="97d3d-153">Related topics</span></span>
- [<span data-ttu-id="97d3d-154">그룹 정책을 Windows 10 장치 온보드</span><span class="sxs-lookup"><span data-stu-id="97d3d-154">Onboard Windows 10 devices using Group Policy</span></span>](dlp-configure-endpoints-gp.md)
- [<span data-ttu-id="97d3d-155">Windows 10 사용하여 장치 온보드 Microsoft Endpoint Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="97d3d-155">Onboard Windows 10 devices using Microsoft Endpoint Configuration Manager</span></span>](dlp-configure-endpoints-sccm.md)
- [<span data-ttu-id="97d3d-156">모바일 장치 관리 도구를 사용하여 Windows 10 장치 온보딩</span><span class="sxs-lookup"><span data-stu-id="97d3d-156">Onboard Windows 10 devices using Mobile Device Management tools</span></span>](dlp-configure-endpoints-mdm.md)
- [<span data-ttu-id="97d3d-157">비영구 VDI(가상 데스크톱 인프라) 장치 온보딩</span><span class="sxs-lookup"><span data-stu-id="97d3d-157">Onboard non-persistent virtual desktop infrastructure (VDI) devices</span></span>](dlp-configure-endpoints-vdi.md)
- [<span data-ttu-id="97d3d-158">새로 온보딩된 엔드포인트 디바이스용 Microsoft Defender에서 검색 테스트 실행</span><span class="sxs-lookup"><span data-stu-id="97d3d-158">Run a detection test on a newly onboarded Microsoft Defender for Endpoint device</span></span>](/windows/security/threat-protection/microsoft-defender-atp/run-detection-test)
- [<span data-ttu-id="97d3d-159">온보 Microsoft Defender Advanced Threat Protection 문제 해결</span><span class="sxs-lookup"><span data-stu-id="97d3d-159">Troubleshoot Microsoft Defender Advanced Threat Protection onboarding issues</span></span>](/windows/security/threat-protection/microsoft-defender-atp/troubleshoot-onboarding)