---
title: 로컬 스크립트를 사용 하는 온보드 Windows 10 장치
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
description: 로컬 스크립트를 사용 하 여 장치에 구성 패키지를 배포 하 여 서비스에 등록 합니다.
ms.openlocfilehash: 74152f9488623d39e32ee4e47a452bd1daea28c7
ms.sourcegitcommit: 6647055154002c7d3b8f7ce25ad53c9636bc8066
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2020
ms.locfileid: "48769473"
---
# <a name="onboard-windows-10-devices-using-a-local-script"></a><span data-ttu-id="f6208-103">로컬 스크립트를 사용 하는 온보드 Windows 10 장치</span><span class="sxs-lookup"><span data-stu-id="f6208-103">Onboard Windows 10 devices using a local script</span></span>

<span data-ttu-id="f6208-104">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="f6208-104">**Applies to:**</span></span>

- [<span data-ttu-id="f6208-105">Microsoft 365 Endpoint data 손실 방지 (DLP)</span><span class="sxs-lookup"><span data-stu-id="f6208-105">Microsoft 365 Endpoint data loss prevention (DLP)</span></span>](/microsoft-365/compliance/endpoint-dlp-learn-about)

<span data-ttu-id="f6208-106">또한 개별 장치를 수동으로 Microsoft 365 끝점 데이터 손실 방지 기능에 등록할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f6208-106">You can also manually onboard individual devices to Microsoft 365 Endpoint data loss prevention.</span></span> <span data-ttu-id="f6208-107">네트워크의 모든 장치에 대 한 온 보 딩을 커밋 하기 전에 서비스를 테스트할 때 먼저이 작업을 수행 해야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f6208-107">You might want to do this first when testing the service before you commit to onboarding all devices in your network.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="f6208-108">이 스크립트는 최대 10 개의 장치에서 사용 하도록 최적화 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="f6208-108">This script has been optimized for use on up to 10 devices.</span></span>
>
> <span data-ttu-id="f6208-109">확장 하 여 배포 하려면 [기타 배포 옵션](dlp-configure-endpoints.md)을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="f6208-109">To deploy at scale, use [other deployment options](dlp-configure-endpoints.md).</span></span> <span data-ttu-id="f6208-110">예를 들어 [그룹 정책을 사용 하 여 온보드 Windows 10 장치](dlp-configure-endpoints-gp.md)에서 사용 가능한 스크립트를 사용 하 여 프로덕션에서 10 개 보다 많은 장치에 온 보 딩 스크립트를 배포할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f6208-110">For example, you can deploy an onboarding script to more than 10 devices in production with the script available in [Onboard Windows 10 devices using Group Policy](dlp-configure-endpoints-gp.md).</span></span>

## <a name="onboard-devices"></a><span data-ttu-id="f6208-111">온보드 장치</span><span class="sxs-lookup"><span data-stu-id="f6208-111">Onboard devices</span></span>
 
1.  <span data-ttu-id="f6208-112">서비스 온 보 딩 마법사에서 다운로드 한 GP 구성 패키지 .zip 파일 ( *DeviceComplianceOnboardingPackage.zip* )을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="f6208-112">Open the GP configuration package .zip file ( *DeviceComplianceOnboardingPackage.zip* ) that you downloaded from the service onboarding wizard.</span></span> <span data-ttu-id="f6208-113">[Microsoft 준수 센터](https://compliance.microsoft.com) 에서 패키지를 가져올 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f6208-113">You can also get the package from [Microsoft Compliance center](https://compliance.microsoft.com)</span></span>

2. <span data-ttu-id="f6208-114">탐색 창에서 **설정**  >  **장치 온 보 딩** 을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="f6208-114">In the navigation pane, select **Settings** > **Device onboarding** .</span></span>

3. <span data-ttu-id="f6208-115">**배포 방법** 필드에서 **로컬 스크립트** 를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="f6208-115">In the **Deployment method** field, select **Local Script** .</span></span>

4. <span data-ttu-id="f6208-116">**패키지 다운로드** 를 클릭 하 고 .zip 파일을 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="f6208-116">Click **Download package** and save the .zip file.</span></span>
  
5. <span data-ttu-id="f6208-117">구성 패키지의 콘텐츠를 온보드 장치 (예: 데스크톱)의 위치로 추출 합니다.</span><span class="sxs-lookup"><span data-stu-id="f6208-117">Extract the contents of the configuration package to a location on the device you want to onboard (for example, the Desktop).</span></span> <span data-ttu-id="f6208-118">*Deviceonboardingscript* 라는 파일이 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f6208-118">You should have a file named *DeviceOnboardingScript.cmd* .</span></span>

6.  <span data-ttu-id="f6208-119">장치에서 관리자 권한 명령줄 프롬프트를 열고 스크립트를 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="f6208-119">Open an elevated command-line prompt on the device and run the script:</span></span>

7.  <span data-ttu-id="f6208-120">**시작** 으로 이동 하 여 **cmd** 를 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="f6208-120">Go to **Start** and type **cmd** .</span></span>

8.  <span data-ttu-id="f6208-121">**명령 프롬프트** 를 마우스 오른쪽 단추로 클릭 하 고 **관리자 권한으로 실행** 을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="f6208-121">Right-click **Command prompt** and select **Run as administrator** .</span></span>

![관리자 권한으로 실행을 가리키는 창 시작 메뉴](../media/dlp-run-as-admin.png)

9.  <span data-ttu-id="f6208-123">스크립트 파일의 위치를 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="f6208-123">Type the location of the script file.</span></span> <span data-ttu-id="f6208-124">파일을 데스크톱에 복사한 경우 다음을 입력 합니다. *%userprofile%\Desktop\WindowsDefenderATPOnboardingScript.cmd*</span><span class="sxs-lookup"><span data-stu-id="f6208-124">If you copied the file to the desktop, type: *%userprofile%\Desktop\WindowsDefenderATPOnboardingScript.cmd*</span></span>

10.  <span data-ttu-id="f6208-125">**Enter** 키를 누르거나 **확인을** 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="f6208-125">Press the **Enter** key or click **OK** .</span></span>

<span data-ttu-id="f6208-126">장치가 호환 되는지 올바르게 보고 하는 방법에 대 한 자세한 내용은 [Microsoft Defender Advanced Threat Protection 온 보 딩 문제](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/troubleshoot-onboarding)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="f6208-126">For information on how you can manually validate that the device is compliant and correctly reports sensor data see, [Troubleshoot Microsoft Defender Advanced Threat Protection onboarding issues](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/troubleshoot-onboarding).</span></span>

## <a name="offboard-devices-using-a-local-script"></a><span data-ttu-id="f6208-127">로컬 스크립트를 사용 하는 offboard 장치</span><span class="sxs-lookup"><span data-stu-id="f6208-127">Offboard devices using a local script</span></span>
<span data-ttu-id="f6208-128">보안상의 이유로, 보드 장치에 사용 된 패키지는 다운로드 한 날짜 로부터 30 일 후에 만료 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f6208-128">For security reasons, the package used to Offboard devices will expire 30 days after the date it was downloaded.</span></span> <span data-ttu-id="f6208-129">만료 된 오프 보 딩 패키지가 장치로 전송 거부 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f6208-129">Expired offboarding packages sent to an device will be rejected.</span></span> <span data-ttu-id="f6208-130">오프 보 딩 패키지를 다운로드할 때 패키지 만료 날짜에 대 한 알림을 받게 되며 패키지 이름에도 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f6208-130">When downloading an offboarding package you will be notified of the packages expiry date and it will also be included in the package name.</span></span>

> [!NOTE]
> <span data-ttu-id="f6208-131">온 보 딩 및 오프 보 딩 정책은 동시에 같은 장치에 배포 해서는 안 되며 그렇지 않으면 예기치 않은 충돌이 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="f6208-131">Onboarding and offboarding policies must not be deployed on the same device at the same time, otherwise this will cause unpredictable collisions.</span></span>

1. <span data-ttu-id="f6208-132">[Microsoft 준수 센터](https://compliance.microsoft.com) 에서 오프 보 딩 패키지 가져오기</span><span class="sxs-lookup"><span data-stu-id="f6208-132">Get the offboarding package from [Microsoft Compliance center](https://compliance.microsoft.com)</span></span>

2. <span data-ttu-id="f6208-133">탐색 창에서 **설정**  >  **장치 오프 보 딩** 을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="f6208-133">In the navigation pane, select **Settings** > **Device offboarding** .</span></span>

3. <span data-ttu-id="f6208-134">**배포 방법** 필드에서 **로컬 스크립트** 를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="f6208-134">In the **Deployment method** field, select **Local Script** .</span></span>

4. <span data-ttu-id="f6208-135">**패키지 다운로드** 를 클릭 하 고 .zip 파일을 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="f6208-135">Click **Download package** and save the .zip file.</span></span>

5. <span data-ttu-id="f6208-136">장치에서 액세스할 수 있는 공유 읽기 전용 위치에 .zip 파일의 내용을 추출 합니다.</span><span class="sxs-lookup"><span data-stu-id="f6208-136">Extract the contents of the .zip file to a shared, read-only location that can be accessed by the devices.</span></span> <span data-ttu-id="f6208-137">*DeviceComplianceOffboardingScript_valid_until_YYYY-MM-DD* 라는 파일이 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f6208-137">You should have a file named *DeviceComplianceOffboardingScript_valid_until_YYYY-MM-DD.cmd* .</span></span>

6.  <span data-ttu-id="f6208-138">장치에서 관리자 권한 명령줄 프롬프트를 열고 스크립트를 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="f6208-138">Open an elevated command-line prompt on the device and run the script:</span></span>

7.  <span data-ttu-id="f6208-139">**시작** 으로 이동 하 여 **cmd** 를 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="f6208-139">Go to **Start** and type **cmd** .</span></span>

8.  <span data-ttu-id="f6208-140">**명령 프롬프트** 를 마우스 오른쪽 단추로 클릭 하 고 **관리자 권한으로 실행** 을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="f6208-140">Right-click **Command prompt** and select **Run as administrator** .</span></span>

![관리자 권한으로 실행을 가리키는 창 시작 메뉴](../media/dlp-run-as-admin.png)

9.  <span data-ttu-id="f6208-142">스크립트 파일의 위치를 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="f6208-142">Type the location of the script file.</span></span> <span data-ttu-id="f6208-143">파일을 데스크톱에 복사한 경우에는 *%userprofile%\desktop\ WindowsDefenderATPOffboardingScript_valid_until_YYYY-MM-DD를 입력 합니다.*</span><span class="sxs-lookup"><span data-stu-id="f6208-143">If you copied the file to the desktop, type: *%userprofile%\Desktop\WindowsDefenderATPOffboardingScript_valid_until_YYYY-MM-DD.cmd*</span></span>

10.  <span data-ttu-id="f6208-144">**Enter** 키를 누르거나 **확인을** 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="f6208-144">Press the **Enter** key or click **OK** .</span></span>

> [!IMPORTANT]
> <span data-ttu-id="f6208-145">오프 보 딩 장치에서 포털에 대 한 센서 데이터 전송을 중지 합니다.</span><span class="sxs-lookup"><span data-stu-id="f6208-145">Offboarding causes the device to stop sending sensor data to the portal.</span></span>


## <a name="monitor-device-configuration"></a><span data-ttu-id="f6208-146">장치 구성 모니터링</span><span class="sxs-lookup"><span data-stu-id="f6208-146">Monitor device configuration</span></span>
<span data-ttu-id="f6208-147">[온 보 딩 문제 해결]의 다양 한 확인 단계를 수행 하 여 https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/troubleshoot-onboarding) 스크립트가 정상적으로 완료 되 고 에이전트가 실행 되 고 있는지 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f6208-147">You can follow the different verification steps in the [Troubleshoot onboarding issues]((https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/troubleshoot-onboarding) to verify that the script completed successfully and the agent is running.</span></span>

<span data-ttu-id="f6208-148">모니터링은 포털에서 직접 또는 다양 한 배포 도구를 사용 하 여 수행할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f6208-148">Monitoring can also be done directly on the portal, or by using the different deployment tools.</span></span>

### <a name="monitor-devices-using-the-portal"></a><span data-ttu-id="f6208-149">포털을 사용 하 여 장치 모니터링</span><span class="sxs-lookup"><span data-stu-id="f6208-149">Monitor devices using the portal</span></span>
1. <span data-ttu-id="f6208-150">[Microsoft 365 준수 센터로](https://compliance.microsoft.com)이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="f6208-150">Go to [Microsoft 365 Compliance center](https://compliance.microsoft.com).</span></span>

2. <span data-ttu-id="f6208-151">**설정**  >  **장치 온 보 딩**  >  **장치** 를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="f6208-151">Choose **Settings** > **Device onboarding** > **Devices** .</span></span>

3. <span data-ttu-id="f6208-152">장치가 나타나는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="f6208-152">Verify that devices are appearing.</span></span>


## <a name="related-topics"></a><span data-ttu-id="f6208-153">관련 항목</span><span class="sxs-lookup"><span data-stu-id="f6208-153">Related topics</span></span>
- [<span data-ttu-id="f6208-154">그룹 정책을 사용 하는 온보드 Windows 10 장치</span><span class="sxs-lookup"><span data-stu-id="f6208-154">Onboard Windows 10 devices using Group Policy</span></span>](dlp-configure-endpoints-gp.md)
- [<span data-ttu-id="f6208-155">Microsoft Endpoint Configuration Manager를 사용 하는 Windows 10 장치 온보드</span><span class="sxs-lookup"><span data-stu-id="f6208-155">Onboard Windows 10 devices using Microsoft Endpoint Configuration Manager</span></span>](dlp-configure-endpoints-sccm.md)
- [<span data-ttu-id="f6208-156">모바일 장치 관리 도구를 사용 하는 온보드 Windows 10 장치</span><span class="sxs-lookup"><span data-stu-id="f6208-156">Onboard Windows 10 devices using Mobile Device Management tools</span></span>](dlp-configure-endpoints-mdm.md)
- [<span data-ttu-id="f6208-157">온보드 VDI (가상 데스크톱 인프라) 장치 (비영구)</span><span class="sxs-lookup"><span data-stu-id="f6208-157">Onboard non-persistent virtual desktop infrastructure (VDI) devices</span></span>](dlp-configure-endpoints-vdi.md)
- [<span data-ttu-id="f6208-158">새로 등록 Microsoft Defender ATP 장치에서 검색 테스트 실행</span><span class="sxs-lookup"><span data-stu-id="f6208-158">Run a detection test on a newly onboarded Microsoft Defender ATP device</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/run-detection-test)
- [<span data-ttu-id="f6208-159">Microsoft Defender Advanced Threat Protection 온 보 딩 문제 해결</span><span class="sxs-lookup"><span data-stu-id="f6208-159">Troubleshoot Microsoft Defender Advanced Threat Protection onboarding issues</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/troubleshoot-onboarding)
