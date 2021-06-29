---
title: iOS의 끝점용 Microsoft Defender와 관련된 FAQ 관련 문제 해결 및 답변 찾기
description: 문제 해결 및 FAQ - iOS의 끝점용 Microsoft Defender
keywords: Microsoft, defender, Endpoint용 Microsoft Defender, ios, 문제 해결, FAQ, 방법
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
ms.openlocfilehash: b82b6993ce9ed5a3f0f3e6e13e8a260a185c9730
ms.sourcegitcommit: 6749455c52b0f98a92f6fffbc2bb86caf3538bd8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/29/2021
ms.locfileid: "53194976"
---
# <a name="troubleshoot-issues-and-find-answers-to-faqs-on-microsoft-defender-for-endpoint-on-ios"></a><span data-ttu-id="cfc81-104">iOS의 끝점용 Microsoft Defender에서 문제를 해결하고 FAQ에 대한 답변 찾기</span><span class="sxs-lookup"><span data-stu-id="cfc81-104">Troubleshoot issues and find answers to FAQs on Microsoft Defender for Endpoint on iOS</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="cfc81-105">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="cfc81-105">**Applies to:**</span></span>
- [<span data-ttu-id="cfc81-106">엔드포인트용 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="cfc81-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="cfc81-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="cfc81-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="cfc81-108">Endpoint용 Defender를 경험하고 싶나요?</span><span class="sxs-lookup"><span data-stu-id="cfc81-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="cfc81-109">무료 평가판에 등록합니다.</span><span class="sxs-lookup"><span data-stu-id="cfc81-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

<span data-ttu-id="cfc81-110">이 항목에서는 iOS에서 끝점용 Microsoft Defender를 사용할 때 발생할 수 있는 문제를 해결하는 데 도움이 되는 문제 해결 정보를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="cfc81-110">This topic provides troubleshooting information to help you address issues that may arise as you use Microsoft Defender for Endpoint on iOS.</span></span>



> [!NOTE]
> <span data-ttu-id="cfc81-111">iOS의 끝점용 Defender는 VPN을 사용하여 웹 보호 기능을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="cfc81-111">Defender for Endpoint on iOS would use a VPN in order to provide the Web Protection feature.</span></span> <span data-ttu-id="cfc81-112">이는 일반 VPN이 아니며 장치 외부에서 트래픽을 취하지 않는 로컬/자체 루프 VPN입니다.</span><span class="sxs-lookup"><span data-stu-id="cfc81-112">This is not a regular VPN and is a local/self-looping VPN that does not take traffic outside the device.</span></span>

## <a name="apps-dont-work-when-vpn-is-turned-on"></a><span data-ttu-id="cfc81-113">VPN이 켜져 있을 때 앱이 작동하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="cfc81-113">Apps don't work when VPN is turned on</span></span>
<span data-ttu-id="cfc81-114">활성 VPN이 감지되면 일부 앱이 작동하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="cfc81-114">There are some apps that stop functioning when an active VPN is detected.</span></span> <span data-ttu-id="cfc81-115">이러한 앱을 사용하는 동안 VPN을 사용하지 않도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cfc81-115">You can disable the VPN during the time you are using such apps.</span></span> 

<span data-ttu-id="cfc81-116">기본적으로 iOS의 Endpoint용 Defender에는 웹 보호 기능이 포함 및 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="cfc81-116">By default, Defender for Endpoint on iOS includes and enables the web protection feature.</span></span> <span data-ttu-id="cfc81-117">[웹 보호는](web-protection-overview.md) 웹 위협으로부터 장치를 보호하고 피싱 공격으로부터 사용자를 보호하는 데 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="cfc81-117">[Web protection](web-protection-overview.md) helps to secure devices against web threats and protect users from phishing attacks.</span></span> <span data-ttu-id="cfc81-118">iOS의 끝점용 Defender는 VPN을 사용하여 이 보호를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="cfc81-118">Defender for Endpoint on iOS uses a VPN in order to provide this protection.</span></span> <span data-ttu-id="cfc81-119">이는 로컬 VPN으로, 기존 VPN과 달리 네트워크 트래픽은 장치 외부로 전송되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="cfc81-119">Please note this is a local VPN and unlike traditional VPN, network traffic is not sent outside the device.</span></span>

<span data-ttu-id="cfc81-120">기본적으로 사용하도록 설정되어 있는 동안 VPN을 사용하지 않도록 설정해야 하는 경우도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cfc81-120">While enabled by default, there might be some cases that require you to disable VPN.</span></span> <span data-ttu-id="cfc81-121">예를 들어 VPN을 구성할 때 작동하지 않는 일부 앱을 실행하려는 경우를 예로 들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cfc81-121">For example, you want to run some apps that do not work when a VPN is configured.</span></span> <span data-ttu-id="cfc81-122">이러한 경우 아래 단계에 따라 디바이스의 앱에서 VPN을 사용하지 않도록 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cfc81-122">In such cases, you can choose to disable VPN from the app on the device by following the steps below:</span></span>

1. <span data-ttu-id="cfc81-123">iOS 장치에서 설정 열고 **일반을 클릭하거나** **탭한** 다음 **VPN 을 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="cfc81-123">On your iOS device, open the **Settings** app, click or tap **General** and then **VPN**.</span></span>
1. <span data-ttu-id="cfc81-124">끝점용 Microsoft Defender의 "i" 단추를 클릭하거나 탭합니다.</span><span class="sxs-lookup"><span data-stu-id="cfc81-124">Click or tap the "i" button for Microsoft Defender for Endpoint.</span></span>
1. <span data-ttu-id="cfc81-125">VPN을 사용하지 **커넥트 On Demand를** 해제합니다.</span><span class="sxs-lookup"><span data-stu-id="cfc81-125">Toggle off **Connect On Demand** to disable VPN.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="cfc81-126">![VPN 구성 필요 시 연결](images/ios-vpn-config.png)</span><span class="sxs-lookup"><span data-stu-id="cfc81-126">![VPN config connect on demand](images/ios-vpn-config.png)</span></span>

> [!NOTE]
> <span data-ttu-id="cfc81-127">VPN을 사용하지 않도록 설정하면 웹 보호를 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="cfc81-127">Web Protection will not be available when VPN is disabled.</span></span> <span data-ttu-id="cfc81-128">웹 보호를 다시 사용하도록 설정하려면 장치에서 끝점용 Microsoft Defender 앱을 열고 VPN 시작 을 클릭하거나 **탭합니다.**</span><span class="sxs-lookup"><span data-stu-id="cfc81-128">To re-enable Web Protection, open the Microsoft Defender for Endpoint app on the device and click or tap **Start VPN**.</span></span>

## <a name="co-existence-with-multiple-vpn-profiles"></a><span data-ttu-id="cfc81-129">여러 VPN 프로필과 함께 사용</span><span class="sxs-lookup"><span data-stu-id="cfc81-129">Co-existence with multiple VPN profiles</span></span>

<span data-ttu-id="cfc81-130">Apple iOS는 동시에  활성화하기 위해 여러 장치 전체의 VPN을 지원하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="cfc81-130">Apple iOS does not support multiple **device-wide** VPNs to be active simultaneously.</span></span> <span data-ttu-id="cfc81-131">디바이스에 여러 VPN 프로필이 존재할 수 있는 반면 한 번의 VPN만 활성화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cfc81-131">While multiple VPN profiles can exist on the device, only one VPN can be active at a time.</span></span>

<span data-ttu-id="cfc81-132">끝점용 Microsoft Defender VPN은 앱 또는 *"개인"으로* 구성된 다른 VPN과 공존할 수 있습니다. </span><span class="sxs-lookup"><span data-stu-id="cfc81-132">Microsoft Defender for Endpoint VPN can co-exist with other VPNs that are configured as *per-app* or *"Personal"*.</span></span>

## <a name="battery-consumption"></a><span data-ttu-id="cfc81-133">배터리 사용</span><span class="sxs-lookup"><span data-stu-id="cfc81-133">Battery consumption</span></span>

<span data-ttu-id="cfc81-134">설정 앱에서 iOS는 특정 기간 동안 사용자에게 표시되는 앱의 배터리 사용만 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="cfc81-134">In the Settings app, iOS only shows battery usage of apps that are visible to the user for a specific duration of time.</span></span> <span data-ttu-id="cfc81-135">화면에 표시된 앱의 배터리 사용량은 해당 기간 동안만 사용하며 CPU 및 네트워크 사용량을 비롯한 다양한 요인에 따라 iOS에서 계산됩니다.</span><span class="sxs-lookup"><span data-stu-id="cfc81-135">The battery usage by apps shown on the screen are only for that time duration and is computed by iOS based on a multitude of factors including CPU and Network usage.</span></span> <span data-ttu-id="cfc81-136">끝점용 Microsoft Defender는 백그라운드에서 로컬/루프백 VPN을 사용하여 악성 웹 사이트 또는 연결에 대한 웹 트래픽을 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="cfc81-136">Microsoft Defender for Endpoint uses a local/loop-back VPN in the background to check web traffic for any malicious websites or connections.</span></span> <span data-ttu-id="cfc81-137">모든 앱에서 네트워크 패킷이 이 검사를 통과하여 끝점용 Microsoft Defender의 배터리 사용이 부정확하게 계산됩니다.</span><span class="sxs-lookup"><span data-stu-id="cfc81-137">Network packets from any app go through this check and that causes the battery usage of Microsoft Defender for Endpoint to be computed inaccurately.</span></span> <span data-ttu-id="cfc81-138">끝점용 Microsoft Defender의 실제 배터리 사용은 장치의 배터리 설정 페이지에 표시된 것보다 훨씬 적습니다.</span><span class="sxs-lookup"><span data-stu-id="cfc81-138">The actual battery consumption of Microsoft Defender for Endpoint is much less than what is shown on the Battery Settings page on the device.</span></span>

<span data-ttu-id="cfc81-139">백그라운드에서 실행되는 끝점용 Microsoft Defender의 하루 평균 배터리 사용량은 하루 동안 소비된 전체 배터리의 **약 8.81%입니다.**</span><span class="sxs-lookup"><span data-stu-id="cfc81-139">On an average, per-day battery usage by Microsoft Defender for Endpoint running on the background is **approximately 8.81% of overall battery consumed in that day**.</span></span> <span data-ttu-id="cfc81-140">이 메트릭은 최종 사용자 장치에서 끝점용 Microsoft Defender의 실제 사용 현황을 기준으로 Apple에서 보고하며 위에서 언급한 이유 때문에 네트워크 활동이 있는 다른 앱에도 고려될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cfc81-140">This metric is reported by Apple based on actual usage of Microsoft Defender for Endpoint on end-user devices and due to reasons mentioned above can also be accounted to other apps that have network activity.</span></span>

<span data-ttu-id="cfc81-141">또한 사용되는 VPN은 로컬 VPN으로, 기존 VPN과 달리 네트워크 트래픽은 장치 외부로 전송되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="cfc81-141">Also, the VPN used is a local VPN and unlike a traditional VPN, network traffic is not sent outside the device.</span></span>

## <a name="data-usage"></a><span data-ttu-id="cfc81-142">데이터 사용 현황</span><span class="sxs-lookup"><span data-stu-id="cfc81-142">Data usage</span></span>

<span data-ttu-id="cfc81-143">끝점용 Microsoft Defender는 로컬/루프백 VPN을 사용하여 악성 웹 사이트 또는 연결에 대한 웹 트래픽을 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="cfc81-143">Microsoft Defender for Endpoint uses a local/loopback VPN to check web traffic for any malicious websites or connections.</span></span> <span data-ttu-id="cfc81-144">이러한 이유로 끝점 데이터 사용에 대한 Microsoft Defender가 부정확하게 고려될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cfc81-144">Due to this reason, Microsoft Defender for Endpoint data usage can be inaccurately accounted for.</span></span> <span data-ttu-id="cfc81-145">또한 디바이스가 셀룰러 네트워크에만 있는 경우 서비스 공급자가 보고하는 데이터 사용량은 실제 사용에 매우 근접한 반면 설정 앱에서 Apple은 소비된 실제 데이터의 약 1.5~2배를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="cfc81-145">We have also observed that if the device is on cellular network only, the data usage reported by service provider is very close to the actual consumption whereas in the Settings app, Apple shows about 1.5x to 2x of actual data consumed.</span></span>

<span data-ttu-id="cfc81-146">다른 VPN 서비스와도 비슷한 관찰을 하여 Apple에 보고했습니다.</span><span class="sxs-lookup"><span data-stu-id="cfc81-146">We have similar observations with other VPN services as well and have reported this to Apple.</span></span>

<span data-ttu-id="cfc81-147">또한 더 나은 보호를 제공하기 위해 백 엔드 서비스를 통해 끝점에 대한 Microsoft Defender를 최신으로 설정하는 것이 중요합니다.</span><span class="sxs-lookup"><span data-stu-id="cfc81-147">In addition, it is critical for Microsoft Defender for Endpoint to be up to date with our backend services to provide better protection.</span></span> <span data-ttu-id="cfc81-148">그러나 Microsoft Defender for Endpoint의 데이터 사용을 최적화하기 위해 작업 중입니다.</span><span class="sxs-lookup"><span data-stu-id="cfc81-148">However, we are working on optimizing the data usage by Microsoft Defender for Endpoint.</span></span>

## <a name="report-unsafe-site"></a><span data-ttu-id="cfc81-149">안전하지 않은 사이트 보고</span><span class="sxs-lookup"><span data-stu-id="cfc81-149">Report unsafe site</span></span>

<span data-ttu-id="cfc81-150">피싱 웹 사이트는 개인 또는 재무 정보를 얻기 위해 신뢰할 수 있는 웹 사이트를 가장합니다.</span><span class="sxs-lookup"><span data-stu-id="cfc81-150">Phishing websites impersonate trustworthy websites for the purpose of obtaining your personal or financial information.</span></span> <span data-ttu-id="cfc81-151">네트워크 [보호에](https://www.microsoft.com/wdsi/filesubmission/exploitguard/networkprotection) 대한 피드백 제공 페이지를 방문하여 피싱 사이트일 수 있는 웹 사이트를 보고합니다.</span><span class="sxs-lookup"><span data-stu-id="cfc81-151">Visit the [Provide feedback about network protection](https://www.microsoft.com/wdsi/filesubmission/exploitguard/networkprotection) page to report a website that could be a phishing site.</span></span>

## <a name="malicious-site-detected"></a><span data-ttu-id="cfc81-152">악성 사이트가 검색되었습니다.</span><span class="sxs-lookup"><span data-stu-id="cfc81-152">Malicious site detected</span></span>

<span data-ttu-id="cfc81-153">끝점용 Microsoft Defender는 피싱 또는 기타 웹 기반 공격으로부터 보호합니다.</span><span class="sxs-lookup"><span data-stu-id="cfc81-153">Microsoft Defender for Endpoint protects you against phishing or other web-based attacks.</span></span> <span data-ttu-id="cfc81-154">악의적인 사이트가 감지되면 연결이 차단되고 경고가 조직의 보안 센터 포털로 전송됩니다.</span><span class="sxs-lookup"><span data-stu-id="cfc81-154">If a malicious site is detected, the connection is blocked and an alert is sent to the organization's Security Center portal.</span></span> <span data-ttu-id="cfc81-155">경고에는 연결의 도메인 이름, 원격 IP 주소 및 장치 세부 정보가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="cfc81-155">The alert includes the domain name of the connection, remote IP address and the device details.</span></span>

<span data-ttu-id="cfc81-156">또한 iOS 장치에 알림이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="cfc81-156">In addition, a notification is shown on the iOS device.</span></span> <span data-ttu-id="cfc81-157">알림을 탭하면 사용자가 세부 정보를 검토할 수 있는 다음 화면이 열립니다.</span><span class="sxs-lookup"><span data-stu-id="cfc81-157">Tapping on the notification opens the following screen for the user to review the details.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="cfc81-158">![안전하지 않은 알림으로 보고된 사이트의 이미지](images/ios-phish-alert.png)</span><span class="sxs-lookup"><span data-stu-id="cfc81-158">![Image of site reported as unsafe notification](images/ios-phish-alert.png)</span></span>

## <a name="data-and-privacy"></a><span data-ttu-id="cfc81-159">데이터 및 개인 정보</span><span class="sxs-lookup"><span data-stu-id="cfc81-159">Data and Privacy</span></span>

<span data-ttu-id="cfc81-160">수집된 데이터 및 개인 정보 보호에 대한 자세한 내용은 개인 정보 보호 [정보 - iOS의 끝점용 Microsoft Defender를 참조하세요.](ios-privacy.md)</span><span class="sxs-lookup"><span data-stu-id="cfc81-160">For details about data collected and privacy, see [Privacy Information - Microsoft Defender for Endpoint on iOS](ios-privacy.md).</span></span>

