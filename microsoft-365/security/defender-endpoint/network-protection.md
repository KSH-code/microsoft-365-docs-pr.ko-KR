---
title: 네트워크 보호를 사용하여 잘못된 사이트에 대한 연결 방지
description: 사용자가 알려진 악성 및 의심스러운 네트워크 주소에 액세스하지 못하게 하여 네트워크 보호
keywords: 네트워크 보호, 악용, 악성 웹 사이트, ip, 도메인, 도메인
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: Normal
audience: ITPro
author: denisebmsft
ms.author: deniseb
ms.reviewer: ''
manager: dansimp
ms.custom: asr
ms.technology: mde
ms.topic: how-to
ms.openlocfilehash: b6b664d471e238e2feb1e1aedd100c1299fc5bbe
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/08/2021
ms.locfileid: "52844265"
---
# <a name="protect-your-network"></a><span data-ttu-id="5288a-104">네트워크 보호</span><span class="sxs-lookup"><span data-stu-id="5288a-104">Protect your network</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="5288a-105">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="5288a-105">**Applies to:**</span></span>
- [<span data-ttu-id="5288a-106">엔드포인트용 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="5288a-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="5288a-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="5288a-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="5288a-108">끝점용 Microsoft Defender를 경험하고 싶나요?</span><span class="sxs-lookup"><span data-stu-id="5288a-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="5288a-109">무료 평가판에 등록합니다.</span><span class="sxs-lookup"><span data-stu-id="5288a-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

<span data-ttu-id="5288a-110">네트워크 보호는 인터넷 기반 이벤트에서 장치의 공격 표면을 줄이는 데 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="5288a-110">Network protection helps reduce the attack surface of your devices from Internet-based events.</span></span> <span data-ttu-id="5288a-111">이를 통해 직원이 응용 프로그램을 사용하여 인터넷에서 피싱 사기, 악용 및 기타 악성 콘텐츠를 호스팅할 수 있는 위험한 도메인에 액세스할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="5288a-111">It prevents employees from using any application to access dangerous domains that might host phishing scams, exploits, and other malicious content on the Internet.</span></span> <span data-ttu-id="5288a-112">네트워크 보호는 신뢰도 [Microsoft Defender SmartScreen(도메인](/windows/security/threat-protection/microsoft-defender-smartscreen/microsoft-defender-smartscreen-overview) 또는 호스트 이름 기반)에 연결하려고 하는 모든 아웃바운드 HTTP 트래픽을 차단하기 위해 네트워크 보호 범위를 확장합니다.</span><span class="sxs-lookup"><span data-stu-id="5288a-112">Network protection expands the scope of [Microsoft Defender SmartScreen](/windows/security/threat-protection/microsoft-defender-smartscreen/microsoft-defender-smartscreen-overview) to block all outbound HTTP(s) traffic that attempts to connect to low-reputation sources (based on the domain or hostname).</span></span>

<span data-ttu-id="5288a-113">네트워크 보호는 Windows 버전 1709부터 Windows 10 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="5288a-113">Network protection is supported on Windows, beginning with Windows 10, version 1709.</span></span> <span data-ttu-id="5288a-114">네트워크 보호는 아직 다른 운영 체제에서 지원되지 않지만, 웹 보호는 다른 운영 체제를 기반으로 하는 Microsoft Edge 지원 Chromium.</span><span class="sxs-lookup"><span data-stu-id="5288a-114">Network protection is not yet supported on other operating systems, but web protection is supported using the new Microsoft Edge based on Chromium.</span></span> <span data-ttu-id="5288a-115">자세한 내용은 웹 [보호를 참조합니다.](web-protection-overview.md)</span><span class="sxs-lookup"><span data-stu-id="5288a-115">To learn more, see [Web protection](web-protection-overview.md).</span></span>

<span data-ttu-id="5288a-116">네트워크 보호는 웹 보호의 [보호를](web-protection-overview.md) 운영 체제 수준으로 확장합니다.</span><span class="sxs-lookup"><span data-stu-id="5288a-116">Network protection extends the protection in [Web protection](web-protection-overview.md) to the operating system level.</span></span> <span data-ttu-id="5288a-117">이 기능은 지원되는 다른 브라우저 및 비 브라우저 응용 프로그램에 Edge의 웹 보호 기능을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="5288a-117">It provides web protection functionality in Edge to other supported browsers and non-browser applications.</span></span> <span data-ttu-id="5288a-118">또한 네트워크 보호는 끝점 감지 및 응답과 함께 사용될 경우 IOC(손상 표시기)를 표시하고 [차단합니다.](overview-endpoint-detection-response.md)</span><span class="sxs-lookup"><span data-stu-id="5288a-118">In addition, network protection provides visibility and blocking of indicators of compromise (IOCs) when used with [Endpoint detection and response](overview-endpoint-detection-response.md).</span></span> <span data-ttu-id="5288a-119">예를 들어 네트워크 보호는 사용자 지정 [표시기 에서 작동합니다.](manage-indicators.md)</span><span class="sxs-lookup"><span data-stu-id="5288a-119">For example, network protection works with your [custom indicators](manage-indicators.md).</span></span>

<span data-ttu-id="5288a-120">네트워크 보호를 사용하도록 설정하는 방법에 대한 자세한 내용은 네트워크 보호 사용 [을 참조하세요.](enable-network-protection.md)</span><span class="sxs-lookup"><span data-stu-id="5288a-120">For more information about how to enable network protection, see [Enable network protection](enable-network-protection.md).</span></span> <span data-ttu-id="5288a-121">그룹 정책, PowerShell 또는 MDM CSP를 사용하여 네트워크에서 네트워크 보호를 사용하도록 설정하고 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5288a-121">Use Group Policy, PowerShell, or MDM CSPs to enable and manage network protection in your network.</span></span>

> [!TIP]
> <span data-ttu-id="5288a-122">네트워크 보호가 작동하는 방법을 demo.wd.microsoft.com Microsoft Defender for [Endpoint](https://demo.wd.microsoft.com?ocid=cx-wddocs-testground) testground 사이트를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="5288a-122">See the Microsoft Defender for Endpoint testground site at [demo.wd.microsoft.com](https://demo.wd.microsoft.com?ocid=cx-wddocs-testground) to see how network protection works.</span></span>

<span data-ttu-id="5288a-123">네트워크 보호는 Exploit Protection 이벤트에 대한 자세한 보고를 제공하며 경고 조사 시나리오의 일부로 차단하는 [끝점용 Microsoft Defender와](microsoft-defender-endpoint.md) [가장 잘 작동합니다.](investigate-alerts.md)</span><span class="sxs-lookup"><span data-stu-id="5288a-123">Network protection works best with [Microsoft Defender for Endpoint](microsoft-defender-endpoint.md), which gives you detailed reporting into exploit protection events and blocks as part of [alert investigation scenarios](investigate-alerts.md).</span></span>

<span data-ttu-id="5288a-124">네트워크 보호가 연결을 차단하면 알림 센터에서 알림이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="5288a-124">When network protection blocks a connection, a notification is displayed from the Action Center.</span></span> <span data-ttu-id="5288a-125">보안 운영 팀은 조직의 [세부](customize-attack-surface-reduction.md#customize-the-notification) 정보 및 연락처 정보로 알림을 사용자 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5288a-125">Your security operations team can [customize the notification](customize-attack-surface-reduction.md#customize-the-notification) with your organization's details and contact information.</span></span> <span data-ttu-id="5288a-126">또한 모니터링할 특정 기술에 맞게 개별 공격 표면 감소 규칙을 사용하도록 설정하고 사용자 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5288a-126">In addition, individual attack surface reduction rules can be enabled and customized to suit certain techniques to monitor.</span></span>

<span data-ttu-id="5288a-127">감사 모드를 [사용하여](audit-windows-defender.md) 네트워크 보호가 사용하도록 설정된 경우 조직에 어떤 영향을 미치는지 평가할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5288a-127">You can also use [audit mode](audit-windows-defender.md) to evaluate how network protection would impact your organization if it were enabled.</span></span>

## <a name="requirements"></a><span data-ttu-id="5288a-128">요구 사항</span><span class="sxs-lookup"><span data-stu-id="5288a-128">Requirements</span></span>

<span data-ttu-id="5288a-129">네트워크 보호를 사용하려면 Windows 10 Pro Enterprise 및 Microsoft Defender 바이러스 백신 보호가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="5288a-129">Network protection requires Windows 10 Pro or Enterprise, and Microsoft Defender Antivirus real-time protection.</span></span>

| <span data-ttu-id="5288a-130">Windows 버전</span><span class="sxs-lookup"><span data-stu-id="5288a-130">Windows version</span></span> | <span data-ttu-id="5288a-131">Windows Defender 바이러스 백신</span><span class="sxs-lookup"><span data-stu-id="5288a-131">Microsoft Defender Antivirus</span></span> |
|:---|:---|
| <span data-ttu-id="5288a-132">Windows 10 버전 1709 이상</span><span class="sxs-lookup"><span data-stu-id="5288a-132">Windows 10 version 1709 or later</span></span> <p><span data-ttu-id="5288a-133">Windows 서버 1803 이상</span><span class="sxs-lookup"><span data-stu-id="5288a-133">Windows Server 1803 or later</span></span> | <span data-ttu-id="5288a-134">[Microsoft Defender 바이러스 백신 보호](configure-real-time-protection-microsoft-defender-antivirus.md) 및 클라우드 [제공](enable-cloud-protection-microsoft-defender-antivirus.md) 보호를 사용하도록 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5288a-134">[Microsoft Defender Antivirus real-time protection](configure-real-time-protection-microsoft-defender-antivirus.md) and [cloud-delivered protection](enable-cloud-protection-microsoft-defender-antivirus.md) must be enabled</span></span> |

<span data-ttu-id="5288a-135">서비스를 사용하도록 설정한 후 서비스와 장치(끝점이라고도 하는) 간의 연결을 허용하도록 네트워크 또는 방화벽을 구성해야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5288a-135">After you have enabled the services, you might need to configure your network or firewall to allow the connections between the services and your devices (also referred to as endpoints).</span></span>  

- `.smartscreen.microsoft.com`
- `.smartscreen-prod.microsoft.com`

## <a name="review-network-protection-events-in-the-microsoft-defender-for-endpoint-security-center"></a><span data-ttu-id="5288a-136">Microsoft Defender for Endpoint 보안 센터에서 네트워크 보호 이벤트 검토</span><span class="sxs-lookup"><span data-stu-id="5288a-136">Review network protection events in the Microsoft Defender for Endpoint Security Center</span></span>

<span data-ttu-id="5288a-137">끝점용 Microsoft Defender는 이벤트에 대한 자세한 보고를 제공하며 경고 조사 시나리오의 일부로 [차단합니다.](investigate-alerts.md)</span><span class="sxs-lookup"><span data-stu-id="5288a-137">Microsoft Defender for Endpoint provides detailed reporting into events and blocks as part of its [alert investigation scenarios](investigate-alerts.md).</span></span>

<span data-ttu-id="5288a-138">고급 헌팅을 사용하여 Microsoft Defender에서 끝점 데이터를 [쿼리할 수 있습니다.](advanced-hunting-overview.md)</span><span class="sxs-lookup"><span data-stu-id="5288a-138">You can query Microsoft Defender for Endpoint data by using [advanced hunting](advanced-hunting-overview.md).</span></span> <span data-ttu-id="5288a-139">감사 모드를 사용하는 [](audit-windows-defender.md)경우 고급 헌팅을 사용하여 네트워크 보호 설정이 사용하도록 설정된 경우 환경에 어떤 영향을 주는지 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5288a-139">If you're using [audit mode](audit-windows-defender.md), you can use advanced hunting to see how network protection settings would affect your environment if they were enabled.</span></span>

<span data-ttu-id="5288a-140">다음은 예제 쿼리입니다.</span><span class="sxs-lookup"><span data-stu-id="5288a-140">Here is an example query</span></span>

```kusto
DeviceEvents
| where ActionType in ('ExploitGuardNetworkProtectionAudited','ExploitGuardNetworkProtectionBlocked')
```

## <a name="review-network-protection-events-in-windows-event-viewer"></a><span data-ttu-id="5288a-141">이벤트 뷰어에서 Windows 이벤트 검토</span><span class="sxs-lookup"><span data-stu-id="5288a-141">Review network protection events in Windows Event Viewer</span></span>

<span data-ttu-id="5288a-142">Windows 로그를 검토하여 네트워크 보호가 악성 IP 또는 도메인에 대한 액세스를 차단(또는 감사)할 때 생성되는 이벤트를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5288a-142">You can review the Windows event log to see events that are created when network protection blocks (or audits) access to a malicious IP or domain:</span></span>

1. <span data-ttu-id="5288a-143">[XML을 직접 복사합니다.](event-views.md)</span><span class="sxs-lookup"><span data-stu-id="5288a-143">[Copy the XML directly](event-views.md).</span></span>

2. <span data-ttu-id="5288a-144">**확인** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="5288a-144">Select **OK**.</span></span>

<span data-ttu-id="5288a-145">이 절차에서는 네트워크 보호와 관련된 다음 이벤트만 표시하기 위해 필터를 지정하는 사용자 지정 보기를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="5288a-145">This procedure creates a custom view that filters to only show the following events related to network protection:</span></span>

| <span data-ttu-id="5288a-146">이벤트 ID</span><span class="sxs-lookup"><span data-stu-id="5288a-146">Event ID</span></span> | <span data-ttu-id="5288a-147">설명</span><span class="sxs-lookup"><span data-stu-id="5288a-147">Description</span></span> |
|:---|:---|
| <span data-ttu-id="5288a-148">5007</span><span class="sxs-lookup"><span data-stu-id="5288a-148">5007</span></span> | <span data-ttu-id="5288a-149">설정이 변경될 때의 이벤트</span><span class="sxs-lookup"><span data-stu-id="5288a-149">Event when settings are changed</span></span> |
| <span data-ttu-id="5288a-150">1125</span><span class="sxs-lookup"><span data-stu-id="5288a-150">1125</span></span> | <span data-ttu-id="5288a-151">감사 모드에서 네트워크 보호가 발생 하는 경우 이벤트</span><span class="sxs-lookup"><span data-stu-id="5288a-151">Event when network protection fires in audit mode</span></span> |
| <span data-ttu-id="5288a-152">1126</span><span class="sxs-lookup"><span data-stu-id="5288a-152">1126</span></span> | <span data-ttu-id="5288a-153">차단 모드에서 네트워크 보호가 발생하면 이벤트</span><span class="sxs-lookup"><span data-stu-id="5288a-153">Event when network protection fires in block mode</span></span> |

## <a name="considerations-for-windows-virtual-desktop-running-windows-10-enterprise-multi-session"></a><span data-ttu-id="5288a-154">다중 세션을 Windows 가상 데스크톱에 Windows 10 Enterprise 고려 사항</span><span class="sxs-lookup"><span data-stu-id="5288a-154">Considerations for Windows virtual desktop running Windows 10 Enterprise Multi-Session</span></span>

<span data-ttu-id="5288a-155">다중 사용자 특성으로 인해 Windows 10 Enterprise 다음에 유의해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5288a-155">Due to the multi-user nature of Windows 10 Enterprise, keep the following points in mind:</span></span>

1. <span data-ttu-id="5288a-156">네트워크 보호는 장치 전체 기능으로, 특정 사용자 세션을 대상으로 할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="5288a-156">Network protection is a device-wide feature and cannot be targeted to specific user sessions.</span></span>

2. <span data-ttu-id="5288a-157">웹 콘텐츠 필터링 정책도 장치 전체에 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="5288a-157">Web content filtering policies are also device wide.</span></span>

3. <span data-ttu-id="5288a-158">사용자 그룹을 구분해야 하는 경우 가상 데스크톱 호스트 풀과 할당을 Windows 만드는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="5288a-158">If you need to differentiate between user groups, consider creating separate Windows Virtual Desktop host pools and assignments.</span></span>

4. <span data-ttu-id="5288a-159">감사 모드에서 네트워크 보호를 테스트하여 롤아웃하기 전에 해당 동작을 평가합니다.</span><span class="sxs-lookup"><span data-stu-id="5288a-159">Test network protection in audit mode to assess its behavior before rolling out.</span></span> 

5. <span data-ttu-id="5288a-160">사용자 수 또는 다중 사용자 세션 수가 많은 경우 배포의 크기 조정을 고려합니다.</span><span class="sxs-lookup"><span data-stu-id="5288a-160">Consider resizing your deployment if you have a large number of users or a large number of multi-user sessions.</span></span>

### <a name="alternative-option-for-network-protection"></a><span data-ttu-id="5288a-161">네트워크 보호를 위한 대체 옵션</span><span class="sxs-lookup"><span data-stu-id="5288a-161">Alternative option for network protection</span></span>

<span data-ttu-id="5288a-162">Azure의 Windows 데스크톱에서 사용되는 Windows 10 Enterprise 세션 1909 이상의 경우 다음 방법을 사용하여 Microsoft Edge 네트워크 보호를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5288a-162">For Windows 10 Enterprise Multi-Session 1909 and up, used in Windows Virtual Desktop on Azure, network protection for Microsoft Edge can be enabled using the following method:</span></span>

1. <span data-ttu-id="5288a-163">네트워크 [보호 켜기 및](enable-network-protection.md) 지침에 따라 정책을 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="5288a-163">Use [Turn on network protection](enable-network-protection.md) and follow the instructions to apply your policy.</span></span>

2. <span data-ttu-id="5288a-164">다음 PowerShell 명령을 실행합니다. `Set-MpPreference -AllowNetworkProtectionOnWinServer 1`</span><span class="sxs-lookup"><span data-stu-id="5288a-164">Execute the following PowerShell command: `Set-MpPreference -AllowNetworkProtectionOnWinServer 1`</span></span>

## <a name="network-protection-troubleshooting"></a><span data-ttu-id="5288a-165">네트워크 보호 문제 해결</span><span class="sxs-lookup"><span data-stu-id="5288a-165">Network protection troubleshooting</span></span>

<span data-ttu-id="5288a-166">네트워크 보호가 실행되는 환경으로 인해 Microsoft는 운영 체제 프록시 설정을 검색하지 못할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5288a-166">Due to the environment where Network Protection runs, Microsoft might not be able to detect operating system proxy settings.</span></span> <span data-ttu-id="5288a-167">경우에 따라 네트워크 보호 클라이언트가 클라우드 서비스에 연결하지 못할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5288a-167">In some cases, network protection clients are unable to reach Cloud Service.</span></span> <span data-ttu-id="5288a-168">연결 문제를 해결하려면 E5 라이선스가 있는 고객은 다음 Defender 레지스트리 키 중 하나를 구성해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5288a-168">To resolve the connectivity problem, customers with E5 licenses should configure one of the following Defender registry keys:</span></span>

```console
reg add "HKLM\Software\Microsoft\Windows Defender" /v ProxyServer /d "<proxy IP address: Port>" /f
reg add "HKLM\Software\Microsoft\Windows Defender" /v ProxyPacUrl /d "<Proxy PAC url>" /f

```

## <a name="related-articles"></a><span data-ttu-id="5288a-169">관련 문서</span><span class="sxs-lookup"><span data-stu-id="5288a-169">Related articles</span></span>

- <span data-ttu-id="5288a-170">[네트워크 보호 |](evaluate-network-protection.md) 기능의 작동 방식과 일반적으로 만들어지게 될 이벤트를 보여줄 수 있는 빠른 시나리오를 진행합니다.</span><span class="sxs-lookup"><span data-stu-id="5288a-170">[Evaluate network protection](evaluate-network-protection.md) | Undertake a quick scenario that demonstrates how the feature works, and what events would typically be created.</span></span>

- <span data-ttu-id="5288a-171">[네트워크 보호 기능](enable-network-protection.md) | 그룹 정책, PowerShell 또는 MDM CSP를 사용하여 네트워크에서 네트워크 보호를 사용하도록 설정하고 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5288a-171">[Enable network protection](enable-network-protection.md) | Use Group Policy, PowerShell, or MDM CSPs to enable and manage network protection in your network.</span></span>
