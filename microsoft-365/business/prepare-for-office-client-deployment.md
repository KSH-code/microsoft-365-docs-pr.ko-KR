---
title: 비즈니스용 Microsoft 365의 Office 클라이언트 배포 준비
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
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
ms.assetid: ed34fff3-2881-4ed4-9906-1ba6bb8dd804
description: Windows 10 컴퓨터에 32비트 Office 앱을 자동으로 설치하고 업데이트된 것으로 유지하는 방법을 알아보고 있습니다.
ms.openlocfilehash: 2de492914edbde2afe593aac290c4a634b801443
ms.sourcegitcommit: 2d664a95b9875f0775f0da44aca73b16a816e1c3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/01/2020
ms.locfileid: "44470950"
---
# <a name="prepare-for-office-client-deployment-by-microsoft-365-for-business"></a><span data-ttu-id="580dc-103">비즈니스용 Microsoft 365의 Office 클라이언트 배포 준비</span><span class="sxs-lookup"><span data-stu-id="580dc-103">Prepare for Office client deployment by Microsoft 365 for business</span></span>

<span data-ttu-id="580dc-104">이 문서는 Microsoft 365 Business Premium에 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="580dc-104">This article applies to Microsoft 365 Business Premium.</span></span>

## <a name="prepare-to-automatically-install-office-apps-to-client-computers"></a><span data-ttu-id="580dc-105">클라이언트 컴퓨터에 Office 앱 자동 설치 준비</span><span class="sxs-lookup"><span data-stu-id="580dc-105">Prepare to automatically install Office apps to client computers</span></span>

<span data-ttu-id="580dc-106">Microsoft 365 Business Premium을 사용하여 Windows 10 컴퓨터에 32비트 Office 앱을 자동으로 설치하고 최신 업데이트로 유지할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="580dc-106">You can use Microsoft 365 Business Premium to automatically install the 32-bit Office apps on Windows 10 computers and keep them current with updates.</span></span>
  
<span data-ttu-id="580dc-107">자동 설치는 최종 사용자의 컴퓨터가 Windows 10 Business에 있는 경우 가장 잘 작동합니다.</span><span class="sxs-lookup"><span data-stu-id="580dc-107">Automatic installation works best if the end user's computer is on Windows 10 Business and:</span></span>
  
- <span data-ttu-id="580dc-108">기존 Office 데스크톱 앱(Word, Excel, PowerPoint, Outlook, OneNote, Publisher, Access, 및 OneDrive)이 없는 경우</span><span class="sxs-lookup"><span data-stu-id="580dc-108">Doesn't have existing Office desktop apps (Word, Excel, PowerPoint, Outlook, OneNote, Publisher, Access, and OneDrive).</span></span>
    
    <span data-ttu-id="580dc-109">또는</span><span class="sxs-lookup"><span data-stu-id="580dc-109">or</span></span>
    
- <span data-ttu-id="580dc-110">기존 간편 실행 버전의 Office가 설치된 경우</span><span class="sxs-lookup"><span data-stu-id="580dc-110">Has an existing version of Click-to-Run Office installed.</span></span>
    
<span data-ttu-id="580dc-111">간편 실행 버전의 Office가 있는지 확인하려는 경우 Office 앱에서 **파일** \> **계정**(Outlook에서는 **Office 계정**)으로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="580dc-111">To determine if you have the Click-to-Run version of Office, in any Office app go to **File** \> **Account** ( **Office Account** in Outlook).</span></span> <span data-ttu-id="580dc-112">다음 그림에 **표시된 Office 업데이트가** 표시된 경우 설치가 클릭하여 실행을 통해 수행된 것입니다.</span><span class="sxs-lookup"><span data-stu-id="580dc-112">If you see **Office Updates** as shown in the following figure, then the installation was done by using Click-to-Run.</span></span> 
  
![Screenshot of Office updates in Office app Account](../media/e3439380-fa43-4ed6-ae5d-64851c297df5.png)
  
 <span data-ttu-id="580dc-114">**이 기능을 사용하면 이점이 있는 사람**</span><span class="sxs-lookup"><span data-stu-id="580dc-114">**Who benefits from having this feature**</span></span>
  
<span data-ttu-id="580dc-115">다음과 같은 PC 환경을 사용하는 최종 사용자에게 유용합니다.</span><span class="sxs-lookup"><span data-stu-id="580dc-115">The end user whose PC:</span></span>
  
- <span data-ttu-id="580dc-116"> Windows 10 Business 사용자 라이선스, 활성 비즈니스용 Microsoft 365 라이선스, Windows 10 크리에이터스 업데이트가 있으며 Azure Active Directory에 가입되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="580dc-116">**Has**  a Windows 10 Business user license, an active Microsoft 365 for business license, Windows 10 Creators Update, and is joined to Azure Active Directory.</span></span> 
    
- <span data-ttu-id="580dc-117"> 64비트 Office 앱이 없습니다(예: Word, Excel, PowerPoint).</span><span class="sxs-lookup"><span data-stu-id="580dc-117">**Doesn't have** 64-bit Office apps (example: Word, Excel, PowerPoint).</span></span> <span data-ttu-id="580dc-118">64비트 Office 앱이 필요한 경우 비즈니스용 Microsoft 365 관리 콘솔에서 64비트 2016 Click-to-Run 버전의 Office를 트리거할 수 있기 때문에 이 기능이 적합하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="580dc-118">If 64-bit Office apps are required, then this feature isn't a good fit because there's no support for triggering a 64-bit 2016 Click-to-Run version of Office from the Microsoft 365 for business admin console.</span></span> 
    
- <span data-ttu-id="580dc-119">2016 Windows Installer(MSI) 독립 실행형 앱(예: Visio 또는 Project)을 **보유하지 않은** 경우.</span><span class="sxs-lookup"><span data-stu-id="580dc-119">**Doesn't have** any 2016 Windows Installer (MSI) standalone apps (for example, Visio or Project).</span></span> <span data-ttu-id="580dc-120">비즈니스용 Microsoft 365는 Office를 Click-to-Run 버전의 Office 2016으로 업그레이드하며 Office 2016 MSI 독립 실행형 앱에서는 작동하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="580dc-120">Microsoft 365 for business upgrades Office to the Click-to-Run version of Office 2016 and that doesn't work with Office 2016 MSI standalone apps.</span></span> 
    
<span data-ttu-id="580dc-121">다음 표에서는 비즈니스용 Microsoft 365 관리 콘솔에서 32비트의 Click-to-Run 버전의 Office 배포를 성공적으로 수행하기 위해 최종 사용자/관리자가 시작 상태에 따라 취해야 할 수 있는 작업을 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="580dc-121">The following table shows what action the end users/admins may need to take, depending on their beginning state, to have a successful 32-bit Click-to-Run version of Office deployment from the Microsoft 365 for business admin console.</span></span>
  
|<span data-ttu-id="580dc-122">**Office 설치 시작 상태**</span><span class="sxs-lookup"><span data-stu-id="580dc-122">**Starting Office install status**</span></span>|<span data-ttu-id="580dc-123">**비즈니스용 Microsoft 365 Office 설치 전에 취할 작업**</span><span class="sxs-lookup"><span data-stu-id="580dc-123">**Action to take before Microsoft 365 for business Office install**</span></span>|<span data-ttu-id="580dc-124">**종료 상태**</span><span class="sxs-lookup"><span data-stu-id="580dc-124">**End state**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="580dc-125">설치된 Office 제품군이 없는 경우</span><span class="sxs-lookup"><span data-stu-id="580dc-125">No Office suite installed</span></span>  <br/> |<span data-ttu-id="580dc-126">없음</span><span class="sxs-lookup"><span data-stu-id="580dc-126">None</span></span>  <br/> |<span data-ttu-id="580dc-127">Click-to-Run을 사용하여 Office 2016 32비트가 설치됩니다.</span><span class="sxs-lookup"><span data-stu-id="580dc-127">Office 2016 32-bit is installed by using Click-to-Run</span></span>  <br/> |
|<span data-ttu-id="580dc-128">간편 실행 32비트 버전의 Office(2016 이하)가 있고 독립 실행형 앱이 없는 경우</span><span class="sxs-lookup"><span data-stu-id="580dc-128">Existing Click-to-Run 32-bit version of Office (2016 or earlier) and no standalone apps</span></span>  <br/> |<span data-ttu-id="580dc-129">없음</span><span class="sxs-lookup"><span data-stu-id="580dc-129">None</span></span>  <br/> |<span data-ttu-id="580dc-130">Upgraded to the latest 32-bit Click-to-Run version of Office 2016, as needed **\***</span><span class="sxs-lookup"><span data-stu-id="580dc-130">Upgraded to the latest 32-bit Click-to-Run version of Office 2016, as needed **\***</span></span> <br/> |
|<span data-ttu-id="580dc-131">기존 Click-to-Run 32비트 버전의 Office 및 Click-to-Run 32비트 또는 64비트 독립 실행형 Office 앱(예: Visio, Project)</span><span class="sxs-lookup"><span data-stu-id="580dc-131">Existing Click-to-Run 32-bit version of Office and Click-to-Run 32-bit or 64-bit standalone Office apps (for example, Visio, Project)</span></span>  <br/> |<span data-ttu-id="580dc-132">없음</span><span class="sxs-lookup"><span data-stu-id="580dc-132">None</span></span>  <br/> |<span data-ttu-id="580dc-133">독립 실행형 앱은 영향을 받지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="580dc-133">Standalone apps aren't affected.</span></span> <span data-ttu-id="580dc-134">제품군이 간편 실행 32비트 버전의 Office 2016으로 업그레이드됩니다.</span><span class="sxs-lookup"><span data-stu-id="580dc-134">Suite is upgraded to Click-to-Run 32-bit version of Office 2016</span></span>  <br/> |
|<span data-ttu-id="580dc-135">간편 실행 32비트 버전의 Office 및 32비트 또는 64비트(2016 제외) MSI 독립 실행형 Office 앱이 있는 경우</span><span class="sxs-lookup"><span data-stu-id="580dc-135">Existing Click-to-Run 32-bit version of Office and any 32-bit or 64-bit (except 2016) MSI standalone Office apps</span></span>  <br/> |<span data-ttu-id="580dc-136">없음</span><span class="sxs-lookup"><span data-stu-id="580dc-136">None</span></span>  <br/> |<span data-ttu-id="580dc-137">독립 실행형 앱은 영향을 받지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="580dc-137">Standalone apps aren't affected.</span></span> <span data-ttu-id="580dc-138">제품군이 간편 실행 32비트 버전의 Office 2016으로 업그레이드됩니다.</span><span class="sxs-lookup"><span data-stu-id="580dc-138">Suite is upgraded to Click-to-Run 32-bit version of Office 2016</span></span>  <br/> ||||
|<span data-ttu-id="580dc-139">간편 실행 64비트 버전의 Office가 있는 경우</span><span class="sxs-lookup"><span data-stu-id="580dc-139">Any existing Click-to-Run 64-bit version of Office</span></span>  <br/> |<span data-ttu-id="580dc-140">32비트 Office 앱으로 바꾸는 것이 괜찮은 경우 64비트 Office 앱 제거</span><span class="sxs-lookup"><span data-stu-id="580dc-140">Uninstall the 64-bit Office apps, if it's OK to replace them with 32-bit Office apps</span></span>  <br/> |<span data-ttu-id="580dc-141">Office 64비트 앱이 제거된 경우 간편 실행 32비트 버전의 Office 2016이 설치됩니다.</span><span class="sxs-lookup"><span data-stu-id="580dc-141">If Office 64-bit apps are removed, the Click-to-Run 32-bit version of Office 2016 is installed</span></span>  <br/> |
|<span data-ttu-id="580dc-142">독립 실행형 앱 유무와 상관없이 Office 2016의 MSI 설치가 있는 경우</span><span class="sxs-lookup"><span data-stu-id="580dc-142">An existing MSI install of Office 2016 with or without standalone apps</span></span>  <br/> |<span data-ttu-id="580dc-143">MSI Office 2016을 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="580dc-143">Uninstall MSI Office 2016.</span></span>  <br/> |<span data-ttu-id="580dc-p106">간편 실행 32비트 버전의 Office 2016이 설치됩니다. 독립 실행형 앱은 변경되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="580dc-p106">Click-to-Run 32-bit version of Office 2016 is installed. No change to standalone apps</span></span>  <br/> |
|<span data-ttu-id="580dc-146">Office 2013(또는 이전 버전)의 MSI 설치 및/또는 독립 실행형 Office 앱이 있는 경우</span><span class="sxs-lookup"><span data-stu-id="580dc-146">Existing MSI install of Office 2013 (or earlier) and/or standalone Office apps</span></span>  <br/> |<span data-ttu-id="580dc-147">없음</span><span class="sxs-lookup"><span data-stu-id="580dc-147">None</span></span>  <br/> |<span data-ttu-id="580dc-148">기존 MSI Office 설치가 포함된 간편 실행 32비트 버전의 Office 2016과 독립 실행형 앱이 함께 존재합니다.</span><span class="sxs-lookup"><span data-stu-id="580dc-148">Click-to-Run 32-bit version of Office 2016 with the pre-existing MSI Office install (and standalone apps) exist side-by-side</span></span>  <br/> |
||||
   
 <span data-ttu-id="580dc-149">**(\*) 참고:** 알려진 버그로 인해 간편 실행 32비트 버전의 Office 2016으로 업그레이드되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="580dc-149">**(\*) Note:** Does not upgrade to Click-to-Run 32-bit version of Office 2016 due to a known bug.</span></span> <span data-ttu-id="580dc-150">수정이 진행 중입니다.</span><span class="sxs-lookup"><span data-stu-id="580dc-150">A fix is in progress.</span></span> 
  
