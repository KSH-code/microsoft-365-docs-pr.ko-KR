---
title: AutoPilot 장치 만들기 및 편집
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: Sirkkuw
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
ms.openlocfilehash: 8c3d029d682ae30444bdc7d30a4790a8f982e0e0
ms.sourcegitcommit: 2d59b24b877487f3b84aefdc7b1e200a21009999
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/27/2020
ms.locfileid: "44400997"
---
# <a name="create-and-edit-autopilot-devices"></a><span data-ttu-id="1afd4-104">AutoPilot 장치 만들기 및 편집</span><span class="sxs-lookup"><span data-stu-id="1afd4-104">Create and edit AutoPilot devices</span></span>

## <a name="upload-a-list-of-devices"></a><span data-ttu-id="1afd4-105">장치 목록 업로드</span><span class="sxs-lookup"><span data-stu-id="1afd4-105">Upload a list of devices</span></span>

<span data-ttu-id="1afd4-106">단계별 가이드를 사용하여 디바이스를 업로드할 수 있지만 장치 탭에서 디바이스를 업로드할 **수도** 있습니다. [](add-autopilot-devices-and-profile.md)</span><span class="sxs-lookup"><span data-stu-id="1afd4-106">You can use the [Step-by-step guide](add-autopilot-devices-and-profile.md) to upload devices, but you can also upload devices in the **Devices** tab.</span></span> 
  
<span data-ttu-id="1afd4-107">장치는 다음 요구 사항을 충족해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1afd4-107">Devices must meet these requirements:</span></span>
  
- <span data-ttu-id="1afd4-108">Windows 10 버전 1703 이상</span><span class="sxs-lookup"><span data-stu-id="1afd4-108">Windows 10, version 1703 or later</span></span>
    
- <span data-ttu-id="1afd4-109">Windows Out-of-box 환경을 통과하지 않은 새 장치</span><span class="sxs-lookup"><span data-stu-id="1afd4-109">New devices that haven't been through Windows out-of-box experience</span></span>

1. <span data-ttu-id="1afd4-110">Microsoft 365 관리 센터에서  \> **장치 AutoPilot을 선택하세요.**</span><span class="sxs-lookup"><span data-stu-id="1afd4-110">In the Microsoft 365 admin center, choose **Devices** \> **AutoPilot**.</span></span>
  
2. <span data-ttu-id="1afd4-111">**AutoPilot 페이지에서** 장치 탭 **장치** \> **추가를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="1afd4-111">On the **AutoPilot** page, choose the **Devices** tab \> **Add devices**.</span></span>
    
    ![In the Devices tab, choose Add devices.](../media/6ba81e22-c873-40ad-8a72-ce64d15ea6ba.png)
  
3. <span data-ttu-id="1afd4-113">장치 추가 **패널에서** 저장 닫기 준비를 한 장치 목록 [CSV](https://docs.microsoft.com/microsoft-365/admin/misc/device-list) \> **파일을** \> **검색합니다.**</span><span class="sxs-lookup"><span data-stu-id="1afd4-113">On the **Add devices** panel, browse to a [Device list CSV file](https://docs.microsoft.com/microsoft-365/admin/misc/device-list) that you prepared \> **Save** \> **Close**.</span></span>
    
    <span data-ttu-id="1afd4-114">하드웨어 공급업체에서 이 정보를 얻거나 [Get-WindowsAutoPilotInfo PowerShell](https://www.powershellgallery.com/packages/Get-WindowsAutoPilotInfo) 스크립트를 사용하여 CSV 파일을 생성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1afd4-114">You can get this information from your hardware vendor, or you can use the [Get-WindowsAutoPilotInfo PowerShell script](https://www.powershellgallery.com/packages/Get-WindowsAutoPilotInfo) to generate a CSV file.</span></span> 
    
## <a name="assign-a-profile-to-a-device-or-a-group-of-devices"></a><span data-ttu-id="1afd4-115">장치 또는 장치 그룹에 프로필 할당</span><span class="sxs-lookup"><span data-stu-id="1afd4-115">Assign a profile to a device or a group of devices</span></span>

1. <span data-ttu-id="1afd4-116">Windows **준비 페이지에서** 장치  탭을 선택하고 하나 이상의 장치 옆에 있는 확인란을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="1afd4-116">On the **Prepare Windows** page, choose the **Devices** tab, and select the check box next to one or more devices.</span></span> 
    
2. <span data-ttu-id="1afd4-117">**장치** 패널의 **할당된 프로필** 드롭다운에서 프로필을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="1afd4-117">On the **Device** panel, select a profile from the **Assigned profile** drop-down.</span></span> 
    
    <span data-ttu-id="1afd4-118">아직 프로필이 없는 경우 지침은 [AutoPilot 프로필 만들기 및 편집](create-and-edit-autopilot-profiles.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="1afd4-118">If you don't have any profiles yet, see [Create and edit AutoPilot profiles](create-and-edit-autopilot-profiles.md) for instructions.</span></span> 
    
