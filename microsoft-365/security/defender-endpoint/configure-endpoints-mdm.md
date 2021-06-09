---
title: 모바일 장치 관리 도구를 사용하여 Windows 10 장치 온보딩
description: 모바일 장치 관리 도구를 사용하여 장치에 구성 패키지를 배포하여 서비스에 온보드합니다.
keywords: mdm을 사용하여 장치 온보딩, 장치 관리, Endpoint 장치용 Microsoft Defender 온보딩, mdm
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
ms.openlocfilehash: 45aa406212fe39f088f58bf311b1aed3fed16498
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/08/2021
ms.locfileid: "52843437"
---
# <a name="onboard-windows-10-devices-using-mobile-device-management-tools"></a><span data-ttu-id="c60ac-104">모바일 장치 관리 도구를 사용하여 Windows 10 장치 온보딩</span><span class="sxs-lookup"><span data-stu-id="c60ac-104">Onboard Windows 10 devices using Mobile Device Management tools</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="c60ac-105">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="c60ac-105">**Applies to:**</span></span>
- [<span data-ttu-id="c60ac-106">엔드포인트용 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="c60ac-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="c60ac-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="c60ac-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="c60ac-108">Endpoint용 Defender를 경험하고 싶나요?</span><span class="sxs-lookup"><span data-stu-id="c60ac-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="c60ac-109">무료 평가판에 등록합니다.</span><span class="sxs-lookup"><span data-stu-id="c60ac-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-configureendpointsmdm-abovefoldlink)

<span data-ttu-id="c60ac-110">MDM(모바일 장치 관리) 솔루션을 사용하여 장치를 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c60ac-110">You can use mobile device management (MDM) solutions to configure devices.</span></span> <span data-ttu-id="c60ac-111">Endpoint용 Defender는 장치 관리 정책을 만들 수 있는 OMA-URIs MDM을 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="c60ac-111">Defender for Endpoint supports MDMs by providing OMA-URIs to create policies to manage devices.</span></span>

<span data-ttu-id="c60ac-112">Endpoint CSP용 Defender 사용에 대한 자세한 내용은 [WindowsAdvancedThreatProtection CSP](https://msdn.microsoft.com/library/windows/hardware/mt723296(v=vs.85).aspx) 및 [WindowsAdvancedThreatProtection DDF 파일](https://msdn.microsoft.com/library/windows/hardware/mt723297(v=vs.85).aspx)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="c60ac-112">For more information on using Defender for Endpoint CSP see, [WindowsAdvancedThreatProtection CSP](https://msdn.microsoft.com/library/windows/hardware/mt723296(v=vs.85).aspx) and [WindowsAdvancedThreatProtection DDF file](https://msdn.microsoft.com/library/windows/hardware/mt723297(v=vs.85).aspx).</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="c60ac-113">시작하기 전에</span><span class="sxs-lookup"><span data-stu-id="c60ac-113">Before you begin</span></span>
<span data-ttu-id="c60ac-114">디바이스를 사용하는 Microsoft Intune MDM이 등록되어 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c60ac-114">If you're using Microsoft Intune, you must have the device MDM Enrolled.</span></span> <span data-ttu-id="c60ac-115">그렇지 않으면 설정이 적용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c60ac-115">Otherwise, settings will not be applied successfully.</span></span> 

<span data-ttu-id="c60ac-116">MDM과 함께 MDM을 사용하도록 설정하는 Microsoft Intune 장치 [등록(Microsoft Intune)을 참조하세요.](/mem/intune/enrollment/device-enrollment)</span><span class="sxs-lookup"><span data-stu-id="c60ac-116">For more information on enabling MDM with Microsoft Intune, see [Device enrollment (Microsoft Intune)](/mem/intune/enrollment/device-enrollment).</span></span>

## <a name="onboard-devices-using-microsoft-intune"></a><span data-ttu-id="c60ac-117">디바이스를 사용하여 장치 온보 Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="c60ac-117">Onboard devices using Microsoft Intune</span></span>

<span data-ttu-id="c60ac-118">[![끝점용 Defender에 온보딩 장치를 표시하는 PDF Microsoft Intune ](images/onboard-intune.png)](images/onboard-intune-big.png#lightbox)</span><span class="sxs-lookup"><span data-stu-id="c60ac-118">[![Image of the PDF showing onboarding devices to Defender for Endpoint using Microsoft Intune](images/onboard-intune.png) ](images/onboard-intune-big.png#lightbox)</span></span>

<span data-ttu-id="c60ac-119">[PDF](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/security/defender-endpoint/downloads/mdatp-deployment-strategy.pdf) 또는 Visio [](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/security/defender-endpoint/downloads/mdatp-deployment-strategy.vsdx) 끝점용 Defender 배포에서 다양한 경로를 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c60ac-119">Check out the [PDF](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/security/defender-endpoint/downloads/mdatp-deployment-strategy.pdf)  or  [Visio](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/security/defender-endpoint/downloads/mdatp-deployment-strategy.vsdx) to see the various paths in deploying Defender for Endpoint.</span></span> 

<span data-ttu-id="c60ac-120">[Intune의](/intune/advanced-threat-protection)지침을 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="c60ac-120">Follow the instructions from [Intune](/intune/advanced-threat-protection).</span></span>

<span data-ttu-id="c60ac-121">Endpoint CSP용 Defender 사용에 대한 자세한 내용은 [WindowsAdvancedThreatProtection CSP](https://msdn.microsoft.com/library/windows/hardware/mt723296(v=vs.85).aspx) 및 [WindowsAdvancedThreatProtection DDF 파일](https://msdn.microsoft.com/library/windows/hardware/mt723297(v=vs.85).aspx)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="c60ac-121">For more information on using Defender for Endpoint CSP see, [WindowsAdvancedThreatProtection CSP](https://msdn.microsoft.com/library/windows/hardware/mt723296(v=vs.85).aspx) and [WindowsAdvancedThreatProtection DDF file](https://msdn.microsoft.com/library/windows/hardware/mt723297(v=vs.85).aspx).</span></span>


> [!NOTE]
> - <span data-ttu-id="c60ac-122">등록된 장치의 **상태** 정책은 읽기 전용 속성을 사용하며 수정될 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="c60ac-122">The **Health Status for onboarded devices** policy uses read-only properties and can't be remediated.</span></span>
> - <span data-ttu-id="c60ac-123">진단 데이터 보고 빈도 구성은 버전 1703의 Windows 10 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c60ac-123">Configuration of diagnostic data reporting frequency is only available for devices on Windows 10, version 1703.</span></span>


>[!TIP]
> <span data-ttu-id="c60ac-124">장치를 온보드한 후 검색 테스트를 실행하여 장치가 서비스에 제대로 온보드되었는지 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c60ac-124">After onboarding the device, you can choose to run a detection test to verify that a device is properly onboarded to the service.</span></span> <span data-ttu-id="c60ac-125">자세한 내용은 새로 온보딩된 끝점 디바이스용 Microsoft Defender에서 검색 테스트 [실행을 참조하세요.](run-detection-test.md)</span><span class="sxs-lookup"><span data-stu-id="c60ac-125">For more information, see [Run a detection test on a newly onboarded Microsoft Defender for Endpoint device](run-detection-test.md).</span></span>


<span data-ttu-id="c60ac-126">[PDF](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/security/defender-endpoint/downloads/mdatp-deployment-strategy.pdf) 또는 Visio [](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/security/defender-endpoint/downloads/mdatp-deployment-strategy.vsdx) Microsoft Defender for Endpoint 배포에서 다양한 경로를 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c60ac-126">Check out the [PDF](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/security/defender-endpoint/downloads/mdatp-deployment-strategy.pdf)  or  [Visio](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/security/defender-endpoint/downloads/mdatp-deployment-strategy.vsdx) to see the various paths in deploying Microsoft Defender for Endpoint.</span></span>

## <a name="offboard-and-monitor-devices-using-mobile-device-management-tools"></a><span data-ttu-id="c60ac-127">모바일 장치 관리 도구를 사용하여 장치 오프보드 및 모니터링</span><span class="sxs-lookup"><span data-stu-id="c60ac-127">Offboard and monitor devices using Mobile Device Management tools</span></span>
<span data-ttu-id="c60ac-128">보안상의 이유로, 오프보드 장치에 사용된 패키지는 다운로드한 날짜 30일 후에 만료됩니다.</span><span class="sxs-lookup"><span data-stu-id="c60ac-128">For security reasons, the package used to Offboard devices will expire 30 days after the date it was downloaded.</span></span> <span data-ttu-id="c60ac-129">장치에 전송된 만료된 오프보더 패키지는 거부됩니다.</span><span class="sxs-lookup"><span data-stu-id="c60ac-129">Expired offboarding packages sent to a device will be rejected.</span></span> <span data-ttu-id="c60ac-130">오프보더 패키지를 다운로드할 때 패키지 만료 날짜에 대한 알림을 하게 되고 패키지 이름에도 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="c60ac-130">When downloading an offboarding package you will be notified of the packages expiry date and it will also be included in the package name.</span></span>

> [!NOTE]
> <span data-ttu-id="c60ac-131">온보드 및 오프보더 정책을 동일한 장치에 동시에 배포하면 안 됩니다. 그렇지 않으면 예측할 수 없는 충돌이 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c60ac-131">Onboarding and offboarding policies must not be deployed on the same device at the same time, otherwise this will cause unpredictable collisions.</span></span>

1. <span data-ttu-id="c60ac-132">에서 오프보더 [패키지를 Microsoft Defender 보안 센터.](https://securitycenter.windows.com/)</span><span class="sxs-lookup"><span data-stu-id="c60ac-132">Get the offboarding package from [Microsoft Defender Security Center](https://securitycenter.windows.com/):</span></span>

   1. <span data-ttu-id="c60ac-133">탐색 창에서 **오프보더 설정**  >  **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="c60ac-133">In the navigation pane, select **Settings** > **Offboarding**.</span></span>

   1. <span data-ttu-id="c60ac-134">운영 Windows 10 로 실행을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="c60ac-134">Select Windows 10 as the operating system.</span></span>

   1. <span data-ttu-id="c60ac-135">배포 **방법 필드에서** 모바일 장치 관리 **/를 Microsoft Intune.**</span><span class="sxs-lookup"><span data-stu-id="c60ac-135">In the **Deployment method** field, select **Mobile Device Management / Microsoft Intune**.</span></span>
    
   1. <span data-ttu-id="c60ac-136">패키지 **다운로드를** 클릭하고 파일 .zip 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="c60ac-136">Click **Download package**, and save the .zip file.</span></span>

2. <span data-ttu-id="c60ac-137">패키지를 배포할 네트워크 관리자가 액세스할 수 있는 .zip 공유 읽기 전용 위치로 파일 파일의 내용을 추출합니다.</span><span class="sxs-lookup"><span data-stu-id="c60ac-137">Extract the contents of the .zip file to a shared, read-only location that can be accessed by the network administrators who will deploy the package.</span></span> <span data-ttu-id="c60ac-138">이름이 *WindowsDefenderATP_valid_until_YYYY-MM-DD.offboarding 입니다.*</span><span class="sxs-lookup"><span data-stu-id="c60ac-138">You should have a file named *WindowsDefenderATP_valid_until_YYYY-MM-DD.offboarding*.</span></span>

3. <span data-ttu-id="c60ac-139">사용자 Microsoft Intune 정책을 사용하여 지원되는 다음 OMA-URI 설정을 배포합니다.</span><span class="sxs-lookup"><span data-stu-id="c60ac-139">Use the Microsoft Intune custom configuration policy to deploy the following supported OMA-URI settings.</span></span>

      <span data-ttu-id="c60ac-140">OMA-URI: ./Device/Vendor/MSFT/WindowsAdvancedThreatProtection/Offboarding</span><span class="sxs-lookup"><span data-stu-id="c60ac-140">OMA-URI: ./Device/Vendor/MSFT/WindowsAdvancedThreatProtection/Offboarding</span></span><br/>
      <span data-ttu-id="c60ac-141">날짜 형식: 문자열</span><span class="sxs-lookup"><span data-stu-id="c60ac-141">Date type: String</span></span><br/>
      <span data-ttu-id="c60ac-142">값: [WindowsDefenderATP_valid_until_YYYY-MM-DD.offboarding 파일의 콘텐츠에서 값을 복사하여 붙여넣기]</span><span class="sxs-lookup"><span data-stu-id="c60ac-142">Value: [Copy and paste the value from the content of the WindowsDefenderATP_valid_until_YYYY-MM-DD.offboarding file]</span></span>

<span data-ttu-id="c60ac-143">정책 설정에 대한 Microsoft Intune 자세한 내용은 Windows 10 정책 설정을 [Microsoft Intune.](/intune/deploy-use/windows-10-policy-settings-in-microsoft-intune)</span><span class="sxs-lookup"><span data-stu-id="c60ac-143">For more information on Microsoft Intune policy settings see, [Windows 10 policy settings in Microsoft Intune](/intune/deploy-use/windows-10-policy-settings-in-microsoft-intune).</span></span>


> [!NOTE]
> <span data-ttu-id="c60ac-144">등록 **해제된 장치의 상태 정책은** 읽기 전용 속성을 사용하며 수정될 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="c60ac-144">The **Health Status for offboarded devices** policy uses read-only properties and can't be remediated.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="c60ac-145">오프보더링을 통해 디바이스가 포털에 센서 데이터 전송을 중지하지만, 디바이스에서 전송한 모든 경고에 대한 참조를 포함하여 장치의 데이터는 최대 6개월 동안 보존됩니다.</span><span class="sxs-lookup"><span data-stu-id="c60ac-145">Offboarding causes the device to stop sending sensor data to the portal but data from the device, including reference to any alerts it has had will be retained for up to 6 months.</span></span>

## <a name="related-topics"></a><span data-ttu-id="c60ac-146">관련 항목</span><span class="sxs-lookup"><span data-stu-id="c60ac-146">Related topics</span></span>
- [<span data-ttu-id="c60ac-147">그룹 정책을 Windows 10 장치 온보드</span><span class="sxs-lookup"><span data-stu-id="c60ac-147">Onboard Windows 10 devices using Group Policy</span></span>](configure-endpoints-gp.md)
- [<span data-ttu-id="c60ac-148">Windows 10 사용하여 장치 온보드 Microsoft Endpoint Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="c60ac-148">Onboard Windows 10 devices using Microsoft Endpoint Configuration Manager</span></span>](configure-endpoints-sccm.md)
- [<span data-ttu-id="c60ac-149">로컬 스크립트를 사용하여 Windows 10 장치 온보딩</span><span class="sxs-lookup"><span data-stu-id="c60ac-149">Onboard Windows 10 devices using a local script</span></span>](configure-endpoints-script.md)
- [<span data-ttu-id="c60ac-150">비영구 VDI(가상 데스크톱 인프라) 장치 온보딩</span><span class="sxs-lookup"><span data-stu-id="c60ac-150">Onboard non-persistent virtual desktop infrastructure (VDI) devices</span></span>](configure-endpoints-vdi.md)
- [<span data-ttu-id="c60ac-151">새로 온보딩된 엔드포인트 디바이스용 Microsoft Defender에서 검색 테스트 실행</span><span class="sxs-lookup"><span data-stu-id="c60ac-151">Run a detection test on a newly onboarded Microsoft Defender for Endpoint device</span></span>](run-detection-test.md)
- [<span data-ttu-id="c60ac-152">끝점 온보딩 문제에 대한 Microsoft Defender 문제 해결</span><span class="sxs-lookup"><span data-stu-id="c60ac-152">Troubleshoot Microsoft Defender for Endpoint onboarding issues</span></span>](troubleshoot-onboarding.md)
