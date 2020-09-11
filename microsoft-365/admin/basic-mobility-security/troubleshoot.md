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
description: 기본 이동성 및 보안 문제를 추적 하려면 다음 단계를 수행 하세요.
ms.openlocfilehash: 43e7533e598f769dd5f2bcae28c4252f96a9be76
ms.sourcegitcommit: aeb94601a81db3ead8610c2f36cff30eb9fe10e7
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/10/2020
ms.locfileid: "47430251"
---
# <a name="troubleshoot-basic-mobility-and-security"></a><span data-ttu-id="49a30-103">기본 이동성 및 보안 문제 해결</span><span class="sxs-lookup"><span data-stu-id="49a30-103">Troubleshoot Basic Mobility and Security</span></span>

<span data-ttu-id="49a30-104">기본 Mobility and Security에서 장치를 등록 하려고 할 때 문제가 발생 하는 경우 다음 단계를 수행 하 여 문제를 추적 해 보세요.</span><span class="sxs-lookup"><span data-stu-id="49a30-104">If you're running into issues when you try to enroll a device in Basic Mobility and Security, try the steps here to track down the problem.</span></span> <span data-ttu-id="49a30-105">일반적인 단계를 수행 해도 문제가 해결 되지 않는 경우에는 해당 디바이스 유형에 대 한 특정 단계를 포함 하는 이후 섹션 중 하나를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="49a30-105">If the general steps don't fix the issue, see one of the later sections with specific steps for your device type.</span></span>

## <a name="steps-to-try-first"></a><span data-ttu-id="49a30-106">먼저 시도해 야 할 단계</span><span class="sxs-lookup"><span data-stu-id="49a30-106">Steps to try first</span></span>

<span data-ttu-id="49a30-107">시작 하려면 다음을 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="49a30-107">To start, check the following:</span></span>

- <span data-ttu-id="49a30-108">장치가 Intune과 같은 다른 모바일 장치 관리 공급자에 등록 되어 있지 않은지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="49a30-108">Make sure that the device is not already enrolled with another mobile device management provider, such as Intune.</span></span>
    
- <span data-ttu-id="49a30-109">장치가 올바른 날짜 및 시간으로 설정 되어 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="49a30-109">Make sure that the device is set to the correct date and time.</span></span>
    
- <span data-ttu-id="49a30-110">장치에서 다른 WIFI 또는 셀룰러 네트워크로 전환 합니다.</span><span class="sxs-lookup"><span data-stu-id="49a30-110">Switch to a different WIFI or cellular network on the device.</span></span>
    
- <span data-ttu-id="49a30-111">Android 또는 iOS 장치의 경우 장치에서 Intune 회사 포털 앱을 제거 하 고 다시 설치 합니다.</span><span class="sxs-lookup"><span data-stu-id="49a30-111">For Android or iOS devices, uninstall and reinstall the Intune Company Portal app on the device.</span></span> 

## <a name="ios-phone-or-tablet"></a><span data-ttu-id="49a30-112">iOS 전화 또는 태블릿</span><span class="sxs-lookup"><span data-stu-id="49a30-112">iOS phone or tablet</span></span>

- <span data-ttu-id="49a30-113">APNs 인증서를 설정 했는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="49a30-113">Make sure that you've set up an APNs certificate.</span></span> <span data-ttu-id="49a30-114">자세한 내용은 [iOS 장치용 APNs 인증서 만들기](create-an-apns-certificate-for-ios-devices.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="49a30-114">For more info, see [Create an APNs Certificate for iOS devices](create-an-apns-certificate-for-ios-devices.md).</span></span>
    
- <span data-ttu-id="49a30-115"> *\*설정**   >  *\*일반**   >  *\*프로필 (또는 장치 관리)** 에서 관리 프로필이 이미 설치 되어 있지 않은지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="49a30-115">In **Settings** > **General** > **Profile (or Device Management)**, make sure that a Management Profile is not already installed.</span></span> <span data-ttu-id="49a30-116">해당 하는 경우 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="49a30-116">If it is, remove it.</span></span>
    
- <span data-ttu-id="49a30-117">"장치를 등록 하지 못했습니다." 라는 오류 메시지가 표시 되 면 Microsoft 365에 로그인 하 여 Exchange Online이 포함 된 라이선스가 장치에 로그인 한 사용자에 게 할당 되었는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="49a30-117">If you see the error message, "Device failed to enroll," sign in to Microsoft 365 and make sure that a license that includes Exchange Online has been assigned to the user who is signed in to the device.</span></span>
    
- <span data-ttu-id="49a30-118">"프로필을 설치 하지 못했습니다." 라는 오류 메시지가 표시 되 면 다음 중 하나를 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="49a30-118">If you see the error message, "Profile failed to install," try one of the following:</span></span>
    
    - <span data-ttu-id="49a30-119">Safari가 장치에서 기본 브라우저이 고 해당 쿠키를 사용 하지 않도록 설정 되어 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="49a30-119">Make sure that Safari is the default browser on the device, and that cookies are not disabled.</span></span>
    
    - <span data-ttu-id="49a30-120">장치를 다시 부팅 한 다음 portal.manage.microsoft.com로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="49a30-120">Reboot the device, and then navigate to portal.manage.microsoft.com.</span></span> <span data-ttu-id="49a30-121">Microsoft 365 사용자 ID 및 암호를 사용 하 여 로그인 하 고 프로필을 수동으로 설치 해 봅니다.</span><span class="sxs-lookup"><span data-stu-id="49a30-121">Sign in with your Microsoft 365 user ID and password, and attempt to install the profile manually.</span></span>    

## <a name="windows-rt"></a><span data-ttu-id="49a30-122">Windows RT</span><span class="sxs-lookup"><span data-stu-id="49a30-122">Windows RT</span></span>

- <span data-ttu-id="49a30-123">기본 이동성 및 보안을 사용 하려면 도메인이 Microsoft 365에 설정 되어 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="49a30-123">Make sure that your domain is set up in Microsoft 365 to work with Basic Mobility and Security.</span></span> <span data-ttu-id="49a30-124">자세한 내용은 [기본 이동성 및 보안 설정을](set-up.md)참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="49a30-124">For more info, see [Set up Basic Mobility and Security](set-up.md).</span></span>
    
- <span data-ttu-id="49a30-125">연결을 선택 하는 대신 사용자가 **설정을**선택 하 고 있는지 확인   합니다. **Join**</span><span class="sxs-lookup"><span data-stu-id="49a30-125">Make sure that the user is choosing **Turn On** rather than choosing **Join**.</span></span>    

## <a name="windows-10-pc"></a><span data-ttu-id="49a30-126">Windows 10 PC</span><span class="sxs-lookup"><span data-stu-id="49a30-126">Windows 10 PC</span></span>

- <span data-ttu-id="49a30-127">기본 이동성 및 보안을 사용 하려면 도메인이 Microsoft 365에 설정 되어 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="49a30-127">Make sure that your domain is set up in Microsoft 365 to work with Basic Mobility and Security.</span></span> <span data-ttu-id="49a30-128">자세한 내용은 [기본 이동성 및 보안 설정을](set-up.md)참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="49a30-128">For more info, see [Set up Basic Mobility and Security](set-up.md).</span></span>
    
- <span data-ttu-id="49a30-129">Azure Active Directory Premium이 없는 경우에는 사용자가 연결을 선택 하는 대신 **장치 관리에서 등록**을 선택 하 고 있는지 확인 합니다   . **Connect**</span><span class="sxs-lookup"><span data-stu-id="49a30-129">Unless you have Azure Active Directory Premium, make sure that the user is choosing **Enroll in Device Management only** rather than choosing **Connect**.</span></span>

## <a name="android-phone-or-tablet"></a><span data-ttu-id="49a30-130">Android 휴대폰 또는 태블릿</span><span class="sxs-lookup"><span data-stu-id="49a30-130">Android phone or tablet</span></span>

- <span data-ttu-id="49a30-131">장치가 Android 4.4 이상 버전을 실행 하 고 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="49a30-131">Make sure the device is running Android 4.4 or later.</span></span>
    
- <span data-ttu-id="49a30-132">Chrome이 최신 상태이 고 기본 브라우저로 설정 되어 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="49a30-132">Make sure that Chrome is up to date and is set as the default browser.</span></span>
    
- <span data-ttu-id="49a30-133">"이 장치를 등록할 수 없습니다." 라는 오류 메시지가 표시 되 면 Microsoft 365에 로그인 하 여 장치에 로그인 한 사용자에 게 Exchange Online을 포함 하는 라이선스가 할당 되었는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="49a30-133">If you see the error message, "We couldn't enroll this device," sign in to Microsoft 365 and make sure that a license that includes Exchange Online has been assigned to the user who is signed in to the device.</span></span>
    
- <span data-ttu-id="49a30-134">장치의 알림 영역에서 필요한 최종 사용자 작업이 보류 중인지 확인 하 고, 있는 경우 해당 작업을 완료 합니다.</span><span class="sxs-lookup"><span data-stu-id="49a30-134">Check the Notification Area on the device to see if any required end-user actions are pending, and if they are, complete the actions.</span></span>