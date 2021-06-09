---
title: 엔드포인트용 Microsoft Defender(미국 정부 고객용)
description: 사용 가능한 미국 정부 고객 요구 사항 및 기능용 Microsoft Defender for Endpoint에 대해 자세히 알아보시고
keywords: government, gcc, high, requirements, capabilities, defender, Microsoft Defender for Endpoint, endpoint, dod
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
ms.openlocfilehash: 7956c1454cd7bd962eda984cc9d93be9824d7458
ms.sourcegitcommit: 50908a93554290ff1157b58d0a868a33e012513c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/08/2021
ms.locfileid: "52822108"
---
# <a name="microsoft-defender-for-endpoint-for-us-government-customers"></a><span data-ttu-id="a368b-104">엔드포인트용 Microsoft Defender(미국 정부 고객용)</span><span class="sxs-lookup"><span data-stu-id="a368b-104">Microsoft Defender for Endpoint for US Government customers</span></span>

<span data-ttu-id="a368b-105">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="a368b-105">**Applies to:**</span></span>
- [<span data-ttu-id="a368b-106">엔드포인트용 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="a368b-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)

<span data-ttu-id="a368b-107">Azure US Government 환경에서 구축된 미국 정부 고객을 위한 끝점용 Microsoft Defender는 Azure Commercial의 Endpoint용 Defender와 동일한 기본 기술을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="a368b-107">Microsoft Defender for Endpoint for US Government customers, built in the Azure US Government environment, uses the same underlying technologies as Defender for Endpoint in Azure Commercial.</span></span>

<span data-ttu-id="a368b-108">이 제품은 GCC, GCC High 및 DoD 고객에게 제공되고 상업용 버전과 동일한 예방, 탐지, 조사 및 수정을 기반으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="a368b-108">This offering is available to GCC, GCC High, and DoD customers and is based on the same prevention, detection, investigation, and remediation as the commercial version.</span></span> <span data-ttu-id="a368b-109">그러나 이 제공 기능에 대한 기능의 가용성에는 몇 가지 차이가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a368b-109">However, there are some differences in the availability of capabilities for this offering.</span></span>

> [!NOTE]
> <span data-ttu-id="a368b-110">Commercial에서 Endpoint용 Defender를 GCC 고객인 경우 공개 설명서 페이지를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="a368b-110">If you are a GCC customer using Defender for Endpoint in Commercial, please refer to the public documentation pages.</span></span>

## <a name="licensing-requirements"></a><span data-ttu-id="a368b-111">라이선스 요구사항</span><span class="sxs-lookup"><span data-stu-id="a368b-111">Licensing requirements</span></span>
<span data-ttu-id="a368b-112">미국 정부 고객을 위한 끝점용 Microsoft Defender에는 다음 Microsoft 볼륨 라이선싱 제품 중 하나가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="a368b-112">Microsoft Defender for Endpoint for US Government customers requires one of the following Microsoft volume licensing offers:</span></span>

### <a name="desktop-licensing"></a><span data-ttu-id="a368b-113">데스크톱 라이선싱</span><span class="sxs-lookup"><span data-stu-id="a368b-113">Desktop licensing</span></span>
<span data-ttu-id="a368b-114">GCC</span><span class="sxs-lookup"><span data-stu-id="a368b-114">GCC</span></span> | <span data-ttu-id="a368b-115">GCC 높음</span><span class="sxs-lookup"><span data-stu-id="a368b-115">GCC High</span></span> | <span data-ttu-id="a368b-116">DoD</span><span class="sxs-lookup"><span data-stu-id="a368b-116">DoD</span></span>
:---|:---|:---
<span data-ttu-id="a368b-117">Windows 10 Enterprise E5 GCC</span><span class="sxs-lookup"><span data-stu-id="a368b-117">Windows 10 Enterprise E5 GCC</span></span> | <span data-ttu-id="a368b-118">Windows 10 Enterprise E5 for GCC High</span><span class="sxs-lookup"><span data-stu-id="a368b-118">Windows 10 Enterprise E5 for GCC High</span></span> | <span data-ttu-id="a368b-119">Windows 10 Enterprise DOD용 E5</span><span class="sxs-lookup"><span data-stu-id="a368b-119">Windows 10 Enterprise E5 for DOD</span></span>
| | <span data-ttu-id="a368b-120">Microsoft 365 E5 대한 GCC 높음</span><span class="sxs-lookup"><span data-stu-id="a368b-120">Microsoft 365 E5 for GCC High</span></span> | <span data-ttu-id="a368b-121">Microsoft 365 DOD용 G5</span><span class="sxs-lookup"><span data-stu-id="a368b-121">Microsoft 365 G5 for DOD</span></span>
| | <span data-ttu-id="a368b-122">Microsoft 365 G5 High용 GCC 보안</span><span class="sxs-lookup"><span data-stu-id="a368b-122">Microsoft 365 G5 Security for GCC High</span></span> | <span data-ttu-id="a368b-123">Microsoft 365 DOD용 G5 보안</span><span class="sxs-lookup"><span data-stu-id="a368b-123">Microsoft 365 G5 Security for DOD</span></span>
<span data-ttu-id="a368b-124">끝점용 Microsoft Defender - GCC</span><span class="sxs-lookup"><span data-stu-id="a368b-124">Microsoft Defender for Endpoint - GCC</span></span> | <span data-ttu-id="a368b-125">Microsoft Defender for Endpoint for GCC High</span><span class="sxs-lookup"><span data-stu-id="a368b-125">Microsoft Defender for Endpoint for GCC High</span></span> | <span data-ttu-id="a368b-126">DOD용 끝점용 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="a368b-126">Microsoft Defender for Endpoint for DOD</span></span>

### <a name="server-licensing"></a><span data-ttu-id="a368b-127">서버 라이선스</span><span class="sxs-lookup"><span data-stu-id="a368b-127">Server licensing</span></span>
<span data-ttu-id="a368b-128">GCC</span><span class="sxs-lookup"><span data-stu-id="a368b-128">GCC</span></span> | <span data-ttu-id="a368b-129">GCC 높음</span><span class="sxs-lookup"><span data-stu-id="a368b-129">GCC High</span></span> | <span data-ttu-id="a368b-130">DoD</span><span class="sxs-lookup"><span data-stu-id="a368b-130">DoD</span></span>
:---|:---|:---
<span data-ttu-id="a368b-131">Microsoft Defender for Endpoint Server GCC</span><span class="sxs-lookup"><span data-stu-id="a368b-131">Microsoft Defender for Endpoint Server GCC</span></span> | <span data-ttu-id="a368b-132">Microsoft Defender for Endpoint Server for GCC High</span><span class="sxs-lookup"><span data-stu-id="a368b-132">Microsoft Defender for Endpoint Server for GCC High</span></span> | <span data-ttu-id="a368b-133">DOD용 끝점 서버용 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="a368b-133">Microsoft Defender for Endpoint Server for DOD</span></span>
<span data-ttu-id="a368b-134">서버용 Azure Defender</span><span class="sxs-lookup"><span data-stu-id="a368b-134">Azure Defender for Servers</span></span> | <span data-ttu-id="a368b-135">서버용 Azure Defender - 정부</span><span class="sxs-lookup"><span data-stu-id="a368b-135">Azure Defender for Servers - Government</span></span> | <span data-ttu-id="a368b-136">서버용 Azure Defender - 정부</span><span class="sxs-lookup"><span data-stu-id="a368b-136">Azure Defender for Servers - Government</span></span>

<br />

## <a name="portal-urls"></a><span data-ttu-id="a368b-137">포털 URL</span><span class="sxs-lookup"><span data-stu-id="a368b-137">Portal URLs</span></span>
<span data-ttu-id="a368b-138">다음은 미국 정부 고객을 위한 Microsoft Defender for Endpoint 포털 URL입니다.</span><span class="sxs-lookup"><span data-stu-id="a368b-138">The following are the Microsoft Defender for Endpoint portal URLs for US Government customers:</span></span>

<span data-ttu-id="a368b-139">고객 유형</span><span class="sxs-lookup"><span data-stu-id="a368b-139">Customer type</span></span> | <span data-ttu-id="a368b-140">포털 URL</span><span class="sxs-lookup"><span data-stu-id="a368b-140">Portal URL</span></span>
:---|:---
<span data-ttu-id="a368b-141">GCC</span><span class="sxs-lookup"><span data-stu-id="a368b-141">GCC</span></span> | https://gcc.securitycenter.microsoft.us
<span data-ttu-id="a368b-142">GCC 높음</span><span class="sxs-lookup"><span data-stu-id="a368b-142">GCC High</span></span> | https://securitycenter.microsoft.us
<span data-ttu-id="a368b-143">DoD</span><span class="sxs-lookup"><span data-stu-id="a368b-143">DoD</span></span> | https://securitycenter.microsoft.us

<br />

## <a name="endpoint-versions"></a><span data-ttu-id="a368b-144">끝점 버전</span><span class="sxs-lookup"><span data-stu-id="a368b-144">Endpoint versions</span></span>

### <a name="standalone-os-versions"></a><span data-ttu-id="a368b-145">독립 실행형 OS 버전</span><span class="sxs-lookup"><span data-stu-id="a368b-145">Standalone OS versions</span></span>
<span data-ttu-id="a368b-146">다음 OS 버전이 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="a368b-146">The following OS versions are supported:</span></span>

<span data-ttu-id="a368b-147">OS 버전</span><span class="sxs-lookup"><span data-stu-id="a368b-147">OS version</span></span> | <span data-ttu-id="a368b-148">GCC</span><span class="sxs-lookup"><span data-stu-id="a368b-148">GCC</span></span> | <span data-ttu-id="a368b-149">GCC 높음</span><span class="sxs-lookup"><span data-stu-id="a368b-149">GCC High</span></span> | <span data-ttu-id="a368b-150">DoD</span><span class="sxs-lookup"><span data-stu-id="a368b-150">DoD</span></span>
:---|:---|:---|:---
<span data-ttu-id="a368b-151">Windows 10 버전 [20H2(KB4586853](https://support.microsoft.com/help/4586853)사용)</span><span class="sxs-lookup"><span data-stu-id="a368b-151">Windows 10, version 20H2 (with [KB4586853](https://support.microsoft.com/help/4586853))</span></span> | ![예](images/svg/check-yes.svg) | ![예](images/svg/check-yes.svg) | ![예](images/svg/check-yes.svg)
<span data-ttu-id="a368b-155">Windows 10 버전 [2004(KB4586853](https://support.microsoft.com/help/4586853)사용)</span><span class="sxs-lookup"><span data-stu-id="a368b-155">Windows 10, version 2004 (with [KB4586853](https://support.microsoft.com/help/4586853))</span></span> | ![예](images/svg/check-yes.svg) | ![예](images/svg/check-yes.svg) | ![예](images/svg/check-yes.svg)
<span data-ttu-id="a368b-159">Windows 10 버전 [1909(KB4586819](https://support.microsoft.com/help/4586819)사용)</span><span class="sxs-lookup"><span data-stu-id="a368b-159">Windows 10, version 1909 (with [KB4586819](https://support.microsoft.com/help/4586819))</span></span> | ![예](images/svg/check-yes.svg) | ![예](images/svg/check-yes.svg) | ![예](images/svg/check-yes.svg)
<span data-ttu-id="a368b-163">Windows 10 버전 [1903(KB4586819](https://support.microsoft.com/help/4586819)사용)</span><span class="sxs-lookup"><span data-stu-id="a368b-163">Windows 10, version 1903 (with [KB4586819](https://support.microsoft.com/help/4586819))</span></span> | ![예](images/svg/check-yes.svg) | ![예](images/svg/check-yes.svg) | ![예](images/svg/check-yes.svg)
<span data-ttu-id="a368b-167">Windows 10 버전 [1809(KB4586839](https://support.microsoft.com/help/4586839)사용)</span><span class="sxs-lookup"><span data-stu-id="a368b-167">Windows 10, version 1809 (with [KB4586839](https://support.microsoft.com/help/4586839))</span></span> | ![예](images/svg/check-yes.svg) | ![예](images/svg/check-yes.svg) | ![예](images/svg/check-yes.svg)
<span data-ttu-id="a368b-171">Windows 10 버전 [1803(KB4598245](https://support.microsoft.com/help/4598245)사용)</span><span class="sxs-lookup"><span data-stu-id="a368b-171">Windows 10, version 1803 (with [KB4598245](https://support.microsoft.com/help/4598245))</span></span> | ![예](images/svg/check-yes.svg) | ![예](images/svg/check-yes.svg) | ![예](images/svg/check-yes.svg)
<span data-ttu-id="a368b-175">Windows 10 버전 1709</span><span class="sxs-lookup"><span data-stu-id="a368b-175">Windows 10, version 1709</span></span> | ![아니요.](images/svg/check-no.svg)<br /><span data-ttu-id="a368b-177">참고: 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="a368b-177">Note: Won't be supported</span></span> | <span data-ttu-id="a368b-178">![](images/svg/check-yes.svg) [예(KB4499147)](https://support.microsoft.com/help/4499147)</span><span class="sxs-lookup"><span data-stu-id="a368b-178">![Yes](images/svg/check-yes.svg) With [KB4499147](https://support.microsoft.com/help/4499147)</span></span><br /><span data-ttu-id="a368b-179">참고: [사용되지 않습니다.](/lifecycle/announcements/revised-end-of-service-windows-10-1709)업그레이드하십시오.</span><span class="sxs-lookup"><span data-stu-id="a368b-179">Note: [Deprecated](/lifecycle/announcements/revised-end-of-service-windows-10-1709), please upgrade</span></span> | ![아니요.](images/svg/check-no.svg)<br /><span data-ttu-id="a368b-181">참고: 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="a368b-181">Note: Won't be supported</span></span>
<span data-ttu-id="a368b-182">Windows 10 버전 1703 이전 버전</span><span class="sxs-lookup"><span data-stu-id="a368b-182">Windows 10, version 1703 and earlier</span></span> | ![아니요.](images/svg/check-no.svg)<br /><span data-ttu-id="a368b-184">참고: 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="a368b-184">Note: Won't be supported</span></span> | ![아니요.](images/svg/check-no.svg)<br /><span data-ttu-id="a368b-186">참고: 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="a368b-186">Note: Won't be supported</span></span> | ![아니요.](images/svg/check-no.svg)<br /><span data-ttu-id="a368b-188">참고: 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="a368b-188">Note: Won't be supported</span></span>
<span data-ttu-id="a368b-189">Windows Server [2019(KB4586839](https://support.microsoft.com/help/4586839)사용)</span><span class="sxs-lookup"><span data-stu-id="a368b-189">Windows Server 2019 (with [KB4586839](https://support.microsoft.com/help/4586839))</span></span> | ![예](images/svg/check-yes.svg) | ![예](images/svg/check-yes.svg) | ![예](images/svg/check-yes.svg)
<span data-ttu-id="a368b-193">Windows Server 2016</span><span class="sxs-lookup"><span data-stu-id="a368b-193">Windows Server 2016</span></span> | ![예](images/svg/check-yes.svg) | ![예](images/svg/check-yes.svg) | ![예](images/svg/check-yes.svg)
<span data-ttu-id="a368b-197">Windows Server 2012 R2</span><span class="sxs-lookup"><span data-stu-id="a368b-197">Windows Server 2012 R2</span></span> | ![예](images/svg/check-yes.svg) | ![예](images/svg/check-yes.svg) | ![예](images/svg/check-yes.svg)
<span data-ttu-id="a368b-201">Windows Server 2008 R2 SP1</span><span class="sxs-lookup"><span data-stu-id="a368b-201">Windows Server 2008 R2 SP1</span></span> | ![예](images/svg/check-yes.svg) | ![예](images/svg/check-yes.svg) | ![예](images/svg/check-yes.svg)
<span data-ttu-id="a368b-205">Windows 8.1 Enterprise</span><span class="sxs-lookup"><span data-stu-id="a368b-205">Windows 8.1 Enterprise</span></span> | ![예](images/svg/check-yes.svg) | ![예](images/svg/check-yes.svg) | ![예](images/svg/check-yes.svg)
<span data-ttu-id="a368b-209">Windows 8 Pro</span><span class="sxs-lookup"><span data-stu-id="a368b-209">Windows 8 Pro</span></span> | ![예](images/svg/check-yes.svg) | ![예](images/svg/check-yes.svg) | ![예](images/svg/check-yes.svg)
<span data-ttu-id="a368b-213">Windows 7 SP1 Enterprise</span><span class="sxs-lookup"><span data-stu-id="a368b-213">Windows 7 SP1 Enterprise</span></span> | ![예](images/svg/check-yes.svg) | ![예](images/svg/check-yes.svg) | ![예](images/svg/check-yes.svg)
<span data-ttu-id="a368b-217">Windows 7 SP1 Pro</span><span class="sxs-lookup"><span data-stu-id="a368b-217">Windows 7 SP1 Pro</span></span> | ![예](images/svg/check-yes.svg) | ![예](images/svg/check-yes.svg) | ![예](images/svg/check-yes.svg)
<span data-ttu-id="a368b-221">Linux</span><span class="sxs-lookup"><span data-stu-id="a368b-221">Linux</span></span> | ![예](images/svg/check-yes.svg) | ![예](images/svg/check-yes.svg) | ![예](images/svg/check-yes.svg)
<span data-ttu-id="a368b-225">macOS</span><span class="sxs-lookup"><span data-stu-id="a368b-225">macOS</span></span> | ![예](images/svg/check-yes.svg) | ![예](images/svg/check-yes.svg) | ![예](images/svg/check-yes.svg)
<span data-ttu-id="a368b-229">Android</span><span class="sxs-lookup"><span data-stu-id="a368b-229">Android</span></span> | ![아니요.](images/svg/check-no.svg) <span data-ttu-id="a368b-231">백로그 엔지니어링</span><span class="sxs-lookup"><span data-stu-id="a368b-231">On engineering backlog</span></span> | ![아니요.](images/svg/check-no.svg) <span data-ttu-id="a368b-233">백로그 엔지니어링</span><span class="sxs-lookup"><span data-stu-id="a368b-233">On engineering backlog</span></span> | ![아니요.](images/svg/check-no.svg) <span data-ttu-id="a368b-235">백로그 엔지니어링</span><span class="sxs-lookup"><span data-stu-id="a368b-235">On engineering backlog</span></span>
<span data-ttu-id="a368b-236">iOS</span><span class="sxs-lookup"><span data-stu-id="a368b-236">iOS</span></span> | ![아니요.](images/svg/check-no.svg) <span data-ttu-id="a368b-238">백로그 엔지니어링</span><span class="sxs-lookup"><span data-stu-id="a368b-238">On engineering backlog</span></span> | ![아니요.](images/svg/check-no.svg) <span data-ttu-id="a368b-240">백로그 엔지니어링</span><span class="sxs-lookup"><span data-stu-id="a368b-240">On engineering backlog</span></span> | ![아니요.](images/svg/check-no.svg) <span data-ttu-id="a368b-242">백로그 엔지니어링</span><span class="sxs-lookup"><span data-stu-id="a368b-242">On engineering backlog</span></span>

> [!NOTE]
> <span data-ttu-id="a368b-243">패치가 지정된 경우 올바른 환경으로 끝점에 대한 Defender를 구성하려면 장치 온보딩 전에 패치를 배포해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a368b-243">Where a patch is specified, it must be deployed prior to device onboarding in order to configure Defender for Endpoint to the correct environment.</span></span>

> [!NOTE]
> <span data-ttu-id="a368b-244">Windows 사용하여 Windows Windows 10 또는 Windows Server 2019보다 오래된 장치를 [온보 Microsoft Monitoring Agent?](configure-server-endpoints.md#option-1-onboard-by-installing-and-configuring-microsoft-monitoring-agent-mma)</span><span class="sxs-lookup"><span data-stu-id="a368b-244">Trying to onboard Windows devices older than Windows 10 or Windows Server 2019 using [Microsoft Monitoring Agent](configure-server-endpoints.md#option-1-onboard-by-installing-and-configuring-microsoft-monitoring-agent-mma)?</span></span> <span data-ttu-id="a368b-245">설치 마법사를 사용하는 경우 또는 명령줄 또는 스크립트를 사용하는 경우 "Azure [](/azure/log-analytics/log-analytics-windows-agents#install-agent-using-command-line) Cloud"에서 [](/azure/log-analytics/log-analytics-windows-agents#install-agent-using-dsc-in-azure-automation) "Azure US Government"를 선택해야 합니다. "OPINSIGHTS_WORKSPACE_AZURE_CLOUD_TYPE" 매개 변수를 1로 설정해야 합니다. [](/azure/log-analytics/log-analytics-windows-agents#install-agent-using-setup-wizard)</span><span class="sxs-lookup"><span data-stu-id="a368b-245">You'll need to choose "Azure US Government" under "Azure Cloud" if using the [setup wizard](/azure/log-analytics/log-analytics-windows-agents#install-agent-using-setup-wizard), or if using a [command line](/azure/log-analytics/log-analytics-windows-agents#install-agent-using-command-line) or a [script](/azure/log-analytics/log-analytics-windows-agents#install-agent-using-dsc-in-azure-automation) - set the "OPINSIGHTS_WORKSPACE_AZURE_CLOUD_TYPE" parameter to 1.</span></span>

### <a name="os-versions-when-using-azure-defender-for-servers"></a><span data-ttu-id="a368b-246">서버용 Azure Defender를 사용하는 경우 OS 버전</span><span class="sxs-lookup"><span data-stu-id="a368b-246">OS versions when using Azure Defender for Servers</span></span>
<span data-ttu-id="a368b-247">다음 OS 버전은 [서버용 Azure Defender를 사용할 때 지원됩니다.](/azure/security-center/security-center-wdatp)</span><span class="sxs-lookup"><span data-stu-id="a368b-247">The following OS versions are supported when using [Azure Defender for Servers](/azure/security-center/security-center-wdatp):</span></span>

<span data-ttu-id="a368b-248">OS 버전</span><span class="sxs-lookup"><span data-stu-id="a368b-248">OS version</span></span> | <span data-ttu-id="a368b-249">GCC</span><span class="sxs-lookup"><span data-stu-id="a368b-249">GCC</span></span> | <span data-ttu-id="a368b-250">GCC 높음</span><span class="sxs-lookup"><span data-stu-id="a368b-250">GCC High</span></span> | <span data-ttu-id="a368b-251">DoD</span><span class="sxs-lookup"><span data-stu-id="a368b-251">DoD</span></span>
:---|:---|:---|:---
<span data-ttu-id="a368b-252">Windows Server 2019</span><span class="sxs-lookup"><span data-stu-id="a368b-252">Windows Server 2019</span></span> | ![예](images/svg/check-yes.svg) | ![예](images/svg/check-yes.svg) | ![예](images/svg/check-yes.svg)
<span data-ttu-id="a368b-256">Windows Server 2016</span><span class="sxs-lookup"><span data-stu-id="a368b-256">Windows Server 2016</span></span> | ![예](images/svg/check-yes.svg) | ![예](images/svg/check-yes.svg) | ![예](images/svg/check-yes.svg)
<span data-ttu-id="a368b-260">Windows Server 2012 R2</span><span class="sxs-lookup"><span data-stu-id="a368b-260">Windows Server 2012 R2</span></span> | ![예](images/svg/check-yes.svg) | ![예](images/svg/check-yes.svg) | ![예](images/svg/check-yes.svg)
<span data-ttu-id="a368b-264">Windows Server 2008 R2 SP1</span><span class="sxs-lookup"><span data-stu-id="a368b-264">Windows Server 2008 R2 SP1</span></span> | ![예](images/svg/check-yes.svg) | ![예](images/svg/check-yes.svg) | ![예](images/svg/check-yes.svg)

<br />

## <a name="required-connectivity-settings"></a><span data-ttu-id="a368b-268">필수 연결 설정</span><span class="sxs-lookup"><span data-stu-id="a368b-268">Required connectivity settings</span></span>
<span data-ttu-id="a368b-269">프록시 또는 방화벽이 기본적으로 모든 트래픽을 차단하고 특정 도메인만 통과하도록 허용하는 경우 다운로드 가능한 시트에 나열된 도메인을 허용된 도메인 목록에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="a368b-269">If a proxy or firewall is blocking all traffic by default and allowing only specific domains through, add the domains listed in the downloadable sheet to the allowed domains list.</span></span>

<span data-ttu-id="a368b-270">다음 다운로드 가능한 스프레드시트에는 네트워크에서 연결할 수 있어야 하는 서비스 및 관련 URL이 나열됩니다.</span><span class="sxs-lookup"><span data-stu-id="a368b-270">The following downloadable spreadsheet lists the services and their associated URLs your network must be able to connect to.</span></span> <span data-ttu-id="a368b-271">이러한 URL에 대한 액세스를 거부하는 방화벽 또는 네트워크 필터링 규칙이 없는지 확인하거나 해당 URL에 대한 허용 규칙을 만들 수 있습니다. </span><span class="sxs-lookup"><span data-stu-id="a368b-271">Verify there are no firewall or network filtering rules that would deny access to these URLs, or create an *allow* rule specifically for them.</span></span>

<span data-ttu-id="a368b-272">도메인 목록의 스프레드시트</span><span class="sxs-lookup"><span data-stu-id="a368b-272">Spreadsheet of domains list</span></span> | <span data-ttu-id="a368b-273">설명</span><span class="sxs-lookup"><span data-stu-id="a368b-273">Description</span></span>
:-----|:-----
![끝점 URL 스프레드시트용 Microsoft Defender의 축소판 이미지](images/mdatp-urls.png)<br/> | <span data-ttu-id="a368b-275">서비스 위치, 지리적 위치 및 OS에 대한 특정 DNS 레코드의 스프레드시트입니다.</span><span class="sxs-lookup"><span data-stu-id="a368b-275">Spreadsheet of specific DNS records for service locations, geographic locations, and OS.</span></span> <br /><br />[<span data-ttu-id="a368b-276">여기에서 스프레드시트를 다운로드합니다.</span><span class="sxs-lookup"><span data-stu-id="a368b-276">Download the spreadsheet here.</span></span>](https://download.microsoft.com/download/8/a/5/8a51eee5-cd02-431c-9d78-a58b7f77c070/mde-urls.xlsx) 

<span data-ttu-id="a368b-277">자세한 내용은 장치 프록시 및 인터넷 연결 설정 [구성을 참조하세요.](configure-proxy-internet.md)</span><span class="sxs-lookup"><span data-stu-id="a368b-277">For more information, see [Configure device proxy and Internet connectivity settings](configure-proxy-internet.md).</span></span>

> [!NOTE]
> <span data-ttu-id="a368b-278">스프레드시트에는 상업용 URL도 포함되어 있습니다. "US Gov" 탭을 선택해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a368b-278">The spreadsheet contains commercial URLs as well, make sure you check the "US Gov" tabs.</span></span>
> 
> <span data-ttu-id="a368b-279">필터링할 때 "US Gov"로 레이블이 붙은 레코드와 해당 지리 열에서 특정 클라우드를 찾아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a368b-279">When filtering, look for the records labeled as "US Gov" and your specific cloud under the geography column.</span></span>

### <a name="service-backend-ip-ranges"></a><span data-ttu-id="a368b-280">서비스 백end IP 범위</span><span class="sxs-lookup"><span data-stu-id="a368b-280">Service backend IP ranges</span></span>

<span data-ttu-id="a368b-281">네트워크 장치가 DNS 기반 규칙을 지원하지 않는 경우 대신 IP 범위를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="a368b-281">If your network devices don't support DNS-based rules, use IP ranges instead.</span></span>

<span data-ttu-id="a368b-282">미국 정부 고객을 위한 끝점용 Defender는 Azure US Government 환경에서 구축되어 다음 지역에 배포됩니다.</span><span class="sxs-lookup"><span data-stu-id="a368b-282">Defender for Endpoint for US Government customers is built in the Azure US Government environment, deployed in the following regions:</span></span>

- <span data-ttu-id="a368b-283">AzureCloud.usgovtexas</span><span class="sxs-lookup"><span data-stu-id="a368b-283">AzureCloud.usgovtexas</span></span>
- <span data-ttu-id="a368b-284">AzureCloud.usgovvirginia</span><span class="sxs-lookup"><span data-stu-id="a368b-284">AzureCloud.usgovvirginia</span></span>

<span data-ttu-id="a368b-285">Azure IP 범위 및 서비스 태그 – 미국 정부 클라우드에서 [Azure IP 범위를 찾을 수 있습니다.](https://www.microsoft.com/download/details.aspx?id=57063)</span><span class="sxs-lookup"><span data-stu-id="a368b-285">You can find the Azure IP ranges in [Azure IP Ranges and Service Tags – US Government Cloud](https://www.microsoft.com/download/details.aspx?id=57063).</span></span>

> [!NOTE]
> <span data-ttu-id="a368b-286">클라우드 기반 솔루션으로 IP 주소 범위는 변경될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a368b-286">As a cloud-based solution, the IP address ranges can change.</span></span> <span data-ttu-id="a368b-287">DNS 기반 규칙으로 이동하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="a368b-287">It's recommended you move to DNS-based rules.</span></span>

<br />

## <a name="api"></a><span data-ttu-id="a368b-288">API</span><span class="sxs-lookup"><span data-stu-id="a368b-288">API</span></span>
<span data-ttu-id="a368b-289">[API](apis-intro.md)설명서에 나열된 공용 URIS 대신 다음 URIS를 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a368b-289">Instead of the public URIs listed in our [API documentation](apis-intro.md), you'll need to use the following URIs:</span></span>

<span data-ttu-id="a368b-290">끝점 유형</span><span class="sxs-lookup"><span data-stu-id="a368b-290">Endpoint type</span></span> | <span data-ttu-id="a368b-291">GCC</span><span class="sxs-lookup"><span data-stu-id="a368b-291">GCC</span></span> | <span data-ttu-id="a368b-292">GCC High & DoD</span><span class="sxs-lookup"><span data-stu-id="a368b-292">GCC High & DoD</span></span>
:---|:---|:---
<span data-ttu-id="a368b-293">로그인</span><span class="sxs-lookup"><span data-stu-id="a368b-293">Login</span></span> | `https://login.microsoftonline.com` | `https://login.microsoftonline.us`
<span data-ttu-id="a368b-294">Endpoint API용 Defender</span><span class="sxs-lookup"><span data-stu-id="a368b-294">Defender for Endpoint API</span></span> | `https://api-gcc.securitycenter.microsoft.us` | `https://api-gov.securitycenter.microsoft.us`
<span data-ttu-id="a368b-295">SIEM</span><span class="sxs-lookup"><span data-stu-id="a368b-295">SIEM</span></span> | `https://wdatp-alertexporter-us.gcc.securitycenter.windows.us` | `https://wdatp-alertexporter-us.securitycenter.windows.us`

<br />

## <a name="feature-parity-with-commercial"></a><span data-ttu-id="a368b-296">상업용 기능 패리티</span><span class="sxs-lookup"><span data-stu-id="a368b-296">Feature parity with commercial</span></span>
<span data-ttu-id="a368b-297">미국 정부 고객을 위한 Endpoint용 Defender는 상업용 제품과 완전한 패리티를 택하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="a368b-297">Defender for Endpoint for US Government customers doesn't have complete parity with the commercial offering.</span></span> <span data-ttu-id="a368b-298">당사의 목표는 모든 상업적 기능을 미국 정부 고객에게 제공하는 것이지만, 아직 사용할 수 없는 몇 가지 기능은 강조하고 싶을 것입니다.</span><span class="sxs-lookup"><span data-stu-id="a368b-298">While our goal is to deliver all commercial features and functionality to our US Government customers, there are some capabilities not yet available we want to highlight.</span></span>

<span data-ttu-id="a368b-299">알려진 간격은 다음 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="a368b-299">These are the known gaps:</span></span>

<span data-ttu-id="a368b-300">기능 이름</span><span class="sxs-lookup"><span data-stu-id="a368b-300">Feature name</span></span> | <span data-ttu-id="a368b-301">GCC</span><span class="sxs-lookup"><span data-stu-id="a368b-301">GCC</span></span> | <span data-ttu-id="a368b-302">GCC 높음</span><span class="sxs-lookup"><span data-stu-id="a368b-302">GCC High</span></span> | <span data-ttu-id="a368b-303">DoD</span><span class="sxs-lookup"><span data-stu-id="a368b-303">DoD</span></span>
:---|:---|:---|:---
<span data-ttu-id="a368b-304">관리 및 API: 스트리밍 API</span><span class="sxs-lookup"><span data-stu-id="a368b-304">Management and APIs: Streaming API</span></span> | ![예](images/svg/check-yes.svg) | ![예](images/svg/check-yes.svg) | ![예](images/svg/check-yes.svg)
<span data-ttu-id="a368b-308">웹 컨텐츠 필터링</span><span class="sxs-lookup"><span data-stu-id="a368b-308">Web content filtering</span></span> | ![아니요.](images/svg/check-no.svg) <span data-ttu-id="a368b-310">개발 중</span><span class="sxs-lookup"><span data-stu-id="a368b-310">In development</span></span> | ![아니요.](images/svg/check-no.svg) <span data-ttu-id="a368b-312">개발 중</span><span class="sxs-lookup"><span data-stu-id="a368b-312">In development</span></span> | ![아니요.](images/svg/check-no.svg) <span data-ttu-id="a368b-314">개발 중</span><span class="sxs-lookup"><span data-stu-id="a368b-314">In development</span></span>
<span data-ttu-id="a368b-315">통합: Azure Sentinel</span><span class="sxs-lookup"><span data-stu-id="a368b-315">Integrations: Azure Sentinel</span></span> | ![예](images/svg/check-yes.svg) | ![예](images/svg/check-yes.svg) <span data-ttu-id="a368b-318">경고</span><span class="sxs-lookup"><span data-stu-id="a368b-318">Alerts</span></span> <br /> ![아니요.](images/svg/check-no.svg) <span data-ttu-id="a368b-320">인시던트 & 데이터: 개발 중</span><span class="sxs-lookup"><span data-stu-id="a368b-320">Incidents & Raw data: In development</span></span> | ![네.](images/svg/check-yes.svg) <span data-ttu-id="a368b-322">경고</span><span class="sxs-lookup"><span data-stu-id="a368b-322">Alerts</span></span> <br /> ![아니요.](images/svg/check-no.svg) <span data-ttu-id="a368b-324">인시던트 & 데이터: 개발 중</span><span class="sxs-lookup"><span data-stu-id="a368b-324">Incidents & Raw data: In development</span></span>
<span data-ttu-id="a368b-325">통합: Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="a368b-325">Integrations: Microsoft Cloud App Security</span></span> | ![예](images/svg/check-yes.svg) | ![아니요](images/svg/check-no.svg) <span data-ttu-id="a368b-328">개발 중</span><span class="sxs-lookup"><span data-stu-id="a368b-328">In development</span></span> | ![아니요.](images/svg/check-no.svg) <span data-ttu-id="a368b-330">개발 중</span><span class="sxs-lookup"><span data-stu-id="a368b-330">In development</span></span>
<span data-ttu-id="a368b-331">통합: Microsoft 준수 관리자</span><span class="sxs-lookup"><span data-stu-id="a368b-331">Integrations: Microsoft Compliance Manager</span></span> | ![아니요.](images/svg/check-no.svg) <span data-ttu-id="a368b-333">개발 중</span><span class="sxs-lookup"><span data-stu-id="a368b-333">In development</span></span> | ![아니요.](images/svg/check-no.svg) <span data-ttu-id="a368b-335">개발 중</span><span class="sxs-lookup"><span data-stu-id="a368b-335">In development</span></span> | ![아니요.](images/svg/check-no.svg) <span data-ttu-id="a368b-337">개발 중</span><span class="sxs-lookup"><span data-stu-id="a368b-337">In development</span></span>
<span data-ttu-id="a368b-338">통합: Id용 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="a368b-338">Integrations: Microsoft Defender for Identity</span></span> | ![아니요.](images/svg/check-no.svg) <span data-ttu-id="a368b-340">개발 중</span><span class="sxs-lookup"><span data-stu-id="a368b-340">In development</span></span> | ![아니요.](images/svg/check-no.svg) <span data-ttu-id="a368b-342">개발 중</span><span class="sxs-lookup"><span data-stu-id="a368b-342">In development</span></span> | ![아니요.](images/svg/check-no.svg) <span data-ttu-id="a368b-344">개발 중</span><span class="sxs-lookup"><span data-stu-id="a368b-344">In development</span></span>
<span data-ttu-id="a368b-345">통합: Microsoft Endpoint DLP</span><span class="sxs-lookup"><span data-stu-id="a368b-345">Integrations: Microsoft Endpoint DLP</span></span> | ![아니요.](images/svg/check-no.svg) <span data-ttu-id="a368b-347">개발 중</span><span class="sxs-lookup"><span data-stu-id="a368b-347">In development</span></span> | ![아니요.](images/svg/check-no.svg) <span data-ttu-id="a368b-349">개발 중</span><span class="sxs-lookup"><span data-stu-id="a368b-349">In development</span></span> | ![아니요.](images/svg/check-no.svg) <span data-ttu-id="a368b-351">개발 중</span><span class="sxs-lookup"><span data-stu-id="a368b-351">In development</span></span>
<span data-ttu-id="a368b-352">통합: Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="a368b-352">Integrations: Microsoft Intune</span></span> | ![예](images/svg/check-yes.svg) | ![예](images/svg/check-yes.svg) | ![예](images/svg/check-yes.svg)
<span data-ttu-id="a368b-356">통합: Microsoft Power Automate & Azure Logic Apps</span><span class="sxs-lookup"><span data-stu-id="a368b-356">Integrations: Microsoft Power Automate & Azure Logic Apps</span></span> | ![예](images/svg/check-yes.svg) | ![아니요](images/svg/check-no.svg) <span data-ttu-id="a368b-359">개발 중</span><span class="sxs-lookup"><span data-stu-id="a368b-359">In development</span></span> | ![아니요.](images/svg/check-no.svg) <span data-ttu-id="a368b-361">개발 중</span><span class="sxs-lookup"><span data-stu-id="a368b-361">In development</span></span>
<span data-ttu-id="a368b-362">Microsoft 위협 전문가</span><span class="sxs-lookup"><span data-stu-id="a368b-362">Microsoft Threat Experts</span></span> | ![아니요.](images/svg/check-no.svg) <span data-ttu-id="a368b-364">백로그 엔지니어링</span><span class="sxs-lookup"><span data-stu-id="a368b-364">On engineering backlog</span></span> | ![아니요.](images/svg/check-no.svg) <span data-ttu-id="a368b-366">백로그 엔지니어링</span><span class="sxs-lookup"><span data-stu-id="a368b-366">On engineering backlog</span></span> | ![아니요.](images/svg/check-no.svg) <span data-ttu-id="a368b-368">백로그 엔지니어링</span><span class="sxs-lookup"><span data-stu-id="a368b-368">On engineering backlog</span></span>
