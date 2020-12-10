---
title: 권한이 부여된 액세스 관리에 대한 자세한 정보
description: 이 문서에서는 FAQ(질문과 대답)를 포함하여 Microsoft 365의 권한이 부여된 액세스 관리에 대한 개요를 제공합니다.
ms.author: robmazz
author: robmazz
manager: laurawi
audience: ITPro
ms.topic: overview
f1.keywords:
- NOCSH
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- Strat_O365_IP
- m365-security-compliance
- m365solution-insiderrisk
- m365initiative-compliance
ms.custom:
- Ent_Solutions
- seo-marvel-apr2020
ms.openlocfilehash: dc7c6807e8c89b4146784e5be7f57472777a4c84
ms.sourcegitcommit: a0cddd1f888edb940717e434cda2dbe62e5e9475
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/09/2020
ms.locfileid: "49613332"
---
# <a name="learn-about-privileged-access-management"></a><span data-ttu-id="a2812-103">권한이 부여된 액세스 관리에 대한 자세한 정보</span><span class="sxs-lookup"><span data-stu-id="a2812-103">Learn about privileged access management</span></span>

<span data-ttu-id="a2812-104">권한이 부여된 액세스 관리를 사용하면 Office 365의 권한 있는 관리 작업을 세부적인 액세스 제어가 허용됩니다.</span><span class="sxs-lookup"><span data-stu-id="a2812-104">Privileged access management allows granular access control over privileged admin tasks in Office 365.</span></span> <span data-ttu-id="a2812-105">중요한 데이터에 대한 액세스 또는 중요한 구성 설정에 대한 액세스 권한이 있는 기존 권한 있는 관리자 계정을 사용하는 위반으로부터 조직을 보호하는 데 도움이 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a2812-105">It can help protect your organization from breaches that use existing privileged admin accounts with standing access to sensitive data or access to critical configuration settings.</span></span> <span data-ttu-id="a2812-106">권한이 부여된 액세스 관리를 사용하려면 사용자가 범위가 넓고 시간이 제한적인 승인 워크플로를 통해 권한 상승 및 권한 있는 작업을 완료하기 위해 적시 액세스를 요청해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a2812-106">Privileged access management requires users to request just-in-time access to complete elevated and privileged tasks through a highly scoped and time-bounded approval workflow.</span></span> <span data-ttu-id="a2812-107">이 구성을 사용하면 중요한 데이터나 중요한 구성 설정이 노출되지 않고도 작업을 수행할 수 있는 충분한 액세스 권한을 사용자에게 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="a2812-107">This configuration gives users just-enough-access to perform the task at hand, without risking exposure of sensitive data or critical configuration settings.</span></span> <span data-ttu-id="a2812-108">Microsoft 365에서 권한이 부여된 액세스 관리를 사용하도록 설정하면 조직이 제로 스위딩 권한으로 운영할 수 있으며, 관리 액세스 취약성에 대한 방어 계층을 제공할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a2812-108">Enabling privileged access management in Microsoft 365 allows your organization to operate with zero standing privileges and provide a layer of defense against standing administrative access vulnerabilities.</span></span>

<span data-ttu-id="a2812-109">통합된 고객 Lockbox 및 권한이 부여된 액세스 관리 워크플로에 대한 간략한 개요는 이 Customer Lockbox 및 권한이 부여된 액세스 [관리 비디오를 참조하세요.](https://go.microsoft.com/fwlink/?linkid=2066800)</span><span class="sxs-lookup"><span data-stu-id="a2812-109">For a quick overview of the integrated Customer Lockbox and privileged access management workflow, see this [Customer Lockbox and privileged access management video](https://go.microsoft.com/fwlink/?linkid=2066800).</span></span>

## <a name="layers-of-protection"></a><span data-ttu-id="a2812-110">보호 계층</span><span class="sxs-lookup"><span data-stu-id="a2812-110">Layers of protection</span></span>

<span data-ttu-id="a2812-111">권한 있는 액세스 관리는 Microsoft 365 보안 아키텍처 내의 다른 데이터 및 액세스 기능 보호를 보완합니다.</span><span class="sxs-lookup"><span data-stu-id="a2812-111">Privileged access management complements other data and access feature protections within the Microsoft 365 security architecture.</span></span> <span data-ttu-id="a2812-112">권한 있는 액세스 관리를 보안에 대한 통합 및 계층적 접근 방식의 일부로 포함하면 중요한 정보 및 Microsoft 365 구성 설정의 보호를 최대화하는 보안 모델이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a2812-112">Including privileged access management as part of an integrated and layered approach to security provides a security model that maximizes protection of sensitive information and Microsoft 365 configuration settings.</span></span> <span data-ttu-id="a2812-113">다이어그램에 표시된 것 처럼 권한 있는 액세스 관리는 Microsoft 365 데이터의 기본 암호화와 Microsoft 365 서비스의 역할 기반 액세스 제어 보안 모델과 함께 제공되는 보호 기능을 기반으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="a2812-113">As shown in the diagram, privileged access management builds on the protection provided with native encryption of Microsoft 365 data and the role-based access control security model of Microsoft 365 services.</span></span> <span data-ttu-id="a2812-114">[Azure AD Privileged Identity Management와](https://docs.microsoft.com/azure/active-directory/active-directory-privileged-identity-management-configure)함께 사용할 경우 이러한 두 기능은 서로 다른 범위에서 Just-In-Time 액세스를 통해 액세스 제어를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="a2812-114">When used with [Azure AD Privileged Identity Management](https://docs.microsoft.com/azure/active-directory/active-directory-privileged-identity-management-configure), these two features provide access control with just-in-time access at different scopes.</span></span>

![Microsoft 365의 계층적 보호](../media/pam-layered-protection.png)

<span data-ttu-id="a2812-116">권한 있는 액세스 관리는 작업  수준에서 정의되고 범위가 지정되는 반면, Azure  AD Privileged Identity Management는 여러 작업을 실행하는 기능을 사용하여 역할 수준에서 보호를 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="a2812-116">Privileged access management is defined and scoped at the **task** level, while Azure AD Privileged Identity Management applies protection at the **role** level with the ability to execute multiple tasks.</span></span> <span data-ttu-id="a2812-117">Azure AD Privileged Identity Management는 주로 AD 역할 및 역할 그룹에 대한 액세스를 관리할 수 있도록 하지만 Microsoft 365의 권한 있는 액세스 관리는 작업 수준에서만 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="a2812-117">Azure AD Privileged Identity Management primarily allows managing accesses for AD roles and role groups, while privileged access management in Microsoft 365 applies only at the task level.</span></span>

- <span data-ttu-id="a2812-118">**Azure AD Privileged Identity Management를** 이미 사용하는 동안 권한 있는 액세스 관리를 사용하도록 설정: 권한 있는 액세스 관리를 추가하면 Microsoft 365 데이터에 대한 권한 있는 액세스에 대한 또 다른 세부적인 보호 및 감사 기능을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="a2812-118">**Enabling privileged access management while already using Azure AD Privileged Identity Management:** Adding privileged access management provides another granular layer of protection and audit capabilities for privileged access to Microsoft 365 data.</span></span>

- <span data-ttu-id="a2812-119">**Office 365에서**  권한 있는 액세스 관리를 이미 사용하는 동안 Azure AD Privileged Identity Management를 사용하도록 설정:  Azure AD Privileged Identity Management를 권한 있는 액세스 관리에 추가하면 주로 사용자 역할 또는 ID에 의해 정의된 Microsoft 365 외부의 데이터에 대한 권한 있는 액세스를 확장할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a2812-119">**Enabling Azure AD Privileged Identity Management while already using privileged access management in Office 365:**  Adding Azure AD Privileged Identity Management to privileged access management can extend privileged access to data outside of Microsoft 365 that's primarily defined by user roles or identity.</span></span>  

## <a name="privileged-access-management-architecture-and-process-flow"></a><span data-ttu-id="a2812-120">권한이 부여된 액세스 관리 아키텍처 및 프로세스 흐름</span><span class="sxs-lookup"><span data-stu-id="a2812-120">Privileged access management architecture and process flow</span></span>

<span data-ttu-id="a2812-121">다음의 각 프로세스 흐름에서는 권한이 부여된 액세스의 아키텍처와 Microsoft 365의 기하 도형, 감사 및 Exchange 관리 실행 영역과 상호 작용하는 방법을 간략하게 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="a2812-121">Each of the following process flows outline the architecture of privileged access and how it interacts with the Microsoft 365 substrate, auditing, and the Exchange Management runspace.</span></span>

### <a name="step-1-configure-a-privileged-access-policy"></a><span data-ttu-id="a2812-122">1단계: 권한 있는 액세스 정책 구성</span><span class="sxs-lookup"><span data-stu-id="a2812-122">Step 1: Configure a privileged access policy</span></span>

<span data-ttu-id="a2812-123">[Microsoft 365](https://admin.microsoft.com) 관리 센터 또는 Exchange 관리 PowerShell을 사용하여 권한 있는 액세스 정책을 구성할 때 Microsoft 365 기술에 권한 있는 액세스 기능 프로세스 및 정책 특성을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="a2812-123">When you configure a privileged access policy with the [Microsoft 365 admin center](https://admin.microsoft.com) or the Exchange Management PowerShell, you define the policy and the privileged access feature processes and the policy attributes in the Microsoft 365 substrate.</span></span> <span data-ttu-id="a2812-124">활동은 보안 준수 센터에 &amp; 기록됩니다.</span><span class="sxs-lookup"><span data-stu-id="a2812-124">The activities are logged in the Security &amp; Compliance Center.</span></span> <span data-ttu-id="a2812-125">이제 정책이 사용하도록 설정되어 승인을 위해 들어오는 요청을 처리할 준비가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a2812-125">The policy is now enabled and ready to handle incoming requests for approvals.</span></span>

![1단계: 정책 만들기](../media/pam-step1-policy-creation.jpg)

### <a name="step-2-access-request"></a><span data-ttu-id="a2812-127">2단계: 액세스 요청</span><span class="sxs-lookup"><span data-stu-id="a2812-127">Step 2: Access request</span></span>

<span data-ttu-id="a2812-128">Microsoft [365](https://admin.microsoft.com) 관리 센터 또는 Exchange 관리 PowerShell을 통해 사용자는 관리자 권한 또는 권한 있는 작업에 대한 액세스를 요청할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a2812-128">In the [Microsoft 365 admin center](https://admin.microsoft.com) or with the Exchange Management PowerShell, users can request access to elevated or privileged tasks.</span></span> <span data-ttu-id="a2812-129">권한 있는 액세스 기능은 구성된 권한 액세스 정책에 대한 처리 요청을 Microsoft 365로 보내고 보안 준수 센터 로그에 &amp; 활동을 기록합니다.</span><span class="sxs-lookup"><span data-stu-id="a2812-129">The privileged access feature sends the request to the Microsoft 365 substrate for processing against the configured privilege access policy and records the Activity in the Security &amp; Compliance Center logs.</span></span>

![2단계: 액세스 요청](../media/pam-step2-access-request.jpg)

### <a name="step-3-access-approval"></a><span data-ttu-id="a2812-131">3단계: 액세스 승인</span><span class="sxs-lookup"><span data-stu-id="a2812-131">Step 3: Access approval</span></span>

<span data-ttu-id="a2812-132">승인 요청이 생성되어 보류 중인 요청 알림이 승인자에 전자 메일로 전송됩니다.</span><span class="sxs-lookup"><span data-stu-id="a2812-132">An approval request is generated and the pending request notification is emailed to approvers.</span></span> <span data-ttu-id="a2812-133">승인되면 권한이 부여된 액세스 요청이 승인으로 처리되어 작업을 완료할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a2812-133">If approved, the privileged access request is processed as an approval and the task is ready to be completed.</span></span> <span data-ttu-id="a2812-134">거부된 경우 작업이 차단된 후 요청자에 대한 액세스 권한이 부여되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="a2812-134">If denied, the task is blocked and no access is granted to the requestor.</span></span> <span data-ttu-id="a2812-135">요청자에 전자 메일 메시지를 통해 요청 승인 또는 거부에 대한 알림이 제공됩니다.</span><span class="sxs-lookup"><span data-stu-id="a2812-135">The requestor is notified of the request approval or denial via email message.</span></span>

![3단계: 액세스 승인](../media/pam-step3-access-approval.jpg)

### <a name="step-4-access-processing"></a><span data-ttu-id="a2812-137">4단계: 액세스 처리</span><span class="sxs-lookup"><span data-stu-id="a2812-137">Step 4: Access processing</span></span>

<span data-ttu-id="a2812-138">승인된 요청의 경우 Exchange 관리 실행 영역이 작업을 처리합니다.</span><span class="sxs-lookup"><span data-stu-id="a2812-138">For an approved request, the task is processed by the Exchange Management runspace.</span></span> <span data-ttu-id="a2812-139">권한이 부여된 액세스 정책에 대해 승인을 확인하고 Microsoft 365 기하 도우미에서 처리합니다.</span><span class="sxs-lookup"><span data-stu-id="a2812-139">The approval is checked against the privileged access policy and processed by the Microsoft 365 substrate.</span></span> <span data-ttu-id="a2812-140">작업에 대한 모든 활동은 보안 준수 센터에 &amp; 기록됩니다.</span><span class="sxs-lookup"><span data-stu-id="a2812-140">All activity for the task is logged in the Security &amp; Compliance Center.</span></span>

![4단계: 액세스 처리](../media/pam-step4-access-processing.jpg)

## <a name="frequently-asked-questions"></a><span data-ttu-id="a2812-142">자주 묻는 질문</span><span class="sxs-lookup"><span data-stu-id="a2812-142">Frequently asked questions</span></span>

### <a name="what-skus-can-use-privileged-access-in-office-365"></a><span data-ttu-id="a2812-143">Office 365에서 권한 있는 액세스를 사용할 수 있는 SKUS는 무엇입니까?</span><span class="sxs-lookup"><span data-stu-id="a2812-143">What SKUs can use privileged access in Office 365?</span></span>

<span data-ttu-id="a2812-144">권한 있는 액세스 관리는 다양한 Microsoft 365 및 Office 365 구독 및 추가 기능에서 고객이 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a2812-144">Privileged access management is available for customers for a wide selection of Microsoft 365 and Office 365 subscriptions and add-ons.</span></span> <span data-ttu-id="a2812-145">자세한 내용은 권한 있는 액세스 [관리 시작을](privileged-access-management-configuration.md) 참조합니다.</span><span class="sxs-lookup"><span data-stu-id="a2812-145">See [Get started with privileged access management](privileged-access-management-configuration.md) for details.</span></span>

### <a name="when-will-privileged-access-support-office-365-workloads-beyond-exchange"></a><span data-ttu-id="a2812-146">권한 있는 액세스는 Exchange를 넘어 Office 365 작업을 언제 지원하나요?</span><span class="sxs-lookup"><span data-stu-id="a2812-146">When will privileged access support Office 365 workloads beyond Exchange?</span></span>

<span data-ttu-id="a2812-147">권한 있는 액세스 관리는 곧 다른 Office 365 워크로드에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a2812-147">Privileged access management will be available in other Office 365 workloads soon.</span></span> <span data-ttu-id="a2812-148">자세한 내용은 [Microsoft 365 로드맵을](https://www.microsoft.com/microsoft-365/roadmap) 방문합니다.</span><span class="sxs-lookup"><span data-stu-id="a2812-148">Visit the [Microsoft 365 Roadmap](https://www.microsoft.com/microsoft-365/roadmap) for more details.</span></span>

### <a name="my-organization-needs-more-than-30-privileged-access-policies-will-this-limit-be-increased"></a><span data-ttu-id="a2812-149">조직에 30개 이상의 권한이 부여된 액세스 정책이 필요합니까? 이 제한을 늘리시겠습니까?</span><span class="sxs-lookup"><span data-stu-id="a2812-149">My organization needs more than 30 privileged access policies, will this limit be increased?</span></span>

<span data-ttu-id="a2812-150">예. 조직당 권한 있는 액세스 정책 30개로 현재 제한을 높이는 것은 기능 로드맵에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a2812-150">Yes, raising the current limit of 30 privileged access policies per organization is on the feature roadmap.</span></span>

### <a name="do-i-need-to-be-a-global-admin-to-manage-privileged-access-in-office-365"></a><span data-ttu-id="a2812-151">Office 365에서 권한이 부여된 액세스를 관리하려면 전역 관리자로 설정해야 하나요?</span><span class="sxs-lookup"><span data-stu-id="a2812-151">Do I need to be a Global Admin to manage privileged access in Office 365?</span></span>

<span data-ttu-id="a2812-152">아니요. Office 365에서 권한이 부여된 액세스를 관리하는 계정에 Exchange 역할 관리 역할을 할당해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a2812-152">No, you need the Exchange Role Management role assigned to accounts that manage privileged access in Office 365.</span></span> <span data-ttu-id="a2812-153">역할 관리 역할을 독립 실행형 계정 권한으로 구성하지 않는 경우 전역 관리자 역할은 기본적으로 이 역할을 포함하며 권한 있는 액세스를 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a2812-153">If you don't want to configure the Role Management role as a stand-alone account permission, the Global Administrator role includes this role by default and can manage privileged access.</span></span> <span data-ttu-id="a2812-154">승인자 그룹에 포함된 사용자는 PowerShell을 통해 요청을 검토하고 승인하기 위해 전역 관리자 또는 역할 관리 역할을 할당할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="a2812-154">Users included in an approvers' group don't need to be a Global Admin or have the Role Management role assigned to review and approve requests with PowerShell.</span></span>

### <a name="how-is-privileged-access-management-related-to-customer-lockbox"></a><span data-ttu-id="a2812-155">고객 Lockbox와 관련된 권한 있는 액세스 관리는 어떻게 하나요?</span><span class="sxs-lookup"><span data-stu-id="a2812-155">How is privileged access management related to Customer Lockbox?</span></span>

<span data-ttu-id="a2812-156">[고객 Lockbox는](https://docs.microsoft.com/office365/admin/manage/customer-lockbox-requests) Microsoft가 데이터에 액세스할 때 조직에 대한 액세스 제어 수준을 허용합니다.</span><span class="sxs-lookup"><span data-stu-id="a2812-156">[Customer Lockbox](https://docs.microsoft.com/office365/admin/manage/customer-lockbox-requests) allows a level of access control for organizations when Microsoft accesses data.</span></span> <span data-ttu-id="a2812-157">권한이 부여된 액세스 관리를 사용하면 조직 내에서 모든 Microsoft 365 권한 작업을 세밀하게 제어할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a2812-157">Privileged access management allows granular access control within an organization for all Microsoft 365 privileged tasks.</span></span>

## <a name="ready-to-get-started"></a><span data-ttu-id="a2812-158">시작할 준비가 되나요?</span><span class="sxs-lookup"><span data-stu-id="a2812-158">Ready to get started?</span></span>

<span data-ttu-id="a2812-159">권한이 부여된 액세스 관리를 위한 조직 [구성을 시작하십시오.](privileged-access-management-configuration.md)</span><span class="sxs-lookup"><span data-stu-id="a2812-159">Start [configuring your organization for privileged access management](privileged-access-management-configuration.md).</span></span>

## <a name="learn-more"></a><span data-ttu-id="a2812-160">자세한 정보</span><span class="sxs-lookup"><span data-stu-id="a2812-160">Learn more</span></span>

[<span data-ttu-id="a2812-161">대화형 가이드: 권한이 부여된 액세스 관리를 사용하여 관리자 작업 모니터링 및 제어</span><span class="sxs-lookup"><span data-stu-id="a2812-161">Interactive guide: Monitor and control administrator tasks with privileged access management</span></span>](https://content.cloudguides.com/guides/Privileged%20Access%20Management)
