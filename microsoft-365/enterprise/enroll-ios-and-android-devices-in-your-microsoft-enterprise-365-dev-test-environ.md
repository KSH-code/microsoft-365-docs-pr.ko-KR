---
title: Microsoft 365 Enterprise 테스트 환경에서 iOS 및 Android 장치 등록
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 07/11/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection: Ent_O365
ms.custom: Ent_TLGs
ms.assetid: 49c7758a-1c01-4153-9b63-5eae3f6305ce
description: 이 테스트 랩 가이드를 Microsoft 365 테스트 환경에서 장치를 등록 하 고 원격으로 관리 하기를 사용 합니다.
ms.openlocfilehash: 98696104ee8453adb7449980cf439eeb152aeea9
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/28/2018
ms.locfileid: "26869856"
---
# <a name="enroll-ios-and-android-devices-in-your-microsoft-365-enterprise-test-environment"></a><span data-ttu-id="b6548-103">Microsoft 365 Enterprise 테스트 환경에서 iOS 및 Android 장치 등록</span><span class="sxs-lookup"><span data-stu-id="b6548-103">Enroll iOS and Android devices in your Microsoft 365 Enterprise test environment</span></span>

<span data-ttu-id="b6548-104">이 문서에서 제공 하는 지침을 따르면를 등록 하 고 Microsoft 365 기업 테스트 환경에서 iOS 및 Android 장치에 대 한 기본 모바일 장치 관리 기능을 테스트 하는 작업을 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b6548-104">By following the instructions provided in this article, you'll be able to enroll and test basic mobile device management capabilities for iOS and Android devices in your Microsoft 365 Enterprise test environment.</span></span>

![Microsoft 클라우드의 테스트 랩 가이드](media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png)
  
> [!TIP]
> <span data-ttu-id="b6548-106">[여기](https://aka.ms/m365etlgstack)를 클릭하여 Microsoft 365 Enterprise 테스트 랩 가이드 스택의 모든 문서에 대한 가상 맵을 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b6548-106">Click [here](https://aka.ms/m365etlgstack) for a visual map to all the articles in the Microsoft 365 Enterprise Test Lab Guide stack.</span></span>

## <a name="phase-1-build-out-your-microsoft-365-enterprise-test-environment"></a><span data-ttu-id="b6548-107">1 단계: Microsoft 365 Enterprise 테스트 환경을 구축합니다</span><span class="sxs-lookup"><span data-stu-id="b6548-107">Phase 1: Build out your Microsoft 365 Enterprise test environment</span></span>

<span data-ttu-id="b6548-108">최소 요구 사항을 경량 방식으로 iOS 및 Android 장치를 등록 하려면 [경량 기본 구성](lightweight-base-configuration-microsoft-365-enterprise.md)의 지시를 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="b6548-108">If you just want to enroll iOS and Android devices in a lightweight way with the minimum requirements, follow the instructions in [Lightweight base configuration](lightweight-base-configuration-microsoft-365-enterprise.md).</span></span>
  
<span data-ttu-id="b6548-109">IOS 및 시뮬레이션 된 엔터프라이즈에서 Android 장치 등록 하려는 경우 [통과 인증](pass-through-auth-m365-ent-test-environment.md)에 대 한 지침을 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="b6548-109">If you want to enroll iOS and Android devices in a simulated enterprise, follow the instructions in [Pass-through authentication](pass-through-auth-m365-ent-test-environment.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="b6548-p101">라이선스 하는 자동화 된 테스트 하 고 그룹 멤버 자격을 원하지 않는 인터넷에 연결 하는 시뮬레이션 된 인트라넷을 포함 하는 시뮬레이션 된 엔터프라이즈 테스트 환경 및 Windows Server AD 포리스트에 대 한 디렉터리 동기화 합니다. 제공는 자동화 된 라이선스 및 그룹 구성원 자격을 테스트 하 고 일반적인 조직을 대표 하는 환경에서 사용해 수 있도록 하는 옵션으로 여기 합니다.</span><span class="sxs-lookup"><span data-stu-id="b6548-p101">Testing automated licensing and group membership does not require the simulated enterprise test environment, which includes a simulated intranet connected to the Internet and directory synchronization for a Windows Server AD forest. It is provided here as an option so that you can test automated licensing and group membership and experiment with it in an environment that represents a typical organization.</span></span> 
>  

## <a name="phase-2-enroll-your-ios-and-android-devices"></a><span data-ttu-id="b6548-112">2 단계: iOS 및 Android 장치 등록</span><span class="sxs-lookup"><span data-stu-id="b6548-112">Phase 2: Enroll your iOS and Android devices</span></span>

<span data-ttu-id="b6548-113">먼저,의 지침을 사용 하 여 [설치 회사 포털 응용 프로그램에 로그인 하 고](https://docs.microsoft.com/intune-user-help/install-and-sign-in-to-the-intune-company-portal-app-ios) 테스트 환경에 대 한 Microsoft Intune 회사 포털 응용 프로그램을 사용자 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b6548-113">First, use the instructions in [Install and sign in to the Company Portal app](https://docs.microsoft.com/intune-user-help/install-and-sign-in-to-the-intune-company-portal-app-ios) to customize the Microsoft Intune Company Portal app for your test environment.</span></span>

<span data-ttu-id="b6548-114">다음으로 iOS 장치를 등록 하려면 [회사 리소스에 대 한 액세스를 설정](https://docs.microsoft.com/intune-user-help/enroll-your-device-in-intune-ios) 하는의 지침을 따르십시오.</span><span class="sxs-lookup"><span data-stu-id="b6548-114">Next, use the instructions in [Set up access to your company resources](https://docs.microsoft.com/intune-user-help/enroll-your-device-in-intune-ios) to enroll an iOS device.</span></span>

<span data-ttu-id="b6548-115">다음으로, Android 장치와 등록 [등록 Intune에서 Android 장치에서](https://docs.microsoft.com/intune-user-help/enroll-your-device-in-intune-android) 에서 지침을 따르십시오.</span><span class="sxs-lookup"><span data-stu-id="b6548-115">Next, use the instructions in [Enroll your Android device in Intune](https://docs.microsoft.com/intune-user-help/enroll-your-device-in-intune-android) to enroll an Android device.</span></span>

## <a name="phase-3-manage-your-ios-and-android-devices-remotely"></a><span data-ttu-id="b6548-116">3 단계: iOS 및 Android 장치를 원격으로 관리</span><span class="sxs-lookup"><span data-stu-id="b6548-116">Phase 3: Manage your iOS and Android devices remotely</span></span>

<span data-ttu-id="b6548-p102">Microsoft Intune 원격 잠금 및 암호를 모두 재설정 기능을 제공 합니다. 다른 사용자가 장치를 잃을 하는 경우 원격으로 장치를 잠글 수 있습니다. 다른 사용자가 자신의 암호를 잊어버린를 원격으로 재설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b6548-p102">Microsoft Intune provides both remote lock and passcode reset capabilities. If someone loses their device, you can lock the device remotely. If someone forgets their passcode, you can reset it remotely.</span></span>
  
<span data-ttu-id="b6548-120">IOS 또는 Android 장치를 원격으로 잠그려면:</span><span class="sxs-lookup"><span data-stu-id="b6548-120">To lock an iOS or Android device remotely:</span></span>

1. <span data-ttu-id="b6548-121">Azure 포털에 로그인 [https://portal.azure.com](https://portal.azure.com) 전역 관리자 계정의 자격 증명을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="b6548-121">Sign in to the Azure portal at [https://portal.azure.com](https://portal.azure.com) with the credentials of your global administrator account.</span></span>
2. <span data-ttu-id="b6548-122">**모든 서비스**를 클릭 하 고 **Intune**입력 다음 **Intune**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="b6548-122">Click **All services**, type **Intune**, and then click **Intune**.</span></span>
3. <span data-ttu-id="b6548-123">클릭 **장치 > 모든 장치**합니다.</span><span class="sxs-lookup"><span data-stu-id="b6548-123">Click **Devices > All devices**.</span></span>
4. <span data-ttu-id="b6548-124">장치 목록에서 iOS 또는 Android 장치를 클릭 하 고 **원격 잠금** 동작을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="b6548-124">In the list of devices, click an iOS or Android device, and then click the **Remote lock** action.</span></span>

    
<span data-ttu-id="b6548-125">원격으로 암호를 초기화하려면:</span><span class="sxs-lookup"><span data-stu-id="b6548-125">To reset the passcode remotely:</span></span>

1. <span data-ttu-id="b6548-126">필요한 경우에서 Azure 포털에 로그인 [https://portal.azure.com](https://portal.azure.com) 전역 관리자 계정의 자격 증명을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="b6548-126">If needed, sign in to the Azure portal at [https://portal.azure.com](https://portal.azure.com) with the credentials of your global administrator account.</span></span>
2. <span data-ttu-id="b6548-127">**모든 서비스**를 클릭 하 고 **Intune**입력 다음 **Intune**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="b6548-127">Click **All services**, type **Intune**, and then click **Intune**.</span></span>
3. <span data-ttu-id="b6548-128">클릭 **장치 > 모든 장치**합니다.</span><span class="sxs-lookup"><span data-stu-id="b6548-128">Click **Devices > All devices**.</span></span>
4. <span data-ttu-id="b6548-p103">관리 장치 목록에서는 iOS 또는 Android 장치를 클릭 한 **선택... 더 많은**합니다. 다음 **암호를 제거** 장치 원격 작업을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="b6548-p103">From the list of devices you manage, click an iOS or Android device, and choose **...More**. Then choose the **Remove passcode** device remote action.</span></span>

<span data-ttu-id="b6548-131">추가 실험 [사용 가능한 장치에 작업](https://docs.microsoft.com/intune/device-management#available-device-actions)을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="b6548-131">For additional experimentation, see [Available device actions](https://docs.microsoft.com/intune/device-management#available-device-actions).</span></span>

    
## <a name="next-step"></a><span data-ttu-id="b6548-132">다음 단계</span><span class="sxs-lookup"><span data-stu-id="b6548-132">Next step</span></span>

<span data-ttu-id="b6548-133">테스트 환경의 [모바일 장치 관리](m365-enterprise-test-lab-guides.md#mobile-device-management) 추가 기능 및 특징을 살펴봅니다.</span><span class="sxs-lookup"><span data-stu-id="b6548-133">Explore additional [mobile device management](m365-enterprise-test-lab-guides.md#mobile-device-management) features and capabilities in your test environment.</span></span>

## <a name="see-also"></a><span data-ttu-id="b6548-134">참고 항목</span><span class="sxs-lookup"><span data-stu-id="b6548-134">See Also</span></span>

[<span data-ttu-id="b6548-135">Microsoft 365 Enterprise 테스트 랩 가이드</span><span class="sxs-lookup"><span data-stu-id="b6548-135">Microsoft 365 Enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)
  
[<span data-ttu-id="b6548-136">Microsoft 365 Enterprise 테스트 환경용 MAM 정책</span><span class="sxs-lookup"><span data-stu-id="b6548-136">MAM policies for your Microsoft 365 Enterprise test environment</span></span>](mam-policies-for-your-microsoft-365-enterprise-dev-test-environment.md)
  
[<span data-ttu-id="b6548-137">Microsoft 365 Enterprise 배포</span><span class="sxs-lookup"><span data-stu-id="b6548-137">Deploy Microsoft 365 Enterprise</span></span>](deploy-microsoft-365-enterprise.md)

[<span data-ttu-id="b6548-138">엔터프라이즈 이동성 + 보안 (EMS)</span><span class="sxs-lookup"><span data-stu-id="b6548-138">Enterprise Mobility + Security (EMS)</span></span>](https://www.microsoft.com/cloud-platform/enterprise-mobility-security)
