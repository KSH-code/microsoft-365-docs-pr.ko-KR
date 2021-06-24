---
title: Microsoft Defender의 위협으로부터 보호Office 365, 맬웨어 방지, 피싱 방지, 스팸 방지, 금고 링크, 금고 첨부 파일, ZAP(제로 아워 자동 제거), MDO 보안 구성
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: Admin
ms.topic: overview
localization_priority: Normal
ms.date: 06/22/2021
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
ms.openlocfilehash: 7e37b67dbed75e3283070ba94321fcb03979a5a6
ms.sourcegitcommit: ccbdf2638fc6646bfb89450169953f4c3ce4b9b0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/24/2021
ms.locfileid: "53105395"
---
# <a name="protect-against-threats"></a><span data-ttu-id="19c8d-103">위협에 대한 보호</span><span class="sxs-lookup"><span data-stu-id="19c8d-103">Protect against threats</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="19c8d-104">**적용 대상**</span><span class="sxs-lookup"><span data-stu-id="19c8d-104">**Applies to**</span></span>
- [<span data-ttu-id="19c8d-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="19c8d-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="19c8d-106">Office 365용 Microsoft Defender 플랜 1 및 플랜 2</span><span class="sxs-lookup"><span data-stu-id="19c8d-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="19c8d-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="19c8d-107">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

<span data-ttu-id="19c8d-108">다음은 2016에 대한 Defender의 구성을 청크로 Office 365 빠른 시작 가이드입니다.</span><span class="sxs-lookup"><span data-stu-id="19c8d-108">Here's a quick-start guide that breaks the configuration of Defender for Office 365 into chunks.</span></span> <span data-ttu-id="19c8d-109">새로운 위협 방지 기능을 Office 365 시작 위치를 잘 모를 수도 있으며, 를 수행하여 가장 잘 알 수 있는 경우 이 지침을 검사 목록 및 시작점으로 사용하세요.</span><span class="sxs-lookup"><span data-stu-id="19c8d-109">If you're new to threat protection features in Office 365, not sure where to begin, or if you learn best by *doing*, use this guidance as a checklist and a starting point.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="19c8d-110">**각 정책 종류에** 대한 초기 권장 설정이 포함되어 있습니다. 그러나 많은 옵션을 사용할 수 있으며 특정 조직의 요구에 맞게 설정을 조정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="19c8d-110">**Initial recommended settings are included for each kind of policy; however, many options are available, and you can adjust your settings to meet your specific organization's needs**.</span></span> <span data-ttu-id="19c8d-111">정책 또는 변경 사항이 데이터 센터를 통해 작동하도록 약 30분 동안 허용합니다.</span><span class="sxs-lookup"><span data-stu-id="19c8d-111">Allow approximately 30 minutes for your policies or changes to work their way through your datacenter.</span></span>
>
> <span data-ttu-id="19c8d-112">Defender for Office 365 대부분의 정책의 수동 구성을 건너뛰기 위해 표준 또는 엄격한 수준에서 미리 설정한 보안 정책을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="19c8d-112">To skip manual configuration of most policies in Defender for Office 365, you can use preset security policies at the Standard or Strict level.</span></span> <span data-ttu-id="19c8d-113">자세한 내용은 EOP에서 보안 정책 미리 설정 및 Microsoft [Defender for Office 365.](preset-security-policies.md)</span><span class="sxs-lookup"><span data-stu-id="19c8d-113">For more information, see [Preset security policies in EOP and Microsoft Defender for Office 365](preset-security-policies.md).</span></span>

## <a name="requirements"></a><span data-ttu-id="19c8d-114">요구 사항</span><span class="sxs-lookup"><span data-stu-id="19c8d-114">Requirements</span></span>

### <a name="subscriptions"></a><span data-ttu-id="19c8d-115">구독</span><span class="sxs-lookup"><span data-stu-id="19c8d-115">Subscriptions</span></span>

<span data-ttu-id="19c8d-116">위협 방지 기능은 모든 *Microsoft* 또는 Office 365 포함되어 있습니다. 그러나 일부 구독에는 고급 기능이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="19c8d-116">Threat protection features are included in *all* Microsoft or Office 365 subscriptions; however, some subscriptions have advanced features.</span></span> <span data-ttu-id="19c8d-117">아래 표에는 이 문서에 포함된 보호 기능과 최소 구독 요구 사항이 나열됩니다.</span><span class="sxs-lookup"><span data-stu-id="19c8d-117">The table below lists the protection features included in this article together with the minimum subscription requirements.</span></span>

> [!TIP]
> <span data-ttu-id="19c8d-118">감사를 켜는 지시 이상의 단계는  EOP(맬웨어 방지) 의 일부로 표시된 맬웨어 방지, 피싱방지 및 스팸 방지를 Office 365 Exchange Online Protection 있습니다.</span><span class="sxs-lookup"><span data-stu-id="19c8d-118">Notice that beyond the directions to turn on auditing, *steps* start anti-malware, anti-phishing, and anti-spam, which are marked as part of Office 365 Exchange Online Protection (**EOP**).</span></span> <span data-ttu-id="19c8d-119">(에 대한 **Defender** for Office 365) EOP를 포함하고 빌드할 때까지 이 문서에서 이 Office 365 이상한 것처럼 보일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="19c8d-119">This can seem odd in an Defender for Office 365 article, until you remember (**Defender for Office 365**) contains, and builds on, EOP.</span></span>

<br>

****

|<span data-ttu-id="19c8d-120">보호 유형</span><span class="sxs-lookup"><span data-stu-id="19c8d-120">Protection type</span></span>|<span data-ttu-id="19c8d-121">구독 요구 사항</span><span class="sxs-lookup"><span data-stu-id="19c8d-121">Subscription requirement</span></span>|
|---|---|
|<span data-ttu-id="19c8d-122">감사 로깅(보고 목적으로)</span><span class="sxs-lookup"><span data-stu-id="19c8d-122">Audit logging (for reporting purposes)</span></span>|[<span data-ttu-id="19c8d-123">Exchange Online</span><span class="sxs-lookup"><span data-stu-id="19c8d-123">Exchange Online</span></span>](/office365/servicedescriptions/exchange-online-service-description/exchange-online-service-description)|
|<span data-ttu-id="19c8d-124">맬웨어 방지 보호 기능</span><span class="sxs-lookup"><span data-stu-id="19c8d-124">Anti-malware protection</span></span>|<span data-ttu-id="19c8d-125">[](/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description) **Exchange Online Protection(EOP)**</span><span class="sxs-lookup"><span data-stu-id="19c8d-125">[Exchange Online Protection](/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description) (**EOP**)</span></span>|
|<span data-ttu-id="19c8d-126">피싱 방지 보호 기능</span><span class="sxs-lookup"><span data-stu-id="19c8d-126">Anti-phishing protection</span></span>|[<span data-ttu-id="19c8d-127">EOP</span><span class="sxs-lookup"><span data-stu-id="19c8d-127">EOP</span></span>](/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description)|
|<span data-ttu-id="19c8d-128">스팸 방지 보호 기능</span><span class="sxs-lookup"><span data-stu-id="19c8d-128">Anti-spam protection</span></span>|[<span data-ttu-id="19c8d-129">EOP</span><span class="sxs-lookup"><span data-stu-id="19c8d-129">EOP</span></span>](/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description)|
|<span data-ttu-id="19c8d-130">전자 메일 및 전자 메일 문서의 악의적인 URL 및 파일 보호(Office 금고 링크 및 금고 첨부 파일)</span><span class="sxs-lookup"><span data-stu-id="19c8d-130">Protection from malicious URLs and files in email and Office documents (Safe Links and Safe Attachments)</span></span>|[<span data-ttu-id="19c8d-131">Office 365용 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="19c8d-131">Microsoft Defender for Office 365</span></span>](/office365/servicedescriptions/office-365-advanced-threat-protection-service-description)|

### <a name="roles-and-permissions"></a><span data-ttu-id="19c8d-132">역할 및 사용 권한</span><span class="sxs-lookup"><span data-stu-id="19c8d-132">Roles and permissions</span></span>

<span data-ttu-id="19c8d-133">정책에 대해 Defender를 Office 365 적절한 역할을 할당해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="19c8d-133">To configure Defender for Office 365 policies, you must be assigned an appropriate role.</span></span> <span data-ttu-id="19c8d-134">아래 표에서 이러한 작업을 수행할 수 있는 역할을 확인하세요.</span><span class="sxs-lookup"><span data-stu-id="19c8d-134">Take a look at the table below for roles that can do these actions.</span></span>

<br>

****

|<span data-ttu-id="19c8d-135">역할 또는 역할 그룹</span><span class="sxs-lookup"><span data-stu-id="19c8d-135">Role or role group</span></span>|<span data-ttu-id="19c8d-136">자세한 내용을 알아보는 위치</span><span class="sxs-lookup"><span data-stu-id="19c8d-136">Where to learn more</span></span>|
|---|---|
|<span data-ttu-id="19c8d-137">전역 관리자</span><span class="sxs-lookup"><span data-stu-id="19c8d-137">global administrator</span></span>|[<span data-ttu-id="19c8d-138">Microsoft 365 관리자 역할 정보</span><span class="sxs-lookup"><span data-stu-id="19c8d-138">About Microsoft 365 admin roles</span></span>](../../admin/add-users/about-admin-roles.md)|
|<span data-ttu-id="19c8d-139">보안 관리자</span><span class="sxs-lookup"><span data-stu-id="19c8d-139">Security Administrator</span></span>|[<span data-ttu-id="19c8d-140">Azure Active Directory의 관리자 역할 권한</span><span class="sxs-lookup"><span data-stu-id="19c8d-140">Administrator role permissions in Azure Active Directory</span></span>](/azure/active-directory/users-groups-roles/directory-assign-admin-roles)|
|<span data-ttu-id="19c8d-141">Exchange Online 조직 관리</span><span class="sxs-lookup"><span data-stu-id="19c8d-141">Exchange Online Organization Management</span></span>|[<span data-ttu-id="19c8d-142">Exchange Online의 사용 권한</span><span class="sxs-lookup"><span data-stu-id="19c8d-142">Permissions in Exchange Online</span></span>](/exchange/permissions-exo/permissions-exo)|
|

<span data-ttu-id="19c8d-143">자세한 내용은 Microsoft 365 Defender [포털의 사용 권한을 참조합니다.](permissions-microsoft-365-security-center.md)</span><span class="sxs-lookup"><span data-stu-id="19c8d-143">To learn more, see [Permissions in the Microsoft 365 Defender portal](permissions-microsoft-365-security-center.md).</span></span>

### <a name="turn-on-audit-logging-for-reporting-and-investigation"></a><span data-ttu-id="19c8d-144">보고 및 조사에 대한 감사 로깅 켜기</span><span class="sxs-lookup"><span data-stu-id="19c8d-144">Turn on audit logging for reporting and investigation</span></span>

- <span data-ttu-id="19c8d-145">감사 로깅을 조기 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="19c8d-145">Start your audit logging early.</span></span> <span data-ttu-id="19c8d-146">다음 단계 중 일부에 대해 **감사를 ON으로** 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="19c8d-146">You'll need auditing to be **ON** for some of the following steps.</span></span> <span data-ttu-id="19c8d-147">감사 로깅은 을(를) 포함 하는 [구독에서 사용할 Exchange Online.](/office365/servicedescriptions/exchange-online-service-description/exchange-online-service-description)</span><span class="sxs-lookup"><span data-stu-id="19c8d-147">Audit logging is available in subscriptions that include [Exchange Online](/office365/servicedescriptions/exchange-online-service-description/exchange-online-service-description).</span></span> <span data-ttu-id="19c8d-148">위협 방지 [보고서,](view-email-security-reports.md)전자 메일 보안 보고서 [](threat-explorer.md)및 탐색기에서 데이터를 확인하려면 감사 로깅이 에 있어야 *합니다.*</span><span class="sxs-lookup"><span data-stu-id="19c8d-148">In order to view data in threat protection reports, [email security reports](view-email-security-reports.md), and [Explorer](threat-explorer.md), audit logging must be *On*.</span></span> <span data-ttu-id="19c8d-149">자세한 내용은 감사 로그 검색 켜기 또는 [끄기 를 참조합니다.](../../compliance/turn-audit-log-search-on-or-off.md)</span><span class="sxs-lookup"><span data-stu-id="19c8d-149">To learn more, see [Turn audit log search on or off](../../compliance/turn-audit-log-search-on-or-off.md).</span></span>

## <a name="part-1---anti-malware-protection-in-eop"></a><span data-ttu-id="19c8d-150">1부 - EOP의 맬웨어 방지 보호</span><span class="sxs-lookup"><span data-stu-id="19c8d-150">Part 1 - Anti-malware protection in EOP</span></span>

<span data-ttu-id="19c8d-151">맬웨어 방지에 대한 권장 설정에 대한 자세한 내용은 EOP 맬웨어 방지 정책 [설정 을 참조하세요.](recommended-settings-for-eop-and-office365.md#eop-anti-malware-policy-settings)</span><span class="sxs-lookup"><span data-stu-id="19c8d-151">For more information about the recommended settings for anti-malware, see [EOP anti-malware policy settings](recommended-settings-for-eop-and-office365.md#eop-anti-malware-policy-settings).</span></span>

1. <span data-ttu-id="19c8d-152">의  Microsoft 365 Defender 포털에서 맬웨어 방지 페이지를 열 수 <https://security.microsoft.com/antimalwarev2> 있습니다.</span><span class="sxs-lookup"><span data-stu-id="19c8d-152">Open the **Anti-malware** page in the Microsoft 365 Defender portal at <https://security.microsoft.com/antimalwarev2>.</span></span>

2. <span data-ttu-id="19c8d-153">**맬웨어 방지 페이지에서** 이름을 클릭하여 **Default(기본값)라는** 정책을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="19c8d-153">On the **Anti-malware** page, select the policy named **Default (Default)** by clicking on the name.</span></span>

3. <span data-ttu-id="19c8d-154">정책 세부 정보 플라이아웃이 열리면 보호 설정 편집을 **클릭하고** 다음 설정을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="19c8d-154">In the policy details flyout that opens, click **Edit protection settings**, and then configure the following settings:</span></span>
   - <span data-ttu-id="19c8d-155">**보호 설정** 섹션:</span><span class="sxs-lookup"><span data-stu-id="19c8d-155">**Protection settings** section:</span></span>
     - <span data-ttu-id="19c8d-156">**공통 첨부 파일 필터 사용:** 선택(켜기)을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="19c8d-156">**Enable the common attachments filter**: Select (turn on).</span></span> <span data-ttu-id="19c8d-157">파일 **형식 사용자 지정을 클릭하여** 파일 형식을 더 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="19c8d-157">Click **Customize file types** to add more file types.</span></span>
     - <span data-ttu-id="19c8d-158">**맬웨어에 대해 0시간 자동 제거** 사용: 이 설정이 선택되어 있는지 확인</span><span class="sxs-lookup"><span data-stu-id="19c8d-158">**Enable zero-hour auto purge for malware**: Verify this setting is selected.</span></span> <span data-ttu-id="19c8d-159">맬웨어에 대한 ZAP에 대한 자세한 내용은 맬웨어에 대한 [ZAP(제로 아워 자동 제거)를 참조하세요.](zero-hour-auto-purge.md#zero-hour-auto-purge-zap-for-malware)</span><span class="sxs-lookup"><span data-stu-id="19c8d-159">For more information about ZAP for malware, see [Zero-hour auto purge (ZAP) for malware](zero-hour-auto-purge.md#zero-hour-auto-purge-zap-for-malware).</span></span>
   - <span data-ttu-id="19c8d-160">**알림** 섹션: 알림 설정이 선택되어 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="19c8d-160">**Notification** section: Verify that none of the notification settings are selected.</span></span>

   <span data-ttu-id="19c8d-161">작업을 마쳤으면 **저장** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="19c8d-161">When you're finished, click **Save**.</span></span>

4. <span data-ttu-id="19c8d-162">정책 세부 정보 플라이아웃으로 돌아와 **닫기** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="19c8d-162">Back on the policy details flyout, click **Close**.</span></span>

<span data-ttu-id="19c8d-163">맬웨어 방지 정책을 구성하는 방법에 대한 자세한 내용은 EOP에서 맬웨어 방지 [정책 구성을 참조하세요.](configure-anti-malware-policies.md)</span><span class="sxs-lookup"><span data-stu-id="19c8d-163">For detailed instructions for configuring anti-malware policies, see [Configure anti-malware policies in EOP](configure-anti-malware-policies.md).</span></span>

## <a name="part-2---anti-phishing-protection-in-eop-and-defender-for-office-365"></a><span data-ttu-id="19c8d-164">2부 - EOP의 피싱 방지 보호 기능 및 EOP용 Defender Office 365</span><span class="sxs-lookup"><span data-stu-id="19c8d-164">Part 2 - Anti-phishing protection in EOP and Defender for Office 365</span></span>

<span data-ttu-id="19c8d-165">[피싱 방지 보호는](anti-phishing-protection.md) EOP를 포함 하는 [구독에서 사용할 수 있습니다.](/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description)</span><span class="sxs-lookup"><span data-stu-id="19c8d-165">[Anti-phishing protection](anti-phishing-protection.md) is available in subscriptions that include [EOP](/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description).</span></span> <span data-ttu-id="19c8d-166">고급 피싱 방지 보호는 에 대한 [Defender에서](/office365/servicedescriptions/office-365-advanced-threat-protection-service-description)사용할 수 Office 365.</span><span class="sxs-lookup"><span data-stu-id="19c8d-166">Advanced anti-phishing protection is available in [Defender for Office 365](/office365/servicedescriptions/office-365-advanced-threat-protection-service-description).</span></span>

<span data-ttu-id="19c8d-167">피싱 방지 정책에 대한 권장 설정에 대한 자세한 내용은 [EOP](recommended-settings-for-eop-and-office365.md#eop-anti-phishing-policy-settings) 피싱 방지 정책 설정 및 Microsoft Defender for [Office 365.](recommended-settings-for-eop-and-office365.md#anti-phishing-policy-settings-in-microsoft-defender-for-office-365)</span><span class="sxs-lookup"><span data-stu-id="19c8d-167">For more information about the recommended settings for anti-phishing policies, see [EOP anti-phishing policy settings](recommended-settings-for-eop-and-office365.md#eop-anti-phishing-policy-settings) and [Anti-phishing policy settings in Microsoft Defender for Office 365](recommended-settings-for-eop-and-office365.md#anti-phishing-policy-settings-in-microsoft-defender-for-office-365).</span></span>

<span data-ttu-id="19c8d-168">다음 절차에서는 기본 피싱 방지 정책을 구성하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="19c8d-168">The following procedure describes how to configure the default anti-phishing policy.</span></span> <span data-ttu-id="19c8d-169">설정 Defender에서만 사용할 수 있는 Office 365 명확하게 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="19c8d-169">Settings that are only available in Defender for Office 365 are clearly marked.</span></span>

1. <span data-ttu-id="19c8d-170">의  Microsoft 365 Defender 포털에서 피싱 방지 페이지를 열 수 <https://security.microsoft.com/antiphishing> 있습니다.</span><span class="sxs-lookup"><span data-stu-id="19c8d-170">Open the **Anti-phishing** page in the Microsoft 365 Defender portal at <https://security.microsoft.com/antiphishing>.</span></span>

2. <span data-ttu-id="19c8d-171">피싱 **방지 페이지에서** 이름을 클릭하여 **Office365 AntiPhish Default(기본값)라는** 정책을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="19c8d-171">On the **Anti-phishing** page, select the policy named **Office365 AntiPhish Default (Default)** by clicking on the name.</span></span>

3. <span data-ttu-id="19c8d-172">나타나는 정책 세부 정보 플라이아웃에서 다음 설정을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="19c8d-172">In the policy details flyout that appears, configure the following settings:</span></span>
   - <span data-ttu-id="19c8d-173">**피싱 임계값 & 보호** 섹션: 보호 설정 편집을 **클릭하고** 플라이아웃에서 열리도록 다음 설정을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="19c8d-173">**Phishing threshold & protection** section: Click **Edit protection settings** and configure the following settings in the flyout that opens:</span></span>
     - <span data-ttu-id="19c8d-174">**피싱 전자 메일 임계값:** <sup>\*</sup> **2 - 적극적(표준)** 또는 **3 - 보다 적극적(엄격)을** 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="19c8d-174">**Phishing email threshold**<sup>\*</sup>: Select **2 - Aggressive** (Standard) or **3 - More Aggressive** (Strict).</span></span>
     - <span data-ttu-id="19c8d-175">**가장 섹션:** <sup>\*</sup> 다음 값을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="19c8d-175">**Impersonation** section<sup>\*</sup>: Configure the following values:</span></span>
       - <span data-ttu-id="19c8d-176">사용자가 **보호할** 수 있도록 설정을 선택하고 나타나는 **(nn)** 보낸 사람 관리 링크를 클릭한 다음 조직의 보드 구성원, CEO, CFO 및 기타 고위 리더와 같은 가장으로부터 보호하기 위해 내부 및 외부 보낸 사람 추가를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="19c8d-176">Select **Enable users to protect**, click the **Manage (nn) sender(s)** link that appears, and then add internal and external senders to protect from impersonation, such as your organization's board members, your CEO, CFO, and other senior leaders.</span></span>
       - <span data-ttu-id="19c8d-177">을 **보호하려면** 도메인 사용 을 선택한 다음 나타나는 다음 설정을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="19c8d-177">Select **Enable domains to protect**, and then configure the following settings that appear:</span></span>
         - <span data-ttu-id="19c8d-178">허용 **도메인의** 내부 보낸 사람(내 도메인 보기 클릭)을 가장에서 보호하려면 소유한 도메인 포함을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="19c8d-178">Select **Include domains I own** to protect internal senders in your accepted domains (visible by clicking **View my domains**) from impersonation.</span></span>
         - <span data-ttu-id="19c8d-179">다른 도메인의 보낸 사람 보호하려면 사용자 지정 도메인 포함을 선택하고 나타나는 **관리(nn)** 사용자 지정 도메인 링크를 클릭한 다음 가장으로부터 보호할 다른 도메인을 추가합니다. </span><span class="sxs-lookup"><span data-stu-id="19c8d-179">To protect senders in other domains, select **Include custom domains**, click the **Manage (nn) custom domain(s)** link that appears, and then add other domains to protect from impersonation.</span></span>
     - <span data-ttu-id="19c8d-180">**신뢰할** 수 있는 보낸 사람 및 도메인 추가 <sup>\*</sup> 섹션: **관리(nn)** 신뢰할 수 있는 보낸 사람 및 도메인을 클릭하여 필요한 경우 가장 보호로 보낸 사람 및 보낸 사람 도메인 예외를 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="19c8d-180">**Add trusted senders and domains** section <sup>\*</sup>: Click **Manage (nn) trusted sender(s) and domains(s)** to configure sender and sender domain exceptions to impersonation protection if needed.</span></span>
     - <span data-ttu-id="19c8d-181">사서함 인텔리전스 설정: 사서함 인텔리전스 사용 및 가장 방지를 위한 인텔리전스 사용이 <sup>\*</sup> 선택되어 있는지  확인합니다. </span><span class="sxs-lookup"><span data-stu-id="19c8d-181">Mailbox intelligence settings <sup>\*</sup>: Verify that **Enable mailbox intelligence** and **Enable intelligence for impersonation protection** are selected.</span></span>
     - <span data-ttu-id="19c8d-182">**스푸핑 섹션:** **스푸핑 인텔리전스 사용이 선택되어 있는지** 확인</span><span class="sxs-lookup"><span data-stu-id="19c8d-182">**Spoof** section: Verify **Enable spoof intelligence** is selected.</span></span>

     <span data-ttu-id="19c8d-183">작업을 마쳤으면 **저장** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="19c8d-183">When you're finished, click **Save**.</span></span>

   - <span data-ttu-id="19c8d-184">**작업** 섹션: 작업 **편집을** 클릭하고 플라이아웃에서 열리도록 다음 설정을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="19c8d-184">**Actions** section: Click **Edit actions** and configure the following settings in the flyout that opens:</span></span>
     - <span data-ttu-id="19c8d-185">**메시지 작업** 섹션: 다음 설정을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="19c8d-185">**Message actions** section: Configure the following settings:</span></span>
       - <span data-ttu-id="19c8d-186">**가장된** 사용자로 메시지가 검색된 경우 : 메시지 을 선택하여 을 <sup>\*</sup> **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="19c8d-186">**If message is detected as an impersonated user**<sup>\*</sup>: Select **Quarantine the message**.</span></span>
       - <span data-ttu-id="19c8d-187">**가장된** 도메인으로 메시지가 검색된 경우 : 메시지 을 선택하여 을 <sup>\*</sup> **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="19c8d-187">**If message is detected as an impersonated domain**<sup>\*</sup>: Select **Quarantine the message**.</span></span>
       - <span data-ttu-id="19c8d-188">**사서함 인텔리전스에서** 가장된 사용자를 검색하는 경우 : 받는 사람의 정크 메일 폴더로 메시지 이동(표준) 또는 메시지 검역(엄격)을 <sup>\*</sup> 선택합니다.  </span><span class="sxs-lookup"><span data-stu-id="19c8d-188">**If mailbox intelligence detects an impersonated user**<sup>\*</sup>: Select **Move message to the recipients' Junk Email folders** (Standard) or **Quarantine the message** (Strict).</span></span>
       - <span data-ttu-id="19c8d-189">**메시지가 스푸핑으로** 검색된 경우  : 받는 사람의 정크 메일 폴더로 메시지  이동(표준) 또는 메시지 검량(엄격)을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="19c8d-189">**If message is detected as spoof**: Select **Move message to the recipients' Junk Email folders** (Standard) or **Quarantine the message** (Strict).</span></span>
     - <span data-ttu-id="19c8d-190">**안전 팁 & 표시기** 섹션: 다음 설정을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="19c8d-190">**Safety tips & indicators** section: Configure the following settings:</span></span>
       - <span data-ttu-id="19c8d-191">**첫 번째 연락처 보안 팁**: 선택(켜기)을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="19c8d-191">**Show first contact safety tip**: Select (turn on).</span></span>
       - <span data-ttu-id="19c8d-192">**사용자 가장 표시** 보안 팁 <sup>\*</sup> : 선택(켜기)을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="19c8d-192">**Show user impersonation safety tip**<sup>\*</sup>: Select (turn on).</span></span>
       - <span data-ttu-id="19c8d-193">**도메인 가장 표시** <sup>\*</sup> 보안 팁 : 선택(켜기)을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="19c8d-193">**Show domain impersonation safety tip**<sup>\*</sup>: Select (turn on).</span></span>
       - <span data-ttu-id="19c8d-194">**사용자 가장 비정상 문자** 보안 팁 <sup>\*</sup> : 선택(켜기)을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="19c8d-194">**Show user impersonation unusual characters safety tip**<sup>\*</sup>: Select (turn on).</span></span>
       - <span data-ttu-id="19c8d-195">**스푸핑에** 대해 확인되지 않은 보낸 사람에 대한 표시(?) : 선택(켜기)을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="19c8d-195">**Show (?) for unauthenticated senders for spoof**: Select (turn on).</span></span>
       - <span data-ttu-id="19c8d-196">**"via" 태그 표시**: 선택(켜기)입니다.</span><span class="sxs-lookup"><span data-stu-id="19c8d-196">**Show "via" tag**: Select (turn on).</span></span>

     <span data-ttu-id="19c8d-197">작업을 마쳤으면 **저장** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="19c8d-197">When you're finished, click **Save**.</span></span>

   <span data-ttu-id="19c8d-198"><sup>\*</sup>이 설정은 사용자용 Defender에서만 사용할 Office 365.</span><span class="sxs-lookup"><span data-stu-id="19c8d-198"><sup>\*</sup> This setting is available only in Defender for Office 365.</span></span>

4. <span data-ttu-id="19c8d-199">**저장을** 클릭한 다음 **닫기 클릭**</span><span class="sxs-lookup"><span data-stu-id="19c8d-199">Click **Save** and then click **Close**</span></span>

<span data-ttu-id="19c8d-200">피싱 방지 정책을 구성하는 방법에 대한 자세한 내용은 [EOP에서](configure-anti-phishing-policies-eop.md) 피싱 방지 정책 구성 및 Microsoft [Defender에서](configure-mdo-anti-phishing-policies.md)피싱 방지 정책 구성을 Office 365.</span><span class="sxs-lookup"><span data-stu-id="19c8d-200">For detailed instructions for configuring anti-phishing policies, see [Configure anti-phishing policies in EOP](configure-anti-phishing-policies-eop.md) and [Configure anti-phishing policies in Microsoft Defender for Office 365](configure-mdo-anti-phishing-policies.md).</span></span>

## <a name="part-3---anti-spam-protection-in-eop"></a><span data-ttu-id="19c8d-201">3부 - EOP의 스팸 방지 보호 기능</span><span class="sxs-lookup"><span data-stu-id="19c8d-201">Part 3 - Anti-spam protection in EOP</span></span>

<span data-ttu-id="19c8d-202">스팸 방지에 대한 권장 설정에 대한 자세한 내용은 EOP 스팸 방지 정책 [설정 을 참조하세요.](recommended-settings-for-eop-and-office365.md#eop-anti-spam-policy-settings)</span><span class="sxs-lookup"><span data-stu-id="19c8d-202">For more information about the recommended settings for anti-spam, see [EOP anti-spam policy settings](recommended-settings-for-eop-and-office365.md#eop-anti-spam-policy-settings).</span></span>

1. <span data-ttu-id="19c8d-203">에서 스팸 **방지 정책** 페이지를 Microsoft 365 Defender 를 <https://security.microsoft.com/antispam> 니다.</span><span class="sxs-lookup"><span data-stu-id="19c8d-203">Open the **Anti-spam policies** page in the Microsoft 365 Defender portal at <https://security.microsoft.com/antispam>.</span></span>

2. <span data-ttu-id="19c8d-204">스팸 **방지 정책** 페이지에서 이름을 클릭하여 목록에서 스팸 방지 인바운드 정책(기본값)이라는 정책을 선택합니다. </span><span class="sxs-lookup"><span data-stu-id="19c8d-204">On the **Anti-spam policies** page, select the policy named **Anti-spam inbound policy (Default)** from the list by clicking on the name.</span></span>

3. <span data-ttu-id="19c8d-205">나타나는 정책 세부 정보 플라이아웃에서 다음 설정을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="19c8d-205">In the policy details flyout that appears, configure the following settings:</span></span>
   - <span data-ttu-id="19c8d-206">**스팸 속성 & 대량** 전자 메일 임계값: 스팸 임계값 및 속성 **편집을 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="19c8d-206">**Bulk email threshold & spam properties** section: Click **Edit spam threshold and properties**.</span></span> <span data-ttu-id="19c8d-207">플라이아웃이 나타나면 다음 설정을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="19c8d-207">In the flyout that appears, configure the following settings:</span></span>
     - <span data-ttu-id="19c8d-208">**대량 전자 메일 임계값:** 이 값을 5(엄격) 또는 6(표준)으로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="19c8d-208">**Bulk email threshold**: Set this value to 5 (Strict) or 6 (Standard).</span></span>
     - <span data-ttu-id="19c8d-209">다른 설정은 기본값(해제 또는 없음)으로 **떠 .**</span><span class="sxs-lookup"><span data-stu-id="19c8d-209">Leave other settings at their default values (**Off** or **None**).</span></span>

     <span data-ttu-id="19c8d-210">작업을 마쳤으면 **저장** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="19c8d-210">When you're finished, click **Save**.</span></span>

   - <span data-ttu-id="19c8d-211">**작업** 섹션: 작업 **편집을 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="19c8d-211">**Actions** section: Click **Edit actions**.</span></span> <span data-ttu-id="19c8d-212">플라이아웃이 나타나면 다음 설정을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="19c8d-212">In the flyout that appears, configure the following settings:</span></span>
     - <span data-ttu-id="19c8d-213">**메시지 작업** 섹션:</span><span class="sxs-lookup"><span data-stu-id="19c8d-213">**Message actions** section:</span></span>
       - <span data-ttu-id="19c8d-214">**스팸:** **정크** 메일 폴더로 메시지 이동이 선택되어 있는지 확인(표준)을 선택하거나 **Quarantine message** (Strict)를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="19c8d-214">**Spam**: Verify **Move message to Junk Email folder** is selected (Standard) or select **Quarantine message** (Strict).</span></span>
       - <span data-ttu-id="19c8d-215">**높은 지수 스팸**: 메시지 **검란을 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="19c8d-215">**High confidence spam**: Select **Quarantine message**.</span></span>
       - <span data-ttu-id="19c8d-216">**피싱**: **메시지 검란을 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="19c8d-216">**Phishing**:  Select **Quarantine message**.</span></span>
       - <span data-ttu-id="19c8d-217">**높은 신뢰도 피싱:** **메시지의 검지가 선택되어 있는지** 확인</span><span class="sxs-lookup"><span data-stu-id="19c8d-217">**High confidence phishing**: Verify **Quarantine messages** is selected.</span></span>
       - <span data-ttu-id="19c8d-218">**대량:** **정크** 메일 폴더로 메시지 이동이 선택되어 있는지 확인(표준) 또는 메시지 검지(엄격)를 선택합니다. </span><span class="sxs-lookup"><span data-stu-id="19c8d-218">**Bulk**: Verify **Move message to Junk Email folder** is selected (Standard) or select **Quarantine message** (Strict).</span></span>
     - <span data-ttu-id="19c8d-219">**이 며칠 동안** 스팸을 검지에서 보존 : **30일** 값을 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="19c8d-219">**Retain spam in quarantine for this many days**: Verify the value **30** days.</span></span>
     - <span data-ttu-id="19c8d-220">**스팸 보안 팁 사용:** 이 설정이 선택되어 있는지 확인(켜져 있습니다.)</span><span class="sxs-lookup"><span data-stu-id="19c8d-220">**Enable spam safety tips**: Verify this setting is selected (turned on).</span></span>
     - <span data-ttu-id="19c8d-221">**ZAP(제로 아워 자동 제거)** 사용: 이 설정이 선택되어 있는지 확인(켜져 있습니다.)</span><span class="sxs-lookup"><span data-stu-id="19c8d-221">**Enable zero-hour auto purge (ZAP)**: Verify this setting is selected (turned on).</span></span>
       - <span data-ttu-id="19c8d-222">**피싱 메시지 사용:** 이 설정이 선택되어 있는지 확인(켜져 있습니다.)</span><span class="sxs-lookup"><span data-stu-id="19c8d-222">**Enable for phishing messages**: Verify this setting is selected (turned on).</span></span> <span data-ttu-id="19c8d-223">자세한 내용은 피싱에 대한 [ZAP(제로 아워 자동 제거)를 참조하세요.](zero-hour-auto-purge.md#zero-hour-auto-purge-zap-for-phishing)</span><span class="sxs-lookup"><span data-stu-id="19c8d-223">For more information, see [Zero-hour auto purge (ZAP) for phishing](zero-hour-auto-purge.md#zero-hour-auto-purge-zap-for-phishing).</span></span>
       - <span data-ttu-id="19c8d-224">**스팸 메시지 사용:** 이 설정이 선택되어 있는지 확인(켜져 있습니다.)</span><span class="sxs-lookup"><span data-stu-id="19c8d-224">**Enable for spam messages**:  Verify this setting is selected (turned on).</span></span> <span data-ttu-id="19c8d-225">자세한 내용은 스팸에 대한 [ZAP(제로 아워 자동 제거)를 참조하세요.](zero-hour-auto-purge.md#zero-hour-auto-purge-zap-for-spam)</span><span class="sxs-lookup"><span data-stu-id="19c8d-225">For more information, see [Zero-hour auto purge (ZAP) for spam](zero-hour-auto-purge.md#zero-hour-auto-purge-zap-for-spam).</span></span>
     - <span data-ttu-id="19c8d-226">**알림 섹션:**</span><span class="sxs-lookup"><span data-stu-id="19c8d-226">**Notifications** section:</span></span>
       - <span data-ttu-id="19c8d-227">최종 **사용자 스팸 알림 사용 을 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="19c8d-227">Select **Enable end-user spam notifications**.</span></span>
         - <span data-ttu-id="19c8d-228">**매일(일)** 최종 사용자 스팸 알림 보내기: **값 3일을** 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="19c8d-228">**Send end-user spam notifications every (days)**: Verify the value **3** days.</span></span>
         - <span data-ttu-id="19c8d-229">**언어:** 기본값 값을 **확인하거나** 언어를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="19c8d-229">**Language**: Verify the value **Default** or select a language.</span></span>

     <span data-ttu-id="19c8d-230">작업을 마쳤으면 **저장** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="19c8d-230">When you're finished, click **Save**.</span></span>

   - <span data-ttu-id="19c8d-231">**허용 및** 차단된 보낸 사람 및 도메인 섹션: [EOP에서](create-block-sender-lists-in-office-365.md) 차단된 보낸 사람 목록 만들기 또는 [EOP에서](create-safe-sender-lists-in-office-365.md)수신 허용 - 보낸 사람 목록 만들기에 설명된 바와 같이 허용된 보낸 사람 및 허용된 도메인을 검토하거나 편집합니다.</span><span class="sxs-lookup"><span data-stu-id="19c8d-231">**Allowed and blocked senders and domains** section: Review or edit your allowed senders and allowed domains as described in [Create blocked sender lists in EOP](create-block-sender-lists-in-office-365.md) or [Create safe sender lists in EOP](create-safe-sender-lists-in-office-365.md).</span></span>

     <span data-ttu-id="19c8d-232">작업을 마쳤으면 **저장** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="19c8d-232">When you're finished, click **Save**.</span></span>

4. <span data-ttu-id="19c8d-233">작업을 마쳤으면 **닫기** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="19c8d-233">When you're finished, click **Close**.</span></span>

<span data-ttu-id="19c8d-234">스팸 방지 정책을 구성하는 방법에 대한 자세한 내용은 [EOP에서 스팸 방지 정책 구성을 참조하세요.](configure-your-spam-filter-policies.md)</span><span class="sxs-lookup"><span data-stu-id="19c8d-234">For detailed instructions for configuring anti-spam policies, see [Configure anti-spam policies in EOP](configure-your-spam-filter-policies.md).</span></span>

## <a name="part-4---protection-from-malicious-urls-and-files-safe-links-and-safe-attachments-in-defender-for-office-365"></a><span data-ttu-id="19c8d-235">4부 - 악의적인 URL 및 파일로부터 보호(금고 Defender의 링크 및 금고 첨부 Office 365 파일)</span><span class="sxs-lookup"><span data-stu-id="19c8d-235">Part 4 - Protection from malicious URLs and files (Safe Links and Safe Attachments in Defender for Office 365)</span></span>

<span data-ttu-id="19c8d-236">악성 URL 및 파일로부터 클릭 시간 보호는 Microsoft [Defender for](/office365/servicedescriptions/office-365-advanced-threat-protection-service-description)Office 365.</span><span class="sxs-lookup"><span data-stu-id="19c8d-236">Time-of-click protection from malicious URLs and files is available in subscriptions that include [Microsoft Defender for Office 365](/office365/servicedescriptions/office-365-advanced-threat-protection-service-description).</span></span> <span data-ttu-id="19c8d-237">첨부 파일 및 링크 금고 [정책을](safe-attachments.md) [통해 금고](safe-links.md) 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="19c8d-237">It's set up through [Safe Attachments](safe-attachments.md) and [Safe Links](safe-links.md) policies.</span></span>

### <a name="safe-attachments-policies-in-microsoft-defender-for-office-365"></a><span data-ttu-id="19c8d-238">금고 Microsoft Defender for Office 365</span><span class="sxs-lookup"><span data-stu-id="19c8d-238">Safe Attachments policies in Microsoft Defender for Office 365</span></span>

<span data-ttu-id="19c8d-239">첨부 파일에 대한 권장 설정에 금고 자세한 내용은 을 참조하세요. [금고 설정 을 선택합니다.](recommended-settings-for-eop-and-office365.md#safe-attachments-settings)</span><span class="sxs-lookup"><span data-stu-id="19c8d-239">For more information about the recommended settings for Safe Attachments, see .[Safe Attachments settings](recommended-settings-for-eop-and-office365.md#safe-attachments-settings).</span></span>

1. <span data-ttu-id="19c8d-240">의 **금고 포털에서** Microsoft 365 Defender 첨부 파일 페이지를 열 수 <https://security.microsoft.com/safeattachmentv2> 있습니다.</span><span class="sxs-lookup"><span data-stu-id="19c8d-240">Open the **Safe Attachments** page in the Microsoft 365 Defender portal at <https://security.microsoft.com/safeattachmentv2>.</span></span>

2. <span data-ttu-id="19c8d-241">첨부 **금고** 페이지에서 전역 설정을 클릭한 다음 나타나는 플라이아웃에서 다음 설정을 구성합니다. </span><span class="sxs-lookup"><span data-stu-id="19c8d-241">On the **Safe Attachments** page, click **Global settings**, and then configure the following settings on the flyout that appears:</span></span>
   - <span data-ttu-id="19c8d-242">**에** 대한 Office 365, SharePoint OneDrive 및 Microsoft Teams : 이 설정 켜기( ![ 토글 켜기). ](../../media/scc-toggle-on.png)</span><span class="sxs-lookup"><span data-stu-id="19c8d-242">**Turn on Defender for Office 365 for SharePoint, OneDrive, and Microsoft Teams**: Turn on this setting (![Toggle on](../../media/scc-toggle-on.png)).</span></span>

     > [!IMPORTANT]
     > <span data-ttu-id="19c8d-243">**금고,** OneDrive 및 SharePoint, OneDrive 및 Microsoft Teams 첨부 파일을 설정하기 전에 조직에서 감사 로깅이 설정되어 있는지 확인해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="19c8d-243">**Before you turn on Safe Attachments for SharePoint, OneDrive, and Microsoft Teams, verify that audit logging is turned in your organization**.</span></span> <span data-ttu-id="19c8d-244">이 작업은 일반적으로 감사 로그 역할이 할당된 사용자가 Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="19c8d-244">This action is typically done by someone who has the Audit Logs role assigned in Exchange Online.</span></span> <span data-ttu-id="19c8d-245">자세한 내용은 감사 로그 검색 켜기 또는 [끄기!를 참조하세요.](../../compliance/turn-audit-log-search-on-or-off.md)</span><span class="sxs-lookup"><span data-stu-id="19c8d-245">For more information, see [Turn audit log search on or off](../../compliance/turn-audit-log-search-on-or-off.md)!</span></span>

   - <span data-ttu-id="19c8d-246">**금고 클라이언트에** 대한 Office 켜기 : 이 설정을 으로 설정( ![ 토글합니다. ](../../media/scc-toggle-on.png)</span><span class="sxs-lookup"><span data-stu-id="19c8d-246">**Turn on Safe Documents for Office clients**: Turn on this setting (![Toggle on](../../media/scc-toggle-on.png)).</span></span> <span data-ttu-id="19c8d-247">이 기능은 Microsoft 365 E5 또는 Microsoft 365 E5 Security 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="19c8d-247">Note that this feature is available and meaningful only with Microsoft 365 E5 or Microsoft 365 E5 Security licenses.</span></span>
   - <span data-ttu-id="19c8d-248">**파일을 악성으로** 식별한 문서가 금고 경우에도 사용자가 보호된 보기를 클릭할 수 있도록 허용: 이 설정이 꺼져 있는지 확인( ![ 토글 ](../../media/scc-toggle-off.png) 해제).</span><span class="sxs-lookup"><span data-stu-id="19c8d-248">**Allow people to click through Protected View even if Safe Documents identified the file as malicious**: Verify this setting is turned off (![Toggle off](../../media/scc-toggle-off.png)).</span></span>

   <span data-ttu-id="19c8d-249">완료되면 **저장을 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="19c8d-249">When you're finished, click **Save**</span></span>

3. <span data-ttu-id="19c8d-250">첨부 파일 **금고 페이지로 돌아가서** 아이콘 ![ 만들기를 ](../../media/m365-cc-sc-create-icon.png) 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="19c8d-250">Back on the **Safe Attachments** page, click ![Create icon](../../media/m365-cc-sc-create-icon.png).</span></span>

4. <span data-ttu-id="19c8d-251">열 **수 있는** 금고 첨부 파일 만들기 정책 마법사에서 다음 설정을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="19c8d-251">In the **Create Safe Attachments policy** wizard that opens, configure the following settings:</span></span>
   - <span data-ttu-id="19c8d-252">**정책 페이지의 이름을 지정합니다.**</span><span class="sxs-lookup"><span data-stu-id="19c8d-252">**Name your policy** page:</span></span>
     - <span data-ttu-id="19c8d-253">**이름:** 고유한 설명을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="19c8d-253">**Name**: Enter something unique and descriptive.</span></span>
     - <span data-ttu-id="19c8d-254">**설명:** 선택적 설명을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="19c8d-254">**Description**: Enter an optional description.</span></span>
   - <span data-ttu-id="19c8d-255">**사용자 및 도메인** 페이지: 첫 번째 정책이기 때문에 적용 범위를 [](/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains) 최대화하려는 경우 도메인 상자에 허용 도메인을 입력하는 **것이** 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="19c8d-255">**Users and domains** page: Because this is your first policy and you likely want to maximize coverage, consider entering your [accepted domains](/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains) in the **Domains** box.</span></span> <span data-ttu-id="19c8d-256">그렇지 않으면 사용자  및  그룹 상자를 사용하여 보다 세부적인 제어를 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="19c8d-256">Otherwise, you can use the **Users** and **Groups** boxes for more granular control.</span></span> <span data-ttu-id="19c8d-257">이러한 사용자, 그룹 및 도메인 제외를 선택하고 값을 입력하여 **예외를 지정할** 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="19c8d-257">You can specify exceptions by selecting **Exclude these users, groups, and domains** and entering values.</span></span>
   - <span data-ttu-id="19c8d-258">**설정** 페이지:</span><span class="sxs-lookup"><span data-stu-id="19c8d-258">**Settings** page:</span></span>
     - <span data-ttu-id="19c8d-259">**금고 알 수 없는 맬웨어 응답**: 차단을 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="19c8d-259">**Safe Attachments unknown malware response**: Select **Block**.</span></span>
     - <span data-ttu-id="19c8d-260">**검색된 첨부 파일이 있는** 첨부 파일 **리디렉션:** 리디렉션 사용: 이 설정을 켜고(선택) 검색된 메시지를 받을 전자 메일 주소를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="19c8d-260">**Redirect attachment with detected attachments** : **Enable redirect**: Turn this setting on (select) and enter an email address to receive detected messages.</span></span>
     - <span data-ttu-id="19c8d-261">**검색을 금고** 수 없는 경우 첨부 파일 검색 응답을 적용합니다(시간 제한 또는 오류). 이 설정이 선택되어 있는지 확인</span><span class="sxs-lookup"><span data-stu-id="19c8d-261">**Apply the Safe Attachments detection response if scanning can't complete (timeout or errors)**: Verify this setting is selected.</span></span>

5. <span data-ttu-id="19c8d-262">완료되면 제출을 **클릭하고** 완료를 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="19c8d-262">When you're finished, click **Submit**, and then click **Done**.</span></span>

6. <span data-ttu-id="19c8d-263">(권장) 전역 관리자 또는 SharePoint Online 관리자로서 _DisallowInfectedFileDownload_ 매개 변수를 SharePoint **[Set-SPOTenant](/powershell/module/sharepoint-online/Set-SPOTenant)** cmdlet을 `$true` 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="19c8d-263">(Recommended) As a global administrator or a SharePoint Online administrator, run the **[Set-SPOTenant](/powershell/module/sharepoint-online/Set-SPOTenant)** cmdlet with the _DisallowInfectedFileDownload_ parameter set to `$true` in SharePoint Online PowerShell.</span></span>
   - <span data-ttu-id="19c8d-264">`$true` 검색된 파일에 대한 모든 작업(삭제 제외)을 차단합니다.</span><span class="sxs-lookup"><span data-stu-id="19c8d-264">`$true` blocks all actions (except Delete) for detected files.</span></span> <span data-ttu-id="19c8d-265">검색된 파일을 열거나, 이동하거나, 복사하거나, 공유할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="19c8d-265">People can't open, move, copy, or share detected files.</span></span>
   - <span data-ttu-id="19c8d-266">`$false` 삭제 및 다운로드를 제외한 모든 작업을 차단합니다.</span><span class="sxs-lookup"><span data-stu-id="19c8d-266">`$false` blocks all actions except Delete and Download.</span></span> <span data-ttu-id="19c8d-267">사람들은 위험을 수락하고 검색된 파일을 다운로드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="19c8d-267">People can choose to accept the risk and download a detected file.</span></span>

7. <span data-ttu-id="19c8d-268">모든 데이터 센터에 변경 내용을 분산하는 데 최대 30분 Microsoft 365 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="19c8d-268">Allow up to 30 minutes for your changes to spread to all Microsoft 365 datacenters.</span></span>

<span data-ttu-id="19c8d-269">첨부 파일에 대한 금고 정책 및 전역 설정을 구성하는 금고 자세한 내용은 다음 항목을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="19c8d-269">For detailed instructions for configuring Safe Attachments policies and global settings for Safe Attachments, see the following topics:</span></span>

- [<span data-ttu-id="19c8d-270">Microsoft Defender에서 금고 첨부 파일 정책 설정 Office 365</span><span class="sxs-lookup"><span data-stu-id="19c8d-270">Set up Safe Attachments policies in Microsoft Defender for Office 365</span></span>](set-up-safe-attachments-policies.md)
- [<span data-ttu-id="19c8d-271">SharePoint, OneDrive 및 Microsoft Teams에 대해 안전한 첨부 파일 설정</span><span class="sxs-lookup"><span data-stu-id="19c8d-271">Turn on Safe Attachments for SharePoint, OneDrive, and Microsoft Teams</span></span>](turn-on-mdo-for-spo-odb-and-teams.md)
- [<span data-ttu-id="19c8d-272">Microsoft 365 E5에서 안전한 문서</span><span class="sxs-lookup"><span data-stu-id="19c8d-272">Safe Documents in Microsoft 365 E5</span></span>](safe-docs.md)

### <a name="safe-links-policies-in-microsoft-defender-for-office-365"></a><span data-ttu-id="19c8d-273">금고 Microsoft Defender for Office 365</span><span class="sxs-lookup"><span data-stu-id="19c8d-273">Safe Links policies in Microsoft Defender for Office 365</span></span>

<span data-ttu-id="19c8d-274">링크의 권장 설정에 대한 자세한 금고 링크 금고 [참조하세요.](recommended-settings-for-eop-and-office365.md#safe-links-settings)</span><span class="sxs-lookup"><span data-stu-id="19c8d-274">For more information about the recommended settings for Safe Links, see [Safe Links settings](recommended-settings-for-eop-and-office365.md#safe-links-settings).</span></span>

1. <span data-ttu-id="19c8d-275">의 **금고** 포털에서 Microsoft 365 Defender 링크 페이지를 열 수 <https://security.microsoft.com/safelinksv2> 있습니다.</span><span class="sxs-lookup"><span data-stu-id="19c8d-275">Open the **Safe Links** page in the Microsoft 365 Defender portal at <https://security.microsoft.com/safelinksv2>.</span></span>

2. <span data-ttu-id="19c8d-276">링크 **금고** 페이지에서 전역 설정을 클릭한 다음 나타나는 플라이아웃에서 다음 설정을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="19c8d-276">On the **Safe Links** page, click **Global settings**, and then configure the following settings on the flyout that appears:</span></span>
   - <span data-ttu-id="19c8d-277">**설정 앱 섹션의** 콘텐츠에 Office 365 적용되는 앱:</span><span class="sxs-lookup"><span data-stu-id="19c8d-277">**Settings that apply to content in supported Office 365 apps** section:</span></span>
     - <span data-ttu-id="19c8d-278">금고 앱에서 Office 365 **링크 사용:** 이 설정이 켜져 있는지 확인( ![ 토글합니다. ](../../media/scc-toggle-on.png)</span><span class="sxs-lookup"><span data-stu-id="19c8d-278">**Use Safe Links in Office 365 apps**: Verify this setting is turned on (![Toggle on](../../media/scc-toggle-on.png)).</span></span>
     - <span data-ttu-id="19c8d-279">사용자가 Office 365 앱에서 보호된 링크를 클릭하는 경우 추적하지 **않습니다.** 이 설정은 끄기(토글 ![ 끄기)입니다. ](../../media/scc-toggle-off.png)</span><span class="sxs-lookup"><span data-stu-id="19c8d-279">**Do not track when users click protected links in Office 365 apps**: Turn this setting off (![Toggle off](../../media/scc-toggle-off.png)).</span></span>
     - <span data-ttu-id="19c8d-280">사용자가 Office 365 앱의 원래 URL을 클릭할 수 없습니다. 이 설정이 켜져 있는지 **확인합니다(** ![ 토글 켜기). ](../../media/scc-toggle-on.png)</span><span class="sxs-lookup"><span data-stu-id="19c8d-280">**Do not let users click through to the original URL in Office 365 apps**: Verify this setting is turned on (![Toggle on](../../media/scc-toggle-on.png)).</span></span>

   <span data-ttu-id="19c8d-281">완료되면 **저장을 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="19c8d-281">When you're finished, click **Save**</span></span>

3. <span data-ttu-id="19c8d-282">다시 금고 **페이지에서** 아이콘 ![ 만들기를 ](../../media/m365-cc-sc-create-icon.png) 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="19c8d-282">Back on the **Safe Links** page, click ![Create icon](../../media/m365-cc-sc-create-icon.png).</span></span>

4. <span data-ttu-id="19c8d-283">열 **수 있는** 금고 정책 만들기 마법사에서 다음 설정을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="19c8d-283">In the **Create Safe Links policy** wizard that opens, configure the following settings:</span></span>
   - <span data-ttu-id="19c8d-284">**정책 페이지의 이름을 지정합니다.**</span><span class="sxs-lookup"><span data-stu-id="19c8d-284">**Name your policy** page:</span></span>
     - <span data-ttu-id="19c8d-285">**이름:** 고유한 설명을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="19c8d-285">**Name**: Enter something unique and descriptive.</span></span>
     - <span data-ttu-id="19c8d-286">**설명:** 선택적 설명을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="19c8d-286">**Description**: Enter an optional description.</span></span>
   - <span data-ttu-id="19c8d-287">**사용자 및 도메인** 페이지: 첫 번째 정책이기 때문에 적용 범위를 [](/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains) 최대화하려는 경우 도메인 상자에 허용 도메인을 입력하는 **것이** 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="19c8d-287">**Users and domains** page: Because this is your first policy and you likely want to maximize coverage, consider entering your [accepted domains](/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains) in the **Domains** box.</span></span> <span data-ttu-id="19c8d-288">그렇지 않으면 사용자  및  그룹 상자를 사용하여 보다 세부적인 제어를 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="19c8d-288">Otherwise, you can use the **Users** and **Groups** boxes for more granular control.</span></span> <span data-ttu-id="19c8d-289">이러한 사용자, 그룹 및 도메인 제외를 선택하고 값을 입력하여 **예외를 지정할** 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="19c8d-289">You can specify exceptions by selecting **Exclude these users, groups, and domains** and entering values.</span></span>
   - <span data-ttu-id="19c8d-290">**보호 설정** 페이지:</span><span class="sxs-lookup"><span data-stu-id="19c8d-290">**Protection settings** page:</span></span>
     - <span data-ttu-id="19c8d-291">**메시지에서 알 수** 없는 악의적인 URL에 대한 작업 선택: 이 설정을 **켜기 를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="19c8d-291">**Select the action for unknown potentially malicious URLs in messages**: Turn this setting **On**.</span></span>
     - <span data-ttu-id="19c8d-292">**에서 알 수 없는 URL** 또는 잠재적으로 악의적인 URL에 대한 작업을 Microsoft Teams : 이 설정을 **켜기 를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="19c8d-292">**Select the action for unknown or potentially malicious URLs within Microsoft Teams**: Turn this setting **On**.</span></span> <span data-ttu-id="19c8d-293">2020년 3월 현재 이 설정은 Preview에 있으며 TAP(Microsoft Teams Technology Adoption Program)의 구성원에게만 제공되거나 작동합니다.</span><span class="sxs-lookup"><span data-stu-id="19c8d-293">As of March 2020, this setting is in Preview and is available or functional only for members of the Microsoft Teams Technology Adoption Program (TAP).</span></span>
     - <span data-ttu-id="19c8d-294">**파일을 지정하는** 의심스러운 링크 및 링크에 대한 실시간 URL 검색 적용: 이 설정을 선택합니다(켜기).</span><span class="sxs-lookup"><span data-stu-id="19c8d-294">**Apply real-time URL scanning for suspicious links and links that point to files**: Select this setting (turn on).</span></span>
       - <span data-ttu-id="19c8d-295">**메시지를 배달하기** 전에 URL 검색이 완료될 때까지 기다렸다가 : 이 설정을 선택합니다(켜기).</span><span class="sxs-lookup"><span data-stu-id="19c8d-295">**Wait for URL scanning to complete before delivering the message**: Select this setting (turn on).</span></span>
     - <span data-ttu-id="19c8d-296">**조직 금고 보낸** 전자 메일 메시지에 대한 링크 적용: 이 설정을 선택합니다(켜기).</span><span class="sxs-lookup"><span data-stu-id="19c8d-296">**Apply Safe Links to email messages sent within the organization**: Select this setting (turn on).</span></span>
     - <span data-ttu-id="19c8d-297">**사용자 클릭 추적 안 하세요.** 이 설정이 선택되어 있지 않은지 확인(꺼져 있습니다.)</span><span class="sxs-lookup"><span data-stu-id="19c8d-297">**Do not track user clicks**: Verify this setting is not selected (turned off).</span></span>
     - <span data-ttu-id="19c8d-298">**사용자가 원래 URL을 클릭할** 수 없습니다. 이 설정이 켜져 있는지 확인합니다(선택).</span><span class="sxs-lookup"><span data-stu-id="19c8d-298">**Do not let users click through to the original URL**: Verify this setting is turned on (selected).</span></span>
     - <span data-ttu-id="19c8d-299">알림 **및** 경고 페이지에 조직 브랜드 표시: 조직에서 회사 로고를 업로드할 수 있도록 조직에 대한 Microsoft 365 테마 사용자 지정의 지침을 따라야만 이 설정을 선택(켜기)할 수 있습니다. [](../../admin/setup/customize-your-organization-theme.md)</span><span class="sxs-lookup"><span data-stu-id="19c8d-299">**Display the organization branding on notification and warning pages**: Selecting this setting (turning it on) is meaningful only after you've followed the instructions in [Customize the Microsoft 365 theme for your organization](../../admin/setup/customize-your-organization-theme.md) to upload your company logo.</span></span>
     - <span data-ttu-id="19c8d-300">**다음 URL을 다시 덮어치지 않습니다.** 이 설정에는 특정 권장이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="19c8d-300">**Do not rewrite the following URLs**: We have no specific recommendation for this setting.</span></span> <span data-ttu-id="19c8d-301">자세한 내용은 링크 정책의 "다음 URL을 다시 [금고 않습니다." 목록을 참조하세요.](safe-links.md#do-not-rewrite-the-following-urls-lists-in-safe-links-policies)</span><span class="sxs-lookup"><span data-stu-id="19c8d-301">For more information, see ["Do not rewrite the following URLs" lists in Safe Links policies](safe-links.md#do-not-rewrite-the-following-urls-lists-in-safe-links-policies).</span></span>
   - <span data-ttu-id="19c8d-302">**알림** 페이지:</span><span class="sxs-lookup"><span data-stu-id="19c8d-302">**Notification** page:</span></span>
     - <span data-ttu-id="19c8d-303">**사용자에게 어떻게 알리시겠습니까?** 섹션: 선택적으로 사용자  지정 알림 텍스트 사용을 선택하여 사용할 사용자 지정 알림 텍스트를 입력할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="19c8d-303">**How would you like to notify users?** section: Optionally, you can select **Use custom notification text** to enter customized notification text to use.</span></span> <span data-ttu-id="19c8d-304">자동 **지역화에** Microsoft 번역기 사용자 지정 알림 텍스트를 사용자 언어로 번역할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="19c8d-304">You can also select **Use Microsoft Translator for automatic localization** to translate the custom notification text into the user's language.</span></span> <span data-ttu-id="19c8d-305">그렇지 않은 경우 기본 알림 텍스트 사용을 **선택된 그대로** 떠날 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="19c8d-305">Otherwise, leave **Use the default notification text** selected.</span></span>

5. <span data-ttu-id="19c8d-306">완료되면 제출을 **클릭하고** 완료를 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="19c8d-306">When you're finished, click **Submit**, and then click **Done**.</span></span>

<span data-ttu-id="19c8d-307">금고 링크 정책 및 전역 설정을 구성하는 금고 지침은 다음 항목을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="19c8d-307">For detailed instructions for configuring Safe Links policies and global settings for Safe Links, see the following topics:</span></span>

- [<span data-ttu-id="19c8d-308">Microsoft Defender에서 금고 링크 정책 Office 365</span><span class="sxs-lookup"><span data-stu-id="19c8d-308">Set up Safe Links policies in Microsoft Defender for Office 365</span></span>](set-up-safe-links-policies.md)
- [<span data-ttu-id="19c8d-309">Microsoft Defender에서 금고 링크에 대한 전역 설정 Office 365</span><span class="sxs-lookup"><span data-stu-id="19c8d-309">Configure global settings for Safe Links in Microsoft Defender for Office 365</span></span>](configure-global-settings-for-safe-links.md)

### <a name="now-set-up-alerts-for-detected-files-in-sharepoint-online-or-onedrive-for-business"></a><span data-ttu-id="19c8d-310">이제 검색된 파일에 대한 알림을 SharePoint Online 또는 비즈니스용 OneDrive</span><span class="sxs-lookup"><span data-stu-id="19c8d-310">Now set up alerts for detected files in SharePoint Online or OneDrive for Business</span></span>

<span data-ttu-id="19c8d-311">SharePoint Online 또는 비즈니스용 OneDrive 파일이 악성으로 식별된 경우 알림을 받으기 위해 이 섹션에 설명된 바와 같이 경고를 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="19c8d-311">To receive notification when a file in SharePoint Online or OneDrive for Business has been identified as malicious, you can set up an alert as described in this section.</span></span>

1. <span data-ttu-id="19c8d-312">의 Microsoft 365 Defender 포털에서 전자 메일 & 공동 작업 정책 & <https://security.microsoft.com>  \> **정책** \> **으로 이동하세요.**</span><span class="sxs-lookup"><span data-stu-id="19c8d-312">In the Microsoft 365 Defender portal at <https://security.microsoft.com>, go to **Email & collaboration** \> **Polices & rules** \> **Alert policy**.</span></span>

2. <span data-ttu-id="19c8d-313">경고 **정책 페이지에서** 새 경고 **정책 을 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="19c8d-313">On the **Alert policy** page, click **New alert policy**.</span></span>

3. <span data-ttu-id="19c8d-314">새 **경고 정책 마법사가** 열립니다.</span><span class="sxs-lookup"><span data-stu-id="19c8d-314">The **New alert policy** wizard opens.</span></span> <span data-ttu-id="19c8d-315">이름 **페이지에서** 다음 설정을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="19c8d-315">On the **Name** page, configure the following settings:</span></span>
   - <span data-ttu-id="19c8d-316">**이름:** 고유하고 설명적인 이름을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="19c8d-316">**Name**: Enter a unique and descriptive name.</span></span> <span data-ttu-id="19c8d-317">예를 들어 라이브러리에 악성 파일을 입력할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="19c8d-317">For example, you could type Malicious Files in Libraries.</span></span>
   - <span data-ttu-id="19c8d-318">**설명:** 선택적 설명을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="19c8d-318">**Description**: Enter an optional description.</span></span>
   - <span data-ttu-id="19c8d-319">**심각도**: **낮음,** 중간 또는 **높음** **을 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="19c8d-319">**Severity**: Select **Low**, **Medium** or **High**.</span></span>
   - <span data-ttu-id="19c8d-320">**범주:** **위협 관리 를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="19c8d-320">**Category**: Select **Threat management**.</span></span>

   <span data-ttu-id="19c8d-321">완료되면 다음을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="19c8d-321">When you're finished, click **Next**</span></span>

4. <span data-ttu-id="19c8d-322">경고 **설정 만들기 페이지에서** 다음 설정을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="19c8d-322">On the **Create alert settings** page, configure the following settings:</span></span>
   - <span data-ttu-id="19c8d-323">**어떤 것을 경고하고 싶나요?** 섹션: **활동이** \> **파일에서 맬웨어가 검색되었습니다.**</span><span class="sxs-lookup"><span data-stu-id="19c8d-323">**What do you want to alert on?** section: **Activity is** \> **Detected malware in file**.</span></span>
   - <span data-ttu-id="19c8d-324">**경고를 트리거할** 방법 섹션: 활동이 규칙과 일치할 때마다 **확인이** 선택됩니다.</span><span class="sxs-lookup"><span data-stu-id="19c8d-324">**How do you want the alert to be triggered** section: Verify **Every time an activity matches the rule** is selected.</span></span>

   <span data-ttu-id="19c8d-325">완료되면 다음을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="19c8d-325">When you're finished, click **Next**</span></span>

5. <span data-ttu-id="19c8d-326">받는 **사람 설정 페이지에서** 다음 설정을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="19c8d-326">On the **Set your recipients** page, configure the following settings:</span></span>
   - <span data-ttu-id="19c8d-327">**전자 메일 알림 보내기:** 이 설정이 lclcted인지 확인</span><span class="sxs-lookup"><span data-stu-id="19c8d-327">**Send email notifications**: Verify this setting is selcted.</span></span>
   - <span data-ttu-id="19c8d-328">**전자 메일 받는 사람:** 악의적인 파일이 감지될 때 알림을 수신해야 하는 전역 관리자, 보안 관리자 또는 보안 독자를 하나 이상 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="19c8d-328">**Email recipients**: Select one or more global administrators, security administrators, or security readers who should receive notification when a malicious file is detected.</span></span>
   - <span data-ttu-id="19c8d-329">**일별 알림 제한:** **제한 없음이 선택되어** 있는지 확인</span><span class="sxs-lookup"><span data-stu-id="19c8d-329">**Daily notification limit**: Verify **No limit** is selected.</span></span>

   <span data-ttu-id="19c8d-330">완료되면 다음을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="19c8d-330">When you're finished, click **Next**</span></span>

6. <span data-ttu-id="19c8d-331">설정 **검토 페이지에서** 설정을 검토하고 **예,** 바로 켜기 선택되어 있는지 확인한 다음 마친을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="19c8d-331">On the **Review your settings** page, review your settings, verify **Yes, turn it on right away** is selected, and then click **Finish**</span></span>

<span data-ttu-id="19c8d-332">경고 정책에 대한 자세한 내용은 에서 [경고 정책을 Microsoft 365 규정 준수 센터.](../../compliance/alert-policies.md)</span><span class="sxs-lookup"><span data-stu-id="19c8d-332">To learn more about alert policies, see [Alert policies in the Microsoft 365 compliance center](../../compliance/alert-policies.md).</span></span>

> [!NOTE]
> <span data-ttu-id="19c8d-333">구성이 완료되면 다음 링크를 사용하여 작업 조사를 시작하세요.</span><span class="sxs-lookup"><span data-stu-id="19c8d-333">When you're finished configuring, use these links to start workload investigations:</span></span>
>
>- [<span data-ttu-id="19c8d-334">위협 방지 상태 보고서</span><span class="sxs-lookup"><span data-stu-id="19c8d-334">Threat protection status report</span></span>](view-email-security-reports.md#threat-protection-status-report)
>- [<span data-ttu-id="19c8d-335">Microsoft 365 Defender 포털을 사용하여 Defender for Office 365</span><span class="sxs-lookup"><span data-stu-id="19c8d-335">Use the Microsoft 365 Defender portal to manage quarantined files in Defender for Office 365</span></span>](manage-quarantined-messages-and-files.md#use-the-microsoft-365-defender-portal-to-manage-quarantined-files-in-defender-for-office-365)
>- [<span data-ttu-id="19c8d-336">SharePoint Online, OneDrive 또는 Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="19c8d-336">What to do when a malicious file is found in SharePoint Online, OneDrive, or Microsoft Teams</span></span>](https://support.microsoft.com/office/01e902ad-a903-4e0f-b093-1e1ac0c37ad2)
>- [<span data-ttu-id="19c8d-337">2016년 8월에 관리자로 quarantined messages and files Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="19c8d-337">Manage quarantined messages and files as an administrator in Microsoft 365</span></span>](manage-quarantined-messages-and-files.md)

## <a name="post-setup-tasks-and-next-steps"></a><span data-ttu-id="19c8d-338">설치 후 작업 및 다음 단계</span><span class="sxs-lookup"><span data-stu-id="19c8d-338">Post-setup tasks and next steps</span></span>

<span data-ttu-id="19c8d-339">위협 방지 기능을 구성한 후 해당 기능이 작동되는 방법을 모니터링해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="19c8d-339">After configuring the threat protection features, make sure to monitor how those features are working!</span></span> <span data-ttu-id="19c8d-340">필요한 작업을 할 수 있도록 정책을 검토하고 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="19c8d-340">Review and revise your policies so that they do what you need them to.</span></span> <span data-ttu-id="19c8d-341">또한 가치를 추가할 수 있는 새로운 기능 및 서비스 업데이트를 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="19c8d-341">Also, watch for new features and service updates that can add value.</span></span>

<br>

****

|<span data-ttu-id="19c8d-342">수행할 작업</span><span class="sxs-lookup"><span data-stu-id="19c8d-342">What to do</span></span>|<span data-ttu-id="19c8d-343">자세한 정보를 알아볼 수 있는 리소스</span><span class="sxs-lookup"><span data-stu-id="19c8d-343">Resources to learn more</span></span>|
|---|---|
|<span data-ttu-id="19c8d-344">보고서를 확인하여 위협 방지 기능이 조직에 어떻게 작동하고 있는지 확인</span><span class="sxs-lookup"><span data-stu-id="19c8d-344">See how threat protection features are working for your organization by viewing reports</span></span>|[<span data-ttu-id="19c8d-345">전자 메일 보안 보고서</span><span class="sxs-lookup"><span data-stu-id="19c8d-345">Email security reports</span></span>](view-email-security-reports.md) <p> [<span data-ttu-id="19c8d-346">Microsoft Defender for Office 365</span><span class="sxs-lookup"><span data-stu-id="19c8d-346">Reports for Microsoft Defender for Office 365</span></span>](view-reports-for-mdo.md) <p> [<span data-ttu-id="19c8d-347">위협 탐색기</span><span class="sxs-lookup"><span data-stu-id="19c8d-347">Threat Explorer</span></span>](threat-explorer.md)|
|<span data-ttu-id="19c8d-348">필요한 경우 위협 방지 정책을 주기적으로 검토하고 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="19c8d-348">Periodically review and revise your threat protection policies as needed</span></span>|[<span data-ttu-id="19c8d-349">Secure Score</span><span class="sxs-lookup"><span data-stu-id="19c8d-349">Secure Score</span></span>](../defender/microsoft-secure-score.md) <p> [<span data-ttu-id="19c8d-350">Microsoft 365 조사 및 대응 기능</span><span class="sxs-lookup"><span data-stu-id="19c8d-350">Microsoft 365 threat investigation and response features</span></span>](./office-365-ti.md)|
|<span data-ttu-id="19c8d-351">새로운 기능 및 서비스 업데이트 감시</span><span class="sxs-lookup"><span data-stu-id="19c8d-351">Watch for new features and service updates</span></span>|[<span data-ttu-id="19c8d-352">표준 및 대상 지정 릴리스 옵션</span><span class="sxs-lookup"><span data-stu-id="19c8d-352">Standard and Targeted release options</span></span>](../../admin/manage/release-options-in-office-365.md) <p> [<span data-ttu-id="19c8d-353">메시지 센터</span><span class="sxs-lookup"><span data-stu-id="19c8d-353">Message Center</span></span>](../../admin/manage/message-center.md) <p> [<span data-ttu-id="19c8d-354">Microsoft 365 로드맵</span><span class="sxs-lookup"><span data-stu-id="19c8d-354">Microsoft 365 Roadmap</span></span>](https://www.microsoft.com/microsoft-365/roadmap?filters=&searchterms=advanced%2Cthreat%2Cprotection) <p> [<span data-ttu-id="19c8d-355">서비스 설명</span><span class="sxs-lookup"><span data-stu-id="19c8d-355">Service Descriptions</span></span>](/office365/servicedescriptions/office-365-service-descriptions-technet-library)|
|
