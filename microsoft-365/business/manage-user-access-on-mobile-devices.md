---
title: 사용자가 모바일 장치에서 Office 문서에 액세스하는 방법 관리
f1.keywords:
- NOCSH
ms.author: efrene
author: efrene
manager: scotv
audience: Admin
ms.topic: conceptual
f1_keywords:
- O365E_BCSSetup4OfficeMobile
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- M365-identity-device-management
ms.custom:
- Adm_O365
- Core_O365Admin_Migration
- MiniMaven
- MSB365
- seo-marvel-mar
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: aa31319c-9196-48c9-a90b-4057e0494c7a
description: 사용자가 모바일 장치에서 Office 앱 및 작업 파일에 액세스하는 방법을 관리할 수 있는 보호 정책에 대해 자세히 알아보습니다.
ms.openlocfilehash: a48aa241c9e70cf087da3f1701e859dae7238024
ms.sourcegitcommit: 53acc851abf68e2272e75df0856c0e16b0c7e48d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/02/2021
ms.locfileid: "51578390"
---
# <a name="manage-how-users-access-office-documents-on-mobile-devices"></a><span data-ttu-id="c4828-103">사용자가 모바일 장치에서 Office 문서에 액세스하는 방법 관리</span><span class="sxs-lookup"><span data-stu-id="c4828-103">Manage how users access Office documents on mobile devices</span></span>

<span data-ttu-id="c4828-104">이 문서는 Microsoft 365 Business Premium에 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="c4828-104">This article applies to Microsoft 365 Business Premium.</span></span>

<span data-ttu-id="c4828-105">사용자가 모바일 장치에서 Office 파일을 액세스하는 방법을 제어하는 정책 설정은 기본적으로 **꺼짐** 으로 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c4828-105">Policy settings that control how users access Office files from their mobile devices are **Off** by default.</span></span> <span data-ttu-id="c4828-106">설치 중에 기본값을 수락하여 모든 사용자에게 적용되는 Android, iOS 및 Windows 10용 응용 프로그램 정책을 만드는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="c4828-106">We recommend that you accept the default values during setup to create application policies for Android, iOS, and Windows 10 that apply to all users.</span></span> <span data-ttu-id="c4828-107">설치가 완료되면 추가로 정책을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c4828-107">You can create more policies after setup completes.</span></span> 
  
## <a name="settings-that-control-how-users-access-office-files-on-mobile-devices"></a><span data-ttu-id="c4828-108">사용자가 모바일 장치에서 Office 파일을 액세스하는 방법을 제어하는 설정</span><span class="sxs-lookup"><span data-stu-id="c4828-108">Settings that control how users access Office files on mobile devices</span></span>

<span data-ttu-id="c4828-109">사용자가 Office 작업 파일을 액세스하는 방법을 관리할 때 다음과 같은 설정을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c4828-109">The following settings are available to manage how users access Office work files:</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="c4828-110">설정</span><span class="sxs-lookup"><span data-stu-id="c4828-110">Setting</span></span>  <br/> |<span data-ttu-id="c4828-111">설명</span><span class="sxs-lookup"><span data-stu-id="c4828-111">Description</span></span>  <br/> |
|<span data-ttu-id="c4828-112">Office 앱 액세스에 PIN 또는 지문 필요</span><span class="sxs-lookup"><span data-stu-id="c4828-112">Require a PIN or fingerprint to access Office apps</span></span>  <br/> |<span data-ttu-id="c4828-113">이 설정이 **으로** 설정되는 경우 사용자는 자신의 사용자 이름 및 암호와 함께 다른 인증 형식을 제공해야 모바일 장치에서 Office 앱을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c4828-113">If this setting is **On**, users must provide another form of authentication, in addition to their username and password, before they can use Office apps on their mobile device.</span></span>  <br/> |
|<span data-ttu-id="c4828-114">PIN을 재설정할 로그인 실패 횟수</span><span class="sxs-lookup"><span data-stu-id="c4828-114">Reset PIN when login fails this many times</span></span>  <br/> |<span data-ttu-id="c4828-115">권한 없는 사용자가 PIN을 임의로 추측하는 것을 방지하기 위해 사용자가 지정한 횟수만큼 잘못된 PIN이 입력되면 PIN을 재설정합니다.</span><span class="sxs-lookup"><span data-stu-id="c4828-115">To prevent an unauthorized user from randomly guessing a PIN, the PIN will reset after the number of wrong entries that you specify.</span></span>  <br/> |
|<span data-ttu-id="c4828-116">Office 앱이 이 시간 동안 유휴 상태인 경우 사용자 다시 로그인 필요</span><span class="sxs-lookup"><span data-stu-id="c4828-116">Require users to sign in again after Office apps have been idle for</span></span>  <br/> |<span data-ttu-id="c4828-117">이 설정은 다시 로그인하라는 메시지가 표시되기 전에 사용자가 유휴일 수 있는 기간을 결정하는 설정입니다.</span><span class="sxs-lookup"><span data-stu-id="c4828-117">This setting determines how long a user can be idle before they're prompted to sign in again.</span></span>  <br/> |
|<span data-ttu-id="c4828-118">탈옥 또는 루팅된 장치에서의 작업 파일 액세스 거부</span><span class="sxs-lookup"><span data-stu-id="c4828-118">Deny access to work files on jailbroken or rooted devices</span></span>  <br/> |<span data-ttu-id="c4828-119">기술을 잘 아는 사용자들은 장치를 탈옥 또는 루팅하여 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c4828-119">Clever users may have a device that is jailbroken or rooted.</span></span> <span data-ttu-id="c4828-120">즉, 사용자가 운영 체제를 수정할 수 있습니다. 이 경우 장치가 맬웨어에 더 쉽게 인식될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c4828-120">This means that the user can modify the operating system, which can make the device more susceptible to malware.</span></span> <span data-ttu-id="c4828-121">이 설정이 **켜기** 로 되어 있을 경우 이러한 장치는 차단됩니다.</span><span class="sxs-lookup"><span data-stu-id="c4828-121">These devices are blocked when this setting is **On**.</span></span>  <br/> |
|<span data-ttu-id="c4828-122">사용자가 Office 앱에서 개인 앱으로 콘텐츠를 복사하도록 허용하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c4828-122">Don't allow users to copy content from Office apps into personal apps</span></span>  <br/> |<span data-ttu-id="c4828-123">설정이 **으로 설정될** 때 사용자는 작업 파일의 정보를 개인 파일에 복사할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="c4828-123">When the setting is **On**, the user can't copy information in a work file to a personal file.</span></span> <span data-ttu-id="c4828-124">설정이 **꺼진 경우** 사용자는 작업 파일의 정보를 개인 앱 또는 개인 계정으로 복사할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c4828-124">If the setting is **Off**, the user can copy information from a work file to a personal app or personal account.</span></span>  <br/> |
   

