---
title: AutoPilot 장치 만들기 및 편집
f1.keywords:
- NOCSH
ms.author: efrene
author: efrene
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Adm_O365
- M365-subscription-management
- M365-identity-device-management
ms.custom:
- Adm_O365
- Core_O365Admin_Migration
- MiniMaven
- MSB365
- OKR_SMB_M365
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 0f7b1d7c-4086-4331-8534-45d7886f9f34
description: Microsoft 365 Business Premium에서 AutoPilot을 사용하여 디바이스를 업로드하는 방법을 학습합니다. 장치 또는 장치 그룹에 프로필을 할당할 수 있습니다.
ms.openlocfilehash: 506ff44e3cb6656b19174e82688b5af141ea2b79
ms.sourcegitcommit: 53acc851abf68e2272e75df0856c0e16b0c7e48d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/02/2021
ms.locfileid: "51578490"
---
# <a name="create-and-edit-autopilot-devices"></a><span data-ttu-id="a1b02-104">AutoPilot 장치 만들기 및 편집</span><span class="sxs-lookup"><span data-stu-id="a1b02-104">Create and edit AutoPilot devices</span></span>

## <a name="upload-a-list-of-devices"></a><span data-ttu-id="a1b02-105">장치 목록 업로드</span><span class="sxs-lookup"><span data-stu-id="a1b02-105">Upload a list of devices</span></span>

<span data-ttu-id="a1b02-106">단계별 가이드를 사용하여 디바이스를 업로드할 수 있지만 장치 탭에서 디바이스를 업로드할 **수도** 있습니다. [](add-autopilot-devices-and-profile.md)</span><span class="sxs-lookup"><span data-stu-id="a1b02-106">You can use the [Step-by-step guide](add-autopilot-devices-and-profile.md) to upload devices, but you can also upload devices in the **Devices** tab.</span></span> 
  
<span data-ttu-id="a1b02-107">장치는 다음 요구 사항을 충족해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a1b02-107">Devices must meet these requirements:</span></span>
  
- <span data-ttu-id="a1b02-108">Windows 10 버전 1703 이상</span><span class="sxs-lookup"><span data-stu-id="a1b02-108">Windows 10, version 1703 or later</span></span>
    
- <span data-ttu-id="a1b02-109">Windows에서 바로 사용할 수 있는 환경을 통해 제공되지 않은 새 장치</span><span class="sxs-lookup"><span data-stu-id="a1b02-109">New devices that haven't been through Windows out-of-box experience</span></span>

1. <span data-ttu-id="a1b02-110">Microsoft 365 관리 센터에서 **장치** \> **AutoPilot 을 선택하세요.**</span><span class="sxs-lookup"><span data-stu-id="a1b02-110">In the Microsoft 365 admin center, choose **Devices** \> **AutoPilot**.</span></span>
  
2. <span data-ttu-id="a1b02-111">**AutoPilot 페이지에서** 장치 탭 **장치** \> **추가 를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="a1b02-111">On the **AutoPilot** page, choose the **Devices** tab \> **Add devices**.</span></span>
    
    ![In the Devices tab, choose Add devices.](../media/6ba81e22-c873-40ad-8a72-ce64d15ea6ba.png)
  
3. <span data-ttu-id="a1b02-113">장치 **추가 패널에서** 저장 닫기 를 준비한 장치 목록 [CSV](../admin/misc/device-list.md) \> **파일을** \> **검색합니다.**</span><span class="sxs-lookup"><span data-stu-id="a1b02-113">On the **Add devices** panel, browse to a [Device list CSV file](../admin/misc/device-list.md) that you prepared \> **Save** \> **Close**.</span></span>
    
    <span data-ttu-id="a1b02-114">하드웨어 공급업체에서 이 정보를 얻거나 [Get-WindowsAutoPilotInfo PowerShell](https://www.powershellgallery.com/packages/Get-WindowsAutoPilotInfo) 스크립트를 사용하여 CSV 파일을 생성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a1b02-114">You can get this information from your hardware vendor, or you can use the [Get-WindowsAutoPilotInfo PowerShell script](https://www.powershellgallery.com/packages/Get-WindowsAutoPilotInfo) to generate a CSV file.</span></span> 
    
## <a name="assign-a-profile-to-a-device-or-a-group-of-devices"></a><span data-ttu-id="a1b02-115">장치 또는 장치 그룹에 프로필 할당</span><span class="sxs-lookup"><span data-stu-id="a1b02-115">Assign a profile to a device or a group of devices</span></span>

1. <span data-ttu-id="a1b02-116">Windows **준비 페이지에서** 장치  탭을 선택하고 하나 이상의 장치 옆에 있는 확인란을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="a1b02-116">On the **Prepare Windows** page, choose the **Devices** tab, and select the check box next to one or more devices.</span></span> 
    
2. <span data-ttu-id="a1b02-117">**장치** 패널의 **할당된 프로필** 드롭다운에서 프로필을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="a1b02-117">On the **Device** panel, select a profile from the **Assigned profile** drop-down.</span></span> 
    
    <span data-ttu-id="a1b02-118">아직 프로필이 없는 경우 지침은 [AutoPilot 프로필 만들기 및 편집](create-and-edit-autopilot-profiles.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="a1b02-118">If you don't have any profiles yet, see [Create and edit AutoPilot profiles](create-and-edit-autopilot-profiles.md) for instructions.</span></span> 
