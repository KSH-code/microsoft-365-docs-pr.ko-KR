---
title: 비즈니스를 위해 Microsoft 365을 사용 하 여 장치의 데이터를 보호 하기 위한 필수 구성 요소
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
description: 비즈니스를 위해 Microsoft 365을 사용 하 여 조직을 설정 하 고 사용자의 장치에서 작업 데이터를 보호 하기 위한 요구 사항에 대해 알아봅니다.
ms.openlocfilehash: 237825d2c2683bb6e71ae2fd31f8a25b1aa85ff7
ms.sourcegitcommit: e5bc49f0a25954d008b6cc09c2b98bb7bfe1aa2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/18/2020
ms.locfileid: "44785895"
---
# <a name="prerequisites-for-protecting-data-on-devices-with-microsoft-365-for-business"></a><span data-ttu-id="52ec2-103">비즈니스를 위해 Microsoft 365을 사용 하 여 장치의 데이터를 보호 하기 위한 필수 구성 요소</span><span class="sxs-lookup"><span data-stu-id="52ec2-103">Prerequisites for protecting data on devices with Microsoft 365 for business</span></span>

<span data-ttu-id="52ec2-104">이 문서는 Microsoft 365 Business Premium에 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="52ec2-104">This article applies to Microsoft 365 Business Premium.</span></span>

<span data-ttu-id="52ec2-105">비즈니스를 위한 Microsoft 365을 사용 하 여 조직을 설정 하는 첫 번째 단계는 필수 구성 요소를 충족할 수 있는지 확인 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="52ec2-105">The first step in setting up your organization with Microsoft 365 for business is to make sure you can meet the prerequisites.</span></span>
  
## <a name="requirements-for-setting-up-your-organization-with-microsoft-365-for-business"></a><span data-ttu-id="52ec2-106">비즈니스를 위한 Microsoft 365을 사용 하 여 조직을 설정 하기 위한 요구 사항</span><span class="sxs-lookup"><span data-stu-id="52ec2-106">Requirements for setting up your organization with Microsoft 365 for business</span></span>

- <span data-ttu-id="52ec2-107">Windows 장치에서는 Windows 7 Professional, Windows 8 Pro 또는 Windows 8.1 Pro를 실행 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="52ec2-107">Windows devices must be running Windows 7 Professional, Windows 8 Pro, or Windows 8.1 Pro.</span></span>
    
    [<span data-ttu-id="52ec2-108">Windows Pro 크리에이터 업데이트로 Windows 장치 업그레이드</span><span class="sxs-lookup"><span data-stu-id="52ec2-108">Upgrade Windows devices to Windows Pro Creators Update</span></span>](upgrade-to-windows-pro-creators-update.md)
    
    <span data-ttu-id="52ec2-109">Windows 10 Home을 실행 하는 경우에는 windows 10 Pro를 **구입** 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="52ec2-109">If you're running Windows 10 Home, then you must **purchase** Windows  10 Pro.</span></span> <span data-ttu-id="52ec2-110">지침을 보려면 [windows 10 Home a windows 10 Pro로 업그레이드를](https://support.microsoft.com/office/0aee10c1-4d34-43ee-a325-579c6c2df90e) 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="52ec2-110">See [upgrade Windows 10 Home to Windows 10 Pro](https://support.microsoft.com/office/0aee10c1-4d34-43ee-a325-579c6c2df90e) for instructions.</span></span> 
    
- <span data-ttu-id="52ec2-111">모바일 관리 솔루션에서 장치 제거 (모바일 철, 락 시청 등)</span><span class="sxs-lookup"><span data-stu-id="52ec2-111">Remove devices from mobile management solutions (Mobile Iron, AirWatch, and so on).</span></span> <span data-ttu-id="52ec2-112">비즈니스 모바일 관리를 위해 Microsoft 365에서 조직의 모든 사용자를 등록 합니다.</span><span class="sxs-lookup"><span data-stu-id="52ec2-112">You'll enroll all the people in your organization in Microsoft 365 for business mobile management.</span></span>
    
- <span data-ttu-id="52ec2-113">Apple iOS 8.0 이상.</span><span class="sxs-lookup"><span data-stu-id="52ec2-113">Apple iOS 8.0 and later.</span></span>
    
    <span data-ttu-id="52ec2-114">Google Android 4.0 이상(Samsung KNOX Standard 4.0 이상 포함).</span><span class="sxs-lookup"><span data-stu-id="52ec2-114">Google Android 4.0 and later (including Samsung KNOX Standard 4.0 and higher).</span></span> <span data-ttu-id="52ec2-115">자세한 내용은 [Intune 지원 장치](https://go.microsoft.com/fwlink/p/?linkid=852307)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="52ec2-115">For more information, see [Intune supported devices](https://go.microsoft.com/fwlink/p/?linkid=852307).</span></span>
    
- <span data-ttu-id="52ec2-116">사용자 컴퓨터에 기존 Office 응용 프로그램이 있는 경우 [office 클라이언트 설치 준비](prepare-for-office-client-deployment.md) 를 통해 비즈니스에 대 한 Microsoft 365을 설정 하 여 사용자 컴퓨터에 office 2016을 설치 하기 전에 수행 해야 할 수 있는 단계를 파악 합니다.</span><span class="sxs-lookup"><span data-stu-id="52ec2-116">If you have existing Office applications on user computers, read [prepare for Office client installation](prepare-for-office-client-deployment.md) to understand steps you might need to take before you can set up Microsoft 365 for business to install Office 2016 on user computers.</span></span> 
