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
ms.openlocfilehash: 1a1bdb449aa1d1ba12cf1de422b3e279df6c1376
ms.sourcegitcommit: 19515d787246d38c4e0da579a767ce67b9dbc2bc
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/31/2020
ms.locfileid: "47315744"
---
# <a name="device-management-roadmap-for-microsoft-365"></a><span data-ttu-id="a6074-104">Microsoft 365에 대 한 장치 관리 로드맵</span><span class="sxs-lookup"><span data-stu-id="a6074-104">Device management roadmap for Microsoft 365</span></span>


<span data-ttu-id="a6074-105">엔터프라이즈에 대 한 Microsoft 365에는 조직 내에서 장치 및 해당 앱을 관리 하는 데 도움이 되는 기능이 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a6074-105">Microsoft 365 for enterprise includes features to help manage devices, and their apps, within your organization.</span></span> <span data-ttu-id="a6074-106">모바일 장치 관리는 조직의 리소스를 보호 하 고 보호 하는 데 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a6074-106">Managing mobile devices helps you secure and protect your organization's resources.</span></span>

<span data-ttu-id="a6074-107">장치 관리에는 두 가지 옵션이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a6074-107">There are two options for device management.</span></span>

## <a name="microsoft-intune"></a><span data-ttu-id="a6074-108">Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="a6074-108">Microsoft Intune</span></span>

<span data-ttu-id="a6074-109">Intune에서는 MDM (모바일 장치 관리) 또는 MAM (모바일 응용 프로그램 관리)를 사용 하 여 조직에 대 한 액세스를 관리할 수 있는 옵션을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="a6074-109">Intune gives you options to manage access to your organization using Mobile Device Management (MDM) or Mobile Application Management (MAM).</span></span> <span data-ttu-id="a6074-110">MDM은 사용자가 Intune에서 장치를 "등록" 하는 경우입니다.</span><span class="sxs-lookup"><span data-stu-id="a6074-110">MDM is when users "enroll" their devices in Intune.</span></span> <span data-ttu-id="a6074-111">등록 된 사용자는 관리 되는 장치 이며 조직에서 사용 하는 모든 정책, 규칙 및 설정을 받을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a6074-111">Once enrolled, they are managed devices, and can receive any policies, rules, and settings used by your organization.</span></span> <span data-ttu-id="a6074-112">예를 들어 특성 앱을 설치 하 고 암호 정책을 만들고 VPN 연결을 설치 하는 등의 다양 한 방법을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a6074-112">For example, you can install specifics apps, create a password policy, install a VPN connection, and more.</span></span>

<span data-ttu-id="a6074-113">개인 장치를 사용 하는 사용자는 장치를 등록 하거나 Intune 및 정책으로 관리 하지 않을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a6074-113">Users with their own personal devices may not want to enroll their devices or be managed by Intune and your policies.</span></span> <span data-ttu-id="a6074-114">하지만 여전히 조직의 리소스 및 데이터를 보호 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a6074-114">But you still need to protect your organization's resources and data.</span></span> <span data-ttu-id="a6074-115">이 시나리오에서는 MAM을 사용 하 여 앱을 보호할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a6074-115">In this scenario, you can protect your apps using MAM.</span></span> <span data-ttu-id="a6074-116">예를 들어 장치에서 SharePoint에 액세스할 때 사용자가 PIN을 입력 해야 하는 MAM 정책을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a6074-116">For example, you can use a MAM policy that requires a user to enter a PIN when accessing SharePoint on the device.</span></span>

<span data-ttu-id="a6074-117">또한 개인 또는 조직 소유 장치를 관리 하는 방법을 결정 합니다.</span><span class="sxs-lookup"><span data-stu-id="a6074-117">You'll also determine how you're going to manage personal or organization-owned devices.</span></span> <span data-ttu-id="a6074-118">사용 방식에 따라 장치를 다르게 처리할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a6074-118">You may want to treat devices differently, depending on their use.</span></span> 

<span data-ttu-id="a6074-119">[여기](https://docs.microsoft.com/mem/intune/fundamentals/planning-guide)에서 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="a6074-119">Start [here](https://docs.microsoft.com/mem/intune/fundamentals/planning-guide).</span></span>

## <a name="basic-mobility-and-security"></a><span data-ttu-id="a6074-120">기본 이동성 및 보안</span><span class="sxs-lookup"><span data-stu-id="a6074-120">Basic Mobility and Security</span></span>
 
<span data-ttu-id="a6074-121">이는 Microsoft 365에 기본적으로 제공 되며, Iphone, Ipad, Androids 및 Windows 휴대폰 같은 사용자의 모바일 장치를 보호 하 고 관리 하는 데 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a6074-121">This is built into Microsoft 365 and helps you secure and manage your users' mobile devices like iPhones, iPads, Androids, and Windows phones.</span></span> <span data-ttu-id="a6074-122">디바이스 보안 정책을 생성하고 관리하며, 원격으로 디바이스를 지우고, 자세한 디바이스 보고서를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a6074-122">You can create and manage device security policies, remotely wipe a device, and view detailed device reports.</span></span> 

<span data-ttu-id="a6074-123">[여기](https://support.microsoft.com/office/set-up-basic-mobility-and-security-dd892318-bc44-4eb1-af00-9db5430be3cd)에서 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="a6074-123">Start [here](https://support.microsoft.com/office/set-up-basic-mobility-and-security-dd892318-bc44-4eb1-af00-9db5430be3cd).</span></span>
 
## <a name="identity-and-device-access-recommendations"></a><span data-ttu-id="a6074-124">ID 및 장치 액세스 권장 사항</span><span class="sxs-lookup"><span data-stu-id="a6074-124">Identity and device access recommendations</span></span>

<span data-ttu-id="a6074-125">Microsoft에서는 직원 안전과 생산성을 유지하기 위해 [ID 및 디바이스 액세스](microsoft-365-policies-configurations.md)에 대한 권장 사항을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="a6074-125">Microsoft provides a set of recommendations for [identity and device access](microsoft-365-policies-configurations.md) to ensure a secure and productive workforce.</span></span> <span data-ttu-id="a6074-126">장치 액세스용으로 다음 문서의 권장 사항 및 설정을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="a6074-126">For device access, use the recommendations and settings in these articles:</span></span>

- [<span data-ttu-id="a6074-127">필수 구성 요소</span><span class="sxs-lookup"><span data-stu-id="a6074-127">Prerequisites</span></span>](identity-access-prerequisites.md)
- [<span data-ttu-id="a6074-128">일반 ID 및 장치 액세스 정책</span><span class="sxs-lookup"><span data-stu-id="a6074-128">Common identity and device access policies</span></span>](identity-access-policies.md)

## <a name="how-contoso-did-device-management-for-microsoft-365"></a><span data-ttu-id="a6074-129">Contoso에서 Microsoft 365에 대 한 장치 관리를 수행 하는 방법</span><span class="sxs-lookup"><span data-stu-id="a6074-129">How Contoso did device management for Microsoft 365</span></span>

<span data-ttu-id="a6074-130">Contoso Corporation (가상의 대표적인 다국적 기업)이 Microsoft 365 클라우드 서비스와 함께 [모바일 장치 관리 인프라를 배포](contoso-mdm.md) 하는 방법을 알아봅니다.</span><span class="sxs-lookup"><span data-stu-id="a6074-130">See how the Contoso Corporation, a fictional but representative multi-national business, [deployed their mobile device management infrastructure](contoso-mdm.md) with Microsoft 365 cloud services.</span></span>
