---
title: Linux의 끝점용 Microsoft Defender 개인 정보
description: 개인 정보 제어, Linux의 끝점용 Microsoft Defender에서 수집된 진단 데이터에 대한 개인 정보 및 정보에 영향을 미치는 정책 설정을 구성하는 방법.
keywords: microsoft, defender, atp, linux, 개인 정보, 진단
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 69af56efa57f389842ed31afa5f0a74667bd8f7b
ms.sourcegitcommit: 13ce4b31303a1a21ca53700a54bcf8d91ad2f8c1
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/20/2021
ms.locfileid: "51903253"
---
# <a name="privacy-for-microsoft-defender-for-endpoint-on-linux"></a><span data-ttu-id="716d8-104">Linux의 끝점용 Microsoft Defender 개인 정보</span><span class="sxs-lookup"><span data-stu-id="716d8-104">Privacy for Microsoft Defender for Endpoint on Linux</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="716d8-105">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="716d8-105">**Applies to:**</span></span>
- [<span data-ttu-id="716d8-106">엔드포인트용 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="716d8-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="716d8-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="716d8-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="716d8-108">Endpoint용 Defender를 경험하고 싶나요?</span><span class="sxs-lookup"><span data-stu-id="716d8-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="716d8-109">무료 평가판에 등록합니다.</span><span class="sxs-lookup"><span data-stu-id="716d8-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-investigateip-abovefoldlink)

<span data-ttu-id="716d8-110">Microsoft는 Linux용 Endpoint용 Defender를 사용할 때 데이터를 수집하고 사용하는 방법에 대해 선택해야 하는 정보와 컨트롤을 사용자에게 제공하기 위해 최선을 다하고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="716d8-110">Microsoft is committed to providing you with the information and controls you need to make choices about how your data is collected and used when you’re using Defender for Endpoint for Linux.</span></span>

<span data-ttu-id="716d8-111">이 항목에서는 제품 내에서 사용할 수 있는 개인 정보 컨트롤, 정책 설정으로 이러한 컨트롤을 관리하는 방법 및 수집된 데이터 이벤트에 대한 세부 정보를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="716d8-111">This topic describes the privacy controls available within the product, how to manage these controls with policy settings and more details on the data events that are collected.</span></span>

## <a name="overview-of-privacy-controls-in-microsoft-defender-for-endpoint-on-linux"></a><span data-ttu-id="716d8-112">Linux의 끝점용 Microsoft Defender의 개인 정보 컨트롤 개요</span><span class="sxs-lookup"><span data-stu-id="716d8-112">Overview of privacy controls in Microsoft Defender for Endpoint on Linux</span></span>

<span data-ttu-id="716d8-113">이 섹션에서는 Linux용 끝점용 Defender에서 수집한 다양한 유형의 데이터에 대한 개인 정보 컨트롤에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="716d8-113">This section describes the privacy controls for the different types of data collected by Defender for Endpoint for Linux.</span></span>

### <a name="diagnostic-data"></a><span data-ttu-id="716d8-114">진단 데이터</span><span class="sxs-lookup"><span data-stu-id="716d8-114">Diagnostic data</span></span>

<span data-ttu-id="716d8-115">진단 데이터는 Endpoint용 Defender를 안전하고 최신 상태를 유지하며, 문제를 감지, 진단 및 해결하며, 제품을 개선하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="716d8-115">Diagnostic data is used to keep Defender for Endpoint secure and up-to-date, detect, diagnose and fix problems, and also make product improvements.</span></span>

<span data-ttu-id="716d8-116">일부 진단 데이터는 필수 사항이지만, 일부 진단 데이터는 선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="716d8-116">Some diagnostic data is required, while some diagnostic data is optional.</span></span> <span data-ttu-id="716d8-117">조직의 정책 설정과 같은 개인 정보 보호 컨트롤 사용을 통해 필수 또는 선택 사항 진단 데이터를 전송할지 여부를 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="716d8-117">We give you the ability to choose whether to send us required or optional diagnostic data through the use of privacy controls, such as policy settings for organizations.</span></span>

<span data-ttu-id="716d8-118">끝점용 Defender 클라이언트 소프트웨어에 대한 진단 데이터에는 다음 두 가지 수준 중 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="716d8-118">There are two levels of diagnostic data for Defender for Endpoint client software that you can choose from:</span></span>

* <span data-ttu-id="716d8-119">**필수:** Endpoint용 Defender를 안전하고 최신으로 유지하며 설치된 디바이스에서 예상대로 수행하는 데 필요한 최소 데이터입니다.</span><span class="sxs-lookup"><span data-stu-id="716d8-119">**Required**: The minimum data necessary to help keep Defender for Endpoint secure, up-to-date, and performing as expected on the device it’s installed on.</span></span>

* <span data-ttu-id="716d8-120">**선택** 사항: Microsoft가 제품을 개선하고 문제를 감지, 진단 및 수정하는 데 도움이 되는 향상된 정보를 제공하는 추가 데이터입니다.</span><span class="sxs-lookup"><span data-stu-id="716d8-120">**Optional**: Additional data that helps Microsoft make product improvements and provides enhanced information to help detect, diagnose, and remediate issues.</span></span>

<span data-ttu-id="716d8-121">기본적으로 필수 진단 데이터만 Microsoft로 전송됩니다.</span><span class="sxs-lookup"><span data-stu-id="716d8-121">By default, only required diagnostic data is sent to Microsoft.</span></span>

### <a name="cloud-delivered-protection-data"></a><span data-ttu-id="716d8-122">클라우드 제공 보호 데이터</span><span class="sxs-lookup"><span data-stu-id="716d8-122">Cloud delivered protection data</span></span>

<span data-ttu-id="716d8-123">클라우드 제공 보호는 클라우드의 최신 보호 데이터에 액세스할 수 있도록 증가하고 더 빠른 보호를 제공하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="716d8-123">Cloud delivered protection is used to provide increased and faster protection with access to the latest protection data in the cloud.</span></span>

<span data-ttu-id="716d8-124">클라우드 제공 보호 서비스를 사용하도록 설정하는 것은 선택 사항이지만 끝점 및 네트워크 전체에서 맬웨어에 대한 중요한 보호 기능을 제공하기 때문에 이 서비스를 사용하도록 설정하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="716d8-124">Enabling the cloud-delivered protection service is optional, however it is highly recommended because it provides important protection against malware on your endpoints and across your network.</span></span>

### <a name="sample-data"></a><span data-ttu-id="716d8-125">예제 데이터</span><span class="sxs-lookup"><span data-stu-id="716d8-125">Sample data</span></span>

<span data-ttu-id="716d8-126">샘플 데이터는 의심스러운 Microsoft 샘플을 전송하여 분석할 수 있도록 제품의 보호 기능을 개선하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="716d8-126">Sample data is used to improve the protection capabilities of the product, by sending Microsoft suspicious samples so they can be analyzed.</span></span> <span data-ttu-id="716d8-127">자동 샘플 제출을 사용하도록 설정하는 것은 선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="716d8-127">Enabling automatic sample submission is optional.</span></span>

<span data-ttu-id="716d8-128">샘플 제출을 제어하는 세 가지 수준이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="716d8-128">There are three levels for controlling sample submission:</span></span>

- <span data-ttu-id="716d8-129">**없음:** 의심스러운 샘플이 Microsoft에 제출하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="716d8-129">**None**: no suspicious samples are submitted to Microsoft.</span></span>
- <span data-ttu-id="716d8-130">**안전**: PII(개인 식별 정보)를 포함하지 않는 의심스러운 샘플만 자동으로 제출됩니다.</span><span class="sxs-lookup"><span data-stu-id="716d8-130">**Safe**: only suspicious samples that do not contain personally identifiable information (PII) are submitted automatically.</span></span> <span data-ttu-id="716d8-131">이 설정의 기본값입니다.</span><span class="sxs-lookup"><span data-stu-id="716d8-131">This is the default value for this setting.</span></span>
- <span data-ttu-id="716d8-132">**모두:** 의심스러운 모든 샘플이 Microsoft에 제출됩니다.</span><span class="sxs-lookup"><span data-stu-id="716d8-132">**All**: all suspicious samples are submitted to Microsoft.</span></span>

## <a name="manage-privacy-controls-with-policy-settings"></a><span data-ttu-id="716d8-133">정책 설정을 사용하여 개인 정보 관리</span><span class="sxs-lookup"><span data-stu-id="716d8-133">Manage privacy controls with policy settings</span></span>

<span data-ttu-id="716d8-134">IT 관리자인 경우 엔터프라이즈 수준에서 이러한 컨트롤을 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="716d8-134">If you're an IT administrator, you might want to configure these controls at the enterprise level.</span></span> 

<span data-ttu-id="716d8-135">이전 섹션에서 설명한 다양한 유형의 데이터에 대한 개인 정보 컨트롤은 [Linux용 끝점용 Defender에](linux-preferences.md)대한 기본 설정 설정에 자세히 설명되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="716d8-135">The privacy controls for the various types of data described in the preceding section are described in detail in [Set preferences for Defender for Endpoint for Linux](linux-preferences.md).</span></span>

<span data-ttu-id="716d8-136">새 정책 설정과 함께, 조직에서 정책 설정을 보다 광범위하게 구현하기 전에 구성한 설정이 원하는 영향을 미치도록 제한되고 제어되는 환경에서 신중하게 테스트해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="716d8-136">As with any new policy settings, you should carefully test them out in a limited, controlled environment to ensure the settings that you configure have the desired effect before you implement the policy settings more widely in your organization.</span></span>

## <a name="diagnostic-data-events"></a><span data-ttu-id="716d8-137">진단 데이터 이벤트</span><span class="sxs-lookup"><span data-stu-id="716d8-137">Diagnostic data events</span></span>

<span data-ttu-id="716d8-138">이 섹션에서는 필수 진단 데이터로 간주되는 항목과 선택적 진단 데이터로 간주되는 항목과 수집된 이벤트 및 필드에 대한 설명을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="716d8-138">This section describes what is considered required diagnostic data and what is considered optional diagnostic data, along with a description of the events and fields that are collected.</span></span>

### <a name="data-fields-that-are-common-for-all-events"></a><span data-ttu-id="716d8-139">모든 이벤트에 공통적인 데이터 필드</span><span class="sxs-lookup"><span data-stu-id="716d8-139">Data fields that are common for all events</span></span>
<span data-ttu-id="716d8-140">범주 또는 데이터 하위 형식에 관계없이 모든 이벤트에 공통적인 이벤트에 대한 몇 가지 정보가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="716d8-140">There is some information about events that is common to all events, regardless of category or data subtype.</span></span> 

<span data-ttu-id="716d8-141">다음 필드는 모든 이벤트에서 공통으로 간주됩니다.</span><span class="sxs-lookup"><span data-stu-id="716d8-141">The following fields are considered common for all events:</span></span>

| <span data-ttu-id="716d8-142">필드</span><span class="sxs-lookup"><span data-stu-id="716d8-142">Field</span></span>                   | <span data-ttu-id="716d8-143">설명</span><span class="sxs-lookup"><span data-stu-id="716d8-143">Description</span></span> |
| ----------------------- | ----------- |
| <span data-ttu-id="716d8-144">플랫폼</span><span class="sxs-lookup"><span data-stu-id="716d8-144">platform</span></span>                | <span data-ttu-id="716d8-145">앱이 실행되는 플랫폼의 광범위한 분류입니다.</span><span class="sxs-lookup"><span data-stu-id="716d8-145">The broad classification of the platform on which the app is running.</span></span> <span data-ttu-id="716d8-146">Microsoft에서 문제의 우선 순위를 올바르게 지정할 수 있도록 문제가 발생한 플랫폼을 식별할 수 있도록 허용합니다.</span><span class="sxs-lookup"><span data-stu-id="716d8-146">Allows Microsoft to identify on which platforms an issue may be occurring so that it can correctly be prioritized.</span></span> |
| <span data-ttu-id="716d8-147">machine_guid</span><span class="sxs-lookup"><span data-stu-id="716d8-147">machine_guid</span></span>            | <span data-ttu-id="716d8-148">장치와 연결된 고유 식별자입니다.</span><span class="sxs-lookup"><span data-stu-id="716d8-148">Unique identifier associated with the device.</span></span> <span data-ttu-id="716d8-149">Microsoft에서 문제가 선택된 설치 집합에 영향을 미치는지 여부와 영향을 미치는 사용자 수를 식별할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="716d8-149">Allows Microsoft to identify whether issues are impacting a select set of installs and how many users are impacted.</span></span> |
| <span data-ttu-id="716d8-150">sense_guid</span><span class="sxs-lookup"><span data-stu-id="716d8-150">sense_guid</span></span>              | <span data-ttu-id="716d8-151">장치와 연결된 고유 식별자입니다.</span><span class="sxs-lookup"><span data-stu-id="716d8-151">Unique identifier associated with the device.</span></span> <span data-ttu-id="716d8-152">Microsoft에서 문제가 선택된 설치 집합에 영향을 미치는지 여부와 영향을 미치는 사용자 수를 식별할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="716d8-152">Allows Microsoft to identify whether issues are impacting a select set of installs and how many users are impacted.</span></span> |
| <span data-ttu-id="716d8-153">org_id</span><span class="sxs-lookup"><span data-stu-id="716d8-153">org_id</span></span>                  | <span data-ttu-id="716d8-154">장치가 속한 엔터프라이즈와 연결된 고유 식별자입니다.</span><span class="sxs-lookup"><span data-stu-id="716d8-154">Unique identifier associated with the enterprise that the device belongs to.</span></span> <span data-ttu-id="716d8-155">Microsoft에서 문제가 선택한 엔터프라이즈 집합에 영향을 미치는지 여부와 영향을 미치는 엔터프라이즈 수를 식별할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="716d8-155">Allows Microsoft to identify whether issues are impacting a select set of enterprises and how many enterprises are impacted.</span></span> |
| <span data-ttu-id="716d8-156">hostname</span><span class="sxs-lookup"><span data-stu-id="716d8-156">hostname</span></span>                | <span data-ttu-id="716d8-157">로컬 장치 이름(DNS 접미사 불포기).</span><span class="sxs-lookup"><span data-stu-id="716d8-157">Local device name (without DNS suffix).</span></span> <span data-ttu-id="716d8-158">Microsoft에서 문제가 선택된 설치 집합에 영향을 미치는지 여부와 영향을 미치는 사용자 수를 식별할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="716d8-158">Allows Microsoft to identify whether issues are impacting a select set of installs and how many users are impacted.</span></span> |
| <span data-ttu-id="716d8-159">product_guid</span><span class="sxs-lookup"><span data-stu-id="716d8-159">product_guid</span></span>            | <span data-ttu-id="716d8-160">제품의 고유 식별자입니다.</span><span class="sxs-lookup"><span data-stu-id="716d8-160">Unique identifier of the product.</span></span> <span data-ttu-id="716d8-161">Microsoft에서 제품의 다양한 특징에 영향을 미치는 문제를 차별화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="716d8-161">Allows Microsoft to differentiate issues impacting different flavors of the product.</span></span> |
| <span data-ttu-id="716d8-162">app_version</span><span class="sxs-lookup"><span data-stu-id="716d8-162">app_version</span></span>             | <span data-ttu-id="716d8-163">Linux용 끝점용 Defender 응용 프로그램의 버전입니다.</span><span class="sxs-lookup"><span data-stu-id="716d8-163">Version of the Defender for Endpoint for Linux application.</span></span> <span data-ttu-id="716d8-164">Microsoft에서 문제를 표시하는 제품 버전을 식별하여 제품의 우선 순위를 올바르게 지정할 수 있도록 허용합니다.</span><span class="sxs-lookup"><span data-stu-id="716d8-164">Allows Microsoft to identify which versions of the product are showing an issue so that it can correctly be prioritized.</span></span>|
| <span data-ttu-id="716d8-165">sig_version</span><span class="sxs-lookup"><span data-stu-id="716d8-165">sig_version</span></span>             | <span data-ttu-id="716d8-166">보안 인텔리전스 데이터베이스의 버전입니다.</span><span class="sxs-lookup"><span data-stu-id="716d8-166">Version of security intelligence database.</span></span> <span data-ttu-id="716d8-167">Microsoft에서 문제를 표시하는 보안 인텔리전스 버전을 식별하여 우선 순위를 올바르게 지정할 수 있도록 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="716d8-167">Allows Microsoft to identify which versions of the security intelligence are showing an issue so that it can correctly be prioritized.</span></span> |
| <span data-ttu-id="716d8-168">supported_compressions</span><span class="sxs-lookup"><span data-stu-id="716d8-168">supported_compressions</span></span>  | <span data-ttu-id="716d8-169">응용 프로그램에서 지원하는 압축 알고리즘 목록(예: `['gzip']` ).</span><span class="sxs-lookup"><span data-stu-id="716d8-169">List of compression algorithms supported by the application, for example `['gzip']`.</span></span> <span data-ttu-id="716d8-170">Microsoft에서 응용 프로그램과 통신할 때 사용할 수 있는 압축 유형을 이해할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="716d8-170">Allows Microsoft to understand what types of compressions can be used when it communicates with the application.</span></span> |
| <span data-ttu-id="716d8-171">release_ring</span><span class="sxs-lookup"><span data-stu-id="716d8-171">release_ring</span></span>            | <span data-ttu-id="716d8-172">디바이스가 연결된 링(예: Insider Fast, Insider Slow, Production)입니다.</span><span class="sxs-lookup"><span data-stu-id="716d8-172">Ring that the device is associated with (for example Insider Fast, Insider Slow, Production).</span></span> <span data-ttu-id="716d8-173">Microsoft에서 문제의 우선 순위를 올바르게 지정할 수 있도록 문제가 발생될 수 있는 릴리스 링을 식별할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="716d8-173">Allows Microsoft to identify on which release ring an issue may be occurring so that it can correctly be prioritized.</span></span> |

### <a name="required-diagnostic-data"></a><span data-ttu-id="716d8-174">필수 진단 데이터</span><span class="sxs-lookup"><span data-stu-id="716d8-174">Required diagnostic data</span></span>

<span data-ttu-id="716d8-175">**필수 진단 데이터는** Endpoint용 Defender를 안전하고 최신으로 유지하며 설치된 디바이스에서 예상대로 수행하는 데 필요한 최소 데이터입니다.</span><span class="sxs-lookup"><span data-stu-id="716d8-175">**Required diagnostic data** is the minimum data necessary to help keep Defender for Endpoint secure, up-to-date, and perform as expected on the device it’s installed on.</span></span>

<span data-ttu-id="716d8-176">필수 진단 데이터는 장치 또는 소프트웨어 구성과 관련이 있을 수 있는 끝점용 Microsoft Defender의 문제를 식별하는 데 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="716d8-176">Required diagnostic data helps to identify problems with Microsoft Defender for Endpoint that may be related to a device or software configuration.</span></span> <span data-ttu-id="716d8-177">예를 들어, 새로운 기능이 도입된 특정 운영 체제 버전에서 또는 특정 Endpoint용 Defender 기능이 비활성화된 경우 끝점용 Defender 기능이 더 자주 충돌하는지 여부를 확인하는 데 도움이 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="716d8-177">For example, it can help determine if a Defender for Endpoint feature crashes more frequently on a particular operating system version, with newly introduced features, or when certain Defender for Endpoint features are disabled.</span></span> <span data-ttu-id="716d8-178">필수 진단 데이터는 Microsoft에서 이러한 문제를 더 빠르게 감지, 진단 및 해결하여 사용자 또는 조직에 미치는 영향을 줄일 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="716d8-178">Required diagnostic data helps Microsoft detect, diagnose, and fix these problems more quickly so the impact to users or organizations is reduced.</span></span>

#### <a name="software-setup-and-inventory-data-events"></a><span data-ttu-id="716d8-179">소프트웨어 설치 및 인벤토리 데이터 이벤트</span><span class="sxs-lookup"><span data-stu-id="716d8-179">Software setup and inventory data events</span></span>

<span data-ttu-id="716d8-180">**끝점용 Microsoft Defender 설치/제거**</span><span class="sxs-lookup"><span data-stu-id="716d8-180">**Microsoft Defender for Endpoint installation / uninstallation**</span></span>

<span data-ttu-id="716d8-181">다음 필드가 수집됩니다.</span><span class="sxs-lookup"><span data-stu-id="716d8-181">The following fields are collected:</span></span>

| <span data-ttu-id="716d8-182">필드</span><span class="sxs-lookup"><span data-stu-id="716d8-182">Field</span></span>            | <span data-ttu-id="716d8-183">설명</span><span class="sxs-lookup"><span data-stu-id="716d8-183">Description</span></span> |
| ---------------- | ----------- |
| <span data-ttu-id="716d8-184">correlation_id</span><span class="sxs-lookup"><span data-stu-id="716d8-184">correlation_id</span></span>   | <span data-ttu-id="716d8-185">설치와 연결된 고유 식별자입니다.</span><span class="sxs-lookup"><span data-stu-id="716d8-185">Unique identifier associated with the installation.</span></span> |
| <span data-ttu-id="716d8-186">버전</span><span class="sxs-lookup"><span data-stu-id="716d8-186">version</span></span>          | <span data-ttu-id="716d8-187">패키지의 버전입니다.</span><span class="sxs-lookup"><span data-stu-id="716d8-187">Version of the package.</span></span> |
| <span data-ttu-id="716d8-188">심각도</span><span class="sxs-lookup"><span data-stu-id="716d8-188">severity</span></span>         | <span data-ttu-id="716d8-189">메시지의 심각도(예: 정보)</span><span class="sxs-lookup"><span data-stu-id="716d8-189">Severity of the message (for example Informational).</span></span> |
| <span data-ttu-id="716d8-190">code</span><span class="sxs-lookup"><span data-stu-id="716d8-190">code</span></span>             | <span data-ttu-id="716d8-191">작업을 설명하는 코드입니다.</span><span class="sxs-lookup"><span data-stu-id="716d8-191">Code that describes the operation.</span></span> |
| <span data-ttu-id="716d8-192">text</span><span class="sxs-lookup"><span data-stu-id="716d8-192">text</span></span>             | <span data-ttu-id="716d8-193">제품 설치와 관련된 추가 정보입니다.</span><span class="sxs-lookup"><span data-stu-id="716d8-193">Additional information associated with the product installation.</span></span> |

<span data-ttu-id="716d8-194">**끝점용 Microsoft Defender 구성**</span><span class="sxs-lookup"><span data-stu-id="716d8-194">**Microsoft Defender for Endpoint configuration**</span></span>

<span data-ttu-id="716d8-195">다음 필드가 수집됩니다.</span><span class="sxs-lookup"><span data-stu-id="716d8-195">The following fields are collected:</span></span>

| <span data-ttu-id="716d8-196">필드</span><span class="sxs-lookup"><span data-stu-id="716d8-196">Field</span></span>                                               | <span data-ttu-id="716d8-197">설명</span><span class="sxs-lookup"><span data-stu-id="716d8-197">Description</span></span> |
| --------------------------------------------------- | ----------- |
| <span data-ttu-id="716d8-198">antivirus_engine.enable_real_time_protection</span><span class="sxs-lookup"><span data-stu-id="716d8-198">antivirus_engine.enable_real_time_protection</span></span>        | <span data-ttu-id="716d8-199">장치에서 실시간 보호를 사용할 수 있는지 여부입니다.</span><span class="sxs-lookup"><span data-stu-id="716d8-199">Whether real-time protection is enabled on the device or not.</span></span> |
| <span data-ttu-id="716d8-200">antivirus_engine.passive_mode</span><span class="sxs-lookup"><span data-stu-id="716d8-200">antivirus_engine.passive_mode</span></span>                       | <span data-ttu-id="716d8-201">디바이스에서 수동 모드가 활성화되어 있는지 여부입니다.</span><span class="sxs-lookup"><span data-stu-id="716d8-201">Whether passive mode is enabled on the device or not.</span></span> |
| <span data-ttu-id="716d8-202">cloud_service.enabled</span><span class="sxs-lookup"><span data-stu-id="716d8-202">cloud_service.enabled</span></span>                               | <span data-ttu-id="716d8-203">클라우드 제공 보호가 장치에서 활성화되어 있는지 여부입니다.</span><span class="sxs-lookup"><span data-stu-id="716d8-203">Whether cloud delivered protection is enabled on the device or not.</span></span> |
| <span data-ttu-id="716d8-204">cloud_service.timeout</span><span class="sxs-lookup"><span data-stu-id="716d8-204">cloud_service.timeout</span></span>                               | <span data-ttu-id="716d8-205">응용 프로그램이 끝점용 Defender 클라우드와 통신할 때의 시간 종료입니다.</span><span class="sxs-lookup"><span data-stu-id="716d8-205">Time out when the application communicates with the Defender for Endpoint cloud.</span></span> |
| <span data-ttu-id="716d8-206">cloud_service.heartbeat_interval</span><span class="sxs-lookup"><span data-stu-id="716d8-206">cloud_service.heartbeat_interval</span></span>                    | <span data-ttu-id="716d8-207">제품이 클라우드로 전송한 연속 하트비트 사이의 간격입니다.</span><span class="sxs-lookup"><span data-stu-id="716d8-207">Interval between consecutive heartbeats sent by the product to the cloud.</span></span> |
| <span data-ttu-id="716d8-208">cloud_service.service_uri</span><span class="sxs-lookup"><span data-stu-id="716d8-208">cloud_service.service_uri</span></span>                           | <span data-ttu-id="716d8-209">클라우드와 통신하는 데 사용되는 URI입니다.</span><span class="sxs-lookup"><span data-stu-id="716d8-209">URI used to communicate with the cloud.</span></span> |
| <span data-ttu-id="716d8-210">cloud_service.diagnostic_level</span><span class="sxs-lookup"><span data-stu-id="716d8-210">cloud_service.diagnostic_level</span></span>                      | <span data-ttu-id="716d8-211">디바이스의 진단 수준(필수, 선택 사항)</span><span class="sxs-lookup"><span data-stu-id="716d8-211">Diagnostic level of the device (required, optional).</span></span> |
| <span data-ttu-id="716d8-212">cloud_service.automatic_sample_submission</span><span class="sxs-lookup"><span data-stu-id="716d8-212">cloud_service.automatic_sample_submission</span></span>           | <span data-ttu-id="716d8-213">장치의 자동 샘플 제출 수준(없음, 안전, 모두)입니다.</span><span class="sxs-lookup"><span data-stu-id="716d8-213">Automatic sample submission level of the device (none, safe, all).</span></span> |
| <span data-ttu-id="716d8-214">edr.early_preview</span><span class="sxs-lookup"><span data-stu-id="716d8-214">edr.early_preview</span></span>                                   | <span data-ttu-id="716d8-215">디바이스에서 EDR 초기 미리 보기 기능을 실행해야 하는지 여부입니다.</span><span class="sxs-lookup"><span data-stu-id="716d8-215">Whether the device should run EDR early preview features.</span></span> |
| <span data-ttu-id="716d8-216">edr.group_id</span><span class="sxs-lookup"><span data-stu-id="716d8-216">edr.group_id</span></span>                                        | <span data-ttu-id="716d8-217">검색 및 응답 구성 요소에서 사용하는 그룹 식별자입니다.</span><span class="sxs-lookup"><span data-stu-id="716d8-217">Group identifier used by the detection and response component.</span></span> |
| <span data-ttu-id="716d8-218">edr.tags</span><span class="sxs-lookup"><span data-stu-id="716d8-218">edr.tags</span></span>                                            | <span data-ttu-id="716d8-219">사용자 정의 태그.</span><span class="sxs-lookup"><span data-stu-id="716d8-219">User-defined tags.</span></span> |
| <span data-ttu-id="716d8-220">기능을 제공합니다. \[ 선택적 기능 이름\]</span><span class="sxs-lookup"><span data-stu-id="716d8-220">features.\[optional feature name\]</span></span>                  | <span data-ttu-id="716d8-221">미리 보기 기능 목록과 해당 기능의 사용 여부</span><span class="sxs-lookup"><span data-stu-id="716d8-221">List of preview features, along with whether they are enabled or not.</span></span> |

#### <a name="product-and-service-usage-data-events"></a><span data-ttu-id="716d8-222">제품 및 서비스 사용 데이터 이벤트</span><span class="sxs-lookup"><span data-stu-id="716d8-222">Product and service usage data events</span></span>

<span data-ttu-id="716d8-223">**보안 인텔리전스 업데이트 보고서**</span><span class="sxs-lookup"><span data-stu-id="716d8-223">**Security intelligence update report**</span></span>

<span data-ttu-id="716d8-224">다음 필드가 수집됩니다.</span><span class="sxs-lookup"><span data-stu-id="716d8-224">The following fields are collected:</span></span>

| <span data-ttu-id="716d8-225">필드</span><span class="sxs-lookup"><span data-stu-id="716d8-225">Field</span></span>            | <span data-ttu-id="716d8-226">설명</span><span class="sxs-lookup"><span data-stu-id="716d8-226">Description</span></span> |
| ---------------- | ----------- |
| <span data-ttu-id="716d8-227">from_version</span><span class="sxs-lookup"><span data-stu-id="716d8-227">from_version</span></span>     | <span data-ttu-id="716d8-228">원래 보안 인텔리전스 버전입니다.</span><span class="sxs-lookup"><span data-stu-id="716d8-228">Original security intelligence version.</span></span> |
| <span data-ttu-id="716d8-229">to_version</span><span class="sxs-lookup"><span data-stu-id="716d8-229">to_version</span></span>       | <span data-ttu-id="716d8-230">새 보안 인텔리전스 버전입니다.</span><span class="sxs-lookup"><span data-stu-id="716d8-230">New security intelligence version.</span></span> |
| <span data-ttu-id="716d8-231">status</span><span class="sxs-lookup"><span data-stu-id="716d8-231">status</span></span>           | <span data-ttu-id="716d8-232">성공 또는 실패를 나타내는 업데이트 상태입니다.</span><span class="sxs-lookup"><span data-stu-id="716d8-232">Status of the update indicating success or failure.</span></span> |
| <span data-ttu-id="716d8-233">using_proxy</span><span class="sxs-lookup"><span data-stu-id="716d8-233">using_proxy</span></span>      | <span data-ttu-id="716d8-234">업데이트가 프록시를 통해 수행된 것인지 여부입니다.</span><span class="sxs-lookup"><span data-stu-id="716d8-234">Whether the update was done over a proxy.</span></span> |
| <span data-ttu-id="716d8-235">error</span><span class="sxs-lookup"><span data-stu-id="716d8-235">error</span></span>            | <span data-ttu-id="716d8-236">업데이트가 실패한 경우 오류 코드입니다.</span><span class="sxs-lookup"><span data-stu-id="716d8-236">Error code if the update failed.</span></span> |
| <span data-ttu-id="716d8-237">이유</span><span class="sxs-lookup"><span data-stu-id="716d8-237">reason</span></span>           | <span data-ttu-id="716d8-238">업데이트가 실패한 경우 오류 메시지가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="716d8-238">Error message if the update failed.</span></span> |

#### <a name="product-and-service-performance-data-events"></a><span data-ttu-id="716d8-239">제품 및 서비스 성능 데이터 이벤트</span><span class="sxs-lookup"><span data-stu-id="716d8-239">Product and service performance data events</span></span>

<span data-ttu-id="716d8-240">**커널 확장 통계**</span><span class="sxs-lookup"><span data-stu-id="716d8-240">**Kernel extension statistics**</span></span>

<span data-ttu-id="716d8-241">다음 필드가 수집됩니다.</span><span class="sxs-lookup"><span data-stu-id="716d8-241">The following fields are collected:</span></span>

| <span data-ttu-id="716d8-242">필드</span><span class="sxs-lookup"><span data-stu-id="716d8-242">Field</span></span>            | <span data-ttu-id="716d8-243">설명</span><span class="sxs-lookup"><span data-stu-id="716d8-243">Description</span></span> |
| ---------------- | ----------- |
| <span data-ttu-id="716d8-244">버전</span><span class="sxs-lookup"><span data-stu-id="716d8-244">version</span></span>          | <span data-ttu-id="716d8-245">Linux용 끝점용 Defender 버전입니다.</span><span class="sxs-lookup"><span data-stu-id="716d8-245">Version of Defender for Endpoint for Linux.</span></span> |
| <span data-ttu-id="716d8-246">instance_id</span><span class="sxs-lookup"><span data-stu-id="716d8-246">instance_id</span></span>      | <span data-ttu-id="716d8-247">커널 확장 시작 시 생성된 고유 식별자입니다.</span><span class="sxs-lookup"><span data-stu-id="716d8-247">Unique identifier generated on kernel extension startup.</span></span> |
| <span data-ttu-id="716d8-248">trace_level</span><span class="sxs-lookup"><span data-stu-id="716d8-248">trace_level</span></span>      | <span data-ttu-id="716d8-249">커널 확장의 추적 수준입니다.</span><span class="sxs-lookup"><span data-stu-id="716d8-249">Trace level of the kernel extension.</span></span> |
| <span data-ttu-id="716d8-250">subsystem</span><span class="sxs-lookup"><span data-stu-id="716d8-250">subsystem</span></span>        | <span data-ttu-id="716d8-251">실시간 보호에 사용되는 밑이 있는 하위입니다.</span><span class="sxs-lookup"><span data-stu-id="716d8-251">The underlying subsystem used for real-time protection.</span></span> |
| <span data-ttu-id="716d8-252">ipc.connects</span><span class="sxs-lookup"><span data-stu-id="716d8-252">ipc.connects</span></span>     | <span data-ttu-id="716d8-253">커널 확장에서 수신한 연결 요청 수입니다.</span><span class="sxs-lookup"><span data-stu-id="716d8-253">Number of connection requests received by the kernel extension.</span></span> |
| <span data-ttu-id="716d8-254">ipc.rejects</span><span class="sxs-lookup"><span data-stu-id="716d8-254">ipc.rejects</span></span>      | <span data-ttu-id="716d8-255">커널 확장에서 거부된 연결 요청 수입니다.</span><span class="sxs-lookup"><span data-stu-id="716d8-255">Number of connection requests rejected by the kernel extension.</span></span> |
| <span data-ttu-id="716d8-256">ipc.connected</span><span class="sxs-lookup"><span data-stu-id="716d8-256">ipc.connected</span></span>    | <span data-ttu-id="716d8-257">커널 확장에 대한 활성 연결이 있는지 여부입니다.</span><span class="sxs-lookup"><span data-stu-id="716d8-257">Whether there is any active connection to the kernel extension.</span></span> |

#### <a name="support-data"></a><span data-ttu-id="716d8-258">지원 데이터</span><span class="sxs-lookup"><span data-stu-id="716d8-258">Support data</span></span>

<span data-ttu-id="716d8-259">**진단 로그**</span><span class="sxs-lookup"><span data-stu-id="716d8-259">**Diagnostic logs**</span></span>

<span data-ttu-id="716d8-260">진단 로그는 피드백 제출 기능의 일부로 사용자의 동의로만 수집됩니다.</span><span class="sxs-lookup"><span data-stu-id="716d8-260">Diagnostic logs are collected only with the consent of the user as part of the feedback submission feature.</span></span> <span data-ttu-id="716d8-261">다음 파일은 지원 로그의 일부로 수집됩니다.</span><span class="sxs-lookup"><span data-stu-id="716d8-261">The following files are collected as part of the support logs:</span></span>

- <span data-ttu-id="716d8-262">*/var/log/microsoft/mdatp* 아래에 있는 모든 파일</span><span class="sxs-lookup"><span data-stu-id="716d8-262">All files under */var/log/microsoft/mdatp*</span></span>
- <span data-ttu-id="716d8-263">Linux용 Endpoint용 Defender에서 만들어 사용하는 */etc/opt/microsoft/mdatp* 아래에 있는 파일의 하위 집합</span><span class="sxs-lookup"><span data-stu-id="716d8-263">Subset of files under */etc/opt/microsoft/mdatp* that are created and used by Defender for Endpoint for Linux</span></span>
- <span data-ttu-id="716d8-264">*/var/log/microsoft_mdatp_ \* .log* 아래에 있는 제품 설치 및 제거 로그</span><span class="sxs-lookup"><span data-stu-id="716d8-264">Product installation and uninstallation logs under */var/log/microsoft_mdatp_\*.log*</span></span>

### <a name="optional-diagnostic-data"></a><span data-ttu-id="716d8-265">선택적 진단 데이터</span><span class="sxs-lookup"><span data-stu-id="716d8-265">Optional diagnostic data</span></span>

<span data-ttu-id="716d8-266">**선택적 진단 데이터는** Microsoft가 제품을 개선하는 데 도움이 되는 추가 데이터이며 문제를 감지, 진단 및 해결하는 데 도움이 되는 향상된 정보를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="716d8-266">**Optional diagnostic data** is additional data that helps Microsoft make product improvements and provides enhanced information to help detect, diagnose, and fix issues.</span></span>

<span data-ttu-id="716d8-267">선택 사항 진단 데이터를 보내시는 경우 필수 진단 데이터도 함께 보내야 합니다.</span><span class="sxs-lookup"><span data-stu-id="716d8-267">If you choose to send us optional diagnostic data, required diagnostic data is also included.</span></span>

<span data-ttu-id="716d8-268">선택적 진단 데이터의 예로는 Microsoft가 제품 구성(예: 장치에 설정된 제외 수) 및 제품 성능(제품의 구성 요소 성능에 대한 집계 측정값)에 대해 수집하는 데이터가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="716d8-268">Examples of optional diagnostic data include data Microsoft collects about product configuration (for example number of exclusions set on the device) and product performance (aggregate measures about the performance of components of the product).</span></span>

#### <a name="software-setup-and-inventory-data-events"></a><span data-ttu-id="716d8-269">소프트웨어 설치 및 인벤토리 데이터 이벤트</span><span class="sxs-lookup"><span data-stu-id="716d8-269">Software setup and inventory data events</span></span>

<span data-ttu-id="716d8-270">**끝점용 Microsoft Defender 구성**</span><span class="sxs-lookup"><span data-stu-id="716d8-270">**Microsoft Defender for Endpoint configuration**</span></span>

<span data-ttu-id="716d8-271">다음 필드가 수집됩니다.</span><span class="sxs-lookup"><span data-stu-id="716d8-271">The following fields are collected:</span></span>

| <span data-ttu-id="716d8-272">필드</span><span class="sxs-lookup"><span data-stu-id="716d8-272">Field</span></span>                                              | <span data-ttu-id="716d8-273">설명</span><span class="sxs-lookup"><span data-stu-id="716d8-273">Description</span></span> |
| -------------------------------------------------- | ----------- |
| <span data-ttu-id="716d8-274">connection_retry_timeout</span><span class="sxs-lookup"><span data-stu-id="716d8-274">connection_retry_timeout</span></span>                           | <span data-ttu-id="716d8-275">연결은 클라우드와 통신할 때 시간 아웃을 다시 시도합니다.</span><span class="sxs-lookup"><span data-stu-id="716d8-275">Connection retry time-out when communication with the cloud.</span></span> |
| <span data-ttu-id="716d8-276">file_hash_cache_maximum</span><span class="sxs-lookup"><span data-stu-id="716d8-276">file_hash_cache_maximum</span></span>                            | <span data-ttu-id="716d8-277">제품 캐시의 크기입니다.</span><span class="sxs-lookup"><span data-stu-id="716d8-277">Size of the product cache.</span></span> |
| <span data-ttu-id="716d8-278">crash_upload_daily_limit</span><span class="sxs-lookup"><span data-stu-id="716d8-278">crash_upload_daily_limit</span></span>                           | <span data-ttu-id="716d8-279">매일 업로드된 크래시 로그 제한.</span><span class="sxs-lookup"><span data-stu-id="716d8-279">Limit of crash logs uploaded daily.</span></span> |
| <span data-ttu-id="716d8-280">antivirus_engine.exclusions[].is_directory</span><span class="sxs-lookup"><span data-stu-id="716d8-280">antivirus_engine.exclusions[].is_directory</span></span>         | <span data-ttu-id="716d8-281">검사 제외가 디렉터리인지 여부입니다.</span><span class="sxs-lookup"><span data-stu-id="716d8-281">Whether the exclusion from scanning is a directory or not.</span></span> |
| <span data-ttu-id="716d8-282">antivirus_engine.exclusions[].path</span><span class="sxs-lookup"><span data-stu-id="716d8-282">antivirus_engine.exclusions[].path</span></span>                 | <span data-ttu-id="716d8-283">검사에서 제외된 경로입니다.</span><span class="sxs-lookup"><span data-stu-id="716d8-283">Path that was excluded from scanning.</span></span> |
| <span data-ttu-id="716d8-284">antivirus_engine.exclusions[].extension</span><span class="sxs-lookup"><span data-stu-id="716d8-284">antivirus_engine.exclusions[].extension</span></span>            | <span data-ttu-id="716d8-285">검색에서 제외된 확장명입니다.</span><span class="sxs-lookup"><span data-stu-id="716d8-285">Extension excluded from scanning.</span></span> |
| <span data-ttu-id="716d8-286">antivirus_engine.exclusions[].name</span><span class="sxs-lookup"><span data-stu-id="716d8-286">antivirus_engine.exclusions[].name</span></span>                 | <span data-ttu-id="716d8-287">검사에서 제외된 파일의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="716d8-287">Name of the file excluded from scanning.</span></span> |
| <span data-ttu-id="716d8-288">antivirus_engine.scan_cache_maximum</span><span class="sxs-lookup"><span data-stu-id="716d8-288">antivirus_engine.scan_cache_maximum</span></span>                | <span data-ttu-id="716d8-289">제품 캐시의 크기입니다.</span><span class="sxs-lookup"><span data-stu-id="716d8-289">Size of the product cache.</span></span> |
| <span data-ttu-id="716d8-290">antivirus_engine.maximum_scan_threads</span><span class="sxs-lookup"><span data-stu-id="716d8-290">antivirus_engine.maximum_scan_threads</span></span>              | <span data-ttu-id="716d8-291">검색에 사용되는 최대 스레드 수입니다.</span><span class="sxs-lookup"><span data-stu-id="716d8-291">Maximum number of threads used for scanning.</span></span> |
| <span data-ttu-id="716d8-292">antivirus_engine.threat_restoration_exclusion_time</span><span class="sxs-lookup"><span data-stu-id="716d8-292">antivirus_engine.threat_restoration_exclusion_time</span></span> | <span data-ttu-id="716d8-293">파일에서 복원된 파일을 다시 검색하기 전의 시간입니다.</span><span class="sxs-lookup"><span data-stu-id="716d8-293">Time out before a file restored from the quarantine can be detected again.</span></span> |
| <span data-ttu-id="716d8-294">filesystem_scanner.full_scan_directory</span><span class="sxs-lookup"><span data-stu-id="716d8-294">filesystem_scanner.full_scan_directory</span></span>             | <span data-ttu-id="716d8-295">전체 검사 디렉터리.</span><span class="sxs-lookup"><span data-stu-id="716d8-295">Full scan directory.</span></span> |
| <span data-ttu-id="716d8-296">filesystem_scanner.quick_scan_directories</span><span class="sxs-lookup"><span data-stu-id="716d8-296">filesystem_scanner.quick_scan_directories</span></span>          | <span data-ttu-id="716d8-297">빠른 검사에 사용되는렉터리 목록입니다.</span><span class="sxs-lookup"><span data-stu-id="716d8-297">List of directories used in quick scan.</span></span> |
| <span data-ttu-id="716d8-298">edr.latency_mode</span><span class="sxs-lookup"><span data-stu-id="716d8-298">edr.latency_mode</span></span>                                   | <span data-ttu-id="716d8-299">검색 및 응답 구성 요소에서 사용되는 대기 시간 모드입니다.</span><span class="sxs-lookup"><span data-stu-id="716d8-299">Latency mode used by the detection and response component.</span></span> |
| <span data-ttu-id="716d8-300">edr.proxy_address</span><span class="sxs-lookup"><span data-stu-id="716d8-300">edr.proxy_address</span></span>                                  | <span data-ttu-id="716d8-301">검색 및 응답 구성 요소에서 사용하는 프록시 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="716d8-301">Proxy address used by the detection and response component.</span></span> |

<span data-ttu-id="716d8-302">**Microsoft 자동 업데이트 구성**</span><span class="sxs-lookup"><span data-stu-id="716d8-302">**Microsoft Auto-Update configuration**</span></span>

<span data-ttu-id="716d8-303">다음 필드가 수집됩니다.</span><span class="sxs-lookup"><span data-stu-id="716d8-303">The following fields are collected:</span></span>

| <span data-ttu-id="716d8-304">필드</span><span class="sxs-lookup"><span data-stu-id="716d8-304">Field</span></span>                       | <span data-ttu-id="716d8-305">설명</span><span class="sxs-lookup"><span data-stu-id="716d8-305">Description</span></span> |
| --------------------------- | ----------- |
| <span data-ttu-id="716d8-306">how_to_check</span><span class="sxs-lookup"><span data-stu-id="716d8-306">how_to_check</span></span>                | <span data-ttu-id="716d8-307">자동 또는 수동과 같은 제품 업데이트를 확인하는 방법을 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="716d8-307">Determines how product updates are checked (for example automatic or manual).</span></span> |
| <span data-ttu-id="716d8-308">channel_name</span><span class="sxs-lookup"><span data-stu-id="716d8-308">channel_name</span></span>                | <span data-ttu-id="716d8-309">장치와 연결된 채널을 업데이트합니다.</span><span class="sxs-lookup"><span data-stu-id="716d8-309">Update channel associated with the device.</span></span> |
| <span data-ttu-id="716d8-310">manifest_server</span><span class="sxs-lookup"><span data-stu-id="716d8-310">manifest_server</span></span>             | <span data-ttu-id="716d8-311">업데이트를 다운로드하는 데 사용되는 서버입니다.</span><span class="sxs-lookup"><span data-stu-id="716d8-311">Server used for downloading updates.</span></span> |
| <span data-ttu-id="716d8-312">update_cache</span><span class="sxs-lookup"><span data-stu-id="716d8-312">update_cache</span></span>                | <span data-ttu-id="716d8-313">업데이트를 저장하는 데 사용되는 캐시 위치입니다.</span><span class="sxs-lookup"><span data-stu-id="716d8-313">Location of the cache used to store updates.</span></span> |

### <a name="product-and-service-usage"></a><span data-ttu-id="716d8-314">제품 및 서비스 사용</span><span class="sxs-lookup"><span data-stu-id="716d8-314">Product and service usage</span></span>

#### <a name="diagnostic-log-upload-started-report"></a><span data-ttu-id="716d8-315">진단 로그 업로드 시작 보고서</span><span class="sxs-lookup"><span data-stu-id="716d8-315">Diagnostic log upload started report</span></span>

<span data-ttu-id="716d8-316">다음 필드가 수집됩니다.</span><span class="sxs-lookup"><span data-stu-id="716d8-316">The following fields are collected:</span></span>

| <span data-ttu-id="716d8-317">필드</span><span class="sxs-lookup"><span data-stu-id="716d8-317">Field</span></span>            | <span data-ttu-id="716d8-318">설명</span><span class="sxs-lookup"><span data-stu-id="716d8-318">Description</span></span> |
| ---------------- | ----------- |
| <span data-ttu-id="716d8-319">sha256</span><span class="sxs-lookup"><span data-stu-id="716d8-319">sha256</span></span>           | <span data-ttu-id="716d8-320">지원 로그의 SHA256 식별자입니다.</span><span class="sxs-lookup"><span data-stu-id="716d8-320">SHA256 identifier of the support log.</span></span> |
| <span data-ttu-id="716d8-321">size</span><span class="sxs-lookup"><span data-stu-id="716d8-321">size</span></span>             | <span data-ttu-id="716d8-322">지원 로그의 크기입니다.</span><span class="sxs-lookup"><span data-stu-id="716d8-322">Size of the support log.</span></span> |
| <span data-ttu-id="716d8-323">original_path</span><span class="sxs-lookup"><span data-stu-id="716d8-323">original_path</span></span>    | <span data-ttu-id="716d8-324">지원 로그 경로(항상 */var/opt/microsoft/mdatp/wdavdiag/ 아래).*</span><span class="sxs-lookup"><span data-stu-id="716d8-324">Path to the support log (always under */var/opt/microsoft/mdatp/wdavdiag/*).</span></span> |
| <span data-ttu-id="716d8-325">형식</span><span class="sxs-lookup"><span data-stu-id="716d8-325">format</span></span>           | <span data-ttu-id="716d8-326">지원 로그의 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="716d8-326">Format of the support log.</span></span> |

#### <a name="diagnostic-log-upload-completed-report"></a><span data-ttu-id="716d8-327">진단 로그 업로드 완료된 보고서</span><span class="sxs-lookup"><span data-stu-id="716d8-327">Diagnostic log upload completed report</span></span>

<span data-ttu-id="716d8-328">다음 필드가 수집됩니다.</span><span class="sxs-lookup"><span data-stu-id="716d8-328">The following fields are collected:</span></span>

| <span data-ttu-id="716d8-329">필드</span><span class="sxs-lookup"><span data-stu-id="716d8-329">Field</span></span>            | <span data-ttu-id="716d8-330">설명</span><span class="sxs-lookup"><span data-stu-id="716d8-330">Description</span></span> |
| ---------------- | ----------- |
| <span data-ttu-id="716d8-331">request_id</span><span class="sxs-lookup"><span data-stu-id="716d8-331">request_id</span></span>       | <span data-ttu-id="716d8-332">지원 로그 업로드 요청의 상관 관계 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="716d8-332">Correlation ID for the support log upload request.</span></span> |
| <span data-ttu-id="716d8-333">sha256</span><span class="sxs-lookup"><span data-stu-id="716d8-333">sha256</span></span>           | <span data-ttu-id="716d8-334">지원 로그의 SHA256 식별자입니다.</span><span class="sxs-lookup"><span data-stu-id="716d8-334">SHA256 identifier of the support log.</span></span> |
| <span data-ttu-id="716d8-335">blob_sas_uri</span><span class="sxs-lookup"><span data-stu-id="716d8-335">blob_sas_uri</span></span>     | <span data-ttu-id="716d8-336">응용 프로그램에서 지원 로그를 업로드하는 데 사용하는 URI입니다.</span><span class="sxs-lookup"><span data-stu-id="716d8-336">URI used by the application to upload the support log.</span></span> |

#### <a name="product-and-service-performance-data-events"></a><span data-ttu-id="716d8-337">제품 및 서비스 성능 데이터 이벤트</span><span class="sxs-lookup"><span data-stu-id="716d8-337">Product and service performance data events</span></span>

<span data-ttu-id="716d8-338">**예기치 않은 응용 프로그램 종료(크래시)**</span><span class="sxs-lookup"><span data-stu-id="716d8-338">**Unexpected application exit (crash)**</span></span>

<span data-ttu-id="716d8-339">예기치 않은 응용 프로그램 종료 및 종료 시의 응용 프로그램 상태입니다.</span><span class="sxs-lookup"><span data-stu-id="716d8-339">Unexpected application exits and the state of the application when that happens.</span></span>

<span data-ttu-id="716d8-340">**커널 확장 통계**</span><span class="sxs-lookup"><span data-stu-id="716d8-340">**Kernel extension statistics**</span></span>

<span data-ttu-id="716d8-341">다음 필드가 수집됩니다.</span><span class="sxs-lookup"><span data-stu-id="716d8-341">The following fields are collected:</span></span>

| <span data-ttu-id="716d8-342">필드</span><span class="sxs-lookup"><span data-stu-id="716d8-342">Field</span></span>                          | <span data-ttu-id="716d8-343">설명</span><span class="sxs-lookup"><span data-stu-id="716d8-343">Description</span></span> |
| ------------------------------ | ----------- |
| <span data-ttu-id="716d8-344">pkt_ack_timeout</span><span class="sxs-lookup"><span data-stu-id="716d8-344">pkt_ack_timeout</span></span>                | <span data-ttu-id="716d8-345">다음 속성은 커널 확장 시작 이후 발생된 이벤트 수를 나타내는 집계된 숫자 값입니다.</span><span class="sxs-lookup"><span data-stu-id="716d8-345">The following properties are aggregated numerical values, representing count of events that happened since kernel extension startup.</span></span> |
| <span data-ttu-id="716d8-346">pkt_ack_conn_timeout</span><span class="sxs-lookup"><span data-stu-id="716d8-346">pkt_ack_conn_timeout</span></span>             | |
| <span data-ttu-id="716d8-347">ipc.ack_pkts</span><span class="sxs-lookup"><span data-stu-id="716d8-347">ipc.ack_pkts</span></span>                     | |
| <span data-ttu-id="716d8-348">ipc.nack_pkts</span><span class="sxs-lookup"><span data-stu-id="716d8-348">ipc.nack_pkts</span></span>                    | |
| <span data-ttu-id="716d8-349">ipc.send.ack_no_conn</span><span class="sxs-lookup"><span data-stu-id="716d8-349">ipc.send.ack_no_conn</span></span>             | |
| <span data-ttu-id="716d8-350">ipc.send.nack_no_conn</span><span class="sxs-lookup"><span data-stu-id="716d8-350">ipc.send.nack_no_conn</span></span>            | |
| <span data-ttu-id="716d8-351">ipc.send.ack_no_qsq</span><span class="sxs-lookup"><span data-stu-id="716d8-351">ipc.send.ack_no_qsq</span></span>              | |
| <span data-ttu-id="716d8-352">ipc.send.nack_no_qsq</span><span class="sxs-lookup"><span data-stu-id="716d8-352">ipc.send.nack_no_qsq</span></span>             | |
| <span data-ttu-id="716d8-353">ipc.ack.no_space</span><span class="sxs-lookup"><span data-stu-id="716d8-353">ipc.ack.no_space</span></span>                 | |
| <span data-ttu-id="716d8-354">ipc.ack.timeout</span><span class="sxs-lookup"><span data-stu-id="716d8-354">ipc.ack.timeout</span></span>                  | |
| <span data-ttu-id="716d8-355">ipc.ack.ackd_fast</span><span class="sxs-lookup"><span data-stu-id="716d8-355">ipc.ack.ackd_fast</span></span>                | |
| <span data-ttu-id="716d8-356">ipc.ack.ackd</span><span class="sxs-lookup"><span data-stu-id="716d8-356">ipc.ack.ackd</span></span>                     | |
| <span data-ttu-id="716d8-357">ipc.recv.bad_pkt_len</span><span class="sxs-lookup"><span data-stu-id="716d8-357">ipc.recv.bad_pkt_len</span></span>             | |
| <span data-ttu-id="716d8-358">ipc.recv.bad_reply_len</span><span class="sxs-lookup"><span data-stu-id="716d8-358">ipc.recv.bad_reply_len</span></span>           | |
| <span data-ttu-id="716d8-359">ipc.recv.no_waiter</span><span class="sxs-lookup"><span data-stu-id="716d8-359">ipc.recv.no_waiter</span></span>               | |
| <span data-ttu-id="716d8-360">ipc.recv.copy_failed</span><span class="sxs-lookup"><span data-stu-id="716d8-360">ipc.recv.copy_failed</span></span>             | |
| <span data-ttu-id="716d8-361">ipc.kauth.vnode.mask</span><span class="sxs-lookup"><span data-stu-id="716d8-361">ipc.kauth.vnode.mask</span></span>             | |
| <span data-ttu-id="716d8-362">ipc.kauth.vnode.read</span><span class="sxs-lookup"><span data-stu-id="716d8-362">ipc.kauth.vnode.read</span></span>             | |
| <span data-ttu-id="716d8-363">ipc.kauth.vnode.write</span><span class="sxs-lookup"><span data-stu-id="716d8-363">ipc.kauth.vnode.write</span></span>            | |
| <span data-ttu-id="716d8-364">ipc.kauth.vnode.exec</span><span class="sxs-lookup"><span data-stu-id="716d8-364">ipc.kauth.vnode.exec</span></span>             | |
| <span data-ttu-id="716d8-365">ipc.kauth.vnode.del</span><span class="sxs-lookup"><span data-stu-id="716d8-365">ipc.kauth.vnode.del</span></span>              | |
| <span data-ttu-id="716d8-366">ipc.kauth.vnode.read_attr</span><span class="sxs-lookup"><span data-stu-id="716d8-366">ipc.kauth.vnode.read_attr</span></span>        | |
| <span data-ttu-id="716d8-367">ipc.kauth.vnode.write_attr</span><span class="sxs-lookup"><span data-stu-id="716d8-367">ipc.kauth.vnode.write_attr</span></span>       | |
| <span data-ttu-id="716d8-368">ipc.kauth.vnode.read_ex_attr</span><span class="sxs-lookup"><span data-stu-id="716d8-368">ipc.kauth.vnode.read_ex_attr</span></span>     | |
| <span data-ttu-id="716d8-369">ipc.kauth.vnode.write_ex_attr</span><span class="sxs-lookup"><span data-stu-id="716d8-369">ipc.kauth.vnode.write_ex_attr</span></span>    | |
| <span data-ttu-id="716d8-370">ipc.kauth.vnode.read_sec</span><span class="sxs-lookup"><span data-stu-id="716d8-370">ipc.kauth.vnode.read_sec</span></span>         | |
| <span data-ttu-id="716d8-371">ipc.kauth.vnode.write_sec</span><span class="sxs-lookup"><span data-stu-id="716d8-371">ipc.kauth.vnode.write_sec</span></span>        | |
| <span data-ttu-id="716d8-372">ipc.kauth.vnode.take_own</span><span class="sxs-lookup"><span data-stu-id="716d8-372">ipc.kauth.vnode.take_own</span></span>         | |
| <span data-ttu-id="716d8-373">ipc.kauth.vnode.link</span><span class="sxs-lookup"><span data-stu-id="716d8-373">ipc.kauth.vnode.link</span></span>             | |
| <span data-ttu-id="716d8-374">ipc.kauth.vnode.create</span><span class="sxs-lookup"><span data-stu-id="716d8-374">ipc.kauth.vnode.create</span></span>           | |
| <span data-ttu-id="716d8-375">ipc.kauth.vnode.move</span><span class="sxs-lookup"><span data-stu-id="716d8-375">ipc.kauth.vnode.move</span></span>             | |
| <span data-ttu-id="716d8-376">ipc.kauth.vnode.mount</span><span class="sxs-lookup"><span data-stu-id="716d8-376">ipc.kauth.vnode.mount</span></span>            | |
| <span data-ttu-id="716d8-377">ipc.kauth.vnode.denied</span><span class="sxs-lookup"><span data-stu-id="716d8-377">ipc.kauth.vnode.denied</span></span>           | |
| <span data-ttu-id="716d8-378">ipc.kauth.vnode.ackd_before_deadline</span><span class="sxs-lookup"><span data-stu-id="716d8-378">ipc.kauth.vnode.ackd_before_deadline</span></span> | |
| <span data-ttu-id="716d8-379">ipc.kauth.vnode.missed_deadline</span><span class="sxs-lookup"><span data-stu-id="716d8-379">ipc.kauth.vnode.missed_deadline</span></span>  | |
| <span data-ttu-id="716d8-380">ipc.kauth.file_op.mask</span><span class="sxs-lookup"><span data-stu-id="716d8-380">ipc.kauth.file_op.mask</span></span>           | |
| <span data-ttu-id="716d8-381">ipc.kauth_file_op.open</span><span class="sxs-lookup"><span data-stu-id="716d8-381">ipc.kauth_file_op.open</span></span>           | |
| <span data-ttu-id="716d8-382">ipc.kauth.file_op.close</span><span class="sxs-lookup"><span data-stu-id="716d8-382">ipc.kauth.file_op.close</span></span>          | |
| <span data-ttu-id="716d8-383">ipc.kauth.file_op.close_modified</span><span class="sxs-lookup"><span data-stu-id="716d8-383">ipc.kauth.file_op.close_modified</span></span> | |
| <span data-ttu-id="716d8-384">ipc.kauth.file_op.move</span><span class="sxs-lookup"><span data-stu-id="716d8-384">ipc.kauth.file_op.move</span></span>           | |
| <span data-ttu-id="716d8-385">ipc.kauth.file_op.link</span><span class="sxs-lookup"><span data-stu-id="716d8-385">ipc.kauth.file_op.link</span></span>           | |
| <span data-ttu-id="716d8-386">ipc.kauth.file_op.exec</span><span class="sxs-lookup"><span data-stu-id="716d8-386">ipc.kauth.file_op.exec</span></span>           | |
| <span data-ttu-id="716d8-387">ipc.kauth.file_op.remove</span><span class="sxs-lookup"><span data-stu-id="716d8-387">ipc.kauth.file_op.remove</span></span>         | |
| <span data-ttu-id="716d8-388">ipc.kauth.file_op.unmount</span><span class="sxs-lookup"><span data-stu-id="716d8-388">ipc.kauth.file_op.unmount</span></span>        | |
| <span data-ttu-id="716d8-389">ipc.kauth.file_op.fork</span><span class="sxs-lookup"><span data-stu-id="716d8-389">ipc.kauth.file_op.fork</span></span>           | |
| <span data-ttu-id="716d8-390">ipc.kauth.file_op.create</span><span class="sxs-lookup"><span data-stu-id="716d8-390">ipc.kauth.file_op.create</span></span>         | |

## <a name="resources"></a><span data-ttu-id="716d8-391">리소스</span><span class="sxs-lookup"><span data-stu-id="716d8-391">Resources</span></span>

- [<span data-ttu-id="716d8-392">Microsoft 개인 정보</span><span class="sxs-lookup"><span data-stu-id="716d8-392">Privacy at Microsoft</span></span>](https://privacy.microsoft.com/)
