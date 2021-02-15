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
ms.openlocfilehash: 74152f9488623d39e32ee4e47a452bd1daea28c7
ms.sourcegitcommit: 6647055154002c7d3b8f7ce25ad53c9636bc8066
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2020
ms.locfileid: "48769473"
---
# <a name="onboard-windows-10-devices-using-a-local-script"></a><span data-ttu-id="718d8-103">로컬 스크립트를 사용하여 Windows 10 장치 온보딩</span><span class="sxs-lookup"><span data-stu-id="718d8-103">Onboard Windows 10 devices using a local script</span></span>

<span data-ttu-id="718d8-104">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="718d8-104">**Applies to:**</span></span>

- [<span data-ttu-id="718d8-105">Microsoft 365 끝점 DLP(데이터 손실 방지)</span><span class="sxs-lookup"><span data-stu-id="718d8-105">Microsoft 365 Endpoint data loss prevention (DLP)</span></span>](/microsoft-365/compliance/endpoint-dlp-learn-about)

<span data-ttu-id="718d8-106">개별 장치를 Microsoft 365 끝점 데이터 손실 방지에 수동으로 온보드할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="718d8-106">You can also manually onboard individual devices to Microsoft 365 Endpoint data loss prevention.</span></span> <span data-ttu-id="718d8-107">네트워크의 모든 장치를 온보드하기 전에 서비스를 테스트할 때 이 작업을 먼저 수행해야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="718d8-107">You might want to do this first when testing the service before you commit to onboarding all devices in your network.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="718d8-108">이 스크립트는 최대 10대의 장치에서 사용할 수 있도록 최적화되었습니다.</span><span class="sxs-lookup"><span data-stu-id="718d8-108">This script has been optimized for use on up to 10 devices.</span></span>
>
> <span data-ttu-id="718d8-109">대규모로 배포하기 위해 다른 [배포 옵션을 사용하세요.](dlp-configure-endpoints.md)</span><span class="sxs-lookup"><span data-stu-id="718d8-109">To deploy at scale, use [other deployment options](dlp-configure-endpoints.md).</span></span> <span data-ttu-id="718d8-110">예를 들어 그룹 정책을 사용하여 온보딩 스크립트를 Windows 10 장치에서 사용할 수 있는 스크립트를 사용하여 프로덕션의 [10개](dlp-configure-endpoints-gp.md)이상의 디바이스에 배포할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="718d8-110">For example, you can deploy an onboarding script to more than 10 devices in production with the script available in [Onboard Windows 10 devices using Group Policy](dlp-configure-endpoints-gp.md).</span></span>

## <a name="onboard-devices"></a><span data-ttu-id="718d8-111">온보드 장치</span><span class="sxs-lookup"><span data-stu-id="718d8-111">Onboard devices</span></span>
 
1.  <span data-ttu-id="718d8-112">서비스 온보더링 마법사에서 *다운로드한* GP 구성 패키지 .zip 파일(DeviceComplianceOnboardingPackage.zip)을 니다.</span><span class="sxs-lookup"><span data-stu-id="718d8-112">Open the GP configuration package .zip file (*DeviceComplianceOnboardingPackage.zip*) that you downloaded from the service onboarding wizard.</span></span> <span data-ttu-id="718d8-113">Microsoft 준수 센터에서 [패키지를 다운로드할 수 있습니다.](https://compliance.microsoft.com)</span><span class="sxs-lookup"><span data-stu-id="718d8-113">You can also get the package from [Microsoft Compliance center](https://compliance.microsoft.com)</span></span>

2. <span data-ttu-id="718d8-114">탐색 창에서 설정 **장치**  >  **온보더링을 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="718d8-114">In the navigation pane, select **Settings** > **Device onboarding**.</span></span>

3. <span data-ttu-id="718d8-115">배포 방법 **필드에서** 로컬 **스크립트를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="718d8-115">In the **Deployment method** field, select **Local Script**.</span></span>

4. <span data-ttu-id="718d8-116">패키지 **다운로드를 클릭하고** .zip 파일을 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="718d8-116">Click **Download package** and save the .zip file.</span></span>
  
5. <span data-ttu-id="718d8-117">온보드할 디바이스의 위치(예: 데스크톱)에 구성 패키지의 내용을 추출합니다.</span><span class="sxs-lookup"><span data-stu-id="718d8-117">Extract the contents of the configuration package to a location on the device you want to onboard (for example, the Desktop).</span></span> <span data-ttu-id="718d8-118">*DeviceOnboardingScript.cmd라는 파일이 필요합니다.*</span><span class="sxs-lookup"><span data-stu-id="718d8-118">You should have a file named *DeviceOnboardingScript.cmd*.</span></span>

6.  <span data-ttu-id="718d8-119">디바이스에서 상승된 명령줄 프롬프트를 열고 스크립트를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="718d8-119">Open an elevated command-line prompt on the device and run the script:</span></span>

7.  <span data-ttu-id="718d8-120">**시작**(으)로 이동하고 **cmd** 를 입력하십시오.</span><span class="sxs-lookup"><span data-stu-id="718d8-120">Go to **Start** and type **cmd**.</span></span>

8.  <span data-ttu-id="718d8-121">**명령 프롬프트** 을(를) 마우스 오른쪽 버튼으로 클릭하고 **관리자**(으)로 실행을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="718d8-121">Right-click **Command prompt** and select **Run as administrator**.</span></span>

![관리자 권한으로 실행을 설정하는 창 시작 메뉴](../media/dlp-run-as-admin.png)

9.  <span data-ttu-id="718d8-123">스크립트 파일의 위치를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="718d8-123">Type the location of the script file.</span></span> <span data-ttu-id="718d8-124">바탕 화면에 파일을 복사한 경우 *%userprofile%\Desktop\WindowsDefenderATPOnboardingScript.cmd를 입력합니다.*</span><span class="sxs-lookup"><span data-stu-id="718d8-124">If you copied the file to the desktop, type: *%userprofile%\Desktop\WindowsDefenderATPOnboardingScript.cmd*</span></span>

10.  <span data-ttu-id="718d8-125">**Enter** 키를 누르거나 확인을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="718d8-125">Press the **Enter** key or click **OK**.</span></span>

<span data-ttu-id="718d8-126">디바이스가 규격을 확인하고 센서 데이터를 올바르게 보고하는지 수동으로 확인할 수 있는 방법에 대한 자세한 내용은 [Microsoft Defender Advanced Threat Protection 온보딩 문제 해결을 참조하세요.](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/troubleshoot-onboarding)</span><span class="sxs-lookup"><span data-stu-id="718d8-126">For information on how you can manually validate that the device is compliant and correctly reports sensor data see, [Troubleshoot Microsoft Defender Advanced Threat Protection onboarding issues](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/troubleshoot-onboarding).</span></span>

## <a name="offboard-devices-using-a-local-script"></a><span data-ttu-id="718d8-127">로컬 스크립트를 사용하여 디바이스 오프보딩</span><span class="sxs-lookup"><span data-stu-id="718d8-127">Offboard devices using a local script</span></span>
<span data-ttu-id="718d8-128">보안상의 이유로 장치의 오프보드에 사용된 패키지는 다운로드한 날짜 30일 후에 만료됩니다.</span><span class="sxs-lookup"><span data-stu-id="718d8-128">For security reasons, the package used to Offboard devices will expire 30 days after the date it was downloaded.</span></span> <span data-ttu-id="718d8-129">장치에 전송된 만료된 오프보더 패키지는 거부됩니다.</span><span class="sxs-lookup"><span data-stu-id="718d8-129">Expired offboarding packages sent to an device will be rejected.</span></span> <span data-ttu-id="718d8-130">오프보더 패키지를 다운로드할 때 패키지 만료 날짜에 대한 알림을 하게 되고 패키지 이름에도 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="718d8-130">When downloading an offboarding package you will be notified of the packages expiry date and it will also be included in the package name.</span></span>

> [!NOTE]
> <span data-ttu-id="718d8-131">온보드 및 오프보더 정책은 동일한 장치에 동시에 배포하면 안 됩니다. 그렇지 않으면 예측할 수 없는 충돌이 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="718d8-131">Onboarding and offboarding policies must not be deployed on the same device at the same time, otherwise this will cause unpredictable collisions.</span></span>

1. <span data-ttu-id="718d8-132">Microsoft 준수 센터에서 [오프보더 패키지 다운로드](https://compliance.microsoft.com)</span><span class="sxs-lookup"><span data-stu-id="718d8-132">Get the offboarding package from [Microsoft Compliance center](https://compliance.microsoft.com)</span></span>

2. <span data-ttu-id="718d8-133">탐색 창에서 설정 장치 오프보더를  >  **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="718d8-133">In the navigation pane, select **Settings** > **Device offboarding**.</span></span>

3. <span data-ttu-id="718d8-134">배포 방법 **필드에서** 로컬 **스크립트를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="718d8-134">In the **Deployment method** field, select **Local Script**.</span></span>

4. <span data-ttu-id="718d8-135">패키지 **다운로드를 클릭하고** .zip 파일을 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="718d8-135">Click **Download package** and save the .zip file.</span></span>

5. <span data-ttu-id="718d8-136">디바이스에서 액세스할 수 있는 공유 읽기 전용 위치에 .zip 파일의 내용을 추출합니다.</span><span class="sxs-lookup"><span data-stu-id="718d8-136">Extract the contents of the .zip file to a shared, read-only location that can be accessed by the devices.</span></span> <span data-ttu-id="718d8-137">이름이 *DeviceComplianceOffboardingScript_valid_until_YYYY-MM-DD.cmd입니다.*</span><span class="sxs-lookup"><span data-stu-id="718d8-137">You should have a file named *DeviceComplianceOffboardingScript_valid_until_YYYY-MM-DD.cmd*.</span></span>

6.  <span data-ttu-id="718d8-138">디바이스에서 상승된 명령줄 프롬프트를 열고 스크립트를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="718d8-138">Open an elevated command-line prompt on the device and run the script:</span></span>

7.  <span data-ttu-id="718d8-139">**시작**(으)로 이동하고 **cmd** 를 입력하십시오.</span><span class="sxs-lookup"><span data-stu-id="718d8-139">Go to **Start** and type **cmd**.</span></span>

8.  <span data-ttu-id="718d8-140">**명령 프롬프트** 을(를) 마우스 오른쪽 버튼으로 클릭하고 **관리자**(으)로 실행을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="718d8-140">Right-click **Command prompt** and select **Run as administrator**.</span></span>

![관리자 권한으로 실행을 설정하는 창 시작 메뉴](../media/dlp-run-as-admin.png)

9.  <span data-ttu-id="718d8-142">스크립트 파일의 위치를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="718d8-142">Type the location of the script file.</span></span> <span data-ttu-id="718d8-143">바탕 화면에 파일을 복사한 경우 *%userprofile%\Desktop\WindowsDefenderATPOffboardingScript_valid_until_YYYY-MM-DD.cmd를 입력합니다.*</span><span class="sxs-lookup"><span data-stu-id="718d8-143">If you copied the file to the desktop, type: *%userprofile%\Desktop\WindowsDefenderATPOffboardingScript_valid_until_YYYY-MM-DD.cmd*</span></span>

10.  <span data-ttu-id="718d8-144">**Enter** 키를 누르거나 확인을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="718d8-144">Press the **Enter** key or click **OK**.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="718d8-145">오프보더를 통해 디바이스가 포털에 센서 데이터 전송을 중지합니다.</span><span class="sxs-lookup"><span data-stu-id="718d8-145">Offboarding causes the device to stop sending sensor data to the portal.</span></span>


## <a name="monitor-device-configuration"></a><span data-ttu-id="718d8-146">장치 구성 모니터링</span><span class="sxs-lookup"><span data-stu-id="718d8-146">Monitor device configuration</span></span>
<span data-ttu-id="718d8-147">[온보딩 문제 해결](() 스크립트가 성공적으로 완료되고 에이전트가 실행되고 있는지 확인을 위해 [온보딩 문제 해결]()의 다양한 확인 단계를 따를 https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/troubleshoot-onboarding) 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="718d8-147">You can follow the different verification steps in the [Troubleshoot onboarding issues]((https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/troubleshoot-onboarding) to verify that the script completed successfully and the agent is running.</span></span>

<span data-ttu-id="718d8-148">모니터링은 포털에서 직접 수행하거나 다른 배포 도구를 사용하여 수행될 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="718d8-148">Monitoring can also be done directly on the portal, or by using the different deployment tools.</span></span>

### <a name="monitor-devices-using-the-portal"></a><span data-ttu-id="718d8-149">포털을 사용하여 장치 모니터링</span><span class="sxs-lookup"><span data-stu-id="718d8-149">Monitor devices using the portal</span></span>
1. <span data-ttu-id="718d8-150">Microsoft [365 규정 준수 센터로 이동](https://compliance.microsoft.com)</span><span class="sxs-lookup"><span data-stu-id="718d8-150">Go to [Microsoft 365 Compliance center](https://compliance.microsoft.com).</span></span>

2. <span data-ttu-id="718d8-151">설정 **장치**  >  **온보더링 디바이스를**  >  **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="718d8-151">Choose **Settings** > **Device onboarding** > **Devices**.</span></span>

3. <span data-ttu-id="718d8-152">장치가 나타나는지 확인</span><span class="sxs-lookup"><span data-stu-id="718d8-152">Verify that devices are appearing.</span></span>


## <a name="related-topics"></a><span data-ttu-id="718d8-153">관련 항목</span><span class="sxs-lookup"><span data-stu-id="718d8-153">Related topics</span></span>
- [<span data-ttu-id="718d8-154">그룹 정책을 사용하여 Windows 10 장치 온보드</span><span class="sxs-lookup"><span data-stu-id="718d8-154">Onboard Windows 10 devices using Group Policy</span></span>](dlp-configure-endpoints-gp.md)
- [<span data-ttu-id="718d8-155">Microsoft Endpoint Configuration Manager를 사용하여 Windows 10 장치 온보드</span><span class="sxs-lookup"><span data-stu-id="718d8-155">Onboard Windows 10 devices using Microsoft Endpoint Configuration Manager</span></span>](dlp-configure-endpoints-sccm.md)
- [<span data-ttu-id="718d8-156">모바일 장치 관리 도구를 사용하여 Windows 10 장치 온보딩</span><span class="sxs-lookup"><span data-stu-id="718d8-156">Onboard Windows 10 devices using Mobile Device Management tools</span></span>](dlp-configure-endpoints-mdm.md)
- [<span data-ttu-id="718d8-157">비영구 가상 데스크톱 인프라(VDI) 장치 온보딩</span><span class="sxs-lookup"><span data-stu-id="718d8-157">Onboard non-persistent virtual desktop infrastructure (VDI) devices</span></span>](dlp-configure-endpoints-vdi.md)
- [<span data-ttu-id="718d8-158">새로 온보딩된 Microsoft Defender ATP 장치에서 검색 테스트 실행</span><span class="sxs-lookup"><span data-stu-id="718d8-158">Run a detection test on a newly onboarded Microsoft Defender ATP device</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/run-detection-test)
- [<span data-ttu-id="718d8-159">Microsoft Defender Advanced Threat Protection 온보딩 문제 해결</span><span class="sxs-lookup"><span data-stu-id="718d8-159">Troubleshoot Microsoft Defender Advanced Threat Protection onboarding issues</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/troubleshoot-onboarding)
