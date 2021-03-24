---
title: 끝점용 Microsoft Defender에 대한 최소 요구 사항
description: 서비스에 대한 장치 온보드에 대한 라이선스 요구 사항 및 요구 사항 이해
keywords: 최소 요구 사항, 라이선스, 비교 표
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 7581c606a7903bd6d32c1e192f35992899289f30
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51069436"
---
# <a name="minimum-requirements-for-microsoft-defender-for-endpoint"></a><span data-ttu-id="8bfc1-104">끝점용 Microsoft Defender에 대한 최소 요구 사항</span><span class="sxs-lookup"><span data-stu-id="8bfc1-104">Minimum requirements for Microsoft Defender for Endpoint</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="8bfc1-105">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="8bfc1-105">**Applies to:**</span></span>
- [<span data-ttu-id="8bfc1-106">엔드포인트용 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="8bfc1-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2146631)
- [<span data-ttu-id="8bfc1-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="8bfc1-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="8bfc1-108">끝점용 Microsoft Defender를 경험하고 싶나요?</span><span class="sxs-lookup"><span data-stu-id="8bfc1-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="8bfc1-109">무료 평가판에 등록합니다.</span><span class="sxs-lookup"><span data-stu-id="8bfc1-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)


<span data-ttu-id="8bfc1-110">장치에 서비스를 온보드하기 위한 몇 가지 최소 요구 사항이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8bfc1-110">There are some minimum requirements for onboarding devices to the service.</span></span> <span data-ttu-id="8bfc1-111">서비스에 장치를 온보드하기 위한 라이선스, 하드웨어 및 소프트웨어 요구 사항 및 기타 구성 설정에 대해 자세히 알아보습니다.</span><span class="sxs-lookup"><span data-stu-id="8bfc1-111">Learn about the licensing, hardware and software requirements, and other configuration settings to onboard devices to the service.</span></span>

> <span data-ttu-id="8bfc1-112">끝점용 Microsoft Defender를 경험하고 싶나요?</span><span class="sxs-lookup"><span data-stu-id="8bfc1-112">Want to experience Microsoft Defender for Endpoint?</span></span> <span data-ttu-id="8bfc1-113">[무료 평가판에 등록합니다.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-minreqs-abovefoldlink)</span><span class="sxs-lookup"><span data-stu-id="8bfc1-113">[Sign up for a free trial](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-minreqs-abovefoldlink).</span></span>

> [!TIP]
> - <span data-ttu-id="8bfc1-114">Endpoint용 Defender: Endpoint 기술 커뮤니티용 [Defender의 최신 향상에 대해 자세히 알아보습니다.](https://techcommunity.microsoft.com/t5/Windows-Defender-Advanced-Threat/ct-p/WindowsDefenderAdvanced)</span><span class="sxs-lookup"><span data-stu-id="8bfc1-114">Learn about the latest enhancements in Defender for Endpoint: [Defender for Endpoint Tech Community](https://techcommunity.microsoft.com/t5/Windows-Defender-Advanced-Threat/ct-p/WindowsDefenderAdvanced).</span></span>
> - <span data-ttu-id="8bfc1-115">Endpoint용 Defender는 최근 MITRE 평가에서 업계를 선도하는 광학 및 감지 기능을 보여 주었다.</span><span class="sxs-lookup"><span data-stu-id="8bfc1-115">Defender for Endpoint demonstrated industry-leading optics and detection capabilities in the recent MITRE evaluation.</span></span> <span data-ttu-id="8bfc1-116">읽기: [MITRE ATT의 인사이트&CK 기반 평가.](https://cloudblogs.microsoft.com/microsoftsecure/2018/12/03/insights-from-the-mitre-attack-based-evaluation-of-windows-defender-atp/)</span><span class="sxs-lookup"><span data-stu-id="8bfc1-116">Read: [Insights from the MITRE ATT&CK-based evaluation](https://cloudblogs.microsoft.com/microsoftsecure/2018/12/03/insights-from-the-mitre-attack-based-evaluation-of-windows-defender-atp/).</span></span>

## <a name="licensing-requirements"></a><span data-ttu-id="8bfc1-117">라이선스 요구 사항</span><span class="sxs-lookup"><span data-stu-id="8bfc1-117">Licensing requirements</span></span>
<span data-ttu-id="8bfc1-118">끝점용 Microsoft Defender에는 다음 Microsoft 볼륨 라이선스 제품 중 하나가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="8bfc1-118">Microsoft Defender for Endpoint requires one of the following Microsoft volume licensing offers:</span></span>

- <span data-ttu-id="8bfc1-119">Windows 10 Enterprise E5</span><span class="sxs-lookup"><span data-stu-id="8bfc1-119">Windows 10 Enterprise E5</span></span>
- <span data-ttu-id="8bfc1-120">Windows 10 Education A5</span><span class="sxs-lookup"><span data-stu-id="8bfc1-120">Windows 10 Education A5</span></span>
- <span data-ttu-id="8bfc1-121">Windows 10 Enterprise E5를 포함하는 Microsoft 365 E5(M365 E5)</span><span class="sxs-lookup"><span data-stu-id="8bfc1-121">Microsoft 365 E5 (M365 E5) which includes Windows 10 Enterprise E5</span></span>
- <span data-ttu-id="8bfc1-122">Microsoft 365 A5(M365 A5)</span><span class="sxs-lookup"><span data-stu-id="8bfc1-122">Microsoft 365 A5 (M365 A5)</span></span>
- <span data-ttu-id="8bfc1-123">Microsoft 365 E5 Security</span><span class="sxs-lookup"><span data-stu-id="8bfc1-123">Microsoft 365 E5 Security</span></span>
- <span data-ttu-id="8bfc1-124">Microsoft 365 A5 보안</span><span class="sxs-lookup"><span data-stu-id="8bfc1-124">Microsoft 365 A5 Security</span></span>
- <span data-ttu-id="8bfc1-125">엔드포인트용 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="8bfc1-125">Microsoft Defender for Endpoint</span></span>

> [!NOTE]
> <span data-ttu-id="8bfc1-126">적격 라이선스 사용자는 최대 5개의 동시 장치에서 끝점용 Microsoft Defender를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8bfc1-126">Eligible licensed users may use Microsoft Defender for Endpoint on up to five concurrent devices.</span></span>
> <span data-ttu-id="8bfc1-127">끝점용 Microsoft Defender는 클라우드 솔루션 공급자(CSP)에서 구입할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8bfc1-127">Microsoft Defender for Endpoint is also available for purchase from a Cloud Solution Provider (CSP).</span></span>

<span data-ttu-id="8bfc1-128">서버용 끝점용 Microsoft Defender에는 다음 라이선스 옵션 중 하나가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="8bfc1-128">Microsoft Defender for Endpoint for servers requires one of the following licensing options:</span></span>

- [<span data-ttu-id="8bfc1-129">Azure Defender가 활성화된 Azure 보안 센터</span><span class="sxs-lookup"><span data-stu-id="8bfc1-129">Azure Security Center with Azure Defender enabled</span></span>](https://docs.microsoft.com/azure/security-center/security-center-pricing)
- <span data-ttu-id="8bfc1-130">서버용 Microsoft Defender for Server(대상 서버당 1개)</span><span class="sxs-lookup"><span data-stu-id="8bfc1-130">Microsoft Defender for Endpoint for Server (one per covered server)</span></span>

> [!NOTE]
> <span data-ttu-id="8bfc1-131">고객은 다음 사용자 라이선스 중 하나 이상에 대해 최소 50개 이상의 라이선스를 합한 경우 서버용 끝점용 Microsoft Defender에 대한 서버 라이선스(대상 서버당 OSE(운영 체제 환경))를 취득할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8bfc1-131">Customers may acquire server licenses (one per covered server Operating System Environment (OSE)) for Microsoft Defender for Endpoint for Servers if they have a combined minimum of 50 licenses for one or more of the following user licenses:</span></span>
>
> * <span data-ttu-id="8bfc1-132">엔드포인트용 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="8bfc1-132">Microsoft Defender for Endpoint</span></span>
> * <span data-ttu-id="8bfc1-133">Windows E5/A5</span><span class="sxs-lookup"><span data-stu-id="8bfc1-133">Windows E5/A5</span></span>
> * <span data-ttu-id="8bfc1-134">Microsoft 365 E5/A5</span><span class="sxs-lookup"><span data-stu-id="8bfc1-134">Microsoft 365 E5/A5</span></span>
> * <span data-ttu-id="8bfc1-135">Microsoft 365 E5/A5 보안</span><span class="sxs-lookup"><span data-stu-id="8bfc1-135">Microsoft 365 E5/A5 Security</span></span>

<span data-ttu-id="8bfc1-136">자세한 라이선스 정보는 제품 사용권 사이트를 참조하고 계정 팀과 함께 사용 약관에 대해 자세히 알아보는 방법을 참조하세요. [](https://www.microsoft.com/licensing/terms/)</span><span class="sxs-lookup"><span data-stu-id="8bfc1-136">For detailed licensing information, see the [Product Terms site](https://www.microsoft.com/licensing/terms/) and work with your account team to learn more about the terms and conditions.</span></span>

<span data-ttu-id="8bfc1-137">Windows 10 버전 기능 배열에 대한 자세한 내용은 [Windows 10 버전 비교를 참조하세요.](https://www.microsoft.com/windowsforbusiness/compare)</span><span class="sxs-lookup"><span data-stu-id="8bfc1-137">For more information on the array of features in Windows 10 editions, see [Compare Windows 10 editions](https://www.microsoft.com/windowsforbusiness/compare).</span></span>

<span data-ttu-id="8bfc1-138">Windows 10 상업용 버전 비교에 대한 자세한 비교 표는 비교 [PDF 를 참조하세요.](https://wfbdevicemanagementprod.blob.core.windows.net/windowsforbusiness/Windows10_CommercialEdition_Comparison.pdf)</span><span class="sxs-lookup"><span data-stu-id="8bfc1-138">For a detailed comparison table of Windows 10 commercial edition comparison, see the [comparison PDF](https://wfbdevicemanagementprod.blob.core.windows.net/windowsforbusiness/Windows10_CommercialEdition_Comparison.pdf).</span></span>

## <a name="browser-requirements"></a><span data-ttu-id="8bfc1-139">브라우저 요구 사항</span><span class="sxs-lookup"><span data-stu-id="8bfc1-139">Browser requirements</span></span>
<span data-ttu-id="8bfc1-140">끝점용 Defender에 대한 액세스는 다음 브라우저를 지원하여 브라우저를 통해 수행됩니다.</span><span class="sxs-lookup"><span data-stu-id="8bfc1-140">Access to Defender for Endpoint is done through a browser, supporting the following browsers:</span></span>

- <span data-ttu-id="8bfc1-141">Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="8bfc1-141">Microsoft Edge</span></span>
- <span data-ttu-id="8bfc1-142">Internet Explorer 버전 11</span><span class="sxs-lookup"><span data-stu-id="8bfc1-142">Internet Explorer version 11</span></span>
- <span data-ttu-id="8bfc1-143">Google Chrome</span><span class="sxs-lookup"><span data-stu-id="8bfc1-143">Google Chrome</span></span>

> [!NOTE]
> <span data-ttu-id="8bfc1-144">다른 브라우저가 작동할 수 있는 반면 언급된 브라우저는 지원되는 브라우저입니다.</span><span class="sxs-lookup"><span data-stu-id="8bfc1-144">While other browsers might work, the mentioned browsers are the ones supported.</span></span>


## <a name="hardware-and-software-requirements"></a><span data-ttu-id="8bfc1-145">하드웨어 및 소프트웨어 요구 사항</span><span class="sxs-lookup"><span data-stu-id="8bfc1-145">Hardware and software requirements</span></span>

### <a name="supported-windows-versions"></a><span data-ttu-id="8bfc1-146">지원되는 Windows 버전</span><span class="sxs-lookup"><span data-stu-id="8bfc1-146">Supported Windows versions</span></span>
- <span data-ttu-id="8bfc1-147">Windows 7 SP1 Enterprise(지원을 위해[ESU가 필요합니다.)](https://docs.microsoft.com/troubleshoot/windows-client/windows-7-eos-faq/windows-7-extended-security-updates-faq)</span><span class="sxs-lookup"><span data-stu-id="8bfc1-147">Windows 7 SP1 Enterprise ([Requires ESU for support](https://docs.microsoft.com/troubleshoot/windows-client/windows-7-eos-faq/windows-7-extended-security-updates-faq).)</span></span>
- <span data-ttu-id="8bfc1-148">Windows 7 SP1 Pro(지원을 위해[ESU가 필요합니다.)](https://docs.microsoft.com/troubleshoot/windows-client/windows-7-eos-faq/windows-7-extended-security-updates-faq)</span><span class="sxs-lookup"><span data-stu-id="8bfc1-148">Windows 7 SP1 Pro ([Requires ESU for support](https://docs.microsoft.com/troubleshoot/windows-client/windows-7-eos-faq/windows-7-extended-security-updates-faq).)</span></span>
- <span data-ttu-id="8bfc1-149">Windows 8.1 Enterprise</span><span class="sxs-lookup"><span data-stu-id="8bfc1-149">Windows 8.1 Enterprise</span></span>
- <span data-ttu-id="8bfc1-150">Windows 8.1 Pro</span><span class="sxs-lookup"><span data-stu-id="8bfc1-150">Windows 8.1 Pro</span></span>
- <span data-ttu-id="8bfc1-151">Windows 10 Enterprise</span><span class="sxs-lookup"><span data-stu-id="8bfc1-151">Windows 10 Enterprise</span></span>
- [<span data-ttu-id="8bfc1-152">Windows 10 Enterprise LTSC</span><span class="sxs-lookup"><span data-stu-id="8bfc1-152">Windows 10 Enterprise LTSC</span></span>](https://docs.microsoft.com/windows/whats-new/ltsc/)
- <span data-ttu-id="8bfc1-153">Windows 10 Education</span><span class="sxs-lookup"><span data-stu-id="8bfc1-153">Windows 10 Education</span></span>
- <span data-ttu-id="8bfc1-154">Windows 10 Pro</span><span class="sxs-lookup"><span data-stu-id="8bfc1-154">Windows 10 Pro</span></span>
- <span data-ttu-id="8bfc1-155">Windows 10 Pro Education</span><span class="sxs-lookup"><span data-stu-id="8bfc1-155">Windows 10 Pro Education</span></span>
- <span data-ttu-id="8bfc1-156">Windows 서버</span><span class="sxs-lookup"><span data-stu-id="8bfc1-156">Windows server</span></span>
  - <span data-ttu-id="8bfc1-157">Windows Server 2008 R2 SP1</span><span class="sxs-lookup"><span data-stu-id="8bfc1-157">Windows Server 2008 R2 SP1</span></span>
  - <span data-ttu-id="8bfc1-158">Windows Server 2012 R2</span><span class="sxs-lookup"><span data-stu-id="8bfc1-158">Windows Server 2012 R2</span></span>
  - <span data-ttu-id="8bfc1-159">Windows Server 2016</span><span class="sxs-lookup"><span data-stu-id="8bfc1-159">Windows Server 2016</span></span>
  - <span data-ttu-id="8bfc1-160">Windows Server, 버전 1803 이상</span><span class="sxs-lookup"><span data-stu-id="8bfc1-160">Windows Server, version 1803 or later</span></span>
  - <span data-ttu-id="8bfc1-161">Windows Server 2019</span><span class="sxs-lookup"><span data-stu-id="8bfc1-161">Windows Server 2019</span></span>
- <span data-ttu-id="8bfc1-162">Windows Virtual Desktop</span><span class="sxs-lookup"><span data-stu-id="8bfc1-162">Windows Virtual Desktop</span></span>

<span data-ttu-id="8bfc1-163">네트워크의 장치는 이러한 버전 중 하나를 실행해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8bfc1-163">Devices on your network must be running one of these editions.</span></span>

<span data-ttu-id="8bfc1-164">디바이스의 Endpoint용 Defender에 대한 하드웨어 요구 사항은 지원되는 버전에서 동일합니다.</span><span class="sxs-lookup"><span data-stu-id="8bfc1-164">The hardware requirements for Defender for Endpoint on devices are the same for the supported editions.</span></span>

> [!NOTE]
> <span data-ttu-id="8bfc1-165">모바일 버전의 Windows(예: Windows CE 및 Windows 10 Mobile)를 실행하는 컴퓨터는 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="8bfc1-165">Machines running mobile versions of Windows (such as Windows CE and Windows 10 Mobile) are not supported.</span></span>
>
> <span data-ttu-id="8bfc1-166">Windows 10 Enterprise 2016 LTSB를 실행하는 가상 컴퓨터는 비 Microsoft 가상화 플랫폼에서 실행되는 경우 성능 문제가 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8bfc1-166">Virtual Machines running Windows 10 Enterprise 2016 LTSB may encounter performance issues if run on non-Microsoft virtualization platforms.</span></span>
>
> <span data-ttu-id="8bfc1-167">가상 환경의 경우 Windows 10 Enterprise LTSC 2019 이상을 사용하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="8bfc1-167">For virtual environments, we recommend using Windows 10 Enterprise LTSC 2019 or later.</span></span>


### <a name="other-supported-operating-systems"></a><span data-ttu-id="8bfc1-168">기타 지원되는 운영 체제</span><span class="sxs-lookup"><span data-stu-id="8bfc1-168">Other supported operating systems</span></span>
- <span data-ttu-id="8bfc1-169">Android</span><span class="sxs-lookup"><span data-stu-id="8bfc1-169">Android</span></span>
- <span data-ttu-id="8bfc1-170">Linux</span><span class="sxs-lookup"><span data-stu-id="8bfc1-170">Linux</span></span>
- <span data-ttu-id="8bfc1-171">macOS</span><span class="sxs-lookup"><span data-stu-id="8bfc1-171">macOS</span></span>

> [!NOTE]
> <span data-ttu-id="8bfc1-172">통합을 위해 Endpoint용 Defender와 호환되는 정확한 Linux 배포 및 Android 및 macOS 버전을 알아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8bfc1-172">You'll need to know the exact Linux distributions and versions of Android and macOS that are compatible with Defender for Endpoint for the integration to work.</span></span>



### <a name="network-and-data-storage-and-configuration-requirements"></a><span data-ttu-id="8bfc1-173">네트워크 및 데이터 저장소 및 구성 요구 사항</span><span class="sxs-lookup"><span data-stu-id="8bfc1-173">Network and data storage and configuration requirements</span></span>
<span data-ttu-id="8bfc1-174">온보딩 마법사를 처음 실행할 때 끝점 관련 정보에 대한 Microsoft Defender가 저장되는 위치(유럽 연합, 영국 또는 미국 데이터 센터)를 선택해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8bfc1-174">When you run the onboarding wizard for the first time, you must choose where your Microsoft Defender for Endpoint-related information is stored: in the European Union, the United Kingdom, or the United States datacenter.</span></span>

> [!NOTE]
> - <span data-ttu-id="8bfc1-175">처음 설치한 후 데이터 저장소 위치를 변경할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="8bfc1-175">You cannot change your data storage location after the first-time setup.</span></span>
> - <span data-ttu-id="8bfc1-176">Microsoft에서 데이터를 저장하는 위치 및 방법에 대한 자세한 내용은 Endpoint 데이터 저장소 및 개인 정보 보호를 위한 [Microsoft Defender를](data-storage-privacy.md) 검토하세요.</span><span class="sxs-lookup"><span data-stu-id="8bfc1-176">Review the [Microsoft Defender for Endpoint data storage and privacy](data-storage-privacy.md) for more information on where and how Microsoft stores your data.</span></span>


### <a name="diagnostic-data-settings"></a><span data-ttu-id="8bfc1-177">진단 데이터 설정</span><span class="sxs-lookup"><span data-stu-id="8bfc1-177">Diagnostic data settings</span></span>

> [!NOTE]
> <span data-ttu-id="8bfc1-178">끝점용 Microsoft Defender는 사용하도록 설정된 경우 특정 진단 수준이 필요하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="8bfc1-178">Microsoft Defender for Endpoint doesn't require any specific diagnostic level as long as it's enabled.</span></span>

<span data-ttu-id="8bfc1-179">조직의 모든 장치에서 진단 데이터 서비스가 사용하도록 설정되어 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="8bfc1-179">Make sure that the diagnostic data service is enabled on all the devices in your organization.</span></span>
<span data-ttu-id="8bfc1-180">기본적으로 이 서비스는 사용하도록 설정되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8bfc1-180">By default, this service is enabled.</span></span> <span data-ttu-id="8bfc1-181">센서 데이터를 얻을 수 있도록 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="8bfc1-181">It's good practice to check to ensure that you'll get sensor data from them.</span></span>

<span data-ttu-id="8bfc1-182">**명령줄을 사용하여 Windows 10 진단** 데이터 서비스 시작 유형을 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8bfc1-182">**Use the command line to check the Windows 10 diagnostic data service startup type**:</span></span>

1. <span data-ttu-id="8bfc1-183">디바이스에서 상승된 명령줄 프롬프트를 니다.</span><span class="sxs-lookup"><span data-stu-id="8bfc1-183">Open an elevated command-line prompt on the device:</span></span>

   1.  <span data-ttu-id="8bfc1-184">**시작**(으)로 이동하고 **cmd** 를 입력하십시오.</span><span class="sxs-lookup"><span data-stu-id="8bfc1-184">Go to **Start** and type **cmd**.</span></span>

   1.  <span data-ttu-id="8bfc1-185">**명령 프롬프트** 을(를) 마우스 오른쪽 버튼으로 클릭하고 **관리자**(으)로 실행을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="8bfc1-185">Right-click **Command prompt** and select **Run as administrator**.</span></span>

2. <span data-ttu-id="8bfc1-186">다음 명령을 입력하고 **Enter를 누를 수 있습니다.**</span><span class="sxs-lookup"><span data-stu-id="8bfc1-186">Enter the following command, and press **Enter**:</span></span>

   ```console
   sc qc diagtrack
   ```

   <span data-ttu-id="8bfc1-187">서비스가 사용하도록 설정된 경우 결과는 다음 스크린샷과 같아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8bfc1-187">If the service is enabled, then the result should look like the following screenshot:</span></span>

   ![diagtrack에 대한 sc 쿼리 명령의 결과](images/windefatp-sc-qc-diagtrack.png)


<span data-ttu-id="8bfc1-189">서비스가 에 대해 로 설정되지 않은  경우 START_TYPE 자동으로 시작 **AUTO_START.**</span><span class="sxs-lookup"><span data-stu-id="8bfc1-189">You'll need to set the service to automatically start if the **START_TYPE** is not set to **AUTO_START**.</span></span>


<span data-ttu-id="8bfc1-190">**명령줄을 사용하여 Windows 10 진단 데이터 서비스가 자동으로 시작될 수 있도록 설정합니다.**</span><span class="sxs-lookup"><span data-stu-id="8bfc1-190">**Use the command line to set the Windows 10 diagnostic data service to automatically start:**</span></span>

1.  <span data-ttu-id="8bfc1-191">끝점에서 상승된 명령줄 프롬프트를 여는 경우:</span><span class="sxs-lookup"><span data-stu-id="8bfc1-191">Open an elevated command-line prompt on the endpoint:</span></span>

    1. <span data-ttu-id="8bfc1-192">**시작**(으)로 이동하고 **cmd** 를 입력하십시오.</span><span class="sxs-lookup"><span data-stu-id="8bfc1-192">Go to **Start** and type **cmd**.</span></span>

    1. <span data-ttu-id="8bfc1-193">**명령 프롬프트** 을(를) 마우스 오른쪽 버튼으로 클릭하고 **관리자**(으)로 실행을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="8bfc1-193">Right-click **Command prompt** and select **Run as administrator**.</span></span>

2.  <span data-ttu-id="8bfc1-194">다음 명령을 입력하고 **Enter를 누를 수 있습니다.**</span><span class="sxs-lookup"><span data-stu-id="8bfc1-194">Enter the following command, and press **Enter**:</span></span>

    ```console
    sc config diagtrack start=auto
    ```

3.  <span data-ttu-id="8bfc1-195">성공 메시지가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="8bfc1-195">A success message is displayed.</span></span> <span data-ttu-id="8bfc1-196">다음 명령을 입력하여 변경을 확인하고 **Enter를 누르고 :**</span><span class="sxs-lookup"><span data-stu-id="8bfc1-196">Verify the change by entering the following command, and press **Enter**:</span></span>

    ```console
    sc qc diagtrack
    ```


#### <a name="internet-connectivity"></a><span data-ttu-id="8bfc1-197">인터넷 연결</span><span class="sxs-lookup"><span data-stu-id="8bfc1-197">Internet connectivity</span></span>
<span data-ttu-id="8bfc1-198">직접 또는 프록시를 통해 디바이스에서 인터넷에 연결해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8bfc1-198">Internet connectivity on devices is required either directly or through proxy.</span></span>

<span data-ttu-id="8bfc1-199">Endpoint용 Defender 센서는 일별 평균 대역폭 5MB를 사용하여 Endpoint 클라우드 서비스용 Defender와 통신하고 사이버 데이터를 보고할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8bfc1-199">The Defender for Endpoint sensor can utilize a daily average bandwidth of 5 MB to communicate with the Defender for Endpoint cloud service and report cyber data.</span></span> <span data-ttu-id="8bfc1-200">파일 업로드 및 조사 패키지 컬렉션과 같은 일회성 활동은 이 일별 평균 대역폭에 포함되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="8bfc1-200">One-off activities such as file uploads and investigation package collection are not included in this daily average bandwidth.</span></span>

<span data-ttu-id="8bfc1-201">추가 프록시 구성 설정에 대한 자세한 내용은 장치 프록시 및 인터넷 연결 설정 [구성을 참조하세요.](configure-proxy-internet.md)</span><span class="sxs-lookup"><span data-stu-id="8bfc1-201">For more information on additional proxy configuration settings, see [Configure device proxy and Internet connectivity settings](configure-proxy-internet.md).</span></span>

<span data-ttu-id="8bfc1-202">장치를 온보드하기 전에 진단 데이터 서비스를 사용하도록 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8bfc1-202">Before you onboard devices, the diagnostic data service must be enabled.</span></span> <span data-ttu-id="8bfc1-203">서비스는 Windows 10에서 기본적으로 사용하도록 설정되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8bfc1-203">The service is enabled by default in Windows 10.</span></span>


## <a name="microsoft-defender-antivirus-configuration-requirement"></a><span data-ttu-id="8bfc1-204">Microsoft Defender 바이러스 백신 구성 요구 사항</span><span class="sxs-lookup"><span data-stu-id="8bfc1-204">Microsoft Defender Antivirus configuration requirement</span></span>
<span data-ttu-id="8bfc1-205">Endpoint용 Defender 에이전트는 Microsoft Defender 바이러스 백신이 파일을 검색하고 해당 파일에 대한 정보를 제공하는 기능을 사용하는지 여부에 따라 달라 습니다.</span><span class="sxs-lookup"><span data-stu-id="8bfc1-205">The Defender for Endpoint agent depends on the ability of Microsoft Defender Antivirus to scan files and provide information about them.</span></span>

<span data-ttu-id="8bfc1-206">Microsoft Defender 바이러스 백신이 활성 맬웨어 방지인지 여부에 관계 없는 끝점 장치용 Defender에서 보안 인텔리전스 업데이트를 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="8bfc1-206">Configure Security intelligence updates on the Defender for Endpoint devices whether Microsoft Defender Antivirus is the active antimalware or not.</span></span> <span data-ttu-id="8bfc1-207">자세한 내용은 Microsoft Defender 바이러스 백신 업데이트 관리 및 [기준 적용을 참조하세요.](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/manage-updates-baselines-microsoft-defender-antivirus)</span><span class="sxs-lookup"><span data-stu-id="8bfc1-207">For more information, see [Manage Microsoft Defender Antivirus updates and apply baselines](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/manage-updates-baselines-microsoft-defender-antivirus).</span></span>

<span data-ttu-id="8bfc1-208">Microsoft Defender 바이러스 백신이 조직에서 활성 맬웨어 방지가 아니고 Endpoint 서비스용 Defender를 사용하는 경우 Microsoft Defender 바이러스 백신은 수동 모드로 전환됩니다.</span><span class="sxs-lookup"><span data-stu-id="8bfc1-208">When Microsoft Defender Antivirus is not the active antimalware in your organization and you use the Defender for Endpoint service, Microsoft Defender Antivirus goes on passive mode.</span></span>

<span data-ttu-id="8bfc1-209">조직에서 그룹 정책 또는 기타 방법을 통해 Microsoft Defender 바이러스 백신을 해제한 경우 온보딩된 장치를 이 그룹 정책에서 제외해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8bfc1-209">If your organization has turned off Microsoft Defender Antivirus through group policy or other methods, devices that are onboarded must be excluded from this group policy.</span></span>

<span data-ttu-id="8bfc1-210">온보딩 서버가 Microsoft Defender 바이러스 백신이 서버에서 활성 맬웨어 방지가 아닌 경우 수동 모드로 전환하거나 제거하도록 Microsoft Defender 바이러스 백신을 구성해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8bfc1-210">If you are onboarding servers and Microsoft Defender Antivirus is not the active antimalware on your servers, Microsoft Defender Antivirus will either need to be configured to go on passive mode or uninstalled.</span></span> <span data-ttu-id="8bfc1-211">구성은 서버 버전에 따라 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="8bfc1-211">The configuration is dependent on the server version.</span></span> <span data-ttu-id="8bfc1-212">자세한 내용은 [Microsoft Defender 바이러스 백신 호환성을 참조하세요.](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus-compatibility.md)</span><span class="sxs-lookup"><span data-stu-id="8bfc1-212">For more information, see [Microsoft Defender Antivirus compatibility](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus-compatibility.md).</span></span>

> [!NOTE]
> <span data-ttu-id="8bfc1-213">일반 그룹 정책은 변조 방지에 적용되지 않습니다. 변조 방지가 설정될 때 Microsoft Defender 바이러스 백신 설정에 대한 변경 내용은 무시됩니다.</span><span class="sxs-lookup"><span data-stu-id="8bfc1-213">Your regular group policy doesn't apply to Tamper Protection, and changes to Microsoft Defender Antivirus settings will be ignored when Tamper Protection is on.</span></span>


## <a name="microsoft-defender-antivirus-early-launch-antimalware-elam-driver-is-enabled"></a><span data-ttu-id="8bfc1-214">Microsoft Defender 바이러스 백신 ELAM(맬웨어 방지 조기 실행) 드라이버가 사용하도록 설정되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8bfc1-214">Microsoft Defender Antivirus Early Launch Antimalware (ELAM) driver is enabled</span></span>
<span data-ttu-id="8bfc1-215">장치에서 Microsoft Defender 바이러스 백신을 기본 맬웨어 방지 제품으로 실행하는 경우 끝점용 Defender 에이전트가 성공적으로 온보딩됩니다.</span><span class="sxs-lookup"><span data-stu-id="8bfc1-215">If you're running Microsoft Defender Antivirus as the primary antimalware product on your devices, the Defender for Endpoint agent will successfully onboard.</span></span>

<span data-ttu-id="8bfc1-216">타사 맬웨어 방지 클라이언트를 실행하고 모바일 장치 관리 솔루션 또는 Microsoft Endpoint Manager(현재 분기)를 사용하는 경우 Microsoft Defender 바이러스 백신 ELAM 드라이버를 사용하도록 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8bfc1-216">If you're running a third-party antimalware client and use Mobile Device Management solutions or Microsoft Endpoint Manager (current branch), you'll need to ensure that the Microsoft Defender Antivirus ELAM driver is enabled.</span></span> <span data-ttu-id="8bfc1-217">자세한 내용은 정책에서 Microsoft Defender 바이러스 백신이 사용하지 [않도록 설정되지 않은지 확인을 참조하세요.](troubleshoot-onboarding.md#ensure-that-microsoft-defender-antivirus-is-not-disabled-by-a-policy)</span><span class="sxs-lookup"><span data-stu-id="8bfc1-217">For more information, see [Ensure that Microsoft Defender Antivirus is not disabled by policy](troubleshoot-onboarding.md#ensure-that-microsoft-defender-antivirus-is-not-disabled-by-a-policy).</span></span>


## <a name="related-topics"></a><span data-ttu-id="8bfc1-218">관련 항목</span><span class="sxs-lookup"><span data-stu-id="8bfc1-218">Related topics</span></span>
- [<span data-ttu-id="8bfc1-219">끝점 배포를 위한 Microsoft Defender 설정</span><span class="sxs-lookup"><span data-stu-id="8bfc1-219">Set up Microsoft Defender for Endpoint deployment</span></span>](production-deployment.md)
- [<span data-ttu-id="8bfc1-220">장치 온보드</span><span class="sxs-lookup"><span data-stu-id="8bfc1-220">Onboard devices</span></span>](onboard-configure.md)
