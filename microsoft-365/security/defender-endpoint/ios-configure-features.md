---
title: iOS 기능에 대한 끝점용 Microsoft Defender 구성
description: iOS 기능에 끝점용 Microsoft Defender를 배포하는 방법을 설명
keywords: Microsoft, defender, Endpoint용 Microsoft Defender, ios, 구성, 기능, ios
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
ms.collection:
- m365-security-compliance
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 749e03cb9d14476245baea82c21d322d4d726aad
ms.sourcegitcommit: 48195345b21b409b175d68acdc25d9f2fc4fc5f1
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/30/2021
ms.locfileid: "53230010"
---
# <a name="configure-microsoft-defender-for-endpoint-on-ios-features"></a><span data-ttu-id="d2fb1-104">iOS 기능에 대한 끝점용 Microsoft Defender 구성</span><span class="sxs-lookup"><span data-stu-id="d2fb1-104">Configure Microsoft Defender for Endpoint on iOS features</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="d2fb1-105">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="d2fb1-105">**Applies to:**</span></span>
- [<span data-ttu-id="d2fb1-106">엔드포인트용 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="d2fb1-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="d2fb1-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="d2fb1-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="d2fb1-108">Endpoint용 Defender를 경험하고 싶나요?</span><span class="sxs-lookup"><span data-stu-id="d2fb1-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="d2fb1-109">무료 평가판에 등록합니다.</span><span class="sxs-lookup"><span data-stu-id="d2fb1-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

> [!NOTE]
> <span data-ttu-id="d2fb1-110">iOS의 끝점용 Defender는 VPN을 사용하여 웹 보호 기능을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="d2fb1-110">Defender for Endpoint on iOS would use a VPN in order to provide the Web Protection feature.</span></span> <span data-ttu-id="d2fb1-111">이는 일반 VPN이 아니며 장치 외부에서 트래픽을 취하지 않는 로컬/자체 루프 VPN입니다.</span><span class="sxs-lookup"><span data-stu-id="d2fb1-111">This is not a regular VPN and is a local/self-looping VPN that does not take traffic outside the device.</span></span>

## <a name="conditional-access-with-defender-for-endpoint-on-ios"></a><span data-ttu-id="d2fb1-112">iOS의 끝점용 Defender를 통해 조건부 액세스</span><span class="sxs-lookup"><span data-stu-id="d2fb1-112">Conditional Access with Defender for Endpoint on iOS</span></span>  
<span data-ttu-id="d2fb1-113">iOS의 끝점용 Microsoft Defender 및 Microsoft Intune Azure Active Directory 장치 위험 점수를 기반으로 장치 준수 및 조건부 액세스 정책을 시행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d2fb1-113">Microsoft Defender for Endpoint on iOS along with Microsoft Intune and Azure Active Directory enables enforcing Device compliance and Conditional Access policies based on device risk score.</span></span> <span data-ttu-id="d2fb1-114">Endpoint용 Defender는 Intune을 통해 이 기능을 활용하기 위해 배포할 수 있는 MTD(Mobile Threat Defense) 솔루션입니다.</span><span class="sxs-lookup"><span data-stu-id="d2fb1-114">Defender for Endpoint is a Mobile Threat Defense (MTD) solution that you can deploy to leverage this capability via Intune.</span></span>

<span data-ttu-id="d2fb1-115">iOS에서 끝점용 Defender를 통해 조건부 액세스를 설정하는 방법에 대한 자세한 내용은 Endpoint 및 [Intune용 Defender를 참조하세요.](/mem/intune/protect/advanced-threat-protection)</span><span class="sxs-lookup"><span data-stu-id="d2fb1-115">For more information about how to set up Conditional Access with Defender for Endpoint on iOS, see [Defender for Endpoint and Intune](/mem/intune/protect/advanced-threat-protection).</span></span>

### <a name="jailbreak-detection-by-microsoft-defender-for-endpoint"></a><span data-ttu-id="d2fb1-116">Endpoint용 Microsoft Defender의 탈옥 감지</span><span class="sxs-lookup"><span data-stu-id="d2fb1-116">Jailbreak detection by Microsoft Defender for Endpoint</span></span>
<span data-ttu-id="d2fb1-117">끝점용 Microsoft Defender에는 무단으로 보호된 관리되지 않는 장치를 검색하는 기능이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d2fb1-117">Microsoft Defender for Endpoint has the capability of detecting unmanaged and managed devices that are jailbroken.</span></span> <span data-ttu-id="d2fb1-118">장치가 무단으로 보호된 것으로 감지되면 보안 센터에 높은 **위험** 경고가 보고되고, 조건부 액세스가 장치 위험 점수를 기반으로 설정되어 있는 경우 장치가 회사 데이터에 액세스하지 못하게 차단됩니다.</span><span class="sxs-lookup"><span data-stu-id="d2fb1-118">If a device is detected to be jailbroken, a **High**-risk alert will be reported to Security Center and if Conditional Access is setup based on device risk score, then the device will be blocked from accessing corporate data.</span></span>

## <a name="web-protection-and-vpn"></a><span data-ttu-id="d2fb1-119">웹 보호 및 VPN</span><span class="sxs-lookup"><span data-stu-id="d2fb1-119">Web Protection and VPN</span></span>

<span data-ttu-id="d2fb1-120">기본적으로 iOS의 Endpoint용 Defender에는 웹 보호 기능이 포함 및 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="d2fb1-120">By default, Defender for Endpoint on iOS includes and enables the web protection feature.</span></span> <span data-ttu-id="d2fb1-121">[웹 보호는](web-protection-overview.md) 웹 위협으로부터 장치를 보호하고 피싱 공격으로부터 사용자를 보호하는 데 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d2fb1-121">[Web protection](web-protection-overview.md) helps to secure devices against web threats and protect users from phishing attacks.</span></span> <span data-ttu-id="d2fb1-122">iOS의 끝점용 Defender는 VPN을 사용하여 이 보호를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="d2fb1-122">Defender for Endpoint on iOS uses a VPN in order to provide this protection.</span></span> <span data-ttu-id="d2fb1-123">이는 로컬 VPN으로, 기존 VPN과 달리 네트워크 트래픽은 장치 외부로 전송되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d2fb1-123">Please note this is a local VPN and unlike traditional VPN, network traffic is not sent outside the device.</span></span>

<span data-ttu-id="d2fb1-124">기본적으로 사용하도록 설정되어 있는 동안 VPN을 사용하지 않도록 설정해야 하는 경우도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d2fb1-124">While enabled by default, there might be some cases that require you to disable VPN.</span></span> <span data-ttu-id="d2fb1-125">예를 들어 VPN을 구성할 때 작동하지 않는 일부 앱을 실행하려는 경우를 예로 들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d2fb1-125">For example, you want to run some apps that do not work when a VPN is configured.</span></span> <span data-ttu-id="d2fb1-126">이러한 경우 아래 단계에 따라 디바이스의 앱에서 VPN을 사용하지 않도록 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d2fb1-126">In such cases, you can choose to disable VPN from the app on the device by following the steps below:</span></span>

1. <span data-ttu-id="d2fb1-127">iOS 장치에서 설정 열고 **일반을 클릭하거나** **탭한** 다음 **VPN 을 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="d2fb1-127">On your iOS device, open the **Settings** app, click or tap **General** and then **VPN**.</span></span>
1. <span data-ttu-id="d2fb1-128">끝점용 Microsoft Defender의 "i" 단추를 클릭하거나 탭합니다.</span><span class="sxs-lookup"><span data-stu-id="d2fb1-128">Click or tap the "i" button for Microsoft Defender for Endpoint.</span></span>
1. <span data-ttu-id="d2fb1-129">VPN을 사용하지 **커넥트 On Demand를** 해제합니다.</span><span class="sxs-lookup"><span data-stu-id="d2fb1-129">Toggle off **Connect On Demand** to disable VPN.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="d2fb1-130">![VPN 구성 필요 시 연결](images/ios-vpn-config.png)</span><span class="sxs-lookup"><span data-stu-id="d2fb1-130">![VPN config connect on demand](images/ios-vpn-config.png)</span></span>

> [!NOTE]
> <span data-ttu-id="d2fb1-131">VPN을 사용하지 않도록 설정하면 웹 보호를 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="d2fb1-131">Web Protection will not be available when VPN is disabled.</span></span> <span data-ttu-id="d2fb1-132">웹 보호를 다시 사용하도록 설정하려면 장치에서 끝점용 Microsoft Defender 앱을 열고 VPN 시작 을 클릭하거나 **탭합니다.**</span><span class="sxs-lookup"><span data-stu-id="d2fb1-132">To re-enable Web Protection, open the Microsoft Defender for Endpoint app on the device and click or tap **Start VPN**.</span></span>

## <a name="co-existence-of-multiple-vpn-profiles"></a><span data-ttu-id="d2fb1-133">여러 VPN 프로필의 동시 사용</span><span class="sxs-lookup"><span data-stu-id="d2fb1-133">Co-existence of multiple VPN profiles</span></span>

<span data-ttu-id="d2fb1-134">Apple iOS는 동시에 활성화하기 위해 여러 장치 전체의 VPN을 지원하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d2fb1-134">Apple iOS does not support multiple device-wide VPNs to be active simultaneously.</span></span> <span data-ttu-id="d2fb1-135">디바이스에 여러 VPN 프로필이 존재할 수 있는 반면 한 번의 VPN만 활성화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d2fb1-135">While multiple VPN profiles can exist on the device, only one VPN can be active at a time.</span></span>

## <a name="configure-microsoft-defender-for-endpoint-risk-signal-in-app-protection-policy-mam"></a><span data-ttu-id="d2fb1-136">MAM(앱 보호 정책)에서 끝점 위험 신호에 대한 Microsoft Defender 구성</span><span class="sxs-lookup"><span data-stu-id="d2fb1-136">Configure Microsoft Defender for Endpoint risk signal in app protection policy (MAM)</span></span>

<span data-ttu-id="d2fb1-137">iOS/iPadOS의 APP(App Protection Policies, MAM)에서 사용할 위협 신호를 보내도록 끝점용 Microsoft Defender를 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d2fb1-137">Microsoft Defender for Endpoint can be configured to send threat signals to be used in App Protection Policies (APP, also known as MAM) on iOS/iPadOS.</span></span> <span data-ttu-id="d2fb1-138">이 기능을 사용하면 끝점용 Microsoft Defender를 사용하여 수집되지 않은 장치에서 회사 데이터에 대한 액세스를 보호할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d2fb1-138">With this capability, you can use Microsoft Defender for Endpoint to protect access to corporate data from unenrolled devices as well.</span></span>

<span data-ttu-id="d2fb1-139">끝점용 Microsoft Defender를 통해 앱 보호 정책을 설정하는 단계는 아래와 같습니다.</span><span class="sxs-lookup"><span data-stu-id="d2fb1-139">Steps to setup app protection policies with Microsoft Defender for Endpoint are as below:</span></span>

1. <span data-ttu-id="d2fb1-140">테넌트에서 끝점용 Microsoft Defender로의 Microsoft Endpoint Manager 연결을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="d2fb1-140">Set up the connection from your Microsoft Endpoint Manager tenant to Microsoft Defender for Endpoint.</span></span> <span data-ttu-id="d2fb1-141">[Microsoft 끝점](https://go.microsoft.com/fwlink/?linkid=2109431)관리자 관리 센터에서 테넌트 관리 커넥터 및 끝점용 Microsoft Defender(플랫폼 간) 또는 끝점용 Microsoft Defender 보안   >    >  Microsoft **Defender(설치** 아래)로 이동한 다음  >   **iOS용** 앱 보호 정책 설정 에서 토글을 켜야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d2fb1-141">In [Microsoft Endpoint manager admin center](https://go.microsoft.com/fwlink/?linkid=2109431), go to **Tenant Administration** > **Connectors and tokens** > **Microsoft Defender for Endpoint** (under Cross platform) or **Endpoint Security** > **Microsoft Defender for Endpoint** (under Setup) and turn on the toggles under **App Protection Policy Settings for iOS**.</span></span>
1. <span data-ttu-id="d2fb1-142">저장을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="d2fb1-142">Select Save.</span></span> <span data-ttu-id="d2fb1-143">이제 **연결** 상태가 사용으로 설정되어 **있습니다.**</span><span class="sxs-lookup"><span data-stu-id="d2fb1-143">You should see **Connection status** is now set to **Enabled**.</span></span>
1. <span data-ttu-id="d2fb1-144">앱 보호 정책 만들기: 끝점 커넥터에 대한 Microsoft Defender 설정이 완료되면 앱 앱 보호 정책(정책 아래)으로 이동하여 새 정책을 만들거나 기존 정책을   >   업데이트합니다.</span><span class="sxs-lookup"><span data-stu-id="d2fb1-144">Create app protection policy: After your Microsoft Defender for Endpoint connector setup is complete, navigate to **Apps** > **App protection policies** (under Policy) to create a new policy or update an existing one.</span></span>
1. <span data-ttu-id="d2fb1-145">조직에서 정책에 필요한 플랫폼, **앱, 데이터** 보호, 액세스 요구 사항 설정을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="d2fb1-145">Select the platform, **Apps, Data protection, Access requirements** settings that your organization requires for your policy.</span></span>
1. <span data-ttu-id="d2fb1-146">조건부 **시작**  >  **장치 조건에서** 허용되는 장치 위협 수준 **최대 설정을 찾을 수 있습니다.**</span><span class="sxs-lookup"><span data-stu-id="d2fb1-146">Under **Conditional launch** > **Device conditions**, you will find the setting **Max allowed device threat level**.</span></span> <span data-ttu-id="d2fb1-147">낮음, 중간, 높음 또는 보안으로 구성해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d2fb1-147">This will need to be configured to either Low, Medium, High, or Secured.</span></span> <span data-ttu-id="d2fb1-148">사용할 수 있는 작업은  액세스 차단 또는 데이터 **지우기 입니다.**</span><span class="sxs-lookup"><span data-stu-id="d2fb1-148">The actions available to you will be **Block access** or **Wipe data**.</span></span> <span data-ttu-id="d2fb1-149">이 설정이 적용하기 전에 커넥터를 설정해야 하는 정보 대화 상자가 표시될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d2fb1-149">You may see an informational dialog to make sure you have your connector set up prior to this setting take effect.</span></span> <span data-ttu-id="d2fb1-150">커넥터가 이미 설정되어 있는 경우 이 대화 상자를 무시할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d2fb1-150">If your connector is already set up, you may ignore this dialog.</span></span>
1. <span data-ttu-id="d2fb1-151">할당을 완료하고 정책을 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="d2fb1-151">Finish with Assignments and save your policy.</span></span>

<span data-ttu-id="d2fb1-152">MAM 또는 앱 보호 정책에 대한 자세한 내용은 iOS 앱 보호 정책 설정을 [참조하세요.](/mem/intune/apps/app-protection-policy-settings-ios)</span><span class="sxs-lookup"><span data-stu-id="d2fb1-152">For more details on MAM or app protection policy, see [iOS app protection policy settings](/mem/intune/apps/app-protection-policy-settings-ios).</span></span>

### <a name="deploying-microsoft-defender-for-endpoint-for-mam-or-on-unenrolled-devices"></a><span data-ttu-id="d2fb1-153">MAM용 끝점 또는 미가용 장치에 Microsoft Defender 배포</span><span class="sxs-lookup"><span data-stu-id="d2fb1-153">Deploying Microsoft Defender for Endpoint for MAM or on unenrolled devices</span></span>

<span data-ttu-id="d2fb1-154">iOS의 끝점용 Microsoft Defender는 앱 보호 정책 시나리오를 사용할 수 있도록 지원하며 Apple 앱 스토어에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d2fb1-154">Microsoft Defender for Endpoint on iOS enables the App Protection Policy scenario and is available in the Apple app store.</span></span>

<span data-ttu-id="d2fb1-155">최종 사용자는 Apple 앱 스토어에서 직접 최신 버전의 앱을 설치해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d2fb1-155">End-users should install the latest version of the app directly from the Apple app store.</span></span>

## <a name="configure-compliance-policy-against-jailbroken-devices"></a><span data-ttu-id="d2fb1-156">무단으로 보호된 장치에 대한 규정 준수 정책 구성</span><span class="sxs-lookup"><span data-stu-id="d2fb1-156">Configure compliance policy against jailbroken devices</span></span>

<span data-ttu-id="d2fb1-157">무단으로 보호된 iOS 장치에서 회사 데이터에 액세스하지 못하도록 보호하기 위해 Intune에서 다음 규정 준수 정책을 설정하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="d2fb1-157">To protect corporate data from being accessed on jailbroken iOS devices, we recommend that you set up the following compliance policy on Intune.</span></span>

> [!NOTE]
> <span data-ttu-id="d2fb1-158">탈옥 검색은 iOS의 끝점에 대해 Microsoft Defender에서 제공하는 기능입니다.</span><span class="sxs-lookup"><span data-stu-id="d2fb1-158">Jailbreak detection is a capability provided by Microsoft Defender for Endpoint on iOS.</span></span> <span data-ttu-id="d2fb1-159">그러나 이 정책을 탈옥 시나리오에 대한 추가 방어 계층으로 설정하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="d2fb1-159">However, we recommend that you setup this policy as an additional layer of defense against jailbreak scenarios.</span></span>

<span data-ttu-id="d2fb1-160">다음 단계에 따라 무단으로 보호된 장치에 대한 규정 준수 정책을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d2fb1-160">Follow the steps below to create a compliance policy against jailbroken devices.</span></span>

1. <span data-ttu-id="d2fb1-161">Microsoft Endpoint Manager [관리 센터에서](https://go.microsoft.com/fwlink/?linkid=2109431)장치 **준수** 정책 정책  ->    ->  **만들기로 이동하세요.**</span><span class="sxs-lookup"><span data-stu-id="d2fb1-161">In [Microsoft Endpoint Manager admin center](https://go.microsoft.com/fwlink/?linkid=2109431), go to **Devices** -> **Compliance policies** -> **Create Policy**.</span></span> <span data-ttu-id="d2fb1-162">플랫폼으로 "iOS/iPadOS"를 선택하고 만들기를 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="d2fb1-162">Select "iOS/iPadOS" as platform and click **Create**.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="d2fb1-163">![정책 만들기](images/ios-jb-policy.png)</span><span class="sxs-lookup"><span data-stu-id="d2fb1-163">![Create Policy](images/ios-jb-policy.png)</span></span>

2. <span data-ttu-id="d2fb1-164&quot;>정책의 이름(예: &quot;탈옥에 대한 규정 준수 정책")을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="d2fb1-164">Specify a name of the policy, for example "Compliance Policy for Jailbreak".</span></span>
3. <span data-ttu-id="d2fb1-165">준수 설정 페이지에서 장치 상태 **섹션을** 클릭하여 확장하고 **무단으로** 차단된 장치 차단 **필드를** 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="d2fb1-165">In the compliance settings page, click to expand **Device Health** section and click **Block** for **Jailbroken devices** field.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="d2fb1-166">![정책 설정](images/ios-jb-settings.png)</span><span class="sxs-lookup"><span data-stu-id="d2fb1-166">![Policy Settings](images/ios-jb-settings.png)</span></span>

4. <span data-ttu-id="d2fb1-167">준수하지 **않는** 작업에 대한 작업 섹션에서 요구 사항에 따라 작업을 선택하고 다음 을 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="d2fb1-167">In the **Action for noncompliance** section, select the actions as per your requirements and select **Next**.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="d2fb1-168">![정책 작업](images/ios-jb-actions.png)</span><span class="sxs-lookup"><span data-stu-id="d2fb1-168">![Policy Actions](images/ios-jb-actions.png)</span></span>

5. <span data-ttu-id="d2fb1-169">할당 **섹션에서** 이 정책에 포함할 사용자 그룹을 선택하고 다음 을 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="d2fb1-169">In the **Assignments** section, select the user groups that you want to include for this policy and then select **Next**.</span></span>
6. <span data-ttu-id="d2fb1-170">**검토+만들기 섹션에서** 입력한 정보가 모두 올바른지 확인한 다음 만들기를 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="d2fb1-170">In the **Review+Create** section, verify that all the information entered is correct and then select **Create**.</span></span>

## <a name="configure-custom-indicators"></a><span data-ttu-id="d2fb1-171">사용자 지정 표시기 구성</span><span class="sxs-lookup"><span data-stu-id="d2fb1-171">Configure custom indicators</span></span>

<span data-ttu-id="d2fb1-172">iOS의 끝점용 Defender를 사용하면 관리자가 iOS 장치에서도 사용자 지정 표시기를 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d2fb1-172">Defender for Endpoint on iOS enables admins to configure custom indicators on iOS devices as well.</span></span> <span data-ttu-id="d2fb1-173">사용자 지정 표시기를 구성하는 방법에 대한 자세한 내용은 [지표 관리를 참조하세요.](/microsoft-365/security/defender-endpoint/manage-indicators)</span><span class="sxs-lookup"><span data-stu-id="d2fb1-173">For more information on how to configure custom indicators, see [Manage indicators](/microsoft-365/security/defender-endpoint/manage-indicators).</span></span>

> [!NOTE]
> <span data-ttu-id="d2fb1-174">iOS의 끝점용 Defender는 IP 주소 및 URL/도메인에 대한 사용자 지정 표시기만 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d2fb1-174">Defender for Endpoint on iOS supports creating custom indicators only for IP addresses and URLs/domains.</span></span>

## <a name="report-unsafe-site"></a><span data-ttu-id="d2fb1-175">안전하지 않은 사이트 보고</span><span class="sxs-lookup"><span data-stu-id="d2fb1-175">Report unsafe site</span></span>

<span data-ttu-id="d2fb1-176">피싱 웹 사이트는 개인 또는 재무 정보를 얻기 위해 신뢰할 수 있는 웹 사이트를 가장합니다.</span><span class="sxs-lookup"><span data-stu-id="d2fb1-176">Phishing websites impersonate trustworthy websites for the purpose of obtaining your personal or financial information.</span></span> <span data-ttu-id="d2fb1-177">피싱 [](https://www.microsoft.com/wdsi/filesubmission/exploitguard/networkprotection) 사이트일 수 있는 웹 사이트를 보고하려는 경우 네트워크 보호에 대한 피드백 제공 페이지를 방문하세요.</span><span class="sxs-lookup"><span data-stu-id="d2fb1-177">Visit the [Provide feedback about network protection](https://www.microsoft.com/wdsi/filesubmission/exploitguard/networkprotection) page if you want to report a website that could be a phishing site.</span></span>

