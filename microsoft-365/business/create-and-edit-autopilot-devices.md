---
title: AutoPilot 장치 만들기 및 편집
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
ms.custom: OKR_SMB_M365
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 0f7b1d7c-4086-4331-8534-45d7886f9f34
description: Microsoft 365 Business에서 AutoPilot을 사용 하 여 장치를 업로드 하는 방법을 알아봅니다. 장치 또는 장치 그룹에 프로필을 할당할 수 있습니다.
ms.openlocfilehash: 9ae94266f5a41d8d115fc92f0f080a6fdbdc9f15
ms.sourcegitcommit: 6003d6da0a85c97357eb3dba3918eb145f381fe1
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/27/2019
ms.locfileid: "37288018"
---
# <a name="create-and-edit-autopilot-devices"></a><span data-ttu-id="9dc70-104">AutoPilot 장치 만들기 및 편집</span><span class="sxs-lookup"><span data-stu-id="9dc70-104">Create and edit AutoPilot devices</span></span>

## <a name="upload-a-list-of-devices"></a><span data-ttu-id="9dc70-105">장치 목록 업로드</span><span class="sxs-lookup"><span data-stu-id="9dc70-105">Upload a list of devices</span></span>

<span data-ttu-id="9dc70-106">[단계별 가이드](add-autopilot-devices-and-profile.md) 를 사용하여 장치를 업로드할 수 있지만 **장치** 탭에서 업로드할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9dc70-106">You can use the [Step-by-step guide](add-autopilot-devices-and-profile.md) to upload devices, but you can also upload the in the **Devices** tab.</span></span> 
  
<span data-ttu-id="9dc70-107">장치가 다음 요구 사항을 충족해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9dc70-107">Devices need to meet these requirements:</span></span>
  
- <span data-ttu-id="9dc70-108">Windows 10 버전 1703 이상</span><span class="sxs-lookup"><span data-stu-id="9dc70-108">Windows 10, version 1703 or later.</span></span>
    
- <span data-ttu-id="9dc70-109">Windows 첫 실행 경험을 완료하지 않은 새 장치</span><span class="sxs-lookup"><span data-stu-id="9dc70-109">New devices that have not been through Windows out-of-box experience.</span></span>

1. <span data-ttu-id="9dc70-110">Microsoft 365 Business 관리 센터에서 **장치** \> **AutoPilot**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="9dc70-110">In the Microsoft 365 Business Admin center, choose **Devices** \> **AutoPilot**.</span></span>
  
2. <span data-ttu-id="9dc70-111">**AutoPilot** 페이지에서 **장치** 탭 \> **장치 추가**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="9dc70-111">On the **AutoPilot** page, choose the **Devices** tab \> **Add devices**.</span></span>
    
    ![In the Devices tab, choose Add devices.](media/6ba81e22-c873-40ad-8a72-ce64d15ea6ba.png)
  
3. <span data-ttu-id="9dc70-113">**장치 추가** 패널에서 \> **저장** \> **닫기**가 준비 된 [장치 목록 CSV 파일](https://support.office.com/article/932e3676-2491-49f0-9177-d893d2f5276e) 을 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="9dc70-113">On the **Add devices** panel, browse to a [Device list CSV-file](https://support.office.com/article/932e3676-2491-49f0-9177-d893d2f5276e) that you have prepared \> **Save** \> **Close**.</span></span>
    
    <span data-ttu-id="9dc70-114">하드웨어 공급업체로부터 이 정보를 얻거나 csv 파일을 생성하는 [Get-WindowsAutoPilotInfo PowerShell 스크립트](https://www.powershellgallery.com/packages/Get-WindowsAutoPilotInfo)를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9dc70-114">You can get this information from your hardware vendor, or you can use the [Get-WindowsAutoPilotInfo PowerShell script](https://www.powershellgallery.com/packages/Get-WindowsAutoPilotInfo) that will generate a csv file.</span></span> 
    
## <a name="assign-a-profile-to-a-device-or-a-group-of-devices"></a><span data-ttu-id="9dc70-115">장치 또는 장치 그룹에 프로필 할당</span><span class="sxs-lookup"><span data-stu-id="9dc70-115">Assign a profile to a device or a group of devices</span></span>

1. <span data-ttu-id="9dc70-116">**Windows 준비** 페이지에서 **장치** 탭을 선택하고 하나 이상의 장치 옆에 있는 확인란을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="9dc70-116">On the **Prepare Windows** page, choose the **Devices** tab and check the check box next to one or more devices.</span></span> 
    
2. <span data-ttu-id="9dc70-117">**장치** 패널의 **할당된 프로필** 드롭다운에서 프로필을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="9dc70-117">On the **Device** panel, select a profile from the **Assigned profile** drop-down.</span></span> 
    
    <span data-ttu-id="9dc70-118">아직 프로필이 없는 경우 지침은 [AutoPilot 프로필 만들기 및 편집](create-and-edit-autopilot-profiles.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="9dc70-118">If you don't have any profiles yet, see [Create and edit AutoPilot profiles](create-and-edit-autopilot-profiles.md) for instructions.</span></span> 
    
