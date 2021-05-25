---
title: Mac의 끝점용 Microsoft Defender 개인 정보
description: 개인 정보 제어, Mac의 끝점용 Microsoft Defender에서 수집된 진단 데이터에 대한 개인 정보 및 정보에 영향을 미치는 정책 설정을 구성하는 방법.
keywords: Microsoft, defender, Endpoint용 Microsoft Defender, mac, 개인 정보, 진단
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
ms.openlocfilehash: 2884ffc695abc1c6b4b5be9bbd7c9ad37ad05439
ms.sourcegitcommit: 07e536f1a6e335f114da55048844e4a866fe731b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/25/2021
ms.locfileid: "52651299"
---
# <a name="privacy-for-microsoft-defender-for-endpoint-on-macos"></a><span data-ttu-id="564de-104">MacOS의 끝점용 Microsoft Defender 개인 정보</span><span class="sxs-lookup"><span data-stu-id="564de-104">Privacy for Microsoft Defender for Endpoint on macOS</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="564de-105">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="564de-105">**Applies to:**</span></span>
- [<span data-ttu-id="564de-106">엔드포인트용 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="564de-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="564de-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="564de-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="564de-108">끝점용 Microsoft Defender를 경험하고 싶나요?</span><span class="sxs-lookup"><span data-stu-id="564de-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="564de-109">무료 평가판에 등록합니다.</span><span class="sxs-lookup"><span data-stu-id="564de-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

<span data-ttu-id="564de-110">Microsoft는 macOS에서 끝점용 Microsoft Defender를 사용할 때 데이터를 수집하고 사용하는 방법에 대해 선택해야 하는 정보와 컨트롤을 사용자에게 제공하기 위해 최선을 다하고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="564de-110">Microsoft is committed to providing you with the information and controls you need to make choices about how your data is collected and used when you’re using Microsoft Defender for Endpoint on macOS.</span></span>

<span data-ttu-id="564de-111">이 항목에서는 제품 내에서 사용할 수 있는 개인 정보 컨트롤, 정책 설정으로 이러한 컨트롤을 관리하는 방법 및 수집된 데이터 이벤트에 대한 세부 정보를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="564de-111">This topic describes the privacy controls available within the product, how to manage these controls with policy settings and more details on the data events that are collected.</span></span>

## <a name="overview-of-privacy-controls-in-microsoft-defender-for-endpoint-on-macos"></a><span data-ttu-id="564de-112">MacOS의 끝점에 대한 Microsoft Defender의 개인 정보 컨트롤 개요</span><span class="sxs-lookup"><span data-stu-id="564de-112">Overview of privacy controls in Microsoft Defender for Endpoint on macOS</span></span>

<span data-ttu-id="564de-113">이 섹션에서는 macOS의 끝점용 Microsoft Defender에서 수집한 다양한 유형의 데이터에 대한 개인 정보 컨트롤에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="564de-113">This section describes the privacy controls for the different types of data collected by Microsoft Defender for Endpoint on macOS.</span></span>

### <a name="diagnostic-data"></a><span data-ttu-id="564de-114">진단 데이터</span><span class="sxs-lookup"><span data-stu-id="564de-114">Diagnostic data</span></span>

<span data-ttu-id="564de-115">진단 데이터는 끝점용 Microsoft Defender를 안전하고 최신으로 유지하며, 문제를 감지, 진단 및 해결하며, 제품을 개선하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="564de-115">Diagnostic data is used to keep Microsoft Defender for Endpoint secure and up-to-date, detect, diagnose and fix problems, and also make product improvements.</span></span>

<span data-ttu-id="564de-116">일부 진단 데이터는 필수 사항이지만, 일부 진단 데이터는 선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="564de-116">Some diagnostic data is required, while some diagnostic data is optional.</span></span> <span data-ttu-id="564de-117">조직의 정책 설정과 같은 개인 정보 보호 컨트롤 사용을 통해 필수 또는 선택 사항 진단 데이터를 전송할지 여부를 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="564de-117">We give you the ability to choose whether to send us required or optional diagnostic data through the use of privacy controls, such as policy settings for organizations.</span></span>

<span data-ttu-id="564de-118">끝점용 Microsoft Defender 클라이언트 소프트웨어에 대한 진단 데이터에는 다음 두 가지 수준 중 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="564de-118">There are two levels of diagnostic data for Microsoft Defender for Endpoint client software that you can choose from:</span></span>

* <span data-ttu-id="564de-119">**필수:** 끝점용 Microsoft Defender를 안전하고 최신으로 유지하며 설치된 디바이스에서 예상대로 수행하는 데 필요한 최소 데이터입니다.</span><span class="sxs-lookup"><span data-stu-id="564de-119">**Required**: The minimum data necessary to help keep Microsoft Defender for Endpoint secure, up-to-date, and performing as expected on the device it’s installed on.</span></span>

* <span data-ttu-id="564de-120">**선택** 사항: Microsoft가 제품을 개선하고 문제를 감지, 진단 및 수정하는 데 도움이 되는 향상된 정보를 제공하는 추가 데이터입니다.</span><span class="sxs-lookup"><span data-stu-id="564de-120">**Optional**: Additional data that helps Microsoft make product improvements and provides enhanced information to help detect, diagnose, and remediate issues.</span></span>

<span data-ttu-id="564de-121">기본적으로 필수 진단 데이터만 Microsoft로 전송됩니다.</span><span class="sxs-lookup"><span data-stu-id="564de-121">By default, only required diagnostic data is sent to Microsoft.</span></span>

### <a name="cloud-delivered-protection-data"></a><span data-ttu-id="564de-122">클라우드 제공 보호 데이터</span><span class="sxs-lookup"><span data-stu-id="564de-122">Cloud delivered protection data</span></span>

<span data-ttu-id="564de-123">클라우드 제공 보호는 클라우드의 최신 보호 데이터에 액세스할 수 있도록 증가하고 더 빠른 보호를 제공하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="564de-123">Cloud delivered protection is used to provide increased and faster protection with access to the latest protection data in the cloud.</span></span>

<span data-ttu-id="564de-124">클라우드 제공 보호 서비스를 사용하도록 설정하는 것은 선택 사항이지만 끝점 및 네트워크 전체에서 맬웨어에 대한 중요한 보호 기능을 제공하기 때문에 이 서비스를 사용하도록 설정하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="564de-124">Enabling the cloud-delivered protection service is optional, however it is highly recommended because it provides important protection against malware on your endpoints and across your network.</span></span>

### <a name="sample-data"></a><span data-ttu-id="564de-125">예제 데이터</span><span class="sxs-lookup"><span data-stu-id="564de-125">Sample data</span></span>

<span data-ttu-id="564de-126">샘플 데이터는 의심스러운 Microsoft 샘플을 전송하여 분석할 수 있도록 제품의 보호 기능을 개선하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="564de-126">Sample data is used to improve the protection capabilities of the product, by sending Microsoft suspicious samples so they can be analyzed.</span></span> <span data-ttu-id="564de-127">자동 샘플 제출을 사용하도록 설정하는 것은 선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="564de-127">Enabling automatic sample submission is optional.</span></span>

<span data-ttu-id="564de-128">이 기능을 사용하도록 설정하고 수집된 샘플에 개인 정보가 포함될 가능성이 있는 경우 사용자에게 동의를 요청하는 메시지가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="564de-128">When this feature is enabled and the sample that is collected is likely to contain personal information, the user is prompted for consent.</span></span>

## <a name="manage-privacy-controls-with-policy-settings"></a><span data-ttu-id="564de-129">정책 설정을 사용하여 개인 정보 관리</span><span class="sxs-lookup"><span data-stu-id="564de-129">Manage privacy controls with policy settings</span></span>

<span data-ttu-id="564de-130">IT 관리자인 경우 엔터프라이즈 수준에서 이러한 컨트롤을 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="564de-130">If you're an IT administrator, you might want to configure these controls at the enterprise level.</span></span> 

<span data-ttu-id="564de-131">이전 섹션에서 설명한 다양한 유형의 데이터에 대한 개인 정보 컨트롤은 [MacOS의 끝점용 Microsoft Defender에](mac-preferences.md)대한 기본 설정 설정에 자세히 설명되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="564de-131">The privacy controls for the various types of data described in the preceding section are described in detail in [Set preferences for Microsoft Defender for Endpoint on macOS](mac-preferences.md).</span></span>

<span data-ttu-id="564de-132">새 정책 설정과 함께, 조직에서 정책 설정을 보다 광범위하게 구현하기 전에 구성한 설정이 원하는 영향을 미치도록 제한되고 제어되는 환경에서 신중하게 테스트해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="564de-132">As with any new policy settings, you should carefully test them out in a limited, controlled environment to ensure the settings that you configure have the desired effect before you implement the policy settings more widely in your organization.</span></span>

## <a name="diagnostic-data-events"></a><span data-ttu-id="564de-133">진단 데이터 이벤트</span><span class="sxs-lookup"><span data-stu-id="564de-133">Diagnostic data events</span></span>

<span data-ttu-id="564de-134">이 섹션에서는 필수 진단 데이터로 간주되는 항목과 선택적 진단 데이터로 간주되는 항목과 수집된 이벤트 및 필드에 대한 설명을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="564de-134">This section describes what is considered required diagnostic data and what is considered optional diagnostic data, along with a description of the events and fields that are collected.</span></span>

### <a name="data-fields-that-are-common-for-all-events"></a><span data-ttu-id="564de-135">모든 이벤트에 공통적인 데이터 필드</span><span class="sxs-lookup"><span data-stu-id="564de-135">Data fields that are common for all events</span></span>
<span data-ttu-id="564de-136">범주 또는 데이터 하위 형식에 관계없이 모든 이벤트에 공통적인 이벤트에 대한 몇 가지 정보가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="564de-136">There is some information about events that is common to all events, regardless of category or data subtype.</span></span> 

<span data-ttu-id="564de-137">다음 필드는 모든 이벤트에서 공통으로 간주됩니다.</span><span class="sxs-lookup"><span data-stu-id="564de-137">The following fields are considered common for all events:</span></span>

| <span data-ttu-id="564de-138">필드</span><span class="sxs-lookup"><span data-stu-id="564de-138">Field</span></span>                   | <span data-ttu-id="564de-139">설명</span><span class="sxs-lookup"><span data-stu-id="564de-139">Description</span></span> |
| ----------------------- | ----------- |
| <span data-ttu-id="564de-140">플랫폼</span><span class="sxs-lookup"><span data-stu-id="564de-140">platform</span></span>                | <span data-ttu-id="564de-141">앱이 실행되는 플랫폼의 광범위한 분류입니다.</span><span class="sxs-lookup"><span data-stu-id="564de-141">The broad classification of the platform on which the app is running.</span></span> <span data-ttu-id="564de-142">Microsoft에서 문제의 우선 순위를 올바르게 지정할 수 있도록 문제가 발생한 플랫폼을 식별할 수 있도록 허용합니다.</span><span class="sxs-lookup"><span data-stu-id="564de-142">Allows Microsoft to identify on which platforms an issue may be occurring so that it can correctly be prioritized.</span></span> |
| <span data-ttu-id="564de-143">machine_guid</span><span class="sxs-lookup"><span data-stu-id="564de-143">machine_guid</span></span>            | <span data-ttu-id="564de-144">장치와 연결된 고유 식별자입니다.</span><span class="sxs-lookup"><span data-stu-id="564de-144">Unique identifier associated with the device.</span></span> <span data-ttu-id="564de-145">Microsoft에서 문제가 선택된 설치 집합에 영향을 미치는지 여부와 영향을 미치는 사용자 수를 식별할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="564de-145">Allows Microsoft to identify whether issues are impacting a select set of installs and how many users are impacted.</span></span> |
| <span data-ttu-id="564de-146">sense_guid</span><span class="sxs-lookup"><span data-stu-id="564de-146">sense_guid</span></span>              | <span data-ttu-id="564de-147">장치와 연결된 고유 식별자입니다.</span><span class="sxs-lookup"><span data-stu-id="564de-147">Unique identifier associated with the device.</span></span> <span data-ttu-id="564de-148">Microsoft에서 문제가 선택된 설치 집합에 영향을 미치는지 여부와 영향을 미치는 사용자 수를 식별할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="564de-148">Allows Microsoft to identify whether issues are impacting a select set of installs and how many users are impacted.</span></span> |
| <span data-ttu-id="564de-149">org_id</span><span class="sxs-lookup"><span data-stu-id="564de-149">org_id</span></span>                  | <span data-ttu-id="564de-150">장치가 속한 엔터프라이즈와 연결된 고유 식별자입니다.</span><span class="sxs-lookup"><span data-stu-id="564de-150">Unique identifier associated with the enterprise that the device belongs to.</span></span> <span data-ttu-id="564de-151">Microsoft에서 문제가 선택한 엔터프라이즈 집합에 영향을 미치는지 여부와 영향을 미치는 엔터프라이즈 수를 식별할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="564de-151">Allows Microsoft to identify whether issues are impacting a select set of enterprises and how many enterprises are impacted.</span></span> |
| <span data-ttu-id="564de-152">hostname</span><span class="sxs-lookup"><span data-stu-id="564de-152">hostname</span></span>                | <span data-ttu-id="564de-153">로컬 장치 이름(DNS 접미사 불포기).</span><span class="sxs-lookup"><span data-stu-id="564de-153">Local device name (without DNS suffix).</span></span> <span data-ttu-id="564de-154">Microsoft에서 문제가 선택된 설치 집합에 영향을 미치는지 여부와 영향을 미치는 사용자 수를 식별할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="564de-154">Allows Microsoft to identify whether issues are impacting a select set of installs and how many users are impacted.</span></span> |
| <span data-ttu-id="564de-155">product_guid</span><span class="sxs-lookup"><span data-stu-id="564de-155">product_guid</span></span>            | <span data-ttu-id="564de-156">제품의 고유 식별자입니다.</span><span class="sxs-lookup"><span data-stu-id="564de-156">Unique identifier of the product.</span></span> <span data-ttu-id="564de-157">Microsoft에서 제품의 다양한 특징에 영향을 미치는 문제를 차별화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="564de-157">Allows Microsoft to differentiate issues impacting different flavors of the product.</span></span> |
| <span data-ttu-id="564de-158">app_version</span><span class="sxs-lookup"><span data-stu-id="564de-158">app_version</span></span>             | <span data-ttu-id="564de-159">macOS 응용 프로그램의 끝점용 Microsoft Defender 버전입니다.</span><span class="sxs-lookup"><span data-stu-id="564de-159">Version of the Microsoft Defender for Endpoint on macOS application.</span></span> <span data-ttu-id="564de-160">Microsoft에서 문제를 표시하는 제품 버전을 식별하여 제품의 우선 순위를 올바르게 지정할 수 있도록 허용합니다.</span><span class="sxs-lookup"><span data-stu-id="564de-160">Allows Microsoft to identify which versions of the product are showing an issue so that it can correctly be prioritized.</span></span>|
| <span data-ttu-id="564de-161">sig_version</span><span class="sxs-lookup"><span data-stu-id="564de-161">sig_version</span></span>             | <span data-ttu-id="564de-162">보안 인텔리전스 데이터베이스의 버전입니다.</span><span class="sxs-lookup"><span data-stu-id="564de-162">Version of security intelligence database.</span></span> <span data-ttu-id="564de-163">Microsoft에서 문제를 표시하는 보안 인텔리전스 버전을 식별하여 우선 순위를 올바르게 지정할 수 있도록 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="564de-163">Allows Microsoft to identify which versions of the security intelligence are showing an issue so that it can correctly be prioritized.</span></span> |
| <span data-ttu-id="564de-164">supported_compressions</span><span class="sxs-lookup"><span data-stu-id="564de-164">supported_compressions</span></span>  | <span data-ttu-id="564de-165">응용 프로그램에서 지원하는 압축 알고리즘 목록(예: `['gzip']` ).</span><span class="sxs-lookup"><span data-stu-id="564de-165">List of compression algorithms supported by the application, for example `['gzip']`.</span></span> <span data-ttu-id="564de-166">Microsoft에서 응용 프로그램과 통신할 때 사용할 수 있는 압축 유형을 이해할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="564de-166">Allows Microsoft to understand what types of compressions can be used when it communicates with the application.</span></span> |
| <span data-ttu-id="564de-167">release_ring</span><span class="sxs-lookup"><span data-stu-id="564de-167">release_ring</span></span>            | <span data-ttu-id="564de-168">디바이스가 연결된 링(예: Insider Fast, Insider Slow, Production)입니다.</span><span class="sxs-lookup"><span data-stu-id="564de-168">Ring that the device is associated with (for example Insider Fast, Insider Slow, Production).</span></span> <span data-ttu-id="564de-169">Microsoft에서 문제의 우선 순위를 올바르게 지정할 수 있도록 문제가 발생될 수 있는 릴리스 링을 식별할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="564de-169">Allows Microsoft to identify on which release ring an issue may be occurring so that it can correctly be prioritized.</span></span> |


### <a name="required-diagnostic-data"></a><span data-ttu-id="564de-170">필수 진단 데이터</span><span class="sxs-lookup"><span data-stu-id="564de-170">Required diagnostic data</span></span>

<span data-ttu-id="564de-171">**필수 진단 데이터는** 끝점용 Microsoft Defender를 안전하고 최신으로 유지하며 설치된 디바이스에서 예상대로 수행하는 데 필요한 최소 데이터입니다.</span><span class="sxs-lookup"><span data-stu-id="564de-171">**Required diagnostic data** is the minimum data necessary to help keep Microsoft Defender for Endpoint secure, up-to-date, and perform as expected on the device it’s installed on.</span></span>

<span data-ttu-id="564de-172">필수 진단 데이터는 장치 또는 소프트웨어 구성과 관련이 있을 수 있는 끝점용 Microsoft Defender의 문제를 식별하는 데 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="564de-172">Required diagnostic data helps to identify problems with Microsoft Defender for Endpoint that may be related to a device or software configuration.</span></span> <span data-ttu-id="564de-173">예를 들어 Microsoft Defender for Endpoint 기능이 특정 운영 체제 버전, 새로 도입된 기능 또는 특정 끝점용 Microsoft Defender 기능을 사용할 수 없는 경우 더 자주 충돌하는지 여부를 확인하는 데 도움이 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="564de-173">For example, it can help determine if a Microsoft Defender for Endpoint feature crashes more frequently on a particular operating system version, with newly introduced features, or when certain Microsoft Defender for Endpoint features are disabled.</span></span> <span data-ttu-id="564de-174">필수 진단 데이터는 Microsoft에서 이러한 문제를 더 빠르게 감지, 진단 및 해결하여 사용자 또는 조직에 미치는 영향을 줄일 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="564de-174">Required diagnostic data helps Microsoft detect, diagnose, and fix these problems more quickly so the impact to users or organizations is reduced.</span></span>

#### <a name="software-setup-and-inventory-data-events"></a><span data-ttu-id="564de-175">소프트웨어 설치 및 인벤토리 데이터 이벤트</span><span class="sxs-lookup"><span data-stu-id="564de-175">Software setup and inventory data events</span></span>

<span data-ttu-id="564de-176">**끝점용 Microsoft Defender 설치/제거**</span><span class="sxs-lookup"><span data-stu-id="564de-176">**Microsoft Defender for Endpoint installation / uninstallation**</span></span>

<span data-ttu-id="564de-177">다음 필드가 수집됩니다.</span><span class="sxs-lookup"><span data-stu-id="564de-177">The following fields are collected:</span></span>

| <span data-ttu-id="564de-178">필드</span><span class="sxs-lookup"><span data-stu-id="564de-178">Field</span></span>            | <span data-ttu-id="564de-179">설명</span><span class="sxs-lookup"><span data-stu-id="564de-179">Description</span></span> |
| ---------------- | ----------- |
| <span data-ttu-id="564de-180">correlation_id</span><span class="sxs-lookup"><span data-stu-id="564de-180">correlation_id</span></span>   | <span data-ttu-id="564de-181">설치와 연결된 고유 식별자입니다.</span><span class="sxs-lookup"><span data-stu-id="564de-181">Unique identifier associated with the installation.</span></span> |
| <span data-ttu-id="564de-182">버전</span><span class="sxs-lookup"><span data-stu-id="564de-182">version</span></span>          | <span data-ttu-id="564de-183">패키지의 버전입니다.</span><span class="sxs-lookup"><span data-stu-id="564de-183">Version of the package.</span></span> |
| <span data-ttu-id="564de-184">심각도</span><span class="sxs-lookup"><span data-stu-id="564de-184">severity</span></span>         | <span data-ttu-id="564de-185">메시지의 심각도(예: 정보)</span><span class="sxs-lookup"><span data-stu-id="564de-185">Severity of the message (for example Informational).</span></span> |
| <span data-ttu-id="564de-186">code</span><span class="sxs-lookup"><span data-stu-id="564de-186">code</span></span>             | <span data-ttu-id="564de-187">작업을 설명하는 코드입니다.</span><span class="sxs-lookup"><span data-stu-id="564de-187">Code that describes the operation.</span></span> |
| <span data-ttu-id="564de-188">text</span><span class="sxs-lookup"><span data-stu-id="564de-188">text</span></span>             | <span data-ttu-id="564de-189">제품 설치와 관련된 추가 정보입니다.</span><span class="sxs-lookup"><span data-stu-id="564de-189">Additional information associated with the product installation.</span></span> |

<span data-ttu-id="564de-190">**끝점용 Microsoft Defender 구성**</span><span class="sxs-lookup"><span data-stu-id="564de-190">**Microsoft Defender for Endpoint configuration**</span></span>

<span data-ttu-id="564de-191">다음 필드가 수집됩니다.</span><span class="sxs-lookup"><span data-stu-id="564de-191">The following fields are collected:</span></span>

| <span data-ttu-id="564de-192">필드</span><span class="sxs-lookup"><span data-stu-id="564de-192">Field</span></span>                                               | <span data-ttu-id="564de-193">설명</span><span class="sxs-lookup"><span data-stu-id="564de-193">Description</span></span> |
| --------------------------------------------------- | ----------- |
| <span data-ttu-id="564de-194">antivirus_engine.enable_real_time_protection</span><span class="sxs-lookup"><span data-stu-id="564de-194">antivirus_engine.enable_real_time_protection</span></span>        | <span data-ttu-id="564de-195">장치에서 실시간 보호를 사용할 수 있는지 여부입니다.</span><span class="sxs-lookup"><span data-stu-id="564de-195">Whether real-time protection is enabled on the device or not.</span></span> |
| <span data-ttu-id="564de-196">antivirus_engine.passive_mode</span><span class="sxs-lookup"><span data-stu-id="564de-196">antivirus_engine.passive_mode</span></span>                       | <span data-ttu-id="564de-197">디바이스에서 수동 모드가 활성화되어 있는지 여부입니다.</span><span class="sxs-lookup"><span data-stu-id="564de-197">Whether passive mode is enabled on the device or not.</span></span> |
| <span data-ttu-id="564de-198">cloud_service.enabled</span><span class="sxs-lookup"><span data-stu-id="564de-198">cloud_service.enabled</span></span>                               | <span data-ttu-id="564de-199">클라우드 제공 보호가 장치에서 활성화되어 있는지 여부입니다.</span><span class="sxs-lookup"><span data-stu-id="564de-199">Whether cloud delivered protection is enabled on the device or not.</span></span> |
| <span data-ttu-id="564de-200">cloud_service.timeout</span><span class="sxs-lookup"><span data-stu-id="564de-200">cloud_service.timeout</span></span>                               | <span data-ttu-id="564de-201">응용 프로그램이 Microsoft Defender for Endpoint 클라우드와 통신할 때의 시간입니다.</span><span class="sxs-lookup"><span data-stu-id="564de-201">Time out when the application communicates with the Microsoft Defender for Endpoint cloud.</span></span> |
| <span data-ttu-id="564de-202">cloud_service.heartbeat_interval</span><span class="sxs-lookup"><span data-stu-id="564de-202">cloud_service.heartbeat_interval</span></span>                    | <span data-ttu-id="564de-203">제품이 클라우드로 전송한 연속 하트비트 사이의 간격입니다.</span><span class="sxs-lookup"><span data-stu-id="564de-203">Interval between consecutive heartbeats sent by the product to the cloud.</span></span> |
| <span data-ttu-id="564de-204">cloud_service.service_uri</span><span class="sxs-lookup"><span data-stu-id="564de-204">cloud_service.service_uri</span></span>                           | <span data-ttu-id="564de-205">클라우드와 통신하는 데 사용되는 URI입니다.</span><span class="sxs-lookup"><span data-stu-id="564de-205">URI used to communicate with the cloud.</span></span> |
| <span data-ttu-id="564de-206">cloud_service.diagnostic_level</span><span class="sxs-lookup"><span data-stu-id="564de-206">cloud_service.diagnostic_level</span></span>                      | <span data-ttu-id="564de-207">디바이스의 진단 수준(필수, 선택 사항)</span><span class="sxs-lookup"><span data-stu-id="564de-207">Diagnostic level of the device (required, optional).</span></span> |
| <span data-ttu-id="564de-208">cloud_service.automatic_sample_submission</span><span class="sxs-lookup"><span data-stu-id="564de-208">cloud_service.automatic_sample_submission</span></span>           | <span data-ttu-id="564de-209">자동 샘플 제출이 켜져 있는지 여부입니다.</span><span class="sxs-lookup"><span data-stu-id="564de-209">Whether automatic sample submission is turned on or not.</span></span> |
| <span data-ttu-id="564de-210">cloud_service.automatic_definition_update_enabled</span><span class="sxs-lookup"><span data-stu-id="564de-210">cloud_service.automatic_definition_update_enabled</span></span>   | <span data-ttu-id="564de-211">자동 정의 업데이트가 켜져 있는지 여부입니다.</span><span class="sxs-lookup"><span data-stu-id="564de-211">Whether automatic definition update is turned on or not.</span></span> |
| <span data-ttu-id="564de-212">edr.early_preview</span><span class="sxs-lookup"><span data-stu-id="564de-212">edr.early_preview</span></span>                                   | <span data-ttu-id="564de-213">디바이스가 초기 미리 보기 EDR 실행해야 하는지 여부입니다.</span><span class="sxs-lookup"><span data-stu-id="564de-213">Whether the device should run EDR early preview features.</span></span> |
| <span data-ttu-id="564de-214">edr.group_id</span><span class="sxs-lookup"><span data-stu-id="564de-214">edr.group_id</span></span>                                        | <span data-ttu-id="564de-215">검색 및 응답 구성 요소에서 사용하는 그룹 식별자입니다.</span><span class="sxs-lookup"><span data-stu-id="564de-215">Group identifier used by the detection and response component.</span></span> |
| <span data-ttu-id="564de-216">edr.tags</span><span class="sxs-lookup"><span data-stu-id="564de-216">edr.tags</span></span>                                            | <span data-ttu-id="564de-217">사용자 정의 태그.</span><span class="sxs-lookup"><span data-stu-id="564de-217">User-defined tags.</span></span> |
| <span data-ttu-id="564de-218">기능을 제공합니다. \[ 선택적 기능 이름\]</span><span class="sxs-lookup"><span data-stu-id="564de-218">features.\[optional feature name\]</span></span>                  | <span data-ttu-id="564de-219">미리 보기 기능 목록과 해당 기능의 사용 여부</span><span class="sxs-lookup"><span data-stu-id="564de-219">List of preview features, along with whether they are enabled or not.</span></span> |

#### <a name="product-and-service-usage-data-events"></a><span data-ttu-id="564de-220">제품 및 서비스 사용 데이터 이벤트</span><span class="sxs-lookup"><span data-stu-id="564de-220">Product and service usage data events</span></span>

<span data-ttu-id="564de-221">**보안 인텔리전스 업데이트 보고서**</span><span class="sxs-lookup"><span data-stu-id="564de-221">**Security intelligence update report**</span></span>

<span data-ttu-id="564de-222">다음 필드가 수집됩니다.</span><span class="sxs-lookup"><span data-stu-id="564de-222">The following fields are collected:</span></span>

| <span data-ttu-id="564de-223">필드</span><span class="sxs-lookup"><span data-stu-id="564de-223">Field</span></span>            | <span data-ttu-id="564de-224">설명</span><span class="sxs-lookup"><span data-stu-id="564de-224">Description</span></span> |
| ---------------- | ----------- |
| <span data-ttu-id="564de-225">from_version</span><span class="sxs-lookup"><span data-stu-id="564de-225">from_version</span></span>     | <span data-ttu-id="564de-226">원래 보안 인텔리전스 버전입니다.</span><span class="sxs-lookup"><span data-stu-id="564de-226">Original security intelligence version.</span></span> |
| <span data-ttu-id="564de-227">to_version</span><span class="sxs-lookup"><span data-stu-id="564de-227">to_version</span></span>       | <span data-ttu-id="564de-228">새 보안 인텔리전스 버전입니다.</span><span class="sxs-lookup"><span data-stu-id="564de-228">New security intelligence version.</span></span> |
| <span data-ttu-id="564de-229">status</span><span class="sxs-lookup"><span data-stu-id="564de-229">status</span></span>           | <span data-ttu-id="564de-230">성공 또는 실패를 나타내는 업데이트 상태입니다.</span><span class="sxs-lookup"><span data-stu-id="564de-230">Status of the update indicating success or failure.</span></span> |
| <span data-ttu-id="564de-231">using_proxy</span><span class="sxs-lookup"><span data-stu-id="564de-231">using_proxy</span></span>      | <span data-ttu-id="564de-232">업데이트가 프록시를 통해 수행된 것인지 여부입니다.</span><span class="sxs-lookup"><span data-stu-id="564de-232">Whether the update was done over a proxy.</span></span> |
| <span data-ttu-id="564de-233">error</span><span class="sxs-lookup"><span data-stu-id="564de-233">error</span></span>            | <span data-ttu-id="564de-234">업데이트가 실패한 경우 오류 코드입니다.</span><span class="sxs-lookup"><span data-stu-id="564de-234">Error code if the update failed.</span></span> |
| <span data-ttu-id="564de-235">이유</span><span class="sxs-lookup"><span data-stu-id="564de-235">reason</span></span>           | <span data-ttu-id="564de-236">업데이트된 파일을 제출한 경우 오류 메시지가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="564de-236">Error message if the updated filed.</span></span> |

#### <a name="product-and-service-performance-data-events"></a><span data-ttu-id="564de-237">제품 및 서비스 성능 데이터 이벤트</span><span class="sxs-lookup"><span data-stu-id="564de-237">Product and service performance data events</span></span>

<span data-ttu-id="564de-238">**예기치 않은 응용 프로그램 종료(크래시)**</span><span class="sxs-lookup"><span data-stu-id="564de-238">**Unexpected application exit (crash)**</span></span>

<span data-ttu-id="564de-239">응용 프로그램이 예기치 않게 종료된 경우 시스템 정보 및 응용 프로그램의 상태를 수집합니다.</span><span class="sxs-lookup"><span data-stu-id="564de-239">Collects system information and the state of an application when an application unexpectedly exits.</span></span>

<span data-ttu-id="564de-240">다음 필드가 수집됩니다.</span><span class="sxs-lookup"><span data-stu-id="564de-240">The following fields are collected:</span></span>

| <span data-ttu-id="564de-241">필드</span><span class="sxs-lookup"><span data-stu-id="564de-241">Field</span></span>                          | <span data-ttu-id="564de-242">설명</span><span class="sxs-lookup"><span data-stu-id="564de-242">Description</span></span> |
| ------------------------------ | ----------- |
| <span data-ttu-id="564de-243">v1_crash_count</span><span class="sxs-lookup"><span data-stu-id="564de-243">v1_crash_count</span></span>                 | <span data-ttu-id="564de-244">클라이언트 컴퓨터의 V1 엔진 프로세스가 매시간 중단된 횟수</span><span class="sxs-lookup"><span data-stu-id="564de-244">Number of times V1 engine process crashed every hour on client machine</span></span>  |
| <span data-ttu-id="564de-245">v2_crash_count</span><span class="sxs-lookup"><span data-stu-id="564de-245">v2_crash_count</span></span>                 | <span data-ttu-id="564de-246">클라이언트 컴퓨터의 V2 엔진 프로세스가 매시간 중단된 횟수</span><span class="sxs-lookup"><span data-stu-id="564de-246">Number of times V2 engine process crashed every hour on client machine</span></span>  |
| <span data-ttu-id="564de-247">EDR_crash_count</span><span class="sxs-lookup"><span data-stu-id="564de-247">EDR_crash_count</span></span>                | <span data-ttu-id="564de-248">클라이언트 EDR 프로세스가 중단된 횟수</span><span class="sxs-lookup"><span data-stu-id="564de-248">Number of times EDR process crashed every hour on client machine</span></span>        |

<span data-ttu-id="564de-249">**커널 확장 통계**</span><span class="sxs-lookup"><span data-stu-id="564de-249">**Kernel extension statistics**</span></span>

<span data-ttu-id="564de-250">다음 필드가 수집됩니다.</span><span class="sxs-lookup"><span data-stu-id="564de-250">The following fields are collected:</span></span>

| <span data-ttu-id="564de-251">필드</span><span class="sxs-lookup"><span data-stu-id="564de-251">Field</span></span>            | <span data-ttu-id="564de-252">설명</span><span class="sxs-lookup"><span data-stu-id="564de-252">Description</span></span> |
| ---------------- | ----------- |
| <span data-ttu-id="564de-253">버전</span><span class="sxs-lookup"><span data-stu-id="564de-253">version</span></span>          | <span data-ttu-id="564de-254">macOS의 끝점용 Microsoft Defender 버전입니다.</span><span class="sxs-lookup"><span data-stu-id="564de-254">Version of Microsoft Defender for Endpoint on macOS.</span></span> |
| <span data-ttu-id="564de-255">instance_id</span><span class="sxs-lookup"><span data-stu-id="564de-255">instance_id</span></span>      | <span data-ttu-id="564de-256">커널 확장 시작 시 생성된 고유 식별자입니다.</span><span class="sxs-lookup"><span data-stu-id="564de-256">Unique identifier generated on kernel extension startup.</span></span> |
| <span data-ttu-id="564de-257">trace_level</span><span class="sxs-lookup"><span data-stu-id="564de-257">trace_level</span></span>      | <span data-ttu-id="564de-258">커널 확장의 추적 수준입니다.</span><span class="sxs-lookup"><span data-stu-id="564de-258">Trace level of the kernel extension.</span></span> |
| <span data-ttu-id="564de-259">subsystem</span><span class="sxs-lookup"><span data-stu-id="564de-259">subsystem</span></span>        | <span data-ttu-id="564de-260">실시간 보호에 사용되는 밑이 있는 하위입니다.</span><span class="sxs-lookup"><span data-stu-id="564de-260">The underlying subsystem used for real-time protection.</span></span> |
| <span data-ttu-id="564de-261">ipc.connects</span><span class="sxs-lookup"><span data-stu-id="564de-261">ipc.connects</span></span>     | <span data-ttu-id="564de-262">커널 확장에서 수신한 연결 요청 수입니다.</span><span class="sxs-lookup"><span data-stu-id="564de-262">Number of connection requests received by the kernel extension.</span></span> |
| <span data-ttu-id="564de-263">ipc.rejects</span><span class="sxs-lookup"><span data-stu-id="564de-263">ipc.rejects</span></span>      | <span data-ttu-id="564de-264">커널 확장에서 거부된 연결 요청 수입니다.</span><span class="sxs-lookup"><span data-stu-id="564de-264">Number of connection requests rejected by the kernel extension.</span></span> |
| <span data-ttu-id="564de-265">ipc.connected</span><span class="sxs-lookup"><span data-stu-id="564de-265">ipc.connected</span></span>    | <span data-ttu-id="564de-266">커널 확장에 대한 활성 연결이 있는지 여부입니다.</span><span class="sxs-lookup"><span data-stu-id="564de-266">Whether there is any active connection to the kernel extension.</span></span> |

#### <a name="support-data"></a><span data-ttu-id="564de-267">지원 데이터</span><span class="sxs-lookup"><span data-stu-id="564de-267">Support data</span></span>

<span data-ttu-id="564de-268">**진단 로그**</span><span class="sxs-lookup"><span data-stu-id="564de-268">**Diagnostic logs**</span></span>

<span data-ttu-id="564de-269">진단 로그는 피드백 제출 기능의 일부로 사용자의 동의로만 수집됩니다.</span><span class="sxs-lookup"><span data-stu-id="564de-269">Diagnostic logs are collected only with the consent of the user as part of the feedback submission feature.</span></span> <span data-ttu-id="564de-270">다음 파일은 지원 로그의 일부로 수집됩니다.</span><span class="sxs-lookup"><span data-stu-id="564de-270">The following files are collected as part of the support logs:</span></span>

- <span data-ttu-id="564de-271">*/Library/Logs/Microsoft/mdatp/ 아래에 있는 모든 파일*</span><span class="sxs-lookup"><span data-stu-id="564de-271">All files under */Library/Logs/Microsoft/mdatp/*</span></span>
- <span data-ttu-id="564de-272">*MacOS의 끝점용 Microsoft Defender에서 만들어 사용하는 /Library/Application Support/Microsoft/Defender/에서* 파일 하위 집합</span><span class="sxs-lookup"><span data-stu-id="564de-272">Subset of files under */Library/Application Support/Microsoft/Defender/* that are created and used by Microsoft Defender for Endpoint on macOS</span></span>
- <span data-ttu-id="564de-273">macOS의 끝점용 Microsoft Defender에서 사용하는 */Library/Managed Preferences* 아래에 있는 파일의 하위 집합</span><span class="sxs-lookup"><span data-stu-id="564de-273">Subset of files under */Library/Managed Preferences* that are used by Microsoft Defender for Endpoint on macOS</span></span>
- <span data-ttu-id="564de-274">/Library/Logs/Microsoft/autoupdate.log</span><span class="sxs-lookup"><span data-stu-id="564de-274">/Library/Logs/Microsoft/autoupdate.log</span></span>
- <span data-ttu-id="564de-275">$HOME/Library/Preferences/com.microsoft.autoupdate2.plist</span><span class="sxs-lookup"><span data-stu-id="564de-275">$HOME/Library/Preferences/com.microsoft.autoupdate2.plist</span></span>

### <a name="optional-diagnostic-data"></a><span data-ttu-id="564de-276">선택적 진단 데이터</span><span class="sxs-lookup"><span data-stu-id="564de-276">Optional diagnostic data</span></span>

<span data-ttu-id="564de-277">**선택적 진단 데이터는** Microsoft가 제품을 개선하는 데 도움이 되는 추가 데이터이며 문제를 감지, 진단 및 해결하는 데 도움이 되는 향상된 정보를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="564de-277">**Optional diagnostic data** is additional data that helps Microsoft make product improvements and provides enhanced information to help detect, diagnose, and fix issues.</span></span>

<span data-ttu-id="564de-278">선택 사항 진단 데이터를 보내시는 경우 필수 진단 데이터도 함께 보내야 합니다.</span><span class="sxs-lookup"><span data-stu-id="564de-278">If you choose to send us optional diagnostic data, required diagnostic data is also included.</span></span>

<span data-ttu-id="564de-279">선택적 진단 데이터의 예로는 Microsoft가 제품 구성(예: 장치에 설정된 제외 수) 및 제품 성능(제품의 구성 요소 성능에 대한 집계 측정값)에 대해 수집하는 데이터가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="564de-279">Examples of optional diagnostic data include data Microsoft collects about product configuration (for example number of exclusions set on the device) and product performance (aggregate measures about the performance of components of the product).</span></span>

#### <a name="software-setup-and-inventory-data-events"></a><span data-ttu-id="564de-280">소프트웨어 설치 및 인벤토리 데이터 이벤트</span><span class="sxs-lookup"><span data-stu-id="564de-280">Software setup and inventory data events</span></span>

<span data-ttu-id="564de-281">**끝점용 Microsoft Defender 구성**</span><span class="sxs-lookup"><span data-stu-id="564de-281">**Microsoft Defender for Endpoint configuration**</span></span>

<span data-ttu-id="564de-282">다음 필드가 수집됩니다.</span><span class="sxs-lookup"><span data-stu-id="564de-282">The following fields are collected:</span></span>

| <span data-ttu-id="564de-283">필드</span><span class="sxs-lookup"><span data-stu-id="564de-283">Field</span></span>                                              | <span data-ttu-id="564de-284">설명</span><span class="sxs-lookup"><span data-stu-id="564de-284">Description</span></span> |
| -------------------------------------------------- | ----------- |
| <span data-ttu-id="564de-285">connection_retry_timeout</span><span class="sxs-lookup"><span data-stu-id="564de-285">connection_retry_timeout</span></span>                           | <span data-ttu-id="564de-286">클라우드와 통신할 때 연결 다시 시도 시간입니다.</span><span class="sxs-lookup"><span data-stu-id="564de-286">Connection retry time out when communication with the cloud.</span></span> |
| <span data-ttu-id="564de-287">file_hash_cache_maximum</span><span class="sxs-lookup"><span data-stu-id="564de-287">file_hash_cache_maximum</span></span>                            | <span data-ttu-id="564de-288">제품 캐시의 크기입니다.</span><span class="sxs-lookup"><span data-stu-id="564de-288">Size of the product cache.</span></span> |
| <span data-ttu-id="564de-289">crash_upload_daily_limit</span><span class="sxs-lookup"><span data-stu-id="564de-289">crash_upload_daily_limit</span></span>                           | <span data-ttu-id="564de-290">매일 업로드된 크래시 로그 제한.</span><span class="sxs-lookup"><span data-stu-id="564de-290">Limit of crash logs uploaded daily.</span></span> |
| <span data-ttu-id="564de-291">antivirus_engine.exclusions[].is_directory</span><span class="sxs-lookup"><span data-stu-id="564de-291">antivirus_engine.exclusions[].is_directory</span></span>         | <span data-ttu-id="564de-292">검사 제외가 디렉터리인지 여부입니다.</span><span class="sxs-lookup"><span data-stu-id="564de-292">Whether the exclusion from scanning is a directory or not.</span></span> |
| <span data-ttu-id="564de-293">antivirus_engine.exclusions[].path</span><span class="sxs-lookup"><span data-stu-id="564de-293">antivirus_engine.exclusions[].path</span></span>                 | <span data-ttu-id="564de-294">검사에서 제외된 경로입니다.</span><span class="sxs-lookup"><span data-stu-id="564de-294">Path that was excluded from scanning.</span></span> |
| <span data-ttu-id="564de-295">antivirus_engine.exclusions[].extension</span><span class="sxs-lookup"><span data-stu-id="564de-295">antivirus_engine.exclusions[].extension</span></span>            | <span data-ttu-id="564de-296">검색에서 제외된 확장명입니다.</span><span class="sxs-lookup"><span data-stu-id="564de-296">Extension excluded from scanning.</span></span> |
| <span data-ttu-id="564de-297">antivirus_engine.exclusions[].name</span><span class="sxs-lookup"><span data-stu-id="564de-297">antivirus_engine.exclusions[].name</span></span>                 | <span data-ttu-id="564de-298">검사에서 제외된 파일의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="564de-298">Name of the file excluded from scanning.</span></span> |
| <span data-ttu-id="564de-299">antivirus_engine.scan_cache_maximum</span><span class="sxs-lookup"><span data-stu-id="564de-299">antivirus_engine.scan_cache_maximum</span></span>                | <span data-ttu-id="564de-300">제품 캐시의 크기입니다.</span><span class="sxs-lookup"><span data-stu-id="564de-300">Size of the product cache.</span></span> |
| <span data-ttu-id="564de-301">antivirus_engine.maximum_scan_threads</span><span class="sxs-lookup"><span data-stu-id="564de-301">antivirus_engine.maximum_scan_threads</span></span>              | <span data-ttu-id="564de-302">검색에 사용되는 최대 스레드 수입니다.</span><span class="sxs-lookup"><span data-stu-id="564de-302">Maximum number of threads used for scanning.</span></span> |
| <span data-ttu-id="564de-303">antivirus_engine.threat_restoration_exclusion_time</span><span class="sxs-lookup"><span data-stu-id="564de-303">antivirus_engine.threat_restoration_exclusion_time</span></span> | <span data-ttu-id="564de-304">파일에서 복원된 파일을 다시 검색하기 전의 시간입니다.</span><span class="sxs-lookup"><span data-stu-id="564de-304">Time out before a file restored from the quarantine can be detected again.</span></span> |
| <span data-ttu-id="564de-305">antivirus_engine.threat_type_settings</span><span class="sxs-lookup"><span data-stu-id="564de-305">antivirus_engine.threat_type_settings</span></span>              | <span data-ttu-id="564de-306">제품에서 다양한 위협 유형을 처리하는 방법에 대한 구성입니다.</span><span class="sxs-lookup"><span data-stu-id="564de-306">Configuration for how different threat types are handled by the product.</span></span> |
| <span data-ttu-id="564de-307">filesystem_scanner.full_scan_directory</span><span class="sxs-lookup"><span data-stu-id="564de-307">filesystem_scanner.full_scan_directory</span></span>             | <span data-ttu-id="564de-308">전체 검사 디렉터리.</span><span class="sxs-lookup"><span data-stu-id="564de-308">Full scan directory.</span></span> |
| <span data-ttu-id="564de-309">filesystem_scanner.quick_scan_directories</span><span class="sxs-lookup"><span data-stu-id="564de-309">filesystem_scanner.quick_scan_directories</span></span>          | <span data-ttu-id="564de-310">빠른 검사에 사용되는렉터리 목록입니다.</span><span class="sxs-lookup"><span data-stu-id="564de-310">List of directories used in quick scan.</span></span> |
| <span data-ttu-id="564de-311">edr.latency_mode</span><span class="sxs-lookup"><span data-stu-id="564de-311">edr.latency_mode</span></span>                                   | <span data-ttu-id="564de-312">검색 및 응답 구성 요소에서 사용되는 대기 시간 모드입니다.</span><span class="sxs-lookup"><span data-stu-id="564de-312">Latency mode used by the detection and response component.</span></span> |
| <span data-ttu-id="564de-313">edr.proxy_address</span><span class="sxs-lookup"><span data-stu-id="564de-313">edr.proxy_address</span></span>                                  | <span data-ttu-id="564de-314">검색 및 응답 구성 요소에서 사용하는 프록시 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="564de-314">Proxy address used by the detection and response component.</span></span> |

<span data-ttu-id="564de-315">**Microsoft 자동 업데이트 구성**</span><span class="sxs-lookup"><span data-stu-id="564de-315">**Microsoft Auto-Update configuration**</span></span>

<span data-ttu-id="564de-316">다음 필드가 수집됩니다.</span><span class="sxs-lookup"><span data-stu-id="564de-316">The following fields are collected:</span></span>

| <span data-ttu-id="564de-317">필드</span><span class="sxs-lookup"><span data-stu-id="564de-317">Field</span></span>                       | <span data-ttu-id="564de-318">설명</span><span class="sxs-lookup"><span data-stu-id="564de-318">Description</span></span> |
| --------------------------- | ----------- |
| <span data-ttu-id="564de-319">how_to_check</span><span class="sxs-lookup"><span data-stu-id="564de-319">how_to_check</span></span>                | <span data-ttu-id="564de-320">자동 또는 수동과 같은 제품 업데이트를 확인하는 방법을 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="564de-320">Determines how product updates are checked (for example automatic or manual).</span></span> |
| <span data-ttu-id="564de-321">channel_name</span><span class="sxs-lookup"><span data-stu-id="564de-321">channel_name</span></span>                | <span data-ttu-id="564de-322">장치와 연결된 채널을 업데이트합니다.</span><span class="sxs-lookup"><span data-stu-id="564de-322">Update channel associated with the device.</span></span> |
| <span data-ttu-id="564de-323">manifest_server</span><span class="sxs-lookup"><span data-stu-id="564de-323">manifest_server</span></span>             | <span data-ttu-id="564de-324">업데이트를 다운로드하는 데 사용되는 서버입니다.</span><span class="sxs-lookup"><span data-stu-id="564de-324">Server used for downloading updates.</span></span> |
| <span data-ttu-id="564de-325">update_cache</span><span class="sxs-lookup"><span data-stu-id="564de-325">update_cache</span></span>                | <span data-ttu-id="564de-326">업데이트를 저장하는 데 사용되는 캐시 위치입니다.</span><span class="sxs-lookup"><span data-stu-id="564de-326">Location of the cache used to store updates.</span></span> |

### <a name="product-and-service-usage"></a><span data-ttu-id="564de-327">제품 및 서비스 사용</span><span class="sxs-lookup"><span data-stu-id="564de-327">Product and service usage</span></span>

#### <a name="diagnostic-log-upload-started-report"></a><span data-ttu-id="564de-328">진단 로그 업로드 시작 보고서</span><span class="sxs-lookup"><span data-stu-id="564de-328">Diagnostic log upload started report</span></span>

<span data-ttu-id="564de-329">다음 필드가 수집됩니다.</span><span class="sxs-lookup"><span data-stu-id="564de-329">The following fields are collected:</span></span>

| <span data-ttu-id="564de-330">필드</span><span class="sxs-lookup"><span data-stu-id="564de-330">Field</span></span>            | <span data-ttu-id="564de-331">설명</span><span class="sxs-lookup"><span data-stu-id="564de-331">Description</span></span> |
| ---------------- | ----------- |
| <span data-ttu-id="564de-332">sha256</span><span class="sxs-lookup"><span data-stu-id="564de-332">sha256</span></span>           | <span data-ttu-id="564de-333">지원 로그의 SHA256 식별자입니다.</span><span class="sxs-lookup"><span data-stu-id="564de-333">SHA256 identifier of the support log.</span></span> |
| <span data-ttu-id="564de-334">size</span><span class="sxs-lookup"><span data-stu-id="564de-334">size</span></span>             | <span data-ttu-id="564de-335">지원 로그의 크기입니다.</span><span class="sxs-lookup"><span data-stu-id="564de-335">Size of the support log.</span></span> |
| <span data-ttu-id="564de-336">original_path</span><span class="sxs-lookup"><span data-stu-id="564de-336">original_path</span></span>    | <span data-ttu-id="564de-337">지원 로그 경로(항상 */Library/Application Support/Microsoft/Defender/wdavdiag/* 아래)</span><span class="sxs-lookup"><span data-stu-id="564de-337">Path to the support log (always under */Library/Application Support/Microsoft/Defender/wdavdiag/*).</span></span> |
| <span data-ttu-id="564de-338">형식</span><span class="sxs-lookup"><span data-stu-id="564de-338">format</span></span>           | <span data-ttu-id="564de-339">지원 로그의 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="564de-339">Format of the support log.</span></span> |

#### <a name="diagnostic-log-upload-completed-report"></a><span data-ttu-id="564de-340">진단 로그 업로드 완료된 보고서</span><span class="sxs-lookup"><span data-stu-id="564de-340">Diagnostic log upload completed report</span></span>

<span data-ttu-id="564de-341">다음 필드가 수집됩니다.</span><span class="sxs-lookup"><span data-stu-id="564de-341">The following fields are collected:</span></span>

| <span data-ttu-id="564de-342">필드</span><span class="sxs-lookup"><span data-stu-id="564de-342">Field</span></span>            | <span data-ttu-id="564de-343">설명</span><span class="sxs-lookup"><span data-stu-id="564de-343">Description</span></span> |
| ---------------- | ----------- |
| <span data-ttu-id="564de-344">request_id</span><span class="sxs-lookup"><span data-stu-id="564de-344">request_id</span></span>       | <span data-ttu-id="564de-345">지원 로그 업로드 요청의 상관 관계 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="564de-345">Correlation ID for the support log upload request.</span></span> |
| <span data-ttu-id="564de-346">sha256</span><span class="sxs-lookup"><span data-stu-id="564de-346">sha256</span></span>           | <span data-ttu-id="564de-347">지원 로그의 SHA256 식별자입니다.</span><span class="sxs-lookup"><span data-stu-id="564de-347">SHA256 identifier of the support log.</span></span> |
| <span data-ttu-id="564de-348">blob_sas_uri</span><span class="sxs-lookup"><span data-stu-id="564de-348">blob_sas_uri</span></span>     | <span data-ttu-id="564de-349">응용 프로그램에서 지원 로그를 업로드하는 데 사용하는 URI입니다.</span><span class="sxs-lookup"><span data-stu-id="564de-349">URI used by the application to upload the support log.</span></span> |

#### <a name="product-and-service-performance-data-events"></a><span data-ttu-id="564de-350">제품 및 서비스 성능 데이터 이벤트</span><span class="sxs-lookup"><span data-stu-id="564de-350">Product and service performance data events</span></span>

<span data-ttu-id="564de-351">**예기치 않은 응용 프로그램 종료(크래시)**</span><span class="sxs-lookup"><span data-stu-id="564de-351">**Unexpected application exit (crash)**</span></span>

<span data-ttu-id="564de-352">예기치 않은 응용 프로그램 종료 및 종료 시의 응용 프로그램 상태입니다.</span><span class="sxs-lookup"><span data-stu-id="564de-352">Unexpected application exits and the state of the application when that happens.</span></span>

<span data-ttu-id="564de-353">**커널 확장 통계**</span><span class="sxs-lookup"><span data-stu-id="564de-353">**Kernel extension statistics**</span></span>

<span data-ttu-id="564de-354">다음 필드가 수집됩니다.</span><span class="sxs-lookup"><span data-stu-id="564de-354">The following fields are collected:</span></span>

| <span data-ttu-id="564de-355">필드</span><span class="sxs-lookup"><span data-stu-id="564de-355">Field</span></span>                          | <span data-ttu-id="564de-356">설명</span><span class="sxs-lookup"><span data-stu-id="564de-356">Description</span></span> |
| ------------------------------ | ----------- |
| <span data-ttu-id="564de-357">pkt_ack_timeout</span><span class="sxs-lookup"><span data-stu-id="564de-357">pkt_ack_timeout</span></span>                | <span data-ttu-id="564de-358">다음 속성은 커널 확장 시작 이후 발생된 이벤트 수를 나타내는 집계된 숫자 값입니다.</span><span class="sxs-lookup"><span data-stu-id="564de-358">The following properties are aggregated numerical values, representing count of events that happened since kernel extension startup.</span></span> |
| <span data-ttu-id="564de-359">pkt_ack_conn_timeout</span><span class="sxs-lookup"><span data-stu-id="564de-359">pkt_ack_conn_timeout</span></span>             | |
| <span data-ttu-id="564de-360">ipc.ack_pkts</span><span class="sxs-lookup"><span data-stu-id="564de-360">ipc.ack_pkts</span></span>                     | |
| <span data-ttu-id="564de-361">ipc.nack_pkts</span><span class="sxs-lookup"><span data-stu-id="564de-361">ipc.nack_pkts</span></span>                    | |
| <span data-ttu-id="564de-362">ipc.send.ack_no_conn</span><span class="sxs-lookup"><span data-stu-id="564de-362">ipc.send.ack_no_conn</span></span>             | |
| <span data-ttu-id="564de-363">ipc.send.nack_no_conn</span><span class="sxs-lookup"><span data-stu-id="564de-363">ipc.send.nack_no_conn</span></span>            | |
| <span data-ttu-id="564de-364">ipc.send.ack_no_qsq</span><span class="sxs-lookup"><span data-stu-id="564de-364">ipc.send.ack_no_qsq</span></span>              | |
| <span data-ttu-id="564de-365">ipc.send.nack_no_qsq</span><span class="sxs-lookup"><span data-stu-id="564de-365">ipc.send.nack_no_qsq</span></span>             | |
| <span data-ttu-id="564de-366">ipc.ack.no_space</span><span class="sxs-lookup"><span data-stu-id="564de-366">ipc.ack.no_space</span></span>                 | |
| <span data-ttu-id="564de-367">ipc.ack.timeout</span><span class="sxs-lookup"><span data-stu-id="564de-367">ipc.ack.timeout</span></span>                  | |
| <span data-ttu-id="564de-368">ipc.ack.ackd_fast</span><span class="sxs-lookup"><span data-stu-id="564de-368">ipc.ack.ackd_fast</span></span>                | |
| <span data-ttu-id="564de-369">ipc.ack.ackd</span><span class="sxs-lookup"><span data-stu-id="564de-369">ipc.ack.ackd</span></span>                     | |
| <span data-ttu-id="564de-370">ipc.recv.bad_pkt_len</span><span class="sxs-lookup"><span data-stu-id="564de-370">ipc.recv.bad_pkt_len</span></span>             | |
| <span data-ttu-id="564de-371">ipc.recv.bad_reply_len</span><span class="sxs-lookup"><span data-stu-id="564de-371">ipc.recv.bad_reply_len</span></span>           | |
| <span data-ttu-id="564de-372">ipc.recv.no_waiter</span><span class="sxs-lookup"><span data-stu-id="564de-372">ipc.recv.no_waiter</span></span>               | |
| <span data-ttu-id="564de-373">ipc.recv.copy_failed</span><span class="sxs-lookup"><span data-stu-id="564de-373">ipc.recv.copy_failed</span></span>             | |
| <span data-ttu-id="564de-374">ipc.kauth.vnode.mask</span><span class="sxs-lookup"><span data-stu-id="564de-374">ipc.kauth.vnode.mask</span></span>             | |
| <span data-ttu-id="564de-375">ipc.kauth.vnode.read</span><span class="sxs-lookup"><span data-stu-id="564de-375">ipc.kauth.vnode.read</span></span>             | |
| <span data-ttu-id="564de-376">ipc.kauth.vnode.write</span><span class="sxs-lookup"><span data-stu-id="564de-376">ipc.kauth.vnode.write</span></span>            | |
| <span data-ttu-id="564de-377">ipc.kauth.vnode.exec</span><span class="sxs-lookup"><span data-stu-id="564de-377">ipc.kauth.vnode.exec</span></span>             | |
| <span data-ttu-id="564de-378">ipc.kauth.vnode.del</span><span class="sxs-lookup"><span data-stu-id="564de-378">ipc.kauth.vnode.del</span></span>              | |
| <span data-ttu-id="564de-379">ipc.kauth.vnode.read_attr</span><span class="sxs-lookup"><span data-stu-id="564de-379">ipc.kauth.vnode.read_attr</span></span>        | |
| <span data-ttu-id="564de-380">ipc.kauth.vnode.write_attr</span><span class="sxs-lookup"><span data-stu-id="564de-380">ipc.kauth.vnode.write_attr</span></span>       | |
| <span data-ttu-id="564de-381">ipc.kauth.vnode.read_ex_attr</span><span class="sxs-lookup"><span data-stu-id="564de-381">ipc.kauth.vnode.read_ex_attr</span></span>     | |
| <span data-ttu-id="564de-382">ipc.kauth.vnode.write_ex_attr</span><span class="sxs-lookup"><span data-stu-id="564de-382">ipc.kauth.vnode.write_ex_attr</span></span>    | |
| <span data-ttu-id="564de-383">ipc.kauth.vnode.read_sec</span><span class="sxs-lookup"><span data-stu-id="564de-383">ipc.kauth.vnode.read_sec</span></span>         | |
| <span data-ttu-id="564de-384">ipc.kauth.vnode.write_sec</span><span class="sxs-lookup"><span data-stu-id="564de-384">ipc.kauth.vnode.write_sec</span></span>        | |
| <span data-ttu-id="564de-385">ipc.kauth.vnode.take_own</span><span class="sxs-lookup"><span data-stu-id="564de-385">ipc.kauth.vnode.take_own</span></span>         | |
| <span data-ttu-id="564de-386">ipc.kauth.vnode.link</span><span class="sxs-lookup"><span data-stu-id="564de-386">ipc.kauth.vnode.link</span></span>             | |
| <span data-ttu-id="564de-387">ipc.kauth.vnode.create</span><span class="sxs-lookup"><span data-stu-id="564de-387">ipc.kauth.vnode.create</span></span>           | |
| <span data-ttu-id="564de-388">ipc.kauth.vnode.move</span><span class="sxs-lookup"><span data-stu-id="564de-388">ipc.kauth.vnode.move</span></span>             | |
| <span data-ttu-id="564de-389">ipc.kauth.vnode.mount</span><span class="sxs-lookup"><span data-stu-id="564de-389">ipc.kauth.vnode.mount</span></span>            | |
| <span data-ttu-id="564de-390">ipc.kauth.vnode.denied</span><span class="sxs-lookup"><span data-stu-id="564de-390">ipc.kauth.vnode.denied</span></span>           | |
| <span data-ttu-id="564de-391">ipc.kauth.vnode.ackd_before_deadline</span><span class="sxs-lookup"><span data-stu-id="564de-391">ipc.kauth.vnode.ackd_before_deadline</span></span> | |
| <span data-ttu-id="564de-392">ipc.kauth.vnode.missed_deadline</span><span class="sxs-lookup"><span data-stu-id="564de-392">ipc.kauth.vnode.missed_deadline</span></span>  | |
| <span data-ttu-id="564de-393">ipc.kauth.file_op.mask</span><span class="sxs-lookup"><span data-stu-id="564de-393">ipc.kauth.file_op.mask</span></span>           | |
| <span data-ttu-id="564de-394">ipc.kauth_file_op.open</span><span class="sxs-lookup"><span data-stu-id="564de-394">ipc.kauth_file_op.open</span></span>           | |
| <span data-ttu-id="564de-395">ipc.kauth.file_op.close</span><span class="sxs-lookup"><span data-stu-id="564de-395">ipc.kauth.file_op.close</span></span>          | |
| <span data-ttu-id="564de-396">ipc.kauth.file_op.close_modified</span><span class="sxs-lookup"><span data-stu-id="564de-396">ipc.kauth.file_op.close_modified</span></span> | |
| <span data-ttu-id="564de-397">ipc.kauth.file_op.move</span><span class="sxs-lookup"><span data-stu-id="564de-397">ipc.kauth.file_op.move</span></span>           | |
| <span data-ttu-id="564de-398">ipc.kauth.file_op.link</span><span class="sxs-lookup"><span data-stu-id="564de-398">ipc.kauth.file_op.link</span></span>           | |
| <span data-ttu-id="564de-399">ipc.kauth.file_op.exec</span><span class="sxs-lookup"><span data-stu-id="564de-399">ipc.kauth.file_op.exec</span></span>           | |
| <span data-ttu-id="564de-400">ipc.kauth.file_op.remove</span><span class="sxs-lookup"><span data-stu-id="564de-400">ipc.kauth.file_op.remove</span></span>         | |
| <span data-ttu-id="564de-401">ipc.kauth.file_op.unmount</span><span class="sxs-lookup"><span data-stu-id="564de-401">ipc.kauth.file_op.unmount</span></span>        | |
| <span data-ttu-id="564de-402">ipc.kauth.file_op.fork</span><span class="sxs-lookup"><span data-stu-id="564de-402">ipc.kauth.file_op.fork</span></span>           | |
| <span data-ttu-id="564de-403">ipc.kauth.file_op.create</span><span class="sxs-lookup"><span data-stu-id="564de-403">ipc.kauth.file_op.create</span></span>         | |

## <a name="resources"></a><span data-ttu-id="564de-404">리소스</span><span class="sxs-lookup"><span data-stu-id="564de-404">Resources</span></span>

- [<span data-ttu-id="564de-405">Microsoft 개인 정보</span><span class="sxs-lookup"><span data-stu-id="564de-405">Privacy at Microsoft</span></span>](https://privacy.microsoft.com/)
