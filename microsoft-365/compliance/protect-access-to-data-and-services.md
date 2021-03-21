---
title: 사용자 및 장치 액세스 보호
f1.keywords:
- NOCSH
ms.author: bcarter
author: brendacarter
manager: laurawi
ms.date: 4/17/2018
audience: Admin
ms.topic: hub-page
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: a6ef28a4-2447-4b43-aae2-f5af6d53c68e
description: Microsoft 365 데이터 및 서비스에 대한 사용자 및 장치 액세스를 보호하고 데이터 손실을 방지하는 방법을 학습합니다.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: bd8bbb62bc87ff59594e2fb2a3e21311c2452d9f
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/19/2021
ms.locfileid: "50925544"
---
# <a name="protect-user-and-device-access"></a><span data-ttu-id="c62ea-103">사용자 및 장치 액세스 보호</span><span class="sxs-lookup"><span data-stu-id="c62ea-103">Protect user and device access</span></span>

<span data-ttu-id="c62ea-104">Microsoft 365 데이터 및 서비스에 대한 액세스를 보호하는 것은 사이버 공격으로부터 보호하고 데이터 손실을 방지하는 데 중요합니다.</span><span class="sxs-lookup"><span data-stu-id="c62ea-104">Protecting access to your Microsoft 365 data and services is crucial to defending against cyberattacks and guarding against data loss.</span></span> <span data-ttu-id="c62ea-105">환경의 다른 SaaS 응용 프로그램과 Azure Active Directory 응용 프로그램 프록시를 사용하여 게시된 사내 응용 프로그램에도 동일한 보호를 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c62ea-105">The same protections can be applied to other SaaS applications in your environment and even to on-premises applications published with Azure Active Directory Application Proxy.</span></span>
  
## <a name="step-1-review-recommendations"></a><span data-ttu-id="c62ea-106">1단계: 권장 사항 검토</span><span class="sxs-lookup"><span data-stu-id="c62ea-106">Step 1: Review recommendations</span></span>

<span data-ttu-id="c62ea-107">Azure AD 애플리케이션 프록시를 사용하여 게시한 온-프레미스 응용 프로그램, Office 365 및 다른 SaaS 서비스에 액세스하는 ID 및 디바이스를 보호하기 위해 권장되는 기능입니다.</span><span class="sxs-lookup"><span data-stu-id="c62ea-107">Recommended capabilities for protecting identities and devices that access Office 365, other SaaS services, and on-premises applications published with Azure AD Application Proxy.</span></span>
  
<span data-ttu-id="c62ea-108">[PDF](https://go.microsoft.com/fwlink/p/?linkid=841656) | [Visio](https://go.microsoft.com/fwlink/p/?linkid=841657) | [더 많은 언어](https://www.microsoft.com/download/details.aspx?id=55032)</span><span class="sxs-lookup"><span data-stu-id="c62ea-108">[PDF](https://go.microsoft.com/fwlink/p/?linkid=841656) | [Visio](https://go.microsoft.com/fwlink/p/?linkid=841657) | [More languages](https://www.microsoft.com/download/details.aspx?id=55032)</span></span>
  
## <a name="step-2-protect-administrator-accounts-and-access"></a><span data-ttu-id="c62ea-109">2단계: 관리자 계정 및 액세스 보호</span><span class="sxs-lookup"><span data-stu-id="c62ea-109">Step 2: Protect administrator accounts and access</span></span>
<span data-ttu-id="c62ea-110">Microsoft 365 환경을 관리하는 데 사용하는 관리 계정에는 상승된 권한이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="c62ea-110">The administrative accounts you use to administer your Microsoft 365 environment include elevated privileges.</span></span> <span data-ttu-id="c62ea-111">이는 해커와 사이버 공격자에 대한 중요한 대상입니다.</span><span class="sxs-lookup"><span data-stu-id="c62ea-111">These are valuable targets for hackers and cyberattackers.</span></span> 

<span data-ttu-id="c62ea-112">먼저 관리자 계정에만 관리합니다.</span><span class="sxs-lookup"><span data-stu-id="c62ea-112">Begin by using administrator accounts only for administration.</span></span> <span data-ttu-id="c62ea-113">관리자는 관리가 아닌 일반 사용에 대해 별도의 사용자 계정이 필요하며, 필요한 경우 해당 작업 기능과 관련된 작업을 완료하는 데만 관리 계정을 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c62ea-113">Admins should have a separate user account for regular, non-administrative use and only use their administrative account when necessary to complete a task associated with their job function.</span></span>

<span data-ttu-id="c62ea-114">다단계 인증 및 조건부 액세스를 통해 관리자 계정을 보호합니다.</span><span class="sxs-lookup"><span data-stu-id="c62ea-114">Protect your administrator accounts with multi-factor authentication and conditional access.</span></span> <span data-ttu-id="c62ea-115">자세한 내용은 관리자 계정 [보호를 참조하세요.](../security/office-365-security/identity-access-prerequisites.md#protecting-administrator-accounts)</span><span class="sxs-lookup"><span data-stu-id="c62ea-115">For more information, see [Protecting administrator accounts](../security/office-365-security/identity-access-prerequisites.md#protecting-administrator-accounts).</span></span> 

<span data-ttu-id="c62ea-116">다음으로, Office 365에서 권한 있는 액세스 관리를 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="c62ea-116">Next, configure privileged access management in Office 365.</span></span> <span data-ttu-id="c62ea-117">권한이 부여된 액세스 관리를 사용하면 Office 365의 권한 있는 관리 작업에 대한 세부적인 액세스 제어가 허용됩니다.</span><span class="sxs-lookup"><span data-stu-id="c62ea-117">Privileged access management allows granular access control over privileged admin tasks in Office 365.</span></span> <span data-ttu-id="c62ea-118">중요한 데이터에 대한 액세스 또는 중요한 구성 설정에 대한 액세스 권한이 있는 기존 권한 있는 관리자 계정을 사용할 수 있는 침해로부터 조직을 보호하는 데 도움이 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c62ea-118">It can help protect your organization from breaches that may use existing privileged admin accounts with standing access to sensitive data or access to critical configuration settings.</span></span>

- [<span data-ttu-id="c62ea-119">권한 있는 액세스 관리 개요</span><span class="sxs-lookup"><span data-stu-id="c62ea-119">Overview of privileged access management</span></span>](privileged-access-management-overview.md)
- [<span data-ttu-id="c62ea-120">권한이 부여된 액세스 관리 구성</span><span class="sxs-lookup"><span data-stu-id="c62ea-120">Configure privileged access management</span></span>](privileged-access-management-configuration.md)

<span data-ttu-id="c62ea-121">또 다른 권장할 점은 관리 작업을 위해 특별히 구성된 Workstation을 사용하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="c62ea-121">Another top recommendation is to use workstations specifically configured for administrative work.</span></span> <span data-ttu-id="c62ea-122">관리 작업에만 사용되는 전용 장치입니다.</span><span class="sxs-lookup"><span data-stu-id="c62ea-122">These are dedicated devices that are only used for administrative tasks.</span></span> <span data-ttu-id="c62ea-123">권한이 [부여된 액세스 보안 을 참조합니다.](/windows-server/identity/securing-privileged-access/securing-privileged-access)</span><span class="sxs-lookup"><span data-stu-id="c62ea-123">See [Securing privileged access](/windows-server/identity/securing-privileged-access/securing-privileged-access).</span></span>

<span data-ttu-id="c62ea-124">마지막으로 테넌트에 긴급 액세스 계정을 두 개 이상 만들어 관리 액세스 권한이 없는 경우의 영향을 완화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c62ea-124">Finally, you can mitigate the impact of inadvertent lack of administrative access by creating two or more emergency access accounts in your tenant.</span></span> <span data-ttu-id="c62ea-125">[Azure AD에서 긴급 액세스 계정 관리를 참조하세요.](/azure/active-directory/users-groups-roles/directory-emergency-access)</span><span class="sxs-lookup"><span data-stu-id="c62ea-125">See [Manage emergency access accounts in Azure AD](/azure/active-directory/users-groups-roles/directory-emergency-access).</span></span> 

## <a name="step-3-configure-recommended-identity-and-device-access-policies"></a><span data-ttu-id="c62ea-126">3단계: 권장 ID 및 장치 액세스 정책 구성</span><span class="sxs-lookup"><span data-stu-id="c62ea-126">Step 3: Configure recommended identity and device access policies</span></span>
<span data-ttu-id="c62ea-127">MFA(다단계 인증) 및 조건부 액세스 정책은 손상된 계정 및 무단 액세스를 완화하는 강력한 도구입니다.</span><span class="sxs-lookup"><span data-stu-id="c62ea-127">Multi-factor authentication (MFA) and conditional access policies are powerful tools for mitigating against compromised accounts and unauthorized access.</span></span> <span data-ttu-id="c62ea-128">함께 테스트된 정책 집합을 구현하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="c62ea-128">We recommend implementing a set of policies that have been tested together.</span></span> <span data-ttu-id="c62ea-129">배포 단계를 비롯한 자세한 내용은 ID 및 장치 액세스 [구성을 참조하세요.](../security/office-365-security/microsoft-365-policies-configurations.md)</span><span class="sxs-lookup"><span data-stu-id="c62ea-129">For more information, including deployment steps, see [Identity and device access configurations](../security/office-365-security/microsoft-365-policies-configurations.md).</span></span>

 <span data-ttu-id="c62ea-130">이러한 정책은 다음 기능을 구현합니다.</span><span class="sxs-lookup"><span data-stu-id="c62ea-130">These policies implement the following capabilities:</span></span>
- <span data-ttu-id="c62ea-131">Mult-factor authentication</span><span class="sxs-lookup"><span data-stu-id="c62ea-131">Mult-factor authentication</span></span>
- <span data-ttu-id="c62ea-132">조건부 액세스</span><span class="sxs-lookup"><span data-stu-id="c62ea-132">Conditional access</span></span>
- <span data-ttu-id="c62ea-133">Intune 앱 보호(디바이스의 앱 및 데이터 보호)</span><span class="sxs-lookup"><span data-stu-id="c62ea-133">Intune app protection (app and data protection for devices)</span></span>
- <span data-ttu-id="c62ea-134">Intune 장치 규정 준수 상태</span><span class="sxs-lookup"><span data-stu-id="c62ea-134">Intune device compliance</span></span>
- <span data-ttu-id="c62ea-135">Azure AD ID 보호</span><span class="sxs-lookup"><span data-stu-id="c62ea-135">Azure AD Identity Protection</span></span>

<span data-ttu-id="c62ea-136">Intune 장치 준수를 구현하려면 장치 등록이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="c62ea-136">Implementing Intune device compliance requires device enrollment.</span></span> <span data-ttu-id="c62ea-137">장치를 관리하면 해당 장치가 환경의 리소스에 액세스할 수 있도록 허용하기 전에 정상 및 규정 준수를 보장할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c62ea-137">Managing devices allows you to ensure that they are healthy and compliant before allowing them access to resources in your environment.</span></span> <span data-ttu-id="c62ea-138">[Intune에서 관리를 위해](/intune-classic/deploy-use/enroll-devices-in-microsoft-intune) 장치 등록을 참조</span><span class="sxs-lookup"><span data-stu-id="c62ea-138">See [Enroll devices for management in Intune](/intune-classic/deploy-use/enroll-devices-in-microsoft-intune)</span></span>

## <a name="step-4-configure-sharepoint-device-access-policies"></a><span data-ttu-id="c62ea-139">4단계: SharePoint 장치 액세스 정책 구성</span><span class="sxs-lookup"><span data-stu-id="c62ea-139">Step 4: Configure SharePoint device access policies</span></span>

<span data-ttu-id="c62ea-140">장치 액세스 제어를 사용하여 중요하고 높은 규제 대상 콘텐츠를 사용하여 SharePoint 사이트의 콘텐츠를 보호하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="c62ea-140">Microsoft recommends you protect content in SharePoint sites with sensitive and highly-regulated content with device access controls.</span></span> <span data-ttu-id="c62ea-141">자세한 내용은 SharePoint 사이트 및 파일 보안에 대한 정책 [권장 사항을 참조하세요.](../security/office-365-security/sharepoint-file-access-policies.md)</span><span class="sxs-lookup"><span data-stu-id="c62ea-141">For more information, see [Policy recommendations for securing SharePoint sites and files](../security/office-365-security/sharepoint-file-access-policies.md).</span></span>



