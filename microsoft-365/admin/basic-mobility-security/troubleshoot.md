---
title: 기본 이동성 및 보안 문제 해결
f1.keywords: NOCSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom: AdminSurgePortfolio
description: 다음 단계에 따라 기본 이동성 및 보안 문제를 추적합니다.
ms.openlocfilehash: b8df8c17f3a2fc5b7b6cce21769ca20742dbd397
ms.sourcegitcommit: 8849dd6f80217c29f427c7f008d918f30c792240
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/15/2021
ms.locfileid: "49876855"
---
# <a name="troubleshoot-basic-mobility-and-security"></a><span data-ttu-id="b168b-103">기본 이동성 및 보안 문제 해결</span><span class="sxs-lookup"><span data-stu-id="b168b-103">Troubleshoot Basic Mobility and Security</span></span>

<span data-ttu-id="b168b-104">기본 이동성 및 보안에서 장치를 등록하려고 할 때 문제가 발생하면 여기에 있는 단계를 시도하여 문제를 추적해 하세요.</span><span class="sxs-lookup"><span data-stu-id="b168b-104">If you're running into issues when you try to enroll a device in Basic Mobility and Security, try the steps here to track down the problem.</span></span> <span data-ttu-id="b168b-105">일반적인 단계로 문제가 해결되지 않는 경우 장치 유형에 대한 특정 단계가 있는 이후 섹션 중 하나를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="b168b-105">If the general steps don't fix the issue, see one of the later sections with specific steps for your device type.</span></span>

## <a name="steps-to-try-first"></a><span data-ttu-id="b168b-106">먼저 시도할 단계</span><span class="sxs-lookup"><span data-stu-id="b168b-106">Steps to try first</span></span>

<span data-ttu-id="b168b-107">시작을 위해 다음을 검사합니다.</span><span class="sxs-lookup"><span data-stu-id="b168b-107">To start, check the following:</span></span>

- <span data-ttu-id="b168b-108">디바이스가 Intune과 같은 다른 모바일 장치 관리 공급자에 아직 등록되어 있지 않은지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="b168b-108">Make sure that the device is not already enrolled with another mobile device management provider, such as Intune.</span></span>

- <span data-ttu-id="b168b-109">장치가 올바른 날짜 및 시간으로 설정되어 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="b168b-109">Make sure that the device is set to the correct date and time.</span></span>

- <span data-ttu-id="b168b-110">디바이스에서 다른 WIFI 또는 셀룰러 네트워크로 전환합니다.</span><span class="sxs-lookup"><span data-stu-id="b168b-110">Switch to a different WIFI or cellular network on the device.</span></span>

- <span data-ttu-id="b168b-111">Android 또는 iOS 장치의 경우 디바이스에서 Intune 회사 포털 앱을 제거하고 다시 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="b168b-111">For Android or iOS devices, uninstall and reinstall the Intune Company Portal app on the device.</span></span> 

## <a name="ios-phone-or-tablet"></a><span data-ttu-id="b168b-112">iOS 휴대폰 또는 태블릿</span><span class="sxs-lookup"><span data-stu-id="b168b-112">iOS phone or tablet</span></span>

- <span data-ttu-id="b168b-113">APNS 인증서를 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b168b-113">Make sure that you've set up an APNs certificate.</span></span> <span data-ttu-id="b168b-114">자세한 내용은 iOS 장치에 대한 APNS 인증서 [만들기를 참조하세요.](create-an-apns-certificate-for-ios-devices.md)</span><span class="sxs-lookup"><span data-stu-id="b168b-114">For more info, see [Create an APNs Certificate for iOS devices](create-an-apns-certificate-for-ios-devices.md).</span></span>

- <span data-ttu-id="b168b-115">설정 **일반**   >  **프로필(또는** 장치 관리)에서 관리 프로필이 아직 설치되어 있지   >  \*\*\*\* 않은지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="b168b-115">In **Settings** > **General** > **Profile (or Device Management)**, make sure that a Management Profile is not already installed.</span></span> <span data-ttu-id="b168b-116">있는 경우 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="b168b-116">If it is, remove it.</span></span>

- <span data-ttu-id="b168b-117">"장치를 등록하지 못했습니다."라는 오류 메시지가 표시될 경우 Microsoft 365에 로그인하고 장치에 로그인한 사용자에게 Exchange Online을 포함하는 라이선스가 할당되어 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="b168b-117">If you see the error message, "Device failed to enroll," sign in to Microsoft 365 and make sure that a license that includes Exchange Online has been assigned to the user who is signed in to the device.</span></span>

- <span data-ttu-id="b168b-118">"프로필을 설치하지 못했습니다."라는 오류 메시지가 표시된 경우 다음 중 하나를 시도해 봐야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b168b-118">If you see the error message, "Profile failed to install," try one of the following:</span></span>

    - <span data-ttu-id="b168b-119">Safari가 장치의 기본 브라우저이고 쿠키가 사용하지 않도록 설정되어 있지 않은지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="b168b-119">Make sure that Safari is the default browser on the device, and that cookies are not disabled.</span></span>

    - <span data-ttu-id="b168b-120">장치를 다시부팅한 다음 장치로 portal.manage.microsoft.com.</span><span class="sxs-lookup"><span data-stu-id="b168b-120">Reboot the device, and then navigate to portal.manage.microsoft.com.</span></span> <span data-ttu-id="b168b-121">Microsoft 365 사용자 ID 및 암호로 로그인하고 프로필을 수동으로 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="b168b-121">Sign in with your Microsoft 365 user ID and password, and attempt to install the profile manually.</span></span>

## <a name="windows-rt"></a><span data-ttu-id="b168b-122">Windows RT</span><span class="sxs-lookup"><span data-stu-id="b168b-122">Windows RT</span></span>

- <span data-ttu-id="b168b-123">기본 이동성 및 보안과 함께 작동하려면 Microsoft 365에서 도메인을 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b168b-123">Make sure that your domain is set up in Microsoft 365 to work with Basic Mobility and Security.</span></span> <span data-ttu-id="b168b-124">자세한 내용은 기본 이동성 및 [보안 설정을 참조하세요.](set-up.md)</span><span class="sxs-lookup"><span data-stu-id="b168b-124">For more info, see [Set up Basic Mobility and Security](set-up.md).</span></span>
    
- <span data-ttu-id="b168b-125">참가를 선택하는 대신 **사용자가 켜기**   기능을 선택해야 **합니다.**</span><span class="sxs-lookup"><span data-stu-id="b168b-125">Make sure that the user is choosing **Turn On** rather than choosing **Join**.</span></span>

## <a name="windows-10-pc"></a><span data-ttu-id="b168b-126">Windows 10 PC</span><span class="sxs-lookup"><span data-stu-id="b168b-126">Windows 10 PC</span></span>

- <span data-ttu-id="b168b-127">기본 이동성 및 보안과 함께 작동하려면 Microsoft 365에서 도메인을 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b168b-127">Make sure that your domain is set up in Microsoft 365 to work with Basic Mobility and Security.</span></span> <span data-ttu-id="b168b-128">자세한 내용은 기본 이동성 및 [보안 설정을 참조하세요.](set-up.md)</span><span class="sxs-lookup"><span data-stu-id="b168b-128">For more info, see [Set up Basic Mobility and Security](set-up.md).</span></span>
    
- <span data-ttu-id="b168b-129">Azure Active Directory Premium이 없는 경우 사용자가 Connect를 선택하는 대신 장치 관리에서 등록을 \*\*\*\*   선택해야 **합니다.**</span><span class="sxs-lookup"><span data-stu-id="b168b-129">Unless you have Azure Active Directory Premium, make sure that the user is choosing **Enroll in Device Management only** rather than choosing **Connect**.</span></span>

## <a name="android-phone-or-tablet"></a><span data-ttu-id="b168b-130">Android 휴대폰 또는 태블릿</span><span class="sxs-lookup"><span data-stu-id="b168b-130">Android phone or tablet</span></span>

- <span data-ttu-id="b168b-131">디바이스에서 Android 4.4 이상을 실행하고 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="b168b-131">Make sure the device is running Android 4.4 or later.</span></span>

- <span data-ttu-id="b168b-132">Chrome이 최신 버전이고 기본 브라우저로 설정되어 있는지 확인</span><span class="sxs-lookup"><span data-stu-id="b168b-132">Make sure that Chrome is up to date and is set as the default browser.</span></span>

- <span data-ttu-id="b168b-133">"이 장치를 등록할 수 없습니다."라는 오류 메시지가 표시될 경우 Microsoft 365에 로그인하고 장치에 로그인한 사용자에게 Exchange Online을 포함하는 라이선스가 할당되어 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="b168b-133">If you see the error message, "We couldn't enroll this device," sign in to Microsoft 365 and make sure that a license that includes Exchange Online has been assigned to the user who is signed in to the device.</span></span>

- <span data-ttu-id="b168b-134">디바이스의 알림 영역을 확인하여 필요한 최종 사용자 작업이 보류 중인지 확인하고, 보류 중인 경우 작업을 완료합니다.</span><span class="sxs-lookup"><span data-stu-id="b168b-134">Check the Notification Area on the device to see if any required end-user actions are pending, and if they are, complete the actions.</span></span>