---
title: 기본 이동성 및 보안을 사용 하 여 모바일 장치 등록
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
description: 장치에서 Microsoft 365 서비스를 사용 하려면 먼저 기본 Mobility and Security for Microsoft 365에 등록 해야 할 수 있습니다.
ms.openlocfilehash: e31054621ba44a4d5f08de9b366fa0978b738cd9
ms.sourcegitcommit: aeb94601a81db3ead8610c2f36cff30eb9fe10e7
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/10/2020
ms.locfileid: "47430261"
---
# <a name="enroll-your-mobile-device-using-basic-mobility-and-security"></a><span data-ttu-id="bdafb-103">기본 이동성 및 보안을 사용 하 여 모바일 장치 등록</span><span class="sxs-lookup"><span data-stu-id="bdafb-103">Enroll your mobile device using Basic Mobility and Security</span></span>

<span data-ttu-id="bdafb-104">직장에서 휴대폰, 태블릿 및 기타 모바일 장치를 사용 하는 것은 사무실 밖에 서 비즈니스 프로젝트에 대 한 정보를 유지 하 고 작업 하는 좋은 방법입니다.</span><span class="sxs-lookup"><span data-stu-id="bdafb-104">Using your phone, tablet, and other mobile devices for work is a great way to stay informed and work on business projects while you’re away from the office.</span></span> <span data-ttu-id="bdafb-105">장치와 함께 Microsoft 365 서비스를 사용 하려면 먼저 microsoft Intune 회사 포털을 사용 하 여 microsoft 365 용 기본 이동성 및 보안에 등록 해야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bdafb-105">Before you can use Microsoft 365 services with your device, you might need to first enroll it in Basic Mobility and Security for Microsoft 365 using Microsoft Intune Company Portal.</span></span>

<span data-ttu-id="bdafb-106">조직은 회사에서 중요 한 데이터를 보호 하 고 준수 요구 사항을 충족 하면서 모바일 장치를 사용 하 여 회사의 전자 메일, 일정 및 문서에 안전 하 게 액세스할 수 있도록 기본 이동성 및 보안을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="bdafb-106">Organizations choose Basic Mobility and Security so that employees can use their mobile devices to securely access work email, calendars, and documents while the business secures important data and meets their compliance requirements.</span></span><span data-ttu-id="bdafb-107">자세한 내용은 [Microsoft 365의 기본 모바일 및 보안 개요](overview.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="bdafb-107"> To learn more, see [Overview of Basic Mobility and Security for Microsoft 365](overview.md).</span></span> <span data-ttu-id="bdafb-108">자세한 내용은 [내 장치를 등록할 때 조직에서 어떤 정보를 확인할 수 있나요?](https://docs.microsoft.com/intune-user-help/what-info-can-your-company-see-when-you-enroll-your-device-in-intune)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="bdafb-108">For more info, see [What information can my organization see when I enroll my device?](https://docs.microsoft.com/intune-user-help/what-info-can-your-company-see-when-you-enroll-your-device-in-intune).</span></span>

>[!IMPORTANT] 
><span data-ttu-id="bdafb-109">Microsoft 365의 기본 Mobility 및 Security에서 디바이스를 등록할 때 작업 조직에 대 한 옵션을 사용 하 여 장치를 초기화 하는 데 필요한 암호를 설정 해야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bdafb-109">When you enroll your device in Basic Mobility and Security for Microsoft 365, you might be required to set up a password, together with allowing the option for your work organization to wipe the device.</span></span> <span data-ttu-id="bdafb-110">예를 들어 Microsoft 365 관리 센터에서 장치 지우기를 수행 하 여 암호를 너무 여러 번 입력 하거나 사용 조건이 끊어진 경우 장치에서 모든 데이터를 제거할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bdafb-110">A device wipe can be performed from the Microsoft 365 admin center, for example, to remove all data from the device if the password is entered incorrectly too many times or if usage terms are broken.</span></span>

## <a name="supported-devices"></a><span data-ttu-id="bdafb-111">지원되는 장치</span><span class="sxs-lookup"><span data-stu-id="bdafb-111">Supported devices</span></span>

<span data-ttu-id="bdafb-112">Intune 서비스에 의해 호스트 되는 Microsoft 365 용 기본 이동성 및 보안은 대부분의 모바일 장치에서 작동 합니다.</span><span class="sxs-lookup"><span data-stu-id="bdafb-112">Basic Mobility and Security for Microsoft 365 hosted by the Intune service works with most, but not all, mobile devices.</span></span> <span data-ttu-id="bdafb-113">기본 이동성 및 보안에서는 다음과 같은 기능을 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="bdafb-113">The following are supported with Basic Mobility and Security:</span></span>

- <span data-ttu-id="bdafb-114">iOS 10.0 이상</span><span class="sxs-lookup"><span data-stu-id="bdafb-114">iOS 10.0 or later</span></span>
    
- <span data-ttu-id="bdafb-115">Android 4.4 이상</span><span class="sxs-lookup"><span data-stu-id="bdafb-115">Android 4.4 or later</span></span>
    
- <span data-ttu-id="bdafb-116">Windows 8.1 및 Windows 10 (전화 및 PC)</span><span class="sxs-lookup"><span data-stu-id="bdafb-116">Windows 8.1 and Windows 10 (Phone and PC)</span></span>
    
<span data-ttu-id="bdafb-117">장치가 위에 나열 되지 않고 기본 이동성 및 보안을 사용 해야 하는 경우 회사 또는 학교 관리자에 게 문의 하세요.</span><span class="sxs-lookup"><span data-stu-id="bdafb-117">If your device is not listed above, and you need to use it with Basic Mobility and Security, contact your work or school administrator.</span></span>

>[!TIP] 
><span data-ttu-id="bdafb-118">장치를 등록 하는 데 문제가 있는 경우 [기본 이동성 및 보안 문제 해결](troubleshoot.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="bdafb-118">If you're having trouble enrolling your device, see [Troubleshoot Basic Mobility and Security](troubleshoot.md).</span></span>

## <a name="set-up-your-mobile-device-with-intune-and-basic-mobility-and-security"></a><span data-ttu-id="bdafb-119">Intune과 기본 이동성 및 보안을 사용 하 여 모바일 장치 설정</span><span class="sxs-lookup"><span data-stu-id="bdafb-119">Set up your mobile device with Intune and Basic Mobility and Security</span></span>

<span data-ttu-id="bdafb-120">Intune 회사 포털을 사용 하면 Microsoft 365 및 기본 이동성 및 보안을 통해 장치를 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bdafb-120">The Intune Company Portal enables a device to be managed by Microsoft 365 and Basic Mobility and Security.</span></span>

### <a name="iphone-or-ipad"></a><span data-ttu-id="bdafb-121">iPhone 또는 iPad</span><span class="sxs-lookup"><span data-stu-id="bdafb-121">iPhone or iPad</span></span>

>[!TIP]
><span data-ttu-id="bdafb-122">이 단계를 완료 해야 전자 메일을 보내고 받을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bdafb-122">You won’t be able to send and receive email until you complete this step.</span></span>

<span data-ttu-id="bdafb-123">Apple App Store로 이동 하 여 Intune 회사 포털을 다운로드 하 고 설치 합니다.</span><span class="sxs-lookup"><span data-stu-id="bdafb-123">Go to the Apple App Store, and download and install Intune Company Portal.</span></span>

<span data-ttu-id="bdafb-124">회사 포털로 Office 365을 사용 하 여 iOS 휴대폰 또는 태블릿을 연결 하 고 구성 하려면 [ios 장치 액세스를 회사 리소스에 설정](https://go.microsoft.com/fwlink/?linkid=875316)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="bdafb-124">To connect and configure your iOS phone or tablet with the Company portal to Office 365, see [Set up iOS device access to your company resources](https://go.microsoft.com/fwlink/?linkid=875316).</span></span>

### <a name="android-phone-or-tablet"></a><span data-ttu-id="bdafb-125">Android 휴대폰 또는 태블릿</span><span class="sxs-lookup"><span data-stu-id="bdafb-125">Android phone or tablet</span></span>

>[!TIP]
><span data-ttu-id="bdafb-126">이 단계를 완료 해야 전자 메일을 보내고 받을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bdafb-126">You won’t be able to send and receive email until you complete this step.</span></span>

<span data-ttu-id="bdafb-127">Google Play store로 이동 하 여 Intune 회사 포털을 다운로드 하 고 설치 합니다.</span><span class="sxs-lookup"><span data-stu-id="bdafb-127">Go to the Google Play store, and download and install Intune Company Portal.</span></span>

<span data-ttu-id="bdafb-128">회사 포털을 사용 하 여 Microsoft 365로 Android 휴대폰 또는 태블릿을 연결 하 고 구성 하려면 [회사 포털에 디바이스 등록](https://go.microsoft.com/fwlink/?linkid=875317)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="bdafb-128">To connect and configure your Android phone or tablet with the Company portal to Microsoft 365, see [Enroll your device with Company Portal](https://go.microsoft.com/fwlink/?linkid=875317).</span></span>

### <a name="windows-81-and-windows-10"></a><span data-ttu-id="bdafb-129">Windows 8.1 및 Windows 10</span><span class="sxs-lookup"><span data-stu-id="bdafb-129">Windows 8.1 and Windows 10</span></span>

<span data-ttu-id="bdafb-130">Microsoft Store로 이동 하 여 Intune 회사 포털 다운로드 및 설치</span><span class="sxs-lookup"><span data-stu-id="bdafb-130">Go to the Microsoft Store, and download and install Intune Company Portal</span></span>

<span data-ttu-id="bdafb-131">회사 포털을 사용 하 여 Windows phone 또는 PC를 Microsoft 365에 연결 하 고 구성 하려면 [Intune 회사 포털에서 windows 디바이스 등록](https://docs.microsoft.com/intune-user-help/windows-enrollment-company-portal)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="bdafb-131">To connect and configure your Windows phone or PC with the Company portal to Microsoft 365, see [Windows device enrollment in Intune Company Portal](https://docs.microsoft.com/intune-user-help/windows-enrollment-company-portal).</span></span>

## <a name="whats-next"></a><span data-ttu-id="bdafb-132">다음 작업</span><span class="sxs-lookup"><span data-stu-id="bdafb-132">What's next?</span></span>

<span data-ttu-id="bdafb-133">장치를 기본 Mobility and Security에 등록 한 후에는 장치에서 Office 앱을 사용 하 여 전자 메일, 일정, 연락처 및 문서로 작업할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bdafb-133">After your device is enrolled in Basic Mobility and Security, you can start using Office apps on your device to work with email, calendar, contacts, and documents.</span></span>