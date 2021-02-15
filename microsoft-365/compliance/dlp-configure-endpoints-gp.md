---
title: 그룹 정책을 통한 Windows 10 장치 온보딩
f1.keywords: NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
audience: ITPro
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
search.appverid:
- MET150
description: 그룹 정책을 사용하여 Windows 10 장치에 구성 패키지를 배포하여 서비스에 온보드됩니다.
ms.openlocfilehash: a9e91f41b6e86e9f75d79d420c0ee830f1e3acf3
ms.sourcegitcommit: 6647055154002c7d3b8f7ce25ad53c9636bc8066
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2020
ms.locfileid: "48769448"
---
# <a name="onboard-windows-10-devices-using-group-policy"></a><span data-ttu-id="70fc0-103">그룹 정책을 사용하여 Windows 10 장치 온보드</span><span class="sxs-lookup"><span data-stu-id="70fc0-103">Onboard Windows 10 devices using Group Policy</span></span> 

<span data-ttu-id="70fc0-104">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="70fc0-104">**Applies to:**</span></span>

- [<span data-ttu-id="70fc0-105">Microsoft 365 끝점 DLP(데이터 손실 방지)</span><span class="sxs-lookup"><span data-stu-id="70fc0-105">Microsoft 365 Endpoint data loss prevention (DLP)</span></span>](/microsoft-365/compliance/endpoint-dlp-learn-about)
- <span data-ttu-id="70fc0-106">그룹 정책</span><span class="sxs-lookup"><span data-stu-id="70fc0-106">Group Policy</span></span>

> [!NOTE]
> <span data-ttu-id="70fc0-107">GP(그룹 정책) 업데이트를 사용하여 패키지를 배포하려면 Windows Server 2008 R2 이상에 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="70fc0-107">To use Group Policy (GP) updates to deploy the package, you must be on Windows Server 2008 R2 or later.</span></span>

> <span data-ttu-id="70fc0-108">Windows Server 2019의 경우 그룹 정책 기본 설정에서 만드는 XML 파일의 NT AUTHORITY\Well-Known-System-Account를 NT AUTHORITY\SYSTEM으로 대체해야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="70fc0-108">For Windows Server 2019, you may need to replace NT AUTHORITY\Well-Known-System-Account with NT AUTHORITY\SYSTEM of the XML file that the Group Policy preference creates.</span></span>

## <a name="onboard-devices-using-group-policy"></a><span data-ttu-id="70fc0-109">그룹 정책을 사용하여 디바이스 온보드</span><span class="sxs-lookup"><span data-stu-id="70fc0-109">Onboard devices using Group Policy</span></span>

1. <span data-ttu-id="70fc0-110">서비스 온보더링 마법사에서 *다운로드한* GP 구성 패키지 .zip 파일(DeviceComplianceOnboardingPackage.zip)을 니다.</span><span class="sxs-lookup"><span data-stu-id="70fc0-110">Open the GP configuration package .zip file (*DeviceComplianceOnboardingPackage.zip*) that you downloaded from the service onboarding wizard.</span></span> <span data-ttu-id="70fc0-111">Microsoft 준수 센터에서 [패키지를 다운로드할 수 있습니다.](https://compliance.microsoft.com/compliancesettings/deviceonboarding)</span><span class="sxs-lookup"><span data-stu-id="70fc0-111">You can also get the package from [Microsoft Compliance center](https://compliance.microsoft.com/compliancesettings/deviceonboarding)</span></span>

2. <span data-ttu-id="70fc0-112">탐색 창에서 설정 **장치**  >  **온보더링을 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="70fc0-112">In the navigation pane, select **Settings** > **Device Onboarding**.</span></span>

3. <span data-ttu-id="70fc0-113">배포 방법 **필드에서** 그룹 **정책을 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="70fc0-113">In the **Deployment method** field, select **Group policy**.</span></span>

4. <span data-ttu-id="70fc0-114">패키지 **다운로드를 클릭하고** .zip 파일을 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="70fc0-114">Click **Download package** and save the .zip file.</span></span>

5. <span data-ttu-id="70fc0-115">.zip 파일의 내용을 장치에서 액세스할 수 있는 읽기 전용 공유 위치로 추출합니다.</span><span class="sxs-lookup"><span data-stu-id="70fc0-115">Extract the contents of the .zip file to a shared, read-only location that can be accessed by the device.</span></span> <span data-ttu-id="70fc0-116">*OptionalParamsPolicy라는* 폴더와 *DeviceComplianceLocalOnboardingScript.cmd* 파일이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="70fc0-116">You should have a folder called *OptionalParamsPolicy* and the file *DeviceComplianceLocalOnboardingScript.cmd*.</span></span>

6. <span data-ttu-id="70fc0-117">GPMC(그룹 정책 관리 콘솔)를 열고 구성할 GPO(그룹 정책 개체)를 마우스 오른쪽 단추로 클릭하고 편집을 **클릭합니다.** [](https://docs.microsoft.com/internet-explorer/ie11-deploy-guide/group-policy-and-group-policy-mgmt-console-ie11)</span><span class="sxs-lookup"><span data-stu-id="70fc0-117">Open the [Group Policy Management Console](https://docs.microsoft.com/internet-explorer/ie11-deploy-guide/group-policy-and-group-policy-mgmt-console-ie11) (GPMC), right-click the Group Policy Object (GPO) you want to configure and click **Edit**.</span></span>

7. <span data-ttu-id="70fc0-118">그룹 정책 **관리 편집기에서** 컴퓨터 **구성으로** 이동한 다음 기본 설정으로 **이동한** 다음 **제어판 설정으로 이동합니다.**</span><span class="sxs-lookup"><span data-stu-id="70fc0-118">In the **Group Policy Management Editor**, go to **Computer configuration**, then **Preferences**, and then **Control panel settings**.</span></span>

8. <span data-ttu-id="70fc0-119">예약된 **작업을 마우스 오른쪽** 단추로 클릭하고 새로 고침을 클릭한 다음 직접 실행 작업(Windows **7 이상)을 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="70fc0-119">Right-click **Scheduled tasks**, point to **New**, and then click **Immediate Task (At least Windows 7)**.</span></span>

9. <span data-ttu-id="70fc0-120">작업 **창이** 열리면 일반 **탭으로** 이동하십시오. 보안 **옵션에서** 사용자 또는 그룹 **변경을** 클릭하고 SYSTEM을 입력한 다음 이름 **확인을** 클릭한 다음 **확인을 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="70fc0-120">In the **Task** window that opens, go to the **General** tab. Under **Security options** click **Change User or Group** and type SYSTEM and then click **Check Names** then **OK**.</span></span> <span data-ttu-id="70fc0-121">NT AUTHORITY\SYSTEM은 작업이 실행될 사용자 계정으로 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="70fc0-121">NT AUTHORITY\SYSTEM appears as the user account the task will run as.</span></span>

10. <span data-ttu-id="70fc0-122">사용자가 **로그온되어** 있는지 여부에 따라 실행을 선택하고 가장 높은 권한으로 실행 **확인란을** 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="70fc0-122">Select **Run whether user is logged on or not** and check the **Run with highest privileges** check box.</span></span>

11. <span data-ttu-id="70fc0-123">작업 **탭으로** 이동하여 새로 **고치기...** 작업 **필드에서 프로그램** **시작이 선택되어 있도록** 합니다.</span><span class="sxs-lookup"><span data-stu-id="70fc0-123">Go to the **Actions** tab and click **New...** Ensure that **Start a program** is selected in the **Action** field.</span></span> <span data-ttu-id="70fc0-124">공유 *WindowsDefenderATPOnboardingScript.cmd* 파일의 파일 이름과 위치를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="70fc0-124">Enter the file name and location of the shared *WindowsDefenderATPOnboardingScript.cmd* file.</span></span>

12. <span data-ttu-id="70fc0-125">확인을 **클릭하고** 열려 있는 GPMC 창을 닫습니다.</span><span class="sxs-lookup"><span data-stu-id="70fc0-125">Click **OK** and close any open GPMC windows.</span></span>


## <a name="offboard-devices-using-group-policy"></a><span data-ttu-id="70fc0-126">그룹 정책을 사용하여 디바이스 오프보드</span><span class="sxs-lookup"><span data-stu-id="70fc0-126">Offboard devices using Group Policy</span></span>
<span data-ttu-id="70fc0-127">보안상의 이유로 장치의 오프보드에 사용된 패키지는 다운로드한 날짜 30일 후에 만료됩니다.</span><span class="sxs-lookup"><span data-stu-id="70fc0-127">For security reasons, the package used to Offboard devices will expire 30 days after the date it was downloaded.</span></span> <span data-ttu-id="70fc0-128">장치에 전송된 만료된 오프보더 패키지는 거부됩니다.</span><span class="sxs-lookup"><span data-stu-id="70fc0-128">Expired offboarding packages sent to a device will be rejected.</span></span> <span data-ttu-id="70fc0-129">오프보더 패키지를 다운로드할 때 패키지 만료 날짜에 대한 알림을 하게 되고 패키지 이름에도 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="70fc0-129">When downloading an offboarding package you will be notified of the packages expiry date and it will also be included in the package name.</span></span>

> [!NOTE]
> <span data-ttu-id="70fc0-130">온보드 및 오프보더 정책은 동일한 장치에 동시에 배포하면 안 됩니다. 그렇지 않으면 예측할 수 없는 충돌이 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="70fc0-130">Onboarding and offboarding policies must not be deployed on the same device at the same time, otherwise this will cause unpredictable collisions.</span></span>

1. <span data-ttu-id="70fc0-131">Microsoft 준수 센터에서 [오프보더 패키지를 다운로드합니다.](https://compliance.microsoft.com/compliancesettings/deviceonboarding)</span><span class="sxs-lookup"><span data-stu-id="70fc0-131">Get the offboarding package from [Microsoft Compliance center](https://compliance.microsoft.com/compliancesettings/deviceonboarding).</span></span>

2. <span data-ttu-id="70fc0-132">탐색 창에서 설정   >  **//장치 온보더링**  >  **오프보더를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="70fc0-132">In the navigation pane, select **Settings** > **//Device onboarding** > **Offboarding**.</span></span>

3. <span data-ttu-id="70fc0-133">배포 방법 **필드에서** 그룹 **정책을 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="70fc0-133">In the **Deployment method** field, select **Group policy**.</span></span>

4. <span data-ttu-id="70fc0-134">패키지 **다운로드를 클릭하고** .zip 파일을 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="70fc0-134">Click **Download package** and save the .zip file.</span></span>

5. <span data-ttu-id="70fc0-135">.zip 파일의 내용을 장치에서 액세스할 수 있는 읽기 전용 공유 위치로 추출합니다.</span><span class="sxs-lookup"><span data-stu-id="70fc0-135">Extract the contents of the .zip file to a shared, read-only location that can be accessed by the device.</span></span> <span data-ttu-id="70fc0-136">이름이 *DeviceComplianceOffboardingScript_valid_until_YYYY-MM-DD.cmd입니다.*</span><span class="sxs-lookup"><span data-stu-id="70fc0-136">You should have a file named *DeviceComplianceOffboardingScript_valid_until_YYYY-MM-DD.cmd*.</span></span>

6. <span data-ttu-id="70fc0-137">GPMC(그룹 정책 관리 콘솔)를 열고 구성할 GPO(그룹 정책 개체)를 마우스 오른쪽 단추로 클릭하고 편집을 **클릭합니다.** [](https://docs.microsoft.com/internet-explorer/ie11-deploy-guide/group-policy-and-group-policy-mgmt-console-ie11)</span><span class="sxs-lookup"><span data-stu-id="70fc0-137">Open the [Group Policy Management Console](https://docs.microsoft.com/internet-explorer/ie11-deploy-guide/group-policy-and-group-policy-mgmt-console-ie11) (GPMC), right-click the Group Policy Object (GPO) you want to configure and click **Edit**.</span></span>

7. <span data-ttu-id="70fc0-138">그룹 정책 관리 **편집기에서** 컴퓨터  **구성,** 기본 설정, 제어판 **설정으로 이동합니다.**</span><span class="sxs-lookup"><span data-stu-id="70fc0-138">In the **Group Policy Management Editor**, go to **Computer configuration,** then **Preferences**, and then **Control panel settings**.</span></span>

8. <span data-ttu-id="70fc0-139">예약된 **작업을 마우스 오른쪽 단추로 클릭하고** 새로 고치고 **직접 실행 작업을 클릭합니다.** </span><span class="sxs-lookup"><span data-stu-id="70fc0-139">Right-click **Scheduled tasks**, point to **New**, and then click **Immediate task**.</span></span>

9. <span data-ttu-id="70fc0-140">작업 **창이** 열리면 일반 **탭으로** 이동하십시오. 보안 옵션에서 로컬 시스템 사용자 계정(BUILTIN\SYSTEM)을 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="70fc0-140">In the **Task** window that opens, go to the **General** tab. Choose the local SYSTEM user account (BUILTIN\SYSTEM) under **Security options**.</span></span>

10. <span data-ttu-id="70fc0-141">사용자가 **로그온되어** 있는지 여부에 따라 실행을 선택하고 가장 높은 권한으로 실행 **확인란을** 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="70fc0-141">Select **Run whether user is logged on or not** and check the **Run with highest privileges** check-box.</span></span>

11. <span data-ttu-id="70fc0-142">작업 **탭으로** 이동하여 새로 **고치기... 를 클릭합니다.** 작업 **필드에서 프로그램** **시작이 선택되어 있도록** 합니다.</span><span class="sxs-lookup"><span data-stu-id="70fc0-142">Go to the **Actions** tab and click **New...**. Ensure that **Start a program** is selected in the **Action** field.</span></span> <span data-ttu-id="70fc0-143">공유  *DeviceComplianceOffboardingScript_valid_until_YYYY-MM-DD.cmd* 파일의 파일 이름과 위치를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="70fc0-143">Enter the file name and location of the shared  *DeviceComplianceOffboardingScript_valid_until_YYYY-MM-DD.cmd* file.</span></span>

12. <span data-ttu-id="70fc0-144">확인을 **클릭하고** 열려 있는 GPMC 창을 닫습니다.</span><span class="sxs-lookup"><span data-stu-id="70fc0-144">Click **OK** and close any open GPMC windows.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="70fc0-145">오프보더를 통해 디바이스는 포털에 센서 데이터 전송을 중지하지만 장치의 데이터는 전송하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="70fc0-145">Offboarding causes the device to stop sending sensor data to the portal but data from the device.</span></span>


## <a name="monitor-device-configuration"></a><span data-ttu-id="70fc0-146">장치 구성 모니터링</span><span class="sxs-lookup"><span data-stu-id="70fc0-146">Monitor device configuration</span></span>
<span data-ttu-id="70fc0-147">그룹 정책을 사용하는 경우 디바이스에서 정책 배포를 모니터링할 수 있는 옵션이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="70fc0-147">With Group Policy there isn’t an option to monitor deployment of policies on the devices.</span></span> <span data-ttu-id="70fc0-148">모니터링은 포털에서 직접 수행하거나 다른 배포 도구를 사용하여 수행될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="70fc0-148">Monitoring can be done directly on the portal, or by using the different deployment tools.</span></span>

## <a name="monitor-devices-using-the-portal"></a><span data-ttu-id="70fc0-149">포털을 사용하여 장치 모니터링</span><span class="sxs-lookup"><span data-stu-id="70fc0-149">Monitor devices using the portal</span></span>
1. <span data-ttu-id="70fc0-150">Microsoft 준수 [센터로 이동](https://compliance.microsoft.com/)</span><span class="sxs-lookup"><span data-stu-id="70fc0-150">Go to [Microsoft Compliance center](https://compliance.microsoft.com/).</span></span>
2. <span data-ttu-id="70fc0-151">장치 **목록을** 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="70fc0-151">Click **Devices** list.</span></span>
3. <span data-ttu-id="70fc0-152">장치가 나타나는지 확인</span><span class="sxs-lookup"><span data-stu-id="70fc0-152">Verify that devices are appearing.</span></span>

> [!NOTE]
> <span data-ttu-id="70fc0-153">디바이스 목록에 디바이스가 표시하기 시작하는 데 며칠이 **걸릴 수 있습니다.**</span><span class="sxs-lookup"><span data-stu-id="70fc0-153">It can take several days for devices to start showing on the **Devices list**.</span></span> <span data-ttu-id="70fc0-154">여기에는 정책이 장치에 배포되는 데 걸리는 시간, 사용자가 로그온하는 데 걸리는 시간 및 끝점에서 보고를 시작하는 데 걸리는 시간이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="70fc0-154">This includes the time it takes for the policies to be distributed to the device, the time it takes before the user logs on, and the time it takes for the endpoint to start reporting.</span></span>


## <a name="related-topics"></a><span data-ttu-id="70fc0-155">관련 항목</span><span class="sxs-lookup"><span data-stu-id="70fc0-155">Related topics</span></span>
- [<span data-ttu-id="70fc0-156">Microsoft Endpoint Configuration Manager를 사용하여 Windows 10 장치 온보드</span><span class="sxs-lookup"><span data-stu-id="70fc0-156">Onboard Windows 10 devices using Microsoft Endpoint Configuration Manager</span></span>](dlp-configure-endpoints-sccm.md)
- [<span data-ttu-id="70fc0-157">모바일 장치 관리 도구를 사용하여 Windows 10 장치 온보딩</span><span class="sxs-lookup"><span data-stu-id="70fc0-157">Onboard Windows 10 devices using Mobile Device Management tools</span></span>](dlp-configure-endpoints-mdm.md)
- [<span data-ttu-id="70fc0-158">로컬 스크립트를 사용하여 Windows 10 장치 온보딩</span><span class="sxs-lookup"><span data-stu-id="70fc0-158">Onboard Windows 10 devices using a local script</span></span>](dlp-configure-endpoints-script.md)
- [<span data-ttu-id="70fc0-159">비영구 가상 데스크톱 인프라(VDI) 장치 온보딩</span><span class="sxs-lookup"><span data-stu-id="70fc0-159">Onboard non-persistent virtual desktop infrastructure (VDI) devices</span></span>](dlp-configure-endpoints-vdi.md)
- [<span data-ttu-id="70fc0-160">새로 온보딩된 Microsoft Defender ATP 장치에서 검색 테스트 실행</span><span class="sxs-lookup"><span data-stu-id="70fc0-160">Run a detection test on a newly onboarded Microsoft Defender ATP devices</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/run-detection-test)
- [<span data-ttu-id="70fc0-161">Microsoft Defender Advanced Threat Protection 온보딩 문제 해결</span><span class="sxs-lookup"><span data-stu-id="70fc0-161">Troubleshoot Microsoft Defender Advanced Threat Protection onboarding issues</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/troubleshoot-onboarding)
