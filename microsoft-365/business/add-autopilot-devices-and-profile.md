---
title: 단계별 가이드를 사용하여 AutoPilot 장치 및 프로필 추가
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.custom:
- Core_O365Admin_Migration
- MiniMaven
- MSB365
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: be5b6d90-3344-4c5e-bf40-5733eb845beb
description: 비즈니스에 대 한 새 Windows 10 장치를 설정 하려면 Windows 작업을 자동화할을 사용 하는 방법에 알아봅니다.
ms.openlocfilehash: 56225424125e9eed9f46867837c564aa5d1c4adc
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/28/2018
ms.locfileid: "26869717"
---
# <a name="use-the-step-by-step-guide-to-add-autopilot-devices-and-profile"></a><span data-ttu-id="f1417-103">단계별 가이드를 사용하여 AutoPilot 장치 및 프로필 추가</span><span class="sxs-lookup"><span data-stu-id="f1417-103">Use the step-by-step guide to add Autopilot devices and profile</span></span>

<span data-ttu-id="f1417-104">Windows AutoPilot을 사용하여 비즈니스용 새 Windows 10 장치를 설정할 수 있으며 직원에게 제공하는 즉시 생산성 있게 사용할 준비가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f1417-104">You can use Windows AutoPilot to set up new Windows 10 devices for your business so they are ready for productive use as soon as you give them to your employees.</span></span>
  
## <a name="device-requirements"></a><span data-ttu-id="f1417-105">장치 요구 사항</span><span class="sxs-lookup"><span data-stu-id="f1417-105">Device requirements</span></span>

<span data-ttu-id="f1417-106">장치가 다음 요구 사항을 충족해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f1417-106">Devices need to meet these requirements:</span></span>
  
- <span data-ttu-id="f1417-107">Windows 10 버전 1703 이상</span><span class="sxs-lookup"><span data-stu-id="f1417-107">Windows 10, version 1703 or later.</span></span>
    
- <span data-ttu-id="f1417-108">Windows 첫 실행 경험을 완료하지 않은 새 장치</span><span class="sxs-lookup"><span data-stu-id="f1417-108">New devices that have not been through Windows out-of-box experience.</span></span>
    
## <a name="use-the-setup-guide-to-create-devices-and-profiles"></a><span data-ttu-id="f1417-109">설정 가이드를 사용하여 장치와 프로필 만들기</span><span class="sxs-lookup"><span data-stu-id="f1417-109">Use the setup guide to create devices and profiles</span></span>

<span data-ttu-id="f1417-110">장치 그룹 또는 프로필을 아직 만들지 않은 경우 시작하는 가장 좋은 방법은 단계별 가이드를 사용하는 것이지만, 가이드를 사용하지 않고 [장치를 추가](create-and-edit-autopilot-devices.md)하고 [프로필을 할당](create-and-edit-autopilot-profiles.md)할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f1417-110">If you have no device groups or profiles created yet, the best way to get started is by using the step-by-step guide, but you can also [add devices](create-and-edit-autopilot-devices.md) and [assign profiles](create-and-edit-autopilot-profiles.md) to them without using the guide.</span></span> 
  
1. <span data-ttu-id="f1417-111">Microsoft 365 Business 관리 센터에서 **장치 작업** 카드를 찾은 다음 **Autopilot으로 Windows 배포**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="f1417-111">In the Microsoft 365 Business admin center, locate the **Device actions** card, and choose **Deploy Windows with Autopilot**.</span></span>
    
    ![On the Device actions card, choose Deploy Windows with Autopilot.](media/160d5c2a-11a8-48f9-a8aa-70f084b85448.png)
  
2. <span data-ttu-id="f1417-113">**Windows 준비** 페이지에서 **시작 가이드**를 클릭하거나 탭합니다.</span><span class="sxs-lookup"><span data-stu-id="f1417-113">On the **Prepare Windows** page, click or tap **Start guide**.</span></span>
    
    ![Click Start guide for step-by-step instructions for Autopilot.](media/31662655-d1e6-437d-87ea-c0dec5da56f7.png)
  
3. <span data-ttu-id="f1417-p101">**장치 목록이 포함된 .csv 파일 업로드** 페이지에서 준비된 .CSV 파일이 있는 위치로 이동한 후 **열기** \> **다음**을 클릭합니다. 파일에 다음 3개의 머리글이 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f1417-p101">On the **Upload .csv file with list of devices** page, browse to a locations where you have the prepared .CSV file, then **Open** \> **Next**. The file should have three headers:</span></span>
    
  - <span data-ttu-id="f1417-117">A 열: 장치 일련 번호</span><span class="sxs-lookup"><span data-stu-id="f1417-117">Column A: Device Serial Number</span></span>
    
  - <span data-ttu-id="f1417-118">B 열: Windows 제품 ID</span><span class="sxs-lookup"><span data-stu-id="f1417-118">Column B: Windows Product ID</span></span>
    
  - <span data-ttu-id="f1417-119">C 열: 하드웨어 해시</span><span class="sxs-lookup"><span data-stu-id="f1417-119">Column C: Hardware Hash</span></span>
    
    <span data-ttu-id="f1417-120">하드웨어 공급업체로부터 이 정보를 얻거나 CSV 파일을 생성하는 [Get-WindowsAutoPilotInfo PowerShell 스크립트](https://www.powershellgallery.com/packages/Get-WindowsAutoPilotInfo)를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f1417-120">You can get this information from your hardware vendor, or you can use the [Get-WindowsAutoPilotInfo PowerShell script](https://www.powershellgallery.com/packages/Get-WindowsAutoPilotInfo) that will generate a CSV file.</span></span> 
    
    <span data-ttu-id="f1417-p102">자세한 내용은 [장치 목록 CSV 파일](https://support.office.com/article/932e3676-2491-49f0-9177-d893d2f5276e)을 참조하세요. **장치 목록이 포함된 .csv 파일 업로드** 페이지에서 샘플 파일을 다운로드할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f1417-p102">For more information, see [Device list CSV-file](https://support.office.com/article/932e3676-2491-49f0-9177-d893d2f5276e). You can also download a sample file on the **Upload .csv file with list of devices** page.</span></span> 
    
4. <span data-ttu-id="f1417-p103">**프로필 할당** 페이지에서 기존 프로필을 선택하거나 새 프로필을 만들 수 있습니다. 아직 프로필이 없는 경우 새 프로필을 만들라는 메시지가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="f1417-p103">On the **Assign a profile** page, you can either pick an existing profile, or create a new one. If you don't have one yet, you will be prompted to create a new one.</span></span> 
    
    <span data-ttu-id="f1417-125">프로필은 단일 장치 또는 장치 그룹에 적용할 수 있는 설정 모음입니다.</span><span class="sxs-lookup"><span data-stu-id="f1417-125">A profile is a collection of settings that can be applied to a single device or to a group of devices.</span></span>
    
    <span data-ttu-id="f1417-p104">기본 기능은 필수이며 자동으로 설정됩니다. 기본 기능은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="f1417-p104">The default features are required and will be set automatically. The default features are:</span></span>
    
  - <span data-ttu-id="f1417-128">Cortana, OneDrive 및 OEM 등록은 건너뜁니다.</span><span class="sxs-lookup"><span data-stu-id="f1417-128">Cortana, OneDrive and OEM registration is skipped.</span></span>
    
  - <span data-ttu-id="f1417-129">회사 브랜드의 로그인 환경을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="f1417-129">Create sign-in experience with your company brand.</span></span>
    
  - <span data-ttu-id="f1417-130">장치가 Azure Active Directory 계정에 연결되고 Microsoft 365 Business에서 관리하도록 자동으로 등록됩니다.</span><span class="sxs-lookup"><span data-stu-id="f1417-130">Your devices are going to be connected to Azure Active Directory accounts and automatically enrolled to be managed by Microsoft 365 Business.</span></span>
    
    <span data-ttu-id="f1417-131">자세한 내용은</span><span class="sxs-lookup"><span data-stu-id="f1417-131">For more information, see</span></span>
    
    <span data-ttu-id="f1417-132">[AutoPilot 프로필 설정 정보](autopilot-profile-settings.md) 를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="f1417-132">[About AutoPilot Profile settings](autopilot-profile-settings.md) .</span></span> 
    
5. <span data-ttu-id="f1417-133">다른 설정은 **개인 정보 설정 건너뛰기** 및 **사용자가 로컬 관리자가 되는 것을 허용하지 않음**입니다. 둘 다 기본적으로 **해제**로 설정되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f1417-133">The other settings are **Skip privacy settings** and **Don't allow user to become the local admin**. These are both set to **Off** by default.</span></span> 
    
    <span data-ttu-id="f1417-134">**다음**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="f1417-134">Choose **Next**.</span></span>
    
6. <span data-ttu-id="f1417-p105">**모두 마쳤습니다** 페이지는 만들었거나 선택한 프로필이 장치 목록을 업로드하여 만든 장치 그룹에 적용됨을 나타냅니다. 이러한 설정은 장치 사용자가 다음에 로그인할 때 적용됩니다. **닫기**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="f1417-p105">**You're done** page indicates that the profile you created (or chose) will be applied to the device group you created by uploading the list of devices. These settings will be in effect when the device users sign in next. Choose **Close**.</span></span>
    