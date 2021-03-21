---
title: 모바일 장치 관리 도구를 사용하여 Windows 10 장치 온보딩
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
description: 모바일 장치 관리 도구를 사용하여 장치에 구성 패키지를 배포하여 서비스에 온보드합니다.
ms.openlocfilehash: 1ad1115308257fa3ce63f10edebb9129638fd52f
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/19/2021
ms.locfileid: "50917994"
---
# <a name="onboard-windows-10-devices-using-mobile-device-management-tools"></a><span data-ttu-id="81ab4-103">모바일 장치 관리 도구를 사용하여 Windows 10 장치 온보딩</span><span class="sxs-lookup"><span data-stu-id="81ab4-103">Onboard Windows 10 devices using Mobile Device Management tools</span></span>

<span data-ttu-id="81ab4-104">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="81ab4-104">**Applies to:**</span></span>

- [<span data-ttu-id="81ab4-105">Microsoft 365 끝점 DLP(데이터 손실 방지)</span><span class="sxs-lookup"><span data-stu-id="81ab4-105">Microsoft 365 Endpoint data loss prevention (DLP)</span></span>](./endpoint-dlp-learn-about.md)

<span data-ttu-id="81ab4-106">MDM(모바일 장치 관리) 솔루션을 사용하여 장치를 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="81ab4-106">You can use mobile device management (MDM) solutions to configure devices.</span></span> <span data-ttu-id="81ab4-107">Microsoft 365 엔드포인트 데이터 손실 방지는 장치 관리 정책을 만들 수 있는 OMA-URIs MDM을 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="81ab4-107">Microsoft 365 Endpoint data loss prevention supports MDMs by providing OMA-URIs to create policies to manage devices.</span></span>


## <a name="before-you-begin"></a><span data-ttu-id="81ab4-108">시작하기 전에</span><span class="sxs-lookup"><span data-stu-id="81ab4-108">Before you begin</span></span>
<span data-ttu-id="81ab4-109">Microsoft Intune을 사용하는 경우 디바이스 MDM이 등록되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="81ab4-109">If you're using Microsoft Intune, you must have the device MDM Enrolled.</span></span> <span data-ttu-id="81ab4-110">그렇지 않으면 설정이 적용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="81ab4-110">Otherwise, settings will not be applied successfully.</span></span> 

<span data-ttu-id="81ab4-111">Microsoft Intune에서 MDM을 사용하도록 설정하는 데 대한 자세한 내용은 [장치 등록(Microsoft Intune)을 참조하세요.](/mem/intune/enrollment/device-enrollment)</span><span class="sxs-lookup"><span data-stu-id="81ab4-111">For more information on enabling MDM with Microsoft Intune, see [Device enrollment (Microsoft Intune)](/mem/intune/enrollment/device-enrollment).</span></span>

## <a name="onboard-devices-using-microsoft-intune"></a><span data-ttu-id="81ab4-112">Microsoft Intune을 사용하여 장치 온보드</span><span class="sxs-lookup"><span data-stu-id="81ab4-112">Onboard devices using Microsoft Intune</span></span>

<span data-ttu-id="81ab4-113">[Intune의](/intune/advanced-threat-protection)지침을 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="81ab4-113">Follow the instructions from [Intune](/intune/advanced-threat-protection).</span></span>

> [!NOTE]
> - <span data-ttu-id="81ab4-114">등록된 장치의 **상태** 정책은 읽기 전용 속성을 사용하며 수정될 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="81ab4-114">The **Health Status for onboarded devices** policy uses read-only properties and can't be remediated.</span></span>

## <a name="offboard-and-monitor-devices-using-mobile-device-management-tools"></a><span data-ttu-id="81ab4-115">모바일 장치 관리 도구를 사용하여 장치 오프보드 및 모니터링</span><span class="sxs-lookup"><span data-stu-id="81ab4-115">Offboard and monitor devices using Mobile Device Management tools</span></span>

<span data-ttu-id="81ab4-116">보안상의 이유로, 오프보드 장치에 사용된 패키지는 다운로드한 날짜 30일 후에 만료됩니다.</span><span class="sxs-lookup"><span data-stu-id="81ab4-116">For security reasons, the package used to Offboard devices will expire 30 days after the date it was downloaded.</span></span> <span data-ttu-id="81ab4-117">장치에 전송된 만료된 오프보더 패키지는 거부됩니다.</span><span class="sxs-lookup"><span data-stu-id="81ab4-117">Expired offboarding packages sent to a device will be rejected.</span></span> <span data-ttu-id="81ab4-118">오프보더 패키지를 다운로드할 때 패키지 만료 날짜에 대한 알림을 하게 되고 패키지 이름에도 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="81ab4-118">When downloading an offboarding package you will be notified of the packages expiry date and it will also be included in the package name.</span></span>

> [!NOTE]
> <span data-ttu-id="81ab4-119">온보드 및 오프보더 정책을 동일한 장치에 동시에 배포하면 안 됩니다. 그렇지 않으면 예측할 수 없는 충돌이 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="81ab4-119">Onboarding and offboarding policies must not be deployed on the same device at the same time, otherwise this will cause unpredictable collisions.</span></span>

1. <span data-ttu-id="81ab4-120">Microsoft 준수 센터에서 [오프보더 패키지를 다운로드합니다.](https://compliance.microsoft.com/)</span><span class="sxs-lookup"><span data-stu-id="81ab4-120">Get the offboarding package from [Microsoft Compliance center](https://compliance.microsoft.com/).</span></span>

2. <span data-ttu-id="81ab4-121">탐색 창에서 설정 **장치**  >  **온보더링 오프보링**  >  **을 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="81ab4-121">In the navigation pane, select **Settings** > **Device onboarding** > **Offboarding**.</span></span>

3. <span data-ttu-id="81ab4-122">배포 **방법 필드에서** 모바일 장치 관리 **/ Microsoft Intune 을 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="81ab4-122">In the **Deployment method** field, select **Mobile Device Management / Microsoft Intune**.</span></span>
    
4. <span data-ttu-id="81ab4-123">패키지 **다운로드를** 클릭하고 .zip 파일을 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="81ab4-123">Click **Download package**, and save the .zip file.</span></span>

5. <span data-ttu-id="81ab4-124">패키지를 배포할 네트워크 관리자가 액세스할 수 있는 공유 읽기 전용 위치에 .zip 파일의 내용을 추출합니다.</span><span class="sxs-lookup"><span data-stu-id="81ab4-124">Extract the contents of the .zip file to a shared, read-only location that can be accessed by the network administrators who will deploy the package.</span></span> <span data-ttu-id="81ab4-125">이름이 *DeviceCompliance_valid_until_YYYY-MM-DD.offboarding 입니다.*</span><span class="sxs-lookup"><span data-stu-id="81ab4-125">You should have a file named *DeviceCompliance_valid_until_YYYY-MM-DD.offboarding*.</span></span>

6. <span data-ttu-id="81ab4-126">Microsoft Intune 사용자 지정 구성 정책을 사용하여 지원되는 다음 OMA-URI 설정을 배포합니다.</span><span class="sxs-lookup"><span data-stu-id="81ab4-126">Use the Microsoft Intune custom configuration policy to deploy the following supported OMA-URI settings.</span></span>

      <span data-ttu-id="81ab4-127">OMA-URI: ./Device/Vendor/MSFT/WindowsAdvancedThreatProtection/Offboarding</span><span class="sxs-lookup"><span data-stu-id="81ab4-127">OMA-URI: ./Device/Vendor/MSFT/WindowsAdvancedThreatProtection/Offboarding</span></span>      
      <span data-ttu-id="81ab4-128">날짜 형식: 문자열</span><span class="sxs-lookup"><span data-stu-id="81ab4-128">Date type: String</span></span>      
      <span data-ttu-id="81ab4-129">값: [DeviceCompliance_valid_until_YYYY-MM-DD.offboarding 파일의 콘텐츠에서 값을 복사하여 붙여넣기]</span><span class="sxs-lookup"><span data-stu-id="81ab4-129">Value: [Copy and paste the value from the content of the DeviceCompliance_valid_until_YYYY-MM-DD.offboarding file]</span></span>

<span data-ttu-id="81ab4-130">Microsoft Intune 정책 설정에 대한 자세한 내용은 [Microsoft Intune의 Windows 10 정책 설정을 참조하세요.](/intune/deploy-use/windows-10-policy-settings-in-microsoft-intune)</span><span class="sxs-lookup"><span data-stu-id="81ab4-130">For more information on Microsoft Intune policy settings see, [Windows 10 policy settings in Microsoft Intune](/intune/deploy-use/windows-10-policy-settings-in-microsoft-intune).</span></span>

> [!NOTE]
> <span data-ttu-id="81ab4-131">등록 **해제된 장치의 상태 정책은** 읽기 전용 속성을 사용하며 수정될 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="81ab4-131">The **Health Status for offboarded devices** policy uses read-only properties and can't be remediated.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="81ab4-132">오프보더링을 통해 디바이스가 포털에 센서 데이터 전송을 중지하지만, 디바이스에서 전송한 모든 경고에 대한 참조를 포함하여 장치의 데이터는 최대 6개월 동안 보존됩니다.</span><span class="sxs-lookup"><span data-stu-id="81ab4-132">Offboarding causes the device to stop sending sensor data to the portal but data from the device, including reference to any alerts it has had will be retained for up to 6 months.</span></span>

## <a name="related-topics"></a><span data-ttu-id="81ab4-133">관련 주제</span><span class="sxs-lookup"><span data-stu-id="81ab4-133">Related topics</span></span>
- [<span data-ttu-id="81ab4-134">그룹 정책을 사용하여 Windows 10 장치 온보드</span><span class="sxs-lookup"><span data-stu-id="81ab4-134">Onboard Windows 10 devices using Group Policy</span></span>](dlp-configure-endpoints-gp.md)
- [<span data-ttu-id="81ab4-135">Microsoft Endpoint Configuration Manager를 사용하여 Windows 10 장치 온보드</span><span class="sxs-lookup"><span data-stu-id="81ab4-135">Onboard Windows 10 devices using Microsoft Endpoint Configuration Manager</span></span>](dlp-configure-endpoints-sccm.md)
- [<span data-ttu-id="81ab4-136">로컬 스크립트를 사용하여 Windows 10 장치 온보딩</span><span class="sxs-lookup"><span data-stu-id="81ab4-136">Onboard Windows 10 devices using a local script</span></span>](dlp-configure-endpoints-script.md)
- [<span data-ttu-id="81ab4-137">비영구 가상 데스크톱 인프라(VDI) 장치 온보딩</span><span class="sxs-lookup"><span data-stu-id="81ab4-137">Onboard non-persistent virtual desktop infrastructure (VDI) devices</span></span>](dlp-configure-endpoints-vdi.md)
- [<span data-ttu-id="81ab4-138">Microsoft Defender Advanced Threat Protection 온보딩 문제 해결</span><span class="sxs-lookup"><span data-stu-id="81ab4-138">Troubleshoot Microsoft Defender Advanced Threat Protection onboarding issues</span></span>](/windows/security/threat-protection/microsoft-defender-atp/troubleshoot-onboarding)