---
title: 장치 및 앱 관리 간의 차이점
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
ms.topic: conceptual
f1_keywords:
- O365E_understand_devices
- BCS365_understand_devices
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
- MOE150
description: 모바일 장치 관리 및 모바일 앱 관리와 MDM 및 MAM 간의 차이점을 알아봅니다.
ms.openlocfilehash: 590dc9522be7adc9c24c61091928133fb13d9027
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42057139"
---
# <a name="difference-between-mdm-and-mam"></a><span data-ttu-id="24e34-103">MDM과 MAM의 차이점</span><span class="sxs-lookup"><span data-stu-id="24e34-103">Difference between MDM and MAM</span></span>

<span data-ttu-id="24e34-104">Microsoft 365 Business에서는 비즈니스 데이터를 보호 하는 다양 한 방법을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="24e34-104">Microsoft 365 Business offers a number of ways for you to protect your business data.</span></span> <span data-ttu-id="24e34-105">[Microsoft 365 Business 개요](../microsoft-365-business-overview.md) 에서는 자동으로 설정 되는 다양 한 보호에 대 한 자세한 내용과 비즈니스 보호를 위해 직접 설정할 수 있는 방법을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="24e34-105">See [Overview of Microsoft 365 Business](../microsoft-365-business-overview.md) for more about the various protections that are automatically set up, and what you can set up yourself to further protect your business.</span></span> <span data-ttu-id="24e34-106">또한 Windows 10 장치 및 모바일 장치에서 데이터를 보호 하는 정책을 설정할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="24e34-106">You can also set up policies that protect your Windows 10 devices and the data in your mobile devices.</span></span>
<span data-ttu-id="24e34-107">[Windows 10 장치에 대 한 응용 프로그램 보호 설정을 설정](../protection-settings-for-windows-10-devices.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="24e34-107">[Set application protection settings for Windows 10 devices](../protection-settings-for-windows-10-devices.md).</span></span>

## <a name="mobile-device-management-or-mdm"></a><span data-ttu-id="24e34-108">모바일 장치 관리 또는 MDM</span><span class="sxs-lookup"><span data-stu-id="24e34-108">Mobile device management or MDM</span></span>

<span data-ttu-id="24e34-109">Microsoft 365 Business에서는 Windows 10 장치에서 데이터를 보호 하는 정책을 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="24e34-109">Microsoft 365 Business lets you set up policies that protect data on your Windows 10 devices.</span></span> <span data-ttu-id="24e34-110">장치가 모바일 장치 관리 아래에 있는 경우 전체 장치를 제어 하 고 해당 디바이스에서 데이터를 지울 수 있으며 공장 설정으로 다시 설정할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="24e34-110">When a device is under mobile device management, you control the entire device, and can wipe data from it, and also reset it to factory settings.</span></span> <span data-ttu-id="24e34-111">자세한 내용은 [Windows 10 pc에 대 한 장치 보호 설정 설정](../protection-settings-for-windows-10-pcs.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="24e34-111">For more information, see [Set device protection settings for Windows 10 PCs](../protection-settings-for-windows-10-pcs.md).</span></span>

## <a name="mobile-application-management-or-mam"></a><span data-ttu-id="24e34-112">모바일 응용 프로그램 관리 또는 MAM</span><span class="sxs-lookup"><span data-stu-id="24e34-112">Mobile application management or MAM</span></span>

<span data-ttu-id="24e34-113">모바일 응용 프로그램 관리에서는 Iphone 및 Androids와 같은 사용자의 개인 장치에서 비즈니스 데이터를 제어 하 고 개인 Win 10 컴퓨터를 제어할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="24e34-113">Mobile application management lets you control your business data in your users' personal devices, such as iPhones and Androids, and their personal Win 10 computers.</span></span> <span data-ttu-id="24e34-114">응용 프로그램 관리 정책을 사용 하 여 사용자가 Office 앱에서 개인 앱으로 비즈니스 데이터를 복사 하지 못하도록 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="24e34-114">You can use application management policies to prevent your users from copying business data from Office apps to their personal apps.</span></span> <span data-ttu-id="24e34-115">또한 개인 장치에서 Office 앱에 있는 모든 데이터를 제거할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="24e34-115">You can also remove all data from the Office apps on their personal devices.</span></span> <span data-ttu-id="24e34-116">자세한 내용은 [Android 또는 iOS 장치에 대 한 앱 보호 설정 설정](../app-protection-settings-for-android-and-ios.md) 및 [Windows 10 장치에 대 한 응용 프로그램 보호](../protection-settings-for-windows-10-devices.md)설정 설정을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="24e34-116">For more information, see [Set app protection settings for Android or iOS devices](../app-protection-settings-for-android-and-ios.md) and [Set application protection settings for Windows 10 devices](../protection-settings-for-windows-10-devices.md).</span></span>
