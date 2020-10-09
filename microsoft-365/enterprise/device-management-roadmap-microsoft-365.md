---
title: Microsoft 365에 대 한 장치 관리 로드맵
keywords: Microsoft 365, enterprise for microsoft 365, Microsoft 365 설명서, 모바일 장치 관리, Intune
author: JoeDavies-MSFT
ms.author: josephd
manager: laurawi
ms.date: 08/10/2020
ms.topic: conceptual
f1.keywords:
- NOCSH
ms.prod: microsoft-365-enterprise
ms.service: ''
ms.technology: ''
ms.assetid: fb4182e6-5e78-45d0-9641-d791c4519441
audience: ITPro
ms.custom: microsoft-intune
description: Microsoft 365에 대 한 장치 관리를 설정 하기 위한 로드맵
ms.openlocfilehash: d359cae62fbd1bf2468ad753670ff8e385d6f25b
ms.sourcegitcommit: cd17328baa58448214487e3e68c37590ab9fd08d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/09/2020
ms.locfileid: "48398964"
---
# <a name="device-management-roadmap-for-microsoft-365"></a><span data-ttu-id="2b61b-104">Microsoft 365에 대 한 장치 관리 로드맵</span><span class="sxs-lookup"><span data-stu-id="2b61b-104">Device management roadmap for Microsoft 365</span></span>

<span data-ttu-id="2b61b-105">엔터프라이즈에 대 한 Microsoft 365에는 조직 내에서 장치 및 해당 앱을 관리 하는 데 도움이 되는 기능이 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2b61b-105">Microsoft 365 for enterprise includes features to help manage devices, and their apps, within your organization.</span></span> <span data-ttu-id="2b61b-106">모바일 장치 관리는 조직의 리소스를 보호 하 고 보호 하는 데 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2b61b-106">Managing mobile devices helps you secure and protect your organization's resources.</span></span>

<span data-ttu-id="2b61b-107">장치 관리에는 다음과 같은 두 가지 옵션이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2b61b-107">There are two options for device management:</span></span>

- [<span data-ttu-id="2b61b-108">Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="2b61b-108">Microsoft Intune</span></span>](#microsoft-intune)
- [<span data-ttu-id="2b61b-109">기본 이동성 및 보안</span><span class="sxs-lookup"><span data-stu-id="2b61b-109">Basic Mobility and Security</span></span>](#basic-mobility-and-security)

## <a name="microsoft-intune"></a><span data-ttu-id="2b61b-110">Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="2b61b-110">Microsoft Intune</span></span>

<span data-ttu-id="2b61b-111">Microsoft Intune을 사용 하 여 모바일 장치 관리 또는 모바일 응용 프로그램 관리를 통해 조직에 대 한 액세스를 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2b61b-111">You can use Microsoft Intune to manage access to your organization using mobile device management or mobile application management.</span></span> <span data-ttu-id="2b61b-112">모바일 장치 관리는 사용자가 Intune에서 장치를 "등록" 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="2b61b-112">Mobile device management is when users "enroll" their devices in Intune.</span></span> <span data-ttu-id="2b61b-113">장치를 등록 한 후에는 관리 되는 장치입니다. 따라서 조직의 정책, 규칙 및 설정을 받을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2b61b-113">After a device is enrolled, it is a managed device; therefore, it can receive your organization's  policies, rules, and settings.</span></span> <span data-ttu-id="2b61b-114">예를 들어 특정 앱을 설치 하 고, 암호 정책을 만들고, VPN 연결을 설치 하는 등의 작업을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2b61b-114">For example, you can install specific apps, create a password policy, install a VPN connection, and more.</span></span>

<span data-ttu-id="2b61b-115">개인 장치를 사용 하는 사용자는 장치를 등록 하거나 Intune 및 조직의 정책에 따라 관리 하지 않을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2b61b-115">Users with their own personal devices may not want to enroll their devices or be managed by Intune and your organization's policies.</span></span> <span data-ttu-id="2b61b-116">하지만 여전히 조직의 리소스 및 데이터를 보호 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2b61b-116">But you still need to protect your organization's resources and data.</span></span> <span data-ttu-id="2b61b-117">이 시나리오에서는 모바일 응용 프로그램 관리를 사용 하 여 앱을 보호할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2b61b-117">In this scenario, you can protect your apps using mobile application management.</span></span> <span data-ttu-id="2b61b-118">예를 들어 사용자가 장치에서 SharePoint Online에 액세스할 때 PIN을 입력 해야 하는 모바일 응용 프로그램 관리 정책을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2b61b-118">For example, you can use a mobile application management policy that requires a user to enter a PIN when accessing SharePoint Online on the device.</span></span>

<span data-ttu-id="2b61b-119">또한 개인 장치 및 조직 소유 장치를 관리 하는 방법을 결정 합니다.</span><span class="sxs-lookup"><span data-stu-id="2b61b-119">You'll also determine how you're going to manage personal devices and organization-owned devices.</span></span> <span data-ttu-id="2b61b-120">사용 방식에 따라 장치를 다르게 처리할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2b61b-120">You might want to treat devices differently, depending on their uses.</span></span>

## <a name="basic-mobility-and-security"></a><span data-ttu-id="2b61b-121">기본 이동성 및 보안</span><span class="sxs-lookup"><span data-stu-id="2b61b-121">Basic Mobility and Security</span></span>

<span data-ttu-id="2b61b-122">이는 Microsoft 365에 기본적으로 제공 되며, Iphone, Ipad, Androids 및 Windows 휴대폰 같은 사용자의 모바일 장치를 보호 하 고 관리 하는 데 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2b61b-122">This is built into Microsoft 365 and helps you secure and manage your users' mobile devices like iPhones, iPads, Androids, and Windows phones.</span></span> <span data-ttu-id="2b61b-123">디바이스 보안 정책을 생성하고 관리하며, 원격으로 디바이스를 지우고, 자세한 디바이스 보고서를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2b61b-123">You can create and manage device security policies, remotely wipe a device, and view detailed device reports.</span></span>

## <a name="choose-between-the-two-options"></a><span data-ttu-id="2b61b-124">두 옵션 중에서 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="2b61b-124">Choose between the two options</span></span>

<span data-ttu-id="2b61b-125">사용자에 게 가장 적합 한 장치 관리 옵션을 보다 쉽게 평가할 수 있도록 [기본 Mobility Security And Intune 사이](https://docs.microsoft.com/office365/securitycompliance/choose-between-mdm-and-intune)에 있는 선택을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="2b61b-125">To help you better assess which device management option is best for you, see [Choose between Basic Mobility Security and Intune](https://docs.microsoft.com/office365/securitycompliance/choose-between-mdm-and-intune).</span></span>

<span data-ttu-id="2b61b-126">평가에 따라 다음을 사용 하 여 장치 관리를 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="2b61b-126">Based on your assessment, get started managing your devices with:</span></span>

- <span data-ttu-id="2b61b-127">[Intune](https://docs.microsoft.com/mem/intune/fundamentals/planning-guide)</span><span class="sxs-lookup"><span data-stu-id="2b61b-127">[Intune](https://docs.microsoft.com/mem/intune/fundamentals/planning-guide).</span></span>
- <span data-ttu-id="2b61b-128">[기본 이동성 및 보안](https://support.microsoft.com/office/set-up-basic-mobility-and-security-dd892318-bc44-4eb1-af00-9db5430be3cd)</span><span class="sxs-lookup"><span data-stu-id="2b61b-128">[Basic Mobility and Security](https://support.microsoft.com/office/set-up-basic-mobility-and-security-dd892318-bc44-4eb1-af00-9db5430be3cd).</span></span>
 
## <a name="identity-and-device-access-recommendations"></a><span data-ttu-id="2b61b-129">ID 및 장치 액세스 권장 사항</span><span class="sxs-lookup"><span data-stu-id="2b61b-129">Identity and device access recommendations</span></span>

<span data-ttu-id="2b61b-130">Microsoft에서는 직원 안전과 생산성을 유지하기 위해 [ID 및 디바이스 액세스](../security/office-365-security/microsoft-365-policies-configurations.md)에 대한 권장 사항을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="2b61b-130">Microsoft provides a set of recommendations for [identity and device access](../security/office-365-security/microsoft-365-policies-configurations.md) to ensure a secure and productive workforce.</span></span> <span data-ttu-id="2b61b-131">장치 액세스용으로 다음 문서의 권장 사항 및 설정을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="2b61b-131">For device access, use the recommendations and settings in these articles:</span></span>

- [<span data-ttu-id="2b61b-132">필수 구성 요소</span><span class="sxs-lookup"><span data-stu-id="2b61b-132">Prerequisites</span></span>](../security/office-365-security/identity-access-prerequisites.md)
- [<span data-ttu-id="2b61b-133">일반 ID 및 장치 액세스 정책</span><span class="sxs-lookup"><span data-stu-id="2b61b-133">Common identity and device access policies</span></span>](../security/office-365-security/identity-access-policies.md)

## <a name="how-contoso-did-device-management-for-microsoft-365"></a><span data-ttu-id="2b61b-134">Contoso에서 Microsoft 365에 대 한 장치 관리를 수행 하는 방법</span><span class="sxs-lookup"><span data-stu-id="2b61b-134">How Contoso did device management for Microsoft 365</span></span>

<span data-ttu-id="2b61b-135">가상의 대표적인 다국적 기업이 Microsoft 365 클라우드 서비스와 함께 모바일 장치 관리 인프라를 배포 하는 방법에 대 한 자세한 내용은 [모바일 장치 관리 Contoso](contoso-mdm.md)를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="2b61b-135">For information about how a fictional but representative multi-national business deployed their mobile device management infrastructure with Microsoft 365 cloud services, see [Mobile device management for Contoso](contoso-mdm.md).</span></span>
