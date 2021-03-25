---
title: 조건부 액세스를 사용하도록 설정하여 사용자, 장치 및 데이터를 보다 잘 보호
description: 조건부 액세스를 사용하도록 설정하여 장치가 위험 상태인 것으로 간주되고 응용 프로그램이 호환되지 않는 것으로 결정된 경우 응용 프로그램이 실행되지 않도록 합니다.
keywords: 조건부 액세스, 응용 프로그램 차단, 보안 수준, intune,
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
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 21d17ee789a4757df10e99514f23cfc26b186405
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/24/2021
ms.locfileid: "51166200"
---
# <a name="enable-conditional-access-to-better-protect-users-devices-and-data"></a><span data-ttu-id="990dd-104">조건부 액세스를 사용하도록 설정하여 사용자, 장치 및 데이터를 보다 잘 보호</span><span class="sxs-lookup"><span data-stu-id="990dd-104">Enable Conditional Access to better protect users, devices, and data</span></span> 

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="990dd-105">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="990dd-105">**Applies to:**</span></span>
- [<span data-ttu-id="990dd-106">엔드포인트용 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="990dd-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="990dd-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="990dd-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="990dd-108">Endpoint용 Defender를 경험하고 싶나요?</span><span class="sxs-lookup"><span data-stu-id="990dd-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="990dd-109">무료 평가판에 등록합니다.</span><span class="sxs-lookup"><span data-stu-id="990dd-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-conditionalaccess-abovefoldlink)

<span data-ttu-id="990dd-110">조건부 액세스는 보안 장치만 응용 프로그램에 액세스할 수 있도록 하여 사용자 및 엔터프라이즈 정보를 보다 잘 보호하는 데 도움이 되는 기능입니다.</span><span class="sxs-lookup"><span data-stu-id="990dd-110">Conditional Access is a capability that helps you better protect your users and enterprise information by making sure that only secure devices have access to applications.</span></span>

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RE4byD1]

<span data-ttu-id="990dd-111">조건부 액세스를 사용하면 장치의 위험 수준에 따라 엔터프라이즈 정보에 대한 액세스를 제어할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="990dd-111">With Conditional Access, you can control access to enterprise information based on the risk level of a device.</span></span> <span data-ttu-id="990dd-112">이렇게 하면 신뢰할 수 있는 사용자가 신뢰할 수 있는 응용 프로그램을 사용하여 신뢰할 수 있는 디바이스를 유지하는 데 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="990dd-112">This helps keep trusted users on trusted devices using trusted applications.</span></span>

<span data-ttu-id="990dd-113">장치 및 응용 프로그램이 실행되고 네트워크의 정보에 액세스할 수 있는 보안 조건을 정의하려면 장치가 규격 상태로 돌아올 때까지 응용 프로그램 실행을 중지하는 정책을 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="990dd-113">You can define security conditions under which devices and applications can run and access information from your network by enforcing policies to stop applications from running until a device returns to a compliant state.</span></span> 

<span data-ttu-id="990dd-114">끝점용 Defender의 조건부 액세스 구현은 Microsoft Intune(Intune) 장치 준수 정책 및 Azure AD(Azure Active Directory) 조건부 액세스 정책을 기반으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="990dd-114">The implementation of Conditional Access in Defender for Endpoint is based on Microsoft Intune (Intune) device compliance policies and Azure Active Directory (Azure AD) conditional access policies.</span></span> 

<span data-ttu-id="990dd-115">준수 정책은 조건부 액세스와 함께 하나 이상의 장치 준수 정책 규칙을 충족하는 장치만 응용 프로그램에 액세스할 수 있도록 허용하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="990dd-115">The compliance policy is used with Conditional Access to allow only devices that fulfill one or more device compliance policy rules to access applications.</span></span> 

## <a name="understand-the-conditional-access-flow"></a><span data-ttu-id="990dd-116">조건부 액세스 흐름 이해</span><span class="sxs-lookup"><span data-stu-id="990dd-116">Understand the Conditional Access flow</span></span>
<span data-ttu-id="990dd-117">조건부 액세스는 장치에 위협이 있는 경우 위협이 수정될 때까지 중요한 콘텐츠에 대한 액세스가 차단될 수 있도록 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="990dd-117">Conditional Access is put in place so that when a threat is seen on a device, access to sensitive content is blocked until the threat is remediated.</span></span> 

<span data-ttu-id="990dd-118">흐름은 낮은, 보통 또는 높은 위험을 지고 있는 장치로 시작됩니다.</span><span class="sxs-lookup"><span data-stu-id="990dd-118">The flow begins with devices being seen to have a low, medium, or high risk.</span></span> <span data-ttu-id="990dd-119">이러한 위험 결정은 Intune으로 전송됩니다.</span><span class="sxs-lookup"><span data-stu-id="990dd-119">These risk determinations are then sent to Intune.</span></span> 

<span data-ttu-id="990dd-120">Intune에서 정책을 구성하는 방법에 따라 특정 조건이 충족될 때 정책이 적용될 수 있도록 조건부 액세스를 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="990dd-120">Depending on how you configure policies in Intune, Conditional Access can be set up so that when certain conditions are met, the policy is applied.</span></span>

<span data-ttu-id="990dd-121">예를 들어 위험이 높은 장치에 조건부 액세스를 적용하도록 Intune을 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="990dd-121">For example, you can configure Intune to apply Conditional Access on devices that have a high risk.</span></span>

<span data-ttu-id="990dd-122">Intune에서 장치 준수 정책은 Azure AD 조건부 액세스와 함께 사용하여 응용 프로그램에 대한 액세스를 차단합니다.</span><span class="sxs-lookup"><span data-stu-id="990dd-122">In Intune, a device compliance policy is used in conjunction with Azure AD Conditional Access to block access to applications.</span></span> <span data-ttu-id="990dd-123">동시에 자동화된 조사 및 수정 프로세스가 실행됩니다.</span><span class="sxs-lookup"><span data-stu-id="990dd-123">In parallel, an automated investigation and remediation process is launched.</span></span>

 <span data-ttu-id="990dd-124">사용자는 자동화된 조사 및 수정이 진행되는 동안에도 장치를 사용할 수 있지만 위협이 완전히 해결될 때까지 엔터프라이즈 데이터에 대한 액세스는 차단됩니다.</span><span class="sxs-lookup"><span data-stu-id="990dd-124">A user can still use the device while the automated investigation and remediation is taking place, but access to enterprise data is blocked until the threat is fully remediated.</span></span> 

<span data-ttu-id="990dd-125">장치에서 발견되는 위험을 해결하려면 장치를 규격 상태로 되찾아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="990dd-125">To resolve the risk found on a device, you'll need to return the device to a compliant state.</span></span> <span data-ttu-id="990dd-126">장치가 위험에 노출될 위험이 없는 경우 규격 상태로 돌아올 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="990dd-126">A device returns to a compliant state when there is no risk seen on it.</span></span> 

<span data-ttu-id="990dd-127">위험을 해결할 수 있는 방법에는 세 가지가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="990dd-127">There are three ways to address a risk:</span></span>
1. <span data-ttu-id="990dd-128">수동 또는 자동화된 수정을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="990dd-128">Use Manual or automated remediation.</span></span>
2. <span data-ttu-id="990dd-129">장치에서 활성 경고를 해결합니다.</span><span class="sxs-lookup"><span data-stu-id="990dd-129">Resolve active alerts on the device.</span></span> <span data-ttu-id="990dd-130">이렇게 하면 장치에서 위험이 제거됩니다.</span><span class="sxs-lookup"><span data-stu-id="990dd-130">This will remove the risk from the device.</span></span>
3. <span data-ttu-id="990dd-131">활성 정책에서 장치를 제거할 수 있으며 결과적으로 조건부 액세스가 장치에 적용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="990dd-131">You can remove the device from the active policies and consequently, Conditional Access will not be applied on the device.</span></span> 

<span data-ttu-id="990dd-132">수동 수정을 위해서는 보안 관리자가 경고를 조사하고 장치에 표시될 위험을 해결해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="990dd-132">Manual remediation requires a secops admin to investigate an alert and address the risk seen on the device.</span></span> <span data-ttu-id="990dd-133">자동화된 수정은 Configure Conditional Access 섹션에 제공된 구성 설정을 [통해 구성됩니다.](configure-conditional-access.md)</span><span class="sxs-lookup"><span data-stu-id="990dd-133">The automated remediation is configured through configuration settings provided in the following section, [Configure Conditional Access](configure-conditional-access.md).</span></span>

<span data-ttu-id="990dd-134">수동 또는 자동화된 수정을 통해 위험을 제거하면 장치가 규격 상태로 돌아와 응용 프로그램에 대한 액세스 권한이 부여됩니다.</span><span class="sxs-lookup"><span data-stu-id="990dd-134">When the risk is removed either through manual or automated remediation, the device returns to a compliant state and access to applications is granted.</span></span>

<span data-ttu-id="990dd-135">다음 이벤트 시퀀스 예제에서는 조건부 액세스의 실행에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="990dd-135">The following example sequence of events explains Conditional Access in action:</span></span>

1. <span data-ttu-id="990dd-136">사용자가 악성 파일을 열고 Endpoint용 Defender가 디바이스에 높은 위험으로 플래그를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="990dd-136">A user opens a malicious file and Defender for Endpoint flags the device as high risk.</span></span>
2. <span data-ttu-id="990dd-137">높은 위험 평가는 Intune을 따라 전달됩니다.</span><span class="sxs-lookup"><span data-stu-id="990dd-137">The high risk assessment is passed along to Intune.</span></span> <span data-ttu-id="990dd-138">동시에 식별된 위협을 수정하기 위해 자동화된 조사가 시작됩니다.</span><span class="sxs-lookup"><span data-stu-id="990dd-138">In parallel, an automated investigation is initiated to remediate the identified threat.</span></span> <span data-ttu-id="990dd-139">식별된 위협을 수정하기 위해 수동 수정을 할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="990dd-139">A manual remediation can also be done to remediate the identified threat.</span></span>
3. <span data-ttu-id="990dd-140">Intune에서 만든 정책에 따라 장치가 규격이 아닌 것으로 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="990dd-140">Based on the policy created in Intune, the device is marked as not compliant.</span></span> <span data-ttu-id="990dd-141">그런 다음 평가는 Intune 조건부 액세스 정책에 의해 Azure AD에 전달됩니다.</span><span class="sxs-lookup"><span data-stu-id="990dd-141">The assessment is then communicated to Azure AD by the Intune Conditional Access policy.</span></span> <span data-ttu-id="990dd-142">Azure AD에서는 응용 프로그램에 대한 액세스를 차단하기 위해 해당 정책이 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="990dd-142">In Azure AD, the corresponding policy is applied to block access to applications.</span></span>
4. <span data-ttu-id="990dd-143">수동 또는 자동화된 조사 및 수정이 완료되고 위협이 제거됩니다.</span><span class="sxs-lookup"><span data-stu-id="990dd-143">The manual or automated investigation and remediation is completed and the threat is removed.</span></span> <span data-ttu-id="990dd-144">Endpoint용 Defender는 장치에 위험이 없음을 보고 Intune은 장치가 규격 상태인 것으로 평가합니다.</span><span class="sxs-lookup"><span data-stu-id="990dd-144">Defender for Endpoint sees that there is no risk on the device and Intune assesses the device to be in a compliant state.</span></span> <span data-ttu-id="990dd-145">Azure AD는 응용 프로그램에 대한 액세스를 허용하는 정책을 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="990dd-145">Azure AD applies the policy which allows access to applications.</span></span>
5. <span data-ttu-id="990dd-146">이제 사용자가 응용 프로그램에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="990dd-146">Users can now access applications.</span></span>

 
## <a name="related-topic"></a><span data-ttu-id="990dd-147">관련 항목</span><span class="sxs-lookup"><span data-stu-id="990dd-147">Related topic</span></span>
- [<span data-ttu-id="990dd-148">끝점용 Microsoft Defender에서 조건부 액세스 구성</span><span class="sxs-lookup"><span data-stu-id="990dd-148">Configure Conditional Access in Microsoft Defender for Endpoint</span></span>](configure-conditional-access.md)
