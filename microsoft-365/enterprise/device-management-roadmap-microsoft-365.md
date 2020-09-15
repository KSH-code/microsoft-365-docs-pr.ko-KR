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
ms.openlocfilehash: bb19c38d5cf92cfc04ac83bc29573ea24c93ef30
ms.sourcegitcommit: 13ae76220b4ad688438a5d1031a6e1b5300ffa23
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/15/2020
ms.locfileid: "47775174"
---
# <a name="device-management-roadmap-for-microsoft-365"></a><span data-ttu-id="6e2b8-104">Microsoft 365에 대 한 장치 관리 로드맵</span><span class="sxs-lookup"><span data-stu-id="6e2b8-104">Device management roadmap for Microsoft 365</span></span>

<span data-ttu-id="6e2b8-105">엔터프라이즈에 대 한 Microsoft 365에는 조직 내에서 장치 및 해당 앱을 관리 하는 데 도움이 되는 기능이 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6e2b8-105">Microsoft 365 for enterprise includes features to help manage devices, and their apps, within your organization.</span></span> <span data-ttu-id="6e2b8-106">모바일 장치 관리는 조직의 리소스를 보호 하 고 보호 하는 데 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6e2b8-106">Managing mobile devices helps you secure and protect your organization's resources.</span></span>

<span data-ttu-id="6e2b8-107">장치 관리에는 다음과 같은 두 가지 옵션이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6e2b8-107">There are two options for device management:</span></span>

- [<span data-ttu-id="6e2b8-108">Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="6e2b8-108">Microsoft Intune</span></span>](#microsoft-intune)
- [<span data-ttu-id="6e2b8-109">기본 이동성 및 보안</span><span class="sxs-lookup"><span data-stu-id="6e2b8-109">Basic Mobility and Security</span></span>](#basic-mobility-and-security)

## <a name="microsoft-intune"></a><span data-ttu-id="6e2b8-110">Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="6e2b8-110">Microsoft Intune</span></span>

<span data-ttu-id="6e2b8-111">Microsoft Intune을 사용 하 여 모바일 장치 관리 또는 모바일 응용 프로그램 관리를 통해 조직에 대 한 액세스를 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6e2b8-111">You can use Microsoft Intune to manage access to your organization using mobile device management or mobile application management.</span></span> <span data-ttu-id="6e2b8-112">모바일 장치 관리는 사용자가 Intune에서 장치를 "등록" 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="6e2b8-112">Mobile device management is when users "enroll" their devices in Intune.</span></span> <span data-ttu-id="6e2b8-113">장치를 등록 한 후에는 관리 되는 장치입니다. 따라서 조직의 정책, 규칙 및 설정을 받을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6e2b8-113">After a device is enrolled, it is a managed device; therefore, it can receive your organization's  policies, rules, and settings.</span></span> <span data-ttu-id="6e2b8-114">예를 들어 특정 앱을 설치 하 고, 암호 정책을 만들고, VPN 연결을 설치 하는 등의 작업을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6e2b8-114">For example, you can install specific apps, create a password policy, install a VPN connection, and more.</span></span>

<span data-ttu-id="6e2b8-115">개인 장치를 사용 하는 사용자는 장치를 등록 하거나 Intune 및 조직의 정책에 따라 관리 하지 않을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6e2b8-115">Users with their own personal devices may not want to enroll their devices or be managed by Intune and your organization's policies.</span></span> <span data-ttu-id="6e2b8-116">하지만 여전히 조직의 리소스 및 데이터를 보호 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6e2b8-116">But you still need to protect your organization's resources and data.</span></span> <span data-ttu-id="6e2b8-117">이 시나리오에서는 모바일 응용 프로그램 관리를 사용 하 여 앱을 보호할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6e2b8-117">In this scenario, you can protect your apps using mobile application management.</span></span> <span data-ttu-id="6e2b8-118">예를 들어 사용자가 장치에서 Microsoft SharePoint에 액세스할 때 PIN을 입력 해야 하는 모바일 응용 프로그램 관리 정책을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6e2b8-118">For example, you can use a mobile application management policy that requires a user to enter a PIN when accessing Microsoft SharePoint on the device.</span></span>

<span data-ttu-id="6e2b8-119">또한 개인 장치 및 조직 소유 장치를 관리 하는 방법을 결정 합니다.</span><span class="sxs-lookup"><span data-stu-id="6e2b8-119">You'll also determine how you're going to manage personal devices and organization-owned devices.</span></span> <span data-ttu-id="6e2b8-120">사용 방식에 따라 장치를 다르게 처리할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6e2b8-120">You might want to treat devices differently, depending on their uses.</span></span>

<span data-ttu-id="6e2b8-121">Intune을 사용 하 여 장치를 관리 하려면 [여기](https://docs.microsoft.com/mem/intune/fundamentals/planning-guide)에서 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="6e2b8-121">To manage devices using Intune, start [here](https://docs.microsoft.com/mem/intune/fundamentals/planning-guide).</span></span>

## <a name="basic-mobility-and-security"></a><span data-ttu-id="6e2b8-122">기본 이동성 및 보안</span><span class="sxs-lookup"><span data-stu-id="6e2b8-122">Basic Mobility and Security</span></span>

<span data-ttu-id="6e2b8-123">이는 Microsoft 365에 기본적으로 제공 되며, Iphone, Ipad, Androids 및 Windows 휴대폰 같은 사용자의 모바일 장치를 보호 하 고 관리 하는 데 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6e2b8-123">This is built into Microsoft 365 and helps you secure and manage your users' mobile devices like iPhones, iPads, Androids, and Windows phones.</span></span> <span data-ttu-id="6e2b8-124">디바이스 보안 정책을 생성하고 관리하며, 원격으로 디바이스를 지우고, 자세한 디바이스 보고서를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6e2b8-124">You can create and manage device security policies, remotely wipe a device, and view detailed device reports.</span></span>

<span data-ttu-id="6e2b8-125">기본 이동성 및 보안을 사용 하 여 장치를 관리 하려면 [여기](https://support.microsoft.com/office/set-up-basic-mobility-and-security-dd892318-bc44-4eb1-af00-9db5430be3cd)에서 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="6e2b8-125">To manage devices using Basic Mobility and Security, start [here](https://support.microsoft.com/office/set-up-basic-mobility-and-security-dd892318-bc44-4eb1-af00-9db5430be3cd).</span></span>
 
## <a name="identity-and-device-access-recommendations"></a><span data-ttu-id="6e2b8-126">ID 및 장치 액세스 권장 사항</span><span class="sxs-lookup"><span data-stu-id="6e2b8-126">Identity and device access recommendations</span></span>

<span data-ttu-id="6e2b8-127">Microsoft에서는 직원 안전과 생산성을 유지하기 위해 [ID 및 디바이스 액세스](microsoft-365-policies-configurations.md)에 대한 권장 사항을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="6e2b8-127">Microsoft provides a set of recommendations for [identity and device access](microsoft-365-policies-configurations.md) to ensure a secure and productive workforce.</span></span> <span data-ttu-id="6e2b8-128">장치 액세스용으로 다음 문서의 권장 사항 및 설정을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="6e2b8-128">For device access, use the recommendations and settings in these articles:</span></span>

- [<span data-ttu-id="6e2b8-129">필수 구성 요소</span><span class="sxs-lookup"><span data-stu-id="6e2b8-129">Prerequisites</span></span>](identity-access-prerequisites.md)
- [<span data-ttu-id="6e2b8-130">일반 ID 및 장치 액세스 정책</span><span class="sxs-lookup"><span data-stu-id="6e2b8-130">Common identity and device access policies</span></span>](identity-access-policies.md)

## <a name="how-contoso-did-device-management-for-microsoft-365"></a><span data-ttu-id="6e2b8-131">Contoso에서 Microsoft 365에 대 한 장치 관리를 수행 하는 방법</span><span class="sxs-lookup"><span data-stu-id="6e2b8-131">How Contoso did device management for Microsoft 365</span></span>

<span data-ttu-id="6e2b8-132">가상의 대표적인 다국적 기업이 Microsoft 365 클라우드 서비스와 함께 모바일 장치 관리 인프라를 배포 하는 방법에 대 한 자세한 내용은 [모바일 장치 관리 Contoso](contoso-mdm.md)를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="6e2b8-132">For information about how a fictional but representative multi-national business deployed their mobile device management infrastructure with Microsoft 365 cloud services, see [Mobile device management for Contoso](contoso-mdm.md).</span></span>
