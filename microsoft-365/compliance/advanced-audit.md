---
title: Microsoft 365의 고급 감사
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- M365-security-compliance
- SPO_Content
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: Microsoft 365의 고급 감사는 조직에서 법의학 및 규정 준수 조사를 수행하는 데 도움이 되는 새로운 감사 기능을 제공합니다.
ms.openlocfilehash: e06e7f6330a36c8f98042fcce472b7baf6ef16ff
ms.sourcegitcommit: c2a36b16e354e20db5fd6275175ca856eae55bfc
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/12/2020
ms.locfileid: "41960244"
---
# <a name="advanced-audit-in-microsoft-365"></a><span data-ttu-id="91e92-103">Microsoft 365의 고급 감사</span><span class="sxs-lookup"><span data-stu-id="91e92-103">Advanced Audit in Microsoft 365</span></span>

<span data-ttu-id="91e92-104">Microsoft 365의 [통합 감사 기능](search-the-audit-log-in-security-and-compliance.md)은 조직에 Microsoft 365의 여러 서비스에서 다양한 유형의 감사 활동에 대한 가시성을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="91e92-104">The [unified auditing functionality](search-the-audit-log-in-security-and-compliance.md) in Microsoft 365 provides organizations with visibility into many types of audited activities across many different services in Microsoft 365.</span></span> <span data-ttu-id="91e92-105">이제 Microsoft 365의 고급 감사가 릴리스되면서 조직에서 법의학 및 규정 준수 조사를 수행하는 데 도움이 되는 새로운 감사 기능이 추가되었습니다.</span><span class="sxs-lookup"><span data-stu-id="91e92-105">Now with the release of Advanced Audit in Microsoft 365, we're adding new auditing capabilities that can help your organization with forensic and compliance investigations.</span></span>

> [!NOTE]
> <span data-ttu-id="91e92-106">Office 365 또는 Microsoft 365 Enterprise E5 구독이 있는 조직의 경우 고급 감사 기능을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="91e92-106">Advanced Audit is available for organizations with an Office 365 or Microsoft 365 Enterprise E5 subscription.</span></span> <span data-ttu-id="91e92-107">또한 감사 로그의 장기 보존 및 높은 값의 감사 이벤트의 경우와 같이 고급 감사 기능에 사용자별 라이선스가 필요한 경우 Microsoft 365 E5 규정 준수 추가 기능 구독을 사용자에게 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="91e92-107">Additionally, a Microsoft 365 E5 Compliance add-on subscription can be assigned to users for when per-user licensing is required for Advanced Audit features as is the case for long-term retention of audit logs and high-value audit events.</span></span>

<span data-ttu-id="91e92-108">이 문서는 이러한 고급 감사 기능에 대한 개요를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="91e92-108">This article provides an overview of these Advanced Audit capabilities.</span></span>

## <a name="long-term-retention-of-audit-logs"></a><span data-ttu-id="91e92-109">감사 로그의 장기 보존</span><span class="sxs-lookup"><span data-stu-id="91e92-109">Long-term retention of audit logs</span></span>

<span data-ttu-id="91e92-110">고급 감사는 1년 동안 모든 Exchange, SharePoint 및 Azure Active Directory 감사 레코드를 보존합니다.</span><span class="sxs-lookup"><span data-stu-id="91e92-110">Advanced Audit retains all Exchange, SharePoint, and Azure Active Directory audit records for one year.</span></span> <span data-ttu-id="91e92-111">이는 1년 동안의 **워크로드** 속성(활동이 발생한 서비스를 나타냄)에 대한 **Exchange**, \*\*SharePoint \*\* 또는 **AzureActiveDirectory** 값을 포함하는 모든 감사 레코드를 보유하는 기본 감사 로그 보유 정책에 의해 수행됩니다.</span><span class="sxs-lookup"><span data-stu-id="91e92-111">This is accomplished by a default audit log retention policy that retains any audit record that contains the value of **Exchange**, **SharePoint**, or **AzureActiveDirectory** for the **Workload** property (which indicates the service in which the activity occurred) for one year.</span></span> <span data-ttu-id="91e92-112">이는 진행 중인 법의학 또는 규정 준수 조사에 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="91e92-112">This can help with on-going forensic or compliance investigations.</span></span> <span data-ttu-id="91e92-113">자세한 정보는 [감사 로그 보존 정책 관리](audit-log-retention-policies.md#default-audit-log-retention-policy)의 "기본 감사 로그 보존 정책"섹션을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="91e92-113">For more information, see the "Default audit log retention policy" section in [Manage audit log retention policies](audit-log-retention-policies.md#default-audit-log-retention-policy).</span></span>

## <a name="audit-log-retention-policies"></a><span data-ttu-id="91e92-114">로그 보존 정책 감사</span><span class="sxs-lookup"><span data-stu-id="91e92-114">Audit log retention policies</span></span>

<span data-ttu-id="91e92-115">기본 감사 로그 보존 정책에 포함되지 않은 다른 서비스에서 생성된 모든 감사 레코드(이전 섹션에서 설명)는 90일 동안 보존됩니다.</span><span class="sxs-lookup"><span data-stu-id="91e92-115">All audit records generated in other services that aren't covered by the default audit log retention policy (described in the previous section) are retained for 90 days.</span></span> <span data-ttu-id="91e92-116">그러나 이제는 최대 1년 동안 다른 감사 레코드를 유지하기 위해 사용자 지정된 감사 로그 보존 정책을 생성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="91e92-116">However, now you can create customized audit log retention policies to retain other audit records for up to one year.</span></span> <span data-ttu-id="91e92-117">다음 기준 중 하나 이상을 기반으로 감사 레코드를 유지하는 정책을 생성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="91e92-117">You can create a policy to retain audit records based on one or more of the following criteria:</span></span>

- <span data-ttu-id="91e92-118">감사되는 활동이 발생하는 Microsoft 365 서비스</span><span class="sxs-lookup"><span data-stu-id="91e92-118">The Microsoft 365 service where the audited activities occur</span></span>

- <span data-ttu-id="91e92-119">감사되는 구체적 활동</span><span class="sxs-lookup"><span data-stu-id="91e92-119">Specific audited activities</span></span>

- <span data-ttu-id="91e92-120">감사되는 활동을 수행하는 사용자</span><span class="sxs-lookup"><span data-stu-id="91e92-120">The user who performs an audited activity</span></span>

<span data-ttu-id="91e92-121">특정 정책이 다른 정책보다 우선하도록 정책 및 우선순위 수준과 일치하는 감사 레코드에 대한 보존 기간을 지정할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="91e92-121">You can also specify how long to retain audit records that match the policy and a priority level so that specific policies will take priority over other policies.</span></span> <span data-ttu-id="91e92-122">또한 조직의 일부 또는 모든 사용자에 대해 Exchange, SharePoint 또는 Azure Active Directory 감사 레코드를 1년 미만 동안 유지해야하는 경우 사용자 지정 감사 로그 보존 정책이 기본 감사 보존 정책보다 우선합니다.</span><span class="sxs-lookup"><span data-stu-id="91e92-122">Also note that any custom audit log retention policy will take precedence over the default audit retention policy in case you need retain Exchange, SharePoint, or Azure Active Directory audit records for less than a year for some or all the users in your organization.</span></span> <span data-ttu-id="91e92-123">자세한 내용은 [감사 로그 보존 정책 관리](audit-log-retention-policies.md)를 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="91e92-123">For more information, see [Manage audit log retention policies](audit-log-retention-policies.md).</span></span>

## <a name="high-value-audit-events"></a><span data-ttu-id="91e92-124">가치가 높은 감사 이벤트</span><span class="sxs-lookup"><span data-stu-id="91e92-124">High-value audit events</span></span>

<span data-ttu-id="91e92-125">가치가 높은 보안 및 준수 관련 감사 이벤트는 가능한 위반사항 또는 기타 법의학 관련 조사를 조사하는 데 도움이 되는 감사 이벤트입니다.</span><span class="sxs-lookup"><span data-stu-id="91e92-125">High-value security- and compliance-related audit events are ones that can help you investigate possible breaches or other forensic-related investigations.</span></span> <span data-ttu-id="91e92-126">Microsoft가 발표하는 첫 번째 고 가치 이벤트는 *MailItemsAccessed* 사서함 감사 이벤트입니다.</span><span class="sxs-lookup"><span data-stu-id="91e92-126">The first such high-value event that we're releasing is the *MailItemsAccessed* mailbox auditing event.</span></span> <span data-ttu-id="91e92-127">이 이벤트는 메일 프로토콜 및 클라이언트가 메일 데이터에 액세스할 때 트리거됩니다.</span><span class="sxs-lookup"><span data-stu-id="91e92-127">This event is trigger when mail data is accessed by mail protocols and clients.</span></span> <span data-ttu-id="91e92-128">MailItemsAccessed 이벤트는 조사자가 데이터 유출을 식별하고 손상되었을 수 있는 메시지 범위를 결정하는 데 도움이됩니다.</span><span class="sxs-lookup"><span data-stu-id="91e92-128">The MailItemsAccessed event can help investigators identify data breaches and determine the scope of messages that may have been compromised.</span></span> <span data-ttu-id="91e92-129">공격자가 전자 메일 메시지에 액세스한 경우 실제로 메시지를 읽었다는 명시적인 신호가 없는 경우에도 MailItemsAccessed 이벤트가 트리거됩니다(즉, 바인딩 또는 동기화를 통한 액세스 유형이 감사 레코드에 기록됨).</span><span class="sxs-lookup"><span data-stu-id="91e92-129">If an attacker gained access to email messages, MailItemsAccessed event will be triggered even if there is no explicit signal that it was actually read (in other words, the type of access such as via bind or sync is recorded in the audit record).</span></span>

<span data-ttu-id="91e92-130">새로운 MailItemsAccessed 사서함 작업은 Exchange Online의 사서함 감사 로깅에서 MessageBind를 대체하고 다음과 같은 향상된 기능을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="91e92-130">The new MailItemsAccessed mailbox action replaces MessageBind in mailbox auditing logging in Exchange Online and provides these improvements:</span></span>

- <span data-ttu-id="91e92-131">MessageBind는 AuditAdmin 사용자 로그온 유형에 대해서만 구성 할 수 있었습니다. 대리인 또는 소유자 조치에는 적용되지 않았습니다.</span><span class="sxs-lookup"><span data-stu-id="91e92-131">MessageBind was only configurable for AuditAdmin user logon type; it did not apply to delegate or owner actions.</span></span> <span data-ttu-id="91e92-132">MailItemsAccessed는 모든 로그온 유형에 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="91e92-132">MailItemsAccessed applies to all logon types.</span></span>

- <span data-ttu-id="91e92-133">MessageBind는 메일 클라이언트만 액세스할 수 있었습니다.</span><span class="sxs-lookup"><span data-stu-id="91e92-133">MessageBind only covered access by a mail client.</span></span> <span data-ttu-id="91e92-134">MessageBind는 동기화 활동에는 적용되지 않았습니다.</span><span class="sxs-lookup"><span data-stu-id="91e92-134">It didn't apply to sync activities.</span></span> <span data-ttu-id="91e92-135">MailItemsAccessed 이벤트는 바인딩 및 동기화 액세스 유형에 의해 트리거됩니다.</span><span class="sxs-lookup"><span data-stu-id="91e92-135">MailItemsAccessed events are triggered by both bind and sync access types.</span></span>

- <span data-ttu-id="91e92-136">MessageBind 작업은 동일한 전자 메일 메시지에 액세스할 때 여러 감사 레코드가 생성되어 "노이즈" 감사가 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="91e92-136">MessageBind actions would trigger multiple audit records to be created when the same email message was accessed, which resulted in auditing "noise".</span></span> <span data-ttu-id="91e92-137">반대로 MailItemsAccessed 이벤트는 더 적은 감사 레코드로 집계됩니다.</span><span class="sxs-lookup"><span data-stu-id="91e92-137">In contrast, MailItemsAccessed events are aggregated in fewer audit records.</span></span>

<span data-ttu-id="91e92-138">사서함 감사 로깅에 대한 자세한 내용은 [사서함 감사 관리](enable-mailbox-auditing.md)를 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="91e92-138">For more information about mailbox auditing logging, see [Manage mailbox auditing](enable-mailbox-auditing.md).</span></span>

## <a name="high-bandwidth-access-to-the-office-365-management-activity-api"></a><span data-ttu-id="91e92-139">Office 365 관리 활동 API에 대한 고 대역폭 액세스</span><span class="sxs-lookup"><span data-stu-id="91e92-139">High-bandwidth access to the Office 365 Management Activity API</span></span>

<span data-ttu-id="91e92-140">Office 365 관리 활동 API를 통해 감사 로그에 액세스하는 조직은 게시자 수준에서 제한을 스로틀링하여 제한되었습니다.</span><span class="sxs-lookup"><span data-stu-id="91e92-140">Organizations that access auditing logs through the Office 365 Management Activity API were restricted by throttling limits at the publisher level.</span></span> <span data-ttu-id="91e92-141">이는 여러 고객을 대신하여 데이터를 가져 오는 게시자의 경우 모든 고객이 한도를 공유했음을 의미합니다.</span><span class="sxs-lookup"><span data-stu-id="91e92-141">This means that for a publisher pulling data on behalf of multiple customers, the limit was shared by all those customers.</span></span>

<span data-ttu-id="91e92-142">고급 감사가 릴리스됨에 따라 Microsoft는 게시자 수준 제한에서 테넌트 수준 제한으로 전환하고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="91e92-142">With the release of Advanced Audit, we're moving from a publisher-level limit to a tenant-level limit.</span></span> <span data-ttu-id="91e92-143">결과적으로 각 조직은 감사 데이터에 액세스하기 위해 자체 할당된 대역폭 할당량을 얻게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="91e92-143">The result is that each organization will get their own fully allocated bandwidth quota to access their auditing data.</span></span> <span data-ttu-id="91e92-144">대역폭은 사전 정의된 정적 제한이 아니지만 조직의 자리 수를 포함하여 E5 조직이 E5 이외의 조직보다 더 많은 대역폭을 갖도록 여러 요인을 조합하여 모델링되었습니다.</span><span class="sxs-lookup"><span data-stu-id="91e92-144">The bandwidth is not a static, predefined limit but is modeled on a combination of factors including the number of seats in the organization and that E5 organizations will get more bandwidth than non-E5 organizations.</span></span>

<span data-ttu-id="91e92-145">모든 조직에는 처음에 분당 2,000건의 요청 기준이 할당됩니다.</span><span class="sxs-lookup"><span data-stu-id="91e92-145">All organizations are initially allocated a baseline of 2,000 requests per minute.</span></span> <span data-ttu-id="91e92-146">이 한도는 조직의 라이선스 수와 라이선스 구독에 따라 동적으로 증가합니다.</span><span class="sxs-lookup"><span data-stu-id="91e92-146">This limit will dynamically increase depending on an organization's seat count and their licensing subscription.</span></span> <span data-ttu-id="91e92-147">E5 조직은 E5 이외의 조직보다 약 2배의 대역폭을 얻게됩니다.</span><span class="sxs-lookup"><span data-stu-id="91e92-147">E5 organizations will get approximately twice as much bandwidth as non-E5 organizations.</span></span> <span data-ttu-id="91e92-148">또한 서비스 상태를 보호하기 위해 최대 대역폭에 제한이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="91e92-148">There will also be cap on the maximum bandwidth to protect the health of the service.</span></span>

<span data-ttu-id="91e92-149">자세한 내용은 [Office 365 관리 활동 API 참조](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-reference#api-throttling)의 "API 조절"섹션을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="91e92-149">For more information, see the "API throttling" section in [Office 365 Management Activity API reference](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-reference#api-throttling).</span></span>
