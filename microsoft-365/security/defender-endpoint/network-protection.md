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
ms.date: 03/08/2021
ms.topic: how-to
ms.openlocfilehash: 2ef3fbeec65be512dfe07f1d533df4d8e9b31532
ms.sourcegitcommit: 437bdbf3f99610869811e80432a59b5f244f7a87
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2021
ms.locfileid: "51644503"
---
# <a name="protect-your-network"></a><span data-ttu-id="371d5-104">네트워크 보호</span><span class="sxs-lookup"><span data-stu-id="371d5-104">Protect your network</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="371d5-105">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="371d5-105">**Applies to:**</span></span>
- <span data-ttu-id="371d5-106">[엔드포인트용 Microsoft Defender](https://go.microsoft.com/fwlink/p/?linkid=2154037) </span><span class="sxs-lookup"><span data-stu-id="371d5-106">[Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)</span></span>
- [<span data-ttu-id="371d5-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="371d5-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="371d5-108">끝점용 Microsoft Defender를 경험하고 싶나요?</span><span class="sxs-lookup"><span data-stu-id="371d5-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="371d5-109">무료 평가판에 등록합니다.</span><span class="sxs-lookup"><span data-stu-id="371d5-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

<span data-ttu-id="371d5-110">네트워크 보호는 인터넷 기반 이벤트에서 장치의 공격 표면을 줄이는 데 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="371d5-110">Network protection helps reduce the attack surface of your devices from Internet-based events.</span></span> <span data-ttu-id="371d5-111">이를 통해 직원이 응용 프로그램을 사용하여 인터넷에서 피싱 사기, 악용 및 기타 악성 콘텐츠를 호스팅할 수 있는 위험한 도메인에 액세스할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="371d5-111">It prevents employees from using any application to access dangerous domains that might host phishing scams, exploits, and other malicious content on the Internet.</span></span> <span data-ttu-id="371d5-112">네트워크 보호는 Microsoft [Defender SmartScreen의](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-smartscreen/microsoft-defender-smartscreen-overview) 범위를 확장하여 신뢰도가 낮은 원본(도메인 또는 호스트 이름 기반)에 연결하려고 하는 모든 아웃바운드 HTTP 트래픽을 차단합니다.</span><span class="sxs-lookup"><span data-stu-id="371d5-112">Network protection expands the scope of [Microsoft Defender SmartScreen](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-smartscreen/microsoft-defender-smartscreen-overview) to block all outbound HTTP(s) traffic that attempts to connect to low-reputation sources (based on the domain or hostname).</span></span>

<span data-ttu-id="371d5-113">네트워크 보호는 Windows 10 버전 1709부터 Windows에서 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="371d5-113">Network protection is supported on Windows, beginning with Windows 10, version 1709.</span></span> 

<span data-ttu-id="371d5-114">네트워크 보호를 사용하도록 설정하는 방법에 대한 자세한 내용은 네트워크 보호 사용 [을 참조하세요.](enable-network-protection.md)</span><span class="sxs-lookup"><span data-stu-id="371d5-114">For more information about how to enable network protection, see [Enable network protection](enable-network-protection.md).</span></span> <span data-ttu-id="371d5-115">그룹 정책, PowerShell 또는 MDM CSP를 사용하여 네트워크에서 네트워크 보호를 사용하도록 설정하고 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="371d5-115">Use Group Policy, PowerShell, or MDM CSPs to enable and manage network protection in your network.</span></span>

> [!TIP]
> <span data-ttu-id="371d5-116">네트워크 보호가 작동하는 방법을 demo.wd.microsoft.com Microsoft [Defender](https://demo.wd.microsoft.com?ocid=cx-wddocs-testground) ATP 테스트그라운드 사이트를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="371d5-116">See the Microsoft Defender ATP testground site at [demo.wd.microsoft.com](https://demo.wd.microsoft.com?ocid=cx-wddocs-testground) to see how network protection works.</span></span>

<span data-ttu-id="371d5-117">네트워크 보호는 Exploit Protection 이벤트에 대한 자세한 보고를 제공하며 경고 조사 시나리오의 일부로 차단하는 [끝점용 Microsoft Defender와](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/microsoft-defender-advanced-threat-protection) [가장 잘 작동합니다.](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/investigate-alerts)</span><span class="sxs-lookup"><span data-stu-id="371d5-117">Network protection works best with [Microsoft Defender for Endpoint](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/microsoft-defender-advanced-threat-protection), which gives you detailed reporting into exploit protection events and blocks as part of [alert investigation scenarios](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/investigate-alerts).</span></span>

<span data-ttu-id="371d5-118">네트워크 보호가 연결을 차단하면 알림 센터에서 알림이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="371d5-118">When network protection blocks a connection, a notification is displayed from the Action Center.</span></span> <span data-ttu-id="371d5-119">보안 운영 팀은 조직의 [세부](customize-attack-surface-reduction.md#customize-the-notification) 정보 및 연락처 정보로 알림을 사용자 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="371d5-119">Your security operations team can [customize the notification](customize-attack-surface-reduction.md#customize-the-notification) with your organization's details and contact information.</span></span> <span data-ttu-id="371d5-120">또한 모니터링할 특정 기술에 맞게 개별 공격 표면 감소 규칙을 사용하도록 설정하고 사용자 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="371d5-120">In addition, individual attack surface reduction rules can be enabled and customized to suit certain techniques to monitor.</span></span>

<span data-ttu-id="371d5-121">감사 모드를 [사용하여](audit-windows-defender.md) 네트워크 보호가 사용하도록 설정된 경우 조직에 어떤 영향을 미치는지 평가할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="371d5-121">You can also use [audit mode](audit-windows-defender.md) to evaluate how network protection would impact your organization if it were enabled.</span></span>

## <a name="requirements"></a><span data-ttu-id="371d5-122">요구 사항</span><span class="sxs-lookup"><span data-stu-id="371d5-122">Requirements</span></span>

<span data-ttu-id="371d5-123">네트워크 보호에는 Windows 10 Pro 또는 Enterprise 및 Microsoft Defender 바이러스 백신 실시간 보호가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="371d5-123">Network protection requires Windows 10 Pro or Enterprise, and Microsoft Defender Antivirus real-time protection.</span></span>

| <span data-ttu-id="371d5-124">Windows 버전</span><span class="sxs-lookup"><span data-stu-id="371d5-124">Windows version</span></span> | <span data-ttu-id="371d5-125">Microsoft Defender 바이러스 백신</span><span class="sxs-lookup"><span data-stu-id="371d5-125">Microsoft Defender Antivirus</span></span> |
|:---|:---|
| <span data-ttu-id="371d5-126">Windows 10 버전 1709 이상</span><span class="sxs-lookup"><span data-stu-id="371d5-126">Windows 10 version 1709 or later</span></span> <p><span data-ttu-id="371d5-127">Windows Server 1803 이상</span><span class="sxs-lookup"><span data-stu-id="371d5-127">Windows Server 1803 or later</span></span> | <span data-ttu-id="371d5-128">[Microsoft Defender 바이러스 백신 실시간 보호](https://docs.microsoft.com/windows/security/threat-protection/configure-real-time-protection-microsoft-defender-antivirus.md) 및 클라우드 [제공](https://docs.microsoft.com/windows/security/threat-protection/enable-cloud-protection-microsoft-defender-antivirus.md) 보호를 사용하도록 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="371d5-128">[Microsoft Defender Antivirus real-time protection](https://docs.microsoft.com/windows/security/threat-protection/configure-real-time-protection-microsoft-defender-antivirus.md) and [cloud-delivered protection](https://docs.microsoft.com/windows/security/threat-protection/enable-cloud-protection-microsoft-defender-antivirus.md) must be enabled</span></span> |

<span data-ttu-id="371d5-129">서비스를 사용하도록 설정한 후 서비스와 장치(끝점이라고도 하는) 간의 연결을 허용하도록 네트워크 또는 방화벽을 구성해야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="371d5-129">After you have enabled the services, you might need to configure your network or firewall to allow the connections between the services and your devices (also referred to as endpoints).</span></span>  

- <span data-ttu-id="371d5-130">.smartscreen.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="371d5-130">.smartscreen.microsoft.com</span></span>
- <span data-ttu-id="371d5-131">.smartscreen-prod.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="371d5-131">.smartscreen-prod.microsoft.com</span></span>

## <a name="review-network-protection-events-in-the-microsoft-defender-for-endpoint-security-center"></a><span data-ttu-id="371d5-132">Microsoft Defender for Endpoint 보안 센터에서 네트워크 보호 이벤트 검토</span><span class="sxs-lookup"><span data-stu-id="371d5-132">Review network protection events in the Microsoft Defender for Endpoint Security Center</span></span>

<span data-ttu-id="371d5-133">끝점용 Microsoft Defender는 이벤트에 대한 자세한 보고를 제공하며 경고 조사 시나리오의 일부로 [차단합니다.](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/investigate-alerts)</span><span class="sxs-lookup"><span data-stu-id="371d5-133">Microsoft Defender for Endpoint provides detailed reporting into events and blocks as part of its [alert investigation scenarios](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/investigate-alerts).</span></span>

<span data-ttu-id="371d5-134">고급 헌팅을 사용하여 Microsoft Defender에서 끝점 데이터를 [쿼리할 수 있습니다.](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-windows-defender-advanced-threat-protection)</span><span class="sxs-lookup"><span data-stu-id="371d5-134">You can query Microsoft Defender for Endpoint data by using [Advanced hunting](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-windows-defender-advanced-threat-protection).</span></span> <span data-ttu-id="371d5-135">감사 모드를 사용하는 [](audit-windows-defender.md)경우 고급 헌팅을 사용하여 네트워크 보호 설정이 사용하도록 설정된 경우 환경에 어떤 영향을 주는지 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="371d5-135">If you're using [audit mode](audit-windows-defender.md), you can use advanced hunting to see how network protection settings would affect your environment if they were enabled.</span></span>

<span data-ttu-id="371d5-136">다음은 예제 쿼리입니다.</span><span class="sxs-lookup"><span data-stu-id="371d5-136">Here is an example query</span></span>

```kusto
DeviceEvents
| where ActionType in ('ExploitGuardNetworkProtectionAudited','ExploitGuardNetworkProtectionBlocked')
```

## <a name="review-network-protection-events-in-windows-event-viewer"></a><span data-ttu-id="371d5-137">Windows 이벤트 뷰어에서 네트워크 보호 이벤트 검토</span><span class="sxs-lookup"><span data-stu-id="371d5-137">Review network protection events in Windows Event Viewer</span></span>

<span data-ttu-id="371d5-138">Windows 이벤트 로그를 검토하여 네트워크 보호가 악성 IP 또는 도메인에 대한 액세스를 차단(또는 감사)할 때 생성되는 이벤트를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="371d5-138">You can review the Windows event log to see events that are created when network protection blocks (or audits) access to a malicious IP or domain:</span></span>

1. <span data-ttu-id="371d5-139">[XML을 직접 복사합니다.](event-views.md)</span><span class="sxs-lookup"><span data-stu-id="371d5-139">[Copy the XML directly](event-views.md).</span></span>

2. <span data-ttu-id="371d5-140">**확인** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="371d5-140">Select **OK**.</span></span>

<span data-ttu-id="371d5-141">이 절차에서는 네트워크 보호와 관련된 다음 이벤트만 표시하기 위해 필터를 지정하는 사용자 지정 보기를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="371d5-141">This procedure creates a custom view that filters to only show the following events related to network protection:</span></span>

| <span data-ttu-id="371d5-142">이벤트 ID</span><span class="sxs-lookup"><span data-stu-id="371d5-142">Event ID</span></span> | <span data-ttu-id="371d5-143">설명</span><span class="sxs-lookup"><span data-stu-id="371d5-143">Description</span></span> |
|:---|:---|
| <span data-ttu-id="371d5-144">5007</span><span class="sxs-lookup"><span data-stu-id="371d5-144">5007</span></span> | <span data-ttu-id="371d5-145">설정이 변경될 때의 이벤트</span><span class="sxs-lookup"><span data-stu-id="371d5-145">Event when settings are changed</span></span> |
| <span data-ttu-id="371d5-146">1125</span><span class="sxs-lookup"><span data-stu-id="371d5-146">1125</span></span> | <span data-ttu-id="371d5-147">감사 모드에서 네트워크 보호가 발생 하는 경우 이벤트</span><span class="sxs-lookup"><span data-stu-id="371d5-147">Event when network protection fires in audit mode</span></span> |
| <span data-ttu-id="371d5-148">1126</span><span class="sxs-lookup"><span data-stu-id="371d5-148">1126</span></span> | <span data-ttu-id="371d5-149">차단 모드에서 네트워크 보호가 발생하면 이벤트</span><span class="sxs-lookup"><span data-stu-id="371d5-149">Event when network protection fires in block mode</span></span> |

## <a name="network-protection-troubleshooting"></a><span data-ttu-id="371d5-150">네트워크 보호 문제 해결</span><span class="sxs-lookup"><span data-stu-id="371d5-150">Network protection troubleshooting</span></span>

<span data-ttu-id="371d5-151">네트워크 보호가 실행되는 환경으로 인해 Microsoft는 운영 체제 프록시 설정을 검색하지 못할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="371d5-151">Due to the environment where Network Protection runs, Microsoft might not be able to detect operating system proxy settings.</span></span> <span data-ttu-id="371d5-152">경우에 따라 네트워크 보호 클라이언트가 클라우드 서비스에 연결하지 못할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="371d5-152">In some cases, Network Protection clients are unable to reach Cloud Service.</span></span> <span data-ttu-id="371d5-153">연결 문제를 해결하려면 E5 라이선스가 있는 고객은 다음 Defender 레지스트리 키 중 하나를 구성해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="371d5-153">To resolve the connectivity problem, customers with E5 licenses should configure one of the following Defender registry keys:</span></span>

```console
reg add "HKLM\Software\Microsoft\Windows Defender" /v ProxyServer /d "<proxy IP address: Port>" /f
reg add "HKLM\Software\Microsoft\Windows Defender" /v ProxyPacUrl /d "<Proxy PAC url>" /f

```

## <a name="related-articles"></a><span data-ttu-id="371d5-154">관련 문서</span><span class="sxs-lookup"><span data-stu-id="371d5-154">Related articles</span></span>

- <span data-ttu-id="371d5-155">[네트워크 보호 |](evaluate-network-protection.md) 기능의 작동 방식과 일반적으로 만들어지게 될 이벤트를 보여줄 수 있는 빠른 시나리오를 진행합니다.</span><span class="sxs-lookup"><span data-stu-id="371d5-155">[Evaluate network protection](evaluate-network-protection.md) | Undertake a quick scenario that demonstrates how the feature works, and what events would typically be created.</span></span>

- <span data-ttu-id="371d5-156">[네트워크 보호 기능](enable-network-protection.md) | 그룹 정책, PowerShell 또는 MDM CSP를 사용하여 네트워크에서 네트워크 보호를 사용하도록 설정하고 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="371d5-156">[Enable network protection](enable-network-protection.md) | Use Group Policy, PowerShell, or MDM CSPs to enable and manage network protection in your network.</span></span>
