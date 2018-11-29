---
title: Microsoft 365 Enterprise 테스트 환경용 MAM 정책
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 09/16/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection: Ent_O365
ms.custom: Ent_TLGs
ms.assetid: 1aa9639b-2862-49c4-bc33-1586dda636b8
description: 이 테스트 랩 가이드를 사용 하 여 테스트 환경에 Microsoft 365 기업 Intune 모바일 응용 프로그램 관리 (MAM) 정책을 추가 합니다.
ms.openlocfilehash: f00379a5e70dce5e07c031a7647b27041d3fa9d1
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/28/2018
ms.locfileid: "26870348"
---
# <a name="mam-policies-for-your-microsoft-365-enterprise-test-environment"></a><span data-ttu-id="e8d09-103">Microsoft 365 Enterprise 테스트 환경용 MAM 정책</span><span class="sxs-lookup"><span data-stu-id="e8d09-103">MAM policies for your Microsoft 365 Enterprise test environment</span></span>

<span data-ttu-id="e8d09-104">이 문서의 지침을 테스트 환경에 Microsoft 365 기업 Intune 모바일 응용 프로그램 관리 (MAM) 정책을 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="e8d09-104">With the instructions in this article, you add Intune mobile application management (MAM) policies to your Microsoft 365 Enterprise test environment.</span></span>

![Microsoft 클라우드의 테스트 랩 가이드](media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png)

> [!TIP]
> <span data-ttu-id="e8d09-106">[여기](https://aka.ms/m365etlgstack)를 클릭하여 Microsoft 365 Enterprise 테스트 랩 가이드 스택의 모든 문서에 대한 가상 맵을 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e8d09-106">Click [here](https://aka.ms/m365etlgstack) for a visual map to all the articles in the Microsoft 365 Enterprise Test Lab Guide stack.</span></span>

## <a name="phase-1-build-out-your-microsoft-365-enterprise-test-environment"></a><span data-ttu-id="e8d09-107">1 단계: Microsoft 365 Enterprise 테스트 환경을 구축합니다</span><span class="sxs-lookup"><span data-stu-id="e8d09-107">Phase 1: Build out your Microsoft 365 Enterprise test environment</span></span>

<span data-ttu-id="e8d09-108">최소 요구 사항을 경량 방식으로 MAM 정책을 구성 하려면 [경량 기본 구성](lightweight-base-configuration-microsoft-365-enterprise.md)의 지시를 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="e8d09-108">If you just want to configure MAM policies in a lightweight way with the minimum requirements, follow the instructions in [Lightweight base configuration](lightweight-base-configuration-microsoft-365-enterprise.md).</span></span>
  
<span data-ttu-id="e8d09-109">시뮬레이션 된 엔터프라이즈에서 MAM 정책을 구성 하려는 경우 [통과 인증](pass-through-auth-m365-ent-test-environment.md)의 지시를 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="e8d09-109">If you want to configure MAM policies in a simulated enterprise, follow the instructions in [Pass-through authentication](pass-through-auth-m365-ent-test-environment.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="e8d09-p101">라이선스 하는 자동화 된 테스트 하 고 그룹 멤버 자격을 원하지 않는 인터넷에 연결 하는 시뮬레이션 된 인트라넷을 포함 하는 시뮬레이션 된 엔터프라이즈 테스트 환경 및 Windows Server AD 포리스트에 대 한 디렉터리 동기화 합니다. 제공는 자동화 된 라이선스 및 그룹 구성원 자격을 테스트 하 고 일반적인 조직을 대표 하는 환경에서 사용해 수 있도록 하는 옵션으로 여기 합니다.</span><span class="sxs-lookup"><span data-stu-id="e8d09-p101">Testing automated licensing and group membership does not require the simulated enterprise test environment, which includes a simulated intranet connected to the Internet and directory synchronization for a Windows Server AD forest. It is provided here as an option so that you can test automated licensing and group membership and experiment with it in an environment that represents a typical organization.</span></span> 
>  

## <a name="phase-2-create-and-deploy-mam-policies-for-ios-and-android-devices"></a><span data-ttu-id="e8d09-112">2단계: iOS 및 Android 장치용으로 MAM 정책 만들고 배포하기</span><span class="sxs-lookup"><span data-stu-id="e8d09-112">Phase 2: Create and deploy MAM policies for iOS and Android devices</span></span>

<span data-ttu-id="e8d09-113">이 단계에서는 두 개의 다른 MAM 정책을 만들고 배포할 수 있습니다. 하나는 iOS 장치용이며 하나는 Android 장치용입니다.</span><span class="sxs-lookup"><span data-stu-id="e8d09-113">In this phase, you create and deploy two different MAM policies: one for iOS devices and one for Android devices.</span></span>
  
1. <span data-ttu-id="e8d09-114">Office 365 포털에서 이동 ([https://portal.office.com](https://portal.office.com)) 전역 관리자 계정 사용 하 여 Office 365 평가판 구독에 로그인 합니다.</span><span class="sxs-lookup"><span data-stu-id="e8d09-114">Go to the Office 365 portal at ([https://portal.office.com](https://portal.office.com)) and sign in to your Office 365 trial subscription with your global administrator account.</span></span>
    
2. <span data-ttu-id="e8d09-115">브라우저의 새 탭에서 Azure 포털을 엽니다 [https://portal.azure.com](https://portal.azure.com)합니다.</span><span class="sxs-lookup"><span data-stu-id="e8d09-115">On a new tab of your browser, open the Azure portal at [https://portal.azure.com](https://portal.azure.com).</span></span>

3. <span data-ttu-id="e8d09-116">탐색 창에서 Internet Explorer에서 포털 Azure 탭에서 **모든 서비스**를 클릭 하 고 **Intune**입력 **Intune**를 클릭 한 다음 합니다.</span><span class="sxs-lookup"><span data-stu-id="e8d09-116">On the Azure portal tab in Internet Explorer, in the navigation pane, click **All services**, type **Intune**, and then click **Intune**.</span></span>
    
4. <span data-ttu-id="e8d09-p102">**Microsoft Intune** 블레이드에 **장치 관리 아직 활성화 하지 않은** 메시지를 표시 하는 경우이 클릭 합니다. **모바일 장치 관리 기관** 블레이드에서 **Intune MDM 기관**클릭 한 다음 **선택**을 클릭 합니다. 브라우저 탭을 새로 고칠 합니다.</span><span class="sxs-lookup"><span data-stu-id="e8d09-p102">If you see a **You haven't enabled device management yet** message on the **Microsoft Intune** blade, click it. On the **Mobile Device Management authority** blade, click **Intune MDM Authority**, and then click **Choose**. Refresh your browser tab.</span></span>
    
5. <span data-ttu-id="e8d09-120">왼쪽 탐색 창에서 **그룹**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="e8d09-120">In the left navigation pane, click **Groups**.</span></span>
    
6. <span data-ttu-id="e8d09-121">**그룹-모든 그룹** 블레이드에서 **+ 새 그룹을**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="e8d09-121">On the **Groups-All groups** blade, click **+ New Group**.</span></span>
    
7. <span data-ttu-id="e8d09-122">**그룹** 블레이드 선택에 대 한 **Office 365** **그룹 종류?**, **iOS 장치 사용자를 관리 되는** **이름**입력 **구성원 종류** **할당 됨** 을 선택 하 고 다음 **만들기**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="e8d09-122">On the **Group** blade, select **Office 365** for **Group type?**, type **Managed iOS device users** in **Name**, select **Assigned** in **Membership type**,  and then click **Create**.</span></span> 
    
8. <span data-ttu-id="e8d09-123">**그룹** 블레이드를 닫습니다.</span><span class="sxs-lookup"><span data-stu-id="e8d09-123">Close the **Group** blade.</span></span>
    
9. <span data-ttu-id="e8d09-124">**그룹-모든 그룹** 블레이드에서 **추가**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="e8d09-124">On the **Groups-All groups** blade, click **Add**.</span></span>
    
10. <span data-ttu-id="e8d09-125">**그룹** 블레이드 선택에 대 한 **Office 365** **그룹 종류?**, **Android 관리 되는 장치 사용자** **이름**입력 **구성원 종류** **할당 됨** 을 선택 하 고 **만들기**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="e8d09-125">On the **Group** blade, select **Office 365** for **Group type?**, type **Managed Android device user** in **Name**, select **Assigned** in **Membership type**,  and then click **Create**.</span></span>
    
11. <span data-ttu-id="e8d09-126">**그룹-모든 그룹** 블레이드를 닫습니다.</span><span class="sxs-lookup"><span data-stu-id="e8d09-126">Close the **Groups-All groups** blade.</span></span>
    
12. <span data-ttu-id="e8d09-127">**Intune** 블레이드의 **빠른 작업** 목록에서 **준수 정책 만들기**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="e8d09-127">On the **Intune** blade, in the **Quick tasks** list, click **Create a compliance policy**.</span></span>
    
13. <span data-ttu-id="e8d09-128">**준수 정책 프로필** 블레이드에서 **정책 만들기**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="e8d09-128">On the **Compliance Policy Profiles** blade, click **Create Policy**.</span></span>
    
14. <span data-ttu-id="e8d09-p103">**정책 만들기** 블레이드에서 **이름**에 **iOS**를 입력합니다. **플랫폼**에서 **iOS**를 선택하고 **iOS 준수 정책** 블레이드에서 **확인**을 클릭한 다음 **만들기**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="e8d09-p103">On the **Create Policy** blade, in **Name**, type **iOS**. In **Platform**, select **iOS**, click **OK** on the **iOS compliance policy** blade, and then click **Create**.</span></span>
    
15. <span data-ttu-id="e8d09-131">**준수 정책 프로필** 블레이드에서 **정책 만들기**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="e8d09-131">On the **Compliance Policy Profiles** blade, click **Create Policy**.</span></span>
    
16. <span data-ttu-id="e8d09-p104">**정책 만들기** 블레이드에서 **이름**에 **Android**를 입력합니다. **플랫폼**에서 **Android**를 선택하고 **Android 준수 정책** 블레이드에서 **확인**을 클릭한 다음 **만들기**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="e8d09-p104">On the **Create Policy** blade, in **Name**, type **Android**. In **Platform**, select **Android**, click **OK** on the **Android compliance policy** blade, and then click **Create**.</span></span>
    
17. <span data-ttu-id="e8d09-134">**준수 정책 프로필** 블레이드에서 **Android** 정책 이름을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="e8d09-134">On the **Compliance Policy Profiles** blade, click the **Android** policy name.</span></span>
    
18. <span data-ttu-id="e8d09-135">왼쪽 탐색 창의 **Android - 속성** 블레이드에서 **배정**을 클릭한 다음 **그룹 선택**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="e8d09-135">In the left navigation of the **Android - Properties** blade, click **Assignments**, and then click **Select groups**.</span></span>
    
19. <span data-ttu-id="e8d09-136">**그룹 선택** 블레이드에서 **관리 Android 장치 사용자** 그룹을 클릭한 다음 **선택**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="e8d09-136">On the **Select groups** blade, click the **Managed Android device users** group, and then click **Select**.</span></span>
    
20. <span data-ttu-id="e8d09-137">**저장**을 클릭 하 고 **Android-배정** 블레이드를 닫습니다.</span><span class="sxs-lookup"><span data-stu-id="e8d09-137">Click **Save**, and then close the **Android - Assignments** blade.</span></span>
    
21. <span data-ttu-id="e8d09-138">**준수 정책 프로필** 블레이드에서 **iOS** 정책 이름을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="e8d09-138">On the **Compliance Policy Profiles** blade, click the **iOS** policy name.</span></span>
    
22. <span data-ttu-id="e8d09-139">왼쪽 탐색 창의 **iOS - 속성** 블레이드에서 **배정**을 클릭한 다음 **그룹 선택**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="e8d09-139">In the left navigation of the **iOS - Properties** blade, click **Assignments**, and then click **Select groups**.</span></span>
    
23. <span data-ttu-id="e8d09-140">**그룹 선택** 블레이드에서 **관리 iOS 장치 사용자** 그룹을 클릭한 다음 **선택**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="e8d09-140">On the **Select groups** blade, click the **Managed iOS device users** group, and then click **Select**.</span></span>
    
24. <span data-ttu-id="e8d09-141">**저장**을 클릭 하 고 **iOS-배정** 블레이드를 닫습니다.</span><span class="sxs-lookup"><span data-stu-id="e8d09-141">Click **Save**, and then close the **iOS - Assignments** blade.</span></span>
    
25. <span data-ttu-id="e8d09-142">**준수 정책 프로필** 블레이드를 닫습니다.</span><span class="sxs-lookup"><span data-stu-id="e8d09-142">Close the **Compliance Policy Profiles** blade.</span></span>
    
26. <span data-ttu-id="e8d09-143">**Intune** 블레이드의 왼쪽 탐색 창에서 **앱 관리**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="e8d09-143">On the **Intune** blade, click **Manage apps** in the left navigation.</span></span>
    
27. <span data-ttu-id="e8d09-144">**모바일 앱** 블레이드에서 **앱**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="e8d09-144">On the **Mobile Apps** blade, click **Apps**.</span></span>
    
28. <span data-ttu-id="e8d09-145">앱 목록에서 **PowerPoint**를 클릭합니다. </span><span class="sxs-lookup"><span data-stu-id="e8d09-145">In the list of apps, click **PowerPoint**,</span></span> 
    
29. <span data-ttu-id="e8d09-p105">**PowerPoint 개요** 블레이드에서 **배정 > 그룹 선택 > 관리 iOS 장치 > 선택**을 클릭합니다. **유형**에서 **사용 가능**을 선택한 다음 **저장**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="e8d09-p105">On the **PowerPoint Overview** blade, click **Assignments > Select groups > Managed iOS devices > Select**. In **Type**, select **Available**, and then click **Save**.</span></span>
    
30. <span data-ttu-id="e8d09-148">다음 응용 프로그램에 대 한 29 단계를 반복 합니다.</span><span class="sxs-lookup"><span data-stu-id="e8d09-148">Repeat step 29 for the following apps:</span></span>
    
    - <span data-ttu-id="e8d09-149">Android용 Outlook</span><span class="sxs-lookup"><span data-stu-id="e8d09-149">Outlook for Android</span></span>
    
    - <span data-ttu-id="e8d09-150">iOS용 Word</span><span class="sxs-lookup"><span data-stu-id="e8d09-150">Word for iOS</span></span>
    
    - <span data-ttu-id="e8d09-151">IOS용 Excel</span><span class="sxs-lookup"><span data-stu-id="e8d09-151">Excel for iOS</span></span>
    
    - <span data-ttu-id="e8d09-152">iOS용 Outlook</span><span class="sxs-lookup"><span data-stu-id="e8d09-152">Outlook for iOS</span></span>
    
    - <span data-ttu-id="e8d09-153">iOS용 iPad의 Microsoft Dynamics CRM</span><span class="sxs-lookup"><span data-stu-id="e8d09-153">Microsoft Dynamics CRM on iPad for iOS</span></span>
    
    - <span data-ttu-id="e8d09-154">iOS용 iPhone의 Microsoft Dynamics CRM</span><span class="sxs-lookup"><span data-stu-id="e8d09-154">Microsoft Dynamics CRM on iPhone for iOS</span></span>
    
    - <span data-ttu-id="e8d09-155">Android 휴대폰용 Dynamics CRM</span><span class="sxs-lookup"><span data-stu-id="e8d09-155">Dynamics CRM for Phones for Android</span></span>
    
    - <span data-ttu-id="e8d09-156">Android 태블릿용 Dynamics CRM</span><span class="sxs-lookup"><span data-stu-id="e8d09-156">Dynamics CRM for Tablets for Android</span></span>
    
    - <span data-ttu-id="e8d09-157">Android용 Excel</span><span class="sxs-lookup"><span data-stu-id="e8d09-157">Excel for Android</span></span>
    
    - <span data-ttu-id="e8d09-158">Android용 Word</span><span class="sxs-lookup"><span data-stu-id="e8d09-158">Word for Android</span></span>
    
    - <span data-ttu-id="e8d09-159">iOS용 OneNote</span><span class="sxs-lookup"><span data-stu-id="e8d09-159">OneNote for iOS</span></span>
    
31. <span data-ttu-id="e8d09-160">**모바일 앱 - 앱** 블레이드를 닫습니다.</span><span class="sxs-lookup"><span data-stu-id="e8d09-160">Close the **Mobile Apps - Apps** blade.</span></span>
    
32. <span data-ttu-id="e8d09-161">**모바일 앱** 블레이드에서 **앱 보호 정책**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="e8d09-161">On the **Mobile Apps** blade, click **App Protection Policies**.</span></span>
    
33. <span data-ttu-id="e8d09-162">**앱 보호 정책** 블레이드에서 **정책 추가**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="e8d09-162">On the **App Protection Policies** blade, click **Add a policy**.</span></span>
    
34. <span data-ttu-id="e8d09-163">**정책 추가** 블레이드에서 **iOS**를 입력한 다음 **필요한 앱 선택**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="e8d09-163">On the **Add a policy** blade, type **iOS**, and then click **Select required apps**.</span></span>
    
35. <span data-ttu-id="e8d09-164">**앱** 블레이드에서 **PowerPoint**, **iPhone의 Microsoft Dynamics CRM**, **Excel**, **iPhone의 Microsoft Dynamics CRM**, **Word**, **OneNote** 및 **Outlook**을 클릭한 다음 **선택**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="e8d09-164">On the **Apps** blade, click **PowerPoint**, **Microsoft Dynamics CRM on iPhone**, **Excel**, **Microsoft Dynamics CRM on iPhone**, **Word**, **OneNote**, and **Outlook**, and then click **Select**.</span></span>
    
36. <span data-ttu-id="e8d09-165">**정책 추가** 블레이드에서 **만들기**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="e8d09-165">On the **Add a policy** blade, click **Create**.</span></span>
    
37. <span data-ttu-id="e8d09-166">**앱 보호 정책** 블레이드에서 **정책 추가**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="e8d09-166">On the **App Protection Policies** blade, click **Add a policy**.</span></span>
    
38. <span data-ttu-id="e8d09-167">**정책 추가** 블레이드에서 **Android**를 입력하고 **플랫폼**에서 **Android**를 선택한 다음 **필요한 앱 선택**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="e8d09-167">On the **Add a policy** blade, type **Android**, select **Android** in **Platform**, and then click **Select required apps**.</span></span>
    
39. <span data-ttu-id="e8d09-168">**앱** 블레이드에서 **PowerPoint**, **태블릿용 Dynamics CRM**, **Excel**, **Word**, **Outlook** 및 **휴대폰용 Dynamics CRM**을 클릭한 다음 **선택**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="e8d09-168">On the **Apps** blade, click **PowerPoint**, **Dynamics CRM for tablets**, **Excel**, **Word**, **Outlook**, and **Dynamics CRM for phones**, and then click **Select**.</span></span>
    
40. <span data-ttu-id="e8d09-169">**정책 추가** 블레이드에서 **만들기**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="e8d09-169">On the **Add a policy** blade, click **Create**.</span></span>
    
<span data-ttu-id="e8d09-170">이제 iOS 장치용과 Android 장치용의 두 가지 MAM 정책이 있으며 선택한 앱의 설정 테스트를 실험할 준비가 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="e8d09-170">You now have two MAM policies, one for iOS devices and one for Android devices, and are ready to experiment with testing settings for the selected apps.</span></span> 
  
## <a name="next-step"></a><span data-ttu-id="e8d09-171">다음 단계</span><span class="sxs-lookup"><span data-stu-id="e8d09-171">Next step</span></span>

<span data-ttu-id="e8d09-172">테스트 환경의 [모바일 장치 관리](m365-enterprise-test-lab-guides.md#mobile-device-management) 추가 기능 및 특징을 살펴봅니다.</span><span class="sxs-lookup"><span data-stu-id="e8d09-172">Explore additional [mobile device management](m365-enterprise-test-lab-guides.md#mobile-device-management) features and capabilities in your test environment.</span></span>

## <a name="see-also"></a><span data-ttu-id="e8d09-173">참고 항목</span><span class="sxs-lookup"><span data-stu-id="e8d09-173">See also</span></span>

<span data-ttu-id="e8d09-174">[Microsoft 365 Enterprise 테스트 랩 가이드](m365-enterprise-test-lab-guides.md)입니다.</span><span class="sxs-lookup"><span data-stu-id="e8d09-174">[Microsoft 365 Enterprise Test Lab Guides](m365-enterprise-test-lab-guides.md).</span></span>
  
[<span data-ttu-id="e8d09-175">Microsoft 365 Enterprise 테스트 환경에서 iOS 및 Android 장치 등록</span><span class="sxs-lookup"><span data-stu-id="e8d09-175">Enroll iOS and Android devices in your Microsoft 365 Enterprise test environment</span></span>](enroll-ios-and-android-devices-in-your-microsoft-enterprise-365-dev-test-environ.md)
  
[<span data-ttu-id="e8d09-176">Microsoft 365 Enterprise 배포</span><span class="sxs-lookup"><span data-stu-id="e8d09-176">Deploy Microsoft 365 Enterprise</span></span>](deploy-microsoft-365-enterprise.md)

[<span data-ttu-id="e8d09-177">엔터프라이즈 이동성 + 보안 (EMS)</span><span class="sxs-lookup"><span data-stu-id="e8d09-177">Enterprise Mobility + Security (EMS)</span></span>](https://www.microsoft.com/cloud-platform/enterprise-mobility-security)
