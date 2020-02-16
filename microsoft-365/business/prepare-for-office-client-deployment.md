---
title: Microsoft 365 Business를 사용한 Office 클라이언트 배포 준비
f1.keywords:
- CSH
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
ms.date: 10/31/2017
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection: M365-subscription-management
ms.custom:
- Core_O365Admin_Migration
- MiniMaven
- MSB365
- OKR_SMB_M365
search.appverid:
- BCS160
- MET150
ms.assetid: ed34fff3-2881-4ed4-9906-1ba6bb8dd804
description: Windows 10 컴퓨터에 32 비트 Office 앱을 자동으로 설치 하 고 업데이트 된 상태로 유지 하는 방법에 대해 알아봅니다.
ms.openlocfilehash: 0f8cd7df49ad627b190fad6737ec95a6d64d99d0
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42065112"
---
# <a name="prepare-for-office-client-deployment-by-microsoft-365-business"></a><span data-ttu-id="7e639-103">Microsoft 365 Business를 사용한 Office 클라이언트 배포 준비</span><span class="sxs-lookup"><span data-stu-id="7e639-103">Prepare for Office client deployment by Microsoft 365 Business</span></span>

## <a name="prepare-to-automatically-install-office-apps-to-client-computers"></a><span data-ttu-id="7e639-104">클라이언트 컴퓨터에 Office 앱 자동 설치 준비</span><span class="sxs-lookup"><span data-stu-id="7e639-104">Prepare to automatically install Office apps to client computers</span></span>

<span data-ttu-id="7e639-105">Microsoft 365 Business를 사용 하 여 Windows 10 컴퓨터에 32 비트 Office 앱을 자동으로 설치 하 고 업데이트를 최신 상태로 유지할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7e639-105">You can use Microsoft 365 Business to automatically install the 32-bit Office apps on Windows 10 computers and keep them current with updates.</span></span>
  
<span data-ttu-id="7e639-106">최종 사용자의 컴퓨터가 Windows 10 Business에 있고 다음을 수행 하는 경우 자동 설치가 가장 효율적으로 작동 합니다.</span><span class="sxs-lookup"><span data-stu-id="7e639-106">Automatic installation works best if the end user's computer is on Windows 10 Business and:</span></span>
  
- <span data-ttu-id="7e639-107">기존 Office 데스크톱 앱(Word, Excel, PowerPoint, Outlook, OneNote, Publisher, Access, 및 OneDrive)이 없는 경우</span><span class="sxs-lookup"><span data-stu-id="7e639-107">Doesn't have existing Office desktop apps (Word, Excel, PowerPoint, Outlook, OneNote, Publisher, Access, and OneDrive).</span></span>
    
    <span data-ttu-id="7e639-108">또는</span><span class="sxs-lookup"><span data-stu-id="7e639-108">or</span></span>
    
- <span data-ttu-id="7e639-109">기존 간편 실행 버전의 Office가 설치된 경우</span><span class="sxs-lookup"><span data-stu-id="7e639-109">Has an existing version of Click-to-Run Office installed.</span></span>
    
<span data-ttu-id="7e639-110">간편 실행 버전의 Office가 있는지 확인하려는 경우 Office 앱에서 **파일** \> **계정**(Outlook에서는 **Office 계정**)으로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="7e639-110">To determine if you have the Click-to-Run version of Office, in any Office app go to **File** \> **Account** ( **Office Account** in Outlook).</span></span> <span data-ttu-id="7e639-111">다음 그림에 표시 된 것 처럼 **Office 업데이트가** 표시 되 면 간편 실행을 사용 하 여 설치를 완료 한 것입니다.</span><span class="sxs-lookup"><span data-stu-id="7e639-111">If you see **Office Updates** as shown in the following figure, then the installation was done by using Click-to-Run.</span></span> 
  
![Screenshot of Office updates in Office app Account](../media/e3439380-fa43-4ed6-ae5d-64851c297df5.png)
  
 <span data-ttu-id="7e639-113">**이 기능이 제공 되는 사용자의 혜택**</span><span class="sxs-lookup"><span data-stu-id="7e639-113">**Who benefits from having this feature**</span></span>
  
<span data-ttu-id="7e639-114">다음과 같은 PC 환경을 사용하는 최종 사용자에게 유용합니다.</span><span class="sxs-lookup"><span data-stu-id="7e639-114">The end user whose PC:</span></span>
  
- <span data-ttu-id="7e639-115">**Has**  a Windows 10 Business user license, an active Microsoft 365 Business license, Windows 10 Creators Update, and is joined to Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="7e639-115">**Has**  a Windows 10 Business user license, an active Microsoft 365 Business license, Windows 10 Creators Update, and is joined to Azure Active Directory.</span></span> 
    
- <span data-ttu-id="7e639-116">64 비트 Office 앱 (예: Word, Excel, PowerPoint)이 **없는** 경우</span><span class="sxs-lookup"><span data-stu-id="7e639-116">**Doesn't have** 64-bit Office apps (example: Word, Excel, PowerPoint).</span></span> <span data-ttu-id="7e639-117">64 비트 Office 앱이 필요한 경우 Microsoft 365 Business 관리 콘솔에서 64 비트 2016 간편 실행 버전의 Office를 트리거하는 것이 지원 되지 않으므로이 기능은 적합 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="7e639-117">If 64-bit Office apps are required, then this feature isn't a good fit because there's no support for triggering a 64-bit 2016 Click-to-Run version of Office from the Microsoft 365 Business admin console.</span></span> 
    
- <span data-ttu-id="7e639-118">2016 Windows Installer(MSI) 독립 실행형 앱(예: Visio 또는 Project)을 **보유하지 않은** 경우.</span><span class="sxs-lookup"><span data-stu-id="7e639-118">**Doesn't have** any 2016 Windows Installer (MSI) standalone apps (for example, Visio or Project).</span></span> <span data-ttu-id="7e639-119">Microsoft 365 Business는 office를 간편 실행 버전의 Office 2016로 업그레이드 하며 Office 2016 MSI 독립 실행형 앱에서는 작동 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="7e639-119">Microsoft 365 Business upgrades Office to the Click-to-Run version of Office 2016 and that doesn't work with Office 2016 MSI standalone apps.</span></span> 
    
<span data-ttu-id="7e639-120">다음 표에는 Microsoft 365 Business administration console에서 성공적인 32 비트 간편 실행 버전의 Office 배포를 구현 하기 위해 최종 사용자/관리자가 시작 상태에 따라 수행 해야 할 수 있는 작업이 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7e639-120">The following table shows what action the end users/admins may need to take, depending on their beginning state, to have a successful 32-bit Click-to-Run version of Office deployment from the Microsoft 365 Business admin console.</span></span>
  
|<span data-ttu-id="7e639-121">**Office 설치 시작 상태**</span><span class="sxs-lookup"><span data-stu-id="7e639-121">**Starting Office install status**</span></span>|<span data-ttu-id="7e639-122">**Microsoft 365 Business Office 설치 전 수행해야 하는 작업**</span><span class="sxs-lookup"><span data-stu-id="7e639-122">**Action to take before Microsoft 365 Business Office install**</span></span>|<span data-ttu-id="7e639-123">**종료 상태**</span><span class="sxs-lookup"><span data-stu-id="7e639-123">**End state**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="7e639-124">설치된 Office 제품군이 없는 경우</span><span class="sxs-lookup"><span data-stu-id="7e639-124">No Office suite installed</span></span>  <br/> |<span data-ttu-id="7e639-125">없음</span><span class="sxs-lookup"><span data-stu-id="7e639-125">None</span></span>  <br/> |<span data-ttu-id="7e639-126">간편 실행을 사용 하 여 Office 2016 32-비트를 설치 합니다.</span><span class="sxs-lookup"><span data-stu-id="7e639-126">Office 2016 32-bit is installed by using Click-to-Run</span></span>  <br/> |
|<span data-ttu-id="7e639-127">간편 실행 32비트 버전의 Office(2016 이하)가 있고 독립 실행형 앱이 없는 경우</span><span class="sxs-lookup"><span data-stu-id="7e639-127">Existing Click-to-Run 32-bit version of Office (2016 or earlier) and no standalone apps</span></span>  <br/> |<span data-ttu-id="7e639-128">없음</span><span class="sxs-lookup"><span data-stu-id="7e639-128">None</span></span>  <br/> |<span data-ttu-id="7e639-129">Upgraded to the latest 32-bit Click-to-Run version of Office 2016, as needed **\***</span><span class="sxs-lookup"><span data-stu-id="7e639-129">Upgraded to the latest 32-bit Click-to-Run version of Office 2016, as needed **\***</span></span> <br/> |
|<span data-ttu-id="7e639-130">기존 간편 실행 32 비트 버전의 Office 및 간편 실행 32 비트 또는 64 비트 독립 실행형 Office 앱 (예: Visio, Project)</span><span class="sxs-lookup"><span data-stu-id="7e639-130">Existing Click-to-Run 32-bit version of Office and Click-to-Run 32-bit or 64-bit standalone Office apps (for example, Visio, Project)</span></span>  <br/> |<span data-ttu-id="7e639-131">없음</span><span class="sxs-lookup"><span data-stu-id="7e639-131">None</span></span>  <br/> |<span data-ttu-id="7e639-132">독립 실행형 앱은 영향을 받지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="7e639-132">Standalone apps aren't affected.</span></span> <span data-ttu-id="7e639-133">제품군이 간편 실행 32비트 버전의 Office 2016으로 업그레이드됩니다.</span><span class="sxs-lookup"><span data-stu-id="7e639-133">Suite is upgraded to Click-to-Run 32-bit version of Office 2016</span></span>  <br/> |
|<span data-ttu-id="7e639-134">간편 실행 32비트 버전의 Office 및 32비트 또는 64비트(2016 제외) MSI 독립 실행형 Office 앱이 있는 경우</span><span class="sxs-lookup"><span data-stu-id="7e639-134">Existing Click-to-Run 32-bit version of Office and any 32-bit or 64-bit (except 2016) MSI standalone Office apps</span></span>  <br/> |<span data-ttu-id="7e639-135">없음</span><span class="sxs-lookup"><span data-stu-id="7e639-135">None</span></span>  <br/> |<span data-ttu-id="7e639-136">독립 실행형 앱은 영향을 받지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="7e639-136">Standalone apps aren't affected.</span></span> <span data-ttu-id="7e639-137">제품군이 간편 실행 32비트 버전의 Office 2016으로 업그레이드됩니다.</span><span class="sxs-lookup"><span data-stu-id="7e639-137">Suite is upgraded to Click-to-Run 32-bit version of Office 2016</span></span>  <br/> ||||
|<span data-ttu-id="7e639-138">간편 실행 64비트 버전의 Office가 있는 경우</span><span class="sxs-lookup"><span data-stu-id="7e639-138">Any existing Click-to-Run 64-bit version of Office</span></span>  <br/> |<span data-ttu-id="7e639-139">32 비트 Office 앱으로 교체 하는 것이 확인 된 경우 64 비트 Office 앱을 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="7e639-139">Uninstall the 64-bit Office apps, if it's OK to replace them with 32-bit Office apps</span></span>  <br/> |<span data-ttu-id="7e639-140">Office 64비트 앱이 제거된 경우 간편 실행 32비트 버전의 Office 2016이 설치됩니다.</span><span class="sxs-lookup"><span data-stu-id="7e639-140">If Office 64-bit apps are removed, the Click-to-Run 32-bit version of Office 2016 is installed</span></span>  <br/> |
|<span data-ttu-id="7e639-141">독립 실행형 앱 유무와 상관없이 Office 2016의 MSI 설치가 있는 경우</span><span class="sxs-lookup"><span data-stu-id="7e639-141">An existing MSI install of Office 2016 with or without standalone apps</span></span>  <br/> |<span data-ttu-id="7e639-142">MSI Office 2016을 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="7e639-142">Uninstall MSI Office 2016.</span></span>  <br/> |<span data-ttu-id="7e639-p106">간편 실행 32비트 버전의 Office 2016이 설치됩니다. 독립 실행형 앱은 변경되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="7e639-p106">Click-to-Run 32-bit version of Office 2016 is installed. No change to standalone apps</span></span>  <br/> |
|<span data-ttu-id="7e639-145">Office 2013(또는 이전 버전)의 MSI 설치 및/또는 독립 실행형 Office 앱이 있는 경우</span><span class="sxs-lookup"><span data-stu-id="7e639-145">Existing MSI install of Office 2013 (or earlier) and/or standalone Office apps</span></span>  <br/> |<span data-ttu-id="7e639-146">없음</span><span class="sxs-lookup"><span data-stu-id="7e639-146">None</span></span>  <br/> |<span data-ttu-id="7e639-147">기존 MSI Office 설치가 포함된 간편 실행 32비트 버전의 Office 2016과 독립 실행형 앱이 함께 존재합니다.</span><span class="sxs-lookup"><span data-stu-id="7e639-147">Click-to-Run 32-bit version of Office 2016 with the pre-existing MSI Office install (and standalone apps) exist side-by-side</span></span>  <br/> |
||||
   
 <span data-ttu-id="7e639-148">**(\*) 참고:** 알려진 버그로 인해 간편 실행 32비트 버전의 Office 2016으로 업그레이드되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="7e639-148">**(\*) Note:** Does not upgrade to Click-to-Run 32-bit version of Office 2016 due to a known bug.</span></span> <span data-ttu-id="7e639-149">수정이 진행 중입니다.</span><span class="sxs-lookup"><span data-stu-id="7e639-149">A fix is in progress.</span></span> 
  
