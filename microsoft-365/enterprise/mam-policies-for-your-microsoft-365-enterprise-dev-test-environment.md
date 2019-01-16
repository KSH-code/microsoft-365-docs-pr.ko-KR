---
title: Microsoft 365 기업에 대 한 규정 준수 정책 장치 테스트 환경
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 11/14/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection: Ent_O365
ms.custom: Ent_TLGs
ms.assetid: 1aa9639b-2862-49c4-bc33-1586dda636b8
description: 이 테스트 랩 가이드를 사용 하 여 Microsoft 365 기업에 Intune 장치 규정 준수 정책 테스트 환경에 추가 합니다.
ms.openlocfilehash: 1d957c5cdc888251224bbca43fe82ab0a15e7a93
ms.sourcegitcommit: e491c4713115610cbe13d2fbd0d65e1a41c34d62
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/16/2019
ms.locfileid: "26870348"
---
# <a name="device-compliance-policies-for-your-microsoft-365-enterprise-test-environment"></a><span data-ttu-id="69602-103">Microsoft 365 기업에 대 한 규정 준수 정책 장치 테스트 환경</span><span class="sxs-lookup"><span data-stu-id="69602-103">Device compliance policies for your Microsoft 365 Enterprise test environment</span></span>

<span data-ttu-id="69602-104">이 문서의 지침을과 함께 Microsoft 365 Enterprise 테스트 환경에 Intune 장치 규정 준수 정책을 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="69602-104">With the instructions in this article, you add an Intune device compliance policy to your Microsoft 365 Enterprise test environment.</span></span>

![Microsoft 클라우드의 테스트 랩 가이드](media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png)

> [!TIP]
> <span data-ttu-id="69602-106">[여기](https://aka.ms/m365etlgstack)를 클릭하여 Microsoft 365 Enterprise 테스트 랩 가이드 스택의 모든 문서에 대한 가상 맵을 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="69602-106">Click [here](https://aka.ms/m365etlgstack) for a visual map to all the articles in the Microsoft 365 Enterprise Test Lab Guide stack.</span></span>

## <a name="phase-1-build-out-your-microsoft-365-enterprise-test-environment"></a><span data-ttu-id="69602-107">1 단계: Microsoft 365 Enterprise 테스트 환경을 구축합니다</span><span class="sxs-lookup"><span data-stu-id="69602-107">Phase 1: Build out your Microsoft 365 Enterprise test environment</span></span>

<span data-ttu-id="69602-108">최소 요구 사항을 경량 방식으로 MAM 정책을 구성 하려면 [경량 기본 구성](lightweight-base-configuration-microsoft-365-enterprise.md)의 지시를 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="69602-108">If you just want to configure MAM policies in a lightweight way with the minimum requirements, follow the instructions in [Lightweight base configuration](lightweight-base-configuration-microsoft-365-enterprise.md).</span></span>
  
<span data-ttu-id="69602-109">시뮬레이션 된 엔터프라이즈에서 MAM 정책을 구성 하려는 경우 [통과 인증](pass-through-auth-m365-ent-test-environment.md)의 지시를 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="69602-109">If you want to configure MAM policies in a simulated enterprise, follow the instructions in [Pass-through authentication](pass-through-auth-m365-ent-test-environment.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="69602-p101">라이선스 하는 자동화 된 테스트 하 고 그룹 멤버 자격을 원하지 않는 인터넷에 연결 하는 시뮬레이션 된 인트라넷을 포함 하는 시뮬레이션 된 엔터프라이즈 테스트 환경 및 Windows Server AD 포리스트에 대 한 디렉터리 동기화 합니다. 제공는 자동화 된 라이선스 및 그룹 구성원 자격을 테스트 하 고 일반적인 조직을 대표 하는 환경에서 사용해 수 있도록 하는 옵션으로 여기 합니다.</span><span class="sxs-lookup"><span data-stu-id="69602-p101">Testing automated licensing and group membership does not require the simulated enterprise test environment, which includes a simulated intranet connected to the Internet and directory synchronization for a Windows Server AD forest. It is provided here as an option so that you can test automated licensing and group membership and experiment with it in an environment that represents a typical organization.</span></span> 
>  

## <a name="phase-2-create-a-device-compliance-policy-for-windows-10-devices"></a><span data-ttu-id="69602-112">2 단계: Windows 10 장치에 대 한 장치 규정 준수 정책 만들기</span><span class="sxs-lookup"><span data-stu-id="69602-112">Phase 2: Create a device compliance policy for Windows 10 devices</span></span>

<span data-ttu-id="69602-113">이 단계에서는 Windows 10 장치에 대 한 장치 규정 준수 정책을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="69602-113">In this phase, you create a device compliance policy for Windows 10 devices.</span></span>
  
1. <span data-ttu-id="69602-114">Office 포털으로 이동 ([https://office.com](https://office.com)) 전역 관리자 계정 사용 하 여 Office 365 평가판 구독에 로그인 합니다.</span><span class="sxs-lookup"><span data-stu-id="69602-114">Go to the Office portal at ([https://office.com](https://office.com)) and sign in to your Office 365 trial subscription with your global administrator account.</span></span>
    
2. <span data-ttu-id="69602-115">브라우저의 새 탭에서 Azure 포털을 엽니다 [https://portal.azure.com](https://portal.azure.com)합니다.</span><span class="sxs-lookup"><span data-stu-id="69602-115">On a new tab of your browser, open the Azure portal at [https://portal.azure.com](https://portal.azure.com).</span></span>

3. <span data-ttu-id="69602-116">탐색 창에서 브라우저에서 Azure 포털 탭에서 **모든 서비스**를 클릭 하 고 **Intune**입력 **Intune**를 클릭 한 다음 합니다.</span><span class="sxs-lookup"><span data-stu-id="69602-116">On the Azure portal tab in your browser, in the navigation pane, click **All services**, type **Intune**, and then click **Intune**.</span></span>
    
4. <span data-ttu-id="69602-p102">**Microsoft Intune** 블레이드에 **장치 관리 아직 활성화 하지 않은** 메시지를 표시 하는 경우이 클릭 합니다. **모바일 장치 관리 기관** 블레이드에서 **Intune MDM 기관**클릭 한 다음 **선택**을 클릭 합니다. 브라우저 탭을 새로 고칠 합니다.</span><span class="sxs-lookup"><span data-stu-id="69602-p102">If you see a **You haven't enabled device management yet** message on the **Microsoft Intune** blade, click it. On the **Mobile Device Management authority** blade, click **Intune MDM Authority**, and then click **Choose**. Refresh your browser tab.</span></span>
    
5. <span data-ttu-id="69602-120">왼쪽 탐색 창에서 **그룹**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="69602-120">In the left navigation pane, click **Groups**.</span></span>
    
6. <span data-ttu-id="69602-121">**그룹-모든 그룹** 블레이드에서 **+ 새 그룹을**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="69602-121">On the **Groups-All groups** blade, click **+ New Group**.</span></span>
    
7. <span data-ttu-id="69602-122">**그룹** 블레이드 선택에 대 한 **Office 365** **그룹 종류?**, **Windows 10 관리 되는 장치 사용자** **이름**입력 하 고 **멤버 자격 종류** **할당 됨** 을 선택 하 고 **만들기**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="69602-122">On the **Group** blade, select **Office 365** for **Group type?**, type **Managed Windows 10 device users** in **Name**, select **Assigned** in **Membership type**,  and then click **Create**.</span></span> 
    
8. <span data-ttu-id="69602-123">**그룹** 블레이드를 닫습니다.</span><span class="sxs-lookup"><span data-stu-id="69602-123">Close the **Group** blade.</span></span>
    
11. <span data-ttu-id="69602-124">**그룹-모든 그룹** 블레이드를 닫습니다.</span><span class="sxs-lookup"><span data-stu-id="69602-124">Close the **Groups-All groups** blade.</span></span>
    
12. <span data-ttu-id="69602-125">**Microsoft Intune** 블레이드 **빠른 작업** 목록에서 **준수 정책 만들기**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="69602-125">On the **Microsoft Intune** blade, in the **Quick tasks** list, click **Create a compliance policy**.</span></span>
    
13. <span data-ttu-id="69602-126">**준수 정책 프로필** 블레이드에서 **정책 만들기**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="69602-126">On the **Compliance Policy Profiles** blade, click **Create Policy**.</span></span>
    
14. <span data-ttu-id="69602-p103">**정책 만들기** 블레이드 **이름** **Windows 10**을 입력 합니다. **플랫폼** **Windows 10 이상**, 선택한 **Windows 10 규정 준수 정책** 블레이드에서 **확인** 을 클릭 한 다음 **만들기**를 클릭 합니다. **Windows 10** 블레이드를 닫습니다.</span><span class="sxs-lookup"><span data-stu-id="69602-p103">On the **Create Policy** blade, in **Name**, type **Windows 10**. In **Platform**, select **Windows 10 and later**, click **OK** on the **Windows 10 compliance policy** blade, and then click **Create**. Close the **Windows 10** blade.</span></span>
    
15. <span data-ttu-id="69602-130">**규정 준수 정책 프로필** 블레이드 **Windows 10** 정책 이름을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="69602-130">On the **Compliance Policy Profiles** blade, click the **Windows 10** policy name.</span></span>
    
16. <span data-ttu-id="69602-131">**Windows 10** 블레이드에서 **할당**을 클릭 하 고 **그룹을 포함 하도록 선택**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="69602-131">On the **Windows 10** blade, click **Assignments**, and then click **Select groups to include**.</span></span>
    
17. <span data-ttu-id="69602-132">**그룹을 포함 하도록 선택** 블레이드 **Windows 10 관리 되는 장치 사용자** 그룹을 클릭 하 고 **선택**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="69602-132">On the **Select groups to include** blade, click the **Managed Windows 10 device users** group, and then click **Select**.</span></span>
    
18. <span data-ttu-id="69602-133">**저장**을 클릭 한 다음 **Windows 10-배정** 블레이드를 닫습니다.</span><span class="sxs-lookup"><span data-stu-id="69602-133">Click **Save**, and then close the **Windows 10 - Assignments** blade.</span></span>
    
19. <span data-ttu-id="69602-134">**준수 정책 프로필** 블레이드를 닫습니다.</span><span class="sxs-lookup"><span data-stu-id="69602-134">Close the **Compliance Policy Profiles** blade.</span></span>
    
20. <span data-ttu-id="69602-135">**Microsoft Intune** 블레이드에서의 왼쪽된 탐색 영역에서 **클라이언트 응용 프로그램** 을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="69602-135">On the **Microsoft Intune** blade, click **Client apps** in the left navigation.</span></span>
    
21. <span data-ttu-id="69602-136">**클라이언트 앱** 블레이드에서 **앱**클릭 한 다음 **추가**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="69602-136">On the **Client Apps** blade, click **Apps**, and then click **Add**.</span></span> 

22. <span data-ttu-id="69602-137">**추가 app** 블레이드 **App 유형**을 선택 하 고 **Office 365 제품군**에서 **Windows 10** 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="69602-137">In the **Add app** blade, select **App type**, and then select **Windows 10** under **Office 365 Suite**.</span></span>

23. <span data-ttu-id="69602-138">**응용 프로그램 제품군 구성**클릭 하 고 **확인**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="69602-138">Click **Configure App Suite**, and then click **OK**.</span></span>

24. <span data-ttu-id="69602-139">**응용 프로그램 제품군 정보**를 클릭 하 고 **제품군 이름**, **설명 제품군** **Windows 10에 대 한 Office 응용 프로그램** 에서 **Windows 10에 대 한 Office 응용 프로그램을** 입력 한 다음 **확인**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="69602-139">Click **App Suite Information**, type **Office Apps for Windows 10** in **Suite Name**, **Office Apps for Windows 10** in **Suite Description**, and then click **OK**.</span></span>

25. <span data-ttu-id="69602-140">**응용 프로그램 제품군 설정**을 클릭, **세미콜론 연간 회의** **업데이트 채널**선택한 다음 **확인**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="69602-140">Click **App Suite Settings**, select **Semi-Annual** in **Update channel**, and then click **OK**.</span></span>

26. <span data-ttu-id="69602-141">**추가 app** 블레이드에서 **추가**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="69602-141">On the **Add app** blade, click **Add**.</span></span>

<span data-ttu-id="69602-142">이제 **Windows 10** 장치 규정 준수 정책에서 선택한 앱을 테스트 하 고 **관리 하는 Windows 10 장치 users** 그룹의 구성원에 대 한 장치 규정 준수 정책.</span><span class="sxs-lookup"><span data-stu-id="69602-142">You now have a device compliance policy for testing the selected apps in the **Windows 10** device compliance policy and for members of the **Managed Windows 10 device users** group.</span></span> 
  
## <a name="next-step"></a><span data-ttu-id="69602-143">다음 단계</span><span class="sxs-lookup"><span data-stu-id="69602-143">Next step</span></span>

<span data-ttu-id="69602-144">테스트 환경의 [모바일 장치 관리](m365-enterprise-test-lab-guides.md#mobile-device-management) 추가 기능 및 특징을 살펴봅니다.</span><span class="sxs-lookup"><span data-stu-id="69602-144">Explore additional [mobile device management](m365-enterprise-test-lab-guides.md#mobile-device-management) features and capabilities in your test environment.</span></span>

## <a name="see-also"></a><span data-ttu-id="69602-145">참고 항목</span><span class="sxs-lookup"><span data-stu-id="69602-145">See also</span></span>

<span data-ttu-id="69602-146">[Microsoft 365 Enterprise 테스트 랩 가이드](m365-enterprise-test-lab-guides.md)입니다.</span><span class="sxs-lookup"><span data-stu-id="69602-146">[Microsoft 365 Enterprise Test Lab Guides](m365-enterprise-test-lab-guides.md).</span></span>
  
[<span data-ttu-id="69602-147">Microsoft 365 Enterprise 테스트 환경에서 iOS 및 Android 장치 등록</span><span class="sxs-lookup"><span data-stu-id="69602-147">Enroll iOS and Android devices in your Microsoft 365 Enterprise test environment</span></span>](enroll-ios-and-android-devices-in-your-microsoft-enterprise-365-dev-test-environ.md)
  
[<span data-ttu-id="69602-148">Microsoft 365 Enterprise 배포</span><span class="sxs-lookup"><span data-stu-id="69602-148">Deploy Microsoft 365 Enterprise</span></span>](deploy-microsoft-365-enterprise.md)

[<span data-ttu-id="69602-149">엔터프라이즈 이동성 + 보안 (EMS)</span><span class="sxs-lookup"><span data-stu-id="69602-149">Enterprise Mobility + Security (EMS)</span></span>](https://www.microsoft.com/cloud-platform/enterprise-mobility-security)
