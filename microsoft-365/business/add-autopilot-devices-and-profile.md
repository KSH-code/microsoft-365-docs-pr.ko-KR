---
title: 단계별 가이드를 사용하여 AutoPilot 장치 및 프로필 추가
f1.keywords:
- NOCSH
ms.author: efrene
author: efrene
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
ms.collection:
- M365-subscription-management
- M365-identity-device-management
localization_priority: Normal
ms.custom:
- Core_O365Admin_Migration
- MiniMaven
- MSB365
- OKR_SMB_M365
- seo-marvel-mar
- AdminSurgePortfolio
- AdminTemplateSet
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: be5b6d90-3344-4c5e-bf40-5733eb845beb
description: AutoPilot을 사용하여 Windows 사용할 수 있도록 비즈니스용 Windows 10 디바이스를 설정하는 방법을 배워야 합니다.
ms.openlocfilehash: f160ddcd1e41bd44c908ecc8bbd30a9819f76902
ms.sourcegitcommit: 00f001019c653269d85718d410f970887d904304
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/12/2021
ms.locfileid: "53393442"
---
# <a name="use-the-step-by-step-guide-to-add-autopilot-devices-and-profile"></a><span data-ttu-id="fab14-103">단계별 가이드를 사용하여 AutoPilot 장치 및 프로필 추가</span><span class="sxs-lookup"><span data-stu-id="fab14-103">Use the step-by-step guide to add Autopilot devices and profile</span></span>

<span data-ttu-id="fab14-104">AutoPilot을 Windows 사용하여 비즈니스용  새 Windows 10 디바이스를 설정할 수 있으므로 직원들에게 제공될 때 사용할 준비가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="fab14-104">You can use Windows AutoPilot to set up **new** Windows 10 devices for your business so they're ready for use when you give them to your employees.</span></span>
  
## <a name="device-requirements"></a><span data-ttu-id="fab14-105">장치 요구 사항</span><span class="sxs-lookup"><span data-stu-id="fab14-105">Device requirements</span></span>

<span data-ttu-id="fab14-106">장치는 다음 요구 사항을 충족해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="fab14-106">Devices must meet these requirements:</span></span>
  
- <span data-ttu-id="fab14-107">Windows 10 버전 1703 이상</span><span class="sxs-lookup"><span data-stu-id="fab14-107">Windows 10, version 1703 or later</span></span>
    
- <span data-ttu-id="fab14-108">2016년 1월 환경을 Windows 새 장치</span><span class="sxs-lookup"><span data-stu-id="fab14-108">New devices that haven't been through Windows out-of-box experience</span></span>
    
## <a name="use-the-setup-guide-to-create-devices-and-profiles"></a><span data-ttu-id="fab14-109">설정 가이드를 사용하여 장치와 프로필 만들기</span><span class="sxs-lookup"><span data-stu-id="fab14-109">Use the setup guide to create devices and profiles</span></span>

<span data-ttu-id="fab14-110">장치 그룹 또는 프로필을 아직 만들지 않은 경우 시작하는 가장 좋은 방법은 단계별 가이드를 사용하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="fab14-110">If you haven't created device groups or profiles yet, the best way to get started is by using the step-by-step guide.</span></span> <span data-ttu-id="fab14-111">가이드를 [사용하지](create-and-edit-autopilot-devices.md) 않고 [](create-and-edit-autopilot-profiles.md) 디바이스를 추가하고 프로필을 할당할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fab14-111">You can also [add devices](create-and-edit-autopilot-devices.md) and [assign profiles](create-and-edit-autopilot-profiles.md) to them without using the guide.</span></span> 
  
1. <span data-ttu-id="fab14-112"><a href="https://go.microsoft.com/fwlink/p/?linkid=837890" target="_blank">https://admin.microsoft.com</a>의 관리 센터로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="fab14-112">Go to the admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=837890" target="_blank">https://admin.microsoft.com</a>.</span></span>

2. <span data-ttu-id="fab14-113">왼쪽 탐색 창에서 **장치** \> **AutoPilot 을 선택 합니다.**</span><span class="sxs-lookup"><span data-stu-id="fab14-113">On the left navigation pane, choose **Devices** \> **AutoPilot**.</span></span>

    ![관리 센터에서 디바이스를 선택한 다음 AutoPilot을 선택하세요.](../media/AutoPilot.png)
  
2. <span data-ttu-id="fab14-115">**AutoPilot 페이지에서** 시작 가이드를 **클릭하거나 탭합니다.**</span><span class="sxs-lookup"><span data-stu-id="fab14-115">On the **AutoPilot** page, click or tap **Start guide**.</span></span>
    
    ![Click Start guide for step-by-step instructions for Autopilot.](../media/31662655-d1e6-437d-87ea-c0dec5da56f7.png)
  
3. <span data-ttu-id="fab14-117">장치 **업로드 .csv** 파일 페이지에서 준비된 .CSV 위치로 이동한 후 다음  \> **열기 를 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="fab14-117">On the **Upload .csv file with list of devices** page, browse to a location where you have the prepared .CSV file, then **Open** \> **Next**.</span></span> <span data-ttu-id="fab14-118">파일에는 다음 세 개의 헤더가 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="fab14-118">The file must have three headers:</span></span>
    
    - <span data-ttu-id="fab14-119">A 열: 장치 일련 번호</span><span class="sxs-lookup"><span data-stu-id="fab14-119">Column A: Device Serial Number</span></span>
    
    - <span data-ttu-id="fab14-120">B 열: Windows 제품 ID</span><span class="sxs-lookup"><span data-stu-id="fab14-120">Column B: Windows Product ID</span></span>
    
    - <span data-ttu-id="fab14-121">C 열: 하드웨어 해시</span><span class="sxs-lookup"><span data-stu-id="fab14-121">Column C: Hardware Hash</span></span>
    
    <span data-ttu-id="fab14-122">하드웨어 공급업체에서 이 정보를 얻거나 [Get-WindowsAutoPilotInfo PowerShell](https://www.powershellgallery.com/packages/Get-WindowsAutoPilotInfo) 스크립트를 사용하여 CSV 파일을 생성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fab14-122">You can get this information from your hardware vendor, or you can use the [Get-WindowsAutoPilotInfo PowerShell script](https://www.powershellgallery.com/packages/Get-WindowsAutoPilotInfo) to generate a CSV file.</span></span> 
    
    <span data-ttu-id="fab14-p103">자세한 내용은 [장치 목록 CSV 파일](../admin/misc/device-list.md)을 참조하세요. **장치 목록이 포함된 .csv 파일 업로드** 페이지에서 샘플 파일을 다운로드할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fab14-p103">For more information, see [Device list CSV-file](../admin/misc/device-list.md). You can also download a sample file on the **Upload .csv file with list of devices** page.</span></span> 
    
> [!NOTE]
> <span data-ttu-id="fab14-125">이 스크립트는 WMI를 사용하여 고객이 Autopilot을 사용하여 디바이스를 등록하는 데 Windows 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="fab14-125">This script uses WMI to retrieve properties needed for a customer to register a device with Windows Autopilot.</span></span> <span data-ttu-id="fab14-126">디바이스를 등록할 필요는 아니며 출력 CSV에 NULL인 PKID가 완전히 괜찮기 때문에 결과 CSV 파일이 PKID(Windows 제품 ID) 값을 수집하지 않는 것은 일반적입니다.</span><span class="sxs-lookup"><span data-stu-id="fab14-126">Note that it is normal for the resulting CSV file to not collect a Windows Product ID (PKID) value since this is not required to register a device and PKID being NULL in the output CSV is totally fine.</span></span> <span data-ttu-id="fab14-127">일련 번호와 하드웨어 해시만 채워지기만 합니다.</span><span class="sxs-lookup"><span data-stu-id="fab14-127">Only the serial number and hardware hash will be populated.</span></span>
    
4. <span data-ttu-id="fab14-128">프로필 **할당 페이지에서** 기존 프로필을 선택하거나 새 프로필을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fab14-128">On the **Assign a profile** page, you can either pick an existing profile or create a new one.</span></span> <span data-ttu-id="fab14-129">아직 만들지 않은 경우 하나를 만들지 묻는 메시지가 표시될 것입니다.</span><span class="sxs-lookup"><span data-stu-id="fab14-129">If you don't have one yet, you'll be prompted to create one.</span></span> 
    
    <span data-ttu-id="fab14-130">프로필은 단일 장치 또는 장치 그룹에 적용할 수 있는 설정 모음입니다.</span><span class="sxs-lookup"><span data-stu-id="fab14-130">A profile is a collection of settings that can be applied to a single device or to a group of devices.</span></span>
    
    <span data-ttu-id="fab14-131">기본 기능은 필수로 설정되며 자동으로 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="fab14-131">The default features are required and are set automatically.</span></span> <span data-ttu-id="fab14-132">기본 기능은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="fab14-132">The default features are:</span></span>
    
    - <span data-ttu-id="fab14-133">등록 Cortana, OneDrive 및 OEM 등록을 건너뜁.</span><span class="sxs-lookup"><span data-stu-id="fab14-133">Skip Cortana, OneDrive, and OEM registration.</span></span>
    
    - <span data-ttu-id="fab14-134">회사 브랜드의 로그인 환경을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="fab14-134">Create sign-in experience with your company brand.</span></span>
    
    - <span data-ttu-id="fab14-135">커넥트 계정을 Azure Active Directory 등록하고 자동으로 등록하여 계정을 Microsoft 365 Business Premium.</span><span class="sxs-lookup"><span data-stu-id="fab14-135">Connect your devices to Azure Active Directory accounts, and automatically enroll them to be managed by Microsoft 365 Business Premium.</span></span>
    
    <span data-ttu-id="fab14-136">자세한 내용은 [AutoPilot 프로필 설정 정보를 참조하세요.](autopilot-profile-settings.md)</span><span class="sxs-lookup"><span data-stu-id="fab14-136">For more information, see [About AutoPilot Profile settings](autopilot-profile-settings.md).</span></span> 
    
5. <span data-ttu-id="fab14-137">다른 설정은 **개인 정보 설정 건너뛰기** 및 **사용자가 로컬 관리자가 되는 것을 허용하지 않음** 입니다. 둘 다 기본적으로 **해제** 로 설정되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fab14-137">The other settings are **Skip privacy settings** and **Don't allow user to become the local admin**. These are both set to **Off** by default.</span></span> 
    
    <span data-ttu-id="fab14-138">**다음** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="fab14-138">Choose **Next**.</span></span>
    
6. <span data-ttu-id="fab14-139">**사용자가 만든(또는** 선택) 프로필이 장치 목록을 업로드하여 만든 디바이스 그룹에 적용될 것 같다고 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="fab14-139">**You're done** indicates that the profile you created (or chose) will be applied to the device group you created by uploading the list of devices.</span></span> <span data-ttu-id="fab14-140">설정은 장치 사용자가 다음에 로그인할 때 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="fab14-140">The settings will be in effect when the device users sign in next.</span></span> <span data-ttu-id="fab14-141">**닫기** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="fab14-141">Choose **Close**.</span></span>

## <a name="related-content"></a><span data-ttu-id="fab14-142">관련 콘텐츠</span><span class="sxs-lookup"><span data-stu-id="fab14-142">Related content</span></span>

<span data-ttu-id="fab14-143">[AutoPilot 프로필 설정](autopilot-profile-settings.md) 정보(문서)</span><span class="sxs-lookup"><span data-stu-id="fab14-143">[About AutoPilot Profile settings](autopilot-profile-settings.md) (article)</span></span>\
<span data-ttu-id="fab14-144">[장치 및 앱 데이터 보호](../admin/devices/choose-device-security.md) 옵션(문서)</span><span class="sxs-lookup"><span data-stu-id="fab14-144">[Options for protecting your devices and app data](../admin/devices/choose-device-security.md) (article)</span></span>
