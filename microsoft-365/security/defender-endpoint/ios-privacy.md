---
title: 개인 정보 보호 정보 - iOS의 끝점용 Microsoft Defender
ms.reviewer: ''
description: iOS의 끝점용 Microsoft Defender에 대한 개인 정보 보호 정보 설명
keywords: Microsoft, defender, Endpoint용 Microsoft Defender, ios, 정책, 개요
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
ms.collection:
- m365-security-compliance
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: b1d64ceb7b0027546e84a9c42c8d2ffed188c03b
ms.sourcegitcommit: 5377b00703b6f559092afe44fb61462e97968a60
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/27/2021
ms.locfileid: "52694476"
---
# <a name="privacy-information---microsoft-defender-for-endpoint-on-ios"></a><span data-ttu-id="5bd2c-104">개인 정보 보호 정보 - iOS의 끝점용 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="5bd2c-104">Privacy information - Microsoft Defender for Endpoint on iOS</span></span>

<span data-ttu-id="5bd2c-105">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="5bd2c-105">**Applies to:**</span></span>
- [<span data-ttu-id="5bd2c-106">엔드포인트용 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="5bd2c-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="5bd2c-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="5bd2c-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="5bd2c-108">Endpoint용 Defender를 경험하고 싶나요?</span><span class="sxs-lookup"><span data-stu-id="5bd2c-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="5bd2c-109">무료 평가판에 등록합니다.</span><span class="sxs-lookup"><span data-stu-id="5bd2c-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-investigateip-abovefoldlink)

> [!NOTE]
> <span data-ttu-id="5bd2c-110">iOS의 끝점용 Defender는 VPN을 사용하여 웹 보호 기능을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="5bd2c-110">Defender for Endpoint on iOS uses a VPN to provide the Web Protection feature.</span></span> <span data-ttu-id="5bd2c-111">이는 일반 VPN이 아니며 장치 외부에서 트래픽을 취하지 않는 로컬 또는 자체 루프 VPN입니다.</span><span class="sxs-lookup"><span data-stu-id="5bd2c-111">This is not a regular VPN and is a local or self-looping VPN that does not take traffic outside the device.</span></span> <span data-ttu-id="5bd2c-112">**Microsoft 또는 조직은 사용자의 검색 활동을 볼 수 없습니다.**</span><span class="sxs-lookup"><span data-stu-id="5bd2c-112">**Microsoft or your organization, does not see your browsing activity.**</span></span>

<span data-ttu-id="5bd2c-113">iOS의 Endpoint용 Defender는 구성된 iOS 장치에서 정보를 수집하고 Endpoint용 Defender가 있는 동일한 테넌트에 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="5bd2c-113">Defender for Endpoint on iOS collects information from your configured iOS devices and stores it in the same tenant where you have Defender for Endpoint.</span></span> <span data-ttu-id="5bd2c-114">이 정보는 iOS에서 끝점에 대한 Defender를 안전하고 최신으로 유지하며 예상대로 수행하고 서비스를 지원하기 위해 수집됩니다.</span><span class="sxs-lookup"><span data-stu-id="5bd2c-114">The information is collected to help keep Defender for Endpoint on iOS secure, up-to-date, performing as expected, and to support the service.</span></span>

<span data-ttu-id="5bd2c-115">데이터 저장소에 대한 자세한 내용은 끝점 데이터 저장소 및 개인 정보 보호를 위한 [Microsoft Defender를 참조하세요.](data-storage-privacy.md)</span><span class="sxs-lookup"><span data-stu-id="5bd2c-115">For more information about data storage, see [Microsoft Defender for Endpoint data storage and privacy](data-storage-privacy.md).</span></span>


<span data-ttu-id="5bd2c-116">Android 및 iOS 모바일 장치의 끝점용 Microsoft Defender에 대한 가장 일반적인 개인 정보 보호 질문에 대한 자세한 내용은 Android 및 iOS 모바일 장치에서 [끝점용 Microsoft Defender](https://support.microsoft.com/topic/microsoft-defender-for-endpoint-and-your-privacy-on-android-and-ios-mobile-devices-4109bc54-8ec5-4433-9c33-d359b75ac22a)및 개인 정보를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="5bd2c-116">For more information on most common privacy questions about Microsoft Defender for Endpoint on Android and iOS mobile devices, see [Microsoft Defender for Endpoint and your privacy on Android and iOS mobile devices](https://support.microsoft.com/topic/microsoft-defender-for-endpoint-and-your-privacy-on-android-and-ios-mobile-devices-4109bc54-8ec5-4433-9c33-d359b75ac22a).</span></span>

## <a name="required-data"></a><span data-ttu-id="5bd2c-117">필수 데이터</span><span class="sxs-lookup"><span data-stu-id="5bd2c-117">Required data</span></span> 

<span data-ttu-id="5bd2c-118">필수 데이터는 iOS의 끝점에 대한 Defender가 예상대로 작동하게 하는 데 필요한 데이터로 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="5bd2c-118">Required data consists of data that is necessary to make Defender for Endpoint on iOS work as expected.</span></span> <span data-ttu-id="5bd2c-119">이 데이터는 서비스 운영에 필수적으로 사용하며 최종 사용자, 조직, 장치 및 앱과 관련된 데이터를 포함할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5bd2c-119">This data is essential to the operation of the service and can include data related to the end user, organization, device, and apps.</span></span> 

<span data-ttu-id="5bd2c-120">수집되는 데이터 형식 목록은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="5bd2c-120">Here is a list of the types of data being collected:</span></span> 

### <a name="web-page-or-network-information"></a><span data-ttu-id="5bd2c-121">웹 페이지 또는 네트워크 정보</span><span class="sxs-lookup"><span data-stu-id="5bd2c-121">Web page or Network information</span></span> 

- <span data-ttu-id="5bd2c-122">악의적인 연결 또는 웹 페이지가 검색된 웹 사이트의 도메인 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="5bd2c-122">Domain name of the website only when a malicious connection or web page is detected.</span></span> 

### <a name="device-and-account-information"></a><span data-ttu-id="5bd2c-123">장치 및 계정 정보</span><span class="sxs-lookup"><span data-stu-id="5bd2c-123">Device and account information</span></span> 

- <span data-ttu-id="5bd2c-124">날짜 및 &, iOS 버전, CPU 정보 및 장치 식별자와 같은 장치 정보입니다. 여기서 장치 식별자는 다음 중 하나입니다.</span><span class="sxs-lookup"><span data-stu-id="5bd2c-124">Device information such as date & time, iOS version, CPU info, and Device identifier, where Device identifier is one of the following:</span></span> 

    - <span data-ttu-id="5bd2c-125">Wi-Fi 어댑터 MAC 주소</span><span class="sxs-lookup"><span data-stu-id="5bd2c-125">Wi-Fi adapter MAC address</span></span> 

    - <span data-ttu-id="5bd2c-126">임의로 생성된 GUID(Globally Unique Identifier)</span><span class="sxs-lookup"><span data-stu-id="5bd2c-126">Randomly generated globally unique identifier (GUID)</span></span> 

- <span data-ttu-id="5bd2c-127">테넌트, 장치 및 사용자 정보</span><span class="sxs-lookup"><span data-stu-id="5bd2c-127">Tenant, Device, and User information</span></span> 

    - <span data-ttu-id="5bd2c-128">Azure Active Directory(AD) 장치 ID 및 Azure 사용자 ID - Azure Active Directory에서 각각 장치를 고유하게 식별합니다.</span><span class="sxs-lookup"><span data-stu-id="5bd2c-128">Azure Active Directory (AD) Device ID and Azure User ID - Uniquely identifies the device, User respectively at Azure Active directory.</span></span> 

    - <span data-ttu-id="5bd2c-129">Azure 테넌트 ID - 조직 내에서 조직을 식별하는 Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="5bd2c-129">Azure tenant ID - GUID that identifies your organization within Azure Active Directory.</span></span> 

    - <span data-ttu-id="5bd2c-130">Microsoft Defender for Endpoint org ID - 장치가 속한 엔터프라이즈와 연결된 고유 식별자.</span><span class="sxs-lookup"><span data-stu-id="5bd2c-130">Microsoft Defender for Endpoint org ID - Unique identifier associated with the enterprise that the device belongs to.</span></span> <span data-ttu-id="5bd2c-131">Microsoft에서 선택한 엔터프라이즈 집합 및 영향을 받는 엔터프라이즈 수에 영향을 주는 문제가 있는지 식별할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5bd2c-131">Allows Microsoft to identify if there are issues affecting a select set of enterprises and the number of enterprises impacted.</span></span> 

    - <span data-ttu-id="5bd2c-132">사용자 계정 이름 - 사용자의 전자 메일 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="5bd2c-132">User Principal Name - Email ID of the user.</span></span> 

### <a name="product-and-service-usage-data"></a><span data-ttu-id="5bd2c-133">제품 및 서비스 사용 현황 데이터</span><span class="sxs-lookup"><span data-stu-id="5bd2c-133">Product and service usage data</span></span> 

<span data-ttu-id="5bd2c-134">다음 정보는 장치에 설치된 끝점용 Microsoft Defender 앱에만 수집됩니다.</span><span class="sxs-lookup"><span data-stu-id="5bd2c-134">The following information is collected only for Microsoft Defender for Endpoint app installed on the device.</span></span> 

- <span data-ttu-id="5bd2c-135">이름, 버전 및 앱 업그레이드 상태를 포함한 앱 패키지 정보입니다.</span><span class="sxs-lookup"><span data-stu-id="5bd2c-135">App package info, including name, version, and app upgrade status.</span></span> 

- <span data-ttu-id="5bd2c-136">앱에서 수행된 작업입니다.</span><span class="sxs-lookup"><span data-stu-id="5bd2c-136">Actions done in the app.</span></span> 

- <span data-ttu-id="5bd2c-137">iOS에서 생성된 크래시 보고서 로그입니다.</span><span class="sxs-lookup"><span data-stu-id="5bd2c-137">Crash report logs generated by iOS.</span></span> 

- <span data-ttu-id="5bd2c-138">메모리 사용량 데이터입니다.</span><span class="sxs-lookup"><span data-stu-id="5bd2c-138">Memory usage data.</span></span> 

## <a name="optional-data"></a><span data-ttu-id="5bd2c-139">선택적 데이터</span><span class="sxs-lookup"><span data-stu-id="5bd2c-139">Optional Data</span></span> 

<span data-ttu-id="5bd2c-140">선택적 데이터에는 클라이언트의 진단 데이터 및 피드백 데이터가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="5bd2c-140">Optional data includes diagnostic data and feedback data from the client.</span></span> <span data-ttu-id="5bd2c-141">선택적 진단 데이터는 제품을 개선하고 향상된 정보를 제공하여 문제를 감지, 진단, 해결하는 데 도움이 되는 추가 데이터입니다.</span><span class="sxs-lookup"><span data-stu-id="5bd2c-141">Optional diagnostic data is additional data that helps us make product improvements and provides enhanced information to help us detect, diagnose, and fix issues.</span></span> <span data-ttu-id="5bd2c-142">이 데이터는 진단 목적으로만 사용하며 서비스 자체에 필요하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="5bd2c-142">This data is only for diagnostic purposes and is not required for the service itself.</span></span> 

<span data-ttu-id="5bd2c-143">선택적 진단 데이터에는 다음이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="5bd2c-143">Optional diagnostic data includes:</span></span> 

- <span data-ttu-id="5bd2c-144">끝점용 Defender에 대한 앱, CPU 및 네트워크 사용.</span><span class="sxs-lookup"><span data-stu-id="5bd2c-144">App, CPU, and network usage for Defender for Endpoint.</span></span> 

- <span data-ttu-id="5bd2c-145">관리자가 끝점용 Defender에 대해 구성한 기능입니다.</span><span class="sxs-lookup"><span data-stu-id="5bd2c-145">Features configured by the admin for Defender for Endpoint.</span></span> 

<span data-ttu-id="5bd2c-146">피드백 데이터는 사용자가 제공한 앱 내 피드백을 통해 수집됩니다.</span><span class="sxs-lookup"><span data-stu-id="5bd2c-146">Feedback Data is collected through in-app feedback provided by the user.</span></span> 

- <span data-ttu-id="5bd2c-147">사용자의 전자 메일 주소(제공하도록 선택한 경우)</span><span class="sxs-lookup"><span data-stu-id="5bd2c-147">The user's email address, if they choose to provide it.</span></span>

- <span data-ttu-id="5bd2c-148">피드백 유형(스마일, 희미한, 아이디어) 및 사용자가 제출한 피드백 설명입니다.</span><span class="sxs-lookup"><span data-stu-id="5bd2c-148">Feedback type (smile, frown, idea) and any feedback comments submitted by the user.</span></span> 

<span data-ttu-id="5bd2c-149">자세한 내용은 개인 정보 [보호에 대한 자세한 정보를 참조하세요.](https://aka.ms/mdatpiosprivacystatement)</span><span class="sxs-lookup"><span data-stu-id="5bd2c-149">For more information, see [More on Privacy](https://aka.ms/mdatpiosprivacystatement).</span></span>


