---
title: Android용 Microsoft Defender ATP - 개인 정보
description: 개인 정보 제어, Android용 Microsoft Defender ATP에서 수집된 진단 데이터에 대한 개인 정보 및 정보에 영향을 미치는 정책 설정을 구성하는 방법입니다.
keywords: Microsoft, defender, atp, android, 개인 정보, 진단
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
ms.openlocfilehash: 79f8882e21f23e75d85813cde03260ef17adf246
ms.sourcegitcommit: 2655bb0ccd66279c35be2fadbd893c937d084109
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/16/2021
ms.locfileid: "51876112"
---
#  <a name="microsoft-defender-for-endpoint-on-android---privacy-information"></a><span data-ttu-id="38c89-104">Microsoft Defender for Endpoint(Android용) - 개인 정보</span><span class="sxs-lookup"><span data-stu-id="38c89-104">Microsoft Defender for Endpoint on Android - Privacy information</span></span>

<span data-ttu-id="38c89-105">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="38c89-105">**Applies to:**</span></span>
- [<span data-ttu-id="38c89-106">엔드포인트용 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="38c89-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="38c89-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="38c89-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="38c89-108">끝점용 Microsoft Defender를 경험하고 싶나요?</span><span class="sxs-lookup"><span data-stu-id="38c89-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="38c89-109">무료 평가판에 등록합니다.</span><span class="sxs-lookup"><span data-stu-id="38c89-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 


<span data-ttu-id="38c89-110">Android용 Endpoint용 Defender는 구성된 Android 장치에서 정보를 수집하고 Endpoint용 Defender가 있는 동일한 테넌트에 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="38c89-110">Defender for Endpoint for Android collects information from your configured Android devices and stores it in the same tenant where you have Defender for Endpoint.</span></span> <span data-ttu-id="38c89-111">이 정보는 iOS용 Endpoint용 Defender를 안전하고 최신으로 유지하며 예상대로 수행하고 서비스를 지원하기 위해 수집됩니다.</span><span class="sxs-lookup"><span data-stu-id="38c89-111">The information is collected to help keep Defender for Endpoint for iOS secure, up-to-date, performing as expected, and to support the service.</span></span>

<span data-ttu-id="38c89-112">데이터 저장소에 대한 자세한 내용은 끝점 데이터 저장소 및 개인 정보 보호를 위한 [Microsoft Defender를 참조하세요.](data-storage-privacy.md)</span><span class="sxs-lookup"><span data-stu-id="38c89-112">For more information about data storage, see [Microsoft Defender for Endpoint data storage and privacy](data-storage-privacy.md).</span></span>

<span data-ttu-id="38c89-113">Android용 Endpoint용 Defender를 예상대로 안전하게 최신으로 유지하고 서비스를 지원하기 위해 수집된 정보입니다.</span><span class="sxs-lookup"><span data-stu-id="38c89-113">Information is collected to help keep Defender for Endpoint for Android secure, up-to-date, performing as expected and to support the service.</span></span>

## <a name="required-data"></a><span data-ttu-id="38c89-114">필수 데이터</span><span class="sxs-lookup"><span data-stu-id="38c89-114">Required Data</span></span> 

<span data-ttu-id="38c89-115">필수 데이터는 Android용 Endpoint용 Defender가 예상대로 작동하게 하는 데 필요한 데이터로 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="38c89-115">Required data consists of data that is necessary to make Defender for Endpoint for Android work as expected.</span></span> <span data-ttu-id="38c89-116">이 데이터는 서비스 운영에 필수적으로 사용하며 최종 사용자, 조직, 장치 및 앱과 관련된 데이터를 포함할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="38c89-116">This data is essential to the operation of the service and can include data related to the end user, organization, device, and apps.</span></span> <span data-ttu-id="38c89-117">수집되는 데이터의 유형 목록은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="38c89-117">Here's a list of the types of data being collected:</span></span>

### <a name="app-information"></a><span data-ttu-id="38c89-118">앱 정보</span><span class="sxs-lookup"><span data-stu-id="38c89-118">App information</span></span>

<span data-ttu-id="38c89-119">디바이스의  악성 Android 응용 프로그램 패키지(APK)에 대한 정보 포함</span><span class="sxs-lookup"><span data-stu-id="38c89-119">Information about **malicious** Android application packages (APKs) on the device including</span></span>

-  <span data-ttu-id="38c89-120">원본 설치</span><span class="sxs-lookup"><span data-stu-id="38c89-120">Install source</span></span>
-  <span data-ttu-id="38c89-121">APK의 저장소 위치(파일 경로)</span><span class="sxs-lookup"><span data-stu-id="38c89-121">Storage location (file path) of the APK</span></span>
-  <span data-ttu-id="38c89-122">설치 시간, APK 크기 및 사용 권한</span><span class="sxs-lookup"><span data-stu-id="38c89-122">Time of install, size of APK and permissions</span></span>

### <a name="web-page--network-information"></a><span data-ttu-id="38c89-123">웹 페이지/네트워크 정보</span><span class="sxs-lookup"><span data-stu-id="38c89-123">Web page / Network information</span></span>

- <span data-ttu-id="38c89-124">악의적인 연결 또는 웹 페이지가 검색된 웹 사이트의 전체 URL입니다.</span><span class="sxs-lookup"><span data-stu-id="38c89-124">Full URL of the website only when a malicious connection or web page is detected.</span></span>
- <span data-ttu-id="38c89-125">연결 정보</span><span class="sxs-lookup"><span data-stu-id="38c89-125">Connection information</span></span>
- <span data-ttu-id="38c89-126">프로토콜 유형(예: HTTP, HTTPS 등)</span><span class="sxs-lookup"><span data-stu-id="38c89-126">Protocol type (such as HTTP, HTTPS, etc.)</span></span>


### <a name="device-and-account-information"></a><span data-ttu-id="38c89-127">장치 및 계정 정보</span><span class="sxs-lookup"><span data-stu-id="38c89-127">Device and account information</span></span>

- <span data-ttu-id="38c89-128">날짜 및 시간& Android 버전, OEM 모델, CPU 정보, 장치 식별자 등의 장치 정보</span><span class="sxs-lookup"><span data-stu-id="38c89-128">Device information such as date & time, Android version, OEM model, CPU       info, and Device identifier</span></span>
- <span data-ttu-id="38c89-129">장치 식별자는 다음 중 하나입니다.</span><span class="sxs-lookup"><span data-stu-id="38c89-129">Device identifier is one of the below:</span></span>
    - <span data-ttu-id="38c89-130">Wi-Fi 어댑터 MAC 주소</span><span class="sxs-lookup"><span data-stu-id="38c89-130">Wi-Fi adapter MAC address</span></span>
    - <span data-ttu-id="38c89-131">[Android](https://developer.android.com/reference/android/provider/Settings.Secure#ANDROID_ID) ID(디바이스를 처음 부팅할 때 Android에서 생성)</span><span class="sxs-lookup"><span data-stu-id="38c89-131">[Android       ID](https://developer.android.com/reference/android/provider/Settings.Secure#ANDROID_ID) (as generated by Android at the time of first boot of the device)</span></span>
    - <span data-ttu-id="38c89-132">임의로 생성된 GUID(Globally Unique Identifier)</span><span class="sxs-lookup"><span data-stu-id="38c89-132">Randomly generated globally unique identifier (GUID)</span></span>

- <span data-ttu-id="38c89-133">테넌트, 장치 및 사용자 정보</span><span class="sxs-lookup"><span data-stu-id="38c89-133">Tenant, Device and User information</span></span>
    -   <span data-ttu-id="38c89-134">Azure AD(Active Directory) 장치 ID 및 Azure 사용자 ID: Azure Active Directory에서 각각 장치를 고유하게 식별합니다.</span><span class="sxs-lookup"><span data-stu-id="38c89-134">Azure Active Directory (AD) Device ID and Azure User ID: Uniquely     identifies the device, User respectively at Azure Active directory.</span></span>

    -   <span data-ttu-id="38c89-135">Azure 테넌트 ID - Azure Active Directory 내에서 조직을 식별하는 GUID</span><span class="sxs-lookup"><span data-stu-id="38c89-135">Azure tenant ID - GUID that identifies your organization within     Azure Active Directory</span></span>

    -   <span data-ttu-id="38c89-136">Microsoft Defender ATP org ID - 장치가 속한 엔터프라이즈와 연결된 고유 식별자입니다.</span><span class="sxs-lookup"><span data-stu-id="38c89-136">Microsoft Defender ATP org ID - Unique identifier associated with the enterprise that the device belongs to.</span></span> <span data-ttu-id="38c89-137">Microsoft에서 문제가 선택한 엔터프라이즈 집합에 영향을 미치는지 여부와 영향을 미치는 엔터프라이즈 수를 식별할 수 있도록 허용</span><span class="sxs-lookup"><span data-stu-id="38c89-137">Allows Microsoft to identify whether issues are impacting a select set of enterprises and how many enterprises are impacted</span></span> 

    -   <span data-ttu-id="38c89-138">사용자 계정 이름 - 사용자의 전자 메일 ID</span><span class="sxs-lookup"><span data-stu-id="38c89-138">User Principal Name – Email ID of the user</span></span>

### <a name="product-and-service-usage-data"></a><span data-ttu-id="38c89-139">제품 및 서비스 사용 현황 데이터</span><span class="sxs-lookup"><span data-stu-id="38c89-139">Product and service usage data</span></span>

<span data-ttu-id="38c89-140">다음 정보는 장치에 설치된 끝점용 Microsoft Defender 앱에만 수집됩니다.</span><span class="sxs-lookup"><span data-stu-id="38c89-140">The following information is collected only for Microsoft Defender for Endpoint app installed on the device.</span></span> 

-   <span data-ttu-id="38c89-141">이름, 버전 및 앱 업그레이드 상태를 포함한 앱 패키지 정보</span><span class="sxs-lookup"><span data-stu-id="38c89-141">App package info, including name, version, and app upgrade status</span></span>

-   <span data-ttu-id="38c89-142">앱에서 수행되는 작업</span><span class="sxs-lookup"><span data-stu-id="38c89-142">Actions performed in the app</span></span>

-   <span data-ttu-id="38c89-143">위협 감지 정보(예: 위협 이름, 범주 등)</span><span class="sxs-lookup"><span data-stu-id="38c89-143">Threat detection information, such as threat name, category, etc.</span></span>

-   <span data-ttu-id="38c89-144">Android에서 생성된 크래시 보고서 로그</span><span class="sxs-lookup"><span data-stu-id="38c89-144">Crash report logs generated by Android</span></span>

## <a name="optional-data"></a><span data-ttu-id="38c89-145">선택적 데이터</span><span class="sxs-lookup"><span data-stu-id="38c89-145">Optional Data</span></span>

<span data-ttu-id="38c89-146">선택적 데이터에는 진단 데이터 및 피드백 데이터가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="38c89-146">Optional data includes diagnostic data and feedback data.</span></span> <span data-ttu-id="38c89-147">선택적 진단 데이터는 제품을 개선하고 향상된 정보를 제공하여 문제를 감지, 진단, 해결하는 데 도움이 되는 추가 데이터입니다.</span><span class="sxs-lookup"><span data-stu-id="38c89-147">Optional diagnostic data is additional data that helps us make product improvements and provides enhanced information to help us detect, diagnose, and fix issues.</span></span> <span data-ttu-id="38c89-148">선택적 진단 데이터에는 다음이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="38c89-148">Optional diagnostic data includes:</span></span>

-   <span data-ttu-id="38c89-149">앱, CPU 및 네트워크 사용</span><span class="sxs-lookup"><span data-stu-id="38c89-149">App, CPU, and network usage</span></span>

-   <span data-ttu-id="38c89-150">검사 상태, 검사 시간, 부여된 앱 권한 및 업그레이드 상태를 포함하여 앱 관점에서 디바이스의 상태</span><span class="sxs-lookup"><span data-stu-id="38c89-150">State of the device from the app perspective, including scan status, scan timings, app permissions granted, and upgrade status</span></span>

-   <span data-ttu-id="38c89-151">관리자가 구성한 기능</span><span class="sxs-lookup"><span data-stu-id="38c89-151">Features configured by the admin</span></span>

-   <span data-ttu-id="38c89-152">장치의 브라우저에 대한 기본 정보</span><span class="sxs-lookup"><span data-stu-id="38c89-152">Basic information about the browsers on the device</span></span>

<span data-ttu-id="38c89-153">**피드백 데이터는** 사용자가 제공한 앱 내 피드백을 통해 수집됩니다.</span><span class="sxs-lookup"><span data-stu-id="38c89-153">**Feedback Data** is collected through in-app feedback provided by the user</span></span>

-   <span data-ttu-id="38c89-154">사용자의 전자 메일 주소(제공하도록 선택한 경우)</span><span class="sxs-lookup"><span data-stu-id="38c89-154">The user’s email address, if they choose to provide it</span></span>

-   <span data-ttu-id="38c89-155">피드백 유형(스마일, 희미한, 아이디어) 및 사용자가 제출한 피드백 설명</span><span class="sxs-lookup"><span data-stu-id="38c89-155">Feedback type (smile, frown, idea) and any feedback comments submitted by the user</span></span>
