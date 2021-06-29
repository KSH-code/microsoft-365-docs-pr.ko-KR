---
title: 공격 표면 감소 규칙 사용자 지정
description: 개별적으로 감사, 차단 또는 비활성화 모드에서 규칙을 설정하고 공격 표면 감소 규칙에서 제외해야 하는 파일 및 폴더를 추가합니다.
keywords: 공격 표면 감소, hips, 호스트 침입 방지 시스템, 보호 규칙, 악용 방지, 악용, 감염 방지, 사용자 지정, 구성, 제외
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
localization_priority: Normal
audience: ITPro
author: denisebmsft
ms.author: deniseb
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.topic: article
ms.openlocfilehash: 6d2770dec270e2d1c1b9750387a0f07f82b357f9
ms.sourcegitcommit: cfd7644570831ceb7f57c61401df6a0001ef0a6a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/29/2021
ms.locfileid: "53177096"
---
# <a name="customize-attack-surface-reduction-rules"></a><span data-ttu-id="41a08-104">공격 표면 감소 규칙 사용자 지정</span><span class="sxs-lookup"><span data-stu-id="41a08-104">Customize attack surface reduction rules</span></span>

<span data-ttu-id="41a08-105">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="41a08-105">**Applies to:**</span></span>

- [<span data-ttu-id="41a08-106">엔드포인트용 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="41a08-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="41a08-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="41a08-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="41a08-108">Endpoint용 Defender를 경험하고 싶나요?</span><span class="sxs-lookup"><span data-stu-id="41a08-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="41a08-109">무료 평가판에 등록합니다.</span><span class="sxs-lookup"><span data-stu-id="41a08-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-assignaccess-abovefoldlink)

> [!IMPORTANT]
> <span data-ttu-id="41a08-110">일부 정보는 상용으로 출시되기 전에 실질적으로 수정될 수 있는 사전 릴리스된 제품과 관련이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="41a08-110">Some information relates to prereleased product which may be substantially modified before it's commercially released.</span></span> <span data-ttu-id="41a08-111">Microsoft는 여기에서 제공하는 정보와 관련하여 명시적이거나 묵시적인 어떠한 보증도 제공하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="41a08-111">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span></span>

<span data-ttu-id="41a08-112">[공격 표면 감소 규칙은](enable-attack-surface-reduction.md) 장치 또는 네트워크를 손상하기 위해 자주 남용되는 소프트웨어 동작을 방지하는 데 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="41a08-112">[Attack surface reduction rules](enable-attack-surface-reduction.md) help prevent software behaviors that are often abused to compromise your device or network.</span></span> <span data-ttu-id="41a08-113">예를 들어 공격자는 USB 드라이브에서 부호 없는 스크립트를 실행하려고 시도하거나, 문서의 매크로가 Office Win32 API를 직접 호출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="41a08-113">For example, an attacker might try to run an unsigned script off of a USB drive, or have a macro in an Office document make calls directly to the Win32 API.</span></span> <span data-ttu-id="41a08-114">공격 표면 감소 규칙은 이러한 종류의 위험한 동작을 제한하고 조직의 방어적 자세를 개선할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="41a08-114">Attack surface reduction rules can constrain these kinds of risky behaviors and improve your organization's defensive posture.</span></span>

<span data-ttu-id="41a08-115">파일 및 폴더를 제외하거나 [](#exclude-files-and-folders) 사용자 컴퓨터에 나타나는 알림 [](#customize-the-notification) 경고에 사용자 지정 텍스트를 추가하여 공격 표면 감소 규칙을 사용자 지정하는 방법을 학습합니다.</span><span class="sxs-lookup"><span data-stu-id="41a08-115">Learn how to customize attack surface reduction rules by [excluding files and folders](#exclude-files-and-folders) or [adding custom text to the notification](#customize-the-notification) alert that appears on a user's computer.</span></span>

<span data-ttu-id="41a08-116">다음 버전 및 버전의 디바이스를 실행하는 장치에 대해 공격 표면 감소 규칙을 설정할 수 Windows.</span><span class="sxs-lookup"><span data-stu-id="41a08-116">You can set attack surface reduction rules for devices running any of the following editions and versions of Windows:</span></span>

- <span data-ttu-id="41a08-117">Windows 10 Pro 버전 [1709](/windows/whats-new/whats-new-windows-10-version-1709) 이상</span><span class="sxs-lookup"><span data-stu-id="41a08-117">Windows 10 Pro, [version 1709](/windows/whats-new/whats-new-windows-10-version-1709) or later</span></span>
- <span data-ttu-id="41a08-118">Windows 10 Enterprise 버전 [1709](/windows/whats-new/whats-new-windows-10-version-1709) 이상</span><span class="sxs-lookup"><span data-stu-id="41a08-118">Windows 10 Enterprise, [version 1709](/windows/whats-new/whats-new-windows-10-version-1709) or later</span></span>
- <span data-ttu-id="41a08-119">Windows 서버, [버전 1803(반기 채널)](/windows-server/get-started/whats-new-in-windows-server-1803) 이상</span><span class="sxs-lookup"><span data-stu-id="41a08-119">Windows Server, [version 1803 (Semi-Annual Channel)](/windows-server/get-started/whats-new-in-windows-server-1803) or later</span></span>
- [<span data-ttu-id="41a08-120">Windows Server 2019</span><span class="sxs-lookup"><span data-stu-id="41a08-120">Windows Server 2019</span></span>](/windows-server/get-started-19/whats-new-19)

<span data-ttu-id="41a08-121">그룹 정책, PowerShell 및 MDM(모바일 장치 관리) CSP(구성 서비스 공급자)를 사용하여 이러한 설정을 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="41a08-121">You can use Group Policy, PowerShell, and Mobile Device Management (MDM) configuration service providers (CSP) to configure these settings.</span></span>

<span data-ttu-id="41a08-122">[지원되는](enable-attack-surface-reduction.md#requirements) 운영 체제 및 추가 요구 사항에 대한 자세한 내용은 "공격 표면 감소 규칙 사용" 문서의 요구 사항을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="41a08-122">See [Requirements](enable-attack-surface-reduction.md#requirements) in the "Enable attack surface reduction rules" article for information about supported operating systems and additional requirement information.</span></span>

## <a name="exclude-files-and-folders"></a><span data-ttu-id="41a08-123">파일 및 폴더 제외</span><span class="sxs-lookup"><span data-stu-id="41a08-123">Exclude files and folders</span></span>

<span data-ttu-id="41a08-124">파일 및 폴더가 공격 표면 축소 규칙에 의해 평가되지 못하게 제외할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="41a08-124">You can choose to exclude files and folders from being evaluated by attack surface reduction rules.</span></span> <span data-ttu-id="41a08-125">제외된 경우 공격 표면 감소 규칙이 파일에 악의적인 동작이 포함되어 있는 것을 감지한 경우에도 파일이 실행되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="41a08-125">When excluded, the file won't be blocked from running even if an attack surface reduction rule detects that the file contains malicious behavior.</span></span>

<span data-ttu-id="41a08-126">예를 들어 랜섬웨어 규칙을 고려합니다.</span><span class="sxs-lookup"><span data-stu-id="41a08-126">For example, consider the ransomware rule:</span></span>

<span data-ttu-id="41a08-127">랜섬웨어 규칙은 기업 고객이 비즈니스 연속성을 보장하면서 랜섬웨어 공격의 위험을 줄일 수 있도록 고안된 규칙입니다.</span><span class="sxs-lookup"><span data-stu-id="41a08-127">The ransomware rule is designed to help enterprise customers reduce risks of ransomware attacks while ensuring business continuity.</span></span> <span data-ttu-id="41a08-128">기본적으로 랜섬웨어 규칙 오류는 신중하게 처리하고 아직 충분한 신뢰도와 신뢰를 거치지 않은 파일에 대해 보호합니다.</span><span class="sxs-lookup"><span data-stu-id="41a08-128">By default, the ransomware rule errors on the side of caution and protect against files that haven't yet attained sufficient reputation and trust.</span></span> <span data-ttu-id="41a08-129">다시 강조하기 위해 랜섬웨어 규칙은 수백만 고객의 사용 메트릭에 따라 충분히 긍정적인 평판과 보전을 얻지 않은 파일에만 트리거합니다.</span><span class="sxs-lookup"><span data-stu-id="41a08-129">To reemphasize, the ransomware rule only triggers on files that have not gained enough positive reputation and prevalence, based on usage metrics of millions of our customers.</span></span> <span data-ttu-id="41a08-130">일반적으로 각 파일의 "신뢰도 및 신뢰" 값은 문제가 없는 사용이 증가하면 증분적으로 업그레이드하기 때문에 블록이 자체적으로 해결됩니다.</span><span class="sxs-lookup"><span data-stu-id="41a08-130">Usually, the blocks are self resolved, because each file's “reputation and trust” values are incrementally upgraded as non-problematic usage increases.</span></span>

<span data-ttu-id="41a08-131">블록이 제시간에 자체적으로 해결되지 않는 경우 고객은 셀프 서비스 메커니즘 또는 IOC(손상 표시기) 기반 "허용 목록" 기능을 사용하여 파일 차단을 해제할 수 있습니다. </span><span class="sxs-lookup"><span data-stu-id="41a08-131">In cases in which blocks aren’t self resolved in a timely manner, customers can - _at their own risk_ - make use of either the self-service mechanism or an Indicator of Compromise (IOC)-based "allow list" capability to unblock the files themselves.</span></span>  

> [!WARNING]
> <span data-ttu-id="41a08-132">파일 또는 폴더를 제외하거나 차단 해제하면 안전하지 않은 파일이 실행되고 장치를 감염시킬 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="41a08-132">Excluding or unblocking files or folders could potentially allow unsafe files to run and infect your devices.</span></span> <span data-ttu-id="41a08-133">파일 또는 폴더를 제외하면 공격 표면 감소 규칙에서 제공하는 보호가 크게 감소할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="41a08-133">Excluding files or folders can severely reduce the protection provided by attack surface reduction rules.</span></span> <span data-ttu-id="41a08-134">규칙에 의해 차단된 파일은 실행할 수 있으며 보고서나 이벤트가 기록되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="41a08-134">Files that would have been blocked by a rule will be allowed to run, and there will be no report or event recorded.</span></span>

<span data-ttu-id="41a08-135">제외는 제외를 허용하는 모든 규칙에 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="41a08-135">An exclusion applies to all rules that allow exclusions.</span></span> <span data-ttu-id="41a08-136">개별 파일, 폴더 경로 또는 리소스의 정식 도메인 이름을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="41a08-136">You can specify an individual file, folder path, or the fully qualified domain name for a resource.</span></span> <span data-ttu-id="41a08-137">그러나 특정 규칙에 대한 제외는 제한할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="41a08-137">However, you cannot limit an exclusion to a specific rule.</span></span>

<span data-ttu-id="41a08-138">제외는 제외된 응용 프로그램 또는 서비스가 시작될 때만 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="41a08-138">An exclusion is applied only when the excluded application or service starts.</span></span> <span data-ttu-id="41a08-139">예를 들어 이미 실행 중인 업데이트 서비스에 대해 제외를 추가하는 경우 업데이트 서비스는 서비스가 중지되고 다시 시작될 때까지 이벤트를 계속 트리거합니다.</span><span class="sxs-lookup"><span data-stu-id="41a08-139">For example, if you add an exclusion for an update service that is already running, the update service will continue to trigger events until the service is stopped and restarted.</span></span>

<span data-ttu-id="41a08-140">공격 범위 축소는 환경 변수 및 와일드카드를 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="41a08-140">Attack surface reduction supports environment variables and wildcards.</span></span> <span data-ttu-id="41a08-141">와일드카드 사용에 대한 자세한 내용은 파일 이름 및 폴더 경로 또는 확장명 제외 목록에서 와일드카드 [사용을 참조하세요.](configure-extension-file-exclusions-microsoft-defender-antivirus.md#use-wildcards-in-the-file-name-and-folder-path-or-extension-exclusion-lists)</span><span class="sxs-lookup"><span data-stu-id="41a08-141">For information about using wildcards, see [use wildcards in the file name and folder path or extension exclusion lists](configure-extension-file-exclusions-microsoft-defender-antivirus.md#use-wildcards-in-the-file-name-and-folder-path-or-extension-exclusion-lists) .</span></span>
<span data-ttu-id="41a08-142">검색되지 않을 것으로 생각되는 파일을 검색하는 규칙에 문제가 발생하는 경우 감사 모드를 사용하여 규칙을 [테스트합니다.](evaluate-attack-surface-reduction.md)</span><span class="sxs-lookup"><span data-stu-id="41a08-142">If you are encountering problems with rules detecting files that you believe should not be detected, [use audit mode to test the rule](evaluate-attack-surface-reduction.md).</span></span>

| <span data-ttu-id="41a08-143">규칙 설명</span><span class="sxs-lookup"><span data-stu-id="41a08-143">Rule description</span></span> | <span data-ttu-id="41a08-144">GUID</span><span class="sxs-lookup"><span data-stu-id="41a08-144">GUID</span></span> |
|:----|:----|
| <span data-ttu-id="41a08-145">악용된 취약한 서명된 드라이버의 남용 차단</span><span class="sxs-lookup"><span data-stu-id="41a08-145">Block abuse of exploited vulnerable signed drivers</span></span> | `56a863a9-875e-4185-98a7-b882c64b5ce5` |
| <span data-ttu-id="41a08-146">Adobe Reader에서 하위 프로세스를 만들지 차단</span><span class="sxs-lookup"><span data-stu-id="41a08-146">Block Adobe Reader from creating child processes</span></span> | `7674ba52-37eb-4a4f-a9a1-f0f9a1619a2c` |
| <span data-ttu-id="41a08-147">모든 Office 응용 프로그램에서 자식 프로세스를 만들지 차단</span><span class="sxs-lookup"><span data-stu-id="41a08-147">Block all Office applications from creating child processes</span></span> | `D4F940AB-401B-4EFC-AADC-AD5F3C50688A` |
| <span data-ttu-id="41a08-148">로컬 보안 기관 하위 Windows(lsass.exe)에서 자격 증명 도용 차단</span><span class="sxs-lookup"><span data-stu-id="41a08-148">Block credential stealing from the Windows local security authority subsystem (lsass.exe)</span></span> | `9e6c4e1f-7d60-472f-ba1a-a39ef669e4b2` |
| <span data-ttu-id="41a08-149">전자 메일 클라이언트 및 웹 메일에서 실행 가능한 콘텐츠 차단</span><span class="sxs-lookup"><span data-stu-id="41a08-149">Block executable content from email client and webmail</span></span> | `BE9BA2D9-53EA-4CDC-84E5-9B1EEEE46550` |
| <span data-ttu-id="41a08-150">실행 파일이 보전, 보존 또는 신뢰할 수 있는 목록 조건을 충족하지 않는 한 실행 파일이 실행되지 못하게 차단</span><span class="sxs-lookup"><span data-stu-id="41a08-150">Block executable files from running unless they meet a prevalence, age, or trusted list criteria</span></span> | `01443614-cd74-433a-b99e-2ecdc07bfc25` |
| <span data-ttu-id="41a08-151">잠재적으로 난치될 수 있는 스크립트의 실행 차단</span><span class="sxs-lookup"><span data-stu-id="41a08-151">Block execution of potentially obfuscated scripts</span></span> | `5BEB7EFE-FD9A-4556-801D-275E5FFC04CC` |
| <span data-ttu-id="41a08-152">JavaScript 또는 VBScript에서 다운로드한 실행 콘텐츠 시작 차단</span><span class="sxs-lookup"><span data-stu-id="41a08-152">Block JavaScript or VBScript from launching downloaded executable content</span></span> | `D3E037E1-3EB8-44C8-A917-57927947596D` |
| <span data-ttu-id="41a08-153">응용 Office 콘텐츠 만들기 차단</span><span class="sxs-lookup"><span data-stu-id="41a08-153">Block Office applications from creating executable content</span></span> | `3B576869-A4EC-4529-8536-B80A7769E899` |
| <span data-ttu-id="41a08-154">응용 Office 코드 삽입 차단</span><span class="sxs-lookup"><span data-stu-id="41a08-154">Block Office applications from injecting code into other processes</span></span> | `75668C1F-73B5-4CF0-BB93-3ECF5CB7CC84` |
| <span data-ttu-id="41a08-155">통신 Office 자식 프로세스를 만들지 차단</span><span class="sxs-lookup"><span data-stu-id="41a08-155">Block Office communication applications from creating child processes</span></span> | `26190899-1602-49e8-8b27-eb1d0a1ce869` |
| <span data-ttu-id="41a08-156">WMI 이벤트 구독을 통한 지속성 차단</span><span class="sxs-lookup"><span data-stu-id="41a08-156">Block persistence through WMI event subscription</span></span> | `e6db77e5-3df2-4cf1-b95a-636979351e5b` |
| <span data-ttu-id="41a08-157">PSExec 및 WMI 명령에서 시작된 프로세스 생성 차단</span><span class="sxs-lookup"><span data-stu-id="41a08-157">Block process creations originating from PSExec and WMI commands</span></span> | `d1e49aac-8f56-4280-b9ba-993a6d77406c` |
| <span data-ttu-id="41a08-158">USB에서 실행된 무단 및 사인되지 않은 프로세스 차단</span><span class="sxs-lookup"><span data-stu-id="41a08-158">Block untrusted and unsigned processes that run from USB</span></span> | `b2b3f03d-6a65-4f7b-a9c7-1c7ef74a9ba4` |
| <span data-ttu-id="41a08-159">매크로에서 Win32 API Office 차단</span><span class="sxs-lookup"><span data-stu-id="41a08-159">Block Win32 API calls from Office macro</span></span> | `92E97FA1-2EDF-4476-BDD6-9DD0B4DDDC7B` |
| <span data-ttu-id="41a08-160">랜섬웨어에 대한 고급 보호 사용</span><span class="sxs-lookup"><span data-stu-id="41a08-160">Use advanced protection against ransomware</span></span> | `c1db55ab-c21a-4637-bb3f-a12568109d35` |

<span data-ttu-id="41a08-161">각 [규칙에 대한 자세한](attack-surface-reduction.md) 내용은 공격 표면 축소 항목을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="41a08-161">See the [attack surface reduction](attack-surface-reduction.md) topic for details on each rule.</span></span>

### <a name="use-group-policy-to-exclude-files-and-folders"></a><span data-ttu-id="41a08-162">그룹 정책을 사용하여 파일 및 폴더 제외</span><span class="sxs-lookup"><span data-stu-id="41a08-162">Use Group Policy to exclude files and folders</span></span>

1. <span data-ttu-id="41a08-163">그룹 정책 관리 컴퓨터에서 [그룹 정책 관리 콘솔](https://technet.microsoft.com/library/cc731212.aspx)을 열고 구성하려는 그룹 정책 개체를 마우스 오른쪽 단추로 클릭한 다음 **편집** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="41a08-163">On your Group Policy management computer, open the [Group Policy Management Console](https://technet.microsoft.com/library/cc731212.aspx), right-click the Group Policy Object you want to configure and select **Edit**.</span></span>

2. <span data-ttu-id="41a08-164">그룹 정책 **관리 편집기에서** 컴퓨터 **구성으로 이동하여** 관리 템플릿 **을 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="41a08-164">In the **Group Policy Management Editor**, go to **Computer configuration** and click **Administrative templates**.</span></span>

3. <span data-ttu-id="41a08-165">공격 표면 **감소를 Windows 구성**  >  **Microsoft Defender 바이러스 백신**  >  **Microsoft Defender Exploit Guard**  >  **트리를 확장합니다.**</span><span class="sxs-lookup"><span data-stu-id="41a08-165">Expand the tree to **Windows components** > **Microsoft Defender Antivirus** > **Microsoft Defender Exploit Guard** > **Attack surface reduction**.</span></span>

4. <span data-ttu-id="41a08-166">공격 표면 축소 **규칙에서** 파일 및 경로 제외 설정을 두 번 클릭하고 옵션을 사용으로 **설정합니다.**</span><span class="sxs-lookup"><span data-stu-id="41a08-166">Double-click the **Exclude files and paths from Attack surface reduction Rules** setting and set the option to **Enabled**.</span></span> <span data-ttu-id="41a08-167">표시를 **선택하고** 값 이름 열에 각 파일 또는 **폴더를 입력합니다.**</span><span class="sxs-lookup"><span data-stu-id="41a08-167">Select **Show** and enter each file or folder in the **Value name** column.</span></span> <span data-ttu-id="41a08-168">각 항목의 값 **열에** **0을** 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="41a08-168">Enter **0** in the **Value** column for each item.</span></span>

> [!WARNING]
> <span data-ttu-id="41a08-169">값 이름 열이나 값 열에 대해  지원되지 않는 따옴표를 사용하지 **않습니다.**</span><span class="sxs-lookup"><span data-stu-id="41a08-169">Do not use quotes as they are not supported for either the **Value name** column or the **Value** column.</span></span>

### <a name="use-powershell-to-exclude-files-and-folders"></a><span data-ttu-id="41a08-170">PowerShell을 사용하여 파일 및 폴더 제외</span><span class="sxs-lookup"><span data-stu-id="41a08-170">Use PowerShell to exclude files and folders</span></span>

1. <span data-ttu-id="41a08-171">목록에서 **powershell을** 시작 메뉴 마우스 오른쪽 **단추로** 클릭하고 Windows PowerShell 관리자 권한으로 **실행을 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="41a08-171">Type **powershell** in the Start menu, right-click **Windows PowerShell** and select **Run as administrator**</span></span>
2. <span data-ttu-id="41a08-172">다음 cmdlet을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="41a08-172">Enter the following cmdlet:</span></span>

    ```PowerShell
    Add-MpPreference -AttackSurfaceReductionOnlyExclusions "<fully qualified path or resource>"
    ```

<span data-ttu-id="41a08-173">계속 사용하여 `Add-MpPreference -AttackSurfaceReductionOnlyExclusions` 목록에 폴더를 더 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="41a08-173">Continue to use `Add-MpPreference -AttackSurfaceReductionOnlyExclusions` to add more folders to the list.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="41a08-174">목록에 `Add-MpPreference` 앱을 추가하거나 추가하는 데 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="41a08-174">Use `Add-MpPreference` to append or add apps to the list.</span></span> <span data-ttu-id="41a08-175">`Set-MpPreference`cmdlet을 사용하여 기존 목록을 덮어 습니다.</span><span class="sxs-lookup"><span data-stu-id="41a08-175">Using the `Set-MpPreference` cmdlet will overwrite the existing list.</span></span>

### <a name="use-mdm-csps-to-exclude-files-and-folders"></a><span data-ttu-id="41a08-176">MDM CSP를 사용하여 파일 및 폴더 제외</span><span class="sxs-lookup"><span data-stu-id="41a08-176">Use MDM CSPs to exclude files and folders</span></span>

<span data-ttu-id="41a08-177">[./Vendor/MSFT/Policy/Config/Defender/AttackSurfaceReductionOnlyExclusions](/windows/client-management/mdm/policy-csp-defender#defender-attacksurfacereductiononlyexclusions) CSP(구성 서비스 공급자)를 사용하여 제외를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="41a08-177">Use the [./Vendor/MSFT/Policy/Config/Defender/AttackSurfaceReductionOnlyExclusions](/windows/client-management/mdm/policy-csp-defender#defender-attacksurfacereductiononlyexclusions) configuration service provider (CSP) to add exclusions.</span></span>

## <a name="customize-the-notification"></a><span data-ttu-id="41a08-178">알림 사용자 지정</span><span class="sxs-lookup"><span data-stu-id="41a08-178">Customize the notification</span></span>

<span data-ttu-id="41a08-179">규칙이 트리거되는 경우 알림을 사용자 지정하고 앱 또는 파일을 차단할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="41a08-179">You can customize the notification for when a rule is triggered and blocks an app or file.</span></span> <span data-ttu-id="41a08-180">자세한 [내용은 Windows 보안](/windows/security/threat-protection/windows-defender-security-center/windows-defender-security-center#customize-notifications-from-the-windows-defender-security-center) 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="41a08-180">See the [Windows Security](/windows/security/threat-protection/windows-defender-security-center/windows-defender-security-center#customize-notifications-from-the-windows-defender-security-center) article.</span></span>

## <a name="related-topics"></a><span data-ttu-id="41a08-181">관련 주제</span><span class="sxs-lookup"><span data-stu-id="41a08-181">Related topics</span></span>

- [<span data-ttu-id="41a08-182">공격 표면 감소 규칙을 사용하여 공격 표면 감소</span><span class="sxs-lookup"><span data-stu-id="41a08-182">Reduce attack surfaces with attack surface reduction rules</span></span>](attack-surface-reduction.md)
- [<span data-ttu-id="41a08-183">공격 표면 감소 규칙 사용</span><span class="sxs-lookup"><span data-stu-id="41a08-183">Enable attack surface reduction rules</span></span>](enable-attack-surface-reduction.md)
- [<span data-ttu-id="41a08-184">공격 표면 감소 규칙 평가</span><span class="sxs-lookup"><span data-stu-id="41a08-184">Evaluate attack surface reduction rules</span></span>](evaluate-attack-surface-reduction.md)
- [<span data-ttu-id="41a08-185">공격 표면 감소 FAQ</span><span class="sxs-lookup"><span data-stu-id="41a08-185">Attack surface reduction FAQ</span></span>](attack-surface-reduction.md)
