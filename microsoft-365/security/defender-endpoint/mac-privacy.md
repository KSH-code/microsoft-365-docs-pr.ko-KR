---
title: Mac용 Microsoft Defender ATP 개인 정보
description: 개인 정보 제어, Mac용 Microsoft Defender ATP에서 수집된 진단 데이터에 대한 개인 정보 및 정보에 영향을 미치는 정책 설정을 구성하는 방법.
keywords: Microsoft, defender, atp, mac, 개인 정보, 진단
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
ms.collection:
- m365-security-compliance
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: d1d4aa871438e10aed86ddd436757072fb6b5cc4
ms.sourcegitcommit: 987f70e44e406ab6b1dd35f336a9d0c228032794
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/05/2021
ms.locfileid: "51587506"
---
# <a name="privacy-for-microsoft-defender-for-endpoint-for-mac"></a><span data-ttu-id="f8708-104">Mac용 끝점용 Microsoft Defender에 대한 개인 정보</span><span class="sxs-lookup"><span data-stu-id="f8708-104">Privacy for Microsoft Defender for Endpoint for Mac</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="f8708-105">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="f8708-105">**Applies to:**</span></span>
- <span data-ttu-id="f8708-106">[엔드포인트용 Microsoft Defender](https://go.microsoft.com/fwlink/p/?linkid=2154037) </span><span class="sxs-lookup"><span data-stu-id="f8708-106">[Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)</span></span>
- [<span data-ttu-id="f8708-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="f8708-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="f8708-108">끝점용 Microsoft Defender를 경험하고 싶나요?</span><span class="sxs-lookup"><span data-stu-id="f8708-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="f8708-109">무료 평가판에 등록합니다.</span><span class="sxs-lookup"><span data-stu-id="f8708-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 


<span data-ttu-id="f8708-110">Microsoft는 Mac용 끝점용 Microsoft Defender를 사용할 때 데이터를 수집하고 사용하는 방법에 대해 선택해야 하는 정보와 컨트롤을 사용자에게 제공하기 위해 최선을 다하고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f8708-110">Microsoft is committed to providing you with the information and controls you need to make choices about how your data is collected and used when you’re using Microsoft Defender for Endpoint for Mac.</span></span>

<span data-ttu-id="f8708-111">이 항목에서는 제품 내에서 사용할 수 있는 개인 정보 컨트롤, 정책 설정으로 이러한 컨트롤을 관리하는 방법 및 수집된 데이터 이벤트에 대한 세부 정보를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="f8708-111">This topic describes the privacy controls available within the product, how to manage these controls with policy settings and more details on the data events that are collected.</span></span>

## <a name="overview-of-privacy-controls-in-microsoft-defender-for-endpoint-for-mac"></a><span data-ttu-id="f8708-112">Mac용 끝점용 Microsoft Defender의 개인 정보 컨트롤 개요</span><span class="sxs-lookup"><span data-stu-id="f8708-112">Overview of privacy controls in Microsoft Defender for Endpoint for Mac</span></span>

<span data-ttu-id="f8708-113">이 섹션에서는 Mac용 끝점용 Microsoft Defender에서 수집한 다양한 유형의 데이터에 대한 개인 정보 컨트롤에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="f8708-113">This section describes the privacy controls for the different types of data collected by Microsoft Defender for Endpoint for Mac.</span></span>

### <a name="diagnostic-data"></a><span data-ttu-id="f8708-114">진단 데이터</span><span class="sxs-lookup"><span data-stu-id="f8708-114">Diagnostic data</span></span>

<span data-ttu-id="f8708-115">진단 데이터는 끝점용 Microsoft Defender를 안전하고 최신으로 유지하며, 문제를 감지, 진단 및 해결하며, 제품을 개선하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="f8708-115">Diagnostic data is used to keep Microsoft Defender for Endpoint secure and up-to-date, detect, diagnose and fix problems, and also make product improvements.</span></span>

<span data-ttu-id="f8708-116">일부 진단 데이터는 필수 사항이지만, 일부 진단 데이터는 선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="f8708-116">Some diagnostic data is required, while some diagnostic data is optional.</span></span> <span data-ttu-id="f8708-117">조직의 정책 설정과 같은 개인 정보 보호 컨트롤 사용을 통해 필수 또는 선택 사항 진단 데이터를 전송할지 여부를 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f8708-117">We give you the ability to choose whether to send us required or optional diagnostic data through the use of privacy controls, such as policy settings for organizations.</span></span>

<span data-ttu-id="f8708-118">끝점용 Microsoft Defender 클라이언트 소프트웨어에 대한 진단 데이터에는 다음 두 가지 수준 중 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f8708-118">There are two levels of diagnostic data for Microsoft Defender for Endpoint client software that you can choose from:</span></span>

* <span data-ttu-id="f8708-119">**필수:** 끝점용 Microsoft Defender를 안전하고 최신으로 유지하며 설치된 디바이스에서 예상대로 수행하는 데 필요한 최소 데이터입니다.</span><span class="sxs-lookup"><span data-stu-id="f8708-119">**Required**: The minimum data necessary to help keep Microsoft Defender for Endpoint secure, up-to-date, and performing as expected on the device it’s installed on.</span></span>

* <span data-ttu-id="f8708-120">**선택** 사항: Microsoft가 제품을 개선하고 문제를 감지, 진단 및 수정하는 데 도움이 되는 향상된 정보를 제공하는 추가 데이터입니다.</span><span class="sxs-lookup"><span data-stu-id="f8708-120">**Optional**: Additional data that helps Microsoft make product improvements and provides enhanced information to help detect, diagnose, and remediate issues.</span></span>

<span data-ttu-id="f8708-121">기본적으로 필수 진단 데이터만 Microsoft로 전송됩니다.</span><span class="sxs-lookup"><span data-stu-id="f8708-121">By default, only required diagnostic data is sent to Microsoft.</span></span>

### <a name="cloud-delivered-protection-data"></a><span data-ttu-id="f8708-122">클라우드 제공 보호 데이터</span><span class="sxs-lookup"><span data-stu-id="f8708-122">Cloud delivered protection data</span></span>

<span data-ttu-id="f8708-123">클라우드 제공 보호는 클라우드의 최신 보호 데이터에 액세스할 수 있도록 증가하고 더 빠른 보호를 제공하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="f8708-123">Cloud delivered protection is used to provide increased and faster protection with access to the latest protection data in the cloud.</span></span>

<span data-ttu-id="f8708-124">클라우드 제공 보호 서비스를 사용하도록 설정하는 것은 선택 사항이지만 끝점 및 네트워크 전체에서 맬웨어에 대한 중요한 보호 기능을 제공하기 때문에 이 서비스를 사용하도록 설정하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="f8708-124">Enabling the cloud-delivered protection service is optional, however it is highly recommended because it provides important protection against malware on your endpoints and across your network.</span></span>

### <a name="sample-data"></a><span data-ttu-id="f8708-125">예제 데이터</span><span class="sxs-lookup"><span data-stu-id="f8708-125">Sample data</span></span>

<span data-ttu-id="f8708-126">샘플 데이터는 의심스러운 Microsoft 샘플을 전송하여 분석할 수 있도록 제품의 보호 기능을 개선하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="f8708-126">Sample data is used to improve the protection capabilities of the product, by sending Microsoft suspicious samples so they can be analyzed.</span></span> <span data-ttu-id="f8708-127">자동 샘플 제출을 사용하도록 설정하는 것은 선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="f8708-127">Enabling automatic sample submission is optional.</span></span>

<span data-ttu-id="f8708-128">이 기능을 사용하도록 설정하고 수집된 샘플에 개인 정보가 포함될 가능성이 있는 경우 사용자에게 동의를 요청하는 메시지가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="f8708-128">When this feature is enabled and the sample that is collected is likely to contain personal information, the user is prompted for consent.</span></span>

## <a name="manage-privacy-controls-with-policy-settings"></a><span data-ttu-id="f8708-129">정책 설정을 사용하여 개인 정보 관리</span><span class="sxs-lookup"><span data-stu-id="f8708-129">Manage privacy controls with policy settings</span></span>

<span data-ttu-id="f8708-130">IT 관리자인 경우 엔터프라이즈 수준에서 이러한 컨트롤을 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f8708-130">If you're an IT administrator, you might want to configure these controls at the enterprise level.</span></span> 

<span data-ttu-id="f8708-131">이전 섹션에서 설명한 다양한 유형의 데이터에 대한 개인 정보 컨트롤은 [Mac용 끝점용 Microsoft Defender에](mac-preferences.md)대한 기본 설정 설정에 자세히 설명되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f8708-131">The privacy controls for the various types of data described in the preceding section are described in detail in [Set preferences for Microsoft Defender for Endpoint for Mac](mac-preferences.md).</span></span>

<span data-ttu-id="f8708-132">새 정책 설정과 함께, 조직에서 정책 설정을 보다 광범위하게 구현하기 전에 구성한 설정이 원하는 영향을 미치도록 제한되고 제어되는 환경에서 신중하게 테스트해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f8708-132">As with any new policy settings, you should carefully test them out in a limited, controlled environment to ensure the settings that you configure have the desired effect before you implement the policy settings more widely in your organization.</span></span>

## <a name="diagnostic-data-events"></a><span data-ttu-id="f8708-133">진단 데이터 이벤트</span><span class="sxs-lookup"><span data-stu-id="f8708-133">Diagnostic data events</span></span>

<span data-ttu-id="f8708-134">이 섹션에서는 필수 진단 데이터로 간주되는 항목과 선택적 진단 데이터로 간주되는 항목과 수집된 이벤트 및 필드에 대한 설명을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="f8708-134">This section describes what is considered required diagnostic data and what is considered optional diagnostic data, along with a description of the events and fields that are collected.</span></span>

### <a name="data-fields-that-are-common-for-all-events"></a><span data-ttu-id="f8708-135">모든 이벤트에 공통적인 데이터 필드</span><span class="sxs-lookup"><span data-stu-id="f8708-135">Data fields that are common for all events</span></span>
<span data-ttu-id="f8708-136">범주 또는 데이터 하위 형식에 관계없이 모든 이벤트에 공통적인 이벤트에 대한 몇 가지 정보가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f8708-136">There is some information about events that is common to all events, regardless of category or data subtype.</span></span> 

<span data-ttu-id="f8708-137">다음 필드는 모든 이벤트에서 공통으로 간주됩니다.</span><span class="sxs-lookup"><span data-stu-id="f8708-137">The following fields are considered common for all events:</span></span>

| <span data-ttu-id="f8708-138">필드</span><span class="sxs-lookup"><span data-stu-id="f8708-138">Field</span></span>                   | <span data-ttu-id="f8708-139">설명</span><span class="sxs-lookup"><span data-stu-id="f8708-139">Description</span></span> |
| ----------------------- | ----------- |
| <span data-ttu-id="f8708-140">플랫폼</span><span class="sxs-lookup"><span data-stu-id="f8708-140">platform</span></span>                | <span data-ttu-id="f8708-141">앱이 실행되는 플랫폼의 광범위한 분류입니다.</span><span class="sxs-lookup"><span data-stu-id="f8708-141">The broad classification of the platform on which the app is running.</span></span> <span data-ttu-id="f8708-142">Microsoft에서 문제의 우선 순위를 올바르게 지정할 수 있도록 문제가 발생한 플랫폼을 식별할 수 있도록 허용합니다.</span><span class="sxs-lookup"><span data-stu-id="f8708-142">Allows Microsoft to identify on which platforms an issue may be occurring so that it can correctly be prioritized.</span></span> |
| <span data-ttu-id="f8708-143">machine_guid</span><span class="sxs-lookup"><span data-stu-id="f8708-143">machine_guid</span></span>            | <span data-ttu-id="f8708-144">장치와 연결된 고유 식별자입니다.</span><span class="sxs-lookup"><span data-stu-id="f8708-144">Unique identifier associated with the device.</span></span> <span data-ttu-id="f8708-145">Microsoft에서 문제가 선택된 설치 집합에 영향을 미치는지 여부와 영향을 미치는 사용자 수를 식별할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="f8708-145">Allows Microsoft to identify whether issues are impacting a select set of installs and how many users are impacted.</span></span> |
| <span data-ttu-id="f8708-146">sense_guid</span><span class="sxs-lookup"><span data-stu-id="f8708-146">sense_guid</span></span>              | <span data-ttu-id="f8708-147">장치와 연결된 고유 식별자입니다.</span><span class="sxs-lookup"><span data-stu-id="f8708-147">Unique identifier associated with the device.</span></span> <span data-ttu-id="f8708-148">Microsoft에서 문제가 선택된 설치 집합에 영향을 미치는지 여부와 영향을 미치는 사용자 수를 식별할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="f8708-148">Allows Microsoft to identify whether issues are impacting a select set of installs and how many users are impacted.</span></span> |
| <span data-ttu-id="f8708-149">org_id</span><span class="sxs-lookup"><span data-stu-id="f8708-149">org_id</span></span>                  | <span data-ttu-id="f8708-150">장치가 속한 엔터프라이즈와 연결된 고유 식별자입니다.</span><span class="sxs-lookup"><span data-stu-id="f8708-150">Unique identifier associated with the enterprise that the device belongs to.</span></span> <span data-ttu-id="f8708-151">Microsoft에서 문제가 선택한 엔터프라이즈 집합에 영향을 미치는지 여부와 영향을 미치는 엔터프라이즈 수를 식별할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="f8708-151">Allows Microsoft to identify whether issues are impacting a select set of enterprises and how many enterprises are impacted.</span></span> |
| <span data-ttu-id="f8708-152">hostname</span><span class="sxs-lookup"><span data-stu-id="f8708-152">hostname</span></span>                | <span data-ttu-id="f8708-153">로컬 장치 이름(DNS 접미사 불포기).</span><span class="sxs-lookup"><span data-stu-id="f8708-153">Local device name (without DNS suffix).</span></span> <span data-ttu-id="f8708-154">Microsoft에서 문제가 선택된 설치 집합에 영향을 미치는지 여부와 영향을 미치는 사용자 수를 식별할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="f8708-154">Allows Microsoft to identify whether issues are impacting a select set of installs and how many users are impacted.</span></span> |
| <span data-ttu-id="f8708-155">product_guid</span><span class="sxs-lookup"><span data-stu-id="f8708-155">product_guid</span></span>            | <span data-ttu-id="f8708-156">제품의 고유 식별자입니다.</span><span class="sxs-lookup"><span data-stu-id="f8708-156">Unique identifier of the product.</span></span> <span data-ttu-id="f8708-157">Microsoft에서 제품의 다양한 특징에 영향을 미치는 문제를 차별화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f8708-157">Allows Microsoft to differentiate issues impacting different flavors of the product.</span></span> |
| <span data-ttu-id="f8708-158">app_version</span><span class="sxs-lookup"><span data-stu-id="f8708-158">app_version</span></span>             | <span data-ttu-id="f8708-159">Mac용 끝점용 Microsoft Defender 응용 프로그램의 버전입니다.</span><span class="sxs-lookup"><span data-stu-id="f8708-159">Version of the Microsoft Defender for Endpoint for Mac application.</span></span> <span data-ttu-id="f8708-160">Microsoft에서 문제를 표시하는 제품 버전을 식별하여 제품의 우선 순위를 올바르게 지정할 수 있도록 허용합니다.</span><span class="sxs-lookup"><span data-stu-id="f8708-160">Allows Microsoft to identify which versions of the product are showing an issue so that it can correctly be prioritized.</span></span>|
| <span data-ttu-id="f8708-161">sig_version</span><span class="sxs-lookup"><span data-stu-id="f8708-161">sig_version</span></span>             | <span data-ttu-id="f8708-162">보안 인텔리전스 데이터베이스의 버전입니다.</span><span class="sxs-lookup"><span data-stu-id="f8708-162">Version of security intelligence database.</span></span> <span data-ttu-id="f8708-163">Microsoft에서 문제를 표시하는 보안 인텔리전스 버전을 식별하여 우선 순위를 올바르게 지정할 수 있도록 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f8708-163">Allows Microsoft to identify which versions of the security intelligence are showing an issue so that it can correctly be prioritized.</span></span> |
| <span data-ttu-id="f8708-164">supported_compressions</span><span class="sxs-lookup"><span data-stu-id="f8708-164">supported_compressions</span></span>  | <span data-ttu-id="f8708-165">응용 프로그램에서 지원하는 압축 알고리즘 목록(예: `['gzip']` ).</span><span class="sxs-lookup"><span data-stu-id="f8708-165">List of compression algorithms supported by the application, for example `['gzip']`.</span></span> <span data-ttu-id="f8708-166">Microsoft에서 응용 프로그램과 통신할 때 사용할 수 있는 압축 유형을 이해할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f8708-166">Allows Microsoft to understand what types of compressions can be used when it communicates with the application.</span></span> |
| <span data-ttu-id="f8708-167">release_ring</span><span class="sxs-lookup"><span data-stu-id="f8708-167">release_ring</span></span>            | <span data-ttu-id="f8708-168">디바이스가 연결된 링(예: Insider Fast, Insider Slow, Production)입니다.</span><span class="sxs-lookup"><span data-stu-id="f8708-168">Ring that the device is associated with (for example Insider Fast, Insider Slow, Production).</span></span> <span data-ttu-id="f8708-169">Microsoft에서 문제의 우선 순위를 올바르게 지정할 수 있도록 문제가 발생될 수 있는 릴리스 링을 식별할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f8708-169">Allows Microsoft to identify on which release ring an issue may be occurring so that it can correctly be prioritized.</span></span> |


### <a name="required-diagnostic-data"></a><span data-ttu-id="f8708-170">필수 진단 데이터</span><span class="sxs-lookup"><span data-stu-id="f8708-170">Required diagnostic data</span></span>

<span data-ttu-id="f8708-171">**필수 진단 데이터는** 끝점용 Microsoft Defender를 안전하고 최신으로 유지하며 설치된 디바이스에서 예상대로 수행하는 데 필요한 최소 데이터입니다.</span><span class="sxs-lookup"><span data-stu-id="f8708-171">**Required diagnostic data** is the minimum data necessary to help keep Microsoft Defender for Endpoint secure, up-to-date, and perform as expected on the device it’s installed on.</span></span>

<span data-ttu-id="f8708-172">필수 진단 데이터는 장치 또는 소프트웨어 구성과 관련이 있을 수 있는 끝점용 Microsoft Defender의 문제를 식별하는 데 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f8708-172">Required diagnostic data helps to identify problems with Microsoft Defender for Endpoint that may be related to a device or software configuration.</span></span> <span data-ttu-id="f8708-173">예를 들어 Microsoft Defender for Endpoint 기능이 특정 운영 체제 버전, 새로 도입된 기능 또는 특정 끝점용 Microsoft Defender 기능을 사용할 수 없는 경우 더 자주 충돌하는지 여부를 확인하는 데 도움이 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f8708-173">For example, it can help determine if a Microsoft Defender for Endpoint feature crashes more frequently on a particular operating system version, with newly introduced features, or when certain Microsoft Defender for Endpoint features are disabled.</span></span> <span data-ttu-id="f8708-174">필수 진단 데이터는 Microsoft에서 이러한 문제를 더 빠르게 감지, 진단 및 해결하여 사용자 또는 조직에 미치는 영향을 줄일 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="f8708-174">Required diagnostic data helps Microsoft detect, diagnose, and fix these problems more quickly so the impact to users or organizations is reduced.</span></span>

#### <a name="software-setup-and-inventory-data-events"></a><span data-ttu-id="f8708-175">소프트웨어 설치 및 인벤토리 데이터 이벤트</span><span class="sxs-lookup"><span data-stu-id="f8708-175">Software setup and inventory data events</span></span>

<span data-ttu-id="f8708-176">**끝점용 Microsoft Defender 설치/제거**</span><span class="sxs-lookup"><span data-stu-id="f8708-176">**Microsoft Defender for Endpoint installation / uninstallation**</span></span>

<span data-ttu-id="f8708-177">다음 필드가 수집됩니다.</span><span class="sxs-lookup"><span data-stu-id="f8708-177">The following fields are collected:</span></span>

| <span data-ttu-id="f8708-178">필드</span><span class="sxs-lookup"><span data-stu-id="f8708-178">Field</span></span>            | <span data-ttu-id="f8708-179">설명</span><span class="sxs-lookup"><span data-stu-id="f8708-179">Description</span></span> |
| ---------------- | ----------- |
| <span data-ttu-id="f8708-180">correlation_id</span><span class="sxs-lookup"><span data-stu-id="f8708-180">correlation_id</span></span>   | <span data-ttu-id="f8708-181">설치와 연결된 고유 식별자입니다.</span><span class="sxs-lookup"><span data-stu-id="f8708-181">Unique identifier associated with the installation.</span></span> |
| <span data-ttu-id="f8708-182">버전</span><span class="sxs-lookup"><span data-stu-id="f8708-182">version</span></span>          | <span data-ttu-id="f8708-183">패키지의 버전입니다.</span><span class="sxs-lookup"><span data-stu-id="f8708-183">Version of the package.</span></span> |
| <span data-ttu-id="f8708-184">심각도</span><span class="sxs-lookup"><span data-stu-id="f8708-184">severity</span></span>         | <span data-ttu-id="f8708-185">메시지의 심각도(예: 정보)</span><span class="sxs-lookup"><span data-stu-id="f8708-185">Severity of the message (for example Informational).</span></span> |
| <span data-ttu-id="f8708-186">code</span><span class="sxs-lookup"><span data-stu-id="f8708-186">code</span></span>             | <span data-ttu-id="f8708-187">작업을 설명하는 코드입니다.</span><span class="sxs-lookup"><span data-stu-id="f8708-187">Code that describes the operation.</span></span> |
| <span data-ttu-id="f8708-188">text</span><span class="sxs-lookup"><span data-stu-id="f8708-188">text</span></span>             | <span data-ttu-id="f8708-189">제품 설치와 관련된 추가 정보입니다.</span><span class="sxs-lookup"><span data-stu-id="f8708-189">Additional information associated with the product installation.</span></span> |

<span data-ttu-id="f8708-190">**끝점용 Microsoft Defender 구성**</span><span class="sxs-lookup"><span data-stu-id="f8708-190">**Microsoft Defender for Endpoint configuration**</span></span>

<span data-ttu-id="f8708-191">다음 필드가 수집됩니다.</span><span class="sxs-lookup"><span data-stu-id="f8708-191">The following fields are collected:</span></span>

| <span data-ttu-id="f8708-192">필드</span><span class="sxs-lookup"><span data-stu-id="f8708-192">Field</span></span>                                               | <span data-ttu-id="f8708-193">설명</span><span class="sxs-lookup"><span data-stu-id="f8708-193">Description</span></span> |
| --------------------------------------------------- | ----------- |
| <span data-ttu-id="f8708-194">antivirus_engine.enable_real_time_protection</span><span class="sxs-lookup"><span data-stu-id="f8708-194">antivirus_engine.enable_real_time_protection</span></span>        | <span data-ttu-id="f8708-195">장치에서 실시간 보호를 사용할 수 있는지 여부입니다.</span><span class="sxs-lookup"><span data-stu-id="f8708-195">Whether real-time protection is enabled on the device or not.</span></span> |
| <span data-ttu-id="f8708-196">antivirus_engine.passive_mode</span><span class="sxs-lookup"><span data-stu-id="f8708-196">antivirus_engine.passive_mode</span></span>                       | <span data-ttu-id="f8708-197">디바이스에서 수동 모드가 활성화되어 있는지 여부입니다.</span><span class="sxs-lookup"><span data-stu-id="f8708-197">Whether passive mode is enabled on the device or not.</span></span> |
| <span data-ttu-id="f8708-198">cloud_service.enabled</span><span class="sxs-lookup"><span data-stu-id="f8708-198">cloud_service.enabled</span></span>                               | <span data-ttu-id="f8708-199">클라우드 제공 보호가 장치에서 활성화되어 있는지 여부입니다.</span><span class="sxs-lookup"><span data-stu-id="f8708-199">Whether cloud delivered protection is enabled on the device or not.</span></span> |
| <span data-ttu-id="f8708-200">cloud_service.timeout</span><span class="sxs-lookup"><span data-stu-id="f8708-200">cloud_service.timeout</span></span>                               | <span data-ttu-id="f8708-201">응용 프로그램이 Microsoft Defender for Endpoint 클라우드와 통신할 때의 시간입니다.</span><span class="sxs-lookup"><span data-stu-id="f8708-201">Time out when the application communicates with the Microsoft Defender for Endpoint cloud.</span></span> |
| <span data-ttu-id="f8708-202">cloud_service.heartbeat_interval</span><span class="sxs-lookup"><span data-stu-id="f8708-202">cloud_service.heartbeat_interval</span></span>                    | <span data-ttu-id="f8708-203">제품이 클라우드로 전송한 연속 하트비트 사이의 간격입니다.</span><span class="sxs-lookup"><span data-stu-id="f8708-203">Interval between consecutive heartbeats sent by the product to the cloud.</span></span> |
| <span data-ttu-id="f8708-204">cloud_service.service_uri</span><span class="sxs-lookup"><span data-stu-id="f8708-204">cloud_service.service_uri</span></span>                           | <span data-ttu-id="f8708-205">클라우드와 통신하는 데 사용되는 URI입니다.</span><span class="sxs-lookup"><span data-stu-id="f8708-205">URI used to communicate with the cloud.</span></span> |
| <span data-ttu-id="f8708-206">cloud_service.diagnostic_level</span><span class="sxs-lookup"><span data-stu-id="f8708-206">cloud_service.diagnostic_level</span></span>                      | <span data-ttu-id="f8708-207">디바이스의 진단 수준(필수, 선택 사항)</span><span class="sxs-lookup"><span data-stu-id="f8708-207">Diagnostic level of the device (required, optional).</span></span> |
| <span data-ttu-id="f8708-208">cloud_service.automatic_sample_submission</span><span class="sxs-lookup"><span data-stu-id="f8708-208">cloud_service.automatic_sample_submission</span></span>           | <span data-ttu-id="f8708-209">자동 샘플 제출이 켜져 있는지 여부입니다.</span><span class="sxs-lookup"><span data-stu-id="f8708-209">Whether automatic sample submission is turned on or not.</span></span> |
| <span data-ttu-id="f8708-210">edr.early_preview</span><span class="sxs-lookup"><span data-stu-id="f8708-210">edr.early_preview</span></span>                                   | <span data-ttu-id="f8708-211">디바이스에서 EDR 초기 미리 보기 기능을 실행해야 하는지 여부입니다.</span><span class="sxs-lookup"><span data-stu-id="f8708-211">Whether the device should run EDR early preview features.</span></span> |
| <span data-ttu-id="f8708-212">edr.group_id</span><span class="sxs-lookup"><span data-stu-id="f8708-212">edr.group_id</span></span>                                        | <span data-ttu-id="f8708-213">검색 및 응답 구성 요소에서 사용하는 그룹 식별자입니다.</span><span class="sxs-lookup"><span data-stu-id="f8708-213">Group identifier used by the detection and response component.</span></span> |
| <span data-ttu-id="f8708-214">edr.tags</span><span class="sxs-lookup"><span data-stu-id="f8708-214">edr.tags</span></span>                                            | <span data-ttu-id="f8708-215">사용자 정의 태그.</span><span class="sxs-lookup"><span data-stu-id="f8708-215">User-defined tags.</span></span> |
| <span data-ttu-id="f8708-216">기능을 제공합니다. \[ 선택적 기능 이름\]</span><span class="sxs-lookup"><span data-stu-id="f8708-216">features.\[optional feature name\]</span></span>                  | <span data-ttu-id="f8708-217">미리 보기 기능 목록과 해당 기능의 사용 여부</span><span class="sxs-lookup"><span data-stu-id="f8708-217">List of preview features, along with whether they are enabled or not.</span></span> |

#### <a name="product-and-service-usage-data-events"></a><span data-ttu-id="f8708-218">제품 및 서비스 사용 데이터 이벤트</span><span class="sxs-lookup"><span data-stu-id="f8708-218">Product and service usage data events</span></span>

<span data-ttu-id="f8708-219">**보안 인텔리전스 업데이트 보고서**</span><span class="sxs-lookup"><span data-stu-id="f8708-219">**Security intelligence update report**</span></span>

<span data-ttu-id="f8708-220">다음 필드가 수집됩니다.</span><span class="sxs-lookup"><span data-stu-id="f8708-220">The following fields are collected:</span></span>

| <span data-ttu-id="f8708-221">필드</span><span class="sxs-lookup"><span data-stu-id="f8708-221">Field</span></span>            | <span data-ttu-id="f8708-222">설명</span><span class="sxs-lookup"><span data-stu-id="f8708-222">Description</span></span> |
| ---------------- | ----------- |
| <span data-ttu-id="f8708-223">from_version</span><span class="sxs-lookup"><span data-stu-id="f8708-223">from_version</span></span>     | <span data-ttu-id="f8708-224">원래 보안 인텔리전스 버전입니다.</span><span class="sxs-lookup"><span data-stu-id="f8708-224">Original security intelligence version.</span></span> |
| <span data-ttu-id="f8708-225">to_version</span><span class="sxs-lookup"><span data-stu-id="f8708-225">to_version</span></span>       | <span data-ttu-id="f8708-226">새 보안 인텔리전스 버전입니다.</span><span class="sxs-lookup"><span data-stu-id="f8708-226">New security intelligence version.</span></span> |
| <span data-ttu-id="f8708-227">status</span><span class="sxs-lookup"><span data-stu-id="f8708-227">status</span></span>           | <span data-ttu-id="f8708-228">성공 또는 실패를 나타내는 업데이트 상태입니다.</span><span class="sxs-lookup"><span data-stu-id="f8708-228">Status of the update indicating success or failure.</span></span> |
| <span data-ttu-id="f8708-229">using_proxy</span><span class="sxs-lookup"><span data-stu-id="f8708-229">using_proxy</span></span>      | <span data-ttu-id="f8708-230">업데이트가 프록시를 통해 수행된 것인지 여부입니다.</span><span class="sxs-lookup"><span data-stu-id="f8708-230">Whether the update was done over a proxy.</span></span> |
| <span data-ttu-id="f8708-231">error</span><span class="sxs-lookup"><span data-stu-id="f8708-231">error</span></span>            | <span data-ttu-id="f8708-232">업데이트가 실패한 경우 오류 코드입니다.</span><span class="sxs-lookup"><span data-stu-id="f8708-232">Error code if the update failed.</span></span> |
| <span data-ttu-id="f8708-233">이유</span><span class="sxs-lookup"><span data-stu-id="f8708-233">reason</span></span>           | <span data-ttu-id="f8708-234">업데이트된 파일을 제출한 경우 오류 메시지가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="f8708-234">Error message if the updated filed.</span></span> |

#### <a name="product-and-service-performance-data-events"></a><span data-ttu-id="f8708-235">제품 및 서비스 성능 데이터 이벤트</span><span class="sxs-lookup"><span data-stu-id="f8708-235">Product and service performance data events</span></span>

<span data-ttu-id="f8708-236">**예기치 않은 응용 프로그램 종료(크래시)**</span><span class="sxs-lookup"><span data-stu-id="f8708-236">**Unexpected application exit (crash)**</span></span>

<span data-ttu-id="f8708-237">응용 프로그램이 예기치 않게 종료된 경우 시스템 정보 및 응용 프로그램의 상태를 수집합니다.</span><span class="sxs-lookup"><span data-stu-id="f8708-237">Collects system information and the state of an application when an application unexpectedly exits.</span></span>

<span data-ttu-id="f8708-238">다음 필드가 수집됩니다.</span><span class="sxs-lookup"><span data-stu-id="f8708-238">The following fields are collected:</span></span>

| <span data-ttu-id="f8708-239">필드</span><span class="sxs-lookup"><span data-stu-id="f8708-239">Field</span></span>                          | <span data-ttu-id="f8708-240">설명</span><span class="sxs-lookup"><span data-stu-id="f8708-240">Description</span></span> |
| ------------------------------ | ----------- |
| <span data-ttu-id="f8708-241">v1_crash_count</span><span class="sxs-lookup"><span data-stu-id="f8708-241">v1_crash_count</span></span>                 | <span data-ttu-id="f8708-242">클라이언트 컴퓨터의 V1 엔진 프로세스가 매시간 중단된 횟수</span><span class="sxs-lookup"><span data-stu-id="f8708-242">Number of times V1 engine process crashed every hour on client machine</span></span>  |
| <span data-ttu-id="f8708-243">v2_crash_count</span><span class="sxs-lookup"><span data-stu-id="f8708-243">v2_crash_count</span></span>                 | <span data-ttu-id="f8708-244">클라이언트 컴퓨터의 V2 엔진 프로세스가 매시간 중단된 횟수</span><span class="sxs-lookup"><span data-stu-id="f8708-244">Number of times V2 engine process crashed every hour on client machine</span></span>  |
| <span data-ttu-id="f8708-245">EDR_crash_count</span><span class="sxs-lookup"><span data-stu-id="f8708-245">EDR_crash_count</span></span>                | <span data-ttu-id="f8708-246">클라이언트 컴퓨터의 EDR 프로세스가 매시간 중단된 횟수</span><span class="sxs-lookup"><span data-stu-id="f8708-246">Number of times EDR process crashed every hour on client machine</span></span>        |

<span data-ttu-id="f8708-247">**커널 확장 통계**</span><span class="sxs-lookup"><span data-stu-id="f8708-247">**Kernel extension statistics**</span></span>

<span data-ttu-id="f8708-248">다음 필드가 수집됩니다.</span><span class="sxs-lookup"><span data-stu-id="f8708-248">The following fields are collected:</span></span>

| <span data-ttu-id="f8708-249">필드</span><span class="sxs-lookup"><span data-stu-id="f8708-249">Field</span></span>            | <span data-ttu-id="f8708-250">설명</span><span class="sxs-lookup"><span data-stu-id="f8708-250">Description</span></span> |
| ---------------- | ----------- |
| <span data-ttu-id="f8708-251">버전</span><span class="sxs-lookup"><span data-stu-id="f8708-251">version</span></span>          | <span data-ttu-id="f8708-252">Mac용 끝점용 Microsoft Defender 버전입니다.</span><span class="sxs-lookup"><span data-stu-id="f8708-252">Version of Microsoft Defender for Endpoint for Mac.</span></span> |
| <span data-ttu-id="f8708-253">instance_id</span><span class="sxs-lookup"><span data-stu-id="f8708-253">instance_id</span></span>      | <span data-ttu-id="f8708-254">커널 확장 시작 시 생성된 고유 식별자입니다.</span><span class="sxs-lookup"><span data-stu-id="f8708-254">Unique identifier generated on kernel extension startup.</span></span> |
| <span data-ttu-id="f8708-255">trace_level</span><span class="sxs-lookup"><span data-stu-id="f8708-255">trace_level</span></span>      | <span data-ttu-id="f8708-256">커널 확장의 추적 수준입니다.</span><span class="sxs-lookup"><span data-stu-id="f8708-256">Trace level of the kernel extension.</span></span> |
| <span data-ttu-id="f8708-257">subsystem</span><span class="sxs-lookup"><span data-stu-id="f8708-257">subsystem</span></span>        | <span data-ttu-id="f8708-258">실시간 보호에 사용되는 밑이 있는 하위입니다.</span><span class="sxs-lookup"><span data-stu-id="f8708-258">The underlying subsystem used for real-time protection.</span></span> |
| <span data-ttu-id="f8708-259">ipc.connects</span><span class="sxs-lookup"><span data-stu-id="f8708-259">ipc.connects</span></span>     | <span data-ttu-id="f8708-260">커널 확장에서 수신한 연결 요청 수입니다.</span><span class="sxs-lookup"><span data-stu-id="f8708-260">Number of connection requests received by the kernel extension.</span></span> |
| <span data-ttu-id="f8708-261">ipc.rejects</span><span class="sxs-lookup"><span data-stu-id="f8708-261">ipc.rejects</span></span>      | <span data-ttu-id="f8708-262">커널 확장에서 거부된 연결 요청 수입니다.</span><span class="sxs-lookup"><span data-stu-id="f8708-262">Number of connection requests rejected by the kernel extension.</span></span> |
| <span data-ttu-id="f8708-263">ipc.connected</span><span class="sxs-lookup"><span data-stu-id="f8708-263">ipc.connected</span></span>    | <span data-ttu-id="f8708-264">커널 확장에 대한 활성 연결이 있는지 여부입니다.</span><span class="sxs-lookup"><span data-stu-id="f8708-264">Whether there is any active connection to the kernel extension.</span></span> |

#### <a name="support-data"></a><span data-ttu-id="f8708-265">지원 데이터</span><span class="sxs-lookup"><span data-stu-id="f8708-265">Support data</span></span>

<span data-ttu-id="f8708-266">**진단 로그**</span><span class="sxs-lookup"><span data-stu-id="f8708-266">**Diagnostic logs**</span></span>

<span data-ttu-id="f8708-267">진단 로그는 피드백 제출 기능의 일부로 사용자의 동의로만 수집됩니다.</span><span class="sxs-lookup"><span data-stu-id="f8708-267">Diagnostic logs are collected only with the consent of the user as part of the feedback submission feature.</span></span> <span data-ttu-id="f8708-268">다음 파일은 지원 로그의 일부로 수집됩니다.</span><span class="sxs-lookup"><span data-stu-id="f8708-268">The following files are collected as part of the support logs:</span></span>

- <span data-ttu-id="f8708-269">*/Library/Logs/Microsoft/mdatp/ 아래에 있는 모든 파일*</span><span class="sxs-lookup"><span data-stu-id="f8708-269">All files under */Library/Logs/Microsoft/mdatp/*</span></span>
- <span data-ttu-id="f8708-270">*Mac용 끝점용 Microsoft Defender에서 만들어 사용하는 /Library/Application Support/Microsoft/Defender/에서* 파일 하위 집합</span><span class="sxs-lookup"><span data-stu-id="f8708-270">Subset of files under */Library/Application Support/Microsoft/Defender/* that are created and used by Microsoft Defender for Endpoint for Mac</span></span>
- <span data-ttu-id="f8708-271">Mac용 끝점용 Microsoft Defender에서 사용하는 */Library/Managed Preferences* 아래에 있는 파일의 하위 집합</span><span class="sxs-lookup"><span data-stu-id="f8708-271">Subset of files under */Library/Managed Preferences* that are used by Microsoft Defender for Endpoint for Mac</span></span>
- <span data-ttu-id="f8708-272">/Library/Logs/Microsoft/autoupdate.log</span><span class="sxs-lookup"><span data-stu-id="f8708-272">/Library/Logs/Microsoft/autoupdate.log</span></span>
- <span data-ttu-id="f8708-273">$HOME/Library/Preferences/com.microsoft.autoupdate2.plist</span><span class="sxs-lookup"><span data-stu-id="f8708-273">$HOME/Library/Preferences/com.microsoft.autoupdate2.plist</span></span>

### <a name="optional-diagnostic-data"></a><span data-ttu-id="f8708-274">선택적 진단 데이터</span><span class="sxs-lookup"><span data-stu-id="f8708-274">Optional diagnostic data</span></span>

<span data-ttu-id="f8708-275">**선택적 진단 데이터는** Microsoft가 제품을 개선하는 데 도움이 되는 추가 데이터이며 문제를 감지, 진단 및 해결하는 데 도움이 되는 향상된 정보를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="f8708-275">**Optional diagnostic data** is additional data that helps Microsoft make product improvements and provides enhanced information to help detect, diagnose, and fix issues.</span></span>

<span data-ttu-id="f8708-276">선택 사항 진단 데이터를 보내시는 경우 필수 진단 데이터도 함께 보내야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f8708-276">If you choose to send us optional diagnostic data, required diagnostic data is also included.</span></span>

<span data-ttu-id="f8708-277">선택적 진단 데이터의 예로는 Microsoft가 제품 구성(예: 장치에 설정된 제외 수) 및 제품 성능(제품의 구성 요소 성능에 대한 집계 측정값)에 대해 수집하는 데이터가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="f8708-277">Examples of optional diagnostic data include data Microsoft collects about product configuration (for example number of exclusions set on the device) and product performance (aggregate measures about the performance of components of the product).</span></span>

#### <a name="software-setup-and-inventory-data-events"></a><span data-ttu-id="f8708-278">소프트웨어 설치 및 인벤토리 데이터 이벤트</span><span class="sxs-lookup"><span data-stu-id="f8708-278">Software setup and inventory data events</span></span>

<span data-ttu-id="f8708-279">**끝점용 Microsoft Defender 구성**</span><span class="sxs-lookup"><span data-stu-id="f8708-279">**Microsoft Defender for Endpoint configuration**</span></span>

<span data-ttu-id="f8708-280">다음 필드가 수집됩니다.</span><span class="sxs-lookup"><span data-stu-id="f8708-280">The following fields are collected:</span></span>

| <span data-ttu-id="f8708-281">필드</span><span class="sxs-lookup"><span data-stu-id="f8708-281">Field</span></span>                                              | <span data-ttu-id="f8708-282">설명</span><span class="sxs-lookup"><span data-stu-id="f8708-282">Description</span></span> |
| -------------------------------------------------- | ----------- |
| <span data-ttu-id="f8708-283">connection_retry_timeout</span><span class="sxs-lookup"><span data-stu-id="f8708-283">connection_retry_timeout</span></span>                           | <span data-ttu-id="f8708-284">클라우드와 통신할 때 연결 다시 시도 시간입니다.</span><span class="sxs-lookup"><span data-stu-id="f8708-284">Connection retry time out when communication with the cloud.</span></span> |
| <span data-ttu-id="f8708-285">file_hash_cache_maximum</span><span class="sxs-lookup"><span data-stu-id="f8708-285">file_hash_cache_maximum</span></span>                            | <span data-ttu-id="f8708-286">제품 캐시의 크기입니다.</span><span class="sxs-lookup"><span data-stu-id="f8708-286">Size of the product cache.</span></span> |
| <span data-ttu-id="f8708-287">crash_upload_daily_limit</span><span class="sxs-lookup"><span data-stu-id="f8708-287">crash_upload_daily_limit</span></span>                           | <span data-ttu-id="f8708-288">매일 업로드된 크래시 로그 제한.</span><span class="sxs-lookup"><span data-stu-id="f8708-288">Limit of crash logs uploaded daily.</span></span> |
| <span data-ttu-id="f8708-289">antivirus_engine.exclusions[].is_directory</span><span class="sxs-lookup"><span data-stu-id="f8708-289">antivirus_engine.exclusions[].is_directory</span></span>         | <span data-ttu-id="f8708-290">검사 제외가 디렉터리인지 여부입니다.</span><span class="sxs-lookup"><span data-stu-id="f8708-290">Whether the exclusion from scanning is a directory or not.</span></span> |
| <span data-ttu-id="f8708-291">antivirus_engine.exclusions[].path</span><span class="sxs-lookup"><span data-stu-id="f8708-291">antivirus_engine.exclusions[].path</span></span>                 | <span data-ttu-id="f8708-292">검사에서 제외된 경로입니다.</span><span class="sxs-lookup"><span data-stu-id="f8708-292">Path that was excluded from scanning.</span></span> |
| <span data-ttu-id="f8708-293">antivirus_engine.exclusions[].extension</span><span class="sxs-lookup"><span data-stu-id="f8708-293">antivirus_engine.exclusions[].extension</span></span>            | <span data-ttu-id="f8708-294">검색에서 제외된 확장명입니다.</span><span class="sxs-lookup"><span data-stu-id="f8708-294">Extension excluded from scanning.</span></span> |
| <span data-ttu-id="f8708-295">antivirus_engine.exclusions[].name</span><span class="sxs-lookup"><span data-stu-id="f8708-295">antivirus_engine.exclusions[].name</span></span>                 | <span data-ttu-id="f8708-296">검사에서 제외된 파일의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="f8708-296">Name of the file excluded from scanning.</span></span> |
| <span data-ttu-id="f8708-297">antivirus_engine.scan_cache_maximum</span><span class="sxs-lookup"><span data-stu-id="f8708-297">antivirus_engine.scan_cache_maximum</span></span>                | <span data-ttu-id="f8708-298">제품 캐시의 크기입니다.</span><span class="sxs-lookup"><span data-stu-id="f8708-298">Size of the product cache.</span></span> |
| <span data-ttu-id="f8708-299">antivirus_engine.maximum_scan_threads</span><span class="sxs-lookup"><span data-stu-id="f8708-299">antivirus_engine.maximum_scan_threads</span></span>              | <span data-ttu-id="f8708-300">검색에 사용되는 최대 스레드 수입니다.</span><span class="sxs-lookup"><span data-stu-id="f8708-300">Maximum number of threads used for scanning.</span></span> |
| <span data-ttu-id="f8708-301">antivirus_engine.threat_restoration_exclusion_time</span><span class="sxs-lookup"><span data-stu-id="f8708-301">antivirus_engine.threat_restoration_exclusion_time</span></span> | <span data-ttu-id="f8708-302">파일에서 복원된 파일을 다시 검색하기 전의 시간입니다.</span><span class="sxs-lookup"><span data-stu-id="f8708-302">Time out before a file restored from the quarantine can be detected again.</span></span> |
| <span data-ttu-id="f8708-303">filesystem_scanner.full_scan_directory</span><span class="sxs-lookup"><span data-stu-id="f8708-303">filesystem_scanner.full_scan_directory</span></span>             | <span data-ttu-id="f8708-304">전체 검사 디렉터리.</span><span class="sxs-lookup"><span data-stu-id="f8708-304">Full scan directory.</span></span> |
| <span data-ttu-id="f8708-305">filesystem_scanner.quick_scan_directories</span><span class="sxs-lookup"><span data-stu-id="f8708-305">filesystem_scanner.quick_scan_directories</span></span>          | <span data-ttu-id="f8708-306">빠른 검사에 사용되는렉터리 목록입니다.</span><span class="sxs-lookup"><span data-stu-id="f8708-306">List of directories used in quick scan.</span></span> |
| <span data-ttu-id="f8708-307">edr.latency_mode</span><span class="sxs-lookup"><span data-stu-id="f8708-307">edr.latency_mode</span></span>                                   | <span data-ttu-id="f8708-308">검색 및 응답 구성 요소에서 사용되는 대기 시간 모드입니다.</span><span class="sxs-lookup"><span data-stu-id="f8708-308">Latency mode used by the detection and response component.</span></span> |
| <span data-ttu-id="f8708-309">edr.proxy_address</span><span class="sxs-lookup"><span data-stu-id="f8708-309">edr.proxy_address</span></span>                                  | <span data-ttu-id="f8708-310">검색 및 응답 구성 요소에서 사용하는 프록시 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="f8708-310">Proxy address used by the detection and response component.</span></span> |

<span data-ttu-id="f8708-311">**Microsoft 자동 업데이트 구성**</span><span class="sxs-lookup"><span data-stu-id="f8708-311">**Microsoft Auto-Update configuration**</span></span>

<span data-ttu-id="f8708-312">다음 필드가 수집됩니다.</span><span class="sxs-lookup"><span data-stu-id="f8708-312">The following fields are collected:</span></span>

| <span data-ttu-id="f8708-313">필드</span><span class="sxs-lookup"><span data-stu-id="f8708-313">Field</span></span>                       | <span data-ttu-id="f8708-314">설명</span><span class="sxs-lookup"><span data-stu-id="f8708-314">Description</span></span> |
| --------------------------- | ----------- |
| <span data-ttu-id="f8708-315">how_to_check</span><span class="sxs-lookup"><span data-stu-id="f8708-315">how_to_check</span></span>                | <span data-ttu-id="f8708-316">자동 또는 수동과 같은 제품 업데이트를 확인하는 방법을 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="f8708-316">Determines how product updates are checked (for example automatic or manual).</span></span> |
| <span data-ttu-id="f8708-317">channel_name</span><span class="sxs-lookup"><span data-stu-id="f8708-317">channel_name</span></span>                | <span data-ttu-id="f8708-318">장치와 연결된 채널을 업데이트합니다.</span><span class="sxs-lookup"><span data-stu-id="f8708-318">Update channel associated with the device.</span></span> |
| <span data-ttu-id="f8708-319">manifest_server</span><span class="sxs-lookup"><span data-stu-id="f8708-319">manifest_server</span></span>             | <span data-ttu-id="f8708-320">업데이트를 다운로드하는 데 사용되는 서버입니다.</span><span class="sxs-lookup"><span data-stu-id="f8708-320">Server used for downloading updates.</span></span> |
| <span data-ttu-id="f8708-321">update_cache</span><span class="sxs-lookup"><span data-stu-id="f8708-321">update_cache</span></span>                | <span data-ttu-id="f8708-322">업데이트를 저장하는 데 사용되는 캐시 위치입니다.</span><span class="sxs-lookup"><span data-stu-id="f8708-322">Location of the cache used to store updates.</span></span> |

### <a name="product-and-service-usage"></a><span data-ttu-id="f8708-323">제품 및 서비스 사용</span><span class="sxs-lookup"><span data-stu-id="f8708-323">Product and service usage</span></span>

#### <a name="diagnostic-log-upload-started-report"></a><span data-ttu-id="f8708-324">진단 로그 업로드 시작 보고서</span><span class="sxs-lookup"><span data-stu-id="f8708-324">Diagnostic log upload started report</span></span>

<span data-ttu-id="f8708-325">다음 필드가 수집됩니다.</span><span class="sxs-lookup"><span data-stu-id="f8708-325">The following fields are collected:</span></span>

| <span data-ttu-id="f8708-326">필드</span><span class="sxs-lookup"><span data-stu-id="f8708-326">Field</span></span>            | <span data-ttu-id="f8708-327">설명</span><span class="sxs-lookup"><span data-stu-id="f8708-327">Description</span></span> |
| ---------------- | ----------- |
| <span data-ttu-id="f8708-328">sha256</span><span class="sxs-lookup"><span data-stu-id="f8708-328">sha256</span></span>           | <span data-ttu-id="f8708-329">지원 로그의 SHA256 식별자입니다.</span><span class="sxs-lookup"><span data-stu-id="f8708-329">SHA256 identifier of the support log.</span></span> |
| <span data-ttu-id="f8708-330">size</span><span class="sxs-lookup"><span data-stu-id="f8708-330">size</span></span>             | <span data-ttu-id="f8708-331">지원 로그의 크기입니다.</span><span class="sxs-lookup"><span data-stu-id="f8708-331">Size of the support log.</span></span> |
| <span data-ttu-id="f8708-332">original_path</span><span class="sxs-lookup"><span data-stu-id="f8708-332">original_path</span></span>    | <span data-ttu-id="f8708-333">지원 로그 경로(항상 */Library/Application Support/Microsoft/Defender/wdavdiag/* 아래)</span><span class="sxs-lookup"><span data-stu-id="f8708-333">Path to the support log (always under */Library/Application Support/Microsoft/Defender/wdavdiag/*).</span></span> |
| <span data-ttu-id="f8708-334">형식</span><span class="sxs-lookup"><span data-stu-id="f8708-334">format</span></span>           | <span data-ttu-id="f8708-335">지원 로그의 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="f8708-335">Format of the support log.</span></span> |

#### <a name="diagnostic-log-upload-completed-report"></a><span data-ttu-id="f8708-336">진단 로그 업로드 완료된 보고서</span><span class="sxs-lookup"><span data-stu-id="f8708-336">Diagnostic log upload completed report</span></span>

<span data-ttu-id="f8708-337">다음 필드가 수집됩니다.</span><span class="sxs-lookup"><span data-stu-id="f8708-337">The following fields are collected:</span></span>

| <span data-ttu-id="f8708-338">필드</span><span class="sxs-lookup"><span data-stu-id="f8708-338">Field</span></span>            | <span data-ttu-id="f8708-339">설명</span><span class="sxs-lookup"><span data-stu-id="f8708-339">Description</span></span> |
| ---------------- | ----------- |
| <span data-ttu-id="f8708-340">request_id</span><span class="sxs-lookup"><span data-stu-id="f8708-340">request_id</span></span>       | <span data-ttu-id="f8708-341">지원 로그 업로드 요청의 상관 관계 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="f8708-341">Correlation ID for the support log upload request.</span></span> |
| <span data-ttu-id="f8708-342">sha256</span><span class="sxs-lookup"><span data-stu-id="f8708-342">sha256</span></span>           | <span data-ttu-id="f8708-343">지원 로그의 SHA256 식별자입니다.</span><span class="sxs-lookup"><span data-stu-id="f8708-343">SHA256 identifier of the support log.</span></span> |
| <span data-ttu-id="f8708-344">blob_sas_uri</span><span class="sxs-lookup"><span data-stu-id="f8708-344">blob_sas_uri</span></span>     | <span data-ttu-id="f8708-345">응용 프로그램에서 지원 로그를 업로드하는 데 사용하는 URI입니다.</span><span class="sxs-lookup"><span data-stu-id="f8708-345">URI used by the application to upload the support log.</span></span> |

#### <a name="product-and-service-performance-data-events"></a><span data-ttu-id="f8708-346">제품 및 서비스 성능 데이터 이벤트</span><span class="sxs-lookup"><span data-stu-id="f8708-346">Product and service performance data events</span></span>

<span data-ttu-id="f8708-347">**예기치 않은 응용 프로그램 종료(크래시)**</span><span class="sxs-lookup"><span data-stu-id="f8708-347">**Unexpected application exit (crash)**</span></span>

<span data-ttu-id="f8708-348">예기치 않은 응용 프로그램 종료 및 종료 시의 응용 프로그램 상태입니다.</span><span class="sxs-lookup"><span data-stu-id="f8708-348">Unexpected application exits and the state of the application when that happens.</span></span>

<span data-ttu-id="f8708-349">**커널 확장 통계**</span><span class="sxs-lookup"><span data-stu-id="f8708-349">**Kernel extension statistics**</span></span>

<span data-ttu-id="f8708-350">다음 필드가 수집됩니다.</span><span class="sxs-lookup"><span data-stu-id="f8708-350">The following fields are collected:</span></span>

| <span data-ttu-id="f8708-351">필드</span><span class="sxs-lookup"><span data-stu-id="f8708-351">Field</span></span>                          | <span data-ttu-id="f8708-352">설명</span><span class="sxs-lookup"><span data-stu-id="f8708-352">Description</span></span> |
| ------------------------------ | ----------- |
| <span data-ttu-id="f8708-353">pkt_ack_timeout</span><span class="sxs-lookup"><span data-stu-id="f8708-353">pkt_ack_timeout</span></span>                | <span data-ttu-id="f8708-354">다음 속성은 커널 확장 시작 이후 발생된 이벤트 수를 나타내는 집계된 숫자 값입니다.</span><span class="sxs-lookup"><span data-stu-id="f8708-354">The following properties are aggregated numerical values, representing count of events that happened since kernel extension startup.</span></span> |
| <span data-ttu-id="f8708-355">pkt_ack_conn_timeout</span><span class="sxs-lookup"><span data-stu-id="f8708-355">pkt_ack_conn_timeout</span></span>             | |
| <span data-ttu-id="f8708-356">ipc.ack_pkts</span><span class="sxs-lookup"><span data-stu-id="f8708-356">ipc.ack_pkts</span></span>                     | |
| <span data-ttu-id="f8708-357">ipc.nack_pkts</span><span class="sxs-lookup"><span data-stu-id="f8708-357">ipc.nack_pkts</span></span>                    | |
| <span data-ttu-id="f8708-358">ipc.send.ack_no_conn</span><span class="sxs-lookup"><span data-stu-id="f8708-358">ipc.send.ack_no_conn</span></span>             | |
| <span data-ttu-id="f8708-359">ipc.send.nack_no_conn</span><span class="sxs-lookup"><span data-stu-id="f8708-359">ipc.send.nack_no_conn</span></span>            | |
| <span data-ttu-id="f8708-360">ipc.send.ack_no_qsq</span><span class="sxs-lookup"><span data-stu-id="f8708-360">ipc.send.ack_no_qsq</span></span>              | |
| <span data-ttu-id="f8708-361">ipc.send.nack_no_qsq</span><span class="sxs-lookup"><span data-stu-id="f8708-361">ipc.send.nack_no_qsq</span></span>             | |
| <span data-ttu-id="f8708-362">ipc.ack.no_space</span><span class="sxs-lookup"><span data-stu-id="f8708-362">ipc.ack.no_space</span></span>                 | |
| <span data-ttu-id="f8708-363">ipc.ack.timeout</span><span class="sxs-lookup"><span data-stu-id="f8708-363">ipc.ack.timeout</span></span>                  | |
| <span data-ttu-id="f8708-364">ipc.ack.ackd_fast</span><span class="sxs-lookup"><span data-stu-id="f8708-364">ipc.ack.ackd_fast</span></span>                | |
| <span data-ttu-id="f8708-365">ipc.ack.ackd</span><span class="sxs-lookup"><span data-stu-id="f8708-365">ipc.ack.ackd</span></span>                     | |
| <span data-ttu-id="f8708-366">ipc.recv.bad_pkt_len</span><span class="sxs-lookup"><span data-stu-id="f8708-366">ipc.recv.bad_pkt_len</span></span>             | |
| <span data-ttu-id="f8708-367">ipc.recv.bad_reply_len</span><span class="sxs-lookup"><span data-stu-id="f8708-367">ipc.recv.bad_reply_len</span></span>           | |
| <span data-ttu-id="f8708-368">ipc.recv.no_waiter</span><span class="sxs-lookup"><span data-stu-id="f8708-368">ipc.recv.no_waiter</span></span>               | |
| <span data-ttu-id="f8708-369">ipc.recv.copy_failed</span><span class="sxs-lookup"><span data-stu-id="f8708-369">ipc.recv.copy_failed</span></span>             | |
| <span data-ttu-id="f8708-370">ipc.kauth.vnode.mask</span><span class="sxs-lookup"><span data-stu-id="f8708-370">ipc.kauth.vnode.mask</span></span>             | |
| <span data-ttu-id="f8708-371">ipc.kauth.vnode.read</span><span class="sxs-lookup"><span data-stu-id="f8708-371">ipc.kauth.vnode.read</span></span>             | |
| <span data-ttu-id="f8708-372">ipc.kauth.vnode.write</span><span class="sxs-lookup"><span data-stu-id="f8708-372">ipc.kauth.vnode.write</span></span>            | |
| <span data-ttu-id="f8708-373">ipc.kauth.vnode.exec</span><span class="sxs-lookup"><span data-stu-id="f8708-373">ipc.kauth.vnode.exec</span></span>             | |
| <span data-ttu-id="f8708-374">ipc.kauth.vnode.del</span><span class="sxs-lookup"><span data-stu-id="f8708-374">ipc.kauth.vnode.del</span></span>              | |
| <span data-ttu-id="f8708-375">ipc.kauth.vnode.read_attr</span><span class="sxs-lookup"><span data-stu-id="f8708-375">ipc.kauth.vnode.read_attr</span></span>        | |
| <span data-ttu-id="f8708-376">ipc.kauth.vnode.write_attr</span><span class="sxs-lookup"><span data-stu-id="f8708-376">ipc.kauth.vnode.write_attr</span></span>       | |
| <span data-ttu-id="f8708-377">ipc.kauth.vnode.read_ex_attr</span><span class="sxs-lookup"><span data-stu-id="f8708-377">ipc.kauth.vnode.read_ex_attr</span></span>     | |
| <span data-ttu-id="f8708-378">ipc.kauth.vnode.write_ex_attr</span><span class="sxs-lookup"><span data-stu-id="f8708-378">ipc.kauth.vnode.write_ex_attr</span></span>    | |
| <span data-ttu-id="f8708-379">ipc.kauth.vnode.read_sec</span><span class="sxs-lookup"><span data-stu-id="f8708-379">ipc.kauth.vnode.read_sec</span></span>         | |
| <span data-ttu-id="f8708-380">ipc.kauth.vnode.write_sec</span><span class="sxs-lookup"><span data-stu-id="f8708-380">ipc.kauth.vnode.write_sec</span></span>        | |
| <span data-ttu-id="f8708-381">ipc.kauth.vnode.take_own</span><span class="sxs-lookup"><span data-stu-id="f8708-381">ipc.kauth.vnode.take_own</span></span>         | |
| <span data-ttu-id="f8708-382">ipc.kauth.vnode.link</span><span class="sxs-lookup"><span data-stu-id="f8708-382">ipc.kauth.vnode.link</span></span>             | |
| <span data-ttu-id="f8708-383">ipc.kauth.vnode.create</span><span class="sxs-lookup"><span data-stu-id="f8708-383">ipc.kauth.vnode.create</span></span>           | |
| <span data-ttu-id="f8708-384">ipc.kauth.vnode.move</span><span class="sxs-lookup"><span data-stu-id="f8708-384">ipc.kauth.vnode.move</span></span>             | |
| <span data-ttu-id="f8708-385">ipc.kauth.vnode.mount</span><span class="sxs-lookup"><span data-stu-id="f8708-385">ipc.kauth.vnode.mount</span></span>            | |
| <span data-ttu-id="f8708-386">ipc.kauth.vnode.denied</span><span class="sxs-lookup"><span data-stu-id="f8708-386">ipc.kauth.vnode.denied</span></span>           | |
| <span data-ttu-id="f8708-387">ipc.kauth.vnode.ackd_before_deadline</span><span class="sxs-lookup"><span data-stu-id="f8708-387">ipc.kauth.vnode.ackd_before_deadline</span></span> | |
| <span data-ttu-id="f8708-388">ipc.kauth.vnode.missed_deadline</span><span class="sxs-lookup"><span data-stu-id="f8708-388">ipc.kauth.vnode.missed_deadline</span></span>  | |
| <span data-ttu-id="f8708-389">ipc.kauth.file_op.mask</span><span class="sxs-lookup"><span data-stu-id="f8708-389">ipc.kauth.file_op.mask</span></span>           | |
| <span data-ttu-id="f8708-390">ipc.kauth_file_op.open</span><span class="sxs-lookup"><span data-stu-id="f8708-390">ipc.kauth_file_op.open</span></span>           | |
| <span data-ttu-id="f8708-391">ipc.kauth.file_op.close</span><span class="sxs-lookup"><span data-stu-id="f8708-391">ipc.kauth.file_op.close</span></span>          | |
| <span data-ttu-id="f8708-392">ipc.kauth.file_op.close_modified</span><span class="sxs-lookup"><span data-stu-id="f8708-392">ipc.kauth.file_op.close_modified</span></span> | |
| <span data-ttu-id="f8708-393">ipc.kauth.file_op.move</span><span class="sxs-lookup"><span data-stu-id="f8708-393">ipc.kauth.file_op.move</span></span>           | |
| <span data-ttu-id="f8708-394">ipc.kauth.file_op.link</span><span class="sxs-lookup"><span data-stu-id="f8708-394">ipc.kauth.file_op.link</span></span>           | |
| <span data-ttu-id="f8708-395">ipc.kauth.file_op.exec</span><span class="sxs-lookup"><span data-stu-id="f8708-395">ipc.kauth.file_op.exec</span></span>           | |
| <span data-ttu-id="f8708-396">ipc.kauth.file_op.remove</span><span class="sxs-lookup"><span data-stu-id="f8708-396">ipc.kauth.file_op.remove</span></span>         | |
| <span data-ttu-id="f8708-397">ipc.kauth.file_op.unmount</span><span class="sxs-lookup"><span data-stu-id="f8708-397">ipc.kauth.file_op.unmount</span></span>        | |
| <span data-ttu-id="f8708-398">ipc.kauth.file_op.fork</span><span class="sxs-lookup"><span data-stu-id="f8708-398">ipc.kauth.file_op.fork</span></span>           | |
| <span data-ttu-id="f8708-399">ipc.kauth.file_op.create</span><span class="sxs-lookup"><span data-stu-id="f8708-399">ipc.kauth.file_op.create</span></span>         | |

## <a name="resources"></a><span data-ttu-id="f8708-400">리소스</span><span class="sxs-lookup"><span data-stu-id="f8708-400">Resources</span></span>

- [<span data-ttu-id="f8708-401">Microsoft 개인 정보</span><span class="sxs-lookup"><span data-stu-id="f8708-401">Privacy at Microsoft</span></span>](https://privacy.microsoft.com/)
