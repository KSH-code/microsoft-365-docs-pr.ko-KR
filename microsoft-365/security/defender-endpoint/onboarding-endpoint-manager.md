---
title: Microsoft Endpoint Manager를 사용하여 온보딩
description: Microsoft Endpoint Manager를 사용하여 끝점용 Microsoft Defender에 온보딩하는 방법 학습
keywords: 온보딩, 구성, 배포, 배포, 끝점 관리자, Endpoint용 Microsoft Defender, 컬렉션 만들기, 끝점 감지 응답, 차세대 보호, 공격 표면 감소, Microsoft 끝점 관리자
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365solution-endpointprotect
- m365solution-scenario
ms.topic: article
ms.technology: mde
ms.openlocfilehash: e744262cfd63383e69abf02be9fbf91d2d229db2
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/21/2021
ms.locfileid: "51935260"
---
# <a name="onboarding-using-microsoft-endpoint-manager"></a><span data-ttu-id="2efd0-104">Microsoft Endpoint Manager를 사용하여 온보딩</span><span class="sxs-lookup"><span data-stu-id="2efd0-104">Onboarding using Microsoft Endpoint Manager</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="2efd0-105">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="2efd0-105">**Applies to:**</span></span>
- [<span data-ttu-id="2efd0-106">엔드포인트용 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="2efd0-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="2efd0-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="2efd0-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)


> <span data-ttu-id="2efd0-108">끝점용 Microsoft Defender를 경험하고 싶나요?</span><span class="sxs-lookup"><span data-stu-id="2efd0-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="2efd0-109">무료 평가판에 등록합니다.</span><span class="sxs-lookup"><span data-stu-id="2efd0-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

<span data-ttu-id="2efd0-110">이 문서는 배포 가이드의 일부로, 온보더링 방법의 예로 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2efd0-110">This article is part of the Deployment guide and acts as an example onboarding method.</span></span> 

<span data-ttu-id="2efd0-111">계획 [항목에서는](deployment-strategy.md) 디바이스를 서비스에 온보드하는 여러 가지 방법이 제공되었습니다.</span><span class="sxs-lookup"><span data-stu-id="2efd0-111">In the [Planning](deployment-strategy.md) topic, there were several methods provided to onboard devices to the service.</span></span> <span data-ttu-id="2efd0-112">이 항목에서는 클라우드 네이티브 아키텍처에 대해 다산합니다.</span><span class="sxs-lookup"><span data-stu-id="2efd0-112">This topic covers the cloud-native architecture.</span></span> 

<span data-ttu-id="2efd0-113">![클라우드 기본 아키텍처의 이미지 ](images/cloud-native-architecture.png)
 *환경 아키텍처 다이어그램*</span><span class="sxs-lookup"><span data-stu-id="2efd0-113">![Image of cloud-native architecture](images/cloud-native-architecture.png)
*Diagram of environment architectures*</span></span>

<span data-ttu-id="2efd0-114">Endpoint용 Defender는 다양한 끝점 및 도구의 온보딩을 지원하기는 하지만 이 문서에서는 이를 다루지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="2efd0-114">While Defender for Endpoint supports onboarding of various endpoints and tools, this article does not cover them.</span></span> <span data-ttu-id="2efd0-115">지원되는 다른 배포 도구 및 방법을 사용하는 일반적인 온보드에 대한 자세한 내용은 [Onboarding overview 를 참조하세요.](onboarding.md)</span><span class="sxs-lookup"><span data-stu-id="2efd0-115">For information on general onboarding using other supported deployment tools and methods, see [Onboarding overview](onboarding.md).</span></span>


<span data-ttu-id="2efd0-116">[Microsoft Endpoint Manager는](https://docs.microsoft.com/mem/endpoint-manager-overview) 여러 서비스를 통합하는 솔루션 플랫폼입니다.</span><span class="sxs-lookup"><span data-stu-id="2efd0-116">[Microsoft Endpoint Manager](https://docs.microsoft.com/mem/endpoint-manager-overview) is a solution platform that unifies several services.</span></span> <span data-ttu-id="2efd0-117">여기에는 클라우드 기반 장치 관리를 위한 [Microsoft Intune이](https://docs.microsoft.com/mem/intune/fundamentals/what-is-intune) 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="2efd0-117">It includes [Microsoft Intune](https://docs.microsoft.com/mem/intune/fundamentals/what-is-intune) for cloud-based device management.</span></span>


<span data-ttu-id="2efd0-118">이 항목에서는 사용자에게 다음을 안내합니다.</span><span class="sxs-lookup"><span data-stu-id="2efd0-118">This topic guides users in:</span></span>
- <span data-ttu-id="2efd0-119">1단계: MEM(Microsoft Endpoint Manager)에서 구성을 할당하는 그룹을 만들어 서비스에 장치 온보드</span><span class="sxs-lookup"><span data-stu-id="2efd0-119">Step 1: Onboarding devices to the service by creating a group in Microsoft Endpoint Manager (MEM) to assign configurations on</span></span>
- <span data-ttu-id="2efd0-120">2단계: Microsoft Endpoint Manager를 사용하여 끝점 기능에 대한 Defender 구성</span><span class="sxs-lookup"><span data-stu-id="2efd0-120">Step 2: Configuring Defender for Endpoint capabilities using Microsoft Endpoint Manager</span></span>

<span data-ttu-id="2efd0-121">이 온보더링 지침은 Microsoft Endpoint Manager를 사용할 때 취해야 하는 다음과 같은 기본 단계를 안내합니다.</span><span class="sxs-lookup"><span data-stu-id="2efd0-121">This onboarding guidance will walk you through the following basic steps that you need to take when using Microsoft Endpoint Manager:</span></span>

-   [<span data-ttu-id="2efd0-122">대상 장치 또는 사용자 식별</span><span class="sxs-lookup"><span data-stu-id="2efd0-122">Identifying target devices or users</span></span>](#identify-target-devices-or-users)

    -   <span data-ttu-id="2efd0-123">Azure Active Directory 그룹 만들기(사용자 또는 장치)</span><span class="sxs-lookup"><span data-stu-id="2efd0-123">Creating an Azure Active Directory group (User or Device)</span></span>

-   [<span data-ttu-id="2efd0-124">구성 프로필 만들기</span><span class="sxs-lookup"><span data-stu-id="2efd0-124">Creating a Configuration Profile</span></span>](#step-2-create-configuration-policies-to-configure-microsoft-defender-for-endpoint-capabilities)

    -   <span data-ttu-id="2efd0-125">Microsoft 끝점 관리자에서 각 기능에 대한 별도의 정책을 만드는 데 대해 안내합니다.</span><span class="sxs-lookup"><span data-stu-id="2efd0-125">In Microsoft Endpoint Manager, we'll guide you in creating a separate policy for each capability.</span></span>





## <a name="resources"></a><span data-ttu-id="2efd0-126">리소스</span><span class="sxs-lookup"><span data-stu-id="2efd0-126">Resources</span></span>


<span data-ttu-id="2efd0-127">나머지 프로세스에 필요한 링크는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="2efd0-127">Here are the links you'll need for the rest of the process:</span></span>

-   [<span data-ttu-id="2efd0-128">MEM 포털</span><span class="sxs-lookup"><span data-stu-id="2efd0-128">MEM portal</span></span>](https://aka.ms/memac)

-   [<span data-ttu-id="2efd0-129">보안 센터</span><span class="sxs-lookup"><span data-stu-id="2efd0-129">Security Center</span></span>](https://securitycenter.windows.com/)

-   [<span data-ttu-id="2efd0-130">Intune 보안 기준</span><span class="sxs-lookup"><span data-stu-id="2efd0-130">Intune Security baselines</span></span>](https://docs.microsoft.com/mem/intune/protect/security-baseline-settings-defender-atp#microsoft-defender)

<span data-ttu-id="2efd0-131">Microsoft Endpoint Manager에 대한 자세한 내용은 다음 리소스를 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="2efd0-131">For more information about Microsoft Endpoint Manager, check out these resources:</span></span>
- [<span data-ttu-id="2efd0-132">Microsoft Endpoint Manager 페이지</span><span class="sxs-lookup"><span data-stu-id="2efd0-132">Microsoft Endpoint Manager page</span></span>](https://docs.microsoft.com/mem/)
- [<span data-ttu-id="2efd0-133">Intune 및 ConfigMgr의 수렴에 대한 블로그 게시물</span><span class="sxs-lookup"><span data-stu-id="2efd0-133">Blog post on convergence of Intune and ConfigMgr</span></span>](https://www.microsoft.com/microsoft-365/blog/2019/11/04/use-the-power-of-cloud-intelligence-to-simplify-and-accelerate-it-and-the-move-to-a-modern-workplace/)
- [<span data-ttu-id="2efd0-134">MEM의 소개 비디오</span><span class="sxs-lookup"><span data-stu-id="2efd0-134">Introduction video on MEM</span></span>](https://www.microsoft.com/microsoft-365/blog/2019/11/04/use-the-power-of-cloud-intelligence-to-simplify-and-accelerate-it-and-the-move-to-a-modern-workplace)

## <a name="step-1-onboard-devices-by-creating-a-group-in-mem-to-assign-configurations-on"></a><span data-ttu-id="2efd0-135">1단계: MEM에서 구성을 할당할 그룹을 만들어 장치 온보드</span><span class="sxs-lookup"><span data-stu-id="2efd0-135">Step 1: Onboard devices by creating a group in MEM to assign configurations on</span></span>
### <a name="identify-target-devices-or-users"></a><span data-ttu-id="2efd0-136">대상 장치 또는 사용자 식별</span><span class="sxs-lookup"><span data-stu-id="2efd0-136">Identify target devices or users</span></span>
<span data-ttu-id="2efd0-137">이 섹션에서는 구성을 할당하는 테스트 그룹을 만들 것입니다.</span><span class="sxs-lookup"><span data-stu-id="2efd0-137">In this section, we will create a test group to assign your configurations on.</span></span>

>[!NOTE]
><span data-ttu-id="2efd0-138">Intune은 Azure AD(Azure Active Directory) 그룹을 사용하여 장치 및 사용자를 관리합니다.</span><span class="sxs-lookup"><span data-stu-id="2efd0-138">Intune uses Azure Active Directory (Azure AD) groups to manage devices and users.</span></span> <span data-ttu-id="2efd0-139">Intune 관리자는 조직의 요구 사항에 맞게 그룹을 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2efd0-139">As an Intune admin, you can set up groups to suit your organizational needs.</span></span><br>
<span data-ttu-id="2efd0-140">자세한 내용은 사용자 및 장치를 구성하는 그룹 [추가를 참조하세요.](https://docs.microsoft.com/mem/intune/fundamentals/groups-add)</span><span class="sxs-lookup"><span data-stu-id="2efd0-140">For more information, see [Add groups to organize users and devices](https://docs.microsoft.com/mem/intune/fundamentals/groups-add).</span></span>

### <a name="create-a-group"></a><span data-ttu-id="2efd0-141">그룹 만들기</span><span class="sxs-lookup"><span data-stu-id="2efd0-141">Create a group</span></span>

1.  <span data-ttu-id="2efd0-142">MEM 포털을 열 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2efd0-142">Open the MEM portal.</span></span>

2.  <span data-ttu-id="2efd0-143">새 **> 그룹 열기**</span><span class="sxs-lookup"><span data-stu-id="2efd0-143">Open **Groups > New Group**.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="2efd0-144">![Microsoft Endpoint Manager 포털의 이미지1](images/66f724598d9c3319cba27f79dd4617a4.png)</span><span class="sxs-lookup"><span data-stu-id="2efd0-144">![Image of Microsoft Endpoint Manager portal1](images/66f724598d9c3319cba27f79dd4617a4.png)</span></span>

3.  <span data-ttu-id="2efd0-145">세부 정보를 입력하고 새 그룹을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2efd0-145">Enter details and create a new group.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="2efd0-146">![Microsoft Endpoint Manager 포털의 이미지2](images/b1e0206d675ad07db218b63cd9b9abc3.png)</span><span class="sxs-lookup"><span data-stu-id="2efd0-146">![Image of Microsoft Endpoint Manager portal2](images/b1e0206d675ad07db218b63cd9b9abc3.png)</span></span>

4.  <span data-ttu-id="2efd0-147">테스트 사용자 또는 장치를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="2efd0-147">Add your test user or device.</span></span>

5.  <span data-ttu-id="2efd0-148">모든 그룹 **> 그룹 창에서** 새 그룹을 열 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2efd0-148">From the **Groups > All groups** pane, open your new group.</span></span>

6.  <span data-ttu-id="2efd0-149">구성원을 **선택하여 > 추가합니다.**</span><span class="sxs-lookup"><span data-stu-id="2efd0-149">Select  **Members > Add members**.</span></span>

7.  <span data-ttu-id="2efd0-150">테스트 사용자 또는 장치를 찾아 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="2efd0-150">Find your test user or device and select it.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="2efd0-151">![Microsoft Endpoint Manager 포털의 이미지3](images/149cbfdf221cdbde8159d0ab72644cd0.png)</span><span class="sxs-lookup"><span data-stu-id="2efd0-151">![Image of Microsoft Endpoint Manager portal3](images/149cbfdf221cdbde8159d0ab72644cd0.png)</span></span>

8.  <span data-ttu-id="2efd0-152">이제 테스트 그룹에 테스트할 구성원이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2efd0-152">Your testing group now has a member to test.</span></span>

## <a name="step-2-create-configuration-policies-to-configure-microsoft-defender-for-endpoint-capabilities"></a><span data-ttu-id="2efd0-153">2단계: 끝점 기능을 위한 Microsoft Defender를 구성하는 구성 정책 만들기</span><span class="sxs-lookup"><span data-stu-id="2efd0-153">Step 2: Create configuration policies to configure Microsoft Defender for Endpoint capabilities</span></span>
<span data-ttu-id="2efd0-154">다음 섹션에서는 다양한 구성 정책을 만들 것입니다.</span><span class="sxs-lookup"><span data-stu-id="2efd0-154">In the following section, you'll create a number of configuration policies.</span></span>

<span data-ttu-id="2efd0-155">첫 번째는 끝점용 Defender에 온보딩할 사용자 또는 장치 그룹을 선택하는 구성 정책입니다.</span><span class="sxs-lookup"><span data-stu-id="2efd0-155">First is a configuration policy to select which groups of users or devices will be onboarded to Defender for Endpoint:</span></span>

- [<span data-ttu-id="2efd0-156">엔드포인트 검색 및 대응</span><span class="sxs-lookup"><span data-stu-id="2efd0-156">Endpoint detection and response</span></span>](#endpoint-detection-and-response) 

<span data-ttu-id="2efd0-157">그런 다음 여러 가지 유형의 끝점 보안 정책을 계속 만들게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2efd0-157">Then you will continue by creating several different types of endpoint security policies:</span></span>

- [<span data-ttu-id="2efd0-158">차세대 보호</span><span class="sxs-lookup"><span data-stu-id="2efd0-158">Next-generation protection</span></span>](#next-generation-protection)
- [<span data-ttu-id="2efd0-159">공격 표면 감소</span><span class="sxs-lookup"><span data-stu-id="2efd0-159">Attack surface reduction</span></span>](#attack-surface-reduction--attack-surface-reduction-rules)

### <a name="endpoint-detection-and-response"></a><span data-ttu-id="2efd0-160">엔드포인트 감지 및 응답</span><span class="sxs-lookup"><span data-stu-id="2efd0-160">Endpoint detection and response</span></span>

1.  <span data-ttu-id="2efd0-161">MEM 포털을 열 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2efd0-161">Open the MEM portal.</span></span>

2.  <span data-ttu-id="2efd0-162">끝점 검색 및 **> 끝점 보안 으로 이동합니다.**</span><span class="sxs-lookup"><span data-stu-id="2efd0-162">Navigate to **Endpoint security > Endpoint detection and response**.</span></span> <span data-ttu-id="2efd0-163">프로필 **만들기를 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="2efd0-163">Click on **Create Profile**.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="2efd0-164">![Microsoft Endpoint Manager 포털의 이미지4](images/58dcd48811147feb4ddc17212b7fe840.png)</span><span class="sxs-lookup"><span data-stu-id="2efd0-164">![Image of Microsoft Endpoint Manager portal4](images/58dcd48811147feb4ddc17212b7fe840.png)</span></span>

3.  <span data-ttu-id="2efd0-165">플랫폼에서 **Windows 10 이상, 프로필 - 끝점** 감지 및 응답 만들기를 > 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="2efd0-165">Under **Platform, select Windows 10 and Later, Profile - Endpoint detection and response > Create**.</span></span>

4.  <span data-ttu-id="2efd0-166">이름과 설명을 입력하고 다음 을 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="2efd0-166">Enter a name and description, then select  **Next**.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="2efd0-167">![Microsoft Endpoint Manager 포털의 이미지5](images/a5b2d23bdd50b160fef4afd25dda28d4.png)</span><span class="sxs-lookup"><span data-stu-id="2efd0-167">![Image of Microsoft Endpoint Manager portal5](images/a5b2d23bdd50b160fef4afd25dda28d4.png)</span></span>

5.  <span data-ttu-id="2efd0-168">필요한 설정을 선택하고 다음 을 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="2efd0-168">Select settings as required, then select  **Next**.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="2efd0-169">![Microsoft Endpoint Manager 포털의 이미지6](images/cea7e288b5d42a9baf1aef0754ade910.png)</span><span class="sxs-lookup"><span data-stu-id="2efd0-169">![Image of Microsoft Endpoint Manager portal6](images/cea7e288b5d42a9baf1aef0754ade910.png)</span></span>

    > [!NOTE]
    > <span data-ttu-id="2efd0-170">이 경우 이는 Endpoint용 Defender가 이미 Intune에 통합되어 있는 것으로 자동 채워진 것입니다.</span><span class="sxs-lookup"><span data-stu-id="2efd0-170">In this instance, this has been auto populated as Defender for Endpoint has already been integrated with Intune.</span></span> <span data-ttu-id="2efd0-171">통합에 대한 자세한 내용은 [Intune에서 끝점에 대해 Microsoft Defender 사용 을 참조하세요.](https://docs.microsoft.com/mem/intune/protect/advanced-threat-protection-configure#to-enable-microsoft-defender-atp)</span><span class="sxs-lookup"><span data-stu-id="2efd0-171">For more information on the integration, see [Enable Microsoft Defender for Endpoint in Intune](https://docs.microsoft.com/mem/intune/protect/advanced-threat-protection-configure#to-enable-microsoft-defender-atp).</span></span>
    > 
    > <span data-ttu-id="2efd0-172">다음 이미지는 끝점용 Microsoft Defender가 Intune과 통합되지 않은 경우 볼 수 있는 예제입니다.</span><span class="sxs-lookup"><span data-stu-id="2efd0-172">The following image is an example of what you'll see when Microsoft Defender for Endpoint is NOT integrated with Intune:</span></span>
    >
    > ![Microsoft Endpoint Manager 포털의 이미지7](images/2466460812371ffae2d19a10c347d6f4.png)

6.  <span data-ttu-id="2efd0-174">필요한 경우 범위 태그를 추가하고 다음 을 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="2efd0-174">Add scope tags if necessary, then select  **Next**.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="2efd0-175">![Microsoft Endpoint Manager Portal의 이미지8](images/ef844f52ec2c0d737ce793f68b5e8408.png)</span><span class="sxs-lookup"><span data-stu-id="2efd0-175">![Image of Microsoft Endpoint Manager portal8](images/ef844f52ec2c0d737ce793f68b5e8408.png)</span></span>

7.  <span data-ttu-id="2efd0-176">포함할 그룹 선택을  클릭하여 테스트 그룹을 추가하고 그룹을 선택한 후 다음 을 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="2efd0-176">Add test group by clicking on **Select groups to include** and choose your group, then select  **Next**.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="2efd0-177">![Microsoft Endpoint Manager 포털의 이미지9](images/fc3525e20752da026ec9f46ab4fec64f.png)</span><span class="sxs-lookup"><span data-stu-id="2efd0-177">![Image of Microsoft Endpoint Manager portal9](images/fc3525e20752da026ec9f46ab4fec64f.png)</span></span>

8.  <span data-ttu-id="2efd0-178">검토하고 수락한 다음 만들기를 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="2efd0-178">Review and accept, then select  **Create**.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="2efd0-179">![Microsoft Endpoint Manager 포털의 이미지10](images/289172dbd7bd34d55d24810d9d4d8158.png)</span><span class="sxs-lookup"><span data-stu-id="2efd0-179">![Image of Microsoft Endpoint Manager portal10](images/289172dbd7bd34d55d24810d9d4d8158.png)</span></span>

9.  <span data-ttu-id="2efd0-180">완료된 정책을 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2efd0-180">You can view your completed policy.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="2efd0-181">![Microsoft Endpoint Manager 포털의 이미지11](images/5a568b6878be8243ea2b9d82d41ed297.png)</span><span class="sxs-lookup"><span data-stu-id="2efd0-181">![Image of Microsoft Endpoint Manager portal11](images/5a568b6878be8243ea2b9d82d41ed297.png)</span></span>

### <a name="next-generation-protection"></a><span data-ttu-id="2efd0-182">차세대 보호</span><span class="sxs-lookup"><span data-stu-id="2efd0-182">Next-generation protection</span></span>

1.  <span data-ttu-id="2efd0-183">MEM 포털을 열 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2efd0-183">Open the MEM portal.</span></span>

2.  <span data-ttu-id="2efd0-184">정책 **만들기 에서 끝점**> 바이러스 > 로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="2efd0-184">Navigate to **Endpoint security > Antivirus > Create Policy**.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="2efd0-185">![Microsoft Endpoint Manager 포털의 이미지12](images/6b728d6e0d71108d768e368b416ff8ba.png)</span><span class="sxs-lookup"><span data-stu-id="2efd0-185">![Image of Microsoft Endpoint Manager portal12](images/6b728d6e0d71108d768e368b416ff8ba.png)</span></span>

3.  <span data-ttu-id="2efd0-186">플랫폼 **선택 - Windows 10 이상 - Windows 및 프로필 - Microsoft Defender** 바이러스 백신 > 만들기 .</span><span class="sxs-lookup"><span data-stu-id="2efd0-186">Select **Platform - Windows 10 and Later - Windows and Profile – Microsoft Defender Antivirus > Create**.</span></span>

4.  <span data-ttu-id="2efd0-187">이름 및 설명을 입력하고 다음 을 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="2efd0-187">Enter name and description, then select  **Next**.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="2efd0-188">![Microsoft Endpoint Manager 포털의 이미지13](images/a7d738dd4509d65407b7d12beaa3e917.png)</span><span class="sxs-lookup"><span data-stu-id="2efd0-188">![Image of Microsoft Endpoint Manager portal13](images/a7d738dd4509d65407b7d12beaa3e917.png)</span></span>

5.  <span data-ttu-id="2efd0-189">구성 **설정 페이지:** Microsoft Defender 바이러스 백신(클라우드 보호, 제외, Real-Time 보호 및 수정)에 필요한 구성을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="2efd0-189">In the **Configuration settings page**: Set the configurations you require for Microsoft Defender Antivirus (Cloud Protection, Exclusions, Real-Time Protection, and Remediation).</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="2efd0-190">![Microsoft Endpoint Manager 포털의 이미지14](images/3840b1576d6f79a1d72eb14760ef5e8c.png)</span><span class="sxs-lookup"><span data-stu-id="2efd0-190">![Image of Microsoft Endpoint Manager portal14](images/3840b1576d6f79a1d72eb14760ef5e8c.png)</span></span>

6.  <span data-ttu-id="2efd0-191">필요한 경우 범위 태그를 추가하고 다음 을 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="2efd0-191">Add scope tags if necessary, then select  **Next**.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="2efd0-192">![Microsoft Endpoint Manager 포털의 이미지15](images/2055e4f9b9141525c0eb681e7ba19381.png)</span><span class="sxs-lookup"><span data-stu-id="2efd0-192">![Image of Microsoft Endpoint Manager portal15](images/2055e4f9b9141525c0eb681e7ba19381.png)</span></span>

7.  <span data-ttu-id="2efd0-193">포함할 그룹을 선택하고 테스트 그룹에 할당한 후 다음 을 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="2efd0-193">Select groups to include, assign to your test group, then select  **Next**.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="2efd0-194">![Microsoft Endpoint Manager 포털의 이미지16](images/48318a51adee06bff3908e8ad4944dc9.png)</span><span class="sxs-lookup"><span data-stu-id="2efd0-194">![Image of Microsoft Endpoint Manager portal16](images/48318a51adee06bff3908e8ad4944dc9.png)</span></span>

8.  <span data-ttu-id="2efd0-195">검토하고 만든 다음 만들기를 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="2efd0-195">Review and create, then select  **Create**.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="2efd0-196">![Microsoft Endpoint Manager 포털의 이미지17](images/dfdadab79112d61bd3693d957084b0ec.png)</span><span class="sxs-lookup"><span data-stu-id="2efd0-196">![Image of Microsoft Endpoint Manager portal17](images/dfdadab79112d61bd3693d957084b0ec.png)</span></span>

9.  <span data-ttu-id="2efd0-197">만든 구성 정책이 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2efd0-197">You'll see the configuration policy you created.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="2efd0-198">![Microsoft Endpoint Manager 포털의 이미지18](images/38180219e632d6e4ec7bd25a46398da8.png)</span><span class="sxs-lookup"><span data-stu-id="2efd0-198">![Image of Microsoft Endpoint Manager portal18](images/38180219e632d6e4ec7bd25a46398da8.png)</span></span>

### <a name="attack-surface-reduction--attack-surface-reduction-rules"></a><span data-ttu-id="2efd0-199">공격 표면 감소 – 공격 표면 감소 규칙</span><span class="sxs-lookup"><span data-stu-id="2efd0-199">Attack Surface Reduction – Attack surface reduction rules</span></span>

1.  <span data-ttu-id="2efd0-200">MEM 포털을 열 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2efd0-200">Open the MEM portal.</span></span>

2.  <span data-ttu-id="2efd0-201">끝점 **보안 및 공격 > 축소로 이동합니다.**</span><span class="sxs-lookup"><span data-stu-id="2efd0-201">Navigate to **Endpoint security > Attack surface reduction**.</span></span>

3.  <span data-ttu-id="2efd0-202">정책 **만들기 를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="2efd0-202">Select  **Create Policy**.</span></span>

4.  <span data-ttu-id="2efd0-203">플랫폼 **선택 - Windows 10 이상 - 프로필 - 만들기에서** 공격 표면 > 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="2efd0-203">Select **Platform - Windows 10 and Later – Profile - Attack surface reduction rules > Create**.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="2efd0-204">![Microsoft Endpoint Manager 포털의 이미지19](images/522d9bb4288dc9c1a957392b51384fdd.png)</span><span class="sxs-lookup"><span data-stu-id="2efd0-204">![Image of Microsoft Endpoint Manager portal19](images/522d9bb4288dc9c1a957392b51384fdd.png)</span></span>

5.  <span data-ttu-id="2efd0-205">이름과 설명을 입력하고 다음 을 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="2efd0-205">Enter a name and description, then select  **Next**.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="2efd0-206">![Microsoft Endpoint Manager Portal의 이미지20](images/a5a71fd73ec389f3cdce6d1a6bd1ff31.png)</span><span class="sxs-lookup"><span data-stu-id="2efd0-206">![Image of Microsoft Endpoint Manager portal20](images/a5a71fd73ec389f3cdce6d1a6bd1ff31.png)</span></span>

6.  <span data-ttu-id="2efd0-207">구성 **설정 페이지에서**: 공격 표면 감소 규칙에 필요한 구성을 설정하고 다음 을 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="2efd0-207">In the **Configuration settings page**: Set the configurations you require for Attack surface reduction rules, then select  **Next**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="2efd0-208">모든 공격 표면 감소 규칙을 감사로 구성할 것입니다.</span><span class="sxs-lookup"><span data-stu-id="2efd0-208">We will be configuring all of the Attack surface reduction rules to Audit.</span></span>
    > 
    > <span data-ttu-id="2efd0-209">자세한 내용은 공격 표면 [감소 규칙을 참조하세요.](attack-surface-reduction.md)</span><span class="sxs-lookup"><span data-stu-id="2efd0-209">For more information, see [Attack surface reduction rules](attack-surface-reduction.md).</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="2efd0-210">![Microsoft Endpoint Manager 포털의 이미지21](images/dd0c00efe615a64a4a368f54257777d0.png)</span><span class="sxs-lookup"><span data-stu-id="2efd0-210">![Image of Microsoft Endpoint Manager portal21](images/dd0c00efe615a64a4a368f54257777d0.png)</span></span>

7.  <span data-ttu-id="2efd0-211">필요한 경우 범위 태그를 추가하고 다음 을 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="2efd0-211">Add Scope Tags as required, then select  **Next**.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="2efd0-212">![Microsoft Endpoint Manager 포털의 이미지22](images/6daa8d347c98fe94a0d9c22797ff6f28.png)</span><span class="sxs-lookup"><span data-stu-id="2efd0-212">![Image of Microsoft Endpoint Manager portal22](images/6daa8d347c98fe94a0d9c22797ff6f28.png)</span></span>

8.  <span data-ttu-id="2efd0-213">포함할 그룹을 선택하고 테스트 그룹에 할당한 후 다음 을 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="2efd0-213">Select groups to include and assign to test group, then select  **Next**.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="2efd0-214">![Microsoft Endpoint Manager 포털의 이미지23](images/45cefc8e4e474321b4d47b4626346597.png)</span><span class="sxs-lookup"><span data-stu-id="2efd0-214">![Image of Microsoft Endpoint Manager portal23](images/45cefc8e4e474321b4d47b4626346597.png)</span></span>

9. <span data-ttu-id="2efd0-215">세부 정보를 검토한 다음 만들기 를 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="2efd0-215">Review the details, then select  **Create**.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="2efd0-216">![Microsoft Endpoint Manager portal24의 이미지](images/2c2e87c5fedc87eba17be0cdeffdb17f.png)</span><span class="sxs-lookup"><span data-stu-id="2efd0-216">![Image of Microsoft Endpoint Manager portal24](images/2c2e87c5fedc87eba17be0cdeffdb17f.png)</span></span>

10. <span data-ttu-id="2efd0-217">정책을 시청합니다.</span><span class="sxs-lookup"><span data-stu-id="2efd0-217">View the policy.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="2efd0-218">![Microsoft Endpoint Manager 포털의 이미지25](images/7a631d17cc42500dacad4e995823ffef.png)</span><span class="sxs-lookup"><span data-stu-id="2efd0-218">![Image of Microsoft Endpoint Manager portal25](images/7a631d17cc42500dacad4e995823ffef.png)</span></span>

### <a name="attack-surface-reduction--web-protection"></a><span data-ttu-id="2efd0-219">공격 표면 감소 – 웹 보호</span><span class="sxs-lookup"><span data-stu-id="2efd0-219">Attack Surface Reduction – Web Protection</span></span>

1.  <span data-ttu-id="2efd0-220">MEM 포털을 열 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2efd0-220">Open the MEM portal.</span></span>

2.  <span data-ttu-id="2efd0-221">끝점 **보안 및 공격 > 축소로 이동합니다.**</span><span class="sxs-lookup"><span data-stu-id="2efd0-221">Navigate to **Endpoint security > Attack surface reduction**.</span></span>

3.  <span data-ttu-id="2efd0-222">정책 **만들기 를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="2efd0-222">Select  **Create Policy**.</span></span>

4.  <span data-ttu-id="2efd0-223">**Windows 10 이상 – 웹** 보호 및 > 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="2efd0-223">Select **Windows 10 and Later – Web protection > Create**.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="2efd0-224">![Microsoft Endpoint Manager 포털의 이미지26](images/cd7b5a1cbc16cc05f878cdc99ba4c27f.png)</span><span class="sxs-lookup"><span data-stu-id="2efd0-224">![Image of Microsoft Endpoint Manager portal26](images/cd7b5a1cbc16cc05f878cdc99ba4c27f.png)</span></span>

5.  <span data-ttu-id="2efd0-225">이름과 설명을 입력하고 다음 을 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="2efd0-225">Enter a name and description, then select  **Next**.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="2efd0-226">![Microsoft Endpoint Manager 포털의 이미지27](images/5be573a60cd4fa56a86a6668b62dd808.png)</span><span class="sxs-lookup"><span data-stu-id="2efd0-226">![Image of Microsoft Endpoint Manager portal27](images/5be573a60cd4fa56a86a6668b62dd808.png)</span></span>

6.  <span data-ttu-id="2efd0-227">구성 **설정 페이지:** 웹 보호에 필요한 구성을 설정하고 다음 을 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="2efd0-227">In the **Configuration settings page**: Set the configurations you require for Web Protection, then select  **Next**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="2efd0-228">웹 보호를 차단으로 구성하고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2efd0-228">We are configuring Web Protection to Block.</span></span>
    > 
    > <span data-ttu-id="2efd0-229">자세한 내용은 Web [Protection 을 참조하세요.](web-protection-overview.md)</span><span class="sxs-lookup"><span data-stu-id="2efd0-229">For more information, see [Web Protection](web-protection-overview.md).</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="2efd0-230">![Microsoft Endpoint Manager 포털의 이미지28](images/6104aa33a56fab750cf30ecabef9f5b6.png)</span><span class="sxs-lookup"><span data-stu-id="2efd0-230">![Image of Microsoft Endpoint Manager portal28](images/6104aa33a56fab750cf30ecabef9f5b6.png)</span></span>

7.  <span data-ttu-id="2efd0-231">다음에 필요한 범위 **> 추가합니다.**</span><span class="sxs-lookup"><span data-stu-id="2efd0-231">Add **Scope Tags as required > Next**.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="2efd0-232">![Microsoft Endpoint Manager 포털의 이미지29](images/6daa8d347c98fe94a0d9c22797ff6f28.png)</span><span class="sxs-lookup"><span data-stu-id="2efd0-232">![Image of Microsoft Endpoint Manager portal29](images/6daa8d347c98fe94a0d9c22797ff6f28.png)</span></span>

8.  <span data-ttu-id="2efd0-233">다음에서 테스트 그룹에 **할당을 > 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="2efd0-233">Select **Assign to test group > Next**.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="2efd0-234">![Microsoft Endpoint Manager portal30 이미지](images/45cefc8e4e474321b4d47b4626346597.png)</span><span class="sxs-lookup"><span data-stu-id="2efd0-234">![Image of Microsoft Endpoint Manager portal30](images/45cefc8e4e474321b4d47b4626346597.png)</span></span>

9.  <span data-ttu-id="2efd0-235">검토 **및 만들기를 > 를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="2efd0-235">Select **Review and Create > Create**.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="2efd0-236">![Microsoft Endpoint Manager 포털의 이미지31](images/8ee0405f1a96c23d2eb6f737f11c1ae5.png)</span><span class="sxs-lookup"><span data-stu-id="2efd0-236">![Image of Microsoft Endpoint Manager portal31](images/8ee0405f1a96c23d2eb6f737f11c1ae5.png)</span></span>

10. <span data-ttu-id="2efd0-237">정책을 시청합니다.</span><span class="sxs-lookup"><span data-stu-id="2efd0-237">View the policy.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="2efd0-238">![Microsoft Endpoint Manager 포털의 이미지32](images/e74f6f6c150d017a286e6ed3dffb7757.png)</span><span class="sxs-lookup"><span data-stu-id="2efd0-238">![Image of Microsoft Endpoint Manager portal32](images/e74f6f6c150d017a286e6ed3dffb7757.png)</span></span>

## <a name="validate-configuration-settings"></a><span data-ttu-id="2efd0-239">구성 설정 유효성 검사</span><span class="sxs-lookup"><span data-stu-id="2efd0-239">Validate configuration settings</span></span>


### <a name="confirm-policies-have-been-applied"></a><span data-ttu-id="2efd0-240">정책이 적용된지 확인</span><span class="sxs-lookup"><span data-stu-id="2efd0-240">Confirm Policies have been applied</span></span>


<span data-ttu-id="2efd0-241">구성 정책이 할당된 후 적용하는 데 시간이 다소 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2efd0-241">Once the Configuration policy has been assigned, it will take some time to apply.</span></span>

<span data-ttu-id="2efd0-242">타이밍에 대한 자세한 내용은 [Intune 구성 정보를 참조하세요.](https://docs.microsoft.com/mem/intune/configuration/device-profile-troubleshoot#how-long-does-it-take-for-devices-to-get-a-policy-profile-or-app-after-they-are-assigned)</span><span class="sxs-lookup"><span data-stu-id="2efd0-242">For information on timing, see [Intune configuration information](https://docs.microsoft.com/mem/intune/configuration/device-profile-troubleshoot#how-long-does-it-take-for-devices-to-get-a-policy-profile-or-app-after-they-are-assigned).</span></span>

<span data-ttu-id="2efd0-243">구성 정책이 테스트 장치에 적용되어 있는지 확인하려면 각 구성 정책에 대해 다음 프로세스를 따르하세요.</span><span class="sxs-lookup"><span data-stu-id="2efd0-243">To confirm that the configuration policy has been applied to your test device, follow the following process for each configuration policy.</span></span>

1.  <span data-ttu-id="2efd0-244">MEM 포털을 열고 위의 단계에 표시된 대로 관련 정책으로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="2efd0-244">Open the MEM portal and navigate to the relevant policy as shown in the steps above.</span></span> <span data-ttu-id="2efd0-245">다음 예에서는 차세대 보호 설정을 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="2efd0-245">The following example shows the next generation protection settings.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="2efd0-246">[![Microsoft Endpoint Manager 포털의 이미지33 ](images/43ab6aa74471ee2977e154a4a5ef2d39.png)](images/43ab6aa74471ee2977e154a4a5ef2d39.png#lightbox)</span><span class="sxs-lookup"><span data-stu-id="2efd0-246">[ ![Image of Microsoft Endpoint Manager portal33](images/43ab6aa74471ee2977e154a4a5ef2d39.png) ](images/43ab6aa74471ee2977e154a4a5ef2d39.png#lightbox)</span></span>

2.  <span data-ttu-id="2efd0-247">정책 **상태를 확인하려면** 구성 정책을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="2efd0-247">Select  the **Configuration Policy** to view the policy status.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="2efd0-248">[![Microsoft Endpoint Manager portal34의 이미지 ](images/55ecaca0e4a022f0e29d45aeed724e6c.png)](images/55ecaca0e4a022f0e29d45aeed724e6c.png#lightbox)</span><span class="sxs-lookup"><span data-stu-id="2efd0-248">[ ![Image of Microsoft Endpoint Manager portal34](images/55ecaca0e4a022f0e29d45aeed724e6c.png) ](images/55ecaca0e4a022f0e29d45aeed724e6c.png#lightbox)</span></span>

3.  <span data-ttu-id="2efd0-249">장치  **상태를 선택하여** 상태를 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="2efd0-249">Select  **Device Status** to see the status.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="2efd0-250">[![Microsoft Endpoint Manager 포털의 이미지35 ](images/18a50df62cc38749000dbfb48e9a4c9b.png)](images/18a50df62cc38749000dbfb48e9a4c9b.png#lightbox)</span><span class="sxs-lookup"><span data-stu-id="2efd0-250">[ ![Image of Microsoft Endpoint Manager portal35](images/18a50df62cc38749000dbfb48e9a4c9b.png) ](images/18a50df62cc38749000dbfb48e9a4c9b.png#lightbox)</span></span>

4.  <span data-ttu-id="2efd0-251">상태를  **확인하려면** 사용자 상태를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="2efd0-251">Select  **User Status** to see the status.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="2efd0-252">[![Microsoft Endpoint Manager 포털의 이미지36 ](images/4e965749ff71178af8873bc91f9fe525.png)](images/4e965749ff71178af8873bc91f9fe525.png#lightbox)</span><span class="sxs-lookup"><span data-stu-id="2efd0-252">[ ![Image of Microsoft Endpoint Manager portal36](images/4e965749ff71178af8873bc91f9fe525.png) ](images/4e965749ff71178af8873bc91f9fe525.png#lightbox)</span></span>

5.  <span data-ttu-id="2efd0-253">상태를  **확인하려면** 설정당 상태를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="2efd0-253">Select  **Per-setting status** to see the status.</span></span>

    >[!TIP]
    ><span data-ttu-id="2efd0-254">이 보기는 다른 정책과 충돌하는 설정을 식별하는 데 매우 유용합니다.</span><span class="sxs-lookup"><span data-stu-id="2efd0-254">This view is very useful to identify any settings that conflict with another policy.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="2efd0-255">[![Microsoft Endpoint Manager 포털의 이미지37 ](images/42acc69d0128ed09804010bdbdf0a43c.png)](images/42acc69d0128ed09804010bdbdf0a43c.png#lightbox)</span><span class="sxs-lookup"><span data-stu-id="2efd0-255">[ ![Image of Microsoft Endpoint Manager portal37](images/42acc69d0128ed09804010bdbdf0a43c.png) ](images/42acc69d0128ed09804010bdbdf0a43c.png#lightbox)</span></span>

### <a name="endpoint-detection-and-response"></a><span data-ttu-id="2efd0-256">엔드포인트 감지 및 응답</span><span class="sxs-lookup"><span data-stu-id="2efd0-256">Endpoint detection and response</span></span>


1.  <span data-ttu-id="2efd0-257">구성을 적용하기 전에 Endpoint Protection용 Defender 서비스를 시작하지 말아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2efd0-257">Before applying the configuration, the Defender for Endpoint Protection service should not be started.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="2efd0-258">[![서비스 패널 1의 이미지 ](images/b418a232a12b3d0a65fc98248dbb0e31.png)](images/b418a232a12b3d0a65fc98248dbb0e31.png#lightbox)</span><span class="sxs-lookup"><span data-stu-id="2efd0-258">[ ![Image of Services panel1](images/b418a232a12b3d0a65fc98248dbb0e31.png) ](images/b418a232a12b3d0a65fc98248dbb0e31.png#lightbox)</span></span>

2.  <span data-ttu-id="2efd0-259">구성이 적용된 후 Endpoint Protection Service용 Defender를 시작해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2efd0-259">After the configuration has been applied, the Defender for Endpoint Protection Service should be started.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="2efd0-260">[![서비스 패널 2의 이미지 ](images/a621b699899f1b41db211170074ea59e.png)](images/a621b699899f1b41db211170074ea59e.png#lightbox)</span><span class="sxs-lookup"><span data-stu-id="2efd0-260">[ ![Image of Services panel2](images/a621b699899f1b41db211170074ea59e.png) ](images/a621b699899f1b41db211170074ea59e.png#lightbox)</span></span>

3.  <span data-ttu-id="2efd0-261">장치에서 서비스가 실행되고 나면 장치가 Microsoft Defender 보안 센터에 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="2efd0-261">After the services are running on the device, the device appears in Microsoft Defender Security Center.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="2efd0-262">[![Microsoft Defender 보안 센터의 이미지 ](images/df0c64001b9219cfbd10f8f81a273190.png)](images/df0c64001b9219cfbd10f8f81a273190.png#lightbox)</span><span class="sxs-lookup"><span data-stu-id="2efd0-262">[ ![Image of Microsoft Defender Security Center](images/df0c64001b9219cfbd10f8f81a273190.png) ](images/df0c64001b9219cfbd10f8f81a273190.png#lightbox)</span></span>

### <a name="next-generation-protection"></a><span data-ttu-id="2efd0-263">차세대 보호</span><span class="sxs-lookup"><span data-stu-id="2efd0-263">Next-generation protection</span></span>

1.  <span data-ttu-id="2efd0-264">테스트 장치에 정책을 적용하기 전에 아래 표시된 설정을 수동으로 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2efd0-264">Before applying the policy on a test device, you should be able to manually manage the settings as shown below.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="2efd0-265">![page1 설정 이미지](images/88efb4c3710493a53f2840c3eac3e3d3.png)</span><span class="sxs-lookup"><span data-stu-id="2efd0-265">![Image of setting page1](images/88efb4c3710493a53f2840c3eac3e3d3.png)</span></span>

2.  <span data-ttu-id="2efd0-266">정책이 적용된 후 설정을 수동으로 관리할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="2efd0-266">After the policy has been applied, you should not be able to manually manage the settings.</span></span>

    > [!NOTE]
    > <span data-ttu-id="2efd0-267">다음 이미지에서 **클라우드 제공** 보호 켜기 및 실시간 보호 켜기가 관리되는 것으로 표시됩니다. </span><span class="sxs-lookup"><span data-stu-id="2efd0-267">In the following image **Turn on cloud-delivered protection** and **Turn on real-time protection** are being shown as managed.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="2efd0-268">![page2 설정 이미지](images/9341428b2d3164ca63d7d4eaa5cff642.png)</span><span class="sxs-lookup"><span data-stu-id="2efd0-268">![Image of setting page2](images/9341428b2d3164ca63d7d4eaa5cff642.png)</span></span>

### <a name="attack-surface-reduction--attack-surface-reduction-rules"></a><span data-ttu-id="2efd0-269">공격 표면 감소 – 공격 표면 감소 규칙</span><span class="sxs-lookup"><span data-stu-id="2efd0-269">Attack Surface Reduction – Attack surface reduction rules</span></span>


1.  <span data-ttu-id="2efd0-270">테스트 장치에 정책을 적용하기 전에 PowerShell 창을 펜으로 처리하고 를 `Get-MpPreference` 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="2efd0-270">Before applying the policy on a test device, pen a PowerShell Window and type `Get-MpPreference`.</span></span>

2.  <span data-ttu-id="2efd0-271">콘텐츠가 없는 다음 줄로 응답해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2efd0-271">This should respond with the following lines with no content:</span></span>

    > <span data-ttu-id="2efd0-272">AttackSurfaceReductionOnlyExclusions:</span><span class="sxs-lookup"><span data-stu-id="2efd0-272">AttackSurfaceReductionOnlyExclusions:</span></span>
    > 
    > <span data-ttu-id="2efd0-273">AttackSurfaceReductionRules_Actions:</span><span class="sxs-lookup"><span data-stu-id="2efd0-273">AttackSurfaceReductionRules_Actions:</span></span>
    > 
    > <span data-ttu-id="2efd0-274">AttackSurfaceReductionRules_Ids:</span><span class="sxs-lookup"><span data-stu-id="2efd0-274">AttackSurfaceReductionRules_Ids:</span></span>

    ![명령줄 1의 이미지](images/cb0260d4b2636814e37eee427211fe71.png)

3.  <span data-ttu-id="2efd0-276">테스트 장치에 정책을 적용한 후 PowerShell Windows를 열고 를 `Get-MpPreference` 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="2efd0-276">After applying the policy on a test device, open a PowerShell Windows and type `Get-MpPreference`.</span></span>

4.  <span data-ttu-id="2efd0-277">아래와 같이 콘텐츠가 있는 다음 줄로 응답해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2efd0-277">This should respond with the following lines with content as shown below:</span></span>

    ![명령줄 2의 이미지](images/619fb877791b1fc8bc7dfae1a579043d.png)

### <a name="attack-surface-reduction--web-protection"></a><span data-ttu-id="2efd0-279">공격 표면 감소 – 웹 보호</span><span class="sxs-lookup"><span data-stu-id="2efd0-279">Attack Surface Reduction – Web Protection</span></span>

1.  <span data-ttu-id="2efd0-280">테스트 장치에서 PowerShell Windows를 열고 를 `(Get-MpPreference).EnableNetworkProtection` 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="2efd0-280">On the test device, open a PowerShell Windows and type `(Get-MpPreference).EnableNetworkProtection`.</span></span>

2.  <span data-ttu-id="2efd0-281">아래와 같이 0으로 응답해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2efd0-281">This should respond with a 0 as shown below.</span></span>

    ![명령줄 3의 이미지](images/196a8e194ac99d84221f405d0f684f8c.png)

3.  <span data-ttu-id="2efd0-283">정책을 적용한 후 PowerShell Windows를 열고 를 `(Get-MpPreference).EnableNetworkProtection` 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="2efd0-283">After applying the policy, open a PowerShell Windows and type `(Get-MpPreference).EnableNetworkProtection`.</span></span>

4.  <span data-ttu-id="2efd0-284">아래와 같이 1로 응답해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2efd0-284">This should respond with a 1 as shown below.</span></span>

    ![명령줄 4의 이미지](images/c06fa3bbc2f70d59dfe1e106cd9a4683.png)
