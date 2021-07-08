---
title: Windows Defender 바이러스 백신
description: Microsoft Defender 바이러스 백신, 내장된 맬웨어 및 바이러스 방지 기능을 관리, 구성 및 사용하는 방법에 대해 알아 보세요.
keywords: Microsoft Defender Antivirus, windows defender, antimalware, scep, system center endpoint protection, system center configuration manager, virus, malware, threat, detection, protection, security
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: Priority
ms.topic: article
author: denisebmsft
ms.author: deniseb
ms.reviewer: mkaminska
manager: dansimp
ms.custom: nextgen
ms.technology: mde
ms.openlocfilehash: ceaf694d8b81e6b06ffe74efc4ad3d4d73471752
ms.sourcegitcommit: b0f464b6300e2977ed51395473a6b2e02b18fc9e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/07/2021
ms.locfileid: "53323053"
---
# <a name="microsoft-defender-antivirus-in-windows"></a><span data-ttu-id="c2a16-104">Windows의 Microsoft Defender 바이러스 백신</span><span class="sxs-lookup"><span data-stu-id="c2a16-104">Microsoft Defender Antivirus in Windows</span></span>

<span data-ttu-id="c2a16-105">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="c2a16-105">**Applies to:**</span></span>

- [<span data-ttu-id="c2a16-106">엔드포인트용 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="c2a16-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

<span data-ttu-id="c2a16-107">Windows Defender 바이러스 백신은 엔드포인트용 Microsoft Defender의 차세대 보호 구성 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="c2a16-107">Microsoft Defender Antivirus is a major component of your next-generation protection in Microsoft Defender for Endpoint.</span></span> <span data-ttu-id="c2a16-108">이 기능은 기계 학습, 빅데이터 분석, 심층 위협 방지 연구, Microsoft 클라우드 인프라를 결합하여 조직의 장치(또는 엔드포인트)를 보호합니다.</span><span class="sxs-lookup"><span data-stu-id="c2a16-108">This protection brings together machine learning, big-data analysis, in-depth threat resistance research, and the Microsoft cloud infrastructure to protect devices (or endpoints) in your organization.</span></span> <span data-ttu-id="c2a16-109">Microsoft Defender 바이러스 백신은 Windows에 기본 제공되며, 엔드포인트용 Microsoft Defender와 함께 작동하여 장치 및 클라우드를 보호합니다.</span><span class="sxs-lookup"><span data-stu-id="c2a16-109">Microsoft Defender Antivirus is built into Windows, and it works with Microsoft Defender for Endpoint to provide protection on your device and in the cloud.</span></span> 

## <a name="compatibility-with-other-antivirus-products"></a><span data-ttu-id="c2a16-110">다른 바이러스 백신 제품과의 호환성</span><span class="sxs-lookup"><span data-stu-id="c2a16-110">Compatibility with other antivirus products</span></span>

<span data-ttu-id="c2a16-111">장치에서 타사 바이러스 백신/맬웨어 방지 제품을 사용하는 경우 타사 바이러스 백신 솔루션과 함께 수동 모드에서 Microsoft Defender 바이러스 백신을 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c2a16-111">If you're using a non-Microsoft antivirus/antimalware product on your device, you might be able to run Microsoft Defender Antivirus in passive mode alongside the non-Microsoft antivirus solution.</span></span> <span data-ttu-id="c2a16-112">사용되는 운영 체제 및 장치가 엔드포인트용 Defender에 온보딩되었는지 여부에 따라 달라집니다.</span><span class="sxs-lookup"><span data-stu-id="c2a16-112">It depends on the operating system used and whether your device is onboarded to Defender for Endpoint.</span></span> <span data-ttu-id="c2a16-113">자세한 내용은 [Microsoft Defender 바이러스 백신 호환성](microsoft-defender-antivirus-compatibility.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="c2a16-113">To learn more, see [Microsoft Defender Antivirus compatibility](microsoft-defender-antivirus-compatibility.md).</span></span>

## <a name="comparing-active-mode-passive-mode-and-disabled-mode"></a><span data-ttu-id="c2a16-114">활성 모드, 수동 모드 및 사용 중지 모드 비교</span><span class="sxs-lookup"><span data-stu-id="c2a16-114">Comparing active mode, passive mode, and disabled mode</span></span>

<span data-ttu-id="c2a16-115">다음 표에서는 Microsoft Defender 바이러스 백신 활성 모드, 수동 모드 또는 사용 중지 상태일 때 예상되는 사항에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="c2a16-115">The following table describes what to expect when Microsoft Defender Antivirus is in active mode, passive mode, or disabled.</span></span>

| <span data-ttu-id="c2a16-116">모드</span><span class="sxs-lookup"><span data-stu-id="c2a16-116">Mode</span></span>  | <span data-ttu-id="c2a16-117">발생 작업</span><span class="sxs-lookup"><span data-stu-id="c2a16-117">What happens</span></span>  |
|---------|---------|
| <span data-ttu-id="c2a16-118">활성 모드</span><span class="sxs-lookup"><span data-stu-id="c2a16-118">Active mode</span></span> | <span data-ttu-id="c2a16-119">활성 모드에서 Microsoft Defender 바이러스 백신은 장치의 기본 바이러스 백신 앱으로 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="c2a16-119">In active mode, Microsoft Defender Antivirus is used as the primary antivirus app on the device.</span></span> <span data-ttu-id="c2a16-120">파일이 스캔되고, 위협이 수정되고, 검색된 위협이 조직의 보안 보고서 및 Windows 보안 앱에 나열됩니다.</span><span class="sxs-lookup"><span data-stu-id="c2a16-120">Files are scanned, threats are remediated, and detected threats are listed in your organization's security reports and in your Windows Security app.</span></span> |
| <span data-ttu-id="c2a16-121">수동 모드</span><span class="sxs-lookup"><span data-stu-id="c2a16-121">Passive mode</span></span> | <span data-ttu-id="c2a16-122">수동 모드에서 Microsoft Defender 바이러스 백신은 장치의 기본 바이러스 백신 앱으로 사용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c2a16-122">In passive mode, Microsoft Defender Antivirus is not used as the primary antivirus app on the device.</span></span> <span data-ttu-id="c2a16-123">파일이 스캔되고 검색된 위협이 보고되지만 위협이 Microsoft Defender 바이러스 백신에 의해 수정되지는 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c2a16-123">Files are scanned, and detected threats are reported, but threats are not remediated by Microsoft Defender Antivirus.</span></span>   |
| <span data-ttu-id="c2a16-124">사용 중지 또는 제거됨</span><span class="sxs-lookup"><span data-stu-id="c2a16-124">Disabled or uninstalled</span></span>  | <span data-ttu-id="c2a16-125">사용 중지하거나 제거하면 Microsoft Defender 바이러스 백신이 사용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c2a16-125">When disabled or uninstalled, Microsoft Defender Antivirus is not used.</span></span> <span data-ttu-id="c2a16-126">파일이 스캔되지 않으며 위협은 수정되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c2a16-126">Files are not scanned, and threats are not remediated.</span></span> <span data-ttu-id="c2a16-127">일반적으로 Microsoft Defender 바이러스 백신을 사용 중지하거나 제거하는 것은 권장되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c2a16-127">In general, we do not recommend disabling or uninstalling Microsoft Defender Antivirus.</span></span>  |

<span data-ttu-id="c2a16-128">자세한 내용은 [Microsoft Defender 바이러스 백신 호환성](microsoft-defender-antivirus-compatibility.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="c2a16-128">To learn more, see [Microsoft Defender Antivirus compatibility](microsoft-defender-antivirus-compatibility.md).</span></span>

## <a name="check-the-state-of-microsoft-defender-antivirus-on-your-device"></a><span data-ttu-id="c2a16-129">장치에서 Microsoft Defender 바이러스 백신 상태 확인</span><span class="sxs-lookup"><span data-stu-id="c2a16-129">Check the state of Microsoft Defender Antivirus on your device</span></span>

<span data-ttu-id="c2a16-130">장치에서 Microsoft Defender 바이러스 백신 상태를 확인하려면 Windows 보안 앱 또는 Windows PowerShell 같은 여러 방법 중 하나를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c2a16-130">If you want to check the state of Microsoft Defender Antivirus on your device, you can use one of several methods, such as the Windows Security app or Windows PowerShell.</span></span>

### <a name="use-the-windows-security-app-to-check-status-of-microsoft-defender-antivirus"></a><span data-ttu-id="c2a16-131">Windows 보안 앱을 사용하여 Microsoft Defender 바이러스 백신 상태 확인</span><span class="sxs-lookup"><span data-stu-id="c2a16-131">Use the Windows Security app to check status of Microsoft Defender Antivirus</span></span>

1. <span data-ttu-id="c2a16-132">Windows 장치에서 시작 메뉴를 선택하고 `Security` 입력을 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="c2a16-132">On your Windows device, select the Start menu, and begin typing `Security`.</span></span> <span data-ttu-id="c2a16-133">그런 다음 결과에서 Windows 보안 앱을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="c2a16-133">Then open the Windows Security app in the results.</span></span>

2. <span data-ttu-id="c2a16-134">**바이러스 및 위협 방지** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="c2a16-134">Select **Virus & threat protection**.</span></span>

3. <span data-ttu-id="c2a16-135">**바이러스 및 위협 방지 설정** 에서 **설정 관리** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="c2a16-135">Under **Virus & threat protection settings**, choose **Manage settings**.</span></span>

<span data-ttu-id="c2a16-136">설정 페이지에 바이러스 백신/맬웨어 방지 솔루션의 이름이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="c2a16-136">You'll see the name of your antivirus/antimalware solution on the settings page.</span></span>

### <a name="use-powershell-to-check-status-of-microsoft-defender-antivirus"></a><span data-ttu-id="c2a16-137">PowerShell을 사용하여 Microsoft Defender 바이러스 백신 상태 확인</span><span class="sxs-lookup"><span data-stu-id="c2a16-137">Use PowerShell to check status of Microsoft Defender Antivirus</span></span>

1. <span data-ttu-id="c2a16-138">시작 메뉴를 선택하고 `PowerShell` 입력을 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="c2a16-138">Select the Start menu, and begin typing `PowerShell`.</span></span> <span data-ttu-id="c2a16-139">그런 다음 결과에서 Windows PowerShell을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="c2a16-139">Then open Windows PowerShell in the results.</span></span>

2. <span data-ttu-id="c2a16-140">`Get-MpComputerStatus`를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="c2a16-140">Type `Get-MpComputerStatus`.</span></span>

3. <span data-ttu-id="c2a16-141">결과 목록에서 **AMRunningMode** 행을 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="c2a16-141">In the list of results, look at the **AMRunningMode** row.</span></span>

   - <span data-ttu-id="c2a16-142">**정상** 은 Microsoft Defender 바이러스 백신이 활성 모드에서 실행 중임을 의미합니다.</span><span class="sxs-lookup"><span data-stu-id="c2a16-142">**Normal** means Microsoft Defender Antivirus is running in active mode.</span></span>
   - <span data-ttu-id="c2a16-143">**수동 모드** 는 Microsoft Defender 바이러스 백신이 실행 중이지만 장치의 기본 바이러스 백신/맬웨어 방지 제품이 아님을 의미합니다.</span><span class="sxs-lookup"><span data-stu-id="c2a16-143">**Passive mode** means Microsoft Defender Antivirus running, but is not the primary antivirus/antimalware product on your device.</span></span>
   - <span data-ttu-id="c2a16-144">**EDR 차단 모드** 는 Microsoft Defender 바이러스 백신이 실행 중이며, "차단 모드의 EDR"이라는 엔드포인트용 Microsoft Defender 기능이 사용됨을 의미합니다.</span><span class="sxs-lookup"><span data-stu-id="c2a16-144">**EDR Block Mode** means Microsoft Defender Antivirus is running and a capability in Microsoft Defender for Endpoint that is called "EDR in block mode" is enabled.</span></span> <span data-ttu-id="c2a16-145">([차단 모드의 EDR(엔드포인트 감지 및 대응)](edr-in-block-mode.md)을 참조하세요.)</span><span class="sxs-lookup"><span data-stu-id="c2a16-145">(See [Endpoint detection and response (EDR) in block mode](edr-in-block-mode.md).)</span></span>
   - <span data-ttu-id="c2a16-146">**SxS 수동 모드** 는 Microsoft Defender 바이러스 백신이 다른 바이러스 백신/맬웨어 방지 제품과 함께 수동 모드로 실행 중이며 장치가 엔드포인트용 Microsoft Defender에 온보딩되지 않음을 의미합니다.</span><span class="sxs-lookup"><span data-stu-id="c2a16-146">**SxS Passive Mode** means Microsoft Defender Antivirus is running in passive mode alongside another antivirus/antimalware product, and your device is not onboarded to Microsoft Defender for Endpoint.</span></span> <span data-ttu-id="c2a16-147">이 경우, Microsoft Defender 바이러스 백신에 대해 제한된 주기적 검사가 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="c2a16-147">In this case, limited periodic scanning is used for Microsoft Defender Antivirus.</span></span> <span data-ttu-id="c2a16-148">자세한 내용은 [Microsoft Defender 바이러스 백신에서 제한된 주기적 검사 사용](limited-periodic-scanning-microsoft-defender-antivirus.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="c2a16-148">To learn more, see [Use limited periodic scanning in Microsoft Defender Antivirus](limited-periodic-scanning-microsoft-defender-antivirus.md).</span></span>

<span data-ttu-id="c2a16-149">Get-MpComputerStatus PowerShell cmdlet에 대한 자세한 내용은 [Get-MpComputerStatus](/powershell/module/defender/get-mpcomputerstatus) 참조 문서를 확인하세요.</span><span class="sxs-lookup"><span data-stu-id="c2a16-149">To learn more about the Get-MpComputerStatus PowerShell cmdlet, see the reference article [Get-MpComputerStatus](/powershell/module/defender/get-mpcomputerstatus).</span></span>

## <a name="get-your-antivirusantimalware-platform-updates"></a><span data-ttu-id="c2a16-150">바이러스 백신 및 맬웨어 방지 업데이트 받기</span><span class="sxs-lookup"><span data-stu-id="c2a16-150">Get your antivirus/antimalware platform updates</span></span>

<span data-ttu-id="c2a16-151">Microsoft Defender 바이러스 백신 또는 모든 바이러스 백신/맬웨어 방지 솔루션을 최신 상태로 유지하는 것이 중요합니다.</span><span class="sxs-lookup"><span data-stu-id="c2a16-151">It's important to keep Microsoft Defender Antivirus, or any antivirus/antimalware solution, up to date.</span></span> <span data-ttu-id="c2a16-152">Microsoft는 장치가 새로운 맬웨어 및 공격 기술로부터 보호할 수 있는 최신 기술을 갖추도록 정기적인 업데이트를 릴리스합니다.</span><span class="sxs-lookup"><span data-stu-id="c2a16-152">Microsoft releases regular updates to help ensure that your devices have the latest technology to protect against new malware and attack techniques.</span></span> <span data-ttu-id="c2a16-153">자세한 내용은 [Microsoft Defender 바이러스 백신 업데이트 관리 및 기준 적용](manage-updates-baselines-microsoft-defender-antivirus.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="c2a16-153">To learn more, see [Manage Microsoft Defender Antivirus updates and apply baselines](manage-updates-baselines-microsoft-defender-antivirus.md).</span></span> 

## <a name="see-also"></a><span data-ttu-id="c2a16-154">참고 항목</span><span class="sxs-lookup"><span data-stu-id="c2a16-154">See also</span></span>

- [<span data-ttu-id="c2a16-155">Windows Server의 Microsoft Defender 바이러스 백신</span><span class="sxs-lookup"><span data-stu-id="c2a16-155">Microsoft Defender Antivirus on Windows Server</span></span>](microsoft-defender-antivirus-on-windows-server.md)
- [<span data-ttu-id="c2a16-156">Microsoft Defender 바이러스 백신 관리 및 구성</span><span class="sxs-lookup"><span data-stu-id="c2a16-156">Microsoft Defender Antivirus management and configuration</span></span>](configuration-management-reference-microsoft-defender-antivirus.md)
- [<span data-ttu-id="c2a16-157">Microsoft Defender 바이러스 백신 평가</span><span class="sxs-lookup"><span data-stu-id="c2a16-157">Evaluate Microsoft Defender Antivirus protection</span></span>](evaluate-microsoft-defender-antivirus.md)
