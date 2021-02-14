---
title: 비즈니스용 Microsoft 365를 사용하여 디바이스의 데이터 보호를 위한 선행 준비
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
ms.collection: M365-subscription-management
ms.custom:
- Core_O365Admin_Migration
- MiniMaven
- MSB365
- OKR_SMB_M365
- seo-marvel-mar
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
ms.assetid: 7770e280-3a6c-436f-a157-b008a2744f51
description: 비즈니스용 Microsoft 365를 사용하여 조직을 설정하고 사용자의 장치에서 작업 데이터를 보호하기 위한 요구 사항에 대해 자세히 알아보습니다.
ms.openlocfilehash: 237825d2c2683bb6e71ae2fd31f8a25b1aa85ff7
ms.sourcegitcommit: e5bc49f0a25954d008b6cc09c2b98bb7bfe1aa2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/18/2020
ms.locfileid: "44785895"
---
# <a name="prerequisites-for-protecting-data-on-devices-with-microsoft-365-for-business"></a><span data-ttu-id="366d2-103">비즈니스용 Microsoft 365를 사용하여 디바이스의 데이터 보호를 위한 선행 준비</span><span class="sxs-lookup"><span data-stu-id="366d2-103">Prerequisites for protecting data on devices with Microsoft 365 for business</span></span>

<span data-ttu-id="366d2-104">이 문서는 Microsoft 365 Business Premium에 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="366d2-104">This article applies to Microsoft 365 Business Premium.</span></span>

<span data-ttu-id="366d2-105">비즈니스용 Microsoft 365를 사용하여 조직을 설정하는 첫 번째 단계는 선행 요구 사항을 충족할 수 있도록 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="366d2-105">The first step in setting up your organization with Microsoft 365 for business is to make sure you can meet the prerequisites.</span></span>
  
## <a name="requirements-for-setting-up-your-organization-with-microsoft-365-for-business"></a><span data-ttu-id="366d2-106">비즈니스용 Microsoft 365를 사용하여 조직을 설정하기 위한 요구 사항</span><span class="sxs-lookup"><span data-stu-id="366d2-106">Requirements for setting up your organization with Microsoft 365 for business</span></span>

- <span data-ttu-id="366d2-107">Windows 장치에서는 Windows 7 Professional, Windows 8 Pro 또는 Windows 8.1 Pro를 실행해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="366d2-107">Windows devices must be running Windows 7 Professional, Windows 8 Pro, or Windows 8.1 Pro.</span></span>
    
    [<span data-ttu-id="366d2-108">Windows Pro 크리에이터 업데이트로 Windows 장치 업그레이드</span><span class="sxs-lookup"><span data-stu-id="366d2-108">Upgrade Windows devices to Windows Pro Creators Update</span></span>](upgrade-to-windows-pro-creators-update.md)
    
    <span data-ttu-id="366d2-109">Windows 10 Home을 실행하는 경우 **Windows** 10 Pro를 구입해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="366d2-109">If you're running Windows 10 Home, then you must **purchase** Windows  10 Pro.</span></span> <span data-ttu-id="366d2-110">지침은 [Windows 10 Home을 Windows 10 Pro로](https://support.microsoft.com/office/0aee10c1-4d34-43ee-a325-579c6c2df90e) 업그레이드하는 방법을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="366d2-110">See [upgrade Windows 10 Home to Windows 10 Pro](https://support.microsoft.com/office/0aee10c1-4d34-43ee-a325-579c6c2df90e) for instructions.</span></span> 
    
- <span data-ttu-id="366d2-111">모바일 관리 솔루션(Mobile Iron, AirWatch 등)에서 장치를 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="366d2-111">Remove devices from mobile management solutions (Mobile Iron, AirWatch, and so on).</span></span> <span data-ttu-id="366d2-112">비즈니스용 Microsoft 365 모바일 관리에 조직의 모든 인원을 등록합니다.</span><span class="sxs-lookup"><span data-stu-id="366d2-112">You'll enroll all the people in your organization in Microsoft 365 for business mobile management.</span></span>
    
- <span data-ttu-id="366d2-113">Apple iOS 8.0 이상.</span><span class="sxs-lookup"><span data-stu-id="366d2-113">Apple iOS 8.0 and later.</span></span>
    
    <span data-ttu-id="366d2-114">Google Android 4.0 이상(Samsung KNOX Standard 4.0 이상 포함).</span><span class="sxs-lookup"><span data-stu-id="366d2-114">Google Android 4.0 and later (including Samsung KNOX Standard 4.0 and higher).</span></span> <span data-ttu-id="366d2-115">자세한 내용은 [Intune 지원 장치를 참조하세요.](https://go.microsoft.com/fwlink/p/?linkid=852307)</span><span class="sxs-lookup"><span data-stu-id="366d2-115">For more information, see [Intune supported devices](https://go.microsoft.com/fwlink/p/?linkid=852307).</span></span>
    
- <span data-ttu-id="366d2-116">사용자 컴퓨터에 기존 Office 응용 프로그램이 있는 경우 Office 클라이언트 설치 준비를 읽고 사용자 컴퓨터에 [Office](prepare-for-office-client-deployment.md) 2016을 설치하기 위해 비즈니스용 Microsoft 365를 설정하기 전에 필요한 단계를 파악합니다.</span><span class="sxs-lookup"><span data-stu-id="366d2-116">If you have existing Office applications on user computers, read [prepare for Office client installation](prepare-for-office-client-deployment.md) to understand steps you might need to take before you can set up Microsoft 365 for business to install Office 2016 on user computers.</span></span> 
