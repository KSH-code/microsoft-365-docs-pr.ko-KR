---
title: 모바일 장치 관리 도구를 사용 하는 온보드 Windows 10 장치
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
description: 모바일 장치 관리 도구를 사용 하 여 장치에 구성 패키지를 배포 하 여 서비스에 등록 되도록 합니다.
ms.openlocfilehash: 1480c918589a1f00e00ceb1233e9a62887ccff32
ms.sourcegitcommit: 6647055154002c7d3b8f7ce25ad53c9636bc8066
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2020
ms.locfileid: "48769483"
---
# <a name="onboard-windows-10-devices-using-mobile-device-management-tools"></a><span data-ttu-id="a68c9-103">모바일 장치 관리 도구를 사용 하는 온보드 Windows 10 장치</span><span class="sxs-lookup"><span data-stu-id="a68c9-103">Onboard Windows 10 devices using Mobile Device Management tools</span></span>

<span data-ttu-id="a68c9-104">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="a68c9-104">**Applies to:**</span></span>

- [<span data-ttu-id="a68c9-105">Microsoft 365 Endpoint data 손실 방지 (DLP)</span><span class="sxs-lookup"><span data-stu-id="a68c9-105">Microsoft 365 Endpoint data loss prevention (DLP)</span></span>](/microsoft-365/compliance/endpoint-dlp-learn-about)

<span data-ttu-id="a68c9-106">MDM (모바일 장치 관리) 솔루션을 사용 하 여 장치를 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a68c9-106">You can use mobile device management (MDM) solutions to configure devices.</span></span> <span data-ttu-id="a68c9-107">Microsoft 365 Endpoint data 손실 방지는 장치를 관리 하기 위한 정책을 만들기 위해 OMA-URIs 제공 하 여 MDMs를 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="a68c9-107">Microsoft 365 Endpoint data loss prevention supports MDMs by providing OMA-URIs to create policies to manage devices.</span></span>


## <a name="before-you-begin"></a><span data-ttu-id="a68c9-108">시작하기 전에</span><span class="sxs-lookup"><span data-stu-id="a68c9-108">Before you begin</span></span>
<span data-ttu-id="a68c9-109">Microsoft Intune을 사용 하는 경우에는 장치 MDM이 등록 되어 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a68c9-109">If you're using Microsoft Intune, you must have the device MDM Enrolled.</span></span> <span data-ttu-id="a68c9-110">그렇지 않으면 설정이 제대로 적용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="a68c9-110">Otherwise, settings will not be applied successfully.</span></span> 

<span data-ttu-id="a68c9-111">Microsoft Intune에서 MDM을 사용 하도록 설정 하는 방법에 대 한 자세한 내용은 [Device 등록할 (Microsoft intune)](https://docs.microsoft.com/mem/intune/enrollment/device-enrollment)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="a68c9-111">For more information on enabling MDM with Microsoft Intune, see [Device enrollment (Microsoft Intune)](https://docs.microsoft.com/mem/intune/enrollment/device-enrollment).</span></span>

## <a name="onboard-devices-using-microsoft-intune"></a><span data-ttu-id="a68c9-112">Microsoft Intune을 사용 하는 온보드 장치</span><span class="sxs-lookup"><span data-stu-id="a68c9-112">Onboard devices using Microsoft Intune</span></span>

<span data-ttu-id="a68c9-113">[Intune](https://docs.microsoft.com/intune/advanced-threat-protection)의 지침을 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="a68c9-113">Follow the instructions from [Intune](https://docs.microsoft.com/intune/advanced-threat-protection).</span></span>

> [!NOTE]
> - <span data-ttu-id="a68c9-114">**등록 장치 정책에 대 한** 상태는 읽기 전용 속성을 사용 하며 수정할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="a68c9-114">The **Health Status for onboarded devices** policy uses read-only properties and can't be remediated.</span></span>

## <a name="offboard-and-monitor-devices-using-mobile-device-management-tools"></a><span data-ttu-id="a68c9-115">모바일 장치 관리 도구를 사용 하는 offboard and monitor devices</span><span class="sxs-lookup"><span data-stu-id="a68c9-115">Offboard and monitor devices using Mobile Device Management tools</span></span>

<span data-ttu-id="a68c9-116">보안상의 이유로, 보드 장치에 사용 된 패키지는 다운로드 한 날짜 로부터 30 일 후에 만료 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a68c9-116">For security reasons, the package used to Offboard devices will expire 30 days after the date it was downloaded.</span></span> <span data-ttu-id="a68c9-117">만료 된 오프 보 딩 패키지가 장치로 전송 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a68c9-117">Expired offboarding packages sent to a device will be rejected.</span></span> <span data-ttu-id="a68c9-118">오프 보 딩 패키지를 다운로드할 때 패키지 만료 날짜에 대 한 알림을 받게 되며 패키지 이름에도 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a68c9-118">When downloading an offboarding package you will be notified of the packages expiry date and it will also be included in the package name.</span></span>

> [!NOTE]
> <span data-ttu-id="a68c9-119">온 보 딩 및 오프 보 딩 정책은 동시에 같은 장치에 배포 해서는 안 되며 그렇지 않으면 예기치 않은 충돌이 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="a68c9-119">Onboarding and offboarding policies must not be deployed on the same device at the same time, otherwise this will cause unpredictable collisions.</span></span>

1. <span data-ttu-id="a68c9-120">[Microsoft 준수 센터](https://compliance.microsoft.com/)에서 오프 보 딩 패키지를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="a68c9-120">Get the offboarding package from [Microsoft Compliance center](https://compliance.microsoft.com/).</span></span>

2. <span data-ttu-id="a68c9-121">탐색 창에서 **설정**  >  **장치 온 보** 딩을 선택  >  **Offboarding** 합니다.</span><span class="sxs-lookup"><span data-stu-id="a68c9-121">In the navigation pane, select **Settings** > **Device onboarding** > **Offboarding** .</span></span>

3. <span data-ttu-id="a68c9-122">**배포 방법** 필드에서 **모바일 장치 관리/Microsoft Intune** 을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="a68c9-122">In the **Deployment method** field, select **Mobile Device Management / Microsoft Intune** .</span></span>
    
4. <span data-ttu-id="a68c9-123">**패키지 다운로드** 를 클릭 하 고 .zip 파일을 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="a68c9-123">Click **Download package** , and save the .zip file.</span></span>

5. <span data-ttu-id="a68c9-124">패키지를 배포할 네트워크 관리자가 액세스할 수 있는 공유, 읽기 전용 위치에 .zip 파일의 내용을 추출 합니다.</span><span class="sxs-lookup"><span data-stu-id="a68c9-124">Extract the contents of the .zip file to a shared, read-only location that can be accessed by the network administrators who will deploy the package.</span></span> <span data-ttu-id="a68c9-125">DeviceCompliance_valid_until_YYYY에는 *-yyyy-mm-dd* 라는 파일이 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a68c9-125">You should have a file named *DeviceCompliance_valid_until_YYYY-MM-DD.offboarding* .</span></span>

6. <span data-ttu-id="a68c9-126">Microsoft Intune 사용자 지정 구성 정책을 사용 하 여 지원 되는 다음 OMA URI 설정을 배포 합니다.</span><span class="sxs-lookup"><span data-stu-id="a68c9-126">Use the Microsoft Intune custom configuration policy to deploy the following supported OMA-URI settings.</span></span>

      <span data-ttu-id="a68c9-127">OMA-URI:./Device/Vendor/MSFT/WindowsAdvancedThreatProtection/Offboarding</span><span class="sxs-lookup"><span data-stu-id="a68c9-127">OMA-URI: ./Device/Vendor/MSFT/WindowsAdvancedThreatProtection/Offboarding</span></span>      
      <span data-ttu-id="a68c9-128">날짜 형식: 문자열</span><span class="sxs-lookup"><span data-stu-id="a68c9-128">Date type: String</span></span>      
      <span data-ttu-id="a68c9-129">값: [DeviceCompliance_valid_until_YYYY-YYYY-MM-DD 파일의 내용에서 값을 복사 하 여 붙여 넣습니다.]</span><span class="sxs-lookup"><span data-stu-id="a68c9-129">Value: [Copy and paste the value from the content of the DeviceCompliance_valid_until_YYYY-MM-DD.offboarding file]</span></span>

<span data-ttu-id="a68c9-130">Microsoft Intune 정책 설정에 대 한 자세한 내용은 [Microsoft intune에서 Windows 10 정책 설정을](https://docs.microsoft.com/intune/deploy-use/windows-10-policy-settings-in-microsoft-intune)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="a68c9-130">For more information on Microsoft Intune policy settings see, [Windows 10 policy settings in Microsoft Intune](https://docs.microsoft.com/intune/deploy-use/windows-10-policy-settings-in-microsoft-intune).</span></span>

> [!NOTE]
> <span data-ttu-id="a68c9-131">**Offboarded 장치 정책에 대 한** 상태는 읽기 전용 속성을 사용 하며 수정할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="a68c9-131">The **Health Status for offboarded devices** policy uses read-only properties and can't be remediated.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="a68c9-132">오프 보 딩은 장치에서 포털에 센서 데이터를 전송 하지 않고 장치에서 가져온 데이터에 대 한 참조를 포함 하 여 최대 6 개월 동안 보존 되도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="a68c9-132">Offboarding causes the device to stop sending sensor data to the portal but data from the device, including reference to any alerts it has had will be retained for up to 6 months.</span></span>

## <a name="related-topics"></a><span data-ttu-id="a68c9-133">관련 항목</span><span class="sxs-lookup"><span data-stu-id="a68c9-133">Related topics</span></span>
- [<span data-ttu-id="a68c9-134">그룹 정책을 사용 하는 온보드 Windows 10 장치</span><span class="sxs-lookup"><span data-stu-id="a68c9-134">Onboard Windows 10 devices using Group Policy</span></span>](dlp-configure-endpoints-gp.md)
- [<span data-ttu-id="a68c9-135">Microsoft Endpoint Configuration Manager를 사용 하는 Windows 10 장치 온보드</span><span class="sxs-lookup"><span data-stu-id="a68c9-135">Onboard Windows 10 devices using Microsoft Endpoint Configuration Manager</span></span>](dlp-configure-endpoints-sccm.md)
- [<span data-ttu-id="a68c9-136">로컬 스크립트를 사용 하는 온보드 Windows 10 장치</span><span class="sxs-lookup"><span data-stu-id="a68c9-136">Onboard Windows 10 devices using a local script</span></span>](dlp-configure-endpoints-script.md)
- [<span data-ttu-id="a68c9-137">온보드 VDI (가상 데스크톱 인프라) 장치 (비영구)</span><span class="sxs-lookup"><span data-stu-id="a68c9-137">Onboard non-persistent virtual desktop infrastructure (VDI) devices</span></span>](dlp-configure-endpoints-vdi.md)
- [<span data-ttu-id="a68c9-138">Microsoft Defender Advanced Threat Protection 온 보 딩 문제 해결</span><span class="sxs-lookup"><span data-stu-id="a68c9-138">Troubleshoot Microsoft Defender Advanced Threat Protection onboarding issues</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/troubleshoot-onboarding)
