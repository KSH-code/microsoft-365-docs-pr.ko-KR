---
title: 엔터프라이즈 테스트 환경용 Microsoft 365에 대 한 장치 준수 정책
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
ms.assetid: 1aa9639b-2862-49c4-bc33-1586dda636b8
description: 이 테스트 랩 가이드를 사용 하 여 엔터프라이즈 테스트 환경용 Microsoft 365에 Intune 장치 준수 정책을 추가 합니다.
ms.openlocfilehash: c1de822e5a97416bd0c672d88f2902d8986638c8
ms.sourcegitcommit: 53ff1fe6d6143b0bf011031eea9b85dc01ae4f74
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48487415"
---
# <a name="device-compliance-policies-for-your-microsoft-365-for-enterprise-test-environment"></a><span data-ttu-id="4f779-103">엔터프라이즈 테스트 환경용 Microsoft 365에 대 한 장치 준수 정책</span><span class="sxs-lookup"><span data-stu-id="4f779-103">Device compliance policies for your Microsoft 365 for enterprise test environment</span></span>

<span data-ttu-id="4f779-104">*이 테스트 랩 가이드는 엔터프라이즈 테스트 환경용 Microsoft 365에만 사용할 수 있습니다.*</span><span class="sxs-lookup"><span data-stu-id="4f779-104">*This Test Lab Guide can only be used for Microsoft 365 for enterprise test environments.*</span></span>

<span data-ttu-id="4f779-105">이 문서에서는 Windows 10 장치에 대 한 Intune 장치 준수 정책을 추가 하는 방법과 엔터프라이즈 용 Microsoft 365 앱을 Microsoft 365 for 엔터프라이즈 테스트 환경에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="4f779-105">This article describes how to add an Intune device compliance policy for Windows 10 devices and Microsoft 365 Apps for enterprise to your Microsoft 365 for enterprise test environment.</span></span>

<span data-ttu-id="4f779-106">Intune 장치 준수 정책 추가에는 두 단계가 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4f779-106">Adding an Intune device compliance policy involves two phases:</span></span>
- [<span data-ttu-id="4f779-107">1 단계: 엔터프라이즈 테스트 환경용 Microsoft 365 구축</span><span class="sxs-lookup"><span data-stu-id="4f779-107">Phase 1: Build out your Microsoft 365 for enterprise test environment</span></span>](#phase-1-build-out-your-microsoft-365-for-enterprise-test-environment)
- [<span data-ttu-id="4f779-108">2 단계: Windows 10 장치에 대 한 장치 준수 정책 만들기</span><span class="sxs-lookup"><span data-stu-id="4f779-108">Phase 2: Create a device compliance policy for Windows 10 devices</span></span>](#phase-2-create-a-device-compliance-policy-for-windows-10-devices)

![Microsoft 클라우드의 테스트 랩 가이드](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png)

> [!TIP]
> <span data-ttu-id="4f779-110">엔터프라이즈 테스트 랩 가이드 스택의 Microsoft 365에 있는 모든 문서에 대 한 시각적 지도를 보려면 [microsoft 365 for 엔터프라이즈 테스트 랩 가이드 스택을](../downloads/Microsoft365EnterpriseTLGStack.pdf)방문 하세요.</span><span class="sxs-lookup"><span data-stu-id="4f779-110">For a visual map to all the articles in the Microsoft 365 for enterprise Test Lab Guide stack, go to [Microsoft 365 for enterprise Test Lab Guide Stack](../downloads/Microsoft365EnterpriseTLGStack.pdf).</span></span>

## <a name="phase-1-build-out-your-microsoft-365-for-enterprise-test-environment"></a><span data-ttu-id="4f779-111">1 단계: 엔터프라이즈 테스트 환경용 Microsoft 365 구축</span><span class="sxs-lookup"><span data-stu-id="4f779-111">Phase 1: Build out your Microsoft 365 for enterprise test environment</span></span>

<span data-ttu-id="4f779-112">최소 요구 사항과 함께 간단한 방식 으로만 MAM 정책을 구성 하려면 [간단한 기본 구성](lightweight-base-configuration-microsoft-365-enterprise.md)의 지침을 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="4f779-112">If you want to configure MAM policies in only a lightweight way with the minimum requirements, follow the instructions in [Lightweight base configuration](lightweight-base-configuration-microsoft-365-enterprise.md).</span></span>
  
<span data-ttu-id="4f779-113">시뮬레이트된 엔터프라이즈에서 MAM 정책을 구성 하려면 [통과 인증](pass-through-auth-m365-ent-test-environment.md)의 지침을 따르세요.</span><span class="sxs-lookup"><span data-stu-id="4f779-113">If you want to configure MAM policies in a simulated enterprise, follow the instructions in [Pass-through authentication](pass-through-auth-m365-ent-test-environment.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="4f779-114">자동 라이선싱 및 그룹 구성원을 테스트 하려면 AD DS (Active Directory 도메인 서비스) 포리스트의 인터넷 및 디렉터리 동기화에 연결 된 시뮬레이트된 인트라넷을 포함 하는 시뮬레이트된 엔터프라이즈 테스트 환경이 필요 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="4f779-114">Testing automated licensing and group membership doesn't require the simulated enterprise test environment, which includes a simulated intranet connected to the internet and directory synchronization for an Active Directory Domain Services (AD DS) forest.</span></span> <span data-ttu-id="4f779-115">자동 라이선스 및 그룹 구성원을 테스트 하 고 일반적인 조직을 나타내는 환경에서 테스트해 볼 수 있도록 여기에서 옵션으로 제공 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4f779-115">It's provided here as an option so that you can test automated licensing and group membership and experiment with it in an environment that represents a typical organization.</span></span>
>  

## <a name="phase-2-create-a-device-compliance-policy-for-windows-10-devices"></a><span data-ttu-id="4f779-116">2 단계: Windows 10 장치에 대 한 장치 준수 정책 만들기</span><span class="sxs-lookup"><span data-stu-id="4f779-116">Phase 2: Create a device compliance policy for Windows 10 devices</span></span>

<span data-ttu-id="4f779-117">이 단계에서는 Windows 10 장치에 대 한 장치 준수 정책을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="4f779-117">In this phase, create a device compliance policy for Windows 10 devices.</span></span>
  
1. <span data-ttu-id="4f779-118">[Microsoft 365 관리 센터로](https://admin.microsoft.com) 이동 하 여 전역 관리자 계정을 사용 하 여 microsoft 365 테스트 랩 구독에 로그인 합니다.</span><span class="sxs-lookup"><span data-stu-id="4f779-118">Go to the [Microsoft 365 admin center](https://admin.microsoft.com) and sign in to your Microsoft 365 test lab subscription with your global administrator account.</span></span>
1. <span data-ttu-id="4f779-119">브라우저의 새 탭에서 Azure portal ()을 엽니다 [https://portal.azure.com](https://portal.azure.com) .</span><span class="sxs-lookup"><span data-stu-id="4f779-119">On a new tab of your browser, open the Azure portal at [https://portal.azure.com](https://portal.azure.com).</span></span>
1. <span data-ttu-id="4f779-120">Azure portal의 검색 상자에 **intune**을 입력 하 고 **intune**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="4f779-120">In the search box of the Azure portal, enter **Intune**, and then select **Intune**.</span></span>
1. <span data-ttu-id="4f779-121">아직 **Microsoft Intune** 창에서 **장치 관리를 사용 하도록 설정 하지 않은** 경우에는 해당 메시지를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="4f779-121">If you see a **You haven't enabled device management yet** message in the **Microsoft Intune** pane, select it.</span></span> <span data-ttu-id="4f779-122">**모바일 장치 관리 기관** 창에서 **Intune MDM 기관을**선택 하 고 **선택을**선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="4f779-122">In the **Mobile Device Management authority** pane, select **Intune MDM Authority**, and then select **Choose**.</span></span>
1. <span data-ttu-id="4f779-123">브라우저 탭을 새로 고칩니다.</span><span class="sxs-lookup"><span data-stu-id="4f779-123">Refresh your browser tab.</span></span>
1. <span data-ttu-id="4f779-124">왼쪽 탐색 창에서 **그룹**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="4f779-124">In the left navigation pane, select **Groups**.</span></span>
1. <span data-ttu-id="4f779-125">**그룹-모든 그룹** 창에서 **+ 새 그룹**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="4f779-125">In the **Groups-All groups** pane, select **+ New Group**.</span></span>
1. <span data-ttu-id="4f779-126">**그룹** 창에서 **Microsoft 365** 또는 **그룹 유형** **보안** 을 선택 하 고 **이름**에 **관리 되는 Windows 10 장치 사용자** 를 입력 한 다음 **멤버 자격 유형에**서 **할당** 을 선택 하 고 **만들기**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="4f779-126">In the **Group** pane, select **Microsoft 365** or **Security** for **Group type?**, enter **Managed Windows 10 device users** in **Name**, select **Assigned** in **Membership type**,  and then select **Create**.</span></span>
1. <span data-ttu-id="4f779-127">**Microsoft Intune**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="4f779-127">Select **Microsoft Intune**.</span></span>
1. <span data-ttu-id="4f779-128">**Microsoft Intune** 창의 **빠른 작업** 목록에서 **준수 정책 만들기**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="4f779-128">In the **Microsoft Intune** pane, in the **Quick tasks** list, select **Create a compliance policy**.</span></span>
1. <span data-ttu-id="4f779-129">**준수 정책 프로필** 창에서 **정책 만들기**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="4f779-129">In the **Compliance Policy Profiles** pane, select **Create Policy**.</span></span>
1. <span data-ttu-id="4f779-130">**정책 만들기** 창의 **이름**에 **Windows 10**을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="4f779-130">In the **Create Policy** pane, in **Name**, enter **Windows 10**.</span></span> <span data-ttu-id="4f779-131">**플랫폼**에서 **windows 10 이상 버전**을 선택 하 고 **windows 10 준수 정책** 창에서 **확인** 을 선택한 다음 **만들기**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="4f779-131">In **Platform**, select **Windows 10 and later**, select **OK** in the **Windows 10 compliance policy** pane, and then select **Create**.</span></span>
1. <span data-ttu-id="4f779-132">**준수 정책 프로필**을 선택한 다음 **Windows 10** 정책 이름을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="4f779-132">Select **Compliance Policy Profiles**, and then select the **Windows 10** policy name.</span></span>
1. <span data-ttu-id="4f779-133">**Windows 10** 창에서 **할당**을 선택 하 고 **포함할 그룹 선택을**선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="4f779-133">In the **Windows 10** pane, select **Assignments**, and then select **Select groups to include**.</span></span>
1. <span data-ttu-id="4f779-134">**포함할 그룹 선택** 창에서 **관리 되는 Windows 10 장치 사용자** 그룹을 선택한 다음 **선택을**선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="4f779-134">In the **Select groups to include** pane, select the **Managed Windows 10 device users** group, and then select **Select**.</span></span>
1. <span data-ttu-id="4f779-135">**저장**을 선택 하 고 **Microsoft Intune-개요**를 선택한 다음 왼쪽 탐색 창에서 **클라이언트 앱** 을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="4f779-135">Select **Save**, select **Microsoft Intune-Overview**, and then select **Client apps** in the left navigation.</span></span>
1. <span data-ttu-id="4f779-136">**클라이언트 앱** 창에서 **앱**을 선택 하 고 **추가**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="4f779-136">In the **Client Apps** pane, select **Apps**, and then select **Add**.</span></span>
1. <span data-ttu-id="4f779-137">**앱 추가** 창에서 **앱 종류**를 선택한 다음 **Microsoft 365 제품군**에서 **Windows 10** 을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="4f779-137">In the **Add app** pane, select **App type**, and then select **Windows 10** under **Microsoft 365 Suite**.</span></span>
1. <span data-ttu-id="4f779-138">**앱 추가** 창에서 **앱 제품군 정보**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="4f779-138">In the **Add App** pane, select **App Suite Information**.</span></span>
1. <span data-ttu-id="4f779-139">**앱 제품군 정보** 창에서 **제품군 이름과** **제품군 설명**모두에 **Microsoft 365 Apps for enterprise** 를 입력 한 다음 **확인**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="4f779-139">In the **App Suite Information** pane, enter **Microsoft 365 Apps for enterprise** in both **Suite Name** and **Suite Description**, and then select **OK**.</span></span>
1. <span data-ttu-id="4f779-140">**앱 추가** 창에서 **앱 제품군 구성을**선택 하 고 **확인**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="4f779-140">In the **Add App** pane, select **Configure App Suite**, and then select **OK**.</span></span>
1. <span data-ttu-id="4f779-141">**앱 추가** 창에서 **앱 제품군 설정을**선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="4f779-141">In the **Add App** pane, select **App Suite Settings**.</span></span>
1. <span data-ttu-id="4f779-142">**업데이트 채널**의 경우 **반기 엔터프라이즈**를 선택 하 고 **확인**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="4f779-142">For **Update Channel**, select **Semi-Annual Enterprise**, and then select **OK**.</span></span>
1. <span data-ttu-id="4f779-143">**앱 추가** 창에서 **추가**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="4f779-143">In the **Add app** pane, select **Add**.</span></span>

<span data-ttu-id="4f779-144">이제 **windows 10** 장치 준수 정책 및 **관리 되는 Windows 10 장치 사용자** 그룹의 구성원에 대해 선택한 앱을 테스트할 수 있는 장치 준수 정책이 만들어졌습니다.</span><span class="sxs-lookup"><span data-stu-id="4f779-144">You now have a device compliance policy for testing the selected apps in the **Windows 10** device compliance policy and for members of the **Managed Windows 10 device users** group.</span></span> <span data-ttu-id="4f779-145">그룹 종류로 **Microsoft 365** 을 선택 하면 추가 리소스가 생성 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4f779-145">Please note that selecting **Microsoft 365** as the group type creates additional resources.</span></span>
  
## <a name="next-step"></a><span data-ttu-id="4f779-146">다음 단계</span><span class="sxs-lookup"><span data-stu-id="4f779-146">Next step</span></span>

<span data-ttu-id="4f779-147">테스트 환경에서 추가 [모바일 장치 관리](m365-enterprise-test-lab-guides.md#mobile-device-management) 기능을 알아봅니다.</span><span class="sxs-lookup"><span data-stu-id="4f779-147">Explore additional [mobile device management](m365-enterprise-test-lab-guides.md#mobile-device-management) features and capabilities in your test environment.</span></span>

## <a name="see-also"></a><span data-ttu-id="4f779-148">참고 항목</span><span class="sxs-lookup"><span data-stu-id="4f779-148">See also</span></span>

<span data-ttu-id="4f779-149">[엔터프라이즈 테스트 랩 가이드에 대 한 Microsoft 365](m365-enterprise-test-lab-guides.md)</span><span class="sxs-lookup"><span data-stu-id="4f779-149">[Microsoft 365 for enterprise Test Lab Guides](m365-enterprise-test-lab-guides.md).</span></span>
  
[<span data-ttu-id="4f779-150">Microsoft 365에서 엔터프라이즈 테스트 환경용 iOS 및 Android 장치 등록</span><span class="sxs-lookup"><span data-stu-id="4f779-150">Enroll iOS and Android devices in your Microsoft 365 for enterprise test environment</span></span>](enroll-ios-and-android-devices-in-your-microsoft-enterprise-365-dev-test-environ.md)
  
[<span data-ttu-id="4f779-151">엔터프라이즈용 Microsoft 365 개요</span><span class="sxs-lookup"><span data-stu-id="4f779-151">Microsoft 365 for enterprise overview</span></span>](microsoft-365-overview.md)

[<span data-ttu-id="4f779-152">Enterprise Mobility + Security(EMS)</span><span class="sxs-lookup"><span data-stu-id="4f779-152">Enterprise Mobility + Security (EMS)</span></span>](https://www.microsoft.com/cloud-platform/enterprise-mobility-security)
