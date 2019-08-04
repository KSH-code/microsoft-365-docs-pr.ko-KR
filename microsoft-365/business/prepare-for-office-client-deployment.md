---
title: Microsoft 365 Business를 사용한 Office 클라이언트 배포 준비
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
search.appverid:
- BCS160
- MET150
ms.assetid: ed34fff3-2881-4ed4-9906-1ba6bb8dd804
description: Windows 10 컴퓨터에 32 비트 Office 앱을 자동으로 설치 하 고 업데이트 된 상태로 유지 하는 방법을 알아봅니다.
ms.openlocfilehash: 20269c493b0e3b5a7deb56a24a5e1a9583ef9d0a
ms.sourcegitcommit: 66bb5af851947078872a4d31d3246e69f7dd42bb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/15/2019
ms.locfileid: "34074653"
---
# <a name="prepare-for-office-client-deployment-by-microsoft-365-business"></a><span data-ttu-id="c8303-103">Microsoft 365 Business를 사용한 Office 클라이언트 배포 준비</span><span class="sxs-lookup"><span data-stu-id="c8303-103">Prepare for Office client deployment by Microsoft 365 Business</span></span>

## <a name="prepare-to-automatically-install-office-apps-to-client-computers"></a><span data-ttu-id="c8303-104">클라이언트 컴퓨터에 Office 앱 자동 설치 준비</span><span class="sxs-lookup"><span data-stu-id="c8303-104">Prepare to automatically install Office apps to client computers</span></span>

<span data-ttu-id="c8303-105">Microsoft 365 Business를 사용하여 32비트 Offce 앱을 Windows 10 컴퓨터에 자동으로 설치하고 항상 최신 상태로 유지할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c8303-105">You can use Microsoft 365 Business to automatically install the 32-bit Office apps to Windows 10 computers and keep them current with updates.</span></span>
  
<span data-ttu-id="c8303-106">이 설치는 최종 사용자의 컴퓨터에서 Windows 10 Business를 사용하고, 컴퓨터 환경이 다음과 같은 경우에 가장 잘 작동합니다.</span><span class="sxs-lookup"><span data-stu-id="c8303-106">This works best if the end user's computer is on Windows 10 Business and:</span></span>
  
- <span data-ttu-id="c8303-107">기존 Office 데스크톱 앱(Word, Excel, PowerPoint, Outlook, OneNote, Publisher, Access, 및 OneDrive)이 없는 경우</span><span class="sxs-lookup"><span data-stu-id="c8303-107">Doesn't have existing Office desktop apps (Word, Excel, PowerPoint, Outlook, OneNote, Publisher, Access, and OneDrive).</span></span>
    
    <span data-ttu-id="c8303-108">또는</span><span class="sxs-lookup"><span data-stu-id="c8303-108">or</span></span>
    
- <span data-ttu-id="c8303-109">기존 간편 실행 버전의 Office가 설치된 경우</span><span class="sxs-lookup"><span data-stu-id="c8303-109">Has an existing version of Click-to-Run Office installed.</span></span>
    
<span data-ttu-id="c8303-p101">간편 실행 버전의 Office가 있는지 확인하려는 경우 Office 앱에서 **파일** \> **계정**(Outlook에서는 **Office 계정**)으로 이동합니다. 다음 그림과 같이 Office 업데이트가 표시되면 간편 실행을 통해 설치되었음을 의미합니다.</span><span class="sxs-lookup"><span data-stu-id="c8303-p101">To determine if you have the Click-to-Run version of Office, in any Office app go to **File** \> **Account** ( **Office Account** in Outlook). If you see Office Updates as shown in the following figure, then the installation was done by using Click-to-Run.</span></span> 
  
![Screenshot of Office updates in Office app Account](media/e3439380-fa43-4ed6-ae5d-64851c297df5.png)
  
 <span data-ttu-id="c8303-113">**이 기능은 어떤 사람에게 유용한가요?**</span><span class="sxs-lookup"><span data-stu-id="c8303-113">**Who will benefit from having this feature**</span></span>
  
<span data-ttu-id="c8303-114">다음과 같은 PC 환경을 사용하는 최종 사용자에게 유용합니다.</span><span class="sxs-lookup"><span data-stu-id="c8303-114">The end user whose PC:</span></span>
  
- <span data-ttu-id="c8303-115">**Has**  a Windows 10 Business user license, an active Microsoft 365 Business license, Windows 10 Creators Update, and is joined to Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="c8303-115">**Has**  a Windows 10 Business user license, an active Microsoft 365 Business license, Windows 10 Creators Update, and is joined to Azure Active Directory.</span></span> 
    
- <span data-ttu-id="c8303-p102">64비트 Office 앱(예: Word, Excel, PowerPoint)을 **보유하지 않은** 경우. Microsoft 365 Business 관리 콘솔에서 64비트 2016 간편 실행 버전의 Office를 트리거하는 기능을 지원하지 않으므로 64비트 Office 앱이 필요한 경우 이 기능을 사용하지 않는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="c8303-p102">**Doesn't have** 64-bit Office apps (example: Word, Excel, Powerpoint). If 64-bit Office apps are required, then this feature is not a good fit because there is no support for triggering a 64-bit 2016 Click-to-Run version of Office from the Microsoft 365 Business admin console.</span></span> 
    
- <span data-ttu-id="c8303-p103">2016 Windows Installer(MSI) 독립 실행형 앱(예: Visio 또는 Project)을 **보유하지 않은** 경우. Microsoft 365 Business는 Office를 간편 실행 버전의 Office 2016으로 업그레이드하며 Office 2016 MSI 독립 실행형 앱과 함께 작동하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c8303-p103">**Doesn't have** any 2016 Windows Installer (MSI) standalone apps (for example, Visio or Project). Microsoft 365 Business upgrades Office to the Click-to-Run version of Office 2016 and that doesn't work with with Office 2016 MSI standalone apps.</span></span> 
    
<span data-ttu-id="c8303-120">다음 표에서는 Microsoft 365 Business 관리 콘솔에서 Office 32비트 간편 실행 버전을 성공적으로 배포하기 위해 최종 사용자 또는 관리자가 수행해야 하는 작업에 대해 시작 상태별로 구분하여 자세히 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="c8303-120">The following table details what action the end users/admins may need to take, depending on their beginning state, to have a successful 32-bit Click-to-Run version of Office deployment from the Microsoft 365 Business admin console.</span></span>
  
|<span data-ttu-id="c8303-121">**Office 설치 시작 상태**</span><span class="sxs-lookup"><span data-stu-id="c8303-121">**Starting Office install status**</span></span>|<span data-ttu-id="c8303-122">**Microsoft 365 Business Office 설치 전 수행해야 하는 작업**</span><span class="sxs-lookup"><span data-stu-id="c8303-122">**Action to take before Microsoft 365 Business Office install**</span></span>|<span data-ttu-id="c8303-123">**종료 상태**</span><span class="sxs-lookup"><span data-stu-id="c8303-123">**End state**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="c8303-124">설치된 Office 제품군이 없는 경우</span><span class="sxs-lookup"><span data-stu-id="c8303-124">No Office suite installed</span></span>  <br/> |<span data-ttu-id="c8303-125">없음</span><span class="sxs-lookup"><span data-stu-id="c8303-125">None</span></span>  <br/> |<span data-ttu-id="c8303-126">간편 실행을 사용하여 Office 2016 32비트가 설치됩니다.</span><span class="sxs-lookup"><span data-stu-id="c8303-126">Office 2016 32-bit is installed by using click-to-run</span></span>  <br/> |
|<span data-ttu-id="c8303-127">간편 실행 32비트 버전의 Office(2016 이하)가 있고 독립 실행형 앱이 없는 경우</span><span class="sxs-lookup"><span data-stu-id="c8303-127">Existing Click-to-Run 32-bit version of Office (2016 or earlier) and no standalone apps</span></span>  <br/> |<span data-ttu-id="c8303-128">없음</span><span class="sxs-lookup"><span data-stu-id="c8303-128">None</span></span>  <br/> |<span data-ttu-id="c8303-129">Upgraded to the latest 32-bit Click-to-Run version of Office 2016, as needed **\***</span><span class="sxs-lookup"><span data-stu-id="c8303-129">Upgraded to the latest 32-bit Click-to-Run version of Office 2016, as needed **\***</span></span> <br/> |
|<span data-ttu-id="c8303-130">간편 실행 32비트 버전의 Office 및 간편 실행 32비트 또는 64비트 독립 실행형 Office 앱이 있는 경우(예: Visio, Project)</span><span class="sxs-lookup"><span data-stu-id="c8303-130">Existing Click-to-Run 32-bit version of Office and Click-to-Run 32- or 64-bit standalone Office apps (for example, Visio, Project)</span></span>  <br/> |<span data-ttu-id="c8303-131">없음</span><span class="sxs-lookup"><span data-stu-id="c8303-131">None</span></span>  <br/> |<span data-ttu-id="c8303-p104">독립 실행형 앱은 영향을 받지 않습니다. 제품군이 간편 실행 32비트 버전의 Office 2016으로 업그레이드됩니다.</span><span class="sxs-lookup"><span data-stu-id="c8303-p104">Standalone apps are not affected. Suite is upgraded to Click-to-Run 32-bit version of Office 2016</span></span>  <br/> |
|<span data-ttu-id="c8303-134">간편 실행 32비트 버전의 Office 및 32비트 또는 64비트(2016 제외) MSI 독립 실행형 Office 앱이 있는 경우</span><span class="sxs-lookup"><span data-stu-id="c8303-134">Existing Click-to-Run 32-bit version of Office and any 32-bit or 64-bit (except 2016) MSI standalone Office apps</span></span>  <br/> |<span data-ttu-id="c8303-135">없음</span><span class="sxs-lookup"><span data-stu-id="c8303-135">None</span></span>  <br/> |<span data-ttu-id="c8303-p105">독립 실행형 앱은 영향을 받지 않습니다. 제품군이 간편 실행 32비트 버전의 Office 2016으로 업그레이드됩니다.</span><span class="sxs-lookup"><span data-stu-id="c8303-p105">Standalone apps are not affected. Suite is upgraded to Click-to-Run 32-bit version of Office 2016</span></span>  <br/> ||||
|<span data-ttu-id="c8303-138">간편 실행 64비트 버전의 Office가 있는 경우</span><span class="sxs-lookup"><span data-stu-id="c8303-138">Any existing Click-to-Run 64-bit version of Office</span></span>  <br/> |<span data-ttu-id="c8303-139">32비트 Office 앱으로 변경해도 괜찮은 경우 64비트 Office 앱을 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="c8303-139">Uninstall the 64-bit Office apps, if it is OK to replace it with 32-bit Office apps</span></span>  <br/> |<span data-ttu-id="c8303-140">Office 64비트 앱이 제거된 경우 간편 실행 32비트 버전의 Office 2016이 설치됩니다.</span><span class="sxs-lookup"><span data-stu-id="c8303-140">If Office 64-bit apps are removed, the Click-to-Run 32-bit version of Office 2016 is installed</span></span>  <br/> |
|<span data-ttu-id="c8303-141">독립 실행형 앱 유무와 상관없이 Office 2016의 MSI 설치가 있는 경우</span><span class="sxs-lookup"><span data-stu-id="c8303-141">An existing MSI install of Office 2016 with or without standalone apps</span></span>  <br/> |<span data-ttu-id="c8303-142">MSI Office 2016을 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="c8303-142">Uninstall MSI Office 2016.</span></span>  <br/> |<span data-ttu-id="c8303-p106">간편 실행 32비트 버전의 Office 2016이 설치됩니다. 독립 실행형 앱은 변경되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c8303-p106">Click-to-Run 32-bit version of Office 2016 is installed. No change to standalone apps</span></span>  <br/> |
|<span data-ttu-id="c8303-145">Office 2013(또는 이전 버전)의 MSI 설치 및/또는 독립 실행형 Office 앱이 있는 경우</span><span class="sxs-lookup"><span data-stu-id="c8303-145">Existing MSI install of Office 2013 (or earlier) and/or standalone Office apps</span></span>  <br/> |<span data-ttu-id="c8303-146">없음</span><span class="sxs-lookup"><span data-stu-id="c8303-146">None</span></span>  <br/> |<span data-ttu-id="c8303-147">기존 MSI Office 설치가 포함된 간편 실행 32비트 버전의 Office 2016과 독립 실행형 앱이 함께 존재합니다.</span><span class="sxs-lookup"><span data-stu-id="c8303-147">Click-to-Run 32-bit version of Office 2016 with the pre-existing MSI Office install (and standalone apps) exist side-by-side</span></span>  <br/> |
||||
   
 <span data-ttu-id="c8303-p107">**(\*) 참고:** 알려진 버그로 인해 간편 실행 32비트 버전의 Office 2016으로 업그레이드되지 않습니다. 해당 문제는 해결 중입니다.</span><span class="sxs-lookup"><span data-stu-id="c8303-p107">**(\*) Note:** Does not upgrade to Click-to-Run 32-bit version of Office 2016 due to a known bug. Fix is in progress.</span></span> 
  


