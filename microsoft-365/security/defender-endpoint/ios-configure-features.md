---
title: iOS 기능에 대한 끝점용 Microsoft Defender 구성
description: iOS 기능용 Microsoft Defender ATP를 배포하는 방법에 대해 설명
keywords: microsoft, defender, atp, ios, 구성, 기능, ios
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
ms.openlocfilehash: 8f74d4799bcb02051cddd09b80ed6ab50258302b
ms.sourcegitcommit: 987f70e44e406ab6b1dd35f336a9d0c228032794
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/05/2021
ms.locfileid: "51587230"
---
# <a name="configure-microsoft-defender-for-endpoint-for-ios-features"></a><span data-ttu-id="5f3da-104">iOS 기능에 대한 끝점용 Microsoft Defender 구성</span><span class="sxs-lookup"><span data-stu-id="5f3da-104">Configure Microsoft Defender for Endpoint for iOS features</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="5f3da-105">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="5f3da-105">**Applies to:**</span></span>
- <span data-ttu-id="5f3da-106">[엔드포인트용 Microsoft Defender](https://go.microsoft.com/fwlink/p/?linkid=2154037) </span><span class="sxs-lookup"><span data-stu-id="5f3da-106">[Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)</span></span>
- [<span data-ttu-id="5f3da-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="5f3da-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="5f3da-108">Endpoint용 Defender를 경험하고 싶나요?</span><span class="sxs-lookup"><span data-stu-id="5f3da-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="5f3da-109">무료 평가판에 등록합니다.</span><span class="sxs-lookup"><span data-stu-id="5f3da-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

> [!NOTE]
> <span data-ttu-id="5f3da-110">iOS용 끝점용 Defender는 웹 보호 기능을 제공하기 위해 VPN을 사용하게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="5f3da-110">Defender for Endpoint for iOS would use a VPN in order to provide the Web Protection feature.</span></span> <span data-ttu-id="5f3da-111">이는 일반 VPN이 아니며 장치 외부에서 트래픽을 취하지 않는 로컬/자체 루프 VPN입니다.</span><span class="sxs-lookup"><span data-stu-id="5f3da-111">This is not a regular VPN and is a local/self-looping VPN that does not take traffic outside the device.</span></span>

## <a name="conditional-access-with-defender-for-endpoint-for-ios"></a><span data-ttu-id="5f3da-112">iOS용 끝점용 Defender를 통해 조건부 액세스</span><span class="sxs-lookup"><span data-stu-id="5f3da-112">Conditional Access with Defender for Endpoint for iOS</span></span>  
<span data-ttu-id="5f3da-113">Microsoft Intune 및 Azure Active Directory와 함께 iOS용 끝점용 Microsoft Defender를 사용하면 장치 위험 수준에 따라 장치 준수 및 조건부 액세스 정책을 시행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5f3da-113">Microsoft Defender for Endpoint for iOS along with Microsoft Intune and Azure Active Directory enables enforcing Device compliance and Conditional Access policies based on device risk levels.</span></span> <span data-ttu-id="5f3da-114">Endpoint용 Defender는 Intune을 통해 이 기능을 활용하기 위해 배포할 수 있는 MTD(Mobile Threat Defense) 솔루션입니다.</span><span class="sxs-lookup"><span data-stu-id="5f3da-114">Defender for Endpoint is a Mobile Threat Defense (MTD) solution that you can deploy to leverage this capability via Intune.</span></span>

<span data-ttu-id="5f3da-115">iOS용 끝점용 Defender를 통해 조건부 액세스를 설정하는 방법에 대한 자세한 내용은 Endpoint 및 [Intune용 Defender를 참조하세요.](https://docs.microsoft.com/mem/intune/protect/advanced-threat-protection)</span><span class="sxs-lookup"><span data-stu-id="5f3da-115">For more information about how to set up Conditional Access with Defender for Endpoint for iOS, see [Defender for Endpoint and Intune](https://docs.microsoft.com/mem/intune/protect/advanced-threat-protection).</span></span>

## <a name="web-protection-and-vpn"></a><span data-ttu-id="5f3da-116">웹 보호 및 VPN</span><span class="sxs-lookup"><span data-stu-id="5f3da-116">Web Protection and VPN</span></span>

<span data-ttu-id="5f3da-117">기본적으로 iOS용 Endpoint용 Defender에는 웹 보호 기능이 포함 및 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="5f3da-117">By default, Defender for Endpoint for iOS includes and enables the web protection feature.</span></span> <span data-ttu-id="5f3da-118">[웹 보호는](web-protection-overview.md) 웹 위협으로부터 장치를 보호하고 피싱 공격으로부터 사용자를 보호하는 데 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="5f3da-118">[Web protection](web-protection-overview.md) helps to secure devices against web threats and protect users from phishing attacks.</span></span> <span data-ttu-id="5f3da-119">iOS용 끝점용 Defender는 VPN을 사용하여 이 보호를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="5f3da-119">Defender for Endpoint for iOS uses a VPN in order to provide this protection.</span></span> <span data-ttu-id="5f3da-120">이는 로컬 VPN으로, 기존 VPN과 달리 네트워크 트래픽은 장치 외부로 전송되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="5f3da-120">Please note this is a local VPN and unlike traditional VPN, network traffic is not sent outside the device.</span></span>

<span data-ttu-id="5f3da-121">기본적으로 사용하도록 설정되어 있는 동안 VPN을 사용하지 않도록 설정해야 하는 경우도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5f3da-121">While enabled by default, there might be some cases that require you to disable VPN.</span></span> <span data-ttu-id="5f3da-122">예를 들어 VPN을 구성할 때 작동하지 않는 일부 앱을 실행하려는 경우를 예로 들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5f3da-122">For example, you want to run some apps that do not work when a VPN is configured.</span></span> <span data-ttu-id="5f3da-123">이러한 경우 아래 단계에 따라 디바이스의 앱에서 VPN을 사용하지 않도록 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5f3da-123">In such cases, you can choose to disable VPN from the app on the device by following the steps below:</span></span>

1. <span data-ttu-id="5f3da-124">iOS 장치에서 설정 앱을  열고 일반을 클릭하거나 **탭한** 다음 VPN 을 **탭합니다.**</span><span class="sxs-lookup"><span data-stu-id="5f3da-124">On your iOS device, open the **Settings** app, click or tap **General** and then **VPN**.</span></span>
1. <span data-ttu-id="5f3da-125">Microsoft Defender ATP의 "i" 단추를 클릭하거나 탭합니다.</span><span class="sxs-lookup"><span data-stu-id="5f3da-125">Click or tap the "i" button for Microsoft Defender ATP.</span></span>
1. <span data-ttu-id="5f3da-126">VPN을 사용하지 않도록 설정하기 **위해 연결 필요를** 해제합니다.</span><span class="sxs-lookup"><span data-stu-id="5f3da-126">Toggle off **Connect On Demand** to disable VPN.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="5f3da-127">![VPN 구성 필요 시 연결](images/ios-vpn-config.png)</span><span class="sxs-lookup"><span data-stu-id="5f3da-127">![VPN config connect on demand](images/ios-vpn-config.png)</span></span>

> [!NOTE]
> <span data-ttu-id="5f3da-128">VPN을 사용하지 않도록 설정하면 웹 보호를 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="5f3da-128">Web Protection will not be available when VPN is disabled.</span></span> <span data-ttu-id="5f3da-129">웹 보호를 다시 사용하도록 설정하려면 장치에서 끝점용 Microsoft Defender 앱을 열고 VPN 시작 을 클릭하거나 **탭합니다.**</span><span class="sxs-lookup"><span data-stu-id="5f3da-129">To re-enable Web Protection, open the Microsoft Defender for Endpoint app on the device and click or tap **Start VPN**.</span></span>

## <a name="co-existence-of-multiple-vpn-profiles"></a><span data-ttu-id="5f3da-130">여러 VPN 프로필의 동시 사용</span><span class="sxs-lookup"><span data-stu-id="5f3da-130">Co-existence of multiple VPN profiles</span></span>

<span data-ttu-id="5f3da-131">Apple iOS는 동시에 활성화하기 위해 여러 장치 전체의 VPN을 지원하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="5f3da-131">Apple iOS does not support multiple device-wide VPNs to be active simultaneously.</span></span> <span data-ttu-id="5f3da-132">디바이스에 여러 VPN 프로필이 존재할 수 있는 반면 한 번의 VPN만 활성화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5f3da-132">While multiple VPN profiles can exist on the device, only one VPN can be active at a time.</span></span>


## <a name="configure-compliance-policy-against-jailbroken-devices"></a><span data-ttu-id="5f3da-133">무단으로 보호된 장치에 대한 규정 준수 정책 구성</span><span class="sxs-lookup"><span data-stu-id="5f3da-133">Configure compliance policy against jailbroken devices</span></span>

<span data-ttu-id="5f3da-134">무단으로 보호된 iOS 장치에서 회사 데이터에 액세스하지 못하도록 보호하기 위해 Intune에서 다음 규정 준수 정책을 설정하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="5f3da-134">To protect corporate data from being accessed on jailbroken iOS devices, we recommend that you set up the following compliance policy on Intune.</span></span>

> [!NOTE]
> <span data-ttu-id="5f3da-135">현재 Microsoft Defender for Endpoint for iOS에서는 탈옥 시나리오에 대한 보호 기능을 제공하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="5f3da-135">At this time Microsoft Defender for Endpoint for iOS does not provide protection against jailbreak scenarios.</span></span> <span data-ttu-id="5f3da-136">무단으로 보호된 장치에서 사용하는 경우 회사 전자 메일 ID 및 회사 프로필 사진(사용 가능한 경우)과 같이 응용 프로그램에서 사용하는 특정 시나리오 데이터를 로컬로 노출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5f3da-136">If used on a jailbroken device, then in specific scenarios data that is used by the application like your corporate email id and corporate profile picture (if available) can be exposed locally</span></span>

<span data-ttu-id="5f3da-137">다음 단계에 따라 무단으로 보호된 장치에 대한 규정 준수 정책을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5f3da-137">Follow the steps below to create a compliance policy against jailbroken devices.</span></span>

1. <span data-ttu-id="5f3da-138">[Microsoft Endpoint Manager 관리 센터에서](https://go.microsoft.com/fwlink/?linkid=2109431)장치 **준수** 정책 정책  ->    ->  **만들기 정책으로 이동하세요.**</span><span class="sxs-lookup"><span data-stu-id="5f3da-138">In [Microsoft Endpoint Manager admin center](https://go.microsoft.com/fwlink/?linkid=2109431), go to **Devices** -> **Compliance policies** -> **Create Policy**.</span></span> <span data-ttu-id="5f3da-139">플랫폼으로 "iOS/iPadOS"를 선택하고 만들기를 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="5f3da-139">Select "iOS/iPadOS" as platform and click **Create**.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="5f3da-140">![정책 만들기](images/ios-jb-policy.png)</span><span class="sxs-lookup"><span data-stu-id="5f3da-140">![Create Policy](images/ios-jb-policy.png)</span></span>

2. <span data-ttu-id="5f3da-141">정책의 이름(예: "탈옥에 대한 규정 준수 정책")을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="5f3da-141">Specify a name of the policy, for example "Compliance Policy for Jailbreak".</span></span>
3. <span data-ttu-id="5f3da-142">준수 설정 페이지에서 장치 상태 **섹션을** 클릭하여 확장하고 **무단으로** 차단된 장치 차단 **필드를** 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="5f3da-142">In the compliance settings page, click to expand **Device Health** section and click **Block** for **Jailbroken devices** field.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="5f3da-143">![정책 설정](images/ios-jb-settings.png)</span><span class="sxs-lookup"><span data-stu-id="5f3da-143">![Policy Settings](images/ios-jb-settings.png)</span></span>

4. <span data-ttu-id="5f3da-144">준수하지 *않는* 작업에 대한 작업 섹션에서 요구 사항에 따라 작업을 선택하고 다음 을 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="5f3da-144">In the *Action for noncompliance* section, select the actions as per your requirements and select **Next**.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="5f3da-145">![정책 작업](images/ios-jb-actions.png)</span><span class="sxs-lookup"><span data-stu-id="5f3da-145">![Policy Actions](images/ios-jb-actions.png)</span></span>

5. <span data-ttu-id="5f3da-146">할당 *섹션에서* 이 정책에 포함할 사용자 그룹을 선택하고 다음 을 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="5f3da-146">In the *Assignments* section, select the user groups that you want to include for this policy and then select **Next**.</span></span>
6. <span data-ttu-id="5f3da-147">**검토+만들기 섹션에서** 입력한 정보가 모두 올바른지 확인한 다음 만들기를 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="5f3da-147">In the **Review+Create** section, verify that all the information entered is correct and then select **Create**.</span></span>

## <a name="configure-custom-indicators"></a><span data-ttu-id="5f3da-148">사용자 지정 표시기 구성</span><span class="sxs-lookup"><span data-stu-id="5f3da-148">Configure custom indicators</span></span>

<span data-ttu-id="5f3da-149">iOS용 Endpoint용 Defender를 사용하면 관리자가 iOS 장치에서도 사용자 지정 표시기를 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5f3da-149">Defender for Endpoint for iOS enables admins to configure custom indicators on iOS devices as well.</span></span> <span data-ttu-id="5f3da-150">사용자 지정 표시기를 구성하는 방법에 대한 자세한 내용은 [지표 관리를 참조하세요.](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/manage-indicators)</span><span class="sxs-lookup"><span data-stu-id="5f3da-150">For more information on how to configure custom indicators, see [Manage indicators](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/manage-indicators).</span></span>

> [!NOTE]
> <span data-ttu-id="5f3da-151">iOS용 Endpoint용 Defender는 IP 주소 및 URL/도메인에 대한 사용자 지정 표시기만 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5f3da-151">Defender for Endpoint for iOS supports creating custom indicators only for IP addresses and URLs/domains.</span></span>

## <a name="report-unsafe-site"></a><span data-ttu-id="5f3da-152">안전하지 않은 사이트 보고</span><span class="sxs-lookup"><span data-stu-id="5f3da-152">Report unsafe site</span></span>

<span data-ttu-id="5f3da-153">피싱 웹 사이트는 개인 또는 재무 정보를 얻기 위해 신뢰할 수 있는 웹 사이트를 가장합니다.</span><span class="sxs-lookup"><span data-stu-id="5f3da-153">Phishing websites impersonate trustworthy websites for the purpose of obtaining your personal or financial information.</span></span> <span data-ttu-id="5f3da-154">피싱 [](https://www.microsoft.com/wdsi/filesubmission/exploitguard/networkprotection) 사이트일 수 있는 웹 사이트를 보고하려는 경우 네트워크 보호에 대한 피드백 제공 페이지를 방문하세요.</span><span class="sxs-lookup"><span data-stu-id="5f3da-154">Visit the [Provide feedback about network protection](https://www.microsoft.com/wdsi/filesubmission/exploitguard/networkprotection) page if you want to report a website that could be a phishing site.</span></span>

## <a name="battery-consumption-issues-on-ios-when-microsoft-defender-for-endpoint-is-installed"></a><span data-ttu-id="5f3da-155">끝점용 Microsoft Defender를 설치할 때 iOS의 배터리 사용 문제</span><span class="sxs-lookup"><span data-stu-id="5f3da-155">Battery Consumption issues on iOS when Microsoft Defender for Endpoint is installed</span></span>

<span data-ttu-id="5f3da-156">앱의 배터리 사용량은 CPU 및 네트워크 사용량을 비롯한 다양한 요인에 따라 Apple에서 계산합니다.</span><span class="sxs-lookup"><span data-stu-id="5f3da-156">The battery usage by an app is computed by Apple based on a multitude of factors including CPU and Network usage.</span></span> <span data-ttu-id="5f3da-157">끝점용 Microsoft Defender는 백그라운드에서 로컬/루프백 VPN을 사용하여 악성 웹 사이트 또는 연결에 대한 웹 트래픽을 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="5f3da-157">Microsoft Defender for Endpoint uses a local/loop-back VPN in the background to check web traffic for any malicious websites or connections.</span></span> <span data-ttu-id="5f3da-158">모든 앱에서 네트워크 패킷이 이 검사를 통과하여 끝점용 Microsoft Defender의 배터리 사용이 부정확하게 계산됩니다.</span><span class="sxs-lookup"><span data-stu-id="5f3da-158">Network packets from any app go through this check and that causes the battery usage of Microsoft Defender for Endpoint to be computed inaccurately.</span></span> <span data-ttu-id="5f3da-159">이렇게 하면 사용자에게 거짓 인상을 줍니다.</span><span class="sxs-lookup"><span data-stu-id="5f3da-159">This gives a false impression to the user.</span></span> <span data-ttu-id="5f3da-160">끝점용 Microsoft Defender의 실제 배터리 사용은 장치의 배터리 설정 페이지에 표시된 것보다 적습니다.</span><span class="sxs-lookup"><span data-stu-id="5f3da-160">The actual battery consumption of Microsoft Defender for Endpoint is lesser than what is shown on the Battery Settings page on the device.</span></span> <span data-ttu-id="5f3da-161">이는 배터리 소비를 이해하기 위해 끝점용 Microsoft Defender 앱에서 수행한 테스트를 기반으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="5f3da-161">This is based on conducted tests done on the Microsoft Defender for Endpoint app to understand battery consumption.</span></span>

<span data-ttu-id="5f3da-162">또한 사용된 VPN은 로컬 VPN으로, 기존 VPN과 달리 네트워크 트래픽은 장치 외부로 전송되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="5f3da-162">Also the VPN used is a local VPN and unlike traditional VPNs, network traffic is not sent outside the device.</span></span>
