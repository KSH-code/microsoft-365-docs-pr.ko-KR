---
title: 끝점용 Microsoft Defender에서 조건부 액세스 구성
description: 조건부 액세스를 구현하기 위해 Intune, Microsoft Defender 보안 센터 및 Azure에서 수행해야 하는 단계에 대해 자세히 알아보십시오.
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
ms.openlocfilehash: ceb69d59dc5208c0908e33d0880d9352562ec140
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/08/2021
ms.locfileid: "52843977"
---
# <a name="configure-conditional-access-in-microsoft-defender-for-endpoint"></a><span data-ttu-id="10672-104">끝점용 Microsoft Defender에서 조건부 액세스 구성</span><span class="sxs-lookup"><span data-stu-id="10672-104">Configure Conditional Access in Microsoft Defender for Endpoint</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="10672-105">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="10672-105">**Applies to:**</span></span>
- [<span data-ttu-id="10672-106">엔드포인트용 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="10672-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="10672-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="10672-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="10672-108">Endpoint용 Defender를 경험하고 싶나요?</span><span class="sxs-lookup"><span data-stu-id="10672-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="10672-109">무료 평가판에 등록합니다.</span><span class="sxs-lookup"><span data-stu-id="10672-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-assignaccess-abovefoldlink)

<span data-ttu-id="10672-110">이 섹션에서는 조건부 액세스를 올바르게 구현하기 위해 필요한 모든 단계를 안내합니다.</span><span class="sxs-lookup"><span data-stu-id="10672-110">This section guides you through all the steps you need to take to properly implement Conditional Access.</span></span>

### <a name="before-you-begin"></a><span data-ttu-id="10672-111">시작하기 전에</span><span class="sxs-lookup"><span data-stu-id="10672-111">Before you begin</span></span>
>[!WARNING]
><span data-ttu-id="10672-112">이 시나리오에서는 Azure AD 등록 장치가 지원되지 않는다는 점에 유의해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="10672-112">It's important to note that Azure AD registered devices is not supported in this scenario.</span></span></br>
><span data-ttu-id="10672-113">Intune 등록 장치만 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="10672-113">Only Intune enrolled devices are supported.</span></span>


<span data-ttu-id="10672-114">모든 장치가 Intune에 등록된지 확인해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="10672-114">You need to make sure that all your devices are enrolled in Intune.</span></span> <span data-ttu-id="10672-115">다음 옵션 중 원하는 옵션을 사용하여 Intune에서 장치를 등록할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="10672-115">You can use any of the following options to enroll devices in Intune:</span></span>


- <span data-ttu-id="10672-116">IT 관리자: 자동 등록을 사용하도록 설정하는 방법에 대한 자세한 내용은 Windows [등록을 참조하세요.](/intune/windows-enroll#enable-windows-10-automatic-enrollment)</span><span class="sxs-lookup"><span data-stu-id="10672-116">IT Admin: For more information on how to enabling auto-enrollment, see [Windows Enrollment](/intune/windows-enroll#enable-windows-10-automatic-enrollment)</span></span>
- <span data-ttu-id="10672-117">최종 사용자: Intune에서 Windows 10 장치를 등록하는 방법에 대한 자세한 내용은 [Intune에서 Windows 10 장치 등록을 참조하세요.](/intune/quickstart-enroll-windows-device)</span><span class="sxs-lookup"><span data-stu-id="10672-117">End-user: For more information on how to enroll your Windows 10 device in Intune, see [Enroll your Windows 10 device in Intune](/intune/quickstart-enroll-windows-device)</span></span>
- <span data-ttu-id="10672-118">최종 사용자 대체: Azure AD 도메인에 가입하는 방법에 대한 자세한 내용은 방법: Azure AD 조인 구현 계획을 [참조하세요.](/azure/active-directory/devices/azureadjoin-plan)</span><span class="sxs-lookup"><span data-stu-id="10672-118">End-user alternative: For more information on joining an Azure AD domain, see [How to: Plan your Azure AD join implementation](/azure/active-directory/devices/azureadjoin-plan).</span></span>



<span data-ttu-id="10672-119">Intune 포털 및 Azure AD 포털에서 Microsoft Defender 보안 센터 단계가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="10672-119">There are steps you'll need to take in Microsoft Defender Security Center, the Intune portal, and Azure AD portal.</span></span>

<span data-ttu-id="10672-120">이러한 포털에 액세스하고 조건부 액세스를 구현하는 데 필요한 역할을 주의해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="10672-120">It's important to note the required roles to access these portals and implement Conditional access:</span></span>
- <span data-ttu-id="10672-121">**Microsoft Defender 보안 센터** - 통합을 설정하려면 전역 관리자 역할로 포털에 로그인해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="10672-121">**Microsoft Defender Security Center** - You'll need to sign into the portal with a global administrator role to turn on the integration.</span></span>
- <span data-ttu-id="10672-122">**Intune** - 관리 권한이 있는 보안 관리자 권한으로 포털에 로그인해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="10672-122">**Intune** - You'll need to sign in to the portal with security administrator rights with management permissions.</span></span> 
- <span data-ttu-id="10672-123">**Azure AD 포털** - 전역 관리자, 보안 관리자 또는 조건부 액세스 관리자로 로그인해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="10672-123">**Azure AD portal** - You'll need to sign in as a global administrator, security administrator, or Conditional Access administrator.</span></span>


> [!NOTE]
> <span data-ttu-id="10672-124">Intune 관리 Microsoft Intune Azure AD가 연결된 장치와 함께 Windows 10 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="10672-124">You'll need a Microsoft Intune environment, with Intune managed and Azure AD joined Windows 10 devices.</span></span>

<span data-ttu-id="10672-125">조건부 액세스를 사용하도록 설정하려면 다음 단계를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="10672-125">Take the following steps to enable Conditional Access:</span></span>
- <span data-ttu-id="10672-126">1단계: Microsoft Intune 연결 Microsoft Defender 보안 센터</span><span class="sxs-lookup"><span data-stu-id="10672-126">Step 1: Turn on the Microsoft Intune connection from Microsoft Defender Security Center</span></span>
- <span data-ttu-id="10672-127">2단계: Intune에서 끝점에 대한 Defender 통합 켜기</span><span class="sxs-lookup"><span data-stu-id="10672-127">Step 2: Turn on the Defender for Endpoint integration in Intune</span></span>
- <span data-ttu-id="10672-128">3단계: Intune에서 준수 정책 만들기</span><span class="sxs-lookup"><span data-stu-id="10672-128">Step 3: Create the compliance policy in Intune</span></span>
- <span data-ttu-id="10672-129">4단계: 정책 할당</span><span class="sxs-lookup"><span data-stu-id="10672-129">Step 4: Assign the policy</span></span> 
- <span data-ttu-id="10672-130">5단계: Azure AD 조건부 액세스 정책 만들기</span><span class="sxs-lookup"><span data-stu-id="10672-130">Step 5: Create an Azure AD Conditional Access policy</span></span>


### <a name="step-1-turn-on-the-microsoft-intune-connection"></a><span data-ttu-id="10672-131">1단계: 연결 Microsoft Intune 켜기</span><span class="sxs-lookup"><span data-stu-id="10672-131">Step 1: Turn on the Microsoft Intune connection</span></span>
1. <span data-ttu-id="10672-132">탐색 창에서 연결 **설정**  >  **고급 Microsoft Intune**  >  **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="10672-132">In the navigation pane, select **Settings** > **Advanced features** > **Microsoft Intune connection**.</span></span>
2. <span data-ttu-id="10672-133">설정의 Microsoft Intune 으로 **전환합니다.**</span><span class="sxs-lookup"><span data-stu-id="10672-133">Toggle the Microsoft Intune setting to **On**.</span></span>
3. <span data-ttu-id="10672-134">기본 **설정 저장을 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="10672-134">Click **Save preferences**.</span></span>


### <a name="step-2-turn-on-the-defender-for-endpoint-integration-in-intune"></a><span data-ttu-id="10672-135">2단계: Intune에서 끝점에 대한 Defender 통합 켜기</span><span class="sxs-lookup"><span data-stu-id="10672-135">Step 2: Turn on the Defender for Endpoint integration in Intune</span></span>
1. <span data-ttu-id="10672-136">[Azure 포털](https://portal.azure.com)에 로그인합니다.</span><span class="sxs-lookup"><span data-stu-id="10672-136">Sign in to the [Azure portal](https://portal.azure.com).</span></span>
2. <span data-ttu-id="10672-137">장치 **준수 를**  >  **Microsoft Defender ATP.**</span><span class="sxs-lookup"><span data-stu-id="10672-137">Select **Device compliance** > **Microsoft Defender ATP**.</span></span>
3. <span data-ttu-id="10672-138">**커넥트 Windows 10.0.15063+** 장치를 으로 Microsoft Defender Advanced Threat Protection 로 **설정하십시오.**</span><span class="sxs-lookup"><span data-stu-id="10672-138">Set **Connect Windows 10.0.15063+ devices to Microsoft Defender Advanced Threat Protection** to **On**.</span></span>
4. <span data-ttu-id="10672-139">**저장** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="10672-139">Click **Save**.</span></span>


### <a name="step-3-create-the-compliance-policy-in-intune"></a><span data-ttu-id="10672-140">3단계: Intune에서 준수 정책 만들기</span><span class="sxs-lookup"><span data-stu-id="10672-140">Step 3: Create the compliance policy in Intune</span></span>
1. <span data-ttu-id="10672-141">Azure [Portal에서](https://portal.azure.com)모든 **서비스를** 선택하고 **Intune을** 필터링하고 를 **Microsoft Intune.**</span><span class="sxs-lookup"><span data-stu-id="10672-141">In the [Azure portal](https://portal.azure.com), select **All services**, filter on **Intune**, and select **Microsoft Intune**.</span></span>
2. <span data-ttu-id="10672-142">장치 **준수 정책**  >  **정책** 만들기 정책을  >  **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="10672-142">Select **Device compliance** > **Policies** > **Create policy**.</span></span>
3. <span data-ttu-id="10672-143">이름 및 **설명을** **입력합니다.**</span><span class="sxs-lookup"><span data-stu-id="10672-143">Enter a **Name** and **Description**.</span></span>
4. <span data-ttu-id="10672-144">**플랫폼에서** 를 선택하고 Windows 10 **이상을 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="10672-144">In **Platform**, select **Windows 10 and later**.</span></span>
5. <span data-ttu-id="10672-145">장치 **상태 설정에서**  장치 위협 수준에 또는 장치 위협 수준 아래에 있도록 요구를 기본 설정 수준으로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="10672-145">In the **Device Health** settings, set **Require the device to be at or under the Device Threat Level** to your preferred level:</span></span>

   - <span data-ttu-id="10672-146">**보안 :** 이 수준이 가장 안전합니다.</span><span class="sxs-lookup"><span data-stu-id="10672-146">**Secured**: This level is the most secure.</span></span> <span data-ttu-id="10672-147">장치에 기존 위협이 없는 경우 회사 리소스에 계속 액세스할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="10672-147">The device cannot have any existing threats and still access company resources.</span></span> <span data-ttu-id="10672-148">위협이 발견되는 경우 장치는 비호조로 평가됩니다.</span><span class="sxs-lookup"><span data-stu-id="10672-148">If any threats are found, the device is evaluated as noncompliant.</span></span>
   - <span data-ttu-id="10672-149">**낮음:** 낮은 수준의 위협만 존재하는 경우 장치가 규격입니다.</span><span class="sxs-lookup"><span data-stu-id="10672-149">**Low**: The device is compliant if only low-level threats exist.</span></span> <span data-ttu-id="10672-150">중간 또는 높은 위협 수준이 있는 장치는 규정을 준수하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="10672-150">Devices with medium or high threat levels are not compliant.</span></span>
   - <span data-ttu-id="10672-151">**보통:** 장치에서 발견되는 위협이 낮거나 중간인 경우 장치가 규격입니다.</span><span class="sxs-lookup"><span data-stu-id="10672-151">**Medium**: The device is compliant if the threats found on the device are low or medium.</span></span> <span data-ttu-id="10672-152">높은 수준의 위협이 감지되면 장치가 비준수로 결정됩니다.</span><span class="sxs-lookup"><span data-stu-id="10672-152">If high-level threats are detected, the device is determined as noncompliant.</span></span>
   - <span data-ttu-id="10672-153">**높음:** 이 수준은 최소 보안 수준으로, 모든 위협 수준을 허용합니다.</span><span class="sxs-lookup"><span data-stu-id="10672-153">**High**: This level is the least secure, and allows all threat levels.</span></span> <span data-ttu-id="10672-154">따라서 높은, 중간 또는 낮은 위협 수준이 있는 장치는 규격으로 간주됩니다.</span><span class="sxs-lookup"><span data-stu-id="10672-154">So devices that with high, medium or low threat levels are considered compliant.</span></span>

6. <span data-ttu-id="10672-155">확인 **및** **만들기를 선택하여** 변경 내용을 저장하고 정책을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="10672-155">Select **OK**, and **Create** to save your changes (and create the policy).</span></span>

### <a name="step-4-assign-the-policy"></a><span data-ttu-id="10672-156">4단계: 정책 할당</span><span class="sxs-lookup"><span data-stu-id="10672-156">Step 4: Assign the policy</span></span>
1. <span data-ttu-id="10672-157">Azure [Portal에서](https://portal.azure.com)모든 **서비스를** 선택하고 **Intune을** 필터링하고 를 **Microsoft Intune.**</span><span class="sxs-lookup"><span data-stu-id="10672-157">In the [Azure portal](https://portal.azure.com), select **All services**, filter on **Intune**, and select **Microsoft Intune**.</span></span>
2. <span data-ttu-id="10672-158">장치 **준수 정책을>** Microsoft  >   Defender 준수 정책을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="10672-158">Select **Device compliance** > **Policies**> select your Microsoft Defender for Endpoint compliance policy.</span></span>
3. <span data-ttu-id="10672-159">**과제** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="10672-159">Select **Assignments**.</span></span>
4. <span data-ttu-id="10672-160">Azure AD 그룹을 포함하거나 제외하여 정책을 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="10672-160">Include or exclude your Azure AD groups to assign them the policy.</span></span>
5. <span data-ttu-id="10672-161">그룹에 정책을 배포하려면 저장 을 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="10672-161">To deploy the policy to the groups, select **Save**.</span></span> <span data-ttu-id="10672-162">정책이 대상으로 하는 사용자 장치는 규정 준수로 평가됩니다.</span><span class="sxs-lookup"><span data-stu-id="10672-162">The user devices targeted by the policy are evaluated for compliance.</span></span>

### <a name="step-5-create-an-azure-ad-conditional-access-policy"></a><span data-ttu-id="10672-163">5단계: Azure AD 조건부 액세스 정책 만들기</span><span class="sxs-lookup"><span data-stu-id="10672-163">Step 5: Create an Azure AD Conditional Access policy</span></span>
1. <span data-ttu-id="10672-164">Azure [Portal에서](https://portal.azure.com) **조건부 Azure Active Directory**  >  **새 정책 을 열** 수  >  **있습니다.**</span><span class="sxs-lookup"><span data-stu-id="10672-164">In the [Azure portal](https://portal.azure.com), open **Azure Active Directory** > **Conditional Access** > **New policy**.</span></span>
2. <span data-ttu-id="10672-165">정책 이름 **을 입력하고** 사용자 및 **그룹을 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="10672-165">Enter a policy **Name**, and select **Users and groups**.</span></span> <span data-ttu-id="10672-166">포함 또는 제외 옵션을 사용하여 정책에 대한 그룹을 추가하고 완료 를 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="10672-166">Use the Include or Exclude options to add your groups for the policy, and select **Done**.</span></span>
3. <span data-ttu-id="10672-167">클라우드 **앱 을** 선택하고 보호할 앱을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="10672-167">Select **Cloud apps**, and choose which apps to protect.</span></span> <span data-ttu-id="10672-168">예를 들어 앱 **선택 을** 선택하고 Office 365 SharePoint **Online을** **선택하고** Office 365 Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="10672-168">For example, choose **Select apps**, and select **Office 365 SharePoint Online** and **Office 365 Exchange Online**.</span></span> <span data-ttu-id="10672-169">**완료** 를 선택하여 변경 내용을 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="10672-169">Select **Done** to save your changes.</span></span>

4. <span data-ttu-id="10672-170">조건 **클라이언트** 앱을 선택하여 앱 및  >   브라우저에 정책을 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="10672-170">Select **Conditions** > **Client apps** to apply the policy to apps and browsers.</span></span> <span data-ttu-id="10672-171">예를 들어 **예, 를** 선택한 다음 **브라우저** 및 모바일 앱 및 데스크톱 클라이언트를 **사용하도록 설정할 수 있습니다.**</span><span class="sxs-lookup"><span data-stu-id="10672-171">For example, select **Yes**, and then enable **Browser** and **Mobile apps and desktop clients**.</span></span> <span data-ttu-id="10672-172">**완료** 를 선택하여 변경 내용을 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="10672-172">Select **Done** to save your changes.</span></span>

5. <span data-ttu-id="10672-173">장치 **준수에** 따라 조건부 액세스를 적용하려면 허용을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="10672-173">Select **Grant** to apply Conditional Access based on device compliance.</span></span> <span data-ttu-id="10672-174">예를 들어 **액세스 허용 디바이스를**  >  **규격으로 표시해야 합니다.를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="10672-174">For example, select **Grant access** > **Require device to be marked as compliant**.</span></span> <span data-ttu-id="10672-175">**선택을** 선택하여 변경 내용을 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="10672-175">Choose **Select** to save your changes.</span></span>

6. <span data-ttu-id="10672-176">정책 **사용 을** 선택한 다음 **만들기를 선택하여** 변경 내용을 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="10672-176">Select **Enable policy**, and then **Create** to save your changes.</span></span>

<span data-ttu-id="10672-177">자세한 내용은 Intune에서 조건부 액세스를 통해 [끝점에 대한 Microsoft Defender 준수 적용을 참조하세요.](/intune/advanced-threat-protection)</span><span class="sxs-lookup"><span data-stu-id="10672-177">For more information, see [Enforce compliance for Microsoft Defender for Endpoint with Conditional Access in Intune](/intune/advanced-threat-protection).</span></span>

><span data-ttu-id="10672-178">Endpoint용 Defender를 경험하고 싶나요?</span><span class="sxs-lookup"><span data-stu-id="10672-178">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="10672-179">무료 평가판에 등록합니다.</span><span class="sxs-lookup"><span data-stu-id="10672-179">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-conditionalaccess-belowfoldlink)
