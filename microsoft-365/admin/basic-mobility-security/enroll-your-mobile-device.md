---
title: 기본 이동성 및 보안을 사용하여 모바일 장치 등록
f1.keywords:
- NOCSH
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
ms.custom:
- AdminSurgePortfolio
search.appverid:
- MET150
description: 디바이스에서 Microsoft 365 서비스를 사용하려면 먼저 Microsoft 365용 Basic Mobility and Security에 등록해야 할 수 있습니다.
ms.openlocfilehash: dc5a43b12fce50c9146200a4559fe9b7e6824b18
ms.sourcegitcommit: 8849dd6f80217c29f427c7f008d918f30c792240
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/15/2021
ms.locfileid: "49877059"
---
# <a name="enroll-your-mobile-device-using-basic-mobility-and-security"></a><span data-ttu-id="0bf71-103">기본 이동성 및 보안을 사용하여 모바일 장치 등록</span><span class="sxs-lookup"><span data-stu-id="0bf71-103">Enroll your mobile device using Basic Mobility and Security</span></span>

<span data-ttu-id="0bf71-104">업무에 휴대폰, 태블릿 및 기타 모바일 장치를 사용하면 사무실을 비우는 동안 비즈니스 프로젝트에 대한 정보를 계속 사용하고 업무를 진행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0bf71-104">Using your phone, tablet, and other mobile devices for work is a great way to stay informed and work on business projects while you’re away from the office.</span></span> <span data-ttu-id="0bf71-105">디바이스에서 Microsoft 365 서비스를 사용하려면 먼저 Microsoft Intune 회사 포털을 사용하여 Microsoft 365용 Basic Mobility and Security에 등록해야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0bf71-105">Before you can use Microsoft 365 services with your device, you might need to first enroll it in Basic Mobility and Security for Microsoft 365 using Microsoft Intune Company Portal.</span></span>

<span data-ttu-id="0bf71-106">조직은 직원이 모바일 장치를 사용하여 회사 전자 메일, 일정 및 문서에 안전하게 액세스할 수 있도록 기본 이동성 및 보안을 선택하고 비즈니스에서 중요한 데이터를 보호하고 규정 준수 요구 사항을 충족합니다.</span><span class="sxs-lookup"><span data-stu-id="0bf71-106">Organizations choose Basic Mobility and Security so that employees can use their mobile devices to securely access work email, calendars, and documents while the business secures important data and meets their compliance requirements.</span></span><span data-ttu-id="0bf71-107">자세한 내용은 [Microsoft 365의 기본 이동성 및 보안 개요를 참조하세요.](overview.md)</span><span class="sxs-lookup"><span data-stu-id="0bf71-107"> To learn more, see [Overview of Basic Mobility and Security for Microsoft 365](overview.md).</span></span> <span data-ttu-id="0bf71-108">자세한 내용은 내 장치를 등록할 때 조직에서 [볼 수 있는 정보를 참조하세요.](https://docs.microsoft.com/intune-user-help/what-info-can-your-company-see-when-you-enroll-your-device-in-intune)</span><span class="sxs-lookup"><span data-stu-id="0bf71-108">For more info, see [What information can my organization see when I enroll my device?](https://docs.microsoft.com/intune-user-help/what-info-can-your-company-see-when-you-enroll-your-device-in-intune).</span></span>

>[!IMPORTANT] 
><span data-ttu-id="0bf71-109">Microsoft 365용 Basic Mobility and Security에 장치를 등록할 때 작업 조직에서 디바이스를 지우는 옵션을 허용하는 것과 함께 암호를 설정해야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0bf71-109">When you enroll your device in Basic Mobility and Security for Microsoft 365, you might be required to set up a password, together with allowing the option for your work organization to wipe the device.</span></span> <span data-ttu-id="0bf71-110">Microsoft 365 관리 센터에서 장치 지우기를 수행할 수 있습니다. 예를 들어 암호를 너무 많이 입력하거나 사용 약관이 손상된 경우 장치에서 모든 데이터를 제거할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0bf71-110">A device wipe can be performed from the Microsoft 365 admin center, for example, to remove all data from the device if the password is entered incorrectly too many times or if usage terms are broken.</span></span>

## <a name="supported-devices"></a><span data-ttu-id="0bf71-111">지원되는 장치</span><span class="sxs-lookup"><span data-stu-id="0bf71-111">Supported devices</span></span>

<span data-ttu-id="0bf71-112">Intune 서비스에서 호스팅하는 Microsoft 365의 기본 이동성 및 보안은 대부분의 모바일 장치에서만 작동합니다.</span><span class="sxs-lookup"><span data-stu-id="0bf71-112">Basic Mobility and Security for Microsoft 365 hosted by the Intune service works with most, but not all, mobile devices.</span></span> <span data-ttu-id="0bf71-113">기본 이동성 및 보안에서는 다음이 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="0bf71-113">The following are supported with Basic Mobility and Security:</span></span>

- <span data-ttu-id="0bf71-114">iOS 10.0 이상</span><span class="sxs-lookup"><span data-stu-id="0bf71-114">iOS 10.0 or later</span></span>

- <span data-ttu-id="0bf71-115">Android 4.4 이상</span><span class="sxs-lookup"><span data-stu-id="0bf71-115">Android 4.4 or later</span></span>

- <span data-ttu-id="0bf71-116">Windows 8.1 및 Windows 10(휴대폰 및 PC)</span><span class="sxs-lookup"><span data-stu-id="0bf71-116">Windows 8.1 and Windows 10 (Phone and PC)</span></span>

<span data-ttu-id="0bf71-117">장치가 위에 나열되지 않은 경우 기본 이동성 및 보안과 함께 장치를 사용하려면 직장 또는 학교 관리자에게 문의하세요.</span><span class="sxs-lookup"><span data-stu-id="0bf71-117">If your device is not listed above, and you need to use it with Basic Mobility and Security, contact your work or school administrator.</span></span>

>[!TIP]
><span data-ttu-id="0bf71-118">장치를 등록하는 데 문제가 있는 경우 기본 이동성 및 보안 문제 [해결을 참조하세요.](/basic-mobility-security/troubleshoot.md)</span><span class="sxs-lookup"><span data-stu-id="0bf71-118">If you're having trouble enrolling your device, see [Troubleshoot Basic Mobility and Security](/basic-mobility-security/troubleshoot.md).</span></span>

## <a name="set-up-your-mobile-device-with-intune-and-basic-mobility-and-security"></a><span data-ttu-id="0bf71-119">Intune 및 기본 이동성 및 보안으로 모바일 장치 설정</span><span class="sxs-lookup"><span data-stu-id="0bf71-119">Set up your mobile device with Intune and Basic Mobility and Security</span></span>

<span data-ttu-id="0bf71-120">Intune 회사 포털을 사용하면 Microsoft 365 및 기본 이동성 및 보안에서 장치를 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0bf71-120">The Intune Company Portal enables a device to be managed by Microsoft 365 and Basic Mobility and Security.</span></span>

### <a name="iphone-or-ipad"></a><span data-ttu-id="0bf71-121">iPhone 또는 iPad</span><span class="sxs-lookup"><span data-stu-id="0bf71-121">iPhone or iPad</span></span>

>[!TIP]
><span data-ttu-id="0bf71-122">이 단계를 완료해야 전자 메일을 보내고 받을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0bf71-122">You won’t be able to send and receive email until you complete this step.</span></span>

<span data-ttu-id="0bf71-123">Apple 앱 스토어로 이동하여 Intune 회사 포털을 다운로드하여 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="0bf71-123">Go to the Apple App Store, and download and install Intune Company Portal.</span></span>

<span data-ttu-id="0bf71-124">회사 포털을 사용하여 iOS 휴대폰 또는 태블릿을 Office 365에 연결하고 구성하려면 회사 리소스에 대한 iOS 장치 액세스 [설정을 참조하세요.](https://go.microsoft.com/fwlink/?linkid=875316)</span><span class="sxs-lookup"><span data-stu-id="0bf71-124">To connect and configure your iOS phone or tablet with the Company portal to Office 365, see [Set up iOS device access to your company resources](https://go.microsoft.com/fwlink/?linkid=875316).</span></span>

### <a name="android-phone-or-tablet"></a><span data-ttu-id="0bf71-125">Android 휴대폰 또는 태블릿</span><span class="sxs-lookup"><span data-stu-id="0bf71-125">Android phone or tablet</span></span>

>[!TIP]
><span data-ttu-id="0bf71-126">이 단계를 완료해야 전자 메일을 보내고 받을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0bf71-126">You won’t be able to send and receive email until you complete this step.</span></span>

<span data-ttu-id="0bf71-127">Google Play 스토어로 이동하여 Intune 회사 포털을 다운로드하여 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="0bf71-127">Go to the Google Play store, and download and install Intune Company Portal.</span></span>

<span data-ttu-id="0bf71-128">회사 포털을 사용하여 Android 휴대폰 또는 태블릿을 Microsoft 365에 연결하고 구성하려면 회사 포털을 사용하여 장치 [등록을 참조하세요.](https://go.microsoft.com/fwlink/?linkid=875317)</span><span class="sxs-lookup"><span data-stu-id="0bf71-128">To connect and configure your Android phone or tablet with the Company portal to Microsoft 365, see [Enroll your device with Company Portal](https://go.microsoft.com/fwlink/?linkid=875317).</span></span>

### <a name="windows-81-and-windows-10"></a><span data-ttu-id="0bf71-129">Windows 8.1 및 Windows 10</span><span class="sxs-lookup"><span data-stu-id="0bf71-129">Windows 8.1 and Windows 10</span></span>

<span data-ttu-id="0bf71-130">Microsoft Store로 이동하여 Intune 회사 포털을 다운로드하여 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="0bf71-130">Go to the Microsoft Store, and download and install Intune Company Portal</span></span>

<span data-ttu-id="0bf71-131">회사 포털을 사용하여 Windows Phone 또는 PC를 Microsoft 365에 연결하고 구성하려면 Intune 회사 포털에서 Windows 장치 [등록을 참조하세요.](https://docs.microsoft.com/intune-user-help/windows-enrollment-company-portal)</span><span class="sxs-lookup"><span data-stu-id="0bf71-131">To connect and configure your Windows phone or PC with the Company portal to Microsoft 365, see [Windows device enrollment in Intune Company Portal](https://docs.microsoft.com/intune-user-help/windows-enrollment-company-portal).</span></span>

## <a name="whats-next"></a><span data-ttu-id="0bf71-132">다음 작업</span><span class="sxs-lookup"><span data-stu-id="0bf71-132">What's next?</span></span>

<span data-ttu-id="0bf71-133">장치가 기본 이동성 및 보안에 등록된 후 장치에서 Office 앱을 사용하여 전자 메일, 일정, 연락처 및 문서로 작업할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0bf71-133">After your device is enrolled in Basic Mobility and Security, you can start using Office apps on your device to work with email, calendar, contacts, and documents.</span></span>
