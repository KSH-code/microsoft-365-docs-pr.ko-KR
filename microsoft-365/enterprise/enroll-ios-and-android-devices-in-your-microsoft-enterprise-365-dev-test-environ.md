---
title: Microsoft 365에서 엔터프라이즈 테스트 환경용 iOS 및 Android 장치 등록
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 12/09/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection: M365-identity-device-management
ms.custom: Ent_TLGs
ms.assetid: 49c7758a-1c01-4153-9b63-5eae3f6305ce
description: 이 테스트 랩 가이드를 사용 하 여 Microsoft 365 테스트 환경에서 장치를 등록 하 고 원격으로 관리 합니다.
ms.openlocfilehash: 3736934dbb62e84aad6a91fcd1d65b4a47ef8637
ms.sourcegitcommit: 53ff1fe6d6143b0bf011031eea9b85dc01ae4f74
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48487699"
---
# <a name="enroll-ios-and-android-devices-in-your-microsoft-365-for-enterprise-test-environment"></a><span data-ttu-id="9c4c9-103">Microsoft 365에서 엔터프라이즈 테스트 환경용 iOS 및 Android 장치 등록</span><span class="sxs-lookup"><span data-stu-id="9c4c9-103">Enroll iOS and Android devices in your Microsoft 365 for enterprise test environment</span></span>

<span data-ttu-id="9c4c9-104">*이 테스트 랩 가이드는 엔터프라이즈 테스트 환경용 Microsoft 365에만 사용할 수 있습니다.*</span><span class="sxs-lookup"><span data-stu-id="9c4c9-104">*This Test Lab Guide can only be used for Microsoft 365 for enterprise test environments.*</span></span>

<span data-ttu-id="9c4c9-105">이 문서에서는 엔터프라이즈 테스트 환경용 Microsoft 365에서 iOS 및 Android 장치에 대 한 기본 모바일 장치 관리 기능을 등록 하 고 테스트 하는 방법에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="9c4c9-105">This article describes how to enroll and test basic mobile device management capabilities for iOS and Android devices in your Microsoft 365 for enterprise test environment.</span></span>

<span data-ttu-id="9c4c9-106">테스트 환경에서 iOS 및 Android 장치를 등록 하는 작업은 다음 세 단계로 진행 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9c4c9-106">Enrolling iOS and Android devices in your test environment involves three phases:</span></span>
- [<span data-ttu-id="9c4c9-107">1 단계: 엔터프라이즈 테스트 환경용 Microsoft 365 구축</span><span class="sxs-lookup"><span data-stu-id="9c4c9-107">Phase 1: Build out your Microsoft 365 for enterprise test environment</span></span>](#phase-1-build-out-your-microsoft-365-for-enterprise-test-environment)
- [<span data-ttu-id="9c4c9-108">2 단계: iOS 및 Android 장치 등록</span><span class="sxs-lookup"><span data-stu-id="9c4c9-108">Phase 2: Enroll your iOS and Android devices</span></span>](#phase-2-enroll-your-ios-and-android-devices)
- [<span data-ttu-id="9c4c9-109">3 단계: 원격으로 iOS 및 Android 장치 관리</span><span class="sxs-lookup"><span data-stu-id="9c4c9-109">Phase 3: Manage your iOS and Android devices remotely</span></span>](#phase-3-manage-your-ios-and-android-devices-remotely)

![Microsoft 클라우드의 테스트 랩 가이드](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png)
  
> [!TIP]
> <span data-ttu-id="9c4c9-111">엔터프라이즈 테스트 랩 가이드 스택의 Microsoft 365에 있는 모든 문서에 대 한 시각적 지도를 보려면 [microsoft 365 for 엔터프라이즈 테스트 랩 가이드 스택을](../downloads/Microsoft365EnterpriseTLGStack.pdf)방문 하세요.</span><span class="sxs-lookup"><span data-stu-id="9c4c9-111">For a visual map to all the articles in the Microsoft 365 for enterprise Test Lab Guide stack, go to [Microsoft 365 for enterprise Test Lab Guide Stack](../downloads/Microsoft365EnterpriseTLGStack.pdf).</span></span>

## <a name="phase-1-build-out-your-microsoft-365-for-enterprise-test-environment"></a><span data-ttu-id="9c4c9-112">1 단계: 엔터프라이즈 테스트 환경용 Microsoft 365 구축</span><span class="sxs-lookup"><span data-stu-id="9c4c9-112">Phase 1: Build out your Microsoft 365 for enterprise test environment</span></span>

<span data-ttu-id="9c4c9-113">최소 요구 사항에 따라 간단한 방식으로 iOS 및 Android 장치를 등록 하려는 경우에는 [간단한 기본 구성](lightweight-base-configuration-microsoft-365-enterprise.md)의 지침을 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="9c4c9-113">If you want to enroll iOS and Android devices in a lightweight way with the minimum requirements, follow the instructions in [Lightweight base configuration](lightweight-base-configuration-microsoft-365-enterprise.md).</span></span>
  
<span data-ttu-id="9c4c9-114">시뮬레이트된 엔터프라이즈에서 iOS 및 Android 장치를 등록 하려면 [통과 인증](pass-through-auth-m365-ent-test-environment.md)의 지침을 따르세요.</span><span class="sxs-lookup"><span data-stu-id="9c4c9-114">If you want to enroll iOS and Android devices in a simulated enterprise, follow the instructions in [Pass-through authentication](pass-through-auth-m365-ent-test-environment.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="9c4c9-115">자동 라이선싱 및 그룹 구성원을 테스트 하려면 AD DS (Active Directory 도메인 서비스) 포리스트의 인터넷 및 디렉터리 동기화에 연결 된 시뮬레이트된 인트라넷을 포함 하는 시뮬레이트된 엔터프라이즈 테스트 환경이 필요 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="9c4c9-115">Testing automated licensing and group membership doesn't require the simulated enterprise test environment, which includes a simulated intranet connected to the internet and directory synchronization for an Active Directory Domain Services (AD DS) forest.</span></span> <span data-ttu-id="9c4c9-116">자동 라이선싱 및 그룹 멤버 자격을 테스트할 수 있도록 옵션으로 제공 되며, 일반적인 조직을 나타내는 환경에서이를 시험해 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9c4c9-116">It's provided here as an option so that you can test automated licensing and group membership, and you can experiment with it in an environment that represents a typical organization.</span></span>

## <a name="phase-2-enroll-your-ios-and-android-devices"></a><span data-ttu-id="9c4c9-117">2 단계: iOS 및 Android 장치 등록</span><span class="sxs-lookup"><span data-stu-id="9c4c9-117">Phase 2: Enroll your iOS and Android devices</span></span>

<span data-ttu-id="9c4c9-118">먼저 Install (설치)의 지침을 사용 하 여 테스트 환경에 대 한 Microsoft Intune 회사 포털 앱을 사용자 지정 하 [고 회사 포털 앱에 로그인](https://docs.microsoft.com/intune-user-help/install-and-sign-in-to-the-intune-company-portal-app-ios) 합니다.</span><span class="sxs-lookup"><span data-stu-id="9c4c9-118">First, use the instructions in [Install and sign in to the Company Portal app](https://docs.microsoft.com/intune-user-help/install-and-sign-in-to-the-intune-company-portal-app-ios) to customize the Microsoft Intune Company Portal app for your test environment.</span></span>

<span data-ttu-id="9c4c9-119">그런 다음 [회사 리소스에 대 한 액세스 설정](https://docs.microsoft.com/intune-user-help/enroll-your-device-in-intune-ios) 의 지침을 사용 하 여 iOS 장치를 등록 합니다.</span><span class="sxs-lookup"><span data-stu-id="9c4c9-119">Next, use the instructions in [Set up access to your company resources](https://docs.microsoft.com/intune-user-help/enroll-your-device-in-intune-ios) to enroll an iOS device.</span></span>

<span data-ttu-id="9c4c9-120">다음으로, [Intune에서 android 장치 등록](https://docs.microsoft.com/intune-user-help/enroll-your-device-in-intune-android) 의 지침을 사용 하 여 android 장치를 등록 합니다.</span><span class="sxs-lookup"><span data-stu-id="9c4c9-120">Next, use the instructions in [Enroll your Android device in Intune](https://docs.microsoft.com/intune-user-help/enroll-your-device-in-intune-android) to enroll an Android device.</span></span>

## <a name="phase-3-manage-your-ios-and-android-devices-remotely"></a><span data-ttu-id="9c4c9-121">3 단계: 원격으로 iOS 및 Android 장치 관리</span><span class="sxs-lookup"><span data-stu-id="9c4c9-121">Phase 3: Manage your iOS and Android devices remotely</span></span>

<span data-ttu-id="9c4c9-122">Microsoft Intune에서는 원격 잠금 및 암호 초기화 기능을 모두 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="9c4c9-122">Microsoft Intune provides both remote lock and passcode reset capabilities.</span></span> <span data-ttu-id="9c4c9-123">다른 사용자가 장치를 분실 한 경우 장치를 원격으로 잠글 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9c4c9-123">If someone loses their device, you can remotely lock the device.</span></span> <span data-ttu-id="9c4c9-124">다른 사용자가 암호를 잊어버린 경우 원격으로 다시 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9c4c9-124">If someone forgets their passcode, you can remotely reset it.</span></span>
  
<span data-ttu-id="9c4c9-125">IOS 또는 Android 장치를 원격으로 잠그려면:</span><span class="sxs-lookup"><span data-stu-id="9c4c9-125">To remotely lock an iOS or Android device:</span></span>

1. <span data-ttu-id="9c4c9-126">전역 관리자 계정의 자격 증명을 사용 하 여 Azure portal에 로그인 [https://portal.azure.com](https://portal.azure.com) 합니다.</span><span class="sxs-lookup"><span data-stu-id="9c4c9-126">Sign in to the Azure portal at [https://portal.azure.com](https://portal.azure.com) with the credentials of your global administrator account.</span></span>
2. <span data-ttu-id="9c4c9-127">Azure portal의 검색 상자에 **intune** 을 입력 하 고 **intune**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="9c4c9-127">In the Azure portal, enter **Intune** in the search box, and then select **Intune**.</span></span>
3. <span data-ttu-id="9c4c9-128">**모든 장치 > 장치**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="9c4c9-128">Click **Devices > All devices**.</span></span>
4. <span data-ttu-id="9c4c9-129">장치 목록에서 iOS 또는 Android 장치를 선택한 다음 **원격 잠금** 작업을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="9c4c9-129">In the list of devices, select an iOS or Android device, and then select the **Remote lock** action.</span></span>
    
<span data-ttu-id="9c4c9-130">원격으로 암호를 다시 설정 하려면:</span><span class="sxs-lookup"><span data-stu-id="9c4c9-130">To remotely reset the passcode:</span></span>

1. <span data-ttu-id="9c4c9-131">필요한 경우 [https://portal.azure.com](https://portal.azure.com) 전역 관리자 계정의 자격 증명을 사용 하 여 Azure portal에 로그인 합니다.</span><span class="sxs-lookup"><span data-stu-id="9c4c9-131">If needed, sign in to the Azure portal at [https://portal.azure.com](https://portal.azure.com) with the credentials of your global administrator account.</span></span>
2. <span data-ttu-id="9c4c9-132">Azure portal의 검색 상자에 **intune** 을 입력 하 고 **intune**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="9c4c9-132">In the Azure portal, enter **Intune** in the search box, and then select **Intune**.</span></span>
3. <span data-ttu-id="9c4c9-133">**장치**  >  **모든 장치**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="9c4c9-133">Select **Devices** > **All devices**.</span></span>
4. <span data-ttu-id="9c4c9-134">관리 하는 장치 목록에서 iOS 또는 Android 장치를 선택 하 고 ...를 선택 **합니다. 추가**를 클릭 한 다음 **암호 제거** 장치 원격 작업을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="9c4c9-134">From the list of devices you manage, select an iOS or Android device, select **...More**, and then select the **Remove passcode** device remote action.</span></span>

<span data-ttu-id="9c4c9-135">자세한 내용은 [사용 가능한 장치 작업](https://docs.microsoft.com/intune/device-management#available-device-actions)을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="9c4c9-135">For additional experimentation, see [Available device actions](https://docs.microsoft.com/intune/device-management#available-device-actions).</span></span>
    
## <a name="next-step"></a><span data-ttu-id="9c4c9-136">다음 단계</span><span class="sxs-lookup"><span data-stu-id="9c4c9-136">Next step</span></span>

<span data-ttu-id="9c4c9-137">테스트 환경에서 추가 [모바일 장치 관리](m365-enterprise-test-lab-guides.md#mobile-device-management) 기능을 알아봅니다.</span><span class="sxs-lookup"><span data-stu-id="9c4c9-137">Explore additional [mobile device management](m365-enterprise-test-lab-guides.md#mobile-device-management) features and capabilities in your test environment.</span></span>

## <a name="see-also"></a><span data-ttu-id="9c4c9-138">참고 항목</span><span class="sxs-lookup"><span data-stu-id="9c4c9-138">See Also</span></span>

[<span data-ttu-id="9c4c9-139">엔터프라이증용 Microsoft 365 테스트 랩 가이드</span><span class="sxs-lookup"><span data-stu-id="9c4c9-139">Microsoft 365 for enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)
  
[<span data-ttu-id="9c4c9-140">엔터프라이즈 테스트 환경용 Microsoft 365에 대 한 장치 준수 정책</span><span class="sxs-lookup"><span data-stu-id="9c4c9-140">Device compliance policies for your Microsoft 365 for enterprise test environment</span></span>](mam-policies-for-your-microsoft-365-enterprise-dev-test-environment.md)
  
[<span data-ttu-id="9c4c9-141">엔터프라이즈용 Microsoft 365 개요</span><span class="sxs-lookup"><span data-stu-id="9c4c9-141">Microsoft 365 for enterprise overview</span></span>](microsoft-365-overview.md)
