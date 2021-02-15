---
title: 5단계. 엔터프라이즈용 Microsoft 365 테넌트의 장치 및 앱 관리
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.audience: ITPro
ms.topic: article
ms.prod: microsoft-365-enterprise
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
- m365solution-tenantmanagement
ms.custom:
- Ent_Solutions
description: Microsoft 365 테넌트에 대한 장치 및 앱 관리에 대한 올바른 옵션을 배포합니다.
ms.openlocfilehash: a581af3ec2ec192112656f1919e27f5b05a41cb1
ms.sourcegitcommit: 99a7354e6a6b4d9d5202674ef57852d52a43fef6
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/20/2021
ms.locfileid: "49908710"
---
# <a name="step-5-device-and-app-management-for-your-microsoft-365-for-enterprise-tenants"></a><span data-ttu-id="8656b-104">5단계.</span><span class="sxs-lookup"><span data-stu-id="8656b-104">Step 5.</span></span> <span data-ttu-id="8656b-105">엔터프라이즈용 Microsoft 365 테넌트의 장치 및 앱 관리</span><span class="sxs-lookup"><span data-stu-id="8656b-105">Device and app management for your Microsoft 365 for enterprise tenants</span></span>

<span data-ttu-id="8656b-106">엔터프라이즈용 Microsoft 365에는 MDM(모바일 장치 관리) 및 MAM(모바일 응용 프로그램 관리)을 사용하여 조직 내의 디바이스에서 장치를 관리하고 앱을 사용하는 데 도움이 되는 기능이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8656b-106">Microsoft 365 for enterprise includes features to help manage devices and the use of apps on those devices within your organization with mobile device management (MDM) and mobile application management (MAM).</span></span> <span data-ttu-id="8656b-107">iOS, Android, macOS 및 Windows 장치를 관리하여 데이터를 포함하여 조직의 리소스에 대한 액세스를 보호할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8656b-107">You can manage iOS, Android, macOS, and Windows devices to protect access to your organization's resources, including your data.</span></span> <span data-ttu-id="8656b-108">예를 들어 조직 외부의 사용자에게 전자 메일이 전송되지 않도록 방지하거나 조직의 데이터를 직장의 개인 장치에서 개인 데이터로부터 격리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8656b-108">For example, you can prevent emails from being sent to people outside your organization or isolate organization data from personal data on your worker's personal devices.</span></span>

<span data-ttu-id="8656b-109">다음은 사용자, 디바이스 및 Microsoft Teams와 같은 로컬 및 클라우드 생산성 앱의 사용에 대한 유효성 검사 및 관리의 예입니다.</span><span class="sxs-lookup"><span data-stu-id="8656b-109">Here is an example of the validation and management of users, their devices, and their use of local and cloud productivity apps like Microsoft Teams.</span></span>

![사용자, 장치 및 앱의 유효성 검사 및 관리](../media/tenant-management-overview/tenant-management-device-app-mgmt.png)

<span data-ttu-id="8656b-111">조직의 리소스를 보호하고 보호할 수 있도록 엔터프라이즈용 Microsoft 365에는 장치 및 앱에 대한 액세스를 관리하는 데 도움이 되는 기능이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8656b-111">To help you secure and protect your organization's resources, Microsoft 365 for enterprise includes features to help manage devices and their access to apps.</span></span> <span data-ttu-id="8656b-112">장치 관리에는 다음과 같은 두 가지 옵션이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8656b-112">There are two options for device management:</span></span>

- <span data-ttu-id="8656b-113">엔터프라이즈를 위한 포괄적인 장치 및 앱 관리 솔루션인 Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="8656b-113">Microsoft Intune, which is a comprehensive device and app management solution for enterprises.</span></span>
- <span data-ttu-id="8656b-114">조직의 장치를 관리하기 위한 모든 Microsoft 365 제품에 포함된 Intune 서비스의 하위 집합인 기본 이동성 및 보안</span><span class="sxs-lookup"><span data-stu-id="8656b-114">Basic Mobility and Security, which is a subset of Intune services included with all Microsoft 365 products for managing devices in your organization.</span></span> <span data-ttu-id="8656b-115">자세한 내용은 [기본 이동성 및 보안 기능을 참조하십시오.](https://docs.microsoft.com/microsoft-365/admin/basic-mobility-security/capabilities)</span><span class="sxs-lookup"><span data-stu-id="8656b-115">For more information, see [Capabilities of Basic Mobility and Security](https://docs.microsoft.com/microsoft-365/admin/basic-mobility-security/capabilities).</span></span>

<span data-ttu-id="8656b-116">Microsoft 365 E3 또는 E5가 있는 경우 Intune을 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8656b-116">If you have Microsoft 365 E3 or E5, you should use Intune.</span></span>

## <a name="microsoft-intune"></a><span data-ttu-id="8656b-117">Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="8656b-117">Microsoft Intune</span></span>

<span data-ttu-id="8656b-118">Microsoft [Intune을](https://docs.microsoft.com/mem/intune/fundamentals/planning-guide) 사용하여 MDM 또는 MAM을 사용하여 조직에 대한 액세스를 관리합니다.</span><span class="sxs-lookup"><span data-stu-id="8656b-118">You use [Microsoft Intune](https://docs.microsoft.com/mem/intune/fundamentals/planning-guide) to manage access to your organization using MDM or MAM.</span></span> <span data-ttu-id="8656b-119">MDM은 사용자가 Intune에서 장치를 "등록"하는 경우입니다.</span><span class="sxs-lookup"><span data-stu-id="8656b-119">MDM is when users "enroll" their devices in Intune.</span></span> <span data-ttu-id="8656b-120">장치가 등록된 후 관리되는 장치로, 조직의 정책, 규칙 및 설정을 받을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8656b-120">After a device is enrolled, it is a managed device and can receive your organization's  policies, rules, and settings.</span></span> <span data-ttu-id="8656b-121">예를 들어 특정 앱을 설치하고, 암호 정책을 만들고, VPN 연결을 설치하는 등 다양한 기능을 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8656b-121">For example, you can install specific apps, create a password policy, install a VPN connection, and more.</span></span>

<span data-ttu-id="8656b-122">개인 장치를 소유한 사용자는 장치를 등록하거나 Intune 및 조직의 정책에 의해 관리하지 않을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8656b-122">Users with their own personal devices may not want to enroll their devices or be managed by Intune and your organization's policies.</span></span> <span data-ttu-id="8656b-123">그러나 여전히 조직의 리소스와 데이터를 보호해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8656b-123">But you still need to protect your organization's resources and data.</span></span> <span data-ttu-id="8656b-124">이 시나리오에서는 MAM을 사용하여 앱을 보호할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8656b-124">In this scenario, you can protect your apps using MAM.</span></span> <span data-ttu-id="8656b-125">예를 들어 장치에서 SharePoint에 액세스할 때 사용자가 PIN을 입력해야 하는 MAM 정책을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8656b-125">For example, you can use an MAM policy that requires a user to enter a PIN when accessing SharePoint on the device.</span></span>

<span data-ttu-id="8656b-126">개인 장치 및 조직 소유 장치를 관리하는 방법도 결정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8656b-126">You'll also determine how you're going to manage personal devices and organization-owned devices.</span></span> <span data-ttu-id="8656b-127">디바이스의 용도에 따라 디바이스를 다르게 처리해야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8656b-127">You might want to treat devices differently, depending on their uses.</span></span>

## <a name="identity-and-device-access-configurations"></a><span data-ttu-id="8656b-128">ID 및 장치 액세스 구성</span><span class="sxs-lookup"><span data-stu-id="8656b-128">Identity and device access configurations</span></span>

<span data-ttu-id="8656b-129">Microsoft는 안전하고 생산적인 [](../security/office-365-security/microsoft-365-policies-configurations.md) 인력을 확보하기 위해 ID 및 장치 액세스에 대한 구성 집합을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="8656b-129">Microsoft provides a set of configurations for [identity and device access](../security/office-365-security/microsoft-365-policies-configurations.md) to ensure a secure and productive workforce.</span></span> <span data-ttu-id="8656b-130">이러한 구성에는 다음의 사용이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="8656b-130">These configurations include the use of:</span></span>

- <span data-ttu-id="8656b-131">Azure AD 조건부 액세스 정책</span><span class="sxs-lookup"><span data-stu-id="8656b-131">Azure AD Conditional Access policies</span></span>
- <span data-ttu-id="8656b-132">Microsoft Intune 장치 준수 및 앱 보호 정책</span><span class="sxs-lookup"><span data-stu-id="8656b-132">Microsoft Intune device compliance and app protection policies</span></span>
- <span data-ttu-id="8656b-133">Azure AD ID 보호 사용자 위험 정책</span><span class="sxs-lookup"><span data-stu-id="8656b-133">Azure AD Identity Protection user risk policies</span></span>
- <span data-ttu-id="8656b-134">클라우드 앱의 추가 정책</span><span class="sxs-lookup"><span data-stu-id="8656b-134">Additional policies of cloud apps</span></span>

<span data-ttu-id="8656b-135">다음은 사용자, 디바이스 및 Microsoft Teams와 같은 로컬 및 클라우드 생산성 앱의 사용에 대한 유효성을 검사하고 제한하기 위한 이러한 설정 및 정책을 적용하는 예제입니다.</span><span class="sxs-lookup"><span data-stu-id="8656b-135">Here is an example of the application of these settings and policies to validate and restrict users, their devices, and their use of local and cloud productivity apps like Microsoft Teams.</span></span>

![사용자, 디바이스 및 앱 사용에 대한 요구 사항 및 제한에 대한 ID 및 장치 액세스 구성](../media/tenant-management-overview/tenant-management-device-app-mgmt-golden-config.png)

<span data-ttu-id="8656b-137">장치 액세스 및 앱 관리를 위해 다음 문서의 구성을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="8656b-137">For device access and app management, use the configurations in these articles:</span></span>

- [<span data-ttu-id="8656b-138">필수 구성 요소</span><span class="sxs-lookup"><span data-stu-id="8656b-138">Prerequisites</span></span>](../security/office-365-security/identity-access-prerequisites.md)
- [<span data-ttu-id="8656b-139">일반 ID 및 장치 액세스 정책</span><span class="sxs-lookup"><span data-stu-id="8656b-139">Common identity and device access policies</span></span>](../security/office-365-security/identity-access-policies.md)

## <a name="results-of-step-5"></a><span data-ttu-id="8656b-140">5단계의 결과</span><span class="sxs-lookup"><span data-stu-id="8656b-140">Results of Step 5</span></span>

<span data-ttu-id="8656b-141">Microsoft 365 테넌트에 대한 장치 및 앱 관리의 경우 사용자, 디바이스 및 로컬 및 클라우드 생산성 앱의 사용에 대한 유효성을 검사하고 제한하기 위한 Intune 설정 및 정책을 결정했습니다.</span><span class="sxs-lookup"><span data-stu-id="8656b-141">For device and app management for your Microsoft 365 tenant, you have determined the Intune settings and policies to validate and restrict users, their devices, and their use of local and cloud productivity apps.</span></span>

<span data-ttu-id="8656b-142">다음은 새 요소가 강조 표시된 Intune 장치 및 앱 관리를 사용하여 테넌트의 예입니다.</span><span class="sxs-lookup"><span data-stu-id="8656b-142">Here is an example of a tenant with Intune device and app management with the new elements highlighted.</span></span>

![Intune 장치 및 앱 관리를 사용하여 테넌트의 예](../media/tenant-management-overview/tenant-management-tenant-build-step5.png)

<span data-ttu-id="8656b-144">이 그림에서 테넌트에는 다음이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8656b-144">In this illustration, the tenant has:</span></span>

- <span data-ttu-id="8656b-145">Intune에 등록된 조직 소유 장치입니다.</span><span class="sxs-lookup"><span data-stu-id="8656b-145">Organization-owned devices enrolled in Intune.</span></span>
- <span data-ttu-id="8656b-146">등록된 디바이스 및 개인 장치에 대한 Intune 장치 및 앱 정책</span><span class="sxs-lookup"><span data-stu-id="8656b-146">Intune device and app policies for enrolled and personal devices.</span></span>

## <a name="ongoing-maintenance-for-device-and-app-management"></a><span data-ttu-id="8656b-147">장치 및 앱 관리에 대한 지속적인 유지 관리</span><span class="sxs-lookup"><span data-stu-id="8656b-147">Ongoing maintenance for device and app management</span></span>

<span data-ttu-id="8656b-148">지속적인 기준에 따라 다음을 해야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8656b-148">On an ongoing basis, you might need to:</span></span> 

- <span data-ttu-id="8656b-149">장치 등록을 관리합니다.</span><span class="sxs-lookup"><span data-stu-id="8656b-149">Manage device enrollment.</span></span>
- <span data-ttu-id="8656b-150">추가 앱, 장치 및 보안 요구 사항에 대한 설정 및 정책을 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="8656b-150">Revise your settings and policies for additional apps, devices, and security requirements.</span></span>
