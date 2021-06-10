---
title: 보안 보호 기능 Microsoft Defender 바이러스 백신 사용 및 구성
description: 동작 모니터링Microsoft Defender 바이러스 백신 학습과 같은 실시간 보호 기능 사용 및 구성
keywords: 바이러스 백신, 실시간 보호, rtp, 기계 학습, 동작 모니터링,추론
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: Normal
author: denisebmsft
ms.author: deniseb
ms.date: 12/16/2019
ms.reviewer: ''
manager: dansimp
ms.custom: nextgen
ms.technology: mde
ms.topic: article
ms.openlocfilehash: 1e39e42b79a2a767473c4473434da249a0d07228
ms.sourcegitcommit: 51b316c23e070ab402a687f927e8fa01cb719c74
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/07/2021
ms.locfileid: "52275135"
---
# <a name="enable-and-configure-microsoft-defender-antivirus-always-on-protection-in-group-policy"></a><span data-ttu-id="77253-104">그룹 정책에서 Microsoft Defender 바이러스 백신 항상 보호 설정 및 구성</span><span class="sxs-lookup"><span data-stu-id="77253-104">Enable and configure Microsoft Defender Antivirus always-on protection in Group Policy</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="77253-105">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="77253-105">**Applies to:**</span></span>

- [<span data-ttu-id="77253-106">엔드포인트용 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="77253-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

<span data-ttu-id="77253-107">항상 보호는 알려진 의심스러운 활동 및 악의적인 활동을 기반으로 맬웨어를 식별하기 위한 실시간 보호, 동작 모니터링 및 추론으로 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="77253-107">Always-on protection consists of real-time protection, behavior monitoring, and heuristics to identify malware based on known suspicious and malicious activities.</span></span>

<span data-ttu-id="77253-108">이러한 활동에는 기존 파일을 비정상적으로 변경하는 프로세스, 자동 시작 레지스트리 키 및 시작 위치(자동 시작 extensibility points 또는 ASEP라고도 하는) 수정 또는 만들기, 파일 시스템 또는 파일 구조에 대한 기타 변경 사항과 같은 이벤트가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="77253-108">These activities include events, such as processes making unusual changes to existing files, modifying or creating automatic startup registry keys and startup locations (also known as auto-start extensibility points, or ASEPs), and other changes to the file system or file structure.</span></span>

## <a name="enable-and-configure-always-on-protection-in-group-policy"></a><span data-ttu-id="77253-109">그룹 정책에서 Always-On 보호 사용 및 구성</span><span class="sxs-lookup"><span data-stu-id="77253-109">Enable and configure always-on protection in Group Policy</span></span>

<span data-ttu-id="77253-110">로컬 그룹 **정책** 편집기를 사용하여 로컬 그룹 정책 편집기를 사용하여 항상 Microsoft Defender 바이러스 백신 설정을 사용하도록 설정하고 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="77253-110">You can use **Local Group Policy Editor** to enable and configure Microsoft Defender Antivirus always-on protection settings.</span></span>

<span data-ttu-id="77253-111">항상 보호를 사용하도록 설정하고 구성하려면</span><span class="sxs-lookup"><span data-stu-id="77253-111">To enable and configure always-on protection:</span></span>

1. <span data-ttu-id="77253-112">로컬 **그룹 정책 편집기를 열습니다.**</span><span class="sxs-lookup"><span data-stu-id="77253-112">Open **Local Group Policy Editor**.</span></span> <span data-ttu-id="77253-113">이렇게 하려면 다음을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="77253-113">To do this:</span></span>  

    1. <span data-ttu-id="77253-114">작업 Windows 10 상자에 **gpedit 를 입력합니다.**</span><span class="sxs-lookup"><span data-stu-id="77253-114">In your Windows 10 taskbar search box, type **gpedit**.</span></span>
    
    1. <span data-ttu-id="77253-115">최상의 **일치 아래에서** 그룹 정책 **편집을 클릭하여** 로컬 그룹 정책 **편집기를 실행합니다.**</span><span class="sxs-lookup"><span data-stu-id="77253-115">Under **Best match**, click **Edit group policy** to launch **Local Group Policy Editor**.</span></span>
    
       ![GPEdit 작업 표시줄 검색 결과](images/gpedit-search.png)

2. <span data-ttu-id="77253-117">로컬 그룹 정책 편집기 왼쪽 창에서 트리를 컴퓨터 구성 관리 템플릿 Windows   >    >  **구성 요소**  >  Microsoft Defender 바이러스 백신.</span><span class="sxs-lookup"><span data-stu-id="77253-117">In the left pane of **Local Group Policy Editor**, expand the tree to **Computer Configuration** > **Administrative Templates** > **Windows Components** > **Microsoft Defender Antivirus**.</span></span> 

3. <span data-ttu-id="77253-118">맬웨어 Microsoft Defender 바이러스 백신 정책 설정을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="77253-118">Configure the Microsoft Defender Antivirus antimalware service policy settings.</span></span> <span data-ttu-id="77253-119">이렇게 하려면 다음을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="77253-119">To do this:</span></span>  

    1. <span data-ttu-id="77253-120">오른쪽의  Microsoft Defender 바이러스 백신 세부 정보 창에서 다음 표에 지정된 정책 설정을 두 번 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="77253-120">In the **Microsoft Defender Antivirus** details pane on right, double-click the policy setting as specified in the following table:</span></span>

       | <span data-ttu-id="77253-121">설정</span><span class="sxs-lookup"><span data-stu-id="77253-121">Setting</span></span> | <span data-ttu-id="77253-122">설명</span><span class="sxs-lookup"><span data-stu-id="77253-122">Description</span></span> | <span data-ttu-id="77253-123">기본 설정</span><span class="sxs-lookup"><span data-stu-id="77253-123">Default setting</span></span> |
       |-----------------------------|------------------------|-------------------------------|
       | <span data-ttu-id="77253-124">맬웨어 방지 서비스가 정상 우선 순위로 시작하도록 허용</span><span class="sxs-lookup"><span data-stu-id="77253-124">Allow antimalware service to startup with normal priority</span></span> | <span data-ttu-id="77253-125">Microsoft Defender 바이러스 백신 엔진의 우선 순위를 낮출 수 있습니다. 시작 프로세스를 최대한 줄이면 경량 배포에 유용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="77253-125">You can lower the priority of the Microsoft Defender Antivirus engine, which may be useful in lightweight deployments where you want to have as lean a startup process as possible.</span></span> <span data-ttu-id="77253-126">이는 끝점에 대한 보호에 영향을 줄 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="77253-126">This may impact protection on the endpoint.</span></span> | <span data-ttu-id="77253-127">사용</span><span class="sxs-lookup"><span data-stu-id="77253-127">Enabled</span></span>
       | <span data-ttu-id="77253-128">맬웨어 방지 서비스가 항상 실행되는 상태로 유지하도록 허용</span><span class="sxs-lookup"><span data-stu-id="77253-128">Allow antimalware service to remain running always</span></span> | <span data-ttu-id="77253-129">보호 업데이트를 사용하지 않도록 설정한 경우 계속 Microsoft Defender 바이러스 백신 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="77253-129">If protection updates have been disabled, you can set Microsoft Defender Antivirus to still run.</span></span> <span data-ttu-id="77253-130">그러면 끝점의 보호 수준이 낮아지게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="77253-130">This lowers the protection on the endpoint.</span></span> | <span data-ttu-id="77253-131">사용 안 함</span><span class="sxs-lookup"><span data-stu-id="77253-131">Disabled</span></span> |
    
    1. <span data-ttu-id="77253-132">설정을 적절하게 구성하고 확인 을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="77253-132">Configure the setting as appropriate, and click **OK**.</span></span>
    
    1. <span data-ttu-id="77253-133">표의 각 설정에 대해 이전 단계를 반복합니다.</span><span class="sxs-lookup"><span data-stu-id="77253-133">Repeat the previous steps for each setting in the table.</span></span>

4. <span data-ttu-id="77253-134">실시간 Microsoft Defender 바이러스 백신 정책 설정을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="77253-134">Configure the Microsoft Defender Antivirus real-time protection policy settings.</span></span> <span data-ttu-id="77253-135">이렇게 하려면 다음을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="77253-135">To do this:</span></span>

    1. <span data-ttu-id="77253-136">세부 **Microsoft Defender 바이러스 백신** 창에서 실시간 보호를 두 **번 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="77253-136">In the **Microsoft Defender Antivirus** details pane, double-click **Real-time Protection**.</span></span> <span data-ttu-id="77253-137">또는 왼쪽 **창의** Microsoft Defender 바이러스 백신 트리에서 실시간 보호 **를 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="77253-137">Or, from the **Microsoft Defender Antivirus** tree on left pane, click **Real-time Protection**.</span></span>
    
    1. <span data-ttu-id="77253-138">오른쪽의  실시간 보호 세부 정보 창에서 다음 표에 지정된 정책 설정을 두 번 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="77253-138">In the **Real-time Protection** details pane on right, double-click the policy setting as specified in the following table:</span></span>  

       | <span data-ttu-id="77253-139">설정</span><span class="sxs-lookup"><span data-stu-id="77253-139">Setting</span></span> | <span data-ttu-id="77253-140">설명</span><span class="sxs-lookup"><span data-stu-id="77253-140">Description</span></span> | <span data-ttu-id="77253-141">기본 설정</span><span class="sxs-lookup"><span data-stu-id="77253-141">Default setting</span></span> |
       |-----------------------------|------------------------|-------------------------------|
       | <span data-ttu-id="77253-142">동작 모니터링 켜기</span><span class="sxs-lookup"><span data-stu-id="77253-142">Turn on behavior monitoring</span></span> | <span data-ttu-id="77253-143">AV 엔진은 파일 프로세스, 파일 및 레지스트리 변경 내용 및 끝점에서 의심스러우고 알려진 악의적인 활동이 있는 기타 이벤트를 모니터링합니다.</span><span class="sxs-lookup"><span data-stu-id="77253-143">The AV engine will monitor file processes, file and registry changes, and other events on your endpoints for suspicious and known malicious activity.</span></span> | <span data-ttu-id="77253-144">사용</span><span class="sxs-lookup"><span data-stu-id="77253-144">Enabled</span></span> |
       | <span data-ttu-id="77253-145">다운로드한 모든 파일 및 첨부 파일 검색</span><span class="sxs-lookup"><span data-stu-id="77253-145">Scan all downloaded files and attachments</span></span> | <span data-ttu-id="77253-146">다운로드한 파일 및 첨부 파일이 자동으로 검색됩니다.</span><span class="sxs-lookup"><span data-stu-id="77253-146">Downloaded files and attachments are automatically scanned.</span></span> <span data-ttu-id="77253-147">이 필터는 다운로드 전과 Windows Defender 검색하는 SmartScreen 필터와 함께 작동됩니다.</span><span class="sxs-lookup"><span data-stu-id="77253-147">This operates in addition to the Windows Defender SmartScreen filter, which scans files before and during downloading.</span></span> | <span data-ttu-id="77253-148">사용</span><span class="sxs-lookup"><span data-stu-id="77253-148">Enabled</span></span> |
       | <span data-ttu-id="77253-149">컴퓨터에서 파일 및 프로그램 활동 모니터링</span><span class="sxs-lookup"><span data-stu-id="77253-149">Monitor file and program activity on your computer</span></span> | <span data-ttu-id="77253-150">Microsoft Defender 바이러스 백신 엔진은 파일 변경 내용(이동, 복사본 또는 수정과 같은 파일 쓰기) 및 일반 프로그램 활동(열리거나 실행되고 다른 프로그램이 실행되는 프로그램)을 기록합니다.</span><span class="sxs-lookup"><span data-stu-id="77253-150">The Microsoft Defender Antivirus engine makes note of any file changes (file writes, such as moves, copies, or modifications) and general program activity (programs that are opened or running and that cause other programs to run).</span></span> | <span data-ttu-id="77253-151">사용</span><span class="sxs-lookup"><span data-stu-id="77253-151">Enabled</span></span> |
       | <span data-ttu-id="77253-152">원시 볼륨 쓰기 알림 켜기</span><span class="sxs-lookup"><span data-stu-id="77253-152">Turn on raw volume write notifications</span></span> | <span data-ttu-id="77253-153">원시 볼륨 쓰기에 대한 정보는 동작 모니터링을 통해 분석됩니다.</span><span class="sxs-lookup"><span data-stu-id="77253-153">Information about raw volume writes will be analyzed by behavior monitoring.</span></span> | <span data-ttu-id="77253-154">사용</span><span class="sxs-lookup"><span data-stu-id="77253-154">Enabled</span></span> |
       | <span data-ttu-id="77253-155">실시간 보호를 사용할 때마다 프로세스 검색 켜기</span><span class="sxs-lookup"><span data-stu-id="77253-155">Turn on process scanning whenever real-time protection is enabled</span></span> | <span data-ttu-id="77253-156">실행 중인 프로세스에서 의심스러운 수정 또는 Microsoft Defender 바이러스 백신 검색할 수 있도록 독립적으로 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="77253-156">You can independently enable the Microsoft Defender Antivirus engine to scan running processes for suspicious modifications or behaviors.</span></span> <span data-ttu-id="77253-157">이 기능은 실시간 보호를 일시적으로 사용하지 않도록 설정하고 사용하지 않도록 설정한 동안 시작된 프로세스를 자동으로 검색하려는 경우 유용합니다.</span><span class="sxs-lookup"><span data-stu-id="77253-157">This is useful if you have temporarily disabled real-time protection and want to automatically scan processes that started while it was disabled.</span></span> | <span data-ttu-id="77253-158">사용</span><span class="sxs-lookup"><span data-stu-id="77253-158">Enabled</span></span> |
       | <span data-ttu-id="77253-159">검사할 다운로드한 파일 및 첨부 파일의 최대 크기 정의</span><span class="sxs-lookup"><span data-stu-id="77253-159">Define the maximum size of downloaded files and attachments to be scanned</span></span> | <span data-ttu-id="77253-160">크기를 킬로바이트로 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="77253-160">You can define the size in kilobytes.</span></span> | <span data-ttu-id="77253-161">사용</span><span class="sxs-lookup"><span data-stu-id="77253-161">Enabled</span></span> |
       | <span data-ttu-id="77253-162">동작 모니터링 켜기에 대한 로컬 설정 다시 설정 구성</span><span class="sxs-lookup"><span data-stu-id="77253-162">Configure local setting override for turn on behavior monitoring</span></span> | <span data-ttu-id="77253-163">동작 모니터링 구성에 대한 로컬 오버라이드를 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="77253-163">Configure a local override for the configuration of behavior monitoring.</span></span> <span data-ttu-id="77253-164">이 설정은 그룹 정책에서만 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="77253-164">This setting can only be set by Group Policy.</span></span> <span data-ttu-id="77253-165">이 설정을 사용하면 로컬 기본 설정이 그룹 정책보다 우선합니다.</span><span class="sxs-lookup"><span data-stu-id="77253-165">If you enable this setting, the local preference setting will take priority over Group Policy.</span></span> <span data-ttu-id="77253-166">이 설정을 사용하지 않도록 설정하거나 구성하지 않는 경우 그룹 정책이 로컬 기본 설정보다 우선합니다.</span><span class="sxs-lookup"><span data-stu-id="77253-166">If you disable or do not configure this setting, Group Policy will take priority over the local preference setting.</span></span>| <span data-ttu-id="77253-167">사용</span><span class="sxs-lookup"><span data-stu-id="77253-167">Enabled</span></span> |
       | <span data-ttu-id="77253-168">다운로드한 모든 파일 및 첨부 파일을 검사하기 위한 로컬 설정 다시 설정 구성</span><span class="sxs-lookup"><span data-stu-id="77253-168">Configure local setting override for scanning all downloaded files and attachments</span></span> | <span data-ttu-id="77253-169">다운로드한 모든 파일 및 첨부 파일에 대한 검사 구성에 대한 로컬 다시 설정을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="77253-169">Configure a local override for the configuration of scanning for all downloaded files and attachments.</span></span> <span data-ttu-id="77253-170">이 설정은 그룹 정책에서만 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="77253-170">This setting can only be set by Group Policy.</span></span> <span data-ttu-id="77253-171">이 설정을 사용하면 로컬 기본 설정이 그룹 정책보다 우선합니다.</span><span class="sxs-lookup"><span data-stu-id="77253-171">If you enable this setting, the local preference setting will take priority over Group Policy.</span></span> <span data-ttu-id="77253-172">이 설정을 사용하지 않도록 설정하거나 구성하지 않는 경우 그룹 정책이 로컬 기본 설정보다 우선합니다.</span><span class="sxs-lookup"><span data-stu-id="77253-172">If you disable or do not configure this setting, Group Policy will take priority over the local preference setting.</span></span>| <span data-ttu-id="77253-173">사용</span><span class="sxs-lookup"><span data-stu-id="77253-173">Enabled</span></span> |
       | <span data-ttu-id="77253-174">컴퓨터의 파일 및 프로그램 활동 모니터링에 대한 로컬 설정 다시 설정 구성</span><span class="sxs-lookup"><span data-stu-id="77253-174">Configure local setting override for monitoring file and program activity on your computer</span></span> | <span data-ttu-id="77253-175">컴퓨터의 파일 및 프로그램 활동에 대한 모니터링 구성에 대한 로컬 다시 설정을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="77253-175">Configure a local override for the configuration of monitoring for file and program activity on your computer.</span></span> <span data-ttu-id="77253-176">이 설정은 그룹 정책에서만 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="77253-176">This setting can only be set by Group Policy.</span></span> <span data-ttu-id="77253-177">이 설정을 사용하면 로컬 기본 설정이 그룹 정책보다 우선합니다.</span><span class="sxs-lookup"><span data-stu-id="77253-177">If you enable this setting, the local preference setting will take priority over Group Policy.</span></span> <span data-ttu-id="77253-178">이 설정을 사용하지 않도록 설정하거나 구성하지 않는 경우 그룹 정책이 로컬 기본 설정보다 우선합니다.</span><span class="sxs-lookup"><span data-stu-id="77253-178">If you disable or do not configure this setting, Group Policy will take priority over the local preference setting.</span></span>| <span data-ttu-id="77253-179">사용</span><span class="sxs-lookup"><span data-stu-id="77253-179">Enabled</span></span> |
       | <span data-ttu-id="77253-180">실시간 보호를 켜도록 로컬 설정 다시 설정 구성</span><span class="sxs-lookup"><span data-stu-id="77253-180">Configure local setting override to turn on real-time protection</span></span> | <span data-ttu-id="77253-181">실시간 보호를 켜도록 구성에 대한 로컬 다시 설정을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="77253-181">Configure a local override for the configuration to turn on real-time protection.</span></span> <span data-ttu-id="77253-182">이 설정은 그룹 정책에서만 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="77253-182">This setting can only be set by Group Policy.</span></span> <span data-ttu-id="77253-183">이 설정을 사용하면 로컬 기본 설정이 그룹 정책보다 우선합니다.</span><span class="sxs-lookup"><span data-stu-id="77253-183">If you enable this setting, the local preference setting will take priority over Group Policy.</span></span> <span data-ttu-id="77253-184">이 설정을 사용하지 않도록 설정하거나 구성하지 않는 경우 그룹 정책이 로컬 기본 설정보다 우선합니다.</span><span class="sxs-lookup"><span data-stu-id="77253-184">If you disable or do not configure this setting, Group Policy will take priority over the local preference setting.</span></span>| <span data-ttu-id="77253-185">사용</span><span class="sxs-lookup"><span data-stu-id="77253-185">Enabled</span></span> |
       | <span data-ttu-id="77253-186">들어오는 파일 및 나올 파일 활동에 대한 모니터링을 위한 로컬 설정 오버라이드 구성</span><span class="sxs-lookup"><span data-stu-id="77253-186">Configure local setting override for monitoring for incoming and outgoing file activity</span></span> | <span data-ttu-id="77253-187">수신 및 전송 파일 활동에 대한 모니터링 구성에 대한 로컬 오버라이드를 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="77253-187">Configure a local override for the configuration of monitoring for incoming and outgoing file activity.</span></span> <span data-ttu-id="77253-188">이 설정은 그룹 정책에서만 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="77253-188">This setting can only be set by Group Policy.</span></span> <span data-ttu-id="77253-189">이 설정을 사용하면 로컬 기본 설정이 그룹 정책보다 우선합니다.</span><span class="sxs-lookup"><span data-stu-id="77253-189">If you enable this setting, the local preference setting will take priority over Group Policy.</span></span> <span data-ttu-id="77253-190">이 설정을 사용하지 않도록 설정하거나 구성하지 않는 경우 그룹 정책이 로컬 기본 설정보다 우선합니다.</span><span class="sxs-lookup"><span data-stu-id="77253-190">If you disable or do not configure this setting, Group Policy will take priority over the local preference setting.</span></span> | <span data-ttu-id="77253-191">사용</span><span class="sxs-lookup"><span data-stu-id="77253-191">Enabled</span></span> |
       | <span data-ttu-id="77253-192">수신 및 전송 파일 및 프로그램 활동에 대한 모니터링 구성</span><span class="sxs-lookup"><span data-stu-id="77253-192">Configure monitoring for incoming and outgoing file and program activity</span></span> | <span data-ttu-id="77253-193">들어오는 방향, 나갈 방향, 둘 다 또는 둘 다에 대해 모니터링이 진행될지 여부를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="77253-193">Specify whether monitoring should occur on incoming, outgoing, both, or neither direction.</span></span> <span data-ttu-id="77253-194">이 설정은 특정 Windows 정의한 서버 설치 또는 많은 양의 파일 변경 내용이 한 방향으로만 표시되고 네트워크 성능을 향상하려는 서버 역할과 관련이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="77253-194">This is relevant for Windows Server installations where you have defined specific servers or Server Roles that see large amounts of file changes in only one direction and you want to improve network performance.</span></span> <span data-ttu-id="77253-195">네트워크에서 완전히 업데이트된 끝점 및 서버는 파일 변경의 수나 방향에 따라 성능에 거의 영향을 줄 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="77253-195">Fully updated endpoints (and servers) on a network will see little performance impact irrespective of the number or direction of file changes.</span></span> | <span data-ttu-id="77253-196">사용(양방향)</span><span class="sxs-lookup"><span data-stu-id="77253-196">Enabled (both directions)</span></span> |

    1. <span data-ttu-id="77253-197">설정을 적절하게 구성하고 확인 을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="77253-197">Configure the setting as appropriate, and click **OK**.</span></span>
    
    1. <span data-ttu-id="77253-198">표의 각 설정에 대해 이전 단계를 반복합니다.</span><span class="sxs-lookup"><span data-stu-id="77253-198">Repeat the previous steps for each setting in the table.</span></span>

5. <span data-ttu-id="77253-199">검색 Microsoft Defender 바이러스 백신 설정을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="77253-199">Configure the Microsoft Defender Antivirus scanning policy setting.</span></span> <span data-ttu-id="77253-200">이렇게 하려면 다음을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="77253-200">To do this:</span></span>  

    1. <span data-ttu-id="77253-201">왼쪽 **창의** Microsoft Defender 바이러스 백신 트리에서 스캔을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="77253-201">From the **Microsoft Defender Antivirus** tree on left pane, click **Scan**.</span></span>
    
       ![Microsoft Defender 바이러스 백신 검사 옵션](images/gpedit-windows-defender-antivirus-scan.png)

    1. <span data-ttu-id="77253-203">오른쪽의 **스캔** 세부 정보 창에서 다음 표에 지정된 정책 설정을 두 번 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="77253-203">In the **Scan** details pane on right, double-click the policy setting as specified in the following table:</span></span>

       | <span data-ttu-id="77253-204">설정</span><span class="sxs-lookup"><span data-stu-id="77253-204">Setting</span></span> | <span data-ttu-id="77253-205">설명</span><span class="sxs-lookup"><span data-stu-id="77253-205">Description</span></span> | <span data-ttu-id="77253-206">기본 설정</span><span class="sxs-lookup"><span data-stu-id="77253-206">Default setting</span></span> |
       |-----------------------------|------------------------|-------------------------------|    
       | <span data-ttu-id="77253-207">추론 켜기</span><span class="sxs-lookup"><span data-stu-id="77253-207">Turn on heuristics</span></span> | <span data-ttu-id="77253-208">추론 보호는 활동 감지를 요청하기 직전에 의심스러운 활동을 Microsoft Defender 바이러스 백신 차단합니다.</span><span class="sxs-lookup"><span data-stu-id="77253-208">Heuristic protection will disable or block suspicious activity immediately before the Microsoft Defender Antivirus engine is asked to detect the activity.</span></span> | <span data-ttu-id="77253-209">사용</span><span class="sxs-lookup"><span data-stu-id="77253-209">Enabled</span></span> |

    1. <span data-ttu-id="77253-210">설정을 적절하게 구성하고 확인 을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="77253-210">Configure the setting as appropriate, and click **OK**.</span></span>
    
6. <span data-ttu-id="77253-211">로컬 **그룹 정책 편집기를 닫습니다.**</span><span class="sxs-lookup"><span data-stu-id="77253-211">Close **Local Group Policy Editor**.</span></span>


## <a name="disable-real-time-protection-in-group-policy"></a><span data-ttu-id="77253-212">그룹 정책에서 실시간 보호를 사용하지 않도록 설정</span><span class="sxs-lookup"><span data-stu-id="77253-212">Disable real-time protection in Group Policy</span></span>

> [!WARNING]
> <span data-ttu-id="77253-213">실시간 보호를 설정하면 끝점의 보호가 크게 감소하며 권장되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="77253-213">Disabling real-time protection drastically reduces the protection on your endpoints and is not recommended.</span></span>

<span data-ttu-id="77253-214">기본 실시간 보호 기능은 기본적으로 사용하도록 설정되어 있지만 로컬 그룹 정책 편집기를 사용하여 사용하지 않도록 설정할 **수 있습니다.**</span><span class="sxs-lookup"><span data-stu-id="77253-214">The main real-time protection capability is enabled by default, but you can disable it by using **Local Group Policy Editor**.</span></span>

<span data-ttu-id="77253-215">그룹 정책에서 실시간 보호를 사용하지 않도록 설정:</span><span class="sxs-lookup"><span data-stu-id="77253-215">To disable real-time protection in Group policy:</span></span>

1. <span data-ttu-id="77253-216">로컬 **그룹 정책 편집기를 열습니다.**</span><span class="sxs-lookup"><span data-stu-id="77253-216">Open **Local Group Policy Editor**.</span></span>

   1. <span data-ttu-id="77253-217">작업 Windows 10 상자에 **gpedit 를 입력합니다.**</span><span class="sxs-lookup"><span data-stu-id="77253-217">In your Windows 10 taskbar search box, type **gpedit**.</span></span>
   
   1. <span data-ttu-id="77253-218">최상의 **일치 아래에서** 그룹 정책 **편집을 클릭하여** 로컬 그룹 정책 **편집기를 실행합니다.**</span><span class="sxs-lookup"><span data-stu-id="77253-218">Under **Best match**, click **Edit group policy** to launch **Local Group Policy Editor**.</span></span>

2.  <span data-ttu-id="77253-219">로컬 그룹 정책 편집기 왼쪽 창에서 컴퓨터 구성 관리 템플릿 Windows 구성 요소 및 실시간 보호로 Microsoft Defender 바이러스 백신  >    >    >    >  **확장합니다.**</span><span class="sxs-lookup"><span data-stu-id="77253-219">In the left pane of **Local Group Policy Editor**, expand the tree to **Computer Configuration** > **Administrative Templates** > **Windows Components** > **Microsoft Defender Antivirus** > **Real-time Protection**.</span></span>

3. <span data-ttu-id="77253-220">오른쪽의  실시간 보호 세부 정보 창에서 실시간 보호 끄기 를 **두 번 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="77253-220">In the **Real-time Protection** details pane on right, double-click **Turn off real-time protection**.</span></span>

   ![실시간 보호 끄기](images/gpedit-turn-off-real-time-protection.png)

4. <span data-ttu-id="77253-222">실시간 **보호** 설정 끄기 창에서 옵션을 사용으로 **설정합니다.**</span><span class="sxs-lookup"><span data-stu-id="77253-222">In the **Turn off real-time protection** setting window, set the option to **Enabled**.</span></span>

   ![실시간 보호 사용 끄기](images/gpedit-turn-off-real-time-protection-enabled.png)
   
5. <span data-ttu-id="77253-224">**확인** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="77253-224">Click **OK**.</span></span>

6. <span data-ttu-id="77253-225">로컬 **그룹 정책 편집기를 닫습니다.**</span><span class="sxs-lookup"><span data-stu-id="77253-225">Close **Local Group Policy Editor**.</span></span>

## <a name="related-articles"></a><span data-ttu-id="77253-226">관련 문서</span><span class="sxs-lookup"><span data-stu-id="77253-226">Related articles</span></span>

- [<span data-ttu-id="77253-227">동작, 추론 및 실시간 보호 구성</span><span class="sxs-lookup"><span data-stu-id="77253-227">Configure behavioral, heuristic, and real-time protection</span></span>](configure-protection-features-microsoft-defender-antivirus.md)
- [<span data-ttu-id="77253-228">Windows 10의 Microsoft Defender 바이러스 백신</span><span class="sxs-lookup"><span data-stu-id="77253-228">Microsoft Defender Antivirus in Windows 10</span></span>](microsoft-defender-antivirus-in-windows-10.md)