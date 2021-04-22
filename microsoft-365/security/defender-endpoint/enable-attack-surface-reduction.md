---
title: 공격 표면 감소 규칙 사용
description: ASR(공격 표면 축소) 규칙을 사용하도록 설정하여 매크로, 스크립트 및 일반적인 삽입 기술을 사용하는 공격으로부터 장치를 보호합니다.
keywords: 공격 표면 감소, hips, 호스트 침입 방지 시스템, 보호 규칙, 악용 방지, 악용, 감염 방지, 사용, 켜기
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
ms.openlocfilehash: 7aeda679d5ce350ef64a2758359390adc4a280f0
ms.sourcegitcommit: 4076b43a4b661de029f6307ddc1a989ab3108edb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/22/2021
ms.locfileid: "51939245"
---
# <a name="enable-attack-surface-reduction-rules"></a><span data-ttu-id="d0827-104">공격 표면 감소 규칙 사용</span><span class="sxs-lookup"><span data-stu-id="d0827-104">Enable attack surface reduction rules</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="d0827-105">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="d0827-105">**Applies to:**</span></span>
- [<span data-ttu-id="d0827-106">엔드포인트용 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="d0827-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="d0827-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="d0827-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> [!TIP]
> <span data-ttu-id="d0827-108">Endpoint용 Defender를 경험하고 싶나요?</span><span class="sxs-lookup"><span data-stu-id="d0827-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="d0827-109">무료 평가판에 등록합니다.</span><span class="sxs-lookup"><span data-stu-id="d0827-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-assignaccess-abovefoldlink)

<span data-ttu-id="d0827-110">ASR [규칙(공격](attack-surface-reduction.md) 표면 축소 규칙)은 맬웨어가 장치 및 네트워크를 손상하기 위해 자주 남용되는 작업을 방지하는 데 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d0827-110">[Attack surface reduction rules](attack-surface-reduction.md) (ASR rules) help prevent actions that malware often abuses to compromise devices and networks.</span></span> <span data-ttu-id="d0827-111">다음 Windows 버전 및 버전을 실행하는 장치에 대해 ASR 규칙을 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d0827-111">You can set ASR rules for devices running any of the following editions and versions of Windows:</span></span>
- <span data-ttu-id="d0827-112">Windows 10 Pro 버전 [1709](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1709) 이상</span><span class="sxs-lookup"><span data-stu-id="d0827-112">Windows 10 Pro, [version 1709](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1709) or later</span></span>
- <span data-ttu-id="d0827-113">Windows 10 Enterprise 버전 [1709](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1709) 이상</span><span class="sxs-lookup"><span data-stu-id="d0827-113">Windows 10 Enterprise, [version 1709](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1709) or later</span></span>
- <span data-ttu-id="d0827-114">Windows Server, [버전 1803(반기 채널)](https://docs.microsoft.com/windows-server/get-started/whats-new-in-windows-server-1803) 이상</span><span class="sxs-lookup"><span data-stu-id="d0827-114">Windows Server, [version 1803 (Semi-Annual Channel)](https://docs.microsoft.com/windows-server/get-started/whats-new-in-windows-server-1803) or later</span></span>
- [<span data-ttu-id="d0827-115">Windows Server 2019</span><span class="sxs-lookup"><span data-stu-id="d0827-115">Windows Server 2019</span></span>](https://docs.microsoft.com/windows-server/get-started-19/whats-new-19)

<span data-ttu-id="d0827-116">**요구 사항** 다음 Windows 버전 및 버전을 실행하는 장치에 대해 공격 표면 감소 규칙을 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d0827-116">**Requirements** You can set attack surface reduction rules for devices that are running any of the following editions and versions of Windows:</span></span>

- <span data-ttu-id="d0827-117">Windows 10 Pro 버전 1709 이상</span><span class="sxs-lookup"><span data-stu-id="d0827-117">Windows 10 Pro, version 1709 or later</span></span>
- <span data-ttu-id="d0827-118">Windows 10 Enterprise 버전 1709 이상</span><span class="sxs-lookup"><span data-stu-id="d0827-118">Windows 10 Enterprise, version 1709 or later</span></span>
- <span data-ttu-id="d0827-119">Windows Server, 버전 1803(반기 채널) 이상</span><span class="sxs-lookup"><span data-stu-id="d0827-119">Windows Server, version 1803 (Semi-Annual Channel) or later</span></span>
- <span data-ttu-id="d0827-120">Windows Server 2019</span><span class="sxs-lookup"><span data-stu-id="d0827-120">Windows Server 2019</span></span>

<span data-ttu-id="d0827-121">공격 표면 감소 규칙에는 Windows E5 라이선스가 필요하지 않습니다. 그러나 Windows E5가 있는 경우 고급 관리 기능을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d0827-121">Although attack surface reduction rules don't require a Windows E5 license, if you have Windows E5, you get advanced management capabilities.</span></span> <span data-ttu-id="d0827-122">Windows E5에서만 사용할 수 있는 이러한 기능에는 끝점용 Defender에서 사용할 수 있는 모니터링, 분석 및 워크플로와 Microsoft 365 보안 센터의 보고 및 구성 기능이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="d0827-122">These capabilities available only in Windows E5 include monitoring, analytics, and workflows available in Defender for Endpoint, as well as reporting and configuration capabilities in the Microsoft 365 security center.</span></span> <span data-ttu-id="d0827-123">이러한 고급 기능은 Windows Professional 또는 Windows E3 라이선스에서 사용할 수 없습니다. 그러나 해당 라이선스가 있는 경우 이벤트 뷰어 및 Microsoft Defender 바이러스 백신 로그를 사용하여 공격 표면 축소 규칙 이벤트를 검토할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d0827-123">These advanced capabilities aren't available with a Windows Professional or Windows E3 license; however, if you do have those licenses, you can use Event Viewer and Microsoft Defender Antivirus logs to review your attack surface reduction rule events.</span></span>

<span data-ttu-id="d0827-124">각 ASR 규칙에는 다음 네 가지 설정 중 하나가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d0827-124">Each ASR rule contains one of four settings:</span></span>

- <span data-ttu-id="d0827-125">**구성되지 않은 경우:** ASR 규칙을 사용하지 않도록 설정</span><span class="sxs-lookup"><span data-stu-id="d0827-125">**Not configured**: Disable the ASR rule</span></span>
- <span data-ttu-id="d0827-126">**차단:** ASR 규칙 사용</span><span class="sxs-lookup"><span data-stu-id="d0827-126">**Block**: Enable the ASR rule</span></span>
- <span data-ttu-id="d0827-127">**감사:** ASR 규칙이 사용하도록 설정된 경우 조직에 미치는 영향 평가</span><span class="sxs-lookup"><span data-stu-id="d0827-127">**Audit**: Evaluate how the ASR rule would impact your organization if enabled</span></span>
- <span data-ttu-id="d0827-128">**경고:** ASR 규칙을 사용하도록 설정하지만 최종 사용자가 차단을 무시하도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="d0827-128">**Warn**: Enable the ASR rule but alow the end user to bypass the block</span></span>

> [!IMPORTANT]
> <span data-ttu-id="d0827-129">현재 MEM(Microsoft Endpoint Manager)에서 ASR 규칙을 구성할 때 세 가지 ASR 규칙에 대해 경고 모드가 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d0827-129">Currently, warn mode is not supported for three ASR rules when you configure ASR rules in Microsoft Endpoint Manager (MEM).</span></span> <span data-ttu-id="d0827-130">자세한 내용은 경고 모드가 지원되지 [않는 경우를 참조합니다.](attack-surface-reduction.md#cases-where-warn-mode-is-not-supported)</span><span class="sxs-lookup"><span data-stu-id="d0827-130">To learn more, see [Cases where warn mode is not supported](attack-surface-reduction.md#cases-where-warn-mode-is-not-supported).</span></span>

<span data-ttu-id="d0827-131">Windows E5 라이선스(또는 유사한 라이선스 SKU)와 함께 ASR 규칙을 사용하여 [끝점용 Microsoft Defender(Endpoint용 Defender)에서](https://docs.microsoft.com/windows/security/threat-protection) 사용할 수 있는 고급 모니터링 및 보고 기능을 활용하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="d0827-131">It's highly recommended you use ASR rules with a Windows E5 license (or similar licensing SKU) to take advantage of the advanced monitoring and reporting capabilities available in [Microsoft Defender for Endpoint](https://docs.microsoft.com/windows/security/threat-protection) (Defender for Endpoint).</span></span> <span data-ttu-id="d0827-132">그러나 고급 모니터링 및 보고 기능에 액세스할 수 없는 Windows Professional 또는 E3와 같은 다른 라이선스의 경우 ASR 규칙이 트리거될 때 각 끝점에서 생성되는 이벤트(예: 이벤트 전달)를 통해 자체 모니터링 및 보고 도구를 개발할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d0827-132">However, for other licenses like Windows Professional or E3 that don't have access to advanced monitoring and reporting capabilities, you can develop your own monitoring and reporting tools on top of the events that are generated at each endpoint when ASR rules are triggered (e.g., Event Forwarding).</span></span>

> [!TIP]
> <span data-ttu-id="d0827-133">Windows 라이선스에 대한 자세한 내용은 Windows 10 라이선스를 참조하고 Windows [10용](https://www.microsoft.com/licensing/product-licensing/windows10?activetab=windows10-pivot:primaryr5) 볼륨 라이선스 [가이드를 참조하세요.](https://download.microsoft.com/download/2/D/1/2D14FE17-66C2-4D4C-AF73-E122930B60F6/Windows-10-Volume-Licensing-Guide.pdf)</span><span class="sxs-lookup"><span data-stu-id="d0827-133">To learn more about Windows licensing, see [Windows 10 Licensing](https://www.microsoft.com/licensing/product-licensing/windows10?activetab=windows10-pivot:primaryr5) and get the [Volume Licensing guide for Windows 10](https://download.microsoft.com/download/2/D/1/2D14FE17-66C2-4D4C-AF73-E122930B60F6/Windows-10-Volume-Licensing-Guide.pdf).</span></span>

<span data-ttu-id="d0827-134">다음 방법을 사용하여 공격 표면 감소 규칙을 사용하도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d0827-134">You can enable attack surface reduction rules by using any of these methods:</span></span>

- [<span data-ttu-id="d0827-135">Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="d0827-135">Microsoft Intune</span></span>](#intune)
- [<span data-ttu-id="d0827-136">MDM(모바일 장치 관리)</span><span class="sxs-lookup"><span data-stu-id="d0827-136">Mobile Device Management (MDM)</span></span>](#mdm)
- [<span data-ttu-id="d0827-137">Microsoft Endpoint Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="d0827-137">Microsoft Endpoint Configuration Manager</span></span>](#microsoft-endpoint-configuration-manager)
- [<span data-ttu-id="d0827-138">그룹 정책</span><span class="sxs-lookup"><span data-stu-id="d0827-138">Group Policy</span></span>](#group-policy)
- [<span data-ttu-id="d0827-139">PowerShell</span><span class="sxs-lookup"><span data-stu-id="d0827-139">PowerShell</span></span>](#powershell)

<span data-ttu-id="d0827-140">Intune 또는 Microsoft Endpoint Manager와 같은 엔터프라이즈 수준 관리가 권장됩니다.</span><span class="sxs-lookup"><span data-stu-id="d0827-140">Enterprise-level management such as Intune or Microsoft Endpoint Manager is recommended.</span></span> <span data-ttu-id="d0827-141">엔터프라이즈 수준 관리는 시작 시 충돌하는 그룹 정책 또는 PowerShell 설정을 덮어 덮어 덮어 들이게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d0827-141">Enterprise-level management will overwrite any conflicting Group Policy or PowerShell settings on startup.</span></span>

## <a name="exclude-files-and-folders-from-asr-rules"></a><span data-ttu-id="d0827-142">ASR 규칙에서 파일 및 폴더 제외</span><span class="sxs-lookup"><span data-stu-id="d0827-142">Exclude files and folders from ASR rules</span></span>

<span data-ttu-id="d0827-143">대부분의 공격 표면 감소 규칙에 의해 평가되지 않는 파일 및 폴더를 제외할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d0827-143">You can exclude files and folders from being evaluated by most attack surface reduction rules.</span></span> <span data-ttu-id="d0827-144">즉, ASR 규칙이 파일 또는 폴더에 악의적인 동작이 포함되어 있는지 확인한 경우에도 파일이 실행되는 것을 차단하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d0827-144">This means that even if an ASR rule determines the file or folder contains malicious behavior, it will not block the file from running.</span></span> <span data-ttu-id="d0827-145">이렇게 하면 안전하지 않은 파일이 실행되고 장치를 감염시킬 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d0827-145">This could potentially allow unsafe files to run and infect your devices.</span></span>

<span data-ttu-id="d0827-146">끝점 파일 및 인증서 표시기를 위해 지정된 Defender를 허용하여 인증서 및 파일 해시에 따라 ASR 규칙을 트리거하지 못하게 제외할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d0827-146">You can also exclude ASR rules from triggering based on certificate and file hashes by allowing specified Defender for Endpoint file and certificate indicators.</span></span> <span data-ttu-id="d0827-147">[(표시기 관리를](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/manage-indicators)참조합니다.)</span><span class="sxs-lookup"><span data-stu-id="d0827-147">(See [Manage indicators](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/manage-indicators).)</span></span>

> [!IMPORTANT]
> <span data-ttu-id="d0827-148">파일 또는 폴더를 제외하면 ASR 규칙에서 제공하는 보호를 심각하게 줄일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d0827-148">Excluding files or folders can severely reduce the protection provided by ASR rules.</span></span> <span data-ttu-id="d0827-149">제외된 파일은 실행될 수 있으며 보고서나 이벤트는 기록되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d0827-149">Excluded files will be allowed to run, and no report or event will be recorded.</span></span>
> <span data-ttu-id="d0827-150">ASR 규칙이 검색되지 않는 것으로 생각되는 파일을 검색하는 경우 먼저 감사 모드를 사용하여 규칙을 [테스트해야 합니다.](evaluate-attack-surface-reduction.md)</span><span class="sxs-lookup"><span data-stu-id="d0827-150">If ASR rules are detecting files that you believe shouldn't be detected, you should [use audit mode first to test the rule](evaluate-attack-surface-reduction.md).</span></span>


<span data-ttu-id="d0827-151">개별 파일 또는 폴더(폴더 경로 또는 정식 리소스 이름을 사용하여)를 지정할 수 있지만 제외가 적용되는 규칙을 지정할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="d0827-151">You can specify individual files or folders (using folder paths or fully qualified resource names), but you can't specify which rules the exclusions apply to.</span></span> <span data-ttu-id="d0827-152">제외는 제외된 응용 프로그램 또는 서비스가 시작될 때만 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="d0827-152">An exclusion is applied only when the excluded application or service starts.</span></span> <span data-ttu-id="d0827-153">예를 들어 이미 실행 중인 업데이트 서비스에 대해 제외를 추가하는 경우 업데이트 서비스는 서비스가 중지되고 다시 시작될 때까지 이벤트를 계속 트리거합니다.</span><span class="sxs-lookup"><span data-stu-id="d0827-153">For example, if you add an exclusion for an update service that is already running, the update service will continue to trigger events until the service is stopped and restarted.</span></span>

<span data-ttu-id="d0827-154">ASR 규칙은 환경 변수 및 와일드카드를 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="d0827-154">ASR rules support environment variables and wildcards.</span></span> <span data-ttu-id="d0827-155">와일드카드 사용에 대한 자세한 내용은 파일 이름 및 폴더 경로 또는 확장명 제외 목록에 와일드카드 사용을 [참조하세요.](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/configure-extension-file-exclusions-microsoft-defender-antivirus#use-wildcards-in-the-file-name-and-folder-path-or-extension-exclusion-lists)</span><span class="sxs-lookup"><span data-stu-id="d0827-155">For information about using wildcards, see [Use wildcards in the file name and folder path or extension exclusion lists](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/configure-extension-file-exclusions-microsoft-defender-antivirus#use-wildcards-in-the-file-name-and-folder-path-or-extension-exclusion-lists).</span></span>

<span data-ttu-id="d0827-156">ASR 규칙을 사용하도록 설정하는 다음 절차에는 파일 및 폴더를 제외하는 방법에 대한 지침이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d0827-156">The following procedures for enabling ASR rules include instructions for how to exclude files and folders.</span></span>

## <a name="intune"></a><span data-ttu-id="d0827-157">Intune</span><span class="sxs-lookup"><span data-stu-id="d0827-157">Intune</span></span>

1. <span data-ttu-id="d0827-158">장치 **구성**  >  **프로필을 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="d0827-158">Select **Device configuration** > **Profiles**.</span></span> <span data-ttu-id="d0827-159">기존 끝점 보호 프로필을 선택하거나 새 끝점 보호 프로필을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d0827-159">Choose an existing endpoint protection profile or create a new one.</span></span> <span data-ttu-id="d0827-160">새 프로필을 만들하려면 프로필 만들기를 **선택하고** 이 프로필에 대한 정보를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="d0827-160">To create a new one, select **Create profile** and enter information for this profile.</span></span> <span data-ttu-id="d0827-161">프로필 **유형에서** **끝점 보호를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="d0827-161">For **Profile type**, select **Endpoint protection**.</span></span> <span data-ttu-id="d0827-162">기존 프로필을 선택한 경우 속성을 선택한 **다음** 설정을 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="d0827-162">If you've chosen an existing profile, select **Properties** and then select **Settings**.</span></span>

2. <span data-ttu-id="d0827-163">끝점 보호 창에서 **Exploit** **Guard** Windows Defender 선택하고 공격 표면 **감소를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="d0827-163">In the **Endpoint protection** pane, select **Windows Defender Exploit Guard**, then select **Attack Surface Reduction**.</span></span> <span data-ttu-id="d0827-164">각 ASR 규칙에 대해 원하는 설정을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="d0827-164">Select the desired setting for each ASR rule.</span></span>

3. <span data-ttu-id="d0827-165">공격 **표면 감소 예외에서** 개별 파일 및 폴더를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="d0827-165">Under **Attack Surface Reduction exceptions**, enter individual files and folders.</span></span> <span data-ttu-id="d0827-166">가져오기 **를** 선택하여 ASR 규칙에서 제외할 파일 및 폴더가 포함된 CSV 파일을 가져올 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d0827-166">You can also select **Import** to import a CSV file that contains files and folders to exclude from ASR rules.</span></span> <span data-ttu-id="d0827-167">CSV 파일의 각 줄 서식은 다음과 같이 지정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d0827-167">Each line in the CSV file should be formatted as follows:</span></span>

   <span data-ttu-id="d0827-168">`C:\folder`, `%ProgramFiles%\folder\file`, `C:\path`</span><span class="sxs-lookup"><span data-stu-id="d0827-168">`C:\folder`, `%ProgramFiles%\folder\file`, `C:\path`</span></span>

4. <span data-ttu-id="d0827-169">세 **개의 구성** 창에서 확인을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="d0827-169">Select **OK** on the three configuration panes.</span></span> <span data-ttu-id="d0827-170">그런 다음 **새** 끝점 보호 파일을 만드는  경우 만들기를 선택하고 기존 끝점 보호 파일을 편집하는 경우 저장을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="d0827-170">Then select **Create** if you're creating a new endpoint protection file or **Save** if you're editing an existing one.</span></span>

## <a name="mdm"></a><span data-ttu-id="d0827-171">MDM</span><span class="sxs-lookup"><span data-stu-id="d0827-171">MDM</span></span>

<span data-ttu-id="d0827-172">[./Vendor/MSFT/Policy/Config/Defender/AttackSurfaceReductionRules](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-defender#defender-attacksurfacereductionrules) CSP(구성 서비스 공급자)를 사용하여 각 규칙에 대해 모드를 개별적으로 사용하도록 설정하고 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d0827-172">Use the [./Vendor/MSFT/Policy/Config/Defender/AttackSurfaceReductionRules](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-defender#defender-attacksurfacereductionrules) configuration service provider (CSP) to individually enable and set the mode for each rule.</span></span>

<span data-ttu-id="d0827-173">다음은 ASR 규칙에 GUID 값을 사용하는 참조용 [샘플입니다.](attack-surface-reduction.md#attack-surface-reduction-rules)</span><span class="sxs-lookup"><span data-stu-id="d0827-173">The following is a sample for reference, using [GUID values for ASR rules](attack-surface-reduction.md#attack-surface-reduction-rules).</span></span>

`OMA-URI path: ./Vendor/MSFT/Policy/Config/Defender/AttackSurfaceReductionRules`

`Value: 75668C1F-73B5-4CF0-BB93-3ECF5CB7CC84=2|3B576869-A4EC-4529-8536-B80A7769E899=1|D4F940AB-401B-4EfC-AADC-AD5F3C50688A=2|D3E037E1-3EB8-44C8-A917-57927947596D=1|5BEB7EFE-FD9A-4556-801D-275E5FFC04CC=0|BE9BA2D9-53EA-4CDC-84E5-9B1EEEE46550=1`

<span data-ttu-id="d0827-174">감사 모드에서 사용(차단), 사용 안 하도록 설정, 경고 또는 사용 하도록 설정할 값은:</span><span class="sxs-lookup"><span data-stu-id="d0827-174">The values to enable (Block), disable, warn, or enable in audit mode are:</span></span>

- <span data-ttu-id="d0827-175">0: 사용 안 하게(ASR 규칙 사용 안 하게)</span><span class="sxs-lookup"><span data-stu-id="d0827-175">0 : Disable (Disable the ASR rule)</span></span>
- <span data-ttu-id="d0827-176">1: 차단(ASR 규칙 사용)</span><span class="sxs-lookup"><span data-stu-id="d0827-176">1 : Block (Enable the ASR rule)</span></span>
- <span data-ttu-id="d0827-177">2: 감사(ASR 규칙이 사용하도록 설정된 경우 조직에 어떤 영향을 미치는지 평가)</span><span class="sxs-lookup"><span data-stu-id="d0827-177">2 : Audit (Evaluate how the ASR rule would impact your organization if enabled)</span></span>
- <span data-ttu-id="d0827-178">6: 경고(ASR 규칙을 사용하도록 설정하지만 최종 사용자가 차단을 무시하도록 허용).</span><span class="sxs-lookup"><span data-stu-id="d0827-178">6 : Warn  (Enable the ASR rule but allow the end-user to bypass the block).</span></span> <span data-ttu-id="d0827-179">이제 경고 모드를 대부분의 ASR 규칙에 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d0827-179">Warn mode is now available for most of the ASR rules.</span></span>

<span data-ttu-id="d0827-180">[./Vendor/MSFT/Policy/Config/Defender/AttackSurfaceReductionOnlyExclusions](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-defender#defender-attacksurfacereductiononlyexclusions) CSP(구성 서비스 공급자)를 사용하여 제외를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="d0827-180">Use the [./Vendor/MSFT/Policy/Config/Defender/AttackSurfaceReductionOnlyExclusions](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-defender#defender-attacksurfacereductiononlyexclusions) configuration service provider (CSP) to add exclusions.</span></span>

<span data-ttu-id="d0827-181">예제:</span><span class="sxs-lookup"><span data-stu-id="d0827-181">Example:</span></span>

`OMA-URI path: ./Vendor/MSFT/Policy/Config/Defender/AttackSurfaceReductionOnlyExclusions`

`Value: c:\path|e:\path|c:\Exclusions.exe`

> [!NOTE]
> <span data-ttu-id="d0827-182">공백 없이 OMA-URI 값을 입력해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d0827-182">Be sure to enter OMA-URI values without spaces.</span></span>

## <a name="microsoft-endpoint-configuration-manager"></a><span data-ttu-id="d0827-183">Microsoft Endpoint Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="d0827-183">Microsoft Endpoint Configuration Manager</span></span>

1. <span data-ttu-id="d0827-184">Microsoft Endpoint Configuration Manager에서 Exploit **Guard의** 자산 및 준수 끝점 보호  >    >  **Windows Defender 로 이동합니다.**</span><span class="sxs-lookup"><span data-stu-id="d0827-184">In Microsoft Endpoint Configuration Manager, go to **Assets and Compliance** > **Endpoint Protection** > **Windows Defender Exploit Guard**.</span></span>

2. <span data-ttu-id="d0827-185">홈 **Exploit**  >  **Guard 정책 만들기 를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="d0827-185">Select **Home** > **Create Exploit Guard Policy**.</span></span>

3. <span data-ttu-id="d0827-186">이름과 설명을 입력하고 공격 **표면 감소를 선택하고** 다음 을 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="d0827-186">Enter a name and a description, select **Attack Surface Reduction**, and select **Next**.</span></span>

4. <span data-ttu-id="d0827-187">작업을 차단하거나 감사할 규칙을 선택하고 다음 을 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="d0827-187">Choose which rules will block or audit actions and select **Next**.</span></span>

5. <span data-ttu-id="d0827-188">설정을 검토하고 **다음을** 선택하여 정책을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d0827-188">Review the settings and select **Next** to create the policy.</span></span>

6. <span data-ttu-id="d0827-189">정책을 만든 후 를 **닫습니다.**</span><span class="sxs-lookup"><span data-stu-id="d0827-189">After the policy is created, **Close**.</span></span>

## <a name="group-policy"></a><span data-ttu-id="d0827-190">그룹 정책</span><span class="sxs-lookup"><span data-stu-id="d0827-190">Group Policy</span></span>

> [!WARNING]
> <span data-ttu-id="d0827-191">Intune, Configuration Manager 또는 기타 엔터프라이즈 수준 관리 플랫폼을 사용하여 컴퓨터와 장치를 관리하는 경우 관리 소프트웨어가 시작 시 충돌하는 그룹 정책 설정을 덮어 덮어 덮어 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="d0827-191">If you manage your computers and devices with Intune, Configuration Manager, or other enterprise-level management platform, the management software will overwrite any conflicting Group Policy settings on startup.</span></span>

1. <span data-ttu-id="d0827-192">그룹 정책 관리 컴퓨터에서 그룹 정책 관리 콘솔을 [열고](https://technet.microsoft.com/library/cc731212.aspx)구성할 그룹 정책 개체를 마우스 오른쪽 단추로 클릭하고 편집을 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="d0827-192">On your Group Policy management computer, open the [Group Policy Management Console](https://technet.microsoft.com/library/cc731212.aspx), right-click the Group Policy Object you want to configure and select **Edit**.</span></span>

2. <span data-ttu-id="d0827-193">그룹 **정책 관리 편집기에서** 컴퓨터 **구성으로 이동하여** 관리 **템플릿을 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="d0827-193">In the **Group Policy Management Editor**, go to **Computer configuration** and select **Administrative templates**.</span></span>

3. <span data-ttu-id="d0827-194">**Windows** 구성 요소 Microsoft Defender 바이러스 백신 Microsoft Defender Exploit Guard 공격 표면 감소까지  >    >    >  **트리를 확장합니다.**</span><span class="sxs-lookup"><span data-stu-id="d0827-194">Expand the tree to **Windows components** > **Microsoft Defender Antivirus** > **Microsoft Defender Exploit Guard** > **Attack surface reduction**.</span></span>

4. <span data-ttu-id="d0827-195">공격 **표면 축소 규칙 구성을 선택하고** 사용 을 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="d0827-195">Select **Configure Attack surface reduction rules** and select **Enabled**.</span></span> <span data-ttu-id="d0827-196">그런 다음 옵션 섹션에서 각 규칙에 대한 개별 상태를 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d0827-196">You can then set the individual state for each rule in the options section.</span></span>

   <span data-ttu-id="d0827-197">  **표시...를** 선택하고 값 이름 열에 규칙 ID를 입력하고 다음과 같이 값 열에 선택한 상태를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="d0827-197">Select **Show...** and enter the rule ID in the **Value name** column and your chosen state in the **Value** column as follows:</span></span>

   - <span data-ttu-id="d0827-198">0: 사용 안 하게(ASR 규칙 사용 안 하게)</span><span class="sxs-lookup"><span data-stu-id="d0827-198">0 : Disable (Disable the ASR rule)</span></span>
   - <span data-ttu-id="d0827-199">1: 차단(ASR 규칙 사용)</span><span class="sxs-lookup"><span data-stu-id="d0827-199">1 : Block (Enable the ASR rule)</span></span>
   - <span data-ttu-id="d0827-200">2: 감사(ASR 규칙이 사용하도록 설정된 경우 조직에 어떤 영향을 미치는지 평가)</span><span class="sxs-lookup"><span data-stu-id="d0827-200">2 : Audit (Evaluate how the ASR rule would impact your organization if enabled)</span></span>
   - <span data-ttu-id="d0827-201">6: 경고(ASR 규칙을 사용하도록 설정하지만 최종 사용자가 차단을 무시하도록 허용)</span><span class="sxs-lookup"><span data-stu-id="d0827-201">6 : Warn  (Enable the ASR rule but allow the end-user to bypass the block)</span></span>

   :::image type="content" source="images/asr-rules-gp.png" alt-text="그룹 정책의 ASR 규칙":::

5. <span data-ttu-id="d0827-203">ASR 규칙에서 파일 및 폴더를  제외하려면 공격 표면 축소 규칙에서 파일 및 경로 제외 설정을 선택하고 옵션을 사용으로 **설정합니다.**</span><span class="sxs-lookup"><span data-stu-id="d0827-203">To exclude files and folders from ASR rules, select the **Exclude files and paths from Attack surface reduction rules** setting and set the option to **Enabled**.</span></span> <span data-ttu-id="d0827-204">표시를 **선택하고** 값 이름 열에 각 파일 또는 **폴더를 입력합니다.**</span><span class="sxs-lookup"><span data-stu-id="d0827-204">Select **Show** and enter each file or folder in the **Value name** column.</span></span> <span data-ttu-id="d0827-205">각 항목의 값 **열에** **0을** 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="d0827-205">Enter **0** in the **Value** column for each item.</span></span>

   > [!WARNING]
   > <span data-ttu-id="d0827-206">값 이름 열이나 값 열에 대해  지원되지 않는 따옴표를 사용하지 **않습니다.**</span><span class="sxs-lookup"><span data-stu-id="d0827-206">Do not use quotes as they are not supported for either the **Value name** column or the **Value** column.</span></span>

## <a name="powershell"></a><span data-ttu-id="d0827-207">PowerShell</span><span class="sxs-lookup"><span data-stu-id="d0827-207">PowerShell</span></span>

> [!WARNING]
> <span data-ttu-id="d0827-208">Intune, Configuration Manager 또는 다른 엔터프라이즈 수준의 관리 플랫폼을 사용하여 컴퓨터 및 장치를 관리하는 경우 관리 소프트웨어가 시작 시 충돌하는 PowerShell 설정을 덮어 덮어 덮어 습니다.</span><span class="sxs-lookup"><span data-stu-id="d0827-208">If you manage your computers and devices with Intune, Configuration Manager, or another enterprise-level management platform, the management software will overwrite any conflicting PowerShell settings on startup.</span></span> <span data-ttu-id="d0827-209">사용자가 PowerShell을 사용하여 값을 정의할 수 있도록 허용하기 위해 관리 플랫폼에서 규칙에 대해 "사용자 정의" 옵션을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="d0827-209">To allow users to define the value using PowerShell, use the "User Defined" option for the rule in the management platform.</span></span>

1. <span data-ttu-id="d0827-210">시작 **메뉴에 powershell을** 입력하고 마우스 오른쪽 단추로 Windows PowerShell **관리자** 권한으로 **실행을 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="d0827-210">Type **powershell** in the Start menu, right-click **Windows PowerShell** and select **Run as administrator**.</span></span>

2. <span data-ttu-id="d0827-211">다음 cmdlet을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="d0827-211">Type the following cmdlet:</span></span>

    ```PowerShell
    Set-MpPreference -AttackSurfaceReductionRules_Ids <rule ID> -AttackSurfaceReductionRules_Actions Enabled
    ```

    <span data-ttu-id="d0827-212">감사 모드에서 ASR 규칙을 사용하도록 설정하려면 다음 cmdlet을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="d0827-212">To enable ASR rules in audit mode, use the following cmdlet:</span></span>

    ```PowerShell
    Add-MpPreference -AttackSurfaceReductionRules_Ids <rule ID> -AttackSurfaceReductionRules_Actions AuditMode
    ```

    <span data-ttu-id="d0827-213">경고 모드에서 ASR 규칙을 사용하도록 설정하려면 다음 cmdlet을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="d0827-213">To enable ASR rules in warn mode, use the following cmdlet:</span></span>

    ```PowerShell
    Add-MpPreference -AttackSurfaceReductionRules_Ids <rule ID> -AttackSurfaceReductionRules_Actions Warn
    ```

    <span data-ttu-id="d0827-214">ASR 규칙을 끄기 위해 다음 cmdlet을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="d0827-214">To turn off ASR rules, use the following cmdlet:</span></span>

    ```PowerShell
    Add-MpPreference -AttackSurfaceReductionRules_Ids <rule ID> -AttackSurfaceReductionRules_Actions Disabled
    ```

    > [!IMPORTANT]
    > <span data-ttu-id="d0827-215">각 규칙에 대해 개별적으로 상태를 지정해야 하지만 규칙과 상태를 콤보로 구분된 목록에서 결합할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d0827-215">You must specify the state individually for each rule, but you can combine rules and states in a comma-separated list.</span></span>
    >
    > <span data-ttu-id="d0827-216">다음 예제에서는 처음 두 규칙을 사용하도록 설정하고, 세 번째 규칙은 사용하지 않도록 설정하고, 네 번째 규칙은 감사 모드에서 사용하도록 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="d0827-216">In the following example, the first two rules will be enabled, the third rule will be disabled, and the fourth rule will be enabled in audit mode:</span></span>
    >
    > ```PowerShell
    > Set-MpPreference -AttackSurfaceReductionRules_Ids <rule ID 1>,<rule ID 2>,<rule ID 3>,<rule ID 4> -AttackSurfaceReductionRules_Actions Enabled, Enabled, Disabled, AuditMode
    > ```

    <span data-ttu-id="d0827-217">PowerShell 동사로 기존 목록에 새 규칙을 `Add-MpPreference` 추가할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d0827-217">You can also use the `Add-MpPreference` PowerShell verb to add new rules to the existing list.</span></span>

    > [!WARNING]
    > <span data-ttu-id="d0827-218">`Set-MpPreference` 는 항상 기존 규칙 집합을 덮어 덮어 들이게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d0827-218">`Set-MpPreference` will always overwrite the existing set of rules.</span></span> <span data-ttu-id="d0827-219">기존 집합에 추가하려는 경우 대신 `Add-MpPreference` 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="d0827-219">If you want to add to the existing set, use `Add-MpPreference` instead.</span></span>
    > <span data-ttu-id="d0827-220">를 사용하여 규칙 및 규칙의 현재 상태 목록을 얻을 수 `Get-MpPreference` 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d0827-220">You can obtain a list of rules and their current state by using `Get-MpPreference`.</span></span>

3. <span data-ttu-id="d0827-221">ASR 규칙에서 파일 및 폴더를 제외하려면 다음 cmdlet을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="d0827-221">To exclude files and folders from ASR rules, use the following cmdlet:</span></span>

    ```PowerShell
    Add-MpPreference -AttackSurfaceReductionOnlyExclusions "<fully qualified path or resource>"
    ```

    <span data-ttu-id="d0827-222">계속 사용하여 목록에 파일 및 `Add-MpPreference -AttackSurfaceReductionOnlyExclusions` 폴더를 더 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="d0827-222">Continue to use `Add-MpPreference -AttackSurfaceReductionOnlyExclusions` to add more files and folders to the list.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="d0827-223">목록에 `Add-MpPreference` 앱을 추가하거나 추가하는 데 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d0827-223">Use `Add-MpPreference` to append or add apps to the list.</span></span> <span data-ttu-id="d0827-224">`Set-MpPreference`cmdlet을 사용하여 기존 목록을 덮어 습니다.</span><span class="sxs-lookup"><span data-stu-id="d0827-224">Using the `Set-MpPreference` cmdlet will overwrite the existing list.</span></span>

## <a name="related-articles"></a><span data-ttu-id="d0827-225">관련 문서</span><span class="sxs-lookup"><span data-stu-id="d0827-225">Related articles</span></span>

- [<span data-ttu-id="d0827-226">공격 표면 감소 규칙을 사용하여 공격 표면 감소</span><span class="sxs-lookup"><span data-stu-id="d0827-226">Reduce attack surfaces with attack surface reduction rules</span></span>](attack-surface-reduction.md)

- [<span data-ttu-id="d0827-227">공격 표면 감소 평가</span><span class="sxs-lookup"><span data-stu-id="d0827-227">Evaluate attack surface reduction</span></span>](evaluate-attack-surface-reduction.md)

- [<span data-ttu-id="d0827-228">공격 표면 감소 FAQ</span><span class="sxs-lookup"><span data-stu-id="d0827-228">Attack surface reduction FAQ</span></span>](attack-surface-reduction.md)
