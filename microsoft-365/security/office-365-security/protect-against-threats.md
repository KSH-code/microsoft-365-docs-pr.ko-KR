---
title: 위협으로부터 보호
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: Admin
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Normal
ms.date: 09/08/2020
search.appverid:
- MOE150
- MET150
ms.assetid: b10023f6-f30f-45d3-b3ad-b71aa4aa0d58
ms.collection:
- M365-security-compliance
description: 관리자는 Microsoft 365의 위협 보호에 대해 알아보고 조직에서이를 사용 하는 방법을 구성할 수 있습니다.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: a78bbea2d11360bbfa48fa3da01391471b2e0a4d
ms.sourcegitcommit: 27daadad9ca0f02a833ff3cff8a574551b9581da
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/12/2020
ms.locfileid: "47547365"
---
# <a name="protect-against-threats"></a><span data-ttu-id="74f67-103">위협으로부터 보호</span><span class="sxs-lookup"><span data-stu-id="74f67-103">Protect against threats</span></span>

<span data-ttu-id="74f67-104">다음은 Advanced Threat Protection의 구성을 청크로 구분 하는 빠른 시작 가이드입니다.</span><span class="sxs-lookup"><span data-stu-id="74f67-104">Here's a quick-start guide that breaks the configuration of Advanced Threat Protection into chunks.</span></span> <span data-ttu-id="74f67-105">Office 365의 위협 방지 기능을 처음 사용 하는 경우 시작할 위치를 잘 모르는 경우에는이 *지침을 검사*목록 및 출발점으로 사용해 보세요.</span><span class="sxs-lookup"><span data-stu-id="74f67-105">If you're new to threat protection features in Office 365, not sure where to begin, or if you learn best by *doing*, use this guidance as a checklist and a starting point.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="74f67-106">**초기 권장 설정은 각 정책 유형에 대해 포함 되지만 대부분의 옵션을 사용할 수 있으며, 특정 조직의 요구에 맞게 설정을 조정할 수**있습니다.</span><span class="sxs-lookup"><span data-stu-id="74f67-106">**Initial recommended settings are included for each kind of policy; however, many options are available, and you can adjust your settings to meet your specific organization's needs**.</span></span> <span data-ttu-id="74f67-107">정책이 나 변경 내용이 데이터 센터를 통해 작동 하는 데 약 30 분 정도 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="74f67-107">Allow approximately 30 minutes for your policies or changes to work their way through your datacenter.</span></span>

## <a name="requirements"></a><span data-ttu-id="74f67-108">요구 사항</span><span class="sxs-lookup"><span data-stu-id="74f67-108">Requirements</span></span>

### <a name="subscriptions"></a><span data-ttu-id="74f67-109">구독</span><span class="sxs-lookup"><span data-stu-id="74f67-109">Subscriptions</span></span>

<span data-ttu-id="74f67-110">위협 보호 기능은 *모든* Microsoft 또는 Office 365 구독에 포함 되어 있습니다. 그러나 일부 구독은 고급 기능을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="74f67-110">Threat protection features are included in *all* Microsoft or Office 365 subscriptions; however, some subscriptions have advanced features.</span></span> <span data-ttu-id="74f67-111">아래 표에는이 문서에 포함 된 보호 기능과 최소 구독 요구 사항이 함께 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="74f67-111">The table below lists the protection features included in this article together with the minimum subscription requirements.</span></span>

> [!TIP]
> <span data-ttu-id="74f67-112">감사를 설정 하는 지침 보다는 Office 365 Exchange Online Protection (**EOP**)의 일부로 표시 되는 맬웨어 방지, 피싱 방지 및 스팸 방지에 대 한 *단계가* 진행 되 고 있음을 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="74f67-112">Notice that, beyond the directions to turn on auditing, *steps* start anti-malware, anti-phishing, and anti-spam, which are marked as part of Office 365 Exchange Online Protection (**EOP**).</span></span> <span data-ttu-id="74f67-113">이는**ATP**(Advanced threat protection)에 포함 하 고 EOP를 구성 하기 전 까지는 Advanced threat protection 문서에서 이상한 일이 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="74f67-113">This can seem odd in an Advanced Threat Protection article, until you remember Advanced Threat Protection (**ATP**) contains, and builds on, EOP.</span></span>

****

|<span data-ttu-id="74f67-114">보호 유형</span><span class="sxs-lookup"><span data-stu-id="74f67-114">Protection type</span></span>|<span data-ttu-id="74f67-115">구독 요구 사항</span><span class="sxs-lookup"><span data-stu-id="74f67-115">Subscription requirement</span></span>|
|---|---|
|<span data-ttu-id="74f67-116">감사 로깅 (보고 목적)</span><span class="sxs-lookup"><span data-stu-id="74f67-116">Audit logging (for reporting purposes)</span></span>|[<span data-ttu-id="74f67-117">Exchange Online</span><span class="sxs-lookup"><span data-stu-id="74f67-117">Exchange Online</span></span>](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/exchange-online-service-description)|
|<span data-ttu-id="74f67-118">맬웨어 방지 보호 기능</span><span class="sxs-lookup"><span data-stu-id="74f67-118">Anti-malware protection</span></span>|<span data-ttu-id="74f67-119">**EOP**( [Exchange Online Protection](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description) )</span><span class="sxs-lookup"><span data-stu-id="74f67-119">[Exchange Online Protection](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description) (**EOP**)</span></span>|
|<span data-ttu-id="74f67-120">피싱 방지 보호 기능</span><span class="sxs-lookup"><span data-stu-id="74f67-120">Anti-phishing protection</span></span>|[<span data-ttu-id="74f67-121">EOP</span><span class="sxs-lookup"><span data-stu-id="74f67-121">EOP</span></span>](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description)|
|<span data-ttu-id="74f67-122">스팸 방지 보호 기능</span><span class="sxs-lookup"><span data-stu-id="74f67-122">Anti-spam protection</span></span>|[<span data-ttu-id="74f67-123">EOP</span><span class="sxs-lookup"><span data-stu-id="74f67-123">EOP</span></span>](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description)|
|<span data-ttu-id="74f67-124">0 시간 자동 삭제 (전자 메일의 경우)</span><span class="sxs-lookup"><span data-stu-id="74f67-124">Zero-hour auto purge (for email)</span></span>|[<span data-ttu-id="74f67-125">EOP</span><span class="sxs-lookup"><span data-stu-id="74f67-125">EOP</span></span>](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description)|
|<span data-ttu-id="74f67-126">전자 메일 및 Office 문서 (안전한 링크 및 안전한 첨부 파일)의 악성 Url 및 파일과의 보호</span><span class="sxs-lookup"><span data-stu-id="74f67-126">Protection from malicious URLs and files in email and Office documents (safe links and safe attachments)</span></span>|<span data-ttu-id="74f67-127">[Office 365 ATP (Advanced Threat Protection](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description) )**ATP**</span><span class="sxs-lookup"><span data-stu-id="74f67-127">[Office 365 Advanced Threat Protection](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description) (**ATP**)</span></span>|
|<span data-ttu-id="74f67-128">SharePoint, OneDrive 및 Microsoft 팀 작업에 대 한 ATP 켜기</span><span class="sxs-lookup"><span data-stu-id="74f67-128">Turn on ATP for SharePoint, OneDrive, and Microsoft Teams workloads</span></span>| [<span data-ttu-id="74f67-129">ATP</span><span class="sxs-lookup"><span data-stu-id="74f67-129">ATP</span></span>](https://docs.microsoft.com/microsoft-365/security/office-365-security/protect-against-threats?view=o365-worldwide)|
|<span data-ttu-id="74f67-130">고급 피싱 방지 보호</span><span class="sxs-lookup"><span data-stu-id="74f67-130">Advanced anti-phishing protection</span></span>|[<span data-ttu-id="74f67-131">ATP</span><span class="sxs-lookup"><span data-stu-id="74f67-131">ATP</span></span>](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description)|

### <a name="roles-and-permissions"></a><span data-ttu-id="74f67-132">역할 및 사용 권한</span><span class="sxs-lookup"><span data-stu-id="74f67-132">Roles and permissions</span></span>

<span data-ttu-id="74f67-133">ATP 정책을 구성 하려면 [보안 & 준수 센터](https://docs.microsoft.com/office365/servicedescriptions/office-365-platform-service-description/office-365-securitycompliance-center)에 적절 한 역할이 할당 되어 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="74f67-133">To configure ATP policies, you must be assigned an appropriate role in the [Security & Compliance Center](https://docs.microsoft.com/office365/servicedescriptions/office-365-platform-service-description/office-365-securitycompliance-center).</span></span> <span data-ttu-id="74f67-134">이러한 작업을 수행할 수 있는 역할은 아래 표를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="74f67-134">Take a look at the table below for roles that can do these actions.</span></span>

****

|<span data-ttu-id="74f67-135">역할 또는 역할 그룹</span><span class="sxs-lookup"><span data-stu-id="74f67-135">Role or role group</span></span>|<span data-ttu-id="74f67-136">자세한 정보</span><span class="sxs-lookup"><span data-stu-id="74f67-136">Where to learn more</span></span>|
|---|---|
|<span data-ttu-id="74f67-137">전역 관리자</span><span class="sxs-lookup"><span data-stu-id="74f67-137">global administrator</span></span>|[<span data-ttu-id="74f67-138">Microsoft 365 관리자 역할 정보</span><span class="sxs-lookup"><span data-stu-id="74f67-138">About Microsoft 365 admin roles</span></span>](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles)|
|<span data-ttu-id="74f67-139">보안 관리자</span><span class="sxs-lookup"><span data-stu-id="74f67-139">Security Administrator</span></span>|[<span data-ttu-id="74f67-140">Azure Active Directory의 관리자 역할 권한</span><span class="sxs-lookup"><span data-stu-id="74f67-140">Administrator role permissions in Azure Active Directory</span></span>](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles)|
|<span data-ttu-id="74f67-141">Exchange Online 조직 관리</span><span class="sxs-lookup"><span data-stu-id="74f67-141">Exchange Online Organization Management</span></span>|[<span data-ttu-id="74f67-142">Exchange Online의 사용 권한</span><span class="sxs-lookup"><span data-stu-id="74f67-142">Permissions in Exchange Online</span></span>](https://docs.microsoft.com/exchange/permissions-exo/permissions-exo) <br><span data-ttu-id="74f67-143">및</span><span class="sxs-lookup"><span data-stu-id="74f67-143">and</span></span><br> [<span data-ttu-id="74f67-144">Exchange Online PowerShell</span><span class="sxs-lookup"><span data-stu-id="74f67-144">Exchange Online PowerShell</span></span>](https://docs.microsoft.com/powershell/exchange/exchange-online-powershell)|
|

<span data-ttu-id="74f67-145">자세한 내용은 [보안 및 &amp; 준수 센터의 사용 권한을](permissions-in-the-security-and-compliance-center.md)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="74f67-145">To learn more, see [Permissions in the Security &amp; Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

## <a name="before-you-begin-turn-on-audit-logging-for-reporting-and-investigation"></a><span data-ttu-id="74f67-146">시작 하기 전에 보고 및 조사에 대 한 감사 로깅 설정</span><span class="sxs-lookup"><span data-stu-id="74f67-146">Before you begin, turn on Audit logging for reporting and investigation</span></span>

<span data-ttu-id="74f67-147">감사 로깅을 일찍 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="74f67-147">Start your audit logging early.</span></span> <span data-ttu-id="74f67-148">다음과 같은 특정 단계에 대해서는 감사를 **설정** 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="74f67-148">You'll need auditing to be **ON** for certain of the steps that follow.</span></span> <span data-ttu-id="74f67-149">감사 로깅은 [Exchange Online](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/exchange-online-service-description)이 포함 된 구독에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="74f67-149">Audit logging is available in subscriptions that include [Exchange Online](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/exchange-online-service-description).</span></span> <span data-ttu-id="74f67-150">[보안 대시보드](security-dashboard.md), [전자 메일 보안 보고서](view-email-security-reports.md)및 [탐색기](threat-explorer.md)와 같은 위협 보호 보고서의 데이터를 보려면 감사 로깅이 *설정*되어 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="74f67-150">In order to view data in threat protection reports, such as the [Security Dashboard](security-dashboard.md), [email security reports](view-email-security-reports.md), and [Explorer](threat-explorer.md), audit logging must be *On*.</span></span> <span data-ttu-id="74f67-151">자세한 내용은 [Turn audit log search on or off](../../compliance/turn-audit-log-search-on-or-off.md)를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="74f67-151">To learn more, see [Turn audit log search on or off](../../compliance/turn-audit-log-search-on-or-off.md).</span></span>

## <a name="part-1---anti-malware-protection"></a><span data-ttu-id="74f67-152">1 부-맬웨어 방지 보호 기능</span><span class="sxs-lookup"><span data-stu-id="74f67-152">Part 1 - Anti-malware protection</span></span>

<span data-ttu-id="74f67-153">[맬웨어 방지 보호](anti-malware-protection.md) 는 [EOP](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description)을 포함 하는 구독에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="74f67-153">[Anti-malware protection](anti-malware-protection.md) is available in subscriptions that include [EOP](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description).</span></span>

1. <span data-ttu-id="74f67-154">[보안 & 준수 센터](https://protection.office.com)에서 **위협 관리**  >  **정책**  >  **맬웨어 방지**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="74f67-154">In the [Security & Compliance Center](https://protection.office.com), choose **Threat management** > **Policy** > **Anti-malware**.</span></span>

2. <span data-ttu-id="74f67-155">**기본** 정책을 두 번 클릭 한 다음 **설정을**선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="74f67-155">Double-click the **Default** policy, and then choose **settings**.</span></span>

3. <span data-ttu-id="74f67-156">다음 설정을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="74f67-156">Specify the following settings:</span></span>

    - <span data-ttu-id="74f67-157">**맬웨어 검색 응답** 섹션에서 기본 설정인 **아니요**를 그대로 둡니다.</span><span class="sxs-lookup"><span data-stu-id="74f67-157">In the **Malware Detection Response** section, keep the default setting of **No**.</span></span>

    - <span data-ttu-id="74f67-158">**일반 첨부 파일 형식 필터** 섹션에서 **설정**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="74f67-158">In the **Common Attachment Types Filter** section, choose **On**.</span></span>

4. <span data-ttu-id="74f67-159">**저장**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="74f67-159">Click **Save**.</span></span>

<span data-ttu-id="74f67-160">맬웨어 방지 정책 옵션에 대 한 자세한 내용은 [맬웨어 방지 정책 구성을](configure-anti-malware-policies.md)참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="74f67-160">To learn more about anti-malware policy options, see [Configure anti-malware policies](configure-anti-malware-policies.md).</span></span>

## <a name="part-2---anti-phishing-protection"></a><span data-ttu-id="74f67-161">2 부-피싱 방지 보호 기능</span><span class="sxs-lookup"><span data-stu-id="74f67-161">Part 2 - Anti-phishing protection</span></span>

<span data-ttu-id="74f67-162">[피싱 방지]</span><span class="sxs-lookup"><span data-stu-id="74f67-162">[Anti-phishing]</span></span>

<span data-ttu-id="74f67-163">[피싱 방지 보호](anti-phishing-protection.md) 기능은 [EOP](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description)을 포함 하는 구독에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="74f67-163">[Anti-phishing protection](anti-phishing-protection.md) is available in subscriptions that include [EOP](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description).</span></span> <span data-ttu-id="74f67-164">고급 피싱 방지 보호는 [ATP](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description)에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="74f67-164">Advanced anti-phishing protection is available in [ATP](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description).</span></span>

<span data-ttu-id="74f67-165">다음 절차에서는 ATP 피싱 방지 정책을 구성 하는 방법에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="74f67-165">The following procedure describes how to configure an ATP anti-phishing policy.</span></span> <span data-ttu-id="74f67-166">이 단계는 피싱 방지 정책 (ATP 없이)을 구성 하는 경우에도 비슷합니다.</span><span class="sxs-lookup"><span data-stu-id="74f67-166">The steps are similar for configuring an anti-phishing policy (without ATP).</span></span>

1. <span data-ttu-id="74f67-167">[보안 & 준수 센터](https://protection.office.com)에서 **위협 관리**  >  **정책**  >  **ATP 피싱 방지**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="74f67-167">In the [Security & Compliance Center](https://protection.office.com), choose **Threat management** > **Policy** > **ATP anti-phishing**.</span></span>

2. <span data-ttu-id="74f67-168">**기본 정책을**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="74f67-168">Click **Default policy**.</span></span>

3. <span data-ttu-id="74f67-169">**가장** 섹션에서 **편집**을 클릭 하 고 다음 설정을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="74f67-169">In the **Impersonation** section, click **Edit**, and then specify the following settings:</span></span>

   - <span data-ttu-id="74f67-170">**보호할 사용자 추가** 탭 *에서 보호를* 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="74f67-170">On the **Add users to protect** tab, turn *On* protection.</span></span> <span data-ttu-id="74f67-171">그런 다음 조직의 보드 구성원, CEO, CFO 및 기타 선임 리더와 같은 사용자를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="74f67-171">Then add users, such as your organization's board members, your CEO, CFO, and other senior leaders.</span></span> <span data-ttu-id="74f67-172">(개별 전자 메일 주소를 입력 하거나를 클릭 하 여 목록을 표시할 수 있습니다.)</span><span class="sxs-lookup"><span data-stu-id="74f67-172">(You can type an individual email address, or click to display a list.)</span></span>

   - <span data-ttu-id="74f67-173">**보호할 도메인 추가** 탭에서 **자신이 소유한 도메인을 자동으로 포함**을 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="74f67-173">On the **Add domains to protect** tab, turn on **Automatically include the domains I own**.</span></span> <span data-ttu-id="74f67-174">사용자 지정 도메인이 있는 경우 지금 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="74f67-174">If you have custom domains, add them now.</span></span>

   - <span data-ttu-id="74f67-175">**작업** 탭에서 **가장 된 사용자** 및 **가장 도메인** 옵션 둘 다에 대해 **메시지 격리** 를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="74f67-175">On the **Actions** tab, select **Quarantine the message** for both the **impersonated user** and **impersonated domain** options.</span></span> <span data-ttu-id="74f67-176">또한 가장 안전한 팁을 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="74f67-176">Also, turn on impersonation safety tips.</span></span>

   - <span data-ttu-id="74f67-177">**사서함** 인텔리전스 탭에서 사서함 인텔리전스가 설정 되어 있고 사서함 인텔리전스 기반 가장을 사용 하도록 설정 되어 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="74f67-177">On the **Mailbox intelligence** tab, make sure mailbox intelligence is turned on and turn on mailbox intelligence-based impersonation protection.</span></span> <span data-ttu-id="74f67-178">가장 된 **사용자 목록이 전자 메일을 보낸 경우** 에는 **메시지 격리**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="74f67-178">In the **If email is sent by an impersonated user** list, choose **Quarantine the message**.</span></span>

   - <span data-ttu-id="74f67-179">**신뢰할 수 있는 보낸 사람 및 도메인 추가** 탭에서 추가 하려는 신뢰할 수 있는 보낸 사람 또는 도메인을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="74f67-179">On the **Add trusted senders and domains** tab, specify any trusted senders or domains that you want to add.</span></span>

   - <span data-ttu-id="74f67-180">설정을 검토 한 후에 **설정 검토** 탭에서 **저장** 합니다.</span><span class="sxs-lookup"><span data-stu-id="74f67-180">**Save** on the **Review your settings** tab after you've reviewed your settings.</span></span>

4. <span data-ttu-id="74f67-181">**스푸핑** 섹션에서 **편집**을 클릭 하 고 다음 설정을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="74f67-181">In the **Spoof** section, click **Edit**, and then specify the following settings:</span></span>

   - <span data-ttu-id="74f67-182">**스푸핑 필터 설정** 탭에서 스푸핑 방지 보호가 설정 되어 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="74f67-182">On the **Spoofing filter settings** tab, make sure anti-spoofing protection is turned on.</span></span>

   - <span data-ttu-id="74f67-183">**작업** 탭에서 **메시지 격리**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="74f67-183">On the **Actions** tab, choose **Quarantine the message**.</span></span>

   - <span data-ttu-id="74f67-184">변경 내용을 검토 한 후에는 **설정 검토** 탭에서 **저장** 합니다.</span><span class="sxs-lookup"><span data-stu-id="74f67-184">**Save** on the **Review your settings** tab after you have reviewed your changes.</span></span> <span data-ttu-id="74f67-185">변경 하지 않은 경우 **취소**를 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="74f67-185">(If you didn't make any changes, **Cancel**.)</span></span>

5. <span data-ttu-id="74f67-186">기본 정책 설정 페이지를 닫습니다.</span><span class="sxs-lookup"><span data-stu-id="74f67-186">Close the default policy settings page.</span></span>

<span data-ttu-id="74f67-187">피싱 방지 정책 옵션에 대 한 자세한 내용은 [ATP 피싱 방지 정책 구성을](configure-atp-anti-phishing-policies.md)참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="74f67-187">To learn more about your anti-phishing policy options, see [Configure ATP anti-phishing policies](configure-atp-anti-phishing-policies.md).</span></span>

## <a name="part-3---anti-spam-protection"></a><span data-ttu-id="74f67-188">3 부-스팸 방지 보호 기능</span><span class="sxs-lookup"><span data-stu-id="74f67-188">Part 3 - Anti-spam protection</span></span>

<span data-ttu-id="74f67-189">[스팸 방지 보호](anti-spam-protection.md) 기능은 [EOP](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description)을 포함 하는 구독에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="74f67-189">[Anti-spam protection](anti-spam-protection.md) is available in subscriptions that include [EOP](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description).</span></span>

1. <span data-ttu-id="74f67-190">[보안 & 준수 센터](https://protection.office.com)에서 **위협 관리**  >  **정책**  >  **스팸 방지**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="74f67-190">In the [Security & Compliance Center](https://protection.office.com), choose **Threat management** > **Policy** > **Anti-spam**.</span></span>

2. <span data-ttu-id="74f67-191">**사용자 지정** 탭에서 사용자 지정 설정을 켭니다.</span><span class="sxs-lookup"><span data-stu-id="74f67-191">On the **Custom** tab, turn on Custom settings.</span></span>

3. <span data-ttu-id="74f67-192">**기본 스팸 필터 정책을**확장 하 고 **정책 편집**을 클릭 한 후 다음 설정을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="74f67-192">Expand **Default spam filter policy**, click **Edit policy**, and then specify the following settings:</span></span>

   - <span data-ttu-id="74f67-193">**스팸 및 대량 작업** 섹션에서 임계값을 5 또는 6으로 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="74f67-193">In the **Spam and bulk actions** section, set the threshold to a value of 5 or 6.</span></span>

   - <span data-ttu-id="74f67-194">**허용 목록** 섹션에서 허용 되는 보낸 사람 및 도메인을 검토 (및/또는 편집) 합니다.</span><span class="sxs-lookup"><span data-stu-id="74f67-194">In the **Allow lists** section, review (and/or edit) your allowed senders and domains.</span></span>

4. <span data-ttu-id="74f67-195">**저장**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="74f67-195">Click **Save**.</span></span>

<span data-ttu-id="74f67-196">스팸 방지 정책 옵션에 대 한 자세한 내용은 [EOP에서 스팸 방지 정책 구성을](configure-your-spam-filter-policies.md)참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="74f67-196">To learn more about your anti-spam policy options, see [Configure anti-spam policies in EOP](configure-your-spam-filter-policies.md).</span></span>

## <a name="part-4---protection-from-malicious-urls-and-files-safe-links-and-safe-attachments"></a><span data-ttu-id="74f67-197">4 부-악성 Url 및 파일의 보호 (안전한 링크 및 안전 첨부 파일)</span><span class="sxs-lookup"><span data-stu-id="74f67-197">Part 4 - Protection from malicious URLs and files (Safe Links and Safe Attachments)</span></span>

<span data-ttu-id="74f67-198">악성 Url 및 파일 로부터의 클릭 시간 보호는 ATP ( [Office 365 ATP](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description) )를 포함 하는 구독에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="74f67-198">Time-of-click protection from malicious URLs and files is available in subscriptions that include [Office 365 ATP](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description) (ATP).</span></span> <span data-ttu-id="74f67-199">[Atp 안전한 첨부 파일](atp-safe-attachments.md) 및 [atp 안전한 링크](atp-safe-links.md) 정책을 통해 설정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="74f67-199">It's set up through [ATP Safe Attachments](atp-safe-attachments.md) and [ATP Safe Links](atp-safe-links.md) policies.</span></span>

### <a name="atp-safe-attachments-policies"></a><span data-ttu-id="74f67-200">ATP 안전한 첨부 파일 정책</span><span class="sxs-lookup"><span data-stu-id="74f67-200">ATP Safe Attachments policies</span></span>

<span data-ttu-id="74f67-201">[Atp 안전한 첨부 파일](atp-safe-attachments.md)을 설정 하려면 Atp 안전 첨부 파일 정책을 하나 이상 정의 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="74f67-201">To set up [ATP Safe Attachments](atp-safe-attachments.md), you must define at least one ATP Safe Attachments policy.</span></span>

1. <span data-ttu-id="74f67-202">[보안 & 준수 센터](https://protection.office.com)에서 **위협 관리**  >  **정책**  >  **ATP 안전한 첨부 파일**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="74f67-202">In the [Security & Compliance Center](https://protection.office.com), choose **Threat management** > **Policy** > **ATP safe attachments**.</span></span>

2. <span data-ttu-id="74f67-203">**SharePoint, OneDrive 및 Microsoft 팀에 대 한 ATP 설정**옵션을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="74f67-203">Select the option **Turn on ATP for SharePoint, OneDrive, and Microsoft Teams**.</span></span>

3. <span data-ttu-id="74f67-204">**전자 메일 첨부 파일 보호** 섹션에서 더하기 기호 ()를 클릭 **+** 합니다.</span><span class="sxs-lookup"><span data-stu-id="74f67-204">In the **Protect email attachments** section, click the plus sign (**+**).</span></span>

4. <span data-ttu-id="74f67-205">다음 설정을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="74f67-205">Specify the following settings:</span></span>

   - <span data-ttu-id="74f67-206">**이름** 상자에를 입력 `Block malware` 합니다.</span><span class="sxs-lookup"><span data-stu-id="74f67-206">In the **Name** box, type `Block malware`.</span></span>

   - <span data-ttu-id="74f67-207">응답 섹션에서 **차단을**선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="74f67-207">In the response section, choose **Block**.</span></span>

   - <span data-ttu-id="74f67-208">**첨부 파일 리디렉션** 섹션에서 **리디렉션 사용**옵션을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="74f67-208">In the **Redirect attachment** section, select the option **Enable redirect**.</span></span> <span data-ttu-id="74f67-209">검색 된 파일을 검토할 사용자 조직의 보안 관리자 또는 운영자의 전자 메일 주소를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="74f67-209">Specify the email address for your organization's security administrator or operator, who will review detected files.</span></span>

   - <span data-ttu-id="74f67-210">**적용 대상** 섹션에서 **받는 사람 도메인**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="74f67-210">In the **Applied to** section, choose **The recipient domain is**.</span></span> <span data-ttu-id="74f67-211">그런 다음 도메인을 선택 하 고 **추가**, **확인**을 차례로 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="74f67-211">Then, select your domain, choose **Add**, and then **OK**.</span></span>

5. <span data-ttu-id="74f67-212">**저장**을 합니다.</span><span class="sxs-lookup"><span data-stu-id="74f67-212">**Save**.</span></span>

6. <span data-ttu-id="74f67-213">(**권장 추가 단계**) 전역 관리자 또는 SharePoint Online 관리자는 Microsoft 365 환경에 대해 **DisallowInfectedFileDownload** 매개 변수를 *true* 로 설정 하 여 **[set-spotenant](https://docs.microsoft.com/powershell/module/sharepoint-online/Set-SPOTenant)** cmdlet을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="74f67-213">(**Recommended additional step**) As a global administrator or a SharePoint Online administrator, run the **[Set-SPOTenant](https://docs.microsoft.com/powershell/module/sharepoint-online/Set-SPOTenant)** cmdlet with the **DisallowInfectedFileDownload** parameter set to  *true* for your Microsoft 365 environment.</span></span> <span data-ttu-id="74f67-214">따라서 사용자가 악성 파일로 검색 된 파일을 열거나 이동 하거나 복사 하거나 공유할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="74f67-214">(This prevents people from opening, moving, copying, or sharing files that are detected as malicious.)</span></span>

<span data-ttu-id="74f67-215">자세한 내용은 [office 365 Atp 안전한 첨부 파일 정책 설정](set-up-atp-safe-attachments-policies.md) 및 [SharePoint, OneDrive 및 Microsoft 팀에 대 한 Office 365 atp 켜기](turn-on-atp-for-spo-odb-and-teams.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="74f67-215">To learn more, see [Set up Office 365 ATP Safe Attachments policies](set-up-atp-safe-attachments-policies.md) and [Turn on Office 365 ATP for SharePoint, OneDrive, and Microsoft Teams](turn-on-atp-for-spo-odb-and-teams.md).</span></span>

### <a name="atp-safe-links-policies"></a><span data-ttu-id="74f67-216">ATP 안전한 링크 정책</span><span class="sxs-lookup"><span data-stu-id="74f67-216">ATP Safe Links policies</span></span>

<span data-ttu-id="74f67-217">[ATP 안전한 링크](atp-safe-links.md)를 설정 하려면 기본 정책을 검토 및 편집 하 고 특정 사용자에 대 한 정책을 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="74f67-217">To set up [ATP Safe Links](atp-safe-links.md), review and edit your default policy, and add a policy for specific users.</span></span>

1. <span data-ttu-id="74f67-218">[보안 & 준수 센터](https://protection.office.com)에서 **위협 관리**  >  **정책**  >  **ATP 안전한 링크**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="74f67-218">In the [Security & Compliance Center](https://protection.office.com), choose **Threat management** > **Policy** > **ATP Safe Links**.</span></span>

2. <span data-ttu-id="74f67-219">**기본** 정책을 두 번 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="74f67-219">Double-click the **Default** policy.</span></span>

3. <span data-ttu-id="74f67-220">다음 **의 안전한 링크 사용** 섹션에서 **Microsoft 365 Apps For enterprise For iOS 및 Android**의 옵션을 선택 하 고 **저장**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="74f67-220">In the **Use safe links in** section, select the option **Microsoft 365 Apps for enterprise, Office for iOS and Android**, and then click **Save**.</span></span>

4. <span data-ttu-id="74f67-221">**특정 받는 사람에 게 적용 되는 정책** 섹션에서 더하기 기호 ()를 클릭 **+** 합니다.</span><span class="sxs-lookup"><span data-stu-id="74f67-221">In the **Policies that apply to specific recipients** section, click the plus sign (**+**).</span></span>

5. <span data-ttu-id="74f67-222">다음 설정을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="74f67-222">Specify the following settings:</span></span>

   - <span data-ttu-id="74f67-223">**이름** 상자에 이름을 입력 `Safe Links` 합니다.</span><span class="sxs-lookup"><span data-stu-id="74f67-223">In the **Name** box, type a name, such as `Safe Links`.</span></span>

   - <span data-ttu-id="74f67-224">**작업 선택** 섹션에서 **설정**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="74f67-224">In the **Select the action** section, choose **On**.</span></span>

   - <span data-ttu-id="74f67-225">다음 옵션을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="74f67-225">Select these options:</span></span>

     - <span data-ttu-id="74f67-226">**다운로드 가능한 콘텐츠를 검색 하기 위해 안전한 첨부 파일 사용**</span><span class="sxs-lookup"><span data-stu-id="74f67-226">**Use safe attachments to scan downloadable content**</span></span>

     - <span data-ttu-id="74f67-227">**조직 내에서 전송 된 전자 메일 메시지에 안전한 링크 적용**</span><span class="sxs-lookup"><span data-stu-id="74f67-227">**Apply safe links to email messages sent within the organization**</span></span>

     - <span data-ttu-id="74f67-228">**사용자가 원본 URL에 대 한 안전한 링크를 클릭 하는 것을 허용 하지 않음**</span><span class="sxs-lookup"><span data-stu-id="74f67-228">**Do not let users click through safe links to original URL**</span></span>

   - <span data-ttu-id="74f67-229">**적용 대상** 섹션에서 **받는 사람 도메인**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="74f67-229">In the **Applied to** section, choose **The recipient domain is**.</span></span> <span data-ttu-id="74f67-230">그런 다음 도메인을 선택 하 고 **추가**, **확인**을 차례로 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="74f67-230">Then, select your domain, choose **Add**, and then **OK**.</span></span>

6. <span data-ttu-id="74f67-231">**저장**을 합니다.</span><span class="sxs-lookup"><span data-stu-id="74f67-231">**Save**.</span></span>

<span data-ttu-id="74f67-232">자세한 내용은 [Office 365 ATP 안전한 링크 정책 설정](set-up-atp-safe-links-policies.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="74f67-232">To learn more, see [Set up Office 365 ATP Safe Links policies](set-up-atp-safe-links-policies.md).</span></span>

## <a name="part-5---turn-on-atp-for-sharepoint-onedrive-and-microsoft-teams-workloads"></a><span data-ttu-id="74f67-233">제 5 부-SharePoint, OneDrive 및 Microsoft 팀 작업에 대 한 ATP 켜기</span><span class="sxs-lookup"><span data-stu-id="74f67-233">Part 5 - Turn on ATP for SharePoint, OneDrive, and Microsoft Teams workloads</span></span>

<span data-ttu-id="74f67-234">SharePoint, OneDrive 및 팀과 같은 워크 로드는 공동 작업을 위해 빌드됩니다.</span><span class="sxs-lookup"><span data-stu-id="74f67-234">Workloads like SharePoint, OneDrive, and Teams are built for collaboration.</span></span> <span data-ttu-id="74f67-235">ATP를 사용 하면 팀 사이트 및 문서 라이브러리에서 해로운 것으로 식별 된 파일을 차단 하 고 검색할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="74f67-235">Using ATP helps with blocking and detection of files that are identified as malicious in team sites and document libraries.</span></span> <span data-ttu-id="74f67-236">여기서 작동 하는 방법에 대 한 자세한 내용은 [여기](https://docs.microsoft.com/microsoft-365/security/office-365-security/atp-for-spo-odb-and-teams?view=o365-worldwide)에서 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="74f67-236">You can read more about how that works [here](https://docs.microsoft.com/microsoft-365/security/office-365-security/atp-for-spo-odb-and-teams?view=o365-worldwide).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="74f67-237">**이 절차를 시작 하기 전에 Microsoft 365 환경에 대해 감사 로깅이 이미 설정 되어 있는지 확인**합니다.</span><span class="sxs-lookup"><span data-stu-id="74f67-237">**Before you begin this procedure, make sure that audit logging is already turned on for your Microsoft 365 environment**.</span></span> <span data-ttu-id="74f67-238">이 작업은 일반적으로 Exchange Online에서 감사 로그 역할이 할당 된 사용자가 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="74f67-238">This is typically done by someone who has the Audit Logs role assigned in Exchange Online.</span></span> <span data-ttu-id="74f67-239">자세한 내용은 [Turn 감사 로그 검색 켜기 또는 끄기를](../../compliance/turn-audit-log-search-on-or-off.md)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="74f67-239">For more information, see [Turn audit log search on or off](../../compliance/turn-audit-log-search-on-or-off.md)!</span></span>

1. <span data-ttu-id="74f67-240">으로 이동 하 여 <https://protection.office.com> 회사 또는 학교 계정으로 로그인 합니다.</span><span class="sxs-lookup"><span data-stu-id="74f67-240">Go to <https://protection.office.com>, and sign in with your work or school account.</span></span>

2. <span data-ttu-id="74f67-241">보안 & 준수 센터의 왼쪽 탐색 창에 있는 **위협 관리**에서 **정책** \> **안전한 첨부 파일**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="74f67-241">In the Security & Compliance Center, in the left navigation pane, under **Threat management**, choose **Policy** \> **Safe Attachments**.</span></span>

   ![보안 & 준수 센터에서 위협 관리 \> 정책 선택](../../media/08849c91-f043-4cd1-a55e-d440c86442f2.png)

3. <span data-ttu-id="74f67-243">**SharePoint, OneDrive 및 Microsoft 팀에 대해 ATP 사용**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="74f67-243">Select **Turn on ATP for SharePoint, OneDrive, and Microsoft Teams**.</span></span>

   ![SharePoint Online, 비즈니스용 OneDrive 및 Microsoft 팀에 대 한 Advanced Threat Protection 설정](../../media/48cfaace-59cc-4e60-bf86-05ff6b99bdbf.png)

4. <span data-ttu-id="74f67-245">**저장**을 합니다.</span><span class="sxs-lookup"><span data-stu-id="74f67-245">**Save**.</span></span>

5. <span data-ttu-id="74f67-246">조직의 [안전한 첨부 파일 정책](set-up-atp-safe-attachments-policies.md) 및 [안전한 링크 정책을](set-up-atp-safe-links-policies.md)검토 하 고 적절 하 게 편집 합니다.</span><span class="sxs-lookup"><span data-stu-id="74f67-246">Review (and, as appropriate, edit) your organization's [Safe Attachments policies](set-up-atp-safe-attachments-policies.md) and [Safe Links policies](set-up-atp-safe-links-policies.md).</span></span>

6. <span data-ttu-id="74f67-247">는 전역 관리자 또는 SharePoint Online 관리자는 _DisallowInfectedFileDownload_ 매개 변수를로 설정 하 여 **[set-spotenant](https://docs.microsoft.com/powershell/module/sharepoint-online/Set-SPOTenant)** cmdlet을 실행 합니다 `$true` .</span><span class="sxs-lookup"><span data-stu-id="74f67-247">(Recommended) As a global administrator or a SharePoint Online administrator, run the **[Set-SPOTenant](https://docs.microsoft.com/powershell/module/sharepoint-online/Set-SPOTenant)** cmdlet with the _DisallowInfectedFileDownload_ parameter set to `$true`.</span></span>

   - <span data-ttu-id="74f67-248">`$true` 검색 된 파일에 대 한 모든 작업 (삭제 제외)을 차단 합니다.</span><span class="sxs-lookup"><span data-stu-id="74f67-248">`$true` blocks all actions (except Delete) for detected files.</span></span> <span data-ttu-id="74f67-249">사용자가 검색 된 파일을 열거나, 이동 하거나, 복사 하거나, 공유할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="74f67-249">People cannot open, move, copy, or share detected files.</span></span>
   - <span data-ttu-id="74f67-250">`$false` 삭제 및 다운로드를 제외한 모든 작업을 차단 합니다.</span><span class="sxs-lookup"><span data-stu-id="74f67-250">`$false` blocks all actions except Delete and Download.</span></span> <span data-ttu-id="74f67-251">사용자는 위험을 수락 하 고 검색 된 파일을 다운로드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="74f67-251">People can choose to accept the risk and download a detected file.</span></span>

   > [!TIP]
   > <span data-ttu-id="74f67-252">Microsoft 365에서 PowerShell을 사용 하는 방법에 대 한 자세한 내용은 PowerShell을 사용 하 여 [microsoft 365 관리](https://docs.microsoft.com/microsoft-365/enterprise/manage-microsoft-365-with-microsoft-365-powershell)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="74f67-252">To learn more about using PowerShell with Microsoft 365, see [Manage Microsoft 365 with PowerShell](https://docs.microsoft.com/microsoft-365/enterprise/manage-microsoft-365-with-microsoft-365-powershell).</span></span>

7. <span data-ttu-id="74f67-253">변경 내용이 모든 Microsoft 365 데이터 센터에 전파 되는 데 최대 30 분 정도 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="74f67-253">Allow up to 30 minutes for your changes to spread to all Microsoft 365 datacenters.</span></span>

### <a name="now-set-up-alerts-for-detected-files"></a><span data-ttu-id="74f67-254">이제 검색 된 파일에 대 한 알림을 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="74f67-254">Now set up alerts for detected files</span></span>

<span data-ttu-id="74f67-255">SharePoint Online의 파일 (비즈니스용 OneDrive 또는 Microsoft 팀)이 악성으로 식별 된 경우 알림을 받으려면 알림을 설정 하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="74f67-255">To receive notification when a file in SharePoint Online, OneDrive for Business, or Microsoft Teams has been identified as malicious, you can set up an alert.</span></span>

1. <span data-ttu-id="74f67-256">[보안 & 준수 센터](https://protection.office.com) **에서 경고를** \> **관리**합니다 .를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="74f67-256">In the [Security & Compliance Center](https://protection.office.com), choose **Alerts** \> **Manage alerts**.</span></span>

2. <span data-ttu-id="74f67-257">**새 경고 정책을**선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="74f67-257">Choose **New alert policy**.</span></span>

3. <span data-ttu-id="74f67-258">알림의 이름을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="74f67-258">Specify a name for the alert.</span></span> <span data-ttu-id="74f67-259">예를 들어 라이브러리에 유해한 파일을 입력할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="74f67-259">For example, you could type Malicious Files in Libraries.</span></span>

4. <span data-ttu-id="74f67-260">경고에 대 한 설명을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="74f67-260">Type a description for the alert.</span></span> <span data-ttu-id="74f67-261">예를 들어 SharePoint Online, OneDrive 또는 Microsoft 팀에서 악성 파일이 검색 되 면 관리자에 게 알림 메시지를 입력할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="74f67-261">For example, you could type Notifies admins when malicious files are detected in SharePoint Online, OneDrive, or Microsoft Teams.</span></span>

5. <span data-ttu-id="74f67-262">다음 **경우에이 알림 보내기** 섹션에서 다음을 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="74f67-262">In the **Send this alert when...** section, set:</span></span>

   <span data-ttu-id="74f67-263">a.</span><span class="sxs-lookup"><span data-stu-id="74f67-263">a.</span></span> <span data-ttu-id="74f67-264">**작업** 목록에서 **검색 된 맬웨어를 파일에서**선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="74f67-264">In the **Activities** list, choose **Detected malware in file**.</span></span>

   <span data-ttu-id="74f67-265">b.</span><span class="sxs-lookup"><span data-stu-id="74f67-265">b.</span></span> <span data-ttu-id="74f67-266">**Users** 필드는 비워 둡니다.</span><span class="sxs-lookup"><span data-stu-id="74f67-266">Leave the **Users** field empty.</span></span>

6. <span data-ttu-id="74f67-267">**이 알림 보내기** ... 섹션에서 악의적인 파일이 검색 되 면 알림을 받을 전역 관리자, 보안 관리자 또는 보안 판독기를 하나 이상 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="74f67-267">In the **Send this alert to...** section, select one or more global administrators, security administrators, or security readers who should receive notification when a malicious file is detected.</span></span>

7. <span data-ttu-id="74f67-268">**저장**을 합니다.</span><span class="sxs-lookup"><span data-stu-id="74f67-268">**Save**.</span></span>

<span data-ttu-id="74f67-269">경고에 대 한 자세한 내용은 [보안 & 준수 센터에서 활동 경고 만들기](../../compliance/create-activity-alerts.md)를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="74f67-269">To learn more about alerts, see [Create activity alerts in the Security & Compliance Center](../../compliance/create-activity-alerts.md).</span></span>

> [!NOTE]
> <span data-ttu-id="74f67-270">구성을 마친 후에는 다음 링크를 사용 하 여 작업 조사를 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="74f67-270">When you're finished configuring, use these links to start workload investigations:</span></span>
>
> - [<span data-ttu-id="74f67-271">SharePoint, OneDrive 또는 Microsoft Teams에서 감지한 악성 파일에 대한 정보 보기</span><span class="sxs-lookup"><span data-stu-id="74f67-271">View information about malicious files detected in SharePoint, OneDrive, or Microsoft Teams</span></span>](malicious-files-detected-in-spo-odb-or-teams.md)
> - [<span data-ttu-id="74f67-272">SharePoint Online, OneDrive 또는 Microsoft 팀에서 악의적인 파일을 찾을 때 수행할 작업</span><span class="sxs-lookup"><span data-stu-id="74f67-272">What to do when a malicious file is found in SharePoint Online, OneDrive, or Microsoft Teams</span></span>](https://support.microsoft.com/office/01e902ad-a903-4e0f-b093-1e1ac0c37ad2)
> - [<span data-ttu-id="74f67-273">Microsoft 365에서 격리 된 메시지 및 파일을 관리자 권한으로 관리</span><span class="sxs-lookup"><span data-stu-id="74f67-273">Manage quarantined messages and files as an administrator in Microsoft 365</span></span>](manage-quarantined-messages-and-files.md)

## <a name="part-6---additional-settings-to-configure"></a><span data-ttu-id="74f67-274">6 부-구성할 추가 설정</span><span class="sxs-lookup"><span data-stu-id="74f67-274">Part 6 - Additional settings to configure</span></span>

<span data-ttu-id="74f67-275">맬웨어, 악성 Url, 파일, 피싱 및 스팸 으로부터 보호를 구성 하는 것과 함께 0 시간 자동 삭제를 구성 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="74f67-275">Along with configuring protection from malware, malicious URLs and files, phishing, and spam, we recommend you configure zero-hour auto purge.</span></span>

### <a name="zero-hour-auto-purge-for-email-in-eop"></a><span data-ttu-id="74f67-276">EOP의 전자 메일에 대 한 제로 시간 자동 삭제</span><span class="sxs-lookup"><span data-stu-id="74f67-276">Zero-hour auto purge for email in EOP</span></span>

<span data-ttu-id="74f67-277">[EOP](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description)을 포함 하는 구독에서 [0 시간 자동 삭제](zero-hour-auto-purge.md) (ZAP)를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="74f67-277">[Zero-hour auto purge](zero-hour-auto-purge.md) (ZAP) is available in subscriptions that include [EOP](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description).</span></span> <span data-ttu-id="74f67-278">이 보호 기능은 기본적으로 설정 되어 있습니다. 그러나 보호 기능을 적용 하려면 다음 조건을 충족 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="74f67-278">This protection is turned on by default; however, the following conditions must be met for protection to be in effect:</span></span>

- <span data-ttu-id="74f67-279">스팸 [방지 정책](anti-spam-protection.md)에서 **정크 메일 폴더로 메시지를 이동** 하도록 스팸 작업을 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="74f67-279">Spam actions are set to **Move message to Junk Email folder** in [anti-spam policies](anti-spam-protection.md).</span></span>

- <span data-ttu-id="74f67-280">사용자가 기본 [정크 메일 설정을](ensure-that-spam-is-routed-to-each-user-s-junk-email-folder.md)유지 하 고 정크 메일 보호 기능을 해제 하지 않은 경우</span><span class="sxs-lookup"><span data-stu-id="74f67-280">Users have kept their default [junk email settings](ensure-that-spam-is-routed-to-each-user-s-junk-email-folder.md), and haven't turned off junk email protection.</span></span>

<span data-ttu-id="74f67-281">자세한 내용은 스팸 및 맬웨어를 방지 하는 [0 시간 자동 삭제](zero-hour-auto-purge.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="74f67-281">To learn more, see [Zero-hour auto purge - protection against spam and malware](zero-hour-auto-purge.md).</span></span>

## <a name="post-setup-tasks-and-next-steps"></a><span data-ttu-id="74f67-282">설치 후 작업 및 다음 단계</span><span class="sxs-lookup"><span data-stu-id="74f67-282">Post-setup tasks and next steps</span></span>

<span data-ttu-id="74f67-283">위협 방지 기능을 구성한 후에는 이러한 기능이 작동 하는 방식을 모니터링 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="74f67-283">After configuring the threat protection features, make sure to monitor how those features are working!</span></span> <span data-ttu-id="74f67-284">필요한 작업을 수행 하도록 정책을 검토 하 고 수정 합니다.</span><span class="sxs-lookup"><span data-stu-id="74f67-284">Review and revise your policies so that they do what you need them to.</span></span> <span data-ttu-id="74f67-285">또한 값을 추가할 수 있는 새로운 기능 및 서비스 업데이트도 시청 하세요.</span><span class="sxs-lookup"><span data-stu-id="74f67-285">Also, watch for new features and service updates that can add value.</span></span>

****

|<span data-ttu-id="74f67-286">수행할 작업</span><span class="sxs-lookup"><span data-stu-id="74f67-286">What to do</span></span>|<span data-ttu-id="74f67-287">자세한 정보를 알아볼 수 있는 리소스</span><span class="sxs-lookup"><span data-stu-id="74f67-287">Resources to learn more</span></span>|
|---|---|
|<span data-ttu-id="74f67-288">보고서를 확인 하 여 조직에서 위협 방지 기능을 사용 하는 방법 보기</span><span class="sxs-lookup"><span data-stu-id="74f67-288">See how threat protection features are working for your organization by viewing reports</span></span>|[<span data-ttu-id="74f67-289">보안 대시보드</span><span class="sxs-lookup"><span data-stu-id="74f67-289">Security dashboard</span></span>](security-dashboard.md)<br/>[<span data-ttu-id="74f67-290">전자 메일 보안 보고서</span><span class="sxs-lookup"><span data-stu-id="74f67-290">Email security reports</span></span>](view-email-security-reports.md)<br/>[<span data-ttu-id="74f67-291">Office 365 ATP에 대 한 보고서</span><span class="sxs-lookup"><span data-stu-id="74f67-291">Reports for Office 365 ATP</span></span>](view-reports-for-atp.md)<br/>[<span data-ttu-id="74f67-292">위협 탐색기</span><span class="sxs-lookup"><span data-stu-id="74f67-292">Threat Explorer</span></span>](threat-explorer.md)|
|<span data-ttu-id="74f67-293">필요에 따라 위협 보호 정책 주기적으로 검토 및 수정</span><span class="sxs-lookup"><span data-stu-id="74f67-293">Periodically review and revise your threat protection policies as needed</span></span>|[<span data-ttu-id="74f67-294">Secure Score</span><span class="sxs-lookup"><span data-stu-id="74f67-294">Secure Score</span></span>](../mtp/microsoft-secure-score.md)<br/>[<span data-ttu-id="74f67-295">스마트 보고서 및 통찰력</span><span class="sxs-lookup"><span data-stu-id="74f67-295">Smart reports and insights</span></span>](reports-and-insights-in-security-and-compliance.md)<br/>[<span data-ttu-id="74f67-296">Microsoft 365 위협 조사 및 응답 기능</span><span class="sxs-lookup"><span data-stu-id="74f67-296">Microsoft 365 threat investigation and response features</span></span>](keep-users-safe-with-office-365-ti.md)|
|<span data-ttu-id="74f67-297">새로운 기능 및 서비스 업데이트 조사</span><span class="sxs-lookup"><span data-stu-id="74f67-297">Watch for new features and service updates</span></span>|[<span data-ttu-id="74f67-298">표준 및 대상 지정 된 릴리스 옵션</span><span class="sxs-lookup"><span data-stu-id="74f67-298">Standard and Targeted release options</span></span>](https://docs.microsoft.com/microsoft-365/admin/manage/release-options-in-office-365)<br/>[<span data-ttu-id="74f67-299">메시지 센터</span><span class="sxs-lookup"><span data-stu-id="74f67-299">Message Center</span></span>](https://docs.microsoft.com/microsoft-365/admin/manage/message-center)<br/>[<span data-ttu-id="74f67-300">Microsoft 365 로드맵</span><span class="sxs-lookup"><span data-stu-id="74f67-300">Microsoft 365 Roadmap</span></span>](https://www.microsoft.com/microsoft-365/roadmap?filters=&searchterms=advanced%2Cthreat%2Cprotection)<br/>[<span data-ttu-id="74f67-301">서비스 설명</span><span class="sxs-lookup"><span data-stu-id="74f67-301">Service Descriptions</span></span>](https://docs.microsoft.com/office365/servicedescriptions/office-365-service-descriptions-technet-library)|
|<span data-ttu-id="74f67-302">EOP 및 ATP에 대 한 권장 표준 및 엄격한 보안 구성에 대 한 세부 정보 알아보기</span><span class="sxs-lookup"><span data-stu-id="74f67-302">Learn the details about recommended Standard and Strict security configurations for EOP and ATP</span></span> | [<span data-ttu-id="74f67-303">EOP 및 Office 365 ATP 보안에 대 한 권장 설정</span><span class="sxs-lookup"><span data-stu-id="74f67-303">Recommended settings for EOP and Office 365 ATP security</span></span>](https://docs.microsoft.com/microsoft-365/security/office-365-security/recommended-settings-for-eop-and-office365-atp?view=o365-worldwide) |
