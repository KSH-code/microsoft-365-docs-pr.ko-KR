---
title: 엔터프라이즈용 Microsoft 365 테스트 환경에 대한 장치 준수 정책
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
ms.assetid: 1aa9639b-2862-49c4-bc33-1586dda636b8
description: 이 테스트 랩 가이드를 사용하여 엔터프라이즈용 Microsoft 365 테스트 환경에 Intune 장치 준수 정책을 추가합니다.
ms.openlocfilehash: d42c9a603ca581941cb5a8f30b9ecd9d6f780759
ms.sourcegitcommit: 001e64f89f9c3cd6bbd4a25459f5bee3b966820c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/20/2020
ms.locfileid: "49367098"
---
# <a name="device-compliance-policies-for-your-microsoft-365-for-enterprise-test-environment"></a><span data-ttu-id="b55ea-103">엔터프라이즈용 Microsoft 365 테스트 환경에 대한 장치 준수 정책</span><span class="sxs-lookup"><span data-stu-id="b55ea-103">Device compliance policies for your Microsoft 365 for enterprise test environment</span></span>

<span data-ttu-id="b55ea-104">*이 테스트 랩 가이드는 엔터프라이즈용 Microsoft 365 테스트 환경에만 사용할 수 있습니다.*</span><span class="sxs-lookup"><span data-stu-id="b55ea-104">*This Test Lab Guide can only be used for Microsoft 365 for enterprise test environments.*</span></span>

<span data-ttu-id="b55ea-105">이 문서에서는 Windows 10 장치 및 엔터프라이즈용 Microsoft 365 앱에 대한 Intune 장치 준수 정책을 엔터프라이즈용 Microsoft 365 테스트 환경에 추가하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="b55ea-105">This article describes how to add an Intune device compliance policy for Windows 10 devices and Microsoft 365 Apps for enterprise to your Microsoft 365 for enterprise test environment.</span></span>

<span data-ttu-id="b55ea-106">Intune 장치 준수 정책을 추가하는 데는 다음 두 단계가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b55ea-106">Adding an Intune device compliance policy involves two phases:</span></span>
- [<span data-ttu-id="b55ea-107">1단계: 엔터프라이즈용 Microsoft 365 테스트 환경 구축</span><span class="sxs-lookup"><span data-stu-id="b55ea-107">Phase 1: Build out your Microsoft 365 for enterprise test environment</span></span>](#phase-1-build-out-your-microsoft-365-for-enterprise-test-environment)
- [<span data-ttu-id="b55ea-108">2단계: Windows 10 장치에 대한 장치 준수 정책 만들기</span><span class="sxs-lookup"><span data-stu-id="b55ea-108">Phase 2: Create a device compliance policy for Windows 10 devices</span></span>](#phase-2-create-a-device-compliance-policy-for-windows-10-devices)

![Microsoft 클라우드의 테스트 랩 가이드](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png)

> [!TIP]
> <span data-ttu-id="b55ea-110">엔터프라이즈용 Microsoft 365 테스트 랩 가이드 스택의 모든 문서에 대한 시각적 맵은 [엔터프라이즈용 Microsoft 365](../downloads/Microsoft365EnterpriseTLGStack.pdf)테스트 랩 가이드 스택으로 이동하세요.</span><span class="sxs-lookup"><span data-stu-id="b55ea-110">For a visual map to all the articles in the Microsoft 365 for enterprise Test Lab Guide stack, go to [Microsoft 365 for enterprise Test Lab Guide Stack](../downloads/Microsoft365EnterpriseTLGStack.pdf).</span></span>

## <a name="phase-1-build-out-your-microsoft-365-for-enterprise-test-environment"></a><span data-ttu-id="b55ea-111">1단계: 엔터프라이즈용 Microsoft 365 테스트 환경 구축</span><span class="sxs-lookup"><span data-stu-id="b55ea-111">Phase 1: Build out your Microsoft 365 for enterprise test environment</span></span>

<span data-ttu-id="b55ea-112">최소 요구 사항을 충족하는 간단한 방식으로만 MAM 정책을 구성하려면 Lightweight base configuration의 지침을 [따르세요.](lightweight-base-configuration-microsoft-365-enterprise.md)</span><span class="sxs-lookup"><span data-stu-id="b55ea-112">If you want to configure MAM policies in only a lightweight way with the minimum requirements, follow the instructions in [Lightweight base configuration](lightweight-base-configuration-microsoft-365-enterprise.md).</span></span>
  
<span data-ttu-id="b55ea-113">시뮬레이트된 엔터프라이즈에서 MAM 정책을 구성하려는 경우 통과 인증의 [지침을 따릅니다.](pass-through-auth-m365-ent-test-environment.md)</span><span class="sxs-lookup"><span data-stu-id="b55ea-113">If you want to configure MAM policies in a simulated enterprise, follow the instructions in [Pass-through authentication](pass-through-auth-m365-ent-test-environment.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="b55ea-114">자동화된 라이선스 및 그룹 멤버 자격을 테스트하는 데는 시뮬레이트된 엔터프라이즈 테스트 환경이 필요하지 않습니다. 여기에는 인터넷에 연결된 시뮬레이트된 인트라넷과 AD DS(Active Directory 도메인 서비스) 포리스트에 대한 디렉터리 동기화가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="b55ea-114">Testing automated licensing and group membership doesn't require the simulated enterprise test environment, which includes a simulated intranet connected to the internet and directory synchronization for an Active Directory Domain Services (AD DS) forest.</span></span> <span data-ttu-id="b55ea-115">여기에서는 자동화된 라이선스 및 그룹 멤버십을 테스트하고 일반적인 조직을 나타내는 환경에서 실험할 수 있도록 옵션으로 제공됩니다.</span><span class="sxs-lookup"><span data-stu-id="b55ea-115">It's provided here as an option so that you can test automated licensing and group membership and experiment with it in an environment that represents a typical organization.</span></span>
>  

## <a name="phase-2-create-a-device-compliance-policy-for-windows-10-devices"></a><span data-ttu-id="b55ea-116">2단계: Windows 10 장치에 대한 장치 준수 정책 만들기</span><span class="sxs-lookup"><span data-stu-id="b55ea-116">Phase 2: Create a device compliance policy for Windows 10 devices</span></span>

<span data-ttu-id="b55ea-117">이 단계에서는 Windows 10 장치에 대한 장치 준수 정책을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="b55ea-117">In this phase, you create a device compliance policy for Windows 10 devices.</span></span> <span data-ttu-id="b55ea-118">이 단계에서는 Microsoft Intune 및 [Microsoft Endpoint Manager](https://go.microsoft.com/fwlink/?linkid=2109431) 관리 센터를 사용하여 그룹을 추가하고 준수 정책을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="b55ea-118">This phase uses Microsoft Intune and the [Microsoft Endpoint Manager admin center](https://go.microsoft.com/fwlink/?linkid=2109431) to add a group, and create a compliance policy.</span></span>

1. <span data-ttu-id="b55ea-119">[Microsoft 365](https://admin.microsoft.com)관리 센터로 이동한 후 전역 관리자 계정으로 Microsoft 365 테스트 랩 구독에 로그인합니다.</span><span class="sxs-lookup"><span data-stu-id="b55ea-119">Go to the [Microsoft 365 admin center](https://admin.microsoft.com), and sign in to your Microsoft 365 test lab subscription with your global administrator account.</span></span> <span data-ttu-id="b55ea-120">**끝점 관리자 관리 센터를** 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="b55ea-120">Select the **Endpoint Manager** admin center.</span></span> <span data-ttu-id="b55ea-121">끝점 [관리자 관리 센터가](https://go.microsoft.com/fwlink/?linkid=2109431) 열립니다.</span><span class="sxs-lookup"><span data-stu-id="b55ea-121">The [Endpoint Manager admin center](https://go.microsoft.com/fwlink/?linkid=2109431) opens.</span></span>

    <span data-ttu-id="b55ea-122">장치 관리를 사용하도록  설정하지 않은 메시지와 유사한 메시지가 표시되면 MDM 기관으로 Intune을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="b55ea-122">If a message similar to **You haven't enabled device management yet** message is shown, then select Intune as the MDM authority.</span></span> <span data-ttu-id="b55ea-123">특정 단계는 모바일 장치 관리 [기관 설정을 참조하세요.](/mem/intune/fundamentals/mdm-authority-set)</span><span class="sxs-lookup"><span data-stu-id="b55ea-123">For the specific steps, see [Set the mobile device management authority](/mem/intune/fundamentals/mdm-authority-set).</span></span>

    <span data-ttu-id="b55ea-124">끝점 관리자 관리 센터는 장치 관리 및 앱 관리에 중점을 니다.</span><span class="sxs-lookup"><span data-stu-id="b55ea-124">The Endpoint Manager admin center focuses on device management and app management.</span></span> <span data-ttu-id="b55ea-125">이 관리 센터를 둘러보는 방법에 대한 자세한 내용은 [자습서: Microsoft Endpoint Manager의 Intune Walkthrough Intune을 참조하세요.](/mem/intune/fundamentals/tutorial-walkthrough-endpoint-manager)</span><span class="sxs-lookup"><span data-stu-id="b55ea-125">For a tour of this admin center, see [Tutorial: Walkthrough Intune in Microsoft Endpoint Manager](/mem/intune/fundamentals/tutorial-walkthrough-endpoint-manager).</span></span>

2. <span data-ttu-id="b55ea-126">그룹에서 할당된 구성원 유형으로 관리되는 **Windows 10** 장치 사용자라는 새 **Microsoft 365** 또는 보안 **그룹을 추가합니다.**  </span><span class="sxs-lookup"><span data-stu-id="b55ea-126">In **Groups**, add a new **Microsoft 365** or **Security** group named **Managed Windows 10 device users**, with an **Assigned** membership type.</span></span> <span data-ttu-id="b55ea-127">다음 단계에서는 이 그룹에 규정 준수 정책을 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="b55ea-127">In the next steps, you'll assign your compliance policy to this group.</span></span> 

    <span data-ttu-id="b55ea-128">특정 단계 및 **Microsoft 365** 또는  보안 그룹에 대한 자세한 내용은 사용자 및 장치를 구성할 그룹 [추가를 참조하세요.](/mem/intune/fundamentals/groups-add)</span><span class="sxs-lookup"><span data-stu-id="b55ea-128">For the specific steps, and for information on **Microsoft 365** or **Security** groups, see [Add groups to organize users and devices](/mem/intune/fundamentals/groups-add).</span></span>

3. <span data-ttu-id="b55ea-129">**디바이스에서** Windows 10 준수 정책을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="b55ea-129">In **Devices**, create a Windows 10 compliance policy.</span></span> <span data-ttu-id="b55ea-130">이 정책을 만든 **관리되는 Windows 10** 장치 사용자 그룹에 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="b55ea-130">Assign this policy to the **Managed Windows 10 device users** group you created.</span></span>

    <span data-ttu-id="b55ea-131">정책에서 간단한 암호를 차단하고, 방화벽을 요구하고, Microsoft Defender 맬웨어 방지 서비스를 실행해야 하는 등 다양한 방법을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b55ea-131">In your policy, you can block simple passwords, require a firewall, require the Microsoft Defender Antimalware service be running, and more.</span></span> <span data-ttu-id="b55ea-132">준수 정책에는 일반적으로 기본 설정 또는 모든 장치에 필요한 최소 설정이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="b55ea-132">A compliance policy typically includes the base settings, or bare minimum that every device should have.</span></span>

    <span data-ttu-id="b55ea-133">특정 단계 및 구성할 수 있는 사용 가능한 준수 설정에 대한 자세한 내용은 준수 정책을 사용하여 관리하는 장치에 대한 규칙을 [설정하세요.](/mem/intune/protect/device-compliance-get-started)</span><span class="sxs-lookup"><span data-stu-id="b55ea-133">For the specific steps, and for information on the available compliance settings you can configure, see [Use compliance policies to set rules for devices you manage](/mem/intune/protect/device-compliance-get-started).</span></span>

<span data-ttu-id="b55ea-134">완료되면 관리되는 **Windows 10** 장치 사용자 그룹에서 구성원을 테스트하기 위한 장치 준수 정책이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b55ea-134">When finished, you have a device compliance policy for testing members in the **Managed Windows 10 device users** group.</span></span>
  
## <a name="next-step"></a><span data-ttu-id="b55ea-135">다음 단계</span><span class="sxs-lookup"><span data-stu-id="b55ea-135">Next step</span></span>

<span data-ttu-id="b55ea-136">테스트 환경에서 추가 [모바일](m365-enterprise-test-lab-guides.md#mobile-device-management) 장치 관리 기능을 살펴보아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b55ea-136">Explore additional [mobile device management](m365-enterprise-test-lab-guides.md#mobile-device-management) features and capabilities in your test environment.</span></span>

## <a name="see-also"></a><span data-ttu-id="b55ea-137">참고 항목</span><span class="sxs-lookup"><span data-stu-id="b55ea-137">See also</span></span>

<span data-ttu-id="b55ea-138">[엔터프라이즈용 Microsoft 365 테스트 랩 가이드.](m365-enterprise-test-lab-guides.md)</span><span class="sxs-lookup"><span data-stu-id="b55ea-138">[Microsoft 365 for enterprise Test Lab Guides](m365-enterprise-test-lab-guides.md).</span></span>
  
[<span data-ttu-id="b55ea-139">엔터프라이즈용 Microsoft 365 테스트 환경에 iOS 및 Android 장치 등록</span><span class="sxs-lookup"><span data-stu-id="b55ea-139">Enroll iOS and Android devices in your Microsoft 365 for enterprise test environment</span></span>](enroll-ios-and-android-devices-in-your-microsoft-enterprise-365-dev-test-environ.md)
  
[<span data-ttu-id="b55ea-140">엔터프라이즈용 Microsoft 365 개요</span><span class="sxs-lookup"><span data-stu-id="b55ea-140">Microsoft 365 for enterprise overview</span></span>](microsoft-365-overview.md)

[<span data-ttu-id="b55ea-141">Enterprise Mobility + Security(EMS)</span><span class="sxs-lookup"><span data-stu-id="b55ea-141">Enterprise Mobility + Security (EMS)</span></span>](https://www.microsoft.com/cloud-platform/enterprise-mobility-security)
