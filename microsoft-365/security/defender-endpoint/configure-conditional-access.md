---
title: Microsoft Defender ATP에서 조건부 액세스 구성
description: 조건부 액세스를 구현하기 위해 Intune, Microsoft Defender 보안 센터 및 Azure에서 해야 하는 단계에 대해 자세히 알아보십시오.
keywords: 조건부 액세스, 조건부, 액세스, 장치 위험, 위험 수준, 통합, intune 통합
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 0185d7875ac149909ef088d041383a1cf36a8a3a
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/24/2021
ms.locfileid: "51165864"
---
# <a name="configure-conditional-access-in-microsoft-defender-for-endpoint"></a><span data-ttu-id="867b8-104">끝점용 Microsoft Defender에서 조건부 액세스 구성</span><span class="sxs-lookup"><span data-stu-id="867b8-104">Configure Conditional Access in Microsoft Defender for Endpoint</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="867b8-105">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="867b8-105">**Applies to:**</span></span>
- [<span data-ttu-id="867b8-106">엔드포인트용 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="867b8-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="867b8-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="867b8-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="867b8-108">Endpoint용 Defender를 경험하고 싶나요?</span><span class="sxs-lookup"><span data-stu-id="867b8-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="867b8-109">무료 평가판에 등록합니다.</span><span class="sxs-lookup"><span data-stu-id="867b8-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-assignaccess-abovefoldlink)

<span data-ttu-id="867b8-110">이 섹션에서는 조건부 액세스를 올바르게 구현하기 위해 필요한 모든 단계를 안내합니다.</span><span class="sxs-lookup"><span data-stu-id="867b8-110">This section guides you through all the steps you need to take to properly implement Conditional Access.</span></span>

### <a name="before-you-begin"></a><span data-ttu-id="867b8-111">시작하기 전에</span><span class="sxs-lookup"><span data-stu-id="867b8-111">Before you begin</span></span>
>[!WARNING]
><span data-ttu-id="867b8-112">이 시나리오에서는 Azure AD 등록 장치가 지원되지 않는다는 점에 유의해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="867b8-112">It's important to note that Azure AD registered devices is not supported in this scenario.</span></span></br>
><span data-ttu-id="867b8-113">Intune 등록 장치만 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="867b8-113">Only Intune enrolled devices are supported.</span></span>


<span data-ttu-id="867b8-114">모든 장치가 Intune에 등록된지 확인해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="867b8-114">You need to make sure that all your devices are enrolled in Intune.</span></span> <span data-ttu-id="867b8-115">다음 옵션 중 원하는 옵션을 사용하여 Intune에서 장치를 등록할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="867b8-115">You can use any of the following options to enroll devices in Intune:</span></span>


- <span data-ttu-id="867b8-116">IT 관리자: 자동 등록을 사용하도록 설정하는 방법에 대한 자세한 내용은 [Windows 등록을 참조하세요.](https://docs.microsoft.com/intune/windows-enroll#enable-windows-10-automatic-enrollment)</span><span class="sxs-lookup"><span data-stu-id="867b8-116">IT Admin: For more information on how to enabling auto-enrollment, see [Windows Enrollment](https://docs.microsoft.com/intune/windows-enroll#enable-windows-10-automatic-enrollment)</span></span>
- <span data-ttu-id="867b8-117">최종 사용자: Intune에서 Windows 10 장치를 등록하는 방법에 대한 자세한 내용은 [Intune에서 Windows 10 장치](https://docs.microsoft.com/intune/quickstart-enroll-windows-device) 등록을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="867b8-117">End-user: For more information on how to enroll your Windows 10 device in Intune, see [Enroll your Windows 10 device in Intune](https://docs.microsoft.com/intune/quickstart-enroll-windows-device)</span></span>
- <span data-ttu-id="867b8-118">최종 사용자 대체: Azure AD 도메인에 가입하는 방법에 대한 자세한 내용은 방법: Azure AD 조인 구현 계획을 [참조하세요.](https://docs.microsoft.com/azure/active-directory/devices/azureadjoin-plan)</span><span class="sxs-lookup"><span data-stu-id="867b8-118">End-user alternative: For more information on joining an Azure AD domain, see [How to: Plan your Azure AD join implementation](https://docs.microsoft.com/azure/active-directory/devices/azureadjoin-plan).</span></span>



<span data-ttu-id="867b8-119">Microsoft Defender 보안 센터, Intune 포털 및 Azure AD 포털에서 수행해야 하는 단계가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="867b8-119">There are steps you'll need to take in Microsoft Defender Security Center, the Intune portal, and Azure AD portal.</span></span>

<span data-ttu-id="867b8-120">이러한 포털에 액세스하고 조건부 액세스를 구현하는 데 필요한 역할을 주의해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="867b8-120">It's important to note the required roles to access these portals and implement Conditional access:</span></span>
- <span data-ttu-id="867b8-121">**Microsoft Defender 보안 센터** - 통합을 켜기 위해 전역 관리자 역할로 포털에 로그인해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="867b8-121">**Microsoft Defender Security Center** - You'll need to sign into the portal with a global administrator role to turn on the integration.</span></span>
- <span data-ttu-id="867b8-122">**Intune** - 관리 권한이 있는 보안 관리자 권한으로 포털에 로그인해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="867b8-122">**Intune** - You'll need to sign in to the portal with security administrator rights with management permissions.</span></span> 
- <span data-ttu-id="867b8-123">**Azure AD 포털** - 전역 관리자, 보안 관리자 또는 조건부 액세스 관리자로 로그인해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="867b8-123">**Azure AD portal** - You'll need to sign in as a global administrator, security administrator, or Conditional Access administrator.</span></span>


> [!NOTE]
> <span data-ttu-id="867b8-124">Intune 관리 및 Azure AD에 가입된 Windows 10 장치를 사용하여 Microsoft Intune 환경이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="867b8-124">You'll need a Microsoft Intune environment, with Intune managed and Azure AD joined Windows 10 devices.</span></span>

<span data-ttu-id="867b8-125">조건부 액세스를 사용하도록 설정하려면 다음 단계를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="867b8-125">Take the following steps to enable Conditional Access:</span></span>
- <span data-ttu-id="867b8-126">1단계: Microsoft Defender 보안 센터에서 Microsoft Intune 연결 켜기</span><span class="sxs-lookup"><span data-stu-id="867b8-126">Step 1: Turn on the Microsoft Intune connection from Microsoft Defender Security Center</span></span>
- <span data-ttu-id="867b8-127">2단계: Intune에서 끝점에 대한 Defender 통합 켜기</span><span class="sxs-lookup"><span data-stu-id="867b8-127">Step 2: Turn on the Defender for Endpoint integration in Intune</span></span>
- <span data-ttu-id="867b8-128">3단계: Intune에서 준수 정책 만들기</span><span class="sxs-lookup"><span data-stu-id="867b8-128">Step 3: Create the compliance policy in Intune</span></span>
- <span data-ttu-id="867b8-129">4단계: 정책 할당</span><span class="sxs-lookup"><span data-stu-id="867b8-129">Step 4: Assign the policy</span></span> 
- <span data-ttu-id="867b8-130">5단계: Azure AD 조건부 액세스 정책 만들기</span><span class="sxs-lookup"><span data-stu-id="867b8-130">Step 5: Create an Azure AD Conditional Access policy</span></span>


### <a name="step-1-turn-on-the-microsoft-intune-connection"></a><span data-ttu-id="867b8-131">1단계: Microsoft Intune 연결 켜기</span><span class="sxs-lookup"><span data-stu-id="867b8-131">Step 1: Turn on the Microsoft Intune connection</span></span>
1. <span data-ttu-id="867b8-132">탐색 창에서 설정 **고급** 기능  >    >  **Microsoft Intune 연결을 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="867b8-132">In the navigation pane, select **Settings** > **Advanced features** > **Microsoft Intune connection**.</span></span>
2. <span data-ttu-id="867b8-133">Microsoft Intune 설정을 으로 **전환합니다.**</span><span class="sxs-lookup"><span data-stu-id="867b8-133">Toggle the Microsoft Intune setting to **On**.</span></span>
3. <span data-ttu-id="867b8-134">기본 **설정 저장을 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="867b8-134">Click **Save preferences**.</span></span>


### <a name="step-2-turn-on-the-defender-for-endpoint-integration-in-intune"></a><span data-ttu-id="867b8-135">2단계: Intune에서 끝점에 대한 Defender 통합 켜기</span><span class="sxs-lookup"><span data-stu-id="867b8-135">Step 2: Turn on the Defender for Endpoint integration in Intune</span></span>
1. <span data-ttu-id="867b8-136">[Azure 포털](https://portal.azure.com)에 로그인합니다.</span><span class="sxs-lookup"><span data-stu-id="867b8-136">Sign in to the [Azure portal](https://portal.azure.com).</span></span>
2. <span data-ttu-id="867b8-137">장치 **준수**  >  **Microsoft Defender ATP를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="867b8-137">Select **Device compliance** > **Microsoft Defender ATP**.</span></span>
3. <span data-ttu-id="867b8-138">**Windows 10.0.15063+ 장치를 Microsoft Defender Advanced Threat Protection에** 연결 을 으로 **설정**</span><span class="sxs-lookup"><span data-stu-id="867b8-138">Set **Connect Windows 10.0.15063+ devices to Microsoft Defender Advanced Threat Protection** to **On**.</span></span>
4. <span data-ttu-id="867b8-139">**저장** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="867b8-139">Click **Save**.</span></span>


### <a name="step-3-create-the-compliance-policy-in-intune"></a><span data-ttu-id="867b8-140">3단계: Intune에서 준수 정책 만들기</span><span class="sxs-lookup"><span data-stu-id="867b8-140">Step 3: Create the compliance policy in Intune</span></span>
1. <span data-ttu-id="867b8-141">Azure [Portal에서](https://portal.azure.com)모든 **서비스를** 선택하고 **Intune을** 필터링하고 **Microsoft Intune 을 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="867b8-141">In the [Azure portal](https://portal.azure.com), select **All services**, filter on **Intune**, and select **Microsoft Intune**.</span></span>
2. <span data-ttu-id="867b8-142">장치 **준수 정책**  >  **정책** 만들기 정책을  >  **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="867b8-142">Select **Device compliance** > **Policies** > **Create policy**.</span></span>
3. <span data-ttu-id="867b8-143">이름 및 **설명을** **입력합니다.**</span><span class="sxs-lookup"><span data-stu-id="867b8-143">Enter a **Name** and **Description**.</span></span>
4. <span data-ttu-id="867b8-144">**플랫폼에서** Windows **10 이상을 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="867b8-144">In **Platform**, select **Windows 10 and later**.</span></span>
5. <span data-ttu-id="867b8-145">장치 **상태 설정에서**  장치 위협 수준에 또는 장치 위협 수준 아래에 있도록 요구를 기본 설정 수준으로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="867b8-145">In the **Device Health** settings, set **Require the device to be at or under the Device Threat Level** to your preferred level:</span></span>

   - <span data-ttu-id="867b8-146">**보안 :** 이 수준이 가장 안전합니다.</span><span class="sxs-lookup"><span data-stu-id="867b8-146">**Secured**: This level is the most secure.</span></span> <span data-ttu-id="867b8-147">장치에 기존 위협이 없는 경우 회사 리소스에 계속 액세스할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="867b8-147">The device cannot have any existing threats and still access company resources.</span></span> <span data-ttu-id="867b8-148">위협이 발견되는 경우 장치는 비호조로 평가됩니다.</span><span class="sxs-lookup"><span data-stu-id="867b8-148">If any threats are found, the device is evaluated as noncompliant.</span></span>
   - <span data-ttu-id="867b8-149">**낮음:** 낮은 수준의 위협만 존재하는 경우 장치가 규격입니다.</span><span class="sxs-lookup"><span data-stu-id="867b8-149">**Low**: The device is compliant if only low-level threats exist.</span></span> <span data-ttu-id="867b8-150">중간 또는 높은 위협 수준이 있는 장치는 규정을 준수하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="867b8-150">Devices with medium or high threat levels are not compliant.</span></span>
   - <span data-ttu-id="867b8-151">**보통:** 장치에서 발견되는 위협이 낮거나 중간인 경우 장치가 규격입니다.</span><span class="sxs-lookup"><span data-stu-id="867b8-151">**Medium**: The device is compliant if the threats found on the device are low or medium.</span></span> <span data-ttu-id="867b8-152">높은 수준의 위협이 감지되면 장치가 비준수로 결정됩니다.</span><span class="sxs-lookup"><span data-stu-id="867b8-152">If high-level threats are detected, the device is determined as noncompliant.</span></span>
   - <span data-ttu-id="867b8-153">**높음:** 이 수준은 최소 보안 수준으로, 모든 위협 수준을 허용합니다.</span><span class="sxs-lookup"><span data-stu-id="867b8-153">**High**: This level is the least secure, and allows all threat levels.</span></span> <span data-ttu-id="867b8-154">따라서 높은, 중간 또는 낮은 위협 수준이 있는 장치는 규격으로 간주됩니다.</span><span class="sxs-lookup"><span data-stu-id="867b8-154">So devices that with high, medium or low threat levels are considered compliant.</span></span>

6. <span data-ttu-id="867b8-155">확인 **및** **만들기를 선택하여** 변경 내용을 저장하고 정책을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="867b8-155">Select **OK**, and **Create** to save your changes (and create the policy).</span></span>

### <a name="step-4-assign-the-policy"></a><span data-ttu-id="867b8-156">4단계: 정책 할당</span><span class="sxs-lookup"><span data-stu-id="867b8-156">Step 4: Assign the policy</span></span>
1. <span data-ttu-id="867b8-157">Azure [Portal에서](https://portal.azure.com)모든 **서비스를** 선택하고 **Intune을** 필터링하고 **Microsoft Intune 을 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="867b8-157">In the [Azure portal](https://portal.azure.com), select **All services**, filter on **Intune**, and select **Microsoft Intune**.</span></span>
2. <span data-ttu-id="867b8-158">장치 **준수 정책을>** Microsoft  >   Defender ATP 규정 준수 정책을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="867b8-158">Select **Device compliance** > **Policies**> select your Microsoft Defender ATP compliance policy.</span></span>
3. <span data-ttu-id="867b8-159">**과제** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="867b8-159">Select **Assignments**.</span></span>
4. <span data-ttu-id="867b8-160">Azure AD 그룹을 포함하거나 제외하여 정책을 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="867b8-160">Include or exclude your Azure AD groups to assign them the policy.</span></span>
5. <span data-ttu-id="867b8-161">그룹에 정책을 배포하려면 저장 을 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="867b8-161">To deploy the policy to the groups, select **Save**.</span></span> <span data-ttu-id="867b8-162">정책이 대상으로 하는 사용자 장치는 규정 준수로 평가됩니다.</span><span class="sxs-lookup"><span data-stu-id="867b8-162">The user devices targeted by the policy are evaluated for compliance.</span></span>

### <a name="step-5-create-an-azure-ad-conditional-access-policy"></a><span data-ttu-id="867b8-163">5단계: Azure AD 조건부 액세스 정책 만들기</span><span class="sxs-lookup"><span data-stu-id="867b8-163">Step 5: Create an Azure AD Conditional Access policy</span></span>
1. <span data-ttu-id="867b8-164">Azure [Portal에서](https://portal.azure.com) **Azure Active Directory**  >  **조건부 액세스 새 정책**  >  **을 열 수 있습니다.**</span><span class="sxs-lookup"><span data-stu-id="867b8-164">In the [Azure portal](https://portal.azure.com), open **Azure Active Directory** > **Conditional Access** > **New policy**.</span></span>
2. <span data-ttu-id="867b8-165">정책 이름 **을 입력하고** 사용자 및 **그룹을 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="867b8-165">Enter a policy **Name**, and select **Users and groups**.</span></span> <span data-ttu-id="867b8-166">포함 또는 제외 옵션을 사용하여 정책에 대한 그룹을 추가하고 완료 를 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="867b8-166">Use the Include or Exclude options to add your groups for the policy, and select **Done**.</span></span>
3. <span data-ttu-id="867b8-167">클라우드 **앱 을** 선택하고 보호할 앱을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="867b8-167">Select **Cloud apps**, and choose which apps to protect.</span></span> <span data-ttu-id="867b8-168">예를 들어 앱 **선택 을** 선택하고 **Office 365 SharePoint Online** 및 Office **365 Exchange Online 을 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="867b8-168">For example, choose **Select apps**, and select **Office 365 SharePoint Online** and **Office 365 Exchange Online**.</span></span> <span data-ttu-id="867b8-169">**완료** 를 선택하여 변경 내용을 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="867b8-169">Select **Done** to save your changes.</span></span>

4. <span data-ttu-id="867b8-170">조건 **클라이언트** 앱을 선택하여 앱 및  >   브라우저에 정책을 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="867b8-170">Select **Conditions** > **Client apps** to apply the policy to apps and browsers.</span></span> <span data-ttu-id="867b8-171">예를 들어 **예, 를** 선택한 다음 **브라우저** 및 모바일 앱 및 데스크톱 클라이언트를 **사용하도록 설정할 수 있습니다.**</span><span class="sxs-lookup"><span data-stu-id="867b8-171">For example, select **Yes**, and then enable **Browser** and **Mobile apps and desktop clients**.</span></span> <span data-ttu-id="867b8-172">**완료** 를 선택하여 변경 내용을 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="867b8-172">Select **Done** to save your changes.</span></span>

5. <span data-ttu-id="867b8-173">장치 **준수에** 따라 조건부 액세스를 적용하려면 허용을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="867b8-173">Select **Grant** to apply Conditional Access based on device compliance.</span></span> <span data-ttu-id="867b8-174">예를 들어 **액세스 허용 디바이스를**  >  **규격으로 표시해야 합니다.를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="867b8-174">For example, select **Grant access** > **Require device to be marked as compliant**.</span></span> <span data-ttu-id="867b8-175">**선택을** 선택하여 변경 내용을 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="867b8-175">Choose **Select** to save your changes.</span></span>

6. <span data-ttu-id="867b8-176">정책 **사용 을** 선택한 다음 **만들기를 선택하여** 변경 내용을 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="867b8-176">Select **Enable policy**, and then **Create** to save your changes.</span></span>

<span data-ttu-id="867b8-177">자세한 내용은 Intune에서 조건부 액세스로 [Microsoft Defender ATP 사용 을 참조하세요.](https://docs.microsoft.com/intune/advanced-threat-protection)</span><span class="sxs-lookup"><span data-stu-id="867b8-177">For more information, see [Enable Microsoft Defender ATP with Conditional Access in Intune](https://docs.microsoft.com/intune/advanced-threat-protection).</span></span>

><span data-ttu-id="867b8-178">Endpoint용 Defender를 경험하고 싶나요?</span><span class="sxs-lookup"><span data-stu-id="867b8-178">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="867b8-179">무료 평가판에 등록합니다.</span><span class="sxs-lookup"><span data-stu-id="867b8-179">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-conditionalaccess-belowfoldlink)
