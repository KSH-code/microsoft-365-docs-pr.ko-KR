---
title: AutoPilot 장치 만들기 및 편집
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection: Adm_O365
ms.custom:
- Adm_O365
- Core_O365Admin_Migration
- MiniMaven
- MSB365
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 0f7b1d7c-4086-4331-8534-45d7886f9f34
description: Microsoft 365 비즈니스에서 작업을 자동화할을 사용 하 여 장치를 업로드 하는 방법에 알아봅니다. 장치 또는 장치 그룹에는 프로필을 할당할 수 있습니다.
ms.openlocfilehash: cc1f81e9efd9b16e27b8abfbb0927d241535077e
ms.sourcegitcommit: e491c4713115610cbe13d2fbd0d65e1a41c34d62
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/16/2019
ms.locfileid: "26869968"
---
# <a name="create-and-edit-autopilot-devices"></a><span data-ttu-id="75a26-104">AutoPilot 장치 만들기 및 편집</span><span class="sxs-lookup"><span data-stu-id="75a26-104">Create and edit AutoPilot devices</span></span>

## <a name="upload-a-list-of-devices"></a><span data-ttu-id="75a26-105">장치 목록 업로드</span><span class="sxs-lookup"><span data-stu-id="75a26-105">Upload a list of devices</span></span>

<span data-ttu-id="75a26-106">[단계별 가이드](add-autopilot-devices-and-profile.md) 를 사용하여 장치를 업로드할 수 있지만 **장치** 탭에서 업로드할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="75a26-106">You can use the [Step-by-step guide](add-autopilot-devices-and-profile.md) to upload devices, but you can also upload the in the **Devices** tab.</span></span> 
  
<span data-ttu-id="75a26-107">장치가 다음 요구 사항을 충족해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="75a26-107">Devices need to meet these requirements:</span></span>
  
- <span data-ttu-id="75a26-108">Windows 10 버전 1703 이상</span><span class="sxs-lookup"><span data-stu-id="75a26-108">Windows 10, version 1703 or later.</span></span>
    
- <span data-ttu-id="75a26-109">Windows 첫 실행 경험을 완료하지 않은 새 장치</span><span class="sxs-lookup"><span data-stu-id="75a26-109">New devices that have not been through Windows out-of-box experience.</span></span>
    
1. <span data-ttu-id="75a26-110">Microsoft 365 Business 관리 센터의 **장치 작업** 카드에서 **Autopilot으로 Windows 배포**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="75a26-110">In the Microsoft 365 Business Admin center, choose **Deploy Windows with AutoPilot** on the **Device actions** card.</span></span> 
    
    ![On the Device actions card, choose Deploy Windows with Autopilot.](media/160d5c2a-11a8-48f9-a8aa-70f084b85448.png)
  
2. <span data-ttu-id="75a26-112">**Windows 준비** 페이지에서 **장치** 탭 \> **장치 추가**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="75a26-112">On the **Prepare Windows** page, choose the **Devices** tab \> **Add devices**.</span></span>
    
    ![In the Devices tab, choose Add devices.](media/6ba81e22-c873-40ad-8a72-ce64d15ea6ba.png)
  
3. <span data-ttu-id="75a26-114">**추가 장치** 패널에서 준비한 [장치 목록 CSV 파일을](https://support.office.com/article/932e3676-2491-49f0-9177-d893d2f5276e) 이동 \> **저장** \> **닫기**합니다.</span><span class="sxs-lookup"><span data-stu-id="75a26-114">On the **Add devices** panel, browse to a [Device list CSV-file](https://support.office.com/article/932e3676-2491-49f0-9177-d893d2f5276e) that you have prepared \> **Save** \> **Close**.</span></span>
    
    <span data-ttu-id="75a26-115">하드웨어 공급업체로부터 이 정보를 얻거나 csv 파일을 생성하는 [Get-WindowsAutoPilotInfo PowerShell 스크립트](https://www.powershellgallery.com/packages/Get-WindowsAutoPilotInfo)를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="75a26-115">You can get this information from your hardware vendor, or you can use the [Get-WindowsAutoPilotInfo PowerShell script](https://www.powershellgallery.com/packages/Get-WindowsAutoPilotInfo) that will generate a csv file.</span></span> 
    
## <a name="assign-a-profile-to-a-device-or-a-group-of-devices"></a><span data-ttu-id="75a26-116">장치 또는 장치 그룹에 프로필 할당</span><span class="sxs-lookup"><span data-stu-id="75a26-116">Assign a profile to a device or a group of devices</span></span>

1. <span data-ttu-id="75a26-117">**Windows 준비** 페이지에서 **장치** 탭을 선택하고 하나 이상의 장치 옆에 있는 확인란을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="75a26-117">On the **Prepare Windows** page, choose the **Devices** tab and check the check box next to one or more devices.</span></span> 
    
2. <span data-ttu-id="75a26-118">**장치** 패널의 **할당된 프로필** 드롭다운에서 프로필을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="75a26-118">On the **Device** panel, select a profile from the **Assigned profile** drop-down.</span></span> 
    
    <span data-ttu-id="75a26-119">아직 프로필이 없는 경우 지침은 [AutoPilot 프로필 만들기 및 편집](create-and-edit-autopilot-profiles.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="75a26-119">If you don't have any profiles yet, see [Create and edit AutoPilot profiles](create-and-edit-autopilot-profiles.md) for instructions.</span></span> 
    
