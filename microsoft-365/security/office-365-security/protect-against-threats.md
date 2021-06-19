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
ms.openlocfilehash: 407838c815a85ce7c73322a0de176970ee93e537
ms.sourcegitcommit: c70067b4ef9c6f8f04aca68c35bb5141857c4e4b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/19/2021
ms.locfileid: "53029612"
---
# <a name="protect-against-threats"></a><span data-ttu-id="b7c99-103">위협에 대한 보호</span><span class="sxs-lookup"><span data-stu-id="b7c99-103">Protect against threats</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="b7c99-104">**적용 대상**</span><span class="sxs-lookup"><span data-stu-id="b7c99-104">**Applies to**</span></span>
- [<span data-ttu-id="b7c99-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="b7c99-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="b7c99-106">Office 365용 Microsoft Defender 플랜 1 및 플랜 2</span><span class="sxs-lookup"><span data-stu-id="b7c99-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="b7c99-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="b7c99-107">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

<span data-ttu-id="b7c99-108">다음은 2016에 대한 Defender의 구성을 청크로 Office 365 빠른 시작 가이드입니다.</span><span class="sxs-lookup"><span data-stu-id="b7c99-108">Here's a quick-start guide that breaks the configuration of Defender for Office 365 into chunks.</span></span> <span data-ttu-id="b7c99-109">새로운 위협 방지 기능을 Office 365 시작 위치를 잘 모를 수도 있으며, 를 수행하여 가장 잘 알 수 있는 경우 이 지침을 검사 목록 및 시작점으로 사용하세요.</span><span class="sxs-lookup"><span data-stu-id="b7c99-109">If you're new to threat protection features in Office 365, not sure where to begin, or if you learn best by *doing*, use this guidance as a checklist and a starting point.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="b7c99-110">**각 정책 종류에** 대한 초기 권장 설정이 포함되어 있습니다. 그러나 많은 옵션을 사용할 수 있으며 특정 조직의 요구에 맞게 설정을 조정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b7c99-110">**Initial recommended settings are included for each kind of policy; however, many options are available, and you can adjust your settings to meet your specific organization's needs**.</span></span> <span data-ttu-id="b7c99-111">정책 또는 변경 사항이 데이터 센터를 통해 작동하도록 약 30분 동안 허용합니다.</span><span class="sxs-lookup"><span data-stu-id="b7c99-111">Allow approximately 30 minutes for your policies or changes to work their way through your datacenter.</span></span>

## <a name="requirements"></a><span data-ttu-id="b7c99-112">요구 사항</span><span class="sxs-lookup"><span data-stu-id="b7c99-112">Requirements</span></span>

### <a name="subscriptions"></a><span data-ttu-id="b7c99-113">구독</span><span class="sxs-lookup"><span data-stu-id="b7c99-113">Subscriptions</span></span>

<span data-ttu-id="b7c99-114">위협 방지 기능은 모든 *Microsoft* 또는 Office 365 포함되어 있습니다. 그러나 일부 구독에는 고급 기능이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b7c99-114">Threat protection features are included in *all* Microsoft or Office 365 subscriptions; however, some subscriptions have advanced features.</span></span> <span data-ttu-id="b7c99-115">아래 표에는 이 문서에 포함된 보호 기능과 최소 구독 요구 사항이 나열됩니다.</span><span class="sxs-lookup"><span data-stu-id="b7c99-115">The table below lists the protection features included in this article together with the minimum subscription requirements.</span></span>

> [!TIP]
> <span data-ttu-id="b7c99-116">감사를 켜는 지시 이외에 단계는 **EOP(맬웨어** 방지) 의 일부로 표시된 맬웨어 방지, 피싱 방지 및 스팸 방지를 Office 365 Exchange Online Protection 있습니다. </span><span class="sxs-lookup"><span data-stu-id="b7c99-116">Notice that, beyond the directions to turn on auditing, *steps* start anti-malware, anti-phishing, and anti-spam, which are marked as part of Office 365 Exchange Online Protection (**EOP**).</span></span> <span data-ttu-id="b7c99-117">(에 대한 **Defender** for Office 365) EOP를 포함하고 빌드할 때까지 이 문서에서 이 Office 365 이상한 것처럼 보일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b7c99-117">This can seem odd in an Defender for Office 365 article, until you remember (**Defender for Office 365**) contains, and builds on, EOP.</span></span>

<br>

****

|<span data-ttu-id="b7c99-118">보호 유형</span><span class="sxs-lookup"><span data-stu-id="b7c99-118">Protection type</span></span>|<span data-ttu-id="b7c99-119">구독 요구 사항</span><span class="sxs-lookup"><span data-stu-id="b7c99-119">Subscription requirement</span></span>|
|---|---|
|<span data-ttu-id="b7c99-120">감사 로깅(보고 목적으로)</span><span class="sxs-lookup"><span data-stu-id="b7c99-120">Audit logging (for reporting purposes)</span></span>|[<span data-ttu-id="b7c99-121">Exchange Online</span><span class="sxs-lookup"><span data-stu-id="b7c99-121">Exchange Online</span></span>](/office365/servicedescriptions/exchange-online-service-description/exchange-online-service-description)|
|<span data-ttu-id="b7c99-122">맬웨어 방지 보호 기능</span><span class="sxs-lookup"><span data-stu-id="b7c99-122">Anti-malware protection</span></span>|<span data-ttu-id="b7c99-123">[](/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description) **Exchange Online Protection(EOP)**</span><span class="sxs-lookup"><span data-stu-id="b7c99-123">[Exchange Online Protection](/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description) (**EOP**)</span></span>|
|<span data-ttu-id="b7c99-124">피싱 방지 보호 기능</span><span class="sxs-lookup"><span data-stu-id="b7c99-124">Anti-phishing protection</span></span>|[<span data-ttu-id="b7c99-125">EOP</span><span class="sxs-lookup"><span data-stu-id="b7c99-125">EOP</span></span>](/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description)|
|<span data-ttu-id="b7c99-126">스팸 방지 보호 기능</span><span class="sxs-lookup"><span data-stu-id="b7c99-126">Anti-spam protection</span></span>|[<span data-ttu-id="b7c99-127">EOP</span><span class="sxs-lookup"><span data-stu-id="b7c99-127">EOP</span></span>](/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description)|
|<span data-ttu-id="b7c99-128">제로 아워 자동 제거(전자 메일용)</span><span class="sxs-lookup"><span data-stu-id="b7c99-128">Zero-hour auto purge (for email)</span></span>|[<span data-ttu-id="b7c99-129">EOP</span><span class="sxs-lookup"><span data-stu-id="b7c99-129">EOP</span></span>](/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description)|
|<span data-ttu-id="b7c99-130">전자 메일 및 전자 메일 문서의 악의적인 URL 및 Office 파일 보호(Safe 링크 및 Safe 첨부 파일)</span><span class="sxs-lookup"><span data-stu-id="b7c99-130">Protection from malicious URLs and files in email and Office documents (Safe Links and Safe Attachments)</span></span>|[<span data-ttu-id="b7c99-131">Office 365용 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="b7c99-131">Microsoft Defender for Office 365</span></span>](/office365/servicedescriptions/office-365-advanced-threat-protection-service-description)|
|<span data-ttu-id="b7c99-132">작업 Safe, SharePoint, OneDrive 및 Microsoft Teams 설정</span><span class="sxs-lookup"><span data-stu-id="b7c99-132">Turn on Safe Attachments for SharePoint, OneDrive, and Microsoft Teams workloads</span></span>|[<span data-ttu-id="b7c99-133">Office 365용 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="b7c99-133">Microsoft Defender for Office 365</span></span>](turn-on-mdo-for-spo-odb-and-teams.md)|
|<span data-ttu-id="b7c99-134">지능형 피싱 방지 보호</span><span class="sxs-lookup"><span data-stu-id="b7c99-134">Advanced anti-phishing protection</span></span>|[<span data-ttu-id="b7c99-135">Office 365용 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="b7c99-135">Microsoft Defender for Office 365</span></span>](/office365/servicedescriptions/office-365-advanced-threat-protection-service-description)|

### <a name="roles-and-permissions"></a><span data-ttu-id="b7c99-136">역할 및 사용 권한</span><span class="sxs-lookup"><span data-stu-id="b7c99-136">Roles and permissions</span></span>

<span data-ttu-id="b7c99-137">정책에 대해 Defender를 Office 365 보안 및 준수 센터에서 [적절한 역할을 & 합니다.](/office365/servicedescriptions/office-365-platform-service-description/office-365-securitycompliance-center)</span><span class="sxs-lookup"><span data-stu-id="b7c99-137">To configure Defender for Office 365 policies, you must be assigned an appropriate role in the [Security & Compliance Center](/office365/servicedescriptions/office-365-platform-service-description/office-365-securitycompliance-center).</span></span> <span data-ttu-id="b7c99-138">아래 표에서 이러한 작업을 수행할 수 있는 역할을 확인하세요.</span><span class="sxs-lookup"><span data-stu-id="b7c99-138">Take a look at the table below for roles that can do these actions.</span></span>

<br>

****

|<span data-ttu-id="b7c99-139">역할 또는 역할 그룹</span><span class="sxs-lookup"><span data-stu-id="b7c99-139">Role or role group</span></span>|<span data-ttu-id="b7c99-140">자세한 내용을 알아보는 위치</span><span class="sxs-lookup"><span data-stu-id="b7c99-140">Where to learn more</span></span>|
|---|---|
|<span data-ttu-id="b7c99-141">전역 관리자</span><span class="sxs-lookup"><span data-stu-id="b7c99-141">global administrator</span></span>|[<span data-ttu-id="b7c99-142">Microsoft 365 관리자 역할 정보</span><span class="sxs-lookup"><span data-stu-id="b7c99-142">About Microsoft 365 admin roles</span></span>](../../admin/add-users/about-admin-roles.md)|
|<span data-ttu-id="b7c99-143">보안 관리자</span><span class="sxs-lookup"><span data-stu-id="b7c99-143">Security Administrator</span></span>|[<span data-ttu-id="b7c99-144">Azure Active Directory의 관리자 역할 권한</span><span class="sxs-lookup"><span data-stu-id="b7c99-144">Administrator role permissions in Azure Active Directory</span></span>](/azure/active-directory/users-groups-roles/directory-assign-admin-roles)|
|<span data-ttu-id="b7c99-145">Exchange Online 조직 관리</span><span class="sxs-lookup"><span data-stu-id="b7c99-145">Exchange Online Organization Management</span></span>|[<span data-ttu-id="b7c99-146">Exchange Online의 사용 권한</span><span class="sxs-lookup"><span data-stu-id="b7c99-146">Permissions in Exchange Online</span></span>](/exchange/permissions-exo/permissions-exo) <p> <span data-ttu-id="b7c99-147">및</span><span class="sxs-lookup"><span data-stu-id="b7c99-147">and</span></span> <p> [<span data-ttu-id="b7c99-148">Exchange Online PowerShell</span><span class="sxs-lookup"><span data-stu-id="b7c99-148">Exchange Online PowerShell</span></span>](/powershell/exchange/exchange-online-powershell)|
|

<span data-ttu-id="b7c99-149">자세한 내용은 [Security & Compliance Center의 사용 권한을 참조합니다.](permissions-in-the-security-and-compliance-center.md)</span><span class="sxs-lookup"><span data-stu-id="b7c99-149">To learn more, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

### <a name="turn-on-audit-logging-for-reporting-and-investigation"></a><span data-ttu-id="b7c99-150">보고 및 조사에 대한 감사 로깅 켜기</span><span class="sxs-lookup"><span data-stu-id="b7c99-150">Turn on Audit logging for reporting and investigation</span></span>

- <span data-ttu-id="b7c99-151">감사 로깅을 조기 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="b7c99-151">Start your audit logging early.</span></span> <span data-ttu-id="b7c99-152">다음 단계 중 일부에 대해 **감사를 ON으로** 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b7c99-152">You'll need auditing to be **ON** for some of the following steps.</span></span> <span data-ttu-id="b7c99-153">감사 로깅은 을(를) 포함 하는 [구독에서 사용할 Exchange Online.](/office365/servicedescriptions/exchange-online-service-description/exchange-online-service-description)</span><span class="sxs-lookup"><span data-stu-id="b7c99-153">Audit logging is available in subscriptions that include [Exchange Online](/office365/servicedescriptions/exchange-online-service-description/exchange-online-service-description).</span></span> <span data-ttu-id="b7c99-154">보안 대시보드, 전자 메일 보안 보고서 [](security-dashboard.md)및 탐색기 등의 위협 [](threat-explorer.md)방지 보고서에서 데이터를 확인하려면 감사 로깅이 에 있어야 *합니다.* [](view-email-security-reports.md)</span><span class="sxs-lookup"><span data-stu-id="b7c99-154">In order to view data in threat protection reports, such as the [Security Dashboard](security-dashboard.md), [email security reports](view-email-security-reports.md), and [Explorer](threat-explorer.md), audit logging must be *On*.</span></span> <span data-ttu-id="b7c99-155">자세한 내용은 감사 로그 검색 켜기 또는 [끄기 를 참조합니다.](../../compliance/turn-audit-log-search-on-or-off.md)</span><span class="sxs-lookup"><span data-stu-id="b7c99-155">To learn more, see [Turn audit log search on or off](../../compliance/turn-audit-log-search-on-or-off.md).</span></span>

## <a name="part-1---anti-malware-protection-in-eop"></a><span data-ttu-id="b7c99-156">1부 - EOP의 맬웨어 방지 보호</span><span class="sxs-lookup"><span data-stu-id="b7c99-156">Part 1 - Anti-malware protection in EOP</span></span>

<span data-ttu-id="b7c99-157">맬웨어 방지에 대한 권장 설정에 대한 자세한 내용은 EOP 맬웨어 방지 정책 [설정 을 참조하세요.](recommended-settings-for-eop-and-office365.md#eop-anti-malware-policy-settings)</span><span class="sxs-lookup"><span data-stu-id="b7c99-157">For more information about the recommended settings for anti-malware, see [EOP anti-malware policy settings](recommended-settings-for-eop-and-office365.md#eop-anti-malware-policy-settings).</span></span>

1. <span data-ttu-id="b7c99-158">을 를 열 <https://security.microsoft.com/antimalwarev2> 수 있습니다</span><span class="sxs-lookup"><span data-stu-id="b7c99-158">Open <https://security.microsoft.com/antimalwarev2>.</span></span>

2. <span data-ttu-id="b7c99-159">**맬웨어 방지 페이지에서** 이름을 클릭하여  기본 정책이라는 정책을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="b7c99-159">On the **Anti-malware** page, select the policy named **Default** policy by clicking on the name.</span></span>

3. <span data-ttu-id="b7c99-160">정책 세부 정보 플라이아웃이 열리면 보호 설정 편집을 **클릭하고** 다음 설정을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="b7c99-160">In the policy details flyout that opens, click **Edit protection settings**, and then configure the following settings:</span></span>
   - <span data-ttu-id="b7c99-161">공통 **첨부 파일 필터** 사용 을 선택하여 공통 첨부 파일 필터를 켜야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b7c99-161">Select **Enable the common attachments filter** to turn on the common attachments filter.</span></span> <span data-ttu-id="b7c99-162">파일 **형식 사용자 지정을 클릭하여** 파일 형식을 더 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="b7c99-162">Click **Customize file types** to add more file types.</span></span>
   - <span data-ttu-id="b7c99-163">**맬웨어에 대한 제로 아워 자동 제거 사용이 선택되어 있는지** 확인</span><span class="sxs-lookup"><span data-stu-id="b7c99-163">Verify that **Enable zero-hour auto purge for malware** is selected.</span></span>
   - <span data-ttu-id="b7c99-164">알림 섹션의 설정이 **선택되어 있는지** 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="b7c99-164">Verify that none of the settings in the **Notification** section are selected.</span></span>

   <span data-ttu-id="b7c99-165">작업을 마쳤으면 **저장** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="b7c99-165">When you're finished, click **Save**.</span></span>

4. <span data-ttu-id="b7c99-166">정책 세부 정보 플라이아웃으로 돌아와 **닫기** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="b7c99-166">Back on the policy details flyout, click **Close**.</span></span>

<span data-ttu-id="b7c99-167">맬웨어 방지 정책을 구성하는 방법에 대한 자세한 내용은 EOP에서 맬웨어 방지 [정책 구성을 참조하세요.](configure-anti-malware-policies.md)</span><span class="sxs-lookup"><span data-stu-id="b7c99-167">For detailed instructions for configuring anti-malware policies, see [Configure anti-malware policies in EOP](configure-anti-malware-policies.md).</span></span>

## <a name="part-2---anti-phishing-protection-in-eop-and-defender-for-office-365"></a><span data-ttu-id="b7c99-168">2부 - EOP의 피싱 방지 보호 기능 및 EOP용 Defender Office 365</span><span class="sxs-lookup"><span data-stu-id="b7c99-168">Part 2 - Anti-phishing protection in EOP and Defender for Office 365</span></span>

<span data-ttu-id="b7c99-169">[피싱 방지 보호는](anti-phishing-protection.md) EOP를 포함 하는 [구독에서 사용할 수 있습니다.](/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description)</span><span class="sxs-lookup"><span data-stu-id="b7c99-169">[Anti-phishing protection](anti-phishing-protection.md) is available in subscriptions that include [EOP](/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description).</span></span> <span data-ttu-id="b7c99-170">고급 피싱 방지 보호는 에 대한 [Defender에서](/office365/servicedescriptions/office-365-advanced-threat-protection-service-description)사용할 수 Office 365.</span><span class="sxs-lookup"><span data-stu-id="b7c99-170">Advanced anti-phishing protection is available in [Defender for Office 365](/office365/servicedescriptions/office-365-advanced-threat-protection-service-description).</span></span>

<span data-ttu-id="b7c99-171">피싱 방지 정책에 대한 권장 설정에 대한 자세한 내용은 [EOP](recommended-settings-for-eop-and-office365.md#eop-anti-phishing-policy-settings) 피싱 방지 정책 설정 및 Microsoft Defender for [Office 365.](recommended-settings-for-eop-and-office365.md#anti-phishing-policy-settings-in-microsoft-defender-for-office-365)</span><span class="sxs-lookup"><span data-stu-id="b7c99-171">For more information about the recommended settings for anti-phishing policies, see [EOP anti-phishing policy settings](recommended-settings-for-eop-and-office365.md#eop-anti-phishing-policy-settings) and [Anti-phishing policy settings in Microsoft Defender for Office 365](recommended-settings-for-eop-and-office365.md#anti-phishing-policy-settings-in-microsoft-defender-for-office-365).</span></span>

<span data-ttu-id="b7c99-172">다음 절차에서는 기본 피싱 방지 정책을 구성하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="b7c99-172">The following procedure describes how to configure the default anti-phishing policy.</span></span> <span data-ttu-id="b7c99-173">설정 Defender에서만 사용할 수 있는 Office 365 명확하게 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="b7c99-173">Settings that are only available in Defender for Office 365 are clearly marked.</span></span>

1. <span data-ttu-id="b7c99-174">을 를 열 <https://security.microsoft.com/antiphishing> 수 있습니다</span><span class="sxs-lookup"><span data-stu-id="b7c99-174">Open <https://security.microsoft.com/antiphishing>.</span></span>

2. <span data-ttu-id="b7c99-175">피싱 **방지 페이지에서** 이름을 클릭하여 **Office365 AntiPhish Default(기본값)라는** 정책을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="b7c99-175">On the **Anti-phishing** page, select the policy named **Office365 AntiPhish Default (Default)** by clicking on the name.</span></span>

3. <span data-ttu-id="b7c99-176">나타나는 정책 세부 정보 플라이아웃에서 다음 설정을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="b7c99-176">In the policy details flyout that appears, configure the following settings:</span></span>

   - <span data-ttu-id="b7c99-177">**피싱 임계값 &** 보호 섹션:  보호 설정 편집을 클릭하고  보호 설정 편집 플라이아웃에서 다음 설정을 구성합니다. 이 플라이아웃이 열립니다.</span><span class="sxs-lookup"><span data-stu-id="b7c99-177">**Phishing threshold & protection** section: Click **Edit protection settings** and configure the following settings in the **Edit protection settings** flyout that opens:</span></span>
     - <span data-ttu-id="b7c99-178">**피싱 전자 메일 임계값:** <sup>\*</sup> **2 - 적극적(표준)** 또는 **3 - 보다 적극적(엄격)을** 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="b7c99-178">**Phishing email threshold**<sup>\*</sup>: Select **2 - Aggressive** (Standard) or **3 - More Aggressive** (Strict).</span></span>
     - <span data-ttu-id="b7c99-179">**가장 섹션:** <sup>\*</sup> 다음 값을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="b7c99-179">**Impersonation** section<sup>\*</sup>: Configure the following values:</span></span>
       - <span data-ttu-id="b7c99-180">사용자가 **보호할** 수 있도록 설정을 선택하고 나타나는 **(nn)** 보낸 사람 관리 링크를 클릭한 다음 조직의 보드 구성원, CEO, CFO 및 기타 고위 리더와 같은 가장으로부터 보호하기 위해 내부 및 외부 보낸 사람 추가를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="b7c99-180">Select **Enable users to protect**, click the **Manage (nn) sender(s)** link that appears, and then add internal and external senders to protect from impersonation, such as your organization's board members, your CEO, CFO, and other senior leaders.</span></span>
       - <span data-ttu-id="b7c99-181">을 **보호하려면** 도메인 사용 을 선택한 다음 나타나는 다음 설정을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="b7c99-181">Select **Enable domains to protect**, and then configure the following settings that appear:</span></span>
         - <span data-ttu-id="b7c99-182">허용 **도메인의** 내부 보낸 사람(내 도메인 보기 클릭)을 가장에서 보호하려면 소유한 도메인 포함을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="b7c99-182">Select **Include domains I own** to protect internal senders in your accepted domains (visible by clicking **View my domains**) from impersonation.</span></span>
         - <span data-ttu-id="b7c99-183">다른 도메인의 보낸 사람 보호하려면 사용자 지정 도메인 포함을 선택하고 나타나는 **관리(nn)** 사용자 지정 도메인 링크를 클릭한 다음 가장으로부터 보호할 다른 도메인을 추가합니다. </span><span class="sxs-lookup"><span data-stu-id="b7c99-183">To protect senders in other domains, select **Include custom domains**, click the **Manage (nn) custom domain(s)** link that appears, and then add other domains to protect from impersonation.</span></span>
     - <span data-ttu-id="b7c99-184">**신뢰할** 수 있는 보낸 사람 및 도메인 추가 <sup>\*</sup> 섹션: **관리(nn)** 신뢰할 수 있는 보낸 사람 및 도메인을 클릭하여 필요한 경우 가장 보호로 보낸 사람 및 보낸 사람 도메인 예외를 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="b7c99-184">**Add trusted senders and domains** section <sup>\*</sup>: Click **Manage (nn) trusted sender(s) and domains(s)** to configure sender and sender domain exceptions to impersonation protection if needed.</span></span>
     - <span data-ttu-id="b7c99-185">사서함 인텔리전스 설정: 사서함 인텔리전스 사용 및 가장 방지를 위한 인텔리전스 사용이 <sup>\*</sup> 선택되어 있는지  확인합니다. </span><span class="sxs-lookup"><span data-stu-id="b7c99-185">Mailbox intelligence settings <sup>\*</sup>: Verify that **Enable mailbox intelligence** and **Enable intelligence for impersonation protection** are selected.</span></span>
     - <span data-ttu-id="b7c99-186">**스푸핑 섹션:** **스푸핑 인텔리전스 사용이 선택되어 있는지** 확인</span><span class="sxs-lookup"><span data-stu-id="b7c99-186">**Spoof** section: Verify **Enable spoof intelligence** is selected.</span></span>

     <span data-ttu-id="b7c99-187">작업을 마쳤으면 **저장** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="b7c99-187">When you're finished, click **Save**.</span></span>

   - <span data-ttu-id="b7c99-188">**작업** 섹션: 작업 **편집을** 클릭하고 작업 편집 플라이아웃에서 열리도록 다음 **설정을** 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="b7c99-188">**Actions** section: Click **Edit actions** and configure the following settings in the **Edit actions** flyout that opens:</span></span>
     - <span data-ttu-id="b7c99-189">**메시지 작업** 섹션: 다음 설정을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="b7c99-189">**Message actions** section: Configure the following settings:</span></span>
       - <span data-ttu-id="b7c99-190">**가장된** 사용자로 메시지가 검색된 경우 : 메시지 을 선택하여 을 <sup>\*</sup> **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="b7c99-190">**If message is detected as an impersonated user**<sup>\*</sup>: Select **Quarantine the message**.</span></span>
       - <span data-ttu-id="b7c99-191">**가장된** 도메인으로 메시지가 검색된 경우 : 메시지 을 선택하여 을 <sup>\*</sup> **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="b7c99-191">**If message is detected as an impersonated domain**<sup>\*</sup>: Select **Quarantine the message**.</span></span>
       - <span data-ttu-id="b7c99-192">**사서함 인텔리전스에서** 가장된 사용자를 검색하는 경우 : 받는 사람의 정크 메일 폴더로 메시지 이동(표준) 또는 메시지 검역(엄격)을 <sup>\*</sup> 선택합니다.  </span><span class="sxs-lookup"><span data-stu-id="b7c99-192">**If mailbox intelligence detects an impersonated user**<sup>\*</sup>: Select **Move message to the recipients' Junk Email folders** (Standard) or **Quarantine the message** (Strict).</span></span>
       - <span data-ttu-id="b7c99-193">**메시지가 스푸핑으로** 검색된 경우  : 받는 사람의 정크 메일 폴더로 메시지  이동(표준) 또는 메시지 검량(엄격)을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="b7c99-193">**If message is detected as spoof**: Select **Move message to the recipients' Junk Email folders** (Standard) or **Quarantine the message** (Strict).</span></span>
     - <span data-ttu-id="b7c99-194">**안전 팁 & 표시기** 섹션: 다음 설정을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="b7c99-194">**Safety tips & indicators** section: Configure the following settings:</span></span>
       - <span data-ttu-id="b7c99-195">**첫 번째 연락처 보안 팁**: 선택(켜기)을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="b7c99-195">**Show first contact safety tip**: Select (turn on).</span></span>
       - <span data-ttu-id="b7c99-196">**사용자 가장 표시** 보안 팁 <sup>\*</sup> : 선택(켜기)을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="b7c99-196">**Show user impersonation safety tip**<sup>\*</sup>: Select (turn on).</span></span>
       - <span data-ttu-id="b7c99-197">**도메인 가장 표시** <sup>\*</sup> 보안 팁 : 선택(켜기)을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="b7c99-197">**Show domain impersonation safety tip**<sup>\*</sup>: Select (turn on).</span></span>
       - <span data-ttu-id="b7c99-198">**사용자 가장 비정상 문자** 보안 팁 <sup>\*</sup> : 선택(켜기)을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="b7c99-198">**Show user impersonation unusual characters safety tip**<sup>\*</sup>: Select (turn on).</span></span>
       - <span data-ttu-id="b7c99-199">**스푸핑에** 대해 확인되지 않은 보낸 사람에 대한 표시(?) : 선택(켜기)을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="b7c99-199">**Show (?) for unauthenticated senders for spoof**: Select (turn on).</span></span>
       - <span data-ttu-id="b7c99-200">**"via" 태그 표시**: 선택(켜기)입니다.</span><span class="sxs-lookup"><span data-stu-id="b7c99-200">**Show "via" tag**: Select (turn on).</span></span>

     <span data-ttu-id="b7c99-201">작업을 마쳤으면 **저장** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="b7c99-201">When you're finished, click **Save**.</span></span>

   <span data-ttu-id="b7c99-202"><sup>\*</sup>이 설정은 사용자용 Defender에서만 사용할 Office 365.</span><span class="sxs-lookup"><span data-stu-id="b7c99-202"><sup>\*</sup> This setting is available only in Defender for Office 365.</span></span>

4. <span data-ttu-id="b7c99-203">**저장을** 클릭한 다음 **닫기 클릭**</span><span class="sxs-lookup"><span data-stu-id="b7c99-203">Click **Save** and then click **Close**</span></span>

<span data-ttu-id="b7c99-204">피싱 방지 정책을 구성하는 방법에 대한 자세한 내용은 [EOP에서](configure-anti-phishing-policies-eop.md) 피싱 방지 정책 구성 및 Microsoft [Defender에서](configure-mdo-anti-phishing-policies.md)피싱 방지 정책 구성을 Office 365.</span><span class="sxs-lookup"><span data-stu-id="b7c99-204">For detailed instructions for configuring anti-phishing policies, see [Configure anti-phishing policies in EOP](configure-anti-phishing-policies-eop.md) and [Configure anti-phishing policies in Microsoft Defender for Office 365](configure-mdo-anti-phishing-policies.md).</span></span>

## <a name="part-3---anti-spam-protection-in-eop"></a><span data-ttu-id="b7c99-205">3부 - EOP의 스팸 방지 보호 기능</span><span class="sxs-lookup"><span data-stu-id="b7c99-205">Part 3 - Anti-spam protection in EOP</span></span>

<span data-ttu-id="b7c99-206">스팸 방지에 대한 권장 설정에 대한 자세한 내용은 EOP 스팸 방지 정책 [설정 을 참조하세요.](recommended-settings-for-eop-and-office365.md#eop-anti-spam-policy-settings)</span><span class="sxs-lookup"><span data-stu-id="b7c99-206">For more information about the recommended settings for anti-spam, see [EOP anti-spam policy settings](recommended-settings-for-eop-and-office365.md#eop-anti-spam-policy-settings).</span></span>

1. <span data-ttu-id="b7c99-207">을 를 열 <https://security.microsoft.com/antispam> 수 있습니다</span><span class="sxs-lookup"><span data-stu-id="b7c99-207">Open <https://security.microsoft.com/antispam>.</span></span>

2. <span data-ttu-id="b7c99-208">스팸 **방지 정책** 페이지에서 이름을 클릭하여 목록에서 스팸 방지 인바운드 정책(기본값)이라는 정책을 선택합니다. </span><span class="sxs-lookup"><span data-stu-id="b7c99-208">On the **Anti-spam policies** page, select the policy named **Anti-spam inbound policy (Default)** from the list by clicking on the name.</span></span>

3. <span data-ttu-id="b7c99-209">나타나는 정책 세부 정보 플라이아웃에서 다음 단계를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="b7c99-209">In the policy details flyout that appears, do the following steps:</span></span>
   - <span data-ttu-id="b7c99-210">**스팸 속성 & 대량** 전자 메일 임계값: 스팸 임계값 및 속성 **편집을 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="b7c99-210">**Bulk email threshold & spam properties** section: Click **Edit spam threshold and properties**.</span></span> <span data-ttu-id="b7c99-211">나타나는 **스팸 임계값** 및 속성 플라이아웃에서  대량 전자 메일 임계값을 5(Strict) 또는 6(표준)으로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="b7c99-211">In the **spam threshold and properties** flyout that appears, set the **Bulk email threshold** value to 5 (Strict) or 6 (Standard).</span></span> <span data-ttu-id="b7c99-212">작업을 마쳤으면 **저장** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="b7c99-212">When you're finished, click **Save**.</span></span>
   - <span data-ttu-id="b7c99-213">**허용 및 차단된 보낸** 사람 및 도메인 섹션: 허용된 보낸 사람 및 허용 도메인을 검토하거나 편집합니다.</span><span class="sxs-lookup"><span data-stu-id="b7c99-213">**Allowed and blocked senders and domains** section: Review or edit your allowed senders and allowed domains.</span></span>

4. <span data-ttu-id="b7c99-214">작업을 마쳤으면 **닫기** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="b7c99-214">When you're finished, click **Close**.</span></span>

<span data-ttu-id="b7c99-215">스팸 방지 정책을 구성하는 방법에 대한 자세한 내용은 [EOP에서 스팸 방지 정책 구성을 참조하세요.](configure-your-spam-filter-policies.md)</span><span class="sxs-lookup"><span data-stu-id="b7c99-215">For detailed instructions for configuring anti-spam policies, see [Configure anti-spam policies in EOP](configure-your-spam-filter-policies.md).</span></span>

## <a name="part-4---protection-from-malicious-urls-and-files-safe-links-and-safe-attachments-in-defender-for-office-365"></a><span data-ttu-id="b7c99-216">4부 - 악의적인 URL 및 파일로부터 보호(Safe Defender의 링크 및 Safe 첨부 Office 365 파일)</span><span class="sxs-lookup"><span data-stu-id="b7c99-216">Part 4 - Protection from malicious URLs and files (Safe Links and Safe Attachments in Defender for Office 365)</span></span>

<span data-ttu-id="b7c99-217">악성 URL 및 파일로부터 클릭 시간 보호는 Microsoft [Defender for](/office365/servicedescriptions/office-365-advanced-threat-protection-service-description)Office 365.</span><span class="sxs-lookup"><span data-stu-id="b7c99-217">Time-of-click protection from malicious URLs and files is available in subscriptions that include [Microsoft Defender for Office 365](/office365/servicedescriptions/office-365-advanced-threat-protection-service-description).</span></span> <span data-ttu-id="b7c99-218">첨부 파일 및 링크 Safe [정책을](safe-attachments.md) [통해 Safe](safe-links.md) 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="b7c99-218">It's set up through [Safe Attachments](safe-attachments.md) and [Safe Links](safe-links.md) policies.</span></span>

### <a name="safe-attachments-policies-in-microsoft-defender-for-office-365"></a><span data-ttu-id="b7c99-219">Safe Microsoft Defender for Office 365</span><span class="sxs-lookup"><span data-stu-id="b7c99-219">Safe Attachments policies in Microsoft Defender for Office 365</span></span>

<span data-ttu-id="b7c99-220">첨부 파일을 [Safe](safe-attachments.md)하나 이상의 링크 정책을 Safe.</span><span class="sxs-lookup"><span data-stu-id="b7c99-220">To set up [Safe Attachments](safe-attachments.md), create at least one Safe Links policy.</span></span>

1. <span data-ttu-id="b7c99-221">보안 및 [& 센터에서](https://protection.office.com)위협  관리 정책 ATP 및 첨부 Safe 를 선택한 다음 \>  \> 만들기를 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="b7c99-221">In the [Security & Compliance Center](https://protection.office.com), choose **Threat management** \> **Policy** \> **ATP Safe Attachments**, and then click **Create**.</span></span>

2. <span data-ttu-id="b7c99-222">나타나는 **새** Safe 첨부 파일 정책 마법사에서 다음 설정을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="b7c99-222">In the **New Safe Attachments policy** wizard that appears, configure the following settings:</span></span>

   - <span data-ttu-id="b7c99-223">이름 **상자에** `Block malware` 를 입력하고 다음 을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="b7c99-223">In the **Name** box, type `Block malware`, and then click **Next**.</span></span>

   - <span data-ttu-id="b7c99-224">설정 **페이지에서** 다음 설정을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="b7c99-224">On the **Settings** page, configure the following settings:</span></span>
     - <span data-ttu-id="b7c99-225">첨부 Safe 알 수 **없는 맬웨어 응답 섹션에서** 차단 을 **선택하세요.**</span><span class="sxs-lookup"><span data-stu-id="b7c99-225">In the **Safe attachments unknown malware response** section, choose **Block**.</span></span>
     - <span data-ttu-id="b7c99-226">첨부 파일 **리디렉션 섹션에서** 리디렉션 사용 **옵션을 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="b7c99-226">In the **Redirect attachment** section, select the option **Enable redirect**.</span></span> <span data-ttu-id="b7c99-227">검색된 파일을 검토할 조직의 보안 관리자 또는 운영자의 전자 메일 주소를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="b7c99-227">Specify the email address for your organization's security administrator or operator, who will review detected files.</span></span>

     <span data-ttu-id="b7c99-228">**다음** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="b7c99-228">Click **Next**.</span></span>

3. <span data-ttu-id="b7c99-229">적용 **대상** 페이지에서 조건 추가를 클릭하고 적용 대상인 경우 적용을 **선택합니다.** 받는 사람 도메인이 입니다. **추가를** 클릭하고 도메인 또는 도메인을 선택하고 **추가,** 완료를 클릭한 후 다음을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="b7c99-229">On the **Applied to** page, click **Add a condition**, choose **Applied if: The recipient domain is**, click **Add**, select your domain or domains, click **Add**, click **Done**, and then click **Next**.</span></span>

4. <span data-ttu-id="b7c99-230">설정을 검토하고 마친 을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="b7c99-230">Review your settings and then click **Finish**.</span></span>

### <a name="safe-links-policies-in-microsoft-defender-for-office-365"></a><span data-ttu-id="b7c99-231">Safe Microsoft Defender for Office 365</span><span class="sxs-lookup"><span data-stu-id="b7c99-231">Safe Links policies in Microsoft Defender for Office 365</span></span>

<span data-ttu-id="b7c99-232">링크 Safe [설정하려면](safe-links.md)Safe 링크에 대한 전역 설정을 검토하고 편집하고 하나 이상의 Safe 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b7c99-232">To set up [Safe Links](safe-links.md), review and edit your global settings for Safe Links, and create at least one Safe Links policy.</span></span>

1. <span data-ttu-id="b7c99-233">보안 & 준수 [센터에서](https://protection.office.com)위협  관리 정책 ATP Safe 링크를 선택하고 전역 설정을 클릭한 후 다음 설정을 \>  \> 구성합니다. </span><span class="sxs-lookup"><span data-stu-id="b7c99-233">In the [Security & Compliance Center](https://protection.office.com), choose **Threat management** \> **Policy** \> **ATP Safe Links**, and click **Global settings**, and then configure the following settings:</span></span>

   - <span data-ttu-id="b7c99-234">다음에서 **Safe 사용 확인:** Office 365 응용 프로그램이 켜져 있습니다. ![ 토글합니다. ](../../media/scc-toggle-on.png)</span><span class="sxs-lookup"><span data-stu-id="b7c99-234">Verify **Use Safe Links in: Office 365 applications** is turned on: ![Toggle on](../../media/scc-toggle-on.png).</span></span>
   - <span data-ttu-id="b7c99-235">**사용자가 링크를 클릭하는 Safe** 추적하지 않습니다. 사용자 클릭을 추적하려면 이 설정을 해제합니다. ![ 토글 끄기. ](../../media/scc-toggle-off.png)</span><span class="sxs-lookup"><span data-stu-id="b7c99-235">**Do not track when users click Safe Links**: Turn this setting off to track user clicks: ![Toggle off](../../media/scc-toggle-off.png).</span></span>
   - <span data-ttu-id="b7c99-236">**사용자가 원래 URL에 대한 안전한** 링크를 클릭할 수 없습니다. 이 설정이 켜져 있는지 확인합니다. ![ 토글합니다. ](../../media/scc-toggle-on.png)</span><span class="sxs-lookup"><span data-stu-id="b7c99-236">**Do not let users click through safe links to original URL**: Verify this setting is turned on: ![Toggle on](../../media/scc-toggle-on.png).</span></span>

   <span data-ttu-id="b7c99-237">작업을 마쳤으면 **저장** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="b7c99-237">When you're finished, click **Save**.</span></span>

2. <span data-ttu-id="b7c99-238">기본 Safe 페이지로 돌아가서 만들기를 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="b7c99-238">Back on the main Safe Links page, click **Create**.</span></span>

3. <span data-ttu-id="b7c99-239">나타나는 **링크 Safe** 만들기 정책 마법사에서 다음 설정을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="b7c99-239">In the **Create Safe Links policy** wizard that appears, configure the following settings:</span></span>

   - <span data-ttu-id="b7c99-240">이름 **상자에** 과 같은 이름을 입력하고 `Safe Links` 다음 을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="b7c99-240">In the **Name** box, type a name, such as `Safe Links`, and then click **Next**.</span></span>

   - <span data-ttu-id="b7c99-241">설정 **페이지에서** 다음 설정을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="b7c99-241">On the **Settings** page, configure the following settings:</span></span>
     - <span data-ttu-id="b7c99-242">**메시지에서 알 수 없는 악의적인 URL에** 대한 작업 선택: 을 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="b7c99-242">**Select the action for unknown potentially malicious URLs in messages**: Choose **On**.</span></span>
     - <span data-ttu-id="b7c99-243">**에서 알 수 없는 URL** 또는 잠재적으로 악의적인 URL에 대한 작업을 Microsoft Teams : 을 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="b7c99-243">**Select the action for unknown or potentially malicious URLs within Microsoft Teams**: Choose **On**.</span></span>
     - <span data-ttu-id="b7c99-244">**조직 내에서 보낸 전자 메일 메시지에 안전한 링크 적용**</span><span class="sxs-lookup"><span data-stu-id="b7c99-244">**Apply safe links to email messages sent within the organization**</span></span>
     - <span data-ttu-id="b7c99-245">**메시지를 배달하기 전에 URL 검색이 완료될 때까지 기다렸다가**</span><span class="sxs-lookup"><span data-stu-id="b7c99-245">**Wait for URL scanning to complete before delivering the message**</span></span>
     - <span data-ttu-id="b7c99-246">**조직 내에서 보낸 전자 메일 메시지에 안전한 링크 적용**</span><span class="sxs-lookup"><span data-stu-id="b7c99-246">**Apply safe links to email messages sent within the organization**</span></span>
     - <span data-ttu-id="b7c99-247">**사용자가 원래 URL을 클릭할 수 있도록 허용 안 하세요.**</span><span class="sxs-lookup"><span data-stu-id="b7c99-247">**Do not allow users to click through to original URL**</span></span>

     <span data-ttu-id="b7c99-248">**다음** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="b7c99-248">Click **Next**</span></span>

4. <span data-ttu-id="b7c99-249">적용 **대상** 페이지에서 조건 추가를 클릭하고 적용 대상인 경우 적용을 **선택합니다.** 받는 사람 도메인이 입니다. **추가를** 클릭하고 도메인 또는 도메인을 선택하고 **추가,** 완료를 클릭한 후 다음을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="b7c99-249">On the **Applied to** page, click **Add a condition**, choose **Applied if: The recipient domain is**, click **Add**, select your domain or domains, click **Add**, click **Done**, and then click **Next**.</span></span>

5. <span data-ttu-id="b7c99-250">설정을 검토하고 마친 을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="b7c99-250">Review your settings and then click **Finish**.</span></span>

<span data-ttu-id="b7c99-251">자세한 내용은 [안전한 링크 정책 설정](set-up-safe-links-policies.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="b7c99-251">To learn more, see [Set up Safe Links policies](set-up-safe-links-policies.md).</span></span>

## <a name="part-5---verify-safe-attachments-for-sharepoint-onedrive-and-microsoft-teams-is-turned-on"></a><span data-ttu-id="b7c99-252">5부 - Safe, SharePoint, OneDrive 및 Microsoft Teams 첨부 파일이 켜져 있는지 확인</span><span class="sxs-lookup"><span data-stu-id="b7c99-252">Part 5 - Verify Safe Attachments for SharePoint, OneDrive, and Microsoft Teams is turned on</span></span>

<span data-ttu-id="b7c99-253">SharePoint, OneDrive 및 Teams 작업은 공동 작업을 위해 구축됩니다.</span><span class="sxs-lookup"><span data-stu-id="b7c99-253">Workloads like SharePoint, OneDrive, and Teams are built for collaboration.</span></span> <span data-ttu-id="b7c99-254">팀 사이트에 Defender를 Office 365 팀 사이트 및 문서 라이브러리에서 악성으로 식별된 파일을 차단하고 검색하는 데 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b7c99-254">Using Defender for Office 365 helps with blocking and detection of files that are identified as malicious in team sites and document libraries.</span></span> <span data-ttu-id="b7c99-255">작동 방식에 대한 자세한 내용은 을(를) 읽어 [볼 수 있습니다.](mdo-for-spo-odb-and-teams.md)</span><span class="sxs-lookup"><span data-stu-id="b7c99-255">You can read more about how that works [here](mdo-for-spo-odb-and-teams.md).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="b7c99-256">**이 절차를 시작하기** 전에 사용자 환경 에 대해 감사 로깅이 Microsoft 365 합니다.</span><span class="sxs-lookup"><span data-stu-id="b7c99-256">**Before you begin this procedure, make sure that audit logging is already turned on for your Microsoft 365 environment**.</span></span> <span data-ttu-id="b7c99-257">이 작업은 일반적으로 감사 로그 역할이 할당된 사용자가 Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="b7c99-257">This is typically done by someone who has the Audit Logs role assigned in Exchange Online.</span></span> <span data-ttu-id="b7c99-258">자세한 내용은 감사 로그 검색 켜기 또는 [끄기!를 참조하세요.](../../compliance/turn-audit-log-search-on-or-off.md)</span><span class="sxs-lookup"><span data-stu-id="b7c99-258">For more information, see [Turn audit log search on or off](../../compliance/turn-audit-log-search-on-or-off.md)!</span></span>

1. <span data-ttu-id="b7c99-259">보안 및 [& 센터에서](https://protection.office.com)위협  관리 정책 ATP Safe 첨부 파일을 선택한 다음 \>  \> **전역** 설정을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="b7c99-259">In the [Security & Compliance Center](https://protection.office.com), choose **Threat management** \> **Policy** \> **ATP Safe Attachments**, and then click **Global settings**.</span></span>

2. <span data-ttu-id="b7c99-260">Office 365, SharePoint, OneDrive 및 Microsoft Teams 토글에 대한 **Defender** 켜기 설정이 오른쪽에 있는지 확인: ![ 을 토글하고 ](../../media/scc-toggle-on.png) 저장을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="b7c99-260">Verify the **Turn on Defender for Office 365 for SharePoint, OneDrive, and Microsoft Teams** toggle is to the right: ![Toggle on](../../media/scc-toggle-on.png), and then click **Save**.</span></span>

3. <span data-ttu-id="b7c99-261">조직의 첨부 파일 정책 및 Safe 정책 [](set-up-safe-attachments-policies.md) 및 링크 정책을 Safe [검토합니다(적절한 경우 편집).](set-up-safe-links-policies.md)</span><span class="sxs-lookup"><span data-stu-id="b7c99-261">Review (and, as appropriate, edit) your organization's [Safe Attachments policies](set-up-safe-attachments-policies.md) and [Safe Links policies](set-up-safe-links-policies.md).</span></span>

4. <span data-ttu-id="b7c99-262">(권장) 전역 관리자 또는 SharePoint Online 관리자로서 _DisallowInfectedFileDownload_ 매개 변수를 로 설정하여 **[Set-SPOTenant](/powershell/module/sharepoint-online/Set-SPOTenant)** cmdlet을 실행합니다. `$true`</span><span class="sxs-lookup"><span data-stu-id="b7c99-262">(Recommended) As a global administrator or a SharePoint Online administrator, run the **[Set-SPOTenant](/powershell/module/sharepoint-online/Set-SPOTenant)** cmdlet with the _DisallowInfectedFileDownload_ parameter set to `$true`.</span></span>

   - <span data-ttu-id="b7c99-263">`$true` 검색된 파일에 대한 모든 작업(삭제 제외)을 차단합니다.</span><span class="sxs-lookup"><span data-stu-id="b7c99-263">`$true` blocks all actions (except Delete) for detected files.</span></span> <span data-ttu-id="b7c99-264">검색된 파일을 열거나 이동, 복사 또는 공유할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="b7c99-264">People cannot open, move, copy, or share detected files.</span></span>
   - <span data-ttu-id="b7c99-265">`$false` 삭제 및 다운로드를 제외한 모든 작업을 차단합니다.</span><span class="sxs-lookup"><span data-stu-id="b7c99-265">`$false` blocks all actions except Delete and Download.</span></span> <span data-ttu-id="b7c99-266">사람들은 위험을 수락하고 검색된 파일을 다운로드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b7c99-266">People can choose to accept the risk and download a detected file.</span></span>

   > [!TIP]
   > <span data-ttu-id="b7c99-267">PowerShell과 함께 PowerShell을 사용하는 Microsoft 365 자세한 내용은 [PowerShell을 사용하여 Microsoft 365 관리를 참조합니다.](../../enterprise/manage-microsoft-365-with-microsoft-365-powershell.md)</span><span class="sxs-lookup"><span data-stu-id="b7c99-267">To learn more about using PowerShell with Microsoft 365, see [Manage Microsoft 365 with PowerShell](../../enterprise/manage-microsoft-365-with-microsoft-365-powershell.md).</span></span>

5. <span data-ttu-id="b7c99-268">모든 데이터 센터에 변경 내용을 분산하는 데 최대 30분 Microsoft 365 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b7c99-268">Allow up to 30 minutes for your changes to spread to all Microsoft 365 datacenters.</span></span>

### <a name="now-set-up-alerts-for-detected-files"></a><span data-ttu-id="b7c99-269">이제 검색된 파일에 대한 경고 설정</span><span class="sxs-lookup"><span data-stu-id="b7c99-269">Now set up alerts for detected files</span></span>

<span data-ttu-id="b7c99-270">SharePoint Online, 비즈니스용 OneDrive 또는 Microsoft Teams 파일이 악성으로 식별된 경우 알림을 받으면 경고를 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b7c99-270">To receive notification when a file in SharePoint Online, OneDrive for Business, or Microsoft Teams has been identified as malicious, you can set up an alert.</span></span>

1. <span data-ttu-id="b7c99-271">보안 및 [& 센터에서](https://protection.office.com) **경고** 관리 \> **를 선택 합니다.**</span><span class="sxs-lookup"><span data-stu-id="b7c99-271">In the [Security & Compliance Center](https://protection.office.com), choose **Alerts** \> **Manage alerts**.</span></span>

2. <span data-ttu-id="b7c99-272">새 **경고 정책 을 선택 합니다.**</span><span class="sxs-lookup"><span data-stu-id="b7c99-272">Choose **New alert policy**.</span></span>

3. <span data-ttu-id="b7c99-273">경고의 이름을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="b7c99-273">Specify a name for the alert.</span></span> <span data-ttu-id="b7c99-274">예를 들어 라이브러리에 악성 파일을 입력할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b7c99-274">For example, you could type Malicious Files in Libraries.</span></span>

4. <span data-ttu-id="b7c99-275">경고에 대한 설명을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="b7c99-275">Type a description for the alert.</span></span> <span data-ttu-id="b7c99-276">예를 들어 online, SharePoint 또는 OneDrive 파일에서 악성 파일이 검색되면 관리자에게 OneDrive 수 Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="b7c99-276">For example, you could type Notifies admins when malicious files are detected in SharePoint Online, OneDrive, or Microsoft Teams.</span></span>

5. <span data-ttu-id="b7c99-277">다음의 **경우 이 경고 보내기... 섹션에서** 다음을 설정하세요.</span><span class="sxs-lookup"><span data-stu-id="b7c99-277">In the **Send this alert when...** section, set:</span></span>

   <span data-ttu-id="b7c99-278">a.</span><span class="sxs-lookup"><span data-stu-id="b7c99-278">a.</span></span> <span data-ttu-id="b7c99-279">활동 **목록에서** **파일에서 검색된 맬웨어를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="b7c99-279">In the **Activities** list, choose **Detected malware in file**.</span></span>

   <span data-ttu-id="b7c99-280">b.</span><span class="sxs-lookup"><span data-stu-id="b7c99-280">b.</span></span> <span data-ttu-id="b7c99-281">사용자 **필드는 비워** 두면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b7c99-281">Leave the **Users** field empty.</span></span>

6. <span data-ttu-id="b7c99-282">이 **알림 보내기...** 섹션에서 악의적인 파일이 감지될 때 알림을 수신해야 하는 전역 관리자, 보안 관리자 또는 보안 독자를 하나 이상 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="b7c99-282">In the **Send this alert to...** section, select one or more global administrators, security administrators, or security readers who should receive notification when a malicious file is detected.</span></span>

7. <span data-ttu-id="b7c99-283">**를 저장합니다.**</span><span class="sxs-lookup"><span data-stu-id="b7c99-283">**Save**.</span></span>

<span data-ttu-id="b7c99-284">경고에 대한 자세한 내용은 보안 및 준수 센터에서 활동 [& 참조합니다.](../../compliance/create-activity-alerts.md)</span><span class="sxs-lookup"><span data-stu-id="b7c99-284">To learn more about alerts, see [Create activity alerts in the Security & Compliance Center](../../compliance/create-activity-alerts.md).</span></span>

> [!NOTE]
> <span data-ttu-id="b7c99-285">구성이 완료되면 다음 링크를 사용하여 작업 조사를 시작하세요.</span><span class="sxs-lookup"><span data-stu-id="b7c99-285">When you're finished configuring, use these links to start workload investigations:</span></span>
>
>- [<span data-ttu-id="b7c99-286">위협 방지 상태 보고서</span><span class="sxs-lookup"><span data-stu-id="b7c99-286">Threat protection status report</span></span>](view-email-security-reports.md#threat-protection-status-report)
>- [<span data-ttu-id="b7c99-287">Microsoft 365 Defender 포털을 사용하여 Defender for Office 365</span><span class="sxs-lookup"><span data-stu-id="b7c99-287">Use the Microsoft 365 Defender portal to manage quarantined files in Defender for Office 365</span></span>](manage-quarantined-messages-and-files.md#use-the-microsoft-365-defender-portal-to-manage-quarantined-files-in-defender-for-office-365)
>- [<span data-ttu-id="b7c99-288">SharePoint Online, OneDrive 또는 Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="b7c99-288">What to do when a malicious file is found in SharePoint Online, OneDrive, or Microsoft Teams</span></span>](https://support.microsoft.com/office/01e902ad-a903-4e0f-b093-1e1ac0c37ad2)
>- [<span data-ttu-id="b7c99-289">2016년 8월에 관리자로 quarantined messages and files Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="b7c99-289">Manage quarantined messages and files as an administrator in Microsoft 365</span></span>](manage-quarantined-messages-and-files.md)

## <a name="part-6---additional-settings-to-configure"></a><span data-ttu-id="b7c99-290">6부 - 구성할 추가 설정</span><span class="sxs-lookup"><span data-stu-id="b7c99-290">Part 6 - Additional settings to configure</span></span>

<span data-ttu-id="b7c99-291">맬웨어, 악의적인 URL 및 파일, 피싱 및 스팸으로부터 보호를 구성하는 것과 함께 제로 아워 자동 제거를 구성하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="b7c99-291">Along with configuring protection from malware, malicious URLs and files, phishing, and spam, we recommend you configure zero-hour auto purge.</span></span>

### <a name="zero-hour-auto-purge-for-email-in-eop"></a><span data-ttu-id="b7c99-292">EOP에서 전자 메일에 대한 제로 아워 자동 제거</span><span class="sxs-lookup"><span data-stu-id="b7c99-292">Zero-hour auto purge for email in EOP</span></span>

<span data-ttu-id="b7c99-293">[ZAP(제로](zero-hour-auto-purge.md) 아워 자동 제거)는 EOP를 포함 하는 [구독에서 사용할 수 있습니다.](/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description)</span><span class="sxs-lookup"><span data-stu-id="b7c99-293">[Zero-hour auto purge](zero-hour-auto-purge.md) (ZAP) is available in subscriptions that include [EOP](/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description).</span></span> <span data-ttu-id="b7c99-294">이 보호는 기본적으로 켜져 있습니다. 그러나 보호를 적용하려면 다음 조건을 충족해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b7c99-294">This protection is turned on by default; however, the following conditions must be met for protection to be in effect:</span></span>

- <span data-ttu-id="b7c99-295">스팸 작업은 스팸 방지 정책에서 메시지를 **정크** 메일 폴더로 [이동으로 설정됩니다.](anti-spam-protection.md)</span><span class="sxs-lookup"><span data-stu-id="b7c99-295">Spam actions are set to **Move message to Junk Email folder** in [anti-spam policies](anti-spam-protection.md).</span></span>

- <span data-ttu-id="b7c99-296">사용자는 기본 정크 메일 설정을 유지하며 정크 메일 보호를 해제하지 않습니다. [](configure-junk-email-settings-on-exo-mailboxes.md)</span><span class="sxs-lookup"><span data-stu-id="b7c99-296">Users have kept their default [junk email settings](configure-junk-email-settings-on-exo-mailboxes.md), and haven't turned off junk email protection.</span></span>

<span data-ttu-id="b7c99-297">자세한 내용은 제로 아워 자동 제거 - 스팸 및 맬웨어로부터 [보호를 참조합니다.](zero-hour-auto-purge.md)</span><span class="sxs-lookup"><span data-stu-id="b7c99-297">To learn more, see [Zero-hour auto purge - protection against spam and malware](zero-hour-auto-purge.md).</span></span>

## <a name="post-setup-tasks-and-next-steps"></a><span data-ttu-id="b7c99-298">설치 후 작업 및 다음 단계</span><span class="sxs-lookup"><span data-stu-id="b7c99-298">Post-setup tasks and next steps</span></span>

<span data-ttu-id="b7c99-299">위협 방지 기능을 구성한 후 해당 기능이 작동되는 방법을 모니터링해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b7c99-299">After configuring the threat protection features, make sure to monitor how those features are working!</span></span> <span data-ttu-id="b7c99-300">필요한 작업을 할 수 있도록 정책을 검토하고 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="b7c99-300">Review and revise your policies so that they do what you need them to.</span></span> <span data-ttu-id="b7c99-301">또한 가치를 추가할 수 있는 새로운 기능 및 서비스 업데이트를 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="b7c99-301">Also, watch for new features and service updates that can add value.</span></span>

****

|<span data-ttu-id="b7c99-302">수행할 작업</span><span class="sxs-lookup"><span data-stu-id="b7c99-302">What to do</span></span>|<span data-ttu-id="b7c99-303">자세한 정보를 알아볼 수 있는 리소스</span><span class="sxs-lookup"><span data-stu-id="b7c99-303">Resources to learn more</span></span>|
|---|---|
|<span data-ttu-id="b7c99-304">보고서를 확인하여 위협 방지 기능이 조직에 어떻게 작동하고 있는지 확인</span><span class="sxs-lookup"><span data-stu-id="b7c99-304">See how threat protection features are working for your organization by viewing reports</span></span>|[<span data-ttu-id="b7c99-305">보안 대시보드</span><span class="sxs-lookup"><span data-stu-id="b7c99-305">Security dashboard</span></span>](security-dashboard.md) <p> [<span data-ttu-id="b7c99-306">전자 메일 보안 보고서</span><span class="sxs-lookup"><span data-stu-id="b7c99-306">Email security reports</span></span>](view-email-security-reports.md) <p> [<span data-ttu-id="b7c99-307">Microsoft Defender for Office 365</span><span class="sxs-lookup"><span data-stu-id="b7c99-307">Reports for Microsoft Defender for Office 365</span></span>](view-reports-for-mdo.md) <p> [<span data-ttu-id="b7c99-308">위협 탐색기</span><span class="sxs-lookup"><span data-stu-id="b7c99-308">Threat Explorer</span></span>](threat-explorer.md)|
|<span data-ttu-id="b7c99-309">필요한 경우 위협 방지 정책을 주기적으로 검토하고 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="b7c99-309">Periodically review and revise your threat protection policies as needed</span></span>|[<span data-ttu-id="b7c99-310">Secure Score</span><span class="sxs-lookup"><span data-stu-id="b7c99-310">Secure Score</span></span>](../defender/microsoft-secure-score.md) <p> [<span data-ttu-id="b7c99-311">스마트 보고서 및 인사이트</span><span class="sxs-lookup"><span data-stu-id="b7c99-311">Smart reports and insights</span></span>](reports-and-insights-in-security-and-compliance.md) <p> [<span data-ttu-id="b7c99-312">Microsoft 365 조사 및 대응 기능</span><span class="sxs-lookup"><span data-stu-id="b7c99-312">Microsoft 365 threat investigation and response features</span></span>](./office-365-ti.md)|
|<span data-ttu-id="b7c99-313">새로운 기능 및 서비스 업데이트 감시</span><span class="sxs-lookup"><span data-stu-id="b7c99-313">Watch for new features and service updates</span></span>|[<span data-ttu-id="b7c99-314">표준 및 대상 지정 릴리스 옵션</span><span class="sxs-lookup"><span data-stu-id="b7c99-314">Standard and Targeted release options</span></span>](../../admin/manage/release-options-in-office-365.md) <p> [<span data-ttu-id="b7c99-315">메시지 센터</span><span class="sxs-lookup"><span data-stu-id="b7c99-315">Message Center</span></span>](../../admin/manage/message-center.md) <p> [<span data-ttu-id="b7c99-316">Microsoft 365 로드맵</span><span class="sxs-lookup"><span data-stu-id="b7c99-316">Microsoft 365 Roadmap</span></span>](https://www.microsoft.com/microsoft-365/roadmap?filters=&searchterms=advanced%2Cthreat%2Cprotection) <p> [<span data-ttu-id="b7c99-317">서비스 설명</span><span class="sxs-lookup"><span data-stu-id="b7c99-317">Service Descriptions</span></span>](/office365/servicedescriptions/office-365-service-descriptions-technet-library)|
|<span data-ttu-id="b7c99-318">EOP 및 Defender for Office 365</span><span class="sxs-lookup"><span data-stu-id="b7c99-318">Learn the details about recommended Standard and Strict security configurations for EOP and Defender for Office 365</span></span>|[<span data-ttu-id="b7c99-319">EOP 및 Microsoft Defender 보안에 대한 Office 365 설정</span><span class="sxs-lookup"><span data-stu-id="b7c99-319">Recommended settings for EOP and Microsoft Defender for Office 365 security</span></span>](recommended-settings-for-eop-and-office365.md)|
