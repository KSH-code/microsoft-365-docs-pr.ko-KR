---
title: 위협에 대한 보호
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: Admin
ms.topic: overview
localization_priority: Normal
ms.date: 09/08/2020
search.appverid:
- MOE150
- MET150
ms.assetid: b10023f6-f30f-45d3-b3ad-b71aa4aa0d58
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
description: 관리자는 조직의 위협 방지에 대해 Microsoft 365 조직에 대해 사용하는 방법을 구성할 수 있습니다.
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 3381ce66433f1f4e32f0251c45601e3cb84865b6
ms.sourcegitcommit: f780de91bc00caeb1598781e0076106c76234bad
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/19/2021
ms.locfileid: "52538726"
---
# <a name="protect-against-threats"></a><span data-ttu-id="feb86-103">위협에 대한 보호</span><span class="sxs-lookup"><span data-stu-id="feb86-103">Protect against threats</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="feb86-104">**적용 대상**</span><span class="sxs-lookup"><span data-stu-id="feb86-104">**Applies to**</span></span>
- [<span data-ttu-id="feb86-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="feb86-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="feb86-106">Office 365용 Microsoft Defender 플랜 1 및 플랜 2</span><span class="sxs-lookup"><span data-stu-id="feb86-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="feb86-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="feb86-107">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

<span data-ttu-id="feb86-108">다음은 2016에 대한 Defender의 구성을 청크로 Office 365 빠른 시작 가이드입니다.</span><span class="sxs-lookup"><span data-stu-id="feb86-108">Here's a quick-start guide that breaks the configuration of Defender for Office 365 into chunks.</span></span> <span data-ttu-id="feb86-109">새로운 위협 방지 기능을 Office 365 시작 위치를 잘 모를 수도 있으며, 를 수행하여 가장 잘 알 수 있는 경우 이 지침을 검사 목록 및 시작점으로 사용하세요.</span><span class="sxs-lookup"><span data-stu-id="feb86-109">If you're new to threat protection features in Office 365, not sure where to begin, or if you learn best by *doing*, use this guidance as a checklist and a starting point.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="feb86-110">**각 정책 종류에** 대한 초기 권장 설정이 포함되어 있습니다. 그러나 많은 옵션을 사용할 수 있으며 특정 조직의 요구에 맞게 설정을 조정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="feb86-110">**Initial recommended settings are included for each kind of policy; however, many options are available, and you can adjust your settings to meet your specific organization's needs**.</span></span> <span data-ttu-id="feb86-111">정책 또는 변경 사항이 데이터 센터를 통해 작동하도록 약 30분 동안 허용합니다.</span><span class="sxs-lookup"><span data-stu-id="feb86-111">Allow approximately 30 minutes for your policies or changes to work their way through your datacenter.</span></span>

## <a name="requirements"></a><span data-ttu-id="feb86-112">요구 사항</span><span class="sxs-lookup"><span data-stu-id="feb86-112">Requirements</span></span>

### <a name="subscriptions"></a><span data-ttu-id="feb86-113">구독</span><span class="sxs-lookup"><span data-stu-id="feb86-113">Subscriptions</span></span>

<span data-ttu-id="feb86-114">위협 방지 기능은 모든 *Microsoft* 또는 Office 365 포함되어 있습니다. 그러나 일부 구독에는 고급 기능이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="feb86-114">Threat protection features are included in *all* Microsoft or Office 365 subscriptions; however, some subscriptions have advanced features.</span></span> <span data-ttu-id="feb86-115">아래 표에는 이 문서에 포함된 보호 기능과 최소 구독 요구 사항이 나열됩니다.</span><span class="sxs-lookup"><span data-stu-id="feb86-115">The table below lists the protection features included in this article together with the minimum subscription requirements.</span></span>

> [!TIP]
> <span data-ttu-id="feb86-116">감사를 켜는 지시 이외에 단계는 **EOP(맬웨어** 방지) 의 일부로 표시된 맬웨어 방지, 피싱 방지 및 스팸 방지를 Office 365 Exchange Online Protection 있습니다. </span><span class="sxs-lookup"><span data-stu-id="feb86-116">Notice that, beyond the directions to turn on auditing, *steps* start anti-malware, anti-phishing, and anti-spam, which are marked as part of Office 365 Exchange Online Protection (**EOP**).</span></span> <span data-ttu-id="feb86-117">(에 대한 **Defender** for Office 365) EOP를 포함하고 빌드할 때까지 이 문서에서 이 Office 365 이상한 것처럼 보일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="feb86-117">This can seem odd in an Defender for Office 365 article, until you remember (**Defender for Office 365**) contains, and builds on, EOP.</span></span>

****

|<span data-ttu-id="feb86-118">보호 유형</span><span class="sxs-lookup"><span data-stu-id="feb86-118">Protection type</span></span>|<span data-ttu-id="feb86-119">구독 요구 사항</span><span class="sxs-lookup"><span data-stu-id="feb86-119">Subscription requirement</span></span>|
|---|---|
|<span data-ttu-id="feb86-120">감사 로깅(보고 목적으로)</span><span class="sxs-lookup"><span data-stu-id="feb86-120">Audit logging (for reporting purposes)</span></span>|[<span data-ttu-id="feb86-121">Exchange Online</span><span class="sxs-lookup"><span data-stu-id="feb86-121">Exchange Online</span></span>](/office365/servicedescriptions/exchange-online-service-description/exchange-online-service-description)|
|<span data-ttu-id="feb86-122">맬웨어 방지 보호 기능</span><span class="sxs-lookup"><span data-stu-id="feb86-122">Anti-malware protection</span></span>|<span data-ttu-id="feb86-123">[](/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description) **Exchange Online Protection(EOP)**</span><span class="sxs-lookup"><span data-stu-id="feb86-123">[Exchange Online Protection](/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description) (**EOP**)</span></span>|
|<span data-ttu-id="feb86-124">피싱 방지 보호 기능</span><span class="sxs-lookup"><span data-stu-id="feb86-124">Anti-phishing protection</span></span>|[<span data-ttu-id="feb86-125">EOP</span><span class="sxs-lookup"><span data-stu-id="feb86-125">EOP</span></span>](/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description)|
|<span data-ttu-id="feb86-126">스팸 방지 보호 기능</span><span class="sxs-lookup"><span data-stu-id="feb86-126">Anti-spam protection</span></span>|[<span data-ttu-id="feb86-127">EOP</span><span class="sxs-lookup"><span data-stu-id="feb86-127">EOP</span></span>](/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description)|
|<span data-ttu-id="feb86-128">제로 아워 자동 제거(전자 메일용)</span><span class="sxs-lookup"><span data-stu-id="feb86-128">Zero-hour auto purge (for email)</span></span>|[<span data-ttu-id="feb86-129">EOP</span><span class="sxs-lookup"><span data-stu-id="feb86-129">EOP</span></span>](/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description)|
|<span data-ttu-id="feb86-130">전자 메일 및 전자 메일의 악의적인 URL 및 Office 보호(안전한 링크 및 안전한 첨부 파일)</span><span class="sxs-lookup"><span data-stu-id="feb86-130">Protection from malicious URLs and files in email and Office documents (Safe Links and Safe Attachments)</span></span>|[<span data-ttu-id="feb86-131">Office 365용 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="feb86-131">Microsoft Defender for Office 365</span></span>](/office365/servicedescriptions/office-365-advanced-threat-protection-service-description)|
|<span data-ttu-id="feb86-132">작업 부하, SharePoint, OneDrive 및 Microsoft Teams 설정</span><span class="sxs-lookup"><span data-stu-id="feb86-132">Turn on Safe Attachments for SharePoint, OneDrive, and Microsoft Teams workloads</span></span>|[<span data-ttu-id="feb86-133">Office 365용 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="feb86-133">Microsoft Defender for Office 365</span></span>](turn-on-mdo-for-spo-odb-and-teams.md)|
|<span data-ttu-id="feb86-134">지능형 피싱 방지 보호</span><span class="sxs-lookup"><span data-stu-id="feb86-134">Advanced anti-phishing protection</span></span>|[<span data-ttu-id="feb86-135">Office 365용 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="feb86-135">Microsoft Defender for Office 365</span></span>](/office365/servicedescriptions/office-365-advanced-threat-protection-service-description)|

### <a name="roles-and-permissions"></a><span data-ttu-id="feb86-136">역할 및 사용 권한</span><span class="sxs-lookup"><span data-stu-id="feb86-136">Roles and permissions</span></span>

<span data-ttu-id="feb86-137">정책에 대해 Defender를 Office 365 보안 및 준수 센터에서 [적절한 역할을 & 합니다.](/office365/servicedescriptions/office-365-platform-service-description/office-365-securitycompliance-center)</span><span class="sxs-lookup"><span data-stu-id="feb86-137">To configure Defender for Office 365 policies, you must be assigned an appropriate role in the [Security & Compliance Center](/office365/servicedescriptions/office-365-platform-service-description/office-365-securitycompliance-center).</span></span> <span data-ttu-id="feb86-138">아래 표에서 이러한 작업을 수행할 수 있는 역할을 확인하세요.</span><span class="sxs-lookup"><span data-stu-id="feb86-138">Take a look at the table below for roles that can do these actions.</span></span>

****

|<span data-ttu-id="feb86-139">역할 또는 역할 그룹</span><span class="sxs-lookup"><span data-stu-id="feb86-139">Role or role group</span></span>|<span data-ttu-id="feb86-140">자세한 내용을 알아보는 위치</span><span class="sxs-lookup"><span data-stu-id="feb86-140">Where to learn more</span></span>|
|---|---|
|<span data-ttu-id="feb86-141">전역 관리자</span><span class="sxs-lookup"><span data-stu-id="feb86-141">global administrator</span></span>|[<span data-ttu-id="feb86-142">Microsoft 365 관리자 역할 정보</span><span class="sxs-lookup"><span data-stu-id="feb86-142">About Microsoft 365 admin roles</span></span>](../../admin/add-users/about-admin-roles.md)|
|<span data-ttu-id="feb86-143">보안 관리자</span><span class="sxs-lookup"><span data-stu-id="feb86-143">Security Administrator</span></span>|[<span data-ttu-id="feb86-144">Azure Active Directory의 관리자 역할 권한</span><span class="sxs-lookup"><span data-stu-id="feb86-144">Administrator role permissions in Azure Active Directory</span></span>](/azure/active-directory/users-groups-roles/directory-assign-admin-roles)|
|<span data-ttu-id="feb86-145">Exchange Online 조직 관리</span><span class="sxs-lookup"><span data-stu-id="feb86-145">Exchange Online Organization Management</span></span>|[<span data-ttu-id="feb86-146">Exchange Online의 사용 권한</span><span class="sxs-lookup"><span data-stu-id="feb86-146">Permissions in Exchange Online</span></span>](/exchange/permissions-exo/permissions-exo) <p> <span data-ttu-id="feb86-147">및</span><span class="sxs-lookup"><span data-stu-id="feb86-147">and</span></span> <p> [<span data-ttu-id="feb86-148">Exchange Online PowerShell</span><span class="sxs-lookup"><span data-stu-id="feb86-148">Exchange Online PowerShell</span></span>](/powershell/exchange/exchange-online-powershell)|
|

<span data-ttu-id="feb86-149">자세한 내용은 [Security & Compliance Center의 사용 권한을 참조합니다.](permissions-in-the-security-and-compliance-center.md)</span><span class="sxs-lookup"><span data-stu-id="feb86-149">To learn more, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

## <a name="before-you-begin-turn-on-audit-logging-for-reporting-and-investigation"></a><span data-ttu-id="feb86-150">시작하기 전에 보고 및 조사에 대한 감사 로깅 켜기</span><span class="sxs-lookup"><span data-stu-id="feb86-150">Before you begin, turn on Audit logging for reporting and investigation</span></span>

<span data-ttu-id="feb86-151">감사 로깅을 조기 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="feb86-151">Start your audit logging early.</span></span> <span data-ttu-id="feb86-152">다음과 같은 특정 단계에 대한 감사를 **ON으로** 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="feb86-152">You'll need auditing to be **ON** for certain of the steps that follow.</span></span> <span data-ttu-id="feb86-153">감사 로깅은 을(를) 포함 하는 [구독에서 사용할 Exchange Online.](/office365/servicedescriptions/exchange-online-service-description/exchange-online-service-description)</span><span class="sxs-lookup"><span data-stu-id="feb86-153">Audit logging is available in subscriptions that include [Exchange Online](/office365/servicedescriptions/exchange-online-service-description/exchange-online-service-description).</span></span> <span data-ttu-id="feb86-154">보안 대시보드, 전자 메일 보안 보고서 [](security-dashboard.md)및 탐색기 등의 위협 [](threat-explorer.md)방지 보고서에서 데이터를 확인하려면 감사 로깅이 에 있어야 *합니다.* [](view-email-security-reports.md)</span><span class="sxs-lookup"><span data-stu-id="feb86-154">In order to view data in threat protection reports, such as the [Security Dashboard](security-dashboard.md), [email security reports](view-email-security-reports.md), and [Explorer](threat-explorer.md), audit logging must be *On*.</span></span> <span data-ttu-id="feb86-155">자세한 내용은 감사 로그 검색 켜기 또는 [끄기 를 참조합니다.](../../compliance/turn-audit-log-search-on-or-off.md)</span><span class="sxs-lookup"><span data-stu-id="feb86-155">To learn more, see [Turn audit log search on or off](../../compliance/turn-audit-log-search-on-or-off.md).</span></span>

## <a name="part-1---anti-malware-protection"></a><span data-ttu-id="feb86-156">1부 - 맬웨어 방지 보호</span><span class="sxs-lookup"><span data-stu-id="feb86-156">Part 1 - Anti-malware protection</span></span>

<span data-ttu-id="feb86-157">[맬웨어 방지 보호는](anti-malware-protection.md) EOP를 포함 하는 [구독에서 사용할 수 있습니다.](/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description)</span><span class="sxs-lookup"><span data-stu-id="feb86-157">[Anti-malware protection](anti-malware-protection.md) is available in subscriptions that include [EOP](/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description).</span></span>

1. <span data-ttu-id="feb86-158">보안 및 [& 센터에서](https://protection.office.com)위협 관리 정책 맬웨어 방지  \>  \> **를 선택 합니다.**</span><span class="sxs-lookup"><span data-stu-id="feb86-158">In the [Security & Compliance Center](https://protection.office.com), choose **Threat management** \> **Policy** \> **Anti-malware**.</span></span>

2. <span data-ttu-id="feb86-159">기본 정책을 **두 번** 클릭한 다음 설정을 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="feb86-159">Double-click the **Default** policy, and then choose **settings**.</span></span>

3. <span data-ttu-id="feb86-160">다음 설정을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="feb86-160">Specify the following settings:</span></span>

    - <span data-ttu-id="feb86-161">**맬웨어 검색 응답 섹션에서** 기본 설정을 **아니요로 지정합니다.**</span><span class="sxs-lookup"><span data-stu-id="feb86-161">In the **Malware Detection Response** section, keep the default setting of **No**.</span></span>

    - <span data-ttu-id="feb86-162">일반 **첨부 파일 형식 필터 섹션에서** 을 **선택 합니다.**</span><span class="sxs-lookup"><span data-stu-id="feb86-162">In the **Common Attachment Types Filter** section, choose **On**.</span></span>

4. <span data-ttu-id="feb86-163">**저장** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="feb86-163">Click **Save**.</span></span>

<span data-ttu-id="feb86-164">맬웨어 방지 정책 옵션에 대한 자세한 내용은 맬웨어 방지 정책 [구성을 참조하세요.](configure-anti-malware-policies.md)</span><span class="sxs-lookup"><span data-stu-id="feb86-164">To learn more about anti-malware policy options, see [Configure anti-malware policies](configure-anti-malware-policies.md).</span></span>

## <a name="part-2---anti-phishing-protection"></a><span data-ttu-id="feb86-165">2부 - 피싱 방지 보호 기능</span><span class="sxs-lookup"><span data-stu-id="feb86-165">Part 2 - Anti-phishing protection</span></span>

<span data-ttu-id="feb86-166">[피싱 방지 보호는](anti-phishing-protection.md) EOP를 포함 하는 [구독에서 사용할 수 있습니다.](/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description)</span><span class="sxs-lookup"><span data-stu-id="feb86-166">[Anti-phishing protection](anti-phishing-protection.md) is available in subscriptions that include [EOP](/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description).</span></span> <span data-ttu-id="feb86-167">고급 피싱 방지 보호는 에 대한 [Defender에서](/office365/servicedescriptions/office-365-advanced-threat-protection-service-description)사용할 수 Office 365.</span><span class="sxs-lookup"><span data-stu-id="feb86-167">Advanced anti-phishing protection is available in [Defender for Office 365](/office365/servicedescriptions/office-365-advanced-threat-protection-service-description).</span></span>

<span data-ttu-id="feb86-168">다음 절차에서는 Microsoft Defender에서 피싱 방지 정책을 구성하는 방법을 Office 365.</span><span class="sxs-lookup"><span data-stu-id="feb86-168">The following procedure describes how to configure an anti-phishing policy in Microsoft Defender for Office 365.</span></span> <span data-ttu-id="feb86-169">단계는 EOP에서 피싱 방지 정책을 구성하는 경우와 비슷합니다.</span><span class="sxs-lookup"><span data-stu-id="feb86-169">The steps are similar for configuring an anti-phishing policy in EOP.</span></span>

1. <span data-ttu-id="feb86-170">보안 및 [& 센터에서](https://protection.office.com)위협 **관리** 정책 피싱 방지 \>  \> **를 선택 합니다.**</span><span class="sxs-lookup"><span data-stu-id="feb86-170">In the [Security & Compliance Center](https://protection.office.com), choose **Threat management** \> **Policy** \> **Anti-phishing**.</span></span>

2. <span data-ttu-id="feb86-171">기본 **정책을 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="feb86-171">Click **Default policy**.</span></span>

3. <span data-ttu-id="feb86-172">가장 **섹션에서** 편집을 **클릭하고** 다음 설정을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="feb86-172">In the **Impersonation** section, click **Edit**, and then specify the following settings:</span></span>

   - <span data-ttu-id="feb86-173">보호할 **사용자 추가 탭에서** 보호 *켜기를* 니다.</span><span class="sxs-lookup"><span data-stu-id="feb86-173">On the **Add users to protect** tab, turn *On* protection.</span></span> <span data-ttu-id="feb86-174">그런 다음 조직의 보드 구성원, CEO, CFO 및 기타 고위 리더와 같은 사용자를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="feb86-174">Then add users, such as your organization's board members, your CEO, CFO, and other senior leaders.</span></span> <span data-ttu-id="feb86-175">개별 전자 메일 주소를 입력하거나 클릭하여 목록을 표시할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="feb86-175">(You can type an individual email address, or click to display a list.)</span></span>

   - <span data-ttu-id="feb86-176">보호할 **도메인 추가 탭에서** 소유한 도메인이 자동으로 **포함을 으로 니다.**</span><span class="sxs-lookup"><span data-stu-id="feb86-176">On the **Add domains to protect** tab, turn on **Automatically include the domains I own**.</span></span> <span data-ttu-id="feb86-177">사용자 지정 도메인이 있는 경우 지금 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="feb86-177">If you have custom domains, add them now.</span></span>

   - <span data-ttu-id="feb86-178">작업 **탭에서** 가장된 사용자 및 가장된 도메인 옵션 둘 다에 대한 메시지  **검역을** 선택합니다. </span><span class="sxs-lookup"><span data-stu-id="feb86-178">On the **Actions** tab, select **Quarantine the message** for both the **impersonated user** and **impersonated domain** options.</span></span> <span data-ttu-id="feb86-179">또한 가장 보안 팁을 켜세요.</span><span class="sxs-lookup"><span data-stu-id="feb86-179">Also, turn on impersonation safety tips.</span></span>

   - <span data-ttu-id="feb86-180">사서함 **인텔리전스 탭에서** 사서함 인텔리전스가 켜져 있는지 확인한 다음 사서함 인텔리전스 기반 가장 보호를 켜야 합니다.</span><span class="sxs-lookup"><span data-stu-id="feb86-180">On the **Mailbox intelligence** tab, make sure mailbox intelligence is turned on and turn on mailbox intelligence-based impersonation protection.</span></span> <span data-ttu-id="feb86-181">가장된  사용자가 전자 메일을 보낸 경우 목록에서 메시지 **검역을 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="feb86-181">In the **If email is sent by an impersonated user** list, choose **Quarantine the message**.</span></span>

   - <span data-ttu-id="feb86-182">신뢰할 **수 있는 보낸** 사람 및 도메인 추가 탭에서 추가할 신뢰할 수 있는 보낸 사람 또는 도메인을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="feb86-182">On the **Add trusted senders and domains** tab, specify any trusted senders or domains that you want to add.</span></span>

   - <span data-ttu-id="feb86-183">**설정을** **검토한** 후 설정 검토 탭에 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="feb86-183">**Save** on the **Review your settings** tab after you've reviewed your settings.</span></span>

4. <span data-ttu-id="feb86-184">**스푸핑 섹션에서** 편집을 **클릭하고** 다음 설정을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="feb86-184">In the **Spoof** section, click **Edit**, and then specify the following settings:</span></span>

   - <span data-ttu-id="feb86-185">스푸핑 필터 **설정 탭에서** 스푸핑 방지 보호가 켜져 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="feb86-185">On the **Spoofing filter settings** tab, make sure anti-spoofing protection is turned on.</span></span>

   - <span data-ttu-id="feb86-186">작업 **탭에서** 메시지 **를 Quarantine (을) 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="feb86-186">On the **Actions** tab, choose **Quarantine the message**.</span></span>

   - <span data-ttu-id="feb86-187">**변경** 내용을  검토한 후 설정 검토 탭에 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="feb86-187">**Save** on the **Review your settings** tab after you have reviewed your changes.</span></span> <span data-ttu-id="feb86-188">(변경하지 않은 경우 **취소**.)</span><span class="sxs-lookup"><span data-stu-id="feb86-188">(If you didn't make any changes, **Cancel**.)</span></span>

5. <span data-ttu-id="feb86-189">기본 정책 설정 페이지를 닫습니다.</span><span class="sxs-lookup"><span data-stu-id="feb86-189">Close the default policy settings page.</span></span>

<span data-ttu-id="feb86-190">피싱 방지 정책 옵션에 대한 자세한 내용은 Microsoft [Defender에서](configure-atp-anti-phishing-policies.md)피싱 방지 정책 구성을 Office 365.</span><span class="sxs-lookup"><span data-stu-id="feb86-190">To learn more about your anti-phishing policy options, see [Configure anti-phishing policies in Microsoft Defender for Office 365](configure-atp-anti-phishing-policies.md).</span></span>

## <a name="part-3---anti-spam-protection"></a><span data-ttu-id="feb86-191">3부 - 스팸 방지 보호</span><span class="sxs-lookup"><span data-stu-id="feb86-191">Part 3 - Anti-spam protection</span></span>

<span data-ttu-id="feb86-192">[스팸 방지 보호는](anti-spam-protection.md) EOP를 포함 하는 [구독에서 사용할 수 있습니다.](/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description)</span><span class="sxs-lookup"><span data-stu-id="feb86-192">[Anti-spam protection](anti-spam-protection.md) is available in subscriptions that include [EOP](/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description).</span></span>

1. <span data-ttu-id="feb86-193">보안 및 [& 센터에서](https://protection.office.com)위협 **관리** 정책 스팸 방지 \>  \> **를 선택 합니다.**</span><span class="sxs-lookup"><span data-stu-id="feb86-193">In the [Security & Compliance Center](https://protection.office.com), choose **Threat management** \> **Policy** \> **Anti-spam**.</span></span>

2. <span data-ttu-id="feb86-194">사용자 지정 **탭에서** 사용자 지정 설정을 니다.</span><span class="sxs-lookup"><span data-stu-id="feb86-194">On the **Custom** tab, turn on Custom settings.</span></span>

3. <span data-ttu-id="feb86-195">기본 **스팸 필터 정책을 확장하고** 정책 **편집을** 클릭한 후 다음 설정을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="feb86-195">Expand **Default spam filter policy**, click **Edit policy**, and then specify the following settings:</span></span>

   - <span data-ttu-id="feb86-196">스팸 **및 대량 작업** 섹션에서 임계값을 5 또는 6으로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="feb86-196">In the **Spam and bulk actions** section, set the threshold to a value of 5 or 6.</span></span>

   - <span data-ttu-id="feb86-197">허용 **목록 섹션에서** 허용된 보낸 사람 및 도메인을 검토(및/또는 편집)합니다.</span><span class="sxs-lookup"><span data-stu-id="feb86-197">In the **Allow lists** section, review (and/or edit) your allowed senders and domains.</span></span>

4. <span data-ttu-id="feb86-198">**저장** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="feb86-198">Click **Save**.</span></span>

<span data-ttu-id="feb86-199">스팸 방지 정책 옵션에 대한 자세한 내용은 [EOP에서 스팸 방지 정책 구성을 참조하세요.](configure-your-spam-filter-policies.md)</span><span class="sxs-lookup"><span data-stu-id="feb86-199">To learn more about your anti-spam policy options, see [Configure anti-spam policies in EOP](configure-your-spam-filter-policies.md).</span></span>

## <a name="part-4---protection-from-malicious-urls-and-files-safe-links-and-safe-attachments-in-defender-for-office-365"></a><span data-ttu-id="feb86-200">4부 - 악의적인 URL 및 파일로부터 보호(안전한 링크 및 안전한 첨부 파일 for Office 365)</span><span class="sxs-lookup"><span data-stu-id="feb86-200">Part 4 - Protection from malicious URLs and files (Safe Links and Safe Attachments in Defender for Office 365)</span></span>

<span data-ttu-id="feb86-201">악성 URL 및 파일로부터 클릭 시간 보호는 Microsoft [Defender for](/office365/servicedescriptions/office-365-advanced-threat-protection-service-description)Office 365.</span><span class="sxs-lookup"><span data-stu-id="feb86-201">Time-of-click protection from malicious URLs and files is available in subscriptions that include [Microsoft Defender for Office 365](/office365/servicedescriptions/office-365-advanced-threat-protection-service-description).</span></span> <span data-ttu-id="feb86-202">안전한 첨부 파일 및 [안전한](safe-attachments.md) 링크 [정책을 통해 설정됩니다.](safe-links.md)</span><span class="sxs-lookup"><span data-stu-id="feb86-202">It's set up through [Safe Attachments](safe-attachments.md) and [Safe Links](safe-links.md) policies.</span></span>

### <a name="safe-attachments-policies-in-microsoft-defender-for-office-365"></a><span data-ttu-id="feb86-203">Microsoft Defender for Office 365</span><span class="sxs-lookup"><span data-stu-id="feb86-203">Safe Attachments policies in Microsoft Defender for Office 365</span></span>

<span data-ttu-id="feb86-204">안전한 첨부 파일을 [설정하기 위해](safe-attachments.md)하나 이상의 안전한 링크 정책을 만드시다.</span><span class="sxs-lookup"><span data-stu-id="feb86-204">To set up [Safe Attachments](safe-attachments.md), create at least one Safe Links policy.</span></span>

1. <span data-ttu-id="feb86-205">보안 및 [& 센터에서](https://protection.office.com) **위협** 관리 정책 ATP 안전한 첨부 파일을 선택한 \>  \> 다음 만들기를 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="feb86-205">In the [Security & Compliance Center](https://protection.office.com), choose **Threat management** \> **Policy** \> **ATP Safe Attachments**, and then click **Create**.</span></span>

2. <span data-ttu-id="feb86-206">나타나는 **새 안전** 첨부 파일 정책 마법사에서 다음 설정을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="feb86-206">In the **New Safe Attachments policy** wizard that appears, configure the following settings:</span></span>

   - <span data-ttu-id="feb86-207">이름 **상자에** `Block malware` 를 입력하고 다음 을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="feb86-207">In the **Name** box, type `Block malware`, and then click **Next**.</span></span>

   - <span data-ttu-id="feb86-208">설정 **페이지에서** 다음 설정을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="feb86-208">On the **Settings** page, configure the following settings:</span></span>
     - <span data-ttu-id="feb86-209">안전한 첨부 **파일 알 수 없는 맬웨어 응답 섹션에서** 차단 을 선택 **합니다.**</span><span class="sxs-lookup"><span data-stu-id="feb86-209">In the **Safe attachments unknown malware response** section, choose **Block**.</span></span>
     - <span data-ttu-id="feb86-210">첨부 파일 **리디렉션 섹션에서** 리디렉션 사용 **옵션을 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="feb86-210">In the **Redirect attachment** section, select the option **Enable redirect**.</span></span> <span data-ttu-id="feb86-211">검색된 파일을 검토할 조직의 보안 관리자 또는 운영자의 전자 메일 주소를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="feb86-211">Specify the email address for your organization's security administrator or operator, who will review detected files.</span></span>

     <span data-ttu-id="feb86-212">**다음** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="feb86-212">Click **Next**.</span></span>

3. <span data-ttu-id="feb86-213">적용 **대상** 페이지에서 조건 추가를 클릭하고 적용 대상인 경우 적용을 **선택합니다.** 받는 사람 도메인이 입니다. **추가를** 클릭하고 도메인 또는 도메인을 선택하고 **추가,** 완료를 클릭한 후 다음을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="feb86-213">On the **Applied to** page, click **Add a condition**, choose **Applied if: The recipient domain is**, click **Add**, select your domain or domains, click **Add**, click **Done**, and then click **Next**.</span></span>

4. <span data-ttu-id="feb86-214">설정을 검토하고 마친 을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="feb86-214">Review your settings and then click **Finish**.</span></span>

### <a name="safe-links-policies-in-microsoft-defender-for-office-365"></a><span data-ttu-id="feb86-215">Microsoft Defender for Office 365</span><span class="sxs-lookup"><span data-stu-id="feb86-215">Safe Links policies in Microsoft Defender for Office 365</span></span>

<span data-ttu-id="feb86-216">안전한 링크를 [설정하려면](safe-links.md)안전한 링크에 대한 전역 설정을 검토 및 편집하고 안전한 링크 정책을 하나 이상 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="feb86-216">To set up [Safe Links](safe-links.md), review and edit your global settings for Safe Links, and create at least one Safe Links policy.</span></span>

1. <span data-ttu-id="feb86-217">보안 및 [&](https://protection.office.com)센터에서 **위협** 관리 정책 ATP 안전한 링크를 선택하고 전역 설정을 클릭한 후 다음 설정을 \>  \> 구성합니다. </span><span class="sxs-lookup"><span data-stu-id="feb86-217">In the [Security & Compliance Center](https://protection.office.com), choose **Threat management** \> **Policy** \> **ATP Safe Links**, and click **Global settings**, and then configure the following settings:</span></span>

   - <span data-ttu-id="feb86-218">다음에서 안전한 링크 사용 **확인: Office 365** 응용 프로그램이 켜져 있는지 확인: ![ 을 토글합니다. ](../../media/scc-toggle-on.png)</span><span class="sxs-lookup"><span data-stu-id="feb86-218">Verify **Use Safe Links in: Office 365 applications** is turned on: ![Toggle on](../../media/scc-toggle-on.png).</span></span>
   - <span data-ttu-id="feb86-219">사용자가 안전한 링크를 **클릭하는** 경우 추적하지 않습니다. 사용자 클릭을 추적하려면 이 설정을 해제합니다. ![ 토글 끄기. ](../../media/scc-toggle-off.png)</span><span class="sxs-lookup"><span data-stu-id="feb86-219">**Do not track when users click Safe Links**: Turn this setting off to track user clicks: ![Toggle off](../../media/scc-toggle-off.png).</span></span>
   - <span data-ttu-id="feb86-220">**사용자가 원래 URL에 대한 안전한** 링크를 클릭할 수 없습니다. 이 설정이 켜져 있는지 확인합니다. ![ 토글합니다. ](../../media/scc-toggle-on.png)</span><span class="sxs-lookup"><span data-stu-id="feb86-220">**Do not let users click through safe links to original URL**: Verify this setting is turned on: ![Toggle on](../../media/scc-toggle-on.png).</span></span>

   <span data-ttu-id="feb86-221">작업을 마쳤으면 **저장** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="feb86-221">When you're finished, click **Save**.</span></span>

2. <span data-ttu-id="feb86-222">기본 안전한 링크 페이지에서 만들기를 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="feb86-222">Back on the main Safe Links page, click **Create**.</span></span>

3. <span data-ttu-id="feb86-223">나타나는 **안전한** 링크 만들기 정책 마법사에서 다음 설정을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="feb86-223">In the **Create Safe Links policy** wizard that appears, configure the following settings:</span></span>

   - <span data-ttu-id="feb86-224">이름 **상자에** 과 같은 이름을 입력하고 `Safe Links` 다음 을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="feb86-224">In the **Name** box, type a name, such as `Safe Links`, and then click **Next**.</span></span>

   - <span data-ttu-id="feb86-225">설정 **페이지에서** 다음 설정을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="feb86-225">On the **Settings** page, configure the following settings:</span></span>
     - <span data-ttu-id="feb86-226">**메시지에서 알 수 없는 악의적인 URL에** 대한 작업 선택: 을 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="feb86-226">**Select the action for unknown potentially malicious URLs in messages**: Choose **On**.</span></span>
     - <span data-ttu-id="feb86-227">**에서 알 수 없는 URL** 또는 잠재적으로 악의적인 URL에 대한 작업을 Microsoft Teams : 을 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="feb86-227">**Select the action for unknown or potentially malicious URLs within Microsoft Teams**: Choose **On**.</span></span>
     - <span data-ttu-id="feb86-228">**조직 내에서 보낸 전자 메일 메시지에 안전한 링크 적용**</span><span class="sxs-lookup"><span data-stu-id="feb86-228">**Apply safe links to email messages sent within the organization**</span></span>
     - <span data-ttu-id="feb86-229">**메시지를 배달하기 전에 URL 검색이 완료될 때까지 기다렸다가**</span><span class="sxs-lookup"><span data-stu-id="feb86-229">**Wait for URL scanning to complete before delivering the message**</span></span>
     - <span data-ttu-id="feb86-230">**조직 내에서 보낸 전자 메일 메시지에 안전한 링크 적용**</span><span class="sxs-lookup"><span data-stu-id="feb86-230">**Apply safe links to email messages sent within the organization**</span></span>
     - <span data-ttu-id="feb86-231">**사용자가 원래 URL을 클릭할 수 있도록 허용 안 하세요.**</span><span class="sxs-lookup"><span data-stu-id="feb86-231">**Do not allow users to click through to original URL**</span></span>

     <span data-ttu-id="feb86-232">**다음** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="feb86-232">Click **Next**</span></span>

4. <span data-ttu-id="feb86-233">적용 **대상** 페이지에서 조건 추가를 클릭하고 적용 대상인 경우 적용을 **선택합니다.** 받는 사람 도메인이 입니다. **추가를** 클릭하고 도메인 또는 도메인을 선택하고 **추가,** 완료를 클릭한 후 다음을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="feb86-233">On the **Applied to** page, click **Add a condition**, choose **Applied if: The recipient domain is**, click **Add**, select your domain or domains, click **Add**, click **Done**, and then click **Next**.</span></span>

5. <span data-ttu-id="feb86-234">설정을 검토하고 마친 을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="feb86-234">Review your settings and then click **Finish**.</span></span>

<span data-ttu-id="feb86-235">자세한 내용은 [안전한 링크 정책 설정](set-up-safe-links-policies.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="feb86-235">To learn more, see [Set up Safe Links policies](set-up-safe-links-policies.md).</span></span>

## <a name="part-5---verify-safe-attachments-for-sharepoint-onedrive-and-microsoft-teams-is-turned-on"></a><span data-ttu-id="feb86-236">5부 - 설정되어 있는 SharePoint, OneDrive 및 Microsoft Teams 첨부 파일 확인</span><span class="sxs-lookup"><span data-stu-id="feb86-236">Part 5 - Verify Safe Attachments for SharePoint, OneDrive, and Microsoft Teams is turned on</span></span>

<span data-ttu-id="feb86-237">SharePoint, OneDrive 및 Teams 작업은 공동 작업을 위해 구축됩니다.</span><span class="sxs-lookup"><span data-stu-id="feb86-237">Workloads like SharePoint, OneDrive, and Teams are built for collaboration.</span></span> <span data-ttu-id="feb86-238">팀 사이트에 Defender를 Office 365 팀 사이트 및 문서 라이브러리에서 악성으로 식별된 파일을 차단하고 검색하는 데 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="feb86-238">Using Defender for Office 365 helps with blocking and detection of files that are identified as malicious in team sites and document libraries.</span></span> <span data-ttu-id="feb86-239">작동 방식에 대한 자세한 내용은 을(를) 읽어 [볼 수 있습니다.](mdo-for-spo-odb-and-teams.md)</span><span class="sxs-lookup"><span data-stu-id="feb86-239">You can read more about how that works [here](mdo-for-spo-odb-and-teams.md).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="feb86-240">**이 절차를 시작하기** 전에 사용자 환경 에 대해 감사 로깅이 Microsoft 365 합니다.</span><span class="sxs-lookup"><span data-stu-id="feb86-240">**Before you begin this procedure, make sure that audit logging is already turned on for your Microsoft 365 environment**.</span></span> <span data-ttu-id="feb86-241">이 작업은 일반적으로 감사 로그 역할이 할당된 사용자가 Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="feb86-241">This is typically done by someone who has the Audit Logs role assigned in Exchange Online.</span></span> <span data-ttu-id="feb86-242">자세한 내용은 감사 로그 검색 켜기 또는 [끄기!를 참조하세요.](../../compliance/turn-audit-log-search-on-or-off.md)</span><span class="sxs-lookup"><span data-stu-id="feb86-242">For more information, see [Turn audit log search on or off](../../compliance/turn-audit-log-search-on-or-off.md)!</span></span>

1. <span data-ttu-id="feb86-243">보안 및 [& 센터에서](https://protection.office.com) **위협** 관리 정책 \>  \> **ATP 안전한** 첨부 파일을 선택한 다음 전역 설정을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="feb86-243">In the [Security & Compliance Center](https://protection.office.com), choose **Threat management** \> **Policy** \> **ATP Safe Attachments**, and then click **Global settings**.</span></span>

2. <span data-ttu-id="feb86-244">Office 365, SharePoint, OneDrive 및 Microsoft Teams 토글에 대한 **Defender** 켜기 설정이 오른쪽에 있는지 확인: ![ 을 토글하고 ](../../media/scc-toggle-on.png) 저장을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="feb86-244">Verify the **Turn on Defender for Office 365 for SharePoint, OneDrive, and Microsoft Teams** toggle is to the right: ![Toggle on](../../media/scc-toggle-on.png), and then click **Save**.</span></span>

3. <span data-ttu-id="feb86-245">조직의 안전 첨부 파일 정책 및 안전한 [](set-up-safe-attachments-policies.md) 링크 정책을 검토하고 적절하게 [편집합니다.](set-up-safe-links-policies.md)</span><span class="sxs-lookup"><span data-stu-id="feb86-245">Review (and, as appropriate, edit) your organization's [Safe Attachments policies](set-up-safe-attachments-policies.md) and [Safe Links policies](set-up-safe-links-policies.md).</span></span>

4. <span data-ttu-id="feb86-246">(권장) 전역 관리자 또는 SharePoint Online 관리자로서 _DisallowInfectedFileDownload_ 매개 변수를 로 설정하여 **[Set-SPOTenant](/powershell/module/sharepoint-online/Set-SPOTenant)** cmdlet을 실행합니다. `$true`</span><span class="sxs-lookup"><span data-stu-id="feb86-246">(Recommended) As a global administrator or a SharePoint Online administrator, run the **[Set-SPOTenant](/powershell/module/sharepoint-online/Set-SPOTenant)** cmdlet with the _DisallowInfectedFileDownload_ parameter set to `$true`.</span></span>

   - <span data-ttu-id="feb86-247">`$true` 검색된 파일에 대한 모든 작업(삭제 제외)을 차단합니다.</span><span class="sxs-lookup"><span data-stu-id="feb86-247">`$true` blocks all actions (except Delete) for detected files.</span></span> <span data-ttu-id="feb86-248">검색된 파일을 열거나 이동, 복사 또는 공유할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="feb86-248">People cannot open, move, copy, or share detected files.</span></span>
   - <span data-ttu-id="feb86-249">`$false` 삭제 및 다운로드를 제외한 모든 작업을 차단합니다.</span><span class="sxs-lookup"><span data-stu-id="feb86-249">`$false` blocks all actions except Delete and Download.</span></span> <span data-ttu-id="feb86-250">사람들은 위험을 수락하고 검색된 파일을 다운로드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="feb86-250">People can choose to accept the risk and download a detected file.</span></span>

   > [!TIP]
   > <span data-ttu-id="feb86-251">PowerShell과 함께 PowerShell을 사용하는 Microsoft 365 자세한 내용은 [PowerShell을 사용하여 Microsoft 365 관리를 참조합니다.](../../enterprise/manage-microsoft-365-with-microsoft-365-powershell.md)</span><span class="sxs-lookup"><span data-stu-id="feb86-251">To learn more about using PowerShell with Microsoft 365, see [Manage Microsoft 365 with PowerShell](../../enterprise/manage-microsoft-365-with-microsoft-365-powershell.md).</span></span>

5. <span data-ttu-id="feb86-252">모든 데이터 센터에 변경 내용을 분산하는 데 최대 30분 Microsoft 365 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="feb86-252">Allow up to 30 minutes for your changes to spread to all Microsoft 365 datacenters.</span></span>

### <a name="now-set-up-alerts-for-detected-files"></a><span data-ttu-id="feb86-253">이제 검색된 파일에 대한 경고 설정</span><span class="sxs-lookup"><span data-stu-id="feb86-253">Now set up alerts for detected files</span></span>

<span data-ttu-id="feb86-254">SharePoint Online, 비즈니스용 OneDrive 또는 Microsoft Teams 파일이 악성으로 식별된 경우 알림을 받으면 경고를 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="feb86-254">To receive notification when a file in SharePoint Online, OneDrive for Business, or Microsoft Teams has been identified as malicious, you can set up an alert.</span></span>

1. <span data-ttu-id="feb86-255">보안 및 [& 센터에서](https://protection.office.com) **경고** 관리 \> **를 선택 합니다.**</span><span class="sxs-lookup"><span data-stu-id="feb86-255">In the [Security & Compliance Center](https://protection.office.com), choose **Alerts** \> **Manage alerts**.</span></span>

2. <span data-ttu-id="feb86-256">새 **경고 정책 을 선택 합니다.**</span><span class="sxs-lookup"><span data-stu-id="feb86-256">Choose **New alert policy**.</span></span>

3. <span data-ttu-id="feb86-257">경고의 이름을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="feb86-257">Specify a name for the alert.</span></span> <span data-ttu-id="feb86-258">예를 들어 라이브러리에 악성 파일을 입력할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="feb86-258">For example, you could type Malicious Files in Libraries.</span></span>

4. <span data-ttu-id="feb86-259">경고에 대한 설명을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="feb86-259">Type a description for the alert.</span></span> <span data-ttu-id="feb86-260">예를 들어 online, SharePoint 또는 OneDrive 파일에서 악성 파일이 검색되면 관리자에게 OneDrive 수 Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="feb86-260">For example, you could type Notifies admins when malicious files are detected in SharePoint Online, OneDrive, or Microsoft Teams.</span></span>

5. <span data-ttu-id="feb86-261">다음의 **경우 이 경고 보내기... 섹션에서** 다음을 설정하세요.</span><span class="sxs-lookup"><span data-stu-id="feb86-261">In the **Send this alert when...** section, set:</span></span>

   <span data-ttu-id="feb86-262">a.</span><span class="sxs-lookup"><span data-stu-id="feb86-262">a.</span></span> <span data-ttu-id="feb86-263">활동 **목록에서** **파일에서 검색된 맬웨어를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="feb86-263">In the **Activities** list, choose **Detected malware in file**.</span></span>

   <span data-ttu-id="feb86-264">b.</span><span class="sxs-lookup"><span data-stu-id="feb86-264">b.</span></span> <span data-ttu-id="feb86-265">사용자 **필드는 비워** 두면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="feb86-265">Leave the **Users** field empty.</span></span>

6. <span data-ttu-id="feb86-266">이 **알림 보내기...** 섹션에서 악의적인 파일이 감지될 때 알림을 수신해야 하는 전역 관리자, 보안 관리자 또는 보안 독자를 하나 이상 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="feb86-266">In the **Send this alert to...** section, select one or more global administrators, security administrators, or security readers who should receive notification when a malicious file is detected.</span></span>

7. <span data-ttu-id="feb86-267">**를 저장합니다.**</span><span class="sxs-lookup"><span data-stu-id="feb86-267">**Save**.</span></span>

<span data-ttu-id="feb86-268">경고에 대한 자세한 내용은 보안 및 준수 센터에서 활동 [& 참조합니다.](../../compliance/create-activity-alerts.md)</span><span class="sxs-lookup"><span data-stu-id="feb86-268">To learn more about alerts, see [Create activity alerts in the Security & Compliance Center](../../compliance/create-activity-alerts.md).</span></span>

> [!NOTE]
> <span data-ttu-id="feb86-269">구성이 완료되면 다음 링크를 사용하여 작업 조사를 시작하세요.</span><span class="sxs-lookup"><span data-stu-id="feb86-269">When you're finished configuring, use these links to start workload investigations:</span></span>
>
>- [<span data-ttu-id="feb86-270">위협 방지 상태 보고서</span><span class="sxs-lookup"><span data-stu-id="feb86-270">Threat protection status report</span></span>](view-email-security-reports.md#threat-protection-status-report)
>- [<span data-ttu-id="feb86-271">보안 및 & 센터를 사용하여 분리된 파일 관리</span><span class="sxs-lookup"><span data-stu-id="feb86-271">Use the Security & Compliance Center to manage quarantined files</span></span>](manage-quarantined-messages-and-files.md#microsoft-defender-for-office-365-only-use-the-security--compliance-center-to-manage-quarantined-files)
>- [<span data-ttu-id="feb86-272">SharePoint Online, OneDrive 또는 Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="feb86-272">What to do when a malicious file is found in SharePoint Online, OneDrive, or Microsoft Teams</span></span>](https://support.microsoft.com/office/01e902ad-a903-4e0f-b093-1e1ac0c37ad2)
>- [<span data-ttu-id="feb86-273">2016년 8월에 관리자로 quarantined messages and files Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="feb86-273">Manage quarantined messages and files as an administrator in Microsoft 365</span></span>](manage-quarantined-messages-and-files.md)

## <a name="part-6---additional-settings-to-configure"></a><span data-ttu-id="feb86-274">6부 - 구성할 추가 설정</span><span class="sxs-lookup"><span data-stu-id="feb86-274">Part 6 - Additional settings to configure</span></span>

<span data-ttu-id="feb86-275">맬웨어, 악의적인 URL 및 파일, 피싱 및 스팸으로부터 보호를 구성하는 것과 함께 제로 아워 자동 제거를 구성하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="feb86-275">Along with configuring protection from malware, malicious URLs and files, phishing, and spam, we recommend you configure zero-hour auto purge.</span></span>

### <a name="zero-hour-auto-purge-for-email-in-eop"></a><span data-ttu-id="feb86-276">EOP에서 전자 메일에 대한 제로 아워 자동 제거</span><span class="sxs-lookup"><span data-stu-id="feb86-276">Zero-hour auto purge for email in EOP</span></span>

<span data-ttu-id="feb86-277">[ZAP(제로](zero-hour-auto-purge.md) 아워 자동 제거)는 EOP를 포함 하는 [구독에서 사용할 수 있습니다.](/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description)</span><span class="sxs-lookup"><span data-stu-id="feb86-277">[Zero-hour auto purge](zero-hour-auto-purge.md) (ZAP) is available in subscriptions that include [EOP](/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description).</span></span> <span data-ttu-id="feb86-278">이 보호는 기본적으로 켜져 있습니다. 그러나 보호를 적용하려면 다음 조건을 충족해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="feb86-278">This protection is turned on by default; however, the following conditions must be met for protection to be in effect:</span></span>

- <span data-ttu-id="feb86-279">스팸 작업은 스팸 방지 정책에서 메시지를 **정크** 메일 폴더로 [이동으로 설정됩니다.](anti-spam-protection.md)</span><span class="sxs-lookup"><span data-stu-id="feb86-279">Spam actions are set to **Move message to Junk Email folder** in [anti-spam policies](anti-spam-protection.md).</span></span>

- <span data-ttu-id="feb86-280">사용자는 기본 정크 메일 설정을 유지하며 정크 메일 보호를 해제하지 않습니다. [](ensure-that-spam-is-routed-to-each-user-s-junk-email-folder.md)</span><span class="sxs-lookup"><span data-stu-id="feb86-280">Users have kept their default [junk email settings](ensure-that-spam-is-routed-to-each-user-s-junk-email-folder.md), and haven't turned off junk email protection.</span></span>

<span data-ttu-id="feb86-281">자세한 내용은 제로 아워 자동 제거 - 스팸 및 맬웨어로부터 [보호를 참조합니다.](zero-hour-auto-purge.md)</span><span class="sxs-lookup"><span data-stu-id="feb86-281">To learn more, see [Zero-hour auto purge - protection against spam and malware](zero-hour-auto-purge.md).</span></span>

## <a name="post-setup-tasks-and-next-steps"></a><span data-ttu-id="feb86-282">설치 후 작업 및 다음 단계</span><span class="sxs-lookup"><span data-stu-id="feb86-282">Post-setup tasks and next steps</span></span>

<span data-ttu-id="feb86-283">위협 방지 기능을 구성한 후 해당 기능이 작동되는 방법을 모니터링해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="feb86-283">After configuring the threat protection features, make sure to monitor how those features are working!</span></span> <span data-ttu-id="feb86-284">필요한 작업을 할 수 있도록 정책을 검토하고 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="feb86-284">Review and revise your policies so that they do what you need them to.</span></span> <span data-ttu-id="feb86-285">또한 가치를 추가할 수 있는 새로운 기능 및 서비스 업데이트를 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="feb86-285">Also, watch for new features and service updates that can add value.</span></span>

****

|<span data-ttu-id="feb86-286">수행할 작업</span><span class="sxs-lookup"><span data-stu-id="feb86-286">What to do</span></span>|<span data-ttu-id="feb86-287">자세한 정보를 알아볼 수 있는 리소스</span><span class="sxs-lookup"><span data-stu-id="feb86-287">Resources to learn more</span></span>|
|---|---|
|<span data-ttu-id="feb86-288">보고서를 확인하여 위협 방지 기능이 조직에 어떻게 작동하고 있는지 확인</span><span class="sxs-lookup"><span data-stu-id="feb86-288">See how threat protection features are working for your organization by viewing reports</span></span>|[<span data-ttu-id="feb86-289">보안 대시보드</span><span class="sxs-lookup"><span data-stu-id="feb86-289">Security dashboard</span></span>](security-dashboard.md) <p> [<span data-ttu-id="feb86-290">전자 메일 보안 보고서</span><span class="sxs-lookup"><span data-stu-id="feb86-290">Email security reports</span></span>](view-email-security-reports.md) <p> [<span data-ttu-id="feb86-291">Microsoft Defender for Office 365</span><span class="sxs-lookup"><span data-stu-id="feb86-291">Reports for Microsoft Defender for Office 365</span></span>](view-reports-for-mdo.md) <p> [<span data-ttu-id="feb86-292">위협 탐색기</span><span class="sxs-lookup"><span data-stu-id="feb86-292">Threat Explorer</span></span>](threat-explorer.md)|
|<span data-ttu-id="feb86-293">필요한 경우 위협 방지 정책을 주기적으로 검토하고 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="feb86-293">Periodically review and revise your threat protection policies as needed</span></span>|[<span data-ttu-id="feb86-294">Secure Score</span><span class="sxs-lookup"><span data-stu-id="feb86-294">Secure Score</span></span>](../defender/microsoft-secure-score.md) <p> [<span data-ttu-id="feb86-295">스마트 보고서 및 인사이트</span><span class="sxs-lookup"><span data-stu-id="feb86-295">Smart reports and insights</span></span>](reports-and-insights-in-security-and-compliance.md) <p> [<span data-ttu-id="feb86-296">Microsoft 365 조사 및 대응 기능</span><span class="sxs-lookup"><span data-stu-id="feb86-296">Microsoft 365 threat investigation and response features</span></span>](./office-365-ti.md)|
|<span data-ttu-id="feb86-297">새로운 기능 및 서비스 업데이트 감시</span><span class="sxs-lookup"><span data-stu-id="feb86-297">Watch for new features and service updates</span></span>|[<span data-ttu-id="feb86-298">표준 및 대상 지정 릴리스 옵션</span><span class="sxs-lookup"><span data-stu-id="feb86-298">Standard and Targeted release options</span></span>](../../admin/manage/release-options-in-office-365.md) <p> [<span data-ttu-id="feb86-299">메시지 센터</span><span class="sxs-lookup"><span data-stu-id="feb86-299">Message Center</span></span>](../../admin/manage/message-center.md) <p> [<span data-ttu-id="feb86-300">Microsoft 365 로드맵</span><span class="sxs-lookup"><span data-stu-id="feb86-300">Microsoft 365 Roadmap</span></span>](https://www.microsoft.com/microsoft-365/roadmap?filters=&searchterms=advanced%2Cthreat%2Cprotection) <p> [<span data-ttu-id="feb86-301">서비스 설명</span><span class="sxs-lookup"><span data-stu-id="feb86-301">Service Descriptions</span></span>](/office365/servicedescriptions/office-365-service-descriptions-technet-library)|
|<span data-ttu-id="feb86-302">EOP 및 Defender for Office 365</span><span class="sxs-lookup"><span data-stu-id="feb86-302">Learn the details about recommended Standard and Strict security configurations for EOP and Defender for Office 365</span></span>|[<span data-ttu-id="feb86-303">EOP 및 Microsoft Defender 보안에 대한 Office 365 설정</span><span class="sxs-lookup"><span data-stu-id="feb86-303">Recommended settings for EOP and Microsoft Defender for Office 365 security</span></span>](recommended-settings-for-eop-and-office365.md)|
