---
title: 다운로드 가능한 준비 평가 검사
description: 필요한 끝점을 포함하여 장치 및 네트워크 설정 확인
keywords: Microsoft Managed Desktop, Microsoft 365, 서비스, 문서
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
audience: Admin
ms.openlocfilehash: eec6bdff2e494e0f55b06cb581c5775d3ffeb9e3
ms.sourcegitcommit: 53acc851abf68e2272e75df0856c0e16b0c7e48d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/02/2021
ms.locfileid: "51581037"
---
# <a name="downloadable-readiness-assessment-checker"></a><span data-ttu-id="baaaa-104">다운로드 가능한 준비 평가 검사</span><span class="sxs-lookup"><span data-stu-id="baaaa-104">Downloadable readiness assessment checker</span></span>

<span data-ttu-id="baaaa-105">Microsoft Managed Desktop에서 잘 작동하려면 장치가 하드웨어 및 설정에 대한 특정 요구 사항을 충족해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="baaaa-105">To work well with Microsoft Managed Desktop, devices must meet certain requirements for hardware and settings.</span></span> <span data-ttu-id="baaaa-106">또한 각 장치는 주요 끝점에 도달할 수 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="baaaa-106">Also, each device must be able to reach key endpoints.</span></span> <span data-ttu-id="baaaa-107">이 도구를 다운로드하여 실행하여 HTML 보고서를 다운로드하고 결과를 본 다음 조치를 취합니다.</span><span class="sxs-lookup"><span data-stu-id="baaaa-107">Download and run this tool to obtain an HTML report, view results, and then take action.</span></span> <span data-ttu-id="baaaa-108">도구 및 지원 파일을 다운로드한 다음 Microsoft Managed Desktop에 등록하려는 각 장치에서 수동으로 실행해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="baaaa-108">You will need to download the tool and supporting files, and then run it manually on each device you want to enroll in Microsoft Managed Desktop.</span></span>

<span data-ttu-id="baaaa-109">각 검사에 대해 도구는 세 가지 결과 중 하나를 보고합니다.</span><span class="sxs-lookup"><span data-stu-id="baaaa-109">For each check, the tool will report one of three possible results:</span></span>


|<span data-ttu-id="baaaa-110">결과</span><span class="sxs-lookup"><span data-stu-id="baaaa-110">Result</span></span>  |<span data-ttu-id="baaaa-111">의미</span><span class="sxs-lookup"><span data-stu-id="baaaa-111">Meaning</span></span>  |
|---------|---------|
|<span data-ttu-id="baaaa-112">준비</span><span class="sxs-lookup"><span data-stu-id="baaaa-112">Ready</span></span>     | <span data-ttu-id="baaaa-113">등록을 완료하기 전에 필요한 작업은 없습니다.</span><span class="sxs-lookup"><span data-stu-id="baaaa-113">No action is required before you complete enrollment.</span></span>        |
|<span data-ttu-id="baaaa-114">권고</span><span class="sxs-lookup"><span data-stu-id="baaaa-114">Advisory</span></span>    | <span data-ttu-id="baaaa-115">등록과 사용자에 대해 최상의 환경을 제공하려면 도구의 단계를 따르세요.</span><span class="sxs-lookup"><span data-stu-id="baaaa-115">Follow the steps in the tool for the best experience with enrollment and for users.</span></span> <span data-ttu-id="baaaa-116">*등록을* 완료할 수 있지만 첫 번째 장치를 배포하기 전에 이러한 문제를 해결해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="baaaa-116">You *can* complete enrollment, but you must fix these issues before you deploy your first device.</span></span>        |
|<span data-ttu-id="baaaa-117">준비되지 않음</span><span class="sxs-lookup"><span data-stu-id="baaaa-117">Not ready</span></span> | <span data-ttu-id="baaaa-118">*이러한 문제를* 해결하지 않는 경우 등록이 실패합니다.</span><span class="sxs-lookup"><span data-stu-id="baaaa-118">*Enrollment will fail* if you don't fix these issues.</span></span> <span data-ttu-id="baaaa-119">도구의 단계에 따라 문제를 해결합니다.</span><span class="sxs-lookup"><span data-stu-id="baaaa-119">Follow the steps in the tool to resolve them.</span></span>        |

## <a name="obtain-the-checker"></a><span data-ttu-id="baaaa-120">검사기 얻기</span><span class="sxs-lookup"><span data-stu-id="baaaa-120">Obtain the checker</span></span>

<span data-ttu-id="baaaa-121">에서 .zip 파일을 https://aka.ms/mmddratoolv0 다운로드합니다.</span><span class="sxs-lookup"><span data-stu-id="baaaa-121">Download the .zip file from https://aka.ms/mmddratoolv0.</span></span>

> [!NOTE]
> <span data-ttu-id="baaaa-122">도구를 실행하는 사용자에게는 도구를 실행 중인 디바이스에 대한 로컬 관리자 권한이 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="baaaa-122">The user running the tool must have local Administrator rights on the device where they're running it.</span></span>

 <span data-ttu-id="baaaa-123">그런 다음 다음 단계를 수행하여 도구를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="baaaa-123">Then run the tool by following these steps:</span></span>

1. <span data-ttu-id="baaaa-124">다운로드한 .zip 파일을 확인하려는 각 디바이스에 복사합니다.</span><span class="sxs-lookup"><span data-stu-id="baaaa-124">Copy the downloaded .zip file to each device you want to check.</span></span>
2. <span data-ttu-id="baaaa-125">압축된 다운로드에서 모든 파일을 추출합니다.</span><span class="sxs-lookup"><span data-stu-id="baaaa-125">Extract all files in the compressed download.</span></span>
3. <span data-ttu-id="baaaa-126">를 **Microsoft.MMD.DeviceReadinessAssessmentTool.exe.**</span><span class="sxs-lookup"><span data-stu-id="baaaa-126">Run **Microsoft.MMD.DeviceReadinessAssessmentTool.exe**.</span></span>
4. <span data-ttu-id="baaaa-127">사용자 액세스 제어 프롬프트가 나타나면 예를 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="baaaa-127">When the User Access Control prompt appears, select **Yes**.</span></span> <span data-ttu-id="baaaa-128">이 도구가 실행되어 기본 브라우저에서 보고서를 여는 경우</span><span class="sxs-lookup"><span data-stu-id="baaaa-128">The tool runs and opens a report in your default browser.</span></span>

<span data-ttu-id="baaaa-129">또한 .zip 보관 파일을 다운로드하여 공유 위치에  추출하고, 각 장치에서Microsoft.MMD.DeviceReadinessAssessmentTool.exe액세스한 다음 로컬로 실행할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="baaaa-129">You could also download and extract the .zip archive to a shared location, access **Microsoft.MMD.DeviceReadinessAssessmentTool.exe** from each device, and then run it locally.</span></span>


## <a name="checks"></a><span data-ttu-id="baaaa-130">검사</span><span class="sxs-lookup"><span data-stu-id="baaaa-130">Checks</span></span>

<span data-ttu-id="baaaa-131">다운로드 가능한 도구는 이러한 장치 및 네트워크 관련 항목을 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="baaaa-131">The downloadable tool checks these device- and network-related items:</span></span>

### <a name="hardware"></a><span data-ttu-id="baaaa-132">하드웨어</span><span class="sxs-lookup"><span data-stu-id="baaaa-132">Hardware</span></span>

<span data-ttu-id="baaaa-133">장치는 Microsoft Managed Desktop에서 작동하려면 특정 하드웨어 요구 사항을 충족해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="baaaa-133">Devices must meet specific hardware requirements to work with Microsoft Managed Desktop.</span></span> <span data-ttu-id="baaaa-134">현재는 승인된 특정 [장치만](../service-description/device-list.md) 등록할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="baaaa-134">Currently, only specific [approved devices](../service-description/device-list.md) are allowed to enroll.</span></span> 

<span data-ttu-id="baaaa-135">장치가 검사에 실패하면 Microsoft Managed Desktop과 호환되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="baaaa-135">If your device fails any of the checks, it's not compatible with Microsoft Managed Desktop.</span></span>

### <a name="network-endpoints"></a><span data-ttu-id="baaaa-136">네트워크 끝점</span><span class="sxs-lookup"><span data-stu-id="baaaa-136">Network endpoints</span></span>

<span data-ttu-id="baaaa-137">디바이스는 Microsoft Managed Desktop에서 [작동하기](network.md) 위해 여러 주요 끝점에 도달할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="baaaa-137">Devices much be able to reach several [key endpoints](network.md) to work with Microsoft Managed Desktop.</span></span>

<span data-ttu-id="baaaa-138">도구에서 준비되지  않은 결과를 보고하는 경우 자세한 보고서를 참조하여 도달할 수 없는 끝점을 찾아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="baaaa-138">If the tool reports a **Not ready** result, see the detailed report to find out which endpoints weren't reachable.</span></span> <span data-ttu-id="baaaa-139">그런 다음 방화벽 또는 기타 네트워크 설정을 조정하여 해당 끝점에 도달할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="baaaa-139">Then adjust your firewall or other network settings to ensure those endpoints can be reached.</span></span>

### <a name="other-settings"></a><span data-ttu-id="baaaa-140">기타 설정</span><span class="sxs-lookup"><span data-stu-id="baaaa-140">Other settings</span></span>

#### <a name="enterprise-wi-fi-profiles"></a><span data-ttu-id="baaaa-141">엔터프라이즈 Wi-Fi 프로필</span><span class="sxs-lookup"><span data-stu-id="baaaa-141">Enterprise wi-fi profiles</span></span>

<span data-ttu-id="baaaa-142">권고 **결과는** 인증서 및 프로필이 제대로 작동해야 하는 일부 Wi-Fi 프로필을 사용 중이란 의미입니다.</span><span class="sxs-lookup"><span data-stu-id="baaaa-142">An **Advisory** result means that you are using some wi-fi profiles that need certificates and profiles to work properly.</span></span> <span data-ttu-id="baaaa-143">자세한 내용은 인증서 배포 및 [Wi-Fi/VPN 프로필을 참조하세요.](certs-wifi-lan.md#deploy-certificates-and-wi-fivpn-profile)</span><span class="sxs-lookup"><span data-stu-id="baaaa-143">For more information, see [Deploy certificates and Wi-Fi/VPN profile](certs-wifi-lan.md#deploy-certificates-and-wi-fivpn-profile).</span></span>

#### <a name="lan-profiles"></a><span data-ttu-id="baaaa-144">LAN 프로필</span><span class="sxs-lookup"><span data-stu-id="baaaa-144">LAN profiles</span></span>

<span data-ttu-id="baaaa-145">권고 **결과는** 인증서 및 프로필이 제대로 작동해야 하는 란이 있는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="baaaa-145">An **Advisory** result means that you have LANs that need certificates and profiles to work properly.</span></span> <span data-ttu-id="baaaa-146">자세한 내용은 Microsoft Managed Desktop에 대한 인증서 및 네트워크 프로필 [준비를 참조하세요.](certs-wifi-lan.md)</span><span class="sxs-lookup"><span data-stu-id="baaaa-146">For more information, see [Prepare certificates and network profiles for Microsoft Managed Desktop](certs-wifi-lan.md).</span></span>

#### <a name="vpn-profiles"></a><span data-ttu-id="baaaa-147">VPN 프로필</span><span class="sxs-lookup"><span data-stu-id="baaaa-147">VPN profiles</span></span>

<span data-ttu-id="baaaa-148">권고 **결과는** VPN(가상 사설망)을 사용 중이란 의미입니다.</span><span class="sxs-lookup"><span data-stu-id="baaaa-148">An **Advisory** result means that you're using a virtual private network (VPN).</span></span> <span data-ttu-id="baaaa-149">Microsoft Intune과 통합된 인증서를 배포하는 VPN 프로필을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="baaaa-149">Create a VPN profile that deploys certificates integrated with Microsoft Intune.</span></span> <span data-ttu-id="baaaa-150">자세한 내용은 Microsoft Managed Desktop에 대한 인증서 및 네트워크 프로필 [준비를 참조하세요.](certs-wifi-lan.md)</span><span class="sxs-lookup"><span data-stu-id="baaaa-150">For more information, see [Prepare certificates and network profiles for Microsoft Managed Desktop](certs-wifi-lan.md).</span></span>

#### <a name="mapped-drives"></a><span data-ttu-id="baaaa-151">매핑된 드라이브</span><span class="sxs-lookup"><span data-stu-id="baaaa-151">Mapped drives</span></span>

<span data-ttu-id="baaaa-152">권고 **결과는** 일부 매핑된 드라이브가 있지만 권장되지 않음을 의미합니다.</span><span class="sxs-lookup"><span data-stu-id="baaaa-152">An **Advisory** result means that you have some mapped drives, which aren't recommended.</span></span> <span data-ttu-id="baaaa-153">자세한 내용은 [Microsoft Managed Desktop용 매핑된 드라이브 준비를 참조하세요.](mapped-drives.md)</span><span class="sxs-lookup"><span data-stu-id="baaaa-153">For more information, see [Prepare mapped drives for Microsoft Managed Desktop](mapped-drives.md).</span></span>

#### <a name="print-queues"></a><span data-ttu-id="baaaa-154">인쇄 큐</span><span class="sxs-lookup"><span data-stu-id="baaaa-154">Print queues</span></span>

<span data-ttu-id="baaaa-155">권고 **결과는** 일부 미해결 인쇄 큐가 있는 것으로, 권장되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="baaaa-155">An **Advisory** result means that you have some outstanding print queues, which aren't recommended.</span></span> <span data-ttu-id="baaaa-156">한 가지 해결 방법은 클라우드 인쇄를 사용하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="baaaa-156">One solution is to use cloud printing.</span></span> <span data-ttu-id="baaaa-157">자세한 내용은 Microsoft Managed Desktop에 대한 인쇄 [리소스 준비를 참조하세요.](printing.md)</span><span class="sxs-lookup"><span data-stu-id="baaaa-157">For more information, see [Prepare printing resources for Microsoft Managed Desktop](printing.md).</span></span>

#### <a name="proxies"></a><span data-ttu-id="baaaa-158">Proxies</span><span class="sxs-lookup"><span data-stu-id="baaaa-158">Proxies</span></span>

<span data-ttu-id="baaaa-159">권고 **결과는** 사용 중 프록시 서버가 있는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="baaaa-159">An **Advisory** result means that you have a proxy server in use.</span></span> <span data-ttu-id="baaaa-160">자세한 내용은 [Microsoft Managed Desktop의 네트워크 구성을 참조하세요.](network.md)</span><span class="sxs-lookup"><span data-stu-id="baaaa-160">For more information, see [Network configuration for Microsoft Managed Desktop](network.md).</span></span>

