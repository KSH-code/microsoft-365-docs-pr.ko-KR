---
title: 엔터프라이즈 테스트 환경에 Microsoft 365 iOS/iPadOS 및 Android 장치 등록
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 11/19/2020
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection: M365-identity-device-management
ms.custom: Ent_TLGs
ms.assetid: 49c7758a-1c01-4153-9b63-5eae3f6305ce
description: 이 테스트 랩 가이드를 사용하여 테스트 환경에 장치를 등록하고 Microsoft 365 원격으로 관리합니다.
ms.openlocfilehash: 06f83d1ed61bcc530b6aa974d7730f1aadc0ecbd
ms.sourcegitcommit: 001e64f89f9c3cd6bbd4a25459f5bee3b966820c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/20/2020
ms.locfileid: "49367086"
---
# <a name="enroll-ios-and-android-devices-in-your-microsoft-365-for-enterprise-test-environment"></a><span data-ttu-id="a1a22-103">엔터프라이즈 테스트 환경에 Microsoft 365 iOS 및 Android 장치 등록</span><span class="sxs-lookup"><span data-stu-id="a1a22-103">Enroll iOS and Android devices in your Microsoft 365 for enterprise test environment</span></span>

<span data-ttu-id="a1a22-104">*이 테스트 랩 가이드는 엔터프라이즈 테스트 환경에 Microsoft 365 사용할 수 있습니다.*</span><span class="sxs-lookup"><span data-stu-id="a1a22-104">*This Test Lab Guide can only be used for Microsoft 365 for enterprise test environments.*</span></span>

<span data-ttu-id="a1a22-105">이 문서에서는 엔터프라이즈 테스트 환경에서 iOS/iPadOS 및 Android 장치에 대한 기본 모바일 장치 관리 기능을 등록하고 Microsoft 365 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="a1a22-105">This article describes how to enroll and test basic mobile device management capabilities for iOS/iPadOS and Android devices in your Microsoft 365 for enterprise test environment.</span></span>

<span data-ttu-id="a1a22-106">테스트 환경에 iOS/iPadOS 및 Android 장치를 등록하는 데는 다음 세 단계가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a1a22-106">Enrolling iOS/iPadOS and Android devices in your test environment involves three phases:</span></span>
- [<span data-ttu-id="a1a22-107">1단계: 엔터프라이즈 테스트 Microsoft 365 사용자 환경 구축</span><span class="sxs-lookup"><span data-stu-id="a1a22-107">Phase 1: Build out your Microsoft 365 for enterprise test environment</span></span>](#phase-1-build-out-your-microsoft-365-for-enterprise-test-environment)
- [<span data-ttu-id="a1a22-108">2단계: iOS/iPadOS 및 Android 장치 등록</span><span class="sxs-lookup"><span data-stu-id="a1a22-108">Phase 2: Enroll your iOS/iPadOS and Android devices</span></span>](#phase-2-enroll-your-ios-and-android-devices)
- [<span data-ttu-id="a1a22-109">3단계: 원격으로 iOS/iPadOS 및 Android 장치 관리</span><span class="sxs-lookup"><span data-stu-id="a1a22-109">Phase 3: Manage your iOS/iPadOS and Android devices remotely</span></span>](#phase-3-manage-your-ios-and-android-devices-remotely)

![Microsoft 클라우드의 테스트 랩 가이드](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png)
  
> [!TIP]
> <span data-ttu-id="a1a22-111">엔터프라이즈용 테스트 랩 가이드 스택의 Microsoft 365 모든 문서에 대한 시각적 맵을 확인한 다음 엔터프라이즈 테스트 랩 Microsoft 365 스택에 대한 자세한 [설명을 참조하세요.](../downloads/Microsoft365EnterpriseTLGStack.pdf)</span><span class="sxs-lookup"><span data-stu-id="a1a22-111">For a visual map to all the articles in the Microsoft 365 for enterprise Test Lab Guide stack, go to [Microsoft 365 for enterprise Test Lab Guide Stack](../downloads/Microsoft365EnterpriseTLGStack.pdf).</span></span>

## <a name="phase-1-build-out-your-microsoft-365-for-enterprise-test-environment"></a><span data-ttu-id="a1a22-112">1단계: 엔터프라이즈 테스트 Microsoft 365 사용자 환경 구축</span><span class="sxs-lookup"><span data-stu-id="a1a22-112">Phase 1: Build out your Microsoft 365 for enterprise test environment</span></span>

<span data-ttu-id="a1a22-113">최소 요구 사항으로 iOS/iPadOS 및 Android 장치를 경량 방식으로 등록하려면 Lightweight [base configuration의](lightweight-base-configuration-microsoft-365-enterprise.md)지침을 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="a1a22-113">If you want to enroll iOS/iPadOS and Android devices in a lightweight way with the minimum requirements, follow the instructions in [Lightweight base configuration](lightweight-base-configuration-microsoft-365-enterprise.md).</span></span>
  
<span data-ttu-id="a1a22-114">시뮬레이트된 엔터프라이즈에서 iOS/iPadOS 및 Android 장치를 등록하려는 경우 통과 인증의 [지침을 따릅니다.](pass-through-auth-m365-ent-test-environment.md)</span><span class="sxs-lookup"><span data-stu-id="a1a22-114">If you want to enroll iOS/iPadOS and Android devices in a simulated enterprise, follow the instructions in [Pass-through authentication](pass-through-auth-m365-ent-test-environment.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="a1a22-115">자동화된 라이선스 및 그룹 멤버 자격을 테스트하는 데는 인터넷에 연결된 시뮬레이트된 인트라넷과 AD DS(Active Directory 도메인 서비스) 포리스트에 대한 디렉터리 동기화를 포함하는 시뮬레이트된 엔터프라이즈 테스트 환경이 필요하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="a1a22-115">Testing automated licensing and group membership doesn't require the simulated enterprise test environment, which includes a simulated intranet connected to the internet and directory synchronization for an Active Directory Domain Services (AD DS) forest.</span></span> <span data-ttu-id="a1a22-116">여기서는 옵션으로 제공되어 자동화된 라이선싱 및 그룹 멤버 자격을 테스트할 수 있으며, 일반적인 조직을 나타내는 환경에서 실험해 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a1a22-116">It's provided here as an option so that you can test automated licensing and group membership, and you can experiment with it in an environment that represents a typical organization.</span></span>

## <a name="phase-2-enroll-your-ios-and-android-devices"></a><span data-ttu-id="a1a22-117">2단계: iOS 및 Android 장치 등록</span><span class="sxs-lookup"><span data-stu-id="a1a22-117">Phase 2: Enroll your iOS and Android devices</span></span>

<span data-ttu-id="a1a22-118">장치를 관리하기 위한 MDM(모바일 장치 관리) 솔루션을 고려하고 있는 경우 이 솔루션을 사용하여 Microsoft Intune.</span><span class="sxs-lookup"><span data-stu-id="a1a22-118">If you're considering a mobile device management (MDM) solution to manage your devices, you can use Microsoft Intune.</span></span> <span data-ttu-id="a1a22-119">Intune을 비롯한 MDM 공급자와 함께 작업하는 경우 장치는 "등록"됩니다.</span><span class="sxs-lookup"><span data-stu-id="a1a22-119">When working with any MDM provider, including Intune, devices are "enrolled".</span></span> <span data-ttu-id="a1a22-120">등록하면 사용자가 구성한 기능 및 설정을 받게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a1a22-120">When enrolled, they receive the features and settings you configure.</span></span> 

<span data-ttu-id="a1a22-121">Intune에서 몇 가지 방법으로 iOS/iPadOS 및 Android 장치를 등록할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a1a22-121">In Intune, there are a few ways to enroll your iOS/iPadOS and Android devices.</span></span> <span data-ttu-id="a1a22-122">조직에 가장 적합한 등록 옵션을 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a1a22-122">You can choose the enrollment option that works best for your organization.</span></span> <span data-ttu-id="a1a22-123">자세한 내용과 지침은 다음 문서를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="a1a22-123">For more information and guidance, see the following articles:</span></span>

- [<span data-ttu-id="a1a22-124">배포 가이드: iOS 및 iPadOS 장치를 Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="a1a22-124">Deployment guide: Enroll iOS and iPadOS devices in Microsoft Intune</span></span>](/mem/intune/fundamentals/deployment-guide-enrollment-ios-ipados)
- [<span data-ttu-id="a1a22-125">배포 가이드: Android 장치에 Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="a1a22-125">Deployment guide: Enroll Android devices in Microsoft Intune</span></span>](/mem/intune/fundamentals/deployment-guide-enrollment-android)

<span data-ttu-id="a1a22-126">장치 관리에 Intune을 사용할 준비가 되어 있으며 몇 가지 지침을 원하는 경우 다음 정보가 도움이 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a1a22-126">If you're ready to use Intune for device management, and want some guidance, then the following information may help:</span></span>

- [<span data-ttu-id="a1a22-127">장치 관리 개요</span><span class="sxs-lookup"><span data-stu-id="a1a22-127">Device management overview</span></span>](/mem/intune/fundamentals/what-is-device-management)
- [<span data-ttu-id="a1a22-128">자습서: Microsoft Endpoint Manager</span><span class="sxs-lookup"><span data-stu-id="a1a22-128">Tutorial: Walkthrough Intune in Microsoft Endpoint Manager</span></span>](/mem/intune/fundamentals/tutorial-walkthrough-endpoint-manager)
- [<span data-ttu-id="a1a22-129">배포 가이드: 설치 또는 배포로 Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="a1a22-129">Deployment guide: Setup or move to Microsoft Intune</span></span>](/mem/intune/fundamentals/deployment-guide-intune-setup)

## <a name="phase-3-manage-your-ios-and-android-devices-remotely"></a><span data-ttu-id="a1a22-130">3단계: 원격으로 iOS 및 Android 장치 관리</span><span class="sxs-lookup"><span data-stu-id="a1a22-130">Phase 3: Manage your iOS and Android devices remotely</span></span>

<span data-ttu-id="a1a22-131">Microsoft Intune 원격 잠금 및 암호 재설정 기능을 제공하는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="a1a22-131">Microsoft Intune provides remote lock and passcode reset feature.</span></span> <span data-ttu-id="a1a22-132">누군가 장치를 분실한 경우 원격으로 디바이스를 잠글 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a1a22-132">If someone loses their device, you can remotely lock the device.</span></span> <span data-ttu-id="a1a22-133">누군가 암호를 잊어버렸다면 원격으로 다시 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a1a22-133">If someone forgets their passcode, you can remotely reset it.</span></span>

- <span data-ttu-id="a1a22-134">iOS/iPadOS 또는 Android 장치를 원격으로 잠그기 위해 Intune을 사용하여 원격으로 디바이스 [잠금을 참조하세요.](/mem/intune/remote-actions/device-remote-lock)</span><span class="sxs-lookup"><span data-stu-id="a1a22-134">To remotely lock an iOS/iPadOS or Android device, see [Remotely lock devices with Intune](/mem/intune/remote-actions/device-remote-lock).</span></span>
- <span data-ttu-id="a1a22-135">원격으로 암호를 다시 설정하려면 Intune에서 장치 암호 재설정 또는 [제거를 참조하세요.](/mem/intune/remote-actions/device-passcode-reset)</span><span class="sxs-lookup"><span data-stu-id="a1a22-135">To remotely reset the passcode, see [Reset or remove a device passcode in Intune](/mem/intune/remote-actions/device-passcode-reset).</span></span>

<span data-ttu-id="a1a22-136">원격으로 실행할 수 있는 추가 작업에 대한 자세한 내용은 사용 가능한 장치 [작업을 참조하세요.](/mem/intune/remote-actions/device-management#available-device-actions)</span><span class="sxs-lookup"><span data-stu-id="a1a22-136">For additional tasks you can run remotely, see [available device actions](/mem/intune/remote-actions/device-management#available-device-actions).</span></span>
    
## <a name="next-step"></a><span data-ttu-id="a1a22-137">다음 단계</span><span class="sxs-lookup"><span data-stu-id="a1a22-137">Next step</span></span>

<span data-ttu-id="a1a22-138">테스트 [환경의](m365-enterprise-test-lab-guides.md#mobile-device-management) 추가 모바일 장치 관리 기능 살펴보기</span><span class="sxs-lookup"><span data-stu-id="a1a22-138">Explore additional [mobile device management](m365-enterprise-test-lab-guides.md#mobile-device-management) features and capabilities in your test environment.</span></span>

## <a name="see-also"></a><span data-ttu-id="a1a22-139">참고 항목</span><span class="sxs-lookup"><span data-stu-id="a1a22-139">See Also</span></span>

[<span data-ttu-id="a1a22-140">엔터프라이증용 Microsoft 365 테스트 랩 가이드</span><span class="sxs-lookup"><span data-stu-id="a1a22-140">Microsoft 365 for enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)
  
[<span data-ttu-id="a1a22-141">엔터프라이즈 테스트 환경에 대한 Microsoft 365 장치 준수 정책</span><span class="sxs-lookup"><span data-stu-id="a1a22-141">Device compliance policies for your Microsoft 365 for enterprise test environment</span></span>](mam-policies-for-your-microsoft-365-enterprise-dev-test-environment.md)
  
[<span data-ttu-id="a1a22-142">엔터프라이즈용 Microsoft 365 개요</span><span class="sxs-lookup"><span data-stu-id="a1a22-142">Microsoft 365 for enterprise overview</span></span>](microsoft-365-overview.md)
