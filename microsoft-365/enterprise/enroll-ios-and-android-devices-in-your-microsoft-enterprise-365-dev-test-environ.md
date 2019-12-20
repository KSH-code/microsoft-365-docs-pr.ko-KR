---
title: Microsoft 365 Enterprise 테스트 환경에서 iOS 및 Android 장치 등록
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
ms.openlocfilehash: 98670e64045b36dcdafb46c6ff798b8be7fd6dc1
ms.sourcegitcommit: 0ad0092d9c5cb2d69fc70c990a9b7cc03140611b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/19/2019
ms.locfileid: "40801873"
---
# <a name="enroll-ios-and-android-devices-in-your-microsoft-365-enterprise-test-environment"></a><span data-ttu-id="99693-103">Microsoft 365 Enterprise 테스트 환경에서 iOS 및 Android 장치 등록</span><span class="sxs-lookup"><span data-stu-id="99693-103">Enroll iOS and Android devices in your Microsoft 365 Enterprise test environment</span></span>

<span data-ttu-id="99693-104">*이 테스트 랩 가이드는 Microsoft 365 Enterprise 테스트 환경에만 사용할 수 있습니다.*</span><span class="sxs-lookup"><span data-stu-id="99693-104">*This Test Lab Guide can only be used for Microsoft 365 Enterprise test environments.*</span></span>

<span data-ttu-id="99693-105">이 문서에 나와 있는 지침을 수행 하 여 Microsoft 365 Enterprise 테스트 환경에서 iOS 및 Android 장치에 대 한 기본 모바일 장치 관리 기능을 등록 하 고 테스트할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="99693-105">By following the instructions provided in this article, you'll be able to enroll and test basic mobile device management capabilities for iOS and Android devices in your Microsoft 365 Enterprise test environment.</span></span>

![Microsoft 클라우드의 테스트 랩 가이드](media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png)
  
> [!TIP]
> <span data-ttu-id="99693-107">[여기](media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf)를 클릭하여 Microsoft 365 Enterprise 테스트 랩 가이드 스택의 모든 문서에 대한 가상 맵을 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="99693-107">Click [here](media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf) for a visual map to all the articles in the Microsoft 365 Enterprise Test Lab Guide stack.</span></span>

## <a name="phase-1-build-out-your-microsoft-365-enterprise-test-environment"></a><span data-ttu-id="99693-108">1단계: Microsoft 365 Enterprise 테스트 환경 구축</span><span class="sxs-lookup"><span data-stu-id="99693-108">Phase 1: Build out your Microsoft 365 Enterprise test environment</span></span>

<span data-ttu-id="99693-109">최소 요구 사항에 따라 간단한 방식으로 iOS 및 Android 장치를 등록 하려는 경우에는 [간단한 기본 구성](lightweight-base-configuration-microsoft-365-enterprise.md)의 지침을 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="99693-109">If you just want to enroll iOS and Android devices in a lightweight way with the minimum requirements, follow the instructions in [Lightweight base configuration](lightweight-base-configuration-microsoft-365-enterprise.md).</span></span>
  
<span data-ttu-id="99693-110">시뮬레이트된 엔터프라이즈에서 iOS 및 Android 장치를 등록 하려면 [통과 인증](pass-through-auth-m365-ent-test-environment.md)의 지침을 따르세요.</span><span class="sxs-lookup"><span data-stu-id="99693-110">If you want to enroll iOS and Android devices in a simulated enterprise, follow the instructions in [Pass-through authentication](pass-through-auth-m365-ent-test-environment.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="99693-111">자동 라이선싱 및 그룹 구성원을 테스트 하는 경우에는 AD DS (Active Directory 도메인 서비스) 포리스트의 인터넷 및 디렉터리 동기화에 연결 된 시뮬레이트된 인트라넷을 포함 하는 시뮬레이트된 엔터프라이즈 테스트 환경이 필요 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="99693-111">Testing automated licensing and group membership does not require the simulated enterprise test environment, which includes a simulated intranet connected to the Internet and directory synchronization for an Active Directory Domain Services (AD DS) forest.</span></span> <span data-ttu-id="99693-112">이 기능은 자동 라이선스 및 그룹 구성원을 테스트 하 고 일반적인 조직을 나타내는 환경에서 테스트할 수 있도록 옵션으로 제공 됩니다.</span><span class="sxs-lookup"><span data-stu-id="99693-112">It is provided here as an option so that you can test automated licensing and group membership and experiment with it in an environment that represents a typical organization.</span></span> 
>  

## <a name="phase-2-enroll-your-ios-and-android-devices"></a><span data-ttu-id="99693-113">2 단계: iOS 및 Android 장치 등록</span><span class="sxs-lookup"><span data-stu-id="99693-113">Phase 2: Enroll your iOS and Android devices</span></span>

<span data-ttu-id="99693-114">먼저 Install (설치)의 지침을 사용 하 여 테스트 환경에 대 한 Microsoft Intune 회사 포털 앱을 사용자 지정 하 [고 회사 포털 앱에 로그인](https://docs.microsoft.com/intune-user-help/install-and-sign-in-to-the-intune-company-portal-app-ios) 합니다.</span><span class="sxs-lookup"><span data-stu-id="99693-114">First, use the instructions in [Install and sign in to the Company Portal app](https://docs.microsoft.com/intune-user-help/install-and-sign-in-to-the-intune-company-portal-app-ios) to customize the Microsoft Intune Company Portal app for your test environment.</span></span>

<span data-ttu-id="99693-115">그런 다음 [회사 리소스에 대 한 액세스 설정](https://docs.microsoft.com/intune-user-help/enroll-your-device-in-intune-ios) 의 지침을 사용 하 여 iOS 장치를 등록 합니다.</span><span class="sxs-lookup"><span data-stu-id="99693-115">Next, use the instructions in [Set up access to your company resources](https://docs.microsoft.com/intune-user-help/enroll-your-device-in-intune-ios) to enroll an iOS device.</span></span>

<span data-ttu-id="99693-116">다음으로, [Intune에서 android 장치 등록](https://docs.microsoft.com/intune-user-help/enroll-your-device-in-intune-android) 의 지침을 사용 하 여 android 장치를 등록 합니다.</span><span class="sxs-lookup"><span data-stu-id="99693-116">Next, use the instructions in [Enroll your Android device in Intune](https://docs.microsoft.com/intune-user-help/enroll-your-device-in-intune-android) to enroll an Android device.</span></span>

## <a name="phase-3-manage-your-ios-and-android-devices-remotely"></a><span data-ttu-id="99693-117">3 단계: 원격으로 iOS 및 Android 장치 관리</span><span class="sxs-lookup"><span data-stu-id="99693-117">Phase 3: Manage your iOS and Android devices remotely</span></span>

<span data-ttu-id="99693-118">Microsoft Intune에서는 원격 잠금 및 암호 초기화 기능을 모두 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="99693-118">Microsoft Intune provides both remote lock and passcode reset capabilities.</span></span> <span data-ttu-id="99693-119">장치를 분실한 경우 원격으로 장치를 잠글 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="99693-119">If someone loses their device, you can lock the device remotely.</span></span> <span data-ttu-id="99693-120">다른 사용자가 암호를 잊어버린 경우 원격으로 다시 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="99693-120">If someone forgets their passcode, you can reset it remotely.</span></span>
  
<span data-ttu-id="99693-121">원격으로 iOS 또는 Android 장치를 잠그려면:</span><span class="sxs-lookup"><span data-stu-id="99693-121">To lock an iOS or Android device remotely:</span></span>

1. <span data-ttu-id="99693-122">전역 관리자 계정의 자격 증명을 [https://portal.azure.com](https://portal.azure.com) 사용 하 여 Azure portal에 로그인 합니다.</span><span class="sxs-lookup"><span data-stu-id="99693-122">Sign in to the Azure portal at [https://portal.azure.com](https://portal.azure.com) with the credentials of your global administrator account.</span></span>
2. <span data-ttu-id="99693-123">브라우저의 Azure portal 탭에 있는 검색 상자에 **intune** 을 입력 한 다음 **intune**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="99693-123">On the Azure portal tab in your browser, type **Intune** in the search box, and then click **Intune**.</span></span>
3. <span data-ttu-id="99693-124">**모든 장치 > 장치**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="99693-124">Click **Devices > All devices**.</span></span>
4. <span data-ttu-id="99693-125">장치 목록에서 iOS 또는 Android 장치를 클릭 한 다음 **원격 잠금** 작업을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="99693-125">In the list of devices, click an iOS or Android device, and then click the **Remote lock** action.</span></span>

    
<span data-ttu-id="99693-126">원격으로 암호를 초기화하려면:</span><span class="sxs-lookup"><span data-stu-id="99693-126">To reset the passcode remotely:</span></span>

1. <span data-ttu-id="99693-127">필요한 경우 전역 관리자 계정의 자격 증명을 [https://portal.azure.com](https://portal.azure.com) 사용 하 여 Azure portal에 로그인 합니다.</span><span class="sxs-lookup"><span data-stu-id="99693-127">If needed, sign in to the Azure portal at [https://portal.azure.com](https://portal.azure.com) with the credentials of your global administrator account.</span></span>
2. <span data-ttu-id="99693-128">브라우저의 Azure portal 탭에 있는 검색 상자에 **intune** 을 입력 한 다음 **intune**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="99693-128">On the Azure portal tab in your browser, type **Intune** in the search box, and then click **Intune**.</span></span>
3. <span data-ttu-id="99693-129">**모든 장치 > 장치**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="99693-129">Click **Devices > All devices**.</span></span>
4. <span data-ttu-id="99693-130">관리 하는 장치 목록에서 iOS 또는 Android 장치를 클릭 하 고 ...를 선택 **합니다. 자세히**</span><span class="sxs-lookup"><span data-stu-id="99693-130">From the list of devices you manage, click an iOS or Android device, and choose **...More**.</span></span> <span data-ttu-id="99693-131">그런 다음 암호 장치 원격 작업 **제거** 를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="99693-131">Then choose the **Remove passcode** device remote action.</span></span>

<span data-ttu-id="99693-132">자세한 내용은 [사용 가능한 장치 작업](https://docs.microsoft.com/intune/device-management#available-device-actions)을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="99693-132">For additional experimentation, see [Available device actions](https://docs.microsoft.com/intune/device-management#available-device-actions).</span></span>

    
## <a name="next-step"></a><span data-ttu-id="99693-133">다음 단계</span><span class="sxs-lookup"><span data-stu-id="99693-133">Next step</span></span>

<span data-ttu-id="99693-134">테스트 환경에서 추가 [모바일 장치 관리](m365-enterprise-test-lab-guides.md#mobile-device-management) 기능을 알아봅니다.</span><span class="sxs-lookup"><span data-stu-id="99693-134">Explore additional [mobile device management](m365-enterprise-test-lab-guides.md#mobile-device-management) features and capabilities in your test environment.</span></span>

## <a name="see-also"></a><span data-ttu-id="99693-135">참고 항목</span><span class="sxs-lookup"><span data-stu-id="99693-135">See Also</span></span>

[<span data-ttu-id="99693-136">Microsoft 365 Enterprise 테스트 랩 가이드</span><span class="sxs-lookup"><span data-stu-id="99693-136">Microsoft 365 Enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)
  
[<span data-ttu-id="99693-137">Microsoft 365 Enterprise 테스트 환경에 대 한 장치 준수 정책</span><span class="sxs-lookup"><span data-stu-id="99693-137">Device compliance policies for your Microsoft 365 Enterprise test environment</span></span>](mam-policies-for-your-microsoft-365-enterprise-dev-test-environment.md)
  
[<span data-ttu-id="99693-138">Microsoft 365 Enterprise 배포</span><span class="sxs-lookup"><span data-stu-id="99693-138">Deploy Microsoft 365 Enterprise</span></span>](deploy-microsoft-365-enterprise.md)

