---
title: Microsoft Defender 오프라인 Windows 10
description: 앱의 Microsoft Defender 오프라인 바로 사용할 Windows Defender 바이러스 백신 있습니다. 네트워크에서 배포되는 방법을 관리할 수도 있습니다.
keywords: 검사, defender, 오프라인
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: Normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.topic: article
ms.openlocfilehash: b2a6ee7c3f3ea2fb31b31d2f1db178bfd9847fbc
ms.sourcegitcommit: bbad1938b6661d4a6bca99f235c44e521b1fb662
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/18/2021
ms.locfileid: "53007479"
---
# <a name="run-and-review-the-results-of-a-microsoft-defender-offline-scan"></a><span data-ttu-id="28782-105">Microsoft Defender 오프라인 검사의 결과 실행 및 검토</span><span class="sxs-lookup"><span data-stu-id="28782-105">Run and review the results of a Microsoft Defender Offline scan</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="28782-106">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="28782-106">**Applies to:**</span></span>

- [<span data-ttu-id="28782-107">엔드포인트용 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="28782-107">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

<span data-ttu-id="28782-108">Microsoft Defender 오프라인 신뢰할 수 있는 환경에서 검색을 부팅하고 실행할 수 있는 맬웨어 방지 검사 도구입니다.</span><span class="sxs-lookup"><span data-stu-id="28782-108">Microsoft Defender Offline is an antimalware scanning tool that lets you boot and run a scan from a trusted environment.</span></span> <span data-ttu-id="28782-109">검사는 일반 Windows 커널 외부에서 실행되어 MBR(마스터 부트 레코드)을 감염 또는 덮어 Windows 셸을 무시하려는 맬웨어를 대상으로 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="28782-109">The scan runs from outside the normal Windows kernel so it can target malware that attempts to bypass the Windows shell, such as viruses and rootkits that infect or overwrite the master boot record (MBR).</span></span>

<span data-ttu-id="28782-110">맬웨어 Microsoft Defender 오프라인 의심하거나 맬웨어 발생 후 끝점을 완전히 정리하려는 경우 이 방법을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="28782-110">You can use Microsoft Defender Offline if you suspect a malware infection, or you want to confirm a thorough clean of the endpoint after a malware outbreak.</span></span>

<span data-ttu-id="28782-111">이 Windows 10 앱에서 Microsoft Defender 오프라인 클릭 한 번으로 실행할 [Windows 보안 있습니다.](microsoft-defender-security-center-antivirus.md)</span><span class="sxs-lookup"><span data-stu-id="28782-111">In Windows 10, Microsoft Defender Offline can be run with one click directly from the [Windows Security app](microsoft-defender-security-center-antivirus.md).</span></span> <span data-ttu-id="28782-112">이전 버전의 Windows 사용자는 부팅 가능한 미디어에 Microsoft Defender 오프라인 끝점을 다시 시작하고 부팅 가능한 미디어를 로드해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="28782-112">In previous versions of Windows, a user had to install Microsoft Defender Offline to bootable media, restart the endpoint, and load the bootable media.</span></span>

## <a name="prerequisites-and-requirements"></a><span data-ttu-id="28782-113">선행 조건 및 요구 사항</span><span class="sxs-lookup"><span data-stu-id="28782-113">prerequisites and requirements</span></span>

<span data-ttu-id="28782-114">Microsoft Defender 오프라인 Windows 10 하드웨어 요구 사항이 Windows 10.</span><span class="sxs-lookup"><span data-stu-id="28782-114">Microsoft Defender Offline in Windows 10 has the same hardware requirements as Windows 10.</span></span> 

<span data-ttu-id="28782-115">요구 사항에 대한 Windows 10 내용은 다음 항목을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="28782-115">For more information about Windows 10 requirements, see the following topics:</span></span>

- [<span data-ttu-id="28782-116">최소 하드웨어 요구 사항</span><span class="sxs-lookup"><span data-stu-id="28782-116">Minimum hardware requirements</span></span>](/windows-hardware/design/minimum/minimum-hardware-requirements-overview)

- [<span data-ttu-id="28782-117">하드웨어 구성 요소 지침</span><span class="sxs-lookup"><span data-stu-id="28782-117">Hardware component guidelines</span></span>](/windows-hardware/design/component-guidelines/components)

> [!NOTE]
> <span data-ttu-id="28782-118">Microsoft Defender 오프라인 프로세서가 있는 컴퓨터나 ARM 서버 주식 보관 Windows 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="28782-118">Microsoft Defender Offline is not supported on machines with ARM processors, or on Windows Server Stock Keeping Units.</span></span>

<span data-ttu-id="28782-119">끝점에서 Microsoft Defender 오프라인 관리자 권한으로 로그인해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="28782-119">To run Microsoft Defender Offline from the endpoint, the user must be logged in with administrator privileges.</span></span>
 
## <a name="microsoft-defender-offline-updates"></a><span data-ttu-id="28782-120">Microsoft Defender 오프라인 업데이트</span><span class="sxs-lookup"><span data-stu-id="28782-120">Microsoft Defender Offline updates</span></span>

<span data-ttu-id="28782-121">Microsoft Defender 오프라인 끝점에서 사용할 수 있는 최신 보호 업데이트를 사용하는지 확인합니다. 업데이트될 때마다 Windows Defender 바이러스 백신 업데이트됩니다.</span><span class="sxs-lookup"><span data-stu-id="28782-121">Microsoft Defender Offline uses the most recent protection updates available on the endpoint; it's updated whenever Windows Defender Antivirus is updated.</span></span> 

> [!NOTE]
> <span data-ttu-id="28782-122">오프라인 검색을 실행하기 전에 Microsoft Defender AV 보호를 업데이트해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="28782-122">Before running an offline scan, you should attempt to update Microsoft Defender AV protection.</span></span> <span data-ttu-id="28782-123">그룹 정책을 사용하여 강제로 업데이트를 수행하거나 일반적으로 끝점에 업데이트를 배포하거나 에서 수동으로 최신 보호 [업데이트를 다운로드하여](https://www.microsoft.com/security/portal/definitions/adl.aspx)설치할 Microsoft 맬웨어 보호 센터.</span><span class="sxs-lookup"><span data-stu-id="28782-123">You can either force an update with Group Policy or however you normally deploy updates to endpoints, or you can manually download and install the latest protection updates from the [Microsoft Malware Protection Center](https://www.microsoft.com/security/portal/definitions/adl.aspx).</span></span>

<span data-ttu-id="28782-124">자세한 내용은 [보안 Microsoft Defender 바이러스 백신 업데이트](manage-protection-updates-microsoft-defender-antivirus.md) 관리 항목을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="28782-124">See the [Manage Microsoft Defender Antivirus Security intelligence  updates](manage-protection-updates-microsoft-defender-antivirus.md) topic for more information.</span></span>

## <a name="usage-scenarios"></a><span data-ttu-id="28782-125">사용 시나리오</span><span class="sxs-lookup"><span data-stu-id="28782-125">Usage scenarios</span></span>

<span data-ttu-id="28782-126">버전 Windows 10 1607에서 오프라인 검색을 수동으로 강제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="28782-126">In Windows 10, version 1607, you can manually force an offline scan.</span></span> <span data-ttu-id="28782-127">또는 Windows Defender 실행해야 Microsoft Defender 오프라인 경우 끝점에서 사용자에게 메시지를 표시하는 메시지가 표시될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="28782-127">Alternatively, if Windows Defender determines that Microsoft Defender Offline needs to run, it will prompt the user on the endpoint.</span></span> 

<span data-ttu-id="28782-128">오프라인 검사 수행의 필요성은 끝점을 관리하는 데 Microsoft Endpoint Manager 오프라인 검사에도 공개됩니다.</span><span class="sxs-lookup"><span data-stu-id="28782-128">The need to perform an offline scan will also be revealed in Microsoft Endpoint Manager if you're using it to manage your endpoints.</span></span>

<span data-ttu-id="28782-129">프롬프트는 다음과 유사한 알림을 통해 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="28782-129">The prompt can occur via a notification, similar to the following:</span></span>

:::image type="content" source="../../media/notification.png" alt-text="알림 실행 Microsoft Defender 오프라인":::

<span data-ttu-id="28782-131">또한 사용자는 클라이언트 내에서 Windows Defender 알림을 하게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="28782-131">The user will also be notified within the Windows Defender client.</span></span>

<span data-ttu-id="28782-132">Configuration Manager에서 Monitoring > **Overview > Security > Endpoint Protection Status로**> System Center Endpoint Protection 있습니다.</span><span class="sxs-lookup"><span data-stu-id="28782-132">In Configuration Manager, you can identify the status of endpoints by navigating to **Monitoring > Overview > Security > Endpoint Protection Status > System Center Endpoint Protection Status**.</span></span> 

<span data-ttu-id="28782-133">Microsoft Defender 오프라인 검사는 오프라인 검사가  필요하여 맬웨어 수정 **상태 아래에 표시됩니다.**</span><span class="sxs-lookup"><span data-stu-id="28782-133">Microsoft Defender Offline scans are indicated under **Malware remediation status** as **Offline scan required**.</span></span>

:::image type="content" source="../../media/sccm-wdo.png" alt-text="Microsoft Defender 오프라인 검사 필요":::

## <a name="configure-notifications"></a><span data-ttu-id="28782-135">알림 구성</span><span class="sxs-lookup"><span data-stu-id="28782-135">Configure notifications</span></span>

<span data-ttu-id="28782-136">Microsoft Defender 오프라인 알림은 다른 Microsoft Defender AV 알림과 동일한 정책 설정으로 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="28782-136">Microsoft Defender Offline notifications are configured in the same policy setting as other Microsoft Defender AV notifications.</span></span>

<span data-ttu-id="28782-137">앱의 알림에 Windows Defender 끝점에 나타나는 알림 구성 항목을 [참조하세요.](configure-notifications-microsoft-defender-antivirus.md)</span><span class="sxs-lookup"><span data-stu-id="28782-137">For more information about notifications in Windows Defender, see the [Configure the notifications that appear on endpoints](configure-notifications-microsoft-defender-antivirus.md) topic.</span></span>

## <a name="run-a-scan"></a><span data-ttu-id="28782-138">검사 실행</span><span class="sxs-lookup"><span data-stu-id="28782-138">Run a scan</span></span> 

> [!IMPORTANT]
> <span data-ttu-id="28782-139">이 Microsoft Defender 오프라인 파일을 저장하고 실행 중인 프로그램을 종료해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="28782-139">Before you use Microsoft Defender Offline, make sure you save any files and shut down running programs.</span></span> <span data-ttu-id="28782-140">Microsoft Defender 오프라인 검사는 실행하는 데 15분 정도 걸립니다.</span><span class="sxs-lookup"><span data-stu-id="28782-140">The Microsoft Defender Offline scan takes about 15 minutes to run.</span></span> <span data-ttu-id="28782-141">검사가 완료되면 끝점이 다시 시작됩니다.</span><span class="sxs-lookup"><span data-stu-id="28782-141">It will restart the endpoint when the scan is complete.</span></span> <span data-ttu-id="28782-142">검사는 일반적인 운영 환경 외부에서 Windows 수행됩니다.</span><span class="sxs-lookup"><span data-stu-id="28782-142">The scan is performed outside of the usual Windows operating environment.</span></span> <span data-ttu-id="28782-143">사용자 인터페이스는 사용자 인터페이스가 사용자 인터페이스에서 수행한 일반 검사와 Windows Defender.</span><span class="sxs-lookup"><span data-stu-id="28782-143">The user interface will appear different to a normal scan performed by Windows Defender.</span></span> <span data-ttu-id="28782-144">검사가 완료되면 끝점이 다시 시작되어 Windows 로드됩니다.</span><span class="sxs-lookup"><span data-stu-id="28782-144">After the scan is completed, the endpoint will be restarted and Windows will load normally.</span></span>

<span data-ttu-id="28782-145">다음을 사용하여 Microsoft Defender 오프라인 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="28782-145">You can run a Microsoft Defender Offline scan with the following:</span></span>

- <span data-ttu-id="28782-146">PowerShell</span><span class="sxs-lookup"><span data-stu-id="28782-146">PowerShell</span></span>
- <span data-ttu-id="28782-147">WMI(Windows Management Instrumentation)</span><span class="sxs-lookup"><span data-stu-id="28782-147">Windows Management Instrumentation (WMI)</span></span>
- <span data-ttu-id="28782-148">앱 Windows 보안 앱</span><span class="sxs-lookup"><span data-stu-id="28782-148">The Windows Security app</span></span>



### <a name="use-powershell-cmdlets-to-run-an-offline-scan"></a><span data-ttu-id="28782-149">PowerShell cmdlet을 사용하여 오프라인 검사 실행</span><span class="sxs-lookup"><span data-stu-id="28782-149">Use PowerShell cmdlets to run an offline scan</span></span>

<span data-ttu-id="28782-150">다음 cmdlet을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="28782-150">Use the following cmdlets:</span></span>

```PowerShell
Start-MpWDOScan
```

<span data-ttu-id="28782-151">PowerShell과 함께 PowerShell을 사용하는 방법에 대한 자세한 내용은 [PowerShell cmdlet을](use-powershell-cmdlets-microsoft-defender-antivirus.md) 사용하여 Microsoft Defender 바이러스 백신 및 [Defender cmdlet을](/powershell/module/defender/) 구성하고 실행을 Microsoft Defender 바이러스 백신.</span><span class="sxs-lookup"><span data-stu-id="28782-151">See [Use PowerShell cmdlets to configure and run Microsoft Defender Antivirus](use-powershell-cmdlets-microsoft-defender-antivirus.md) and [Defender cmdlets](/powershell/module/defender/) for more information on how to use PowerShell with Microsoft Defender Antivirus.</span></span>

### <a name="use-windows-management-instruction-wmi-to-run-an-offline-scan"></a><span data-ttu-id="28782-152">WMI(Windows 관리 명령)를 사용하여 오프라인 검사 실행</span><span class="sxs-lookup"><span data-stu-id="28782-152">Use Windows Management Instruction (WMI) to run an offline scan</span></span>

<span data-ttu-id="28782-153">MSFT_MpWDOScan [**클래스를**](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) 사용하여 오프라인 검색을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="28782-153">Use the [**MSFT_MpWDOScan**](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) class to run an offline scan.</span></span>

<span data-ttu-id="28782-154">다음 WMI 스크립트 코드는 즉시 Microsoft Defender 오프라인 실행하여 끝점을 다시 시작하고 오프라인 검색을 실행한 다음 다시 시작하여 Windows.</span><span class="sxs-lookup"><span data-stu-id="28782-154">The following WMI script snippet will immediately run a Microsoft Defender Offline scan, which will cause the endpoint to restart, run the offline scan, and then restart and boot into Windows.</span></span>

```console
wmic /namespace:\\root\Microsoft\Windows\Defender path MSFT_MpWDOScan call Start 
```

<span data-ttu-id="28782-155">자세한 내용은 다음을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="28782-155">See the following for more information:</span></span>
- [<span data-ttu-id="28782-156">Windows Defender WMIv2 API</span><span class="sxs-lookup"><span data-stu-id="28782-156">Windows Defender WMIv2 APIs</span></span>](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)


### <a name="use-the-windows-defender-security-app-to-run-an-offline-scan"></a><span data-ttu-id="28782-157">Windows Defender 앱을 사용하여 오프라인 검사 실행</span><span class="sxs-lookup"><span data-stu-id="28782-157">Use the Windows Defender Security app to run an offline scan</span></span>

1. <span data-ttu-id="28782-158">작업 표시줄에서 방패 아이콘을 클릭하거나 **Defender의** 시작 메뉴를 검색하여 Windows 보안 앱을 열 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="28782-158">Open the Windows Security app by clicking the shield icon in the task bar or searching the start menu for **Defender**.</span></span>

2. <span data-ttu-id="28782-159">바이러스 & **보호** 타일(또는 왼쪽 메뉴 표시줄의 방패 아이콘)을 클릭한 다음 **고급 검사 레이블을** 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="28782-159">Click the **Virus & threat protection** tile (or the shield icon on the left menu bar) and then the **Advanced scan** label:</span></span>
    
3. <span data-ttu-id="28782-160">검색 **Microsoft Defender 오프라인 선택하고** 지금 **스캔 을 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="28782-160">Select **Microsoft Defender Offline scan** and click **Scan now**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="28782-161">버전 Windows 10 1607에서는 Windows 설정 Update & security Windows Defender 또는 Windows Defender 클라이언트에서 오프라인 검색을 실행할 수  >    >   있습니다.</span><span class="sxs-lookup"><span data-stu-id="28782-161">In Windows 10, version 1607, the offline scan could be run from under **Windows Settings** > **Update & security** > **Windows Defender** or from the Windows Defender client.</span></span>


## <a name="review-scan-results"></a><span data-ttu-id="28782-162">검사 결과 검토</span><span class="sxs-lookup"><span data-stu-id="28782-162">Review scan results</span></span>

<span data-ttu-id="28782-163">Microsoft Defender 오프라인 검사 결과가 앱의 검사 기록 [섹션에 Windows 보안 표시됩니다.](microsoft-defender-security-center-antivirus.md)</span><span class="sxs-lookup"><span data-stu-id="28782-163">Microsoft Defender Offline scan results will be listed in the [Scan history section of the Windows Security app](microsoft-defender-security-center-antivirus.md).</span></span> 


## <a name="related-articles"></a><span data-ttu-id="28782-164">관련 문서</span><span class="sxs-lookup"><span data-stu-id="28782-164">Related articles</span></span>

- [<span data-ttu-id="28782-165">검사 및 수정 결과 사용자 지정, 시작 및 검토</span><span class="sxs-lookup"><span data-stu-id="28782-165">Customize, initiate, and review the results of scans and remediation</span></span>](customize-run-review-remediate-scans-microsoft-defender-antivirus.md)
- [<span data-ttu-id="28782-166">Windows 10의 Microsoft Defender 바이러스 백신</span><span class="sxs-lookup"><span data-stu-id="28782-166">Microsoft Defender Antivirus in Windows 10</span></span>](microsoft-defender-antivirus-in-windows-10.md)