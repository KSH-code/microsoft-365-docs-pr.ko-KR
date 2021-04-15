---
title: 네트워크 보호 문제 해결
description: 끝점용 Microsoft Defender의 네트워크 보호 문제를 해결하기 위한 리소스 및 샘플 코드입니다.
keywords: 문제 해결, 오류, 수정, windows defender eg, asr, 규칙, hips, 문제 해결, 감사, 제외, 가극적, 손상된, 차단, 끝점용 Microsoft Defender, Microsoft Defender Advanced Threat Protection
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: Normal
audience: ITPro
author: dansimp
ms.author: dansimp
ms.reviewer: oogunrinde
manager: dansimp
ms.technology: mde
ms.topic: how-to
ms.openlocfilehash: 9efc42441c2cb30f35abf658071088f7f7bbaf00
ms.sourcegitcommit: 223a36a86753fe9cebee96f05ab4c9a144133677
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2021
ms.locfileid: "51760101"
---
# <a name="troubleshoot-network-protection"></a><span data-ttu-id="3eab0-104">네트워크 보호 문제 해결</span><span class="sxs-lookup"><span data-stu-id="3eab0-104">Troubleshoot network protection</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="3eab0-105">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="3eab0-105">**Applies to:**</span></span>
- <span data-ttu-id="3eab0-106">[엔드포인트용 Microsoft Defender](https://go.microsoft.com/fwlink/p/?linkid=2154037) </span><span class="sxs-lookup"><span data-stu-id="3eab0-106">[Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)</span></span>
- [<span data-ttu-id="3eab0-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="3eab0-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> [!TIP]
> <span data-ttu-id="3eab0-108">Endpoint용 Defender를 경험하고 싶나요?</span><span class="sxs-lookup"><span data-stu-id="3eab0-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="3eab0-109">무료 평가판에 등록합니다.</span><span class="sxs-lookup"><span data-stu-id="3eab0-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-pullalerts-abovefoldlink) 


<span data-ttu-id="3eab0-110">네트워크 [보호를 사용하는 경우](network-protection.md) 다음과 같은 문제가 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3eab0-110">When you use [Network protection](network-protection.md) you may encounter issues, such as:</span></span>

- <span data-ttu-id="3eab0-111">네트워크 보호는 안전한 웹 사이트(가음성)를 차단합니다.</span><span class="sxs-lookup"><span data-stu-id="3eab0-111">Network protection blocks a website that is safe (false positive)</span></span>
- <span data-ttu-id="3eab0-112">네트워크 보호가 의심스나 알려진 악성 웹 사이트(거짓 부정)를 차단하지 못합니다.</span><span class="sxs-lookup"><span data-stu-id="3eab0-112">Network protection fails to block a suspicious or known malicious website (false negative)</span></span>

<span data-ttu-id="3eab0-113">이러한 문제를 해결하는 네 가지 단계가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3eab0-113">There are four steps to troubleshooting these problems:</span></span>

1. <span data-ttu-id="3eab0-114">선행 준비 확인</span><span class="sxs-lookup"><span data-stu-id="3eab0-114">Confirm prerequisites</span></span>
2. <span data-ttu-id="3eab0-115">감사 모드를 사용하여 규칙 테스트</span><span class="sxs-lookup"><span data-stu-id="3eab0-115">Use audit mode to test the rule</span></span>
3. <span data-ttu-id="3eab0-116">지정된 규칙에 대한 제외 추가(가음성의 경우)</span><span class="sxs-lookup"><span data-stu-id="3eab0-116">Add exclusions for the specified rule (for false positives)</span></span>
4. <span data-ttu-id="3eab0-117">지원 로그 제출</span><span class="sxs-lookup"><span data-stu-id="3eab0-117">Submit support logs</span></span>

## <a name="confirm-prerequisites"></a><span data-ttu-id="3eab0-118">선행 준비 확인</span><span class="sxs-lookup"><span data-stu-id="3eab0-118">Confirm prerequisites</span></span>

<span data-ttu-id="3eab0-119">네트워크 보호는 다음 조건이 있는 디바이스에서만 작동합니다.</span><span class="sxs-lookup"><span data-stu-id="3eab0-119">Network protection will only work on devices with the following conditions:</span></span>

>[!div class="checklist"]
> - <span data-ttu-id="3eab0-120">끝점에서 Windows 10 Pro 또는 Enterprise 버전, 버전 1709 이상을 실행하고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3eab0-120">Endpoints are running Windows 10 Pro or Enterprise edition, version 1709 or higher.</span></span>
> - <span data-ttu-id="3eab0-121">끝점에서 Microsoft Defender 바이러스 백신을 단독 바이러스 백신 보호 앱으로 사용하고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3eab0-121">Endpoints are using Microsoft Defender Antivirus as the sole antivirus protection app.</span></span> <span data-ttu-id="3eab0-122">[Microsoft가 아닌 바이러스 백신](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-antivirus-compatibility)솔루션을 사용할 때 발생하는 문제를 참조합니다.</span><span class="sxs-lookup"><span data-stu-id="3eab0-122">[See what happens when you are using a non-Microsoft antivirus solution](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-antivirus-compatibility).</span></span>
> - <span data-ttu-id="3eab0-123">[실시간 보호가](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/configure-real-time-protection-microsoft-defender-antivirus) 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="3eab0-123">[Real-time protection](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/configure-real-time-protection-microsoft-defender-antivirus) is enabled.</span></span>
> - <span data-ttu-id="3eab0-124">[클라우드 제공 보호를](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/enable-cloud-protection-microsoft-defender-antivirus) 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3eab0-124">[Cloud-delivered protection](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/enable-cloud-protection-microsoft-defender-antivirus) is enabled.</span></span>
> - <span data-ttu-id="3eab0-125">감사 모드를 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="3eab0-125">Audit mode is not enabled.</span></span> <span data-ttu-id="3eab0-126">그룹 [정책을 사용하여](enable-network-protection.md#group-policy) 규칙을 사용 안 하게 **설정(값:** **0)합니다.**</span><span class="sxs-lookup"><span data-stu-id="3eab0-126">Use [Group Policy](enable-network-protection.md#group-policy) to set the rule to **Disabled** (value: **0**).</span></span>

## <a name="use-audit-mode"></a><span data-ttu-id="3eab0-127">감사 모드 사용</span><span class="sxs-lookup"><span data-stu-id="3eab0-127">Use audit mode</span></span>

<span data-ttu-id="3eab0-128">감사 모드에서 네트워크 보호를 사용하도록 설정한 다음 기능을 데모하기 위해 만든 웹 사이트를 방문할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3eab0-128">You can enable network protection in audit mode and then visit a website that we've created to demo the feature.</span></span> <span data-ttu-id="3eab0-129">모든 웹 사이트 연결은 네트워크 보호에서 허용되지만 네트워크 보호를 사용하도록 설정한 경우 차단될 모든 연결을 나타내는 이벤트가 기록됩니다.</span><span class="sxs-lookup"><span data-stu-id="3eab0-129">All website connections will be allowed by network protection but an event will be logged to indicate any connection that would have been blocked if network protection was enabled.</span></span>

1. <span data-ttu-id="3eab0-130">네트워크 보호를 감사 **모드로 설정**</span><span class="sxs-lookup"><span data-stu-id="3eab0-130">Set network protection to **Audit mode**.</span></span>

   ```PowerShell
   Set-MpPreference -EnableNetworkProtection AuditMode
   ```

2. <span data-ttu-id="3eab0-131">문제를 일으키는 연결 활동을 수행합니다(예: 사이트를 방문하거나 차단하려는 IP 주소에 연결하려고 시도).</span><span class="sxs-lookup"><span data-stu-id="3eab0-131">Perform the connection activity that is causing an issue (for example, attempt to visit the site, or connect to the IP address you do or don't want to block).</span></span>

3. <span data-ttu-id="3eab0-132">[네트워크 보호 이벤트](network-protection.md#review-network-protection-events-in-windows-event-viewer) 로그를 검토하여 기능이 사용으로 설정된 경우 연결을 차단할 수 없는지 **확인합니다.**</span><span class="sxs-lookup"><span data-stu-id="3eab0-132">[Review the network protection event logs](network-protection.md#review-network-protection-events-in-windows-event-viewer) to see if the feature would have blocked the connection if it had been set to **Enabled**.</span></span>
   
   <span data-ttu-id="3eab0-133">네트워크 보호가 차단해야 하는 연결을 차단하지 않는 경우 기능을 사용하도록 설정하십시오.</span><span class="sxs-lookup"><span data-stu-id="3eab0-133">If network protection is not blocking a connection that you are expecting it should block, enable the feature.</span></span>

   ```PowerShell
   Set-MpPreference -EnableNetworkProtection Enabled
   ```

## <a name="report-a-false-positive-or-false-negative"></a><span data-ttu-id="3eab0-134">가짓 긍정 또는 거짓 부정 보고</span><span class="sxs-lookup"><span data-stu-id="3eab0-134">Report a false positive or false negative</span></span>

<span data-ttu-id="3eab0-135">데모 사이트 및 감사 모드로 기능을 테스트했지만 네트워크 보호가 미리 구성된 시나리오에서 작동하지만 특정 연결에 대해 예상대로 작동하지 않는 경우 [Windows Defender 보안](https://www.microsoft.com/wdsi/filesubmission) 인텔리전스 웹 기반 제출 양식을 사용하여 네트워크 보호에 대한 거짓 부정 또는 가양성 보고를 합니다.</span><span class="sxs-lookup"><span data-stu-id="3eab0-135">If you've tested the feature with the demo site and with audit mode, and network protection is working on pre-configured scenarios, but is not working as expected for a specific connection, use the [Windows Defender Security Intelligence web-based submission form](https://www.microsoft.com/wdsi/filesubmission) to report a false negative or false positive for network protection.</span></span> <span data-ttu-id="3eab0-136">E5 구독을 사용하면 연결된 경고에 대한 링크를 [제공할 수도 있습니다.](alerts-queue.md)</span><span class="sxs-lookup"><span data-stu-id="3eab0-136">With an E5 subscription, you can also [provide a link to any associated alert](alerts-queue.md).</span></span>

<span data-ttu-id="3eab0-137">끝점에 대한 [Microsoft Defender의 가짓 긍정/부정 주소를 참조하세요.](defender-endpoint-false-positives-negatives.md)</span><span class="sxs-lookup"><span data-stu-id="3eab0-137">See [Address false positives/negatives in Microsoft Defender for Endpoint](defender-endpoint-false-positives-negatives.md).</span></span>

## <a name="exclude-website-from-network-protection-scope"></a><span data-ttu-id="3eab0-138">네트워크 보호 범위에서 웹 사이트 제외</span><span class="sxs-lookup"><span data-stu-id="3eab0-138">Exclude website from network protection scope</span></span>

<span data-ttu-id="3eab0-139">차단되는 웹 사이트(가음성)를 허용하기 위해 신뢰할 수 있는 사이트 목록에 해당 URL을 [추가합니다.](https://blogs.msdn.microsoft.com/asiatech/2014/08/19/how-to-add-web-sites-to-trusted-sites-via-gpo-from-dc-installed-ie10-or-higher-ie-version/)</span><span class="sxs-lookup"><span data-stu-id="3eab0-139">To allow the website that is being blocked (false positive), add its URL to the [list of trusted sites](https://blogs.msdn.microsoft.com/asiatech/2014/08/19/how-to-add-web-sites-to-trusted-sites-via-gpo-from-dc-installed-ie10-or-higher-ie-version/).</span></span> <span data-ttu-id="3eab0-140">이 목록의 웹 리소스는 네트워크 보호 검사를 무시합니다.</span><span class="sxs-lookup"><span data-stu-id="3eab0-140">Web resources from this list bypass the network protection check.</span></span>

## <a name="collect-diagnostic-data-for-file-submissions"></a><span data-ttu-id="3eab0-141">파일 전송에 대한 진단 데이터 수집</span><span class="sxs-lookup"><span data-stu-id="3eab0-141">Collect diagnostic data for file submissions</span></span>

<span data-ttu-id="3eab0-142">네트워크 보호 관련 문제를 보고하는 경우 Microsoft 지원 및 엔지니어링 팀에서 문제를 해결하는 데 사용할 수 있는 진단 데이터를 수집하고 제출해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3eab0-142">When you report a problem with network protection, you are asked to collect and submit diagnostic data that can be used by Microsoft support and engineering teams to help troubleshoot issues.</span></span>

1. <span data-ttu-id="3eab0-143">승강된 명령 프롬프트를 열고 Windows Defender 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="3eab0-143">Open an elevated command prompt and change to the Windows Defender directory:</span></span>

   ```console
   cd c:\program files\windows defender
   ```

2. <span data-ttu-id="3eab0-144">다음 명령을 실행하여 진단 로그를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="3eab0-144">Run this command to generate the diagnostic logs:</span></span>

   ```console
   mpcmdrun -getfiles
   ```

3. <span data-ttu-id="3eab0-145">파일을 제출 양식에 첨부합니다.</span><span class="sxs-lookup"><span data-stu-id="3eab0-145">Attach the file to the submission form.</span></span> <span data-ttu-id="3eab0-146">기본적으로 진단 로그는 에 `C:\ProgramData\Microsoft\Windows Defender\Support\MpSupportFiles.cab` 저장됩니다.</span><span class="sxs-lookup"><span data-stu-id="3eab0-146">By default, diagnostic logs are saved at `C:\ProgramData\Microsoft\Windows Defender\Support\MpSupportFiles.cab`.</span></span> 

## <a name="resolve-connectivity-issues-with-network-protection-for-e5-customers"></a><span data-ttu-id="3eab0-147">네트워크 보호 관련 연결 문제 해결(E5 고객용)</span><span class="sxs-lookup"><span data-stu-id="3eab0-147">Resolve connectivity issues with network protection (for E5 customers)</span></span>

<span data-ttu-id="3eab0-148">네트워크 보호가 실행되는 환경으로 인해 Microsoft는 운영 체제 프록시 설정을 볼 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="3eab0-148">Due to the environment where network protection runs, Microsoft is unable to see your operating system proxy settings.</span></span> <span data-ttu-id="3eab0-149">경우에 따라 네트워크 보호 클라이언트가 클라우드 서비스에 연결하지 못할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3eab0-149">In some cases, network protection clients are unable to reach the cloud service.</span></span> <span data-ttu-id="3eab0-150">네트워크 보호와의 연결 문제를 해결하려면 네트워크 보호에서 프록시 구성을 인식하도록 다음 레지스트리 키 중 하나를 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="3eab0-150">To resolve connectivity issues with network protection, configure one of the following registry keys so that network protection becomes aware of the proxy configuration:</span></span>

```powershell
reg add "HKLM\Software\Microsoft\Windows Defender" /v ProxyServer /d "<proxy IP address: Port>" /f
```

<span data-ttu-id="3eab0-151">---OR---</span><span class="sxs-lookup"><span data-stu-id="3eab0-151">---OR---</span></span>


```powershell
reg add "HKLM\Software\Microsoft\Windows Defender" /v ProxyPacUrl /d "<Proxy PAC url>" /f
```

<span data-ttu-id="3eab0-152">PowerShell, Microsoft Endpoint Manager 또는 그룹 정책을 사용하여 레지스트리 키를 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3eab0-152">You can configure the registry key by using PowerShell, Microsoft Endpoint Manager, or Group Policy.</span></span> <span data-ttu-id="3eab0-153">다음은 도움이 되는 몇 가지 리소스입니다.</span><span class="sxs-lookup"><span data-stu-id="3eab0-153">Here are some resources to help:</span></span>
- [<span data-ttu-id="3eab0-154">레지스트리 키 작업</span><span class="sxs-lookup"><span data-stu-id="3eab0-154">Working with Registry Keys</span></span>](/powershell/scripting/samples/working-with-registry-keys)
- [<span data-ttu-id="3eab0-155">Endpoint Protection에 대한 사용자 지정 클라이언트 설정 구성</span><span class="sxs-lookup"><span data-stu-id="3eab0-155">Configure custom client settings for Endpoint Protection</span></span>](/mem/configmgr/protect/deploy-use/endpoint-protection-configure-client)
- [<span data-ttu-id="3eab0-156">그룹 정책 설정을 사용하여 끝점 보호 관리</span><span class="sxs-lookup"><span data-stu-id="3eab0-156">Use Group Policy settings to manage Endpoint Protection</span></span>](/mem/configmgr/protect/deploy-use/endpoint-protection-group-policies)

## <a name="see-also"></a><span data-ttu-id="3eab0-157">참고 항목</span><span class="sxs-lookup"><span data-stu-id="3eab0-157">See also</span></span>

- [<span data-ttu-id="3eab0-158">네트워크 보호</span><span class="sxs-lookup"><span data-stu-id="3eab0-158">Network protection</span></span>](network-protection.md)
- [<span data-ttu-id="3eab0-159">네트워크 보호 평가</span><span class="sxs-lookup"><span data-stu-id="3eab0-159">Evaluate network protection</span></span>](evaluate-network-protection.md)
- [<span data-ttu-id="3eab0-160">네트워크 보호 사용</span><span class="sxs-lookup"><span data-stu-id="3eab0-160">Enable network protection</span></span>](enable-network-protection.md)
- [<span data-ttu-id="3eab0-161">끝점용 Defender에서 가짓 긍정/음수 해결</span><span class="sxs-lookup"><span data-stu-id="3eab0-161">Address false positives/negatives in Defender for Endpoint</span></span>](defender-endpoint-false-positives-negatives.md)
