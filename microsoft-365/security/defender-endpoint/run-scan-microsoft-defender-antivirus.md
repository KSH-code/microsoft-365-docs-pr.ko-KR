---
title: 조직에서 요구 시 검사 실행 및 Microsoft Defender 바이러스 백신
description: PowerShell, Windows 관리 계측을 사용하여 또는 Windows 보안 끝점에서 개별적으로 검사 실행 및 구성
keywords: 검사, on-demand, dos, intune, instant scan
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: normal
ms.topic: article
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 06/10/2021
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.openlocfilehash: b2910f9fe1c49178b8696d1a421248156b0fc4c2
ms.sourcegitcommit: be929f79751c0c52dfa6bd98a854432a0c63faf0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/14/2021
ms.locfileid: "52925734"
---
# <a name="configure-and-run-on-demand-microsoft-defender-antivirus-scans"></a><span data-ttu-id="0064d-104">요청 기반 Microsoft Defender 바이러스 백신 검사 구성 및 실행</span><span class="sxs-lookup"><span data-stu-id="0064d-104">Configure and run on-demand Microsoft Defender Antivirus scans</span></span>

<span data-ttu-id="0064d-105">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="0064d-105">**Applies to:**</span></span>

- [<span data-ttu-id="0064d-106">엔드포인트용 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="0064d-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

<span data-ttu-id="0064d-107">개별 끝점에서 필요한 경우 검색을 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0064d-107">You can run an on-demand scan on individual endpoints.</span></span> <span data-ttu-id="0064d-108">이러한 검사는 즉시 시작하며 위치 또는 유형과 같은 검사에 대한 매개 변수를 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0064d-108">These scans will start immediately, and you can define parameters for the scan, such as the location or type.</span></span> <span data-ttu-id="0064d-109">검색을 실행할 때 빠른 검사, 전체 검사 및 사용자 지정 검사의 세 가지 유형 중에서 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0064d-109">When you run a scan, you can choose from among three types: Quick scan, full scan, and custom scan.</span></span> <span data-ttu-id="0064d-110">대부분의 경우 빠른 검색을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="0064d-110">In most cases, use a quick scan.</span></span> <span data-ttu-id="0064d-111">빠른 검사는 레지스트리 키 및 알려진 시작 폴더와 같이 시스템으로 시작하기 위해 등록된 맬웨어가 있을 수 있는 모든 Windows 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="0064d-111">A quick scan looks at all the locations where there could be malware registered to start with the system, such as registry keys and known Windows startup folders.</span></span> 

<span data-ttu-id="0064d-112">파일을 열고 닫을 때 그리고 사용자가 폴더를 탐색할 때마다 파일을 검토하는 실시간 보호와 함께 빠른 검사가 시스템 및 커널 수준 맬웨어로 시작되는 맬웨어를 강력한 보호하는 데 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0064d-112">Combined with always-on, real-time protection, which reviews files when they are opened and closed, and whenever a user navigates to a folder, a quick scan helps provide strong protection against malware that starts with the system and kernel-level malware.</span></span> <span data-ttu-id="0064d-113">대부분의 경우 빠른 검사만으로 충분하며 예약된 검사 또는 요구 시 검사에 권장되는 옵션입니다.</span><span class="sxs-lookup"><span data-stu-id="0064d-113">In most cases, a quick scan is sufficient and is the recommended option for scheduled or on-demand scans.</span></span>  <span data-ttu-id="0064d-114">[검사 유형에 대해 자세히 알아보시다.](schedule-antivirus-scans.md#quick-scan-full-scan-and-custom-scan)</span><span class="sxs-lookup"><span data-stu-id="0064d-114">[Learn more about scan types](schedule-antivirus-scans.md#quick-scan-full-scan-and-custom-scan).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="0064d-115">Microsoft Defender 바이러스 백신 로컬 검색을 수행할 때 [LocalSystem](/windows/win32/services/localsystem-account) 계정의 컨텍스트에서 실행됩니다.</span><span class="sxs-lookup"><span data-stu-id="0064d-115">Microsoft Defender Antivirus runs in the context of the [LocalSystem](/windows/win32/services/localsystem-account) account when performing a local scan.</span></span> <span data-ttu-id="0064d-116">네트워크 검사의 경우 디바이스 계정의 컨텍스트를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="0064d-116">For network scans, it uses the context of the device account.</span></span> <span data-ttu-id="0064d-117">도메인 장치 계정에 공유에 액세스할 수 있는 적절한 권한이 없는 경우 검사가 작동하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="0064d-117">If the domain device account doesn't have appropriate permissions to access the share, the scan won't work.</span></span> <span data-ttu-id="0064d-118">디바이스에 액세스 네트워크 공유에 대한 사용 권한이 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="0064d-118">Ensure that the device has permissions to the access network share.</span></span>

## <a name="use-microsoft-endpoint-manager-to-run-a-scan"></a><span data-ttu-id="0064d-119">검색 Microsoft Endpoint Manager 실행</span><span class="sxs-lookup"><span data-stu-id="0064d-119">Use Microsoft Endpoint Manager to run a scan</span></span>

1. <span data-ttu-id="0064d-120">Microsoft Endpoint Manager 관리 센터()로 [https://endpoint.microsoft.com](https://endpoint.microsoft.com) 이동하여 로그인합니다.</span><span class="sxs-lookup"><span data-stu-id="0064d-120">Go to the Microsoft Endpoint Manager admin center ([https://endpoint.microsoft.com](https://endpoint.microsoft.com)) and log in.</span></span>

2. <span data-ttu-id="0064d-121">끝점 **보안 바이러스 백신**  >  **을 선택 합니다.**</span><span class="sxs-lookup"><span data-stu-id="0064d-121">Choose **Endpoint security** > **Antivirus**.</span></span>

3. <span data-ttu-id="0064d-122">탭 목록에서 Windows 10 **끝점을 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="0064d-122">In the list of tabs, select **Windows 10 unhealthy endpoints**.</span></span>

4. <span data-ttu-id="0064d-123">제공된 작업 목록에서  빠른 검사(권장) 또는 전체 검사 **를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="0064d-123">From the list of actions provided, select **Quick Scan** (recommended) or **Full Scan**.</span></span>

<span data-ttu-id="0064d-124">[![이미지 ](images/mem-antivirus-scan-on-demand.png)](images/mem-antivirus-scan-on-demand.png#lightbox)</span><span class="sxs-lookup"><span data-stu-id="0064d-124">[ ![IMAGE](images/mem-antivirus-scan-on-demand.png) ](images/mem-antivirus-scan-on-demand.png#lightbox)</span></span>

> [!TIP]
> <span data-ttu-id="0064d-125">검색 기능을 사용하여 Microsoft Endpoint Manager 자세한 내용은 맬웨어 방지 및 방화벽 작업: 필요한 경우 검색을 수행하는 [방법을 참조하세요.](/configmgr/protect/deploy-use/endpoint-antimalware-firewall#how-to-perform-an-on-demand-scan-of-computers)</span><span class="sxs-lookup"><span data-stu-id="0064d-125">For more information about using Microsoft Endpoint Manager to run a scan, see [Antimalware and firewall tasks: How to perform an on-demand scan](/configmgr/protect/deploy-use/endpoint-antimalware-firewall#how-to-perform-an-on-demand-scan-of-computers).</span></span>

## <a name="use-the-mpcmdrunexe-command-line-utility-to-run-a-scan"></a><span data-ttu-id="0064d-126">명령줄 mpcmdrun.exe 사용하여 검사 실행</span><span class="sxs-lookup"><span data-stu-id="0064d-126">Use the mpcmdrun.exe command-line utility to run a scan</span></span>

<span data-ttu-id="0064d-127">다음 매개 `-scan` 변수를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="0064d-127">Use the following `-scan` parameter:</span></span>

```console
mpcmdrun.exe -scan -scantype 1
```

<span data-ttu-id="0064d-128">전체 검사 시작 또는 경로 정의를 포함하여 도구 및 추가 매개 변수를 사용하는 방법에 대한 자세한 내용은 mpcmdrun.exe [명령줄](command-line-arguments-microsoft-defender-antivirus.md)도구를 사용하여 Microsoft Defender 바이러스 백신.</span><span class="sxs-lookup"><span data-stu-id="0064d-128">For more information about how to use the tool and additional parameters, including starting a full scan, or defining paths, see [Use the mpcmdrun.exe commandline tool to configure and manage Microsoft Defender Antivirus](command-line-arguments-microsoft-defender-antivirus.md).</span></span>

## <a name="use-microsoft-intune-to-run-a-scan"></a><span data-ttu-id="0064d-129">검색 Microsoft Intune 사용하여 검사 실행</span><span class="sxs-lookup"><span data-stu-id="0064d-129">Use Microsoft Intune to run a scan</span></span>

1. <span data-ttu-id="0064d-130">Microsoft Endpoint Manager 관리 센터()로 [https://endpoint.microsoft.com](https://endpoint.microsoft.com) 이동하여 로그인합니다.</span><span class="sxs-lookup"><span data-stu-id="0064d-130">Go to the Microsoft Endpoint Manager admin center ([https://endpoint.microsoft.com](https://endpoint.microsoft.com)) and log in.</span></span>

2. <span data-ttu-id="0064d-131">사이드바에서 장치 **모든** 장치를 선택하고 스캔할  >   장치를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="0064d-131">From the sidebar, select **Devices** > **All Devices** and choose the device you want to scan.</span></span>

3. <span data-ttu-id="0064d-132">**...를 선택합니다. 추가 .**</span><span class="sxs-lookup"><span data-stu-id="0064d-132">Select **...More**.</span></span> <span data-ttu-id="0064d-133">옵션에서 빠른  검사(권장) 또는 전체 **검사 를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="0064d-133">From the options, select **Quick Scan** (recommended) or **Full Scan**.</span></span>

## <a name="use-the-windows-security-app-to-run-a-scan"></a><span data-ttu-id="0064d-134">앱 Windows 보안 사용하여 검사 실행</span><span class="sxs-lookup"><span data-stu-id="0064d-134">Use the Windows Security app to run a scan</span></span>

<span data-ttu-id="0064d-135">개별 [끝점에서](microsoft-defender-security-center-antivirus.md) Windows 보안 실행에 대한 지침은 Windows 보안 앱에서 검사 실행을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="0064d-135">See [Run a scan in the Windows Security app](microsoft-defender-security-center-antivirus.md) for instructions on running a scan on individual endpoints.</span></span>

## <a name="use-powershell-cmdlets-to-run-a-scan"></a><span data-ttu-id="0064d-136">PowerShell cmdlet을 사용하여 검사 실행</span><span class="sxs-lookup"><span data-stu-id="0064d-136">Use PowerShell cmdlets to run a scan</span></span>

<span data-ttu-id="0064d-137">다음 cmdlet을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="0064d-137">Use the following cmdlet:</span></span>

```PowerShell
Start-MpScan
```

<span data-ttu-id="0064d-138">PowerShell과 함께 PowerShell을 사용하는 방법에 대한 자세한 Microsoft Defender 바이러스 백신 [PowerShell cmdlet을](use-powershell-cmdlets-microsoft-defender-antivirus.md) 사용하여 Microsoft Defender 바이러스 백신 [및 Defender cmdlet](/powershell/module/defender/)구성 및 실행을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="0064d-138">For more information on how to use PowerShell with Microsoft Defender Antivirus, see [Use PowerShell cmdlets to configure and run Microsoft Defender Antivirus](use-powershell-cmdlets-microsoft-defender-antivirus.md) and [Defender cmdlets](/powershell/module/defender/).</span></span>

## <a name="use-windows-management-instruction-wmi-to-run-a-scan"></a><span data-ttu-id="0064d-139">WMI(Windows 관리 명령)를 사용하여 검사 실행</span><span class="sxs-lookup"><span data-stu-id="0064d-139">Use Windows Management Instruction (WMI) to run a scan</span></span>

<span data-ttu-id="0064d-140">이 [ **클래스의 Start**](/previous-versions/windows/desktop/defender/start-msft-mpscan) 메서드를 MSFT_MpScan **사용합니다.**</span><span class="sxs-lookup"><span data-stu-id="0064d-140">Use the [**Start** method](/previous-versions/windows/desktop/defender/start-msft-mpscan) of the **MSFT_MpScan** class.</span></span>

<span data-ttu-id="0064d-141">허용되는 매개 변수에 대한 자세한 내용은 [WMIv2](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal) API Windows Defender 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="0064d-141">For more information about which parameters are allowed, see [Windows Defender WMIv2 APIs](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)</span></span>

