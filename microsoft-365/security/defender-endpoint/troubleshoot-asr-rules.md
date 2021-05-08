---
title: 끝점 ASR 규칙에 대한 Microsoft Defender 보고 및 문제 해결
description: 이 항목에서는 끝점 ASR 규칙에 대한 Microsoft Defender를 보고하고 문제를 해결하는 방법을 설명
keywords: 공격 표면 감소 규칙, asr, hips, 호스트 침입 방지 시스템, 보호 규칙, 악용 방지, 악용, 감염 방지, 끝점용 Microsoft Defender
search.product: eADQiWindows 10XVcnh
ms.pagetype: security
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
localization_priority: Normal
audience: ITPro
author: lovina-saldanha
ms.author: v-lsaldanha
ms.reviewer: ''
manager: dansimp
ms.custom: asr
ms.topic: article
ms.technology: mde
ms.openlocfilehash: c043e97d6c02e4f41d000e9ce8cfea4a0950252a
ms.sourcegitcommit: ff20f5b4e3268c7c98a84fb1cbe7db7151596b6d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/06/2021
ms.locfileid: "52246147"
---
# <a name="report-and-troubleshoot-microsoft-defender-for-atp-asr-rules"></a><span data-ttu-id="fbf8e-104">ATP ASR 규칙에 대한 Microsoft Defender 보고 및 문제 해결</span><span class="sxs-lookup"><span data-stu-id="fbf8e-104">Report and troubleshoot Microsoft Defender for ATP ASR Rules</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="fbf8e-105">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="fbf8e-105">**Applies to:**</span></span>

- [<span data-ttu-id="fbf8e-106">엔드포인트용 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="fbf8e-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)
- [<span data-ttu-id="fbf8e-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="fbf8e-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

<span data-ttu-id="fbf8e-108">Microsoft 365 보안 센터는 Microsoft ID, 데이터, 장치, 앱 및 인프라 전체의 보안을 모니터링하고 관리하기 위한 새로운 인터페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="fbf8e-108">The Microsoft 365 security center is the new interface for monitoring and managing security across your Microsoft identities, data, devices, apps, and infrastructure.</span></span> <span data-ttu-id="fbf8e-109">Microsoft 365 보안 센터를 통해 조직의 보안 상태를 쉽게 검토할 수 있으며 디바이스, 사용자 및 앱을 구성하는 작업을 비롯하여 의심스러운 활동에 대해 알림을 받을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fbf8e-109">Here you can easily view the security health of your organization, act to configure devices, users, and apps, and get alerts for suspicious activity.</span></span> <span data-ttu-id="fbf8e-110">Microsoft 365 보안 센터는 보안 관리자와 보안 운영 팀이 조직을 더 효과적으로 관리하고 보호하는 데 도움을 줄 수 있도록 설계되었습니다.</span><span class="sxs-lookup"><span data-stu-id="fbf8e-110">The Microsoft 365 security center is intended for security admins and security operations teams to better manage and protect their organization.</span></span> <span data-ttu-id="fbf8e-111">의 Microsoft 365 보안 센터를 https://security.microsoft.com 방문합니다.</span><span class="sxs-lookup"><span data-stu-id="fbf8e-111">Visit the Microsoft 365 security center at https://security.microsoft.com.</span></span>
<span data-ttu-id="fbf8e-112">Microsoft 365 센터에서 현재 ASR 규칙 구성 및 자산의 이벤트를 전체적으로 살펴 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fbf8e-112">In Microsoft 365 security center, we offer you a complete look at the current ASR rules configuration and events in your estate.</span></span> <span data-ttu-id="fbf8e-113">이러한 보고서를 채우기 위해 디바이스를 끝점용 Microsoft Defender 서비스에 온보딩해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="fbf8e-113">Note that your devices must be onboarded into the Microsoft Defender for Endpoint service for these reports to be populated.</span></span>
<span data-ttu-id="fbf8e-114">다음은 Microsoft 365 보안 센터의 스크린샷입니다(보고서 장치 공격 표면  >    >  **감소).**</span><span class="sxs-lookup"><span data-stu-id="fbf8e-114">Here's a screenshot from the Microsoft 365 security center (under **Reports** > **Devices** > **Attack surface reduction**).</span></span> <span data-ttu-id="fbf8e-115">장치 수준에서 공격 **표면** 감소 규칙 창에서 **구성을** 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="fbf8e-115">At the device level, select **Configuration** from the **Attack surface reduction rules** pane.</span></span> <span data-ttu-id="fbf8e-116">다음 화면이 표시되어 특정 장치를 선택하고 개별 ASR 규칙 구성을 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fbf8e-116">The following screen is displayed, where you can select a specific device and check its individual ASR rule configuration.</span></span>

:::image type="content" source="images/asrrulesnew.png" alt-text="ASR 규칙 화면":::

## <a name="microsoft-defender-for-endpoint--advanced-hunting"></a><span data-ttu-id="fbf8e-118">끝점용 Microsoft Defender – 고급 헌팅</span><span class="sxs-lookup"><span data-stu-id="fbf8e-118">Microsoft Defender for Endpoint – Advanced hunting</span></span>

<span data-ttu-id="fbf8e-119">끝점용 Microsoft Defender의 가장 강력한 기능 중 하나는 고급 헌팅입니다.</span><span class="sxs-lookup"><span data-stu-id="fbf8e-119">One of the most powerful features of Microsoft Defender for Endpoint is advanced hunting.</span></span> <span data-ttu-id="fbf8e-120">고급 헌팅에 익숙하지 않은 경우 고급 헌팅을 통해 위협에 대한 사전 예방적 헌팅을 [참조합니다.](advanced-hunting-overview.md)</span><span class="sxs-lookup"><span data-stu-id="fbf8e-120">If you're unfamiliar with advanced hunting, refer [proactively hunt for threats with advanced hunting](advanced-hunting-overview.md).</span></span>

<span data-ttu-id="fbf8e-121">고급 헌팅은 MDE 끝점 감지 및 응답(EDR)이 모든 컴퓨터로부터 수집하는 캡처된(원시) 데이터의 최대 30일을 탐색할 수 있는 쿼리 기반(Kusto 쿼리 언어) 위협 헌팅 도구입니다.</span><span class="sxs-lookup"><span data-stu-id="fbf8e-121">Advanced hunting is a query-based (Kusto Query Language) threat-hunting tool that lets you explore up to 30 days of the captured (raw) data, that MDE Endpoint Detection and Response (EDR) collects from all your machines.</span></span> <span data-ttu-id="fbf8e-122">고급 헌팅을 통해 이벤트를 사전적으로 검사하여 흥미로운 지표와 엔터티를 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fbf8e-122">Through advanced hunting, you can proactively inspect events to locate interesting indicators and entities.</span></span> <span data-ttu-id="fbf8e-123">데이터에 유연하게 액세스하면 알려진 위협과 잠재적 위협 모두에 대한 제약이 없는 헌팅에 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="fbf8e-123">The flexible access to data helps unconstrained hunting for both known and potential threats.</span></span>

<span data-ttu-id="fbf8e-124">고급 헌팅을 통해 ASR 규칙 정보를 추출하고, 보고서를 만들고, 특정 ASR 규칙 감사 또는 차단 이벤트의 컨텍스트에 대한 자세한 정보를 얻을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fbf8e-124">Through advanced hunting, it's possible to extract ASR rules information, create reports, and get in-depth information on the context of a given ASR rule audit or block event.</span></span>

<span data-ttu-id="fbf8e-125">ASR 규칙 이벤트는 디바이스의 고급 헌팅 섹션에 있는 DeviceEvents 테이블에서 Microsoft Defender 보안 센터.</span><span class="sxs-lookup"><span data-stu-id="fbf8e-125">ASR rules events are available to be queried from the DeviceEvents table in the advanced hunting section of the Microsoft Defender Security Center.</span></span> <span data-ttu-id="fbf8e-126">예를 들어 아래 쿼리와 같은 간단한 쿼리는 지난 30일 동안 ASR 규칙이 있는 모든 이벤트를 데이터 원본으로 보고하고 ActionType 수로 요약하여 요약할 수 있습니다. 이 경우 ASR 규칙의 실제 코드 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="fbf8e-126">For example, a simple query such as the one below can report all the events that have ASR rules as data source, for the last 30 days, and will summarize them by the ActionType count, that in this case it will be the actual codename of the ASR rule.</span></span>

:::image type="content" source="images/adv-hunt-querynew.png" alt-text="고급 헌팅 쿼리":::

:::image type="content" source="images/adv-hunt-sc-2new.png" alt-text="고급 헌팅 화면":::

<span data-ttu-id="fbf8e-129">고급 헌팅을 사용하면 쿼리를 원하는 내용에 따라 구성할 수 있으므로 개별 컴퓨터의 특정 정보를 파악하거나 전체 환경에서 정보를 추출하려는지 여부에 관계없이 쿼리가 진행될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fbf8e-129">With advanced hunting you can shape the queries to your liking, so that you can see what is happening, regardless of whether you want to pinpoint something on an individual machine, or you want to extract insights from your entire environment.</span></span>

## <a name="microsoft-defender-for-endpoint-machine-timeline"></a><span data-ttu-id="fbf8e-130">끝점 컴퓨터 타임라인용 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="fbf8e-130">Microsoft Defender for Endpoint machine timeline</span></span>

<span data-ttu-id="fbf8e-131">고급 헌팅 대신 더 좁은 범위의 끝점 컴퓨터 타임라인에 대한 Microsoft Defender가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fbf8e-131">An alternative to advanced hunting, but with a narrower scope, is the Microsoft Defender for Endpoint machine timeline.</span></span> <span data-ttu-id="fbf8e-132">디바이스의 수집된 모든 이벤트를 볼 수 있습니다. 지난 6개월 동안의 Microsoft Defender 보안 센터 컴퓨터 목록으로 이동하여 특정 컴퓨터를 선택한 다음 시간 표시 막대 탭을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="fbf8e-132">You can view all the collected events of a device, for the past six months, in the Microsoft Defender Security Center, by going to the Machines list, select a given machine, and then click on the Timeline tab.</span></span>

<span data-ttu-id="fbf8e-133">아래 그림은 주어진 끝점에서 이러한 이벤트의 시간 표시 막대 보기의 스크린샷입니다.</span><span class="sxs-lookup"><span data-stu-id="fbf8e-133">Pictured below is a screenshot of the Timeline view of these events on a given endpoint.</span></span>  <span data-ttu-id="fbf8e-134">이 보기에서 오른쪽 창의 이벤트 그룹을 기준으로 이벤트 목록을 필터링할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fbf8e-134">From this view, you can filter the events list based on any of the Event Groups along the right-side pane.</span></span> <span data-ttu-id="fbf8e-135">경고를 보고 기록 타임라인을 스크롤하는 동안 Flagged 및 Verbose 이벤트를 활성화 또는 비활성화할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fbf8e-135">You can also enable or disable Flagged and Verbose events while viewing alerts and scrolling through the historical timeline.</span></span>

:::image type="content" source="images/mic-sec-def-timelinenew.png" alt-text="Microsoft Defender 보안 센터 타임라인":::

## <a name="how-to-troubleshoot-asr-rules"></a><span data-ttu-id="fbf8e-137">ASR 규칙을 해결하는 방법</span><span class="sxs-lookup"><span data-stu-id="fbf8e-137">How to troubleshoot ASR rules?</span></span>

<span data-ttu-id="fbf8e-138">첫 번째로 가장 즉각적인 방법은 POWERShell cmdlet을 Windows ASR 규칙이 활성화된 디바이스에서 로컬로 검사하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="fbf8e-138">The first and most immediate way is to check locally, on a Windows device, which ASR rules are enabled (and their configuration) is by using the PowerShell cmdlets.</span></span>

<span data-ttu-id="fbf8e-139">다음은 ASR 규칙의 영향 및 작동 문제를 해결하기 위해 Windows 정보를 제공하는 몇 가지 다른 소스입니다.</span><span class="sxs-lookup"><span data-stu-id="fbf8e-139">Here are a few other sources of information that Windows offers, to troubleshoot ASR rules’ impact and operation.</span></span>

### <a name="querying-which-rules-are-active"></a><span data-ttu-id="fbf8e-140">활성 상태인 규칙 쿼리</span><span class="sxs-lookup"><span data-stu-id="fbf8e-140">Querying which rules are active</span></span>
<span data-ttu-id="fbf8e-141">ASR 규칙이 이미 활성화되어 있는지 확인하는 가장 쉬운 방법 중 하나는 PowerShell cmdlet인 Get-MpPreference를 사용하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="fbf8e-141">One of the easiest ways to determine if ASR rules are already enabled—and, is through a PowerShell cmdlet, Get-MpPreference.</span></span>
<span data-ttu-id="fbf8e-142">다음은 예입니다.</span><span class="sxs-lookup"><span data-stu-id="fbf8e-142">Here's an example:</span></span>

:::image type="content" source="images/getmpreferencescriptnew.png" alt-text="mppreference 스크립트를 얻습니다.":::

<span data-ttu-id="fbf8e-144">구성된 작업이 서로 다른 여러 ASR 규칙이 활성화됩니다.</span><span class="sxs-lookup"><span data-stu-id="fbf8e-144">There are multiple ASR rules active, with different configured actions.</span></span>

<span data-ttu-id="fbf8e-145">ASR 규칙에 대한 위의 정보를 확장하기 위해 및/또는 에 대한 AttackSurfaceReductionRules_Ids **사용할** **AttackSurfaceReductionRules_Actions.**</span><span class="sxs-lookup"><span data-stu-id="fbf8e-145">To expand the above information on ASR rules, you can use the properties **AttackSurfaceReductionRules_Ids** and/or **AttackSurfaceReductionRules_Actions**.</span></span>

<span data-ttu-id="fbf8e-146">예제:</span><span class="sxs-lookup"><span data-stu-id="fbf8e-146">Example:</span></span>

<span data-ttu-id="fbf8e-147">*Get-MPPreference | Select-Object -ExpandProperty\*\*AttackSurfaceReductionRules_Ids*</span><span class="sxs-lookup"><span data-stu-id="fbf8e-147">*Get-MPPreference | Select-Object -ExpandProperty\*\*AttackSurfaceReductionRules_Ids*</span></span>

:::image type="content" source="images/getmpref-examplenew.png" alt-text="mpreference 예제를 얻습니다.":::

<span data-ttu-id="fbf8e-149">위에는 0(구성되지 않은)의 설정이 있는 ASR 규칙의 모든 ID가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="fbf8e-149">The above shows all the IDs for ASR rules that have a setting different from 0 (Not Configured).</span></span>

<span data-ttu-id="fbf8e-150">다음 단계에서는 각 규칙이 구성된 실제 작업(차단 또는 감사)을 나열합니다.</span><span class="sxs-lookup"><span data-stu-id="fbf8e-150">The next step is then to list the actual actions (Block or Audit) that each rule is configured with.</span></span> 

<span data-ttu-id="fbf8e-151">*Get-MPPreference | Select-Object -ExpandProperty\*\*AttackSurfaceReductionRules_Actions*</span><span class="sxs-lookup"><span data-stu-id="fbf8e-151">*Get-MPPreference | Select-Object -ExpandProperty\*\*AttackSurfaceReductionRules_Actions*</span></span>

:::image type="content" source="images/getmpref-example2new.png" alt-text="get mppreference example2":::

### <a name="querying-blocking-and-auditing-events"></a><span data-ttu-id="fbf8e-153">쿼리 차단 및 감사 이벤트</span><span class="sxs-lookup"><span data-stu-id="fbf8e-153">Querying blocking and auditing events</span></span>
<span data-ttu-id="fbf8e-154">ASR 규칙 이벤트는 로그 내에서 볼 Windows Defender 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fbf8e-154">ASR rule events can be viewed within the Windows Defender log.</span></span>

<span data-ttu-id="fbf8e-155">액세스하려면 이벤트 뷰어를 Windows 열고 응용 프로그램 및 서비스 로그 Microsoft Windows Windows Defender  >    >    >    >  **를 탐색합니다.**</span><span class="sxs-lookup"><span data-stu-id="fbf8e-155">To access it, open Windows Event Viewer, and browse to **Applications and Services Logs** > **Microsoft** > **Windows** > **Windows Defender** > **Operational**.</span></span>

:::image type="content" source="images/eventviewerscrnew.png" alt-text="이벤트 뷰어 스크러":::

## <a name="microsoft-defender-malware-protection-logs"></a><span data-ttu-id="fbf8e-157">Microsoft Defender 맬웨어 보호 로그</span><span class="sxs-lookup"><span data-stu-id="fbf8e-157">Microsoft Defender Malware Protection Logs</span></span>
<span data-ttu-id="fbf8e-158">또한 이라는 전용 명령줄 Microsoft Defender 바이러스 백신 통해 규칙 이벤트를 볼 수도 있습니다. 이 도구를 사용하여 필요한 경우 작업을 관리 및 구성하고 `*mpcmdrun.exe*` 자동화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fbf8e-158">You can also view rule events through the Microsoft Defender Antivirus dedicated command-line tool, called `*mpcmdrun.exe*`, that can be used to manage and configure, and automate tasks if needed.</span></span>

<span data-ttu-id="fbf8e-159">이 유틸리티는 *%ProgramFiles%\Windows Defender\MpCmdRun.exe.*</span><span class="sxs-lookup"><span data-stu-id="fbf8e-159">You can find this utility in *%ProgramFiles%\Windows Defender\MpCmdRun.exe*.</span></span> <span data-ttu-id="fbf8e-160">관리자 권한 명령 프롬프트(즉, 관리자 권한으로 실행)에서 실행해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="fbf8e-160">You must run it from an elevated command prompt (that is, run as Admin).</span></span>

<span data-ttu-id="fbf8e-161">지원 정보를 생성하기 위해 *-getfilesMpCmdRun.exe 입력합니다.*</span><span class="sxs-lookup"><span data-stu-id="fbf8e-161">To generate the support information, type *MpCmdRun.exe -getfiles*.</span></span> <span data-ttu-id="fbf8e-162">잠시 후 여러 로그가 보관함(MpSupportFiles.cab)에 패키지되어 *C:\ProgramData\Microsoft\Windows Defender\Support 에서* 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fbf8e-162">After a while, several logs will be packaged into an archive (MpSupportFiles.cab) and made available in *C:\ProgramData\Microsoft\Windows Defender\Support*.</span></span>

:::image type="content" source="images/malware-prot-logsnew.png" alt-text="맬웨어 보호 로그":::

<span data-ttu-id="fbf8e-164">해당 보관 파일을 추출하면 문제 해결을 위해 여러 파일을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fbf8e-164">Extract that archive and you'll have many files available for troubleshooting purposes.</span></span>

<span data-ttu-id="fbf8e-165">가장 관련성이 높은 파일은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="fbf8e-165">The most relevant files are as follows:</span></span>

- <span data-ttu-id="fbf8e-166">**MPOperationalEvents.txt** - 이 파일에는 작업 로그에 대한 이벤트 뷰어에 Windows Defender 수준이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fbf8e-166">**MPOperationalEvents.txt** - This file contains same level of information found in Event Viewer for Windows Defender’s Operational log.</span></span>
- <span data-ttu-id="fbf8e-167">**MPRegistry.txt** – 이 파일에서 지원 로그가 캡처된 Windows Defender 현재 모든 구성을 분석할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fbf8e-167">**MPRegistry.txt** – In this file you will can analyze all the current Windows Defender configurations, from the moment the support logs were captured.</span></span>
- <span data-ttu-id="fbf8e-168">**MPLog.txt** - 이 로그에는 로그의 모든 작업/작업에 대한 자세한 정보가 Windows Defender.</span><span class="sxs-lookup"><span data-stu-id="fbf8e-168">**MPLog.txt** – This log contains more verbose information about all the actions/operations of the Windows Defender.</span></span>
