---
title: 비즈니스용 Office 클라이언트 배포를 Microsoft 365 준비
f1.keywords:
- CSH
ms.author: efrene
author: efrene
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
description: Windows 10 컴퓨터에 32비트 Office 앱을 자동으로 설치하고 업데이트된 Windows 10 방법을 배워야 합니다.
ms.openlocfilehash: 843be426d817da1173769b3b66dc4c054179f0fd
ms.sourcegitcommit: be929f79751c0c52dfa6bd98a854432a0c63faf0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/14/2021
ms.locfileid: "52924230"
---
# <a name="prepare-for-office-client-deployment-by-microsoft-365-for-business"></a><span data-ttu-id="47f92-103">비즈니스용 Office 클라이언트 배포를 Microsoft 365 준비</span><span class="sxs-lookup"><span data-stu-id="47f92-103">Prepare for Office client deployment by Microsoft 365 for business</span></span>

<span data-ttu-id="47f92-104">이 문서는 이 문서에 Microsoft 365 Business Premium.</span><span class="sxs-lookup"><span data-stu-id="47f92-104">This article applies to Microsoft 365 Business Premium.</span></span>

## <a name="prepare-to-automatically-install-office-apps-to-client-computers"></a><span data-ttu-id="47f92-105">클라이언트 컴퓨터에 Office 앱 자동 설치 준비</span><span class="sxs-lookup"><span data-stu-id="47f92-105">Prepare to automatically install Office apps to client computers</span></span>

<span data-ttu-id="47f92-106">32비트 Microsoft 365 Business Premium 컴퓨터에 32비트 Office 앱을 자동으로 설치하고 Windows 10 최신 앱으로 유지할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="47f92-106">You can use Microsoft 365 Business Premium to automatically install the 32-bit Office apps on Windows 10 computers and keep them current with updates.</span></span>
  
<span data-ttu-id="47f92-107">자동 설치는 최종 사용자의 컴퓨터가 다음 Windows 10 Business 가장 잘 작동합니다.</span><span class="sxs-lookup"><span data-stu-id="47f92-107">Automatic installation works best if the end user's computer is on Windows 10 Business and:</span></span>
  
- <span data-ttu-id="47f92-108">기존 Office 데스크톱 앱(Word, Excel, PowerPoint, Outlook, OneNote, Publisher, Access, 및 OneDrive)이 없는 경우</span><span class="sxs-lookup"><span data-stu-id="47f92-108">Doesn't have existing Office desktop apps (Word, Excel, PowerPoint, Outlook, OneNote, Publisher, Access, and OneDrive).</span></span>
    
    <span data-ttu-id="47f92-109">또는</span><span class="sxs-lookup"><span data-stu-id="47f92-109">or</span></span>
    
- <span data-ttu-id="47f92-110">기존 간편 실행 버전의 Office가 설치된 경우</span><span class="sxs-lookup"><span data-stu-id="47f92-110">Has an existing version of Click-to-Run Office installed.</span></span>
    
<span data-ttu-id="47f92-111">간편 실행 버전의 Office가 있는지 확인하려는 경우 Office 앱에서 **파일** \> **계정**(Outlook에서는 **Office 계정**)으로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="47f92-111">To determine if you have the Click-to-Run version of Office, in any Office app go to **File** \> **Account** ( **Office Account** in Outlook).</span></span> <span data-ttu-id="47f92-112">다음 그림에 Office 업데이트가 표시되어 있는 경우 Click-to-Run을 사용하여 설치를 수행한 것입니다. </span><span class="sxs-lookup"><span data-stu-id="47f92-112">If you see **Office Updates** as shown in the following figure, then the installation was done by using Click-to-Run.</span></span> 
  
![Screenshot of Office updates in Office app Account](../media/e3439380-fa43-4ed6-ae5d-64851c297df5.png)
  
 <span data-ttu-id="47f92-114">**Who 기능을 사용할 경우의 이점**</span><span class="sxs-lookup"><span data-stu-id="47f92-114">**Who benefits from having this feature**</span></span>
  
<span data-ttu-id="47f92-115">다음과 같은 PC 환경을 사용하는 최종 사용자에게 유용합니다.</span><span class="sxs-lookup"><span data-stu-id="47f92-115">The end user whose PC:</span></span>
  
- <span data-ttu-id="47f92-116">**사용자** Windows 10 Business 라이선스, 비즈니스용 활성 Microsoft 365 라이선스, Windows 10 크리에이터스 업데이트가 있으며 Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="47f92-116">**Has**  a Windows 10 Business user license, an active Microsoft 365 for business license, Windows 10 Creators Update, and is joined to Azure Active Directory.</span></span> 
    
- <span data-ttu-id="47f92-117">**64비트** Office(예: Word, Excel, PowerPoint).</span><span class="sxs-lookup"><span data-stu-id="47f92-117">**Doesn't have** 64-bit Office apps (example: Word, Excel, PowerPoint).</span></span> <span data-ttu-id="47f92-118">64비트 Office 앱이 필요한 경우 비즈니스용 앱 콘솔에서 64비트 2016 Click-to-Run 버전을 트리거하는 Office 지원이 Microsoft 365 적합하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="47f92-118">If 64-bit Office apps are required, then this feature isn't a good fit because there's no support for triggering a 64-bit 2016 Click-to-Run version of Office from the Microsoft 365 for business admin console.</span></span> 
    
- <span data-ttu-id="47f92-119">2016 Windows Installer(MSI) 독립 실행형 앱(예: Visio 또는 Project)을 **보유하지 않은** 경우.</span><span class="sxs-lookup"><span data-stu-id="47f92-119">**Doesn't have** any 2016 Windows Installer (MSI) standalone apps (for example, Visio or Project).</span></span> <span data-ttu-id="47f92-120">Microsoft 365 비즈니스용 업그레이드는 Office 2016의 Click-to-Run 버전으로 Office 2016 MSI 독립 실행형 Office 작동하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="47f92-120">Microsoft 365 for business upgrades Office to the Click-to-Run version of Office 2016 and that doesn't work with Office 2016 MSI standalone apps.</span></span> 
    
<span data-ttu-id="47f92-121">다음 표에는 비즈니스용 Microsoft 365 콘솔에서 32비트의 32비트 Click-to-Run 버전을 성공적으로 배포하기 위해 최종 사용자/관리자가 시작 상태와 관계없이 Office 수 있는 작업을 보여 줄 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="47f92-121">The following table shows what action the end users/admins may need to take, depending on their beginning state, to have a successful 32-bit Click-to-Run version of Office deployment from the Microsoft 365 for business admin console.</span></span><br/>


|<span data-ttu-id="47f92-122">Office 설치 시작 상태</span><span class="sxs-lookup"><span data-stu-id="47f92-122">Starting Office install status</span></span>|<span data-ttu-id="47f92-123">비즈니스용 비즈니스 Microsoft 365 설치하기 Office 작업</span><span class="sxs-lookup"><span data-stu-id="47f92-123">Action to take before Microsoft 365 for business Office install</span></span>|<span data-ttu-id="47f92-124">최종 상태</span><span class="sxs-lookup"><span data-stu-id="47f92-124">End state</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="47f92-125">설치된 Office 제품군이 없는 경우</span><span class="sxs-lookup"><span data-stu-id="47f92-125">No Office suite installed</span></span>  <br/> |<span data-ttu-id="47f92-126">없음</span><span class="sxs-lookup"><span data-stu-id="47f92-126">None</span></span>  <br/> |<span data-ttu-id="47f92-127">Office 사용하여 2016 32비트 설치</span><span class="sxs-lookup"><span data-stu-id="47f92-127">Office 2016 32-bit is installed by using Click-to-Run</span></span>  <br/> |
|<span data-ttu-id="47f92-128">간편 실행 32비트 버전의 Office(2016 이하)가 있고 독립 실행형 앱이 없는 경우</span><span class="sxs-lookup"><span data-stu-id="47f92-128">Existing Click-to-Run 32-bit version of Office (2016 or earlier) and no standalone apps</span></span>  <br/> |<span data-ttu-id="47f92-129">없음</span><span class="sxs-lookup"><span data-stu-id="47f92-129">None</span></span>  <br/> |<span data-ttu-id="47f92-130">Upgraded to the latest 32-bit Click-to-Run version of Office 2016, as needed **\***</span><span class="sxs-lookup"><span data-stu-id="47f92-130">Upgraded to the latest 32-bit Click-to-Run version of Office 2016, as needed **\***</span></span> <br/> |
|<span data-ttu-id="47f92-131">기존 Click-to-Run 32비트 버전의 Office 및 32비트 또는 64비트 독립 실행형 Office 앱(예: Visio, Project)</span><span class="sxs-lookup"><span data-stu-id="47f92-131">Existing Click-to-Run 32-bit version of Office and Click-to-Run 32-bit or 64-bit standalone Office apps (for example, Visio, Project)</span></span>  <br/> |<span data-ttu-id="47f92-132">없음</span><span class="sxs-lookup"><span data-stu-id="47f92-132">None</span></span>  <br/> |<span data-ttu-id="47f92-133">독립 실행형 앱은 영향을 받지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="47f92-133">Standalone apps aren't affected.</span></span> <span data-ttu-id="47f92-134">제품군이 간편 실행 32비트 버전의 Office 2016으로 업그레이드됩니다.</span><span class="sxs-lookup"><span data-stu-id="47f92-134">Suite is upgraded to Click-to-Run 32-bit version of Office 2016</span></span>  <br/> |
|<span data-ttu-id="47f92-135">간편 실행 32비트 버전의 Office 및 32비트 또는 64비트(2016 제외) MSI 독립 실행형 Office 앱이 있는 경우</span><span class="sxs-lookup"><span data-stu-id="47f92-135">Existing Click-to-Run 32-bit version of Office and any 32-bit or 64-bit (except 2016) MSI standalone Office apps</span></span>  <br/> |<span data-ttu-id="47f92-136">없음</span><span class="sxs-lookup"><span data-stu-id="47f92-136">None</span></span>  <br/> |<span data-ttu-id="47f92-137">독립 실행형 앱은 영향을 받지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="47f92-137">Standalone apps aren't affected.</span></span> <span data-ttu-id="47f92-138">제품군이 간편 실행 32비트 버전의 Office 2016으로 업그레이드됩니다.</span><span class="sxs-lookup"><span data-stu-id="47f92-138">Suite is upgraded to Click-to-Run 32-bit version of Office 2016</span></span>  <br/> |
|<span data-ttu-id="47f92-139">간편 실행 64비트 버전의 Office가 있는 경우</span><span class="sxs-lookup"><span data-stu-id="47f92-139">Any existing Click-to-Run 64-bit version of Office</span></span>  <br/> |<span data-ttu-id="47f92-140">64비트 Office 앱을 32비트 앱으로 바꾸면 됩니다Office 제거</span><span class="sxs-lookup"><span data-stu-id="47f92-140">Uninstall the 64-bit Office apps, if it's OK to replace them with 32-bit Office apps</span></span>  <br/> |<span data-ttu-id="47f92-141">Office 64비트 앱이 제거된 경우 간편 실행 32비트 버전의 Office 2016이 설치됩니다.</span><span class="sxs-lookup"><span data-stu-id="47f92-141">If Office 64-bit apps are removed, the Click-to-Run 32-bit version of Office 2016 is installed</span></span>  <br/> |
|<span data-ttu-id="47f92-142">독립 실행형 앱 유무와 상관없이 Office 2016의 MSI 설치가 있는 경우</span><span class="sxs-lookup"><span data-stu-id="47f92-142">An existing MSI install of Office 2016 with or without standalone apps</span></span>  <br/> |<span data-ttu-id="47f92-143">MSI Office 2016을 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="47f92-143">Uninstall MSI Office 2016.</span></span>  <br/> |<span data-ttu-id="47f92-p106">간편 실행 32비트 버전의 Office 2016이 설치됩니다. 독립 실행형 앱은 변경되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="47f92-p106">Click-to-Run 32-bit version of Office 2016 is installed. No change to standalone apps</span></span>  <br/> |
|<span data-ttu-id="47f92-146">Office 2013(또는 이전 버전)의 MSI 설치 및/또는 독립 실행형 Office 앱이 있는 경우</span><span class="sxs-lookup"><span data-stu-id="47f92-146">Existing MSI install of Office 2013 (or earlier) and/or standalone Office apps</span></span>  <br/> |<span data-ttu-id="47f92-147">없음</span><span class="sxs-lookup"><span data-stu-id="47f92-147">None</span></span>  <br/> |<span data-ttu-id="47f92-148">기존 MSI Office 설치가 포함된 간편 실행 32비트 버전의 Office 2016과 독립 실행형 앱이 함께 존재합니다.</span><span class="sxs-lookup"><span data-stu-id="47f92-148">Click-to-Run 32-bit version of Office 2016 with the pre-existing MSI Office install (and standalone apps) exist side-by-side</span></span>  <br/> |
||||
   
 <span data-ttu-id="47f92-149">**(\*) 참고:** 알려진 버그로 인해 간편 실행 32비트 버전의 Office 2016으로 업그레이드되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="47f92-149">**(\*) Note:** Does not upgrade to Click-to-Run 32-bit version of Office 2016 due to a known bug.</span></span> <span data-ttu-id="47f92-150">수정이 진행 중입니다.</span><span class="sxs-lookup"><span data-stu-id="47f92-150">A fix is in progress.</span></span> 
  
