---
title: 로컬 스크립트를 사용하여 Windows 10 장치 온보딩
description: 로컬 스크립트를 사용하여 장치에 구성 패키지를 배포하여 서비스에 온보딩합니다.
keywords: 로컬 스크립트를 사용하여 장치 구성, 장치 관리, 끝점 장치용 Microsoft Defender 구성
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
ms.technology: mde
ms.openlocfilehash: 2510fb1a187bbe136669e11bc73103438b51d811
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/08/2021
ms.locfileid: "52842173"
---
# <a name="onboard-windows-10-devices-using-a-local-script"></a><span data-ttu-id="62a11-104">로컬 스크립트를 사용하여 Windows 10 장치 온보딩</span><span class="sxs-lookup"><span data-stu-id="62a11-104">Onboard Windows 10 devices using a local script</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

- [<span data-ttu-id="62a11-105">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="62a11-105">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)


><span data-ttu-id="62a11-106">Endpoint용 Defender를 경험하고 싶나요?</span><span class="sxs-lookup"><span data-stu-id="62a11-106">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="62a11-107">무료 평가판에 등록합니다.</span><span class="sxs-lookup"><span data-stu-id="62a11-107">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-configureendpointsscript-abovefoldlink)

<span data-ttu-id="62a11-108">개별 디바이스를 Endpoint용 Defender에 수동으로 온보딩할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="62a11-108">You can also manually onboard individual devices to Defender for Endpoint.</span></span> <span data-ttu-id="62a11-109">네트워크의 모든 장치를 온보드하기 전에 서비스를 테스트할 때 이 작업을 먼저 수행해야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="62a11-109">You might want to do this first when testing the service before you commit to onboarding all devices in your network.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="62a11-110">이 스크립트는 최대 10대의 장치에서 사용하기 위해 최적화되었습니다.</span><span class="sxs-lookup"><span data-stu-id="62a11-110">This script has been optimized for use on up to 10 devices.</span></span>
>
> <span data-ttu-id="62a11-111">대규모로 배포하기 위해 다른 [배포 옵션을 사용하세요.](configure-endpoints.md)</span><span class="sxs-lookup"><span data-stu-id="62a11-111">To deploy at scale, use [other deployment options](configure-endpoints.md).</span></span> <span data-ttu-id="62a11-112">예를 들어 그룹 정책을 사용하여 온보딩 스크립트를 온보딩 장치에서 사용할 수 있는 스크립트를 사용하여 프로덕션의 10개가 넘는 디바이스에 배포할 [Windows 10 있습니다.](configure-endpoints-gp.md)</span><span class="sxs-lookup"><span data-stu-id="62a11-112">For example, you can deploy an onboarding script to more than 10 devices in production with the script available in [Onboard Windows 10 devices using Group Policy](configure-endpoints-gp.md).</span></span>

## <a name="onboard-devices"></a><span data-ttu-id="62a11-113">온보딩 장치</span><span class="sxs-lookup"><span data-stu-id="62a11-113">Onboard devices</span></span> 

<span data-ttu-id="62a11-114">[![다양한 배포 경로를 보여 주며 PDF 이미지](images/onboard-script.png)](images/onboard-script.png#lightbox)</span><span class="sxs-lookup"><span data-stu-id="62a11-114">[![Image of the PDF showing the various deployment paths](images/onboard-script.png)](images/onboard-script.png#lightbox)</span></span>


<span data-ttu-id="62a11-115">[PDF](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/security/defender-endpoint/downloads/mdatp-deployment-strategy.pdf) 또는 Visio [](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/security/defender-endpoint/downloads/mdatp-deployment-strategy.vsdx) 끝점용 Defender 배포에서 다양한 경로를 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="62a11-115">Check out the [PDF](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/security/defender-endpoint/downloads/mdatp-deployment-strategy.pdf)  or  [Visio](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/security/defender-endpoint/downloads/mdatp-deployment-strategy.vsdx) to see the various paths in deploying Defender for Endpoint.</span></span> 


1.  <span data-ttu-id="62a11-116">서비스 온보더링 마법사에서 .zip \*\* 다운로드한 GP 구성 패키지 파일(WindowsDefenderATPOnboardingPackage.zip)을 열 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="62a11-116">Open the GP configuration package .zip file (*WindowsDefenderATPOnboardingPackage.zip*) that you downloaded from the service onboarding wizard.</span></span> <span data-ttu-id="62a11-117">에서 패키지를 얻을 [Microsoft Defender 보안 센터.](https://securitycenter.windows.com/)</span><span class="sxs-lookup"><span data-stu-id="62a11-117">You can also get the package from [Microsoft Defender Security Center](https://securitycenter.windows.com/):</span></span>

    1. <span data-ttu-id="62a11-118">탐색 창에서 **온보 설정**  >  **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="62a11-118">In the navigation pane, select **Settings** > **Onboarding**.</span></span>

    1. <span data-ttu-id="62a11-119">운영 Windows 10 로 실행을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="62a11-119">Select Windows 10 as the operating system.</span></span>

    1. <span data-ttu-id="62a11-120">배포 **방법 필드에서** 로컬 스크립트 **를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="62a11-120">In the **Deployment method** field, select **Local Script**.</span></span>

    1. <span data-ttu-id="62a11-121">패키지 **다운로드를** 클릭하고 파일 .zip 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="62a11-121">Click **Download package** and save the .zip file.</span></span>

  
2.  <span data-ttu-id="62a11-122">온보더할 디바이스의 위치(예: 데스크톱)에 구성 패키지의 내용을 추출합니다.</span><span class="sxs-lookup"><span data-stu-id="62a11-122">Extract the contents of the configuration package to a location on the device you want to onboard (for example, the Desktop).</span></span> <span data-ttu-id="62a11-123">*이름이 WindowsDefenderATPLocalOnboardingScript.cmd인 파일이 있습니다.*</span><span class="sxs-lookup"><span data-stu-id="62a11-123">You should have a file named *WindowsDefenderATPLocalOnboardingScript.cmd*.</span></span>

3.  <span data-ttu-id="62a11-124">디바이스에서 상승된 명령줄 프롬프트를 열고 스크립트를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="62a11-124">Open an elevated command-line prompt on the device and run the script:</span></span>

    1.  <span data-ttu-id="62a11-125">**시작**(으)로 이동하고 **cmd** 를 입력하십시오.</span><span class="sxs-lookup"><span data-stu-id="62a11-125">Go to **Start** and type **cmd**.</span></span>

    1.  <span data-ttu-id="62a11-126">**명령 프롬프트** 을(를) 마우스 오른쪽 버튼으로 클릭하고 **관리자**(으)로 실행을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="62a11-126">Right-click **Command prompt** and select **Run as administrator**.</span></span>

        ![관리자 권한으로 실행을 설정하는 창 시작 메뉴](images/run-as-admin.png)

4.  <span data-ttu-id="62a11-128">스크립트 파일의 위치를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="62a11-128">Type the location of the script file.</span></span> <span data-ttu-id="62a11-129">바탕 화면에 파일을 복사한 경우 *%userprofile%\Desktop\WindowsDefenderATPLocalOnboardingScript.cmd를 입력합니다.*</span><span class="sxs-lookup"><span data-stu-id="62a11-129">If you copied the file to the desktop, type: *%userprofile%\Desktop\WindowsDefenderATPLocalOnboardingScript.cmd*</span></span>

5.  <span data-ttu-id="62a11-130">Enter 키를 **누르거나** 확인을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="62a11-130">Press the **Enter** key or click **OK**.</span></span>

<span data-ttu-id="62a11-131">장치가 규격을 확인하고 센서 데이터를 올바르게 보고하는지 수동으로 확인할 수 있는 방법에 대한 자세한 내용은 Endpoint 온보딩 문제에 [대한 Microsoft Defender 문제 해결을 참조하세요.](troubleshoot-onboarding.md)</span><span class="sxs-lookup"><span data-stu-id="62a11-131">For information on how you can manually validate that the device is compliant and correctly reports sensor data see, [Troubleshoot Microsoft Defender for Endpoint onboarding issues](troubleshoot-onboarding.md).</span></span>


>[!TIP]
> <span data-ttu-id="62a11-132">장치를 온보드한 후 검색 테스트를 실행하여 장치가 서비스에 제대로 온보드되었는지 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="62a11-132">After onboarding the device, you can choose to run a detection test to verify that an device is properly onboarded to the service.</span></span> <span data-ttu-id="62a11-133">자세한 내용은 새로 온보딩된 [끝점용 Microsoft Defender](run-detection-test.md)끝점에서 검색 테스트 실행을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="62a11-133">For more information, see [Run a detection test on a newly onboarded Microsoft Defender for Endpoint endpoint](run-detection-test.md).</span></span>

## <a name="configure-sample-collection-settings"></a><span data-ttu-id="62a11-134">샘플 수집 설정 구성</span><span class="sxs-lookup"><span data-stu-id="62a11-134">Configure sample collection settings</span></span>
<span data-ttu-id="62a11-135">각 디바이스에 대해 심층 분석을 위해 파일을 제출하기 위해 요청을 할 때 장치에서 샘플을 수집할 수 있는지 여부를 Microsoft Defender 보안 센터 구성 값을 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="62a11-135">For each device, you can set a configuration value to state whether samples can be collected from the device when a request is made through Microsoft Defender Security Center to submit a file for deep analysis.</span></span>

<span data-ttu-id="62a11-136">*regedit를* 사용하거나 .reg 파일을 만들고 실행하여 디바이스에서 샘플 공유 설정을 수동으로 *구성할 수* 있습니다.</span><span class="sxs-lookup"><span data-stu-id="62a11-136">You can manually configure the sample sharing setting on the device by using *regedit* or creating and running a *.reg* file.</span></span>  

<span data-ttu-id="62a11-137">구성은 다음 레지스트리 키 항목을 통해 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="62a11-137">The configuration is set through the following registry key entry:</span></span>

```console
Path: “HKLM\SOFTWARE\Policies\Microsoft\Windows Advanced Threat Protection”
Name: "AllowSampleCollection"
Value: 0 or 1
```
<span data-ttu-id="62a11-138">여기서,</span><span class="sxs-lookup"><span data-stu-id="62a11-138">Where:</span></span><br>
<span data-ttu-id="62a11-139">이름 형식은 D-WORD입니다.</span><span class="sxs-lookup"><span data-stu-id="62a11-139">Name type is a D-WORD.</span></span> <br>
<span data-ttu-id="62a11-140">가능한 값은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="62a11-140">Possible values are:</span></span>
- <span data-ttu-id="62a11-141">0 - 이 장치에서 샘플 공유를 허용하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="62a11-141">0 - doesn't allow sample sharing  from this device</span></span>
- <span data-ttu-id="62a11-142">1 - 이 장치에서 모든 파일 형식을 공유할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="62a11-142">1 - allows sharing of all file types from this device</span></span>

<span data-ttu-id="62a11-143">레지스트리 키가 없는 경우의 기본값은 1입니다.</span><span class="sxs-lookup"><span data-stu-id="62a11-143">The default value in case the registry key doesn’t exist is 1.</span></span>


## <a name="offboard-devices-using-a-local-script"></a><span data-ttu-id="62a11-144">로컬 스크립트를 사용하여 디바이스 오프보딩</span><span class="sxs-lookup"><span data-stu-id="62a11-144">Offboard devices using a local script</span></span>
<span data-ttu-id="62a11-145">보안상의 이유로, 오프보드 장치에 사용된 패키지는 다운로드한 날짜 30일 후에 만료됩니다.</span><span class="sxs-lookup"><span data-stu-id="62a11-145">For security reasons, the package used to Offboard devices will expire 30 days after the date it was downloaded.</span></span> <span data-ttu-id="62a11-146">장치로 전송된 만료된 오프보더 패키지는 거부됩니다.</span><span class="sxs-lookup"><span data-stu-id="62a11-146">Expired offboarding packages sent to an device will be rejected.</span></span> <span data-ttu-id="62a11-147">오프보더 패키지를 다운로드할 때 패키지 만료 날짜에 대한 알림을 하게 되고 패키지 이름에도 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="62a11-147">When downloading an offboarding package you will be notified of the packages expiry date and it will also be included in the package name.</span></span>

> [!NOTE]
> <span data-ttu-id="62a11-148">온보드 및 오프보더 정책을 동일한 장치에 동시에 배포하면 안 됩니다. 그렇지 않으면 예측할 수 없는 충돌이 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="62a11-148">Onboarding and offboarding policies must not be deployed on the same device at the same time, otherwise this will cause unpredictable collisions.</span></span>

1. <span data-ttu-id="62a11-149">에서 오프보더 [패키지를 Microsoft Defender 보안 센터.](https://securitycenter.windows.com/)</span><span class="sxs-lookup"><span data-stu-id="62a11-149">Get the offboarding package from [Microsoft Defender Security Center](https://securitycenter.windows.com/):</span></span>

    1. <span data-ttu-id="62a11-150">탐색 창에서 **오프보더 설정**  >  **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="62a11-150">In the navigation pane, select **Settings** > **Offboarding**.</span></span>

    1. <span data-ttu-id="62a11-151">운영 Windows 10 로 실행을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="62a11-151">Select Windows 10 as the operating system.</span></span>

    1. <span data-ttu-id="62a11-152">배포 **방법 필드에서** 로컬 스크립트 **를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="62a11-152">In the **Deployment method** field, select **Local Script**.</span></span>

    1. <span data-ttu-id="62a11-153">패키지 **다운로드를** 클릭하고 파일 .zip 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="62a11-153">Click **Download package** and save the .zip file.</span></span>

2. <span data-ttu-id="62a11-154">디바이스에서 액세스할 수 .zip 읽기 전용 공유 위치로 파일 콘텐츠의 추출</span><span class="sxs-lookup"><span data-stu-id="62a11-154">Extract the contents of the .zip file to a shared, read-only location that can be accessed by the devices.</span></span> <span data-ttu-id="62a11-155">이름이 *WindowsDefenderATPOffboardingScript_valid_until_YYYY-MM-DD.cmd 입니다.*</span><span class="sxs-lookup"><span data-stu-id="62a11-155">You should have a file named *WindowsDefenderATPOffboardingScript_valid_until_YYYY-MM-DD.cmd*.</span></span>

3.  <span data-ttu-id="62a11-156">디바이스에서 상승된 명령줄 프롬프트를 열고 스크립트를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="62a11-156">Open an elevated command-line prompt on the device and run the script:</span></span>

    1.  <span data-ttu-id="62a11-157">**시작**(으)로 이동하고 **cmd** 를 입력하십시오.</span><span class="sxs-lookup"><span data-stu-id="62a11-157">Go to **Start** and type **cmd**.</span></span>

    1.  <span data-ttu-id="62a11-158">**명령 프롬프트** 을(를) 마우스 오른쪽 버튼으로 클릭하고 **관리자**(으)로 실행을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="62a11-158">Right-click **Command prompt** and select **Run as administrator**.</span></span>

        ![관리자 권한으로 실행을 설정하는 창 시작 메뉴](images/run-as-admin.png)

4.  <span data-ttu-id="62a11-160">스크립트 파일의 위치를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="62a11-160">Type the location of the script file.</span></span> <span data-ttu-id="62a11-161">바탕 화면에 파일을 복사한 경우 *%userprofile%\Desktop\WindowsDefenderATPOffboardingScript_valid_until_YYYY-MM-DD.cmd를 입력합니다.*</span><span class="sxs-lookup"><span data-stu-id="62a11-161">If you copied the file to the desktop, type: *%userprofile%\Desktop\WindowsDefenderATPOffboardingScript_valid_until_YYYY-MM-DD.cmd*</span></span>

5.  <span data-ttu-id="62a11-162">Enter 키를 **누르거나** 확인을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="62a11-162">Press the **Enter** key or click **OK**.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="62a11-163">오프보더링을 통해 디바이스가 포털에 센서 데이터 전송을 중지하지만, 디바이스에서 전송한 모든 경고에 대한 참조를 포함하여 장치의 데이터는 최대 6개월 동안 보존됩니다.</span><span class="sxs-lookup"><span data-stu-id="62a11-163">Offboarding causes the device to stop sending sensor data to the portal but data from the device, including reference to any alerts it has had will be retained for up to 6 months.</span></span>


## <a name="monitor-device-configuration"></a><span data-ttu-id="62a11-164">장치 구성 모니터링</span><span class="sxs-lookup"><span data-stu-id="62a11-164">Monitor device configuration</span></span>
<span data-ttu-id="62a11-165">온보딩 문제 해결의 [](troubleshoot-onboarding.md) 다양한 확인 단계를 수행하여 스크립트가 성공적으로 완료되고 에이전트가 실행되고 있는지 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="62a11-165">You can follow the different verification steps in the [Troubleshoot onboarding issues](troubleshoot-onboarding.md) to verify that the script completed successfully and the agent is running.</span></span>

<span data-ttu-id="62a11-166">모니터링은 포털에서 직접 수행하거나 다른 배포 도구를 사용하여 수행될 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="62a11-166">Monitoring can also be done directly on the portal, or by using the different deployment tools.</span></span>

### <a name="monitor-devices-using-the-portal"></a><span data-ttu-id="62a11-167">포털을 사용하여 장치 모니터링</span><span class="sxs-lookup"><span data-stu-id="62a11-167">Monitor devices using the portal</span></span>
1. <span data-ttu-id="62a11-168">다음으로 Microsoft Defender 보안 센터.</span><span class="sxs-lookup"><span data-stu-id="62a11-168">Go to Microsoft Defender Security Center.</span></span>

2. <span data-ttu-id="62a11-169">장치 **목록을 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="62a11-169">Click **Devices list**.</span></span>

3. <span data-ttu-id="62a11-170">장치가 나타나는지 확인</span><span class="sxs-lookup"><span data-stu-id="62a11-170">Verify that devices are appearing.</span></span>


## <a name="related-topics"></a><span data-ttu-id="62a11-171">관련 항목</span><span class="sxs-lookup"><span data-stu-id="62a11-171">Related topics</span></span>
- [<span data-ttu-id="62a11-172">그룹 정책을 Windows 10 장치 온보드</span><span class="sxs-lookup"><span data-stu-id="62a11-172">Onboard Windows 10 devices using Group Policy</span></span>](configure-endpoints-gp.md)
- [<span data-ttu-id="62a11-173">Windows 10 사용하여 장치 온보드 Microsoft Endpoint Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="62a11-173">Onboard Windows 10 devices using Microsoft Endpoint Configuration Manager</span></span>](configure-endpoints-sccm.md)
- [<span data-ttu-id="62a11-174">모바일 장치 관리 도구를 사용하여 Windows 10 장치 온보딩</span><span class="sxs-lookup"><span data-stu-id="62a11-174">Onboard Windows 10 devices using Mobile Device Management tools</span></span>](configure-endpoints-mdm.md)
- [<span data-ttu-id="62a11-175">비영구 VDI(가상 데스크톱 인프라) 장치 온보딩</span><span class="sxs-lookup"><span data-stu-id="62a11-175">Onboard non-persistent virtual desktop infrastructure (VDI) devices</span></span>](configure-endpoints-vdi.md)
- [<span data-ttu-id="62a11-176">새로 온보딩된 엔드포인트 디바이스용 Microsoft Defender에서 검색 테스트 실행</span><span class="sxs-lookup"><span data-stu-id="62a11-176">Run a detection test on a newly onboarded Microsoft Defender for Endpoint device</span></span>](run-detection-test.md)
- [<span data-ttu-id="62a11-177">끝점 온보딩 문제에 대한 Microsoft Defender 문제 해결</span><span class="sxs-lookup"><span data-stu-id="62a11-177">Troubleshoot Microsoft Defender for Endpoint onboarding issues</span></span>](troubleshoot-onboarding.md)
