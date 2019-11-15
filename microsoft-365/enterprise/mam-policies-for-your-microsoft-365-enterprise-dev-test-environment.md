---
title: Microsoft 365 Enterprise 테스트 환경에 대 한 장치 준수 정책
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 11/14/2018
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection: M365-identity-device-management
ms.custom: Ent_TLGs
ms.assetid: 1aa9639b-2862-49c4-bc33-1586dda636b8
description: 이 테스트 랩 가이드를 사용 하 여 Microsoft 365 Enterprise 테스트 환경에 Intune 장치 준수 정책을 추가 합니다.
ms.openlocfilehash: dbe0592dfcac7090da194c85db8e788e8e64a0e7
ms.sourcegitcommit: 2c2248b03f7753d64490f2f7e56ec644a235b65a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/15/2019
ms.locfileid: "38639808"
---
# <a name="device-compliance-policies-for-your-microsoft-365-enterprise-test-environment"></a><span data-ttu-id="4c8e6-103">Microsoft 365 Enterprise 테스트 환경에 대 한 장치 준수 정책</span><span class="sxs-lookup"><span data-stu-id="4c8e6-103">Device compliance policies for your Microsoft 365 Enterprise test environment</span></span>

<span data-ttu-id="4c8e6-104">이 문서의 지침을 사용 하 여 Microsoft 365 Enterprise 테스트 환경에 Intune 장치 준수 정책을 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="4c8e6-104">With the instructions in this article, you add an Intune device compliance policy to your Microsoft 365 Enterprise test environment.</span></span>

![Microsoft 클라우드의 테스트 랩 가이드](media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png)

> [!TIP]
> <span data-ttu-id="4c8e6-106">[여기](media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf)를 클릭하여 Microsoft 365 Enterprise 테스트 랩 가이드 스택의 모든 문서에 대한 가상 맵을 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4c8e6-106">Click [here](media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf) for a visual map to all the articles in the Microsoft 365 Enterprise Test Lab Guide stack.</span></span>

## <a name="phase-1-build-out-your-microsoft-365-enterprise-test-environment"></a><span data-ttu-id="4c8e6-107">1 단계: Microsoft 365 Enterprise 테스트 환경 구축</span><span class="sxs-lookup"><span data-stu-id="4c8e6-107">Phase 1: Build out your Microsoft 365 Enterprise test environment</span></span>

<span data-ttu-id="4c8e6-108">최소 요구 사항을 사용 하 여 간단한 방식으로 MAM 정책을 구성 하려면 [간단한 기본 구성](lightweight-base-configuration-microsoft-365-enterprise.md)의 지침을 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="4c8e6-108">If you just want to configure MAM policies in a lightweight way with the minimum requirements, follow the instructions in [Lightweight base configuration](lightweight-base-configuration-microsoft-365-enterprise.md).</span></span>
  
<span data-ttu-id="4c8e6-109">시뮬레이트된 엔터프라이즈에서 MAM 정책을 구성 하려면 [통과 인증](pass-through-auth-m365-ent-test-environment.md)의 지침을 따르세요.</span><span class="sxs-lookup"><span data-stu-id="4c8e6-109">If you want to configure MAM policies in a simulated enterprise, follow the instructions in [Pass-through authentication](pass-through-auth-m365-ent-test-environment.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="4c8e6-110">자동 라이선싱 및 그룹 구성원을 테스트 하는 경우에는 AD DS (Active Directory 도메인 서비스) 포리스트의 인터넷 및 디렉터리 동기화에 연결 된 시뮬레이트된 인트라넷을 포함 하는 시뮬레이트된 엔터프라이즈 테스트 환경이 필요 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="4c8e6-110">Testing automated licensing and group membership does not require the simulated enterprise test environment, which includes a simulated intranet connected to the Internet and directory synchronization for a Active Directory Domain Services (AD DS) forest.</span></span> <span data-ttu-id="4c8e6-111">이 기능은 자동 라이선스 및 그룹 구성원을 테스트 하 고 일반적인 조직을 나타내는 환경에서 테스트할 수 있도록 옵션으로 제공 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4c8e6-111">It is provided here as an option so that you can test automated licensing and group membership and experiment with it in an environment that represents a typical organization.</span></span> 
>  

## <a name="phase-2-create-a-device-compliance-policy-for-windows-10-devices"></a><span data-ttu-id="4c8e6-112">2 단계: Windows 10 장치에 대 한 장치 준수 정책 만들기</span><span class="sxs-lookup"><span data-stu-id="4c8e6-112">Phase 2: Create a device compliance policy for Windows 10 devices</span></span>

<span data-ttu-id="4c8e6-113">이 단계에서는 Windows 10 장치에 대 한 장치 준수 정책을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="4c8e6-113">In this phase, you create a device compliance policy for Windows 10 devices.</span></span>
  
1. <span data-ttu-id="4c8e6-114">에서[https://portal.office.com](https://portal.office.com)office 365 포털로 이동 하 여 전역 관리자 계정을 사용 하 여 office 365 테스트 랩 구독에 로그인 합니다.</span><span class="sxs-lookup"><span data-stu-id="4c8e6-114">Go to the Office 365 portal at ([https://portal.office.com](https://portal.office.com)) and sign in to your Office 365 test lab subscription with your global administrator account.</span></span>
    
2. <span data-ttu-id="4c8e6-115">브라우저의 새 탭에서 Azure portal ()을 엽니다 [https://portal.azure.com](https://portal.azure.com).</span><span class="sxs-lookup"><span data-stu-id="4c8e6-115">On a new tab of your browser, open the Azure portal at [https://portal.azure.com](https://portal.azure.com).</span></span>

3. <span data-ttu-id="4c8e6-116">브라우저의 Azure portal 탭에 있는 탐색 창에서 **모든 서비스**를 클릭 하 고 **intune**을 입력 한 다음 **intune**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="4c8e6-116">On the Azure portal tab in your browser, in the navigation pane, click **All services**, type **Intune**, and then click **Intune**.</span></span>
    
4. <span data-ttu-id="4c8e6-117">**Microsoft Intune** 블레이드에서 **장치 관리 아직 메시지를 사용 하도록 설정 하지 않은** 경우에는 해당 항목을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="4c8e6-117">If you see a **You haven't enabled device management yet** message on the **Microsoft Intune** blade, click it.</span></span> <span data-ttu-id="4c8e6-118">**모바일 장치 관리 기관** 블레이드에서 **Intune MDM 기관을**클릭 한 다음 **선택을**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="4c8e6-118">On the **Mobile Device Management authority** blade, click **Intune MDM Authority**, and then click **Choose**.</span></span> <span data-ttu-id="4c8e6-119">브라우저 탭을 새로 고칩니다.</span><span class="sxs-lookup"><span data-stu-id="4c8e6-119">Refresh your browser tab.</span></span>
    
5. <span data-ttu-id="4c8e6-120">왼쪽 탐색 창에서 **그룹**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="4c8e6-120">In the left navigation pane, click **Groups**.</span></span>
    
6. <span data-ttu-id="4c8e6-121">**그룹-모든 그룹** 블레이드에서 **+ 새 그룹**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="4c8e6-121">On the **Groups-All groups** blade, click **+ New Group**.</span></span>
    
7. <span data-ttu-id="4c8e6-122">**그룹** 블레이드에서 **Office 365** 또는 **보안** 을 선택 **하**고 **이름**에 **관리 되는 Windows 10 장치 사용자** 를 입력 한 다음 **멤버 자격 유형에**서 **할당 됨** 을 선택 하 고 **만들기**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="4c8e6-122">On the **Group** blade, select **Office 365** or **Security** for **Group type?**, type **Managed Windows 10 device users** in **Name**, select **Assigned** in **Membership type**,  and then click **Create**.</span></span> 
    
8. <span data-ttu-id="4c8e6-123">**그룹** 블레이드를 닫습니다.</span><span class="sxs-lookup"><span data-stu-id="4c8e6-123">Close the **Group** blade.</span></span>
    
11. <span data-ttu-id="4c8e6-124">**그룹-모든 그룹** 블레이드를 닫습니다.</span><span class="sxs-lookup"><span data-stu-id="4c8e6-124">Close the **Groups-All groups** blade.</span></span>
    
12. <span data-ttu-id="4c8e6-125">**Microsoft Intune** 블레이드에서 **빠른 작업** 목록에서 **준수 정책 만들기**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="4c8e6-125">On the **Microsoft Intune** blade, in the **Quick tasks** list, click **Create a compliance policy**.</span></span>
    
13. <span data-ttu-id="4c8e6-126">**준수 정책 프로필** 블레이드에서 **정책 만들기**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="4c8e6-126">On the **Compliance Policy Profiles** blade, click **Create Policy**.</span></span>
    
14. <span data-ttu-id="4c8e6-127">**정책 만들기** 블레이드에서 **Name (이름**)에 **Windows 10**을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="4c8e6-127">On the **Create Policy** blade, in **Name**, type **Windows 10**.</span></span> <span data-ttu-id="4c8e6-128">**플랫폼**에서 **windows 10 이상**을 선택 하 고 **Windows 10 준수 정책** 블레이드에서 **확인** 을 클릭 한 다음 **만들기**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="4c8e6-128">In **Platform**, select **Windows 10 and later**, click **OK** on the **Windows 10 compliance policy** blade, and then click **Create**.</span></span> <span data-ttu-id="4c8e6-129">**Windows 10** 블레이드를 닫습니다.</span><span class="sxs-lookup"><span data-stu-id="4c8e6-129">Close the **Windows 10** blade.</span></span>
    
15. <span data-ttu-id="4c8e6-130">**준수 정책 프로필** 블레이드에서 **Windows 10** 정책 이름을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="4c8e6-130">On the **Compliance Policy Profiles** blade, click the **Windows 10** policy name.</span></span>
    
16. <span data-ttu-id="4c8e6-131">**Windows 10** 블레이드에서 **할당**을 클릭 하 고 **포함할 그룹 선택을**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="4c8e6-131">On the **Windows 10** blade, click **Assignments**, and then click **Select groups to include**.</span></span>
    
17. <span data-ttu-id="4c8e6-132">**포함할 그룹 선택** 블레이드에서 **관리 되는 Windows 10 장치 사용자** 그룹을 클릭 한 다음 **선택을**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="4c8e6-132">On the **Select groups to include** blade, click the **Managed Windows 10 device users** group, and then click **Select**.</span></span>
    
18. <span data-ttu-id="4c8e6-133">**저장**을 클릭 하 고 **Windows 10 할당** 블레이드를 닫습니다.</span><span class="sxs-lookup"><span data-stu-id="4c8e6-133">Click **Save**, and then close the **Windows 10 - Assignments** blade.</span></span>
    
19. <span data-ttu-id="4c8e6-134">**준수 정책 프로필** 블레이드를 닫습니다.</span><span class="sxs-lookup"><span data-stu-id="4c8e6-134">Close the **Compliance Policy Profiles** blade.</span></span>
    
20. <span data-ttu-id="4c8e6-135">**Microsoft Intune** 블레이드에서 왼쪽 탐색 창에서 **클라이언트 앱** 을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="4c8e6-135">On the **Microsoft Intune** blade, click **Client apps** in the left navigation.</span></span>
    
21. <span data-ttu-id="4c8e6-136">**클라이언트 응용 프로그램** 블레이드에서 **앱**을 클릭 하 고 **추가**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="4c8e6-136">On the **Client Apps** blade, click **Apps**, and then click **Add**.</span></span> 

22. <span data-ttu-id="4c8e6-137">**앱 추가** 블레이드에서 **앱 유형을**선택 하 고 **Office 365 제품군**에서 **Windows 10** 을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="4c8e6-137">In the **Add app** blade, select **App type**, and then select **Windows 10** under **Office 365 Suite**.</span></span>

23. <span data-ttu-id="4c8e6-138">**앱 제품군 구성을**클릭 한 다음 **확인**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="4c8e6-138">Click **Configure App Suite**, and then click **OK**.</span></span>

24. <span data-ttu-id="4c8e6-139">**앱 제품군 정보**를 클릭 하 고 제품군 **이름**에 **windows 10 용 office 앱** 을 입력 하 고 **Suite 설명**에 **windows 10 용 office 앱** 을 설정한 다음 **확인**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="4c8e6-139">Click **App Suite Information**, type **Office Apps for Windows 10** in **Suite Name**, **Office Apps for Windows 10** in **Suite Description**, and then click **OK**.</span></span>

25. <span data-ttu-id="4c8e6-140">**앱 제품군 설정을**클릭 하 고 **업데이트 채널**에서 **반기** 를 선택한 다음 **확인**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="4c8e6-140">Click **App Suite Settings**, select **Semi-Annual** in **Update channel**, and then click **OK**.</span></span>

26. <span data-ttu-id="4c8e6-141">**앱 추가** 블레이드에서 **추가**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="4c8e6-141">On the **Add app** blade, click **Add**.</span></span>

<span data-ttu-id="4c8e6-142">이제 **windows 10** 장치 준수 정책 및 **관리 되는 Windows 10 장치 사용자** 그룹의 구성원에 대해 선택한 앱을 테스트할 수 있는 장치 준수 정책이 만들어졌습니다.</span><span class="sxs-lookup"><span data-stu-id="4c8e6-142">You now have a device compliance policy for testing the selected apps in the **Windows 10** device compliance policy and for members of the **Managed Windows 10 device users** group.</span></span> <span data-ttu-id="4c8e6-143">그룹 유형으로 Office 365을 선택 하면 추가 리소스가 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="4c8e6-143">Please note that selecting Office 365 as the group type will create additional resources.</span></span> 
  
## <a name="next-step"></a><span data-ttu-id="4c8e6-144">다음 단계</span><span class="sxs-lookup"><span data-stu-id="4c8e6-144">Next step</span></span>

<span data-ttu-id="4c8e6-145">테스트 환경에서 추가 [모바일 장치 관리](m365-enterprise-test-lab-guides.md#mobile-device-management) 기능을 알아봅니다.</span><span class="sxs-lookup"><span data-stu-id="4c8e6-145">Explore additional [mobile device management](m365-enterprise-test-lab-guides.md#mobile-device-management) features and capabilities in your test environment.</span></span>

## <a name="see-also"></a><span data-ttu-id="4c8e6-146">참고 항목</span><span class="sxs-lookup"><span data-stu-id="4c8e6-146">See also</span></span>

<span data-ttu-id="4c8e6-147">[Microsoft 365 Enterprise 테스트 랩 가이드](m365-enterprise-test-lab-guides.md)</span><span class="sxs-lookup"><span data-stu-id="4c8e6-147">[Microsoft 365 Enterprise Test Lab Guides](m365-enterprise-test-lab-guides.md).</span></span>
  
[<span data-ttu-id="4c8e6-148">Microsoft 365 Enterprise 테스트 환경에서 iOS 및 Android 장치 등록</span><span class="sxs-lookup"><span data-stu-id="4c8e6-148">Enroll iOS and Android devices in your Microsoft 365 Enterprise test environment</span></span>](enroll-ios-and-android-devices-in-your-microsoft-enterprise-365-dev-test-environ.md)
  
[<span data-ttu-id="4c8e6-149">Microsoft 365 Enterprise 배포</span><span class="sxs-lookup"><span data-stu-id="4c8e6-149">Deploy Microsoft 365 Enterprise</span></span>](deploy-microsoft-365-enterprise.md)

[<span data-ttu-id="4c8e6-150">EMS (Enterprise Mobility + Security)</span><span class="sxs-lookup"><span data-stu-id="4c8e6-150">Enterprise Mobility + Security (EMS)</span></span>](https://www.microsoft.com/cloud-platform/enterprise-mobility-security)
