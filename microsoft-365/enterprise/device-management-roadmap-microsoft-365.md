---
title: Microsoft 365에 대한 장치 관리 로드맵
keywords: Microsoft 365, 엔터프라이즈용 Microsoft 365, Microsoft 365 설명서, 모바일 장치 관리, Intune
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
description: Microsoft 365에 대한 장치 관리를 설정하기 위한 로드맵입니다.
ms.openlocfilehash: 79be47d6bc83c124f2203866986e06181a1f7f3d
ms.sourcegitcommit: ae646779d84e993cf80b1207e76b856a21be5790
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/04/2021
ms.locfileid: "49749542"
---
# <a name="device-management-roadmap-for-microsoft-365"></a><span data-ttu-id="ab519-104">Microsoft 365에 대한 장치 관리 로드맵</span><span class="sxs-lookup"><span data-stu-id="ab519-104">Device management roadmap for Microsoft 365</span></span>

<span data-ttu-id="ab519-105">엔터프라이즈용 Microsoft 365에는 조직 내에서 장치 및 해당 앱을 관리하는 데 도움이 되는 기능이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ab519-105">Microsoft 365 for enterprise includes features to help manage devices, and their apps, within your organization.</span></span> <span data-ttu-id="ab519-106">모바일 장치를 관리하면 조직의 리소스를 보호하고 보호할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ab519-106">Managing mobile devices helps you secure and protect your organization's resources.</span></span>

<span data-ttu-id="ab519-107">장치 관리에는 다음과 같은 두 가지 옵션이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ab519-107">There are two options for device management:</span></span>

- [<span data-ttu-id="ab519-108">Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="ab519-108">Microsoft Intune</span></span>](#microsoft-intune)
- [<span data-ttu-id="ab519-109">기본 모바일 및 보안</span><span class="sxs-lookup"><span data-stu-id="ab519-109">Basic Mobility and Security</span></span>](#basic-mobility-and-security)

## <a name="microsoft-intune"></a><span data-ttu-id="ab519-110">Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="ab519-110">Microsoft Intune</span></span>

<span data-ttu-id="ab519-111">Microsoft Intune을 사용하여 모바일 장치 관리 또는 모바일 응용 프로그램 관리를 사용하여 조직에 대한 액세스를 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ab519-111">You can use Microsoft Intune to manage access to your organization using mobile device management or mobile application management.</span></span> <span data-ttu-id="ab519-112">모바일 장치 관리는 사용자가 Intune에서 장치를 "등록"하는 경우입니다.</span><span class="sxs-lookup"><span data-stu-id="ab519-112">Mobile device management is when users "enroll" their devices in Intune.</span></span> <span data-ttu-id="ab519-113">장치가 등록된 후 관리되는 장치입니다. 따라서 조직의 정책, 규칙 및 설정을 받을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ab519-113">After a device is enrolled, it is a managed device; therefore, it can receive your organization's  policies, rules, and settings.</span></span> <span data-ttu-id="ab519-114">예를 들어 특정 앱을 설치하고, 암호 정책을 만들고, VPN 연결을 설치하는 등 다양한 기능을 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ab519-114">For example, you can install specific apps, create a password policy, install a VPN connection, and more.</span></span>

<span data-ttu-id="ab519-115">개인 장치를 소유한 사용자는 장치를 등록하거나 Intune 및 조직의 정책에 의해 관리하지 않을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ab519-115">Users with their own personal devices may not want to enroll their devices or be managed by Intune and your organization's policies.</span></span> <span data-ttu-id="ab519-116">그러나 여전히 조직의 리소스와 데이터를 보호해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ab519-116">But you still need to protect your organization's resources and data.</span></span> <span data-ttu-id="ab519-117">이 시나리오에서는 모바일 응용 프로그램 관리를 사용하여 앱을 보호할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ab519-117">In this scenario, you can protect your apps using mobile application management.</span></span> <span data-ttu-id="ab519-118">예를 들어 장치에서 SharePoint Online에 액세스할 때 사용자가 PIN을 입력해야 하는 모바일 응용 프로그램 관리 정책을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ab519-118">For example, you can use a mobile application management policy that requires a user to enter a PIN when accessing SharePoint Online on the device.</span></span>

<span data-ttu-id="ab519-119">개인 장치 및 조직 소유 장치를 관리하는 방법도 결정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ab519-119">You'll also determine how you're going to manage personal devices and organization-owned devices.</span></span> <span data-ttu-id="ab519-120">디바이스의 용도에 따라 디바이스를 다르게 처리해야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ab519-120">You might want to treat devices differently, depending on their uses.</span></span>

## <a name="basic-mobility-and-security"></a><span data-ttu-id="ab519-121">기본 모바일 및 보안</span><span class="sxs-lookup"><span data-stu-id="ab519-121">Basic Mobility and Security</span></span>

<span data-ttu-id="ab519-122">이 기능은 Microsoft 365에 기본 제공되어 iPhone, iPad, Android 및 Windows 휴대폰과 같은 사용자의 모바일 장치를 보호하고 관리하는 데 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ab519-122">This is built into Microsoft 365 and helps you secure and manage your users' mobile devices like iPhones, iPads, Androids, and Windows phones.</span></span> <span data-ttu-id="ab519-123">디바이스 보안 정책을 생성하고 관리하며, 원격으로 디바이스를 지우고, 자세한 디바이스 보고서를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ab519-123">You can create and manage device security policies, remotely wipe a device, and view detailed device reports.</span></span>

## <a name="choose-between-the-two-options"></a><span data-ttu-id="ab519-124">두 옵션 중 선택</span><span class="sxs-lookup"><span data-stu-id="ab519-124">Choose between the two options</span></span>

<span data-ttu-id="ab519-125">가장 적합한 장치 관리 옵션을 보다 잘 평가하려면 기본 이동성 보안과 Intune 중 선택을 [참조하세요.](https://docs.microsoft.com/office365/securitycompliance/choose-between-mdm-and-intune)</span><span class="sxs-lookup"><span data-stu-id="ab519-125">To help you better assess which device management option is best for you, see [Choose between Basic Mobility Security and Intune](https://docs.microsoft.com/office365/securitycompliance/choose-between-mdm-and-intune).</span></span>

<span data-ttu-id="ab519-126">평가에 따라 다음을 통해 디바이스 관리를 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="ab519-126">Based on your assessment, get started managing your devices with:</span></span>

- [<span data-ttu-id="ab519-127">Intune</span><span class="sxs-lookup"><span data-stu-id="ab519-127">Intune</span></span>](https://docs.microsoft.com/mem/intune/fundamentals/planning-guide)
- [<span data-ttu-id="ab519-128">기본 모바일 및 보안</span><span class="sxs-lookup"><span data-stu-id="ab519-128">Basic Mobility and Security</span></span>](https://support.microsoft.com/office/set-up-basic-mobility-and-security-dd892318-bc44-4eb1-af00-9db5430be3cd)
 
## <a name="identity-and-device-access-recommendations"></a><span data-ttu-id="ab519-129">ID 및 장치 액세스 권장 사항</span><span class="sxs-lookup"><span data-stu-id="ab519-129">Identity and device access recommendations</span></span>

<span data-ttu-id="ab519-130">Microsoft에서는 직원 안전과 생산성을 유지하기 위해 [ID 및 디바이스 액세스](../security/office-365-security/microsoft-365-policies-configurations.md)에 대한 권장 사항을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="ab519-130">Microsoft provides a set of recommendations for [identity and device access](../security/office-365-security/microsoft-365-policies-configurations.md) to ensure a secure and productive workforce.</span></span> <span data-ttu-id="ab519-131">장치 액세스의 경우 다음 문서의 권장 사항 및 설정을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="ab519-131">For device access, use the recommendations and settings in these articles:</span></span>

- [<span data-ttu-id="ab519-132">필수 구성 요소</span><span class="sxs-lookup"><span data-stu-id="ab519-132">Prerequisites</span></span>](../security/office-365-security/identity-access-prerequisites.md)
- [<span data-ttu-id="ab519-133">일반 ID 및 장치 액세스 정책</span><span class="sxs-lookup"><span data-stu-id="ab519-133">Common identity and device access policies</span></span>](../security/office-365-security/identity-access-policies.md)

## <a name="how-contoso-did-device-management-for-microsoft-365"></a><span data-ttu-id="ab519-134">Contoso에서 Microsoft 365에 대한 장치 관리를 한 방법</span><span class="sxs-lookup"><span data-stu-id="ab519-134">How Contoso did device management for Microsoft 365</span></span>

<span data-ttu-id="ab519-135">대표적인 다국적 기업이 Microsoft 365 클라우드 서비스를 사용하여 모바일 장치 관리 인프라를 배포한 방법에 대한 자세한 내용은 [Contoso의](contoso-mdm.md)모바일 장치 관리를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="ab519-135">For information about how a fictional but representative multi-national business deployed their mobile device management infrastructure with Microsoft 365 cloud services, see [Mobile device management for Contoso](contoso-mdm.md).</span></span>
